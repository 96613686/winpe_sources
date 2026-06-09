# MsiUIMessageContext::RunInstall(CEngineMainThreadData &,iuiEnum,IMsiMessage *)

- ea: `0x180009268`
- end: `0x180009c32`
- name: `?RunInstall@MsiUIMessageContext@@QEAAIAEAUCEngineMainThreadData@@W4iuiEnum@@PEAUIMsiMessage@@@Z`
- size: `2506`
- prototype: `unsigned int __high(struct CEngineMainThreadData *, enum iuiEnum, struct IMsiMessage *)`
- caller_count: `2`
- callee_count: `20`
- tags: `authz_impersonation, installer_update`

## callers

- `0x1800079a8`
- `0x1801b8530`

## callees

- `0x18000919c`
- `0x180009268`
- `0x180009c38`
- `0x18000c4bc`
- `0x18001f57c`
- `0x1800200a4`
- `0x1800202e4`
- `0x180027634`
- `0x18004ccbc`
- `0x18004d644`
- `0x180078fc8`
- `0x1800a614c`
- `0x1800ca3a0`
- `0x180140058`
- `0x18015d038`
- `0x1801c8618`
- `0x1801d58b0`
- `0x18022255c`
- `0x180259830`
- `0x180266010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180009954`
- `KERNEL32!LeaveCriticalSection` at `0x180009954`
- `KERNEL32!GetExitCodeThread` at `0x1800099c9`
- `KERNEL32!GetExitCodeThread` at `0x1800099c9`
- `KERNEL32!GetLastError` at `0x18000950a`
- `KERNEL32!GetLastError` at `0x18000950a`
- `KERNEL32!IsDebuggerPresent` at `0x1800098f5`
- `KERNEL32!IsDebuggerPresent` at `0x1800098f5`
- `KERNEL32!EnterCriticalSection` at `0x180009929`
- `KERNEL32!EnterCriticalSection` at `0x180009929`
- `KERNEL32!SetEvent` at `0x1800094b1`
- `KERNEL32!SetEvent` at `0x1800094b1`
- `KERNEL32!CreateThread` at `0x1800093e5`
- `KERNEL32!CreateThread` at `0x1800093e5`
- `KERNEL32!TerminateThread` at `0x180009941`
- `KERNEL32!TerminateThread` at `0x180009941`
- `USER32!MsgWaitForMultipleObjects` at `0x180009433`
- `USER32!MsgWaitForMultipleObjects` at `0x180009433`
- `USER32!PeekMessageW` at `0x1800095cb`
- `USER32!PeekMessageW` at `0x1800095cb`
- `USER32!TranslateMessage` at `0x180009ae4`
- `USER32!TranslateMessage` at `0x180009ae4`
- `USER32!DispatchMessageW` at `0x180009af8`
- `USER32!DispatchMessageW` at `0x180009af8`
- `USER32!IsDialogMessageW` at `0x1800095ef`
- `USER32!IsDialogMessageW` at `0x1800095ef`

## string_xrefs

- `0x180009bab`: `Internal MSI error. Installer terminated prematurely.`
- `0x1800096c8`: `Running installation inside multi-package transaction %s`
- `0x180009b36`: `Invalid event trigger in wait for engine thread`
- `0x180009705`: `_MSIExecute`

## pseudocode

