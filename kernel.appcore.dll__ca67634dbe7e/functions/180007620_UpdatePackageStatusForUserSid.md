# UpdatePackageStatusForUserSid

- ea: `0x180007620`
- end: `0x180007626`
- name: `UpdatePackageStatusForUserSid`
- size: `6`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, installer_update`

## import_xrefs

- `KERNELBASE!UpdatePackageStatusForUserSid` at `0x180007620`

## pseudocode

```c
// attributes: thunk
__int64 UpdatePackageStatusForUserSid()
{
  return __imp_UpdatePackageStatusForUserSid();
}

```

## disassembly

```asm
0x180007620  jmp     cs:__imp_UpdatePackageStatusForUserSid
```
