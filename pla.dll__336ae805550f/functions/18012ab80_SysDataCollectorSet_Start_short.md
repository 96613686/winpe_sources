# SysDataCollectorSet::Start(short)

- ea: `0x18012ab80`
- end: `0x18012c15b`
- name: `?Start@SysDataCollectorSet@@UEAAJF@Z`
- size: `5595`
- prototype: `__int64 __fastcall(SysDataCollectorSet *__hidden this, __int16)`
- caller_count: `0`
- callee_count: `26`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x1800106d0`
- `0x180012ef0`
- `0x180015f98`
- `0x1800182a4`
- `0x180018420`
- `0x1800198b0`
- `0x180024ea0`
- `0x180026850`
- `0x18002b3a0`
- `0x18003ca10`
- `0x180052754`
- `0x1800768c4`
- `0x180097594`
- `0x1800a2908`
- `0x1800b62e0`
- `0x1800d8af4`
- `0x1800e9cf0`
- `0x1800edc58`
- `0x1800f1dec`
- `0x1800fae54`
- `0x1800fc514`
- `0x18012ab80`
- `0x18013aee0`
- `0x18013c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012b8c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18012b8c9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18012c003`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18012c003`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18012acb6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18012acb6`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18012b4e0`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18012b4e0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18012c0c3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18012c0c3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18012b952`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18012b952`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18012b95a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18012b95a`
- `RPCRT4!UuidCreate` at `0x18012b373`
- `RPCRT4!UuidCreate` at `0x18012b373`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18012b8bb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18012b8bb`
- `wevtapi!EvtClose` at `0x18012c0b5`
- `wevtapi!EvtClose` at `0x18012c0b5`

## pseudocode

