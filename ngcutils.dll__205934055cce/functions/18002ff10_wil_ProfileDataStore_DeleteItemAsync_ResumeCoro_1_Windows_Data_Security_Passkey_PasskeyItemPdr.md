# wil::ProfileDataStore::DeleteItemAsync$_ResumeCoro$1_Windows::Data::Security::Passkey::PasskeyItemPdr_

- ea: `0x18002ff10`
- end: `0x180030514`
- name: `wil::ProfileDataStore::DeleteItemAsync$_ResumeCoro$1_Windows::Data::Security::Passkey::PasskeyItemPdr_`
- size: `1540`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18002ee14`

## callees

- `0x180003080`
- `0x180003520`
- `0x180003c97`
- `0x180003cdf`
- `0x18000cac0`
- `0x18000ce74`
- `0x18001ae30`
- `0x18002ff10`
- `0x18003113c`
- `0x180042aac`
- `0x18004519c`
- `0x180045224`
- `0x18004eaac`
- `0x18004ed50`
- `0x18004ee8c`
- `0x18004f8fc`
- `0x180061010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180030476`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180030476`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800300a8`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800300e7`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180030330`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18003036f`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800300a8`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800300e7`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180030330`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18003036f`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall wil::ProfileDataStore::DeleteItemAsync__ResumeCoro_1_Windows::Data::Security::Passkey::PasskeyItemPdr_(
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
  __int64 v19; // rax
  volatile signed __int32 **v20; // r12
  volatile signed __int32 **v21; // r13
  struct winrt::hstring *v22; // rdx
  int v23; // r9d
  _QWORD *v24; // r8
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rdx
  __int64 v28; // r8
  __int64 v29; // rcx
  volatile signed __int32 *v30; // r14
  int v31; // eax
  HANDLE ProcessHeap; // rax
  volatile signed __int32 *v33; // r14
  int v34; // eax
  HANDLE v35; // rax
  volatile signed __int32 *v36; // r14
  volatile signed __int32 *v37; // rbx
  volatile signed __int32 *v38; // rcx
  int v39; // [rsp+20h] [rbp-F8h]
  struct winrt::hstring *v40; // [rsp+48h] [rbp-D0h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+0h]

  v4 = a1 + 8;
  v5 = &_ImageBase;
  switch ( *(_WORD *)(a1 + 8) )
  {
    case 0xFFFF:
    case 1:
    case 3:
      goto LABEL_61;
    case 2:
      if ( !*(_QWORD *)(a1 + 232) )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x58D,
          (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil\\profiledatastore.h",
          (const char *)0x80070057LL,
          v39);
      if ( !*(_QWORD *)(a1 + 248) )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x58E,
          (unsigned int)"onecoreuap\\internal\\sdk\\inc\\wil\\profiledatastore.h",
          (const char *)0x80070057LL,
          v39);
      std::make_shared<wil::ProfileDataItemReference<Windows::Data::Security::Passkey::PasskeyItemPdr>,wil::ProfileDataItemReference<Windows::Data::Security::Passkey::PasskeyItemPdr> const &>(
        a1 + 16,
        *(_QWORD *)(a1 + 224));
      v6 = *(_QWORD **)(v4 + 208);
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
      winrt::to_hstring<char const *,0>(a1 + 48, a1 + 232);
      winrt::hstring::hstring((winrt::hstring *)(a1 + 56), *(const unsigned __int16 **)(a1 + 248));
      *(_BYTE *)(a1 + 64) = 0;
      *(_WORD *)v4 = 4;
      `winrt::resume_background'::`2'::awaitable::await_suspend(v10, a1);
      break;
    case 4:
      *(_QWORD *)(a1 + 80) = a1 + 72;
      v19 = *(_QWORD *)(a1 + 240);
      if ( v19 )
        _InterlockedAdd((volatile signed __int32 *)(v19 + 8), 1u);
      *(_QWORD *)(a1 + 72) = v19;
      *(_QWORD *)(a1 + 96) = a1 + 88;
      v20 = (volatile signed __int32 **)(a1 + 48);
      v40 = (struct winrt::hstring *)winrt::hstring::hstring(
                                       (winrt::hstring *)(a1 + 88),
                                       (const struct winrt::hstring *)(a1 + 48));
      v21 = (volatile signed __int32 **)(a1 + 56);
      v22 = (struct winrt::hstring *)winrt::hstring::hstring(
                                       (winrt::hstring *)(a1 + 104),
                                       (const struct winrt::hstring *)(a1 + 56));
      v23 = *(_DWORD *)(a1 + 256);
      v24 = (_QWORD *)(a1 + 112);
      *(_QWORD *)(a1 + 112) = 0;
      *(_QWORD *)(a1 + 120) = 0;
      if ( *(_QWORD *)(a1 + 24) )
        _InterlockedAdd((volatile signed __int32 *)(*(_QWORD *)(a1 + 24) + 8LL), 1u);
      *v24 = *(_QWORD *)(a1 + 16);
      *(_QWORD *)(a1 + 120) = *(_QWORD *)(a1 + 24);
      v25 = wil::ProfileDataStore::DeleteItemInternalAsync<Windows::Data::Security::Passkey::PasskeyItemPdr>(
              *(_QWORD *)(v4 + 208),
              (int)a1 + 128,
              (int)v24,
              v23,
              v22,
              v40,
              a1 + 72);
      v26 = wil::details::coro::task_base<wil::ProfileDataStoreSaveResult>::get(v25, a1 + 136);
      *(_QWORD *)(a1 - 72) = *(_QWORD *)v26;
      *(_DWORD *)(a1 - 64) = *(_DWORD *)(v26 + 8);
      *(_DWORD *)(a1 - 60) = *(_DWORD *)(v26 + 12);
      *(_OWORD *)(a1 - 56) = 0;
      *(_QWORD *)(a1 - 40) = 0;
      *(_QWORD *)(a1 - 32) = 0;
      *(_OWORD *)(a1 - 56) = *(_OWORD *)(v26 + 16);
      *(_OWORD *)(a1 - 40) = *(_OWORD *)(v26 + 32);
      *(_QWORD *)(v26 + 32) = 0;
      *(_QWORD *)(v26 + 40) = 7;
      *(_WORD *)(v26 + 16) = 0;
      *(_QWORD *)(a1 - 24) = *(_QWORD *)(v26 + 48);
      *(_DWORD *)(a1 - 80) = 1;
      std::wstring::~wstring(a1 + 152, v27, v28);
      v29 = *(_QWORD *)(a1 + 128);
      *(_QWORD *)(a1 + 128) = 0;
      if ( v29 && _InterlockedExchange64((volatile __int64 *)(v29 + 8), 2) )
      {
        *(_QWORD *)(v29 + 104) |= 1uLL;
        (*(void (__fastcall **)(__int64))(v29 + 96))(v29 + 96);
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
      v33 = *v20;
      if ( *v20 )
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
        *v20 = 0;
      }
      if ( *(_QWORD *)(a1 + 40) )
      {
        v36 = *(volatile signed __int32 **)(a1 + 40);
        if ( _InterlockedExchangeAdd(v36 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v36)(v36);
          if ( _InterlockedExchangeAdd(v36 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v36 + 8LL))(v36);
        }
      }
      if ( *(_QWORD *)(a1 + 24) )
      {
        v37 = *(volatile signed __int32 **)(a1 + 24);
        if ( _InterlockedExchangeAdd(v37 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v37)(v37);
          if ( _InterlockedExchangeAdd(v37 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v37 + 8LL))(v37);
        }
      }
      *(_QWORD *)(a1 + 192) = a1 - 96;
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
        if ( !_InterlockedDecrement(v18 + 2) )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v18)(v18);
          if ( !_InterlockedDecrement(v18 + 3) )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v18 + 8LL))(v18);
        }
      }
