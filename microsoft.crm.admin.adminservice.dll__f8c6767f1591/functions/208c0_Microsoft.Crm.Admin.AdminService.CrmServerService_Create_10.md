# Microsoft.Crm.Admin.AdminService.CrmServerService::Create_10

- ea: `0x208c0`
- end: `0x20b0f`
- name: `Microsoft.Crm.Admin.AdminService.CrmServerService::Create_10`
- size: `591`
- prototype: ``
- caller_count: `4`
- callee_count: `19`
- tags: `service_task, broker_com_uri`

## callers

- `0x207b0`
- `0x207d0`
- `0x20810`
- `0x208a0`

## callees

- `0x18790`
- `0x208c0`
- `0x21670`
- `0x21d70`
- `0x21d90`
- `0x21db0`
- `0x21df0`
- `0x21e30`
- `0x21e70`
- `0x21ec0`
- `0x21f00`
- `0x21f50`
- `0x22070`
- `0x220b0`
- `0x22110`
- `0x22150`
- `0x222f0`
- `0x22300`
- `0x22350`

## string_xrefs

- `0x20a5f`: `Create`
- `0x20995`: `Server {0} already exist in scale group {1}, storage group {2}, or pod {3}`
- `0x20a64`: `D:\a\1\s\src\CrmLive\Admin\Server\CrmServerService.cs`
- `0x20ab6`: `Created Server, Id=({0})`

## pseudocode

```c

```

## disassembly

