# AppPolicyGetLifecycleManagement

- ea: `0x1800068f0`
- end: `0x1800068f6`
- name: `AppPolicyGetLifecycleManagement`
- size: `6`
- prototype: `LONG __stdcall(HANDLE processToken, AppPolicyLifecycleManagement *policy)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `KERNELBASE!AppPolicyGetLifecycleManagement` at `0x1800068f0`

## pseudocode

```c
// attributes: thunk
LONG __stdcall AppPolicyGetLifecycleManagement(HANDLE processToken, AppPolicyLifecycleManagement *policy)
{
  return __imp_AppPolicyGetLifecycleManagement(processToken, policy);
}

```

## disassembly

```asm
0x1800068f0  jmp     cs:__imp_AppPolicyGetLifecycleManagement
```
