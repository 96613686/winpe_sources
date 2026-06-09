# CHistoryDataFactory::LoadHistoryDataEntryFromUrl(ushort const *,ushort * *,IHistoryData * *)

- ea: `0x18000a400`
- end: `0x18000b2f0`
- name: `?LoadHistoryDataEntryFromUrl@CHistoryDataFactory@@UEAAJPEBGPEAPEAGPEAPEAUIHistoryData@@@Z`
- size: `3824`
- prototype: `int(CHistoryDataFactory *__hidden this, const unsigned __int16 *, unsigned __int16 **, struct IHistoryData **)`
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180009cc0`
- `0x180009e74`
- `0x18000a0f8`
- `0x18000a130`
- `0x18000a400`
- `0x18000b9e0`
- `0x18000c530`
- `0x18000c5c0`
- `0x18002acc0`
- `0x18004ab60`
- `0x1800b83c8`
- `0x1800c322c`
- `0x18054e310`
- `0x180550010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x18000aa75`
- `msvcrt!memcpy_s` at `0x18000aa75`
- `KERNEL32!InitOnceExecuteOnce` at `0x18000ac7d`
- `KERNEL32!InitOnceExecuteOnce` at `0x18000ac7d`
- `KERNEL32!GetProcessHeap` at `0x18000a44a`
- `KERNEL32!GetProcessHeap` at `0x18000a77d`
- `KERNEL32!GetProcessHeap` at `0x18000aa9b`
- `KERNEL32!GetProcessHeap` at `0x18000ae31`
- `KERNEL32!GetProcessHeap` at `0x18000ae5a`
- `KERNEL32!GetProcessHeap` at `0x18000aee2`
- `KERNEL32!GetProcessHeap` at `0x18000afa1`
- `KERNEL32!GetProcessHeap` at `0x18000a44a`
- `KERNEL32!GetProcessHeap` at `0x18000a77d`
- `KERNEL32!GetProcessHeap` at `0x18000aa9b`
- `KERNEL32!GetProcessHeap` at `0x18000ae31`
- `KERNEL32!GetProcessHeap` at `0x18000ae5a`
- `KERNEL32!GetProcessHeap` at `0x18000aee2`
- `KERNEL32!GetProcessHeap` at `0x18000afa1`
- `KERNEL32!HeapAlloc` at `0x18000a45e`
- `KERNEL32!HeapAlloc` at `0x18000a791`
- `KERNEL32!HeapAlloc` at `0x18000afb2`
- `KERNEL32!HeapAlloc` at `0x18000a45e`
- `KERNEL32!HeapAlloc` at `0x18000a791`
- `KERNEL32!HeapAlloc` at `0x18000afb2`
- `KERNEL32!LeaveCriticalSection` at `0x18000a506`
- `KERNEL32!LeaveCriticalSection` at `0x18000b16e`
- `KERNEL32!LeaveCriticalSection` at `0x18000a506`
- `KERNEL32!LeaveCriticalSection` at `0x18000b16e`
- `KERNEL32!EnterCriticalSection` at `0x18000a4e0`
- `KERNEL32!EnterCriticalSection` at `0x18000a4e0`
- `KERNEL32!HeapFree` at `0x18000aaa9`
- `KERNEL32!HeapFree` at `0x18000ae3f`
- `KERNEL32!HeapFree` at `0x18000ae68`
- `KERNEL32!HeapFree` at `0x18000aef0`
- `KERNEL32!HeapFree` at `0x18000aaa9`
- `KERNEL32!HeapFree` at `0x18000ae3f`
- `KERNEL32!HeapFree` at `0x18000ae68`
- `KERNEL32!HeapFree` at `0x18000aef0`
- `api-ms-win-downlevel-shlwapi-l1-1-0!QISearch` at `0x18000ad94`
- `api-ms-win-downlevel-shlwapi-l1-1-0!QISearch` at `0x18000ad94`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a68a`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a734`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ae18`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ae22`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b286`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b293`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a68a`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a734`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ae18`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ae22`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b286`
- `OLEAUT32!__imp_SysFreeString` at `0x18000b293`
- `iertutil!CreateIUriBuilder` at `0x18000b1d8`
- `iertutil!CreateIUriBuilder` at `0x18000b1d8`
- `iertutil!CreateUri` at `0x18000a4b4`
- `iertutil!CreateUri` at `0x18000a4b4`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x18000ac48`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x18000ac48`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x18000a9eb`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x18000a9eb`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18000aa82`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18000ad5e`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18000aed2`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18000aedc`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18000aa82`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18000ad5e`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18000aed2`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18000aedc`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x18000a817`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x18000a82d`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x18000adea`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x18000a817`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x18000a82d`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x18000adea`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHCreateMemStream` at `0x18000ab16`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHCreateMemStream` at `0x18000ab16`
- `Secur32!GetUserNameExW` at `0x18000b131`
- `Secur32!GetUserNameExW` at `0x18000b131`
- `WININET!GetUrlCacheEntryBinaryBlob` at `0x18000a9d0`
- `WININET!GetUrlCacheEntryBinaryBlob` at `0x18000a9d0`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18000a801`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18000ab56`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18000a801`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18000ab56`

## pseudocode

