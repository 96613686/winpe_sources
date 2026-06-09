# GetSystemMetadataPath

- ea: `0x180007160`
- end: `0x180007166`
- name: `GetSystemMetadataPath`
- size: `6`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `KERNELBASE!GetSystemMetadataPath` at `0x180007160`

## pseudocode

```c
// attributes: thunk
__int64 GetSystemMetadataPath()
{
  return __imp_GetSystemMetadataPath();
}

```

## disassembly

```asm
0x180007160  jmp     cs:__imp_GetSystemMetadataPath
```
