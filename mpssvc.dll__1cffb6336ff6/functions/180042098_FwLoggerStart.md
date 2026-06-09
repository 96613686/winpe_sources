# FwLoggerStart

- ea: `0x180042098`
- end: `0x180042364`
- name: `FwLoggerStart`
- size: `716`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18006a7e0`
- `0x180094570`

## callees

- `0x1800093b0`
- `0x180009460`
- `0x18000a0c0`
- `0x18000af3c`
- `0x180042098`
- `0x18004236c`
- `0x180042f74`
- `0x180042fec`
- `0x18006ac80`
- `0x18006bbe0`
- `0x180079750`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180042167`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180042167`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180042277`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800422b1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180042277`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800422b1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800420ac`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800420ac`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x1800421c5`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x1800421c5`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x1800422e5`
- `fwbase!FwGetProfileTypeFromProfileIndex` at `0x1800422e5`

## pseudocode

```c
void FwLoggerStart()
{
  int v0; // r8d
  __int64 v1; // rdx
  __int64 v2; // rcx
  int v3; // ebp
  __int64 v4; // r8
  __int64 v5; // r9
  int v6; // esi
  __int64 i; // rdi
  unsigned int v8; // eax
  unsigned __int64 *v9; // rdx
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 v13; // r9
  struct tagHNET_FW_LOGGING_SETTINGS * near **v14; // r14
  int LogSettings; // eax
  int v16; // r8d
  int v17; // r8d
  int v18; // ebx

  EnterCriticalSection(&g_FwLock);
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    WPP_SF_ss(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 18, v0, (unsigned int)"FwLoggerStart", (__int64)"g_Fw");
  v3 = FwLock();
  if ( v3 >= 0 )
  {
    v6 = 0;
    g_fTracingActive = 1;
    for ( i = 0; (unsigned int)i < 3; i = (unsigned int)(i + 1) )
    {
      v14 = &(&g_pSettings)[i];
      if ( !*v14 )
      {
        LogSettings = FwGetLogSettings((unsigned int)i, &(&g_pSettings)[i]);
        v3 = LogSettings;
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
      v18 = dword_18012F89C;
      if ( ((unsigned int)FwGetProfileTypeFromProfileIndex((unsigned int)i) & v18) != 0
        && (v6 || *((_BYTE *)*v14 + 12) || *((_BYTE *)*v14 + 13)) )
      {
        v6 = 1;
      }
    }
    if ( v3 < 0 || !v6 || g_hSession )
      goto LABEL_27;
    if ( g_hThread )
      MicrosoftTelemetryAssertTriggeredNoArgs(v2, v1, v4, v5);
    FwDeleteProfileToIntIFMapping();
    v8 = FwConstructProfileToIntIFMapping();
    if ( v8 )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 43, WPP_3d59fee1d00932d8b651bda1e8e67a3f_Traceguids, v8);
      goto LABEL_27;
    }
    if ( FwpLaunchTraceSession(v6, v9) )
    {
LABEL_27:
      FwUnlockInternal(0, "FwLoggerStart");
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
        WPP_SF_ss(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 19, v16, (unsigned int)"FwLoggerStart", (__int64)"g_Fw");
      LeaveCriticalSection(&g_FwLock);
      return;
    }
    g_fStoppingLogger = 0;
    g_hThread = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)FwpTraceProcessingThreadRoutine, 0, 0, 0);
    if ( g_hThread )
    {
      if ( g_hDroppedEventTimer )
        MicrosoftTelemetryAssertTriggeredNoArgs(v11, v10, v12, v13);
      if ( g_hTimerQueue )
        CreateTimerQueueTimer(&g_hDroppedEventTimer, g_hTimerQueue, FwpDroppedEventTimerRoutine, 0, 0, 0x493E0u, 0);
      goto LABEL_27;
    }
    FwUnlockInternal(0, "FwLoggerStart");
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
      WPP_SF_ss(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 19, v17, (unsigned int)"FwLoggerStart", (__int64)"g_Fw");
    LeaveCriticalSection(&g_FwLock);
    FwLoggerStop();
  }
}

```

## disassembly

