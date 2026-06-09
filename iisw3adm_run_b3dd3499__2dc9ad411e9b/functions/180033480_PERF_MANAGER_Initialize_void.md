# PERF_MANAGER::Initialize(void)

- ea: `0x180033480`
- end: `0x18003365f`
- name: `?Initialize@PERF_MANAGER@@QEAAJXZ`
- size: `479`
- prototype: `__int64 __fastcall(PERF_MANAGER *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001d018`

## callees

- `0x180032728`
- `0x180032af8`
- `0x180032d44`
- `0x180033480`
- `0x18005d834`
- `0x18005d8e8`
- `0x18005dc20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003357b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003357b`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18003356c`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18003356c`
- `iisutil!PuDbgPrint` at `0x18003364e`
- `iisutil!PuDbgPrint` at `0x18003364e`
- `iisutil!PuDbgPrintError` at `0x1800335c0`
- `iisutil!PuDbgPrintError` at `0x1800335fa`
- `iisutil!PuDbgPrintError` at `0x1800335c0`
- `iisutil!PuDbgPrintError` at `0x1800335fa`

## string_xrefs

- `0x180033498`: `servercommon\inetsrv\iis\iisrearc\core\ap\was\dll\perf_manager.cxx`
- `0x18003353a`: `Failed to adjust process security thread \n`
- `0x1800335d3`: `Failed to launch the perf counter waiting thread \n`
- `0x1800335a0`: `Could not spin up thread to wait for event\n`
- `0x1800335ac`: `PERF_MANAGER::LaunchPerfCounterWaitingThread`

## pseudocode

