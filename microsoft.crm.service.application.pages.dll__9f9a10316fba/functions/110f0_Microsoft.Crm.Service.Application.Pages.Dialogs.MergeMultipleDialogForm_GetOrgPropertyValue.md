# Microsoft.Crm.Service.Application.Pages.Dialogs.MergeMultipleDialogForm::GetOrgPropertyValue

- ea: `0x110f0`
- end: `0x11123`
- name: `Microsoft.Crm.Service.Application.Pages.Dialogs.MergeMultipleDialogForm::GetOrgPropertyValue`
- size: `51`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x10d30`

## callees

- `0x110f0`

## string_xrefs

- `0x11113`: `d:\dbs\sh\dccm2\1101_190851\cmd\57\src\Service\Application\WebPages\_grid\Cmds\dlg_mergemultiple.aspx.cs`

## pseudocode

```c

```

## disassembly

```asm
0x110f0  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::get_IsOffline()
0x110f5  brfalse.s loc_110F9
0x110f7  ldarg.2
0x110f8  ret
0x110f9  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.OrganizationSettingsProvider::get_Instance()
0x110fe  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0x11103  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.ISecurityPrincipal::get_OrganizationId()
0x11108  ldarg.1
0x11109  ldc.i4   0xD9
0x1110e  ldstr    aGetorgproperty// "GetOrgPropertyValue"
0x11113  ldstr    aDDbsShDccm2110// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\5"...
0x11118  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationSettingsProvider::GetOrganizationSetting(valuetype [mscorlib]System.Guid, string, int32, string, string)
0x1111d  dup
0x1111e  brtrue.s loc_11122
0x11120  pop
0x11121  ldarg.2
0x11122  ret
```
