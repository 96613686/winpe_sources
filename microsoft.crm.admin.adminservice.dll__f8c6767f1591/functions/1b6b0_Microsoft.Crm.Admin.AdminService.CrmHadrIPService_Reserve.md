# Microsoft.Crm.Admin.AdminService.CrmHadrIPService::Reserve

- ea: `0x1b6b0`
- end: `0x1b8ed`
- name: `Microsoft.Crm.Admin.AdminService.CrmHadrIPService::Reserve`
- size: `573`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x17810`
- `0x1b150`
- `0x1b160`
- `0x1b1a0`
- `0x1b1e0`
- `0x1b220`
- `0x1b6b0`
- `0x1ba40`
- `0x1bc30`

## string_xrefs

- `0x1b7bc`: `Owner has already reserved another HadrIP, IPAddress=({0}), Id=({1})`
- `0x1b7e8`: `Owner has already reserved IP address {0} in this datacenter`
- `0x1b88e`: `D:\a\1\s\src\CrmLive\Admin\HadrIPs\HadrIPService.cs`
- `0x1b74e`: `Owner has already reserved this HadrIP, Id=({0})`
- `0x1b770`: `HadrIP has already been reserved by another owner, IPAddress=({0}), Owner=({1}), DatacenterID=({2})`
- `0x1b8a1`: `HadrIP has already been reserved by another owner, IPAddress=({0})`

## pseudocode

```c

