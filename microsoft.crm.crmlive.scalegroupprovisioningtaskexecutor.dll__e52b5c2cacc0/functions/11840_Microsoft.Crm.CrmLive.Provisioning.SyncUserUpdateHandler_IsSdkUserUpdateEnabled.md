# Microsoft.Crm.CrmLive.Provisioning.SyncUserUpdateHandler::IsSdkUserUpdateEnabled

- ea: `0x11840`
- end: `0x11893`
- name: `Microsoft.Crm.CrmLive.Provisioning.SyncUserUpdateHandler::IsSdkUserUpdateEnabled`
- size: `83`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x11680`

## callees

- `0x11840`

## string_xrefs

- `0x11877`: `IsSdkUserUpdateEnabled`
- `0x1187c`: `d:\dbs\sh\dccm2\1101_190851\cmd\76\src\CrmLive\Provisioning\ScaleGroupProvisioningTask\Action\SyncData\UserHandler\SyncUserUpdateHandler.cs`

## pseudocode

```c

```

## disassembly

```asm
0x11840  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISiteSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.SiteSettingsProvider::get_Instance()
0x11845  ldstr    aUsermanagement// "UserManagementUseSdk"
0x1184a  ldc.i4.0
0x1184b  callvirt T0x2B000031
0x11850  stloc.0
0x11851  ldloca.s 0
0x11853  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x11858  brtrue.s loc_1185C
0x1185a  ldc.i4.0
0x1185b  ret
0x1185c  ldloca.s 0
0x1185e  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x11863  brfalse.s loc_11867
0x11865  ldc.i4.1
0x11866  ret
0x11867  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.OrganizationSettingsProvider::get_Instance()
0x1186c  ldarg.0
0x1186d  ldstr    aUsermanagement// "UserManagementUseSdk"
0x11872  ldc.i4   0x171
0x11877  ldstr    aIssdkuserupdat// "IsSdkUserUpdateEnabled"
0x1187c  ldstr    aDDbsShDccm2110_23// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0x11881  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationSettingsProvider::GetOrganizationSetting(valuetype [mscorlib]System.Guid, string, int32, string, string)
0x11886  stloc.1
0x11887  ldloc.1
0x11888  brtrue.s loc_1188C
0x1188a  ldc.i4.0
0x1188b  ret
0x1188c  ldloc.1
0x1188d  unbox.any [mscorlib]System.Boolean
0x11892  ret
```
