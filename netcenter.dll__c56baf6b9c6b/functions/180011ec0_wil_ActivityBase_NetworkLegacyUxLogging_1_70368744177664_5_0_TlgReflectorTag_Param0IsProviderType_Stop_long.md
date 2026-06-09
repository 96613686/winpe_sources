# wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x180011ec0`
- end: `0x180011fa0`
- name: `?Stop@?$ActivityBase@VNetworkLegacyUxLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `224`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18000bd00`

## callees

- `0x1800012cc`
- `0x180001a5c`
- `0x18000815c`
- `0x18000bcd8`
- `0x18000c940`
- `0x18000f7b0`
- `0x180011770`
- `0x180011ec0`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011f3b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011f3b`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
        _QWORD *a1)
{
  char v2; // bl
  __int64 v3; // rdx
  __int64 v4; // r8
  __int64 v5; // r9
  const struct _tlgProvider_t *v6; // rax
  int v7; // ebx
  DWORD CurrentThreadId; // eax
  __int64 v9; // r8
  int v10; // r9d
  int v12; // [rsp+50h] [rbp+8h] BYREF
  DWORD v13; // [rsp+58h] [rbp+10h] BYREF
  __int64 v14; // [rsp+60h] [rbp+18h] BYREF

  v13 = 0;
  wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &v12);
  v2 = wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<NetworkLegacyUxLogging,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
         a1[34],
         0,
         &v13);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v12);
  if ( v2 )
  {
    (*(void (__fastcall **)(_QWORD *))(*a1 + 8LL))(a1);
  }
  else
  {
    v6 = NetworkLegacyUxLogging::Provider();
    v7 = (int)v6;
    if ( *(_DWORD *)v6 > 5u && (unsigned __int8)tlgKeywordOn(v6, 0x400000000000LL) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v9 = a1[34];
      v13 = CurrentThreadId;
      v12 = 0;
      v14 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v7,
        (unsigned int)&unk_18002A389,
        v9 + 8,
        v10,
        (__int64)&v14,
        (__int64)&v12,
        (__int64)&v13);
    }
  }
  return wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
           a1,
           v3,
           v4,
           v5);
}

```

## disassembly

```asm
0x180011ec0  mov     rax, rsp
0x180011ec3  mov     [rax+20h], rbx
0x180011ec7  mov     [rax+10h], edx
0x180011eca  push    rdi
0x180011ecb  sub     rsp, 40h
0x180011ecf  lea     rdx, [rax+8]
0x180011ed3  mov     dword ptr [rax+10h], 0
0x180011eda  mov     rdi, rcx
0x180011edd  call    ?LockExclusive@?$ActivityBase@VNetworkLegacyUxLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180011ee2  mov     rcx, [rdi+110h]
0x180011ee9  lea     r8, [rsp+48h+arg_8]
0x180011eee  xor     edx, edx
0x180011ef0  call    ?SetStopResult@?$ActivityData@VNetworkLegacyUxLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VNetworkLegacyUxLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA_NJPEAJ@Z; wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<NetworkLegacyUxLogging,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(long,long *)
0x180011ef5  lea     rcx, [rsp+48h+arg_0]
0x180011efa  mov     bl, al
0x180011efc  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180011f01  test    bl, bl
0x180011f03  jz      short loc_180011F16
0x180011f05  mov     rax, [rdi]
0x180011f08  mov     rcx, rdi
0x180011f0b  mov     rax, [rax+8]
0x180011f0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011f14  jmp     short loc_180011F8E
0x180011f16  call    ?Provider@NetworkLegacyUxLogging@@SAPEBU_tlgProvider_t@@XZ; NetworkLegacyUxLogging::Provider(void)
0x180011f1b  mov     rbx, rax
0x180011f1e  mov     ecx, [rax]
0x180011f20  cmp     ecx, 5
0x180011f23  jbe     short loc_180011F8E
0x180011f25  mov     rdx, 400000000000h
0x180011f2f  mov     rcx, rax
0x180011f32  call    _tlgKeywordOn
0x180011f37  test    al, al
0x180011f39  jz      short loc_180011F8E
0x180011f3b  call    cs:__imp_GetCurrentThreadId
0x180011f41  mov     r8, [rdi+110h]
0x180011f48  lea     rdx, unk_18002A389
0x180011f4f  mov     [rsp+48h+arg_8], eax
0x180011f53  add     r8, 8
0x180011f57  lea     rax, [rsp+48h+arg_8]
0x180011f5c  mov     [rsp+48h+arg_0], 0
0x180011f64  mov     [rsp+48h+var_18], rax
0x180011f69  mov     rcx, rbx
0x180011f6c  lea     rax, [rsp+48h+arg_0]
0x180011f71  mov     [rsp+48h+arg_10], 1000000h
0x180011f7a  mov     [rsp+48h+var_20], rax
0x180011f7f  lea     rax, [rsp+48h+arg_10]
0x180011f84  mov     [rsp+48h+var_28], rax
0x180011f89  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180011f8e  mov     rcx, rdi
0x180011f91  mov     rbx, [rsp+48h+arg_18]
0x180011f96  add     rsp, 40h
0x180011f9a  pop     rdi
0x180011f9b  jmp     ?IgnoreCurrentThread@?$ActivityBase@VNetworkLegacyUxLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
