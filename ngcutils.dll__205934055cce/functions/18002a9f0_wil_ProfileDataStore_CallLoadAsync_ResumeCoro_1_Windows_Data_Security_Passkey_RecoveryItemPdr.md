# wil::ProfileDataStore::CallLoadAsync$_ResumeCoro$1_Windows::Data::Security::Passkey::RecoveryItemPdr_

- ea: `0x18002a9f0`
- end: `0x18002b224`
- name: `wil::ProfileDataStore::CallLoadAsync$_ResumeCoro$1_Windows::Data::Security::Passkey::RecoveryItemPdr_`
- size: `2100`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18003a4e4`

## callees

- `0x180003080`
- `0x180003520`
- `0x180007a5c`
- `0x18000ce74`
- `0x18000cfcc`
- `0x18000f7fc`
- `0x18001354c`
- `0x18002a9f0`
- `0x180037a3c`
- `0x18003fcd8`
- `0x18004295c`
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

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002ad98`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002ae1a`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002aea4`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002ad98`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002ae1a`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18002aea4`

## pseudocode

```c
// Hidden C++ exception states: #wind=22 #try_helpers=1
void __fastcall wil::ProfileDataStore::CallLoadAsync__ResumeCoro_1_Windows::Data::Security::Passkey::RecoveryItemPdr_(
        __int64 a1)
{
  __int64 v1; // r14
  __int64 v2; // r12
  _QWORD *v3; // r8
  volatile signed __int32 **v4; // r13
  __int64 v5; // rdx
  signed __int32 v6; // eax
  signed __int32 v7; // ett
  __int64 v8; // rax
  __int64 v9; // r13
  __int64 v10; // r8
  __int64 v11; // rdi
  _QWORD *v12; // rax
  volatile signed __int32 *v13; // rdi
  __int64 v14; // rdx
  __int64 v15; // r8
  volatile signed __int32 *v16; // rdi
  _QWORD *v17; // rsi
  const char *v18; // r9
  int v19; // r8d
  int v20; // edx
  int v21; // ecx
  int v22; // edx
  int v23; // eax
  _QWORD *v24; // rax
  _QWORD *v25; // rcx
  __int64 v26; // rdx
  __int64 v27; // rax
  __int64 v28; // rdx
  __int64 v29; // rcx
  __int64 v30; // rax
  __int64 v31; // rdx
  __int64 v32; // rcx
  __int64 v33; // rax
  __int64 v34; // r8
  __int64 Async; // r8
  __int64 v36; // rdx
  __int64 v37; // r8
  __int64 v38; // rdx
  __int64 v39; // r8
  __int64 v40; // rdx
  __int64 v41; // r8
  _QWORD *v42; // rax
  __int64 (__fastcall ***v43)(_QWORD, __int64 *, _QWORD **); // rdx
  _QWORD *v44; // rax
  volatile signed __int32 *v45; // rdi
  volatile signed __int32 *v46; // rdi
  _QWORD *v47; // rax
  volatile signed __int32 *v48; // rbx
  __int64 v49; // rdx
  __int64 v50; // r8
  volatile signed __int32 *v52; // [rsp+80h] [rbp-158h]
  int CloudStore; // [rsp+80h] [rbp-158h]
  _QWORD *v54; // [rsp+A8h] [rbp-130h]
  volatile signed __int32 **v55; // [rsp+B8h] [rbp-120h]
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
        `wil::ProfileDataStore::CallLoadAsync<Windows::Data::Security::Passkey::ScenarioKeysItemPdr>'::`8'::_parameters_::~_parameters_(v2 + 640);
        if ( *(_WORD *)(v1 + 10) )
          operator delete((void *)(v1 - 48), 0x2F0u);
        return;
      case 0:
        goto LABEL_84;
      case 2:
        v3 = *(_QWORD **)(a1 + 648);
        *(_QWORD *)(a1 + 16) = 0;
        v4 = (volatile signed __int32 **)(a1 + 24);
        *(_QWORD *)(a1 + 24) = 0;
        v5 = v3[1];
        if ( !v5 )
          goto LABEL_80;
        v6 = *(_DWORD *)(v5 + 8);
        do
        {
          if ( !v6 )
LABEL_80:
            std::_Throw_bad_weak_ptr();
          v7 = v6;
          v6 = _InterlockedCompareExchange((volatile signed __int32 *)(v5 + 8), v6 + 1, v6);
        }
        while ( v7 != v6 );
        v55 = (volatile signed __int32 **)(a1 + 24);
        *(_QWORD *)(a1 + 16) = *v3;
        v52 = (volatile signed __int32 *)v3[1];
        *v4 = v52;
        v8 = *(_QWORD *)(a1 + 688);
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
          v10 = *(_QWORD *)(a1 + 656);
          *(_QWORD *)(a1 + 104) = 0;
          *(_QWORD *)(a1 + 112) = 0;
          *(_QWORD *)(a1 + 120) = 0;
          v11 = a1 + 40;
          v12 = (_QWORD *)std::make_shared<wil::ProfileDataItem<Windows::Data::Security::Passkey::RecoveryItemPdr>,Windows::Data::Security::Passkey::RecoveryItemPdr,wil::ProfileDataItemReference<Windows::Data::Security::Passkey::RecoveryItemPdr> &,int,enum wil::ProfileDataItemStatus,enum wil::DataDescriptionLanguage,wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudStoreData,wil::err_exception_policy>,bool,bool,bool,std::wstring,long,int>(
                            (int)a1 + 128,
                            (int)a1 + 104,
                            v10,
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
          *(_QWORD *)(v1 - 24) = *v12;
          *(_QWORD *)(v1 - 16) = v12[1];
          *v12 = 0;
          v12[1] = 0;
          *(_DWORD *)(v1 - 32) = 1;
          if ( *(_QWORD *)(v1 + 136) )
          {
            v13 = *(volatile signed __int32 **)(v1 + 136);
            if ( _InterlockedExchangeAdd(v13 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v13)(v13);
              if ( _InterlockedExchangeAdd(v13 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
            }
            v11 = v1 + 40;
          }
          std::vector<unsigned char>::~vector<unsigned char>(v1 + 104);
          if ( *(_QWORD *)v9 )
            (*(void (**)(void))(**(_QWORD **)v9 + 16LL))();
          std::wstring::~wstring(v11, v14, v15);
          if ( v52 )
          {
            v16 = *(volatile signed __int32 **)(v1 + 24);
            if ( _InterlockedExchangeAdd(v16 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v16)(v16);
              if ( _InterlockedExchangeAdd(v16 + 3, 0xFFFFFFFF) == 1 )
LABEL_20:
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
            }
          }
        }
        else
        {
          try
          {
            v17 = (_QWORD *)(a1 + 144);
            v54 = (_QWORD *)(a1 + 144);
            *(_QWORD *)(a1 + 144) = 0;
            CloudStore = wil::details::SharedCloudStoreState::GetCloudStore(v3[2], a1 + 176);
            *(_QWORD *)(v1 + 184) = *(_QWORD *)(v1 + 696);
            *(_QWORD *)(v1 + 216) = *(_QWORD *)(v1 + 680);
            v19 = *(_DWORD *)(v1 + 672);
            v20 = v19 & 1;
            if ( (v19 & 4) != 0 )
            {
              if ( (v19 & 1) == 0 )
                wil::details::in1diag3::_FailFast_Unexpected(
                  retaddr,
                  (void *)0x8FE,
                  (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil\\profiledatastore.h",
                  v18);
              v20 |= 2u;
            }
            v21 = v20 | 4;
            if ( (v19 & 8) == 0 )
              v21 = v20;
            v22 = v21 | 8;
            if ( (v19 & 0x10) == 0 )
              v22 = v21;
            v23 = v22 | 0x10;
            if ( (v19 & 0x20) == 0 )
              v23 = v22;
            *(_DWORD *)(v1 + 248) = v23;
            v24 = (_QWORD *)wil::ProfileDataStore::GetTypeNameWideString<Windows::Data::Security::Passkey::RecoveryItemPdr>(v1 + 288);
            v25 = v24;
            v26 = v24[2];
            if ( v24[3] > 7u )
              v25 = (_QWORD *)*v24;
            if ( (_DWORD)v26 )
            {
              if ( *((_WORD *)v25 + (unsigned int)v26) )
                abort();
              v27 = v1 + 264;
              *(_DWORD *)(v1 + 264) = 1;
              *(_DWORD *)(v1 + 268) = v26;
              *(_QWORD *)(v1 + 280) = v25;
            }
            else
            {
              v27 = 0;
            }
            *(_QWORD *)(v1 + 256) = v27;
            std::wstring::wstring(v1 + 352, *(_QWORD *)(v1 + 656));
            v28 = *(_QWORD *)(v1 + 368);
            if ( *(_QWORD *)(v1 + 376) <= 7u )
              v29 = v1 + 352;
            else
              v29 = *(_QWORD *)(v1 + 352);
            if ( (_DWORD)v28 )
            {
              if ( *(_WORD *)(v29 + 2LL * (unsigned int)v28) )
                abort();
              v30 = v1 + 328;
              *(_DWORD *)(v1 + 328) = 1;
              *(_DWORD *)(v1 + 332) = v28;
              *(_QWORD *)(v1 + 344) = v29;
            }
            else
            {
              v30 = 0;
            }
            *(_QWORD *)(v1 + 320) = v30;
            std::wstring::wstring(v1 + 416, *(_QWORD *)(v1 + 656) + 32LL);
            v31 = *(_QWORD *)(v1 + 432);
            if ( *(_QWORD *)(v1 + 440) <= 7u )
              v32 = v1 + 416;
            else
              v32 = *(_QWORD *)(v1 + 416);
            if ( (_DWORD)v31 )
            {
              if ( *(_WORD *)(v32 + 2LL * (unsigned int)v31) )
                abort();
              v33 = v1 + 392;
              *(_DWORD *)(v1 + 392) = 1;
              *(_DWORD *)(v1 + 396) = v31;
              *(_QWORD *)(v1 + 408) = v32;
            }
            else
            {
              v33 = 0;
            }
            *(_QWORD *)(v1 + 384) = v33;
            v34 = *(_QWORD *)(v2 + 640);
            *(_QWORD *)(v1 + 448) = *(_QWORD *)(v34 + 40);
            Async = winrt::impl::consume_Windows_Internal_Storage_Cloud_ICloudStore2<winrt::Windows::Internal::Storage::Cloud::CloudStore>::LoadAsync(
                      CloudStore,
                      (int)v1 + 480,
                      (int)v34 + 32,
                      (int)v1 + 448,
                      v1 + 384,
                      v1 + 320,
                      v1 + 256,
                      v1 + 248,
                      v1 + 216,
                      v1 + 184);
            wil::details::AsyncOpWaiter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::CloudStoreData>,winrt::Windows::Internal::Storage::Cloud::CloudStoreData>::AsyncOpWaiter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::CloudStoreData>,winrt::Windows::Internal::Storage::Cloud::CloudStoreData>(
              v1 + 152,
              v1 + 688,
              Async);
            if ( *(_QWORD *)(v1 + 480) )
              winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v1 + 480);
            std::wstring::~wstring(v1 + 416, v36, v37);
            std::wstring::~wstring(v1 + 352, v38, v39);
            std::wstring::~wstring(v1 + 288, v40, v41);
            if ( *(_QWORD *)(v1 + 176) )
              winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v1 + 176);
            v42 = (_QWORD *)wil::details::AsyncOpWaiter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::CloudStoreData>,winrt::Windows::Internal::Storage::Cloud::CloudStoreData>::WaitForResult(
                              v1 + 152,
                              v1 + 488);
            if ( v17 != v42 )
            {
              v43 = (__int64 (__fastcall ***)(_QWORD, __int64 *, _QWORD **))*v42;
              *v42 = 0;
              *v17 = v43;
            }
            if ( *(_QWORD *)(v1 + 488) )
              winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v1 + 488);
            wil::details::AsyncOpWaiter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>,winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>::~AsyncOpWaiter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>,winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>(v1 + 152);
          }
          catch ( Concurrency::task_canceled )
          {
            *(_DWORD *)(a1 + 496) = 0;
            *(_DWORD *)(a1 + 500) = -2147023673;
            *(_OWORD *)(a1 + 504) = 0;
            *(_QWORD *)(a1 + 520) = 0;
            *(_QWORD *)(a1 + 528) = 7;
            *(_WORD *)(a1 + 504) = 0;
            *(_WORD *)(a1 + 536) = 0;
            *(_BYTE *)(a1 + 538) = 1;
            *(_QWORD *)(a1 + 544) = 0;
            *(_QWORD *)(a1 + 552) = 1;
            *(_DWORD *)(a1 + 560) = 0;
            *(_OWORD *)(a1 + 568) = 0;
            *(_QWORD *)(a1 + 568) = 0;
            *(_QWORD *)(a1 + 576) = 0;
            *(_QWORD *)(a1 + 584) = 0;
            v47 = (_QWORD *)std::make_shared<wil::ProfileDataItem<Windows::Data::Security::Passkey::RecoveryItemPdr>,Windows::Data::Security::Passkey::RecoveryItemPdr,wil::ProfileDataItemReference<Windows::Data::Security::Passkey::RecoveryItemPdr> &,int,enum wil::ProfileDataItemStatus,enum wil::DataDescriptionLanguage,wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudStoreData,wil::err_exception_policy>,bool,bool,bool,std::wstring,long,int>(
                              (int)a1 + 592,
                              (int)a1 + 568,
                              *(_QWORD *)(a1 + 656),
                              (int)a1 + 560,
                              a1 + 556,
                              a1 + 552,
                              a1 + 544,
                              a1 + 538,
                              a1 + 537,
                              a1 + 536,
                              a1 + 504,
                              a1 + 500,
                              a1 + 496);
            *(_QWORD *)(a1 - 24) = 0;
            *(_QWORD *)(a1 - 16) = 0;
            *(_QWORD *)(a1 - 24) = *v47;
            *(_QWORD *)(a1 - 16) = v47[1];
            *v47 = 0;
            v47[1] = 0;
            *(_DWORD *)(a1 - 32) = 1;
            if ( *(_QWORD *)(a1 + 600) )
            {
              v48 = *(volatile signed __int32 **)(a1 + 600);
              if ( _InterlockedExchangeAdd(v48 + 2, 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v48)(v48);
                if ( _InterlockedExchangeAdd(v48 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v48 + 8LL))(v48);
              }
            }
            std::vector<unsigned char>::~vector<unsigned char>(a1 + 568);
            if ( *(_QWORD *)(a1 + 544) )
              (*(void (**)(void))(**(_QWORD **)(a1 + 544) + 16LL))();
            std::wstring::~wstring(a1 + 504, v49, v50);
            if ( *v54 )
              winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v54);
            if ( *v55 )
            {
              v46 = *v55;
              if ( _InterlockedExchangeAdd(*v55 + 2, 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v46)(v46);
                if ( _InterlockedExchangeAdd(v46 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v46 + 8LL))(v46);
              }
            }
            v1 = a1;
            goto LABEL_81;
          }
          v44 = wil::ProfileDataStore::Unmarshal<Windows::Data::Security::Passkey::RecoveryItemPdr>(
                  (_QWORD *)(v1 + 608),
                  (__int64 (__fastcall ****)(_QWORD, __int64 *, _QWORD **))v17,
                  *(_DWORD *)(v1 + 672));
          *(_QWORD *)(v1 - 24) = 0;
          *(_QWORD *)(v1 - 16) = 0;
          *(_QWORD *)(v1 - 24) = *v44;
          *(_QWORD *)(v1 - 16) = v44[1];
          *v44 = 0;
          v44[1] = 0;
          *(_DWORD *)(v1 - 32) = 1;
          if ( *(_QWORD *)(v1 + 616) )
          {
            v45 = *(volatile signed __int32 **)(v1 + 616);
            if ( _InterlockedExchangeAdd(v45 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v45)(v45);
              if ( _InterlockedExchangeAdd(v45 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v45 + 8LL))(v45);
            }
          }
          if ( *v17 )
            winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v17);
          if ( *v4 )
          {
            v16 = *v4;
            if ( _InterlockedExchangeAdd(*v4 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v16)(v16);
              if ( _InterlockedExchangeAdd(v16 + 3, 0xFFFFFFFF) == 1 )
                goto LABEL_20;
            }
          }
        }
