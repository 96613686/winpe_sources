# wil::ProfileDataStore::SaveAsync$_ResumeCoro$1_Windows::Data::Security::Passkey::PasskeyItemPdr_

- ea: `0x18003b8f0`
- end: `0x18003bf20`
- name: `wil::ProfileDataStore::SaveAsync$_ResumeCoro$1_Windows::Data::Security::Passkey::PasskeyItemPdr_`
- size: `1584`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18003cba8`

## callees

- `0x180003080`
- `0x180003520`
- `0x180003c97`
- `0x180003cdf`
- `0x18000cac0`
- `0x18000ce74`
- `0x18001ae30`
- `0x18003b8f0`
- `0x18003ecf0`
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

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18003be9f`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18003be9f`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18003ba8c`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18003bace`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18003bd5f`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18003bda1`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18003ba8c`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18003bace`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18003bd5f`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18003bda1`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall wil::ProfileDataStore::SaveAsync__ResumeCoro_1_Windows::Data::Security::Passkey::PasskeyItemPdr_(
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
      goto LABEL_63;
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
      v28 = wil::ProfileDataStore::SaveInternalAsync<Windows::Data::Security::Passkey::PasskeyItemPdr>(
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
        if ( !_InterlockedDecrement(v18 + 2) )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v18)(v18);
          if ( !_InterlockedDecrement(v18 + 3) )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v18 + 8LL))(v18);
        }
      }
LABEL_63:
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
0x18003b8f0  mov     r11, rsp
0x18003b8f3  mov     [r11+10h], rbx
0x18003b8f7  mov     [r11+18h], rsi
0x18003b8fb  mov     [r11+8], rcx
0x18003b8ff  push    rdi
0x18003b900  push    r12
0x18003b902  push    r13
0x18003b904  push    r14
0x18003b906  push    r15
0x18003b908  sub     rsp, 100h
0x18003b90f  mov     rax, cs:__security_cookie
0x18003b916  xor     rax, rsp
0x18003b919  mov     [rsp+128h+var_38], rax
0x18003b921  mov     rbx, rcx
0x18003b924  mov     [rsp+128h+var_B0], rcx
0x18003b929  lea     r15, [rbx+8]
0x18003b92d  movzx   eax, word ptr [r15]
0x18003b931  mov     [rsp+128h+var_D8], ax
0x18003b936  mov     r14d, 1
0x18003b93c  add     ax, r14w
0x18003b940  cmp     ax, 6; switch 7 cases
0x18003b944  ja      def_18003B967; jumptable 000000018003B967 default case, case 1
0x18003b94a  mov     [rsp+128h+var_90], r15
0x18003b952  movsx   rax, ax
0x18003b956  lea     rdx, __ImageBase
0x18003b95d  mov     ecx, ds:(jpt_18003B967 - 180000000h)[rdx+rax*4]
0x18003b964  add     rcx, rdx
0x18003b967  jmp     rcx; switch jump
0x18003b969  xor     edi, edi; jumptable 000000018003B967 case 4
0x18003b96b  jmp     loc_18003BE70
0x18003b970  xor     edi, edi; jumptable 000000018003B967 case 3
0x18003b972  lea     rsi, [rbx+108h]
0x18003b979  mov     rcx, [rsp+128h]; this
0x18003b981  cmp     [rsi], rdi
0x18003b984  jnz     short loc_18003B99D
0x18003b986  mov     r9d, 80070057h; char *
0x18003b98c  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\sdk\\inc\\wil\\pr"...
0x18003b993  mov     edx, 53Fh; void *
0x18003b998  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003b99d  mov     rcx, [rsp+128h]; this
0x18003b9a5  cmp     [rbx+128h], rdi
0x18003b9ac  jnz     short loc_18003B9C5
0x18003b9ae  mov     r9d, 80070057h; char *
0x18003b9b4  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\sdk\\inc\\wil\\pr"...
0x18003b9bb  mov     edx, 540h; void *
0x18003b9c0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003b9c5  lea     rcx, [rbx+10h]
0x18003b9c9  mov     rdx, [rbx+100h]
0x18003b9d0  call    ??$make_shared@V?$ProfileDataItemReference@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@wil@@AEBV12@@std@@YA?AV?$shared_ptr@V?$ProfileDataItemReference@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@wil@@@0@AEBV?$ProfileDataItemReference@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@wil@@@Z; std::make_shared<wil::ProfileDataItemReference<Windows::Data::Security::Passkey::PasskeyItemPdr>,wil::ProfileDataItemReference<Windows::Data::Security::Passkey::PasskeyItemPdr> const &>(wil::ProfileDataItemReference<Windows::Data::Security::Passkey::PasskeyItemPdr> const &)
0x18003b9d5  nop
0x18003b9d6  mov     r8, [r15+0E0h]
0x18003b9dd  mov     [rbx+20h], rdi
0x18003b9e1  mov     [rbx+28h], rdi
0x18003b9e5  mov     rdx, [r8+8]
0x18003b9e9  test    rdx, rdx
0x18003b9ec  jz      short loc_18003BA4A
0x18003b9ee  mov     eax, [rdx+8]
0x18003b9f1  jmp     short loc_18003B9FD
0x18003b9f3  lea     ecx, [rax+1]
0x18003b9f6  lock cmpxchg [rdx+8], ecx
0x18003b9fb  jz      short loc_18003BA03
0x18003b9fd  test    eax, eax
0x18003b9ff  jnz     short loc_18003B9F3
0x18003ba01  jmp     short loc_18003BA4A
0x18003ba03  mov     rax, [r8]
0x18003ba06  mov     [rbx+20h], rax
0x18003ba0a  mov     rax, [r8+8]
0x18003ba0e  mov     [rbx+28h], rax
0x18003ba12  lea     rcx, [rbx+30h]
0x18003ba16  mov     rdx, rsi
0x18003ba19  call    ??$to_hstring@PEBD$0A@@winrt@@YA?AUhstring@0@AEBQEBD@Z; winrt::to_hstring<char const *,0>(char const * const &)
0x18003ba1e  nop
0x18003ba1f  lea     rcx, [rbx+38h]; this
0x18003ba23  mov     rdx, [rbx+128h]; unsigned __int16 *
0x18003ba2a  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x18003ba2f  nop
0x18003ba30  mov     [rbx+40h], dil
0x18003ba34  mov     eax, 4
0x18003ba39  mov     [r15], ax
0x18003ba3d  mov     rdx, rbx
0x18003ba40  call    ?await_suspend@awaitable@?1??resume_background@winrt@@YA@XZ@QEBAXU?$coroutine_handle@X@experimental@std@@@Z; `winrt::resume_background(void)'::`2'::awaitable::await_suspend(std::experimental::coroutine_handle<void>)
0x18003ba45  jmp     loc_18003BED4
0x18003ba4a  call    ?_Throw_bad_weak_ptr@std@@YAXXZ; std::_Throw_bad_weak_ptr(void)
0x18003ba50  mov     r14, [rbx+38h]; jumptable 000000018003B967 case 6
0x18003ba54  mov     [rsp+128h+var_A0], r14
0x18003ba5c  xor     edi, edi
0x18003ba5e  or      esi, 0FFFFFFFFh
0x18003ba61  test    r14, r14
0x18003ba64  jz      short loc_18003BA97
0x18003ba66  mov     eax, esi
0x18003ba68  lock xadd [r14+18h], eax
0x18003ba6e  sub     eax, 1
0x18003ba71  jnz     short loc_18003BA88
0x18003ba73  nop
0x18003ba74  call    WINRT_IMPL_GetProcessHeap
0x18003ba79  mov     rcx, rax; hHeap
0x18003ba7c  mov     r8, r14; lpMem
0x18003ba7f  xor     edx, edx; dwFlags
0x18003ba81  call    WINRT_IMPL_HeapFree
0x18003ba86  jmp     short loc_18003BA93
0x18003ba88  test    eax, eax
0x18003ba8a  jns     short loc_18003BA93
0x18003ba8c  call    cs:__imp_abort
0x18003ba93  mov     [rbx+38h], rdi
0x18003ba97  mov     r14, [rbx+30h]
0x18003ba9b  mov     [rsp+128h+var_98], r14
0x18003baa3  test    r14, r14
0x18003baa6  jz      short loc_18003BAD9
0x18003baa8  mov     eax, esi
0x18003baaa  lock xadd [r14+18h], eax
0x18003bab0  sub     eax, 1
0x18003bab3  jnz     short loc_18003BACA
0x18003bab5  nop
0x18003bab6  call    WINRT_IMPL_GetProcessHeap
0x18003babb  mov     rcx, rax; hHeap
0x18003babe  mov     r8, r14; lpMem
0x18003bac1  xor     edx, edx; dwFlags
0x18003bac3  call    WINRT_IMPL_HeapFree
0x18003bac8  jmp     short loc_18003BAD5
0x18003baca  test    eax, eax
0x18003bacc  jns     short loc_18003BAD5
0x18003bace  call    cs:__imp_abort
0x18003bad5  mov     [rbx+30h], rdi
0x18003bad9  mov     rax, [rbx+28h]
0x18003badd  mov     [rsp+128h+var_B8], rax
0x18003bae2  test    rax, rax
0x18003bae5  jz      short loc_18003BB26
0x18003bae7  mov     r14, [rbx+28h]
0x18003baeb  mov     [rsp+128h+var_B8], r14
0x18003baf0  mov     eax, esi
0x18003baf2  lock xadd [r14+8], eax
0x18003baf8  add     eax, esi
0x18003bafa  jnz     short loc_18003BB26
0x18003bafc  mov     rax, [r14]
0x18003baff  mov     rcx, r14
0x18003bb02  mov     rax, [rax]
0x18003bb05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bb0a  mov     eax, esi
0x18003bb0c  lock xadd [r14+0Ch], eax
0x18003bb12  add     eax, esi
0x18003bb14  jnz     short loc_18003BB26
0x18003bb16  mov     rax, [r14]
0x18003bb19  mov     rcx, r14
0x18003bb1c  mov     rax, [rax+8]
0x18003bb20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bb25  nop
0x18003bb26  mov     rax, [rbx+18h]
0x18003bb2a  mov     [rsp+128h+var_C8], rax
0x18003bb2f  test    rax, rax
0x18003bb32  jz      short loc_18003BB73
0x18003bb34  mov     r14, [rbx+18h]
0x18003bb38  mov     [rsp+128h+var_C8], r14
0x18003bb3d  mov     eax, esi
0x18003bb3f  lock xadd [r14+8], eax
0x18003bb45  add     eax, esi
0x18003bb47  jnz     short loc_18003BB73
0x18003bb49  mov     rax, [r14]
0x18003bb4c  mov     rcx, r14
0x18003bb4f  mov     rax, [rax]
0x18003bb52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bb57  mov     eax, esi
0x18003bb59  lock xadd [r14+0Ch], eax
0x18003bb5f  add     eax, esi
0x18003bb61  jnz     short loc_18003BB73
0x18003bb63  mov     rax, [r14]
0x18003bb66  mov     rcx, r14
0x18003bb69  mov     rax, [rax+8]
0x18003bb6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bb72  nop
0x18003bb73  jmp     loc_18003BE70
0x18003bb78  lea     rsi, [rbx+48h]; jumptable 000000018003B967 case 5
0x18003bb7c  mov     [rbx+50h], rsi
0x18003bb80  lea     r13, [rbx+30h]
0x18003bb84  mov     rax, [r13+0E0h]
0x18003bb8b  xor     edi, edi
0x18003bb8d  test    rax, rax
0x18003bb90  jz      short loc_18003BB97
0x18003bb92  lock add [rax+8], r14d
0x18003bb97  mov     [rsi], rax
0x18003bb9a  lea     rcx, [rbx+58h]; this
0x18003bb9e  mov     [rbx+60h], rcx
0x18003bba2  mov     rdx, r13; struct winrt::hstring *
0x18003bba5  call    ??0hstring@winrt@@QEAA@AEBU01@@Z; winrt::hstring::hstring(winrt::hstring const &)
0x18003bbaa  mov     [rsp+128h+var_C0], rax
0x18003bbaf  lea     rcx, [rbx+68h]; this
0x18003bbb3  lea     r12, [rbx+38h]
0x18003bbb7  mov     rdx, r12; struct winrt::hstring *
0x18003bbba  call    ??0hstring@winrt@@QEAA@AEBU01@@Z; winrt::hstring::hstring(winrt::hstring const &)
0x18003bbbf  mov     rdx, rax
0x18003bbc2  mov     r10, [rbx+120h]
0x18003bbc9  mov     r11d, [r12+0E0h]
0x18003bbd1  lea     r9, [rbx+70h]; int
0x18003bbd5  mov     [r9], rdi
0x18003bbd8  mov     [rbx+78h], rdi
0x18003bbdc  mov     rcx, [rbx+18h]
0x18003bbe0  mov     [rsp+128h+var_C8], rcx
0x18003bbe5  test    rcx, rcx
0x18003bbe8  jz      short loc_18003BBF8
0x18003bbea  mov     rax, [rbx+18h]
0x18003bbee  mov     [rsp+128h+var_C8], rax
0x18003bbf3  lock add [rax+8], r14d
0x18003bbf8  mov     rax, [rbx+10h]
0x18003bbfc  mov     [rsp+128h+var_D0], rax
0x18003bc01  mov     [r9], rax
0x18003bc04  mov     rax, [rbx+18h]
0x18003bc08  mov     [rsp+128h+var_C8], rax
0x18003bc0d  mov     [rbx+78h], rax
0x18003bc11  lea     r8, [rbx+80h]; int
0x18003bc18  mov     [r8], rdi
0x18003bc1b  mov     [rbx+88h], rdi
0x18003bc22  mov     rax, [rbx+0F8h]
0x18003bc29  test    rax, rax
0x18003bc2c  jz      short loc_18003BC33
0x18003bc2e  lock add [rax+8], r14d
0x18003bc33  mov     rax, [rbx+0F0h]
0x18003bc3a  mov     [r8], rax
0x18003bc3d  mov     rax, [rbx+0F8h]
0x18003bc44  mov     [rbx+88h], rax
0x18003bc4b  lea     r14, [rbx+90h]
0x18003bc52  mov     [rsp+128h+var_E8], rsi; __int64
0x18003bc57  mov     rax, [rsp+128h+var_C0]
0x18003bc5c  mov     [rsp+128h+var_F0], rax; struct winrt::hstring *
0x18003bc61  mov     [rsp+128h+var_F8], rdx; struct winrt::hstring *
0x18003bc66  mov     [rsp+128h+var_100], r10; __int64
0x18003bc6b  mov     [rsp+128h+var_108], r11d; int
0x18003bc70  mov     rdx, r14; int
0x18003bc73  mov     rcx, [r15+0E0h]; int
0x18003bc7a  call    ??$SaveInternalAsync@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@ProfileDataStore@wil@@AEAA?AU?$task@VProfileDataStoreSaveResult@wil@@@1@V?$shared_ptr@V?$ProfileDataItem@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@wil@@@std@@V?$shared_ptr@V?$ProfileDataItemReference@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@wil@@@4@W4ProfileDataStoreSaveOptions@1@_KUhstring@winrt@@4Vcancellation_token@Concurrency@@@Z; wil::ProfileDataStore::SaveInternalAsync<Windows::Data::Security::Passkey::PasskeyItemPdr>(std::shared_ptr<wil::ProfileDataItem<Windows::Data::Security::Passkey::PasskeyItemPdr>>,std::shared_ptr<wil::ProfileDataItemReference<Windows::Data::Security::Passkey::PasskeyItemPdr>>,wil::ProfileDataStoreSaveOptions,unsigned __int64,winrt::hstring,winrt::hstring,Concurrency::cancellation_token)
0x18003bc7f  nop
0x18003bc80  lea     rdx, [rbx+98h]
0x18003bc87  mov     rcx, rax
0x18003bc8a  call    ?get@?$task_base@VProfileDataStoreSaveResult@wil@@@coro@details@wil@@QEHAA@XZ; wil::details::coro::task_base<wil::ProfileDataStoreSaveResult>::get(void)
0x18003bc8f  mov     rcx, [rax]
0x18003bc92  mov     [rbx-48h], rcx
0x18003bc96  mov     ecx, [rax+8]
0x18003bc99  mov     [rbx-40h], ecx
0x18003bc9c  mov     ecx, [rax+0Ch]
0x18003bc9f  mov     [rbx-3Ch], ecx
0x18003bca2  xorps   xmm0, xmm0
0x18003bca5  movups  xmmword ptr [rbx-38h], xmm0
0x18003bca9  mov     [rbx-28h], rdi
0x18003bcad  mov     [rbx-20h], rdi
0x18003bcb1  movups  xmm0, xmmword ptr [rax+10h]
0x18003bcb5  movups  xmmword ptr [rbx-38h], xmm0
0x18003bcb9  movups  xmm1, xmmword ptr [rax+20h]
0x18003bcbd  movups  xmmword ptr [rbx-28h], xmm1
0x18003bcc1  mov     [rax+20h], rdi
0x18003bcc5  mov     qword ptr [rax+28h], 7
0x18003bccd  xor     ecx, ecx
0x18003bccf  mov     [rax+10h], cx
0x18003bcd3  mov     rax, [rax+30h]
0x18003bcd7  mov     [rbx-18h], rax
0x18003bcdb  mov     dword ptr [rbx-50h], 1
0x18003bce2  lea     rcx, [rbx+0A8h]
0x18003bce9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003bcee  nop
0x18003bcef  mov     rcx, [r14]
0x18003bcf2  mov     [rsp+128h+var_88], rcx
0x18003bcfa  mov     [r14], rdi
0x18003bcfd  test    rcx, rcx
0x18003bd00  jz      short loc_18003BD25
0x18003bd02  mov     eax, 2
0x18003bd07  xchg    rax, [rcx+8]
0x18003bd0b  test    rax, rax
0x18003bd0e  jz      short loc_18003BD25
0x18003bd10  lea     rax, [rcx+60h]
0x18003bd14  or      qword ptr [rax+8], 1
0x18003bd19  mov     rcx, rax
0x18003bd1c  mov     rax, [rax]
0x18003bd1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bd24  nop
0x18003bd25  mov     r14, [r12]
0x18003bd29  mov     [rsp+128h+var_A0], r14
0x18003bd31  or      esi, 0FFFFFFFFh
0x18003bd34  test    r14, r14
0x18003bd37  jz      short loc_18003BD6A
0x18003bd39  mov     eax, esi
0x18003bd3b  lock xadd [r14+18h], eax
0x18003bd41  sub     eax, 1
0x18003bd44  jnz     short loc_18003BD5B
0x18003bd46  nop
0x18003bd47  call    WINRT_IMPL_GetProcessHeap
0x18003bd4c  mov     rcx, rax; hHeap
0x18003bd4f  mov     r8, r14; lpMem
0x18003bd52  xor     edx, edx; dwFlags
0x18003bd54  call    WINRT_IMPL_HeapFree
0x18003bd59  jmp     short loc_18003BD66
0x18003bd5b  test    eax, eax
0x18003bd5d  jns     short loc_18003BD66
0x18003bd5f  call    cs:__imp_abort
0x18003bd66  mov     [r12], rdi
0x18003bd6a  mov     r14, [r13+0]
0x18003bd6e  mov     [rsp+128h+var_98], r14
0x18003bd76  test    r14, r14
0x18003bd79  jz      short loc_18003BDAC
0x18003bd7b  mov     eax, esi
0x18003bd7d  lock xadd [r14+18h], eax
0x18003bd83  sub     eax, 1
0x18003bd86  jnz     short loc_18003BD9D
0x18003bd88  nop
  ... truncated ...
```
