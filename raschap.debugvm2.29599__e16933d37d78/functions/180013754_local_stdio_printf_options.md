# __local_stdio_printf_options

- ea: `0x180013754`
- end: `0x18001375c`
- name: `__local_stdio_printf_options`
- size: `8`
- prototype: `unsigned __int64 *__cdecl()`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x180013730`
- `0x180013780`
- `0x180013b44`
- `0x1800140b0`
- `0x18001461c`
- `0x180014670`
- `0x1800146d4`

## pseudocode

```c
unsigned __int64 *__cdecl _local_stdio_printf_options()
{
  return (unsigned __int64 *)&`__local_stdio_printf_options'::`2'::_OptionsStorage;
}

```

## disassembly

```asm
0x180013754  lea     rax, ?_OptionsStorage@?1??__local_stdio_printf_options@@9@4_KA; unsigned __int64 `__local_stdio_printf_options'::`2'::_OptionsStorage
0x18001375b  retn
```
