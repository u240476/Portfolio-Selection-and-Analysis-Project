# Portfolio-Selection-and-Analysis-Project
This project uses finacial and economic theory and mathematics to optimise investment around user inputed specifications. 
My goal is to bridge the gap between new and experienced investors to allow users to create wealth and maximise the return on their investments without needed a background in finance or paying for a financial advisor.

## Project Structure
<pre>
project-root/
├── src/
│   └── main/
│       └── java/
│           └── com/example/project/
│               └── TradingBotv2.java       # Main class with 21 calculation methods
│
├── src/
│   └── test/
│       └── java/
│           └── com/example/project/
│               └── Tradingbotv2Test.java  # Unit tests for Calculator methods
│
├── pom.xml                               # Maven build configuration
├── README.md                             # Project documentation
└── .gitignore                             # Files/folders Git should ignore
</pre>
## Core Project Methods and Their Functions
###static double CalculatingExpReturnonCAL(double TPExpectedReturn, double weightInTP)
 -> Calculates Expected return for the special case that the portfolio is on the capital allocation line.

### static double[] CalculatingForGivenReturn(double[][] inverse, double[] ExpReturns, double R)
 -> Calculates the weights for the portfolio on the efficient frontier for a user inputed level of standard deviation This      is one of our optimal portfolios, we can use the weights to calculate the optimal portfolios metrics.

### static double[] CalculatingForGivenRisk(double[][] inverse, double[] ExpReturns, double STDV)
 -> Calculates the weights for the portfolio on the efficient frontier for a user inputed level of standard deviation This      is one of our optimal portfolios, we can use the weights to calculate the optimal portfolios metrics.

### static org.ojalgo.optimisation.Optimisation.Result CalculatingMVPWeights(double[][] covariance)
 -> Calculates the Minimum Variance Portfolio, one of our optimal portfolios.

### static double CalculatingPortfolioReturn(double[] EmonthlyReturns, double[] Weights)
 -> Calculates the portfolios expected returns.

### static double CalculatingPortfolioSTDV(double variance)
 -> Calculates a portfolios standard deviation.

### static double CalculatingPortfolioVariance(double[][] coVar, double[] weights)
 -> Calculates the portfolios variance.

### static double[][] CalculatingReturnMatrix(double[][] rawData)
 -> Finds logarithmic returns {ln(ri+1/ri)} for the securites using their historic price data.

### static double CalculatingSharpeRatio(double STDV, double ExpReturn, double Rf)
 -> Calculates the Sharpe Ratio for the tangency portfolio This allows us to construct the capital allocation line.

### static double CalculatingSTDVonCAL(double TPStandardDeviation, double weightInTP)
 -> Calculates standard deviation for the special case that the portfolio is on the capital allocation line.

### static double[] CalculatingStockSTDV(double[] variance)
 -> Calculates the standard deviaton of the securities using their variance.

### static double[] CalculatingTangencyPortfolio(double[][] inverse, double[] ExpReturns, double rf)
 -> Calculates the Tangency portfolio, one of our optimal portfolios This portfolio has the highest return to risk ratio of     any possible portfolio given the selected securities.

### static double[] CalculatingUserWeights(double[] proportions)
 -> Calculates the weights in the users current portfolio with these weights we can calculate the portfolios metrics and        compare them to our optimal portfolios.

### static double[] CalculatingVariance(double[][] returns, double[] averageReturns)
 -> Calculates the variance of the securities based on logarithmic and average returns.

### static double[] CovarianceTerms(double[][] CoVar)
 -> Extracts the covaraince terms from the covariance matrix.

### static double[] downloadYahooAdjClose(String ticker, long startUnix, long endUnix, String interval)
 -> Helper method for GetPriceMatrix that performs the API call, downloads the returns and returns them to GetPriceMatrix.

### static double[] ExpectedMonthlyReturns(double[][] returnData)
 -> Calculates average monthly returns based on logarithmic returns.

### static double[][] getPriceMatrix(String[] tickers, Calendar start, Calendar end, String yahooInterval)
 -> Sets up an API call to Yahoo Finance to get 10 years of historic data for the securities chosen by the user.

### static void main(String[] args)
 -> main method asks the user to input how many securities they would like to invest in and their ticker values makes calls     to the 20 other methods in the project to allow them to optimise their investing Asks user to input the interval they       would like to use also asks the user for the percentage they want to invest in the risk free asset and a level of           standard deviation that they would like to invest with.

### static double[][] pseudoInverse(double[][] matrix)
 -> Calculates the inverse matrix using the ejml library Calculated using an import library as covariance matrixes are          singular and difficult to invert iteratively Needed later to perform calculations for optimal portfolios.

### static double[][] varianceCovarianceMatrix(double[][] returns, double[] means)
 -> Calculates the covariance matrix for the securities. this is a requirement for calculating optimal portfolios later on.
