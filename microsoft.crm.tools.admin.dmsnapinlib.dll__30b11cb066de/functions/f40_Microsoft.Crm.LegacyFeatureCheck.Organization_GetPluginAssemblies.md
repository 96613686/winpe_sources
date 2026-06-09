# Microsoft.Crm.LegacyFeatureCheck.Organization::GetPluginAssemblies

- ea: `0xf40`
- end: `0x1040`
- name: `Microsoft.Crm.LegacyFeatureCheck.Organization::GetPluginAssemblies`
- size: `256`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18c0`

## callees

- `0xee0`
- `0xf40`
- `0x12a0`
- `0x12f0`
- `0x1310`
- `0x1330`
- `0x1350`
- `0x1370`
- `0x1390`
- `0x13b0`
- `0x13d0`
- `0x1760`

## string_xrefs

- `0xf60`: `select PluginAssemblyId, Name, Version, Culture, PublicKeyToken, SourceType, Path, Content from PluginAssemblyBase with (NOLOCK) where CustomizationLevel >0 and PublicKeyToken != '31bf3856ad364e35'`
- `0xf7e`: `PluginAssemblyId`
- `0xfc7`: `PublicKeyToken`

## pseudocode

```c

```

## disassembly

```asm
0xf40  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.LegacyFeatureCheck.PluginAssembly>::.ctor()
0xf45  stloc.0
0xf46  ldarg.0
0xf47  call     instance string Microsoft.Crm.LegacyFeatureCheck.Organization::get_ConnectionString()
0xf4c  newobj   instance void [System.Data]System.Data.SqlClient.SqlConnection::.ctor(string)
0xf51  stloc.1
0xf52  ldloc.1
0xf53  callvirt instance void [System.Data]System.Data.Common.DbConnection::Open()
0xf58  ldloc.1
0xf59  callvirt instance class [System.Data]System.Data.SqlClient.SqlCommand [System.Data]System.Data.SqlClient.SqlConnection::CreateCommand()
0xf5e  stloc.2
0xf5f  ldloc.2
0xf60  ldstr    aSelectPluginas// "select PluginAssemblyId, Name, Version,"...
0xf65  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_CommandText(string)
0xf6a  ldloc.2
0xf6b  callvirt instance class [System.Data]System.Data.SqlClient.SqlDataReader [System.Data]System.Data.SqlClient.SqlCommand::ExecuteReader()
0xf70  stloc.3
0xf71  br       loc_1013
0xf76  ldloc.0
0xf77  newobj   instance void Microsoft.Crm.LegacyFeatureCheck.PluginAssembly::.ctor()
0xf7c  dup
0xf7d  ldloc.3
0xf7e  ldstr    aPluginassembly// "PluginAssemblyId"
0xf83  callvirt instance object [System.Data]System.Data.Common.DbDataReader::get_Item(string)
0xf88  unbox.any [mscorlib]System.Guid
0xf8d  callvirt instance void Microsoft.Crm.LegacyFeatureCheck.PluginAssembly::set_Id(valuetype [mscorlib]System.Guid value)
0xf92  dup
0xf93  ldloc.3
0xf94  ldstr    aName// "Name"
0xf99  call     string Microsoft.Crm.LegacyFeatureCheck.Extensions::ReadString(class [System.Data]System.Data.SqlClient.SqlDataReader reader, string columnName)
0xf9e  callvirt instance void Microsoft.Crm.LegacyFeatureCheck.PluginAssembly::set_Name(string value)
0xfa3  dup
0xfa4  ldloc.3
0xfa5  ldstr    aVersion// "Version"
0xfaa  call     string Microsoft.Crm.LegacyFeatureCheck.Extensions::ReadString(class [System.Data]System.Data.SqlClient.SqlDataReader reader, string columnName)
0xfaf  callvirt instance void Microsoft.Crm.LegacyFeatureCheck.PluginAssembly::set_Version(string value)
0xfb4  dup
0xfb5  ldloc.3
0xfb6  ldstr    aCulture// "Culture"
0xfbb  call     string Microsoft.Crm.LegacyFeatureCheck.Extensions::ReadString(class [System.Data]System.Data.SqlClient.SqlDataReader reader, string columnName)
0xfc0  callvirt instance void Microsoft.Crm.LegacyFeatureCheck.PluginAssembly::set_Culture(string value)
0xfc5  dup
0xfc6  ldloc.3
0xfc7  ldstr    aPublickeytoken// "PublicKeyToken"
0xfcc  call     string Microsoft.Crm.LegacyFeatureCheck.Extensions::ReadString(class [System.Data]System.Data.SqlClient.SqlDataReader reader, string columnName)
0xfd1  callvirt instance void Microsoft.Crm.LegacyFeatureCheck.PluginAssembly::set_PublicKeyToken(string value)
0xfd6  dup
0xfd7  ldloc.3
0xfd8  ldstr    aSourcetype// "SourceType"
0xfdd  callvirt instance object [System.Data]System.Data.Common.DbDataReader::get_Item(string)
0xfe2  unbox.any Microsoft.Crm.LegacyFeatureCheck.PluginAssemblyLocation
0xfe7  callvirt instance void Microsoft.Crm.LegacyFeatureCheck.PluginAssembly::set_Source(valuetype Microsoft.Crm.LegacyFeatureCheck.PluginAssemblyLocation value)
0xfec  dup
0xfed  ldloc.3
0xfee  ldstr    aPath// "Path"
0xff3  call     string Microsoft.Crm.LegacyFeatureCheck.Extensions::ReadString(class [System.Data]System.Data.SqlClient.SqlDataReader reader, string columnName)
0xff8  callvirt instance void Microsoft.Crm.LegacyFeatureCheck.PluginAssembly::set_Path(string value)
0xffd  dup
0xffe  ldloc.3
0xfff  ldstr    aContent// "Content"
0x1004  call     string Microsoft.Crm.LegacyFeatureCheck.Extensions::ReadString(class [System.Data]System.Data.SqlClient.SqlDataReader reader, string columnName)
0x1009  callvirt instance void Microsoft.Crm.LegacyFeatureCheck.PluginAssembly::set_Contents(string value)
0x100e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.LegacyFeatureCheck.PluginAssembly>::Add(var<u1>)
0x1013  ldloc.3
0x1014  callvirt instance bool [System.Data]System.Data.Common.DbDataReader::Read()
0x1019  brtrue   loc_F76
0x101e  leave.s  loc_103E
0x1020  ldloc.3
0x1021  brfalse.s loc_1029
0x1023  ldloc.3
0x1024  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1029  endfinally
0x102a  ldloc.2
0x102b  brfalse.s loc_1033
0x102d  ldloc.2
0x102e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1033  endfinally
0x1034  ldloc.1
0x1035  brfalse.s loc_103D
0x1037  ldloc.1
0x1038  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x103d  endfinally
0x103e  ldloc.0
0x103f  ret
```
