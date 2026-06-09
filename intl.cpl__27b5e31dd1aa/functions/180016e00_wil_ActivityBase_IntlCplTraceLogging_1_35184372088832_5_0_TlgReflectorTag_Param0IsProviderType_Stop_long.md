# wil::ActivityBase<IntlCplTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x180016e00`
- end: `0x180016ed6`
- name: `?Stop@?$ActivityBase@VIntlCplTraceLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `214`
- prototype: ``
- caller_count: `6`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180014c90`
- `0x180017cf0`
- `0x18001ebc8`
- `0x180024900`
- `0x180026304`
- `0x180026994`

## callees

- `0x1800017fc`
- `0x180001c94`
- `0x1800093fc`
- `0x18000ac00`
- `0x18000d524`
- `0x18000d548`
- `0x18000e590`
- `0x180016e00`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016e78`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016e78`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<IntlCplTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
        _QWORD *a1,
        unsigned int a2)
{
  char v4; // bl
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // r9
  const struct _tlgProvider_t *v8; // rax
  int v9; // ebx
  DWORD CurrentThreadId; // eax
  __int64 v11; // r8
  int v12; // r9d
  DWORD v14; // [rsp+60h] [rbp+8h] BYREF
  unsigned int v15; // [rsp+70h] [rbp+18h] BYREF
  __int64 v16; // [rsp+78h] [rbp+20h] BYREF

  v14 = 0;
  wil::ActivityBase<IntlCplTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &v15);
  v4 = wil::ActivityBase<IntlCplTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<IntlCplTraceLogging,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
         a1[34],
         a2,
         &v14);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v15);
  if ( v4 )
  {
    (*(void (__fastcall **)(_QWORD *))(*a1 + 8LL))(a1);
  }
  else
  {
    v8 = IntlCplTraceLogging::Provider();
    v9 = (int)v8;
    if ( *(_DWORD *)v8 > 5u && (unsigned __int8)tlgKeywordOn(v8, 0x200000000000LL) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v11 = a1[34];
      v14 = CurrentThreadId;
      v15 = a2;
      v16 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v9,
        (unsigned int)&unk_180033922,
        v11 + 8,
        v12,
        (__int64)&v16,
        (__int64)&v15,
        (__int64)&v14);
    }
  }
  return wil::ActivityBase<IntlCplTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
           a1,
           v5,
           v6,
           v7);
}

```

## disassembly

```asm
0x180016e00  push    rbx
0x180016e02  push    rsi
0x180016e03  push    rdi
0x180016e04  sub     rsp, 40h
0x180016e08  mov     esi, edx
0x180016e0a  mov     [rsp+58h+arg_0], 0
0x180016e12  lea     rdx, [rsp+58h+arg_10]
0x180016e17  mov     rdi, rcx
0x180016e1a  call    ?LockExclusive@?$ActivityBase@VIntlCplTraceLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<IntlCplTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180016e1f  mov     rcx, [rdi+110h]
0x180016e26  lea     r8, [rsp+58h+arg_0]
0x180016e2b  mov     edx, esi
0x180016e2d  call    ?SetStopResult@?$ActivityData@VIntlCplTraceLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VIntlCplTraceLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA_NJPEAJ@Z; wil::ActivityBase<IntlCplTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<IntlCplTraceLogging,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(long,long *)
0x180016e32  lea     rcx, [rsp+58h+arg_10]
0x180016e37  mov     bl, al
0x180016e39  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180016e3e  test    bl, bl
0x180016e40  jz      short loc_180016E53
0x180016e42  mov     rax, [rdi]
0x180016e45  mov     rcx, rdi
0x180016e48  mov     rax, [rax+8]
0x180016e4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016e51  jmp     short loc_180016EC7
0x180016e53  call    ?Provider@IntlCplTraceLogging@@SAPEBU_tlgProvider_t@@XZ; IntlCplTraceLogging::Provider(void)
0x180016e58  mov     rbx, rax
0x180016e5b  mov     ecx, [rax]
0x180016e5d  cmp     ecx, 5
0x180016e60  jbe     short loc_180016EC7
0x180016e62  mov     rdx, 200000000000h
0x180016e6c  mov     rcx, rax
0x180016e6f  call    _tlgKeywordOn
0x180016e74  test    al, al
0x180016e76  jz      short loc_180016EC7
0x180016e78  call    cs:__imp_GetCurrentThreadId
0x180016e7e  mov     r8, [rdi+110h]
0x180016e85  lea     rdx, unk_180033922
0x180016e8c  mov     [rsp+58h+arg_0], eax
0x180016e90  add     r8, 8
0x180016e94  lea     rax, [rsp+58h+arg_0]
0x180016e99  mov     [rsp+58h+arg_10], esi
0x180016e9d  mov     [rsp+58h+var_28], rax
0x180016ea2  mov     rcx, rbx
0x180016ea5  lea     rax, [rsp+58h+arg_10]
0x180016eaa  mov     [rsp+58h+arg_18], 1000000h
0x180016eb3  mov     [rsp+58h+var_30], rax
0x180016eb8  lea     rax, [rsp+58h+arg_18]
0x180016ebd  mov     [rsp+58h+var_38], rax
0x180016ec2  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180016ec7  mov     rcx, rdi
0x180016eca  add     rsp, 40h
0x180016ece  pop     rdi
0x180016ecf  pop     rsi
0x180016ed0  pop     rbx
0x180016ed1  jmp     ?IgnoreCurrentThread@?$ActivityBase@VIntlCplTraceLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<IntlCplTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