```c
__int64 __fastcall CHistoryDataFactory::LoadHistoryDataEntryFromUrl(
        CHistoryDataFactory *this,
        const unsigned __int16 *a2,
        unsigned __int16 **a3,
        struct IHistoryData **a4)
{
  char v4; // r13
  struct IHistoryData **v5; // r15
  LPWSTR *v6; // rsi
  HANDLE ProcessHeap; // rax
  const WCHAR **v9; // rax
  char *v10; // r14
  const WCHAR **v11; // rax
  int Error; // edi
  IUri *v13; // r12
  WCHAR *v14; // rbx
  __int64 v15; // rsi
  __int64 v16; // r15
  size_t *v17; // rdx
  __int64 v18; // rcx
  struct IUriVtbl *lpVtbl; // rax
  struct IUriVtbl *v20; // rax
  unsigned int v21; // ebx
  int v22; // eax
  __int64 v23; // rax
  OLECHAR *v24; // rbx
  _WORD *v25; // r14
  _WORD *i; // rcx
  wchar_t *v27; // rax
  size_t *v28; // r8
  unsigned __int16 *v29; // rsi
  const WCHAR *v30; // rsi
  const WCHAR *v31; // rbx
  HANDLE v32; // rax
  char *v33; // rax
  char *v34; // r12
  _QWORD *v35; // r15
  LPVOID *v36; // r14
  LPVOID *v37; // r13
  unsigned __int64 v38; // rax
  __int64 (__fastcall ***v39)(_QWORD, GUID *, __int64 *); // rcx
  int v40; // eax
  __int16 v41; // r8
  unsigned __int64 j; // rax
  int v43; // ecx
  unsigned __int64 k; // rax
  int v45; // ecx
  char *v46; // rbx
  signed int UrlCacheEntryBinaryBlob; // eax
  SIZE_T v48; // rsi
  char *v49; // rax
  char *v50; // rdi
  BYTE *v51; // rsi
  HANDLE v52; // rax
  ULONG v53; // esi
  __int64 (__fastcall ***v54)(_QWORD, GUID *, __int64 *); // rcx
  IStream *v55; // rax
  IStream *v56; // r13
  __int64 *v57; // r14
  __int64 (__fastcall ***v58)(_QWORD, GUID *, __int64 *); // r15
  __int64 v59; // rax
  __int64 v60; // rax
  int (__fastcall ***v61)(_QWORD, GUID *, ULONG *); // rcx
  const WCHAR *v62; // rcx
  BSTR *v63; // rsi
  BSTR v64; // rbx
  HANDLE v65; // rax
  BSTR v66; // rcx
  HANDLE v67; // rax
  __int64 (__fastcall ***v69)(_QWORD, GUID *, __int64 *); // rcx
  HANDLE v70; // rax
  __int64 (__fastcall ***v71)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v72; // rcx
  __int64 v74; // rax
  unsigned __int64 v75; // rsi
  SIZE_T v76; // rdi
  HANDLE v77; // rax
  _WORD *v78; // rax
  _WORD *v79; // rcx
  _QWORD *v80; // r10
  __int64 v81; // rdx
  unsigned __int16 *v82; // r8
  unsigned __int64 v83; // r9
  unsigned __int64 v84; // rcx
  _WORD *v85; // rax
  unsigned __int64 v86; // rax
  _WORD *v87; // rcx
  unsigned __int64 v88; // rsi
  int v89; // eax
  __int64 (__fastcall ***v90)(_QWORD, GUID *, __int64 *); // rcx
  int v91; // eax
  size_t cchToCopy; // [rsp+20h] [rbp-E0h]
  DWORD pcbBlob; // [rsp+40h] [rbp-C0h] BYREF
  ULONG nSize[2]; // [rsp+48h] [rbp-B8h] BYREF
  DWORD dwType; // [rsp+50h] [rbp-B0h] BYREF
  BYTE *ppbBlob; // [rsp+58h] [rbp-A8h] BYREF
  struct IHistoryData **v97; // [rsp+60h] [rbp-A0h]
  IUri *ppURI; // [rsp+68h] [rbp-98h] BYREF
  void *ppv; // [rsp+70h] [rbp-90h] BYREF
  LPVOID lpMem; // [rsp+78h] [rbp-88h]
  PROPVARIANT pvar[2]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v102; // [rsp+90h] [rbp-70h]
  FILETIME pftModifiedTime; // [rsp+98h] [rbp-68h] BYREF
  __int64 *v104; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v105; // [rsp+A8h] [rbp-58h] BYREF
  LPWSTR *ppwsz; // [rsp+B0h] [rbp-50h]
  FILETIME pftExpireTime; // [rsp+B8h] [rbp-48h] BYREF
  FILETIME pftAccessTime; // [rsp+C0h] [rbp-40h] BYREF
  const WCHAR **v109; // [rsp+C8h] [rbp-38h]
  GUID v110; // [rsp+D0h] [rbp-30h] BYREF
  int v111; // [rsp+E0h] [rbp-20h]
  unsigned __int16 v112[272]; // [rsp+F0h] [rbp-10h] BYREF
  _WORD v113[264]; // [rsp+310h] [rbp+210h] BYREF

  v4 = 0;
  v97 = a4;
  ppwsz = a3;
  v5 = a4;
  v6 = a3;
  if ( a3 )
    *a3 = 0;
  *a4 = 0;
  ProcessHeap = GetProcessHeap();
  v9 = (const WCHAR **)HeapAlloc(ProcessHeap, 8u, 0x28u);
  lpMem = v9;
  v10 = (char *)v9;
  if ( !v9 )
    std::_Xbad_alloc();
  *v9 = 0;
  v11 = v9 + 1;
  *((_QWORD *)v10 + 2) = 0;
  v10[24] = 0;
  *v11 = 0;
  *((_QWORD *)v10 + 4) = 0;
  v109 = v11;
  ppURI = 0;
  Error = CreateUri(a2, 0x3002B84u, 0, &ppURI);
  if ( Error >= 0 )
  {
    v13 = ppURI;
    v112[0] = 0;
    Error = 0;
    v113[0] = 0;
    EnterCriticalSection(&g_userNameInfo);
    v14 = &NameBuffer;
    v15 = 257;
    if ( !NameBuffer )
    {
      nSize[0] = 257;
      if ( GetUserNameExW((EXTENDED_NAME_FORMAT)65538, &NameBuffer, nSize) )
      {
        ConvertToUtf8Escaped(&NameBuffer, 257);
        LeaveCriticalSection(&g_userNameInfo);
        goto LABEL_7;
      }
      Error = ResultFromKnownLastError();
    }
    LeaveCriticalSection(&g_userNameInfo);
    if ( Error < 0 )
    {
LABEL_39:
      v6 = ppwsz;
      goto LABEL_40;
    }
LABEL_7:
    v16 = 2147483646;
    v17 = (size_t *)v113;
    v18 = 2147483646;
    while ( v18 && *v14 )
    {
      *(_WORD *)v17 = *v14++;
      v17 = (size_t *)((char *)v17 + 2);
      --v18;
      if ( !--v15 )
      {
        *((_WORD *)v17 - 1) = 0;
        Error = -2147024774;
        goto LABEL_38;
      }
    }
    *(_WORD *)v17 = 0;
    Error = StringCchPrintfW(v112, 0x10Du, L"%s%s@", L"Visited: ", v113);
    if ( Error < 0 )
      goto LABEL_38;
    lpVtbl = v13->lpVtbl;
    dwType = 0;
    Error = ((__int64 (__fastcall *)(IUri *, DWORD *))lpVtbl->GetScheme)(v13, &dwType);
    if ( Error < 0 )
      goto LABEL_38;
    if ( dwType - 15 > 1 )
      v4 = 1;
    v20 = v13->lpVtbl;
    pcbBlob = 0;
    v21 = 0;
    if ( ((int (__fastcall *)(IUri *, __int64, DWORD *))v20->HasProperty)(v13, 14, &pcbBlob) >= 0 && pcbBlob )
      v21 = 0x4000;
    if ( ((int (__fastcall *)(IUri *, __int64, DWORD *))v13->lpVtbl->HasProperty)(v13, 7, &pcbBlob) >= 0 && pcbBlob )
      v21 |= 0x80u;
    if ( v4
      && ((int (__fastcall *)(IUri *, __int64, DWORD *))v13->lpVtbl->HasProperty)(v13, 5, &pcbBlob) >= 0
      && pcbBlob )
    {
      v21 |= 0x20u;
    }
    *(_QWORD *)nSize = 0;
    if ( v21 )
    {
      Error = CreateIUriBuilder(v13, 0, 0, (IUriBuilder **)nSize);
      if ( Error >= 0 )
      {
        Error = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)nSize + 192LL))(*(_QWORD *)nSize, v21);
        if ( Error >= 0 )
        {
          ppbBlob = 0;
          Error = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, BYTE **))(**(_QWORD **)nSize + 24LL))(
                    *(_QWORD *)nSize,
                    0,
                    0,
                    &ppbBlob);
          if ( Error >= 0 )
          {
            Error = CWinINetPrefixInfo::s_GetAbsoluteUriAndFailIfNotPresent(
                      (struct IUri *)ppbBlob,
                      (unsigned __int16 **)v10);
            if ( Error >= 0 )
              ATL::CComPtrBase<IHistoryData>::CopyTo(&ppbBlob, v10 + 32);
          }
          ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(&ppbBlob);
        }
      }
      ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(nSize);
      if ( Error >= 0 )
        goto LABEL_29;
    }
    else
    {
      *(_QWORD *)v10 = 0;
      v22 = ((__int64 (__fastcall *)(IUri *, ULONG *))v13->lpVtbl->GetAbsoluteUri)(v13, nSize);
      Error = v22;
      if ( !v22 )
      {
        v23 = *(_QWORD *)nSize;
        *(_QWORD *)nSize = 0;
        *(_QWORD *)v10 = v23;
        SysFreeString(0);
        ((void (__fastcall *)(IUri *))v13->lpVtbl->AddRef)(v13);
        *((_QWORD *)v10 + 4) = v13;
LABEL_29:
        v24 = 0;
        v25 = *(_WORD **)v10;
        ppv = 0;
        if ( dwType != 9 )
        {
          for ( i = v25; *i; ++i )
          {
            if ( *i > 0x7Fu )
            {
              v27 = (wchar_t *)operator new(0x1048u);
              v29 = v27;
              if ( !v27 )
              {
                Error = -2147024882;
                goto LABEL_37;
              }
              Error = StringCopyWorkerW(v27, 0x824u, v28, *(STRSAFE_PCNZWCH *)lpMem, cchToCopy);
              if ( Error >= 0 )
              {
                ConvertToUtf8Escaped(v29, 2084);
                *((_BYTE *)lpMem + 24) = 1;
                v89 = CWinINetPrefixInfo::s_CanonicalizeUrl(v29, (unsigned __int16 **)&ppv);
                v24 = (OLECHAR *)ppv;
                Error = v89;
                if ( v89 >= 0 )
                  v25 = ppv;
              }
              operator delete(v29);
              if ( Error >= 0 )
                break;
              goto LABEL_37;
            }
          }
        }
        v72 = -1;
        while ( v112[++v72] != 0 )
          ;
        v74 = -1;
        do
          ++v74;
        while ( v25[v74] );
        v75 = v74 + v72 + 2;
        v76 = 2 * v75;
        if ( !is_mul_ok(v75, 2u) )
          v76 = -1;
        v77 = GetProcessHeap();
        v78 = HeapAlloc(v77, 8u, v76);
        v79 = v78;
        if ( !v78 )
          std::_Xbad_alloc();
        v80 = lpMem;
        *((_QWORD *)lpMem + 2) = v78;
        if ( v75 )
        {
          if ( v75 > 0x7FFFFFFF )
          {
            Error = -2147024809;
            *v78 = 0;
          }
          else
          {
            v81 = 2147483646;
            v82 = v112;
            v83 = v75;
            Error = 0;
            while ( v81 && *v82 )
            {
              *v79++ = *v82++;
              --v81;
              if ( !--v83 )
              {
                --v79;
                Error = -2147024774;
                break;
              }
            }
            *v79 = 0;
            if ( Error >= 0 )
            {
              v84 = v75;
              v85 = (_WORD *)v80[2];
              do
              {
                if ( !*v85 )
                  break;
                ++v85;
                --v84;
              }
              while ( v84 );
              Error = -2147024809;
              if ( v84 )
              {
                v86 = v75 - v84;
                v87 = (_WORD *)(v80[2] + 2 * (v75 - v84));
                Error = 0;
                v88 = v75 - v86;
                if ( v88 )
                {
                  while ( v16 && *v25 )
                  {
                    *v87++ = *v25++;
                    --v16;
                    if ( !--v88 )
                      goto LABEL_168;
                  }
                }
                else
                {
LABEL_168:
                  --v87;
                  Error = -2147024774;
                }
                *v87 = 0;
                if ( Error >= 0 )
                {
                  if ( ppwsz )
                  {
                    if ( v4 )
                    {
                      Error = ((__int64 (__fastcall *)(IUri *, _QWORD *, unsigned __int16 *, unsigned __int64))v13->lpVtbl->GetFragment)(
                                v13,
                                v80 + 1,
                                v82,
                                v83);
                      if ( Error == 1 )
                        Error = 0;
                    }
                  }
                }
              }
            }
          }
        }
        else
        {
          Error = -2147024809;
        }
LABEL_37:
        SysFreeString(v24);
        v10 = (char *)lpMem;
        goto LABEL_38;
      }
      if ( v22 < 0 )
      {
        SysFreeString(*(BSTR *)nSize);
      }
      else
      {
        SysFreeString(*(BSTR *)nSize);
        Error = -2147467259;
      }
    }
LABEL_38:
    v5 = v97;
    goto LABEL_39;
  }
LABEL_40:
  if ( ppURI )
    ((void (__fastcall *)(IUri *))ppURI->lpVtbl->Release)(ppURI);
  if ( Error >= 0 )
  {
    if ( v6 )
      *v6 = 0;
    *v5 = 0;
    v30 = (const WCHAR *)*((_QWORD *)v10 + 2);
    v31 = *(const WCHAR **)v10;
    ppv = 0;
    v32 = GetProcessHeap();
    v33 = (char *)HeapAlloc(v32, 8u, 0x50u);
    v34 = v33;
    if ( !v33 )
      std::_Xbad_alloc();
    *((_QWORD *)v33 + 6) = 0;
    v35 = v33 + 48;
    *(_QWORD *)v33 = &CHistoryData::`vftable';
    v36 = (LPVOID *)(v33 + 56);
    *((_QWORD *)v33 + 7) = 0;
    v37 = (LPVOID *)(v33 + 64);
    *(_QWORD *)(v33 + 12) = c_li0;
    *(_QWORD *)(v33 + 20) = c_li0;
    *(_QWORD *)(v33 + 28) = c_li0;
    *(_QWORD *)(v33 + 36) = c_li0;
    *((_QWORD *)v33 + 8) = 0;
    *((_DWORD *)v33 + 2) = 1;
    v33[72] = 1;
    Error = PSCreateMemoryPropertyStore(&GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, (void **)v33 + 6);
    if ( Error >= 0 )
    {
      Error = SHStrDupW(v31, (LPWSTR *)v34 + 8);
      if ( Error >= 0 )
      {
        Error = SHStrDupW(v30, (LPWSTR *)v34 + 7);
        if ( Error >= 0 )
        {
          v38 = 0;
          v102 = 0;
          *(_OWORD *)pvar = 0;
          LODWORD(pvar[1]) = 0;
          LOWORD(pvar[0]) = 19;
          while ( v38 < 0x24 )
          {
            if ( dword_1805C31B0[2 * v38] == 13 )
            {
              if ( LOWORD(dword_1805C31B0[2 * v38 + 1]) != 19 )
              {
                Error = -2147023267;
                v34[72] = 1;
                goto LABEL_119;
              }
              break;
            }
            ++v38;
          }
          v39 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*v35;
          v111 = 13;
          v110 = FMTID_InternetSite;
          v40 = (*v39)[6](v39, &v110, (__int64 *)pvar);
          v34[72] = 1;
          Error = v40;
          if ( v40 < 0 )
            goto LABEL_119;
          v41 = (__int16)pvar[0];
          if ( !LOWORD(pvar[0]) )
            goto LABEL_199;
          for ( j = 0; ; ++j )
          {
            v43 = 0;
            if ( j >= 0x24 )
              break;
            if ( dword_1805C31B0[2 * j] == 6 )
            {
              LOBYTE(v43) = LOWORD(pvar[0]) != LOWORD(dword_1805C31B0[2 * j + 1]);
              ++v43;
              break;
            }
          }
          if ( v43 == 2 )
          {
            Error = -2147023267;
          }
          else
          {
LABEL_199:
            v90 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*v35;
            v111 = 6;
            v110 = FMTID_InternetSite;
            v91 = (*v90)[6](v90, &v110, (__int64 *)pvar);
            v41 = (__int16)pvar[0];
            Error = v91;
          }
          v34[72] = 1;
          if ( Error < 0 )
            goto LABEL_121;
          if ( !v41 )
            goto LABEL_144;
          for ( k = 0; ; ++k )
          {
            v45 = 0;
            if ( k >= 0x24 )
              break;
            if ( dword_1805C31B0[2 * k] == 9 )
            {
              LOBYTE(v45) = v41 != LOWORD(dword_1805C31B0[2 * k + 1]);
              ++v45;
              break;
            }
          }
          if ( v45 == 2 )
          {
            Error = -2147023267;
          }
          else
          {
LABEL_144:
            v71 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*v35;
            v111 = 9;
            v110 = FMTID_InternetSite;
            Error = (*v71)[6](v71, &v110, (__int64 *)pvar);
          }
          v34[72] = 1;
          if ( Error < 0 )
          {
LABEL_121:
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)v34 + 2, 0xFFFFFFFF) == 1 )
            {
              v69 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*v35;
              *(_QWORD *)v34 = &CHistoryData::`vftable';
              if ( v69 )
                ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v69)[2])(v69);
              CoTaskMemFree(*v36);
              CoTaskMemFree(*v37);
              v70 = GetProcessHeap();
              HeapFree(v70, 0, v34);
            }
            if ( Error < 0 )
              goto LABEL_128;
            v62 = *v109;
            if ( *v109 )
            {
              if ( *v62 == 35 )
              {
                if ( !++v62 )
                  goto LABEL_141;
              }
              else if ( !*v62 )
              {
                goto LABEL_141;
              }
              if ( ppwsz )
              {
                Error = SHStrDupW(v62, ppwsz);
                if ( Error < 0 )
                {
LABEL_128:
                  if ( ppv )
                    (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
                  goto LABEL_130;
                }
              }
            }
LABEL_141:
            *v97 = (struct IHistoryData *)ppv;
            goto LABEL_130;
          }
          ppbBlob = 0;
          pcbBlob = 0;
          dwType = 0;
          pftExpireTime = 0;
          pftAccessTime = 0;
          v46 = 0;
          pftModifiedTime = 0;
          UrlCacheEntryBinaryBlob = GetUrlCacheEntryBinaryBlob(
                                      v30,
                                      &dwType,
                                      &pftExpireTime,
                                      &pftAccessTime,
                                      &pftModifiedTime,
                                      &ppbBlob,
                                      &pcbBlob);
          Error = UrlCacheEntryBinaryBlob;
          if ( UrlCacheEntryBinaryBlob )
          {
            if ( UrlCacheEntryBinaryBlob > 0 )
              Error = (unsigned __int16)UrlCacheEntryBinaryBlob | 0x80070000;
          }
          else
          {
            v48 = pcbBlob + 112;
            v49 = (char *)CoTaskMemAlloc(v48);
            v50 = v49;
            if ( v49 )
            {
              *(_OWORD *)(v49 + 4) = 0;
              *(_OWORD *)(v49 + 20) = 0;
              *(_OWORD *)(v49 + 36) = 0;
              *(_OWORD *)(v49 + 52) = 0;
              *(_OWORD *)(v49 + 68) = 0;
              *(_OWORD *)(v49 + 84) = 0;
              *((_OWORD *)v49 + 6) = 0;
              *(_DWORD *)v49 = 112;
              *((_DWORD *)v49 + 6) = dwType;
              *(FILETIME *)(v49 + 44) = pftModifiedTime;
              *(FILETIME *)(v49 + 52) = pftExpireTime;
              *(FILETIME *)(v49 + 60) = pftAccessTime;
              *(FILETIME *)(v49 + 68) = pftModifiedTime;
              if ( ppbBlob && pcbBlob )
              {
                *((_QWORD *)v49 + 10) = v49 + 112;
                *((_DWORD *)v49 + 22) = pcbBlob;
                memcpy_s(v49 + 112, v48 - 112, ppbBlob, pcbBlob);
              }
              v46 = v50;
              Error = 0;
            }
            else
            {
              Error = -2147024882;
            }
            CoTaskMemFree(0);
          }
          v51 = ppbBlob;
          ppbBlob = 0;
          if ( v51 )
          {
            v52 = GetProcessHeap();
            HeapFree(v52, 0, v51);
          }
          if ( Error >= 0 )
          {
            v53 = 0;
            *(_QWORD *)(v34 + 12) = *(_QWORD *)(v46 + 60);
            Error = 0;
            *(_QWORD *)(v34 + 20) = *(_QWORD *)(v46 + 44);
            *(_QWORD *)(v34 + 28) = *(_QWORD *)(v46 + 52);
            *(_QWORD *)(v34 + 36) = *(_QWORD *)(v46 + 68);
            if ( *((_DWORD *)v46 + 22) )
            {
              v54 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*v35;
              v105 = 0;
              Error = (**v54)(v54, &GUID_00000109_0000_0000_c000_000000000046, &v105);
              if ( Error >= 0 )
              {
                v55 = SHCreateMemStream(*((const BYTE **)v46 + 10), *((_DWORD *)v46 + 22));
                v56 = v55;
                if ( v55 )
                {
                  Error = (*(__int64 (__fastcall **)(__int64, IStream *))(*(_QWORD *)v105 + 40LL))(v105, v55);
                  if ( Error < 0 )
                  {
                    if ( Error == -2147024883 )
                      Error = 0;
                  }
                  else
                  {
                    ppURI = 0;
                    Error = PSCreateMemoryPropertyStore(&GUID_00000109_0000_0000_c000_000000000046, (void **)&ppURI);
                    if ( Error >= 0
                      && ((int (__fastcall *)(IUri *, IStream *))ppURI->lpVtbl->GetPropertyDWORD)(ppURI, v56) >= 0 )
                    {
                      v104 = 0;
                      Error = ((__int64 (__fastcall *)(IUri *, GUID *, __int64 **))ppURI->lpVtbl->QueryInterface)(
                                ppURI,
                                &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99,
                                &v104);
                      if ( Error >= 0 )
                      {
                        v57 = v104;
                        v58 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*v35;
                        nSize[0] = 0;
                        for ( Error = (*(__int64 (__fastcall **)(__int64 *, ULONG *))(*v104 + 24))(v104, nSize);
                              Error >= 0;
                              ++v53 )
                        {
                          if ( v53 >= nSize[0] )
                            break;
                          v111 = 0;
                          v59 = *v57;
                          v110 = 0;
                          Error = (*(__int64 (__fastcall **)(__int64 *, _QWORD, GUID *))(v59 + 32))(v57, v53, &v110);
                          if ( Error >= 0 )
                          {
                            v102 = 0;
                            v60 = *v57;
                            *(_OWORD *)pvar = 0;
                            Error = (*(__int64 (__fastcall **)(__int64 *, GUID *, PROPVARIANT *))(v60 + 40))(
                                      v57,
                                      &v110,
                                      pvar);
                            if ( Error >= 0 )
                            {
                              Error = (*v58)[6](v58, &v110, (__int64 *)pvar);
                              PropVariantClear(pvar);
                            }
                          }
                        }
                        if ( Error >= 0
                          && *((_DWORD *)v46 + 6) == 2097153
                          && (InitOnceExecuteOnce(&InitOnce, InitOnceVersionInfo, 0, 0),
                              VersionInformation.dwPlatformId == 2)
                          && (VersionInformation.dwMajorVersion > 6
                           || VersionInformation.dwMajorVersion == 6 && VersionInformation.dwMinorVersion > 1) )
                        {
                          v61 = (int (__fastcall ***)(_QWORD, GUID *, ULONG *))*((_QWORD *)v34 + 6);
                          v35 = v34 + 48;
                          *(_QWORD *)nSize = 0;
                          if ( (**v61)(v61, &GUID_e318ad57_0aa0_450f_aca5_6fab7103d917, nSize) >= 0
                            && (*(int (__fastcall **)(_QWORD, __int64))(**(_QWORD **)nSize + 24LL))(*(_QWORD *)nSize, 2) >= 0 )
                          {
                            v34[72] = 0;
                          }
                          if ( *(_QWORD *)nSize )
                            (*(void (__fastcall **)(_QWORD))(**(_QWORD **)nSize + 16LL))(*(_QWORD *)nSize);
                        }
                        else
                        {
                          v35 = v34 + 48;
                        }
                        v36 = (LPVOID *)(v34 + 56);
                      }
                      if ( v104 )
                        (*(void (__fastcall **)(__int64 *))(*v104 + 16))(v104);
                    }
                    if ( ppURI )
                      ((void (__fastcall *)(IUri *))ppURI->lpVtbl->Release)(ppURI);
                  }
                  (*(void (__fastcall **)(IStream *))(*(_QWORD *)v56 + 16LL))(v56);
                }
                else
                {
                  Error = -2147024882;
                }
                v37 = (LPVOID *)(v34 + 64);
              }
              if ( v105 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v105 + 16LL))(v105);
            }
          }
          CoTaskMemFree(v46);
        }
      }
    }
LABEL_119:
    if ( Error >= 0 )
    {
      ppv = 0;
      Error = QISearch(v34, &`CHistoryData::QueryInterface'::`2'::qit, &GUID_94aeefba_1ea6_41d9_b4c7_a37a98d3da6f, &ppv);
    }
    goto LABEL_121;
  }
