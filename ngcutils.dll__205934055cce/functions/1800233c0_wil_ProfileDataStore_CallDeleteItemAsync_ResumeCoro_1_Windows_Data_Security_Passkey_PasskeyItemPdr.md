# wil::ProfileDataStore::CallDeleteItemAsync$_ResumeCoro$1_Windows::Data::Security::Passkey::PasskeyItemPdr_

- ea: `0x1800233c0`
- end: `0x180023b54`
- name: `wil::ProfileDataStore::CallDeleteItemAsync$_ResumeCoro$1_Windows::Data::Security::Passkey::PasskeyItemPdr_`
- size: `1940`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180024a9c`

## callees

- `0x180003080`
- `0x180003520`
- `0x180007a5c`
- `0x18000ce74`
- `0x18000f7fc`
- `0x18001354c`
- `0x1800233c0`
- `0x1800378f4`
- `0x180043818`
- `0x18004478c`
- `0x180045428`
- `0x180045914`
- `0x180048b78`
- `0x180049238`
- `0x18004d964`
- `0x18004eaac`
- `0x18004ee8c`
- `0x180061010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180023adb`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180023adb`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800236b8`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180023739`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800237c1`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800236b8`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180023739`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800237c1`

## pseudocode

```c
// Hidden C++ exception states: #wind=15 #try_helpers=1
void __fastcall wil::ProfileDataStore::CallDeleteItemAsync__ResumeCoro_1_Windows::Data::Security::Passkey::PasskeyItemPdr_(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v3; // rdi
  __int64 v4; // r14
  __int16 *v5; // rdx
  _QWORD *v6; // r8
  volatile signed __int32 **v7; // r12
  __int64 v8; // rdx
  signed __int32 v9; // eax
  signed __int32 v10; // ett
  __int64 v11; // rdx
  char v12; // al
  int v13; // ecx
  int v14; // eax
  __int64 v15; // rax
  __int128 v16; // xmm0
  __int128 v17; // xmm0
  __int64 v18; // rdx
  __int64 v19; // r8
  volatile signed __int32 *v20; // rsi
  const struct winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult *v21; // rbx
  _QWORD *v22; // rax
  _QWORD *v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // rax
  __int64 *v26; // r15
  __int64 v27; // rdx
  __int64 v28; // rcx
  __int64 v29; // rax
  __int64 *v30; // r15
  __int64 v31; // rdx
  __int64 v32; // rcx
  __int64 v33; // rax
  __int64 v34; // r8
  __int64 v35; // r8
  __int64 v36; // rdx
  __int64 v37; // r8
  __int64 v38; // rdx
  __int64 v39; // r8
  __int64 v40; // rdx
  __int64 v41; // r8
  const struct winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult *v42; // rax
  __int64 v43; // rdx
  __int64 v44; // r8
  __int64 v45; // rax
  __int64 v46; // rdx
  __int64 v47; // r8
  volatile signed __int32 *v48; // rdi
  __int64 v49; // rbx
  int v50; // ecx
  __int16 v51; // ax
  int v52; // ecx
  __int16 v53; // ax
  __int64 v54; // rdx
  __int64 v55; // r8
  __int64 v56; // [rsp+0h] [rbp-228h] BYREF
  __int64 v57; // [rsp+60h] [rbp-1C8h]
  __int64 v58; // [rsp+68h] [rbp-1C0h]
  __int16 v59; // [rsp+70h] [rbp-1B8h]
  __int64 v60; // [rsp+78h] [rbp-1B0h]
  __int64 CloudStore; // [rsp+80h] [rbp-1A8h]
  volatile signed __int32 *v62; // [rsp+90h] [rbp-198h]
  __int64 *v63; // [rsp+98h] [rbp-190h]
  __int64 v64; // [rsp+A0h] [rbp-188h]
  volatile signed __int32 **v65; // [rsp+A8h] [rbp-180h]
  __int64 v68; // [rsp+C2h] [rbp-166h]
  int v69; // [rsp+CAh] [rbp-15Eh]
  __int16 v70; // [rsp+CEh] [rbp-15Ah]
  __int64 v71; // [rsp+E0h] [rbp-148h]
  __int64 v72; // [rsp+F0h] [rbp-138h]
  unsigned __int64 v73; // [rsp+F8h] [rbp-130h]
  __int64 v74; // [rsp+100h] [rbp-128h]
  __int64 v75; // [rsp+110h] [rbp-118h]
  unsigned __int64 v76; // [rsp+118h] [rbp-110h]
  __int64 v77; // [rsp+120h] [rbp-108h]
  int v78; // [rsp+128h] [rbp-100h]
  int v79; // [rsp+12Ch] [rbp-FCh]
  __int128 v80; // [rsp+130h] [rbp-F8h]
  __int128 v81; // [rsp+140h] [rbp-E8h]
  __int128 v82; // [rsp+158h] [rbp-D0h]
  __int128 v83; // [rsp+168h] [rbp-C0h]
  __int64 v84; // [rsp+178h] [rbp-B0h]
  int v85; // [rsp+180h] [rbp-A8h]
  int v86; // [rsp+184h] [rbp-A4h]
  wil::details::in1diag3 *retaddr; // [rsp+228h] [rbp+0h]

  v3 = a1;
  v58 = a1;
  v4 = a1 + 8;
  v59 = *(_WORD *)(a1 + 8);
  if ( (unsigned __int16)(v59 + 1) > 4u )
  {
LABEL_82:
    __debugbreak();
  }
  else
  {
    v60 = a1 + 8;
    v5 = &_ImageBase;
    switch ( v59 )
    {
      case -1:
      case 1:
      case 3:
        if ( *(_QWORD *)(a1 - 16) && wil::details::coro::g_pfnDestroyRestrictedErrorInformation )
        {
          wil::details::coro::g_pfnDestroyRestrictedErrorInformation();
          *(_QWORD *)(v3 - 16) = 0;
        }
        if ( *(_DWORD *)(v3 - 80) == 1 )
        {
          std::wstring::~wstring(v3 - 56, v5, a3);
        }
        else if ( *(_DWORD *)(v3 - 80) == 2 )
        {
          __ExceptionPtrDestroy((void *)(v3 - 72));
        }
        `wil::ProfileDataStore::CallDeleteItemAsync<Windows::Data::Security::Passkey::PasskeyItemPdr>'::`8'::_parameters_::~_parameters_(v4 + 624);
        if ( *(_WORD *)(v3 + 10) )
          operator delete((void *)(v3 - 96), 0x320u);
        return;
      case 0:
        goto LABEL_82;
      case 2:
        v6 = *(_QWORD **)(a1 + 632);
        *(_QWORD *)(a1 + 16) = 0;
        v7 = (volatile signed __int32 **)(a1 + 24);
        *(_QWORD *)(a1 + 24) = 0;
        v8 = v6[1];
        if ( !v8 )
          goto LABEL_71;
        v9 = *(_DWORD *)(v8 + 8);
        do
        {
          if ( !v9 )
LABEL_71:
            std::_Throw_bad_weak_ptr();
          v10 = v9;
          v9 = _InterlockedCompareExchange((volatile signed __int32 *)(v8 + 8), v9 + 1, v9);
        }
        while ( v10 != v9 );
        v65 = (volatile signed __int32 **)(a1 + 24);
        *(_QWORD *)(a1 + 16) = *v6;
        *v7 = (volatile signed __int32 *)v6[1];
        v11 = *(unsigned int *)(a1 + 664);
        if ( (*(_DWORD *)(a1 + 664) & 7) == 0
          || (v12 = 1, (((*(_DWORD *)(a1 + 664) & 7) - 1LL) & *(_DWORD *)(a1 + 664) & 7) == 0) )
        {
          v12 = 0;
        }
        if ( v12 )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x91F,
            (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil\\profiledatastore.h",
            (const char *)4);
        if ( (v11 & 1) != 0 )
        {
          v13 = 1;
        }
        else
        {
          v13 = 2;
          if ( (v11 & 2) == 0 )
          {
            v13 = 0;
            if ( (v11 & 4) != 0 )
              v13 = 4;
          }
        }
        v14 = v13 | 0x20;
        if ( (v11 & 0x10) == 0 )
          v14 = v13;
        *(_DWORD *)(v3 + 32) = v14;
        v15 = *(_QWORD *)(v3 + 688);
        if ( v15 && *(_DWORD *)(v15 + 16) )
        {
          *(_OWORD *)(v3 + 96) = 0;
          *(_QWORD *)(v3 + 112) = 0;
          *(_QWORD *)(v3 + 120) = 7;
          *(_WORD *)(v3 + 96) = 0;
          *(_QWORD *)(v3 + 40) = 0;
          *(_DWORD *)(v3 + 48) = 0;
          *(_DWORD *)(v3 + 52) = -2147023673;
          v82 = *(_OWORD *)(v3 + 96);
          v83 = *(_OWORD *)(v3 + 112);
          v16 = v83;
          *(_OWORD *)(v3 + 56) = v82;
          *(_OWORD *)(v3 + 72) = v16;
          *(_QWORD *)(v3 + 112) = 0;
          *(_QWORD *)(v3 + 120) = 7;
          *(_WORD *)(v3 + 96) = 0;
          *(_QWORD *)(v3 + 88) = 0;
          v77 = *(_QWORD *)(v3 + 40);
          *(_QWORD *)(v3 - 72) = v77;
          v78 = *(_DWORD *)(v3 + 48);
          *(_DWORD *)(v3 - 64) = v78;
          v79 = *(_DWORD *)(v3 + 52);
          *(_DWORD *)(v3 - 60) = v79;
          v80 = *(_OWORD *)(v3 + 56);
          v81 = *(_OWORD *)(v3 + 72);
          v17 = v81;
          *(_OWORD *)(v3 - 56) = v80;
          *(_OWORD *)(v3 - 40) = v17;
          *(_QWORD *)(v3 + 72) = 0;
          *(_QWORD *)(v3 + 80) = 7;
          *(_WORD *)(v3 + 56) = 0;
          *(_QWORD *)(v3 - 24) = 0;
          *(_DWORD *)(v3 - 80) = 1;
          std::wstring::~wstring(v3 + 56, v11, v6);
          std::wstring::~wstring(v3 + 96, v18, v19);
          v62 = *v7;
          if ( v62 )
          {
            v20 = *v7;
            v62 = v20;
            if ( _InterlockedExchangeAdd(v20 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v20)(v20);
              if ( _InterlockedExchangeAdd(v20 + 3, 0xFFFFFFFF) == 1 )
LABEL_25:
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v20 + 8LL))(v20);
            }
          }
        }
        else
        {
          try
          {
            v21 = (const struct winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult *)(v3 + 128);
            v63 = (__int64 *)(v3 + 128);
            *(_QWORD *)(v3 + 128) = 0;
            CloudStore = wil::details::SharedCloudStoreState::GetCloudStore(v6[2], v3 + 160);
            *(_QWORD *)(v3 + 168) = *(_QWORD *)(v3 + 680);
            *(_QWORD *)(v3 + 200) = *(_QWORD *)(v3 + 672);
            v57 = *(_QWORD *)(v3 + 656);
            v22 = (_QWORD *)wil::ProfileDataStore::GetTypeNameWideString<Windows::Data::Security::Passkey::PasskeyItemPdr>(v3 + 264);
            v23 = v22;
            v24 = v22[2];
            if ( v22[3] > 7u )
              v23 = (_QWORD *)*v22;
            if ( (_DWORD)v24 )
            {
              if ( *((_WORD *)v23 + (unsigned int)v24) )
                abort();
              v25 = v3 + 240;
              *(_DWORD *)(v3 + 240) = 1;
              *(_DWORD *)(v3 + 244) = v24;
              *(_QWORD *)(v3 + 256) = v23;
            }
            else
            {
              v25 = 0;
            }
            *(_QWORD *)(v3 + 232) = v25;
            v26 = (__int64 *)(v3 + 328);
            std::wstring::wstring(v3 + 328, *(_QWORD *)(v3 + 640));
            v27 = *(_QWORD *)(v3 + 344);
            v72 = v27;
            v73 = *(_QWORD *)(v3 + 352);
            if ( v73 <= 7 )
            {
              v28 = v3 + 328;
            }
            else
            {
              v28 = *v26;
              v71 = *v26;
            }
            if ( (_DWORD)v27 )
            {
              if ( *(_WORD *)(v28 + 2LL * (unsigned int)v27) )
                abort();
              v29 = v3 + 304;
              *(_DWORD *)(v3 + 304) = 1;
              *(_DWORD *)(v3 + 308) = v27;
              *(_QWORD *)(v3 + 320) = v28;
            }
            else
            {
              v29 = 0;
            }
            *(_QWORD *)(v3 + 296) = v29;
            v30 = (__int64 *)(v3 + 392);
            std::wstring::wstring(v3 + 392, *(_QWORD *)(v3 + 640) + 32LL);
            v31 = *(_QWORD *)(v3 + 408);
            v75 = v31;
            v76 = *(_QWORD *)(v3 + 416);
            if ( v76 <= 7 )
            {
              v32 = v3 + 392;
            }
            else
            {
              v32 = *v30;
              v74 = *v30;
            }
            if ( (_DWORD)v31 )
            {
              if ( *(_WORD *)(v32 + 2LL * (unsigned int)v31) )
                abort();
              v33 = v3 + 368;
              *(_DWORD *)(v3 + 368) = 1;
              *(_DWORD *)(v3 + 372) = v31;
              *(_QWORD *)(v3 + 384) = v32;
            }
            else
            {
              v33 = 0;
            }
            *(_QWORD *)(v3 + 360) = v33;
            v34 = *(_QWORD *)(v4 + 624);
            *(_QWORD *)(v3 + 424) = *(_QWORD *)(v34 + 40);
            v35 = winrt::impl::consume_Windows_Internal_Storage_Cloud_ICloudStore2<winrt::Windows::Internal::Storage::Cloud::CloudStore>::DeleteAsync(
                    CloudStore,
                    (int)v3 + 456,
                    (int)v34 + 32,
                    (int)v3 + 424,
                    v3 + 360,
                    v3 + 296,
                    v3 + 232,
                    v57,
                    v3 + 32,
                    v3 + 200,
                    v3 + 168);
            wil::details::AsyncOpWaiter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>,winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>::AsyncOpWaiter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>,winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>(
              v3 + 136,
              v3 + 688,
              v35);
            if ( *(_QWORD *)(v3 + 456) )
              winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v3 + 456);
            std::wstring::~wstring(v3 + 392, v36, v37);
            std::wstring::~wstring(v3 + 328, v38, v39);
            std::wstring::~wstring(v3 + 264, v40, v41);
            if ( *(_QWORD *)(v3 + 160) )
              winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v3 + 160);
            v42 = (const struct winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult *)wil::details::AsyncOpWaiter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>,winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>::WaitForResult(
                                                                                                   v3 + 136,
                                                                                                   v3 + 464);
            if ( v21 != v42 )
            {
              v43 = *(_QWORD *)v42;
              *(_QWORD *)v42 = 0;
              *(_QWORD *)v21 = v43;
            }
            CloudStore = *(_QWORD *)(v3 + 464);
            if ( CloudStore )
              winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v3 + 464);
            wil::details::AsyncOpWaiter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>,winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>::~AsyncOpWaiter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>,winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>(v3 + 136);
          }
          catch ( Concurrency::task_canceled )
          {
            v49 = v58;
            *(_OWORD *)(v58 + 528) = 0;
            *(_QWORD *)(v49 + 472) = 0;
            *(_DWORD *)(v49 + 480) = 0;
            *(_DWORD *)(v49 + 484) = -2147023673;
            *(_OWORD *)(v49 + 488) = 0;
            v68 = *(_QWORD *)(v49 + 530);
            v69 = *(_DWORD *)(v49 + 538);
            v50 = v69;
            v70 = *(_WORD *)(v49 + 542);
            v51 = v70;
            *(_QWORD *)(v49 + 490) = v68;
            *(_DWORD *)(v49 + 498) = v50;
            *(_WORD *)(v49 + 502) = v51;
            *(_QWORD *)(v49 + 544) = 0;
            *(_QWORD *)(v49 + 552) = 7;
            *(_WORD *)(v49 + 528) = 0;
            *(_QWORD *)(v49 + 520) = 0;
            v84 = *(_QWORD *)(v49 + 472);
            *(_QWORD *)(v49 - 72) = v84;
            v85 = *(_DWORD *)(v49 + 480);
            *(_DWORD *)(v49 - 64) = v85;
            v86 = *(_DWORD *)(v49 + 484);
            *(_DWORD *)(v49 - 60) = v86;
            *(_OWORD *)(v49 - 56) = 0;
            *(_QWORD *)(v49 - 40) = 0;
            *(_QWORD *)(v49 - 32) = 0;
            *(_WORD *)(v49 - 56) = 0;
            v68 = *(_QWORD *)(v49 + 530);
            v69 = *(_DWORD *)(v49 + 538);
            v52 = v69;
            v70 = *(_WORD *)(v49 + 542);
            v53 = v70;
            *(_QWORD *)(v49 - 54) = v68;
            *(_DWORD *)(v49 - 46) = v52;
            *(_WORD *)(v49 - 42) = v53;
            *(_QWORD *)(v49 - 40) = 0;
            *(_QWORD *)(v49 - 32) = 7;
            *(_QWORD *)(v49 + 504) = 0;
            *(_QWORD *)(v49 + 512) = 7;
            *(_WORD *)(v49 + 488) = 0;
            *(_QWORD *)(v49 - 24) = 0;
            *(_DWORD *)(v49 - 80) = 1;
            std::wstring::~wstring(v49 + 488, &v56, v44);
            std::wstring::~wstring(v49 + 528, v54, v55);
            v64 = *v63;
            if ( v64 )
              winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v63);
            v62 = *v65;
            if ( v62 )
            {
              v48 = *v65;
              v62 = v48;
              if ( _InterlockedExchangeAdd(v48 + 2, 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v48)(v48);
                if ( _InterlockedExchangeAdd(v48 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v48 + 8LL))(v48);
              }
            }
            v3 = v58;
            v4 = v60;
            goto LABEL_72;
          }
          v45 = wil::ProfileDataStoreSaveResult::ProfileDataStoreSaveResult(
                  (wil::ProfileDataStoreSaveResult *)(v3 + 560),
                  v21);
          *(_QWORD *)(v3 - 72) = *(_QWORD *)v45;
          *(_DWORD *)(v3 - 64) = *(_DWORD *)(v45 + 8);
          *(_DWORD *)(v3 - 60) = *(_DWORD *)(v45 + 12);
          *(_OWORD *)(v3 - 56) = 0;
          *(_QWORD *)(v3 - 40) = 0;
          *(_QWORD *)(v3 - 32) = 0;
          *(_OWORD *)(v3 - 56) = *(_OWORD *)(v45 + 16);
          *(_OWORD *)(v3 - 40) = *(_OWORD *)(v45 + 32);
          *(_QWORD *)(v45 + 32) = 0;
          *(_QWORD *)(v45 + 40) = 7;
          *(_WORD *)(v45 + 16) = 0;
          *(_QWORD *)(v3 - 24) = *(_QWORD *)(v45 + 48);
          *(_DWORD *)(v3 - 80) = 1;
          std::wstring::~wstring(v3 + 576, v46, v47);
          v64 = *(_QWORD *)v21;
          if ( v64 )
            winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v21);
          v62 = *v7;
          if ( v62 )
          {
            v20 = *v7;
            v62 = v20;
            if ( _InterlockedExchangeAdd(v20 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v20)(v20);
              if ( _InterlockedExchangeAdd(v20 + 3, 0xFFFFFFFF) == 1 )
                goto LABEL_25;
            }
          }
        }
