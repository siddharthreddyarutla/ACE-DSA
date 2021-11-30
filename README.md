# Ace-DSA
Hi there, here is  the new kickstart to ace DSA for beginners, you will be finding solutions for many problems which will level you up to crack placements and also for coding enthusiast.
 ---
#QUESTION

Merge Sort 
Given an array arr[], its starting position l and its ending position r. Sort the array using merge sort algorithm.
Example 1:

Input:
N = 5
arr[] = {4 1 3 9 7}
Output:
1 3 4 7 9
Example 2:

Input:
N = 10
arr[] = {10 9 8 7 6 5 4 3 2 1}
Output:
1 2 3 4 5 6 7 8 9 10

Your Task:
You don't need to take the input or print anything. Your task is to complete the function merge() which takes arr[], l, m, r as its input parameters and modifies arr[] in-place such that it is sorted from position l to position r, and function mergeSort() which uses merge() to sort the array in ascending order using merge sort algorithm.

Expected Time Complexity: O(nlogn) 
Expected Auxiliary Space: O(n)

Constraints:
1 <= N <= 105
1 <= arr[i] <= 103

# SOLUTION





    void merge(int arr[], int l, int m, int r)  
    
    {
        
         int n1=m-l+1;
         int n2=r-m;
         
         int a[n1];
         int b[n2];
         
         for(int i=0;i<n1;i++)
         {
             a[i]=arr[l+i];
         }
         for(int i=0;i<n2;i++)
         {
             b[i]=arr[m+1+i];
         }
         int i=0;
         int j=0;
         int k=l;
         while(i<n1 && j<n2)
         {
             if(a[i]<b[j])
             {
                 arr[k]=a[i];
                 k++;
                 i++;
             }
             else
             {
                 arr[k]=b[j];
                 k++;
                 j++;
             }
         }
         while(i<n1)
         {
             arr[k]=a[i];
             k++;
             i++;
         }
         while(j<n2)
         {
             arr[k]=b[j];
             k++;
             j++;
         }
    }
    public:
    void mergeSort(int arr[], int l, int r)
    {
        if(l<r)
        {
            int m=(l+r)/2;
            mergeSort(arr,l,m);
            mergeSort(arr,m+1,r);
            merge(arr,l,m,r);
        }
    }
