# PackageCollector::Search(void)

- ea: `0x1800296a0`
- end: `0x180029f02`
- name: `?Search@PackageCollector@@QEAA?AV?$vector@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@V?$allocator@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@@2@@std@@XZ`
- size: `2146`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `3`
- callee_count: `22`
- tags: `file_ops, reparse_path, loader_planting, broker_com_uri`

## callers

- `0x18000f8d0`
- `0x180015f60`
- `0x180016840`

## callees

- `0x1800015b4`
- `0x18000164c`
- `0x180001678`
- `0x1800017ec`
- `0x180001878`
- `0x180002300`
- `0x180002614`
- `0x180002f44`
- `0x180004d68`
- `0x18001b388`
- `0x1800202e4`
- `0x180020710`
- `0x180020bc8`
- `0x180020fe0`
- `0x1800210f0`
- `0x180021200`
- `0x180021214`
- `0x180026068`
- `0x1800296a0`
- `0x18002e030`
- `0x180033e9a`
- `0x180033ed0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180029a46`
- `msvcrt!??3@YAXPEAX@Z` at `0x180029a85`
- `msvcrt!??3@YAXPEAX@Z` at `0x180029a97`
- `msvcrt!??3@YAXPEAX@Z` at `0x180029a46`
- `msvcrt!??3@YAXPEAX@Z` at `0x180029a85`
- `msvcrt!??3@YAXPEAX@Z` at `0x180029a97`
- `msvcrt!_wcsicmp` at `0x180029b1e`
- `msvcrt!_wcsicmp` at `0x180029b1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029814`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029814`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18002971e`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18002973c`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18002971e`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18002973c`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180029a53`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180029a53`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180029a76`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180029a76`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180029801`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180029801`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180029ac4`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180029ac4`
- `api-ms-win-core-path-l1-1-0!PathCchCombineEx` at `0x1800297d9`
- `api-ms-win-core-path-l1-1-0!PathCchCombineEx` at `0x18002994e`
- `api-ms-win-core-path-l1-1-0!PathCchCombineEx` at `0x1800297d9`
- `api-ms-win-core-path-l1-1-0!PathCchCombineEx` at `0x18002994e`
- `api-ms-win-core-path-l1-1-0!PathCchFindExtension` at `0x180029afd`
- `api-ms-win-core-path-l1-1-0!PathCchFindExtension` at `0x180029afd`

## pseudocode

```c
// Hidden C++ exception states: #wind=58
_QWORD *__fastcall PackageCollector::Search(__int64 a1, _QWORD *a2)
{
  __int64 v3; // rbx
  __int64 v4; // rsi
  const WCHAR *v5; // rcx
  const WCHAR *v6; // rcx
  __int64 v7; // rdx
  unsigned __int64 v8; // r8
  const WCHAR *v9; // r9
  const WCHAR *v10; // r8
  WCHAR *v11; // r13
  HRESULT v12; // edi
  _WORD *FirstFileW; // rdi
  int v14; // r8d
  int v15; // r9d
  int v16; // r9d
  __int64 v17; // r9
  WCHAR *v18; // rax
  __int64 v19; // rcx
  unsigned __int64 v20; // rdx
  const WCHAR *v21; // r8
  PWSTR v22; // r12
  HRESULT v23; // r14d
  void *v24; // r14
  __int64 v25; // r8
  __int64 v26; // r8
  __int64 v27; // r14
  const WCHAR *v28; // rcx
  LPWSTR FileNameW; // rdi
  const WCHAR *v30; // rcx
  HRESULT Extension; // eax
  void *v32; // r14
  __int64 v33; // r8
  __int64 v34; // rdi
  const char *v36; // r9
  __int64 v37; // rax
  __int64 v38; // rax
  int v39; // r9d
  const char *v40; // r9
  int v41; // r8d
  __int64 v42; // rax
  __int64 v43; // rax
  int v44; // r9d
  __int64 v45; // rax
  __int64 v46; // rax
  __int64 v47; // r8
  int v48; // r9d
  unsigned int v49; // eax
  __int64 v50; // rax
  __int64 v51; // rax
  int v52; // r9d
  unsigned int v53; // eax
  __int64 v54; // rax
  __int64 v55; // rax
  __int64 v56; // r8
  int v57; // r9d
  unsigned int v58; // eax
  int dwFlags; // [rsp+20h] [rbp-E0h]
  WCHAR *cFileName; // [rsp+40h] [rbp-C0h] BYREF
  void *v61; // [rsp+48h] [rbp-B8h] BYREF
  int v62; // [rsp+50h] [rbp-B0h]
  int v63[2]; // [rsp+58h] [rbp-A8h] BYREF
  PCWSTR ppszExt; // [rsp+60h] [rbp-A0h] BYREF
  void *v65; // [rsp+68h] [rbp-98h] BYREF
  PWSTR pszPathOut[2]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v67; // [rsp+80h] [rbp-80h]
  _WORD *v68; // [rsp+88h] [rbp-78h]
  PWSTR v69[2]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v70; // [rsp+A0h] [rbp-60h]
  _WORD v71[8]; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v72; // [rsp+B8h] [rbp-48h]
  __int64 v73; // [rsp+C0h] [rbp-40h]
  _WORD v74[8]; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v75; // [rsp+D8h] [rbp-28h]
  __int64 v76; // [rsp+E0h] [rbp-20h]
  _WORD v77[8]; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v78; // [rsp+F8h] [rbp-8h]
  __int64 v79; // [rsp+100h] [rbp+0h]
  _QWORD *v80; // [rsp+108h] [rbp+8h]
  PCWSTR pszMore[2]; // [rsp+110h] [rbp+10h] BYREF
  __int64 v82; // [rsp+120h] [rbp+20h]
  unsigned __int64 v83; // [rsp+128h] [rbp+28h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+130h] [rbp+30h] BYREF
  _WORD v85[8]; // [rsp+380h] [rbp+280h] BYREF
  __int64 v86; // [rsp+390h] [rbp+290h]
  __int64 v87; // [rsp+398h] [rbp+298h]
  wil::details::in1diag3 *retaddr; // [rsp+3F8h] [rbp+2F8h]

  v80 = a2;
  *a2 = 0;
  a2[1] = 0;
  a2[2] = 0;
  v62 = 1;
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
      v36 = (const char *)g_hProvTraceProvider;
      if ( *(_DWORD *)g_hProvTraceProvider > 2u && (unsigned __int8)tlgKeywordOn(g_hProvTraceProvider, 0) )
      {
        v37 = std::wstring::c_str(v3);
        v38 = _tlgTypeMapBase<unsigned short *,void>::_tlgWrapAuto(&v61, v37);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          v39,
          (unsigned int)qword_180041388,
          0,
          v39,
          v38);
      }
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0xC3,
        (unsigned int)"onecoreuap\\admin\\prov\\lib\\packagecollector.cpp",
        v36);
    }
    if ( *(_QWORD *)(v3 + 24) < 8u )
      v6 = (const WCHAR *)v3;
    else
      v6 = *(const WCHAR **)v3;
    if ( (GetFileAttributesW(v6) & 0x10) != 0 )
    {
      v83 = 7;
      v82 = 0;
      LOWORD(pszMore[0]) = 0;
      std::wstring::assign(pszMore, L"*.ppkg");
      *(_OWORD *)pszPathOut = 0;
      v7 = 0;
      v67 = 0;
      v8 = *(_QWORD *)(v3 + 16) + v82 + 6;
      if ( v8 )
      {
        if ( v8 > 0x7FFFFFFFFFFFFFFFLL )
          ((void (__noreturn *)(void))std::vector<std::unique_ptr<ProvPackage>>::_Xlen)();
        std::vector<unsigned short>::_Reallocate(pszPathOut, *(_QWORD *)(v3 + 16) + v82 + 6);
        v7 = v67;
      }
      v9 = (const WCHAR *)pszMore;
      if ( v83 >= 8 )
        v9 = pszMore[0];
      if ( *(_QWORD *)(v3 + 24) < 8u )
        v10 = (const WCHAR *)v3;
      else
        v10 = *(const WCHAR **)v3;
      v11 = pszPathOut[0];
      v12 = PathCchCombineEx(pszPathOut[0], (signed __int64)(v7 - (unsigned __int64)pszPathOut[0]) >> 1, v10, v9, 1u);
      if ( v12 < 0 )
      {
        if ( *(_DWORD *)g_hProvTraceProvider > 2u && (unsigned __int8)tlgKeywordOn(g_hProvTraceProvider, 0) )
        {
          LODWORD(cFileName) = v12;
          v50 = std::vector<unsigned short>::data(pszPathOut);
          v51 = _tlgTypeMapBase<unsigned short *,void>::_tlgWrapAuto(&v61, v50);
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
            v52,
            (unsigned int)&byte_18004130F,
            0,
            v52,
            v51,
            (__int64)&cFileName);
        }
        v53 = wil::verify_hresult<long>((unsigned int)v12);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xE6,
          (unsigned int)"onecoreuap\\admin\\prov\\lib\\packagecollector.cpp",
          (const char *)v53,
          dwFlags);
      }
      memset_0(&FindFileData, 0, sizeof(FindFileData));
      FirstFileW = FindFirstFileW(v11, &FindFileData);
      v68 = FirstFileW;
      if ( FirstFileW == (_WORD *)-1LL )
      {
        if ( GetLastError() != 2 )
        {
          v40 = (const char *)g_hProvTraceProvider;
          if ( *(_DWORD *)g_hProvTraceProvider > 2u && (unsigned __int8)tlgKeywordOn(g_hProvTraceProvider, 0) )
          {
            LODWORD(cFileName) = v41;
            v42 = std::vector<unsigned short>::data(pszPathOut);
            v43 = _tlgTypeMapBase<unsigned short *,void>::_tlgWrapAuto(&v61, v42);
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
              v44,
              (unsigned int)byte_1800412A3,
              0,
              v44,
              v43,
              (__int64)&cFileName);
          }
          wil::details::in1diag3::Throw_GetLastError(
            retaddr,
            (void *)0xF9,
            (unsigned int)"onecoreuap\\admin\\prov\\lib\\packagecollector.cpp",
            v40);
        }
        if ( *(_DWORD *)g_hProvTraceProvider > 4u )
        {
          cFileName = v11;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
            g_hProvTraceProvider,
            (unsigned int)byte_1800412DD,
            0,
            v16,
            (__int64)&cFileName);
        }
      }
      else
      {
        do
        {
          if ( *(_DWORD *)g_hProvTraceProvider > 5u )
          {
            cFileName = FindFileData.cFileName;
            *(_QWORD *)v63 = v11;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
              g_hProvTraceProvider,
              (unsigned int)&byte_180041267,
              v14,
              v15,
              (__int64)v63,
              (__int64)&cFileName);
          }
          v17 = 260;
          v18 = FindFileData.cFileName;
          do
          {
            if ( !*v18 )
              break;
            ++v18;
            --v17;
          }
          while ( v17 );
          if ( !v17 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x104,
              (unsigned int)"onecoreuap\\admin\\prov\\lib\\packagecollector.cpp",
              (const char *)0x80070057LL,
              dwFlags);
          *(_OWORD *)v69 = 0;
          v19 = 0;
          v70 = 0;
          v20 = ((260 - v17) & ((unsigned __int128)-(__int128)(unsigned __int64)v17 >> 64) & -(__int64)(v17 != 0))
              + *(_QWORD *)(v3 + 16)
              + 6LL;
          if ( v20 )
          {
            if ( v20 > 0x7FFFFFFFFFFFFFFFLL )
              std::vector<std::unique_ptr<ProvPackage>>::_Xlen(0, v20, -v17);
            std::vector<unsigned short>::_Reallocate(v69, v20);
            v19 = v70;
          }
          if ( *(_QWORD *)(v3 + 24) < 8u )
            v21 = (const WCHAR *)v3;
          else
            v21 = *(const WCHAR **)v3;
          v22 = v69[0];
          v23 = PathCchCombineEx(
                  v69[0],
                  (signed __int64)(v19 - (unsigned __int64)v69[0]) >> 1,
                  v21,
                  FindFileData.cFileName,
                  1u);
          if ( v23 < 0 )
          {
            if ( *(_DWORD *)g_hProvTraceProvider > 2u && (unsigned __int8)tlgKeywordOn(g_hProvTraceProvider, 0) )
            {
              LODWORD(cFileName) = v23;
              _tlgTypeMapBase<unsigned short *,void>::_tlgWrapAuto(&v61, FindFileData.cFileName);
              v45 = std::vector<unsigned short>::data(v69);
              v46 = _tlgTypeMapBase<unsigned short *,void>::_tlgWrapAuto(&v65, v45);
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
                v48,
                (unsigned int)&unk_180041218,
                v47,
                v48,
                v46,
                v47,
                (__int64)&cFileName);
            }
            v49 = wil::verify_hresult<long>((unsigned int)v23);
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x113,
              (unsigned int)"onecoreuap\\admin\\prov\\lib\\packagecollector.cpp",
              (const char *)v49,
              dwFlags);
          }
          v24 = operator new(0xA8u);
          v65 = v24;
          if ( v24 )
          {
            *(_QWORD *)v63 = v71;
            v73 = 7;
            v72 = 0;
            v71[0] = 0;
            if ( *v22 )
            {
              v25 = -1;
              do
                ++v25;
              while ( v22[v25] );
            }
            std::wstring::assign(v71, v22);
            v87 = 7;
            v86 = 0;
            v85[0] = 0;
            if ( FindFileData.cFileName[0] )
            {
              v26 = -1;
              do
                ++v26;
              while ( FindFileData.cFileName[v26] );
            }
            std::wstring::assign(v85, FindFileData.cFileName);
            v27 = ProvPackage::ProvPackage(v24, v85, v71);
          }
          else
          {
            v27 = 0;
          }
          if ( a2[1] == a2[2] )
            std::vector<std::unique_ptr<ProvPackage>>::_Reserve(a2);
          *(_QWORD *)a2[1] = v27;
          a2[1] += 8LL;
          if ( v22 )
            operator delete(v22);
        }
        while ( FindNextFileW(FirstFileW, &FindFileData) );
        if ( FirstFileW )
          FindClose(FirstFileW);
      }
      if ( v11 )
        operator delete(v11);
      if ( v83 >= 8 )
        operator delete((void *)pszMore[0]);
      v83 = 7;
      v82 = 0;
      LOWORD(pszMore[0]) = 0;
    }
    else
    {
      if ( *(_QWORD *)(v3 + 24) < 8u )
        v28 = (const WCHAR *)v3;
      else
        v28 = *(const WCHAR **)v3;
      FileNameW = PathFindFileNameW(v28);
      if ( !FileNameW )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xC9,
          (unsigned int)"onecoreuap\\admin\\prov\\lib\\packagecollector.cpp",
          (const char *)0x80070057LL,
          dwFlags);
      ppszExt = 0;
      if ( *(_QWORD *)(v3 + 24) < 8u )
        v30 = (const WCHAR *)v3;
      else
        v30 = *(const WCHAR **)v3;
      Extension = PathCchFindExtension(v30, *(_QWORD *)(v3 + 16) + 1LL, &ppszExt);
      if ( Extension < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xCC,
          (unsigned int)"onecoreuap\\admin\\prov\\lib\\packagecollector.cpp",
          (const char *)(unsigned int)Extension,
          dwFlags);
      if ( _wcsicmp(ppszExt, L".ppkg") )
      {
        if ( *(_DWORD *)g_hProvTraceProvider > 2u
          && (unsigned __int8)tlgKeywordOn(g_hProvTraceProvider, 0x400000000000LL) )
        {
          LODWORD(cFileName) = -2147024809;
          _tlgTypeMapBase<unsigned short *,void>::_tlgWrapAuto(&v61, FileNameW);
          v54 = std::wstring::c_str(v3);
          v55 = _tlgTypeMapBase<unsigned short *,void>::_tlgWrapAuto(&v65, v54);
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
            v57,
            (unsigned int)&dword_18004134C,
            v56,
            v57,
            v55,
            v56,
            (__int64)&cFileName);
        }
        v58 = wil::verify_hresult<long>(2147942487LL);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xD3,
          (unsigned int)"onecoreuap\\admin\\prov\\lib\\packagecollector.cpp",
          (const char *)v58,
          dwFlags);
      }
      v32 = operator new(0xA8u);
      v61 = v32;
      if ( v32 )
      {
        v68 = v74;
        v76 = 7;
        v75 = 0;
        v74[0] = 0;
        std::wstring::assign(v74);
        v79 = 7;
        v78 = 0;
        v77[0] = 0;
        if ( *FileNameW )
        {
          v33 = -1;
          do
            ++v33;
          while ( FileNameW[v33] );
        }
        std::wstring::assign(v77, FileNameW);
        v34 = ProvPackage::ProvPackage(v32, v77, v74);
      }
      else
      {
        v34 = 0;
      }
      if ( a2[1] == a2[2] )
        std::vector<std::unique_ptr<ProvPackage>>::_Reserve(a2);
      *(_QWORD *)a2[1] = v34;
      a2[1] += 8LL;
    }
    v3 += 32;
  }
  if ( *(_DWORD *)g_hProvTraceProvider > 5u )
    tlgWriteTransfer_EventWriteTransfer(g_hProvTraceProvider, &word_1800411EE, 0, 0);
  return a2;
}

