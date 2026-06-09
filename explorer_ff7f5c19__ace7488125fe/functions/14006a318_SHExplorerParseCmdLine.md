# SHExplorerParseCmdLine

- ea: `0x14006a318`
- end: `0x14006a719`
- name: `SHExplorerParseCmdLine`
- size: `1025`
- prototype: `__int64 __fastcall(unsigned __int16 *, LPITEMIDLIST *ppidl)`
- caller_count: `2`
- callee_count: `8`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x14006a074`
- `0x1400a3f04`

## callees

- `0x140033ec0`
- `0x140069b04`
- `0x14006a318`
- `0x14006a720`
- `0x14006a778`
- `0x14010e160`
- `0x140114014`
- `0x140114164`

## import_xrefs

- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x14006a398`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x14006a3bc`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x14006a3e1`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x14006a406`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x14006a4f8`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x14006a525`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x14006a54a`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x14006a56a`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x14006a58e`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x14006a5e8`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x14006a398`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x14006a3bc`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x14006a3e1`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x14006a406`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x14006a4f8`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x14006a525`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x14006a54a`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x14006a56a`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x14006a58e`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x14006a5e8`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14006a6ca`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14006a6ca`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryW` at `0x14006a622`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryW` at `0x14006a622`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathCombineW` at `0x14006a641`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathCombineW` at `0x14006a641`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x14006a68f`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x14006a68f`
- `api-ms-win-shell-namespace-l1-1-0!SHParseDisplayName` at `0x14006a4c2`
- `api-ms-win-shell-namespace-l1-1-0!SHParseDisplayName` at `0x14006a4c2`
- `SHCORE!__imp_GUIDFromStringW` at `0x14006a450`
- `SHCORE!__imp_GUIDFromStringW` at `0x14006a450`
- `SHELL32!__imp_ILCreateFromPathW` at `0x14006a602`
- `SHELL32!__imp_ILCreateFromPathW` at `0x14006a659`
- `SHELL32!__imp_ILCreateFromPathW` at `0x14006a602`
- `SHELL32!__imp_ILCreateFromPathW` at `0x14006a659`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetFolderLocation` at `0x14006a6b7`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetFolderLocation` at `0x14006a6b7`

## pseudocode

```c
__int64 __fastcall SHExplorerParseCmdLine(unsigned __int16 *a1, LPITEMIDLIST *ppidl)
{
  bool v4; // r12
  unsigned int v5; // edi
  int v6; // r13d
  int i; // esi
  int v8; // r8d
  ITEMIDLIST *v9; // rax
  char *v10; // rax
  ITEMIDLIST *v11; // r14
  ITEMIDLIST *v12; // rsi
  LPITEMIDLIST ppidla; // [rsp+30h] [rbp-D0h] BYREF
  int v15; // [rsp+38h] [rbp-C8h]
  struct _GUID v16; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v17; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR pszStr1[264]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v19[40]; // [rsp+270h] [rbp+170h] BYREF
  WCHAR Buffer[264]; // [rsp+2C0h] [rbp+1C0h] BYREF
  WCHAR pszDest[264]; // [rsp+4D0h] [rbp+3D0h] BYREF

  v4 = 0;
  v15 = SHCoInitialize();
  v5 = 1;
  if ( v15 >= 0 )
  {
    v6 = 0;
    for ( i = 1; ; ++i )
    {
      if ( !_private_ParseField(a1, i, pszStr1, 260) )
      {
LABEL_41:
        if ( !*ppidl )
          SHGetFolderLocation(0, 5, 0, 0, ppidl);
        if ( !v15 )
          CoUninitialize();
        goto LABEL_45;
      }
      if ( !StrCmpICW(pszStr1, L"/N") )
      {
        *((_DWORD *)ppidl + 5) |= 1u;
        continue;
      }
      if ( !StrCmpICW(pszStr1, L"/EXPAND") )
      {
        *((_DWORD *)ppidl + 5) |= 0x10u;
        continue;
      }
      if ( !StrCmpICW(pszStr1, L"/E") )
      {
        *((_DWORD *)ppidl + 5) |= 8u;
        continue;
      }
      if ( !StrCmpICW(pszStr1, L"/ROOT") )
        break;
      if ( StrCmpICW(pszStr1, L"/SELECT") )
      {
        if ( !StrCmpICW(pszStr1, L"/IDLIST") )
        {
          v12 = (ITEMIDLIST *)IDListFromCmdLine(a1, i + 1);
          if ( v12 )
          {
            ILFree(*ppidl);
            *ppidl = v12;
          }
          else if ( !*ppidl )
          {
            return 0;
          }
          *((_DWORD *)ppidl + 3) = 1;
          goto LABEL_41;
        }
        if ( StrCmpICW(pszStr1, L"/SEPARATE") )
        {
          if ( StrCmpICW(pszStr1, L"/FACTORY") )
          {
            if ( StrCmpICW(pszStr1, L"/LOADSAVEDWINDOWS") && !*ppidl )
            {
              v11 = ILCreateFromPathW(pszStr1);
              if ( !v11 )
              {
                GetCurrentDirectoryW(0x104u, Buffer);
                if ( PathCombineW(pszDest, Buffer, pszStr1) )
                  v11 = ILCreateFromPathW(pszDest);
              }
              *ppidl = v11;
            }
          }
          else
          {
            *(struct _GUID *)(ppidl + 3) = *GUIDFromCmdLine(&v16, a1, ++i);
            v10 = (char *)ppidl[3] - *(_QWORD *)&GUID_NULL.Data1;
            if ( !v10 )
              v10 = (char *)ppidl[4] - *(_QWORD *)GUID_NULL.Data4;
            v4 = v10 != 0;
          }
        }
        else
        {
          *((_DWORD *)ppidl + 4) = 1;
        }
      }
      else
      {
        *((_DWORD *)ppidl + 5) |= 4u;
      }
LABEL_37:
      ;
    }
    ppidla = 0;
    ++i;
    v17 = 0;
    if ( !_private_ParseField(a1, i, pszStr1, 260) )
      return 0;
    if ( (unsigned int)GUIDFromStringW(pszStr1, &v17) )
    {
      StringCchCopyW(v19, 0x27u, pszStr1);
      if ( !_private_ParseField(a1, ++i, pszStr1, 260) && !GetRootFromRootClass(v19, pszStr1, v8) )
        return 0;
    }
    else if ( !StrCmpICW(pszStr1, L"/IDLIST") )
    {
      ++i;
      v6 = 1;
      v9 = (ITEMIDLIST *)IDListFromCmdLine(a1, i);
LABEL_16:
      if ( v9 )
      {
        *ppidl = v9;
        *((_DWORD *)ppidl + 2) = 1;
      }
      if ( v6 )
        goto LABEL_41;
      goto LABEL_37;
    }
    SHParseDisplayName(pszStr1, 0, &ppidla, 0, 0);
    v9 = ppidla;
    goto LABEL_16;
  }
LABEL_45:
  if ( !*ppidl && !v4 )
    return 0;
  return v5;
}

