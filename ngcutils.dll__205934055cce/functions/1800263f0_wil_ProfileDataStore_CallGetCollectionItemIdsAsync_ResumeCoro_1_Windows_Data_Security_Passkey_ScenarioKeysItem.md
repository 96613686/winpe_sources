# wil::ProfileDataStore::CallGetCollectionItemIdsAsync$_ResumeCoro$1_Windows::Data::Security::Passkey::ScenarioKeysItemPdr_

- ea: `0x1800263f0`
- end: `0x180026d38`
- name: `wil::ProfileDataStore::CallGetCollectionItemIdsAsync$_ResumeCoro$1_Windows::Data::Security::Passkey::ScenarioKeysItemPdr_`
- size: `2376`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180027180`

## callees

- `0x180003080`
- `0x180003520`
- `0x180003c97`
- `0x180003cdf`
- `0x180007a5c`
- `0x18000c95c`
- `0x18000ce74`
- `0x18000f7fc`
- `0x1800263f0`
- `0x180037b84`
- `0x18003ad68`
- `0x1800439bc`
- `0x180045530`
- `0x180045914`
- `0x180049238`
- `0x180049728`
- `0x18004bf18`
- `0x18004c034`
- `0x18004ce6c`
- `0x18004d9d8`
- `0x18004eaac`
- `0x18004ead4`
- `0x18004ed9c`
- `0x180061010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180026cb5`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180026cb5`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800267a5`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180026b32`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800267a5`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180026b32`

## pseudocode

