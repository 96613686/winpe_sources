# GPOScripts::ExecuteScriptsSynchronously(ulong,void *)

- ea: `0x18009479c`
- end: `0x180094af6`
- name: `?ExecuteScriptsSynchronously@GPOScripts@@AEAAKKPEAX@Z`
- size: `858`
- prototype: `unsigned int __fastcall(GPOScripts *__hidden this, DWORD dwMilliseconds, void *)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x180022d38`

## callees

- `0x18000a52c`
- `0x180039148`
- `0x180055098`
- `0x180066684`
- `0x180075ec0`
- `0x18007de08`
- `0x18009479c`
- `0x1800950d0`
- `0x1800952e8`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180094a52`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180094a52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800947ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800949ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800947ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800949ca`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1800949d9`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1800949d9`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1800949e9`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x1800949e9`
- `api-ms-win-core-job-l2-1-0!AssignProcessToJobObject` at `0x1800949c0`
- `api-ms-win-core-job-l2-1-0!AssignProcessToJobObject` at `0x1800949c0`
- `api-ms-win-core-job-l2-1-0!TerminateJobObject` at `0x180094a68`
- `api-ms-win-core-job-l2-1-0!TerminateJobObject` at `0x180094a68`
- `api-ms-win-core-job-l2-1-0!CreateJobObjectW` at `0x1800947ed`
- `api-ms-win-core-job-l2-1-0!CreateJobObjectW` at `0x1800947ed`
- `api-ms-win-core-job-l2-1-0!SetInformationJobObject` at `0x180094827`
- `api-ms-win-core-job-l2-1-0!SetInformationJobObject` at `0x180094827`

## string_xrefs

