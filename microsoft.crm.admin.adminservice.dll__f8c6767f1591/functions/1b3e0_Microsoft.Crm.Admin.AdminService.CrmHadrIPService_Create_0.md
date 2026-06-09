# Microsoft.Crm.Admin.AdminService.CrmHadrIPService::Create_0

- ea: `0x1b3e0`
- end: `0x1b550`
- name: `Microsoft.Crm.Admin.AdminService.CrmHadrIPService::Create_0`
- size: `368`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `service_task, broker_com_uri`

## callees

- `0x17830`
- `0x1b140`
- `0x1b150`
- `0x1b160`
- `0x1b180`
- `0x1b1a0`
- `0x1b1c0`
- `0x1b1e0`
- `0x1b200`
- `0x1b220`
- `0x1b250`
- `0x1b2a0`
- `0x1b3e0`
- `0x1ba40`
- `0x1bbd0`
- `0x1bc30`

## string_xrefs

- `0x1b467`: `HadrIP already exists under the same owner, IPAddress=({0})`
- `0x1b484`: `HadrIP already exists under another owner, IPAddress=({0}), Owner=({1}), DatacenterID=({2})`
- `0x1b4ce`: `Owner has already reserved another HadrIP, IPAddress=({0}), Id=({1})`
- `0x1b4fa`: `Owner has already reserved IP address {0} in this datacenter`

## pseudocode

```c

```

## disassembly

