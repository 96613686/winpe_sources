# DsRolepValidatePath

- ea: `0x18000e118`
- end: `0x18000e2f6`
- name: `DsRolepValidatePath`
- size: `478`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, int, _DWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180003994`

## callees

- `0x180009020`
- `0x18000e118`
- `0x180020dbc`
- `0x18002c050`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000e289`
- `msvcrt!_wcsicmp` at `0x18000e2ab`
- `msvcrt!_wcsicmp` at `0x18000e289`
- `msvcrt!_wcsicmp` at `0x18000e2ab`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x18000e254`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x18000e254`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x18000e1ed`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x18000e1ed`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000e16c`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000e16c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e177`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e25e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e177`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e25e`

## string_xrefs

- `0x18000e14e`: `Validating path %ws.\n`
- `0x18000e1a3`: `	Path is a directory\n`
- `0x18000e1af`: `	Path is a NOT directory\n`
- `0x18000e1fb`: `	Path is on a fixed disk drive.\n`
- `0x18000e207`: `	Path is NOT on a fixed disk drive.\n`
- `0x18000e271`: `	Can't determine if path is on an NTFS volume.\n`
- `0x18000e296`: `	Path is on an NTFS volume\n`
- `0x18000e2b8`: `	Path is on an ReFS volume\n`
- `0x18000e2c1`: `	Path is NOT on an NTFS or ReFS volume\n`

## pseudocode

```c
__int64 __fastcall DsRolepValidatePath(STRSAFE_PCNZWCH pszSrc, int a2, _DWORD *a3)
{
  DWORD LastError; // edi
  size_t *v7; // r8
  DWORD FileAttributesW; // eax
  const char *v9; // rdx
  __int64 v10; // rcx
  DWORD FileSystemFlags; // [rsp+40h] [rbp-48h] BYREF
  DWORD MaximumComponentLength; // [rsp+44h] [rbp-44h] BYREF
  wchar_t pszDest[4]; // [rsp+48h] [rbp-40h] BYREF
  WCHAR FileSystemNameBuffer[8]; // [rsp+50h] [rbp-38h] BYREF

  LastError = 0;
  FileSystemFlags = 0;
  MaximumComponentLength = 0;
  DsRolepLogPrintRoutine(4, "Validating path %ws.\n", pszSrc);
  *a3 = 0;
  if ( (a2 & 1) != 0 )
  {
    FileAttributesW = GetFileAttributesW(pszSrc);
    if ( FileAttributesW == -1 )
    {
      LastError = GetLastError();
      DsRolepLogPrintRoutine(1, "\tCan't get file attributes (%lu)\n", LastError);
      if ( LastError )
        return LastError;
    }
    else if ( (FileAttributesW & 0x10) != 0 )
    {
      *a3 |= 1u;
      DsRolepLogPrintRoutine(4, "\tPath is a directory\n");
    }
    else
    {
      DsRolepLogPrintRoutine(2, "\tPath is a NOT directory\n");
    }
  }
  StringCopyWorkerW(pszDest, 4u, v7, pszSrc, 3u);
  pszDest[3] = 0;
  if ( (a2 & 2) != 0 )
  {
    if ( GetDriveTypeW(pszDest) == 3 )
    {
      *a3 |= 2u;
      DsRolepLogPrintRoutine(4, "\tPath is on a fixed disk drive.\n");
    }
    else
    {
      DsRolepLogPrintRoutine(2, "\tPath is NOT on a fixed disk drive.\n");
    }
  }
  if ( (a2 & 4) != 0 )
  {
    if ( GetVolumeInformationW(pszDest, 0, 0, 0, &MaximumComponentLength, &FileSystemFlags, FileSystemNameBuffer, 6u) )
    {
      if ( _wcsicmp(FileSystemNameBuffer, L"NTFS") )
      {
        if ( _wcsicmp(FileSystemNameBuffer, L"REFS") )
        {
          v9 = "\tPath is NOT on an NTFS or ReFS volume\n";
          v10 = 2;
          goto LABEL_23;
        }
        *a3 |= 4u;
        v9 = "\tPath is on an ReFS volume\n";
      }
      else
      {
        *a3 |= 4u;
        v9 = "\tPath is on an NTFS volume\n";
      }
    }
    else
    {
      LastError = GetLastError();
      if ( *a3 != (a2 & 0xFFFFFFFB) )
        return 0;
      v9 = "\tCan't determine if path is on an NTFS volume.\n";
    }
    v10 = 4;
LABEL_23:
    DsRolepLogPrintRoutine(v10, v9);
  }
  return LastError;
}

```

