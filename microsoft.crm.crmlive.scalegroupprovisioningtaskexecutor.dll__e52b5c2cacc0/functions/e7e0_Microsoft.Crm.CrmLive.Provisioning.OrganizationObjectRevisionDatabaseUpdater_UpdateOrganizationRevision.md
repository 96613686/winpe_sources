# Microsoft.Crm.CrmLive.Provisioning.OrganizationObjectRevisionDatabaseUpdater::UpdateOrganizationRevision

- ea: `0xe7e0`
- end: `0xe870`
- name: `Microsoft.Crm.CrmLive.Provisioning.OrganizationObjectRevisionDatabaseUpdater::UpdateOrganizationRevision`
- size: `144`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0xe7e0`
- `0xe930`

## string_xrefs

- `0xe7ed`: `DirectoryObjectRevision`
- `0xe7fe`: `DirectoryObjectRevisionUpdateTime`
- `0xe853`: `UpdateOrganizationRevision`
- `0xe858`: `d:\dbs\sh\dccm2\1101_190851\cmd\76\src\CrmLive\Provisioning\ScaleGroupProvisioningTask\Action\SyncData\OrganizationObjectRevisionDatabaseUpdater.cs`

## pseudocode

```c

```

## disassembly

```asm
0xe7e0  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0xe7e5  stloc.0
0xe7e6  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0xe7eb  stloc.1
0xe7ec  ldloc.1
0xe7ed  ldstr    aDirectoryobjec_2// "DirectoryObjectRevision"
0xe7f2  ldarg.1
0xe7f3  box      [mscorlib]System.Int64
0xe7f8  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xe7fd  ldloc.1
0xe7fe  ldstr    aDirectoryobjec_3// "DirectoryObjectRevisionUpdateTime"
0xe803  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0xe808  box      [mscorlib]System.DateTime
0xe80d  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xe812  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0xe817  stloc.2
0xe818  ldloc.2
0xe819  ldstr    aCrmorganizatio// "CrmOrganizationId"
0xe81e  ldarg.0
0xe81f  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Provisioning.OrganizationObjectRevisionUpdater::get_OrganizationId()
0xe824  box      [mscorlib]System.Guid
0xe829  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xe82e  ldloc.2
0xe82f  ldstr    aContextid// "ContextId"
0xe834  ldc.i4.5
0xe835  ldnull
0xe836  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyComparison::.ctor(valuetype [Microsoft.Crm.Core]Microsoft.Crm.Data.ConditionalOperator, object)
0xe83b  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0xe840  ldloc.0
0xe841  ldstr    aOrganizationli// "OrganizationLifecycle"
0xe846  ldloc.1
0xe847  ldc.i4.1
0xe848  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0xe84d  dup
0xe84e  ldc.i4.0
0xe84f  ldloc.2
0xe850  stelem.ref
0xe851  ldc.i4.s 0x23
0xe853  ldstr    aUpdateorganiza// "UpdateOrganizationRevision"
0xe858  ldstr    aDDbsShDccm2110_17// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0xe85d  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Update(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0xe862  pop
0xe863  leave.s  loc_E86F
0xe865  ldloc.0
0xe866  brfalse.s loc_E86E
0xe868  ldloc.0
0xe869  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xe86e  endfinally
0xe86f  ret
```
