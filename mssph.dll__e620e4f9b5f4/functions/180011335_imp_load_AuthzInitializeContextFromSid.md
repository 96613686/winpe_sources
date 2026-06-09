# __imp_load_AuthzInitializeContextFromSid

- ea: `0x180011335`
- end: `0x180011341`
- name: `__imp_load_AuthzInitializeContextFromSid`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, installer_update`

## callees

- `0x180010d27`

## import_xrefs

- `AUTHZ!AuthzInitializeContextFromSid` at `0x180011335`

## pseudocode

```c
__int64 load_AuthzInitializeContextFromSid()
{
  return _tailMerge_authz_dll();
}

```

## disassembly

```asm
0x180011335  lea     rax, __imp_AuthzInitializeContextFromSid
0x18001133c  jmp     __tailMerge_authz_dll
```
