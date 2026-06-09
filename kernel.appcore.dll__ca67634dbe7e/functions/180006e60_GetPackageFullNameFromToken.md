# GetPackageFullNameFromToken

- ea: `0x180006e60`
- end: `0x180006e66`
- name: `GetPackageFullNameFromToken`
- size: `6`
- prototype: `LONG __stdcall(HANDLE token, UINT32 *packageFullNameLength, PWSTR packageFullName)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `KERNELBASE!GetPackageFullNameFromToken` at `0x180006e60`

## pseudocode

```c
// attributes: thunk
LONG __stdcall GetPackageFullNameFromToken(HANDLE token, UINT32 *packageFullNameLength, PWSTR packageFullName)
{
  return __imp_GetPackageFullNameFromToken(token, packageFullNameLength, packageFullName);
}

```

## disassembly

```asm
0x180006e60  jmp     cs:__imp_GetPackageFullNameFromToken
```
