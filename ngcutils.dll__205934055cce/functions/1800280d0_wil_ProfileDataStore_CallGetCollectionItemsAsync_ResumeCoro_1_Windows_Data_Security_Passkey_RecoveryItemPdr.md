# wil::ProfileDataStore::CallGetCollectionItemsAsync$_ResumeCoro$1_Windows::Data::Security::Passkey::RecoveryItemPdr_

- ea: `0x1800280d0`
- end: `0x180028df4`
- name: `wil::ProfileDataStore::CallGetCollectionItemsAsync$_ResumeCoro$1_Windows::Data::Security::Passkey::RecoveryItemPdr_`
- size: `3364`
- prototype: ``
- caller_count: `1`
- callee_count: `30`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180029d4c`

## callees

- `0x180003080`
- `0x180003520`
- `0x180003c97`
- `0x180003cdf`
- `0x180007a5c`
- `0x18000c95c`
- `0x18000ce74`
- `0x18000f7fc`
- `0x18001354c`
- `0x1800280d0`
- `0x180037a3c`
- `0x18003fcd8`
- `0x180041aa0`
- `0x180041f44`
- `0x1800439bc`
- `0x180045530`
- `0x180045914`
- `0x180046ad0`
- `0x180049238`
- `0x180049728`
- `0x18004a7f4`
- `0x18004bf18`
- `0x18004c034`
- `0x18004ccf0`
- `0x18004ce6c`
- `0x18004d9d8`
- `0x18004eaac`
- `0x18004eba0`
- `0x18004ed9c`
- `0x180061010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180028d74`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180028d74`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180028473`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180028c05`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180028473`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180028c05`

## pseudocode

