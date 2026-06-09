# Microsoft.Crm.Admin.AdminService.CrmAsyncGroupService::Create

- ea: `0x17490`
- end: `0x17596`
- name: `Microsoft.Crm.Admin.AdminService.CrmAsyncGroupService::Create`
- size: `262`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x17360`
- `0x17380`
- `0x173a0`
- `0x173e0`
- `0x17420`
- `0x17460`
- `0x17490`
- `0x18790`

## string_xrefs

- `0x174c6`: `Create`
- `0x1752f`: `Create`
- `0x174cb`: `D:\a\1\s\src\CrmLive\Admin\AsyncGroup\CrmAsyncGroupService.cs`
- `0x17534`: `D:\a\1\s\src\CrmLive\Admin\AsyncGroup\CrmAsyncGroupService.cs`
- `0x174e1`: `An async group with the name {0} already exists`
- `0x17557`: `Guid {0} received from IDatabaseService.Create did not equal requested Guid {1}`

## pseudocode

```c

```

## disassembly

```asm
0x17490  ldarg.1
0x17491  ldstr    aName_0// "name"
0x17496  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x1749b  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x174a0  stloc.0
0x174a1  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x174a6  stloc.1
0x174a7  ldloc.1
0x174a8  ldstr    aName// "Name"
0x174ad  ldarg.1
0x174ae  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x174b3  ldloc.0
0x174b4  ldstr    aAsyncgroup// "AsyncGroup"
0x174b9  ldnull
0x174ba  ldc.i4.1
0x174bb  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x174c0  dup
0x174c1  ldc.i4.0
0x174c2  ldloc.1
0x174c3  stelem.ref
0x174c4  ldc.i4.s 0x1F
0x174c6  ldstr    aCreate// "Create"
0x174cb  ldstr    aDA1SSrcCrmlive_32// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Async"...
0x174d0  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x174d5  call     bool [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection::IsNullOrEmpty(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection)
0x174da  brtrue.s loc_174FB
0x174dc  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x174e1  ldstr    aAnAsyncGroupWi// "An async group with the name {0} alread"...
0x174e6  ldc.i4.1
0x174e7  newarr   [mscorlib]System.Object
0x174ec  dup
0x174ed  ldc.i4.0
0x174ee  ldarg.1
0x174ef  stelem.ref
0x174f0  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x174f5  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x174fa  throw
0x174fb  newobj   instance void Microsoft.Crm.Admin.AdminService.AsyncGroupData::.ctor()
0x17500  stloc.2
0x17501  ldloc.2
0x17502  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.SequentialGuid::CreateGuid()
0x17507  callvirt instance void Microsoft.Crm.Admin.AdminService.AsyncGroupData::set_Id(valuetype [mscorlib]System.Guid value)
0x1750c  ldloc.2
0x1750d  ldarg.1
0x1750e  callvirt instance void Microsoft.Crm.Admin.AdminService.AsyncGroupData::set_Name(string value)
0x17513  ldloc.2
0x17514  ldarg.2
0x17515  callvirt instance void Microsoft.Crm.Admin.AdminService.AsyncGroupData::set_Description(string value)
0x1751a  ldloc.2
0x1751b  ldc.i4.0
0x1751c  callvirt instance void Microsoft.Crm.Admin.AdminService.AsyncGroupData::set_Status(valuetype Microsoft.Crm.Admin.AdminService.AsyncGroupStatus value)
0x17521  ldloc.0
0x17522  ldstr    aAsyncgroup// "AsyncGroup"
0x17527  ldloc.2
0x17528  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.Admin.AdminService.BaseData::get_InternalPropertyBag()
0x1752d  ldc.i4.s 0x2D
0x1752f  ldstr    aCreate// "Create"
0x17534  ldstr    aDA1SSrcCrmlive_32// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Async"...
0x17539  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x1753e  unbox.any [mscorlib]System.Guid
0x17543  stloc.3
0x17544  ldloc.3
0x17545  ldloc.2
0x17546  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.AsyncGroupData::get_Id()
0x1754b  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x17550  brfalse.s loc_17584
0x17552  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x17557  ldstr    aGuid0ReceivedF// "Guid {0} received from IDatabaseService"...
0x1755c  ldc.i4.2
0x1755d  newarr   [mscorlib]System.Object
0x17562  dup
0x17563  ldc.i4.0
0x17564  ldloc.3
0x17565  box      [mscorlib]System.Guid
0x1756a  stelem.ref
0x1756b  dup
0x1756c  ldc.i4.1
0x1756d  ldloc.2
0x1756e  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.AsyncGroupData::get_Id()
0x17573  box      [mscorlib]System.Guid
0x17578  stelem.ref
0x17579  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1757e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x17583  throw
0x17584  ldloc.3
0x17585  stloc.s  4
0x17587  leave.s  loc_17593
0x17589  ldloc.0
0x1758a  brfalse.s loc_17592
0x1758c  ldloc.0
0x1758d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x17592  endfinally
0x17593  ldloc.s  4
0x17595  ret
```
