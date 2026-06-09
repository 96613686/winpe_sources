# Microsoft.Crm.Extensibility.OData.CrmODataHeaders::GetEmptyODataResponse

- ea: `0x18fd0`
- end: `0x19099`
- name: `Microsoft.Crm.Extensibility.OData.CrmODataHeaders::GetEmptyODataResponse`
- size: `201`
- prototype: ``
- caller_count: `18`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x10630`
- `0x10b80`
- `0x11a80`
- `0x11c90`
- `0x11eb0`
- `0x12150`
- `0x12280`
- `0x12570`
- `0x12610`
- `0x128a0`
- `0x12940`
- `0x12a60`
- `0x12d50`
- `0x12df0`
- `0x12e90`
- `0x12fe0`
- `0x130f0`
- `0x190d0`

## callees

- `0x18fd0`
- `0x19150`
- `0x19170`
- `0x19180`
- `0x191e0`
- `0x19200`
- `0x19cc0`
- `0x21890`

## pseudocode

```c

```

## disassembly

```asm
0x18fd0  newobj   instance void [System.Net.Http]System.Net.Http.HttpResponseMessage::.ctor()
0x18fd5  stloc.0
0x18fd6  ldloc.0
0x18fd7  ldarg.0
0x18fd8  call     instance class [System.Net.Http]System.Net.Http.HttpRequestMessage Microsoft.Crm.Extensibility.OData.CrmODataHeaders::get_Request()
0x18fdd  callvirt instance void [System.Net.Http]System.Net.Http.HttpResponseMessage::set_RequestMessage(class [System.Net.Http]System.Net.Http.HttpRequestMessage)
0x18fe2  ldloc.0
0x18fe3  callvirt instance class [System.Net.Http]System.Net.Http.Headers.HttpResponseHeaders [System.Net.Http]System.Net.Http.HttpResponseMessage::get_Headers()
0x18fe8  ldstr    aOdataVersion// "OData-Version"
0x18fed  ldc.i4.0
0x18fee  call     string [Microsoft.OData.Core]Microsoft.OData.ODataUtils::ODataVersionToString(valuetype [Microsoft.OData.Core]Microsoft.OData.ODataVersion)
0x18ff3  callvirt instance void [System.Net.Http]System.Net.Http.Headers.HttpHeaders::Add(string, string)
0x18ff8  ldarg.0
0x18ff9  call     instance bool Microsoft.Crm.Extensibility.OData.CrmODataHeaders::get_ODataCreateResponseHeadersSet()
0x18ffe  brfalse.s loc_1902C
0x19000  ldloc.0
0x19001  callvirt instance class [System.Net.Http]System.Net.Http.Headers.HttpResponseHeaders [System.Net.Http]System.Net.Http.HttpResponseMessage::get_Headers()
0x19006  ldarg.0
0x19007  call     instance class [System]System.Uri Microsoft.Crm.Extensibility.OData.CrmODataHeaders::get_ODataEntityId()
0x1900c  callvirt instance void [System.Net.Http]System.Net.Http.Headers.HttpResponseHeaders::set_Location(class [System]System.Uri)
0x19011  ldloc.0
0x19012  callvirt instance class [System.Net.Http]System.Net.Http.Headers.HttpResponseHeaders [System.Net.Http]System.Net.Http.HttpResponseMessage::get_Headers()
0x19017  ldstr    aOdataEntityid// "OData-EntityId"
0x1901c  ldarg.0
0x1901d  call     instance class [System]System.Uri Microsoft.Crm.Extensibility.OData.CrmODataHeaders::get_ODataEntityId()
0x19022  callvirt instance string [mscorlib]System.Object::ToString()
0x19027  callvirt instance void [System.Net.Http]System.Net.Http.Headers.HttpHeaders::Add(string, string)
0x1902c  ldarg.0
0x1902d  call     instance bool Microsoft.Crm.Extensibility.OData.CrmODataHeaders::get_ODataReturnRowVersionSet()
0x19032  brfalse.s loc_1906F
0x19034  ldarg.0
0x19035  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1903a  ldstr    a0_4// "\"{0}\""
0x1903f  ldc.i4.1
0x19040  newarr   [mscorlib]System.Object
0x19045  dup
0x19046  ldc.i4.0
0x19047  ldarg.0
0x19048  call     instance string Microsoft.Crm.Extensibility.OData.CrmODataHeaders::get_RowVersion()
0x1904d  stelem.ref
0x1904e  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x19053  call     instance void Microsoft.Crm.Extensibility.OData.CrmODataHeaders::set_RowVersion(string value)
0x19058  ldloc.0
0x19059  callvirt instance class [System.Net.Http]System.Net.Http.Headers.HttpResponseHeaders [System.Net.Http]System.Net.Http.HttpResponseMessage::get_Headers()
0x1905e  ldarg.0
0x1905f  call     instance string Microsoft.Crm.Extensibility.OData.CrmODataHeaders::get_RowVersion()
0x19064  ldc.i4.1
0x19065  newobj   instance void [System.Net.Http]System.Net.Http.Headers.EntityTagHeaderValue::.ctor(string, bool)
0x1906a  callvirt instance void [System.Net.Http]System.Net.Http.Headers.HttpResponseHeaders::set_ETag(class [System.Net.Http]System.Net.Http.Headers.EntityTagHeaderValue)
0x1906f  ldarg.1
0x19070  brfalse.s loc_19087
0x19072  ldloc.0
0x19073  callvirt instance class [System.Net.Http]System.Net.Http.Headers.HttpResponseHeaders [System.Net.Http]System.Net.Http.HttpResponseMessage::get_Headers()
0x19078  ldstr    aPreferenceAppl_0// "Preference-Applied"
0x1907d  ldstr    aReturnMinimal// "return=minimal"
0x19082  callvirt instance void [System.Net.Http]System.Net.Http.Headers.HttpHeaders::Add(string, string)
0x19087  ldloc.0
0x19088  ldc.i4   0xCC
0x1908d  callvirt instance void [System.Net.Http]System.Net.Http.HttpResponseMessage::set_StatusCode(valuetype [System]System.Net.HttpStatusCode)
0x19092  ldloc.0
0x19093  newobj   instance void Microsoft.Crm.Extensibility.OData.CrmStatusCodeResult::.ctor(class [System.Net.Http]System.Net.Http.HttpResponseMessage response)
0x19098  ret
```
