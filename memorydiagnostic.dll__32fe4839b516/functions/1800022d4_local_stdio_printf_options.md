# __local_stdio_printf_options

- ea: `0x1800022d4`
- end: `0x1800022dc`
- name: `__local_stdio_printf_options`
- size: `8`
- prototype: `unsigned __int64 *__cdecl()`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x1800022b0`
- `0x180002300`
- `0x180002c38`
- `0x18000338c`
- `0x1800033f4`
- `0x18000344c`

## pseudocode

```c
unsigned __int64 *__cdecl _local_stdio_printf_options()
{
  return (unsigned __int64 *)&`__local_stdio_printf_options'::`2'::_OptionsStorage;
}

```

## disassembly

```asm
0x1800022d4  lea     rax, ?_OptionsStorage@?1??__local_stdio_printf_options@@9@4_KA
0x1800022db  retn
```
