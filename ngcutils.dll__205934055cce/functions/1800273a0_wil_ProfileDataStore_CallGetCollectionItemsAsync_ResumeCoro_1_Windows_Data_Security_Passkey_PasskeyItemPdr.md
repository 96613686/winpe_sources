# wil::ProfileDataStore::CallGetCollectionItemsAsync$_ResumeCoro$1_Windows::Data::Security::Passkey::PasskeyItemPdr_

- ea: `0x1800273a0`
- end: `0x1800280c4`
- name: `wil::ProfileDataStore::CallGetCollectionItemsAsync$_ResumeCoro$1_Windows::Data::Security::Passkey::PasskeyItemPdr_`
- size: `3364`
- prototype: ``
- caller_count: `1`
- callee_count: `30`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180029b2c`

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
- `0x1800273a0`
- `0x1800378f4`
- `0x18003f6bc`
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

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180028044`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180028044`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180027743`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180027ed5`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180027743`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180027ed5`

## pseudocode

```c
// Hidden C++ exception states: #wind=27
void __fastcall wil::ProfileDataStore::CallGetCollectionItemsAsync__ResumeCoro_1_Windows::Data::Security::Passkey::PasskeyItemPdr_(
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
  unsigned __int64 v38; // r9
  int v39; // r12d
  int i; // eax
  _QWORD *v41; // r15
  __int64 v42; // rax
  __int64 v43; // rdx
  __int64 v44; // rcx
  __int64 v45; // rax
  __int64 v46; // rdx
  __int64 v47; // r8
  __int64 v48; // rdx
  __int64 v49; // r8
  _QWORD *v50; // rax
  _QWORD *v51; // r8
  _QWORD *v52; // rdx
  volatile signed __int32 *v53; // r14
  volatile signed __int32 **v54; // r13
  __int64 v55; // rax
  const WCHAR *v56; // rdx
  __int64 v57; // r8
  __int64 v58; // rdx
  __int64 v59; // rcx
  __int64 v60; // rax
  __int64 v61; // rdx
  __int64 v62; // rcx
  __int64 v63; // rax
  __int64 v64; // rdx
  __int64 v65; // r8
  volatile signed __int32 *v66; // r15
  int v67; // eax
  HANDLE ProcessHeap; // rax
  __int64 v69; // rdx
  __int64 v70; // r8
  int v71; // [rsp+50h] [rbp-2A8h]
  __int64 v72; // [rsp+68h] [rbp-290h]
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
        goto LABEL_93;
      v8 = *(_DWORD *)(v7 + 8);
      do
      {
        if ( !v8 )
LABEL_93:
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
LABEL_92:
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 8LL))(v17);
          }
        }
      }
      else
      {
        v18 = (_QWORD *)(a1 + 168);
        wil::ProfileDataStore::GetTypeNameWideString<Windows::Data::Security::Passkey::PasskeyItemPdr>(a1 + 168);
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
        v38 = (unsigned int)winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::Storage::Cloud::CloudStoreData>,winrt::Windows::Internal::Storage::Cloud::CloudStoreData>::Size(v37);
        *(_QWORD *)(a1 + 936) = v38;
        if ( v38 > (__int64)(*(_QWORD *)(a1 + 584) - *(_QWORD *)(a1 + 568)) >> 4 )
          std::vector<std::shared_ptr<wil::ProfileDataItem<Windows::Data::Security::Passkey::RecoveryItemPdr>>>::_Reallocate<0>(a1 + 568);
        if ( *(_QWORD *)(a1 + 592) )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 592);
        winrt::impl::consume_Windows_Internal_Storage_Cloud_IGetCollectionItemsResult<winrt::Windows::Internal::Storage::Cloud::IGetCollectionItemsResult>::Items(
          a1 + 200,
          a1 + 600);
        *(_QWORD *)(a1 + 608) = a1 + 600;
        *(_DWORD *)(a1 + 616) = 0;
        v39 = winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::Storage::Cloud::CloudStoreData>,winrt::Windows::Internal::Storage::Cloud::CloudStoreData>::Size(a1 + 600);
        for ( i = 0; ; *(_DWORD *)(a1 + 616) = i )
        {
          if ( i == v39 )
          {
            if ( *(_QWORD *)(a1 + 600) )
              winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 600);
            v72 = winrt::impl::consume_Windows_Internal_Storage_Cloud_IGetCollectionItemsResult<winrt::Windows::Internal::Storage::Cloud::IGetCollectionItemsResult>::RetryAfter(a1 + 200);
            v71 = *(_DWORD *)winrt::impl::consume_Windows_Internal_Storage_Cloud_IGetCollectionItemsResult<winrt::Windows::Internal::Storage::Cloud::IGetCollectionItemsResult>::ResultCode(
                               a1 + 200,
                               a1 + 880);
            v54 = (volatile signed __int32 **)(a1 + 920);
            v55 = winrt::impl::consume_Windows_Internal_Storage_Cloud_IGetCollectionItemsResult<winrt::Windows::Internal::Storage::Cloud::IGetCollectionItemsResult>::SyncToken(
                    a1 + 200,
                    a1 + 920);
            if ( *(_QWORD *)v55 )
              v56 = *(const WCHAR **)(*(_QWORD *)v55 + 16LL);
            else
              v56 = &String1;
            *(_OWORD *)(a1 + 888) = 0;
            *(_QWORD *)(a1 + 904) = 0;
            *(_QWORD *)(a1 + 912) = 0;
            v57 = -1;
            do
              ++v57;
            while ( v56[v57] );
            std::wstring::_Construct<1,unsigned short const *>(a1 + 888, v56, v57);
            v58 = *(_QWORD *)(a1 + 584);
            *(_QWORD *)(a1 + 584) = 0;
            v59 = *(_QWORD *)(a1 + 576);
            *(_QWORD *)(a1 + 576) = 0;
            v60 = *(_QWORD *)(a1 + 568);
            *(_QWORD *)(a1 + 568) = 0;
            *(_QWORD *)(a1 + 800) = v60;
            *(_QWORD *)(a1 + 808) = v59;
            *(_QWORD *)(a1 + 816) = v58;
            std::wstring::wstring(a1 + 824, a1 + 888);
            *(_DWORD *)(a1 + 856) = v71;
            *(_QWORD *)(a1 + 864) = v72;
            v61 = *(_QWORD *)(a1 + 816);
            *(_QWORD *)(a1 + 816) = 0;
            v62 = *(_QWORD *)(a1 + 808);
            *(_QWORD *)(a1 + 808) = 0;
            v63 = *(_QWORD *)(a1 + 800);
            *(_QWORD *)(a1 + 800) = 0;
            *(_QWORD *)(a1 - 88) = v63;
            *(_QWORD *)(a1 - 80) = v62;
            *(_QWORD *)(a1 - 72) = v61;
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
            std::wstring::~wstring(a1 + 824, v61, a1 + 800);
            std::vector<std::shared_ptr<wil::ProfileDataItem<Windows::Data::Security::Passkey::PasskeyItemPdr>>>::_Tidy(a1 + 800);
            std::wstring::~wstring(a1 + 888, v64, v65);
            v66 = *v54;
            if ( *v54 )
            {
              v67 = _InterlockedDecrement(v66 + 6);
              if ( v67 )
              {
                if ( v67 < 0 )
                  abort();
              }
              else
              {
                ProcessHeap = WINRT_IMPL_GetProcessHeap();
                WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v66);
              }
              *v54 = 0;
            }
            std::vector<std::shared_ptr<wil::ProfileDataItem<Windows::Data::Security::Passkey::PasskeyItemPdr>>>::_Tidy(a1 + 568);
            if ( *(_QWORD *)(a1 + 200) )
              winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 200);
            std::wstring::~wstring(a1 + 168, v69, v70);
            if ( *(_QWORD *)(a1 + 24) )
            {
              v17 = *(volatile signed __int32 **)(a1 + 24);
              if ( _InterlockedExchangeAdd(v17 + 2, 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v17)(v17);
                if ( _InterlockedExchangeAdd(v17 + 3, 0xFFFFFFFF) == 1 )
                  goto LABEL_92;
              }
            }
            goto LABEL_94;
          }
          v41 = (_QWORD *)(a1 + 624);
          winrt::impl::fast_iterator<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::Storage::Cloud::CloudStoreData>>::operator*(
            a1 + 608,
            a1 + 624);
          v42 = *(_QWORD *)(a1 + 992);
          if ( v42 )
          {
            if ( *(_DWORD *)(v42 + 16) )
              break;
          }
          v50 = (_QWORD *)wil::ProfileDataStore::Unmarshal<Windows::Data::Security::Passkey::PasskeyItemPdr>(
                            a1 + 776,
                            a1 + 624,
                            *(unsigned int *)(a1 + 968));
          v51 = v50;
          v52 = *(_QWORD **)(a1 + 576);
          if ( v52 == *(_QWORD **)(a1 + 584) )
          {
            std::vector<std::shared_ptr<wil::ProfileDataItem<Windows::Data::Security::Passkey::PasskeyItemPdr>>>::_Emplace_reallocate<std::shared_ptr<wil::ProfileDataItem<Windows::Data::Security::Passkey::PasskeyItemPdr>>>(
              a1 + 568,
              v52,
              v50);
          }
          else
          {
            *v52 = 0;
            v52[1] = 0;
            *v52 = *v50;
            v52[1] = v50[1];
            *v50 = 0;
            v50[1] = 0;
            *(_QWORD *)(a1 + 576) += 16LL;
          }
          if ( *(_QWORD *)(a1 + 784) )
          {
            v53 = *(volatile signed __int32 **)(a1 + 784);
            if ( _InterlockedExchangeAdd(v53 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *, _QWORD *, _QWORD *))v53)(v53, v52, v51);
              if ( _InterlockedExchangeAdd(v53 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v53 + 8LL))(v53);
            }
          }
          if ( *v41 )
            winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 624);
          i = *(_DWORD *)(a1 + 616) + 1;
        }
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
          v17 = *(volatile signed __int32 **)(a1 + 24);
          if ( _InterlockedExchangeAdd(v17 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v17)(v17);
            if ( _InterlockedExchangeAdd(v17 + 3, 0xFFFFFFFF) == 1 )
              goto LABEL_92;
          }
        }
      }