```

## disassembly

```asm
0x1b6b0  ldarg.1
0x1b6b1  ldstr    aIpaddress_0// "ipAddress"
0x1b6b6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x1b6bb  ldarg.2
0x1b6bc  ldstr    aOwner_0// "owner"
0x1b6c1  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x1b6c6  ldarg.3
0x1b6c7  ldstr    aDatacenterid// "datacenterId"
0x1b6cc  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x1b6d1  ldarg.2
0x1b6d2  callvirt instance string [mscorlib]System.String::ToUpperInvariant()
0x1b6d7  starg.s  2
0x1b6d9  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x1b6de  ldc.i4.s 9
0x1b6e0  ldstr    aReservingHadri// "Reserving HadrIP, Owner=({0}), Datacent"...
0x1b6e5  ldc.i4.3
0x1b6e6  newarr   [mscorlib]System.Object
0x1b6eb  dup
0x1b6ec  ldc.i4.0
0x1b6ed  ldarg.2
0x1b6ee  stelem.ref
0x1b6ef  dup
0x1b6f0  ldc.i4.1
0x1b6f1  ldarg.3
0x1b6f2  box      [mscorlib]System.Guid
0x1b6f7  stelem.ref
0x1b6f8  dup
0x1b6f9  ldc.i4.2
0x1b6fa  ldarg.1
0x1b6fb  stelem.ref
0x1b6fc  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1b701  ldarg.1
0x1b702  ldnull
0x1b703  call     class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.Admin.AdminService.CrmHadrIPService::RetrieveIPAddressData(string ipAddress, string[] columnSet)
0x1b708  stloc.0
0x1b709  ldloc.0
0x1b70a  brfalse  loc_1B79D
0x1b70f  ldloc.0
0x1b710  newobj   instance void Microsoft.Crm.Admin.AdminService.HadrIPData::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag propertyBag)
0x1b715  stloc.3
0x1b716  ldloc.3
0x1b717  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.HadrIPData::get_Id()
0x1b71c  stloc.1
0x1b71d  ldloc.3
0x1b71e  callvirt instance string Microsoft.Crm.Admin.AdminService.HadrIPData::get_Owner()
0x1b723  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1b728  brtrue.s loc_1B7A9
0x1b72a  ldloc.3
0x1b72b  callvirt instance string Microsoft.Crm.Admin.AdminService.HadrIPData::get_Owner()
0x1b730  ldarg.2
0x1b731  ldc.i4.5
0x1b732  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x1b737  brfalse.s loc_1B769
0x1b739  ldloc.3
0x1b73a  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.HadrIPData::get_DatacenterId()
0x1b73f  ldarg.3
0x1b740  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1b745  brfalse.s loc_1B769
0x1b747  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x1b74c  ldc.i4.s 9
0x1b74e  ldstr    aOwnerHasAlread_1// "Owner has already reserved this HadrIP,"...
0x1b753  ldc.i4.1
0x1b754  newarr   [mscorlib]System.Object
0x1b759  dup
0x1b75a  ldc.i4.0
0x1b75b  ldloc.1
0x1b75c  box      [mscorlib]System.Guid
0x1b761  stelem.ref
0x1b762  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1b767  ldc.i4.1
0x1b768  ret
0x1b769  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x1b76e  ldc.i4.s 9
0x1b770  ldstr    aHadripHasAlrea// "HadrIP has already been reserved by ano"...
0x1b775  ldc.i4.3
0x1b776  newarr   [mscorlib]System.Object
0x1b77b  dup
0x1b77c  ldc.i4.0
0x1b77d  ldarg.1
0x1b77e  stelem.ref
0x1b77f  dup
0x1b780  ldc.i4.1
0x1b781  ldloc.3
0x1b782  callvirt instance string Microsoft.Crm.Admin.AdminService.HadrIPData::get_Owner()
0x1b787  stelem.ref
0x1b788  dup
0x1b789  ldc.i4.2
0x1b78a  ldloc.3
0x1b78b  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.HadrIPData::get_DatacenterId()
0x1b790  box      [mscorlib]System.Guid
0x1b795  stelem.ref
0x1b796  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1b79b  ldc.i4.0
0x1b79c  ret
0x1b79d  ldstr    aHadrip// "HadrIP"
0x1b7a2  ldarg.1
0x1b7a3  call     class [Microsoft.Crm.Core]Microsoft.Crm.CrmException Microsoft.Crm.Admin.AdminService.ExceptionsHelper::BuildConfigDBObjectDoesNotExist(string objectType, object value)
0x1b7a8  throw
0x1b7a9  ldarg.0
0x1b7aa  ldarg.2
0x1b7ab  ldarg.3
0x1b7ac  call     instance class Microsoft.Crm.Admin.AdminService.HadrIPData Microsoft.Crm.Admin.AdminService.CrmHadrIPService::RetrieveReservedAddress(string owner, valuetype [mscorlib]System.Guid datacenterId)
0x1b7b1  stloc.2
0x1b7b2  ldloc.2
0x1b7b3  brfalse.s loc_1B807
0x1b7b5  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x1b7ba  ldc.i4.s 9
0x1b7bc  ldstr    aOwnerHasAlread// "Owner has already reserved another Hadr"...
0x1b7c1  ldc.i4.2
0x1b7c2  newarr   [mscorlib]System.Object
0x1b7c7  dup
0x1b7c8  ldc.i4.0
0x1b7c9  ldloc.2
0x1b7ca  callvirt instance string Microsoft.Crm.Admin.AdminService.HadrIPData::get_IPAddress()
0x1b7cf  stelem.ref
0x1b7d0  dup
0x1b7d1  ldc.i4.1
0x1b7d2  ldloc.2
0x1b7d3  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.HadrIPData::get_Id()
0x1b7d8  box      [mscorlib]System.Guid
0x1b7dd  stelem.ref
0x1b7de  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1b7e3  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1b7e8  ldstr    aOwnerHasAlread_0// "Owner has already reserved IP address {"...
0x1b7ed  ldc.i4.1
0x1b7ee  newarr   [mscorlib]System.Object
0x1b7f3  dup
0x1b7f4  ldc.i4.0
0x1b7f5  ldloc.2
0x1b7f6  callvirt instance string Microsoft.Crm.Admin.AdminService.HadrIPData::get_IPAddress()
0x1b7fb  stelem.ref
0x1b7fc  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1b801  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x1b806  throw
0x1b807  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x1b80c  stloc.s  4
0x1b80e  ldloc.s  4
0x1b810  ldstr    aOwner// "Owner"
0x1b815  ldarg.2
0x1b816  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x1b81b  ldloc.s  4
0x1b81d  ldstr    aDatacenterid_1// "DatacenterId"
0x1b822  ldarg.3
0x1b823  box      [mscorlib]System.Guid
0x1b828  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x1b82d  ldloc.s  4
0x1b82f  ldstr    aLastmodificati// "LastModificationTime"
0x1b834  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x1b839  box      [mscorlib]System.DateTime
0x1b83e  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x1b843  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x1b848  stloc.s  5
0x1b84a  ldloc.s  5
0x1b84c  ldstr    aId// "Id"
0x1b851  ldloc.1
0x1b852  box      [mscorlib]System.Guid
0x1b857  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x1b85c  ldloc.s  5
0x1b85e  ldstr    aOwner// "Owner"
0x1b863  ldnull
0x1b864  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x1b869  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x1b86e  stloc.s  6
0x1b870  ldloc.s  6
0x1b872  ldstr    aHadrips// "HadrIPs"
0x1b877  ldloc.s  4
0x1b879  ldc.i4.1
0x1b87a  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x1b87f  dup
0x1b880  ldc.i4.0
0x1b881  ldloc.s  5
0x1b883  stelem.ref
0x1b884  ldc.i4   0x102
0x1b889  ldstr    aReserve// "Reserve"
0x1b88e  ldstr    aDA1SSrcCrmlive_37// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\HadrI"...
0x1b893  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Update(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x1b898  brtrue.s loc_1B8BA
0x1b89a  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x1b89f  ldc.i4.s 9
0x1b8a1  ldstr    aHadripHasAlrea_0// "HadrIP has already been reserved by ano"...
0x1b8a6  ldc.i4.1
0x1b8a7  newarr   [mscorlib]System.Object
0x1b8ac  dup
0x1b8ad  ldc.i4.0
0x1b8ae  ldarg.1
0x1b8af  stelem.ref
0x1b8b0  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1b8b5  ldc.i4.0
0x1b8b6  stloc.s  7
0x1b8b8  leave.s  loc_1B8EA
0x1b8ba  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x1b8bf  ldc.i4.s 9
0x1b8c1  ldstr    aReservedHadrip// "Reserved HadrIP, Id=({0})"
0x1b8c6  ldc.i4.1
0x1b8c7  newarr   [mscorlib]System.Object
0x1b8cc  dup
0x1b8cd  ldc.i4.0
0x1b8ce  ldloc.1
0x1b8cf  box      [mscorlib]System.Guid
0x1b8d4  stelem.ref
0x1b8d5  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1b8da  leave.s  loc_1B8E8
0x1b8dc  ldloc.s  6
0x1b8de  brfalse.s loc_1B8E7
0x1b8e0  ldloc.s  6
0x1b8e2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1b8e7  endfinally
0x1b8e8  ldc.i4.1
0x1b8e9  ret
0x1b8ea  ldloc.s  7
0x1b8ec  ret
```
