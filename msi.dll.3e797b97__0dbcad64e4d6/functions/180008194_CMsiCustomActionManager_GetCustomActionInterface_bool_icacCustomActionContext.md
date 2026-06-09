# CMsiCustomActionManager::GetCustomActionInterface(bool,icacCustomActionContext)

- ea: `0x180008194`
- end: `0x1800086d9`
- name: `?GetCustomActionInterface@CMsiCustomActionManager@@AEAAPEAUIMsiCustomAction@@_NW4icacCustomActionContext@@@Z`
- size: `1349`
- prototype: ``
- caller_count: `27`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180007f3c`
- `0x1800080a8`
- `0x18013a628`
- `0x18015a0bc`
- `0x180209c0c`
- `0x18020a3a4`
- `0x18020a524`
- `0x18020a9a8`
- `0x18020aa3c`
- `0x18020aac0`
- `0x18020af1c`
- `0x18020b094`
- `0x18020b208`
- `0x18020c2fc`
- `0x18020c48c`
- `0x18020c658`
- `0x18020c7f0`
- `0x18020c928`
- `0x18020ca70`
- `0x18020cc24`
- `0x18020cdd8`
- `0x18020cfa4`
- `0x18020d11c`
- `0x18020d28c`
- `0x18020d458`
- `0x18020d614`
- `0x18020d694`

## callees

- `0x180008194`
- `0x1800086e0`
- `0x18000c4bc`
- `0x180045ba4`
- `0x18009bf74`
- `0x1801c82fc`
- `0x18020ae54`
- `0x180266010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180008465`
- `KERNEL32!CloseHandle` at `0x180008465`
- `KERNEL32!LeaveCriticalSection` at `0x1800085ed`
- `KERNEL32!LeaveCriticalSection` at `0x1800086b3`
- `KERNEL32!LeaveCriticalSection` at `0x1800085ed`
- `KERNEL32!LeaveCriticalSection` at `0x1800086b3`
- `KERNEL32!GetLastError` at `0x18000850c`
- `KERNEL32!GetLastError` at `0x180008588`
- `KERNEL32!GetLastError` at `0x18000850c`
- `KERNEL32!GetLastError` at `0x180008588`
- `KERNEL32!EnterCriticalSection` at `0x1800081b8`
- `KERNEL32!EnterCriticalSection` at `0x1800081b8`
- `KERNEL32!WaitForSingleObject` at `0x1800082d4`
- `KERNEL32!WaitForSingleObject` at `0x18000843c`
- `KERNEL32!WaitForSingleObject` at `0x1800082d4`
- `KERNEL32!WaitForSingleObject` at `0x18000843c`
- `KERNEL32!SetEvent` at `0x18000856b`
- `KERNEL32!SetEvent` at `0x18000856b`
- `KERNEL32!CreateEventW` at `0x1800084b2`
- `KERNEL32!CreateEventW` at `0x1800084b2`
- `KERNEL32!CreateThread` at `0x1800084e7`
- `KERNEL32!CreateThread` at `0x1800084e7`
- `KERNEL32!TerminateProcess` at `0x180008455`
- `KERNEL32!TerminateProcess` at `0x180008455`

## string_xrefs

- `0x18000837d`: `EEUI - Attempting to join existing EEUI custom action server process.`
- `0x180008277`: `CoCreateInstance failed on CLSID_StdGlobalInterfaceTable. Error: 0x%X`
- `0x18000851d`: `CreateThread failed on while creating Custom Action Manager Thread. Error: %d`
- `0x1800083d9`: `Lost connection to custom action server process. Attempting to regenerate.`
- `0x180008596`: `Could not set an event to awaken the manager thread. Error: %d`
- `0x18000861a`: `Could not wait successfully on Remote API thread/event`

## pseudocode

```c
struct IUnknown *__fastcall CMsiCustomActionManager::GetCustomActionInterface(__int64 a1, char a2, signed int a3)
{
  struct _RTL_CRITICAL_SECTION *v3; // r12
  void *UserToken; // rax
  void *v8; // rbx
  _QWORD *v9; // r15
  int v10; // eax
  void *v11; // rcx
  __int64 v12; // rsi
  void *v13; // rcx
  HANDLE Thread; // rax
  DWORD LastError; // eax
  const unsigned __int16 *v16; // r9
  void *v17; // rcx
  const unsigned __int16 *v18; // rax
  const unsigned __int16 *v19; // r9
  __int64 v21; // rdx
  const unsigned __int16 *dwCreationFlags; // [rsp+20h] [rbp-88h]
  struct IUnknown *v23; // [rsp+B0h] [rbp+8h] BYREF

