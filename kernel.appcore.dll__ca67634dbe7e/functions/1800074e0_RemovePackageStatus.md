# RemovePackageStatus

- ea: `0x1800074e0`
- end: `0x1800074e6`
- name: `RemovePackageStatus`
- size: `6`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `KERNELBASE!RemovePackageStatus` at `0x1800074e0`

## pseudocode

```c
// attributes: thunk
__int64 RemovePackageStatus()
{
  return __imp_RemovePackageStatus();
}

```

## disassembly

```asm
0x1800074e0  jmp     cs:__imp_RemovePackageStatus
```
