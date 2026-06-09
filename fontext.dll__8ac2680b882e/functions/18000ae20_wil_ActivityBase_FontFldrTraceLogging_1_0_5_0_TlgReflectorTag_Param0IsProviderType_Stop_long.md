# wil::ActivityBase<FontFldrTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x18000ae20`
- end: `0x18000aedd`
- name: `?Stop@?$ActivityBase@VFontFldrTraceLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `189`
- prototype: ``
- caller_count: `19`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000912c`
- `0x18000982c`
- `0x180009eb8`
- `0x18000dab0`
- `0x18000db98`
- `0x18000de28`
- `0x18000e144`
- `0x18000e374`
- `0x18000e704`
- `0x18000e920`
- `0x18000ed04`
- `0x18000ee64`
- `0x18000f074`
- `0x18000f198`
- `0x18000f548`
- `0x18000f6b8`
- `0x18000fc40`
- `0x180010024`
- `0x180016bd0`

## callees

- `0x180001698`
- `0x180008c84`
- `0x180009328`
- `0x18000935c`
- `0x180009930`
- `0x18000998c`
- `0x18000a254`
- `0x18000ae20`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ae7f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ae7f`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<FontFldrTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
        __int64 a1,
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
  wil::ActivityBase<FontFldrTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &v15);
  v4 = wil::ActivityBase<FontFldrTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<FontFldrTraceLogging,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
         *(_QWORD *)(a1 + 272),
         a2,
         &v14);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v15);
  if ( v4 )
  {
    wil::ActivityBase<FontFldrTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(a1, v14);
  }
  else
  {
    v8 = FontFldrTraceLogging::Provider();
    v9 = (int)v8;
    if ( *(_DWORD *)v8 > 5u )
    {
      CurrentThreadId = GetCurrentThreadId();
      v11 = *(_QWORD *)(a1 + 272);
      v14 = CurrentThreadId;
      v15 = a2;
      v16 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v9,
        (unsigned int)&byte_18003AA17,
        v11 + 8,
        v12,
        (__int64)&v16,
        (__int64)&v15,
        (__int64)&v14);
    }
  }
  return wil::ActivityBase<FontFldrTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
           a1,
           v5,
           v6,
           v7);
}

```

## disassembly

```asm
0x18000ae20  push    rbx
0x18000ae22  push    rsi
0x18000ae23  push    rdi
0x18000ae24  sub     rsp, 40h
0x18000ae28  mov     esi, edx
0x18000ae2a  mov     [rsp+58h+arg_0], 0
0x18000ae32  lea     rdx, [rsp+58h+arg_10]
0x18000ae37  mov     rdi, rcx
0x18000ae3a  call    ?LockExclusive@?$ActivityBase@VFontFldrTraceLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<FontFldrTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000ae3f  mov     rcx, [rdi+110h]
0x18000ae46  lea     r8, [rsp+58h+arg_0]
0x18000ae4b  mov     edx, esi
0x18000ae4d  call    ?SetStopResult@?$ActivityData@VFontFldrTraceLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VFontFldrTraceLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA_NJPEAJ@Z; wil::ActivityBase<FontFldrTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<FontFldrTraceLogging,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(long,long *)
0x18000ae52  lea     rcx, [rsp+58h+arg_10]
0x18000ae57  mov     bl, al
0x18000ae59  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000ae5e  test    bl, bl
0x18000ae60  jz      short loc_18000AE70
0x18000ae62  mov     edx, [rsp+58h+arg_0]
0x18000ae66  mov     rcx, rdi
0x18000ae69  call    ?ReportStopActivity@?$ActivityBase@VFontFldrTraceLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAAXJ@Z; wil::ActivityBase<FontFldrTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(long)
0x18000ae6e  jmp     short loc_18000AECE
0x18000ae70  call    ?Provider@FontFldrTraceLogging@@SAPEBU_tlgProvider_t@@XZ; FontFldrTraceLogging::Provider(void)
0x18000ae75  mov     rbx, rax
0x18000ae78  mov     ecx, [rax]
0x18000ae7a  cmp     ecx, 5
0x18000ae7d  jbe     short loc_18000AECE
0x18000ae7f  call    cs:__imp_GetCurrentThreadId
0x18000ae85  mov     r8, [rdi+110h]
0x18000ae8c  lea     rdx, byte_18003AA17
0x18000ae93  mov     [rsp+58h+arg_0], eax
0x18000ae97  add     r8, 8
0x18000ae9b  lea     rax, [rsp+58h+arg_0]
0x18000aea0  mov     [rsp+58h+arg_10], esi
0x18000aea4  mov     [rsp+58h+var_28], rax
0x18000aea9  mov     rcx, rbx
0x18000aeac  lea     rax, [rsp+58h+arg_10]
0x18000aeb1  mov     [rsp+58h+arg_18], 1000000h
0x18000aeba  mov     [rsp+58h+var_30], rax
0x18000aebf  lea     rax, [rsp+58h+arg_18]
0x18000aec4  mov     [rsp+58h+var_38], rax
0x18000aec9  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000aece  mov     rcx, rdi
0x18000aed1  add     rsp, 40h
0x18000aed5  pop     rdi
0x18000aed6  pop     rsi
0x18000aed7  pop     rbx
0x18000aed8  jmp     ?IgnoreCurrentThread@?$ActivityBase@VFontFldrTraceLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<FontFldrTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