```c
__int64 __fastcall PERF_MANAGER::Initialize(PERF_MANAGER *this, int a2)
{
  char *v2; // rsi
  signed int NewCounterSet; // eax
  signed int v5; // ebx
  bool v6; // cc
  HANDLE Thread; // rax
  signed int LastError; // eax

  v2 = (char *)this + 24;
  NewCounterSet = PERF_SM_MANAGER::Initialize((PERF_MANAGER *)((char *)this + 24), a2);
  v5 = NewCounterSet;
  v6 = NewCounterSet <= 0;
  if ( !NewCounterSet )
  {
    NewCounterSet = PERF_SM_MANAGER::CreateNewCounterSet(v2, 0);
    v5 = NewCounterSet;
    v6 = NewCounterSet <= 0;
    if ( !NewCounterSet )
    {
      NewCounterSet = PERF_SM_MANAGER::CreateNewCounterSet(v2, 1);
      v5 = NewCounterSet;
      v6 = NewCounterSet <= 0;
      if ( !NewCounterSet )
      {
        v5 = PERF_SM_MANAGER::ReallocSharedMemIfNeccessary(v2, 1, 1);
        if ( v5 >= 0 )
        {
          *((_DWORD *)this + 3) = 3;
          PERF_MANAGER::CompleteCounterUpdate(this);
          v5 = AdjustProcessSecurityToAllowPowerUsersToWait();
          if ( v5 >= 0 )
          {
            v5 = 0;
            Thread = CreateThread(0, 0x8000u, PerfCountPing, this, 0, (LPDWORD)this + 30);
            *((_QWORD *)this + 14) = Thread;
            if ( !Thread )
            {
              LastError = GetLastError();
              v5 = LastError;
              if ( LastError > 0 )
                v5 = (unsigned __int16)LastError | 0x80070000;
              if ( (g_dwDebugFlags & 0xF) != 0 )
                PuDbgPrintError(
                  g_pDebug,
                  "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\perf_manager.cxx",
                  1441,
                  "PERF_MANAGER::LaunchPerfCounterWaitingThread",
                  v5,
                  "Could not spin up thread to wait for event\n");
            }
            if ( v5 >= 0 )
            {
              PERF_MANAGER::BeginPerfCounterTimer(this);
              goto LABEL_24;
            }
            if ( (g_dwDebugFlags & 0xF) != 0 )
              PuDbgPrintError(
                g_pDebug,
                "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\perf_manager.cxx",
                659,
                "PERF_MANAGER::Initialize",
                v5,
                "Failed to launch the perf counter waiting thread \n");
          }
          else if ( (g_dwDebugFlags & 0xF) != 0 )
          {
            PuDbgPrintError(
              g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\perf_manager.cxx",
              643,
              "PERF_MANAGER::Initialize",
              v5,
              "Failed to adjust process security thread \n");
          }
        }
        else if ( (g_dwDebugFlags & 0xF) != 0 )
        {
          PuDbgPrintError(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\perf_manager.cxx",
            616,
            "PERF_MANAGER::Initialize",
            v5,
            "Error allocating global shared memory. Turning off perf counter publishing, you must restart w3svc to reactivate them\n");
        }
LABEL_22:
        *((_DWORD *)this + 3) = 1;
        goto LABEL_24;
      }
    }
  }
  if ( !v6 )
    v5 = (unsigned __int16)NewCounterSet | 0x80070000;
  if ( v5 < 0 )
    goto LABEL_22;
LABEL_24:
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x2000000) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\ap\\was\\dll\\perf_manager.cxx",
      685,
      "PERF_MANAGER::Initialize",
      "Initializing the Perf Manager is returning: %x\n",
      v5);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180033480  push    rbx
0x180033482  push    rbp
0x180033483  push    rsi
0x180033484  push    rdi
0x180033485  sub     rsp, 38h
0x180033489  lea     rsi, [rcx+18h]
0x18003348d  mov     rdi, rcx
0x180033490  mov     rcx, rsi; this
0x180033493  call    ?Initialize@PERF_SM_MANAGER@@QEAAKH@Z; PERF_SM_MANAGER::Initialize(int)
0x180033498  lea     rbp, aServercommonIn_15; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18003349f  mov     ebx, eax
0x1800334a1  test    eax, eax
0x1800334a3  jnz     short loc_1800334C6
0x1800334a5  xor     edx, edx
0x1800334a7  mov     rcx, rsi
0x1800334aa  call    ?CreateNewCounterSet@PERF_SM_MANAGER@@QEAAKW4_COUNTER_SET_ENUM@@@Z; PERF_SM_MANAGER::CreateNewCounterSet(_COUNTER_SET_ENUM)
0x1800334af  mov     ebx, eax
0x1800334b1  test    eax, eax
0x1800334b3  jnz     short loc_1800334C6
0x1800334b5  lea     edx, [rax+1]
0x1800334b8  mov     rcx, rsi
0x1800334bb  call    ?CreateNewCounterSet@PERF_SM_MANAGER@@QEAAKW4_COUNTER_SET_ENUM@@@Z; PERF_SM_MANAGER::CreateNewCounterSet(_COUNTER_SET_ENUM)
0x1800334c0  mov     ebx, eax
0x1800334c2  test    eax, eax
0x1800334c4  jz      short loc_1800334DE
0x1800334c6  jle     short loc_1800334D1
0x1800334c8  movzx   ebx, ax
0x1800334cb  or      ebx, 80070000h
0x1800334d1  test    ebx, ebx
0x1800334d3  js      loc_180033600
0x1800334d9  jmp     loc_180033611
0x1800334de  mov     edx, 1
0x1800334e3  mov     rcx, rsi
0x1800334e6  mov     r8d, edx
0x1800334e9  call    ?ReallocSharedMemIfNeccessary@PERF_SM_MANAGER@@QEAAJW4_COUNTER_SET_ENUM@@K@Z; PERF_SM_MANAGER::ReallocSharedMemIfNeccessary(_COUNTER_SET_ENUM,ulong)
0x1800334ee  mov     ebx, eax
0x1800334f0  test    eax, eax
0x1800334f2  jns     short loc_180033513
0x1800334f4  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800334fb  jz      loc_180033600
0x180033501  lea     rax, aErrorAllocatin; "Error allocating global shared memory. "...
0x180033508  mov     r8d, 268h
0x18003350e  jmp     loc_1800335E0
0x180033513  mov     rcx, rdi; this
0x180033516  mov     dword ptr [rdi+0Ch], 3
0x18003351d  call    ?CompleteCounterUpdate@PERF_MANAGER@@AEAAXXZ; PERF_MANAGER::CompleteCounterUpdate(void)
0x180033522  call    ?AdjustProcessSecurityToAllowPowerUsersToWait@@YAJXZ; AdjustProcessSecurityToAllowPowerUsersToWait(void)
0x180033527  mov     ebx, eax
0x180033529  test    eax, eax
0x18003352b  jns     short loc_18003354C
0x18003352d  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180033534  jz      loc_180033600
0x18003353a  lea     rax, aFailedToAdjust; "Failed to adjust process security threa"...
0x180033541  mov     r8d, 283h
0x180033547  jmp     loc_1800335E0
0x18003354c  lea     rax, [rdi+78h]
0x180033550  xor     ebx, ebx
0x180033552  mov     [rsp+58h+lpThreadId], rax; lpThreadId
0x180033557  lea     r8, ?PerfCountPing@@YAKPEAX@Z; lpStartAddress
0x18003355e  mov     r9, rdi; lpParameter
0x180033561  mov     [rsp+58h+dwCreationFlags], ebx; dwCreationFlags
0x180033565  mov     edx, 8000h; dwStackSize
0x18003356a  xor     ecx, ecx; lpThreadAttributes
0x18003356c  call    cs:__imp_CreateThread
0x180033572  mov     [rdi+70h], rax
0x180033576  test    rax, rax
0x180033579  jnz     short loc_1800335C6
0x18003357b  call    cs:__imp_GetLastError
0x180033581  mov     ebx, eax
0x180033583  test    eax, eax
0x180033585  jle     short loc_180033590
0x180033587  movzx   ebx, ax
0x18003358a  or      ebx, 80070000h
0x180033590  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180033597  jz      short loc_1800335C6
0x180033599  mov     rcx, cs:g_pDebug
0x1800335a0  lea     rax, aCouldNotSpinUp; "Could not spin up thread to wait for ev"...
0x1800335a7  mov     [rsp+58h+lpThreadId], rax
0x1800335ac  lea     r9, aPerfManagerLau; "PERF_MANAGER::LaunchPerfCounterWaitingT"...
0x1800335b3  mov     r8d, 5A1h
0x1800335b9  mov     [rsp+58h+dwCreationFlags], ebx
0x1800335bd  mov     rdx, rbp
0x1800335c0  call    cs:__imp_PuDbgPrintError
0x1800335c6  test    ebx, ebx
0x1800335c8  jns     short loc_180033609
0x1800335ca  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800335d1  jz      short loc_180033600
0x1800335d3  lea     rax, aFailedToLaunch_0; "Failed to launch the perf counter waiti"...
0x1800335da  mov     r8d, 293h
0x1800335e0  mov     rcx, cs:g_pDebug
0x1800335e7  lea     r9, aPerfManagerIni; "PERF_MANAGER::Initialize"
0x1800335ee  mov     [rsp+58h+lpThreadId], rax
0x1800335f3  mov     rdx, rbp
0x1800335f6  mov     [rsp+58h+dwCreationFlags], ebx
0x1800335fa  call    cs:__imp_PuDbgPrintError
0x180033600  mov     dword ptr [rdi+0Ch], 1
0x180033607  jmp     short loc_180033611
0x180033609  mov     rcx, rdi; this
0x18003360c  call    ?BeginPerfCounterTimer@PERF_MANAGER@@AEAAXXZ; PERF_MANAGER::BeginPerfCounterTimer(void)
0x180033611  mov     eax, cs:g_dwDebugFlags
0x180033617  test    al, 3
0x180033619  setnz   cl
0x18003361c  bt      eax, 19h
0x180033620  setb    al
0x180033623  test    al, cl
0x180033625  jz      short loc_180033654
0x180033627  mov     rcx, cs:g_pDebug
0x18003362e  lea     rax, aInitializingTh; "Initializing the Perf Manager is return"...
0x180033635  mov     dword ptr [rsp+58h+lpThreadId], ebx
0x180033639  lea     r9, aPerfManagerIni; "PERF_MANAGER::Initialize"
0x180033640  mov     r8d, 2ADh
0x180033646  mov     qword ptr [rsp+58h+dwCreationFlags], rax
0x18003364b  mov     rdx, rbp
0x18003364e  call    cs:__imp_PuDbgPrint
0x180033654  mov     eax, ebx
0x180033656  add     rsp, 38h
0x18003365a  pop     rdi
0x18003365b  pop     rsi
0x18003365c  pop     rbp
0x18003365d  pop     rbx
0x18003365e  retn
```
