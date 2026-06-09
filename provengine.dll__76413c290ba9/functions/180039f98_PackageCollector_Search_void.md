# PackageCollector::Search(void)

- ea: `0x180039f98`
- end: `0x18003a823`
- name: `?Search@PackageCollector@@QEAA?AV?$vector@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@V?$allocator@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@@2@@std@@XZ`
- size: `2187`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `2`
- callee_count: `22`
- tags: `file_ops, reparse_path, loader_planting, broker_com_uri`

## callers

- `0x1800141f0`
- `0x180014810`

## callees

- `0x180001008`
- `0x18000109c`
- `0x1800010c8`
- `0x1800011ac`
- `0x1800017f4`
- `0x1800018ec`
- `0x180001a14`
- `0x1800021b4`
- `0x1800071a4`
- `0x18000adec`
- `0x18000aef0`
- `0x18000af20`
- `0x18000b030`
- `0x18000b140`
- `0x18000b154`
- `0x180021cd8`
- `0x180021cf4`
- `0x180039f98`
- `0x18003a914`
- `0x18004116c`
- `0x18004371a`
- `0x180043750`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18003a0a3`
- `msvcrt!_wcsicmp` at `0x18003a0a3`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003a287`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003a29d`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003a493`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003a4d2`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003a4e4`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003a287`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003a29d`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003a493`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003a4d2`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003a4e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a23c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a23c`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18003a4c3`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18003a4c3`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18003a011`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18003a02f`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18003a011`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18003a02f`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18003a229`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18003a229`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18003a4a0`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18003a4a0`
- `api-ms-win-core-path-l1-1-0!PathCchCombineEx` at `0x18003a201`
- `api-ms-win-core-path-l1-1-0!PathCchCombineEx` at `0x18003a39b`
- `api-ms-win-core-path-l1-1-0!PathCchCombineEx` at `0x18003a201`
- `api-ms-win-core-path-l1-1-0!PathCchCombineEx` at `0x18003a39b`
- `api-ms-win-core-path-l1-1-0!PathCchFindExtension` at `0x18003a083`
- `api-ms-win-core-path-l1-1-0!PathCchFindExtension` at `0x18003a083`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18003a04c`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18003a04c`

## pseudocode

```c
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
  __int64 v14; // rdi
  __int64 v15; // rdx
  unsigned __int64 v16; // r8
  const WCHAR *v17; // r9
  const WCHAR *v18; // r8
  WCHAR *v19; // r13
  HRESULT v20; // edi
  int v21; // ecx
  HANDLE FirstFileW; // rdi
  int v23; // r8d
  int v24; // r9d
  const char *v25; // r9
  __int64 v26; // r9
  WCHAR *v27; // rax
  __int64 v28; // rcx
  unsigned __int64 v29; // rdx
  const WCHAR *v30; // r8
  PWSTR v31; // r12
  HRESULT v32; // r14d
  void *v33; // r14
  __int64 v34; // r8
  __int64 v35; // r8
  __int64 v36; // r14
  __int64 v38; // rax
  __int64 v39; // rax
  int v40; // r9d
  __int64 v41; // rax
  __int64 v42; // rax
  int v43; // ecx
  __int64 v44; // r8
  int v45; // r9d
  unsigned int v46; // eax
  int v47; // r8d
  __int64 v48; // rax
  __int64 v49; // rax
  int v50; // r9d
  __int64 v51; // rax
  __int64 v52; // rax
  __int64 v53; // r8
  int v54; // r9d
  unsigned int v55; // eax
  __int64 v56; // rax
  __int64 v57; // rax
  int v58; // r9d
  unsigned int v59; // eax
  int dwFlags; // [rsp+20h] [rbp-E0h]
  WCHAR *cFileName; // [rsp+40h] [rbp-C0h] BYREF
  void *v62; // [rsp+48h] [rbp-B8h] BYREF
  int v63; // [rsp+50h] [rbp-B0h]
  int v64[2]; // [rsp+58h] [rbp-A8h] BYREF
  PWSTR pszPathOut[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v66; // [rsp+70h] [rbp-90h]
  __int64 v67; // [rsp+78h] [rbp-88h]
  PCWSTR ppszExt; // [rsp+80h] [rbp-80h] BYREF
  PWSTR v69[2]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v70; // [rsp+98h] [rbp-68h]
  __int64 v71; // [rsp+A0h] [rbp-60h]
  void *v72; // [rsp+A8h] [rbp-58h] BYREF
  HANDLE v73; // [rsp+B0h] [rbp-50h] BYREF
  _WORD v74[8]; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v75; // [rsp+C8h] [rbp-38h]
  __int64 v76; // [rsp+D0h] [rbp-30h]
  _QWORD *v77; // [rsp+D8h] [rbp-28h]
  PCWSTR pszMore[2]; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v79; // [rsp+F0h] [rbp-10h]
  unsigned __int64 v80; // [rsp+F8h] [rbp-8h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+100h] [rbp+0h] BYREF
  _WORD v82[8]; // [rsp+350h] [rbp+250h] BYREF
  __int64 v83; // [rsp+360h] [rbp+260h]
  __int64 v84; // [rsp+368h] [rbp+268h]
  wil::details::in1diag3 *retaddr; // [rsp+3C8h] [rbp+2C8h]

  v77 = a2;
  *a2 = 0;
  a2[1] = 0;
  a2[2] = 0;
  v63 = 1;
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
      if ( (unsigned int)dword_18005A000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_18005A000, 0) )
      {
        v38 = std::wstring::c_str(v3);
        v39 = _tlgTypeMapBase<unsigned short *,void>::_tlgWrapAuto(&v62, v38);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          (unsigned int)&dword_18005A000,
          (unsigned int)&word_1800502B6,
          0,
          v40,
          v39);
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
      v80 = 7;
      v79 = 0;
      LOWORD(pszMore[0]) = 0;
      std::wstring::assign(pszMore, L"*.ppkg");
      *(_OWORD *)pszPathOut = 0;
      v15 = 0;
      v66 = 0;
      v16 = *(_QWORD *)(v3 + 16) + v79 + 6;
      if ( v16 )
      {
        if ( v16 > 0x7FFFFFFFFFFFFFFFLL )
          ((void (__noreturn *)(void))std::vector<ProvSource *>::_Xlen)();
        std::vector<unsigned short>::_Reallocate(pszPathOut, *(_QWORD *)(v3 + 16) + v79 + 6);
        v15 = v66;
      }
      v17 = (const WCHAR *)pszMore;
      if ( v80 >= 8 )
        v17 = pszMore[0];
      if ( *(_QWORD *)(v3 + 24) < 8u )
        v18 = (const WCHAR *)v3;
      else
        v18 = *(const WCHAR **)v3;
      v19 = pszPathOut[0];
      v20 = PathCchCombineEx(pszPathOut[0], (signed __int64)(v15 - (unsigned __int64)pszPathOut[0]) >> 1, v18, v17, 1u);
      if ( v20 < 0 )
      {
        if ( (unsigned int)dword_18005A000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_18005A000, 0) )
        {
          LODWORD(cFileName) = v20;
          v56 = std::vector<unsigned short>::data(pszPathOut);
          v57 = _tlgTypeMapBase<unsigned short *,void>::_tlgWrapAuto(&v62, v56);
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
            (unsigned int)&dword_18005A000,
            (unsigned int)byte_18005020B,
            0,
            v58,
            v57,
            (__int64)&cFileName);
        }
        v59 = wil::verify_hresult<long>((unsigned int)v20);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xE6,
          (unsigned int)"onecoreuap\\admin\\prov\\lib\\packagecollector.cpp",
          (const char *)v59,
          dwFlags);
      }
      memset_0(&FindFileData, 0, sizeof(FindFileData));
      FirstFileW = FindFirstFileW(v19, &FindFileData);
      v73 = FirstFileW;
      if ( FirstFileW == (HANDLE)-1LL )
      {
        if ( GetLastError() != 2 )
        {
          if ( (unsigned int)dword_18005A000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_18005A000, 0) )
          {
            LODWORD(cFileName) = v47;
            v48 = std::vector<unsigned short>::data(pszPathOut);
            v49 = _tlgTypeMapBase<unsigned short *,void>::_tlgWrapAuto(&v62, v48);
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_18005A000,
              (unsigned int)byte_1800501D1,
              0,
              v50,
              v49,
              (__int64)&cFileName);
          }
          wil::details::in1diag3::Throw_GetLastError(
            retaddr,
            (void *)0xF9,
            (unsigned int)"onecoreuap\\admin\\prov\\lib\\packagecollector.cpp",
            v25);
        }
        if ( (unsigned int)dword_18005A000 > 4 )
        {
          cFileName = v19;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
            (unsigned int)&dword_18005A000,
            (unsigned int)&byte_18005019F,
            0,
            (_DWORD)v25,
            (__int64)&cFileName);
        }
        if ( v19 )
          operator delete(v19);
        if ( v80 >= 8 )
          goto LABEL_78;
      }
      else
      {
        do
        {
          if ( (unsigned int)dword_18005A000 > 5 )
          {
            cFileName = FindFileData.cFileName;
            *(_QWORD *)v64 = v19;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
              v21,
              (unsigned int)byte_180050163,
              v23,
              v24,
              (__int64)v64,
              (__int64)&cFileName);
          }
          v26 = 260;
          v27 = FindFileData.cFileName;
          do
          {
            if ( !*v27 )
              break;
            ++v27;
            --v26;
          }
          while ( v26 );
          if ( !v26 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x104,
              (unsigned int)"onecoreuap\\admin\\prov\\lib\\packagecollector.cpp",
              (const char *)0x80070057LL,
              dwFlags);
          *(_OWORD *)v69 = 0;
          v28 = 0;
          v70 = 0;
          v29 = ((260 - v26) & ((unsigned __int128)-(__int128)(unsigned __int64)v26 >> 64) & -(__int64)(v26 != 0))
              + *(_QWORD *)(v3 + 16)
              + 6LL;
          if ( v29 )
          {
            if ( v29 > 0x7FFFFFFFFFFFFFFFLL )
              std::vector<ProvSource *>::_Xlen(0, v29, -v26);
            std::vector<unsigned short>::_Reallocate(v69, v29);
            v28 = v70;
          }
          if ( *(_QWORD *)(v3 + 24) < 8u )
            v30 = (const WCHAR *)v3;
          else
            v30 = *(const WCHAR **)v3;
          v31 = v69[0];
          v32 = PathCchCombineEx(
                  v69[0],
                  (signed __int64)(v28 - (unsigned __int64)v69[0]) >> 1,
                  v30,
                  FindFileData.cFileName,
                  1u);
          if ( v32 < 0 )
          {
            if ( (unsigned int)dword_18005A000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_18005A000, 0) )
            {
              LODWORD(cFileName) = v32;
              _tlgTypeMapBase<unsigned short *,void>::_tlgWrapAuto(&v62, FindFileData.cFileName);
              v51 = std::vector<unsigned short>::data(v69);
              v52 = _tlgTypeMapBase<unsigned short *,void>::_tlgWrapAuto(&v72, v51);
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
                (unsigned int)&cFileName,
                (unsigned int)&dword_180050114,
                v53,
                v54,
                v52,
                v53,
                (__int64)&cFileName);
            }
            v55 = wil::verify_hresult<long>((unsigned int)v32);
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x113,
              (unsigned int)"onecoreuap\\admin\\prov\\lib\\packagecollector.cpp",
              (const char *)v55,
              dwFlags);
          }
          v33 = operator new(0xA8u);
          v62 = v33;
          if ( v33 )
          {
            *(_QWORD *)v64 = v74;
            v76 = 7;
            v75 = 0;
            v74[0] = 0;
            if ( *v31 )
            {
              v34 = -1;
              do
                ++v34;
              while ( v31[v34] );
            }
            std::wstring::assign(v74, v31);
            v84 = 7;
            v83 = 0;
            v82[0] = 0;
            if ( FindFileData.cFileName[0] )
            {
              v35 = -1;
              do
                ++v35;
              while ( FindFileData.cFileName[v35] );
            }
            std::wstring::assign(v82, FindFileData.cFileName);
            v36 = ProvPackage::ProvPackage(v33, v82, v74);
          }
          else
          {
            v36 = 0;
          }
          if ( a2[1] == a2[2] )
            std::vector<std::unique_ptr<ProvPackage>>::_Reserve(a2);
          *(_QWORD *)a2[1] = v36;
          a2[1] += 8LL;
          if ( v31 )
            operator delete(v31);
        }
        while ( FindNextFileW(FirstFileW, &FindFileData) );
        if ( FirstFileW )
          FindClose(FirstFileW);
        if ( v19 )
          operator delete(v19);
        if ( v80 >= 8 )
