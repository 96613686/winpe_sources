# wil::ProfileDataStore::CallBatchSaveAsync$_ResumeCoro$1_Windows::Data::Security::Passkey::PasskeyItemPdr_

- ea: `0x18001fb70`
- end: `0x180020ca0`
- name: `wil::ProfileDataStore::CallBatchSaveAsync$_ResumeCoro$1_Windows::Data::Security::Passkey::PasskeyItemPdr_`
- size: `4400`
- prototype: ``
- caller_count: `1`
- callee_count: `41`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180022f18`

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
- `0x18001fb70`
- `0x1800318c8`
- `0x1800378f4`
- `0x18003b304`
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

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180020533`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002069e`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800206fc`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180020b12`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180020533`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002069e`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800206fc`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180020b12`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001ffa0`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001ffa0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180020244`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180020373`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002039c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180020244`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180020373`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002039c`

## pseudocode

```c
// Hidden C++ exception states: #wind=57
void __fastcall wil::ProfileDataStore::CallBatchSaveAsync__ResumeCoro_1_Windows::Data::Security::Passkey::PasskeyItemPdr_(
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
  __int64 v27; // r8
  __int64 v28; // r9
  int v29; // ebx
  const WCHAR *v30; // r8
  const WCHAR *v31; // rcx
  int v32; // ebx
  __int64 v33; // rdx
  __int64 v34; // r8
  __int64 v35; // rdx
  __int64 v36; // r8
  __int64 v37; // rdx
  __int64 v38; // r8
  __int64 v39; // rdx
  __int64 v40; // r8
  const char *v41; // r9
  __int64 v42; // rcx
  int v43; // ebx
  const WCHAR *v44; // rdi
  __int64 v45; // rdx
  __int64 v46; // r8
  int v47; // r12d
  __int64 v48; // rdi
  __int64 v49; // rdx
  __int64 v50; // r8
  const char *v51; // rbx
  const WCHAR *v52; // rdx
  HSTRING *v53; // r12
  const char **v54; // rax
  __int64 v55; // rdx
  __int64 v56; // r8
  _QWORD *v57; // r12
  int v58; // eax
  __int64 v59; // rax
  __int64 v60; // rdx
  __int64 v61; // r8
  int v62; // edx
  int v64; // ecx
  int v65; // eax
  __int64 *v66; // r12
  _QWORD *View; // rax
  _QWORD *v68; // rax
  _QWORD *v69; // rcx
  __int64 v70; // rdx
  __int64 v71; // rax
  __int64 v72; // rax
  int v73; // ecx
  __int64 v74; // r8
  __int64 v75; // rax
  __int64 v76; // rdx
  __int64 v77; // r8
  int v78; // eax
  volatile signed __int32 *v79; // rbx
  int v80; // eax
  HANDLE ProcessHeap; // rax
  int v82; // eax
  volatile signed __int32 *v83; // rbx
  int v84; // eax
  HANDLE v85; // rax
  __int64 *v86; // rax
  __int64 v87; // rdx
  unsigned int v88; // eax
  unsigned int v89; // ebx
  int v90; // r13d
  __int64 v91; // rax
  __int64 v92; // r8
  __int64 v93; // rdx
  __int64 v94; // r8
  __int64 v95; // rdx
  __int64 v96; // rax
  volatile signed __int32 *v97; // rbx
  int v98; // eax
  HANDLE v99; // rax
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
        goto LABEL_141;
      v4 = *(_DWORD *)(v3 + 8);
      do
      {
        if ( !v4 )
LABEL_141:
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
LABEL_140:
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
          v11 = *(volatile signed __int32 **)(a1 + 24);
          if ( _InterlockedExchangeAdd(v11 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
            if ( _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1 )
              goto LABEL_140;
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
            v29 = *(_DWORD *)(a1 + 1200) | 0x40;
            *(_DWORD *)(a1 + 1200) = v29;
            std::wstring::wstring(a1 + 464, a1 + 400);
            *(_DWORD *)(a1 + 1200) = v29 | 0x80;
            if ( *(_QWORD *)(a1 + 488) <= 7u )
              v30 = (const WCHAR *)(a1 + 464);
            else
              v30 = *(const WCHAR **)(a1 + 464);
            if ( *(_QWORD *)(a1 + 168) )
              v31 = *(const WCHAR **)(*(_QWORD *)(a1 + 168) + 16LL);
            else
              v31 = &String1;
            v32 = CompareStringOrdinal(v31, -1, v30, -1, 1);
            std::wstring::~wstring(a1 + 464, v33, v34);
            std::wstring::~wstring(a1 + 432, v35, v36);
            std::wstring::~wstring(a1 + 400, v37, v38);
            std::wstring::~wstring(a1 + 368, v39, v40);
            if ( v32 != 2 )
            {
              v41 = (const char *)(unsigned int)wil::verify_hresult<long>(2147942487LL);
              wil::details::in1diag3::Throw_HrMsg(
                retaddr,
                (void *)0x771,
                (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil\\profiledatastore.h",
                v41,
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
          wil::ProfileDataStore::Marshal<wil::ProfileDataItem<Windows::Data::Security::Passkey::PasskeyItemPdr>>(
            a1 + 496,
            *v13,
            v27,
            v28);
          *(_QWORD *)(a1 + 504) = *(_QWORD *)(a1 + 496);
          if ( *(_QWORD *)(a1 + 496) )
            (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 496) + 8LL))(*(_QWORD *)(a1 + 496));
          v42 = *(_QWORD *)(*v13 + 64LL);
          v104 = v42;
          *(_QWORD *)(a1 + 512) = v42;
          if ( v42 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 8LL))(v42);
          std::wstring::wstring(a1 + 520, *v13 + 88LL);
          v43 = *(_DWORD *)(a1 + 1200) | 0x300;
          *(_DWORD *)(a1 + 1200) = v43;
          if ( *(_QWORD *)(a1 + 536) )
          {
            v44 = (const WCHAR *)(a1 + 552);
            std::wstring::wstring(a1 + 552, *v13 + 88LL);
            v43 |= 0xC01u;
            *(_DWORD *)(a1 + 1200) = v43;
            if ( *(_QWORD *)(a1 + 576) > 7u )
              v44 = *(const WCHAR **)v44;
          }
          else
          {
            v44 = L"default";
          }
          wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(
            (HSTRING *)(a1 + 584),
            v44);
          if ( (v43 & 1) != 0 )
          {
            *(_DWORD *)(a1 + 1200) &= ~1u;
            std::wstring::~wstring(a1 + 552, v45, v46);
          }
          std::wstring::~wstring(a1 + 520, v45, v46);
          *(_QWORD *)(a1 + 592) = 0;
          std::wstring::wstring(a1 + 600, *v13 + 184LL);
          v47 = *(_DWORD *)(a1 + 1200) | 0x1000;
          *(_DWORD *)(a1 + 1200) = v47;
          v48 = *(_QWORD *)(a1 + 616);
          std::wstring::~wstring(a1 + 600, v49, v50);
          v51 = 0;
          if ( v48 )
          {
            std::wstring::wstring(a1 + 632, *v13 + 184LL);
            *(_DWORD *)(a1 + 1200) = v47 | 0x2000;
            if ( *(_QWORD *)(a1 + 656) <= 7u )
              v52 = (const WCHAR *)(a1 + 632);
            else
              v52 = *(const WCHAR **)(a1 + 632);
            v53 = (HSTRING *)(a1 + 664);
            v54 = (const char **)wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>(
                                   (HSTRING *)(a1 + 664),
                                   v52);
            v51 = 0;
            if ( (const char **)(a1 + 592) != v54 )
            {
              v51 = *v54;
              *(_QWORD *)(a1 + 592) = *v54;
              *v54 = 0;
            }
            if ( *v53 )
              WindowsDeleteString(*v53);
            std::wstring::~wstring(a1 + 632, v55, v56);
          }
          v57 = (_QWORD *)(a1 + 672);
          *(_QWORD *)(a1 + 672) = 0;
          v101 = v51;
          *(_QWORD *)bIgnoreCase = *(_QWORD *)(a1 + 504);
          v58 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, _QWORD))(**(_QWORD **)(a1 + 216) + 48LL))(
                  *(_QWORD *)(a1 + 216),
                  *(_QWORD *)(a1 + 584),
                  v104,
                  *(_QWORD *)(*v13 + 232LL));
          if ( v58 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x789,
              (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil\\profiledatastore.h",
              (const char *)(unsigned int)v58,
              bIgnoreCase[0]);
          v59 = *v57;
          *v57 = 0;
          *(_QWORD *)(a1 + 680) = v59;
          winrt::impl::consume_Windows_Foundation_Collections_IVector<winrt::Windows::Foundation::Collections::IVector<winrt::Windows::Internal::Storage::Cloud::CloudStoreBatchSaveItemData>,winrt::Windows::Internal::Storage::Cloud::CloudStoreBatchSaveItemData>::Append(
            a1 + 208,
            a1 + 680);
          if ( *(_QWORD *)(a1 + 680) )
            winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 680);
          if ( *v57 )
            (*(void (__fastcall **)(_QWORD, __int64, __int64))(*(_QWORD *)*v57 + 16LL))(*v57, v60, v61);
          if ( *(_QWORD *)(a1 + 592) )
            WindowsDeleteString(*(HSTRING *)(a1 + 592));
          if ( *(_QWORD *)(a1 + 584) )
            WindowsDeleteString(*(HSTRING *)(a1 + 584));
          if ( v104 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v104 + 16LL))(v104);
          if ( *(_QWORD *)(a1 + 504) )
            (*(void (__fastcall **)(_QWORD, __int64, __int64))(**(_QWORD **)(a1 + 504) + 16LL))(
              *(_QWORD *)(a1 + 504),
              v60,
              v61);
          if ( *(_QWORD *)(a1 + 496) )
            winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 496);
          v13 += 2;
          v14 = v102;
        }
        v62 = *(_DWORD *)(a1 + 1272);
        if ( (v62 & 7) != 0 && (((*(_DWORD *)(a1 + 1272) & 7) - 1LL) & *(_DWORD *)(a1 + 1272) & 7) != 0 )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x91F,
            (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil\\profiledatastore.h",
            v12);
        if ( (v62 & 1) != 0 )
        {
          v64 = 1;
        }
        else if ( (v62 & 2) != 0 )
        {
          v64 = 2;
        }
        else
        {
          v64 = 0;
          if ( (v62 & 4) != 0 )
            v64 = 4;
        }
        v65 = v64 | 0x20;
        if ( (v62 & 0x10) == 0 )
          v65 = v64;
        *(_DWORD *)(a1 + 688) = v65;
        v66 = (__int64 *)(a1 + 696);
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
        v68 = (_QWORD *)wil::ProfileDataStore::GetTypeNameWideString<Windows::Data::Security::Passkey::PasskeyItemPdr>(a1 + 824);
        v69 = v68;
        v70 = v68[2];
        if ( v68[3] > 7u )
          v69 = (_QWORD *)*v68;
        if ( (_DWORD)v70 )
        {
          if ( *((_WORD *)v69 + (unsigned int)v70) )
            abort();
          v71 = a1 + 800;
          *(_DWORD *)(a1 + 800) = 1;
          *(_DWORD *)(a1 + 804) = v70;
          *(_QWORD *)(a1 + 816) = v69;
        }
        else
        {
          v71 = 0;
        }
        *(_QWORD *)(a1 + 792) = v71;
        if ( *(_BYTE *)(a1 + 176) )
        {
          v72 = *(_QWORD *)winrt::hstring::hstring(
                             (winrt::hstring *)(a1 + 888),
                             (const struct winrt::hstring *)(a1 + 168));
          v73 = *(_DWORD *)(a1 + 1200) | 2;
        }
        else
        {
          *(_QWORD *)(a1 + 896) = 0;
          v72 = 0;
          v73 = *(_DWORD *)(a1 + 1200) | 4;
        }
        *(_DWORD *)(a1 + 1200) = v73;
        *(_QWORD *)(a1 + 856) = v72;
        v74 = *(_QWORD *)(a1 + 1224);
        *(_QWORD *)(a1 + 904) = *(_QWORD *)(v74 + 40);
        v75 = winrt::impl::consume_Windows_Internal_Storage_Cloud_ICloudStore2<winrt::Windows::Internal::Storage::Cloud::CloudStore>::BatchSaveAsync(
                CloudStore,
                (int)a1 + 936,
                (int)v74 + 32,
                (int)a1 + 904,
                a1 + 856,
                a1 + 792,
                a1 + 688,
                a1 + 768,
                a1 + 736);
        wil::details::AsyncOpWaiter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>>,winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>>::AsyncOpWaiter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>>,winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>>(
          a1 + 704,
          a1 + 1264,
          v75);
        if ( *(_QWORD *)(a1 + 936) )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 936);
        v78 = *(_DWORD *)(a1 + 1200);
        if ( (v78 & 4) != 0 )
        {
          *(_DWORD *)(a1 + 1200) = v78 & 0xFFFFFFFB;
          v79 = *(volatile signed __int32 **)(a1 + 896);
          if ( v79 )
          {
            v80 = _InterlockedDecrement(v79 + 6);
            if ( v80 )
            {
              if ( v80 < 0 )
                abort();
            }
            else
            {
              ProcessHeap = WINRT_IMPL_GetProcessHeap();
              WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v79);
            }
          }
        }
        v82 = *(_DWORD *)(a1 + 1200);
        if ( (v82 & 2) != 0 )
        {
          *(_DWORD *)(a1 + 1200) = v82 & 0xFFFFFFFD;
          v83 = *(volatile signed __int32 **)(a1 + 888);
          if ( v83 )
          {
            v84 = _InterlockedDecrement(v83 + 6);
            if ( v84 )
            {
              if ( v84 < 0 )
                abort();
            }
            else
            {
              v85 = WINRT_IMPL_GetProcessHeap();
              WINRT_IMPL_HeapFree(v85, 0, (LPVOID)v83);
            }
            *(_QWORD *)(a1 + 888) = 0;
          }
        }
        std::wstring::~wstring(a1 + 824, v76, v77);
        if ( *(_QWORD *)(a1 + 784) )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 784);
        if ( *(_QWORD *)(a1 + 728) )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 728);
        v86 = (__int64 *)wil::details::AsyncOpWaiter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>>,winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>>::WaitForResult(
                           a1 + 704,
                           a1 + 944);
        if ( v66 != v86 )
        {
          v87 = *v86;
          *v86 = 0;
          *v66 = v87;
        }
        if ( *(_QWORD *)(a1 + 944) )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 944);
        wil::details::AsyncOpWaiter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>,winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>::~AsyncOpWaiter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>,winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>(a1 + 704);
        *(_QWORD *)(a1 + 1064) = 0;
        *(_QWORD *)(a1 + 1072) = 0;
        *(_QWORD *)(a1 + 1080) = 0;
        v88 = winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::Storage::Cloud::CloudStoreData>,winrt::Windows::Internal::Storage::Cloud::CloudStoreData>::Size(a1 + 696);
        std::vector<wil::ProfileDataStoreSaveResult>::reserve(a1 + 1064, v88);
        v89 = 0;
        v90 = winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::Storage::Cloud::CloudStoreData>,winrt::Windows::Internal::Storage::Cloud::CloudStoreData>::Size(a1 + 696);
        while ( v89 != v90 )
        {
          winrt::impl::consume_Windows_Foundation_Collections_IVectorView<winrt::Windows::Foundation::Collections::IVectorView<winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>,winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>::GetAt(
            a1 + 696,
            a1 + 1088,
            v89);
          *(_DWORD *)(a1 + 1200) |= 0x4000u;
          v91 = wil::ProfileDataStoreSaveResult::ProfileDataStoreSaveResult(
                  (wil::ProfileDataStoreSaveResult *)(a1 + 1096),
                  (const struct winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult *)(a1 + 1088));
          v92 = v91;
          v93 = *(_QWORD *)(a1 + 1072);
          if ( v93 == *(_QWORD *)(a1 + 1080) )
          {
            std::vector<wil::ProfileDataStoreSaveResult>::_Emplace_reallocate<wil::ProfileDataStoreSaveResult>(
              a1 + 1064,
              v93,
              v91);
          }
          else
          {
            *(_QWORD *)v93 = *(_QWORD *)v91;
            *(_DWORD *)(v93 + 8) = *(_DWORD *)(v91 + 8);
            *(_DWORD *)(v93 + 12) = *(_DWORD *)(v91 + 12);
            *(_OWORD *)(v93 + 16) = 0;
            *(_QWORD *)(v93 + 32) = 0;
            *(_QWORD *)(v93 + 40) = 0;
            *(_OWORD *)(v93 + 16) = *(_OWORD *)(v91 + 16);
            *(_OWORD *)(v93 + 32) = *(_OWORD *)(v91 + 32);
            *(_QWORD *)(v91 + 32) = 0;
            *(_QWORD *)(v91 + 40) = 7;
            *(_WORD *)(v91 + 16) = 0;
            *(_QWORD *)(v93 + 48) = *(_QWORD *)(v91 + 48);
            *(_QWORD *)(a1 + 1072) += 56LL;
          }
          std::wstring::~wstring(a1 + 1112, v93, v92);
          if ( *(_QWORD *)(a1 + 1088) )
            winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 1088);
          ++v89;
        }
        v94 = *(_QWORD *)(a1 + 1080);
        *(_QWORD *)(a1 + 1080) = 0;
        v95 = *(_QWORD *)(a1 + 1072);
        *(_QWORD *)(a1 + 1072) = 0;
        v96 = *(_QWORD *)(a1 + 1064);
        *(_QWORD *)(a1 + 1064) = 0;
        *(_QWORD *)(a1 - 40) = v96;
        *(_QWORD *)(a1 - 32) = v95;
        *(_QWORD *)(a1 - 24) = v94;
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
          v97 = *(volatile signed __int32 **)(a1 + 168);
          if ( v97 )
          {
            v98 = _InterlockedDecrement(v97 + 6);
            if ( v98 )
            {
              if ( v98 < 0 )
                abort();
            }
            else
            {
              v99 = WINRT_IMPL_GetProcessHeap();
              WINRT_IMPL_HeapFree(v99, 0, (LPVOID)v97);
            }
            *(_QWORD *)(a1 + 168) = 0;
          }
        }
        if ( *(_QWORD *)(a1 + 24) )
        {
          v11 = *(volatile signed __int32 **)(a1 + 24);
          if ( _InterlockedExchangeAdd(v11 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
            if ( _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1 )
              goto LABEL_140;
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
0x18001fb70  mov     r11, rsp
0x18001fb73  mov     [r11+10h], rbx
0x18001fb77  mov     [r11+18h], rsi
0x18001fb7b  mov     [r11+8], rcx
0x18001fb7f  push    rdi
0x18001fb80  push    r12
0x18001fb82  push    r13
0x18001fb84  push    r14
0x18001fb86  push    r15
0x18001fb88  sub     rsp, 3F0h
0x18001fb8f  mov     rax, cs:__security_cookie
0x18001fb96  xor     rax, rsp
0x18001fb99  mov     [rsp+418h+var_38], rax
0x18001fba1  mov     rsi, rcx
0x18001fba4  mov     [rsp+418h+var_3B8], rcx
0x18001fba9  movzx   eax, word ptr [rsi+8]
0x18001fbad  mov     [rsp+418h+var_3A8], ax
0x18001fbb2  inc     ax; switch 5 cases
0x18001fbb5  mov     r12d, 4
0x18001fbbb  cmp     ax, r12w
0x18001fbbf  ja      def_18001FBDA; jumptable 000000018001FBDA default case, case 0
0x18001fbc5  movsx   rax, ax
0x18001fbc9  lea     rdx, __ImageBase
0x18001fbd0  mov     ecx, ds:(jpt_18001FBDA - 180000000h)[rdx+rax*4]
0x18001fbd7  add     rcx, rdx
0x18001fbda  jmp     rcx; switch jump
0x18001fbdc  jmp     loc_180020C2B; jumptable 000000018001FBDA case 3
0x18001fbe1  xor     r14d, r14d; jumptable 000000018001FBDA case 2
0x18001fbe4  mov     [rsi+4B0h], r14d
0x18001fbeb  mov     rbx, [rsi+4C8h]
0x18001fbf2  mov     [rsi+10h], r14
0x18001fbf6  mov     [rsi+18h], r14
0x18001fbfa  mov     rdx, [rbx+8]
0x18001fbfe  test    rdx, rdx
0x18001fc01  jz      loc_180020C05
0x18001fc07  mov     eax, [rdx+8]
0x18001fc0a  jmp     short loc_18001FC16
0x18001fc0c  lea     ecx, [rax+1]
0x18001fc0f  lock cmpxchg [rdx+8], ecx
0x18001fc14  jz      short loc_18001FC1F
0x18001fc16  test    eax, eax
0x18001fc18  jnz     short loc_18001FC0C
0x18001fc1a  jmp     loc_180020C05
0x18001fc1f  mov     rax, [rbx]
0x18001fc22  mov     [rsi+10h], rax
0x18001fc26  mov     rbx, [rbx+8]
0x18001fc2a  mov     [rsi+18h], rbx
0x18001fc2e  mov     dword ptr [rsi+4B0h], 8
0x18001fc38  mov     rax, [rsi+4F0h]
0x18001fc3f  test    rax, rax
0x18001fc42  jz      loc_18001FD6F
0x18001fc48  mov     eax, [rax+10h]
0x18001fc4b  nop
0x18001fc4c  test    eax, eax
0x18001fc4e  jz      loc_18001FD6F
0x18001fc54  lea     rdi, [rsi+70h]
0x18001fc58  xorps   xmm0, xmm0
0x18001fc5b  movups  xmmword ptr [rdi], xmm0
0x18001fc5e  mov     [rsi+80h], r14
0x18001fc65  mov     eax, 7
0x18001fc6a  mov     [rsi+88h], rax
0x18001fc71  xor     ecx, ecx
0x18001fc73  mov     [rdi], cx
0x18001fc76  lea     r12, [rsi+38h]
0x18001fc7a  mov     [r12], r14
0x18001fc7e  mov     [rsi+40h], r14d
0x18001fc82  mov     dword ptr [rsi+44h], 800704C7h
0x18001fc89  movups  xmm1, xmmword ptr [rdi]
0x18001fc8c  movups  [rsp+418h+var_2C0], xmm1
0x18001fc94  movups  xmm0, xmmword ptr [rdi+10h]
0x18001fc98  movups  [rsp+418h+var_2B0], xmm0
0x18001fca0  movups  xmmword ptr [rsi+48h], xmm1
0x18001fca4  movups  xmmword ptr [rsi+58h], xmm0
0x18001fca8  mov     [rsi+80h], r14
0x18001fcaf  mov     [rsi+88h], rax
0x18001fcb6  xor     eax, eax
0x18001fcb8  mov     [rdi], ax
0x18001fcbb  mov     [rsi+68h], r14
0x18001fcbf  lea     rdx, [rsi+490h]
0x18001fcc6  mov     [rdx], r12
0x18001fcc9  mov     [rsi+498h], rdi
0x18001fcd0  lea     r15, [rsi+20h]
0x18001fcd4  mov     rcx, r15
0x18001fcd7  call    ??0?$vector@VProfileDataStoreSaveResult@wil@@V?$allocator@VProfileDataStoreSaveResult@wil@@@std@@@std@@QEAA@V?$initializer_list@VProfileDataStoreSaveResult@wil@@@1@AEBV?$allocator@VProfileDataStoreSaveResult@wil@@@1@@Z; std::vector<wil::ProfileDataStoreSaveResult>::vector<wil::ProfileDataStoreSaveResult>(std::initializer_list<wil::ProfileDataStoreSaveResult>,std::allocator<wil::ProfileDataStoreSaveResult> const &)
0x18001fcdc  nop
0x18001fcdd  mov     rdx, r15
0x18001fce0  lea     rcx, [rsi-40h]
0x18001fce4  call    ?return_value@?$task_promise@V?$vector@VProfileDataStoreSaveResult@wil@@V?$allocator@VProfileDataStoreSaveResult@wil@@@std@@@std@@@coro@details@wil@@QEAAXAEBV?$vector@VProfileDataStoreSaveResult@wil@@V?$allocator@VProfileDataStoreSaveResult@wil@@@std@@@std@@@Z; wil::details::coro::task_promise<std::vector<wil::ProfileDataStoreSaveResult>>::return_value(std::vector<wil::ProfileDataStoreSaveResult> const &)
0x18001fce9  nop
0x18001fcea  mov     rcx, r15
0x18001fced  call    ?_Tidy@?$vector@VProfileDataStoreSaveResult@wil@@V?$allocator@VProfileDataStoreSaveResult@wil@@@std@@@std@@AEAAXXZ; std::vector<wil::ProfileDataStoreSaveResult>::_Tidy(void)
0x18001fcf2  nop
0x18001fcf3  lea     r9, ??1ProfileDataStoreSaveResult@wil@@QEAA@XZ; void (*)(void *)
0x18001fcfa  mov     edx, 38h ; '8'; unsigned __int64
0x18001fcff  lea     r8d, [rdx-37h]; unsigned __int64
0x18001fd03  mov     rcx, r12; void *
0x18001fd06  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18001fd0b  nop
0x18001fd0c  mov     rcx, rdi
0x18001fd0f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001fd14  nop
0x18001fd15  mov     [rsp+418h+var_368], rbx
0x18001fd1d  test    rbx, rbx
0x18001fd20  jz      short loc_18001FD6A
0x18001fd22  mov     rbx, [rsi+18h]
0x18001fd26  mov     [rsp+418h+var_368], rbx
0x18001fd2e  or      r15d, 0FFFFFFFFh
0x18001fd32  mov     eax, r15d
0x18001fd35  lock xadd [rbx+8], eax
0x18001fd3a  add     eax, r15d
0x18001fd3d  jnz     short loc_18001FD6A
0x18001fd3f  mov     rax, [rbx]
0x18001fd42  mov     rcx, rbx
0x18001fd45  mov     rax, [rax]
0x18001fd48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fd4d  mov     eax, r15d
0x18001fd50  lock xadd [rbx+0Ch], eax
0x18001fd55  add     eax, r15d
0x18001fd58  jnz     short loc_18001FD6A
0x18001fd5a  mov     rax, [rbx]
0x18001fd5d  mov     rcx, rbx
0x18001fd60  mov     rax, [rax+8]
0x18001fd64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fd69  nop
0x18001fd6a  jmp     loc_180020C10
0x18001fd6f  mov     rax, [rsi+4D8h]
0x18001fd76  cmp     [rsi+4D0h], rax
0x18001fd7d  jz      loc_180020B80
0x18001fd83  mov     [rsi+0B0h], r14b
0x18001fd8a  lea     rbx, [rsi+0B8h]
0x18001fd91  mov     [rbx], r14
0x18001fd94  mov     [rsi+0C0h], r14
0x18001fd9b  mov     [rsi+0C8h], r14
0x18001fda2  lea     rcx, [rsi+0D0h]
0x18001fda9  mov     rdx, rbx
0x18001fdac  call    ??$single_threaded_vector@UCloudStoreBatchSaveItemData@Cloud@Storage@Internal@Windows@winrt@@V?$allocator@UCloudStoreBatchSaveItemData@Cloud@Storage@Internal@Windows@winrt@@@std@@@winrt@@YA?AU?$IVector@UCloudStoreBatchSaveItemData@Cloud@Storage@Internal@Windows@winrt@@@Collections@Foundation@Windows@0@$$QEAV?$vector@UCloudStoreBatchSaveItemData@Cloud@Storage@Internal@Windows@winrt@@V?$allocator@UCloudStoreBatchSaveItemData@Cloud@Storage@Internal@Windows@winrt@@@std@@@std@@@Z; winrt::single_threaded_vector<winrt::Windows::Internal::Storage::Cloud::CloudStoreBatchSaveItemData,std::allocator<winrt::Windows::Internal::Storage::Cloud::CloudStoreBatchSaveItemData>>(std::vector<winrt::Windows::Internal::Storage::Cloud::CloudStoreBatchSaveItemData> &&)
0x18001fdb1  nop
0x18001fdb2  mov     rcx, rbx
0x18001fdb5  call    ??1?$vector@UCloudStoreBatchSaveItemData@Cloud@Storage@Internal@Windows@winrt@@V?$allocator@UCloudStoreBatchSaveItemData@Cloud@Storage@Internal@Windows@winrt@@@std@@@std@@QEAA@XZ; std::vector<winrt::Windows::Internal::Storage::Cloud::CloudStoreBatchSaveItemData>::~vector<winrt::Windows::Internal::Storage::Cloud::CloudStoreBatchSaveItemData>(void)
0x18001fdba  lea     rcx, [rsi+0D8h]
0x18001fdc1  call    ??$GetActivationFactoryPdr@UICloudStoreBatchSaveItemDataFactory@Cloud@Storage@Internal@Windows@@@details@wil@@YA?AV?$com_ptr_t@UICloudStoreBatchSaveItemDataFactory@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@1@PEBG@Z; wil::details::GetActivationFactoryPdr<Windows::Internal::Storage::Cloud::ICloudStoreBatchSaveItemDataFactory>(ushort const *)
0x18001fdc6  nop
0x18001fdc7  mov     r13, [rsi+4D0h]
0x18001fdce  mov     rax, [rsi+4D8h]
0x18001fdd5  mov     [rsp+418h+var_3B0], rax
0x18001fdda  or      r15d, 0FFFFFFFFh
0x18001fdde  cmp     r13, rax
0x18001fde1  jz      loc_180020421
0x18001fde7  mov     rbx, [r13+0]
0x18001fdeb  mov     al, [rsi+0B0h]
0x18001fdf1  mov     [rsp+418h+var_378], al
0x18001fdf8  lea     rdx, [rbx+58h]
0x18001fdfc  test    al, al
0x18001fdfe  jnz     loc_18001FED5
0x18001fe04  lea     rcx, [rsi+0F0h]
0x18001fe0b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001fe10  nop
0x18001fe11  lea     r12, [rsi+110h]
0x18001fe18  lea     rdx, [rbx+78h]
0x18001fe1c  mov     rcx, r12
0x18001fe1f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001fe24  nop
0x18001fe25  lea     rcx, [rsi+130h]
0x18001fe2c  lea     rdx, [rbx+98h]
0x18001fe33  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001fe38  nop
0x18001fe39  mov     ebx, [rsi+4B0h]
0x18001fe3f  mov     [rsp+418h+var_3C8], ebx
0x18001fe43  or      ebx, 10h
0x18001fe46  mov     [rsi+4B0h], ebx
0x18001fe4c  lea     rdi, [rsi+150h]
0x18001fe53  mov     rdx, r12
0x18001fe56  mov     rcx, rdi
0x18001fe59  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001fe5e  mov     [rsp+418h+var_3C8], ebx
0x18001fe62  or      ebx, 20h
0x18001fe65  mov     [rsi+4B0h], ebx
0x18001fe6b  mov     rax, [rsi+168h]
0x18001fe72  mov     [rsp+418h+var_288], rax
0x18001fe7a  cmp     rax, 7
0x18001fe7e  jbe     short loc_18001FE8D
0x18001fe80  mov     rax, [rdi]
0x18001fe83  mov     [rsp+418h+var_2A0], rax
0x18001fe8b  jmp     short loc_18001FE90
0x18001fe8d  mov     rax, rdi
0x18001fe90  lea     rdx, [rsi+0E0h]
0x18001fe97  mov     [rdx], rax
0x18001fe9a  lea     rcx, [rsi+0A8h]
0x18001fea1  call    ??$?4PEBG$0A@@?$optional@Uhstring@winrt@@@std@@QEAAAEAV01@$$QEAPEBG@Z; std::optional<winrt::hstring>::operator=<ushort const *,0>(ushort const * &&)
0x18001fea6  nop
0x18001fea7  mov     rcx, rdi
0x18001feaa  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001feaf  nop
0x18001feb0  lea     rcx, [rsi+130h]
0x18001feb7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001febc  mov     rcx, r12
0x18001febf  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001fec4  lea     rcx, [rsi+0F0h]
0x18001fecb  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001fed0  jmp     loc_180020008
0x18001fed5  lea     rcx, [rsi+170h]
0x18001fedc  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001fee1  nop
0x18001fee2  lea     r12, [rsi+190h]
0x18001fee9  lea     rdx, [rbx+78h]
0x18001feed  mov     rcx, r12
0x18001fef0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001fef5  nop
0x18001fef6  lea     rcx, [rsi+1B0h]
0x18001fefd  lea     rdx, [rbx+98h]
0x18001ff04  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001ff09  nop
0x18001ff0a  mov     ebx, [rsi+4B0h]
0x18001ff10  mov     [rsp+418h+var_3C8], ebx
0x18001ff14  or      ebx, 40h
0x18001ff17  mov     [rsi+4B0h], ebx
0x18001ff1d  lea     rdi, [rsi+1D0h]
0x18001ff24  mov     rdx, r12
0x18001ff27  mov     rcx, rdi
0x18001ff2a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001ff2f  mov     [rsp+418h+var_3C8], ebx
0x18001ff33  bts     ebx, 7
0x18001ff37  mov     [rsi+4B0h], ebx
0x18001ff3d  mov     rax, [rsi+1E8h]
0x18001ff44  mov     [rsp+418h+var_268], rax
0x18001ff4c  cmp     rax, 7
0x18001ff50  jbe     short loc_18001FF5F
0x18001ff52  mov     r8, [rdi]
0x18001ff55  mov     [rsp+418h+var_280], r8
0x18001ff5d  jmp     short loc_18001FF62
0x18001ff5f  mov     r8, rdi; lpString2
0x18001ff62  mov     rax, [rsi+0A8h]
0x18001ff69  mov     [rsp+418h+var_380], rax
0x18001ff71  test    rax, rax
0x18001ff74  jz      short loc_18001FF8B
0x18001ff76  mov     rax, [rsi+0A8h]
0x18001ff7d  mov     [rsp+418h+var_380], rax
0x18001ff85  mov     rcx, [rax+10h]
0x18001ff89  jmp     short loc_18001FF92
0x18001ff8b  lea     rcx, String1; lpString1
0x18001ff92  mov     [rsp+418h+bIgnoreCase], 1; bIgnoreCase
0x18001ff9a  mov     r9d, r15d; cchCount2
0x18001ff9d  mov     edx, r15d; cchCount1
0x18001ffa0  call    cs:__imp_CompareStringOrdinal
0x18001ffa6  mov     ebx, eax
0x18001ffa8  mov     rcx, rdi
0x18001ffab  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001ffb0  nop
0x18001ffb1  lea     rcx, [rsi+1B0h]
0x18001ffb8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001ffbd  mov     rcx, r12
0x18001ffc0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001ffc5  lea     rcx, [rsi+170h]
0x18001ffcc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001ffd1  cmp     ebx, 2
0x18001ffd4  jz      short loc_180020008
0x18001ffd6  mov     ecx, 80070057h
0x18001ffdb  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18001ffe0  mov     r9d, eax; char *
0x18001ffe3  mov     rcx, [rsp+418h]; this
0x18001ffeb  lea     rax, aAllPayloadsMus; "All payloads must be for the same colle"...
0x18001fff2  mov     qword ptr [rsp+418h+bIgnoreCase], rax; int
0x18001fff7  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\sdk\\inc\\wil\\pr"...
0x18001fffe  mov     edx, 771h; void *
0x180020003  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x180020008  lea     rbx, [rsi+1F0h]
0x18002000f  mov     rdx, [r13+0]
0x180020013  mov     rcx, rbx
0x180020016  call    ??$Marshal@V?$ProfileDataItem@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@wil@@@ProfileDataStore@wil@@CA?AUIBuffer@Streams@Storage@Windows@winrt@@AEBV?$ProfileDataItem@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@1@@Z; wil::ProfileDataStore::Marshal<wil::ProfileDataItem<Windows::Data::Security::Passkey::PasskeyItemPdr>>(wil::ProfileDataItem<Windows::Data::Security::Passkey::PasskeyItemPdr> const &)
0x18002001b  nop
0x18002001c  mov     rax, [rbx]
0x18002001f  mov     [rsp+418h+var_390], rax
0x180020027  mov     [rsi+1F8h], rax
0x18002002e  mov     rax, [rbx]
0x180020031  mov     [rsp+418h+var_390], rax
0x180020039  test    rax, rax
0x18002003c  jz      short loc_180020055
0x18002003e  mov     rcx, [rbx]
0x180020041  mov     [rsp+418h+var_390], rcx
0x180020049  mov     rax, [rcx]
0x18002004c  mov     rax, [rax+8]
0x180020050  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020055  mov     rax, [r13+0]
0x180020059  mov     rcx, [rax+40h]
0x18002005d  mov     [rsp+418h+var_388], rcx
0x180020065  mov     [rsi+200h], rcx
0x18002006c  test    rcx, rcx
0x18002006f  jz      short loc_18002007E
0x180020071  mov     rax, [rcx]
0x180020074  mov     rax, [rax+8]
0x180020078  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002007d  nop
0x18002007e  lea     r12, [rsi+208h]
0x180020085  mov     rdx, [r13+0]
0x180020089  add     rdx, 58h ; 'X'
0x18002008d  mov     rcx, r12
0x180020090  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180020095  mov     ebx, [rsi+4B0h]
0x18002009b  mov     [rsp+418h+var_3C8], ebx
0x18002009f  or      ebx, 300h
  ... truncated ...
```
