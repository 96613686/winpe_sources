# GetApplicationUserModelIdFromToken

- ea: `0x180006c00`
- end: `0x180006c06`
- name: `GetApplicationUserModelIdFromToken`
- size: `6`
- prototype: `LONG __stdcall(HANDLE token, UINT32 *applicationUserModelIdLength, PWSTR applicationUserModelId)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `KERNELBASE!GetApplicationUserModelIdFromToken` at `0x180006c00`

## pseudocode

```c
// attributes: thunk
LONG __stdcall GetApplicationUserModelIdFromToken(
        HANDLE token,
        UINT32 *applicationUserModelIdLength,
        PWSTR applicationUserModelId)
{
  return __imp_GetApplicationUserModelIdFromToken(token, applicationUserModelIdLength, applicationUserModelId);
}

```

## disassembly

```asm
0x180006c00  jmp     cs:__imp_GetApplicationUserModelIdFromToken
```
