# FwLoggerCreateLogFilesAsCaller

- ea: `0x18005b220`
- end: `0x18005b716`
- name: `FwLoggerCreateLogFilesAsCaller`
- size: `1270`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180007484`
- `0x180094570`

## callees

- `0x18000af3c`
- `0x180017110`
- `0x18005b220`
- `0x18006f520`
- `0x18007150c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b471`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b4e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b578`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b636`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b684`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b471`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b4e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b578`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b636`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005b684`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005b529`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005b667`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005b529`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005b667`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18005b4d3`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18005b62a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18005b4d3`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18005b62a`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18005b357`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18005b357`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x18005b51e`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x18005b51e`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x18005b39a`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x18005b39a`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18005b417`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18005b5f7`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18005b417`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18005b5f7`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveFileSpecW` at `0x18005b40d`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveFileSpecW` at `0x18005b40d`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x18005b56e`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x18005b67a`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x18005b56e`
- `api-ms-win-security-base-l1-1-0!SetFileSecurityW` at `0x18005b67a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005b6ce`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005b6ce`
- `RPCRT4!RpcRevertToSelf` at `0x18005b6bf`
- `RPCRT4!RpcRevertToSelf` at `0x18005b6bf`
- `RPCRT4!RpcImpersonateClient` at `0x18005b29a`
- `RPCRT4!RpcImpersonateClient` at `0x18005b29a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18005b467`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18005b467`
- `ext-ms-win-shell-shlwapi-l1-1-0!PathIsDirectoryW` at `0x18005b320`
- `ext-ms-win-shell-shlwapi-l1-1-0!PathIsDirectoryW` at `0x18005b320`
- `fwbase!FwExpandEnvironmentStrings` at `0x18005b2e0`
- `fwbase!FwExpandEnvironmentStrings` at `0x18005b2e0`
- `fwbase!FwCreateDirectory` at `0x18005b425`
- `fwbase!FwCreateDirectory` at `0x18005b425`
- `fwbase!FwStringBuild` at `0x18005b5c3`
- `fwbase!FwStringBuild` at `0x18005b5c3`
- `fwbase!FwStringCopy` at `0x18005b3d9`
- `fwbase!FwStringCopy` at `0x18005b3d9`
- `fwbase!FwFree` at `0x18005b6d8`
- `fwbase!FwFree` at `0x18005b6e2`
- `fwbase!FwFree` at `0x18005b6ec`
- `fwbase!FwFree` at `0x18005b6d8`
- `fwbase!FwFree` at `0x18005b6e2`
- `fwbase!FwFree` at `0x18005b6ec`

## pseudocode

