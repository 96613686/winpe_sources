# __local_stdio_printf_options

- ea: `0x180002a84`
- end: `0x180002a8c`
- name: `__local_stdio_printf_options`
- size: `8`
- prototype: `unsigned __int64 *__cdecl()`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x180002a60`
- `0x180002ab0`
- `0x1800036d8`
- `0x180003970`
- `0x1800039c4`
- `0x180003a28`

## pseudocode

```c
unsigned __int64 *__cdecl _local_stdio_printf_options()
{
  return (unsigned __int64 *)&`__local_stdio_printf_options'::`2'::_OptionsStorage;
}

```

## disassembly

```asm
0x180002a84  lea     rax, ?_OptionsStorage@?1??__local_stdio_printf_options@@9@4_KA; unsigned __int64 `__local_stdio_printf_options'::`2'::_OptionsStorage
0x180002a8b  retn
```
