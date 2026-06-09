# Microsoft.Crm.Application.Forms.FormHeader::GetScriptForNotificationClick

- ea: `0x36d50`
- end: `0x36e46`
- name: `Microsoft.Crm.Application.Forms.FormHeader::GetScriptForNotificationClick`
- size: `246`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x362f0`

## string_xrefs

- `0x36d5f`: `var readnotificationIds = getReadNotificationCookie("ReadNotifications") != null ? unescape(getReadNotificationCookie("ReadNotifications")).split("|") : null;\n`
- `0x36d69`: `if(readnotificationIds!=null && readnotificationIds!=""){\n`
- `0x36d73`: `for (var j = 0; j < readnotificationIds.length; j++){\n`
- `0x36d7d`: `var readnotification = readnotificationIds[j].split(":");\n`
- `0x36d87`: `if(document.getElementById(readnotification[0])!=null)document.getElementById(readnotification[0]).style.color = "gray";}}\n`
- `0x36db9`: `function getReadNotificationCookie(cname) {\n`

## pseudocode

```c

```

## disassembly

```asm
0x36d50  ldsfld   string [mscorlib]System.String::Empty
0x36d55  ldstr    aFunctionDispla_0// "function DisplayNotifications() { \n"
0x36d5a  call     string [mscorlib]System.String::Concat(string, string)
0x36d5f  ldstr    aVarReadnotific// "var readnotificationIds = getReadNotifi"...
0x36d64  call     string [mscorlib]System.String::Concat(string, string)
0x36d69  ldstr    aIfReadnotifica// "if(readnotificationIds!=null && readnot"...
0x36d6e  call     string [mscorlib]System.String::Concat(string, string)
0x36d73  ldstr    aForVarJ0JReadn// "for (var j = 0; j < readnotificationIds"...
0x36d78  call     string [mscorlib]System.String::Concat(string, string)
0x36d7d  ldstr    aVarReadnotific_0// "var readnotification = readnotification"...
0x36d82  call     string [mscorlib]System.String::Concat(string, string)
0x36d87  ldstr    aIfDocumentGete// "if(document.getElementById(readnotifica"...
0x36d8c  call     string [mscorlib]System.String::Concat(string, string)
0x36d91  ldstr    aVarDivnotifica// "var divNotifications = document.getElem"...
0x36d96  call     string [mscorlib]System.String::Concat(string, string)
0x36d9b  ldstr    aIfDivnotificat// "if (divNotifications.style.visibility !"...
0x36da0  call     string [mscorlib]System.String::Concat(string, string)
0x36da5  ldstr    aDivnotificatio// "{divNotifications.style.visibility = \""...
0x36daa  call     string [mscorlib]System.String::Concat(string, string)
0x36daf  ldstr    aReturnFalse// "return false;} \n"
0x36db4  call     string [mscorlib]System.String::Concat(string, string)
0x36db9  ldstr    aFunctionGetrea// "function getReadNotificationCookie(cnam"...
0x36dbe  call     string [mscorlib]System.String::Concat(string, string)
0x36dc3  ldstr    aVarNameCname// "var name = cname + \"=\";\n"
0x36dc8  call     string [mscorlib]System.String::Concat(string, string)
0x36dcd  ldstr    aVarCaDocumentC// " var ca = document.cookie.split(';');\n"
0x36dd2  call     string [mscorlib]System.String::Concat(string, string)
0x36dd7  ldstr    aForVarI0ICaLen// "for(var i = 0; i < ca.length; i++) {\n"
0x36ddc  call     string [mscorlib]System.String::Concat(string, string)
0x36de1  ldstr    aVarCCaI// "var c = ca[i];\n"
0x36de6  call     string [mscorlib]System.String::Concat(string, string)
0x36deb  ldstr    aWhileCCharat0// "while (c.charAt(0) == ' ') {\n"
0x36df0  call     string [mscorlib]System.String::Concat(string, string)
0x36df5  ldstr    aCCSubstring1// "c = c.substring(1);\n"
0x36dfa  call     string [mscorlib]System.String::Concat(string, string)
0x36dff  ldstr    asc_1286EA// "}\n"
0x36e04  call     string [mscorlib]System.String::Concat(string, string)
0x36e09  ldstr    aIfCIndexofName// "if (c.indexOf(name) == 0) {\n"
0x36e0e  call     string [mscorlib]System.String::Concat(string, string)
0x36e13  ldstr    aReturnCSubstri// " return c.substring(name.length, c.leng"...
0x36e18  call     string [mscorlib]System.String::Concat(string, string)
0x36e1d  ldstr    asc_1286EA// "}\n"
0x36e22  call     string [mscorlib]System.String::Concat(string, string)
0x36e27  ldstr    asc_1286EA// "}\n"
0x36e2c  call     string [mscorlib]System.String::Concat(string, string)
0x36e31  ldstr    aReturn// "return \"\";\n"
0x36e36  call     string [mscorlib]System.String::Concat(string, string)
0x36e3b  ldstr    asc_1286EA// "}\n"
0x36e40  call     string [mscorlib]System.String::Concat(string, string)
0x36e45  ret
```
