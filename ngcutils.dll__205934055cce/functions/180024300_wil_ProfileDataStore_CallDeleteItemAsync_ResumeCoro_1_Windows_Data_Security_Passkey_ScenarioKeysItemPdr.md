# wil::ProfileDataStore::CallDeleteItemAsync$_ResumeCoro$1_Windows::Data::Security::Passkey::ScenarioKeysItemPdr_

- ea: `0x180024300`
- end: `0x180024a94`
- name: `wil::ProfileDataStore::CallDeleteItemAsync$_ResumeCoro$1_Windows::Data::Security::Passkey::ScenarioKeysItemPdr_`
- size: `1940`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180024f14`

## callees

- `0x180003080`
- `0x180003520`
- `0x180007a5c`
- `0x18000ce74`
- `0x18000f7fc`
- `0x18001354c`
- `0x180024300`
- `0x180037b84`
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

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180024a1b`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180024a1b`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800245f8`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180024679`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180024701`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800245f8`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180024679`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180024701`

## pseudocode

```c
void __fastcall wil::ProfileDataStore::CallDeleteItemAsync__ResumeCoro_1_Windows::Data::Security::Passkey::ScenarioKeysItemPdr_(
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
          v22 = (_QWORD *)wil::ProfileDataStore::GetTypeNameWideString<Windows::Data::Security::Passkey::ScenarioKeysItemPdr>(a1 + 264);
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
0x180024300  mov     r11, rsp
0x180024303  mov     [r11+10h], rbx
0x180024307  mov     [r11+18h], rsi
0x18002430b  mov     [r11+8], rcx
0x18002430f  push    rdi
0x180024310  push    r12
0x180024312  push    r13
0x180024314  push    r14
0x180024316  push    r15
0x180024318  sub     rsp, 200h
0x18002431f  mov     rax, cs:__security_cookie
0x180024326  xor     rax, rsp
0x180024329  mov     [rsp+228h+var_38], rax
0x180024331  mov     rdi, rcx
0x180024334  mov     [rsp+228h+var_1C0], rcx
0x180024339  lea     r14, [rdi+8]
0x18002433d  movzx   eax, word ptr [r14]
0x180024341  mov     [rsp+228h+var_1B8], ax
0x180024346  mov     r15d, 1
0x18002434c  add     ax, r15w
0x180024350  lea     r9d, [r15+3]; char *
0x180024354  cmp     ax, r9w
0x180024358  ja      loc_180024A4F; jumptable 0000000180024378 case 1
0x18002435e  mov     [rsp+228h+var_1B0], r14
0x180024363  movsx   rax, ax
0x180024367  lea     rdx, __ImageBase
0x18002436e  mov     ecx, ds:(jpt_180024378 - 180000000h)[rdx+rax*4]; switch 5 cases
0x180024375  add     rcx, rdx
0x180024378  jmp     rcx; switch jump
0x18002437a  jmp     loc_1800249EA; jumptable 0000000180024378 case 4
0x18002437f  xor     esi, esi; jumptable 0000000180024378 case 3
0x180024381  mov     r8, [r14+270h]
0x180024388  mov     [rdi+10h], rsi
0x18002438c  lea     r12, [rdi+18h]
0x180024390  mov     [r12], rsi
0x180024394  mov     rdx, [r8+8]
0x180024398  test    rdx, rdx
0x18002439b  jz      loc_1800249BF
0x1800243a1  mov     eax, [rdx+8]
0x1800243a4  jmp     short loc_1800243B0
0x1800243a6  lea     ecx, [rax+1]
0x1800243a9  lock cmpxchg [rdx+8], ecx
0x1800243ae  jz      short loc_1800243B9
0x1800243b0  test    eax, eax
0x1800243b2  jnz     short loc_1800243A6
0x1800243b4  jmp     loc_1800249BF
0x1800243b9  mov     [rsp+228h+var_180], r12
0x1800243c1  mov     rax, [r8]
0x1800243c4  mov     [rdi+10h], rax
0x1800243c8  mov     rax, [r8+8]
0x1800243cc  mov     [r12], rax
0x1800243d0  mov     edx, [rdi+298h]
0x1800243d6  mov     eax, edx
0x1800243d8  mov     r10d, 7
0x1800243de  and     eax, r10d
0x1800243e1  jz      short loc_1800243F0
0x1800243e3  mov     ecx, eax
0x1800243e5  dec     rax
0x1800243e8  test    rcx, rax
0x1800243eb  mov     al, r15b
0x1800243ee  jnz     short loc_1800243F3
0x1800243f0  mov     al, sil
0x1800243f3  mov     rcx, [rsp+228h]; this
0x1800243fb  test    al, al
0x1800243fd  jz      short loc_180024411
0x1800243ff  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\sdk\\inc\\wil\\pr"...
0x180024406  mov     edx, 91Fh; void *
0x18002440b  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180024411  test    r15d, edx
0x180024414  jz      short loc_18002441B
0x180024416  mov     ecx, r15d
0x180024419  jmp     short loc_18002442D
0x18002441b  mov     ecx, 2
0x180024420  test    ecx, edx
0x180024422  jnz     short loc_18002442D
0x180024424  mov     ecx, esi
0x180024426  test    r9d, edx
0x180024429  cmovnz  ecx, r9d
0x18002442d  lea     r13, [rdi+20h]
0x180024431  mov     eax, ecx
0x180024433  or      eax, 20h
0x180024436  bt      edx, 4
0x18002443a  cmovnb  eax, ecx
0x18002443d  mov     [r13+0], eax
0x180024441  mov     rax, [rdi+2B0h]
0x180024448  test    rax, rax
0x18002444b  jz      loc_180024578
0x180024451  mov     eax, [rax+10h]
0x180024454  nop
0x180024455  test    eax, eax
0x180024457  jz      loc_180024578
0x18002445d  lea     rbx, [rdi+60h]
0x180024461  xorps   xmm0, xmm0
0x180024464  movups  xmmword ptr [rbx], xmm0
0x180024467  mov     [rdi+70h], rsi
0x18002446b  mov     [rdi+78h], r10
0x18002446f  xor     eax, eax
0x180024471  mov     [rbx], ax
0x180024474  mov     [rdi+28h], rsi
0x180024478  mov     [rdi+30h], esi
0x18002447b  mov     dword ptr [rdi+34h], 800704C7h
0x180024482  lea     rcx, [rdi+38h]
0x180024486  movups  xmm1, xmmword ptr [rbx]
0x180024489  movups  [rsp+228h+var_D0], xmm1
0x180024491  movups  xmm0, xmmword ptr [rbx+10h]
0x180024495  movups  [rsp+228h+var_C0], xmm0
0x18002449d  movups  xmmword ptr [rcx], xmm1
0x1800244a0  movups  xmmword ptr [rcx+10h], xmm0
0x1800244a4  mov     [rdi+70h], rsi
0x1800244a8  mov     [rdi+78h], r10
0x1800244ac  mov     [rbx], ax
0x1800244af  mov     [rdi+58h], rsi
0x1800244b3  mov     rax, [rdi+28h]
0x1800244b7  mov     [rsp+228h+var_108], rax
0x1800244bf  mov     [rdi-48h], rax
0x1800244c3  mov     eax, [rdi+30h]
0x1800244c6  mov     [rsp+228h+var_100], eax
0x1800244cd  mov     [rdi-40h], eax
0x1800244d0  mov     eax, [rdi+34h]
0x1800244d3  mov     [rsp+228h+var_FC], eax
0x1800244da  mov     [rdi-3Ch], eax
0x1800244dd  movups  xmm1, xmmword ptr [rcx]
0x1800244e0  movups  [rsp+228h+var_F8], xmm1
0x1800244e8  movups  xmm0, xmmword ptr [rcx+10h]
0x1800244ec  movups  [rsp+228h+var_E8], xmm0
0x1800244f4  movups  xmmword ptr [rdi-38h], xmm1
0x1800244f8  movups  xmmword ptr [rdi-28h], xmm0
0x1800244fc  mov     [rdi+48h], rsi
0x180024500  mov     [rdi+50h], r10
0x180024504  xor     eax, eax
0x180024506  mov     [rcx], ax
0x180024509  mov     [rdi-18h], rsi
0x18002450d  mov     [rdi-50h], r15d
0x180024511  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180024516  mov     rcx, rbx
0x180024519  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002451e  nop
0x18002451f  mov     rax, [r12]
0x180024523  mov     [rsp+228h+var_198], rax
0x18002452b  test    rax, rax
0x18002452e  jz      short loc_180024573
0x180024530  mov     rsi, [r12]
0x180024534  mov     [rsp+228h+var_198], rsi
0x18002453c  or      ebx, 0FFFFFFFFh
0x18002453f  mov     eax, ebx
0x180024541  lock xadd [rsi+8], eax
0x180024546  add     eax, ebx
0x180024548  jnz     short loc_180024573
0x18002454a  mov     rax, [rsi]
0x18002454d  mov     rcx, rsi
0x180024550  mov     rax, [rax]
0x180024553  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024558  mov     eax, ebx
0x18002455a  lock xadd [rsi+0Ch], eax
0x18002455f  add     eax, ebx
0x180024561  jnz     short loc_180024573
0x180024563  mov     rax, [rsi]
0x180024566  mov     rcx, rsi
0x180024569  mov     rax, [rax+8]
0x18002456d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024572  nop
0x180024573  jmp     loc_1800249CF
0x180024578  lea     rbx, [rdi+80h]
0x18002457f  mov     [rsp+228h+var_190], rbx
0x180024587  mov     [rbx], rsi
0x18002458a  lea     rdx, [rdi+0A0h]
0x180024591  mov     rcx, [r8+10h]
0x180024595  call    ?GetCloudStore@SharedCloudStoreState@details@wil@@QEAA?BUCloudStore@Cloud@Storage@Internal@Windows@winrt@@XZ; wil::details::SharedCloudStoreState::GetCloudStore(void)
0x18002459a  mov     qword ptr [rsp+228h+var_1A8], rax
0x1800245a2  mov     rcx, [rdi+2A8h]
0x1800245a9  mov     [rdi+0A8h], rcx
0x1800245b0  mov     rcx, [rdi+2A0h]
0x1800245b7  mov     [rdi+0C8h], rcx
0x1800245be  mov     rax, [r13+270h]
0x1800245c5  mov     [rsp+228h+var_1C8], rax
0x1800245ca  lea     rcx, [rdi+108h]
0x1800245d1  call    ??$GetTypeNameWideString@UScenarioKeysItemPdr@Passkey@Security@Data@Windows@@@ProfileDataStore@wil@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; wil::ProfileDataStore::GetTypeNameWideString<Windows::Data::Security::Passkey::ScenarioKeysItemPdr>(void)
0x1800245d6  mov     rcx, rax
0x1800245d9  mov     rdx, [rax+10h]
0x1800245dd  cmp     qword ptr [rax+18h], 7
0x1800245e2  jbe     short loc_1800245E7
0x1800245e4  mov     rcx, [rax]
0x1800245e7  test    edx, edx
0x1800245e9  jnz     short loc_1800245F0
0x1800245eb  mov     rax, rsi
0x1800245ee  jmp     short loc_180024616
0x1800245f0  mov     eax, edx
0x1800245f2  cmp     [rcx+rax*2], si
0x1800245f6  jz      short loc_1800245FF
0x1800245f8  call    cs:__imp_abort
0x1800245ff  lea     rax, [rdi+0F0h]
0x180024606  mov     [rax], r15d
0x180024609  mov     [rdi+0F4h], edx
0x18002460f  mov     [rdi+100h], rcx
0x180024616  mov     [rdi+0E8h], rax
0x18002461d  lea     r15, [rdi+148h]
0x180024624  mov     rdx, [rdi+280h]
0x18002462b  mov     rcx, r15
0x18002462e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180024633  nop
0x180024634  mov     rdx, [rdi+158h]
0x18002463b  mov     [rsp+228h+var_138], rdx
0x180024643  mov     rax, [rdi+160h]
0x18002464a  mov     [rsp+228h+var_130], rax
0x180024652  cmp     rax, 7
0x180024656  jbe     short loc_180024665
0x180024658  mov     rcx, [r15]
0x18002465b  mov     [rsp+228h+var_148], rcx
0x180024663  jmp     short loc_180024668
0x180024665  mov     rcx, r15
0x180024668  test    edx, edx
0x18002466a  jnz     short loc_180024671
0x18002466c  mov     rax, rsi
0x18002466f  jmp     short loc_18002469A
0x180024671  mov     eax, edx
0x180024673  cmp     [rcx+rax*2], si
0x180024677  jz      short loc_180024680
0x180024679  call    cs:__imp_abort
0x180024680  lea     rax, [rdi+130h]
0x180024687  mov     dword ptr [rax], 1
0x18002468d  mov     [rdi+134h], edx
0x180024693  mov     [rdi+140h], rcx
0x18002469a  mov     [rdi+128h], rax
0x1800246a1  lea     r15, [rdi+188h]
0x1800246a8  mov     rdx, [rdi+280h]
0x1800246af  add     rdx, 20h ; ' '
0x1800246b3  mov     rcx, r15
0x1800246b6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800246bb  nop
0x1800246bc  mov     rdx, [rdi+198h]
0x1800246c3  mov     [rsp+228h+var_118], rdx
0x1800246cb  mov     rax, [rdi+1A0h]
0x1800246d2  mov     [rsp+228h+var_110], rax
0x1800246da  cmp     rax, 7
0x1800246de  jbe     short loc_1800246ED
0x1800246e0  mov     rcx, [r15]
0x1800246e3  mov     [rsp+228h+var_128], rcx
0x1800246eb  jmp     short loc_1800246F0
0x1800246ed  mov     rcx, r15
0x1800246f0  test    edx, edx
0x1800246f2  jnz     short loc_1800246F9
0x1800246f4  mov     rax, rsi
0x1800246f7  jmp     short loc_180024722
0x1800246f9  mov     eax, edx
0x1800246fb  cmp     [rcx+rax*2], si
0x1800246ff  jz      short loc_180024708
0x180024701  call    cs:__imp_abort
0x180024708  lea     rax, [rdi+170h]
0x18002470f  mov     dword ptr [rax], 1
0x180024715  mov     [rdi+174h], edx
0x18002471b  mov     [rdi+180h], rcx
0x180024722  mov     [rdi+168h], rax
0x180024729  mov     r8, [r14+270h]
0x180024730  lea     r9, [rdi+1A8h]
0x180024737  mov     rax, [r8+28h]
0x18002473b  mov     [r9], rax
0x18002473e  lea     rdx, [rdi+1C8h]
0x180024745  lea     rax, [rdi+0E8h]
0x18002474c  lea     rcx, [rdi+128h]
0x180024753  lea     r10, [rdi+168h]
0x18002475a  add     r8, 20h ; ' '
0x18002475e  lea     r11, [rdi+0A8h]
0x180024765  mov     [rsp+228h+var_1D8], r11
0x18002476a  lea     r11, [rdi+0C8h]
0x180024771  mov     [rsp+228h+var_1E0], r11
0x180024776  mov     [rsp+228h+var_1E8], r13
0x18002477b  mov     r11, [rsp+228h+var_1C8]
0x180024780  mov     [rsp+228h+var_1F0], r11
0x180024785  mov     [rsp+228h+var_1F8], rax
0x18002478a  mov     [rsp+228h+var_200], rcx
0x18002478f  mov     [rsp+228h+var_208], r10
0x180024794  mov     rcx, qword ptr [rsp+228h+var_1A8]
0x18002479c  call    ?DeleteAsync@?$consume_Windows_Internal_Storage_Cloud_ICloudStore2@UCloudStore@Cloud@Storage@Internal@Windows@winrt@@@impl@winrt@@QEBA@AEBW4PartitionKind@Cloud@Storage@Internal@Windows@3@AEBUhstring@param@3@111_KAEBW4SaveOptions@56783@11@Z; winrt::impl::consume_Windows_Internal_Storage_Cloud_ICloudStore2<winrt::Windows::Internal::Storage::Cloud::CloudStore>::DeleteAsync(winrt::Windows::Internal::Storage::Cloud::PartitionKind const &,winrt::param::hstring const &,winrt::param::hstring const &,winrt::param::hstring const &,winrt::param::hstring const &,unsigned __int64,winrt::Windows::Internal::Storage::Cloud::SaveOptions const &,winrt::param::hstring const &,winrt::param::hstring const &)
0x1800247a1  nop
0x1800247a2  lea     r13, [rdi+88h]
0x1800247a9  mov     r8, rax
0x1800247ac  lea     rdx, [rdi+2B0h]
0x1800247b3  mov     rcx, r13
0x1800247b6  call    ??0?$AsyncOpWaiter@U?$IAsyncOperation@UCloudStoreSaveResult@Cloud@Storage@Internal@Windows@winrt@@@Foundation@Windows@winrt@@UCloudStoreSaveResult@Cloud@Storage@Internal@34@@details@wil@@QEAA@AEBVcancellation_token@Concurrency@@AEBU?$IAsyncOperation@UCloudStoreSaveResult@Cloud@Storage@Internal@Windows@winrt@@@Foundation@Windows@winrt@@@Z; wil::details::AsyncOpWaiter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>,winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>::AsyncOpWaiter<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>,winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult>(Concurrency::cancellation_token const &,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Internal::Storage::Cloud::CloudStoreSaveResult> const &)
0x1800247bb  nop
0x1800247bc  lea     rcx, [rdi+1C8h]
0x1800247c3  mov     rax, [rcx]
0x1800247c6  mov     [rsp+228h+var_178], rax
0x1800247ce  test    rax, rax
0x1800247d1  jz      short loc_1800247D9
0x1800247d3  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800247d8  nop
0x1800247d9  mov     rcx, r15
0x1800247dc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800247e1  nop
0x1800247e2  lea     rcx, [rdi+148h]
0x1800247e9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800247ee  nop
0x1800247ef  lea     rcx, [rdi+108h]
0x1800247f6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800247fb  nop
0x1800247fc  lea     rcx, [rdi+0A0h]
0x180024803  mov     rax, [rcx]
0x180024806  mov     [rsp+228h+var_170], rax
0x18002480e  test    rax, rax
  ... truncated ...
```
