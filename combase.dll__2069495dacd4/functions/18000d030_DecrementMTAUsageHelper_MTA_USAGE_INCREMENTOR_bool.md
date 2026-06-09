# DecrementMTAUsageHelper(_MTA_USAGE_INCREMENTOR *,bool)

- ea: `0x18000d030`
- end: `0x18000d129`
- name: `?DecrementMTAUsageHelper@@YAJPEAU_MTA_USAGE_INCREMENTOR@@_N@Z`
- size: `249`
- prototype: `HRESULT __fastcall(_MTA_USAGE_INCREMENTOR *pIncrementor, bool fHostThread)`
- caller_count: `7`
- callee_count: `9`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18001c250`
- `0x1800922b4`
- `0x180092b10`
- `0x1800eda64`
- `0x18011c830`
- `0x180126b1c`
- `0x180158b00`

## callees

- `0x180006250`
- `0x180006390`
- `0x18000712c`
- `0x18000d030`
- `0x18000d130`
- `0x18000d190`
- `0x18000f72c`
- `0x1800101c8`
- `0x1800114c0`

## import_xrefs

- `ntdll!RtlIsCriticalSectionLockedByThread` at `0x18000d091`
- `ntdll!RtlIsCriticalSectionLockedByThread` at `0x18000d091`
- `ntdll!RtlDllShutdownInProgress` at `0x18000d077`
- `ntdll!RtlDllShutdownInProgress` at `0x18000d077`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d121`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d121`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000d10f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000d10f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18000d118`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18000d118`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000d103`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000d103`

## string_xrefs

- `0x18000d04e`: `onecore\com\combase\class\compobj.cxx`

## pseudocode

```c
__int64 __fastcall DecrementMTAUsageHelper(COleStaticMutexSem *pIncrementor, bool fHostThread)
{
  BOOL v2; // ebx
  __int64 v4; // rcx
  const char *v5; // r9
  unsigned int v6; // esi
  _UNINITMTAWORKERCONTEXT *v8; // r8
  void *hUninitMTADoneEvent; // rdi
  _TP_WORK *ptpWork; // rbx

  v2 = fHostThread;
  if ( COleStaticMutexSem::IsLockHeld(pIncrementor) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v4);
  COleStaticMutexSem::Request(&g_mxsSingleThreadOle, "onecore\\com\\combase\\class\\compobj.cxx", 0x57Du, v5);
  if ( (int)g_cMTAIncInits <= 0 )
  {
LABEL_4:
    CrashProcessWithWERReport();
    __debugbreak();
  }
  if ( RtlDllShutdownInProgress() )
  {
    v6 = -2147024809;
    goto LABEL_9;
  }
  if ( RtlIsCriticalSectionLockedByThread(NtCurrentPeb()->LoaderLock) )
    goto LABEL_4;
  v6 = 0;
  if ( --g_cMTAIncInits )
  {
    wCoDecrementMTAUsage();
    DecrementProcessInitializeCount();
LABEL_9:
    COleStaticMutexSem::Release(&g_mxsSingleThreadOle);
    goto LABEL_10;
  }
  v8 = g_pUninitMTAWorkerContext;
  g_pUninitMTAWorkerContext = 0;
  v8->flags |= v2;
  hUninitMTADoneEvent = v8->hUninitMTADoneEvent;
  ptpWork = v8->ptpWork;
  COleStaticMutexSem::Release(&g_mxsSingleThreadOle);
  SubmitThreadpoolWork(ptpWork);
  WaitForSingleObject(hUninitMTADoneEvent, 0xFFFFFFFF);
  CloseThreadpoolWork(ptpWork);
  CloseHandle(hUninitMTADoneEvent);
LABEL_10:
  if ( pIncrementor )
    CoTaskMemFree(pIncrementor);
  return v6;
}

