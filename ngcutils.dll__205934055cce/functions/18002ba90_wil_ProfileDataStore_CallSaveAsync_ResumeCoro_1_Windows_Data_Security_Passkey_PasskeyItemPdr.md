# wil::ProfileDataStore::CallSaveAsync$_ResumeCoro$1_Windows::Data::Security::Passkey::PasskeyItemPdr_

- ea: `0x18002ba90`
- end: `0x18002c8c8`
- name: `wil::ProfileDataStore::CallSaveAsync$_ResumeCoro$1_Windows::Data::Security::Passkey::PasskeyItemPdr_`
- size: `3640`
- prototype: ``
- caller_count: `1`
- callee_count: `31`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18002e550`

## callees

- `0x180003080`
- `0x180003520`
- `0x1800060a4`
- `0x180007a5c`
- `0x18000ce74`
- `0x18000f7fc`
- `0x18001354c`
- `0x18001ae30`
- `0x18002ba90`
- `0x1800318c8`
- `0x1800378f4`
- `0x18003b304`
- `0x180042b40`
- `0x18004302c`
- `0x1800434d0`
- `0x18004478c`
- `0x180045734`
- `0x180045914`
- `0x1800461d4`
- `0x1800471b4`
- `0x180047e08`
- `0x180049038`
- `0x180049238`
- `0x18004a2d4`
- `0x18004ac3c`
- `0x18004ccf0`
- `0x18004cf2c`
- `0x18004d87c`
- `0x18004eaac`
- `0x18004ee8c`
- `0x180061010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18002c851`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18002c851`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002c142`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002c1cb`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002c142`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002c1cb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002bfea`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002bfea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bfd7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bfd7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002bfe2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002c4c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002c4ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002c68a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002c6b4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002bfe2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002c4c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002c4ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002c68a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002c6b4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18002bf7d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18002bf7d`

## pseudocode

```c
// Hidden C++ exception states: #wind=44 #try_helpers=1
void __fastcall wil::ProfileDataStore::CallSaveAsync__ResumeCoro_1_Windows::Data::Security::Passkey::PasskeyItemPdr_(
        __int64 a1)
{
  __int64 v1; // rsi
  __int64 v2; // r14
  __int64 v3; // r9
  __int64 v4; // r8
  __int16 *v5; // rdx
  _QWORD *v6; // r12
  volatile signed __int32 **v7; // r15
  __int64 v8; // rdx
  signed __int32 v9; // eax
  signed __int32 v10; // ett
  volatile signed __int32 *v11; // r14
  __int64 v12; // rax
  __int128 v13; // xmm0
  __int128 v14; // xmm0
  __int64 v15; // rdx
  __int64 v16; // r8
  volatile signed __int32 *v17; // rdi
  __int64 v18; // rdx
  char v19; // al
  int v20; // eax
  int v21; // ebx
  __int64 v22; // r14
  __int64 v23; // r14
  bool v24; // zf
  char v25; // r14
  int v26; // eax
  __int64 v27; // rcx
  __int64 v28; // rcx
  __int64 v29; // r13
  int v30; // ebx
  const WCHAR *v31; // r14
  __int64 v32; // rdx
  __int64 v33; // r8
  HSTRING *v34; // rbx
  HRESULT v35; // eax
  HSTRING v36; // r15
  HSTRING *v37; // r14
  HSTRING v38; // r12
  DWORD LastError; // ebx
  __int64 *v40; // rbx
  __int64 v41; // rax
  __int64 v42; // r9
  int v43; // eax
  __int64 v44; // rax
  __int64 *v45; // rbx
  _QWORD *View; // rax
  _QWORD *v47; // rax
  _QWORD *v48; // rcx
  __int64 v49; // rdx
  __int64 v50; // rax
  __int64 *v51; // r12
  __int64 v52; // rdx
  __int64 v53; // rcx
  __int64 v54; // rax
  __int64 v55; // r8
  __int64 v56; // r8
  __int64 v57; // rdx
  __int64 v58; // r8
  __int64 v59; // rdx
  __int64 v60; // r8
  __int64 *v61; // rax
  __int64 v62; // rdx
  __int64 v63; // r8
  unsigned int v64; // eax
  const struct winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult *v65; // rax
  __int64 v66; // rax
  __int64 v67; // rdx
  __int64 v68; // r8
  __int64 *v69; // rdx
  void (*v70)(void); // rax
  __int64 **v71; // rdx
  void (*v72)(void); // rax
  __int64 *v73; // rdx
  void (*v74)(void); // rax
  void (*v75)(void); // rax
  void (*v76)(void); // rax
  void (*v77)(void); // rax
  volatile signed __int32 *v78; // rdi
  __int64 v79; // rbx
  int v80; // ecx
  __int16 v81; // ax
  int v82; // ecx
  __int16 v83; // ax
  __int64 v84; // rdx
  __int64 v85; // r8
  __int64 v86; // [rsp+0h] [rbp-388h] BYREF
  int v87[2]; // [rsp+20h] [rbp-368h]
  char *v88; // [rsp+28h] [rbp-360h]
  __int64 v89; // [rsp+30h] [rbp-358h]
  int v90; // [rsp+50h] [rbp-338h]
  __int64 v91; // [rsp+58h] [rbp-330h]
  __int64 *v92; // [rsp+60h] [rbp-328h]
  __int64 v93; // [rsp+68h] [rbp-320h]
  __int64 v94; // [rsp+70h] [rbp-318h]
  char *v95; // [rsp+78h] [rbp-310h]
  HSTRING v96; // [rsp+80h] [rbp-308h]
  __int64 v97; // [rsp+88h] [rbp-300h]
  _QWORD *v98; // [rsp+90h] [rbp-2F8h]
  __int16 v99; // [rsp+98h] [rbp-2F0h]
  __int64 CloudStore; // [rsp+A0h] [rbp-2E8h]
  __int64 v101; // [rsp+A8h] [rbp-2E0h]
  __int64 v102; // [rsp+B0h] [rbp-2D8h]
  volatile signed __int32 **v103; // [rsp+B8h] [rbp-2D0h]
  volatile signed __int32 *v104; // [rsp+C8h] [rbp-2C0h]
  __int64 *v105; // [rsp+D0h] [rbp-2B8h]
  __int64 v106; // [rsp+D8h] [rbp-2B0h]
  __int64 *v107; // [rsp+E0h] [rbp-2A8h]
  char **v108; // [rsp+E8h] [rbp-2A0h]
  HSTRING *v109; // [rsp+F0h] [rbp-298h]
  __int64 **v110; // [rsp+F8h] [rbp-290h]
  __int64 *v111; // [rsp+100h] [rbp-288h]
  __int64 v112; // [rsp+108h] [rbp-280h]
  __int64 v113; // [rsp+110h] [rbp-278h]
  __int64 *v114; // [rsp+118h] [rbp-270h]
  __int64 *v115; // [rsp+120h] [rbp-268h]
  int v116; // [rsp+128h] [rbp-260h]
  _QWORD *v117; // [rsp+130h] [rbp-258h]
  HSTRING *v121; // [rsp+150h] [rbp-238h]
  HSTRING v122; // [rsp+158h] [rbp-230h]
  __int64 v124; // [rsp+16Ah] [rbp-21Eh]
  int v125; // [rsp+172h] [rbp-216h]
  __int16 v126; // [rsp+176h] [rbp-212h]
  __int64 v127; // [rsp+188h] [rbp-200h]
  __int64 v128; // [rsp+198h] [rbp-1F0h]
  unsigned __int64 v129; // [rsp+1A0h] [rbp-1E8h]
  __int64 v130; // [rsp+1A8h] [rbp-1E0h]
  int v131; // [rsp+1B0h] [rbp-1D8h]
  int v132; // [rsp+1B4h] [rbp-1D4h]
  __int128 v133; // [rsp+1B8h] [rbp-1D0h]
  __int128 v134; // [rsp+1C8h] [rbp-1C0h]
  __int128 v135; // [rsp+1E0h] [rbp-1A8h]
  __int128 v136; // [rsp+1F0h] [rbp-198h]
  const WCHAR *v137; // [rsp+200h] [rbp-188h]
  unsigned __int64 v138; // [rsp+218h] [rbp-170h]
  __int64 v139; // [rsp+220h] [rbp-168h]
  int v140; // [rsp+228h] [rbp-160h]
  int v141; // [rsp+22Ch] [rbp-15Ch]
  wil::details::in1diag3 *retaddr; // [rsp+388h] [rbp+0h]

  v1 = a1;
  v97 = a1;
  v2 = a1 + 8;
  v94 = a1 + 8;
  v99 = *(_WORD *)(a1 + 8);
  v3 = 1;
  v4 = 4;
  if ( (unsigned __int16)(v99 + 1) > 4u )
  {
LABEL_149:
    __debugbreak();
  }
  else
  {
    v102 = a1 + 8;
    v5 = &_ImageBase;
    switch ( v99 )
    {
      case -1:
      case 1:
      case 3:
        if ( *(_QWORD *)(a1 - 16) && wil::details::coro::g_pfnDestroyRestrictedErrorInformation )
        {
          wil::details::coro::g_pfnDestroyRestrictedErrorInformation();
          *(_QWORD *)(v1 - 16) = 0;
        }
        if ( *(_DWORD *)(v1 - 80) == 1 )
        {
          std::wstring::~wstring(v1 - 56, v5, v4);
        }
        else if ( *(_DWORD *)(v1 - 80) == 2 )
        {
          __ExceptionPtrDestroy((void *)(v1 - 72));
        }
        `wil::ProfileDataStore::CallSaveAsync<Windows::Data::Security::Passkey::RecoveryItemPdr>'::`18'::_parameters_::~_parameters_(v2 + 768);
        if ( *(_WORD *)(v1 + 10) )
          operator delete((void *)(v1 - 96), 0x3C0u);
        return;
      case 0:
        goto LABEL_149;
      case 2:
        *(_DWORD *)(a1 + 752) = 0;
        v98 = *(_QWORD **)(a1 + 776);
        v6 = v98;
        *(_QWORD *)(a1 + 16) = 0;
        v7 = (volatile signed __int32 **)(a1 + 24);
        *(_QWORD *)(a1 + 24) = 0;
        v8 = v6[1];
        if ( !v8 )
          goto LABEL_138;
        v9 = *(_DWORD *)(v8 + 8);
        do
        {
          if ( !v9 )
LABEL_138:
            std::_Throw_bad_weak_ptr();
          v10 = v9;
          v9 = _InterlockedCompareExchange((volatile signed __int32 *)(v8 + 8), v9 + 1, v9);
        }
        while ( v10 != v9 );
        v103 = (volatile signed __int32 **)(a1 + 24);
        *(_QWORD *)(a1 + 16) = *v6;
        v11 = (volatile signed __int32 *)v6[1];
        *v7 = v11;
        *(_DWORD *)(a1 + 752) = 4;
        v12 = *(_QWORD *)(a1 + 848);
        if ( v12 && *(_DWORD *)(v12 + 16) )
        {
          *(_OWORD *)(a1 + 88) = 0;
          *(_QWORD *)(a1 + 104) = 0;
          *(_QWORD *)(a1 + 112) = 7;
          *(_WORD *)(a1 + 88) = 0;
          *(_QWORD *)(a1 + 32) = 0;
          *(_DWORD *)(a1 + 40) = 0;
          *(_DWORD *)(a1 + 44) = -2147023673;
          v135 = *(_OWORD *)(a1 + 88);
          v136 = *(_OWORD *)(a1 + 104);
          v13 = v136;
          *(_OWORD *)(a1 + 48) = v135;
          *(_OWORD *)(a1 + 64) = v13;
          *(_QWORD *)(a1 + 104) = 0;
          *(_QWORD *)(a1 + 112) = 7;
          *(_WORD *)(a1 + 88) = 0;
          *(_QWORD *)(a1 + 80) = 0;
          v130 = *(_QWORD *)(a1 + 32);
          *(_QWORD *)(a1 - 72) = v130;
          v131 = *(_DWORD *)(a1 + 40);
          *(_DWORD *)(a1 - 64) = v131;
          v132 = *(_DWORD *)(a1 + 44);
          *(_DWORD *)(a1 - 60) = v132;
          v133 = *(_OWORD *)(a1 + 48);
          v134 = *(_OWORD *)(a1 + 64);
          v14 = v134;
          *(_OWORD *)(a1 - 56) = v133;
          *(_OWORD *)(a1 - 40) = v14;
          *(_QWORD *)(a1 + 64) = 0;
          *(_QWORD *)(a1 + 72) = 7;
          *(_WORD *)(a1 + 48) = 0;
          *(_QWORD *)(a1 - 24) = 0;
          *(_DWORD *)(a1 - 80) = 1;
          std::wstring::~wstring(a1 + 48, 7, 4);
          std::wstring::~wstring(v1 + 88, v15, v16);
          v104 = v11;
          if ( v11 )
          {
            v17 = *v7;
            v104 = v17;
            if ( _InterlockedExchangeAdd(v17 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v17)(v17);
              if ( _InterlockedExchangeAdd(v17 + 3, 0xFFFFFFFF) == 1 )
LABEL_13:
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 8LL))(v17);
            }
          }
        }
        else
        {
          v18 = *(unsigned int *)(a1 + 824);
          if ( (*(_DWORD *)(a1 + 824) & 7) == 0
            || (v19 = 1, (((*(_DWORD *)(a1 + 824) & 7) - 1LL) & *(_DWORD *)(a1 + 824) & 7) == 0) )
          {
            v19 = 0;
          }
          if ( v19 )
            wil::details::in1diag3::_FailFast_Unexpected(
              retaddr,
              (void *)0x91F,
              (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil\\profiledatastore.h",
              (const char *)1);
          if ( (v18 & 1) != 0 )
          {
            v20 = 1;
          }
          else if ( (v18 & 2) != 0 )
          {
            v20 = 2;
          }
          else
          {
            v20 = 0;
            if ( (v18 & 4) != 0 )
              v20 = 4;
          }
          v21 = v20 | 0x20;
          if ( (v18 & 0x10) == 0 )
            v21 = v20;
          *(_DWORD *)(a1 + 120) = v21;
          v22 = *(_QWORD *)(a1 + 800);
          if ( *(_BYTE *)(v22 + 73) )
            goto LABEL_31;
          v23 = *(_QWORD *)(v22 + 64);
          *(_QWORD *)(a1 + 128) = v23;
          if ( v23 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 8LL))(v23);
            v3 = 1;
          }
          *(_DWORD *)(v1 + 752) = 5;
          v24 = v23 == 0;
          v25 = 0;
          if ( v24 )
LABEL_31:
            v25 = 1;
          v26 = *(_DWORD *)(v1 + 752);
          v90 = v26;
          if ( (v26 & 1) != 0 )
          {
            v90 = v26;
            *(_DWORD *)(v1 + 752) = v26 & 0xFFFFFFFE;
            v27 = *(_QWORD *)(v1 + 128);
            if ( v27 )
              (*(void (__fastcall **)(__int64, __int64, __int64, __int64))(*(_QWORD *)v27 + 16LL))(v27, v18, v4, 1);
          }
          if ( v25 )
          {
            v116 = v21;
            *(_DWORD *)(v1 + 120) = v21 | 8;
          }
          v115 = (__int64 *)(v1 + 136);
          wil::ProfileDataStore::Marshal<wil::ProfileDataItem<Windows::Data::Security::Passkey::PasskeyItemPdr>>(
            v1 + 136,
            *(_QWORD *)(v1 + 800),
            v4,
            v3);
          v28 = *(_QWORD *)(v1 + 136);
          v101 = v28;
          v114 = (__int64 *)(v1 + 144);
          *(_QWORD *)(v1 + 144) = v28;
          if ( v28 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 8LL))(v28);
          v29 = *(_QWORD *)(*(_QWORD *)(v1 + 800) + 64LL);
          v113 = v29;
          *(_QWORD *)(v1 + 152) = v29;
          if ( v29 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 8LL))(v29);
          *(_QWORD *)(v1 + 160) = 0;
          *(_QWORD *)(v1 + 168) = 0;
          *(_QWORD *)(v1 + 176) = 0;
          v111 = (__int64 *)(v1 + 184);
          winrt::single_threaded_vector<winrt::Windows::Internal::Storage::Cloud::CloudStoreBatchSaveItemData,std::allocator<winrt::Windows::Internal::Storage::Cloud::CloudStoreBatchSaveItemData>>(
            v1 + 184,
            v1 + 160);
          std::vector<winrt::Windows::Internal::Storage::Cloud::CloudStoreBatchSaveItemData>::~vector<winrt::Windows::Internal::Storage::Cloud::CloudStoreBatchSaveItemData>(v1 + 160);
          v110 = (__int64 **)(v1 + 192);
          wil::details::GetActivationFactoryPdr<Windows::Internal::Storage::Cloud::ICloudStoreBatchSaveItemDataFactory>(v1 + 192);
          std::wstring::wstring(v1 + 200, *(_QWORD *)(v1 + 784));
          v90 = *(_DWORD *)(v1 + 752);
          v30 = v90 | 8;
          *(_DWORD *)(v1 + 752) = v90 | 8;
          if ( *(_QWORD *)(v1 + 216) )
          {
            v31 = (const WCHAR *)(v1 + 232);
            std::wstring::wstring(v1 + 232, *(_QWORD *)(v1 + 784));
            v90 = v30 | 0x10;
            v30 |= 0x12u;
            *(_DWORD *)(v1 + 752) = v30;
            v138 = *(_QWORD *)(v1 + 256);
            if ( v138 > 7 )
            {
              v31 = *(const WCHAR **)v31;
              v137 = v31;
            }
          }
          else
          {
            v31 = L"default";
          }
          v109 = (HSTRING *)(v1 + 264);
          wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(
            (HSTRING *)(v1 + 264),
            v31);
          v90 = v30;
          if ( (v30 & 2) != 0 )
            std::wstring::~wstring(v1 + 232, v32, v33);
          std::wstring::~wstring(v1 + 200, v32, v33);
          v108 = (char **)(v1 + 272);
          *(_QWORD *)(v1 + 272) = 0;
          *(_QWORD *)(v1 + 280) = v1 + 272;
          v34 = (HSTRING *)(v1 + 288);
          *(_QWORD *)(v1 + 288) = 0;
          *(_BYTE *)(v1 + 296) = 1;
          v35 = WindowsDuplicateString(*(HSTRING *)(v1 + 832), (HSTRING *)(v1 + 288));
          if ( v35 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x70E,
              (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil\\profiledatastore.h",
              (const char *)(unsigned int)v35,
              v87[0]);
          if ( *(_BYTE *)(v1 + 296) )
          {
            v36 = *v34;
            v122 = *v34;
            v37 = *(HSTRING **)(v1 + 280);
            v121 = v37;
            v38 = *v37;
            if ( *v37 )
            {
              LastError = GetLastError();
              WindowsDeleteString(v38);
              SetLastError(LastError);
            }
            *v37 = v36;
            v6 = v98;
          }
          v40 = (__int64 *)(v1 + 304);
          v107 = (__int64 *)(v1 + 304);
          *(_QWORD *)(v1 + 304) = 0;
          v92 = *(__int64 **)(v1 + 192);
          v41 = *v92;
          v95 = *(char **)(v1 + 272);
          v42 = *(_QWORD *)(v1 + 816);
          v96 = *(HSTRING *)(v1 + 264);
          v93 = *(_QWORD *)(v1 + 144);
          v89 = v1 + 304;
          v88 = v95;
          *(_QWORD *)v87 = v93;
          v43 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, __int64, __int64))(v41 + 48))(v92, v96, v29, v42);
          if ( v43 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x717,
              (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil\\profiledatastore.h",
              (const char *)(unsigned int)v43,
              v87[0]);
          v91 = *v40;
          v44 = v91;
          *v40 = 0;
          v105 = (__int64 *)(v1 + 312);
          *(_QWORD *)(v1 + 312) = v44;
          winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Internal::Storage::Cloud::CloudStoreBatchSaveItemData>,winrt::Windows::Internal::Storage::Cloud::CloudStoreBatchSaveItemData>::Append(
            v1 + 184,
            v1 + 312);
          v45 = (__int64 *)(v1 + 320);
          v117 = (_QWORD *)(v1 + 320);
          *(_QWORD *)(v1 + 320) = 0;
          try
          {
            CloudStore = wil::details::SharedCloudStoreState::GetCloudStore(v6[2], v1 + 352);
            *(_QWORD *)(v1 + 360) = *(_QWORD *)(v1 + 840);
            View = (_QWORD *)winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Internal::Storage::Cloud::CloudStoreBatchSaveItemData>,winrt::Windows::Internal::Storage::Cloud::CloudStoreBatchSaveItemData>::GetView(
                               v1 + 184,
                               v1 + 408);
            *(_BYTE *)(v1 + 400) = 0;
            *(_QWORD *)(v1 + 392) = *View;
            v47 = (_QWORD *)wil::ProfileDataStore::GetTypeNameWideString<Windows::Data::Security::Passkey::PasskeyItemPdr>(v1 + 448);
            v48 = v47;
            v49 = v47[2];
            if ( v47[3] > 7u )
              v48 = (_QWORD *)*v47;
            if ( (_DWORD)v49 )
            {
              if ( *((_WORD *)v48 + (unsigned int)v49) )
                abort();
              v50 = v1 + 424;
              *(_DWORD *)(v1 + 424) = 1;
              *(_DWORD *)(v1 + 428) = v49;
              *(_QWORD *)(v1 + 440) = v48;
            }
            else
            {
              v50 = 0;
            }
            *(_QWORD *)(v1 + 416) = v50;
            v51 = (__int64 *)(v1 + 512);
            std::wstring::wstring(v1 + 512, *(_QWORD *)(v1 + 784) + 32LL);
            v52 = *(_QWORD *)(v1 + 528);
            v128 = v52;
            v129 = *(_QWORD *)(v1 + 536);
            if ( v129 <= 7 )
            {
              v53 = v1 + 512;
            }
            else
            {
              v53 = *v51;
              v127 = *v51;
            }
            if ( (_DWORD)v52 )
            {
              if ( *(_WORD *)(v53 + 2LL * (unsigned int)v52) )
                abort();
              v54 = v1 + 488;
              *(_DWORD *)(v1 + 488) = 1;
              *(_DWORD *)(v1 + 492) = v52;
              *(_QWORD *)(v1 + 504) = v53;
            }
            else
            {
              v54 = 0;
            }
            *(_QWORD *)(v1 + 480) = v54;
            v55 = *(_QWORD *)(v94 + 768);
            *(_QWORD *)(v1 + 544) = *(_QWORD *)(v55 + 40);
            v56 = winrt::impl::consume_Windows_Internal_Storage_Cloud_ICloudStore2<winrt::Windows::Internal::Storage::Cloud::CloudStore>::BatchSaveAsync(
                    CloudStore,
                    (int)v1 + 576,
                    (int)v55 + 32,
                    (int)v1 + 544,
                    v1 + 480,
                    v1 + 416,
                    v1 + 120,
                    v1 + 392,
                    v1 + 360);
            wil::details::AsyncOpWaiter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>>,winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>>::AsyncOpWaiter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>>,winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>>(
              v1 + 328,
              v1 + 848,
              v56);
            if ( *(_QWORD *)(v1 + 576) )
              winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v1 + 576);
            std::wstring::~wstring(v1 + 512, v57, v58);
            std::wstring::~wstring(v1 + 448, v59, v60);
            if ( *(_QWORD *)(v1 + 408) )
              winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v1 + 408);
            if ( *(_QWORD *)(v1 + 352) )
              winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v1 + 352);
            v61 = (__int64 *)wil::details::AsyncOpWaiter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>>,winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>>::WaitForResult(
                               v1 + 328,
                               v1 + 584);
            if ( v45 != v61 )
            {
              v62 = *v61;
              *v61 = 0;
              *v45 = v62;
            }
            CloudStore = *(_QWORD *)(v1 + 584);
            if ( CloudStore )
              winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v1 + 584);
            wil::details::AsyncOpWaiter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>,winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>::~AsyncOpWaiter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>,winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>(v1 + 328);
          }
          catch ( Concurrency::task_canceled )
          {
            v79 = v97;
            *(_OWORD *)(v97 + 648) = 0;
            *(_QWORD *)(v79 + 592) = 0;
            *(_DWORD *)(v79 + 600) = 0;
            *(_DWORD *)(v79 + 604) = -2147023673;
            *(_OWORD *)(v79 + 608) = 0;
            v124 = *(_QWORD *)(v79 + 650);
            v125 = *(_DWORD *)(v79 + 658);
            v80 = v125;
            v126 = *(_WORD *)(v79 + 662);
            v81 = v126;
            *(_QWORD *)(v79 + 610) = v124;
            *(_DWORD *)(v79 + 618) = v80;
            *(_WORD *)(v79 + 622) = v81;
            *(_QWORD *)(v79 + 664) = 0;
            *(_QWORD *)(v79 + 672) = 7;
            *(_WORD *)(v79 + 648) = 0;
            *(_QWORD *)(v79 + 640) = 0;
            v139 = *(_QWORD *)(v79 + 592);
            *(_QWORD *)(v79 - 72) = v139;
            v140 = *(_DWORD *)(v79 + 600);
            *(_DWORD *)(v79 - 64) = v140;
            v141 = *(_DWORD *)(v79 + 604);
            *(_DWORD *)(v79 - 60) = v141;
            *(_OWORD *)(v79 - 56) = 0;
            *(_QWORD *)(v79 - 40) = 0;
            *(_QWORD *)(v79 - 32) = 0;
            *(_WORD *)(v79 - 56) = 0;
            v124 = *(_QWORD *)(v79 + 650);
            v125 = *(_DWORD *)(v79 + 658);
            v82 = v125;
            v126 = *(_WORD *)(v79 + 662);
            v83 = v126;
            *(_QWORD *)(v79 - 54) = v124;
            *(_DWORD *)(v79 - 46) = v82;
            *(_WORD *)(v79 - 42) = v83;
            *(_QWORD *)(v79 - 40) = 0;
            *(_QWORD *)(v79 - 32) = 7;
            *(_QWORD *)(v79 + 624) = 0;
            *(_QWORD *)(v79 + 632) = 7;
            *(_WORD *)(v79 + 608) = 0;
            *(_QWORD *)(v79 - 24) = 0;
            *(_DWORD *)(v79 - 80) = 1;
            std::wstring::~wstring(v79 + 608, &v86, v63);
            std::wstring::~wstring(v79 + 648, v84, v85);
            v98 = (_QWORD *)*v117;
            if ( v98 )
              winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v117);
            v106 = *v105;
            if ( v106 )
              winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v105);
            v91 = *v107;
            if ( v91 )
            {
              v91 = *v107;
              v75 = *(void (**)(void))(*(_QWORD *)v91 + 16LL);
              v91 = *v107;
              v75();
            }
            v95 = *v108;
            if ( v95 )
            {
              v95 = *v108;
              WindowsDeleteString((HSTRING)v95);
            }
            v96 = *v109;
            if ( v96 )
            {
              v96 = *v109;
              WindowsDeleteString(v96);
            }
            v92 = *v110;
            if ( v92 )
            {
              v92 = *v110;
              v76 = *(void (**)(void))(*v92 + 16);
              v92 = *v110;
              v76();
            }
            v112 = *v111;
            if ( v112 )
              winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v111);
            if ( v113 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v113 + 16LL))(v113);
            v93 = *v114;
            if ( v93 )
            {
              v93 = *v114;
              v77 = *(void (**)(void))(*(_QWORD *)v93 + 16LL);
              v93 = *v114;
              v77();
            }
            v101 = *v115;
            if ( v101 )
              winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v115);
            v104 = *v103;
            if ( v104 )
            {
              v78 = *v103;
              v104 = v78;
              if ( _InterlockedExchangeAdd(v78 + 2, 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v78)(v78);
                if ( _InterlockedExchangeAdd(v78 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v78 + 8LL))(v78);
              }
            }
            v94 = v102;
            v1 = v97;
            goto LABEL_139;
          }
          v98 = (_QWORD *)*v45;
          if ( v98
            && !(unsigned int)winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::Storage::Cloud::CloudStoreData>,winrt::Windows::Internal::Storage::Cloud::CloudStoreData>::Size(v1 + 320) )
          {
            v64 = wil::verify_hresult<long>(13);
            wil::details::in1diag3::Throw_HrMsg(
              retaddr,
              (void *)0x73B,
              (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil\\profiledatastore.h",
              (const char *)v64,
              (int)"Expected exactly one result from the batch save operation.",
              v88);
          }
          if ( (unsigned int)winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::Storage::Cloud::CloudStoreData>,winrt::Windows::Internal::Storage::Cloud::CloudStoreData>::Size(v1 + 320) > 1 )
            wil::details::in1diag3::Log_HrMsg(
              retaddr,
              (void *)0x73F,
              (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil\\profiledatastore.h",
              (const char *)0xD,
              (int)"Too many results from the batch save operation.",
              v88);
          v65 = (const struct winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult *)winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>,winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>::GetAt(
                                                                                                 v1 + 320,
                                                                                                 v1 + 736,
                                                                                                 0);
          v66 = wil::ProfileDataStoreSaveResult::ProfileDataStoreSaveResult(
                  (wil::ProfileDataStoreSaveResult *)(v1 + 680),
                  v65);
          *(_QWORD *)(v1 - 72) = *(_QWORD *)v66;
          *(_DWORD *)(v1 - 64) = *(_DWORD *)(v66 + 8);
          *(_DWORD *)(v1 - 60) = *(_DWORD *)(v66 + 12);
          *(_OWORD *)(v1 - 56) = 0;
          *(_QWORD *)(v1 - 40) = 0;
          *(_QWORD *)(v1 - 32) = 0;
          *(_OWORD *)(v1 - 56) = *(_OWORD *)(v66 + 16);
          *(_OWORD *)(v1 - 40) = *(_OWORD *)(v66 + 32);
          *(_QWORD *)(v66 + 32) = 0;
          *(_QWORD *)(v66 + 40) = 7;
          *(_WORD *)(v66 + 16) = 0;
          *(_QWORD *)(v1 - 24) = *(_QWORD *)(v66 + 48);
          *(_DWORD *)(v1 - 80) = 1;
          std::wstring::~wstring(v1 + 696, v67, v68);
          v103 = *(volatile signed __int32 ***)(v1 + 736);
          if ( v103 )
            winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v1 + 736);
          v98 = (_QWORD *)*v45;
          if ( v98 )
            winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v1 + 320);
          v106 = *(_QWORD *)(v1 + 312);
          if ( v106 )
            winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v1 + 312);
          v69 = (__int64 *)(v1 + 304);
          v91 = *(_QWORD *)(v1 + 304);
          if ( v91 )
          {
            v91 = *v69;
            v70 = *(void (**)(void))(*(_QWORD *)v91 + 16LL);
            v91 = *v69;
            v70();
          }
          v95 = *(char **)(v1 + 272);
          if ( v95 )
          {
            v95 = *(char **)(v1 + 272);
            WindowsDeleteString((HSTRING)v95);
          }
          v96 = *(HSTRING *)(v1 + 264);
          if ( v96 )
          {
            v96 = *(HSTRING *)(v1 + 264);
            WindowsDeleteString(v96);
          }
          v71 = (__int64 **)(v1 + 192);
          v92 = *(__int64 **)(v1 + 192);
          if ( v92 )
          {
            v92 = *v71;
            v72 = *(void (**)(void))(*v92 + 16);
            v92 = *v71;
            v72();
          }
          v112 = *(_QWORD *)(v1 + 184);
          if ( v112 )
            winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v1 + 184);
          if ( v29 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
          v73 = (__int64 *)(v1 + 144);
          v93 = *(_QWORD *)(v1 + 144);
          if ( v93 )
          {
            v93 = *v73;
            v74 = *(void (**)(void))(*(_QWORD *)v93 + 16LL);
            v93 = *v73;
            v74();
          }
          v101 = *(_QWORD *)(v1 + 136);
          if ( v101 )
            winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v1 + 136);
          v104 = *(volatile signed __int32 **)(v1 + 24);
          if ( v104 )
          {
            v17 = *(volatile signed __int32 **)(v1 + 24);
            v104 = v17;
            if ( _InterlockedExchangeAdd(v17 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v17)(v17);
              if ( _InterlockedExchangeAdd(v17 + 3, 0xFFFFFFFF) == 1 )
                goto LABEL_13;
            }
          }
        }
