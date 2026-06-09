# PackageCollector::Search(void)

- ea: `0x1800322c0`
- end: `0x180032b69`
- name: `?Search@PackageCollector@@QEAA?AV?$vector@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@V?$allocator@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@@2@@std@@XZ`
- size: `2217`
- prototype: ``
- caller_count: `3`
- callee_count: `22`
- tags: `file_ops, reparse_path, loader_planting, broker_com_uri`

## callers

- `0x180008d50`
- `0x18000f58c`
- `0x1800133d8`

## callees

- `0x180001a30`
- `0x180001a40`
- `0x180001a70`
- `0x180001b14`
- `0x180001c10`
- `0x180001cf0`
- `0x180001d9c`
- `0x180002fd4`
- `0x1800046ac`
- `0x1800090e0`
- `0x18000918c`
- `0x18000929c`
- `0x180009fac`
- `0x18000fd40`
- `0x180024508`
- `0x180028ee8`
- `0x180028f94`
- `0x180031818`
- `0x1800322c0`
- `0x1800333c8`
- `0x18003586a`
- `0x1800358a0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800323e3`
- `msvcrt!_wcsicmp` at `0x1800323e3`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800325c9`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800325e5`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800327d8`
- `msvcrt!??3@YAXPEAX@Z` at `0x180032829`
- `msvcrt!??3@YAXPEAX@Z` at `0x180032841`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800325c9`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800325e5`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800327d8`
- `msvcrt!??3@YAXPEAX@Z` at `0x180032829`
- `msvcrt!??3@YAXPEAX@Z` at `0x180032841`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032582`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032582`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180032569`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180032569`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180032339`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18003235d`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180032339`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18003235d`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800327eb`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800327eb`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180032814`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180032814`
- `api-ms-win-core-path-l1-1-0!PathCchCombineEx` at `0x18003253b`
- `api-ms-win-core-path-l1-1-0!PathCchCombineEx` at `0x1800326e9`
- `api-ms-win-core-path-l1-1-0!PathCchCombineEx` at `0x18003253b`
- `api-ms-win-core-path-l1-1-0!PathCchCombineEx` at `0x1800326e9`
- `api-ms-win-core-path-l1-1-0!PathCchFindExtension` at `0x1800323bd`
- `api-ms-win-core-path-l1-1-0!PathCchFindExtension` at `0x1800323bd`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180032380`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180032380`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
_QWORD *__fastcall PackageCollector::Search(__int64 a1, _QWORD *a2)
{
  __int64 v3; // rbx
  __int64 v4; // rsi
  const WCHAR *v5; // rcx
  const char *v6; // r9
  const WCHAR *v7; // rcx
  const WCHAR *v8; // rcx
  LPWSTR FileNameW; // rdi
  const WCHAR *v10; // rcx
  HRESULT Extension; // eax
  void *v12; // r14
  __int64 v13; // r8
  __int64 v14; // rax
  __int64 v15; // rcx
  __int64 v16; // rdx
  unsigned __int64 v17; // r8
  const WCHAR *v18; // r9
  const WCHAR *v19; // r8
  WCHAR *v20; // r12
  HRESULT v21; // edi
  int v22; // ecx
  HANDLE FirstFileW; // rdi
  int v24; // r8d
  int v25; // r9d
  int v26; // ecx
  DWORD LastError; // r8d
  const char *v28; // r9
  __int64 v29; // r9
  WCHAR *v30; // rax
  __int64 v31; // rcx
  unsigned __int64 v32; // rdx
  const WCHAR *v33; // r8
  PWSTR v34; // r15
  HRESULT v35; // r14d
  void *v36; // r14
  __int64 v37; // r8
  __int64 v38; // r8
  __int64 v39; // rax
  __int64 v41; // rax
  __int64 v42; // rax
  int v43; // ecx
  int v44; // r8d
  int v45; // r9d
  __int64 v46; // rax
  __int64 v47; // rax
  int v48; // ecx
  __int64 v49; // r8
  int v50; // r9d
  unsigned int v51; // eax
  int v52; // r8d
  __int64 v53; // rax
  __int64 v54; // rax
  int v55; // r8d
  int v56; // r9d
  __int64 v57; // rax
  __int64 v58; // rax
  __int64 v59; // r8
  int v60; // r9d
  unsigned int v61; // eax
  __int64 v62; // rax
  __int64 v63; // rax
  int v64; // r8d
  int v65; // r9d
  unsigned int v66; // eax
  int dwFlags; // [rsp+20h] [rbp-E0h]
  WCHAR *cFileName; // [rsp+40h] [rbp-C0h] BYREF
  int v69[2]; // [rsp+48h] [rbp-B8h] BYREF
  void *v70; // [rsp+50h] [rbp-B0h] BYREF
  int v71; // [rsp+58h] [rbp-A8h]
  PWSTR pszPathOut[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v73; // [rsp+70h] [rbp-90h]
  __int64 v74; // [rsp+78h] [rbp-88h]
  PCWSTR ppszExt; // [rsp+80h] [rbp-80h] BYREF
  PWSTR v76[2]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v77; // [rsp+98h] [rbp-68h]
  __int64 v78; // [rsp+A0h] [rbp-60h]
  void *v79; // [rsp+A8h] [rbp-58h] BYREF
  HANDLE v80; // [rsp+B0h] [rbp-50h] BYREF
  _WORD v81[8]; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v82; // [rsp+C8h] [rbp-38h]
  __int64 v83; // [rsp+D0h] [rbp-30h]
  _QWORD *v84; // [rsp+D8h] [rbp-28h]
  PCWSTR pszMore[2]; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v86; // [rsp+F0h] [rbp-10h]
  unsigned __int64 v87; // [rsp+F8h] [rbp-8h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+100h] [rbp+0h] BYREF
  _WORD v89[8]; // [rsp+350h] [rbp+250h] BYREF
  __int64 v90; // [rsp+360h] [rbp+260h]
  __int64 v91; // [rsp+368h] [rbp+268h]
  wil::details::in1diag3 *retaddr; // [rsp+3C8h] [rbp+2C8h]

  v84 = a2;
  *a2 = 0;
  a2[1] = 0;
  a2[2] = 0;
  v71 = 1;
  v3 = *(_QWORD *)(a1 + 8);
  v4 = *(_QWORD *)(a1 + 16);
  while ( v3 != v4 )
  {
    if ( *(_QWORD *)(v3 + 24) < 8u )
      v5 = (const WCHAR *)v3;
    else
      v5 = *(const WCHAR **)v3;
    if ( GetFileAttributesW(v5) == -1 )
    {
      if ( (unsigned int)dword_1800495B0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800495B0, 0) )
      {
        v41 = std::wstring::c_str(v3);
        v42 = _tlgWrapSz<unsigned short>::_tlgWrapSz<unsigned short>(&v70, v41);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          v43,
          (unsigned int)byte_18004198B,
          v44,
          v45,
          v42);
      }
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0xC3,
        (unsigned int)"onecoreuap\\admin\\prov\\lib\\packagecollector.cpp",
        v6);
    }
    if ( *(_QWORD *)(v3 + 24) < 8u )
      v7 = (const WCHAR *)v3;
    else
      v7 = *(const WCHAR **)v3;
    if ( (GetFileAttributesW(v7) & 0x10) != 0 )
    {
      v87 = 7;
      v86 = 0;
      LOWORD(pszMore[0]) = 0;
      std::wstring::assign(pszMore, L"*.ppkg");
      *(_OWORD *)pszPathOut = 0;
      v16 = 0;
      v73 = 0;
      v17 = v86 + 6 + *(_QWORD *)(v3 + 16);
      if ( v17 )
      {
        if ( v17 > 0x7FFFFFFFFFFFFFFFLL )
          std::vector<std::unique_ptr<ProvPackage>>::_Xlen(v15, 0, v17);
        std::vector<unsigned short>::_Reallocate(pszPathOut, v17);
        v16 = v73;
      }
      v18 = (const WCHAR *)pszMore;
      if ( v87 >= 8 )
        v18 = pszMore[0];
      if ( *(_QWORD *)(v3 + 24) < 8u )
        v19 = (const WCHAR *)v3;
      else
        v19 = *(const WCHAR **)v3;
      v20 = pszPathOut[0];
      v21 = PathCchCombineEx(pszPathOut[0], (signed __int64)(v16 - (unsigned __int64)pszPathOut[0]) >> 1, v19, v18, 1u);
      if ( v21 < 0 )
      {
        if ( (unsigned int)dword_1800495B0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800495B0, 0) )
        {
          LODWORD(cFileName) = v21;
          v62 = std::vector<unsigned short>::data(pszPathOut);
          v63 = _tlgWrapSz<unsigned short>::_tlgWrapSz<unsigned short>(&v70, v62);
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
            (unsigned int)&cFileName,
            (unsigned int)&dword_18004189C,
            v64,
            v65,
            v63,
            (__int64)&cFileName);
        }
        v66 = wil::verify_hresult<long>((unsigned int)v21);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xE6,
          (unsigned int)"onecoreuap\\admin\\prov\\lib\\packagecollector.cpp",
          (const char *)v66,
          dwFlags);
      }
      memset_0(&FindFileData, 0, sizeof(FindFileData));
      FirstFileW = FindFirstFileW(v20, &FindFileData);
      v80 = FirstFileW;
      if ( FirstFileW == (HANDLE)-1LL )
      {
        LastError = GetLastError();
        if ( LastError != 2 )
        {
          if ( (unsigned int)dword_1800495B0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800495B0, 0) )
          {
            LODWORD(cFileName) = v52;
            v53 = std::vector<unsigned short>::data(pszPathOut);
            v54 = _tlgWrapSz<unsigned short>::_tlgWrapSz<unsigned short>(&v70, v53);
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
              (unsigned int)&cFileName,
              (unsigned int)byte_180041915,
              v55,
              v56,
              v54,
              (__int64)&cFileName);
          }
          wil::details::in1diag3::Throw_GetLastError(
            retaddr,
            (void *)0xF9,
            (unsigned int)"onecoreuap\\admin\\prov\\lib\\packagecollector.cpp",
            v28);
        }
        if ( (unsigned int)dword_1800495B0 > 4 )
        {
          cFileName = v20;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
            v26,
            (unsigned int)word_18004186A,
            LastError,
            (_DWORD)v28,
            (__int64)&cFileName);
        }
        if ( v20 )
          operator delete(v20);
        if ( v87 >= 8 )
          goto LABEL_74;
      }
      else
      {
        do
        {
          if ( (unsigned int)dword_1800495B0 > 5 )
          {
            cFileName = FindFileData.cFileName;
            *(_QWORD *)v69 = v20;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
              v22,
              (unsigned int)byte_1800418D9,
              v24,
              v25,
              (__int64)v69,
              (__int64)&cFileName);
          }
          v29 = 260;
          v30 = FindFileData.cFileName;
          do
          {
            if ( !*v30 )
              break;
            ++v30;
            --v29;
          }
          while ( v29 );
          if ( !v29 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x104,
              (unsigned int)"onecoreuap\\admin\\prov\\lib\\packagecollector.cpp",
              (const char *)0x80070057LL,
              dwFlags);
          *(_OWORD *)v76 = 0;
          v31 = 0;
          v77 = 0;
          v32 = ((260 - v29) & ((unsigned __int128)-(__int128)(unsigned __int64)v29 >> 64) & -(__int64)(v29 != 0))
              + *(_QWORD *)(v3 + 16)
              + 6LL;
          if ( v32 )
          {
            if ( v32 > 0x7FFFFFFFFFFFFFFFLL )
              std::vector<std::unique_ptr<ProvPackage>>::_Xlen(0, v32, -v29);
            std::vector<unsigned short>::_Reallocate(v76, v32);
            v31 = v77;
          }
          if ( *(_QWORD *)(v3 + 24) < 8u )
            v33 = (const WCHAR *)v3;
          else
            v33 = *(const WCHAR **)v3;
          v34 = v76[0];
          v35 = PathCchCombineEx(
                  v76[0],
                  (signed __int64)(v31 - (unsigned __int64)v76[0]) >> 1,
                  v33,
                  FindFileData.cFileName,
                  1u);
          if ( v35 < 0 )
          {
            if ( (unsigned int)dword_1800495B0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800495B0, 0) )
            {
              LODWORD(cFileName) = v35;
              _tlgWrapSz<unsigned short>::_tlgWrapSz<unsigned short>(&v70, FindFileData.cFileName);
              v57 = std::vector<unsigned short>::data(v76);
              v58 = _tlgWrapSz<unsigned short>::_tlgWrapSz<unsigned short>(&v79, v57);
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
                (unsigned int)&cFileName,
                (unsigned int)byte_18004181B,
                v59,
                v60,
                v58,
                v59,
                (__int64)&cFileName);
            }
            v61 = wil::verify_hresult<long>((unsigned int)v35);
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x113,
              (unsigned int)"onecoreuap\\admin\\prov\\lib\\packagecollector.cpp",
              (const char *)v61,
              dwFlags);
          }
          v36 = operator new(0xA8u);
          v70 = v36;
          if ( v36 )
          {
            *(_QWORD *)v69 = v81;
            v83 = 7;
            v82 = 0;
            v81[0] = 0;
            if ( *v34 )
            {
              v37 = -1;
              do
                ++v37;
              while ( v34[v37] );
            }
            std::wstring::assign(v81, v34);
            v91 = 7;
            v90 = 0;
            v89[0] = 0;
            if ( FindFileData.cFileName[0] )
            {
              v38 = -1;
              do
                ++v38;
              while ( FindFileData.cFileName[v38] );
            }
            std::wstring::assign(v89, FindFileData.cFileName);
            v39 = ProvPackage::ProvPackage(v36, v89, v81);
          }
          else
          {
            v39 = 0;
          }
          *(_QWORD *)v69 = v39;
          std::vector<std::unique_ptr<ProvPackage>>::emplace_back<ProvPackage *>(a2, v69);
          if ( v34 )
            operator delete(v34);
        }
        while ( FindNextFileW(FirstFileW, &FindFileData) );
        if ( FirstFileW )
          FindClose(FirstFileW);
        if ( v20 )
          operator delete(v20);
        if ( v87 >= 8 )
