# PlaiSetControl(void *)

- ea: `0x180134620`
- end: `0x1801350f6`
- name: `?PlaiSetControl@@YAKPEAX@Z`
- size: `2774`
- prototype: `__int64 __fastcall(struct _SET_INSTANCE *Parameter)`
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
  int v6; // ebx
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
  int *v19; // rax
  DWORD LastError; // eax
  int v21; // eax
  unsigned __int64 v22; // rdx
  __int64 v23; // rax
  int v24; // eax
  unsigned __int64 v25; // rdx
  __int64 v26; // rax
  int v27; // r14d
  DWORD v28; // r9d
  DWORD v29; // eax
  unsigned __int64 v30; // rdx
  signed int v31; // eax
  struct _SET_INSTANCE *v32; // r14
  DWORD v33; // eax
  DWORD v34; // eax
  __int64 v35; // rax
  struct _SET_INSTANCE *v36; // r15
  unsigned __int64 v37; // rdx
  __int64 v38; // rax
  unsigned __int64 v39; // rdx
  __int64 v40; // rax
  int v41; // eax
  unsigned __int64 v42; // rdx
  __int64 v43; // rax
  struct _SET_INSTANCE *v44; // rdi
  __int64 v45; // r9
  __int64 v46; // rax
  __int64 v47; // rcx
  __int64 v48; // r9
  __int64 v49; // rcx
  __int64 v50; // rcx
  BOOL fResume[2]; // [rsp+28h] [rbp-D8h]
  __int64 v53; // [rsp+30h] [rbp-D0h]
  __int64 v54; // [rsp+38h] [rbp-C8h]
  __int64 v55; // [rsp+40h] [rbp-C0h]
  __int64 v56; // [rsp+48h] [rbp-B8h]
  __int64 v57; // [rsp+50h] [rbp-B0h]
  int v58; // [rsp+70h] [rbp-90h] BYREF
  HRESULT v59; // [rsp+78h] [rbp-88h] BYREF
  int v60; // [rsp+80h] [rbp-80h] BYREF
  DWORD i; // [rsp+88h] [rbp-78h] BYREF
  struct IDataCollectorSet *v62; // [rsp+90h] [rbp-70h]
  HANDLE WaitableTimerW; // [rsp+98h] [rbp-68h]
  struct _SET_INSTANCE *v64; // [rsp+A0h] [rbp-60h]
  LARGE_INTEGER DueTime; // [rsp+A8h] [rbp-58h] BYREF
  HANDLE Handles[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v67; // [rsp+C0h] [rbp-40h]
  __int128 v68; // [rsp+D0h] [rbp-30h]
  unsigned __int16 v69[64]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int16 v70[64]; // [rsp+160h] [rbp+60h] BYREF
  unsigned __int16 v71[64]; // [rsp+1E0h] [rbp+E0h] BYREF
  unsigned __int16 v72[64]; // [rsp+260h] [rbp+160h] BYREF
  unsigned __int16 v73[64]; // [rsp+2E0h] [rbp+1E0h] BYREF
  unsigned __int16 v74[64]; // [rsp+360h] [rbp+260h] BYREF
  unsigned __int16 v75[64]; // [rsp+3E0h] [rbp+2E0h] BYREF
  unsigned __int16 v76[64]; // [rsp+460h] [rbp+360h] BYREF
  unsigned __int16 v77[64]; // [rsp+4E0h] [rbp+3E0h] BYREF

  v64 = Parameter;
  WaitableTimerW = 0;
  DueTime.QuadPart = 0;
  *(_OWORD *)Handles = 0;
  v2 = 0;
  i = 0;
  v67 = 0;
  v68 = 0;
  v3 = CoInitializeEx(0, 0);
  v5 = -1;
  v6 = v3;
  if ( v3 < 0 )
  {
    v7 = 0;
    v8 = 0;
    v58 = 0;
    v59 = v3;
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
    {
      PlaiWhoAmI(v69, v4);
      v9 = -1;
      do
        ++v9;
      while ( v69[v9] );
      EventingWriteEvent(&g_Eventing, PLA_EVENT_ERROR, 5, &v59, 4, qword_180147320, 1, &v58, 4, "PlaiSetControl", 15);
      v7 = 0;
    }
    goto LABEL_99;
  }
  v7 = (struct IDataCollectorSet *)*((_QWORD *)Parameter + 15);
  v8 = 1;
  Handles[0] = *((HANDLE *)Parameter + 3);
  Handles[1] = *((HANDLE *)Parameter + 9);
  *(_QWORD *)&v67 = *((_QWORD *)Parameter + 8);
  *((_QWORD *)&v67 + 1) = *((_QWORD *)Parameter + 4);
  *(_QWORD *)&v68 = *((_QWORD *)Parameter + 2);
  v10.lpVtbl = v7->lpVtbl;
  v58 = 1;
  v62 = v7;
  ((void (__fastcall *)(struct IDataCollectorSet *))v10.lpVtbl->AddRef)(v7);
  v11 = ((__int64 (__fastcall *)(struct IDataCollectorSet *, DWORD *))v7->lpVtbl->get_Duration)(v7, &i);
  v6 = v11;
  if ( v11 < 0 )
  {
    v59 = 0;
    v58 = v11;
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
    {
      PlaiWhoAmI(v70, v12);
      v13 = -1;
      do
        ++v13;
      while ( v70[v13] );
      EventingWriteEvent(&g_Eventing, PLA_EVENT_ERROR, 5, &v58, 4, qword_180147320, 1, &v59, 4, "PlaiSetControl", 15);
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
        || (LastError = GetLastError(), v21 = PlaiHResultFromWin32(LastError), v6 = v21, v21 >= 0) )
      {
        v14 = 6;
        *((_QWORD *)&v68 + 1) = WaitableTimerW;
        goto LABEL_34;
      }
      v60 = 0;
      v59 = v21;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v72, v22);
        v23 = -1;
        do
          ++v23;
        while ( v72[v23] );
        v18 = &v59;
        v19 = &v60;
        goto LABEL_24;
      }
    }
    else
    {
      v15 = GetLastError();
      v6 = PlaiHResultFromWin32(v15);
      v59 = 0;
      v60 = v6;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v71, v16);
        v17 = -1;
        do
          ++v17;
        while ( v71[v17] );
        v18 = &v60;
        v19 = &v59;
