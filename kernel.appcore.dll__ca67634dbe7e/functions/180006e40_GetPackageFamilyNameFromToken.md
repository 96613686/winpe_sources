# GetPackageFamilyNameFromToken

- ea: `0x180006e40`
- end: `0x180006e46`
- name: `GetPackageFamilyNameFromToken`
- size: `6`
- prototype: `LONG __stdcall(HANDLE token, UINT32 *packageFamilyNameLength, PWSTR packageFamilyName)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `KERNELBASE!GetPackageFamilyNameFromToken` at `0x180006e40`

## pseudocode

```c
// attributes: thunk
LONG __stdcall GetPackageFamilyNameFromToken(HANDLE token, UINT32 *packageFamilyNameLength, PWSTR packageFamilyName)
{
  return __imp_GetPackageFamilyNameFromToken(token, packageFamilyNameLength, packageFamilyName);
}

```

## disassembly

```asm
0x180006e40  jmp     cs:__imp_GetPackageFamilyNameFromToken
```
