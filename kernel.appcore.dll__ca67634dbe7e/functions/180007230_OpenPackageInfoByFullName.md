# OpenPackageInfoByFullName

- ea: `0x180007230`
- end: `0x180007236`
- name: `OpenPackageInfoByFullName`
- size: `6`
- prototype: `LONG __stdcall(PCWSTR packageFullName, const UINT32 reserved, PACKAGE_INFO_REFERENCE *packageInfoReference)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `KERNELBASE!OpenPackageInfoByFullName` at `0x180007230`

## pseudocode

```c
// attributes: thunk
LONG __stdcall OpenPackageInfoByFullName(
        PCWSTR packageFullName,
        const UINT32 reserved,
        PACKAGE_INFO_REFERENCE *packageInfoReference)
{
  return __imp_OpenPackageInfoByFullName(packageFullName, reserved, packageInfoReference);
}

```

## disassembly

```asm
0x180007230  jmp     cs:__imp_OpenPackageInfoByFullName
```
