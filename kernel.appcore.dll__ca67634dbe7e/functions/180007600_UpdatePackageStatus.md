# UpdatePackageStatus

- ea: `0x180007600`
- end: `0x180007606`
- name: `UpdatePackageStatus`
- size: `6`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## import_xrefs

- `KERNELBASE!UpdatePackageStatus` at `0x180007600`

## pseudocode

```c
// attributes: thunk
__int64 UpdatePackageStatus()
{
  return __imp_UpdatePackageStatus();
}

```

## disassembly

```asm
0x180007600  jmp     cs:__imp_UpdatePackageStatus
```
