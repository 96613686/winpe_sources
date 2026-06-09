# _CatDBServiceStopJet

- ea: `0x18001b320`
- end: `0x18001b4d4`
- name: `_CatDBServiceStopJet`
- size: `436`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18000ad54`

## callees

- `0x180002b90`
- `0x18000a59c`
- `0x18001b320`
- `0x18001b620`
- `0x18001b670`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001b3eb`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001b3eb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b354`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b447`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b354`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001b447`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001b426`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001b426`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b3fb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b40c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b476`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b4a6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b3fb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b40c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b476`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001b4a6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001b339`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001b3ce`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001b45b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001b4b1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001b339`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001b3ce`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001b45b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001b4b1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b488`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b488`

## pseudocode

```c
void CatDBServiceStopJet()
{
  unsigned int v0; // edx
  unsigned __int16 *v1; // rcx
  unsigned int v2; // r8d
  unsigned int v3; // edx
  unsigned __int16 *v4; // rcx
  unsigned int v5; // edx
  unsigned __int16 *v6; // rcx
  unsigned int v7; // r8d
  unsigned int v8; // edx
  unsigned __int16 *v9; // rcx
  int v10; // [rsp+28h] [rbp-10h]

  if ( !g_fDBSvcInitialized )
  {
    SetLastError(0x426u);
    v2 = 8391;
LABEL_27:
    ErrLog_LogError(v1, v0, v2, 0, 0, v10);
    return;
  }
  EnterCriticalSection(&g_JetDBOpenCS);
  if ( g_fJetDBServiceStop || !g_hJetDBServiceStopWaitEvent )
  {
    LeaveCriticalSection(&g_JetDBOpenCS);
    SetLastError(0x8000FFFF);
    v2 = 8401;
    goto LABEL_27;
  }
  g_fJetDBServiceStop = 1;
  if ( g_fJetDBFreeze )
  {
    g_fJetDBFreeze = 0;
    ErrLog_LogError(v4, v3, 0x20DBu, 0x426u, 0, v10);
  }
  CatDBSignalPendingJetOpen(1062);
  if ( g_dwJetDBState == 1 )
  {
    ++g_dwJetDBOpenRefCnt;
    LeaveCriticalSection(&g_JetDBOpenCS);
    _CatDBCloseJet(1);
  }
  else
  {
    if ( g_dwJetDBState == 2 )
    {
      CatDBSignalPendingJetFreezeOrStop();
    }
    else if ( g_dwJetDBState == 3 )
    {
      if ( g_hJetDBOpenThreadWaitEvent )
        SetEvent(g_hJetDBOpenThreadWaitEvent);
    }
    else if ( g_dwJetDBState - 4 >= 2 )
    {
      SetLastError(0x8000FFFF);
      v7 = 8447;
      goto LABEL_21;
    }
    LeaveCriticalSection(&g_JetDBOpenCS);
  }
  if ( !WaitForSingleObject(g_hJetDBServiceStopWaitEvent, 0xFFFFFFFF) )
  {
    EnterCriticalSection(&g_JetDBOpenCS);
    if ( g_dwJetDBState == 2 )
    {
LABEL_22:
      LeaveCriticalSection(&g_JetDBOpenCS);
      goto LABEL_23;
    }
    SetLastError(0x8000FFFF);
    v7 = 8473;
LABEL_21:
    ErrLog_LogError(v6, v5, v7, 0, 0, v10);
    goto LABEL_22;
  }
  ErrLog_LogError(v9, v8, 0x210Fu, 0, 0, v10);
LABEL_23:
  if ( g_hJetDBServiceStopWaitEvent )
  {
    CloseHandle(g_hJetDBServiceStopWaitEvent);
    g_hJetDBServiceStopWaitEvent = 0;
  }
  g_dwJetDBState = 0;
  g_fJetDBServiceStop = 0;
}

```

## disassembly

