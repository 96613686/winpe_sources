# CDefaultAclCache::CanGetAcl(ushort const *)

- ea: `0x180033dd8`
- end: `0x180033fba`
- name: `?CanGetAcl@CDefaultAclCache@@QEAAHPEBG@Z`
- size: `482`
- prototype: `int(CDefaultAclCache *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800560c0`

## callees

- `0x180013220`
- `0x1800254e0`
- `0x180026370`
- `0x180033dd8`

## import_xrefs

- `SHELL32!SHGetFolderPathEx` at `0x180033ea2`
- `SHELL32!SHGetFolderPathEx` at `0x180033f0e`
- `SHELL32!SHGetFolderPathEx` at `0x180033ea2`
- `SHELL32!SHGetFolderPathEx` at `0x180033f0e`
- `SHELL32!__imp_PathIsEqualOrSubFolder` at `0x180033eb3`
- `SHELL32!__imp_PathIsEqualOrSubFolder` at `0x180033eb3`
- `SHLWAPI!PathRemoveFileSpecW` at `0x180033f65`
- `SHLWAPI!PathRemoveFileSpecW` at `0x180033f65`
- `SHLWAPI!PathIsRootW` at `0x180033e07`
- `SHLWAPI!PathIsRootW` at `0x180033e07`
- `SHLWAPI!__imp_StrCmpICW` at `0x180033f1f`
- `SHLWAPI!__imp_StrCmpICW` at `0x180033f7a`
- `SHLWAPI!__imp_StrCmpICW` at `0x180033f1f`
- `SHLWAPI!__imp_StrCmpICW` at `0x180033f7a`

## pseudocode

