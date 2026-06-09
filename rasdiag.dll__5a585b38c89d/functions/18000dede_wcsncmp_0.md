# wcsncmp_0

- ea: `0x18000dede`
- end: `0x18000dee4`
- name: `wcsncmp_0`
- size: `6`
- prototype: `int __cdecl(const wchar_t *String1, const wchar_t *String2, size_t MaxCount)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x1800075e0`
- `0x180009440`
- `0x18000a710`
- `0x18000b610`
- `0x18000d720`

## import_xrefs

- `msvcrt!wcsncmp` at `0x18000dede`

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
0x18000dede  jmp     cs:__imp_wcsncmp
```
