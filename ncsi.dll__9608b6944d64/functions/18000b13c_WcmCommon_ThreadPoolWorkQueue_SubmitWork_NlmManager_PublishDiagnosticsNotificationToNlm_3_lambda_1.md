# WcmCommon::ThreadPoolWorkQueue::SubmitWork__NlmManager::PublishDiagnosticsNotificationToNlm_::_3_::_lambda_1___

- ea: `0x18000b13c`
- end: `0x18000b1cc`
- name: `WcmCommon::ThreadPoolWorkQueue::SubmitWork__NlmManager::PublishDiagnosticsNotificationToNlm_::_3_::_lambda_1___`
- size: `144`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000afdc`

## callees

- `0x18000b13c`
- `0x18006da18`
- `0x18006dabc`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000b1b6`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000b1b6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b178`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b1a1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b178`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000b1a1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b158`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000b158`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall WcmCommon::ThreadPoolWorkQueue::SubmitWork__NlmManager::PublishDiagnosticsNotificationToNlm_::_3_::_lambda_1___(
        __int64 a1,
        __int64 a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rbx

  v4 = (struct _RTL_CRITICAL_SECTION *)(a1 + 8);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  if ( *(_BYTE *)(a1 + 272) )
  {
    if ( v4 )
      LeaveCriticalSection(v4);
  }
  else
  {
    if ( *(_DWORD *)a1 == 1 )
      std::deque_std::function_void___cdecl_void___std::allocator_std::function_void___cdecl_void______::emplace_back__NlmManager::PublishDiagnosticsNotificationToNlm_::_3_::_lambda_1___(
        a1 + 152,
        a2);
    else
      std::deque_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult____std::allocator_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult_______::emplace_back__NlmManager::PublishDiagnosticsNotificationToNlm_::_3_::_lambda_1___(
        a1 + 232,
        a2);
    if ( v4 )
      LeaveCriticalSection(v4);
    _InterlockedIncrement64((volatile signed __int64 *)(a1 + 136));
    SubmitThreadpoolWork(*(PTP_WORK *)(a1 + 128));
  }
}

```

## disassembly

```asm
0x18000b13c  mov     [rsp+arg_10], rbx
0x18000b141  mov     [rsp+arg_18], rsi
0x18000b146  push    rdi
0x18000b147  sub     rsp, 30h
0x18000b14b  mov     rsi, rdx
0x18000b14e  mov     rdi, rcx
0x18000b151  lea     rbx, [rcx+8]
0x18000b155  mov     rcx, rbx; lpCriticalSection
0x18000b158  call    cs:__imp_EnterCriticalSection
0x18000b15e  mov     [rsp+38h+var_18], rbx
0x18000b163  lea     rcx, [rdi+98h]
0x18000b16a  cmp     byte ptr [rcx+78h], 0
0x18000b16e  jz      short loc_18000B180
0x18000b170  test    rbx, rbx
0x18000b173  jz      short loc_18000B1BC
0x18000b175  mov     rcx, rbx; lpCriticalSection
0x18000b178  call    cs:__imp_LeaveCriticalSection
0x18000b17e  jmp     short loc_18000B1BC
0x18000b180  mov     rdx, rsi
0x18000b183  cmp     dword ptr [rdi], 1
0x18000b186  jnz     short loc_18000B18F
0x18000b188  call    std__deque_std__function_void___cdecl_void___std__allocator_std__function_void___cdecl_void________emplace_back__NlmManager__PublishDiagnosticsNotificationToNlm____3____lambda_1___
0x18000b18d  jmp     short loc_18000B199
0x18000b18f  add     rcx, 50h ; 'P'
0x18000b193  call    std__deque_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult____std__allocator_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult_________emplace_back__NlmManager__PublishDiagnosticsNotificationToNlm____3____lambda_1___
0x18000b198  nop
0x18000b199  test    rbx, rbx
0x18000b19c  jz      short loc_18000B1A7
0x18000b19e  mov     rcx, rbx; lpCriticalSection
0x18000b1a1  call    cs:__imp_LeaveCriticalSection
0x18000b1a7  lock inc qword ptr [rdi+88h]
0x18000b1af  mov     rcx, [rdi+80h]; pwk
0x18000b1b6  call    cs:__imp_SubmitThreadpoolWork
0x18000b1bc  mov     rbx, [rsp+38h+arg_10]
0x18000b1c1  mov     rsi, [rsp+38h+arg_18]
0x18000b1c6  add     rsp, 30h
0x18000b1ca  pop     rdi
0x18000b1cb  retn
```