```c
__int64 __fastcall MsiUIMessageContext::RunInstall(__int64 a1, __int64 a2, int a3, __int64 a4)
{
  int v7; // eax
  unsigned int v8; // ebx
  __int64 v9; // rdi
  struct IMsiRecord *Record; // rbx
  int v11; // ebx
  DWORD v12; // eax
  DWORD LastError; // eax
  MsiUIMessageContext *v15; // rcx
  HWND CurrentWindow; // rax
  struct IUnknown *v17; // rbx
  struct IUnknownVtbl *lpVtbl; // rbx
  const unsigned __int16 *v19; // rax
  void *v20; // rbx
  unsigned int v21; // ebx
  unsigned int v22; // r8d
  unsigned int v23; // ebx
  unsigned int v24; // ebx
  unsigned int v25; // [rsp+50h] [rbp-98h]
  void *v26; // [rsp+58h] [rbp-90h]
  __int64 v27; // [rsp+60h] [rbp-88h] BYREF
  int v28; // [rsp+68h] [rbp-80h]
  int v29; // [rsp+6Ch] [rbp-7Ch] BYREF
  unsigned int v30; // [rsp+70h] [rbp-78h] BYREF
  void *v31; // [rsp+78h] [rbp-70h] BYREF
  _QWORD v32[2]; // [rsp+80h] [rbp-68h] BYREF
  tagMSG Msg; // [rsp+90h] [rbp-58h] BYREF
  __int64 ExitCode; // [rsp+F0h] [rbp+8h] BYREF

  ExitCode = a1;
  v32[1] = &g_MessageContext;
  v30 = 0;
  v29 = 1;
  if ( (a3 & 0xFFFF23FF) != 0 )
  {
    switch ( a3 & 0xFFFF23FF )
    {
      case 1u:
        v7 = 4;
        break;
      case 2u:
        v7 = 3;
        break;
      case 3u:
        v7 = 2;
        break;
      default:
        v7 = 1;
        break;
    }
  }
  else
  {
    v7 = 5;
  }
  if ( !(unsigned int)((__int64 (__fastcall *)(bool, _QWORD, _QWORD, _QWORD, int, int *, unsigned int *))TSAPPCMP::TermSrvMSIOkToRun)(
                        g_scServerContext == 2,
                        *(_QWORD *)(a2 + 8),
                        *(_QWORD *)(a2 + 16),
                        *(_QWORD *)(a2 + 24),
                        v7,
                        &v29,
                        &v30)
    && !v29 )
  {
    return v30;
  }
  v8 = MsiUIMessageContext::Initialize((__int64)&g_MessageContext, 0, a3, (const struct CEngineMainThreadData *)a2, 0);
  if ( v8 )
  {
    if ( *((_QWORD *)&xmmword_180313710 + 1) )
      CLogFile::Flush(*((CLogFile **)&xmmword_180313710 + 1), 1);
    return v8;
  }
  else
  {
    v9 = -1;
    v27 = -1;
    if ( g_scServerContext == 2 )
    {
      v17 = CMsiTransaction::m_pMsiTransaction;
      if ( CMsiTransaction::m_pMsiTransaction )
      {
        (*((void (__fastcall **)(struct IUnknownVtbl *))CMsiTransaction::m_pMsiTransaction[1].lpVtbl->QueryInterface + 1))(CMsiTransaction::m_pMsiTransaction[1].lpVtbl);
        lpVtbl = v17[1].lpVtbl;
        v32[0] = lpVtbl;
        if ( g_dmDiagnosticMode )
        {
          v19 = (const unsigned __int16 *)MsiString::operator unsigned short const *(v32);
          DebugString(
            9,
            0,
            0,
            L"Running installation inside multi-package transaction %s",
            v19,
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            0,
            0);
        }
        (*((void (__fastcall **)(struct IUnknownVtbl *))lpVtbl->QueryInterface + 2))(lpVtbl);
      }
      v31 = 0;
      if ( FMutexExists(L"_MSIExecute", &v31) && (v20 = v31) != 0 )
      {
        if ( g_dmDiagnosticMode )
          DebugString(
            9,
            0,
            0,
            L"Grabbed execution mutex.",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            0,
            0);
        CSysHandle::operator=(&v27, v20);
        v9 = v27;
      }
      else if ( g_dmDiagnosticMode )
      {
        DebugString(
          9,
          0,
          0,
          L"Failed to grab execution mutex.",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          0,
          0);
      }
    }
    if ( a4 )
    {
      qword_180313698 = a4;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a4 + 8LL))(a4);
      Record = CreateRecord(1u);
      (*(void (__fastcall **)(struct IMsiRecord *, __int64, __int64))(*(_QWORD *)Record + 104LL))(Record, 1, 6);
      MsiUIMessageContext::Invoke(&g_MessageContext, 402653184, Record);
      (*(void (__fastcall **)(struct IMsiRecord *))(*(_QWORD *)Record + 16LL))(Record);
    }
    if ( GetTestFlag(84) )
    {
      v21 = CreateAndRunEngine(
              *(_DWORD *)a2,
              *(const WCHAR **)(a2 + 8),
              *(const unsigned __int16 **)(a2 + 16),
              *(const unsigned __int16 **)(a2 + 24),
              0,
              *(_DWORD *)(a2 + 32),
              *(_QWORD *)(a2 + 40));
      MsiUIMessageContext::Terminate((MsiUIMessageContext *)&g_MessageContext, 0, v21 != 0, 0);
      CSysHandle::~CSysHandle((CSysHandle *)&v27);
      return v21;
    }
    LODWORD(ExitCode) = 0;
    hThread = CreateThread(
                0,
                0xA000u,
                MsiUIMessageContext::MainEngineThread,
                (LPVOID)a2,
                0,
                (LPDWORD)&qword_180313658 + 1);
    if ( hThread )
    {
      v11 = 0;
      v28 = 0;
      HIDWORD(qword_1803136B4) = 0;
      while ( 1 )
      {
        v12 = MsgWaitForMultipleObjects(2u, &pHandles, 0, g_iUIWaitTick, 0x1CFFu);
        if ( v12 == -1 )
          break;
        switch ( v12 )
        {
          case 0x102u:
            if ( !qword_180313698
              && (unsigned int)MsiUIMessageContext::ProcessMessage(&g_MessageContext, 167772160, &off_18030FDB0) == 2 )
            {
              LOBYTE(word_180313684) = 1;
            }
            if ( (_DWORD)qword_1803136B4 )
            {
              LODWORD(qword_1803136B4) = 0;
              v11 = 0;
              v28 = 0;
            }
            else if ( !HIDWORD(qword_1803136AC) )
            {
              v11 += g_iUITicksStep;
              v28 = v11;
              if ( v11 >= g_cWaitTimeout )
              {
                if ( g_dmDiagnosticMode )
                  DebugString(
                    9,
                    0,
                    0,
                    "RunEngine wait timed out",
                    "(NULL)",
                    "(NULL)",
                    "(NULL)",
                    "(NULL)",
                    "(NULL)",
                    "(NULL)",
                    v25,
                    v26);
                if ( !IsDebuggerPresent()
                  && (unsigned int)MsiUIMessageContext::ProcessMessage(&g_MessageContext, 251658533, 0) != 4 )
                {
                  EnterCriticalSection(&vcsHeap);
                  TerminateThread(hThread, 0x3E3u);
                  LeaveCriticalSection(&vcsHeap);
                  if ( *((_QWORD *)&xmmword_180313710 + 1) )
                    CLogFile::Flush(*((CLogFile **)&xmmword_180313710 + 1), 1);
                  CSysHandle::operator=(&v27, -1);
                  MsiUIMessageContext::Terminate((MsiUIMessageContext *)&g_MessageContext, 1, 1, 0);
                  CSysHandle::~CSysHandle((CSysHandle *)&v27);
                  return 1603;
                }
                v11 = 0;
                v28 = 0;
                HIDWORD(qword_1803136B4) = 0;
              }
            }
            break;
          case 1u:
            GetExitCodeThread(hThread, (LPDWORD)&ExitCode);
            v22 = ExitCode;
            switch ( (_DWORD)ExitCode )
            {
              case 7:
                MsiUIMessageContext::ProcessMessage(&g_MessageContext, 251658256, 0);
                v22 = 995;
                break;
              case 8:
                v22 = 14;
                break;
              case 0x3E3:
                goto LABEL_83;
              default:
                if ( !g_scServerContext && qword_1803136E0 )
                {
                  CMsiSQMSession::RecordDWORD(qword_1803136E0, 0xE27u, ExitCode);
                  v22 = ExitCode;
                }
                MsiUIMessageContext::Terminate((MsiUIMessageContext *)&g_MessageContext, 0, v22 != 0, 0);
                v23 = ExitCode;
                CSysHandle::~CSysHandle((CSysHandle *)&v27);
                return v23;
            }
            LODWORD(ExitCode) = v22;
LABEL_83:
            if ( *((_QWORD *)&xmmword_180313710 + 1) )
            {
              CLogFile::Flush(*((CLogFile **)&xmmword_180313710 + 1), 1);
              v22 = ExitCode;
            }
            if ( !g_scServerContext && qword_1803136E0 )
              CMsiSQMSession::RecordDWORD(qword_1803136E0, 0xE27u, v22);
            CSysHandle::operator=(&v27, -1);
            MsiUIMessageContext::Terminate((MsiUIMessageContext *)&g_MessageContext, 1, 1, 0);
            v24 = ExitCode;
            CSysHandle::~CSysHandle((CSysHandle *)&v27);
            return v24;
          case 2u:
            memset(&Msg, 0, sizeof(Msg));
            while ( PeekMessageW(&Msg, 0, 0, 0, 1u) )
            {
              CurrentWindow = MsiUIMessageContext::GetCurrentWindow(v15);
              if ( !IsDialogMessageW(CurrentWindow, &Msg) )
              {
                TranslateMessage(&Msg);
                DispatchMessageW(&Msg);
              }
            }
            break;
          default:
            v11 = 0;
            v28 = 0;
            HIDWORD(qword_1803136B4) = 0;
            if ( dword_180313630 == 0x80000000 )
            {
              if ( g_dmDiagnosticMode )
                DebugString(
                  9,
                  0,
                  0,
                  "Invalid event trigger in wait for engine thread",
                  "(NULL)",
                  "(NULL)",
                  "(NULL)",
                  "(NULL)",
                  "(NULL)",
                  "(NULL)",
                  v25,
                  v26);
            }
            else
            {
              dword_180313680 = -2147483647;
              dword_180313680 = MsiUIMessageContext::ProcessMessage(
                                  &g_MessageContext,
                                  (unsigned int)dword_180313630,
                                  qword_180313628);
              dword_180313630 = 0x80000000;
              SetEvent(*(&hThread + 1));
            }
            break;
        }
      }
      LastError = GetLastError();
      LODWORD(ExitCode) = LastError;
      if ( g_dmDiagnosticMode )
        DebugString(
          9,
          0,
          0,
          L"Wait Failed in RunEngine. GetLastError returned %d.",
          (const unsigned __int16 *)LastError,
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          0,
          0);
      if ( *((_QWORD *)&xmmword_180313710 + 1) )
        CLogFile::Flush(*((CLogFile **)&xmmword_180313710 + 1), 1);
      if ( v9 != -1 )
        MsiCloseSysHandle(v9);
      return 0;
    }
    else
    {
      if ( !g_scServerContext && qword_1803136E0 )
        CMsiSQMSession::RecordDWORD(qword_1803136E0, 0xE27u, 0x65Fu);
      CSysHandle::operator=(&v27, -1);
      MsiUIMessageContext::Terminate((MsiUIMessageContext *)&g_MessageContext, 1, 1, 0);
      CSysHandle::~CSysHandle((CSysHandle *)&v27);
      return 1631;
    }
  }
}

```

