# wcscmp_0

- ea: `0x18000ac5e`
- end: `0x18000ac64`
- name: `wcscmp_0`
- size: `6`
- prototype: `int __cdecl(const wchar_t *String1, const wchar_t *String2)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1800047a4`
- `0x180009948`

## import_xrefs

- `msvcrt!wcscmp` at `0x18000ac5e`

## pseudocode

```c
// attributes: thunk
int __cdecl wcscmp_0(const wchar_t *String1, const wchar_t *String2)
{
  return wcscmp(String1, String2);
}

```

## disassembly

```asm
0x18000ac5e  jmp     cs:__imp_wcscmp
```
