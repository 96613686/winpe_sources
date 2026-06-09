# Microsoft.Crm.Asynchronous.YammerPostOperation::PostJson

- ea: `0x96c0`
- end: `0x9789`
- name: `Microsoft.Crm.Asynchronous.YammerPostOperation::PostJson`
- size: `201`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0xa2b0`

## callees

- `0x96c0`
- `0x9790`

## pseudocode

```c

```

## disassembly

```asm
0x96c0  ldarg.1
0x96c1  call     class [System]System.Net.WebRequest [System]System.Net.WebRequest::Create(class [System]System.Uri)
0x96c6  castclass [System]System.Net.HttpWebRequest
0x96cb  stloc.0
0x96cc  ldarg.3
0x96cd  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x96d2  brtrue.s loc_96DB
0x96d4  ldloc.0
0x96d5  ldarg.3
0x96d6  callvirt instance void [System]System.Net.WebRequest::set_Method(string)
0x96db  ldarg.s  4
0x96dd  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x96e2  brtrue.s loc_96EC
0x96e4  ldloc.0
0x96e5  ldarg.s  4
0x96e7  callvirt instance void [System]System.Net.WebRequest::set_ContentType(string)
0x96ec  ldarg.s  5
0x96ee  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x96f3  brtrue.s loc_96FD
0x96f5  ldloc.0
0x96f6  ldarg.s  5
0x96f8  callvirt instance void [System]System.Net.HttpWebRequest::set_Accept(string)
0x96fd  ldarg.2
0x96fe  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x9703  brtrue.s loc_971D
0x9705  ldloc.0
0x9706  callvirt instance class [System]System.Net.WebHeaderCollection [System]System.Net.WebRequest::get_Headers()
0x970b  ldc.i4.s 0x18
0x970d  ldstr    aBearer// "Bearer "
0x9712  ldarg.2
0x9713  call     string [mscorlib]System.String::Concat(string, string)
0x9718  callvirt instance void [System]System.Net.WebHeaderCollection::set_Item(valuetype [System]System.Net.HttpRequestHeader, string)
0x971d  ldarg.s  7
0x971f  ldsfld   valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::Zero
0x9724  call     bool [mscorlib]System.TimeSpan::op_GreaterThan(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0x9729  brfalse.s loc_974B
0x972b  ldarga.s 7
0x972d  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMilliseconds()
0x9732  ldc.r8   2.147483647e9
0x973b  bgt.un.s loc_974B
0x973d  ldloc.0
0x973e  ldarga.s 7
0x9740  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMilliseconds()
0x9745  conv.i4
0x9746  callvirt instance void [System]System.Net.WebRequest::set_Timeout(int32)
0x974b  ldarg.s  6
0x974d  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x9752  brtrue.s loc_9780
0x9754  ldloc.0
0x9755  callvirt instance class [mscorlib]System.IO.Stream [System]System.Net.WebRequest::GetRequestStream()
0x975a  stloc.1
0x975b  ldloc.1
0x975c  newobj   instance void [mscorlib]System.IO.StreamWriter::.ctor(class [mscorlib]System.IO.Stream)
0x9761  stloc.2
0x9762  ldloc.2
0x9763  ldarg.s  6
0x9765  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x976a  leave.s  loc_9780
0x976c  ldloc.2
0x976d  brfalse.s loc_9775
0x976f  ldloc.2
0x9770  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x9775  endfinally
0x9776  ldloc.1
0x9777  brfalse.s loc_977F
0x9779  ldloc.1
0x977a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x977f  endfinally
0x9780  ldloc.0
0x9781  ldarg.s  8
0x9783  call     string Microsoft.Crm.Asynchronous.YammerPostOperation::GetWebResponseCode(class [System]System.Net.WebRequest request, [out] valuetype [System]System.Net.HttpStatusCode& statusCode)
0x9788  ret
```
