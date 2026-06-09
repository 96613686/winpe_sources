# Microsoft.Crm.ObjectModel.TraceLogService::Create

- ea: `0x1b94f0`
- end: `0x1b9761`
- name: `Microsoft.Crm.ObjectModel.TraceLogService::Create`
- size: `625`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1b94f0`
- `0x1b9770`
- `0x1b9970`
- `0x1b99d0`
- `0x1b9a70`
- `0x1b9cd0`
- `0x1cbaf0`
- `0x1cbd80`

## string_xrefs

- `0x1b967a`: `Create`
- `0x1b951b`: `traceparameterxml`
- `0x1b9529`: `traceparameterxml`
- `0x1b9506`: `CreateTrace`
- `0x1b95fd`: `CreateIfNotExists`
- `0x1b969f`: `CreateTraceAssociation`

## pseudocode

```c

```

## disassembly

```asm
0x1b94f0  ldarg.1
0x1b94f1  ldstr    aEntity_0// "entity"
0x1b94f6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1b94fb  ldarg.2
0x1b94fc  ldstr    aContext// "context"
0x1b9501  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x1b9506  ldstr    aCreatetrace// "CreateTrace"
0x1b950b  ldc.i4.0
0x1b950c  call     class [Microsoft.Crm.Core]Microsoft.Crm.CounterList [Microsoft.Crm.Core]Microsoft.Crm.CounterList::CreateAndStart(string, bool)
0x1b9511  stloc.0
0x1b9512  ldnull
0x1b9513  stloc.1
0x1b9514  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x1b9519  stloc.2
0x1b951a  ldarg.1
0x1b951b  ldstr    aTraceparameter// "traceparameterxml"
0x1b9520  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x1b9525  brtrue.s loc_1B9583
0x1b9527  ldarg.0
0x1b9528  ldarg.1
0x1b9529  ldstr    aTraceparameter// "traceparameterxml"
0x1b952e  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x1b9533  castclass [mscorlib]System.String
0x1b9538  ldc.i4.1
0x1b9539  call     instance class [Microsoft.Crm]Microsoft.Crm.TraceParameterSet Microsoft.Crm.ObjectModel.TraceLogService::DeserializeTraceParameters(string traceParameterXml, bool forCreateTrace)
0x1b953e  stloc.1
0x1b953f  ldloc.1
0x1b9540  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm]Microsoft.Crm.TraceParameter> [Microsoft.Crm]Microsoft.Crm.TraceParameterSet::get_Parameters()
0x1b9545  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm]Microsoft.Crm.TraceParameter>::GetEnumerator()
0x1b954a  stloc.s  5
0x1b954c  br.s     loc_1B956C
0x1b954e  ldloc.s  5
0x1b9550  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm]Microsoft.Crm.TraceParameter>::get_Current()
0x1b9555  stloc.s  6
0x1b9557  ldarg.0
0x1b9558  ldloc.s  6
0x1b955a  call     instance void Microsoft.Crm.ObjectModel.TraceLogService::ValidateTraceParameterData(class [Microsoft.Crm]Microsoft.Crm.TraceParameter parameter)
0x1b955f  ldloc.2
0x1b9560  ldloc.s  6
0x1b9562  callvirt instance string [Microsoft.Crm]Microsoft.Crm.TraceParameter::get_Value()
0x1b9567  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1b956c  ldloc.s  5
0x1b956e  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1b9573  brtrue.s loc_1B954E
0x1b9575  leave.s  loc_1B9583
0x1b9577  ldloc.s  5
0x1b9579  brfalse.s loc_1B9582
0x1b957b  ldloc.s  5
0x1b957d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1b9582  endfinally
0x1b9583  ldarg.1
0x1b9584  ldstr    aTracecode// "tracecode"
0x1b9589  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x1b958e  brtrue.s loc_1B95FC
0x1b9590  ldarg.1
0x1b9591  ldstr    aLevel// "level"
0x1b9596  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x1b959b  brtrue.s loc_1B95FC
0x1b959d  ldarg.1
0x1b959e  ldstr    aCollationlevel// "collationlevel"
0x1b95a3  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x1b95a8  brtrue.s loc_1B95FC
0x1b95aa  ldarg.0
0x1b95ab  ldarg.1
0x1b95ac  ldstr    aTracecode// "tracecode"
0x1b95b1  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x1b95b6  unbox.any [mscorlib]System.Int32
0x1b95bb  ldarg.1
0x1b95bc  ldstr    aLevel// "level"
0x1b95c1  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x1b95c6  unbox.any [mscorlib]System.Int32
0x1b95cb  ldarg.1
0x1b95cc  ldstr    aCollationlevel// "collationlevel"
0x1b95d1  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x1b95d6  unbox.any [mscorlib]System.Int32
0x1b95db  ldloc.2
0x1b95dc  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<string>::ToArray()
0x1b95e1  ldarg.2
0x1b95e2  ldloca.s 3
0x1b95e4  call     instance bool Microsoft.Crm.ObjectModel.TraceLogService::TryGetLocalizedTraceMessage(int32 traceCode, int32 traceLevel, int32 collationLevel, string[] traceParameters, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, [out] string& traceMessage)
0x1b95e9  brtrue.s loc_1B95FC
0x1b95eb  ldc.i4   0x8004F900
0x1b95f0  ldc.i4.0
0x1b95f1  newarr   [mscorlib]System.Object
0x1b95f6  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(int32, object[])
0x1b95fb  throw
0x1b95fc  ldloc.0
0x1b95fd  ldstr    aCreateifnotexi// "CreateIfNotExists"
0x1b9602  ldc.i4.0
0x1b9603  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CounterList [Microsoft.Crm.Core]Microsoft.Crm.CounterList::InitStepListCounter(string, bool)
0x1b9608  stloc.s  7
0x1b960a  ldarg.1
0x1b960b  ldstr    aRegardingobjec_0// "regardingobjectid"
0x1b9610  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x1b9615  unbox.any [mscorlib]System.Guid
0x1b961a  ldarg.1
0x1b961b  ldstr    aRegardingobjec_1// "regardingobjecttypecode"
0x1b9620  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x1b9625  unbox.any [mscorlib]System.Int32
0x1b962a  stloc.s  8
0x1b962c  ldarg.2
0x1b962d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_MetadataCache()
0x1b9632  ldloc.s  8
0x1b9634  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0x1b9639  stloc.s  9
0x1b963b  ldloc.s  9
0x1b963d  ldarg.2
0x1b963e  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityAttributes Microsoft.Crm.ObjectModel.DenormalizedRegardingService::CheckReadAccess(valuetype [mscorlib]System.Guid regardingObjectId, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata regardingEntityMetadata, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1b9643  pop
0x1b9644  newobj   instance void Microsoft.Crm.ObjectModel.TraceRegardingService::.ctor()
0x1b9649  ldarg.1
0x1b964a  ldarg.2
0x1b964b  ldloc.s  7
0x1b964d  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker Microsoft.Crm.ObjectModel.DenormalizedRegardingService::Create(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity childEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, class [Microsoft.Crm.Core]Microsoft.Crm.CounterList listCounters)
0x1b9652  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0x1b9657  stloc.s  0xA
0x1b9659  ldarg.1
0x1b965a  ldstr    aTraceregarding// "traceregardingid"
0x1b965f  ldloc.s  0xA
0x1b9661  box      [mscorlib]System.Guid
0x1b9666  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::set_Item(string, object)
0x1b966b  leave.s  loc_1B9679
0x1b966d  ldloc.s  7
0x1b966f  brfalse.s loc_1B9678
0x1b9671  ldloc.s  7
0x1b9673  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1b9678  endfinally
0x1b9679  ldloc.0
0x1b967a  ldstr    aCreate// "Create"
0x1b967f  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Counter [Microsoft.Crm.Core]Microsoft.Crm.CounterList::InitStepCounter(string)
0x1b9684  stloc.s  0xB
0x1b9686  ldarg.0
0x1b9687  ldarg.1
0x1b9688  ldarg.2
0x1b9689  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Create(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1b968e  stloc.s  4
0x1b9690  leave.s  loc_1B969E
0x1b9692  ldloc.s  0xB
0x1b9694  brfalse.s loc_1B969D
0x1b9696  ldloc.s  0xB
0x1b9698  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1b969d  endfinally
0x1b969e  ldloc.0
0x1b969f  ldstr    aCreatetraceass// "CreateTraceAssociation"
0x1b96a4  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Counter [Microsoft.Crm.Core]Microsoft.Crm.CounterList::InitStepCounter(string)
0x1b96a9  stloc.s  0xB
0x1b96ab  ldloc.1
0x1b96ac  brfalse  loc_1B9740
0x1b96b1  ldarg.2
0x1b96b2  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_RootPluginContext()
0x1b96b7  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_SharedVariables()
0x1b96bc  ldstr    aTracelogduplic// "TraceLogDuplicateRecordFound"
0x1b96c1  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x1b96c6  brfalse.s loc_1B9740
0x1b96c8  ldarg.2
0x1b96c9  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_RootPluginContext()
0x1b96ce  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_SharedVariables()
0x1b96d3  ldstr    aTracelogduplic// "TraceLogDuplicateRecordFound"
0x1b96d8  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x1b96dd  unbox.any [mscorlib]System.Boolean
0x1b96e2  brtrue.s loc_1B9740
0x1b96e4  ldarg.2
0x1b96e5  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SystemUserContext::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x1b96ea  stloc.s  0xC
0x1b96ec  ldloc.1
0x1b96ed  callvirt instance class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm]Microsoft.Crm.TraceParameter> [Microsoft.Crm]Microsoft.Crm.TraceParameterSet::get_Parameters()
0x1b96f2  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm]Microsoft.Crm.TraceParameter>::GetEnumerator()
0x1b96f7  stloc.s  5
0x1b96f9  br.s     loc_1B971D
0x1b96fb  ldloc.s  5
0x1b96fd  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm]Microsoft.Crm.TraceParameter>::get_Current()
0x1b9702  stloc.s  0xD
0x1b9704  ldloc.s  0xD
0x1b9706  callvirt instance int32 [Microsoft.Crm]Microsoft.Crm.TraceParameter::get_ParameterType()
0x1b970b  brtrue.s loc_1B971D
0x1b970d  ldarg.0
0x1b970e  ldloc.s  0xD
0x1b9710  ldloc.s  4
0x1b9712  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0x1b9717  ldarg.2
0x1b9718  call     instance void Microsoft.Crm.ObjectModel.TraceLogService::CreateTraceAssociation(class [Microsoft.Crm]Microsoft.Crm.TraceParameter parameter, valuetype [mscorlib]System.Guid traceId, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x1b971d  ldloc.s  5
0x1b971f  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1b9724  brtrue.s loc_1B96FB
0x1b9726  leave.s  loc_1B974E
0x1b9728  ldloc.s  5
0x1b972a  brfalse.s loc_1B9733
0x1b972c  ldloc.s  5
0x1b972e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1b9733  endfinally
0x1b9734  ldloc.s  0xC
0x1b9736  brfalse.s loc_1B973F
0x1b9738  ldloc.s  0xC
0x1b973a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1b973f  endfinally
0x1b9740  leave.s  loc_1B974E
0x1b9742  ldloc.s  0xB
0x1b9744  brfalse.s loc_1B974D
0x1b9746  ldloc.s  0xB
0x1b9748  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1b974d  endfinally
0x1b974e  ldloc.s  4
0x1b9750  stloc.s  0xE
0x1b9752  leave.s  loc_1B975E
0x1b9754  ldloc.0
0x1b9755  brfalse.s loc_1B975D
0x1b9757  ldloc.0
0x1b9758  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1b975d  endfinally
0x1b975e  ldloc.s  0xE
0x1b9760  ret
```