- `0x180094a83`: `GPOScripts::ExecuteScriptsSynchronously: Completed WaitForSingleObject.`
- `0x180094aa6`: `GPOScripts::ExecuteScriptsSynchronously: Completed WaitForSingleObject.`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall GPOScripts::ExecuteScriptsSynchronously(GPOScripts *this, DWORD dwMilliseconds, HKEY a3)
{
  HANDLE JobObjectW; // rax
  void *v7; // rbx
  UINT LastError; // edi
  WCHAR *v9; // rax
  DWORD v10; // eax
  UINT v11; // edx
  unsigned int v13; // [rsp+28h] [rbp-A1h]
  struct _PROCESS_INFORMATION hProcess; // [rsp+40h] [rbp-89h] BYREF
  void *v15; // [rsp+58h] [rbp-71h] BYREF
  void *v16; // [rsp+60h] [rbp-69h] BYREF
  HANDLE v17; // [rsp+68h] [rbp-61h] BYREF
  struct _STARTUPINFOW v18; // [rsp+70h] [rbp-59h] BYREF
  int JobObjectInformation; // [rsp+148h] [rbp+7Fh] BYREF

  memset(&hProcess, 0, sizeof(hProcess));
  memset_0(&v18, 0, sizeof(v18));
  v16 = 0;
  v15 = 0;
  JobObjectW = CreateJobObjectW(0, 0);
  v7 = JobObjectW;
  v17 = JobObjectW;
  if ( JobObjectW
    && (JobObjectInformation = 1,
        SetInformationJobObject(JobObjectW, JobObjectEndOfJobTimeInformation, &JobObjectInformation, 4u)) )
  {
    memset(&hProcess, 0, sizeof(hProcess));
    memset_0(&v18, 0, sizeof(v18));
    v18.cb = 104;
    v18.wShowWindow = 2;
    v9 = L"Winsta0\\Winlogon";
    if ( !*((_DWORD *)this + 4) )
      v9 = L"Winsta0\\Default";
    v18.lpDesktop = v9;
    v18.dwFlags = 0;
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(
          4u,
          L"Synchronously processing script <%ws>",
          *(&GPOScripts::ScriptParametersArray + 3 * *(int *)this + 1));
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(
          4u,
          L"Synchronously processing script <%ws>",
          *(&GPOScripts::ScriptParametersArray + 3 * *(int *)this + 1));
      }
    }
    LastError = GPOScripts::LaunchProcessInSession(
                  this,
                  (const unsigned __int16 *)*(&GPOScripts::ScriptParametersArray + 3 * *(int *)this + 1),
                  *((_DWORD *)this + 5),
                  &v18,
                  &hProcess,
                  v13,
                  a3);
    if ( LastError )
    {
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(
            2u,
            L"Failed to start system process <%ws>, with 0x%x",
            *(&GPOScripts::ScriptParametersArray + 3 * *(int *)this + 1),
            LastError);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(
            2u,
            L"Failed to start system process <%ws>, with 0x%x",
            *(&GPOScripts::ScriptParametersArray + 3 * *(int *)this + 1),
            LastError);
        }
      }
    }
    else
    {
      XHandle::operator=(&v16, hProcess.hThread);
      XHandle::operator=(&v15, hProcess.hProcess);
      if ( AssignProcessToJobObject(v7, hProcess.hProcess) )
      {
        ResumeThread(hProcess.hThread);
        if ( *(_DWORD *)this == 3 )
        {
          v10 = CGPService::KeepServiceAlive(hProcess.hProcess, dwMilliseconds);
        }
        else
        {
          if ( *(_DWORD *)&g_dwDebugLevel )
          {
            if ( g_lpDebugMsg )
            {
              g_lpDebugMsg(4u, L"GPOScripts::ExecuteScriptsSynchronously: Beginning WaitForSingleObject.");
            }
            else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            {
              RedirectDebugMsg(4u, L"GPOScripts::ExecuteScriptsSynchronously: Beginning WaitForSingleObject.");
            }
          }
          v10 = WaitForSingleObject(hProcess.hProcess, dwMilliseconds);
        }
        if ( v10 )
          v11 = 258;
        else
          v11 = 0;
        TerminateJobObject(v7, v11);
        if ( *(_DWORD *)&g_dwDebugLevel )
        {
          if ( g_lpDebugMsg )
          {
            g_lpDebugMsg(4u, L"GPOScripts::ExecuteScriptsSynchronously: Completed WaitForSingleObject.");
          }
          else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
          {
            RedirectDebugMsg(4u, L"GPOScripts::ExecuteScriptsSynchronously: Completed WaitForSingleObject.");
          }
        }
        GPOScripts::HandleScriptErrorReporting(this, 0, a3);
      }
      else
      {
        LastError = GetLastError();
        TerminateProcess(hProcess.hProcess, LastError);
      }
    }
  }
  else
  {
    LastError = GetLastError();
  }
  XHandle::~XHandle(&v15);
  XHandle::~XHandle(&v16);
  CJob::~CJob((CJob *)&v17);
  return LastError;
}

