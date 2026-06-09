# Microsoft.Crm.ServiceBus.WebhookClient::GetUriWithQueryParams_0

- ea: `0x6100`
- end: `0x61b3`
- name: `Microsoft.Crm.ServiceBus.WebhookClient::GetUriWithQueryParams_0`
- size: `179`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x60b0`
- `0x6c10`

## callees

- `0x6100`
- `0x6330`

## string_xrefs

- `0x6179`: `Received exception when adding custom query params to Url: for OrgId:{0}, serviceEndpointId: {1}, name: {2}, exception:{3}`

## pseudocode

```c

```

## disassembly

```asm
0x6100  ldarg.1
0x6101  newobj   instance void [System]System.UriBuilder::.ctor(string)
0x6106  stloc.0
0x6107  ldarg.s  5
0x6109  brfalse.s loc_616C
0x610b  ldarg.s  5
0x610d  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Count()
0x6112  ldc.i4.0
0x6113  ble.s    loc_616C
0x6115  ldloc.0
0x6116  callvirt instance string [System]System.UriBuilder::get_Query()
0x611b  call     class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpUtility::ParseQueryString(string)
0x6120  stloc.1
0x6121  ldarg.s  5
0x6123  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::GetEnumerator()
0x6128  stloc.2
0x6129  br.s     loc_6147
0x612b  ldloca.s 2
0x612d  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, string>::get_Current()
0x6132  stloc.3
0x6133  ldloc.1
0x6134  ldloca.s 3
0x6136  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Key()
0x613b  ldloca.s 3
0x613d  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Value()
0x6142  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::set_Item(string, string)
0x6147  ldloca.s 2
0x6149  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, string>::MoveNext()
0x614e  brtrue.s loc_612B
0x6150  leave.s  loc_6160
0x6152  ldloca.s 2
0x6154  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, string>
0x615a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x615f  endfinally
0x6160  ldloc.0
0x6161  ldloc.1
0x6162  callvirt instance string [mscorlib]System.Object::ToString()
0x6167  callvirt instance void [System]System.UriBuilder::set_Query(string)
0x616c  ldloc.0
0x616d  callvirt instance class [System]System.Uri [System]System.UriBuilder::get_Uri()
0x6172  stloc.s  4
0x6174  leave.s  loc_61B0
0x6176  stloc.s  5
0x6178  ldarg.0
0x6179  ldstr    aReceivedExcept_0// "Received exception when adding custom q"...
0x617e  ldc.i4.4
0x617f  newarr   [mscorlib]System.Object
0x6184  dup
0x6185  ldc.i4.0
0x6186  ldarg.2
0x6187  box      [mscorlib]System.Guid
0x618c  stelem.ref
0x618d  dup
0x618e  ldc.i4.1
0x618f  ldarg.3
0x6190  stelem.ref
0x6191  dup
0x6192  ldc.i4.2
0x6193  ldarg.s  4
0x6195  stelem.ref
0x6196  dup
0x6197  ldc.i4.3
0x6198  ldloc.s  5
0x619a  callvirt instance string [mscorlib]System.Object::ToString()
0x619f  stelem.ref
0x61a0  call     string [mscorlib]System.String::Format(string, object[])
0x61a5  ldc.i4   0x80050204
0x61aa  call     instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmException Microsoft.Crm.ServiceBus.WebhookClient::GetCrmExceptionWithInnerException(string message, int32 errorCode)
0x61af  throw
0x61b0  ldloc.s  4
0x61b2  ret
```
