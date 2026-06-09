# ?Start@ThreadpoolWait@@QEAAX$$QEAV?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@$$QEAV?$function@$$A6AXXZ@std@@PEAU_FILETIME@@@Z

- ea: `0x180019880`
- end: `0x180019997`
- name: `?Start@ThreadpoolWait@@QEAAX$$QEAV?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@$$QEAV?$function@$$A6AXXZ@std@@PEAU_FILETIME@@@Z`
- size: `279`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180018a30`
- `0x180077b90`

## callees

- `0x180008390`
- `0x1800104b0`
- `0x180011da0`
- `0x180019880`
- `0x18001a18c`
- `0x18001a510`
- `0x18002d848`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800198a1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800198a1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180019984`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180019984`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180019972`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180019972`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180019937`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180019937`

## string_xrefs

- `0x1800198b7`: `shell\onecore\desktopshellext\inc\ThreadpoolWaitHelpers.h`
- `0x180019957`: `shell\onecore\desktopshellext\inc\ThreadpoolWaitHelpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ThreadpoolWait::Start(RTL_SRWLOCK *a1, __int64 *a2, __int64 a3)
{
  RTL_SRWLOCK *v6; // rbp
  const char *v7; // r9
  _DWORD *Ptr; // rax
  volatile signed __int32 *v9; // rax
  PVOID v10; // rcx
  std::_Ref_count_base *v11; // rcx
  PTP_WAIT ThreadpoolWait; // rax
  const char *v13; // r9
  struct _TP_WAIT *v14; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v6 = a1 + 2;
  AcquireSRWLockExclusive(a1 + 2);
  if ( LOBYTE(a1[11].Ptr) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x97,
      (unsigned int)"shell\\onecore\\desktopshellext\\inc\\ThreadpoolWaitHelpers.h",
      v7);
  Ptr = a1[13].Ptr;
  if ( !Ptr || !Ptr[2] )
  {
    v9 = (volatile signed __int32 *)a1[1].Ptr;
    if ( v9 )
    {
      v10 = a1->Ptr;
      _InterlockedIncrement(v9 + 3);
    }
    else
    {
      v10 = 0;
    }
    a1[12].Ptr = v10;
    v11 = (std::_Ref_count_base *)a1[13].Ptr;
    a1[13].Ptr = (PVOID)v9;
    if ( v11 )
      std::_Ref_count_base::_Decwref(v11);
  }
  if ( &a1[15] != (RTL_SRWLOCK *)a2 )
  {
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      &a1[15],
      *a2);
    *a2 = 0;
  }
  std::function<void (void)>::operator=(&a1[3], a3);
  ThreadpoolWait = CreateThreadpoolWait(
                     _lambda_8b0b9dbd4459d626ffc8152be8328efc_::_lambda_invoker_cdecl_<_TP_CALLBACK_INSTANCE *,void *,_TP_WAIT *,long>,
                     &a1[12],
                     0);
  wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&public: static void wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(
    &a1[14],
    ThreadpoolWait);
  v14 = (struct _TP_WAIT *)a1[14].Ptr;
  if ( !v14 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xBC,
      (unsigned int)"shell\\onecore\\desktopshellext\\inc\\ThreadpoolWaitHelpers.h",
      v13);
  SetThreadpoolWait(v14, a1[15].Ptr, 0);
  LOBYTE(a1[11].Ptr) = 1;
  if ( v6 )
    ReleaseSRWLockExclusive(v6);
}