LABEL_24:
        EventingWriteEvent(&g_Eventing, PLA_EVENT_ERROR, 5, v18, 4, qword_180147320, 1, v19, 4, "PlaiSetControl", 15);
        goto LABEL_97;
      }
    }
LABEL_42:
    v8 = v58;
    goto LABEL_99;
  }
  v14 = 5;
LABEL_34:
  v24 = ((__int64 (__fastcall *)(struct IDataCollectorSet *, DWORD *))v7->lpVtbl->get_SegmentMaxDuration)(v7, &i);
  v6 = v24;
  if ( v24 < 0 )
  {
    v60 = 0;
    v59 = v24;
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
    {
      PlaiWhoAmI(v73, v25);
      v26 = -1;
      do
        ++v26;
      while ( v73[v26] );
      EventingWriteEvent(&g_Eventing, PLA_EVENT_ERROR, 5, &v59, 4, qword_180147320, 1, &v60, 4, "PlaiSetControl", 15);
      goto LABEL_96;
    }
    v2 = WaitableTimerW;
    goto LABEL_42;
  }
  v27 = 1;
  if ( i )
    v28 = 1000 * i;
  else
    v28 = -1;
  for ( i = v28; ; v28 = i )
  {
    v29 = WaitForMultipleObjects(v14, Handles, 0, v28);
    if ( !v29 )
      goto LABEL_60;
    if ( v29 == 1 )
      goto LABEL_59;
    if ( v29 != 2 )
    {
      if ( v29 == 3 )
      {
        v32 = v64;
        v6 = PlaiControlCollectorSet(v64, 1);
        if ( v6 >= 0 )
        {
          if ( ResetEvent(*((HANDLE *)v32 + 4)) )
          {
            v6 = 0;
          }
          else
          {
            v33 = GetLastError();
            v6 = PlaiHResultFromWin32(v33);
          }
        }
LABEL_59:
        SetEvent(*((HANDLE *)v64 + 2));
LABEL_60:
        v27 = 0;
        goto LABEL_61;
      }
      if ( v29 - 4 <= 1 )
        goto LABEL_59;
      if ( v29 != 258 )
      {
        if ( v29 == -1 )
        {
          v31 = GetLastError();
          v6 = v31;
          if ( v31 > 0 )
            v6 = (unsigned __int16)v31 | 0x80070000;
        }
        goto LABEL_60;
      }
    }
    v6 = PlaiControlCollectorSet(v64, 2);
    if ( v6 < 0 )
      break;
    if ( ResetEvent(*((HANDLE *)v64 + 8)) )
    {
      v6 = 0;
      goto LABEL_62;
    }
    v34 = GetLastError();
    v6 = PlaiHResultFromWin32(v34);
LABEL_61:
    if ( v6 < 0 )
      break;
LABEL_62:
    if ( !v27 )
      goto LABEL_75;
  }
  v60 = 0;
  v59 = v6;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
  {
    PlaiWhoAmI(v74, v30);
    v35 = -1;
    do
      ++v35;
    while ( v74[v35] );
    EventingWriteEvent(&g_Eventing, PLA_EVENT_ERROR, 5, &v59, 4, qword_180147320, 1, &v60, 4, "PlaiSetControl", 15);
  }
