# CheckMissingMasterKeyDecryption(_GUID)

- ea: `0x18001af90`
- end: `0x18001b0d2`
- name: `?CheckMissingMasterKeyDecryption@@YAJU_GUID@@@Z`
- size: `322`
- prototype: `__int64 __fastcall(struct _GUID *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800193c0`

## callees

- `0x180010d14`
- `0x180010dc4`
- `0x18001142c`
- `0x180011668`
- `0x1800116ec`
- `0x1800125e8`
- `0x18001af90`
- `0x18001c760`
- `0x18001c808`
- `0x18001c974`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18001b099`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18001b099`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18001b033`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18001b033`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001afa9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001afa9`

## string_xrefs

- `0x18001afd9`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\masterkeydiagnosticlog.cpp`
- `0x18001b05b`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\masterkeydiagnosticlog.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CheckMissingMasterKeyDecryption(struct _GUID *a1)
{
  HLOCAL v2; // rax
  PTP_WORK ThreadpoolWork; // rax
  const char *v5; // r9
  unsigned int LastError; // ebx
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  struct _GUID *v9; // [rsp+38h] [rbp+10h] BYREF
  PVOID pv; // [rsp+40h] [rbp+18h] BYREF
  PTP_WORK pwk; // [rsp+48h] [rbp+20h] BYREF

  v9 = 0;
  v2 = LocalAlloc(0, 0x10u);
  wil::details::unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>::reset(
    &v9,
    v2);
  if ( v9 )
  {
    *v9 = *a1;
    std::make_unique<ThreadPoolWorkPayload,,0>(&pv);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>>::operator=(
      pv,
      &v9);
    pwk = 0;
    ThreadpoolWork = CreateThreadpoolWork(CheckMissingMasterKeyDecryptionFn, pv, 0);
    wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<2>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::reset(
      &pwk,
      ThreadpoolWork);
    if ( pwk )
    {
      pv = 0;
      SubmitThreadpoolWork(pwk);
      wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<2>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<2>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>(&pwk);
      std::unique_ptr<ThreadPoolWorkPayload>::~unique_ptr<ThreadPoolWorkPayload>(&pv);
      wil::details::unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>((void **)&v9);
      return 0;
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x3A1,
                    (unsigned int)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\masterkeydiagnosticlog.cpp",
                    v5);
      wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<2>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<2>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>(&pwk);
      std::unique_ptr<ThreadPoolWorkPayload>::~unique_ptr<ThreadPoolWorkPayload>(&pv);
      wil::details::unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>((void **)&v9);
      return LastError;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x393,
      (unsigned int)"onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\masterkeydiagnosticlog.cpp",
      (const char *)0x8007000ELL,
      v7);
    wil::details::unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>((void **)&v9);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x18001af90  push    rbx; int
0x18001af92  sub     rsp, 20h
0x18001af96  mov     rbx, rcx
0x18001af99  mov     [rsp+28h+arg_8], 0
0x18001afa2  mov     edx, 10h; uBytes
0x18001afa7  xor     ecx, ecx; uFlags
0x18001afa9  call    cs:__imp_LocalAlloc
0x18001afb0  nop     dword ptr [rax+rax+00h]
0x18001afb5  mov     rdx, rax
0x18001afb8  lea     rcx, [rsp+28h+arg_8]
0x18001afbd  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_GUID@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_GUID@@@Z; wil::details::unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>::reset(_GUID *)
0x18001afc2  mov     rax, [rsp+28h+arg_8]
0x18001afc7  test    rax, rax
0x18001afca  jnz     short loc_18001AFFB
0x18001afcc  mov     rcx, [rsp+28h]; this
0x18001afd1  mov     ebx, 8007000Eh
0x18001afd6  mov     r9d, ebx; char *
0x18001afd9  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18001afe0  mov     edx, 393h; void *
0x18001afe5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001afea  lea     rcx, [rsp+28h+arg_8]
0x18001afef  call    ??1?$unique_storage@U?$resource_policy@PEAU_GUID@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>(void)
0x18001aff4  mov     eax, ebx
0x18001aff6  jmp     loc_18001B0CB
0x18001affb  movaps  xmm0, xmmword ptr [rbx]
0x18001affe  movdqu  xmmword ptr [rax], xmm0
0x18001b002  lea     rcx, [rsp+28h+pv]
0x18001b007  call    ??$make_unique@UThreadPoolWorkPayload@@$$V$0A@@std@@YA?AV?$unique_ptr@UThreadPoolWorkPayload@@U?$default_delete@UThreadPoolWorkPayload@@@std@@@0@XZ; std::make_unique<ThreadPoolWorkPayload,,0>(void)
0x18001b00c  lea     rdx, [rsp+28h+arg_8]
0x18001b011  mov     rcx, [rsp+28h+pv]
0x18001b016  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_GUID@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>> &&)
0x18001b01b  mov     [rsp+28h+pwk], 0
0x18001b024  xor     r8d, r8d; pcbe
0x18001b027  mov     rdx, [rsp+28h+pv]; pv
0x18001b02c  lea     rcx, ?CheckMissingMasterKeyDecryptionFn@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18001b033  call    cs:__imp_CreateThreadpoolWork
0x18001b03a  nop     dword ptr [rax+rax+00h]
0x18001b03f  mov     rdx, rax
0x18001b042  lea     rcx, [rsp+28h+pwk]
0x18001b047  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_WORK@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWork@$01@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_WORK@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<2>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::reset(_TP_WORK *)
0x18001b04c  mov     rcx, [rsp+28h+pwk]; pwk
0x18001b051  test    rcx, rcx
0x18001b054  jnz     short loc_18001B090
0x18001b056  mov     rcx, [rsp+28h]; this
0x18001b05b  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18001b062  mov     edx, 3A1h; void *
0x18001b067  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001b06c  mov     ebx, eax
0x18001b06e  lea     rcx, [rsp+28h+pwk]
0x18001b073  call    ??1?$unique_storage@U?$resource_policy@PEAU_TP_WORK@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWork@$01@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<2>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<2>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>(void)
0x18001b078  lea     rcx, [rsp+28h+pv]
0x18001b07d  call    ??1?$unique_ptr@UThreadPoolWorkPayload@@U?$default_delete@UThreadPoolWorkPayload@@@std@@@std@@QEAA@XZ; std::unique_ptr<ThreadPoolWorkPayload>::~unique_ptr<ThreadPoolWorkPayload>(void)
0x18001b082  lea     rcx, [rsp+28h+arg_8]
0x18001b087  call    ??1?$unique_storage@U?$resource_policy@PEAU_GUID@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>(void)
0x18001b08c  mov     eax, ebx
0x18001b08e  jmp     short loc_18001B0CB
0x18001b090  mov     [rsp+28h+pv], 0
0x18001b099  call    cs:__imp_SubmitThreadpoolWork
0x18001b0a0  nop     dword ptr [rax+rax+00h]
0x18001b0a5  lea     rcx, [rsp+28h+pwk]
0x18001b0aa  call    ??1?$unique_storage@U?$resource_policy@PEAU_TP_WORK@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWork@$01@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<2>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<2>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>(void)
0x18001b0af  lea     rcx, [rsp+28h+pv]
0x18001b0b4  call    ??1?$unique_ptr@UThreadPoolWorkPayload@@U?$default_delete@UThreadPoolWorkPayload@@@std@@@std@@QEAA@XZ; std::unique_ptr<ThreadPoolWorkPayload>::~unique_ptr<ThreadPoolWorkPayload>(void)
0x18001b0b9  lea     rcx, [rsp+28h+arg_8]
0x18001b0be  call    ??1?$unique_storage@U?$resource_policy@PEAU_GUID@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_GUID *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_GUID *,_GUID *,0,std::nullptr_t>>(void)
0x18001b0c3  xor     eax, eax
0x18001b0c5  jmp     short loc_18001B0CB
0x18001b0c7  mov     eax, dword ptr [rsp+28h+arg_8]
0x18001b0cb  add     rsp, 20h
0x18001b0cf  pop     rbx
0x18001b0d0  retn
```
