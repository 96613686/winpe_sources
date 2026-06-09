# __o___stdio_common_vswprintf

- ea: `0x1005f0ac`
- end: `0x1005f0b2`
- name: `__o___stdio_common_vswprintf`
- size: `6`
- prototype: `int __cdecl(unsigned __int64 Options, wchar_t *Buffer, size_t BufferCount, const wchar_t *Format, _locale_t Locale, va_list ArgList)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1005f1a4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o___stdio_common_vswprintf` at `0x1005f0ac`

## pseudocode

```c
// attributes: thunk
int __cdecl _o___stdio_common_vswprintf(
        unsigned __int64 Options,
        wchar_t *Buffer,
        size_t BufferCount,
        const wchar_t *Format,
        _locale_t Locale,
        va_list ArgList)
{
  return ___stdio_common_vswprintf(Options, Buffer, BufferCount, Format, Locale, ArgList);
}

```

## disassembly

```asm
0x1005f0ac  jmp     ds:__imp____stdio_common_vswprintf
```
