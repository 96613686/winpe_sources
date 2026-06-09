# Microsoft.Crm.Extensibility.ODataV4.Routing.CrmODataRoutingConvention::ValidateMetadataRequest

- ea: `0x2de50`
- end: `0x2df4b`
- name: `Microsoft.Crm.Extensibility.ODataV4.Routing.CrmODataRoutingConvention::ValidateMetadataRequest`
- size: `251`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x2dbe0`

## callees

- `0x2de50`

## string_xrefs

- `0x2de5b`: `application/atom+xml`
- `0x2de91`: `application/xml`
- `0x2deff`: `application/xml`

## pseudocode

```c

```

## disassembly

```asm
0x2de50  ldarg.1
0x2de51  callvirt instance class [System.Net.Http]System.Net.Http.HttpContent [System.Net.Http]System.Net.Http.HttpRequestMessage::get_Content()
0x2de56  callvirt instance class [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders [System.Net.Http]System.Net.Http.HttpContent::get_Headers()
0x2de5b  ldstr    aApplicationAto// "application/atom+xml"
0x2de60  call     class [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue::Parse(string)
0x2de65  callvirt instance void [System.Net.Http]System.Net.Http.Headers.HttpContentHeaders::set_ContentType(class [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue)
0x2de6a  ldarg.1
0x2de6b  callvirt instance class [System.Net.Http]System.Net.Http.Headers.HttpRequestHeaders [System.Net.Http]System.Net.Http.HttpRequestMessage::get_Headers()
0x2de70  callvirt instance class [System.Net.Http]System.Net.Http.Headers.HttpHeaderValueCollection`1<class [System.Net.Http]System.Net.Http.Headers.MediaTypeWithQualityHeaderValue> [System.Net.Http]System.Net.Http.Headers.HttpRequestHeaders::get_Accept()
0x2de75  callvirt instance string [mscorlib]System.Object::ToString()
0x2de7a  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2de7f  brtrue.s loc_2DECF
0x2de81  ldarg.1
0x2de82  callvirt instance class [System.Net.Http]System.Net.Http.Headers.HttpRequestHeaders [System.Net.Http]System.Net.Http.HttpRequestMessage::get_Headers()
0x2de87  callvirt instance class [System.Net.Http]System.Net.Http.Headers.HttpHeaderValueCollection`1<class [System.Net.Http]System.Net.Http.Headers.MediaTypeWithQualityHeaderValue> [System.Net.Http]System.Net.Http.Headers.HttpRequestHeaders::get_Accept()
0x2de8c  callvirt instance string [mscorlib]System.Object::ToString()
0x2de91  ldstr    aApplicationXml// "application/xml"
0x2de96  callvirt instance bool [mscorlib]System.String::Contains(string)
0x2de9b  brtrue.s loc_2DECF
0x2de9d  ldarg.1
0x2de9e  callvirt instance class [System.Net.Http]System.Net.Http.Headers.HttpRequestHeaders [System.Net.Http]System.Net.Http.HttpRequestMessage::get_Headers()
0x2dea3  callvirt instance class [System.Net.Http]System.Net.Http.Headers.HttpHeaderValueCollection`1<class [System.Net.Http]System.Net.Http.Headers.MediaTypeWithQualityHeaderValue> [System.Net.Http]System.Net.Http.Headers.HttpRequestHeaders::get_Accept()
0x2dea8  callvirt instance string [mscorlib]System.Object::ToString()
0x2dead  ldstr    asc_464B2// "*/*"
0x2deb2  callvirt instance bool [mscorlib]System.String::Contains(string)
0x2deb7  brtrue.s loc_2DECF
0x2deb9  ldc.i4   0x19F
0x2debe  ldstr    aASupportedMime// "A supported MIME type could not be foun"...
0x2dec3  ldc.i4.0
0x2dec4  newarr   [mscorlib]System.Object
0x2dec9  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmHttpException::.ctor(valuetype [System]System.Net.HttpStatusCode, string, object[])
0x2dece  throw
0x2decf  ldarg.1
0x2ded0  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>> [System.Web.Http]System.Net.Http.HttpRequestMessageExtensions::GetQueryNameValuePairs(class [System.Net.Http]System.Net.Http.HttpRequestMessage)
0x2ded5  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>>::GetEnumerator()
0x2deda  stloc.0
0x2dedb  br.s     loc_2DF36
0x2dedd  ldloc.0
0x2dede  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>>::get_Current()
0x2dee3  stloc.1
0x2dee4  ldloca.s 1
0x2dee6  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Key()
0x2deeb  ldstr    aFormat// "$format"
0x2def0  ldc.i4.4
0x2def1  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x2def6  brfalse.s loc_2DF36
0x2def8  ldloca.s 1
0x2defa  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Value()
0x2deff  ldstr    aApplicationXml// "application/xml"
0x2df04  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2df09  brtrue.s loc_2DF1E
0x2df0b  ldloca.s 1
0x2df0d  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, string>::get_Value()
0x2df12  ldstr    asc_464B2// "*/*"
0x2df17  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2df1c  brfalse.s loc_2DF20
0x2df1e  leave.s  loc_2DF4A
0x2df20  ldc.i4   0x19F
0x2df25  ldstr    aASupportedMime// "A supported MIME type could not be foun"...
0x2df2a  ldc.i4.0
0x2df2b  newarr   [mscorlib]System.Object
0x2df30  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmHttpException::.ctor(valuetype [System]System.Net.HttpStatusCode, string, object[])
0x2df35  throw
0x2df36  ldloc.0
0x2df37  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2df3c  brtrue.s loc_2DEDD
0x2df3e  leave.s  loc_2DF4A
0x2df40  ldloc.0
0x2df41  brfalse.s loc_2DF49
0x2df43  ldloc.0
0x2df44  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2df49  endfinally
0x2df4a  ret
```
