# Microsoft.Crm.ApplicationConfig::GetReportServerUrl

- ea: `0x18d80`
- end: `0x18e50`
- name: `Microsoft.Crm.ApplicationConfig::GetReportServerUrl`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18d80`

## string_xrefs

- `0x18dac`: `D:\a\1\s\src\Shared\Server\Utils\ApplicationConfig.cs`
- `0x18e15`: `D:\a\1\s\src\Shared\Server\Utils\ApplicationConfig.cs`

## pseudocode

```c

```

## disassembly

```asm
0x18d80  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInClientContext()
0x18d85  brtrue   loc_18E4C
0x18d8a  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDataCenterInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DataCenterInfoProvider::get_Instance()
0x18d8f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IDataCenterInfoProvider::GetDatacenterId()
0x18d94  ldarg.0
0x18d95  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x18d9a  brfalse.s loc_18DCB
0x18d9c  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.OrganizationSettingsProvider::get_Instance()
0x18da1  ldarg.1
0x18da2  ldc.i4   0xEC
0x18da7  ldstr    aGetreportserve// "GetReportServerUrl"
0x18dac  ldstr    aDA1SSrcSharedS_0// "D:\\a\\1\\s\\src\\Shared\\Server\\Utils"...
0x18db1  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationSettingsProvider::GetOrganization(valuetype [mscorlib]System.Guid, int32, string, string)
0x18db6  ldstr    aSrsurl// "SrsUrl"
0x18dbb  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x18dc0  castclass [mscorlib]System.String
0x18dc5  newobj   instance void [System]System.Uri::.ctor(string)
0x18dca  ret
0x18dcb  ldarg.0
0x18dcc  call     class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection [Microsoft.Crm.Core]Microsoft.Crm.ConfigurationDatabase.ConfigurationMetadata::GetSiteConfigDBConnection(valuetype [mscorlib]System.Guid)
0x18dd1  stloc.0
0x18dd2  ldloc.0
0x18dd3  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0x18dd8  ldloc.0
0x18dd9  ldstr    aSelectTop1Repo// "SELECT TOP 1 ReportServerUrl FROM Scale"...
0x18dde  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::CreateCommand(string)
0x18de3  stloc.1
0x18de4  ldloc.1
0x18de5  callvirt instance class [System.Data]System.Data.IDataParameterCollection [System.Data]System.Data.IDbCommand::get_Parameters()
0x18dea  castclass [System.Data]System.Data.SqlClient.SqlParameterCollection
0x18def  ldstr    aScalegroupid// "@scaleGroupId"
0x18df4  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationMetadataProvider [Microsoft.Crm.Core]Microsoft.Crm.OrganizationMetadataProvider::get_Instance()
0x18df9  ldarg.1
0x18dfa  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationMetadataProvider::GetOrganizationScaleGroupId(valuetype [mscorlib]System.Guid)
0x18dff  box      [mscorlib]System.Guid
0x18e04  callvirt instance class [System.Data]System.Data.SqlClient.SqlParameter [System.Data]System.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x18e09  pop
0x18e0a  ldloc.1
0x18e0b  ldc.i4   0xF9
0x18e10  ldstr    aGetreportserve// "GetReportServerUrl"
0x18e15  ldstr    aDA1SSrcSharedS_0// "D:\\a\\1\\s\\src\\Shared\\Server\\Utils"...
0x18e1a  call     object [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::ExecuteScalar(class [System.Data]System.Data.IDbCommand, int32, string, string)
0x18e1f  stloc.2
0x18e20  ldloc.2
0x18e21  brfalse.s loc_18E36
0x18e23  ldloc.2
0x18e24  callvirt instance string [mscorlib]System.Object::ToString()
0x18e29  callvirt instance string [mscorlib]System.String::Trim()
0x18e2e  newobj   instance void [System]System.Uri::.ctor(string)
0x18e33  stloc.3
0x18e34  leave.s  loc_18E4E
0x18e36  leave.s  loc_18E4C
0x18e38  ldloc.1
0x18e39  brfalse.s loc_18E41
0x18e3b  ldloc.1
0x18e3c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x18e41  endfinally
0x18e42  ldloc.0
0x18e43  brfalse.s loc_18E4B
0x18e45  ldloc.0
0x18e46  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x18e4b  endfinally
0x18e4c  ldnull
0x18e4d  ret
0x18e4e  ldloc.3
0x18e4f  ret
```
