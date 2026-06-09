# Microsoft::Diagnostics::UtcApiManager::GetCustomTraceList(wchar_t * * *,ulong *)

- ea: `0x180291460`
- end: `0x180291b71`
- name: `?GetCustomTraceList@UtcApiManager@Diagnostics@Microsoft@@UEAAJPEAPEAPEA_WPEAK@Z`
- size: `1809`
- prototype: `__int64 __fastcall(Microsoft::Diagnostics::UtcApiManager *__hidden this, wchar_t ***, unsigned int *)`
- caller_count: `0`
- callee_count: `30`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callees

- `0x18002110c`
- `0x18002afd8`
- `0x18002b7c0`
- `0x18002cb04`
- `0x18002df00`
- `0x180064e8c`
- `0x180081924`
- `0x18008a4ec`
- `0x18009c194`
- `0x18009c8c0`
- `0x1800c1920`
- `0x1800c6024`
- `0x1800d3790`
- `0x1800dce08`
- `0x18010e55c`
- `0x18010f9b8`
- `0x1801245e0`
- `0x180124720`
- `0x1801288a0`
- `0x180142fcc`
- `0x1801b7bd0`
- `0x1801bbc78`
- `0x18020aac0`
- `0x18020baa0`
- `0x18020bab8`
- `0x18020ccd8`
- `0x18020dc9c`
- `0x180287660`
- `0x180291460`
- `0x180369010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18029152b`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180291719`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180291864`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18029152b`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180291719`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180291864`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x18029167a`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x18029167a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18029164d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18029164d`
- `RPCRT4!RpcRevertToSelf` at `0x180291848`
- `RPCRT4!RpcRevertToSelf` at `0x180291848`

## string_xrefs

- `0x18029168e`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x1802919ab`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x180291ac0`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x180291b17`: `onecore\base\telemetry\utc\service\engine\utcapimanager.cpp`
- `0x180291b5f`: `onecore\base\telemetry\utc\service\include\UtcApiManager.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall Microsoft::Diagnostics::UtcApiManager::GetCustomTraceList(
        Microsoft::Diagnostics::UtcApiManager *this,
        wchar_t ***a2,
        unsigned int *a3)
{
  unsigned int v5; // ebx
  __int64 v6; // rdx
  const WCHAR *v7; // rcx
  DWORD FileAttributesW; // eax
  int v9; // r8d
  int v10; // r9d
  __int128 *v11; // rax
  _QWORD *v12; // rdx
  void *v13; // rbx
  HRESULT v14; // eax
  __int64 v15; // rax
  __int64 v16; // rax
  const WCHAR *v17; // rcx
  DWORD v18; // eax
  Microsoft::Diagnostics::UtcApiManager *v19; // rcx
  int v20; // r8d
  int v21; // r9d
  __int128 *v22; // rax
  _QWORD *v23; // rdx
  const char *v24; // r9
  const WCHAR *v25; // rcx
  DWORD v26; // eax
  int v27; // r8d
  int v28; // r9d
  __int128 *v29; // rax
  _QWORD *v30; // rdx
  const void **v31; // rbx
  const void **v32; // rdi
  unsigned __int64 v33; // rbx
  wchar_t **v34; // rax
  __int64 v35; // rsi
  unsigned __int64 v36; // r14
  wchar_t *v37; // rax
  wchar_t *v38; // rcx
  const void *v39; // rdx
  int v41; // [rsp+20h] [rbp-E0h]
  int v42[4]; // [rsp+30h] [rbp-D0h] BYREF
  char v43; // [rsp+41h] [rbp-BFh]
  LPVOID pv; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t **v45; // [rsp+50h] [rbp-B0h] BYREF
  void *Src[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v47; // [rsp+68h] [rbp-98h]
  _BYTE v48[16]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v49[64]; // [rsp+80h] [rbp-80h] BYREF
  char v50; // [rsp+C0h] [rbp-40h]
  LPCWSTR lpFileName[3]; // [rsp+C8h] [rbp-38h] BYREF
  unsigned __int64 v52; // [rsp+E0h] [rbp-20h]
  __int128 v53; // [rsp+E8h] [rbp-18h] BYREF
  __m128i si128; // [rsp+F8h] [rbp-8h]
  _QWORD v55[2]; // [rsp+108h] [rbp+8h] BYREF
  char v56; // [rsp+118h] [rbp+18h]
  _OWORD v57[2]; // [rsp+130h] [rbp+30h] BYREF
  _QWORD v58[7]; // [rsp+150h] [rbp+50h] BYREF
  _QWORD *v59; // [rsp+188h] [rbp+88h]
  _QWORD v60[7]; // [rsp+190h] [rbp+90h] BYREF
  Microsoft::Diagnostics::UtcApiManager *v61; // [rsp+1C8h] [rbp+C8h]
  _QWORD v62[7]; // [rsp+1D0h] [rbp+D0h] BYREF
  _QWORD *v63; // [rsp+208h] [rbp+108h]
  wil::details::in1diag3 *retaddr; // [rsp+258h] [rbp+158h]

  *(_QWORD *)v42 = 60000;
  std::unique_lock<std::recursive_timed_mutex>::unique_lock<std::recursive_timed_mutex>(v48, (char *)this + 384, v42);
  if ( !v48[8] )
  {
    v5 = -2017128405;
    v6 = 2973;
LABEL_62:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
      (const char *)v5,
      v41);
    goto LABEL_63;
  }
  if ( !a2 || !a3 )
  {
    v5 = -2147024809;
    v6 = 2978;
    goto LABEL_62;
  }
  v53 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v53) = 0;
  *(_OWORD *)Src = 0;
  v47 = 0;
  std::wstring::wstring(lpFileName);
  Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(lpFileName, 1, 0);
  v7 = (const WCHAR *)lpFileName;
  if ( v52 > 7 )
    v7 = lpFileName[0];
  FileAttributesW = GetFileAttributesW(v7);
  if ( FileAttributesW != -1 && (FileAttributesW & 0x10) != 0 )
  {
    std::wstring::operator=(&v53, lpFileName);
    if ( (unsigned int)dword_1804543B0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1804543B0, 0x2000) )
    {
      v11 = &v53;
      if ( si128.m128i_i64[1] > 7uLL )
        v11 = (__int128 *)v53;
      *(_QWORD *)v42 = v11;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
        (unsigned int)&dword_1804543B0,
        (unsigned int)&byte_1803EBF07,
        v9,
        v10,
        (__int64)v42);
    }
    v50 = 0;
    v58[0] = off_18037E3A0;
    v58[1] = Src;
    v59 = v58;
    *(_OWORD *)v42 = *(_OWORD *)&Microsoft::Diagnostics::UtcApiManager::k_customProfilesFilePattern;
    v57[0] = *(_OWORD *)std::wstring::operator std::wstring_view(&v53, v55);
    Microsoft::Diagnostics::Utils::FileSystem::DoForEachFileInPattern(v57, v42, v58, v49);
    if ( v59 )
    {
      v12 = v58;
      LOBYTE(v12) = v59 != v58;
      (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v59 + 32LL))(v59, v12);
    }
  }
  pv = 0;
  if ( (unsigned __int8)IsSHGetKnownFolderPathPresent() )
  {
    v13 = pv;
    if ( pv )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)v42);
      CoTaskMemFree(v13);
      wil::last_error_context::~last_error_context((wil::last_error_context *)v42);
    }
    pv = 0;
    v14 = SHGetKnownFolderPath(&FOLDERID_PublicDocuments, 0x8000u, 0, (PWSTR *)&pv);
    if ( v14 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xBC3,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
        (const char *)(unsigned int)v14,
        v41);
  }
  if ( pv )
  {
    v15 = std::wstring::wstring(v57, pv);
    v16 = std::operator+<wchar_t>(v55, v15, L"\\FeedbackHub\\CustomTraceProfiles");
    std::wstring::operator=(lpFileName, v16);
    std::wstring::_Tidy_deallocate(v55);
    std::wstring::_Tidy_deallocate(v57);
  }
  else
  {
    std::wstring::_Assign<wchar_t>(lpFileName, L"%Public%\\Documents\\FeedbackHub\\CustomTraceProfiles", 50);
    Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(lpFileName, 1, 0);
  }
  v17 = (const WCHAR *)lpFileName;
  if ( v52 > 7 )
    v17 = lpFileName[0];
  v18 = GetFileAttributesW(v17);
  if ( v18 != -1 && (v18 & 0x10) != 0 )
  {
    std::wstring::operator=(&v53, lpFileName);
    if ( (unsigned int)dword_1804543B0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1804543B0, 0x2000) )
    {
      v22 = &v53;
      if ( si128.m128i_i64[1] > 7uLL )
        v22 = (__int128 *)v53;
      *(_QWORD *)v42 = v22;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
        (unsigned int)&dword_1804543B0,
        (unsigned int)&dword_1803EBEB4,
        v20,
        v21,
        (__int64)v42);
    }
    v50 = 0;
    v60[0] = off_18037E3D0;
    v60[1] = Src;
    v61 = (Microsoft::Diagnostics::UtcApiManager *)v60;
    v57[0] = *(_OWORD *)&Microsoft::Diagnostics::UtcApiManager::k_customProfilesFilePattern;
    *(_OWORD *)v42 = *(_OWORD *)std::wstring::operator std::wstring_view(&v53, v55);
    Microsoft::Diagnostics::Utils::FileSystem::DoForEachFileInPattern(v42, v57, v60, v49);
    v19 = v61;
    if ( v61 )
    {
      v23 = v60;
      LOBYTE(v23) = v61 != (Microsoft::Diagnostics::UtcApiManager *)v60;
      (*(void (__fastcall **)(Microsoft::Diagnostics::UtcApiManager *, _QWORD *))(*(_QWORD *)v61 + 32LL))(v61, v23);
    }
  }
  Microsoft::Diagnostics::UtcApiManager::ImpersonateRpcCaller(v19);
  std::wstring::_Assign<wchar_t>(lpFileName, L"%USERPROFILE%\\Documents\\FeedbackHub\\CustomTraceProfiles", 55);
  Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(lpFileName, 1, 0);
  if ( v43 && RpcRevertToSelf() )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x21E,
      (unsigned int)"onecore\\base\\telemetry\\utc\\service\\include\\UtcApiManager.h",
      v24);
  v25 = (const WCHAR *)lpFileName;
  if ( v52 > 7 )
    v25 = lpFileName[0];
  v26 = GetFileAttributesW(v25);
  if ( v26 != -1 && (v26 & 0x10) != 0 )
  {
    std::wstring::operator=(&v53, lpFileName);
    if ( (unsigned int)dword_1804543B0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1804543B0, 0x2000) )
    {
      v29 = &v53;
      if ( si128.m128i_i64[1] > 7uLL )
        v29 = (__int128 *)v53;
      *(_QWORD *)v42 = v29;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
        (unsigned int)&dword_1804543B0,
        (unsigned int)&word_1803EBDEE,
        v27,
        v28,
        (__int64)v42);
    }
    v50 = 0;
    v62[0] = off_18037E400;
    v62[1] = Src;
    v63 = v62;
    v57[0] = *(_OWORD *)&Microsoft::Diagnostics::UtcApiManager::k_customProfilesFilePattern;
    *(_OWORD *)v42 = *(_OWORD *)std::wstring::operator std::wstring_view(&v53, v55);
    Microsoft::Diagnostics::Utils::FileSystem::DoForEachFileInPattern(v42, v57, v62, v49);
    if ( v63 )
    {
      v30 = v62;
      LOBYTE(v30) = v63 != v62;
      (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v63 + 32LL))(v63, v30);
    }
  }
  v45 = 0;
  v31 = (const void **)Src[1];
  v32 = (const void **)Src[0];
  if ( Src[0] == Src[1] )
    goto LABEL_58;
  v33 = 8 * (((char *)Src[1] - (char *)Src[0]) >> 5);
  v34 = (wchar_t **)operator new[](v33, (const struct std::nothrow_t *)&std::nothrow);
  v45 = v34;
  if ( v34 )
  {
    memset_0(v34, 0, v33);
    v55[0] = Src;
    v55[1] = &v45;
    v56 = 1;
    v35 = 0;
    v32 = (const void **)Src[0];
    v31 = (const void **)Src[1];
    if ( Src[0] != Src[1] )
    {
      while ( 1 )
      {
        v36 = 2LL * (_QWORD)v32[2] + 2;
        v37 = (wchar_t *)operator new[](v36, (const struct std::nothrow_t *)&std::nothrow);
        v45[v35] = v37;
        v38 = v45[v35];
        if ( !v38 )
          break;
        if ( (unsigned __int64)v32[3] <= 7 )
          v39 = v32;
        else
          v39 = *v32;
        memcpy_0(v38, v39, v36);
        v35 = (unsigned int)(v35 + 1);
        v32 += 4;
        if ( v32 == v31 )
        {
          v31 = (const void **)Src[1];
          v32 = (const void **)Src[0];
          goto LABEL_58;
        }
      }
      v5 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC28,
        (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
        (const char *)0x8007000ELL,
        v41);
      v56 = 0;
      Microsoft::Diagnostics::UtcApiManager::GetCustomTraceList_::_54_::_lambda_4_::operator()(v55);
      goto LABEL_60;
    }
LABEL_58:
    *a2 = v45;
    v45 = 0;
    *a3 = ((char *)v31 - (char *)v32) >> 5;
    __1__unique_ptr___BY0A__WU__generic_delete___BY0A__WU__generic_deallocate__MP6AXPEAX_Z1_CoTaskMemFree__YAX0_ZPEAX_tlx___tlx___utl__QEAA_XZ(&pv);
    std::wstring::_Tidy_deallocate(lpFileName);
    std::vector<std::wstring>::_Tidy(Src);
    std::wstring::_Tidy_deallocate(&v53);
    std::unique_lock<std::recursive_timed_mutex>::~unique_lock<std::recursive_timed_mutex>(v48);
    return 0;
  }
  v5 = -2147024882;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xC0B,
    (unsigned int)"onecore\\base\\telemetry\\utc\\service\\engine\\utcapimanager.cpp",
    (const char *)0x8007000ELL,
    v41);
LABEL_60:
  __1__unique_ptr___BY0A__WU__generic_delete___BY0A__WU__generic_deallocate__MP6AXPEAX_Z1_CoTaskMemFree__YAX0_ZPEAX_tlx___tlx___utl__QEAA_XZ(&pv);
  std::wstring::_Tidy_deallocate(lpFileName);
  std::vector<std::wstring>::_Tidy(Src);
  std::wstring::_Tidy_deallocate(&v53);
LABEL_63:
  std::unique_lock<std::recursive_timed_mutex>::~unique_lock<std::recursive_timed_mutex>(v48);
  return v5;
}

```

