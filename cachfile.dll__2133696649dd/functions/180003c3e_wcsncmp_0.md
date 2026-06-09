# wcsncmp_0

- ea: `0x180003c3e`
- end: `0x180003c44`
- name: `wcsncmp_0`
- size: `6`
- prototype: `int __cdecl(const wchar_t *String1, const wchar_t *String2, size_t MaxCount)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180003b40`

## import_xrefs

- `msvcrt!wcsncmp` at `0x180003c3e`

## pseudocode

```c
// attributes: thunk
int __cdecl wcsncmp_0(const wchar_t *String1, const wchar_t *String2, size_t MaxCount)
{
  return wcsncmp(String1, String2, MaxCount);
}

```

## disassembly

```asm
0x180003c3e  jmp     cs:__imp_wcsncmp
```