```

## disassembly

```asm
0x1800296a0  push    rbp
0x1800296a2  push    rbx
0x1800296a3  push    rsi
0x1800296a4  push    rdi
0x1800296a5  push    r12
0x1800296a7  push    r13
0x1800296a9  push    r14
0x1800296ab  push    r15
0x1800296ad  lea     rbp, [rsp-2B8h]
0x1800296b5  sub     rsp, 3B8h
0x1800296bc  mov     rax, cs:__security_cookie
0x1800296c3  xor     rax, rsp
0x1800296c6  mov     [rbp+2F0h+var_50], rax
0x1800296cd  mov     r15, rdx
0x1800296d0  mov     [rbp+2F0h+var_2E8], rdx
0x1800296d4  xor     r12d, r12d
0x1800296d7  mov     [rsp+3F0h+var_3A0], r12d
0x1800296dc  mov     [rdx], r12
0x1800296df  mov     [rdx+8], r12
0x1800296e3  mov     [rdx+10h], r12
0x1800296e7  mov     [rsp+3F0h+var_3A0], 1
0x1800296ef  mov     rbx, [rcx+8]
0x1800296f3  mov     rsi, [rcx+10h]
0x1800296f7  lea     r13d, [r12+7]
0x1800296fc  mov     r14, 7FFFFFFFFFFFFFFFh
0x180029706  cmp     rbx, rsi
0x180029709  jz      loc_180029BDE
0x18002970f  cmp     qword ptr [rbx+18h], 8
0x180029714  jb      short loc_18002971B
0x180029716  mov     rcx, [rbx]
0x180029719  jmp     short loc_18002971E
0x18002971b  mov     rcx, rbx; lpFileName
0x18002971e  call    cs:__imp_GetFileAttributesW
0x180029724  cmp     eax, 0FFFFFFFFh
0x180029727  jz      loc_180029C38
0x18002972d  cmp     qword ptr [rbx+18h], 8
0x180029732  jb      short loc_180029739
0x180029734  mov     rcx, [rbx]
0x180029737  jmp     short loc_18002973C
0x180029739  mov     rcx, rbx; lpFileName
0x18002973c  call    cs:__imp_GetFileAttributesW
0x180029742  test    al, 10h
0x180029744  jz      loc_180029AB5
0x18002974a  mov     [rbp+2F0h+var_2C8], r13
0x18002974e  mov     [rbp+2F0h+var_2D0], r12
0x180029752  mov     word ptr [rbp+2F0h+pszMore], r12w
0x180029757  mov     r8d, 6
0x18002975d  lea     rdx, aPpkg; "*.ppkg"
0x180029764  lea     rcx, [rbp+2F0h+pszMore]; void *
0x180029768  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18002976d  nop
0x18002976e  xorps   xmm0, xmm0
0x180029771  movdqu  xmmword ptr [rsp+3F0h+pszPathOut], xmm0
0x180029777  mov     rdx, r12
0x18002977a  mov     [rbp+2F0h+var_370], rdx
0x18002977e  mov     r8, [rbp+2F0h+var_2D0]
0x180029782  add     r8, 6
0x180029786  add     r8, [rbx+10h]
0x18002978a  jz      short loc_1800297A6
0x18002978c  cmp     r8, r14
0x18002978f  ja      loc_180029C9A
0x180029795  mov     rdx, r8
0x180029798  lea     rcx, [rsp+3F0h+pszPathOut]
0x18002979d  call    ?_Reallocate@?$vector@GV?$allocator@G@std@@@std@@IEAAX_K@Z; std::vector<ushort>::_Reallocate(unsigned __int64)
0x1800297a2  mov     rdx, [rbp+2F0h+var_370]
0x1800297a6  lea     r9, [rbp+2F0h+pszMore]
0x1800297aa  cmp     [rbp+2F0h+var_2C8], 8
0x1800297af  cmovnb  r9, [rbp+2F0h+pszMore]; pszMore
0x1800297b4  cmp     qword ptr [rbx+18h], 8
0x1800297b9  jb      short loc_1800297C0
0x1800297bb  mov     r8, [rbx]
0x1800297be  jmp     short loc_1800297C3
0x1800297c0  mov     r8, rbx; pszPathIn
0x1800297c3  mov     r13, [rsp+3F0h+pszPathOut]
0x1800297c8  sub     rdx, r13
0x1800297cb  sar     rdx, 1; cchPathOut
0x1800297ce  mov     [rsp+3F0h+dwFlags], 1; dwFlags
0x1800297d6  mov     rcx, r13; pszPathOut
0x1800297d9  call    cs:__imp_PathCchCombineEx
0x1800297df  mov     edi, eax
0x1800297e1  test    eax, eax
0x1800297e3  js      loc_180029DBE
0x1800297e9  xor     edx, edx; Val
0x1800297eb  mov     r8d, 250h; Size
0x1800297f1  lea     rcx, [rbp+2F0h+FindFileData]; void *
0x1800297f5  call    memset_0
0x1800297fa  lea     rdx, [rbp+2F0h+FindFileData]; lpFindFileData
0x1800297fe  mov     rcx, r13; lpFileName
0x180029801  call    cs:__imp_FindFirstFileW
0x180029807  mov     rdi, rax
0x18002980a  mov     [rbp+2F0h+var_368], rax
0x18002980e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180029812  jnz     short loc_180029858
0x180029814  call    cs:__imp_GetLastError
0x18002981a  mov     r8d, eax
0x18002981d  cmp     eax, 2
0x180029820  jnz     loc_180029CA0
0x180029826  mov     rcx, cs:g_hProvTraceProvider
0x18002982d  mov     eax, [rcx]
0x18002982f  cmp     eax, 4
0x180029832  jbe     short loc_180029853
0x180029834  mov     [rsp+3F0h+var_3B0], r13
0x180029839  lea     rax, [rsp+3F0h+var_3B0]
0x18002983e  mov     qword ptr [rsp+3F0h+dwFlags], rax
0x180029843  xor     r8d, r8d
0x180029846  lea     rdx, byte_1800412DD
0x18002984d  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x180029852  nop
0x180029853  jmp     loc_180029A7D
0x180029858  mov     rcx, cs:g_hProvTraceProvider
0x18002985f  mov     eax, [rcx]
0x180029861  cmp     eax, 5
0x180029864  jbe     short loc_180029894
0x180029866  lea     rax, [rbp+2F0h+FindFileData.cFileName]
0x18002986a  mov     [rsp+3F0h+var_3B0], rax
0x18002986f  mov     qword ptr [rsp+3F0h+var_398], r13
0x180029874  lea     rax, [rsp+3F0h+var_3B0]
0x180029879  mov     [rsp+3F0h+var_3C8], rax
0x18002987e  lea     rax, [rsp+3F0h+var_398]
0x180029883  mov     qword ptr [rsp+3F0h+dwFlags], rax; int
0x180029888  lea     rdx, byte_180041267
0x18002988f  call    ??$Write@U?$_tlgWrapSz@G@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180029894  mov     r9d, 104h
0x18002989a  lea     rax, [rbp+2F0h+FindFileData.cFileName]
0x18002989e  cmp     [rax], r12w
0x1800298a2  jz      short loc_1800298AE
0x1800298a4  add     rax, 2
0x1800298a8  sub     r9, 1
0x1800298ac  jnz     short loc_18002989E
0x1800298ae  mov     rax, r9
0x1800298b1  neg     rax
0x1800298b4  sbb     r10d, r10d
0x1800298b7  not     r10d
0x1800298ba  and     r10d, 80070057h
0x1800298c1  mov     r8, r9
0x1800298c4  mov     rax, r9
0x1800298c7  mov     ecx, 104h
0x1800298cc  sub     rcx, r9
0x1800298cf  neg     rax
0x1800298d2  sbb     rdx, rdx
0x1800298d5  and     rdx, rcx
0x1800298d8  neg     r8
0x1800298db  sbb     r11, r11
0x1800298de  and     r11, rdx
0x1800298e1  mov     rcx, [rbp+2F8h]; this
0x1800298e8  test    r9, r9
0x1800298eb  jz      loc_180029DA9
0x1800298f1  xorps   xmm0, xmm0
0x1800298f4  movdqu  xmmword ptr [rbp+2F0h+var_360], xmm0
0x1800298f9  mov     rcx, r12
0x1800298fc  mov     [rbp+2F0h+var_350], rcx
0x180029900  mov     rdx, [rbx+10h]
0x180029904  add     rdx, 6
0x180029908  add     rdx, r11
0x18002990b  jz      short loc_180029923
0x18002990d  cmp     rdx, r14
0x180029910  ja      loc_180029D13
0x180029916  lea     rcx, [rbp+2F0h+var_360]
0x18002991a  call    ?_Reallocate@?$vector@GV?$allocator@G@std@@@std@@IEAAX_K@Z; std::vector<ushort>::_Reallocate(unsigned __int64)
0x18002991f  mov     rcx, [rbp+2F0h+var_350]
0x180029923  cmp     qword ptr [rbx+18h], 8
0x180029928  jb      short loc_18002992F
0x18002992a  mov     r8, [rbx]
0x18002992d  jmp     short loc_180029932
0x18002992f  mov     r8, rbx; pszPathIn
0x180029932  mov     r12, [rbp+2F0h+var_360]
0x180029936  sub     rcx, r12
0x180029939  sar     rcx, 1
0x18002993c  mov     [rsp+3F0h+dwFlags], 1; dwFlags
0x180029944  lea     r9, [rbp+2F0h+FindFileData.cFileName]; pszMore
0x180029948  mov     rdx, rcx; cchPathOut
0x18002994b  mov     rcx, r12; pszPathOut
0x18002994e  call    cs:__imp_PathCchCombineEx
0x180029954  mov     r14d, eax
0x180029957  test    eax, eax
0x180029959  js      loc_180029D19
0x18002995f  mov     ecx, 0A8h; Size
0x180029964  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180029969  mov     r14, rax
0x18002996c  mov     [rsp+3F0h+var_388], rax
0x180029971  xor     edx, edx
0x180029973  test    rax, rax
0x180029976  jz      loc_180029A1D
0x18002997c  lea     rax, [rbp+2F0h+var_348]
0x180029980  mov     qword ptr [rsp+3F0h+var_398], rax
0x180029985  mov     [rbp+2F0h+var_330], 7
0x18002998d  mov     [rbp+2F0h+var_338], rdx
0x180029991  mov     [rbp+2F0h+var_348], dx
0x180029995  cmp     [r12], dx
0x18002999a  jnz     short loc_1800299A1
0x18002999c  mov     r8d, edx
0x18002999f  jmp     short loc_1800299AF
0x1800299a1  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800299a5  inc     r8
0x1800299a8  cmp     [r12+r8*2], dx
0x1800299ad  jnz     short loc_1800299A5
0x1800299af  mov     rdx, r12; Src
0x1800299b2  lea     rcx, [rbp+2F0h+var_348]; void *
0x1800299b6  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x1800299bb  nop
0x1800299bc  mov     [rbp+2F0h+var_58], 7
0x1800299c7  xor     ecx, ecx
0x1800299c9  mov     [rbp+2F0h+var_60], rcx
0x1800299d0  mov     [rbp+2F0h+var_70], cx
0x1800299d7  cmp     [rbp+2F0h+FindFileData.cFileName], cx
0x1800299db  jnz     short loc_1800299E2
0x1800299dd  mov     r8d, ecx
0x1800299e0  jmp     short loc_1800299F4
0x1800299e2  lea     rax, [rbp+2F0h+FindFileData.cFileName]
0x1800299e6  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800299ea  inc     r8
0x1800299ed  cmp     [rax+r8*2], cx
0x1800299f2  jnz     short loc_1800299EA
0x1800299f4  lea     rdx, [rbp+2F0h+FindFileData.cFileName]; Src
0x1800299f8  lea     rcx, [rbp+2F0h+var_70]; void *
0x1800299ff  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180029a04  nop
0x180029a05  lea     r8, [rbp+2F0h+var_348]
0x180029a09  lea     rdx, [rbp+2F0h+var_70]
0x180029a10  mov     rcx, r14
0x180029a13  call    ??0ProvPackage@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; ProvPackage::ProvPackage(std::wstring,std::wstring)
0x180029a18  mov     r14, rax
0x180029a1b  jmp     short loc_180029A20
0x180029a1d  mov     r14, rdx
0x180029a20  mov     rax, [r15+10h]
0x180029a24  cmp     [r15+8], rax
0x180029a28  jnz     short loc_180029A32
0x180029a2a  mov     rcx, r15
0x180029a2d  call    ?_Reserve@?$vector@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@V?$allocator@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@@2@@std@@IEAAX_K@Z; std::vector<std::unique_ptr<ProvPackage>>::_Reserve(unsigned __int64)
0x180029a32  mov     rax, [r15+8]
0x180029a36  mov     [rax], r14
0x180029a39  add     qword ptr [r15+8], 8
0x180029a3e  test    r12, r12
0x180029a41  jz      short loc_180029A4C
0x180029a43  mov     rcx, r12
0x180029a46  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180029a4c  lea     rdx, [rbp+2F0h+FindFileData]; lpFindFileData
0x180029a50  mov     rcx, rdi; hFindFile
0x180029a53  call    cs:__imp_FindNextFileW
0x180029a59  xor     r12d, r12d
0x180029a5c  test    eax, eax
0x180029a5e  mov     r14, 7FFFFFFFFFFFFFFFh
0x180029a68  jnz     loc_180029858
0x180029a6e  test    rdi, rdi
0x180029a71  jz      short loc_180029A7D
0x180029a73  mov     rcx, rdi; hFindFile
0x180029a76  call    cs:__imp_FindClose
0x180029a7c  nop
0x180029a7d  test    r13, r13
0x180029a80  jz      short loc_180029A8C
0x180029a82  mov     rcx, r13
0x180029a85  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180029a8b  nop
0x180029a8c  cmp     [rbp+2F0h+var_2C8], 8
0x180029a91  jb      short loc_180029A9D
0x180029a93  mov     rcx, [rbp+2F0h+pszMore]
0x180029a97  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180029a9d  mov     r13d, 7
0x180029aa3  mov     [rbp+2F0h+var_2C8], r13
0x180029aa7  mov     [rbp+2F0h+var_2D0], r12
0x180029aab  mov     word ptr [rbp+2F0h+pszMore], r12w
0x180029ab0  jmp     loc_180029BD5
0x180029ab5  cmp     qword ptr [rbx+18h], 8
0x180029aba  jb      short loc_180029AC1
0x180029abc  mov     rcx, [rbx]
0x180029abf  jmp     short loc_180029AC4
0x180029ac1  mov     rcx, rbx; pszPath
0x180029ac4  call    cs:__imp_PathFindFileNameW
0x180029aca  mov     rdi, rax
0x180029acd  mov     rcx, [rbp+2F8h]; this
0x180029ad4  test    rax, rax
0x180029ad7  jz      loc_180029EEA
0x180029add  mov     [rsp+3F0h+ppszExt], r12
0x180029ae2  mov     rdx, [rbx+10h]
0x180029ae6  inc     rdx; cchPath
0x180029ae9  cmp     qword ptr [rbx+18h], 8
0x180029aee  jb      short loc_180029AF5
0x180029af0  mov     rcx, [rbx]
0x180029af3  jmp     short loc_180029AF8
0x180029af5  mov     rcx, rbx; pszPath
0x180029af8  lea     r8, [rsp+3F0h+ppszExt]; ppszExt
0x180029afd  call    cs:__imp_PathCchFindExtension
0x180029b03  mov     rcx, [rbp+2F8h]; this
0x180029b0a  test    eax, eax
0x180029b0c  js      loc_180029ED5
0x180029b12  lea     rdx, aPpkg_0; ".ppkg"
0x180029b19  mov     rcx, [rsp+3F0h+ppszExt]; String1
0x180029b1e  call    cs:__imp__wcsicmp
0x180029b24  test    eax, eax
0x180029b26  jnz     loc_180029E3A
0x180029b2c  mov     ecx, 0A8h; Size
0x180029b31  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180029b36  mov     r14, rax
0x180029b39  mov     [rsp+3F0h+var_3A8], rax
0x180029b3e  test    rax, rax
0x180029b41  jz      short loc_180029BB4
0x180029b43  lea     rax, [rbp+2F0h+var_328]
0x180029b47  mov     [rbp+2F0h+var_368], rax
0x180029b4b  mov     [rbp+2F0h+var_310], r13
0x180029b4f  mov     [rbp+2F0h+var_318], r12
  ... truncated ...
```
