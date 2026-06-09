# Microsoft.Crm.ServiceBus.WebhookClient::GetUriWithQueryParams

- ea: `0x60b0`
- end: `0x6100`
- name: `Microsoft.Crm.ServiceBus.WebhookClient::GetUriWithQueryParams`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x6c10`

## callees

- `0x60b0`
- `0x6100`
- `0x61c0`
- `0x6330`

## string_xrefs

- `0x60bd`: `Received exception when extracing keyValue pairs for custom query params  for OrgId:{0}, serviceEndpointId: {1}, name: {2}, exception:{3}`

## pseudocode

```c

```

## disassembly

```asm
0x60b0  ldarg.0
0x60b1  ldarg.s  5
0x60b3  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Crm.ServiceBus.WebhookClient::ExtractKeyValuePairs(string inputXml)
0x60b8  stloc.0
0x60b9  leave.s  loc_60F3
0x60bb  stloc.1
0x60bc  ldarg.0
0x60bd  ldstr    aReceivedExcept// "Received exception when extracing keyVa"...
0x60c2  ldc.i4.4
0x60c3  newarr   [mscorlib]System.Object
0x60c8  dup
0x60c9  ldc.i4.0
0x60ca  ldarg.2
0x60cb  box      [mscorlib]System.Guid
0x60d0  stelem.ref
0x60d1  dup
0x60d2  ldc.i4.1
0x60d3  ldarg.3
0x60d4  stelem.ref
0x60d5  dup
0x60d6  ldc.i4.2
0x60d7  ldarg.s  4
0x60d9  stelem.ref
0x60da  dup
0x60db  ldc.i4.3
0x60dc  ldloc.1
0x60dd  callvirt instance string [mscorlib]System.Object::ToString()
0x60e2  stelem.ref
0x60e3  call     string [mscorlib]System.String::Format(string, object[])
0x60e8  ldc.i4   0x80050204
0x60ed  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmException Microsoft.Crm.ServiceBus.WebhookClient::GetCrmExceptionWithInnerException(string message, int32 errorCode)
0x60f2  throw
0x60f3  ldarg.0
0x60f4  ldarg.1
0x60f5  ldarg.2
0x60f6  ldarg.3
0x60f7  ldarg.s  4
0x60f9  ldloc.0
0x60fa  call     instance class [System]System.Uri Microsoft.Crm.ServiceBus.WebhookClient::GetUriWithQueryParams(string url, valuetype [mscorlib]System.Guid organizationId, string serviceEndpointId, string serviceEndpointName, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> queryParams)
0x60ff  ret
```