LABEL_130:
  v63 = (BSTR *)lpMem;
  SysFreeString(*(BSTR *)lpMem);
  SysFreeString(v63[1]);
  v64 = v63[2];
  if ( v64 )
  {
    v65 = GetProcessHeap();
    HeapFree(v65, 0, v64);
  }
  v66 = v63[4];
  if ( v66 )
    (*(void (__fastcall **)(BSTR))(*(_QWORD *)v66 + 16LL))(v66);
  v67 = GetProcessHeap();
  HeapFree(v67, 0, v63);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18000a400  push    rbp
0x18000a402  push    rbx
0x18000a403  push    rsi
0x18000a404  push    r13
0x18000a406  push    r14
0x18000a408  push    r15
0x18000a40a  lea     rbp, [rsp-438h]
0x18000a412  sub     rsp, 538h
0x18000a419  mov     rax, cs:__security_cookie
0x18000a420  xor     rax, rsp
0x18000a423  mov     [rbp+460h+var_40], rax
0x18000a42a  xor     r13d, r13d
0x18000a42d  mov     [rsp+560h+var_500], r9
0x18000a432  mov     [rbp+460h+ppwsz], r8
0x18000a436  mov     r15, r9
0x18000a439  mov     rsi, r8
0x18000a43c  mov     rbx, rdx
0x18000a43f  test    r8, r8
0x18000a442  jz      short loc_18000A447
0x18000a444  mov     [r8], r13
0x18000a447  mov     [r9], r13
0x18000a44a  call    cs:__imp_GetProcessHeap
0x18000a450  mov     edx, 8; dwFlags
0x18000a455  mov     r8d, 28h ; '('; dwBytes
0x18000a45b  mov     rcx, rax; hHeap
0x18000a45e  call    cs:__imp_HeapAlloc
0x18000a464  mov     [rsp+560h+lpMem], rax
0x18000a469  mov     r14, rax
0x18000a46c  test    rax, rax
0x18000a46f  jz      loc_18000A554
0x18000a475  mov     [rax], r13
0x18000a478  lea     r9, [rsp+560h+ppURI]; ppURI
0x18000a47d  add     rax, 8
0x18000a481  mov     [r14+10h], r13
0x18000a485  mov     [r14+18h], r13b
0x18000a489  xor     r8d, r8d; dwReserved
0x18000a48c  mov     [rsp+560h+arg_0], rdi
0x18000a494  mov     edx, 3002B84h; dwFlags
0x18000a499  mov     rcx, rbx; pwzURI
0x18000a49c  mov     [rsp+560h+var_30], r12
0x18000a4a4  mov     [rax], r13
0x18000a4a7  mov     [r14+20h], r13
0x18000a4ab  mov     [rbp+460h+var_498], rax
0x18000a4af  mov     [rsp+560h+ppURI], r13
0x18000a4b4  call    cs:__imp_CreateUri
0x18000a4ba  mov     edi, eax
0x18000a4bc  test    eax, eax
0x18000a4be  js      loc_18000A748
0x18000a4c4  mov     r12, [rsp+560h+ppURI]
0x18000a4c9  lea     rcx, ?g_userNameInfo@@3VCUserNameInfo@@A; lpCriticalSection
0x18000a4d0  mov     [rbp+460h+var_470], r13w
0x18000a4d5  mov     edi, r13d
0x18000a4d8  mov     [rbp+460h+var_250], r13w
0x18000a4e0  call    cs:__imp_EnterCriticalSection
0x18000a4e6  cmp     cs:NameBuffer, di
0x18000a4ed  lea     rbx, NameBuffer
0x18000a4f4  mov     esi, 101h
0x18000a4f9  jz      loc_18000B120
0x18000a4ff  lea     rcx, ?g_userNameInfo@@3VCUserNameInfo@@A; lpCriticalSection
0x18000a506  call    cs:__imp_LeaveCriticalSection
0x18000a50c  test    edi, edi
0x18000a50e  js      loc_18000A744
0x18000a514  mov     r15d, 7FFFFFFEh
0x18000a51a  lea     rdx, [rbp+460h+var_250]
0x18000a521  mov     ecx, r15d
0x18000a524  test    rcx, rcx
0x18000a527  jz      short loc_18000A55F
0x18000a529  movzx   eax, word ptr [rbx]
0x18000a52c  test    ax, ax
0x18000a52f  jz      short loc_18000A55A
0x18000a531  mov     [rdx], ax
0x18000a534  add     rbx, 2
0x18000a538  add     rdx, 2
0x18000a53c  dec     rcx
0x18000a53f  sub     rsi, 1
0x18000a543  jnz     short loc_18000A524
0x18000a545  mov     [rdx-2], r13w
0x18000a54a  mov     edi, 8007007Ah
0x18000a54f  jmp     loc_18000A73F
0x18000a554  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x18000a55a  test    rsi, rsi
0x18000a55d  jz      short loc_18000A545
0x18000a55f  mov     [rdx], r13w
0x18000a563  lea     rax, [rbp+460h+var_250]
0x18000a56a  mov     edx, 10Dh; unsigned __int64
0x18000a56f  mov     [rsp+560h+cchToCopy], rax; cchToCopy
0x18000a574  lea     r9, aVisited_0; "Visited: "
0x18000a57b  lea     r8, aSS_6; "%s%s@"
0x18000a582  lea     rcx, [rbp+460h+var_470]; unsigned __int16 *
0x18000a586  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000a58b  mov     edi, eax
0x18000a58d  test    eax, eax
0x18000a58f  js      loc_18000A73F
0x18000a595  mov     rax, [r12]
0x18000a599  lea     rdx, [rsp+560h+dwType]
0x18000a59e  mov     rcx, r12
0x18000a5a1  mov     [rsp+560h+dwType], r13d
0x18000a5a6  mov     rax, [rax+0C0h]
0x18000a5ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a5b2  mov     edi, eax
0x18000a5b4  test    eax, eax
0x18000a5b6  js      loc_18000A73F
0x18000a5bc  mov     eax, [rsp+560h+dwType]
0x18000a5c0  add     eax, 0FFFFFFF1h
0x18000a5c3  cmp     eax, 1
0x18000a5c6  ja      loc_18000B155
0x18000a5cc  mov     rax, [r12]
0x18000a5d0  lea     r8, [rsp+560h+var_520]
0x18000a5d5  xor     esi, esi
0x18000a5d7  mov     edx, 0Eh
0x18000a5dc  mov     rcx, r12
0x18000a5df  mov     [rsp+560h+var_520], esi
0x18000a5e3  mov     ebx, esi
0x18000a5e5  mov     rax, [rax+30h]
0x18000a5e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a5ee  test    eax, eax
0x18000a5f0  jns     loc_18000A879
0x18000a5f6  mov     rax, [r12]
0x18000a5fa  lea     r8, [rsp+560h+var_520]
0x18000a5ff  mov     edx, 7
0x18000a604  mov     rcx, r12
0x18000a607  mov     rax, [rax+30h]
0x18000a60b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a610  test    eax, eax
0x18000a612  js      short loc_18000A61E
0x18000a614  cmp     [rsp+560h+var_520], esi
0x18000a618  jnz     loc_18000B1BD
0x18000a61e  test    r13b, r13b
0x18000a621  jz      short loc_18000A64B
0x18000a623  mov     rax, [r12]
0x18000a627  lea     r8, [rsp+560h+var_520]
0x18000a62c  mov     edx, 5
0x18000a631  mov     rcx, r12
0x18000a634  mov     rax, [rax+30h]
0x18000a638  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a63d  test    eax, eax
0x18000a63f  js      short loc_18000A64B
0x18000a641  cmp     [rsp+560h+var_520], esi
0x18000a645  jnz     loc_18000B1C6
0x18000a64b  mov     qword ptr [rsp+560h+nSize], rsi
0x18000a650  mov     rcx, r12; pIUri
0x18000a653  test    ebx, ebx
0x18000a655  jnz     loc_18000B1CE
0x18000a65b  mov     [r14], rsi
0x18000a65e  lea     rdx, [rsp+560h+nSize]
0x18000a663  mov     rax, [r12]
0x18000a667  mov     rax, [rax+38h]
0x18000a66b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a670  mov     edi, eax
0x18000a672  test    eax, eax
0x18000a674  jnz     loc_18000B27F
0x18000a67a  mov     rax, qword ptr [rsp+560h+nSize]
0x18000a67f  mov     rcx, rsi; bstrString
0x18000a682  mov     qword ptr [rsp+560h+nSize], rcx
0x18000a687  mov     [r14], rax
0x18000a68a  call    cs:__imp_SysFreeString
0x18000a690  mov     rax, [r12]
0x18000a694  mov     rcx, r12
0x18000a697  mov     rax, [rax+8]
0x18000a69b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a6a0  mov     [r14+20h], r12
0x18000a6a4  jmp     short loc_18000A6B8
0x18000a6a6  lea     rcx, [rsp+560h+nSize]; void *
0x18000a6ab  call    ??1?$CComPtr@UIBrowserThreadState@@@ATL@@QEAA@XZ; ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(void)
0x18000a6b0  test    edi, edi
0x18000a6b2  js      loc_18000B299
0x18000a6b8  cmp     [rsp+560h+dwType], 9
0x18000a6bd  mov     rbx, rsi
0x18000a6c0  mov     r14, [r14]
0x18000a6c3  mov     [rsp+560h+ppv], rbx
0x18000a6c8  jz      loc_18000AF5A
0x18000a6ce  mov     rcx, r14
0x18000a6d1  movzx   eax, word ptr [rcx]
0x18000a6d4  test    ax, ax
0x18000a6d7  jz      loc_18000AF5A
0x18000a6dd  cmp     ax, 7Fh
0x18000a6e1  ja      short loc_18000A6E9
0x18000a6e3  add     rcx, 2
0x18000a6e7  jmp     short loc_18000A6D1
0x18000a6e9  mov     ecx, 1048h; dwBytes
0x18000a6ee  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a6f3  mov     rsi, rax
0x18000a6f6  test    rax, rax
0x18000a6f9  jz      loc_18000B1B3
0x18000a6ff  mov     r9, [rsp+560h+lpMem]
0x18000a704  mov     edx, 824h; cchDest
0x18000a709  mov     rcx, rax; pszDest
0x18000a70c  mov     r9, [r9]; pszSrc
0x18000a70f  call    StringCopyWorkerW
0x18000a714  mov     edi, eax
0x18000a716  test    eax, eax
0x18000a718  jns     loc_18000B179
0x18000a71e  mov     rcx, rsi; lpMem
0x18000a721  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a726  test    edi, edi
0x18000a728  jns     loc_18000AF5A
0x18000a72e  xor     r13d, r13d
0x18000a731  mov     rcx, rbx; bstrString
0x18000a734  call    cs:__imp_SysFreeString
0x18000a73a  mov     r14, [rsp+560h+lpMem]
0x18000a73f  mov     r15, [rsp+560h+var_500]
0x18000a744  mov     rsi, [rbp+460h+ppwsz]
0x18000a748  mov     rcx, [rsp+560h+ppURI]
0x18000a74d  test    rcx, rcx
0x18000a750  jz      short loc_18000A75E
0x18000a752  mov     rax, [rcx]
0x18000a755  mov     rax, [rax+10h]
0x18000a759  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a75e  test    edi, edi
0x18000a760  js      loc_18000AE10
0x18000a766  test    rsi, rsi
0x18000a769  jz      short loc_18000A76E
0x18000a76b  mov     [rsi], r13
0x18000a76e  mov     [r15], r13
0x18000a771  mov     rsi, [r14+10h]
0x18000a775  mov     rbx, [r14]
0x18000a778  mov     [rsp+560h+ppv], r13
0x18000a77d  call    cs:__imp_GetProcessHeap
0x18000a783  mov     edx, 8; dwFlags
0x18000a788  mov     r8d, 50h ; 'P'; dwBytes
0x18000a78e  mov     rcx, rax; hHeap
0x18000a791  call    cs:__imp_HeapAlloc
0x18000a797  mov     r12, rax
0x18000a79a  test    rax, rax
0x18000a79d  jz      loc_18000AEAA
0x18000a7a3  lea     rax, ??_7CHistoryData@@6B@; const CHistoryData::`vftable'
0x18000a7aa  mov     [r12+30h], r13
0x18000a7af  lea     r15, [r12+30h]
0x18000a7b4  mov     [r12], rax
0x18000a7b8  mov     rax, cs:c_li0
0x18000a7bf  lea     r14, [r12+38h]
0x18000a7c4  mov     [r14], r13
0x18000a7c7  lea     rcx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99; riid
0x18000a7ce  lea     r13, [r12+40h]
0x18000a7d3  mov     [r12+0Ch], rax
0x18000a7d8  mov     rdx, r15; ppv
0x18000a7db  mov     [r12+14h], rax
0x18000a7e0  mov     [r12+1Ch], rax
0x18000a7e5  mov     [r12+24h], rax
0x18000a7ea  mov     qword ptr [r13+0], 0
0x18000a7f2  mov     dword ptr [r12+8], 1
0x18000a7fb  mov     byte ptr [r12+48h], 1
0x18000a801  call    cs:__imp_PSCreateMemoryPropertyStore
0x18000a807  mov     edi, eax
0x18000a809  test    eax, eax
0x18000a80b  js      loc_18000AD71
0x18000a811  mov     rdx, r13; ppwsz
0x18000a814  mov     rcx, rbx; psz
0x18000a817  call    cs:__imp_SHStrDupW
0x18000a81d  mov     edi, eax
0x18000a81f  test    eax, eax
0x18000a821  js      loc_18000AD71
0x18000a827  mov     rdx, r14; ppwsz
0x18000a82a  mov     rcx, rsi; psz
0x18000a82d  call    cs:__imp_SHStrDupW
0x18000a833  mov     edi, eax
0x18000a835  test    eax, eax
0x18000a837  js      loc_18000AD71
0x18000a83d  xor     eax, eax
0x18000a83f  lea     rbx, dword_1805C31B0
0x18000a846  xorps   xmm0, xmm0
0x18000a849  mov     [rbp+460h+var_4D0], rax
0x18000a84d  movups  xmmword ptr [rbp+460h+pvar], xmm0
0x18000a851  mov     edx, 13h
0x18000a856  mov     dword ptr [rbp+460h+pvar+8], eax
0x18000a859  mov     word ptr [rbp+460h+pvar], dx
0x18000a85d  nop     dword ptr [rax]
0x18000a860  cmp     rax, 24h ; '$'
0x18000a864  jnb     short loc_18000A895
0x18000a866  lea     rcx, ds:0[rax*8]
0x18000a86e  cmp     dword ptr [rcx+rbx], 0Dh
0x18000a872  jz      short loc_18000A88A
0x18000a874  inc     rax
0x18000a877  jmp     short loc_18000A860
0x18000a879  cmp     [rsp+560h+var_520], ebx
0x18000a87d  mov     eax, 4000h
0x18000a882  cmovnz  ebx, eax
0x18000a885  jmp     loc_18000A5F6
0x18000a88a  cmp     dx, [rcx+rbx+4]
0x18000a88f  jnz     loc_18000AD66
0x18000a895  movups  xmm0, xmmword ptr cs:FMTID_InternetSite.Data1
0x18000a89c  mov     rcx, [r15]
0x18000a89f  lea     r8, [rbp+460h+pvar]
0x18000a8a3  mov     [rbp+460h+var_480], 0Dh
0x18000a8aa  lea     rdx, [rbp+460h+var_490]
0x18000a8ae  movups  [rbp+460h+var_490], xmm0
0x18000a8b2  mov     rax, [rcx]
0x18000a8b5  mov     rax, [rax+30h]
0x18000a8b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a8be  mov     byte ptr [r12+48h], 1
0x18000a8c4  mov     edi, eax
0x18000a8c6  test    eax, eax
0x18000a8c8  js      loc_18000AD71
0x18000a8ce  movzx   r8d, word ptr [rbp+460h+pvar]
0x18000a8d3  test    r8w, r8w
0x18000a8d7  jz      loc_18000B2A1
0x18000a8dd  xor     r10d, r10d
0x18000a8e0  mov     eax, r10d
0x18000a8e3  mov     ecx, r10d
0x18000a8e6  cmp     rax, 24h ; '$'
  ... truncated ...
```
