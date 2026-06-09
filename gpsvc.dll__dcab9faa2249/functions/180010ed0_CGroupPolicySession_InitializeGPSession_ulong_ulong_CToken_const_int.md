# CGroupPolicySession::InitializeGPSession(ulong,ulong,CToken const &,int)

- ea: `0x180010ed0`
- end: `0x1800111d3`
- name: `?InitializeGPSession@CGroupPolicySession@@QEAAKKKAEBVCToken@@H@Z`
- size: `771`
- prototype: `unsigned int __usercall@<eax>(CGroupPolicySession *__hidden this@<rcx>, unsigned int@<edx>, unsigned int@<r8d>, const struct CToken *@<r9>, int)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18000fa40`
- `0x180010760`

## callees

- `0x180010ed0`
- `0x18001c850`
- `0x180023b6c`
- `0x180033430`
- `0x180049700`
- `0x180075ec0`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180010f1e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180010f6b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180010f8a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001114f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180010f1e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180010f6b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180010f8a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001114f`
- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x18001108f`
- `api-ms-win-core-synch-l1-1-0!CreateWaitableTimerExW` at `0x18001108f`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x1800110dd`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x1800110dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010f30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001101e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010f30`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001101e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180010fe5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180010fe5`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180011010`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180011010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CGroupPolicySession::InitializeGPSession(
        HANDLE *this,
        int a2,
        int a3,
        const struct CToken *a4,
        int a5)
{
  HANDLE EventW; // rax
  unsigned int LastError; // edi
  HANDLE v11; // rax
  HANDLE v12; // rax
  HANDLE v13; // rdi
  HANDLE CurrentProcess; // rax
  HANDLE WaitableTimer; // rax
  HANDLE v16; // rax
  HANDLE TargetHandle; // [rsp+40h] [rbp-48h] BYREF
  LARGE_INTEGER DueTime; // [rsp+48h] [rbp-40h] BYREF
  CGroupPolicySession *v19; // [rsp+50h] [rbp-38h]
  HANDLE hSourceHandle; // [rsp+90h] [rbp+8h] BYREF
  int v21; // [rsp+A0h] [rbp+18h] BYREF

  v21 = a3;
  v19 = (CGroupPolicySession *)this;
  if ( this )
    (*(void (__fastcall **)(HANDLE *))*this)(this);
  if ( !this[19] )
  {
    LastError = 14;
    goto LABEL_6;
  }
  EventW = CreateEventW(0, 1, 0, 0);
  this[35] = EventW;
  if ( !EventW
    || (v11 = CreateEventW(0, 1, 0, 0), (this[36] = v11) == 0)
    || (v12 = CreateEventW(0, 1, 0, 0), (this[27] = v12) == 0) )
  {
LABEL_5:
    LastError = GetLastError();
    goto LABEL_6;
  }
  hSourceHandle = 0;
  LastError = (*(__int64 (__fastcall **)(const struct CToken *, HANDLE *))(*(_QWORD *)a4 + 8LL))(a4, &hSourceHandle);
  if ( LastError )
    goto LABEL_6;
  v13 = hSourceHandle;
  TargetHandle = 0;
  this[24] = 0;
  if ( !v13 )
    goto LABEL_23;
  CurrentProcess = GetCurrentProcess();
  if ( CurrentProcess && DuplicateHandle(CurrentProcess, v13, CurrentProcess, &TargetHandle, 0, 0, 2u) )
  {
    this[24] = TargetHandle;
LABEL_23:
    *((_DWORD *)this + 50) = 1;
    goto LABEL_14;
  }
  LastError = GetLastError();
  if ( LastError )
    goto LABEL_6;
LABEL_14:
  v21 = 0;
  LastError = (*((__int64 (__fastcall **)(char *, int *))this[23] + 2))((char *)this + 184, &v21);
  if ( LastError )
    goto LABEL_6;
  if ( v21 )
  {
    v16 = CreateEventW(0, 1, 0, 0);
    this[37] = v16;
    if ( !v16 )
      goto LABEL_5;
  }
  LastError = CGroupPolicySession::CreateAndSecurePolicyApplicationStateRegistry((CGroupPolicySession *)this);
  if ( LastError )
    goto LABEL_6;
  WaitableTimer = CreateWaitableTimerExW(0, 0, 1u, 0x1F0003u);
  this[39] = WaitableTimer;
  if ( !WaitableTimer )
    goto LABEL_5;
  DueTime.QuadPart = -36000000000LL;
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(4u, L"CGroupPolicySession::InitializeGPSession ::(dwTimeOut: %ld)", 3600000);
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(4u, L"CGroupPolicySession::InitializeGPSession ::(dwTimeOut: %ld)", 3600000);
    }
  }
  if ( !SetWaitableTimer(this[39], &DueTime, 0, 0, 0, 0) )
    goto LABEL_5;
  LastError = CGroupPolicySession::InitializeSessionSecurityDescriptor((CGroupPolicySession *)this);
  if ( !LastError )
  {
    CGroupPolicySession::SetForegroundPolicyApplicationState((CGroupPolicySession *)this, v21, a5);
    CGroupPolicySession::AddSessionIdAndUpdateTargetId((struct _RTL_CRITICAL_SECTION **)this, a4, a2);
  }
