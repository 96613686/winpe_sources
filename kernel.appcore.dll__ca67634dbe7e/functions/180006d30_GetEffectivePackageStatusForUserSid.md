# GetEffectivePackageStatusForUserSid

- ea: `0x180006d30`
- end: `0x180006d36`
- name: `GetEffectivePackageStatusForUserSid`
- size: `6`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation`

## import_xrefs

- `KERNELBASE!GetEffectivePackageStatusForUserSid` at `0x180006d30`

## pseudocode

```c
// attributes: thunk
__int64 GetEffectivePackageStatusForUserSid()
{
  return __imp_GetEffectivePackageStatusForUserSid();
}

```

## disassembly

```asm
0x180006d30  jmp     cs:__imp_GetEffectivePackageStatusForUserSid
```
