# CForbidTokenChangesDuringCall::~CForbidTokenChangesDuringCall(void)

- ea: `0x18001d960`
- end: `0x18001daf4`
- name: `??1CForbidTokenChangesDuringCall@@QEAA@XZ`
- size: `404`
- prototype: `void __fastcall(LPVOID *this)`
- caller_count: `165`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001b230`
- `0x18001bb30`
- `0x18001c420`
- `0x18001cca0`
- `0x18001db00`
- `0x18001f190`
- `0x180031ff0`
- `0x18004aff0`
- `0x18004b2e0`
- `0x18004b450`
- `0x18004b75c`
- `0x18004c654`
- `0x18004cb90`
- `0x18004e3b0`
- `0x18004ecf0`
- `0x18004fca0`
- `0x180050710`
- `0x1800515f0`
- `0x180051740`
- `0x180051b70`
- `0x1800546a0`
- `0x180054ef0`
- `0x180055030`
- `0x180056600`
- `0x180065330`
- `0x18006c790`
- `0x180081170`
- `0x180090ed0`
- `0x1800c2bf0`
- `0x1800e2530`
- `0x1800e4fb0`
- `0x1800ea890`
- `0x180109260`
- `0x180115a80`
- `0x1801240e0`
- `0x180128480`
- `0x180129c60`
- `0x18014c880`
- `0x18014c9d0`
- `0x18014cb40`
- `0x18014ef90`
- `0x18014f1c0`
- `0x18014f4b0`
- `0x18014f940`
- `0x18014fbd0`
- `0x18014ff70`
- `0x1801502b0`
- `0x180150470`
- `0x1801510f0`
- `0x180151290`

## callees

- `0x18001d960`
- `0x180025a18`
- `0x1800a9d48`
- `0x180157094`

## import_xrefs

- `ADVAPI32!SetThreadToken` at `0x18001da75`
- `ADVAPI32!SetThreadToken` at `0x18001da95`
- `ADVAPI32!SetThreadToken` at `0x18001da75`
- `ADVAPI32!SetThreadToken` at `0x18001da95`
- `ADVAPI32!OpenThreadToken` at `0x18001d9f1`
- `ADVAPI32!OpenThreadToken` at `0x18001d9f1`
- `ADVAPI32!OpenProcessToken` at `0x18001da26`
- `ADVAPI32!OpenProcessToken` at `0x18001da26`
- `KERNEL32!CloseHandle` at `0x18001da65`
- `KERNEL32!CloseHandle` at `0x18001da89`
- `KERNEL32!CloseHandle` at `0x18001da65`
- `KERNEL32!CloseHandle` at `0x18001da89`
- `KERNEL32!LeaveCriticalSection` at `0x18001d9a7`
- `KERNEL32!LeaveCriticalSection` at `0x18001d9a7`
- `KERNEL32!EnterCriticalSection` at `0x18001d998`
- `KERNEL32!EnterCriticalSection` at `0x18001d998`
- `KERNEL32!GetCurrentThread` at `0x18001d9da`
- `KERNEL32!GetCurrentThread` at `0x18001d9da`
- `KERNEL32!GetCurrentProcess` at `0x18001da10`
- `KERNEL32!GetCurrentProcess` at `0x18001da10`
- `KERNEL32!TlsSetValue` at `0x18001d9bd`
- `KERNEL32!TlsSetValue` at `0x18001d9bd`

## pseudocode

```c
void __fastcall CForbidTokenChangesDuringCall::~CForbidTokenChangesDuringCall(LPVOID *this)
{
  int v1; // eax
  DWORD v3; // ebx
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  BOOL v6; // ebx
  void *TokenHandle; // [rsp+78h] [rbp+10h] BYREF
  HANDLE hObject; // [rsp+80h] [rbp+18h] BYREF

  v1 = dword_180306D40;
  if ( dword_180306D40 == -1 )
  {
    TokenHandle = (void *)-1LL;
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 4u, 1, &TokenHandle) )
    {
      if ( !SetThreadToken(0, 0) )
        ExitProcessIfNotClient();
    }
    else
    {
      TokenHandle = (void *)-1LL;
    }
    hObject = 0;
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 8u, &hObject) )
    {
      v6 = IsLocalSystemToken(hObject);
      CloseHandle(hObject);
      dword_180306D40 = v6;
    }
    else if ( g_dmDiagnosticMode )
    {
      DebugString(
        9,
        0,
        0,
        L"Could not determine if the process is running as local system or not.",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        L"(NULL)",
        0,
        0);
    }
    if ( TokenHandle != (void *)-1LL )
    {
      if ( !SetThreadToken(0, TokenHandle) )
        ExitProcessIfNotClient();
      CloseHandle(TokenHandle);
    }
    v1 = dword_180306D40;
  }
  if ( v1 == 1 && g_scServerContext != 2 )
  {
    EnterCriticalSection(&g_csImpersonationLock);
    v3 = g_dwImpersonationSlot;
    LeaveCriticalSection(&g_csImpersonationLock);
    if ( v3 != -1 )
    {
      if ( *((_BYTE *)this + 8) )
        TlsSetValue(v3, *this);
    }
  }
}

