CodeAlpha_StockTradingPlatform
Java Programming Internship — CodeAlpha — Task 2: Stock Trading Platform

What it does
A console-based simulation of a stock trading environment:

View simulated market data for 8 stocks (price updates via Market.tick())
Buy and sell shares, with validation for funds and share availability
Track portfolio performance: cash balance, holdings value, total net worth, overall profit/loss
Full transaction history (every buy/sell recorded with timestamp)
File I/O: portfolio (cash, holdings, transaction history) is saved to portfolio.txt on exit and reloaded automatically next run, so progress persists between sessions
Design (OOP)
Stock — a single tradable stock with a simulated price
Market — holds all stocks, simulates price movement
Transaction — immutable record of one buy/sell, with CSV (de)serialization
Portfolio — cash balance, holdings, transaction history, and buy/sell business logic
PortfolioStorage — file I/O layer that saves/loads a Portfolio to/from a text file
StockTradingApp — console menu / entry point
Tech
Plain Java (no external dependencies), Java 17+
Built with Maven
Simple text-file persistence (no external DB required)
How to run
Using Maven
mvn compile exec:java -Dexec.mainClass="com.codealpha.stocktrading.StockTradingApp"
Using javac/java directly
javac -d out src/main/java/com/codealpha/stocktrading/*.java
java -cp out com.codealpha.stocktrading.StockTradingApp
As a packaged jar
mvn package
java -jar target/StockTradingPlatform.jar
Sample menu
----------- MENU -----------
1. View market data
2. Buy shares
3. Sell shares
4. View portfolio
5. View transaction history
6. Advance market (simulate price changes)
7. Save and exit
Notes
Starting cash: $10,000 (only on first run — subsequent runs reload your saved portfolio)
Option 6 simulates a market "tick," moving every stock price by a random +/-3%, so you can see how buy/sell decisions play out over time