  v3 = (struct _RTL_CRITICAL_SECTION *)(a1 + 160);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 160));
  v23 = 0;
  if ( (unsigned int)a3 <= 1 && g_scServerContext == 2 )
  {
    UserToken = MsiUIMessageContext::GetUserToken((MsiUIMessageContext *)&g_MessageContext);
    v8 = UserToken;
    if ( UserToken )
    {
      if ( IsLocalSystemToken(UserToken) && !TokenIsUniqueSystemToken(v8) )
      {
        if ( a3 )
          a3 = 5;
        else
          a3 = 4;
      }
    }
  }
  v9 = (_QWORD *)(a1 + 232);
  if ( !*(_QWORD *)(a1 + 232) )
  {
    v10 = ((__int64 (__fastcall *)(GUID *, _QWORD, __int64, GUID *, __int64))OLE32::CoCreateInstance)(
            &CLSID_StdGlobalInterfaceTable,
            0,
            1,
            &IID_IGlobalInterfaceTable,
            a1 + 232);
    *(_DWORD *)(a1 + 272) = v10;
    if ( v10 )
    {
      if ( g_dmDiagnosticMode )
        DebugString(
          10,
          0,
          0,
          L"CoCreateInstance failed on CLSID_StdGlobalInterfaceTable. Error: 0x%X",
          (const unsigned __int16 *)v10,
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          0,
          0);
      goto LABEL_49;
    }
  }
  if ( *(_BYTE *)(a1 + 256) )
  {
    *(_DWORD *)(a1 + 252) = a3;
  }
  else if ( *(_DWORD *)(a1 + 16LL * a3 + 8) )
  {
    v11 = *(void **)(a1 + 16LL * a3);
    if ( v11 )
    {
      if ( WaitForSingleObject(v11, 0)
        && !(*(unsigned int (__fastcall **)(_QWORD, _QWORD, GUID *, struct IUnknown **))(*(_QWORD *)*v9 + 40LL))(
              *v9,
              *(unsigned int *)(a1 + 16LL * a3 + 8),
              &IID_IMsiCustomAction,
              &v23)
        && (int)SetMinProxyBlanketIfAnonymousImpLevel(v23) >= 0
        && (unsigned int)((__int64 (__fastcall *)(struct IUnknown *))OLE32::CoIsHandlerConnected)(v23) )
      {
        goto LABEL_61;
      }
    }
  }
  if ( v23 )
  {
    ((void (__fastcall *)(struct IUnknown *))v23->lpVtbl->Release)(v23);
    v23 = 0;
  }
  if ( *(_BYTE *)(a1 + 256) )
  {
    if ( g_dmDiagnosticMode )
      DebugString(
        10,
        0,
        0,
        L"EEUI - Attempting to join existing EEUI custom action server process.",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        0,
        0);
    v12 = 16LL * a3;
  }
  else
  {
    v12 = 16LL * a3;
    if ( (*(_DWORD *)(v12 + a1 + 8) || *(_QWORD *)(v12 + a1)) && g_dmDiagnosticMode )
      DebugString(
        10,
        0,
        0,
        L"Lost connection to custom action server process. Attempting to regenerate.",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        0,
        0);
    if ( *(_DWORD *)(v12 + a1 + 8) )
    {
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v9 + 32LL))(*v9);
      *(_DWORD *)(v12 + a1 + 8) = 0;
    }
    v13 = *(void **)(v12 + a1);
    if ( v13 )
    {
      if ( WaitForSingleObject(v13, 0) == 258 )
        TerminateProcess(*(HANDLE *)(v12 + a1), 0);
      CloseHandle(*(HANDLE *)(v12 + a1));
    }
  }
  *(_QWORD *)(v12 + a1 + 8) = 0;
  *(_QWORD *)(v12 + a1) = 0;
  if ( !a2 && !*(_BYTE *)(a1 + 256) )
    goto LABEL_49;
  if ( !*(_QWORD *)(a1 + 224) )
  {
    *(_QWORD *)(a1 + 208) = CreateEventW(0, 0, 0, 0);
    Thread = CreateThread(
               0,
               0xA000u,
               CMsiCustomActionManager::CustomActionManagerThread,
               (LPVOID)a1,
               0,
               (LPDWORD)(a1 + 216));
    *(_QWORD *)(a1 + 224) = Thread;
    if ( !Thread )
    {
      if ( g_dmDiagnosticMode )
      {
        LastError = GetLastError();
        v16 = L"CreateThread failed on while creating Custom Action Manager Thread. Error: %d";
        dwCreationFlags = (const unsigned __int16 *)LastError;
LABEL_53:
        DebugString(10, 0, 0, v16, dwCreationFlags, L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", 0, 0);
        goto LABEL_49;
      }
      goto LABEL_49;
    }
    if ( !CMsiCustomActionManager::MsgWaitForThreadOrEvent((CMsiCustomActionManager *)a1) )
      goto LABEL_51;
  }
  v17 = *(void **)(a1 + 264);
  *(_DWORD *)(a1 + 260) = a3;
  if ( !SetEvent(v17) )
  {
    if ( !g_dmDiagnosticMode )
    {
LABEL_48:
      (*(void (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*v9 + 32LL))(*v9, *(unsigned int *)(v12 + a1 + 8));
      *(_DWORD *)(v12 + a1 + 8) = 0;
      goto LABEL_49;
    }
    v18 = (const unsigned __int16 *)GetLastError();
    v19 = L"Could not set an event to awaken the manager thread. Error: %d";
LABEL_47:
    DebugString(10, 0, 0, v19, v18, L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", 0, 0);
    goto LABEL_48;
  }
  if ( !CMsiCustomActionManager::MsgWaitForThreadOrEvent((CMsiCustomActionManager *)a1) )
  {
LABEL_51:
    if ( g_dmDiagnosticMode )
    {
      v16 = L"Could not wait successfully on Remote API thread/event";
      dwCreationFlags = L"(NULL)";
      goto LABEL_53;
    }
LABEL_49:
    LeaveCriticalSection(v3);
    return 0;
  }
  v21 = *(unsigned int *)(v12 + a1 + 8);
  if ( (_DWORD)v21 && *(_QWORD *)(v12 + a1) )
    (*(void (__fastcall **)(_QWORD, __int64, GUID *, struct IUnknown **))(*(_QWORD *)*v9 + 40LL))(
      *v9,
      v21,
      &IID_IMsiCustomAction,
      &v23);
  if ( v23 )
  {
    LODWORD(v18) = SetMinProxyBlanketIfAnonymousImpLevel(v23);
    if ( (int)v18 < 0 )
    {
      if ( !g_dmDiagnosticMode )
        goto LABEL_48;
      v18 = (const unsigned __int16 *)(int)v18;
      v19 = L"Could not set proxy blanket on CA proxy interface. Error: 0x%X";
      goto LABEL_47;
    }
  }
LABEL_61:
  LeaveCriticalSection(v3);
  return v23;
}

```

## disassembly

```asm
0x180008194  push    rbx
0x180008196  push    rbp
0x180008197  push    rsi
0x180008198  push    rdi
0x180008199  push    r12
0x18000819b  push    r13
0x18000819d  push    r14
0x18000819f  push    r15
0x1800081a1  sub     rsp, 68h
0x1800081a5  lea     r12, [rcx+0A0h]
0x1800081ac  mov     rdi, rcx
0x1800081af  mov     rcx, r12; lpCriticalSection
0x1800081b2  mov     ebp, r8d
0x1800081b5  mov     r13b, dl
0x1800081b8  call    cs:__imp_EnterCriticalSection
0x1800081bf  nop     dword ptr [rax+rax+00h]
0x1800081c4  xor     r14d, r14d
0x1800081c7  mov     [rsp+0A8h+arg_0], r14
0x1800081cf  cmp     ebp, 1
0x1800081d2  ja      short loc_18000821E
0x1800081d4  cmp     cs:?g_scServerContext@@3W4scEnum@@A, 2; scEnum g_scServerContext
0x1800081db  jnz     short loc_18000821E
0x1800081dd  lea     rcx, ?g_MessageContext@@3UMsiUIMessageContext@@A; this
0x1800081e4  call    ?GetUserToken@MsiUIMessageContext@@QEAAPEAXXZ; MsiUIMessageContext::GetUserToken(void)
0x1800081e9  mov     rbx, rax
0x1800081ec  test    rax, rax
0x1800081ef  jz      short loc_18000821E
0x1800081f1  mov     rcx, rax; void *
0x1800081f4  call    ?IsLocalSystemToken@@YA_NPEAX@Z; IsLocalSystemToken(void *)
0x1800081f9  test    al, al
0x1800081fb  jz      short loc_18000821E
0x1800081fd  mov     rcx, rbx; void *
0x180008200  call    ?TokenIsUniqueSystemToken@@YA_NPEAX@Z; TokenIsUniqueSystemToken(void *)
0x180008205  test    al, al
0x180008207  jnz     short loc_18000821E
0x180008209  test    ebp, ebp
0x18000820b  jnz     short loc_180008213
0x18000820d  lea     ebp, [r14+4]
0x180008211  jmp     short loc_18000821E
0x180008213  cmp     ebp, 1
0x180008216  mov     eax, 5
0x18000821b  cmovz   ebp, eax
0x18000821e  lea     r15, [rdi+0E8h]
0x180008225  cmp     [r15], r14
0x180008228  jnz     short loc_1800082A8
0x18000822a  mov     rax, cs:?CoCreateInstance@OLE32@@3P6AJAEBU_GUID@@PEAUIUnknown@@K0PEAPEAX@ZEA; long (*OLE32::CoCreateInstance)(_GUID const &,IUnknown *,ulong,_GUID const &,void * *)
0x180008231  lea     r9, IID_IGlobalInterfaceTable
0x180008238  xor     edx, edx
0x18000823a  mov     qword ptr [rsp+0A8h+dwCreationFlags], r15
0x18000823f  lea     rcx, CLSID_StdGlobalInterfaceTable
0x180008246  lea     r8d, [rdx+1]
0x18000824a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000824f  mov     [rdi+110h], eax
0x180008255  test    eax, eax
0x180008257  jz      short loc_1800082A8
0x180008259  cmp     cs:?g_dmDiagnosticMode@@3HA, r14d; int g_dmDiagnosticMode
0x180008260  jz      loc_1800085EA
0x180008266  mov     [rsp+0A8h+var_50], r14
0x18000826b  lea     rbx, aNull; "(NULL)"
0x180008272  mov     [rsp+0A8h+var_58], r14d
0x180008277  lea     r9, aCocreateinstan_0; "CoCreateInstance failed on CLSID_StdGlo"...
0x18000827e  mov     [rsp+0A8h+var_60], rbx
0x180008283  mov     ecx, 0Ah
0x180008288  mov     [rsp+0A8h+var_68], rbx
0x18000828d  mov     [rsp+0A8h+var_70], rbx
0x180008292  mov     [rsp+0A8h+var_78], rbx
0x180008297  cdqe
0x180008299  mov     [rsp+0A8h+lpThreadId], rbx
0x18000829e  mov     qword ptr [rsp+0A8h+dwCreationFlags], rax
0x1800082a3  jmp     loc_180008647
0x1800082a8  movsxd  rsi, ebp
0x1800082ab  cmp     [rdi+100h], r14b
0x1800082b2  jz      short loc_1800082BC
0x1800082b4  mov     [rdi+0FCh], ebp
0x1800082ba  jmp     short loc_180008337
0x1800082bc  mov     rbx, rsi
0x1800082bf  add     rbx, rbx
0x1800082c2  cmp     [rdi+rbx*8+8], r14d
0x1800082c7  jz      short loc_180008337
0x1800082c9  mov     rcx, [rdi+rbx*8]; hHandle
0x1800082cd  test    rcx, rcx
0x1800082d0  jz      short loc_180008337
0x1800082d2  xor     edx, edx; dwMilliseconds
0x1800082d4  call    cs:__imp_WaitForSingleObject
0x1800082db  nop     dword ptr [rax+rax+00h]
0x1800082e0  test    eax, eax
0x1800082e2  jz      short loc_180008337
0x1800082e4  mov     rcx, [r15]
0x1800082e7  lea     r9, [rsp+0A8h+arg_0]
0x1800082ef  mov     edx, [rdi+rbx*8+8]
0x1800082f3  lea     r8, IID_IMsiCustomAction
0x1800082fa  mov     rax, [rcx]
0x1800082fd  mov     rax, [rax+28h]
0x180008301  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008306  test    eax, eax
0x180008308  jnz     short loc_180008337
0x18000830a  mov     rcx, [rsp+0A8h+arg_0]; struct IUnknown *
0x180008312  call    ?SetMinProxyBlanketIfAnonymousImpLevel@@YAJPEAUIUnknown@@@Z; SetMinProxyBlanketIfAnonymousImpLevel(IUnknown *)
0x180008317  test    eax, eax
0x180008319  js      short loc_180008337
0x18000831b  mov     rcx, [rsp+0A8h+arg_0]
0x180008323  mov     rax, cs:?CoIsHandlerConnected@OLE32@@3P6AHPEAUIUnknown@@@ZEA; int (*OLE32::CoIsHandlerConnected)(IUnknown *)
0x18000832a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000832f  test    eax, eax
0x180008331  jnz     loc_1800086B0
0x180008337  mov     rcx, [rsp+0A8h+arg_0]
0x18000833f  test    rcx, rcx
0x180008342  jz      short loc_180008358
0x180008344  mov     rax, [rcx]
0x180008347  mov     rax, [rax+10h]
0x18000834b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008350  mov     [rsp+0A8h+arg_0], r14
0x180008358  cmp     [rdi+100h], r14b
0x18000835f  lea     rbx, aNull; "(NULL)"
0x180008366  mov     r14d, 0Ah
0x18000836c  jz      short loc_1800083BC
0x18000836e  xor     eax, eax
0x180008370  cmp     cs:?g_dmDiagnosticMode@@3HA, eax; int g_dmDiagnosticMode
0x180008376  jz      short loc_1800083B3
0x180008378  mov     [rsp+0A8h+var_50], rax; void *
0x18000837d  lea     r9, aEeuiAttempting; "EEUI - Attempting to join existing EEUI"...
0x180008384  mov     [rsp+0A8h+var_58], eax; unsigned int
0x180008388  xor     edx, edx; unsigned __int16
0x18000838a  mov     [rsp+0A8h+var_60], rbx; unsigned __int16 *
0x18000838f  xor     r8d, r8d; int
0x180008392  mov     [rsp+0A8h+var_68], rbx; unsigned __int16 *
0x180008397  mov     ecx, r14d; int
0x18000839a  mov     [rsp+0A8h+var_70], rbx; unsigned __int16 *
0x18000839f  mov     [rsp+0A8h+var_78], rbx; unsigned __int16 *
0x1800083a4  mov     [rsp+0A8h+lpThreadId], rbx; unsigned __int16 *
0x1800083a9  mov     qword ptr [rsp+0A8h+dwCreationFlags], rbx; unsigned __int16 *
0x1800083ae  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1800083b3  shl     rsi, 4
0x1800083b7  jmp     loc_180008471
0x1800083bc  shl     rsi, 4
0x1800083c0  cmp     dword ptr [rsi+rdi+8], 0
0x1800083c5  jnz     short loc_1800083CE
0x1800083c7  cmp     qword ptr [rsi+rdi], 0
0x1800083cc  jz      short loc_180008412
0x1800083ce  cmp     cs:?g_dmDiagnosticMode@@3HA, 0; int g_dmDiagnosticMode
0x1800083d5  jz      short loc_180008412
0x1800083d7  xor     edx, edx; unsigned __int16
0x1800083d9  lea     r9, aLostConnection; "Lost connection to custom action server"...
0x1800083e0  mov     [rsp+0A8h+var_50], rdx; void *
0x1800083e5  xor     r8d, r8d; int
0x1800083e8  mov     [rsp+0A8h+var_58], edx; unsigned int
0x1800083ec  mov     ecx, r14d; int
0x1800083ef  mov     [rsp+0A8h+var_60], rbx; unsigned __int16 *
0x1800083f4  mov     [rsp+0A8h+var_68], rbx; unsigned __int16 *
0x1800083f9  mov     [rsp+0A8h+var_70], rbx; unsigned __int16 *
0x1800083fe  mov     [rsp+0A8h+var_78], rbx; unsigned __int16 *
0x180008403  mov     [rsp+0A8h+lpThreadId], rbx; unsigned __int16 *
0x180008408  mov     qword ptr [rsp+0A8h+dwCreationFlags], rbx; unsigned __int16 *
0x18000840d  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x180008412  mov     edx, [rsi+rdi+8]
0x180008416  test    edx, edx
0x180008418  jz      short loc_180008431
0x18000841a  mov     rcx, [r15]
0x18000841d  mov     rax, [rcx]
0x180008420  mov     rax, [rax+20h]
0x180008424  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008429  mov     dword ptr [rsi+rdi+8], 0
0x180008431  mov     rcx, [rsi+rdi]; hHandle
0x180008435  test    rcx, rcx
0x180008438  jz      short loc_180008471
0x18000843a  xor     edx, edx; dwMilliseconds
0x18000843c  call    cs:__imp_WaitForSingleObject
0x180008443  nop     dword ptr [rax+rax+00h]
0x180008448  cmp     eax, 102h
0x18000844d  jnz     short loc_180008461
0x18000844f  mov     rcx, [rsi+rdi]; hProcess
0x180008453  xor     edx, edx; uExitCode
0x180008455  call    cs:__imp_TerminateProcess
0x18000845c  nop     dword ptr [rax+rax+00h]
0x180008461  mov     rcx, [rsi+rdi]; hObject
0x180008465  call    cs:__imp_CloseHandle
0x18000846c  nop     dword ptr [rax+rax+00h]
0x180008471  mov     qword ptr [rsi+rdi+8], 0
0x18000847a  mov     qword ptr [rsi+rdi], 0
0x180008482  test    r13b, r13b
0x180008485  jnz     short loc_180008498
0x180008487  xor     r13d, r13d
0x18000848a  cmp     [rdi+100h], r13b
0x180008491  jnz     short loc_18000849B
0x180008493  jmp     loc_1800085EA
0x180008498  xor     r13d, r13d
0x18000849b  cmp     [rdi+0E0h], r13
0x1800084a2  jnz     loc_18000855E
0x1800084a8  xor     r9d, r9d; lpName
0x1800084ab  xor     r8d, r8d; bInitialState
0x1800084ae  xor     edx, edx; bManualReset
0x1800084b0  xor     ecx, ecx; lpEventAttributes
0x1800084b2  call    cs:__imp_CreateEventW
0x1800084b9  nop     dword ptr [rax+rax+00h]
0x1800084be  mov     [rdi+0D0h], rax
0x1800084c5  mov     r9, rdi; lpParameter
0x1800084c8  lea     r8, ?CustomActionManagerThread@CMsiCustomActionManager@@CAKPEAV1@@Z; lpStartAddress
0x1800084cf  mov     edx, 0A000h; dwStackSize
0x1800084d4  lea     rax, [rdi+0D8h]
0x1800084db  xor     ecx, ecx; lpThreadAttributes
0x1800084dd  mov     [rsp+0A8h+lpThreadId], rax; lpThreadId
0x1800084e2  mov     [rsp+0A8h+dwCreationFlags], r13d; dwCreationFlags
0x1800084e7  call    cs:__imp_CreateThread
0x1800084ee  nop     dword ptr [rax+rax+00h]
0x1800084f3  mov     [rdi+0E0h], rax
0x1800084fa  test    rax, rax
0x1800084fd  jnz     short loc_18000854E
0x1800084ff  cmp     cs:?g_dmDiagnosticMode@@3HA, r13d; int g_dmDiagnosticMode
0x180008506  jz      loc_1800085EA
0x18000850c  call    cs:__imp_GetLastError
0x180008513  nop     dword ptr [rax+rax+00h]
0x180008518  mov     [rsp+0A8h+var_50], r13
0x18000851d  lea     r9, aCreatethreadFa; "CreateThread failed on while creating C"...
0x180008524  mov     [rsp+0A8h+var_58], r13d
0x180008529  mov     [rsp+0A8h+var_60], rbx
0x18000852e  mov     [rsp+0A8h+var_68], rbx
0x180008533  mov     [rsp+0A8h+var_70], rbx
0x180008538  mov     [rsp+0A8h+var_78], rbx
0x18000853d  mov     eax, eax
0x18000853f  mov     [rsp+0A8h+lpThreadId], rbx
0x180008544  mov     qword ptr [rsp+0A8h+dwCreationFlags], rax
0x180008549  jmp     loc_180008644
0x18000854e  mov     rcx, rdi; this
0x180008551  call    ?MsgWaitForThreadOrEvent@CMsiCustomActionManager@@AEAA_NXZ; CMsiCustomActionManager::MsgWaitForThreadOrEvent(void)
0x180008556  test    al, al
0x180008558  jz      loc_18000860C
0x18000855e  mov     rcx, [rdi+108h]; hEvent
0x180008565  mov     [rdi+104h], ebp
0x18000856b  call    cs:__imp_SetEvent
0x180008572  nop     dword ptr [rax+rax+00h]
0x180008577  test    eax, eax
0x180008579  jnz     loc_180008600
0x18000857f  cmp     cs:?g_dmDiagnosticMode@@3HA, r13d; int g_dmDiagnosticMode
0x180008586  jz      short loc_1800085D2
0x180008588  call    cs:__imp_GetLastError
0x18000858f  nop     dword ptr [rax+rax+00h]
0x180008594  mov     eax, eax
0x180008596  lea     r9, aCouldNotSetAnE; "Could not set an event to awaken the ma"...
0x18000859d  mov     [rsp+0A8h+var_50], r13; void *
0x1800085a2  xor     edx, edx; unsigned __int16
0x1800085a4  mov     [rsp+0A8h+var_58], r13d; unsigned int
0x1800085a9  xor     r8d, r8d; int
0x1800085ac  mov     [rsp+0A8h+var_60], rbx; unsigned __int16 *
0x1800085b1  mov     ecx, r14d; int
0x1800085b4  mov     [rsp+0A8h+var_68], rbx; unsigned __int16 *
0x1800085b9  mov     [rsp+0A8h+var_70], rbx; unsigned __int16 *
0x1800085be  mov     [rsp+0A8h+var_78], rbx; unsigned __int16 *
0x1800085c3  mov     [rsp+0A8h+lpThreadId], rbx; unsigned __int16 *
0x1800085c8  mov     qword ptr [rsp+0A8h+dwCreationFlags], rax; unsigned __int16 *
0x1800085cd  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1800085d2  mov     rcx, [r15]
0x1800085d5  mov     edx, [rsi+rdi+8]
0x1800085d9  mov     rax, [rcx]
0x1800085dc  mov     rax, [rax+20h]
0x1800085e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800085e5  mov     [rsi+rdi+8], r13d
0x1800085ea  mov     rcx, r12; lpCriticalSection
0x1800085ed  call    cs:__imp_LeaveCriticalSection
0x1800085f4  nop     dword ptr [rax+rax+00h]
0x1800085f9  xor     eax, eax
0x1800085fb  jmp     loc_1800086C7
0x180008600  mov     rcx, rdi; this
0x180008603  call    ?MsgWaitForThreadOrEvent@CMsiCustomActionManager@@AEAA_NXZ; CMsiCustomActionManager::MsgWaitForThreadOrEvent(void)
0x180008608  test    al, al
0x18000860a  jnz     short loc_180008653
0x18000860c  cmp     cs:?g_dmDiagnosticMode@@3HA, r13d; int g_dmDiagnosticMode
0x180008613  jz      short loc_1800085EA
0x180008615  mov     [rsp+0A8h+var_50], r13; void *
0x18000861a  lea     r9, aCouldNotWaitSu; "Could not wait successfully on Remote A"...
0x180008621  mov     [rsp+0A8h+var_58], r13d; unsigned int
0x180008626  mov     [rsp+0A8h+var_60], rbx; unsigned __int16 *
0x18000862b  mov     [rsp+0A8h+var_68], rbx; unsigned __int16 *
0x180008630  mov     [rsp+0A8h+var_70], rbx; unsigned __int16 *
0x180008635  mov     [rsp+0A8h+var_78], rbx; unsigned __int16 *
0x18000863a  mov     [rsp+0A8h+lpThreadId], rbx; unsigned __int16 *
0x18000863f  mov     qword ptr [rsp+0A8h+dwCreationFlags], rbx; unsigned __int16 *
0x180008644  mov     ecx, r14d; int
0x180008647  xor     r8d, r8d; int
0x18000864a  xor     edx, edx; unsigned __int16
0x18000864c  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x180008651  jmp     short loc_1800085EA
0x180008653  mov     edx, [rsi+rdi+8]
0x180008657  test    edx, edx
0x180008659  jz      short loc_18000867F
0x18000865b  cmp     [rsi+rdi], r13
0x18000865f  jz      short loc_18000867F
0x180008661  mov     rcx, [r15]
0x180008664  lea     r9, [rsp+0A8h+arg_0]
0x18000866c  lea     r8, IID_IMsiCustomAction
0x180008673  mov     rax, [rcx]
0x180008676  mov     rax, [rax+28h]
0x18000867a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000867f  mov     rcx, [rsp+0A8h+arg_0]; struct IUnknown *
0x180008687  test    rcx, rcx
0x18000868a  jz      short loc_1800086B0
0x18000868c  call    ?SetMinProxyBlanketIfAnonymousImpLevel@@YAJPEAUIUnknown@@@Z; SetMinProxyBlanketIfAnonymousImpLevel(IUnknown *)
0x180008691  test    eax, eax
0x180008693  jns     short loc_1800086B0
0x180008695  cmp     cs:?g_dmDiagnosticMode@@3HA, r13d; int g_dmDiagnosticMode
0x18000869c  jz      loc_1800085D2
  ... truncated ...
```
