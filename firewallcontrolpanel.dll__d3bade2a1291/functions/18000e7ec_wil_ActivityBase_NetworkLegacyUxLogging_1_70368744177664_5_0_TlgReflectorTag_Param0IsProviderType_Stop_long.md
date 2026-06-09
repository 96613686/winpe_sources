# wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x18000e7ec`
- end: `0x18000e8c2`
- name: `?Stop@?$ActivityBase@VNetworkLegacyUxLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `214`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18000d440`
- `0x18000dd70`
- `0x180017020`
- `0x1800171c8`
- `0x180019890`
- `0x18001bc30`
- `0x18001bd90`

## callees

- `0x1800015dc`
- `0x180001b8c`
- `0x18000c2bc`
- `0x18000cc84`
- `0x18000d744`
- `0x18000dfc0`
- `0x18000e58c`
- `0x18000e7ec`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e864`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e864`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
        _QWORD *a1,
        unsigned int a2)
{
  char v4; // bl
  __int64 v5; // rdx
  __int64 v6; // r8
  __int64 v7; // r9
  const struct _tlgProvider_t *v8; // rax
  __int64 v9; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v11; // r8
  __int64 v12; // r9
  DWORD v14; // [rsp+60h] [rbp+8h] BYREF
  unsigned int v15; // [rsp+70h] [rbp+18h] BYREF
  __int64 v16; // [rsp+78h] [rbp+20h] BYREF

  v14 = 0;
  wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &v15);
  v4 = wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<NetworkLegacyUxLogging,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
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
    v8 = NetworkLegacyUxLogging::Provider();
    v9 = (__int64)v8;
    if ( *(_DWORD *)v8 > 5u && (unsigned __int8)tlgKeywordOn(v8, 0x400000000000LL, v6) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v11 = a1[34];
      v14 = CurrentThreadId;
      v15 = a2;
      v16 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v9,
        (__int64)&dword_18003909C,
        v11 + 8,
        v12,
        (__int64)&v16,
        (__int64)&v15,
        (__int64)&v14);
    }
  }
  return wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
           a1,
           v5,
           v6,
           v7);
}

```

## disassembly

```asm
0x18000e7ec  push    rbx
0x18000e7ee  push    rsi
0x18000e7ef  push    rdi
0x18000e7f0  sub     rsp, 40h
0x18000e7f4  mov     esi, edx
0x18000e7f6  mov     [rsp+58h+arg_0], 0
0x18000e7fe  lea     rdx, [rsp+58h+arg_10]
0x18000e803  mov     rdi, rcx
0x18000e806  call    ?LockExclusive@?$ActivityBase@VNetworkLegacyUxLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000e80b  mov     rcx, [rdi+110h]
0x18000e812  lea     r8, [rsp+58h+arg_0]
0x18000e817  mov     edx, esi
0x18000e819  call    ?SetStopResult@?$ActivityData@VNetworkLegacyUxLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VNetworkLegacyUxLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA_NJPEAJ@Z; wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<NetworkLegacyUxLogging,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(long,long *)
0x18000e81e  lea     rcx, [rsp+58h+arg_10]
0x18000e823  mov     bl, al
0x18000e825  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000e82a  test    bl, bl
0x18000e82c  jz      short loc_18000E83F
0x18000e82e  mov     rax, [rdi]
0x18000e831  mov     rcx, rdi
0x18000e834  mov     rax, [rax+8]
0x18000e838  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e83d  jmp     short loc_18000E8B3
0x18000e83f  call    ?Provider@NetworkLegacyUxLogging@@SAPEBU_tlgProvider_t@@XZ; NetworkLegacyUxLogging::Provider(void)
0x18000e844  mov     rbx, rax
0x18000e847  mov     ecx, [rax]
0x18000e849  cmp     ecx, 5
0x18000e84c  jbe     short loc_18000E8B3
0x18000e84e  mov     rdx, 400000000000h
0x18000e858  mov     rcx, rax
0x18000e85b  call    _tlgKeywordOn
0x18000e860  test    al, al
0x18000e862  jz      short loc_18000E8B3
0x18000e864  call    cs:__imp_GetCurrentThreadId
0x18000e86a  mov     r8, [rdi+110h]
0x18000e871  lea     rdx, dword_18003909C
0x18000e878  mov     [rsp+58h+arg_0], eax
0x18000e87c  add     r8, 8
0x18000e880  lea     rax, [rsp+58h+arg_0]
0x18000e885  mov     [rsp+58h+arg_10], esi
0x18000e889  mov     [rsp+58h+var_28], rax
0x18000e88e  mov     rcx, rbx
0x18000e891  lea     rax, [rsp+58h+arg_10]
0x18000e896  mov     [rsp+58h+arg_18], 1000000h
0x18000e89f  mov     [rsp+58h+var_30], rax
0x18000e8a4  lea     rax, [rsp+58h+arg_18]
0x18000e8a9  mov     [rsp+58h+var_38], rax
0x18000e8ae  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000e8b3  mov     rcx, rdi
0x18000e8b6  add     rsp, 40h
0x18000e8ba  pop     rdi
0x18000e8bb  pop     rsi
0x18000e8bc  pop     rbx
0x18000e8bd  jmp     ?IgnoreCurrentThread@?$ActivityBase@VNetworkLegacyUxLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
