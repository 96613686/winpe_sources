# Microsoft.Crm.Unzip.Common.EndpointUrlHelper::BuildUrl

- ea: `0x90`
- end: `0xaf`
- name: `Microsoft.Crm.Unzip.Common.EndpointUrlHelper::BuildUrl`
- size: `31`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0xd0`

## pseudocode

```c

```

## disassembly

```asm
0x90  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x95  ldstr    aNetTcp0Unzippr// "net.tcp://{0}/UnzipProxy/2009"
0x9a  ldc.i4.1
0x9b  newarr   [mscorlib]System.Object
0xa0  dup
0xa1  ldc.i4.0
0xa2  ldarg.0
0xa3  stelem.ref
0xa4  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xa9  newobj   instance void [System]System.Uri::.ctor(string)
0xae  ret
```