LABEL_75:
  v36 = v64;
  v6 = PlaiWaitForStop(v64);
  if ( v6 >= 0 )
  {
    v6 = PlaiExecuteTask(v62, 1);
    if ( v6 >= 0 )
    {
      v41 = PlaiRunDataManager(v36);
      v6 = v41;
      if ( v41 >= 0 )
        goto LABEL_96;
      v60 = 0;
      v59 = v41;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_96;
      }
      PlaiWhoAmI(v77, v42);
      v43 = -1;
      do
        ++v43;
      while ( v77[v43] );
    }
    else
    {
      v60 = 0;
      v59 = v6;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_96;
      }
      PlaiWhoAmI(v76, v39);
      v40 = -1;
      do
        ++v40;
      while ( v76[v40] );
    }
LABEL_95:
    EventingWriteEvent(&g_Eventing, PLA_EVENT_ERROR, 5, &v59, 4, qword_180147320, 1, &v60, 4, "PlaiSetControl", 15);
    goto LABEL_96;
  }
  v60 = 0;
  v59 = v6;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
  {
    PlaiWhoAmI(v75, v37);
    v38 = -1;
    do
      ++v38;
    while ( v75[v38] );
    goto LABEL_95;
  }
LABEL_96:
  v2 = WaitableTimerW;
LABEL_97:
  v8 = v58;
LABEL_98:
  v7 = v62;
LABEL_99:
  v44 = v64;
  PlaiCloseCollectorSet(v64);
  EnterCriticalSection(&g_cs);
  LeaveCriticalSection(&g_cs);
  SetEvent(*((HANDLE *)v44 + 7));
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000100LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000100LL) )
  {
    v45 = *(_QWORD *)v44;
    if ( *(_QWORD *)v44 )
    {
      v46 = -1;
      do
        ++v46;
      while ( *(_WORD *)(v45 + 2 * v46) );
      v47 = (unsigned int)(2 * v46) + 2LL;
    }
    else
    {
      v47 = 0;
    }
    EventingWriteEvent(&g_Eventing, PLA_EVENT_DCS_STOP, 1, v45, v47, *(_QWORD *)fResume, v53, v54, v55, v56, v57);
  }
  v48 = *(_QWORD *)v44;
  v60 = v6;
  if ( v6 < 0 )
  {
    if ( v48 )
    {
      do
        ++v5;
      while ( *(_WORD *)(v48 + 2 * v5) );
      v50 = (unsigned int)(2 * v5) + 2LL;
    }
    else
    {
      v50 = 0;
    }
    EventingWriteEvent(&g_Eventing, PLA_EVENTLOG_DCS_STOP_FAILURE, 2, v48, v50, &v60, 4, v54, v55, v56, v57);
  }
  else
  {
    if ( v48 )
    {
      do
        ++v5;
      while ( *(_WORD *)(v48 + 2 * v5) );
      v49 = (unsigned int)(2 * v5) + 2LL;
    }
    else
    {
      v49 = 0;
    }
    EventingWriteEvent(&g_Eventing, PLA_EVENTLOG_DCS_STOP, 1, v48, v49, *(_QWORD *)fResume, v53, v54, v55, v56, v57);
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
0x180134742  lea     rax, qword_180147320
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
0x180134888  lea     rax, qword_180147320
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
0x1801349a5  lea     rax, qword_180147320
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
0x180134b76  lea     rax, qword_180147320
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
