# DoesVolumeSupportSecurity(ushort const *)

- ea: `0x180072ae4`
- end: `0x180072baf`
- name: `?DoesVolumeSupportSecurity@@YAHPEBG@Z`
- size: `203`
- prototype: `__int64 __fastcall(LPCWSTR lpszFileName)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180045440`
- `0x18005a2c8`
- `0x18005bf4c`
- `0x180063ca0`
- `0x180063ef0`

## callees

- `0x1800254e0`
- `0x180072ae4`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x180072b3e`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x180072b3e`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x180072b7c`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x180072b7c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180072b11`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180072b11`

## pseudocode

```c
_BOOL8 __fastcall DoesVolumeSupportSecurity(LPCWSTR lpszFileName)
{
  const WCHAR *v1; // rbx
  UINT SystemDirectoryW; // eax
  WCHAR *v3; // rdx
  DWORD FileSystemFlags[4]; // [rsp+40h] [rbp-448h] BYREF
  WCHAR Buffer[264]; // [rsp+50h] [rbp-438h] BYREF
  WCHAR szVolumePathName[264]; // [rsp+260h] [rbp-228h] BYREF

  v1 = lpszFileName;
  if ( !lpszFileName )
  {
    SystemDirectoryW = GetSystemDirectoryW(Buffer, 0x104u);
    v3 = Buffer;
    if ( !SystemDirectoryW )
      v3 = 0;
    v1 = v3;
  }
  FileSystemFlags[0] = 0;
  return GetVolumePathNameW(v1, szVolumePathName, 0x104u)
      && GetVolumeInformationW(szVolumePathName, 0, 0, 0, 0, FileSystemFlags, 0, 0)
      && (FileSystemFlags[0] & 8) != 0;
}

```

## disassembly

```asm
0x180072ae4  push    rbx
0x180072ae6  sub     rsp, 480h
0x180072aed  mov     rax, cs:__security_cookie
0x180072af4  xor     rax, rsp
0x180072af7  mov     [rsp+488h+var_18], rax
0x180072aff  mov     rbx, rcx
0x180072b02  test    rcx, rcx
0x180072b05  jnz     short loc_180072B25
0x180072b07  mov     edx, 104h; uSize
0x180072b0c  lea     rcx, [rsp+488h+Buffer]; lpBuffer
0x180072b11  call    cs:__imp_GetSystemDirectoryW
0x180072b17  test    eax, eax
0x180072b19  lea     rdx, [rsp+488h+Buffer]
0x180072b1e  cmovz   rdx, rbx
0x180072b22  mov     rbx, rdx
0x180072b25  mov     r8d, 104h; cchBufferLength
0x180072b2b  mov     [rsp+488h+FileSystemFlags], 0
0x180072b33  lea     rdx, [rsp+488h+szVolumePathName]; lpszVolumePathName
0x180072b3b  mov     rcx, rbx; lpszFileName
0x180072b3e  call    cs:__imp_GetVolumePathNameW
0x180072b44  test    eax, eax
0x180072b46  jz      short loc_180072B94
0x180072b48  mov     [rsp+488h+nFileSystemNameSize], 0; nFileSystemNameSize
0x180072b50  lea     rax, [rsp+488h+FileSystemFlags]
0x180072b55  mov     [rsp+488h+lpFileSystemNameBuffer], 0; lpFileSystemNameBuffer
0x180072b5e  lea     rcx, [rsp+488h+szVolumePathName]; lpRootPathName
0x180072b66  mov     [rsp+488h+lpFileSystemFlags], rax; lpFileSystemFlags
0x180072b6b  xor     r9d, r9d; lpVolumeSerialNumber
0x180072b6e  xor     r8d, r8d; nVolumeNameSize
0x180072b71  mov     [rsp+488h+lpMaximumComponentLength], 0; lpMaximumComponentLength
0x180072b7a  xor     edx, edx; lpVolumeNameBuffer
0x180072b7c  call    cs:__imp_GetVolumeInformationW
0x180072b82  test    eax, eax
0x180072b84  jz      short loc_180072B94
0x180072b86  test    byte ptr [rsp+488h+FileSystemFlags], 8
0x180072b8b  jz      short loc_180072B94
0x180072b8d  mov     eax, 1
0x180072b92  jmp     short loc_180072B96
0x180072b94  xor     eax, eax
0x180072b96  mov     rcx, [rsp+488h+var_18]
0x180072b9e  xor     rcx, rsp; StackCookie
0x180072ba1  call    __security_check_cookie
0x180072ba6  add     rsp, 480h
0x180072bad  pop     rbx
0x180072bae  retn
```
