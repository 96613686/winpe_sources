# _dynamic_initializer_for__g_clsid__

- ea: `0x140001010`
- end: `0x140001020`
- name: `_dynamic_initializer_for__g_clsid__`
- size: `16`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## pseudocode

```c
void dynamic_initializer_for__g_clsid__()
{
  g_clsid = GUID_NULL;
}

```

## disassembly

```asm
0x140001010  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x140001017  movdqu  xmmword ptr cs:?g_clsid@@3U_GUID@@A.Data1, xmm0; _GUID g_clsid ...
0x14000101f  retn
```
