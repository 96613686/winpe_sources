# Microsoft.Crm.Authentication.AuthenticationPredicateXml::.ctor_0

- ea: `0x5000`
- end: `0x502a`
- name: `Microsoft.Crm.Authentication.AuthenticationPredicateXml::.ctor_0`
- size: `42`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x4fd0`

## callees

- `0x4fa0`
- `0x5030`

## string_xrefs

- `0x500c`: `{0}, {1}, Version={{0}}, Culture=neutral, PublicKeyToken=31bf3856ad364e35`

## pseudocode

```c

```

## disassembly

```asm
0x5000  ldarg.0
0x5001  call     instance void Microsoft.Crm.Authentication.AuthenticationPredicateXml::.ctor()
0x5006  ldarg.0
0x5007  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x500c  ldstr    a01Version0Cult// "{0}, {1}, Version={{0}}, Culture=neutra"...
0x5011  ldc.i4.2
0x5012  newarr   [mscorlib]System.Object
0x5017  dup
0x5018  ldc.i4.0
0x5019  ldarg.1
0x501a  stelem.ref
0x501b  dup
0x501c  ldc.i4.1
0x501d  ldarg.2
0x501e  stelem.ref
0x501f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x5024  call     instance void Microsoft.Crm.Authentication.AuthenticationPredicateXml::set_Type(string value)
0x5029  ret
```