LABEL_78:
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
        if ( (unsigned int)dword_18005A000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_18005A000, 0x400000000000LL) )
        {
          LODWORD(cFileName) = -2147024809;
          _tlgTypeMapBase<unsigned short *,void>::_tlgWrapAuto(&v62, FileNameW);
          v41 = std::wstring::c_str(v3);
          v42 = _tlgTypeMapBase<unsigned short *,void>::_tlgWrapAuto(&v73, v41);
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
            v43,
            (unsigned int)&unk_180050248,
            v44,
            v45,
            v42,
            v44,
            (__int64)&cFileName);
        }
        v46 = wil::verify_hresult<long>(2147942487LL);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xD3,
          (unsigned int)"onecoreuap\\admin\\prov\\lib\\packagecollector.cpp",
          (const char *)v46,
          dwFlags);
      }
      v12 = operator new(0xA8u);
      v72 = v12;
      if ( v12 )
      {
        *(_QWORD *)v64 = v69;
        v71 = 7;
        v70 = 0;
        LOWORD(v69[0]) = 0;
        std::wstring::assign(v69);
        v67 = 7;
        v66 = 0;
        LOWORD(pszPathOut[0]) = 0;
        if ( *FileNameW )
        {
          v13 = -1;
          do
            ++v13;
          while ( FileNameW[v13] );
        }
        std::wstring::assign(pszPathOut, FileNameW);
        v14 = ProvPackage::ProvPackage(v12, pszPathOut, v69);
      }
      else
      {
        v14 = 0;
      }
      if ( a2[1] == a2[2] )
        std::vector<std::unique_ptr<ProvPackage>>::_Reserve(a2);
      *(_QWORD *)a2[1] = v14;
      a2[1] += 8LL;
    }
    v3 += 32;
  }
  if ( (unsigned int)dword_18005A000 > 5 )
    tlgWriteTransfer_EventWriteTransfer(&dword_18005A000, word_1800500EA, 0, 0, 2, v82);
  return a2;
}