```c
__int64 __fastcall FwLoggerCreateLogFilesAsCaller(__int64 a1)
{
  RPC_STATUS v2; // eax
  unsigned int v3; // ebx
  int Directory; // eax
  __int64 v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // r9
  DWORD FileAttributesW; // eax
  signed int LastError; // eax
  HANDLE FileW; // rax
  void *v11; // rdi
  signed int v12; // eax
  DWORD FileType; // ebx
  signed int v14; // eax
  HANDLE v15; // rax
  signed int v16; // eax
  signed int v17; // eax
  LPCWSTR pszPath; // [rsp+40h] [rbp-30h] BYREF
  LPWSTR v20; // [rsp+48h] [rbp-28h] BYREF
  LPCWSTR lpFileName; // [rsp+50h] [rbp-20h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+58h] [rbp-18h] BYREF

  SecurityDescriptor = 0;
  pszPath = 0;
  lpFileName = 0;
  v20 = 0;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 52, WPP_3d59fee1d00932d8b651bda1e8e67a3f_Traceguids);
  v2 = RpcImpersonateClient(0);
  v3 = v2;
  if ( v2 >= 0 )
  {
    Directory = FwExpandEnvironmentStrings(a1, &pszPath);
    v3 = Directory;
    if ( Directory < 0 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_78;
      v6 = 54;
      goto LABEL_12;
    }
    if ( (unsigned __int8)IsPathIsDirectoryWPresent() )
    {
      if ( PathIsDirectoryW(pszPath) )
      {
        v7 = 2147942487LL;
        v3 = -2147024809;
        v5 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_78;
        v6 = 55;
        goto LABEL_77;
      }
    }
    else
    {
      FileAttributesW = GetFileAttributesW(pszPath);
      if ( FileAttributesW - 1 <= 0xFFFFFFFD && (FileAttributesW & 0x10) != 0 )
      {
        v7 = 2147942487LL;
        v3 = -2147024809;
        v5 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_78;
        v6 = 56;
        goto LABEL_77;
      }
    }
    if ( PathIsRelativeW(pszPath) )
    {
      v7 = 2147942487LL;
      v3 = -2147024809;
      v5 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_78;
      v6 = 57;
      goto LABEL_77;
    }
    Directory = FwStringCopy(pszPath, &v20);
    v3 = Directory;
    if ( Directory < 0 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_78;
      v6 = 58;
      goto LABEL_12;
    }
    PathRemoveFileSpecW(v20);
    if ( !PathFileExistsW(v20) )
    {
      Directory = FwCreateDirectory(v20);
      v3 = Directory;
      if ( Directory < 0 )
      {
        v5 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_78;
        v6 = 59;
        goto LABEL_12;
      }
    }
    if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
            L"D:PAI(A;;FA;;;S-1-5-80-3088073201-1464728630-1879813800-1107566885-823218052)(A;;FA;;;SY)(A;;FA;;;BA)(A;;FA;;;NO)",
            1u,
            &SecurityDescriptor,
            0) )
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
      v5 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_78;
      v6 = 60;
      goto LABEL_76;
    }
    FileW = CreateFileW(pszPath, 0x80000000, 3u, 0, 4u, 0x80u, 0);
    v11 = FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      v12 = GetLastError();
      v3 = v12;
      if ( v12 > 0 )
        v3 = (unsigned __int16)v12 | 0x80070000;
      v5 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_78;
      v6 = 61;
      goto LABEL_76;
    }
    FileType = GetFileType(FileW);
    CloseHandle(v11);
    if ( FileType != 1 )
    {
      v7 = 2147942487LL;
      v3 = -2147024809;
      v5 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_78;
      v6 = 62;
      goto LABEL_77;
    }
    if ( !SetFileSecurityW(pszPath, 4u, SecurityDescriptor) )
    {
      v14 = GetLastError();
      v3 = v14;
      if ( v14 > 0 )
        v3 = (unsigned __int16)v14 | 0x80070000;
      v5 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_78;
      v6 = 63;
      goto LABEL_76;
    }
    Directory = FwStringBuild(&lpFileName, pszPath, L".old", 0);
    v3 = Directory;
    if ( Directory < 0 )
    {
      v5 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_78;
      v6 = 64;
LABEL_12:
      v7 = (unsigned int)Directory;
LABEL_77:
      WPP_SF_d(*(_QWORD *)(v5 + 16), v6, WPP_3d59fee1d00932d8b651bda1e8e67a3f_Traceguids, v7);
LABEL_78:
      RpcRevertToSelf();
      goto LABEL_79;
    }
    if ( !PathFileExistsW(lpFileName) )
    {
      v15 = CreateFileW(lpFileName, 0x80000000, 3u, 0, 4u, 0x80u, 0);
      if ( v15 == (HANDLE)-1LL )
      {
        v16 = GetLastError();
        v3 = v16;
        if ( v16 > 0 )
          v3 = (unsigned __int16)v16 | 0x80070000;
        v5 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
          goto LABEL_78;
        v6 = 65;
        goto LABEL_76;
      }
      CloseHandle(v15);
    }
    if ( SetFileSecurityW(lpFileName, 4u, SecurityDescriptor) )
      goto LABEL_78;
    v17 = GetLastError();
    v3 = v17;
    if ( v17 > 0 )
      v3 = (unsigned __int16)v17 | 0x80070000;
    v5 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
      goto LABEL_78;
    v6 = 66;
LABEL_76:
    v7 = v3;
    goto LABEL_77;
  }
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    WPP_SF_d(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      53,
      WPP_3d59fee1d00932d8b651bda1e8e67a3f_Traceguids,
      (unsigned int)v2);
LABEL_79:
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  FwFree(pszPath);
  FwFree(v20);
  FwFree(lpFileName);
  return v3;
}

```

