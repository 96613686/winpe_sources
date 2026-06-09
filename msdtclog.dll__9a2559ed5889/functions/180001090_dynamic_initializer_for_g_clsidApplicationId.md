# _dynamic_initializer_for__g_clsidApplicationId__

- ea: `0x180001090`
- end: `0x1800010a0`
- name: `_dynamic_initializer_for__g_clsidApplicationId__`
- size: `16`
- prototype: `void()`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## pseudocode

```c
void dynamic_initializer_for__g_clsidApplicationId__()
{
  g_clsidApplicationId = GUID_NULL;
}

```

## disassembly

```asm
0x180001090  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180001097  movdqu  xmmword ptr cs:?g_clsidApplicationId@@3U_GUID@@A.Data1, xmm0; _GUID g_clsidApplicationId ...
0x18000109f  retn
```
