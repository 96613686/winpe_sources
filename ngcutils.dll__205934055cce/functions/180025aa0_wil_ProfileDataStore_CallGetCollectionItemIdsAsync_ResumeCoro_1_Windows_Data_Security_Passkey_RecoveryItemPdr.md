# wil::ProfileDataStore::CallGetCollectionItemIdsAsync$_ResumeCoro$1_Windows::Data::Security::Passkey::RecoveryItemPdr_

- ea: `0x180025aa0`
- end: `0x1800263e8`
- name: `wil::ProfileDataStore::CallGetCollectionItemIdsAsync$_ResumeCoro$1_Windows::Data::Security::Passkey::RecoveryItemPdr_`
- size: `2376`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180026f60`

## callees

- `0x180003080`
- `0x180003520`
- `0x180003c97`
- `0x180003cdf`
- `0x180007a5c`
- `0x18000c95c`
- `0x18000ce74`
- `0x18000f7fc`
- `0x180025aa0`
- `0x180037a3c`
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

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180026365`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180026365`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180025e55`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800261e2`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180025e55`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800261e2`

## pseudocode

```c
void __fastcall wil::ProfileDataStore::CallGetCollectionItemIdsAsync__ResumeCoro_1_Windows::Data::Security::Passkey::RecoveryItemPdr_(
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
        wil::ProfileDataStore::GetTypeNameWideString<Windows::Data::Security::Passkey::RecoveryItemPdr>(a1 + 168);
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
0x180025aa0  mov     r11, rsp
0x180025aa3  mov     [r11+10h], rbx
0x180025aa7  mov     [r11+18h], rsi
0x180025aab  mov     [r11+8], rcx
0x180025aaf  push    rdi
0x180025ab0  push    r12
0x180025ab2  push    r13
0x180025ab4  push    r14
0x180025ab6  push    r15
0x180025ab8  sub     rsp, 220h
0x180025abf  mov     rax, cs:__security_cookie
0x180025ac6  xor     rax, rsp
0x180025ac9  mov     [rsp+248h+var_38], rax
0x180025ad1  mov     r14, rcx
0x180025ad4  mov     [rsp+248h+var_1F0], rcx
0x180025ad9  lea     r13, [r14+8]
0x180025add  movzx   eax, word ptr [r13+0]
0x180025ae2  mov     [rsp+248h+var_1D8], ax
0x180025ae7  inc     ax; switch 5 cases
0x180025aea  mov     ecx, 4
0x180025aef  cmp     ax, cx
0x180025af2  ja      def_180025B15; jumptable 0000000180025B15 default case, case 0
0x180025af8  mov     [rsp+248h+var_1C0], r13
0x180025b00  movsx   rax, ax
0x180025b04  lea     rdx, __ImageBase
0x180025b0b  mov     ecx, ds:(jpt_180025B15 - 180000000h)[rdx+rax*4]
0x180025b12  add     rcx, rdx
0x180025b15  jmp     rcx; switch jump
0x180025b17  jmp     loc_180026332; jumptable 0000000180025B15 case 3
0x180025b1c  xor     r15d, r15d; jumptable 0000000180025B15 case 2
0x180025b1f  mov     rsi, [r13+2F0h]
0x180025b26  mov     [r14+10h], r15
0x180025b2a  lea     rbx, [r14+18h]
0x180025b2e  mov     [rbx], r15
0x180025b31  mov     rdx, [rsi+8]
0x180025b35  test    rdx, rdx
0x180025b38  jz      loc_180026303
0x180025b3e  mov     eax, [rdx+8]
0x180025b41  jmp     short loc_180025B4D
0x180025b43  lea     ecx, [rax+1]
0x180025b46  lock cmpxchg [rdx+8], ecx
0x180025b4b  jz      short loc_180025B56
0x180025b4d  test    eax, eax
0x180025b4f  jnz     short loc_180025B43
0x180025b51  jmp     loc_180026303
0x180025b56  mov     [rsp+248h+var_1E8], rbx
0x180025b5b  mov     rax, [rsi]
0x180025b5e  mov     [r14+10h], rax
0x180025b62  mov     r12, [rsi+8]
0x180025b66  mov     [rbx], r12
0x180025b69  mov     rax, [r14+320h]
0x180025b70  test    rax, rax
0x180025b73  jz      loc_180025D03
0x180025b79  mov     eax, [rax+10h]
0x180025b7c  nop
0x180025b7d  test    eax, eax
0x180025b7f  jz      loc_180025D03
0x180025b85  lea     rcx, [r14+70h]
0x180025b89  xorps   xmm0, xmm0
0x180025b8c  movups  xmmword ptr [rcx], xmm0
0x180025b8f  mov     [r14+80h], r15
0x180025b96  mov     eax, 7
0x180025b9b  mov     [r14+88h], rax
0x180025ba2  xor     edx, edx
0x180025ba4  mov     [rcx], dx
0x180025ba7  mov     [r14+0A0h], r15
0x180025bae  mov     [r14+98h], r15
0x180025bb5  lea     rsi, [r14+90h]
0x180025bbc  mov     [rsi], r15
0x180025bbf  lea     rdi, [r14+20h]
0x180025bc3  mov     [rdi], r15
0x180025bc6  mov     [r14+28h], r15
0x180025bca  mov     [r14+30h], r15
0x180025bce  lea     rbx, [r14+38h]
0x180025bd2  movups  xmm1, xmmword ptr [rcx]
0x180025bd5  movups  [rsp+248h+var_158], xmm1
0x180025bdd  movups  xmm0, xmmword ptr [rcx+10h]
0x180025be1  movups  [rsp+248h+var_148], xmm0
0x180025be9  movups  xmmword ptr [rbx], xmm1
0x180025bec  movups  xmmword ptr [rbx+10h], xmm0
0x180025bf0  mov     [r14+80h], r15
0x180025bf7  mov     [r14+88h], rax
0x180025bfe  xor     eax, eax
0x180025c00  mov     [rcx], ax
0x180025c03  mov     dword ptr [r14+58h], 800704C7h
0x180025c0b  mov     [r14+60h], r15
0x180025c0f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180025c14  mov     rdx, [r14+30h]
0x180025c18  mov     [rsp+248h+var_B8], rdx
0x180025c20  mov     [r14+30h], r15
0x180025c24  mov     rcx, [r14+28h]
0x180025c28  mov     [rsp+248h+var_C0], rcx
0x180025c30  mov     [r14+28h], r15
0x180025c34  mov     rax, [rdi]
0x180025c37  mov     [rsp+248h+var_C8], rax
0x180025c3f  mov     [rdi], r15
0x180025c42  mov     [r14-58h], rax
0x180025c46  mov     [r14-50h], rcx
0x180025c4a  mov     [r14-48h], rdx
0x180025c4e  movups  xmm1, xmmword ptr [rbx]
0x180025c51  movups  [rsp+248h+var_B0], xmm1
0x180025c59  movups  xmm0, xmmword ptr [rbx+10h]
0x180025c5d  movups  [rsp+248h+var_A0], xmm0
0x180025c65  movups  xmmword ptr [r14-40h], xmm1
0x180025c6a  movups  xmmword ptr [r14-30h], xmm0
0x180025c6f  mov     [r14+48h], r15
0x180025c73  mov     qword ptr [r14+50h], 7
0x180025c7b  xor     eax, eax
0x180025c7d  mov     [rbx], ax
0x180025c80  mov     dword ptr [r14-20h], 800704C7h
0x180025c88  mov     [r14-18h], r15
0x180025c8c  mov     dword ptr [r14-60h], 1
0x180025c94  mov     rcx, rbx
0x180025c97  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180025c9c  mov     rcx, rdi
0x180025c9f  call    ?_Tidy@?$vector@V?$ProfileDataItemReference@URecoveryItemPdr@Passkey@Security@Data@Windows@@@wil@@V?$allocator@V?$ProfileDataItemReference@URecoveryItemPdr@Passkey@Security@Data@Windows@@@wil@@@std@@@std@@AEAAXXZ; std::vector<wil::ProfileDataItemReference<Windows::Data::Security::Passkey::RecoveryItemPdr>>::_Tidy(void)
0x180025ca4  mov     rcx, rsi
0x180025ca7  call    ?_Tidy@?$vector@V?$ProfileDataItemReference@URecoveryItemPdr@Passkey@Security@Data@Windows@@@wil@@V?$allocator@V?$ProfileDataItemReference@URecoveryItemPdr@Passkey@Security@Data@Windows@@@wil@@@std@@@std@@AEAAXXZ; std::vector<wil::ProfileDataItemReference<Windows::Data::Security::Passkey::RecoveryItemPdr>>::_Tidy(void)
0x180025cac  nop
0x180025cad  mov     [rsp+248h+var_1B0], r12
0x180025cb5  test    r12, r12
0x180025cb8  jz      short loc_180025CFE
0x180025cba  mov     rbx, [r14+18h]
0x180025cbe  mov     [rsp+248h+var_1B0], rbx
0x180025cc6  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180025cca  mov     eax, esi
0x180025ccc  lock xadd [rbx+8], eax
0x180025cd1  add     eax, esi
0x180025cd3  jnz     short loc_180025CFE
0x180025cd5  mov     rax, [rbx]
0x180025cd8  mov     rcx, rbx
0x180025cdb  mov     rax, [rax]
0x180025cde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025ce3  mov     eax, esi
0x180025ce5  lock xadd [rbx+0Ch], eax
0x180025cea  add     eax, esi
0x180025cec  jnz     short loc_180025CFE
0x180025cee  mov     rax, [rbx]
0x180025cf1  mov     rcx, rbx
0x180025cf4  mov     rax, [rax+8]
0x180025cf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025cfd  nop
0x180025cfe  jmp     loc_180026316
0x180025d03  lea     rdi, [r14+0A8h]
0x180025d0a  mov     [rsp+248h+var_1F8], rdi
0x180025d0f  mov     rcx, rdi
0x180025d12  call    ??$GetTypeNameWideString@URecoveryItemPdr@Passkey@Security@Data@Windows@@@ProfileDataStore@wil@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; wil::ProfileDataStore::GetTypeNameWideString<Windows::Data::Security::Passkey::RecoveryItemPdr>(void)
0x180025d17  nop
0x180025d18  lea     r12, [r14+0C8h]
0x180025d1f  mov     [rsp+248h+var_1D0], r12
0x180025d24  mov     [r12], r15
0x180025d28  lea     rdx, [r14+0E8h]
0x180025d2f  mov     rcx, [rsi+10h]
0x180025d33  call    ?GetCloudStore@SharedCloudStoreState@details@wil@@QEAA?BUCloudStore@Cloud@Storage@Internal@Windows@winrt@@XZ; wil::details::SharedCloudStoreState::GetCloudStore(void)
0x180025d38  mov     r11, rax
0x180025d3b  lea     rsi, [r14+0F0h]
0x180025d42  mov     rcx, [r14+318h]
0x180025d49  mov     [rsi], rcx
0x180025d4c  mov     rcx, [r14+310h]
0x180025d53  mov     [r14+110h], rcx
0x180025d5a  mov     r8d, [r14+30Ch]
0x180025d61  mov     ecx, r8d
0x180025d64  and     ecx, 1
0x180025d67  mov     edx, ecx
0x180025d69  or      edx, 2
0x180025d6c  bt      r8d, 1
0x180025d71  cmovnb  edx, ecx
0x180025d74  mov     r9d, 4; char *
0x180025d7a  mov     ecx, edx
0x180025d7c  or      ecx, r9d
0x180025d7f  test    r9d, r8d
0x180025d82  cmovz   ecx, edx
0x180025d85  mov     edx, ecx
0x180025d87  or      edx, 10h
0x180025d8a  bt      r8d, 4
0x180025d8f  cmovnb  edx, ecx
0x180025d92  mov     eax, edx
0x180025d94  or      eax, 8
0x180025d97  bt      r8d, 3
0x180025d9c  cmovnb  eax, edx
0x180025d9f  or      eax, 20h
0x180025da2  mov     [r14+130h], eax
0x180025da9  mov     r8d, [rbx+2F0h]
0x180025db0  mov     edx, r8d
0x180025db3  and     edx, 1
0x180025db6  test    r9d, r8d
0x180025db9  jz      short loc_180025DDE
0x180025dbb  mov     rcx, [rsp+248h]; this
0x180025dc3  mov     al, dl
0x180025dc5  xor     al, 1
0x180025dc7  jz      short loc_180025DDB
0x180025dc9  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\sdk\\inc\\wil\\pr"...
0x180025dd0  mov     edx, 8FEh; void *
0x180025dd5  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180025ddb  or      edx, 2
0x180025dde  mov     ecx, edx
0x180025de0  or      ecx, r9d
0x180025de3  bt      r8d, 3
0x180025de8  cmovnb  ecx, edx
0x180025deb  mov     edx, ecx
0x180025ded  or      edx, 8
0x180025df0  bt      r8d, 4
0x180025df5  cmovnb  edx, ecx
0x180025df8  lea     r10, [r14+134h]
0x180025dff  mov     eax, edx
0x180025e01  or      eax, 10h
0x180025e04  bt      r8d, 5
0x180025e09  cmovnb  eax, edx
0x180025e0c  mov     [r10], eax
0x180025e0f  mov     rdx, [r14+0B8h]
0x180025e16  mov     [rsp+248h+var_D8], rdx
0x180025e1e  mov     rax, [r14+0C0h]
0x180025e25  mov     [rsp+248h+var_D0], rax
0x180025e2d  cmp     rax, 7
0x180025e31  jbe     short loc_180025E40
0x180025e33  mov     rcx, [rdi]
0x180025e36  mov     [rsp+248h+var_E8], rcx
0x180025e3e  jmp     short loc_180025E43
0x180025e40  mov     rcx, rdi
0x180025e43  test    edx, edx
0x180025e45  jnz     short loc_180025E4C
0x180025e47  mov     rax, r15
0x180025e4a  jmp     short loc_180025E77
0x180025e4c  mov     eax, edx
0x180025e4e  cmp     [rcx+rax*2], r15w
0x180025e53  jz      short loc_180025E5C
0x180025e55  call    cs:__imp_abort
0x180025e5c  lea     rax, [r14+140h]
0x180025e63  mov     dword ptr [rax], 1
0x180025e69  mov     [r14+144h], edx
0x180025e70  mov     [r14+150h], rcx
0x180025e77  mov     [r14+138h], rax
0x180025e7e  lea     rcx, [r14+158h]
0x180025e85  mov     rax, [r14+300h]
0x180025e8c  mov     [rcx], rax
0x180025e8f  mov     r8, [r13+2F0h]
0x180025e96  lea     r9, [r14+178h]
0x180025e9d  mov     rax, [r8+28h]
0x180025ea1  mov     [r9], rax
0x180025ea4  lea     rbx, [r14+198h]
0x180025eab  lea     rax, [r14+138h]
0x180025eb2  add     r8, 20h ; ' '
0x180025eb6  mov     [rsp+248h+var_200], rsi
0x180025ebb  lea     rdx, [r14+110h]
0x180025ec2  mov     [rsp+248h+var_208], rdx
0x180025ec7  lea     rdx, [r14+130h]
0x180025ece  mov     [rsp+248h+var_210], rdx
0x180025ed3  mov     [rsp+248h+var_218], r10
0x180025ed8  mov     [rsp+248h+var_220], rax
0x180025edd  mov     [rsp+248h+var_228], rcx
0x180025ee2  mov     rdx, rbx
0x180025ee5  mov     rcx, r11
0x180025ee8  call    ?GetCollectionItemsAsync@?$consume_Windows_Internal_Storage_Cloud_ICloudStore2@UCloudStore@Cloud@Storage@Internal@Windows@winrt@@@impl@winrt@@QEBA@AEBW4PartitionKind@Cloud@Storage@Internal@Windows@3@AEBUhstring@param@3@11AEBW4LoadOptions@56783@AEBW4CollectionOptions@56783@11@Z; winrt::impl::consume_Windows_Internal_Storage_Cloud_ICloudStore2<winrt::Windows::Internal::Storage::Cloud::CloudStore>::GetCollectionItemsAsync(winrt::Windows::Internal::Storage::Cloud::PartitionKind const &,winrt::param::hstring const &,winrt::param::hstring const &,winrt::param::hstring const &,winrt::Windows::Internal::Storage::Cloud::LoadOptions const &,winrt::Windows::Internal::Storage::Cloud::CollectionOptions const &,winrt::param::hstring const &,winrt::param::hstring const &)
0x180025eed  nop
0x180025eee  lea     rsi, [r14+0D0h]
0x180025ef5  mov     r8, rax
0x180025ef8  lea     rdx, [r14+320h]
0x180025eff  mov     rcx, rsi
0x180025f02  call    ??0?$AsyncOpWaiter@U?$IAsyncOperation@UGetCollectionItemsResult@Cloud@Storage@Internal@Windows@winrt@@@Foundation@Windows@winrt@@UGetCollectionItemsResult@Cloud@Storage@Internal@34@@details@wil@@QEAA@AEBVcancellation_token@Concurrency@@AEBU?$IAsyncOperation@UGetCollectionItemsResult@Cloud@Storage@Internal@Windows@winrt@@@Foundation@Windows@winrt@@@Z; wil::details::AsyncOpWaiter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::GetCollectionItemsResult>,winrt::Windows::Internal::Storage::Cloud::GetCollectionItemsResult>::AsyncOpWaiter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::GetCollectionItemsResult>,winrt::Windows::Internal::Storage::Cloud::GetCollectionItemsResult>(Concurrency::cancellation_token const &,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::GetCollectionItemsResult> const &)
0x180025f07  nop
0x180025f08  mov     rax, [rbx]
0x180025f0b  mov     [rsp+248h+var_188], rax
0x180025f13  test    rax, rax
0x180025f16  jz      short loc_180025F21
0x180025f18  mov     rcx, rbx
0x180025f1b  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180025f20  nop
0x180025f21  lea     rcx, [r14+0E8h]
0x180025f28  mov     rax, [rcx]
0x180025f2b  mov     [rsp+248h+var_180], rax
0x180025f33  test    rax, rax
0x180025f36  jz      short loc_180025F3D
0x180025f38  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180025f3d  lea     rbx, [r14+1A0h]
0x180025f44  mov     rdx, rbx
0x180025f47  mov     rcx, rsi
0x180025f4a  call    ?WaitForResult@?$AsyncOpWaiter@U?$IAsyncOperation@UGetCollectionItemsResult@Cloud@Storage@Internal@Windows@winrt@@@Foundation@Windows@winrt@@UGetCollectionItemsResult@Cloud@Storage@Internal@34@@details@wil@@QEAA?AUGetCollectionItemsResult@Cloud@Storage@Internal@Windows@winrt@@XZ; wil::details::AsyncOpWaiter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::GetCollectionItemsResult>,winrt::Windows::Internal::Storage::Cloud::GetCollectionItemsResult>::WaitForResult(void)
0x180025f4f  cmp     r12, rax
0x180025f52  jz      short loc_180025F5E
0x180025f54  mov     rdx, [rax]
0x180025f57  mov     [rax], r15
0x180025f5a  mov     [r12], rdx
0x180025f5e  mov     rax, [rbx]
0x180025f61  mov     [rsp+248h+var_178], rax
0x180025f69  test    rax, rax
0x180025f6c  jz      short loc_180025F77
0x180025f6e  mov     rcx, rbx
0x180025f71  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180025f76  nop
0x180025f77  mov     rcx, rsi
0x180025f7a  call    ??1?$AsyncOpWaiter@U?$IAsyncOperation@UCloudStoreSaveResult@Cloud@Storage@Internal@Windows@winrt@@@Foundation@Windows@winrt@@UCloudStoreSaveResult@Cloud@Storage@Internal@34@@details@wil@@QEAA@XZ; wil::details::AsyncOpWaiter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>,winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>::~AsyncOpWaiter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>,winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>(void)
0x180025f7f  nop
0x180025f80  lea     rbx, [r14+238h]
0x180025f87  mov     rcx, [r12]
0x180025f8b  mov     [rsp+248h+var_1C8], rcx
0x180025f93  mov     [rbx], rcx
0x180025f96  test    rcx, rcx
0x180025f99  jz      short loc_180025FA7
0x180025f9b  mov     rax, [rcx]
0x180025f9e  mov     rax, [rax+8]
  ... truncated ...
```
