# AppPolicyGetShowDeveloperDiagnostic

- ea: `0x180006920`
- end: `0x180006926`
- name: `AppPolicyGetShowDeveloperDiagnostic`
- size: `6`
- prototype: `LONG __stdcall(HANDLE processToken, AppPolicyShowDeveloperDiagnostic *policy)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `KERNELBASE!AppPolicyGetShowDeveloperDiagnostic` at `0x180006920`

## pseudocode

```c
// attributes: thunk
LONG __stdcall AppPolicyGetShowDeveloperDiagnostic(HANDLE processToken, AppPolicyShowDeveloperDiagnostic *policy)
{
  return __imp_AppPolicyGetShowDeveloperDiagnostic(processToken, policy);
}

```

## disassembly

```asm
0x180006920  jmp     cs:__imp_AppPolicyGetShowDeveloperDiagnostic
```