LABEL_94:
      *(_QWORD *)(a1 + 928) = a1 - 112;
      *(_WORD *)(a1 + 8) = 0;
      `wil::details::coro::promise_base<wil::GetCollectionItemsResult<Windows::Data::Security::Passkey::PasskeyItemPdr>>::final_suspend'::`2'::awaiter::await_suspend();
      return;
    default:
      __debugbreak();
      return;
  }
}

```

## disassembly

```asm
0x1800273a0  mov     r11, rsp
0x1800273a3  mov     [r11+10h], rbx
0x1800273a7  mov     [r11+18h], rsi
0x1800273ab  mov     [r11+8], rcx
0x1800273af  push    rdi
0x1800273b0  push    r12
0x1800273b2  push    r13
0x1800273b4  push    r14
0x1800273b6  push    r15
0x1800273b8  sub     rsp, 2D0h
0x1800273bf  mov     rax, cs:__security_cookie
0x1800273c6  xor     rax, rsp
0x1800273c9  mov     [rsp+2F8h+var_30], rax
0x1800273d1  mov     rdi, rcx
0x1800273d4  mov     [rsp+2F8h+var_2A0], rcx
0x1800273d9  movzx   eax, word ptr [rdi+8]
0x1800273dd  mov     [rsp+2F8h+var_298], ax
0x1800273e2  inc     ax; switch 5 cases
0x1800273e5  mov     ecx, 4
0x1800273ea  cmp     ax, cx
0x1800273ed  ja      def_180027408; jumptable 0000000180027408 default case, case 0
0x1800273f3  movsx   rax, ax
0x1800273f7  lea     rdx, __ImageBase
0x1800273fe  mov     ecx, ds:(jpt_180027408 - 180000000h)[rdx+rax*4]
0x180027405  add     rcx, rdx
0x180027408  jmp     rcx; switch jump
0x18002740a  jmp     loc_180028013; jumptable 0000000180027408 case 3
0x18002740f  xor     esi, esi; jumptable 0000000180027408 case 2
0x180027411  mov     r12, [rdi+3B8h]
0x180027418  mov     [rdi+10h], rsi
0x18002741c  lea     r15, [rdi+18h]
0x180027420  mov     [r15], rsi
0x180027423  mov     rdx, [r12+8]
0x180027428  test    rdx, rdx
0x18002742b  jz      loc_180027FED
0x180027431  mov     eax, [rdx+8]
0x180027434  jmp     short loc_180027440
0x180027436  lea     ecx, [rax+1]
0x180027439  lock cmpxchg [rdx+8], ecx
0x18002743e  jz      short loc_180027449
0x180027440  test    eax, eax
0x180027442  jnz     short loc_180027436
0x180027444  jmp     loc_180027FED
0x180027449  mov     [rsp+2F8h+var_268], r15
0x180027451  mov     rax, [r12]
0x180027455  mov     [rdi+10h], rax
0x180027459  mov     r13, [r12+8]
0x18002745e  mov     [r15], r13
0x180027461  mov     rax, [rdi+3E0h]
0x180027468  test    rax, rax
0x18002746b  jz      loc_1800275F7
0x180027471  mov     eax, [rax+10h]
0x180027474  nop
0x180027475  test    eax, eax
0x180027477  jz      loc_1800275F7
0x18002747d  lea     rbx, [rdi+70h]
0x180027481  xorps   xmm0, xmm0
0x180027484  movups  xmmword ptr [rbx], xmm0
0x180027487  mov     [rdi+80h], rsi
0x18002748e  mov     qword ptr [rdi+88h], 7
0x180027499  xor     eax, eax
0x18002749b  mov     [rbx], ax
0x18002749e  mov     [rdi+0A0h], rsi
0x1800274a5  mov     [rdi+98h], rsi
0x1800274ac  mov     [rdi+90h], rsi
0x1800274b3  lea     r14, [rdi+20h]
0x1800274b7  mov     [r14], rsi
0x1800274ba  mov     [rdi+28h], rsi
0x1800274be  mov     [rdi+30h], rsi
0x1800274c2  lea     r12, [rdi+38h]
0x1800274c6  mov     rdx, rbx
0x1800274c9  mov     rcx, r12
0x1800274cc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800274d1  mov     r8d, 800704C7h
0x1800274d7  mov     [rdi+58h], r8d
0x1800274db  mov     [rdi+60h], rsi
0x1800274df  mov     rdx, [rdi+30h]
0x1800274e3  mov     [rsp+2F8h+var_198], rdx
0x1800274eb  mov     [rdi+30h], rsi
0x1800274ef  mov     rcx, [rdi+28h]
0x1800274f3  mov     [rsp+2F8h+var_1A0], rcx
0x1800274fb  mov     [rdi+28h], rsi
0x1800274ff  mov     rax, [r14]
0x180027502  mov     [rsp+2F8h+var_1A8], rax
0x18002750a  mov     [r14], rsi
0x18002750d  mov     [rdi-58h], rax
0x180027511  mov     [rdi-50h], rcx
0x180027515  mov     [rdi-48h], rdx
0x180027519  mov     rax, [r12]
0x18002751d  mov     [rsp+2F8h+var_190], rax
0x180027525  mov     [rdi-40h], rax
0x180027529  mov     rax, [rdi+40h]
0x18002752d  mov     [rsp+2F8h+var_188], rax
0x180027535  mov     [rdi-38h], rax
0x180027539  mov     rax, [rdi+48h]
0x18002753d  mov     [rsp+2F8h+var_180], rax
0x180027545  mov     [rdi-30h], rax
0x180027549  mov     rax, [rdi+50h]
0x18002754d  mov     [rsp+2F8h+var_178], rax
0x180027555  mov     [rdi-28h], rax
0x180027559  mov     [rdi+48h], rsi
0x18002755d  mov     qword ptr [rdi+50h], 7
0x180027565  xor     eax, eax
0x180027567  mov     [r12], ax
0x18002756c  mov     [rdi-20h], r8d
0x180027570  mov     [rdi-18h], rsi
0x180027574  mov     dword ptr [rdi-60h], 1
0x18002757b  mov     rcx, r12
0x18002757e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180027583  mov     rcx, r14
0x180027586  call    ?_Tidy@?$vector@V?$shared_ptr@V?$ProfileDataItem@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@wil@@@std@@V?$allocator@V?$shared_ptr@V?$ProfileDataItem@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@wil@@@std@@@2@@std@@AEAAXXZ; std::vector<std::shared_ptr<wil::ProfileDataItem<Windows::Data::Security::Passkey::PasskeyItemPdr>>>::_Tidy(void)
0x18002758b  nop
0x18002758c  lea     rcx, [rdi+90h]
0x180027593  call    ?_Tidy@?$vector@V?$shared_ptr@V?$ProfileDataItem@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@wil@@@std@@V?$allocator@V?$shared_ptr@V?$ProfileDataItem@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@wil@@@std@@@2@@std@@AEAAXXZ; std::vector<std::shared_ptr<wil::ProfileDataItem<Windows::Data::Security::Passkey::PasskeyItemPdr>>>::_Tidy(void)
0x180027598  nop
0x180027599  mov     rcx, rbx
0x18002759c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800275a1  nop
0x1800275a2  mov     [rsp+2F8h+var_278], r13
0x1800275aa  test    r13, r13
0x1800275ad  jz      short loc_1800275F2
0x1800275af  mov     rsi, [r15]
0x1800275b2  mov     [rsp+2F8h+var_278], rsi
0x1800275ba  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800275be  mov     eax, ebx
0x1800275c0  lock xadd [rsi+8], eax
0x1800275c5  add     eax, ebx
0x1800275c7  jnz     short loc_1800275F2
0x1800275c9  mov     rax, [rsi]
0x1800275cc  mov     rcx, rsi
0x1800275cf  mov     rax, [rax]
0x1800275d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800275d7  mov     eax, ebx
0x1800275d9  lock xadd [rsi+0Ch], eax
0x1800275de  add     eax, ebx
0x1800275e0  jnz     short loc_1800275F2
0x1800275e2  mov     rax, [rsi]
0x1800275e5  mov     rcx, rsi
0x1800275e8  mov     rax, [rax+8]
0x1800275ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800275f1  nop
0x1800275f2  jmp     loc_180027FF8
0x1800275f7  lea     rbx, [rdi+0A8h]
0x1800275fe  mov     [rsp+2F8h+var_2A8], rbx
0x180027603  mov     rcx, rbx
0x180027606  call    ??$GetTypeNameWideString@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@ProfileDataStore@wil@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; wil::ProfileDataStore::GetTypeNameWideString<Windows::Data::Security::Passkey::PasskeyItemPdr>(void)
0x18002760b  nop
0x18002760c  lea     r14, [rdi+0C8h]
0x180027613  mov     [rsp+2F8h+var_290], r14
0x180027618  mov     [r14], rsi
0x18002761b  lea     r13, [rdi+0E8h]
0x180027622  mov     rdx, r13
0x180027625  mov     rcx, [r12+10h]
0x18002762a  call    ?GetCloudStore@SharedCloudStoreState@details@wil@@QEAA?BUCloudStore@Cloud@Storage@Internal@Windows@winrt@@XZ; wil::details::SharedCloudStoreState::GetCloudStore(void)
0x18002762f  mov     r11, rax
0x180027632  lea     r12, [rdi+0F0h]
0x180027639  mov     rcx, [rdi+3D8h]
0x180027640  mov     [r12], rcx
0x180027644  mov     rcx, [rdi+3D0h]
0x18002764b  mov     [rdi+110h], rcx
0x180027652  mov     r8d, [rdi+3CCh]
0x180027659  mov     ecx, r8d
0x18002765c  and     ecx, 1
0x18002765f  mov     edx, ecx
0x180027661  or      edx, 2
0x180027664  bt      r8d, 1
0x180027669  cmovnb  edx, ecx
0x18002766c  mov     r9d, 4; char *
0x180027672  mov     ecx, edx
0x180027674  or      ecx, r9d
0x180027677  test    r9d, r8d
0x18002767a  cmovz   ecx, edx
0x18002767d  mov     edx, ecx
0x18002767f  or      edx, 10h
0x180027682  bt      r8d, 4
0x180027687  cmovnb  edx, ecx
0x18002768a  mov     eax, edx
0x18002768c  or      eax, 8
0x18002768f  bt      r8d, 3
0x180027694  cmovnb  eax, edx
0x180027697  mov     [rdi+130h], eax
0x18002769d  mov     r8d, [r15+3B0h]
0x1800276a4  mov     edx, r8d
0x1800276a7  and     edx, 1
0x1800276aa  test    r9d, r8d
0x1800276ad  jz      short loc_1800276D2
0x1800276af  mov     rcx, [rsp+2F8h]; this
0x1800276b7  mov     al, dl
0x1800276b9  xor     al, 1
0x1800276bb  jz      short loc_1800276CF
0x1800276bd  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\sdk\\inc\\wil\\pr"...
0x1800276c4  mov     edx, 8FEh; void *
0x1800276c9  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800276cf  or      edx, 2
0x1800276d2  mov     ecx, edx
0x1800276d4  or      ecx, r9d
0x1800276d7  bt      r8d, 3
0x1800276dc  cmovnb  ecx, edx
0x1800276df  mov     edx, ecx
0x1800276e1  or      edx, 8
0x1800276e4  bt      r8d, 4
0x1800276e9  cmovnb  edx, ecx
0x1800276ec  lea     r10, [rdi+134h]
0x1800276f3  mov     eax, edx
0x1800276f5  or      eax, 10h
0x1800276f8  bt      r8d, 5
0x1800276fd  cmovnb  eax, edx
0x180027700  mov     [r10], eax
0x180027703  mov     rcx, [rdi+0B8h]
0x18002770a  mov     [rsp+2F8h+var_F8], rcx
0x180027712  mov     rax, [rdi+0C0h]
0x180027719  mov     [rsp+2F8h+var_F0], rax
0x180027721  cmp     rax, 7
0x180027725  jbe     short loc_180027732
0x180027727  mov     rbx, [rbx]
0x18002772a  mov     [rsp+2F8h+var_108], rbx
0x180027732  test    ecx, ecx
0x180027734  jnz     short loc_18002773B
0x180027736  mov     rax, rsi
0x180027739  jmp     short loc_180027764
0x18002773b  mov     eax, ecx
0x18002773d  cmp     [rbx+rax*2], si
0x180027741  jz      short loc_18002774A
0x180027743  call    cs:__imp_abort
0x18002774a  lea     rax, [rdi+140h]
0x180027751  mov     dword ptr [rax], 1
0x180027757  mov     [rdi+144h], ecx
0x18002775d  mov     [rdi+150h], rbx
0x180027764  mov     [rdi+138h], rax
0x18002776b  lea     rcx, [rdi+158h]
0x180027772  mov     rax, [rdi+3C0h]
0x180027779  mov     [rcx], rax
0x18002777c  mov     r8, [rdi+3B8h]
0x180027783  lea     r9, [rdi+178h]
0x18002778a  mov     rax, [r8+28h]
0x18002778e  mov     [r9], rax
0x180027791  lea     rbx, [rdi+198h]
0x180027798  lea     rax, [rdi+138h]
0x18002779f  add     r8, 20h ; ' '
0x1800277a3  mov     [rsp+2F8h+var_2B0], r12
0x1800277a8  lea     rdx, [rdi+110h]
0x1800277af  mov     [rsp+2F8h+var_2B8], rdx
0x1800277b4  lea     rdx, [rdi+130h]
0x1800277bb  mov     [rsp+2F8h+var_2C0], rdx
0x1800277c0  mov     [rsp+2F8h+var_2C8], r10
0x1800277c5  mov     [rsp+2F8h+var_2D0], rax
0x1800277ca  mov     [rsp+2F8h+var_2D8], rcx
0x1800277cf  mov     rdx, rbx
0x1800277d2  mov     rcx, r11
0x1800277d5  call    ?GetCollectionItemsAsync@?$consume_Windows_Internal_Storage_Cloud_ICloudStore2@UCloudStore@Cloud@Storage@Internal@Windows@winrt@@@impl@winrt@@QEBA@AEBW4PartitionKind@Cloud@Storage@Internal@Windows@3@AEBUhstring@param@3@11AEBW4LoadOptions@56783@AEBW4CollectionOptions@56783@11@Z; winrt::impl::consume_Windows_Internal_Storage_Cloud_ICloudStore2<winrt::Windows::Internal::Storage::Cloud::CloudStore>::GetCollectionItemsAsync(winrt::Windows::Internal::Storage::Cloud::PartitionKind const &,winrt::param::hstring const &,winrt::param::hstring const &,winrt::param::hstring const &,winrt::Windows::Internal::Storage::Cloud::LoadOptions const &,winrt::Windows::Internal::Storage::Cloud::CollectionOptions const &,winrt::param::hstring const &,winrt::param::hstring const &)
0x1800277da  nop
0x1800277db  lea     r15, [rdi+0D0h]
0x1800277e2  mov     r8, rax
0x1800277e5  lea     rdx, [rdi+3E0h]
0x1800277ec  mov     rcx, r15
0x1800277ef  call    ??0?$AsyncOpWaiter@U?$IAsyncOperation@UGetCollectionItemsResult@Cloud@Storage@Internal@Windows@winrt@@@Foundation@Windows@winrt@@UGetCollectionItemsResult@Cloud@Storage@Internal@34@@details@wil@@QEAA@AEBVcancellation_token@Concurrency@@AEBU?$IAsyncOperation@UGetCollectionItemsResult@Cloud@Storage@Internal@Windows@winrt@@@Foundation@Windows@winrt@@@Z; wil::details::AsyncOpWaiter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::GetCollectionItemsResult>,winrt::Windows::Internal::Storage::Cloud::GetCollectionItemsResult>::AsyncOpWaiter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::GetCollectionItemsResult>,winrt::Windows::Internal::Storage::Cloud::GetCollectionItemsResult>(Concurrency::cancellation_token const &,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::GetCollectionItemsResult> const &)
0x1800277f4  nop
0x1800277f5  mov     rax, [rbx]
0x1800277f8  mov     [rsp+2F8h+var_238], rax
0x180027800  test    rax, rax
0x180027803  jz      short loc_18002780E
0x180027805  mov     rcx, rbx
0x180027808  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18002780d  nop
0x18002780e  mov     rax, [r13+0]
0x180027812  mov     [rsp+2F8h+var_230], rax
0x18002781a  test    rax, rax
0x18002781d  jz      short loc_180027827
0x18002781f  mov     rcx, r13
0x180027822  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180027827  lea     rbx, [rdi+1A0h]
0x18002782e  mov     rdx, rbx
0x180027831  mov     rcx, r15
0x180027834  call    ?WaitForResult@?$AsyncOpWaiter@U?$IAsyncOperation@UGetCollectionItemsResult@Cloud@Storage@Internal@Windows@winrt@@@Foundation@Windows@winrt@@UGetCollectionItemsResult@Cloud@Storage@Internal@34@@details@wil@@QEAA?AUGetCollectionItemsResult@Cloud@Storage@Internal@Windows@winrt@@XZ; wil::details::AsyncOpWaiter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::GetCollectionItemsResult>,winrt::Windows::Internal::Storage::Cloud::GetCollectionItemsResult>::WaitForResult(void)
0x180027839  cmp     r14, rax
0x18002783c  jz      short loc_180027847
0x18002783e  mov     rdx, [rax]
0x180027841  mov     [rax], rsi
0x180027844  mov     [r14], rdx
0x180027847  mov     rax, [rbx]
0x18002784a  mov     [rsp+2F8h+var_228], rax
0x180027852  test    rax, rax
0x180027855  jz      short loc_180027860
0x180027857  mov     rcx, rbx
0x18002785a  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18002785f  nop
0x180027860  mov     rcx, r15
0x180027863  call    ??1?$AsyncOpWaiter@U?$IAsyncOperation@UCloudStoreSaveResult@Cloud@Storage@Internal@Windows@winrt@@@Foundation@Windows@winrt@@UCloudStoreSaveResult@Cloud@Storage@Internal@34@@details@wil@@QEAA@XZ; wil::details::AsyncOpWaiter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>,winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>::~AsyncOpWaiter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>,winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>(void)
0x180027868  nop
0x180027869  lea     r15, [rdi+238h]
0x180027870  mov     [r15], rsi
0x180027873  mov     [rdi+240h], rsi
0x18002787a  mov     [rdi+248h], rsi
0x180027881  lea     rbx, [rdi+250h]
0x180027888  mov     rdx, rbx
0x18002788b  mov     rcx, r14
0x18002788e  call    ?Items@?$consume_Windows_Internal_Storage_Cloud_IGetCollectionItemsResult@UIGetCollectionItemsResult@Cloud@Storage@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_Storage_Cloud_IGetCollectionItemsResult<winrt::Windows::Internal::Storage::Cloud::IGetCollectionItemsResult>::Items(void)
0x180027893  nop
0x180027894  mov     rcx, rax
0x180027897  call    ?Size@?$consume_Windows_Foundation_Collections_IVectorView@U?$IVectorView@UCloudStoreData@Cloud@Storage@Internal@Windows@winrt@@@Collections@Foundation@Windows@winrt@@UCloudStoreData@Cloud@Storage@Internal@45@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::Storage::Cloud::CloudStoreData>,winrt::Windows::Internal::Storage::Cloud::CloudStoreData>::Size(void)
  ... truncated ...
```
