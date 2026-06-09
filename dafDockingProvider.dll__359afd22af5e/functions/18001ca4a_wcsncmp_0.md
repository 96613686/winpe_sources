# wcsncmp_0

- ea: `0x18001ca4a`
- end: `0x18001ca50`
- name: `wcsncmp_0`
- size: `6`
- prototype: `int __cdecl(const wchar_t *String1, const wchar_t *String2, size_t MaxCount)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x18000d9b4`
- `0x18000dcd0`
- `0x18000e344`
- `0x180011994`
- `0x180011c2c`
- `0x1800129c4`
- `0x180016374`

## import_xrefs

- `msvcrt!wcsncmp` at `0x18001ca4a`

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
0x18001ca4a  jmp     cs:__imp_wcsncmp
```
