# Microsoft.Crm.Tools.Admin.OneTimePostAppsInstallUpgradeAction::InitializeEntityToBaseSolutionMap

- ea: `0xaab0`
- end: `0xab6b`
- name: `Microsoft.Crm.Tools.Admin.OneTimePostAppsInstallUpgradeAction::InitializeEntityToBaseSolutionMap`
- size: `187`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0xa880`

## callees

- `0xaab0`
- `0xab70`
- `0xabc0`

## string_xrefs

- `0xaabb`: `\n						select distinct ObjectId, BaseSolutionId\n						from DependencyNodeBase\n						where ComponentType = 1\n						and BaseSolutionId in ({0}, {1})`

## pseudocode

```c

```

## disassembly

```asm
0xaab0  ldarg.0
0xaab1  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid>::.ctor()
0xaab6  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid> Microsoft.Crm.Tools.Admin.OneTimePostAppsInstallUpgradeAction::EntityToBaseSolutionMap
0xaabb  ldstr    aSelectDistinct_1// "\r\n\t\t\t\t\t\tselect distinct ObjectI"...
0xaac0  stloc.0
0xaac1  ldloc.0
0xaac2  ldsfld   valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.Admin.OneTimePostAppsInstallUpgradeAction::SystemSolutionId
0xaac7  call     string Microsoft.Crm.Tools.Admin.OneTimePostAppsInstallUpgradeAction::WrapGuidForSql(valuetype [mscorlib]System.Guid guid)
0xaacc  ldarg.0
0xaacd  ldarg.1
0xaace  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0xaad3  call     instance string Microsoft.Crm.Tools.Admin.OneTimePostAppsInstallUpgradeAction::GetCrmAppsSolutionIdsString(class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext context)
0xaad8  call     string [mscorlib]System.String::Format(string, object, object)
0xaadd  stloc.0
0xaade  ldarg.1
0xaadf  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0xaae4  ldloc.0
0xaae5  callvirt instance class [System.Data]System.Data.IDbCommand [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext::CreateSqlCommand(string)
0xaaea  stloc.1
0xaaeb  ldarg.1
0xaaec  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Connection()
0xaaf1  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Open()
0xaaf6  ldarg.1
0xaaf7  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Connection()
0xaafc  ldloc.1
0xaafd  ldarg.1
0xaafe  call     class [System.Data]System.Data.IDataReader [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::ExecuteQuery(class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection, class [System.Data]System.Data.IDbCommand, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xab03  stloc.2
0xab04  br.s     loc_AB25
0xab06  ldloc.2
0xab07  ldc.i4.0
0xab08  callvirt instance valuetype [mscorlib]System.Guid [System.Data]System.Data.IDataRecord::GetGuid(int32)
0xab0d  stloc.3
0xab0e  ldloc.2
0xab0f  ldc.i4.1
0xab10  callvirt instance valuetype [mscorlib]System.Guid [System.Data]System.Data.IDataRecord::GetGuid(int32)
0xab15  stloc.s  4
0xab17  ldarg.0
0xab18  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid> Microsoft.Crm.Tools.Admin.OneTimePostAppsInstallUpgradeAction::EntityToBaseSolutionMap
0xab1d  ldloc.3
0xab1e  ldloc.s  4
0xab20  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid>::Add(var<u1>, !!T0)
0xab25  ldloc.2
0xab26  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0xab2b  brtrue.s loc_AB06
0xab2d  leave.s  loc_AB64
0xab2f  ldloc.2
0xab30  brfalse.s loc_AB38
0xab32  ldloc.2
0xab33  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xab38  endfinally
0xab39  ldarg.1
0xab3a  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Connection()
0xab3f  brfalse.s loc_AB59
0xab41  ldarg.1
0xab42  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Connection()
0xab47  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::IsConnectionOpen()
0xab4c  brfalse.s loc_AB59
0xab4e  ldarg.1
0xab4f  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Connection()
0xab54  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::Close()
0xab59  endfinally
0xab5a  ldloc.1
0xab5b  brfalse.s loc_AB63
0xab5d  ldloc.1
0xab5e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xab63  endfinally
0xab64  ldarg.0
0xab65  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid> Microsoft.Crm.Tools.Admin.OneTimePostAppsInstallUpgradeAction::EntityToBaseSolutionMap
0xab6a  ret
```