LABEL_74:
          operator delete((void *)pszMore[0]);
      }
    }
    else
    {
      if ( *(_QWORD *)(v3 + 24) < 8u )
        v8 = (const WCHAR *)v3;
      else
        v8 = *(const WCHAR **)v3;
      FileNameW = PathFindFileNameW(v8);
      if ( !FileNameW )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xC9,
          (unsigned int)"onecoreuap\\admin\\prov\\lib\\packagecollector.cpp",
          (const char *)0x80070057LL,
          dwFlags);
      ppszExt = 0;
      if ( *(_QWORD *)(v3 + 24) < 8u )
        v10 = (const WCHAR *)v3;
      else
        v10 = *(const WCHAR **)v3;
      Extension = PathCchFindExtension(v10, *(_QWORD *)(v3 + 16) + 1LL, &ppszExt);
      if ( Extension < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xCC,
          (unsigned int)"onecoreuap\\admin\\prov\\lib\\packagecollector.cpp",
          (const char *)(unsigned int)Extension,
          dwFlags);
      if ( _wcsicmp(ppszExt, L".ppkg") )
      {
        if ( (unsigned int)dword_1800495B0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800495B0, 0x400000000000LL) )
        {
          LODWORD(cFileName) = -2147024809;
          _tlgWrapSz<unsigned short>::_tlgWrapSz<unsigned short>(&v70, FileNameW);
          v46 = std::wstring::c_str(v3);
          v47 = _tlgWrapSz<unsigned short>::_tlgWrapSz<unsigned short>(&v80, v46);
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
            v48,
            (unsigned int)&byte_18004194F,
            v49,
            v50,
            v47,
            v49,
            (__int64)&cFileName);
        }
        v51 = wil::verify_hresult<long>(2147942487LL);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xD3,
          (unsigned int)"onecoreuap\\admin\\prov\\lib\\packagecollector.cpp",
          (const char *)v51,
          dwFlags);
      }
      v12 = operator new(0xA8u);
      v79 = v12;
      if ( v12 )
      {
        *(_QWORD *)v69 = v76;
        v78 = 7;
        v77 = 0;
        LOWORD(v76[0]) = 0;
        std::wstring::assign(v76);
        v74 = 7;
        v73 = 0;
        LOWORD(pszPathOut[0]) = 0;
        if ( *FileNameW )
        {
          v13 = -1;
          do
            ++v13;
          while ( FileNameW[v13] );
        }
        std::wstring::assign(pszPathOut, FileNameW);
        v14 = ProvPackage::ProvPackage(v12, pszPathOut, v76);
      }
      else
      {
        v14 = 0;
      }
      cFileName = (WCHAR *)v14;
      std::vector<std::unique_ptr<ProvPackage>>::emplace_back<ProvPackage *>(a2, &cFileName);
    }
    v3 += 32;
  }
  if ( (unsigned int)dword_1800495B0 > 5 )
    tlgWriteTransfer_EventWriteTransfer(&dword_1800495B0, byte_1800417F1, 0, 0, 2, v89);
  return a2;
}

