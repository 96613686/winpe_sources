# __imp_load_AuthzInitializeContextFromSid

- ea: `0x180013932`
- end: `0x18001393e`
- name: `__imp_load_AuthzInitializeContextFromSid`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, installer_update`

## callees

- `0x18001388f`

## import_xrefs

- `AUTHZ!AuthzInitializeContextFromSid` at `0x180013932`

## pseudocode

```c
__int64 load_AuthzInitializeContextFromSid()
{
  return _tailMerge_authz_dll();
}

```

## disassembly

```asm
0x180013932  lea     rax, __imp_AuthzInitializeContextFromSid
0x180013939  jmp     __tailMerge_authz_dll
```
