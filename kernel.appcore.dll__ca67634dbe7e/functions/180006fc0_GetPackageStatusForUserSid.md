# GetPackageStatusForUserSid

- ea: `0x180006fc0`
- end: `0x180006fc6`
- name: `GetPackageStatusForUserSid`
- size: `6`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation`

## import_xrefs

- `KERNELBASE!GetPackageStatusForUserSid` at `0x180006fc0`

## pseudocode

```c
// attributes: thunk
__int64 GetPackageStatusForUserSid()
{
  return __imp_GetPackageStatusForUserSid();
}

```

## disassembly

```asm
0x180006fc0  jmp     cs:__imp_GetPackageStatusForUserSid
```
