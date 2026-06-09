# CIEFrameAuto::_get_Location(ushort * *,uint)

- ea: `0x1800413e0`
- end: `0x180041b06`
- name: `?_get_Location@CIEFrameAuto@@IEAAJPEAPEAGI@Z`
- size: `1830`
- prototype: `__int64 __fastcall(CIEFrameAuto *__hidden this, unsigned __int16 **, unsigned int)`
- caller_count: `4`
- callee_count: `14`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1801028b4`
- `0x18010639c`
- `0x18010bb70`
- `0x18010bb90`

## callees

- `0x180011230`
- `0x1800231c4`
- `0x180024180`
- `0x1800413e0`
- `0x180041b0c`
- `0x180041c20`
- `0x1800bab8c`
- `0x1800babd4`
- `0x1800bf808`
- `0x1804e6f3c`
- `0x18054e286`
- `0x18054e310`
- `0x18054e3d0`
- `0x180550010`

## import_xrefs

- `SHLWAPI!StrRetToBufW` at `0x1800417b2`
- `SHLWAPI!StrRetToBufW` at `0x1800417b2`
- `api-ms-win-downlevel-shlwapi-l1-1-0!UrlCreateFromPathW` at `0x180041a6b`
- `api-ms-win-downlevel-shlwapi-l1-1-0!UrlCreateFromPathW` at `0x180041a6b`
- `api-ms-win-downlevel-shlwapi-l1-1-0!UrlCombineW` at `0x180041667`
- `api-ms-win-downlevel-shlwapi-l1-1-0!UrlCombineW` at `0x1800416a7`
- `api-ms-win-downlevel-shlwapi-l1-1-0!UrlCombineW` at `0x18004192a`
- `api-ms-win-downlevel-shlwapi-l1-1-0!UrlCombineW` at `0x1800419fb`
- `api-ms-win-downlevel-shlwapi-l1-1-0!UrlCombineW` at `0x180041667`
- `api-ms-win-downlevel-shlwapi-l1-1-0!UrlCombineW` at `0x1800416a7`
- `api-ms-win-downlevel-shlwapi-l1-1-0!UrlCombineW` at `0x18004192a`
- `api-ms-win-downlevel-shlwapi-l1-1-0!UrlCombineW` at `0x1800419fb`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathIsURLW` at `0x180041aa8`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathIsURLW` at `0x180041aa8`
- `OLEAUT32!__imp_SysAllocString` at `0x180041ac5`
- `OLEAUT32!__imp_SysAllocString` at `0x180041ac5`
- `SHELL32!__imp_ILFree` at `0x180041a92`
- `SHELL32!__imp_ILFree` at `0x180041a92`
- `api-ms-win-downlevel-ole32-l1-1-0!CoInitializeEx` at `0x1800416f1`
- `api-ms-win-downlevel-ole32-l1-1-0!CoInitializeEx` at `0x180041705`
- `api-ms-win-downlevel-ole32-l1-1-0!CoInitializeEx` at `0x1800416f1`
- `api-ms-win-downlevel-ole32-l1-1-0!CoInitializeEx` at `0x180041705`
- `api-ms-win-downlevel-ole32-l1-1-0!CoUninitialize` at `0x1800417ea`
- `api-ms-win-downlevel-ole32-l1-1-0!CoUninitialize` at `0x1800417ea`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHAnsiToUnicode` at `0x180041531`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHAnsiToUnicode` at `0x18004163d`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHAnsiToUnicode` at `0x180041900`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHAnsiToUnicode` at `0x1800419d1`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHAnsiToUnicode` at `0x180041531`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHAnsiToUnicode` at `0x18004163d`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHAnsiToUnicode` at `0x180041900`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHAnsiToUnicode` at `0x1800419d1`

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
  HRESULT v18; // edi
  LPITEMIDLIST ID_0; // rax
  unsigned __int64 cb; // r8
  __int64 v21; // r9
  unsigned __int16 *v22; // rdx
  const CHAR *v23; // rax
  int v24; // r8d
  WCHAR *v25; // rcx
  DWORD v26; // edi
  HRESULT v27; // r15d
  __int64 v28; // rdx
  __int64 v29; // r8
  __int64 v30; // r9
  const ITEMIDLIST *v31; // r12
  void *v32; // rsi
  DWORD v33; // ebx
  __int64 v34; // rdx
  __int64 v35; // r8
  __int64 v36; // r9
  HRESULT v37; // edi
  LPITEMIDLIST v38; // rax
  unsigned __int64 v39; // r8
  __int64 v40; // r9
  unsigned __int16 *v41; // rdx
  const CHAR *v42; // rax
  int v43; // r8d
  STRRET *v44; // rcx
  LPITEMIDLIST v45; // rbx
  unsigned __int16 *HiddenID; // rdx
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
      goto LABEL_123;
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
                goto LABEL_131;
              ID_0 = ILFindLastID_0((LPCITEMIDLIST)v13);
              cb = ID_0->mkid.cb;
              v21 = *(unsigned __int16 *)((char *)ID_0 + cb - 2);
              if ( (_WORD)v21
                && v21 + 8 < cb
                && (v22 = (USHORT *)((char *)&ID_0->mkid.cb + *(unsigned __int16 *)((char *)ID_0 + cb - 2)),
                    HIWORD(*((_DWORD *)v22 + 1)) == 0xBEEF)
                && (unsigned int)v21 + *v22 <= (unsigned int)cb )
              {
                while ( *((_DWORD *)v22 + 1) != -1091633150 )
                {
                  v22 = (unsigned __int16 *)((char *)v22 + *v22);
                  if ( v22 >= (unsigned __int16 *)((char *)&ID_0->mkid.cb + cb)
                    || HIWORD(*((_DWORD *)v22 + 1)) != 0xBEEF )
                  {
                    goto LABEL_37;
                  }
                  if ( !v22 )
                    break;
                }
              }
              else
              {
LABEL_37:
                v22 = 0;
              }
              if ( !v22 )
                goto LABEL_131;
              v23 = (const CHAR *)(v22 + 5);
              v24 = 2084;
              if ( v22[4] == 2 )
              {
                v25 = pszRelative;
                while ( *(_WORD *)v23 )
                {
                  *v25 = *(_WORD *)v23;
                  v23 += 2;
                  ++v25;
                  if ( !--v24 )
                  {
                    *(v25 - 1) = 0;
                    goto LABEL_46;
                  }
                }
                *v25 = 0;
              }
              else
              {
                SHAnsiToUnicode(v23, pszRelative, 2084);
              }
LABEL_46:
              if ( pszRelative[0] != 63
                || (v18 = UrlCombineW(pwszDst, pszRelative, pwszDst, &pcchCombined, 0), v18 >= 0) )
              {
LABEL_131:
                if ( (unsigned int)ILGetHiddenStringW(v13, 3203334145LL, pszRelative) )
                  v18 = UrlCombineW(pwszDst, pszRelative, pwszDst, &pcchUrl, 0);
              }
              v7 = 0;
              if ( v18 != -2147467261 )
                v7 = v18;
              if ( v7 >= 0 )
                goto LABEL_114;
            }
          }
        }
      }
    }
    if ( IEShimsDisableRedirection::SetEnabled )
      v26 = IEShimsDisableRedirection::SetEnabled(0, v6, v8, v10);
    else
      v26 = pcchUrl;
    pwszDst[0] = 0;
    v27 = CoInitializeEx(0, 6u);
    if ( v27 < 0 )
      v27 = CoInitializeEx(0, 4u);
    ppv = 0;
    ppidlLast = 0;
    v7 = SHBindToParent_0(v9, &GUID_000214e6_0000_0000_c000_000000000046, &ppv, &ppidlLast);
    if ( v7 >= 0 )
    {
      v31 = ppidlLast;
      v32 = ppv;
      if ( IEShimsDisableRedirection::SetEnabled )
        v33 = IEShimsDisableRedirection::SetEnabled(0, v28, v29, v30);
      else
        v33 = pcchUrl;
      pwszDst[0] = 0;
      memset_0(pszSrc, 0, 0x110u);
      v7 = (*(__int64 (__fastcall **)(void *, const ITEMIDLIST *, _QWORD, STRRET *))(*(_QWORD *)v32 + 88LL))(
             v32,
             v31,
             a3,
             pszSrc);
      if ( v7 >= 0 )
        v7 = StrRetToBufW(pszSrc, v31, pwszDst, 0x824u);
      if ( IEShimsDisableRedirection::SetEnabled )
        IEShimsDisableRedirection::SetEnabled(v33, v34, v35, v36);
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
      v5 = v57;
    }
    if ( v27 >= 0 )
      CoUninitialize();
    if ( IEShimsDisableRedirection::SetEnabled )
      IEShimsDisableRedirection::SetEnabled(v26, v28, v29, v30);
    if ( v7 >= 0 )
    {
      if ( (a3 & 0x8000) != 0 )
      {
        v37 = 0;
        pcchCombined = 2084;
        pcchUrl = 2084;
        if ( v9 && v9->mkid.cb )
        {
          v38 = ILFindLastID_0(v9);
          v39 = v38->mkid.cb;
          v40 = *(unsigned __int16 *)((char *)v38 + v39 - 2);
          if ( (_WORD)v40
            && v40 + 8 < v39
            && (v41 = (USHORT *)((char *)&v38->mkid.cb + *(unsigned __int16 *)((char *)v38 + v39 - 2)),
                HIWORD(*((_DWORD *)v41 + 1)) == 0xBEEF)
            && (unsigned int)v40 + *v41 <= (unsigned int)v39 )
          {
            while ( *((_DWORD *)v41 + 1) != -1091633150 )
            {
              v41 = (unsigned __int16 *)((char *)v41 + *v41);
              if ( v41 >= (unsigned __int16 *)((char *)&v38->mkid.cb + v39) || HIWORD(*((_DWORD *)v41 + 1)) != 0xBEEF )
                goto LABEL_84;
              if ( !v41 )
                break;
            }
          }
          else
          {
LABEL_84:
            v41 = 0;
          }
          if ( !v41 )
            goto LABEL_132;
          v42 = (const CHAR *)(v41 + 5);
          v43 = 2084;
          if ( v41[4] == 2 )
          {
            v44 = pszSrc;
            while ( *(_WORD *)v42 )
            {
              LOWORD(v44->uType) = *(_WORD *)v42;
              v42 += 2;
              v44 = (STRRET *)((char *)v44 + 2);
              if ( !--v43 )
              {
                *(_WORD *)&v44[-1].cStr[262] = 0;
                goto LABEL_93;
              }
            }
            LOWORD(v44->uType) = 0;
          }
          else
          {
            SHAnsiToUnicode(v42, (PWSTR)pszSrc, 2084);
          }
LABEL_93:
          if ( LOWORD(pszSrc[0].uType) != 63
            || (v37 = UrlCombineW(pwszDst, (PCWSTR)pszSrc, pwszDst, &pcchUrl, 0), v37 >= 0) )
          {
LABEL_132:
            if ( v9->mkid.cb )
            {
              v45 = ILFindLastID_0(v9);
              HiddenID = (unsigned __int16 *)ILFindFirstHiddenID(v45);
              v47 = (USHORT *)((char *)&v45->mkid.cb + v45->mkid.cb);
              if ( HiddenID )
              {
                while ( *((_DWORD *)HiddenID + 1) != -1091633151 )
                {
                  HiddenID = (unsigned __int16 *)((char *)HiddenID + *HiddenID);
                  if ( HiddenID >= v47 || HIWORD(*((_DWORD *)HiddenID + 1)) != 0xBEEF )
                  {
                    HiddenID = 0;
                    break;
                  }
                  if ( !HiddenID )
                    break;
                }
              }
              if ( HiddenID )
              {
                if ( HiddenID[4] == 2 )
                  ualstrcpynW(pszSrc, HiddenID + 5, 2084);
                else
                  SHAnsiToUnicode((PCSTR)HiddenID + 10, (PWSTR)pszSrc, 2084);
                if ( LOWORD(pszSrc[0].uType) == 35 )
                  v37 = UrlCombineW(pwszDst, (PCWSTR)pszSrc, pwszDst, &pcchCombined, 0);
              }
            }
          }
        }
        v7 = 0;
        if ( v37 != -2147467261 )
          v7 = v37;
      }
      if ( v7 >= 0 && (a3 & 0x8000) != 0 )
      {
LABEL_114:
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
LABEL_124:
      if ( v49 )
        goto LABEL_126;
      goto LABEL_125;
    }
    if ( (a3 & 0x8000) == 0 || PathIsURLW(pwszDst) )
    {
LABEL_123:
      v49 = v7 == 0;
      goto LABEL_124;
    }
  }
LABEL_125:
  pwszDst[0] = 0;
  v7 = 1;
LABEL_126:
  v50 = SysAllocString(pwszDst);
  *v5 = v50;
  if ( !v50 )
    return (unsigned int)-2147024882;
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800413e0  mov     [rsp-8+arg_18], rbx
0x1800413e5  push    rbp
0x1800413e6  push    rsi
0x1800413e7  push    rdi
0x1800413e8  push    r12
0x1800413ea  push    r13
0x1800413ec  push    r14
0x1800413ee  push    r15
0x1800413f0  lea     rbp, [rsp-3060h]
0x1800413f8  mov     eax, 3160h
0x1800413fd  call    _alloca_probe
0x180041402  sub     rsp, rax
0x180041405  mov     rax, cs:__security_cookie
0x18004140c  xor     rax, rsp
0x18004140f  mov     [rbp+3090h+var_40], rax
0x180041416  mov     rcx, [rcx+1B8h]
0x18004141d  xor     ebx, ebx
0x18004141f  mov     [rsp+3190h+var_3138], rdx
0x180041424  mov     r13d, r8d
0x180041427  mov     r12, rdx
0x18004142a  test    rcx, rcx
0x18004142d  jz      loc_180041AB6
0x180041433  mov     [rsp+3190h+pidl], rbx
0x180041438  lea     rdx, [rsp+3190h+pidl]
0x18004143d  mov     rax, [rcx]
0x180041440  mov     rax, [rax+0B0h]
0x180041447  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004144c  mov     esi, eax
0x18004144e  test    eax, eax
0x180041450  js      loc_180041AB2
0x180041456  mov     r14, [rsp+3190h+pidl]
0x18004145b  lea     r9d, [rbx+2]
0x18004145f  mov     [rsp+3190h+pwszDst], bx
0x180041464  mov     r15d, 824h
0x18004146a  test    r14, r14
0x18004146d  jz      loc_1800416CA
0x180041473  cmp     word ptr [r14], 14h
0x180041478  jnz     loc_1800416CA
0x18004147e  cmp     byte ptr [r14+2], 1Fh
0x180041483  jnz     loc_1800416CA
0x180041489  mov     rax, [r14+4]
0x18004148d  sub     rax, qword ptr cs:CLSID_Internet.Data1
0x180041494  jnz     short loc_1800414A1
0x180041496  mov     rax, [r14+0Ch]
0x18004149a  sub     rax, qword ptr cs:CLSID_Internet.Data4
0x1800414a1  test    rax, rax
0x1800414a4  jnz     loc_1800416CA
0x1800414aa  lea     rcx, [r14+14h]; struct _ITEMIDLIST_RELATIVE *
0x1800414ae  cmp     word ptr [rcx], 0Ch
0x1800414b2  jb      short loc_1800414CA
0x1800414b4  cmp     byte ptr [rcx+2], 61h ; 'a'
0x1800414b8  jnz     short loc_1800414CA
0x1800414ba  test    byte ptr [rcx+3], 7Fh
0x1800414be  jz      short loc_1800414CD
0x1800414c0  call    ?_IsValidDelegateID@@YAPEFBUDELEGATEITEMID@@PEFBU_ITEMIDLIST_RELATIVE@@@Z; _IsValidDelegateID(_ITEMIDLIST_RELATIVE const *)
0x1800414c5  test    rax, rax
0x1800414c8  jnz     short loc_1800414CD
0x1800414ca  mov     rcx, rbx
0x1800414cd  test    rcx, rcx
0x1800414d0  jz      loc_1800416CA
0x1800414d6  bt      r13d, 0Fh
0x1800414db  jnb     loc_1800416CA
0x1800414e1  movzx   ebx, word ptr [r14]
0x1800414e5  add     rbx, r14
0x1800414e8  cmp     word ptr [rbx], 0Ch
0x1800414ec  jb      loc_1800416C8
0x1800414f2  cmp     byte ptr [rbx+2], 61h ; 'a'
0x1800414f6  jnz     loc_1800416C8
0x1800414fc  test    byte ptr [rbx+3], 7Fh
0x180041500  jnz     loc_1800416C8
0x180041506  mov     al, [rbx+3]
0x180041509  xor     esi, esi
0x18004150b  test    al, al
0x18004150d  jnz     short loc_180041539
0x18004150f  lea     r8, [rbx+8]; char *
0x180041513  mov     rdx, r15; unsigned __int64
0x180041516  lea     rcx, [rbp+3090h+pszSrc]; char *
0x18004151d  call    ?StringCbCopyA@@YAJPEAD_KPEBD@Z; StringCbCopyA(char *,unsigned __int64,char const *)
0x180041522  mov     r8d, r15d; cwchBuf
0x180041525  lea     rdx, [rsp+3190h+pwszDst]; pwszDst
0x18004152a  lea     rcx, [rbp+3090h+pszSrc]; pszSrc
0x180041531  call    cs:__imp_SHAnsiToUnicode
0x180041537  jmp     short loc_180041569
0x180041539  cmp     al, 80h
0x18004153b  jnz     short loc_180041569
0x18004153d  mov     r8d, r15d
0x180041540  lea     rax, [rbx+8]
0x180041544  lea     rcx, [rsp+3190h+pwszDst]
0x180041549  movzx   edx, word ptr [rax]
0x18004154c  test    dx, dx
0x18004154f  jz      short loc_180041566
0x180041551  mov     [rcx], dx
0x180041554  add     rax, r9
0x180041557  add     rcx, r9
0x18004155a  sub     r8d, 1
0x18004155e  jnz     short loc_180041549
0x180041560  mov     [rcx-2], si
0x180041564  jmp     short loc_180041569
0x180041566  mov     [rcx], si
0x180041569  mov     edi, esi
0x18004156b  mov     [rsp+3190h+pcchUrl], r15d
0x180041570  mov     [rsp+3190h+pcchCombined], r15d
0x180041575  cmp     [rbx], si
0x180041578  jz      loc_180041673
0x18004157e  mov     rcx, rbx; pidl
0x180041581  call    ILFindLastID_0
0x180041586  movzx   r8d, word ptr [rax]
0x18004158a  lea     r10, [rax+r8]
0x18004158e  movzx   r9d, word ptr [r10-2]
0x180041593  test    r9w, r9w
0x180041597  jz      short loc_1800415EE
0x180041599  lea     rcx, [r9+8]
0x18004159d  mov     edx, r9d
0x1800415a0  cmp     rcx, r8
0x1800415a3  jnb     short loc_1800415EE
0x1800415a5  add     rdx, rax
0x1800415a8  mov     r11d, 0BEEFh
0x1800415ae  mov     eax, [rdx+4]
0x1800415b1  shr     rax, 10h
0x1800415b5  cmp     ax, r11w
0x1800415b9  jnz     short loc_1800415EE
0x1800415bb  movzx   ecx, word ptr [rdx]
0x1800415be  add     ecx, r9d
0x1800415c1  cmp     ecx, r8d
0x1800415c4  ja      short loc_1800415EE
0x1800415c6  cmp     dword ptr [rdx+4], 0BEEF0002h
0x1800415cd  jz      short loc_1800415F1
0x1800415cf  movzx   eax, word ptr [rdx]
0x1800415d2  add     rdx, rax
0x1800415d5  cmp     rdx, r10
0x1800415d8  jnb     short loc_1800415EE
0x1800415da  mov     eax, [rdx+4]
0x1800415dd  shr     rax, 10h
0x1800415e1  cmp     ax, r11w
0x1800415e5  jnz     short loc_1800415EE
0x1800415e7  test    rdx, rdx
0x1800415ea  jnz     short loc_1800415C6
0x1800415ec  jmp     short loc_1800415F1
0x1800415ee  mov     rdx, rsi
0x1800415f1  test    rdx, rdx
0x1800415f4  jz      short loc_180041673
0x1800415f6  mov     r9d, 2
0x1800415fc  lea     rax, [rdx+0Ah]
0x180041600  mov     r8d, r15d; cwchBuf
0x180041603  cmp     [rdx+8], r9w
0x180041608  jnz     short loc_180041633
0x18004160a  lea     rcx, [rbp+3090h+pszRelative]
0x180041611  movzx   edx, word ptr [rax]
0x180041614  test    dx, dx
0x180041617  jz      short loc_18004162E
0x180041619  mov     [rcx], dx
0x18004161c  add     rax, r9
0x18004161f  add     rcx, r9
0x180041622  sub     r8d, 1
0x180041626  jnz     short loc_180041611
0x180041628  mov     [rcx-2], si
0x18004162c  jmp     short loc_180041643
0x18004162e  mov     [rcx], si
0x180041631  jmp     short loc_180041643
0x180041633  lea     rdx, [rbp+3090h+pszRelative]; pwszDst
0x18004163a  mov     rcx, rax; pszSrc
0x18004163d  call    cs:__imp_SHAnsiToUnicode
0x180041643  cmp     [rbp+3090h+pszRelative], 3Fh ; '?'
0x18004164b  jnz     short loc_180041673
0x18004164d  lea     r9, [rsp+3190h+pcchCombined]; pcchCombined
0x180041652  mov     [rsp+3190h+dwFlags], esi; dwFlags
0x180041656  lea     r8, [rsp+3190h+pwszDst]; pszCombined
0x18004165b  lea     rdx, [rbp+3090h+pszRelative]; pszRelative
0x180041662  lea     rcx, [rsp+3190h+pwszDst]; pszBase
0x180041667  call    cs:__imp_UrlCombineW
0x18004166d  mov     edi, eax
0x18004166f  test    eax, eax
0x180041671  js      short loc_1800416B1
0x180041673  lea     r8, [rbp+3090h+pszRelative]
0x18004167a  mov     edx, 0BEEF0001h
0x18004167f  mov     rcx, rbx
0x180041682  call    ILGetHiddenStringW
0x180041687  xor     ebx, ebx
0x180041689  test    eax, eax
0x18004168b  jz      short loc_1800416B3
0x18004168d  lea     r9, [rsp+3190h+pcchUrl]; pcchCombined
0x180041692  mov     [rsp+3190h+dwFlags], ebx; dwFlags
0x180041696  lea     r8, [rsp+3190h+pwszDst]; pszCombined
0x18004169b  lea     rdx, [rbp+3090h+pszRelative]; pszRelative
0x1800416a2  lea     rcx, [rsp+3190h+pwszDst]; pszBase
0x1800416a7  call    cs:__imp_UrlCombineW
0x1800416ad  mov     edi, eax
0x1800416af  jmp     short loc_1800416B3
0x1800416b1  xor     ebx, ebx
0x1800416b3  cmp     edi, 80004003h
0x1800416b9  mov     esi, ebx
0x1800416bb  cmovnz  esi, edi
0x1800416be  test    esi, esi
0x1800416c0  jns     loc_180041A1D
0x1800416c6  jmp     short loc_1800416CA
0x1800416c8  xor     ebx, ebx
0x1800416ca  mov     rax, cs:?SetEnabled@IEShimsDisableRedirection@@2P6AHH@ZEA; int (*IEShimsDisableRedirection::SetEnabled)(int)
0x1800416d1  test    rax, rax
0x1800416d4  jz      short loc_1800416E1
0x1800416d6  xor     ecx, ecx
0x1800416d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800416dd  mov     edi, eax
0x1800416df  jmp     short loc_1800416E5
0x1800416e1  mov     edi, [rsp+3190h+pcchUrl]
0x1800416e5  mov     edx, 6; dwCoInit
0x1800416ea  mov     [rsp+3190h+pwszDst], bx
0x1800416ef  xor     ecx, ecx; pvReserved
0x1800416f1  call    cs:__imp_CoInitializeEx
0x1800416f7  mov     r15d, eax
0x1800416fa  test    eax, eax
0x1800416fc  jns     short loc_18004170E
0x1800416fe  mov     edx, 4; dwCoInit
0x180041703  xor     ecx, ecx; pvReserved
0x180041705  call    cs:__imp_CoInitializeEx
0x18004170b  mov     r15d, eax
0x18004170e  lea     r9, [rsp+3190h+ppidlLast]; ppidlLast
0x180041713  mov     [rsp+3190h+ppv], rbx
0x180041718  lea     r8, [rsp+3190h+ppv]; ppv
0x18004171d  mov     [rsp+3190h+ppidlLast], rbx
0x180041722  lea     rdx, _GUID_000214e6_0000_0000_c000_000000000046; riid
0x180041729  mov     rcx, r14; pidl
0x18004172c  call    SHBindToParent_0
0x180041731  mov     esi, eax
0x180041733  test    eax, eax
0x180041735  js      loc_1800417E5
0x18004173b  mov     rax, cs:?SetEnabled@IEShimsDisableRedirection@@2P6AHH@ZEA; int (*IEShimsDisableRedirection::SetEnabled)(int)
0x180041742  mov     r12, [rsp+3190h+ppidlLast]
0x180041747  mov     rsi, [rsp+3190h+ppv]
0x18004174c  test    rax, rax
0x18004174f  jz      short loc_18004175C
0x180041751  xor     ecx, ecx
0x180041753  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041758  mov     ebx, eax
0x18004175a  jmp     short loc_180041760
0x18004175c  mov     ebx, [rsp+3190h+pcchUrl]
0x180041760  xor     eax, eax
0x180041762  lea     rcx, [rbp+3090h+pszSrc]; void *
0x180041769  xor     edx, edx; Val
0x18004176b  mov     [rsp+3190h+pwszDst], ax
0x180041770  mov     r8d, 110h; Size
0x180041776  call    memset_0
0x18004177b  mov     rax, [rsi]
0x18004177e  lea     r9, [rbp+3090h+pszSrc]
0x180041785  mov     r8d, r13d
0x180041788  mov     rdx, r12
0x18004178b  mov     rcx, rsi
0x18004178e  mov     rax, [rax+58h]
0x180041792  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041797  mov     esi, eax
0x180041799  test    eax, eax
0x18004179b  js      short loc_1800417BA
0x18004179d  mov     r9d, 824h; cchBuf
0x1800417a3  lea     r8, [rsp+3190h+pwszDst]; pszBuf
0x1800417a8  mov     rdx, r12; pidl
0x1800417ab  lea     rcx, [rbp+3090h+pszSrc]; pstr
0x1800417b2  call    cs:__imp_StrRetToBufW
0x1800417b8  mov     esi, eax
0x1800417ba  mov     rax, cs:?SetEnabled@IEShimsDisableRedirection@@2P6AHH@ZEA; int (*IEShimsDisableRedirection::SetEnabled)(int)
0x1800417c1  test    rax, rax
0x1800417c4  jz      short loc_1800417CD
0x1800417c6  mov     ecx, ebx
0x1800417c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800417cd  mov     rcx, [rsp+3190h+ppv]
0x1800417d2  mov     rax, [rcx]
0x1800417d5  mov     rax, [rax+10h]
0x1800417d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800417de  mov     r12, [rsp+3190h+var_3138]
0x1800417e3  xor     ebx, ebx
0x1800417e5  test    r15d, r15d
0x1800417e8  js      short loc_1800417F0
0x1800417ea  call    cs:__imp_CoUninitialize
0x1800417f0  mov     rax, cs:?SetEnabled@IEShimsDisableRedirection@@2P6AHH@ZEA; int (*IEShimsDisableRedirection::SetEnabled)(int)
0x1800417f7  test    rax, rax
0x1800417fa  jz      short loc_180041803
0x1800417fc  mov     ecx, edi
0x1800417fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041803  test    esi, esi
0x180041805  js      loc_180041A8D
0x18004180b  mov     r15d, r13d
0x18004180e  and     r15d, 8000h
0x180041815  jz      loc_180041A0E
0x18004181b  mov     esi, 824h
0x180041820  mov     edi, ebx
0x180041822  mov     [rsp+3190h+pcchCombined], esi
0x180041826  mov     [rsp+3190h+pcchUrl], esi
0x18004182a  test    r14, r14
0x18004182d  jz      loc_180041A03
0x180041833  cmp     [r14], bx
0x180041837  jz      loc_180041A03
0x18004183d  mov     rcx, r14; pidl
0x180041840  call    ILFindLastID_0
0x180041845  movzx   r8d, word ptr [rax]
0x180041849  lea     r10, [rax+r8]
0x18004184d  movzx   r9d, word ptr [r10-2]
0x180041852  test    r9w, r9w
0x180041856  jz      short loc_1800418AD
0x180041858  lea     rcx, [r9+8]
0x18004185c  mov     edx, r9d
0x18004185f  cmp     rcx, r8
0x180041862  jnb     short loc_1800418AD
  ... truncated ...
```