```c
void __fastcall wil::ProfileDataStore::CallGetCollectionItemsAsync__ResumeCoro_1_Windows::Data::Security::Passkey::RecoveryItemPdr_(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int16 *v4; // rdx
  _QWORD *v5; // r12
  volatile signed __int32 **v6; // r15
  __int64 v7; // rdx
  signed __int32 v8; // eax
  signed __int32 v9; // ett
  volatile signed __int32 *v10; // r13
  __int64 v11; // rax
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rax
  __int64 v15; // rdx
  __int64 v16; // r8
  volatile signed __int32 *v17; // rsi
  _QWORD *v18; // rbx
  __int64 *v19; // r14
  int CloudStore; // r11d
  int v21; // r8d
  int v22; // edx
  int v23; // ecx
  int v24; // edx
  int v25; // eax
  int v26; // r8d
  int v27; // edx
  int v28; // ecx
  int v29; // edx
  int v30; // eax
  __int64 v31; // rcx
  __int64 v32; // rax
  __int64 v33; // r8
  __int64 CollectionItemsAsync; // r8
  __int64 *v35; // rax
  __int64 v36; // rdx
  __int64 v37; // rcx
  unsigned int v38; // eax
  int v39; // r12d
  int v40; // eax
  _QWORD *v41; // r15
  __int64 v42; // rax
  __int64 v43; // rdx
  __int64 v44; // rcx
  __int64 v45; // rax
  __int64 v46; // rdx
  __int64 v47; // r8
  __int64 v48; // rdx
  __int64 v49; // r8
  volatile signed __int32 *v50; // rsi
  _QWORD *v51; // rax
  _QWORD *v52; // r8
  _QWORD *v53; // rdx
  volatile signed __int32 *v54; // r14
  volatile signed __int32 **v55; // r13
  __int64 v56; // rax
  const WCHAR *v57; // rdx
  __int64 v58; // r8
  __int64 v59; // rdx
  __int64 v60; // rcx
  __int64 v61; // rax
  __int64 v62; // rdx
  __int64 v63; // rcx
  __int64 v64; // rax
  __int64 v65; // rdx
  __int64 v66; // r8
  volatile signed __int32 *v67; // r15
  int v68; // eax
  HANDLE ProcessHeap; // rax
  __int64 v70; // rdx
  __int64 v71; // r8
  volatile signed __int32 *v72; // rsi
  int v73; // [rsp+50h] [rbp-2A8h]
  __int64 v74; // [rsp+68h] [rbp-290h]
  wil::details::in1diag3 *retaddr; // [rsp+2F8h] [rbp+0h]

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
      if ( *(_DWORD *)(a1 - 96) == 1 )
      {
        std::wstring::~wstring(a1 - 64, v4, a3);
        std::vector<std::shared_ptr<wil::ProfileDataItem<Windows::Data::Security::Passkey::PasskeyItemPdr>>>::_Tidy(a1 - 88);
      }
      else if ( *(_DWORD *)(a1 - 96) == 2 )
      {
        __ExceptionPtrDestroy((void *)(a1 - 88));
      }
      `wil::ProfileDataStore::CallGetCollectionItemIdsAsync<Windows::Data::Security::Passkey::RecoveryItemPdr>'::`8'::_parameters_::~_parameters_(a1 + 952);
      if ( *(_WORD *)(a1 + 10) )
        operator delete((void *)(a1 - 112), 0x460u);
      return;
    case 2:
      v5 = *(_QWORD **)(a1 + 952);
      *(_QWORD *)(a1 + 16) = 0;
      v6 = (volatile signed __int32 **)(a1 + 24);
      *(_QWORD *)(a1 + 24) = 0;
      v7 = v5[1];
      if ( !v7 )
        goto LABEL_96;
      v8 = *(_DWORD *)(v7 + 8);
      do
      {
        if ( !v8 )
LABEL_96:
          std::_Throw_bad_weak_ptr();
        v9 = v8;
        v8 = _InterlockedCompareExchange((volatile signed __int32 *)(v7 + 8), v8 + 1, v8);
      }
      while ( v9 != v8 );
      *(_QWORD *)(a1 + 16) = *v5;
      v10 = (volatile signed __int32 *)v5[1];
      *v6 = v10;
      v11 = *(_QWORD *)(a1 + 992);
      if ( v11 && *(_DWORD *)(v11 + 16) )
      {
        *(_OWORD *)(a1 + 112) = 0;
        *(_QWORD *)(a1 + 128) = 0;
        *(_QWORD *)(a1 + 136) = 7;
        *(_WORD *)(a1 + 112) = 0;
        *(_QWORD *)(a1 + 160) = 0;
        *(_QWORD *)(a1 + 152) = 0;
        *(_QWORD *)(a1 + 144) = 0;
        *(_QWORD *)(a1 + 32) = 0;
        *(_QWORD *)(a1 + 40) = 0;
        *(_QWORD *)(a1 + 48) = 0;
        std::wstring::wstring(a1 + 56, a1 + 112);
        *(_DWORD *)(a1 + 88) = -2147023673;
        *(_QWORD *)(a1 + 96) = 0;
        v12 = *(_QWORD *)(a1 + 48);
        *(_QWORD *)(a1 + 48) = 0;
        v13 = *(_QWORD *)(a1 + 40);
        *(_QWORD *)(a1 + 40) = 0;
        v14 = *(_QWORD *)(a1 + 32);
        *(_QWORD *)(a1 + 32) = 0;
        *(_QWORD *)(a1 - 88) = v14;
        *(_QWORD *)(a1 - 80) = v13;
        *(_QWORD *)(a1 - 72) = v12;
        *(_QWORD *)(a1 - 64) = *(_QWORD *)(a1 + 56);
        *(_QWORD *)(a1 - 56) = *(_QWORD *)(a1 + 64);
        *(_QWORD *)(a1 - 48) = *(_QWORD *)(a1 + 72);
        *(_QWORD *)(a1 - 40) = *(_QWORD *)(a1 + 80);
        *(_QWORD *)(a1 + 72) = 0;
        *(_QWORD *)(a1 + 80) = 7;
        *(_WORD *)(a1 + 56) = 0;
        *(_DWORD *)(a1 - 32) = -2147023673;
        *(_QWORD *)(a1 - 24) = 0;
        *(_DWORD *)(a1 - 96) = 1;
        std::wstring::~wstring(a1 + 56, v12, 2147943623LL);
        std::vector<std::shared_ptr<wil::ProfileDataItem<Windows::Data::Security::Passkey::PasskeyItemPdr>>>::_Tidy(a1 + 32);
        std::vector<std::shared_ptr<wil::ProfileDataItem<Windows::Data::Security::Passkey::PasskeyItemPdr>>>::_Tidy(a1 + 144);
        std::wstring::~wstring(a1 + 112, v15, v16);
        if ( v10 )
        {
          v17 = *v6;
          if ( _InterlockedExchangeAdd(*v6 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v17)(v17);
            if ( _InterlockedExchangeAdd(v17 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 8LL))(v17);
          }
        }
        goto LABEL_97;
      }
      v18 = (_QWORD *)(a1 + 168);
      wil::ProfileDataStore::GetTypeNameWideString<Windows::Data::Security::Passkey::RecoveryItemPdr>(a1 + 168);
      v19 = (__int64 *)(a1 + 200);
      *(_QWORD *)(a1 + 200) = 0;
      CloudStore = wil::details::SharedCloudStoreState::GetCloudStore(v5[2], a1 + 232);
      *(_QWORD *)(a1 + 240) = *(_QWORD *)(a1 + 984);
      *(_QWORD *)(a1 + 272) = *(_QWORD *)(a1 + 976);
      v21 = *(_DWORD *)(a1 + 972);
      v22 = v21 & 1 | 2;
      if ( (v21 & 2) == 0 )
        v22 = *(_DWORD *)(a1 + 972) & 1;
      v23 = v22 | 4;
      if ( (v21 & 4) == 0 )
        v23 = v22;
      v24 = v23 | 0x10;
      if ( (v21 & 0x10) == 0 )
        v24 = v23;
      v25 = v24 | 8;
      if ( (v21 & 8) == 0 )
        v25 = v24;
      *(_DWORD *)(a1 + 304) = v25;
      v26 = *(_DWORD *)(a1 + 968);
      v27 = v26 & 1;
      if ( (v26 & 4) != 0 )
      {
        if ( (v26 & 1) == 0 )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x8FE,
            (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil\\profiledatastore.h",
            (const char *)4);
        v27 |= 2u;
      }
      v28 = v27 | 4;
      if ( (v26 & 8) == 0 )
        v28 = v27;
      v29 = v28 | 8;
      if ( (v26 & 0x10) == 0 )
        v29 = v28;
      v30 = v29 | 0x10;
      if ( (v26 & 0x20) == 0 )
        v30 = v29;
      *(_DWORD *)(a1 + 308) = v30;
      v31 = *(_QWORD *)(a1 + 184);
      if ( *(_QWORD *)(a1 + 192) > 7u )
        v18 = (_QWORD *)*v18;
      if ( (_DWORD)v31 )
      {
        if ( *((_WORD *)v18 + (unsigned int)v31) )
          abort();
        v32 = a1 + 320;
        *(_DWORD *)(a1 + 320) = 1;
        *(_DWORD *)(a1 + 324) = v31;
        *(_QWORD *)(a1 + 336) = v18;
      }
      else
      {
        v32 = 0;
      }
      *(_QWORD *)(a1 + 312) = v32;
      *(_QWORD *)(a1 + 344) = *(_QWORD *)(a1 + 960);
      v33 = *(_QWORD *)(a1 + 952);
      *(_QWORD *)(a1 + 376) = *(_QWORD *)(v33 + 40);
      CollectionItemsAsync = winrt::impl::consume_Windows_Internal_Storage_Cloud_ICloudStore2<winrt::Windows::Internal::Storage::Cloud::CloudStore>::GetCollectionItemsAsync(
                               CloudStore,
                               (int)a1 + 408,
                               (int)v33 + 32,
                               (int)a1 + 376,
                               a1 + 344,
                               a1 + 312,
                               a1 + 308,
                               a1 + 304,
                               a1 + 272,
                               a1 + 240);
      wil::details::AsyncOpWaiter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::GetCollectionItemsResult>,winrt::Windows::Internal::Storage::Cloud::GetCollectionItemsResult>::AsyncOpWaiter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::GetCollectionItemsResult>,winrt::Windows::Internal::Storage::Cloud::GetCollectionItemsResult>(
        a1 + 208,
        a1 + 992,
        CollectionItemsAsync);
      if ( *(_QWORD *)(a1 + 408) )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 408);
      if ( *(_QWORD *)(a1 + 232) )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 232);
      v35 = (__int64 *)wil::details::AsyncOpWaiter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::GetCollectionItemsResult>,winrt::Windows::Internal::Storage::Cloud::GetCollectionItemsResult>::WaitForResult(
                         a1 + 208,
                         a1 + 416);
      if ( v19 != v35 )
      {
        v36 = *v35;
        *v35 = 0;
        *v19 = v36;
      }
      if ( *(_QWORD *)(a1 + 416) )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 416);
      wil::details::AsyncOpWaiter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>,winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>::~AsyncOpWaiter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>,winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>(a1 + 208);
      *(_QWORD *)(a1 + 568) = 0;
      *(_QWORD *)(a1 + 576) = 0;
      *(_QWORD *)(a1 + 584) = 0;
      v37 = winrt::impl::consume_Windows_Internal_Storage_Cloud_IGetCollectionItemsResult<winrt::Windows::Internal::Storage::Cloud::IGetCollectionItemsResult>::Items(
              a1 + 200,
              a1 + 592);
      v38 = winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::Storage::Cloud::CloudStoreData>,winrt::Windows::Internal::Storage::Cloud::CloudStoreData>::Size(v37);
      *(_QWORD *)(a1 + 936) = v38;
      if ( v38 > (unsigned __int64)((__int64)(*(_QWORD *)(a1 + 584) - *(_QWORD *)(a1 + 568)) >> 4) )
        std::vector<std::shared_ptr<wil::ProfileDataItem<Windows::Data::Security::Passkey::RecoveryItemPdr>>>::_Reallocate<0>(a1 + 568);
      if ( *(_QWORD *)(a1 + 592) )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 592);
      winrt::impl::consume_Windows_Internal_Storage_Cloud_IGetCollectionItemsResult<winrt::Windows::Internal::Storage::Cloud::IGetCollectionItemsResult>::Items(
        a1 + 200,
        a1 + 600);
      *(_QWORD *)(a1 + 608) = a1 + 600;
      *(_DWORD *)(a1 + 616) = 0;
      v39 = winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::Storage::Cloud::CloudStoreData>,winrt::Windows::Internal::Storage::Cloud::CloudStoreData>::Size(a1 + 600);
      v40 = 0;
      break;
    default:
      __debugbreak();
      return;
  }
  while ( v40 != v39 )
  {
    v41 = (_QWORD *)(a1 + 624);
    winrt::impl::fast_iterator<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::Storage::Cloud::CloudStoreData>>::operator*(
      a1 + 608,
      a1 + 624);
    v42 = *(_QWORD *)(a1 + 992);
    if ( v42 && *(_DWORD *)(v42 + 16) )
    {
      *(_OWORD *)(a1 + 720) = 0;
      *(_QWORD *)(a1 + 736) = 0;
      *(_QWORD *)(a1 + 744) = 7;
      *(_WORD *)(a1 + 720) = 0;
      *(_QWORD *)(a1 + 768) = 0;
      *(_QWORD *)(a1 + 760) = 0;
      *(_QWORD *)(a1 + 752) = 0;
      *(_QWORD *)(a1 + 640) = 0;
      *(_QWORD *)(a1 + 648) = 0;
      *(_QWORD *)(a1 + 656) = 0;
      std::wstring::wstring(a1 + 664, a1 + 720);
      *(_DWORD *)(a1 + 696) = -2147023673;
      *(_QWORD *)(a1 + 704) = 0;
      v43 = *(_QWORD *)(a1 + 656);
      *(_QWORD *)(a1 + 656) = 0;
      v44 = *(_QWORD *)(a1 + 648);
      *(_QWORD *)(a1 + 648) = 0;
      v45 = *(_QWORD *)(a1 + 640);
      *(_QWORD *)(a1 + 640) = 0;
      *(_QWORD *)(a1 - 88) = v45;
      *(_QWORD *)(a1 - 80) = v44;
      *(_QWORD *)(a1 - 72) = v43;
      *(_QWORD *)(a1 - 64) = *(_QWORD *)(a1 + 664);
      *(_QWORD *)(a1 - 56) = *(_QWORD *)(a1 + 672);
      *(_QWORD *)(a1 - 48) = *(_QWORD *)(a1 + 680);
      *(_QWORD *)(a1 - 40) = *(_QWORD *)(a1 + 688);
      *(_QWORD *)(a1 + 680) = 0;
      *(_QWORD *)(a1 + 688) = 7;
      *(_WORD *)(a1 + 664) = 0;
      *(_DWORD *)(a1 - 32) = -2147023673;
      *(_QWORD *)(a1 - 24) = 0;
      *(_DWORD *)(a1 - 96) = 1;
      std::wstring::~wstring(a1 + 664, v43, 2147943623LL);
      std::vector<std::shared_ptr<wil::ProfileDataItem<Windows::Data::Security::Passkey::PasskeyItemPdr>>>::_Tidy(a1 + 640);
      std::vector<std::shared_ptr<wil::ProfileDataItem<Windows::Data::Security::Passkey::PasskeyItemPdr>>>::_Tidy(a1 + 752);
      std::wstring::~wstring(a1 + 720, v46, v47);
      if ( *v41 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 624);
      if ( *(_QWORD *)(a1 + 600) )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 600);
      std::vector<std::shared_ptr<wil::ProfileDataItem<Windows::Data::Security::Passkey::PasskeyItemPdr>>>::_Tidy(a1 + 568);
      if ( *(_QWORD *)(a1 + 200) )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 200);
      std::wstring::~wstring(a1 + 168, v48, v49);
      if ( *(_QWORD *)(a1 + 24) )
      {
        v50 = *(volatile signed __int32 **)(a1 + 24);
        if ( _InterlockedExchangeAdd(v50 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v50)(v50);
          if ( _InterlockedExchangeAdd(v50 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v50 + 8LL))(v50);
        }
      }
      goto LABEL_97;
    }
    v51 = (_QWORD *)wil::ProfileDataStore::Unmarshal<Windows::Data::Security::Passkey::RecoveryItemPdr>(
                      a1 + 776,
                      a1 + 624,
                      *(unsigned int *)(a1 + 968));
    v52 = v51;
    v53 = *(_QWORD **)(a1 + 576);
    if ( v53 == *(_QWORD **)(a1 + 584) )
    {
      std::vector<std::shared_ptr<wil::ProfileDataItem<Windows::Data::Security::Passkey::PasskeyItemPdr>>>::_Emplace_reallocate<std::shared_ptr<wil::ProfileDataItem<Windows::Data::Security::Passkey::PasskeyItemPdr>>>(
        a1 + 568,
        v53,
        v51);
    }
    else
    {
      *v53 = 0;
      v53[1] = 0;
      *v53 = *v51;
      v53[1] = v51[1];
      *v51 = 0;
      v51[1] = 0;
      *(_QWORD *)(a1 + 576) += 16LL;
    }
    if ( *(_QWORD *)(a1 + 784) )
    {
      v54 = *(volatile signed __int32 **)(a1 + 784);
      if ( _InterlockedExchangeAdd(v54 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *, _QWORD *, _QWORD *))v54)(v54, v53, v52);
        if ( _InterlockedExchangeAdd(v54 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v54 + 8LL))(v54);
      }
    }
    if ( *v41 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 624);
    v40 = *(_DWORD *)(a1 + 616) + 1;
    *(_DWORD *)(a1 + 616) = v40;
  }
  if ( *(_QWORD *)(a1 + 600) )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 600);
  v74 = winrt::impl::consume_Windows_Internal_Storage_Cloud_IGetCollectionItemsResult<winrt::Windows::Internal::Storage::Cloud::IGetCollectionItemsResult>::RetryAfter(a1 + 200);
  v73 = *(_DWORD *)winrt::impl::consume_Windows_Internal_Storage_Cloud_IGetCollectionItemsResult<winrt::Windows::Internal::Storage::Cloud::IGetCollectionItemsResult>::ResultCode(
                     a1 + 200,
                     a1 + 880);
  v55 = (volatile signed __int32 **)(a1 + 920);
  v56 = winrt::impl::consume_Windows_Internal_Storage_Cloud_IGetCollectionItemsResult<winrt::Windows::Internal::Storage::Cloud::IGetCollectionItemsResult>::SyncToken(
          a1 + 200,
          a1 + 920);
  if ( *(_QWORD *)v56 )
    v57 = *(const WCHAR **)(*(_QWORD *)v56 + 16LL);
  else
    v57 = &String1;
  *(_OWORD *)(a1 + 888) = 0;
  *(_QWORD *)(a1 + 904) = 0;
  *(_QWORD *)(a1 + 912) = 0;
  v58 = -1;
  do
    ++v58;
  while ( v57[v58] );
  std::wstring::_Construct<1,unsigned short const *>(a1 + 888, v57, v58);
  v59 = *(_QWORD *)(a1 + 584);
  *(_QWORD *)(a1 + 584) = 0;
  v60 = *(_QWORD *)(a1 + 576);
  *(_QWORD *)(a1 + 576) = 0;
  v61 = *(_QWORD *)(a1 + 568);
  *(_QWORD *)(a1 + 568) = 0;
  *(_QWORD *)(a1 + 800) = v61;
  *(_QWORD *)(a1 + 808) = v60;
  *(_QWORD *)(a1 + 816) = v59;
  std::wstring::wstring(a1 + 824, a1 + 888);
  *(_DWORD *)(a1 + 856) = v73;
  *(_QWORD *)(a1 + 864) = v74;
  v62 = *(_QWORD *)(a1 + 816);
  *(_QWORD *)(a1 + 816) = 0;
  v63 = *(_QWORD *)(a1 + 808);
  *(_QWORD *)(a1 + 808) = 0;
  v64 = *(_QWORD *)(a1 + 800);
  *(_QWORD *)(a1 + 800) = 0;
  *(_QWORD *)(a1 - 88) = v64;
  *(_QWORD *)(a1 - 80) = v63;
  *(_QWORD *)(a1 - 72) = v62;
  *(_QWORD *)(a1 - 64) = *(_QWORD *)(a1 + 824);
  *(_QWORD *)(a1 - 56) = *(_QWORD *)(a1 + 832);
  *(_QWORD *)(a1 - 48) = *(_QWORD *)(a1 + 840);
  *(_QWORD *)(a1 - 40) = *(_QWORD *)(a1 + 848);
  *(_QWORD *)(a1 + 840) = 0;
  *(_QWORD *)(a1 + 848) = 7;
  *(_WORD *)(a1 + 824) = 0;
  *(_DWORD *)(a1 - 32) = *(_DWORD *)(a1 + 856);
  *(_QWORD *)(a1 - 24) = *(_QWORD *)(a1 + 864);
  *(_DWORD *)(a1 - 96) = 1;
  std::wstring::~wstring(a1 + 824, v62, a1 + 800);
  std::vector<std::shared_ptr<wil::ProfileDataItem<Windows::Data::Security::Passkey::PasskeyItemPdr>>>::_Tidy(a1 + 800);
  std::wstring::~wstring(a1 + 888, v65, v66);
  v67 = *v55;
  if ( *v55 )
  {
    v68 = _InterlockedDecrement(v67 + 6);
    if ( v68 )
    {
      if ( v68 < 0 )
        abort();
    }
    else
    {
      ProcessHeap = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v67);
    }
    *v55 = 0;
  }
  std::vector<std::shared_ptr<wil::ProfileDataItem<Windows::Data::Security::Passkey::PasskeyItemPdr>>>::_Tidy(a1 + 568);
  if ( *(_QWORD *)(a1 + 200) )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 200);
  std::wstring::~wstring(a1 + 168, v70, v71);
  if ( *(_QWORD *)(a1 + 24) )
  {
    v72 = *(volatile signed __int32 **)(a1 + 24);
    if ( _InterlockedExchangeAdd(v72 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v72)(v72);
      if ( _InterlockedExchangeAdd(v72 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v72 + 8LL))(v72);
    }
  }
