# Microsoft.Crm.Admin.AdminService.CrmPodServiceProvider::Create

- ea: `0x1e370`
- end: `0x1e3e4`
- name: `Microsoft.Crm.Admin.AdminService.CrmPodServiceProvider::Create`
- size: `116`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x1e150`
- `0x1e260`
- `0x1e370`
- `0x1e4c0`

## string_xrefs

- `0x1e3c1`: `Create`
- `0x1e38e`: `Pod with name {0} already exist.`
- `0x1e3c6`: `D:\a\1\s\src\CrmLive\Admin\Pod\CrmPodServiceProvider.cs`

## pseudocode

```c

```

## disassembly

```asm
0x1e370  ldarg.1
0x1e371  ldstr    aPod// "Pod"
0x1e376  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1e37b  ldarg.0
0x1e37c  ldarg.1
0x1e37d  callvirt instance string Microsoft.Crm.Admin.AdminService.Pod::get_Name()
0x1e382  call     instance class Microsoft.Crm.Admin.AdminService.Pod Microsoft.Crm.Admin.AdminService.CrmPodServiceProvider::Retrieve(string name)
0x1e387  brfalse.s loc_1E3AD
0x1e389  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1e38e  ldstr    aPodWithName0Al// "Pod with name {0} already exist."
0x1e393  ldc.i4.1
0x1e394  newarr   [mscorlib]System.Object
0x1e399  dup
0x1e39a  ldc.i4.0
0x1e39b  ldarg.1
0x1e39c  callvirt instance string Microsoft.Crm.Admin.AdminService.Pod::get_Name()
0x1e3a1  stelem.ref
0x1e3a2  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1e3a7  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x1e3ac  throw
0x1e3ad  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x1e3b2  stloc.0
0x1e3b3  ldloc.0
0x1e3b4  ldstr    aPod// "Pod"
0x1e3b9  ldarg.1
0x1e3ba  call     class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.Admin.AdminService.PodHelper::PodToPropertyBag(class Microsoft.Crm.Admin.AdminService.Pod pod)
0x1e3bf  ldc.i4.s 0x17
0x1e3c1  ldstr    aCreate// "Create"
0x1e3c6  ldstr    aDA1SSrcCrmlive_41// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Pod\\"...
0x1e3cb  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x1e3d0  unbox.any [mscorlib]System.Guid
0x1e3d5  stloc.1
0x1e3d6  leave.s  loc_1E3E2
0x1e3d8  ldloc.0
0x1e3d9  brfalse.s loc_1E3E1
0x1e3db  ldloc.0
0x1e3dc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1e3e1  endfinally
0x1e3e2  ldloc.1
0x1e3e3  ret
```
