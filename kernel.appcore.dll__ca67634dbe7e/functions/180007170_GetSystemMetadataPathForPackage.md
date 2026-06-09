# GetSystemMetadataPathForPackage

- ea: `0x180007170`
- end: `0x180007176`
- name: `GetSystemMetadataPathForPackage`
- size: `6`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `KERNELBASE!GetSystemMetadataPathForPackage` at `0x180007170`

## pseudocode

```c
// attributes: thunk
__int64 GetSystemMetadataPathForPackage()
{
  return __imp_GetSystemMetadataPathForPackage();
}

```

## disassembly

```asm
0x180007170  jmp     cs:__imp_GetSystemMetadataPathForPackage
```