LABEL_61:
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
      v38 = *(volatile signed __int32 **)(v4 + 232);
      if ( v38 && !_InterlockedDecrement(v38 + 2) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v38 + 8LL))(v38);
      *(_QWORD *)(v4 + 232) = 0;
      if ( *(_WORD *)(a1 + 10) )
        operator delete((void *)(a1 - 96), 0x170u);
      break;
    default:
      __debugbreak();
      break;
  }
}

```

## disassembly

```asm
0x18002ff10  mov     r11, rsp
0x18002ff13  mov     [r11+10h], rbx
0x18002ff17  mov     [r11+18h], rsi
0x18002ff1b  mov     [r11+8], rcx
0x18002ff1f  push    rdi
0x18002ff20  push    r12
0x18002ff22  push    r13
0x18002ff24  push    r14
0x18002ff26  push    r15
0x18002ff28  sub     rsp, 0F0h
0x18002ff2f  mov     rax, cs:__security_cookie
0x18002ff36  xor     rax, rsp
0x18002ff39  mov     [rsp+118h+var_30], rax
0x18002ff41  mov     rdi, rcx
0x18002ff44  mov     [rsp+118h+var_B8], rcx
0x18002ff49  lea     r15, [rdi+8]
0x18002ff4d  movzx   eax, word ptr [r15]
0x18002ff51  mov     [rsp+118h+var_D8], ax
0x18002ff56  mov     r14d, 1
0x18002ff5c  add     ax, r14w
0x18002ff60  cmp     ax, 6; switch 7 cases
0x18002ff64  ja      def_18002FF84; jumptable 000000018002FF84 default case, case 1
0x18002ff6a  mov     [rsp+118h+var_A0], r15
0x18002ff6f  movsx   rax, ax
0x18002ff73  lea     rdx, __ImageBase
0x18002ff7a  mov     ecx, ds:(jpt_18002FF84 - 180000000h)[rdx+rax*4]
0x18002ff81  add     rcx, rdx
0x18002ff84  jmp     rcx; switch jump
0x18002ff86  xor     ebx, ebx; jumptable 000000018002FF84 case 4
0x18002ff88  or      esi, 0FFFFFFFFh
0x18002ff8b  jmp     loc_180030447
0x18002ff90  xor     ebx, ebx; jumptable 000000018002FF84 case 3
0x18002ff92  lea     rsi, [rdi+0E8h]
0x18002ff99  mov     rcx, [rsp+118h]; this
0x18002ffa1  cmp     [rsi], rbx
0x18002ffa4  jnz     short loc_18002FFBD
0x18002ffa6  mov     r9d, 80070057h; char *
0x18002ffac  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\sdk\\inc\\wil\\pr"...
0x18002ffb3  mov     edx, 58Dh; void *
0x18002ffb8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002ffbd  mov     rcx, [rsp+118h]; this
0x18002ffc5  cmp     [rdi+0F8h], rbx
0x18002ffcc  jnz     short loc_18002FFE5
0x18002ffce  mov     r9d, 80070057h; char *
0x18002ffd4  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\sdk\\inc\\wil\\pr"...
0x18002ffdb  mov     edx, 58Eh; void *
0x18002ffe0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002ffe5  lea     rcx, [rdi+10h]
0x18002ffe9  mov     rdx, [rcx+0D0h]
0x18002fff0  call    ??$make_shared@V?$ProfileDataItemReference@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@wil@@AEBV12@@std@@YA?AV?$shared_ptr@V?$ProfileDataItemReference@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@wil@@@0@AEBV?$ProfileDataItemReference@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@wil@@@Z; std::make_shared<wil::ProfileDataItemReference<Windows::Data::Security::Passkey::PasskeyItemPdr>,wil::ProfileDataItemReference<Windows::Data::Security::Passkey::PasskeyItemPdr> const &>(wil::ProfileDataItemReference<Windows::Data::Security::Passkey::PasskeyItemPdr> const &)
0x18002fff5  nop
0x18002fff6  mov     r8, [r15+0D0h]
0x18002fffd  mov     [rdi+20h], rbx
0x180030001  mov     [rdi+28h], rbx
0x180030005  mov     rdx, [r8+8]
0x180030009  test    rdx, rdx
0x18003000c  jz      short loc_180030069
0x18003000e  mov     eax, [rdx+8]
0x180030011  jmp     short loc_18003001D
0x180030013  lea     ecx, [rax+1]
0x180030016  lock cmpxchg [rdx+8], ecx
0x18003001b  jz      short loc_180030023
0x18003001d  test    eax, eax
0x18003001f  jnz     short loc_180030013
0x180030021  jmp     short loc_180030069
0x180030023  mov     rax, [r8]
0x180030026  mov     [rdi+20h], rax
0x18003002a  mov     rax, [r8+8]
0x18003002e  mov     [rdi+28h], rax
0x180030032  lea     rcx, [rdi+30h]
0x180030036  mov     rdx, rsi
0x180030039  call    ??$to_hstring@PEBD$0A@@winrt@@YA?AUhstring@0@AEBQEBD@Z; winrt::to_hstring<char const *,0>(char const * const &)
0x18003003e  nop
0x18003003f  lea     rcx, [rdi+38h]; this
0x180030043  mov     rdx, [rdi+0F8h]; unsigned __int16 *
0x18003004a  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x18003004f  nop
0x180030050  mov     [rdi+40h], bl
0x180030053  mov     eax, 4
0x180030058  mov     [r15], ax
0x18003005c  mov     rdx, rdi
0x18003005f  call    ?await_suspend@awaitable@?1??resume_background@winrt@@YA@XZ@QEBAXU?$coroutine_handle@X@experimental@std@@@Z; `winrt::resume_background(void)'::`2'::awaitable::await_suspend(std::experimental::coroutine_handle<void>)
0x180030064  jmp     loc_1800304C9
0x180030069  call    ?_Throw_bad_weak_ptr@std@@YAXXZ; std::_Throw_bad_weak_ptr(void)
0x18003006f  mov     r14, [rdi+38h]; jumptable 000000018002FF84 case 6
0x180030073  mov     [rsp+118h+var_B0], r14
0x180030078  xor     ebx, ebx
0x18003007a  or      esi, 0FFFFFFFFh
0x18003007d  test    r14, r14
0x180030080  jz      short loc_1800300B3
0x180030082  mov     eax, esi
0x180030084  lock xadd [r14+18h], eax
0x18003008a  sub     eax, 1
0x18003008d  jnz     short loc_1800300A4
0x18003008f  nop
0x180030090  call    WINRT_IMPL_GetProcessHeap
0x180030095  mov     rcx, rax; hHeap
0x180030098  mov     r8, r14; lpMem
0x18003009b  xor     edx, edx; dwFlags
0x18003009d  call    WINRT_IMPL_HeapFree
0x1800300a2  jmp     short loc_1800300AF
0x1800300a4  test    eax, eax
0x1800300a6  jns     short loc_1800300AF
0x1800300a8  call    cs:__imp_abort
0x1800300af  mov     [rdi+38h], rbx
0x1800300b3  mov     r14, [rdi+30h]
0x1800300b7  mov     [rsp+118h+var_A8], r14
0x1800300bc  test    r14, r14
0x1800300bf  jz      short loc_1800300F2
0x1800300c1  mov     eax, esi
0x1800300c3  lock xadd [r14+18h], eax
0x1800300c9  sub     eax, 1
0x1800300cc  jnz     short loc_1800300E3
0x1800300ce  nop
0x1800300cf  call    WINRT_IMPL_GetProcessHeap
0x1800300d4  mov     rcx, rax; hHeap
0x1800300d7  mov     r8, r14; lpMem
0x1800300da  xor     edx, edx; dwFlags
0x1800300dc  call    WINRT_IMPL_HeapFree
0x1800300e1  jmp     short loc_1800300EE
0x1800300e3  test    eax, eax
0x1800300e5  jns     short loc_1800300EE
0x1800300e7  call    cs:__imp_abort
0x1800300ee  mov     [rdi+30h], rbx
0x1800300f2  mov     rax, [rdi+28h]
0x1800300f6  mov     [rsp+118h+var_88], rax
0x1800300fe  test    rax, rax
0x180030101  jz      short loc_180030145
0x180030103  mov     r14, [rdi+28h]
0x180030107  mov     [rsp+118h+var_88], r14
0x18003010f  mov     eax, esi
0x180030111  lock xadd [r14+8], eax
0x180030117  add     eax, esi
0x180030119  jnz     short loc_180030145
0x18003011b  mov     rax, [r14]
0x18003011e  mov     rcx, r14
0x180030121  mov     rax, [rax]
0x180030124  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030129  mov     eax, esi
0x18003012b  lock xadd [r14+0Ch], eax
0x180030131  add     eax, esi
0x180030133  jnz     short loc_180030145
0x180030135  mov     rax, [r14]
0x180030138  mov     rcx, r14
0x18003013b  mov     rax, [rax+8]
0x18003013f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030144  nop
0x180030145  mov     rax, [rdi+18h]
0x180030149  mov     [rsp+118h+var_C0], rax
0x18003014e  test    rax, rax
0x180030151  jz      short loc_180030192
0x180030153  mov     r14, [rdi+18h]
0x180030157  mov     [rsp+118h+var_C0], r14
0x18003015c  mov     eax, esi
0x18003015e  lock xadd [r14+8], eax
0x180030164  add     eax, esi
0x180030166  jnz     short loc_180030192
0x180030168  mov     rax, [r14]
0x18003016b  mov     rcx, r14
0x18003016e  mov     rax, [rax]
0x180030171  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030176  mov     eax, esi
0x180030178  lock xadd [r14+0Ch], eax
0x18003017e  add     eax, esi
0x180030180  jnz     short loc_180030192
0x180030182  mov     rax, [r14]
0x180030185  mov     rcx, r14
0x180030188  mov     rax, [rax+8]
0x18003018c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030191  nop
0x180030192  jmp     loc_180030447
0x180030197  lea     rsi, [rdi+48h]; jumptable 000000018002FF84 case 5
0x18003019b  mov     [rdi+50h], rsi
0x18003019f  mov     rax, [rdi+0F0h]
0x1800301a6  xor     ebx, ebx
0x1800301a8  test    rax, rax
0x1800301ab  jz      short loc_1800301B2
0x1800301ad  lock add [rax+8], r14d
0x1800301b2  mov     [rsi], rax
0x1800301b5  lea     rcx, [rdi+58h]; this
0x1800301b9  mov     [rdi+60h], rcx
0x1800301bd  lea     r12, [rdi+30h]
0x1800301c1  mov     rdx, r12; struct winrt::hstring *
0x1800301c4  call    ??0hstring@winrt@@QEAA@AEBU01@@Z; winrt::hstring::hstring(winrt::hstring const &)
0x1800301c9  mov     [rsp+118h+var_D0], rax
0x1800301ce  lea     rcx, [rdi+68h]; this
0x1800301d2  lea     r13, [rdi+38h]
0x1800301d6  mov     rdx, r13; struct winrt::hstring *
0x1800301d9  call    ??0hstring@winrt@@QEAA@AEBU01@@Z; winrt::hstring::hstring(winrt::hstring const &)
0x1800301de  mov     rdx, rax
0x1800301e1  mov     r9d, [r12+0D0h]; int
0x1800301e9  lea     r8, [rdi+70h]; int
0x1800301ed  mov     [r8], rbx
0x1800301f0  mov     [rdi+78h], rbx
0x1800301f4  mov     rcx, [rdi+18h]
0x1800301f8  mov     [rsp+118h+var_C0], rcx
0x1800301fd  test    rcx, rcx
0x180030200  jz      short loc_180030210
0x180030202  mov     rax, [rdi+18h]
0x180030206  mov     [rsp+118h+var_C0], rax
0x18003020b  lock add [rax+8], r14d
0x180030210  mov     rax, [rdi+10h]
0x180030214  mov     [rsp+118h+var_C8], rax
0x180030219  mov     [r8], rax
0x18003021c  mov     rax, [rdi+18h]
0x180030220  mov     [rsp+118h+var_C0], rax
0x180030225  mov     [rdi+78h], rax
0x180030229  lea     r14, [rdi+80h]
0x180030230  mov     [rsp+118h+var_E8], rsi; __int64
0x180030235  mov     rax, [rsp+118h+var_D0]
0x18003023a  mov     [rsp+118h+var_F0], rax; struct winrt::hstring *
0x18003023f  mov     [rsp+118h+var_F8], rdx; struct winrt::hstring *
0x180030244  mov     rdx, r14; int
0x180030247  mov     rcx, [r15+0D0h]; int
0x18003024e  call    ??$DeleteItemInternalAsync@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@ProfileDataStore@wil@@AEAA?AU?$task@VProfileDataStoreSaveResult@wil@@@1@V?$shared_ptr@V?$ProfileDataItemReference@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@wil@@@std@@W4ProfileDataStoreSaveOptions@1@Uhstring@winrt@@2Vcancellation_token@Concurrency@@@Z; wil::ProfileDataStore::DeleteItemInternalAsync<Windows::Data::Security::Passkey::PasskeyItemPdr>(std::shared_ptr<wil::ProfileDataItemReference<Windows::Data::Security::Passkey::PasskeyItemPdr>>,wil::ProfileDataStoreSaveOptions,winrt::hstring,winrt::hstring,Concurrency::cancellation_token)
0x180030253  nop
0x180030254  lea     rdx, [rdi+88h]
0x18003025b  mov     rcx, rax
0x18003025e  call    ?get@?$task_base@VProfileDataStoreSaveResult@wil@@@coro@details@wil@@QEHAA@XZ; wil::details::coro::task_base<wil::ProfileDataStoreSaveResult>::get(void)
0x180030263  mov     rcx, [rax]
0x180030266  mov     [rdi-48h], rcx
0x18003026a  mov     ecx, [rax+8]
0x18003026d  mov     [rdi-40h], ecx
0x180030270  mov     ecx, [rax+0Ch]
0x180030273  mov     [rdi-3Ch], ecx
0x180030276  xorps   xmm0, xmm0
0x180030279  movups  xmmword ptr [rdi-38h], xmm0
0x18003027d  mov     [rdi-28h], rbx
0x180030281  mov     [rdi-20h], rbx
0x180030285  movups  xmm0, xmmword ptr [rax+10h]
0x180030289  movups  xmmword ptr [rdi-38h], xmm0
0x18003028d  movups  xmm1, xmmword ptr [rax+20h]
0x180030291  movups  xmmword ptr [rdi-28h], xmm1
0x180030295  mov     [rax+20h], rbx
0x180030299  mov     qword ptr [rax+28h], 7
0x1800302a1  xor     ecx, ecx
0x1800302a3  mov     [rax+10h], cx
0x1800302a7  mov     rax, [rax+30h]
0x1800302ab  mov     [rdi-18h], rax
0x1800302af  mov     dword ptr [rdi-50h], 1
0x1800302b6  lea     rcx, [rdi+98h]
0x1800302bd  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800302c2  nop
0x1800302c3  mov     rcx, [r14]
0x1800302c6  mov     [rsp+118h+var_80], rcx
0x1800302ce  mov     [r14], rbx
0x1800302d1  test    rcx, rcx
0x1800302d4  jz      short loc_1800302F9
0x1800302d6  mov     eax, 2
0x1800302db  xchg    rax, [rcx+8]
0x1800302df  test    rax, rax
0x1800302e2  jz      short loc_1800302F9
0x1800302e4  lea     rax, [rcx+60h]
0x1800302e8  or      qword ptr [rax+8], 1
0x1800302ed  mov     rcx, rax
0x1800302f0  mov     rax, [rax]
0x1800302f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800302f8  nop
0x1800302f9  mov     r14, [r13+0]
0x1800302fd  mov     [rsp+118h+var_B0], r14
0x180030302  or      esi, 0FFFFFFFFh
0x180030305  test    r14, r14
0x180030308  jz      short loc_18003033B
0x18003030a  mov     eax, esi
0x18003030c  lock xadd [r14+18h], eax
0x180030312  sub     eax, 1
0x180030315  jnz     short loc_18003032C
0x180030317  nop
0x180030318  call    WINRT_IMPL_GetProcessHeap
0x18003031d  mov     rcx, rax; hHeap
0x180030320  mov     r8, r14; lpMem
0x180030323  xor     edx, edx; dwFlags
0x180030325  call    WINRT_IMPL_HeapFree
0x18003032a  jmp     short loc_180030337
0x18003032c  test    eax, eax
0x18003032e  jns     short loc_180030337
0x180030330  call    cs:__imp_abort
0x180030337  mov     [r13+0], rbx
0x18003033b  mov     r14, [r12]
0x18003033f  mov     [rsp+118h+var_A8], r14
0x180030344  test    r14, r14
0x180030347  jz      short loc_18003037A
0x180030349  mov     eax, esi
0x18003034b  lock xadd [r14+18h], eax
0x180030351  sub     eax, 1
0x180030354  jnz     short loc_18003036B
0x180030356  nop
0x180030357  call    WINRT_IMPL_GetProcessHeap
0x18003035c  mov     rcx, rax; hHeap
0x18003035f  mov     r8, r14; lpMem
0x180030362  xor     edx, edx; dwFlags
0x180030364  call    WINRT_IMPL_HeapFree
0x180030369  jmp     short loc_180030376
0x18003036b  test    eax, eax
0x18003036d  jns     short loc_180030376
0x18003036f  call    cs:__imp_abort
0x180030376  mov     [r12], rbx
0x18003037a  mov     rax, [rdi+28h]
0x18003037e  mov     [rsp+118h+var_88], rax
0x180030386  test    rax, rax
  ... truncated ...
```
