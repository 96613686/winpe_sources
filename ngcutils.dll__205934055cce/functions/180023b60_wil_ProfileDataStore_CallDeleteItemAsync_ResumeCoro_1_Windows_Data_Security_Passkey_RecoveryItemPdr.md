# wil::ProfileDataStore::CallDeleteItemAsync$_ResumeCoro$1_Windows::Data::Security::Passkey::RecoveryItemPdr_

- ea: `0x180023b60`
- end: `0x1800242f4`
- name: `wil::ProfileDataStore::CallDeleteItemAsync$_ResumeCoro$1_Windows::Data::Security::Passkey::RecoveryItemPdr_`
- size: `1940`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180024cd8`

## callees

- `0x180003080`
- `0x180003520`
- `0x180007a5c`
- `0x18000ce74`
- `0x18000f7fc`
- `0x18001354c`
- `0x180023b60`
- `0x180037a3c`
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

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18002427b`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18002427b`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180023e58`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180023ed9`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180023f61`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180023e58`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180023ed9`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180023f61`

## pseudocode

```c
void __fastcall wil::ProfileDataStore::CallDeleteItemAsync__ResumeCoro_1_Windows::Data::Security::Passkey::RecoveryItemPdr_(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
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
  __int64 *v21; // rbx
  _QWORD *v22; // rax
  _QWORD *v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // rax
  __int64 v26; // rdx
  __int64 v27; // rcx
  __int64 v28; // rax
  __int64 v29; // rdx
  __int64 v30; // rcx
  __int64 v31; // rax
  __int64 v32; // r8
  __int64 v33; // r8
  __int64 v34; // rdx
  __int64 v35; // r8
  __int64 v36; // rdx
  __int64 v37; // r8
  __int64 v38; // rdx
  __int64 v39; // r8
  __int64 *v40; // rax
  __int64 v41; // rdx
  __int64 v42; // rax
  __int64 v43; // rdx
  __int64 v44; // r8
  volatile signed __int32 *v45; // rsi
  __int64 v46; // [rsp+60h] [rbp-1C8h]
  int CloudStore; // [rsp+80h] [rbp-1A8h]
  wil::details::in1diag3 *retaddr; // [rsp+228h] [rbp+0h]

  v4 = a1 + 8;
  if ( (unsigned __int16)(*(_WORD *)(a1 + 8) + 1) > 4u )
  {
LABEL_76:
    __debugbreak();
  }
  else
  {
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
        if ( *(_DWORD *)(a1 - 80) == 1 )
        {
          std::wstring::~wstring(a1 - 56, v5, a3);
        }
        else if ( *(_DWORD *)(a1 - 80) == 2 )
        {
          __ExceptionPtrDestroy((void *)(a1 - 72));
        }
        `wil::ProfileDataStore::CallDeleteItemAsync<Windows::Data::Security::Passkey::PasskeyItemPdr>'::`8'::_parameters_::~_parameters_(v4 + 624);
        if ( *(_WORD *)(a1 + 10) )
          operator delete((void *)(a1 - 96), 0x320u);
        return;
      case 0:
        goto LABEL_76;
      case 2:
        v6 = *(_QWORD **)(a1 + 632);
        *(_QWORD *)(a1 + 16) = 0;
        v7 = (volatile signed __int32 **)(a1 + 24);
        *(_QWORD *)(a1 + 24) = 0;
        v8 = v6[1];
        if ( !v8 )
          goto LABEL_65;
        v9 = *(_DWORD *)(v8 + 8);
        do
        {
          if ( !v9 )
LABEL_65:
            std::_Throw_bad_weak_ptr();
          v10 = v9;
          v9 = _InterlockedCompareExchange((volatile signed __int32 *)(v8 + 8), v9 + 1, v9);
        }
        while ( v10 != v9 );
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
        *(_DWORD *)(a1 + 32) = v14;
        v15 = *(_QWORD *)(a1 + 688);
        if ( v15 && *(_DWORD *)(v15 + 16) )
        {
          *(_OWORD *)(a1 + 96) = 0;
          *(_QWORD *)(a1 + 112) = 0;
          *(_QWORD *)(a1 + 120) = 7;
          *(_WORD *)(a1 + 96) = 0;
          *(_QWORD *)(a1 + 40) = 0;
          *(_DWORD *)(a1 + 48) = 0;
          *(_DWORD *)(a1 + 52) = -2147023673;
          v16 = *(_OWORD *)(a1 + 112);
          *(_OWORD *)(a1 + 56) = *(_OWORD *)(a1 + 96);
          *(_OWORD *)(a1 + 72) = v16;
          *(_QWORD *)(a1 + 112) = 0;
          *(_QWORD *)(a1 + 120) = 7;
          *(_WORD *)(a1 + 96) = 0;
          *(_QWORD *)(a1 + 88) = 0;
          *(_QWORD *)(a1 - 72) = *(_QWORD *)(a1 + 40);
          *(_DWORD *)(a1 - 64) = *(_DWORD *)(a1 + 48);
          *(_DWORD *)(a1 - 60) = *(_DWORD *)(a1 + 52);
          v17 = *(_OWORD *)(a1 + 72);
          *(_OWORD *)(a1 - 56) = *(_OWORD *)(a1 + 56);
          *(_OWORD *)(a1 - 40) = v17;
          *(_QWORD *)(a1 + 72) = 0;
          *(_QWORD *)(a1 + 80) = 7;
          *(_WORD *)(a1 + 56) = 0;
          *(_QWORD *)(a1 - 24) = 0;
          *(_DWORD *)(a1 - 80) = 1;
          std::wstring::~wstring(a1 + 56, v11, v6);
          std::wstring::~wstring(a1 + 96, v18, v19);
          if ( *v7 )
          {
            v20 = *v7;
            if ( _InterlockedExchangeAdd(*v7 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v20)(v20);
              if ( _InterlockedExchangeAdd(v20 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v20 + 8LL))(v20);
            }
          }
        }
        else
        {
          v21 = (__int64 *)(a1 + 128);
          *(_QWORD *)(a1 + 128) = 0;
          CloudStore = wil::details::SharedCloudStoreState::GetCloudStore(v6[2], a1 + 160);
          *(_QWORD *)(a1 + 168) = *(_QWORD *)(a1 + 680);
          *(_QWORD *)(a1 + 200) = *(_QWORD *)(a1 + 672);
          v46 = *(_QWORD *)(a1 + 656);
          v22 = (_QWORD *)wil::ProfileDataStore::GetTypeNameWideString<Windows::Data::Security::Passkey::RecoveryItemPdr>(a1 + 264);
          v23 = v22;
          v24 = v22[2];
          if ( v22[3] > 7u )
            v23 = (_QWORD *)*v22;
          if ( (_DWORD)v24 )
          {
            if ( *((_WORD *)v23 + (unsigned int)v24) )
              abort();
            v25 = a1 + 240;
            *(_DWORD *)(a1 + 240) = 1;
            *(_DWORD *)(a1 + 244) = v24;
            *(_QWORD *)(a1 + 256) = v23;
          }
          else
          {
            v25 = 0;
          }
          *(_QWORD *)(a1 + 232) = v25;
          std::wstring::wstring(a1 + 328, *(_QWORD *)(a1 + 640));
          v26 = *(_QWORD *)(a1 + 344);
          if ( *(_QWORD *)(a1 + 352) <= 7u )
            v27 = a1 + 328;
          else
            v27 = *(_QWORD *)(a1 + 328);
          if ( (_DWORD)v26 )
          {
            if ( *(_WORD *)(v27 + 2LL * (unsigned int)v26) )
              abort();
            v28 = a1 + 304;
            *(_DWORD *)(a1 + 304) = 1;
            *(_DWORD *)(a1 + 308) = v26;
            *(_QWORD *)(a1 + 320) = v27;
          }
          else
          {
            v28 = 0;
          }
          *(_QWORD *)(a1 + 296) = v28;
          std::wstring::wstring(a1 + 392, *(_QWORD *)(a1 + 640) + 32LL);
          v29 = *(_QWORD *)(a1 + 408);
          if ( *(_QWORD *)(a1 + 416) <= 7u )
            v30 = a1 + 392;
          else
            v30 = *(_QWORD *)(a1 + 392);
          if ( (_DWORD)v29 )
          {
            if ( *(_WORD *)(v30 + 2LL * (unsigned int)v29) )
              abort();
            v31 = a1 + 368;
            *(_DWORD *)(a1 + 368) = 1;
            *(_DWORD *)(a1 + 372) = v29;
            *(_QWORD *)(a1 + 384) = v30;
          }
          else
          {
            v31 = 0;
          }
          *(_QWORD *)(a1 + 360) = v31;
          v32 = *(_QWORD *)(v4 + 624);
          *(_QWORD *)(a1 + 424) = *(_QWORD *)(v32 + 40);
          v33 = winrt::impl::consume_Windows_Internal_Storage_Cloud_ICloudStore2<winrt::Windows::Internal::Storage::Cloud::CloudStore>::DeleteAsync(
                  CloudStore,
                  (int)a1 + 456,
                  (int)v32 + 32,
                  (int)a1 + 424,
                  a1 + 360,
                  a1 + 296,
                  a1 + 232,
                  v46,
                  a1 + 32,
                  a1 + 200,
                  a1 + 168);
          wil::details::AsyncOpWaiter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>,winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>::AsyncOpWaiter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>,winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>(
            a1 + 136,
            a1 + 688,
            v33);
          if ( *(_QWORD *)(a1 + 456) )
            winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 456);
          std::wstring::~wstring(a1 + 392, v34, v35);
          std::wstring::~wstring(a1 + 328, v36, v37);
          std::wstring::~wstring(a1 + 264, v38, v39);
          if ( *(_QWORD *)(a1 + 160) )
            winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 160);
          v40 = (__int64 *)wil::details::AsyncOpWaiter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>,winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>::WaitForResult(
                             a1 + 136,
                             a1 + 464);
          if ( v21 != v40 )
          {
            v41 = *v40;
            *v40 = 0;
            *v21 = v41;
          }
          if ( *(_QWORD *)(a1 + 464) )
            winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 464);
          wil::details::AsyncOpWaiter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>,winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>::~AsyncOpWaiter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>,winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>(a1 + 136);
          v42 = wil::ProfileDataStoreSaveResult::ProfileDataStoreSaveResult(
                  (wil::ProfileDataStoreSaveResult *)(a1 + 560),
                  (const struct winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult *)(a1 + 128));
          *(_QWORD *)(a1 - 72) = *(_QWORD *)v42;
          *(_DWORD *)(a1 - 64) = *(_DWORD *)(v42 + 8);
          *(_DWORD *)(a1 - 60) = *(_DWORD *)(v42 + 12);
          *(_OWORD *)(a1 - 56) = 0;
          *(_QWORD *)(a1 - 40) = 0;
          *(_QWORD *)(a1 - 32) = 0;
          *(_OWORD *)(a1 - 56) = *(_OWORD *)(v42 + 16);
          *(_OWORD *)(a1 - 40) = *(_OWORD *)(v42 + 32);
          *(_QWORD *)(v42 + 32) = 0;
          *(_QWORD *)(v42 + 40) = 7;
          *(_WORD *)(v42 + 16) = 0;
          *(_QWORD *)(a1 - 24) = *(_QWORD *)(v42 + 48);
          *(_DWORD *)(a1 - 80) = 1;
          std::wstring::~wstring(a1 + 576, v43, v44);
          if ( *v21 )
            winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a1 + 128);
          if ( *v7 )
          {
            v45 = *v7;
            if ( _InterlockedExchangeAdd(*v7 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v45)(v45);
              if ( _InterlockedExchangeAdd(v45 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v45 + 8LL))(v45);
            }
          }
        }
        *(_QWORD *)(a1 + 616) = a1 - 96;
        *(_WORD *)v4 = 0;
        `wil::details::coro::promise_base<wil::ProfileDataStoreSaveResult>::final_suspend'::`2'::awaiter::await_suspend();
        break;
    }
  }
}

