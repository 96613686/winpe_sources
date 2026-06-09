# Microsoft.Crm.PageParametersCache::GetPageParametersByMethodInternal

- ea: `0x640`
- end: `0x65d`
- name: `Microsoft.Crm.PageParametersCache::GetPageParametersByMethodInternal`
- size: `29`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x400`

## callees

- `0x640`
- `0x660`
- `0x710`
- `0x760`

## pseudocode

```c

```

## disassembly

```asm
0x640  ldarg.0
0x641  ldarg.1
0x642  call     instance class Microsoft.Crm.PageParameters Microsoft.Crm.PageParametersCache::GetPageParametersFromCache(string physicalPath)
0x647  stloc.0
0x648  ldloc.0
0x649  brtrue.s loc_65B
0x64b  ldarg.0
0x64c  ldarg.2
0x64d  call     instance class Microsoft.Crm.PageParameters Microsoft.Crm.PageParametersCache::ReadParametersFromAttributes(class [mscorlib]System.Reflection.ICustomAttributeProvider resource)
0x652  stloc.0
0x653  ldarg.0
0x654  ldarg.1
0x655  ldloc.0
0x656  call     instance void Microsoft.Crm.PageParametersCache::AddPageParametersToCache(string physicalPath, class Microsoft.Crm.PageParameters pageParameters)
0x65b  ldloc.0
0x65c  ret
```
