# FREB_REQUEST_CONTEXT::WriteTraceEventsToFile(ushort const *)

- ea: `0x180005588`
- end: `0x1800057f1`
- name: `?WriteTraceEventsToFile@FREB_REQUEST_CONTEXT@@QEAAJPEBG@Z`
- size: `617`
- prototype: `__int64 __fastcall(FREB_REQUEST_CONTEXT *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18000209c`
- `0x1800040e0`

## callees

- `0x180003bbc`
- `0x180003c58`
- `0x180004168`
- `0x1800047a4`
- `0x180004ae4`
- `0x180005588`
- `0x1800087a8`
- `0x18000a6a8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005711`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180005711`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005703`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180005703`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180005678`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180005678`
- `iisutil!PuDbgPrint` at `0x1800056c5`
- `iisutil!PuDbgPrint` at `0x1800056c5`
- `iisutil!PuDbgPrintError` at `0x180005778`
- `iisutil!PuDbgPrintError` at `0x180005778`

## string_xrefs

- `0x1800056be`: `servercommon\inetsrv\iis\iisrearc\iis70\freb\freb_request_context.cxx`
- `0x18000576c`: `servercommon\inetsrv\iis\iisrearc\iis70\freb\freb_request_context.cxx`
- `0x1800056a5`: `Freb: There are buffered events present but FREB is currently not able to write out data becausescavenging of files doesn't work log\n`
- `0x1800056ac`: `FREB_REQUEST_CONTEXT::WriteTraceEventsToFile`
- `0x180005760`: `FREB_REQUEST_CONTEXT::WriteTraceEventsToFile`
- `0x1800057df`: `Failed to write freb log file\n`

## pseudocode

