# CheckIsMSIXPackage

- ea: `0x180006a10`
- end: `0x180006a16`
- name: `CheckIsMSIXPackage`
- size: `6`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## import_xrefs

- `KERNELBASE!CheckIsMSIXPackage` at `0x180006a10`

## pseudocode

```c
// attributes: thunk
__int64 CheckIsMSIXPackage()
{
  return __imp_CheckIsMSIXPackage();
}

```

## disassembly

```asm
0x180006a10  jmp     cs:__imp_CheckIsMSIXPackage
```
