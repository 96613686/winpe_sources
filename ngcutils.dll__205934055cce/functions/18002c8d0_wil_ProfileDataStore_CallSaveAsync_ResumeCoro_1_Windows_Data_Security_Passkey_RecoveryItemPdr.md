# wil::ProfileDataStore::CallSaveAsync$_ResumeCoro$1_Windows::Data::Security::Passkey::RecoveryItemPdr_

- ea: `0x18002c8d0`
- end: `0x18002d708`
- name: `wil::ProfileDataStore::CallSaveAsync$_ResumeCoro$1_Windows::Data::Security::Passkey::RecoveryItemPdr_`
- size: `3640`
- prototype: ``
- caller_count: `1`
- callee_count: `31`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18002e7e4`

## callees

- `0x180003080`
- `0x180003520`
- `0x1800060a4`
- `0x180007a5c`
- `0x18000ce74`
- `0x18000f7fc`
- `0x18001354c`
- `0x18001ae30`
- `0x18002c8d0`
- `0x1800318c8`
- `0x180037a3c`
- `0x18003b3f0`
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

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18002d691`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18002d691`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002cf82`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002d00b`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002cf82`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002d00b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ce2a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ce2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ce17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ce17`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002ce22`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002d304`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002d32d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002d4ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002d4f4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002ce22`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002d304`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002d32d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002d4ca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002d4f4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18002cdbd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18002cdbd`

## pseudocode