## disassembly

```asm
0x180009268  mov     rax, rsp
0x18000926b  mov     [rax+10h], rbx
0x18000926f  mov     [rax+18h], rsi
0x180009273  mov     [rax+8], rcx
0x180009277  push    rdi
0x180009278  push    r12
0x18000927a  push    r13
0x18000927c  push    r14
0x18000927e  push    r15
0x180009280  sub     rsp, 0C0h
0x180009287  mov     r15, r9
0x18000928a  mov     ebx, r8d
0x18000928d  mov     r14, rdx
0x180009290  lea     rdi, ?g_MessageContext@@3UMsiUIMessageContext@@A; MsiUIMessageContext g_MessageContext
0x180009297  mov     [rsp+0E8h+var_60], rdi
0x18000929f  xor     r12d, r12d
0x1800092a2  mov     [rax-78h], r12d
0x1800092a6  lea     r13d, [r12+1]
0x1800092ab  mov     [rax-7Ch], r13d
0x1800092af  mov     ecx, ebx
0x1800092b1  and     ecx, 0FFFF23FFh
0x1800092b7  jnz     loc_180009605
0x1800092bd  lea     eax, [rcx+5]
0x1800092c0  mov     ecx, r12d
0x1800092c3  cmp     cs:?g_scServerContext@@3W4scEnum@@A, 2; scEnum g_scServerContext
0x1800092ca  setz    cl
0x1800092cd  lea     rdx, [rsp+0E8h+var_78]
0x1800092d2  mov     [rsp+0E8h+var_B8], rdx
0x1800092d7  lea     rdx, [rsp+0E8h+var_7C]
0x1800092dc  mov     [rsp+0E8h+lpThreadId], rdx
0x1800092e1  mov     [rsp+0E8h+dwCreationFlags], eax
0x1800092e5  mov     r9, [r14+18h]
0x1800092e9  mov     r8, [r14+10h]
0x1800092ed  mov     rdx, [r14+8]
0x1800092f1  mov     rax, cs:?TermSrvMSIOkToRun@TSAPPCMP@@3P6AJHPEBG00KPEAHPEAI@ZEA; long (*TSAPPCMP::TermSrvMSIOkToRun)(int,ushort const *,ushort const *,ushort const *,ulong,int *,uint *)
0x1800092f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800092fd  test    eax, eax
0x1800092ff  jz      loc_180009547
0x180009305  mov     byte ptr [rsp+0E8h+dwCreationFlags], r12b
0x18000930a  mov     r9, r14
0x18000930d  mov     r8d, ebx
0x180009310  xor     edx, edx
0x180009312  mov     rcx, rdi
0x180009315  call    ?Initialize@MsiUIMessageContext@@QEAAI_NW4iuiEnum@@PEBUCEngineMainThreadData@@_N@Z; MsiUIMessageContext::Initialize(bool,iuiEnum,CEngineMainThreadData const *,bool)
0x18000931a  mov     ebx, eax
0x18000931c  test    eax, eax
0x18000931e  jnz     loc_18000963A
0x180009324  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180009328  mov     [rsp+0E8h+var_88], rdi
0x18000932d  cmp     cs:?g_scServerContext@@3W4scEnum@@A, 2; scEnum g_scServerContext
0x180009334  jz      loc_180009655
0x18000933a  lea     rsi, aNull; "(NULL)"
0x180009341  test    r15, r15
0x180009344  jz      loc_1800097C9
0x18000934a  mov     cs:qword_180313698, r15
0x180009351  mov     rax, [r15]
0x180009354  mov     rcx, r15
0x180009357  mov     rax, [rax+8]
0x18000935b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009360  mov     ecx, r13d; unsigned int
0x180009363  call    ?CreateRecord@@YAAEAVIMsiRecord@@I@Z; CreateRecord(uint)
0x180009368  mov     rbx, rax
0x18000936b  mov     rax, [rax]
0x18000936e  mov     r8d, 6
0x180009374  mov     edx, r13d
0x180009377  mov     rcx, rbx
0x18000937a  mov     rax, [rax+68h]
0x18000937e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009383  mov     r8, rbx
0x180009386  mov     edx, 18000000h
0x18000938b  lea     r15, ?g_MessageContext@@3UMsiUIMessageContext@@A; MsiUIMessageContext g_MessageContext
0x180009392  mov     rcx, r15
0x180009395  call    ?Invoke@MsiUIMessageContext@@QEAA?AW4imsEnum@@W4imtEnum@@PEAVIMsiRecord@@@Z; MsiUIMessageContext::Invoke(imtEnum,IMsiRecord *)
0x18000939a  mov     rax, [rbx]
0x18000939d  mov     rcx, rbx
0x1800093a0  mov     rax, [rax+10h]
0x1800093a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800093a9  mov     ecx, 54h ; 'T'; int
0x1800093ae  call    ?GetTestFlag@@YA_NH@Z; GetTestFlag(int)
0x1800093b3  test    al, al
0x1800093b5  jnz     loc_1800097D5
0x1800093bb  mov     dword ptr [rsp+0E8h+ExitCode], r12d
0x1800093c3  lea     rax, qword_180313658+4
0x1800093ca  mov     [rsp+0E8h+lpThreadId], rax; lpThreadId
0x1800093cf  mov     [rsp+0E8h+dwCreationFlags], r12d; dwCreationFlags
0x1800093d4  mov     r9, r14; lpParameter
0x1800093d7  lea     r8, ?MainEngineThread@MsiUIMessageContext@@CAKPEAX@Z; lpStartAddress
0x1800093de  mov     edx, 0A000h; dwStackSize
0x1800093e3  xor     ecx, ecx; lpThreadAttributes
0x1800093e5  call    cs:__imp_CreateThread
0x1800093ec  nop     dword ptr [rax+rax+00h]
0x1800093f1  mov     qword ptr cs:hThread, rax
0x1800093f8  test    rax, rax
0x1800093fb  jz      loc_180009825
0x180009401  mov     ebx, r12d
0x180009404  mov     [rsp+0E8h+var_80], ebx
0x180009408  mov     dword ptr cs:qword_1803136B4+4, r12d
0x18000940f  lea     r14, aNull_0; "(NULL)"
0x180009416  mov     [rsp+0E8h+dwCreationFlags], 1CFFh; dwWakeMask
0x18000941e  mov     r9d, cs:?g_iUIWaitTick@@3HA; dwMilliseconds
0x180009425  xor     r8d, r8d; fWaitAll
0x180009428  lea     rdx, pHandles; pHandles
0x18000942f  lea     ecx, [r8+2]; nCount
0x180009433  call    cs:__imp_MsgWaitForMultipleObjects
0x18000943a  nop     dword ptr [rax+rax+00h]
0x18000943f  cmp     eax, 0FFFFFFFFh
0x180009442  jz      loc_18000950A
0x180009448  cmp     eax, 102h
0x18000944d  jz      short loc_1800094C2
0x18000944f  cmp     eax, r13d
0x180009452  jz      loc_1800099BA
0x180009458  cmp     eax, 2
0x18000945b  jz      loc_18000959B
0x180009461  mov     ebx, r12d
0x180009464  mov     [rsp+0E8h+var_80], ebx
0x180009468  mov     dword ptr cs:qword_1803136B4+4, r12d
0x18000946f  mov     edx, cs:dword_180313630
0x180009475  cmp     edx, 80000000h
0x18000947b  jz      loc_180009B09
0x180009481  mov     cs:dword_180313680, 80000001h
0x18000948b  mov     r8, cs:qword_180313628
0x180009492  mov     rcx, r15
0x180009495  call    ?ProcessMessage@MsiUIMessageContext@@AEAA?AW4imsEnum@@W4imtEnum@@PEAVIMsiRecord@@@Z; MsiUIMessageContext::ProcessMessage(imtEnum,IMsiRecord *)
0x18000949a  mov     cs:dword_180313680, eax
0x1800094a0  mov     cs:dword_180313630, 80000000h
0x1800094aa  mov     rcx, qword ptr cs:hThread+8; hEvent
0x1800094b1  call    cs:__imp_SetEvent
0x1800094b8  nop     dword ptr [rax+rax+00h]
0x1800094bd  jmp     loc_180009416
0x1800094c2  cmp     cs:qword_180313698, r12
0x1800094c9  jz      short loc_1800094E8
0x1800094cb  cmp     dword ptr cs:qword_1803136B4, r12d
0x1800094d2  jz      loc_180009897
0x1800094d8  mov     dword ptr cs:qword_1803136B4, r12d
0x1800094df  mov     ebx, r12d
0x1800094e2  mov     [rsp+0E8h+var_80], ebx
0x1800094e6  jmp     short loc_1800094BD
0x1800094e8  lea     r8, off_18030FDB0
0x1800094ef  mov     edx, 0A000000h
0x1800094f4  mov     rcx, r15
0x1800094f7  call    ?ProcessMessage@MsiUIMessageContext@@AEAA?AW4imsEnum@@W4imtEnum@@PEAVIMsiRecord@@@Z; MsiUIMessageContext::ProcessMessage(imtEnum,IMsiRecord *)
0x1800094fc  cmp     eax, 2
0x1800094ff  jnz     short loc_1800094CB
0x180009501  mov     byte ptr cs:word_180313684, r13b
0x180009508  jmp     short loc_1800094CB
0x18000950a  call    cs:__imp_GetLastError
0x180009511  nop     dword ptr [rax+rax+00h]
0x180009516  mov     dword ptr [rsp+0E8h+ExitCode], eax
0x18000951d  cmp     cs:?g_dmDiagnosticMode@@3HA, r12d; int g_dmDiagnosticMode
0x180009524  jnz     short loc_18000955B
0x180009526  mov     rcx, qword ptr cs:xmmword_180313710+8; this
0x18000952d  test    rcx, rcx
0x180009530  jnz     loc_18000987D
0x180009536  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18000953a  jnz     loc_18000988A
0x180009540  xor     eax, eax
0x180009542  jmp     loc_180009C14
0x180009547  cmp     [rsp+0E8h+var_7C], r12d
0x18000954c  jnz     loc_180009305
0x180009552  mov     eax, [rsp+0E8h+var_78]
0x180009556  jmp     loc_180009C14
0x18000955b  mov     eax, eax
0x18000955d  xor     edx, edx; unsigned __int16
0x18000955f  mov     [rsp+0E8h+var_90], r12; void *
0x180009564  mov     [rsp+0E8h+var_98], r12d; unsigned int
0x180009569  mov     [rsp+0E8h+var_A0], rsi; unsigned __int16 *
0x18000956e  mov     [rsp+0E8h+var_A8], rsi; unsigned __int16 *
0x180009573  mov     [rsp+0E8h+var_B0], rsi; unsigned __int16 *
0x180009578  mov     [rsp+0E8h+var_B8], rsi; unsigned __int16 *
0x18000957d  mov     [rsp+0E8h+lpThreadId], rsi; unsigned __int16 *
0x180009582  mov     qword ptr [rsp+0E8h+dwCreationFlags], rax; unsigned __int16 *
0x180009587  lea     r9, aWaitFailedInRu; "Wait Failed in RunEngine. GetLastError "...
0x18000958e  xor     r8d, r8d; int
0x180009591  lea     ecx, [rdx+9]; int
0x180009594  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x180009599  jmp     short loc_180009526
0x18000959b  xorps   xmm0, xmm0
0x18000959e  movups  xmmword ptr [rsp+0E8h+Msg.hwnd], xmm0
0x1800095a6  movups  xmmword ptr [rsp+0E8h+Msg.wParam], xmm0
0x1800095ae  movups  xmmword ptr [rsp+0E8h+Msg.time], xmm0
0x1800095b6  mov     [rsp+0E8h+dwCreationFlags], r13d; wRemoveMsg
0x1800095bb  xor     r9d, r9d; wMsgFilterMax
0x1800095be  xor     r8d, r8d; wMsgFilterMin
0x1800095c1  xor     edx, edx; hWnd
0x1800095c3  lea     rcx, [rsp+0E8h+Msg]; lpMsg
0x1800095cb  call    cs:__imp_PeekMessageW
0x1800095d2  nop     dword ptr [rax+rax+00h]
0x1800095d7  test    eax, eax
0x1800095d9  jz      loc_1800094BD
0x1800095df  call    ?GetCurrentWindow@MsiUIMessageContext@@QEAAPEAUHWND__@@XZ; MsiUIMessageContext::GetCurrentWindow(void)
0x1800095e4  mov     rcx, rax; hDlg
0x1800095e7  lea     rdx, [rsp+0E8h+Msg]; lpMsg
0x1800095ef  call    cs:__imp_IsDialogMessageW
0x1800095f6  nop     dword ptr [rax+rax+00h]
0x1800095fb  test    eax, eax
0x1800095fd  jz      loc_180009ADC
0x180009603  jmp     short loc_1800095B6
0x180009605  sub     ecx, r13d
0x180009608  jz      short loc_180009630
0x18000960a  sub     ecx, r13d
0x18000960d  jz      short loc_180009626
0x18000960f  cmp     ecx, r13d
0x180009612  jz      short loc_18000961C
0x180009614  mov     eax, r13d
0x180009617  jmp     loc_1800092C0
0x18000961c  mov     eax, 2
0x180009621  jmp     loc_1800092C0
0x180009626  mov     eax, 3
0x18000962b  jmp     loc_1800092C0
0x180009630  mov     eax, 4
0x180009635  jmp     loc_1800092C0
0x18000963a  mov     rcx, qword ptr cs:xmmword_180313710+8; this
0x180009641  test    rcx, rcx
0x180009644  jz      short loc_18000964E
0x180009646  mov     dl, r13b; bool
0x180009649  call    ?Flush@CLogFile@@QEAA_N_N@Z; CLogFile::Flush(bool)
0x18000964e  mov     eax, ebx
0x180009650  jmp     loc_180009C14
0x180009655  mov     rbx, cs:?m_pMsiTransaction@CMsiTransaction@@0PEAV1@EA; CMsiTransaction * CMsiTransaction::m_pMsiTransaction
0x18000965c  test    rbx, rbx
0x18000965f  jz      loc_1800096F4
0x180009665  mov     rcx, [rbx+8]
0x180009669  mov     rax, [rcx]
0x18000966c  mov     rax, [rax+8]
0x180009670  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009675  mov     rbx, [rbx+8]
0x180009679  mov     [rsp+0E8h+var_68], rbx
0x180009681  cmp     cs:?g_dmDiagnosticMode@@3HA, r12d; int g_dmDiagnosticMode
0x180009688  jz      short loc_1800096DC
0x18000968a  lea     rcx, [rsp+0E8h+var_68]
0x180009692  call    ??BMsiString@@QEBAPEBGXZ; MsiString::operator ushort const *(void)
0x180009697  xor     edx, edx; unsigned __int16
0x180009699  mov     [rsp+0E8h+var_90], r12; void *
0x18000969e  mov     [rsp+0E8h+var_98], r12d; unsigned int
0x1800096a3  lea     rsi, aNull; "(NULL)"
0x1800096aa  mov     [rsp+0E8h+var_A0], rsi; unsigned __int16 *
0x1800096af  mov     [rsp+0E8h+var_A8], rsi; unsigned __int16 *
0x1800096b4  mov     [rsp+0E8h+var_B0], rsi; unsigned __int16 *
0x1800096b9  mov     [rsp+0E8h+var_B8], rsi; unsigned __int16 *
0x1800096be  mov     [rsp+0E8h+lpThreadId], rsi; unsigned __int16 *
0x1800096c3  mov     qword ptr [rsp+0E8h+dwCreationFlags], rax; unsigned __int16 *
0x1800096c8  lea     r9, aRunningInstall; "Running installation inside multi-packa"...
0x1800096cf  xor     r8d, r8d; int
0x1800096d2  lea     ecx, [rdx+9]; int
0x1800096d5  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1800096da  jmp     short loc_1800096E3
0x1800096dc  lea     rsi, aNull; "(NULL)"
0x1800096e3  mov     rax, [rbx]
0x1800096e6  mov     rcx, rbx
0x1800096e9  mov     rax, [rax+10h]
0x1800096ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800096f2  jmp     short loc_1800096FB
0x1800096f4  lea     rsi, aNull; "(NULL)"
0x1800096fb  mov     [rsp+0E8h+var_70], r12
0x180009700  lea     rdx, [rsp+0E8h+var_70]; void **
0x180009705  lea     rcx, aMsiexecute; "_MSIExecute"
0x18000970c  call    ?FMutexExists@@YA_NPEBGAEAPEAX@Z; FMutexExists(ushort const *,void * &)
0x180009711  test    al, al
0x180009713  jz      short loc_18000977B
0x180009715  mov     rbx, [rsp+0E8h+var_70]
0x18000971a  test    rbx, rbx
0x18000971d  jz      short loc_18000977B
0x18000971f  cmp     cs:?g_dmDiagnosticMode@@3HA, r12d; int g_dmDiagnosticMode
0x180009726  jz      short loc_180009764
0x180009728  xor     edx, edx; unsigned __int16
0x18000972a  mov     [rsp+0E8h+var_90], r12; void *
0x18000972f  mov     [rsp+0E8h+var_98], r12d; unsigned int
0x180009734  mov     [rsp+0E8h+var_A0], rsi; unsigned __int16 *
0x180009739  mov     [rsp+0E8h+var_A8], rsi; unsigned __int16 *
0x18000973e  mov     [rsp+0E8h+var_B0], rsi; unsigned __int16 *
0x180009743  mov     [rsp+0E8h+var_B8], rsi; unsigned __int16 *
0x180009748  mov     [rsp+0E8h+lpThreadId], rsi; unsigned __int16 *
0x18000974d  mov     qword ptr [rsp+0E8h+dwCreationFlags], rsi; unsigned __int16 *
0x180009752  lea     r9, aGrabbedExecuti; "Grabbed execution mutex."
0x180009759  xor     r8d, r8d; int
0x18000975c  lea     ecx, [rdx+9]; int
0x18000975f  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x180009764  mov     rdx, rbx
0x180009767  lea     rcx, [rsp+0E8h+var_88]
0x18000976c  call    ??4CSysHandle@@QEAAXPEAX@Z; CSysHandle::operator=(void *)
0x180009771  mov     rdi, [rsp+0E8h+var_88]
0x180009776  jmp     loc_180009341
0x18000977b  cmp     cs:?g_dmDiagnosticMode@@3HA, r12d; int g_dmDiagnosticMode
0x180009782  jz      loc_180009341
0x180009788  xor     edx, edx; unsigned __int16
0x18000978a  mov     [rsp+0E8h+var_90], r12; void *
0x18000978f  mov     [rsp+0E8h+var_98], r12d; unsigned int
0x180009794  mov     [rsp+0E8h+var_A0], rsi; unsigned __int16 *
0x180009799  mov     [rsp+0E8h+var_A8], rsi; unsigned __int16 *
0x18000979e  mov     [rsp+0E8h+var_B0], rsi; unsigned __int16 *
0x1800097a3  mov     [rsp+0E8h+var_B8], rsi; unsigned __int16 *
0x1800097a8  mov     [rsp+0E8h+lpThreadId], rsi; unsigned __int16 *
0x1800097ad  mov     qword ptr [rsp+0E8h+dwCreationFlags], rsi; unsigned __int16 *
0x1800097b2  lea     r9, aFailedToGrabEx; "Failed to grab execution mutex."
0x1800097b9  xor     r8d, r8d; int
0x1800097bc  lea     ecx, [rdx+9]; int
0x1800097bf  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1800097c4  jmp     loc_180009341
0x1800097c9  lea     r15, ?g_MessageContext@@3UMsiUIMessageContext@@A; MsiUIMessageContext g_MessageContext
0x1800097d0  jmp     loc_1800093A9
  ... truncated ...
```
