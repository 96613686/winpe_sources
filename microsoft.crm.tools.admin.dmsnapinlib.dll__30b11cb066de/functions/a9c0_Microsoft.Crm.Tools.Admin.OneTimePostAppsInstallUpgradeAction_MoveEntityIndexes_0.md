# Microsoft.Crm.Tools.Admin.OneTimePostAppsInstallUpgradeAction::MoveEntityIndexes_0

- ea: `0xa9c0`
- end: `0xaaa7`
- name: `Microsoft.Crm.Tools.Admin.OneTimePostAppsInstallUpgradeAction::MoveEntityIndexes_0`
- size: `231`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0xa900`

## callees

- `0xa9c0`
- `0xabc0`

## string_xrefs

- `0xaa1d`: `update EntityIndex set SolutionId = {0}\n									where IndexId = {1}`

## pseudocode

```c

```

## disassembly

```asm
0xa9c0  ldarg.1
0xa9c1  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid>::get_Keys()
0xa9c6  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid>::GetEnumerator()
0xa9cb  stloc.0
0xa9cc  br       loc_AA8A
0xa9d1  ldloca.s 0
0xa9d3  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid>::get_Current()
0xa9d8  stloc.1
0xa9d9  ldarg.1
0xa9da  ldloc.1
0xa9db  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid>::get_Item(void)
0xa9e0  stloc.2
0xa9e1  ldarg.0
0xa9e2  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid> Microsoft.Crm.Tools.Admin.OneTimePostAppsInstallUpgradeAction::EntityToBaseSolutionMap
0xa9e7  ldloc.2
0xa9e8  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid>::ContainsKey(var<u1>)
0xa9ed  brtrue.s loc_A9F6
0xa9ef  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xa9f4  br.s     loc_AA02
0xa9f6  ldarg.0
0xa9f7  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid> Microsoft.Crm.Tools.Admin.OneTimePostAppsInstallUpgradeAction::EntityToBaseSolutionMap
0xa9fc  ldloc.2
0xa9fd  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid>::get_Item(void)
0xaa02  stloc.3
0xaa03  ldloc.3
0xaa04  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xaa09  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xaa0e  brfalse.s loc_AA8A
0xaa10  ldloc.3
0xaa11  ldsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.Admin.OneTimePostAppsInstallUpgradeAction::SystemSolutionId
0xaa16  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xaa1b  brfalse.s loc_AA8A
0xaa1d  ldstr    aUpdateEntityin// "update EntityIndex set SolutionId = {0}"...
0xaa22  stloc.s  4
0xaa24  ldloc.s  4
0xaa26  ldloc.3
0xaa27  call     string Microsoft.Crm.Tools.Admin.OneTimePostAppsInstallUpgradeAction::WrapGuidForSql(valuetype [mscorlib]System.Guid guid)
0xaa2c  ldloc.1
0xaa2d  call     string Microsoft.Crm.Tools.Admin.OneTimePostAppsInstallUpgradeAction::WrapGuidForSql(valuetype [mscorlib]System.Guid guid)
0xaa32  call     string [mscorlib]System.String::Format(string, object, object)
0xaa37  stloc.s  4
0xaa39  ldarg.2
0xaa3a  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0xaa3f  ldloc.s  4
0xaa41  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext::CreateSqlCommand(string)
0xaa46  stloc.s  5
0xaa48  ldarg.2
0xaa49  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Connection()
0xaa4e  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0xaa53  ldloc.s  5
0xaa55  callvirt instance int32 [System.Data]System.Data.IDbCommand::ExecuteNonQuery()
0xaa5a  pop
0xaa5b  leave.s  loc_AA8A
0xaa5d  ldarg.2
0xaa5e  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Connection()
0xaa63  brfalse.s loc_AA7D
0xaa65  ldarg.2
0xaa66  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Connection()
0xaa6b  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::IsConnectionOpen()
0xaa70  brfalse.s loc_AA7D
0xaa72  ldarg.2
0xaa73  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Connection()
0xaa78  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Close()
0xaa7d  endfinally
0xaa7e  ldloc.s  5
0xaa80  brfalse.s loc_AA89
0xaa82  ldloc.s  5
0xaa84  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xaa89  endfinally
0xaa8a  ldloca.s 0
0xaa8c  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid>::MoveNext()
0xaa91  brtrue   loc_A9D1
0xaa96  leave.s  loc_AAA6
0xaa98  ldloca.s 0
0xaa9a  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid>
0xaaa0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xaaa5  endfinally
0xaaa6  ret
```
