# WEBSOCKET_PING_MANAGER::PingTimerCallback(_TP_CALLBACK_INSTANCE *,void *,_TP_TIMER *)

- ea: `0x180003480`
- end: `0x1800035aa`
- name: `?PingTimerCallback@WEBSOCKET_PING_MANAGER@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z`
- size: `298`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_TIMER Timer)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180003480`
- `0x1800069a0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000353a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000353a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000352d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003581`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000352d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003581`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800034c2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800034fc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800034c2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800034fc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180003590`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180003590`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180003505`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180003505`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800034a6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800034a6`

## pseudocode

```c
void __fastcall WEBSOCKET_PING_MANAGER::PingTimerCallback(
        PTP_CALLBACK_INSTANCE Instance,
        PVOID Context,
        PTP_TIMER Timer)
{
  struct _LIST_ENTRY *Flink; // rdi
  DWORD v4; // ebx
  struct _LIST_ENTRY *Blink; // rax
  struct _FILETIME pftDueTime; // [rsp+58h] [rbp+20h] BYREF

  pftDueTime = 0;
  AcquireSRWLockShared(&WEBSOCKET_PING_MANAGER::sm_RequestsListLock);
  Flink = WEBSOCKET_PING_MANAGER::sm_trackerListHead.Flink;
  if ( WEBSOCKET_PING_MANAGER::sm_trackerListHead.Flink == &WEBSOCKET_PING_MANAGER::sm_trackerListHead )
  {
    ReleaseSRWLockShared(&WEBSOCKET_PING_MANAGER::sm_RequestsListLock);
  }
  else
  {
    v4 = 0;
    while ( Flink != &WEBSOCKET_PING_MANAGER::sm_trackerListHead )
    {
      if ( (int)WEBSOCKET_CONTEXT::SendPingMessage((WEBSOCKET_CONTEXT *)&Flink[-1]) >= 0 )
      {
        Blink = Flink[15].Blink;
        if ( v4 > LODWORD(Blink[1].Blink) || !v4 )
          v4 = (DWORD)Blink[1].Blink;
      }
      Flink = Flink->Flink;
    }
    ReleaseSRWLockShared(&WEBSOCKET_PING_MANAGER::sm_RequestsListLock);
    AcquireSRWLockExclusive(&WEBSOCKET_PING_MANAGER::sm_RequestsListLock);
    if ( WEBSOCKET_PING_MANAGER::sm_dwInitializationFlags == 1 )
    {
      if ( v4 )
      {
        if ( v4 != WEBSOCKET_PING_MANAGER::sm_dwPingInterval )
        {
          pftDueTime.dwLowDateTime = -10000 * v4;
          pftDueTime.dwHighDateTime = 0;
          SetThreadpoolTimer(WEBSOCKET_PING_MANAGER::sm_hPingTimer, &pftDueTime, v4, 0);
          WEBSOCKET_PING_MANAGER::sm_dwPingInterval = v4;
        }
      }
      else
      {
        WEBSOCKET_PING_MANAGER::sm_dwInitializationFlags = 0;
        SetThreadpoolTimer(WEBSOCKET_PING_MANAGER::sm_hPingTimer, 0, 0, 0);
        CloseThreadpoolTimer(WEBSOCKET_PING_MANAGER::sm_hPingTimer);
        WEBSOCKET_PING_MANAGER::sm_hPingTimer = 0;
        WEBSOCKET_PING_MANAGER::sm_dwPingInterval = 0;
      }
    }
    ReleaseSRWLockExclusive(&WEBSOCKET_PING_MANAGER::sm_RequestsListLock);
  }
}

