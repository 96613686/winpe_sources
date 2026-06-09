# CMsiCustomActionManager::GetCustomActionInterface(bool,icacCustomActionContext)

- ea: `0x18009a2e0`
- end: `0x18009a7d8`
- name: `?GetCustomActionInterface@CMsiCustomActionManager@@AEAAPEAUIMsiCustomAction@@_NW4icacCustomActionContext@@@Z`
- size: `1272`
- prototype: ``
- caller_count: `27`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18009a08c`
- `0x18009a1f8`
- `0x180135228`
- `0x1801546e4`
- `0x1802009c4`
- `0x180201134`
- `0x1802012b0`
- `0x1802016e8`
- `0x18020177c`
- `0x1802017fc`
- `0x180201c38`
- `0x180201db0`
- `0x180201f24`
- `0x180202fd4`
- `0x180203164`
- `0x180203330`
- `0x1802034c8`
- `0x180203600`
- `0x180203748`
- `0x1802038f8`
- `0x180203aac`
- `0x180203c78`
- `0x180203df0`
- `0x180203f60`
- `0x18020412c`
- `0x1802042e8`
- `0x180204368`

## callees

- `0x180025a18`
- `0x180082fc8`
- `0x18009a2e0`
- `0x18009a7e0`
- `0x1800a9d48`
- `0x1801bfe7c`
- `0x180201b90`
- `0x18025c010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18009a599`
- `KERNEL32!CloseHandle` at `0x18009a599`
- `KERNEL32!LeaveCriticalSection` at `0x18009a6f9`
- `KERNEL32!LeaveCriticalSection` at `0x18009a7b9`
- `KERNEL32!LeaveCriticalSection` at `0x18009a6f9`
- `KERNEL32!LeaveCriticalSection` at `0x18009a7b9`
- `KERNEL32!GetLastError` at `0x18009a62e`
- `KERNEL32!GetLastError` at `0x18009a69a`
- `KERNEL32!GetLastError` at `0x18009a62e`
- `KERNEL32!GetLastError` at `0x18009a69a`
- `KERNEL32!EnterCriticalSection` at `0x18009a304`
- `KERNEL32!EnterCriticalSection` at `0x18009a304`
- `KERNEL32!WaitForSingleObject` at `0x18009a41a`
- `KERNEL32!WaitForSingleObject` at `0x18009a57c`
- `KERNEL32!WaitForSingleObject` at `0x18009a41a`
- `KERNEL32!WaitForSingleObject` at `0x18009a57c`
- `KERNEL32!SetEvent` at `0x18009a687`
- `KERNEL32!SetEvent` at `0x18009a687`
- `KERNEL32!CreateEventW` at `0x18009a5e0`
- `KERNEL32!CreateEventW` at `0x18009a5e0`
- `KERNEL32!CreateThread` at `0x18009a60f`
- `KERNEL32!CreateThread` at `0x18009a60f`
- `KERNEL32!TerminateProcess` at `0x18009a58f`
- `KERNEL32!TerminateProcess` at `0x18009a58f`

## string_xrefs

- `0x18009a3bd`: `CoCreateInstance failed on CLSID_StdGlobalInterfaceTable. Error: 0x%X`
- `0x18009a519`: `Lost connection to custom action server process. Attempting to regenerate.`
- `0x18009a4bd`: `EEUI - Attempting to join existing EEUI custom action server process.`
- `0x18009a720`: `Could not wait successfully on Remote API thread/event`
- `0x18009a639`: `CreateThread failed on while creating Custom Action Manager Thread. Error: %d`
- `0x18009a6a2`: `Could not set an event to awaken the manager thread. Error: %d`

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
0x18009a2e0  push    rbx
0x18009a2e2  push    rbp
0x18009a2e3  push    rsi
0x18009a2e4  push    rdi
0x18009a2e5  push    r12
0x18009a2e7  push    r13
0x18009a2e9  push    r14
0x18009a2eb  push    r15
0x18009a2ed  sub     rsp, 68h
0x18009a2f1  lea     r12, [rcx+0A0h]
0x18009a2f8  mov     rdi, rcx
0x18009a2fb  mov     rcx, r12; lpCriticalSection
0x18009a2fe  mov     ebp, r8d
0x18009a301  mov     r13b, dl
0x18009a304  call    cs:__imp_EnterCriticalSection
0x18009a30a  xor     r14d, r14d
0x18009a30d  mov     [rsp+0A8h+arg_0], r14
0x18009a315  cmp     ebp, 1
0x18009a318  ja      short loc_18009A364
0x18009a31a  cmp     cs:?g_scServerContext@@3W4scEnum@@A, 2; scEnum g_scServerContext
0x18009a321  jnz     short loc_18009A364
0x18009a323  lea     rcx, ?g_MessageContext@@3UMsiUIMessageContext@@A; this
0x18009a32a  call    ?GetUserToken@MsiUIMessageContext@@QEAAPEAXXZ; MsiUIMessageContext::GetUserToken(void)
0x18009a32f  mov     rbx, rax
0x18009a332  test    rax, rax
0x18009a335  jz      short loc_18009A364
0x18009a337  mov     rcx, rax; void *
0x18009a33a  call    ?IsLocalSystemToken@@YA_NPEAX@Z; IsLocalSystemToken(void *)
0x18009a33f  test    al, al
0x18009a341  jz      short loc_18009A364
0x18009a343  mov     rcx, rbx; void *
0x18009a346  call    ?TokenIsUniqueSystemToken@@YA_NPEAX@Z; TokenIsUniqueSystemToken(void *)
0x18009a34b  test    al, al
0x18009a34d  jnz     short loc_18009A364
0x18009a34f  test    ebp, ebp
0x18009a351  jnz     short loc_18009A359
0x18009a353  lea     ebp, [r14+4]
0x18009a357  jmp     short loc_18009A364
0x18009a359  cmp     ebp, 1
0x18009a35c  mov     eax, 5
0x18009a361  cmovz   ebp, eax
0x18009a364  lea     r15, [rdi+0E8h]
0x18009a36b  cmp     [r15], r14
0x18009a36e  jnz     short loc_18009A3EE
0x18009a370  mov     rax, cs:?CoCreateInstance@OLE32@@3P6AJAEBU_GUID@@PEAUIUnknown@@K0PEAPEAX@ZEA; long (*OLE32::CoCreateInstance)(_GUID const &,IUnknown *,ulong,_GUID const &,void * *)
0x18009a377  lea     r9, IID_IGlobalInterfaceTable
0x18009a37e  xor     edx, edx
0x18009a380  mov     qword ptr [rsp+0A8h+dwCreationFlags], r15
0x18009a385  lea     rcx, CLSID_StdGlobalInterfaceTable
0x18009a38c  lea     r8d, [rdx+1]
0x18009a390  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a395  mov     [rdi+110h], eax
0x18009a39b  test    eax, eax
0x18009a39d  jz      short loc_18009A3EE
0x18009a39f  cmp     cs:?g_dmDiagnosticMode@@3HA, r14d; int g_dmDiagnosticMode
0x18009a3a6  jz      loc_18009A6F6
0x18009a3ac  mov     [rsp+0A8h+var_50], r14
0x18009a3b1  lea     rbx, aNull; "(NULL)"
0x18009a3b8  mov     [rsp+0A8h+var_58], r14d
0x18009a3bd  lea     r9, aCocreateinstan_0; "CoCreateInstance failed on CLSID_StdGlo"...
0x18009a3c4  mov     [rsp+0A8h+var_60], rbx
0x18009a3c9  mov     ecx, 0Ah
0x18009a3ce  mov     [rsp+0A8h+var_68], rbx
0x18009a3d3  mov     [rsp+0A8h+var_70], rbx
0x18009a3d8  mov     [rsp+0A8h+var_78], rbx
0x18009a3dd  cdqe
0x18009a3df  mov     [rsp+0A8h+lpThreadId], rbx
0x18009a3e4  mov     qword ptr [rsp+0A8h+dwCreationFlags], rax
0x18009a3e9  jmp     loc_18009A74D
0x18009a3ee  movsxd  rsi, ebp
0x18009a3f1  cmp     [rdi+100h], r14b
0x18009a3f8  jz      short loc_18009A402
0x18009a3fa  mov     [rdi+0FCh], ebp
0x18009a400  jmp     short loc_18009A477
0x18009a402  mov     rbx, rsi
0x18009a405  add     rbx, rbx
0x18009a408  cmp     [rdi+rbx*8+8], r14d
0x18009a40d  jz      short loc_18009A477
0x18009a40f  mov     rcx, [rdi+rbx*8]; hHandle
0x18009a413  test    rcx, rcx
0x18009a416  jz      short loc_18009A477
0x18009a418  xor     edx, edx; dwMilliseconds
0x18009a41a  call    cs:__imp_WaitForSingleObject
0x18009a420  test    eax, eax
0x18009a422  jz      short loc_18009A477
0x18009a424  mov     rcx, [r15]
0x18009a427  lea     r9, [rsp+0A8h+arg_0]
0x18009a42f  mov     edx, [rdi+rbx*8+8]
0x18009a433  lea     r8, IID_IMsiCustomAction
0x18009a43a  mov     rax, [rcx]
0x18009a43d  mov     rax, [rax+28h]
0x18009a441  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a446  test    eax, eax
0x18009a448  jnz     short loc_18009A477
0x18009a44a  mov     rcx, [rsp+0A8h+arg_0]; struct IUnknown *
0x18009a452  call    ?SetMinProxyBlanketIfAnonymousImpLevel@@YAJPEAUIUnknown@@@Z; SetMinProxyBlanketIfAnonymousImpLevel(IUnknown *)
0x18009a457  test    eax, eax
0x18009a459  js      short loc_18009A477
0x18009a45b  mov     rcx, [rsp+0A8h+arg_0]
0x18009a463  mov     rax, cs:?CoIsHandlerConnected@OLE32@@3P6AHPEAUIUnknown@@@ZEA; int (*OLE32::CoIsHandlerConnected)(IUnknown *)
0x18009a46a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a46f  test    eax, eax
0x18009a471  jnz     loc_18009A7B6
0x18009a477  mov     rcx, [rsp+0A8h+arg_0]
0x18009a47f  test    rcx, rcx
0x18009a482  jz      short loc_18009A498
0x18009a484  mov     rax, [rcx]
0x18009a487  mov     rax, [rax+10h]
0x18009a48b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a490  mov     [rsp+0A8h+arg_0], r14
0x18009a498  cmp     [rdi+100h], r14b
0x18009a49f  lea     rbx, aNull; "(NULL)"
0x18009a4a6  mov     r14d, 0Ah
0x18009a4ac  jz      short loc_18009A4FC
0x18009a4ae  xor     eax, eax
0x18009a4b0  cmp     cs:?g_dmDiagnosticMode@@3HA, eax; int g_dmDiagnosticMode
0x18009a4b6  jz      short loc_18009A4F3
0x18009a4b8  mov     [rsp+0A8h+var_50], rax; void *
0x18009a4bd  lea     r9, aEeuiAttempting; "EEUI - Attempting to join existing EEUI"...
0x18009a4c4  mov     [rsp+0A8h+var_58], eax; unsigned int
0x18009a4c8  xor     edx, edx; unsigned __int16
0x18009a4ca  mov     [rsp+0A8h+var_60], rbx; unsigned __int16 *
0x18009a4cf  xor     r8d, r8d; int
0x18009a4d2  mov     [rsp+0A8h+var_68], rbx; unsigned __int16 *
0x18009a4d7  mov     ecx, r14d; int
0x18009a4da  mov     [rsp+0A8h+var_70], rbx; unsigned __int16 *
0x18009a4df  mov     [rsp+0A8h+var_78], rbx; unsigned __int16 *
0x18009a4e4  mov     [rsp+0A8h+lpThreadId], rbx; unsigned __int16 *
0x18009a4e9  mov     qword ptr [rsp+0A8h+dwCreationFlags], rbx; unsigned __int16 *
0x18009a4ee  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18009a4f3  shl     rsi, 4
0x18009a4f7  jmp     loc_18009A59F
0x18009a4fc  shl     rsi, 4
0x18009a500  cmp     dword ptr [rsi+rdi+8], 0
0x18009a505  jnz     short loc_18009A50E
0x18009a507  cmp     qword ptr [rsi+rdi], 0
0x18009a50c  jz      short loc_18009A552
0x18009a50e  cmp     cs:?g_dmDiagnosticMode@@3HA, 0; int g_dmDiagnosticMode
0x18009a515  jz      short loc_18009A552
0x18009a517  xor     edx, edx; unsigned __int16
0x18009a519  lea     r9, aLostConnection; "Lost connection to custom action server"...
0x18009a520  mov     [rsp+0A8h+var_50], rdx; void *
0x18009a525  xor     r8d, r8d; int
0x18009a528  mov     [rsp+0A8h+var_58], edx; unsigned int
0x18009a52c  mov     ecx, r14d; int
0x18009a52f  mov     [rsp+0A8h+var_60], rbx; unsigned __int16 *
0x18009a534  mov     [rsp+0A8h+var_68], rbx; unsigned __int16 *
0x18009a539  mov     [rsp+0A8h+var_70], rbx; unsigned __int16 *
0x18009a53e  mov     [rsp+0A8h+var_78], rbx; unsigned __int16 *
0x18009a543  mov     [rsp+0A8h+lpThreadId], rbx; unsigned __int16 *
0x18009a548  mov     qword ptr [rsp+0A8h+dwCreationFlags], rbx; unsigned __int16 *
0x18009a54d  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18009a552  mov     edx, [rsi+rdi+8]
0x18009a556  test    edx, edx
0x18009a558  jz      short loc_18009A571
0x18009a55a  mov     rcx, [r15]
0x18009a55d  mov     rax, [rcx]
0x18009a560  mov     rax, [rax+20h]
0x18009a564  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a569  mov     dword ptr [rsi+rdi+8], 0
0x18009a571  mov     rcx, [rsi+rdi]; hHandle
0x18009a575  test    rcx, rcx
0x18009a578  jz      short loc_18009A59F
0x18009a57a  xor     edx, edx; dwMilliseconds
0x18009a57c  call    cs:__imp_WaitForSingleObject
0x18009a582  cmp     eax, 102h
0x18009a587  jnz     short loc_18009A595
0x18009a589  mov     rcx, [rsi+rdi]; hProcess
0x18009a58d  xor     edx, edx; uExitCode
0x18009a58f  call    cs:__imp_TerminateProcess
0x18009a595  mov     rcx, [rsi+rdi]; hObject
0x18009a599  call    cs:__imp_CloseHandle
0x18009a59f  mov     qword ptr [rsi+rdi+8], 0
0x18009a5a8  mov     qword ptr [rsi+rdi], 0
0x18009a5b0  test    r13b, r13b
0x18009a5b3  jnz     short loc_18009A5C6
0x18009a5b5  xor     r13d, r13d
0x18009a5b8  cmp     [rdi+100h], r13b
0x18009a5bf  jnz     short loc_18009A5C9
0x18009a5c1  jmp     loc_18009A6F6
0x18009a5c6  xor     r13d, r13d
0x18009a5c9  cmp     [rdi+0E0h], r13
0x18009a5d0  jnz     loc_18009A67A
0x18009a5d6  xor     r9d, r9d; lpName
0x18009a5d9  xor     r8d, r8d; bInitialState
0x18009a5dc  xor     edx, edx; bManualReset
0x18009a5de  xor     ecx, ecx; lpEventAttributes
0x18009a5e0  call    cs:__imp_CreateEventW
0x18009a5e6  mov     [rdi+0D0h], rax
0x18009a5ed  mov     r9, rdi; lpParameter
0x18009a5f0  lea     r8, ?CustomActionManagerThread@CMsiCustomActionManager@@CAKPEAV1@@Z; lpStartAddress
0x18009a5f7  mov     edx, 0A000h; dwStackSize
0x18009a5fc  lea     rax, [rdi+0D8h]
0x18009a603  xor     ecx, ecx; lpThreadAttributes
0x18009a605  mov     [rsp+0A8h+lpThreadId], rax; lpThreadId
0x18009a60a  mov     [rsp+0A8h+dwCreationFlags], r13d; dwCreationFlags
0x18009a60f  call    cs:__imp_CreateThread
0x18009a615  mov     [rdi+0E0h], rax
0x18009a61c  test    rax, rax
0x18009a61f  jnz     short loc_18009A66A
0x18009a621  cmp     cs:?g_dmDiagnosticMode@@3HA, r13d; int g_dmDiagnosticMode
0x18009a628  jz      loc_18009A6F6
0x18009a62e  call    cs:__imp_GetLastError
0x18009a634  mov     [rsp+0A8h+var_50], r13
0x18009a639  lea     r9, aCreatethreadFa; "CreateThread failed on while creating C"...
0x18009a640  mov     [rsp+0A8h+var_58], r13d
0x18009a645  mov     [rsp+0A8h+var_60], rbx
0x18009a64a  mov     [rsp+0A8h+var_68], rbx
0x18009a64f  mov     [rsp+0A8h+var_70], rbx
0x18009a654  mov     [rsp+0A8h+var_78], rbx
0x18009a659  mov     eax, eax
0x18009a65b  mov     [rsp+0A8h+lpThreadId], rbx
0x18009a660  mov     qword ptr [rsp+0A8h+dwCreationFlags], rax
0x18009a665  jmp     loc_18009A74A
0x18009a66a  mov     rcx, rdi; this
0x18009a66d  call    ?MsgWaitForThreadOrEvent@CMsiCustomActionManager@@AEAA_NXZ; CMsiCustomActionManager::MsgWaitForThreadOrEvent(void)
0x18009a672  test    al, al
0x18009a674  jz      loc_18009A712
0x18009a67a  mov     rcx, [rdi+108h]; hEvent
0x18009a681  mov     [rdi+104h], ebp
0x18009a687  call    cs:__imp_SetEvent
0x18009a68d  test    eax, eax
0x18009a68f  jnz     short loc_18009A706
0x18009a691  cmp     cs:?g_dmDiagnosticMode@@3HA, r13d; int g_dmDiagnosticMode
0x18009a698  jz      short loc_18009A6DE
0x18009a69a  call    cs:__imp_GetLastError
0x18009a6a0  mov     eax, eax
0x18009a6a2  lea     r9, aCouldNotSetAnE; "Could not set an event to awaken the ma"...
0x18009a6a9  mov     [rsp+0A8h+var_50], r13; void *
0x18009a6ae  xor     edx, edx; unsigned __int16
0x18009a6b0  mov     [rsp+0A8h+var_58], r13d; unsigned int
0x18009a6b5  xor     r8d, r8d; int
0x18009a6b8  mov     [rsp+0A8h+var_60], rbx; unsigned __int16 *
0x18009a6bd  mov     ecx, r14d; int
0x18009a6c0  mov     [rsp+0A8h+var_68], rbx; unsigned __int16 *
0x18009a6c5  mov     [rsp+0A8h+var_70], rbx; unsigned __int16 *
0x18009a6ca  mov     [rsp+0A8h+var_78], rbx; unsigned __int16 *
0x18009a6cf  mov     [rsp+0A8h+lpThreadId], rbx; unsigned __int16 *
0x18009a6d4  mov     qword ptr [rsp+0A8h+dwCreationFlags], rax; unsigned __int16 *
0x18009a6d9  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18009a6de  mov     rcx, [r15]
0x18009a6e1  mov     edx, [rsi+rdi+8]
0x18009a6e5  mov     rax, [rcx]
0x18009a6e8  mov     rax, [rax+20h]
0x18009a6ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a6f1  mov     [rsi+rdi+8], r13d
0x18009a6f6  mov     rcx, r12; lpCriticalSection
0x18009a6f9  call    cs:__imp_LeaveCriticalSection
0x18009a6ff  xor     eax, eax
0x18009a701  jmp     loc_18009A7C7
0x18009a706  mov     rcx, rdi; this
0x18009a709  call    ?MsgWaitForThreadOrEvent@CMsiCustomActionManager@@AEAA_NXZ; CMsiCustomActionManager::MsgWaitForThreadOrEvent(void)
0x18009a70e  test    al, al
0x18009a710  jnz     short loc_18009A759
0x18009a712  cmp     cs:?g_dmDiagnosticMode@@3HA, r13d; int g_dmDiagnosticMode
0x18009a719  jz      short loc_18009A6F6
0x18009a71b  mov     [rsp+0A8h+var_50], r13; void *
0x18009a720  lea     r9, aCouldNotWaitSu; "Could not wait successfully on Remote A"...
0x18009a727  mov     [rsp+0A8h+var_58], r13d; unsigned int
0x18009a72c  mov     [rsp+0A8h+var_60], rbx; unsigned __int16 *
0x18009a731  mov     [rsp+0A8h+var_68], rbx; unsigned __int16 *
0x18009a736  mov     [rsp+0A8h+var_70], rbx; unsigned __int16 *
0x18009a73b  mov     [rsp+0A8h+var_78], rbx; unsigned __int16 *
0x18009a740  mov     [rsp+0A8h+lpThreadId], rbx; unsigned __int16 *
0x18009a745  mov     qword ptr [rsp+0A8h+dwCreationFlags], rbx; unsigned __int16 *
0x18009a74a  mov     ecx, r14d; int
0x18009a74d  xor     r8d, r8d; int
0x18009a750  xor     edx, edx; unsigned __int16
0x18009a752  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18009a757  jmp     short loc_18009A6F6
0x18009a759  mov     edx, [rsi+rdi+8]
0x18009a75d  test    edx, edx
0x18009a75f  jz      short loc_18009A785
0x18009a761  cmp     [rsi+rdi], r13
0x18009a765  jz      short loc_18009A785
0x18009a767  mov     rcx, [r15]
0x18009a76a  lea     r9, [rsp+0A8h+arg_0]
0x18009a772  lea     r8, IID_IMsiCustomAction
0x18009a779  mov     rax, [rcx]
0x18009a77c  mov     rax, [rax+28h]
0x18009a780  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a785  mov     rcx, [rsp+0A8h+arg_0]; struct IUnknown *
0x18009a78d  test    rcx, rcx
0x18009a790  jz      short loc_18009A7B6
0x18009a792  call    ?SetMinProxyBlanketIfAnonymousImpLevel@@YAJPEAUIUnknown@@@Z; SetMinProxyBlanketIfAnonymousImpLevel(IUnknown *)
0x18009a797  test    eax, eax
0x18009a799  jns     short loc_18009A7B6
0x18009a79b  cmp     cs:?g_dmDiagnosticMode@@3HA, r13d; int g_dmDiagnosticMode
0x18009a7a2  jz      loc_18009A6DE
0x18009a7a8  cdqe
0x18009a7aa  lea     r9, aCouldNotSetPro; "Could not set proxy blanket on CA proxy"...
0x18009a7b1  jmp     loc_18009A6A9
0x18009a7b6  mov     rcx, r12; lpCriticalSection
0x18009a7b9  call    cs:__imp_LeaveCriticalSection
0x18009a7bf  mov     rax, [rsp+0A8h+arg_0]
0x18009a7c7  add     rsp, 68h
0x18009a7cb  pop     r15
0x18009a7cd  pop     r14
0x18009a7cf  pop     r13
0x18009a7d1  pop     r12
  ... truncated ...
```
