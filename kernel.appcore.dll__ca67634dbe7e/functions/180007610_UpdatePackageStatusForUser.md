# UpdatePackageStatusForUser

- ea: `0x180007610`
- end: `0x180007616`
- name: `UpdatePackageStatusForUser`
- size: `6`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## import_xrefs

- `KERNELBASE!UpdatePackageStatusForUser` at `0x180007610`

## pseudocode

```c
// attributes: thunk
__int64 UpdatePackageStatusForUser()
{
  return __imp_UpdatePackageStatusForUser();
}

```

## disassembly

```asm
0x180007610  jmp     cs:__imp_UpdatePackageStatusForUser
```
