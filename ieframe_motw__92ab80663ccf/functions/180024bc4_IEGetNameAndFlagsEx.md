# IEGetNameAndFlagsEx

- ea: `0x180024bc4`
- end: `0x18002561d`
- name: `IEGetNameAndFlagsEx`
- size: `2649`
- prototype: `__int64 __fastcall(int, int, int, int, UINT cchBuf, __int64)`
- caller_count: `101`
- callee_count: `17`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180014bac`
- `0x180023c68`
- `0x180023f50`
- `0x180026830`
- `0x180033dd8`
- `0x18005ebb4`
- `0x180073110`
- `0x180083ed0`
- `0x18008f660`
- `0x180098894`
- `0x180099a08`
- `0x1800a7620`
- `0x1800b4b40`
- `0x1800cf7b0`
- `0x1800cfaa8`
- `0x1800d1850`
- `0x1800d98a0`
- `0x1800ddc78`
- `0x1800dede4`
- `0x1800dfbe0`
- `0x1800e02cc`
- `0x1800e0c68`
- `0x1800e1164`
- `0x1800f80c8`
- `0x180100098`
- `0x180101460`
- `0x180103b78`
- `0x18013f14c`
- `0x180143cf0`
- `0x1801492ec`
- `0x1801494e4`
- `0x180196f40`
- `0x1801b0750`
- `0x1801b6070`
- `0x1801b6610`
- `0x1801b6948`
- `0x1801b7fe8`
- `0x1801b824c`
- `0x1801b86b0`
- `0x1801b8cd4`
- `0x1801b9868`
- `0x1801bb038`
- `0x1801bc400`
- `0x1801bc9d0`
- `0x1801bcfe0`
- `0x1801be170`
- `0x1801d3740`
- `0x1801e269c`
- `0x1801e27bc`
- `0x1801e4e9c`

## callees

- `0x180005030`
- `0x1800144d0`
- `0x180023c4c`
- `0x180024b74`
- `0x180024bc4`
- `0x18002649c`
- `0x180056d9c`
- `0x180076974`
- `0x1800c18bc`
- `0x1800c1904`
- `0x1800c663c`
- `0x180525568`
- `0x18057b21c`
- `0x180591ef6`
- `0x180591f80`
- `0x180592040`
- `0x180594010`

## import_xrefs

- `SHLWAPI!StrRetToBufW` at `0x180024e5d`
- `SHLWAPI!StrRetToBufW` at `0x180024e5d`
- `api-ms-win-downlevel-shlwapi-l1-1-0!UrlCreateFromPathW` at `0x1800255ef`
- `api-ms-win-downlevel-shlwapi-l1-1-0!UrlCreateFromPathW` at `0x1800255ef`
- `api-ms-win-downlevel-shlwapi-l1-1-0!UrlCombineW` at `0x1800251ea`
- `api-ms-win-downlevel-shlwapi-l1-1-0!UrlCombineW` at `0x1800252f5`
- `api-ms-win-downlevel-shlwapi-l1-1-0!UrlCombineW` at `0x1800253b7`
- `api-ms-win-downlevel-shlwapi-l1-1-0!UrlCombineW` at `0x18002543e`
- `api-ms-win-downlevel-shlwapi-l1-1-0!UrlCombineW` at `0x1800251ea`
- `api-ms-win-downlevel-shlwapi-l1-1-0!UrlCombineW` at `0x1800252f5`
- `api-ms-win-downlevel-shlwapi-l1-1-0!UrlCombineW` at `0x1800253b7`
- `api-ms-win-downlevel-shlwapi-l1-1-0!UrlCombineW` at `0x18002543e`
- `iertutil!CreateUri` at `0x180024fbd`
- `iertutil!CreateUri` at `0x180024fbd`
- `api-ms-win-downlevel-ole32-l1-1-0!CoInitializeEx` at `0x180024d9a`
- `api-ms-win-downlevel-ole32-l1-1-0!CoInitializeEx` at `0x18002550b`
- `api-ms-win-downlevel-ole32-l1-1-0!CoInitializeEx` at `0x180024d9a`
- `api-ms-win-downlevel-ole32-l1-1-0!CoInitializeEx` at `0x18002550b`
- `api-ms-win-downlevel-ole32-l1-1-0!CoUninitialize` at `0x180024e9f`
- `api-ms-win-downlevel-ole32-l1-1-0!CoUninitialize` at `0x180024e9f`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHAnsiToUnicode` at `0x180025287`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHAnsiToUnicode` at `0x18002534e`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHAnsiToUnicode` at `0x1800253d1`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHAnsiToUnicode` at `0x180025458`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHAnsiToUnicode` at `0x1800254c8`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHAnsiToUnicode` at `0x180025287`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHAnsiToUnicode` at `0x18002534e`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHAnsiToUnicode` at `0x1800253d1`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHAnsiToUnicode` at `0x180025458`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHAnsiToUnicode` at `0x1800254c8`

## pseudocode

```c
__int64 __fastcall IEGetNameAndFlagsEx(
        unsigned __int16 *a1,
        unsigned __int64 a2,
        unsigned __int64 cb,
        WCHAR *a4,
        UINT cchBuf,
        unsigned int *a6)
{
  unsigned int *v6; // r12
  unsigned __int16 *v8; // r11
  char v9; // si
  __int64 v11; // r9
  __int64 v12; // rax
  unsigned __int16 *v13; // rcx
  char *v14; // rbx
  char v15; // al
  DWORD v16; // r15d
  unsigned __int16 *v17; // rax
  WCHAR *v18; // rcx
  HRESULT v19; // edi
  LPITEMIDLIST ID_0; // rax
  HRESULT v21; // esi
  DWORD v22; // edi
  HRESULT v23; // r15d
  HRESULT v24; // eax
  __int64 v25; // rdx
  __int64 v26; // r8
  __int64 v27; // r9
  const ITEMIDLIST *v28; // r12
  void *v29; // rsi
  DWORD v30; // ebx
  __int64 v31; // rdx
  __int64 v32; // r8
  __int64 v33; // r9
  HRESULT v34; // edi
  LPITEMIDLIST v35; // rax
  unsigned __int64 v36; // r8
  __int64 v37; // r9
  unsigned __int16 *v38; // rdx
  char v39; // r12
  LPITEMIDLIST v41; // rbx
  __int64 v42; // rax
  unsigned __int16 *v43; // rbx
  unsigned __int16 *v44; // rdx
  const CHAR *v45; // rax
  int v46; // r8d
  WCHAR *v47; // rcx
  HRESULT v48; // eax
  const ITEMIDLIST *v49; // rcx
  LPITEMIDLIST v50; // rbx
  __int64 HiddenID; // rax
  char *v52; // rbx
  const CHAR *v53; // rax
  WCHAR *v54; // rcx
  HRESULT v55; // eax
  const CHAR *v56; // rax
  int v57; // r8d
  WCHAR *v58; // rcx
  const CHAR *v59; // rax
  WCHAR *v60; // rcx
  const struct DELEGATEITEMID *v61; // rax
  unsigned int v62; // r8d
  DWORD v64; // [rsp+30h] [rbp-D0h] BYREF
  int Uri; // [rsp+38h] [rbp-C8h] BYREF
  DWORD pcchCombined; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v67; // [rsp+48h] [rbp-B8h]
  void *ppv; // [rsp+50h] [rbp-B0h] BYREF
  LPCITEMIDLIST ppidlLast; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v70; // [rsp+60h] [rbp-A0h]
  _QWORD v71[7]; // [rsp+68h] [rbp-98h] BYREF
  WCHAR pszRelative[2088]; // [rsp+A0h] [rbp-60h] BYREF
  STRRET pstr; // [rsp+10F0h] [rbp+FF0h] BYREF

  v6 = a6;
  v8 = 0;
  Uri = cb;
  v67 = a2;
  v9 = cb;
  v70 = (__int64)a6;
  v11 = 2;
  if ( a4 )
  {
    *a4 = 0;
    if ( a1 )
    {
      if ( *a1 == 20 && *((_BYTE *)a1 + 2) == 31 )
      {
        v12 = *(_QWORD *)(a1 + 2) - *(_QWORD *)&CLSID_Internet.Data1;
        if ( !v12 )
          v12 = *(_QWORD *)(a1 + 6) - *(_QWORD *)CLSID_Internet.Data4;
        if ( !v12 )
        {
          v13 = a1 + 10;
          if ( *v13 < 0xCu
            || *((_BYTE *)v13 + 2) != 97
            || (*((_BYTE *)v13 + 3) & 0x7F) != 0
            && (v61 = _IsValidDelegateID((const struct _ITEMIDLIST_RELATIVE *)v13), a2 = v67, !v61) )
          {
            v13 = v8;
          }
          if ( v13 )
          {
            if ( (a2 & 0x8000) != 0 && !a6 )
            {
              v14 = (char *)a1 + *a1;
              if ( *(_WORD *)v14 >= 0xCu && v14[2] == 97 && (v14[3] & 0x7F) == 0 )
              {
                v15 = v14[3];
                if ( v15 )
                {
                  v16 = cchBuf;
                  if ( v15 == (char)0x80 )
                  {
                    v17 = (unsigned __int16 *)(v14 + 8);
                    cb = cchBuf;
                    v18 = a4;
                    if ( cchBuf )
                    {
                      while ( 1 )
                      {
                        a2 = *v17;
                        if ( !(_WORD)a2 )
                          break;
                        *v18 = a2;
                        v17 = (unsigned __int16 *)((char *)v17 + v11);
                        v18 = (WCHAR *)((char *)v18 + v11);
                        cb = (unsigned int)(cb - 1);
                        if ( !(_DWORD)cb )
                          goto LABEL_22;
                      }
                      *v18 = (unsigned __int16)v8;
                    }
                    else
                    {
LABEL_22:
                      *(v18 - 1) = (unsigned __int16)v8;
                    }
                  }
                }
                else
                {
                  StringCbCopyA((char *)&pstr, 0x824u, v14 + 8);
                  v16 = cchBuf;
                  SHAnsiToUnicode((PCSTR)&pstr, a4, cchBuf);
                  LODWORD(v8) = 0;
                }
                v19 = (int)v8;
                pcchCombined = v16;
                v64 = v16;
                if ( *(_WORD *)v14 == (_WORD)v8 )
                  goto LABEL_175;
                ID_0 = ILFindLastID_0((LPCITEMIDLIST)v14);
                LODWORD(v8) = 0;
                cb = ID_0->mkid.cb;
                v11 = *(unsigned __int16 *)((char *)ID_0 + cb - 2);
                if ( (_WORD)v11
                  && v11 + 8 < cb
                  && (a2 = (unsigned __int64)ID_0 + v11,
                      HIWORD(*(_DWORD *)((char *)&ID_0[1].mkid.cb + v11 + 1)) == 0xBEEF)
                  && (unsigned int)v11 + *(unsigned __int16 *)a2 <= (unsigned int)cb )
                {
                  while ( *(_DWORD *)(a2 + 4) != -1091633150 )
                  {
                    a2 += *(unsigned __int16 *)a2;
                    if ( a2 >= (unsigned __int64)ID_0 + cb || HIWORD(*(_DWORD *)(a2 + 4)) != 0xBEEF )
                      goto LABEL_26;
                    if ( !a2 )
                      break;
                  }
                }
                else
                {
LABEL_26:
                  a2 = 0;
                }
                if ( !a2 )
                  goto LABEL_175;
                v11 = 2;
                v53 = (const CHAR *)(a2 + 10);
                cb = 2084;
                if ( *(_WORD *)(a2 + 8) == 2 )
                {
                  v54 = pszRelative;
                  while ( 1 )
                  {
                    a2 = *(unsigned __int16 *)v53;
                    if ( !(_WORD)a2 )
                      break;
                    *v54 = a2;
                    v53 += 2;
                    ++v54;
                    cb = (unsigned int)(cb - 1);
                    if ( !(_DWORD)cb )
                    {
                      *(v54 - 1) = 0;
                      goto LABEL_122;
                    }
                  }
                  *v54 = 0;
                }
                else
                {
                  SHAnsiToUnicode(v53, pszRelative, 2084);
                  LODWORD(v8) = 0;
                }
LABEL_122:
                if ( pszRelative[0] != 63
                  || (v55 = UrlCombineW(a4, pszRelative, a4, &v64, 0), LODWORD(v8) = 0, v19 = v55, v55 >= 0) )
                {
LABEL_175:
                  if ( (v9 & 1) == 0 && !(unsigned int)ILIsEmpty((const struct _ITEMIDLIST_RELATIVE *)v14) )
                  {
                    v50 = ILFindLastID_0(v49);
                    HiddenID = ILFindFirstHiddenID(v50);
                    v11 = 0;
                    v52 = (char *)v50 + v50->mkid.cb;
                    a2 = HiddenID;
                    if ( HiddenID )
                    {
                      while ( *(_DWORD *)(a2 + 4) != -1091633151 )
                      {
                        a2 += *(unsigned __int16 *)a2;
                        if ( a2 >= (unsigned __int64)v52 || HIWORD(*(_DWORD *)(a2 + 4)) != 0xBEEF )
                        {
                          a2 = 0;
                          break;
                        }
                        if ( !a2 )
                          break;
                      }
                    }
                    if ( a2 )
                    {
                      v59 = (const CHAR *)(a2 + 10);
                      cb = 2084;
                      if ( *(_WORD *)(a2 + 8) == 2 )
                      {
                        v60 = pszRelative;
                        while ( 1 )
                        {
                          a2 = *(unsigned __int16 *)v59;
                          if ( !(_WORD)a2 )
                            break;
                          *v60 = a2;
                          v59 += 2;
                          ++v60;
                          cb = (unsigned int)(cb - 1);
                          if ( !(_DWORD)cb )
                          {
                            *(v60 - 1) = 0;
                            goto LABEL_146;
                          }
                        }
                        *v60 = 0;
                      }
                      else
                      {
                        SHAnsiToUnicode(v59, pszRelative, 2084);
                        v11 = 0;
                      }
LABEL_146:
                      if ( pszRelative[0] == 35 )
                        v19 = UrlCombineW(a4, pszRelative, a4, &pcchCombined, 0);
                    }
                    LODWORD(v8) = 0;
                  }
                }
                v21 = (int)v8;
                if ( v19 != -2147467261 )
                  v21 = v19;
                if ( v21 >= 0 )
                {
LABEL_67:
                  v39 = Uri;
LABEL_68:
                  if ( (v39 & 0x20) != 0
                    && (*a4 == 92 || *a4 != (_WORD)v8 && a4[1] == 58 || (unsigned int)GetUrlSchemeW(a4) == 9) )
                  {
                    pcchCombined = 2084;
                    v21 = UrlCreateFromPathW(a4, pszRelative, &pcchCombined, 0);
                    if ( v21 >= 0 )
                      v21 = StringCchCopyW(a4, v16, pszRelative);
                  }
                  if ( v21 >= 0 && (v39 & 0x10) != 0 )
                  {
                    ppv = 0;
                    Uri = CreateUri(a4, 0x3002B84u, 0, (IUri **)&ppv);
                    v21 = Uri;
                    if ( Uri >= 0 )
                    {
                      v64 = 0;
                      if ( !(*(unsigned int (__fastcall **)(void *, DWORD *))(*(_QWORD *)ppv + 192LL))(ppv, &v64)
                        && (v64 - 1 <= 1 || v64 == 11) )
                      {
                        CUString::CUString((CUString *)v71, (struct IUri *)ppv, Uri_PROPERTY_DISPLAY_URI, &Uri);
                        v21 = Uri;
                        if ( Uri >= 0 )
                          v21 = StringCchCopyW(a4, v16, (const unsigned __int16 *)v71[4]);
                        v71[0] = &CUString::`vftable';
                        CUString::Set((CUString *)v71, 0, Uri_PROPERTY_RAW_URI);
                      }
                    }
                    ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(&ppv);
                  }
                  return (unsigned int)v21;
                }
              }
            }
          }
        }
      }
    }
  }
  if ( IEShimsDisableRedirection::SetEnabled )
  {
    v22 = IEShimsDisableRedirection::SetEnabled(0, a2, cb, v11);
    LOWORD(v8) = 0;
  }
  else
  {
    v22 = pcchCombined;
  }
  if ( a4 )
    *a4 = (unsigned __int16)v8;
  v23 = CoInitializeEx(0, 6u);
  if ( v23 < 0 )
    v23 = CoInitializeEx(0, 4u);
  ppv = 0;
  ppidlLast = 0;
  v24 = SHBindToParent_0((LPCITEMIDLIST)a1, &GUID_000214e6_0000_0000_c000_000000000046, &ppv, &ppidlLast);
  LOWORD(v8) = 0;
  v21 = v24;
  if ( v24 >= 0 )
  {
    if ( a4 )
    {
      v28 = ppidlLast;
      v29 = ppv;
      if ( IEShimsDisableRedirection::SetEnabled )
        v30 = IEShimsDisableRedirection::SetEnabled(0, v25, v26, v27);
      else
        v30 = pcchCombined;
      *a4 = 0;
      memset_0(&pstr, 0, sizeof(pstr));
      v21 = (*(__int64 (__fastcall **)(void *, const ITEMIDLIST *, _QWORD, STRRET *))(*(_QWORD *)v29 + 88LL))(
              v29,
              v28,
              v67,
              &pstr);
      if ( v21 >= 0 )
        v21 = StrRetToBufW(&pstr, v28, a4, cchBuf);
      if ( IEShimsDisableRedirection::SetEnabled )
        IEShimsDisableRedirection::SetEnabled(v30, v31, v32, v33);
      if ( v21 < 0 )
        goto LABEL_47;
      v6 = (unsigned int *)v70;
    }
    if ( v6 )
    {
      v62 = *v6;
      v64 = 0;
      _GetAttributesFromFolderAndIDList((struct IShellFolder *)ppv, ppidlLast, v62, &v64);
      *v6 = v64;
    }
LABEL_47:
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
    LOWORD(v8) = 0;
  }
  if ( v23 >= 0 )
  {
    CoUninitialize();
    LOWORD(v8) = 0;
  }
  if ( IEShimsDisableRedirection::SetEnabled )
  {
    IEShimsDisableRedirection::SetEnabled(v22, v25, v26, v27);
    LOWORD(v8) = 0;
  }
  if ( v21 < 0 )
    return (unsigned int)v21;
  if ( !a4 )
  {
    if ( (v67 & 0x8000) == 0 )
      return (unsigned int)v21;
    v16 = cchBuf;
    goto LABEL_67;
  }
  if ( (v67 & 0x8000) != 0 )
  {
    v16 = cchBuf;
    v34 = 0;
    v64 = cchBuf;
    pcchCombined = cchBuf;
    if ( !a1 || !*a1 )
      goto LABEL_60;
    v35 = ILFindLastID_0((LPCITEMIDLIST)a1);
    LOWORD(v8) = 0;
    v36 = v35->mkid.cb;
    v37 = *(unsigned __int16 *)((char *)v35 + v36 - 2);
    if ( (_WORD)v37
      && v37 + 8 < v36
      && (v38 = (USHORT *)((char *)&v35->mkid.cb + v37), HIWORD(*(_DWORD *)((char *)&v35[1].mkid.cb + v37 + 1)) == 0xBEEF)
      && (unsigned int)v37 + *v38 <= (unsigned int)v36 )
    {
      while ( *((_DWORD *)v38 + 1) != -1091633150 )
      {
        v38 = (unsigned __int16 *)((char *)v38 + *v38);
        if ( v38 >= (unsigned __int16 *)((char *)&v35->mkid.cb + v36) || HIWORD(*((_DWORD *)v38 + 1)) != 0xBEEF )
          goto LABEL_58;
        if ( !v38 )
          break;
      }
    }
    else
    {
LABEL_58:
      v38 = 0;
    }
    if ( !v38 )
      goto LABEL_60;
    v45 = (const CHAR *)(v38 + 5);
    v46 = 2084;
    if ( v38[4] == 2 )
    {
      v47 = pszRelative;
      while ( *(_WORD *)v45 )
      {
        *v47 = *(_WORD *)v45;
        v45 += 2;
        ++v47;
        if ( !--v46 )
        {
          *(v47 - 1) = 0;
          goto LABEL_105;
        }
      }
      *v47 = 0;
    }
    else
    {
      SHAnsiToUnicode(v45, pszRelative, 2084);
      LOWORD(v8) = 0;
    }
LABEL_105:
    if ( pszRelative[0] == 63
      && (v48 = UrlCombineW(a4, pszRelative, a4, &pcchCombined, 0), LOWORD(v8) = 0, v34 = v48, v48 < 0) )
    {
      v39 = Uri;
    }
    else
    {
LABEL_60:
      v39 = Uri;
      if ( (Uri & 1) == 0 && a1 && *a1 )
      {
        v41 = ILFindLastID_0((LPCITEMIDLIST)a1);
        v42 = ILFindFirstHiddenID(v41);
        v43 = (USHORT *)((char *)&v41->mkid.cb + v41->mkid.cb);
        v44 = (unsigned __int16 *)v42;
        if ( v42 )
        {
          while ( *((_DWORD *)v44 + 1) != -1091633151 )
          {
            v44 = (unsigned __int16 *)((char *)v44 + *v44);
            if ( v44 >= v43 || HIWORD(*((_DWORD *)v44 + 1)) != 0xBEEF )
            {
              v44 = 0;
              break;
            }
            if ( !v44 )
              break;
          }
        }
        if ( v44 )
        {
          v56 = (const CHAR *)(v44 + 5);
          v57 = 2084;
          if ( v44[4] == 2 )
          {
            v58 = pszRelative;
            while ( *(_WORD *)v56 )
            {
              *v58 = *(_WORD *)v56;
              v56 += 2;
              ++v58;
              if ( !--v57 )
              {
                *(v58 - 1) = 0;
                goto LABEL_137;
              }
            }
            *v58 = 0;
          }
          else
          {
            SHAnsiToUnicode(v56, pszRelative, 2084);
          }
LABEL_137:
          if ( pszRelative[0] == 35 )
            v34 = UrlCombineW(a4, pszRelative, a4, &v64, 0);
        }
        LOWORD(v8) = 0;
      }
    }
    v21 = 0;
    if ( v34 != -2147467261 )
      v21 = v34;
    if ( v21 >= 0 )
      goto LABEL_68;
  }
  return (unsigned int)v21;
}

```

## disassembly

```asm
0x180024bc4  mov     [rsp-8+arg_10], rbx
0x180024bc9  push    rbp
0x180024bca  push    rsi
0x180024bcb  push    rdi
0x180024bcc  push    r12
0x180024bce  push    r13
0x180024bd0  push    r14
0x180024bd2  push    r15
0x180024bd4  lea     rbp, [rsp-1830h]
0x180024bdc  mov     eax, 1930h
0x180024be1  call    _alloca_probe
0x180024be6  sub     rsp, rax
0x180024be9  mov     rax, cs:__security_cookie
0x180024bf0  xor     rax, rsp
0x180024bf3  mov     [rbp+1860h+var_40], rax
0x180024bfa  mov     r12, [rbp+1860h+arg_28]
0x180024c01  mov     r14, r9
0x180024c04  xor     r11d, r11d
0x180024c07  mov     [rsp+1960h+var_1928], r8d
0x180024c0c  mov     [rsp+1960h+var_1918], edx
0x180024c10  mov     esi, r8d
0x180024c13  mov     [rsp+1960h+var_1900], r12
0x180024c18  mov     r13, rcx
0x180024c1b  mov     r9d, 2
0x180024c21  test    r14, r14
0x180024c24  jz      loc_180024D76
0x180024c2a  mov     [r14], r11w
0x180024c2e  test    rcx, rcx
0x180024c31  jz      loc_180024D76
0x180024c37  cmp     word ptr [rcx], 14h
0x180024c3b  jnz     loc_180024D76
0x180024c41  cmp     byte ptr [rcx+2], 1Fh
0x180024c45  jnz     loc_180024D76
0x180024c4b  mov     rax, [rcx+4]
0x180024c4f  sub     rax, qword ptr cs:CLSID_Internet.Data1
0x180024c56  jnz     short loc_180024C63
0x180024c58  mov     rax, [rcx+0Ch]
0x180024c5c  sub     rax, qword ptr cs:CLSID_Internet.Data4
0x180024c63  test    rax, rax
0x180024c66  jnz     loc_180024D76
0x180024c6c  add     rcx, 14h; struct _ITEMIDLIST_RELATIVE *
0x180024c70  cmp     word ptr [rcx], 0Ch
0x180024c74  jb      loc_180025497
0x180024c7a  cmp     byte ptr [rcx+2], 61h ; 'a'
0x180024c7e  jnz     loc_180025497
0x180024c84  test    byte ptr [rcx+3], 7Fh
0x180024c88  jnz     loc_180025485
0x180024c8e  test    rcx, rcx
0x180024c91  jz      loc_180024D76
0x180024c97  bt      edx, 0Fh
0x180024c9b  jnb     loc_180024D76
0x180024ca1  test    r12, r12
0x180024ca4  jnz     loc_180024D76
0x180024caa  movzx   ebx, word ptr [r13+0]
0x180024caf  add     rbx, r13
0x180024cb2  cmp     word ptr [rbx], 0Ch
0x180024cb6  jb      loc_180024D76
0x180024cbc  cmp     byte ptr [rbx+2], 61h ; 'a'
0x180024cc0  jnz     loc_180024D76
0x180024cc6  test    byte ptr [rbx+3], 7Fh
0x180024cca  jnz     loc_180024D76
0x180024cd0  mov     al, [rbx+3]
0x180024cd3  test    al, al
0x180024cd5  jz      loc_18002549F
0x180024cdb  mov     r15d, [rbp+1860h+cchBuf]
0x180024ce2  cmp     al, 80h
0x180024ce4  jnz     short loc_180024D17
0x180024ce6  lea     rax, [rbx+8]
0x180024cea  mov     r8d, r15d
0x180024ced  mov     rcx, r14
0x180024cf0  test    r15d, r15d
0x180024cf3  jz      short loc_180024D0C
0x180024cf5  movzx   edx, word ptr [rax]
0x180024cf8  test    dx, dx
0x180024cfb  jz      short loc_180024D13
0x180024cfd  mov     [rcx], dx
0x180024d00  add     rax, r9
0x180024d03  add     rcx, r9
0x180024d06  sub     r8d, 1
0x180024d0a  jnz     short loc_180024CF5
0x180024d0c  mov     [rcx-2], r11w
0x180024d11  jmp     short loc_180024D17
0x180024d13  mov     [rcx], r11w
0x180024d17  mov     edi, r11d
0x180024d1a  mov     [rsp+1960h+pcchCombined], r15d
0x180024d1f  mov     [rsp+1960h+var_1930], r15d
0x180024d24  cmp     [rbx], r11w
0x180024d28  jz      short loc_180024D58
0x180024d2a  mov     rcx, rbx; pidl
0x180024d2d  call    ILFindLastID_0
0x180024d32  xor     r11d, r11d
0x180024d35  movzx   r8d, word ptr [rax]
0x180024d39  lea     r10, [rax+r8]
0x180024d3d  movzx   r9d, word ptr [r10-2]
0x180024d42  test    r9w, r9w
0x180024d46  jnz     loc_1800250D4
0x180024d4c  mov     rdx, r11
0x180024d4f  test    rdx, rdx
0x180024d52  jnz     loc_18002529B
0x180024d58  test    sil, 1
0x180024d5c  jz      loc_18002520D
0x180024d62  cmp     edi, 80004003h
0x180024d68  mov     esi, r11d
0x180024d6b  cmovnz  esi, edi
0x180024d6e  test    esi, esi
0x180024d70  jns     loc_180024F8D
0x180024d76  mov     rax, cs:?SetEnabled@IEShimsDisableRedirection@@2P6AHH@ZEA; int (*IEShimsDisableRedirection::SetEnabled)(int)
0x180024d7d  test    rax, rax
0x180024d80  jnz     loc_1800254F3
0x180024d86  mov     edi, [rsp+1960h+pcchCombined]
0x180024d8a  test    r14, r14
0x180024d8d  jz      short loc_180024D93
0x180024d8f  mov     [r14], r11w
0x180024d93  mov     edx, 6; dwCoInit
0x180024d98  xor     ecx, ecx; pvReserved
0x180024d9a  call    cs:__imp_CoInitializeEx
0x180024da1  nop     dword ptr [rax+rax+00h]
0x180024da6  xor     ebx, ebx
0x180024da8  mov     r15d, eax
0x180024dab  test    eax, eax
0x180024dad  js      loc_180025504
0x180024db3  lea     r9, [rsp+1960h+ppidlLast]; ppidlLast
0x180024db8  mov     [rsp+1960h+ppv], rbx
0x180024dbd  lea     r8, [rsp+1960h+ppv]; ppv
0x180024dc2  mov     [rsp+1960h+ppidlLast], rbx
0x180024dc7  lea     rdx, _GUID_000214e6_0000_0000_c000_000000000046; riid
0x180024dce  mov     rcx, r13; pidl
0x180024dd1  call    SHBindToParent_0
0x180024dd6  xor     r11d, r11d
0x180024dd9  mov     esi, eax
0x180024ddb  test    eax, eax
0x180024ddd  js      loc_180024E9A
0x180024de3  test    r14, r14
0x180024de6  jz      loc_180025544
0x180024dec  mov     rax, cs:?SetEnabled@IEShimsDisableRedirection@@2P6AHH@ZEA; int (*IEShimsDisableRedirection::SetEnabled)(int)
0x180024df3  mov     r12, [rsp+1960h+ppidlLast]
0x180024df8  mov     rsi, [rsp+1960h+ppv]
0x180024dfd  test    rax, rax
0x180024e00  jnz     loc_18002551F
0x180024e06  mov     ebx, [rsp+1960h+pcchCombined]
0x180024e0a  xor     edx, edx; Val
0x180024e0c  mov     [r14], r11w
0x180024e10  mov     r8d, 110h; Size
0x180024e16  lea     rcx, [rbp+1860h+pstr]; void *
0x180024e1d  call    memset_0
0x180024e22  mov     rax, [rsi]
0x180024e25  lea     r9, [rbp+1860h+pstr]
0x180024e2c  mov     r8d, [rsp+1960h+var_1918]
0x180024e31  mov     rdx, r12
0x180024e34  mov     rcx, rsi
0x180024e37  mov     rax, [rax+58h]
0x180024e3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024e40  xor     r11d, r11d
0x180024e43  mov     esi, eax
0x180024e45  test    eax, eax
0x180024e47  js      short loc_180024E6E
0x180024e49  mov     r9d, [rbp+1860h+cchBuf]; cchBuf
0x180024e50  lea     rcx, [rbp+1860h+pstr]; pstr
0x180024e57  mov     r8, r14; pszBuf
0x180024e5a  mov     rdx, r12; pidl
0x180024e5d  call    cs:__imp_StrRetToBufW
0x180024e64  nop     dword ptr [rax+rax+00h]
0x180024e69  mov     esi, eax
0x180024e6b  xor     r11d, r11d
0x180024e6e  mov     rax, cs:?SetEnabled@IEShimsDisableRedirection@@2P6AHH@ZEA; int (*IEShimsDisableRedirection::SetEnabled)(int)
0x180024e75  test    rax, rax
0x180024e78  jnz     loc_180025530
0x180024e7e  test    esi, esi
0x180024e80  jns     loc_18002553F
0x180024e86  mov     rcx, [rsp+1960h+ppv]
0x180024e8b  mov     rax, [rcx]
0x180024e8e  mov     rax, [rax+10h]
0x180024e92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024e97  xor     r11d, r11d
0x180024e9a  test    r15d, r15d
0x180024e9d  js      short loc_180024EAE
0x180024e9f  call    cs:__imp_CoUninitialize
0x180024ea6  nop     dword ptr [rax+rax+00h]
0x180024eab  xor     r11d, r11d
0x180024eae  mov     rax, cs:?SetEnabled@IEShimsDisableRedirection@@2P6AHH@ZEA; int (*IEShimsDisableRedirection::SetEnabled)(int)
0x180024eb5  test    rax, rax
0x180024eb8  jnz     loc_180025577
0x180024ebe  test    esi, esi
0x180024ec0  js      loc_180024F53
0x180024ec6  mov     eax, [rsp+1960h+var_1918]
0x180024eca  test    r14, r14
0x180024ecd  jz      loc_180024F80
0x180024ed3  bt      eax, 0Fh
0x180024ed7  jnb     short loc_180024F53
0x180024ed9  mov     r15d, [rbp+1860h+cchBuf]
0x180024ee0  mov     edi, r11d
0x180024ee3  mov     [rsp+1960h+var_1930], r15d
0x180024ee8  mov     [rsp+1960h+pcchCombined], r15d
0x180024eed  test    r13, r13
0x180024ef0  jz      loc_180025337
0x180024ef6  cmp     [r13+0], r11w
0x180024efb  jz      loc_180025337
0x180024f01  mov     rcx, r13; pidl
0x180024f04  call    ILFindLastID_0
0x180024f09  xor     r11d, r11d
0x180024f0c  movzx   r8d, word ptr [rax]
0x180024f10  lea     r10, [rax+r8]
0x180024f14  movzx   r9d, word ptr [r10-2]
0x180024f19  test    r9w, r9w
0x180024f1d  jnz     loc_180025067
0x180024f23  mov     rdx, r11
0x180024f26  mov     esi, 2
0x180024f2b  test    rdx, rdx
0x180024f2e  jnz     loc_180025193
0x180024f34  mov     r12d, [rsp+1960h+var_1928]
0x180024f39  test    r12b, 1
0x180024f3d  jz      loc_180025146
0x180024f43  cmp     edi, 80004003h
0x180024f49  mov     esi, r11d
0x180024f4c  cmovnz  esi, edi
0x180024f4f  test    esi, esi
0x180024f51  jns     short loc_180024F92
0x180024f53  mov     eax, esi
0x180024f55  mov     rcx, [rbp+1860h+var_40]
0x180024f5c  xor     rcx, rsp; StackCookie
0x180024f5f  call    __security_check_cookie
0x180024f64  mov     rbx, [rsp+1960h+arg_10]
0x180024f6c  add     rsp, 1930h
0x180024f73  pop     r15
0x180024f75  pop     r14
0x180024f77  pop     r13
0x180024f79  pop     r12
0x180024f7b  pop     rdi
0x180024f7c  pop     rsi
0x180024f7d  pop     rbp
0x180024f7e  retn
0x180024f80  bt      eax, 0Fh
0x180024f84  jnb     short loc_180024F53
0x180024f86  mov     r15d, [rbp+1860h+cchBuf]
0x180024f8d  mov     r12d, [rsp+1960h+var_1928]
0x180024f92  test    r12b, 20h
0x180024f96  jnz     loc_1800255A0
0x180024f9c  xor     ebx, ebx
0x180024f9e  test    esi, esi
0x180024fa0  js      short loc_180024F53
0x180024fa2  test    r12b, 10h
0x180024fa6  jz      short loc_180024F53
0x180024fa8  lea     r9, [rsp+1960h+ppv]; ppURI
0x180024fad  mov     [rsp+1960h+ppv], rbx
0x180024fb2  xor     r8d, r8d; dwReserved
0x180024fb5  mov     edx, 3002B84h; dwFlags
0x180024fba  mov     rcx, r14; pwzURI
0x180024fbd  call    cs:__imp_CreateUri
0x180024fc4  nop     dword ptr [rax+rax+00h]
0x180024fc9  mov     [rsp+1960h+var_1928], eax
0x180024fcd  mov     esi, eax
0x180024fcf  test    eax, eax
0x180024fd1  js      loc_180025058
0x180024fd7  mov     rcx, [rsp+1960h+ppv]
0x180024fdc  lea     rdx, [rsp+1960h+var_1930]
0x180024fe1  mov     [rsp+1960h+var_1930], ebx
0x180024fe5  mov     rax, [rcx]
0x180024fe8  mov     rax, [rax+0C0h]
0x180024fef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024ff4  test    eax, eax
0x180024ff6  jnz     short loc_180025058
0x180024ff8  mov     ecx, [rsp+1960h+var_1930]
0x180024ffc  lea     eax, [rcx-1]
0x180024fff  cmp     eax, 1
0x180025002  jbe     short loc_180025009
0x180025004  cmp     ecx, 0Bh
0x180025007  jnz     short loc_180025058
0x180025009  mov     rdx, [rsp+1960h+ppv]; struct IUri *
0x18002500e  lea     r9, [rsp+1960h+var_1928]; int *
0x180025013  mov     r8d, 2; enum __MIDL_IUri_0001
0x180025019  lea     rcx, [rsp+1960h+var_18F8]; this
0x18002501e  call    ??0CUString@@QEAA@PEAUIUri@@W4__MIDL_IUri_0001@@PEAJ@Z; CUString::CUString(IUri *,__MIDL_IUri_0001,long *)
0x180025023  mov     esi, [rsp+1960h+var_1928]
0x180025027  test    esi, esi
0x180025029  js      short loc_18002503C
0x18002502b  mov     r8, [rbp+1860h+var_18D8]; unsigned __int16 *
0x18002502f  mov     rcx, r14; unsigned __int16 *
0x180025032  mov     edx, r15d; unsigned __int64
0x180025035  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002503a  mov     esi, eax
0x18002503c  xor     edx, edx; struct IUri *
0x18002503e  lea     rax, ??_7CUString@@6B@; const CUString::`vftable'
0x180025045  lea     rcx, [rsp+1960h+var_18F8]; this
0x18002504a  mov     [rsp+1960h+var_18F8], rax
0x18002504f  lea     r8d, [rdx+0Bh]; enum __MIDL_IUri_0001
0x180025053  call    ?Set@CUString@@QEAAJPEAUIUri@@W4__MIDL_IUri_0001@@@Z; CUString::Set(IUri *,__MIDL_IUri_0001)
0x180025058  lea     rcx, [rsp+1960h+ppv]; void *
0x18002505d  call    ??1?$CComPtr@UIBrowserThreadState@@@ATL@@QEAA@XZ; ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(void)
0x180025062  jmp     loc_180024F53
0x180025067  lea     rcx, [r9+8]
0x18002506b  mov     rdx, r9
0x18002506e  cmp     rcx, r8
0x180025071  jnb     loc_180024F23
0x180025077  add     rdx, rax
0x18002507a  mov     ebx, 0BEEFh
0x18002507f  mov     eax, [rdx+4]
0x180025082  shr     rax, 10h
0x180025086  cmp     ax, bx
0x180025089  jnz     loc_180024F23
0x18002508f  movzx   ecx, word ptr [rdx]
  ... truncated ...
```
