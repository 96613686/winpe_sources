# RemovePackageStatusForUser

- ea: `0x1800074f0`
- end: `0x1800074f6`
- name: `RemovePackageStatusForUser`
- size: `6`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `KERNELBASE!RemovePackageStatusForUser` at `0x1800074f0`

## pseudocode

```c
// attributes: thunk
__int64 RemovePackageStatusForUser()
{
  return __imp_RemovePackageStatusForUser();
}

```

## disassembly

```asm
0x1800074f0  jmp     cs:__imp_RemovePackageStatusForUser
```
