# SDataCollectorSet::Start(short)

- ea: `0x1800430d0`
- end: `0x180043e02`
- name: `?Start@SDataCollectorSet@@UEAAJF@Z`
- size: `3378`
- prototype: `__int64 __fastcall(SDataCollectorSet *__hidden this, __int16)`
- caller_count: `0`
- callee_count: `16`
- tags: `authz_impersonation, service_task`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x1800106d0`
- `0x180012ef0`
- `0x180015f98`
- `0x1800182a4`
- `0x1800198b0`
- `0x18002b3a0`
- `0x18003c808`
- `0x1800430d0`
- `0x180052754`
- `0x1800768c4`
- `0x180097594`
- `0x1800fc514`
- `0x18013aee0`
- `0x18013c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004345a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004345a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180043d31`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180043d31`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800431e1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800431e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180043dd7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180043dd7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800434e4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800434e4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800434ec`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800434ec`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18004344c`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18004344c`
- `wevtapi!EvtClose` at `0x180043dc9`
- `wevtapi!EvtClose` at `0x180043dc9`
- `OLEAUT32!__imp_VariantInit` at `0x180043145`
- `OLEAUT32!__imp_VariantInit` at `0x180043145`
- `OLEAUT32!__imp_VariantClear` at `0x180043d3b`
- `OLEAUT32!__imp_VariantClear` at `0x180043d3b`

## pseudocode

