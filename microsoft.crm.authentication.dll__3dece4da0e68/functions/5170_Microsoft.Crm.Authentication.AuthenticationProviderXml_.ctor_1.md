# Microsoft.Crm.Authentication.AuthenticationProviderXml::.ctor_1

- ea: `0x5170`
- end: `0x519a`
- name: `Microsoft.Crm.Authentication.AuthenticationProviderXml::.ctor_1`
- size: `42`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x5140`

## callees

- `0x50f0`
- `0x5120`

## string_xrefs

- `0x517c`: `{0}, {1}, Version={{0}}, Culture=neutral, PublicKeyToken=31bf3856ad364e35`

## pseudocode

```c

```

## disassembly

```asm
0x5170  ldarg.0
0x5171  call     instance void Microsoft.Crm.Authentication.AuthenticationProviderXml::.ctor()
0x5176  ldarg.0
0x5177  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x517c  ldstr    a01Version0Cult// "{0}, {1}, Version={{0}}, Culture=neutra"...
0x5181  ldc.i4.2
0x5182  newarr   [mscorlib]System.Object
0x5187  dup
0x5188  ldc.i4.0
0x5189  ldarg.1
0x518a  stelem.ref
0x518b  dup
0x518c  ldc.i4.1
0x518d  ldarg.2
0x518e  stelem.ref
0x518f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x5194  call     instance void Microsoft.Crm.Authentication.AuthenticationProviderXml::set_Type(string value)
0x5199  ret
```