```

## disassembly

```asm
0x180019880  mov     [rsp+arg_18], r9
0x180019885  push    rbx
0x180019886  push    rbp
0x180019887  push    rsi
0x180019888  push    rdi
0x180019889  push    r14
0x18001988b  push    r15
0x18001988d  sub     rsp, 28h
0x180019891  mov     r15, r8
0x180019894  mov     rbx, rdx
0x180019897  mov     rdi, rcx
0x18001989a  lea     rbp, [rcx+10h]
0x18001989e  mov     rcx, rbp; SRWLock
0x1800198a1  call    cs:__imp_AcquireSRWLockExclusive
0x1800198a7  mov     [rsp+58h+arg_18], rbp
0x1800198ac  mov     rcx, [rsp+58h]; this
0x1800198b1  cmp     byte ptr [rdi+58h], 0
0x1800198b5  jz      short loc_1800198C9
0x1800198b7  lea     r8, aShellOnecoreDe_6; "shell\\onecore\\desktopshellext\\inc\\T"...
0x1800198be  mov     edx, 97h; void *
0x1800198c3  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800198c9  mov     rax, [rdi+68h]
0x1800198cd  test    rax, rax
0x1800198d0  jz      short loc_1800198D8
0x1800198d2  cmp     dword ptr [rax+8], 0
0x1800198d6  jnz     short loc_180019902
0x1800198d8  mov     rax, [rdi+8]
0x1800198dc  test    rax, rax
0x1800198df  jz      short loc_1800198EA
0x1800198e1  mov     rcx, [rdi]
0x1800198e4  lock inc dword ptr [rax+0Ch]
0x1800198e8  jmp     short loc_1800198EC
0x1800198ea  xor     ecx, ecx
0x1800198ec  mov     [rdi+60h], rcx
0x1800198f0  mov     rcx, [rdi+68h]; this
0x1800198f4  mov     [rdi+68h], rax
0x1800198f8  test    rcx, rcx
0x1800198fb  jz      short loc_180019902
0x1800198fd  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x180019902  lea     r14, [rdi+78h]
0x180019906  cmp     r14, rbx
0x180019909  jz      short loc_18001991D
0x18001990b  mov     rdx, [rbx]
0x18001990e  mov     rcx, r14
0x180019911  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180019916  mov     qword ptr [rbx], 0
0x18001991d  lea     rcx, [rdi+18h]
0x180019921  mov     rdx, r15
0x180019924  call    ??4?$function@$$A6AXXZ@std@@QEAAAEAV01@$$QEAV01@@Z; std::function<void (void)>::operator=(std::function<void (void)> &&)
0x180019929  xor     r8d, r8d; pcbe
0x18001992c  lea     rdx, [rdi+60h]; pv
0x180019930  lea     rcx, ??$_lambda_invoker_cdecl_@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@_lambda_8b0b9dbd4459d626ffc8152be8328efc_@@CA?A_PPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x180019937  call    cs:__imp_CreateThreadpoolWait
0x18001993d  mov     rdx, rax
0x180019940  lea     rcx, [rdi+70h]
0x180019944  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_WAIT@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>::reset(_TP_WAIT *)
0x180019949  mov     rcx, [rdi+70h]; pwa
0x18001994d  mov     rax, [rsp+58h]
0x180019952  test    rcx, rcx
0x180019955  jnz     short loc_18001996C
0x180019957  lea     r8, aShellOnecoreDe_6; "shell\\onecore\\desktopshellext\\inc\\T"...
0x18001995e  mov     edx, 0BCh; void *
0x180019963  mov     rcx, rax; this
0x180019966  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18001996c  xor     r8d, r8d; pftTimeout
0x18001996f  mov     rdx, [r14]; h
0x180019972  call    cs:__imp_SetThreadpoolWait
0x180019978  mov     byte ptr [rdi+58h], 1
0x18001997c  test    rbp, rbp
0x18001997f  jz      short loc_18001998A
0x180019981  mov     rcx, rbp; SRWLock
0x180019984  call    cs:__imp_ReleaseSRWLockExclusive
0x18001998a  add     rsp, 28h
0x18001998e  pop     r15
0x180019990  pop     r14
0x180019992  pop     rdi
0x180019993  pop     rsi
0x180019994  pop     rbp
0x180019995  pop     rbx
0x180019996  retn
```
