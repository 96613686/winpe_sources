# GetPackagePathOnVolume

- ea: `0x180006f30`
- end: `0x180006f36`
- name: `GetPackagePathOnVolume`
- size: `6`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `KERNELBASE!GetPackagePathOnVolume` at `0x180006f30`

## pseudocode

```c
// attributes: thunk
__int64 GetPackagePathOnVolume()
{
  return __imp_GetPackagePathOnVolume();
}

```

## disassembly

```asm
0x180006f30  jmp     cs:__imp_GetPackagePathOnVolume
```
