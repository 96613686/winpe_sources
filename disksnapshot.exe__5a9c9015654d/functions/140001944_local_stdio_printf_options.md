# __local_stdio_printf_options

- ea: `0x140001944`
- end: `0x14000194c`
- name: `__local_stdio_printf_options`
- size: `8`
- prototype: `unsigned __int64 *__cdecl()`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x140001920`
- `0x140001970`
- `0x1400023dc`
- `0x14000281c`
- `0x140002870`
- `0x1400028cc`
- `0x140002920`

## pseudocode

```c
unsigned __int64 *__cdecl _local_stdio_printf_options()
{
  return (unsigned __int64 *)&`__local_stdio_printf_options'::`2'::_OptionsStorage;
}

```

## disassembly

```asm
0x140001944  lea     rax, ?_OptionsStorage@?1??__local_stdio_printf_options@@9@4_KA; unsigned __int64 `__local_stdio_printf_options'::`2'::_OptionsStorage
0x14000194b  retn
```
