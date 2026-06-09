# ___local_stdio_scanf_options

- ea: `0x10012771`
- end: `0x10012777`
- name: `___local_stdio_scanf_options`
- size: `6`
- prototype: `unsigned __int64 *__cdecl()`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x10012740`
- `0x10012780`
- `0x10012c2e`

## pseudocode

```c
unsigned __int64 *__cdecl __local_stdio_scanf_options()
{
  return (unsigned __int64 *)`__local_stdio_scanf_options'::`2'::_OptionsStorage;
}

```

## disassembly

```asm
0x10012771  mov     eax, offset ?_OptionsStorage@?1??__local_stdio_scanf_options@@9@4_KA; unsigned __int64 `__local_stdio_scanf_options'::`2'::_OptionsStorage
0x10012776  retn
```
