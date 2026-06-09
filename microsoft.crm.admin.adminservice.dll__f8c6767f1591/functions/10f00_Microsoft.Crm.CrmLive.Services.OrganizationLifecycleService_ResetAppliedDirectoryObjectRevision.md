# Microsoft.Crm.CrmLive.Services.OrganizationLifecycleService::ResetAppliedDirectoryObjectRevision

- ea: `0x10f00`
- end: `0x10f6d`
- name: `Microsoft.Crm.CrmLive.Services.OrganizationLifecycleService::ResetAppliedDirectoryObjectRevision`
- size: `109`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x10f70`

## callees

- `0x10f00`

## string_xrefs

- `0x10f18`: `DirectoryObjectRevision`
- `0x10f55`: `D:\a\1\s\src\CrmLive\Admin\OrganizationLifecycle\OrganizationLifecycleService.cs`
- `0x10f50`: `ResetAppliedDirectoryObjectRevision`

## pseudocode

```c

```

## disassembly

```asm
0x10f00  ldarg.1
0x10f01  ldstr    aOrganizationid// "organizationId"
0x10f06  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x10f0b  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x10f10  stloc.0
0x10f11  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x10f16  stloc.1
0x10f17  ldloc.1
0x10f18  ldstr    aDirectoryobjec_1// "DirectoryObjectRevision"
0x10f1d  ldnull
0x10f1e  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x10f23  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x10f28  stloc.2
0x10f29  ldloc.2
0x10f2a  ldstr    aCrmorganizatio// "CrmOrganizationId"
0x10f2f  ldarg.1
0x10f30  box      [mscorlib]System.Guid
0x10f35  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x10f3a  ldloc.0
0x10f3b  ldstr    aOrganizationli// "OrganizationLifecycle"
0x10f40  ldloc.1
0x10f41  ldc.i4.1
0x10f42  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x10f47  dup
0x10f48  ldc.i4.0
0x10f49  ldloc.2
0x10f4a  stelem.ref
0x10f4b  ldc.i4   0x280
0x10f50  ldstr    aResetapplieddi// "ResetAppliedDirectoryObjectRevision"
0x10f55  ldstr    aDA1SSrcCrmlive_21// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Organ"...
0x10f5a  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Update(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x10f5f  pop
0x10f60  leave.s  loc_10F6C
0x10f62  ldloc.0
0x10f63  brfalse.s loc_10F6B
0x10f65  ldloc.0
0x10f66  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x10f6b  endfinally
0x10f6c  ret
```
