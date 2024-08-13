# Olah Data Semarang
# WhatsApp : +6285227746673
# IG : @olahdatasemarang_
# Doubly robust nonparametric estimation and inference Use drtmle With (In) R Software
# Nonparametric estimators of the average treatment effect with doubly-robust confidence intervals and hypothesis tests Use drtmle With (In) R Software
install.packages("drtmle")
library("drtmle")
library("SuperLearner")
drtmle = read.csv("https://raw.githubusercontent.com/timbulwidodostp/drtmle/main/drtmle/drtmle.csv",sep = ";")
# Estimation Doubly robust nonparametric estimation and inference Use drtmle With (In) R Software
A <- drtmle$A
Y <- drtmle$Y
W1 <- drtmle$W1
W2 <- drtmle$W2
W <- data.frame(W1, W2)
drtmle_univariate<-drtmle(W=W,A=A,Y=Y,family= binomial(),glm_g="W1+W2",glm_Q="W1+W2*A",glm_gr="Qn",glm_Qr="gn",stratify=FALSE)
drtmle_univariate
ci(drtmle_univariate)
wald_test(drtmle_univariate)
drtmle_bivariate<-drtmle(W=W,A=A,Y=Y,family=binomial(),glm_g="W1+W2",glm_Q="W1+ W2*A",glm_gr="Qn",glm_Qr="gn",stratify=FALSE,reduction="bivariate")
drtmle_bivariate
ci(drtmle_bivariate)
wald_test(drtmle_bivariate)
# Doubly robust nonparametric estimation and inference Use drtmle With (In) R Software
# Nonparametric estimators of the average treatment effect with doubly-robust confidence intervals and hypothesis tests Use drtmle With (In) R Software
# Olah Data Semarang
# WhatsApp : +6285227746673
# IG : @olahdatasemarang_
# Finished