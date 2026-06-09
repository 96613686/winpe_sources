# GetPackageVolumeSisPath

- ea: `0x180006fe0`
- end: `0x180006fe6`
- name: `GetPackageVolumeSisPath`
- size: `6`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `KERNELBASE!GetPackageVolumeSisPath` at `0x180006fe0`

## pseudocode

```c
// attributes: thunk
__int64 GetPackageVolumeSisPath()
{
  return __imp_GetPackageVolumeSisPath();
}

```

## disassembly

```asm
0x180006fe0  jmp     cs:__imp_GetPackageVolumeSisPath
```
