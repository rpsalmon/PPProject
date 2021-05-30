Here are some columns I don't think we need:
LoanNumber                       int64
SBAOfficeCode                  float64
ProcessingMethod                object
BorrowerName                    object
BorrowerAddress                 object
BorrowerZip                     object
ServicingLenderLocationID      float64
ServicingLenderAddress          object
ServicingLenderZip              object
ProjectCity                     object
ProjectZip                      object
OriginatingLenderLocationID    float64
OriginatingLenderCity          object

Column changes needed to be made:
What does the Project data? 

Need to think about changes that can be made:
- What to do with the Borrower City - leave it or keep it?
- LoanStatusDate - turn into datetime
- LoanStatus - The three values are 
	- Exemption 4: means we can't know because it is protected by law
	- Paid in Full: disbursed the amount in full 
	- Active Un-Disbursed - loan is approved but not disbursed 

- Creating a coloumn that is the difference between Current Approval Amount and Initial Approval
- Creating a coloumn that is the difference between Undisbursed amount and Current Approval Amount
- Franchise Name - clean the column, drop the nan and make the strings cohesive (upper case it)
- RuralUrbanIndicator - change R/U into Rural and Urban
- HubzoneIndicator - these are business that have employee from those in historically under-utilized Business Zone
	- turn Y/N into Yes and No and drop Nan
- LMIIndicator - means Low and Medium income business 
	- turn Y/N into Yes and No and drop Nan 
- BusinessAgeDescription
	- Catergorize Values: Existing or more than 2 years old, New Business or 2 years or less, Unanswered, Startup, Loan Funds will Open Business, and Change of Ownership
- NAICSCode - turn numbers into industry name
- Race - how do you catergorize "Unanswered" for race
- Ethnicity - how do you categorize 'Unknown/NotStated'
- BusinessType - clean up the categorizations so nonprofit are consistent across
- Create a column that shows the difference between servicing lender to originating lender 
- Gender - how to catergorize 'Unanswered'
- Veteran - how to catergorize 'Unanswered'
- NonProfit - turn the Y to Yes and drop the rest?

Columns that we just need to drop NaN 
- Term
- SBAGuarantyPercentage - all is 100% so the SBA back up all of the loan ammount 
- InitialApproval
- CurrentApprovalAmount
- UndisbursedAmount
- Servcing Lender Name
- ProjectCountyName
- ProjectState
- CD 
- JobsReported 
- UTILITIES_PROCEED
- PAYROLL_PROCEED                
- MORTGAGE_INTEREST_PROCEED      
- RENT_PROCEED                   
- REFINANCE_EIDL_PROCEED         
- HEALTH_CARE_PROCEED            
- DEBT_INTEREST_PROCEED
- OriginatingLender
- OriginatingLenderState
