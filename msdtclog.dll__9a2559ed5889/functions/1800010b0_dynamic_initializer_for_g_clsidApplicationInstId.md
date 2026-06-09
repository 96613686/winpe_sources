# _dynamic_initializer_for__g_clsidApplicationInstId__

- ea: `0x1800010b0`
- end: `0x1800010c0`
- name: `_dynamic_initializer_for__g_clsidApplicationInstId__`
- size: `16`
- prototype: `void()`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## pseudocode

```c
void dynamic_initializer_for__g_clsidApplicationInstId__()
{
  g_clsidApplicationInstId = GUID_NULL;
}

```

## disassembly

```asm
0x1800010b0  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800010b7  movdqu  xmmword ptr cs:?g_clsidApplicationInstId@@3U_GUID@@A.Data1, xmm0; _GUID g_clsidApplicationInstId ...
0x1800010bf  retn
```
