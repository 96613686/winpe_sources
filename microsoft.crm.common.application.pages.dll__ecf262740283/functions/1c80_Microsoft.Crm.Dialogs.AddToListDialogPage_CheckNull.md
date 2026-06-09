# Microsoft.Crm.Dialogs.AddToListDialogPage::CheckNull

- ea: `0x1c80`
- end: `0x1ca7`
- name: `Microsoft.Crm.Dialogs.AddToListDialogPage::CheckNull`
- size: `39`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1720`

## callees

- `0x1c80`

## string_xrefs

- `0x1c92`: `ListAddToListPage.ConfigureForm Object NULL: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x1c80  ldarg.1
0x1c81  brtrue.s loc_1CA6
0x1c83  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1c88  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x1c8d  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetTraceCategory()
0x1c92  ldstr    aListaddtolistp// "ListAddToListPage.ConfigureForm Object "...
0x1c97  ldc.i4.1
0x1c98  newarr   [mscorlib]System.Object
0x1c9d  dup
0x1c9e  ldc.i4.0
0x1c9f  ldarg.2
0x1ca0  stelem.ref
0x1ca1  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1ca6  ret
```
