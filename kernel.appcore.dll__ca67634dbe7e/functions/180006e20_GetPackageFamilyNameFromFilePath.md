# GetPackageFamilyNameFromFilePath

- ea: `0x180006e20`
- end: `0x180006e26`
- name: `GetPackageFamilyNameFromFilePath`
- size: `6`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `KERNELBASE!GetPackageFamilyNameFromFilePath` at `0x180006e20`

## pseudocode

```c
// attributes: thunk
__int64 GetPackageFamilyNameFromFilePath()
{
  return __imp_GetPackageFamilyNameFromFilePath();
}

```

## disassembly

```asm
0x180006e20  jmp     cs:__imp_GetPackageFamilyNameFromFilePath
```
