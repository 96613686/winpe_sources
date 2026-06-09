# __local_stdio_printf_options

- ea: `0x180001b94`
- end: `0x180001b9c`
- name: `__local_stdio_printf_options`
- size: `8`
- prototype: `unsigned __int64 *__cdecl()`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180001b70`
- `0x180001bc0`
- `0x180002450`
- `0x1800028e8`
- `0x18000293c`

## pseudocode

```c
unsigned __int64 *__cdecl _local_stdio_printf_options()
{
  return (unsigned __int64 *)&`__local_stdio_printf_options'::`2'::_OptionsStorage;
}

```

## disassembly

```asm
0x180001b94  lea     rax, ?_OptionsStorage@?1??__local_stdio_printf_options@@9@4_KA; unsigned __int64 `__local_stdio_printf_options'::`2'::_OptionsStorage
0x180001b9b  retn
```
