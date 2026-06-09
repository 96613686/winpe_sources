# IsSideloadingPolicyApplied

- ea: `0x180007220`
- end: `0x180007226`
- name: `IsSideloadingPolicyApplied`
- size: `6`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, registry_config`

## import_xrefs

- `KERNELBASE!IsSideloadingPolicyApplied` at `0x180007220`

## pseudocode

```c
// attributes: thunk
__int64 IsSideloadingPolicyApplied()
{
  return __imp_IsSideloadingPolicyApplied();
}

```

## disassembly

```asm
0x180007220  jmp     cs:__imp_IsSideloadingPolicyApplied
```
