# _o___stdio_common_vsprintf_0

- ea: `0x140001bd2`
- end: `0x140001bd8`
- name: `_o___stdio_common_vsprintf_0`
- size: `6`
- prototype: `int __cdecl(unsigned __int64 Options, char *Buffer, size_t BufferCount, const char *Format, _locale_t Locale, va_list ArgList)`
- caller_count: `3`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140001dc0`
- `0x140001e14`
- `0x140001e7c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___stdio_common_vsprintf` at `0x140001bd2`

## pseudocode

```c
// attributes: thunk
int __cdecl o___stdio_common_vsprintf_0(
        unsigned __int64 Options,
        char *Buffer,
        size_t BufferCount,
        const char *Format,
        _locale_t Locale,
        va_list ArgList)
{
  return __stdio_common_vsprintf(Options, Buffer, BufferCount, Format, Locale, ArgList);
}

```

## disassembly

```asm
0x140001bd2  jmp     cs:__imp___stdio_common_vsprintf
```
