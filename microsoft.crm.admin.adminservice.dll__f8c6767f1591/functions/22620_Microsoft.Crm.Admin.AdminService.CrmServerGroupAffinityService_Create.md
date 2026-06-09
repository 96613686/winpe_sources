# Microsoft.Crm.Admin.AdminService.CrmServerGroupAffinityService::Create

- ea: `0x22620`
- end: `0x227e7`
- name: `Microsoft.Crm.Admin.AdminService.CrmServerGroupAffinityService::Create`
- size: `455`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callees

- `0x18790`
- `0x1c8d0`
- `0x1cc20`
- `0x223e0`
- `0x22400`
- `0x22420`
- `0x22460`
- `0x224a0`
- `0x224e0`
- `0x22520`
- `0x22560`
- `0x225a0`
- `0x22620`

## string_xrefs

- `0x226f9`: `Create`
- `0x22782`: `Create`
- `0x227ab`: `Guid {0} received from IDatabaseService.Create did not equal requested Guid {1}`
- `0x22661`: `CreateServerGroupAffinity(name={0}, description={1}, isNegativeAffinity={2}, affinityType={3}, owningGroup={4}, scaleGroupId={5}, organizationIds={6})`
- `0x226fe`: `D:\a\1\s\src\CrmLive\Admin\ServerGroupAffinity\CrmServerGroupAffinityService.cs`
- `0x22787`: `D:\a\1\s\src\CrmLive\Admin\ServerGroupAffinity\CrmServerGroupAffinityService.cs`
- `0x22714`: `An server group affinity with name {0} already exists`

## pseudocode

```c

```

## disassembly

