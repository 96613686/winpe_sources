# wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x180008fd0`
- end: `0x1800090a6`
- name: `?Stop@?$ActivityBase@VAdvancedSettingsLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `214`
- prototype: ``
- caller_count: `11`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x1800076f0`
- `0x18000a9c0`
- `0x18000abc8`
- `0x180014f30`
- `0x1800151fc`
- `0x180015324`
- `0x1800154e8`
- `0x18001568c`
- `0x180015858`
- `0x1800159cc`
- `0x180015b98`

## callees

- `0x18000141c`
- `0x180001bac`
- `0x1800070ac`
- `0x180007698`
- `0x1800079f0`
- `0x18000845c`
- `0x180008b9c`
- `0x180008fd0`
- `0x18001a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009048`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009048`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
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
  wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &v15);
  v4 = wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<AdvancedSettingsLogging,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
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
    v8 = AdvancedSettingsLogging::Provider();
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
        (unsigned int)&byte_180020F77,
        v11 + 8,
        v12,
        (__int64)&v16,
        (__int64)&v15,
        (__int64)&v14);
    }
  }
  return wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
           a1,
           v5,
           v6,
           v7);
}

```

## disassembly

```asm
0x180008fd0  push    rbx
0x180008fd2  push    rsi
0x180008fd3  push    rdi
0x180008fd4  sub     rsp, 40h
0x180008fd8  mov     esi, edx
0x180008fda  mov     [rsp+58h+arg_0], 0
0x180008fe2  lea     rdx, [rsp+58h+arg_10]
0x180008fe7  mov     rdi, rcx
0x180008fea  call    ?LockExclusive@?$ActivityBase@VNetworkLegacyUxLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180008fef  mov     rcx, [rdi+110h]
0x180008ff6  lea     r8, [rsp+58h+arg_0]
0x180008ffb  mov     edx, esi
0x180008ffd  call    ?SetStopResult@?$ActivityData@VAdvancedSettingsLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VAdvancedSettingsLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA_NJPEAJ@Z; wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<AdvancedSettingsLogging,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(long,long *)
0x180009002  lea     rcx, [rsp+58h+arg_10]
0x180009007  mov     bl, al
0x180009009  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000900e  test    bl, bl
0x180009010  jz      short loc_180009023
0x180009012  mov     rax, [rdi]
0x180009015  mov     rcx, rdi
0x180009018  mov     rax, [rax+8]
0x18000901c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009021  jmp     short loc_180009097
0x180009023  call    ?Provider@AdvancedSettingsLogging@@SAPEBU_tlgProvider_t@@XZ; AdvancedSettingsLogging::Provider(void)
0x180009028  mov     rbx, rax
0x18000902b  mov     ecx, [rax]
0x18000902d  cmp     ecx, 5
0x180009030  jbe     short loc_180009097
0x180009032  mov     rdx, 200000000000h
0x18000903c  mov     rcx, rax
0x18000903f  call    _tlgKeywordOn
0x180009044  test    al, al
0x180009046  jz      short loc_180009097
0x180009048  call    cs:__imp_GetCurrentThreadId
0x18000904e  mov     r8, [rdi+110h]
0x180009055  lea     rdx, byte_180020F77
0x18000905c  mov     [rsp+58h+arg_0], eax
0x180009060  add     r8, 8
0x180009064  lea     rax, [rsp+58h+arg_0]
0x180009069  mov     [rsp+58h+arg_10], esi
0x18000906d  mov     [rsp+58h+var_28], rax
0x180009072  mov     rcx, rbx
0x180009075  lea     rax, [rsp+58h+arg_10]
0x18000907a  mov     [rsp+58h+arg_18], 1000000h
0x180009083  mov     [rsp+58h+var_30], rax
0x180009088  lea     rax, [rsp+58h+arg_18]
0x18000908d  mov     [rsp+58h+var_38], rax
0x180009092  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180009097  mov     rcx, rdi
0x18000909a  add     rsp, 40h
0x18000909e  pop     rdi
0x18000909f  pop     rsi
0x1800090a0  pop     rbx
0x1800090a1  jmp     ?IgnoreCurrentThread@?$ActivityBase@VAdvancedSettingsLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<AdvancedSettingsLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
