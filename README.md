# perceptron
x1 = float(input())
x2 = float(input())
alpha = 0.5
w1 = 0.5
w2 = 0.3
 
if x1 == 1 and x2 == 1:
    predict_result = 1
else:
    predict_result = 0

active_function = x1 * w1 + x2 * w2
print("Active function is:", active_function)
print("Predict result is:", predict_result)

def oprava(x1,x2,w1,w2):
    if active_function != predict_result:
        print("Active function is not same as predict result.")
        w1 = w1 + x1*alpha*(predict_result - active_function)
        w2 = w2 + x2*alpha*(predict_result - active_function)
        porovnanie(active_function, predict_result, x1,x2,w1,w2)
    else:
        print("Predict result = active function")

def porovnanie(active_function, predict_result, x1,x2,w1,w2):
    active_function = x1 * w1 + x2 * w2
    print("New active function:", active_function)
    if active_function == predict_result:
        print("predict presult = active function")
    else:
        oprava(x1,x2,w1,w2)
        
oprava(x1,x2,w1,w2)
