# websim
The repository has python programmes I am developing to simulate on websim by worldquant
#import scipy as sp
#from numpy import *
#import scipy.stats as ss
#delay=DELAY
##dr is the Data Registry
#valid = dr.GetData("UNIVID")
#Lines above will be added as a common header to your code, without "#".
# -------------------------Write your code below------------------------
import scipy as sp
from numpy import *
import scipy.stats as ss
delay = 0
dr = WQSim_DataRegistry.Instance()
volume = dr.GetData("volume")
returns = dr.GetData("returns")
sales_growth = dr.GetData("sales_growth")
sales = dr.GetData("sales")
est_sales = dr.GetData("est_sales")
revenue = dr.GetData("revenue")
goodwill = dr.GetData("goodwill")
income = dr.GetData("income")

def Generate(di,alpha):
  alpha[:] = volume[di-delay, :] + returns[di-delay,:] # + ss.rankdata(sales_growth[di-delay,:]) + (ss.rankdata(sales[di-delay,:]) - ss.rankdata(est_sales[di-delay,:])) + ss.rankdata(revenue[di-delay,:]) + ss.rankdata(goodwill[di-delay,:]) + ss.rankdata(income[di-delay,:])
  #alpha[:] = where(valid[di-delay,:],alpha[:],nan)
  







#Python code is copyright © 2001-2014 Python Software Foundation. All Rights Reserved