```c
__int64 __fastcall FREB_REQUEST_CONTEXT::WriteTraceEventsToFile(FREB_REQUEST_CONTEXT *this, const unsigned __int16 *a2)
{
  unsigned int v2; // r14d
  __int64 v5; // rax
  __int64 v6; // rcx
  int v7; // eax
  struct TRACE_EVENTS_LIST_ENTRY *v8; // rdx
  __int64 v9; // rax
  _DWORD *v10; // rbx
  unsigned int v11; // eax
  int v12; // edi
  DWORD TickCount; // eax
  int *v15; // rbx
  struct _RTL_CRITICAL_SECTION *v16; // rsi
  int v17; // edi
  int v18; // eax
  FREB_LOG_NT_EVENT_TABLE *v19; // rcx
  const char *v20; // rax
  __int64 v21; // r8
  unsigned __int8 *v22; // rdx
  FREB_LOG_FILE_MANAGER *v23; // rcx
  unsigned int v24; // r8d
  int v25; // eax
  FREB_LOG_NT_EVENT_TABLE *v26; // rcx

  v2 = 0;
  if ( _InterlockedIncrement((volatile signed __int32 *)this + 50) != 1 )
    return v2;
  v5 = *((_QWORD *)this + 9);
  if ( !v5 )
    return v2;
  if ( *(_DWORD *)(v5 + 76) )
  {
    v6 = *((_QWORD *)this + 10);
    if ( v6 )
    {
      if ( *(_DWORD *)(v6 + 104) )
      {
        if ( _InterlockedIncrement((volatile signed __int32 *)(v6 + 172)) > *(_DWORD *)(v6 + 168) )
        {
          v8 = (struct TRACE_EVENTS_LIST_ENTRY *)*((_QWORD *)this + 31);
          if ( v8 && *((_QWORD *)this + 32) )
          {
            FREB_REQUEST_CONTEXT::AppendCommon(this, v8);
            v9 = *((_QWORD *)this + 31);
            *(_DWORD *)(v9 + 60) = 4;
            *(_QWORD *)(v9 + 48) = L"CUSTOM_ACTION_TRIGGER_LIMIT_EXCEEDED";
            *((_QWORD *)this + 31) = 0;
            *((_QWORD *)this + 32) = 0;
          }
        }
        else
        {
          v7 = FREB_REQUEST_CONTEXT::RunCustomAction(this, a2);
          v2 = v7;
          if ( v7 >= 0 )
            return v2;
          FREB_REQUEST_CONTEXT::AppendCustomActionFailed(this, v7);
        }
      }
    }
  }
  v10 = (_DWORD *)*((_QWORD *)this + 9);
  v11 = v10[187];
  if ( v11 > v10[18] || v11 > 0x1E )
  {
    v12 = v10[188];
    TickCount = GetTickCount();
    if ( !v12 )
    {
      v10[188] = TickCount;
LABEL_16:
      if ( (g_dwDebugFlags & 3) != 0 && g_dwDebugFlags < 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\freb\\freb_request_context.cxx",
          888,
          "FREB_REQUEST_CONTEXT::WriteTraceEventsToFile",
          "Freb: There are buffered events present but FREB is currently not able to write out data becausescavenging of "
          "files doesn't work log\n");
      return (unsigned int)-2147467259;
    }
    if ( TickCount - v12 <= 0x7530 )
      goto LABEL_16;
    *(_QWORD *)(v10 + 187) = 0;
  }
  v15 = (int *)FREB_LOG_FILE_MANAGER::sm_pLossyQueue;
  v16 = (struct _RTL_CRITICAL_SECTION *)((char *)FREB_LOG_FILE_MANAGER::sm_pLossyQueue + 32);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)FREB_LOG_FILE_MANAGER::sm_pLossyQueue + 32));
  v17 = *v15;
  LODWORD(v15) = v15[25];
  LeaveCriticalSection(v16);
  if ( v17 != (_DWORD)v15 )
  {
    v2 = FREB_REQUEST_CONTEXT::FilterWWWServerAreasAndVerbosity(this);
    if ( (v2 & 0x80000000) == 0 )
    {
      v18 = FREB_REQUEST_CONTEXT::SerializeAllTraceEventsToLogDataString(this, a2);
      v2 = v18;
      if ( v18 >= 0 )
      {
        v22 = (unsigned __int8 *)*((_QWORD *)this + 20);
        v23 = (FREB_LOG_FILE_MANAGER *)(*((_QWORD *)this + 9) + 144LL);
        v24 = *((_DWORD *)this + 44);
        *((_QWORD *)this + 20) = 0;
        *((_DWORD *)this + 42) = 0;
        *((_DWORD *)this + 44) = 0;
        v25 = FREB_LOG_FILE_MANAGER::QueueWriteLogFile(v23, v22, v24);
        v2 = v25;
        if ( v25 >= 0 )
          return v2;
        FREB_LOG_NT_EVENT_TABLE::LogEventFrebRuntimeError(v26, v25);
        if ( (g_dwDebugFlags & 0xF) == 0 )
          return v2;
        v20 = "Failed to write freb log file\n";
        v21 = 927;
      }
      else
      {
        FREB_LOG_NT_EVENT_TABLE::LogEventFrebRuntimeError(v19, v18);
        if ( (g_dwDebugFlags & 0xF) == 0 )
          return v2;
        v20 = "Failed to serialize all trace events\n";
        v21 = 915;
      }
      PuDbgPrintError(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\freb\\freb_request_context.cxx",
        v21,
        "FREB_REQUEST_CONTEXT::WriteTraceEventsToFile",
        v2,
        v20);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180005588  push    rbx
0x18000558a  push    rbp
0x18000558b  push    rsi
0x18000558c  push    rdi
0x18000558d  push    r14
0x18000558f  push    r15
0x180005591  sub     rsp, 38h
0x180005595  xor     r14d, r14d
0x180005598  mov     r15, rdx
0x18000559b  mov     rbp, rcx
0x18000559e  lea     edx, [r14+1]
0x1800055a2  mov     eax, edx
0x1800055a4  lock xadd [rcx+0C8h], eax
0x1800055ac  add     eax, edx
0x1800055ae  cmp     eax, edx
0x1800055b0  jnz     loc_1800056D1
0x1800055b6  mov     rax, [rcx+48h]
0x1800055ba  test    rax, rax
0x1800055bd  jz      loc_1800056D1
0x1800055c3  cmp     [rax+4Ch], r14d
0x1800055c7  jz      loc_18000565A
0x1800055cd  mov     rcx, [rcx+50h]
0x1800055d1  test    rcx, rcx
0x1800055d4  jz      loc_18000565A
0x1800055da  cmp     [rcx+68h], r14d
0x1800055de  jz      short loc_18000565A
0x1800055e0  mov     eax, edx
0x1800055e2  lock xadd [rcx+0ACh], eax
0x1800055ea  add     eax, edx
0x1800055ec  cmp     eax, [rcx+0A8h]
0x1800055f2  jg      short loc_180005616
0x1800055f4  mov     rdx, r15; unsigned __int16 *
0x1800055f7  mov     rcx, rbp; this
0x1800055fa  call    ?RunCustomAction@FREB_REQUEST_CONTEXT@@AEAAJPEBG@Z; FREB_REQUEST_CONTEXT::RunCustomAction(ushort const *)
0x1800055ff  mov     r14d, eax
0x180005602  test    eax, eax
0x180005604  jns     loc_1800056D1
0x18000560a  mov     edx, eax; int
0x18000560c  mov     rcx, rbp; this
0x18000560f  call    ?AppendCustomActionFailed@FREB_REQUEST_CONTEXT@@AEAAXJ@Z; FREB_REQUEST_CONTEXT::AppendCustomActionFailed(long)
0x180005614  jmp     short loc_18000565A
0x180005616  mov     rdx, [rbp+0F8h]; struct TRACE_EVENTS_LIST_ENTRY *
0x18000561d  test    rdx, rdx
0x180005620  jz      short loc_18000565A
0x180005622  cmp     [rbp+100h], r14
0x180005629  jz      short loc_18000565A
0x18000562b  mov     rcx, rbp; this
0x18000562e  call    ?AppendCommon@FREB_REQUEST_CONTEXT@@AEAAXPEAVTRACE_EVENTS_LIST_ENTRY@@@Z; FREB_REQUEST_CONTEXT::AppendCommon(TRACE_EVENTS_LIST_ENTRY *)
0x180005633  mov     rax, [rbp+0F8h]
0x18000563a  lea     rcx, aCustomActionTr; "CUSTOM_ACTION_TRIGGER_LIMIT_EXCEEDED"
0x180005641  mov     dword ptr [rax+3Ch], 4
0x180005648  mov     [rax+30h], rcx
0x18000564c  mov     [rbp+0F8h], r14
0x180005653  mov     [rbp+100h], r14
0x18000565a  mov     rbx, [rbp+48h]
0x18000565e  mov     eax, [rbx+2ECh]
0x180005664  cmp     eax, [rbx+48h]
0x180005667  ja      short loc_180005672
0x180005669  cmp     eax, 1Eh
0x18000566c  jbe     loc_1800056F5
0x180005672  mov     edi, [rbx+2F0h]
0x180005678  call    cs:__imp_GetTickCount
0x18000567e  test    edi, edi
0x180005680  jnz     short loc_1800056E1
0x180005682  mov     [rbx+2F0h], eax
0x180005688  mov     eax, cs:g_dwDebugFlags
0x18000568e  test    al, 3
0x180005690  setnz   cl
0x180005693  bt      eax, 1Fh
0x180005697  setb    al
0x18000569a  test    al, cl
0x18000569c  jz      short loc_1800056CB
0x18000569e  mov     rcx, cs:g_pDebug
0x1800056a5  lea     rax, aFrebThereAreBu; "Freb: There are buffered events present"...
0x1800056ac  lea     r9, aFrebRequestCon_2; "FREB_REQUEST_CONTEXT::WriteTraceEventsT"...
0x1800056b3  mov     [rsp+68h+var_48], rax
0x1800056b8  mov     r8d, 378h
0x1800056be  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800056c5  call    cs:__imp_PuDbgPrint
0x1800056cb  mov     r14d, 80004005h
0x1800056d1  mov     eax, r14d
0x1800056d4  add     rsp, 38h
0x1800056d8  pop     r15
0x1800056da  pop     r14
0x1800056dc  pop     rdi
0x1800056dd  pop     rsi
0x1800056de  pop     rbp
0x1800056df  pop     rbx
0x1800056e0  retn
0x1800056e1  sub     eax, edi
0x1800056e3  cmp     eax, 7530h
0x1800056e8  jbe     short loc_180005688
0x1800056ea  mov     qword ptr [rbx+2ECh], 0
0x1800056f5  mov     rbx, cs:?sm_pLossyQueue@FREB_LOG_FILE_MANAGER@@0PEAVLOSSY_QUEUE@@EA; LOSSY_QUEUE * FREB_LOG_FILE_MANAGER::sm_pLossyQueue
0x1800056fc  lea     rsi, [rbx+20h]
0x180005700  mov     rcx, rsi; lpCriticalSection
0x180005703  call    cs:__imp_EnterCriticalSection
0x180005709  mov     edi, [rbx]
0x18000570b  mov     rcx, rsi; lpCriticalSection
0x18000570e  mov     ebx, [rbx+64h]
0x180005711  call    cs:__imp_LeaveCriticalSection
0x180005717  cmp     edi, ebx
0x180005719  jz      short loc_1800056D1
0x18000571b  mov     rcx, rbp; this
0x18000571e  call    ?FilterWWWServerAreasAndVerbosity@FREB_REQUEST_CONTEXT@@AEAAJXZ; FREB_REQUEST_CONTEXT::FilterWWWServerAreasAndVerbosity(void)
0x180005723  mov     r14d, eax
0x180005726  test    eax, eax
0x180005728  js      short loc_1800056D1
0x18000572a  mov     rdx, r15; unsigned __int16 *
0x18000572d  mov     rcx, rbp; this
0x180005730  call    ?SerializeAllTraceEventsToLogDataString@FREB_REQUEST_CONTEXT@@AEAAJPEBG@Z; FREB_REQUEST_CONTEXT::SerializeAllTraceEventsToLogDataString(ushort const *)
0x180005735  mov     r14d, eax
0x180005738  test    eax, eax
0x18000573a  jns     short loc_180005783
0x18000573c  mov     edx, eax; int
0x18000573e  call    ?LogEventFrebRuntimeError@FREB_LOG_NT_EVENT_TABLE@@QEAAXJ@Z; FREB_LOG_NT_EVENT_TABLE::LogEventFrebRuntimeError(long)
0x180005743  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000574a  jz      short loc_1800056D1
0x18000574c  lea     rax, aFailedToSerial; "Failed to serialize all trace events\n"
0x180005753  mov     r8d, 393h
0x180005759  mov     rcx, cs:g_pDebug
0x180005760  lea     r9, aFrebRequestCon_2; "FREB_REQUEST_CONTEXT::WriteTraceEventsT"...
0x180005767  mov     [rsp+68h+var_40], rax
0x18000576c  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180005773  mov     dword ptr [rsp+68h+var_48], r14d
0x180005778  call    cs:__imp_PuDbgPrintError
0x18000577e  jmp     loc_1800056D1
0x180005783  mov     rcx, [rbp+48h]
0x180005787  mov     rdx, [rbp+0A0h]; unsigned __int8 *
0x18000578e  add     rcx, 90h; this
0x180005795  mov     r8d, [rbp+0B0h]; unsigned int
0x18000579c  mov     qword ptr [rbp+0A0h], 0
0x1800057a7  mov     dword ptr [rbp+0A8h], 0
0x1800057b1  mov     dword ptr [rbp+0B0h], 0
0x1800057bb  call    ?QueueWriteLogFile@FREB_LOG_FILE_MANAGER@@QEAAJPEAEK@Z; FREB_LOG_FILE_MANAGER::QueueWriteLogFile(uchar *,ulong)
0x1800057c0  mov     r14d, eax
0x1800057c3  test    eax, eax
0x1800057c5  jns     loc_1800056D1
0x1800057cb  mov     edx, eax; int
0x1800057cd  call    ?LogEventFrebRuntimeError@FREB_LOG_NT_EVENT_TABLE@@QEAAXJ@Z; FREB_LOG_NT_EVENT_TABLE::LogEventFrebRuntimeError(long)
0x1800057d2  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800057d9  jz      loc_1800056D1
0x1800057df  lea     rax, aFailedToWriteF; "Failed to write freb log file\n"
0x1800057e6  mov     r8d, 39Fh
0x1800057ec  jmp     loc_180005759
```