```

## disassembly

```asm
0x18001d960  mov     [rsp+arg_0], rbx
0x18001d965  mov     [rsp+arg_18], rbp
0x18001d96a  push    rdi
0x18001d96b  sub     rsp, 60h
0x18001d96f  mov     eax, cs:dword_180306D40
0x18001d975  or      rbp, 0FFFFFFFFFFFFFFFFh
0x18001d979  mov     rdi, rcx
0x18001d97c  cmp     eax, ebp
0x18001d97e  jz      short loc_18001D9D5
0x18001d980  cmp     eax, 1
0x18001d983  jnz     short loc_18001D9C3
0x18001d985  cmp     cs:?g_scServerContext@@3W4scEnum@@A, 2; scEnum g_scServerContext
0x18001d98c  jz      short loc_18001D9C3
0x18001d98e  lea     rbp, ?g_csImpersonationLock@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_csImpersonationLock
0x18001d995  mov     rcx, rbp; lpCriticalSection
0x18001d998  call    cs:__imp_EnterCriticalSection
0x18001d99e  mov     ebx, cs:?g_dwImpersonationSlot@@3KA; ulong g_dwImpersonationSlot
0x18001d9a4  mov     rcx, rbp; lpCriticalSection
0x18001d9a7  call    cs:__imp_LeaveCriticalSection
0x18001d9ad  cmp     ebx, 0FFFFFFFFh
0x18001d9b0  jz      short loc_18001D9C3
0x18001d9b2  cmp     byte ptr [rdi+8], 0
0x18001d9b6  jz      short loc_18001D9C3
0x18001d9b8  mov     rdx, [rdi]; lpTlsValue
0x18001d9bb  mov     ecx, ebx; dwTlsIndex
0x18001d9bd  call    cs:__imp_TlsSetValue
0x18001d9c3  lea     r11, [rsp+68h+var_8]
0x18001d9c8  mov     rbx, [r11+10h]
0x18001d9cc  mov     rbp, [r11+28h]
0x18001d9d0  mov     rsp, r11
0x18001d9d3  pop     rdi
0x18001d9d4  retn
0x18001d9d5  mov     [rsp+68h+TokenHandle], rbp
0x18001d9da  call    cs:__imp_GetCurrentThread
0x18001d9e0  mov     edx, 4; DesiredAccess
0x18001d9e5  lea     r9, [rsp+68h+TokenHandle]; TokenHandle
0x18001d9ea  mov     rcx, rax; ThreadHandle
0x18001d9ed  lea     r8d, [rdx-3]; OpenAsSelf
0x18001d9f1  call    cs:__imp_OpenThreadToken
0x18001d9f7  test    eax, eax
0x18001d9f9  jnz     loc_18001DA91
0x18001d9ff  mov     [rsp+68h+TokenHandle], rbp
0x18001da04  mov     [rsp+68h+hObject], 0
0x18001da10  call    cs:__imp_GetCurrentProcess
0x18001da16  lea     r8, [rsp+68h+hObject]; TokenHandle
0x18001da1e  mov     edx, 8; DesiredAccess
0x18001da23  mov     rcx, rax; ProcessHandle
0x18001da26  call    cs:__imp_OpenProcessToken
0x18001da2c  test    eax, eax
0x18001da2e  jnz     short loc_18001DA4D
0x18001da30  cmp     cs:?g_dmDiagnosticMode@@3HA, eax; int g_dmDiagnosticMode
0x18001da36  jnz     short loc_18001DAAD
0x18001da38  mov     rdx, [rsp+68h+TokenHandle]; Token
0x18001da3d  cmp     rdx, rbp
0x18001da40  jnz     short loc_18001DA73
0x18001da42  mov     eax, cs:dword_180306D40
0x18001da48  jmp     loc_18001D980
0x18001da4d  mov     rcx, [rsp+68h+hObject]; void *
0x18001da55  call    ?IsLocalSystemToken@@YA_NPEAX@Z; IsLocalSystemToken(void *)
0x18001da5a  mov     rcx, [rsp+68h+hObject]; hObject
0x18001da62  movzx   ebx, al
0x18001da65  call    cs:__imp_CloseHandle
0x18001da6b  mov     cs:dword_180306D40, ebx
0x18001da71  jmp     short loc_18001DA38
0x18001da73  xor     ecx, ecx; Thread
0x18001da75  call    cs:__imp_SetThreadToken
0x18001da7b  test    eax, eax
0x18001da7d  jnz     short loc_18001DA84
0x18001da7f  call    ExitProcessIfNotClient
0x18001da84  mov     rcx, [rsp+68h+TokenHandle]; hObject
0x18001da89  call    cs:__imp_CloseHandle
0x18001da8f  jmp     short loc_18001DA42
0x18001da91  xor     edx, edx; Token
0x18001da93  xor     ecx, ecx; Thread
0x18001da95  call    cs:__imp_SetThreadToken
0x18001da9b  test    eax, eax
0x18001da9d  jnz     loc_18001DA04
0x18001daa3  call    ExitProcessIfNotClient
0x18001daa8  jmp     loc_18001DA04
0x18001daad  lea     rax, aNull; "(NULL)"
0x18001dab4  xor     edx, edx; unsigned __int16
0x18001dab6  mov     [rsp+68h+var_10], rdx; void *
0x18001dabb  lea     r9, aCouldNotDeterm_1; "Could not determine if the process is r"...
0x18001dac2  mov     [rsp+68h+var_18], edx; unsigned int
0x18001dac6  xor     r8d, r8d; int
0x18001dac9  mov     [rsp+68h+var_20], rax; unsigned __int16 *
0x18001dace  mov     [rsp+68h+var_28], rax; unsigned __int16 *
0x18001dad3  lea     ecx, [rdx+9]; int
0x18001dad6  mov     [rsp+68h+var_30], rax; unsigned __int16 *
0x18001dadb  mov     [rsp+68h+var_38], rax; unsigned __int16 *
0x18001dae0  mov     [rsp+68h+var_40], rax; unsigned __int16 *
0x18001dae5  mov     [rsp+68h+var_48], rax; unsigned __int16 *
0x18001daea  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18001daef  jmp     loc_18001DA38
```