LABEL_6:
  (*((void (__fastcall **)(HANDLE *))*this + 1))(this);
  return LastError;
}

```

## disassembly

```asm
0x180010ed0  mov     [rsp+arg_8], rbx
0x180010ed5  mov     [rsp+arg_10], r8d
0x180010eda  push    rbp
0x180010edb  push    rsi
0x180010edc  push    rdi
0x180010edd  push    r14
0x180010edf  push    r15
0x180010ee1  sub     rsp, 60h
0x180010ee5  mov     rsi, r9
0x180010ee8  mov     ebp, edx
0x180010eea  mov     rbx, rcx
0x180010eed  mov     [rsp+88h+var_38], rcx
0x180010ef2  test    rcx, rcx
0x180010ef5  jz      short loc_180010F03
0x180010ef7  mov     rax, [rcx]
0x180010efa  mov     rax, [rax]
0x180010efd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f02  nop
0x180010f03  cmp     qword ptr [rbx+98h], 0
0x180010f0b  jz      loc_18001116A
0x180010f11  xor     r9d, r9d; lpName
0x180010f14  xor     r8d, r8d; bInitialState
0x180010f17  mov     edx, 1; bManualReset
0x180010f1c  xor     ecx, ecx; lpEventAttributes
0x180010f1e  call    cs:__imp_CreateEventW
0x180010f24  mov     [rbx+118h], rax
0x180010f2b  test    rax, rax
0x180010f2e  jnz     short loc_180010F5E
0x180010f30  call    cs:__imp_GetLastError
0x180010f36  mov     edi, eax
0x180010f38  mov     rax, [rbx]
0x180010f3b  mov     rcx, rbx
0x180010f3e  mov     rax, [rax+8]
0x180010f42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f47  nop
0x180010f48  mov     eax, edi
0x180010f4a  mov     rbx, [rsp+88h+arg_8]
0x180010f52  add     rsp, 60h
0x180010f56  pop     r15
0x180010f58  pop     r14
0x180010f5a  pop     rdi
0x180010f5b  pop     rsi
0x180010f5c  pop     rbp
0x180010f5d  retn
0x180010f5e  xor     r9d, r9d; lpName
0x180010f61  xor     r8d, r8d; bInitialState
0x180010f64  mov     edx, 1; bManualReset
0x180010f69  xor     ecx, ecx; lpEventAttributes
0x180010f6b  call    cs:__imp_CreateEventW
0x180010f71  mov     [rbx+120h], rax
0x180010f78  test    rax, rax
0x180010f7b  jz      short loc_180010F30
0x180010f7d  xor     r9d, r9d; lpName
0x180010f80  xor     r8d, r8d; bInitialState
0x180010f83  mov     edx, 1; bManualReset
0x180010f88  xor     ecx, ecx; lpEventAttributes
0x180010f8a  call    cs:__imp_CreateEventW
0x180010f90  mov     [rbx+0D8h], rax
0x180010f97  test    rax, rax
0x180010f9a  jz      short loc_180010F30
0x180010f9c  xor     r15d, r15d
0x180010f9f  mov     [rsp+88h+hSourceHandle], r15
0x180010fa7  mov     rax, [rsi]
0x180010faa  lea     rdx, [rsp+88h+hSourceHandle]
0x180010fb2  mov     rcx, rsi
0x180010fb5  mov     rax, [rax+8]
0x180010fb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010fbe  mov     edi, eax
0x180010fc0  test    eax, eax
0x180010fc2  jnz     loc_180010F38
0x180010fc8  mov     rdi, [rsp+88h+hSourceHandle]
0x180010fd0  mov     [rsp+88h+TargetHandle], r15
0x180010fd5  mov     [rbx+0C0h], r15
0x180010fdc  test    rdi, rdi
0x180010fdf  jz      loc_180011133
0x180010fe5  call    cs:__imp_GetCurrentProcess
0x180010feb  test    rax, rax
0x180010fee  jz      short loc_18001101E
0x180010ff0  mov     [rsp+88h+dwOptions], 2; dwOptions
0x180010ff8  mov     [rsp+88h+bInheritHandle], r15d; bInheritHandle
0x180010ffd  mov     [rsp+88h+dwDesiredAccess], r15d; dwDesiredAccess
0x180011002  lea     r9, [rsp+88h+TargetHandle]; lpTargetHandle
0x180011007  mov     r8, rax; hTargetProcessHandle
0x18001100a  mov     rdx, rdi; hSourceHandle
0x18001100d  mov     rcx, rax; hSourceProcessHandle
0x180011010  call    cs:__imp_DuplicateHandle
0x180011016  test    eax, eax
0x180011018  jnz     loc_180011127
0x18001101e  call    cs:__imp_GetLastError
0x180011024  mov     edi, eax
0x180011026  test    eax, eax
0x180011028  jnz     loc_180010F38
0x18001102e  mov     [rsp+88h+arg_10], r15d
0x180011036  mov     rax, [rbx+0B8h]
0x18001103d  lea     rdx, [rsp+88h+arg_10]
0x180011045  lea     rcx, [rbx+0B8h]
0x18001104c  mov     rax, [rax+10h]
0x180011050  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011055  mov     edi, eax
0x180011057  test    eax, eax
0x180011059  jnz     loc_180010F38
0x18001105f  cmp     [rsp+88h+arg_10], r15d
0x180011067  jnz     loc_180011142
0x18001106d  mov     rcx, rbx; this
0x180011070  call    ?CreateAndSecurePolicyApplicationStateRegistry@CGroupPolicySession@@AEAAKXZ; CGroupPolicySession::CreateAndSecurePolicyApplicationStateRegistry(void)
0x180011075  mov     edi, eax
0x180011077  test    eax, eax
0x180011079  jnz     loc_180010F38
0x18001107f  xor     edx, edx; lpTimerName
0x180011081  xor     ecx, ecx; lpTimerAttributes
0x180011083  mov     r9d, 1F0003h; dwDesiredAccess
0x180011089  mov     r8d, 1; dwFlags
0x18001108f  call    cs:__imp_CreateWaitableTimerExW
0x180011095  mov     [rbx+138h], rax
0x18001109c  test    rax, rax
0x18001109f  jz      loc_180010F30
0x1800110a5  mov     rax, 0FFFFFFF79E3B9800h
0x1800110af  mov     qword ptr [rsp+88h+DueTime], rax
0x1800110b4  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x1800110bb  jnz     loc_180011174
0x1800110c1  mov     [rsp+88h+bInheritHandle], r15d; fResume
0x1800110c6  mov     qword ptr [rsp+88h+dwDesiredAccess], r15; lpArgToCompletionRoutine
0x1800110cb  xor     r9d, r9d; pfnCompletionRoutine
0x1800110ce  xor     r8d, r8d; lPeriod
0x1800110d1  lea     rdx, [rsp+88h+DueTime]; lpDueTime
0x1800110d6  mov     rcx, [rbx+138h]; hTimer
0x1800110dd  call    cs:__imp_SetWaitableTimer
0x1800110e3  test    eax, eax
0x1800110e5  jz      loc_180010F30
0x1800110eb  mov     rcx, rbx; this
0x1800110ee  call    ?InitializeSessionSecurityDescriptor@CGroupPolicySession@@AEAAKXZ; CGroupPolicySession::InitializeSessionSecurityDescriptor(void)
0x1800110f3  mov     edi, eax
0x1800110f5  test    eax, eax
0x1800110f7  jnz     loc_180010F38
0x1800110fd  mov     r8d, [rsp+88h+arg_20]; int
0x180011105  mov     edx, [rsp+88h+arg_10]; int
0x18001110c  mov     rcx, rbx; this
0x18001110f  call    ?SetForegroundPolicyApplicationState@CGroupPolicySession@@AEAAXHH@Z; CGroupPolicySession::SetForegroundPolicyApplicationState(int,int)
0x180011114  mov     r8d, ebp; unsigned int
0x180011117  mov     rdx, rsi; struct CToken *
0x18001111a  mov     rcx, rbx; this
0x18001111d  call    ?AddSessionIdAndUpdateTargetId@CGroupPolicySession@@QEAAKAEBVCToken@@K@Z; CGroupPolicySession::AddSessionIdAndUpdateTargetId(CToken const &,ulong)
0x180011122  jmp     loc_180010F38
0x180011127  mov     rax, [rsp+88h+TargetHandle]
0x18001112c  mov     [rbx+0C0h], rax
0x180011133  mov     dword ptr [rbx+0C8h], 1
0x18001113d  jmp     loc_18001102E
0x180011142  xor     r9d, r9d; lpName
0x180011145  xor     r8d, r8d; bInitialState
0x180011148  mov     edx, 1; bManualReset
0x18001114d  xor     ecx, ecx; lpEventAttributes
0x18001114f  call    cs:__imp_CreateEventW
0x180011155  mov     [rbx+128h], rax
0x18001115c  test    rax, rax
0x18001115f  jnz     loc_18001106D
0x180011165  jmp     loc_180010F30
0x18001116a  mov     edi, 0Eh
0x18001116f  jmp     loc_180010F38
0x180011174  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18001117b  test    rax, rax
0x18001117e  jz      short loc_18001119C
0x180011180  mov     r8d, 36EE80h
0x180011186  lea     rdx, aCgrouppolicyse_67; "CGroupPolicySession::InitializeGPSessio"...
0x18001118d  mov     ecx, 4
0x180011192  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011197  jmp     loc_1800110C1
0x18001119c  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x1800111a3  jz      loc_1800110C1
0x1800111a9  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800111b0  jz      loc_1800110C1
0x1800111b6  mov     r8d, 36EE80h
0x1800111bc  lea     rdx, aCgrouppolicyse_67; "CGroupPolicySession::InitializeGPSessio"...
0x1800111c3  mov     ecx, 4; unsigned int
0x1800111c8  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800111cd  jmp     loc_1800110C1
```
