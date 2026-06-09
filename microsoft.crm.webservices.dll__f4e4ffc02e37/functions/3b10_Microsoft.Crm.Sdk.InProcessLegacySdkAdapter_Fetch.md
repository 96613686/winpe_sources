# Microsoft.Crm.Sdk.InProcessLegacySdkAdapter::Fetch

- ea: `0x3b10`
- end: `0x3b5f`
- name: `Microsoft.Crm.Sdk.InProcessLegacySdkAdapter::Fetch`
- size: `79`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x3cd0`
- `0x45e0`
- `0x62b0`
- `0x8150`
- `0xa9c0`

## string_xrefs

- `0x3b11`: `fetchXml`
- `0x3b4f`: `FetchXmlResult`
- `0x3b33`: `FetchXml`

## pseudocode

```c

```

## disassembly

```asm
0x3b10  ldarg.1
0x3b11  ldstr    aFetchxml// "fetchXml"
0x3b16  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x3b1b  ldstr    aExecutefetch// "ExecuteFetch"
0x3b20  ldc.i4.0
0x3b21  ldarg.0
0x3b22  call     instance valuetype [mscorlib]System.Guid Microsoft.Crm.Sdk.LegacySdkAdapterBase::get_OrganizationId()
0x3b27  newobj   instance void Microsoft.Crm.Sdk.Crm2007.Request::.ctor(string requestName, bool returnDynamicEntities, valuetype [mscorlib]System.Guid organizationId)
0x3b2c  stloc.0
0x3b2d  ldloc.0
0x3b2e  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PropertyBag Microsoft.Crm.Sdk.RequestBase::get_InputParameters()
0x3b33  ldstr    aFetchxml_0// "FetchXml"
0x3b38  ldarg.1
0x3b39  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PropertyBag::set_Item(string, object)
0x3b3e  ldarg.0
0x3b3f  ldloc.0
0x3b40  call     instance object Microsoft.Crm.Sdk.InProcessLegacySdkAdapter::Execute(object request)
0x3b45  castclass Microsoft.Crm.Sdk.Crm2007.Response
0x3b4a  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PropertyBag Microsoft.Crm.Sdk.ResponseBase::get_OutPuts()
0x3b4f  ldstr    aFetchxmlresult// "FetchXmlResult"
0x3b54  callvirt instance object [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PropertyBag::get_Item(string)
0x3b59  isinst   [mscorlib]System.String
0x3b5e  ret
```
