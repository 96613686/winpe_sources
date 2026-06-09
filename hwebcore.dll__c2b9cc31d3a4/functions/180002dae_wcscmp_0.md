# wcscmp_0

- ea: `0x180002dae`
- end: `0x180002db4`
- name: `wcscmp_0`
- size: `6`
- prototype: `int __cdecl(const wchar_t *String1, const wchar_t *String2)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x1800020b0`

## import_xrefs

- `msvcrt!wcscmp` at `0x180002dae`

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
0x180002dae  jmp     cs:__imp_wcscmp
```
