# wil::ProfileDataStore::GetCollectionItemIdsAsync$_ResumeCoro$1_Windows::Data::Security::Passkey::RecoveryItemPdr_

- ea: `0x1800334a0`
- end: `0x180033ae4`
- name: `wil::ProfileDataStore::GetCollectionItemIdsAsync$_ResumeCoro$1_Windows::Data::Security::Passkey::RecoveryItemPdr_`
- size: `1604`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18003206c`

## callees

- `0x180003080`
- `0x180003520`
- `0x180003c97`
- `0x180003cdf`
- `0x18000cac0`
- `0x18000ce74`
- `0x18001ae30`
- `0x180026f60`
- `0x1800334a0`
- `0x18004519c`
- `0x180045224`
- `0x18004eaac`
- `0x18004ead4`
- `0x18004ed50`
- `0x18004ed9c`
- `0x18004f554`
- `0x180061010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180033a37`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180033a37`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180033669`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800336a8`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800336ea`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800338fb`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180033939`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18003397a`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180033669`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800336a8`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800336ea`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800338fb`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180033939`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18003397a`

## pseudocode

```c
void __fastcall wil::ProfileDataStore::GetCollectionItemIdsAsync__ResumeCoro_1_Windows::Data::Security::Passkey::RecoveryItemPdr_(
        __int64 a1)
{
  __int64 v2; // r12
  __int64 v3; // r8
  __int16 *v4; // rdx
  _QWORD *v5; // r8
  __int64 v6; // rdx
  signed __int32 v7; // eax
  signed __int32 v8; // ett
  __int64 v9; // rcx
  volatile signed __int32 *v10; // rbx
  int v11; // eax
  HANDLE v12; // rax
  volatile signed __int32 *v13; // rbx
  int v14; // eax
  HANDLE v15; // rax
  volatile signed __int32 *v16; // rbx
  int v17; // eax
  HANDLE v18; // rax
  volatile signed __int32 *v19; // rbx
  __int64 v20; // rax
  volatile signed __int32 **v21; // r13
  volatile signed __int32 **v22; // r15
  int v23; // r8d
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // r8
  __int64 v27; // rdx
  __int64 v28; // rcx
  __int64 v29; // rcx
  volatile signed __int32 *v30; // rbx
  int v31; // eax
  HANDLE ProcessHeap; // rax
  volatile signed __int32 *v33; // rbx
  int v34; // eax
  HANDLE v35; // rax
  volatile signed __int32 *v36; // rbx
  int v37; // eax
  HANDLE v38; // rax
  volatile signed __int32 *v39; // rbx
  volatile signed __int32 *v40; // rcx
  int v41; // [rsp+20h] [rbp-108h]
  int v42; // [rsp+40h] [rbp-E8h]
  int v43; // [rsp+48h] [rbp-E0h]
  __int64 v44; // [rsp+58h] [rbp-D0h]
  __int64 v45; // [rsp+68h] [rbp-C0h]
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+0h]

  v2 = a1 + 8;
  v3 = 1;
  v4 = &_ImageBase;
  switch ( *(_WORD *)(a1 + 8) )
  {
    case 0xFFFF:
    case 1:
    case 3:
      goto LABEL_66;
    case 2:
      if ( !*(_QWORD *)(a1 + 256) )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x495,
          (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil\\profiledatastore.h",
          (const char *)0x80070057LL,
          v41);
      if ( !*(_QWORD *)(a1 + 240) )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x496,
          (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil\\profiledatastore.h",
          (const char *)0x80070057LL,
          v41);
      if ( !*(_QWORD *)(a1 + 272) )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x497,
          (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil\\profiledatastore.h",
          (const char *)0x80070057LL,
          v41);
      v5 = *(_QWORD **)(a1 + 232);
      *(_QWORD *)(a1 + 16) = 0;
      *(_QWORD *)(a1 + 24) = 0;
      v6 = v5[1];
      if ( !v6 )
        goto LABEL_14;
      v7 = *(_DWORD *)(v6 + 8);
      do
      {
        if ( !v7 )
LABEL_14:
          std::_Throw_bad_weak_ptr();
        v8 = v7;
        v7 = _InterlockedCompareExchange((volatile signed __int32 *)(v6 + 8), v7 + 1, v7);
      }
      while ( v8 != v7 );
      *(_QWORD *)(a1 + 16) = *v5;
      *(_QWORD *)(a1 + 24) = v5[1];
      winrt::to_hstring<char const *,0>(a1 + 32, a1 + 240);
      winrt::hstring::hstring((winrt::hstring *)(a1 + 40), *(const unsigned __int16 **)(a1 + 256));
      winrt::hstring::hstring((winrt::hstring *)(a1 + 48), *(const unsigned __int16 **)(a1 + 272));
      *(_BYTE *)(a1 + 56) = 0;
      *(_WORD *)v2 = 4;
      `winrt::resume_background'::`2'::awaitable::await_suspend(v9, a1);
      break;
    case 4:
      *(_QWORD *)(a1 + 72) = a1 + 64;
      v20 = *(_QWORD *)(a1 + 248);
      if ( v20 )
        _InterlockedAdd((volatile signed __int32 *)(v20 + 8), 1u);
      *(_QWORD *)(a1 + 64) = v20;
      *(_QWORD *)(a1 + 88) = a1 + 80;
      v45 = winrt::hstring::hstring((winrt::hstring *)(a1 + 80), (const struct winrt::hstring *)(a1 + 32));
      *(_QWORD *)(a1 + 104) = a1 + 96;
      v21 = (volatile signed __int32 **)(a1 + 48);
      v44 = winrt::hstring::hstring((winrt::hstring *)(a1 + 96), (const struct winrt::hstring *)(a1 + 48));
      v43 = *(_DWORD *)(a1 + 268);
      v22 = (volatile signed __int32 **)(a1 + 40);
      v42 = *(_DWORD *)(a1 + 264);
      v23 = winrt::hstring::hstring((winrt::hstring *)(a1 + 112), (const struct winrt::hstring *)(a1 + 40));
      v24 = wil::ProfileDataStore::CallGetCollectionItemIdsAsync<Windows::Data::Security::Passkey::RecoveryItemPdr>(
              *(_QWORD *)(v2 + 224),
              (int)a1 + 120,
              v23,
              v42,
              v43,
              v44,
              v45,
              a1 + 64);
      v25 = wil::details::coro::task_base<wil::GetCollectionItemIdsResult<Windows::Data::Security::Passkey::PasskeyItemPdr>>::get(
              v24,
              a1 + 128);
      v26 = *(_QWORD *)(v25 + 16);
      *(_QWORD *)(v25 + 16) = 0;
      v27 = *(_QWORD *)(v25 + 8);
      *(_QWORD *)(v25 + 8) = 0;
      v28 = *(_QWORD *)v25;
      *(_QWORD *)v25 = 0;
      *(_QWORD *)(a1 - 88) = v28;
      *(_QWORD *)(a1 - 80) = v27;
      *(_QWORD *)(a1 - 72) = v26;
      *(_OWORD *)(a1 - 64) = 0;
      *(_QWORD *)(a1 - 48) = 0;
      *(_QWORD *)(a1 - 40) = 0;
      *(_OWORD *)(a1 - 64) = *(_OWORD *)(v25 + 24);
      *(_OWORD *)(a1 - 48) = *(_OWORD *)(v25 + 40);
      *(_QWORD *)(v25 + 40) = 0;
      *(_QWORD *)(v25 + 48) = 7;
      *(_WORD *)(v25 + 24) = 0;
      *(_DWORD *)(a1 - 32) = *(_DWORD *)(v25 + 56);
      *(_QWORD *)(a1 - 24) = *(_QWORD *)(v25 + 64);
      *(_DWORD *)(a1 - 96) = 1;
      std::wstring::~wstring(a1 + 152, v27, v26);
      std::vector<wil::ProfileDataItemReference<Windows::Data::Security::Passkey::RecoveryItemPdr>>::_Tidy(a1 + 128);
      v29 = *(_QWORD *)(a1 + 120);
      *(_QWORD *)(a1 + 120) = 0;
      if ( v29 && _InterlockedExchange64((volatile __int64 *)(v29 + 8), 2) )
      {
        *(_QWORD *)(v29 + 120) |= 1uLL;
        (*(void (__fastcall **)(__int64))(v29 + 112))(v29 + 112);
      }
      v30 = *v21;
      if ( *v21 )
      {
        v31 = _InterlockedDecrement(v30 + 6);
        if ( v31 )
        {
          if ( v31 < 0 )
            abort();
        }
        else
        {
          ProcessHeap = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v30);
        }
        *v21 = 0;
      }
      v33 = *v22;
      if ( *v22 )
      {
        v34 = _InterlockedDecrement(v33 + 6);
        if ( v34 )
        {
          if ( v34 < 0 )
            abort();
        }
        else
        {
          v35 = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(v35, 0, (LPVOID)v33);
        }
        *v22 = 0;
      }
      v36 = *(volatile signed __int32 **)(a1 + 32);
      if ( v36 )
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
        *(_QWORD *)(a1 + 32) = 0;
      }
      if ( *(_QWORD *)(a1 + 24) )
      {
        v39 = *(volatile signed __int32 **)(a1 + 24);
        if ( _InterlockedExchangeAdd(v39 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v39)(v39);
          if ( _InterlockedExchangeAdd(v39 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v39 + 8LL))(v39);
        }
      }
      *(_QWORD *)(a1 + 208) = a1 - 112;
      *(_WORD *)v2 = 0;
      `wil::details::coro::promise_base<wil::GetCollectionItemsResult<Windows::Data::Security::Passkey::PasskeyItemPdr>>::final_suspend'::`2'::awaiter::await_suspend();
      return;
    case 5:
      v10 = *(volatile signed __int32 **)(a1 + 48);
      if ( v10 )
      {
        v11 = _InterlockedDecrement(v10 + 6);
        if ( v11 )
        {
          if ( v11 < 0 )
            abort();
        }
        else
        {
          v12 = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(v12, 0, (LPVOID)v10);
        }
        *(_QWORD *)(a1 + 48) = 0;
      }
      v13 = *(volatile signed __int32 **)(a1 + 40);
      if ( v13 )
      {
        v14 = _InterlockedDecrement(v13 + 6);
        if ( v14 )
        {
          if ( v14 < 0 )
            abort();
        }
        else
        {
          v15 = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(v15, 0, (LPVOID)v13);
        }
        *(_QWORD *)(a1 + 40) = 0;
      }
      v16 = *(volatile signed __int32 **)(a1 + 32);
      if ( v16 )
      {
        v17 = _InterlockedDecrement(v16 + 6);
        if ( v17 )
        {
          if ( v17 < 0 )
            abort();
        }
        else
        {
          v18 = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(v18, 0, (LPVOID)v16);
        }
        *(_QWORD *)(a1 + 32) = 0;
      }
      if ( *(_QWORD *)(a1 + 24) )
      {
        v19 = *(volatile signed __int32 **)(a1 + 24);
        if ( !_InterlockedDecrement(v19 + 2) )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v19)(v19);
          if ( !_InterlockedDecrement(v19 + 3) )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v19 + 8LL))(v19);
        }
      }
