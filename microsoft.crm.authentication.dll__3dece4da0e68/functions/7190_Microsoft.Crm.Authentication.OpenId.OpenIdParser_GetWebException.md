# Microsoft.Crm.Authentication.OpenId.OpenIdParser::GetWebException

- ea: `0x7190`
- end: `0x723a`
- name: `Microsoft.Crm.Authentication.OpenId.OpenIdParser::GetWebException`
- size: `170`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x6f90`
- `0x7060`

## callees

- `0x7190`

## pseudocode

```c

```

## disassembly

```asm
0x7190  ldarg.1
0x7191  brtrue.s loc_7199
0x7193  ldsfld   string [mscorlib]System.String::Empty
0x7198  ret
0x7199  ldarg.1
0x719a  callvirt instance class [System]System.Net.WebResponse [System]System.Net.WebException::get_Response()
0x719f  isinst   [System]System.Net.HttpWebResponse
0x71a4  stloc.0
0x71a5  ldloc.0
0x71a6  brtrue.s loc_71AE
0x71a8  ldsfld   string [mscorlib]System.String::Empty
0x71ad  ret
0x71ae  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x71b3  stloc.1
0x71b4  ldloc.1
0x71b5  ldstr    aStatus0// "Status : {0}\n"
0x71ba  ldarg.1
0x71bb  callvirt instance valuetype [System]System.Net.WebExceptionStatus [System]System.Net.WebException::get_Status()
0x71c0  box      [System]System.Net.WebExceptionStatus
0x71c5  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0x71ca  pop
0x71cb  ldloc.1
0x71cc  ldstr    aStatusCode0// "Status Code : {0}\n"
0x71d1  ldloc.0
0x71d2  callvirt instance valuetype [System]System.Net.HttpStatusCode [System]System.Net.HttpWebResponse::get_StatusCode()
0x71d7  box      [System]System.Net.HttpStatusCode
0x71dc  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0x71e1  pop
0x71e2  ldloc.1
0x71e3  ldstr    aStatusDescript// "Status Description : {0}\n"
0x71e8  ldloc.0
0x71e9  callvirt instance string [System]System.Net.HttpWebResponse::get_StatusDescription()
0x71ee  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0x71f3  pop
0x71f4  ldloc.0
0x71f5  callvirt instance class [mscorlib]System.IO.Stream [System]System.Net.WebResponse::GetResponseStream()
0x71fa  stloc.2
0x71fb  ldloc.2
0x71fc  brfalse.s loc_7227
0x71fe  ldloc.2
0x71ff  newobj   instance void [mscorlib]System.IO.StreamReader::.ctor(class [mscorlib]System.IO.Stream)
0x7204  stloc.3
0x7205  ldloc.3
0x7206  callvirt instance string [mscorlib]System.IO.TextReader::ReadToEnd()
0x720b  stloc.s  4
0x720d  ldloc.1
0x720e  ldstr    aResponseConten// "Response Content : {0}\n"
0x7213  ldloc.s  4
0x7215  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0x721a  pop
0x721b  leave.s  loc_7233
0x721d  ldloc.3
0x721e  brfalse.s loc_7226
0x7220  ldloc.3
0x7221  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7226  endfinally
0x7227  leave.s  loc_7233
0x7229  ldloc.2
0x722a  brfalse.s loc_7232
0x722c  ldloc.2
0x722d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7232  endfinally
0x7233  ldloc.1
0x7234  callvirt instance string [mscorlib]System.Object::ToString()
0x7239  ret
```
