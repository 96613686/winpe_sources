# PERF_SM_MANAGER::EvaluateIfCountersAreFresh(void)

- ea: `0x180002648`
- end: `0x1800027f0`
- name: `?EvaluateIfCountersAreFresh@PERF_SM_MANAGER@@QEAAHXZ`
- size: `424`
- prototype: `__int64 __fastcall(PERF_SM_MANAGER *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180002024`

## callees

- `0x180002648`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180002759`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180002759`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002663`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000271b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002790`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002663`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000271b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002790`
- `iisutil!PuDbgPrint` at `0x1800026d6`
- `iisutil!PuDbgPrint` at `0x180002750`
- `iisutil!PuDbgPrint` at `0x1800027cf`
- `iisutil!PuDbgPrint` at `0x1800026d6`
- `iisutil!PuDbgPrint` at `0x180002750`
- `iisutil!PuDbgPrint` at `0x1800027cf`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800026f4`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800026f4`

## string_xrefs

- `0x1800026a3`: `servercommon\inetsrv\iis\iisrearc\core\prfshmem\perf_sm.cxx`
- `0x180002733`: `servercommon\inetsrv\iis\iisrearc\core\prfshmem\perf_sm.cxx`
- `0x1800027a5`: `servercommon\inetsrv\iis\iisrearc\core\prfshmem\perf_sm.cxx`
- `0x1800026c1`: `Evaluating if we need to refresh counters.  \nNumberOfTickCountsPassed = %d; \nLastUpdatedTickCount starts = %d \nMillisecondsCountersAreFresh = %d; \nMaxNumberTimesToCheckCountersOnRefresh = %d \nMillisecondsToSleepBeforeCheckingForRefresh = %d \n\n`

## pseudocode

```c
_BOOL8 __fastcall PERF_SM_MANAGER::EvaluateIfCountersAreFresh(PERF_SM_MANAGER *this)
{
  unsigned int v2; // r15d
  DWORD TickCount; // eax
  _DWORD *v4; // rdi
  unsigned int v5; // ebp
  int v6; // edx
  void *v7; // rcx
  int v8; // ebx
  DWORD v9; // eax
  DWORD v10; // eax

  v2 = *(_DWORD *)(*((_QWORD *)this + 2) + 4104LL);
  TickCount = GetTickCount();
  v4 = (_DWORD *)((char *)this + 76);
  v5 = TickCount - v2 - 1;
  if ( TickCount >= v2 )
    v5 = TickCount - v2;
  v6 = g_dwDebugFlags;
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x2000000) != 0 )
  {
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\prfshmem\\perf_sm.cxx",
      1114,
      "PERF_SM_MANAGER::EvaluateIfCountersAreFresh",
      "Evaluating if we need to refresh counters.  \n"
      "NumberOfTickCountsPassed = %d; \n"
      "LastUpdatedTickCount starts = %d \n"
      "MillisecondsCountersAreFresh = %d; \n"
      "MaxNumberTimesToCheckCountersOnRefresh = %d \n"
      "MillisecondsToSleepBeforeCheckingForRefresh = %d \n"
      "\n",
      v5,
      v2,
      *((_DWORD *)this + 18),
      *v4,
      *((_DWORD *)this + 20));
    v6 = g_dwDebugFlags;
  }
  if ( v5 <= *((_DWORD *)this + 18) )
    return 1;
  v7 = (void *)*((_QWORD *)this + 6);
  if ( v7 )
  {
    SetEvent(v7);
    v6 = g_dwDebugFlags;
  }
  v8 = 0;
  if ( *v4 )
  {
    while ( 1 )
    {
      if ( (v6 & 3) != 0 && (v6 & 0x2000000) != 0 )
      {
        v9 = GetTickCount();
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\prfshmem\\perf_sm.cxx",
          1136,
          "PERF_SM_MANAGER::EvaluateIfCountersAreFresh",
          "Waiting for the %d time  \nCurrentTickCount is = %d \n\n",
          v8,
          v9);
      }
      Sleep(*((_DWORD *)this + 20));
      if ( *(_DWORD *)(*((_QWORD *)this + 2) + 4104LL) != v2 )
        break;
      if ( (unsigned int)++v8 >= *v4 )
        return v8 != *v4;
      v6 = g_dwDebugFlags;
    }
    if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x2000000) != 0 )
    {
      v10 = GetTickCount();
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\prfshmem\\perf_sm.cxx",
        1150,
        "PERF_SM_MANAGER::EvaluateIfCountersAreFresh",
        "Finished waiting, tick count is now set to %d \nCurrentTickCount is = %d \n\n",
        *(_DWORD *)(*((_QWORD *)this + 2) + 4104LL),
        v10);
    }
  }
  return v8 != *v4;
}

```

## disassembly

