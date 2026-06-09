# Microsoft.Crm.Application.WebServices.BusinessRulesWebService::RetrieveBusinessRulesXml

- ea: `0x5d0`
- end: `0x628`
- name: `Microsoft.Crm.Application.WebServices.BusinessRulesWebService::RetrieveBusinessRulesXml`
- size: `88`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x5d0`

## pseudocode

```c

```

## disassembly

```asm
0x5d0  ldarg.2
0x5d1  ldstr    aFormid// "formId"
0x5d6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfEmpty(string, string)
0x5db  ldarg.1
0x5dc  ldstr    aOtc// "otc"
0x5e1  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNegative(int32, string)
0x5e6  newobj   instance void [System]System.Collections.Specialized.NameValueCollection::.ctor()
0x5eb  stloc.0
0x5ec  ldloc.0
0x5ed  ldstr    aEtc// "etc"
0x5f2  ldarga.s 1
0x5f4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5f9  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x5fe  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Add(string, string)
0x603  ldloc.0
0x604  ldstr    aFormid// "formId"
0x609  ldarg.2
0x60a  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Add(string, string)
0x60f  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.SystemCustomization.BusinessRuleXmlDataProvider::.ctor()
0x614  ldloc.0
0x615  callvirt instance string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.SystemCustomization.BusinessRuleXmlDataProvider::RetrieveBusinessRulesXml(class [System]System.Collections.Specialized.NameValueCollection)
0x61a  stloc.1
0x61b  leave.s  loc_626
0x61d  stloc.2
0x61e  ldarg.0
0x61f  ldloc.2
0x620  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0x625  throw
0x626  ldloc.1
0x627  ret
```
