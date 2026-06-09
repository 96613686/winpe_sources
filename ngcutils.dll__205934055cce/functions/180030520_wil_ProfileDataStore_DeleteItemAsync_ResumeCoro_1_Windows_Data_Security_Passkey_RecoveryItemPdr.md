# wil::ProfileDataStore::DeleteItemAsync$_ResumeCoro$1_Windows::Data::Security::Passkey::RecoveryItemPdr_

- ea: `0x180030520`
- end: `0x180030b24`
- name: `wil::ProfileDataStore::DeleteItemAsync$_ResumeCoro$1_Windows::Data::Security::Passkey::RecoveryItemPdr_`
- size: `1540`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18002f3bc`

## callees

- `0x180003080`
- `0x180003520`
- `0x180003c97`
- `0x180003cdf`
- `0x18000cac0`
- `0x18000ce74`
- `0x18001ae30`
- `0x180030520`
- `0x1800313c0`
- `0x180042aac`
- `0x18004519c`
- `0x180045224`
- `0x18004eaac`
- `0x18004ed50`
- `0x18004ee8c`
- `0x18004f8fc`
- `0x180061010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180030a86`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180030a86`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800306b8`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800306f7`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180030940`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18003097f`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800306b8`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800306f7`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180030940`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18003097f`

## pseudocode

