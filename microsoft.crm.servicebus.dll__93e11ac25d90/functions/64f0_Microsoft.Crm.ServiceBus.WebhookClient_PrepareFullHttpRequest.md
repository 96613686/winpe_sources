# Microsoft.Crm.ServiceBus.WebhookClient::PrepareFullHttpRequest

- ea: `0x64f0`
- end: `0x658b`
- name: `Microsoft.Crm.ServiceBus.WebhookClient::PrepareFullHttpRequest`
- size: `155`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x68c0`

## callees

- `0x5e50`
- `0x64f0`

## string_xrefs

- `0x650d`: `application/json`

## pseudocode

```c

```

## disassembly

```asm
0x64f0  ldarg.1
0x64f1  callvirt instance class [System]System.Uri [System]System.Net.WebRequest::get_RequestUri()
0x64f6  call     class [System]System.Net.WebRequest [System]System.Net.WebRequest::Create(class [System]System.Uri)
0x64fb  castclass [System]System.Net.HttpWebRequest
0x6500  stloc.0
0x6501  ldloc.0
0x6502  ldstr    aPost// "POST"
0x6507  callvirt instance void [System]System.Net.WebRequest::set_Method(string)
0x650c  ldloc.0
0x650d  ldstr    aApplicationJso// "application/json"
0x6512  callvirt instance void [System]System.Net.WebRequest::set_ContentType(string)
0x6517  ldloc.0
0x6518  ldc.i4.1
0x6519  callvirt instance void [System]System.Net.HttpWebRequest::set_KeepAlive(bool)
0x651e  ldloc.0
0x651f  ldc.i4.1
0x6520  callvirt instance void [System]System.Net.HttpWebRequest::set_Pipelined(bool)
0x6525  ldloc.0
0x6526  ldarg.2
0x6527  callvirt instance int32 Microsoft.Crm.ServiceBus.WebhookHttpRequestConfig::get_HttpRequestTimeoutInMilliSeconds()
0x652c  callvirt instance void [System]System.Net.WebRequest::set_Timeout(int32)
0x6531  ldloc.0
0x6532  callvirt instance class [mscorlib]System.IO.Stream [System]System.Net.WebRequest::GetRequestStream()
0x6537  newobj   instance void [mscorlib]System.IO.StreamWriter::.ctor(class [mscorlib]System.IO.Stream)
0x653c  stloc.1
0x653d  ldloc.1
0x653e  ldarg.3
0x653f  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x6544  leave.s  loc_6550
0x6546  ldloc.1
0x6547  brfalse.s loc_654F
0x6549  ldloc.1
0x654a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x654f  endfinally
0x6550  ldarg.1
0x6551  callvirt instance class [System]System.Net.WebHeaderCollection [System]System.Net.WebRequest::get_Headers()
0x6556  callvirt instance string[] [System]System.Collections.Specialized.NameValueCollection::get_AllKeys()
0x655b  stloc.2
0x655c  ldc.i4.0
0x655d  stloc.3
0x655e  br.s     loc_6583
0x6560  ldloc.2
0x6561  ldloc.3
0x6562  ldelem.ref
0x6563  stloc.s  4
0x6565  ldloc.0
0x6566  callvirt instance class [System]System.Net.WebHeaderCollection [System]System.Net.WebRequest::get_Headers()
0x656b  ldloc.s  4
0x656d  ldarg.1
0x656e  callvirt instance class [System]System.Net.WebHeaderCollection [System]System.Net.WebRequest::get_Headers()
0x6573  ldloc.s  4
0x6575  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x657a  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Add(string, string)
0x657f  ldloc.3
0x6580  ldc.i4.1
0x6581  add
0x6582  stloc.3
0x6583  ldloc.3
0x6584  ldloc.2
0x6585  ldlen
0x6586  conv.i4
0x6587  blt.s    loc_6560
0x6589  ldloc.0
0x658a  ret
```
