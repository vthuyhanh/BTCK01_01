package pages;

import org.apache.logging.log4j.LogManager;
import org.apache.logging.log4j.Logger;
import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;


public class AddNewEmployeePage {
    private WebDriver driver;
    private static final Logger logger = LogManager.getLogger(AddNewEmployeePage.class);

    // Locators cho các elements trên trang Thêm mới nhân viên
    private By fullNameInput = By.xpath("//label[text()='Họ và tên đệm']/following-sibling::input");
    private By firstNameInput = By.xpath("//label[text()='Tên']/following-sibling::input");
    private By birthdayInput = By.xpath("//label[text()='Ngày sinh']/following-sibling::div/input");
    private By departmentDropdown = By.xpath("//label[text()='Phòng ban']/following-sibling::div/div/div[1]"); // Cần locator chính xác cho dropdown
    private By officeRadioButton = By.xpath("//label[text()='Văn phòng']/preceding-sibling::input[@type='radio']");
    private By trainingRadioButton = By.xpath("//label[text()='Đào tạo']/preceding-sibling::input[@type='radio']");
    private By startDateInput = By.xpath("//label[text()='Ngày bắt đầu làm việc']/following-sibling::div/input");
    private By contractLinkInput = By.xpath("//label[text()='Link Hợp đồng']/following-sibling::input");
    private By usernameInput = By.xpath("//label[text()='Tên đăng nhập / Tài khoản']/following-sibling::input");
    private By passwordInput = By.xpath("//label[text()='Mật khẩu']/following-sibling::input");
    private By sdtInput = By.xpath("//label[text()='SĐT']/following-sibling::input");
    private By saveButton = By.xpath("//span[text()='XÁC NHẬN']");
    private By cancelButton = By.xpath("//span[text()='HỦY BỎ']");
    private By successMessage = By.xpath("//div[@class='alert alert-success']"); // Cần locator chính xác nếu có

    public AddNewEmployeePage(WebDriver driver) {
        this.driver = driver;
        logger.info("Khởi tạo trang AddNewEmployeePage.");
    }

    public void enterFullName(String fullName) {
        WebElement fullNameElement = driver.findElement(fullNameInput);
        fullNameElement.sendKeys(fullName);
        logger.info("Nhập họ và tên đệm: " + fullName);
    }

    public void enterFirstName(String firstName) {
        WebElement firstNameElement = driver.findElement(firstNameInput);
        firstNameElement.sendKeys(firstName);
        logger.info("Nhập tên: " + firstName);
    }

    public void enterBirthday(String birthday) {
        WebElement birthdayElement = driver.findElement(birthdayInput);
        birthdayElement.sendKeys(birthday);
        logger.info("Chọn ngày sinh: " + birthday);
    }

    public void selectDepartment(String department) {
        // Cần implement logic để chọn từ dropdown. Có thể cần click vào dropdown để mở và sau đó chọn item.
        WebElement departmentDropdownElement = driver.findElement(departmentDropdown);
        departmentDropdownElement.click();
        WebElement departmentOption = driver.findElement(By.xpath("//div[@class='ant-select-dropdown']//div[contains(text(), '" + department + "')]")); // Ví dụ locator
        departmentOption.click();
        logger.info("Chọn phòng ban: " + department);
    }

    public void selectOfficeRadioButton() {
        WebElement officeRadio = driver.findElement(officeRadioButton);
        officeRadio.click();
        logger.info("Chọn phòng ban: Văn phòng.");
    }

    public void selectTrainingRadioButton() {
        WebElement trainingRadio = driver.findElement(trainingRadioButton);
        trainingRadio.click();
        logger.info("Chọn phòng ban: Đào tạo.");
    }

    public void enterStartDate(String startDate) {
        WebElement startDateElement = driver.findElement(startDateInput);
        startDateElement.sendKeys(startDate);
        logger.info("Chọn ngày bắt đầu làm việc: " + startDate);
    }

    public void enterContractLink(String contractLink) {
        WebElement contractLinkElement = driver.findElement(contractLinkInput);
        contractLinkElement.sendKeys(contractLink);
        logger.info("Nhập link hợp đồng: " + contractLink);
    }

    public void enterUsername(String username) {
        WebElement usernameElement = driver.findElement(usernameInput);
        usernameElement.sendKeys(username);
        logger.info("Nhập tên đăng nhập: " + username);
    }

    public void enterPassword(String password) {
        WebElement passwordElement = driver.findElement(passwordInput);
        passwordElement.sendKeys(password);
        logger.info("Nhập mật khẩu: " + password);
    }

    public void enterSDT(String sdt) {
        WebElement sdtElement = driver.findElement(sdtInput);
        sdtElement.sendKeys(sdt);
        logger.info("Nhập số điện thoại: " + sdt);
    }

    public void clickSaveButton() {
        WebElement saveBtn = driver.findElement(saveButton);
        saveBtn.click();
        logger.info("Click nút XÁC NHẬN.");
    }

    public void clickCancelButton() {
        WebElement cancelBtn = driver.findElement(cancelButton);
        cancelBtn.click();
        logger.info("Click nút HỦY BỎ.");
    }

    public boolean isSuccessMessageDisplayed() {
        try {
            WebElement successMsgElement = driver.findElement(successMessage);
            boolean isDisplayed = successMsgElement.isDisplayed();
            logger.info("Kiểm tra hiển thị thông báo thành công: " + isDisplayed);
            return isDisplayed;
        } catch (org.openqa.selenium.NoSuchElementException e) {
            logger.warn("Không tìm thấy thông báo thành công.");
            return false;
        }
    }

    public void addNewEmployee(String fullName, String firstName, String birthday, String department, String startDate, String contractLink, String username, String password, String sdt) {
        enterFullName(fullName);
        enterFirstName(firstName);
        enterBirthday(birthday);
        selectDepartment(department);
        enterStartDate(startDate);
        enterContractLink(contractLink);
        enterUsername(username);
        enterPassword(password);
        enterSDT(sdt);
        clickSaveButton();
    }
}
