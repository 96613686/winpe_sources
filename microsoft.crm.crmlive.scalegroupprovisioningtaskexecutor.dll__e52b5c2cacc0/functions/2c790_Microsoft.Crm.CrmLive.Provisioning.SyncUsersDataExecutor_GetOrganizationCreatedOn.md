# Microsoft.Crm.CrmLive.Provisioning.SyncUsersDataExecutor::GetOrganizationCreatedOn

- ea: `0x2c790`
- end: `0x2c821`
- name: `Microsoft.Crm.CrmLive.Provisioning.SyncUsersDataExecutor::GetOrganizationCreatedOn`
- size: `145`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x2bd10`

## callees

- `0x2c790`

## string_xrefs

- `0x2c79e`: `CreatedOn`
- `0x2c801`: `CreatedOn`
- `0x2c7c9`: `GetOrganizationCreatedOn`
- `0x2c7ce`: `d:\dbs\sh\dccm2\1101_190851\cmd\76\src\CrmLive\Provisioning\ScaleGroupProvisioningTask\TaskExecutor\SyncUsersDataExecutor.cs`

## pseudocode

```c

```

## disassembly

```asm
0x2c790  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x2c795  stloc.0
0x2c796  ldc.i4.1
0x2c797  newarr   [mscorlib]System.String
0x2c79c  dup
0x2c79d  ldc.i4.0
0x2c79e  ldstr    aCreatedon// "CreatedOn"
0x2c7a3  stelem.ref
0x2c7a4  stloc.1
0x2c7a5  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x2c7aa  stloc.2
0x2c7ab  ldloc.2
0x2c7ac  ldstr    aCrmorganizatio// "CrmOrganizationId"
0x2c7b1  ldarg.0
0x2c7b2  box      [mscorlib]System.Guid
0x2c7b7  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x2c7bc  ldloc.0
0x2c7bd  ldstr    aOrganizationli// "OrganizationLifecycle"
0x2c7c2  ldloc.1
0x2c7c3  ldloc.2
0x2c7c4  ldc.i4   0x1F2
0x2c7c9  ldstr    aGetorganizatio_6// "GetOrganizationCreatedOn"
0x2c7ce  ldstr    aDDbsShDccm2110_43// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0x2c7d3  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::RetrieveSingleItem(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x2c7d8  stloc.3
0x2c7d9  ldloc.3
0x2c7da  brtrue.s loc_2C800
0x2c7dc  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2c7e1  ldstr    aOrganizationid_4// "OrganizationId '{0}' does not exist"
0x2c7e6  ldc.i4.1
0x2c7e7  newarr   [mscorlib]System.Object
0x2c7ec  dup
0x2c7ed  ldc.i4.0
0x2c7ee  ldarg.0
0x2c7ef  box      [mscorlib]System.Guid
0x2c7f4  stelem.ref
0x2c7f5  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2c7fa  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string)
0x2c7ff  throw
0x2c800  ldloc.3
0x2c801  ldstr    aCreatedon// "CreatedOn"
0x2c806  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x2c80b  unbox.any [mscorlib]System.DateTime
0x2c810  stloc.s  4
0x2c812  leave.s  loc_2C81E
0x2c814  ldloc.0
0x2c815  brfalse.s loc_2C81D
0x2c817  ldloc.0
0x2c818  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2c81d  endfinally
0x2c81e  ldloc.s  4
0x2c820  ret
```