```asm
0x22620  ldarg.1
0x22621  ldstr    aName_0// "name"
0x22626  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x2262b  ldarg.s  5
0x2262d  ldstr    aOwninggroup// "owningGroup"
0x22632  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x22637  ldarg.s  4
0x22639  brtrue.s loc_22649
0x2263b  ldarg.s  6
0x2263d  ldstr    aScalegroupid// "scaleGroupId"
0x22642  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x22647  br.s     loc_2265A
0x22649  ldarg.s  4
0x2264b  ldc.i4.1
0x2264c  bne.un.s loc_2265A
0x2264e  ldarg.s  7
0x22650  ldstr    aOrganizationid_2// "organizationIds"
0x22655  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x2265a  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x2265f  ldc.i4.s 0x14
0x22661  ldstr    aCreateservergr// "CreateServerGroupAffinity(name={0}, des"...
0x22666  ldc.i4.7
0x22667  newarr   [mscorlib]System.Object
0x2266c  dup
0x2266d  ldc.i4.0
0x2266e  ldarg.1
0x2266f  stelem.ref
0x22670  dup
0x22671  ldc.i4.1
0x22672  ldarg.2
0x22673  stelem.ref
0x22674  dup
0x22675  ldc.i4.2
0x22676  ldarg.3
0x22677  box      [mscorlib]System.Boolean
0x2267c  stelem.ref
0x2267d  dup
0x2267e  ldc.i4.3
0x2267f  ldarg.s  4
0x22681  box      [Microsoft.Crm.Core]Microsoft.Crm.ServerGroupAffinityType
0x22686  stelem.ref
0x22687  dup
0x22688  ldc.i4.4
0x22689  ldarg.s  5
0x2268b  box      [mscorlib]System.Guid
0x22690  stelem.ref
0x22691  dup
0x22692  ldc.i4.5
0x22693  ldarg.s  6
0x22695  box      [mscorlib]System.Guid
0x2269a  stelem.ref
0x2269b  dup
0x2269c  ldc.i4.6
0x2269d  ldarg.s  7
0x2269f  stelem.ref
0x226a0  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x226a5  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x226aa  stloc.0
0x226ab  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x226b0  stloc.1
0x226b1  ldarg.s  4
0x226b3  brtrue.s loc_226BA
0x226b5  ldarg.s  6
0x226b7  stloc.1
0x226b8  br.s     loc_226CE
0x226ba  ldarg.s  4
0x226bc  ldc.i4.1
0x226bd  bne.un.s loc_226CE
0x226bf  newobj   instance void Microsoft.Crm.Admin.AdminService.CrmOrganizationGroupService::.ctor()
0x226c4  ldarg.1
0x226c5  ldarg.2
0x226c6  ldarg.s  7
0x226c8  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.CrmOrganizationGroupService::Create(string name, string description, valuetype [mscorlib]System.Guid[] organizationIds)
0x226cd  stloc.1
0x226ce  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x226d3  stloc.2
0x226d4  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x226d9  stloc.3
0x226da  ldloc.3
0x226db  ldstr    aName// "Name"
0x226e0  ldarg.1
0x226e1  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x226e6  ldloc.2
0x226e7  ldstr    aServergroupaff// "ServerGroupAffinity"
0x226ec  ldnull
0x226ed  ldc.i4.1
0x226ee  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x226f3  dup
0x226f4  ldc.i4.0
0x226f5  ldloc.3
0x226f6  stelem.ref
0x226f7  ldc.i4.s 0x3A
0x226f9  ldstr    aCreate// "Create"
0x226fe  ldstr    aDA1SSrcCrmlive_44// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Serve"...
0x22703  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x22708  call     bool [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection::IsNullOrEmpty(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection)
0x2270d  brtrue.s loc_2272E
0x2270f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x22714  ldstr    aAnServerGroupA// "An server group affinity with name {0} "...
0x22719  ldc.i4.1
0x2271a  newarr   [mscorlib]System.Object
0x2271f  dup
0x22720  ldc.i4.0
0x22721  ldarg.1
0x22722  stelem.ref
0x22723  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x22728  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x2272d  throw
0x2272e  newobj   instance void Microsoft.Crm.Admin.AdminService.ServerGroupAffinityData::.ctor()
0x22733  stloc.s  4
0x22735  ldloc.s  4
0x22737  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.SequentialGuid::CreateGuid()
0x2273c  callvirt instance void Microsoft.Crm.Admin.AdminService.ServerGroupAffinityData::set_Id(valuetype [mscorlib]System.Guid value)
0x22741  ldloc.s  4
0x22743  ldarg.1
0x22744  callvirt instance void Microsoft.Crm.Admin.AdminService.ServerGroupAffinityData::set_Name(string value)
0x22749  ldloc.s  4
0x2274b  ldarg.s  5
0x2274d  callvirt instance void Microsoft.Crm.Admin.AdminService.ServerGroupAffinityData::set_OwningGroupId(valuetype [mscorlib]System.Guid value)
0x22752  ldloc.s  4
0x22754  ldarg.2
0x22755  callvirt instance void Microsoft.Crm.Admin.AdminService.ServerGroupAffinityData::set_Description(string value)
0x2275a  ldloc.s  4
0x2275c  ldarg.s  4
0x2275e  callvirt instance void Microsoft.Crm.Admin.AdminService.ServerGroupAffinityData::set_AffinityType(valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerGroupAffinityType value)
0x22763  ldloc.s  4
0x22765  ldloc.1
0x22766  callvirt instance void Microsoft.Crm.Admin.AdminService.ServerGroupAffinityData::set_GroupId(valuetype [mscorlib]System.Guid value)
0x2276b  ldloc.s  4
0x2276d  ldarg.3
0x2276e  callvirt instance void Microsoft.Crm.Admin.AdminService.ServerGroupAffinityData::set_IsNegativeAffinity(bool value)
0x22773  ldloc.2
0x22774  ldstr    aServergroupaff// "ServerGroupAffinity"
0x22779  ldloc.s  4
0x2277b  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.Admin.AdminService.BaseData::get_InternalPropertyBag()
0x22780  ldc.i4.s 0x4D
0x22782  ldstr    aCreate// "Create"
0x22787  ldstr    aDA1SSrcCrmlive_44// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Serve"...
0x2278c  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x22791  unbox.any [mscorlib]System.Guid
0x22796  stloc.0
0x22797  ldloc.0
0x22798  ldloc.s  4
0x2279a  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.ServerGroupAffinityData::get_Id()
0x2279f  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x227a4  brfalse.s loc_227D9
0x227a6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x227ab  ldstr    aGuid0ReceivedF// "Guid {0} received from IDatabaseService"...
0x227b0  ldc.i4.2
0x227b1  newarr   [mscorlib]System.Object
0x227b6  dup
0x227b7  ldc.i4.0
0x227b8  ldloc.0
0x227b9  box      [mscorlib]System.Guid
0x227be  stelem.ref
0x227bf  dup
0x227c0  ldc.i4.1
0x227c1  ldloc.s  4
0x227c3  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.ServerGroupAffinityData::get_Id()
0x227c8  box      [mscorlib]System.Guid
0x227cd  stelem.ref
0x227ce  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x227d3  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x227d8  throw
0x227d9  leave.s  loc_227E5
0x227db  ldloc.2
0x227dc  brfalse.s loc_227E4
0x227de  ldloc.2
0x227df  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x227e4  endfinally
0x227e5  ldloc.0
0x227e6  ret
```