```

## disassembly

```asm
0x14006a318  mov     [rsp-8+arg_10], rbx
0x14006a31d  push    rbp
0x14006a31e  push    rsi
0x14006a31f  push    rdi
0x14006a320  push    r12
0x14006a322  push    r13
0x14006a324  push    r14
0x14006a326  push    r15
0x14006a328  lea     rbp, [rsp-5F0h]
0x14006a330  sub     rsp, 6F0h
0x14006a337  mov     rax, cs:__security_cookie
0x14006a33e  xor     rax, rsp
0x14006a341  mov     [rbp+620h+var_40], rax
0x14006a348  mov     rbx, rdx
0x14006a34b  mov     r15, rcx
0x14006a34e  call    ?SHCoInitialize@@YAJXZ; SHCoInitialize(void)
0x14006a353  xor     r12b, r12b
0x14006a356  mov     [rsp+720h+var_6E8], eax
0x14006a35a  xor     r14d, r14d
0x14006a35d  mov     edi, 1
0x14006a362  test    eax, eax
0x14006a364  js      loc_14006A6D6
0x14006a36a  mov     r13d, r14d
0x14006a36d  mov     esi, edi
0x14006a36f  mov     r9d, 104h; int
0x14006a375  lea     r8, [rsp+720h+pszStr1]; unsigned __int16 *
0x14006a37a  mov     edx, esi; int
0x14006a37c  mov     rcx, r15; unsigned __int16 *
0x14006a37f  call    ?_private_ParseField@@YAHPEBGHPEAGH@Z; _private_ParseField(ushort const *,int,ushort *,int)
0x14006a384  test    eax, eax
0x14006a386  jz      loc_14006A6A1
0x14006a38c  lea     rdx, aN; "/N"
0x14006a393  lea     rcx, [rsp+720h+pszStr1]; pszStr1
0x14006a398  call    cs:__imp_StrCmpICW
0x14006a39f  nop     dword ptr [rax+rax+00h]
0x14006a3a4  test    eax, eax
0x14006a3a6  jnz     short loc_14006A3B0
0x14006a3a8  or      [rbx+14h], edi
0x14006a3ab  jmp     loc_14006A66E
0x14006a3b0  lea     rdx, aExpand; "/EXPAND"
0x14006a3b7  lea     rcx, [rsp+720h+pszStr1]; pszStr1
0x14006a3bc  call    cs:__imp_StrCmpICW
0x14006a3c3  nop     dword ptr [rax+rax+00h]
0x14006a3c8  test    eax, eax
0x14006a3ca  jnz     short loc_14006A3D5
0x14006a3cc  or      dword ptr [rbx+14h], 10h
0x14006a3d0  jmp     loc_14006A66E
0x14006a3d5  lea     rdx, aE; "/E"
0x14006a3dc  lea     rcx, [rsp+720h+pszStr1]; pszStr1
0x14006a3e1  call    cs:__imp_StrCmpICW
0x14006a3e8  nop     dword ptr [rax+rax+00h]
0x14006a3ed  test    eax, eax
0x14006a3ef  jnz     short loc_14006A3FA
0x14006a3f1  or      dword ptr [rbx+14h], 8
0x14006a3f5  jmp     loc_14006A66E
0x14006a3fa  lea     rdx, aRoot; "/ROOT"
0x14006a401  lea     rcx, [rsp+720h+pszStr1]; pszStr1
0x14006a406  call    cs:__imp_StrCmpICW
0x14006a40d  nop     dword ptr [rax+rax+00h]
0x14006a412  test    eax, eax
0x14006a414  jnz     loc_14006A519
0x14006a41a  xorps   xmm0, xmm0
0x14006a41d  mov     [rsp+720h+ppidl], r14
0x14006a422  inc     esi
0x14006a424  lea     r8, [rsp+720h+pszStr1]; unsigned __int16 *
0x14006a429  mov     edx, esi; int
0x14006a42b  mov     r9d, 104h; int
0x14006a431  mov     rcx, r15; unsigned __int16 *
0x14006a434  movups  [rsp+720h+var_6D0], xmm0
0x14006a439  call    ?_private_ParseField@@YAHPEBGHPEAGH@Z; _private_ParseField(ushort const *,int,ushort *,int)
0x14006a43e  test    eax, eax
0x14006a440  jz      loc_14006A715
0x14006a446  lea     rdx, [rsp+720h+var_6D0]
0x14006a44b  lea     rcx, [rsp+720h+pszStr1]
0x14006a450  call    cs:__imp_GUIDFromStringW
0x14006a457  nop     dword ptr [rax+rax+00h]
0x14006a45c  test    eax, eax
0x14006a45e  jz      loc_14006A4EC
0x14006a464  lea     r8, [rsp+720h+pszStr1]; unsigned __int16 *
0x14006a469  mov     edx, 27h ; '''; unsigned __int64
0x14006a46e  lea     rcx, [rbp+620h+var_4B0]; unsigned __int16 *
0x14006a475  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14006a47a  inc     esi
0x14006a47c  lea     r8, [rsp+720h+pszStr1]; unsigned __int16 *
0x14006a481  mov     edx, esi; int
0x14006a483  mov     r9d, 104h; int
0x14006a489  mov     rcx, r15; unsigned __int16 *
0x14006a48c  call    ?_private_ParseField@@YAHPEBGHPEAGH@Z; _private_ParseField(ushort const *,int,ushort *,int)
0x14006a491  test    eax, eax
0x14006a493  jnz     short loc_14006A4AE
0x14006a495  lea     rdx, [rsp+720h+pszStr1]; unsigned __int16 *
0x14006a49a  lea     rcx, [rbp+620h+var_4B0]; unsigned __int16 *
0x14006a4a1  call    ?GetRootFromRootClass@@YAHPEBGPEAGH@Z; GetRootFromRootClass(ushort const *,ushort *,int)
0x14006a4a6  test    eax, eax
0x14006a4a8  jz      loc_14006A715
0x14006a4ae  xor     r9d, r9d; sfgaoIn
0x14006a4b1  mov     [rsp+720h+psfgaoOut], r14; psfgaoOut
0x14006a4b6  lea     r8, [rsp+720h+ppidl]; ppidl
0x14006a4bb  xor     edx, edx; pbc
0x14006a4bd  lea     rcx, [rsp+720h+pszStr1]; pszName
0x14006a4c2  call    cs:__imp_SHParseDisplayName
0x14006a4c9  nop     dword ptr [rax+rax+00h]
0x14006a4ce  mov     rax, [rsp+720h+ppidl]
0x14006a4d3  test    rax, rax
0x14006a4d6  jz      short loc_14006A4DE
0x14006a4d8  mov     [rbx], rax
0x14006a4db  mov     [rbx+8], edi
0x14006a4de  test    r13d, r13d
0x14006a4e1  jz      loc_14006A66E
0x14006a4e7  jmp     loc_14006A6A1
0x14006a4ec  lea     rdx, aIdlist; "/IDLIST"
0x14006a4f3  lea     rcx, [rsp+720h+pszStr1]; pszStr1
0x14006a4f8  call    cs:__imp_StrCmpICW
0x14006a4ff  nop     dword ptr [rax+rax+00h]
0x14006a504  test    eax, eax
0x14006a506  jnz     short loc_14006A4AE
0x14006a508  add     esi, edi
0x14006a50a  mov     rcx, r15; unsigned __int16 *
0x14006a50d  mov     edx, esi; int
0x14006a50f  mov     r13d, edi
0x14006a512  call    ?IDListFromCmdLine@@YAPEAU_ITEMIDLIST_ABSOLUTE@@PEBGH@Z; IDListFromCmdLine(ushort const *,int)
0x14006a517  jmp     short loc_14006A4D3
0x14006a519  lea     rdx, aSelect; "/SELECT"
0x14006a520  lea     rcx, [rsp+720h+pszStr1]; pszStr1
0x14006a525  call    cs:__imp_StrCmpICW
0x14006a52c  nop     dword ptr [rax+rax+00h]
0x14006a531  test    eax, eax
0x14006a533  jnz     short loc_14006A53E
0x14006a535  or      dword ptr [rbx+14h], 4
0x14006a539  jmp     loc_14006A66E
0x14006a53e  lea     rdx, aIdlist; "/IDLIST"
0x14006a545  lea     rcx, [rsp+720h+pszStr1]; pszStr1
0x14006a54a  call    cs:__imp_StrCmpICW
0x14006a551  nop     dword ptr [rax+rax+00h]
0x14006a556  test    eax, eax
0x14006a558  jz      loc_14006A675
0x14006a55e  lea     rdx, aSeparate; "/SEPARATE"
0x14006a565  lea     rcx, [rsp+720h+pszStr1]; pszStr1
0x14006a56a  call    cs:__imp_StrCmpICW
0x14006a571  nop     dword ptr [rax+rax+00h]
0x14006a576  test    eax, eax
0x14006a578  jnz     short loc_14006A582
0x14006a57a  mov     [rbx+10h], edi
0x14006a57d  jmp     loc_14006A66E
0x14006a582  lea     rdx, aFactory; "/FACTORY"
0x14006a589  lea     rcx, [rsp+720h+pszStr1]; pszStr1
0x14006a58e  call    cs:__imp_StrCmpICW
0x14006a595  nop     dword ptr [rax+rax+00h]
0x14006a59a  test    eax, eax
0x14006a59c  jnz     short loc_14006A5DC
0x14006a59e  add     esi, edi
0x14006a5a0  lea     rcx, [rsp+720h+var_6E0]; retstr
0x14006a5a5  mov     r8d, esi; int
0x14006a5a8  mov     rdx, r15; unsigned __int16 *
0x14006a5ab  call    ?GUIDFromCmdLine@@YA?AU_GUID@@PEBGH@Z; GUIDFromCmdLine(ushort const *,int)
0x14006a5b0  movups  xmm0, xmmword ptr [rax]
0x14006a5b3  movdqu  xmmword ptr [rbx+18h], xmm0
0x14006a5b8  mov     rax, [rbx+18h]
0x14006a5bc  sub     rax, qword ptr cs:GUID_NULL.Data1
0x14006a5c3  jnz     short loc_14006A5D0
0x14006a5c5  mov     rax, [rbx+20h]
0x14006a5c9  sub     rax, qword ptr cs:GUID_NULL.Data4
0x14006a5d0  test    rax, rax
0x14006a5d3  setnz   r12b
0x14006a5d7  jmp     loc_14006A66E
0x14006a5dc  lea     rdx, pwzCommandline; "/LOADSAVEDWINDOWS"
0x14006a5e3  lea     rcx, [rsp+720h+pszStr1]; pszStr1
0x14006a5e8  call    cs:__imp_StrCmpICW
0x14006a5ef  nop     dword ptr [rax+rax+00h]
0x14006a5f4  test    eax, eax
0x14006a5f6  jz      short loc_14006A66E
0x14006a5f8  cmp     [rbx], r14
0x14006a5fb  jnz     short loc_14006A66E
0x14006a5fd  lea     rcx, [rsp+720h+pszStr1]; pszPath
0x14006a602  call    cs:__imp_ILCreateFromPathW
0x14006a609  nop     dword ptr [rax+rax+00h]
0x14006a60e  mov     r14, rax
0x14006a611  test    rax, rax
0x14006a614  jnz     short loc_14006A668
0x14006a616  lea     rdx, [rbp+620h+Buffer]; lpBuffer
0x14006a61d  mov     ecx, 104h; nBufferLength
0x14006a622  call    cs:__imp_GetCurrentDirectoryW
0x14006a629  nop     dword ptr [rax+rax+00h]
0x14006a62e  lea     r8, [rsp+720h+pszStr1]; pszFile
0x14006a633  lea     rdx, [rbp+620h+Buffer]; pszDir
0x14006a63a  lea     rcx, [rbp+620h+pszDest]; pszDest
0x14006a641  call    cs:__imp_PathCombineW
0x14006a648  nop     dword ptr [rax+rax+00h]
0x14006a64d  test    rax, rax
0x14006a650  jz      short loc_14006A668
0x14006a652  lea     rcx, [rbp+620h+pszDest]; pszPath
0x14006a659  call    cs:__imp_ILCreateFromPathW
0x14006a660  nop     dword ptr [rax+rax+00h]
0x14006a665  mov     r14, rax
0x14006a668  mov     [rbx], r14
0x14006a66b  xor     r14d, r14d
0x14006a66e  add     esi, edi
0x14006a670  jmp     loc_14006A36F
0x14006a675  lea     edx, [rsi+1]; int
0x14006a678  mov     rcx, r15; unsigned __int16 *
0x14006a67b  call    ?IDListFromCmdLine@@YAPEAU_ITEMIDLIST_ABSOLUTE@@PEBGH@Z; IDListFromCmdLine(ushort const *,int)
0x14006a680  mov     rsi, rax
0x14006a683  test    rax, rax
0x14006a686  jz      loc_14006A710
0x14006a68c  mov     rcx, [rbx]; pidl
0x14006a68f  call    cs:__imp_ILFree
0x14006a696  nop     dword ptr [rax+rax+00h]
0x14006a69b  mov     [rbx], rsi
0x14006a69e  mov     [rbx+0Ch], edi
0x14006a6a1  cmp     [rbx], r14
0x14006a6a4  jnz     short loc_14006A6C3
0x14006a6a6  xor     r9d, r9d; dwFlags
0x14006a6a9  mov     [rsp+720h+psfgaoOut], rbx; ppidl
0x14006a6ae  xor     r8d, r8d; hToken
0x14006a6b1  xor     ecx, ecx; hwnd
0x14006a6b3  lea     edx, [r9+5]; csidl
0x14006a6b7  call    cs:__imp_SHGetFolderLocation
0x14006a6be  nop     dword ptr [rax+rax+00h]
0x14006a6c3  cmp     [rsp+720h+var_6E8], r14d
0x14006a6c8  jnz     short loc_14006A6D6
0x14006a6ca  call    cs:__imp_CoUninitialize
0x14006a6d1  nop     dword ptr [rax+rax+00h]
0x14006a6d6  cmp     [rbx], r14
0x14006a6d9  jnz     short loc_14006A6E3
0x14006a6db  test    r12b, r12b
0x14006a6de  jnz     short loc_14006A6E3
0x14006a6e0  mov     edi, r14d
0x14006a6e3  mov     eax, edi
0x14006a6e5  mov     rcx, [rbp+620h+var_40]
0x14006a6ec  xor     rcx, rsp; StackCookie
0x14006a6ef  call    __security_check_cookie
0x14006a6f4  mov     rbx, [rsp+720h+arg_10]
0x14006a6fc  add     rsp, 6F0h
0x14006a703  pop     r15
0x14006a705  pop     r14
0x14006a707  pop     r13
0x14006a709  pop     r12
0x14006a70b  pop     rdi
0x14006a70c  pop     rsi
0x14006a70d  pop     rbp
0x14006a70e  retn
0x14006a710  cmp     [rbx], r14
0x14006a713  jnz     short loc_14006A69E
0x14006a715  xor     eax, eax
0x14006a717  jmp     short loc_14006A6E5
```
