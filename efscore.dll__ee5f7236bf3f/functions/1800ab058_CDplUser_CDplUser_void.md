# CDplUser::~CDplUser(void)

- ea: `0x1800ab058`
- end: `0x1800ab18d`
- name: `??1CDplUser@@UEAA@XZ`
- size: `309`
- prototype: `void __fastcall(CDplUser *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800ab1a0`

## callees

- `0x180087d68`
- `0x1800ab058`
- `0x1800d5af8`
- `0x1800dca3c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800ab186`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800ab0bf`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800ab103`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800ab0bf`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800ab103`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800ab0de`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800ab122`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800ab0de`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800ab122`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800ab0d1`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800ab115`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800ab0d1`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800ab115`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ab13c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ab153`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ab13c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ab153`

## pseudocode

```c
void __fastcall CDplUser::~CDplUser(CDplUser *this)
{
  __int64 v2; // rax
  __int64 v3; // rcx
  bool v4; // zf
  struct _TP_TIMER *v5; // rcx
  struct _TP_TIMER *v6; // rcx
  void *v7; // rcx
  void *v8; // rcx
  void *v9; // rcx

  *(_QWORD *)this = &CDplUser::`vftable';
  v2 = ReleaseIf<CDplKeyPair>(*((_QWORD *)this + 20));
  v4 = *((_DWORD *)this + 10) == 0;
  *((_QWORD *)this + 20) = v2;
  if ( !v4 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v3);
  if ( *((CDplUser **)this + 25) != (CDplUser *)((char *)this + 200) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v3);
  if ( *((CDplUser **)this + 27) != (CDplUser *)((char *)this + 216) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v3);
  v5 = (struct _TP_TIMER *)*((_QWORD *)this + 41);
  if ( v5 )
  {
    SetThreadpoolTimer(v5, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)this + 41), 1);
    CloseThreadpoolTimer(*((PTP_TIMER *)this + 41));
    *((_QWORD *)this + 41) = 0;
  }
  v6 = (struct _TP_TIMER *)*((_QWORD *)this + 34);
  if ( v6 )
  {
    SetThreadpoolTimer(v6, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)this + 34), 1);
    CloseThreadpoolTimer(*((PTP_TIMER *)this + 34));
    *((_QWORD *)this + 34) = 0;
  }
  v7 = (void *)*((_QWORD *)this + 14);
  if ( v7 )
  {
    LocalFree(v7);
    *((_QWORD *)this + 14) = 0;
  }
  v8 = (void *)*((_QWORD *)this + 13);
  if ( v8 )
  {
    LocalFree(v8);
    *((_QWORD *)this + 13) = 0;
  }
  v9 = (void *)*((_QWORD *)this + 38);
  if ( v9 )
    DplibMemFree(v9);
  *((_QWORD *)this + 38) = 0;
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
}

```

## disassembly

```asm
0x1800ab058  push    rbx
0x1800ab05a  sub     rsp, 20h
0x1800ab05e  lea     rax, ??_7CDplUser@@6B@; const CDplUser::`vftable'
0x1800ab065  mov     rbx, rcx
0x1800ab068  mov     [rcx], rax
0x1800ab06b  mov     rcx, [rcx+0A0h]
0x1800ab072  call    ??$ReleaseIf@VCDplKeyPair@@@@YAPEAVCDplKeyPair@@PEAV0@@Z; ReleaseIf<CDplKeyPair>(CDplKeyPair *)
0x1800ab077  cmp     dword ptr [rbx+28h], 0
0x1800ab07b  mov     [rbx+0A0h], rax
0x1800ab082  jz      short loc_1800AB089
0x1800ab084  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "m_RefCount == 0")
0x1800ab089  lea     rax, [rbx+0C8h]
0x1800ab090  cmp     [rax], rax
0x1800ab093  jz      short loc_1800AB09A
0x1800ab095  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "IsListEmpty(&m_DplAccountListHead)")
0x1800ab09a  lea     rax, [rbx+0D8h]
0x1800ab0a1  cmp     [rax], rax
0x1800ab0a4  jz      short loc_1800AB0AB
0x1800ab0a6  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "IsListEmpty(&m_DecryptionFailedAccountListHead)")
0x1800ab0ab  mov     rcx, [rbx+148h]; pti
0x1800ab0b2  test    rcx, rcx
0x1800ab0b5  jz      short loc_1800AB0EF
0x1800ab0b7  xor     r9d, r9d; msWindowLength
0x1800ab0ba  xor     r8d, r8d; msPeriod
0x1800ab0bd  xor     edx, edx; pftDueTime
0x1800ab0bf  call    cs:__imp_SetThreadpoolTimer
0x1800ab0c5  mov     rcx, [rbx+148h]; pti
0x1800ab0cc  mov     edx, 1; fCancelPendingCallbacks
0x1800ab0d1  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800ab0d7  mov     rcx, [rbx+148h]; pti
0x1800ab0de  call    cs:__imp_CloseThreadpoolTimer
0x1800ab0e4  mov     qword ptr [rbx+148h], 0
0x1800ab0ef  mov     rcx, [rbx+110h]; pti
0x1800ab0f6  test    rcx, rcx
0x1800ab0f9  jz      short loc_1800AB133
0x1800ab0fb  xor     r9d, r9d; msWindowLength
0x1800ab0fe  xor     r8d, r8d; msPeriod
0x1800ab101  xor     edx, edx; pftDueTime
0x1800ab103  call    cs:__imp_SetThreadpoolTimer
0x1800ab109  mov     rcx, [rbx+110h]; pti
0x1800ab110  mov     edx, 1; fCancelPendingCallbacks
0x1800ab115  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800ab11b  mov     rcx, [rbx+110h]; pti
0x1800ab122  call    cs:__imp_CloseThreadpoolTimer
0x1800ab128  mov     qword ptr [rbx+110h], 0
0x1800ab133  mov     rcx, [rbx+70h]; hMem
0x1800ab137  test    rcx, rcx
0x1800ab13a  jz      short loc_1800AB14A
0x1800ab13c  call    cs:__imp_LocalFree
0x1800ab142  mov     qword ptr [rbx+70h], 0
0x1800ab14a  mov     rcx, [rbx+68h]; hMem
0x1800ab14e  test    rcx, rcx
0x1800ab151  jz      short loc_1800AB161
0x1800ab153  call    cs:__imp_LocalFree
0x1800ab159  mov     qword ptr [rbx+68h], 0
0x1800ab161  mov     rcx, [rbx+130h]; void *
0x1800ab168  test    rcx, rcx
0x1800ab16b  jz      short loc_1800AB172
0x1800ab16d  call    ?DplibMemFree@@YAJPEAX@Z; DplibMemFree(void *)
0x1800ab172  lea     rcx, [rbx+38h]
0x1800ab176  mov     qword ptr [rbx+130h], 0
0x1800ab181  add     rsp, 20h
0x1800ab185  pop     rbx
0x1800ab186  jmp     cs:__imp_DeleteCriticalSection
```
