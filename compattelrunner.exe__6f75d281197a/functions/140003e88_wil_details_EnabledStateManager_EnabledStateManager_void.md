# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x140003e88`
- end: `0x140003fe0`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `344`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400a7b50`

## callees

- `0x140003e88`
- `0x140006f2c`
- `0x1400a8010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003f65`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003f8a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003f65`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003f8a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003f73`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003f98`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003f73`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003f98`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140003edb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140003edb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003ea9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003ea9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140003eca`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140003fc0`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140003eca`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140003fc0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140003ed3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140003fc9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140003ed3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140003fc9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140003ebc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140003fb2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140003ebc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140003fb2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::EnabledStateManager::~EnabledStateManager(wil::details::EnabledStateManager *this)
{
  struct _TP_TIMER *v2; // rsi
  DWORD LastError; // ebx
  void (*v4)(void); // rax
  __int64 v5; // rdx
  void *v6; // rbx
  HANDLE ProcessHeap; // rax
  void *v8; // rbx
  HANDLE v9; // rax
  struct _TP_TIMER *v10; // rbx

  *(_DWORD *)this = 0;
  v2 = (struct _TP_TIMER *)*((_QWORD *)this + 2);
  if ( v2 )
  {
    LastError = GetLastError();
    SetThreadpoolTimer(v2, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v2, 1);
    CloseThreadpoolTimer(v2);
    SetLastError(LastError);
  }
  *((_QWORD *)this + 2) = 0;
  wil::details::EnabledStateManager::ProcessShutdown(this);
  if ( !*((_QWORD *)this + 13) )
  {
    v4 = (void (*)(void))g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
    v5 = g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
    goto LABEL_10;
  }
  v4 = (void (*)(void))g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
  if ( !g_wil_details_internalUnsubscribeFeatureStateChangeNotification )
  {
    v5 = g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
    if ( !g_wil_details_apiUnsubscribeFeatureStateChangeNotification )
      goto LABEL_10;
    v4 = (void (*)(void))g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
  }
  v4();
  v5 = g_wil_details_apiUnsubscribeFeatureStateChangeNotification;
  v4 = (void (*)(void))g_wil_details_internalUnsubscribeFeatureStateChangeNotification;
LABEL_10:
  if ( !*((_QWORD *)this + 12) )
    goto LABEL_15;
  if ( !v4 )
  {
    if ( !v5 )
      goto LABEL_15;
    v4 = (void (*)(void))v5;
  }
  v4();
LABEL_15:
  v6 = (void *)*((_QWORD *)this + 11);
  *((_QWORD *)this + 11) = 0;
  if ( v6 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v6);
  }
  v8 = (void *)*((_QWORD *)this + 7);
  *((_QWORD *)this + 7) = 0;
  if ( v8 )
  {
    v9 = GetProcessHeap();
    HeapFree(v9, 0, v8);
  }
  v10 = (struct _TP_TIMER *)*((_QWORD *)this + 2);
  if ( v10 )
  {
    SetThreadpoolTimer(*((PTP_TIMER *)this + 2), 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v10, 1);
    CloseThreadpoolTimer(v10);
  }
}

```

## disassembly

```asm
0x140003e88  mov     [rsp+arg_0], rbx
0x140003e8d  mov     [rsp+arg_8], rsi
0x140003e92  push    rdi
0x140003e93  sub     rsp, 20h
0x140003e97  mov     rdi, rcx
0x140003e9a  mov     dword ptr [rcx], 0
0x140003ea0  mov     rsi, [rcx+10h]
0x140003ea4  test    rsi, rsi
0x140003ea7  jz      short loc_140003EE1
0x140003ea9  call    cs:__imp_GetLastError
0x140003eaf  mov     ebx, eax
0x140003eb1  xor     r9d, r9d; msWindowLength
0x140003eb4  xor     r8d, r8d; msPeriod
0x140003eb7  xor     edx, edx; pftDueTime
0x140003eb9  mov     rcx, rsi; pti
0x140003ebc  call    cs:__imp_SetThreadpoolTimer
0x140003ec2  mov     edx, 1; fCancelPendingCallbacks
0x140003ec7  mov     rcx, rsi; pti
0x140003eca  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140003ed0  mov     rcx, rsi; pti
0x140003ed3  call    cs:__imp_CloseThreadpoolTimer
0x140003ed9  mov     ecx, ebx; dwErrCode
0x140003edb  call    cs:__imp_SetLastError
0x140003ee1  mov     qword ptr [rdi+10h], 0
0x140003ee9  mov     rcx, rdi; this
0x140003eec  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x140003ef1  mov     rcx, [rdi+68h]
0x140003ef5  test    rcx, rcx
0x140003ef8  jz      short loc_140003F2A
0x140003efa  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x140003f01  test    rax, rax
0x140003f04  jnz     short loc_140003F15
0x140003f06  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x140003f0d  test    rdx, rdx
0x140003f10  jz      short loc_140003F28
0x140003f12  mov     rax, rdx
0x140003f15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003f1a  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x140003f21  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x140003f28  jmp     short loc_140003F38
0x140003f2a  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x140003f31  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x140003f38  mov     rcx, [rdi+60h]
0x140003f3c  test    rcx, rcx
0x140003f3f  jz      short loc_140003F54
0x140003f41  test    rax, rax
0x140003f44  jnz     short loc_140003F4E
0x140003f46  test    rdx, rdx
0x140003f49  jz      short loc_140003F54
0x140003f4b  mov     rax, rdx
0x140003f4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003f53  nop
0x140003f54  mov     rbx, [rdi+58h]
0x140003f58  mov     qword ptr [rdi+58h], 0
0x140003f60  test    rbx, rbx
0x140003f63  jz      short loc_140003F79
0x140003f65  call    cs:__imp_GetProcessHeap
0x140003f6b  mov     rcx, rax; hHeap
0x140003f6e  mov     r8, rbx; lpMem
0x140003f71  xor     edx, edx; dwFlags
0x140003f73  call    cs:__imp_HeapFree
0x140003f79  mov     rbx, [rdi+38h]
0x140003f7d  mov     qword ptr [rdi+38h], 0
0x140003f85  test    rbx, rbx
0x140003f88  jz      short loc_140003F9E
0x140003f8a  call    cs:__imp_GetProcessHeap
0x140003f90  mov     rcx, rax; hHeap
0x140003f93  mov     r8, rbx; lpMem
0x140003f96  xor     edx, edx; dwFlags
0x140003f98  call    cs:__imp_HeapFree
0x140003f9e  mov     rbx, [rdi+10h]
0x140003fa2  test    rbx, rbx
0x140003fa5  jz      short loc_140003FD0
0x140003fa7  xor     r9d, r9d; msWindowLength
0x140003faa  xor     r8d, r8d; msPeriod
0x140003fad  xor     edx, edx; pftDueTime
0x140003faf  mov     rcx, rbx; pti
0x140003fb2  call    cs:__imp_SetThreadpoolTimer
0x140003fb8  mov     edx, 1; fCancelPendingCallbacks
0x140003fbd  mov     rcx, rbx; pti
0x140003fc0  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140003fc6  mov     rcx, rbx; pti
0x140003fc9  call    cs:__imp_CloseThreadpoolTimer
0x140003fcf  nop
0x140003fd0  mov     rbx, [rsp+28h+arg_0]
0x140003fd5  mov     rsi, [rsp+28h+arg_8]
0x140003fda  add     rsp, 20h
0x140003fde  pop     rdi
0x140003fdf  retn
```
