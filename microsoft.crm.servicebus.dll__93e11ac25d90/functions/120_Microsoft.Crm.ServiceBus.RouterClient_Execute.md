# Microsoft.Crm.ServiceBus.RouterClient::Execute

- ea: `0x120`
- end: `0x17a`
- name: `Microsoft.Crm.ServiceBus.RouterClient::Execute`
- size: `90`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x120`
- `0x180`
- `0x460`
- `0x4c0`

## string_xrefs

- `0x145`: `Retrying for communication exception: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x120  ldarg.0
0x121  ldarg.1
0x122  ldarg.2
0x123  call     instance string Microsoft.Crm.ServiceBus.RouterClient::ExecuteInternal(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext context, class Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation endpointInfo)
0x128  stloc.0
0x129  leave.s  loc_178
0x12b  stloc.1
0x12c  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x131  ldc.i4.s 0x2F
0x133  ldstr    a0// "{0}"
0x138  ldc.i4.1
0x139  newarr   [mscorlib]System.Object
0x13e  dup
0x13f  ldc.i4.0
0x140  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x145  ldstr    aRetryingForCom// "Retrying for communication exception: {"...
0x14a  ldc.i4.1
0x14b  newarr   [mscorlib]System.Object
0x150  dup
0x151  ldc.i4.0
0x152  ldloc.1
0x153  stelem.ref
0x154  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x159  stelem.ref
0x15a  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x15f  call     class Microsoft.Crm.ServiceBus.IRouterClientManager Microsoft.Crm.ServiceBus.RouterClientManager::get_Current()
0x164  callvirt instance class Microsoft.Crm.ServiceBus.IRouterClient Microsoft.Crm.ServiceBus.IRouterClientManager::RetrieveReadyClient()
0x169  castclass Microsoft.Crm.ServiceBus.RouterClient
0x16e  ldarg.1
0x16f  ldarg.2
0x170  callvirt instance string Microsoft.Crm.ServiceBus.RouterClient::ExecuteInternal(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.RemoteExecutionContext context, class Microsoft.Crm.ServiceBus.ServiceBusEndpointInformation endpointInfo)
0x175  stloc.0
0x176  leave.s  loc_178
0x178  ldloc.0
0x179  ret
```
