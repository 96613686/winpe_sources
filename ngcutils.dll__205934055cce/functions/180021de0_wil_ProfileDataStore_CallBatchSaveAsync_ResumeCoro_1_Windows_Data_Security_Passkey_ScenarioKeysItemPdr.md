# wil::ProfileDataStore::CallBatchSaveAsync$_ResumeCoro$1_Windows::Data::Security::Passkey::ScenarioKeysItemPdr_

- ea: `0x180021de0`
- end: `0x180022f10`
- name: `wil::ProfileDataStore::CallBatchSaveAsync$_ResumeCoro$1_Windows::Data::Security::Passkey::ScenarioKeysItemPdr_`
- size: `4400`
- prototype: ``
- caller_count: `1`
- callee_count: `41`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180023230`

## callees

- `0x180003080`
- `0x1800030a4`
- `0x180003520`
- `0x180003c97`
- `0x180003cdf`
- `0x1800060a4`
- `0x180007a5c`
- `0x18000ce74`
- `0x18000f7fc`
- `0x18001354c`
- `0x18001ae30`
- `0x18001cfb8`
- `0x180021de0`
- `0x1800318c8`
- `0x180037b84`
- `0x18003b4dc`
- `0x180041cf4`
- `0x180042b40`
- `0x18004302c`
- `0x1800434d0`
- `0x180044174`
- `0x18004478c`
- `0x18004519c`
- `0x180045880`
- `0x180045914`
- `0x1800460d4`
- `0x1800461d4`
- `0x1800471b4`
- `0x180047e08`
- `0x180049038`
- `0x180049238`
- `0x18004a2d4`
- `0x18004ccf0`
- `0x18004cf2c`
- `0x18004d87c`
- `0x18004eaac`
- `0x18004ec6c`
- `0x18004ee3c`
- `0x180050270`
- `0x180050384`
- `0x180061010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800227a3`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002290e`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002296c`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180022d82`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800227a3`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002290e`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002296c`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180022d82`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180022210`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180022210`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800224b4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800225e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002260c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800224b4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800225e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002260c`

## pseudocode

```c
void __fastcall wil::ProfileDataStore::CallBatchSaveAsync__ResumeCoro_1_Windows::Data::Security::Passkey::ScenarioKeysItemPdr_(
        __int64 a1)
{
  _QWORD *v2; // rbx
  __int64 v3; // rdx
  signed __int32 v4; // eax
  signed __int32 v5; // ett
  __int64 v6; // rbx
  __int64 v7; // rax
  __int128 v8; // xmm0
  __int64 v9; // rdx
  __int64 v10; // r8
  volatile signed __int32 *v11; // rbx
  const char *v12; // r9
  _QWORD *v13; // r13
  _QWORD *v14; // rax
  __int64 v15; // rbx
  __int64 v16; // rdx
  int v17; // ebx
  __int64 v18; // rax
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // rdx
  __int64 v26; // r8
  int v27; // ebx
  const WCHAR *v28; // r8
  const WCHAR *v29; // rcx
  int v30; // ebx
  __int64 v31; // rdx
  __int64 v32; // r8
  __int64 v33; // rdx
  __int64 v34; // r8
  __int64 v35; // rdx
  __int64 v36; // r8
  __int64 v37; // rdx
  __int64 v38; // r8
  const char *v39; // r9
  __int64 v40; // rcx
  int v41; // ebx
  const WCHAR *v42; // rdi
  __int64 v43; // rdx
  __int64 v44; // r8
  int v45; // r12d
  __int64 v46; // rdi
  __int64 v47; // rdx
  __int64 v48; // r8
  const char *v49; // rbx
  const WCHAR *v50; // rdx
  HSTRING *v51; // r12
  const char **v52; // rax
  __int64 v53; // rdx
  __int64 v54; // r8
  _QWORD *v55; // r12
  int v56; // eax
  __int64 v57; // rax
  __int64 v58; // rdx
  __int64 v59; // r8
  int v60; // edx
  int v62; // ecx
  int v63; // eax
  __int64 *v64; // r12
  _QWORD *View; // rax
  _QWORD *v66; // rax
  _QWORD *v67; // rcx
  __int64 v68; // rdx
  __int64 v69; // rax
  __int64 v70; // rax
  int v71; // ecx
  __int64 v72; // r8
  __int64 v73; // rax
  __int64 v74; // rdx
  __int64 v75; // r8
  int v76; // eax
  volatile signed __int32 *v77; // rbx
  int v78; // eax
  HANDLE ProcessHeap; // rax
  int v80; // eax
  volatile signed __int32 *v81; // rbx
  int v82; // eax
  HANDLE v83; // rax
  __int64 *v84; // rax
  __int64 v85; // rdx
  unsigned int v86; // eax
  unsigned int v87; // ebx
  int v88; // r13d
  __int64 v89; // rax
  __int64 v90; // r8
  __int64 v91; // rdx
  __int64 v92; // r8
  __int64 v93; // rdx
  __int64 v94; // rax
  volatile signed __int32 *v95; // rbx
  int v96; // eax
  HANDLE v97; // rax
  volatile signed __int32 *v98; // rbx
  volatile signed __int32 *v99; // rbx
  BOOL bIgnoreCase[2]; // [rsp+20h] [rbp-3F8h]
  const char *v101; // [rsp+28h] [rbp-3F0h]
  _QWORD *v102; // [rsp+68h] [rbp-3B0h]
  int CloudStore; // [rsp+68h] [rbp-3B0h]
  __int64 v104; // [rsp+90h] [rbp-388h]
  wil::details::in1diag3 *retaddr; // [rsp+418h] [rbp+0h]

  switch ( *(_WORD *)(a1 + 8) )
  {
    case 0xFFFF:
    case 1:
    case 3:
      wil::details::coro::task_promise<std::vector<wil::ProfileDataStoreSaveResult>>::~task_promise<std::vector<wil::ProfileDataStoreSaveResult>>(a1 - 64);
      `wil::ProfileDataStore::CallBatchSaveAsync<Windows::Data::Security::Passkey::RecoveryItemPdr>'::`29'::_parameters_::~_parameters_(a1 + 1224);
      if ( *(_WORD *)(a1 + 10) )
        operator delete((void *)(a1 - 64), 0x540u);
      return;
    case 2:
      *(_DWORD *)(a1 + 1200) = 0;
      v2 = *(_QWORD **)(a1 + 1224);
      *(_QWORD *)(a1 + 16) = 0;
      *(_QWORD *)(a1 + 24) = 0;
      v3 = v2[1];
      if ( !v3 )
        goto LABEL_144;
      v4 = *(_DWORD *)(v3 + 8);
      do
      {
        if ( !v4 )
LABEL_144:
          std::_Throw_bad_weak_ptr();
        v5 = v4;
        v4 = _InterlockedCompareExchange((volatile signed __int32 *)(v3 + 8), v4 + 1, v4);
      }
      while ( v5 != v4 );
      *(_QWORD *)(a1 + 16) = *v2;
      v6 = v2[1];
      *(_QWORD *)(a1 + 24) = v6;
      *(_DWORD *)(a1 + 1200) = 8;
      v7 = *(_QWORD *)(a1 + 1264);
      if ( v7 && *(_DWORD *)(v7 + 16) )
      {
        *(_OWORD *)(a1 + 112) = 0;
        *(_QWORD *)(a1 + 128) = 0;
        *(_QWORD *)(a1 + 136) = 7;
        *(_WORD *)(a1 + 112) = 0;
        *(_QWORD *)(a1 + 56) = 0;
        *(_DWORD *)(a1 + 64) = 0;
        *(_DWORD *)(a1 + 68) = -2147023673;
        v8 = *(_OWORD *)(a1 + 128);
        *(_OWORD *)(a1 + 72) = *(_OWORD *)(a1 + 112);
        *(_OWORD *)(a1 + 88) = v8;
        *(_QWORD *)(a1 + 128) = 0;
        *(_QWORD *)(a1 + 136) = 7;
        *(_WORD *)(a1 + 112) = 0;
        *(_QWORD *)(a1 + 104) = 0;
        *(_QWORD *)(a1 + 1168) = a1 + 56;
        *(_QWORD *)(a1 + 1176) = a1 + 112;
        std::vector<wil::ProfileDataStoreSaveResult>::vector<wil::ProfileDataStoreSaveResult>(a1 + 32, a1 + 1168);
        wil::details::coro::task_promise<std::vector<wil::ProfileDataStoreSaveResult>>::return_value(a1 - 64, a1 + 32);
        std::vector<wil::ProfileDataStoreSaveResult>::_Tidy(a1 + 32);
        `eh vector destructor iterator'(
          (void *)(a1 + 56),
          0x38u,
          1u,
          (void (*)(void *))wil::ProfileDataStoreSaveResult::~ProfileDataStoreSaveResult);
        std::wstring::~wstring(a1 + 112, v9, v10);
        if ( v6 )
        {
          v11 = *(volatile signed __int32 **)(a1 + 24);
          if ( _InterlockedExchangeAdd(v11 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
            if ( _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
          }
        }
      }
      else if ( *(_QWORD *)(a1 + 1232) == *(_QWORD *)(a1 + 1240) )
      {
        *(_QWORD *)(a1 + 144) = 0;
        *(_QWORD *)(a1 + 152) = 0;
        *(_QWORD *)(a1 + 160) = 0;
        wil::details::coro::task_promise<std::vector<wil::ProfileDataStoreSaveResult>>::return_value(a1 - 64, a1 + 144);
        std::vector<wil::ProfileDataStoreSaveResult>::_Tidy(a1 + 144);
        if ( v6 )
        {
          v99 = *(volatile signed __int32 **)(a1 + 24);
          if ( _InterlockedExchangeAdd(v99 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v99)(v99);
            if ( _InterlockedExchangeAdd(v99 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v99 + 8LL))(v99);
          }
        }
      }
      else
      {
        *(_BYTE *)(a1 + 176) = 0;
        *(_QWORD *)(a1 + 184) = 0;
        *(_QWORD *)(a1 + 192) = 0;
        *(_QWORD *)(a1 + 200) = 0;
        winrt::single_threaded_vector<winrt::Windows::Internal::Storage::Cloud::CloudStoreBatchSaveItemData,std::allocator<winrt::Windows::Internal::Storage::Cloud::CloudStoreBatchSaveItemData>>(
          a1 + 208,
          a1 + 184);
        std::vector<winrt::Windows::Internal::Storage::Cloud::CloudStoreBatchSaveItemData>::~vector<winrt::Windows::Internal::Storage::Cloud::CloudStoreBatchSaveItemData>(a1 + 184);
        wil::details::GetActivationFactoryPdr<Windows::Internal::Storage::Cloud::ICloudStoreBatchSaveItemDataFactory>(a1 + 216);
        v13 = *(_QWORD **)(a1 + 1232);
        v14 = *(_QWORD **)(a1 + 1240);
        v102 = v14;
        while ( v13 != v14 )
        {
          v15 = *v13;
          v16 = *v13 + 88LL;
          if ( *(_BYTE *)(a1 + 176) )
          {
            std::wstring::wstring(a1 + 368, v16);
            std::wstring::wstring(a1 + 400, v15 + 120);
            std::wstring::wstring(a1 + 432, v15 + 152);
            v27 = *(_DWORD *)(a1 + 1200) | 0x40;
            *(_DWORD *)(a1 + 1200) = v27;
            std::wstring::wstring(a1 + 464, a1 + 400);
            *(_DWORD *)(a1 + 1200) = v27 | 0x80;
            if ( *(_QWORD *)(a1 + 488) <= 7u )
              v28 = (const WCHAR *)(a1 + 464);
            else
              v28 = *(const WCHAR **)(a1 + 464);
            if ( *(_QWORD *)(a1 + 168) )
              v29 = *(const WCHAR **)(*(_QWORD *)(a1 + 168) + 16LL);
            else
              v29 = &String1;
            v30 = CompareStringOrdinal(v29, -1, v28, -1, 1);
            std::wstring::~wstring(a1 + 464, v31, v32);
            std::wstring::~wstring(a1 + 432, v33, v34);
            std::wstring::~wstring(a1 + 400, v35, v36);
            std::wstring::~wstring(a1 + 368, v37, v38);
            if ( v30 != 2 )
            {
              v39 = (const char *)(unsigned int)wil::verify_hresult<long>(2147942487LL);
              wil::details::in1diag3::Throw_HrMsg(
                retaddr,
                (void *)0x771,
                (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil\\profiledatastore.h",
                v39,
                (int)"All payloads must be for the same collection.",
                v101);
            }
          }
          else
          {
            std::wstring::wstring(a1 + 240, v16);
            std::wstring::wstring(a1 + 272, v15 + 120);
            std::wstring::wstring(a1 + 304, v15 + 152);
            v17 = *(_DWORD *)(a1 + 1200) | 0x10;
            *(_DWORD *)(a1 + 1200) = v17;
            std::wstring::wstring(a1 + 336, a1 + 272);
            *(_DWORD *)(a1 + 1200) = v17 | 0x20;
            if ( *(_QWORD *)(a1 + 360) <= 7u )
              v18 = a1 + 336;
            else
              v18 = *(_QWORD *)(a1 + 336);
            *(_QWORD *)(a1 + 224) = v18;
            std::optional<winrt::hstring>::operator=<unsigned short const *,0>(a1 + 168);
            std::wstring::~wstring(a1 + 336, v19, v20);
            std::wstring::~wstring(a1 + 304, v21, v22);
            std::wstring::~wstring(a1 + 272, v23, v24);
            std::wstring::~wstring(a1 + 240, v25, v26);
          }
          wil::ProfileDataStore::Marshal<wil::ProfileDataItem<Windows::Data::Security::Passkey::ScenarioKeysItemPdr>>(
            a1 + 496,
            *v13);
          *(_QWORD *)(a1 + 504) = *(_QWORD *)(a1 + 496);
          if ( *(_QWORD *)(a1 + 496) )
            (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 496) + 8LL))(*(_QWORD *)(a1 + 496));
          v40 = *(_QWORD *)(*v13 + 64LL);
          v104 = v40;
          *(_QWORD *)(a1 + 512) = v40;
          if ( v40 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 8LL))(v40);
          std::wstring::wstring(a1 + 520, *v13 + 88LL);
          v41 = *(_DWORD *)(a1 + 1200) | 0x300;
          *(_DWORD *)(a1 + 1200) = v41;
          if ( *(_QWORD *)(a1 + 536) )
          {
            v42 = (const WCHAR *)(a1 + 552);
            std::wstring::wstring(a1 + 552, *v13 + 88LL);
            v41 |= 0xC01u;
            *(_DWORD *)(a1 + 1200) = v41;
            if ( *(_QWORD *)(a1 + 576) > 7u )
              v42 = *(const WCHAR **)v42;
          }
          else
          {
            v42 = L"default";
          }
          wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(
            (HSTRING *)(a1 + 584),
            v42);
          if ( (v41 & 1) != 0 )
          {
            *(_DWORD *)(a1 + 1200) &= ~1u;
            std::wstring::~wstring(a1 + 552, v43, v44);
          }
          std::wstring::~wstring(a1 + 520, v43, v44);
          *(_QWORD *)(a1 + 592) = 0;
          std::wstring::wstring(a1 + 600, *v13 + 184LL);
          v45 = *(_DWORD *)(a1 + 1200) | 0x1000;
          *(_DWORD *)(a1 + 1200) = v45;
          v46 = *(_QWORD *)(a1 + 616);
          std::wstring::~wstring(a1 + 600, v47, v48);
          v49 = 0;
          if ( v46 )
          {
            std::wstring::wstring(a1 + 632, *v13 + 184LL);
            *(_DWORD *)(a1 + 1200) = v45 | 0x2000;
            if ( *(_QWORD *)(a1 + 656) <= 7u )
              v50 = (const WCHAR *)(a1 + 632);
            else
              v50 = *(const WCHAR **)(a1 + 632);
            v51 = (HSTRING *)(a1 + 664);
            v52 = (const char **)wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(
                                   (HSTRING *)(a1 + 664),
                                   v50);
            v49 = 0;
            if ( (const char **)(a1 + 592) != v52 )
            {
              v49 = *v52;
              *(_QWORD *)(a1 + 592) = *v52;
              *v52 = 0;
            }
            if ( *v51 )
              WindowsDeleteString(*v51);
            std::wstring::~wstring(a1 + 632, v53, v54);
          }
          v55 = (_QWORD *)(a1 + 672);
          *(_QWORD *)(a1 + 672) = 0;
          v101 = v49;
          *(_QWORD *)bIgnoreCase = *(_QWORD *)(a1 + 504);
          v56 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, _QWORD))(**(_QWORD **)(a1 + 216) + 48LL))(
                  *(_QWORD *)(a1 + 216),
                  *(_QWORD *)(a1 + 584),
                  v104,
                  *(_QWORD *)(*v13 + 232LL));
          if ( v56 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x789,
              (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil\\profiledatastore.h",
              (const char *)(unsigned int)v56,
              bIgnoreCase[0]);
          v57 = *v55;
          *v55 = 0;
          *(_QWORD *)(a1 + 680) = v57;
          winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Internal::Storage::Cloud::CloudStoreBatchSaveItemData>,winrt::Windows::Internal::Storage::Cloud::CloudStoreBatchSaveItemData>::Append(
            a1 + 208,
            a1 + 680);
          if ( *(_QWORD *)(a1 + 680) )
            winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 680);
          if ( *v55 )
            (*(void (__fastcall **)(_QWORD, __int64, __int64))(*(_QWORD *)*v55 + 16LL))(*v55, v58, v59);
          if ( *(_QWORD *)(a1 + 592) )
            WindowsDeleteString(*(HSTRING *)(a1 + 592));
          if ( *(_QWORD *)(a1 + 584) )
            WindowsDeleteString(*(HSTRING *)(a1 + 584));
          if ( v104 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v104 + 16LL))(v104);
          if ( *(_QWORD *)(a1 + 504) )
            (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(a1 + 504) + 16LL))(
              *(_QWORD *)(a1 + 504),
              v58,
              v59);
          if ( *(_QWORD *)(a1 + 496) )
            winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 496);
          v13 += 2;
          v14 = v102;
        }
        v60 = *(_DWORD *)(a1 + 1272);
        if ( (v60 & 7) != 0 && (((*(_DWORD *)(a1 + 1272) & 7) - 1LL) & *(_DWORD *)(a1 + 1272) & 7) != 0 )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x91F,
            (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil\\profiledatastore.h",
            v12);
        if ( (v60 & 1) != 0 )
        {
          v62 = 1;
        }
        else if ( (v60 & 2) != 0 )
        {
          v62 = 2;
        }
        else
        {
          v62 = 0;
          if ( (v60 & 4) != 0 )
            v62 = 4;
        }
        v63 = v62 | 0x20;
        if ( (v60 & 0x10) == 0 )
          v63 = v62;
        *(_DWORD *)(a1 + 688) = v63;
        v64 = (__int64 *)(a1 + 696);
        *(_QWORD *)(a1 + 696) = 0;
        CloudStore = wil::details::SharedCloudStoreState::GetCloudStore(
                       *(_QWORD *)(*(_QWORD *)(a1 + 1224) + 16LL),
                       a1 + 728);
        *(_QWORD *)(a1 + 736) = *(_QWORD *)(a1 + 1256);
        View = (_QWORD *)winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Internal::Storage::Cloud::CloudStoreBatchSaveItemData>,winrt::Windows::Internal::Storage::Cloud::CloudStoreBatchSaveItemData>::GetView(
                           a1 + 208,
                           a1 + 784);
        *(_BYTE *)(a1 + 776) = 0;
        *(_QWORD *)(a1 + 768) = *View;
        v66 = (_QWORD *)wil::ProfileDataStore::GetTypeNameWideString<Windows::Data::Security::Passkey::ScenarioKeysItemPdr>(a1 + 824);
        v67 = v66;
        v68 = v66[2];
        if ( v66[3] > 7u )
          v67 = (_QWORD *)*v66;
        if ( (_DWORD)v68 )
        {
          if ( *((_WORD *)v67 + (unsigned int)v68) )
            abort();
          v69 = a1 + 800;
          *(_DWORD *)(a1 + 800) = 1;
          *(_DWORD *)(a1 + 804) = v68;
          *(_QWORD *)(a1 + 816) = v67;
        }
        else
        {
          v69 = 0;
        }
        *(_QWORD *)(a1 + 792) = v69;
        if ( *(_BYTE *)(a1 + 176) )
        {
          v70 = *(_QWORD *)winrt::hstring::hstring(
                             (winrt::hstring *)(a1 + 888),
                             (const struct winrt::hstring *)(a1 + 168));
          v71 = *(_DWORD *)(a1 + 1200) | 2;
        }
        else
        {
          *(_QWORD *)(a1 + 896) = 0;
          v70 = 0;
          v71 = *(_DWORD *)(a1 + 1200) | 4;
        }
        *(_DWORD *)(a1 + 1200) = v71;
        *(_QWORD *)(a1 + 856) = v70;
        v72 = *(_QWORD *)(a1 + 1224);
        *(_QWORD *)(a1 + 904) = *(_QWORD *)(v72 + 40);
        v73 = winrt::impl::consume_Windows_Internal_Storage_Cloud_ICloudStore2<winrt::Windows::Internal::Storage::Cloud::CloudStore>::BatchSaveAsync(
                CloudStore,
                (int)a1 + 936,
                (int)v72 + 32,
                (int)a1 + 904,
                a1 + 856,
                a1 + 792,
                a1 + 688,
                a1 + 768,
                a1 + 736);
        wil::details::AsyncOpWaiter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>>,winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>>::AsyncOpWaiter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>>,winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>>(
          a1 + 704,
          a1 + 1264,
          v73);
        if ( *(_QWORD *)(a1 + 936) )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 936);
        v76 = *(_DWORD *)(a1 + 1200);
        if ( (v76 & 4) != 0 )
        {
          *(_DWORD *)(a1 + 1200) = v76 & 0xFFFFFFFB;
          v77 = *(volatile signed __int32 **)(a1 + 896);
          if ( v77 )
          {
            v78 = _InterlockedDecrement(v77 + 6);
            if ( v78 )
            {
              if ( v78 < 0 )
                abort();
            }
            else
            {
              ProcessHeap = WINRT_IMPL_GetProcessHeap();
              WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v77);
            }
          }
        }
        v80 = *(_DWORD *)(a1 + 1200);
        if ( (v80 & 2) != 0 )
        {
          *(_DWORD *)(a1 + 1200) = v80 & 0xFFFFFFFD;
          v81 = *(volatile signed __int32 **)(a1 + 888);
          if ( v81 )
          {
            v82 = _InterlockedDecrement(v81 + 6);
            if ( v82 )
            {
              if ( v82 < 0 )
                abort();
            }
            else
            {
              v83 = WINRT_IMPL_GetProcessHeap();
              WINRT_IMPL_HeapFree(v83, 0, (LPVOID)v81);
            }
            *(_QWORD *)(a1 + 888) = 0;
          }
        }
        std::wstring::~wstring(a1 + 824, v74, v75);
        if ( *(_QWORD *)(a1 + 784) )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 784);
        if ( *(_QWORD *)(a1 + 728) )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 728);
        v84 = (__int64 *)wil::details::AsyncOpWaiter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>>,winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>>::WaitForResult(
                           a1 + 704,
                           a1 + 944);
        if ( v64 != v84 )
        {
          v85 = *v84;
          *v84 = 0;
          *v64 = v85;
        }
        if ( *(_QWORD *)(a1 + 944) )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 944);
        wil::details::AsyncOpWaiter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>,winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>::~AsyncOpWaiter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>,winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>(a1 + 704);
        *(_QWORD *)(a1 + 1064) = 0;
        *(_QWORD *)(a1 + 1072) = 0;
        *(_QWORD *)(a1 + 1080) = 0;
        v86 = winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::Storage::Cloud::CloudStoreData>,winrt::Windows::Internal::Storage::Cloud::CloudStoreData>::Size(a1 + 696);
        std::vector<wil::ProfileDataStoreSaveResult>::reserve(a1 + 1064, v86);
        v87 = 0;
        v88 = winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::Storage::Cloud::CloudStoreData>,winrt::Windows::Internal::Storage::Cloud::CloudStoreData>::Size(a1 + 696);
        while ( v87 != v88 )
        {
          winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>,winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>::GetAt(
            a1 + 696,
            a1 + 1088,
            v87);
          *(_DWORD *)(a1 + 1200) |= 0x4000u;
          v89 = wil::ProfileDataStoreSaveResult::ProfileDataStoreSaveResult(
                  (wil::ProfileDataStoreSaveResult *)(a1 + 1096),
                  (const struct winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult *)(a1 + 1088));
          v90 = v89;
          v91 = *(_QWORD *)(a1 + 1072);
          if ( v91 == *(_QWORD *)(a1 + 1080) )
          {
            std::vector<wil::ProfileDataStoreSaveResult>::_Emplace_reallocate<wil::ProfileDataStoreSaveResult>(
              a1 + 1064,
              v91,
              v89);
          }
          else
          {
            *(_QWORD *)v91 = *(_QWORD *)v89;
            *(_DWORD *)(v91 + 8) = *(_DWORD *)(v89 + 8);
            *(_DWORD *)(v91 + 12) = *(_DWORD *)(v89 + 12);
            *(_OWORD *)(v91 + 16) = 0;
            *(_QWORD *)(v91 + 32) = 0;
            *(_QWORD *)(v91 + 40) = 0;
            *(_OWORD *)(v91 + 16) = *(_OWORD *)(v89 + 16);
            *(_OWORD *)(v91 + 32) = *(_OWORD *)(v89 + 32);
            *(_QWORD *)(v89 + 32) = 0;
            *(_QWORD *)(v89 + 40) = 7;
            *(_WORD *)(v89 + 16) = 0;
            *(_QWORD *)(v91 + 48) = *(_QWORD *)(v89 + 48);
            *(_QWORD *)(a1 + 1072) += 56LL;
          }
          std::wstring::~wstring(a1 + 1112, v91, v90);
          if ( *(_QWORD *)(a1 + 1088) )
            winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 1088);
          ++v87;
        }
        v92 = *(_QWORD *)(a1 + 1080);
        *(_QWORD *)(a1 + 1080) = 0;
        v93 = *(_QWORD *)(a1 + 1072);
        *(_QWORD *)(a1 + 1072) = 0;
        v94 = *(_QWORD *)(a1 + 1064);
        *(_QWORD *)(a1 + 1064) = 0;
        *(_QWORD *)(a1 - 40) = v94;
        *(_QWORD *)(a1 - 32) = v93;
        *(_QWORD *)(a1 - 24) = v92;
        *(_DWORD *)(a1 - 48) = 1;
        std::vector<wil::ProfileDataStoreSaveResult>::_Tidy(a1 + 1064);
        if ( *(_QWORD *)(a1 + 696) )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 696);
        if ( *(_QWORD *)(a1 + 216) )
          (*(void (**)(void))(**(_QWORD **)(a1 + 216) + 16LL))();
        if ( *(_QWORD *)(a1 + 208) )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 208);
        if ( *(_BYTE *)(a1 + 176) )
        {
          v95 = *(volatile signed __int32 **)(a1 + 168);
          if ( v95 )
          {
            v96 = _InterlockedDecrement(v95 + 6);
            if ( v96 )
            {
              if ( v96 < 0 )
                abort();
            }
            else
            {
              v97 = WINRT_IMPL_GetProcessHeap();
              WINRT_IMPL_HeapFree(v97, 0, (LPVOID)v95);
            }
            *(_QWORD *)(a1 + 168) = 0;
          }
        }
        if ( *(_QWORD *)(a1 + 24) )
        {
          v98 = *(volatile signed __int32 **)(a1 + 24);
          if ( _InterlockedExchangeAdd(v98 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v98)(v98);
            if ( _InterlockedExchangeAdd(v98 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v98 + 8LL))(v98);
          }
        }
      }
      *(_QWORD *)(a1 + 1152) = a1 - 64;
      *(_WORD *)(a1 + 8) = 0;
      `wil::details::coro::promise_base<std::vector<wil::ProfileDataStoreSaveResult>>::final_suspend'::`2'::awaiter::await_suspend();
      return;
    default:
      __debugbreak();
      return;
  }
}

```

## disassembly

```asm
0x180021de0  mov     r11, rsp
0x180021de3  mov     [r11+10h], rbx
0x180021de7  mov     [r11+18h], rsi
0x180021deb  mov     [r11+8], rcx
0x180021def  push    rdi
0x180021df0  push    r12
0x180021df2  push    r13
0x180021df4  push    r14
0x180021df6  push    r15
0x180021df8  sub     rsp, 3F0h
0x180021dff  mov     rax, cs:__security_cookie
0x180021e06  xor     rax, rsp
0x180021e09  mov     [rsp+418h+var_38], rax
0x180021e11  mov     rsi, rcx
0x180021e14  mov     [rsp+418h+var_3B8], rcx
0x180021e19  movzx   eax, word ptr [rsi+8]
0x180021e1d  mov     [rsp+418h+var_3A8], ax
0x180021e22  inc     ax; switch 5 cases
0x180021e25  mov     r12d, 4
0x180021e2b  cmp     ax, r12w
0x180021e2f  ja      def_180021E4A; jumptable 0000000180021E4A default case, case 0
0x180021e35  movsx   rax, ax
0x180021e39  lea     rdx, __ImageBase
0x180021e40  mov     ecx, ds:(jpt_180021E4A - 180000000h)[rdx+rax*4]
0x180021e47  add     rcx, rdx
0x180021e4a  jmp     rcx; switch jump
0x180021e4c  jmp     loc_180022E9B; jumptable 0000000180021E4A case 3
0x180021e51  xor     r14d, r14d; jumptable 0000000180021E4A case 2
0x180021e54  mov     [rsi+4B0h], r14d
0x180021e5b  mov     rbx, [rsi+4C8h]
0x180021e62  mov     [rsi+10h], r14
0x180021e66  mov     [rsi+18h], r14
0x180021e6a  mov     rdx, [rbx+8]
0x180021e6e  test    rdx, rdx
0x180021e71  jz      loc_180022E75
0x180021e77  mov     eax, [rdx+8]
0x180021e7a  jmp     short loc_180021E86
0x180021e7c  lea     ecx, [rax+1]
0x180021e7f  lock cmpxchg [rdx+8], ecx
0x180021e84  jz      short loc_180021E8F
0x180021e86  test    eax, eax
0x180021e88  jnz     short loc_180021E7C
0x180021e8a  jmp     loc_180022E75
0x180021e8f  mov     rax, [rbx]
0x180021e92  mov     [rsi+10h], rax
0x180021e96  mov     rbx, [rbx+8]
0x180021e9a  mov     [rsi+18h], rbx
0x180021e9e  mov     dword ptr [rsi+4B0h], 8
0x180021ea8  mov     rax, [rsi+4F0h]
0x180021eaf  test    rax, rax
0x180021eb2  jz      loc_180021FDF
0x180021eb8  mov     eax, [rax+10h]
0x180021ebb  nop
0x180021ebc  test    eax, eax
0x180021ebe  jz      loc_180021FDF
0x180021ec4  lea     rdi, [rsi+70h]
0x180021ec8  xorps   xmm0, xmm0
0x180021ecb  movups  xmmword ptr [rdi], xmm0
0x180021ece  mov     [rsi+80h], r14
0x180021ed5  mov     eax, 7
0x180021eda  mov     [rsi+88h], rax
0x180021ee1  xor     ecx, ecx
0x180021ee3  mov     [rdi], cx
0x180021ee6  lea     r12, [rsi+38h]
0x180021eea  mov     [r12], r14
0x180021eee  mov     [rsi+40h], r14d
0x180021ef2  mov     dword ptr [rsi+44h], 800704C7h
0x180021ef9  movups  xmm1, xmmword ptr [rdi]
0x180021efc  movups  [rsp+418h+var_2C0], xmm1
0x180021f04  movups  xmm0, xmmword ptr [rdi+10h]
0x180021f08  movups  [rsp+418h+var_2B0], xmm0
0x180021f10  movups  xmmword ptr [rsi+48h], xmm1
0x180021f14  movups  xmmword ptr [rsi+58h], xmm0
0x180021f18  mov     [rsi+80h], r14
0x180021f1f  mov     [rsi+88h], rax
0x180021f26  xor     eax, eax
0x180021f28  mov     [rdi], ax
0x180021f2b  mov     [rsi+68h], r14
0x180021f2f  lea     rdx, [rsi+490h]
0x180021f36  mov     [rdx], r12
0x180021f39  mov     [rsi+498h], rdi
0x180021f40  lea     r15, [rsi+20h]
0x180021f44  mov     rcx, r15
0x180021f47  call    ??0?$vector@VProfileDataStoreSaveResult@wil@@V?$allocator@VProfileDataStoreSaveResult@wil@@@std@@@std@@QEAA@V?$initializer_list@VProfileDataStoreSaveResult@wil@@@1@AEBV?$allocator@VProfileDataStoreSaveResult@wil@@@1@@Z; std::vector<wil::ProfileDataStoreSaveResult>::vector<wil::ProfileDataStoreSaveResult>(std::initializer_list<wil::ProfileDataStoreSaveResult>,std::allocator<wil::ProfileDataStoreSaveResult> const &)
0x180021f4c  nop
0x180021f4d  mov     rdx, r15
0x180021f50  lea     rcx, [rsi-40h]
0x180021f54  call    ?return_value@?$task_promise@V?$vector@VProfileDataStoreSaveResult@wil@@V?$allocator@VProfileDataStoreSaveResult@wil@@@std@@@std@@@coro@details@wil@@QEAAXAEBV?$vector@VProfileDataStoreSaveResult@wil@@V?$allocator@VProfileDataStoreSaveResult@wil@@@std@@@std@@@Z; wil::details::coro::task_promise<std::vector<wil::ProfileDataStoreSaveResult>>::return_value(std::vector<wil::ProfileDataStoreSaveResult> const &)
0x180021f59  nop
0x180021f5a  mov     rcx, r15
0x180021f5d  call    ?_Tidy@?$vector@VProfileDataStoreSaveResult@wil@@V?$allocator@VProfileDataStoreSaveResult@wil@@@std@@@std@@AEAAXXZ; std::vector<wil::ProfileDataStoreSaveResult>::_Tidy(void)
0x180021f62  nop
0x180021f63  lea     r9, ??1ProfileDataStoreSaveResult@wil@@QEAA@XZ; void (*)(void *)
0x180021f6a  mov     edx, 38h ; '8'; unsigned __int64
0x180021f6f  lea     r8d, [rdx-37h]; unsigned __int64
0x180021f73  mov     rcx, r12; void *
0x180021f76  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180021f7b  nop
0x180021f7c  mov     rcx, rdi
0x180021f7f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180021f84  nop
0x180021f85  mov     [rsp+418h+var_368], rbx
0x180021f8d  test    rbx, rbx
0x180021f90  jz      short loc_180021FDA
0x180021f92  mov     rbx, [rsi+18h]
0x180021f96  mov     [rsp+418h+var_368], rbx
0x180021f9e  or      r15d, 0FFFFFFFFh
0x180021fa2  mov     eax, r15d
0x180021fa5  lock xadd [rbx+8], eax
0x180021faa  add     eax, r15d
0x180021fad  jnz     short loc_180021FDA
0x180021faf  mov     rax, [rbx]
0x180021fb2  mov     rcx, rbx
0x180021fb5  mov     rax, [rax]
0x180021fb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021fbd  mov     eax, r15d
0x180021fc0  lock xadd [rbx+0Ch], eax
0x180021fc5  add     eax, r15d
0x180021fc8  jnz     short loc_180021FDA
0x180021fca  mov     rax, [rbx]
0x180021fcd  mov     rcx, rbx
0x180021fd0  mov     rax, [rax+8]
0x180021fd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021fd9  nop
0x180021fda  jmp     loc_180022E80
0x180021fdf  mov     rax, [rsi+4D8h]
0x180021fe6  cmp     [rsi+4D0h], rax
0x180021fed  jz      loc_180022DF0
0x180021ff3  mov     [rsi+0B0h], r14b
0x180021ffa  lea     rbx, [rsi+0B8h]
0x180022001  mov     [rbx], r14
0x180022004  mov     [rsi+0C0h], r14
0x18002200b  mov     [rsi+0C8h], r14
0x180022012  lea     rcx, [rsi+0D0h]
0x180022019  mov     rdx, rbx
0x18002201c  call    ??$single_threaded_vector@UCloudStoreBatchSaveItemData@Cloud@Storage@Internal@Windows@winrt@@V?$allocator@UCloudStoreBatchSaveItemData@Cloud@Storage@Internal@Windows@winrt@@@std@@@winrt@@YA?AU?$IVector@UCloudStoreBatchSaveItemData@Cloud@Storage@Internal@Windows@winrt@@@Collections@Foundation@Windows@0@$$QEAV?$vector@UCloudStoreBatchSaveItemData@Cloud@Storage@Internal@Windows@winrt@@V?$allocator@UCloudStoreBatchSaveItemData@Cloud@Storage@Internal@Windows@winrt@@@std@@@std@@@Z; winrt::single_threaded_vector<winrt::Windows::Internal::Storage::Cloud::CloudStoreBatchSaveItemData,std::allocator<winrt::Windows::Internal::Storage::Cloud::CloudStoreBatchSaveItemData>>(std::vector<winrt::Windows::Internal::Storage::Cloud::CloudStoreBatchSaveItemData> &&)
0x180022021  nop
0x180022022  mov     rcx, rbx
0x180022025  call    ??1?$vector@UCloudStoreBatchSaveItemData@Cloud@Storage@Internal@Windows@winrt@@V?$allocator@UCloudStoreBatchSaveItemData@Cloud@Storage@Internal@Windows@winrt@@@std@@@std@@QEAA@XZ; std::vector<winrt::Windows::Internal::Storage::Cloud::CloudStoreBatchSaveItemData>::~vector<winrt::Windows::Internal::Storage::Cloud::CloudStoreBatchSaveItemData>(void)
0x18002202a  lea     rcx, [rsi+0D8h]
0x180022031  call    ??$GetActivationFactoryPdr@UICloudStoreBatchSaveItemDataFactory@Cloud@Storage@Internal@Windows@@@details@wil@@YA?AV?$com_ptr_t@UICloudStoreBatchSaveItemDataFactory@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@1@PEBG@Z; wil::details::GetActivationFactoryPdr<Windows::Internal::Storage::Cloud::ICloudStoreBatchSaveItemDataFactory>(ushort const *)
0x180022036  nop
0x180022037  mov     r13, [rsi+4D0h]
0x18002203e  mov     rax, [rsi+4D8h]
0x180022045  mov     [rsp+418h+var_3B0], rax
0x18002204a  or      r15d, 0FFFFFFFFh
0x18002204e  cmp     r13, rax
0x180022051  jz      loc_180022691
0x180022057  mov     rbx, [r13+0]
0x18002205b  mov     al, [rsi+0B0h]
0x180022061  mov     [rsp+418h+var_378], al
0x180022068  lea     rdx, [rbx+58h]
0x18002206c  test    al, al
0x18002206e  jnz     loc_180022145
0x180022074  lea     rcx, [rsi+0F0h]
0x18002207b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180022080  nop
0x180022081  lea     r12, [rsi+110h]
0x180022088  lea     rdx, [rbx+78h]
0x18002208c  mov     rcx, r12
0x18002208f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180022094  nop
0x180022095  lea     rcx, [rsi+130h]
0x18002209c  lea     rdx, [rbx+98h]
0x1800220a3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800220a8  nop
0x1800220a9  mov     ebx, [rsi+4B0h]
0x1800220af  mov     [rsp+418h+var_3C8], ebx
0x1800220b3  or      ebx, 10h
0x1800220b6  mov     [rsi+4B0h], ebx
0x1800220bc  lea     rdi, [rsi+150h]
0x1800220c3  mov     rdx, r12
0x1800220c6  mov     rcx, rdi
0x1800220c9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800220ce  mov     [rsp+418h+var_3C8], ebx
0x1800220d2  or      ebx, 20h
0x1800220d5  mov     [rsi+4B0h], ebx
0x1800220db  mov     rax, [rsi+168h]
0x1800220e2  mov     [rsp+418h+var_288], rax
0x1800220ea  cmp     rax, 7
0x1800220ee  jbe     short loc_1800220FD
0x1800220f0  mov     rax, [rdi]
0x1800220f3  mov     [rsp+418h+var_2A0], rax
0x1800220fb  jmp     short loc_180022100
0x1800220fd  mov     rax, rdi
0x180022100  lea     rdx, [rsi+0E0h]
0x180022107  mov     [rdx], rax
0x18002210a  lea     rcx, [rsi+0A8h]
0x180022111  call    ??$?4PEBG$0A@@?$optional@Uhstring@winrt@@@std@@QEAAAEAV01@$$QEAPEBG@Z; std::optional<winrt::hstring>::operator=<ushort const *,0>(ushort const * &&)
0x180022116  nop
0x180022117  mov     rcx, rdi
0x18002211a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002211f  nop
0x180022120  lea     rcx, [rsi+130h]
0x180022127  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002212c  mov     rcx, r12
0x18002212f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180022134  lea     rcx, [rsi+0F0h]
0x18002213b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180022140  jmp     loc_180022278
0x180022145  lea     rcx, [rsi+170h]
0x18002214c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180022151  nop
0x180022152  lea     r12, [rsi+190h]
0x180022159  lea     rdx, [rbx+78h]
0x18002215d  mov     rcx, r12
0x180022160  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180022165  nop
0x180022166  lea     rcx, [rsi+1B0h]
0x18002216d  lea     rdx, [rbx+98h]
0x180022174  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180022179  nop
0x18002217a  mov     ebx, [rsi+4B0h]
0x180022180  mov     [rsp+418h+var_3C8], ebx
0x180022184  or      ebx, 40h
0x180022187  mov     [rsi+4B0h], ebx
0x18002218d  lea     rdi, [rsi+1D0h]
0x180022194  mov     rdx, r12
0x180022197  mov     rcx, rdi
0x18002219a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002219f  mov     [rsp+418h+var_3C8], ebx
0x1800221a3  bts     ebx, 7
0x1800221a7  mov     [rsi+4B0h], ebx
0x1800221ad  mov     rax, [rsi+1E8h]
0x1800221b4  mov     [rsp+418h+var_268], rax
0x1800221bc  cmp     rax, 7
0x1800221c0  jbe     short loc_1800221CF
0x1800221c2  mov     r8, [rdi]
0x1800221c5  mov     [rsp+418h+var_280], r8
0x1800221cd  jmp     short loc_1800221D2
0x1800221cf  mov     r8, rdi; lpString2
0x1800221d2  mov     rax, [rsi+0A8h]
0x1800221d9  mov     [rsp+418h+var_380], rax
0x1800221e1  test    rax, rax
0x1800221e4  jz      short loc_1800221FB
0x1800221e6  mov     rax, [rsi+0A8h]
0x1800221ed  mov     [rsp+418h+var_380], rax
0x1800221f5  mov     rcx, [rax+10h]
0x1800221f9  jmp     short loc_180022202
0x1800221fb  lea     rcx, String1; lpString1
0x180022202  mov     [rsp+418h+bIgnoreCase], 1; bIgnoreCase
0x18002220a  mov     r9d, r15d; cchCount2
0x18002220d  mov     edx, r15d; cchCount1
0x180022210  call    cs:__imp_CompareStringOrdinal
0x180022216  mov     ebx, eax
0x180022218  mov     rcx, rdi
0x18002221b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180022220  nop
0x180022221  lea     rcx, [rsi+1B0h]
0x180022228  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002222d  mov     rcx, r12
0x180022230  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180022235  lea     rcx, [rsi+170h]
0x18002223c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180022241  cmp     ebx, 2
0x180022244  jz      short loc_180022278
0x180022246  mov     ecx, 80070057h
0x18002224b  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180022250  mov     r9d, eax; char *
0x180022253  mov     rcx, [rsp+418h]; this
0x18002225b  lea     rax, aAllPayloadsMus; "All payloads must be for the same colle"...
0x180022262  mov     qword ptr [rsp+418h+bIgnoreCase], rax; int
0x180022267  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\sdk\\inc\\wil\\pr"...
0x18002226e  mov     edx, 771h; void *
0x180022273  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x180022278  lea     rbx, [rsi+1F0h]
0x18002227f  mov     rdx, [r13+0]
0x180022283  mov     rcx, rbx
0x180022286  call    ??$Marshal@V?$ProfileDataItem@UScenarioKeysItemPdr@Passkey@Security@Data@Windows@@@wil@@@ProfileDataStore@wil@@CA?AUIBuffer@Streams@Storage@Windows@winrt@@AEBV?$ProfileDataItem@UScenarioKeysItemPdr@Passkey@Security@Data@Windows@@@1@@Z; wil::ProfileDataStore::Marshal<wil::ProfileDataItem<Windows::Data::Security::Passkey::ScenarioKeysItemPdr>>(wil::ProfileDataItem<Windows::Data::Security::Passkey::ScenarioKeysItemPdr> const &)
0x18002228b  nop
0x18002228c  mov     rax, [rbx]
0x18002228f  mov     [rsp+418h+var_390], rax
0x180022297  mov     [rsi+1F8h], rax
0x18002229e  mov     rax, [rbx]
0x1800222a1  mov     [rsp+418h+var_390], rax
0x1800222a9  test    rax, rax
0x1800222ac  jz      short loc_1800222C5
0x1800222ae  mov     rcx, [rbx]
0x1800222b1  mov     [rsp+418h+var_390], rcx
0x1800222b9  mov     rax, [rcx]
0x1800222bc  mov     rax, [rax+8]
0x1800222c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800222c5  mov     rax, [r13+0]
0x1800222c9  mov     rcx, [rax+40h]
0x1800222cd  mov     [rsp+418h+var_388], rcx
0x1800222d5  mov     [rsi+200h], rcx
0x1800222dc  test    rcx, rcx
0x1800222df  jz      short loc_1800222EE
0x1800222e1  mov     rax, [rcx]
0x1800222e4  mov     rax, [rax+8]
0x1800222e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800222ed  nop
0x1800222ee  lea     r12, [rsi+208h]
0x1800222f5  mov     rdx, [r13+0]
0x1800222f9  add     rdx, 58h ; 'X'
0x1800222fd  mov     rcx, r12
0x180022300  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180022305  mov     ebx, [rsi+4B0h]
0x18002230b  mov     [rsp+418h+var_3C8], ebx
0x18002230f  or      ebx, 300h
  ... truncated ...
```
