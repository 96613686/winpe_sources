# Microsoft.Crm.Common.Repository::GetTypeFromCacheKey

- ea: `0x1840`
- end: `0x186a`
- name: `Microsoft.Crm.Common.Repository::GetTypeFromCacheKey`
- size: `42`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0xce0`

## pseudocode

```c

```

## disassembly

```asm
0x1840  ldarg.0
0x1841  ldstr    asc_2974// ";"
0x1846  ldc.i4.5
0x1847  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0x184c  stloc.0
0x184d  ldarg.0
0x184e  ldstr    aRepository// "Repository_"
0x1853  call     instance int32 [mscorlib]System.String::get_Length()
0x1858  ldloc.0
0x1859  ldstr    aRepository// "Repository_"
0x185e  call     instance int32 [mscorlib]System.String::get_Length()
0x1863  sub
0x1864  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x1869  ret
```