```c
__int64 __fastcall CDefaultAclCache::CanGetAcl(CDefaultAclCache *this, const unsigned __int16 *a2)
{
  unsigned int v3; // ebx
  unsigned int v4; // edi
  unsigned int v5; // esi
  unsigned int v6; // edi
  _OWORD v8[2]; // [rsp+30h] [rbp-D0h] BYREF
  _OWORD v9[8]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR pszStr1[264]; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR pszPath[264]; // [rsp+2E0h] [rbp+1E0h] BYREF

  if ( PathIsRootW(a2) )
  {
    return 0;
  }
  else
  {
    v3 = 1;
    v4 = 0;
    v9[0] = FOLDERID_System;
    v9[1] = FOLDERID_SystemX86;
    v9[2] = FOLDERID_Windows;
    v9[3] = FOLDERID_ProgramFiles;
    v9[4] = FOLDERID_ProgramFilesX86;
    v9[5] = FOLDERID_ProgramFilesCommon;
    v9[6] = FOLDERID_ProgramFilesCommonX86;
    v9[7] = FOLDERID_Public;
    do
    {
      if ( (int)SHGetFolderPathEx(&v9[v4], 0, 0, pszStr1, 260) >= 0 && (unsigned int)PathIsEqualOrSubFolder(pszStr1, a2) )
        v3 = 0;
      ++v4;
    }
    while ( v4 < 8 );
    if ( v3 )
    {
      v5 = 0;
      v8[0] = FOLDERID_UserProfiles;
      v8[1] = FOLDERID_Profile;
      do
      {
        if ( (int)SHGetFolderPathEx(&v8[v5], 0, 0, pszStr1, 260) >= 0 )
        {
          v6 = StrCmpICW(pszStr1, a2) != 0 ? v3 : 0;
          if ( v6 )
          {
            if ( !memcmp_0(&v8[v5], &FOLDERID_UserProfiles, 0x10u)
              && (int)StringCchCopyW(pszPath, 0x104u, a2) >= 0
              && PathRemoveFileSpecW(pszPath) )
            {
              v3 = StrCmpICW(pszStr1, pszPath) != 0 ? v6 : 0;
            }
            else
            {
              v3 = v6;
            }
          }
          else
          {
            v3 = 0;
          }
        }
        ++v5;
      }
      while ( v5 < 2 );
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180033dd8  push    rbp
0x180033dda  push    rbx
0x180033ddb  push    rsi
0x180033ddc  push    rdi
0x180033ddd  push    r14
0x180033ddf  push    r15
0x180033de1  lea     rbp, [rsp-408h]
0x180033de9  sub     rsp, 508h
0x180033df0  mov     rax, cs:__security_cookie
0x180033df7  xor     rax, rsp
0x180033dfa  mov     [rbp+430h+var_40], rax
0x180033e01  mov     rcx, rdx; pszPath
0x180033e04  mov     r14, rdx
0x180033e07  call    cs:__imp_PathIsRootW
0x180033e0d  test    eax, eax
0x180033e0f  jz      short loc_180033E18
0x180033e11  xor     ebx, ebx
0x180033e13  jmp     loc_180033F99
0x180033e18  movups  xmm0, xmmword ptr cs:FOLDERID_System.Data1
0x180033e1f  mov     ebx, 1
0x180033e24  xor     edi, edi
0x180033e26  movups  xmm1, xmmword ptr cs:FOLDERID_SystemX86.Data1
0x180033e2d  movdqu  [rsp+530h+var_4E0], xmm0
0x180033e33  movups  xmm0, xmmword ptr cs:FOLDERID_Windows.Data1
0x180033e3a  movdqu  [rsp+530h+var_4D0], xmm1
0x180033e40  movups  xmm1, xmmword ptr cs:FOLDERID_ProgramFiles.Data1
0x180033e47  movdqu  [rsp+530h+var_4C0], xmm0
0x180033e4d  movups  xmm0, xmmword ptr cs:FOLDERID_ProgramFilesX86.Data1
0x180033e54  movdqu  [rbp+430h+var_4B0], xmm1
0x180033e59  movups  xmm1, xmmword ptr cs:FOLDERID_ProgramFilesCommon.Data1
0x180033e60  movdqu  [rbp+430h+var_4A0], xmm0
0x180033e65  movups  xmm0, xmmword ptr cs:FOLDERID_ProgramFilesCommonX86.Data1
0x180033e6c  movdqu  [rbp+430h+var_490], xmm1
0x180033e71  movups  xmm1, xmmword ptr cs:FOLDERID_Public.Data1
0x180033e78  movdqu  [rbp+430h+var_480], xmm0
0x180033e7d  movdqu  [rbp+430h+var_470], xmm1
0x180033e82  movsxd  rax, edi
0x180033e85  lea     rcx, [rsp+530h+var_4E0]
0x180033e8a  shl     rax, 4
0x180033e8e  lea     r9, [rbp+430h+pszStr1]
0x180033e92  add     rcx, rax
0x180033e95  mov     [rsp+530h+var_510], 104h
0x180033e9d  xor     r8d, r8d
0x180033ea0  xor     edx, edx
0x180033ea2  call    cs:__imp_SHGetFolderPathEx
0x180033ea8  test    eax, eax
0x180033eaa  js      short loc_180033EC0
0x180033eac  mov     rdx, r14
0x180033eaf  lea     rcx, [rbp+430h+pszStr1]
0x180033eb3  call    cs:__imp_PathIsEqualOrSubFolder
0x180033eb9  xor     ecx, ecx
0x180033ebb  test    eax, eax
0x180033ebd  cmovnz  ebx, ecx
0x180033ec0  inc     edi
0x180033ec2  cmp     edi, 8
0x180033ec5  jb      short loc_180033E82
0x180033ec7  test    ebx, ebx
0x180033ec9  jz      loc_180033F99
0x180033ecf  movups  xmm0, xmmword ptr cs:FOLDERID_UserProfiles.Data1
0x180033ed6  xor     esi, esi
0x180033ed8  movups  xmm1, xmmword ptr cs:FOLDERID_Profile.Data1
0x180033edf  movdqu  [rsp+530h+var_500], xmm0
0x180033ee5  movdqu  [rsp+530h+var_4F0], xmm1
0x180033eeb  movsxd  rax, esi
0x180033eee  lea     r15, [rsp+530h+var_500]
0x180033ef3  shl     rax, 4
0x180033ef7  lea     r9, [rbp+430h+pszStr1]
0x180033efb  add     r15, rax
0x180033efe  mov     [rsp+530h+var_510], 104h
0x180033f06  mov     rcx, r15
0x180033f09  xor     r8d, r8d
0x180033f0c  xor     edx, edx
0x180033f0e  call    cs:__imp_SHGetFolderPathEx
0x180033f14  test    eax, eax
0x180033f16  js      short loc_180033F8E
0x180033f18  mov     rdx, r14; pszStr2
0x180033f1b  lea     rcx, [rbp+430h+pszStr1]; pszStr1
0x180033f1f  call    cs:__imp_StrCmpICW
0x180033f25  neg     eax
0x180033f27  sbb     edi, edi
0x180033f29  and     edi, ebx
0x180033f2b  jz      short loc_180033F8C
0x180033f2d  mov     r8d, 10h; Size
0x180033f33  lea     rdx, FOLDERID_UserProfiles; Buf2
0x180033f3a  mov     rcx, r15; Buf1
0x180033f3d  call    memcmp_0
0x180033f42  test    eax, eax
0x180033f44  jnz     short loc_180033F88
0x180033f46  mov     r8, r14; unsigned __int16 *
0x180033f49  lea     rcx, [rbp+430h+pszPath]; unsigned __int16 *
0x180033f50  mov     edx, 104h; unsigned __int64
0x180033f55  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180033f5a  test    eax, eax
0x180033f5c  js      short loc_180033F88
0x180033f5e  lea     rcx, [rbp+430h+pszPath]; pszPath
0x180033f65  call    cs:__imp_PathRemoveFileSpecW
0x180033f6b  test    eax, eax
0x180033f6d  jz      short loc_180033F88
0x180033f6f  lea     rdx, [rbp+430h+pszPath]; pszStr2
0x180033f76  lea     rcx, [rbp+430h+pszStr1]; pszStr1
0x180033f7a  call    cs:__imp_StrCmpICW
0x180033f80  neg     eax
0x180033f82  sbb     ebx, ebx
0x180033f84  and     ebx, edi
0x180033f86  jmp     short loc_180033F8E
0x180033f88  mov     ebx, edi
0x180033f8a  jmp     short loc_180033F8E
0x180033f8c  xor     ebx, ebx
0x180033f8e  inc     esi
0x180033f90  cmp     esi, 2
0x180033f93  jb      loc_180033EEB
0x180033f99  mov     eax, ebx
0x180033f9b  mov     rcx, [rbp+430h+var_40]
0x180033fa2  xor     rcx, rsp; StackCookie
0x180033fa5  call    __security_check_cookie
0x180033faa  add     rsp, 508h
0x180033fb1  pop     r15
0x180033fb3  pop     r14
0x180033fb5  pop     rdi
0x180033fb6  pop     rsi
0x180033fb7  pop     rbx
0x180033fb8  pop     rbp
0x180033fb9  retn
```
