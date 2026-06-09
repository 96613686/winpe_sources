# PackageCopier::CopyPackages(std::vector<std::unique_ptr<ProvPackage,std::default_delete<ProvPackage>>,std::allocator<std::unique_ptr<ProvPackage,std::default_delete<ProvPackage>>>> const &,std::vector<bool,std::allocator<bool>> const &,std::vector<std::unique_ptr<ProvPackage,std::default_delete<ProvPackage>>,std::allocator<std::unique_ptr<ProvPackage,std::default_delete<ProvPackage>>>> *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x18002b410`
- end: `0x18002bb9e`
- name: `?CopyPackages@PackageCopier@@QEAAXAEBV?$vector@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@V?$allocator@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@@2@@std@@AEBV?$vector@_NV?$allocator@_N@std@@@3@PEAV23@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@@Z`
- size: `1934`
- prototype: `void __fastcall(__int64, __int64 *, _QWORD *, _QWORD *, PCWSTR pszPathIn)`
- caller_count: `1`
- callee_count: `22`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x18000f8d0`

## callees

- `0x1800015b4`
- `0x18000164c`
- `0x180001678`
- `0x180001878`
- `0x180001920`
- `0x180002614`
- `0x180002f44`
- `0x180004d68`
- `0x18001b388`
- `0x1800202e4`
- `0x180020bc8`
- `0x180020fe0`
- `0x1800210f0`
- `0x180021200`
- `0x180021214`
- `0x180026068`
- `0x18002b17c`
- `0x18002b410`
- `0x18002bba4`
- `0x18002e030`
- `0x180033ed0`
- `0x180037010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18002b5f4`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002b612`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002b628`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002b7b1`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002b814`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002b83a`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002b869`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002b5f4`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002b612`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002b628`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002b7b1`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002b814`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002b83a`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002b869`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b904`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b980`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b904`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b980`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18002b8b4`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18002b8b4`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18002b8de`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18002b8de`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18002b95a`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18002b95a`
- `api-ms-win-core-path-l1-1-0!PathCchCombineEx` at `0x18002b55c`
- `api-ms-win-core-path-l1-1-0!PathCchCombineEx` at `0x18002b55c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall PackageCopier::CopyPackages(__int64 a1, __int64 *a2, _QWORD *a3, _QWORD *a4, PCWSTR pszPathIn)
{
  __int64 v7; // rdx
  __int64 v8; // rax
  unsigned int v9; // r13d
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // rdx
  unsigned __int64 v13; // rax
  const WCHAR *v14; // r9
  const WCHAR *v15; // r8
  PWSTR v16; // r14
  HRESULT v17; // esi
  __int64 v18; // r8
  const WCHAR *v19; // rcx
  WCHAR *v20; // rcx
  int v21; // esi
  void *v22; // rsi
  PCWSTR *v23; // rdx
  __int64 v24; // r8
  __int64 v25; // rsi
  char v26; // al
  __int64 v27; // rcx
  __int64 v28; // rsi
  _QWORD *v29; // rcx
  __int64 v30; // rax
  __int64 v31; // rcx
  const WCHAR *v32; // rax
  DWORD FileAttributesW; // eax
  const WCHAR *v34; // rax
  DWORD v35; // edx
  int v36; // ebx
  signed int LastError; // eax
  __int64 v38; // rax
  __int64 v39; // rax
  int v40; // r9d
  const WCHAR *v41; // rax
  int v42; // ebx
  signed int v43; // eax
  __int64 v44; // rax
  __int64 v45; // rax
  int v46; // r9d
  __int64 v47; // rax
  __int64 v48; // rax
  int v49; // r9d
  unsigned int v50; // eax
  __int64 v51; // rax
  __int64 v52; // rax
  __int64 v53; // rax
  __int64 v54; // r8
  int v55; // r9d
  unsigned int v56; // eax
  int v57; // r9d
  unsigned int v58; // eax
  int v59; // r9d
  unsigned int v60; // eax
  int dwFlags; // [rsp+20h] [rbp-E0h]
  int dwFlagsa; // [rsp+20h] [rbp-E0h]
  int v63[2]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD *v64; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v65; // [rsp+50h] [rbp-B0h] BYREF
  char v66[8]; // [rsp+58h] [rbp-A8h] BYREF
  _WORD *v67; // [rsp+60h] [rbp-A0h] BYREF
  PWSTR pszPathOut[2]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v69; // [rsp+78h] [rbp-88h]
  _WORD v70[8]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v71; // [rsp+90h] [rbp-70h]
  __int64 v72; // [rsp+98h] [rbp-68h]
  PCWSTR v73; // [rsp+A0h] [rbp-60h]
  LPWSTR pObjectName[2]; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v75; // [rsp+B8h] [rbp-48h]
  unsigned __int64 v76; // [rsp+C0h] [rbp-40h]
  PCWSTR pszMore[2]; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v78; // [rsp+D8h] [rbp-28h]
  unsigned __int64 v79; // [rsp+E0h] [rbp-20h]
  void *v80[2]; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v81; // [rsp+F8h] [rbp-8h]
  unsigned __int64 v82; // [rsp+100h] [rbp+0h]
  _WORD v83[8]; // [rsp+108h] [rbp+8h] BYREF
  __int64 v84; // [rsp+118h] [rbp+18h]
  __int64 v85; // [rsp+120h] [rbp+20h]
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]

  v64 = a3;
  v73 = pszPathIn;
  if ( !*((_QWORD *)pszPathIn + 2) )
  {
    if ( *(_DWORD *)g_hProvTraceProvider > 2u && (unsigned __int8)tlgKeywordOn(g_hProvTraceProvider, 0) )
    {
      v63[0] = -2147024809;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        v57,
        (unsigned int)&word_180041826,
        0,
        v57,
        (__int64)v63);
    }
    v58 = wil::verify_hresult<long>(2147942487LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x5A,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\packagecopier.cpp",
      (const char *)v58,
      dwFlags);
  }
  v7 = *a2;
  v8 = (a2[1] - v7) >> 3;
  if ( v8 != a3[3] )
  {
    if ( *(_DWORD *)g_hProvTraceProvider > 2u && (unsigned __int8)tlgKeywordOn(g_hProvTraceProvider, 0) )
    {
      v63[0] = -2147024809;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        v59,
        (unsigned int)byte_1800417EB,
        0,
        v59,
        (__int64)v63);
    }
    v60 = wil::verify_hresult<long>(2147500036LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x64,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\packagecopier.cpp",
      (const char *)v60,
      dwFlags);
  }
  if ( v8 )
  {
    v9 = 0;
    while ( 1 )
    {
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v7 + 8LL * v9) + 56LL))(*(_QWORD *)(v7 + 8LL * v9));
      v82 = 7;
      v81 = 0;
      LOWORD(v80[0]) = 0;
      std::wstring::assign(v80);
      v10 = *(_QWORD *)(*a2 + 8LL * v9);
      (*(void (__fastcall **)(__int64, PCWSTR *))(*(_QWORD *)v10 + 8LL))(v10, pszMore);
      if ( !v81 || !v78 )
      {
        if ( *(_DWORD *)g_hProvTraceProvider > 3u )
          tlgWriteTransfer_EventWriteTransfer(g_hProvTraceProvider, &byte_1800417C7, 0, 0);
        if ( v79 < 8 )
          goto LABEL_60;
LABEL_59:
        operator delete((void *)pszMore[0]);
        goto LABEL_60;
      }
      *(_OWORD *)pszPathOut = 0;
      v12 = 0;
      v69 = 0;
      v13 = *((_QWORD *)pszPathIn + 2) + 266LL;
      if ( *((_QWORD *)pszPathIn + 2) != -266 )
      {
        if ( v13 > 0x7FFFFFFFFFFFFFFFLL )
          std::vector<std::unique_ptr<ProvPackage>>::_Xlen(0x7FFFFFFFFFFFFFFFLL, 0, v11);
        std::vector<unsigned short>::_Reallocate(pszPathOut, v13);
        v12 = v69;
      }
      v14 = (const WCHAR *)pszMore;
      if ( v79 >= 8 )
        v14 = pszMore[0];
      if ( *((_QWORD *)pszPathIn + 3) < 8u )
        v15 = pszPathIn;
      else
        v15 = *(const WCHAR **)pszPathIn;
      v16 = pszPathOut[0];
      v17 = PathCchCombineEx(pszPathOut[0], (signed __int64)(v12 - (unsigned __int64)pszPathOut[0]) >> 1, v15, v14, 1u);
      if ( v17 < 0 )
      {
        if ( *(_DWORD *)g_hProvTraceProvider > 2u && (unsigned __int8)tlgKeywordOn(g_hProvTraceProvider, 0) )
        {
          LODWORD(v64) = v17;
          v51 = std::wstring::c_str(pszMore);
          _tlgTypeMapBase<unsigned short *,void>::_tlgWrapAuto(v66, v51);
          v52 = std::vector<unsigned short>::data(pszPathOut);
          v53 = _tlgTypeMapBase<unsigned short *,void>::_tlgWrapAuto(&v67, v52);
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
            v55,
            (unsigned int)byte_18004177B,
            v54,
            v55,
            v53,
            v54,
            (__int64)&v64);
        }
        v56 = wil::verify_hresult<long>((unsigned int)v17);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x8E,
          (unsigned int)"onecoreuap\\admin\\prov\\lib\\packagecopier.cpp",
          (const char *)v56,
          dwFlagsa);
      }
      v76 = 7;
      v75 = 0;
      LOWORD(pObjectName[0]) = 0;
      if ( *v16 )
      {
        v18 = -1;
        do
          ++v18;
        while ( v16[v18] );
      }
      std::wstring::assign(pObjectName, v16);
      if ( !(unsigned int)PackageCopier::CopyFileW(v19, (const WCHAR *)v80, (__int64)pObjectName) )
        break;
      if ( ((1 << v9) & *(_DWORD *)(*v64 + 4 * ((unsigned __int64)v9 >> 5))) != 0 )
      {
        v20 = (WCHAR *)pObjectName;
        if ( v76 >= 8 )
          v20 = pObjectName[0];
        v21 = SetPackageAsSystemOrAdminOnlyFile(v20);
        if ( v21 < 0 )
        {
          v32 = (const WCHAR *)std::wstring::c_str(pObjectName);
          FileAttributesW = GetFileAttributesW(v32);
          if ( FileAttributesW != -1 )
          {
            if ( (FileAttributesW & 1) != 0 )
            {
              v34 = (const WCHAR *)std::wstring::c_str(pObjectName);
              if ( !SetFileAttributesW(v34, v35) )
              {
                v36 = g_hProvTraceProvider;
                if ( *(_DWORD *)g_hProvTraceProvider > 2u )
                {
                  if ( (unsigned __int8)tlgKeywordOn(g_hProvTraceProvider, 0) )
                  {
                    LastError = GetLastError();
                    if ( LastError > 0 )
                      LastError = (unsigned __int16)LastError | 0x80070000;
                    v63[0] = LastError;
                    v38 = std::wstring::c_str(pObjectName);
                    v39 = _tlgTypeMapBase<unsigned short *,void>::_tlgWrapAuto(v66, v38);
                    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
                      v36,
                      (unsigned int)byte_180041709,
                      0,
                      v40,
                      v39,
                      (__int64)v63);
                  }
                }
              }
            }
            v41 = (const WCHAR *)std::wstring::c_str(pObjectName);
            if ( !DeleteFileW(v41) )
            {
              v42 = g_hProvTraceProvider;
              if ( *(_DWORD *)g_hProvTraceProvider > 2u )
              {
                if ( (unsigned __int8)tlgKeywordOn(g_hProvTraceProvider, 0) )
                {
                  v43 = GetLastError();
                  if ( v43 > 0 )
                    v43 = (unsigned __int16)v43 | 0x80070000;
                  v63[0] = v43;
                  v44 = std::wstring::c_str(pObjectName);
                  v45 = _tlgTypeMapBase<unsigned short *,void>::_tlgWrapAuto(v66, v44);
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
                    v42,
                    (unsigned int)&word_1800416C6,
                    0,
                    v46,
                    v45,
                    (__int64)v63);
                }
              }
            }
          }
          if ( *(_DWORD *)g_hProvTraceProvider > 2u && (unsigned __int8)tlgKeywordOn(g_hProvTraceProvider, 0) )
          {
            LODWORD(v64) = v21;
            v47 = std::wstring::c_str(pObjectName);
            v48 = _tlgTypeMapBase<unsigned short *,void>::_tlgWrapAuto(&v67, v47);
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
              v49,
              (unsigned int)&unk_180041688,
              0,
              v49,
              v48,
              (__int64)&v64);
          }
          v50 = wil::verify_hresult<long>((unsigned int)v21);
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xC5,
            (unsigned int)"onecoreuap\\admin\\prov\\lib\\packagecopier.cpp",
            (const char *)v50,
            dwFlagsa);
        }
      }
      v22 = operator new(0xA8u);
      *(_QWORD *)v63 = v22;
      if ( v22 )
      {
        v67 = v70;
        v72 = 7;
        v71 = 0;
        v70[0] = 0;
        std::wstring::assign(v70);
        v23 = pszMore;
        if ( v79 >= 8 )
          v23 = (PCWSTR *)pszMore[0];
        v85 = 7;
        v84 = 0;
        v83[0] = 0;
        if ( *(_WORD *)v23 )
        {
          v24 = -1;
          do
            ++v24;
          while ( *((_WORD *)v23 + v24) );
        }
        std::wstring::assign(v83, v23);
        v25 = ProvPackage::ProvPackage(v22, v83, v70);
      }
      else
      {
        v25 = 0;
      }
      v65 = v25;
      if ( (unsigned __int64)&v65 >= a4[1] || (v26 = 1, *a4 > (unsigned __int64)&v65) )
        v26 = 0;
      v27 = a4[2];
      if ( v26 )
      {
        v28 = (__int64)&v66[-*a4 - 8] >> 3;
        if ( a4[1] == v27 )
          std::vector<std::unique_ptr<ProvPackage>>::_Reserve(a4);
        v29 = (_QWORD *)a4[1];
        v30 = *(_QWORD *)(*a4 + 8 * v28);
        *(_QWORD *)(*a4 + 8 * v28) = 0;
        *v29 = v30;
        v31 = v65;
      }
      else
      {
        if ( a4[1] == v27 )
          std::vector<std::unique_ptr<ProvPackage>>::_Reserve(a4);
        v31 = 0;
        *(_QWORD *)a4[1] = v25;
      }
      a4[1] += 8LL;
      if ( v31 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v31 + 64LL))(v31, 1);
      if ( v76 >= 8 )
        operator delete(pObjectName[0]);
      v76 = 7;
      v75 = 0;
      LOWORD(pObjectName[0]) = 0;
      if ( v16 )
        goto LABEL_25;
LABEL_26:
      if ( v79 >= 8 )
        goto LABEL_59;
LABEL_60:
      v79 = 7;
      v78 = 0;
      LOWORD(pszMore[0]) = 0;
      if ( v82 >= 8 )
        operator delete(v80[0]);
      ++v9;
      v7 = *a2;
      if ( v9 >= (unsigned __int64)((a2[1] - *a2) >> 3) )
        goto LABEL_63;
    }
    if ( *(_DWORD *)g_hProvTraceProvider > 3u )
      tlgWriteTransfer_EventWriteTransfer(g_hProvTraceProvider, byte_180041753, 0, 0);
    if ( v76 >= 8 )
      operator delete(pObjectName[0]);
    v76 = 7;
    v75 = 0;
    LOWORD(pObjectName[0]) = 0;
LABEL_25:
    operator delete(v16);
    goto LABEL_26;
  }
LABEL_63:
  if ( *((_QWORD *)pszPathIn + 3) >= 8u )
    operator delete(*(void **)pszPathIn);
  *((_QWORD *)pszPathIn + 3) = 7;
  *((_QWORD *)pszPathIn + 2) = 0;
  *pszPathIn = 0;
}

```

