# PlaiSetControl(void *)

- ea: `0x180134620`
- end: `0x1801350f6`
- name: `?PlaiSetControl@@YAKPEAX@Z`
- size: `2774`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x18002b3a0`
- `0x180075de0`
- `0x18008832c`
- `0x18009be9c`
- `0x1800d1638`
- `0x180134620`
- `0x1801350fc`
- `0x18013aee0`
- `0x18013c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801348e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180134a03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180134c15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180134c80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180134cbf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801348e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180134a03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180134c15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180134c80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180134cbf`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180134c5f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180134f9f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180134c5f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180134f9f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180134f95`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180134f95`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180134c49`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180134caf`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180134c49`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180134caf`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x1801349f5`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x1801349f5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180134f88`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180134f88`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180134679`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180134679`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1801350cb`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1801350cb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801350ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801350ab`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180134bc6`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180134bc6`
- `api-ms-win-core-synch-l1-2-1!CreateWaitableTimerW` at `0x1801348cc`
- `api-ms-win-core-synch-l1-2-1!CreateWaitableTimerW` at `0x1801348cc`

## pseudocode

```c
__int64 __fastcall PlaiSetControl(struct _SET_INSTANCE *Parameter)
{
  HANDLE v2; // r15
  HRESULT v3; // eax
  unsigned __int64 v4; // rdx
  __int64 v5; // rsi
  signed int v6; // ebx
  struct IDataCollectorSet *v7; // r12
  int v8; // r14d
  __int64 v9; // rax
  struct IDataCollectorSet v10; // rax
  int v11; // eax
  unsigned __int64 v12; // rdx
  __int64 v13; // rax
  DWORD v14; // r15d
  DWORD v15; // eax
  unsigned __int64 v16; // rdx
  __int64 v17; // rax
  HRESULT *v18; // r9
  DWORD LastError; // eax
  int v20; // eax
  unsigned __int64 v21; // rdx
  __int64 v22; // rax
  int v23; // eax
  unsigned __int64 v24; // rdx
  __int64 v25; // rax
  int v26; // r14d
  DWORD v27; // r9d
  DWORD v28; // eax
  unsigned __int64 v29; // rdx
  signed int v30; // eax
  struct _SET_INSTANCE *v31; // r14
  DWORD v32; // eax
  DWORD v33; // eax
  __int64 v34; // rax
  struct _SET_INSTANCE *v35; // r15
  unsigned __int64 v36; // rdx
  __int64 v37; // rax
  unsigned __int64 v38; // rdx
  __int64 v39; // rax
  int v40; // eax
  unsigned __int64 v41; // rdx
  __int64 v42; // rax
  struct _SET_INSTANCE *v43; // rdi
  __int64 v44; // r9
  __int64 v45; // rax
  __int64 v46; // r9
  int v48; // [rsp+70h] [rbp-90h] BYREF
  HRESULT v49; // [rsp+78h] [rbp-88h] BYREF
  signed int v50; // [rsp+80h] [rbp-80h] BYREF
  DWORD i; // [rsp+88h] [rbp-78h] BYREF
  struct IDataCollectorSet *v52; // [rsp+90h] [rbp-70h]
  HANDLE WaitableTimerW; // [rsp+98h] [rbp-68h]
  struct _SET_INSTANCE *v54; // [rsp+A0h] [rbp-60h]
  LARGE_INTEGER DueTime; // [rsp+A8h] [rbp-58h] BYREF
  HANDLE Handles[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v57; // [rsp+C0h] [rbp-40h]
  __int128 v58; // [rsp+D0h] [rbp-30h]
  unsigned __int16 v59[64]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int16 v60[64]; // [rsp+160h] [rbp+60h] BYREF
  unsigned __int16 v61[64]; // [rsp+1E0h] [rbp+E0h] BYREF
  unsigned __int16 v62[64]; // [rsp+260h] [rbp+160h] BYREF
  unsigned __int16 v63[64]; // [rsp+2E0h] [rbp+1E0h] BYREF
  unsigned __int16 v64[64]; // [rsp+360h] [rbp+260h] BYREF
  unsigned __int16 v65[64]; // [rsp+3E0h] [rbp+2E0h] BYREF
  unsigned __int16 v66[64]; // [rsp+460h] [rbp+360h] BYREF
  unsigned __int16 v67[64]; // [rsp+4E0h] [rbp+3E0h] BYREF

  v54 = Parameter;
  WaitableTimerW = 0;
  DueTime.QuadPart = 0;
  *(_OWORD *)Handles = 0;
  v2 = 0;
  i = 0;
  v57 = 0;
  v58 = 0;
  v3 = CoInitializeEx(0, 0);
  v5 = -1;
  v6 = v3;
  if ( v3 < 0 )
  {
    v7 = 0;
    v8 = 0;
    v48 = 0;
    v49 = v3;
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
    {
      PlaiWhoAmI(v59, v4);
      v9 = -1;
      do
        ++v9;
      while ( v59[v9] );
      EventingWriteEvent((__int64)&g_Eventing, (__int64)&PLA_EVENT_ERROR, 5, (__int64)&v49);
      v7 = 0;
    }
    goto LABEL_99;
  }
  v7 = (struct IDataCollectorSet *)*((_QWORD *)Parameter + 15);
  v8 = 1;
  Handles[0] = *((HANDLE *)Parameter + 3);
  Handles[1] = *((HANDLE *)Parameter + 9);
  *(_QWORD *)&v57 = *((_QWORD *)Parameter + 8);
  *((_QWORD *)&v57 + 1) = *((_QWORD *)Parameter + 4);
  *(_QWORD *)&v58 = *((_QWORD *)Parameter + 2);
  v10.lpVtbl = v7->lpVtbl;
  v48 = 1;
  v52 = v7;
  ((void (__fastcall *)(struct IDataCollectorSet *))v10.lpVtbl->AddRef)(v7);
  v11 = ((__int64 (__fastcall *)(struct IDataCollectorSet *, DWORD *))v7->lpVtbl->get_Duration)(v7, &i);
  v6 = v11;
  if ( v11 < 0 )
  {
    v49 = 0;
    v48 = v11;
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
    {
      PlaiWhoAmI(v60, v12);
      v13 = -1;
      do
        ++v13;
      while ( v60[v13] );
      EventingWriteEvent((__int64)&g_Eventing, (__int64)&PLA_EVENT_ERROR, 5, (__int64)&v48);
      goto LABEL_98;
    }
    goto LABEL_99;
  }
  if ( i )
  {
    WaitableTimerW = CreateWaitableTimerW(0, 1, 0);
    v2 = WaitableTimerW;
    if ( WaitableTimerW )
    {
      DueTime.QuadPart = -10000000LL * i;
      if ( SetWaitableTimer(WaitableTimerW, &DueTime, 0, 0, 0, 0)
        || (LastError = GetLastError(), v20 = PlaiHResultFromWin32(LastError), v6 = v20, v20 >= 0) )
      {
        v14 = 6;
        *((_QWORD *)&v58 + 1) = WaitableTimerW;
        goto LABEL_34;
      }
      v50 = 0;
      v49 = v20;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v62, v21);
        v22 = -1;
        do
          ++v22;
        while ( v62[v22] );
        v18 = &v49;
        goto LABEL_24;
      }
    }
    else
    {
      v15 = GetLastError();
      v6 = PlaiHResultFromWin32(v15);
      v49 = 0;
      v50 = v6;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v61, v16);
        v17 = -1;
        do
          ++v17;
        while ( v61[v17] );
        v18 = &v50;
LABEL_24:
        EventingWriteEvent((__int64)&g_Eventing, (__int64)&PLA_EVENT_ERROR, 5, (__int64)v18);
        goto LABEL_97;
      }
    }
LABEL_42:
    v8 = v48;
    goto LABEL_99;
  }
  v14 = 5;
LABEL_34:
  v23 = ((__int64 (__fastcall *)(struct IDataCollectorSet *, DWORD *))v7->lpVtbl->get_SegmentMaxDuration)(v7, &i);
  v6 = v23;
  if ( v23 < 0 )
  {
    v50 = 0;
    v49 = v23;
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
    {
      PlaiWhoAmI(v63, v24);
      v25 = -1;
      do
        ++v25;
      while ( v63[v25] );
      goto LABEL_95;
    }
    v2 = WaitableTimerW;
    goto LABEL_42;
  }
  v26 = 1;
  if ( i )
    v27 = 1000 * i;
  else
    v27 = -1;
  for ( i = v27; ; v27 = i )
  {
    v28 = WaitForMultipleObjects(v14, Handles, 0, v27);
    if ( !v28 )
      goto LABEL_60;
    if ( v28 == 1 )
      goto LABEL_59;
    if ( v28 != 2 )
    {
      if ( v28 == 3 )
      {
        v31 = v54;
        v6 = PlaiControlCollectorSet(v54, 1);
        if ( v6 >= 0 )
        {
          if ( ResetEvent(*((HANDLE *)v31 + 4)) )
          {
            v6 = 0;
          }
          else
          {
            v32 = GetLastError();
            v6 = PlaiHResultFromWin32(v32);
          }
        }
LABEL_59:
        SetEvent(*((HANDLE *)v54 + 2));
LABEL_60:
        v26 = 0;
        goto LABEL_61;
      }
      if ( v28 - 4 <= 1 )
        goto LABEL_59;
      if ( v28 != 258 )
      {
        if ( v28 == -1 )
        {
          v30 = GetLastError();
          v6 = v30;
          if ( v30 > 0 )
            v6 = (unsigned __int16)v30 | 0x80070000;
        }
        goto LABEL_60;
      }
    }
    v6 = PlaiControlCollectorSet(v54, 2);
    if ( v6 < 0 )
      break;
    if ( ResetEvent(*((HANDLE *)v54 + 8)) )
    {
      v6 = 0;
      goto LABEL_62;
    }
    v33 = GetLastError();
    v6 = PlaiHResultFromWin32(v33);
LABEL_61:
    if ( v6 < 0 )
      break;
LABEL_62:
    if ( !v26 )
      goto LABEL_75;
  }
  v50 = 0;
  v49 = v6;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
  {
    PlaiWhoAmI(v64, v29);
    v34 = -1;
    do
      ++v34;
    while ( v64[v34] );
    EventingWriteEvent((__int64)&g_Eventing, (__int64)&PLA_EVENT_ERROR, 5, (__int64)&v49);
  }
LABEL_75:
  v35 = v54;
  v6 = PlaiWaitForStop(v54);
  if ( v6 >= 0 )
  {
    v6 = PlaiExecuteTask(v52, 1);
    if ( v6 >= 0 )
    {
      v40 = PlaiRunDataManager(v35);
      v6 = v40;
      if ( v40 >= 0 )
        goto LABEL_96;
      v50 = 0;
      v49 = v40;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_96;
      }
      PlaiWhoAmI(v67, v41);
      v42 = -1;
      do
        ++v42;
      while ( v67[v42] );
    }
    else
    {
      v50 = 0;
      v49 = v6;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_96;
      }
      PlaiWhoAmI(v66, v38);
      v39 = -1;
      do
        ++v39;
      while ( v66[v39] );
    }
LABEL_95:
    EventingWriteEvent((__int64)&g_Eventing, (__int64)&PLA_EVENT_ERROR, 5, (__int64)&v49);
    goto LABEL_96;
  }
  v50 = 0;
  v49 = v6;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
  {
    PlaiWhoAmI(v65, v36);
    v37 = -1;
    do
      ++v37;
    while ( v65[v37] );
    goto LABEL_95;
  }
LABEL_96:
  v2 = WaitableTimerW;
LABEL_97:
  v8 = v48;
LABEL_98:
  v7 = v52;
LABEL_99:
  v43 = v54;
  PlaiCloseCollectorSet(v54);
  EnterCriticalSection(&g_cs);
  LeaveCriticalSection(&g_cs);
  SetEvent(*((HANDLE *)v43 + 7));
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000100LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000100LL) )
  {
    v44 = *(_QWORD *)v43;
    if ( *(_QWORD *)v43 )
    {
      v45 = -1;
      do
        ++v45;
      while ( *(_WORD *)(v44 + 2 * v45) );
    }
    EventingWriteEvent((__int64)&g_Eventing, (__int64)&PLA_EVENT_DCS_STOP, 1, v44);
  }
  v46 = *(_QWORD *)v43;
  v50 = v6;
  if ( v6 < 0 )
  {
    if ( v46 )
    {
      do
        ++v5;
      while ( *(_WORD *)(v46 + 2 * v5) );
    }
    EventingWriteEvent((__int64)&g_Eventing, (__int64)&PLA_EVENTLOG_DCS_STOP_FAILURE, 2, v46);
  }
  else
  {
    if ( v46 )
    {
      do
        ++v5;
      while ( *(_WORD *)(v46 + 2 * v5) );
    }
    EventingWriteEvent((__int64)&g_Eventing, (__int64)&PLA_EVENTLOG_DCS_STOP, 1, v46);
  }
  if ( v2 )
    CloseHandle(v2);
  if ( v7 )
    ((void (__fastcall *)(struct IDataCollectorSet *))v7->lpVtbl->Release)(v7);
  if ( v8 )
    CoUninitialize();
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180134620  push    rbp
0x180134622  push    rbx
0x180134623  push    rsi
0x180134624  push    rdi
0x180134625  push    r12
0x180134627  push    r13
0x180134629  push    r14
0x18013462b  push    r15
0x18013462d  lea     rbp, [rsp-478h]
0x180134635  sub     rsp, 578h
0x18013463c  mov     rax, cs:__security_cookie
0x180134643  xor     rax, rsp
0x180134646  mov     [rbp+4B0h+var_50], rax
0x18013464d  xorps   xmm0, xmm0
0x180134650  mov     [rbp+4B0h+var_510], rcx
0x180134654  xor     r13d, r13d
0x180134657  mov     rdi, rcx
0x18013465a  xor     ecx, ecx; pvReserved
0x18013465c  mov     [rbp+4B0h+var_518], r13
0x180134660  xor     edx, edx; dwCoInit
0x180134662  mov     qword ptr [rbp+4B0h+DueTime], r13
0x180134666  movups  xmmword ptr [rbp+4B0h+Handles], xmm0
0x18013466a  mov     r15d, r13d
0x18013466d  mov     [rbp+4B0h+var_528], r13d
0x180134671  movups  [rbp+4B0h+var_4F0], xmm0
0x180134675  movups  [rbp+4B0h+var_4E0], xmm0
0x180134679  call    cs:__imp_CoInitializeEx
0x18013467f  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180134683  mov     ebx, eax
0x180134685  test    eax, eax
0x180134687  jns     loc_180134770
0x18013468d  cmp     dword ptr cs:xmmword_180169738, r13d
0x180134694  mov     r12d, r13d
0x180134697  mov     r14d, r13d
0x18013469a  mov     [rsp+5B0h+var_540], r13d
0x18013469f  mov     [rsp+5B0h+var_538], eax
0x1801346a3  jz      loc_180134F75
0x1801346a9  mov     rdi, 4000000000000800h
0x1801346b3  test    qword ptr cs:xmmword_180169738+8, rdi
0x1801346ba  jz      loc_180134F75
0x1801346c0  mov     rax, cs:qword_180169748
0x1801346c7  and     rax, rdi
0x1801346ca  cmp     cs:qword_180169748, rax
0x1801346d1  jnz     loc_180134F75
0x1801346d7  lea     rcx, [rbp+4B0h+var_4D0]; unsigned __int16 *
0x1801346db  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1801346e0  lea     rcx, [rbp+4B0h+var_4D0]
0x1801346e4  mov     rax, rsi
0x1801346e7  inc     rax
0x1801346ea  cmp     [rcx+rax*2], r13w
0x1801346ef  jnz     short loc_1801346E7
0x1801346f1  lea     ecx, [rax+rax]
0x1801346f4  mov     r12d, 0Fh
0x1801346fa  add     rcx, 2
0x1801346fe  lea     rax, [rbp+4B0h+var_4D0]
0x180134702  mov     [rsp+5B0h+var_550], rcx
0x180134707  lea     r13, aPlaisetcontrol; "PlaiSetControl"
0x18013470e  mov     [rsp+5B0h+var_558], rax
0x180134713  lea     r9, [rsp+5B0h+var_538]
0x180134718  mov     [rsp+5B0h+var_560], r12
0x18013471d  lea     ecx, [r12-0Bh]
0x180134722  mov     [rsp+5B0h+var_568], r13
0x180134727  lea     rax, [rsp+5B0h+var_540]
0x18013472c  mov     [rsp+5B0h+var_570], rcx
0x180134731  lea     r8d, [r12-0Ah]
0x180134736  mov     [rsp+5B0h+var_578], rax
0x18013473b  lea     rdx, PLA_EVENT_ERROR
0x180134742  lea     rax, byte_180147320
0x180134749  mov     [rsp+5B0h+var_580], 1
0x180134752  mov     qword ptr [rsp+5B0h+fResume], rax
0x180134757  mov     [rsp+5B0h+lpArgToCompletionRoutine], rcx
0x18013475c  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x180134763  call    EventingWriteEvent
0x180134768  mov     r12, r14
0x18013476b  jmp     loc_180134F72
0x180134770  mov     r12, [rdi+78h]
0x180134774  mov     r14d, 1
0x18013477a  mov     rax, [rdi+18h]
0x18013477e  mov     rcx, r12
0x180134781  mov     [rbp+4B0h+Handles], rax
0x180134785  mov     rax, [rdi+48h]
0x180134789  mov     [rbp+4B0h+Handles+8], rax
0x18013478d  mov     rax, [rdi+40h]
0x180134791  mov     qword ptr [rbp+4B0h+var_4F0], rax
0x180134795  mov     rax, [rdi+20h]
0x180134799  mov     qword ptr [rbp+4B0h+var_4F0+8], rax
0x18013479d  mov     rax, [rdi+10h]
0x1801347a1  mov     qword ptr [rbp+4B0h+var_4E0], rax
0x1801347a5  mov     rax, [r12]
0x1801347a9  mov     [rsp+5B0h+var_540], r14d
0x1801347ae  mov     [rbp+4B0h+var_520], r12
0x1801347b2  mov     rax, [rax+8]
0x1801347b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801347bb  mov     rax, [r12]
0x1801347bf  lea     rdx, [rbp+4B0h+var_528]
0x1801347c3  mov     rcx, r12
0x1801347c6  mov     rax, [rax+40h]
0x1801347ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801347cf  mov     ebx, eax
0x1801347d1  test    eax, eax
0x1801347d3  jns     loc_1801348AF
0x1801347d9  cmp     dword ptr cs:xmmword_180169738, r13d
0x1801347e0  mov     [rsp+5B0h+var_538], r13d
0x1801347e5  mov     [rsp+5B0h+var_540], eax
0x1801347e9  jz      loc_180134F75
0x1801347ef  mov     rdi, 4000000000000800h
0x1801347f9  test    qword ptr cs:xmmword_180169738+8, rdi
0x180134800  jz      loc_180134F75
0x180134806  mov     rax, cs:qword_180169748
0x18013480d  and     rax, rdi
0x180134810  cmp     cs:qword_180169748, rax
0x180134817  jnz     loc_180134F75
0x18013481d  lea     rcx, [rbp+4B0h+var_450]; unsigned __int16 *
0x180134821  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180134826  lea     rcx, [rbp+4B0h+var_450]
0x18013482a  mov     rax, rsi
0x18013482d  inc     rax
0x180134830  cmp     [rcx+rax*2], r13w
0x180134835  jnz     short loc_18013482D
0x180134837  lea     ecx, [rax+rax]
0x18013483a  mov     r12d, 0Fh
0x180134840  add     rcx, 2
0x180134844  lea     rax, [rbp+4B0h+var_450]
0x180134848  mov     [rsp+5B0h+var_550], rcx
0x18013484d  lea     r13, aPlaisetcontrol; "PlaiSetControl"
0x180134854  mov     [rsp+5B0h+var_558], rax
0x180134859  lea     r9, [rsp+5B0h+var_540]
0x18013485e  mov     [rsp+5B0h+var_560], r12
0x180134863  lea     ecx, [r12-0Bh]
0x180134868  mov     [rsp+5B0h+var_568], r13
0x18013486d  lea     rax, [rsp+5B0h+var_538]
0x180134872  mov     [rsp+5B0h+var_570], rcx
0x180134877  lea     r8d, [r12-0Ah]
0x18013487c  mov     [rsp+5B0h+var_578], rax
0x180134881  lea     rdx, PLA_EVENT_ERROR
0x180134888  lea     rax, byte_180147320
0x18013488f  mov     [rsp+5B0h+var_580], r14
0x180134894  mov     qword ptr [rsp+5B0h+fResume], rax
0x180134899  mov     [rsp+5B0h+lpArgToCompletionRoutine], rcx
0x18013489e  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1801348a5  call    EventingWriteEvent
0x1801348aa  jmp     loc_180134F6E
0x1801348af  mov     r14d, 5
0x1801348b5  cmp     [rbp+4B0h+var_528], r13d
0x1801348b9  jnz     short loc_1801348C3
0x1801348bb  mov     r15d, r14d
0x1801348be  jmp     loc_180134AB1
0x1801348c3  xor     r8d, r8d; lpTimerName
0x1801348c6  xor     ecx, ecx; lpTimerAttributes
0x1801348c8  lea     edx, [r8+1]; bManualReset
0x1801348cc  call    cs:__imp_CreateWaitableTimerW
0x1801348d2  mov     [rbp+4B0h+var_518], rax
0x1801348d6  mov     r15, rax
0x1801348d9  test    rax, rax
0x1801348dc  jnz     loc_1801349D0
0x1801348e2  call    cs:__imp_GetLastError
0x1801348e8  mov     ecx, eax; unsigned int
0x1801348ea  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x1801348ef  cmp     dword ptr cs:xmmword_180169738, r13d
0x1801348f6  mov     ebx, eax
0x1801348f8  mov     [rsp+5B0h+var_538], r13d
0x1801348fd  mov     [rbp+4B0h+var_530], eax
0x180134900  jz      loc_180134B94
0x180134906  mov     rdi, 4000000000000800h
0x180134910  test    qword ptr cs:xmmword_180169738+8, rdi
0x180134917  jz      loc_180134B94
0x18013491d  mov     rax, cs:qword_180169748
0x180134924  and     rax, rdi
0x180134927  cmp     cs:qword_180169748, rax
0x18013492e  jnz     loc_180134B94
0x180134934  lea     rcx, [rbp+4B0h+var_3D0]; unsigned __int16 *
0x18013493b  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180134940  lea     rcx, [rbp+4B0h+var_3D0]
0x180134947  mov     rax, rsi
0x18013494a  inc     rax
0x18013494d  cmp     [rcx+rax*2], r13w
0x180134952  jnz     short loc_18013494A
0x180134954  lea     ecx, [rax+rax]
0x180134957  lea     rax, [rbp+4B0h+var_3D0]
0x18013495e  add     rcx, 2
0x180134962  mov     [rsp+5B0h+var_550], rcx
0x180134967  lea     r9, [rbp+4B0h+var_530]
0x18013496b  mov     [rsp+5B0h+var_558], rax
0x180134970  lea     rax, [rsp+5B0h+var_538]
0x180134975  mov     r12d, 0Fh
0x18013497b  lea     r13, aPlaisetcontrol; "PlaiSetControl"
0x180134982  mov     [rsp+5B0h+var_560], r12
0x180134987  lea     rdx, PLA_EVENT_ERROR
0x18013498e  mov     [rsp+5B0h+var_568], r13
0x180134993  mov     r8d, r14d
0x180134996  lea     ecx, [r12-0Bh]
0x18013499b  mov     [rsp+5B0h+var_570], rcx
0x1801349a0  mov     [rsp+5B0h+var_578], rax
0x1801349a5  lea     rax, byte_180147320
0x1801349ac  mov     [rsp+5B0h+var_580], 1
0x1801349b5  mov     qword ptr [rsp+5B0h+fResume], rax
0x1801349ba  mov     [rsp+5B0h+lpArgToCompletionRoutine], rcx
0x1801349bf  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1801349c6  call    EventingWriteEvent
0x1801349cb  jmp     loc_180134F69
0x1801349d0  mov     eax, [rbp+4B0h+var_528]
0x1801349d3  lea     rdx, [rbp+4B0h+DueTime]; lpDueTime
0x1801349d7  imul    rcx, rax, 0FFFFFFFFFF676980h
0x1801349de  mov     [rsp+5B0h+fResume], r13d; fResume
0x1801349e3  xor     r9d, r9d; pfnCompletionRoutine
0x1801349e6  mov     qword ptr [rbp+4B0h+DueTime], rcx
0x1801349ea  xor     r8d, r8d; lPeriod
0x1801349ed  mov     rcx, r15; hTimer
0x1801349f0  mov     [rsp+5B0h+lpArgToCompletionRoutine], r13; lpArgToCompletionRoutine
0x1801349f5  call    cs:__imp_SetWaitableTimer
0x1801349fb  test    eax, eax
0x1801349fd  jnz     loc_180134AA3
0x180134a03  call    cs:__imp_GetLastError
0x180134a09  mov     ecx, eax; unsigned int
0x180134a0b  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x180134a10  mov     ebx, eax
0x180134a12  test    eax, eax
0x180134a14  jns     loc_180134AA3
0x180134a1a  cmp     dword ptr cs:xmmword_180169738, r13d
0x180134a21  mov     [rbp+4B0h+var_530], r13d
0x180134a25  mov     [rsp+5B0h+var_538], eax
0x180134a29  jz      loc_180134B94
0x180134a2f  mov     rdi, 4000000000000800h
0x180134a39  test    qword ptr cs:xmmword_180169738+8, rdi
0x180134a40  jz      loc_180134B94
0x180134a46  mov     rax, cs:qword_180169748
0x180134a4d  and     rax, rdi
0x180134a50  cmp     cs:qword_180169748, rax
0x180134a57  jnz     loc_180134B94
0x180134a5d  lea     rcx, [rbp+4B0h+var_350]; unsigned __int16 *
0x180134a64  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180134a69  lea     rcx, [rbp+4B0h+var_350]
0x180134a70  mov     rax, rsi
0x180134a73  inc     rax
0x180134a76  cmp     [rcx+rax*2], r13w
0x180134a7b  jnz     short loc_180134A73
0x180134a7d  lea     ecx, [rax+rax]
0x180134a80  lea     rax, [rbp+4B0h+var_350]
0x180134a87  add     rcx, 2
0x180134a8b  mov     [rsp+5B0h+var_550], rcx
0x180134a90  lea     r9, [rsp+5B0h+var_538]
0x180134a95  mov     [rsp+5B0h+var_558], rax
0x180134a9a  lea     rax, [rbp+4B0h+var_530]
0x180134a9e  jmp     loc_180134975
0x180134aa3  mov     rax, [rbp+4B0h+var_518]
0x180134aa7  mov     r15d, 6
0x180134aad  mov     qword ptr [rbp+4B0h+var_4E0+8], rax
0x180134ab1  mov     rax, [r12]
0x180134ab5  lea     rdx, [rbp+4B0h+var_528]
0x180134ab9  mov     rcx, r12
0x180134abc  mov     rax, [rax+0D0h]
0x180134ac3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180134ac8  mov     ebx, eax
0x180134aca  test    eax, eax
0x180134acc  jns     loc_180134B9E
0x180134ad2  cmp     dword ptr cs:xmmword_180169738, r13d
0x180134ad9  mov     [rbp+4B0h+var_530], r13d
0x180134add  mov     [rsp+5B0h+var_538], eax
0x180134ae1  jz      loc_180134B90
0x180134ae7  mov     rdi, 4000000000000800h
0x180134af1  test    qword ptr cs:xmmword_180169738+8, rdi
0x180134af8  jz      loc_180134B90
0x180134afe  mov     rax, cs:qword_180169748
0x180134b05  and     rax, rdi
0x180134b08  cmp     cs:qword_180169748, rax
0x180134b0f  jnz     short loc_180134B90
0x180134b11  lea     rcx, [rbp+4B0h+var_2D0]; unsigned __int16 *
0x180134b18  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180134b1d  lea     rcx, [rbp+4B0h+var_2D0]
0x180134b24  mov     rax, rsi
0x180134b27  inc     rax
0x180134b2a  cmp     [rcx+rax*2], r13w
0x180134b2f  jnz     short loc_180134B27
0x180134b31  lea     ecx, [rax+rax]
0x180134b34  mov     r12d, 0Fh
0x180134b3a  add     rcx, 2
0x180134b3e  lea     rax, [rbp+4B0h+var_2D0]
0x180134b45  mov     [rsp+5B0h+var_550], rcx
0x180134b4a  lea     r13, aPlaisetcontrol; "PlaiSetControl"
0x180134b51  mov     [rsp+5B0h+var_558], rax
0x180134b56  mov     r8d, r14d
0x180134b59  mov     [rsp+5B0h+var_560], r12
0x180134b5e  lea     rax, [rbp+4B0h+var_530]
0x180134b62  mov     [rsp+5B0h+var_568], r13
0x180134b67  lea     ecx, [r12-0Bh]
0x180134b6c  mov     [rsp+5B0h+var_570], rcx
0x180134b71  mov     [rsp+5B0h+var_578], rax
0x180134b76  lea     rax, byte_180147320
0x180134b7d  mov     [rsp+5B0h+var_580], 1
0x180134b86  mov     qword ptr [rsp+5B0h+fResume], rax
0x180134b8b  jmp     loc_180134F48
0x180134b90  mov     r15, [rbp+4B0h+var_518]
0x180134b94  mov     r14d, [rsp+5B0h+var_540]
0x180134b99  jmp     loc_180134F75
0x180134b9e  mov     eax, [rbp+4B0h+var_528]
0x180134ba1  mov     r14d, 1
0x180134ba7  test    eax, eax
0x180134ba9  jz      short loc_180134BB4
0x180134bab  imul    r9d, eax, 3E8h
0x180134bb2  jmp     short loc_180134BB8
  ... truncated ...
```
