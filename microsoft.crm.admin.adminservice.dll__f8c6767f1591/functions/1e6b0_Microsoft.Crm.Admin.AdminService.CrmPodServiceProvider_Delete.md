# Microsoft.Crm.Admin.AdminService.CrmPodServiceProvider::Delete

- ea: `0x1e6b0`
- end: `0x1e76e`
- name: `Microsoft.Crm.Admin.AdminService.CrmPodServiceProvider::Delete`
- size: `190`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x1e190`
- `0x1e1b0`
- `0x1e440`
- `0x1e6b0`

## string_xrefs

- `0x1e752`: `Delete`
- `0x1e757`: `D:\a\1\s\src\CrmLive\Admin\Pod\CrmPodServiceProvider.cs`

## pseudocode

```c

```

## disassembly

```asm
0x1e6b0  ldarg.1
0x1e6b1  ldstr    aPodId// "Pod Id"
0x1e6b6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x1e6bb  ldarg.0
0x1e6bc  ldarg.1
0x1e6bd  call     instance class Microsoft.Crm.Admin.AdminService.Pod Microsoft.Crm.Admin.AdminService.CrmPodServiceProvider::Retrieve(valuetype [mscorlib]System.Guid podId)
0x1e6c2  stloc.0
0x1e6c3  ldloc.0
0x1e6c4  callvirt instance class Microsoft.Crm.Admin.AdminService.ServerData[] Microsoft.Crm.Admin.AdminService.Pod::get_Servers()
0x1e6c9  brfalse.s loc_1E6FF
0x1e6cb  ldloc.0
0x1e6cc  callvirt instance class Microsoft.Crm.Admin.AdminService.ServerData[] Microsoft.Crm.Admin.AdminService.Pod::get_Servers()
0x1e6d1  ldlen
0x1e6d2  brfalse.s loc_1E6FF
0x1e6d4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1e6d9  ldstr    aThereAre0Serve// "There are {0} servers in the Pod."
0x1e6de  ldc.i4.1
0x1e6df  newarr   [mscorlib]System.Object
0x1e6e4  dup
0x1e6e5  ldc.i4.0
0x1e6e6  ldloc.0
0x1e6e7  callvirt instance class Microsoft.Crm.Admin.AdminService.ServerData[] Microsoft.Crm.Admin.AdminService.Pod::get_Servers()
0x1e6ec  ldlen
0x1e6ed  conv.i4
0x1e6ee  box      [mscorlib]System.Int32
0x1e6f3  stelem.ref
0x1e6f4  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1e6f9  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x1e6fe  throw
0x1e6ff  ldloc.0
0x1e700  callvirt instance class Microsoft.Crm.Admin.AdminService.ScaleGroupData[] Microsoft.Crm.Admin.AdminService.Pod::get_ScaleGroups()
0x1e705  brfalse.s loc_1E73B
0x1e707  ldloc.0
0x1e708  callvirt instance class Microsoft.Crm.Admin.AdminService.ScaleGroupData[] Microsoft.Crm.Admin.AdminService.Pod::get_ScaleGroups()
0x1e70d  ldlen
0x1e70e  brfalse.s loc_1E73B
0x1e710  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1e715  ldstr    aThereAre0Scale// "There are {0} scale groups in the Pod."
0x1e71a  ldc.i4.1
0x1e71b  newarr   [mscorlib]System.Object
0x1e720  dup
0x1e721  ldc.i4.0
0x1e722  ldloc.0
0x1e723  callvirt instance class Microsoft.Crm.Admin.AdminService.ScaleGroupData[] Microsoft.Crm.Admin.AdminService.Pod::get_ScaleGroups()
0x1e728  ldlen
0x1e729  conv.i4
0x1e72a  box      [mscorlib]System.Int32
0x1e72f  stelem.ref
0x1e730  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1e735  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x1e73a  throw
0x1e73b  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x1e740  stloc.1
0x1e741  ldloc.1
0x1e742  ldstr    aPod// "Pod"
0x1e747  ldarg.1
0x1e748  box      [mscorlib]System.Guid
0x1e74d  ldc.i4   0x91
0x1e752  ldstr    aDelete// "Delete"
0x1e757  ldstr    aDA1SSrcCrmlive_41// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Pod\\"...
0x1e75c  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Delete(string, object, int32, string, string)
0x1e761  leave.s  loc_1E76D
0x1e763  ldloc.1
0x1e764  brfalse.s loc_1E76C
0x1e766  ldloc.1
0x1e767  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1e76c  endfinally
0x1e76d  ret
```
