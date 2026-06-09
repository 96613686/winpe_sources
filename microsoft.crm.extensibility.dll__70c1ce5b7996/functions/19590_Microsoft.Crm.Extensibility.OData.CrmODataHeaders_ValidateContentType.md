# Microsoft.Crm.Extensibility.OData.CrmODataHeaders::ValidateContentType

- ea: `0x19590`
- end: `0x19654`
- name: `Microsoft.Crm.Extensibility.OData.CrmODataHeaders::ValidateContentType`
- size: `196`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18ee0`

## callees

- `0x19590`
- `0x19cc0`

## string_xrefs

- `0x1962f`: `{0} request requires Content-Type application/json.`

## pseudocode

```c

```

## disassembly

```asm
0x19590  ldarg.0
0x19591  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage Microsoft.Crm.Extensibility.OData.CrmODataHeaders::get_Request()
0x19596  callvirt instance class [System.Net.Http]System.Net.Http.HttpMethod [System.Net.Http]System.Net.Http.HttpRequestMessage::get_Method()
0x1959b  call     class [System.Net.Http]System.Net.Http.HttpMethod [System.Net.Http]System.Net.Http.HttpMethod::get_Post()
0x195a0  callvirt instance bool [System.Net.Http]System.Net.Http.HttpMethod::Equals(class [System.Net.Http]System.Net.Http.HttpMethod)
0x195a5  brfalse  loc_19653
0x195aa  ldnull
0x195ab  stloc.0
0x195ac  ldarg.0
0x195ad  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage Microsoft.Crm.Extensibility.OData.CrmODataHeaders::get_Request()
0x195b2  callvirt instance class [System.Net.Http]System.Net.Http.HttpContent [System.Net.Http]System.Net.Http.HttpRequestMessage::get_Content()
0x195b7  brfalse.s loc_195FD
0x195b9  ldarg.0
0x195ba  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage Microsoft.Crm.Extensibility.OData.CrmODataHeaders::get_Request()
0x195bf  callvirt instance class [System.Net.Http]System.Net.Http.HttpContent [System.Net.Http]System.Net.Http.HttpRequestMessage::get_Content()
0x195c4  callvirt instance class [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders [System.Net.Http]System.Net.Http.HttpContent::get_Headers()
0x195c9  brfalse.s loc_195FD
0x195cb  ldarg.0
0x195cc  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage Microsoft.Crm.Extensibility.OData.CrmODataHeaders::get_Request()
0x195d1  callvirt instance class [System.Net.Http]System.Net.Http.HttpContent [System.Net.Http]System.Net.Http.HttpRequestMessage::get_Content()
0x195d6  callvirt instance class [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders [System.Net.Http]System.Net.Http.HttpContent::get_Headers()
0x195db  callvirt instance class [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders::get_ContentType()
0x195e0  brfalse.s loc_195FD
0x195e2  ldarg.0
0x195e3  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage Microsoft.Crm.Extensibility.OData.CrmODataHeaders::get_Request()
0x195e8  callvirt instance class [System.Net.Http]System.Net.Http.HttpContent [System.Net.Http]System.Net.Http.HttpRequestMessage::get_Content()
0x195ed  callvirt instance class [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders [System.Net.Http]System.Net.Http.HttpContent::get_Headers()
0x195f2  callvirt instance class [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders::get_ContentType()
0x195f7  callvirt instance string [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue::get_MediaType()
0x195fc  stloc.0
0x195fd  ldloc.0
0x195fe  brtrue.s loc_19601
0x19600  ret
0x19601  ldc.i4.0
0x19602  stloc.1
0x19603  ldsfld   string[] Microsoft.Crm.Extensibility.OData.CrmODataHeaders::WhitelistContentTypes
0x19608  stloc.2
0x19609  ldc.i4.0
0x1960a  stloc.3
0x1960b  br.s     loc_19621
0x1960d  ldloc.2
0x1960e  ldloc.3
0x1960f  ldelem.ref
0x19610  ldloc.0
0x19611  ldc.i4.5
0x19612  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x19617  brfalse.s loc_1961D
0x19619  ldc.i4.1
0x1961a  stloc.1
0x1961b  br.s     loc_19627
0x1961d  ldloc.3
0x1961e  ldc.i4.1
0x1961f  add
0x19620  stloc.3
0x19621  ldloc.3
0x19622  ldloc.2
0x19623  ldlen
0x19624  conv.i4
0x19625  blt.s    loc_1960D
0x19627  ldloc.1
0x19628  brtrue.s loc_19653
0x1962a  ldc.i4   0x19F
0x1962f  ldstr    a0RequestRequir// "{0} request requires Content-Type appli"...
0x19634  ldc.i4.1
0x19635  newarr   [mscorlib]System.Object
0x1963a  dup
0x1963b  ldc.i4.0
0x1963c  ldarg.0
0x1963d  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage Microsoft.Crm.Extensibility.OData.CrmODataHeaders::get_Request()
0x19642  callvirt instance class [System.Net.Http]System.Net.Http.HttpMethod [System.Net.Http]System.Net.Http.HttpRequestMessage::get_Method()
0x19647  callvirt instance string [System.Net.Http]System.Net.Http.HttpMethod::get_Method()
0x1964c  stelem.ref
0x1964d  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmHttpException::.ctor(valuetype [System]System.Net.HttpStatusCode, string, object[])
0x19652  throw
0x19653  ret
```
