# Microsoft.Crm.Admin.AdminService.CrmServerService::RetrieveMultiple_0

- ea: `0x21670`
- end: `0x21892`
- name: `Microsoft.Crm.Admin.AdminService.CrmServerService::RetrieveMultiple_0`
- size: `546`
- prototype: ``
- caller_count: `13`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x13d0`
- `0x1a150`
- `0x1e770`
- `0x1ee60`
- `0x1f220`
- `0x1fe40`
- `0x208c0`
- `0x21630`
- `0x21660`
- `0x21ae0`
- `0x22aa0`
- `0x23bd0`
- `0x23fb0`

## callees

- `0x21670`
- `0x21d80`
- `0x22220`
- `0x22240`
- `0x22260`
- `0x22280`
- `0x222a0`
- `0x222c0`
- `0x222e0`

## string_xrefs

- `0x217a7`: `D:\a\1\s\src\CrmLive\Admin\Server\CrmServerService.cs`
- `0x217c6`: `D:\a\1\s\src\CrmLive\Admin\Server\CrmServerService.cs`

## pseudocode

```c

```

## disassembly

```asm
0x21670  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x21675  ldc.i4.s 0x14
0x21677  ldstr    aRetrieveMultip_3// "Retrieve multiple Servers"
0x2167c  ldc.i4.0
0x2167d  newarr   [mscorlib]System.Object
0x21682  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x21687  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0x2168c  stloc.0
0x2168d  ldnull
0x2168e  stloc.1
0x2168f  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x21694  stloc.2
0x21695  ldnull
0x21696  stloc.3
0x21697  ldarg.1
0x21698  brfalse  loc_21780
0x2169d  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::.ctor()
0x216a2  stloc.1
0x216a3  ldarg.1
0x216a4  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.ServerFilter::get_ScaleGroupId()
0x216a9  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x216ae  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x216b3  brfalse.s loc_216CB
0x216b5  ldloc.1
0x216b6  ldstr    aScalegroupid_0// "ScaleGroupId"
0x216bb  ldarg.1
0x216bc  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.ServerFilter::get_ScaleGroupId()
0x216c1  box      [mscorlib]System.Guid
0x216c6  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x216cb  ldarg.1
0x216cc  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.ServerFilter::get_StorageGroupId()
0x216d1  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x216d6  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x216db  brfalse.s loc_216F3
0x216dd  ldloc.1
0x216de  ldstr    aStoragegroupid_0// "StorageGroupId"
0x216e3  ldarg.1
0x216e4  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.ServerFilter::get_StorageGroupId()
0x216e9  box      [mscorlib]System.Guid
0x216ee  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x216f3  ldarg.1
0x216f4  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.ServerFilter::get_PodId()
0x216f9  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x216fe  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x21703  brfalse.s loc_2171B
0x21705  ldloc.1
0x21706  ldstr    aPodid// "PodId"
0x2170b  ldarg.1
0x2170c  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.ServerFilter::get_PodId()
0x21711  box      [mscorlib]System.Guid
0x21716  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x2171b  ldarg.1
0x2171c  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.ServerFilter::get_DatacenterId()
0x21721  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x21726  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x2172b  brfalse.s loc_21743
0x2172d  ldloc.1
0x2172e  ldstr    aDatacenterid_1// "DatacenterId"
0x21733  ldarg.1
0x21734  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.ServerFilter::get_DatacenterId()
0x21739  box      [mscorlib]System.Guid
0x2173e  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x21743  ldarg.1
0x21744  callvirt instance valuetype Microsoft.Crm.Admin.AdminService.ServerState Microsoft.Crm.Admin.AdminService.ServerFilter::get_State()
0x21749  ldc.i4.m1
0x2174a  beq.s    loc_21762
0x2174c  ldloc.1
0x2174d  ldstr    aState// "State"
0x21752  ldarg.1
0x21753  callvirt instance valuetype Microsoft.Crm.Admin.AdminService.ServerState Microsoft.Crm.Admin.AdminService.ServerFilter::get_State()
0x21758  box      Microsoft.Crm.Admin.AdminService.ServerState
0x2175d  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x21762  ldarg.1
0x21763  callvirt instance string Microsoft.Crm.Admin.AdminService.ServerFilter::get_Name()
0x21768  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2176d  brtrue.s loc_21780
0x2176f  ldloc.1
0x21770  ldstr    aName// "Name"
0x21775  ldarg.1
0x21776  callvirt instance string Microsoft.Crm.Admin.AdminService.ServerFilter::get_Name()
0x2177b  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::set_Item(string, object)
0x21780  ldloc.1
0x21781  brfalse.s loc_217B4
0x21783  ldloc.1
0x21784  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Count()
0x21789  ldc.i4.0
0x2178a  ble.s    loc_217B4
0x2178c  ldloc.2
0x2178d  ldstr    aServer_1// "Server"
0x21792  ldnull
0x21793  ldc.i4.1
0x21794  newarr   [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag
0x21799  dup
0x2179a  ldc.i4.0
0x2179b  ldloc.1
0x2179c  stelem.ref
0x2179d  ldc.i4   0x33F
0x217a2  ldstr    aRetrievemultip// "RetrieveMultiple"
0x217a7  ldstr    aDA1SSrcCrmlive_43// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Serve"...
0x217ac  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x217b1  stloc.3
0x217b2  br.s     loc_217D1
0x217b4  ldloc.2
0x217b5  ldstr    aServer_1// "Server"
0x217ba  ldnull
0x217bb  ldnull
0x217bc  ldc.i4   0x343
0x217c1  ldstr    aRetrievemultip// "RetrieveMultiple"
0x217c6  ldstr    aDA1SSrcCrmlive_43// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Serve"...
0x217cb  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Retrieve(string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag[], int32, string, string)
0x217d0  stloc.3
0x217d1  ldloc.3
0x217d2  call     bool [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection::IsNullOrEmpty(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBagCollection)
0x217d7  brtrue.s loc_21847
0x217d9  ldloc.3
0x217da  callvirt instance class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Values()
0x217df  callvirt instance valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [System]System.Collections.Generic.SortedDictionary`2/ValueCollection<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::GetEnumerator()
0x217e4  stloc.s  4
0x217e6  br.s     loc_2182E
0x217e8  ldloca.s 4
0x217ea  call     instance var<u1> valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::get_Current()
0x217ef  stloc.s  5
0x217f1  ldarg.1
0x217f2  brfalse.s loc_2181C
0x217f4  ldarg.1
0x217f5  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles Microsoft.Crm.Admin.AdminService.ServerFilter::get_Roles()
0x217fa  brfalse.s loc_2181C
0x217fc  ldloc.s  5
0x217fe  ldstr    aRoles// "Roles"
0x21803  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x21808  unbox.any [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles
0x2180d  ldarg.1
0x2180e  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles Microsoft.Crm.Admin.AdminService.ServerFilter::get_Roles()
0x21813  and
0x21814  ldarg.1
0x21815  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles Microsoft.Crm.Admin.AdminService.ServerFilter::get_Roles()
0x2181a  bne.un.s loc_2182E
0x2181c  ldloc.s  5
0x2181e  newobj   instance void Microsoft.Crm.Admin.AdminService.ServerData::.ctor(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag propertyBag)
0x21823  stloc.s  6
0x21825  ldloc.0
0x21826  ldloc.s  6
0x21828  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x2182d  pop
0x2182e  ldloca.s 4
0x21830  call     instance bool valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>::MoveNext()
0x21835  brtrue.s loc_217E8
0x21837  leave.s  loc_21847
0x21839  ldloca.s 4
0x2183b  constrained. valuetype [System]System.Collections.Generic.SortedDictionary`2/ValueCollection/Enumerator<object, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag>
0x21841  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x21846  endfinally
0x21847  ldloc.0
0x21848  ldtoken  Microsoft.Crm.Admin.AdminService.ServerData
0x2184d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x21852  callvirt instance class [mscorlib]System.Array [mscorlib]System.Collections.ArrayList::ToArray(class [mscorlib]System.Type)
0x21857  castclass class Microsoft.Crm.Admin.AdminService.ServerData[]
0x2185c  stloc.s  7
0x2185e  leave.s  loc_2188F
0x21860  ldloc.2
0x21861  brfalse.s loc_21869
0x21863  ldloc.2
0x21864  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x21869  endfinally
0x2186a  stloc.s  8
0x2186c  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x21871  ldc.i4.s 0x14
0x21873  ldstr    aExceptionInRet_9// "Exception in retrieve multiple Server {"...
0x21878  ldc.i4.1
0x21879  newarr   [mscorlib]System.Object
0x2187e  dup
0x2187f  ldc.i4.0
0x21880  ldloc.s  8
0x21882  callvirt instance string [mscorlib]System.Exception::get_Message()
0x21887  stelem.ref
0x21888  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x2188d  rethrow
0x2188f  ldloc.s  7
0x21891  ret
```