```asm
0x180042098  push    rbx
0x18004209a  push    rbp
0x18004209b  push    rsi
0x18004209c  push    rdi
0x18004209d  push    r13
0x18004209f  push    r14
0x1800420a1  sub     rsp, 48h
0x1800420a5  lea     rcx, ?g_FwLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800420ac  call    cs:__imp_EnterCriticalSection
0x1800420b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800420b9  lea     r13, WPP_GLOBAL_Control
0x1800420c0  lea     rbx, aGFw; "g_Fw"
0x1800420c7  cmp     rcx, r13
0x1800420ca  jz      short loc_1800420D6
0x1800420cc  test    byte ptr [rcx+1Ch], 4
0x1800420d0  jnz     loc_1800422BE
0x1800420d6  call    FwLock
0x1800420db  mov     ebp, eax
0x1800420dd  test    eax, eax
0x1800420df  js      loc_18004227D
0x1800420e5  xor     esi, esi
0x1800420e7  mov     cs:?g_fTracingActive@@3EA, 1; uchar g_fTracingActive
0x1800420ee  xor     edi, edi
0x1800420f0  cmp     edi, 3
0x1800420f3  jb      loc_1800421F9
0x1800420f9  test    ebp, ebp
0x1800420fb  js      loc_18004224C
0x180042101  test    esi, esi
0x180042103  jz      loc_18004224C
0x180042109  cmp     cs:?g_hSession@@3_KA, 0; unsigned __int64 g_hSession
0x180042111  jnz     loc_18004224C
0x180042117  cmp     cs:?g_hThread@@3PEAXEA, 0; void * g_hThread
0x18004211f  jnz     loc_18004230E
0x180042125  call    ?FwDeleteProfileToIntIFMapping@@YAXXZ; FwDeleteProfileToIntIFMapping(void)
0x18004212a  call    ?FwConstructProfileToIntIFMapping@@YAKXZ; FwConstructProfileToIntIFMapping(void)
0x18004212f  test    eax, eax
0x180042131  jnz     loc_1800421CD
0x180042137  mov     ecx, esi; int
0x180042139  call    ?FwpLaunchTraceSession@@YAKHPEA_K@Z; FwpLaunchTraceSession(int,unsigned __int64 *)
0x18004213e  test    eax, eax
0x180042140  jnz     loc_18004224C
0x180042146  mov     [rsp+78h+lpThreadId], 0; lpThreadId
0x18004214f  lea     r8, ?FwpTraceProcessingThreadRoutine@@YAKPEAX@Z; lpStartAddress
0x180042156  xor     r9d, r9d; lpParameter
0x180042159  mov     [rsp+78h+dwCreationFlags], eax; dwCreationFlags
0x18004215d  xor     edx, edx; dwStackSize
0x18004215f  mov     cs:?g_fStoppingLogger@@3HA, eax; int g_fStoppingLogger
0x180042165  xor     ecx, ecx; lpThreadAttributes
0x180042167  call    cs:__imp_CreateThread
0x18004216d  mov     cs:?g_hThread@@3PEAXEA, rax; void * g_hThread
0x180042174  test    rax, rax
0x180042177  jz      loc_18004228A
0x18004217d  cmp     cs:?g_hDroppedEventTimer@@3PEAXEA, 0; void * g_hDroppedEventTimer
0x180042185  jz      short loc_18004218C
0x180042187  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18004218c  mov     rdx, cs:?g_hTimerQueue@@3PEAXEA; TimerQueue
0x180042193  test    rdx, rdx
0x180042196  jz      loc_18004224C
0x18004219c  mov     [rsp+78h+Flags], 0; Flags
0x1800421a4  lea     r8, ?FwpDroppedEventTimerRoutine@@YAXPEAXE@Z; Callback
0x1800421ab  mov     dword ptr [rsp+78h+lpThreadId], 493E0h; Period
0x1800421b3  lea     rcx, ?g_hDroppedEventTimer@@3PEAXEA; phNewTimer
0x1800421ba  xor     r9d, r9d; Parameter
0x1800421bd  mov     [rsp+78h+dwCreationFlags], 0; DueTime
0x1800421c5  call    cs:__imp_CreateTimerQueueTimer
0x1800421cb  jmp     short loc_18004224C
0x1800421cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800421d4  cmp     rcx, r13
0x1800421d7  jz      short loc_18004224C
0x1800421d9  test    byte ptr [rcx+1Ch], 1
0x1800421dd  jz      short loc_18004224C
0x1800421df  mov     rcx, [rcx+10h]
0x1800421e3  lea     r8, WPP_3d59fee1d00932d8b651bda1e8e67a3f_Traceguids
0x1800421ea  mov     edx, 2Bh ; '+'
0x1800421ef  mov     r9d, eax
0x1800421f2  call    WPP_SF_d
0x1800421f7  jmp     short loc_18004224C
0x1800421f9  lea     rcx, ?g_pSettings@@3PAPEAUtagHNET_FW_LOGGING_SETTINGS@@A; tagHNET_FW_LOGGING_SETTINGS * near * g_pSettings
0x180042200  lea     r14, [rcx+rdi*8]
0x180042204  cmp     qword ptr [r14], 0
0x180042208  jnz     loc_1800422DD
0x18004220e  mov     rdx, r14
0x180042211  mov     ecx, edi
0x180042213  call    FwGetLogSettings
0x180042218  mov     ebp, eax
0x18004221a  test    eax, eax
0x18004221c  jns     loc_1800422DD
0x180042222  mov     rcx, cs:WPP_GLOBAL_Control
0x180042229  cmp     rcx, r13
0x18004222c  jz      short loc_18004224C
0x18004222e  test    byte ptr [rcx+1Ch], 1
0x180042232  jz      short loc_18004224C
0x180042234  mov     rcx, [rcx+10h]
0x180042238  lea     r8, WPP_3d59fee1d00932d8b651bda1e8e67a3f_Traceguids
0x18004223f  mov     edx, 2Ah ; '*'
0x180042244  mov     r9d, eax
0x180042247  call    WPP_SF_d
0x18004224c  lea     rdx, aFwloggerstart; "FwLoggerStart"
0x180042253  xor     ecx, ecx; void *
0x180042255  call    FwUnlockInternal
0x18004225a  mov     rcx, cs:WPP_GLOBAL_Control
0x180042261  cmp     rcx, r13
0x180042264  jz      short loc_180042270
0x180042266  test    byte ptr [rcx+1Ch], 4
0x18004226a  jnz     loc_18004233E
0x180042270  lea     rcx, ?g_FwLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180042277  call    cs:__imp_LeaveCriticalSection
0x18004227d  add     rsp, 48h
0x180042281  pop     r14
0x180042283  pop     r13
0x180042285  pop     rdi
0x180042286  pop     rsi
0x180042287  pop     rbp
0x180042288  pop     rbx
0x180042289  retn
0x18004228a  lea     rdx, aFwloggerstart; "FwLoggerStart"
0x180042291  xor     ecx, ecx; void *
0x180042293  call    FwUnlockInternal
0x180042298  mov     rcx, cs:WPP_GLOBAL_Control
0x18004229f  cmp     rcx, r13
0x1800422a2  jz      short loc_1800422AA
0x1800422a4  test    byte ptr [rcx+1Ch], 4
0x1800422a8  jnz     short loc_180042318
0x1800422aa  lea     rcx, ?g_FwLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800422b1  call    cs:__imp_LeaveCriticalSection
0x1800422b7  call    FwLoggerStop
0x1800422bc  jmp     short loc_18004227D
0x1800422be  mov     rcx, [rcx+10h]
0x1800422c2  lea     r9, aFwloggerstart; "FwLoggerStart"
0x1800422c9  mov     edx, 12h
0x1800422ce  mov     qword ptr [rsp+78h+dwCreationFlags], rbx
0x1800422d3  call    WPP_SF_ss
0x1800422d8  jmp     loc_1800420D6
0x1800422dd  mov     ebx, cs:dword_18012F89C
0x1800422e3  mov     ecx, edi
0x1800422e5  call    cs:__imp_FwGetProfileTypeFromProfileIndex
0x1800422eb  test    ebx, eax
0x1800422ed  jz      short loc_180042307
0x1800422ef  test    esi, esi
0x1800422f1  jnz     short loc_180042302
0x1800422f3  mov     rax, [r14]
0x1800422f6  cmp     [rax+0Ch], sil
0x1800422fa  jnz     short loc_180042302
0x1800422fc  cmp     [rax+0Dh], sil
0x180042300  jz      short loc_180042307
0x180042302  mov     esi, 1
0x180042307  inc     edi
0x180042309  jmp     loc_1800420F0
0x18004230e  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180042313  jmp     loc_180042125
0x180042318  mov     rcx, [rcx+10h]
0x18004231c  lea     rax, aGFw; "g_Fw"
0x180042323  mov     edx, 13h
0x180042328  mov     qword ptr [rsp+78h+dwCreationFlags], rax
0x18004232d  lea     r9, aFwloggerstart; "FwLoggerStart"
0x180042334  call    WPP_SF_ss
0x180042339  jmp     loc_1800422AA
0x18004233e  mov     rcx, [rcx+10h]
0x180042342  lea     rax, aGFw; "g_Fw"
0x180042349  mov     edx, 13h
0x18004234e  mov     qword ptr [rsp+78h+dwCreationFlags], rax
0x180042353  lea     r9, aFwloggerstart; "FwLoggerStart"
0x18004235a  call    WPP_SF_ss
0x18004235f  jmp     loc_180042270
```
