# __stdio_common_vswprintf_s

- ea: `0x1400039f6`
- end: `0x1400039fc`
- name: `__stdio_common_vswprintf_s`
- size: `6`
- prototype: `int __cdecl(unsigned __int64 Options, wchar_t *Buffer, size_t BufferCount, const wchar_t *Format, _locale_t Locale, va_list ArgList)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140003bc4`
- `0x140003c28`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___stdio_common_vswprintf_s` at `0x1400039f6`

## pseudocode

```c
// attributes: thunk
int __cdecl _stdio_common_vswprintf_s(
        unsigned __int64 Options,
        wchar_t *Buffer,
        size_t BufferCount,
        const wchar_t *Format,
        _locale_t Locale,
        va_list ArgList)
{
  return _o___stdio_common_vswprintf_s(Options, Buffer, BufferCount, Format, Locale, ArgList);
}

```

## disassembly

```asm
0x1400039f6  jmp     cs:__imp__o___stdio_common_vswprintf_s
```