LABEL_66:
      if ( *(_QWORD *)(a1 - 16) && wil::details::coro::g_pfnDestroyRestrictedErrorInformation )
      {
        wil::details::coro::g_pfnDestroyRestrictedErrorInformation();
        *(_QWORD *)(a1 - 16) = 0;
      }
      if ( *(_DWORD *)(a1 - 96) == 1 )
      {
        std::wstring::~wstring(a1 - 64, v4, v3);
        std::vector<wil::ProfileDataItemReference<Windows::Data::Security::Passkey::RecoveryItemPdr>>::_Tidy(a1 - 88);
      }
      else if ( *(_DWORD *)(a1 - 96) == 2 )
      {
        __ExceptionPtrDestroy((void *)(a1 - 88));
      }
      v40 = *(volatile signed __int32 **)(v2 + 240);
      if ( v40 && !_InterlockedDecrement(v40 + 2) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v40 + 8LL))(v40);
      *(_QWORD *)(v2 + 240) = 0;
      if ( *(_WORD *)(a1 + 10) )
        operator delete((void *)(a1 - 112), 0x190u);
      break;
    default:
      __debugbreak();
      break;
  }
}

```

## disassembly

```asm
0x1800334a0  mov     r11, rsp
0x1800334a3  mov     [r11+10h], rbx
0x1800334a7  mov     [r11+18h], rsi
0x1800334ab  mov     [r11+8], rcx
0x1800334af  push    rdi
0x1800334b0  push    r12
0x1800334b2  push    r13
0x1800334b4  push    r14
0x1800334b6  push    r15
0x1800334b8  sub     rsp, 100h
0x1800334bf  mov     rax, cs:__security_cookie
0x1800334c6  xor     rax, rsp
0x1800334c9  mov     [rsp+128h+var_30], rax
0x1800334d1  mov     rsi, rcx
0x1800334d4  mov     [rsp+128h+var_D8], rcx
0x1800334d9  lea     r12, [rsi+8]
0x1800334dd  movzx   eax, word ptr [r12]
0x1800334e2  mov     [rsp+128h+var_E4], ax
0x1800334e7  mov     r8d, 1
0x1800334ed  add     ax, r8w
0x1800334f1  cmp     ax, 6; switch 7 cases
0x1800334f5  ja      def_180033518; jumptable 0000000180033518 default case, case 1
0x1800334fb  mov     [rsp+128h+var_A0], r12
0x180033503  movsx   rax, ax
0x180033507  lea     rdx, __ImageBase
0x18003350e  mov     ecx, ds:(jpt_180033518 - 180000000h)[rdx+rax*4]
0x180033515  add     rcx, rdx
0x180033518  jmp     rcx; switch jump
0x18003351a  xor     edi, edi; jumptable 0000000180033518 case 4
0x18003351c  or      r14d, 0FFFFFFFFh
0x180033520  jmp     loc_180033A08
0x180033525  xor     edi, edi; jumptable 0000000180033518 case 3
0x180033527  mov     rcx, [rsp+128h]; this
0x18003352f  cmp     [rsi+100h], rdi
0x180033536  jnz     short loc_18003354F
0x180033538  mov     r9d, 80070057h; char *
0x18003353e  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\sdk\\inc\\wil\\pr"...
0x180033545  mov     edx, 495h; void *
0x18003354a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003354f  lea     r9, [rsi+0F0h]
0x180033556  mov     rcx, [rsp+128h]; this
0x18003355e  cmp     [r9], rdi
0x180033561  jnz     short loc_18003357A
0x180033563  mov     r9d, 80070057h; char *
0x180033569  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\sdk\\inc\\wil\\pr"...
0x180033570  mov     edx, 496h; void *
0x180033575  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003357a  mov     rcx, [rsp+128h]; this
0x180033582  cmp     [rsi+110h], rdi
0x180033589  jnz     short loc_1800335A2
0x18003358b  mov     r9d, 80070057h; char *
0x180033591  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\sdk\\inc\\wil\\pr"...
0x180033598  mov     edx, 497h; void *
0x18003359d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800335a2  mov     r8, [r12+0E0h]
0x1800335aa  mov     [rsi+10h], rdi
0x1800335ae  mov     [rsi+18h], rdi
0x1800335b2  mov     rdx, [r8+8]
0x1800335b6  test    rdx, rdx
0x1800335b9  jz      short loc_180033629
0x1800335bb  mov     eax, [rdx+8]
0x1800335be  jmp     short loc_1800335CA
0x1800335c0  lea     ecx, [rax+1]
0x1800335c3  lock cmpxchg [rdx+8], ecx
0x1800335c8  jz      short loc_1800335D0
0x1800335ca  test    eax, eax
0x1800335cc  jnz     short loc_1800335C0
0x1800335ce  jmp     short loc_180033629
0x1800335d0  mov     rax, [r8]
0x1800335d3  mov     [rsi+10h], rax
0x1800335d7  mov     rax, [r8+8]
0x1800335db  mov     [rsi+18h], rax
0x1800335df  mov     rdx, r9
0x1800335e2  lea     rcx, [rsi+20h]
0x1800335e6  call    ??$to_hstring@PEBD$0A@@winrt@@YA?AUhstring@0@AEBQEBD@Z; winrt::to_hstring<char const *,0>(char const * const &)
0x1800335eb  nop
0x1800335ec  lea     rcx, [rsi+28h]; this
0x1800335f0  mov     rdx, [rsi+100h]; unsigned __int16 *
0x1800335f7  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x1800335fc  nop
0x1800335fd  mov     rdx, [rsi+110h]; unsigned __int16 *
0x180033604  lea     rcx, [rsi+30h]; this
0x180033608  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x18003360d  nop
0x18003360e  mov     [rsi+38h], dil
0x180033612  mov     eax, 4
0x180033617  mov     [r12], ax
0x18003361c  mov     rdx, rsi
0x18003361f  call    ?await_suspend@awaitable@?1??resume_background@winrt@@YA@XZ@QEBAXU?$coroutine_handle@X@experimental@std@@@Z; `winrt::resume_background(void)'::`2'::awaitable::await_suspend(std::experimental::coroutine_handle<void>)
0x180033624  jmp     loc_180033A97
0x180033629  call    ?_Throw_bad_weak_ptr@std@@YAXXZ; std::_Throw_bad_weak_ptr(void)
0x18003362f  mov     rbx, [rsi+30h]; jumptable 0000000180033518 case 6
0x180033633  mov     [rsp+128h+var_B8], rbx
0x180033638  xor     edi, edi
0x18003363a  or      r14d, 0FFFFFFFFh
0x18003363e  test    rbx, rbx
0x180033641  jz      short loc_180033674
0x180033643  mov     eax, r14d
0x180033646  lock xadd [rbx+18h], eax
0x18003364b  sub     eax, 1
0x18003364e  jnz     short loc_180033665
0x180033650  nop
0x180033651  call    WINRT_IMPL_GetProcessHeap
0x180033656  mov     rcx, rax; hHeap
0x180033659  mov     r8, rbx; lpMem
0x18003365c  xor     edx, edx; dwFlags
0x18003365e  call    WINRT_IMPL_HeapFree
0x180033663  jmp     short loc_180033670
0x180033665  test    eax, eax
0x180033667  jns     short loc_180033670
0x180033669  call    cs:__imp_abort
0x180033670  mov     [rsi+30h], rdi
0x180033674  mov     rbx, [rsi+28h]
0x180033678  mov     [rsp+128h+var_B0], rbx
0x18003367d  test    rbx, rbx
0x180033680  jz      short loc_1800336B3
0x180033682  mov     eax, r14d
0x180033685  lock xadd [rbx+18h], eax
0x18003368a  sub     eax, 1
0x18003368d  jnz     short loc_1800336A4
0x18003368f  nop
0x180033690  call    WINRT_IMPL_GetProcessHeap
0x180033695  mov     rcx, rax; hHeap
0x180033698  mov     r8, rbx; lpMem
0x18003369b  xor     edx, edx; dwFlags
0x18003369d  call    WINRT_IMPL_HeapFree
0x1800336a2  jmp     short loc_1800336AF
0x1800336a4  test    eax, eax
0x1800336a6  jns     short loc_1800336AF
0x1800336a8  call    cs:__imp_abort
0x1800336af  mov     [rsi+28h], rdi
0x1800336b3  mov     rbx, [rsi+20h]
0x1800336b7  mov     [rsp+128h+var_A8], rbx
0x1800336bf  test    rbx, rbx
0x1800336c2  jz      short loc_1800336F5
0x1800336c4  mov     eax, r14d
0x1800336c7  lock xadd [rbx+18h], eax
0x1800336cc  sub     eax, 1
0x1800336cf  jnz     short loc_1800336E6
0x1800336d1  nop
0x1800336d2  call    WINRT_IMPL_GetProcessHeap
0x1800336d7  mov     rcx, rax; hHeap
0x1800336da  mov     r8, rbx; lpMem
0x1800336dd  xor     edx, edx; dwFlags
0x1800336df  call    WINRT_IMPL_HeapFree
0x1800336e4  jmp     short loc_1800336F1
0x1800336e6  test    eax, eax
0x1800336e8  jns     short loc_1800336F1
0x1800336ea  call    cs:__imp_abort
0x1800336f1  mov     [rsi+20h], rdi
0x1800336f5  mov     rax, [rsi+18h]
0x1800336f9  mov     [rsp+128h+var_C8], rax
0x1800336fe  test    rax, rax
0x180033701  jz      short loc_180033744
0x180033703  mov     rbx, [rsi+18h]
0x180033707  mov     [rsp+128h+var_C8], rbx
0x18003370c  mov     eax, r14d
0x18003370f  lock xadd [rbx+8], eax
0x180033714  add     eax, r14d
0x180033717  jnz     short loc_180033744
0x180033719  mov     rax, [rbx]
0x18003371c  mov     rcx, rbx
0x18003371f  mov     rax, [rax]
0x180033722  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033727  mov     eax, r14d
0x18003372a  lock xadd [rbx+0Ch], eax
0x18003372f  add     eax, r14d
0x180033732  jnz     short loc_180033744
0x180033734  mov     rax, [rbx]
0x180033737  mov     rcx, rbx
0x18003373a  mov     rax, [rax+8]
0x18003373e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033743  nop
0x180033744  jmp     loc_180033A08
0x180033749  lea     rbx, [rsi+40h]; jumptable 0000000180033518 case 5
0x18003374d  mov     [rsi+48h], rbx
0x180033751  mov     rax, [rsi+0F8h]
0x180033758  xor     edi, edi
0x18003375a  test    rax, rax
0x18003375d  jz      short loc_180033764
0x18003375f  lock add [rax+8], r8d
0x180033764  mov     [rbx], rax
0x180033767  lea     rcx, [rsi+50h]; this
0x18003376b  mov     [rsi+58h], rcx
0x18003376f  lea     rdx, [rsi+20h]; struct winrt::hstring *
0x180033773  call    ??0hstring@winrt@@QEAA@AEBU01@@Z; winrt::hstring::hstring(winrt::hstring const &)
0x180033778  mov     [rsp+128h+var_C0], rax
0x18003377d  lea     rcx, [rsi+60h]; this
0x180033781  mov     [rsi+68h], rcx
0x180033785  lea     r13, [rsi+30h]
0x180033789  mov     rdx, r13; struct winrt::hstring *
0x18003378c  call    ??0hstring@winrt@@QEAA@AEBU01@@Z; winrt::hstring::hstring(winrt::hstring const &)
0x180033791  mov     [rsp+128h+var_D0], rax
0x180033796  mov     eax, [rsi+10Ch]
0x18003379c  mov     [rsp+128h+var_E0], eax
0x1800337a0  lea     r15, [rsi+28h]
0x1800337a4  mov     eax, [r15+0E0h]
0x1800337ab  mov     [rsp+128h+var_E8], eax
0x1800337af  lea     rcx, [rsi+70h]; this
0x1800337b3  mov     rdx, r15; struct winrt::hstring *
0x1800337b6  call    ??0hstring@winrt@@QEAA@AEBU01@@Z; winrt::hstring::hstring(winrt::hstring const &)
0x1800337bb  mov     r8, rax
0x1800337be  lea     r14, [rsi+78h]
0x1800337c2  mov     [rsp+128h+var_F0], rbx
0x1800337c7  mov     rax, [rsp+128h+var_C0]
0x1800337cc  mov     [rsp+128h+var_F8], rax
0x1800337d1  mov     rax, [rsp+128h+var_D0]
0x1800337d6  mov     [rsp+128h+var_100], rax
0x1800337db  mov     ecx, [rsp+128h+var_E0]
0x1800337df  mov     [rsp+128h+var_108], ecx
0x1800337e3  mov     r9d, [rsp+128h+var_E8]
0x1800337e8  mov     rdx, r14
0x1800337eb  mov     rcx, [r12+0E0h]
0x1800337f3  call    ??$CallGetCollectionItemIdsAsync@URecoveryItemPdr@Passkey@Security@Data@Windows@@@ProfileDataStore@wil@@AEAA?AU?$task@V?$GetCollectionItemIdsResult@URecoveryItemPdr@Passkey@Security@Data@Windows@@@wil@@@1@Uhstring@winrt@@W4ProfileDataStoreLoadOptions@1@W4ProfileDataStoreCollectionOptions@1@00Vcancellation_token@Concurrency@@@Z; wil::ProfileDataStore::CallGetCollectionItemIdsAsync<Windows::Data::Security::Passkey::RecoveryItemPdr>(winrt::hstring,wil::ProfileDataStoreLoadOptions,wil::ProfileDataStoreCollectionOptions,winrt::hstring,winrt::hstring,Concurrency::cancellation_token)
0x1800337f8  nop
0x1800337f9  lea     rbx, [rsi+80h]
0x180033800  mov     rdx, rbx
0x180033803  mov     rcx, rax
0x180033806  call    ?get@?$task_base@V?$GetCollectionItemIdsResult@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@wil@@@coro@details@wil@@QEHAA@XZ; wil::details::coro::task_base<wil::GetCollectionItemIdsResult<Windows::Data::Security::Passkey::PasskeyItemPdr>>::get(void)
0x18003380b  mov     r9, rax
0x18003380e  mov     r8, [rax+10h]
0x180033812  mov     [rax+10h], rdi
0x180033816  mov     rdx, [rax+8]
0x18003381a  mov     [rax+8], rdi
0x18003381e  mov     rcx, [rax]
0x180033821  mov     [rax], rdi
0x180033824  mov     [rsi-58h], rcx
0x180033828  mov     [rsi-50h], rdx
0x18003382c  mov     [rsi-48h], r8
0x180033830  xorps   xmm0, xmm0
0x180033833  movups  xmmword ptr [rsi-40h], xmm0
0x180033837  mov     [rsi-30h], rdi
0x18003383b  mov     [rsi-28h], rdi
0x18003383f  movups  xmm0, xmmword ptr [rax+18h]
0x180033843  movups  xmmword ptr [rsi-40h], xmm0
0x180033847  movups  xmm1, xmmword ptr [rax+28h]
0x18003384b  movups  xmmword ptr [rsi-30h], xmm1
0x18003384f  mov     [rax+28h], rdi
0x180033853  mov     qword ptr [rax+30h], 7
0x18003385b  xor     eax, eax
0x18003385d  mov     [r9+18h], ax
0x180033862  mov     eax, [r9+38h]
0x180033866  mov     [rsi-20h], eax
0x180033869  mov     rax, [r9+40h]
0x18003386d  mov     [rsi-18h], rax
0x180033871  mov     dword ptr [rsi-60h], 1
0x180033878  lea     rcx, [rsi+98h]
0x18003387f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180033884  mov     rcx, rbx
0x180033887  call    ?_Tidy@?$vector@V?$ProfileDataItemReference@URecoveryItemPdr@Passkey@Security@Data@Windows@@@wil@@V?$allocator@V?$ProfileDataItemReference@URecoveryItemPdr@Passkey@Security@Data@Windows@@@wil@@@std@@@std@@AEAAXXZ; std::vector<wil::ProfileDataItemReference<Windows::Data::Security::Passkey::RecoveryItemPdr>>::_Tidy(void)
0x18003388c  nop
0x18003388d  mov     rcx, [r14]
0x180033890  mov     [rsp+128h+var_90], rcx
0x180033898  mov     [r14], rdi
0x18003389b  test    rcx, rcx
0x18003389e  jz      short loc_1800338C3
0x1800338a0  mov     eax, 2
0x1800338a5  xchg    rax, [rcx+8]
0x1800338a9  test    rax, rax
0x1800338ac  jz      short loc_1800338C3
0x1800338ae  lea     rax, [rcx+70h]
0x1800338b2  or      qword ptr [rax+8], 1
0x1800338b7  mov     rcx, rax
0x1800338ba  mov     rax, [rax]
0x1800338bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800338c2  nop
0x1800338c3  mov     rbx, [r13+0]
0x1800338c7  mov     [rsp+128h+var_B8], rbx
0x1800338cc  or      r14d, 0FFFFFFFFh
0x1800338d0  test    rbx, rbx
0x1800338d3  jz      short loc_180033906
0x1800338d5  mov     eax, r14d
0x1800338d8  lock xadd [rbx+18h], eax
0x1800338dd  sub     eax, 1
0x1800338e0  jnz     short loc_1800338F7
0x1800338e2  nop
0x1800338e3  call    WINRT_IMPL_GetProcessHeap
0x1800338e8  mov     rcx, rax; hHeap
0x1800338eb  mov     r8, rbx; lpMem
0x1800338ee  xor     edx, edx; dwFlags
0x1800338f0  call    WINRT_IMPL_HeapFree
0x1800338f5  jmp     short loc_180033902
0x1800338f7  test    eax, eax
0x1800338f9  jns     short loc_180033902
0x1800338fb  call    cs:__imp_abort
0x180033902  mov     [r13+0], rdi
0x180033906  mov     rbx, [r15]
0x180033909  mov     [rsp+128h+var_B0], rbx
0x18003390e  test    rbx, rbx
0x180033911  jz      short loc_180033943
0x180033913  mov     eax, r14d
0x180033916  lock xadd [rbx+18h], eax
0x18003391b  sub     eax, 1
0x18003391e  jnz     short loc_180033935
0x180033920  nop
0x180033921  call    WINRT_IMPL_GetProcessHeap
0x180033926  mov     rcx, rax; hHeap
0x180033929  mov     r8, rbx; lpMem
0x18003392c  xor     edx, edx; dwFlags
0x18003392e  call    WINRT_IMPL_HeapFree
  ... truncated ...
```
