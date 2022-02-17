import csv
import datetime

now = datetime.datetime.now()
chars = ['"','&','*','(','\\',',',')','[',']',':','/','`','=','\'','-']
with open(r'/Users/vamshikrishnajakku/PycharmProjects/FirstProject/Inputs/ORA_ASE_FUNCTIONAL_SECURITY_CUSTOM_ROLESvk.csv') as inputcsvfile:
    print(type(inputcsvfile))
    inputcsv_data = csv.reader(inputcsvfile)
    print(type(inputcsv_data))
    with open(rf'/Users/vamshikrishnajakku/PycharmProjects/FirstProject/outputs/testoutputfile_{now}.csv', mode='w') as outputcsv:
        outputcsv_writer = csv.writer(outputcsv)
        for row in inputcsv_data:
            row[0] = row[0].replace(" ","_")
            for char in chars:
                row[2] = row[2].replace(char, "")
            outputcsv_writer.writerow(row)


