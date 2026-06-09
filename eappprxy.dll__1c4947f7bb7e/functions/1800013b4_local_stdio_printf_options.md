# __local_stdio_printf_options

- ea: `0x1800013b4`
- end: `0x1800013bc`
- name: `__local_stdio_printf_options`
- size: `8`
- prototype: `unsigned __int64 *__cdecl()`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180001390`
- `0x1800013e0`
- `0x180001c6c`
- `0x1800021e8`
- `0x18000223c`

## pseudocode

```c
unsigned __int64 *__cdecl _local_stdio_printf_options()
{
  return (unsigned __int64 *)&`__local_stdio_printf_options'::`2'::_OptionsStorage;
}

```

## disassembly

```asm
0x1800013b4  lea     rax, ?_OptionsStorage@?1??__local_stdio_printf_options@@9@4_KA; unsigned __int64 `__local_stdio_printf_options'::`2'::_OptionsStorage
0x1800013bb  retn
```
