# WEBSOCKET_PING_MANAGER::DelayStart(ulong)

- ea: `0x1800033a4`
- end: `0x18000346b`
- name: `?DelayStart@WEBSOCKET_PING_MANAGER@@CAJK@Z`
- size: `199`
- prototype: `__int64 __fastcall(DWORD msPeriod)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180008080`

## callees

- `0x1800033a4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800033d0`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800033d0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003407`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180003407`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000344e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000344e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800033e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800033e2`

## pseudocode

```c
__int64 __fastcall WEBSOCKET_PING_MANAGER::DelayStart(DWORD msPeriod)
{
  signed int v1; // ebx
  struct _TP_TIMER *ThreadpoolTimer; // rax
  signed int LastError; // eax
  struct _FILETIME pftDueTime; // [rsp+38h] [rbp+10h] BYREF

  v1 = 0;
  pftDueTime = 0;
  if ( WEBSOCKET_PING_MANAGER::sm_dwInitializationFlags != 1 )
  {
    ThreadpoolTimer = CreateThreadpoolTimer((PTP_TIMER_CALLBACK)WEBSOCKET_PING_MANAGER::PingTimerCallback, 0, 0);
    WEBSOCKET_PING_MANAGER::sm_hPingTimer = ThreadpoolTimer;
    if ( ThreadpoolTimer )
    {
      WEBSOCKET_PING_MANAGER::sm_dwPingInterval = msPeriod;
      pftDueTime.dwLowDateTime = -10000 * msPeriod;
      pftDueTime.dwHighDateTime = 0;
      SetThreadpoolTimer(ThreadpoolTimer, &pftDueTime, msPeriod, 0);
      WEBSOCKET_PING_MANAGER::sm_dwInitializationFlags = 1;
    }
    else
    {
      LastError = GetLastError();
      v1 = LastError;
      if ( LastError > 0 )
        v1 = (unsigned __int16)LastError | 0x80070000;
      if ( v1 < 0 )
      {
        if ( WEBSOCKET_PING_MANAGER::sm_hPingTimer )
        {
          CloseThreadpoolTimer(WEBSOCKET_PING_MANAGER::sm_hPingTimer);
          WEBSOCKET_PING_MANAGER::sm_hPingTimer = 0;
        }
        WEBSOCKET_PING_MANAGER::sm_dwInitializationFlags = 2;
      }
    }
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x1800033a4  mov     [rsp+arg_0], rbx
0x1800033a9  push    rdi
0x1800033aa  sub     rsp, 20h
0x1800033ae  xor     ebx, ebx
0x1800033b0  mov     edi, ecx
0x1800033b2  cmp     cs:?sm_dwInitializationFlags@WEBSOCKET_PING_MANAGER@@0W4PingManagerInitializationFlags@@A, 1; PingManagerInitializationFlags WEBSOCKET_PING_MANAGER::sm_dwInitializationFlags
0x1800033b9  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], rbx
0x1800033be  jz      loc_18000345E
0x1800033c4  xor     r8d, r8d; pcbe
0x1800033c7  lea     rcx, ?PingTimerCallback@WEBSOCKET_PING_MANAGER@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800033ce  xor     edx, edx; pv
0x1800033d0  call    cs:__imp_CreateThreadpoolTimer
0x1800033d6  mov     cs:?sm_hPingTimer@WEBSOCKET_PING_MANAGER@@2PEAU_TP_TIMER@@EA, rax; _TP_TIMER * WEBSOCKET_PING_MANAGER::sm_hPingTimer
0x1800033dd  test    rax, rax
0x1800033e0  jnz     short loc_180003424
0x1800033e2  call    cs:__imp_GetLastError
0x1800033e8  mov     ebx, eax
0x1800033ea  test    eax, eax
0x1800033ec  jle     short loc_1800033F7
0x1800033ee  movzx   ebx, ax
0x1800033f1  or      ebx, 80070000h
0x1800033f7  test    ebx, ebx
0x1800033f9  jns     short loc_18000345E
0x1800033fb  mov     rcx, cs:?sm_hPingTimer@WEBSOCKET_PING_MANAGER@@2PEAU_TP_TIMER@@EA; pti
0x180003402  test    rcx, rcx
0x180003405  jz      short loc_180003418
0x180003407  call    cs:__imp_CloseThreadpoolTimer
0x18000340d  mov     cs:?sm_hPingTimer@WEBSOCKET_PING_MANAGER@@2PEAU_TP_TIMER@@EA, 0; _TP_TIMER * WEBSOCKET_PING_MANAGER::sm_hPingTimer
0x180003418  mov     cs:?sm_dwInitializationFlags@WEBSOCKET_PING_MANAGER@@0W4PingManagerInitializationFlags@@A, 2; PingManagerInitializationFlags WEBSOCKET_PING_MANAGER::sm_dwInitializationFlags
0x180003422  jmp     short loc_18000345E
0x180003424  imul    edx, edi, 0FFFFD8F0h
0x18000342a  xor     r9d, r9d; msWindowLength
0x18000342d  mov     rcx, rax; pti
0x180003430  mov     cs:?sm_dwPingInterval@WEBSOCKET_PING_MANAGER@@0KA, edi; ulong WEBSOCKET_PING_MANAGER::sm_dwPingInterval
0x180003436  mov     r8d, edx
0x180003439  mov     [rsp+28h+pftDueTime.dwLowDateTime], edx
0x18000343d  shr     r8, 20h
0x180003441  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x180003446  mov     [rsp+28h+pftDueTime.dwHighDateTime], r8d
0x18000344b  mov     r8d, edi; msPeriod
0x18000344e  call    cs:__imp_SetThreadpoolTimer
0x180003454  mov     cs:?sm_dwInitializationFlags@WEBSOCKET_PING_MANAGER@@0W4PingManagerInitializationFlags@@A, 1; PingManagerInitializationFlags WEBSOCKET_PING_MANAGER::sm_dwInitializationFlags
0x18000345e  mov     eax, ebx
0x180003460  mov     rbx, [rsp+28h+arg_0]
0x180003465  add     rsp, 20h
0x180003469  pop     rdi
0x18000346a  retn
```
