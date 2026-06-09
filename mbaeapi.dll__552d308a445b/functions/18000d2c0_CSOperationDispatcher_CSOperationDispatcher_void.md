# CSOperationDispatcher::~CSOperationDispatcher(void)

- ea: `0x18000d2c0`
- end: `0x18000d397`
- name: `??1CSOperationDispatcher@@QEAA@XZ`
- size: `215`
- prototype: `void __fastcall(CSOperationDispatcher *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x18000d128`

## callees

- `0x18000cda4`
- `0x18000d2c0`
- `0x180013a74`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000d2e9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000d339`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000d2e9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000d339`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000d2fb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000d34b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000d2fb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000d34b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000d358`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000d358`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d32a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d32a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d309`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d309`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18000d319`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18000d377`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18000d319`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18000d377`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18000d322`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18000d380`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18000d322`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18000d380`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CSOperationDispatcher::~CSOperationDispatcher(CSOperationDispatcher *this)
{
  RTL_SRWLOCK *v2; // rbx
  struct _TP_WORK *v3; // rsi
  DWORD LastError; // ebx
  struct _TP_WORK *v5; // rbx

  v2 = (RTL_SRWLOCK *)((char *)this + 48);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_NetworkUX_BugFix_58122346>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_NetworkUX_BugFix_58122346>::GetImpl'::`2'::impl) )
  {
    AcquireSRWLockExclusive(v2);
    *((_BYTE *)this + 57) = 1;
    if ( v2 )
      ReleaseSRWLockExclusive(v2);
    v3 = *(struct _TP_WORK **)this;
    if ( *(_QWORD *)this )
    {
      LastError = GetLastError();
      WaitForThreadpoolWorkCallbacks(v3, 1);
      CloseThreadpoolWork(v3);
      SetLastError(LastError);
    }
    *(_QWORD *)this = 0;
  }
  else
  {
    AcquireSRWLockExclusive(v2);
    *((_BYTE *)this + 57) = 1;
    if ( v2 )
      ReleaseSRWLockExclusive(v2);
    WaitForSingleObject(*((HANDLE *)this + 8), 0xFFFFFFFF);
  }
  std::deque<std::shared_ptr<WaitableOperation>>::~deque<std::shared_ptr<WaitableOperation>>((char *)this + 8);
  v5 = *(struct _TP_WORK **)this;
  if ( *(_QWORD *)this )
  {
    WaitForThreadpoolWorkCallbacks(*(PTP_WORK *)this, 1);
    CloseThreadpoolWork(v5);
  }
}

```

## disassembly

```asm
0x18000d2c0  mov     [rsp+arg_0], rbx
0x18000d2c5  mov     [rsp+arg_8], rsi
0x18000d2ca  push    rdi
0x18000d2cb  sub     rsp, 20h
0x18000d2cf  mov     rdi, rcx
0x18000d2d2  lea     rbx, [rcx+30h]
0x18000d2d6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_NetworkUX_BugFix_58122346@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_NetworkUX_BugFix_58122346@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NetworkUX_BugFix_58122346> `wil::Feature<__WilFeatureTraits_Feature_NetworkUX_BugFix_58122346>::GetImpl(void)'::`2'::impl
0x18000d2dd  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_NetworkUX_BugFix_58122346@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NetworkUX_BugFix_58122346>::__private_IsEnabled(void)
0x18000d2e2  mov     rcx, rbx; SRWLock
0x18000d2e5  test    al, al
0x18000d2e7  jz      short loc_18000D339
0x18000d2e9  call    cs:__imp_AcquireSRWLockExclusive
0x18000d2ef  mov     byte ptr [rdi+39h], 1
0x18000d2f3  test    rbx, rbx
0x18000d2f6  jz      short loc_18000D301
0x18000d2f8  mov     rcx, rbx; SRWLock
0x18000d2fb  call    cs:__imp_ReleaseSRWLockExclusive
0x18000d301  mov     rsi, [rdi]
0x18000d304  test    rsi, rsi
0x18000d307  jz      short loc_18000D330
0x18000d309  call    cs:__imp_GetLastError
0x18000d30f  mov     ebx, eax
0x18000d311  mov     edx, 1; fCancelPendingCallbacks
0x18000d316  mov     rcx, rsi; pwk
0x18000d319  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18000d31f  mov     rcx, rsi; pwk
0x18000d322  call    cs:__imp_CloseThreadpoolWork
0x18000d328  mov     ecx, ebx; dwErrCode
0x18000d32a  call    cs:__imp_SetLastError
0x18000d330  mov     qword ptr [rdi], 0
0x18000d337  jmp     short loc_18000D35E
0x18000d339  call    cs:__imp_AcquireSRWLockExclusive
0x18000d33f  mov     byte ptr [rdi+39h], 1
0x18000d343  test    rbx, rbx
0x18000d346  jz      short loc_18000D351
0x18000d348  mov     rcx, rbx; SRWLock
0x18000d34b  call    cs:__imp_ReleaseSRWLockExclusive
0x18000d351  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000d354  mov     rcx, [rdi+40h]; hHandle
0x18000d358  call    cs:__imp_WaitForSingleObject
0x18000d35e  lea     rcx, [rdi+8]
0x18000d362  call    ??1?$deque@V?$shared_ptr@VWaitableOperation@@@std@@V?$allocator@V?$shared_ptr@VWaitableOperation@@@std@@@2@@std@@QEAA@XZ; std::deque<std::shared_ptr<WaitableOperation>>::~deque<std::shared_ptr<WaitableOperation>>(void)
0x18000d367  mov     rbx, [rdi]
0x18000d36a  test    rbx, rbx
0x18000d36d  jz      short loc_18000D387
0x18000d36f  mov     edx, 1; fCancelPendingCallbacks
0x18000d374  mov     rcx, rbx; pwk
0x18000d377  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18000d37d  mov     rcx, rbx; pwk
0x18000d380  call    cs:__imp_CloseThreadpoolWork
0x18000d386  nop
0x18000d387  mov     rbx, [rsp+28h+arg_0]
0x18000d38c  mov     rsi, [rsp+28h+arg_8]
0x18000d391  add     rsp, 20h
0x18000d395  pop     rdi
0x18000d396  retn
```
