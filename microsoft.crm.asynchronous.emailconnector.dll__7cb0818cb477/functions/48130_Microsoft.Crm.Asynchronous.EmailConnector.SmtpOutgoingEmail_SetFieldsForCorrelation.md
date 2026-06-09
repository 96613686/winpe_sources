# Microsoft.Crm.Asynchronous.EmailConnector.SmtpOutgoingEmail::SetFieldsForCorrelation

- ea: `0x48130`
- end: `0x481f2`
- name: `Microsoft.Crm.Asynchronous.EmailConnector.SmtpOutgoingEmail::SetFieldsForCorrelation`
- size: `194`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x47ea0`

## callees

- `0xa830`
- `0xa850`
- `0xa870`
- `0x420e0`
- `0x47c60`
- `0x47c80`
- `0x48130`

## string_xrefs

- `0x481ad`: `Thread-Topic`
- `0x481e1`: `Thread-Index`

## pseudocode

```c

```

## disassembly

```asm
0x48130  ldarg.0
0x48131  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IOutgoingEmailActivity Microsoft.Crm.Asynchronous.EmailConnector.SmtpOutgoingEmail::get_OutgoingEmail()
0x48136  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.EmailConnector.IOutgoingActivity::get_Entity()
0x4813b  call     string Microsoft.Crm.Asynchronous.EmailConnector.CrmHelper::GetEmailMessageId(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity sendEmail)
0x48140  stloc.0
0x48141  ldloc.0
0x48142  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x48147  brtrue.s loc_4815F
0x48149  ldarg.0
0x4814a  call     instance class [System]System.Net.Mail.MailMessage Microsoft.Crm.Asynchronous.EmailConnector.SmtpOutgoingEmail::get_Message()
0x4814f  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System]System.Net.Mail.MailMessage::get_Headers()
0x48154  ldstr    aMessageId// "Message-ID"
0x48159  ldloc.0
0x4815a  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Add(string, string)
0x4815f  ldarg.0
0x48160  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IOutgoingEmailActivity Microsoft.Crm.Asynchronous.EmailConnector.SmtpOutgoingEmail::get_OutgoingEmail()
0x48165  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.EmailConnector.IOutgoingActivity::get_Entity()
0x4816a  call     string Microsoft.Crm.Asynchronous.EmailConnector.CrmHelper::GetEmailInReplyTo(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity sendEmail)
0x4816f  stloc.1
0x48170  ldloc.1
0x48171  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x48176  brtrue.s loc_4818E
0x48178  ldarg.0
0x48179  call     instance class [System]System.Net.Mail.MailMessage Microsoft.Crm.Asynchronous.EmailConnector.SmtpOutgoingEmail::get_Message()
0x4817e  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System]System.Net.Mail.MailMessage::get_Headers()
0x48183  ldstr    aInReplyTo// "In-Reply-To"
0x48188  ldloc.1
0x48189  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Add(string, string)
0x4818e  ldarg.0
0x4818f  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IOutgoingEmailActivity Microsoft.Crm.Asynchronous.EmailConnector.SmtpOutgoingEmail::get_OutgoingEmail()
0x48194  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.EmailConnector.IOutgoingActivity::get_Entity()
0x48199  call     unsigned int8[] Microsoft.Crm.Asynchronous.EmailConnector.CrmHelper::GetEmailConversationIndex(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity sendEmail)
0x4819e  stloc.2
0x4819f  ldloc.2
0x481a0  brfalse.s loc_481F1
0x481a2  ldarg.0
0x481a3  call     instance class [System]System.Net.Mail.MailMessage Microsoft.Crm.Asynchronous.EmailConnector.SmtpOutgoingEmail::get_Message()
0x481a8  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System]System.Net.Mail.MailMessage::get_Headers()
0x481ad  ldstr    aThreadTopic// "Thread-Topic"
0x481b2  ldarg.0
0x481b3  call     instance class Microsoft.Crm.Asynchronous.EmailConnector.IOutgoingEmailActivity Microsoft.Crm.Asynchronous.EmailConnector.SmtpOutgoingEmail::get_OutgoingEmail()
0x481b8  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.EmailConnector.IOutgoingActivity::get_Entity()
0x481bd  ldstr    aSubject// "subject"
0x481c2  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x481c7  castclass [mscorlib]System.String
0x481cc  call     string [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmUtility::GetNormalizedEmailSubject(string)
0x481d1  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Add(string, string)
0x481d6  ldarg.0
0x481d7  call     instance class [System]System.Net.Mail.MailMessage Microsoft.Crm.Asynchronous.EmailConnector.SmtpOutgoingEmail::get_Message()
0x481dc  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System]System.Net.Mail.MailMessage::get_Headers()
0x481e1  ldstr    aThreadIndex// "Thread-Index"
0x481e6  ldloc.2
0x481e7  call     string [mscorlib]System.Convert::ToBase64String(unsigned int8[])
0x481ec  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Add(string, string)
0x481f1  ret
```
