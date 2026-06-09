# AppPolicyGetThreadInitializationType

- ea: `0x180006930`
- end: `0x180006936`
- name: `AppPolicyGetThreadInitializationType`
- size: `6`
- prototype: `LONG __stdcall(HANDLE processToken, AppPolicyThreadInitializationType *policy)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `KERNELBASE!AppPolicyGetThreadInitializationType` at `0x180006930`

## pseudocode

```c
// attributes: thunk
LONG __stdcall AppPolicyGetThreadInitializationType(HANDLE processToken, AppPolicyThreadInitializationType *policy)
{
  return __imp_AppPolicyGetThreadInitializationType(processToken, policy);
}

```

## disassembly

```asm
0x180006930  jmp     cs:__imp_AppPolicyGetThreadInitializationType
```
