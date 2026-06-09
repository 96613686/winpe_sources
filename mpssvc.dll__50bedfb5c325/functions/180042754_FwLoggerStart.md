# FwLoggerStart

- ea: `0x180042754`
- end: `0x180042a45`
- name: `FwLoggerStart`
- size: `753`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18006d5f4`
- `0x1800993a4`

## callees

- `0x1800089bc`
- `0x180008a80`
- `0x1800097b0`
- `0x18000a710`
- `0x180042754`
- `0x180042a4c`
- `0x1800436d4`
- `0x180043758`
- `0x18006dc98`
- `0x18006ed38`
- `0x18007d3c8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180042829`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180042829`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180042945`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180042986`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180042945`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180042986`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180042768`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180042768`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18004288d`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18004288d`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x1800429c0`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x1800429c0`

## pseudocode

```c
void FwLoggerStart()
{
  int v0; // r8d
  __int64 v1; // rcx
  int v2; // ebp
  int v3; // esi
  __int64 i; // rdi
  unsigned int v5; // eax
  unsigned __int64 *v6; // rdx
  __int64 v7; // rcx
  struct tagHNET_FW_LOGGING_SETTINGS * near **v8; // r14
  int LogSettings; // eax
  int v10; // r8d
  int v11; // r8d
  int v12; // ebx

  EnterCriticalSection(&g_FwLock);
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    WPP_SF_ss(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 18, v0, (unsigned int)"FwLoggerStart", (__int64)"g_Fw");
  v2 = FwLock();
  if ( v2 >= 0 )
  {
    v3 = 0;
    g_fTracingActive = 1;
    for ( i = 0; (unsigned int)i < 3; i = (unsigned int)(i + 1) )
    {
      v8 = &(&g_pSettings)[i];
      if ( !*v8 )
      {
        LogSettings = FwGetLogSettings((unsigned int)i, &(&g_pSettings)[i]);
        v2 = LogSettings;
        if ( LogSettings < 0 )
        {
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
            WPP_SF_d(
              *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
              42,
              WPP_3d59fee1d00932d8b651bda1e8e67a3f_Traceguids,
              (unsigned int)LogSettings);
          goto LABEL_27;
        }
      }
      v12 = dword_180135A5C;
      if ( ((unsigned int)FwGetProfileTypeFromProfileIndex((unsigned int)i) & v12) != 0
        && (v3 || *((_BYTE *)*v8 + 12) || *((_BYTE *)*v8 + 13)) )
      {
        v3 = 1;
      }
    }
    if ( v2 < 0 || !v3 || g_hSession )
      goto LABEL_27;
    if ( g_hThread )
      MicrosoftTelemetryAssertTriggeredNoArgs(v1);
    FwDeleteProfileToIntIFMapping();
    v5 = FwConstructProfileToIntIFMapping();
    if ( v5 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 43, WPP_3d59fee1d00932d8b651bda1e8e67a3f_Traceguids, v5);
      goto LABEL_27;
    }
    if ( FwpLaunchTraceSession(v3, v6) )
    {
LABEL_27:
      FwUnlockInternal(0, "FwLoggerStart");
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
        WPP_SF_ss(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 19, v10, (unsigned int)"FwLoggerStart", (__int64)"g_Fw");
      LeaveCriticalSection(&g_FwLock);
      return;
    }
    g_fStoppingLogger = 0;
    g_hThread = CreateThread(0, 0, FwpTraceProcessingThreadRoutine, 0, 0, 0);
    if ( g_hThread )
    {
      if ( g_hDroppedEventTimer )
        MicrosoftTelemetryAssertTriggeredNoArgs(v7);
      if ( g_hTimerQueue )
        CreateTimerQueueTimer(&g_hDroppedEventTimer, g_hTimerQueue, FwpDroppedEventTimerRoutine, 0, 0, 0x493E0u, 0);
      goto LABEL_27;
    }
    FwUnlockInternal(0, "FwLoggerStart");
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
      WPP_SF_ss(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 19, v11, (unsigned int)"FwLoggerStart", (__int64)"g_Fw");
    LeaveCriticalSection(&g_FwLock);
    FwLoggerStop();
  }
}

```

## disassembly

