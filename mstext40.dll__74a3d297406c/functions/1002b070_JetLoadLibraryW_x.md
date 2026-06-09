# JetLoadLibraryW(x)

- ea: `0x1002b070`
- end: `0x1002b080`
- name: `_JetLoadLibraryW@4`
- size: `16`
- prototype: `int __stdcall(LPCWSTR lpLibFileName)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1000ddd0`
- `0x1001cb30`

## callees

- `0x1002afa0`

## pseudocode

```c
HMODULE __stdcall JetLoadLibraryW(LPCWSTR lpLibFileName)
{
  return JetLoadLibraryExW(lpLibFileName, 0, 0);
}

```

## disassembly

```asm
0x1002b070  push    0; int
0x1002b072  push    0; hFile
0x1002b074  push    [esp+8+lpLibFileName]; lpLibFileName
0x1002b078  call    _JetLoadLibraryExW@12; JetLoadLibraryExW(x,x,x)
0x1002b07d  retn    4
```