## disassembly

```asm
0x18002b410  mov     [rsp-8+arg_0], rbx
0x18002b415  push    rbp
0x18002b416  push    rsi
0x18002b417  push    rdi
0x18002b418  push    r12
0x18002b41a  push    r13
0x18002b41c  push    r14
0x18002b41e  push    r15
0x18002b420  lea     rbp, [rsp-30h]
0x18002b425  sub     rsp, 130h
0x18002b42c  mov     rax, cs:__security_cookie
0x18002b433  xor     rax, rsp
0x18002b436  mov     [rbp+60h+var_38], rax
0x18002b43a  mov     rdi, r9
0x18002b43d  mov     [rsp+160h+var_118], r8
0x18002b442  mov     r12, rdx
0x18002b445  mov     rbx, [rbp+60h+pszPathIn]
0x18002b44c  mov     [rbp+60h+var_C0], rbx
0x18002b450  xor     r15d, r15d
0x18002b453  cmp     [rbx+10h], r15
0x18002b457  jz      loc_18002BAD6
0x18002b45d  mov     rdx, [rdx]
0x18002b460  mov     rax, [r12+8]
0x18002b465  sub     rax, rdx
0x18002b468  sar     rax, 3
0x18002b46c  cmp     rax, [r8+18h]
0x18002b470  jnz     loc_18002BB3A
0x18002b476  lea     esi, [r15+7]
0x18002b47a  test    rax, rax
0x18002b47d  jz      loc_18002B85F
0x18002b483  mov     r13d, r15d
0x18002b486  mov     r15d, r13d
0x18002b489  mov     rcx, [rdx+r15*8]
0x18002b48d  mov     rax, [rcx]
0x18002b490  mov     rax, [rax+38h]
0x18002b494  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b499  mov     [rbp+60h+var_60], rsi
0x18002b49d  xor     esi, esi
0x18002b49f  mov     [rbp+60h+var_68], rsi
0x18002b4a3  mov     word ptr [rbp+60h+var_78], si
0x18002b4a7  or      r9, 0FFFFFFFFFFFFFFFFh
0x18002b4ab  xor     r8d, r8d
0x18002b4ae  mov     rdx, rax
0x18002b4b1  lea     rcx, [rbp+60h+var_78]; void *
0x18002b4b5  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x18002b4ba  nop
0x18002b4bb  mov     rax, [r12]
0x18002b4bf  mov     rcx, [rax+r15*8]
0x18002b4c3  mov     rax, [rcx]
0x18002b4c6  lea     rdx, [rbp+60h+pszMore]
0x18002b4ca  mov     rax, [rax+8]
0x18002b4ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b4d3  nop
0x18002b4d4  cmp     [rbp+60h+var_68], rsi
0x18002b4d8  jz      loc_18002B7D7
0x18002b4de  cmp     [rbp+60h+var_88], rsi
0x18002b4e2  jz      loc_18002B7D7
0x18002b4e8  xorps   xmm0, xmm0
0x18002b4eb  movdqu  xmmword ptr [rsp+160h+pszPathOut], xmm0
0x18002b4f1  mov     edx, esi
0x18002b4f3  mov     [rsp+160h+var_E8], rdx
0x18002b4f8  mov     rax, [rbx+10h]
0x18002b4fc  add     rax, 10Ah
0x18002b502  jz      short loc_18002B529
0x18002b504  mov     rcx, 7FFFFFFFFFFFFFFFh
0x18002b50e  cmp     rax, rcx
0x18002b511  ja      loc_18002B8A2
0x18002b517  mov     rdx, rax
0x18002b51a  lea     rcx, [rsp+160h+pszPathOut]
0x18002b51f  call    ?_Reallocate@?$vector@GV?$allocator@G@std@@@std@@IEAAX_K@Z; std::vector<ushort>::_Reallocate(unsigned __int64)
0x18002b524  mov     rdx, [rsp+160h+var_E8]
0x18002b529  lea     r9, [rbp+60h+pszMore]
0x18002b52d  cmp     [rbp+60h+var_80], 8
0x18002b532  cmovnb  r9, [rbp+60h+pszMore]; pszMore
0x18002b537  cmp     qword ptr [rbx+18h], 8
0x18002b53c  jb      short loc_18002B543
0x18002b53e  mov     r8, [rbx]
0x18002b541  jmp     short loc_18002B546
0x18002b543  mov     r8, rbx; pszPathIn
0x18002b546  mov     r14, [rsp+160h+pszPathOut]
0x18002b54b  sub     rdx, r14
0x18002b54e  sar     rdx, 1; cchPathOut
0x18002b551  mov     [rsp+160h+dwFlags], 1; dwFlags
0x18002b559  mov     rcx, r14; pszPathOut
0x18002b55c  call    cs:__imp_PathCchCombineEx
0x18002b562  mov     esi, eax
0x18002b564  xor     r10d, r10d
0x18002b567  test    eax, eax
0x18002b569  js      loc_18002BA42
0x18002b56f  mov     [rbp+60h+var_A0], 7
0x18002b577  mov     [rbp+60h+var_A8], r10
0x18002b57b  mov     word ptr [rbp+60h+pObjectName], r10w
0x18002b580  cmp     [r14], r10w
0x18002b584  jnz     short loc_18002B58B
0x18002b586  mov     r8d, r10d
0x18002b589  jmp     short loc_18002B599
0x18002b58b  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002b58f  inc     r8
0x18002b592  cmp     [r14+r8*2], r10w
0x18002b597  jnz     short loc_18002B58F
0x18002b599  mov     rdx, r14; Src
0x18002b59c  lea     rcx, [rbp+60h+pObjectName]; void *
0x18002b5a0  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18002b5a5  nop
0x18002b5a6  lea     r8, [rbp+60h+pObjectName]
0x18002b5aa  lea     rdx, [rbp+60h+var_78]
0x18002b5ae  call    ?CopyFileW@PackageCopier@@QEAAHAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; PackageCopier::CopyFileW(std::wstring const &,std::wstring const &)
0x18002b5b3  test    eax, eax
0x18002b5b5  jnz     short loc_18002B633
0x18002b5b7  mov     rcx, cs:g_hProvTraceProvider
0x18002b5be  mov     eax, [rcx]
0x18002b5c0  cmp     eax, 3
0x18002b5c3  jbe     short loc_18002B5E9
0x18002b5c5  lea     rax, [rbp+60h+var_58]
0x18002b5c9  mov     [rsp+160h+var_138], rax
0x18002b5ce  mov     [rsp+160h+dwFlags], 2
0x18002b5d6  xor     r9d, r9d
0x18002b5d9  xor     r8d, r8d
0x18002b5dc  lea     rdx, byte_180041753
0x18002b5e3  call    _tlgWriteTransfer_EventWriteTransfer
0x18002b5e8  nop
0x18002b5e9  cmp     [rbp+60h+var_A0], 8
0x18002b5ee  jb      short loc_18002B5FA
0x18002b5f0  mov     rcx, [rbp+60h+pObjectName]
0x18002b5f4  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18002b5fa  mov     esi, 7
0x18002b5ff  mov     [rbp+60h+var_A0], rsi
0x18002b603  xor     r15d, r15d
0x18002b606  mov     [rbp+60h+var_A8], r15
0x18002b60a  mov     word ptr [rbp+60h+pObjectName], r15w
0x18002b60f  mov     rcx, r14
0x18002b612  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18002b618  nop
0x18002b619  cmp     [rbp+60h+var_80], 8
0x18002b61e  jb      loc_18002B822
0x18002b624  mov     rcx, [rbp+60h+pszMore]
0x18002b628  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18002b62e  jmp     loc_18002B822
0x18002b633  mov     rcx, r15
0x18002b636  shr     r15, 5
0x18002b63a  mov     rax, [rsp+160h+var_118]
0x18002b63f  mov     rdx, [rax]
0x18002b642  mov     eax, 1
0x18002b647  shl     eax, cl
0x18002b649  test    [rdx+r15*4], eax
0x18002b64d  jz      short loc_18002B671
0x18002b64f  lea     rcx, [rbp+60h+pObjectName]
0x18002b653  cmp     [rbp+60h+var_A0], 8
0x18002b658  cmovnb  rcx, [rbp+60h+pObjectName]; pObjectName
0x18002b65d  call    ?SetPackageAsSystemOrAdminOnlyFile@@YAJPEAG@Z; SetPackageAsSystemOrAdminOnlyFile(ushort *)
0x18002b662  mov     esi, eax
0x18002b664  xor     r15d, r15d
0x18002b667  test    eax, eax
0x18002b669  js      loc_18002B8A8
0x18002b66f  jmp     short loc_18002B674
0x18002b671  xor     r15d, r15d
0x18002b674  mov     ecx, 0A8h; Size
0x18002b679  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002b67e  mov     rsi, rax
0x18002b681  mov     qword ptr [rsp+160h+var_120], rax
0x18002b686  test    rax, rax
0x18002b689  jz      loc_18002B715
0x18002b68f  lea     rax, [rbp+60h+var_E0]
0x18002b693  mov     [rsp+160h+var_100], rax
0x18002b698  mov     [rbp+60h+var_C8], 7
0x18002b6a0  mov     [rbp+60h+var_D0], r15
0x18002b6a4  mov     [rbp+60h+var_E0], r15w
0x18002b6a9  or      r9, 0FFFFFFFFFFFFFFFFh
0x18002b6ad  xor     r8d, r8d
0x18002b6b0  lea     rdx, [rbp+60h+pObjectName]
0x18002b6b4  lea     rcx, [rbp+60h+var_E0]; void *
0x18002b6b8  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x18002b6bd  nop
0x18002b6be  lea     rdx, [rbp+60h+pszMore]
0x18002b6c2  cmp     [rbp+60h+var_80], 8
0x18002b6c7  cmovnb  rdx, [rbp+60h+pszMore]; Src
0x18002b6cc  mov     [rbp+60h+var_40], 7
0x18002b6d4  mov     [rbp+60h+var_48], r15
0x18002b6d8  mov     [rbp+60h+var_58], r15w
0x18002b6dd  cmp     [rdx], r15w
0x18002b6e1  jnz     short loc_18002B6E8
0x18002b6e3  mov     r8, r15
0x18002b6e6  jmp     short loc_18002B6F6
0x18002b6e8  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002b6ec  inc     r8
0x18002b6ef  cmp     [rdx+r8*2], r15w
0x18002b6f4  jnz     short loc_18002B6EC
0x18002b6f6  lea     rcx, [rbp+60h+var_58]; void *
0x18002b6fa  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18002b6ff  nop
0x18002b700  lea     r8, [rbp+60h+var_E0]
0x18002b704  lea     rdx, [rbp+60h+var_58]
0x18002b708  mov     rcx, rsi
0x18002b70b  call    ??0ProvPackage@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; ProvPackage::ProvPackage(std::wstring,std::wstring)
0x18002b710  mov     rsi, rax
0x18002b713  jmp     short loc_18002B718
0x18002b715  mov     rsi, r15
0x18002b718  mov     [rsp+160h+var_110], rsi
0x18002b71d  lea     rax, [rsp+160h+var_110]
0x18002b722  cmp     rax, [rdi+8]
0x18002b726  jnb     short loc_18002B734
0x18002b728  lea     rax, [rsp+160h+var_110]
0x18002b72d  cmp     [rdi], rax
0x18002b730  mov     al, 1
0x18002b732  jbe     short loc_18002B737
0x18002b734  mov     al, r15b
0x18002b737  mov     rcx, [rdi+10h]
0x18002b73b  test    al, al
0x18002b73d  jz      short loc_18002B772
0x18002b73f  lea     rsi, [rsp+160h+var_110]
0x18002b744  sub     rsi, [rdi]
0x18002b747  sar     rsi, 3
0x18002b74b  cmp     [rdi+8], rcx
0x18002b74f  jnz     short loc_18002B759
0x18002b751  mov     rcx, rdi
0x18002b754  call    ?_Reserve@?$vector@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@V?$allocator@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@@2@@std@@IEAAX_K@Z; std::vector<std::unique_ptr<ProvPackage>>::_Reserve(unsigned __int64)
0x18002b759  mov     rdx, [rdi]
0x18002b75c  mov     rcx, [rdi+8]
0x18002b760  mov     rax, [rdx+rsi*8]
0x18002b764  mov     [rdx+rsi*8], r15
0x18002b768  mov     [rcx], rax
0x18002b76b  mov     rcx, [rsp+160h+var_110]
0x18002b770  jmp     short loc_18002B78A
0x18002b772  cmp     [rdi+8], rcx
0x18002b776  jnz     short loc_18002B780
0x18002b778  mov     rcx, rdi
0x18002b77b  call    ?_Reserve@?$vector@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@V?$allocator@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@@2@@std@@IEAAX_K@Z; std::vector<std::unique_ptr<ProvPackage>>::_Reserve(unsigned __int64)
0x18002b780  mov     rcx, r15
0x18002b783  mov     rax, [rdi+8]
0x18002b787  mov     [rax], rsi
0x18002b78a  add     qword ptr [rdi+8], 8
0x18002b78f  test    rcx, rcx
0x18002b792  jz      short loc_18002B7A6
0x18002b794  mov     rax, [rcx]
0x18002b797  mov     edx, 1
0x18002b79c  mov     rax, [rax+40h]
0x18002b7a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b7a5  nop
0x18002b7a6  cmp     [rbp+60h+var_A0], 8
0x18002b7ab  jb      short loc_18002B7B7
0x18002b7ad  mov     rcx, [rbp+60h+pObjectName]
0x18002b7b1  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18002b7b7  mov     esi, 7
0x18002b7bc  mov     [rbp+60h+var_A0], rsi
0x18002b7c0  mov     [rbp+60h+var_A8], r15
0x18002b7c4  mov     word ptr [rbp+60h+pObjectName], r15w
0x18002b7c9  test    r14, r14
0x18002b7cc  jz      loc_18002B619
0x18002b7d2  jmp     loc_18002B60F
0x18002b7d7  mov     rcx, cs:g_hProvTraceProvider
0x18002b7de  mov     eax, [rcx]
0x18002b7e0  cmp     eax, 3
0x18002b7e3  jbe     short loc_18002B809
0x18002b7e5  lea     rax, [rbp+60h+var_58]
0x18002b7e9  mov     [rsp+160h+var_138], rax
0x18002b7ee  mov     [rsp+160h+dwFlags], 2
0x18002b7f6  xor     r9d, r9d
0x18002b7f9  xor     r8d, r8d
0x18002b7fc  lea     rdx, byte_1800417C7
0x18002b803  call    _tlgWriteTransfer_EventWriteTransfer
0x18002b808  nop
0x18002b809  cmp     [rbp+60h+var_80], 8
0x18002b80e  jb      short loc_18002B81A
0x18002b810  mov     rcx, [rbp+60h+pszMore]
0x18002b814  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18002b81a  mov     esi, 7
0x18002b81f  xor     r15d, r15d
0x18002b822  mov     [rbp+60h+var_80], rsi
0x18002b826  mov     [rbp+60h+var_88], r15
0x18002b82a  mov     word ptr [rbp+60h+pszMore], r15w
0x18002b82f  cmp     [rbp+60h+var_60], 8
0x18002b834  jb      short loc_18002B840
0x18002b836  mov     rcx, [rbp+60h+var_78]
0x18002b83a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18002b840  inc     r13d
0x18002b843  mov     rdx, [r12]
0x18002b847  mov     rcx, [r12+8]
0x18002b84c  sub     rcx, rdx
0x18002b84f  sar     rcx, 3
0x18002b853  mov     eax, r13d
0x18002b856  cmp     rax, rcx
0x18002b859  jb      loc_18002B486
0x18002b85f  cmp     qword ptr [rbx+18h], 8
0x18002b864  jb      short loc_18002B86F
0x18002b866  mov     rcx, [rbx]
0x18002b869  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18002b86f  mov     [rbx+18h], rsi
0x18002b873  mov     [rbx+10h], r15
0x18002b877  mov     [rbx], r15w
0x18002b87b  mov     rcx, [rbp+60h+var_38]
0x18002b87f  xor     rcx, rsp; StackCookie
0x18002b882  call    __security_check_cookie
0x18002b887  mov     rbx, [rsp+160h+arg_0]
0x18002b88f  add     rsp, 130h
0x18002b896  pop     r15
0x18002b898  pop     r14
0x18002b89a  pop     r13
0x18002b89c  pop     r12
0x18002b89e  pop     rdi
0x18002b89f  pop     rsi
  ... truncated ...
```
