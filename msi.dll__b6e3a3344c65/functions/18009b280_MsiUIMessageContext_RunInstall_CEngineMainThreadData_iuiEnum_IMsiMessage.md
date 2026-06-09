# MsiUIMessageContext::RunInstall(CEngineMainThreadData &,iuiEnum,IMsiMessage *)

- ea: `0x18009b280`
- end: `0x18009bbf7`
- name: `?RunInstall@MsiUIMessageContext@@QEAAIAEAUCEngineMainThreadData@@W4iuiEnum@@PEAUIMsiMessage@@@Z`
- size: `2423`
- prototype: `unsigned int __high(struct CEngineMainThreadData *, enum iuiEnum, struct IMsiMessage *)`
- caller_count: `2`
- callee_count: `20`
- tags: `authz_impersonation, installer_update`

## callers

- `0x180099b50`
- `0x1801b08b0`

## callees

- `0x18000a150`
- `0x180025a18`
- `0x18003bccc`
- `0x18003c7e0`
- `0x18003ca18`
- `0x18007af4c`
- `0x18009b23c`
- `0x18009b280`
- `0x18009bc00`
- `0x18009de10`
- `0x1800bc65c`
- `0x180111454`
- `0x180111d80`
- `0x18013ae34`
- `0x180157544`
- `0x1801c0160`
- `0x1801ccef8`
- `0x18021896c`
- `0x18024f4dc`
- `0x18025c010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18009b932`
- `KERNEL32!LeaveCriticalSection` at `0x18009b932`
- `KERNEL32!GetExitCodeThread` at `0x18009b9a1`
- `KERNEL32!GetExitCodeThread` at `0x18009b9a1`
- `KERNEL32!GetLastError` at `0x18009b510`
- `KERNEL32!GetLastError` at `0x18009b510`
- `KERNEL32!IsDebuggerPresent` at `0x18009b8e9`
- `KERNEL32!IsDebuggerPresent` at `0x18009b8e9`
- `KERNEL32!EnterCriticalSection` at `0x18009b913`
- `KERNEL32!EnterCriticalSection` at `0x18009b913`
- `KERNEL32!SetEvent` at `0x18009b4bd`
- `KERNEL32!SetEvent` at `0x18009b4bd`
- `KERNEL32!CreateThread` at `0x18009b3fd`
- `KERNEL32!CreateThread` at `0x18009b3fd`
- `KERNEL32!TerminateThread` at `0x18009b925`
- `KERNEL32!TerminateThread` at `0x18009b925`
- `USER32!MsgWaitForMultipleObjects` at `0x18009b445`
- `USER32!MsgWaitForMultipleObjects` at `0x18009b445`
- `USER32!PeekMessageW` at `0x18009b5cb`
- `USER32!PeekMessageW` at `0x18009b5cb`
- `USER32!TranslateMessage` at `0x18009bab6`
- `USER32!TranslateMessage` at `0x18009bab6`
- `USER32!DispatchMessageW` at `0x18009bac4`
- `USER32!DispatchMessageW` at `0x18009bac4`
- `USER32!IsDialogMessageW` at `0x18009b5e9`
- `USER32!IsDialogMessageW` at `0x18009b5e9`

## string_xrefs