```

## disassembly

```asm
0x180039f98  push    rbp
0x180039f9a  push    rbx
0x180039f9b  push    rsi
0x180039f9c  push    rdi
0x180039f9d  push    r12
0x180039f9f  push    r13
0x180039fa1  push    r14
0x180039fa3  push    r15
0x180039fa5  lea     rbp, [rsp-288h]
0x180039fad  sub     rsp, 388h
0x180039fb4  mov     rax, cs:__security_cookie
0x180039fbb  xor     rax, rsp
0x180039fbe  mov     [rbp+2C0h+var_50], rax
0x180039fc5  mov     r15, rdx
0x180039fc8  mov     [rbp+2C0h+var_2E8], rdx
0x180039fcc  xor     r12d, r12d
0x180039fcf  mov     [rsp+3C0h+var_370], r12d
0x180039fd4  mov     [rdx], r12
0x180039fd7  mov     [rdx+8], r12
0x180039fdb  mov     [rdx+10h], r12
0x180039fdf  mov     [rsp+3C0h+var_370], 1
0x180039fe7  mov     rbx, [rcx+8]
0x180039feb  mov     rsi, [rcx+10h]
0x180039fef  mov     r14, 7FFFFFFFFFFFFFFFh
0x180039ff9  cmp     rbx, rsi
0x180039ffc  jz      loc_18003A4FD
0x18003a002  cmp     qword ptr [rbx+18h], 8
0x18003a007  jb      short loc_18003A00E
0x18003a009  mov     rcx, [rbx]
0x18003a00c  jmp     short loc_18003A011
0x18003a00e  mov     rcx, rbx; lpFileName
0x18003a011  call    cs:__imp_GetFileAttributesW
0x18003a017  cmp     eax, 0FFFFFFFFh
0x18003a01a  jz      loc_18003A55B
0x18003a020  cmp     qword ptr [rbx+18h], 8
0x18003a025  jb      short loc_18003A02C
0x18003a027  mov     rcx, [rbx]
0x18003a02a  jmp     short loc_18003A02F
0x18003a02c  mov     rcx, rbx; lpFileName
0x18003a02f  call    cs:__imp_GetFileAttributesW
0x18003a035  test    al, 10h
0x18003a037  jnz     loc_18003A16C
0x18003a03d  cmp     qword ptr [rbx+18h], 8
0x18003a042  jb      short loc_18003A049
0x18003a044  mov     rcx, [rbx]
0x18003a047  jmp     short loc_18003A04C
0x18003a049  mov     rcx, rbx; pszPath
0x18003a04c  call    cs:__imp_PathFindFileNameW
0x18003a052  mov     rdi, rax
0x18003a055  mov     rcx, [rbp+2C8h]; this
0x18003a05c  test    rax, rax
0x18003a05f  jz      loc_18003A66D
0x18003a065  mov     [rbp+2C0h+ppszExt], r12
0x18003a069  mov     rdx, [rbx+10h]
0x18003a06d  inc     rdx; cchPath
0x18003a070  cmp     qword ptr [rbx+18h], 8
0x18003a075  jb      short loc_18003A07C
0x18003a077  mov     rcx, [rbx]
0x18003a07a  jmp     short loc_18003A07F
0x18003a07c  mov     rcx, rbx; pszPath
0x18003a07f  lea     r8, [rbp+2C0h+ppszExt]; ppszExt
0x18003a083  call    cs:__imp_PathCchFindExtension
0x18003a089  mov     rcx, [rbp+2C8h]; this
0x18003a090  test    eax, eax
0x18003a092  js      loc_18003A658
0x18003a098  lea     rdx, aPpkg_0; ".ppkg"
0x18003a09f  mov     rcx, [rbp+2C0h+ppszExt]; String1
0x18003a0a3  call    cs:__imp__wcsicmp
0x18003a0a9  test    eax, eax
0x18003a0ab  jnz     loc_18003A5C1
0x18003a0b1  mov     ecx, 0A8h; Size
0x18003a0b6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003a0bb  mov     r14, rax
0x18003a0be  mov     [rbp+2C0h+var_318], rax
0x18003a0c2  test    rax, rax
0x18003a0c5  jz      short loc_18003A146
0x18003a0c7  lea     rax, [rbp+2C0h+var_338]
0x18003a0cb  mov     qword ptr [rsp+3C0h+var_368], rax
0x18003a0d0  mov     [rbp+2C0h+var_320], 7
0x18003a0d8  mov     [rbp+2C0h+var_328], r12
0x18003a0dc  mov     word ptr [rbp+2C0h+var_338], r12w
0x18003a0e1  or      r9, 0FFFFFFFFFFFFFFFFh
0x18003a0e5  xor     r8d, r8d
0x18003a0e8  mov     rdx, rbx
0x18003a0eb  lea     rcx, [rbp+2C0h+var_338]; void *
0x18003a0ef  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x18003a0f4  nop
0x18003a0f5  mov     [rsp+3C0h+var_348], 7
0x18003a0fe  mov     [rsp+3C0h+var_350], r12
0x18003a103  mov     word ptr [rsp+3C0h+pszPathOut], r12w
0x18003a109  cmp     [rdi], r12w
0x18003a10d  jnz     short loc_18003A114
0x18003a10f  mov     r8, r12
0x18003a112  jmp     short loc_18003A122
0x18003a114  or      r8, 0FFFFFFFFFFFFFFFFh
0x18003a118  inc     r8
0x18003a11b  cmp     [rdi+r8*2], r12w
0x18003a120  jnz     short loc_18003A118
0x18003a122  mov     rdx, rdi; Src
0x18003a125  lea     rcx, [rsp+3C0h+pszPathOut]; void *
0x18003a12a  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18003a12f  nop
0x18003a130  lea     r8, [rbp+2C0h+var_338]
0x18003a134  lea     rdx, [rsp+3C0h+pszPathOut]
0x18003a139  mov     rcx, r14
0x18003a13c  call    ??0ProvPackage@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; ProvPackage::ProvPackage(std::wstring,std::wstring)
0x18003a141  mov     rdi, rax
0x18003a144  jmp     short loc_18003A149
0x18003a146  mov     rdi, r12
0x18003a149  mov     rax, [r15+10h]
0x18003a14d  cmp     [r15+8], rax
0x18003a151  jnz     short loc_18003A15B
0x18003a153  mov     rcx, r15
0x18003a156  call    ?_Reserve@?$vector@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@V?$allocator@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@@2@@std@@IEAAX_K@Z; std::vector<std::unique_ptr<ProvPackage>>::_Reserve(unsigned __int64)
0x18003a15b  mov     rax, [r15+8]
0x18003a15f  mov     [rax], rdi
0x18003a162  add     qword ptr [r15+8], 8
0x18003a167  jmp     loc_18003A4EA
0x18003a16c  mov     [rbp+2C0h+var_2C8], 7
0x18003a174  mov     [rbp+2C0h+var_2D0], r12
0x18003a178  mov     word ptr [rbp+2C0h+pszMore], r12w
0x18003a17d  mov     r8d, 6
0x18003a183  lea     rdx, aPpkg; "*.ppkg"
0x18003a18a  lea     rcx, [rbp+2C0h+pszMore]; void *
0x18003a18e  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18003a193  nop
0x18003a194  xorps   xmm0, xmm0
0x18003a197  movdqu  xmmword ptr [rsp+3C0h+pszPathOut], xmm0
0x18003a19d  mov     rdx, r12
0x18003a1a0  mov     [rsp+3C0h+var_350], rdx
0x18003a1a5  mov     r8, [rbp+2C0h+var_2D0]
0x18003a1a9  add     r8, 6
0x18003a1ad  add     r8, [rbx+10h]
0x18003a1b1  jz      short loc_18003A1CE
0x18003a1b3  cmp     r8, r14
0x18003a1b6  ja      loc_18003A685
0x18003a1bc  mov     rdx, r8
0x18003a1bf  lea     rcx, [rsp+3C0h+pszPathOut]
0x18003a1c4  call    ?_Reallocate@?$vector@GV?$allocator@G@std@@@std@@IEAAX_K@Z; std::vector<ushort>::_Reallocate(unsigned __int64)
0x18003a1c9  mov     rdx, [rsp+3C0h+var_350]
0x18003a1ce  lea     r9, [rbp+2C0h+pszMore]
0x18003a1d2  cmp     [rbp+2C0h+var_2C8], 8
0x18003a1d7  cmovnb  r9, [rbp+2C0h+pszMore]; pszMore
0x18003a1dc  cmp     qword ptr [rbx+18h], 8
0x18003a1e1  jb      short loc_18003A1E8
0x18003a1e3  mov     r8, [rbx]
0x18003a1e6  jmp     short loc_18003A1EB
0x18003a1e8  mov     r8, rbx; pszPathIn
0x18003a1eb  mov     r13, [rsp+3C0h+pszPathOut]
0x18003a1f0  sub     rdx, r13
0x18003a1f3  sar     rdx, 1; cchPathOut
0x18003a1f6  mov     [rsp+3C0h+dwFlags], 1; dwFlags
0x18003a1fe  mov     rcx, r13; pszPathOut
0x18003a201  call    cs:__imp_PathCchCombineEx
0x18003a207  mov     edi, eax
0x18003a209  test    eax, eax
0x18003a20b  js      loc_18003A7A3
0x18003a211  xor     edx, edx; Val
0x18003a213  mov     r8d, 250h; Size
0x18003a219  lea     rcx, [rbp+2C0h+FindFileData]; void *
0x18003a21d  call    memset_0
0x18003a222  lea     rdx, [rbp+2C0h+FindFileData]; lpFindFileData
0x18003a226  mov     rcx, r13; lpFileName
0x18003a229  call    cs:__imp_FindFirstFileW
0x18003a22f  mov     rdi, rax
0x18003a232  mov     [rbp+2C0h+var_310], rax
0x18003a236  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18003a23a  jnz     short loc_18003A2A8
0x18003a23c  call    cs:__imp_GetLastError
0x18003a242  mov     r8d, eax
0x18003a245  cmp     eax, 2
0x18003a248  mov     eax, cs:dword_18005A000
0x18003a24e  jnz     loc_18003A68B
0x18003a254  cmp     eax, 4
0x18003a257  jbe     short loc_18003A27F
0x18003a259  mov     [rsp+3C0h+var_380], r13
0x18003a25e  lea     rax, [rsp+3C0h+var_380]
0x18003a263  mov     qword ptr [rsp+3C0h+dwFlags], rax
0x18003a268  xor     r8d, r8d
0x18003a26b  lea     rdx, byte_18005019F
0x18003a272  lea     rcx, dword_18005A000
0x18003a279  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18003a27e  nop
0x18003a27f  test    r13, r13
0x18003a282  jz      short loc_18003A28E
0x18003a284  mov     rcx, r13
0x18003a287  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003a28d  nop
0x18003a28e  cmp     [rbp+2C0h+var_2C8], 8
0x18003a293  jb      loc_18003A4F4
0x18003a299  mov     rcx, [rbp+2C0h+pszMore]
0x18003a29d  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003a2a3  jmp     loc_18003A4F4
0x18003a2a8  mov     eax, cs:dword_18005A000
0x18003a2ae  cmp     eax, 5
0x18003a2b1  jbe     short loc_18003A2E1
0x18003a2b3  lea     rax, [rbp+2C0h+FindFileData.cFileName]
0x18003a2b7  mov     [rsp+3C0h+var_380], rax
0x18003a2bc  mov     qword ptr [rsp+3C0h+var_368], r13
0x18003a2c1  lea     rax, [rsp+3C0h+var_380]
0x18003a2c6  mov     [rsp+3C0h+var_398], rax
0x18003a2cb  lea     rax, [rsp+3C0h+var_368]
0x18003a2d0  mov     qword ptr [rsp+3C0h+dwFlags], rax; int
0x18003a2d5  lea     rdx, byte_180050163
0x18003a2dc  call    ??$Write@U?$_tlgWrapSz@G@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18003a2e1  mov     r9d, 104h
0x18003a2e7  lea     rax, [rbp+2C0h+FindFileData.cFileName]
0x18003a2eb  cmp     [rax], r12w
0x18003a2ef  jz      short loc_18003A2FB
0x18003a2f1  add     rax, 2
0x18003a2f5  sub     r9, 1
0x18003a2f9  jnz     short loc_18003A2EB
0x18003a2fb  mov     rax, r9
0x18003a2fe  neg     rax
0x18003a301  sbb     r10d, r10d
0x18003a304  not     r10d
0x18003a307  and     r10d, 80070057h
0x18003a30e  mov     r8, r9
0x18003a311  mov     rax, r9
0x18003a314  mov     ecx, 104h
0x18003a319  sub     rcx, r9
0x18003a31c  neg     rax
0x18003a31f  sbb     rdx, rdx
0x18003a322  and     rdx, rcx
0x18003a325  neg     r8
0x18003a328  sbb     r11, r11
0x18003a32b  and     r11, rdx
0x18003a32e  mov     rcx, [rbp+2C8h]; this
0x18003a335  test    r9, r9
0x18003a338  jz      loc_18003A78E
0x18003a33e  xorps   xmm0, xmm0
0x18003a341  movdqu  xmmword ptr [rbp+2C0h+var_338], xmm0
0x18003a346  mov     rcx, r12
0x18003a349  mov     [rbp+2C0h+var_328], rcx
0x18003a34d  mov     rdx, [rbx+10h]
0x18003a351  add     rdx, 6
0x18003a355  add     rdx, r11
0x18003a358  jz      short loc_18003A370
0x18003a35a  cmp     rdx, r14
0x18003a35d  ja      loc_18003A6FC
0x18003a363  lea     rcx, [rbp+2C0h+var_338]
0x18003a367  call    ?_Reallocate@?$vector@GV?$allocator@G@std@@@std@@IEAAX_K@Z; std::vector<ushort>::_Reallocate(unsigned __int64)
0x18003a36c  mov     rcx, [rbp+2C0h+var_328]
0x18003a370  cmp     qword ptr [rbx+18h], 8
0x18003a375  jb      short loc_18003A37C
0x18003a377  mov     r8, [rbx]
0x18003a37a  jmp     short loc_18003A37F
0x18003a37c  mov     r8, rbx; pszPathIn
0x18003a37f  mov     r12, [rbp+2C0h+var_338]
0x18003a383  sub     rcx, r12
0x18003a386  sar     rcx, 1
0x18003a389  mov     [rsp+3C0h+dwFlags], 1; dwFlags
0x18003a391  lea     r9, [rbp+2C0h+FindFileData.cFileName]; pszMore
0x18003a395  mov     rdx, rcx; cchPathOut
0x18003a398  mov     rcx, r12; pszPathOut
0x18003a39b  call    cs:__imp_PathCchCombineEx
0x18003a3a1  mov     r14d, eax
0x18003a3a4  test    eax, eax
0x18003a3a6  js      loc_18003A702
0x18003a3ac  mov     ecx, 0A8h; Size
0x18003a3b1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003a3b6  mov     r14, rax
0x18003a3b9  mov     [rsp+3C0h+var_378], rax
0x18003a3be  xor     edx, edx
0x18003a3c0  test    rax, rax
0x18003a3c3  jz      loc_18003A46A
0x18003a3c9  lea     rax, [rbp+2C0h+var_308]
0x18003a3cd  mov     qword ptr [rsp+3C0h+var_368], rax
0x18003a3d2  mov     [rbp+2C0h+var_2F0], 7
0x18003a3da  mov     [rbp+2C0h+var_2F8], rdx
0x18003a3de  mov     [rbp+2C0h+var_308], dx
0x18003a3e2  cmp     [r12], dx
0x18003a3e7  jnz     short loc_18003A3EE
0x18003a3e9  mov     r8d, edx
0x18003a3ec  jmp     short loc_18003A3FC
0x18003a3ee  or      r8, 0FFFFFFFFFFFFFFFFh
0x18003a3f2  inc     r8
0x18003a3f5  cmp     [r12+r8*2], dx
0x18003a3fa  jnz     short loc_18003A3F2
0x18003a3fc  mov     rdx, r12; Src
0x18003a3ff  lea     rcx, [rbp+2C0h+var_308]; void *
0x18003a403  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18003a408  nop
0x18003a409  mov     [rbp+2C0h+var_58], 7
0x18003a414  xor     ecx, ecx
0x18003a416  mov     [rbp+2C0h+var_60], rcx
0x18003a41d  mov     [rbp+2C0h+var_70], cx
0x18003a424  cmp     [rbp+2C0h+FindFileData.cFileName], cx
0x18003a428  jnz     short loc_18003A42F
0x18003a42a  mov     r8d, ecx
0x18003a42d  jmp     short loc_18003A441
0x18003a42f  lea     rax, [rbp+2C0h+FindFileData.cFileName]
0x18003a433  or      r8, 0FFFFFFFFFFFFFFFFh
0x18003a437  inc     r8
0x18003a43a  cmp     [rax+r8*2], cx
0x18003a43f  jnz     short loc_18003A437
0x18003a441  lea     rdx, [rbp+2C0h+FindFileData.cFileName]; Src
0x18003a445  lea     rcx, [rbp+2C0h+var_70]; void *
0x18003a44c  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18003a451  nop
  ... truncated ...
```
