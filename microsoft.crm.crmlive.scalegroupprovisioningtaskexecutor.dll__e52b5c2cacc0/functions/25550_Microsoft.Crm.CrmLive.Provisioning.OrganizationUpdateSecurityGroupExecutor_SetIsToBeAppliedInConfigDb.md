# Microsoft.Crm.CrmLive.Provisioning.OrganizationUpdateSecurityGroupExecutor::SetIsToBeAppliedInConfigDb

- ea: `0x25550`
- end: `0x255b7`
- name: `Microsoft.Crm.CrmLive.Provisioning.OrganizationUpdateSecurityGroupExecutor::SetIsToBeAppliedInConfigDb`
- size: `103`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x250c0`

## callees

- `0x25550`

## string_xrefs

- `0x25585`: `DirectoryObjectState`
- `0x2559a`: `SetIsToBeAppliedInConfigDb`
- `0x2559f`: `d:\dbs\sh\dccm2\1101_190851\cmd\76\src\CrmLive\Provisioning\ScaleGroupProvisioningTask\TaskExecutor\OrganizationUpdateSecurityGroupExecutor.cs`

## pseudocode

```c

```

## disassembly

```asm
0x25550  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x25555  stloc.0
0x25556  ldloc.0
0x25557  ldstr    aObjectid_1// "ObjectId"
0x2555c  ldarg.0
0x2555d  box      [mscorlib]System.Guid
0x25562  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x25567  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x2556c  stloc.1
0x2556d  ldloc.1
0x2556e  ldstr    aIstobeapplied// "IsToBeApplied"
0x25573  ldc.i4.1
0x25574  box      [mscorlib]System.Boolean
0x25579  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x2557e  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x25583  stloc.2
0x25584  ldloc.2
0x25585  ldstr    aDirectoryobjec_0// "DirectoryObjectState"
0x2558a  ldloc.1
0x2558b  ldc.i4.1
0x2558c  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x25591  dup
0x25592  ldc.i4.0
0x25593  ldloc.0
0x25594  stelem.ref
0x25595  ldc.i4   0xD9
0x2559a  ldstr    aSetistobeappli// "SetIsToBeAppliedInConfigDb"
0x2559f  ldstr    aDDbsShDccm2110_37// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\7"...
0x255a4  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Update(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x255a9  pop
0x255aa  leave.s  loc_255B6
0x255ac  ldloc.2
0x255ad  brfalse.s loc_255B5
0x255af  ldloc.2
0x255b0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x255b5  endfinally
0x255b6  ret
```
