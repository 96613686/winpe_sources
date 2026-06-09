# CHistoryDataFactory::LoadHistoryDataEntryFromUrl(ushort const *,ushort * *,IHistoryData * *)

- ea: `0x180007300`
- end: `0x1800082fe`
- name: `?LoadHistoryDataEntryFromUrl@CHistoryDataFactory@@UEAAJPEBGPEAPEAGPEAPEAUIHistoryData@@@Z`
- size: `4094`
- prototype: `int(CHistoryDataFactory *__hidden this, const unsigned __int16 *, unsigned __int16 **, struct IHistoryData **)`
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180005030`
- `0x180007010`
- `0x180007300`
- `0x180009610`
- `0x1800096a0`
- `0x18000bc38`
- `0x1800114d0`
- `0x180046eb0`
- `0x18004bdd0`
- `0x1800654dc`
- `0x1800bf0d8`
- `0x1800ca4ac`
- `0x180591f80`
- `0x180594010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800079d1`
- `msvcrt!memcpy_s` at `0x1800079d1`
- `KERNEL32!InitOnceExecuteOnce` at `0x180007c0b`
- `KERNEL32!InitOnceExecuteOnce` at `0x180007c0b`
- `KERNEL32!GetProcessHeap` at `0x18000734a`
- `KERNEL32!GetProcessHeap` at `0x1800076b2`
- `KERNEL32!GetProcessHeap` at `0x180007a03`
- `KERNEL32!GetProcessHeap` at `0x180007de3`
- `KERNEL32!GetProcessHeap` at `0x180007e18`
- `KERNEL32!GetProcessHeap` at `0x180007eb9`
- `KERNEL32!GetProcessHeap` at `0x180007f81`
- `KERNEL32!GetProcessHeap` at `0x18000734a`
- `KERNEL32!GetProcessHeap` at `0x1800076b2`
- `KERNEL32!GetProcessHeap` at `0x180007a03`
- `KERNEL32!GetProcessHeap` at `0x180007de3`
- `KERNEL32!GetProcessHeap` at `0x180007e18`
- `KERNEL32!GetProcessHeap` at `0x180007eb9`
- `KERNEL32!GetProcessHeap` at `0x180007f81`
- `KERNEL32!HeapAlloc` at `0x180007364`
- `KERNEL32!HeapAlloc` at `0x1800076cc`
- `KERNEL32!HeapAlloc` at `0x180007f98`
- `KERNEL32!HeapAlloc` at `0x180007364`
- `KERNEL32!HeapAlloc` at `0x1800076cc`
- `KERNEL32!HeapAlloc` at `0x180007f98`
- `KERNEL32!LeaveCriticalSection` at `0x18000741e`
- `KERNEL32!LeaveCriticalSection` at `0x180008164`
- `KERNEL32!LeaveCriticalSection` at `0x18000741e`
- `KERNEL32!LeaveCriticalSection` at `0x180008164`
- `KERNEL32!EnterCriticalSection` at `0x1800073f2`
- `KERNEL32!EnterCriticalSection` at `0x1800073f2`
- `KERNEL32!HeapFree` at `0x180007a17`
- `KERNEL32!HeapFree` at `0x180007df7`
- `KERNEL32!HeapFree` at `0x180007e2c`
- `KERNEL32!HeapFree` at `0x180007ecd`
- `KERNEL32!HeapFree` at `0x180007a17`
- `KERNEL32!HeapFree` at `0x180007df7`
- `KERNEL32!HeapFree` at `0x180007e2c`
- `KERNEL32!HeapFree` at `0x180007ecd`
- `api-ms-win-downlevel-shlwapi-l1-1-0!QISearch` at `0x180007d2e`
- `api-ms-win-downlevel-shlwapi-l1-1-0!QISearch` at `0x180007d2e`
- `OLEAUT32!__imp_SysFreeString` at `0x1800075a8`
- `OLEAUT32!__imp_SysFreeString` at `0x180007663`
- `OLEAUT32!__imp_SysFreeString` at `0x180007dbe`
- `OLEAUT32!__imp_SysFreeString` at `0x180007dce`
- `OLEAUT32!__imp_SysFreeString` at `0x180008288`
- `OLEAUT32!__imp_SysFreeString` at `0x18000829b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800075a8`
- `OLEAUT32!__imp_SysFreeString` at `0x180007663`
- `OLEAUT32!__imp_SysFreeString` at `0x180007dbe`
- `OLEAUT32!__imp_SysFreeString` at `0x180007dce`
- `OLEAUT32!__imp_SysFreeString` at `0x180008288`
- `OLEAUT32!__imp_SysFreeString` at `0x18000829b`
- `iertutil!CreateIUriBuilder` at `0x1800081d4`
- `iertutil!CreateIUriBuilder` at `0x1800081d4`
- `iertutil!CreateUri` at `0x1800073c0`
- `iertutil!CreateUri` at `0x1800073c0`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x180007bcc`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x180007bcc`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x180007941`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x180007941`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1800079e4`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180007cf2`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180007e9d`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180007ead`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x1800079e4`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180007cf2`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180007e9d`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180007ead`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x18000775e`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x18000777a`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x180007d8a`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x18000775e`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x18000777a`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x180007d8a`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHCreateMemStream` at `0x180007a8a`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHCreateMemStream` at `0x180007a8a`
- `Secur32!GetUserNameExW` at `0x180008121`
- `Secur32!GetUserNameExW` at `0x180008121`
- `WININET!GetUrlCacheEntryBinaryBlob` at `0x180007920`
- `WININET!GetUrlCacheEntryBinaryBlob` at `0x180007920`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180007742`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180007ad0`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180007742`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x180007ad0`

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
    v14 = &SrcStr;
    v15 = 257;
    if ( !SrcStr )
    {
      nSize[0] = 257;
      if ( GetUserNameExW((EXTENDED_NAME_FORMAT)65538, &SrcStr, nSize) )
      {
        ConvertToUtf8Escaped(&SrcStr, 257);
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
            if ( dword_1806073F0[2 * v38] == 13 )
            {
              if ( LOWORD(dword_1806073F0[2 * v38 + 1]) != 19 )
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
            if ( dword_1806073F0[2 * j] == 6 )
            {
              LOBYTE(v43) = LOWORD(pvar[0]) != LOWORD(dword_1806073F0[2 * j + 1]);
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
            if ( dword_1806073F0[2 * k] == 9 )
            {
              LOBYTE(v45) = v41 != LOWORD(dword_1806073F0[2 * k + 1]);
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
0x180007300  push    rbp
0x180007302  push    rbx
0x180007303  push    rsi
0x180007304  push    r13
0x180007306  push    r14
0x180007308  push    r15
0x18000730a  lea     rbp, [rsp-438h]
0x180007312  sub     rsp, 538h
0x180007319  mov     rax, cs:__security_cookie
0x180007320  xor     rax, rsp
0x180007323  mov     [rbp+460h+var_40], rax
0x18000732a  xor     r13d, r13d
0x18000732d  mov     [rsp+560h+var_500], r9
0x180007332  mov     [rbp+460h+ppwsz], r8
0x180007336  mov     r15, r9
0x180007339  mov     rsi, r8
0x18000733c  mov     rbx, rdx
0x18000733f  test    r8, r8
0x180007342  jz      short loc_180007347
0x180007344  mov     [r8], r13
0x180007347  mov     [r9], r13
0x18000734a  call    cs:__imp_GetProcessHeap
0x180007351  nop     dword ptr [rax+rax+00h]
0x180007356  mov     edx, 8; dwFlags
0x18000735b  mov     r8d, 28h ; '('; dwBytes
0x180007361  mov     rcx, rax; hHeap
0x180007364  call    cs:__imp_HeapAlloc
0x18000736b  nop     dword ptr [rax+rax+00h]
0x180007370  mov     [rsp+560h+lpMem], rax
0x180007375  mov     r14, rax
0x180007378  test    rax, rax
0x18000737b  jz      loc_180007472
0x180007381  mov     [rax], r13
0x180007384  lea     r9, [rsp+560h+ppURI]; ppURI
0x180007389  add     rax, 8
0x18000738d  mov     [r14+10h], r13
0x180007391  mov     [r14+18h], r13b
0x180007395  xor     r8d, r8d; dwReserved
0x180007398  mov     [rsp+560h+arg_0], rdi
0x1800073a0  mov     edx, 3002B84h; dwFlags
0x1800073a5  mov     rcx, rbx; pwzURI
0x1800073a8  mov     [rsp+560h+var_30], r12
0x1800073b0  mov     [rax], r13
0x1800073b3  mov     [r14+20h], r13
0x1800073b7  mov     [rbp+460h+var_498], rax
0x1800073bb  mov     [rsp+560h+ppURI], r13
0x1800073c0  call    cs:__imp_CreateUri
0x1800073c7  nop     dword ptr [rax+rax+00h]
0x1800073cc  mov     edi, eax
0x1800073ce  test    eax, eax
0x1800073d0  js      loc_18000767D
0x1800073d6  mov     r12, [rsp+560h+ppURI]
0x1800073db  lea     rcx, ?g_userNameInfo@@3VCUserNameInfo@@A; lpCriticalSection
0x1800073e2  mov     [rbp+460h+var_470], r13w
0x1800073e7  mov     edi, r13d
0x1800073ea  mov     [rbp+460h+var_250], r13w
0x1800073f2  call    cs:__imp_EnterCriticalSection
0x1800073f9  nop     dword ptr [rax+rax+00h]
0x1800073fe  cmp     cs:SrcStr, di
0x180007405  lea     rbx, SrcStr
0x18000740c  mov     esi, 101h
0x180007411  jz      loc_180008110
0x180007417  lea     rcx, ?g_userNameInfo@@3VCUserNameInfo@@A; lpCriticalSection
0x18000741e  call    cs:__imp_LeaveCriticalSection
0x180007425  nop     dword ptr [rax+rax+00h]
0x18000742a  test    edi, edi
0x18000742c  js      loc_180007679
0x180007432  mov     r15d, 7FFFFFFEh
0x180007438  lea     rdx, [rbp+460h+var_250]
0x18000743f  mov     ecx, r15d
0x180007442  test    rcx, rcx
0x180007445  jz      short loc_18000747D
0x180007447  movzx   eax, word ptr [rbx]
0x18000744a  test    ax, ax
0x18000744d  jz      short loc_180007478
0x18000744f  mov     [rdx], ax
0x180007452  add     rbx, 2
0x180007456  add     rdx, 2
0x18000745a  dec     rcx
0x18000745d  sub     rsi, 1
0x180007461  jnz     short loc_180007442
0x180007463  mov     [rdx-2], r13w
0x180007468  mov     edi, 8007007Ah
0x18000746d  jmp     loc_180007674
0x180007472  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x180007478  test    rsi, rsi
0x18000747b  jz      short loc_180007463
0x18000747d  mov     [rdx], r13w
0x180007481  lea     rax, [rbp+460h+var_250]
0x180007488  mov     edx, 10Dh; unsigned __int64
0x18000748d  mov     [rsp+560h+cchToCopy], rax; cchToCopy
0x180007492  lea     r9, aVisited_0; "Visited: "
0x180007499  lea     r8, aSS_6; "%s%s@"
0x1800074a0  lea     rcx, [rbp+460h+var_470]; unsigned __int16 *
0x1800074a4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800074a9  mov     edi, eax
0x1800074ab  test    eax, eax
0x1800074ad  js      loc_180007674
0x1800074b3  mov     rax, [r12]
0x1800074b7  lea     rdx, [rsp+560h+dwType]
0x1800074bc  mov     rcx, r12
0x1800074bf  mov     [rsp+560h+dwType], r13d
0x1800074c4  mov     rax, [rax+0C0h]
0x1800074cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800074d0  mov     edi, eax
0x1800074d2  test    eax, eax
0x1800074d4  js      loc_180007674
0x1800074da  mov     eax, [rsp+560h+dwType]
0x1800074de  add     eax, 0FFFFFFF1h
0x1800074e1  cmp     eax, 1
0x1800074e4  ja      loc_18000814B
0x1800074ea  mov     rax, [r12]
0x1800074ee  lea     r8, [rsp+560h+var_520]
0x1800074f3  xor     esi, esi
0x1800074f5  mov     edx, 0Eh
0x1800074fa  mov     rcx, r12
0x1800074fd  mov     [rsp+560h+var_520], esi
0x180007501  mov     ebx, esi
0x180007503  mov     rax, [rax+30h]
0x180007507  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000750c  test    eax, eax
0x18000750e  jns     loc_1800077C9
0x180007514  mov     rax, [r12]
0x180007518  lea     r8, [rsp+560h+var_520]
0x18000751d  mov     edx, 7
0x180007522  mov     rcx, r12
0x180007525  mov     rax, [rax+30h]
0x180007529  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000752e  test    eax, eax
0x180007530  js      short loc_18000753C
0x180007532  cmp     [rsp+560h+var_520], esi
0x180007536  jnz     loc_1800081B9
0x18000753c  test    r13b, r13b
0x18000753f  jz      short loc_180007569
0x180007541  mov     rax, [r12]
0x180007545  lea     r8, [rsp+560h+var_520]
0x18000754a  mov     edx, 5
0x18000754f  mov     rcx, r12
0x180007552  mov     rax, [rax+30h]
0x180007556  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000755b  test    eax, eax
0x18000755d  js      short loc_180007569
0x18000755f  cmp     [rsp+560h+var_520], esi
0x180007563  jnz     loc_1800081C2
0x180007569  mov     qword ptr [rsp+560h+nSize], rsi
0x18000756e  mov     rcx, r12; pIUri
0x180007571  test    ebx, ebx
0x180007573  jnz     loc_1800081CA
0x180007579  mov     [r14], rsi
0x18000757c  lea     rdx, [rsp+560h+nSize]
0x180007581  mov     rax, [r12]
0x180007585  mov     rax, [rax+38h]
0x180007589  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000758e  mov     edi, eax
0x180007590  test    eax, eax
0x180007592  jnz     loc_180008281
0x180007598  mov     rax, qword ptr [rsp+560h+nSize]
0x18000759d  mov     rcx, rsi; bstrString
0x1800075a0  mov     qword ptr [rsp+560h+nSize], rcx
0x1800075a5  mov     [r14], rax
0x1800075a8  call    cs:__imp_SysFreeString
0x1800075af  nop     dword ptr [rax+rax+00h]
0x1800075b4  mov     rax, [r12]
0x1800075b8  mov     rcx, r12
0x1800075bb  mov     rax, [rax+8]
0x1800075bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800075c4  mov     [r14+20h], r12
0x1800075c8  jmp     short loc_1800075DC
0x1800075ca  lea     rcx, [rsp+560h+nSize]; void *
0x1800075cf  call    ??1?$CComPtr@UIBrowserThreadState@@@ATL@@QEAA@XZ; ATL::CComPtr<IBrowserThreadState>::~CComPtr<IBrowserThreadState>(void)
0x1800075d4  test    edi, edi
0x1800075d6  js      loc_1800082A7
0x1800075dc  cmp     [rsp+560h+dwType], 9
0x1800075e1  mov     rbx, rsi
0x1800075e4  mov     r14, [r14]
0x1800075e7  mov     [rsp+560h+ppv], rbx
0x1800075ec  jz      loc_180007F3D
0x1800075f2  mov     rcx, r14
0x1800075f5  nop     word ptr [rax+rax+00000000h]
0x180007600  movzx   eax, word ptr [rcx]
0x180007603  test    ax, ax
0x180007606  jz      loc_180007F3D
0x18000760c  cmp     ax, 7Fh
0x180007610  ja      short loc_180007618
0x180007612  add     rcx, 2
0x180007616  jmp     short loc_180007600
0x180007618  mov     ecx, 1048h; dwBytes
0x18000761d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007622  mov     rsi, rax
0x180007625  test    rax, rax
0x180007628  jz      loc_1800081AF
0x18000762e  mov     r9, [rsp+560h+lpMem]
0x180007633  mov     edx, 824h; cchDest
0x180007638  mov     rcx, rax; pszDest
0x18000763b  mov     r9, [r9]; pszSrc
0x18000763e  call    StringCopyWorkerW
0x180007643  mov     edi, eax
0x180007645  test    eax, eax
0x180007647  jns     loc_180008175
0x18000764d  mov     rcx, rsi; lpMem
0x180007650  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180007655  test    edi, edi
0x180007657  jns     loc_180007F3D
0x18000765d  xor     r13d, r13d
0x180007660  mov     rcx, rbx; bstrString
0x180007663  call    cs:__imp_SysFreeString
0x18000766a  nop     dword ptr [rax+rax+00h]
0x18000766f  mov     r14, [rsp+560h+lpMem]
0x180007674  mov     r15, [rsp+560h+var_500]
0x180007679  mov     rsi, [rbp+460h+ppwsz]
0x18000767d  mov     rcx, [rsp+560h+ppURI]
0x180007682  test    rcx, rcx
0x180007685  jz      short loc_180007693
0x180007687  mov     rax, [rcx]
0x18000768a  mov     rax, [rax+10h]
0x18000768e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007693  test    edi, edi
0x180007695  js      loc_180007DB6
0x18000769b  test    rsi, rsi
0x18000769e  jz      short loc_1800076A3
0x1800076a0  mov     [rsi], r13
0x1800076a3  mov     [r15], r13
0x1800076a6  mov     rsi, [r14+10h]
0x1800076aa  mov     rbx, [r14]
0x1800076ad  mov     [rsp+560h+ppv], r13
0x1800076b2  call    cs:__imp_GetProcessHeap
0x1800076b9  nop     dword ptr [rax+rax+00h]
0x1800076be  mov     edx, 8; dwFlags
0x1800076c3  mov     r8d, 50h ; 'P'; dwBytes
0x1800076c9  mov     rcx, rax; hHeap
0x1800076cc  call    cs:__imp_HeapAlloc
0x1800076d3  nop     dword ptr [rax+rax+00h]
0x1800076d8  mov     r12, rax
0x1800076db  test    rax, rax
0x1800076de  jz      loc_180007E75
0x1800076e4  lea     rax, ??_7CHistoryData@@6B@; const CHistoryData::`vftable'
0x1800076eb  mov     [r12+30h], r13
0x1800076f0  lea     r15, [r12+30h]
0x1800076f5  mov     [r12], rax
0x1800076f9  mov     rax, cs:c_li0
0x180007700  lea     r14, [r12+38h]
0x180007705  mov     [r14], r13
0x180007708  lea     rcx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99; riid
0x18000770f  lea     r13, [r12+40h]
0x180007714  mov     [r12+0Ch], rax
0x180007719  mov     rdx, r15; ppv
0x18000771c  mov     [r12+14h], rax
0x180007721  mov     [r12+1Ch], rax
0x180007726  mov     [r12+24h], rax
0x18000772b  mov     qword ptr [r13+0], 0
0x180007733  mov     dword ptr [r12+8], 1
0x18000773c  mov     byte ptr [r12+48h], 1
0x180007742  call    cs:__imp_PSCreateMemoryPropertyStore
0x180007749  nop     dword ptr [rax+rax+00h]
0x18000774e  mov     edi, eax
0x180007750  test    eax, eax
0x180007752  js      loc_180007D0B
0x180007758  mov     rdx, r13; ppwsz
0x18000775b  mov     rcx, rbx; psz
0x18000775e  call    cs:__imp_SHStrDupW
0x180007765  nop     dword ptr [rax+rax+00h]
0x18000776a  mov     edi, eax
0x18000776c  test    eax, eax
0x18000776e  js      loc_180007D0B
0x180007774  mov     rdx, r14; ppwsz
0x180007777  mov     rcx, rsi; psz
0x18000777a  call    cs:__imp_SHStrDupW
0x180007781  nop     dword ptr [rax+rax+00h]
0x180007786  mov     edi, eax
0x180007788  test    eax, eax
0x18000778a  js      loc_180007D0B
0x180007790  xor     eax, eax
0x180007792  lea     rbx, dword_1806073F0
0x180007799  xorps   xmm0, xmm0
0x18000779c  mov     [rbp+460h+var_4D0], rax
0x1800077a0  movups  xmmword ptr [rbp+460h+pvar], xmm0
0x1800077a4  mov     edx, 13h
0x1800077a9  mov     dword ptr [rbp+460h+pvar+8], eax
0x1800077ac  mov     word ptr [rbp+460h+pvar], dx
0x1800077b0  cmp     rax, 24h ; '$'
0x1800077b4  jnb     short loc_1800077E5
0x1800077b6  lea     rcx, ds:0[rax*8]
0x1800077be  cmp     dword ptr [rcx+rbx], 0Dh
0x1800077c2  jz      short loc_1800077DA
0x1800077c4  inc     rax
0x1800077c7  jmp     short loc_1800077B0
0x1800077c9  cmp     [rsp+560h+var_520], ebx
0x1800077cd  mov     eax, 4000h
0x1800077d2  cmovnz  ebx, eax
0x1800077d5  jmp     loc_180007514
0x1800077da  cmp     dx, [rcx+rbx+4]
0x1800077df  jnz     loc_180007D00
0x1800077e5  movups  xmm0, xmmword ptr cs:FMTID_InternetSite.Data1
0x1800077ec  mov     rcx, [r15]
0x1800077ef  lea     r8, [rbp+460h+pvar]
0x1800077f3  mov     [rbp+460h+var_480], 0Dh
0x1800077fa  lea     rdx, [rbp+460h+var_490]
0x1800077fe  movups  [rbp+460h+var_490], xmm0
0x180007802  mov     rax, [rcx]
0x180007805  mov     rax, [rax+30h]
  ... truncated ...
```
