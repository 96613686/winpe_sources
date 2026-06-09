# wil::ProfileDataStore::GetCollectionItemIdsAsync$_ResumeCoro$1_Windows::Data::Security::Passkey::PasskeyItemPdr_

- ea: `0x180032e50`
- end: `0x180033494`
- name: `wil::ProfileDataStore::GetCollectionItemIdsAsync$_ResumeCoro$1_Windows::Data::Security::Passkey::PasskeyItemPdr_`
- size: `1604`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18003197c`

## callees

- `0x180003080`
- `0x180003520`
- `0x180003c97`
- `0x180003cdf`
- `0x18000cac0`
- `0x18000ce74`
- `0x18001ae30`
- `0x180026d40`
- `0x180032e50`
- `0x18004519c`
- `0x180045224`
- `0x18004eaac`
- `0x18004ead4`
- `0x18004ed50`
- `0x18004ed9c`
- `0x18004f554`
- `0x180061010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800333e7`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800333e7`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180033019`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180033058`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18003309a`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800332ab`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800332e9`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18003332a`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180033019`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180033058`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18003309a`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800332ab`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800332e9`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18003332a`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall wil::ProfileDataStore::GetCollectionItemIdsAsync__ResumeCoro_1_Windows::Data::Security::Passkey::PasskeyItemPdr_(
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
      goto LABEL_65;
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
      v24 = wil::ProfileDataStore::CallGetCollectionItemIdsAsync<Windows::Data::Security::Passkey::PasskeyItemPdr>(
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
LABEL_65:
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
0x180032e50  mov     r11, rsp
0x180032e53  mov     [r11+10h], rbx
0x180032e57  mov     [r11+18h], rsi
0x180032e5b  mov     [r11+8], rcx
0x180032e5f  push    rdi
0x180032e60  push    r12
0x180032e62  push    r13
0x180032e64  push    r14
0x180032e66  push    r15
0x180032e68  sub     rsp, 100h
0x180032e6f  mov     rax, cs:__security_cookie
0x180032e76  xor     rax, rsp
0x180032e79  mov     [rsp+128h+var_30], rax
0x180032e81  mov     rsi, rcx
0x180032e84  mov     [rsp+128h+var_D8], rcx
0x180032e89  lea     r12, [rsi+8]
0x180032e8d  movzx   eax, word ptr [r12]
0x180032e92  mov     [rsp+128h+var_E4], ax
0x180032e97  mov     r8d, 1
0x180032e9d  add     ax, r8w
0x180032ea1  cmp     ax, 6; switch 7 cases
0x180032ea5  ja      def_180032EC8; jumptable 0000000180032EC8 default case, case 1
0x180032eab  mov     [rsp+128h+var_A0], r12
0x180032eb3  movsx   rax, ax
0x180032eb7  lea     rdx, __ImageBase
0x180032ebe  mov     ecx, ds:(jpt_180032EC8 - 180000000h)[rdx+rax*4]
0x180032ec5  add     rcx, rdx
0x180032ec8  jmp     rcx; switch jump
0x180032eca  xor     edi, edi; jumptable 0000000180032EC8 case 4
0x180032ecc  or      r14d, 0FFFFFFFFh
0x180032ed0  jmp     loc_1800333B8
0x180032ed5  xor     edi, edi; jumptable 0000000180032EC8 case 3
0x180032ed7  mov     rcx, [rsp+128h]; this
0x180032edf  cmp     [rsi+100h], rdi
0x180032ee6  jnz     short loc_180032EFF
0x180032ee8  mov     r9d, 80070057h; char *
0x180032eee  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\sdk\\inc\\wil\\pr"...
0x180032ef5  mov     edx, 495h; void *
0x180032efa  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180032eff  lea     r9, [rsi+0F0h]
0x180032f06  mov     rcx, [rsp+128h]; this
0x180032f0e  cmp     [r9], rdi
0x180032f11  jnz     short loc_180032F2A
0x180032f13  mov     r9d, 80070057h; char *
0x180032f19  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\sdk\\inc\\wil\\pr"...
0x180032f20  mov     edx, 496h; void *
0x180032f25  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180032f2a  mov     rcx, [rsp+128h]; this
0x180032f32  cmp     [rsi+110h], rdi
0x180032f39  jnz     short loc_180032F52
0x180032f3b  mov     r9d, 80070057h; char *
0x180032f41  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\sdk\\inc\\wil\\pr"...
0x180032f48  mov     edx, 497h; void *
0x180032f4d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180032f52  mov     r8, [r12+0E0h]
0x180032f5a  mov     [rsi+10h], rdi
0x180032f5e  mov     [rsi+18h], rdi
0x180032f62  mov     rdx, [r8+8]
0x180032f66  test    rdx, rdx
0x180032f69  jz      short loc_180032FD9
0x180032f6b  mov     eax, [rdx+8]
0x180032f6e  jmp     short loc_180032F7A
0x180032f70  lea     ecx, [rax+1]
0x180032f73  lock cmpxchg [rdx+8], ecx
0x180032f78  jz      short loc_180032F80
0x180032f7a  test    eax, eax
0x180032f7c  jnz     short loc_180032F70
0x180032f7e  jmp     short loc_180032FD9
0x180032f80  mov     rax, [r8]
0x180032f83  mov     [rsi+10h], rax
0x180032f87  mov     rax, [r8+8]
0x180032f8b  mov     [rsi+18h], rax
0x180032f8f  mov     rdx, r9
0x180032f92  lea     rcx, [rsi+20h]
0x180032f96  call    ??$to_hstring@PEBD$0A@@winrt@@YA?AUhstring@0@AEBQEBD@Z; winrt::to_hstring<char const *,0>(char const * const &)
0x180032f9b  nop
0x180032f9c  lea     rcx, [rsi+28h]; this
0x180032fa0  mov     rdx, [rsi+100h]; unsigned __int16 *
0x180032fa7  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x180032fac  nop
0x180032fad  mov     rdx, [rsi+110h]; unsigned __int16 *
0x180032fb4  lea     rcx, [rsi+30h]; this
0x180032fb8  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x180032fbd  nop
0x180032fbe  mov     [rsi+38h], dil
0x180032fc2  mov     eax, 4
0x180032fc7  mov     [r12], ax
0x180032fcc  mov     rdx, rsi
0x180032fcf  call    ?await_suspend@awaitable@?1??resume_background@winrt@@YA@XZ@QEBAXU?$coroutine_handle@X@experimental@std@@@Z; `winrt::resume_background(void)'::`2'::awaitable::await_suspend(std::experimental::coroutine_handle<void>)
0x180032fd4  jmp     loc_180033447
0x180032fd9  call    ?_Throw_bad_weak_ptr@std@@YAXXZ; std::_Throw_bad_weak_ptr(void)
0x180032fdf  mov     rbx, [rsi+30h]; jumptable 0000000180032EC8 case 6
0x180032fe3  mov     [rsp+128h+var_B8], rbx
0x180032fe8  xor     edi, edi
0x180032fea  or      r14d, 0FFFFFFFFh
0x180032fee  test    rbx, rbx
0x180032ff1  jz      short loc_180033024
0x180032ff3  mov     eax, r14d
0x180032ff6  lock xadd [rbx+18h], eax
0x180032ffb  sub     eax, 1
0x180032ffe  jnz     short loc_180033015
0x180033000  nop
0x180033001  call    WINRT_IMPL_GetProcessHeap
0x180033006  mov     rcx, rax; hHeap
0x180033009  mov     r8, rbx; lpMem
0x18003300c  xor     edx, edx; dwFlags
0x18003300e  call    WINRT_IMPL_HeapFree
0x180033013  jmp     short loc_180033020
0x180033015  test    eax, eax
0x180033017  jns     short loc_180033020
0x180033019  call    cs:__imp_abort
0x180033020  mov     [rsi+30h], rdi
0x180033024  mov     rbx, [rsi+28h]
0x180033028  mov     [rsp+128h+var_B0], rbx
0x18003302d  test    rbx, rbx
0x180033030  jz      short loc_180033063
0x180033032  mov     eax, r14d
0x180033035  lock xadd [rbx+18h], eax
0x18003303a  sub     eax, 1
0x18003303d  jnz     short loc_180033054
0x18003303f  nop
0x180033040  call    WINRT_IMPL_GetProcessHeap
0x180033045  mov     rcx, rax; hHeap
0x180033048  mov     r8, rbx; lpMem
0x18003304b  xor     edx, edx; dwFlags
0x18003304d  call    WINRT_IMPL_HeapFree
0x180033052  jmp     short loc_18003305F
0x180033054  test    eax, eax
0x180033056  jns     short loc_18003305F
0x180033058  call    cs:__imp_abort
0x18003305f  mov     [rsi+28h], rdi
0x180033063  mov     rbx, [rsi+20h]
0x180033067  mov     [rsp+128h+var_A8], rbx
0x18003306f  test    rbx, rbx
0x180033072  jz      short loc_1800330A5
0x180033074  mov     eax, r14d
0x180033077  lock xadd [rbx+18h], eax
0x18003307c  sub     eax, 1
0x18003307f  jnz     short loc_180033096
0x180033081  nop
0x180033082  call    WINRT_IMPL_GetProcessHeap
0x180033087  mov     rcx, rax; hHeap
0x18003308a  mov     r8, rbx; lpMem
0x18003308d  xor     edx, edx; dwFlags
0x18003308f  call    WINRT_IMPL_HeapFree
0x180033094  jmp     short loc_1800330A1
0x180033096  test    eax, eax
0x180033098  jns     short loc_1800330A1
0x18003309a  call    cs:__imp_abort
0x1800330a1  mov     [rsi+20h], rdi
0x1800330a5  mov     rax, [rsi+18h]
0x1800330a9  mov     [rsp+128h+var_C8], rax
0x1800330ae  test    rax, rax
0x1800330b1  jz      short loc_1800330F4
0x1800330b3  mov     rbx, [rsi+18h]
0x1800330b7  mov     [rsp+128h+var_C8], rbx
0x1800330bc  mov     eax, r14d
0x1800330bf  lock xadd [rbx+8], eax
0x1800330c4  add     eax, r14d
0x1800330c7  jnz     short loc_1800330F4
0x1800330c9  mov     rax, [rbx]
0x1800330cc  mov     rcx, rbx
0x1800330cf  mov     rax, [rax]
0x1800330d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800330d7  mov     eax, r14d
0x1800330da  lock xadd [rbx+0Ch], eax
0x1800330df  add     eax, r14d
0x1800330e2  jnz     short loc_1800330F4
0x1800330e4  mov     rax, [rbx]
0x1800330e7  mov     rcx, rbx
0x1800330ea  mov     rax, [rax+8]
0x1800330ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800330f3  nop
0x1800330f4  jmp     loc_1800333B8
0x1800330f9  lea     rbx, [rsi+40h]; jumptable 0000000180032EC8 case 5
0x1800330fd  mov     [rsi+48h], rbx
0x180033101  mov     rax, [rsi+0F8h]
0x180033108  xor     edi, edi
0x18003310a  test    rax, rax
0x18003310d  jz      short loc_180033114
0x18003310f  lock add [rax+8], r8d
0x180033114  mov     [rbx], rax
0x180033117  lea     rcx, [rsi+50h]; this
0x18003311b  mov     [rsi+58h], rcx
0x18003311f  lea     rdx, [rsi+20h]; struct winrt::hstring *
0x180033123  call    ??0hstring@winrt@@QEAA@AEBU01@@Z; winrt::hstring::hstring(winrt::hstring const &)
0x180033128  mov     [rsp+128h+var_C0], rax
0x18003312d  lea     rcx, [rsi+60h]; this
0x180033131  mov     [rsi+68h], rcx
0x180033135  lea     r13, [rsi+30h]
0x180033139  mov     rdx, r13; struct winrt::hstring *
0x18003313c  call    ??0hstring@winrt@@QEAA@AEBU01@@Z; winrt::hstring::hstring(winrt::hstring const &)
0x180033141  mov     [rsp+128h+var_D0], rax
0x180033146  mov     eax, [rsi+10Ch]
0x18003314c  mov     [rsp+128h+var_E0], eax
0x180033150  lea     r15, [rsi+28h]
0x180033154  mov     eax, [r15+0E0h]
0x18003315b  mov     [rsp+128h+var_E8], eax
0x18003315f  lea     rcx, [rsi+70h]; this
0x180033163  mov     rdx, r15; struct winrt::hstring *
0x180033166  call    ??0hstring@winrt@@QEAA@AEBU01@@Z; winrt::hstring::hstring(winrt::hstring const &)
0x18003316b  mov     r8, rax
0x18003316e  lea     r14, [rsi+78h]
0x180033172  mov     [rsp+128h+var_F0], rbx
0x180033177  mov     rax, [rsp+128h+var_C0]
0x18003317c  mov     [rsp+128h+var_F8], rax
0x180033181  mov     rax, [rsp+128h+var_D0]
0x180033186  mov     [rsp+128h+var_100], rax
0x18003318b  mov     ecx, [rsp+128h+var_E0]
0x18003318f  mov     [rsp+128h+var_108], ecx
0x180033193  mov     r9d, [rsp+128h+var_E8]
0x180033198  mov     rdx, r14
0x18003319b  mov     rcx, [r12+0E0h]
0x1800331a3  call    ??$CallGetCollectionItemIdsAsync@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@ProfileDataStore@wil@@AEAA?AU?$task@V?$GetCollectionItemIdsResult@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@wil@@@1@Uhstring@winrt@@W4ProfileDataStoreLoadOptions@1@W4ProfileDataStoreCollectionOptions@1@00Vcancellation_token@Concurrency@@@Z; wil::ProfileDataStore::CallGetCollectionItemIdsAsync<Windows::Data::Security::Passkey::PasskeyItemPdr>(winrt::hstring,wil::ProfileDataStoreLoadOptions,wil::ProfileDataStoreCollectionOptions,winrt::hstring,winrt::hstring,Concurrency::cancellation_token)
0x1800331a8  nop
0x1800331a9  lea     rbx, [rsi+80h]
0x1800331b0  mov     rdx, rbx
0x1800331b3  mov     rcx, rax
0x1800331b6  call    ?get@?$task_base@V?$GetCollectionItemIdsResult@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@wil@@@coro@details@wil@@QEHAA@XZ; wil::details::coro::task_base<wil::GetCollectionItemIdsResult<Windows::Data::Security::Passkey::PasskeyItemPdr>>::get(void)
0x1800331bb  mov     r9, rax
0x1800331be  mov     r8, [rax+10h]
0x1800331c2  mov     [rax+10h], rdi
0x1800331c6  mov     rdx, [rax+8]
0x1800331ca  mov     [rax+8], rdi
0x1800331ce  mov     rcx, [rax]
0x1800331d1  mov     [rax], rdi
0x1800331d4  mov     [rsi-58h], rcx
0x1800331d8  mov     [rsi-50h], rdx
0x1800331dc  mov     [rsi-48h], r8
0x1800331e0  xorps   xmm0, xmm0
0x1800331e3  movups  xmmword ptr [rsi-40h], xmm0
0x1800331e7  mov     [rsi-30h], rdi
0x1800331eb  mov     [rsi-28h], rdi
0x1800331ef  movups  xmm0, xmmword ptr [rax+18h]
0x1800331f3  movups  xmmword ptr [rsi-40h], xmm0
0x1800331f7  movups  xmm1, xmmword ptr [rax+28h]
0x1800331fb  movups  xmmword ptr [rsi-30h], xmm1
0x1800331ff  mov     [rax+28h], rdi
0x180033203  mov     qword ptr [rax+30h], 7
0x18003320b  xor     eax, eax
0x18003320d  mov     [r9+18h], ax
0x180033212  mov     eax, [r9+38h]
0x180033216  mov     [rsi-20h], eax
0x180033219  mov     rax, [r9+40h]
0x18003321d  mov     [rsi-18h], rax
0x180033221  mov     dword ptr [rsi-60h], 1
0x180033228  lea     rcx, [rsi+98h]
0x18003322f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180033234  mov     rcx, rbx
0x180033237  call    ?_Tidy@?$vector@V?$ProfileDataItemReference@URecoveryItemPdr@Passkey@Security@Data@Windows@@@wil@@V?$allocator@V?$ProfileDataItemReference@URecoveryItemPdr@Passkey@Security@Data@Windows@@@wil@@@std@@@std@@AEAAXXZ; std::vector<wil::ProfileDataItemReference<Windows::Data::Security::Passkey::RecoveryItemPdr>>::_Tidy(void)
0x18003323c  nop
0x18003323d  mov     rcx, [r14]
0x180033240  mov     [rsp+128h+var_90], rcx
0x180033248  mov     [r14], rdi
0x18003324b  test    rcx, rcx
0x18003324e  jz      short loc_180033273
0x180033250  mov     eax, 2
0x180033255  xchg    rax, [rcx+8]
0x180033259  test    rax, rax
0x18003325c  jz      short loc_180033273
0x18003325e  lea     rax, [rcx+70h]
0x180033262  or      qword ptr [rax+8], 1
0x180033267  mov     rcx, rax
0x18003326a  mov     rax, [rax]
0x18003326d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033272  nop
0x180033273  mov     rbx, [r13+0]
0x180033277  mov     [rsp+128h+var_B8], rbx
0x18003327c  or      r14d, 0FFFFFFFFh
0x180033280  test    rbx, rbx
0x180033283  jz      short loc_1800332B6
0x180033285  mov     eax, r14d
0x180033288  lock xadd [rbx+18h], eax
0x18003328d  sub     eax, 1
0x180033290  jnz     short loc_1800332A7
0x180033292  nop
0x180033293  call    WINRT_IMPL_GetProcessHeap
0x180033298  mov     rcx, rax; hHeap
0x18003329b  mov     r8, rbx; lpMem
0x18003329e  xor     edx, edx; dwFlags
0x1800332a0  call    WINRT_IMPL_HeapFree
0x1800332a5  jmp     short loc_1800332B2
0x1800332a7  test    eax, eax
0x1800332a9  jns     short loc_1800332B2
0x1800332ab  call    cs:__imp_abort
0x1800332b2  mov     [r13+0], rdi
0x1800332b6  mov     rbx, [r15]
0x1800332b9  mov     [rsp+128h+var_B0], rbx
0x1800332be  test    rbx, rbx
0x1800332c1  jz      short loc_1800332F3
0x1800332c3  mov     eax, r14d
0x1800332c6  lock xadd [rbx+18h], eax
0x1800332cb  sub     eax, 1
0x1800332ce  jnz     short loc_1800332E5
0x1800332d0  nop
0x1800332d1  call    WINRT_IMPL_GetProcessHeap
0x1800332d6  mov     rcx, rax; hHeap
0x1800332d9  mov     r8, rbx; lpMem
0x1800332dc  xor     edx, edx; dwFlags
0x1800332de  call    WINRT_IMPL_HeapFree
  ... truncated ...
```
