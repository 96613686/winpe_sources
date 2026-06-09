# AppPolicyGetCreateFileAccess

- ea: `0x1800068e0`
- end: `0x1800068e6`
- name: `AppPolicyGetCreateFileAccess`
- size: `6`
- prototype: `LONG __stdcall(HANDLE processToken, AppPolicyCreateFileAccess *policy)`
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops, registry_config`

## import_xrefs

- `KERNELBASE!AppPolicyGetCreateFileAccess` at `0x1800068e0`

## pseudocode

```c
// attributes: thunk
LONG __stdcall AppPolicyGetCreateFileAccess(HANDLE processToken, AppPolicyCreateFileAccess *policy)
{
  return __imp_AppPolicyGetCreateFileAccess(processToken, policy);
}

```

## disassembly

```asm
0x1800068e0  jmp     cs:__imp_AppPolicyGetCreateFileAccess
```
