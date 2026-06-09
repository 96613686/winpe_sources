# ThreadpoolTimer::Start(std::function<void (void)> &&,_FILETIME *)

- ea: `0x1800194f0`
- end: `0x1800195f6`
- name: `?Start@ThreadpoolTimer@@QEAAX$$QEAV?$function@$$A6AXXZ@std@@PEAU_FILETIME@@@Z`
- size: `262`
- prototype: ``
- caller_count: `7`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1800188e0`
- `0x180018eb4`
- `0x1800191e4`
- `0x1800192c4`
- `0x1800199a0`
- `0x18001a630`
- `0x18004e284`

## callees

- `0x180004980`
- `0x180008390`
- `0x1800194f0`
- `0x18001a18c`
- `0x18001a510`
- `0x18002d848`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180019512`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180019512`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800195dd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800195dd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800195cb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800195cb`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180019591`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180019591`

## string_xrefs

- `0x180019528`: `shell\onecore\desktopshellext\inc\ThreadpoolWaitHelpers.h`
- `0x1800195ad`: `shell\onecore\desktopshellext\inc\ThreadpoolWaitHelpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ThreadpoolTimer::Start(__int64 *a1, __int64 a2, struct _FILETIME *a3)
{
  RTL_SRWLOCK *v6; // rsi
  const char *v7; // r9
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rcx
  std::_Ref_count_base *v11; // rcx
  struct _TP_TIMER *ThreadpoolTimer; // rax
  const char *v13; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v6 = (RTL_SRWLOCK *)(a1 + 2);
  AcquireSRWLockExclusive((PSRWLOCK)a1 + 2);
  if ( *((_BYTE *)a1 + 88) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x11,
      (unsigned int)"shell\\onecore\\desktopshellext\\inc\\ThreadpoolWaitHelpers.h",
      v7);
  v8 = a1[13];
  if ( !v8 || !*(_DWORD *)(v8 + 8) )
  {
    v9 = a1[1];
    if ( v9 )
    {
      v10 = *a1;
      _InterlockedIncrement((volatile signed __int32 *)(v9 + 12));
    }
    else
    {
      v10 = 0;
    }
    a1[12] = v10;
    v11 = (std::_Ref_count_base *)a1[13];
    a1[13] = v9;
    if ( v11 )
      std::_Ref_count_base::_Decwref(v11);
  }
  std::function<void (void)>::operator=(a1 + 3, a2);
  ThreadpoolTimer = CreateThreadpoolTimer(
                      _lambda_15a91b6fe58e2949bad0dd29371232e8_::_lambda_invoker_cdecl_<_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *>,
                      a1 + 12,
                      0);
  wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
    (struct _TP_TIMER **)a1 + 14,
    ThreadpoolTimer);
  if ( !a1[14] )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x34,
      (unsigned int)"shell\\onecore\\desktopshellext\\inc\\ThreadpoolWaitHelpers.h",
      v13);
  SetThreadpoolTimer((PTP_TIMER)a1[14], a3, 0, 0);
  *((_BYTE *)a1 + 88) = 1;
  if ( v6 )
    ReleaseSRWLockExclusive(v6);
}

```

## disassembly

```asm
0x1800194f0  mov     [rsp+arg_8], rbx
0x1800194f5  mov     [rsp+arg_10], rbp
0x1800194fa  push    rsi
0x1800194fb  push    rdi
0x1800194fc  push    r14
0x1800194fe  sub     rsp, 20h
0x180019502  mov     rbp, r8
0x180019505  mov     rbx, rdx
0x180019508  mov     rdi, rcx
0x18001950b  lea     rsi, [rcx+10h]
0x18001950f  mov     rcx, rsi; SRWLock
0x180019512  call    cs:__imp_AcquireSRWLockExclusive
0x180019518  mov     [rsp+38h+arg_0], rsi
0x18001951d  mov     rcx, [rsp+38h]; this
0x180019522  cmp     byte ptr [rdi+58h], 0
0x180019526  jz      short loc_18001953A
0x180019528  lea     r8, aShellOnecoreDe_6; "shell\\onecore\\desktopshellext\\inc\\T"...
0x18001952f  mov     edx, 11h; void *
0x180019534  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18001953a  mov     rax, [rdi+68h]
0x18001953e  test    rax, rax
0x180019541  jz      short loc_180019549
0x180019543  cmp     dword ptr [rax+8], 0
0x180019547  jnz     short loc_180019573
0x180019549  mov     rax, [rdi+8]
0x18001954d  test    rax, rax
0x180019550  jz      short loc_18001955B
0x180019552  mov     rcx, [rdi]
0x180019555  lock inc dword ptr [rax+0Ch]
0x180019559  jmp     short loc_18001955D
0x18001955b  xor     ecx, ecx
0x18001955d  mov     [rdi+60h], rcx
0x180019561  mov     rcx, [rdi+68h]; this
0x180019565  mov     [rdi+68h], rax
0x180019569  test    rcx, rcx
0x18001956c  jz      short loc_180019573
0x18001956e  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x180019573  lea     rcx, [rdi+18h]
0x180019577  mov     rdx, rbx
0x18001957a  call    ??4?$function@$$A6AXXZ@std@@QEAAAEAV01@$$QEAV01@@Z; std::function<void (void)>::operator=(std::function<void (void)> &&)
0x18001957f  lea     rbx, [rdi+70h]
0x180019583  xor     r8d, r8d; pcbe
0x180019586  lea     rdx, [rdi+60h]; pv
0x18001958a  lea     rcx, ??$_lambda_invoker_cdecl_@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@_lambda_15a91b6fe58e2949bad0dd29371232e8_@@CA?A_PPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180019591  call    cs:__imp_CreateThreadpoolTimer
0x180019597  mov     rdx, rax
0x18001959a  mov     rcx, rbx
0x18001959d  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800195a2  mov     rcx, [rsp+38h]; this
0x1800195a7  cmp     qword ptr [rbx], 0
0x1800195ab  jnz     short loc_1800195BF
0x1800195ad  lea     r8, aShellOnecoreDe_6; "shell\\onecore\\desktopshellext\\inc\\T"...
0x1800195b4  mov     edx, 34h ; '4'; void *
0x1800195b9  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800195bf  xor     r9d, r9d; msWindowLength
0x1800195c2  xor     r8d, r8d; msPeriod
0x1800195c5  mov     rdx, rbp; pftDueTime
0x1800195c8  mov     rcx, [rbx]; pti
0x1800195cb  call    cs:__imp_SetThreadpoolTimer
0x1800195d1  mov     byte ptr [rdi+58h], 1
0x1800195d5  test    rsi, rsi
0x1800195d8  jz      short loc_1800195E3
0x1800195da  mov     rcx, rsi; SRWLock
0x1800195dd  call    cs:__imp_ReleaseSRWLockExclusive
0x1800195e3  mov     rbx, [rsp+38h+arg_8]
0x1800195e8  mov     rbp, [rsp+38h+arg_10]
0x1800195ed  add     rsp, 20h
0x1800195f1  pop     r14
0x1800195f3  pop     rdi
0x1800195f4  pop     rsi
0x1800195f5  retn
```
