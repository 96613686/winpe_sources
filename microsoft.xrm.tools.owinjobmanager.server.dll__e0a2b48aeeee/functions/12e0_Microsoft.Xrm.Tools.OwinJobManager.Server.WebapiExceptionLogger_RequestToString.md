# Microsoft.Xrm.Tools.OwinJobManager.Server.WebapiExceptionLogger::RequestToString

- ea: `0x12e0`
- end: `0x132d`
- name: `Microsoft.Xrm.Tools.OwinJobManager.Server.WebapiExceptionLogger::RequestToString`
- size: `77`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x12b0`

## callees

- `0x12e0`

## pseudocode

```c

```

## disassembly

```asm
0x12e0  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x12e5  stloc.0
0x12e6  ldarg.0
0x12e7  callvirt instance class [System.Net.Http]System.Net.Http.HttpMethod [System.Net.Http]System.Net.Http.HttpRequestMessage::get_Method()
0x12ec  ldnull
0x12ed  call     bool [System.Net.Http]System.Net.Http.HttpMethod::op_Inequality(class [System.Net.Http]System.Net.Http.HttpMethod, class [System.Net.Http]System.Net.Http.HttpMethod)
0x12f2  brfalse.s loc_1301
0x12f4  ldloc.0
0x12f5  ldarg.0
0x12f6  callvirt instance class [System.Net.Http]System.Net.Http.HttpMethod [System.Net.Http]System.Net.Http.HttpRequestMessage::get_Method()
0x12fb  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(object)
0x1300  pop
0x1301  ldarg.0
0x1302  callvirt instance class [System]System.Uri [System.Net.Http]System.Net.Http.HttpRequestMessage::get_RequestUri()
0x1307  ldnull
0x1308  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0x130d  brfalse.s loc_1326
0x130f  ldloc.0
0x1310  ldstr    asc_239C// " "
0x1315  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x131a  ldarg.0
0x131b  callvirt instance class [System]System.Uri [System.Net.Http]System.Net.Http.HttpRequestMessage::get_RequestUri()
0x1320  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(object)
0x1325  pop
0x1326  ldloc.0
0x1327  callvirt instance string [mscorlib]System.Object::ToString()
0x132c  ret
```
