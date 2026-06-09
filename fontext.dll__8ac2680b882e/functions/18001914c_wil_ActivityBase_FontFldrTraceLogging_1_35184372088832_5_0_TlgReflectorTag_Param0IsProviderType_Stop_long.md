# wil::ActivityBase<FontFldrTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x18001914c`
- end: `0x180019222`
- name: `?Stop@?$ActivityBase@VFontFldrTraceLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `214`
- prototype: ``
- caller_count: `4`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180015a90`
- `0x18002b988`
- `0x18002bda0`
- `0x18002c100`

## callees

- `0x180001698`
- `0x180001f1c`
- `0x180008c84`
- `0x180009328`
- `0x18000935c`
- `0x180009930`
- `0x18000a254`
- `0x18001914c`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800191c4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800191c4`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<FontFldrTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
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
  wil::ActivityBase<FontFldrTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &v15);
  v4 = wil::ActivityBase<FontFldrTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<FontFldrTraceLogging,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
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
    v8 = FontFldrTraceLogging::Provider();
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
        (unsigned int)&word_18003D22E,
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
0x18001914c  push    rbx
0x18001914e  push    rsi
0x18001914f  push    rdi
0x180019150  sub     rsp, 40h
0x180019154  mov     esi, edx
0x180019156  mov     [rsp+58h+arg_0], 0
0x18001915e  lea     rdx, [rsp+58h+arg_10]
0x180019163  mov     rdi, rcx
0x180019166  call    ?LockExclusive@?$ActivityBase@VFontFldrTraceLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<FontFldrTraceLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18001916b  mov     rcx, [rdi+110h]
0x180019172  lea     r8, [rsp+58h+arg_0]
0x180019177  mov     edx, esi
0x180019179  call    ?SetStopResult@?$ActivityData@VFontFldrTraceLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VFontFldrTraceLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA_NJPEAJ@Z; wil::ActivityBase<FontFldrTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<FontFldrTraceLogging,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(long,long *)
0x18001917e  lea     rcx, [rsp+58h+arg_10]
0x180019183  mov     bl, al
0x180019185  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001918a  test    bl, bl
0x18001918c  jz      short loc_18001919F
0x18001918e  mov     rax, [rdi]
0x180019191  mov     rcx, rdi
0x180019194  mov     rax, [rax+8]
0x180019198  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001919d  jmp     short loc_180019213
0x18001919f  call    ?Provider@FontFldrTraceLogging@@SAPEBU_tlgProvider_t@@XZ; FontFldrTraceLogging::Provider(void)
0x1800191a4  mov     rbx, rax
0x1800191a7  mov     ecx, [rax]
0x1800191a9  cmp     ecx, 5
0x1800191ac  jbe     short loc_180019213
0x1800191ae  mov     rdx, 200000000000h
0x1800191b8  mov     rcx, rax
0x1800191bb  call    _tlgKeywordOn
0x1800191c0  test    al, al
0x1800191c2  jz      short loc_180019213
0x1800191c4  call    cs:__imp_GetCurrentThreadId
0x1800191ca  mov     r8, [rdi+110h]
0x1800191d1  lea     rdx, word_18003D22E
0x1800191d8  mov     [rsp+58h+arg_0], eax
0x1800191dc  add     r8, 8
0x1800191e0  lea     rax, [rsp+58h+arg_0]
0x1800191e5  mov     [rsp+58h+arg_10], esi
0x1800191e9  mov     [rsp+58h+var_28], rax
0x1800191ee  mov     rcx, rbx
0x1800191f1  lea     rax, [rsp+58h+arg_10]
0x1800191f6  mov     [rsp+58h+arg_18], 1000000h
0x1800191ff  mov     [rsp+58h+var_30], rax
0x180019204  lea     rax, [rsp+58h+arg_18]
0x180019209  mov     [rsp+58h+var_38], rax
0x18001920e  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180019213  mov     rcx, rdi
0x180019216  add     rsp, 40h
0x18001921a  pop     rdi
0x18001921b  pop     rsi
0x18001921c  pop     rbx
0x18001921d  jmp     ?IgnoreCurrentThread@?$ActivityBase@VFontFldrTraceLogging@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<FontFldrTraceLogging,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
