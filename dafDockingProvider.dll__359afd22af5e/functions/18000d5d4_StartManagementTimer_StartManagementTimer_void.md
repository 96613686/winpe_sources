# StartManagementTimer::~StartManagementTimer(void)

- ea: `0x18000d5d4`
- end: `0x18000d651`
- name: `??1StartManagementTimer@@QEAA@XZ`
- size: `125`
- prototype: `void __fastcall(PTP_TIMER *this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000d4f4`

## callees

- `0x18000d5d4`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000d5fb`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000d5fb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000d5ed`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000d5ed`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000d604`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000d604`

## pseudocode

```c
void __fastcall StartManagementTimer::~StartManagementTimer(PTP_TIMER *this)
{
  struct _TP_TIMER *v2; // rcx
  PTP_TIMER v3; // rcx
  PTP_TIMER v4; // rcx

  v2 = *this;
  if ( v2 )
  {
    SetThreadpoolTimer(v2, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(*this, 1);
    CloseThreadpoolTimer(*this);
    *this = 0;
  }
  v3 = this[3];
  if ( v3 )
  {
    (*(void (__fastcall **)(PTP_TIMER))(*(_QWORD *)v3 + 16LL))(v3);
    this[3] = 0;
  }
  v4 = this[2];
  if ( v4 )
  {
    (*(void (__fastcall **)(PTP_TIMER))(*(_QWORD *)v4 + 16LL))(v4);
    this[2] = 0;
  }
}

```

## disassembly

```asm
0x18000d5d4  push    rbx
0x18000d5d6  sub     rsp, 20h
0x18000d5da  mov     rbx, rcx
0x18000d5dd  mov     rcx, [rcx]; pti
0x18000d5e0  test    rcx, rcx
0x18000d5e3  jz      short loc_18000D611
0x18000d5e5  xor     r9d, r9d; msWindowLength
0x18000d5e8  xor     r8d, r8d; msPeriod
0x18000d5eb  xor     edx, edx; pftDueTime
0x18000d5ed  call    cs:__imp_SetThreadpoolTimer
0x18000d5f3  mov     edx, 1; fCancelPendingCallbacks
0x18000d5f8  mov     rcx, [rbx]; pti
0x18000d5fb  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000d601  mov     rcx, [rbx]; pti
0x18000d604  call    cs:__imp_CloseThreadpoolTimer
0x18000d60a  mov     qword ptr [rbx], 0
0x18000d611  mov     rcx, [rbx+18h]
0x18000d615  test    rcx, rcx
0x18000d618  jz      short loc_18000D62E
0x18000d61a  mov     rax, [rcx]
0x18000d61d  mov     rax, [rax+10h]
0x18000d621  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d626  mov     qword ptr [rbx+18h], 0
0x18000d62e  mov     rcx, [rbx+10h]
0x18000d632  test    rcx, rcx
0x18000d635  jz      short loc_18000D64B
0x18000d637  mov     rax, [rcx]
0x18000d63a  mov     rax, [rax+10h]
0x18000d63e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d643  mov     qword ptr [rbx+10h], 0
0x18000d64b  add     rsp, 20h
0x18000d64f  pop     rbx
0x18000d650  retn
```
