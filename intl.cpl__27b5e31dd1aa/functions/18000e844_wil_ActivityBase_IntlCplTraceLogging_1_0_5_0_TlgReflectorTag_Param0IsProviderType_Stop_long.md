# wil::ActivityBase<IntlCplTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x18000e844`
- end: `0x18000e901`
- name: `?Stop@?$ActivityBase@VIntlCplTraceLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `189`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000ba98`
- `0x18000c454`
- `0x18000dce0`

## callees

- `0x180001c94`
- `0x1800093fc`
- `0x18000ac00`
- `0x18000d524`
- `0x18000d548`
- `0x18000da94`
- `0x18000e590`
- `0x18000e844`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e8a3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e8a3`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<IntlCplTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
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
    wil::ActivityBase<IntlCplTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(a1, v14);
  }
  else
  {
    v8 = IntlCplTraceLogging::Provider();
    v9 = (int)v8;
    if ( *(_DWORD *)v8 > 5u )
    {
      CurrentThreadId = GetCurrentThreadId();
      v11 = a1[34];
      v14 = CurrentThreadId;
      v15 = a2;
      v16 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v9,
        (unsigned int)&unk_1800332DC,
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
0x18000e844  push    rbx
0x18000e846  push    rsi
0x18000e847  push    rdi
0x18000e848  sub     rsp, 40h
0x18000e84c  mov     esi, edx
0x18000e84e  mov     [rsp+58h+arg_0], 0
0x18000e856  lea     rdx, [rsp+58h+arg_10]
0x18000e85b  mov     rdi, rcx
0x18000e85e  call    ?LockExclusive@?$ActivityBase@VIntlCplTraceLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<IntlCplTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000e863  mov     rcx, [rdi+110h]
0x18000e86a  lea     r8, [rsp+58h+arg_0]
0x18000e86f  mov     edx, esi
0x18000e871  call    ?SetStopResult@?$ActivityData@VIntlCplTraceLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VIntlCplTraceLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA_NJPEAJ@Z; wil::ActivityBase<IntlCplTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<IntlCplTraceLogging,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(long,long *)
0x18000e876  lea     rcx, [rsp+58h+arg_10]
0x18000e87b  mov     bl, al
0x18000e87d  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000e882  test    bl, bl
0x18000e884  jz      short loc_18000E894
0x18000e886  mov     edx, [rsp+58h+arg_0]
0x18000e88a  mov     rcx, rdi
0x18000e88d  call    ?ReportStopActivity@?$ActivityBase@VIntlCplTraceLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAAXJ@Z; wil::ActivityBase<IntlCplTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(long)
0x18000e892  jmp     short loc_18000E8F2
0x18000e894  call    ?Provider@IntlCplTraceLogging@@SAPEBU_tlgProvider_t@@XZ; IntlCplTraceLogging::Provider(void)
0x18000e899  mov     rbx, rax
0x18000e89c  mov     ecx, [rax]
0x18000e89e  cmp     ecx, 5
0x18000e8a1  jbe     short loc_18000E8F2
0x18000e8a3  call    cs:__imp_GetCurrentThreadId
0x18000e8a9  mov     r8, [rdi+110h]
0x18000e8b0  lea     rdx, unk_1800332DC
0x18000e8b7  mov     [rsp+58h+arg_0], eax
0x18000e8bb  add     r8, 8
0x18000e8bf  lea     rax, [rsp+58h+arg_0]
0x18000e8c4  mov     [rsp+58h+arg_10], esi
0x18000e8c8  mov     [rsp+58h+var_28], rax
0x18000e8cd  mov     rcx, rbx
0x18000e8d0  lea     rax, [rsp+58h+arg_10]
0x18000e8d5  mov     [rsp+58h+arg_18], 1000000h
0x18000e8de  mov     [rsp+58h+var_30], rax
0x18000e8e3  lea     rax, [rsp+58h+arg_18]
0x18000e8e8  mov     [rsp+58h+var_38], rax
0x18000e8ed  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000e8f2  mov     rcx, rdi
0x18000e8f5  add     rsp, 40h
0x18000e8f9  pop     rdi
0x18000e8fa  pop     rsi
0x18000e8fb  pop     rbx
0x18000e8fc  jmp     ?IgnoreCurrentThread@?$ActivityBase@VIntlCplTraceLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<IntlCplTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