```asm
0x1b3e0  ldarg.1
0x1b3e1  ldstr    aIpaddress_0// "ipAddress"
0x1b3e6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x1b3eb  ldarg.2
0x1b3ec  ldstr    aOwner_0// "owner"
0x1b3f1  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x1b3f6  ldarg.3
0x1b3f7  ldstr    aDatacenterid// "datacenterId"
0x1b3fc  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x1b401  ldarg.2
0x1b402  callvirt instance string [mscorlib]System.String::ToUpperInvariant()
0x1b407  starg.s  2
0x1b409  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x1b40e  ldc.i4.s 9
0x1b410  ldstr    aCreatingHadrip_0// "Creating HadrIP, IPAddress=({0}), Owner"...
0x1b415  ldc.i4.3
0x1b416  newarr   [mscorlib]System.Object
0x1b41b  dup
0x1b41c  ldc.i4.0
0x1b41d  ldarg.1
0x1b41e  stelem.ref
0x1b41f  dup
0x1b420  ldc.i4.1
0x1b421  ldarg.2
0x1b422  stelem.ref
0x1b423  dup
0x1b424  ldc.i4.2
0x1b425  ldarg.3
0x1b426  box      [mscorlib]System.Guid
0x1b42b  stelem.ref
0x1b42c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1b431  ldarg.1
0x1b432  ldnull
0x1b433  call     class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.Admin.AdminService.CrmHadrIPService::RetrieveIPAddressData(string ipAddress, string[] columnSet)
0x1b438  stloc.0
0x1b439  ldloc.0
0x1b43a  brfalse.s loc_1B4BB
0x1b43c  ldloc.0
0x1b43d  newobj   instance void Microsoft.Crm.Admin.AdminService.HadrIPData::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag propertyBag)
0x1b442  stloc.2
0x1b443  ldloc.2
0x1b444  callvirt instance string Microsoft.Crm.Admin.AdminService.HadrIPData::get_Owner()
0x1b449  ldarg.2
0x1b44a  ldc.i4.5
0x1b44b  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x1b450  brfalse.s loc_1B47D
0x1b452  ldloc.2
0x1b453  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.HadrIPData::get_DatacenterId()
0x1b458  ldarg.3
0x1b459  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1b45e  brfalse.s loc_1B47D
0x1b460  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x1b465  ldc.i4.s 9
0x1b467  ldstr    aHadripAlreadyE_1// "HadrIP already exists under the same ow"...
0x1b46c  ldc.i4.1
0x1b46d  newarr   [mscorlib]System.Object
0x1b472  dup
0x1b473  ldc.i4.0
0x1b474  ldarg.1
0x1b475  stelem.ref
0x1b476  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1b47b  ldloc.2
0x1b47c  ret
0x1b47d  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x1b482  ldc.i4.s 9
0x1b484  ldstr    aHadripAlreadyE_2// "HadrIP already exists under another own"...
0x1b489  ldc.i4.3
0x1b48a  newarr   [mscorlib]System.Object
0x1b48f  dup
0x1b490  ldc.i4.0
0x1b491  ldarg.1
0x1b492  stelem.ref
0x1b493  dup
0x1b494  ldc.i4.1
0x1b495  ldloc.2
0x1b496  callvirt instance string Microsoft.Crm.Admin.AdminService.HadrIPData::get_Owner()
0x1b49b  stelem.ref
0x1b49c  dup
0x1b49d  ldc.i4.2
0x1b49e  ldloc.2
0x1b49f  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.HadrIPData::get_DatacenterId()
0x1b4a4  box      [mscorlib]System.Guid
0x1b4a9  stelem.ref
0x1b4aa  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1b4af  ldstr    aHadrip// "HadrIP"
0x1b4b4  ldarg.1
0x1b4b5  call     class [Microsoft.Crm.Core]Microsoft.Crm.CrmException Microsoft.Crm.Admin.AdminService.ExceptionsHelper::BuildConfigDBDuplicateRecord(string objectType, object value)
0x1b4ba  throw
0x1b4bb  ldarg.0
0x1b4bc  ldarg.2
0x1b4bd  ldarg.3
0x1b4be  call     instance class Microsoft.Crm.Admin.AdminService.HadrIPData Microsoft.Crm.Admin.AdminService.CrmHadrIPService::RetrieveReservedAddress(string owner, valuetype [mscorlib]System.Guid datacenterId)
0x1b4c3  stloc.1
0x1b4c4  ldloc.1
0x1b4c5  brfalse.s loc_1B519
0x1b4c7  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x1b4cc  ldc.i4.s 9
0x1b4ce  ldstr    aOwnerHasAlread// "Owner has already reserved another Hadr"...
0x1b4d3  ldc.i4.2
0x1b4d4  newarr   [mscorlib]System.Object
0x1b4d9  dup
0x1b4da  ldc.i4.0
0x1b4db  ldloc.1
0x1b4dc  callvirt instance string Microsoft.Crm.Admin.AdminService.HadrIPData::get_IPAddress()
0x1b4e1  stelem.ref
0x1b4e2  dup
0x1b4e3  ldc.i4.1
0x1b4e4  ldloc.1
0x1b4e5  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.HadrIPData::get_Id()
0x1b4ea  box      [mscorlib]System.Guid
0x1b4ef  stelem.ref
0x1b4f0  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1b4f5  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1b4fa  ldstr    aOwnerHasAlread_0// "Owner has already reserved IP address {"...
0x1b4ff  ldc.i4.1
0x1b500  newarr   [mscorlib]System.Object
0x1b505  dup
0x1b506  ldc.i4.0
0x1b507  ldloc.1
0x1b508  callvirt instance string Microsoft.Crm.Admin.AdminService.HadrIPData::get_IPAddress()
0x1b50d  stelem.ref
0x1b50e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1b513  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x1b518  throw
0x1b519  newobj   instance void Microsoft.Crm.Admin.AdminService.HadrIPData::.ctor()
0x1b51e  dup
0x1b51f  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x1b524  callvirt instance void Microsoft.Crm.Admin.AdminService.HadrIPData::set_Id(valuetype [mscorlib]System.Guid value)
0x1b529  dup
0x1b52a  ldarg.1
0x1b52b  callvirt instance void Microsoft.Crm.Admin.AdminService.HadrIPData::set_IPAddress(string value)
0x1b530  dup
0x1b531  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x1b536  callvirt instance void Microsoft.Crm.Admin.AdminService.HadrIPData::set_LastModificationTime(valuetype [mscorlib]System.DateTime value)
0x1b53b  dup
0x1b53c  ldarg.2
0x1b53d  callvirt instance void Microsoft.Crm.Admin.AdminService.HadrIPData::set_Owner(string value)
0x1b542  dup
0x1b543  ldarg.3
0x1b544  callvirt instance void Microsoft.Crm.Admin.AdminService.HadrIPData::set_DatacenterId(valuetype [mscorlib]System.Guid value)
0x1b549  dup
0x1b54a  call     void Microsoft.Crm.Admin.AdminService.CrmHadrIPService::Create(class Microsoft.Crm.Admin.AdminService.HadrIPData hadrIPData)
0x1b54f  ret
```
