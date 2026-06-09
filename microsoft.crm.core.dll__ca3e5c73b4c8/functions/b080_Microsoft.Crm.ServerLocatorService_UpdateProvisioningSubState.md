# Microsoft.Crm.ServerLocatorService::UpdateProvisioningSubState

- ea: `0xb080`
- end: `0xb137`
- name: `Microsoft.Crm.ServerLocatorService::UpdateProvisioningSubState`
- size: `183`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0xb140`

## callees

- `0xb080`
- `0xbfa0`
- `0x1be90`
- `0x44400`
- `0x44510`
- `0x4d750`
- `0x62500`

## string_xrefs

- `0xb11f`: `D:\a\1\s\src\Platform\Core\DataServices\Configuration\LocatorService\ServerLocatorService.cs`
- `0xb11a`: `UpdateProvisioningSubState`

## pseudocode

```c

```

## disassembly

```asm
0xb080  ldarg.1
0xb081  ldstr    aOrganizationid_0// "organizationId"
0xb086  call     void Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid parameter, string name)
0xb08b  newobj   instance void Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::.ctor()
0xb090  stloc.0
0xb091  ldloc.0
0xb092  call     void Microsoft.Crm.ServerLocatorService::AddQueryInstrumentation(class Microsoft.Crm.SharedDatabase.IDatabaseService dbService)
0xb097  newobj   instance void Microsoft.Crm.Data.PropertyBag::.ctor()
0xb09c  stloc.1
0xb09d  ldloc.1
0xb09e  ldstr    aOrganizationid_1// "OrganizationId"
0xb0a3  ldarg.1
0xb0a4  box      [mscorlib]System.Guid
0xb0a9  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0xb0ae  ldloc.1
0xb0af  ldstr    aOrgapplication// "OrgApplicationType"
0xb0b4  ldarg.3
0xb0b5  box      [mscorlib]System.Int32
0xb0ba  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0xb0bf  newobj   instance void Microsoft.Crm.Data.PropertyBag::.ctor()
0xb0c4  stloc.2
0xb0c5  ldloc.2
0xb0c6  ldstr    aMobileofflineo// "MobileOfflineOrgApplicationStatus"
0xb0cb  ldarg.2
0xb0cc  box      [mscorlib]System.Int32
0xb0d1  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0xb0d6  ldloc.2
0xb0d7  ldstr    aOrgstatusmodif// "OrgStatusModifiedOn"
0xb0dc  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0xb0e1  box      [mscorlib]System.DateTime
0xb0e6  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0xb0eb  ldarg.2
0xb0ec  brfalse.s loc_B0F2
0xb0ee  ldarg.2
0xb0ef  ldc.i4.5
0xb0f0  bne.un.s loc_B103
0xb0f2  ldloc.2
0xb0f3  ldstr    aOrgapplication_1// "OrgApplicationStatus"
0xb0f8  ldc.i4.0
0xb0f9  box      [mscorlib]System.Int32
0xb0fe  callvirt instance void Microsoft.Crm.Data.PropertyBag::set_Item(string propertyName, object value)
0xb103  ldloc.0
0xb104  ldstr    aOrgapplication_0// "OrgApplicationMap"
0xb109  ldloc.2
0xb10a  ldc.i4.1
0xb10b  newarr   Microsoft.Crm.Data.PropertyBag
0xb110  dup
0xb111  ldc.i4.0
0xb112  ldloc.1
0xb113  stelem.ref
0xb114  ldc.i4.1
0xb115  ldc.i4   0xB6B
0xb11a  ldstr    aUpdateprovisio_0// "UpdateProvisioningSubState"
0xb11f  ldstr    aDA1SSrcPlatfor_1// "D:\\a\\1\\s\\src\\Platform\\Core\\DataS"...
0xb124  callvirt instance int32 Microsoft.Crm.SharedDatabase.DatabaseService::Update(string tableName, class Microsoft.Crm.Data.PropertyBag columnSet, class Microsoft.Crm.Data.PropertyBag[] conditions, bool fireNotification, [opt] int32 sourceLineNumber, [opt] string memberName, [opt] string sourceFilePath)
0xb129  pop
0xb12a  leave.s  loc_B136
0xb12c  ldloc.0
0xb12d  brfalse.s loc_B135
0xb12f  ldloc.0
0xb130  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xb135  endfinally
0xb136  ret
```
