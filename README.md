# Exchangeable Convertible Bond Valuation

A convertible bond issuer pays periodic coupons to the convertible bond holder. The bond holder can convert the bond into the underlying stock within the period(s) of time specified by the conversion schedule. The bond issuer can call the bond and the holder can put it according to the call and put provisions. 

The Exchangeable feature assumes that the convertible bond and the underlying stock are issued by different parties. There are two possible cases with respect to stock conversion:

·  covered: the bond issuer holds the underlying stock for the life time of the
convertible;
·  vulnerable: the bond issuer does not hold the stock prior to the stock conversion.

We assume a convertible bond that is specified by
	(t1, t2, …, tM) 	- the set of coupon dates, tM is also the bond maturity date;
	(c1, c2, …, cM) 	- the set of coupons, each coupon payable on the respective coupon date;
	P			- the bond principal, payable at maturity date, tM.
	Tx 			- the exercise date on which the bond can be converted into the
  underlying stock, which pays dividends. 

We consider discrete dividends that are specified by absolute amounts paid at pre-determined times.  In particular we assume that an absolute amount,  , is paid at a time,  , for  , where   (here   is the convertible’s maturity).   We model the stock price based on a Hull-White approach.  Specifically, let

	  denote a capital gains process,
	  represent the stock price,
	  denote the bond issuer’s default time.

Let
 						(1)

for  , where   is a deterministic risk-free rate.  We then assume that
 ,			(2)

for  , where 
	  is a deterministic hazard-rate,
	 

(here we set  ).

Furthermore the process   satisfies, under the risk-neutral probability measure, an SDE of the form
 					(3)
where
	  is a constant volatility parameter,
	  is a standard Brownian motion,
	 .							(4)

Thus,
 						(5)

Let
	Tj    be the dividend date immediately after the option maturity date, 
i.e. Tj = min(T1, T2, …, TN) such that Tj  Tx, where (T1, …, TN) is the set of dividend payment dates;
	tm     is the coupon date immediately after the option maturity date, 
i.e. tm = min(t1, t2, …, tM) such that tm   Tx.

Then 
S_(T_x )=(G_(T_x )+e^∫_0^(T_x)▒〖(r+h)ds〗 ∑_(i=j)^N▒d_i  e^(-∫_0^(T_i)▒rds) ) 1_(τ>T_x )=e^∫_0^(T_x)▒〖(r+h)ds〗 (G_0 e^(-σ^2/2 T_x+σW_(T_x ) )+∑_(i=j)^N▒d_i  e^(-∫_0^(T_i)▒rds) ) 1_(τ>T_x ) (6)

Using arguments similar to those used in ref [1] one can show that the Tx-time price of the straight bond (see https://finpricing.com/lib/FiZeroBond.html),  , is
		 				(7)

and its present value is
 					(8)

If the conversion ratio is , the present value of the conversion option is  V=E(├ e^(-∫_0^(T_x)▒rds)  max⁡(γS_(T_x )-B_(T_x ),0) ┤| F_0 )=
=E[max⁡(e^∫_0^(T_x)▒hds γ(G_0 e^(-σ^2/2 t+σW)+∑_(i=j)^N▒d_i  e^(-∫_0^(T_i)▒rds) ) 1_(τ>T_x )-(Pe^(-∫_0^T▒rds) e^(-∫_(T_x)^T▒hds)+∑_(k=m)^M▒〖c_k e^(-∫_0^(t_k)▒rds) e^(-∫_(T_x)^(t_k)▒hds) 〗) 1_(τ>T_x ),0) ├|F_0 ┤]=
=e^∫_0^(T_x)▒hds E[max⁡((γG_0 e^(-σ^2/2 t+σW)+γ∑_(i=j)^N▒d_i  e^(-∫_0^(T_i)▒rds)-Pe^(-∫_0^T▒〖(r+h)ds〗)-∑_(k=m)^M▒〖c_k e^(-∫_0^(t_k)▒〖(r+h)ds〗) 〗) 1_(τ>T_x ),0) ├|F_0 ┤]

Using the assumption that the time to default process is independent from the Brownian motion process, Wt,  that drives the capital gain process (see ref[1]), and the fact that the probability of default before time Tx, P(τ>T_x)=〖exp⁡(-∫_0^(T_x)▒hds)〗^,  we get further
			V=E[max⁡((γG_0 e^(-σ^2/2 t+σW)-K),0) ├|F_0 ┤]	(9)	
where

K=Pe^(-∫_0^T▒〖(r+h)ds〗)+∑_(k=m)^M▒〖c_k e^(-∫_0^(t_k)▒〖(r+h)ds〗) 〗-γ∑_(i=j)^N▒d_i  e^(-∫_0^(T_i)▒rds)≡B_(0,T_x )-γPV(remngDvd)	(10)	

Finally, one gets
 		(11)	

where
 ,								(12)
		 ,							(13)
		 ,							(14)

and   is the standard normal cumulative distribution function.
 
The convertible bond price is 
 						(15)
where V is given by eq. (9) and  by eq. (8).


