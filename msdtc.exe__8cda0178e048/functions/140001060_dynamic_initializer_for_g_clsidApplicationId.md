# _dynamic_initializer_for__g_clsidApplicationId__

- ea: `0x140001060`
- end: `0x140001070`
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
0x140001060  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x140001067  movdqu  xmmword ptr cs:?g_clsidApplicationId@@3U_GUID@@A.Data1, xmm0; _GUID g_clsidApplicationId ...
0x14000106f  retn
```
