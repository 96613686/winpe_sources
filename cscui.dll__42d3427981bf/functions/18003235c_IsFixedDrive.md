# IsFixedDrive

- ea: `0x18003235c`
- end: `0x1800323b7`
- name: `IsFixedDrive`
- size: `91`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180006c94`

## callees

- `0x18003235c`
- `0x18004c670`

## import_xrefs

- `SHLWAPI!PathGetDriveNumberW` at `0x18003236f`
- `SHLWAPI!PathGetDriveNumberW` at `0x18003236f`
- `SHLWAPI!PathBuildRootW` at `0x180032381`
- `SHLWAPI!PathBuildRootW` at `0x180032381`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x180032391`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x180032391`

## pseudocode

```c
_BOOL8 __fastcall IsFixedDrive(const WCHAR *a1)
{
  int DriveNumberW; // eax
  WCHAR pszRoot; // [rsp+20h] [rbp-18h] BYREF

  DriveNumberW = PathGetDriveNumberW(a1);
  return DriveNumberW != -1 && PathBuildRootW(&pszRoot, DriveNumberW) && GetDriveTypeW(&pszRoot) == 3;
}

```

## disassembly

```asm
0x18003235c  sub     rsp, 38h
0x180032360  mov     rax, cs:__security_cookie
0x180032367  xor     rax, rsp
0x18003236a  mov     [rsp+38h+var_10], rax
0x18003236f  call    cs:__imp_PathGetDriveNumberW
0x180032375  cmp     eax, 0FFFFFFFFh
0x180032378  jz      short loc_1800323A3
0x18003237a  mov     edx, eax; iDrive
0x18003237c  lea     rcx, [rsp+38h+pszRoot]; pszRoot
0x180032381  call    cs:__imp_PathBuildRootW
0x180032387  test    rax, rax
0x18003238a  jz      short loc_1800323A3
0x18003238c  lea     rcx, [rsp+38h+pszRoot]; lpRootPathName
0x180032391  call    cs:__imp_GetDriveTypeW
0x180032397  cmp     eax, 3
0x18003239a  jnz     short loc_1800323A3
0x18003239c  mov     eax, 1
0x1800323a1  jmp     short loc_1800323A5
0x1800323a3  xor     eax, eax
0x1800323a5  mov     rcx, [rsp+38h+var_10]
0x1800323aa  xor     rcx, rsp; StackCookie
0x1800323ad  call    __security_check_cookie
0x1800323b2  add     rsp, 38h
0x1800323b6  retn
```