```

## disassembly

```asm
0x1800322c0  push    rbp
0x1800322c2  push    rbx
0x1800322c3  push    rsi
0x1800322c4  push    rdi
0x1800322c5  push    r12
0x1800322c7  push    r13
0x1800322c9  push    r14
0x1800322cb  push    r15
0x1800322cd  lea     rbp, [rsp-288h]
0x1800322d5  sub     rsp, 388h
0x1800322dc  mov     rax, cs:__security_cookie
0x1800322e3  xor     rax, rsp
0x1800322e6  mov     [rbp+2C0h+var_50], rax
0x1800322ed  mov     r13, rdx
0x1800322f0  mov     [rbp+2C0h+var_2E8], rdx
0x1800322f4  xor     r15d, r15d
0x1800322f7  mov     [rsp+3C0h+var_368], r15d
0x1800322fc  mov     [rdx], r15
0x1800322ff  mov     [rdx+8], r15
0x180032303  mov     [rdx+10h], r15
0x180032307  mov     [rsp+3C0h+var_368], 1
0x18003230f  mov     rbx, [rcx+8]
0x180032313  mov     rsi, [rcx+10h]
0x180032317  mov     r14, 7FFFFFFFFFFFFFFFh
0x180032321  cmp     rbx, rsi
0x180032324  jz      loc_180032860
0x18003232a  cmp     qword ptr [rbx+18h], 8
0x18003232f  jb      short loc_180032336
0x180032331  mov     rcx, [rbx]
0x180032334  jmp     short loc_180032339
0x180032336  mov     rcx, rbx; lpFileName
0x180032339  call    cs:__imp_GetFileAttributesW
0x180032340  nop     dword ptr [rax+rax+00h]
0x180032345  cmp     eax, 0FFFFFFFFh
0x180032348  jz      loc_1800328BF
0x18003234e  cmp     qword ptr [rbx+18h], 8
0x180032353  jb      short loc_18003235A
0x180032355  mov     rcx, [rbx]
0x180032358  jmp     short loc_18003235D
0x18003235a  mov     rcx, rbx; lpFileName
0x18003235d  call    cs:__imp_GetFileAttributesW
0x180032364  nop     dword ptr [rax+rax+00h]
0x180032369  test    al, 10h
0x18003236b  jnz     loc_1800324A3
0x180032371  cmp     qword ptr [rbx+18h], 8
0x180032376  jb      short loc_18003237D
0x180032378  mov     rcx, [rbx]
0x18003237b  jmp     short loc_180032380
0x18003237d  mov     rcx, rbx; pszPath
0x180032380  call    cs:__imp_PathFindFileNameW
0x180032387  nop     dword ptr [rax+rax+00h]
0x18003238c  mov     rdi, rax
0x18003238f  mov     rcx, [rbp+2C8h]; this
0x180032396  test    rax, rax
0x180032399  jz      loc_1800329C7
0x18003239f  mov     [rbp+2C0h+ppszExt], r15
0x1800323a3  mov     rdx, [rbx+10h]
0x1800323a7  inc     rdx; cchPath
0x1800323aa  cmp     qword ptr [rbx+18h], 8
0x1800323af  jb      short loc_1800323B6
0x1800323b1  mov     rcx, [rbx]
0x1800323b4  jmp     short loc_1800323B9
0x1800323b6  mov     rcx, rbx; pszPath
0x1800323b9  lea     r8, [rbp+2C0h+ppszExt]; ppszExt
0x1800323bd  call    cs:__imp_PathCchFindExtension
0x1800323c4  nop     dword ptr [rax+rax+00h]
0x1800323c9  mov     rcx, [rbp+2C8h]; this
0x1800323d0  test    eax, eax
0x1800323d2  js      loc_1800329B2
0x1800323d8  lea     rdx, aPpkg_0; ".ppkg"
0x1800323df  mov     rcx, [rbp+2C0h+ppszExt]; String1
0x1800323e3  call    cs:__imp__wcsicmp
0x1800323ea  nop     dword ptr [rax+rax+00h]
0x1800323ef  test    eax, eax
0x1800323f1  jnz     loc_18003291B
0x1800323f7  mov     ecx, 0A8h; Size
0x1800323fc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180032401  mov     r14, rax
0x180032404  mov     [rbp+2C0h+var_318], rax
0x180032408  test    rax, rax
0x18003240b  jz      short loc_180032489
0x18003240d  lea     rax, [rbp+2C0h+var_338]
0x180032411  mov     qword ptr [rsp+3C0h+var_378], rax
0x180032416  mov     [rbp+2C0h+var_320], 7
0x18003241e  mov     [rbp+2C0h+var_328], r15
0x180032422  mov     word ptr [rbp+2C0h+var_338], r15w
0x180032427  or      r9, 0FFFFFFFFFFFFFFFFh
0x18003242b  xor     r8d, r8d
0x18003242e  mov     rdx, rbx
0x180032431  lea     rcx, [rbp+2C0h+var_338]; void *
0x180032435  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x18003243a  nop
0x18003243b  mov     [rsp+3C0h+var_348], 7
0x180032444  mov     [rsp+3C0h+var_350], r15
0x180032449  mov     word ptr [rsp+3C0h+pszPathOut], r15w
0x18003244f  cmp     [rdi], r15w
0x180032453  jnz     short loc_18003245A
0x180032455  mov     r8, r15
0x180032458  jmp     short loc_180032468
0x18003245a  or      r8, 0FFFFFFFFFFFFFFFFh
0x18003245e  inc     r8
0x180032461  cmp     [rdi+r8*2], r15w
0x180032466  jnz     short loc_18003245E
0x180032468  mov     rdx, rdi; Src
0x18003246b  lea     rcx, [rsp+3C0h+pszPathOut]; void *
0x180032470  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180032475  nop
0x180032476  lea     r8, [rbp+2C0h+var_338]
0x18003247a  lea     rdx, [rsp+3C0h+pszPathOut]
0x18003247f  mov     rcx, r14
0x180032482  call    ??0ProvPackage@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; ProvPackage::ProvPackage(std::wstring,std::wstring)
0x180032487  jmp     short loc_18003248C
0x180032489  mov     rax, r15
0x18003248c  mov     [rsp+3C0h+var_380], rax
0x180032491  lea     rdx, [rsp+3C0h+var_380]
0x180032496  mov     rcx, r13
0x180032499  call    ??$emplace_back@PEAVProvPackage@@@?$vector@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@V?$allocator@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@@2@@std@@QEAAX$$QEAPEAVProvPackage@@@Z; std::vector<std::unique_ptr<ProvPackage>>::emplace_back<ProvPackage *>(ProvPackage * &&)
0x18003249e  jmp     loc_18003284D
0x1800324a3  mov     [rbp+2C0h+var_2C8], 7
0x1800324ab  mov     [rbp+2C0h+var_2D0], r15
0x1800324af  mov     word ptr [rbp+2C0h+pszMore], r15w
0x1800324b4  mov     r8d, 6
0x1800324ba  lea     rdx, aPpkg; "*.ppkg"
0x1800324c1  lea     rcx, [rbp+2C0h+pszMore]; void *
0x1800324c5  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x1800324ca  nop
0x1800324cb  xorps   xmm0, xmm0
0x1800324ce  movdqu  xmmword ptr [rsp+3C0h+pszPathOut], xmm0
0x1800324d4  mov     rdx, r15
0x1800324d7  mov     [rsp+3C0h+var_350], rdx
0x1800324dc  mov     r8, [rbx+10h]
0x1800324e0  mov     rax, [rbp+2C0h+var_2D0]
0x1800324e4  add     rax, 6
0x1800324e8  add     r8, rax
0x1800324eb  jz      short loc_180032508
0x1800324ed  cmp     r8, r14
0x1800324f0  ja      loc_1800329DF
0x1800324f6  mov     rdx, r8
0x1800324f9  lea     rcx, [rsp+3C0h+pszPathOut]
0x1800324fe  call    ?_Reallocate@?$vector@GV?$allocator@G@std@@@std@@IEAAX_K@Z; std::vector<ushort>::_Reallocate(unsigned __int64)
0x180032503  mov     rdx, [rsp+3C0h+var_350]
0x180032508  lea     r9, [rbp+2C0h+pszMore]
0x18003250c  cmp     [rbp+2C0h+var_2C8], 8
0x180032511  cmovnb  r9, [rbp+2C0h+pszMore]; pszMore
0x180032516  cmp     qword ptr [rbx+18h], 8
0x18003251b  jb      short loc_180032522
0x18003251d  mov     r8, [rbx]
0x180032520  jmp     short loc_180032525
0x180032522  mov     r8, rbx; pszPathIn
0x180032525  mov     r12, [rsp+3C0h+pszPathOut]
0x18003252a  sub     rdx, r12
0x18003252d  sar     rdx, 1; cchPathOut
0x180032530  mov     [rsp+3C0h+dwFlags], 1; dwFlags
0x180032538  mov     rcx, r12; pszPathOut
0x18003253b  call    cs:__imp_PathCchCombineEx
0x180032542  nop     dword ptr [rax+rax+00h]
0x180032547  mov     edi, eax
0x180032549  test    eax, eax
0x18003254b  js      loc_180032AF3
0x180032551  xor     edx, edx; Val
0x180032553  mov     r8d, 250h; Size
0x180032559  lea     rcx, [rbp+2C0h+FindFileData]; void *
0x18003255d  call    memset_0
0x180032562  lea     rdx, [rbp+2C0h+FindFileData]; lpFindFileData
0x180032566  mov     rcx, r12; lpFileName
0x180032569  call    cs:__imp_FindFirstFileW
0x180032570  nop     dword ptr [rax+rax+00h]
0x180032575  mov     rdi, rax
0x180032578  mov     [rbp+2C0h+var_310], rax
0x18003257c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180032580  jnz     short loc_1800325F6
0x180032582  call    cs:__imp_GetLastError
0x180032589  nop     dword ptr [rax+rax+00h]
0x18003258e  mov     r8d, eax
0x180032591  cmp     eax, 2
0x180032594  mov     eax, cs:dword_1800495B0
0x18003259a  jnz     loc_1800329E5
0x1800325a0  cmp     eax, 4
0x1800325a3  jbe     short loc_1800325C1
0x1800325a5  mov     [rsp+3C0h+var_380], r12
0x1800325aa  lea     rax, [rsp+3C0h+var_380]
0x1800325af  mov     qword ptr [rsp+3C0h+dwFlags], rax
0x1800325b4  lea     rdx, word_18004186A
0x1800325bb  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x1800325c0  nop
0x1800325c1  test    r12, r12
0x1800325c4  jz      short loc_1800325D6
0x1800325c6  mov     rcx, r12
0x1800325c9  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800325d0  nop     dword ptr [rax+rax+00h]
0x1800325d5  nop
0x1800325d6  cmp     [rbp+2C0h+var_2C8], 8
0x1800325db  jb      loc_180032857
0x1800325e1  mov     rcx, [rbp+2C0h+pszMore]
0x1800325e5  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800325ec  nop     dword ptr [rax+rax+00h]
0x1800325f1  jmp     loc_180032857
0x1800325f6  mov     eax, cs:dword_1800495B0
0x1800325fc  cmp     eax, 5
0x1800325ff  jbe     short loc_18003262F
0x180032601  lea     rax, [rbp+2C0h+FindFileData.cFileName]
0x180032605  mov     [rsp+3C0h+var_380], rax
0x18003260a  mov     qword ptr [rsp+3C0h+var_378], r12
0x18003260f  lea     rax, [rsp+3C0h+var_380]
0x180032614  mov     [rsp+3C0h+var_398], rax
0x180032619  lea     rax, [rsp+3C0h+var_378]
0x18003261e  mov     qword ptr [rsp+3C0h+dwFlags], rax; int
0x180032623  lea     rdx, byte_1800418D9
0x18003262a  call    ??$Write@U?$_tlgWrapSz@G@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18003262f  mov     r9d, 104h
0x180032635  lea     rax, [rbp+2C0h+FindFileData.cFileName]
0x180032639  cmp     [rax], r15w
0x18003263d  jz      short loc_180032649
0x18003263f  add     rax, 2
0x180032643  sub     r9, 1
0x180032647  jnz     short loc_180032639
0x180032649  mov     rax, r9
0x18003264c  neg     rax
0x18003264f  sbb     r10d, r10d
0x180032652  not     r10d
0x180032655  and     r10d, 80070057h
0x18003265c  mov     r8, r9
0x18003265f  mov     rax, r9
0x180032662  mov     ecx, 104h
0x180032667  sub     rcx, r9
0x18003266a  neg     rax
0x18003266d  sbb     rdx, rdx
0x180032670  and     rdx, rcx
0x180032673  neg     r8
0x180032676  sbb     r11, r11
0x180032679  and     r11, rdx
0x18003267c  mov     rcx, [rbp+2C8h]; this
0x180032683  test    r9, r9
0x180032686  jz      loc_180032ADE
0x18003268c  xorps   xmm0, xmm0
0x18003268f  movdqu  xmmword ptr [rbp+2C0h+var_338], xmm0
0x180032694  mov     rcx, r15
0x180032697  mov     [rbp+2C0h+var_328], rcx
0x18003269b  mov     rdx, [rbx+10h]
0x18003269f  add     rdx, 6
0x1800326a3  add     rdx, r11
0x1800326a6  jz      short loc_1800326BE
0x1800326a8  cmp     rdx, r14
0x1800326ab  ja      loc_180032A4C
0x1800326b1  lea     rcx, [rbp+2C0h+var_338]
0x1800326b5  call    ?_Reallocate@?$vector@GV?$allocator@G@std@@@std@@IEAAX_K@Z; std::vector<ushort>::_Reallocate(unsigned __int64)
0x1800326ba  mov     rcx, [rbp+2C0h+var_328]
0x1800326be  cmp     qword ptr [rbx+18h], 8
0x1800326c3  jb      short loc_1800326CA
0x1800326c5  mov     r8, [rbx]
0x1800326c8  jmp     short loc_1800326CD
0x1800326ca  mov     r8, rbx; pszPathIn
0x1800326cd  mov     r15, [rbp+2C0h+var_338]
0x1800326d1  sub     rcx, r15
0x1800326d4  sar     rcx, 1
0x1800326d7  mov     [rsp+3C0h+dwFlags], 1; dwFlags
0x1800326df  lea     r9, [rbp+2C0h+FindFileData.cFileName]; pszMore
0x1800326e3  mov     rdx, rcx; cchPathOut
0x1800326e6  mov     rcx, r15; pszPathOut
0x1800326e9  call    cs:__imp_PathCchCombineEx
0x1800326f0  nop     dword ptr [rax+rax+00h]
0x1800326f5  mov     r14d, eax
0x1800326f8  test    eax, eax
0x1800326fa  js      loc_180032A52
0x180032700  mov     ecx, 0A8h; Size
0x180032705  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003270a  mov     r14, rax
0x18003270d  mov     [rsp+3C0h+var_370], rax
0x180032712  xor     edx, edx
0x180032714  test    rax, rax
0x180032717  jz      loc_1800327BA
0x18003271d  lea     rax, [rbp+2C0h+var_308]
0x180032721  mov     qword ptr [rsp+3C0h+var_378], rax
0x180032726  mov     [rbp+2C0h+var_2F0], 7
0x18003272e  mov     [rbp+2C0h+var_2F8], rdx
0x180032732  mov     [rbp+2C0h+var_308], dx
0x180032736  cmp     [r15], dx
0x18003273a  jnz     short loc_180032741
0x18003273c  mov     r8d, edx
0x18003273f  jmp     short loc_18003274F
0x180032741  or      r8, 0FFFFFFFFFFFFFFFFh
0x180032745  inc     r8
0x180032748  cmp     [r15+r8*2], dx
0x18003274d  jnz     short loc_180032745
0x18003274f  mov     rdx, r15; Src
0x180032752  lea     rcx, [rbp+2C0h+var_308]; void *
0x180032756  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18003275b  nop
0x18003275c  mov     [rbp+2C0h+var_58], 7
0x180032767  xor     ecx, ecx
0x180032769  mov     [rbp+2C0h+var_60], rcx
0x180032770  mov     [rbp+2C0h+var_70], cx
0x180032777  cmp     [rbp+2C0h+FindFileData.cFileName], cx
0x18003277b  jnz     short loc_180032782
0x18003277d  mov     r8d, ecx
0x180032780  jmp     short loc_180032794
0x180032782  lea     rax, [rbp+2C0h+FindFileData.cFileName]
0x180032786  or      r8, 0FFFFFFFFFFFFFFFFh
0x18003278a  inc     r8
0x18003278d  cmp     [rax+r8*2], cx
  ... truncated ...
```
