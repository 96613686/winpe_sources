# Microsoft.Crm.ParameterFilterBase::GetInputStream

- ea: `0x1160`
- end: `0x1180`
- name: `Microsoft.Crm.ParameterFilterBase::GetInputStream`
- size: `32`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1370`

## pseudocode

```c

```

## disassembly

```asm
0x1160  ldarg.0
0x1161  callvirt instance class [mscorlib]System.IO.Stream [System.Web]System.Web.HttpRequest::get_InputStream()
0x1166  newobj   instance void [mscorlib]System.IO.StreamReader::.ctor(class [mscorlib]System.IO.Stream)
0x116b  callvirt instance string [mscorlib]System.IO.TextReader::ReadToEnd()
0x1170  ldarg.0
0x1171  callvirt instance class [mscorlib]System.IO.Stream [System.Web]System.Web.HttpRequest::get_InputStream()
0x1176  ldc.i4.0
0x1177  conv.i8
0x1178  ldc.i4.0
0x1179  callvirt instance int64 [mscorlib]System.IO.Stream::Seek(int64, valuetype [mscorlib]System.IO.SeekOrigin)
0x117e  pop
0x117f  ret
```
