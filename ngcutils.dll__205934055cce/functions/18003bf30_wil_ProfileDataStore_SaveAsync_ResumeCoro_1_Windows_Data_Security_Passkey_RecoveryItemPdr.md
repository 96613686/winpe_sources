# wil::ProfileDataStore::SaveAsync$_ResumeCoro$1_Windows::Data::Security::Passkey::RecoveryItemPdr_

- ea: `0x18003bf30`
- end: `0x18003c560`
- name: `wil::ProfileDataStore::SaveAsync$_ResumeCoro$1_Windows::Data::Security::Passkey::RecoveryItemPdr_`
- size: `1584`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18003cd44`

## callees

- `0x180003080`
- `0x180003520`
- `0x180003c97`
- `0x180003cdf`
- `0x18000cac0`
- `0x18000ce74`
- `0x18001ae30`
- `0x18003bf30`
- `0x18003f034`
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

- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18003c4df`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18003c4df`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18003c0cc`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18003c10e`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18003c39f`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18003c3e1`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18003c0cc`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18003c10e`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18003c39f`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18003c3e1`

## pseudocode

```c
void __fastcall wil::ProfileDataStore::SaveAsync__ResumeCoro_1_Windows::Data::Security::Passkey::RecoveryItemPdr_(
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
      v28 = wil::ProfileDataStore::SaveInternalAsync<Windows::Data::Security::Passkey::RecoveryItemPdr>(
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
0x18003bf30  mov     r11, rsp
0x18003bf33  mov     [r11+10h], rbx
0x18003bf37  mov     [r11+18h], rsi
0x18003bf3b  mov     [r11+8], rcx
0x18003bf3f  push    rdi
0x18003bf40  push    r12
0x18003bf42  push    r13
0x18003bf44  push    r14
0x18003bf46  push    r15
0x18003bf48  sub     rsp, 100h
0x18003bf4f  mov     rax, cs:__security_cookie
0x18003bf56  xor     rax, rsp
0x18003bf59  mov     [rsp+128h+var_38], rax
0x18003bf61  mov     rbx, rcx
0x18003bf64  mov     [rsp+128h+var_B0], rcx
0x18003bf69  lea     r15, [rbx+8]
0x18003bf6d  movzx   eax, word ptr [r15]
0x18003bf71  mov     [rsp+128h+var_D8], ax
0x18003bf76  mov     r14d, 1
0x18003bf7c  add     ax, r14w
0x18003bf80  cmp     ax, 6; switch 7 cases
0x18003bf84  ja      def_18003BFA7; jumptable 000000018003BFA7 default case, case 1
0x18003bf8a  mov     [rsp+128h+var_90], r15
0x18003bf92  movsx   rax, ax
0x18003bf96  lea     rdx, __ImageBase
0x18003bf9d  mov     ecx, ds:(jpt_18003BFA7 - 180000000h)[rdx+rax*4]
0x18003bfa4  add     rcx, rdx
0x18003bfa7  jmp     rcx; switch jump
0x18003bfa9  xor     edi, edi; jumptable 000000018003BFA7 case 4
0x18003bfab  jmp     loc_18003C4B0
0x18003bfb0  xor     edi, edi; jumptable 000000018003BFA7 case 3
0x18003bfb2  lea     rsi, [rbx+108h]
0x18003bfb9  mov     rcx, [rsp+128h]; this
0x18003bfc1  cmp     [rsi], rdi
0x18003bfc4  jnz     short loc_18003BFDD
0x18003bfc6  mov     r9d, 80070057h; char *
0x18003bfcc  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\sdk\\inc\\wil\\pr"...
0x18003bfd3  mov     edx, 53Fh; void *
0x18003bfd8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003bfdd  mov     rcx, [rsp+128h]; this
0x18003bfe5  cmp     [rbx+128h], rdi
0x18003bfec  jnz     short loc_18003C005
0x18003bfee  mov     r9d, 80070057h; char *
0x18003bff4  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\sdk\\inc\\wil\\pr"...
0x18003bffb  mov     edx, 540h; void *
0x18003c000  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003c005  lea     rcx, [rbx+10h]
0x18003c009  mov     rdx, [rbx+100h]
0x18003c010  call    ??$make_shared@V?$ProfileDataItemReference@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@wil@@AEBV12@@std@@YA?AV?$shared_ptr@V?$ProfileDataItemReference@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@wil@@@0@AEBV?$ProfileDataItemReference@UPasskeyItemPdr@Passkey@Security@Data@Windows@@@wil@@@Z; std::make_shared<wil::ProfileDataItemReference<Windows::Data::Security::Passkey::PasskeyItemPdr>,wil::ProfileDataItemReference<Windows::Data::Security::Passkey::PasskeyItemPdr> const &>(wil::ProfileDataItemReference<Windows::Data::Security::Passkey::PasskeyItemPdr> const &)
0x18003c015  nop
0x18003c016  mov     r8, [r15+0E0h]
0x18003c01d  mov     [rbx+20h], rdi
0x18003c021  mov     [rbx+28h], rdi
0x18003c025  mov     rdx, [r8+8]
0x18003c029  test    rdx, rdx
0x18003c02c  jz      short loc_18003C08A
0x18003c02e  mov     eax, [rdx+8]
0x18003c031  jmp     short loc_18003C03D
0x18003c033  lea     ecx, [rax+1]
0x18003c036  lock cmpxchg [rdx+8], ecx
0x18003c03b  jz      short loc_18003C043
0x18003c03d  test    eax, eax
0x18003c03f  jnz     short loc_18003C033
0x18003c041  jmp     short loc_18003C08A
0x18003c043  mov     rax, [r8]
0x18003c046  mov     [rbx+20h], rax
0x18003c04a  mov     rax, [r8+8]
0x18003c04e  mov     [rbx+28h], rax
0x18003c052  lea     rcx, [rbx+30h]
0x18003c056  mov     rdx, rsi
0x18003c059  call    ??$to_hstring@PEBD$0A@@winrt@@YA?AUhstring@0@AEBQEBD@Z; winrt::to_hstring<char const *,0>(char const * const &)
0x18003c05e  nop
0x18003c05f  lea     rcx, [rbx+38h]; this
0x18003c063  mov     rdx, [rbx+128h]; unsigned __int16 *
0x18003c06a  call    ??0hstring@winrt@@QEAA@PEBG@Z; winrt::hstring::hstring(ushort const *)
0x18003c06f  nop
0x18003c070  mov     [rbx+40h], dil
0x18003c074  mov     eax, 4
0x18003c079  mov     [r15], ax
0x18003c07d  mov     rdx, rbx
0x18003c080  call    ?await_suspend@awaitable@?1??resume_background@winrt@@YA@XZ@QEBAXU?$coroutine_handle@X@experimental@std@@@Z; `winrt::resume_background(void)'::`2'::awaitable::await_suspend(std::experimental::coroutine_handle<void>)
0x18003c085  jmp     loc_18003C514
0x18003c08a  call    ?_Throw_bad_weak_ptr@std@@YAXXZ; std::_Throw_bad_weak_ptr(void)
0x18003c090  mov     r14, [rbx+38h]; jumptable 000000018003BFA7 case 6
0x18003c094  mov     [rsp+128h+var_A0], r14
0x18003c09c  xor     edi, edi
0x18003c09e  or      esi, 0FFFFFFFFh
0x18003c0a1  test    r14, r14
0x18003c0a4  jz      short loc_18003C0D7
0x18003c0a6  mov     eax, esi
0x18003c0a8  lock xadd [r14+18h], eax
0x18003c0ae  sub     eax, 1
0x18003c0b1  jnz     short loc_18003C0C8
0x18003c0b3  nop
0x18003c0b4  call    WINRT_IMPL_GetProcessHeap
0x18003c0b9  mov     rcx, rax; hHeap
0x18003c0bc  mov     r8, r14; lpMem
0x18003c0bf  xor     edx, edx; dwFlags
0x18003c0c1  call    WINRT_IMPL_HeapFree
0x18003c0c6  jmp     short loc_18003C0D3
0x18003c0c8  test    eax, eax
0x18003c0ca  jns     short loc_18003C0D3
0x18003c0cc  call    cs:__imp_abort
0x18003c0d3  mov     [rbx+38h], rdi
0x18003c0d7  mov     r14, [rbx+30h]
0x18003c0db  mov     [rsp+128h+var_98], r14
0x18003c0e3  test    r14, r14
0x18003c0e6  jz      short loc_18003C119
0x18003c0e8  mov     eax, esi
0x18003c0ea  lock xadd [r14+18h], eax
0x18003c0f0  sub     eax, 1
0x18003c0f3  jnz     short loc_18003C10A
0x18003c0f5  nop
0x18003c0f6  call    WINRT_IMPL_GetProcessHeap
0x18003c0fb  mov     rcx, rax; hHeap
0x18003c0fe  mov     r8, r14; lpMem
0x18003c101  xor     edx, edx; dwFlags
0x18003c103  call    WINRT_IMPL_HeapFree
0x18003c108  jmp     short loc_18003C115
0x18003c10a  test    eax, eax
0x18003c10c  jns     short loc_18003C115
0x18003c10e  call    cs:__imp_abort
0x18003c115  mov     [rbx+30h], rdi
0x18003c119  mov     rax, [rbx+28h]
0x18003c11d  mov     [rsp+128h+var_B8], rax
0x18003c122  test    rax, rax
0x18003c125  jz      short loc_18003C166
0x18003c127  mov     r14, [rbx+28h]
0x18003c12b  mov     [rsp+128h+var_B8], r14
0x18003c130  mov     eax, esi
0x18003c132  lock xadd [r14+8], eax
0x18003c138  add     eax, esi
0x18003c13a  jnz     short loc_18003C166
0x18003c13c  mov     rax, [r14]
0x18003c13f  mov     rcx, r14
0x18003c142  mov     rax, [rax]
0x18003c145  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c14a  mov     eax, esi
0x18003c14c  lock xadd [r14+0Ch], eax
0x18003c152  add     eax, esi
0x18003c154  jnz     short loc_18003C166
0x18003c156  mov     rax, [r14]
0x18003c159  mov     rcx, r14
0x18003c15c  mov     rax, [rax+8]
0x18003c160  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c165  nop
0x18003c166  mov     rax, [rbx+18h]
0x18003c16a  mov     [rsp+128h+var_C8], rax
0x18003c16f  test    rax, rax
0x18003c172  jz      short loc_18003C1B3
0x18003c174  mov     r14, [rbx+18h]
0x18003c178  mov     [rsp+128h+var_C8], r14
0x18003c17d  mov     eax, esi
0x18003c17f  lock xadd [r14+8], eax
0x18003c185  add     eax, esi
0x18003c187  jnz     short loc_18003C1B3
0x18003c189  mov     rax, [r14]
0x18003c18c  mov     rcx, r14
0x18003c18f  mov     rax, [rax]
0x18003c192  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c197  mov     eax, esi
0x18003c199  lock xadd [r14+0Ch], eax
0x18003c19f  add     eax, esi
0x18003c1a1  jnz     short loc_18003C1B3
0x18003c1a3  mov     rax, [r14]
0x18003c1a6  mov     rcx, r14
0x18003c1a9  mov     rax, [rax+8]
0x18003c1ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c1b2  nop
0x18003c1b3  jmp     loc_18003C4B0
0x18003c1b8  lea     rsi, [rbx+48h]; jumptable 000000018003BFA7 case 5
0x18003c1bc  mov     [rbx+50h], rsi
0x18003c1c0  lea     r13, [rbx+30h]
0x18003c1c4  mov     rax, [r13+0E0h]
0x18003c1cb  xor     edi, edi
0x18003c1cd  test    rax, rax
0x18003c1d0  jz      short loc_18003C1D7
0x18003c1d2  lock add [rax+8], r14d
0x18003c1d7  mov     [rsi], rax
0x18003c1da  lea     rcx, [rbx+58h]; this
0x18003c1de  mov     [rbx+60h], rcx
0x18003c1e2  mov     rdx, r13; struct winrt::hstring *
0x18003c1e5  call    ??0hstring@winrt@@QEAA@AEBU01@@Z; winrt::hstring::hstring(winrt::hstring const &)
0x18003c1ea  mov     [rsp+128h+var_C0], rax
0x18003c1ef  lea     rcx, [rbx+68h]; this
0x18003c1f3  lea     r12, [rbx+38h]
0x18003c1f7  mov     rdx, r12; struct winrt::hstring *
0x18003c1fa  call    ??0hstring@winrt@@QEAA@AEBU01@@Z; winrt::hstring::hstring(winrt::hstring const &)
0x18003c1ff  mov     rdx, rax
0x18003c202  mov     r10, [rbx+120h]
0x18003c209  mov     r11d, [r12+0E0h]
0x18003c211  lea     r9, [rbx+70h]; int
0x18003c215  mov     [r9], rdi
0x18003c218  mov     [rbx+78h], rdi
0x18003c21c  mov     rcx, [rbx+18h]
0x18003c220  mov     [rsp+128h+var_C8], rcx
0x18003c225  test    rcx, rcx
0x18003c228  jz      short loc_18003C238
0x18003c22a  mov     rax, [rbx+18h]
0x18003c22e  mov     [rsp+128h+var_C8], rax
0x18003c233  lock add [rax+8], r14d
0x18003c238  mov     rax, [rbx+10h]
0x18003c23c  mov     [rsp+128h+var_D0], rax
0x18003c241  mov     [r9], rax
0x18003c244  mov     rax, [rbx+18h]
0x18003c248  mov     [rsp+128h+var_C8], rax
0x18003c24d  mov     [rbx+78h], rax
0x18003c251  lea     r8, [rbx+80h]; int
0x18003c258  mov     [r8], rdi
0x18003c25b  mov     [rbx+88h], rdi
0x18003c262  mov     rax, [rbx+0F8h]
0x18003c269  test    rax, rax
0x18003c26c  jz      short loc_18003C273
0x18003c26e  lock add [rax+8], r14d
0x18003c273  mov     rax, [rbx+0F0h]
0x18003c27a  mov     [r8], rax
0x18003c27d  mov     rax, [rbx+0F8h]
0x18003c284  mov     [rbx+88h], rax
0x18003c28b  lea     r14, [rbx+90h]
0x18003c292  mov     [rsp+128h+var_E8], rsi; __int64
0x18003c297  mov     rax, [rsp+128h+var_C0]
0x18003c29c  mov     [rsp+128h+var_F0], rax; struct winrt::hstring *
0x18003c2a1  mov     [rsp+128h+var_F8], rdx; struct winrt::hstring *
0x18003c2a6  mov     [rsp+128h+var_100], r10; __int64
0x18003c2ab  mov     [rsp+128h+var_108], r11d; int
0x18003c2b0  mov     rdx, r14; int
0x18003c2b3  mov     rcx, [r15+0E0h]; int
0x18003c2ba  call    ??$SaveInternalAsync@URecoveryItemPdr@Passkey@Security@Data@Windows@@@ProfileDataStore@wil@@AEAA?AU?$task@VProfileDataStoreSaveResult@wil@@@1@V?$shared_ptr@V?$ProfileDataItem@URecoveryItemPdr@Passkey@Security@Data@Windows@@@wil@@@std@@V?$shared_ptr@V?$ProfileDataItemReference@URecoveryItemPdr@Passkey@Security@Data@Windows@@@wil@@@4@W4ProfileDataStoreSaveOptions@1@_KUhstring@winrt@@4Vcancellation_token@Concurrency@@@Z; wil::ProfileDataStore::SaveInternalAsync<Windows::Data::Security::Passkey::RecoveryItemPdr>(std::shared_ptr<wil::ProfileDataItem<Windows::Data::Security::Passkey::RecoveryItemPdr>>,std::shared_ptr<wil::ProfileDataItemReference<Windows::Data::Security::Passkey::RecoveryItemPdr>>,wil::ProfileDataStoreSaveOptions,unsigned __int64,winrt::hstring,winrt::hstring,Concurrency::cancellation_token)
0x18003c2bf  nop
0x18003c2c0  lea     rdx, [rbx+98h]
0x18003c2c7  mov     rcx, rax
0x18003c2ca  call    ?get@?$task_base@VProfileDataStoreSaveResult@wil@@@coro@details@wil@@QEHAA@XZ; wil::details::coro::task_base<wil::ProfileDataStoreSaveResult>::get(void)
0x18003c2cf  mov     rcx, [rax]
0x18003c2d2  mov     [rbx-48h], rcx
0x18003c2d6  mov     ecx, [rax+8]
0x18003c2d9  mov     [rbx-40h], ecx
0x18003c2dc  mov     ecx, [rax+0Ch]
0x18003c2df  mov     [rbx-3Ch], ecx
0x18003c2e2  xorps   xmm0, xmm0
0x18003c2e5  movups  xmmword ptr [rbx-38h], xmm0
0x18003c2e9  mov     [rbx-28h], rdi
0x18003c2ed  mov     [rbx-20h], rdi
0x18003c2f1  movups  xmm0, xmmword ptr [rax+10h]
0x18003c2f5  movups  xmmword ptr [rbx-38h], xmm0
0x18003c2f9  movups  xmm1, xmmword ptr [rax+20h]
0x18003c2fd  movups  xmmword ptr [rbx-28h], xmm1
0x18003c301  mov     [rax+20h], rdi
0x18003c305  mov     qword ptr [rax+28h], 7
0x18003c30d  xor     ecx, ecx
0x18003c30f  mov     [rax+10h], cx
0x18003c313  mov     rax, [rax+30h]
0x18003c317  mov     [rbx-18h], rax
0x18003c31b  mov     dword ptr [rbx-50h], 1
0x18003c322  lea     rcx, [rbx+0A8h]
0x18003c329  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003c32e  nop
0x18003c32f  mov     rcx, [r14]
0x18003c332  mov     [rsp+128h+var_88], rcx
0x18003c33a  mov     [r14], rdi
0x18003c33d  test    rcx, rcx
0x18003c340  jz      short loc_18003C365
0x18003c342  mov     eax, 2
0x18003c347  xchg    rax, [rcx+8]
0x18003c34b  test    rax, rax
0x18003c34e  jz      short loc_18003C365
0x18003c350  lea     rax, [rcx+60h]
0x18003c354  or      qword ptr [rax+8], 1
0x18003c359  mov     rcx, rax
0x18003c35c  mov     rax, [rax]
0x18003c35f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c364  nop
0x18003c365  mov     r14, [r12]
0x18003c369  mov     [rsp+128h+var_A0], r14
0x18003c371  or      esi, 0FFFFFFFFh
0x18003c374  test    r14, r14
0x18003c377  jz      short loc_18003C3AA
0x18003c379  mov     eax, esi
0x18003c37b  lock xadd [r14+18h], eax
0x18003c381  sub     eax, 1
0x18003c384  jnz     short loc_18003C39B
0x18003c386  nop
0x18003c387  call    WINRT_IMPL_GetProcessHeap
0x18003c38c  mov     rcx, rax; hHeap
0x18003c38f  mov     r8, r14; lpMem
0x18003c392  xor     edx, edx; dwFlags
0x18003c394  call    WINRT_IMPL_HeapFree
0x18003c399  jmp     short loc_18003C3A6
0x18003c39b  test    eax, eax
0x18003c39d  jns     short loc_18003C3A6
0x18003c39f  call    cs:__imp_abort
0x18003c3a6  mov     [r12], rdi
0x18003c3aa  mov     r14, [r13+0]
0x18003c3ae  mov     [rsp+128h+var_98], r14
0x18003c3b6  test    r14, r14
0x18003c3b9  jz      short loc_18003C3EC
0x18003c3bb  mov     eax, esi
0x18003c3bd  lock xadd [r14+18h], eax
0x18003c3c3  sub     eax, 1
0x18003c3c6  jnz     short loc_18003C3DD
0x18003c3c8  nop
  ... truncated ...
```
