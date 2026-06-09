# IEGetNameAndFlagsEx

- ea: `0x18002320c`
- end: `0x180023c04`
- name: `IEGetNameAndFlagsEx`
- size: `2552`
- prototype: `__int64 __fastcall(int, int, int, int, UINT cchBuf, __int64)`
- caller_count: `101`
- callee_count: `16`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800118d4`
- `0x18002237c`
- `0x180022648`
- `0x1800247e0`
- `0x180037f6c`
- `0x18005aef4`
- `0x18006d850`
- `0x18007da30`
- `0x1800896e0`
- `0x180091768`
- `0x1800927d8`
- `0x1800a14b0`
- `0x1800ae940`
- `0x1800c808c`
- `0x1800c8354`
- `0x1800c9bec`
- `0x1800d15f0`
- `0x1800d55f8`
- `0x1800d65a4`
- `0x1800d7274`
- `0x1800d78f8`
- `0x1800d815c`
- `0x1800d862c`
- `0x1800eded0`
- `0x1800f54cc`
- `0x1800f6730`
- `0x1800f8c34`
- `0x1801310e0`
- `0x1801354c0`
- `0x18013a590`
- `0x18013a764`
- `0x180184270`
- `0x18019c060`
- `0x1801a1590`
- `0x1801a1af0`
- `0x1801a1e18`
- `0x1801a3430`
- `0x1801a369c`
- `0x1801a3aec`
- `0x1801a40dc`
- `0x1801a4b9c`
- `0x1801a6214`
- `0x1801a7528`
- `0x1801a7a98`
- `0x1801a8040`
- `0x1801a90f0`
- `0x1801bcff8`
- `0x1801cace4`
- `0x1801cadfc`
- `0x1801cd258`

## callees

- `0x18000b9e0`
- `0x180011230`
- `0x1800231c4`
- `0x18002320c`
- `0x180024180`
- `0x180053590`
- `0x1800712c4`
- `0x1800bab8c`
- `0x1800babd4`
- `0x1800bf808`
- `0x1804e6f3c`
- `0x180538a98`
- `0x18054e286`
- `0x18054e310`
- `0x18054e3d0`
- `0x180550010`

## import_xrefs

- `SHLWAPI!StrRetToBufW` at `0x18002349f`
- `SHLWAPI!StrRetToBufW` at `0x18002349f`
- `api-ms-win-downlevel-shlwapi-l1-1-0!UrlCreateFromPathW` at `0x180023bdc`
- `api-ms-win-downlevel-shlwapi-l1-1-0!UrlCreateFromPathW` at `0x180023bdc`
- `api-ms-win-downlevel-shlwapi-l1-1-0!UrlCombineW` at `0x180023819`
- `api-ms-win-downlevel-shlwapi-l1-1-0!UrlCombineW` at `0x180023915`
- `api-ms-win-downlevel-shlwapi-l1-1-0!UrlCombineW` at `0x1800239c8`
- `api-ms-win-downlevel-shlwapi-l1-1-0!UrlCombineW` at `0x180023a43`
- `api-ms-win-downlevel-shlwapi-l1-1-0!UrlCombineW` at `0x180023819`
- `api-ms-win-downlevel-shlwapi-l1-1-0!UrlCombineW` at `0x180023915`
- `api-ms-win-downlevel-shlwapi-l1-1-0!UrlCombineW` at `0x1800239c8`
- `api-ms-win-downlevel-shlwapi-l1-1-0!UrlCombineW` at `0x180023a43`
- `iertutil!CreateUri` at `0x1800235f2`
- `iertutil!CreateUri` at `0x1800235f2`
- `api-ms-win-downlevel-ole32-l1-1-0!CoInitializeEx` at `0x1800233e2`
- `api-ms-win-downlevel-ole32-l1-1-0!CoInitializeEx` at `0x180023afe`
- `api-ms-win-downlevel-ole32-l1-1-0!CoInitializeEx` at `0x1800233e2`
- `api-ms-win-downlevel-ole32-l1-1-0!CoInitializeEx` at `0x180023afe`
- `api-ms-win-downlevel-ole32-l1-1-0!CoUninitialize` at `0x1800234db`
- `api-ms-win-downlevel-ole32-l1-1-0!CoUninitialize` at `0x1800234db`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHAnsiToUnicode` at `0x1800238ad`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHAnsiToUnicode` at `0x180023968`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHAnsiToUnicode` at `0x1800239dc`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHAnsiToUnicode` at `0x180023a57`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHAnsiToUnicode` at `0x180023ac1`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHAnsiToUnicode` at `0x1800238ad`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHAnsiToUnicode` at `0x180023968`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHAnsiToUnicode` at `0x1800239dc`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHAnsiToUnicode` at `0x180023a57`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHAnsiToUnicode` at `0x180023ac1`

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
  LPITEMIDLIST v49; // rbx
  __int64 HiddenID; // rax
  char *v51; // rbx
  const CHAR *v52; // rax
  WCHAR *v53; // rcx
  HRESULT v54; // eax
  const CHAR *v55; // rax
  int v56; // r8d
  WCHAR *v57; // rcx
  const CHAR *v58; // rax
  WCHAR *v59; // rcx
  const struct DELEGATEITEMID *v60; // rax
  unsigned int v61; // r8d
  DWORD v63; // [rsp+30h] [rbp-D0h] BYREF
  int Uri; // [rsp+38h] [rbp-C8h] BYREF
  DWORD pcchCombined; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v66; // [rsp+48h] [rbp-B8h]
  void *ppv; // [rsp+50h] [rbp-B0h] BYREF
  LPCITEMIDLIST ppidlLast; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v69; // [rsp+60h] [rbp-A0h]
  _QWORD v70[7]; // [rsp+68h] [rbp-98h] BYREF
  WCHAR pszRelative[2088]; // [rsp+A0h] [rbp-60h] BYREF
  STRRET pstr; // [rsp+10F0h] [rbp+FF0h] BYREF

  v6 = a6;
  v8 = 0;
  Uri = cb;
  v66 = a2;
  v9 = cb;
  v69 = (__int64)a6;
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
            && (v60 = _IsValidDelegateID((const struct _ITEMIDLIST_RELATIVE *)v13), a2 = v66, !v60) )
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
                v63 = v16;
                if ( *(_WORD *)v14 == (_WORD)v8 )
                  goto LABEL_108;
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
                  goto LABEL_108;
                v11 = 2;
                v52 = (const CHAR *)(a2 + 10);
                cb = 2084;
                if ( *(_WORD *)(a2 + 8) == 2 )
                {
                  v53 = pszRelative;
                  while ( 1 )
                  {
                    a2 = *(unsigned __int16 *)v52;
                    if ( !(_WORD)a2 )
                      break;
                    *v53 = a2;
                    v52 += 2;
                    ++v53;
                    cb = (unsigned int)(cb - 1);
                    if ( !(_DWORD)cb )
                    {
                      *(v53 - 1) = 0;
                      goto LABEL_122;
                    }
                  }
                  *v53 = 0;
                }
                else
                {
                  SHAnsiToUnicode(v52, pszRelative, 2084);
                  LODWORD(v8) = 0;
                }
LABEL_122:
                if ( pszRelative[0] != 63
                  || (v54 = UrlCombineW(a4, pszRelative, a4, &v63, 0), LODWORD(v8) = 0, v19 = v54, v54 >= 0) )
                {
LABEL_108:
                  if ( (v9 & 1) == 0 && *(_WORD *)v14 != (_WORD)v8 )
                  {
                    v49 = ILFindLastID_0((LPCITEMIDLIST)v14);
                    HiddenID = ILFindFirstHiddenID(v49);
                    v11 = 0;
                    v51 = (char *)v49 + v49->mkid.cb;
                    a2 = HiddenID;
                    if ( HiddenID )
                    {
                      while ( *(_DWORD *)(a2 + 4) != -1091633151 )
                      {
                        a2 += *(unsigned __int16 *)a2;
                        if ( a2 >= (unsigned __int64)v51 || HIWORD(*(_DWORD *)(a2 + 4)) != 0xBEEF )
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
                      v58 = (const CHAR *)(a2 + 10);
                      cb = 2084;
                      if ( *(_WORD *)(a2 + 8) == 2 )
                      {
                        v59 = pszRelative;
                        while ( 1 )
                        {
                          a2 = *(unsigned __int16 *)v58;
                          if ( !(_WORD)a2 )
                            break;
                          *v59 = a2;
                          v58 += 2;
                          ++v59;
                          cb = (unsigned int)(cb - 1);
                          if ( !(_DWORD)cb )
                          {
                            *(v59 - 1) = 0;
                            goto LABEL_146;
                          }
                        }
                        *v59 = 0;
                      }
                      else
                      {
                        SHAnsiToUnicode(v58, pszRelative, 2084);
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
                      v63 = 0;
                      if ( !(*(unsigned int (__fastcall **)(void *, DWORD *))(*(_QWORD *)ppv + 192LL))(ppv, &v63)
                        && (v63 - 1 <= 1 || v63 == 11) )
                      {
                        CUString::CUString((CUString *)v70, (struct IUri *)ppv, Uri_PROPERTY_DISPLAY_URI, &Uri);
                        v21 = Uri;
                        if ( Uri >= 0 )
                          v21 = StringCchCopyW(a4, v16, (const unsigned __int16 *)v70[4]);
                        v70[0] = &CUString::`vftable';
                        CUString::Set((CUString *)v70, 0, Uri_PROPERTY_RAW_URI);
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
              v66,
              &pstr);
      if ( v21 >= 0 )
        v21 = StrRetToBufW(&pstr, v28, a4, cchBuf);
      if ( IEShimsDisableRedirection::SetEnabled )
        IEShimsDisableRedirection::SetEnabled(v30, v31, v32, v33);
      if ( v21 < 0 )
        goto LABEL_47;
      v6 = (unsigned int *)v69;
    }
    if ( v6 )
    {
      v61 = *v6;
      v63 = 0;
      _GetAttributesFromFolderAndIDList((struct IShellFolder *)ppv, ppidlLast, v61, &v63);
      *v6 = v63;
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
    if ( (v66 & 0x8000) == 0 )
      return (unsigned int)v21;
    v16 = cchBuf;
    goto LABEL_67;
  }
  if ( (v66 & 0x8000) != 0 )
  {
    v16 = cchBuf;
    v34 = 0;
    v63 = cchBuf;
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
          v55 = (const CHAR *)(v44 + 5);
          v56 = 2084;
          if ( v44[4] == 2 )
          {
            v57 = pszRelative;
            while ( *(_WORD *)v55 )
            {
              *v57 = *(_WORD *)v55;
              v55 += 2;
              ++v57;
              if ( !--v56 )
              {
                *(v57 - 1) = 0;
                goto LABEL_137;
              }
            }
            *v57 = 0;
          }
          else
          {
            SHAnsiToUnicode(v55, pszRelative, 2084);
          }
LABEL_137:
          if ( pszRelative[0] == 35 )
            v34 = UrlCombineW(a4, pszRelative, a4, &v63, 0);
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
0x18002320c  mov     [rsp-8+arg_10], rbx
0x180023211  push    rbp
0x180023212  push    rsi
0x180023213  push    rdi
0x180023214  push    r12
0x180023216  push    r13
0x180023218  push    r14
0x18002321a  push    r15
0x18002321c  lea     rbp, [rsp-1830h]
0x180023224  mov     eax, 1930h
0x180023229  call    _alloca_probe
0x18002322e  sub     rsp, rax
0x180023231  mov     rax, cs:__security_cookie
0x180023238  xor     rax, rsp
0x18002323b  mov     [rbp+1860h+var_40], rax
0x180023242  mov     r12, [rbp+1860h+arg_28]
0x180023249  mov     r14, r9
0x18002324c  xor     r11d, r11d
0x18002324f  mov     [rsp+1960h+var_1928], r8d
0x180023254  mov     [rsp+1960h+var_1918], edx
0x180023258  mov     esi, r8d
0x18002325b  mov     [rsp+1960h+var_1900], r12
0x180023260  mov     r13, rcx
0x180023263  mov     r9d, 2
0x180023269  test    r14, r14
0x18002326c  jz      loc_1800233BE
0x180023272  mov     [r14], r11w
0x180023276  test    rcx, rcx
0x180023279  jz      loc_1800233BE
0x18002327f  cmp     word ptr [rcx], 14h
0x180023283  jnz     loc_1800233BE
0x180023289  cmp     byte ptr [rcx+2], 1Fh
0x18002328d  jnz     loc_1800233BE
0x180023293  mov     rax, [rcx+4]
0x180023297  sub     rax, qword ptr cs:CLSID_Internet.Data1
0x18002329e  jnz     short loc_1800232AB
0x1800232a0  mov     rax, [rcx+0Ch]
0x1800232a4  sub     rax, qword ptr cs:CLSID_Internet.Data4
0x1800232ab  test    rax, rax
0x1800232ae  jnz     loc_1800233BE
0x1800232b4  add     rcx, 14h; struct _ITEMIDLIST_RELATIVE *
0x1800232b8  cmp     word ptr [rcx], 0Ch
0x1800232bc  jb      loc_180023A90
0x1800232c2  cmp     byte ptr [rcx+2], 61h ; 'a'
0x1800232c6  jnz     loc_180023A90
0x1800232cc  test    byte ptr [rcx+3], 7Fh
0x1800232d0  jnz     loc_180023A7E
0x1800232d6  test    rcx, rcx
0x1800232d9  jz      loc_1800233BE
0x1800232df  bt      edx, 0Fh
0x1800232e3  jnb     loc_1800233BE
0x1800232e9  test    r12, r12
0x1800232ec  jnz     loc_1800233BE
0x1800232f2  movzx   ebx, word ptr [r13+0]
0x1800232f7  add     rbx, r13
0x1800232fa  cmp     word ptr [rbx], 0Ch
0x1800232fe  jb      loc_1800233BE
0x180023304  cmp     byte ptr [rbx+2], 61h ; 'a'
0x180023308  jnz     loc_1800233BE
0x18002330e  test    byte ptr [rbx+3], 7Fh
0x180023312  jnz     loc_1800233BE
0x180023318  mov     al, [rbx+3]
0x18002331b  test    al, al
0x18002331d  jz      loc_180023A98
0x180023323  mov     r15d, [rbp+1860h+cchBuf]
0x18002332a  cmp     al, 80h
0x18002332c  jnz     short loc_18002335F
0x18002332e  lea     rax, [rbx+8]
0x180023332  mov     r8d, r15d
0x180023335  mov     rcx, r14
0x180023338  test    r15d, r15d
0x18002333b  jz      short loc_180023354
0x18002333d  movzx   edx, word ptr [rax]
0x180023340  test    dx, dx
0x180023343  jz      short loc_18002335B
0x180023345  mov     [rcx], dx
0x180023348  add     rax, r9
0x18002334b  add     rcx, r9
0x18002334e  sub     r8d, 1
0x180023352  jnz     short loc_18002333D
0x180023354  mov     [rcx-2], r11w
0x180023359  jmp     short loc_18002335F
0x18002335b  mov     [rcx], r11w
0x18002335f  mov     edi, r11d
0x180023362  mov     [rsp+1960h+pcchCombined], r15d
0x180023367  mov     [rsp+1960h+var_1930], r15d
0x18002336c  cmp     [rbx], r11w
0x180023370  jz      short loc_1800233A0
0x180023372  mov     rcx, rbx; pidl
0x180023375  call    ILFindLastID_0
0x18002337a  xor     r11d, r11d
0x18002337d  movzx   r8d, word ptr [rax]
0x180023381  lea     r10, [r8+rax]
0x180023385  movzx   r9d, word ptr [r10-2]
0x18002338a  test    r9w, r9w
0x18002338e  jnz     loc_180023703
0x180023394  mov     rdx, r11
0x180023397  test    rdx, rdx
0x18002339a  jnz     loc_1800238BB
0x1800233a0  test    sil, 1
0x1800233a4  jz      loc_180023836
0x1800233aa  cmp     edi, 80004003h
0x1800233b0  mov     esi, r11d
0x1800233b3  cmovnz  esi, edi
0x1800233b6  test    esi, esi
0x1800233b8  jns     loc_1800235C2
0x1800233be  mov     rax, cs:?SetEnabled@IEShimsDisableRedirection@@2P6AHH@ZEA; int (*IEShimsDisableRedirection::SetEnabled)(int)
0x1800233c5  test    rax, rax
0x1800233c8  jnz     loc_180023AE6
0x1800233ce  mov     edi, [rsp+1960h+pcchCombined]
0x1800233d2  test    r14, r14
0x1800233d5  jz      short loc_1800233DB
0x1800233d7  mov     [r14], r11w
0x1800233db  mov     edx, 6; dwCoInit
0x1800233e0  xor     ecx, ecx; pvReserved
0x1800233e2  call    cs:__imp_CoInitializeEx
0x1800233e8  xor     ebx, ebx
0x1800233ea  mov     r15d, eax
0x1800233ed  test    eax, eax
0x1800233ef  js      loc_180023AF7
0x1800233f5  lea     r9, [rsp+1960h+ppidlLast]; ppidlLast
0x1800233fa  mov     [rsp+1960h+ppv], rbx
0x1800233ff  lea     r8, [rsp+1960h+ppv]; ppv
0x180023404  mov     [rsp+1960h+ppidlLast], rbx
0x180023409  lea     rdx, _GUID_000214e6_0000_0000_c000_000000000046; riid
0x180023410  mov     rcx, r13; pidl
0x180023413  call    SHBindToParent_0
0x180023418  xor     r11d, r11d
0x18002341b  mov     esi, eax
0x18002341d  test    eax, eax
0x18002341f  js      loc_1800234D6
0x180023425  test    r14, r14
0x180023428  jz      loc_180023B31
0x18002342e  mov     rax, cs:?SetEnabled@IEShimsDisableRedirection@@2P6AHH@ZEA; int (*IEShimsDisableRedirection::SetEnabled)(int)
0x180023435  mov     r12, [rsp+1960h+ppidlLast]
0x18002343a  mov     rsi, [rsp+1960h+ppv]
0x18002343f  test    rax, rax
0x180023442  jnz     loc_180023B0C
0x180023448  mov     ebx, [rsp+1960h+pcchCombined]
0x18002344c  xor     edx, edx; Val
0x18002344e  mov     [r14], r11w
0x180023452  mov     r8d, 110h; Size
0x180023458  lea     rcx, [rbp+1860h+pstr]; void *
0x18002345f  call    memset_0
0x180023464  mov     rax, [rsi]
0x180023467  lea     r9, [rbp+1860h+pstr]
0x18002346e  mov     r8d, [rsp+1960h+var_1918]
0x180023473  mov     rdx, r12
0x180023476  mov     rcx, rsi
0x180023479  mov     rax, [rax+58h]
0x18002347d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023482  xor     r11d, r11d
0x180023485  mov     esi, eax
0x180023487  test    eax, eax
0x180023489  js      short loc_1800234AA
0x18002348b  mov     r9d, [rbp+1860h+cchBuf]; cchBuf
0x180023492  lea     rcx, [rbp+1860h+pstr]; pstr
0x180023499  mov     r8, r14; pszBuf
0x18002349c  mov     rdx, r12; pidl
0x18002349f  call    cs:__imp_StrRetToBufW
0x1800234a5  mov     esi, eax
0x1800234a7  xor     r11d, r11d
0x1800234aa  mov     rax, cs:?SetEnabled@IEShimsDisableRedirection@@2P6AHH@ZEA; int (*IEShimsDisableRedirection::SetEnabled)(int)
0x1800234b1  test    rax, rax
0x1800234b4  jnz     loc_180023B1D
0x1800234ba  test    esi, esi
0x1800234bc  jns     loc_180023B2C
0x1800234c2  mov     rcx, [rsp+1960h+ppv]
0x1800234c7  mov     rax, [rcx]
0x1800234ca  mov     rax, [rax+10h]
0x1800234ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800234d3  xor     r11d, r11d
0x1800234d6  test    r15d, r15d
0x1800234d9  js      short loc_1800234E4
0x1800234db  call    cs:__imp_CoUninitialize
0x1800234e1  xor     r11d, r11d
0x1800234e4  mov     rax, cs:?SetEnabled@IEShimsDisableRedirection@@2P6AHH@ZEA; int (*IEShimsDisableRedirection::SetEnabled)(int)
0x1800234eb  test    rax, rax
0x1800234ee  jnz     loc_180023B64
0x1800234f4  test    esi, esi
0x1800234f6  js      loc_180023589
0x1800234fc  mov     eax, [rsp+1960h+var_1918]
0x180023500  test    r14, r14
0x180023503  jz      loc_1800235B5
0x180023509  bt      eax, 0Fh
0x18002350d  jnb     short loc_180023589
0x18002350f  mov     r15d, [rbp+1860h+cchBuf]
0x180023516  mov     edi, r11d
0x180023519  mov     [rsp+1960h+var_1930], r15d
0x18002351e  mov     [rsp+1960h+pcchCombined], r15d
0x180023523  test    r13, r13
0x180023526  jz      loc_180023951
0x18002352c  cmp     [r13+0], r11w
0x180023531  jz      loc_180023951
0x180023537  mov     rcx, r13; pidl
0x18002353a  call    ILFindLastID_0
0x18002353f  xor     r11d, r11d
0x180023542  movzx   r8d, word ptr [rax]
0x180023546  lea     r10, [rax+r8]
0x18002354a  movzx   r9d, word ptr [r10-2]
0x18002354f  test    r9w, r9w
0x180023553  jnz     loc_180023696
0x180023559  mov     rdx, r11
0x18002355c  mov     esi, 2
0x180023561  test    rdx, rdx
0x180023564  jnz     loc_1800237C2
0x18002356a  mov     r12d, [rsp+1960h+var_1928]
0x18002356f  test    r12b, 1
0x180023573  jz      loc_180023775
0x180023579  cmp     edi, 80004003h
0x18002357f  mov     esi, r11d
0x180023582  cmovnz  esi, edi
0x180023585  test    esi, esi
0x180023587  jns     short loc_1800235C7
0x180023589  mov     eax, esi
0x18002358b  mov     rcx, [rbp+1860h+var_40]
0x180023592  xor     rcx, rsp; StackCookie
0x180023595  call    __security_check_cookie
0x18002359a  mov     rbx, [rsp+1960h+arg_10]
0x1800235a2  add     rsp, 1930h
0x1800235a9  pop     r15
0x1800235ab  pop     r14
0x1800235ad  pop     r13
0x1800235af  pop     r12
0x1800235b1  pop     rdi
0x1800235b2  pop     rsi
0x1800235b3  pop     rbp
0x1800235b4  retn
0x1800235b5  bt      eax, 0Fh
0x1800235b9  jnb     short loc_180023589
0x1800235bb  mov     r15d, [rbp+1860h+cchBuf]
0x1800235c2  mov     r12d, [rsp+1960h+var_1928]
0x1800235c7  test    r12b, 20h
0x1800235cb  jnz     loc_180023B8D
0x1800235d1  xor     ebx, ebx
0x1800235d3  test    esi, esi
0x1800235d5  js      short loc_180023589
0x1800235d7  test    r12b, 10h
0x1800235db  jz      short loc_180023589
0x1800235dd  lea     r9, [rsp+1960h+ppv]; ppURI
0x1800235e2  mov     [rsp+1960h+ppv], rbx
0x1800235e7  xor     r8d, r8d; dwReserved
0x1800235ea  mov     edx, 3002B84h; dwFlags
0x1800235ef  mov     rcx, r14; pwzURI
0x1800235f2  call    cs:__imp_CreateUri
0x1800235f8  mov     [rsp+1960h+var_1928], eax
0x1800235fc  mov     esi, eax
0x1800235fe  test    eax, eax
0x180023600  js      loc_180023687
0x180023606  mov     rcx, [rsp+1960h+ppv]
0x18002360b  lea     rdx, [rsp+1960h+var_1930]
0x180023610  mov     [rsp+1960h+var_1930], ebx
0x180023614  mov     rax, [rcx]
0x180023617  mov     rax, [rax+0C0h]
0x18002361e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023623  test    eax, eax
0x180023625  jnz     short loc_180023687
0x180023627  mov     ecx, [rsp+1960h+var_1930]
0x18002362b  lea     eax, [rcx-1]
0x18002362e  cmp     eax, 1
0x180023631  jbe     short loc_180023638
0x180023633  cmp     ecx, 0Bh
0x180023636  jnz     short loc_180023687
0x180023638  mov     rdx, [rsp+1960h+ppv]; struct IUri *
0x18002363d  lea     r9, [rsp+1960h+var_1928]; int *
0x180023642  mov     r8d, 2; enum __MIDL_IUri_0001
0x180023648  lea     rcx, [rsp+1960h+var_18F8]; this
0x18002364d  call    ??0CUString@@QEAA@PEAUIUri@@W4__MIDL_IUri_0001@@PEAJ@Z; CUString::CUString(IUri *,__MIDL_IUri_0001,long *)
0x180023652  mov     esi, [rsp+1960h+var_1928]
0x180023656  test    esi, esi
0x180023658  js      short loc_18002366B
0x18002365a  mov     r8, [rbp+1860h+var_18D8]; unsigned __int16 *
0x18002365e  mov     rcx, r14; unsigned __int16 *
0x180023661  mov     edx, r15d; unsigned __int64
0x180023664  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180023669  mov     esi, eax
0x18002366b  xor     edx, edx; struct IUri *
0x18002366d  lea     rax, ??_7CUString@@6B@; const CUString::`vftable'
0x180023674  lea     rcx, [rsp+1960h+var_18F8]; this
0x180023679  mov     [rsp+1960h+var_18F8], rax
0x18002367e  lea     r8d, [rdx+0Bh]; enum __MIDL_IUri_0001
0x180023682  call    ?Set@CUString@@QEAAJPEAUIUri@@W4__MIDL_IUri_0001@@@Z; CUString::Set(IUri *,__MIDL_IUri_0001)
0x180023687  lea     rcx, [rsp+1960h+ppv]; void *
0x18002368c  call    ??1?$CComPtr@UIBrowserThreadState@@@ATL@@QEAA@XZ; ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(void)
0x180023691  jmp     loc_180023589
0x180023696  lea     rcx, [r9+8]
0x18002369a  mov     rdx, r9
0x18002369d  cmp     rcx, r8
0x1800236a0  jnb     loc_180023559
0x1800236a6  add     rdx, rax
0x1800236a9  mov     ebx, 0BEEFh
0x1800236ae  mov     eax, [rdx+4]
0x1800236b1  shr     rax, 10h
0x1800236b5  cmp     ax, bx
0x1800236b8  jnz     loc_180023559
0x1800236be  movzx   ecx, word ptr [rdx]
0x1800236c1  add     ecx, r9d
0x1800236c4  cmp     ecx, r8d
0x1800236c7  ja      loc_180023559
0x1800236cd  cmp     dword ptr [rdx+4], 0BEEF0002h
  ... truncated ...
```
