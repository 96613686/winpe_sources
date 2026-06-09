# Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathAshxWebService

- ea: `0x4c20`
- end: `0x4c51`
- name: `Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPathAshxWebService`
- size: `49`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x79c0`

## callees

- `0x3ef0`

## string_xrefs

- `0x4c25`: `/AppWebServices/{0}.ashx`

## pseudocode

```c

```

## disassembly

```asm
0x4c20  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4c25  ldstr    aAppwebservices// "/AppWebServices/{0}.ashx"
0x4c2a  ldc.i4.1
0x4c2b  newarr   [mscorlib]System.Object
0x4c30  dup
0x4c31  ldc.i4.0
0x4c32  ldarg.1
0x4c33  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmUrlEncode(string)
0x4c38  stelem.ref
0x4c39  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x4c3e  stloc.0
0x4c3f  ldarg.0
0x4c40  ldloc.0
0x4c41  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x4c46  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x4c4b  call     instance void Microsoft.Crm.Controls.PageResourceManager::AddWrpcTokenActionPath(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri actionPagePath)
0x4c50  ret
```
