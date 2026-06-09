# JetLoadLibraryW(x)

- ea: `0x10032dda`
- end: `0x10032de5`
- name: `_JetLoadLibraryW@4`
- size: `11`
- prototype: `int __thiscall(LPCWSTR lpLibFileName)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1001e690`

## callees

- `0x10032d47`

## pseudocode

```c
HMODULE __thiscall JetLoadLibraryW(LPCWSTR lpLibFileName)
{
  return JetLoadLibraryExW(lpLibFileName, 0, 0);
}

```

## disassembly

```asm
0x10032dda  push    0; int
0x10032ddc  push    0; hFile
0x10032dde  push    ecx; lpLibFileName
0x10032ddf  call    _JetLoadLibraryExW@12; JetLoadLibraryExW(x,x,x)
0x10032de4  retn
```
