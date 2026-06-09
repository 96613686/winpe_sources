# Microsoft.Crm.ParameterFilterBase::HasFormStream

- ea: `0x1180`
- end: `0x11c1`
- name: `Microsoft.Crm.ParameterFilterBase::HasFormStream`
- size: `65`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1370`

## callees

- `0x1180`

## pseudocode

```c

```

## disassembly

```asm
0x1180  ldarg.0
0x1181  callvirt instance class [mscorlib]System.IO.Stream [System.Web]System.Web.HttpRequest::get_InputStream()
0x1186  callvirt instance int64 [mscorlib]System.IO.Stream::get_Length()
0x118b  ldc.i4.0
0x118c  conv.i8
0x118d  ble.s    loc_11BF
0x118f  ldarg.0
0x1190  callvirt instance string [System.Web]System.Web.HttpRequest::get_ContentType()
0x1195  brfalse.s loc_11BF
0x1197  ldarg.0
0x1198  callvirt instance string [System.Web]System.Web.HttpRequest::get_ContentType()
0x119d  ldstr    aApplicationXWw// "application/x-www-form-urlencoded"
0x11a2  ldc.i4.5
0x11a3  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x11a8  brtrue.s loc_11BF
0x11aa  ldarg.0
0x11ab  callvirt instance string [System.Web]System.Web.HttpRequest::get_ContentType()
0x11b0  ldstr    aMultipartFormD// "multipart/form-data"
0x11b5  ldc.i4.5
0x11b6  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x11bb  ldc.i4.0
0x11bc  ceq
0x11be  ret
0x11bf  ldc.i4.0
0x11c0  ret
```