LABEL_72:
        *(_QWORD *)(v3 + 616) = v3 - 96;
        *(_WORD *)v4 = 0;
        `wil::details::coro::promise_base<wil::ProfileDataStoreSaveResult>::final_suspend'::`2'::awaiter::await_suspend();
        break;
    }
  }
}

```

## disassembly

```asm
0x1800233c0  mov     r11, rsp
0x1800233c3  mov     [r11+10h], rbx
0x1800233c7  mov     [r11+18h], rsi
0x1800233cb  mov     [r11+8], rcx
0x1800233cf  push    rdi
0x1800233d0  push    r12
0x1800233d2  push    r13
0x1800233d4  push    r14
0x1800233d6  push    r15
0x1800233d8  sub     rsp, 200h
0x1800233df  mov     rax, cs:__security_cookie
0x1800233e6  xor     rax, rsp
0x1800233e9  mov     [rsp+228h+var_38], rax
0x1800233f1  mov     rdi, rcx
0x1800233f4  mov     [rsp+228h+var_1C0], rcx
0x1800233f9  lea     r14, [rdi+8]
0x1800233fd  movzx   eax, word ptr [r14]
0x180023401  mov     [rsp+228h+var_1B8], ax
0x180023406  mov     r15d, 1
0x18002340c  add     ax, r15w
0x180023410  lea     r9d, [r15+3]; char *
0x180023414  cmp     ax, r9w
0x180023418  ja      loc_180023B0F; jumptable 0000000180023438 case 1
0x18002341e  mov     [rsp+228h+var_1B0], r14
0x180023423  movsx   rax, ax
0x180023427  lea     rdx, __ImageBase
0x18002342e  mov     ecx, ds:(jpt_180023438 - 180000000h)[rdx+rax*4]; switch 5 cases
0x180023435  add     rcx, rdx
0x180023438  jmp     rcx; switch jump
0x18002343a  jmp     loc_180023AAA; jumptable 0000000180023438 case 4
0x18002343f  xor     esi, esi; jumptable 0000000180023438 case 3
0x180023441  mov     r8, [r14+270h]
0x180023448  mov     [rdi+10h], rsi
0x18002344c  lea     r12, [rdi+18h]
0x180023450  mov     [r12], rsi
0x180023454  mov     rdx, [r8+8]
0x180023458  test    rdx, rdx
0x18002345b  jz      loc_180023A7F
0x180023461  mov     eax, [rdx+8]
0x180023464  jmp     short loc_180023470
0x180023466  lea     ecx, [rax+1]
0x180023469  lock cmpxchg [rdx+8], ecx
0x18002346e  jz      short loc_180023479
0x180023470  test    eax, eax
0x180023472  jnz     short loc_180023466
0x180023474  jmp     loc_180023A7F
0x180023479  mov     [rsp+228h+var_180], r12
0x180023481  mov     rax, [r8]
0x180023484  mov     [rdi+10h], rax
0x180023488  mov     rax, [r8+8]
0x18002348c  mov     [r12], rax
0x180023490  mov     edx, [rdi+298h]
0x180023496  mov     eax, edx
0x180023498  mov     r10d, 7
0x18002349e  and     eax, r10d
0x1800234a1  jz      short loc_1800234B0
0x1800234a3  mov     ecx, eax
0x1800234a5  dec     rax
0x1800234a8  test    rcx, rax
0x1800234ab  mov     al, r15b
0x1800234ae  jnz     short loc_1800234B3
0x1800234b0  mov     al, sil
0x1800234b3  mov     rcx, [rsp+228h]; this
0x1800234bb  test    al, al
0x1800234bd  jz      short loc_1800234D1
0x1800234bf  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\sdk\\inc\\wil\\pr"...
0x1800234c6  mov     edx, 91Fh; void *
0x1800234cb  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800234d1  test    r15d, edx
0x1800234d4  jz      short loc_1800234DB
0x1800234d6  mov     ecx, r15d
0x1800234d9  jmp     short loc_1800234ED
0x1800234db  mov     ecx, 2
0x1800234e0  test    ecx, edx
0x1800234e2  jnz     short loc_1800234ED
0x1800234e4  mov     ecx, esi
0x1800234e6  test    r9d, edx
0x1800234e9  cmovnz  ecx, r9d
0x1800234ed  lea     r13, [rdi+20h]
0x1800234f1  mov     eax, ecx
0x1800234f3  or      eax, 20h
0x1800234f6  bt      edx, 4
0x1800234fa  cmovnb  eax, ecx
0x1800234fd  mov     [r13+0], eax
0x180023501  mov     rax, [rdi+2B0h]
0x180023508  test    rax, rax
0x18002350b  jz      loc_180023638
0x180023511  mov     eax, [rax+10h]
0x180023514  nop
0x180023515  test    eax, eax
0x180023517  jz      loc_180023638
0x18002351d  lea     rbx, [rdi+60h]
0x180023521  xorps   xmm0, xmm0
0x180023524  movups  xmmword ptr [rbx], xmm0
0x180023527  mov     [rdi+70h], rsi
0x18002352b  mov     [rdi+78h], r10
0x18002352f  xor     eax, eax
0x180023531  mov     [rbx], ax
0x180023534  mov     [rdi+28h], rsi
0x180023538  mov     [rdi+30h], esi
0x18002353b  mov     dword ptr [rdi+34h], 800704C7h
0x180023542  lea     rcx, [rdi+38h]
0x180023546  movups  xmm1, xmmword ptr [rbx]
0x180023549  movups  [rsp+228h+var_D0], xmm1
0x180023551  movups  xmm0, xmmword ptr [rbx+10h]
0x180023555  movups  [rsp+228h+var_C0], xmm0
0x18002355d  movups  xmmword ptr [rcx], xmm1
0x180023560  movups  xmmword ptr [rcx+10h], xmm0
0x180023564  mov     [rdi+70h], rsi
0x180023568  mov     [rdi+78h], r10
0x18002356c  mov     [rbx], ax
0x18002356f  mov     [rdi+58h], rsi
0x180023573  mov     rax, [rdi+28h]
0x180023577  mov     [rsp+228h+var_108], rax
0x18002357f  mov     [rdi-48h], rax
0x180023583  mov     eax, [rdi+30h]
0x180023586  mov     [rsp+228h+var_100], eax
0x18002358d  mov     [rdi-40h], eax
0x180023590  mov     eax, [rdi+34h]
0x180023593  mov     [rsp+228h+var_FC], eax
0x18002359a  mov     [rdi-3Ch], eax
0x18002359d  movups  xmm1, xmmword ptr [rcx]
0x1800235a0  movups  [rsp+228h+var_F8], xmm1
0x1800235a8  movups  xmm0, xmmword ptr [rcx+10h]
0x1800235ac  movups  [rsp+228h+var_E8], xmm0
0x1800235b4  movups  xmmword ptr [rdi-38h], xmm1
0x1800235b8  movups  xmmword ptr [rdi-28h], xmm0
0x1800235bc  mov     [rdi+48h], rsi
0x1800235c0  mov     [rdi+50h], r10
0x1800235c4  xor     eax, eax
0x1800235c6  mov     [rcx], ax
0x1800235c9  mov     [rdi-18h], rsi
0x1800235cd  mov     [rdi-50h], r15d
0x1800235d1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800235d6  mov     rcx, rbx
0x1800235d9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800235de  nop
0x1800235df  mov     rax, [r12]
0x1800235e3  mov     [rsp+228h+var_198], rax
0x1800235eb  test    rax, rax
0x1800235ee  jz      short loc_180023633
0x1800235f0  mov     rsi, [r12]
0x1800235f4  mov     [rsp+228h+var_198], rsi
0x1800235fc  or      ebx, 0FFFFFFFFh
0x1800235ff  mov     eax, ebx
0x180023601  lock xadd [rsi+8], eax
0x180023606  add     eax, ebx
0x180023608  jnz     short loc_180023633
0x18002360a  mov     rax, [rsi]
0x18002360d  mov     rcx, rsi
0x180023610  mov     rax, [rax]
0x180023613  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023618  mov     eax, ebx
0x18002361a  lock xadd [rsi+0Ch], eax
0x18002361f  add     eax, ebx
0x180023621  jnz     short loc_180023633
0x180023623  mov     rax, [rsi]
0x180023626  mov     rcx, rsi
0x180023629  mov     rax, [rax+8]
0x18002362d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023632  nop
0x180023633  jmp     loc_180023A8F
0x180023638  lea     rbx, [rdi+80h]
0x18002363f  mov     [rsp+228h+var_190], rbx
0x180023647  mov     [rbx], rsi
0x18002364a  lea     rdx, [rdi+0A0h]
0x180023651  mov     rcx, [r8+10h]
0x180023655  call    ?GetCloudStore@SharedCloudStoreState@details@wil@@QEAA?BUCloudStore@Cloud@Storage@Internal@Windows@winrt@@XZ; wil::details::SharedCloudStoreState::GetCloudStore(void)
0x18002365a  mov     [rsp+228h+var_1A8], rax
0x180023662  mov     rcx, [rdi+2A8h]
0x180023669  mov     [rdi+0A8h], rcx
0x180023670  mov     rcx, [rdi+2A0h]
0x180023677  mov     [rdi+0C8h], rcx
0x18002367e  mov     rax, [r13+270h]
0x180023685  mov     [rsp+228h+var_1C8], rax
0x18002368a  lea     rcx, [rdi+108h]
0x180023691  call    ??$GetTypeNameWideString@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@ProfileDataStore@wil@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; wil::ProfileDataStore::GetTypeNameWideString<Windows::Data::Security::Passkey::PasskeyItemPdr>(void)
0x180023696  mov     rcx, rax
0x180023699  mov     rdx, [rax+10h]
0x18002369d  cmp     qword ptr [rax+18h], 7
0x1800236a2  jbe     short loc_1800236A7
0x1800236a4  mov     rcx, [rax]
0x1800236a7  test    edx, edx
0x1800236a9  jnz     short loc_1800236B0
0x1800236ab  mov     rax, rsi
0x1800236ae  jmp     short loc_1800236D6
0x1800236b0  mov     eax, edx
0x1800236b2  cmp     [rcx+rax*2], si
0x1800236b6  jz      short loc_1800236BF
0x1800236b8  call    cs:__imp_abort
0x1800236bf  lea     rax, [rdi+0F0h]
0x1800236c6  mov     [rax], r15d
0x1800236c9  mov     [rdi+0F4h], edx
0x1800236cf  mov     [rdi+100h], rcx
0x1800236d6  mov     [rdi+0E8h], rax
0x1800236dd  lea     r15, [rdi+148h]
0x1800236e4  mov     rdx, [rdi+280h]
0x1800236eb  mov     rcx, r15
0x1800236ee  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800236f3  nop
0x1800236f4  mov     rdx, [rdi+158h]
0x1800236fb  mov     [rsp+228h+var_138], rdx
0x180023703  mov     rax, [rdi+160h]
0x18002370a  mov     [rsp+228h+var_130], rax
0x180023712  cmp     rax, 7
0x180023716  jbe     short loc_180023725
0x180023718  mov     rcx, [r15]
0x18002371b  mov     [rsp+228h+var_148], rcx
0x180023723  jmp     short loc_180023728
0x180023725  mov     rcx, r15
0x180023728  test    edx, edx
0x18002372a  jnz     short loc_180023731
0x18002372c  mov     rax, rsi
0x18002372f  jmp     short loc_18002375A
0x180023731  mov     eax, edx
0x180023733  cmp     [rcx+rax*2], si
0x180023737  jz      short loc_180023740
0x180023739  call    cs:__imp_abort
0x180023740  lea     rax, [rdi+130h]
0x180023747  mov     dword ptr [rax], 1
0x18002374d  mov     [rdi+134h], edx
0x180023753  mov     [rdi+140h], rcx
0x18002375a  mov     [rdi+128h], rax
0x180023761  lea     r15, [rdi+188h]
0x180023768  mov     rdx, [rdi+280h]
0x18002376f  add     rdx, 20h ; ' '
0x180023773  mov     rcx, r15
0x180023776  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002377b  nop
0x18002377c  mov     rdx, [rdi+198h]
0x180023783  mov     [rsp+228h+var_118], rdx
0x18002378b  mov     rax, [rdi+1A0h]
0x180023792  mov     [rsp+228h+var_110], rax
0x18002379a  cmp     rax, 7
0x18002379e  jbe     short loc_1800237AD
0x1800237a0  mov     rcx, [r15]
0x1800237a3  mov     [rsp+228h+var_128], rcx
0x1800237ab  jmp     short loc_1800237B0
0x1800237ad  mov     rcx, r15
0x1800237b0  test    edx, edx
0x1800237b2  jnz     short loc_1800237B9
0x1800237b4  mov     rax, rsi
0x1800237b7  jmp     short loc_1800237E2
0x1800237b9  mov     eax, edx
0x1800237bb  cmp     [rcx+rax*2], si
0x1800237bf  jz      short loc_1800237C8
0x1800237c1  call    cs:__imp_abort
0x1800237c8  lea     rax, [rdi+170h]
0x1800237cf  mov     dword ptr [rax], 1
0x1800237d5  mov     [rdi+174h], edx
0x1800237db  mov     [rdi+180h], rcx
0x1800237e2  mov     [rdi+168h], rax
0x1800237e9  mov     r8, [r14+270h]
0x1800237f0  lea     r9, [rdi+1A8h]
0x1800237f7  mov     rax, [r8+28h]
0x1800237fb  mov     [r9], rax
0x1800237fe  lea     rdx, [rdi+1C8h]
0x180023805  lea     rax, [rdi+0E8h]
0x18002380c  lea     rcx, [rdi+128h]
0x180023813  lea     r10, [rdi+168h]
0x18002381a  add     r8, 20h ; ' '
0x18002381e  lea     r11, [rdi+0A8h]
0x180023825  mov     [rsp+228h+var_1D8], r11
0x18002382a  lea     r11, [rdi+0C8h]
0x180023831  mov     [rsp+228h+var_1E0], r11
0x180023836  mov     [rsp+228h+var_1E8], r13
0x18002383b  mov     r11, [rsp+228h+var_1C8]
0x180023840  mov     [rsp+228h+var_1F0], r11
0x180023845  mov     [rsp+228h+var_1F8], rax
0x18002384a  mov     [rsp+228h+var_200], rcx
0x18002384f  mov     [rsp+228h+var_208], r10
0x180023854  mov     rcx, [rsp+228h+var_1A8]
0x18002385c  call    ?DeleteAsync@?$consume_Windows_Internal_Storage_Cloud_ICloudStore2@UCloudStore@Cloud@Storage@Internal@Windows@winrt@@@impl@winrt@@QEBA@AEBW4PartitionKind@Cloud@Storage@Internal@Windows@3@AEBUhstring@param@3@111_KAEBW4SaveOptions@56783@11@Z; winrt::impl::consume_Windows_Internal_Storage_Cloud_ICloudStore2<winrt::Windows::Internal::Storage::Cloud::CloudStore>::DeleteAsync(winrt::Windows::Internal::Storage::Cloud::PartitionKind const &,winrt::param::hstring const &,winrt::param::hstring const &,winrt::param::hstring const &,winrt::param::hstring const &,unsigned __int64,winrt::Windows::Internal::Storage::Cloud::SaveOptions const &,winrt::param::hstring const &,winrt::param::hstring const &)
0x180023861  nop
0x180023862  lea     r13, [rdi+88h]
0x180023869  mov     r8, rax
0x18002386c  lea     rdx, [rdi+2B0h]
0x180023873  mov     rcx, r13
0x180023876  call    ??0?$AsyncOpWaiter@U?$IAsyncOperation@UCloudStoreSaveResult@Cloud@Storage@Internal@Windows@winrt@@@Foundation@Windows@winrt@@UCloudStoreSaveResult@Cloud@Storage@Internal@34@@details@wil@@QEAA@AEBVcancellation_token@Concurrency@@AEBU?$IAsyncOperation@UCloudStoreSaveResult@Cloud@Storage@Internal@Windows@winrt@@@Foundation@Windows@winrt@@@Z; wil::details::AsyncOpWaiter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>,winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>::AsyncOpWaiter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>,winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>(Concurrency::cancellation_token const &,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult> const &)
0x18002387b  nop
0x18002387c  lea     rcx, [rdi+1C8h]
0x180023883  mov     rax, [rcx]
0x180023886  mov     [rsp+228h+var_178], rax
0x18002388e  test    rax, rax
0x180023891  jz      short loc_180023899
0x180023893  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180023898  nop
0x180023899  mov     rcx, r15
0x18002389c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800238a1  nop
0x1800238a2  lea     rcx, [rdi+148h]
0x1800238a9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800238ae  nop
0x1800238af  lea     rcx, [rdi+108h]
0x1800238b6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800238bb  nop
0x1800238bc  lea     rcx, [rdi+0A0h]
0x1800238c3  mov     rax, [rcx]
0x1800238c6  mov     [rsp+228h+var_170], rax
0x1800238ce  test    rax, rax
  ... truncated ...
```
