# Microsoft.Crm.ServiceBus.TokenProvider::RetrieveEndpointToken

- ea: `0x55a0`
- end: `0x574f`
- name: `Microsoft.Crm.ServiceBus.TokenProvider::RetrieveEndpointToken`
- size: `431`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x4450`
- `0x5cd0`

## callees

- `0x13f0`
- `0x1700`
- `0x1820`
- `0x5570`
- `0x55a0`
- `0x5b90`
- `0x5c50`

## string_xrefs

- `0x567a`: `Token`
- `0x56f3`: `The timeout elapsed upon attempting to obtain a token.`
- `0x570a`: `The token provider was unable to provide a security token. {0} : {1}`

## pseudocode

```c

```

## disassembly

```asm
0x55a0  ldarg.0
0x55a1  call     instance class Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation Microsoft.Crm.ServiceBus.TokenProvider::get_EndpointInfo()
0x55a6  ldstr    aEndpointinfo_0// "EndpointInfo"
0x55ab  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x55b0  ldsfld   string [mscorlib]System.String::Empty
0x55b5  stloc.0
0x55b6  newobj   instance void [System]System.Net.WebClient::.ctor()
0x55bb  stloc.2
0x55bc  ldloc.2
0x55bd  ldarg.0
0x55be  ldarg.0
0x55bf  call     instance class Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation Microsoft.Crm.ServiceBus.TokenProvider::get_EndpointInfo()
0x55c4  callvirt instance string Microsoft.Crm.ServiceBus.IServiceBusEndpointInformation::get_SolutionName()
0x55c9  ldarg.1
0x55ca  call     instance class [System]System.Uri Microsoft.Crm.ServiceBus.TokenProvider::AccessControlPath(string solutionName, bool isServiceBusScope)
0x55cf  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x55d4  callvirt instance void [System]System.Net.WebClient::set_BaseAddress(string)
0x55d9  ldloc.2
0x55da  callvirt instance class [System]System.Net.WebHeaderCollection [System]System.Net.WebClient::get_Headers()
0x55df  ldc.i4.s 0xC
0x55e1  ldstr    aApplicationXWw// "application/x-www-form-urlencoded"
0x55e6  callvirt instance void [System]System.Net.WebHeaderCollection::set_Item(valuetype [System]System.Net.HttpRequestHeader, string)
0x55eb  ldloc.2
0x55ec  ldsfld   string [mscorlib]System.String::Empty
0x55f1  ldstr    aPost// "POST"
0x55f6  ldarg.0
0x55f7  ldarg.1
0x55f8  call     instance class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.ServiceBus.TokenProvider::CreateTokenRequestBody(bool forServiceBusScope)
0x55fd  callvirt instance unsigned int8[] [System]System.Net.WebClient::UploadValues(string, string, class [System]System.Collections.Specialized.NameValueCollection)
0x5602  stloc.3
0x5603  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_UTF8()
0x5608  ldloc.3
0x5609  callvirt instance string [mscorlib]System.Text.Encoding::GetString(unsigned int8[])
0x560e  stloc.0
0x560f  leave.s  loc_561B
0x5611  ldloc.2
0x5612  brfalse.s loc_561A
0x5614  ldloc.2
0x5615  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x561a  endfinally
0x561b  ldloc.0
0x561c  ldc.i4.1
0x561d  newarr   [mscorlib]System.Char
0x5622  dup
0x5623  ldc.i4.0
0x5624  ldc.i4.s 0x26
0x5626  stelem.i2
0x5627  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x562c  ldsfld   class [mscorlib]System.Func`2<string, bool> <>c::<>9__5_0
0x5631  dup
0x5632  brtrue.s loc_564B
0x5634  pop
0x5635  ldsfld   class <>c <>c::<>9
0x563a  ldftn    instance bool <>c::<RetrieveEndpointToken>b__5_0(string value)
0x5640  newobj   instance void class [mscorlib]System.Func`2<string, bool>::.ctor(object, native int)
0x5645  dup
0x5646  stsfld   class [mscorlib]System.Func`2<string, bool> <>c::<>9__5_0
0x564b  call     T0x2B000007
0x5650  ldc.i4.1
0x5651  newarr   [mscorlib]System.Char
0x5656  dup
0x5657  ldc.i4.0
0x5658  ldc.i4.s 0x3D
0x565a  stelem.i2
0x565b  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x5660  ldc.i4.1
0x5661  ldelem.ref
0x5662  call     string [System]System.Uri::UnescapeDataString(string)
0x5667  stloc.1
0x5668  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x566d  ldstr    a01_1// "{0} {1}"
0x5672  ldc.i4.2
0x5673  newarr   [mscorlib]System.Object
0x5678  dup
0x5679  ldc.i4.0
0x567a  ldstr    aToken// "Token"
0x567f  stelem.ref
0x5680  dup
0x5681  ldc.i4.1
0x5682  ldloc.1
0x5683  stelem.ref
0x5684  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x5689  stloc.s  4
0x568b  leave    loc_574C
0x5690  stloc.s  5
0x5692  ldsfld   string [mscorlib]System.String::Empty
0x5697  stloc.s  6
0x5699  ldloc.s  5
0x569b  callvirt instance class [System]System.Net.WebResponse [System]System.Net.WebException::get_Response()
0x56a0  brfalse.s loc_56D8
0x56a2  ldloc.s  5
0x56a4  callvirt instance class [System]System.Net.WebResponse [System]System.Net.WebException::get_Response()
0x56a9  callvirt instance class [mscorlib]System.IO.Stream [System]System.Net.WebResponse::GetResponseStream()
0x56ae  newobj   instance void [mscorlib]System.IO.StreamReader::.ctor(class [mscorlib]System.IO.Stream)
0x56b3  stloc.s  7
0x56b5  ldloc.s  7
0x56b7  callvirt instance string [mscorlib]System.IO.TextReader::ReadToEnd()
0x56bc  stloc.s  6
0x56be  leave.s  loc_56CC
0x56c0  ldloc.s  7
0x56c2  brfalse.s loc_56CB
0x56c4  ldloc.s  7
0x56c6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x56cb  endfinally
0x56cc  ldloc.s  5
0x56ce  callvirt instance class [System]System.Net.WebResponse [System]System.Net.WebException::get_Response()
0x56d3  callvirt instance void [System]System.Net.WebResponse::Close()
0x56d8  ldloc.s  5
0x56da  callvirt instance valuetype [System]System.Net.WebExceptionStatus [System]System.Net.WebException::get_Status()
0x56df  ldc.i4.s 0xE
0x56e1  bne.un.s loc_5705
0x56e3  call     class Microsoft.Crm.ServiceBus.PerformanceCounters Microsoft.Crm.ServiceBus.PerformanceCounters::get_Current()
0x56e8  callvirt instance class [System]System.Diagnostics.PerformanceCounter Microsoft.Crm.ServiceBus.PerformanceCounters::get_AppFabricRequestTimeout()
0x56ed  callvirt instance int64 [System]System.Diagnostics.PerformanceCounter::Increment()
0x56f2  pop
0x56f3  ldstr    aTheTimeoutElap// "The timeout elapsed upon attempting to "...
0x56f8  ldloc.s  5
0x56fa  ldc.i4   0x80044178
0x56ff  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, class [mscorlib]System.Exception, int32)
0x5704  throw
0x5705  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x570a  ldstr    aTheTokenProvid// "The token provider was unable to provid"...
0x570f  ldc.i4.2
0x5710  newarr   [mscorlib]System.Object
0x5715  dup
0x5716  ldc.i4.0
0x5717  ldloc.s  5
0x5719  callvirt instance string [mscorlib]System.Exception::get_Message()
0x571e  stelem.ref
0x571f  dup
0x5720  ldc.i4.1
0x5721  ldloc.s  6
0x5723  stelem.ref
0x5724  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x5729  ldloc.s  5
0x572b  ldc.i4   0x80044178
0x5730  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, class [mscorlib]System.Exception, int32)
0x5735  throw
0x5736  stloc.s  8
0x5738  ldloc.s  8
0x573a  callvirt instance string [mscorlib]System.Exception::get_Message()
0x573f  ldloc.s  8
0x5741  ldc.i4   0x80044178
0x5746  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, class [mscorlib]System.Exception, int32)
0x574b  throw
0x574c  ldloc.s  4
0x574e  ret
```
