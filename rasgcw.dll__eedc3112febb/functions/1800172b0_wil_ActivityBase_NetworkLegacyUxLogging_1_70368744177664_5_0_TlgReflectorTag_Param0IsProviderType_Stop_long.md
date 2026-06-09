# wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x1800172b0`
- end: `0x180017390`
- name: `?Stop@?$ActivityBase@VNetworkLegacyUxLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `224`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180016410`

## callees

- `0x180001374`
- `0x180001b0c`
- `0x180014754`
- `0x180015a00`
- `0x180015a38`
- `0x1800166d4`
- `0x1800170ac`
- `0x1800172b0`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001732b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001732b`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
        _QWORD *a1)
{
  char v2; // bl
  const struct _tlgProvider_t *v3; // rax
  __int64 v4; // r8
  __int64 v5; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v7; // r8
  __int64 v8; // r9
  int v10; // [rsp+50h] [rbp+8h] BYREF
  DWORD v11; // [rsp+58h] [rbp+10h] BYREF
  __int64 v12; // [rsp+60h] [rbp+18h] BYREF

  v11 = 0;
  wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &v10);
  v2 = wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<NetworkLegacyUxLogging,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
         a1[34],
         0,
         &v11);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v10);
  if ( v2 )
  {
    (*(void (__fastcall **)(_QWORD *))(*a1 + 8LL))(a1);
  }
  else
  {
    v3 = NetworkLegacyUxLogging::Provider();
    v5 = (__int64)v3;
    if ( *(_DWORD *)v3 > 5u && (unsigned __int8)tlgKeywordOn(v3, 0x400000000000LL, v4) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v7 = a1[34];
      v11 = CurrentThreadId;
      v10 = 0;
      v12 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v5,
        (__int64)&unk_180043190,
        v7 + 8,
        v8,
        (__int64)&v12,
        (__int64)&v10,
        (__int64)&v11);
    }
  }
  return wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(a1);
}

```

## disassembly

```asm
0x1800172b0  mov     rax, rsp
0x1800172b3  mov     [rax+20h], rbx
0x1800172b7  mov     [rax+10h], edx
0x1800172ba  push    rdi
0x1800172bb  sub     rsp, 40h
0x1800172bf  lea     rdx, [rax+8]
0x1800172c3  mov     dword ptr [rax+10h], 0
0x1800172ca  mov     rdi, rcx
0x1800172cd  call    ?LockExclusive@?$ActivityBase@VNetworkLegacyUxLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800172d2  mov     rcx, [rdi+110h]
0x1800172d9  lea     r8, [rsp+48h+arg_8]
0x1800172de  xor     edx, edx
0x1800172e0  call    ?SetStopResult@?$ActivityData@VNetworkLegacyUxLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VNetworkLegacyUxLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA_NJPEAJ@Z; wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<NetworkLegacyUxLogging,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(long,long *)
0x1800172e5  lea     rcx, [rsp+48h+arg_0]
0x1800172ea  mov     bl, al
0x1800172ec  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800172f1  test    bl, bl
0x1800172f3  jz      short loc_180017306
0x1800172f5  mov     rax, [rdi]
0x1800172f8  mov     rcx, rdi
0x1800172fb  mov     rax, [rax+8]
0x1800172ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017304  jmp     short loc_18001737E
0x180017306  call    ?Provider@NetworkLegacyUxLogging@@SAPEBU_tlgProvider_t@@XZ; NetworkLegacyUxLogging::Provider(void)
0x18001730b  mov     rbx, rax
0x18001730e  mov     ecx, [rax]
0x180017310  cmp     ecx, 5
0x180017313  jbe     short loc_18001737E
0x180017315  mov     rdx, 400000000000h
0x18001731f  mov     rcx, rax
0x180017322  call    _tlgKeywordOn
0x180017327  test    al, al
0x180017329  jz      short loc_18001737E
0x18001732b  call    cs:__imp_GetCurrentThreadId
0x180017331  mov     r8, [rdi+110h]
0x180017338  lea     rdx, unk_180043190
0x18001733f  mov     [rsp+48h+arg_8], eax
0x180017343  add     r8, 8
0x180017347  lea     rax, [rsp+48h+arg_8]
0x18001734c  mov     [rsp+48h+arg_0], 0
0x180017354  mov     [rsp+48h+var_18], rax
0x180017359  mov     rcx, rbx
0x18001735c  lea     rax, [rsp+48h+arg_0]
0x180017361  mov     [rsp+48h+arg_10], 1000000h
0x18001736a  mov     [rsp+48h+var_20], rax
0x18001736f  lea     rax, [rsp+48h+arg_10]
0x180017374  mov     [rsp+48h+var_28], rax
0x180017379  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001737e  mov     rcx, rdi
0x180017381  mov     rbx, [rsp+48h+arg_18]
0x180017386  add     rsp, 40h
0x18001738a  pop     rdi
0x18001738b  jmp     ?IgnoreCurrentThread@?$ActivityBase@VNetworkLegacyUxLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<NetworkLegacyUxLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
