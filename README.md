# helleo-world
学习GitHub，创建一个新的存储库


from selenium import webdriver

from selenium.webdriver.support.wait import WebDriverWait

# 把webdriver的Firefox对象赋值给变量driver
driver = webdriver.Firefox()

# 打开百度首页
driver.get("https://www.baidu.com")

# 把浏览器窗口最大化
driver.maximize_window()

# 等待搜索框出现
WebDriverWait(driver, 15).until(lambda x: x.find_element_by_xpath(".//*[@id='kw']"))

# 输入中国
driver.find_element_by_xpath(".//*[@id='kw']").send_keys("中国")

# 点击搜索按钮
driver.find_element_by_xpath(".//*[@id='su']").click()

# 等待中国_百度百科元素加载
WebDriverWait(driver, 15).until(lambda x: x.find_element_by_xpath(".//*[@id='1']/h3/a"))

# 关闭浏览器窗口
driver.close()

# 结束
driver.quit()