```

## disassembly

```asm
0x18009479c  push    rbp
0x18009479e  push    rbx
0x18009479f  push    rsi
0x1800947a0  push    rdi
0x1800947a1  push    r12
0x1800947a3  push    r13
0x1800947a5  push    r14
0x1800947a7  push    r15
0x1800947a9  lea     rbp, [rsp-1Fh]
0x1800947ae  sub     rsp, 0E8h
0x1800947b5  mov     r15, r8
0x1800947b8  mov     r14d, edx
0x1800947bb  mov     rsi, rcx
0x1800947be  xorps   xmm0, xmm0
0x1800947c1  xor     eax, eax
0x1800947c3  movups  xmmword ptr [rsp+120h+hProcess], xmm0
0x1800947c8  mov     [rbp+57h+var_D0], rax
0x1800947cc  lea     edi, [rax+68h]
0x1800947cf  mov     r8d, edi; Size
0x1800947d2  xor     edx, edx; Val
0x1800947d4  lea     rcx, [rbp+57h+var_B0]; void *
0x1800947d8  call    memset_0
0x1800947dd  nop
0x1800947de  xor     r12d, r12d
0x1800947e1  mov     [rbp+57h+var_C0], r12
0x1800947e5  mov     [rbp+57h+var_C8], r12
0x1800947e9  xor     edx, edx; lpName
0x1800947eb  xor     ecx, ecx; lpJobAttributes
0x1800947ed  call    cs:__imp_CreateJobObjectW
0x1800947f3  mov     rbx, rax
0x1800947f6  mov     [rbp+57h+var_B8], rax
0x1800947fa  test    rax, rax
0x1800947fd  jnz     short loc_18009480C
0x1800947ff  call    cs:__imp_GetLastError
0x180094805  mov     edi, eax
0x180094807  jmp     loc_180094AC3
0x18009480c  mov     [rbp+57h+JobObjectInformation], 1
0x180094813  mov     r13d, 4
0x180094819  mov     r9d, r13d; cbJobObjectInformationLength
0x18009481c  lea     r8, [rbp+57h+JobObjectInformation]; lpJobObjectInformation
0x180094820  lea     edx, [r13+2]; JobObjectInformationClass
0x180094824  mov     rcx, rbx; hJob
0x180094827  call    cs:__imp_SetInformationJobObject
0x18009482d  test    eax, eax
0x18009482f  jz      short loc_1800947FF
0x180094831  xorps   xmm0, xmm0
0x180094834  xor     eax, eax
0x180094836  movups  xmmword ptr [rsp+120h+hProcess], xmm0
0x18009483b  mov     [rbp+57h+var_D0], rax
0x18009483f  mov     r8, rdi; Size
0x180094842  xor     edx, edx; Val
0x180094844  lea     rcx, [rbp+57h+var_B0]; void *
0x180094848  call    memset_0
0x18009484d  mov     [rbp+57h+var_B0.cb], edi
0x180094850  lea     eax, [r13-2]
0x180094854  mov     [rbp+57h+var_B0.wShowWindow], ax
0x180094858  lea     rax, aWinsta0Winlogo; "Winsta0\\Winlogon"
0x18009485f  lea     rcx, aWinsta0Default; "Winsta0\\Default"
0x180094866  cmp     [rsi+10h], r12d
0x18009486a  cmovz   rax, rcx
0x18009486e  mov     [rbp+57h+var_B0.lpDesktop], rax
0x180094872  mov     [rbp+57h+var_B0.dwFlags], r12d
0x180094876  lea     rdi, ?ScriptParametersArray@GPOScripts@@0PAU_ScriptParameters@@A; _ScriptParameters near * GPOScripts::ScriptParametersArray
0x18009487d  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x180094884  jz      short loc_1800948DC
0x180094886  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18009488d  test    rax, rax
0x180094890  jz      short loc_1800948AF
0x180094892  movsxd  rcx, dword ptr [rsi]
0x180094895  lea     r8, [rcx+rcx*2]
0x180094899  mov     r8, [rdi+r8*8+8]
0x18009489e  lea     rdx, aSynchronouslyP; "Synchronously processing script <%ws>"
0x1800948a5  mov     ecx, r13d
0x1800948a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800948ad  jmp     short loc_1800948DC
0x1800948af  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x1800948b6  jz      short loc_1800948DC
0x1800948b8  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800948bf  jz      short loc_1800948DC
0x1800948c1  movsxd  rax, dword ptr [rsi]
0x1800948c4  lea     r8, [rax+rax*2]
0x1800948c8  mov     r8, [rdi+r8*8+8]
0x1800948cd  lea     rdx, aSynchronouslyP; "Synchronously processing script <%ws>"
0x1800948d4  mov     ecx, r13d; unsigned int
0x1800948d7  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800948dc  movsxd  rax, dword ptr [rsi]
0x1800948df  lea     rdx, [rax+rax*2]
0x1800948e3  mov     [rsp+120h+var_F0], r15; void *
0x1800948e8  lea     rax, [rsp+120h+hProcess]
0x1800948ed  mov     [rsp+120h+var_100], rax; struct _PROCESS_INFORMATION *
0x1800948f2  lea     r9, [rbp+57h+var_B0]; struct _STARTUPINFOW *
0x1800948f6  mov     r8d, [rsi+14h]; unsigned int
0x1800948fa  mov     rdx, [rdi+rdx*8+8]; unsigned __int16 *
0x1800948ff  mov     rcx, rsi; this
0x180094902  call    ?LaunchProcessInSession@GPOScripts@@AEAAKPEBGKPEAU_STARTUPINFOW@@PEAU_PROCESS_INFORMATION@@KPEAX@Z; GPOScripts::LaunchProcessInSession(ushort const *,ulong,_STARTUPINFOW *,_PROCESS_INFORMATION *,ulong,void *)
0x180094907  mov     edi, eax
0x180094909  test    eax, eax
0x18009490b  jz      loc_18009499C
0x180094911  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x180094918  jz      loc_180094AC3
0x18009491e  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180094925  test    rax, rax
0x180094928  jz      short loc_180094956
0x18009492a  movsxd  rdx, dword ptr [rsi]
0x18009492d  lea     r8, [rdx+rdx*2]
0x180094931  mov     r9d, edi
0x180094934  lea     rdx, ?ScriptParametersArray@GPOScripts@@0PAU_ScriptParameters@@A; _ScriptParameters near * GPOScripts::ScriptParametersArray
0x18009493b  mov     r8, [rdx+r8*8+8]
0x180094940  lea     rdx, aFailedToStartS; "Failed to start system process <%ws>, w"...
0x180094947  mov     ecx, 2
0x18009494c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094951  jmp     loc_180094AC3
0x180094956  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x18009495d  jz      loc_180094AC3
0x180094963  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18009496a  jz      loc_180094AC3
0x180094970  movsxd  rax, dword ptr [rsi]
0x180094973  lea     r8, [rax+rax*2]
0x180094977  mov     r9d, edi
0x18009497a  lea     rdx, ?ScriptParametersArray@GPOScripts@@0PAU_ScriptParameters@@A; _ScriptParameters near * GPOScripts::ScriptParametersArray
0x180094981  mov     r8, [rdx+r8*8+8]
0x180094986  lea     rdx, aFailedToStartS; "Failed to start system process <%ws>, w"...
0x18009498d  mov     ecx, 2; unsigned int
0x180094992  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180094997  jmp     loc_180094AC3
0x18009499c  mov     rdx, [rsp+120h+hProcess+8]
0x1800949a1  lea     rcx, [rbp+57h+var_C0]
0x1800949a5  call    ??4XHandle@@QEAAXPEAX@Z; XHandle::operator=(void *)
0x1800949aa  mov     rdx, [rsp+120h+hProcess]
0x1800949af  lea     rcx, [rbp+57h+var_C8]
0x1800949b3  call    ??4XHandle@@QEAAXPEAX@Z; XHandle::operator=(void *)
0x1800949b8  mov     rdx, [rsp+120h+hProcess]; hProcess
0x1800949bd  mov     rcx, rbx; hJob
0x1800949c0  call    cs:__imp_AssignProcessToJobObject
0x1800949c6  test    eax, eax
0x1800949c8  jnz     short loc_1800949E4
0x1800949ca  call    cs:__imp_GetLastError
0x1800949d0  mov     edi, eax
0x1800949d2  mov     edx, eax; uExitCode
0x1800949d4  mov     rcx, [rsp+120h+hProcess]; hProcess
0x1800949d9  call    cs:__imp_TerminateProcess
0x1800949df  jmp     loc_180094AC3
0x1800949e4  mov     rcx, [rsp+120h+hProcess+8]; hThread
0x1800949e9  call    cs:__imp_ResumeThread
0x1800949ef  cmp     dword ptr [rsi], 3
0x1800949f2  jnz     short loc_180094A03
0x1800949f4  mov     edx, r14d; dwMilliseconds
0x1800949f7  mov     rcx, [rsp+120h+hProcess]; hHandle
0x1800949fc  call    ?KeepServiceAlive@CGPService@@SAKPEAXK@Z; CGPService::KeepServiceAlive(void *,ulong)
0x180094a01  jmp     short loc_180094A58
0x180094a03  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x180094a0a  jz      short loc_180094A4A
0x180094a0c  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180094a13  test    rax, rax
0x180094a16  jz      short loc_180094A29
0x180094a18  lea     rdx, aGposcriptsExec_2; "GPOScripts::ExecuteScriptsSynchronously"...
0x180094a1f  mov     ecx, r13d
0x180094a22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094a27  jmp     short loc_180094A4A
0x180094a29  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x180094a30  jz      short loc_180094A4A
0x180094a32  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180094a39  jz      short loc_180094A4A
0x180094a3b  lea     rdx, aGposcriptsExec_2; "GPOScripts::ExecuteScriptsSynchronously"...
0x180094a42  mov     ecx, r13d; unsigned int
0x180094a45  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180094a4a  mov     edx, r14d; dwMilliseconds
0x180094a4d  mov     rcx, [rsp+120h+hProcess]; hHandle
0x180094a52  call    cs:__imp_WaitForSingleObject
0x180094a58  mov     rcx, rbx; hJob
0x180094a5b  test    eax, eax
0x180094a5d  jnz     short loc_180094A63
0x180094a5f  xor     edx, edx
0x180094a61  jmp     short loc_180094A68
0x180094a63  mov     edx, 102h; uExitCode
0x180094a68  call    cs:__imp_TerminateJobObject
0x180094a6e  cmp     cs:?g_dwDebugLevel@@3KA, r12d; ulong g_dwDebugLevel
0x180094a75  jz      short loc_180094AB5
0x180094a77  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x180094a7e  test    rax, rax
0x180094a81  jz      short loc_180094A94
0x180094a83  lea     rdx, aGposcriptsExec_5; "GPOScripts::ExecuteScriptsSynchronously"...
0x180094a8a  mov     ecx, r13d
0x180094a8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094a92  jmp     short loc_180094AB5
0x180094a94  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r12; void * g_lpDebugMsgContextInstance
0x180094a9b  jz      short loc_180094AB5
0x180094a9d  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r12; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x180094aa4  jz      short loc_180094AB5
0x180094aa6  lea     rdx, aGposcriptsExec_5; "GPOScripts::ExecuteScriptsSynchronously"...
0x180094aad  mov     ecx, r13d; unsigned int
0x180094ab0  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x180094ab5  mov     r8, r15; void *
0x180094ab8  xor     edx, edx; int
0x180094aba  mov     rcx, rsi; this
0x180094abd  call    ?HandleScriptErrorReporting@GPOScripts@@AEAAKHPEAX@Z; GPOScripts::HandleScriptErrorReporting(int,void *)
0x180094ac2  nop
0x180094ac3  lea     rcx, [rbp+57h+var_C8]; this
0x180094ac7  call    ??1XHandle@@QEAA@XZ; XHandle::~XHandle(void)
0x180094acc  nop
0x180094acd  lea     rcx, [rbp+57h+var_C0]; this
0x180094ad1  call    ??1XHandle@@QEAA@XZ; XHandle::~XHandle(void)
0x180094ad6  nop
0x180094ad7  lea     rcx, [rbp+57h+var_B8]; this
0x180094adb  call    ??1CJob@@QEAA@XZ; CJob::~CJob(void)
0x180094ae0  mov     eax, edi
0x180094ae2  add     rsp, 0E8h
0x180094ae9  pop     r15
0x180094aeb  pop     r14
0x180094aed  pop     r13
0x180094aef  pop     r12
0x180094af1  pop     rdi
0x180094af2  pop     rsi
0x180094af3  pop     rbx
0x180094af4  pop     rbp
0x180094af5  retn
```
