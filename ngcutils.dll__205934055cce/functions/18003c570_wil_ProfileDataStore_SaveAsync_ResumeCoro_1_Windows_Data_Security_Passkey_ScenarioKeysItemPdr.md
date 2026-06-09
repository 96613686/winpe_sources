# wil::ProfileDataStore::SaveAsync$_ResumeCoro$1_Windows::Data::Security::Passkey::ScenarioKeysItemPdr_

- ea: `0x18003c570`
- end: `0x18003cba0`
- name: `wil::ProfileDataStore::SaveAsync$_ResumeCoro$1_Windows::Data::Security::Passkey::ScenarioKeysItemPdr_`
- size: `1584`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18003cee0`

## callees

- `0x180003080`
- `0x180003520`
- `0x180003c97`
- `0x180003cdf`
- `0x18000cac0`
- `0x18000ce74`
- `0x18001ae30`
- `0x18003c570`
- `0x18003f378`
- `0x180042aac`
- `0x18004519c`
- `0x180045224`
- `0x180045360`
- `0x18004eaac`
- `0x18004ed50`
- `0x18004ee8c`
- `0x18004f8fc`
- `0x180061010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18003cb1f`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18003cb1f`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18003c70c`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18003c74e`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18003c9df`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18003ca21`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18003c70c`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18003c74e`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18003c9df`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18003ca21`

## pseudocode