```c
__int64 __fastcall SysDataCollectorSet::Start(SysDataCollectorSet *this, __int16 a2)
{
  EVT_HANDLE v4; // r15
  HANDLE v5; // rdi
  unsigned __int16 *v6; // r12
  int v7; // eax
  __int64 v8; // r14
  int v9; // ebx
  __int64 v10; // rax
  SysDataCollectorSet **v11; // r9
  SysDataCollectorSet **v12; // rax
  int Task; // eax
  __int64 v14; // rax
  int v15; // eax
  __int64 v16; // rax
  const char *v17; // rdx
  int v18; // r8d
  unsigned __int16 *v19; // rax
  __int64 v20; // rax
  int v21; // eax
  __int64 v22; // rax
  enum _TASK_LOGON_TYPE v23; // edi
  int v24; // eax
  __int64 v25; // rax
  const char *v26; // rdx
  int v27; // r8d
  __int64 v28; // rax
  int v29; // eax
  __int64 v30; // rax
  int v31; // eax
  __int64 v32; // rax
  RPC_STATUS v33; // eax
  __int64 v34; // rax
  void *v35; // rax
  void *v36; // rbx
  __int64 v37; // rax
  __int64 v38; // rax
  __int64 v39; // rax
  int v40; // eax
  const char *v41; // rdx
  int v42; // r8d
  __int64 v43; // rax
  OLECHAR *v44; // rax
  __int64 v45; // rax
  int v46; // eax
  __int64 v47; // rax
  int v48; // eax
  __int64 v49; // rax
  DWORD LastError; // eax
  int v51; // eax
  __int64 v52; // rax
  DWORD CurrentThreadId; // ebx
  DWORD CurrentProcessId; // eax
  unsigned __int16 *v55; // rdi
  int v56; // eax
  __int64 v57; // rax
  void *v58; // rax
  __int64 v59; // rax
  int v60; // eax
  const char *v61; // r8
  int v62; // r9d
  __int64 v63; // rax
  int v64; // eax
  __int64 v65; // rax
  __int64 v66; // rax
  int started; // eax
  __int64 v68; // rax
  struct IRegisteredTaskVtbl *lpVtbl; // rax
  __int64 v70; // rax
  int v71; // eax
  __int64 v72; // rax
  int v73; // eax
  __int64 v74; // rax
  int v75; // eax
  __int64 v76; // rax
  int TraceDataCollectors; // eax
  __int64 v78; // rax
  BSTR v79; // rax
  __int64 i; // rcx
  int v82; // [rsp+20h] [rbp-E0h]
  int v83; // [rsp+20h] [rbp-E0h]
  int v84; // [rsp+20h] [rbp-E0h]
  int v85; // [rsp+70h] [rbp-90h] BYREF
  SysDataCollectorSet *v86; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 *v87; // [rsp+80h] [rbp-80h]
  EVT_HANDLE ResultSet; // [rsp+88h] [rbp-78h] BYREF
  HANDLE hEvent; // [rsp+90h] [rbp-70h] BYREF
  BSTR bstrString; // [rsp+98h] [rbp-68h] BYREF
  struct ITaskDefinition *v91; // [rsp+A0h] [rbp-60h] BYREF
  BSTR v92; // [rsp+A8h] [rbp-58h] BYREF
  struct IRegisteredTask *v93; // [rsp+B0h] [rbp-50h] BYREF
  BSTR v94; // [rsp+B8h] [rbp-48h] BYREF
  struct IDataCollectorCollection *v95; // [rsp+C0h] [rbp-40h] BYREF
  LPCVOID v96; // [rsp+C8h] [rbp-38h]
  BSTR v97; // [rsp+D0h] [rbp-30h] BYREF
  BSTR v98; // [rsp+D8h] [rbp-28h]
  __int64 v99; // [rsp+E0h] [rbp-20h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+E8h] [rbp-18h] BYREF
  double v101; // [rsp+F0h] [rbp-10h] BYREF
  LPCVOID lpMem; // [rsp+F8h] [rbp-8h]
  VARIANTARG pvarg; // [rsp+100h] [rbp+0h] BYREF
  __int128 v104; // [rsp+118h] [rbp+18h] BYREF
  const wchar_t *v105; // [rsp+128h] [rbp+28h]
  VARIANTARG v106; // [rsp+130h] [rbp+30h] BYREF
  UUID Uuid; // [rsp+150h] [rbp+50h] BYREF
  unsigned __int16 v108[64]; // [rsp+160h] [rbp+60h] BYREF
  unsigned __int16 v109[64]; // [rsp+1E0h] [rbp+E0h] BYREF
  unsigned __int16 v110[64]; // [rsp+260h] [rbp+160h] BYREF
  unsigned __int16 v111[64]; // [rsp+2E0h] [rbp+1E0h] BYREF
  unsigned __int16 v112[64]; // [rsp+360h] [rbp+260h] BYREF
  unsigned __int16 v113[64]; // [rsp+3E0h] [rbp+2E0h] BYREF
  unsigned __int16 v114[64]; // [rsp+460h] [rbp+360h] BYREF
  unsigned __int16 v115[64]; // [rsp+4E0h] [rbp+3E0h] BYREF
  unsigned __int16 v116[64]; // [rsp+560h] [rbp+460h] BYREF
  unsigned __int16 v117[64]; // [rsp+5E0h] [rbp+4E0h] BYREF
  unsigned __int16 v118[64]; // [rsp+660h] [rbp+560h] BYREF
  unsigned __int16 v119[64]; // [rsp+6E0h] [rbp+5E0h] BYREF
  unsigned __int16 v120[64]; // [rsp+760h] [rbp+660h] BYREF
  unsigned __int16 v121[64]; // [rsp+7E0h] [rbp+6E0h] BYREF
  unsigned __int16 v122[64]; // [rsp+860h] [rbp+760h] BYREF
  unsigned __int16 v123[64]; // [rsp+8E0h] [rbp+7E0h] BYREF
  unsigned __int16 v124[64]; // [rsp+960h] [rbp+860h] BYREF
  unsigned __int16 v125[64]; // [rsp+9E0h] [rbp+8E0h] BYREF
  unsigned __int16 v126[64]; // [rsp+A60h] [rbp+960h] BYREF
  unsigned __int16 v127[64]; // [rsp+AE0h] [rbp+9E0h] BYREF
  unsigned __int16 v128[64]; // [rsp+B60h] [rbp+A60h] BYREF
  unsigned __int16 v129[64]; // [rsp+BE0h] [rbp+AE0h] BYREF
  unsigned __int16 v130[64]; // [rsp+C60h] [rbp+B60h] BYREF
  unsigned __int16 v131[64]; // [rsp+CE0h] [rbp+BE0h] BYREF
  unsigned __int16 v132[64]; // [rsp+D60h] [rbp+C60h] BYREF
  unsigned __int16 v133[64]; // [rsp+DE0h] [rbp+CE0h] BYREF
  unsigned __int16 v134[64]; // [rsp+E60h] [rbp+D60h] BYREF
  unsigned __int16 v135[64]; // [rsp+EE0h] [rbp+DE0h] BYREF
  unsigned __int16 v136[64]; // [rsp+F60h] [rbp+E60h] BYREF

  v105 = L"\\Microsoft\\Windows\\PLA\\System";
  v101 = 0.0;
  PerformanceCount.QuadPart = 0;
  lpMem = 0;
  v104 = 0;
  bstrString = 0;
  v4 = 0;
  Uuid = 0;
  v92 = 0;
  v5 = 0;
  v97 = 0;
  v6 = 0;
  v98 = 0;
  v91 = 0;
  v93 = 0;
  v99 = 0;
  v94 = 0;
  ResultSet = 0;
  hEvent = 0;
  v96 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  v95 = 0;
  PlaiVariantInit(&pvarg);
  v85 = *((_DWORD *)this + 14);
  v86 = this;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000400LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000400LL) )
  {
    EventingWriteEvent(&g_Eventing, &PLA_EVENT_METHOD, 3, "SysDataCollectorSet::Start", 27, &v86, 8, &v85, 4);
  }
  if ( *((_DWORD *)this + 2) )
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  v7 = PlaiCreateSystemName(*((unsigned __int16 **)this + 15), &v94);
  v8 = -1;
  v9 = v7;
  if ( v7 >= 0 )
  {
    Task = PlaTaskService::GetTask((PlaTaskService *)&v104, &v91);
    v9 = Task;
    if ( Task < 0 )
    {
      v85 = Task;
      LODWORD(v86) = 0;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_228;
      }
      PlaiWhoAmI(v109, 0x4000000000000800uLL);
      v14 = -1;
      do
        ++v14;
      while ( v109[v14] );
LABEL_22:
      v11 = (SysDataCollectorSet **)&v85;
      v12 = &v86;
LABEL_14:
      EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, v11, 4, byte_180147320, 1, v12, 4);
LABEL_15:
      v6 = 0;
LABEL_227:
      v4 = ResultSet;
      goto LABEL_228;
    }
    v15 = PlaiSetTaskSettings(v91, v94);
    v9 = v15;
    if ( v15 < 0 )
    {
      v85 = v15;
      LODWORD(v86) = 0;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_228;
      }
      PlaiWhoAmI(v110, 0x4000000000000800uLL);
      v16 = -1;
      do
        ++v16;
      while ( v110[v16] );
      goto LABEL_22;
    }
    if ( *((_DWORD *)this + 60) )
    {
      v21 = (*(__int64 (__fastcall **)(SysDataCollectorSet *, BSTR *))(*(_QWORD *)this + 408LL))(this, &bstrString);
      v9 = v21;
      if ( v21 < 0 )
      {
        v85 = v21;
        LODWORD(v86) = 0;
        if ( (_DWORD)xmmword_180169738
          && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
          && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
        {
          PlaiWhoAmI(v112, 0x4000000000000800uLL);
          v22 = -1;
          do
            ++v22;
          while ( v112[v22] );
          goto LABEL_37;
        }
LABEL_56:
        v6 = 0;
        goto LABEL_228;
      }
      if ( bstrString && *bstrString )
      {
        v23 = TASK_LOGON_PASSWORD;
        v24 = (*(__int64 (__fastcall **)(SysDataCollectorSet *, BSTR *))(*(_QWORD *)this + 576LL))(this, &v92);
        v9 = v24;
        if ( v24 < 0 )
        {
          v85 = v24;
          LODWORD(v86) = 0;
          if ( (_DWORD)xmmword_180169738
            && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
            && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
          {
            PlaiWhoAmI(v113, 0x4000000000000800uLL);
            v25 = -1;
            do
              ++v25;
            while ( v113[v25] );
            goto LABEL_53;
          }
          goto LABEL_55;
        }
        v19 = bstrString;
LABEL_66:
        v29 = PlaiSetTaskRunLevel(v91, v23, v19, v92);
        v9 = v29;
        if ( v29 < 0 )
        {
          v85 = v29;
          LODWORD(v86) = 0;
          if ( (_DWORD)xmmword_180169738
            && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
            && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
          {
            PlaiWhoAmI(v115, 0x4000000000000800uLL);
            v30 = -1;
            do
              ++v30;
            while ( v115[v30] );
            goto LABEL_53;
          }
LABEL_55:
          v5 = hEvent;
          goto LABEL_56;
        }
        v31 = PlaiCreateSddl(2u, &v97);
        v9 = v31;
        if ( v31 < 0 )
        {
          v85 = v31;
          LODWORD(v86) = 0;
          if ( (_DWORD)xmmword_180169738
            && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
            && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
          {
            PlaiWhoAmI(v116, 0x4000000000000800uLL);
            v32 = -1;
            do
              ++v32;
            while ( v116[v32] );
            goto LABEL_53;
          }
          goto LABEL_55;
        }
        v33 = UuidCreate(&Uuid);
        v9 = v33;
        if ( v33 < 0 )
        {
          v85 = v33;
          LODWORD(v86) = 0;
          if ( (_DWORD)xmmword_180169738
            && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
            && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
          {
            PlaiWhoAmI(v117, 0x4000000000000800uLL);
            v34 = -1;
            do
              ++v34;
            while ( v117[v34] );
            goto LABEL_53;
          }
          goto LABEL_55;
        }
        v35 = PlaiAlloc(0x50u, 1, 0, byte_180147320, v82);
        lpMem = v35;
        v36 = v35;
        if ( !v35 )
        {
          v9 = -2147024882;
          LODWORD(v86) = 0;
          v85 = -2147024882;
          if ( !(_DWORD)xmmword_180169738
            || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            goto LABEL_54;
          }
          PlaiWhoAmI(v118, 0x4000000000000800uLL);
          v37 = -1;
          do
            ++v37;
          while ( v118[v37] );
LABEL_53:
          EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v85, 4, byte_180147320, 1, &v86, 4);
LABEL_54:
          v5 = hEvent;
          goto LABEL_15;
        }
        if ( !StringFromGUID2(&Uuid, (LPOLESTR)v35, 40) )
        {
          v9 = -2147467259;
          LODWORD(v86) = 0;
          v85 = -2147467259;
          if ( !(_DWORD)xmmword_180169738
            || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            goto LABEL_54;
          }
          PlaiWhoAmI(v119, 0x4000000000000800uLL);
          v38 = -1;
          do
            ++v38;
          while ( v119[v38] );
          goto LABEL_53;
        }
        v87 = (unsigned __int16 *)PlaiAlloc(0x800u, 1, 0, byte_180147320, v83);
        if ( !v87 )
        {
          v9 = -2147024882;
          LODWORD(v86) = 0;
          v85 = -2147024882;
          if ( !(_DWORD)xmmword_180169738
            || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            v5 = hEvent;
            v6 = 0;
            goto LABEL_227;
          }
          PlaiWhoAmI(v120, 0x4000000000000800uLL);
          v39 = -1;
          do
            ++v39;
          while ( v120[v39] );
          goto LABEL_107;
        }
        v40 = StringCchPrintfW(v87, 0x400u, L"%s_%s", v36, *((_QWORD *)this + 15));
        v9 = v40;
        if ( v40 < 0 )
        {
          v85 = v40;
          LODWORD(v86) = 0;
          if ( !(_DWORD)xmmword_180169738
            || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            goto LABEL_108;
          }
          PlaiWhoAmI(v121, 0x4000000000000800uLL);
          v43 = -1;
          do
            ++v43;
          while ( v121[v43] );
LABEL_107:
          EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v85, 4, byte_180147320, 1, &v86, 4);
LABEL_108:
          v5 = hEvent;
LABEL_226:
          v6 = v87;
          goto LABEL_227;
        }
        v44 = PlaiAllocStringEx(v87, v41, v42);
        v98 = v44;
        if ( !v44 )
        {
          v9 = -2147024882;
          LODWORD(v86) = 0;
          v85 = -2147024882;
          if ( !(_DWORD)xmmword_180169738
            || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            goto LABEL_108;
          }
          PlaiWhoAmI(v122, 0x4000000000000800uLL);
          v45 = -1;
          do
            ++v45;
          while ( v122[v45] );
          goto LABEL_107;
        }
        v46 = PlaiCreateTaskDeleteAction(v91, v44);
        v9 = v46;
        if ( v46 < 0 )
        {
          v85 = v46;
          LODWORD(v86) = 0;
          if ( !(_DWORD)xmmword_180169738
            || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            goto LABEL_108;
          }
          PlaiWhoAmI(v123, 0x4000000000000800uLL);
          v47 = -1;
          do
            ++v47;
          while ( v123[v47] );
          goto LABEL_107;
        }
        v48 = PlaTaskService::Save((PlaTaskService *)&v104, v91, v98, v97, bstrString, v92, v23, &v93);
        v9 = v48;
        if ( v48 < 0 )
        {
          v85 = v48;
          LODWORD(v86) = 0;
          if ( !(_DWORD)xmmword_180169738
            || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            goto LABEL_108;
          }
          PlaiWhoAmI(v124, 0x4000000000000800uLL);
          v49 = -1;
          do
            ++v49;
          while ( v124[v49] );
          goto LABEL_107;
        }
        if ( !QueryPerformanceCounter(&PerformanceCount) )
        {
          LastError = GetLastError();
          v51 = PlaiHResultFromWin32(LastError);
          v9 = v51;
          if ( v51 < 0 )
          {
            v85 = v51;
            LODWORD(v86) = 0;
            if ( !(_DWORD)xmmword_180169738
              || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
              || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
            {
              goto LABEL_108;
            }
            PlaiWhoAmI(v125, 0x4000000000000800uLL);
            v52 = -1;
            do
              ++v52;
            while ( v125[v52] );
            goto LABEL_107;
          }
        }
        CurrentThreadId = GetCurrentThreadId();
        CurrentProcessId = GetCurrentProcessId();
        v55 = v87;
        v84 = CurrentThreadId;
        v56 = StringCchPrintfW(v87, 0x400u, L"0x%x_0x%x_0x%I64x", CurrentProcessId);
        v9 = v56;
        if ( v56 < 0 )
        {
          v85 = v56;
          LODWORD(v86) = 0;
          if ( !(_DWORD)xmmword_180169738
            || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            goto LABEL_108;
          }
          PlaiWhoAmI(v126, 0x4000000000000800uLL);
          v57 = -1;
          do
            ++v57;
          while ( v126[v57] );
          goto LABEL_107;
        }
        v58 = PlaiAlloc(0x800u, 1, 0, byte_180147320, v84);
        v96 = v58;
        if ( !v58 )
        {
          v9 = -2147024882;
          LODWORD(v86) = 0;
          v85 = -2147024882;
          if ( !(_DWORD)xmmword_180169738
            || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            goto LABEL_108;
          }
          PlaiWhoAmI(v127, 0x4000000000000800uLL);
          v59 = -1;
          do
            ++v59;
          while ( v127[v59] );
          goto LABEL_107;
        }
        v60 = StringCchPrintfW((unsigned __int16 *)v58, 0x400u, L"%s", v55);
        v9 = v60;
        if ( v60 < 0 )
        {
          v85 = v60;
          LODWORD(v86) = 0;
          if ( !(_DWORD)xmmword_180169738
            || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            goto LABEL_108;
          }
          PlaiWhoAmI(v128, 0x4000000000000800uLL);
          v63 = -1;
          do
            ++v63;
          while ( v128[v63] );
          goto LABEL_107;
        }
        v64 = PlaiSetVariantEx((const unsigned __int16 *)v96, &pvarg, v61, v62);
        v9 = v64;
        if ( v64 < 0 )
        {
          v85 = v64;
          LODWORD(v86) = 0;
          if ( !(_DWORD)xmmword_180169738
            || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            goto LABEL_108;
          }
          PlaiWhoAmI(v129, 0x4000000000000800uLL);
          v65 = -1;
          do
            ++v65;
          while ( v129[v65] );
          goto LABEL_107;
        }
        v9 = ((__int64 (__fastcall *)(struct IRegisteredTask *, double *))v93->lpVtbl->get_LastRunTime)(v93, &v101);
        if ( v9 < 0 )
        {
          v85 = v9;
          LODWORD(v86) = 0;
          if ( !(_DWORD)xmmword_180169738
            || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            goto LABEL_108;
          }
          PlaiWhoAmI(v130, 0x4000000000000800uLL);
          v66 = -1;
          do
            ++v66;
          while ( v130[v66] );
          goto LABEL_107;
        }
        if ( a2 )
        {
          started = PlaiRegisterForStartNotification(v94, v55, &hEvent, &ResultSet);
          v9 = started;
          if ( started < 0 )
          {
            v85 = started;
            LODWORD(v86) = 0;
            if ( !(_DWORD)xmmword_180169738
              || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
              || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
            {
              goto LABEL_108;
            }
            PlaiWhoAmI(v131, 0x4000000000000800uLL);
            v68 = -1;
            do
              ++v68;
            while ( v131[v68] );
            goto LABEL_107;
          }
        }
        lpVtbl = v93->lpVtbl;
        v106 = pvarg;
        v9 = ((__int64 (__fastcall *)(struct IRegisteredTask *, VARIANTARG *, __int64 *))lpVtbl->Run)(v93, &v106, &v99);
        if ( v9 < 0 )
        {
          v85 = v9;
          LODWORD(v86) = 0;
          if ( !(_DWORD)xmmword_180169738
            || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            goto LABEL_108;
          }
          PlaiWhoAmI(v132, 0x4000000000000800uLL);
          v70 = -1;
          do
            ++v70;
          while ( v132[v70] );
          goto LABEL_107;
        }
        if ( a2 )
        {
          v71 = PlaiWaitForTaskStart(v93, &v101);
          v9 = v71;
          if ( v71 < 0 )
          {
            LODWORD(v86) = 0;
            v85 = v71;
            if ( !(_DWORD)xmmword_180169738
              || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
              || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
            {
              goto LABEL_108;
            }
            PlaiWhoAmI(v133, 0x4000000000000800uLL);
            v72 = -1;
            do
              ++v72;
            while ( v133[v72] );
            goto LABEL_107;
          }
          v5 = hEvent;
          v73 = PlaiWaitForStartNotification(hEvent, ResultSet);
          v9 = v73;
          if ( v73 < 0 )
          {
            LODWORD(v86) = 0;
            v85 = v73;
            if ( !(_DWORD)xmmword_180169738
              || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
              || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
            {
              goto LABEL_226;
            }
            PlaiWhoAmI(v134, 0x4000000000000800uLL);
            v74 = -1;
            do
              ++v74;
            while ( v134[v74] );
            goto LABEL_225;
          }
        }
        else
        {
          v5 = hEvent;
        }
        v75 = (*(__int64 (__fastcall **)(SysDataCollectorSet *, struct IDataCollectorCollection **))(*(_QWORD *)this + 56LL))(
                this,
                &v95);
        v9 = v75;
        if ( v75 >= 0 )
        {
          TraceDataCollectors = PlaiQueryTraceDataCollectors(v95);
          v9 = TraceDataCollectors;
          if ( TraceDataCollectors >= 0 )
            goto LABEL_226;
          LODWORD(v86) = 0;
          v85 = TraceDataCollectors;
          if ( !(_DWORD)xmmword_180169738
            || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            goto LABEL_226;
          }
          PlaiWhoAmI(v136, 0x4000000000000800uLL);
          v78 = -1;
          do
            ++v78;
          while ( v136[v78] );
        }
        else
        {
          LODWORD(v86) = 0;
          v85 = v75;
          if ( !(_DWORD)xmmword_180169738
            || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            goto LABEL_226;
          }
          PlaiWhoAmI(v135, 0x4000000000000800uLL);
          v76 = -1;
          do
            ++v76;
          while ( v135[v76] );
        }
LABEL_225:
        EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v85, 4, byte_180147320, 1, &v86, 4);
        goto LABEL_226;
      }
      PlaiFreeString(bstrString);
      bstrString = 0;
      v19 = PlaiAllocStringEx(L"System", v26, v27);
      bstrString = v19;
      if ( !v19 )
      {
        v9 = -2147024882;
        LODWORD(v86) = 0;
        v85 = -2147024882;
        if ( (_DWORD)xmmword_180169738
          && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
          && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
        {
          PlaiWhoAmI(v114, 0x4000000000000800uLL);
          v28 = -1;
          do
            ++v28;
          while ( v114[v28] );
          goto LABEL_37;
        }
        goto LABEL_56;
      }
    }
    else
    {
      PlaiFreeString(bstrString);
      bstrString = 0;
      v19 = PlaiAllocStringEx(L"System", v17, v18);
      bstrString = v19;
      if ( !v19 )
      {
        v9 = -2147024882;
        LODWORD(v86) = 0;
        v85 = -2147024882;
        if ( (_DWORD)xmmword_180169738
          && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
          && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
        {
          PlaiWhoAmI(v111, 0x4000000000000800uLL);
          v20 = -1;
          do
            ++v20;
          while ( v111[v20] );
LABEL_37:
          v11 = (SysDataCollectorSet **)&v85;
          v12 = &v86;
          goto LABEL_14;
        }
        goto LABEL_56;
      }
    }
    v23 = TASK_LOGON_SERVICE_ACCOUNT;
    goto LABEL_66;
  }
  LODWORD(v86) = v7;
  v85 = 0;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
  {
    PlaiWhoAmI(v108, 0x4000000000000800uLL);
    v10 = -1;
    do
      ++v10;
    while ( v108[v10] );
    v11 = &v86;
    v12 = (SysDataCollectorSet **)&v85;
    goto LABEL_14;
  }
LABEL_228:
  if ( *((_DWORD *)this + 2) )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  v79 = v92;
  if ( v92 )
  {
    do
      ++v8;
    while ( v92[v8] );
    for ( i = 2 * v8; i; --i )
    {
      *(_BYTE *)v79 = 0;
      v79 = (BSTR)((char *)v79 + 1);
    }
  }
  PlaiVariantClear(&pvarg);
  if ( lpMem )
    PlaiFree(lpMem, 1);
  if ( v6 )
    PlaiFree(v6, 1);
  if ( v96 )
    PlaiFree(v96, 1);
  PlaiFreeString(v94);
  PlaiFreeString(bstrString);
  bstrString = 0;
  PlaiFreeString(v92);
  v92 = 0;
  PlaiFreeString(v97);
  PlaiFreeString(v98);
  if ( v4 )
    EvtClose(v4);
  if ( v5 )
    CloseHandle(v5);
  if ( v91 )
  {
    ((void (__fastcall *)(struct ITaskDefinition *))v91->lpVtbl->Release)(v91);
    v91 = 0;
  }
  if ( v93 )
  {
    ((void (__fastcall *)(struct IRegisteredTask *))v93->lpVtbl->Release)(v93);
    v93 = 0;
  }
  if ( v99 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v99 + 16LL))(v99);
    v99 = 0;
  }
  if ( v95 )
  {
    ((void (__fastcall *)(struct IDataCollectorCollection *))v95->lpVtbl->Release)(v95);
    v95 = 0;
  }
  PlaTaskService::~PlaTaskService((PlaTaskService *)&v104);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18012ab80  push    rbp
0x18012ab82  push    rbx
0x18012ab83  push    rsi
0x18012ab84  push    rdi
0x18012ab85  push    r12
0x18012ab87  push    r13
0x18012ab89  push    r14
0x18012ab8b  push    r15
0x18012ab8d  lea     rbp, [rsp-0EF8h]
0x18012ab95  sub     rsp, 0FF8h
0x18012ab9c  mov     rax, cs:__security_cookie
0x18012aba3  xor     rax, rsp
0x18012aba6  mov     [rbp+0F30h+var_50], rax
0x18012abad  xor     ebx, ebx
0x18012abaf  lea     rax, aMicrosoftWindo_0; "\\Microsoft\\Windows\\PLA\\System"
0x18012abb6  xorps   xmm0, xmm0
0x18012abb9  mov     [rbp+0F30h+var_F08], rax
0x18012abbd  xor     eax, eax
0x18012abbf  movsd   [rbp+0F30h+var_F40], xmm0
0x18012abc4  mov     r13, rcx
0x18012abc7  mov     qword ptr [rbp+0F30h+pvarg+10h], rax
0x18012abcb  lea     rcx, [rbp+0F30h+pvarg]; struct tagVARIANT *
0x18012abcf  mov     qword ptr [rbp+0F30h+PerformanceCount], rbx
0x18012abd3  movzx   esi, dx
0x18012abd6  mov     [rbp+0F30h+lpMem], rbx
0x18012abda  movdqu  [rbp+0F30h+var_F18], xmm0
0x18012abdf  mov     [rbp+0F30h+bstrString], rbx
0x18012abe3  mov     r15d, ebx
0x18012abe6  movups  xmmword ptr [rbp+0F30h+Uuid.Data1], xmm0
0x18012abea  mov     [rbp+0F30h+var_F88], rbx
0x18012abee  mov     edi, ebx
0x18012abf0  mov     [rbp+0F30h+var_F60], rbx
0x18012abf4  mov     r12d, ebx
0x18012abf7  mov     [rbp+0F30h+var_F58], rbx
0x18012abfb  mov     [rbp+0F30h+var_F90], rbx
0x18012abff  mov     [rbp+0F30h+var_F80], rbx
0x18012ac03  mov     [rbp+0F30h+var_F50], rbx
0x18012ac07  mov     [rbp+0F30h+var_F78], rbx
0x18012ac0b  mov     [rbp+0F30h+ResultSet], rbx
0x18012ac0f  mov     [rbp+0F30h+hEvent], rbx
0x18012ac13  mov     [rbp+0F30h+var_F68], rbx
0x18012ac17  movups  xmmword ptr [rbp+0F30h+pvarg], xmm0
0x18012ac1b  mov     [rbp+0F30h+var_F70], rbx
0x18012ac1f  call    ?PlaiVariantInit@@YAJPEAUtagVARIANT@@@Z; PlaiVariantInit(tagVARIANT *)
0x18012ac24  cmp     dword ptr cs:xmmword_180169738, ebx
0x18012ac2a  mov     eax, [r13+38h]
0x18012ac2e  mov     [rsp+1030h+var_FC0], eax
0x18012ac32  mov     [rsp+1030h+var_FB8], r13
0x18012ac37  jz      short loc_18012ACAC
0x18012ac39  mov     rdx, 4000000000000400h
0x18012ac43  test    qword ptr cs:xmmword_180169738+8, rdx
0x18012ac4a  jz      short loc_18012ACAC
0x18012ac4c  mov     rax, cs:qword_180169748
0x18012ac53  and     rax, rdx
0x18012ac56  cmp     cs:qword_180169748, rax
0x18012ac5d  jnz     short loc_18012ACAC
0x18012ac5f  mov     [rsp+1030h+var_FF0], 4
0x18012ac68  lea     rax, [rsp+1030h+var_FC0]
0x18012ac6d  mov     [rsp+1030h+var_FF8], rax
0x18012ac72  lea     r9, aSysdatacollect_1; "SysDataCollectorSet::Start"
0x18012ac79  lea     rax, [rsp+1030h+var_FB8]
0x18012ac7e  mov     qword ptr [rsp+1030h+var_1000], 8
0x18012ac87  mov     [rsp+1030h+var_1008], rax
0x18012ac8c  lea     r8d, [rbx+3]
0x18012ac90  lea     rdx, PLA_EVENT_METHOD
0x18012ac97  mov     [rsp+1030h+var_1010], 1Bh; int
0x18012aca0  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x18012aca7  call    EventingWriteEvent
0x18012acac  cmp     [r13+8], ebx
0x18012acb0  jz      short loc_18012ACBC
0x18012acb2  lea     rcx, [r13+10h]; lpCriticalSection
0x18012acb6  call    cs:__imp_EnterCriticalSection
0x18012acbc  mov     rcx, [r13+78h]; unsigned __int16 *
0x18012acc0  lea     rdx, [rbp+0F30h+var_F78]; unsigned __int16 **
0x18012acc4  call    ?PlaiCreateSystemName@@YAJPEAGPEAPEAG@Z; PlaiCreateSystemName(ushort *,ushort * *)
0x18012acc9  or      r14, 0FFFFFFFFFFFFFFFFh
0x18012accd  mov     ebx, eax
0x18012accf  test    eax, eax
0x18012acd1  jns     loc_18012ADB2
0x18012acd7  xor     esi, esi
0x18012acd9  mov     dword ptr [rsp+1030h+var_FB8], eax
0x18012acdd  cmp     dword ptr cs:xmmword_180169738, esi
0x18012ace3  mov     [rsp+1030h+var_FC0], esi
0x18012ace7  jz      loc_18012BFF9
0x18012aced  mov     rdx, 4000000000000800h; unsigned __int64
0x18012acf7  test    qword ptr cs:xmmword_180169738+8, rdx
0x18012acfe  jz      loc_18012BFF9
0x18012ad04  mov     rax, cs:qword_180169748
0x18012ad0b  and     rax, rdx
0x18012ad0e  cmp     cs:qword_180169748, rax
0x18012ad15  jnz     loc_18012BFF9
0x18012ad1b  lea     rcx, [rbp+0F30h+var_ED0]; unsigned __int16 *
0x18012ad1f  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18012ad24  lea     rcx, [rbp+0F30h+var_ED0]
0x18012ad28  mov     rax, r14
0x18012ad2b  inc     rax
0x18012ad2e  cmp     [rcx+rax*2], si
0x18012ad32  jnz     short loc_18012AD2B
0x18012ad34  lea     ecx, [rax+rax]
0x18012ad37  lea     rax, [rbp+0F30h+var_ED0]
0x18012ad3b  add     rcx, 2
0x18012ad3f  mov     [rsp+1030h+var_FD0], rcx
0x18012ad44  lea     r9, [rsp+1030h+var_FB8]
0x18012ad49  mov     [rsp+1030h+var_FD8], rax
0x18012ad4e  lea     rax, aSysdatacollect_1; "SysDataCollectorSet::Start"
0x18012ad55  mov     [rsp+1030h+var_FE0], 1Bh
0x18012ad5e  mov     [rsp+1030h+var_FE8], rax
0x18012ad63  lea     rax, [rsp+1030h+var_FC0]
0x18012ad68  mov     r8d, 5
0x18012ad6e  mov     ecx, 4
0x18012ad73  lea     r15, byte_180147320
0x18012ad7a  mov     [rsp+1030h+var_FF0], rcx
0x18012ad7f  lea     rdx, PLA_EVENT_ERROR
0x18012ad86  mov     [rsp+1030h+var_FF8], rax
0x18012ad8b  mov     qword ptr [rsp+1030h+var_1000], 1
0x18012ad94  mov     [rsp+1030h+var_1008], r15
0x18012ad99  mov     [rsp+1030h+var_1010], rcx
0x18012ad9e  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x18012ada5  call    EventingWriteEvent
0x18012adaa  mov     r12, rsi
0x18012adad  jmp     loc_18012BFF5
0x18012adb2  lea     rdx, [rbp+0F30h+var_F90]; struct ITaskDefinition **
0x18012adb6  lea     rcx, [rbp+0F30h+var_F18]; this
0x18012adba  call    ?GetTask@PlaTaskService@@QEAAJPEAPEAUITaskDefinition@@@Z; PlaTaskService::GetTask(ITaskDefinition * *)
0x18012adbf  mov     ebx, eax
0x18012adc1  test    eax, eax
0x18012adc3  jns     loc_18012AE68
0x18012adc9  xor     esi, esi
0x18012adcb  mov     [rsp+1030h+var_FC0], eax
0x18012adcf  cmp     dword ptr cs:xmmword_180169738, esi
0x18012add5  mov     dword ptr [rsp+1030h+var_FB8], esi
0x18012add9  jz      loc_18012BFF9
0x18012addf  mov     rdx, 4000000000000800h; unsigned __int64
0x18012ade9  test    qword ptr cs:xmmword_180169738+8, rdx
0x18012adf0  jz      loc_18012BFF9
0x18012adf6  mov     rax, cs:qword_180169748
0x18012adfd  and     rax, rdx
0x18012ae00  cmp     cs:qword_180169748, rax
0x18012ae07  jnz     loc_18012BFF9
0x18012ae0d  lea     rcx, [rbp+0F30h+var_E50]; unsigned __int16 *
0x18012ae14  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18012ae19  lea     rcx, [rbp+0F30h+var_E50]
0x18012ae20  mov     rax, r14
0x18012ae23  inc     rax
0x18012ae26  cmp     [rcx+rax*2], si
0x18012ae2a  jnz     short loc_18012AE23
0x18012ae2c  lea     ecx, [rax+rax]
0x18012ae2f  lea     rax, [rbp+0F30h+var_E50]
0x18012ae36  add     rcx, 2
0x18012ae3a  lea     r9, [rsp+1030h+var_FC0]
0x18012ae3f  mov     [rsp+1030h+var_FD0], rcx
0x18012ae44  mov     [rsp+1030h+var_FD8], rax
0x18012ae49  lea     rax, aSysdatacollect_1; "SysDataCollectorSet::Start"
0x18012ae50  mov     [rsp+1030h+var_FE0], 1Bh
0x18012ae59  mov     [rsp+1030h+var_FE8], rax
0x18012ae5e  lea     rax, [rsp+1030h+var_FB8]
0x18012ae63  jmp     loc_18012AD68
0x18012ae68  mov     rdx, [rbp+0F30h+var_F78]; unsigned __int16 *
0x18012ae6c  mov     rcx, [rbp+0F30h+var_F90]; struct ITaskDefinition *
0x18012ae70  call    ?PlaiSetTaskSettings@@YAJPEAUITaskDefinition@@PEAG@Z; PlaiSetTaskSettings(ITaskDefinition *,ushort *)
0x18012ae75  mov     ebx, eax
0x18012ae77  test    eax, eax
0x18012ae79  jns     short loc_18012AEED
0x18012ae7b  xor     esi, esi
0x18012ae7d  mov     [rsp+1030h+var_FC0], eax
0x18012ae81  cmp     dword ptr cs:xmmword_180169738, esi
0x18012ae87  mov     dword ptr [rsp+1030h+var_FB8], esi
0x18012ae8b  jz      loc_18012BFF9
0x18012ae91  mov     rdx, 4000000000000800h; unsigned __int64
0x18012ae9b  test    qword ptr cs:xmmword_180169738+8, rdx
0x18012aea2  jz      loc_18012BFF9
0x18012aea8  mov     rax, cs:qword_180169748
0x18012aeaf  and     rax, rdx
0x18012aeb2  cmp     cs:qword_180169748, rax
0x18012aeb9  jnz     loc_18012BFF9
0x18012aebf  lea     rcx, [rbp+0F30h+var_DD0]; unsigned __int16 *
0x18012aec6  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18012aecb  lea     rcx, [rbp+0F30h+var_DD0]
0x18012aed2  mov     rax, r14
0x18012aed5  inc     rax
0x18012aed8  cmp     [rcx+rax*2], si
0x18012aedc  jnz     short loc_18012AED5
0x18012aede  lea     ecx, [rax+rax]
0x18012aee1  lea     rax, [rbp+0F30h+var_DD0]
0x18012aee8  jmp     loc_18012AE36
0x18012aeed  xor     ebx, ebx
0x18012aeef  lea     r12d, [rbx+5]
0x18012aef3  cmp     [r13+0F0h], ebx
0x18012aefa  jnz     loc_18012AFCF
0x18012af00  mov     rcx, [rbp+0F30h+bstrString]; bstrString
0x18012af04  call    ?PlaiFreeString@@YAJPEAG@Z; PlaiFreeString(ushort *)
0x18012af09  lea     rcx, aSystem_0; "System"
0x18012af10  mov     [rbp+0F30h+bstrString], rbx
0x18012af14  call    ?PlaiAllocStringEx@@YAPEAGPEBGPEBDH@Z; PlaiAllocStringEx(ushort const *,char const *,int)
0x18012af19  mov     [rbp+0F30h+bstrString], rax
0x18012af1d  test    rax, rax
0x18012af20  jnz     loc_18012B218
0x18012af26  xor     esi, esi
0x18012af28  mov     eax, 8007000Eh
0x18012af2d  cmp     dword ptr cs:xmmword_180169738, esi
0x18012af33  mov     ebx, eax
0x18012af35  mov     dword ptr [rsp+1030h+var_FB8], esi
0x18012af39  mov     [rsp+1030h+var_FC0], eax
0x18012af3d  jz      loc_18012B17C
0x18012af43  mov     rdx, 4000000000000800h; unsigned __int64
0x18012af4d  test    qword ptr cs:xmmword_180169738+8, rdx
0x18012af54  jz      loc_18012B17C
0x18012af5a  mov     rax, cs:qword_180169748
0x18012af61  and     rax, rdx
0x18012af64  cmp     cs:qword_180169748, rax
0x18012af6b  jnz     loc_18012B17C
0x18012af71  lea     rcx, [rbp+0F30h+var_D50]; unsigned __int16 *
0x18012af78  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18012af7d  lea     rcx, [rbp+0F30h+var_D50]
0x18012af84  mov     rax, r14
0x18012af87  inc     rax
0x18012af8a  cmp     [rcx+rax*2], si
0x18012af8e  jnz     short loc_18012AF87
0x18012af90  lea     ecx, [rax+rax]
0x18012af93  lea     rax, [rbp+0F30h+var_D50]
0x18012af9a  add     rcx, 2
0x18012af9e  lea     r9, [rsp+1030h+var_FC0]
0x18012afa3  mov     [rsp+1030h+var_FD0], rcx
0x18012afa8  mov     r8d, r12d
0x18012afab  mov     [rsp+1030h+var_FD8], rax
0x18012afb0  lea     rax, aSysdatacollect_1; "SysDataCollectorSet::Start"
0x18012afb7  mov     [rsp+1030h+var_FE0], 1Bh
0x18012afc0  mov     [rsp+1030h+var_FE8], rax
0x18012afc5  lea     rax, [rsp+1030h+var_FB8]
0x18012afca  jmp     loc_18012AD6E
0x18012afcf  mov     rax, [r13+0]
0x18012afd3  lea     rdx, [rbp+0F30h+bstrString]
0x18012afd7  mov     rcx, r13
0x18012afda  mov     rax, [rax+198h]
0x18012afe1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012afe6  mov     ebx, eax
0x18012afe8  test    eax, eax
0x18012afea  jns     short loc_18012B05E
0x18012afec  xor     esi, esi
0x18012afee  mov     [rsp+1030h+var_FC0], eax
0x18012aff2  cmp     dword ptr cs:xmmword_180169738, esi
0x18012aff8  mov     dword ptr [rsp+1030h+var_FB8], esi
0x18012affc  jz      loc_18012B17C
0x18012b002  mov     rdx, 4000000000000800h; unsigned __int64
0x18012b00c  test    qword ptr cs:xmmword_180169738+8, rdx
0x18012b013  jz      loc_18012B17C
0x18012b019  mov     rax, cs:qword_180169748
0x18012b020  and     rax, rdx
0x18012b023  cmp     cs:qword_180169748, rax
0x18012b02a  jnz     loc_18012B17C
0x18012b030  lea     rcx, [rbp+0F30h+var_CD0]; unsigned __int16 *
0x18012b037  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18012b03c  lea     rcx, [rbp+0F30h+var_CD0]
0x18012b043  mov     rax, r14
0x18012b046  inc     rax
0x18012b049  cmp     [rcx+rax*2], si
0x18012b04d  jnz     short loc_18012B046
0x18012b04f  lea     ecx, [rax+rax]
0x18012b052  lea     rax, [rbp+0F30h+var_CD0]
0x18012b059  jmp     loc_18012AF9A
0x18012b05e  mov     rcx, [rbp+0F30h+bstrString]; bstrString
0x18012b062  xor     ebx, ebx
0x18012b064  test    rcx, rcx
0x18012b067  jz      loc_18012B18D
0x18012b06d  cmp     bx, [rcx]
0x18012b070  jz      loc_18012B18D
0x18012b076  mov     rax, [r13+0]
0x18012b07a  lea     rdx, [rbp+0F30h+var_F88]
0x18012b07e  mov     rcx, r13
0x18012b081  lea     edi, [rbx+1]
0x18012b084  mov     rax, [rax+240h]
0x18012b08b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012b090  mov     ebx, eax
0x18012b092  test    eax, eax
0x18012b094  jns     loc_18012B184
0x18012b09a  xor     esi, esi
0x18012b09c  mov     [rsp+1030h+var_FC0], eax
0x18012b0a0  cmp     dword ptr cs:xmmword_180169738, esi
0x18012b0a6  mov     dword ptr [rsp+1030h+var_FB8], esi
0x18012b0aa  jz      loc_18012B178
0x18012b0b0  mov     rdx, 4000000000000800h; unsigned __int64
0x18012b0ba  test    qword ptr cs:xmmword_180169738+8, rdx
0x18012b0c1  jz      loc_18012B178
0x18012b0c7  mov     rax, cs:qword_180169748
0x18012b0ce  and     rax, rdx
0x18012b0d1  cmp     cs:qword_180169748, rax
0x18012b0d8  jnz     loc_18012B178
0x18012b0de  lea     rcx, [rbp+0F30h+var_C50]; unsigned __int16 *
0x18012b0e5  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18012b0ea  lea     rcx, [rbp+0F30h+var_C50]
0x18012b0f1  mov     rax, r14
0x18012b0f4  inc     rax
0x18012b0f7  cmp     [rcx+rax*2], si
0x18012b0fb  jnz     short loc_18012B0F4
0x18012b0fd  lea     ecx, [rax+rax]
0x18012b100  add     rcx, 2
0x18012b104  lea     rax, [rbp+0F30h+var_C50]
0x18012b10b  mov     [rsp+1030h+var_FD0], rcx
0x18012b110  mov     ecx, 4
0x18012b115  mov     [rsp+1030h+var_FD8], rax
  ... truncated ...
```
