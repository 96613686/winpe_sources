# AppPolicyGetClrCompat

- ea: `0x1800068d0`
- end: `0x1800068d6`
- name: `AppPolicyGetClrCompat`
- size: `6`
- prototype: `LONG __stdcall(HANDLE processToken, AppPolicyClrCompat *policy)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## import_xrefs

- `KERNELBASE!AppPolicyGetClrCompat` at `0x1800068d0`

## pseudocode

```c
// attributes: thunk
LONG __stdcall AppPolicyGetClrCompat(HANDLE processToken, AppPolicyClrCompat *policy)
{
  return __imp_AppPolicyGetClrCompat(processToken, policy);
}

```

## disassembly

```asm
0x1800068d0  jmp     cs:__imp_AppPolicyGetClrCompat
```
