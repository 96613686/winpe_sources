# wcsncmp_0

- ea: `0x180008bca`
- end: `0x180008bd0`
- name: `wcsncmp_0`
- size: `6`
- prototype: `int __cdecl(const wchar_t *String1, const wchar_t *String2, size_t MaxCount)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x1800063f0`
- `0x180007660`
- `0x1800081b0`

## import_xrefs

- `msvcrt!wcsncmp` at `0x180008bca`

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
0x180008bca  jmp     cs:__imp_wcsncmp
```
