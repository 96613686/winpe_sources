# Microsoft.Crm.PageParametersCache::GetPageParameters

- ea: `0x3e0`
- end: `0x3f0`
- name: `Microsoft.Crm.PageParametersCache::GetPageParameters`
- size: `16`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xf70`
- `0xfa0`

## callees

- `0x480`

## pseudocode

```c

```

## disassembly

```asm
0x3e0  ldarg.0
0x3e1  ldarg.1
0x3e2  ldarg.1
0x3e3  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.UI.Page::get_Request()
0x3e8  ldarg.2
0x3e9  ldarg.3
0x3ea  call     instance class Microsoft.Crm.PageParameters Microsoft.Crm.PageParametersCache::GetPageParametersInternal(object resource, class [System.Web]System.Web.HttpRequest request, valuetype [mscorlib]System.Guid orgId, valuetype [mscorlib]System.Guid CurrentFormId)
0x3ef  ret
```
