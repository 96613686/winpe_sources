# wil::details::EnabledStateManager::~EnabledStateManager(void)

- ea: `0x180008e80`
- end: `0x180008fd8`
- name: `??1EnabledStateManager@details@wil@@QEAA@XZ`
- size: `344`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18002fc50`

## callees

- `0x180008e80`
- `0x18000ac40`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008f6b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008f90`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008f6b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008f90`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008f5d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008f82`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008f5d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180008f82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008ea1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008ea1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008ed3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008ed3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180008ec2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180008fb8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180008ec2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180008fb8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008ecb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008fc1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008ecb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008fc1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008eb4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008faa`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008eb4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008faa`

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
0x180008e80  mov     [rsp+arg_0], rbx
0x180008e85  mov     [rsp+arg_8], rsi
0x180008e8a  push    rdi
0x180008e8b  sub     rsp, 20h
0x180008e8f  mov     rdi, rcx
0x180008e92  mov     dword ptr [rcx], 0
0x180008e98  mov     rsi, [rcx+10h]
0x180008e9c  test    rsi, rsi
0x180008e9f  jz      short loc_180008ED9
0x180008ea1  call    cs:__imp_GetLastError
0x180008ea7  mov     ebx, eax
0x180008ea9  xor     r9d, r9d; msWindowLength
0x180008eac  xor     r8d, r8d; msPeriod
0x180008eaf  xor     edx, edx; pftDueTime
0x180008eb1  mov     rcx, rsi; pti
0x180008eb4  call    cs:__imp_SetThreadpoolTimer
0x180008eba  mov     edx, 1; fCancelPendingCallbacks
0x180008ebf  mov     rcx, rsi; pti
0x180008ec2  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180008ec8  mov     rcx, rsi; pti
0x180008ecb  call    cs:__imp_CloseThreadpoolTimer
0x180008ed1  mov     ecx, ebx; dwErrCode
0x180008ed3  call    cs:__imp_SetLastError
0x180008ed9  mov     qword ptr [rdi+10h], 0
0x180008ee1  mov     rcx, rdi; this
0x180008ee4  call    ?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ; wil::details::EnabledStateManager::ProcessShutdown(void)
0x180008ee9  mov     rcx, [rdi+68h]
0x180008eed  test    rcx, rcx
0x180008ef0  jz      short loc_180008F22
0x180008ef2  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180008ef9  test    rax, rax
0x180008efc  jnz     short loc_180008F0D
0x180008efe  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180008f05  test    rdx, rdx
0x180008f08  jz      short loc_180008F20
0x180008f0a  mov     rax, rdx
0x180008f0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f12  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180008f19  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180008f20  jmp     short loc_180008F30
0x180008f22  mov     rax, cs:g_wil_details_internalUnsubscribeFeatureStateChangeNotification
0x180008f29  mov     rdx, cs:g_wil_details_apiUnsubscribeFeatureStateChangeNotification
0x180008f30  mov     rcx, [rdi+60h]
0x180008f34  test    rcx, rcx
0x180008f37  jz      short loc_180008F4C
0x180008f39  test    rax, rax
0x180008f3c  jnz     short loc_180008F46
0x180008f3e  test    rdx, rdx
0x180008f41  jz      short loc_180008F4C
0x180008f43  mov     rax, rdx
0x180008f46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f4b  nop
0x180008f4c  mov     rbx, [rdi+58h]
0x180008f50  mov     qword ptr [rdi+58h], 0
0x180008f58  test    rbx, rbx
0x180008f5b  jz      short loc_180008F71
0x180008f5d  call    cs:__imp_GetProcessHeap
0x180008f63  mov     rcx, rax; hHeap
0x180008f66  mov     r8, rbx; lpMem
0x180008f69  xor     edx, edx; dwFlags
0x180008f6b  call    cs:__imp_HeapFree
0x180008f71  mov     rbx, [rdi+38h]
0x180008f75  mov     qword ptr [rdi+38h], 0
0x180008f7d  test    rbx, rbx
0x180008f80  jz      short loc_180008F96
0x180008f82  call    cs:__imp_GetProcessHeap
0x180008f88  mov     rcx, rax; hHeap
0x180008f8b  mov     r8, rbx; lpMem
0x180008f8e  xor     edx, edx; dwFlags
0x180008f90  call    cs:__imp_HeapFree
0x180008f96  mov     rbx, [rdi+10h]
0x180008f9a  test    rbx, rbx
0x180008f9d  jz      short loc_180008FC8
0x180008f9f  xor     r9d, r9d; msWindowLength
0x180008fa2  xor     r8d, r8d; msPeriod
0x180008fa5  xor     edx, edx; pftDueTime
0x180008fa7  mov     rcx, rbx; pti
0x180008faa  call    cs:__imp_SetThreadpoolTimer
0x180008fb0  mov     edx, 1; fCancelPendingCallbacks
0x180008fb5  mov     rcx, rbx; pti
0x180008fb8  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180008fbe  mov     rcx, rbx; pti
0x180008fc1  call    cs:__imp_CloseThreadpoolTimer
0x180008fc7  nop
0x180008fc8  mov     rbx, [rsp+28h+arg_0]
0x180008fcd  mov     rsi, [rsp+28h+arg_8]
0x180008fd2  add     rsp, 20h
0x180008fd6  pop     rdi
0x180008fd7  retn
```
