# Microsoft.Crm.Service.Web.CS.UIScriptErrorPage::ConfigureForm

- ea: `0x6430`
- end: `0x6498`
- name: `Microsoft.Crm.Service.Web.CS.UIScriptErrorPage::ConfigureForm`
- size: `104`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x6430`
- `0x64a0`
- `0x6560`

## pseudocode

```c

```

## disassembly

```asm
0x6430  ldarg.0
0x6431  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x6436  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x643b  ldstr    aHresult// "hresult"
0x6440  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x6445  stloc.0
0x6446  ldloc.0
0x6447  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x644c  brtrue.s loc_6460
0x644e  ldarg.0
0x644f  ldloc.0
0x6450  call     class [mscorlib]System.Globalization.CultureInfo [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmCultureInfo::get_CurrentCulture()
0x6455  call     int32 [mscorlib]System.Convert::ToInt32(string, class [mscorlib]System.IFormatProvider)
0x645a  call     instance void Microsoft.Crm.Service.Web.CS.UIScriptErrorPage::ShowError(int32 errorCode)
0x645f  ret
0x6460  ldarg.0
0x6461  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x6466  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x646b  ldstr    aCustomerror// "customError"
0x6470  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x6475  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x647a  brtrue.s loc_6497
0x647c  ldarg.0
0x647d  ldarg.0
0x647e  call     instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x6483  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_QueryString()
0x6488  ldstr    aCustomerror// "customError"
0x648d  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x6492  call     instance void Microsoft.Crm.Service.Web.CS.UIScriptErrorPage::ShowCustomError(string customError)
0x6497  ret
```
