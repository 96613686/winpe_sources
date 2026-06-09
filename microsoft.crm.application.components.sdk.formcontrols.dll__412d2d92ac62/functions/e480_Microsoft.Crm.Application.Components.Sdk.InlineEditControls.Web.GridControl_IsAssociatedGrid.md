# Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.GridControl::IsAssociatedGrid

- ea: `0xe480`
- end: `0xe48d`
- name: `Microsoft.Crm.Application.Components.Sdk.InlineEditControls.Web.GridControl::IsAssociatedGrid`
- size: `13`
- prototype: ``
- caller_count: `10`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xb970`
- `0xbbf0`
- `0xbc50`
- `0xbcf0`
- `0xbd60`
- `0xbee0`
- `0xc620`
- `0xc7d0`
- `0xc910`
- `0xde50`

## callees

- `0x1c810`

## pseudocode

```c

```

## disassembly

```asm
0xe480  ldarg.0
0xe481  call     instance valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.GridTypeCode Microsoft.Crm.Application.Components.Sdk.FormControls.Web.GridControl::get_GridType()
0xe486  ldc.i4.4
0xe487  ceq
0xe489  ldc.i4.0
0xe48a  ceq
0xe48c  ret
```
