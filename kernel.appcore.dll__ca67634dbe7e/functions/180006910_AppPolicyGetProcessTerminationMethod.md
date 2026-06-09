# AppPolicyGetProcessTerminationMethod

- ea: `0x180006910`
- end: `0x180006916`
- name: `AppPolicyGetProcessTerminationMethod`
- size: `6`
- prototype: `LONG __stdcall(HANDLE processToken, AppPolicyProcessTerminationMethod *policy)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `KERNELBASE!AppPolicyGetProcessTerminationMethod` at `0x180006910`

## pseudocode

```c
// attributes: thunk
LONG __stdcall AppPolicyGetProcessTerminationMethod(HANDLE processToken, AppPolicyProcessTerminationMethod *policy)
{
  return __imp_AppPolicyGetProcessTerminationMethod(processToken, policy);
}

```

## disassembly

```asm
0x180006910  jmp     cs:__imp_AppPolicyGetProcessTerminationMethod
```