LABEL_97:
  *(_QWORD *)(a1 + 928) = a1 - 112;
  *(_WORD *)(a1 + 8) = 0;
  `wil::details::coro::promise_base<wil::GetCollectionItemsResult<Windows::Data::Security::Passkey::PasskeyItemPdr>>::final_suspend'::`2'::awaiter::await_suspend();
}

```

## disassembly

```asm
0x1800280d0  mov     r11, rsp
0x1800280d3  mov     [r11+10h], rbx
0x1800280d7  mov     [r11+18h], rsi
0x1800280db  mov     [r11+8], rcx
0x1800280df  push    rdi
0x1800280e0  push    r12
0x1800280e2  push    r13
0x1800280e4  push    r14
0x1800280e6  push    r15
0x1800280e8  sub     rsp, 2D0h
0x1800280ef  mov     rax, cs:__security_cookie
0x1800280f6  xor     rax, rsp
0x1800280f9  mov     [rsp+2F8h+var_30], rax
0x180028101  mov     rdi, rcx
0x180028104  mov     [rsp+2F8h+var_2A0], rcx
0x180028109  movzx   eax, word ptr [rdi+8]
0x18002810d  mov     [rsp+2F8h+var_298], ax
0x180028112  inc     ax; switch 5 cases
0x180028115  mov     ecx, 4
0x18002811a  cmp     ax, cx
0x18002811d  ja      def_180028138; jumptable 0000000180028138 default case, case 0
0x180028123  movsx   rax, ax
0x180028127  lea     rdx, __ImageBase
0x18002812e  mov     ecx, ds:(jpt_180028138 - 180000000h)[rdx+rax*4]
0x180028135  add     rcx, rdx
0x180028138  jmp     rcx; switch jump
0x18002813a  jmp     loc_180028D43; jumptable 0000000180028138 case 3
0x18002813f  xor     esi, esi; jumptable 0000000180028138 case 2
0x180028141  mov     r12, [rdi+3B8h]
0x180028148  mov     [rdi+10h], rsi
0x18002814c  lea     r15, [rdi+18h]
0x180028150  mov     [r15], rsi
0x180028153  mov     rdx, [r12+8]
0x180028158  test    rdx, rdx
0x18002815b  jz      loc_180028D1D
0x180028161  mov     eax, [rdx+8]
0x180028164  jmp     short loc_180028170
0x180028166  lea     ecx, [rax+1]
0x180028169  lock cmpxchg [rdx+8], ecx
0x18002816e  jz      short loc_180028179
0x180028170  test    eax, eax
0x180028172  jnz     short loc_180028166
0x180028174  jmp     loc_180028D1D
0x180028179  mov     [rsp+2F8h+var_268], r15
0x180028181  mov     rax, [r12]
0x180028185  mov     [rdi+10h], rax
0x180028189  mov     r13, [r12+8]
0x18002818e  mov     [r15], r13
0x180028191  mov     rax, [rdi+3E0h]
0x180028198  test    rax, rax
0x18002819b  jz      loc_180028327
0x1800281a1  mov     eax, [rax+10h]
0x1800281a4  nop
0x1800281a5  test    eax, eax
0x1800281a7  jz      loc_180028327
0x1800281ad  lea     rbx, [rdi+70h]
0x1800281b1  xorps   xmm0, xmm0
0x1800281b4  movups  xmmword ptr [rbx], xmm0
0x1800281b7  mov     [rdi+80h], rsi
0x1800281be  mov     qword ptr [rdi+88h], 7
0x1800281c9  xor     eax, eax
0x1800281cb  mov     [rbx], ax
0x1800281ce  mov     [rdi+0A0h], rsi
0x1800281d5  mov     [rdi+98h], rsi
0x1800281dc  mov     [rdi+90h], rsi
0x1800281e3  lea     r14, [rdi+20h]
0x1800281e7  mov     [r14], rsi
0x1800281ea  mov     [rdi+28h], rsi
0x1800281ee  mov     [rdi+30h], rsi
0x1800281f2  lea     r12, [rdi+38h]
0x1800281f6  mov     rdx, rbx
0x1800281f9  mov     rcx, r12
0x1800281fc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180028201  mov     r8d, 800704C7h
0x180028207  mov     [rdi+58h], r8d
0x18002820b  mov     [rdi+60h], rsi
0x18002820f  mov     rdx, [rdi+30h]
0x180028213  mov     [rsp+2F8h+var_198], rdx
0x18002821b  mov     [rdi+30h], rsi
0x18002821f  mov     rcx, [rdi+28h]
0x180028223  mov     [rsp+2F8h+var_1A0], rcx
0x18002822b  mov     [rdi+28h], rsi
0x18002822f  mov     rax, [r14]
0x180028232  mov     [rsp+2F8h+var_1A8], rax
0x18002823a  mov     [r14], rsi
0x18002823d  mov     [rdi-58h], rax
0x180028241  mov     [rdi-50h], rcx
0x180028245  mov     [rdi-48h], rdx
0x180028249  mov     rax, [r12]
0x18002824d  mov     [rsp+2F8h+var_190], rax
0x180028255  mov     [rdi-40h], rax
0x180028259  mov     rax, [rdi+40h]
0x18002825d  mov     [rsp+2F8h+var_188], rax
0x180028265  mov     [rdi-38h], rax
0x180028269  mov     rax, [rdi+48h]
0x18002826d  mov     [rsp+2F8h+var_180], rax
0x180028275  mov     [rdi-30h], rax
0x180028279  mov     rax, [rdi+50h]
0x18002827d  mov     [rsp+2F8h+var_178], rax
0x180028285  mov     [rdi-28h], rax
0x180028289  mov     [rdi+48h], rsi
0x18002828d  mov     qword ptr [rdi+50h], 7
0x180028295  xor     eax, eax
0x180028297  mov     [r12], ax
0x18002829c  mov     [rdi-20h], r8d
0x1800282a0  mov     [rdi-18h], rsi
0x1800282a4  mov     dword ptr [rdi-60h], 1
0x1800282ab  mov     rcx, r12
0x1800282ae  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800282b3  mov     rcx, r14
0x1800282b6  call    ?_Tidy@?$vector@V?$shared_ptr@V?$ProfileDataItem@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@wil@@@std@@V?$allocator@V?$shared_ptr@V?$ProfileDataItem@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@wil@@@std@@@2@@std@@AEAAXXZ; std::vector<std::shared_ptr<wil::ProfileDataItem<Windows::Data::Security::Passkey::PasskeyItemPdr>>>::_Tidy(void)
0x1800282bb  nop
0x1800282bc  lea     rcx, [rdi+90h]
0x1800282c3  call    ?_Tidy@?$vector@V?$shared_ptr@V?$ProfileDataItem@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@wil@@@std@@V?$allocator@V?$shared_ptr@V?$ProfileDataItem@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@wil@@@std@@@2@@std@@AEAAXXZ; std::vector<std::shared_ptr<wil::ProfileDataItem<Windows::Data::Security::Passkey::PasskeyItemPdr>>>::_Tidy(void)
0x1800282c8  nop
0x1800282c9  mov     rcx, rbx
0x1800282cc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800282d1  nop
0x1800282d2  mov     [rsp+2F8h+var_278], r13
0x1800282da  test    r13, r13
0x1800282dd  jz      short loc_180028322
0x1800282df  mov     rsi, [r15]
0x1800282e2  mov     [rsp+2F8h+var_278], rsi
0x1800282ea  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800282ee  mov     eax, ebx
0x1800282f0  lock xadd [rsi+8], eax
0x1800282f5  add     eax, ebx
0x1800282f7  jnz     short loc_180028322
0x1800282f9  mov     rax, [rsi]
0x1800282fc  mov     rcx, rsi
0x1800282ff  mov     rax, [rax]
0x180028302  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028307  mov     eax, ebx
0x180028309  lock xadd [rsi+0Ch], eax
0x18002830e  add     eax, ebx
0x180028310  jnz     short loc_180028322
0x180028312  mov     rax, [rsi]
0x180028315  mov     rcx, rsi
0x180028318  mov     rax, [rax+8]
0x18002831c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028321  nop
0x180028322  jmp     loc_180028D28
0x180028327  lea     rbx, [rdi+0A8h]
0x18002832e  mov     [rsp+2F8h+var_2A8], rbx
0x180028333  mov     rcx, rbx
0x180028336  call    ??$GetTypeNameWideString@URecoveryItemPdr@Passkey@Security@Data@Windows@@@ProfileDataStore@wil@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; wil::ProfileDataStore::GetTypeNameWideString<Windows::Data::Security::Passkey::RecoveryItemPdr>(void)
0x18002833b  nop
0x18002833c  lea     r14, [rdi+0C8h]
0x180028343  mov     [rsp+2F8h+var_290], r14
0x180028348  mov     [r14], rsi
0x18002834b  lea     r13, [rdi+0E8h]
0x180028352  mov     rdx, r13
0x180028355  mov     rcx, [r12+10h]
0x18002835a  call    ?GetCloudStore@SharedCloudStoreState@details@wil@@QEAA?BUCloudStore@Cloud@Storage@Internal@Windows@winrt@@XZ; wil::details::SharedCloudStoreState::GetCloudStore(void)
0x18002835f  mov     r11, rax
0x180028362  lea     r12, [rdi+0F0h]
0x180028369  mov     rcx, [rdi+3D8h]
0x180028370  mov     [r12], rcx
0x180028374  mov     rcx, [rdi+3D0h]
0x18002837b  mov     [rdi+110h], rcx
0x180028382  mov     r8d, [rdi+3CCh]
0x180028389  mov     ecx, r8d
0x18002838c  and     ecx, 1
0x18002838f  mov     edx, ecx
0x180028391  or      edx, 2
0x180028394  bt      r8d, 1
0x180028399  cmovnb  edx, ecx
0x18002839c  mov     r9d, 4; char *
0x1800283a2  mov     ecx, edx
0x1800283a4  or      ecx, r9d
0x1800283a7  test    r9d, r8d
0x1800283aa  cmovz   ecx, edx
0x1800283ad  mov     edx, ecx
0x1800283af  or      edx, 10h
0x1800283b2  bt      r8d, 4
0x1800283b7  cmovnb  edx, ecx
0x1800283ba  mov     eax, edx
0x1800283bc  or      eax, 8
0x1800283bf  bt      r8d, 3
0x1800283c4  cmovnb  eax, edx
0x1800283c7  mov     [rdi+130h], eax
0x1800283cd  mov     r8d, [r15+3B0h]
0x1800283d4  mov     edx, r8d
0x1800283d7  and     edx, 1
0x1800283da  test    r9d, r8d
0x1800283dd  jz      short loc_180028402
0x1800283df  mov     rcx, [rsp+2F8h]; this
0x1800283e7  mov     al, dl
0x1800283e9  xor     al, 1
0x1800283eb  jz      short loc_1800283FF
0x1800283ed  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\sdk\\inc\\wil\\pr"...
0x1800283f4  mov     edx, 8FEh; void *
0x1800283f9  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800283ff  or      edx, 2
0x180028402  mov     ecx, edx
0x180028404  or      ecx, r9d
0x180028407  bt      r8d, 3
0x18002840c  cmovnb  ecx, edx
0x18002840f  mov     edx, ecx
0x180028411  or      edx, 8
0x180028414  bt      r8d, 4
0x180028419  cmovnb  edx, ecx
0x18002841c  lea     r10, [rdi+134h]
0x180028423  mov     eax, edx
0x180028425  or      eax, 10h
0x180028428  bt      r8d, 5
0x18002842d  cmovnb  eax, edx
0x180028430  mov     [r10], eax
0x180028433  mov     rcx, [rdi+0B8h]
0x18002843a  mov     [rsp+2F8h+var_F8], rcx
0x180028442  mov     rax, [rdi+0C0h]
0x180028449  mov     [rsp+2F8h+var_F0], rax
0x180028451  cmp     rax, 7
0x180028455  jbe     short loc_180028462
0x180028457  mov     rbx, [rbx]
0x18002845a  mov     [rsp+2F8h+var_108], rbx
0x180028462  test    ecx, ecx
0x180028464  jnz     short loc_18002846B
0x180028466  mov     rax, rsi
0x180028469  jmp     short loc_180028494
0x18002846b  mov     eax, ecx
0x18002846d  cmp     [rbx+rax*2], si
0x180028471  jz      short loc_18002847A
0x180028473  call    cs:__imp_abort
0x18002847a  lea     rax, [rdi+140h]
0x180028481  mov     dword ptr [rax], 1
0x180028487  mov     [rdi+144h], ecx
0x18002848d  mov     [rdi+150h], rbx
0x180028494  mov     [rdi+138h], rax
0x18002849b  lea     rcx, [rdi+158h]
0x1800284a2  mov     rax, [rdi+3C0h]
0x1800284a9  mov     [rcx], rax
0x1800284ac  mov     r8, [rdi+3B8h]
0x1800284b3  lea     r9, [rdi+178h]
0x1800284ba  mov     rax, [r8+28h]
0x1800284be  mov     [r9], rax
0x1800284c1  lea     rbx, [rdi+198h]
0x1800284c8  lea     rax, [rdi+138h]
0x1800284cf  add     r8, 20h ; ' '
0x1800284d3  mov     [rsp+2F8h+var_2B0], r12
0x1800284d8  lea     rdx, [rdi+110h]
0x1800284df  mov     [rsp+2F8h+var_2B8], rdx
0x1800284e4  lea     rdx, [rdi+130h]
0x1800284eb  mov     [rsp+2F8h+var_2C0], rdx
0x1800284f0  mov     [rsp+2F8h+var_2C8], r10
0x1800284f5  mov     [rsp+2F8h+var_2D0], rax
0x1800284fa  mov     [rsp+2F8h+var_2D8], rcx
0x1800284ff  mov     rdx, rbx
0x180028502  mov     rcx, r11
0x180028505  call    ?GetCollectionItemsAsync@?$consume_Windows_Internal_Storage_Cloud_ICloudStore2@UCloudStore@Cloud@Storage@Internal@Windows@winrt@@@impl@winrt@@QEBA@AEBW4PartitionKind@Cloud@Storage@Internal@Windows@3@AEBUhstring@param@3@11AEBW4LoadOptions@56783@AEBW4CollectionOptions@56783@11@Z; winrt::impl::consume_Windows_Internal_Storage_Cloud_ICloudStore2<winrt::Windows::Internal::Storage::Cloud::CloudStore>::GetCollectionItemsAsync(winrt::Windows::Internal::Storage::Cloud::PartitionKind const &,winrt::param::hstring const &,winrt::param::hstring const &,winrt::param::hstring const &,winrt::Windows::Internal::Storage::Cloud::LoadOptions const &,winrt::Windows::Internal::Storage::Cloud::CollectionOptions const &,winrt::param::hstring const &,winrt::param::hstring const &)
0x18002850a  nop
0x18002850b  lea     r15, [rdi+0D0h]
0x180028512  mov     r8, rax
0x180028515  lea     rdx, [rdi+3E0h]
0x18002851c  mov     rcx, r15
0x18002851f  call    ??0?$AsyncOpWaiter@U?$IAsyncOperation@UGetCollectionItemsResult@Cloud@Storage@Internal@Windows@winrt@@@Foundation@Windows@winrt@@UGetCollectionItemsResult@Cloud@Storage@Internal@34@@details@wil@@QEAA@AEBVcancellation_token@Concurrency@@AEBU?$IAsyncOperation@UGetCollectionItemsResult@Cloud@Storage@Internal@Windows@winrt@@@Foundation@Windows@winrt@@@Z; wil::details::AsyncOpWaiter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::GetCollectionItemsResult>,winrt::Windows::Internal::Storage::Cloud::GetCollectionItemsResult>::AsyncOpWaiter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::GetCollectionItemsResult>,winrt::Windows::Internal::Storage::Cloud::GetCollectionItemsResult>(Concurrency::cancellation_token const &,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::GetCollectionItemsResult> const &)
0x180028524  nop
0x180028525  mov     rax, [rbx]
0x180028528  mov     [rsp+2F8h+var_238], rax
0x180028530  test    rax, rax
0x180028533  jz      short loc_18002853E
0x180028535  mov     rcx, rbx
0x180028538  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18002853d  nop
0x18002853e  mov     rax, [r13+0]
0x180028542  mov     [rsp+2F8h+var_230], rax
0x18002854a  test    rax, rax
0x18002854d  jz      short loc_180028557
0x18002854f  mov     rcx, r13
0x180028552  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180028557  lea     rbx, [rdi+1A0h]
0x18002855e  mov     rdx, rbx
0x180028561  mov     rcx, r15
0x180028564  call    ?WaitForResult@?$AsyncOpWaiter@U?$IAsyncOperation@UGetCollectionItemsResult@Cloud@Storage@Internal@Windows@winrt@@@Foundation@Windows@winrt@@UGetCollectionItemsResult@Cloud@Storage@Internal@34@@details@wil@@QEAA?AUGetCollectionItemsResult@Cloud@Storage@Internal@Windows@winrt@@XZ; wil::details::AsyncOpWaiter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::GetCollectionItemsResult>,winrt::Windows::Internal::Storage::Cloud::GetCollectionItemsResult>::WaitForResult(void)
0x180028569  cmp     r14, rax
0x18002856c  jz      short loc_180028577
0x18002856e  mov     rdx, [rax]
0x180028571  mov     [rax], rsi
0x180028574  mov     [r14], rdx
0x180028577  mov     rax, [rbx]
0x18002857a  mov     [rsp+2F8h+var_228], rax
0x180028582  test    rax, rax
0x180028585  jz      short loc_180028590
0x180028587  mov     rcx, rbx
0x18002858a  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18002858f  nop
0x180028590  mov     rcx, r15
0x180028593  call    ??1?$AsyncOpWaiter@U?$IAsyncOperation@UCloudStoreSaveResult@Cloud@Storage@Internal@Windows@winrt@@@Foundation@Windows@winrt@@UCloudStoreSaveResult@Cloud@Storage@Internal@34@@details@wil@@QEAA@XZ; wil::details::AsyncOpWaiter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>,winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>::~AsyncOpWaiter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>,winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>(void)
0x180028598  nop
0x180028599  lea     r15, [rdi+238h]
0x1800285a0  mov     [r15], rsi
0x1800285a3  mov     [rdi+240h], rsi
0x1800285aa  mov     [rdi+248h], rsi
0x1800285b1  lea     rbx, [rdi+250h]
0x1800285b8  mov     rdx, rbx
0x1800285bb  mov     rcx, r14
0x1800285be  call    ?Items@?$consume_Windows_Internal_Storage_Cloud_IGetCollectionItemsResult@UIGetCollectionItemsResult@Cloud@Storage@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_Storage_Cloud_IGetCollectionItemsResult<winrt::Windows::Internal::Storage::Cloud::IGetCollectionItemsResult>::Items(void)
0x1800285c3  nop
0x1800285c4  mov     rcx, rax
0x1800285c7  call    ?Size@?$consume_Windows_Foundation_Collections_IVectorView@U?$IVectorView@UCloudStoreData@Cloud@Storage@Internal@Windows@winrt@@@Collections@Foundation@Windows@winrt@@UCloudStoreData@Cloud@Storage@Internal@45@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::Storage::Cloud::CloudStoreData>,winrt::Windows::Internal::Storage::Cloud::CloudStoreData>::Size(void)
  ... truncated ...
```
