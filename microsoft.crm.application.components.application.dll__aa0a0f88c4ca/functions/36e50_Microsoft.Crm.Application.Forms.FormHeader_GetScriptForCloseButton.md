# Microsoft.Crm.Application.Forms.FormHeader::GetScriptForCloseButton

- ea: `0x36e50`
- end: `0x36f47`
- name: `Microsoft.Crm.Application.Forms.FormHeader::GetScriptForCloseButton`
- size: `247`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## callers

- `0x362f0`

## string_xrefs

- `0x36e73`: `var NotificationLink = document.getElementById("notificationLink");\n`
- `0x36e7d`: `notificationLink.innerHTML= "`
- `0x36eba`: `UpdateReadNotificationsCookie();\n`
- `0x36ece`: `function UpdateReadNotificationsCookie() { \n`
- `0x36f3c`: `document.cookie="ReadNotifications = "+ escape(notificationIds)+";expires="+date.toGMTString()+";path=/";}\n`

## pseudocode

```c

```

## disassembly

```asm
0x36e50  ldsfld   string [mscorlib]System.String::Empty
0x36e55  ldstr    aFunctionClosen// "function CloseNotifications() {\n"
0x36e5a  call     string [mscorlib]System.String::Concat(string, string)
0x36e5f  ldstr    aVarDivnotifica// "var divNotifications = document.getElem"...
0x36e64  call     string [mscorlib]System.String::Concat(string, string)
0x36e69  ldstr    aDivnotificatio_0// "divNotifications.style.visibility = \"h"...
0x36e6e  call     string [mscorlib]System.String::Concat(string, string)
0x36e73  ldstr    aVarNotificatio// "var NotificationLink = document.getElem"...
0x36e78  call     string [mscorlib]System.String::Concat(string, string)
0x36e7d  ldstr    aNotificationli_0// "notificationLink.innerHTML= \""
0x36e82  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x36e87  ldstr    aMailboxNotific// "Mailbox.Notification.NoNotifications"
0x36e8c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x36e91  ldc.i4.0
0x36e92  newarr   [mscorlib]System.Object
0x36e97  call     string [mscorlib]System.String::Format(string, object[])
0x36e9c  ldstr    asc_130BE0// "\";\n"
0x36ea1  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x36ea6  ldstr    aVarNotificatio_0// "var notificationSubTitle=document.getEl"...
0x36eab  call     string [mscorlib]System.String::Concat(string, string)
0x36eb0  ldstr    aNotificationsu_0// "notificationSubTitle.innerHTML=\" \";\n"
0x36eb5  call     string [mscorlib]System.String::Concat(string, string)
0x36eba  ldstr    aUpdatereadnoti// "UpdateReadNotificationsCookie();\n"
0x36ebf  call     string [mscorlib]System.String::Concat(string, string)
0x36ec4  ldstr    aReturnFalse_0// "return false;}\n "
0x36ec9  call     string [mscorlib]System.String::Concat(string, string)
0x36ece  ldstr    aFunctionUpdate// "function UpdateReadNotificationsCookie("...
0x36ed3  call     string [mscorlib]System.String::Concat(string, string)
0x36ed8  ldstr    aVarNotificatio_1// "var notificationDIVs= document.querySel"...
0x36edd  call     string [mscorlib]System.String::Concat(string, string)
0x36ee2  ldstr    aVarNotificatio_2// "var notificationIds=\"\";\n"
0x36ee7  call     string [mscorlib]System.String::Concat(string, string)
0x36eec  ldstr    aForVarI0INotif// "for(var i = 0; i<notificationDIVs.lengt"...
0x36ef1  call     string [mscorlib]System.String::Concat(string, string)
0x36ef6  ldstr    aVarNotificatio_3// "var notificationText = document.getElem"...
0x36efb  call     string [mscorlib]System.String::Concat(string, string)
0x36f00  ldstr    aNotificationid// "notificationIds+=notificationDIVs[i].id"...
0x36f05  call     string [mscorlib]System.String::Concat(string, string)
0x36f0a  ldstr    aIfNotification// "if (notificationIds.charAt(notification"...
0x36f0f  call     string [mscorlib]System.String::Concat(string, string)
0x36f14  ldstr    aNotificationid_0// "notificationIds = notificationIds.subst"...
0x36f19  call     string [mscorlib]System.String::Concat(string, string)
0x36f1e  ldstr    aVarExpiredurat// "var expireDuration = 1;\n"
0x36f23  call     string [mscorlib]System.String::Concat(string, string)
0x36f28  ldstr    aVarDateNewDate// "var date = new Date();\n"
0x36f2d  call     string [mscorlib]System.String::Concat(string, string)
0x36f32  ldstr    aDateSettimeDat// "date.setTime(date.getTime()+(expireDura"...
0x36f37  call     string [mscorlib]System.String::Concat(string, string)
0x36f3c  ldstr    aDocumentCookie// "document.cookie=\"ReadNotifications = "...
0x36f41  call     string [mscorlib]System.String::Concat(string, string)
0x36f46  ret
```
