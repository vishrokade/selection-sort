# selection-sort
write a program to perform selection sort in java


package vishal;

import java.util.Arrays;

public class selectionsort{
	public static void main(String[] args) {
	int[] arr= {9,-8,0,7,6,1}; 
	//for(int i =0; i<arr.length;i++){
   //     arr[i]=arr[i]*arr[i];
//	}

	selection(arr);
	System.out.println(Arrays.toString(arr));
	int duplicate = checkduplicate(arr); 
     System.out.println(duplicate);
	}
  
	static int checkduplicate(int[] arr) {   
		for(int i=1; i<arr.length;i++){
	         if(arr[i]==arr[i-1]){
	             return 1;
	         }
	        
	     }
		return 0;
	}
  
	static void selection(int[] nums) {     //in selection sort the large number is swaped with last position
		for(int i=0; i<nums.length; i++) {
			int last = nums.length-i-1;    //every time the lat nuber is decreased
			int large = largenumber(nums,0,last);  //find the large number in the array
			swap(nums,large,last);
		}
	}
  
	static int largenumber(int[] nums, int start, int end) {  // find the large number in the array
		int large = start;
		for(int i=start; i <=end; i++) {
			if (nums[large]<nums[i])
			{
				large = i;
			}
		}
		return large;
	}
  
	static void swap(int[] nums, int first, int second) { //function for swapping the max number with last index
		int temp = nums[first];
		nums[first] = nums[second];
		nums[second]=temp;
	}
}
