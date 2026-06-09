# Microsoft.Crm.PageParametersCache::GetPageParameters_0

- ea: `0x3f0`
- end: `0x3fc`
- name: `Microsoft.Crm.PageParametersCache::GetPageParameters_0`
- size: `12`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xea0`
- `0xee0`

## callees

- `0x480`

## pseudocode

```c

```

## disassembly

```asm
0x3f0  ldarg.0
0x3f1  ldarg.1
0x3f2  ldarg.2
0x3f3  ldarg.3
0x3f4  ldarg.s  4
0x3f6  call     instance class Microsoft.Crm.PageParameters Microsoft.Crm.PageParametersCache::GetPageParametersInternal(object resource, class [System.Web]System.Web.HttpRequest request, valuetype [mscorlib]System.Guid orgId, valuetype [mscorlib]System.Guid CurrentFormId)
0x3fb  ret
```
