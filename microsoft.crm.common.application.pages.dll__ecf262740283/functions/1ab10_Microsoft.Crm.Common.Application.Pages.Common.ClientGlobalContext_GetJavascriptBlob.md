# Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::GetJavascriptBlob

- ea: `0x1ab10`
- end: `0x1ac1c`
- name: `Microsoft.Crm.Common.Application.Pages.Common.ClientGlobalContext::GetJavascriptBlob`
- size: `268`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x19eb0`

## callees

- `0x1ab10`

## string_xrefs

- `0x1ab4f`: `var xhr = new XMLHttpRequest();`
- `0x1ab71`: `xhr.open("GET", "/`
- `0x1abab`: `xhr.open("GET", "/WebResources/ClientGlobalContext.js.aspx`
- `0x1abe6`: `xhr.onreadystatechange  = function() { if (xhr.readyState==4 && xhr.status==200) {eval(xhr.responseText);} }`
- `0x1abfe`: `xhr.setRequestHeader("Content-Type", "application/json");xhr.send();`

## pseudocode

```c

```

## disassembly

```asm
0x1ab10  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x1ab15  stloc.0
0x1ab16  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x1ab1b  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x1ab20  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x1ab25  ldstr    aAppid// "appid"
0x1ab2a  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x1ab2f  stloc.1
0x1ab30  ldsfld   string [mscorlib]System.String::Empty
0x1ab35  stloc.2
0x1ab36  ldloc.1
0x1ab37  brfalse.s loc_1AB4E
0x1ab39  ldloc.1
0x1ab3a  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1ab3f  ldc.i4.0
0x1ab40  ble.s    loc_1AB4E
0x1ab42  ldstr    aAppid_0// "?appid="
0x1ab47  ldloc.1
0x1ab48  call     string [mscorlib]System.String::Concat(string, string)
0x1ab4d  stloc.2
0x1ab4e  ldloc.0
0x1ab4f  ldstr    aVarXhrNewXmlht// "var xhr = new XMLHttpRequest();"
0x1ab54  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x1ab59  pop
0x1ab5a  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsOnPremise()
0x1ab5f  brfalse.s loc_1ABAA
0x1ab61  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsSpla()
0x1ab66  brtrue.s loc_1ABAA
0x1ab68  ldloc.0
0x1ab69  ldc.i4.5
0x1ab6a  newarr   [mscorlib]System.String
0x1ab6f  dup
0x1ab70  ldc.i4.0
0x1ab71  ldstr    aXhrOpenGet// "xhr.open(\"GET\", \"/"
0x1ab76  stelem.ref
0x1ab77  dup
0x1ab78  ldc.i4.1
0x1ab79  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1ab7e  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::RetrieveOrganizationName(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1ab83  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmJavaScriptEncodeNoQuotes(string)
0x1ab88  stelem.ref
0x1ab89  dup
0x1ab8a  ldc.i4.2
0x1ab8b  ldstr    aWebresourcesCl// "/WebResources/ClientGlobalContext.js.as"...
0x1ab90  stelem.ref
0x1ab91  dup
0x1ab92  ldc.i4.3
0x1ab93  ldloc.2
0x1ab94  stelem.ref
0x1ab95  dup
0x1ab96  ldc.i4.4
0x1ab97  ldstr    aFalse_0// "\", false);"
0x1ab9c  stelem.ref
0x1ab9d  call     string [mscorlib]System.String::Concat(string[])
0x1aba2  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x1aba7  pop
0x1aba8  br.s     loc_1ABC1
0x1abaa  ldloc.0
0x1abab  ldstr    aXhrOpenGetWebr// "xhr.open(\"GET\", \"/WebResources/Clien"...
0x1abb0  ldloc.2
0x1abb1  ldstr    aFalse_0// "\", false);"
0x1abb6  call     string [mscorlib]System.String::Concat(string, string, string)
0x1abbb  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x1abc0  pop
0x1abc1  ldloc.0
0x1abc2  ldstr    aIfXhrAddeventl// "if(xhr.addEventListener) {"
0x1abc7  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x1abcc  pop
0x1abcd  ldloc.0
0x1abce  ldstr    aXhrAddeventlis// "   xhr.addEventListener('load',function"...
0x1abd3  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x1abd8  pop
0x1abd9  ldloc.0
0x1abda  ldstr    aElse// " } else { "
0x1abdf  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x1abe4  pop
0x1abe5  ldloc.0
0x1abe6  ldstr    aXhrOnreadystat// "xhr.onreadystatechange  = function() { "...
0x1abeb  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x1abf0  pop
0x1abf1  ldloc.0
0x1abf2  ldstr    asc_25B1E// " }"
0x1abf7  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x1abfc  pop
0x1abfd  ldloc.0
0x1abfe  ldstr    aXhrSetrequesth// "xhr.setRequestHeader(\"Content-Type\", "...
0x1ac03  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x1ac08  pop
0x1ac09  ldloc.0
0x1ac0a  ldstr    asc_23888// "}"
0x1ac0f  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x1ac14  pop
0x1ac15  ldloc.0
0x1ac16  callvirt instance string [mscorlib]System.Object::ToString()
0x1ac1b  ret
```