```

## disassembly

```asm
0x180003480  mov     [rsp+arg_0], rbx
0x180003485  mov     [rsp+arg_8], rsi
0x18000348a  push    rdi
0x18000348b  push    r14
0x18000348d  push    r15
0x18000348f  sub     rsp, 20h
0x180003493  lea     r14, ?sm_RequestsListLock@WEBSOCKET_PING_MANAGER@@2U_RTL_SRWLOCK@@A; _RTL_SRWLOCK WEBSOCKET_PING_MANAGER::sm_RequestsListLock
0x18000349a  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], 0
0x1800034a3  mov     rcx, r14; SRWLock
0x1800034a6  call    cs:__imp_AcquireSRWLockShared
0x1800034ac  mov     rdi, cs:?sm_trackerListHead@WEBSOCKET_PING_MANAGER@@2U_LIST_ENTRY@@A; _LIST_ENTRY WEBSOCKET_PING_MANAGER::sm_trackerListHead
0x1800034b3  lea     r15, ?sm_trackerListHead@WEBSOCKET_PING_MANAGER@@2U_LIST_ENTRY@@A; _LIST_ENTRY WEBSOCKET_PING_MANAGER::sm_trackerListHead
0x1800034ba  cmp     rdi, r15
0x1800034bd  jnz     short loc_1800034CD
0x1800034bf  mov     rcx, r14; SRWLock
0x1800034c2  call    cs:__imp_ReleaseSRWLockShared
0x1800034c8  jmp     loc_180003596
0x1800034cd  xor     ebx, ebx
0x1800034cf  jmp     short loc_1800034F4
0x1800034d1  lea     rcx, [rdi-10h]; this
0x1800034d5  call    ?SendPingMessage@WEBSOCKET_CONTEXT@@QEAAJXZ; WEBSOCKET_CONTEXT::SendPingMessage(void)
0x1800034da  test    eax, eax
0x1800034dc  js      short loc_1800034F1
0x1800034de  mov     rax, [rdi+0F8h]
0x1800034e5  cmp     ebx, [rax+18h]
0x1800034e8  ja      short loc_1800034EE
0x1800034ea  test    ebx, ebx
0x1800034ec  jnz     short loc_1800034F1
0x1800034ee  mov     ebx, [rax+18h]
0x1800034f1  mov     rdi, [rdi]
0x1800034f4  cmp     rdi, r15
0x1800034f7  jnz     short loc_1800034D1
0x1800034f9  mov     rcx, r14; SRWLock
0x1800034fc  call    cs:__imp_ReleaseSRWLockShared
0x180003502  mov     rcx, r14; SRWLock
0x180003505  call    cs:__imp_AcquireSRWLockExclusive
0x18000350b  cmp     cs:?sm_dwInitializationFlags@WEBSOCKET_PING_MANAGER@@0W4PingManagerInitializationFlags@@A, 1; PingManagerInitializationFlags WEBSOCKET_PING_MANAGER::sm_dwInitializationFlags
0x180003512  jnz     short loc_18000358D
0x180003514  test    ebx, ebx
0x180003516  jnz     short loc_180003553
0x180003518  mov     rcx, cs:?sm_hPingTimer@WEBSOCKET_PING_MANAGER@@2PEAU_TP_TIMER@@EA; pti
0x18000351f  xor     r9d, r9d; msWindowLength
0x180003522  xor     r8d, r8d; msPeriod
0x180003525  mov     cs:?sm_dwInitializationFlags@WEBSOCKET_PING_MANAGER@@0W4PingManagerInitializationFlags@@A, ebx; PingManagerInitializationFlags WEBSOCKET_PING_MANAGER::sm_dwInitializationFlags
0x18000352b  xor     edx, edx; pftDueTime
0x18000352d  call    cs:__imp_SetThreadpoolTimer
0x180003533  mov     rcx, cs:?sm_hPingTimer@WEBSOCKET_PING_MANAGER@@2PEAU_TP_TIMER@@EA; pti
0x18000353a  call    cs:__imp_CloseThreadpoolTimer
0x180003540  mov     cs:?sm_hPingTimer@WEBSOCKET_PING_MANAGER@@2PEAU_TP_TIMER@@EA, 0; _TP_TIMER * WEBSOCKET_PING_MANAGER::sm_hPingTimer
0x18000354b  mov     cs:?sm_dwPingInterval@WEBSOCKET_PING_MANAGER@@0KA, ebx; ulong WEBSOCKET_PING_MANAGER::sm_dwPingInterval
0x180003551  jmp     short loc_18000358D
0x180003553  cmp     ebx, cs:?sm_dwPingInterval@WEBSOCKET_PING_MANAGER@@0KA; ulong WEBSOCKET_PING_MANAGER::sm_dwPingInterval
0x180003559  jz      short loc_18000358D
0x18000355b  imul    eax, ebx, 0FFFFD8F0h
0x180003561  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x180003566  xor     r9d, r9d; msWindowLength
0x180003569  mov     r8d, ebx; msPeriod
0x18000356c  mov     ecx, eax
0x18000356e  mov     [rsp+38h+pftDueTime.dwLowDateTime], eax
0x180003572  shr     rcx, 20h
0x180003576  mov     [rsp+38h+pftDueTime.dwHighDateTime], ecx
0x18000357a  mov     rcx, cs:?sm_hPingTimer@WEBSOCKET_PING_MANAGER@@2PEAU_TP_TIMER@@EA; pti
0x180003581  call    cs:__imp_SetThreadpoolTimer
0x180003587  mov     cs:?sm_dwPingInterval@WEBSOCKET_PING_MANAGER@@0KA, ebx; ulong WEBSOCKET_PING_MANAGER::sm_dwPingInterval
0x18000358d  mov     rcx, r14; SRWLock
0x180003590  call    cs:__imp_ReleaseSRWLockExclusive
0x180003596  mov     rbx, [rsp+38h+arg_0]
0x18000359b  mov     rsi, [rsp+38h+arg_8]
0x1800035a0  add     rsp, 20h
0x1800035a4  pop     r15
0x1800035a6  pop     r14
0x1800035a8  pop     rdi
0x1800035a9  retn
```