```asm
0x208c0  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x208c5  ldc.i4.s 0x14
0x208c7  ldstr    aCreatingServer// "Creating Server, Name=({0}), FullName=("...
0x208cc  ldc.i4.8
0x208cd  newarr   [mscorlib]System.Object
0x208d2  dup
0x208d3  ldc.i4.0
0x208d4  ldarg.1
0x208d5  stelem.ref
0x208d6  dup
0x208d7  ldc.i4.1
0x208d8  ldarg.2
0x208d9  stelem.ref
0x208da  dup
0x208db  ldc.i4.2
0x208dc  ldarg.3
0x208dd  box      [mscorlib]System.Guid
0x208e2  stelem.ref
0x208e3  dup
0x208e4  ldc.i4.3
0x208e5  ldarg.s  4
0x208e7  box      [mscorlib]System.Guid
0x208ec  stelem.ref
0x208ed  dup
0x208ee  ldc.i4.4
0x208ef  ldarg.s  5
0x208f1  box      [mscorlib]System.Guid
0x208f6  stelem.ref
0x208f7  dup
0x208f8  ldc.i4.5
0x208f9  ldarg.s  7
0x208fb  box      [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles
0x20900  stelem.ref
0x20901  dup
0x20902  ldc.i4.6
0x20903  ldarg.s  9
0x20905  stelem.ref
0x20906  dup
0x20907  ldc.i4.7
0x20908  ldarg.s  8
0x2090a  box      Microsoft.Crm.Admin.AdminService.ServerState
0x2090f  stelem.ref
0x20910  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x20915  ldarg.1
0x20916  ldstr    aServerName// "Server name"
0x2091b  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x20920  ldarg.s  9
0x20922  ldstr    aServerVersion// "Server version"
0x20927  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x2092c  ldarg.3
0x2092d  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x20932  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x20937  brfalse.s loc_20952
0x20939  ldarg.s  5
0x2093b  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x20940  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x20945  brfalse.s loc_20952
0x20947  ldstr    aServerCanNotBe// "Server can not belong to both a scale g"...
0x2094c  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x20951  throw
0x20952  ldc.i4.2
0x20953  ldc.i4.2
0x20954  call     class [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.SkuInfoProvider::get_Instance()
0x20959  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.ConfigSku [Microsoft.Crm.Core]Microsoft.Crm.ISkuInfoProvider::GetSku()
0x2095e  and
0x2095f  beq.s    loc_20979
0x20961  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x20966  ldarg.3
0x20967  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x2096c  brfalse.s loc_20979
0x2096e  ldstr    aScalegroupidMu// "ScaleGroupId must be Guid.Empty in non "...
0x20973  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x20978  throw
0x20979  newobj   instance void Microsoft.Crm.Admin.AdminService.ServerFilter::.ctor()
0x2097e  stloc.0
0x2097f  ldloc.0
0x20980  ldarg.1
0x20981  callvirt instance void Microsoft.Crm.Admin.AdminService.ServerFilter::set_Name(string value)
0x20986  ldarg.0
0x20987  ldloc.0
0x20988  call     instance class Microsoft.Crm.Admin.AdminService.ServerData[] Microsoft.Crm.Admin.AdminService.CrmServerService::RetrieveMultiple(class Microsoft.Crm.Admin.AdminService.ServerFilter filter)
0x2098d  ldlen
0x2098e  brfalse.s loc_209CC
0x20990  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x20995  ldstr    aServer0Already// "Server {0} already exist in scale group"...
0x2099a  ldc.i4.4
0x2099b  newarr   [mscorlib]System.Object
0x209a0  dup
0x209a1  ldc.i4.0
0x209a2  ldarg.1
0x209a3  stelem.ref
0x209a4  dup
0x209a5  ldc.i4.1
0x209a6  ldarg.3
0x209a7  box      [mscorlib]System.Guid
0x209ac  stelem.ref
0x209ad  dup
0x209ae  ldc.i4.2
0x209af  ldarg.s  4
0x209b1  box      [mscorlib]System.Guid
0x209b6  stelem.ref
0x209b7  dup
0x209b8  ldc.i4.3
0x209b9  ldarg.s  5
0x209bb  box      [mscorlib]System.Guid
0x209c0  stelem.ref
0x209c1  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x209c6  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x209cb  throw
0x209cc  ldsfld   string [mscorlib]System.String::Empty
0x209d1  stloc.1
0x209d2  ldarg.s  9
0x209d4  ldloca.s 1
0x209d6  call     bool Microsoft.Crm.Admin.AdminService.ServerVersionFormat::TryCanonicalizeServerVersion(string serverVersion, [out] string& canonicalizedServerVersion)
0x209db  brfalse.s loc_209E0
0x209dd  ldloc.1
0x209de  starg.s  9
0x209e0  newobj   instance void Microsoft.Crm.Admin.AdminService.ServerData::.ctor()
0x209e5  stloc.2
0x209e6  ldloc.2
0x209e7  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.SequentialGuid::CreateGuid()
0x209ec  callvirt instance void Microsoft.Crm.Admin.AdminService.ServerData::set_Id(valuetype [mscorlib]System.Guid value)
0x209f1  ldloc.2
0x209f2  ldarg.1
0x209f3  callvirt instance void Microsoft.Crm.Admin.AdminService.ServerData::set_Name(string value)
0x209f8  ldloc.2
0x209f9  ldarg.2
0x209fa  callvirt instance void Microsoft.Crm.Admin.AdminService.ServerData::set_FullName(string value)
0x209ff  ldloc.2
0x20a00  ldarg.3
0x20a01  callvirt instance void Microsoft.Crm.Admin.AdminService.ServerData::set_ScaleGroupId(valuetype [mscorlib]System.Guid value)
0x20a06  ldloc.2
0x20a07  ldarg.s  4
0x20a09  callvirt instance void Microsoft.Crm.Admin.AdminService.ServerData::set_StorageGroupId(valuetype [mscorlib]System.Guid value)
0x20a0e  ldloc.2
0x20a0f  ldarg.s  7
0x20a11  callvirt instance void Microsoft.Crm.Admin.AdminService.ServerData::set_Roles(valuetype [Microsoft.Crm.Core]Microsoft.Crm.ServerRoles value)
0x20a16  ldloc.2
0x20a17  ldarg.s  9
0x20a19  callvirt instance void Microsoft.Crm.Admin.AdminService.ServerData::set_Version(string value)
0x20a1e  ldloc.2
0x20a1f  ldarg.s  8
0x20a21  callvirt instance void Microsoft.Crm.Admin.AdminService.ServerData::set_State(valuetype Microsoft.Crm.Admin.AdminService.ServerState value)
0x20a26  ldloc.2
0x20a27  ldarg.s  5
0x20a29  callvirt instance void Microsoft.Crm.Admin.AdminService.ServerData::set_PodId(valuetype [mscorlib]System.Guid value)
0x20a2e  ldloc.2
0x20a2f  ldarg.s  6
0x20a31  callvirt instance void Microsoft.Crm.Admin.AdminService.ServerData::set_DatacenterId(valuetype [mscorlib]System.Guid value)
0x20a36  ldloc.2
0x20a37  ldarg.s  9
0x20a39  newobj   instance void [mscorlib]System.Version::.ctor(string)
0x20a3e  call     instance int32 [mscorlib]System.Version::get_Revision()
0x20a43  callvirt instance void Microsoft.Crm.Admin.AdminService.ServerData::set_ServiceabilityRevision(int32 value)
0x20a48  call     class [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationDatabaseService::NewService()
0x20a4d  stloc.3
0x20a4e  ldloc.3
0x20a4f  ldstr    aServer_1// "Server"
0x20a54  ldloc.2
0x20a55  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag Microsoft.Crm.Admin.AdminService.BaseData::get_InternalPropertyBag()
0x20a5a  ldc.i4   0x139
0x20a5f  ldstr    aCreate// "Create"
0x20a64  ldstr    aDA1SSrcCrmlive_43// "D:\\a\\1\\s\\src\\CrmLive\\Admin\\Serve"...
0x20a69  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.SharedDatabase.IDatabaseService::Create(string, class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, int32, string, string)
0x20a6e  unbox.any [mscorlib]System.Guid
0x20a73  stloc.s  4
0x20a75  ldloc.2
0x20a76  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.ServerData::get_Id()
0x20a7b  ldloc.s  4
0x20a7d  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x20a82  brfalse.s loc_20A8F
0x20a84  ldstr    aServerIdsMustB// "Server Ids must be equal"
0x20a89  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x20a8e  throw
0x20a8f  ldc.i4.s 0x2B
0x20a91  ldloc.2
0x20a92  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.ServerData::get_Id()
0x20a97  stloc.s  5
0x20a99  ldloca.s 5
0x20a9b  ldstr    aB// "B"
0x20aa0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x20aa5  call     instance string [mscorlib]System.Guid::ToString(string, class [mscorlib]System.IFormatProvider)
0x20aaa  call     void [Microsoft.Crm.Core]Microsoft.Crm.NotificationManager::FireNonOrganizationSpecificEvent(valuetype [Microsoft.Crm.Core]Microsoft.Crm.NotificationEventType, string)
0x20aaf  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x20ab4  ldc.i4.s 0x14
0x20ab6  ldstr    aCreatedServerI// "Created Server, Id=({0})"
0x20abb  ldc.i4.1
0x20abc  newarr   [mscorlib]System.Object
0x20ac1  dup
0x20ac2  ldc.i4.0
0x20ac3  ldloc.2
0x20ac4  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Admin.AdminService.ServerData::get_Id()
0x20ac9  box      [mscorlib]System.Guid
0x20ace  stelem.ref
0x20acf  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x20ad4  ldloc.2
0x20ad5  stloc.s  6
0x20ad7  leave.s  loc_20B0C
0x20ad9  ldloc.3
0x20ada  brfalse.s loc_20AE2
0x20adc  ldloc.3
0x20add  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x20ae2  endfinally
0x20ae3  stloc.s  7
0x20ae5  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x20aea  ldc.i4.s 0x14
0x20aec  ldstr    aExceptionCreat_4// "Exception creating Server, Name=({0} :{"...
0x20af1  ldc.i4.2
0x20af2  newarr   [mscorlib]System.Object
0x20af7  dup
0x20af8  ldc.i4.0
0x20af9  ldarg.1
0x20afa  stelem.ref
0x20afb  dup
0x20afc  ldc.i4.1
0x20afd  ldloc.s  7
0x20aff  callvirt instance string [mscorlib]System.Exception::get_Message()
0x20b04  stelem.ref
0x20b05  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x20b0a  rethrow
0x20b0c  ldloc.s  6
0x20b0e  ret
```