```asm
0x180042754  push    rbx
0x180042756  push    rbp
0x180042757  push    rsi
0x180042758  push    rdi
0x180042759  push    r13
0x18004275b  push    r14
0x18004275d  sub     rsp, 48h
0x180042761  lea     rcx, ?g_FwLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180042768  call    cs:__imp_EnterCriticalSection
0x18004276f  nop     dword ptr [rax+rax+00h]
0x180042774  mov     rcx, cs:WPP_GLOBAL_Control
0x18004277b  lea     r13, WPP_GLOBAL_Control
0x180042782  lea     rbx, aGFw; "g_Fw"
0x180042789  cmp     rcx, r13
0x18004278c  jz      short loc_180042798
0x18004278e  test    byte ptr [rcx+1Ch], 4
0x180042792  jnz     loc_180042999
0x180042798  call    FwLock
0x18004279d  mov     ebp, eax
0x18004279f  test    eax, eax
0x1800427a1  js      loc_180042951
0x1800427a7  xor     esi, esi
0x1800427a9  mov     cs:?g_fTracingActive@@3EA, 1; uchar g_fTracingActive
0x1800427b0  xor     edi, edi
0x1800427b2  cmp     edi, 3
0x1800427b5  jb      loc_1800428C7
0x1800427bb  test    ebp, ebp
0x1800427bd  js      loc_18004291A
0x1800427c3  test    esi, esi
0x1800427c5  jz      loc_18004291A
0x1800427cb  cmp     cs:?g_hSession@@3_KA, 0; unsigned __int64 g_hSession
0x1800427d3  jnz     loc_18004291A
0x1800427d9  cmp     cs:?g_hThread@@3PEAXEA, 0; void * g_hThread
0x1800427e1  jnz     loc_1800429EF
0x1800427e7  call    ?FwDeleteProfileToIntIFMapping@@YAXXZ; FwDeleteProfileToIntIFMapping(void)
0x1800427ec  call    ?FwConstructProfileToIntIFMapping@@YAKXZ; FwConstructProfileToIntIFMapping(void)
0x1800427f1  test    eax, eax
0x1800427f3  jnz     loc_18004289B
0x1800427f9  mov     ecx, esi; int
0x1800427fb  call    ?FwpLaunchTraceSession@@YAKHPEA_K@Z; FwpLaunchTraceSession(int,unsigned __int64 *)
0x180042800  test    eax, eax
0x180042802  jnz     loc_18004291A
0x180042808  mov     [rsp+78h+lpThreadId], 0; lpThreadId
0x180042811  lea     r8, ?FwpTraceProcessingThreadRoutine@@YAKPEAX@Z; lpStartAddress
0x180042818  xor     r9d, r9d; lpParameter
0x18004281b  mov     [rsp+78h+dwCreationFlags], eax; dwCreationFlags
0x18004281f  xor     edx, edx; dwStackSize
0x180042821  mov     cs:?g_fStoppingLogger@@3HA, eax; int g_fStoppingLogger
0x180042827  xor     ecx, ecx; lpThreadAttributes
0x180042829  call    cs:__imp_CreateThread
0x180042830  nop     dword ptr [rax+rax+00h]
0x180042835  mov     cs:?g_hThread@@3PEAXEA, rax; void * g_hThread
0x18004283c  test    rax, rax
0x18004283f  jz      loc_18004295F
0x180042845  cmp     cs:?g_hDroppedEventTimer@@3PEAXEA, 0; void * g_hDroppedEventTimer
0x18004284d  jz      short loc_180042854
0x18004284f  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "g_hDroppedEventTimer == NULL")
0x180042854  mov     rdx, cs:?g_hTimerQueue@@3PEAXEA; TimerQueue
0x18004285b  test    rdx, rdx
0x18004285e  jz      loc_18004291A
0x180042864  mov     [rsp+78h+Flags], 0; Flags
0x18004286c  lea     r8, ?FwpDroppedEventTimerRoutine@@YAXPEAXE@Z; Callback
0x180042873  mov     dword ptr [rsp+78h+lpThreadId], 493E0h; Period
0x18004287b  lea     rcx, ?g_hDroppedEventTimer@@3PEAXEA; phNewTimer
0x180042882  xor     r9d, r9d; Parameter
0x180042885  mov     [rsp+78h+dwCreationFlags], 0; DueTime
0x18004288d  call    cs:__imp_CreateTimerQueueTimer
0x180042894  nop     dword ptr [rax+rax+00h]
0x180042899  jmp     short loc_18004291A
0x18004289b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800428a2  cmp     rcx, r13
0x1800428a5  jz      short loc_18004291A
0x1800428a7  test    byte ptr [rcx+1Ch], 1
0x1800428ab  jz      short loc_18004291A
0x1800428ad  mov     rcx, [rcx+10h]
0x1800428b1  lea     r8, WPP_3d59fee1d00932d8b651bda1e8e67a3f_Traceguids
0x1800428b8  mov     edx, 2Bh ; '+'
0x1800428bd  mov     r9d, eax
0x1800428c0  call    WPP_SF_d
0x1800428c5  jmp     short loc_18004291A
0x1800428c7  lea     rcx, ?g_pSettings@@3PAPEAUtagHNET_FW_LOGGING_SETTINGS@@A; tagHNET_FW_LOGGING_SETTINGS * near * g_pSettings
0x1800428ce  lea     r14, [rcx+rdi*8]
0x1800428d2  cmp     qword ptr [r14], 0
0x1800428d6  jnz     loc_1800429B8
0x1800428dc  mov     rdx, r14
0x1800428df  mov     ecx, edi
0x1800428e1  call    FwGetLogSettings
0x1800428e6  mov     ebp, eax
0x1800428e8  test    eax, eax
0x1800428ea  jns     loc_1800429B8
0x1800428f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800428f7  cmp     rcx, r13
0x1800428fa  jz      short loc_18004291A
0x1800428fc  test    byte ptr [rcx+1Ch], 1
0x180042900  jz      short loc_18004291A
0x180042902  mov     rcx, [rcx+10h]
0x180042906  lea     r8, WPP_3d59fee1d00932d8b651bda1e8e67a3f_Traceguids
0x18004290d  mov     edx, 2Ah ; '*'
0x180042912  mov     r9d, eax
0x180042915  call    WPP_SF_d
0x18004291a  lea     rdx, aFwloggerstart; "FwLoggerStart"
0x180042921  xor     ecx, ecx; void *
0x180042923  call    FwUnlockInternal
0x180042928  mov     rcx, cs:WPP_GLOBAL_Control
0x18004292f  cmp     rcx, r13
0x180042932  jz      short loc_18004293E
0x180042934  test    byte ptr [rcx+1Ch], 4
0x180042938  jnz     loc_180042A1F
0x18004293e  lea     rcx, ?g_FwLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180042945  call    cs:__imp_LeaveCriticalSection
0x18004294c  nop     dword ptr [rax+rax+00h]
0x180042951  add     rsp, 48h
0x180042955  pop     r14
0x180042957  pop     r13
0x180042959  pop     rdi
0x18004295a  pop     rsi
0x18004295b  pop     rbp
0x18004295c  pop     rbx
0x18004295d  retn
0x18004295f  lea     rdx, aFwloggerstart; "FwLoggerStart"
0x180042966  xor     ecx, ecx; void *
0x180042968  call    FwUnlockInternal
0x18004296d  mov     rcx, cs:WPP_GLOBAL_Control
0x180042974  cmp     rcx, r13
0x180042977  jz      short loc_18004297F
0x180042979  test    byte ptr [rcx+1Ch], 4
0x18004297d  jnz     short loc_1800429F9
0x18004297f  lea     rcx, ?g_FwLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180042986  call    cs:__imp_LeaveCriticalSection
0x18004298d  nop     dword ptr [rax+rax+00h]
0x180042992  call    FwLoggerStop
0x180042997  jmp     short loc_180042951
0x180042999  mov     rcx, [rcx+10h]
0x18004299d  lea     r9, aFwloggerstart; "FwLoggerStart"
0x1800429a4  mov     edx, 12h
0x1800429a9  mov     qword ptr [rsp+78h+dwCreationFlags], rbx
0x1800429ae  call    WPP_SF_ss
0x1800429b3  jmp     loc_180042798
0x1800429b8  mov     ebx, cs:dword_180135A5C
0x1800429be  mov     ecx, edi
0x1800429c0  call    cs:__imp_FwGetProfileTypeFromProfileIndex
0x1800429c7  nop     dword ptr [rax+rax+00h]
0x1800429cc  test    ebx, eax
0x1800429ce  jz      short loc_1800429E8
0x1800429d0  test    esi, esi
0x1800429d2  jnz     short loc_1800429E3
0x1800429d4  mov     rax, [r14]
0x1800429d7  cmp     [rax+0Ch], sil
0x1800429db  jnz     short loc_1800429E3
0x1800429dd  cmp     [rax+0Dh], sil
0x1800429e1  jz      short loc_1800429E8
0x1800429e3  mov     esi, 1
0x1800429e8  inc     edi
0x1800429ea  jmp     loc_1800427B2
0x1800429ef  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "NULL == g_hThread")
0x1800429f4  jmp     loc_1800427E7
0x1800429f9  mov     rcx, [rcx+10h]
0x1800429fd  lea     rax, aGFw; "g_Fw"
0x180042a04  mov     edx, 13h
0x180042a09  mov     qword ptr [rsp+78h+dwCreationFlags], rax
0x180042a0e  lea     r9, aFwloggerstart; "FwLoggerStart"
0x180042a15  call    WPP_SF_ss
0x180042a1a  jmp     loc_18004297F
0x180042a1f  mov     rcx, [rcx+10h]
0x180042a23  lea     rax, aGFw; "g_Fw"
0x180042a2a  mov     edx, 13h
0x180042a2f  mov     qword ptr [rsp+78h+dwCreationFlags], rax
0x180042a34  lea     r9, aFwloggerstart; "FwLoggerStart"
0x180042a3b  call    WPP_SF_ss
0x180042a40  jmp     loc_18004293E
```
