# ___stdio_common_vswscanf

- ea: `0x1003b4ff`
- end: `0x1003b505`
- name: `___stdio_common_vswscanf`
- size: `6`
- prototype: `int __cdecl(unsigned __int64 Options, const wchar_t *Buffer, size_t BufferCount, const wchar_t *Format, _locale_t Locale, va_list ArgList)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1003b64d`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___stdio_common_vswscanf` at `0x1003b4ff`

## pseudocode

```c
// attributes: thunk
int __cdecl __stdio_common_vswscanf(
        unsigned __int64 Options,
        const wchar_t *Buffer,
        size_t BufferCount,
        const wchar_t *Format,
        _locale_t Locale,
        va_list ArgList)
{
  return ___stdio_common_vswscanf(Options, Buffer, BufferCount, Format, Locale, ArgList);
}

```

## disassembly

```asm
0x1003b4ff  jmp     ds:__imp____stdio_common_vswscanf
```
