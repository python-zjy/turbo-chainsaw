#!/usr/bin/python
#codng=utf-8 
import smtplib
from email.mime.text import MIMEText
msg_from = '762893259@qq.com'
passwd = 'aeruxuigqhjobdec'
msg_to= '57820048@qq.com'
subject = "2019144117张净源"
content = "本机：  10.101.28.209 172.69.22.124 校园网：39.129.40.50  10.101.83.239"
msg = MIMEText(content)
msg['Subject'] = subject
msg['From'] = msg_from
msg['To'] = msg_to
try:
    s=smtplib.SMTP_SSL("smtp.qq.com",465)
    s.login(msg_from,passwd)
    s.sendmail(msg_from,msg_to,msg.as_string())
    print("发送成功")
except(s.SMTPException,e):
    print("发送失败")
finally:
    s.quit()
