# AppPolicyGetMediaFoundationCodecLoading

- ea: `0x180006900`
- end: `0x180006906`
- name: `AppPolicyGetMediaFoundationCodecLoading`
- size: `6`
- prototype: `LONG __stdcall(HANDLE processToken, AppPolicyMediaFoundationCodecLoading *policy)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `KERNELBASE!AppPolicyGetMediaFoundationCodecLoading` at `0x180006900`

## pseudocode

```c
// attributes: thunk
LONG __stdcall AppPolicyGetMediaFoundationCodecLoading(
        HANDLE processToken,
        AppPolicyMediaFoundationCodecLoading *policy)
{
  return __imp_AppPolicyGetMediaFoundationCodecLoading(processToken, policy);
}

```

## disassembly

```asm
0x180006900  jmp     cs:__imp_AppPolicyGetMediaFoundationCodecLoading
```
