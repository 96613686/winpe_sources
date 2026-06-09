# __imp_load_AuthzAccessCheck

- ea: `0x180014ad4`
- end: `0x180014ae0`
- name: `__imp_load_AuthzAccessCheck`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180014a55`

## import_xrefs

- `AUTHZ!AuthzAccessCheck` at `0x180014ad4`

## pseudocode

```c
__int64 load_AuthzAccessCheck()
{
  return _tailMerge_authz_dll();
}

```

## disassembly

```asm
0x180014ad4  lea     rax, __imp_AuthzAccessCheck
0x180014adb  jmp     __tailMerge_authz_dll
```