```c
void __fastcall wil::ProfileDataStore::SaveAsync__ResumeCoro_1_Windows::Data::Security::Passkey::ScenarioKeysItemPdr_(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v4; // r15
  __int16 *v5; // rdx
  _QWORD *v6; // r8
  __int64 v7; // rdx
  signed __int32 v8; // eax
  signed __int32 v9; // ett
  __int64 v10; // rcx
  volatile signed __int32 *v11; // r14
  int v12; // eax
  HANDLE v13; // rax
  volatile signed __int32 *v14; // r14
  int v15; // eax
  HANDLE v16; // rax
  volatile signed __int32 *v17; // r14
  volatile signed __int32 *v18; // r14
  volatile signed __int32 **v19; // r13
  __int64 v20; // rax
  volatile signed __int32 **v21; // r12
  struct winrt::hstring *v22; // rdx
  __int64 v23; // r10
  int v24; // r11d
  _QWORD *v25; // r9
  _QWORD *v26; // r8
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // rdx
  __int64 v31; // r8
  __int64 v32; // rcx
  volatile signed __int32 *v33; // r14
  int v34; // eax
  HANDLE ProcessHeap; // rax
  volatile signed __int32 *v36; // r14
  int v37; // eax
  HANDLE v38; // rax
  volatile signed __int32 *v39; // r14
  volatile signed __int32 *v40; // rdi
  int v41; // [rsp+20h] [rbp-108h]
  struct winrt::hstring *v42; // [rsp+68h] [rbp-C0h]
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+0h]

  v4 = a1 + 8;
  v5 = &_ImageBase;
  switch ( *(_WORD *)(a1 + 8) )
  {
    case 0xFFFF:
    case 1:
    case 3:
      goto LABEL_64;
    case 2:
      if ( !*(_QWORD *)(a1 + 264) )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x53F,
          (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil\\profiledatastore.h",
          (const char *)0x80070057LL,
          v41);
      if ( !*(_QWORD *)(a1 + 296) )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x540,
          (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil\\profiledatastore.h",
          (const char *)0x80070057LL,
          v41);
      std::make_shared<wil::ProfileDataItemReference<Windows::Data::Security::Passkey::PasskeyItemPdr>,wil::ProfileDataItemReference<Windows::Data::Security::Passkey::PasskeyItemPdr> const &>(
        a1 + 16,
        *(_QWORD *)(a1 + 256));
      v6 = *(_QWORD **)(v4 + 224);
      *(_QWORD *)(a1 + 32) = 0;
      *(_QWORD *)(a1 + 40) = 0;
      v7 = v6[1];
      if ( !v7 )
        goto LABEL_12;
      v8 = *(_DWORD *)(v7 + 8);
      do
      {
        if ( !v8 )
LABEL_12:
          std::_Throw_bad_weak_ptr();
        v9 = v8;
        v8 = _InterlockedCompareExchange((volatile signed __int32 *)(v7 + 8), v8 + 1, v8);
      }
      while ( v9 != v8 );
      *(_QWORD *)(a1 + 32) = *v6;
      *(_QWORD *)(a1 + 40) = v6[1];
      winrt::to_hstring<char const *,0>(a1 + 48, a1 + 264);
      winrt::hstring::hstring((winrt::hstring *)(a1 + 56), *(const unsigned __int16 **)(a1 + 296));
      *(_BYTE *)(a1 + 64) = 0;
      *(_WORD *)v4 = 4;
      `winrt::resume_background'::`2'::awaitable::await_suspend(v10, a1);
      break;
    case 4:
      *(_QWORD *)(a1 + 80) = a1 + 72;
      v19 = (volatile signed __int32 **)(a1 + 48);
      v20 = *(_QWORD *)(a1 + 272);
      if ( v20 )
        _InterlockedAdd((volatile signed __int32 *)(v20 + 8), 1u);
      *(_QWORD *)(a1 + 72) = v20;
      *(_QWORD *)(a1 + 96) = a1 + 88;
      v42 = (struct winrt::hstring *)winrt::hstring::hstring(
                                       (winrt::hstring *)(a1 + 88),
                                       (const struct winrt::hstring *)(a1 + 48));
      v21 = (volatile signed __int32 **)(a1 + 56);
      v22 = (struct winrt::hstring *)winrt::hstring::hstring(
                                       (winrt::hstring *)(a1 + 104),
                                       (const struct winrt::hstring *)(a1 + 56));
      v23 = *(_QWORD *)(a1 + 288);
      v24 = *(_DWORD *)(a1 + 280);
      v25 = (_QWORD *)(a1 + 112);
      *(_QWORD *)(a1 + 112) = 0;
      *(_QWORD *)(a1 + 120) = 0;
      if ( *(_QWORD *)(a1 + 24) )
        _InterlockedAdd((volatile signed __int32 *)(*(_QWORD *)(a1 + 24) + 8LL), 1u);
      *v25 = *(_QWORD *)(a1 + 16);
      *(_QWORD *)(a1 + 120) = *(_QWORD *)(a1 + 24);
      v26 = (_QWORD *)(a1 + 128);
      *(_QWORD *)(a1 + 128) = 0;
      *(_QWORD *)(a1 + 136) = 0;
      v27 = *(_QWORD *)(a1 + 248);
      if ( v27 )
        _InterlockedAdd((volatile signed __int32 *)(v27 + 8), 1u);
      *v26 = *(_QWORD *)(a1 + 240);
      *(_QWORD *)(a1 + 136) = *(_QWORD *)(a1 + 248);
      v28 = wil::ProfileDataStore::SaveInternalAsync<Windows::Data::Security::Passkey::ScenarioKeysItemPdr>(
              *(_QWORD *)(v4 + 224),
              (int)a1 + 144,
              (int)v26,
              (int)v25,
              v24,
              v23,
              v22,
              v42,
              a1 + 72);
      v29 = wil::details::coro::task_base<wil::ProfileDataStoreSaveResult>::get(v28, a1 + 152);
      *(_QWORD *)(a1 - 72) = *(_QWORD *)v29;
      *(_DWORD *)(a1 - 64) = *(_DWORD *)(v29 + 8);
      *(_DWORD *)(a1 - 60) = *(_DWORD *)(v29 + 12);
      *(_OWORD *)(a1 - 56) = 0;
      *(_QWORD *)(a1 - 40) = 0;
      *(_QWORD *)(a1 - 32) = 0;
      *(_OWORD *)(a1 - 56) = *(_OWORD *)(v29 + 16);
      *(_OWORD *)(a1 - 40) = *(_OWORD *)(v29 + 32);
      *(_QWORD *)(v29 + 32) = 0;
      *(_QWORD *)(v29 + 40) = 7;
      *(_WORD *)(v29 + 16) = 0;
      *(_QWORD *)(a1 - 24) = *(_QWORD *)(v29 + 48);
      *(_DWORD *)(a1 - 80) = 1;
      std::wstring::~wstring(a1 + 168, v30, v31);
      v32 = *(_QWORD *)(a1 + 144);
      *(_QWORD *)(a1 + 144) = 0;
      if ( v32 && _InterlockedExchange64((volatile __int64 *)(v32 + 8), 2) )
      {
        *(_QWORD *)(v32 + 104) |= 1uLL;
        (*(void (__fastcall **)(__int64))(v32 + 96))(v32 + 96);
      }
      v33 = *v21;
      if ( *v21 )
      {
        v34 = _InterlockedDecrement(v33 + 6);
        if ( v34 )
        {
          if ( v34 < 0 )
            abort();
        }
        else
        {
          ProcessHeap = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v33);
        }
        *v21 = 0;
      }
      v36 = *v19;
      if ( *v19 )
      {
        v37 = _InterlockedDecrement(v36 + 6);
        if ( v37 )
        {
          if ( v37 < 0 )
            abort();
        }
        else
        {
          v38 = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(v38, 0, (LPVOID)v36);
        }
        *v19 = 0;
      }
      if ( *(_QWORD *)(a1 + 40) )
      {
        v39 = *(volatile signed __int32 **)(a1 + 40);
        if ( _InterlockedExchangeAdd(v39 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v39)(v39);
          if ( _InterlockedExchangeAdd(v39 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v39 + 8LL))(v39);
        }
      }
      if ( *(_QWORD *)(a1 + 24) )
      {
        v40 = *(volatile signed __int32 **)(a1 + 24);
        if ( _InterlockedExchangeAdd(v40 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v40)(v40);
          if ( _InterlockedExchangeAdd(v40 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v40 + 8LL))(v40);
        }
      }
      *(_QWORD *)(a1 + 208) = a1 - 96;
      *(_WORD *)v4 = 0;
      `wil::details::coro::promise_base<wil::ProfileDataStoreSaveResult>::final_suspend'::`2'::awaiter::await_suspend();
      return;
    case 5:
      v11 = *(volatile signed __int32 **)(a1 + 56);
      if ( v11 )
      {
        v12 = _InterlockedDecrement(v11 + 6);
        if ( v12 )
        {
          if ( v12 < 0 )
            abort();
        }
        else
        {
          v13 = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(v13, 0, (LPVOID)v11);
        }
        *(_QWORD *)(a1 + 56) = 0;
      }
      v14 = *(volatile signed __int32 **)(a1 + 48);
      if ( v14 )
      {
        v15 = _InterlockedDecrement(v14 + 6);
        if ( v15 )
        {
          if ( v15 < 0 )
            abort();
        }
        else
        {
          v16 = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(v16, 0, (LPVOID)v14);
        }
        *(_QWORD *)(a1 + 48) = 0;
      }
      if ( *(_QWORD *)(a1 + 40) )
      {
        v17 = *(volatile signed __int32 **)(a1 + 40);
        if ( _InterlockedExchangeAdd(v17 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v17)(v17);
          if ( _InterlockedExchangeAdd(v17 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 8LL))(v17);
        }
      }
      if ( *(_QWORD *)(a1 + 24) )
      {
        v18 = *(volatile signed __int32 **)(a1 + 24);
        if ( _InterlockedExchangeAdd(v18 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v18)(v18);
          if ( _InterlockedExchangeAdd(v18 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v18 + 8LL))(v18);
        }
      }
