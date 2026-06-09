# wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x14000b5fc`
- end: `0x14000b6dc`
- name: `?Stop@?$ActivityBase@VDirectXDatabaseUpdaterLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `224`
- prototype: `void __fastcall(__int64 *)`
- caller_count: `3`
- callee_count: `9`
- tags: `registry_config, installer_update`

## callers

- `0x140007ad8`
- `0x14000b0cc`
- `0x14000f2a4`

## callees

- `0x1400018ec`
- `0x1400022ec`
- `0x140005e18`
- `0x1400082c0`
- `0x140008578`
- `0x14000946c`
- `0x14000aaec`
- `0x14000b5fc`
- `0x14001a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000b677`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000b677`

## pseudocode

```c
void __fastcall wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(
        __int64 *a1)
{
  bool v2; // bl
  __int64 v3; // rcx
  const struct _tlgProvider_t *v4; // rax
  __int64 v5; // r8
  __int64 v6; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v8; // r8
  __int64 v9; // r9
  RTL_SRWLOCK *v10; // [rsp+50h] [rbp+8h] BYREF
  DWORD v11; // [rsp+58h] [rbp+10h] BYREF
  __int64 v12; // [rsp+60h] [rbp+18h] BYREF

  v11 = 0;
  wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    (__int64)a1,
    &v10);
  v2 = wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DirectXDatabaseUpdaterLogging,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
         a1[34],
         0,
         &v11);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v10);
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64 *))(*a1 + 8))(a1);
  }
  else
  {
    v4 = DirectXDatabaseUpdaterLogging::Provider(v3);
    v6 = (__int64)v4;
    if ( *(_DWORD *)v4 > 5u && (unsigned __int8)tlgKeywordOn(v4, 0x400000000000LL, v5) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v8 = a1[34];
      v11 = CurrentThreadId;
      LODWORD(v10) = 0;
      v12 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v6,
        (__int64)word_14001E9CA,
        v8 + 8,
        v9,
        (__int64)&v12,
        (__int64)&v10,
        (__int64)&v11);
    }
  }
  wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)a1);
}

```

## disassembly

```asm
0x14000b5fc  mov     rax, rsp
0x14000b5ff  mov     [rax+20h], rbx
0x14000b603  mov     [rax+10h], edx
0x14000b606  push    rdi
0x14000b607  sub     rsp, 40h
0x14000b60b  lea     rdx, [rax+8]
0x14000b60f  mov     dword ptr [rax+10h], 0
0x14000b616  mov     rdi, rcx
0x14000b619  call    ?LockExclusive@?$ActivityBase@VDirectXDatabaseUpdaterLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x14000b61e  mov     rcx, [rdi+110h]
0x14000b625  lea     r8, [rsp+48h+arg_8]
0x14000b62a  xor     edx, edx
0x14000b62c  call    ?SetStopResult@?$ActivityData@VDirectXDatabaseUpdaterLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VDirectXDatabaseUpdaterLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA_NJPEAJ@Z; wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityData<DirectXDatabaseUpdaterLogging,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(long,long *)
0x14000b631  lea     rcx, [rsp+48h+arg_0]
0x14000b636  mov     bl, al
0x14000b638  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x14000b63d  test    bl, bl
0x14000b63f  jz      short loc_14000B652
0x14000b641  mov     rax, [rdi]
0x14000b644  mov     rcx, rdi
0x14000b647  mov     rax, [rax+8]
0x14000b64b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b650  jmp     short loc_14000B6CA
0x14000b652  call    ?Provider@DirectXDatabaseUpdaterLogging@@SAPEBU_tlgProvider_t@@XZ; DirectXDatabaseUpdaterLogging::Provider(void)
0x14000b657  mov     rbx, rax
0x14000b65a  mov     ecx, [rax]
0x14000b65c  cmp     ecx, 5
0x14000b65f  jbe     short loc_14000B6CA
0x14000b661  mov     rdx, 400000000000h
0x14000b66b  mov     rcx, rax
0x14000b66e  call    _tlgKeywordOn
0x14000b673  test    al, al
0x14000b675  jz      short loc_14000B6CA
0x14000b677  call    cs:__imp_GetCurrentThreadId
0x14000b67d  mov     r8, [rdi+110h]
0x14000b684  lea     rdx, word_14001E9CA
0x14000b68b  mov     [rsp+48h+arg_8], eax
0x14000b68f  add     r8, 8
0x14000b693  lea     rax, [rsp+48h+arg_8]
0x14000b698  mov     dword ptr [rsp+48h+arg_0], 0
0x14000b6a0  mov     [rsp+48h+var_18], rax
0x14000b6a5  mov     rcx, rbx
0x14000b6a8  lea     rax, [rsp+48h+arg_0]
0x14000b6ad  mov     [rsp+48h+arg_10], 1000000h
0x14000b6b6  mov     [rsp+48h+var_20], rax
0x14000b6bb  lea     rax, [rsp+48h+arg_10]
0x14000b6c0  mov     [rsp+48h+var_28], rax
0x14000b6c5  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14000b6ca  mov     rcx, rdi
0x14000b6cd  mov     rbx, [rsp+48h+arg_18]
0x14000b6d2  add     rsp, 40h
0x14000b6d6  pop     rdi
0x14000b6d7  jmp     ?IgnoreCurrentThread@?$ActivityBase@VDirectXDatabaseUpdaterLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
