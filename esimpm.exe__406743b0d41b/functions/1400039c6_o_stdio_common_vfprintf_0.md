# _o___stdio_common_vfprintf_0

- ea: `0x1400039c6`
- end: `0x1400039cc`
- name: `_o___stdio_common_vfprintf_0`
- size: `6`
- prototype: `int __cdecl(unsigned __int64 Options, FILE *Stream, const char *Format, _locale_t Locale, va_list ArgList)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140003cf8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___stdio_common_vfprintf` at `0x1400039c6`

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
0x1400039c6  jmp     cs:__imp___stdio_common_vfprintf
```
