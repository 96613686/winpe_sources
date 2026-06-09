# wil::ProfileDataStore::CallLoadAsync$_ResumeCoro$1_Windows::Data::Security::Passkey::PasskeyItemPdr_

- ea: `0x18002a190`
- end: `0x18002a9dc`
- name: `wil::ProfileDataStore::CallLoadAsync$_ResumeCoro$1_Windows::Data::Security::Passkey::PasskeyItemPdr_`
- size: `2124`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18003a16c`

## callees

- `0x180003080`
- `0x180003520`
- `0x180007a5c`
- `0x18000ce74`
- `0x18000cfcc`
- `0x18000f7fc`
- `0x18001354c`
- `0x18001361c`
- `0x18002a190`
- `0x1800378f4`
- `0x18003f6bc`
- `0x18004280c`
- `0x180043674`
- `0x18004562c`
- `0x180045914`
- `0x180045e14`
- `0x180049238`
- `0x18004aae8`
- `0x18004d8f0`
- `0x18004eaac`
- `0x18004edec`
- `0x180061010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002a556`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002a5d7`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002a660`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002a556`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002a5d7`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002a660`

## pseudocode

```c
// Hidden C++ exception states: #wind=22 #try_helpers=1
void __fastcall wil::ProfileDataStore::CallLoadAsync__ResumeCoro_1_Windows::Data::Security::Passkey::PasskeyItemPdr_(
        __int64 a1)
{
  __int64 v1; // rsi
  __int64 v2; // r15
  _QWORD *v3; // r8
  __int64 v4; // rdx
  signed __int32 v5; // eax
  signed __int32 v6; // ett
  __int64 v7; // r13
  __int64 v8; // rax
  __int64 v9; // r12
  __int64 v10; // rdi
  _QWORD *v11; // rax
  volatile signed __int32 *v12; // rdi
  __int64 v13; // rdx
  __int64 v14; // r8
  volatile signed __int32 *v15; // rdi
  _QWORD *v16; // r12
  const char *v17; // r9
  int v18; // r8d
  int v19; // edx
  int v20; // ecx
  int v21; // edx
  int v22; // eax
  _QWORD *v23; // rax
  _QWORD *v24; // rcx
  __int64 v25; // rdx
  __int64 v26; // rax
  __int64 v27; // rdx
  __int64 v28; // rcx
  __int64 v29; // rax
  __int64 v30; // rdx
  __int64 v31; // rcx
  __int64 v32; // rax
  __int64 v33; // r8
  __int64 Async; // r8
  __int64 v35; // rdx
  __int64 v36; // r8
  __int64 v37; // rdx
  __int64 v38; // r8
  __int64 v39; // rdx
  __int64 v40; // r8
  _QWORD *v41; // rax
  __int64 (__fastcall ***v42)(_QWORD, __int64 *, _QWORD **); // rdx
  _QWORD *v43; // rax
  volatile signed __int32 *v44; // rdi
  volatile signed __int32 *v45; // rdi
  _QWORD *v46; // rax
  volatile signed __int32 *v47; // rbx
  __int64 v48; // rdx
  __int64 v49; // r8
  int CloudStore; // [rsp+70h] [rbp-168h]
  _QWORD *v52; // [rsp+A0h] [rbp-138h]
  volatile signed __int32 **v53; // [rsp+B0h] [rbp-128h]
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+0h]

  v1 = a1;
  v2 = a1 + 8;
  if ( (unsigned __int16)(*(_WORD *)(a1 + 8) + 1) > 4u )
  {
LABEL_84:
    __debugbreak();
  }
  else
  {
    switch ( *(_WORD *)(a1 + 8) )
    {
      case 0xFFFF:
      case 1:
      case 3:
        wil::details::coro::result_holder<std::shared_ptr<wil::ProfileDataItem<Windows::Data::Security::Passkey::RecoveryItemPdr>>>::~result_holder<std::shared_ptr<wil::ProfileDataItem<Windows::Data::Security::Passkey::RecoveryItemPdr>>>(a1 - 32);
        `wil::ProfileDataStore::CallLoadAsync<Windows::Data::Security::Passkey::ScenarioKeysItemPdr>'::`8'::_parameters_::~_parameters_(v2 + 704);
        if ( *(_WORD *)(v1 + 10) )
          operator delete((void *)(v1 - 48), 0x330u);
        return;
      case 0:
        goto LABEL_84;
      case 2:
        v3 = *(_QWORD **)(a1 + 712);
        *(_QWORD *)(a1 + 16) = 0;
        *(_QWORD *)(a1 + 24) = 0;
        v4 = v3[1];
        if ( !v4 )
          goto LABEL_80;
        v5 = *(_DWORD *)(v4 + 8);
        do
        {
          if ( !v5 )
LABEL_80:
            std::_Throw_bad_weak_ptr();
          v6 = v5;
          v5 = _InterlockedCompareExchange((volatile signed __int32 *)(v4 + 8), v5 + 1, v5);
        }
        while ( v6 != v5 );
        v53 = (volatile signed __int32 **)(a1 + 24);
        *(_QWORD *)(a1 + 16) = *v3;
        v7 = v3[1];
        *(_QWORD *)(a1 + 24) = v7;
        v8 = *(_QWORD *)(a1 + 752);
        if ( v8 && *(_DWORD *)(v8 + 16) )
        {
          *(_DWORD *)(a1 + 32) = 0;
          *(_DWORD *)(a1 + 36) = -2147023673;
          *(_OWORD *)(a1 + 40) = 0;
          *(_QWORD *)(a1 + 56) = 0;
          *(_QWORD *)(a1 + 64) = 7;
          *(_WORD *)(a1 + 40) = 0;
          *(_BYTE *)(a1 + 72) = 0;
          *(_BYTE *)(a1 + 73) = 0;
          *(_BYTE *)(a1 + 74) = 1;
          v9 = a1 + 80;
          *(_QWORD *)(a1 + 80) = 0;
          *(_DWORD *)(a1 + 88) = 1;
          *(_DWORD *)(a1 + 92) = 0;
          *(_DWORD *)(a1 + 96) = 0;
          *(_OWORD *)(a1 + 104) = 0;
          *(_OWORD *)(a1 + 120) = 0;
          *(_OWORD *)(a1 + 136) = 0;
          *(_QWORD *)(a1 + 120) = 0;
          *(_QWORD *)(a1 + 128) = 15;
          *(_BYTE *)(a1 + 104) = 0;
          *(_QWORD *)(a1 + 136) = 0;
          *(_QWORD *)(a1 + 144) = 0;
          *(_QWORD *)(a1 + 152) = 0;
          v10 = a1 + 40;
          v11 = (_QWORD *)std::make_shared<wil::ProfileDataItem<Windows::Data::Security::Passkey::PasskeyItemPdr>,Windows::Data::Security::Passkey::PasskeyItemPdr,wil::ProfileDataItemReference<Windows::Data::Security::Passkey::PasskeyItemPdr> &,int,enum wil::ProfileDataItemStatus,enum wil::DataDescriptionLanguage,wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudStoreData,wil::err_exception_policy>,bool,bool,bool,std::wstring,long,int>(
                            (int)a1 + 160,
                            (int)a1 + 104,
                            *(_QWORD *)(a1 + 720),
                            (int)a1 + 96,
                            a1 + 92,
                            a1 + 88,
                            a1 + 80,
                            a1 + 74,
                            a1 + 73,
                            a1 + 72,
                            a1 + 40,
                            a1 + 36,
                            a1 + 32);
          *(_QWORD *)(v1 - 24) = 0;
          *(_QWORD *)(v1 - 16) = 0;
          *(_QWORD *)(v1 - 24) = *v11;
          *(_QWORD *)(v1 - 16) = v11[1];
          *v11 = 0;
          v11[1] = 0;
          *(_DWORD *)(v1 - 32) = 1;
          if ( *(_QWORD *)(v1 + 168) )
          {
            v12 = *(volatile signed __int32 **)(v1 + 168);
            if ( _InterlockedExchangeAdd(v12 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
              if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
            }
            v10 = v1 + 40;
          }
          std::vector<unsigned char>::~vector<unsigned char>(v1 + 136);
          std::string::~string(v1 + 104);
          if ( *(_QWORD *)v9 )
            (*(void (**)(void))(**(_QWORD **)v9 + 16LL))();
          std::wstring::~wstring(v10, v13, v14);
          if ( v7 )
          {
            v15 = *(volatile signed __int32 **)(v1 + 24);
            if ( _InterlockedExchangeAdd(v15 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
              if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
LABEL_20:
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
            }
          }
        }
        else
        {
          try
          {
            v16 = (_QWORD *)(a1 + 176);
            v52 = (_QWORD *)(a1 + 176);
            *(_QWORD *)(a1 + 176) = 0;
            CloudStore = wil::details::SharedCloudStoreState::GetCloudStore(v3[2], a1 + 208);
            *(_QWORD *)(v1 + 216) = *(_QWORD *)(v1 + 760);
            *(_QWORD *)(v1 + 248) = *(_QWORD *)(v1 + 744);
            v18 = *(_DWORD *)(v1 + 736);
            v19 = v18 & 1;
            if ( (v18 & 4) != 0 )
            {
              if ( (v18 & 1) == 0 )
                wil::details::in1diag3::_FailFast_Unexpected(
                  retaddr,
                  (void *)0x8FE,
                  (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil\\profiledatastore.h",
                  v17);
              v19 |= 2u;
            }
            v20 = v19 | 4;
            if ( (v18 & 8) == 0 )
              v20 = v19;
            v21 = v20 | 8;
            if ( (v18 & 0x10) == 0 )
              v21 = v20;
            v22 = v21 | 0x10;
            if ( (v18 & 0x20) == 0 )
              v22 = v21;
            *(_DWORD *)(v1 + 280) = v22;
            v23 = (_QWORD *)wil::ProfileDataStore::GetTypeNameWideString<Windows::Data::Security::Passkey::PasskeyItemPdr>(v1 + 320);
            v24 = v23;
            v25 = v23[2];
            if ( v23[3] > 7u )
              v24 = (_QWORD *)*v23;
            if ( (_DWORD)v25 )
            {
              if ( *((_WORD *)v24 + (unsigned int)v25) )
                abort();
              v26 = v1 + 296;
              *(_DWORD *)(v1 + 296) = 1;
              *(_DWORD *)(v1 + 300) = v25;
              *(_QWORD *)(v1 + 312) = v24;
            }
            else
            {
              v26 = 0;
            }
            *(_QWORD *)(v1 + 288) = v26;
            std::wstring::wstring(v1 + 384, *(_QWORD *)(v1 + 720));
            v27 = *(_QWORD *)(v1 + 400);
            if ( *(_QWORD *)(v1 + 408) <= 7u )
              v28 = v1 + 384;
            else
              v28 = *(_QWORD *)(v1 + 384);
            if ( (_DWORD)v27 )
            {
              if ( *(_WORD *)(v28 + 2LL * (unsigned int)v27) )
                abort();
              v29 = v1 + 360;
              *(_DWORD *)(v1 + 360) = 1;
              *(_DWORD *)(v1 + 364) = v27;
              *(_QWORD *)(v1 + 376) = v28;
            }
            else
            {
              v29 = 0;
            }
            *(_QWORD *)(v1 + 352) = v29;
            std::wstring::wstring(v1 + 448, *(_QWORD *)(v1 + 720) + 32LL);
            v30 = *(_QWORD *)(v1 + 464);
            if ( *(_QWORD *)(v1 + 472) <= 7u )
              v31 = v1 + 448;
            else
              v31 = *(_QWORD *)(v1 + 448);
            if ( (_DWORD)v30 )
            {
              if ( *(_WORD *)(v31 + 2LL * (unsigned int)v30) )
                abort();
              v32 = v1 + 424;
              *(_DWORD *)(v1 + 424) = 1;
              *(_DWORD *)(v1 + 428) = v30;
              *(_QWORD *)(v1 + 440) = v31;
            }
            else
            {
              v32 = 0;
            }
            *(_QWORD *)(v1 + 416) = v32;
            v33 = *(_QWORD *)(v2 + 704);
            *(_QWORD *)(v1 + 480) = *(_QWORD *)(v33 + 40);
            Async = winrt::impl::consume_Windows_Internal_Storage_Cloud_ICloudStore2<winrt::Windows::Internal::Storage::Cloud::CloudStore>::LoadAsync(
                      CloudStore,
                      (int)v1 + 512,
                      (int)v33 + 32,
                      (int)v1 + 480,
                      v1 + 416,
                      v1 + 352,
                      v1 + 288,
                      v1 + 280,
                      v1 + 248,
                      v1 + 216);
            wil::details::AsyncOpWaiter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::CloudStoreData>,winrt::Windows::Internal::Storage::Cloud::CloudStoreData>::AsyncOpWaiter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::CloudStoreData>,winrt::Windows::Internal::Storage::Cloud::CloudStoreData>(
              v1 + 184,
              v1 + 752,
              Async);
            if ( *(_QWORD *)(v1 + 512) )
              winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v1 + 512);
            std::wstring::~wstring(v1 + 448, v35, v36);
            std::wstring::~wstring(v1 + 384, v37, v38);
            std::wstring::~wstring(v1 + 320, v39, v40);
            if ( *(_QWORD *)(v1 + 208) )
              winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v1 + 208);
            v41 = (_QWORD *)wil::details::AsyncOpWaiter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::CloudStoreData>,winrt::Windows::Internal::Storage::Cloud::CloudStoreData>::WaitForResult(
                              v1 + 184,
                              v1 + 520);
            if ( v16 != v41 )
            {
              v42 = (__int64 (__fastcall ***)(_QWORD, __int64 *, _QWORD **))*v41;
              *v41 = 0;
              *v16 = v42;
            }
            if ( *(_QWORD *)(v1 + 520) )
              winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v1 + 520);
            wil::details::AsyncOpWaiter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>,winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>::~AsyncOpWaiter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>,winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>(v1 + 184);
          }
          catch ( Concurrency::task_canceled )
          {
            *(_DWORD *)(a1 + 528) = 0;
            *(_DWORD *)(a1 + 532) = -2147023673;
            *(_OWORD *)(a1 + 536) = 0;
            *(_QWORD *)(a1 + 552) = 0;
            *(_QWORD *)(a1 + 560) = 7;
            *(_WORD *)(a1 + 536) = 0;
            *(_WORD *)(a1 + 568) = 0;
            *(_BYTE *)(a1 + 570) = 1;
            *(_QWORD *)(a1 + 576) = 0;
            *(_QWORD *)(a1 + 584) = 1;
            *(_DWORD *)(a1 + 592) = 0;
            *(_OWORD *)(a1 + 616) = 0;
            *(_OWORD *)(a1 + 632) = 0;
            *(_OWORD *)(a1 + 600) = 0;
            *(_QWORD *)(a1 + 616) = 0;
            *(_QWORD *)(a1 + 624) = 15;
            *(_BYTE *)(a1 + 600) = 0;
            *(_QWORD *)(a1 + 632) = 0;
            *(_QWORD *)(a1 + 640) = 0;
            *(_QWORD *)(a1 + 648) = 0;
            v46 = (_QWORD *)std::make_shared<wil::ProfileDataItem<Windows::Data::Security::Passkey::PasskeyItemPdr>,Windows::Data::Security::Passkey::PasskeyItemPdr,wil::ProfileDataItemReference<Windows::Data::Security::Passkey::PasskeyItemPdr> &,int,enum wil::ProfileDataItemStatus,enum wil::DataDescriptionLanguage,wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudStoreData,wil::err_exception_policy>,bool,bool,bool,std::wstring,long,int>(
                              (int)a1 + 656,
                              (int)a1 + 600,
                              *(_QWORD *)(a1 + 720),
                              (int)a1 + 592,
                              a1 + 588,
                              a1 + 584,
                              a1 + 576,
                              a1 + 570,
                              a1 + 569,
                              a1 + 568,
                              a1 + 536,
                              a1 + 532,
                              a1 + 528);
            *(_QWORD *)(a1 - 24) = 0;
            *(_QWORD *)(a1 - 16) = 0;
            *(_QWORD *)(a1 - 24) = *v46;
            *(_QWORD *)(a1 - 16) = v46[1];
            *v46 = 0;
            v46[1] = 0;
            *(_DWORD *)(a1 - 32) = 1;
            if ( *(_QWORD *)(a1 + 664) )
            {
              v47 = *(volatile signed __int32 **)(a1 + 664);
              if ( _InterlockedExchangeAdd(v47 + 2, 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v47)(v47);
                if ( _InterlockedExchangeAdd(v47 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v47 + 8LL))(v47);
              }
            }
            std::vector<unsigned char>::~vector<unsigned char>(a1 + 632);
            std::string::~string(a1 + 600);
            if ( *(_QWORD *)(a1 + 576) )
              (*(void (**)(void))(**(_QWORD **)(a1 + 576) + 16LL))();
            std::wstring::~wstring(a1 + 536, v48, v49);
            if ( *v52 )
              winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v52);
            if ( *v53 )
            {
              v45 = *v53;
              if ( _InterlockedExchangeAdd(*v53 + 2, 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v45)(v45);
                if ( _InterlockedExchangeAdd(v45 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v45 + 8LL))(v45);
              }
            }
            v1 = a1;
            goto LABEL_81;
          }
          v43 = wil::ProfileDataStore::Unmarshal<Windows::Data::Security::Passkey::PasskeyItemPdr>(
                  (_QWORD *)(v1 + 672),
                  (__int64 (__fastcall ****)(_QWORD, __int64 *, _QWORD **))v16,
                  *(_DWORD *)(v1 + 736));
          *(_QWORD *)(v1 - 24) = 0;
          *(_QWORD *)(v1 - 16) = 0;
          *(_QWORD *)(v1 - 24) = *v43;
          *(_QWORD *)(v1 - 16) = v43[1];
          *v43 = 0;
          v43[1] = 0;
          *(_DWORD *)(v1 - 32) = 1;
          if ( *(_QWORD *)(v1 + 680) )
          {
            v44 = *(volatile signed __int32 **)(v1 + 680);
            if ( _InterlockedExchangeAdd(v44 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v44)(v44);
              if ( _InterlockedExchangeAdd(v44 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v44 + 8LL))(v44);
            }
          }
          if ( *v16 )
            winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v16);
          if ( *(_QWORD *)(v1 + 24) )
          {
            v15 = *(volatile signed __int32 **)(v1 + 24);
            if ( _InterlockedExchangeAdd(v15 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
              if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
                goto LABEL_20;
            }
          }
        }
