# OpenPackageInfoByFullNameForUser

- ea: `0x180007250`
- end: `0x180007256`
- name: `OpenPackageInfoByFullNameForUser`
- size: `6`
- prototype: `LONG __stdcall(PSID userSid, PCWSTR packageFullName, const UINT32 reserved, PACKAGE_INFO_REFERENCE *packageInfoReference)`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation`

## import_xrefs

- `KERNELBASE!OpenPackageInfoByFullNameForUser` at `0x180007250`

## pseudocode

```c
// attributes: thunk
LONG __stdcall OpenPackageInfoByFullNameForUser(
        PSID userSid,
        PCWSTR packageFullName,
        const UINT32 reserved,
        PACKAGE_INFO_REFERENCE *packageInfoReference)
{
  return __imp_OpenPackageInfoByFullNameForUser(userSid, packageFullName, reserved, packageInfoReference);
}

```

## disassembly

```asm
0x180007250  jmp     cs:__imp_OpenPackageInfoByFullNameForUser
```
