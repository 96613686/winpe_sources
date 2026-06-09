# wil::ProfileDataStore::CallGetCollectionItemIdsAsync$_ResumeCoro$1_Windows::Data::Security::Passkey::PasskeyItemPdr_

- ea: `0x180025150`
- end: `0x180025a98`
- name: `wil::ProfileDataStore::CallGetCollectionItemIdsAsync$_ResumeCoro$1_Windows::Data::Security::Passkey::PasskeyItemPdr_`
- size: `2376`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180026d40`

## callees

- `0x180003080`
- `0x180003520`
- `0x180003c97`
- `0x180003cdf`
- `0x180007a5c`
- `0x18000c95c`
- `0x18000ce74`
- `0x18000f7fc`
- `0x180025150`
- `0x1800378f4`
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

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180025a15`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180025a15`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180025505`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180025892`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180025505`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180025892`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
void __fastcall wil::ProfileDataStore::CallGetCollectionItemIdsAsync__ResumeCoro_1_Windows::Data::Security::Passkey::PasskeyItemPdr_(
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
  int v57; // [rsp+50h] [rbp-1F8h]
  __int64 v58; // [rsp+78h] [rbp-1D0h]
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
        goto LABEL_66;
      v8 = *(_DWORD *)(v7 + 8);
      do
      {
        if ( !v8 )
LABEL_66:
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
LABEL_12:
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v18 + 8LL))(v18);
          }
        }
      }
      else
      {
        v19 = (__int64 *)(a1 + 168);
        wil::ProfileDataStore::GetTypeNameWideString<Windows::Data::Security::Passkey::PasskeyItemPdr>(a1 + 168);
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
        v58 = winrt::impl::consume_Windows_Internal_Storage_Cloud_IGetCollectionItemsResult<winrt::Windows::Internal::Storage::Cloud::IGetCollectionItemsResult>::RetryAfter(a1 + 200);
        v57 = *(_DWORD *)winrt::impl::consume_Windows_Internal_Storage_Cloud_IGetCollectionItemsResult<winrt::Windows::Internal::Storage::Cloud::IGetCollectionItemsResult>::ResultCode(
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
        *(_DWORD *)(a1 + 664) = v57;
        *(_QWORD *)(a1 + 672) = v58;
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
          v18 = *(volatile signed __int32 **)(a1 + 24);
          if ( _InterlockedExchangeAdd(v18 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v18)(v18);
            if ( _InterlockedExchangeAdd(v18 + 3, 0xFFFFFFFF) == 1 )
              goto LABEL_12;
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
0x180025150  mov     r11, rsp
0x180025153  mov     [r11+10h], rbx
0x180025157  mov     [r11+18h], rsi
0x18002515b  mov     [r11+8], rcx
0x18002515f  push    rdi
0x180025160  push    r12
0x180025162  push    r13
0x180025164  push    r14
0x180025166  push    r15
0x180025168  sub     rsp, 220h
0x18002516f  mov     rax, cs:__security_cookie
0x180025176  xor     rax, rsp
0x180025179  mov     [rsp+248h+var_38], rax
0x180025181  mov     r14, rcx
0x180025184  mov     [rsp+248h+var_1F0], rcx
0x180025189  lea     r13, [r14+8]
0x18002518d  movzx   eax, word ptr [r13+0]
0x180025192  mov     [rsp+248h+var_1D8], ax
0x180025197  inc     ax; switch 5 cases
0x18002519a  mov     ecx, 4
0x18002519f  cmp     ax, cx
0x1800251a2  ja      def_1800251C5; jumptable 00000001800251C5 default case, case 0
0x1800251a8  mov     [rsp+248h+var_1C0], r13
0x1800251b0  movsx   rax, ax
0x1800251b4  lea     rdx, __ImageBase
0x1800251bb  mov     ecx, ds:(jpt_1800251C5 - 180000000h)[rdx+rax*4]
0x1800251c2  add     rcx, rdx
0x1800251c5  jmp     rcx; switch jump
0x1800251c7  jmp     loc_1800259E2; jumptable 00000001800251C5 case 3
0x1800251cc  xor     r15d, r15d; jumptable 00000001800251C5 case 2
0x1800251cf  mov     rsi, [r13+2F0h]
0x1800251d6  mov     [r14+10h], r15
0x1800251da  lea     rbx, [r14+18h]
0x1800251de  mov     [rbx], r15
0x1800251e1  mov     rdx, [rsi+8]
0x1800251e5  test    rdx, rdx
0x1800251e8  jz      loc_1800259B3
0x1800251ee  mov     eax, [rdx+8]
0x1800251f1  jmp     short loc_1800251FD
0x1800251f3  lea     ecx, [rax+1]
0x1800251f6  lock cmpxchg [rdx+8], ecx
0x1800251fb  jz      short loc_180025206
0x1800251fd  test    eax, eax
0x1800251ff  jnz     short loc_1800251F3
0x180025201  jmp     loc_1800259B3
0x180025206  mov     [rsp+248h+var_1E8], rbx
0x18002520b  mov     rax, [rsi]
0x18002520e  mov     [r14+10h], rax
0x180025212  mov     r12, [rsi+8]
0x180025216  mov     [rbx], r12
0x180025219  mov     rax, [r14+320h]
0x180025220  test    rax, rax
0x180025223  jz      loc_1800253B3
0x180025229  mov     eax, [rax+10h]
0x18002522c  nop
0x18002522d  test    eax, eax
0x18002522f  jz      loc_1800253B3
0x180025235  lea     rcx, [r14+70h]
0x180025239  xorps   xmm0, xmm0
0x18002523c  movups  xmmword ptr [rcx], xmm0
0x18002523f  mov     [r14+80h], r15
0x180025246  mov     eax, 7
0x18002524b  mov     [r14+88h], rax
0x180025252  xor     edx, edx
0x180025254  mov     [rcx], dx
0x180025257  mov     [r14+0A0h], r15
0x18002525e  mov     [r14+98h], r15
0x180025265  lea     rsi, [r14+90h]
0x18002526c  mov     [rsi], r15
0x18002526f  lea     rdi, [r14+20h]
0x180025273  mov     [rdi], r15
0x180025276  mov     [r14+28h], r15
0x18002527a  mov     [r14+30h], r15
0x18002527e  lea     rbx, [r14+38h]
0x180025282  movups  xmm1, xmmword ptr [rcx]
0x180025285  movups  [rsp+248h+var_158], xmm1
0x18002528d  movups  xmm0, xmmword ptr [rcx+10h]
0x180025291  movups  [rsp+248h+var_148], xmm0
0x180025299  movups  xmmword ptr [rbx], xmm1
0x18002529c  movups  xmmword ptr [rbx+10h], xmm0
0x1800252a0  mov     [r14+80h], r15
0x1800252a7  mov     [r14+88h], rax
0x1800252ae  xor     eax, eax
0x1800252b0  mov     [rcx], ax
0x1800252b3  mov     dword ptr [r14+58h], 800704C7h
0x1800252bb  mov     [r14+60h], r15
0x1800252bf  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800252c4  mov     rdx, [r14+30h]
0x1800252c8  mov     [rsp+248h+var_B8], rdx
0x1800252d0  mov     [r14+30h], r15
0x1800252d4  mov     rcx, [r14+28h]
0x1800252d8  mov     [rsp+248h+var_C0], rcx
0x1800252e0  mov     [r14+28h], r15
0x1800252e4  mov     rax, [rdi]
0x1800252e7  mov     [rsp+248h+var_C8], rax
0x1800252ef  mov     [rdi], r15
0x1800252f2  mov     [r14-58h], rax
0x1800252f6  mov     [r14-50h], rcx
0x1800252fa  mov     [r14-48h], rdx
0x1800252fe  movups  xmm1, xmmword ptr [rbx]
0x180025301  movups  [rsp+248h+var_B0], xmm1
0x180025309  movups  xmm0, xmmword ptr [rbx+10h]
0x18002530d  movups  [rsp+248h+var_A0], xmm0
0x180025315  movups  xmmword ptr [r14-40h], xmm1
0x18002531a  movups  xmmword ptr [r14-30h], xmm0
0x18002531f  mov     [r14+48h], r15
0x180025323  mov     qword ptr [r14+50h], 7
0x18002532b  xor     eax, eax
0x18002532d  mov     [rbx], ax
0x180025330  mov     dword ptr [r14-20h], 800704C7h
0x180025338  mov     [r14-18h], r15
0x18002533c  mov     dword ptr [r14-60h], 1
0x180025344  mov     rcx, rbx
0x180025347  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002534c  mov     rcx, rdi
0x18002534f  call    ?_Tidy@?$vector@V?$ProfileDataItemReference@URecoveryItemPdr@Passkey@Security@Data@Windows@@@wil@@V?$allocator@V?$ProfileDataItemReference@URecoveryItemPdr@Passkey@Security@Data@Windows@@@wil@@@std@@@std@@AEAAXXZ; std::vector<wil::ProfileDataItemReference<Windows::Data::Security::Passkey::RecoveryItemPdr>>::_Tidy(void)
0x180025354  mov     rcx, rsi
0x180025357  call    ?_Tidy@?$vector@V?$ProfileDataItemReference@URecoveryItemPdr@Passkey@Security@Data@Windows@@@wil@@V?$allocator@V?$ProfileDataItemReference@URecoveryItemPdr@Passkey@Security@Data@Windows@@@wil@@@std@@@std@@AEAAXXZ; std::vector<wil::ProfileDataItemReference<Windows::Data::Security::Passkey::RecoveryItemPdr>>::_Tidy(void)
0x18002535c  nop
0x18002535d  mov     [rsp+248h+var_1B0], r12
0x180025365  test    r12, r12
0x180025368  jz      short loc_1800253AE
0x18002536a  mov     rbx, [r14+18h]
0x18002536e  mov     [rsp+248h+var_1B0], rbx
0x180025376  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18002537a  mov     eax, esi
0x18002537c  lock xadd [rbx+8], eax
0x180025381  add     eax, esi
0x180025383  jnz     short loc_1800253AE
0x180025385  mov     rax, [rbx]
0x180025388  mov     rcx, rbx
0x18002538b  mov     rax, [rax]
0x18002538e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025393  mov     eax, esi
0x180025395  lock xadd [rbx+0Ch], eax
0x18002539a  add     eax, esi
0x18002539c  jnz     short loc_1800253AE
0x18002539e  mov     rax, [rbx]
0x1800253a1  mov     rcx, rbx
0x1800253a4  mov     rax, [rax+8]
0x1800253a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800253ad  nop
0x1800253ae  jmp     loc_1800259C6
0x1800253b3  lea     rdi, [r14+0A8h]
0x1800253ba  mov     [rsp+248h+var_1F8], rdi
0x1800253bf  mov     rcx, rdi
0x1800253c2  call    ??$GetTypeNameWideString@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@ProfileDataStore@wil@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; wil::ProfileDataStore::GetTypeNameWideString<Windows::Data::Security::Passkey::PasskeyItemPdr>(void)
0x1800253c7  nop
0x1800253c8  lea     r12, [r14+0C8h]
0x1800253cf  mov     [rsp+248h+var_1D0], r12
0x1800253d4  mov     [r12], r15
0x1800253d8  lea     rdx, [r14+0E8h]
0x1800253df  mov     rcx, [rsi+10h]
0x1800253e3  call    ?GetCloudStore@SharedCloudStoreState@details@wil@@QEAA?BUCloudStore@Cloud@Storage@Internal@Windows@winrt@@XZ; wil::details::SharedCloudStoreState::GetCloudStore(void)
0x1800253e8  mov     r11, rax
0x1800253eb  lea     rsi, [r14+0F0h]
0x1800253f2  mov     rcx, [r14+318h]
0x1800253f9  mov     [rsi], rcx
0x1800253fc  mov     rcx, [r14+310h]
0x180025403  mov     [r14+110h], rcx
0x18002540a  mov     r8d, [r14+30Ch]
0x180025411  mov     ecx, r8d
0x180025414  and     ecx, 1
0x180025417  mov     edx, ecx
0x180025419  or      edx, 2
0x18002541c  bt      r8d, 1
0x180025421  cmovnb  edx, ecx
0x180025424  mov     r9d, 4; char *
0x18002542a  mov     ecx, edx
0x18002542c  or      ecx, r9d
0x18002542f  test    r9d, r8d
0x180025432  cmovz   ecx, edx
0x180025435  mov     edx, ecx
0x180025437  or      edx, 10h
0x18002543a  bt      r8d, 4
0x18002543f  cmovnb  edx, ecx
0x180025442  mov     eax, edx
0x180025444  or      eax, 8
0x180025447  bt      r8d, 3
0x18002544c  cmovnb  eax, edx
0x18002544f  or      eax, 20h
0x180025452  mov     [r14+130h], eax
0x180025459  mov     r8d, [rbx+2F0h]
0x180025460  mov     edx, r8d
0x180025463  and     edx, 1
0x180025466  test    r9d, r8d
0x180025469  jz      short loc_18002548E
0x18002546b  mov     rcx, [rsp+248h]; this
0x180025473  mov     al, dl
0x180025475  xor     al, 1
0x180025477  jz      short loc_18002548B
0x180025479  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\sdk\\inc\\wil\\pr"...
0x180025480  mov     edx, 8FEh; void *
0x180025485  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18002548b  or      edx, 2
0x18002548e  mov     ecx, edx
0x180025490  or      ecx, r9d
0x180025493  bt      r8d, 3
0x180025498  cmovnb  ecx, edx
0x18002549b  mov     edx, ecx
0x18002549d  or      edx, 8
0x1800254a0  bt      r8d, 4
0x1800254a5  cmovnb  edx, ecx
0x1800254a8  lea     r10, [r14+134h]
0x1800254af  mov     eax, edx
0x1800254b1  or      eax, 10h
0x1800254b4  bt      r8d, 5
0x1800254b9  cmovnb  eax, edx
0x1800254bc  mov     [r10], eax
0x1800254bf  mov     rdx, [r14+0B8h]
0x1800254c6  mov     [rsp+248h+var_D8], rdx
0x1800254ce  mov     rax, [r14+0C0h]
0x1800254d5  mov     [rsp+248h+var_D0], rax
0x1800254dd  cmp     rax, 7
0x1800254e1  jbe     short loc_1800254F0
0x1800254e3  mov     rcx, [rdi]
0x1800254e6  mov     [rsp+248h+var_E8], rcx
0x1800254ee  jmp     short loc_1800254F3
0x1800254f0  mov     rcx, rdi
0x1800254f3  test    edx, edx
0x1800254f5  jnz     short loc_1800254FC
0x1800254f7  mov     rax, r15
0x1800254fa  jmp     short loc_180025527
0x1800254fc  mov     eax, edx
0x1800254fe  cmp     [rcx+rax*2], r15w
0x180025503  jz      short loc_18002550C
0x180025505  call    cs:__imp_abort
0x18002550c  lea     rax, [r14+140h]
0x180025513  mov     dword ptr [rax], 1
0x180025519  mov     [r14+144h], edx
0x180025520  mov     [r14+150h], rcx
0x180025527  mov     [r14+138h], rax
0x18002552e  lea     rcx, [r14+158h]
0x180025535  mov     rax, [r14+300h]
0x18002553c  mov     [rcx], rax
0x18002553f  mov     r8, [r13+2F0h]
0x180025546  lea     r9, [r14+178h]
0x18002554d  mov     rax, [r8+28h]
0x180025551  mov     [r9], rax
0x180025554  lea     rbx, [r14+198h]
0x18002555b  lea     rax, [r14+138h]
0x180025562  add     r8, 20h ; ' '
0x180025566  mov     [rsp+248h+var_200], rsi
0x18002556b  lea     rdx, [r14+110h]
0x180025572  mov     [rsp+248h+var_208], rdx
0x180025577  lea     rdx, [r14+130h]
0x18002557e  mov     [rsp+248h+var_210], rdx
0x180025583  mov     [rsp+248h+var_218], r10
0x180025588  mov     [rsp+248h+var_220], rax
0x18002558d  mov     [rsp+248h+var_228], rcx
0x180025592  mov     rdx, rbx
0x180025595  mov     rcx, r11
0x180025598  call    ?GetCollectionItemsAsync@?$consume_Windows_Internal_Storage_Cloud_ICloudStore2@UCloudStore@Cloud@Storage@Internal@Windows@winrt@@@impl@winrt@@QEBA@AEBW4PartitionKind@Cloud@Storage@Internal@Windows@3@AEBUhstring@param@3@11AEBW4LoadOptions@56783@AEBW4CollectionOptions@56783@11@Z; winrt::impl::consume_Windows_Internal_Storage_Cloud_ICloudStore2<winrt::Windows::Internal::Storage::Cloud::CloudStore>::GetCollectionItemsAsync(winrt::Windows::Internal::Storage::Cloud::PartitionKind const &,winrt::param::hstring const &,winrt::param::hstring const &,winrt::param::hstring const &,winrt::Windows::Internal::Storage::Cloud::LoadOptions const &,winrt::Windows::Internal::Storage::Cloud::CollectionOptions const &,winrt::param::hstring const &,winrt::param::hstring const &)
0x18002559d  nop
0x18002559e  lea     rsi, [r14+0D0h]
0x1800255a5  mov     r8, rax
0x1800255a8  lea     rdx, [r14+320h]
0x1800255af  mov     rcx, rsi
0x1800255b2  call    ??0?$AsyncOpWaiter@U?$IAsyncOperation@UGetCollectionItemsResult@Cloud@Storage@Internal@Windows@winrt@@@Foundation@Windows@winrt@@UGetCollectionItemsResult@Cloud@Storage@Internal@34@@details@wil@@QEAA@AEBVcancellation_token@Concurrency@@AEBU?$IAsyncOperation@UGetCollectionItemsResult@Cloud@Storage@Internal@Windows@winrt@@@Foundation@Windows@winrt@@@Z; wil::details::AsyncOpWaiter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::GetCollectionItemsResult>,winrt::Windows::Internal::Storage::Cloud::GetCollectionItemsResult>::AsyncOpWaiter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::GetCollectionItemsResult>,winrt::Windows::Internal::Storage::Cloud::GetCollectionItemsResult>(Concurrency::cancellation_token const &,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::GetCollectionItemsResult> const &)
0x1800255b7  nop
0x1800255b8  mov     rax, [rbx]
0x1800255bb  mov     [rsp+248h+var_188], rax
0x1800255c3  test    rax, rax
0x1800255c6  jz      short loc_1800255D1
0x1800255c8  mov     rcx, rbx
0x1800255cb  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800255d0  nop
0x1800255d1  lea     rcx, [r14+0E8h]
0x1800255d8  mov     rax, [rcx]
0x1800255db  mov     [rsp+248h+var_180], rax
0x1800255e3  test    rax, rax
0x1800255e6  jz      short loc_1800255ED
0x1800255e8  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800255ed  lea     rbx, [r14+1A0h]
0x1800255f4  mov     rdx, rbx
0x1800255f7  mov     rcx, rsi
0x1800255fa  call    ?WaitForResult@?$AsyncOpWaiter@U?$IAsyncOperation@UGetCollectionItemsResult@Cloud@Storage@Internal@Windows@winrt@@@Foundation@Windows@winrt@@UGetCollectionItemsResult@Cloud@Storage@Internal@34@@details@wil@@QEAA?AUGetCollectionItemsResult@Cloud@Storage@Internal@Windows@winrt@@XZ; wil::details::AsyncOpWaiter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::GetCollectionItemsResult>,winrt::Windows::Internal::Storage::Cloud::GetCollectionItemsResult>::WaitForResult(void)
0x1800255ff  cmp     r12, rax
0x180025602  jz      short loc_18002560E
0x180025604  mov     rdx, [rax]
0x180025607  mov     [rax], r15
0x18002560a  mov     [r12], rdx
0x18002560e  mov     rax, [rbx]
0x180025611  mov     [rsp+248h+var_178], rax
0x180025619  test    rax, rax
0x18002561c  jz      short loc_180025627
0x18002561e  mov     rcx, rbx
0x180025621  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180025626  nop
0x180025627  mov     rcx, rsi
0x18002562a  call    ??1?$AsyncOpWaiter@U?$IAsyncOperation@UCloudStoreSaveResult@Cloud@Storage@Internal@Windows@winrt@@@Foundation@Windows@winrt@@UCloudStoreSaveResult@Cloud@Storage@Internal@34@@details@wil@@QEAA@XZ; wil::details::AsyncOpWaiter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>,winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>::~AsyncOpWaiter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>,winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>(void)
0x18002562f  nop
0x180025630  lea     rbx, [r14+238h]
0x180025637  mov     rcx, [r12]
0x18002563b  mov     [rsp+248h+var_1C8], rcx
0x180025643  mov     [rbx], rcx
0x180025646  test    rcx, rcx
0x180025649  jz      short loc_180025657
0x18002564b  mov     rax, [rcx]
0x18002564e  mov     rax, [rax+8]
  ... truncated ...
```
