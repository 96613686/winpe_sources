# Microsoft.Crm.Sdk.CrmServiceInternal::Fetch

- ea: `0x920`
- end: `0x987`
- name: `Microsoft.Crm.Sdk.CrmServiceInternal::Fetch`
- size: `103`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xaab0`

## callees

- `0x990`
- `0xb70`
- `0x4a80`
- `0x4b80`

## string_xrefs

- `0x941`: `fetchXml`
- `0x977`: `FetchXmlResult`

## pseudocode

```c

```

## disassembly

```asm
0x920  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::GetOrganizationGuid()
0x925  stloc.0
0x926  ldstr    aExecutefetchre// "ExecuteFetchRequest"
0x92b  ldarg.1
0x92c  ldloc.0
0x92d  call     class Microsoft.Crm.Sdk.IRequestBuilder Microsoft.Crm.Sdk.RequestBuilderFactory::Create(string requestName, string targetNamespace, valuetype [mscorlib]System.Guid organizationId)
0x932  stloc.1
0x933  ldarg.0
0x934  ldloc.1
0x935  call     instance void Microsoft.Crm.Sdk.CrmServiceInternal::ThrowIfMessageNotSupported(class Microsoft.Crm.Sdk.IRequestBuilder requestBuilder)
0x93a  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection::.ctor()
0x93f  stloc.2
0x940  ldloc.2
0x941  ldstr    aFetchxml// "fetchXml"
0x946  ldarg.2
0x947  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x94c  ldloc.2
0x94d  ldstr    aOptionalparame// "OptionalParameters"
0x952  ldc.i4.0
0x953  newarr   [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.OptionalParameter
0x958  callvirt instance void class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::set_Item(var<u1>, !!T0)
0x95d  ldarg.0
0x95e  ldstr    aExecute// "Execute"
0x963  ldloc.1
0x964  callvirt instance string Microsoft.Crm.Sdk.IRequestBuilder::get_RequestName()
0x969  ldc.i4.0
0x96a  ldloc.2
0x96b  ldarg.3
0x96c  ldarg.s  4
0x96e  ldarg.s  5
0x970  ldarg.s  6
0x972  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection Microsoft.Crm.Sdk.CrmServiceInternal::ExecuteRequest(string messageName, string requestName, int32 primaryObjectTypeCode, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.ParameterCollection fields, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CorrelationToken correlationToken, class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CallerOriginToken originToken, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.UserAuth userAuth, valuetype [mscorlib]System.Guid callerId)
0x977  ldstr    aFetchxmlresult// "FetchXmlResult"
0x97c  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x981  castclass [mscorlib]System.String
0x986  ret
```