## disassembly

```asm
0x18000e118  mov     [rsp+arg_8], rbx
0x18000e11d  mov     [rsp+arg_18], rbp
0x18000e122  push    rsi
0x18000e123  push    rdi
0x18000e124  push    r14
0x18000e126  sub     rsp, 70h
0x18000e12a  mov     rax, cs:__security_cookie
0x18000e131  xor     rax, rsp
0x18000e134  mov     [rsp+88h+var_28], rax
0x18000e139  xor     edi, edi
0x18000e13b  mov     rbx, r8
0x18000e13e  mov     esi, edx
0x18000e140  mov     [rsp+88h+FileSystemFlags], edi
0x18000e144  mov     rbp, rcx
0x18000e147  mov     [rsp+88h+MaximumComponentLength], edi
0x18000e14b  mov     r8, rcx
0x18000e14e  lea     rdx, aValidatingPath; "Validating path %ws.\n"
0x18000e155  lea     r14d, [rdi+4]
0x18000e159  mov     ecx, r14d
0x18000e15c  call    DsRolepLogPrintRoutine
0x18000e161  mov     [rbx], edi
0x18000e163  test    sil, 1
0x18000e167  jz      short loc_18000E1C0
0x18000e169  mov     rcx, rbp; lpFileName
0x18000e16c  call    cs:__imp_GetFileAttributesW
0x18000e172  cmp     eax, 0FFFFFFFFh
0x18000e175  jnz     short loc_18000E19C
0x18000e177  call    cs:__imp_GetLastError
0x18000e17d  mov     r8d, eax
0x18000e180  lea     rdx, aCanTGetFileAtt; "\tCan't get file attributes (%lu)\n"
0x18000e187  lea     ecx, [r14-3]
0x18000e18b  mov     edi, eax
0x18000e18d  call    DsRolepLogPrintRoutine
0x18000e192  test    edi, edi
0x18000e194  jnz     loc_18000E2D2
0x18000e19a  jmp     short loc_18000E1C0
0x18000e19c  test    al, 10h
0x18000e19e  jz      short loc_18000E1AF
0x18000e1a0  or      dword ptr [rbx], 1
0x18000e1a3  lea     rdx, aPathIsADirecto; "\tPath is a directory\n"
0x18000e1aa  mov     ecx, r14d
0x18000e1ad  jmp     short loc_18000E1BB
0x18000e1af  lea     rdx, aPathIsANotDire; "\tPath is a NOT directory\n"
0x18000e1b6  mov     ecx, 2
0x18000e1bb  call    DsRolepLogPrintRoutine
0x18000e1c0  mov     r9, rbp; pszSrc
0x18000e1c3  mov     [rsp+88h+cchToCopy], 3; cchToCopy
0x18000e1cc  mov     rdx, r14; cchDest
0x18000e1cf  lea     rcx, [rsp+88h+pszDest]; pszDest
0x18000e1d4  call    StringCopyWorkerW
0x18000e1d9  xor     r11d, r11d
0x18000e1dc  mov     [rsp+88h+var_3A], r11w
0x18000e1e2  test    sil, 2
0x18000e1e6  jz      short loc_18000E218
0x18000e1e8  lea     rcx, [rsp+88h+pszDest]; lpRootPathName
0x18000e1ed  call    cs:__imp_GetDriveTypeW
0x18000e1f3  cmp     eax, 3
0x18000e1f6  jnz     short loc_18000E207
0x18000e1f8  or      dword ptr [rbx], 2
0x18000e1fb  lea     rdx, aPathIsOnAFixed; "\tPath is on a fixed disk drive.\n"
0x18000e202  mov     ecx, r14d
0x18000e205  jmp     short loc_18000E213
0x18000e207  lea     rdx, aPathIsNotOnAFi; "\tPath is NOT on a fixed disk drive.\n"
0x18000e20e  mov     ecx, 2
0x18000e213  call    DsRolepLogPrintRoutine
0x18000e218  test    r14b, sil
0x18000e21b  jz      loc_18000E2D2
0x18000e221  mov     [rsp+88h+nFileSystemNameSize], 6; nFileSystemNameSize
0x18000e229  lea     rax, [rsp+88h+FileSystemNameBuffer]
0x18000e22e  mov     [rsp+88h+lpFileSystemNameBuffer], rax; lpFileSystemNameBuffer
0x18000e233  lea     rcx, [rsp+88h+pszDest]; lpRootPathName
0x18000e238  lea     rax, [rsp+88h+FileSystemFlags]
0x18000e23d  xor     r9d, r9d; lpVolumeSerialNumber
0x18000e240  mov     [rsp+88h+lpFileSystemFlags], rax; lpFileSystemFlags
0x18000e245  xor     r8d, r8d; nVolumeNameSize
0x18000e248  lea     rax, [rsp+88h+MaximumComponentLength]
0x18000e24d  xor     edx, edx; lpVolumeNameBuffer
0x18000e24f  mov     [rsp+88h+cchToCopy], rax; lpMaximumComponentLength
0x18000e254  call    cs:__imp_GetVolumeInformationW
0x18000e25a  test    eax, eax
0x18000e25c  jnz     short loc_18000E27D
0x18000e25e  call    cs:__imp_GetLastError
0x18000e264  and     esi, 0FFFFFFFBh
0x18000e267  mov     edi, eax
0x18000e269  cmp     [rbx], esi
0x18000e26b  jz      short loc_18000E271
0x18000e26d  xor     edi, edi
0x18000e26f  jmp     short loc_18000E2D2
0x18000e271  lea     rdx, aCanTDetermineI; "\tCan't determine if path is on an NTFS"...
0x18000e278  mov     ecx, r14d
0x18000e27b  jmp     short loc_18000E2CD
0x18000e27d  lea     rdx, aNtfs; "NTFS"
0x18000e284  lea     rcx, [rsp+88h+FileSystemNameBuffer]; String1
0x18000e289  call    cs:__imp__wcsicmp
0x18000e28f  test    eax, eax
0x18000e291  jnz     short loc_18000E29F
0x18000e293  or      [rbx], r14d
0x18000e296  lea     rdx, aPathIsOnAnNtfs; "\tPath is on an NTFS volume\n"
0x18000e29d  jmp     short loc_18000E278
0x18000e29f  lea     rdx, aRefs; "REFS"
0x18000e2a6  lea     rcx, [rsp+88h+FileSystemNameBuffer]; String1
0x18000e2ab  call    cs:__imp__wcsicmp
0x18000e2b1  test    eax, eax
0x18000e2b3  jnz     short loc_18000E2C1
0x18000e2b5  or      [rbx], r14d
0x18000e2b8  lea     rdx, aPathIsOnAnRefs; "\tPath is on an ReFS volume\n"
0x18000e2bf  jmp     short loc_18000E278
0x18000e2c1  lea     rdx, aPathIsNotOnAnN; "\tPath is NOT on an NTFS or ReFS volume"...
0x18000e2c8  mov     ecx, 2
0x18000e2cd  call    DsRolepLogPrintRoutine
0x18000e2d2  mov     eax, edi
0x18000e2d4  mov     rcx, [rsp+88h+var_28]
0x18000e2d9  xor     rcx, rsp; StackCookie
0x18000e2dc  call    __security_check_cookie
0x18000e2e1  lea     r11, [rsp+88h+var_18]
0x18000e2e6  mov     rbx, [r11+28h]
0x18000e2ea  mov     rbp, [r11+38h]
0x18000e2ee  mov     rsp, r11
0x18000e2f1  pop     r14
0x18000e2f3  pop     rdi
0x18000e2f4  pop     rsi
0x18000e2f5  retn
```