```c
__int64 __fastcall SDataCollectorSet::Start(SDataCollectorSet *this, __int16 a2)
{
  void *v3; // r13
  void *v4; // r12
  unsigned __int16 *v5; // rdi
  unsigned __int16 *v6; // r14
  int v8; // eax
  int v9; // ebx
  __int64 v10; // rax
  int RegisteredTask; // eax
  __int64 v12; // rax
  __int64 v13; // rax
  DWORD LastError; // eax
  int v15; // eax
  __int64 v16; // rax
  DWORD CurrentThreadId; // ebx
  DWORD CurrentProcessId; // eax
  int v19; // eax
  __int64 v20; // rax
  unsigned __int16 *v21; // rax
  __int64 v22; // rax
  int v23; // eax
  const char *v24; // r8
  int v25; // r9d
  __int64 v26; // rax
  int v27; // eax
  __int64 v28; // rax
  __int64 v29; // rax
  int started; // eax
  __int64 v31; // rax
  int v32; // eax
  __int64 v33; // rax
  __int64 v34; // rax
  struct IRegisteredTaskVtbl *lpVtbl; // rax
  __int64 v36; // rax
  int v37; // eax
  __int64 v38; // rax
  int v39; // eax
  __int64 v40; // rax
  int v41; // eax
  __int64 v42; // rax
  int TraceDataCollectors; // eax
  __int64 v44; // rax
  int v46; // [rsp+20h] [rbp-E0h]
  int v47; // [rsp+20h] [rbp-E0h]
  __int64 v48; // [rsp+48h] [rbp-B8h]
  __int64 v49; // [rsp+50h] [rbp-B0h]
  int v50; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 *v51; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 *v52; // [rsp+80h] [rbp-80h]
  struct IRegisteredTask *v53; // [rsp+88h] [rbp-78h] BYREF
  int v54; // [rsp+90h] [rbp-70h] BYREF
  BSTR bstrString; // [rsp+98h] [rbp-68h] BYREF
  void *v56; // [rsp+A0h] [rbp-60h] BYREF
  void *v57; // [rsp+A8h] [rbp-58h] BYREF
  struct IDataCollectorCollection *v58; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v59; // [rsp+B8h] [rbp-48h]
  LARGE_INTEGER PerformanceCount; // [rsp+C0h] [rbp-40h] BYREF
  double v61; // [rsp+C8h] [rbp-38h] BYREF
  VARIANTARG pvarg; // [rsp+D0h] [rbp-30h] BYREF
  VARIANTARG v63; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int16 v64[64]; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int16 v65[64]; // [rsp+190h] [rbp+90h] BYREF
  unsigned __int16 v66[64]; // [rsp+210h] [rbp+110h] BYREF
  unsigned __int16 v67[64]; // [rsp+290h] [rbp+190h] BYREF
  unsigned __int16 v68[64]; // [rsp+310h] [rbp+210h] BYREF
  unsigned __int16 v69[64]; // [rsp+390h] [rbp+290h] BYREF
  unsigned __int16 v70[64]; // [rsp+410h] [rbp+310h] BYREF
  unsigned __int16 v71[64]; // [rsp+490h] [rbp+390h] BYREF
  unsigned __int16 v72[64]; // [rsp+510h] [rbp+410h] BYREF
  unsigned __int16 v73[64]; // [rsp+590h] [rbp+490h] BYREF
  unsigned __int16 v74[64]; // [rsp+610h] [rbp+510h] BYREF
  unsigned __int16 v75[64]; // [rsp+690h] [rbp+590h] BYREF
  unsigned __int16 v76[64]; // [rsp+710h] [rbp+610h] BYREF
  unsigned __int16 v77[64]; // [rsp+790h] [rbp+690h] BYREF
  unsigned __int16 v78[64]; // [rsp+810h] [rbp+710h] BYREF
  unsigned __int16 v79[64]; // [rsp+890h] [rbp+790h] BYREF
  unsigned __int16 v80[64]; // [rsp+910h] [rbp+810h] BYREF

  v61 = 0.0;
  PerformanceCount.QuadPart = 0;
  v53 = 0;
  bstrString = 0;
  v3 = 0;
  v59 = 0;
  v4 = 0;
  v56 = 0;
  v5 = 0;
  v57 = 0;
  v6 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  v54 = 0;
  v58 = 0;
  VariantInit(&pvarg);
  v50 = *((_DWORD *)this + 14);
  pvarg.llVal = 0;
  v51 = (unsigned __int16 *)this;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000400LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000400LL) )
  {
    EventingWriteEvent(&g_Eventing, PLA_EVENT_METHOD, 3, "SDataCollectorSet::Start", 25, &v51, 8, &v50, 4, v48, v49);
  }
  if ( *((_DWORD *)this + 2) )
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  v8 = (*(__int64 (__fastcall **)(SDataCollectorSet *, BSTR *))(*(_QWORD *)this + 160LL))(this, &bstrString);
  v9 = v8;
  if ( v8 >= 0 )
  {
    RegisteredTask = PlaTaskService::GetRegisteredTask((SDataCollectorSet *)((char *)this + 272), bstrString, &v53);
    v9 = RegisteredTask;
    if ( RegisteredTask < 0 )
    {
      v50 = RegisteredTask;
      LODWORD(v51) = 0;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_133;
      }
      PlaiWhoAmI(v65, 0x4000000000000800uLL);
      v12 = -1;
      do
        ++v12;
      while ( v65[v12] );
LABEL_21:
      EventingWriteEvent(
        &g_Eventing,
        PLA_EVENT_ERROR,
        5,
        &v50,
        4,
        qword_180147320,
        1,
        &v51,
        4,
        "SDataCollectorSet::Start",
        25);
LABEL_14:
      v6 = 0;
      goto LABEL_133;
    }
    v51 = (unsigned __int16 *)PlaiAlloc(0x800u, 1, 0, qword_180147320, v46);
    v5 = v51;
    if ( !v51 )
    {
      v9 = -2147024882;
      LODWORD(v51) = 0;
      v50 = -2147024882;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_14;
      }
      PlaiWhoAmI(v66, 0x4000000000000800uLL);
      v13 = -1;
      do
        ++v13;
      while ( v66[v13] );
      goto LABEL_21;
    }
    if ( !QueryPerformanceCounter(&PerformanceCount) )
    {
      LastError = GetLastError();
      v15 = PlaiHResultFromWin32(LastError);
      v9 = v15;
      if ( v15 < 0 )
      {
        v50 = v15;
        LODWORD(v51) = 0;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_14;
        }
        PlaiWhoAmI(v67, 0x4000000000000800uLL);
        v16 = -1;
        do
          ++v16;
        while ( v67[v16] );
        goto LABEL_21;
      }
    }
    CurrentThreadId = GetCurrentThreadId();
    CurrentProcessId = GetCurrentProcessId();
    v5 = v51;
    v47 = CurrentThreadId;
    v19 = StringCchPrintfW(v51, 0x400u, L"0x%x_0x%x_0x%I64x", CurrentProcessId);
    v9 = v19;
    if ( v19 < 0 )
    {
      v50 = v19;
      LODWORD(v51) = 0;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_14;
      }
      PlaiWhoAmI(v68, 0x4000000000000800uLL);
      v20 = -1;
      do
        ++v20;
      while ( v68[v20] );
      goto LABEL_21;
    }
    v21 = (unsigned __int16 *)PlaiAlloc(0x800u, 1, 0, qword_180147320, v47);
    v52 = v21;
    if ( v21 )
    {
      v23 = StringCchPrintfW(v21, 0x400u, L"%s", v5);
      v9 = v23;
      if ( v23 < 0 )
      {
        v50 = v23;
        LODWORD(v51) = 0;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_132;
        }
        PlaiWhoAmI(v70, 0x4000000000000800uLL);
        v26 = -1;
        do
          ++v26;
        while ( v70[v26] );
        goto LABEL_131;
      }
      v27 = PlaiSetVariantEx(v52, &pvarg, v24, v25);
      v9 = v27;
      if ( v27 < 0 )
      {
        v50 = v27;
        LODWORD(v51) = 0;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_132;
        }
        PlaiWhoAmI(v71, 0x4000000000000800uLL);
        v28 = -1;
        do
          ++v28;
        while ( v71[v28] );
        goto LABEL_131;
      }
      v9 = ((__int64 (__fastcall *)(struct IRegisteredTask *, double *))v53->lpVtbl->get_LastRunTime)(v53, &v61);
      if ( v9 < 0 )
      {
        v50 = v9;
        LODWORD(v51) = 0;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_132;
        }
        PlaiWhoAmI(v72, 0x4000000000000800uLL);
        v29 = -1;
        do
          ++v29;
        while ( v72[v29] );
        goto LABEL_131;
      }
      if ( a2 )
      {
        started = PlaiRegisterForStartNotification(bstrString, v5, &v57, &v56);
        v9 = started;
        if ( started < 0 )
        {
          v50 = started;
          LODWORD(v51) = 0;
          if ( (_DWORD)xmmword_180169738
            && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
            && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
          {
            PlaiWhoAmI(v73, 0x4000000000000800uLL);
            v31 = -1;
            do
              ++v31;
            while ( v73[v31] );
            EventingWriteEvent(
              &g_Eventing,
              PLA_EVENT_ERROR,
              5,
              &v50,
              4,
              qword_180147320,
              1,
              &v51,
              4,
              "SDataCollectorSet::Start",
              25);
          }
          v3 = v56;
          v4 = v57;
          goto LABEL_132;
        }
        v3 = v56;
        v4 = v57;
      }
      v32 = ((__int64 (__fastcall *)(struct IRegisteredTask *, int *))v53->lpVtbl->get_State)(v53, &v54);
      v9 = v32;
      if ( v32 < 0 )
      {
        v50 = v32;
        LODWORD(v51) = 0;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_132;
        }
        PlaiWhoAmI(v74, 0x4000000000000800uLL);
        v33 = -1;
        do
          ++v33;
        while ( v74[v33] );
        goto LABEL_131;
      }
      if ( v54 != 3 )
      {
        v9 = -2147020576;
        LODWORD(v51) = 0;
        v50 = -2147020576;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_132;
        }
        PlaiWhoAmI(v75, 0x4000000000000800uLL);
        v34 = -1;
        do
          ++v34;
        while ( v75[v34] );
        goto LABEL_131;
      }
      lpVtbl = v53->lpVtbl;
      v63 = pvarg;
      v9 = ((__int64 (__fastcall *)(struct IRegisteredTask *, VARIANTARG *, __int64))lpVtbl->RunEx)(v53, &v63, 2);
      if ( v9 < 0 )
      {
        v50 = v9;
        LODWORD(v51) = 0;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_132;
        }
        PlaiWhoAmI(v76, 0x4000000000000800uLL);
        v36 = -1;
        do
          ++v36;
        while ( v76[v36] );
        goto LABEL_131;
      }
      if ( !a2 )
        goto LABEL_118;
      v37 = PlaiWaitForTaskStart(v53, &v61);
      v9 = v37;
      if ( v37 < 0 )
      {
        LODWORD(v51) = 0;
        v50 = v37;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_132;
        }
        PlaiWhoAmI(v77, 0x4000000000000800uLL);
        v38 = -1;
        do
          ++v38;
        while ( v77[v38] );
        goto LABEL_131;
      }
      v39 = PlaiWaitForStartNotification(v4, v3);
      v9 = v39;
      if ( v39 < 0 )
      {
        LODWORD(v51) = 0;
        v50 = v39;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_132;
        }
        PlaiWhoAmI(v78, 0x4000000000000800uLL);
        v40 = -1;
        do
          ++v40;
        while ( v78[v40] );
      }
      else
      {
LABEL_118:
        v41 = (*(__int64 (__fastcall **)(SDataCollectorSet *, struct IDataCollectorCollection **))(*(_QWORD *)this + 56LL))(
                this,
                &v58);
        v9 = v41;
        if ( v41 >= 0 )
        {
          TraceDataCollectors = PlaiQueryTraceDataCollectors(v58);
          v9 = TraceDataCollectors;
          if ( TraceDataCollectors >= 0 )
            goto LABEL_132;
          LODWORD(v51) = 0;
          v50 = TraceDataCollectors;
          if ( !(_DWORD)xmmword_180169738
            || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            goto LABEL_132;
          }
          PlaiWhoAmI(v80, 0x4000000000000800uLL);
          v44 = -1;
          do
            ++v44;
          while ( v80[v44] );
        }
        else
        {
          LODWORD(v51) = 0;
          v50 = v41;
          if ( !(_DWORD)xmmword_180169738
            || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            goto LABEL_132;
          }
          PlaiWhoAmI(v79, 0x4000000000000800uLL);
          v42 = -1;
          do
            ++v42;
          while ( v79[v42] );
        }
      }
    }
    else
    {
      v9 = -2147024882;
      LODWORD(v51) = 0;
      v50 = -2147024882;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_132;
      }
      PlaiWhoAmI(v69, 0x4000000000000800uLL);
      v22 = -1;
      do
        ++v22;
      while ( v69[v22] );
    }
LABEL_131:
    EventingWriteEvent(
      &g_Eventing,
      PLA_EVENT_ERROR,
      5,
      &v50,
      4,
      qword_180147320,
      1,
      &v51,
      4,
      "SDataCollectorSet::Start",
      25);
LABEL_132:
    v6 = v52;
    goto LABEL_133;
  }
  LODWORD(v51) = v8;
  v50 = 0;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
  {
    PlaiWhoAmI(v64, 0x4000000000000800uLL);
    v10 = -1;
    do
      ++v10;
    while ( v64[v10] );
    EventingWriteEvent(
      &g_Eventing,
      PLA_EVENT_ERROR,
      5,
      &v51,
      4,
      qword_180147320,
      1,
      &v50,
      4,
      "SDataCollectorSet::Start",
      25);
    goto LABEL_14;
  }
LABEL_133:
  if ( *((_DWORD *)this + 2) )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  VariantClear(&pvarg);
  pvarg.llVal = 0;
  if ( v5 )
    PlaiFree(v5, 1);
  if ( v6 )
    PlaiFree(v6, 1);
  PlaiFreeString(bstrString);
  bstrString = 0;
  if ( v53 )
  {
    ((void (__fastcall *)(struct IRegisteredTask *))v53->lpVtbl->Release)(v53);
    v53 = 0;
  }
  if ( v59 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 16LL))(v59);
    v59 = 0;
  }
  if ( v58 )
  {
    ((void (__fastcall *)(struct IDataCollectorCollection *))v58->lpVtbl->Release)(v58);
    v58 = 0;
  }
  if ( v3 )
    EvtClose(v3);
  if ( v4 )
    CloseHandle(v4);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800430d0  push    rbp
0x1800430d2  push    rbx
0x1800430d3  push    rsi
0x1800430d4  push    rdi
0x1800430d5  push    r12
0x1800430d7  push    r13
0x1800430d9  push    r14
0x1800430db  push    r15
0x1800430dd  lea     rbp, [rsp-8A8h]
0x1800430e5  sub     rsp, 9A8h
0x1800430ec  mov     rax, cs:__security_cookie
0x1800430f3  xor     rax, rsp
0x1800430f6  mov     [rbp+8E0h+var_50], rax
0x1800430fd  xor     ebx, ebx
0x1800430ff  xorps   xmm0, xmm0
0x180043102  mov     r15, rcx
0x180043105  movsd   [rbp+8E0h+var_918], xmm0
0x18004310a  xor     eax, eax
0x18004310c  mov     qword ptr [rbp+8E0h+PerformanceCount], rbx
0x180043110  lea     rcx, [rbp+8E0h+pvarg]; pvarg
0x180043114  mov     [rbp+8E0h+var_958], rbx
0x180043118  mov     [rbp+8E0h+bstrString], rbx
0x18004311c  mov     r13d, ebx
0x18004311f  mov     [rbp+8E0h+var_928], rbx
0x180043123  mov     r12d, ebx
0x180043126  mov     [rbp+8E0h+var_940], rbx
0x18004312a  mov     edi, ebx
0x18004312c  mov     [rbp+8E0h+var_938], rbx
0x180043130  mov     r14d, ebx
0x180043133  movups  xmmword ptr [rbp+8E0h+pvarg], xmm0
0x180043137  mov     qword ptr [rbp+8E0h+pvarg+10h], rax
0x18004313b  movzx   esi, dx
0x18004313e  mov     [rbp+8E0h+var_950], ebx
0x180043141  mov     [rbp+8E0h+var_930], rbx
0x180043145  call    cs:__imp_VariantInit
0x18004314b  cmp     dword ptr cs:xmmword_180169738, ebx
0x180043151  mov     eax, [r15+38h]
0x180043155  mov     [rsp+9E0h+var_970], eax
0x180043159  mov     qword ptr [rbp+8E0h+pvarg+8], rbx
0x18004315d  mov     [rsp+9E0h+var_968], r15
0x180043162  jz      short loc_1800431D7
0x180043164  mov     rdx, 4000000000000400h
0x18004316e  test    qword ptr cs:xmmword_180169738+8, rdx
0x180043175  jz      short loc_1800431D7
0x180043177  mov     rax, cs:qword_180169748
0x18004317e  and     rax, rdx
0x180043181  cmp     cs:qword_180169748, rax
0x180043188  jnz     short loc_1800431D7
0x18004318a  mov     [rsp+9E0h+var_9A0], 4
0x180043193  lea     rax, [rsp+9E0h+var_970]
0x180043198  mov     [rsp+9E0h+var_9A8], rax
0x18004319d  lea     r9, aSdatacollector_0; "SDataCollectorSet::Start"
0x1800431a4  lea     rax, [rsp+9E0h+var_968]
0x1800431a9  mov     [rsp+9E0h+var_9B0], 8
0x1800431b2  mov     [rsp+9E0h+var_9B8], rax
0x1800431b7  lea     r8d, [rbx+3]
0x1800431bb  lea     rdx, PLA_EVENT_METHOD
0x1800431c2  mov     qword ptr [rsp+9E0h+var_9C0], 19h; int
0x1800431cb  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1800431d2  call    EventingWriteEvent
0x1800431d7  cmp     [r15+8], ebx
0x1800431db  jz      short loc_1800431E7
0x1800431dd  lea     rcx, [r15+10h]; lpCriticalSection
0x1800431e1  call    cs:__imp_EnterCriticalSection
0x1800431e7  mov     rax, [r15]
0x1800431ea  lea     rdx, [rbp+8E0h+bstrString]
0x1800431ee  mov     rcx, r15
0x1800431f1  mov     rax, [rax+0A0h]
0x1800431f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800431fd  mov     ebx, eax
0x1800431ff  test    eax, eax
0x180043201  jns     loc_1800432E1
0x180043207  xor     esi, esi
0x180043209  mov     dword ptr [rsp+9E0h+var_968], eax
0x18004320d  cmp     dword ptr cs:xmmword_180169738, esi
0x180043213  mov     [rsp+9E0h+var_970], esi
0x180043217  jz      loc_180043D27
0x18004321d  mov     rdx, 4000000000000800h; unsigned __int64
0x180043227  test    qword ptr cs:xmmword_180169738+8, rdx
0x18004322e  jz      loc_180043D27
0x180043234  mov     rax, cs:qword_180169748
0x18004323b  and     rax, rdx
0x18004323e  cmp     cs:qword_180169748, rax
0x180043245  jnz     loc_180043D27
0x18004324b  lea     rcx, [rbp+8E0h+var_8D0]; unsigned __int16 *
0x18004324f  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180043254  lea     rcx, [rbp+8E0h+var_8D0]
0x180043258  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004325c  inc     rax
0x18004325f  cmp     [rcx+rax*2], si
0x180043263  jnz     short loc_18004325C
0x180043265  lea     ecx, [rax+rax]
0x180043268  lea     rax, [rbp+8E0h+var_8D0]
0x18004326c  add     rcx, 2
0x180043270  mov     [rsp+9E0h+var_980], rcx
0x180043275  lea     r14, qword_180147320
0x18004327c  mov     [rsp+9E0h+var_988], rax
0x180043281  lea     r9, [rsp+9E0h+var_968]
0x180043286  lea     rax, aSdatacollector_0; "SDataCollectorSet::Start"
0x18004328d  mov     [rsp+9E0h+var_990], 19h
0x180043296  mov     [rsp+9E0h+var_998], rax
0x18004329b  lea     rax, [rsp+9E0h+var_970]
0x1800432a0  mov     ecx, 4
0x1800432a5  lea     rdx, PLA_EVENT_ERROR
0x1800432ac  mov     [rsp+9E0h+var_9A0], rcx
0x1800432b1  mov     [rsp+9E0h+var_9A8], rax
0x1800432b6  mov     [rsp+9E0h+var_9B0], 1
0x1800432bf  lea     r8d, [rcx+1]
0x1800432c3  mov     [rsp+9E0h+var_9B8], r14
0x1800432c8  mov     qword ptr [rsp+9E0h+var_9C0], rcx
0x1800432cd  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1800432d4  call    EventingWriteEvent
0x1800432d9  mov     r14, rsi
0x1800432dc  jmp     loc_180043D27
0x1800432e1  mov     rdx, [rbp+8E0h+bstrString]; unsigned __int16 *
0x1800432e5  lea     rcx, [r15+110h]; this
0x1800432ec  lea     r8, [rbp+8E0h+var_958]; struct IRegisteredTask **
0x1800432f0  call    ?GetRegisteredTask@PlaTaskService@@QEAAJPEAGPEAPEAUIRegisteredTask@@@Z; PlaTaskService::GetRegisteredTask(ushort *,IRegisteredTask * *)
0x1800432f5  mov     ebx, eax
0x1800432f7  test    eax, eax
0x1800432f9  jns     loc_1800433A6
0x1800432ff  xor     esi, esi
0x180043301  mov     [rsp+9E0h+var_970], eax
0x180043305  cmp     dword ptr cs:xmmword_180169738, esi
0x18004330b  mov     dword ptr [rsp+9E0h+var_968], esi
0x18004330f  jz      loc_180043D27
0x180043315  mov     rdx, 4000000000000800h; unsigned __int64
0x18004331f  test    qword ptr cs:xmmword_180169738+8, rdx
0x180043326  jz      loc_180043D27
0x18004332c  mov     rax, cs:qword_180169748
0x180043333  and     rax, rdx
0x180043336  cmp     cs:qword_180169748, rax
0x18004333d  jnz     loc_180043D27
0x180043343  lea     rcx, [rbp+8E0h+var_850]; unsigned __int16 *
0x18004334a  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18004334f  lea     rcx, [rbp+8E0h+var_850]
0x180043356  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004335a  inc     rax
0x18004335d  cmp     [rcx+rax*2], si
0x180043361  jnz     short loc_18004335A
0x180043363  lea     ecx, [rax+rax]
0x180043366  lea     rax, [rbp+8E0h+var_850]
0x18004336d  lea     r14, qword_180147320
0x180043374  add     rcx, 2
0x180043378  lea     r9, [rsp+9E0h+var_970]
0x18004337d  mov     [rsp+9E0h+var_980], rcx
0x180043382  mov     [rsp+9E0h+var_988], rax
0x180043387  lea     rax, aSdatacollector_0; "SDataCollectorSet::Start"
0x18004338e  mov     [rsp+9E0h+var_990], 19h
0x180043397  mov     [rsp+9E0h+var_998], rax
0x18004339c  lea     rax, [rsp+9E0h+var_968]
0x1800433a1  jmp     loc_1800432A0
0x1800433a6  xor     r8d, r8d; int
0x1800433a9  lea     r14, qword_180147320
0x1800433b0  mov     r9, r14; char *
0x1800433b3  mov     ecx, 800h; dwBytes
0x1800433b8  lea     edx, [r8+1]; int
0x1800433bc  call    ?PlaiAlloc@@YAPEAX_KHHPEBDH@Z; PlaiAlloc(unsigned __int64,int,int,char const *,int)
0x1800433c1  mov     [rsp+9E0h+var_968], rax
0x1800433c6  mov     rdi, rax
0x1800433c9  test    rax, rax
0x1800433cc  jnz     short loc_180043448
0x1800433ce  xor     esi, esi
0x1800433d0  mov     ecx, 8007000Eh
0x1800433d5  cmp     dword ptr cs:xmmword_180169738, esi
0x1800433db  mov     ebx, ecx
0x1800433dd  mov     dword ptr [rsp+9E0h+var_968], esi
0x1800433e1  mov     [rsp+9E0h+var_970], ecx
0x1800433e5  jz      loc_1800432D9
0x1800433eb  mov     rdx, 4000000000000800h; unsigned __int64
0x1800433f5  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800433fc  jz      loc_1800432D9
0x180043402  mov     rax, cs:qword_180169748
0x180043409  and     rax, rdx
0x18004340c  cmp     cs:qword_180169748, rax
0x180043413  jnz     loc_1800432D9
0x180043419  lea     rcx, [rbp+8E0h+var_7D0]; unsigned __int16 *
0x180043420  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180043425  lea     rcx, [rbp+8E0h+var_7D0]
0x18004342c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180043430  inc     rax
0x180043433  cmp     [rcx+rax*2], si
0x180043437  jnz     short loc_180043430
0x180043439  lea     ecx, [rax+rax]
0x18004343c  lea     rax, [rbp+8E0h+var_7D0]
0x180043443  jmp     loc_180043374
0x180043448  lea     rcx, [rbp+8E0h+PerformanceCount]; lpPerformanceCount
0x18004344c  call    cs:__imp_QueryPerformanceCounter
0x180043452  test    eax, eax
0x180043454  jnz     loc_1800434E0
0x18004345a  call    cs:__imp_GetLastError
0x180043460  mov     ecx, eax; unsigned int
0x180043462  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x180043467  mov     ebx, eax
0x180043469  test    eax, eax
0x18004346b  jns     short loc_1800434E0
0x18004346d  xor     esi, esi
0x18004346f  mov     [rsp+9E0h+var_970], eax
0x180043473  cmp     dword ptr cs:xmmword_180169738, esi
0x180043479  mov     dword ptr [rsp+9E0h+var_968], esi
0x18004347d  jz      loc_1800432D9
0x180043483  mov     rdx, 4000000000000800h; unsigned __int64
0x18004348d  test    qword ptr cs:xmmword_180169738+8, rdx
0x180043494  jz      loc_1800432D9
0x18004349a  mov     rax, cs:qword_180169748
0x1800434a1  and     rax, rdx
0x1800434a4  cmp     cs:qword_180169748, rax
0x1800434ab  jnz     loc_1800432D9
0x1800434b1  lea     rcx, [rbp+8E0h+var_750]; unsigned __int16 *
0x1800434b8  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800434bd  lea     rcx, [rbp+8E0h+var_750]
0x1800434c4  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800434c8  inc     rax
0x1800434cb  cmp     [rcx+rax*2], si
0x1800434cf  jnz     short loc_1800434C8
0x1800434d1  lea     ecx, [rax+rax]
0x1800434d4  lea     rax, [rbp+8E0h+var_750]
0x1800434db  jmp     loc_180043374
0x1800434e0  mov     rdi, qword ptr [rbp+8E0h+PerformanceCount]
0x1800434e4  call    cs:__imp_GetCurrentThreadId
0x1800434ea  mov     ebx, eax
0x1800434ec  call    cs:__imp_GetCurrentProcessId
0x1800434f2  mov     [rsp+9E0h+var_9B8], rdi
0x1800434f7  lea     r8, a0xX0xX0xI64x; "0x%x_0x%x_0x%I64x"
0x1800434fe  mov     rdi, [rsp+9E0h+var_968]
0x180043503  mov     r9d, eax
0x180043506  mov     rcx, rdi; unsigned __int16 *
0x180043509  mov     [rsp+9E0h+var_9C0], ebx; int
0x18004350d  mov     edx, 400h; unsigned __int64
0x180043512  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180043517  mov     ebx, eax
0x180043519  test    eax, eax
0x18004351b  jns     short loc_180043590
0x18004351d  xor     esi, esi
0x18004351f  mov     [rsp+9E0h+var_970], eax
0x180043523  cmp     dword ptr cs:xmmword_180169738, esi
0x180043529  mov     dword ptr [rsp+9E0h+var_968], esi
0x18004352d  jz      loc_1800432D9
0x180043533  mov     rdx, 4000000000000800h; unsigned __int64
0x18004353d  test    qword ptr cs:xmmword_180169738+8, rdx
0x180043544  jz      loc_1800432D9
0x18004354a  mov     rax, cs:qword_180169748
0x180043551  and     rax, rdx
0x180043554  cmp     cs:qword_180169748, rax
0x18004355b  jnz     loc_1800432D9
0x180043561  lea     rcx, [rbp+8E0h+var_6D0]; unsigned __int16 *
0x180043568  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18004356d  lea     rcx, [rbp+8E0h+var_6D0]
0x180043574  or      rax, 0FFFFFFFFFFFFFFFFh
0x180043578  inc     rax
0x18004357b  cmp     [rcx+rax*2], si
0x18004357f  jnz     short loc_180043578
0x180043581  lea     ecx, [rax+rax]
0x180043584  lea     rax, [rbp+8E0h+var_6D0]
0x18004358b  jmp     loc_180043374
0x180043590  xor     r8d, r8d; int
0x180043593  mov     r9, r14; char *
0x180043596  mov     ecx, 800h; dwBytes
0x18004359b  lea     edx, [r8+1]; int
0x18004359f  call    ?PlaiAlloc@@YAPEAX_KHHPEBDH@Z; PlaiAlloc(unsigned __int64,int,int,char const *,int)
0x1800435a4  mov     [rbp+8E0h+var_960], rax
0x1800435a8  test    rax, rax
0x1800435ab  jnz     short loc_180043627
0x1800435ad  xor     esi, esi
0x1800435af  mov     ecx, 8007000Eh
0x1800435b4  cmp     dword ptr cs:xmmword_180169738, esi
0x1800435ba  mov     ebx, ecx
0x1800435bc  mov     dword ptr [rsp+9E0h+var_968], esi
0x1800435c0  mov     [rsp+9E0h+var_970], ecx
0x1800435c4  jz      loc_180043D23
0x1800435ca  mov     rdx, 4000000000000800h; unsigned __int64
0x1800435d4  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800435db  jz      loc_180043D23
0x1800435e1  mov     rax, cs:qword_180169748
0x1800435e8  and     rax, rdx
0x1800435eb  cmp     cs:qword_180169748, rax
0x1800435f2  jnz     loc_180043D23
0x1800435f8  lea     rcx, [rbp+8E0h+var_650]; unsigned __int16 *
0x1800435ff  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180043604  lea     rcx, [rbp+8E0h+var_650]
0x18004360b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004360f  inc     rax
0x180043612  cmp     [rcx+rax*2], si
0x180043616  jnz     short loc_18004360F
0x180043618  lea     ecx, [rax+rax]
0x18004361b  lea     rax, [rbp+8E0h+var_650]
0x180043622  jmp     loc_180043CBD
0x180043627  mov     r9, rdi
0x18004362a  lea     r8, aS; "%s"
0x180043631  mov     edx, 400h; unsigned __int64
0x180043636  mov     rcx, rax; unsigned __int16 *
0x180043639  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004363e  mov     ebx, eax
0x180043640  test    eax, eax
0x180043642  jns     short loc_1800436B7
0x180043644  xor     esi, esi
0x180043646  mov     [rsp+9E0h+var_970], eax
0x18004364a  cmp     dword ptr cs:xmmword_180169738, esi
0x180043650  mov     dword ptr [rsp+9E0h+var_968], esi
0x180043654  jz      loc_180043D23
  ... truncated ...
```