```asm
0x18001b320  mov     [rsp+arg_0], rbx
0x18001b325  push    rdi
0x18001b326  sub     rsp, 30h
0x18001b32a  xor     ebx, ebx
0x18001b32c  cmp     cs:?g_fDBSvcInitialized@@3HA, ebx; int g_fDBSvcInitialized
0x18001b332  jnz     short loc_18001B34A
0x18001b334  mov     ecx, 426h; dwErrCode
0x18001b339  call    cs:__imp_SetLastError
0x18001b33f  mov     r8d, 20C7h
0x18001b345  jmp     loc_18001B4BD
0x18001b34a  lea     rdi, ?g_JetDBOpenCS@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_JetDBOpenCS
0x18001b351  mov     rcx, rdi; lpCriticalSection
0x18001b354  call    cs:__imp_EnterCriticalSection
0x18001b35a  cmp     cs:?g_fJetDBServiceStop@@3HA, ebx; int g_fJetDBServiceStop
0x18001b360  jnz     loc_18001B4A3
0x18001b366  cmp     cs:?g_hJetDBServiceStopWaitEvent@@3PEAXEA, rbx; void * g_hJetDBServiceStopWaitEvent
0x18001b36d  jz      loc_18001B4A3
0x18001b373  cmp     cs:?g_fJetDBFreeze@@3HA, ebx; int g_fJetDBFreeze
0x18001b379  mov     cs:?g_fJetDBServiceStop@@3HA, 1; int g_fJetDBServiceStop
0x18001b383  jz      short loc_18001B3A0
0x18001b385  mov     r9d, 426h; unsigned int
0x18001b38b  mov     cs:?g_fJetDBFreeze@@3HA, ebx; int g_fJetDBFreeze
0x18001b391  mov     r8d, 20DBh; unsigned int
0x18001b397  mov     [rsp+38h+var_18], ebx; int
0x18001b39b  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x18001b3a0  mov     ecx, 426h
0x18001b3a5  call    _CatDBSignalPendingJetOpen
0x18001b3aa  mov     eax, cs:?g_dwJetDBState@@3KA; ulong g_dwJetDBState
0x18001b3b0  sub     eax, 1
0x18001b3b3  jz      short loc_18001B403
0x18001b3b5  sub     eax, 1
0x18001b3b8  jz      short loc_18001B3F3
0x18001b3ba  sub     eax, 1
0x18001b3bd  jz      short loc_18001B3DF
0x18001b3bf  sub     eax, 1
0x18001b3c2  jz      short loc_18001B3F8
0x18001b3c4  cmp     eax, 1
0x18001b3c7  jz      short loc_18001B3F8
0x18001b3c9  mov     ecx, 8000FFFFh; dwErrCode
0x18001b3ce  call    cs:__imp_SetLastError
0x18001b3d4  mov     r8d, 20FFh
0x18001b3da  jmp     loc_18001B467
0x18001b3df  mov     rcx, cs:?g_hJetDBOpenThreadWaitEvent@@3PEAXEA; hEvent
0x18001b3e6  test    rcx, rcx
0x18001b3e9  jz      short loc_18001B3F8
0x18001b3eb  call    cs:__imp_SetEvent
0x18001b3f1  jmp     short loc_18001B3F8
0x18001b3f3  call    _CatDBSignalPendingJetFreezeOrStop
0x18001b3f8  mov     rcx, rdi; lpCriticalSection
0x18001b3fb  call    cs:__imp_LeaveCriticalSection
0x18001b401  jmp     short loc_18001B41C
0x18001b403  inc     cs:?g_dwJetDBOpenRefCnt@@3KA; ulong g_dwJetDBOpenRefCnt
0x18001b409  mov     rcx, rdi; lpCriticalSection
0x18001b40c  call    cs:__imp_LeaveCriticalSection
0x18001b412  mov     ecx, 1; int
0x18001b417  call    ?_CatDBCloseJet@@YAXH@Z; _CatDBCloseJet(int)
0x18001b41c  mov     rcx, cs:?g_hJetDBServiceStopWaitEvent@@3PEAXEA; hHandle
0x18001b423  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18001b426  call    cs:__imp_WaitForSingleObject
0x18001b42c  test    eax, eax
0x18001b42e  jz      short loc_18001B444
0x18001b430  xor     r9d, r9d; unsigned int
0x18001b433  mov     [rsp+38h+var_18], ebx; int
0x18001b437  mov     r8d, 210Fh; unsigned int
0x18001b43d  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x18001b442  jmp     short loc_18001B47C
0x18001b444  mov     rcx, rdi; lpCriticalSection
0x18001b447  call    cs:__imp_EnterCriticalSection
0x18001b44d  cmp     cs:?g_dwJetDBState@@3KA, 2; ulong g_dwJetDBState
0x18001b454  jz      short loc_18001B473
0x18001b456  mov     ecx, 8000FFFFh; dwErrCode
0x18001b45b  call    cs:__imp_SetLastError
0x18001b461  mov     r8d, 2119h; unsigned int
0x18001b467  xor     r9d, r9d; unsigned int
0x18001b46a  mov     [rsp+38h+var_18], ebx; int
0x18001b46e  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x18001b473  mov     rcx, rdi; lpCriticalSection
0x18001b476  call    cs:__imp_LeaveCriticalSection
0x18001b47c  mov     rcx, cs:?g_hJetDBServiceStopWaitEvent@@3PEAXEA; hObject
0x18001b483  test    rcx, rcx
0x18001b486  jz      short loc_18001B495
0x18001b488  call    cs:__imp_CloseHandle
0x18001b48e  mov     cs:?g_hJetDBServiceStopWaitEvent@@3PEAXEA, rbx; void * g_hJetDBServiceStopWaitEvent
0x18001b495  mov     cs:?g_dwJetDBState@@3KA, ebx; ulong g_dwJetDBState
0x18001b49b  mov     cs:?g_fJetDBServiceStop@@3HA, ebx; int g_fJetDBServiceStop
0x18001b4a1  jmp     short loc_18001B4C9
0x18001b4a3  mov     rcx, rdi; lpCriticalSection
0x18001b4a6  call    cs:__imp_LeaveCriticalSection
0x18001b4ac  mov     ecx, 8000FFFFh; dwErrCode
0x18001b4b1  call    cs:__imp_SetLastError
0x18001b4b7  mov     r8d, 20D1h; unsigned int
0x18001b4bd  xor     r9d, r9d; unsigned int
0x18001b4c0  mov     [rsp+38h+var_18], ebx; int
0x18001b4c4  call    ?ErrLog_LogError@@YAXPEAGKKKHH@Z; ErrLog_LogError(ushort *,ulong,ulong,ulong,int,int)
0x18001b4c9  mov     rbx, [rsp+38h+arg_0]
0x18001b4ce  add     rsp, 30h
0x18001b4d2  pop     rdi
0x18001b4d3  retn
```