```c
void __fastcall wil::ProfileDataStore::DeleteItemAsync__ResumeCoro_1_Windows::Data::Security::Passkey::RecoveryItemPdr_(
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
      goto LABEL_62;
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
      v25 = wil::ProfileDataStore::DeleteItemInternalAsync<Windows::Data::Security::Passkey::RecoveryItemPdr>(
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
LABEL_62:
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
0x180030520  mov     r11, rsp
0x180030523  mov     [r11+10h], rbx
0x180030527  mov     [r11+18h], rsi
0x18003052b  mov     [r11+8], rcx
0x18003052f  push    rdi
0x180030530  push    r12
0x180030532  push    r13
0x180030534  push    r14
0x180030536  push    r15
0x180030538  sub     rsp, 0F0h
0x18003053f  mov     rax, cs:__security_cookie
0x180030546  xor     rax, rsp
0x180030549  mov     [rsp+118h+var_30], rax
0x180030551  mov     rdi, rcx
0x180030554  mov     [rsp+118h+var_B8], rcx
0x180030559  lea     r15, [rdi+8]
0x18003055d  movzx   eax, word ptr [r15]
0x180030561  mov     [rsp+118h+var_D8], ax
0x180030566  mov     r14d, 1
0x18003056c  add     ax, r14w
0x180030570  cmp     ax, 6; switch 7 cases
0x180030574  ja      def_180030594; jumptable 0000000180030594 default case, case 1
0x18003057a  mov     [rsp+118h+var_A0], r15
0x18003057f  movsx   rax, ax
0x180030583  lea     rdx, __ImageBase
0x18003058a  mov     ecx, ds:(jpt_180030594 - 180000000h)[rdx+rax*4]
0x180030591  add     rcx, rdx
0x180030594  jmp     rcx; switch jump
0x180030596  xor     ebx, ebx; jumptable 0000000180030594 case 4
0x180030598  or      esi, 0FFFFFFFFh
0x18003059b  jmp     loc_180030A57
0x1800305a0  xor     ebx, ebx; jumptable 0000000180030594 case 3
0x1800305a2  lea     rsi, [rdi+0E8h]
0x1800305a9  mov     rcx, [rsp+118h]; this
0x1800305b1  cmp     [rsi], rbx
0x1800305b4  jnz     short loc_1800305CD
0x1800305b6  mov     r9d, 80070057h; char *
0x1800305bc  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\sdk\\inc\\wil\\pr"...
0x1800305c3  mov     edx, 58Dh; void *
0x1800305c8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800305cd  mov     rcx, [rsp+118h]; this
0x1800305d5  cmp     [rdi+0F8h], rbx
0x1800305dc  jnz     short loc_1800305F5
0x1800305de  mov     r9d, 80070057h; char *
0x1800305e4  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\sdk\\inc\\wil\\pr"...
0x1800305eb  mov     edx, 58Eh; void *
0x1800305f0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800305f5  lea     rcx, [rdi+10h]
0x1800305f9  mov     rdx, [rcx+0D0h]
0x180030600  call    ??$make_shared@V?$ProfileDataItemReference@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@wil@@AEBV12@@std@@YA?AV?$shared_ptr@V?$ProfileDataItemReference@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@wil@@@0@AEBV?$ProfileDataItemReference@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@wil@@@Z; std::make_shared<wil::ProfileDataItemReference<Windows::Data::Security::Passkey::PasskeyItemPdr>,wil::ProfileDataItemReference<Windows::Data::Security::Passkey::PasskeyItemPdr> const &>(wil::ProfileDataItemReference<Windows::Data::Security::Passkey::PasskeyItemPdr> const &)
0x180030605  nop
0x180030606  mov     r8, [r15+0D0h]
0x18003060d  mov     [rdi+20h], rbx
0x180030611  mov     [rdi+28h], rbx
0x180030615  mov     rdx, [r8+8]
0x180030619  test    rdx, rdx
0x18003061c  jz      short loc_180030679
0x18003061e  mov     eax, [rdx+8]
0x180030621  jmp     short loc_18003062D
0x180030623  lea     ecx, [rax+1]
0x180030626  lock cmpxchg [rdx+8], ecx
0x18003062b  jz      short loc_180030633
0x18003062d  test    eax, eax
0x18003062f  jnz     short loc_180030623
0x180030631  jmp     short loc_180030679
0x180030633  mov     rax, [r8]
0x180030636  mov     [rdi+20h], rax
0x18003063a  mov     rax, [r8+8]
0x18003063e  mov     [rdi+28h], rax
0x180030642  lea     rcx, [rdi+30h]
0x180030646  mov     rdx, rsi
0x180030649  call    ??$to_hstring@PEBD$0A@@winrt@@YA?AUhstring@0@AEBQEBD@Z; winrt::to_hstring<char const *,0>(char const * const &)
0x18003064e  nop
0x18003064f  lea     rcx, [rdi+38h]; this
0x180030653  mov     rdx, [rdi+0F8h]; unsigned __int16 *
0x18003065a  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x18003065f  nop
0x180030660  mov     [rdi+40h], bl
0x180030663  mov     eax, 4
0x180030668  mov     [r15], ax
0x18003066c  mov     rdx, rdi
0x18003066f  call    ?await_suspend@awaitable@?1??resume_background@winrt@@YA@XZ@QEBAXU?$coroutine_handle@X@experimental@std@@@Z; `winrt::resume_background(void)'::`2'::awaitable::await_suspend(std::experimental::coroutine_handle<void>)
0x180030674  jmp     loc_180030AD9
0x180030679  call    ?_Throw_bad_weak_ptr@std@@YAXXZ; std::_Throw_bad_weak_ptr(void)
0x18003067f  mov     r14, [rdi+38h]; jumptable 0000000180030594 case 6
0x180030683  mov     [rsp+118h+var_B0], r14
0x180030688  xor     ebx, ebx
0x18003068a  or      esi, 0FFFFFFFFh
0x18003068d  test    r14, r14
0x180030690  jz      short loc_1800306C3
0x180030692  mov     eax, esi
0x180030694  lock xadd [r14+18h], eax
0x18003069a  sub     eax, 1
0x18003069d  jnz     short loc_1800306B4
0x18003069f  nop
0x1800306a0  call    WINRT_IMPL_GetProcessHeap
0x1800306a5  mov     rcx, rax; hHeap
0x1800306a8  mov     r8, r14; lpMem
0x1800306ab  xor     edx, edx; dwFlags
0x1800306ad  call    WINRT_IMPL_HeapFree
0x1800306b2  jmp     short loc_1800306BF
0x1800306b4  test    eax, eax
0x1800306b6  jns     short loc_1800306BF
0x1800306b8  call    cs:__imp_abort
0x1800306bf  mov     [rdi+38h], rbx
0x1800306c3  mov     r14, [rdi+30h]
0x1800306c7  mov     [rsp+118h+var_A8], r14
0x1800306cc  test    r14, r14
0x1800306cf  jz      short loc_180030702
0x1800306d1  mov     eax, esi
0x1800306d3  lock xadd [r14+18h], eax
0x1800306d9  sub     eax, 1
0x1800306dc  jnz     short loc_1800306F3
0x1800306de  nop
0x1800306df  call    WINRT_IMPL_GetProcessHeap
0x1800306e4  mov     rcx, rax; hHeap
0x1800306e7  mov     r8, r14; lpMem
0x1800306ea  xor     edx, edx; dwFlags
0x1800306ec  call    WINRT_IMPL_HeapFree
0x1800306f1  jmp     short loc_1800306FE
0x1800306f3  test    eax, eax
0x1800306f5  jns     short loc_1800306FE
0x1800306f7  call    cs:__imp_abort
0x1800306fe  mov     [rdi+30h], rbx
0x180030702  mov     rax, [rdi+28h]
0x180030706  mov     [rsp+118h+var_88], rax
0x18003070e  test    rax, rax
0x180030711  jz      short loc_180030755
0x180030713  mov     r14, [rdi+28h]
0x180030717  mov     [rsp+118h+var_88], r14
0x18003071f  mov     eax, esi
0x180030721  lock xadd [r14+8], eax
0x180030727  add     eax, esi
0x180030729  jnz     short loc_180030755
0x18003072b  mov     rax, [r14]
0x18003072e  mov     rcx, r14
0x180030731  mov     rax, [rax]
0x180030734  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030739  mov     eax, esi
0x18003073b  lock xadd [r14+0Ch], eax
0x180030741  add     eax, esi
0x180030743  jnz     short loc_180030755
0x180030745  mov     rax, [r14]
0x180030748  mov     rcx, r14
0x18003074b  mov     rax, [rax+8]
0x18003074f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030754  nop
0x180030755  mov     rax, [rdi+18h]
0x180030759  mov     [rsp+118h+var_C0], rax
0x18003075e  test    rax, rax
0x180030761  jz      short loc_1800307A2
0x180030763  mov     r14, [rdi+18h]
0x180030767  mov     [rsp+118h+var_C0], r14
0x18003076c  mov     eax, esi
0x18003076e  lock xadd [r14+8], eax
0x180030774  add     eax, esi
0x180030776  jnz     short loc_1800307A2
0x180030778  mov     rax, [r14]
0x18003077b  mov     rcx, r14
0x18003077e  mov     rax, [rax]
0x180030781  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030786  mov     eax, esi
0x180030788  lock xadd [r14+0Ch], eax
0x18003078e  add     eax, esi
0x180030790  jnz     short loc_1800307A2
0x180030792  mov     rax, [r14]
0x180030795  mov     rcx, r14
0x180030798  mov     rax, [rax+8]
0x18003079c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800307a1  nop
0x1800307a2  jmp     loc_180030A57
0x1800307a7  lea     rsi, [rdi+48h]; jumptable 0000000180030594 case 5
0x1800307ab  mov     [rdi+50h], rsi
0x1800307af  mov     rax, [rdi+0F0h]
0x1800307b6  xor     ebx, ebx
0x1800307b8  test    rax, rax
0x1800307bb  jz      short loc_1800307C2
0x1800307bd  lock add [rax+8], r14d
0x1800307c2  mov     [rsi], rax
0x1800307c5  lea     rcx, [rdi+58h]; this
0x1800307c9  mov     [rdi+60h], rcx
0x1800307cd  lea     r12, [rdi+30h]
0x1800307d1  mov     rdx, r12; struct winrt::hstring *
0x1800307d4  call    ??0hstring@winrt@@QEAA@AEBU01@@Z; winrt::hstring::hstring(winrt::hstring const &)
0x1800307d9  mov     [rsp+118h+var_D0], rax
0x1800307de  lea     rcx, [rdi+68h]; this
0x1800307e2  lea     r13, [rdi+38h]
0x1800307e6  mov     rdx, r13; struct winrt::hstring *
0x1800307e9  call    ??0hstring@winrt@@QEAA@AEBU01@@Z; winrt::hstring::hstring(winrt::hstring const &)
0x1800307ee  mov     rdx, rax
0x1800307f1  mov     r9d, [r12+0D0h]; int
0x1800307f9  lea     r8, [rdi+70h]; int
0x1800307fd  mov     [r8], rbx
0x180030800  mov     [rdi+78h], rbx
0x180030804  mov     rcx, [rdi+18h]
0x180030808  mov     [rsp+118h+var_C0], rcx
0x18003080d  test    rcx, rcx
0x180030810  jz      short loc_180030820
0x180030812  mov     rax, [rdi+18h]
0x180030816  mov     [rsp+118h+var_C0], rax
0x18003081b  lock add [rax+8], r14d
0x180030820  mov     rax, [rdi+10h]
0x180030824  mov     [rsp+118h+var_C8], rax
0x180030829  mov     [r8], rax
0x18003082c  mov     rax, [rdi+18h]
0x180030830  mov     [rsp+118h+var_C0], rax
0x180030835  mov     [rdi+78h], rax
0x180030839  lea     r14, [rdi+80h]
0x180030840  mov     [rsp+118h+var_E8], rsi; __int64
0x180030845  mov     rax, [rsp+118h+var_D0]
0x18003084a  mov     [rsp+118h+var_F0], rax; struct winrt::hstring *
0x18003084f  mov     [rsp+118h+var_F8], rdx; struct winrt::hstring *
0x180030854  mov     rdx, r14; int
0x180030857  mov     rcx, [r15+0D0h]; int
0x18003085e  call    ??$DeleteItemInternalAsync@URecoveryItemPdr@Passkey@Security@Data@Windows@@@ProfileDataStore@wil@@AEAA?AU?$task@VProfileDataStoreSaveResult@wil@@@1@V?$shared_ptr@V?$ProfileDataItemReference@URecoveryItemPdr@Passkey@Security@Data@Windows@@@wil@@@std@@W4ProfileDataStoreSaveOptions@1@Uhstring@winrt@@2Vcancellation_token@Concurrency@@@Z; wil::ProfileDataStore::DeleteItemInternalAsync<Windows::Data::Security::Passkey::RecoveryItemPdr>(std::shared_ptr<wil::ProfileDataItemReference<Windows::Data::Security::Passkey::RecoveryItemPdr>>,wil::ProfileDataStoreSaveOptions,winrt::hstring,winrt::hstring,Concurrency::cancellation_token)
0x180030863  nop
0x180030864  lea     rdx, [rdi+88h]
0x18003086b  mov     rcx, rax
0x18003086e  call    ?get@?$task_base@VProfileDataStoreSaveResult@wil@@@coro@details@wil@@QEHAA@XZ; wil::details::coro::task_base<wil::ProfileDataStoreSaveResult>::get(void)
0x180030873  mov     rcx, [rax]
0x180030876  mov     [rdi-48h], rcx
0x18003087a  mov     ecx, [rax+8]
0x18003087d  mov     [rdi-40h], ecx
0x180030880  mov     ecx, [rax+0Ch]
0x180030883  mov     [rdi-3Ch], ecx
0x180030886  xorps   xmm0, xmm0
0x180030889  movups  xmmword ptr [rdi-38h], xmm0
0x18003088d  mov     [rdi-28h], rbx
0x180030891  mov     [rdi-20h], rbx
0x180030895  movups  xmm0, xmmword ptr [rax+10h]
0x180030899  movups  xmmword ptr [rdi-38h], xmm0
0x18003089d  movups  xmm1, xmmword ptr [rax+20h]
0x1800308a1  movups  xmmword ptr [rdi-28h], xmm1
0x1800308a5  mov     [rax+20h], rbx
0x1800308a9  mov     qword ptr [rax+28h], 7
0x1800308b1  xor     ecx, ecx
0x1800308b3  mov     [rax+10h], cx
0x1800308b7  mov     rax, [rax+30h]
0x1800308bb  mov     [rdi-18h], rax
0x1800308bf  mov     dword ptr [rdi-50h], 1
0x1800308c6  lea     rcx, [rdi+98h]
0x1800308cd  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800308d2  nop
0x1800308d3  mov     rcx, [r14]
0x1800308d6  mov     [rsp+118h+var_80], rcx
0x1800308de  mov     [r14], rbx
0x1800308e1  test    rcx, rcx
0x1800308e4  jz      short loc_180030909
0x1800308e6  mov     eax, 2
0x1800308eb  xchg    rax, [rcx+8]
0x1800308ef  test    rax, rax
0x1800308f2  jz      short loc_180030909
0x1800308f4  lea     rax, [rcx+60h]
0x1800308f8  or      qword ptr [rax+8], 1
0x1800308fd  mov     rcx, rax
0x180030900  mov     rax, [rax]
0x180030903  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030908  nop
0x180030909  mov     r14, [r13+0]
0x18003090d  mov     [rsp+118h+var_B0], r14
0x180030912  or      esi, 0FFFFFFFFh
0x180030915  test    r14, r14
0x180030918  jz      short loc_18003094B
0x18003091a  mov     eax, esi
0x18003091c  lock xadd [r14+18h], eax
0x180030922  sub     eax, 1
0x180030925  jnz     short loc_18003093C
0x180030927  nop
0x180030928  call    WINRT_IMPL_GetProcessHeap
0x18003092d  mov     rcx, rax; hHeap
0x180030930  mov     r8, r14; lpMem
0x180030933  xor     edx, edx; dwFlags
0x180030935  call    WINRT_IMPL_HeapFree
0x18003093a  jmp     short loc_180030947
0x18003093c  test    eax, eax
0x18003093e  jns     short loc_180030947
0x180030940  call    cs:__imp_abort
0x180030947  mov     [r13+0], rbx
0x18003094b  mov     r14, [r12]
0x18003094f  mov     [rsp+118h+var_A8], r14
0x180030954  test    r14, r14
0x180030957  jz      short loc_18003098A
0x180030959  mov     eax, esi
0x18003095b  lock xadd [r14+18h], eax
0x180030961  sub     eax, 1
0x180030964  jnz     short loc_18003097B
0x180030966  nop
0x180030967  call    WINRT_IMPL_GetProcessHeap
0x18003096c  mov     rcx, rax; hHeap
0x18003096f  mov     r8, r14; lpMem
0x180030972  xor     edx, edx; dwFlags
0x180030974  call    WINRT_IMPL_HeapFree
0x180030979  jmp     short loc_180030986
0x18003097b  test    eax, eax
0x18003097d  jns     short loc_180030986
0x18003097f  call    cs:__imp_abort
0x180030986  mov     [r12], rbx
0x18003098a  mov     rax, [rdi+28h]
0x18003098e  mov     [rsp+118h+var_88], rax
0x180030996  test    rax, rax
  ... truncated ...
```
