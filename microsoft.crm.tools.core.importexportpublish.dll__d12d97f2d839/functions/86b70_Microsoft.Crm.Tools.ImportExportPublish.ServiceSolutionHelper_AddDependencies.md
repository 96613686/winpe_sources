# Microsoft.Crm.Tools.ImportExportPublish.ServiceSolutionHelper::AddDependencies

- ea: `0x86b70`
- end: `0x86de9`
- name: `Microsoft.Crm.Tools.ImportExportPublish.ServiceSolutionHelper::AddDependencies`
- size: `633`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x75980`

## callees

- `0x2a7b0`
- `0x2aad0`
- `0x6b110`
- `0x6b380`
- `0x86b70`
- `0x8abd0`
- `0x8af80`

## string_xrefs

- `0x86be1`: `componenttype`
- `0x86c30`: `componenttype`
- `0x86c80`: `componenttype`
- `0x86cd0`: `componenttype`
- `0x86b8e`: `SolutionComponent`

## pseudocode

```c

```

## disassembly

```asm
0x86b70  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SolutionComponentService::.ctor()
0x86b75  stloc.0
0x86b76  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0x86b7b  pop
0x86b7c  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0x86b81  stloc.1
0x86b82  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0x86b87  stloc.2
0x86b88  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0x86b8d  stloc.3
0x86b8e  ldstr    aSolutioncompon// "SolutionComponent"
0x86b93  ldarg.0
0x86b94  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ServiceSolutionHelper::_context
0x86b99  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x86b9e  stloc.s  4
0x86ba0  ldloc.s  4
0x86ba2  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x86ba7  ldstr    aSolutionid// "solutionid"
0x86bac  ldc.i4.0
0x86bad  ldarg.0
0x86bae  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.ImportExportPublish.ServiceSolutionHelper::_solutionId
0x86bb3  box      [mscorlib]System.Guid
0x86bb8  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x86bbd  pop
0x86bbe  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x86bc3  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x86bc8  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_MocaOffline()
0x86bcd  ldarg.0
0x86bce  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ServiceSolutionHelper::_context
0x86bd3  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsNonOrgFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x86bd8  brfalse.s loc_86C29
0x86bda  ldloc.s  4
0x86bdc  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x86be1  ldstr    aComponenttype// "componenttype"
0x86be6  ldc.i4.8
0x86be7  ldc.i4.4
0x86be8  newarr   [mscorlib]System.Object
0x86bed  dup
0x86bee  ldc.i4.0
0x86bef  ldc.i4   0x96
0x86bf4  box      [mscorlib]System.Int32
0x86bf9  stelem.ref
0x86bfa  dup
0x86bfb  ldc.i4.1
0x86bfc  ldc.i4   0x98
0x86c01  box      [mscorlib]System.Int32
0x86c06  stelem.ref
0x86c07  dup
0x86c08  ldc.i4.2
0x86c09  ldc.i4   0x9A
0x86c0e  box      [mscorlib]System.Int32
0x86c13  stelem.ref
0x86c14  dup
0x86c15  ldc.i4.3
0x86c16  ldc.i4   0xA1
0x86c1b  box      [mscorlib]System.Int32
0x86c20  stelem.ref
0x86c21  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, class [mscorlib]System.Array)
0x86c26  pop
0x86c27  br.s     loc_86C69
0x86c29  ldloc.s  4
0x86c2b  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x86c30  ldstr    aComponenttype// "componenttype"
0x86c35  ldc.i4.8
0x86c36  ldc.i4.3
0x86c37  newarr   [mscorlib]System.Object
0x86c3c  dup
0x86c3d  ldc.i4.0
0x86c3e  ldc.i4   0x96
0x86c43  box      [mscorlib]System.Int32
0x86c48  stelem.ref
0x86c49  dup
0x86c4a  ldc.i4.1
0x86c4b  ldc.i4   0x98
0x86c50  box      [mscorlib]System.Int32
0x86c55  stelem.ref
0x86c56  dup
0x86c57  ldc.i4.2
0x86c58  ldc.i4   0x9A
0x86c5d  box      [mscorlib]System.Int32
0x86c62  stelem.ref
0x86c63  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, class [mscorlib]System.Array)
0x86c68  pop
0x86c69  ldloc.s  4
0x86c6b  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x86c70  ldc.i4.4
0x86c71  newarr   [mscorlib]System.String
0x86c76  dup
0x86c77  ldc.i4.0
0x86c78  ldstr    aObjectid// "objectid"
0x86c7d  stelem.ref
0x86c7e  dup
0x86c7f  ldc.i4.1
0x86c80  ldstr    aComponenttype// "componenttype"
0x86c85  stelem.ref
0x86c86  dup
0x86c87  ldc.i4.2
0x86c88  ldstr    aSolutionid// "solutionid"
0x86c8d  stelem.ref
0x86c8e  dup
0x86c8f  ldc.i4.3
0x86c90  ldstr    aIsmetadata// "ismetadata"
0x86c95  stelem.ref
0x86c96  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x86c9b  ldloc.0
0x86c9c  ldloc.s  4
0x86c9e  ldarg.0
0x86c9f  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ServiceSolutionHelper::_context
0x86ca4  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x86ca9  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x86cae  stloc.s  5
0x86cb0  br.s     loc_86D1A
0x86cb2  ldloc.s  5
0x86cb4  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x86cb9  castclass [Microsoft.Crm.Entities]Microsoft.Crm.Entities.SolutionComponent
0x86cbe  dup
0x86cbf  ldstr    aObjectid// "objectid"
0x86cc4  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x86cc9  unbox.any [mscorlib]System.Guid
0x86cce  stloc.s  6
0x86cd0  ldstr    aComponenttype// "componenttype"
0x86cd5  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x86cda  unbox.any [mscorlib]System.Int32
0x86cdf  stloc.s  7
0x86ce1  ldloc.s  7
0x86ce3  ldc.i4   0x98
0x86ce8  beq.s    loc_86D08
0x86cea  ldloc.s  7
0x86cec  ldc.i4   0x9A
0x86cf1  beq.s    loc_86CFE
0x86cf3  ldloc.s  7
0x86cf5  ldc.i4   0xA1
0x86cfa  beq.s    loc_86D12
0x86cfc  br.s     loc_86D1A
0x86cfe  ldloc.1
0x86cff  ldloc.s  6
0x86d01  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x86d06  br.s     loc_86D1A
0x86d08  ldloc.2
0x86d09  ldloc.s  6
0x86d0b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x86d10  br.s     loc_86D1A
0x86d12  ldloc.3
0x86d13  ldloc.s  6
0x86d15  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Add(var<u1>)
0x86d1a  ldloc.s  5
0x86d1c  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x86d21  brtrue.s loc_86CB2
0x86d23  leave.s  loc_86D3A
0x86d25  ldloc.s  5
0x86d27  isinst   [mscorlib]System.IDisposable
0x86d2c  stloc.s  8
0x86d2e  ldloc.s  8
0x86d30  brfalse.s loc_86D39
0x86d32  ldloc.s  8
0x86d34  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x86d39  endfinally
0x86d3a  ldloc.1
0x86d3b  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::get_Count()
0x86d40  ldc.i4.0
0x86d41  ble.s    loc_86D72
0x86d43  ldloc.1
0x86d44  ldarg.0
0x86d45  ldfld    string Microsoft.Crm.Tools.ImportExportPublish.ServiceSolutionHelper::_solutionName
0x86d4a  ldarg.0
0x86d4b  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ServiceSolutionHelper::_context
0x86d50  ldarg.0
0x86d51  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ExportTracer Microsoft.Crm.Tools.ImportExportPublish.ServiceSolutionHelper::_tracer
0x86d56  ldarg.0
0x86d57  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.Tools.ImportExportPublish.ServiceSolutionHelper::_cache
0x86d5c  ldarg.0
0x86d5d  ldfld    bool Microsoft.Crm.Tools.ImportExportPublish.ServiceSolutionHelper::_exportDeltaOverride
0x86d62  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.ConvertRuleHandler::.ctor(class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> ConvertRules, string solutionName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class Microsoft.Crm.Tools.ImportExportPublish.ExportTracer tracer, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache cache, bool exportDeltaOverride)
0x86d67  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.ConvertRuleHandler::AddConvertRuleDependencies()
0x86d6c  ldloc.1
0x86d6d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Clear()
0x86d72  ldloc.2
0x86d73  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::get_Count()
0x86d78  ldc.i4.0
0x86d79  ble.s    loc_86DB0
0x86d7b  ldloc.2
0x86d7c  ldarg.0
0x86d7d  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ServiceSolutionHelper::_context
0x86d82  ldarg.0
0x86d83  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ExportTracer Microsoft.Crm.Tools.ImportExportPublish.ServiceSolutionHelper::_tracer
0x86d88  ldarg.0
0x86d89  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.Tools.ImportExportPublish.ServiceSolutionHelper::_cache
0x86d8e  ldarg.0
0x86d8f  ldfld    bool Microsoft.Crm.Tools.ImportExportPublish.ServiceSolutionHelper::_exportDeltaOverride
0x86d94  ldarg.0
0x86d95  ldfld    string Microsoft.Crm.Tools.ImportExportPublish.ServiceSolutionHelper::_solutionName
0x86d9a  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.SLAHandler::.ctor(class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> slaCollection, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class Microsoft.Crm.Tools.ImportExportPublish.ExportTracer tracer, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache cache, bool exportDeltaOverride, string _solutionName)
0x86d9f  ldarg.0
0x86da0  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext Microsoft.Crm.Tools.ImportExportPublish.ServiceSolutionHelper::_exportToTargetVersionContext
0x86da5  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.SLAHandler::AddSlaDependencies(class Microsoft.Crm.Tools.ImportExportPublish.ExportToTargetVersionContext exportToTargetVersionContext)
0x86daa  ldloc.2
0x86dab  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Clear()
0x86db0  ldloc.3
0x86db1  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::get_Count()
0x86db6  ldc.i4.0
0x86db7  ble.s    loc_86DE8
0x86db9  ldloc.3
0x86dba  ldarg.0
0x86dbb  ldfld    string Microsoft.Crm.Tools.ImportExportPublish.ServiceSolutionHelper::_solutionName
0x86dc0  ldarg.0
0x86dc1  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Tools.ImportExportPublish.ServiceSolutionHelper::_context
0x86dc6  ldarg.0
0x86dc7  ldfld    class Microsoft.Crm.Tools.ImportExportPublish.ExportTracer Microsoft.Crm.Tools.ImportExportPublish.ServiceSolutionHelper::_tracer
0x86dcc  ldarg.0
0x86dcd  ldfld    class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.Tools.ImportExportPublish.ServiceSolutionHelper::_cache
0x86dd2  ldarg.0
0x86dd3  ldfld    bool Microsoft.Crm.Tools.ImportExportPublish.ServiceSolutionHelper::_exportDeltaOverride
0x86dd8  newobj   instance void Microsoft.Crm.Tools.ImportExportPublish.MobileOfflineProfileHandler::.ctor(class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid> MobileOfflineProfiles, string solutionName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class Microsoft.Crm.Tools.ImportExportPublish.ExportTracer tracer, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache cache, bool exportDeltaOverride)
0x86ddd  callvirt instance void Microsoft.Crm.Tools.ImportExportPublish.MobileOfflineProfileHandler::AddMobileOfflineProfileDependencies()
0x86de2  ldloc.3
0x86de3  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::Clear()
0x86de8  ret
```
