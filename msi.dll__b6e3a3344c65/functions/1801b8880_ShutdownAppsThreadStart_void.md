# ShutdownAppsThreadStart(void *)

- ea: `0x1801b8880`
- end: `0x1801b8953`
- name: `?ShutdownAppsThreadStart@@YAKPEAX@Z`
- size: `211`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation`

## callees

- `0x180064b4c`
- `0x180064f18`
- `0x1801b8880`
- `0x1801bf96c`
- `0x18025c010`

## import_xrefs

- `ADVAPI32!SetThreadToken` at `0x1801b8902`
- `ADVAPI32!SetThreadToken` at `0x1801b8902`
- `KERNEL32!ExitThread` at `0x1801b894c`
- `KERNEL32!ExitThread` at `0x1801b894c`
- `KERNEL32!CloseHandle` at `0x1801b891e`
- `KERNEL32!CloseHandle` at `0x1801b891e`
- `KERNEL32!LeaveCriticalSection` at `0x1801b88b5`
- `KERNEL32!LeaveCriticalSection` at `0x1801b8944`
- `KERNEL32!LeaveCriticalSection` at `0x1801b88b5`
- `KERNEL32!LeaveCriticalSection` at `0x1801b8944`
- `KERNEL32!GetLastError` at `0x1801b890c`
- `KERNEL32!GetLastError` at `0x1801b890c`
- `KERNEL32!EnterCriticalSection` at `0x1801b889f`
- `KERNEL32!EnterCriticalSection` at `0x1801b892b`
- `KERNEL32!EnterCriticalSection` at `0x1801b889f`
- `KERNEL32!EnterCriticalSection` at `0x1801b892b`

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
0x1801b8880  mov     [rsp+arg_10], rbx
0x1801b8885  push    rbp
0x1801b8886  push    rsi
0x1801b8887  push    rdi
0x1801b8888  sub     rsp, 20h
0x1801b888c  mov     rbp, rcx
0x1801b888f  mov     [rsp+38h+Token], 0
0x1801b8898  lea     rcx, ?m_csAccessControl@CRestartManagerWrapper@@1U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1801b889f  call    cs:__imp_EnterCriticalSection
0x1801b88a5  mov     edi, [rbp+8]
0x1801b88a8  lea     rcx, ?m_csAccessControl@CRestartManagerWrapper@@1U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1801b88af  mov     ebx, [rbp+31Ch]
0x1801b88b5  call    cs:__imp_LeaveCriticalSection
0x1801b88bb  lea     rcx, [rsp+38h+Token]; TokenHandle
0x1801b88c0  call    ?ImpersonateElevAdmin@@YA_NPEAPEAX@Z; ImpersonateElevAdmin(void * *)
0x1801b88c5  mov     dl, al
0x1801b88c7  lea     rcx, [rsp+38h+arg_8]; this
0x1801b88cc  xor     dl, 1; bool
0x1801b88cf  mov     sil, al
0x1801b88d2  call    ??0CImpersonate@@QEAA@_N@Z; CImpersonate::CImpersonate(bool)
0x1801b88d7  mov     rax, cs:?RmShutdown@RSTRTMGR@@3P6AKKKP6AXI@Z@ZEA; ulong (*RSTRTMGR::RmShutdown)(ulong,ulong,void (*)(uint))
0x1801b88de  xor     r8d, r8d
0x1801b88e1  mov     edx, ebx
0x1801b88e3  mov     ecx, edi
0x1801b88e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b88ea  lea     rcx, [rsp+38h+arg_8]; this
0x1801b88ef  mov     ebx, eax
0x1801b88f1  call    ??1CImpersonate@@QEAA@XZ; CImpersonate::~CImpersonate(void)
0x1801b88f6  test    sil, sil
0x1801b88f9  jz      short loc_1801B8914
0x1801b88fb  mov     rdx, [rsp+38h+Token]; Token
0x1801b8900  xor     ecx, ecx; Thread
0x1801b8902  call    cs:__imp_SetThreadToken
0x1801b8908  test    eax, eax
0x1801b890a  jnz     short loc_1801B8914
0x1801b890c  call    cs:__imp_GetLastError
0x1801b8912  mov     ebx, eax
0x1801b8914  mov     rcx, [rsp+38h+Token]; hObject
0x1801b8919  test    rcx, rcx
0x1801b891c  jz      short loc_1801B8924
0x1801b891e  call    cs:__imp_CloseHandle
0x1801b8924  lea     rcx, ?m_csAccessControl@CRestartManagerWrapper@@1U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1801b892b  call    cs:__imp_EnterCriticalSection
0x1801b8931  xor     eax, eax
0x1801b8933  lea     rcx, ?m_csAccessControl@CRestartManagerWrapper@@1U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1801b893a  test    ebx, ebx
0x1801b893c  setz    al
0x1801b893f  inc     eax
0x1801b8941  mov     [rbp+58h], eax
0x1801b8944  call    cs:__imp_LeaveCriticalSection
0x1801b894a  mov     ecx, ebx; dwExitCode
0x1801b894c  call    cs:__imp_ExitThread
```
