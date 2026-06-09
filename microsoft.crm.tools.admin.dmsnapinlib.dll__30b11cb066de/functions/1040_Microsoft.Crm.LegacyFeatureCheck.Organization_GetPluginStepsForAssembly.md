# Microsoft.Crm.LegacyFeatureCheck.Organization::GetPluginStepsForAssembly

- ea: `0x1040`
- end: `0x110a`
- name: `Microsoft.Crm.LegacyFeatureCheck.Organization::GetPluginStepsForAssembly`
- size: `202`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1590`

## callees

- `0xee0`
- `0x1040`
- `0x12a0`
- `0x17b0`
- `0x17d0`
- `0x17f0`
- `0x1810`
- `0x1840`

## string_xrefs

- `0x1065`: `select distinct\nm.Name as SdkMessageName,\np.TypeName,\np.PluginTypeId,\ne.LogicalName\nfrom SdkMessageProcessingStepBase step with (NOLOCK) \njoin SdkMessageBase m with (NOLOCK) on (step.SdkMessageId = m.SdkMessageId)\njoin PluginTypeBase p with (NOLOCK) on (p.PluginTypeId = step.PluginTypeId)\njoin PluginAssemblyBase pa with (NOLOCK) on (pa.PluginAssemblyId = p.PluginAssemblyId)\nleft join SdkMessageFilterBase f with (NOLOCK) on (f.SdkMessageFilterId = step.SdkMessageFilterId)\nleft`
- `0x10c7`: `PluginTypeId`

## pseudocode

```c

```

## disassembly

```asm
0x1040  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.LegacyFeatureCheck.PluginStep>::.ctor()
0x1045  stloc.0
0x1046  ldarg.0
0x1047  call     instance string Microsoft.Crm.LegacyFeatureCheck.Organization::get_ConnectionString()
0x104c  newobj   instance void [System.Data]System.Data.SqlClient.SqlConnection::.ctor(string)
0x1051  stloc.1
0x1052  ldloc.1
0x1053  callvirt instance void [System.Data]System.Data.Common.DbConnection::Open()
0x1058  ldloc.1
0x1059  callvirt instance class [System.Data]System.Data.SqlClient.SqlCommand [System.Data]System.Data.SqlClient.SqlConnection::CreateCommand()
0x105e  stloc.2
0x105f  ldloc.2
0x1060  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1065  ldstr    aSelectDistinct// "select distinct\r\nm.Name as SdkMessage"...
0x106a  ldc.i4.1
0x106b  newarr   [mscorlib]System.Object
0x1070  dup
0x1071  ldc.i4.0
0x1072  ldarg.1
0x1073  box      [mscorlib]System.Guid
0x1078  stelem.ref
0x1079  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x107e  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_CommandText(string)
0x1083  ldloc.2
0x1084  callvirt instance class [System.Data]System.Data.SqlClient.SqlDataReader [System.Data]System.Data.SqlClient.SqlCommand::ExecuteReader()
0x1089  stloc.3
0x108a  br.s     loc_10E0
0x108c  ldloc.0
0x108d  newobj   instance void Microsoft.Crm.LegacyFeatureCheck.PluginStep::.ctor()
0x1092  dup
0x1093  ldloc.3
0x1094  ldstr    aSdkmessagename// "SdkMessageName"
0x1099  call     string Microsoft.Crm.LegacyFeatureCheck.Extensions::ReadString(class [System.Data]System.Data.SqlClient.SqlDataReader reader, string columnName)
0x109e  callvirt instance void Microsoft.Crm.LegacyFeatureCheck.PluginStep::set_SdkMessage(string value)
0x10a3  dup
0x10a4  ldloc.3
0x10a5  ldstr    aTypename// "TypeName"
0x10aa  call     string Microsoft.Crm.LegacyFeatureCheck.Extensions::ReadString(class [System.Data]System.Data.SqlClient.SqlDataReader reader, string columnName)
0x10af  callvirt instance void Microsoft.Crm.LegacyFeatureCheck.PluginStep::set_PluginType(string value)
0x10b4  dup
0x10b5  ldloc.3
0x10b6  ldstr    aLogicalname// "LogicalName"
0x10bb  call     string Microsoft.Crm.LegacyFeatureCheck.Extensions::ReadString(class [System.Data]System.Data.SqlClient.SqlDataReader reader, string columnName)
0x10c0  callvirt instance void Microsoft.Crm.LegacyFeatureCheck.PluginStep::set_Entity(string value)
0x10c5  dup
0x10c6  ldloc.3
0x10c7  ldstr    aPlugintypeid// "PluginTypeId"
0x10cc  callvirt instance object [System.Data]System.Data.Common.DbDataReader::get_Item(string)
0x10d1  unbox.any [mscorlib]System.Guid
0x10d6  callvirt instance void Microsoft.Crm.LegacyFeatureCheck.PluginStep::set_PluginTypeId(valuetype [mscorlib]System.Guid value)
0x10db  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.LegacyFeatureCheck.PluginStep>::Add(var<u1>)
0x10e0  ldloc.3
0x10e1  callvirt instance bool [System.Data]System.Data.Common.DbDataReader::Read()
0x10e6  brtrue.s loc_108C
0x10e8  leave.s  loc_1108
0x10ea  ldloc.3
0x10eb  brfalse.s loc_10F3
0x10ed  ldloc.3
0x10ee  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x10f3  endfinally
0x10f4  ldloc.2
0x10f5  brfalse.s loc_10FD
0x10f7  ldloc.2
0x10f8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x10fd  endfinally
0x10fe  ldloc.1
0x10ff  brfalse.s loc_1107
0x1101  ldloc.1
0x1102  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1107  endfinally
0x1108  ldloc.0
0x1109  ret
```