```c
void __fastcall wil::ProfileDataStore::CallSaveAsync__ResumeCoro_1_Windows::Data::Security::Passkey::RecoveryItemPdr_(
        __int64 a1)
{
  __int64 v2; // r14
  __int64 v3; // r8
  __int16 *v4; // rdx
  _QWORD *v5; // r12
  volatile signed __int32 **v6; // r15
  __int64 v7; // rdx
  signed __int32 v8; // eax
  signed __int32 v9; // ett
  volatile signed __int32 *v10; // r14
  __int64 v11; // rax
  __int128 v12; // xmm0
  __int128 v13; // xmm0
  __int64 v14; // rdx
  __int64 v15; // r8
  volatile signed __int32 *v16; // rdi
  int v17; // edx
  char v18; // al
  int v19; // eax
  int v20; // ebx
  __int64 v21; // r14
  __int64 v22; // r14
  bool v23; // zf
  char v24; // r14
  int v25; // eax
  __int64 v26; // rcx
  __int64 v27; // rcx
  __int64 v28; // r13
  int v29; // ebx
  const WCHAR *v30; // r14
  __int64 v31; // rdx
  __int64 v32; // r8
  HRESULT v33; // eax
  HSTRING v34; // r15
  HSTRING *v35; // r14
  HSTRING v36; // r12
  DWORD LastError; // ebx
  __int64 *v38; // rbx
  int v39; // eax
  __int64 v40; // rax
  __int64 *v41; // rbx
  _QWORD *View; // rax
  _QWORD *v43; // rax
  _QWORD *v44; // rcx
  __int64 v45; // rdx
  __int64 v46; // rax
  __int64 v47; // rdx
  __int64 v48; // rcx
  __int64 v49; // rax
  __int64 v50; // r8
  __int64 v51; // r8
  __int64 v52; // rdx
  __int64 v53; // r8
  __int64 v54; // rdx
  __int64 v55; // r8
  __int64 *v56; // rax
  __int64 v57; // rdx
  unsigned int v58; // eax
  const struct winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult *v59; // rax
  __int64 v60; // rax
  __int64 v61; // rdx
  __int64 v62; // r8
  volatile signed __int32 *v63; // rdi
  int v64; // [rsp+20h] [rbp-368h]
  int v65[2]; // [rsp+20h] [rbp-368h]
  char *v66; // [rsp+28h] [rbp-360h]
  __int64 v67; // [rsp+70h] [rbp-318h]
  _QWORD *v68; // [rsp+90h] [rbp-2F8h]
  int CloudStore; // [rsp+A0h] [rbp-2E8h]
  wil::details::in1diag3 *retaddr; // [rsp+388h] [rbp+0h]

  v2 = a1 + 8;
  v67 = a1 + 8;
  v3 = 4;
  if ( (unsigned __int16)(*(_WORD *)(a1 + 8) + 1) > 4u )
  {
LABEL_124:
    __debugbreak();
  }
  else
  {
    v4 = &_ImageBase;
    switch ( *(_WORD *)(a1 + 8) )
    {
      case 0xFFFF:
      case 1:
      case 3:
        if ( *(_QWORD *)(a1 - 16) && wil::details::coro::g_pfnDestroyRestrictedErrorInformation )
        {
          wil::details::coro::g_pfnDestroyRestrictedErrorInformation();
          *(_QWORD *)(a1 - 16) = 0;
        }
        if ( *(_DWORD *)(a1 - 80) == 1 )
        {
          std::wstring::~wstring(a1 - 56, v4, v3);
        }
        else if ( *(_DWORD *)(a1 - 80) == 2 )
        {
          __ExceptionPtrDestroy((void *)(a1 - 72));
        }
        `wil::ProfileDataStore::CallSaveAsync<Windows::Data::Security::Passkey::RecoveryItemPdr>'::`18'::_parameters_::~_parameters_(v2 + 768);
        if ( *(_WORD *)(a1 + 10) )
          operator delete((void *)(a1 - 96), 0x3C0u);
        return;
      case 0:
        goto LABEL_124;
      case 2:
        *(_DWORD *)(a1 + 752) = 0;
        v68 = *(_QWORD **)(a1 + 776);
        v5 = v68;
        *(_QWORD *)(a1 + 16) = 0;
        v6 = (volatile signed __int32 **)(a1 + 24);
        *(_QWORD *)(a1 + 24) = 0;
        v7 = v68[1];
        if ( !v7 )
          goto LABEL_113;
        v8 = *(_DWORD *)(v7 + 8);
        do
        {
          if ( !v8 )
LABEL_113:
            std::_Throw_bad_weak_ptr();
          v9 = v8;
          v8 = _InterlockedCompareExchange((volatile signed __int32 *)(v7 + 8), v8 + 1, v8);
        }
        while ( v9 != v8 );
        *(_QWORD *)(a1 + 16) = *v68;
        v10 = (volatile signed __int32 *)v68[1];
        *v6 = v10;
        *(_DWORD *)(a1 + 752) = 4;
        v11 = *(_QWORD *)(a1 + 848);
        if ( v11 && *(_DWORD *)(v11 + 16) )
        {
          *(_OWORD *)(a1 + 88) = 0;
          *(_QWORD *)(a1 + 104) = 0;
          *(_QWORD *)(a1 + 112) = 7;
          *(_WORD *)(a1 + 88) = 0;
          *(_QWORD *)(a1 + 32) = 0;
          *(_DWORD *)(a1 + 40) = 0;
          *(_DWORD *)(a1 + 44) = -2147023673;
          v12 = *(_OWORD *)(a1 + 104);
          *(_OWORD *)(a1 + 48) = *(_OWORD *)(a1 + 88);
          *(_OWORD *)(a1 + 64) = v12;
          *(_QWORD *)(a1 + 104) = 0;
          *(_QWORD *)(a1 + 112) = 7;
          *(_WORD *)(a1 + 88) = 0;
          *(_QWORD *)(a1 + 80) = 0;
          *(_QWORD *)(a1 - 72) = *(_QWORD *)(a1 + 32);
          *(_DWORD *)(a1 - 64) = *(_DWORD *)(a1 + 40);
          *(_DWORD *)(a1 - 60) = *(_DWORD *)(a1 + 44);
          v13 = *(_OWORD *)(a1 + 64);
          *(_OWORD *)(a1 - 56) = *(_OWORD *)(a1 + 48);
          *(_OWORD *)(a1 - 40) = v13;
          *(_QWORD *)(a1 + 64) = 0;
          *(_QWORD *)(a1 + 72) = 7;
          *(_WORD *)(a1 + 48) = 0;
          *(_QWORD *)(a1 - 24) = 0;
          *(_DWORD *)(a1 - 80) = 1;
          std::wstring::~wstring(a1 + 48, 7, 4);
          std::wstring::~wstring(a1 + 88, v14, v15);
          if ( v10 )
          {
            v16 = *v6;
            if ( _InterlockedExchangeAdd(*v6 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v16)(v16);
              if ( _InterlockedExchangeAdd(v16 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
            }
          }
        }
        else
        {
          v17 = *(_DWORD *)(a1 + 824);
          if ( (v17 & 7) == 0 || (v18 = 1, (((*(_DWORD *)(a1 + 824) & 7) - 1LL) & *(_DWORD *)(a1 + 824) & 7) == 0) )
            v18 = 0;
          if ( v18 )
            wil::details::in1diag3::_FailFast_Unexpected(
              retaddr,
              (void *)0x91F,
              (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil\\profiledatastore.h",
              (const char *)1);
          if ( (v17 & 1) != 0 )
          {
            v19 = 1;
          }
          else if ( (v17 & 2) != 0 )
          {
            v19 = 2;
          }
          else
          {
            v19 = 0;
            if ( (v17 & 4) != 0 )
              v19 = 4;
          }
          v20 = v19 | 0x20;
          if ( (v17 & 0x10) == 0 )
            v20 = v19;
          *(_DWORD *)(a1 + 120) = v20;
          v21 = *(_QWORD *)(a1 + 800);
          if ( *(_BYTE *)(v21 + 41) )
            goto LABEL_32;
          v22 = *(_QWORD *)(v21 + 32);
          *(_QWORD *)(a1 + 128) = v22;
          if ( v22 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 8LL))(v22);
          *(_DWORD *)(a1 + 752) = 5;
          v23 = v22 == 0;
          v24 = 0;
          if ( v23 )
LABEL_32:
            v24 = 1;
          v25 = *(_DWORD *)(a1 + 752);
          if ( (v25 & 1) != 0 )
          {
            *(_DWORD *)(a1 + 752) = v25 & 0xFFFFFFFE;
            v26 = *(_QWORD *)(a1 + 128);
            if ( v26 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
          }
          if ( v24 )
            *(_DWORD *)(a1 + 120) = v20 | 8;
          wil::ProfileDataStore::Marshal<wil::ProfileDataItem<Windows::Data::Security::Passkey::RecoveryItemPdr>>(
            a1 + 136,
            *(_QWORD *)(a1 + 800));
          v27 = *(_QWORD *)(a1 + 136);
          *(_QWORD *)(a1 + 144) = v27;
          if ( v27 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 8LL))(v27);
          v28 = *(_QWORD *)(*(_QWORD *)(a1 + 800) + 32LL);
          *(_QWORD *)(a1 + 152) = v28;
          if ( v28 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 8LL))(v28);
          *(_QWORD *)(a1 + 160) = 0;
          *(_QWORD *)(a1 + 168) = 0;
          *(_QWORD *)(a1 + 176) = 0;
          winrt::single_threaded_vector<winrt::Windows::Internal::Storage::Cloud::CloudStoreBatchSaveItemData,std::allocator<winrt::Windows::Internal::Storage::Cloud::CloudStoreBatchSaveItemData>>(
            a1 + 184,
            a1 + 160);
          std::vector<winrt::Windows::Internal::Storage::Cloud::CloudStoreBatchSaveItemData>::~vector<winrt::Windows::Internal::Storage::Cloud::CloudStoreBatchSaveItemData>(a1 + 160);
          wil::details::GetActivationFactoryPdr<Windows::Internal::Storage::Cloud::ICloudStoreBatchSaveItemDataFactory>(a1 + 192);
          std::wstring::wstring(a1 + 200, *(_QWORD *)(a1 + 784));
          v29 = *(_DWORD *)(a1 + 752) | 8;
          *(_DWORD *)(a1 + 752) = v29;
          if ( *(_QWORD *)(a1 + 216) )
          {
            v30 = (const WCHAR *)(a1 + 232);
            std::wstring::wstring(a1 + 232, *(_QWORD *)(a1 + 784));
            v29 |= 0x12u;
            *(_DWORD *)(a1 + 752) = v29;
            if ( *(_QWORD *)(a1 + 256) > 7u )
              v30 = *(const WCHAR **)v30;
          }
          else
          {
            v30 = L"default";
          }
          wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(
            (HSTRING *)(a1 + 264),
            v30);
          if ( (v29 & 2) != 0 )
            std::wstring::~wstring(a1 + 232, v31, v32);
          std::wstring::~wstring(a1 + 200, v31, v32);
          *(_QWORD *)(a1 + 272) = 0;
          *(_QWORD *)(a1 + 280) = a1 + 272;
          *(_QWORD *)(a1 + 288) = 0;
          *(_BYTE *)(a1 + 296) = 1;
          v33 = WindowsDuplicateString(*(HSTRING *)(a1 + 832), (HSTRING *)(a1 + 288));
          if ( v33 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x70E,
              (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil\\profiledatastore.h",
              (const char *)(unsigned int)v33,
              v64);
          if ( *(_BYTE *)(a1 + 296) )
          {
            v34 = *(HSTRING *)(a1 + 288);
            v35 = *(HSTRING **)(a1 + 280);
            v36 = *v35;
            if ( *v35 )
            {
              LastError = GetLastError();
              WindowsDeleteString(v36);
              SetLastError(LastError);
            }
            *v35 = v34;
            v5 = v68;
          }
          v38 = (__int64 *)(a1 + 304);
          *(_QWORD *)(a1 + 304) = 0;
          *(_QWORD *)v65 = *(_QWORD *)(a1 + 144);
          v39 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, _QWORD))(**(_QWORD **)(a1 + 192) + 48LL))(
                  *(_QWORD *)(a1 + 192),
                  *(_QWORD *)(a1 + 264),
                  v28,
                  *(_QWORD *)(a1 + 816));
          if ( v39 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x717,
              (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil\\profiledatastore.h",
              (const char *)(unsigned int)v39,
              v65[0]);
          v40 = *v38;
          *v38 = 0;
          *(_QWORD *)(a1 + 312) = v40;
          winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Internal::Storage::Cloud::CloudStoreBatchSaveItemData>,winrt::Windows::Internal::Storage::Cloud::CloudStoreBatchSaveItemData>::Append(
            a1 + 184,
            a1 + 312);
          v41 = (__int64 *)(a1 + 320);
          *(_QWORD *)(a1 + 320) = 0;
          CloudStore = wil::details::SharedCloudStoreState::GetCloudStore(v5[2], a1 + 352);
          *(_QWORD *)(a1 + 360) = *(_QWORD *)(a1 + 840);
          View = (_QWORD *)winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Internal::Storage::Cloud::CloudStoreBatchSaveItemData>,winrt::Windows::Internal::Storage::Cloud::CloudStoreBatchSaveItemData>::GetView(
                             a1 + 184,
                             a1 + 408);
          *(_BYTE *)(a1 + 400) = 0;
          *(_QWORD *)(a1 + 392) = *View;
          v43 = (_QWORD *)wil::ProfileDataStore::GetTypeNameWideString<Windows::Data::Security::Passkey::RecoveryItemPdr>(a1 + 448);
          v44 = v43;
          v45 = v43[2];
          if ( v43[3] > 7u )
            v44 = (_QWORD *)*v43;
          if ( (_DWORD)v45 )
          {
            if ( *((_WORD *)v44 + (unsigned int)v45) )
              abort();
            v46 = a1 + 424;
            *(_DWORD *)(a1 + 424) = 1;
            *(_DWORD *)(a1 + 428) = v45;
            *(_QWORD *)(a1 + 440) = v44;
          }
          else
          {
            v46 = 0;
          }
          *(_QWORD *)(a1 + 416) = v46;
          std::wstring::wstring(a1 + 512, *(_QWORD *)(a1 + 784) + 32LL);
          v47 = *(_QWORD *)(a1 + 528);
          if ( *(_QWORD *)(a1 + 536) <= 7u )
            v48 = a1 + 512;
          else
            v48 = *(_QWORD *)(a1 + 512);
          if ( (_DWORD)v47 )
          {
            if ( *(_WORD *)(v48 + 2LL * (unsigned int)v47) )
              abort();
            v49 = a1 + 488;
            *(_DWORD *)(a1 + 488) = 1;
            *(_DWORD *)(a1 + 492) = v47;
            *(_QWORD *)(a1 + 504) = v48;
          }
          else
          {
            v49 = 0;
          }
          *(_QWORD *)(a1 + 480) = v49;
          v50 = *(_QWORD *)(v67 + 768);
          *(_QWORD *)(a1 + 544) = *(_QWORD *)(v50 + 40);
          v51 = winrt::impl::consume_Windows_Internal_Storage_Cloud_ICloudStore2<winrt::Windows::Internal::Storage::Cloud::CloudStore>::BatchSaveAsync(
                  CloudStore,
                  (int)a1 + 576,
                  (int)v50 + 32,
                  (int)a1 + 544,
                  a1 + 480,
                  a1 + 416,
                  a1 + 120,
                  a1 + 392,
                  a1 + 360);
          wil::details::AsyncOpWaiter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>>,winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>>::AsyncOpWaiter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>>,winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>>(
            a1 + 328,
            a1 + 848,
            v51);
          if ( *(_QWORD *)(a1 + 576) )
            winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 576);
          std::wstring::~wstring(a1 + 512, v52, v53);
          std::wstring::~wstring(a1 + 448, v54, v55);
          if ( *(_QWORD *)(a1 + 408) )
            winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 408);
          if ( *(_QWORD *)(a1 + 352) )
            winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 352);
          v56 = (__int64 *)wil::details::AsyncOpWaiter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>>,winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>>::WaitForResult(
                             a1 + 328,
                             a1 + 584);
          if ( v41 != v56 )
          {
            v57 = *v56;
            *v56 = 0;
            *v41 = v57;
          }
          if ( *(_QWORD *)(a1 + 584) )
            winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 584);
          wil::details::AsyncOpWaiter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>,winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>::~AsyncOpWaiter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>,winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>(a1 + 328);
          if ( *v41
            && !(unsigned int)winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::Storage::Cloud::CloudStoreData>,winrt::Windows::Internal::Storage::Cloud::CloudStoreData>::Size(a1 + 320) )
          {
            v58 = wil::verify_hresult<long>(13);
            wil::details::in1diag3::Throw_HrMsg(
              retaddr,
              (void *)0x73B,
              (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil\\profiledatastore.h",
              (const char *)v58,
              (int)"Expected exactly one result from the batch save operation.",
              v66);
          }
          if ( (unsigned int)winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::Storage::Cloud::CloudStoreData>,winrt::Windows::Internal::Storage::Cloud::CloudStoreData>::Size(a1 + 320) > 1 )
            wil::details::in1diag3::Log_HrMsg(
              retaddr,
              (void *)0x73F,
              (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil\\profiledatastore.h",
              (const char *)0xD,
              (int)"Too many results from the batch save operation.",
              v66);
          v59 = (const struct winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult *)winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>,winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>::GetAt(
                                                                                                 a1 + 320,
                                                                                                 a1 + 736,
                                                                                                 0);
          v60 = wil::ProfileDataStoreSaveResult::ProfileDataStoreSaveResult(
                  (wil::ProfileDataStoreSaveResult *)(a1 + 680),
                  v59);
          *(_QWORD *)(a1 - 72) = *(_QWORD *)v60;
          *(_DWORD *)(a1 - 64) = *(_DWORD *)(v60 + 8);
          *(_DWORD *)(a1 - 60) = *(_DWORD *)(v60 + 12);
          *(_OWORD *)(a1 - 56) = 0;
          *(_QWORD *)(a1 - 40) = 0;
          *(_QWORD *)(a1 - 32) = 0;
          *(_OWORD *)(a1 - 56) = *(_OWORD *)(v60 + 16);
          *(_OWORD *)(a1 - 40) = *(_OWORD *)(v60 + 32);
          *(_QWORD *)(v60 + 32) = 0;
          *(_QWORD *)(v60 + 40) = 7;
          *(_WORD *)(v60 + 16) = 0;
          *(_QWORD *)(a1 - 24) = *(_QWORD *)(v60 + 48);
          *(_DWORD *)(a1 - 80) = 1;
          std::wstring::~wstring(a1 + 696, v61, v62);
          if ( *(_QWORD *)(a1 + 736) )
            winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 736);
          if ( *v41 )
            winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 320);
          if ( *(_QWORD *)(a1 + 312) )
            winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 312);
          if ( *(_QWORD *)(a1 + 304) )
            (*(void (**)(void))(**(_QWORD **)(a1 + 304) + 16LL))();
          if ( *(_QWORD *)(a1 + 272) )
            WindowsDeleteString(*(HSTRING *)(a1 + 272));
          if ( *(_QWORD *)(a1 + 264) )
            WindowsDeleteString(*(HSTRING *)(a1 + 264));
          if ( *(_QWORD *)(a1 + 192) )
            (*(void (**)(void))(**(_QWORD **)(a1 + 192) + 16LL))();
          if ( *(_QWORD *)(a1 + 184) )
            winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 184);
          if ( v28 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
          if ( *(_QWORD *)(a1 + 144) )
            (*(void (**)(void))(**(_QWORD **)(a1 + 144) + 16LL))();
          if ( *(_QWORD *)(a1 + 136) )
            winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 136);
          if ( *(_QWORD *)(a1 + 24) )
          {
            v63 = *(volatile signed __int32 **)(a1 + 24);
            if ( _InterlockedExchangeAdd(v63 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v63)(v63);
              if ( _InterlockedExchangeAdd(v63 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v63 + 8LL))(v63);
            }
          }
        }
        *(_QWORD *)(a1 + 744) = a1 - 96;
        *(_WORD *)v67 = 0;
        `wil::details::coro::promise_base<wil::ProfileDataStoreSaveResult>::final_suspend'::`2'::awaiter::await_suspend();
        break;
    }
  }
}