```

## disassembly

```asm
0x180023b60  mov     r11, rsp
0x180023b63  mov     [r11+10h], rbx
0x180023b67  mov     [r11+18h], rsi
0x180023b6b  mov     [r11+8], rcx
0x180023b6f  push    rdi
0x180023b70  push    r12
0x180023b72  push    r13
0x180023b74  push    r14
0x180023b76  push    r15
0x180023b78  sub     rsp, 200h
0x180023b7f  mov     rax, cs:__security_cookie
0x180023b86  xor     rax, rsp
0x180023b89  mov     [rsp+228h+var_38], rax
0x180023b91  mov     rdi, rcx
0x180023b94  mov     [rsp+228h+var_1C0], rcx
0x180023b99  lea     r14, [rdi+8]
0x180023b9d  movzx   eax, word ptr [r14]
0x180023ba1  mov     [rsp+228h+var_1B8], ax
0x180023ba6  mov     r15d, 1
0x180023bac  add     ax, r15w
0x180023bb0  lea     r9d, [r15+3]; char *
0x180023bb4  cmp     ax, r9w
0x180023bb8  ja      loc_1800242AF; jumptable 0000000180023BD8 case 1
0x180023bbe  mov     [rsp+228h+var_1B0], r14
0x180023bc3  movsx   rax, ax
0x180023bc7  lea     rdx, __ImageBase
0x180023bce  mov     ecx, ds:(jpt_180023BD8 - 180000000h)[rdx+rax*4]; switch 5 cases
0x180023bd5  add     rcx, rdx
0x180023bd8  jmp     rcx; switch jump
0x180023bda  jmp     loc_18002424A; jumptable 0000000180023BD8 case 4
0x180023bdf  xor     esi, esi; jumptable 0000000180023BD8 case 3
0x180023be1  mov     r8, [r14+270h]
0x180023be8  mov     [rdi+10h], rsi
0x180023bec  lea     r12, [rdi+18h]
0x180023bf0  mov     [r12], rsi
0x180023bf4  mov     rdx, [r8+8]
0x180023bf8  test    rdx, rdx
0x180023bfb  jz      loc_18002421F
0x180023c01  mov     eax, [rdx+8]
0x180023c04  jmp     short loc_180023C10
0x180023c06  lea     ecx, [rax+1]
0x180023c09  lock cmpxchg [rdx+8], ecx
0x180023c0e  jz      short loc_180023C19
0x180023c10  test    eax, eax
0x180023c12  jnz     short loc_180023C06
0x180023c14  jmp     loc_18002421F
0x180023c19  mov     [rsp+228h+var_180], r12
0x180023c21  mov     rax, [r8]
0x180023c24  mov     [rdi+10h], rax
0x180023c28  mov     rax, [r8+8]
0x180023c2c  mov     [r12], rax
0x180023c30  mov     edx, [rdi+298h]
0x180023c36  mov     eax, edx
0x180023c38  mov     r10d, 7
0x180023c3e  and     eax, r10d
0x180023c41  jz      short loc_180023C50
0x180023c43  mov     ecx, eax
0x180023c45  dec     rax
0x180023c48  test    rcx, rax
0x180023c4b  mov     al, r15b
0x180023c4e  jnz     short loc_180023C53
0x180023c50  mov     al, sil
0x180023c53  mov     rcx, [rsp+228h]; this
0x180023c5b  test    al, al
0x180023c5d  jz      short loc_180023C71
0x180023c5f  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\sdk\\inc\\wil\\pr"...
0x180023c66  mov     edx, 91Fh; void *
0x180023c6b  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180023c71  test    r15d, edx
0x180023c74  jz      short loc_180023C7B
0x180023c76  mov     ecx, r15d
0x180023c79  jmp     short loc_180023C8D
0x180023c7b  mov     ecx, 2
0x180023c80  test    ecx, edx
0x180023c82  jnz     short loc_180023C8D
0x180023c84  mov     ecx, esi
0x180023c86  test    r9d, edx
0x180023c89  cmovnz  ecx, r9d
0x180023c8d  lea     r13, [rdi+20h]
0x180023c91  mov     eax, ecx
0x180023c93  or      eax, 20h
0x180023c96  bt      edx, 4
0x180023c9a  cmovnb  eax, ecx
0x180023c9d  mov     [r13+0], eax
0x180023ca1  mov     rax, [rdi+2B0h]
0x180023ca8  test    rax, rax
0x180023cab  jz      loc_180023DD8
0x180023cb1  mov     eax, [rax+10h]
0x180023cb4  nop
0x180023cb5  test    eax, eax
0x180023cb7  jz      loc_180023DD8
0x180023cbd  lea     rbx, [rdi+60h]
0x180023cc1  xorps   xmm0, xmm0
0x180023cc4  movups  xmmword ptr [rbx], xmm0
0x180023cc7  mov     [rdi+70h], rsi
0x180023ccb  mov     [rdi+78h], r10
0x180023ccf  xor     eax, eax
0x180023cd1  mov     [rbx], ax
0x180023cd4  mov     [rdi+28h], rsi
0x180023cd8  mov     [rdi+30h], esi
0x180023cdb  mov     dword ptr [rdi+34h], 800704C7h
0x180023ce2  lea     rcx, [rdi+38h]
0x180023ce6  movups  xmm1, xmmword ptr [rbx]
0x180023ce9  movups  [rsp+228h+var_D0], xmm1
0x180023cf1  movups  xmm0, xmmword ptr [rbx+10h]
0x180023cf5  movups  [rsp+228h+var_C0], xmm0
0x180023cfd  movups  xmmword ptr [rcx], xmm1
0x180023d00  movups  xmmword ptr [rcx+10h], xmm0
0x180023d04  mov     [rdi+70h], rsi
0x180023d08  mov     [rdi+78h], r10
0x180023d0c  mov     [rbx], ax
0x180023d0f  mov     [rdi+58h], rsi
0x180023d13  mov     rax, [rdi+28h]
0x180023d17  mov     [rsp+228h+var_108], rax
0x180023d1f  mov     [rdi-48h], rax
0x180023d23  mov     eax, [rdi+30h]
0x180023d26  mov     [rsp+228h+var_100], eax
0x180023d2d  mov     [rdi-40h], eax
0x180023d30  mov     eax, [rdi+34h]
0x180023d33  mov     [rsp+228h+var_FC], eax
0x180023d3a  mov     [rdi-3Ch], eax
0x180023d3d  movups  xmm1, xmmword ptr [rcx]
0x180023d40  movups  [rsp+228h+var_F8], xmm1
0x180023d48  movups  xmm0, xmmword ptr [rcx+10h]
0x180023d4c  movups  [rsp+228h+var_E8], xmm0
0x180023d54  movups  xmmword ptr [rdi-38h], xmm1
0x180023d58  movups  xmmword ptr [rdi-28h], xmm0
0x180023d5c  mov     [rdi+48h], rsi
0x180023d60  mov     [rdi+50h], r10
0x180023d64  xor     eax, eax
0x180023d66  mov     [rcx], ax
0x180023d69  mov     [rdi-18h], rsi
0x180023d6d  mov     [rdi-50h], r15d
0x180023d71  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180023d76  mov     rcx, rbx
0x180023d79  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180023d7e  nop
0x180023d7f  mov     rax, [r12]
0x180023d83  mov     [rsp+228h+var_198], rax
0x180023d8b  test    rax, rax
0x180023d8e  jz      short loc_180023DD3
0x180023d90  mov     rsi, [r12]
0x180023d94  mov     [rsp+228h+var_198], rsi
0x180023d9c  or      ebx, 0FFFFFFFFh
0x180023d9f  mov     eax, ebx
0x180023da1  lock xadd [rsi+8], eax
0x180023da6  add     eax, ebx
0x180023da8  jnz     short loc_180023DD3
0x180023daa  mov     rax, [rsi]
0x180023dad  mov     rcx, rsi
0x180023db0  mov     rax, [rax]
0x180023db3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023db8  mov     eax, ebx
0x180023dba  lock xadd [rsi+0Ch], eax
0x180023dbf  add     eax, ebx
0x180023dc1  jnz     short loc_180023DD3
0x180023dc3  mov     rax, [rsi]
0x180023dc6  mov     rcx, rsi
0x180023dc9  mov     rax, [rax+8]
0x180023dcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023dd2  nop
0x180023dd3  jmp     loc_18002422F
0x180023dd8  lea     rbx, [rdi+80h]
0x180023ddf  mov     [rsp+228h+var_190], rbx
0x180023de7  mov     [rbx], rsi
0x180023dea  lea     rdx, [rdi+0A0h]
0x180023df1  mov     rcx, [r8+10h]
0x180023df5  call    ?GetCloudStore@SharedCloudStoreState@details@wil@@QEAA?BUCloudStore@Cloud@Storage@Internal@Windows@winrt@@XZ; wil::details::SharedCloudStoreState::GetCloudStore(void)
0x180023dfa  mov     qword ptr [rsp+228h+var_1A8], rax
0x180023e02  mov     rcx, [rdi+2A8h]
0x180023e09  mov     [rdi+0A8h], rcx
0x180023e10  mov     rcx, [rdi+2A0h]
0x180023e17  mov     [rdi+0C8h], rcx
0x180023e1e  mov     rax, [r13+270h]
0x180023e25  mov     [rsp+228h+var_1C8], rax
0x180023e2a  lea     rcx, [rdi+108h]
0x180023e31  call    ??$GetTypeNameWideString@URecoveryItemPdr@Passkey@Security@Data@Windows@@@ProfileDataStore@wil@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; wil::ProfileDataStore::GetTypeNameWideString<Windows::Data::Security::Passkey::RecoveryItemPdr>(void)
0x180023e36  mov     rcx, rax
0x180023e39  mov     rdx, [rax+10h]
0x180023e3d  cmp     qword ptr [rax+18h], 7
0x180023e42  jbe     short loc_180023E47
0x180023e44  mov     rcx, [rax]
0x180023e47  test    edx, edx
0x180023e49  jnz     short loc_180023E50
0x180023e4b  mov     rax, rsi
0x180023e4e  jmp     short loc_180023E76
0x180023e50  mov     eax, edx
0x180023e52  cmp     [rcx+rax*2], si
0x180023e56  jz      short loc_180023E5F
0x180023e58  call    cs:__imp_abort
0x180023e5f  lea     rax, [rdi+0F0h]
0x180023e66  mov     [rax], r15d
0x180023e69  mov     [rdi+0F4h], edx
0x180023e6f  mov     [rdi+100h], rcx
0x180023e76  mov     [rdi+0E8h], rax
0x180023e7d  lea     r15, [rdi+148h]
0x180023e84  mov     rdx, [rdi+280h]
0x180023e8b  mov     rcx, r15
0x180023e8e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180023e93  nop
0x180023e94  mov     rdx, [rdi+158h]
0x180023e9b  mov     [rsp+228h+var_138], rdx
0x180023ea3  mov     rax, [rdi+160h]
0x180023eaa  mov     [rsp+228h+var_130], rax
0x180023eb2  cmp     rax, 7
0x180023eb6  jbe     short loc_180023EC5
0x180023eb8  mov     rcx, [r15]
0x180023ebb  mov     [rsp+228h+var_148], rcx
0x180023ec3  jmp     short loc_180023EC8
0x180023ec5  mov     rcx, r15
0x180023ec8  test    edx, edx
0x180023eca  jnz     short loc_180023ED1
0x180023ecc  mov     rax, rsi
0x180023ecf  jmp     short loc_180023EFA
0x180023ed1  mov     eax, edx
0x180023ed3  cmp     [rcx+rax*2], si
0x180023ed7  jz      short loc_180023EE0
0x180023ed9  call    cs:__imp_abort
0x180023ee0  lea     rax, [rdi+130h]
0x180023ee7  mov     dword ptr [rax], 1
0x180023eed  mov     [rdi+134h], edx
0x180023ef3  mov     [rdi+140h], rcx
0x180023efa  mov     [rdi+128h], rax
0x180023f01  lea     r15, [rdi+188h]
0x180023f08  mov     rdx, [rdi+280h]
0x180023f0f  add     rdx, 20h ; ' '
0x180023f13  mov     rcx, r15
0x180023f16  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180023f1b  nop
0x180023f1c  mov     rdx, [rdi+198h]
0x180023f23  mov     [rsp+228h+var_118], rdx
0x180023f2b  mov     rax, [rdi+1A0h]
0x180023f32  mov     [rsp+228h+var_110], rax
0x180023f3a  cmp     rax, 7
0x180023f3e  jbe     short loc_180023F4D
0x180023f40  mov     rcx, [r15]
0x180023f43  mov     [rsp+228h+var_128], rcx
0x180023f4b  jmp     short loc_180023F50
0x180023f4d  mov     rcx, r15
0x180023f50  test    edx, edx
0x180023f52  jnz     short loc_180023F59
0x180023f54  mov     rax, rsi
0x180023f57  jmp     short loc_180023F82
0x180023f59  mov     eax, edx
0x180023f5b  cmp     [rcx+rax*2], si
0x180023f5f  jz      short loc_180023F68
0x180023f61  call    cs:__imp_abort
0x180023f68  lea     rax, [rdi+170h]
0x180023f6f  mov     dword ptr [rax], 1
0x180023f75  mov     [rdi+174h], edx
0x180023f7b  mov     [rdi+180h], rcx
0x180023f82  mov     [rdi+168h], rax
0x180023f89  mov     r8, [r14+270h]
0x180023f90  lea     r9, [rdi+1A8h]
0x180023f97  mov     rax, [r8+28h]
0x180023f9b  mov     [r9], rax
0x180023f9e  lea     rdx, [rdi+1C8h]
0x180023fa5  lea     rax, [rdi+0E8h]
0x180023fac  lea     rcx, [rdi+128h]
0x180023fb3  lea     r10, [rdi+168h]
0x180023fba  add     r8, 20h ; ' '
0x180023fbe  lea     r11, [rdi+0A8h]
0x180023fc5  mov     [rsp+228h+var_1D8], r11
0x180023fca  lea     r11, [rdi+0C8h]
0x180023fd1  mov     [rsp+228h+var_1E0], r11
0x180023fd6  mov     [rsp+228h+var_1E8], r13
0x180023fdb  mov     r11, [rsp+228h+var_1C8]
0x180023fe0  mov     [rsp+228h+var_1F0], r11
0x180023fe5  mov     [rsp+228h+var_1F8], rax
0x180023fea  mov     [rsp+228h+var_200], rcx
0x180023fef  mov     [rsp+228h+var_208], r10
0x180023ff4  mov     rcx, qword ptr [rsp+228h+var_1A8]
0x180023ffc  call    ?DeleteAsync@?$consume_Windows_Internal_Storage_Cloud_ICloudStore2@UCloudStore@Cloud@Storage@Internal@Windows@winrt@@@impl@winrt@@QEBA@AEBW4PartitionKind@Cloud@Storage@Internal@Windows@3@AEBUhstring@param@3@111_KAEBW4SaveOptions@56783@11@Z; winrt::impl::consume_Windows_Internal_Storage_Cloud_ICloudStore2<winrt::Windows::Internal::Storage::Cloud::CloudStore>::DeleteAsync(winrt::Windows::Internal::Storage::Cloud::PartitionKind const &,winrt::param::hstring const &,winrt::param::hstring const &,winrt::param::hstring const &,winrt::param::hstring const &,unsigned __int64,winrt::Windows::Internal::Storage::Cloud::SaveOptions const &,winrt::param::hstring const &,winrt::param::hstring const &)
0x180024001  nop
0x180024002  lea     r13, [rdi+88h]
0x180024009  mov     r8, rax
0x18002400c  lea     rdx, [rdi+2B0h]
0x180024013  mov     rcx, r13
0x180024016  call    ??0?$AsyncOpWaiter@U?$IAsyncOperation@UCloudStoreSaveResult@Cloud@Storage@Internal@Windows@winrt@@@Foundation@Windows@winrt@@UCloudStoreSaveResult@Cloud@Storage@Internal@34@@details@wil@@QEAA@AEBVcancellation_token@Concurrency@@AEBU?$IAsyncOperation@UCloudStoreSaveResult@Cloud@Storage@Internal@Windows@winrt@@@Foundation@Windows@winrt@@@Z; wil::details::AsyncOpWaiter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>,winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>::AsyncOpWaiter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>,winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>(Concurrency::cancellation_token const &,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult> const &)
0x18002401b  nop
0x18002401c  lea     rcx, [rdi+1C8h]
0x180024023  mov     rax, [rcx]
0x180024026  mov     [rsp+228h+var_178], rax
0x18002402e  test    rax, rax
0x180024031  jz      short loc_180024039
0x180024033  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180024038  nop
0x180024039  mov     rcx, r15
0x18002403c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180024041  nop
0x180024042  lea     rcx, [rdi+148h]
0x180024049  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002404e  nop
0x18002404f  lea     rcx, [rdi+108h]
0x180024056  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002405b  nop
0x18002405c  lea     rcx, [rdi+0A0h]
0x180024063  mov     rax, [rcx]
0x180024066  mov     [rsp+228h+var_170], rax
0x18002406e  test    rax, rax
  ... truncated ...
```
