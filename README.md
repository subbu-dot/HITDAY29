# HITDAY29

package hit.day28;
import java.util.Comparator;
import java.util.HashSet;
import java.util.Iterator;
import java.util.Set;
import java.util.TreeSet;
//homework - stack and queue
public class ColDemo4 {
	public static void main(String[] args) {
		//Set<String> set=new HashSet<String>();
		Set<String> set=new TreeSet<String>(new MyComparator());
		set.add("hello");
		set.add("hai");
		set.add("hello");
		set.add("world");
		set.add("earth");
		
		System.out.println(set);
		set.add("zebra");
		set.add("almighty");
		
		System.out.println(set);
		
		Iterator iter=set.iterator();
		while(iter.hasNext()) {
			System.out.println(iter.next());
		}
		
		for(String s:set) {
			System.out.println(s);
		}
		int i=10;
		i+=10;//i=i+10;
		System.out.println(i);
	
		
	}
}
class MyComparator implements Comparator<String>{
	@Override
	public int compare(String o1, String o2) {
		// TODO Auto-generated method stub
		return o2.compareTo(o1);
	}
}
  
  package hit.day28;
import java.util.Comparator;
import java.util.HashSet;
import java.util.Set;
import java.util.TreeSet;
public class ColDemo5 {
	public static void main(String[] args) {
		ColDemo5 obj=new ColDemo5();
		Set<Question> qset=obj.getQuestionSet();
		
		System.out.println(qset);
	}
	
	public Set<Question> getQuestionSet(){
//		Set<Question> questionSet=new TreeSet<>(new MyQuestionComparator());
		Set<Question> questionSet=new TreeSet<>((q1,q2)->{return q2.qid.compareTo(q1.qid);});
//		Set<Question> questionSet=new TreeSet<>(new Comparator<Question>() {
//			@Override
//			public int compare(Question o1, Question o2) {
//				// TODO Auto-generated method stub
//				return o1.compareTo(o2);
//			}
//		});
		Question q1=new Question("1", "who is cm", "chiefmember", "chiefminister", "chiefmajor", "2");
		Question q2=new Question("2", "who is pm", "primemember", "primeminister", "primemajor", "2");
		Question q3=new Question("3", "who is dm", "districtmember", "districtmajistrate", "districtmajor", "2");
		Question q4=new Question("4", "who is hm", "headmember", "headmaster", "headmajor", "2");
		Question q5=new Question("5", "who is cm", "chiefmember", "chiefminister", "chiefmajor", "2");
		questionSet.add(q1);
		questionSet.add(q2);
		questionSet.add(q3);
		questionSet.add(q4);
		questionSet.add(q5);
		
		return questionSet;
	}
}
class MyQuestionComparator implements Comparator<Question>{
	@Override
	public int compare(Question o1, Question o2) {
		// TODO Auto-generated method stub
		return o2.compareTo(o1);
	}
}
class Question implements Comparable<Question>{
	String qid,question,option1,option2,option3,answer;
	public Question(String qid, String question, String option1, String option2, String option3, String answer) {
		this.qid = qid;
		this.question = question;
		this.option1 = option1;
		this.option2 = option2;
		this.option3 = option3;
		this.answer = answer;
	}
	@Override
	public String toString() {
		return "Question [qid=" + qid + ", question=" + question + ", option1=" + option1 + ", option2=" + option2
				+ ", option3=" + option3 + ", answer=" + answer + "]\n";
	}
	@Override
	public int compareTo(Question o) {
		return this.qid.compareTo(o.qid);
		//return o.qid.compareTo(this.qid);
	}
}
  
  
