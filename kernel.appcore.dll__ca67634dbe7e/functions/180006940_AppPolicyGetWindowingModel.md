# AppPolicyGetWindowingModel

- ea: `0x180006940`
- end: `0x180006946`
- name: `AppPolicyGetWindowingModel`
- size: `6`
- prototype: `LONG __stdcall(HANDLE processToken, AppPolicyWindowingModel *policy)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `KERNELBASE!AppPolicyGetWindowingModel` at `0x180006940`

## pseudocode

```c
// attributes: thunk
LONG __stdcall AppPolicyGetWindowingModel(HANDLE processToken, AppPolicyWindowingModel *policy)
{
  return __imp_AppPolicyGetWindowingModel(processToken, policy);
}

```

## disassembly

```asm
0x180006940  jmp     cs:__imp_AppPolicyGetWindowingModel
```
