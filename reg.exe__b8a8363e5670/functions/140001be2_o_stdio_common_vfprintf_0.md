# _o___stdio_common_vfprintf_0

- ea: `0x140001be2`
- end: `0x140001be8`
- name: `_o___stdio_common_vfprintf_0`
- size: `6`
- prototype: `int __cdecl(unsigned __int64 Options, FILE *Stream, const char *Format, _locale_t Locale, va_list ArgList)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140001d28`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___stdio_common_vfprintf` at `0x140001be2`

## pseudocode

```c
// attributes: thunk
int __cdecl o___stdio_common_vfprintf_0(
        unsigned __int64 Options,
        FILE *Stream,
        const char *Format,
        _locale_t Locale,
        va_list ArgList)
{
  return __stdio_common_vfprintf(Options, Stream, Format, Locale, ArgList);
}

```

## disassembly

```asm
0x140001be2  jmp     cs:__imp___stdio_common_vfprintf
```
