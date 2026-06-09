# Microsoft.Crm.WebServices.TranslationImportExportService::CreateImportTranslationsAsyncJob

- ea: `0xf0d0`
- end: `0xf16e`
- name: `Microsoft.Crm.WebServices.TranslationImportExportService::CreateImportTranslationsAsyncJob`
- size: `158`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xf0a0`

## callees

- `0xf0d0`

## pseudocode

```c

```

## disassembly

```asm
0xf0d0  ldstr    aFieldTranslati// "Field Translations Import Job"
0xf0d5  stloc.0
0xf0d6  ldarg.2
0xf0d7  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_PluginContext()
0xf0dc  brfalse.s loc_F127
0xf0de  ldarg.2
0xf0df  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_PluginContext()
0xf0e4  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_InputParameters()
0xf0e9  ldstr    aImportfieldtra// "ImportFieldTranslationFile"
0xf0ee  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::ContainsKey(var<u1>)
0xf0f3  brfalse.s loc_F127
0xf0f5  ldarg.2
0xf0f6  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_PluginContext()
0xf0fb  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_InputParameters()
0xf100  ldstr    aImportfieldtra// "ImportFieldTranslationFile"
0xf105  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0xf10a  brfalse.s loc_F127
0xf10c  ldarg.2
0xf10d  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IPluginExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_PluginContext()
0xf112  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IExecutionContext::get_InputParameters()
0xf117  ldstr    aImportfieldtra// "ImportFieldTranslationFile"
0xf11c  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0xf121  callvirt instance string [mscorlib]System.Object::ToString()
0xf126  stloc.0
0xf127  ldc.i4.s 0x3B
0xf129  ldarg.1
0xf12a  ldnull
0xf12b  ldnull
0xf12c  ldnull
0xf12d  ldnull
0xf12e  ldloca.s 2
0xf130  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0xf136  ldloc.2
0xf137  ldloc.0
0xf138  ldarg.2
0xf139  callvirt instance class [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.CorrelationToken [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_CorrelationToken()
0xf13e  ldnull
0xf13f  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AsyncRequest::.ctor(int32, string, string, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.EntityNameReference, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>, string, class [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.CorrelationToken, string)
0xf144  stloc.1
0xf145  ldarg.2
0xf146  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0xf14b  ldc.i4.s 0x14
0xf14d  ldstr    aSubmittingImpo// "Submitting Import Translations job: {0}"
0xf152  ldc.i4.1
0xf153  newarr   [mscorlib]System.Object
0xf158  dup
0xf159  ldc.i4.0
0xf15a  ldloc.0
0xf15b  stelem.ref
0xf15c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xf161  ldloc.1
0xf162  ldarg.2
0xf163  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AsyncQueue::Enqueue(class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.AsyncRequest, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0xf168  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0xf16d  ret
```
