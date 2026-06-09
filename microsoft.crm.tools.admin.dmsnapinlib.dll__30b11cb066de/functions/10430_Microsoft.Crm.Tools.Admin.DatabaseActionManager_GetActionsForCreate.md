# Microsoft.Crm.Tools.Admin.DatabaseActionManager::GetActionsForCreate

- ea: `0x10430`
- end: `0x1049f`
- name: `Microsoft.Crm.Tools.Admin.DatabaseActionManager::GetActionsForCreate`
- size: `111`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x121f0`

## callees

- `0x72a0`
- `0x10520`
- `0x10560`
- `0x10a40`
- `0x10c00`
- `0x10e70`
- `0x11090`
- `0x11140`
- `0x11190`

## pseudocode

```c

```

## disassembly

```asm
0x10430  newobj   instance void Microsoft.Crm.Tools.Admin.OrganizationActionCollection::.ctor()
0x10435  dup
0x10436  ldarg.0
0x10437  ldc.i4.5
0x10438  newobj   instance void Microsoft.Crm.Tools.Admin.AddOrganizationToConfigurationDatabaseAction::.ctor(class Microsoft.Crm.Tools.Admin.OrganizationOperation operation, int32 nominalProgressWeighting)
0x1043d  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Tools.Admin.OrganizationAction>::Add(var<u1>)
0x10442  dup
0x10443  ldarg.0
0x10444  ldc.i4.s 0x50
0x10446  newobj   instance void Microsoft.Crm.Tools.Admin.CreateDatabaseAction::.ctor(class Microsoft.Crm.Tools.Admin.OrganizationOperation source, int32 nominalProgressWeighting)
0x1044b  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Tools.Admin.OrganizationAction>::Add(var<u1>)
0x10450  dup
0x10451  ldarg.0
0x10452  ldc.i4.0
0x10453  newobj   instance void Microsoft.Crm.Tools.Admin.SetupAuditPartitioningAction::.ctor(class Microsoft.Crm.Tools.Admin.OrganizationOperation source, int32 nominalProgressWeighting)
0x10458  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Tools.Admin.OrganizationAction>::Add(var<u1>)
0x1045d  dup
0x1045e  ldarg.0
0x1045f  ldc.i4.5
0x10460  newobj   instance void Microsoft.Crm.Tools.Admin.SetOrgVersionInConfigDBAction::.ctor(class Microsoft.Crm.Tools.Admin.OrganizationOperation operation, int32 nominalProgressWeighting)
0x10465  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Tools.Admin.OrganizationAction>::Add(var<u1>)
0x1046a  dup
0x1046b  ldarg.0
0x1046c  ldc.i4.5
0x1046d  newobj   instance void Microsoft.Crm.Tools.Admin.SetDatabaseCollationAction::.ctor(class Microsoft.Crm.Tools.Admin.OrganizationOperation operation, int32 nominalProgressWeighting)
0x10472  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Tools.Admin.OrganizationAction>::Add(var<u1>)
0x10477  dup
0x10478  ldarg.0
0x10479  ldc.i4.5
0x1047a  newobj   instance void Microsoft.Crm.Tools.Admin.GrantCrmDatabaseAccessAction::.ctor(class Microsoft.Crm.Tools.Admin.OrganizationOperation operation, int32 nominalProgressWeighting)
0x1047f  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Tools.Admin.OrganizationAction>::Add(var<u1>)
0x10484  dup
0x10485  ldarg.0
0x10486  ldc.i4.0
0x10487  newobj   instance void Microsoft.Crm.Tools.Admin.SetReportsUnpublishedAction::.ctor(class Microsoft.Crm.Tools.Admin.OrganizationOperation operationBase, int32 nominalProgressWeighting)
0x1048c  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Tools.Admin.OrganizationAction>::Add(var<u1>)
0x10491  dup
0x10492  ldarg.0
0x10493  ldc.i4.0
0x10494  newobj   instance void Microsoft.Crm.Tools.Admin.FlushMetadataCacheAction::.ctor(class Microsoft.Crm.Tools.Admin.OrganizationOperation operation, int32 nominalProgressWeighting)
0x10499  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class Microsoft.Crm.Tools.Admin.OrganizationAction>::Add(var<u1>)
0x1049e  ret
```