```asm
0x180002648  push    rbx
0x18000264a  push    rbp
0x18000264b  push    rsi
0x18000264c  push    rdi
0x18000264d  push    r14
0x18000264f  push    r15
0x180002651  sub     rsp, 58h
0x180002655  mov     rax, [rcx+10h]
0x180002659  mov     rsi, rcx
0x18000265c  mov     r15d, [rax+1008h]
0x180002663  call    cs:__imp_GetTickCount
0x180002669  mov     edx, eax
0x18000266b  lea     rdi, [rsi+4Ch]
0x18000266f  sub     edx, r15d
0x180002672  cmp     eax, r15d
0x180002675  lea     ebp, [rdx-1]
0x180002678  cmovnb  ebp, edx
0x18000267b  mov     edx, cs:g_dwDebugFlags
0x180002681  test    dl, 3
0x180002684  setnz   cl
0x180002687  bt      edx, 19h
0x18000268b  setb    al
0x18000268e  test    al, cl
0x180002690  jz      short loc_1800026E2
0x180002692  mov     eax, [rsi+50h]
0x180002695  lea     r9, aPerfSmManagerE; "PERF_SM_MANAGER::EvaluateIfCountersAreF"...
0x18000269c  mov     rcx, cs:g_pDebug
0x1800026a3  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800026aa  mov     [rsp+88h+var_40], eax
0x1800026ae  mov     r8d, 45Ah
0x1800026b4  mov     eax, [rdi]
0x1800026b6  mov     [rsp+88h+var_48], eax
0x1800026ba  mov     eax, [rsi+48h]
0x1800026bd  mov     [rsp+88h+var_50], eax
0x1800026c1  lea     rax, aEvaluatingIfWe; "Evaluating if we need to refresh counte"...
0x1800026c8  mov     [rsp+88h+var_58], r15d
0x1800026cd  mov     [rsp+88h+var_60], ebp
0x1800026d1  mov     [rsp+88h+var_68], rax
0x1800026d6  call    cs:__imp_PuDbgPrint
0x1800026dc  mov     edx, cs:g_dwDebugFlags
0x1800026e2  cmp     ebp, [rsi+48h]
0x1800026e5  jbe     loc_1800027DE
0x1800026eb  mov     rcx, [rsi+30h]; hEvent
0x1800026ef  test    rcx, rcx
0x1800026f2  jz      short loc_180002700
0x1800026f4  call    cs:__imp_SetEvent
0x1800026fa  mov     edx, cs:g_dwDebugFlags
0x180002700  xor     ebx, ebx
0x180002702  cmp     [rdi], ebx
0x180002704  jbe     loc_1800027D5
0x18000270a  test    dl, 3
0x18000270d  setnz   cl
0x180002710  bt      edx, 19h
0x180002714  setb    al
0x180002717  test    al, cl
0x180002719  jz      short loc_180002756
0x18000271b  call    cs:__imp_GetTickCount
0x180002721  mov     rcx, cs:g_pDebug
0x180002728  lea     r9, aPerfSmManagerE; "PERF_SM_MANAGER::EvaluateIfCountersAreF"...
0x18000272f  mov     [rsp+88h+var_58], eax
0x180002733  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000273a  lea     rax, aWaitingForTheD; "Waiting for the %d time  \nCurrentTickC"...
0x180002741  mov     [rsp+88h+var_60], ebx
0x180002745  mov     r8d, 470h
0x18000274b  mov     [rsp+88h+var_68], rax
0x180002750  call    cs:__imp_PuDbgPrint
0x180002756  mov     ecx, [rsi+50h]; dwMilliseconds
0x180002759  call    cs:__imp_Sleep
0x18000275f  mov     rax, [rsi+10h]
0x180002763  cmp     [rax+1008h], r15d
0x18000276a  jnz     short loc_18000277A
0x18000276c  inc     ebx
0x18000276e  cmp     ebx, [rdi]
0x180002770  jnb     short loc_1800027D5
0x180002772  mov     edx, cs:g_dwDebugFlags
0x180002778  jmp     short loc_18000270A
0x18000277a  mov     eax, cs:g_dwDebugFlags
0x180002780  test    al, 3
0x180002782  setnz   cl
0x180002785  bt      eax, 19h
0x180002789  setb    al
0x18000278c  test    al, cl
0x18000278e  jz      short loc_1800027D5
0x180002790  call    cs:__imp_GetTickCount
0x180002796  mov     rcx, [rsi+10h]
0x18000279a  lea     r9, aPerfSmManagerE; "PERF_SM_MANAGER::EvaluateIfCountersAreF"...
0x1800027a1  mov     [rsp+88h+var_58], eax
0x1800027a5  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800027ac  mov     r8d, 47Eh
0x1800027b2  mov     eax, [rcx+1008h]
0x1800027b8  mov     rcx, cs:g_pDebug
0x1800027bf  mov     [rsp+88h+var_60], eax
0x1800027c3  lea     rax, aFinishedWaitin; "Finished waiting, tick count is now set"...
0x1800027ca  mov     [rsp+88h+var_68], rax
0x1800027cf  call    cs:__imp_PuDbgPrint
0x1800027d5  xor     eax, eax
0x1800027d7  cmp     ebx, [rdi]
0x1800027d9  setnz   al
0x1800027dc  jmp     short loc_1800027E3
0x1800027de  mov     eax, 1
0x1800027e3  add     rsp, 58h
0x1800027e7  pop     r15
0x1800027e9  pop     r14
0x1800027eb  pop     rdi
0x1800027ec  pop     rsi
0x1800027ed  pop     rbp
0x1800027ee  pop     rbx
0x1800027ef  retn
```
