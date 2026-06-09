# ComputeService::Vmwp::Details::ComCallTracker::~ComCallTracker(void)

- ea: `0x18004e4ec`
- end: `0x18004e59a`
- name: `??1ComCallTracker@Details@Vmwp@ComputeService@@QEAA@XZ`
- size: `174`
- prototype: `void __fastcall(ComputeService::Vmwp::Details::ComCallTracker *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18004df3c`
- `0x18009e0fd`

## callees

- `0x18004e4ec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004e538`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004e538`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e506`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e506`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18004e530`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18004e584`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18004e530`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18004e584`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18004e527`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18004e57b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18004e527`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18004e57b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18004e519`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18004e56d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18004e519`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18004e56d`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x18004e54d`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x18004e54d`

## pseudocode

```c
void __fastcall ComputeService::Vmwp::Details::ComCallTracker::~ComCallTracker(struct _TP_TIMER **this)
{
  struct _TP_TIMER *v1; // rsi
  DWORD LastError; // ebx
  struct _TP_TIMER *v4; // rbx

  v1 = *this;
  if ( *this )
  {
    LastError = GetLastError();
    SetThreadpoolTimer(v1, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v1, 1);
    CloseThreadpoolTimer(v1);
    SetLastError(LastError);
  }
  *this = 0;
  if ( *((_DWORD *)this + 2) )
  {
    CoDisableCallCancellation(0);
    *((_DWORD *)this + 2) = 0;
  }
  v4 = *this;
  if ( *this )
  {
    SetThreadpoolTimer(*this, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v4, 1);
    CloseThreadpoolTimer(v4);
  }
}

```

## disassembly

```asm
0x18004e4ec  mov     [rsp+arg_0], rbx
0x18004e4f1  mov     [rsp+arg_8], rsi
0x18004e4f6  push    rdi
0x18004e4f7  sub     rsp, 20h
0x18004e4fb  mov     rsi, [rcx]
0x18004e4fe  mov     rdi, rcx
0x18004e501  test    rsi, rsi
0x18004e504  jz      short loc_18004E53E
0x18004e506  call    cs:__imp_GetLastError
0x18004e50c  xor     r9d, r9d; msWindowLength
0x18004e50f  xor     r8d, r8d; msPeriod
0x18004e512  xor     edx, edx; pftDueTime
0x18004e514  mov     rcx, rsi; pti
0x18004e517  mov     ebx, eax
0x18004e519  call    cs:__imp_SetThreadpoolTimer
0x18004e51f  mov     edx, 1; fCancelPendingCallbacks
0x18004e524  mov     rcx, rsi; pti
0x18004e527  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18004e52d  mov     rcx, rsi; pti
0x18004e530  call    cs:__imp_CloseThreadpoolTimer
0x18004e536  mov     ecx, ebx; dwErrCode
0x18004e538  call    cs:__imp_SetLastError
0x18004e53e  mov     qword ptr [rdi], 0
0x18004e545  cmp     dword ptr [rdi+8], 0
0x18004e549  jz      short loc_18004E55A
0x18004e54b  xor     ecx, ecx; pReserved
0x18004e54d  call    cs:__imp_CoDisableCallCancellation
0x18004e553  mov     dword ptr [rdi+8], 0
0x18004e55a  mov     rbx, [rdi]
0x18004e55d  test    rbx, rbx
0x18004e560  jz      short loc_18004E58A
0x18004e562  xor     r9d, r9d; msWindowLength
0x18004e565  xor     r8d, r8d; msPeriod
0x18004e568  xor     edx, edx; pftDueTime
0x18004e56a  mov     rcx, rbx; pti
0x18004e56d  call    cs:__imp_SetThreadpoolTimer
0x18004e573  mov     edx, 1; fCancelPendingCallbacks
0x18004e578  mov     rcx, rbx; pti
0x18004e57b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18004e581  mov     rcx, rbx; pti
0x18004e584  call    cs:__imp_CloseThreadpoolTimer
0x18004e58a  mov     rbx, [rsp+28h+arg_0]
0x18004e58f  mov     rsi, [rsp+28h+arg_8]
0x18004e594  add     rsp, 20h
0x18004e598  pop     rdi
0x18004e599  retn
```
