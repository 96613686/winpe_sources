# __imp_load_AuthzAccessCheck

- ea: `0x180013944`
- end: `0x180013950`
- name: `__imp_load_AuthzAccessCheck`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x18001388f`

## import_xrefs

- `AUTHZ!AuthzAccessCheck` at `0x180013944`

## pseudocode

```c
__int64 load_AuthzAccessCheck()
{
  return _tailMerge_authz_dll();
}

```

## disassembly

```asm
0x180013944  lea     rax, __imp_AuthzAccessCheck
0x18001394b  jmp     __tailMerge_authz_dll
```
