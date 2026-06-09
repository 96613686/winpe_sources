# wil::ProfileDataStore::CallGetCollectionItemsAsync$_ResumeCoro$1_Windows::Data::Security::Passkey::ScenarioKeysItemPdr_

- ea: `0x180028e00`
- end: `0x180029b24`
- name: `wil::ProfileDataStore::CallGetCollectionItemsAsync$_ResumeCoro$1_Windows::Data::Security::Passkey::ScenarioKeysItemPdr_`
- size: `3364`
- prototype: ``
- caller_count: `1`
- callee_count: `30`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180029f6c`

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
- `0x180028e00`
- `0x180037b84`
- `0x1800402c8`
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

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180029aa4`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180029aa4`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800291a3`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180029935`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800291a3`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180029935`

## pseudocode

```c
void __fastcall wil::ProfileDataStore::CallGetCollectionItemsAsync__ResumeCoro_1_Windows::Data::Security::Passkey::ScenarioKeysItemPdr_(
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
      wil::ProfileDataStore::GetTypeNameWideString<Windows::Data::Security::Passkey::ScenarioKeysItemPdr>(a1 + 168);
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
    v51 = (_QWORD *)wil::ProfileDataStore::Unmarshal<Windows::Data::Security::Passkey::ScenarioKeysItemPdr>(
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
0x180028e00  mov     r11, rsp
0x180028e03  mov     [r11+10h], rbx
0x180028e07  mov     [r11+18h], rsi
0x180028e0b  mov     [r11+8], rcx
0x180028e0f  push    rdi
0x180028e10  push    r12
0x180028e12  push    r13
0x180028e14  push    r14
0x180028e16  push    r15
0x180028e18  sub     rsp, 2D0h
0x180028e1f  mov     rax, cs:__security_cookie
0x180028e26  xor     rax, rsp
0x180028e29  mov     [rsp+2F8h+var_30], rax
0x180028e31  mov     rdi, rcx
0x180028e34  mov     [rsp+2F8h+var_2A0], rcx
0x180028e39  movzx   eax, word ptr [rdi+8]
0x180028e3d  mov     [rsp+2F8h+var_298], ax
0x180028e42  inc     ax; switch 5 cases
0x180028e45  mov     ecx, 4
0x180028e4a  cmp     ax, cx
0x180028e4d  ja      def_180028E68; jumptable 0000000180028E68 default case, case 0
0x180028e53  movsx   rax, ax
0x180028e57  lea     rdx, __ImageBase
0x180028e5e  mov     ecx, ds:(jpt_180028E68 - 180000000h)[rdx+rax*4]
0x180028e65  add     rcx, rdx
0x180028e68  jmp     rcx; switch jump
0x180028e6a  jmp     loc_180029A73; jumptable 0000000180028E68 case 3
0x180028e6f  xor     esi, esi; jumptable 0000000180028E68 case 2
0x180028e71  mov     r12, [rdi+3B8h]
0x180028e78  mov     [rdi+10h], rsi
0x180028e7c  lea     r15, [rdi+18h]
0x180028e80  mov     [r15], rsi
0x180028e83  mov     rdx, [r12+8]
0x180028e88  test    rdx, rdx
0x180028e8b  jz      loc_180029A4D
0x180028e91  mov     eax, [rdx+8]
0x180028e94  jmp     short loc_180028EA0
0x180028e96  lea     ecx, [rax+1]
0x180028e99  lock cmpxchg [rdx+8], ecx
0x180028e9e  jz      short loc_180028EA9
0x180028ea0  test    eax, eax
0x180028ea2  jnz     short loc_180028E96
0x180028ea4  jmp     loc_180029A4D
0x180028ea9  mov     [rsp+2F8h+var_268], r15
0x180028eb1  mov     rax, [r12]
0x180028eb5  mov     [rdi+10h], rax
0x180028eb9  mov     r13, [r12+8]
0x180028ebe  mov     [r15], r13
0x180028ec1  mov     rax, [rdi+3E0h]
0x180028ec8  test    rax, rax
0x180028ecb  jz      loc_180029057
0x180028ed1  mov     eax, [rax+10h]
0x180028ed4  nop
0x180028ed5  test    eax, eax
0x180028ed7  jz      loc_180029057
0x180028edd  lea     rbx, [rdi+70h]
0x180028ee1  xorps   xmm0, xmm0
0x180028ee4  movups  xmmword ptr [rbx], xmm0
0x180028ee7  mov     [rdi+80h], rsi
0x180028eee  mov     qword ptr [rdi+88h], 7
0x180028ef9  xor     eax, eax
0x180028efb  mov     [rbx], ax
0x180028efe  mov     [rdi+0A0h], rsi
0x180028f05  mov     [rdi+98h], rsi
0x180028f0c  mov     [rdi+90h], rsi
0x180028f13  lea     r14, [rdi+20h]
0x180028f17  mov     [r14], rsi
0x180028f1a  mov     [rdi+28h], rsi
0x180028f1e  mov     [rdi+30h], rsi
0x180028f22  lea     r12, [rdi+38h]
0x180028f26  mov     rdx, rbx
0x180028f29  mov     rcx, r12
0x180028f2c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180028f31  mov     r8d, 800704C7h
0x180028f37  mov     [rdi+58h], r8d
0x180028f3b  mov     [rdi+60h], rsi
0x180028f3f  mov     rdx, [rdi+30h]
0x180028f43  mov     [rsp+2F8h+var_198], rdx
0x180028f4b  mov     [rdi+30h], rsi
0x180028f4f  mov     rcx, [rdi+28h]
0x180028f53  mov     [rsp+2F8h+var_1A0], rcx
0x180028f5b  mov     [rdi+28h], rsi
0x180028f5f  mov     rax, [r14]
0x180028f62  mov     [rsp+2F8h+var_1A8], rax
0x180028f6a  mov     [r14], rsi
0x180028f6d  mov     [rdi-58h], rax
0x180028f71  mov     [rdi-50h], rcx
0x180028f75  mov     [rdi-48h], rdx
0x180028f79  mov     rax, [r12]
0x180028f7d  mov     [rsp+2F8h+var_190], rax
0x180028f85  mov     [rdi-40h], rax
0x180028f89  mov     rax, [rdi+40h]
0x180028f8d  mov     [rsp+2F8h+var_188], rax
0x180028f95  mov     [rdi-38h], rax
0x180028f99  mov     rax, [rdi+48h]
0x180028f9d  mov     [rsp+2F8h+var_180], rax
0x180028fa5  mov     [rdi-30h], rax
0x180028fa9  mov     rax, [rdi+50h]
0x180028fad  mov     [rsp+2F8h+var_178], rax
0x180028fb5  mov     [rdi-28h], rax
0x180028fb9  mov     [rdi+48h], rsi
0x180028fbd  mov     qword ptr [rdi+50h], 7
0x180028fc5  xor     eax, eax
0x180028fc7  mov     [r12], ax
0x180028fcc  mov     [rdi-20h], r8d
0x180028fd0  mov     [rdi-18h], rsi
0x180028fd4  mov     dword ptr [rdi-60h], 1
0x180028fdb  mov     rcx, r12
0x180028fde  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180028fe3  mov     rcx, r14
0x180028fe6  call    ?_Tidy@?$vector@V?$shared_ptr@V?$ProfileDataItem@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@wil@@@std@@V?$allocator@V?$shared_ptr@V?$ProfileDataItem@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@wil@@@std@@@2@@std@@AEAAXXZ; std::vector<std::shared_ptr<wil::ProfileDataItem<Windows::Data::Security::Passkey::PasskeyItemPdr>>>::_Tidy(void)
0x180028feb  nop
0x180028fec  lea     rcx, [rdi+90h]
0x180028ff3  call    ?_Tidy@?$vector@V?$shared_ptr@V?$ProfileDataItem@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@wil@@@std@@V?$allocator@V?$shared_ptr@V?$ProfileDataItem@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@wil@@@std@@@2@@std@@AEAAXXZ; std::vector<std::shared_ptr<wil::ProfileDataItem<Windows::Data::Security::Passkey::PasskeyItemPdr>>>::_Tidy(void)
0x180028ff8  nop
0x180028ff9  mov     rcx, rbx
0x180028ffc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180029001  nop
0x180029002  mov     [rsp+2F8h+var_278], r13
0x18002900a  test    r13, r13
0x18002900d  jz      short loc_180029052
0x18002900f  mov     rsi, [r15]
0x180029012  mov     [rsp+2F8h+var_278], rsi
0x18002901a  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002901e  mov     eax, ebx
0x180029020  lock xadd [rsi+8], eax
0x180029025  add     eax, ebx
0x180029027  jnz     short loc_180029052
0x180029029  mov     rax, [rsi]
0x18002902c  mov     rcx, rsi
0x18002902f  mov     rax, [rax]
0x180029032  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029037  mov     eax, ebx
0x180029039  lock xadd [rsi+0Ch], eax
0x18002903e  add     eax, ebx
0x180029040  jnz     short loc_180029052
0x180029042  mov     rax, [rsi]
0x180029045  mov     rcx, rsi
0x180029048  mov     rax, [rax+8]
0x18002904c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029051  nop
0x180029052  jmp     loc_180029A58
0x180029057  lea     rbx, [rdi+0A8h]
0x18002905e  mov     [rsp+2F8h+var_2A8], rbx
0x180029063  mov     rcx, rbx
0x180029066  call    ??$GetTypeNameWideString@UScenarioKeysItemPdr@Passkey@Security@Data@Windows@@@ProfileDataStore@wil@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; wil::ProfileDataStore::GetTypeNameWideString<Windows::Data::Security::Passkey::ScenarioKeysItemPdr>(void)
0x18002906b  nop
0x18002906c  lea     r14, [rdi+0C8h]
0x180029073  mov     [rsp+2F8h+var_290], r14
0x180029078  mov     [r14], rsi
0x18002907b  lea     r13, [rdi+0E8h]
0x180029082  mov     rdx, r13
0x180029085  mov     rcx, [r12+10h]
0x18002908a  call    ?GetCloudStore@SharedCloudStoreState@details@wil@@QEAA?BUCloudStore@Cloud@Storage@Internal@Windows@winrt@@XZ; wil::details::SharedCloudStoreState::GetCloudStore(void)
0x18002908f  mov     r11, rax
0x180029092  lea     r12, [rdi+0F0h]
0x180029099  mov     rcx, [rdi+3D8h]
0x1800290a0  mov     [r12], rcx
0x1800290a4  mov     rcx, [rdi+3D0h]
0x1800290ab  mov     [rdi+110h], rcx
0x1800290b2  mov     r8d, [rdi+3CCh]
0x1800290b9  mov     ecx, r8d
0x1800290bc  and     ecx, 1
0x1800290bf  mov     edx, ecx
0x1800290c1  or      edx, 2
0x1800290c4  bt      r8d, 1
0x1800290c9  cmovnb  edx, ecx
0x1800290cc  mov     r9d, 4; char *
0x1800290d2  mov     ecx, edx
0x1800290d4  or      ecx, r9d
0x1800290d7  test    r9d, r8d
0x1800290da  cmovz   ecx, edx
0x1800290dd  mov     edx, ecx
0x1800290df  or      edx, 10h
0x1800290e2  bt      r8d, 4
0x1800290e7  cmovnb  edx, ecx
0x1800290ea  mov     eax, edx
0x1800290ec  or      eax, 8
0x1800290ef  bt      r8d, 3
0x1800290f4  cmovnb  eax, edx
0x1800290f7  mov     [rdi+130h], eax
0x1800290fd  mov     r8d, [r15+3B0h]
0x180029104  mov     edx, r8d
0x180029107  and     edx, 1
0x18002910a  test    r9d, r8d
0x18002910d  jz      short loc_180029132
0x18002910f  mov     rcx, [rsp+2F8h]; this
0x180029117  mov     al, dl
0x180029119  xor     al, 1
0x18002911b  jz      short loc_18002912F
0x18002911d  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\sdk\\inc\\wil\\pr"...
0x180029124  mov     edx, 8FEh; void *
0x180029129  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18002912f  or      edx, 2
0x180029132  mov     ecx, edx
0x180029134  or      ecx, r9d
0x180029137  bt      r8d, 3
0x18002913c  cmovnb  ecx, edx
0x18002913f  mov     edx, ecx
0x180029141  or      edx, 8
0x180029144  bt      r8d, 4
0x180029149  cmovnb  edx, ecx
0x18002914c  lea     r10, [rdi+134h]
0x180029153  mov     eax, edx
0x180029155  or      eax, 10h
0x180029158  bt      r8d, 5
0x18002915d  cmovnb  eax, edx
0x180029160  mov     [r10], eax
0x180029163  mov     rcx, [rdi+0B8h]
0x18002916a  mov     [rsp+2F8h+var_F8], rcx
0x180029172  mov     rax, [rdi+0C0h]
0x180029179  mov     [rsp+2F8h+var_F0], rax
0x180029181  cmp     rax, 7
0x180029185  jbe     short loc_180029192
0x180029187  mov     rbx, [rbx]
0x18002918a  mov     [rsp+2F8h+var_108], rbx
0x180029192  test    ecx, ecx
0x180029194  jnz     short loc_18002919B
0x180029196  mov     rax, rsi
0x180029199  jmp     short loc_1800291C4
0x18002919b  mov     eax, ecx
0x18002919d  cmp     [rbx+rax*2], si
0x1800291a1  jz      short loc_1800291AA
0x1800291a3  call    cs:__imp_abort
0x1800291aa  lea     rax, [rdi+140h]
0x1800291b1  mov     dword ptr [rax], 1
0x1800291b7  mov     [rdi+144h], ecx
0x1800291bd  mov     [rdi+150h], rbx
0x1800291c4  mov     [rdi+138h], rax
0x1800291cb  lea     rcx, [rdi+158h]
0x1800291d2  mov     rax, [rdi+3C0h]
0x1800291d9  mov     [rcx], rax
0x1800291dc  mov     r8, [rdi+3B8h]
0x1800291e3  lea     r9, [rdi+178h]
0x1800291ea  mov     rax, [r8+28h]
0x1800291ee  mov     [r9], rax
0x1800291f1  lea     rbx, [rdi+198h]
0x1800291f8  lea     rax, [rdi+138h]
0x1800291ff  add     r8, 20h ; ' '
0x180029203  mov     [rsp+2F8h+var_2B0], r12
0x180029208  lea     rdx, [rdi+110h]
0x18002920f  mov     [rsp+2F8h+var_2B8], rdx
0x180029214  lea     rdx, [rdi+130h]
0x18002921b  mov     [rsp+2F8h+var_2C0], rdx
0x180029220  mov     [rsp+2F8h+var_2C8], r10
0x180029225  mov     [rsp+2F8h+var_2D0], rax
0x18002922a  mov     [rsp+2F8h+var_2D8], rcx
0x18002922f  mov     rdx, rbx
0x180029232  mov     rcx, r11
0x180029235  call    ?GetCollectionItemsAsync@?$consume_Windows_Internal_Storage_Cloud_ICloudStore2@UCloudStore@Cloud@Storage@Internal@Windows@winrt@@@impl@winrt@@QEBA@AEBW4PartitionKind@Cloud@Storage@Internal@Windows@3@AEBUhstring@param@3@11AEBW4LoadOptions@56783@AEBW4CollectionOptions@56783@11@Z; winrt::impl::consume_Windows_Internal_Storage_Cloud_ICloudStore2<winrt::Windows::Internal::Storage::Cloud::CloudStore>::GetCollectionItemsAsync(winrt::Windows::Internal::Storage::Cloud::PartitionKind const &,winrt::param::hstring const &,winrt::param::hstring const &,winrt::param::hstring const &,winrt::Windows::Internal::Storage::Cloud::LoadOptions const &,winrt::Windows::Internal::Storage::Cloud::CollectionOptions const &,winrt::param::hstring const &,winrt::param::hstring const &)
0x18002923a  nop
0x18002923b  lea     r15, [rdi+0D0h]
0x180029242  mov     r8, rax
0x180029245  lea     rdx, [rdi+3E0h]
0x18002924c  mov     rcx, r15
0x18002924f  call    ??0?$AsyncOpWaiter@U?$IAsyncOperation@UGetCollectionItemsResult@Cloud@Storage@Internal@Windows@winrt@@@Foundation@Windows@winrt@@UGetCollectionItemsResult@Cloud@Storage@Internal@34@@details@wil@@QEAA@AEBVcancellation_token@Concurrency@@AEBU?$IAsyncOperation@UGetCollectionItemsResult@Cloud@Storage@Internal@Windows@winrt@@@Foundation@Windows@winrt@@@Z; wil::details::AsyncOpWaiter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::GetCollectionItemsResult>,winrt::Windows::Internal::Storage::Cloud::GetCollectionItemsResult>::AsyncOpWaiter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::GetCollectionItemsResult>,winrt::Windows::Internal::Storage::Cloud::GetCollectionItemsResult>(Concurrency::cancellation_token const &,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::GetCollectionItemsResult> const &)
0x180029254  nop
0x180029255  mov     rax, [rbx]
0x180029258  mov     [rsp+2F8h+var_238], rax
0x180029260  test    rax, rax
0x180029263  jz      short loc_18002926E
0x180029265  mov     rcx, rbx
0x180029268  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18002926d  nop
0x18002926e  mov     rax, [r13+0]
0x180029272  mov     [rsp+2F8h+var_230], rax
0x18002927a  test    rax, rax
0x18002927d  jz      short loc_180029287
0x18002927f  mov     rcx, r13
0x180029282  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180029287  lea     rbx, [rdi+1A0h]
0x18002928e  mov     rdx, rbx
0x180029291  mov     rcx, r15
0x180029294  call    ?WaitForResult@?$AsyncOpWaiter@U?$IAsyncOperation@UGetCollectionItemsResult@Cloud@Storage@Internal@Windows@winrt@@@Foundation@Windows@winrt@@UGetCollectionItemsResult@Cloud@Storage@Internal@34@@details@wil@@QEAA?AUGetCollectionItemsResult@Cloud@Storage@Internal@Windows@winrt@@XZ; wil::details::AsyncOpWaiter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::GetCollectionItemsResult>,winrt::Windows::Internal::Storage::Cloud::GetCollectionItemsResult>::WaitForResult(void)
0x180029299  cmp     r14, rax
0x18002929c  jz      short loc_1800292A7
0x18002929e  mov     rdx, [rax]
0x1800292a1  mov     [rax], rsi
0x1800292a4  mov     [r14], rdx
0x1800292a7  mov     rax, [rbx]
0x1800292aa  mov     [rsp+2F8h+var_228], rax
0x1800292b2  test    rax, rax
0x1800292b5  jz      short loc_1800292C0
0x1800292b7  mov     rcx, rbx
0x1800292ba  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800292bf  nop
0x1800292c0  mov     rcx, r15
0x1800292c3  call    ??1?$AsyncOpWaiter@U?$IAsyncOperation@UCloudStoreSaveResult@Cloud@Storage@Internal@Windows@winrt@@@Foundation@Windows@winrt@@UCloudStoreSaveResult@Cloud@Storage@Internal@34@@details@wil@@QEAA@XZ; wil::details::AsyncOpWaiter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>,winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>::~AsyncOpWaiter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>,winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>(void)
0x1800292c8  nop
0x1800292c9  lea     r15, [rdi+238h]
0x1800292d0  mov     [r15], rsi
0x1800292d3  mov     [rdi+240h], rsi
0x1800292da  mov     [rdi+248h], rsi
0x1800292e1  lea     rbx, [rdi+250h]
0x1800292e8  mov     rdx, rbx
0x1800292eb  mov     rcx, r14
0x1800292ee  call    ?Items@?$consume_Windows_Internal_Storage_Cloud_IGetCollectionItemsResult@UIGetCollectionItemsResult@Cloud@Storage@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_Storage_Cloud_IGetCollectionItemsResult<winrt::Windows::Internal::Storage::Cloud::IGetCollectionItemsResult>::Items(void)
0x1800292f3  nop
0x1800292f4  mov     rcx, rax
0x1800292f7  call    ?Size@?$consume_Windows_Foundation_Collections_IVectorView@U?$IVectorView@UCloudStoreData@Cloud@Storage@Internal@Windows@winrt@@@Collections@Foundation@Windows@winrt@@UCloudStoreData@Cloud@Storage@Internal@45@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::Storage::Cloud::CloudStoreData>,winrt::Windows::Internal::Storage::Cloud::CloudStoreData>::Size(void)
  ... truncated ...
```