## disassembly

```asm
0x180291460  push    rbp
0x180291462  push    rbx
0x180291463  push    rsi
0x180291464  push    rdi
0x180291465  push    r12
0x180291467  push    r14
0x180291469  push    r15
0x18029146b  lea     rbp, [rsp-120h]
0x180291473  sub     rsp, 220h
0x18029147a  mov     rax, cs:__security_cookie
0x180291481  xor     rax, rsp
0x180291484  mov     [rbp+150h+var_40], rax
0x18029148b  mov     r12, r8
0x18029148e  mov     r15, rdx
0x180291491  mov     qword ptr [rsp+250h+var_220], 0EA60h
0x18029149a  lea     rdx, [rcx+180h]
0x1802914a1  lea     r8, [rsp+250h+var_220]
0x1802914a6  lea     rcx, [rsp+250h+var_1E0]
0x1802914ab  call    ??$?0_JU?$ratio@$00$0DOI@@std@@@?$unique_lock@Vrecursive_timed_mutex@std@@@std@@QEAA@AEAVrecursive_timed_mutex@1@AEBV?$duration@_JU?$ratio@$00$0DOI@@std@@@chrono@1@@Z; std::unique_lock<std::recursive_timed_mutex>::unique_lock<std::recursive_timed_mutex>(std::recursive_timed_mutex &,std::chrono::duration<__int64,std::ratio<1,1000>> const &)
0x1802914b0  nop
0x1802914b1  cmp     [rsp+250h+var_1D8], 0
0x1802914b6  jnz     short loc_1802914C7
0x1802914b8  mov     ebx, 87C5102Bh
0x1802914bd  mov     edx, 0B9Dh
0x1802914c2  jmp     loc_180291B14
0x1802914c7  test    r15, r15
0x1802914ca  jz      loc_180291B0A
0x1802914d0  test    r12, r12
0x1802914d3  jz      loc_180291B0A
0x1802914d9  xorps   xmm0, xmm0
0x1802914dc  movups  [rbp+150h+var_168], xmm0
0x1802914e0  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1802914e8  movdqu  [rbp+150h+var_158], xmm1
0x1802914ed  xor     eax, eax
0x1802914ef  mov     word ptr [rbp+150h+var_168], ax
0x1802914f3  movdqu  xmmword ptr [rsp+250h+Src], xmm0
0x1802914f9  mov     [rsp+250h+var_1E8], rax
0x1802914fe  lea     rdx, off_1803853B0; "%DiagtrackStorageRoot%\\CustomTraceProf"...
0x180291505  lea     rcx, [rbp+150h+lpFileName]
0x180291509  call    ??$?0V?$basic_zstring_view@_W@wil@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV?$basic_zstring_view@_W@wil@@AEBV?$allocator@_W@1@@Z; std::wstring::wstring(wil::basic_zstring_view<wchar_t> const &,std::allocator<wchar_t> const &)
0x18029150e  nop
0x18029150f  xor     r8d, r8d
0x180291512  mov     dl, 1
0x180291514  lea     rcx, [rbp+150h+lpFileName]; lpSrc
0x180291518  call    ?ExpandEnvironmentStringsInString@String@Utils@Diagnostics@Microsoft@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_NPEAX@Z; Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(std::wstring &,bool,void *)
0x18029151d  lea     rcx, [rbp+150h+lpFileName]
0x180291521  cmp     [rbp+150h+var_170], 7
0x180291526  cmova   rcx, [rbp+150h+lpFileName]; lpFileName
0x18029152b  call    cs:__imp_GetFileAttributesW
0x180291531  mov     sil, 10h
0x180291534  mov     r14d, 2000h
0x18029153a  lea     rdi, dword_1804543B0
0x180291541  cmp     eax, 0FFFFFFFFh
0x180291544  jz      loc_180291624
0x18029154a  test    sil, al
0x18029154d  jz      loc_180291624
0x180291553  lea     rdx, [rbp+150h+lpFileName]
0x180291557  lea     rcx, [rbp+150h+var_168]
0x18029155b  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180291560  mov     eax, cs:dword_1804543B0
0x180291566  cmp     eax, 4
0x180291569  jbe     short loc_1802915A6
0x18029156b  mov     edx, r14d
0x18029156e  mov     rcx, rdi
0x180291571  call    _tlgKeywordOn
0x180291576  test    al, al
0x180291578  jz      short loc_1802915A6
0x18029157a  lea     rax, [rbp+150h+var_168]
0x18029157e  cmp     qword ptr [rbp+150h+var_158+8], 7
0x180291583  cmova   rax, qword ptr [rbp+150h+var_168]
0x180291588  mov     qword ptr [rsp+250h+var_220], rax
0x18029158d  lea     rax, [rsp+250h+var_220]
0x180291592  mov     qword ptr [rsp+250h+var_230], rax; int
0x180291597  lea     rdx, byte_1803EBF07
0x18029159e  mov     rcx, rdi
0x1802915a1  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x1802915a6  mov     [rbp+150h+var_190], 0
0x1802915aa  lea     rax, off_18037E3A0
0x1802915b1  mov     [rbp+150h+var_100], rax
0x1802915b5  lea     rax, [rsp+250h+Src]
0x1802915ba  mov     [rbp+150h+var_F8], rax
0x1802915be  lea     rax, [rbp+150h+var_100]
0x1802915c2  mov     [rbp+150h+var_C8], rax
0x1802915c9  movups  xmm0, xmmword ptr cs:?k_customProfilesFilePattern@UtcApiManager@Diagnostics@Microsoft@@0V?$basic_zstring_view@_W@wil@@B; wil::basic_zstring_view<wchar_t> const Microsoft::Diagnostics::UtcApiManager::k_customProfilesFilePattern
0x1802915d0  movdqu  xmmword ptr [rsp+250h+var_220], xmm0
0x1802915d6  lea     rdx, [rbp+150h+var_148]
0x1802915da  lea     rcx, [rbp+150h+var_168]
0x1802915de  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1802915e3  movups  xmm0, xmmword ptr [rax]
0x1802915e6  movdqu  [rbp+150h+var_120], xmm0
0x1802915eb  lea     r9, [rbp+150h+var_1D0]
0x1802915ef  lea     r8, [rbp+150h+var_100]
0x1802915f3  lea     rdx, [rsp+250h+var_220]
0x1802915f8  lea     rcx, [rbp+150h+var_120]
0x1802915fc  call    ?DoForEachFileInPattern@FileSystem@Utils@Diagnostics@Microsoft@@SAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEBV?$function@$$A6A_NAEBVAutoFindFile@@@Z@6@V?$optional@V?$function@$$A6A_NJ@Z@std@@@6@@Z; Microsoft::Diagnostics::Utils::FileSystem::DoForEachFileInPattern(std::wstring_view,std::wstring_view,std::function<bool (AutoFindFile const &)> const &,std::optional<std::function<bool (long)>>)
0x180291601  nop
0x180291602  mov     rcx, [rbp+150h+var_C8]
0x180291609  test    rcx, rcx
0x18029160c  jz      short loc_180291624
0x18029160e  mov     rax, [rcx]
0x180291611  lea     rdx, [rbp+150h+var_100]
0x180291615  cmp     rcx, rdx
0x180291618  setnz   dl
0x18029161b  mov     rax, [rax+20h]
0x18029161f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180291624  mov     [rsp+250h+pv], 0
0x18029162d  call    IsSHGetKnownFolderPathPresent
0x180291632  test    al, al
0x180291634  jz      short loc_18029169F
0x180291636  mov     rbx, [rsp+250h+pv]
0x18029163b  test    rbx, rbx
0x18029163e  jz      short loc_18029165D
0x180291640  lea     rcx, [rsp+250h+var_220]; this
0x180291645  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18029164a  mov     rcx, rbx; pv
0x18029164d  call    cs:__imp_CoTaskMemFree
0x180291653  lea     rcx, [rsp+250h+var_220]; this
0x180291658  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18029165d  mov     [rsp+250h+pv], 0
0x180291666  lea     r9, [rsp+250h+pv]; ppszPath
0x18029166b  xor     r8d, r8d; hToken
0x18029166e  mov     edx, 8000h; dwFlags
0x180291673  lea     rcx, FOLDERID_PublicDocuments; rfid
0x18029167a  call    cs:__imp_SHGetKnownFolderPath
0x180291680  mov     rcx, [rbp+158h]; this
0x180291687  test    eax, eax
0x180291689  jns     short loc_18029169F
0x18029168b  mov     r9d, eax; char *
0x18029168e  lea     r8, aOnecoreBaseTel_269; "onecore\\base\\telemetry\\utc\\service"...
0x180291695  mov     edx, 0BC3h; void *
0x18029169a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18029169f  mov     rdx, [rsp+250h+pv]
0x1802916a4  test    rdx, rdx
0x1802916a7  jz      short loc_1802916E7
0x1802916a9  lea     rcx, [rbp+150h+var_120]
0x1802916ad  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1802916b2  nop
0x1802916b3  lea     r8, aFeedbackhubCus; "\\FeedbackHub\\CustomTraceProfiles"
0x1802916ba  mov     rdx, rax
0x1802916bd  lea     rcx, [rbp+150h+var_148]
0x1802916c1  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@$$QEAV10@QEB_W@Z; std::operator+<wchar_t>(std::wstring &&,wchar_t const * const)
0x1802916c6  mov     rdx, rax
0x1802916c9  lea     rcx, [rbp+150h+lpFileName]
0x1802916cd  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1802916d2  lea     rcx, [rbp+150h+var_148]
0x1802916d6  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1802916db  nop
0x1802916dc  lea     rcx, [rbp+150h+var_120]
0x1802916e0  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1802916e5  jmp     short loc_18029170B
0x1802916e7  mov     r8d, 32h ; '2'
0x1802916ed  mov     rdx, cs:off_1803853A0; "%Public%\\Documents\\FeedbackHub\\Custo"...
0x1802916f4  lea     rcx, [rbp+150h+lpFileName]
0x1802916f8  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x1802916fd  xor     r8d, r8d
0x180291700  mov     dl, 1
0x180291702  lea     rcx, [rbp+150h+lpFileName]; lpSrc
0x180291706  call    ?ExpandEnvironmentStringsInString@String@Utils@Diagnostics@Microsoft@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_NPEAX@Z; Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(std::wstring &,bool,void *)
0x18029170b  lea     rcx, [rbp+150h+lpFileName]
0x18029170f  cmp     [rbp+150h+var_170], 7
0x180291714  cmova   rcx, [rbp+150h+lpFileName]; lpFileName
0x180291719  call    cs:__imp_GetFileAttributesW
0x18029171f  cmp     eax, 0FFFFFFFFh
0x180291722  jz      loc_180291811
0x180291728  test    sil, al
0x18029172b  jz      loc_180291811
0x180291731  lea     rdx, [rbp+150h+lpFileName]
0x180291735  lea     rcx, [rbp+150h+var_168]
0x180291739  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18029173e  mov     eax, cs:dword_1804543B0
0x180291744  cmp     eax, 4
0x180291747  jbe     short loc_180291784
0x180291749  mov     rdx, r14
0x18029174c  mov     rcx, rdi
0x18029174f  call    _tlgKeywordOn
0x180291754  test    al, al
0x180291756  jz      short loc_180291784
0x180291758  lea     rax, [rbp+150h+var_168]
0x18029175c  cmp     qword ptr [rbp+150h+var_158+8], 7
0x180291761  cmova   rax, qword ptr [rbp+150h+var_168]
0x180291766  mov     qword ptr [rsp+250h+var_220], rax
0x18029176b  lea     rax, [rsp+250h+var_220]
0x180291770  mov     qword ptr [rsp+250h+var_230], rax
0x180291775  lea     rdx, dword_1803EBEB4
0x18029177c  mov     rcx, rdi
0x18029177f  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x180291784  mov     [rbp+150h+var_190], 0
0x180291788  lea     rax, off_18037E3D0
0x18029178f  mov     [rbp+150h+var_C0], rax
0x180291796  lea     rax, [rsp+250h+Src]
0x18029179b  mov     [rbp+150h+var_B8], rax
0x1802917a2  lea     rax, [rbp+150h+var_C0]
0x1802917a9  mov     [rbp+150h+var_88], rax
0x1802917b0  movups  xmm0, xmmword ptr cs:?k_customProfilesFilePattern@UtcApiManager@Diagnostics@Microsoft@@0V?$basic_zstring_view@_W@wil@@B; wil::basic_zstring_view<wchar_t> const Microsoft::Diagnostics::UtcApiManager::k_customProfilesFilePattern
0x1802917b7  movdqu  [rbp+150h+var_120], xmm0
0x1802917bc  lea     rdx, [rbp+150h+var_148]
0x1802917c0  lea     rcx, [rbp+150h+var_168]
0x1802917c4  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x1802917c9  movups  xmm0, xmmword ptr [rax]
0x1802917cc  movdqu  xmmword ptr [rsp+250h+var_220], xmm0
0x1802917d2  lea     r9, [rbp+150h+var_1D0]
0x1802917d6  lea     r8, [rbp+150h+var_C0]
0x1802917dd  lea     rdx, [rbp+150h+var_120]
0x1802917e1  lea     rcx, [rsp+250h+var_220]
0x1802917e6  call    ?DoForEachFileInPattern@FileSystem@Utils@Diagnostics@Microsoft@@SAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEBV?$function@$$A6A_NAEBVAutoFindFile@@@Z@6@V?$optional@V?$function@$$A6A_NJ@Z@std@@@6@@Z; Microsoft::Diagnostics::Utils::FileSystem::DoForEachFileInPattern(std::wstring_view,std::wstring_view,std::function<bool (AutoFindFile const &)> const &,std::optional<std::function<bool (long)>>)
0x1802917eb  nop
0x1802917ec  mov     rcx, [rbp+150h+var_88]
0x1802917f3  test    rcx, rcx
0x1802917f6  jz      short loc_180291811
0x1802917f8  mov     rax, [rcx]
0x1802917fb  lea     rdx, [rbp+150h+var_C0]
0x180291802  cmp     rcx, rdx
0x180291805  setnz   dl
0x180291808  mov     rax, [rax+20h]
0x18029180c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180291811  lea     rdx, [rsp+250h+var_210]
0x180291816  call    ?ImpersonateRpcCaller@UtcApiManager@Diagnostics@Microsoft@@AEAA@XZ; Microsoft::Diagnostics::UtcApiManager::ImpersonateRpcCaller(void)
0x18029181b  nop
0x18029181c  mov     r8d, 37h ; '7'
0x180291822  mov     rdx, cs:off_180385380; "%USERPROFILE%\\Documents\\FeedbackHub\\"...
0x180291829  lea     rcx, [rbp+150h+lpFileName]
0x18029182d  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x180291832  xor     r8d, r8d
0x180291835  mov     dl, 1
0x180291837  lea     rcx, [rbp+150h+lpFileName]; lpSrc
0x18029183b  call    ?ExpandEnvironmentStringsInString@String@Utils@Diagnostics@Microsoft@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@_NPEAX@Z; Microsoft::Diagnostics::Utils::String::ExpandEnvironmentStringsInString(std::wstring &,bool,void *)
0x180291840  nop
0x180291841  cmp     [rsp+250h+var_20F], 0
0x180291846  jz      short loc_180291856
0x180291848  call    cs:__imp_RpcRevertToSelf
0x18029184e  test    eax, eax
0x180291850  jnz     loc_180291B58
0x180291856  lea     rcx, [rbp+150h+lpFileName]
0x18029185a  cmp     [rbp+150h+var_170], 7
0x18029185f  cmova   rcx, [rbp+150h+lpFileName]; lpFileName
0x180291864  call    cs:__imp_GetFileAttributesW
0x18029186a  cmp     eax, 0FFFFFFFFh
0x18029186d  jz      loc_18029195C
0x180291873  test    sil, al
0x180291876  jz      loc_18029195C
0x18029187c  lea     rdx, [rbp+150h+lpFileName]
0x180291880  lea     rcx, [rbp+150h+var_168]
0x180291884  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180291889  mov     eax, cs:dword_1804543B0
0x18029188f  cmp     eax, 4
0x180291892  jbe     short loc_1802918CF
0x180291894  mov     rdx, r14
0x180291897  mov     rcx, rdi
0x18029189a  call    _tlgKeywordOn
0x18029189f  test    al, al
0x1802918a1  jz      short loc_1802918CF
0x1802918a3  lea     rax, [rbp+150h+var_168]
0x1802918a7  cmp     qword ptr [rbp+150h+var_158+8], 7
0x1802918ac  cmova   rax, qword ptr [rbp+150h+var_168]
0x1802918b1  mov     qword ptr [rsp+250h+var_220], rax
0x1802918b6  lea     rax, [rsp+250h+var_220]
0x1802918bb  mov     qword ptr [rsp+250h+var_230], rax; int
0x1802918c0  lea     rdx, word_1803EBDEE
0x1802918c7  mov     rcx, rdi
0x1802918ca  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x1802918cf  mov     [rbp+150h+var_190], 0
0x1802918d3  lea     rax, off_18037E400
0x1802918da  mov     [rbp+150h+var_80], rax
0x1802918e1  lea     rax, [rsp+250h+Src]
0x1802918e6  mov     [rbp+150h+var_78], rax
0x1802918ed  lea     rax, [rbp+150h+var_80]
0x1802918f4  mov     [rbp+150h+var_48], rax
0x1802918fb  movups  xmm0, xmmword ptr cs:?k_customProfilesFilePattern@UtcApiManager@Diagnostics@Microsoft@@0V?$basic_zstring_view@_W@wil@@B; wil::basic_zstring_view<wchar_t> const Microsoft::Diagnostics::UtcApiManager::k_customProfilesFilePattern
0x180291902  movdqu  [rbp+150h+var_120], xmm0
0x180291907  lea     rdx, [rbp+150h+var_148]
0x18029190b  lea     rcx, [rbp+150h+var_168]
0x18029190f  call    ??B?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV?$basic_string_view@_WU?$char_traits@_W@std@@@1@XZ; std::wstring::operator std::wstring_view(void)
0x180291914  movups  xmm0, xmmword ptr [rax]
0x180291917  movdqu  xmmword ptr [rsp+250h+var_220], xmm0
0x18029191d  lea     r9, [rbp+150h+var_1D0]
0x180291921  lea     r8, [rbp+150h+var_80]
0x180291928  lea     rdx, [rbp+150h+var_120]
0x18029192c  lea     rcx, [rsp+250h+var_220]
0x180291931  call    ?DoForEachFileInPattern@FileSystem@Utils@Diagnostics@Microsoft@@SAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@0AEBV?$function@$$A6A_NAEBVAutoFindFile@@@Z@6@V?$optional@V?$function@$$A6A_NJ@Z@std@@@6@@Z; Microsoft::Diagnostics::Utils::FileSystem::DoForEachFileInPattern(std::wstring_view,std::wstring_view,std::function<bool (AutoFindFile const &)> const &,std::optional<std::function<bool (long)>>)
0x180291936  nop
0x180291937  mov     rcx, [rbp+150h+var_48]
0x18029193e  test    rcx, rcx
0x180291941  jz      short loc_18029195C
0x180291943  mov     rax, [rcx]
0x180291946  lea     rdx, [rbp+150h+var_80]
0x18029194d  cmp     rcx, rdx
0x180291950  setnz   dl
0x180291953  mov     rax, [rax+20h]
0x180291957  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18029195c  mov     [rsp+250h+var_200], 0
0x180291965  mov     rbx, [rsp+250h+Src+8]
0x18029196a  mov     rdi, [rsp+250h+Src]
0x18029196f  cmp     rdi, rbx
0x180291972  jz      loc_180291A5A
0x180291978  sub     rbx, rdi
0x18029197b  sar     rbx, 5
0x18029197f  shl     rbx, 3
0x180291983  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18029198a  mov     rcx, rbx; unsigned __int64
0x18029198d  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
  ... truncated ...
```
