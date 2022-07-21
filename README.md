

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.interactions.Actions;

import io.github.bonigarcia.wdm.WebDriverManager;

public class dragdrop {

	public static void main(String[] args) throws InterruptedException {
		// TODO Auto-generated method stub
WebDriverManager.chromedriver().setup();
WebDriver driver = new ChromeDriver();
 driver.get("https://demoqa.com/droppable/");
driver.manage().window().maximize();
Thread.sleep(3000);

WebElement s = driver.findElement(By.xpath("//div[@id='draggable']"));

Thread.sleep(3000);

WebElement d = driver.findElement(By.xpath("//div[@id='droppable']"));

Actions act = new Actions(driver);
act.dragAndDrop(s, d).build().perform();
Thread.sleep(4000);
driver.close();

	}

}