LABEL_81:
        *(_QWORD *)(v1 + 624) = v1 - 48;
        *(_WORD *)v2 = 0;
        `wil::details::coro::promise_base<std::shared_ptr<wil::ProfileDataItem<Windows::Data::Security::Passkey::RecoveryItemPdr>>>::final_suspend'::`2'::awaiter::await_suspend();
        break;
    }
  }
}

```

## disassembly

```asm
0x18002a9f0  mov     r11, rsp
0x18002a9f3  mov     [r11+10h], rbx
0x18002a9f7  mov     [r11+18h], rsi
0x18002a9fb  mov     [r11+8], rcx
0x18002a9ff  push    rdi
0x18002aa00  push    r12
0x18002aa02  push    r13
0x18002aa04  push    r14
0x18002aa06  push    r15
0x18002aa08  sub     rsp, 1B0h
0x18002aa0f  mov     rax, cs:__security_cookie
0x18002aa16  xor     rax, rsp
0x18002aa19  mov     [rsp+1D8h+var_38], rax
0x18002aa21  mov     r14, rcx
0x18002aa24  mov     [rsp+1D8h+var_160], rcx
0x18002aa29  lea     r12, [r14+8]
0x18002aa2d  movzx   eax, word ptr [r12]
0x18002aa32  mov     [rsp+1D8h+var_150], ax
0x18002aa3a  mov     ebx, 1
0x18002aa3f  add     ax, bx
0x18002aa42  lea     ecx, [rbx+3]
0x18002aa45  cmp     ax, cx
0x18002aa48  ja      loc_18002B1E0; jumptable 000000018002AA6B case 1
0x18002aa4e  mov     [rsp+1D8h+var_148], r12
0x18002aa56  movsx   rax, ax
0x18002aa5a  lea     rdx, __ImageBase
0x18002aa61  mov     ecx, ds:(jpt_18002AA6B - 180000000h)[rdx+rax*4]; switch 5 cases
0x18002aa68  add     rcx, rdx
0x18002aa6b  jmp     rcx; switch jump
0x18002aa6d  jmp     loc_18002B1B0; jumptable 000000018002AA6B case 4
0x18002aa72  xor     r15d, r15d; jumptable 000000018002AA6B case 3
0x18002aa75  mov     r8, [r12+280h]
0x18002aa7d  mov     [r14+10h], r15
0x18002aa81  lea     r13, [r14+18h]
0x18002aa85  mov     [r13+0], r15
0x18002aa89  mov     rdx, [r8+8]
0x18002aa8d  test    rdx, rdx
0x18002aa90  jz      loc_18002B181
0x18002aa96  mov     eax, [rdx+8]
0x18002aa99  jmp     short loc_18002AAA5
0x18002aa9b  lea     ecx, [rax+1]
0x18002aa9e  lock cmpxchg [rdx+8], ecx
0x18002aaa3  jz      short loc_18002AAAE
0x18002aaa5  test    eax, eax
0x18002aaa7  jnz     short loc_18002AA9B
0x18002aaa9  jmp     loc_18002B181
0x18002aaae  mov     [rsp+1D8h+var_120], r13
0x18002aab6  mov     rax, [r8]
0x18002aab9  mov     [r14+10h], rax
0x18002aabd  mov     rax, [r8+8]
0x18002aac1  mov     [rsp+1D8h+var_158], rax
0x18002aac9  mov     [r13+0], rax
0x18002aacd  mov     rax, [r14+2B0h]
0x18002aad4  test    rax, rax
0x18002aad7  jz      loc_18002ACBC
0x18002aadd  mov     eax, [rax+10h]
0x18002aae0  nop
0x18002aae1  test    eax, eax
0x18002aae3  jz      loc_18002ACBC
0x18002aae9  lea     rsi, [r14+20h]
0x18002aaed  mov     [rsi], r15d
0x18002aaf0  lea     rdi, [r14+24h]
0x18002aaf4  mov     dword ptr [rdi], 800704C7h
0x18002aafa  xorps   xmm0, xmm0
0x18002aafd  movups  xmmword ptr [r14+28h], xmm0
0x18002ab02  mov     [r14+38h], r15
0x18002ab06  mov     qword ptr [r14+40h], 7
0x18002ab0e  xor     ecx, ecx
0x18002ab10  mov     [r14+28h], cx
0x18002ab15  lea     rbx, [r14+48h]
0x18002ab19  mov     [rbx], r15b
0x18002ab1c  lea     r11, [r14+49h]
0x18002ab20  mov     [r11], r15b
0x18002ab23  lea     r10, [r14+4Ah]
0x18002ab27  mov     byte ptr [r10], 1
0x18002ab2b  lea     r13, [r14+50h]
0x18002ab2f  mov     [r13+0], r15
0x18002ab33  lea     rdx, [r14+58h]
0x18002ab37  mov     dword ptr [rdx], 1
0x18002ab3d  lea     rax, [r14+5Ch]
0x18002ab41  mov     [rax], r15d
0x18002ab44  lea     r9, [r14+60h]
0x18002ab48  mov     [r9], r15d
0x18002ab4b  mov     r8, [r14+290h]
0x18002ab52  mov     [r14+68h], r15
0x18002ab56  mov     [r14+70h], r15
0x18002ab5a  mov     [r14+78h], r15
0x18002ab5e  lea     rcx, [r14+80h]
0x18002ab65  mov     [rsp+1D8h+var_178], rsi
0x18002ab6a  mov     [rsp+1D8h+var_180], rdi
0x18002ab6f  lea     rdi, [r14+28h]
0x18002ab73  mov     [rsp+1D8h+var_188], rdi
0x18002ab78  mov     [rsp+1D8h+var_190], rbx
0x18002ab7d  mov     [rsp+1D8h+var_198], r11
0x18002ab82  mov     [rsp+1D8h+var_1A0], r10
0x18002ab87  mov     [rsp+1D8h+var_1A8], r13
0x18002ab8c  mov     [rsp+1D8h+var_1B0], rdx
0x18002ab91  mov     [rsp+1D8h+var_1B8], rax
0x18002ab96  lea     rdx, [r14+68h]
0x18002ab9a  call    ??$make_shared@V?$ProfileDataItem@URecoveryItemPdr@Passkey@Security@Data@Windows@@@wil@@URecoveryItemPdr@Passkey@Security@Data@Windows@@AEAV?$ProfileDataItemReference@URecoveryItemPdr@Passkey@Security@Data@Windows@@@2@HW4ProfileDataItemStatus@2@W4DataDescriptionLanguage@2@V?$com_ptr_t@UICloudStoreData@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@2@_N_N_NV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@JH@std@@YA?AV?$shared_ptr@V?$ProfileDataItem@URecoveryItemPdr@Passkey@Security@Data@Windows@@@wil@@@0@$$QEAURecoveryItemPdr@Passkey@Security@Data@Windows@@AEAV?$ProfileDataItemReference@URecoveryItemPdr@Passkey@Security@Data@Windows@@@wil@@$$QEAH$$QEAW4ProfileDataItemStatus@8@$$QEAW4DataDescriptionLanguage@8@$$QEAV?$com_ptr_t@UICloudStoreData@Cloud@Storage@Internal@Windows@@Uerr_exception_policy@wil@@@8@$$QEA_N66$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAJ2@Z; std::make_shared<wil::ProfileDataItem<Windows::Data::Security::Passkey::RecoveryItemPdr>,Windows::Data::Security::Passkey::RecoveryItemPdr,wil::ProfileDataItemReference<Windows::Data::Security::Passkey::RecoveryItemPdr> &,int,wil::ProfileDataItemStatus,wil::DataDescriptionLanguage,wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudStoreData,wil::err_exception_policy>,bool,bool,bool,std::wstring,long,int>(Windows::Data::Security::Passkey::RecoveryItemPdr &&,wil::ProfileDataItemReference<Windows::Data::Security::Passkey::RecoveryItemPdr> &,int &&,wil::ProfileDataItemStatus &&,wil::DataDescriptionLanguage &&,wil::com_ptr_t<Windows::Internal::Storage::Cloud::ICloudStoreData,wil::err_exception_policy> &&,bool &&,bool &&,bool &&,std::wstring &&,long &&,int &&)
0x18002ab9f  mov     [r14-18h], r15
0x18002aba3  mov     [r14-10h], r15
0x18002aba7  mov     rcx, [rax]
0x18002abaa  mov     [r14-18h], rcx
0x18002abae  mov     rcx, [rax+8]
0x18002abb2  mov     [r14-10h], rcx
0x18002abb6  mov     [rax], r15
0x18002abb9  mov     [rax+8], r15
0x18002abbd  mov     dword ptr [r14-20h], 1
0x18002abc5  mov     rax, [r14+88h]
0x18002abcc  mov     [rsp+1D8h+var_108], rax
0x18002abd4  or      ebx, 0FFFFFFFFh
0x18002abd7  test    rax, rax
0x18002abda  jz      short loc_18002AC22
0x18002abdc  mov     rdi, [r14+88h]
0x18002abe3  mov     [rsp+1D8h+var_108], rdi
0x18002abeb  mov     eax, ebx
0x18002abed  lock xadd [rdi+8], eax
0x18002abf2  add     eax, ebx
0x18002abf4  jnz     short loc_18002AC1E
0x18002abf6  mov     rax, [rdi]
0x18002abf9  mov     rcx, rdi
0x18002abfc  mov     rax, [rax]
0x18002abff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ac04  mov     eax, ebx
0x18002ac06  lock xadd [rdi+0Ch], eax
0x18002ac0b  add     eax, ebx
0x18002ac0d  jnz     short loc_18002AC1E
0x18002ac0f  mov     rax, [rdi]
0x18002ac12  mov     rcx, rdi
0x18002ac15  mov     rax, [rax+8]
0x18002ac19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ac1e  lea     rdi, [r14+28h]
0x18002ac22  lea     rcx, [r14+68h]
0x18002ac26  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x18002ac2b  nop
0x18002ac2c  mov     rax, [r13+0]
0x18002ac30  mov     [rsp+1D8h+var_168], rax
0x18002ac35  test    rax, rax
0x18002ac38  jz      short loc_18002AC59
0x18002ac3a  mov     rax, [r13+0]
0x18002ac3e  mov     [rsp+1D8h+var_168], rax
0x18002ac43  mov     rcx, [rax]
0x18002ac46  mov     rax, [rcx+10h]
0x18002ac4a  mov     rcx, [r13+0]
0x18002ac4e  mov     [rsp+1D8h+var_168], rcx
0x18002ac53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ac58  nop
0x18002ac59  mov     rcx, rdi
0x18002ac5c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002ac61  nop
0x18002ac62  mov     rax, [rsp+1D8h+var_158]
0x18002ac6a  mov     [rsp+1D8h+var_138], rax
0x18002ac72  test    rax, rax
0x18002ac75  jz      short loc_18002ACB7
0x18002ac77  mov     rdi, [r14+18h]
0x18002ac7b  mov     [rsp+1D8h+var_138], rdi
0x18002ac83  mov     eax, ebx
0x18002ac85  lock xadd [rdi+8], eax
0x18002ac8a  add     eax, ebx
0x18002ac8c  jnz     short loc_18002ACB7
0x18002ac8e  mov     rax, [rdi]
0x18002ac91  mov     rcx, rdi
0x18002ac94  mov     rax, [rax]
0x18002ac97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ac9c  mov     eax, ebx
0x18002ac9e  lock xadd [rdi+0Ch], eax
0x18002aca3  add     eax, ebx
0x18002aca5  jnz     short loc_18002ACB7
0x18002aca7  mov     rax, [rdi]
0x18002acaa  mov     rcx, rdi
0x18002acad  mov     rax, [rax+8]
0x18002acb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002acb6  nop
0x18002acb7  jmp     loc_18002B194
0x18002acbc  lea     rsi, [r14+90h]
0x18002acc3  mov     [rsp+1D8h+var_130], rsi
0x18002accb  mov     [rsi], r15
0x18002acce  lea     rdx, [r14+0B0h]
0x18002acd5  mov     rcx, [r8+10h]
0x18002acd9  call    ?GetCloudStore@SharedCloudStoreState@details@wil@@QEAA?BUCloudStore@Cloud@Storage@Internal@Windows@winrt@@XZ; wil::details::SharedCloudStoreState::GetCloudStore(void)
0x18002acde  mov     [rsp+1D8h+var_158], rax
0x18002ace6  lea     rdi, [r14+0B8h]
0x18002aced  mov     rcx, [r14+2B8h]
0x18002acf4  mov     [rdi], rcx
0x18002acf7  mov     rcx, [r14+2A8h]
0x18002acfe  mov     [r14+0D8h], rcx
0x18002ad05  mov     r8d, [r14+2A0h]
0x18002ad0c  mov     edx, r8d
0x18002ad0f  and     edx, ebx
0x18002ad11  bt      r8d, 2
0x18002ad16  jnb     short loc_18002AD3B
0x18002ad18  mov     rcx, [rsp+1D8h]; this
0x18002ad20  mov     al, dl
0x18002ad22  xor     al, bl
0x18002ad24  jz      short loc_18002AD38
0x18002ad26  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\sdk\\inc\\wil\\pr"...
0x18002ad2d  mov     edx, 8FEh; void *
0x18002ad32  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18002ad38  or      edx, 2
0x18002ad3b  mov     ecx, edx
0x18002ad3d  or      ecx, 4
0x18002ad40  bt      r8d, 3
0x18002ad45  cmovnb  ecx, edx
0x18002ad48  mov     edx, ecx
0x18002ad4a  or      edx, 8
0x18002ad4d  bt      r8d, 4
0x18002ad52  cmovnb  edx, ecx
0x18002ad55  mov     eax, edx
0x18002ad57  or      eax, 10h
0x18002ad5a  bt      r8d, 5
0x18002ad5f  cmovnb  eax, edx
0x18002ad62  mov     [r14+0F8h], eax
0x18002ad69  lea     rcx, [r14+120h]
0x18002ad70  call    ??$GetTypeNameWideString@URecoveryItemPdr@Passkey@Security@Data@Windows@@@ProfileDataStore@wil@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; wil::ProfileDataStore::GetTypeNameWideString<Windows::Data::Security::Passkey::RecoveryItemPdr>(void)
0x18002ad75  mov     rcx, rax
0x18002ad78  mov     rdx, [rax+10h]
0x18002ad7c  cmp     qword ptr [rax+18h], 7
0x18002ad81  jbe     short loc_18002AD86
0x18002ad83  mov     rcx, [rax]
0x18002ad86  test    edx, edx
0x18002ad88  jnz     short loc_18002AD8F
0x18002ad8a  mov     rax, r15
0x18002ad8d  jmp     short loc_18002ADB6
0x18002ad8f  mov     eax, edx
0x18002ad91  cmp     [rcx+rax*2], r15w
0x18002ad96  jz      short loc_18002AD9F
0x18002ad98  call    cs:__imp_abort
0x18002ad9f  lea     rax, [r14+108h]
0x18002ada6  mov     [rax], ebx
0x18002ada8  mov     [r14+10Ch], edx
0x18002adaf  mov     [r14+118h], rcx
0x18002adb6  mov     [r14+100h], rax
0x18002adbd  lea     rbx, [r14+160h]
0x18002adc4  mov     rdx, [r14+290h]
0x18002adcb  mov     rcx, rbx
0x18002adce  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002add3  nop
0x18002add4  mov     rdx, [r14+170h]
0x18002addb  mov     [rsp+1D8h+var_D8], rdx
0x18002ade3  mov     rax, [r14+178h]
0x18002adea  mov     [rsp+1D8h+var_D0], rax
0x18002adf2  cmp     rax, 7
0x18002adf6  jbe     short loc_18002AE05
0x18002adf8  mov     rcx, [rbx]
0x18002adfb  mov     [rsp+1D8h+var_E8], rcx
0x18002ae03  jmp     short loc_18002AE08
0x18002ae05  mov     rcx, rbx
0x18002ae08  test    edx, edx
0x18002ae0a  jnz     short loc_18002AE11
0x18002ae0c  mov     rax, r15
0x18002ae0f  jmp     short loc_18002AE3C
0x18002ae11  mov     eax, edx
0x18002ae13  cmp     [rcx+rax*2], r15w
0x18002ae18  jz      short loc_18002AE21
0x18002ae1a  call    cs:__imp_abort
0x18002ae21  lea     rax, [r14+148h]
0x18002ae28  mov     dword ptr [rax], 1
0x18002ae2e  mov     [r14+14Ch], edx
0x18002ae35  mov     [r14+158h], rcx
0x18002ae3c  mov     [r14+140h], rax
0x18002ae43  lea     rbx, [r14+1A0h]
0x18002ae4a  mov     rdx, [r14+290h]
0x18002ae51  add     rdx, 20h ; ' '
0x18002ae55  mov     rcx, rbx
0x18002ae58  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002ae5d  nop
0x18002ae5e  mov     rdx, [r14+1B0h]
0x18002ae65  mov     [rsp+1D8h+var_B8], rdx
0x18002ae6d  mov     rax, [r14+1B8h]
0x18002ae74  mov     [rsp+1D8h+var_B0], rax
0x18002ae7c  cmp     rax, 7
0x18002ae80  jbe     short loc_18002AE8F
0x18002ae82  mov     rcx, [rbx]
0x18002ae85  mov     [rsp+1D8h+var_C8], rcx
0x18002ae8d  jmp     short loc_18002AE92
0x18002ae8f  mov     rcx, rbx
0x18002ae92  test    edx, edx
0x18002ae94  jnz     short loc_18002AE9B
0x18002ae96  mov     rax, r15
0x18002ae99  jmp     short loc_18002AEC6
0x18002ae9b  mov     eax, edx
0x18002ae9d  cmp     [rcx+rax*2], r15w
0x18002aea2  jz      short loc_18002AEAB
0x18002aea4  call    cs:__imp_abort
0x18002aeab  lea     rax, [r14+188h]
0x18002aeb2  mov     dword ptr [rax], 1
0x18002aeb8  mov     [r14+18Ch], edx
0x18002aebf  mov     [r14+198h], rcx
0x18002aec6  mov     [r14+180h], rax
0x18002aecd  mov     r8, [r12+280h]
0x18002aed5  lea     r9, [r14+1C0h]
0x18002aedc  mov     rax, [r8+28h]
0x18002aee0  mov     [r9], rax
0x18002aee3  lea     rdx, [r14+1E0h]
0x18002aeea  lea     rax, [r14+100h]
0x18002aef1  lea     rcx, [r14+140h]
0x18002aef8  lea     r10, [r14+180h]
0x18002aeff  add     r8, 20h ; ' '
0x18002af03  mov     [rsp+1D8h+var_190], rdi
  ... truncated ...
```
