# haoareyou
网易云课堂：丝竹悦耳
下面代码输出时间

package hello;

import java.util.Scanner;

public class Main {

	public static void main(String[] args) {
		// TODO Auto-generated method stub
		Scanner in =new Scanner(System.in);
		String s = "";
		String s2 = "END";
		String time ="";
		while(s.equals(s2)==false)
		{
		s = in.nextLine();
		if (s.equals(s2)==true)
		{
			break;
		}
		int i = 2;
		int sum = s.charAt(1);
		String s1 = "$GPRMC";
		if ( s1.equals(s.substring(0, 6))==true &&s.indexOf('A')>0)
		{
			while(i<s.indexOf('*'))
			{
			char m = s.charAt(i);
			sum = sum^m;
			i++;
			}
			String n = s.substring(s.length()-2);
			if(sum%65536 == Integer.parseInt(n,16))
			{
				String h = s.substring(7,9);
				String f = s.substring(9,11);
				String j = s.substring(11,13);
				if (Integer.parseInt(h) >= 16)
				{
					time = "0"+(Integer.parseInt(h)+8-24)+":"+f+":"+j;
				}
				else if (Integer.parseInt(h)<2)
				{
					time = "0"+(Integer.parseInt(h)+8)+":"+f+":"+j;
				}
				else
				{
					time = (Integer.parseInt(h)+8)+":"+f+":"+j;
				}
			}
		}
		}
		System.out.println(time);
	}
}