LABEL_139:
        *(_QWORD *)(v1 + 744) = v1 - 96;
        *(_WORD *)v94 = 0;
        `wil::details::coro::promise_base<wil::ProfileDataStoreSaveResult>::final_suspend'::`2'::awaiter::await_suspend();
        break;
    }
  }
}

```

## disassembly

```asm
0x18002ba90  mov     r11, rsp
0x18002ba93  mov     [r11+10h], rbx
0x18002ba97  mov     [r11+18h], rsi
0x18002ba9b  mov     [r11+8], rcx
0x18002ba9f  push    rdi
0x18002baa0  push    r12
0x18002baa2  push    r13
0x18002baa4  push    r14
0x18002baa6  push    r15
0x18002baa8  sub     rsp, 360h
0x18002baaf  mov     rax, cs:__security_cookie
0x18002bab6  xor     rax, rsp
0x18002bab9  mov     [rsp+388h+var_38], rax
0x18002bac1  mov     rsi, rcx
0x18002bac4  mov     [rsp+388h+var_300], rcx
0x18002bacc  lea     r14, [rsi+8]
0x18002bad0  mov     [rsp+388h+var_318], r14
0x18002bad5  movzx   eax, word ptr [r14]
0x18002bad9  mov     [rsp+388h+var_2F0], ax
0x18002bae1  mov     r9d, 1
0x18002bae7  add     ax, r9w
0x18002baeb  lea     r8d, [r9+3]
0x18002baef  cmp     ax, r8w
0x18002baf3  ja      loc_18002C885; jumptable 000000018002BB16 case 1
0x18002baf9  mov     [rsp+388h+var_2D8], r14
0x18002bb01  movsx   rax, ax
0x18002bb05  lea     rdx, __ImageBase
0x18002bb0c  mov     ecx, ds:(jpt_18002BB16 - 180000000h)[rdx+rax*4]; switch 5 cases
0x18002bb13  add     rcx, rdx
0x18002bb16  jmp     rcx; switch jump
0x18002bb18  jmp     loc_18002C820; jumptable 000000018002BB16 case 4
0x18002bb1d  xor     edi, edi; jumptable 000000018002BB16 case 3
0x18002bb1f  mov     [rsi+2F0h], edi
0x18002bb25  mov     r12, [r14+300h]
0x18002bb2c  mov     [rsp+388h+var_2F8], r12
0x18002bb34  mov     [rsi+10h], rdi
0x18002bb38  lea     r15, [rsi+18h]
0x18002bb3c  mov     [r15], rdi
0x18002bb3f  mov     rdx, [r12+8]
0x18002bb44  test    rdx, rdx
0x18002bb47  jz      loc_18002C7E6
0x18002bb4d  mov     eax, [rdx+8]
0x18002bb50  jmp     short loc_18002BB5C
0x18002bb52  lea     ecx, [rax+1]
0x18002bb55  lock cmpxchg [rdx+8], ecx
0x18002bb5a  jz      short loc_18002BB65
0x18002bb5c  test    eax, eax
0x18002bb5e  jnz     short loc_18002BB52
0x18002bb60  jmp     loc_18002C7E6
0x18002bb65  mov     [rsp+388h+var_2D0], r15
0x18002bb6d  mov     rax, [r12]
0x18002bb71  mov     [rsi+10h], rax
0x18002bb75  mov     r14, [r12+8]
0x18002bb7a  mov     [r15], r14
0x18002bb7d  mov     [rsi+2F0h], r8d
0x18002bb84  mov     rax, [rsi+350h]
0x18002bb8b  test    rax, rax
0x18002bb8e  jz      loc_18002BCBB
0x18002bb94  mov     eax, [rax+10h]
0x18002bb97  nop
0x18002bb98  test    eax, eax
0x18002bb9a  jz      loc_18002BCBB
0x18002bba0  lea     rbx, [rsi+58h]
0x18002bba4  xorps   xmm0, xmm0
0x18002bba7  movups  xmmword ptr [rbx], xmm0
0x18002bbaa  mov     [rsi+68h], rdi
0x18002bbae  mov     edx, 7
0x18002bbb3  mov     [rsi+70h], rdx
0x18002bbb7  xor     eax, eax
0x18002bbb9  mov     [rbx], ax
0x18002bbbc  mov     [rsi+20h], rdi
0x18002bbc0  mov     [rsi+28h], edi
0x18002bbc3  mov     dword ptr [rsi+2Ch], 800704C7h
0x18002bbca  lea     rcx, [rsi+30h]
0x18002bbce  movups  xmm1, xmmword ptr [rbx]
0x18002bbd1  movups  [rsp+388h+var_1A8], xmm1
0x18002bbd9  movups  xmm0, xmmword ptr [rbx+10h]
0x18002bbdd  movups  [rsp+388h+var_198], xmm0
0x18002bbe5  movups  xmmword ptr [rcx], xmm1
0x18002bbe8  movups  xmmword ptr [rcx+10h], xmm0
0x18002bbec  mov     [rsi+68h], rdi
0x18002bbf0  mov     [rsi+70h], rdx
0x18002bbf4  mov     [rbx], ax
0x18002bbf7  mov     [rsi+50h], rdi
0x18002bbfb  mov     rax, [rsi+20h]
0x18002bbff  mov     [rsp+388h+var_1E0], rax
0x18002bc07  mov     [rsi-48h], rax
0x18002bc0b  mov     eax, [rsi+28h]
0x18002bc0e  mov     [rsp+388h+var_1D8], eax
0x18002bc15  mov     [rsi-40h], eax
0x18002bc18  mov     eax, [rsi+2Ch]
0x18002bc1b  mov     [rsp+388h+var_1D4], eax
0x18002bc22  mov     [rsi-3Ch], eax
0x18002bc25  movups  xmm1, xmmword ptr [rcx]
0x18002bc28  movups  [rsp+388h+var_1D0], xmm1
0x18002bc30  movups  xmm0, xmmword ptr [rcx+10h]
0x18002bc34  movups  [rsp+388h+var_1C0], xmm0
0x18002bc3c  movups  xmmword ptr [rsi-38h], xmm1
0x18002bc40  movups  xmmword ptr [rsi-28h], xmm0
0x18002bc44  mov     [rsi+40h], rdi
0x18002bc48  mov     [rsi+48h], rdx
0x18002bc4c  xor     eax, eax
0x18002bc4e  mov     [rcx], ax
0x18002bc51  mov     [rsi-18h], rdi
0x18002bc55  mov     [rsi-50h], r9d
0x18002bc59  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002bc5e  mov     rcx, rbx
0x18002bc61  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002bc66  nop
0x18002bc67  mov     [rsp+388h+var_2C0], r14
0x18002bc6f  test    r14, r14
0x18002bc72  jz      short loc_18002BCB6
0x18002bc74  mov     rdi, [r15]
0x18002bc77  mov     [rsp+388h+var_2C0], rdi
0x18002bc7f  or      ebx, 0FFFFFFFFh
0x18002bc82  mov     eax, ebx
0x18002bc84  lock xadd [rdi+8], eax
0x18002bc89  add     eax, ebx
0x18002bc8b  jnz     short loc_18002BCB6
0x18002bc8d  mov     rax, [rdi]
0x18002bc90  mov     rcx, rdi
0x18002bc93  mov     rax, [rax]
0x18002bc96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bc9b  mov     eax, ebx
0x18002bc9d  lock xadd [rdi+0Ch], eax
0x18002bca2  add     eax, ebx
0x18002bca4  jnz     short loc_18002BCB6
0x18002bca6  mov     rax, [rdi]
0x18002bca9  mov     rcx, rdi
0x18002bcac  mov     rax, [rax+8]
0x18002bcb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bcb5  nop
0x18002bcb6  jmp     loc_18002C801
0x18002bcbb  mov     edx, [rsi+338h]
0x18002bcc1  mov     eax, edx
0x18002bcc3  and     eax, 7
0x18002bcc6  jz      short loc_18002BCD5
0x18002bcc8  mov     ecx, eax
0x18002bcca  dec     rax
0x18002bccd  test    rcx, rax
0x18002bcd0  mov     al, r9b
0x18002bcd3  jnz     short loc_18002BCD8
0x18002bcd5  mov     al, dil
0x18002bcd8  mov     rcx, [rsp+388h]; this
0x18002bce0  test    al, al
0x18002bce2  jz      short loc_18002BCF6
0x18002bce4  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\sdk\\inc\\wil\\pr"...
0x18002bceb  mov     edx, 91Fh; void *
0x18002bcf0  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18002bcf6  test    r9d, edx
0x18002bcf9  jz      short loc_18002BD00
0x18002bcfb  mov     eax, r9d
0x18002bcfe  jmp     short loc_18002BD16
0x18002bd00  bt      edx, 1
0x18002bd04  jnb     short loc_18002BD0D
0x18002bd06  mov     eax, 2
0x18002bd0b  jmp     short loc_18002BD16
0x18002bd0d  mov     eax, edi
0x18002bd0f  test    r8d, edx
0x18002bd12  cmovnz  eax, r8d
0x18002bd16  mov     ebx, eax
0x18002bd18  or      ebx, 20h
0x18002bd1b  bt      edx, 4
0x18002bd1f  cmovnb  ebx, eax
0x18002bd22  mov     [rsi+78h], ebx
0x18002bd25  mov     r14, [rsi+320h]
0x18002bd2c  cmp     [r14+49h], dil
0x18002bd30  jnz     short loc_18002BD69
0x18002bd32  mov     r14, [r14+40h]
0x18002bd36  mov     [rsi+80h], r14
0x18002bd3d  test    r14, r14
0x18002bd40  jz      short loc_18002BD57
0x18002bd42  mov     rax, [r14]
0x18002bd45  mov     rcx, r14
0x18002bd48  mov     rax, [rax+8]
0x18002bd4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bd51  mov     r9d, 1
0x18002bd57  mov     dword ptr [rsi+2F0h], 5
0x18002bd61  test    r14, r14
0x18002bd64  mov     r14b, dil
0x18002bd67  jnz     short loc_18002BD6C
0x18002bd69  mov     r14b, r9b
0x18002bd6c  mov     eax, [rsi+2F0h]
0x18002bd72  mov     [rsp+388h+var_338], eax
0x18002bd76  test    r9d, eax
0x18002bd79  jz      short loc_18002BDA1
0x18002bd7b  mov     [rsp+388h+var_338], eax
0x18002bd7f  and     eax, 0FFFFFFFEh
0x18002bd82  mov     [rsi+2F0h], eax
0x18002bd88  mov     rcx, [rsi+80h]
0x18002bd8f  test    rcx, rcx
0x18002bd92  jz      short loc_18002BDA1
0x18002bd94  mov     rax, [rcx]
0x18002bd97  mov     rax, [rax+10h]
0x18002bd9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bda0  nop
0x18002bda1  test    r14b, r14b
0x18002bda4  jz      short loc_18002BDB3
0x18002bda6  mov     [rsp+388h+var_260], ebx
0x18002bdad  or      ebx, 8
0x18002bdb0  mov     [rsi+78h], ebx
0x18002bdb3  lea     rbx, [rsi+88h]
0x18002bdba  mov     [rsp+388h+var_268], rbx
0x18002bdc2  mov     rdx, [rsi+320h]
0x18002bdc9  mov     rcx, rbx
0x18002bdcc  call    ??$Marshal@V?$ProfileDataItem@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@wil@@@ProfileDataStore@wil@@CA?AUIBuffer@Streams@Storage@Windows@winrt@@AEBV?$ProfileDataItem@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@1@@Z; wil::ProfileDataStore::Marshal<wil::ProfileDataItem<Windows::Data::Security::Passkey::PasskeyItemPdr>>(wil::ProfileDataItem<Windows::Data::Security::Passkey::PasskeyItemPdr> const &)
0x18002bdd1  nop
0x18002bdd2  mov     rcx, [rbx]
0x18002bdd5  mov     [rsp+388h+var_2E0], rcx
0x18002bddd  lea     rax, [rsi+90h]
0x18002bde4  mov     [rsp+388h+var_270], rax
0x18002bdec  mov     [rax], rcx
0x18002bdef  test    rcx, rcx
0x18002bdf2  jz      short loc_18002BE00
0x18002bdf4  mov     rax, [rcx]
0x18002bdf7  mov     rax, [rax+8]
0x18002bdfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002be00  mov     rax, [rsi+320h]
0x18002be07  mov     r13, [rax+40h]
0x18002be0b  mov     [rsp+388h+var_278], r13
0x18002be13  mov     [rsi+98h], r13
0x18002be1a  test    r13, r13
0x18002be1d  jz      short loc_18002BE30
0x18002be1f  mov     rax, [r13+0]
0x18002be23  mov     rcx, r13
0x18002be26  mov     rax, [rax+8]
0x18002be2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002be2f  nop
0x18002be30  lea     rbx, [rsi+0A0h]
0x18002be37  mov     [rbx], rdi
0x18002be3a  mov     [rsi+0A8h], rdi
0x18002be41  mov     [rsi+0B0h], rdi
0x18002be48  lea     rax, [rsi+0B8h]
0x18002be4f  mov     [rsp+388h+var_288], rax
0x18002be57  mov     rdx, rbx
0x18002be5a  mov     rcx, rax
0x18002be5d  call    ??$single_threaded_vector@UCloudStoreBatchSaveItemData@Cloud@Storage@Internal@Windows@winrt@@V?$allocator@UCloudStoreBatchSaveItemData@Cloud@Storage@Internal@Windows@winrt@@@std@@@winrt@@YA?AU?$IVector@UCloudStoreBatchSaveItemData@Cloud@Storage@Internal@Windows@winrt@@@Collections@Foundation@Windows@0@$$QEAV?$vector@UCloudStoreBatchSaveItemData@Cloud@Storage@Internal@Windows@winrt@@V?$allocator@UCloudStoreBatchSaveItemData@Cloud@Storage@Internal@Windows@winrt@@@std@@@std@@@Z; winrt::single_threaded_vector<winrt::Windows::Internal::Storage::Cloud::CloudStoreBatchSaveItemData,std::allocator<winrt::Windows::Internal::Storage::Cloud::CloudStoreBatchSaveItemData>>(std::vector<winrt::Windows::Internal::Storage::Cloud::CloudStoreBatchSaveItemData> &&)
0x18002be62  nop
0x18002be63  mov     rcx, rbx
0x18002be66  call    ??1?$vector@UCloudStoreBatchSaveItemData@Cloud@Storage@Internal@Windows@winrt@@V?$allocator@UCloudStoreBatchSaveItemData@Cloud@Storage@Internal@Windows@winrt@@@std@@@std@@QEAA@XZ; std::vector<winrt::Windows::Internal::Storage::Cloud::CloudStoreBatchSaveItemData>::~vector<winrt::Windows::Internal::Storage::Cloud::CloudStoreBatchSaveItemData>(void)
0x18002be6b  lea     rax, [rsi+0C0h]
0x18002be72  mov     [rsp+388h+var_290], rax
0x18002be7a  mov     rcx, rax
0x18002be7d  call    ??$GetActivationFactoryPdr@UICloudStoreBatchSaveItemDataFactory@Cloud@Storage@Internal@Windows@@@details@wil@@YA?AV?$com_ptr_t@UICloudStoreBatchSaveItemDataFactory@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@1@PEBG@Z; wil::details::GetActivationFactoryPdr<Windows::Internal::Storage::Cloud::ICloudStoreBatchSaveItemDataFactory>(ushort const *)
0x18002be82  nop
0x18002be83  lea     r15, [rsi+0C8h]
0x18002be8a  mov     rdx, [rsi+310h]
0x18002be91  mov     rcx, r15
0x18002be94  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002be99  mov     ebx, [rsi+2F0h]
0x18002be9f  mov     [rsp+388h+var_338], ebx
0x18002bea3  or      ebx, 8
0x18002bea6  mov     [rsi+2F0h], ebx
0x18002beac  mov     rax, [rsi+0D8h]
0x18002beb3  mov     [rsp+388h+var_120], rax
0x18002bebb  test    rax, rax
0x18002bebe  jnz     short loc_18002BEC9
0x18002bec0  lea     r14, sourceString; "default"
0x18002bec7  jmp     short loc_18002BF0F
0x18002bec9  lea     r14, [rsi+0E8h]
0x18002bed0  mov     rdx, [rsi+310h]
0x18002bed7  mov     rcx, r14
0x18002beda  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002bedf  or      ebx, 10h
0x18002bee2  mov     [rsp+388h+var_338], ebx
0x18002bee6  or      ebx, 2
0x18002bee9  mov     [rsi+2F0h], ebx
0x18002beef  mov     rax, [rsi+100h]
0x18002bef6  mov     [rsp+388h+var_170], rax
0x18002befe  cmp     rax, 7
0x18002bf02  jbe     short loc_18002BF0F
0x18002bf04  mov     r14, [r14]
0x18002bf07  mov     [rsp+388h+var_188], r14
0x18002bf0f  lea     rax, [rsi+108h]
0x18002bf16  mov     [rsp+388h+var_298], rax
0x18002bf1e  mov     rdx, r14; sourceString
0x18002bf21  mov     rcx, rax; string
0x18002bf24  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18002bf29  nop
0x18002bf2a  mov     [rsp+388h+var_338], ebx
0x18002bf2e  bt      ebx, 1
0x18002bf32  jnb     short loc_18002BF41
0x18002bf34  lea     rcx, [rsi+0E8h]
0x18002bf3b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002bf40  nop
0x18002bf41  mov     rcx, r15
0x18002bf44  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002bf49  lea     rax, [rsi+110h]
0x18002bf50  mov     [rsp+388h+var_2A0], rax
0x18002bf58  mov     [rax], rdi
0x18002bf5b  mov     [rsi+118h], rax
0x18002bf62  lea     rbx, [rsi+120h]
0x18002bf69  mov     [rbx], rdi
0x18002bf6c  mov     byte ptr [rsi+128h], 1
0x18002bf73  mov     rdx, rbx; newString
0x18002bf76  mov     rcx, [rsi+340h]; string
0x18002bf7d  call    cs:__imp_WindowsDuplicateString
0x18002bf83  mov     rcx, [rsp+388h]; this
0x18002bf8b  test    eax, eax
0x18002bf8d  jns     short loc_18002BFA4
  ... truncated ...
```
