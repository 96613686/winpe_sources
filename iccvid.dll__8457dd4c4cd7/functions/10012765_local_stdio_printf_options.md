# ___local_stdio_printf_options

- ea: `0x10012765`
- end: `0x1001276b`
- name: `___local_stdio_printf_options`
- size: `6`
- prototype: `unsigned __int64 *__cdecl()`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x10012740`
- `0x10012780`
- `0x10012c2e`
- `0x10013493`

## pseudocode

```c
unsigned __int64 *__cdecl __local_stdio_printf_options()
{
  return (unsigned __int64 *)`__local_stdio_printf_options'::`2'::_OptionsStorage;
}

```

## disassembly

```asm
0x10012765  mov     eax, offset ?_OptionsStorage@?1??__local_stdio_printf_options@@9@4_KA; unsigned __int64 `__local_stdio_printf_options'::`2'::_OptionsStorage
0x1001276a  retn
```
