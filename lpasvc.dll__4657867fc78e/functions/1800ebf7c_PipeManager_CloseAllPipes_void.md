# PipeManager::CloseAllPipes(void *)

- ea: `0x1800ebf7c`
- end: `0x1800ec1c0`
- name: `?CloseAllPipes@PipeManager@@QEAAXPEAX@Z`
- size: `580`
- prototype: `void __fastcall(PipeManager *__hidden this, void *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x1800eb268`

## callees

- `0x180001010`
- `0x1800cf300`
- `0x1800eb8c4`
- `0x1800ebb1c`
- `0x1800ebf7c`
- `0x1800ec1c8`
- `0x1800ecc94`
- `0x1800ece54`
- `0x180101010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800ec034`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800ec139`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800ec034`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800ec139`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800ec092`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800ec0de`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800ec18c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800ec092`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800ec0de`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800ec18c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800ec0d4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800ec182`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800ec0d4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800ec182`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ebfc1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ec0a6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ec15c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ebfc1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ec0a6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800ec15c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ebfab`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ec0fb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ebfab`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800ec0fb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800ec0ef`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800ec19d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800ec0ef`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800ec19d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800ec0b9`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800ec16f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800ec0b9`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x1800ec16f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall PipeManager::CloseAllPipes(PipeManager *this, void *a2)
{
  int v4; // ecx
  int v5; // r8d
  int v6; // r9d
  HANDLE v7; // rax
  PipeManager *v8; // rcx
  __int64 **v9; // r15
  __int64 **j; // rbx
  struct _TP_WAIT *ThreadpoolWait; // rax
  PipeManager *v12; // rcx
  __int64 **v13; // r14
  __int64 **i; // rbx
  HANDLE EventW; // rax
  _BYTE v16[8]; // [rsp+30h] [rbp-58h] BYREF
  __int64 **v17; // [rsp+38h] [rbp-50h]
  const char *v18; // [rsp+A0h] [rbp+18h] BYREF
  const char *v19; // [rsp+A8h] [rbp+20h] BYREF

  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Lpasvc_Fix_OpenHandleOnStopping>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Lpasvc_Fix_OpenHandleOnStopping>::GetImpl'::`2'::impl) )
  {
    EnterCriticalSection(&PipeManager::_lockPipeManager);
    *((_QWORD *)this + 1) = a2;
    std::unordered_set<PipeManager::PipeImplementation *>::unordered_set<PipeManager::PipeImplementation *>(
      v16,
      (char *)this + 88);
    v13 = v17;
    for ( i = (__int64 **)*v17; i != v13; i = (__int64 **)*i )
      PipeManager::CloseAndReleasePipeIfOpen(v12, (struct PipeManager::PipeImplementation *)i[2]);
    EventW = CreateEventW(0, 0, 0, 0);
    *(_QWORD *)this = EventW;
    DataStructureHelpers::IsEmptyCallbackDataStructure<PipeManager::PipeImplementation *>::SetIsEmptyCallback(
      (char *)this + 64,
      PipeManager::CloseAllPipes_::_27_::_lambda_2_::_lambda_invoker_cdecl_,
      EventW);
    LeaveCriticalSection(&PipeManager::_lockPipeManager);
    ThreadpoolWait = CreateThreadpoolWait(PipeManager::OnStopEvent, this, 0);
    if ( !ThreadpoolWait )
    {
      WaitForSingleObject(*(HANDLE *)this, 0x3E8u);
      SetEvent(*((HANDLE *)this + 1));
      goto LABEL_19;
    }
LABEL_18:
    SetThreadpoolWait(ThreadpoolWait, *(HANDLE *)this, 0);
    goto LABEL_19;
  }
  EnterCriticalSection(&PipeManager::_lockPipeManager);
  if ( !*((_BYTE *)this + 156) )
  {
    *((_BYTE *)this + 156) = 1;
    *((_QWORD *)this + 1) = a2;
    v7 = CreateEventW(0, 0, 0, 0);
    *(_QWORD *)this = v7;
    DataStructureHelpers::IsEmptyCallbackDataStructure<PipeManager::PipeImplementation *>::SetIsEmptyCallback(
      (char *)this + 64,
      PipeManager::CloseAllPipes_::_27_::_lambda_2_::_lambda_invoker_cdecl_,
      v7);
    std::unordered_set<PipeManager::PipeImplementation *>::unordered_set<PipeManager::PipeImplementation *>(
      v16,
      (char *)this + 88);
    v9 = v17;
    for ( j = (__int64 **)*v17; j != v9; j = (__int64 **)*j )
      PipeManager::CloseAndReleasePipeIfOpen(v8, (struct PipeManager::PipeImplementation *)j[2]);
    if ( (**((unsigned __int8 (__fastcall ***)(char *))this + 8))((char *)this + 64) )
      SetEvent(*(HANDLE *)this);
    _InterlockedIncrement((volatile signed __int32 *)this + 38);
    LeaveCriticalSection(&PipeManager::_lockPipeManager);
    ThreadpoolWait = CreateThreadpoolWait(PipeManager::OnStopEvent, this, 0);
    if ( !ThreadpoolWait )
    {
      PipeManager::Release(this);
      WaitForSingleObject(*(HANDLE *)this, 0x3E8u);
      SetEvent(*((HANDLE *)this + 1));
LABEL_19:
      std::_Hash<std::_Uset_traits<PipeManager::PipeImplementation *,std::_Uhash_compare<PipeManager::PipeImplementation *,std::hash<PipeManager::PipeImplementation *>,std::equal_to<PipeManager::PipeImplementation *>>,std::allocator<PipeManager::PipeImplementation *>,0>>::~_Hash<std::_Uset_traits<PipeManager::PipeImplementation *,std::_Uhash_compare<PipeManager::PipeImplementation *,std::hash<PipeManager::PipeImplementation *>,std::equal_to<PipeManager::PipeImplementation *>>,std::allocator<PipeManager::PipeImplementation *>,0>>(v16);
      return;
    }
    goto LABEL_18;
  }
  LeaveCriticalSection(&PipeManager::_lockPipeManager);
  if ( (unsigned int)CallbackContext > 3 )
  {
    v18 = "PipeManager::CloseAllPipes";
    v19 = "LuiPipeManager";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(
      v4,
      (unsigned int)&word_180134F76,
      v5,
      v6,
      (__int64)&v19,
      (__int64)&v18);
  }
}

