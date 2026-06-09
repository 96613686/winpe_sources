# CIEFrameAuto::_get_Location(ushort * *,uint)

- ea: `0x180025d30`
- end: `0x180026494`
- name: `?_get_Location@CIEFrameAuto@@IEAAJPEAPEAGI@Z`
- size: `1892`
- prototype: `__int64 __fastcall(CIEFrameAuto *__hidden this, unsigned __int16 **, unsigned int)`
- caller_count: `4`
- callee_count: `15`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18010e1a4`
- `0x180111f1c`
- `0x180117a60`
- `0x180117a80`

## callees

- `0x1800144d0`
- `0x180023c4c`
- `0x180024b74`
- `0x180025d30`
- `0x18002649c`
- `0x1800488b0`
- `0x18006fb04`
- `0x1800c18bc`
- `0x1800c1904`
- `0x1800c663c`
- `0x180525568`
- `0x180591ef6`
- `0x180591f80`
- `0x180592040`
- `0x180594010`

## import_xrefs

- `SHLWAPI!StrRetToBufW` at `0x18002610e`
- `SHLWAPI!StrRetToBufW` at `0x18002610e`
- `api-ms-win-downlevel-shlwapi-l1-1-0!UrlCreateFromPathW` at `0x1800263e1`
- `api-ms-win-downlevel-shlwapi-l1-1-0!UrlCreateFromPathW` at `0x1800263e1`
- `api-ms-win-downlevel-shlwapi-l1-1-0!UrlCombineW` at `0x180025fa7`
- `api-ms-win-downlevel-shlwapi-l1-1-0!UrlCombineW` at `0x180025fee`
- `api-ms-win-downlevel-shlwapi-l1-1-0!UrlCombineW` at `0x180026298`
- `api-ms-win-downlevel-shlwapi-l1-1-0!UrlCombineW` at `0x18002636d`
- `api-ms-win-downlevel-shlwapi-l1-1-0!UrlCombineW` at `0x180025fa7`
- `api-ms-win-downlevel-shlwapi-l1-1-0!UrlCombineW` at `0x180025fee`
- `api-ms-win-downlevel-shlwapi-l1-1-0!UrlCombineW` at `0x180026298`
- `api-ms-win-downlevel-shlwapi-l1-1-0!UrlCombineW` at `0x18002636d`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathIsURLW` at `0x180026429`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathIsURLW` at `0x180026429`
- `OLEAUT32!__imp_SysAllocString` at `0x18002644c`
- `OLEAUT32!__imp_SysAllocString` at `0x18002644c`
- `SHELL32!__imp_ILFree` at `0x18002640d`
- `SHELL32!__imp_ILFree` at `0x18002640d`
- `api-ms-win-downlevel-ole32-l1-1-0!CoInitializeEx` at `0x180026041`
- `api-ms-win-downlevel-ole32-l1-1-0!CoInitializeEx` at `0x18002605b`
- `api-ms-win-downlevel-ole32-l1-1-0!CoInitializeEx` at `0x180026041`
- `api-ms-win-downlevel-ole32-l1-1-0!CoInitializeEx` at `0x18002605b`
- `api-ms-win-downlevel-ole32-l1-1-0!CoUninitialize` at `0x18002614c`
- `api-ms-win-downlevel-ole32-l1-1-0!CoUninitialize` at `0x18002614c`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHAnsiToUnicode` at `0x180025e80`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHAnsiToUnicode` at `0x180025f77`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHAnsiToUnicode` at `0x180026268`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHAnsiToUnicode` at `0x18002633d`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHAnsiToUnicode` at `0x180025e80`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHAnsiToUnicode` at `0x180025f77`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHAnsiToUnicode` at `0x180026268`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHAnsiToUnicode` at `0x18002633d`

## pseudocode

```c
__int64 __fastcall CIEFrameAuto::_get_Location(CIEFrameAuto *this, unsigned __int16 **a2, unsigned int a3)
{
  __int64 v3; // rcx
  unsigned __int16 **v5; // r12
  __int64 v6; // rdx
  HRESULT v7; // esi
  __int64 v8; // r8
  const ITEMIDLIST *v9; // r14
  __int64 v10; // r9
  __int64 v11; // rax
  const struct _ITEMIDLIST_RELATIVE *abID; // rcx
  char *v13; // rbx
  char v14; // al
  int v15; // r8d
  WCHAR *v16; // rax
  WCHAR *v17; // rcx
  HRESULT v18; // r15d
  LPITEMIDLIST ID_0; // rdi
  unsigned __int16 *HiddenID; // rdx
  unsigned __int16 *v21; // rdi
  const CHAR *v22; // rax
  int v23; // r8d
  WCHAR *v24; // rcx
  DWORD v25; // edi
  HRESULT v26; // r15d
  __int64 v27; // rdx
  __int64 v28; // r8
  __int64 v29; // r9
  const ITEMIDLIST *v30; // r12
  void *v31; // rsi
  DWORD v32; // ebx
  __int64 v33; // rdx
  __int64 v34; // r8
  __int64 v35; // r9
  HRESULT v36; // edi
  LPITEMIDLIST v37; // rax
  unsigned __int64 cb; // r8
  __int64 v39; // r9
  unsigned __int16 *v40; // rdx
  const CHAR *v41; // rax
  int v42; // r8d
  STRRET *v43; // rcx
  const ITEMIDLIST *v44; // rcx
  LPITEMIDLIST v45; // rbx
  unsigned __int16 *v46; // rdx
  unsigned __int16 *v47; // rbx
  bool v49; // zf
  BSTR v50; // rax
  DWORD pcchUrl; // [rsp+30h] [rbp-D0h] BYREF
  DWORD pcchCombined; // [rsp+38h] [rbp-C8h] BYREF
  void *ppv; // [rsp+40h] [rbp-C0h] BYREF
  LPCITEMIDLIST pidl; // [rsp+48h] [rbp-B8h] BYREF
  LPCITEMIDLIST ppidlLast; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 **v57; // [rsp+58h] [rbp-A8h]
  WCHAR pwszDst[2088]; // [rsp+60h] [rbp-A0h] BYREF
  STRRET pszSrc[15]; // [rsp+10B0h] [rbp+FB0h] BYREF
  WCHAR pszRelative[2088]; // [rsp+2100h] [rbp+2000h] BYREF

  v3 = *((_QWORD *)this + 55);
  v57 = a2;
  v5 = a2;
  if ( v3 )
  {
    pidl = 0;
    v7 = (*(__int64 (__fastcall **)(__int64, LPCITEMIDLIST *))(*(_QWORD *)v3 + 176LL))(v3, &pidl);
    if ( v7 < 0 )
      goto LABEL_120;
    v9 = pidl;
    v10 = 2;
    pwszDst[0] = 0;
    if ( pidl && pidl->mkid.cb == 20 && pidl->mkid.abID[0] == 31 )
    {
      v11 = *(_QWORD *)((char *)&pidl[1].mkid.cb + 1) - *(_QWORD *)&CLSID_Internet.Data1;
      if ( !v11 )
        v11 = *(_QWORD *)&pidl[4].mkid.cb - *(_QWORD *)CLSID_Internet.Data4;
      if ( !v11 )
      {
        abID = (const struct _ITEMIDLIST_RELATIVE *)pidl[6].mkid.abID;
        if ( *(_WORD *)pidl[6].mkid.abID < 0xCu
          || HIBYTE(pidl[7].mkid.cb) != 97
          || (pidl[7].mkid.abID[0] & 0x7F) != 0 && !_IsValidDelegateID(abID) )
        {
          abID = 0;
        }
        if ( abID )
        {
          if ( (a3 & 0x8000) != 0 )
          {
            v13 = (char *)v9 + v9->mkid.cb;
            if ( *(_WORD *)v13 >= 0xCu && v13[2] == 97 && (v13[3] & 0x7F) == 0 )
            {
              v14 = v13[3];
              if ( v14 )
              {
                if ( v14 == (char)0x80 )
                {
                  v15 = 2084;
                  v16 = (WCHAR *)(v13 + 8);
                  v17 = pwszDst;
                  while ( *v16 )
                  {
                    *v17 = *v16;
                    v16 = (WCHAR *)((char *)v16 + v10);
                    v17 = (WCHAR *)((char *)v17 + v10);
                    if ( !--v15 )
                    {
                      *(v17 - 1) = 0;
                      goto LABEL_27;
                    }
                  }
                  *v17 = 0;
                }
              }
              else
              {
                StringCbCopyA((char *)pszSrc, 0x824u, v13 + 8);
                SHAnsiToUnicode((PCSTR)pszSrc, pwszDst, 2084);
              }
LABEL_27:
              v18 = 0;
              pcchUrl = 2084;
              pcchCombined = 2084;
              if ( !*(_WORD *)v13 )
                goto LABEL_128;
              ID_0 = ILFindLastID_0((LPCITEMIDLIST)v13);
              HiddenID = (unsigned __int16 *)ILFindFirstHiddenID(ID_0);
              v21 = (USHORT *)((char *)&ID_0->mkid.cb + ID_0->mkid.cb);
              if ( HiddenID )
              {
                while ( *((_DWORD *)HiddenID + 1) != -1091633150 )
                {
                  HiddenID = (unsigned __int16 *)((char *)HiddenID + *HiddenID);
                  if ( HiddenID >= v21 || HIWORD(*((_DWORD *)HiddenID + 1)) != 0xBEEF )
                  {
                    HiddenID = 0;
                    break;
                  }
                  if ( !HiddenID )
                    break;
                }
              }
              if ( !HiddenID )
                goto LABEL_128;
              v22 = (const CHAR *)(HiddenID + 5);
              v23 = 2084;
              if ( HiddenID[4] == 2 )
              {
                v24 = pszRelative;
                while ( *(_WORD *)v22 )
                {
                  *v24 = *(_WORD *)v22;
                  v22 += 2;
                  ++v24;
                  if ( !--v23 )
                  {
                    *(v24 - 1) = 0;
                    goto LABEL_43;
                  }
                }
                *v24 = 0;
              }
              else
              {
                SHAnsiToUnicode(v22, pszRelative, 2084);
              }
LABEL_43:
              if ( pszRelative[0] != 63
                || (v18 = UrlCombineW(pwszDst, pszRelative, pwszDst, &pcchCombined, 0), v18 >= 0) )
              {
LABEL_128:
                if ( (unsigned int)ILGetHiddenStringW(v13, 3203334145LL, pszRelative) )
                  v18 = UrlCombineW(pwszDst, pszRelative, pwszDst, &pcchUrl, 0);
              }
              v7 = 0;
              if ( v18 != -2147467261 )
                v7 = v18;
              if ( v7 >= 0 )
                goto LABEL_111;
            }
          }
        }
      }
    }
    if ( IEShimsDisableRedirection::SetEnabled )
      v25 = IEShimsDisableRedirection::SetEnabled(0, v6, v8, v10);
    else
      v25 = pcchUrl;
    pwszDst[0] = 0;
    v26 = CoInitializeEx(0, 6u);
    if ( v26 < 0 )
      v26 = CoInitializeEx(0, 4u);
    ppv = 0;
    ppidlLast = 0;
    v7 = SHBindToParent_0(v9, &GUID_000214e6_0000_0000_c000_000000000046, &ppv, &ppidlLast);
    if ( v7 >= 0 )
    {
      v30 = ppidlLast;
      v31 = ppv;
      if ( IEShimsDisableRedirection::SetEnabled )
        v32 = IEShimsDisableRedirection::SetEnabled(0, v27, v28, v29);
      else
        v32 = pcchUrl;
      pwszDst[0] = 0;
      memset_0(pszSrc, 0, 0x110u);
      v7 = (*(__int64 (__fastcall **)(void *, const ITEMIDLIST *, _QWORD, STRRET *))(*(_QWORD *)v31 + 88LL))(
             v31,
             v30,
             a3,
             pszSrc);
      if ( v7 >= 0 )
        v7 = StrRetToBufW(pszSrc, v30, pwszDst, 0x824u);
      if ( IEShimsDisableRedirection::SetEnabled )
        IEShimsDisableRedirection::SetEnabled(v32, v33, v34, v35);
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
      v5 = v57;
    }
    if ( v26 >= 0 )
      CoUninitialize();
    if ( IEShimsDisableRedirection::SetEnabled )
      IEShimsDisableRedirection::SetEnabled(v25, v27, v28, v29);
    if ( v7 >= 0 )
    {
      if ( (a3 & 0x8000) != 0 )
      {
        v36 = 0;
        pcchCombined = 2084;
        pcchUrl = 2084;
        if ( !v9 || !v9->mkid.cb )
          goto LABEL_129;
        v37 = ILFindLastID_0(v9);
        cb = v37->mkid.cb;
        v39 = *(unsigned __int16 *)((char *)v37 + cb - 2);
        if ( (_WORD)v39
          && v39 + 8 < cb
          && (v40 = (USHORT *)((char *)&v37->mkid.cb + *(unsigned __int16 *)((char *)v37 + cb - 2)),
              HIWORD(*((_DWORD *)v40 + 1)) == 0xBEEF)
          && (unsigned int)v39 + *v40 <= (unsigned int)cb )
        {
          while ( *((_DWORD *)v40 + 1) != -1091633150 )
          {
            v40 = (unsigned __int16 *)((char *)v40 + *v40);
            if ( v40 >= (unsigned __int16 *)((char *)&v37->mkid.cb + cb) || HIWORD(*((_DWORD *)v40 + 1)) != 0xBEEF )
              goto LABEL_81;
            if ( !v40 )
              break;
          }
        }
        else
        {
LABEL_81:
          v40 = 0;
        }
        if ( !v40 )
          goto LABEL_129;
        v41 = (const CHAR *)(v40 + 5);
        v42 = 2084;
        if ( v40[4] == 2 )
        {
          v43 = pszSrc;
          while ( *(_WORD *)v41 )
          {
            LOWORD(v43->uType) = *(_WORD *)v41;
            v41 += 2;
            v43 = (STRRET *)((char *)v43 + 2);
            if ( !--v42 )
            {
              *(_WORD *)&v43[-1].cStr[262] = 0;
              goto LABEL_90;
            }
          }
          LOWORD(v43->uType) = 0;
        }
        else
        {
          SHAnsiToUnicode(v41, (PWSTR)pszSrc, 2084);
        }
LABEL_90:
        if ( LOWORD(pszSrc[0].uType) != 63
          || (v36 = UrlCombineW(pwszDst, (PCWSTR)pszSrc, pwszDst, &pcchUrl, 0), v36 >= 0) )
        {
LABEL_129:
          if ( !(unsigned int)ILIsEmpty((const struct _ITEMIDLIST_RELATIVE *)v9) )
          {
            v45 = ILFindLastID_0(v44);
            v46 = (unsigned __int16 *)ILFindFirstHiddenID(v45);
            v47 = (USHORT *)((char *)&v45->mkid.cb + v45->mkid.cb);
            if ( v46 )
            {
              while ( *((_DWORD *)v46 + 1) != -1091633151 )
              {
                v46 = (unsigned __int16 *)((char *)v46 + *v46);
                if ( v46 >= v47 || HIWORD(*((_DWORD *)v46 + 1)) != 0xBEEF )
                {
                  v46 = 0;
                  break;
                }
                if ( !v46 )
                  break;
              }
            }
            if ( v46 )
            {
              if ( v46[4] == 2 )
                ualstrcpynW(pszSrc, v46 + 5, 2084);
              else
                SHAnsiToUnicode((PCSTR)v46 + 10, (PWSTR)pszSrc, 2084);
              if ( LOWORD(pszSrc[0].uType) == 35 )
                v36 = UrlCombineW(pwszDst, (PCWSTR)pszSrc, pwszDst, &pcchCombined, 0);
            }
          }
        }
        v7 = 0;
        if ( v36 != -2147467261 )
          v7 = v36;
      }
      if ( v7 >= 0 && (a3 & 0x8000) != 0 )
      {
LABEL_111:
        if ( pwszDst[0] == 92 || pwszDst[0] && pwszDst[1] == 58 || GetUrlSchemeW(pwszDst) == 9 )
        {
          pcchUrl = 2084;
          v7 = UrlCreateFromPathW(pwszDst, pszRelative, &pcchUrl, 0);
          if ( v7 >= 0 )
            v7 = StringCchCopyW(pwszDst, 0x824u, pszRelative);
        }
      }
    }
    ILFree((LPITEMIDLIST)pidl);
    v49 = v7 == 0;
    if ( v7 < 0 )
    {
LABEL_121:
      if ( v49 )
        goto LABEL_123;
      goto LABEL_122;
    }
    if ( (a3 & 0x8000) == 0 || PathIsURLW(pwszDst) )
    {
LABEL_120:
      v49 = v7 == 0;
      goto LABEL_121;
    }
  }
LABEL_122:
  pwszDst[0] = 0;
  v7 = 1;
LABEL_123:
  v50 = SysAllocString(pwszDst);
  *v5 = v50;
  if ( !v50 )
    return (unsigned int)-2147024882;
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180025d30  mov     [rsp-8+arg_18], rbx
0x180025d35  push    rbp
0x180025d36  push    rsi
0x180025d37  push    rdi
0x180025d38  push    r12
0x180025d3a  push    r13
0x180025d3c  push    r14
0x180025d3e  push    r15
0x180025d40  lea     rbp, [rsp-3060h]
0x180025d48  mov     eax, 3160h
0x180025d4d  call    _alloca_probe
0x180025d52  sub     rsp, rax
0x180025d55  mov     rax, cs:__security_cookie
0x180025d5c  xor     rax, rsp
0x180025d5f  mov     [rbp+3090h+var_40], rax
0x180025d66  mov     rcx, [rcx+1B8h]
0x180025d6d  xor     ebx, ebx
0x180025d6f  mov     [rsp+3190h+var_3138], rdx
0x180025d74  mov     r13d, r8d
0x180025d77  mov     r12, rdx
0x180025d7a  test    rcx, rcx
0x180025d7d  jz      loc_18002643D
0x180025d83  mov     [rsp+3190h+pidl], rbx
0x180025d88  lea     rdx, [rsp+3190h+pidl]
0x180025d8d  mov     rax, [rcx]
0x180025d90  mov     rax, [rax+0B0h]
0x180025d97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025d9c  mov     esi, eax
0x180025d9e  test    eax, eax
0x180025da0  js      loc_180026439
0x180025da6  mov     r14, [rsp+3190h+pidl]
0x180025dab  lea     r9d, [rbx+2]
0x180025daf  mov     [rsp+3190h+pwszDst], bx
0x180025db4  mov     edi, 824h
0x180025db9  test    r14, r14
0x180025dbc  jz      loc_18002601A
0x180025dc2  cmp     word ptr [r14], 14h
0x180025dc7  jnz     loc_18002601A
0x180025dcd  cmp     byte ptr [r14+2], 1Fh
0x180025dd2  jnz     loc_18002601A
0x180025dd8  mov     rax, [r14+4]
0x180025ddc  sub     rax, qword ptr cs:CLSID_Internet.Data1
0x180025de3  jnz     short loc_180025DF0
0x180025de5  mov     rax, [r14+0Ch]
0x180025de9  sub     rax, qword ptr cs:CLSID_Internet.Data4
0x180025df0  test    rax, rax
0x180025df3  jnz     loc_18002601A
0x180025df9  lea     rcx, [r14+14h]; struct _ITEMIDLIST_RELATIVE *
0x180025dfd  cmp     word ptr [rcx], 0Ch
0x180025e01  jb      short loc_180025E19
0x180025e03  cmp     byte ptr [rcx+2], 61h ; 'a'
0x180025e07  jnz     short loc_180025E19
0x180025e09  test    byte ptr [rcx+3], 7Fh
0x180025e0d  jz      short loc_180025E1C
0x180025e0f  call    ?_IsValidDelegateID@@YAPEFBUDELEGATEITEMID@@PEFBU_ITEMIDLIST_RELATIVE@@@Z; _IsValidDelegateID(_ITEMIDLIST_RELATIVE const *)
0x180025e14  test    rax, rax
0x180025e17  jnz     short loc_180025E1C
0x180025e19  mov     rcx, rbx
0x180025e1c  test    rcx, rcx
0x180025e1f  jz      loc_18002601A
0x180025e25  bt      r13d, 0Fh
0x180025e2a  jnb     loc_18002601A
0x180025e30  movzx   ebx, word ptr [r14]
0x180025e34  add     rbx, r14
0x180025e37  cmp     word ptr [rbx], 0Ch
0x180025e3b  jb      loc_180026018
0x180025e41  cmp     byte ptr [rbx+2], 61h ; 'a'
0x180025e45  jnz     loc_180026018
0x180025e4b  test    byte ptr [rbx+3], 7Fh
0x180025e4f  jnz     loc_180026018
0x180025e55  mov     al, [rbx+3]
0x180025e58  xor     esi, esi
0x180025e5a  test    al, al
0x180025e5c  jnz     short loc_180025E8E
0x180025e5e  lea     r8, [rbx+8]; char *
0x180025e62  mov     rdx, rdi; unsigned __int64
0x180025e65  lea     rcx, [rbp+3090h+pszSrc]; char *
0x180025e6c  call    ?StringCbCopyA@@YAJPEAD_KPEBD@Z; StringCbCopyA(char *,unsigned __int64,char const *)
0x180025e71  mov     r8d, edi; cwchBuf
0x180025e74  lea     rdx, [rsp+3190h+pwszDst]; pwszDst
0x180025e79  lea     rcx, [rbp+3090h+pszSrc]; pszSrc
0x180025e80  call    cs:__imp_SHAnsiToUnicode
0x180025e87  nop     dword ptr [rax+rax+00h]
0x180025e8c  jmp     short loc_180025EBE
0x180025e8e  cmp     al, 80h
0x180025e90  jnz     short loc_180025EBE
0x180025e92  mov     r8d, edi
0x180025e95  lea     rax, [rbx+8]
0x180025e99  lea     rcx, [rsp+3190h+pwszDst]
0x180025e9e  movzx   edx, word ptr [rax]
0x180025ea1  test    dx, dx
0x180025ea4  jz      short loc_180025EBB
0x180025ea6  mov     [rcx], dx
0x180025ea9  add     rax, r9
0x180025eac  add     rcx, r9
0x180025eaf  sub     r8d, 1
0x180025eb3  jnz     short loc_180025E9E
0x180025eb5  mov     [rcx-2], si
0x180025eb9  jmp     short loc_180025EBE
0x180025ebb  mov     [rcx], si
0x180025ebe  mov     r15d, esi
0x180025ec1  mov     [rsp+3190h+pcchUrl], edi
0x180025ec5  mov     [rsp+3190h+pcchCombined], edi
0x180025ec9  cmp     [rbx], si
0x180025ecc  jz      loc_180025FBA
0x180025ed2  mov     rcx, rbx; pidl
0x180025ed5  call    ILFindLastID_0
0x180025eda  mov     rcx, rax
0x180025edd  mov     rdi, rax
0x180025ee0  call    ILFindFirstHiddenID
0x180025ee5  movzx   ecx, word ptr [rdi]
0x180025ee8  mov     rdx, rax
0x180025eeb  add     rdi, rcx
0x180025eee  test    rax, rax
0x180025ef1  jz      short loc_180025F24
0x180025ef3  mov     r8d, 0BEEFh
0x180025ef9  cmp     dword ptr [rdx+4], 0BEEF0002h
0x180025f00  jz      short loc_180025F24
0x180025f02  movzx   ecx, word ptr [rdx]
0x180025f05  add     rdx, rcx
0x180025f08  cmp     rdx, rdi
0x180025f0b  jnb     short loc_180025F21
0x180025f0d  mov     eax, [rdx+4]
0x180025f10  shr     rax, 10h
0x180025f14  cmp     ax, r8w
0x180025f18  jnz     short loc_180025F21
0x180025f1a  test    rdx, rdx
0x180025f1d  jnz     short loc_180025EF9
0x180025f1f  jmp     short loc_180025F24
0x180025f21  mov     rdx, rsi
0x180025f24  test    rdx, rdx
0x180025f27  jz      loc_180025FBA
0x180025f2d  mov     r9d, 2
0x180025f33  lea     rax, [rdx+0Ah]
0x180025f37  mov     r8d, 824h; cwchBuf
0x180025f3d  cmp     [rdx+8], r9w
0x180025f42  jnz     short loc_180025F6D
0x180025f44  lea     rcx, [rbp+3090h+pszRelative]
0x180025f4b  movzx   edx, word ptr [rax]
0x180025f4e  test    dx, dx
0x180025f51  jz      short loc_180025F68
0x180025f53  mov     [rcx], dx
0x180025f56  add     rax, r9
0x180025f59  add     rcx, r9
0x180025f5c  sub     r8d, 1
0x180025f60  jnz     short loc_180025F4B
0x180025f62  mov     [rcx-2], si
0x180025f66  jmp     short loc_180025F83
0x180025f68  mov     [rcx], si
0x180025f6b  jmp     short loc_180025F83
0x180025f6d  lea     rdx, [rbp+3090h+pszRelative]; pwszDst
0x180025f74  mov     rcx, rax; pszSrc
0x180025f77  call    cs:__imp_SHAnsiToUnicode
0x180025f7e  nop     dword ptr [rax+rax+00h]
0x180025f83  cmp     [rbp+3090h+pszRelative], 3Fh ; '?'
0x180025f8b  jnz     short loc_180025FBA
0x180025f8d  lea     r9, [rsp+3190h+pcchCombined]; pcchCombined
0x180025f92  mov     [rsp+3190h+dwFlags], esi; dwFlags
0x180025f96  lea     r8, [rsp+3190h+pwszDst]; pszCombined
0x180025f9b  lea     rdx, [rbp+3090h+pszRelative]; pszRelative
0x180025fa2  lea     rcx, [rsp+3190h+pwszDst]; pszBase
0x180025fa7  call    cs:__imp_UrlCombineW
0x180025fae  nop     dword ptr [rax+rax+00h]
0x180025fb3  mov     r15d, eax
0x180025fb6  test    eax, eax
0x180025fb8  js      short loc_180025FFF
0x180025fba  lea     r8, [rbp+3090h+pszRelative]
0x180025fc1  mov     edx, 0BEEF0001h
0x180025fc6  mov     rcx, rbx
0x180025fc9  call    ILGetHiddenStringW
0x180025fce  xor     ebx, ebx
0x180025fd0  test    eax, eax
0x180025fd2  jz      short loc_180026001
0x180025fd4  lea     r9, [rsp+3190h+pcchUrl]; pcchCombined
0x180025fd9  mov     [rsp+3190h+dwFlags], ebx; dwFlags
0x180025fdd  lea     r8, [rsp+3190h+pwszDst]; pszCombined
0x180025fe2  lea     rdx, [rbp+3090h+pszRelative]; pszRelative
0x180025fe9  lea     rcx, [rsp+3190h+pwszDst]; pszBase
0x180025fee  call    cs:__imp_UrlCombineW
0x180025ff5  nop     dword ptr [rax+rax+00h]
0x180025ffa  mov     r15d, eax
0x180025ffd  jmp     short loc_180026001
0x180025fff  xor     ebx, ebx
0x180026001  cmp     r15d, 80004003h
0x180026008  mov     esi, ebx
0x18002600a  cmovnz  esi, r15d
0x18002600e  test    esi, esi
0x180026010  jns     loc_18002638F
0x180026016  jmp     short loc_18002601A
0x180026018  xor     ebx, ebx
0x18002601a  mov     rax, cs:?SetEnabled@IEShimsDisableRedirection@@2P6AHH@ZEA; int (*IEShimsDisableRedirection::SetEnabled)(int)
0x180026021  test    rax, rax
0x180026024  jz      short loc_180026031
0x180026026  xor     ecx, ecx
0x180026028  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002602d  mov     edi, eax
0x18002602f  jmp     short loc_180026035
0x180026031  mov     edi, [rsp+3190h+pcchUrl]
0x180026035  mov     edx, 6; dwCoInit
0x18002603a  mov     [rsp+3190h+pwszDst], bx
0x18002603f  xor     ecx, ecx; pvReserved
0x180026041  call    cs:__imp_CoInitializeEx
0x180026048  nop     dword ptr [rax+rax+00h]
0x18002604d  mov     r15d, eax
0x180026050  test    eax, eax
0x180026052  jns     short loc_18002606A
0x180026054  mov     edx, 4; dwCoInit
0x180026059  xor     ecx, ecx; pvReserved
0x18002605b  call    cs:__imp_CoInitializeEx
0x180026062  nop     dword ptr [rax+rax+00h]
0x180026067  mov     r15d, eax
0x18002606a  lea     r9, [rsp+3190h+ppidlLast]; ppidlLast
0x18002606f  mov     [rsp+3190h+ppv], rbx
0x180026074  lea     r8, [rsp+3190h+ppv]; ppv
0x180026079  mov     [rsp+3190h+ppidlLast], rbx
0x18002607e  lea     rdx, _GUID_000214e6_0000_0000_c000_000000000046; riid
0x180026085  mov     rcx, r14; pidl
0x180026088  call    SHBindToParent_0
0x18002608d  mov     esi, eax
0x18002608f  test    eax, eax
0x180026091  js      loc_180026147
0x180026097  mov     rax, cs:?SetEnabled@IEShimsDisableRedirection@@2P6AHH@ZEA; int (*IEShimsDisableRedirection::SetEnabled)(int)
0x18002609e  mov     r12, [rsp+3190h+ppidlLast]
0x1800260a3  mov     rsi, [rsp+3190h+ppv]
0x1800260a8  test    rax, rax
0x1800260ab  jz      short loc_1800260B8
0x1800260ad  xor     ecx, ecx
0x1800260af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800260b4  mov     ebx, eax
0x1800260b6  jmp     short loc_1800260BC
0x1800260b8  mov     ebx, [rsp+3190h+pcchUrl]
0x1800260bc  xor     eax, eax
0x1800260be  lea     rcx, [rbp+3090h+pszSrc]; void *
0x1800260c5  xor     edx, edx; Val
0x1800260c7  mov     [rsp+3190h+pwszDst], ax
0x1800260cc  mov     r8d, 110h; Size
0x1800260d2  call    memset_0
0x1800260d7  mov     rax, [rsi]
0x1800260da  lea     r9, [rbp+3090h+pszSrc]
0x1800260e1  mov     r8d, r13d
0x1800260e4  mov     rdx, r12
0x1800260e7  mov     rcx, rsi
0x1800260ea  mov     rax, [rax+58h]
0x1800260ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800260f3  mov     esi, eax
0x1800260f5  test    eax, eax
0x1800260f7  js      short loc_18002611C
0x1800260f9  mov     r9d, 824h; cchBuf
0x1800260ff  lea     r8, [rsp+3190h+pwszDst]; pszBuf
0x180026104  mov     rdx, r12; pidl
0x180026107  lea     rcx, [rbp+3090h+pszSrc]; pstr
0x18002610e  call    cs:__imp_StrRetToBufW
0x180026115  nop     dword ptr [rax+rax+00h]
0x18002611a  mov     esi, eax
0x18002611c  mov     rax, cs:?SetEnabled@IEShimsDisableRedirection@@2P6AHH@ZEA; int (*IEShimsDisableRedirection::SetEnabled)(int)
0x180026123  test    rax, rax
0x180026126  jz      short loc_18002612F
0x180026128  mov     ecx, ebx
0x18002612a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002612f  mov     rcx, [rsp+3190h+ppv]
0x180026134  mov     rax, [rcx]
0x180026137  mov     rax, [rax+10h]
0x18002613b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026140  mov     r12, [rsp+3190h+var_3138]
0x180026145  xor     ebx, ebx
0x180026147  test    r15d, r15d
0x18002614a  js      short loc_180026158
0x18002614c  call    cs:__imp_CoUninitialize
0x180026153  nop     dword ptr [rax+rax+00h]
0x180026158  mov     rax, cs:?SetEnabled@IEShimsDisableRedirection@@2P6AHH@ZEA; int (*IEShimsDisableRedirection::SetEnabled)(int)
0x18002615f  test    rax, rax
0x180026162  jz      short loc_18002616B
0x180026164  mov     ecx, edi
0x180026166  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002616b  test    esi, esi
0x18002616d  js      loc_180026408
0x180026173  mov     r15d, r13d
0x180026176  and     r15d, 8000h
0x18002617d  jz      loc_180026386
0x180026183  mov     esi, 824h
0x180026188  mov     edi, ebx
0x18002618a  mov     [rsp+3190h+pcchCombined], esi
0x18002618e  mov     [rsp+3190h+pcchUrl], esi
0x180026192  test    r14, r14
0x180026195  jz      loc_1800262AE
0x18002619b  cmp     [r14], bx
0x18002619f  jz      loc_1800262AE
0x1800261a5  mov     rcx, r14; pidl
0x1800261a8  call    ILFindLastID_0
0x1800261ad  movzx   r8d, word ptr [rax]
0x1800261b1  lea     r10, [rax+r8]
0x1800261b5  movzx   r9d, word ptr [r10-2]
0x1800261ba  test    r9w, r9w
0x1800261be  jz      short loc_180026215
0x1800261c0  lea     rcx, [r9+8]
0x1800261c4  mov     edx, r9d
0x1800261c7  cmp     rcx, r8
0x1800261ca  jnb     short loc_180026215
0x1800261cc  add     rdx, rax
0x1800261cf  mov     r11d, 0BEEFh
  ... truncated ...
```
