# SHExplorerParseCmdLine

- ea: `0x14000e118`
- end: `0x14000e49f`
- name: `SHExplorerParseCmdLine`
- size: `903`
- prototype: `__int64 __fastcall(unsigned __int16 *, LPITEMIDLIST *ppidl)`
- caller_count: `2`
- callee_count: `8`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x14000deb4`
- `0x14009ae00`

## callees

- `0x14000e118`
- `0x14000e4a8`
- `0x14000e4f4`
- `0x14000ec10`
- `0x14003dd00`
- `0x1401040e0`
- `0x140109ea0`
- `0x140109fe0`

## import_xrefs

- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x14000e198`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x14000e1b6`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x14000e1d5`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x14000e1f4`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x14000e2d4`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x14000e2fb`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x14000e31a`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x14000e334`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x14000e352`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x14000e3a3`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x14000e198`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x14000e1b6`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x14000e1d5`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x14000e1f4`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x14000e2d4`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x14000e2fb`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x14000e31a`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x14000e334`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x14000e352`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x14000e3a3`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14000e457`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14000e457`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryW` at `0x14000e3d1`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryW` at `0x14000e3d1`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathCombineW` at `0x14000e3ea`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathCombineW` at `0x14000e3ea`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x14000e428`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x14000e428`
- `api-ms-win-shell-namespace-l1-1-0!SHParseDisplayName` at `0x14000e2a4`
- `api-ms-win-shell-namespace-l1-1-0!SHParseDisplayName` at `0x14000e2a4`
- `SHCORE!__imp_GUIDFromStringW` at `0x14000e238`
- `SHCORE!__imp_GUIDFromStringW` at `0x14000e238`
- `SHELL32!__imp_ILCreateFromPathW` at `0x14000e3b7`
- `SHELL32!__imp_ILCreateFromPathW` at `0x14000e3fc`
- `SHELL32!__imp_ILCreateFromPathW` at `0x14000e3b7`
- `SHELL32!__imp_ILCreateFromPathW` at `0x14000e3fc`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetFolderLocation` at `0x14000e44a`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetFolderLocation` at `0x14000e44a`

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
0x14000e118  mov     [rsp-8+arg_10], rbx
0x14000e11d  push    rbp
0x14000e11e  push    rsi
0x14000e11f  push    rdi
0x14000e120  push    r12
0x14000e122  push    r13
0x14000e124  push    r14
0x14000e126  push    r15
0x14000e128  lea     rbp, [rsp-5F0h]
0x14000e130  sub     rsp, 6F0h
0x14000e137  mov     rax, cs:__security_cookie
0x14000e13e  xor     rax, rsp
0x14000e141  mov     [rbp+620h+var_40], rax
0x14000e148  mov     rbx, rdx
0x14000e14b  mov     r15, rcx
0x14000e14e  call    ?SHCoInitialize@@YAJXZ; SHCoInitialize(void)
0x14000e153  xor     r12b, r12b
0x14000e156  mov     [rsp+720h+var_6E8], eax
0x14000e15a  xor     r14d, r14d
0x14000e15d  mov     edi, 1
0x14000e162  test    eax, eax
0x14000e164  js      loc_14000E45D
0x14000e16a  mov     r13d, r14d
0x14000e16d  mov     esi, edi
0x14000e16f  mov     r9d, 104h; int
0x14000e175  lea     r8, [rsp+720h+pszStr1]; unsigned __int16 *
0x14000e17a  mov     edx, esi; int
0x14000e17c  mov     rcx, r15; unsigned __int16 *
0x14000e17f  call    ?_private_ParseField@@YAHPEBGHPEAGH@Z; _private_ParseField(ushort const *,int,ushort *,int)
0x14000e184  test    eax, eax
0x14000e186  jz      loc_14000E434
0x14000e18c  lea     rdx, aN; "/N"
0x14000e193  lea     rcx, [rsp+720h+pszStr1]; pszStr1
0x14000e198  call    cs:__imp_StrCmpICW
0x14000e19e  test    eax, eax
0x14000e1a0  jnz     short loc_14000E1AA
0x14000e1a2  or      [rbx+14h], edi
0x14000e1a5  jmp     loc_14000E40B
0x14000e1aa  lea     rdx, aExpand; "/EXPAND"
0x14000e1b1  lea     rcx, [rsp+720h+pszStr1]; pszStr1
0x14000e1b6  call    cs:__imp_StrCmpICW
0x14000e1bc  test    eax, eax
0x14000e1be  jnz     short loc_14000E1C9
0x14000e1c0  or      dword ptr [rbx+14h], 10h
0x14000e1c4  jmp     loc_14000E40B
0x14000e1c9  lea     rdx, aE; "/E"
0x14000e1d0  lea     rcx, [rsp+720h+pszStr1]; pszStr1
0x14000e1d5  call    cs:__imp_StrCmpICW
0x14000e1db  test    eax, eax
0x14000e1dd  jnz     short loc_14000E1E8
0x14000e1df  or      dword ptr [rbx+14h], 8
0x14000e1e3  jmp     loc_14000E40B
0x14000e1e8  lea     rdx, aRoot; "/ROOT"
0x14000e1ef  lea     rcx, [rsp+720h+pszStr1]; pszStr1
0x14000e1f4  call    cs:__imp_StrCmpICW
0x14000e1fa  test    eax, eax
0x14000e1fc  jnz     loc_14000E2EF
0x14000e202  xorps   xmm0, xmm0
0x14000e205  mov     [rsp+720h+ppidl], r14
0x14000e20a  inc     esi
0x14000e20c  lea     r8, [rsp+720h+pszStr1]; unsigned __int16 *
0x14000e211  mov     edx, esi; int
0x14000e213  mov     r9d, 104h; int
0x14000e219  mov     rcx, r15; unsigned __int16 *
0x14000e21c  movups  [rsp+720h+var_6D0], xmm0
0x14000e221  call    ?_private_ParseField@@YAHPEBGHPEAGH@Z; _private_ParseField(ushort const *,int,ushort *,int)
0x14000e226  test    eax, eax
0x14000e228  jz      loc_14000E49B
0x14000e22e  lea     rdx, [rsp+720h+var_6D0]
0x14000e233  lea     rcx, [rsp+720h+pszStr1]
0x14000e238  call    cs:__imp_GUIDFromStringW
0x14000e23e  test    eax, eax
0x14000e240  jz      loc_14000E2C8
0x14000e246  lea     r8, [rsp+720h+pszStr1]; unsigned __int16 *
0x14000e24b  mov     edx, 27h ; '''; unsigned __int64
0x14000e250  lea     rcx, [rbp+620h+var_4B0]; unsigned __int16 *
0x14000e257  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14000e25c  inc     esi
0x14000e25e  lea     r8, [rsp+720h+pszStr1]; unsigned __int16 *
0x14000e263  mov     edx, esi; int
0x14000e265  mov     r9d, 104h; int
0x14000e26b  mov     rcx, r15; unsigned __int16 *
0x14000e26e  call    ?_private_ParseField@@YAHPEBGHPEAGH@Z; _private_ParseField(ushort const *,int,ushort *,int)
0x14000e273  test    eax, eax
0x14000e275  jnz     short loc_14000E290
0x14000e277  lea     rdx, [rsp+720h+pszStr1]; unsigned __int16 *
0x14000e27c  lea     rcx, [rbp+620h+var_4B0]; unsigned __int16 *
0x14000e283  call    ?GetRootFromRootClass@@YAHPEBGPEAGH@Z; GetRootFromRootClass(ushort const *,ushort *,int)
0x14000e288  test    eax, eax
0x14000e28a  jz      loc_14000E49B
0x14000e290  xor     r9d, r9d; sfgaoIn
0x14000e293  mov     [rsp+720h+psfgaoOut], r14; psfgaoOut
0x14000e298  lea     r8, [rsp+720h+ppidl]; ppidl
0x14000e29d  xor     edx, edx; pbc
0x14000e29f  lea     rcx, [rsp+720h+pszStr1]; pszName
0x14000e2a4  call    cs:__imp_SHParseDisplayName
0x14000e2aa  mov     rax, [rsp+720h+ppidl]
0x14000e2af  test    rax, rax
0x14000e2b2  jz      short loc_14000E2BA
0x14000e2b4  mov     [rbx], rax
0x14000e2b7  mov     [rbx+8], edi
0x14000e2ba  test    r13d, r13d
0x14000e2bd  jz      loc_14000E40B
0x14000e2c3  jmp     loc_14000E434
0x14000e2c8  lea     rdx, aIdlist; "/IDLIST"
0x14000e2cf  lea     rcx, [rsp+720h+pszStr1]; pszStr1
0x14000e2d4  call    cs:__imp_StrCmpICW
0x14000e2da  test    eax, eax
0x14000e2dc  jnz     short loc_14000E290
0x14000e2de  add     esi, edi
0x14000e2e0  mov     rcx, r15; unsigned __int16 *
0x14000e2e3  mov     edx, esi; int
0x14000e2e5  mov     r13d, edi
0x14000e2e8  call    ?IDListFromCmdLine@@YAPEAU_ITEMIDLIST_ABSOLUTE@@PEBGH@Z; IDListFromCmdLine(ushort const *,int)
0x14000e2ed  jmp     short loc_14000E2AF
0x14000e2ef  lea     rdx, aSelect; "/SELECT"
0x14000e2f6  lea     rcx, [rsp+720h+pszStr1]; pszStr1
0x14000e2fb  call    cs:__imp_StrCmpICW
0x14000e301  test    eax, eax
0x14000e303  jnz     short loc_14000E30E
0x14000e305  or      dword ptr [rbx+14h], 4
0x14000e309  jmp     loc_14000E40B
0x14000e30e  lea     rdx, aIdlist; "/IDLIST"
0x14000e315  lea     rcx, [rsp+720h+pszStr1]; pszStr1
0x14000e31a  call    cs:__imp_StrCmpICW
0x14000e320  test    eax, eax
0x14000e322  jz      loc_14000E412
0x14000e328  lea     rdx, aSeparate; "/SEPARATE"
0x14000e32f  lea     rcx, [rsp+720h+pszStr1]; pszStr1
0x14000e334  call    cs:__imp_StrCmpICW
0x14000e33a  test    eax, eax
0x14000e33c  jnz     short loc_14000E346
0x14000e33e  mov     [rbx+10h], edi
0x14000e341  jmp     loc_14000E40B
0x14000e346  lea     rdx, aFactory; "/FACTORY"
0x14000e34d  lea     rcx, [rsp+720h+pszStr1]; pszStr1
0x14000e352  call    cs:__imp_StrCmpICW
0x14000e358  test    eax, eax
0x14000e35a  jnz     short loc_14000E397
0x14000e35c  add     esi, edi
0x14000e35e  lea     rcx, [rsp+720h+var_6E0]; retstr
0x14000e363  mov     r8d, esi; int
0x14000e366  mov     rdx, r15; unsigned __int16 *
0x14000e369  call    ?GUIDFromCmdLine@@YA?AU_GUID@@PEBGH@Z; GUIDFromCmdLine(ushort const *,int)
0x14000e36e  movups  xmm0, xmmword ptr [rax]
0x14000e371  movdqu  xmmword ptr [rbx+18h], xmm0
0x14000e376  mov     rax, [rbx+18h]
0x14000e37a  sub     rax, qword ptr cs:GUID_NULL.Data1
0x14000e381  jnz     short loc_14000E38E
0x14000e383  mov     rax, [rbx+20h]
0x14000e387  sub     rax, qword ptr cs:GUID_NULL.Data4
0x14000e38e  test    rax, rax
0x14000e391  setnz   r12b
0x14000e395  jmp     short loc_14000E40B
0x14000e397  lea     rdx, pwzCommandline; "/LOADSAVEDWINDOWS"
0x14000e39e  lea     rcx, [rsp+720h+pszStr1]; pszStr1
0x14000e3a3  call    cs:__imp_StrCmpICW
0x14000e3a9  test    eax, eax
0x14000e3ab  jz      short loc_14000E40B
0x14000e3ad  cmp     [rbx], r14
0x14000e3b0  jnz     short loc_14000E40B
0x14000e3b2  lea     rcx, [rsp+720h+pszStr1]; pszPath
0x14000e3b7  call    cs:__imp_ILCreateFromPathW
0x14000e3bd  mov     r14, rax
0x14000e3c0  test    rax, rax
0x14000e3c3  jnz     short loc_14000E405
0x14000e3c5  lea     rdx, [rbp+620h+Buffer]; lpBuffer
0x14000e3cc  mov     ecx, 104h; nBufferLength
0x14000e3d1  call    cs:__imp_GetCurrentDirectoryW
0x14000e3d7  lea     r8, [rsp+720h+pszStr1]; pszFile
0x14000e3dc  lea     rdx, [rbp+620h+Buffer]; pszDir
0x14000e3e3  lea     rcx, [rbp+620h+pszDest]; pszDest
0x14000e3ea  call    cs:__imp_PathCombineW
0x14000e3f0  test    rax, rax
0x14000e3f3  jz      short loc_14000E405
0x14000e3f5  lea     rcx, [rbp+620h+pszDest]; pszPath
0x14000e3fc  call    cs:__imp_ILCreateFromPathW
0x14000e402  mov     r14, rax
0x14000e405  mov     [rbx], r14
0x14000e408  xor     r14d, r14d
0x14000e40b  add     esi, edi
0x14000e40d  jmp     loc_14000E16F
0x14000e412  lea     edx, [rsi+1]; int
0x14000e415  mov     rcx, r15; unsigned __int16 *
0x14000e418  call    ?IDListFromCmdLine@@YAPEAU_ITEMIDLIST_ABSOLUTE@@PEBGH@Z; IDListFromCmdLine(ushort const *,int)
0x14000e41d  mov     rsi, rax
0x14000e420  test    rax, rax
0x14000e423  jz      short loc_14000E496
0x14000e425  mov     rcx, [rbx]; pidl
0x14000e428  call    cs:__imp_ILFree
0x14000e42e  mov     [rbx], rsi
0x14000e431  mov     [rbx+0Ch], edi
0x14000e434  cmp     [rbx], r14
0x14000e437  jnz     short loc_14000E450
0x14000e439  xor     r9d, r9d; dwFlags
0x14000e43c  mov     [rsp+720h+psfgaoOut], rbx; ppidl
0x14000e441  xor     r8d, r8d; hToken
0x14000e444  xor     ecx, ecx; hwnd
0x14000e446  lea     edx, [r9+5]; csidl
0x14000e44a  call    cs:__imp_SHGetFolderLocation
0x14000e450  cmp     [rsp+720h+var_6E8], r14d
0x14000e455  jnz     short loc_14000E45D
0x14000e457  call    cs:__imp_CoUninitialize
0x14000e45d  cmp     [rbx], r14
0x14000e460  jnz     short loc_14000E46A
0x14000e462  test    r12b, r12b
0x14000e465  jnz     short loc_14000E46A
0x14000e467  mov     edi, r14d
0x14000e46a  mov     eax, edi
0x14000e46c  mov     rcx, [rbp+620h+var_40]
0x14000e473  xor     rcx, rsp; StackCookie
0x14000e476  call    __security_check_cookie
0x14000e47b  mov     rbx, [rsp+720h+arg_10]
0x14000e483  add     rsp, 6F0h
0x14000e48a  pop     r15
0x14000e48c  pop     r14
0x14000e48e  pop     r13
0x14000e490  pop     r12
0x14000e492  pop     rdi
0x14000e493  pop     rsi
0x14000e494  pop     rbp
0x14000e495  retn
0x14000e496  cmp     [rbx], r14
0x14000e499  jnz     short loc_14000E431
0x14000e49b  xor     eax, eax
0x14000e49d  jmp     short loc_14000E46C
```