```

## disassembly

```asm
0x1800ebf7c  mov     [rsp+arg_0], rbx
0x1800ebf81  push    rdi
0x1800ebf82  push    r14
0x1800ebf84  push    r15
0x1800ebf86  sub     rsp, 70h
0x1800ebf8a  mov     rbx, rdx
0x1800ebf8d  mov     rdi, rcx
0x1800ebf90  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Lpasvc_Fix_OpenHandleOnStopping@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Lpasvc_Fix_OpenHandleOnStopping@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Lpasvc_Fix_OpenHandleOnStopping> `wil::Feature<__WilFeatureTraits_Feature_Lpasvc_Fix_OpenHandleOnStopping>::GetImpl(void)'::`2'::impl
0x1800ebf97  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Lpasvc_Fix_OpenHandleOnStopping@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Lpasvc_Fix_OpenHandleOnStopping>::__private_IsEnabled(void)
0x1800ebf9c  lea     rcx, ?_lockPipeManager@PipeManager@@0VBasicLock@LockHelpers@@A; lpCriticalSection
0x1800ebfa3  test    al, al
0x1800ebfa5  jz      loc_1800EC0FB
0x1800ebfab  call    cs:__imp_EnterCriticalSection
0x1800ebfb1  cmp     byte ptr [rdi+9Ch], 0
0x1800ebfb8  jz      short loc_1800EC01F
0x1800ebfba  lea     rcx, ?_lockPipeManager@PipeManager@@0VBasicLock@LockHelpers@@A; lpCriticalSection
0x1800ebfc1  call    cs:__imp_LeaveCriticalSection
0x1800ebfc7  mov     eax, cs:CallbackContext
0x1800ebfcd  cmp     eax, 3
0x1800ebfd0  jbe     loc_1800EC1AE
0x1800ebfd6  lea     rax, aPipemanagerClo; "PipeManager::CloseAllPipes"
0x1800ebfdd  mov     [rsp+88h+arg_10], rax
0x1800ebfe5  lea     rax, aLuipipemanager; "LuiPipeManager"
0x1800ebfec  mov     [rsp+88h+arg_18], rax
0x1800ebff4  lea     rax, [rsp+88h+arg_10]
0x1800ebffc  mov     [rsp+88h+var_60], rax
0x1800ec001  lea     rax, [rsp+88h+arg_18]
0x1800ec009  mov     [rsp+88h+var_68], rax
0x1800ec00e  lea     rdx, word_180134F76
0x1800ec015  call    ??$Write@U?$_tlgWrapSz@D@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800ec01a  jmp     loc_1800EC1AE
0x1800ec01f  mov     byte ptr [rdi+9Ch], 1
0x1800ec026  mov     [rdi+8], rbx
0x1800ec02a  xor     r9d, r9d; lpName
0x1800ec02d  xor     r8d, r8d; bInitialState
0x1800ec030  xor     edx, edx; bManualReset
0x1800ec032  xor     ecx, ecx; lpEventAttributes
0x1800ec034  call    cs:__imp_CreateEventW
0x1800ec03a  mov     [rdi], rax
0x1800ec03d  lea     r14, [rdi+40h]
0x1800ec041  mov     r8, rax
0x1800ec044  lea     rdx, _PipeManager__CloseAllPipes____27____lambda_2____lambda_invoker_cdecl_
0x1800ec04b  mov     rcx, r14
0x1800ec04e  call    ?SetIsEmptyCallback@?$IsEmptyCallbackDataStructure@PEAVPipeImplementation@PipeManager@@@DataStructureHelpers@@QEAAXP6AXPEAV12@PEAX@Z1@Z; DataStructureHelpers::IsEmptyCallbackDataStructure<PipeManager::PipeImplementation *>::SetIsEmptyCallback(void (*)(DataStructureHelpers::IsEmptyCallbackDataStructure<PipeManager::PipeImplementation *> *,void *),void *)
0x1800ec053  lea     rdx, [rdi+58h]
0x1800ec057  lea     rcx, [rsp+88h+var_58]
0x1800ec05c  call    ??0?$unordered_set@PEAVPipeImplementation@PipeManager@@U?$hash@PEAVPipeImplementation@PipeManager@@@std@@U?$equal_to@PEAVPipeImplementation@PipeManager@@@4@V?$allocator@PEAVPipeImplementation@PipeManager@@@4@@std@@QEAA@AEBV01@@Z; std::unordered_set<PipeManager::PipeImplementation *>::unordered_set<PipeManager::PipeImplementation *>(std::unordered_set<PipeManager::PipeImplementation *> const &)
0x1800ec061  nop
0x1800ec062  mov     r15, [rsp+88h+var_50]
0x1800ec067  mov     rbx, [r15]
0x1800ec06a  cmp     rbx, r15
0x1800ec06d  jz      short loc_1800EC07D
0x1800ec06f  mov     rdx, [rbx+10h]; struct PipeManager::PipeImplementation *
0x1800ec073  call    ?CloseAndReleasePipeIfOpen@PipeManager@@AEAAXPEAVPipeImplementation@1@@Z; PipeManager::CloseAndReleasePipeIfOpen(PipeManager::PipeImplementation *)
0x1800ec078  mov     rbx, [rbx]
0x1800ec07b  jmp     short loc_1800EC06A
0x1800ec07d  mov     rax, [r14]
0x1800ec080  mov     rcx, r14
0x1800ec083  mov     rax, [rax]
0x1800ec086  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ec08b  test    al, al
0x1800ec08d  jz      short loc_1800EC098
0x1800ec08f  mov     rcx, [rdi]; hEvent
0x1800ec092  call    cs:__imp_SetEvent
0x1800ec098  lock inc dword ptr [rdi+98h]
0x1800ec09f  lea     rcx, ?_lockPipeManager@PipeManager@@0VBasicLock@LockHelpers@@A; lpCriticalSection
0x1800ec0a6  call    cs:__imp_LeaveCriticalSection
0x1800ec0ac  xor     r8d, r8d; pcbe
0x1800ec0af  mov     rdx, rdi; pv
0x1800ec0b2  lea     rcx, ?OnStopEvent@PipeManager@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x1800ec0b9  call    cs:__imp_CreateThreadpoolWait
0x1800ec0bf  test    rax, rax
0x1800ec0c2  jnz     short loc_1800EC0E6
0x1800ec0c4  mov     rcx, rdi; this
0x1800ec0c7  call    ?Release@PipeManager@@QEAAXXZ; PipeManager::Release(void)
0x1800ec0cc  mov     edx, 3E8h; dwMilliseconds
0x1800ec0d1  mov     rcx, [rdi]; hHandle
0x1800ec0d4  call    cs:__imp_WaitForSingleObject
0x1800ec0da  mov     rcx, [rdi+8]; hEvent
0x1800ec0de  call    cs:__imp_SetEvent
0x1800ec0e4  jmp     short loc_1800EC0F6
0x1800ec0e6  xor     r8d, r8d; pftTimeout
0x1800ec0e9  mov     rdx, [rdi]; h
0x1800ec0ec  mov     rcx, rax; pwa
0x1800ec0ef  call    cs:__imp_SetThreadpoolWait
0x1800ec0f5  nop
0x1800ec0f6  jmp     loc_1800EC1A4
0x1800ec0fb  call    cs:__imp_EnterCriticalSection
0x1800ec101  mov     [rdi+8], rbx
0x1800ec105  lea     rdx, [rdi+58h]
0x1800ec109  lea     rcx, [rsp+88h+var_58]
0x1800ec10e  call    ??0?$unordered_set@PEAVPipeImplementation@PipeManager@@U?$hash@PEAVPipeImplementation@PipeManager@@@std@@U?$equal_to@PEAVPipeImplementation@PipeManager@@@4@V?$allocator@PEAVPipeImplementation@PipeManager@@@4@@std@@QEAA@AEBV01@@Z; std::unordered_set<PipeManager::PipeImplementation *>::unordered_set<PipeManager::PipeImplementation *>(std::unordered_set<PipeManager::PipeImplementation *> const &)
0x1800ec113  nop
0x1800ec114  mov     r14, [rsp+88h+var_50]
0x1800ec119  mov     rbx, [r14]
0x1800ec11c  cmp     rbx, r14
0x1800ec11f  jz      short loc_1800EC12F
0x1800ec121  mov     rdx, [rbx+10h]; struct PipeManager::PipeImplementation *
0x1800ec125  call    ?CloseAndReleasePipeIfOpen@PipeManager@@AEAAXPEAVPipeImplementation@1@@Z; PipeManager::CloseAndReleasePipeIfOpen(PipeManager::PipeImplementation *)
0x1800ec12a  mov     rbx, [rbx]
0x1800ec12d  jmp     short loc_1800EC11C
0x1800ec12f  xor     r9d, r9d; lpName
0x1800ec132  xor     r8d, r8d; bInitialState
0x1800ec135  xor     edx, edx; bManualReset
0x1800ec137  xor     ecx, ecx; lpEventAttributes
0x1800ec139  call    cs:__imp_CreateEventW
0x1800ec13f  mov     [rdi], rax
0x1800ec142  lea     rcx, [rdi+40h]
0x1800ec146  mov     r8, rax
0x1800ec149  lea     rdx, _PipeManager__CloseAllPipes____27____lambda_2____lambda_invoker_cdecl_
0x1800ec150  call    ?SetIsEmptyCallback@?$IsEmptyCallbackDataStructure@PEAVPipeImplementation@PipeManager@@@DataStructureHelpers@@QEAAXP6AXPEAV12@PEAX@Z1@Z; DataStructureHelpers::IsEmptyCallbackDataStructure<PipeManager::PipeImplementation *>::SetIsEmptyCallback(void (*)(DataStructureHelpers::IsEmptyCallbackDataStructure<PipeManager::PipeImplementation *> *,void *),void *)
0x1800ec155  lea     rcx, ?_lockPipeManager@PipeManager@@0VBasicLock@LockHelpers@@A; lpCriticalSection
0x1800ec15c  call    cs:__imp_LeaveCriticalSection
0x1800ec162  xor     r8d, r8d; pcbe
0x1800ec165  mov     rdx, rdi; pv
0x1800ec168  lea     rcx, ?OnStopEvent@PipeManager@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x1800ec16f  call    cs:__imp_CreateThreadpoolWait
0x1800ec175  test    rax, rax
0x1800ec178  jnz     short loc_1800EC194
0x1800ec17a  mov     edx, 3E8h; dwMilliseconds
0x1800ec17f  mov     rcx, [rdi]; hHandle
0x1800ec182  call    cs:__imp_WaitForSingleObject
0x1800ec188  mov     rcx, [rdi+8]; hEvent
0x1800ec18c  call    cs:__imp_SetEvent
0x1800ec192  jmp     short loc_1800EC1A4
0x1800ec194  xor     r8d, r8d; pftTimeout
0x1800ec197  mov     rdx, [rdi]; h
0x1800ec19a  mov     rcx, rax; pwa
0x1800ec19d  call    cs:__imp_SetThreadpoolWait
0x1800ec1a3  nop
0x1800ec1a4  lea     rcx, [rsp+88h+var_58]
0x1800ec1a9  call    ??1?$_Hash@V?$_Uset_traits@PEAVPipeImplementation@PipeManager@@V?$_Uhash_compare@PEAVPipeImplementation@PipeManager@@U?$hash@PEAVPipeImplementation@PipeManager@@@std@@U?$equal_to@PEAVPipeImplementation@PipeManager@@@4@@std@@V?$allocator@PEAVPipeImplementation@PipeManager@@@4@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Uset_traits<PipeManager::PipeImplementation *,std::_Uhash_compare<PipeManager::PipeImplementation *,std::hash<PipeManager::PipeImplementation *>,std::equal_to<PipeManager::PipeImplementation *>>,std::allocator<PipeManager::PipeImplementation *>,0>>::~_Hash<std::_Uset_traits<PipeManager::PipeImplementation *,std::_Uhash_compare<PipeManager::PipeImplementation *,std::hash<PipeManager::PipeImplementation *>,std::equal_to<PipeManager::PipeImplementation *>>,std::allocator<PipeManager::PipeImplementation *>,0>>(void)
0x1800ec1ae  mov     rbx, [rsp+88h+arg_0]
0x1800ec1b6  add     rsp, 70h
0x1800ec1ba  pop     r15
0x1800ec1bc  pop     r14
0x1800ec1be  pop     rdi
0x1800ec1bf  retn
```
