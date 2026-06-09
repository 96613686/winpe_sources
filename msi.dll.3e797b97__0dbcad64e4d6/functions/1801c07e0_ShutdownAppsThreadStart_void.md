# ShutdownAppsThreadStart(void *)

- ea: `0x1801c07e0`
- end: `0x1801c08e3`
- name: `?ShutdownAppsThreadStart@@YAKPEAX@Z`
- size: `259`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation`

## callees

- `0x180013d64`
- `0x180014f18`
- `0x1801c07e0`
- `0x1801c7d98`
- `0x180266010`

## import_xrefs

- `ADVAPI32!SetThreadToken` at `0x1801c086e`
- `ADVAPI32!SetThreadToken` at `0x1801c086e`
- `KERNEL32!ExitThread` at `0x1801c08d6`
- `KERNEL32!ExitThread` at `0x1801c08d6`
- `KERNEL32!CloseHandle` at `0x1801c0896`
- `KERNEL32!CloseHandle` at `0x1801c0896`
- `KERNEL32!LeaveCriticalSection` at `0x1801c081b`
- `KERNEL32!LeaveCriticalSection` at `0x1801c08c8`
- `KERNEL32!LeaveCriticalSection` at `0x1801c081b`
- `KERNEL32!LeaveCriticalSection` at `0x1801c08c8`
- `KERNEL32!GetLastError` at `0x1801c087e`
- `KERNEL32!GetLastError` at `0x1801c087e`
- `KERNEL32!EnterCriticalSection` at `0x1801c07ff`
- `KERNEL32!EnterCriticalSection` at `0x1801c08a9`
- `KERNEL32!EnterCriticalSection` at `0x1801c07ff`
- `KERNEL32!EnterCriticalSection` at `0x1801c08a9`

## pseudocode

```c
void __fastcall __noreturn ShutdownAppsThreadStart(_DWORD *Parameter)
{
  unsigned int v2; // edi
  unsigned int v3; // ebx
  bool v4; // si
  DWORD LastError; // ebx
  HANDLE Token; // [rsp+40h] [rbp+8h] BYREF
  char v7; // [rsp+48h] [rbp+10h] BYREF

  Token = 0;
  EnterCriticalSection(&CRestartManagerWrapper::m_csAccessControl);
  v2 = Parameter[2];
  v3 = Parameter[199];
  LeaveCriticalSection(&CRestartManagerWrapper::m_csAccessControl);
  v4 = ImpersonateElevAdmin(&Token);
  CImpersonate::CImpersonate((CImpersonate *)&v7, !v4);
  LastError = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))RSTRTMGR::RmShutdown)(v2, v3, 0);
  CImpersonate::~CImpersonate((CImpersonate *)&v7);
  if ( v4 && !SetThreadToken(0, Token) )
    LastError = GetLastError();
  if ( Token )
    CloseHandle(Token);
  EnterCriticalSection(&CRestartManagerWrapper::m_csAccessControl);
  Parameter[22] = (LastError == 0) + 1;
  LeaveCriticalSection(&CRestartManagerWrapper::m_csAccessControl);
  ExitThread(LastError);
}

```

## disassembly

```asm
0x1801c07e0  mov     [rsp+arg_10], rbx
0x1801c07e5  push    rbp
0x1801c07e6  push    rsi
0x1801c07e7  push    rdi
0x1801c07e8  sub     rsp, 20h
0x1801c07ec  mov     rbp, rcx
0x1801c07ef  mov     [rsp+38h+Token], 0
0x1801c07f8  lea     rcx, ?m_csAccessControl@CRestartManagerWrapper@@1U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1801c07ff  call    cs:__imp_EnterCriticalSection
0x1801c0806  nop     dword ptr [rax+rax+00h]
0x1801c080b  mov     edi, [rbp+8]
0x1801c080e  lea     rcx, ?m_csAccessControl@CRestartManagerWrapper@@1U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1801c0815  mov     ebx, [rbp+31Ch]
0x1801c081b  call    cs:__imp_LeaveCriticalSection
0x1801c0822  nop     dword ptr [rax+rax+00h]
0x1801c0827  lea     rcx, [rsp+38h+Token]; TokenHandle
0x1801c082c  call    ?ImpersonateElevAdmin@@YA_NPEAPEAX@Z; ImpersonateElevAdmin(void * *)
0x1801c0831  mov     dl, al
0x1801c0833  lea     rcx, [rsp+38h+arg_8]; this
0x1801c0838  xor     dl, 1; bool
0x1801c083b  mov     sil, al
0x1801c083e  call    ??0CImpersonate@@QEAA@_N@Z; CImpersonate::CImpersonate(bool)
0x1801c0843  mov     rax, cs:?RmShutdown@RSTRTMGR@@3P6AKKKP6AXI@Z@ZEA; ulong (*RSTRTMGR::RmShutdown)(ulong,ulong,void (*)(uint))
0x1801c084a  xor     r8d, r8d
0x1801c084d  mov     edx, ebx
0x1801c084f  mov     ecx, edi
0x1801c0851  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c0856  lea     rcx, [rsp+38h+arg_8]; this
0x1801c085b  mov     ebx, eax
0x1801c085d  call    ??1CImpersonate@@QEAA@XZ; CImpersonate::~CImpersonate(void)
0x1801c0862  test    sil, sil
0x1801c0865  jz      short loc_1801C088C
0x1801c0867  mov     rdx, [rsp+38h+Token]; Token
0x1801c086c  xor     ecx, ecx; Thread
0x1801c086e  call    cs:__imp_SetThreadToken
0x1801c0875  nop     dword ptr [rax+rax+00h]
0x1801c087a  test    eax, eax
0x1801c087c  jnz     short loc_1801C088C
0x1801c087e  call    cs:__imp_GetLastError
0x1801c0885  nop     dword ptr [rax+rax+00h]
0x1801c088a  mov     ebx, eax
0x1801c088c  mov     rcx, [rsp+38h+Token]; hObject
0x1801c0891  test    rcx, rcx
0x1801c0894  jz      short loc_1801C08A2
0x1801c0896  call    cs:__imp_CloseHandle
0x1801c089d  nop     dword ptr [rax+rax+00h]
0x1801c08a2  lea     rcx, ?m_csAccessControl@CRestartManagerWrapper@@1U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1801c08a9  call    cs:__imp_EnterCriticalSection
0x1801c08b0  nop     dword ptr [rax+rax+00h]
0x1801c08b5  xor     eax, eax
0x1801c08b7  lea     rcx, ?m_csAccessControl@CRestartManagerWrapper@@1U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1801c08be  test    ebx, ebx
0x1801c08c0  setz    al
0x1801c08c3  inc     eax
0x1801c08c5  mov     [rbp+58h], eax
0x1801c08c8  call    cs:__imp_LeaveCriticalSection
0x1801c08cf  nop     dword ptr [rax+rax+00h]
0x1801c08d4  mov     ecx, ebx; dwExitCode
0x1801c08d6  call    cs:__imp_ExitThread
```
