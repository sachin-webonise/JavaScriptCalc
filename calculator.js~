       function add(number1, number2)
        {
         var addition = parseInt(number1) +parseInt(number2);           
         return parseInt(addition);    
        }
       function sub(number1, number2)
        {
         var substraction = parseInt(number1) -parseInt(number2);           
         return parseInt(substraction);    
        }
       function mul(number1, number2)
        {
         var multiplication = parseInt(number1) *parseInt(number2);           
         return parseInt(multiplication);    
        }
       function div(number1, number2)
        {
         var division = parseInt(number1)/parseInt(number2);           
         return parseInt(division);    
        }         
        function addValuesToTextBox(input)
         {
          val= document.getElementById('textBox').value + input;
          document.getElementById('textBox').value=val;                     
         }
        var nextOprtrIndex;
        var prevOprtrIndex;
        function getOperandTwo(array,index1)
         { 
          // alert("Entered in GO2");
           var op2;
           var nextOprtr;
           nextOprtrIndex=array.length+1;//global      
           var opratorDetected=0;  
                 for(var index2=index1+1;index2<array.length;index2++)
                   {
                    //alert("right part"+array[index2]);
                     switch(array[index2])
                       {
                        case '/':
                        case '*':
                        case '+':
                        case '-'://alert("operator Detected");
                                 nextOprtr=array[index2];
                                 nextOprtrIndex=index2;           
                                 opratorDetected=1;
                                  break;
                        default: ;
                                
                       }
                     if(opratorDetected==1)
                       {
                         break;
                       }
                   }// end for
                  
                 op2 = array.substring(index1+1,nextOprtrIndex);
                 op2 = parseInt(op2);
                 //alert("op2 is:"+op2);
           return op2;  
        }

        function getOperandOne(array,index1)
         { 
           //alert("Entered in GO1");
           var op1;
           var prevOprtr;
           prevOprtrIndex=-1;//global
           var opratorDetected=0;  
                 for(var index2=index1-1;index2>=0;index2--)
                   {
                    //alert("hey"+array[index2]);
                     switch(array[index2])
                       {
                        case '/':
                        case '*':
                        case '+':
                        case '-'://alert("operator Detected");
                                 prevOprtr=array[index2];
                                 prevOprtrIndex=index2;           
                                 opratorDetected=1;
                                  break;
                        default: ;
                                
                       }
                     if(opratorDetected==1)
                       {
                         break;
                       }
                   }// end for
                  
                 op1 = array.substring(prevOprtrIndex+1,index1);
                 op1 = parseInt(op1);
                 //alert("op1 is:"+op1);
           return op1;  
        }
        function replaceEvaluatedPart(array,middleAns)
         {
           var firstPartOfExp = array.substring(0,prevOprtrIndex+1);
           var middlePartOfExp = middleAns;
           var lastPartOfExp = array.substring(nextOprtrIndex,array.length+1);
           var newExp = firstPartOfExp+middlePartOfExp+lastPartOfExp;
           return newExp;
         }
        function calculate(op1,op2,operator)
         {
          var answer;
          switch(operator)
           {
             case '/' :
                       answer =div(op1,op2);
                       break;
             case '*' :
                       answer=mul(op1,op2);
                       break;
             case '+' :
                       answer=add(op1,op2);
                       break;
             case '-' :
                       answer=sub(op1,op2);
                       break;
             default:
                      //alert("There is operator in expression other than /*+- !!!!!!!");
           }
           return(answer);   
         }
        function evaluate(operator,array)
         {
          
          var op1;
          var op2;
          var ans;
          for(var index1=0;index1 < array.length;index1++)
            {
              if(array[index1]==operator)
                {
                 op1=getOperandOne(array,index1);
                 op2=getOperandTwo(array,index1);
                 //alert("op1 in evaluate is: "+op1);
                // alert("op2 in evaluate is: "+op2);

                 ans=calculate(op1,op2,array[index1]);
                // alert("Ans in evaluate is: "+ans);
                 array=replaceEvaluatedPart(array,ans);
                // alert("Array in evaluate is: "+array);
                 index1=-1;
                }// end outer if

            }// end outer for

           return array;
         }
        function displayAnswer() 
         {
          var array = document.getElementById('textBox').value;
          var operators = ["/", "*", "+", "-"];
           for(var index=0;index<4;index++)
             {
              array=evaluate(operators[index],array);
             }
          // alert("Array in DA is: "+array);
          document.getElementById('textBox').value = array; 
         }
        function clearTextBox()
         {
          document.getElementById('textBox').value = "";
         }
        