LABEL_64:
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
      `wil::ProfileDataStore::SaveAsync<Windows::Data::Security::Passkey::ScenarioKeysItemPdr>'::`3'::_parameters_::~_parameters_(v4 + 224);
      if ( *(_WORD *)(a1 + 10) )
        operator delete((void *)(a1 - 96), 0x190u);
      break;
    default:
      __debugbreak();
      break;
  }
}

```

## disassembly

```asm
0x18003c570  mov     r11, rsp
0x18003c573  mov     [r11+10h], rbx
0x18003c577  mov     [r11+18h], rsi
0x18003c57b  mov     [r11+8], rcx
0x18003c57f  push    rdi
0x18003c580  push    r12
0x18003c582  push    r13
0x18003c584  push    r14
0x18003c586  push    r15
0x18003c588  sub     rsp, 100h
0x18003c58f  mov     rax, cs:__security_cookie
0x18003c596  xor     rax, rsp
0x18003c599  mov     [rsp+128h+var_38], rax
0x18003c5a1  mov     rbx, rcx
0x18003c5a4  mov     [rsp+128h+var_B0], rcx
0x18003c5a9  lea     r15, [rbx+8]
0x18003c5ad  movzx   eax, word ptr [r15]
0x18003c5b1  mov     [rsp+128h+var_D8], ax
0x18003c5b6  mov     r14d, 1
0x18003c5bc  add     ax, r14w
0x18003c5c0  cmp     ax, 6; switch 7 cases
0x18003c5c4  ja      def_18003C5E7; jumptable 000000018003C5E7 default case, case 1
0x18003c5ca  mov     [rsp+128h+var_90], r15
0x18003c5d2  movsx   rax, ax
0x18003c5d6  lea     rdx, __ImageBase
0x18003c5dd  mov     ecx, ds:(jpt_18003C5E7 - 180000000h)[rdx+rax*4]
0x18003c5e4  add     rcx, rdx
0x18003c5e7  jmp     rcx; switch jump
0x18003c5e9  xor     edi, edi; jumptable 000000018003C5E7 case 4
0x18003c5eb  jmp     loc_18003CAF0
0x18003c5f0  xor     edi, edi; jumptable 000000018003C5E7 case 3
0x18003c5f2  lea     rsi, [rbx+108h]
0x18003c5f9  mov     rcx, [rsp+128h]; this
0x18003c601  cmp     [rsi], rdi
0x18003c604  jnz     short loc_18003C61D
0x18003c606  mov     r9d, 80070057h; char *
0x18003c60c  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\sdk\\inc\\wil\\pr"...
0x18003c613  mov     edx, 53Fh; void *
0x18003c618  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003c61d  mov     rcx, [rsp+128h]; this
0x18003c625  cmp     [rbx+128h], rdi
0x18003c62c  jnz     short loc_18003C645
0x18003c62e  mov     r9d, 80070057h; char *
0x18003c634  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\sdk\\inc\\wil\\pr"...
0x18003c63b  mov     edx, 540h; void *
0x18003c640  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003c645  lea     rcx, [rbx+10h]
0x18003c649  mov     rdx, [rbx+100h]
0x18003c650  call    ??$make_shared@V?$ProfileDataItemReference@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@wil@@AEBV12@@std@@YA?AV?$shared_ptr@V?$ProfileDataItemReference@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@wil@@@0@AEBV?$ProfileDataItemReference@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@wil@@@Z; std::make_shared<wil::ProfileDataItemReference<Windows::Data::Security::Passkey::PasskeyItemPdr>,wil::ProfileDataItemReference<Windows::Data::Security::Passkey::PasskeyItemPdr> const &>(wil::ProfileDataItemReference<Windows::Data::Security::Passkey::PasskeyItemPdr> const &)
0x18003c655  nop
0x18003c656  mov     r8, [r15+0E0h]
0x18003c65d  mov     [rbx+20h], rdi
0x18003c661  mov     [rbx+28h], rdi
0x18003c665  mov     rdx, [r8+8]
0x18003c669  test    rdx, rdx
0x18003c66c  jz      short loc_18003C6CA
0x18003c66e  mov     eax, [rdx+8]
0x18003c671  jmp     short loc_18003C67D
0x18003c673  lea     ecx, [rax+1]
0x18003c676  lock cmpxchg [rdx+8], ecx
0x18003c67b  jz      short loc_18003C683
0x18003c67d  test    eax, eax
0x18003c67f  jnz     short loc_18003C673
0x18003c681  jmp     short loc_18003C6CA
0x18003c683  mov     rax, [r8]
0x18003c686  mov     [rbx+20h], rax
0x18003c68a  mov     rax, [r8+8]
0x18003c68e  mov     [rbx+28h], rax
0x18003c692  lea     rcx, [rbx+30h]
0x18003c696  mov     rdx, rsi
0x18003c699  call    ??$to_hstring@PEBD$0A@@winrt@@YA?AUhstring@0@AEBQEBD@Z; winrt::to_hstring<char const *,0>(char const * const &)
0x18003c69e  nop
0x18003c69f  lea     rcx, [rbx+38h]; this
0x18003c6a3  mov     rdx, [rbx+128h]; unsigned __int16 *
0x18003c6aa  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x18003c6af  nop
0x18003c6b0  mov     [rbx+40h], dil
0x18003c6b4  mov     eax, 4
0x18003c6b9  mov     [r15], ax
0x18003c6bd  mov     rdx, rbx
0x18003c6c0  call    ?await_suspend@awaitable@?1??resume_background@winrt@@YA@XZ@QEBAXU?$coroutine_handle@X@experimental@std@@@Z; `winrt::resume_background(void)'::`2'::awaitable::await_suspend(std::experimental::coroutine_handle<void>)
0x18003c6c5  jmp     loc_18003CB54
0x18003c6ca  call    ?_Throw_bad_weak_ptr@std@@YAXXZ; std::_Throw_bad_weak_ptr(void)
0x18003c6d0  mov     r14, [rbx+38h]; jumptable 000000018003C5E7 case 6
0x18003c6d4  mov     [rsp+128h+var_A0], r14
0x18003c6dc  xor     edi, edi
0x18003c6de  or      esi, 0FFFFFFFFh
0x18003c6e1  test    r14, r14
0x18003c6e4  jz      short loc_18003C717
0x18003c6e6  mov     eax, esi
0x18003c6e8  lock xadd [r14+18h], eax
0x18003c6ee  sub     eax, 1
0x18003c6f1  jnz     short loc_18003C708
0x18003c6f3  nop
0x18003c6f4  call    WINRT_IMPL_GetProcessHeap
0x18003c6f9  mov     rcx, rax; hHeap
0x18003c6fc  mov     r8, r14; lpMem
0x18003c6ff  xor     edx, edx; dwFlags
0x18003c701  call    WINRT_IMPL_HeapFree
0x18003c706  jmp     short loc_18003C713
0x18003c708  test    eax, eax
0x18003c70a  jns     short loc_18003C713
0x18003c70c  call    cs:__imp_abort
0x18003c713  mov     [rbx+38h], rdi
0x18003c717  mov     r14, [rbx+30h]
0x18003c71b  mov     [rsp+128h+var_98], r14
0x18003c723  test    r14, r14
0x18003c726  jz      short loc_18003C759
0x18003c728  mov     eax, esi
0x18003c72a  lock xadd [r14+18h], eax
0x18003c730  sub     eax, 1
0x18003c733  jnz     short loc_18003C74A
0x18003c735  nop
0x18003c736  call    WINRT_IMPL_GetProcessHeap
0x18003c73b  mov     rcx, rax; hHeap
0x18003c73e  mov     r8, r14; lpMem
0x18003c741  xor     edx, edx; dwFlags
0x18003c743  call    WINRT_IMPL_HeapFree
0x18003c748  jmp     short loc_18003C755
0x18003c74a  test    eax, eax
0x18003c74c  jns     short loc_18003C755
0x18003c74e  call    cs:__imp_abort
0x18003c755  mov     [rbx+30h], rdi
0x18003c759  mov     rax, [rbx+28h]
0x18003c75d  mov     [rsp+128h+var_B8], rax
0x18003c762  test    rax, rax
0x18003c765  jz      short loc_18003C7A6
0x18003c767  mov     r14, [rbx+28h]
0x18003c76b  mov     [rsp+128h+var_B8], r14
0x18003c770  mov     eax, esi
0x18003c772  lock xadd [r14+8], eax
0x18003c778  add     eax, esi
0x18003c77a  jnz     short loc_18003C7A6
0x18003c77c  mov     rax, [r14]
0x18003c77f  mov     rcx, r14
0x18003c782  mov     rax, [rax]
0x18003c785  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c78a  mov     eax, esi
0x18003c78c  lock xadd [r14+0Ch], eax
0x18003c792  add     eax, esi
0x18003c794  jnz     short loc_18003C7A6
0x18003c796  mov     rax, [r14]
0x18003c799  mov     rcx, r14
0x18003c79c  mov     rax, [rax+8]
0x18003c7a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c7a5  nop
0x18003c7a6  mov     rax, [rbx+18h]
0x18003c7aa  mov     [rsp+128h+var_C8], rax
0x18003c7af  test    rax, rax
0x18003c7b2  jz      short loc_18003C7F3
0x18003c7b4  mov     r14, [rbx+18h]
0x18003c7b8  mov     [rsp+128h+var_C8], r14
0x18003c7bd  mov     eax, esi
0x18003c7bf  lock xadd [r14+8], eax
0x18003c7c5  add     eax, esi
0x18003c7c7  jnz     short loc_18003C7F3
0x18003c7c9  mov     rax, [r14]
0x18003c7cc  mov     rcx, r14
0x18003c7cf  mov     rax, [rax]
0x18003c7d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c7d7  mov     eax, esi
0x18003c7d9  lock xadd [r14+0Ch], eax
0x18003c7df  add     eax, esi
0x18003c7e1  jnz     short loc_18003C7F3
0x18003c7e3  mov     rax, [r14]
0x18003c7e6  mov     rcx, r14
0x18003c7e9  mov     rax, [rax+8]
0x18003c7ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c7f2  nop
0x18003c7f3  jmp     loc_18003CAF0
0x18003c7f8  lea     rsi, [rbx+48h]; jumptable 000000018003C5E7 case 5
0x18003c7fc  mov     [rbx+50h], rsi
0x18003c800  lea     r13, [rbx+30h]
0x18003c804  mov     rax, [r13+0E0h]
0x18003c80b  xor     edi, edi
0x18003c80d  test    rax, rax
0x18003c810  jz      short loc_18003C817
0x18003c812  lock add [rax+8], r14d
0x18003c817  mov     [rsi], rax
0x18003c81a  lea     rcx, [rbx+58h]; this
0x18003c81e  mov     [rbx+60h], rcx
0x18003c822  mov     rdx, r13; struct winrt::hstring *
0x18003c825  call    ??0hstring@winrt@@QEAA@AEBU01@@Z; winrt::hstring::hstring(winrt::hstring const &)
0x18003c82a  mov     [rsp+128h+var_C0], rax
0x18003c82f  lea     rcx, [rbx+68h]; this
0x18003c833  lea     r12, [rbx+38h]
0x18003c837  mov     rdx, r12; struct winrt::hstring *
0x18003c83a  call    ??0hstring@winrt@@QEAA@AEBU01@@Z; winrt::hstring::hstring(winrt::hstring const &)
0x18003c83f  mov     rdx, rax
0x18003c842  mov     r10, [rbx+120h]
0x18003c849  mov     r11d, [r12+0E0h]
0x18003c851  lea     r9, [rbx+70h]; int
0x18003c855  mov     [r9], rdi
0x18003c858  mov     [rbx+78h], rdi
0x18003c85c  mov     rcx, [rbx+18h]
0x18003c860  mov     [rsp+128h+var_C8], rcx
0x18003c865  test    rcx, rcx
0x18003c868  jz      short loc_18003C878
0x18003c86a  mov     rax, [rbx+18h]
0x18003c86e  mov     [rsp+128h+var_C8], rax
0x18003c873  lock add [rax+8], r14d
0x18003c878  mov     rax, [rbx+10h]
0x18003c87c  mov     [rsp+128h+var_D0], rax
0x18003c881  mov     [r9], rax
0x18003c884  mov     rax, [rbx+18h]
0x18003c888  mov     [rsp+128h+var_C8], rax
0x18003c88d  mov     [rbx+78h], rax
0x18003c891  lea     r8, [rbx+80h]; int
0x18003c898  mov     [r8], rdi
0x18003c89b  mov     [rbx+88h], rdi
0x18003c8a2  mov     rax, [rbx+0F8h]
0x18003c8a9  test    rax, rax
0x18003c8ac  jz      short loc_18003C8B3
0x18003c8ae  lock add [rax+8], r14d
0x18003c8b3  mov     rax, [rbx+0F0h]
0x18003c8ba  mov     [r8], rax
0x18003c8bd  mov     rax, [rbx+0F8h]
0x18003c8c4  mov     [rbx+88h], rax
0x18003c8cb  lea     r14, [rbx+90h]
0x18003c8d2  mov     [rsp+128h+var_E8], rsi; __int64
0x18003c8d7  mov     rax, [rsp+128h+var_C0]
0x18003c8dc  mov     [rsp+128h+var_F0], rax; struct winrt::hstring *
0x18003c8e1  mov     [rsp+128h+var_F8], rdx; struct winrt::hstring *
0x18003c8e6  mov     [rsp+128h+var_100], r10; __int64
0x18003c8eb  mov     [rsp+128h+var_108], r11d; int
0x18003c8f0  mov     rdx, r14; int
0x18003c8f3  mov     rcx, [r15+0E0h]; int
0x18003c8fa  call    ??$SaveInternalAsync@UScenarioKeysItemPdr@Passkey@Security@Data@Windows@@@ProfileDataStore@wil@@AEAA?AU?$task@VProfileDataStoreSaveResult@wil@@@1@V?$shared_ptr@V?$ProfileDataItem@UScenarioKeysItemPdr@Passkey@Security@Data@Windows@@@wil@@@std@@V?$shared_ptr@V?$ProfileDataItemReference@UScenarioKeysItemPdr@Passkey@Security@Data@Windows@@@wil@@@4@W4ProfileDataStoreSaveOptions@1@_KUhstring@winrt@@4Vcancellation_token@Concurrency@@@Z; wil::ProfileDataStore::SaveInternalAsync<Windows::Data::Security::Passkey::ScenarioKeysItemPdr>(std::shared_ptr<wil::ProfileDataItem<Windows::Data::Security::Passkey::ScenarioKeysItemPdr>>,std::shared_ptr<wil::ProfileDataItemReference<Windows::Data::Security::Passkey::ScenarioKeysItemPdr>>,wil::ProfileDataStoreSaveOptions,unsigned __int64,winrt::hstring,winrt::hstring,Concurrency::cancellation_token)
0x18003c8ff  nop
0x18003c900  lea     rdx, [rbx+98h]
0x18003c907  mov     rcx, rax
0x18003c90a  call    ?get@?$task_base@VProfileDataStoreSaveResult@wil@@@coro@details@wil@@QEHAA@XZ; wil::details::coro::task_base<wil::ProfileDataStoreSaveResult>::get(void)
0x18003c90f  mov     rcx, [rax]
0x18003c912  mov     [rbx-48h], rcx
0x18003c916  mov     ecx, [rax+8]
0x18003c919  mov     [rbx-40h], ecx
0x18003c91c  mov     ecx, [rax+0Ch]
0x18003c91f  mov     [rbx-3Ch], ecx
0x18003c922  xorps   xmm0, xmm0
0x18003c925  movups  xmmword ptr [rbx-38h], xmm0
0x18003c929  mov     [rbx-28h], rdi
0x18003c92d  mov     [rbx-20h], rdi
0x18003c931  movups  xmm0, xmmword ptr [rax+10h]
0x18003c935  movups  xmmword ptr [rbx-38h], xmm0
0x18003c939  movups  xmm1, xmmword ptr [rax+20h]
0x18003c93d  movups  xmmword ptr [rbx-28h], xmm1
0x18003c941  mov     [rax+20h], rdi
0x18003c945  mov     qword ptr [rax+28h], 7
0x18003c94d  xor     ecx, ecx
0x18003c94f  mov     [rax+10h], cx
0x18003c953  mov     rax, [rax+30h]
0x18003c957  mov     [rbx-18h], rax
0x18003c95b  mov     dword ptr [rbx-50h], 1
0x18003c962  lea     rcx, [rbx+0A8h]
0x18003c969  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003c96e  nop
0x18003c96f  mov     rcx, [r14]
0x18003c972  mov     [rsp+128h+var_88], rcx
0x18003c97a  mov     [r14], rdi
0x18003c97d  test    rcx, rcx
0x18003c980  jz      short loc_18003C9A5
0x18003c982  mov     eax, 2
0x18003c987  xchg    rax, [rcx+8]
0x18003c98b  test    rax, rax
0x18003c98e  jz      short loc_18003C9A5
0x18003c990  lea     rax, [rcx+60h]
0x18003c994  or      qword ptr [rax+8], 1
0x18003c999  mov     rcx, rax
0x18003c99c  mov     rax, [rax]
0x18003c99f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c9a4  nop
0x18003c9a5  mov     r14, [r12]
0x18003c9a9  mov     [rsp+128h+var_A0], r14
0x18003c9b1  or      esi, 0FFFFFFFFh
0x18003c9b4  test    r14, r14
0x18003c9b7  jz      short loc_18003C9EA
0x18003c9b9  mov     eax, esi
0x18003c9bb  lock xadd [r14+18h], eax
0x18003c9c1  sub     eax, 1
0x18003c9c4  jnz     short loc_18003C9DB
0x18003c9c6  nop
0x18003c9c7  call    WINRT_IMPL_GetProcessHeap
0x18003c9cc  mov     rcx, rax; hHeap
0x18003c9cf  mov     r8, r14; lpMem
0x18003c9d2  xor     edx, edx; dwFlags
0x18003c9d4  call    WINRT_IMPL_HeapFree
0x18003c9d9  jmp     short loc_18003C9E6
0x18003c9db  test    eax, eax
0x18003c9dd  jns     short loc_18003C9E6
0x18003c9df  call    cs:__imp_abort
0x18003c9e6  mov     [r12], rdi
0x18003c9ea  mov     r14, [r13+0]
0x18003c9ee  mov     [rsp+128h+var_98], r14
0x18003c9f6  test    r14, r14
0x18003c9f9  jz      short loc_18003CA2C
0x18003c9fb  mov     eax, esi
0x18003c9fd  lock xadd [r14+18h], eax
0x18003ca03  sub     eax, 1
0x18003ca06  jnz     short loc_18003CA1D
0x18003ca08  nop
  ... truncated ...
```
