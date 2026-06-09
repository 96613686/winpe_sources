# Microsoft.Crm.PageParametersCache::GetPageParameters_1

- ea: `0x400`
- end: `0x446`
- name: `Microsoft.Crm.PageParametersCache::GetPageParameters_1`
- size: `70`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0xf20`

## callees

- `0x400`
- `0x640`
- `0x8c0`

## pseudocode

```c

```

## disassembly

```asm
0x400  ldarg.1
0x401  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x406  brfalse.s loc_40F
0x408  ldsfld   string [mscorlib]System.String::Empty
0x40d  starg.s  1
0x40f  ldarg.3
0x410  brtrue.s loc_41D
0x412  ldstr    aRequestCannotB// "Request cannot be null"
0x417  newobj   instance void Microsoft.Crm.PageParametersCacheException::.ctor(string message)
0x41c  throw
0x41d  ldarg.2
0x41e  brtrue.s loc_42B
0x420  ldstr    aResourceToBeCh// "Resource to be checked cannot be null"
0x425  newobj   instance void Microsoft.Crm.PageParametersCacheException::.ctor(string message)
0x42a  throw
0x42b  ldarg.3
0x42c  callvirt instance string [System.Web]System.Web.HttpRequest::get_Path()
0x431  ldstr    asc_208E// "+"
0x436  ldarg.1
0x437  call     string [mscorlib]System.String::Concat(string, string, string)
0x43c  stloc.0
0x43d  ldarg.0
0x43e  ldloc.0
0x43f  ldarg.2
0x440  call     instance class Microsoft.Crm.PageParameters Microsoft.Crm.PageParametersCache::GetPageParametersByMethodInternal(string key, class [mscorlib]System.Reflection.ICustomAttributeProvider resource)
0x445  ret
```