LABEL_81:
        *(_QWORD *)(v1 + 688) = v1 - 48;
        *(_WORD *)v2 = 0;
        `wil::details::coro::promise_base<std::shared_ptr<wil::ProfileDataItem<Windows::Data::Security::Passkey::RecoveryItemPdr>>>::final_suspend'::`2'::awaiter::await_suspend();
        break;
    }
  }
}

```

## disassembly

```asm
0x18002a190  mov     r11, rsp
0x18002a193  mov     [r11+10h], rbx
0x18002a197  mov     [r11+18h], rsi
0x18002a19b  mov     [r11+8], rcx
0x18002a19f  push    rdi
0x18002a1a0  push    r12
0x18002a1a2  push    r13
0x18002a1a4  push    r14
0x18002a1a6  push    r15
0x18002a1a8  sub     rsp, 1B0h
0x18002a1af  mov     rax, cs:__security_cookie
0x18002a1b6  xor     rax, rsp
0x18002a1b9  mov     [rsp+1D8h+var_38], rax
0x18002a1c1  mov     rsi, rcx
0x18002a1c4  mov     [rsp+1D8h+var_160], rcx
0x18002a1c9  lea     r15, [rsi+8]
0x18002a1cd  movzx   eax, word ptr [r15]
0x18002a1d1  mov     [rsp+1D8h+var_158], ax
0x18002a1d9  mov     ebx, 1
0x18002a1de  add     ax, bx
0x18002a1e1  lea     ecx, [rbx+3]
0x18002a1e4  cmp     ax, cx
0x18002a1e7  ja      loc_18002A996; jumptable 000000018002A20A case 1
0x18002a1ed  mov     [rsp+1D8h+var_150], r15
0x18002a1f5  movsx   rax, ax
0x18002a1f9  lea     rdx, __ImageBase
0x18002a200  mov     ecx, ds:(jpt_18002A20A - 180000000h)[rdx+rax*4]; switch 5 cases
0x18002a207  add     rcx, rdx
0x18002a20a  jmp     rcx; switch jump
0x18002a20c  jmp     loc_18002A967; jumptable 000000018002A20A case 4
0x18002a211  xor     r14d, r14d; jumptable 000000018002A20A case 3
0x18002a214  mov     r8, [r15+2C0h]
0x18002a21b  mov     [rsi+10h], r14
0x18002a21f  lea     r9, [rsi+18h]
0x18002a223  mov     [r9], r14
0x18002a226  mov     rdx, [r8+8]
0x18002a22a  test    rdx, rdx
0x18002a22d  jz      loc_18002A939
0x18002a233  mov     eax, [rdx+8]
0x18002a236  jmp     short loc_18002A242
0x18002a238  lea     ecx, [rax+1]
0x18002a23b  lock cmpxchg [rdx+8], ecx
0x18002a240  jz      short loc_18002A24B
0x18002a242  test    eax, eax
0x18002a244  jnz     short loc_18002A238
0x18002a246  jmp     loc_18002A939
0x18002a24b  mov     [rsp+1D8h+var_128], r9
0x18002a253  mov     rax, [r8]
0x18002a256  mov     [rsi+10h], rax
0x18002a25a  mov     r13, [r8+8]
0x18002a25e  mov     [r9], r13
0x18002a261  mov     rax, [rsi+2F0h]
0x18002a268  test    rax, rax
0x18002a26b  jz      loc_18002A47D
0x18002a271  mov     eax, [rax+10h]
0x18002a274  nop
0x18002a275  test    eax, eax
0x18002a277  jz      loc_18002A47D
0x18002a27d  mov     [rsi+20h], r14d
0x18002a281  lea     rbx, [rsi+24h]
0x18002a285  mov     dword ptr [rbx], 800704C7h
0x18002a28b  xorps   xmm0, xmm0
0x18002a28e  movups  xmmword ptr [rsi+28h], xmm0
0x18002a292  mov     [rsi+38h], r14
0x18002a296  mov     qword ptr [rsi+40h], 7
0x18002a29e  xor     ecx, ecx
0x18002a2a0  mov     [rsi+28h], cx
0x18002a2a4  lea     r11, [rsi+48h]
0x18002a2a8  mov     [r11], r14b
0x18002a2ab  lea     r10, [rsi+49h]
0x18002a2af  mov     [r10], r14b
0x18002a2b2  lea     r8, [rsi+4Ah]
0x18002a2b6  mov     byte ptr [r8], 1
0x18002a2ba  lea     r12, [rsi+50h]
0x18002a2be  mov     [r12], r14
0x18002a2c2  lea     rdx, [rsi+58h]
0x18002a2c6  mov     dword ptr [rdx], 1
0x18002a2cc  lea     rax, [rsi+5Ch]
0x18002a2d0  mov     [rax], r14d
0x18002a2d3  lea     r9, [rsi+60h]
0x18002a2d7  mov     [r9], r14d
0x18002a2da  movups  xmmword ptr [rsi+68h], xmm0
0x18002a2de  movups  xmmword ptr [rsi+78h], xmm0
0x18002a2e2  movups  xmmword ptr [rsi+88h], xmm0
0x18002a2e9  mov     [rsi+78h], r14
0x18002a2ed  mov     qword ptr [rsi+80h], 0Fh
0x18002a2f8  mov     [rsi+68h], r14b
0x18002a2fc  mov     [rsi+88h], r14
0x18002a303  mov     [rsi+90h], r14
0x18002a30a  mov     [rsi+98h], r14
0x18002a311  lea     rcx, [rsi+0A0h]
0x18002a318  lea     rdi, [rsi+20h]
0x18002a31c  mov     [rsp+1D8h+var_178], rdi
0x18002a321  mov     [rsp+1D8h+var_180], rbx
0x18002a326  lea     rdi, [rsi+28h]
0x18002a32a  mov     [rsp+1D8h+var_188], rdi
0x18002a32f  mov     [rsp+1D8h+var_190], r11
0x18002a334  mov     [rsp+1D8h+var_198], r10
0x18002a339  mov     [rsp+1D8h+var_1A0], r8
0x18002a33e  mov     [rsp+1D8h+var_1A8], r12
0x18002a343  mov     [rsp+1D8h+var_1B0], rdx
0x18002a348  mov     [rsp+1D8h+var_1B8], rax
0x18002a34d  mov     r8, [rsi+2D0h]
0x18002a354  lea     rdx, [rsi+68h]
0x18002a358  call    ??$make_shared@V?$ProfileDataItem@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@wil@@UPasskeyItemPdr@Passkey@Security@Data@Windows@@AEAV?$ProfileDataItemReference@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@2@HW4ProfileDataItemStatus@2@W4DataDescriptionLanguage@2@V?$com_ptr_t@UICloudStoreData@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@2@_N_N_NV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@JH@std@@YA?AV?$shared_ptr@V?$ProfileDataItem@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@wil@@@0@$$QEAUPasskeyItemPdr@Passkey@Security@Data@Windows@@AEAV?$ProfileDataItemReference@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@wil@@$$QEAH$$QEAW4ProfileDataItemStatus@8@$$QEAW4DataDescriptionLanguage@8@$$QEAV?$com_ptr_t@UICloudStoreData@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@8@$$QEA_N66$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAJ2@Z; std::make_shared<wil::ProfileDataItem<Windows::Data::Security::Passkey::PasskeyItemPdr>,Windows::Data::Security::Passkey::PasskeyItemPdr,wil::ProfileDataItemReference<Windows::Data::Security::Passkey::PasskeyItemPdr> &,int,wil::ProfileDataItemStatus,wil::DataDescriptionLanguage,wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudStoreData,wil::err_exception_policy>,bool,bool,bool,std::wstring,long,int>(Windows::Data::Security::Passkey::PasskeyItemPdr &&,wil::ProfileDataItemReference<Windows::Data::Security::Passkey::PasskeyItemPdr> &,int &&,wil::ProfileDataItemStatus &&,wil::DataDescriptionLanguage &&,wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudStoreData,wil::err_exception_policy> &&,bool &&,bool &&,bool &&,std::wstring &&,long &&,int &&)
0x18002a35d  mov     [rsi-18h], r14
0x18002a361  mov     [rsi-10h], r14
0x18002a365  mov     rcx, [rax]
0x18002a368  mov     [rsi-18h], rcx
0x18002a36c  mov     rcx, [rax+8]
0x18002a370  mov     [rsi-10h], rcx
0x18002a374  mov     [rax], r14
0x18002a377  mov     [rax+8], r14
0x18002a37b  mov     dword ptr [rsi-20h], 1
0x18002a382  mov     rax, [rsi+0A8h]
0x18002a389  mov     [rsp+1D8h+var_110], rax
0x18002a391  or      ebx, 0FFFFFFFFh
0x18002a394  test    rax, rax
0x18002a397  jz      short loc_18002A3DF
0x18002a399  mov     rdi, [rsi+0A8h]
0x18002a3a0  mov     [rsp+1D8h+var_110], rdi
0x18002a3a8  mov     eax, ebx
0x18002a3aa  lock xadd [rdi+8], eax
0x18002a3af  add     eax, ebx
0x18002a3b1  jnz     short loc_18002A3DB
0x18002a3b3  mov     rax, [rdi]
0x18002a3b6  mov     rcx, rdi
0x18002a3b9  mov     rax, [rax]
0x18002a3bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a3c1  mov     eax, ebx
0x18002a3c3  lock xadd [rdi+0Ch], eax
0x18002a3c8  add     eax, ebx
0x18002a3ca  jnz     short loc_18002A3DB
0x18002a3cc  mov     rax, [rdi]
0x18002a3cf  mov     rcx, rdi
0x18002a3d2  mov     rax, [rax+8]
0x18002a3d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a3db  lea     rdi, [rsi+28h]
0x18002a3df  lea     rcx, [rsi+88h]
0x18002a3e6  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x18002a3eb  lea     rcx, [rsi+68h]
0x18002a3ef  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18002a3f4  nop
0x18002a3f5  mov     rax, [r12]
0x18002a3f9  mov     [rsp+1D8h+var_168], rax
0x18002a3fe  test    rax, rax
0x18002a401  jz      short loc_18002A422
0x18002a403  mov     rax, [r12]
0x18002a407  mov     [rsp+1D8h+var_168], rax
0x18002a40c  mov     rcx, [rax]
0x18002a40f  mov     rax, [rcx+10h]
0x18002a413  mov     rcx, [r12]
0x18002a417  mov     [rsp+1D8h+var_168], rcx
0x18002a41c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a421  nop
0x18002a422  mov     rcx, rdi
0x18002a425  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002a42a  nop
0x18002a42b  mov     [rsp+1D8h+var_140], r13
0x18002a433  test    r13, r13
0x18002a436  jz      short loc_18002A478
0x18002a438  mov     rdi, [rsi+18h]
0x18002a43c  mov     [rsp+1D8h+var_140], rdi
0x18002a444  mov     eax, ebx
0x18002a446  lock xadd [rdi+8], eax
0x18002a44b  add     eax, ebx
0x18002a44d  jnz     short loc_18002A478
0x18002a44f  mov     rax, [rdi]
0x18002a452  mov     rcx, rdi
0x18002a455  mov     rax, [rax]
0x18002a458  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a45d  mov     eax, ebx
0x18002a45f  lock xadd [rdi+0Ch], eax
0x18002a464  add     eax, ebx
0x18002a466  jnz     short loc_18002A478
0x18002a468  mov     rax, [rdi]
0x18002a46b  mov     rcx, rdi
0x18002a46e  mov     rax, [rax+8]
0x18002a472  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a477  nop
0x18002a478  jmp     loc_18002A94C
0x18002a47d  lea     r12, [rsi+0B0h]
0x18002a484  mov     [rsp+1D8h+var_138], r12
0x18002a48c  mov     [r12], r14
0x18002a490  lea     rdx, [rsi+0D0h]
0x18002a497  mov     rcx, [r8+10h]
0x18002a49b  call    ?GetCloudStore@SharedCloudStoreState@details@wil@@QEAA?BUCloudStore@Cloud@Storage@Internal@Windows@winrt@@XZ; wil::details::SharedCloudStoreState::GetCloudStore(void)
0x18002a4a0  mov     [rsp+1D8h+var_168], rax
0x18002a4a5  lea     rdi, [rsi+0D8h]
0x18002a4ac  mov     rcx, [rsi+2F8h]
0x18002a4b3  mov     [rdi], rcx
0x18002a4b6  mov     rcx, [rsi+2E8h]
0x18002a4bd  mov     [rsi+0F8h], rcx
0x18002a4c4  mov     r8d, [rsi+2E0h]
0x18002a4cb  mov     edx, r8d
0x18002a4ce  and     edx, ebx
0x18002a4d0  bt      r8d, 2
0x18002a4d5  jnb     short loc_18002A4FA
0x18002a4d7  mov     rcx, [rsp+1D8h]; this
0x18002a4df  mov     al, dl
0x18002a4e1  xor     al, bl
0x18002a4e3  jz      short loc_18002A4F7
0x18002a4e5  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\sdk\\inc\\wil\\pr"...
0x18002a4ec  mov     edx, 8FEh; void *
0x18002a4f1  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18002a4f7  or      edx, 2
0x18002a4fa  mov     ecx, edx
0x18002a4fc  or      ecx, 4
0x18002a4ff  bt      r8d, 3
0x18002a504  cmovnb  ecx, edx
0x18002a507  mov     edx, ecx
0x18002a509  or      edx, 8
0x18002a50c  bt      r8d, 4
0x18002a511  cmovnb  edx, ecx
0x18002a514  mov     eax, edx
0x18002a516  or      eax, 10h
0x18002a519  bt      r8d, 5
0x18002a51e  cmovnb  eax, edx
0x18002a521  mov     [rsi+118h], eax
0x18002a527  lea     rcx, [rsi+140h]
0x18002a52e  call    ??$GetTypeNameWideString@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@ProfileDataStore@wil@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; wil::ProfileDataStore::GetTypeNameWideString<Windows::Data::Security::Passkey::PasskeyItemPdr>(void)
0x18002a533  mov     rcx, rax
0x18002a536  mov     rdx, [rax+10h]
0x18002a53a  cmp     qword ptr [rax+18h], 7
0x18002a53f  jbe     short loc_18002A544
0x18002a541  mov     rcx, [rax]
0x18002a544  test    edx, edx
0x18002a546  jnz     short loc_18002A54D
0x18002a548  mov     rax, r14
0x18002a54b  jmp     short loc_18002A573
0x18002a54d  mov     eax, edx
0x18002a54f  cmp     [rcx+rax*2], r14w
0x18002a554  jz      short loc_18002A55D
0x18002a556  call    cs:__imp_abort
0x18002a55d  lea     rax, [rsi+128h]
0x18002a564  mov     [rax], ebx
0x18002a566  mov     [rsi+12Ch], edx
0x18002a56c  mov     [rsi+138h], rcx
0x18002a573  mov     [rsi+120h], rax
0x18002a57a  lea     rbx, [rsi+180h]
0x18002a581  mov     rdx, [rsi+2D0h]
0x18002a588  mov     rcx, rbx
0x18002a58b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002a590  nop
0x18002a591  mov     rdx, [rsi+190h]
0x18002a598  mov     [rsp+1D8h+var_D8], rdx
0x18002a5a0  mov     rax, [rsi+198h]
0x18002a5a7  mov     [rsp+1D8h+var_D0], rax
0x18002a5af  cmp     rax, 7
0x18002a5b3  jbe     short loc_18002A5C2
0x18002a5b5  mov     rcx, [rbx]
0x18002a5b8  mov     [rsp+1D8h+var_E8], rcx
0x18002a5c0  jmp     short loc_18002A5C5
0x18002a5c2  mov     rcx, rbx
0x18002a5c5  test    edx, edx
0x18002a5c7  jnz     short loc_18002A5CE
0x18002a5c9  mov     rax, r14
0x18002a5cc  jmp     short loc_18002A5F8
0x18002a5ce  mov     eax, edx
0x18002a5d0  cmp     [rcx+rax*2], r14w
0x18002a5d5  jz      short loc_18002A5DE
0x18002a5d7  call    cs:__imp_abort
0x18002a5de  lea     rax, [rsi+168h]
0x18002a5e5  mov     dword ptr [rax], 1
0x18002a5eb  mov     [rsi+16Ch], edx
0x18002a5f1  mov     [rsi+178h], rcx
0x18002a5f8  mov     [rsi+160h], rax
0x18002a5ff  lea     rbx, [rsi+1C0h]
0x18002a606  mov     rdx, [rsi+2D0h]
0x18002a60d  add     rdx, 20h ; ' '
0x18002a611  mov     rcx, rbx
0x18002a614  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002a619  nop
0x18002a61a  mov     rdx, [rsi+1D0h]
0x18002a621  mov     [rsp+1D8h+var_B8], rdx
0x18002a629  mov     rax, [rsi+1D8h]
0x18002a630  mov     [rsp+1D8h+var_B0], rax
0x18002a638  cmp     rax, 7
0x18002a63c  jbe     short loc_18002A64B
0x18002a63e  mov     rcx, [rbx]
0x18002a641  mov     [rsp+1D8h+var_C8], rcx
0x18002a649  jmp     short loc_18002A64E
0x18002a64b  mov     rcx, rbx
0x18002a64e  test    edx, edx
0x18002a650  jnz     short loc_18002A657
0x18002a652  mov     rax, r14
0x18002a655  jmp     short loc_18002A681
0x18002a657  mov     eax, edx
0x18002a659  cmp     [rcx+rax*2], r14w
0x18002a65e  jz      short loc_18002A667
0x18002a660  call    cs:__imp_abort
0x18002a667  lea     rax, [rsi+1A8h]
0x18002a66e  mov     dword ptr [rax], 1
0x18002a674  mov     [rsi+1ACh], edx
0x18002a67a  mov     [rsi+1B8h], rcx
0x18002a681  mov     [rsi+1A0h], rax
0x18002a688  mov     r8, [r15+2C0h]
0x18002a68f  lea     r9, [rsi+1E0h]
0x18002a696  mov     rax, [r8+28h]
0x18002a69a  mov     [r9], rax
  ... truncated ...
```
