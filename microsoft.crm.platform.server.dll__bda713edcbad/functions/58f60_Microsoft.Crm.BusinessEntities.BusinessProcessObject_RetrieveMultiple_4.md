# Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple_4

- ea: `0x58f60`
- end: `0x5925f`
- name: `Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple_4`
- size: `767`
- prototype: ``
- caller_count: `3`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x58f50`
- `0x59330`
- `0x7f7f0`

## callees

- `0x140e0`
- `0x18520`
- `0x18540`
- `0x18df0`
- `0x1aa80`
- `0x58f60`
- `0x592a0`
- `0x5cf90`
- `0x5e4a0`
- `0x66f10`
- `0x67120`
- `0x68780`
- `0x68940`
- `0x8b890`
- `0x8b8e0`

## string_xrefs

- `0x58f79`: `DatabaseQueryTarget of Table is not allowed in RetrieveMultiple - raw rows must be read through a different API`
- `0x59049`: `Not An Error: [ExtendedRetrieveMultipleNullChecks] Completed PreRetrieveMultiple events for RetrieveMultiple({0}); extensionArgs.Entities is now {2}`
- `0x590ae`: `[ExtendedRetrieveMultipleNullChecks] DoRetrieveMultiple(?, {1}, {2}, {3}, {4}, {5}) caused the return value for RetrieveMultiple({0}) to become null`
- `0x591bf`: `Not An Error: [ExtendedRetrieveMultipleNullChecks] Completed PostRetrieveMultiple events for RetrieveMultiple({0}) ; extensionArgs.Entities is now {1}`

## pseudocode

```c

