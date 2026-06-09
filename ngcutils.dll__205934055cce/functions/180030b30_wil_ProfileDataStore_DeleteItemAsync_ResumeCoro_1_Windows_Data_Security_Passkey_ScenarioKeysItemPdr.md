# wil::ProfileDataStore::DeleteItemAsync$_ResumeCoro$1_Windows::Data::Security::Passkey::ScenarioKeysItemPdr_

- ea: `0x180030b30`
- end: `0x180031134`
- name: `wil::ProfileDataStore::DeleteItemAsync$_ResumeCoro$1_Windows::Data::Security::Passkey::ScenarioKeysItemPdr_`
- size: `1540`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18002f964`

## callees

- `0x180003080`
- `0x180003520`
- `0x180003c97`
- `0x180003cdf`
- `0x18000cac0`
- `0x18000ce74`
- `0x18001ae30`
- `0x180030b30`
- `0x180031644`
- `0x180042aac`
- `0x18004519c`
- `0x180045224`
- `0x18004eaac`
- `0x18004ed50`
- `0x18004ee8c`
- `0x18004f8fc`
- `0x180061010`

## import_xrefs

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180031096`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x180031096`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180030cc8`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180030d07`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180030f50`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180030f8f`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180030cc8`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180030d07`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180030f50`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180030f8f`

## pseudocode

```c
void __fastcall wil::ProfileDataStore::DeleteItemAsync__ResumeCoro_1_Windows::Data::Security::Passkey::ScenarioKeysItemPdr_(
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
      v25 = wil::ProfileDataStore::DeleteItemInternalAsync<Windows::Data::Security::Passkey::ScenarioKeysItemPdr>(
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
0x180030b30  mov     r11, rsp
0x180030b33  mov     [r11+10h], rbx
0x180030b37  mov     [r11+18h], rsi
0x180030b3b  mov     [r11+8], rcx
0x180030b3f  push    rdi
0x180030b40  push    r12
0x180030b42  push    r13
0x180030b44  push    r14
0x180030b46  push    r15
0x180030b48  sub     rsp, 0F0h
0x180030b4f  mov     rax, cs:__security_cookie
0x180030b56  xor     rax, rsp
0x180030b59  mov     [rsp+118h+var_30], rax
0x180030b61  mov     rdi, rcx
0x180030b64  mov     [rsp+118h+var_B8], rcx
0x180030b69  lea     r15, [rdi+8]
0x180030b6d  movzx   eax, word ptr [r15]
0x180030b71  mov     [rsp+118h+var_D8], ax
0x180030b76  mov     r14d, 1
0x180030b7c  add     ax, r14w
0x180030b80  cmp     ax, 6; switch 7 cases
0x180030b84  ja      def_180030BA4; jumptable 0000000180030BA4 default case, case 1
0x180030b8a  mov     [rsp+118h+var_A0], r15
0x180030b8f  movsx   rax, ax
0x180030b93  lea     rdx, __ImageBase
0x180030b9a  mov     ecx, ds:(jpt_180030BA4 - 180000000h)[rdx+rax*4]
0x180030ba1  add     rcx, rdx
0x180030ba4  jmp     rcx; switch jump
0x180030ba6  xor     ebx, ebx; jumptable 0000000180030BA4 case 4
0x180030ba8  or      esi, 0FFFFFFFFh
0x180030bab  jmp     loc_180031067
0x180030bb0  xor     ebx, ebx; jumptable 0000000180030BA4 case 3
0x180030bb2  lea     rsi, [rdi+0E8h]
0x180030bb9  mov     rcx, [rsp+118h]; this
0x180030bc1  cmp     [rsi], rbx
0x180030bc4  jnz     short loc_180030BDD
0x180030bc6  mov     r9d, 80070057h; char *
0x180030bcc  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\sdk\\inc\\wil\\pr"...
0x180030bd3  mov     edx, 58Dh; void *
0x180030bd8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180030bdd  mov     rcx, [rsp+118h]; this
0x180030be5  cmp     [rdi+0F8h], rbx
0x180030bec  jnz     short loc_180030C05
0x180030bee  mov     r9d, 80070057h; char *
0x180030bf4  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\sdk\\inc\\wil\\pr"...
0x180030bfb  mov     edx, 58Eh; void *
0x180030c00  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180030c05  lea     rcx, [rdi+10h]
0x180030c09  mov     rdx, [rcx+0D0h]
0x180030c10  call    ??$make_shared@V?$ProfileDataItemReference@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@wil@@AEBV12@@std@@YA?AV?$shared_ptr@V?$ProfileDataItemReference@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@wil@@@0@AEBV?$ProfileDataItemReference@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@wil@@@Z; std::make_shared<wil::ProfileDataItemReference<Windows::Data::Security::Passkey::PasskeyItemPdr>,wil::ProfileDataItemReference<Windows::Data::Security::Passkey::PasskeyItemPdr> const &>(wil::ProfileDataItemReference<Windows::Data::Security::Passkey::PasskeyItemPdr> const &)
0x180030c15  nop
0x180030c16  mov     r8, [r15+0D0h]
0x180030c1d  mov     [rdi+20h], rbx
0x180030c21  mov     [rdi+28h], rbx
0x180030c25  mov     rdx, [r8+8]
0x180030c29  test    rdx, rdx
0x180030c2c  jz      short loc_180030C89
0x180030c2e  mov     eax, [rdx+8]
0x180030c31  jmp     short loc_180030C3D
0x180030c33  lea     ecx, [rax+1]
0x180030c36  lock cmpxchg [rdx+8], ecx
0x180030c3b  jz      short loc_180030C43
0x180030c3d  test    eax, eax
0x180030c3f  jnz     short loc_180030C33
0x180030c41  jmp     short loc_180030C89
0x180030c43  mov     rax, [r8]
0x180030c46  mov     [rdi+20h], rax
0x180030c4a  mov     rax, [r8+8]
0x180030c4e  mov     [rdi+28h], rax
0x180030c52  lea     rcx, [rdi+30h]
0x180030c56  mov     rdx, rsi
0x180030c59  call    ??$to_hstring@PEBD$0A@@winrt@@YA?AUhstring@0@AEBQEBD@Z; winrt::to_hstring<char const *,0>(char const * const &)
0x180030c5e  nop
0x180030c5f  lea     rcx, [rdi+38h]; this
0x180030c63  mov     rdx, [rdi+0F8h]; unsigned __int16 *
0x180030c6a  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x180030c6f  nop
0x180030c70  mov     [rdi+40h], bl
0x180030c73  mov     eax, 4
0x180030c78  mov     [r15], ax
0x180030c7c  mov     rdx, rdi
0x180030c7f  call    ?await_suspend@awaitable@?1??resume_background@winrt@@YA@XZ@QEBAXU?$coroutine_handle@X@experimental@std@@@Z; `winrt::resume_background(void)'::`2'::awaitable::await_suspend(std::experimental::coroutine_handle<void>)
0x180030c84  jmp     loc_1800310E9
0x180030c89  call    ?_Throw_bad_weak_ptr@std@@YAXXZ; std::_Throw_bad_weak_ptr(void)
0x180030c8f  mov     r14, [rdi+38h]; jumptable 0000000180030BA4 case 6
0x180030c93  mov     [rsp+118h+var_B0], r14
0x180030c98  xor     ebx, ebx
0x180030c9a  or      esi, 0FFFFFFFFh
0x180030c9d  test    r14, r14
0x180030ca0  jz      short loc_180030CD3
0x180030ca2  mov     eax, esi
0x180030ca4  lock xadd [r14+18h], eax
0x180030caa  sub     eax, 1
0x180030cad  jnz     short loc_180030CC4
0x180030caf  nop
0x180030cb0  call    WINRT_IMPL_GetProcessHeap
0x180030cb5  mov     rcx, rax; hHeap
0x180030cb8  mov     r8, r14; lpMem
0x180030cbb  xor     edx, edx; dwFlags
0x180030cbd  call    WINRT_IMPL_HeapFree
0x180030cc2  jmp     short loc_180030CCF
0x180030cc4  test    eax, eax
0x180030cc6  jns     short loc_180030CCF
0x180030cc8  call    cs:__imp_abort
0x180030ccf  mov     [rdi+38h], rbx
0x180030cd3  mov     r14, [rdi+30h]
0x180030cd7  mov     [rsp+118h+var_A8], r14
0x180030cdc  test    r14, r14
0x180030cdf  jz      short loc_180030D12
0x180030ce1  mov     eax, esi
0x180030ce3  lock xadd [r14+18h], eax
0x180030ce9  sub     eax, 1
0x180030cec  jnz     short loc_180030D03
0x180030cee  nop
0x180030cef  call    WINRT_IMPL_GetProcessHeap
0x180030cf4  mov     rcx, rax; hHeap
0x180030cf7  mov     r8, r14; lpMem
0x180030cfa  xor     edx, edx; dwFlags
0x180030cfc  call    WINRT_IMPL_HeapFree
0x180030d01  jmp     short loc_180030D0E
0x180030d03  test    eax, eax
0x180030d05  jns     short loc_180030D0E
0x180030d07  call    cs:__imp_abort
0x180030d0e  mov     [rdi+30h], rbx
0x180030d12  mov     rax, [rdi+28h]
0x180030d16  mov     [rsp+118h+var_88], rax
0x180030d1e  test    rax, rax
0x180030d21  jz      short loc_180030D65
0x180030d23  mov     r14, [rdi+28h]
0x180030d27  mov     [rsp+118h+var_88], r14
0x180030d2f  mov     eax, esi
0x180030d31  lock xadd [r14+8], eax
0x180030d37  add     eax, esi
0x180030d39  jnz     short loc_180030D65
0x180030d3b  mov     rax, [r14]
0x180030d3e  mov     rcx, r14
0x180030d41  mov     rax, [rax]
0x180030d44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030d49  mov     eax, esi
0x180030d4b  lock xadd [r14+0Ch], eax
0x180030d51  add     eax, esi
0x180030d53  jnz     short loc_180030D65
0x180030d55  mov     rax, [r14]
0x180030d58  mov     rcx, r14
0x180030d5b  mov     rax, [rax+8]
0x180030d5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030d64  nop
0x180030d65  mov     rax, [rdi+18h]
0x180030d69  mov     [rsp+118h+var_C0], rax
0x180030d6e  test    rax, rax
0x180030d71  jz      short loc_180030DB2
0x180030d73  mov     r14, [rdi+18h]
0x180030d77  mov     [rsp+118h+var_C0], r14
0x180030d7c  mov     eax, esi
0x180030d7e  lock xadd [r14+8], eax
0x180030d84  add     eax, esi
0x180030d86  jnz     short loc_180030DB2
0x180030d88  mov     rax, [r14]
0x180030d8b  mov     rcx, r14
0x180030d8e  mov     rax, [rax]
0x180030d91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030d96  mov     eax, esi
0x180030d98  lock xadd [r14+0Ch], eax
0x180030d9e  add     eax, esi
0x180030da0  jnz     short loc_180030DB2
0x180030da2  mov     rax, [r14]
0x180030da5  mov     rcx, r14
0x180030da8  mov     rax, [rax+8]
0x180030dac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030db1  nop
0x180030db2  jmp     loc_180031067
0x180030db7  lea     rsi, [rdi+48h]; jumptable 0000000180030BA4 case 5
0x180030dbb  mov     [rdi+50h], rsi
0x180030dbf  mov     rax, [rdi+0F0h]
0x180030dc6  xor     ebx, ebx
0x180030dc8  test    rax, rax
0x180030dcb  jz      short loc_180030DD2
0x180030dcd  lock add [rax+8], r14d
0x180030dd2  mov     [rsi], rax
0x180030dd5  lea     rcx, [rdi+58h]; this
0x180030dd9  mov     [rdi+60h], rcx
0x180030ddd  lea     r12, [rdi+30h]
0x180030de1  mov     rdx, r12; struct winrt::hstring *
0x180030de4  call    ??0hstring@winrt@@QEAA@AEBU01@@Z; winrt::hstring::hstring(winrt::hstring const &)
0x180030de9  mov     [rsp+118h+var_D0], rax
0x180030dee  lea     rcx, [rdi+68h]; this
0x180030df2  lea     r13, [rdi+38h]
0x180030df6  mov     rdx, r13; struct winrt::hstring *
0x180030df9  call    ??0hstring@winrt@@QEAA@AEBU01@@Z; winrt::hstring::hstring(winrt::hstring const &)
0x180030dfe  mov     rdx, rax
0x180030e01  mov     r9d, [r12+0D0h]; int
0x180030e09  lea     r8, [rdi+70h]; int
0x180030e0d  mov     [r8], rbx
0x180030e10  mov     [rdi+78h], rbx
0x180030e14  mov     rcx, [rdi+18h]
0x180030e18  mov     [rsp+118h+var_C0], rcx
0x180030e1d  test    rcx, rcx
0x180030e20  jz      short loc_180030E30
0x180030e22  mov     rax, [rdi+18h]
0x180030e26  mov     [rsp+118h+var_C0], rax
0x180030e2b  lock add [rax+8], r14d
0x180030e30  mov     rax, [rdi+10h]
0x180030e34  mov     [rsp+118h+var_C8], rax
0x180030e39  mov     [r8], rax
0x180030e3c  mov     rax, [rdi+18h]
0x180030e40  mov     [rsp+118h+var_C0], rax
0x180030e45  mov     [rdi+78h], rax
0x180030e49  lea     r14, [rdi+80h]
0x180030e50  mov     [rsp+118h+var_E8], rsi; __int64
0x180030e55  mov     rax, [rsp+118h+var_D0]
0x180030e5a  mov     [rsp+118h+var_F0], rax; struct winrt::hstring *
0x180030e5f  mov     [rsp+118h+var_F8], rdx; struct winrt::hstring *
0x180030e64  mov     rdx, r14; int
0x180030e67  mov     rcx, [r15+0D0h]; int
0x180030e6e  call    ??$DeleteItemInternalAsync@UScenarioKeysItemPdr@Passkey@Security@Data@Windows@@@ProfileDataStore@wil@@AEAA?AU?$task@VProfileDataStoreSaveResult@wil@@@1@V?$shared_ptr@V?$ProfileDataItemReference@UScenarioKeysItemPdr@Passkey@Security@Data@Windows@@@wil@@@std@@W4ProfileDataStoreSaveOptions@1@Uhstring@winrt@@2Vcancellation_token@Concurrency@@@Z; wil::ProfileDataStore::DeleteItemInternalAsync<Windows::Data::Security::Passkey::ScenarioKeysItemPdr>(std::shared_ptr<wil::ProfileDataItemReference<Windows::Data::Security::Passkey::ScenarioKeysItemPdr>>,wil::ProfileDataStoreSaveOptions,winrt::hstring,winrt::hstring,Concurrency::cancellation_token)
0x180030e73  nop
0x180030e74  lea     rdx, [rdi+88h]
0x180030e7b  mov     rcx, rax
0x180030e7e  call    ?get@?$task_base@VProfileDataStoreSaveResult@wil@@@coro@details@wil@@QEHAA@XZ; wil::details::coro::task_base<wil::ProfileDataStoreSaveResult>::get(void)
0x180030e83  mov     rcx, [rax]
0x180030e86  mov     [rdi-48h], rcx
0x180030e8a  mov     ecx, [rax+8]
0x180030e8d  mov     [rdi-40h], ecx
0x180030e90  mov     ecx, [rax+0Ch]
0x180030e93  mov     [rdi-3Ch], ecx
0x180030e96  xorps   xmm0, xmm0
0x180030e99  movups  xmmword ptr [rdi-38h], xmm0
0x180030e9d  mov     [rdi-28h], rbx
0x180030ea1  mov     [rdi-20h], rbx
0x180030ea5  movups  xmm0, xmmword ptr [rax+10h]
0x180030ea9  movups  xmmword ptr [rdi-38h], xmm0
0x180030ead  movups  xmm1, xmmword ptr [rax+20h]
0x180030eb1  movups  xmmword ptr [rdi-28h], xmm1
0x180030eb5  mov     [rax+20h], rbx
0x180030eb9  mov     qword ptr [rax+28h], 7
0x180030ec1  xor     ecx, ecx
0x180030ec3  mov     [rax+10h], cx
0x180030ec7  mov     rax, [rax+30h]
0x180030ecb  mov     [rdi-18h], rax
0x180030ecf  mov     dword ptr [rdi-50h], 1
0x180030ed6  lea     rcx, [rdi+98h]
0x180030edd  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180030ee2  nop
0x180030ee3  mov     rcx, [r14]
0x180030ee6  mov     [rsp+118h+var_80], rcx
0x180030eee  mov     [r14], rbx
0x180030ef1  test    rcx, rcx
0x180030ef4  jz      short loc_180030F19
0x180030ef6  mov     eax, 2
0x180030efb  xchg    rax, [rcx+8]
0x180030eff  test    rax, rax
0x180030f02  jz      short loc_180030F19
0x180030f04  lea     rax, [rcx+60h]
0x180030f08  or      qword ptr [rax+8], 1
0x180030f0d  mov     rcx, rax
0x180030f10  mov     rax, [rax]
0x180030f13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030f18  nop
0x180030f19  mov     r14, [r13+0]
0x180030f1d  mov     [rsp+118h+var_B0], r14
0x180030f22  or      esi, 0FFFFFFFFh
0x180030f25  test    r14, r14
0x180030f28  jz      short loc_180030F5B
0x180030f2a  mov     eax, esi
0x180030f2c  lock xadd [r14+18h], eax
0x180030f32  sub     eax, 1
0x180030f35  jnz     short loc_180030F4C
0x180030f37  nop
0x180030f38  call    WINRT_IMPL_GetProcessHeap
0x180030f3d  mov     rcx, rax; hHeap
0x180030f40  mov     r8, r14; lpMem
0x180030f43  xor     edx, edx; dwFlags
0x180030f45  call    WINRT_IMPL_HeapFree
0x180030f4a  jmp     short loc_180030F57
0x180030f4c  test    eax, eax
0x180030f4e  jns     short loc_180030F57
0x180030f50  call    cs:__imp_abort
0x180030f57  mov     [r13+0], rbx
0x180030f5b  mov     r14, [r12]
0x180030f5f  mov     [rsp+118h+var_A8], r14
0x180030f64  test    r14, r14
0x180030f67  jz      short loc_180030F9A
0x180030f69  mov     eax, esi
0x180030f6b  lock xadd [r14+18h], eax
0x180030f71  sub     eax, 1
0x180030f74  jnz     short loc_180030F8B
0x180030f76  nop
0x180030f77  call    WINRT_IMPL_GetProcessHeap
0x180030f7c  mov     rcx, rax; hHeap
0x180030f7f  mov     r8, r14; lpMem
0x180030f82  xor     edx, edx; dwFlags
0x180030f84  call    WINRT_IMPL_HeapFree
0x180030f89  jmp     short loc_180030F96
0x180030f8b  test    eax, eax
0x180030f8d  jns     short loc_180030F96
0x180030f8f  call    cs:__imp_abort
0x180030f96  mov     [r12], rbx
0x180030f9a  mov     rax, [rdi+28h]
0x180030f9e  mov     [rsp+118h+var_88], rax
0x180030fa6  test    rax, rax
  ... truncated ...
```