```

## disassembly

```asm
0x18000d030  push    rbx
0x18000d032  push    rbp
0x18000d033  push    rsi
0x18000d034  push    rdi
0x18000d035  sub     rsp, 28h
0x18000d039  movzx   ebx, fHostThread
0x18000d03c  mov     rbp, pIncrementor
0x18000d03f  call    ?IsLockHeld@COleStaticMutexSem@@QEAA_NXZ; COleStaticMutexSem::IsLockHeld(void)
0x18000d044  test    al, al
0x18000d046  jnz     short loc_18000D070
0x18000d048  mov     r8d, 57Dh; dwLine
0x18000d04e  lea     rdx, aOnecoreComComb_154; "onecore\\com\\combase\\class\\compobj.c"...
0x18000d055  lea     pIncrementor, ?g_mxsSingleThreadOle@@3VCOleStaticMutexSem@@A; this
0x18000d05c  call    ?Request@COleStaticMutexSem@@QEAAXPEBDK0@Z; COleStaticMutexSem::Request(char const *,ulong,char const *)
0x18000d061  cmp     cs:g_cMTAIncInits, 0
0x18000d068  jg      short loc_18000D077
0x18000d06a  call    ?CrashProcessWithWERReport@@YAXXZ; CrashProcessWithWERReport(void)
0x18000d06f  int     3; Trap to Debugger
0x18000d070  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "!g_mxsSingleThreadOle.IsLockHeld()")
0x18000d075  jmp     short loc_18000D048
0x18000d077  call    cs:__imp_RtlDllShutdownInProgress
0x18000d07d  test    al, al
0x18000d07f  jnz     short loc_18000D0D4
0x18000d081  mov     pIncrementor, gs:60h
0x18000d08a  mov     pIncrementor, [pIncrementor+110h]; CriticalSection
0x18000d091  call    cs:__imp_RtlIsCriticalSectionLockedByThread
0x18000d097  test    eax, eax
0x18000d099  jnz     short loc_18000D06A
0x18000d09b  xor     esi, esi
0x18000d09d  add     cs:g_cMTAIncInits, 0FFFFFFFFh
0x18000d0a4  jz      short loc_18000D0DB
0x18000d0a6  call    ?wCoDecrementMTAUsage@@YAXXZ; wCoDecrementMTAUsage(void)
0x18000d0ab  call    ?DecrementProcessInitializeCount@@YA_NXZ; DecrementProcessInitializeCount(void)
0x18000d0b0  lea     pIncrementor, ?g_mxsSingleThreadOle@@3VCOleStaticMutexSem@@A; this
0x18000d0b7  call    ?Release@COleStaticMutexSem@@QEAAXXZ; COleStaticMutexSem::Release(void)
0x18000d0bc  test    rbp, rbp
0x18000d0bf  jz      short loc_18000D0C9
0x18000d0c1  mov     pIncrementor, rbp; pv
0x18000d0c4  call    CoTaskMemFree
0x18000d0c9  mov     eax, esi
0x18000d0cb  add     rsp, 28h
0x18000d0cf  pop     rdi
0x18000d0d0  pop     rsi
0x18000d0d1  pop     rbp
0x18000d0d2  pop     rbx
0x18000d0d3  retn
0x18000d0d4  mov     esi, 80070057h
0x18000d0d9  jmp     short loc_18000D0B0
0x18000d0db  mov     r8, cs:?g_pUninitMTAWorkerContext@@3PEAU_UNINITMTAWORKERCONTEXT@@EA; _UNINITMTAWORKERCONTEXT * g_pUninitMTAWorkerContext
0x18000d0e2  lea     pIncrementor, ?g_mxsSingleThreadOle@@3VCOleStaticMutexSem@@A; this
0x18000d0e9  mov     cs:?g_pUninitMTAWorkerContext@@3PEAU_UNINITMTAWORKERCONTEXT@@EA, rsi; _UNINITMTAWORKERCONTEXT * g_pUninitMTAWorkerContext
0x18000d0f0  or      [r8+18h], ebx
0x18000d0f4  mov     rdi, [r8]
0x18000d0f7  mov     rbx, [r8+10h]
0x18000d0fb  call    ?Release@COleStaticMutexSem@@QEAAXXZ; COleStaticMutexSem::Release(void)
0x18000d100  mov     pIncrementor, rbx; pwk
0x18000d103  call    cs:__imp_SubmitThreadpoolWork
0x18000d109  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18000d10c  mov     pIncrementor, rdi; hHandle
0x18000d10f  call    cs:__imp_WaitForSingleObject
0x18000d115  mov     pIncrementor, rbx; pwk
0x18000d118  call    cs:__imp_CloseThreadpoolWork
0x18000d11e  mov     pIncrementor, rdi; hObject
0x18000d121  call    cs:__imp_CloseHandle
0x18000d127  jmp     short loc_18000D0BC
```