```

## disassembly

```asm
0x18002c8d0  mov     r11, rsp
0x18002c8d3  mov     [r11+10h], rbx
0x18002c8d7  mov     [r11+18h], rsi
0x18002c8db  mov     [r11+8], rcx
0x18002c8df  push    rdi
0x18002c8e0  push    r12
0x18002c8e2  push    r13
0x18002c8e4  push    r14
0x18002c8e6  push    r15
0x18002c8e8  sub     rsp, 360h
0x18002c8ef  mov     rax, cs:__security_cookie
0x18002c8f6  xor     rax, rsp
0x18002c8f9  mov     [rsp+388h+var_38], rax
0x18002c901  mov     rsi, rcx
0x18002c904  mov     [rsp+388h+var_300], rcx
0x18002c90c  lea     r14, [rsi+8]
0x18002c910  mov     [rsp+388h+var_318], r14
0x18002c915  movzx   eax, word ptr [r14]
0x18002c919  mov     [rsp+388h+var_2F0], ax
0x18002c921  mov     r9d, 1
0x18002c927  add     ax, r9w
0x18002c92b  lea     r8d, [r9+3]
0x18002c92f  cmp     ax, r8w
0x18002c933  ja      loc_18002D6C5; jumptable 000000018002C956 case 1
0x18002c939  mov     [rsp+388h+var_2D8], r14
0x18002c941  movsx   rax, ax
0x18002c945  lea     rdx, __ImageBase
0x18002c94c  mov     ecx, ds:(jpt_18002C956 - 180000000h)[rdx+rax*4]; switch 5 cases
0x18002c953  add     rcx, rdx
0x18002c956  jmp     rcx; switch jump
0x18002c958  jmp     loc_18002D660; jumptable 000000018002C956 case 4
0x18002c95d  xor     edi, edi; jumptable 000000018002C956 case 3
0x18002c95f  mov     [rsi+2F0h], edi
0x18002c965  mov     r12, [r14+300h]
0x18002c96c  mov     [rsp+388h+var_2F8], r12
0x18002c974  mov     [rsi+10h], rdi
0x18002c978  lea     r15, [rsi+18h]
0x18002c97c  mov     [r15], rdi
0x18002c97f  mov     rdx, [r12+8]
0x18002c984  test    rdx, rdx
0x18002c987  jz      loc_18002D626
0x18002c98d  mov     eax, [rdx+8]
0x18002c990  jmp     short loc_18002C99C
0x18002c992  lea     ecx, [rax+1]
0x18002c995  lock cmpxchg [rdx+8], ecx
0x18002c99a  jz      short loc_18002C9A5
0x18002c99c  test    eax, eax
0x18002c99e  jnz     short loc_18002C992
0x18002c9a0  jmp     loc_18002D626
0x18002c9a5  mov     [rsp+388h+var_2D0], r15
0x18002c9ad  mov     rax, [r12]
0x18002c9b1  mov     [rsi+10h], rax
0x18002c9b5  mov     r14, [r12+8]
0x18002c9ba  mov     [r15], r14
0x18002c9bd  mov     [rsi+2F0h], r8d
0x18002c9c4  mov     rax, [rsi+350h]
0x18002c9cb  test    rax, rax
0x18002c9ce  jz      loc_18002CAFB
0x18002c9d4  mov     eax, [rax+10h]
0x18002c9d7  nop
0x18002c9d8  test    eax, eax
0x18002c9da  jz      loc_18002CAFB
0x18002c9e0  lea     rbx, [rsi+58h]
0x18002c9e4  xorps   xmm0, xmm0
0x18002c9e7  movups  xmmword ptr [rbx], xmm0
0x18002c9ea  mov     [rsi+68h], rdi
0x18002c9ee  mov     edx, 7
0x18002c9f3  mov     [rsi+70h], rdx
0x18002c9f7  xor     eax, eax
0x18002c9f9  mov     [rbx], ax
0x18002c9fc  mov     [rsi+20h], rdi
0x18002ca00  mov     [rsi+28h], edi
0x18002ca03  mov     dword ptr [rsi+2Ch], 800704C7h
0x18002ca0a  lea     rcx, [rsi+30h]
0x18002ca0e  movups  xmm1, xmmword ptr [rbx]
0x18002ca11  movups  [rsp+388h+var_1A8], xmm1
0x18002ca19  movups  xmm0, xmmword ptr [rbx+10h]
0x18002ca1d  movups  [rsp+388h+var_198], xmm0
0x18002ca25  movups  xmmword ptr [rcx], xmm1
0x18002ca28  movups  xmmword ptr [rcx+10h], xmm0
0x18002ca2c  mov     [rsi+68h], rdi
0x18002ca30  mov     [rsi+70h], rdx
0x18002ca34  mov     [rbx], ax
0x18002ca37  mov     [rsi+50h], rdi
0x18002ca3b  mov     rax, [rsi+20h]
0x18002ca3f  mov     [rsp+388h+var_1E0], rax
0x18002ca47  mov     [rsi-48h], rax
0x18002ca4b  mov     eax, [rsi+28h]
0x18002ca4e  mov     [rsp+388h+var_1D8], eax
0x18002ca55  mov     [rsi-40h], eax
0x18002ca58  mov     eax, [rsi+2Ch]
0x18002ca5b  mov     [rsp+388h+var_1D4], eax
0x18002ca62  mov     [rsi-3Ch], eax
0x18002ca65  movups  xmm1, xmmword ptr [rcx]
0x18002ca68  movups  [rsp+388h+var_1D0], xmm1
0x18002ca70  movups  xmm0, xmmword ptr [rcx+10h]
0x18002ca74  movups  [rsp+388h+var_1C0], xmm0
0x18002ca7c  movups  xmmword ptr [rsi-38h], xmm1
0x18002ca80  movups  xmmword ptr [rsi-28h], xmm0
0x18002ca84  mov     [rsi+40h], rdi
0x18002ca88  mov     [rsi+48h], rdx
0x18002ca8c  xor     eax, eax
0x18002ca8e  mov     [rcx], ax
0x18002ca91  mov     [rsi-18h], rdi
0x18002ca95  mov     [rsi-50h], r9d
0x18002ca99  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002ca9e  mov     rcx, rbx
0x18002caa1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002caa6  nop
0x18002caa7  mov     [rsp+388h+var_2C0], r14
0x18002caaf  test    r14, r14
0x18002cab2  jz      short loc_18002CAF6
0x18002cab4  mov     rdi, [r15]
0x18002cab7  mov     [rsp+388h+var_2C0], rdi
0x18002cabf  or      ebx, 0FFFFFFFFh
0x18002cac2  mov     eax, ebx
0x18002cac4  lock xadd [rdi+8], eax
0x18002cac9  add     eax, ebx
0x18002cacb  jnz     short loc_18002CAF6
0x18002cacd  mov     rax, [rdi]
0x18002cad0  mov     rcx, rdi
0x18002cad3  mov     rax, [rax]
0x18002cad6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cadb  mov     eax, ebx
0x18002cadd  lock xadd [rdi+0Ch], eax
0x18002cae2  add     eax, ebx
0x18002cae4  jnz     short loc_18002CAF6
0x18002cae6  mov     rax, [rdi]
0x18002cae9  mov     rcx, rdi
0x18002caec  mov     rax, [rax+8]
0x18002caf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002caf5  nop
0x18002caf6  jmp     loc_18002D641
0x18002cafb  mov     edx, [rsi+338h]
0x18002cb01  mov     eax, edx
0x18002cb03  and     eax, 7
0x18002cb06  jz      short loc_18002CB15
0x18002cb08  mov     ecx, eax
0x18002cb0a  dec     rax
0x18002cb0d  test    rcx, rax
0x18002cb10  mov     al, r9b
0x18002cb13  jnz     short loc_18002CB18
0x18002cb15  mov     al, dil
0x18002cb18  mov     rcx, [rsp+388h]; this
0x18002cb20  test    al, al
0x18002cb22  jz      short loc_18002CB36
0x18002cb24  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\sdk\\inc\\wil\\pr"...
0x18002cb2b  mov     edx, 91Fh; void *
0x18002cb30  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18002cb36  test    r9d, edx
0x18002cb39  jz      short loc_18002CB40
0x18002cb3b  mov     eax, r9d
0x18002cb3e  jmp     short loc_18002CB56
0x18002cb40  bt      edx, 1
0x18002cb44  jnb     short loc_18002CB4D
0x18002cb46  mov     eax, 2
0x18002cb4b  jmp     short loc_18002CB56
0x18002cb4d  mov     eax, edi
0x18002cb4f  test    r8d, edx
0x18002cb52  cmovnz  eax, r8d
0x18002cb56  mov     ebx, eax
0x18002cb58  or      ebx, 20h
0x18002cb5b  bt      edx, 4
0x18002cb5f  cmovnb  ebx, eax
0x18002cb62  mov     [rsi+78h], ebx
0x18002cb65  mov     r14, [rsi+320h]
0x18002cb6c  cmp     [r14+29h], dil
0x18002cb70  jnz     short loc_18002CBA9
0x18002cb72  mov     r14, [r14+20h]
0x18002cb76  mov     [rsi+80h], r14
0x18002cb7d  test    r14, r14
0x18002cb80  jz      short loc_18002CB97
0x18002cb82  mov     rax, [r14]
0x18002cb85  mov     rcx, r14
0x18002cb88  mov     rax, [rax+8]
0x18002cb8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cb91  mov     r9d, 1
0x18002cb97  mov     dword ptr [rsi+2F0h], 5
0x18002cba1  test    r14, r14
0x18002cba4  mov     r14b, dil
0x18002cba7  jnz     short loc_18002CBAC
0x18002cba9  mov     r14b, r9b
0x18002cbac  mov     eax, [rsi+2F0h]
0x18002cbb2  mov     [rsp+388h+var_338], eax
0x18002cbb6  test    r9d, eax
0x18002cbb9  jz      short loc_18002CBE1
0x18002cbbb  mov     [rsp+388h+var_338], eax
0x18002cbbf  and     eax, 0FFFFFFFEh
0x18002cbc2  mov     [rsi+2F0h], eax
0x18002cbc8  mov     rcx, [rsi+80h]
0x18002cbcf  test    rcx, rcx
0x18002cbd2  jz      short loc_18002CBE1
0x18002cbd4  mov     rax, [rcx]
0x18002cbd7  mov     rax, [rax+10h]
0x18002cbdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cbe0  nop
0x18002cbe1  test    r14b, r14b
0x18002cbe4  jz      short loc_18002CBF3
0x18002cbe6  mov     [rsp+388h+var_260], ebx
0x18002cbed  or      ebx, 8
0x18002cbf0  mov     [rsi+78h], ebx
0x18002cbf3  lea     rbx, [rsi+88h]
0x18002cbfa  mov     [rsp+388h+var_268], rbx
0x18002cc02  mov     rdx, [rsi+320h]
0x18002cc09  mov     rcx, rbx
0x18002cc0c  call    ??$Marshal@V?$ProfileDataItem@URecoveryItemPdr@Passkey@Security@Data@Windows@@@wil@@@ProfileDataStore@wil@@CA?AUIBuffer@Streams@Storage@Windows@winrt@@AEBV?$ProfileDataItem@URecoveryItemPdr@Passkey@Security@Data@Windows@@@1@@Z; wil::ProfileDataStore::Marshal<wil::ProfileDataItem<Windows::Data::Security::Passkey::RecoveryItemPdr>>(wil::ProfileDataItem<Windows::Data::Security::Passkey::RecoveryItemPdr> const &)
0x18002cc11  nop
0x18002cc12  mov     rcx, [rbx]
0x18002cc15  mov     [rsp+388h+var_2E0], rcx
0x18002cc1d  lea     rax, [rsi+90h]
0x18002cc24  mov     [rsp+388h+var_270], rax
0x18002cc2c  mov     [rax], rcx
0x18002cc2f  test    rcx, rcx
0x18002cc32  jz      short loc_18002CC40
0x18002cc34  mov     rax, [rcx]
0x18002cc37  mov     rax, [rax+8]
0x18002cc3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cc40  mov     rax, [rsi+320h]
0x18002cc47  mov     r13, [rax+20h]
0x18002cc4b  mov     [rsp+388h+var_278], r13
0x18002cc53  mov     [rsi+98h], r13
0x18002cc5a  test    r13, r13
0x18002cc5d  jz      short loc_18002CC70
0x18002cc5f  mov     rax, [r13+0]
0x18002cc63  mov     rcx, r13
0x18002cc66  mov     rax, [rax+8]
0x18002cc6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cc6f  nop
0x18002cc70  lea     rbx, [rsi+0A0h]
0x18002cc77  mov     [rbx], rdi
0x18002cc7a  mov     [rsi+0A8h], rdi
0x18002cc81  mov     [rsi+0B0h], rdi
0x18002cc88  lea     rax, [rsi+0B8h]
0x18002cc8f  mov     [rsp+388h+var_288], rax
0x18002cc97  mov     rdx, rbx
0x18002cc9a  mov     rcx, rax
0x18002cc9d  call    ??$single_threaded_vector@UCloudStoreBatchSaveItemData@Cloud@Storage@Internal@Windows@winrt@@V?$allocator@UCloudStoreBatchSaveItemData@Cloud@Storage@Internal@Windows@winrt@@@std@@@winrt@@YA?AU?$IVector@UCloudStoreBatchSaveItemData@Cloud@Storage@Internal@Windows@winrt@@@Collections@Foundation@Windows@0@$$QEAV?$vector@UCloudStoreBatchSaveItemData@Cloud@Storage@Internal@Windows@winrt@@V?$allocator@UCloudStoreBatchSaveItemData@Cloud@Storage@Internal@Windows@winrt@@@std@@@std@@@Z; winrt::single_threaded_vector<winrt::Windows::Internal::Storage::Cloud::CloudStoreBatchSaveItemData,std::allocator<winrt::Windows::Internal::Storage::Cloud::CloudStoreBatchSaveItemData>>(std::vector<winrt::Windows::Internal::Storage::Cloud::CloudStoreBatchSaveItemData> &&)
0x18002cca2  nop
0x18002cca3  mov     rcx, rbx
0x18002cca6  call    ??1?$vector@UCloudStoreBatchSaveItemData@Cloud@Storage@Internal@Windows@winrt@@V?$allocator@UCloudStoreBatchSaveItemData@Cloud@Storage@Internal@Windows@winrt@@@std@@@std@@QEAA@XZ; std::vector<winrt::Windows::Internal::Storage::Cloud::CloudStoreBatchSaveItemData>::~vector<winrt::Windows::Internal::Storage::Cloud::CloudStoreBatchSaveItemData>(void)
0x18002ccab  lea     rax, [rsi+0C0h]
0x18002ccb2  mov     [rsp+388h+var_290], rax
0x18002ccba  mov     rcx, rax
0x18002ccbd  call    ??$GetActivationFactoryPdr@UICloudStoreBatchSaveItemDataFactory@Cloud@Storage@Internal@Windows@@@details@wil@@YA?AV?$com_ptr_t@UICloudStoreBatchSaveItemDataFactory@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@1@PEBG@Z; wil::details::GetActivationFactoryPdr<Windows::Internal::Storage::Cloud::ICloudStoreBatchSaveItemDataFactory>(ushort const *)
0x18002ccc2  nop
0x18002ccc3  lea     r15, [rsi+0C8h]
0x18002ccca  mov     rdx, [rsi+310h]
0x18002ccd1  mov     rcx, r15
0x18002ccd4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002ccd9  mov     ebx, [rsi+2F0h]
0x18002ccdf  mov     [rsp+388h+var_338], ebx
0x18002cce3  or      ebx, 8
0x18002cce6  mov     [rsi+2F0h], ebx
0x18002ccec  mov     rax, [rsi+0D8h]
0x18002ccf3  mov     [rsp+388h+var_120], rax
0x18002ccfb  test    rax, rax
0x18002ccfe  jnz     short loc_18002CD09
0x18002cd00  lea     r14, sourceString; "default"
0x18002cd07  jmp     short loc_18002CD4F
0x18002cd09  lea     r14, [rsi+0E8h]
0x18002cd10  mov     rdx, [rsi+310h]
0x18002cd17  mov     rcx, r14
0x18002cd1a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002cd1f  or      ebx, 10h
0x18002cd22  mov     [rsp+388h+var_338], ebx
0x18002cd26  or      ebx, 2
0x18002cd29  mov     [rsi+2F0h], ebx
0x18002cd2f  mov     rax, [rsi+100h]
0x18002cd36  mov     [rsp+388h+var_170], rax
0x18002cd3e  cmp     rax, 7
0x18002cd42  jbe     short loc_18002CD4F
0x18002cd44  mov     r14, [r14]
0x18002cd47  mov     [rsp+388h+var_188], r14
0x18002cd4f  lea     rax, [rsi+108h]
0x18002cd56  mov     [rsp+388h+var_298], rax
0x18002cd5e  mov     rdx, r14; sourceString
0x18002cd61  mov     rcx, rax; string
0x18002cd64  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18002cd69  nop
0x18002cd6a  mov     [rsp+388h+var_338], ebx
0x18002cd6e  bt      ebx, 1
0x18002cd72  jnb     short loc_18002CD81
0x18002cd74  lea     rcx, [rsi+0E8h]
0x18002cd7b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002cd80  nop
0x18002cd81  mov     rcx, r15
0x18002cd84  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002cd89  lea     rax, [rsi+110h]
0x18002cd90  mov     [rsp+388h+var_2A0], rax
0x18002cd98  mov     [rax], rdi
0x18002cd9b  mov     [rsi+118h], rax
0x18002cda2  lea     rbx, [rsi+120h]
0x18002cda9  mov     [rbx], rdi
0x18002cdac  mov     byte ptr [rsi+128h], 1
0x18002cdb3  mov     rdx, rbx; newString
0x18002cdb6  mov     rcx, [rsi+340h]; string
0x18002cdbd  call    cs:__imp_WindowsDuplicateString
0x18002cdc3  mov     rcx, [rsp+388h]; this
0x18002cdcb  test    eax, eax
0x18002cdcd  jns     short loc_18002CDE4
  ... truncated ...
```