```c
void __fastcall wil::ProfileDataStore::CallGetCollectionItemIdsAsync__ResumeCoro_1_Windows::Data::Security::Passkey::ScenarioKeysItemPdr_(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v4; // r13
  __int16 *v5; // rdx
  _QWORD *v6; // rsi
  __int64 v7; // rdx
  signed __int32 v8; // eax
  signed __int32 v9; // ett
  __int64 v10; // r12
  __int64 v11; // rax
  __int128 v12; // xmm0
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // rax
  __int128 v16; // xmm0
  __int64 v17; // r8
  volatile signed __int32 *v18; // rbx
  __int64 *v19; // rdi
  __int64 *v20; // r12
  int CloudStore; // r11d
  int v22; // r8d
  int v23; // edx
  int v24; // ecx
  int v25; // edx
  int v26; // eax
  int v27; // r8d
  int v28; // edx
  int v29; // ecx
  int v30; // edx
  int v31; // eax
  __int64 v32; // rdx
  __int64 v33; // rcx
  __int64 v34; // rax
  __int64 v35; // r8
  __int64 CollectionItemsAsync; // r8
  __int64 *v37; // rax
  __int64 v38; // rdx
  __int64 v39; // rcx
  __int64 v40; // rax
  const WCHAR *v41; // rdx
  __int64 v42; // r8
  __int64 v43; // rdx
  __int64 v44; // rcx
  __int64 v45; // rax
  __int128 v46; // xmm0
  __int64 v47; // rdx
  __int64 v48; // rcx
  __int64 v49; // rax
  __int128 v50; // xmm0
  __int64 v51; // r8
  volatile signed __int32 *v52; // rbx
  int v53; // eax
  HANDLE ProcessHeap; // rax
  __int64 v55; // rdx
  __int64 v56; // r8
  volatile signed __int32 *v57; // rbx
  int v58; // [rsp+50h] [rbp-1F8h]
  __int64 v59; // [rsp+78h] [rbp-1D0h]
  wil::details::in1diag3 *retaddr; // [rsp+248h] [rbp+0h]

  v4 = a1 + 8;
  v5 = &_ImageBase;
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
        std::wstring::~wstring(a1 - 64, v5, a3);
        std::vector<wil::ProfileDataItemReference<Windows::Data::Security::Passkey::RecoveryItemPdr>>::_Tidy(a1 - 88);
      }
      else if ( *(_DWORD *)(a1 - 96) == 2 )
      {
        __ExceptionPtrDestroy((void *)(a1 - 88));
      }
      `wil::ProfileDataStore::CallGetCollectionItemIdsAsync<Windows::Data::Security::Passkey::RecoveryItemPdr>'::`8'::_parameters_::~_parameters_(v4 + 752);
      if ( *(_WORD *)(a1 + 10) )
        operator delete((void *)(a1 - 112), 0x3A0u);
      return;
    case 2:
      v6 = *(_QWORD **)(a1 + 760);
      *(_QWORD *)(a1 + 16) = 0;
      *(_QWORD *)(a1 + 24) = 0;
      v7 = v6[1];
      if ( !v7 )
        goto LABEL_68;
      v8 = *(_DWORD *)(v7 + 8);
      do
      {
        if ( !v8 )
LABEL_68:
          std::_Throw_bad_weak_ptr();
        v9 = v8;
        v8 = _InterlockedCompareExchange((volatile signed __int32 *)(v7 + 8), v8 + 1, v8);
      }
      while ( v9 != v8 );
      *(_QWORD *)(a1 + 16) = *v6;
      v10 = v6[1];
      *(_QWORD *)(a1 + 24) = v10;
      v11 = *(_QWORD *)(a1 + 800);
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
        v12 = *(_OWORD *)(a1 + 128);
        *(_OWORD *)(a1 + 56) = *(_OWORD *)(a1 + 112);
        *(_OWORD *)(a1 + 72) = v12;
        *(_QWORD *)(a1 + 128) = 0;
        *(_QWORD *)(a1 + 136) = 7;
        *(_WORD *)(a1 + 112) = 0;
        *(_DWORD *)(a1 + 88) = -2147023673;
        *(_QWORD *)(a1 + 96) = 0;
        std::wstring::~wstring(a1 + 112, 0, a3);
        v13 = *(_QWORD *)(a1 + 48);
        *(_QWORD *)(a1 + 48) = 0;
        v14 = *(_QWORD *)(a1 + 40);
        *(_QWORD *)(a1 + 40) = 0;
        v15 = *(_QWORD *)(a1 + 32);
        *(_QWORD *)(a1 + 32) = 0;
        *(_QWORD *)(a1 - 88) = v15;
        *(_QWORD *)(a1 - 80) = v14;
        *(_QWORD *)(a1 - 72) = v13;
        v16 = *(_OWORD *)(a1 + 72);
        *(_OWORD *)(a1 - 64) = *(_OWORD *)(a1 + 56);
        *(_OWORD *)(a1 - 48) = v16;
        *(_QWORD *)(a1 + 72) = 0;
        *(_QWORD *)(a1 + 80) = 7;
        *(_WORD *)(a1 + 56) = 0;
        *(_DWORD *)(a1 - 32) = -2147023673;
        *(_QWORD *)(a1 - 24) = 0;
        *(_DWORD *)(a1 - 96) = 1;
        std::wstring::~wstring(a1 + 56, v13, v17);
        std::vector<wil::ProfileDataItemReference<Windows::Data::Security::Passkey::RecoveryItemPdr>>::_Tidy(a1 + 32);
        std::vector<wil::ProfileDataItemReference<Windows::Data::Security::Passkey::RecoveryItemPdr>>::_Tidy(a1 + 144);
        if ( v10 )
        {
          v18 = *(volatile signed __int32 **)(a1 + 24);
          if ( _InterlockedExchangeAdd(v18 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v18)(v18);
            if ( _InterlockedExchangeAdd(v18 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v18 + 8LL))(v18);
          }
        }
      }
      else
      {
        v19 = (__int64 *)(a1 + 168);
        wil::ProfileDataStore::GetTypeNameWideString<Windows::Data::Security::Passkey::ScenarioKeysItemPdr>(a1 + 168);
        v20 = (__int64 *)(a1 + 200);
        *(_QWORD *)(a1 + 200) = 0;
        CloudStore = wil::details::SharedCloudStoreState::GetCloudStore(v6[2], a1 + 232);
        *(_QWORD *)(a1 + 240) = *(_QWORD *)(a1 + 792);
        *(_QWORD *)(a1 + 272) = *(_QWORD *)(a1 + 784);
        v22 = *(_DWORD *)(a1 + 780);
        v23 = v22 & 1 | 2;
        if ( (v22 & 2) == 0 )
          v23 = *(_DWORD *)(a1 + 780) & 1;
        v24 = v23 | 4;
        if ( (v22 & 4) == 0 )
          v24 = v23;
        v25 = v24 | 0x10;
        if ( (v22 & 0x10) == 0 )
          v25 = v24;
        v26 = v25 | 8;
        if ( (v22 & 8) == 0 )
          v26 = v25;
        *(_DWORD *)(a1 + 304) = v26 | 0x20;
        v27 = *(_DWORD *)(a1 + 776);
        v28 = v27 & 1;
        if ( (v27 & 4) != 0 )
        {
          if ( (v27 & 1) == 0 )
            wil::details::in1diag3::_FailFast_Unexpected(
              retaddr,
              (void *)0x8FE,
              (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil\\profiledatastore.h",
              (const char *)4);
          v28 |= 2u;
        }
        v29 = v28 | 4;
        if ( (v27 & 8) == 0 )
          v29 = v28;
        v30 = v29 | 8;
        if ( (v27 & 0x10) == 0 )
          v30 = v29;
        v31 = v30 | 0x10;
        if ( (v27 & 0x20) == 0 )
          v31 = v30;
        *(_DWORD *)(a1 + 308) = v31;
        v32 = *(_QWORD *)(a1 + 184);
        if ( *(_QWORD *)(a1 + 192) <= 7u )
          v33 = a1 + 168;
        else
          v33 = *v19;
        if ( (_DWORD)v32 )
        {
          if ( *(_WORD *)(v33 + 2LL * (unsigned int)v32) )
            abort();
          v34 = a1 + 320;
          *(_DWORD *)(a1 + 320) = 1;
          *(_DWORD *)(a1 + 324) = v32;
          *(_QWORD *)(a1 + 336) = v33;
        }
        else
        {
          v34 = 0;
        }
        *(_QWORD *)(a1 + 312) = v34;
        *(_QWORD *)(a1 + 344) = *(_QWORD *)(a1 + 768);
        v35 = *(_QWORD *)(v4 + 752);
        *(_QWORD *)(a1 + 376) = *(_QWORD *)(v35 + 40);
        CollectionItemsAsync = winrt::impl::consume_Windows_Internal_Storage_Cloud_ICloudStore2<winrt::Windows::Internal::Storage::Cloud::CloudStore>::GetCollectionItemsAsync(
                                 CloudStore,
                                 (int)a1 + 408,
                                 (int)v35 + 32,
                                 (int)a1 + 376,
                                 a1 + 344,
                                 a1 + 312,
                                 a1 + 308,
                                 a1 + 304,
                                 a1 + 272,
                                 a1 + 240);
        wil::details::AsyncOpWaiter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::GetCollectionItemsResult>,winrt::Windows::Internal::Storage::Cloud::GetCollectionItemsResult>::AsyncOpWaiter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::GetCollectionItemsResult>,winrt::Windows::Internal::Storage::Cloud::GetCollectionItemsResult>(
          a1 + 208,
          a1 + 800,
          CollectionItemsAsync);
        if ( *(_QWORD *)(a1 + 408) )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 408);
        if ( *(_QWORD *)(a1 + 232) )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 232);
        v37 = (__int64 *)wil::details::AsyncOpWaiter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::GetCollectionItemsResult>,winrt::Windows::Internal::Storage::Cloud::GetCollectionItemsResult>::WaitForResult(
                           a1 + 208,
                           a1 + 416);
        if ( v20 != v37 )
        {
          v38 = *v37;
          *v37 = 0;
          *v20 = v38;
        }
        if ( *(_QWORD *)(a1 + 416) )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 416);
        wil::details::AsyncOpWaiter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>,winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>::~AsyncOpWaiter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>,winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>(a1 + 208);
        v39 = *v20;
        *(_QWORD *)(a1 + 568) = *v20;
        if ( v39 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 8LL))(v39);
        wil::ProfileDataStore::MakeCloudStoreReferenceVector<Windows::Data::Security::Passkey::PasskeyItemPdr>(
          (_QWORD *)(a1 + 576),
          (_QWORD *)(a1 + 568),
          a1 + 168);
        v59 = winrt::impl::consume_Windows_Internal_Storage_Cloud_IGetCollectionItemsResult<winrt::Windows::Internal::Storage::Cloud::IGetCollectionItemsResult>::RetryAfter(a1 + 200);
        v58 = *(_DWORD *)winrt::impl::consume_Windows_Internal_Storage_Cloud_IGetCollectionItemsResult<winrt::Windows::Internal::Storage::Cloud::IGetCollectionItemsResult>::ResultCode(
                           a1 + 200,
                           a1 + 688);
        v40 = winrt::impl::consume_Windows_Internal_Storage_Cloud_IGetCollectionItemsResult<winrt::Windows::Internal::Storage::Cloud::IGetCollectionItemsResult>::SyncToken(
                a1 + 200,
                a1 + 728);
        if ( *(_QWORD *)v40 )
          v41 = *(const WCHAR **)(*(_QWORD *)v40 + 16LL);
        else
          v41 = &String1;
        *(_OWORD *)(a1 + 696) = 0;
        *(_QWORD *)(a1 + 712) = 0;
        *(_QWORD *)(a1 + 720) = 0;
        v42 = -1;
        do
          ++v42;
        while ( v41[v42] );
        std::wstring::_Construct<1,unsigned short const *>(a1 + 696, v41, v42);
        v43 = *(_QWORD *)(a1 + 592);
        *(_QWORD *)(a1 + 592) = 0;
        v44 = *(_QWORD *)(a1 + 584);
        *(_QWORD *)(a1 + 584) = 0;
        v45 = *(_QWORD *)(a1 + 576);
        *(_QWORD *)(a1 + 576) = 0;
        *(_QWORD *)(a1 + 608) = v45;
        *(_QWORD *)(a1 + 616) = v44;
        *(_QWORD *)(a1 + 624) = v43;
        v46 = *(_OWORD *)(a1 + 712);
        *(_OWORD *)(a1 + 632) = *(_OWORD *)(a1 + 696);
        *(_OWORD *)(a1 + 648) = v46;
        *(_QWORD *)(a1 + 712) = 0;
        *(_QWORD *)(a1 + 720) = 7;
        *(_WORD *)(a1 + 696) = 0;
        *(_DWORD *)(a1 + 664) = v58;
        *(_QWORD *)(a1 + 672) = v59;
        std::wstring::~wstring(a1 + 696, v43, a1 + 576);
        v47 = *(_QWORD *)(a1 + 624);
        *(_QWORD *)(a1 + 624) = 0;
        v48 = *(_QWORD *)(a1 + 616);
        *(_QWORD *)(a1 + 616) = 0;
        v49 = *(_QWORD *)(a1 + 608);
        *(_QWORD *)(a1 + 608) = 0;
        *(_QWORD *)(a1 - 88) = v49;
        *(_QWORD *)(a1 - 80) = v48;
        *(_QWORD *)(a1 - 72) = v47;
        v50 = *(_OWORD *)(a1 + 648);
        *(_OWORD *)(a1 - 64) = *(_OWORD *)(a1 + 632);
        *(_OWORD *)(a1 - 48) = v50;
        *(_QWORD *)(a1 + 648) = 0;
        *(_QWORD *)(a1 + 656) = 7;
        *(_WORD *)(a1 + 632) = 0;
        *(_DWORD *)(a1 - 32) = *(_DWORD *)(a1 + 664);
        *(_QWORD *)(a1 - 24) = *(_QWORD *)(a1 + 672);
        *(_DWORD *)(a1 - 96) = 1;
        std::wstring::~wstring(a1 + 632, v47, v51);
        std::vector<wil::ProfileDataItemReference<Windows::Data::Security::Passkey::RecoveryItemPdr>>::_Tidy(a1 + 608);
        v52 = *(volatile signed __int32 **)(a1 + 728);
        if ( v52 )
        {
          v53 = _InterlockedDecrement(v52 + 6);
          if ( v53 )
          {
            if ( v53 < 0 )
              abort();
          }
          else
          {
            ProcessHeap = WINRT_IMPL_GetProcessHeap();
            WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v52);
          }
          *(_QWORD *)(a1 + 728) = 0;
        }
        std::vector<wil::ProfileDataItemReference<Windows::Data::Security::Passkey::RecoveryItemPdr>>::_Tidy(a1 + 576);
        if ( *v20 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 200);
        std::wstring::~wstring(a1 + 168, v55, v56);
        if ( *(_QWORD *)(a1 + 24) )
        {
          v57 = *(volatile signed __int32 **)(a1 + 24);
          if ( _InterlockedExchangeAdd(v57 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v57)(v57);
            if ( _InterlockedExchangeAdd(v57 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v57 + 8LL))(v57);
          }
        }
      }
      *(_QWORD *)(a1 + 736) = a1 - 112;
      *(_WORD *)v4 = 0;
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
0x1800263f0  mov     r11, rsp
0x1800263f3  mov     [r11+10h], rbx
0x1800263f7  mov     [r11+18h], rsi
0x1800263fb  mov     [r11+8], rcx
0x1800263ff  push    rdi
0x180026400  push    r12
0x180026402  push    r13
0x180026404  push    r14
0x180026406  push    r15
0x180026408  sub     rsp, 220h
0x18002640f  mov     rax, cs:__security_cookie
0x180026416  xor     rax, rsp
0x180026419  mov     [rsp+248h+var_38], rax
0x180026421  mov     r14, rcx
0x180026424  mov     [rsp+248h+var_1F0], rcx
0x180026429  lea     r13, [r14+8]
0x18002642d  movzx   eax, word ptr [r13+0]
0x180026432  mov     [rsp+248h+var_1D8], ax
0x180026437  inc     ax; switch 5 cases
0x18002643a  mov     ecx, 4
0x18002643f  cmp     ax, cx
0x180026442  ja      def_180026465; jumptable 0000000180026465 default case, case 0
0x180026448  mov     [rsp+248h+var_1C0], r13
0x180026450  movsx   rax, ax
0x180026454  lea     rdx, __ImageBase
0x18002645b  mov     ecx, ds:(jpt_180026465 - 180000000h)[rdx+rax*4]
0x180026462  add     rcx, rdx
0x180026465  jmp     rcx; switch jump
0x180026467  jmp     loc_180026C82; jumptable 0000000180026465 case 3
0x18002646c  xor     r15d, r15d; jumptable 0000000180026465 case 2
0x18002646f  mov     rsi, [r13+2F0h]
0x180026476  mov     [r14+10h], r15
0x18002647a  lea     rbx, [r14+18h]
0x18002647e  mov     [rbx], r15
0x180026481  mov     rdx, [rsi+8]
0x180026485  test    rdx, rdx
0x180026488  jz      loc_180026C53
0x18002648e  mov     eax, [rdx+8]
0x180026491  jmp     short loc_18002649D
0x180026493  lea     ecx, [rax+1]
0x180026496  lock cmpxchg [rdx+8], ecx
0x18002649b  jz      short loc_1800264A6
0x18002649d  test    eax, eax
0x18002649f  jnz     short loc_180026493
0x1800264a1  jmp     loc_180026C53
0x1800264a6  mov     [rsp+248h+var_1E8], rbx
0x1800264ab  mov     rax, [rsi]
0x1800264ae  mov     [r14+10h], rax
0x1800264b2  mov     r12, [rsi+8]
0x1800264b6  mov     [rbx], r12
0x1800264b9  mov     rax, [r14+320h]
0x1800264c0  test    rax, rax
0x1800264c3  jz      loc_180026653
0x1800264c9  mov     eax, [rax+10h]
0x1800264cc  nop
0x1800264cd  test    eax, eax
0x1800264cf  jz      loc_180026653
0x1800264d5  lea     rcx, [r14+70h]
0x1800264d9  xorps   xmm0, xmm0
0x1800264dc  movups  xmmword ptr [rcx], xmm0
0x1800264df  mov     [r14+80h], r15
0x1800264e6  mov     eax, 7
0x1800264eb  mov     [r14+88h], rax
0x1800264f2  xor     edx, edx
0x1800264f4  mov     [rcx], dx
0x1800264f7  mov     [r14+0A0h], r15
0x1800264fe  mov     [r14+98h], r15
0x180026505  lea     rsi, [r14+90h]
0x18002650c  mov     [rsi], r15
0x18002650f  lea     rdi, [r14+20h]
0x180026513  mov     [rdi], r15
0x180026516  mov     [r14+28h], r15
0x18002651a  mov     [r14+30h], r15
0x18002651e  lea     rbx, [r14+38h]
0x180026522  movups  xmm1, xmmword ptr [rcx]
0x180026525  movups  [rsp+248h+var_158], xmm1
0x18002652d  movups  xmm0, xmmword ptr [rcx+10h]
0x180026531  movups  [rsp+248h+var_148], xmm0
0x180026539  movups  xmmword ptr [rbx], xmm1
0x18002653c  movups  xmmword ptr [rbx+10h], xmm0
0x180026540  mov     [r14+80h], r15
0x180026547  mov     [r14+88h], rax
0x18002654e  xor     eax, eax
0x180026550  mov     [rcx], ax
0x180026553  mov     dword ptr [r14+58h], 800704C7h
0x18002655b  mov     [r14+60h], r15
0x18002655f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180026564  mov     rdx, [r14+30h]
0x180026568  mov     [rsp+248h+var_B8], rdx
0x180026570  mov     [r14+30h], r15
0x180026574  mov     rcx, [r14+28h]
0x180026578  mov     [rsp+248h+var_C0], rcx
0x180026580  mov     [r14+28h], r15
0x180026584  mov     rax, [rdi]
0x180026587  mov     [rsp+248h+var_C8], rax
0x18002658f  mov     [rdi], r15
0x180026592  mov     [r14-58h], rax
0x180026596  mov     [r14-50h], rcx
0x18002659a  mov     [r14-48h], rdx
0x18002659e  movups  xmm1, xmmword ptr [rbx]
0x1800265a1  movups  [rsp+248h+var_B0], xmm1
0x1800265a9  movups  xmm0, xmmword ptr [rbx+10h]
0x1800265ad  movups  [rsp+248h+var_A0], xmm0
0x1800265b5  movups  xmmword ptr [r14-40h], xmm1
0x1800265ba  movups  xmmword ptr [r14-30h], xmm0
0x1800265bf  mov     [r14+48h], r15
0x1800265c3  mov     qword ptr [r14+50h], 7
0x1800265cb  xor     eax, eax
0x1800265cd  mov     [rbx], ax
0x1800265d0  mov     dword ptr [r14-20h], 800704C7h
0x1800265d8  mov     [r14-18h], r15
0x1800265dc  mov     dword ptr [r14-60h], 1
0x1800265e4  mov     rcx, rbx
0x1800265e7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800265ec  mov     rcx, rdi
0x1800265ef  call    ?_Tidy@?$vector@V?$ProfileDataItemReference@URecoveryItemPdr@Passkey@Security@Data@Windows@@@wil@@V?$allocator@V?$ProfileDataItemReference@URecoveryItemPdr@Passkey@Security@Data@Windows@@@wil@@@std@@@std@@AEAAXXZ; std::vector<wil::ProfileDataItemReference<Windows::Data::Security::Passkey::RecoveryItemPdr>>::_Tidy(void)
0x1800265f4  mov     rcx, rsi
0x1800265f7  call    ?_Tidy@?$vector@V?$ProfileDataItemReference@URecoveryItemPdr@Passkey@Security@Data@Windows@@@wil@@V?$allocator@V?$ProfileDataItemReference@URecoveryItemPdr@Passkey@Security@Data@Windows@@@wil@@@std@@@std@@AEAAXXZ; std::vector<wil::ProfileDataItemReference<Windows::Data::Security::Passkey::RecoveryItemPdr>>::_Tidy(void)
0x1800265fc  nop
0x1800265fd  mov     [rsp+248h+var_1B0], r12
0x180026605  test    r12, r12
0x180026608  jz      short loc_18002664E
0x18002660a  mov     rbx, [r14+18h]
0x18002660e  mov     [rsp+248h+var_1B0], rbx
0x180026616  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18002661a  mov     eax, esi
0x18002661c  lock xadd [rbx+8], eax
0x180026621  add     eax, esi
0x180026623  jnz     short loc_18002664E
0x180026625  mov     rax, [rbx]
0x180026628  mov     rcx, rbx
0x18002662b  mov     rax, [rax]
0x18002662e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026633  mov     eax, esi
0x180026635  lock xadd [rbx+0Ch], eax
0x18002663a  add     eax, esi
0x18002663c  jnz     short loc_18002664E
0x18002663e  mov     rax, [rbx]
0x180026641  mov     rcx, rbx
0x180026644  mov     rax, [rax+8]
0x180026648  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002664d  nop
0x18002664e  jmp     loc_180026C66
0x180026653  lea     rdi, [r14+0A8h]
0x18002665a  mov     [rsp+248h+var_1F8], rdi
0x18002665f  mov     rcx, rdi
0x180026662  call    ??$GetTypeNameWideString@UScenarioKeysItemPdr@Passkey@Security@Data@Windows@@@ProfileDataStore@wil@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; wil::ProfileDataStore::GetTypeNameWideString<Windows::Data::Security::Passkey::ScenarioKeysItemPdr>(void)
0x180026667  nop
0x180026668  lea     r12, [r14+0C8h]
0x18002666f  mov     [rsp+248h+var_1D0], r12
0x180026674  mov     [r12], r15
0x180026678  lea     rdx, [r14+0E8h]
0x18002667f  mov     rcx, [rsi+10h]
0x180026683  call    ?GetCloudStore@SharedCloudStoreState@details@wil@@QEAA?BUCloudStore@Cloud@Storage@Internal@Windows@winrt@@XZ; wil::details::SharedCloudStoreState::GetCloudStore(void)
0x180026688  mov     r11, rax
0x18002668b  lea     rsi, [r14+0F0h]
0x180026692  mov     rcx, [r14+318h]
0x180026699  mov     [rsi], rcx
0x18002669c  mov     rcx, [r14+310h]
0x1800266a3  mov     [r14+110h], rcx
0x1800266aa  mov     r8d, [r14+30Ch]
0x1800266b1  mov     ecx, r8d
0x1800266b4  and     ecx, 1
0x1800266b7  mov     edx, ecx
0x1800266b9  or      edx, 2
0x1800266bc  bt      r8d, 1
0x1800266c1  cmovnb  edx, ecx
0x1800266c4  mov     r9d, 4; char *
0x1800266ca  mov     ecx, edx
0x1800266cc  or      ecx, r9d
0x1800266cf  test    r9d, r8d
0x1800266d2  cmovz   ecx, edx
0x1800266d5  mov     edx, ecx
0x1800266d7  or      edx, 10h
0x1800266da  bt      r8d, 4
0x1800266df  cmovnb  edx, ecx
0x1800266e2  mov     eax, edx
0x1800266e4  or      eax, 8
0x1800266e7  bt      r8d, 3
0x1800266ec  cmovnb  eax, edx
0x1800266ef  or      eax, 20h
0x1800266f2  mov     [r14+130h], eax
0x1800266f9  mov     r8d, [rbx+2F0h]
0x180026700  mov     edx, r8d
0x180026703  and     edx, 1
0x180026706  test    r9d, r8d
0x180026709  jz      short loc_18002672E
0x18002670b  mov     rcx, [rsp+248h]; this
0x180026713  mov     al, dl
0x180026715  xor     al, 1
0x180026717  jz      short loc_18002672B
0x180026719  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\sdk\\inc\\wil\\pr"...
0x180026720  mov     edx, 8FEh; void *
0x180026725  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18002672b  or      edx, 2
0x18002672e  mov     ecx, edx
0x180026730  or      ecx, r9d
0x180026733  bt      r8d, 3
0x180026738  cmovnb  ecx, edx
0x18002673b  mov     edx, ecx
0x18002673d  or      edx, 8
0x180026740  bt      r8d, 4
0x180026745  cmovnb  edx, ecx
0x180026748  lea     r10, [r14+134h]
0x18002674f  mov     eax, edx
0x180026751  or      eax, 10h
0x180026754  bt      r8d, 5
0x180026759  cmovnb  eax, edx
0x18002675c  mov     [r10], eax
0x18002675f  mov     rdx, [r14+0B8h]
0x180026766  mov     [rsp+248h+var_D8], rdx
0x18002676e  mov     rax, [r14+0C0h]
0x180026775  mov     [rsp+248h+var_D0], rax
0x18002677d  cmp     rax, 7
0x180026781  jbe     short loc_180026790
0x180026783  mov     rcx, [rdi]
0x180026786  mov     [rsp+248h+var_E8], rcx
0x18002678e  jmp     short loc_180026793
0x180026790  mov     rcx, rdi
0x180026793  test    edx, edx
0x180026795  jnz     short loc_18002679C
0x180026797  mov     rax, r15
0x18002679a  jmp     short loc_1800267C7
0x18002679c  mov     eax, edx
0x18002679e  cmp     [rcx+rax*2], r15w
0x1800267a3  jz      short loc_1800267AC
0x1800267a5  call    cs:__imp_abort
0x1800267ac  lea     rax, [r14+140h]
0x1800267b3  mov     dword ptr [rax], 1
0x1800267b9  mov     [r14+144h], edx
0x1800267c0  mov     [r14+150h], rcx
0x1800267c7  mov     [r14+138h], rax
0x1800267ce  lea     rcx, [r14+158h]
0x1800267d5  mov     rax, [r14+300h]
0x1800267dc  mov     [rcx], rax
0x1800267df  mov     r8, [r13+2F0h]
0x1800267e6  lea     r9, [r14+178h]
0x1800267ed  mov     rax, [r8+28h]
0x1800267f1  mov     [r9], rax
0x1800267f4  lea     rbx, [r14+198h]
0x1800267fb  lea     rax, [r14+138h]
0x180026802  add     r8, 20h ; ' '
0x180026806  mov     [rsp+248h+var_200], rsi
0x18002680b  lea     rdx, [r14+110h]
0x180026812  mov     [rsp+248h+var_208], rdx
0x180026817  lea     rdx, [r14+130h]
0x18002681e  mov     [rsp+248h+var_210], rdx
0x180026823  mov     [rsp+248h+var_218], r10
0x180026828  mov     [rsp+248h+var_220], rax
0x18002682d  mov     [rsp+248h+var_228], rcx
0x180026832  mov     rdx, rbx
0x180026835  mov     rcx, r11
0x180026838  call    ?GetCollectionItemsAsync@?$consume_Windows_Internal_Storage_Cloud_ICloudStore2@UCloudStore@Cloud@Storage@Internal@Windows@winrt@@@impl@winrt@@QEBA@AEBW4PartitionKind@Cloud@Storage@Internal@Windows@3@AEBUhstring@param@3@11AEBW4LoadOptions@56783@AEBW4CollectionOptions@56783@11@Z; winrt::impl::consume_Windows_Internal_Storage_Cloud_ICloudStore2<winrt::Windows::Internal::Storage::Cloud::CloudStore>::GetCollectionItemsAsync(winrt::Windows::Internal::Storage::Cloud::PartitionKind const &,winrt::param::hstring const &,winrt::param::hstring const &,winrt::param::hstring const &,winrt::Windows::Internal::Storage::Cloud::LoadOptions const &,winrt::Windows::Internal::Storage::Cloud::CollectionOptions const &,winrt::param::hstring const &,winrt::param::hstring const &)
0x18002683d  nop
0x18002683e  lea     rsi, [r14+0D0h]
0x180026845  mov     r8, rax
0x180026848  lea     rdx, [r14+320h]
0x18002684f  mov     rcx, rsi
0x180026852  call    ??0?$AsyncOpWaiter@U?$IAsyncOperation@UGetCollectionItemsResult@Cloud@Storage@Internal@Windows@winrt@@@Foundation@Windows@winrt@@UGetCollectionItemsResult@Cloud@Storage@Internal@34@@details@wil@@QEAA@AEBVcancellation_token@Concurrency@@AEBU?$IAsyncOperation@UGetCollectionItemsResult@Cloud@Storage@Internal@Windows@winrt@@@Foundation@Windows@winrt@@@Z; wil::details::AsyncOpWaiter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::GetCollectionItemsResult>,winrt::Windows::Internal::Storage::Cloud::GetCollectionItemsResult>::AsyncOpWaiter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::GetCollectionItemsResult>,winrt::Windows::Internal::Storage::Cloud::GetCollectionItemsResult>(Concurrency::cancellation_token const &,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::GetCollectionItemsResult> const &)
0x180026857  nop
0x180026858  mov     rax, [rbx]
0x18002685b  mov     [rsp+248h+var_188], rax
0x180026863  test    rax, rax
0x180026866  jz      short loc_180026871
0x180026868  mov     rcx, rbx
0x18002686b  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180026870  nop
0x180026871  lea     rcx, [r14+0E8h]
0x180026878  mov     rax, [rcx]
0x18002687b  mov     [rsp+248h+var_180], rax
0x180026883  test    rax, rax
0x180026886  jz      short loc_18002688D
0x180026888  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18002688d  lea     rbx, [r14+1A0h]
0x180026894  mov     rdx, rbx
0x180026897  mov     rcx, rsi
0x18002689a  call    ?WaitForResult@?$AsyncOpWaiter@U?$IAsyncOperation@UGetCollectionItemsResult@Cloud@Storage@Internal@Windows@winrt@@@Foundation@Windows@winrt@@UGetCollectionItemsResult@Cloud@Storage@Internal@34@@details@wil@@QEAA?AUGetCollectionItemsResult@Cloud@Storage@Internal@Windows@winrt@@XZ; wil::details::AsyncOpWaiter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::GetCollectionItemsResult>,winrt::Windows::Internal::Storage::Cloud::GetCollectionItemsResult>::WaitForResult(void)
0x18002689f  cmp     r12, rax
0x1800268a2  jz      short loc_1800268AE
0x1800268a4  mov     rdx, [rax]
0x1800268a7  mov     [rax], r15
0x1800268aa  mov     [r12], rdx
0x1800268ae  mov     rax, [rbx]
0x1800268b1  mov     [rsp+248h+var_178], rax
0x1800268b9  test    rax, rax
0x1800268bc  jz      short loc_1800268C7
0x1800268be  mov     rcx, rbx
0x1800268c1  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800268c6  nop
0x1800268c7  mov     rcx, rsi
0x1800268ca  call    ??1?$AsyncOpWaiter@U?$IAsyncOperation@UCloudStoreSaveResult@Cloud@Storage@Internal@Windows@winrt@@@Foundation@Windows@winrt@@UCloudStoreSaveResult@Cloud@Storage@Internal@34@@details@wil@@QEAA@XZ; wil::details::AsyncOpWaiter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>,winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>::~AsyncOpWaiter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>,winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>(void)
0x1800268cf  nop
0x1800268d0  lea     rbx, [r14+238h]
0x1800268d7  mov     rcx, [r12]
0x1800268db  mov     [rsp+248h+var_1C8], rcx
0x1800268e3  mov     [rbx], rcx
0x1800268e6  test    rcx, rcx
0x1800268e9  jz      short loc_1800268F7
0x1800268eb  mov     rax, [rcx]
0x1800268ee  mov     rax, [rax+8]
  ... truncated ...
```