## disassembly

```asm
0x18005b220  mov     [rsp-18h+arg_8], rbx
0x18005b225  mov     [rsp-18h+arg_10], rdi
0x18005b22a  push    rbp
0x18005b22b  push    r14
0x18005b22d  push    r15
0x18005b22f  mov     rbp, rsp
0x18005b232  sub     rsp, 70h
0x18005b236  mov     rax, cs:__security_cookie
0x18005b23d  xor     rax, rsp
0x18005b240  mov     [rbp+var_10], rax
0x18005b244  mov     rdi, rcx
0x18005b247  mov     [rbp+SecurityDescriptor], 0
0x18005b24f  mov     [rbp+pszPath], 0
0x18005b257  mov     [rbp+lpFileName], 0
0x18005b25f  mov     [rbp+var_28], 0
0x18005b267  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b26e  lea     r14, WPP_GLOBAL_Control
0x18005b275  lea     r15, WPP_3d59fee1d00932d8b651bda1e8e67a3f_Traceguids
0x18005b27c  cmp     rcx, r14
0x18005b27f  jz      short loc_18005B298
0x18005b281  test    byte ptr [rcx+1Ch], 8
0x18005b285  jz      short loc_18005B298
0x18005b287  mov     rcx, [rcx+10h]
0x18005b28b  mov     edx, 34h ; '4'
0x18005b290  mov     r8, r15
0x18005b293  call    WPP_SF_
0x18005b298  xor     ecx, ecx; BindingHandle
0x18005b29a  call    cs:__imp_RpcImpersonateClient
0x18005b2a0  mov     ebx, eax
0x18005b2a2  test    eax, eax
0x18005b2a4  jns     short loc_18005B2D9
0x18005b2a6  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b2ad  cmp     rcx, r14
0x18005b2b0  jz      loc_18005B6C5
0x18005b2b6  test    byte ptr [rcx+1Ch], 1
0x18005b2ba  jz      loc_18005B6C5
0x18005b2c0  mov     rcx, [rcx+10h]
0x18005b2c4  mov     edx, 35h ; '5'
0x18005b2c9  mov     r9d, eax
0x18005b2cc  mov     r8, r15
0x18005b2cf  call    WPP_SF_d
0x18005b2d4  jmp     loc_18005B6C5
0x18005b2d9  lea     rdx, [rbp+pszPath]
0x18005b2dd  mov     rcx, rdi
0x18005b2e0  call    cs:__imp_FwExpandEnvironmentStrings
0x18005b2e6  mov     ebx, eax
0x18005b2e8  test    eax, eax
0x18005b2ea  jns     short loc_18005B313
0x18005b2ec  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b2f3  cmp     rcx, r14
0x18005b2f6  jz      loc_18005B6BF
0x18005b2fc  test    byte ptr [rcx+1Ch], 1
0x18005b300  jz      loc_18005B6BF
0x18005b306  mov     edx, 36h ; '6'
0x18005b30b  mov     r9d, eax
0x18005b30e  jmp     loc_18005B6B3
0x18005b313  call    IsPathIsDirectoryWPresent
0x18005b318  mov     rcx, [rbp+pszPath]; lpFileName
0x18005b31c  test    al, al
0x18005b31e  jz      short loc_18005B357
0x18005b320  call    cs:__imp_PathIsDirectoryW
0x18005b326  test    eax, eax
0x18005b328  jz      short loc_18005B396
0x18005b32a  mov     r9d, 80070057h
0x18005b330  mov     ebx, r9d
0x18005b333  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b33a  cmp     rcx, r14
0x18005b33d  jz      loc_18005B6BF
0x18005b343  test    byte ptr [rcx+1Ch], 1
0x18005b347  jz      loc_18005B6BF
0x18005b34d  mov     edx, 37h ; '7'
0x18005b352  jmp     loc_18005B6B3
0x18005b357  call    cs:__imp_GetFileAttributesW
0x18005b35d  lea     ecx, [rax-1]
0x18005b360  cmp     ecx, 0FFFFFFFDh
0x18005b363  ja      short loc_18005B396
0x18005b365  test    al, 10h
0x18005b367  jz      short loc_18005B396
0x18005b369  mov     r9d, 80070057h
0x18005b36f  mov     ebx, r9d
0x18005b372  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b379  cmp     rcx, r14
0x18005b37c  jz      loc_18005B6BF
0x18005b382  test    byte ptr [rcx+1Ch], 1
0x18005b386  jz      loc_18005B6BF
0x18005b38c  mov     edx, 38h ; '8'
0x18005b391  jmp     loc_18005B6B3
0x18005b396  mov     rcx, [rbp+pszPath]; pszPath
0x18005b39a  call    cs:__imp_PathIsRelativeW
0x18005b3a0  test    eax, eax
0x18005b3a2  jz      short loc_18005B3D1
0x18005b3a4  mov     r9d, 80070057h
0x18005b3aa  mov     ebx, r9d
0x18005b3ad  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b3b4  cmp     rcx, r14
0x18005b3b7  jz      loc_18005B6BF
0x18005b3bd  test    byte ptr [rcx+1Ch], 1
0x18005b3c1  jz      loc_18005B6BF
0x18005b3c7  mov     edx, 39h ; '9'
0x18005b3cc  jmp     loc_18005B6B3
0x18005b3d1  mov     rcx, [rbp+pszPath]
0x18005b3d5  lea     rdx, [rbp+var_28]
0x18005b3d9  call    cs:__imp_FwStringCopy
0x18005b3df  mov     ebx, eax
0x18005b3e1  test    eax, eax
0x18005b3e3  jns     short loc_18005B409
0x18005b3e5  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b3ec  cmp     rcx, r14
0x18005b3ef  jz      loc_18005B6BF
0x18005b3f5  test    byte ptr [rcx+1Ch], 1
0x18005b3f9  jz      loc_18005B6BF
0x18005b3ff  mov     edx, 3Ah ; ':'
0x18005b404  jmp     loc_18005B30B
0x18005b409  mov     rcx, [rbp+var_28]; pszPath
0x18005b40d  call    cs:__imp_PathRemoveFileSpecW
0x18005b413  mov     rcx, [rbp+var_28]; pszPath
0x18005b417  call    cs:__imp_PathFileExistsW
0x18005b41d  test    eax, eax
0x18005b41f  jnz     short loc_18005B455
0x18005b421  mov     rcx, [rbp+var_28]
0x18005b425  call    cs:__imp_FwCreateDirectory
0x18005b42b  mov     ebx, eax
0x18005b42d  test    eax, eax
0x18005b42f  jns     short loc_18005B455
0x18005b431  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b438  cmp     rcx, r14
0x18005b43b  jz      loc_18005B6BF
0x18005b441  test    byte ptr [rcx+1Ch], 1
0x18005b445  jz      loc_18005B6BF
0x18005b44b  mov     edx, 3Bh ; ';'
0x18005b450  jmp     loc_18005B30B
0x18005b455  xor     r9d, r9d; SecurityDescriptorSize
0x18005b458  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18005b45c  lea     rcx, aDPaiAFaS158030; "D:PAI(A;;FA;;;S-1-5-80-3088073201-14647"...
0x18005b463  lea     edx, [r9+1]; StringSDRevision
0x18005b467  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18005b46d  test    eax, eax
0x18005b46f  jnz     short loc_18005B4AA
0x18005b471  call    cs:__imp_GetLastError
0x18005b477  mov     ebx, eax
0x18005b479  test    eax, eax
0x18005b47b  jle     short loc_18005B486
0x18005b47d  movzx   ebx, ax
0x18005b480  or      ebx, 80070000h
0x18005b486  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b48d  cmp     rcx, r14
0x18005b490  jz      loc_18005B6BF
0x18005b496  test    byte ptr [rcx+1Ch], 1
0x18005b49a  jz      loc_18005B6BF
0x18005b4a0  mov     edx, 3Ch ; '<'
0x18005b4a5  jmp     loc_18005B6B0
0x18005b4aa  mov     rcx, [rbp+pszPath]; lpFileName
0x18005b4ae  xor     r9d, r9d; lpSecurityAttributes
0x18005b4b1  mov     [rsp+70h+hTemplateFile], 0; hTemplateFile
0x18005b4ba  mov     edx, 80000000h; dwDesiredAccess
0x18005b4bf  mov     [rsp+70h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18005b4c7  mov     [rsp+70h+dwCreationDisposition], 4; dwCreationDisposition
0x18005b4cf  lea     r8d, [r9+3]; dwShareMode
0x18005b4d3  call    cs:__imp_CreateFileW
0x18005b4d9  mov     rdi, rax
0x18005b4dc  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18005b4e0  jnz     short loc_18005B51B
0x18005b4e2  call    cs:__imp_GetLastError
0x18005b4e8  mov     ebx, eax
0x18005b4ea  test    eax, eax
0x18005b4ec  jle     short loc_18005B4F7
0x18005b4ee  movzx   ebx, ax
0x18005b4f1  or      ebx, 80070000h
0x18005b4f7  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b4fe  cmp     rcx, r14
0x18005b501  jz      loc_18005B6BF
0x18005b507  test    byte ptr [rcx+1Ch], 1
0x18005b50b  jz      loc_18005B6BF
0x18005b511  mov     edx, 3Dh ; '='
0x18005b516  jmp     loc_18005B6B0
0x18005b51b  mov     rcx, rdi; hFile
0x18005b51e  call    cs:__imp_GetFileType
0x18005b524  mov     rcx, rdi; hObject
0x18005b527  mov     ebx, eax
0x18005b529  call    cs:__imp_CloseHandle
0x18005b52f  cmp     ebx, 1
0x18005b532  jz      short loc_18005B561
0x18005b534  mov     r9d, 80070057h
0x18005b53a  mov     ebx, r9d
0x18005b53d  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b544  cmp     rcx, r14
0x18005b547  jz      loc_18005B6BF
0x18005b54d  test    byte ptr [rcx+1Ch], 1
0x18005b551  jz      loc_18005B6BF
0x18005b557  mov     edx, 3Eh ; '>'
0x18005b55c  jmp     loc_18005B6B3
0x18005b561  mov     r8, [rbp+SecurityDescriptor]; pSecurityDescriptor
0x18005b565  mov     edx, 4; SecurityInformation
0x18005b56a  mov     rcx, [rbp+pszPath]; lpFileName
0x18005b56e  call    cs:__imp_SetFileSecurityW
0x18005b574  test    eax, eax
0x18005b576  jnz     short loc_18005B5B1
0x18005b578  call    cs:__imp_GetLastError
0x18005b57e  mov     ebx, eax
0x18005b580  test    eax, eax
0x18005b582  jle     short loc_18005B58D
0x18005b584  movzx   ebx, ax
0x18005b587  or      ebx, 80070000h
0x18005b58d  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b594  cmp     rcx, r14
0x18005b597  jz      loc_18005B6BF
0x18005b59d  test    byte ptr [rcx+1Ch], 1
0x18005b5a1  jz      loc_18005B6BF
0x18005b5a7  mov     edx, 3Fh ; '?'
0x18005b5ac  jmp     loc_18005B6B0
0x18005b5b1  mov     rdx, [rbp+pszPath]
0x18005b5b5  lea     r8, aOld; ".old"
0x18005b5bc  xor     r9d, r9d
0x18005b5bf  lea     rcx, [rbp+lpFileName]
0x18005b5c3  call    cs:__imp_FwStringBuild
0x18005b5c9  mov     ebx, eax
0x18005b5cb  test    eax, eax
0x18005b5cd  jns     short loc_18005B5F3
0x18005b5cf  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b5d6  cmp     rcx, r14
0x18005b5d9  jz      loc_18005B6BF
0x18005b5df  test    byte ptr [rcx+1Ch], 1
0x18005b5e3  jz      loc_18005B6BF
0x18005b5e9  mov     edx, 40h ; '@'
0x18005b5ee  jmp     loc_18005B30B
0x18005b5f3  mov     rcx, [rbp+lpFileName]; pszPath
0x18005b5f7  call    cs:__imp_PathFileExistsW
0x18005b5fd  test    eax, eax
0x18005b5ff  jnz     short loc_18005B66D
0x18005b601  mov     rcx, [rbp+lpFileName]; lpFileName
0x18005b605  lea     r8d, [rax+3]; dwShareMode
0x18005b609  mov     [rsp+70h+hTemplateFile], 0; hTemplateFile
0x18005b612  xor     r9d, r9d; lpSecurityAttributes
0x18005b615  mov     [rsp+70h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18005b61d  mov     edx, 80000000h; dwDesiredAccess
0x18005b622  mov     [rsp+70h+dwCreationDisposition], 4; dwCreationDisposition
0x18005b62a  call    cs:__imp_CreateFileW
0x18005b630  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18005b634  jnz     short loc_18005B664
0x18005b636  call    cs:__imp_GetLastError
0x18005b63c  mov     ebx, eax
0x18005b63e  test    eax, eax
0x18005b640  jle     short loc_18005B64B
0x18005b642  movzx   ebx, ax
0x18005b645  or      ebx, 80070000h
0x18005b64b  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b652  cmp     rcx, r14
0x18005b655  jz      short loc_18005B6BF
0x18005b657  test    byte ptr [rcx+1Ch], 1
0x18005b65b  jz      short loc_18005B6BF
0x18005b65d  mov     edx, 41h ; 'A'
0x18005b662  jmp     short loc_18005B6B0
0x18005b664  mov     rcx, rax; hObject
0x18005b667  call    cs:__imp_CloseHandle
0x18005b66d  mov     r8, [rbp+SecurityDescriptor]; pSecurityDescriptor
0x18005b671  mov     edx, 4; SecurityInformation
0x18005b676  mov     rcx, [rbp+lpFileName]; lpFileName
0x18005b67a  call    cs:__imp_SetFileSecurityW
0x18005b680  test    eax, eax
0x18005b682  jnz     short loc_18005B6BF
0x18005b684  call    cs:__imp_GetLastError
0x18005b68a  mov     ebx, eax
0x18005b68c  test    eax, eax
0x18005b68e  jle     short loc_18005B699
0x18005b690  movzx   ebx, ax
0x18005b693  or      ebx, 80070000h
0x18005b699  mov     rcx, cs:WPP_GLOBAL_Control
0x18005b6a0  cmp     rcx, r14
0x18005b6a3  jz      short loc_18005B6BF
0x18005b6a5  test    byte ptr [rcx+1Ch], 1
0x18005b6a9  jz      short loc_18005B6BF
0x18005b6ab  mov     edx, 42h ; 'B'
0x18005b6b0  mov     r9d, ebx
0x18005b6b3  mov     rcx, [rcx+10h]
0x18005b6b7  mov     r8, r15
0x18005b6ba  call    WPP_SF_d
0x18005b6bf  call    cs:__imp_RpcRevertToSelf
0x18005b6c5  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x18005b6c9  test    rcx, rcx
0x18005b6cc  jz      short loc_18005B6D4
0x18005b6ce  call    cs:__imp_LocalFree
0x18005b6d4  mov     rcx, [rbp+pszPath]
0x18005b6d8  call    cs:__imp_FwFree
0x18005b6de  mov     rcx, [rbp+var_28]
0x18005b6e2  call    cs:__imp_FwFree
0x18005b6e8  mov     rcx, [rbp+lpFileName]
0x18005b6ec  call    cs:__imp_FwFree
0x18005b6f2  mov     eax, ebx
0x18005b6f4  mov     rcx, [rbp+var_10]
0x18005b6f8  xor     rcx, rsp; StackCookie
0x18005b6fb  call    __security_check_cookie
0x18005b700  lea     r11, [rsp+70h+var_s0]
0x18005b705  mov     rbx, [r11+28h]
0x18005b709  mov     rdi, [r11+30h]
0x18005b70d  mov     rsp, r11
0x18005b710  pop     r15
0x18005b712  pop     r14
0x18005b714  pop     rbp
0x18005b715  retn
```
