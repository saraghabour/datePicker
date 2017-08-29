# datePicker
create date picker for android application

this is calling object called DatePicker
 //Calling DatePickerFragment
    public void datePicker(View view){
        DatePickerFragment datePickerFragment = new DatePickerFragment(edDate);
        datePickerFragment.show(getFragmentManager(),"Date Picker");

    }
    
    // Here class of DatePicker 
    
    
@SuppressLint("ValidFragment")
public class DatePickerFragment extends DialogFragment  implements DatePickerDialog.OnDateSetListener{

public EditText activity_edittext;

    @SuppressLint("ValidFragment")
    public DatePickerFragment(EditText edit_text) {
        activity_edittext = edit_text;
    }

    @Override
    public Dialog onCreateDialog(Bundle savedInstanceState) {
        final Calendar calendar = Calendar.getInstance();
        int year = calendar.get(Calendar.YEAR);
        int month = calendar.get(Calendar.MONTH);
        int day = calendar.get(Calendar.DAY_OF_MONTH);
        return new DatePickerDialog(getActivity(),this,year,month,day);
    }

    @Override
    public void onDateSet(DatePicker datePicker, int year , int month, int day) {
       activity_edittext.setText(String.valueOf(year) +"/"+String.valueOf(month)+"/"+String.valueOf(day));

    }
}

