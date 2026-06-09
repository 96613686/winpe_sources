# _o___stdio_common_vfprintf_0

- ea: `0x18002131a`
- end: `0x180021320`
- name: `_o___stdio_common_vfprintf_0`
- size: `6`
- prototype: `int __cdecl(unsigned __int64 Options, FILE *Stream, const char *Format, _locale_t Locale, va_list ArgList)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800216d8`
- `0x180021724`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___stdio_common_vfprintf` at `0x18002131a`

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
0x18002131a  jmp     cs:__imp___stdio_common_vfprintf
```
