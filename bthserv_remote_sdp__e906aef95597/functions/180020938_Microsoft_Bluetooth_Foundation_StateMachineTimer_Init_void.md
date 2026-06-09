# Microsoft::Bluetooth::Foundation::StateMachineTimer::Init(void)

- ea: `0x180020938`
- end: `0x180020d6b`
- name: `?Init@StateMachineTimer@Foundation@Bluetooth@Microsoft@@AEAAXXZ`
- size: `1075`
- prototype: `void __fastcall(Microsoft::Bluetooth::Foundation::StateMachineTimer *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180020f74`

## callees

- `0x1800017a0`
- `0x180001bcc`
- `0x180001e9c`
- `0x180007f94`
- `0x180007fb4`
- `0x180009944`
- `0x180011b9c`
- `0x18001f1cc`
- `0x18001fba0`
- `0x180020938`
- `0x180020d74`
- `0x180021454`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180020aaa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180020aaa`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002097d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002097d`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180020b08`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180020b08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020bde`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020c63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020bde`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020c63`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180020bfd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180020c7b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180020bfd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180020c7b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180020bef`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180020bef`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180020bc6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180020bc6`

## string_xrefs

- `0x180020ba3`: `onecore\drivers\bluetooth\foundation\lib\ThreadpoolCoordinator.h`
- `0x180020c16`: `onecore\drivers\bluetooth\foundation\lib\ThreadpoolCoordinator.h`
- `0x180020d59`: `onecore\drivers\bluetooth\foundation\lib\ThreadpoolCoordinator.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall Microsoft::Bluetooth::Foundation::StateMachineTimer::Init(
        Microsoft::Bluetooth::Foundation::StateMachineTimer *this)
{
  __int64 v2; // rdx
  signed __int32 v3; // eax
  signed __int32 v4; // ett
  char *v5; // rdi
  volatile signed __int32 *v6; // rbx
  volatile signed __int32 *v7; // rcx
  struct _TP_CALLBACK_ENVIRON_V3 *v8; // r14
  struct wil::details::threadpool_timer_context *v9; // rbx
  _QWORD *v10; // rax
  _QWORD *v11; // rsi
  __int64 v12; // rdi
  unsigned int v13; // r8d
  const char *v14; // r9
  _QWORD *v15; // rdx
  int v16; // edi
  const char *v17; // r9
  PTP_TIMER ThreadpoolTimer; // r14
  struct _TP_TIMER *v19; // r15
  DWORD LastError; // edi
  const char *v21; // r9
  struct wil::details::threadpool_timer_context **v22; // rsi
  struct wil::details::threadpool_timer_context *v23; // r14
  DWORD v24; // edi
  _QWORD *v25; // rdx
  __int64 v26; // rbx
  _QWORD *v27; // [rsp+28h] [rbp-59h] BYREF
  __int128 v28; // [rsp+30h] [rbp-51h]
  int v29; // [rsp+40h] [rbp-41h]
  int v30; // [rsp+44h] [rbp-3Dh]
  RTL_SRWLOCK *v31; // [rsp+48h] [rbp-39h]
  _QWORD *v32; // [rsp+50h] [rbp-31h]
  char v33; // [rsp+58h] [rbp-29h] BYREF
  _QWORD v34[7]; // [rsp+68h] [rbp-19h] BYREF
  _QWORD *v35; // [rsp+A0h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+E0h] [rbp+5Fh]

  v29 = 0;
  AcquireSRWLockExclusive(&Microsoft::Bluetooth::Foundation::SingletonWithFactory<Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator,Microsoft::Bluetooth::Foundation::SingletonDefaultFactory<Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator>>::s_lock);
  v31 = &Microsoft::Bluetooth::Foundation::SingletonWithFactory<Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator,Microsoft::Bluetooth::Foundation::SingletonDefaultFactory<Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator>>::s_lock;
  v28 = 0;
  v2 = *((_QWORD *)&Microsoft::Bluetooth::Foundation::SingletonWithFactory<Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator,Microsoft::Bluetooth::Foundation::SingletonDefaultFactory<Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator>>::s_instance
       + 1);
  if ( *((_QWORD *)&Microsoft::Bluetooth::Foundation::SingletonWithFactory<Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator,Microsoft::Bluetooth::Foundation::SingletonDefaultFactory<Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator>>::s_instance
       + 1) )
  {
    v3 = *(_DWORD *)(*((_QWORD *)&Microsoft::Bluetooth::Foundation::SingletonWithFactory<Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator,Microsoft::Bluetooth::Foundation::SingletonDefaultFactory<Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator>>::s_instance
                     + 1)
                   + 8LL);
    while ( v3 )
    {
      v4 = v3;
      v3 = _InterlockedCompareExchange((volatile signed __int32 *)(v2 + 8), v3 + 1, v3);
      if ( v4 == v3 )
      {
        v28 = Microsoft::Bluetooth::Foundation::SingletonWithFactory<Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator,Microsoft::Bluetooth::Foundation::SingletonDefaultFactory<Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator>>::s_instance;
        break;
      }
    }
  }
  v29 = 1;
  if ( !(_QWORD)v28 )
  {
    v5 = (char *)operator new(0x28u);
    v30 = HIDWORD(v5);
    *(_OWORD *)v5 = 0;
    *((_DWORD *)v5 + 2) = 1;
    *((_DWORD *)v5 + 3) = 1;
    *(_QWORD *)v5 = &std::_Ref_count_obj2<Microsoft::Bluetooth::Foundation::Details::ThreadpoolObjectRegistrar>::`vftable';
    *((_OWORD *)v5 + 1) = 0;
    *((_QWORD *)v5 + 2) = &Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator::`vftable';
    *((_QWORD *)v5 + 3) = 0;
    *((_QWORD *)v5 + 4) = 0;
    v29 = 7;
    *(_QWORD *)&v28 = v5 + 16;
    v6 = (volatile signed __int32 *)*((_QWORD *)&v28 + 1);
    *((_QWORD *)&v28 + 1) = v5;
    if ( v6 )
    {
      if ( _InterlockedExchangeAdd(v6 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v6)(v6);
        if ( _InterlockedExchangeAdd(v6 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 8LL))(v6);
      }
    }
    _InterlockedAdd((volatile signed __int32 *)v5 + 3, 1u);
    *(_QWORD *)&Microsoft::Bluetooth::Foundation::SingletonWithFactory<Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator,Microsoft::Bluetooth::Foundation::SingletonDefaultFactory<Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator>>::s_instance = v5 + 16;
    v7 = (volatile signed __int32 *)*((_QWORD *)&Microsoft::Bluetooth::Foundation::SingletonWithFactory<Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator,Microsoft::Bluetooth::Foundation::SingletonDefaultFactory<Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator>>::s_instance
                                    + 1);
    *((_QWORD *)&Microsoft::Bluetooth::Foundation::SingletonWithFactory<Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator,Microsoft::Bluetooth::Foundation::SingletonDefaultFactory<Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator>>::s_instance
    + 1) = v5;
    if ( v7 && _InterlockedExchangeAdd(v7 + 3, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 8LL))(v7);
  }
  ReleaseSRWLockExclusive(&Microsoft::Bluetooth::Foundation::SingletonWithFactory<Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator,Microsoft::Bluetooth::Foundation::SingletonDefaultFactory<Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator>>::s_lock);
  v34[0] = &std::_Func_impl_no_alloc<_lambda_f604df4af10e482d3da48bf7aa3884e9_,void,>::`vftable';
  v34[1] = this;
  v35 = v34;
  v8 = *(struct _TP_CALLBACK_ENVIRON_V3 **)(v28 + 8);
  v9 = 0;
  v10 = operator new(0x68u, (const struct std::nothrow_t *)&std::nothrow);
  v11 = v10;
  v32 = v10;
  if ( v10 )
  {
    Microsoft::Bluetooth::Foundation::SingletonWithFactory<Microsoft::Bluetooth::Foundation::Details::ThreadpoolObjectRegistrar,Microsoft::Bluetooth::Foundation::SingletonDefaultFactory<Microsoft::Bluetooth::Foundation::Details::ThreadpoolObjectRegistrar>>::Instance(v10);
    v12 = *v11;
    if ( !ResetEvent(*(HANDLE *)(*v11 + 16LL)) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D8, v13, v14);
    _InterlockedIncrement((volatile signed __int32 *)(v12 + 8));
    v11[9] = 0;
    if ( !v35 )
      goto LABEL_23;
    if ( v35 == v34 )
    {
      v11[9] = (*(__int64 (__fastcall **)(_QWORD *, _QWORD *))(*v35 + 8LL))(v35, v11 + 2);
      if ( !v35 )
      {
LABEL_23:
        v11[10] = 0;
        v11[11] = 0;
        *((_DWORD *)v11 + 24) = 0;
        *((_BYTE *)v11 + 100) = 0;
        goto LABEL_25;
      }
      v15 = v34;
      LOBYTE(v15) = v35 != v34;
      (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v35 + 32LL))(v35, v15);
    }
    else
    {
      v11[9] = v35;
    }
    v35 = 0;
    goto LABEL_23;
  }
  v11 = 0;
LABEL_25:
  v27 = v11;
  if ( v11 )
  {
    ThreadpoolTimer = CreateThreadpoolTimer(_lambda_25492e723f3fb512063019ab9c6aa90a_::_lambda_invoker_cdecl_, v11, v8);
    v19 = (struct _TP_TIMER *)v11[10];
    if ( v19 )
    {
      LastError = GetLastError();
      CloseThreadpoolTimer(v19);
      SetLastError(LastError);
    }
    v11[10] = ThreadpoolTimer;
    if ( ThreadpoolTimer )
    {
      v27 = 0;
      v9 = (struct wil::details::threadpool_timer_context *)v11;
      v16 = 0;
    }
    else
    {
      v16 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0x182,
              (unsigned int)"onecore\\drivers\\bluetooth\\foundation\\lib\\ThreadpoolCoordinator.h",
              v17);
    }
  }
  else
  {
    v16 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x177,
      (unsigned int)"onecore\\drivers\\bluetooth\\foundation\\lib\\ThreadpoolCoordinator.h",
      (const char *)0x8007000ELL,
      0);
  }
  std::unique_ptr<wil::details::threadpool_timer_context>::~unique_ptr<wil::details::threadpool_timer_context>(&v27);
  if ( v16 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1AF,
      (unsigned int)"onecore\\drivers\\bluetooth\\foundation\\lib\\ThreadpoolCoordinator.h",
      (const char *)(unsigned int)v16,
      (int)v27);
  v22 = (struct wil::details::threadpool_timer_context **)((char *)this + 24);
  if ( (char *)this + 24 == &v33 )
  {
    if ( v9 )
      wil::details::threadpool_timer_context::RequestRelease(v9);
  }
  else
  {
    v23 = *v22;
    if ( *v22 )
    {
      v24 = GetLastError();
      wil::details::threadpool_timer_context::RequestRelease(v23);
      SetLastError(v24);
    }
    *v22 = v9;
  }
  if ( v35 )
  {
    v25 = v34;
    LOBYTE(v25) = v35 != v34;
    (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v35 + 32LL))(v35, v25);
    v35 = 0;
  }
  if ( *((_QWORD *)&v28 + 1) )
  {
    if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v28 + 1) + 8LL)) )
    {
      v26 = *((_QWORD *)&v28 + 1);
      (***((void (__fastcall ****)(_QWORD))&v28 + 1))(*((_QWORD *)&v28 + 1));
      if ( !_InterlockedDecrement((volatile signed __int32 *)(v26 + 12)) )
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v28 + 1) + 8LL))(*((_QWORD *)&v28 + 1));
    }
  }
  if ( !*v22 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x82,
      (unsigned int)"onecore\\drivers\\bluetooth\\foundation\\lib\\StateMachines.h",
      v21);
}

```

## disassembly

```asm
0x180020938  mov     rax, rsp
0x18002093b  mov     [rax+10h], rbx
0x18002093f  mov     [rax+18h], rsi
0x180020943  mov     [rax+20h], rdi
0x180020947  push    rbp
0x180020948  push    r12
0x18002094a  push    r13
0x18002094c  push    r14
0x18002094e  push    r15
0x180020950  lea     rbp, [rax-5Fh]
0x180020954  sub     rsp, 0B0h
0x18002095b  mov     rax, cs:__security_cookie
0x180020962  xor     rax, rsp
0x180020965  mov     [rbp+57h+var_30], rax
0x180020969  mov     r13, rcx
0x18002096c  xor     r12d, r12d
0x18002096f  mov     dword ptr [rbp+57h+var_98], r12d
0x180020973  lea     r14, ?s_lock@?$SingletonWithFactory@VThreadpoolCoordinator@Foundation@Bluetooth@Microsoft@@U?$SingletonDefaultFactory@VThreadpoolCoordinator@Foundation@Bluetooth@Microsoft@@@234@@Foundation@Bluetooth@Microsoft@@0Vsrwlock@wil@@A; wil::srwlock Microsoft::Bluetooth::Foundation::SingletonWithFactory<Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator,Microsoft::Bluetooth::Foundation::SingletonDefaultFactory<Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator>>::s_lock
0x18002097a  mov     rcx, r14; SRWLock
0x18002097d  call    cs:__imp_AcquireSRWLockExclusive
0x180020984  nop     dword ptr [rax+rax+00h]
0x180020989  mov     [rbp+57h+var_90], r14
0x18002098d  xorps   xmm0, xmm0
0x180020990  movdqu  [rbp+57h+var_A8], xmm0
0x180020995  mov     rdx, qword ptr cs:?s_instance@?$SingletonWithFactory@VThreadpoolCoordinator@Foundation@Bluetooth@Microsoft@@U?$SingletonDefaultFactory@VThreadpoolCoordinator@Foundation@Bluetooth@Microsoft@@@234@@Foundation@Bluetooth@Microsoft@@0V?$weak_ptr@VThreadpoolCoordinator@Foundation@Bluetooth@Microsoft@@@std@@A+8; std::weak_ptr<Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator> Microsoft::Bluetooth::Foundation::SingletonWithFactory<Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator,Microsoft::Bluetooth::Foundation::SingletonDefaultFactory<Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator>>::s_instance
0x18002099c  test    rdx, rdx
0x18002099f  jz      short loc_1800209C2
0x1800209a1  mov     eax, [rdx+8]
0x1800209a4  jmp     short loc_1800209B0
0x1800209a6  lea     ecx, [rax+1]
0x1800209a9  lock cmpxchg [rdx+8], ecx
0x1800209ae  jz      short loc_1800209B6
0x1800209b0  test    eax, eax
0x1800209b2  jnz     short loc_1800209A6
0x1800209b4  jmp     short loc_1800209C2
0x1800209b6  movups  xmm0, cs:?s_instance@?$SingletonWithFactory@VThreadpoolCoordinator@Foundation@Bluetooth@Microsoft@@U?$SingletonDefaultFactory@VThreadpoolCoordinator@Foundation@Bluetooth@Microsoft@@@234@@Foundation@Bluetooth@Microsoft@@0V?$weak_ptr@VThreadpoolCoordinator@Foundation@Bluetooth@Microsoft@@@std@@A; std::weak_ptr<Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator> Microsoft::Bluetooth::Foundation::SingletonWithFactory<Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator,Microsoft::Bluetooth::Foundation::SingletonDefaultFactory<Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator>>::s_instance
0x1800209bd  movdqu  [rbp+57h+var_A8], xmm0
0x1800209c2  mov     r14d, 1
0x1800209c8  mov     dword ptr [rbp+57h+var_98], r14d
0x1800209cc  or      r15d, 0FFFFFFFFh
0x1800209d0  cmp     qword ptr [rbp+57h+var_A8], r12
0x1800209d4  jnz     loc_180020AA3
0x1800209da  lea     ecx, [r14+27h]; Size
0x1800209de  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800209e3  mov     rdi, rax
0x1800209e6  mov     [rbp+57h+var_98], rax
0x1800209ea  xorps   xmm0, xmm0
0x1800209ed  movups  xmmword ptr [rax], xmm0
0x1800209f0  mov     [rax+8], r14d
0x1800209f4  mov     [rax+0Ch], r14d
0x1800209f8  lea     rax, ??_7?$_Ref_count_obj2@VThreadpoolObjectRegistrar@Details@Foundation@Bluetooth@Microsoft@@@std@@6B@; const std::_Ref_count_obj2<Microsoft::Bluetooth::Foundation::Details::ThreadpoolObjectRegistrar>::`vftable'
0x1800209ff  mov     [rdi], rax
0x180020a02  lea     rsi, [rdi+10h]
0x180020a06  movups  xmmword ptr [rsi], xmm0
0x180020a09  lea     rax, ??_7ThreadpoolCoordinator@Foundation@Bluetooth@Microsoft@@6B@; const Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator::`vftable'
0x180020a10  mov     [rsi], rax
0x180020a13  mov     [rsi+8], r12
0x180020a17  mov     [rsi+10h], r12
0x180020a1b  mov     dword ptr [rbp+57h+var_98], 7
0x180020a22  mov     qword ptr [rbp+57h+var_A8], rsi
0x180020a26  mov     rbx, qword ptr [rbp+57h+var_A8+8]
0x180020a2a  mov     qword ptr [rbp+57h+var_A8+8], rdi
0x180020a2e  test    rbx, rbx
0x180020a31  jz      short loc_180020A6A
0x180020a33  mov     eax, r15d
0x180020a36  lock xadd [rbx+8], eax
0x180020a3b  add     eax, r15d
0x180020a3e  jnz     short loc_180020A6A
0x180020a40  mov     rax, [rbx]
0x180020a43  mov     rcx, rbx
0x180020a46  mov     rax, [rax]
0x180020a49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020a4e  mov     eax, r15d
0x180020a51  lock xadd [rbx+0Ch], eax
0x180020a56  add     eax, r15d
0x180020a59  jnz     short loc_180020A6A
0x180020a5b  mov     rax, [rbx]
0x180020a5e  mov     rcx, rbx
0x180020a61  mov     rax, [rax+8]
0x180020a65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020a6a  lock add [rdi+0Ch], r14d
0x180020a6f  mov     qword ptr cs:?s_instance@?$SingletonWithFactory@VThreadpoolCoordinator@Foundation@Bluetooth@Microsoft@@U?$SingletonDefaultFactory@VThreadpoolCoordinator@Foundation@Bluetooth@Microsoft@@@234@@Foundation@Bluetooth@Microsoft@@0V?$weak_ptr@VThreadpoolCoordinator@Foundation@Bluetooth@Microsoft@@@std@@A, rsi; std::weak_ptr<Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator> Microsoft::Bluetooth::Foundation::SingletonWithFactory<Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator,Microsoft::Bluetooth::Foundation::SingletonDefaultFactory<Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator>>::s_instance
0x180020a76  mov     rcx, qword ptr cs:?s_instance@?$SingletonWithFactory@VThreadpoolCoordinator@Foundation@Bluetooth@Microsoft@@U?$SingletonDefaultFactory@VThreadpoolCoordinator@Foundation@Bluetooth@Microsoft@@@234@@Foundation@Bluetooth@Microsoft@@0V?$weak_ptr@VThreadpoolCoordinator@Foundation@Bluetooth@Microsoft@@@std@@A+8; std::weak_ptr<Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator> Microsoft::Bluetooth::Foundation::SingletonWithFactory<Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator,Microsoft::Bluetooth::Foundation::SingletonDefaultFactory<Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator>>::s_instance
0x180020a7d  mov     qword ptr cs:?s_instance@?$SingletonWithFactory@VThreadpoolCoordinator@Foundation@Bluetooth@Microsoft@@U?$SingletonDefaultFactory@VThreadpoolCoordinator@Foundation@Bluetooth@Microsoft@@@234@@Foundation@Bluetooth@Microsoft@@0V?$weak_ptr@VThreadpoolCoordinator@Foundation@Bluetooth@Microsoft@@@std@@A+8, rdi; std::weak_ptr<Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator> Microsoft::Bluetooth::Foundation::SingletonWithFactory<Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator,Microsoft::Bluetooth::Foundation::SingletonDefaultFactory<Microsoft::Bluetooth::Foundation::ThreadpoolCoordinator>>::s_instance
0x180020a84  test    rcx, rcx
0x180020a87  jz      short loc_180020AA3
0x180020a89  mov     eax, r15d
0x180020a8c  lock xadd [rcx+0Ch], eax
0x180020a91  add     eax, r15d
0x180020a94  jnz     short loc_180020AA3
0x180020a96  mov     rax, [rcx]
0x180020a99  mov     rax, [rax+8]
0x180020a9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020aa2  nop
0x180020aa3  lea     rcx, ?s_lock@?$SingletonWithFactory@VThreadpoolCoordinator@Foundation@Bluetooth@Microsoft@@U?$SingletonDefaultFactory@VThreadpoolCoordinator@Foundation@Bluetooth@Microsoft@@@234@@Foundation@Bluetooth@Microsoft@@0Vsrwlock@wil@@A; SRWLock
0x180020aaa  call    cs:__imp_ReleaseSRWLockExclusive
0x180020ab1  nop     dword ptr [rax+rax+00h]
0x180020ab6  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_f604df4af10e482d3da48bf7aa3884e9_@@X$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_f604df4af10e482d3da48bf7aa3884e9_,void,>::`vftable'
0x180020abd  mov     [rbp+57h+var_70], rax
0x180020ac1  mov     [rbp+57h+var_68], r13
0x180020ac5  lea     rax, [rbp+57h+var_70]
0x180020ac9  mov     [rbp+57h+var_38], rax
0x180020acd  mov     rax, qword ptr [rbp+57h+var_A8]
0x180020ad1  mov     r14, [rax+8]
0x180020ad5  mov     rbx, r12
0x180020ad8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180020adf  mov     ecx, 68h ; 'h'; unsigned __int64
0x180020ae4  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180020ae9  mov     rsi, rax
0x180020aec  mov     [rbp+57h+var_88], rax
0x180020af0  test    rax, rax
0x180020af3  jz      loc_180020B8B
0x180020af9  mov     rcx, rax
0x180020afc  call    ?Instance@?$SingletonWithFactory@VThreadpoolObjectRegistrar@Details@Foundation@Bluetooth@Microsoft@@U?$SingletonDefaultFactory@VThreadpoolObjectRegistrar@Details@Foundation@Bluetooth@Microsoft@@@345@@Foundation@Bluetooth@Microsoft@@SA?AV?$shared_ptr@VThreadpoolObjectRegistrar@Details@Foundation@Bluetooth@Microsoft@@@std@@XZ; Microsoft::Bluetooth::Foundation::SingletonWithFactory<Microsoft::Bluetooth::Foundation::Details::ThreadpoolObjectRegistrar,Microsoft::Bluetooth::Foundation::SingletonDefaultFactory<Microsoft::Bluetooth::Foundation::Details::ThreadpoolObjectRegistrar>>::Instance(void)
0x180020b01  mov     rdi, [rsi]
0x180020b04  mov     rcx, [rdi+10h]; hEvent
0x180020b08  call    cs:__imp_ResetEvent
0x180020b0f  nop     dword ptr [rax+rax+00h]
0x180020b14  mov     rcx, [rbp+5Fh]; this
0x180020b18  test    eax, eax
0x180020b1a  jz      loc_180020D4B
0x180020b20  lock inc dword ptr [rdi+8]
0x180020b24  mov     [rsi+48h], r12
0x180020b28  mov     rcx, [rbp+57h+var_38]
0x180020b2c  test    rcx, rcx
0x180020b2f  jz      short loc_180020B77
0x180020b31  lea     rax, [rbp+57h+var_70]
0x180020b35  cmp     rcx, rax
0x180020b38  jnz     short loc_180020B6F
0x180020b3a  mov     rax, [rcx]
0x180020b3d  lea     rdx, [rsi+10h]
0x180020b41  mov     rax, [rax+8]
0x180020b45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020b4a  mov     [rsi+48h], rax
0x180020b4e  mov     rcx, [rbp+57h+var_38]
0x180020b52  test    rcx, rcx
0x180020b55  jz      short loc_180020B77
0x180020b57  mov     rax, [rcx]
0x180020b5a  lea     rdx, [rbp+57h+var_70]
0x180020b5e  cmp     rcx, rdx
0x180020b61  setnz   dl
0x180020b64  mov     rax, [rax+20h]
0x180020b68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020b6d  jmp     short loc_180020B73
0x180020b6f  mov     [rsi+48h], rcx
0x180020b73  mov     [rbp+57h+var_38], r12
0x180020b77  mov     [rsi+50h], r12
0x180020b7b  xor     eax, eax
0x180020b7d  mov     [rsi+58h], rax
0x180020b81  mov     [rsi+60h], r12d
0x180020b85  mov     [rsi+64h], r12b
0x180020b89  jmp     short loc_180020B8E
0x180020b8b  mov     rsi, r12
0x180020b8e  mov     [rbp+57h+var_B0], rsi
0x180020b92  test    rsi, rsi
0x180020b95  jnz     short loc_180020BB9
0x180020b97  mov     rcx, [rbp+5Fh]; this
0x180020b9b  mov     edi, 8007000Eh
0x180020ba0  mov     r9d, edi; char *
0x180020ba3  lea     r8, aOnecoreDrivers_8; "onecore\\drivers\\bluetooth\\foundation"...
0x180020baa  mov     edx, 177h; void *
0x180020baf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020bb4  jmp     loc_180020C39
0x180020bb9  mov     r8, r14; pcbe
0x180020bbc  mov     rdx, rsi; pv
0x180020bbf  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_25492e723f3fb512063019ab9c6aa90a_@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180020bc6  call    cs:__imp_CreateThreadpoolTimer
0x180020bcd  nop     dword ptr [rax+rax+00h]
0x180020bd2  mov     r14, rax
0x180020bd5  mov     r15, [rsi+50h]
0x180020bd9  test    r15, r15
0x180020bdc  jz      short loc_180020C09
0x180020bde  call    cs:__imp_GetLastError
0x180020be5  nop     dword ptr [rax+rax+00h]
0x180020bea  mov     edi, eax
0x180020bec  mov     rcx, r15; pti
0x180020bef  call    cs:__imp_CloseThreadpoolTimer
0x180020bf6  nop     dword ptr [rax+rax+00h]
0x180020bfb  mov     ecx, edi; dwErrCode
0x180020bfd  call    cs:__imp_SetLastError
0x180020c04  nop     dword ptr [rax+rax+00h]
0x180020c09  mov     [rsi+50h], r14
0x180020c0d  test    r14, r14
0x180020c10  jnz     short loc_180020C2B
0x180020c12  mov     rcx, [rbp+5Fh]; this
0x180020c16  lea     r8, aOnecoreDrivers_8; "onecore\\drivers\\bluetooth\\foundation"...
0x180020c1d  mov     edx, 182h; void *
0x180020c22  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180020c27  mov     edi, eax
0x180020c29  jmp     short loc_180020C35
0x180020c2b  mov     [rbp+57h+var_B0], r12
0x180020c2f  mov     rbx, rsi
0x180020c32  mov     edi, r12d
0x180020c35  or      r15d, 0FFFFFFFFh
0x180020c39  lea     rcx, [rbp+57h+var_B0]
0x180020c3d  call    ??1?$unique_ptr@Uthreadpool_timer_context@details@wil@@U?$default_delete@Uthreadpool_timer_context@details@wil@@@std@@@std@@QEAA@XZ; std::unique_ptr<wil::details::threadpool_timer_context>::~unique_ptr<wil::details::threadpool_timer_context>(void)
0x180020c42  mov     rcx, [rbp+5Fh]; this
0x180020c46  test    edi, edi
0x180020c48  js      loc_180020D56
0x180020c4e  lea     rsi, [r13+18h]
0x180020c52  lea     rax, [rbp+57h+var_80]
0x180020c56  cmp     rsi, rax
0x180020c59  jz      short loc_180020C8C
0x180020c5b  mov     r14, [rsi]
0x180020c5e  test    r14, r14
0x180020c61  jz      short loc_180020C87
0x180020c63  call    cs:__imp_GetLastError
0x180020c6a  nop     dword ptr [rax+rax+00h]
0x180020c6f  mov     edi, eax
0x180020c71  mov     rcx, r14; this
0x180020c74  call    ?RequestRelease@threadpool_timer_context@details@wil@@SAXPEAU123@@Z; wil::details::threadpool_timer_context::RequestRelease(wil::details::threadpool_timer_context *)
0x180020c79  mov     ecx, edi; dwErrCode
0x180020c7b  call    cs:__imp_SetLastError
0x180020c82  nop     dword ptr [rax+rax+00h]
0x180020c87  mov     [rsi], rbx
0x180020c8a  jmp     short loc_180020C9A
0x180020c8c  test    rbx, rbx
0x180020c8f  jz      short loc_180020C9A
0x180020c91  mov     rcx, rbx; this
0x180020c94  call    ?RequestRelease@threadpool_timer_context@details@wil@@SAXPEAU123@@Z; wil::details::threadpool_timer_context::RequestRelease(wil::details::threadpool_timer_context *)
0x180020c99  nop
0x180020c9a  mov     rcx, [rbp+57h+var_38]
0x180020c9e  test    rcx, rcx
0x180020ca1  jz      short loc_180020CBD
0x180020ca3  mov     rax, [rcx]
0x180020ca6  lea     rdx, [rbp+57h+var_70]
0x180020caa  cmp     rcx, rdx
0x180020cad  setnz   dl
0x180020cb0  mov     rax, [rax+20h]
0x180020cb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020cb9  mov     [rbp+57h+var_38], r12
0x180020cbd  mov     rcx, qword ptr [rbp+57h+var_A8+8]
0x180020cc1  test    rcx, rcx
0x180020cc4  jz      short loc_180020D02
0x180020cc6  mov     eax, r15d
0x180020cc9  lock xadd [rcx+8], eax
0x180020cce  add     eax, r15d
0x180020cd1  jnz     short loc_180020D02
0x180020cd3  mov     rbx, qword ptr [rbp+57h+var_A8+8]
0x180020cd7  mov     rax, [rbx]
0x180020cda  mov     rcx, rbx
0x180020cdd  mov     rax, [rax]
0x180020ce0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020ce5  mov     eax, r15d
0x180020ce8  lock xadd [rbx+0Ch], eax
0x180020ced  add     eax, r15d
0x180020cf0  jnz     short loc_180020D02
0x180020cf2  mov     rcx, qword ptr [rbp+57h+var_A8+8]
0x180020cf6  mov     rax, [rcx]
0x180020cf9  mov     rax, [rax+8]
0x180020cfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020d02  cmp     [rsi], r12
0x180020d05  jz      short loc_180020D35
0x180020d07  mov     rcx, [rbp+57h+var_30]
0x180020d0b  xor     rcx, rsp; StackCookie
0x180020d0e  call    __security_check_cookie
0x180020d13  lea     r11, [rsp+0D0h+var_20]
0x180020d1b  mov     rbx, [r11+38h]
0x180020d1f  mov     rsi, [r11+40h]
0x180020d23  mov     rdi, [r11+48h]
0x180020d27  mov     rsp, r11
0x180020d2a  pop     r15
0x180020d2c  pop     r14
0x180020d2e  pop     r13
0x180020d30  pop     r12
0x180020d32  pop     rbp
0x180020d33  retn
0x180020d35  mov     rcx, [rbp+5Fh]; this
0x180020d39  lea     r8, aOnecoreDrivers_5; "onecore\\drivers\\bluetooth\\foundation"...
0x180020d40  mov     edx, 82h; void *
0x180020d45  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180020d4b  mov     edx, 9D8h; void *
0x180020d50  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180020d56  mov     r9d, edi; char *
0x180020d59  lea     r8, aOnecoreDrivers_8; "onecore\\drivers\\bluetooth\\foundation"...
0x180020d60  mov     edx, 1AFh; void *
0x180020d65  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