```

## disassembly

```asm
0x58f60  ldarg.1
0x58f61  ldstr    aEntityexpressi_0// "entityExpression"
0x58f66  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x58f6b  ldarg.3
0x58f6c  ldstr    aContext// "context"
0x58f71  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x58f76  ldarg.2
0x58f77  brtrue.s loc_58F84
0x58f79  ldstr    aDatabasequeryt// "DatabaseQueryTarget of Table is not all"...
0x58f7e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0x58f83  throw
0x58f84  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationBuildVersionCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.OrganizationBuildVersionCache::Instance()
0x58f89  ldarg.3
0x58f8a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x58f8f  ldarg.3
0x58f90  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.BasicCrmCache`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.VersionCacheData>::LookupEntry(void, var<u1>)
0x58f95  callvirt instance class [mscorlib]System.Version [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.VersionCacheData::get_CrmVersion()
0x58f9a  ldarg.3
0x58f9b  callvirt instance class [mscorlib]System.Version Microsoft.Crm.BusinessEntities.ExecutionContext::get_SdkClientVersion()
0x58fa0  stloc.0
0x58fa1  ldarg.1
0x58fa2  callvirt instance class Microsoft.Crm.Query.ColumnSetExpression Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x58fa7  brtrue.s loc_58FAC
0x58fa9  ldc.i4.0
0x58faa  br.s     loc_58FBC
0x58fac  ldarg.1
0x58fad  callvirt instance class Microsoft.Crm.Query.ColumnSetExpression Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x58fb2  ldstr    aVersionnumber// "versionnumber"
0x58fb7  callvirt instance bool Microsoft.Crm.Query.ColumnSetExpression::ContainsColumn(string attribute)
0x58fbc  stloc.1
0x58fbd  ldc.i4.0
0x58fbe  stloc.2
0x58fbf  ldarg.1
0x58fc0  callvirt instance object Microsoft.Crm.Query.EntityExpression::Clone()
0x58fc5  castclass Microsoft.Crm.Query.EntityExpression
0x58fca  stloc.3
0x58fcb  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.VersionUtility::IsCarinaVersion(class [mscorlib]System.Version)
0x58fd0  brfalse.s loc_58FEA
0x58fd2  ldloc.0
0x58fd3  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.VersionUtility::IsCarinaVersion(class [mscorlib]System.Version)
0x58fd8  brfalse.s loc_58FEA
0x58fda  ldarg.3
0x58fdb  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext Microsoft.Crm.BusinessEntities.ExecutionContext::get_PluginContext()
0x58fe0  brfalse.s loc_58FEA
0x58fe2  ldarg.0
0x58fe3  ldloc.3
0x58fe4  call     instance bool Microsoft.Crm.BusinessEntities.BusinessProcessObject::TryAddRowVersionColumn(class Microsoft.Crm.Query.EntityExpression entityExpression)
0x58fe9  stloc.2
0x58fea  ldloc.3
0x58feb  callvirt instance class Microsoft.Crm.Query.FilterExpression Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x58ff0  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Query.FilterExpression::get_EntityMetadata()
0x58ff5  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x58ffa  ldarg.3
0x58ffb  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x59000  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::.ctor(string, valuetype [mscorlib]System.Guid)
0x59005  stloc.s  4
0x59007  ldnull
0x59008  ldnull
0x59009  ldloc.s  4
0x5900b  ldloc.3
0x5900c  ldarg.3
0x5900d  newobj   instance void Microsoft.Crm.BusinessEntities.ExtensionEventArgs::.ctor(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker moniker, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection entities, class Microsoft.Crm.Query.EntityExpression entityExpression, class Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x59012  stloc.s  5
0x59014  ldstr    aExtendedretrie// "ExtendedRetrieveMultipleNullChecks"
0x59019  ldc.i4.0
0x5901a  box      [mscorlib]System.Int32
0x5901f  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string, object)
0x59024  unbox.any [mscorlib]System.Int32
0x59029  ldc.i4.1
0x5902a  ceq
0x5902c  stloc.s  6
0x5902e  ldarg.0
0x5902f  ldfld    class PreRetrieveMultipleEventHandler Microsoft.Crm.BusinessEntities.BusinessProcessObject::PreRetrieveMultiple
0x59034  brfalse.s loc_5908B
0x59036  ldarg.0
0x59037  ldfld    class PreRetrieveMultipleEventHandler Microsoft.Crm.BusinessEntities.BusinessProcessObject::PreRetrieveMultiple
0x5903c  ldarg.0
0x5903d  ldloc.s  5
0x5903f  callvirt instance void PreRetrieveMultipleEventHandler::Invoke(object sender, class Microsoft.Crm.BusinessEntities.ExtensionEventArgs e)
0x59044  ldloc.s  6
0x59046  brfalse.s loc_5908B
0x59048  ldnull
0x59049  ldstr    aNotAnErrorExte// "Not An Error: [ExtendedRetrieveMultiple"...
0x5904e  ldc.i4.2
0x5904f  newarr   [mscorlib]System.Object
0x59054  dup
0x59055  ldc.i4.0
0x59056  ldloc.3
0x59057  callvirt instance class Microsoft.Crm.Query.FilterExpression Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x5905c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Query.FilterExpression::get_EntityMetadata()
0x59061  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x59066  stelem.ref
0x59067  dup
0x59068  ldc.i4.1
0x59069  ldloc.s  5
0x5906b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Entities()
0x59070  brfalse.s loc_59080
0x59072  ldloc.s  5
0x59074  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Entities()
0x59079  callvirt instance string [mscorlib]System.Object::ToString()
0x5907e  br.s     loc_59085
0x59080  ldstr    aNull_2// "null"
0x59085  stelem.ref
0x59086  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::Error(class [mscorlib]System.Exception, string, object[])
0x5908b  ldarg.0
0x5908c  ldloc.s  4
0x5908e  ldloc.3
0x5908f  ldarg.2
0x59090  ldarg.3
0x59091  ldloc.2
0x59092  ldloc.1
0x59093  call     instance void Microsoft.Crm.BusinessEntities.BusinessProcessObject::DoRetrieveMultiple(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection entities, class Microsoft.Crm.Query.EntityExpression entityExp, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.DatabaseQueryTarget queryTarget, class Microsoft.Crm.BusinessEntities.ExecutionContext context, [opt] bool needToSetRowVersion, [opt] bool isVersionNumberRequestedInRetrieve)
0x59098  ldloc.s  6
0x5909a  brfalse  loc_5916B
0x5909f  ldloc.s  4
0x590a1  brtrue.s loc_590F6
0x590a3  ldstr    asc_9320C// ""
0x590a8  newobj   instance void Microsoft.Crm.BusinessEntities.RetrieveMultipleReturningNullEntityCollectionException::.ctor(string hint)
0x590ad  throw
0x590ae  ldstr    aExtendedretrie_0// "[ExtendedRetrieveMultipleNullChecks] Do"...
0x590b3  ldc.i4.6
0x590b4  newarr   [mscorlib]System.Object
0x590b9  dup
0x590ba  ldc.i4.0
0x590bb  ldloc.3
0x590bc  callvirt instance class Microsoft.Crm.Query.FilterExpression Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x590c1  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Query.FilterExpression::get_EntityMetadata()
0x590c6  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x590cb  stelem.ref
0x590cc  dup
0x590cd  ldc.i4.1
0x590ce  ldloc.3
0x590cf  stelem.ref
0x590d0  dup
0x590d1  ldc.i4.2
0x590d2  ldarg.2
0x590d3  box      [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.DatabaseQueryTarget
0x590d8  stelem.ref
0x590d9  dup
0x590da  ldc.i4.3
0x590db  ldarg.3
0x590dc  stelem.ref
0x590dd  dup
0x590de  ldc.i4.4
0x590df  ldloc.2
0x590e0  box      [mscorlib]System.Boolean
0x590e5  stelem.ref
0x590e6  dup
0x590e7  ldc.i4.5
0x590e8  ldloc.1
0x590e9  box      [mscorlib]System.Boolean
0x590ee  stelem.ref
0x590ef  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::Error(class [mscorlib]System.Exception, string, object[])
0x590f4  leave.s  loc_5916B
0x590f6  ldnull
0x590f7  ldstr    aNotAnErrorExte_0// "Not An Error: [ExtendedRetrieveMultiple"...
0x590fc  ldc.i4.s 9
0x590fe  newarr   [mscorlib]System.Object
0x59103  dup
0x59104  ldc.i4.0
0x59105  ldloc.s  4
0x59107  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x5910c  box      [mscorlib]System.Int32
0x59111  stelem.ref
0x59112  dup
0x59113  ldc.i4.1
0x59114  ldloc.s  4
0x59116  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x5911b  ldc.i4.1
0x5911c  beq.s    loc_59125
0x5911e  ldstr    aS// "s"
0x59123  br.s     loc_5912A
0x59125  ldstr    asc_9320C// ""
0x5912a  stelem.ref
0x5912b  dup
0x5912c  ldc.i4.2
0x5912d  ldloc.3
0x5912e  callvirt instance class Microsoft.Crm.Query.FilterExpression Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x59133  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Query.FilterExpression::get_EntityMetadata()
0x59138  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x5913d  stelem.ref
0x5913e  dup
0x5913f  ldc.i4.3
0x59140  ldloc.s  4
0x59142  stelem.ref
0x59143  dup
0x59144  ldc.i4.4
0x59145  ldloc.3
0x59146  stelem.ref
0x59147  dup
0x59148  ldc.i4.5
0x59149  ldarg.2
0x5914a  box      [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Platform.DatabaseQueryTarget
0x5914f  stelem.ref
0x59150  dup
0x59151  ldc.i4.6
0x59152  ldarg.3
0x59153  stelem.ref
0x59154  dup
0x59155  ldc.i4.7
0x59156  ldloc.2
0x59157  box      [mscorlib]System.Boolean
0x5915c  stelem.ref
0x5915d  dup
0x5915e  ldc.i4.8
0x5915f  ldloc.1
0x59160  box      [mscorlib]System.Boolean
0x59165  stelem.ref
0x59166  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::Error(class [mscorlib]System.Exception, string, object[])
0x5916b  ldarg.0
0x5916c  ldfld    class PostRetrieveMultipleEventHandler Microsoft.Crm.BusinessEntities.BusinessProcessObject::PostRetrieveMultiple
0x59171  brfalse  loc_5920A
0x59176  ldloc.s  6
0x59178  brfalse.s loc_591AC
0x5917a  ldloc.s  4
0x5917c  brtrue.s loc_591AC
0x5917e  ldnull
0x5917f  ldstr    aWarningExtende// "Warning: [ExtendedRetrieveMultipleNullC"...
0x59184  ldc.i4.0
0x59185  newarr   [mscorlib]System.Object
0x5918a  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::Error(class [mscorlib]System.Exception, string, object[])
0x5918f  ldloc.3
0x59190  callvirt instance class Microsoft.Crm.Query.FilterExpression Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x59195  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Query.FilterExpression::get_EntityMetadata()
0x5919a  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x5919f  ldarg.3
0x591a0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x591a5  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::.ctor(string, valuetype [mscorlib]System.Guid)
0x591aa  stloc.s  4
0x591ac  ldarg.0
0x591ad  ldfld    class PostRetrieveMultipleEventHandler Microsoft.Crm.BusinessEntities.BusinessProcessObject::PostRetrieveMultiple
0x591b2  ldarg.0
0x591b3  ldloc.s  5
0x591b5  callvirt instance void PostRetrieveMultipleEventHandler::Invoke(object sender, class Microsoft.Crm.BusinessEntities.ExtensionEventArgs e)
0x591ba  ldloc.s  6
0x591bc  brfalse.s loc_59201
0x591be  ldnull
0x591bf  ldstr    aNotAnErrorExte_1// "Not An Error: [ExtendedRetrieveMultiple"...
0x591c4  ldc.i4.2
0x591c5  newarr   [mscorlib]System.Object
0x591ca  dup
0x591cb  ldc.i4.0
0x591cc  ldloc.3
0x591cd  callvirt instance class Microsoft.Crm.Query.FilterExpression Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x591d2  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Query.FilterExpression::get_EntityMetadata()
0x591d7  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x591dc  stelem.ref
0x591dd  dup
0x591de  ldc.i4.1
0x591df  ldloc.s  5
0x591e1  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Entities()
0x591e6  brfalse.s loc_591F6
0x591e8  ldloc.s  5
0x591ea  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Entities()
0x591ef  callvirt instance string [mscorlib]System.Object::ToString()
0x591f4  br.s     loc_591FB
0x591f6  ldstr    aNull_2// "null"
0x591fb  stelem.ref
0x591fc  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::Error(class [mscorlib]System.Exception, string, object[])
0x59201  ldloc.s  5
0x59203  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.BusinessEntities.ExtensionEventArgs::get_Entities()
0x59208  stloc.s  4
0x5920a  ldloc.s  4
0x5920c  brtrue.s loc_5925C
0x5920e  ldstr    asc_9320C// ""
0x59213  newobj   instance void Microsoft.Crm.BusinessEntities.RetrieveMultipleReturningNullEntityCollectionException::.ctor(string hint)
0x59218  throw
0x59219  ldstr    aExtendedretrie_1// "[ExtendedRetrieveMultipleNullChecks] Re"...
0x5921e  ldc.i4.1
0x5921f  newarr   [mscorlib]System.Object
0x59224  dup
0x59225  ldc.i4.0
0x59226  ldloc.3
0x59227  callvirt instance class Microsoft.Crm.Query.FilterExpression Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x5922c  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Query.FilterExpression::get_EntityMetadata()
0x59231  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x59236  stelem.ref
0x59237  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::Error(class [mscorlib]System.Exception, string, object[])
0x5923c  leave.s  loc_5925C
0x5923e  ldloc.3
0x5923f  callvirt instance class Microsoft.Crm.Query.FilterExpression Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x59244  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata Microsoft.Crm.Query.FilterExpression::get_EntityMetadata()
0x59249  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PlatformName()
0x5924e  ldarg.3
0x5924f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x59254  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::.ctor(string, valuetype [mscorlib]System.Guid)
0x59259  stloc.s  4
0x5925b  endfinally
0x5925c  ldloc.s  4
0x5925e  ret
```