- `0x18009bb71`: `Internal MSI error. Installer terminated prematurely.`
- `0x18009b6bc`: `Running installation inside multi-package transaction %s`
- `0x18009bafc`: `Invalid event trigger in wait for engine thread`
- `0x18009b6f9`: `_MSIExecute`

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
  struct tagMSG Msg; // [rsp+90h] [rbp-58h] BYREF
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
    if ( *((_QWORD *)&xmmword_180309760 + 1) )
      CLogFile::Flush(*((CLogFile **)&xmmword_180309760 + 1), 1);
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
      qword_1803096E8 = a4;
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
                (LPDWORD)&qword_1803096A8 + 1);
    if ( hThread )
    {
      v11 = 0;
      v28 = 0;
      HIDWORD(qword_180309704) = 0;
      while ( 1 )
      {
        v12 = MsgWaitForMultipleObjects(2u, &pHandles, 0, g_iUIWaitTick, 0x1CFFu);
        if ( v12 == -1 )
          break;
        switch ( v12 )
        {
          case 0x102u:
            if ( !qword_1803096E8
              && (unsigned int)MsiUIMessageContext::ProcessMessage(&g_MessageContext, 167772160, &off_180305DB0) == 2 )
            {
              LOBYTE(word_1803096D4) = 1;
            }
            if ( (_DWORD)qword_180309704 )
            {
              LODWORD(qword_180309704) = 0;
              v11 = 0;
              v28 = 0;
            }
            else if ( !HIDWORD(qword_1803096FC) )
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
                  if ( *((_QWORD *)&xmmword_180309760 + 1) )
                    CLogFile::Flush(*((CLogFile **)&xmmword_180309760 + 1), 1);
                  CSysHandle::operator=(&v27, -1);
                  MsiUIMessageContext::Terminate((MsiUIMessageContext *)&g_MessageContext, 1, 1, 0);
                  CSysHandle::~CSysHandle((CSysHandle *)&v27);
                  return 1603;
                }
                v11 = 0;
                v28 = 0;
                HIDWORD(qword_180309704) = 0;
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
                if ( !g_scServerContext && qword_180309730 )
                {
                  CMsiSQMSession::RecordDWORD(qword_180309730, 0xE27u, ExitCode);
                  v22 = ExitCode;
                }
                MsiUIMessageContext::Terminate((MsiUIMessageContext *)&g_MessageContext, 0, v22 != 0, 0);
                v23 = ExitCode;
                CSysHandle::~CSysHandle((CSysHandle *)&v27);
                return v23;
            }
            LODWORD(ExitCode) = v22;
LABEL_83:
            if ( *((_QWORD *)&xmmword_180309760 + 1) )
            {
              CLogFile::Flush(*((CLogFile **)&xmmword_180309760 + 1), 1);
              v22 = ExitCode;
            }
            if ( !g_scServerContext && qword_180309730 )
              CMsiSQMSession::RecordDWORD(qword_180309730, 0xE27u, v22);
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
            HIDWORD(qword_180309704) = 0;
            if ( dword_180309680 == 0x80000000 )
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
              dword_1803096D0 = -2147483647;
              dword_1803096D0 = MsiUIMessageContext::ProcessMessage(
                                  &g_MessageContext,
                                  (unsigned int)dword_180309680,
                                  qword_180309678);
              dword_180309680 = 0x80000000;
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
      if ( *((_QWORD *)&xmmword_180309760 + 1) )
        CLogFile::Flush(*((CLogFile **)&xmmword_180309760 + 1), 1);
      if ( v9 != -1 )
        MsiCloseSysHandle(v9);
      return 0;
    }
    else
    {
      if ( !g_scServerContext && qword_180309730 )
        CMsiSQMSession::RecordDWORD(qword_180309730, 0xE27u, 0x65Fu);
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
0x18009b280  mov     rax, rsp
0x18009b283  mov     [rax+10h], rbx
0x18009b287  mov     [rax+18h], rsi
0x18009b28b  mov     [rax+8], rcx
0x18009b28f  push    rdi
0x18009b290  push    r12
0x18009b292  push    r13
0x18009b294  push    r14
0x18009b296  push    r15
0x18009b298  sub     rsp, 0C0h
0x18009b29f  mov     r15, r9
0x18009b2a2  mov     ebx, r8d
0x18009b2a5  mov     r14, rdx
0x18009b2a8  lea     rdi, ?g_MessageContext@@3UMsiUIMessageContext@@A; MsiUIMessageContext g_MessageContext
0x18009b2af  mov     [rsp+0E8h+var_60], rdi
0x18009b2b7  xor     r12d, r12d
0x18009b2ba  mov     [rax-78h], r12d
0x18009b2be  lea     r13d, [r12+1]
0x18009b2c3  mov     [rax-7Ch], r13d
0x18009b2c7  mov     ecx, ebx
0x18009b2c9  and     ecx, 0FFFF23FFh
0x18009b2cf  jnz     loc_18009B5F9
0x18009b2d5  lea     eax, [rcx+5]
0x18009b2d8  mov     ecx, r12d
0x18009b2db  cmp     cs:?g_scServerContext@@3W4scEnum@@A, 2; scEnum g_scServerContext
0x18009b2e2  setz    cl
0x18009b2e5  lea     rdx, [rsp+0E8h+var_78]
0x18009b2ea  mov     [rsp+0E8h+var_B8], rdx
0x18009b2ef  lea     rdx, [rsp+0E8h+var_7C]
0x18009b2f4  mov     [rsp+0E8h+lpThreadId], rdx
0x18009b2f9  mov     [rsp+0E8h+dwCreationFlags], eax
0x18009b2fd  mov     r9, [r14+18h]
0x18009b301  mov     r8, [r14+10h]
0x18009b305  mov     rdx, [r14+8]
0x18009b309  mov     rax, cs:?TermSrvMSIOkToRun@TSAPPCMP@@3P6AJHPEBG00KPEAHPEAI@ZEA; long (*TSAPPCMP::TermSrvMSIOkToRun)(int,ushort const *,ushort const *,ushort const *,ulong,int *,uint *)
0x18009b310  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009b315  test    eax, eax
0x18009b317  jz      loc_18009B547
0x18009b31d  mov     byte ptr [rsp+0E8h+dwCreationFlags], r12b
0x18009b322  mov     r9, r14
0x18009b325  mov     r8d, ebx
0x18009b328  xor     edx, edx
0x18009b32a  mov     rcx, rdi
0x18009b32d  call    ?Initialize@MsiUIMessageContext@@QEAAI_NW4iuiEnum@@PEBUCEngineMainThreadData@@_N@Z; MsiUIMessageContext::Initialize(bool,iuiEnum,CEngineMainThreadData const *,bool)
0x18009b332  mov     ebx, eax
0x18009b334  test    eax, eax
0x18009b336  jnz     loc_18009B62E
0x18009b33c  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18009b340  mov     [rsp+0E8h+var_88], rdi
0x18009b345  cmp     cs:?g_scServerContext@@3W4scEnum@@A, 2; scEnum g_scServerContext
0x18009b34c  jz      loc_18009B649
0x18009b352  lea     rsi, aNull; "(NULL)"
0x18009b359  test    r15, r15
0x18009b35c  jz      loc_18009B7BD
0x18009b362  mov     cs:qword_1803096E8, r15
0x18009b369  mov     rax, [r15]
0x18009b36c  mov     rcx, r15
0x18009b36f  mov     rax, [rax+8]
0x18009b373  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009b378  mov     ecx, r13d; unsigned int
0x18009b37b  call    ?CreateRecord@@YAAEAVIMsiRecord@@I@Z; CreateRecord(uint)
0x18009b380  mov     rbx, rax
0x18009b383  mov     rax, [rax]
0x18009b386  mov     r8d, 6
0x18009b38c  mov     edx, r13d
0x18009b38f  mov     rcx, rbx
0x18009b392  mov     rax, [rax+68h]
0x18009b396  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009b39b  mov     r8, rbx
0x18009b39e  mov     edx, 18000000h
0x18009b3a3  lea     r15, ?g_MessageContext@@3UMsiUIMessageContext@@A; MsiUIMessageContext g_MessageContext
0x18009b3aa  mov     rcx, r15
0x18009b3ad  call    ?Invoke@MsiUIMessageContext@@QEAA?AW4imsEnum@@W4imtEnum@@PEAVIMsiRecord@@@Z; MsiUIMessageContext::Invoke(imtEnum,IMsiRecord *)
0x18009b3b2  mov     rax, [rbx]
0x18009b3b5  mov     rcx, rbx
0x18009b3b8  mov     rax, [rax+10h]
0x18009b3bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009b3c1  mov     ecx, 54h ; 'T'; int
0x18009b3c6  call    ?GetTestFlag@@YA_NH@Z; GetTestFlag(int)
0x18009b3cb  test    al, al
0x18009b3cd  jnz     loc_18009B7C9
0x18009b3d3  mov     dword ptr [rsp+0E8h+ExitCode], r12d
0x18009b3db  lea     rax, qword_1803096A8+4
0x18009b3e2  mov     [rsp+0E8h+lpThreadId], rax; lpThreadId
0x18009b3e7  mov     [rsp+0E8h+dwCreationFlags], r12d; dwCreationFlags
0x18009b3ec  mov     r9, r14; lpParameter
0x18009b3ef  lea     r8, ?MainEngineThread@MsiUIMessageContext@@CAKPEAX@Z; lpStartAddress
0x18009b3f6  mov     edx, 0A000h; dwStackSize
0x18009b3fb  xor     ecx, ecx; lpThreadAttributes
0x18009b3fd  call    cs:__imp_CreateThread
0x18009b403  mov     qword ptr cs:hThread, rax
0x18009b40a  test    rax, rax
0x18009b40d  jz      loc_18009B819
0x18009b413  mov     ebx, r12d
0x18009b416  mov     [rsp+0E8h+var_80], ebx
0x18009b41a  mov     dword ptr cs:qword_180309704+4, r12d
0x18009b421  lea     r14, aNull_0; "(NULL)"
0x18009b428  mov     [rsp+0E8h+dwCreationFlags], 1CFFh; dwWakeMask
0x18009b430  mov     r9d, cs:?g_iUIWaitTick@@3HA; dwMilliseconds
0x18009b437  xor     r8d, r8d; fWaitAll
0x18009b43a  lea     rdx, pHandles; pHandles
0x18009b441  lea     ecx, [r8+2]; nCount
0x18009b445  call    cs:__imp_MsgWaitForMultipleObjects
0x18009b44b  cmp     eax, 0FFFFFFFFh
0x18009b44e  jz      loc_18009B510
0x18009b454  cmp     eax, 102h
0x18009b459  jz      short loc_18009B4C8
0x18009b45b  cmp     eax, r13d
0x18009b45e  jz      loc_18009B992
0x18009b464  cmp     eax, 2
0x18009b467  jz      loc_18009B59B
0x18009b46d  mov     ebx, r12d
0x18009b470  mov     [rsp+0E8h+var_80], ebx
0x18009b474  mov     dword ptr cs:qword_180309704+4, r12d
0x18009b47b  mov     edx, cs:dword_180309680
0x18009b481  cmp     edx, 80000000h
0x18009b487  jz      loc_18009BACF
0x18009b48d  mov     cs:dword_1803096D0, 80000001h
0x18009b497  mov     r8, cs:qword_180309678
0x18009b49e  mov     rcx, r15
0x18009b4a1  call    ?ProcessMessage@MsiUIMessageContext@@AEAA?AW4imsEnum@@W4imtEnum@@PEAVIMsiRecord@@@Z; MsiUIMessageContext::ProcessMessage(imtEnum,IMsiRecord *)
0x18009b4a6  mov     cs:dword_1803096D0, eax
0x18009b4ac  mov     cs:dword_180309680, 80000000h
0x18009b4b6  mov     rcx, qword ptr cs:hThread+8; hEvent
0x18009b4bd  call    cs:__imp_SetEvent
0x18009b4c3  jmp     loc_18009B428
0x18009b4c8  cmp     cs:qword_1803096E8, r12
0x18009b4cf  jz      short loc_18009B4EE
0x18009b4d1  cmp     dword ptr cs:qword_180309704, r12d
0x18009b4d8  jz      loc_18009B88B
0x18009b4de  mov     dword ptr cs:qword_180309704, r12d
0x18009b4e5  mov     ebx, r12d
0x18009b4e8  mov     [rsp+0E8h+var_80], ebx
0x18009b4ec  jmp     short loc_18009B4C3
0x18009b4ee  lea     r8, off_180305DB0
0x18009b4f5  mov     edx, 0A000000h
0x18009b4fa  mov     rcx, r15
0x18009b4fd  call    ?ProcessMessage@MsiUIMessageContext@@AEAA?AW4imsEnum@@W4imtEnum@@PEAVIMsiRecord@@@Z; MsiUIMessageContext::ProcessMessage(imtEnum,IMsiRecord *)
0x18009b502  cmp     eax, 2
0x18009b505  jnz     short loc_18009B4D1
0x18009b507  mov     byte ptr cs:word_1803096D4, r13b
0x18009b50e  jmp     short loc_18009B4D1
0x18009b510  call    cs:__imp_GetLastError
0x18009b516  mov     dword ptr [rsp+0E8h+ExitCode], eax
0x18009b51d  cmp     cs:?g_dmDiagnosticMode@@3HA, r12d; int g_dmDiagnosticMode
0x18009b524  jnz     short loc_18009B55B
0x18009b526  mov     rcx, qword ptr cs:xmmword_180309760+8; this
0x18009b52d  test    rcx, rcx
0x18009b530  jnz     loc_18009B871
0x18009b536  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18009b53a  jnz     loc_18009B87E
0x18009b540  xor     eax, eax
0x18009b542  jmp     loc_18009BBDA
0x18009b547  cmp     [rsp+0E8h+var_7C], r12d
0x18009b54c  jnz     loc_18009B31D
0x18009b552  mov     eax, [rsp+0E8h+var_78]
0x18009b556  jmp     loc_18009BBDA
0x18009b55b  mov     eax, eax
0x18009b55d  xor     edx, edx; unsigned __int16
0x18009b55f  mov     [rsp+0E8h+var_90], r12; void *
0x18009b564  mov     [rsp+0E8h+var_98], r12d; unsigned int
0x18009b569  mov     [rsp+0E8h+var_A0], rsi; unsigned __int16 *
0x18009b56e  mov     [rsp+0E8h+var_A8], rsi; unsigned __int16 *
0x18009b573  mov     [rsp+0E8h+var_B0], rsi; unsigned __int16 *
0x18009b578  mov     [rsp+0E8h+var_B8], rsi; unsigned __int16 *
0x18009b57d  mov     [rsp+0E8h+lpThreadId], rsi; unsigned __int16 *
0x18009b582  mov     qword ptr [rsp+0E8h+dwCreationFlags], rax; unsigned __int16 *
0x18009b587  lea     r9, aWaitFailedInRu; "Wait Failed in RunEngine. GetLastError "...
0x18009b58e  xor     r8d, r8d; int
0x18009b591  lea     ecx, [rdx+9]; int
0x18009b594  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18009b599  jmp     short loc_18009B526
0x18009b59b  xorps   xmm0, xmm0
0x18009b59e  movups  xmmword ptr [rsp+0E8h+Msg.hwnd], xmm0
0x18009b5a6  movups  xmmword ptr [rsp+0E8h+Msg.wParam], xmm0
0x18009b5ae  movups  xmmword ptr [rsp+0E8h+Msg.time], xmm0
0x18009b5b6  mov     [rsp+0E8h+dwCreationFlags], r13d; wRemoveMsg
0x18009b5bb  xor     r9d, r9d; wMsgFilterMax
0x18009b5be  xor     r8d, r8d; wMsgFilterMin
0x18009b5c1  xor     edx, edx; hWnd
0x18009b5c3  lea     rcx, [rsp+0E8h+Msg]; lpMsg
0x18009b5cb  call    cs:__imp_PeekMessageW
0x18009b5d1  test    eax, eax
0x18009b5d3  jz      loc_18009B4C3
0x18009b5d9  call    ?GetCurrentWindow@MsiUIMessageContext@@QEAAPEAUHWND__@@XZ; MsiUIMessageContext::GetCurrentWindow(void)
0x18009b5de  mov     rcx, rax; hDlg
0x18009b5e1  lea     rdx, [rsp+0E8h+Msg]; lpMsg
0x18009b5e9  call    cs:__imp_IsDialogMessageW
0x18009b5ef  test    eax, eax
0x18009b5f1  jz      loc_18009BAAE
0x18009b5f7  jmp     short loc_18009B5B6
0x18009b5f9  sub     ecx, r13d
0x18009b5fc  jz      short loc_18009B624
0x18009b5fe  sub     ecx, r13d
0x18009b601  jz      short loc_18009B61A
0x18009b603  cmp     ecx, r13d
0x18009b606  jz      short loc_18009B610
0x18009b608  mov     eax, r13d
0x18009b60b  jmp     loc_18009B2D8
0x18009b610  mov     eax, 2
0x18009b615  jmp     loc_18009B2D8
0x18009b61a  mov     eax, 3
0x18009b61f  jmp     loc_18009B2D8
0x18009b624  mov     eax, 4
0x18009b629  jmp     loc_18009B2D8
0x18009b62e  mov     rcx, qword ptr cs:xmmword_180309760+8; this
0x18009b635  test    rcx, rcx
0x18009b638  jz      short loc_18009B642
0x18009b63a  mov     dl, r13b; bool
0x18009b63d  call    ?Flush@CLogFile@@QEAA_N_N@Z; CLogFile::Flush(bool)
0x18009b642  mov     eax, ebx
0x18009b644  jmp     loc_18009BBDA
0x18009b649  mov     rbx, cs:?m_pMsiTransaction@CMsiTransaction@@0PEAV1@EA; CMsiTransaction * CMsiTransaction::m_pMsiTransaction
0x18009b650  test    rbx, rbx
0x18009b653  jz      loc_18009B6E8
0x18009b659  mov     rcx, [rbx+8]
0x18009b65d  mov     rax, [rcx]
0x18009b660  mov     rax, [rax+8]
0x18009b664  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009b669  mov     rbx, [rbx+8]
0x18009b66d  mov     [rsp+0E8h+var_68], rbx
0x18009b675  cmp     cs:?g_dmDiagnosticMode@@3HA, r12d; int g_dmDiagnosticMode
0x18009b67c  jz      short loc_18009B6D0
0x18009b67e  lea     rcx, [rsp+0E8h+var_68]
0x18009b686  call    ??BMsiString@@QEBAPEBGXZ; MsiString::operator ushort const *(void)
0x18009b68b  xor     edx, edx; unsigned __int16
0x18009b68d  mov     [rsp+0E8h+var_90], r12; void *
0x18009b692  mov     [rsp+0E8h+var_98], r12d; unsigned int
0x18009b697  lea     rsi, aNull; "(NULL)"
0x18009b69e  mov     [rsp+0E8h+var_A0], rsi; unsigned __int16 *
0x18009b6a3  mov     [rsp+0E8h+var_A8], rsi; unsigned __int16 *
0x18009b6a8  mov     [rsp+0E8h+var_B0], rsi; unsigned __int16 *
0x18009b6ad  mov     [rsp+0E8h+var_B8], rsi; unsigned __int16 *
0x18009b6b2  mov     [rsp+0E8h+lpThreadId], rsi; unsigned __int16 *
0x18009b6b7  mov     qword ptr [rsp+0E8h+dwCreationFlags], rax; unsigned __int16 *
0x18009b6bc  lea     r9, aRunningInstall; "Running installation inside multi-packa"...
0x18009b6c3  xor     r8d, r8d; int
0x18009b6c6  lea     ecx, [rdx+9]; int
0x18009b6c9  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18009b6ce  jmp     short loc_18009B6D7
0x18009b6d0  lea     rsi, aNull; "(NULL)"
0x18009b6d7  mov     rax, [rbx]
0x18009b6da  mov     rcx, rbx
0x18009b6dd  mov     rax, [rax+10h]
0x18009b6e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009b6e6  jmp     short loc_18009B6EF
0x18009b6e8  lea     rsi, aNull; "(NULL)"
0x18009b6ef  mov     [rsp+0E8h+var_70], r12
0x18009b6f4  lea     rdx, [rsp+0E8h+var_70]; void **
0x18009b6f9  lea     rcx, aMsiexecute; "_MSIExecute"
0x18009b700  call    ?FMutexExists@@YA_NPEBGAEAPEAX@Z; FMutexExists(ushort const *,void * &)
0x18009b705  test    al, al
0x18009b707  jz      short loc_18009B76F
0x18009b709  mov     rbx, [rsp+0E8h+var_70]
0x18009b70e  test    rbx, rbx
0x18009b711  jz      short loc_18009B76F
0x18009b713  cmp     cs:?g_dmDiagnosticMode@@3HA, r12d; int g_dmDiagnosticMode
0x18009b71a  jz      short loc_18009B758
0x18009b71c  xor     edx, edx; unsigned __int16
0x18009b71e  mov     [rsp+0E8h+var_90], r12; void *
0x18009b723  mov     [rsp+0E8h+var_98], r12d; unsigned int
0x18009b728  mov     [rsp+0E8h+var_A0], rsi; unsigned __int16 *
0x18009b72d  mov     [rsp+0E8h+var_A8], rsi; unsigned __int16 *
0x18009b732  mov     [rsp+0E8h+var_B0], rsi; unsigned __int16 *
0x18009b737  mov     [rsp+0E8h+var_B8], rsi; unsigned __int16 *
0x18009b73c  mov     [rsp+0E8h+lpThreadId], rsi; unsigned __int16 *
0x18009b741  mov     qword ptr [rsp+0E8h+dwCreationFlags], rsi; unsigned __int16 *
0x18009b746  lea     r9, aGrabbedExecuti; "Grabbed execution mutex."
0x18009b74d  xor     r8d, r8d; int
0x18009b750  lea     ecx, [rdx+9]; int
0x18009b753  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18009b758  mov     rdx, rbx
0x18009b75b  lea     rcx, [rsp+0E8h+var_88]
0x18009b760  call    ??4CSysHandle@@QEAAXPEAX@Z; CSysHandle::operator=(void *)
0x18009b765  mov     rdi, [rsp+0E8h+var_88]
0x18009b76a  jmp     loc_18009B359
0x18009b76f  cmp     cs:?g_dmDiagnosticMode@@3HA, r12d; int g_dmDiagnosticMode
0x18009b776  jz      loc_18009B359
0x18009b77c  xor     edx, edx; unsigned __int16
0x18009b77e  mov     [rsp+0E8h+var_90], r12; void *
0x18009b783  mov     [rsp+0E8h+var_98], r12d; unsigned int
0x18009b788  mov     [rsp+0E8h+var_A0], rsi; unsigned __int16 *
0x18009b78d  mov     [rsp+0E8h+var_A8], rsi; unsigned __int16 *
0x18009b792  mov     [rsp+0E8h+var_B0], rsi; unsigned __int16 *
0x18009b797  mov     [rsp+0E8h+var_B8], rsi; unsigned __int16 *
0x18009b79c  mov     [rsp+0E8h+lpThreadId], rsi; unsigned __int16 *
0x18009b7a1  mov     qword ptr [rsp+0E8h+dwCreationFlags], rsi; unsigned __int16 *
0x18009b7a6  lea     r9, aFailedToGrabEx; "Failed to grab execution mutex."
0x18009b7ad  xor     r8d, r8d; int
0x18009b7b0  lea     ecx, [rdx+9]; int
0x18009b7b3  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18009b7b8  jmp     loc_18009B359
0x18009b7bd  lea     r15, ?g_MessageContext@@3UMsiUIMessageContext@@A; MsiUIMessageContext g_MessageContext
0x18009b7c4  jmp     loc_18009B3C1
0x18009b7c9  mov     rax, [r14+28h]
0x18009b7cd  mov     [rsp+0E8h+var_B8], rax
0x18009b7d2  mov     eax, [r14+20h]
0x18009b7d6  mov     dword ptr [rsp+0E8h+lpThreadId], eax
0x18009b7da  mov     qword ptr [rsp+0E8h+dwCreationFlags], r12
0x18009b7df  mov     r9, [r14+18h]
  ... truncated ...
```
