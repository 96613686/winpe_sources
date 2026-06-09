# GetSystemMetadataPathForPackageFamily

- ea: `0x180007180`
- end: `0x180007186`
- name: `GetSystemMetadataPathForPackageFamily`
- size: `6`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `KERNELBASE!GetSystemMetadataPathForPackageFamily` at `0x180007180`

## pseudocode

```c
// attributes: thunk
__int64 GetSystemMetadataPathForPackageFamily()
{
  return __imp_GetSystemMetadataPathForPackageFamily();
}

```

## disassembly

```asm
0x180007180  jmp     cs:__imp_GetSystemMetadataPathForPackageFamily
```
