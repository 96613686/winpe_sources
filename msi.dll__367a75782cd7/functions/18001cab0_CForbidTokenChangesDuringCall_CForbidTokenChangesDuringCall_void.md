# CForbidTokenChangesDuringCall::CForbidTokenChangesDuringCall(void)

- ea: `0x18001cab0`
- end: `0x18001cc8f`
- name: `??0CForbidTokenChangesDuringCall@@QEAA@XZ`
- size: `479`
- prototype: `CForbidTokenChangesDuringCall *__fastcall(CForbidTokenChangesDuringCall *__hidden this)`
- caller_count: `163`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001b230`
- `0x18001bb30`
- `0x18001c420`
- `0x18001db00`
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
- `0x180151430`
- `0x180151700`

## callees

- `0x18001cab0`
- `0x180025a18`
- `0x1800a9d48`
- `0x180157094`

## import_xrefs

- `ADVAPI32!SetThreadToken` at `0x18001cc0e`
- `ADVAPI32!SetThreadToken` at `0x18001cc2e`
- `ADVAPI32!SetThreadToken` at `0x18001cc0e`
- `ADVAPI32!SetThreadToken` at `0x18001cc2e`
- `ADVAPI32!OpenThreadToken` at `0x18001cb68`
- `ADVAPI32!OpenThreadToken` at `0x18001cb68`
- `ADVAPI32!OpenProcessToken` at `0x18001cb97`
- `ADVAPI32!OpenProcessToken` at `0x18001cb97`
- `KERNEL32!CloseHandle` at `0x18001cbfe`
- `KERNEL32!CloseHandle` at `0x18001cc22`
- `KERNEL32!CloseHandle` at `0x18001cbfe`
- `KERNEL32!CloseHandle` at `0x18001cc22`
- `KERNEL32!LeaveCriticalSection` at `0x18001cb02`
- `KERNEL32!LeaveCriticalSection` at `0x18001cbe1`
- `KERNEL32!LeaveCriticalSection` at `0x18001cb02`
- `KERNEL32!LeaveCriticalSection` at `0x18001cbe1`
- `KERNEL32!GetLastError` at `0x18001cb18`
- `KERNEL32!GetLastError` at `0x18001cb18`
- `KERNEL32!EnterCriticalSection` at `0x18001cae6`
- `KERNEL32!EnterCriticalSection` at `0x18001cae6`
- `KERNEL32!GetCurrentThread` at `0x18001cb4f`
- `KERNEL32!GetCurrentThread` at `0x18001cb4f`
- `KERNEL32!GetCurrentProcess` at `0x18001cb84`
- `KERNEL32!GetCurrentProcess` at `0x18001cb84`
- `KERNEL32!TlsSetValue` at `0x18001cb2b`
- `KERNEL32!TlsSetValue` at `0x18001cb2b`
- `KERNEL32!TlsGetValue` at `0x18001cb0a`
- `KERNEL32!TlsGetValue` at `0x18001cb0a`
- `KERNEL32!TlsAlloc` at `0x18001cbc3`
- `KERNEL32!TlsAlloc` at `0x18001cbc3`

## pseudocode

```c
CForbidTokenChangesDuringCall *__fastcall CForbidTokenChangesDuringCall::CForbidTokenChangesDuringCall(
        CForbidTokenChangesDuringCall *this)
{
  int v1; // eax
  DWORD v3; // edi
  LPVOID Value; // rax
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  BOOL v8; // edi
  void *TokenHandle; // [rsp+70h] [rbp+8h] BYREF
  HANDLE hObject; // [rsp+78h] [rbp+10h] BYREF

  v1 = dword_180306D40;
  *(_QWORD *)this = 0;
  *((_BYTE *)this + 8) = 0;
  if ( v1 == -1 )
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
      v8 = IsLocalSystemToken(hObject);
      CloseHandle(hObject);
      dword_180306D40 = v8;
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
  if ( g_scServerContext != 2 && v1 == 1 )
  {
    EnterCriticalSection(&g_csImpersonationLock);
    v3 = g_dwImpersonationSlot;
    if ( g_dwImpersonationSlot == -1
      && (g_dwImpersonationSlot = TlsAlloc(), v3 = g_dwImpersonationSlot, g_dwImpersonationSlot == -1) )
    {
      LeaveCriticalSection(&g_csImpersonationLock);
    }
    else
    {
      LeaveCriticalSection(&g_csImpersonationLock);
      Value = TlsGetValue(v3);
      *(_QWORD *)this = Value;
      if ( Value || !GetLastError() )
      {
        TlsSetValue(v3, (LPVOID)0xFFFFFFFF80000000LL);
        *((_BYTE *)this + 8) = 1;
      }
    }
  }
  return this;
}

```

## disassembly

```asm
0x18001cab0  mov     [rsp+arg_10], rbx
0x18001cab5  push    rdi
0x18001cab6  sub     rsp, 60h
0x18001caba  mov     eax, cs:dword_180306D40
0x18001cac0  xor     edi, edi
0x18001cac2  mov     [rcx], rdi
0x18001cac5  mov     rbx, rcx
0x18001cac8  mov     [rcx+8], dil
0x18001cacc  cmp     eax, 0FFFFFFFFh
0x18001cacf  jz      short loc_18001CB46
0x18001cad1  cmp     cs:?g_scServerContext@@3W4scEnum@@A, 2; scEnum g_scServerContext
0x18001cad8  jz      short loc_18001CB35
0x18001cada  cmp     eax, 1
0x18001cadd  jnz     short loc_18001CB35
0x18001cadf  lea     rcx, ?g_csImpersonationLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001cae6  call    cs:__imp_EnterCriticalSection
0x18001caec  mov     edi, cs:?g_dwImpersonationSlot@@3KA; ulong g_dwImpersonationSlot
0x18001caf2  cmp     edi, 0FFFFFFFFh
0x18001caf5  jz      loc_18001CBC3
0x18001cafb  lea     rcx, ?g_csImpersonationLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001cb02  call    cs:__imp_LeaveCriticalSection
0x18001cb08  mov     ecx, edi; dwTlsIndex
0x18001cb0a  call    cs:__imp_TlsGetValue
0x18001cb10  mov     [rbx], rax
0x18001cb13  test    rax, rax
0x18001cb16  jnz     short loc_18001CB22
0x18001cb18  call    cs:__imp_GetLastError
0x18001cb1e  test    eax, eax
0x18001cb20  jnz     short loc_18001CB35
0x18001cb22  mov     rdx, 0FFFFFFFF80000000h; lpTlsValue
0x18001cb29  mov     ecx, edi; dwTlsIndex
0x18001cb2b  call    cs:__imp_TlsSetValue
0x18001cb31  mov     byte ptr [rbx+8], 1
0x18001cb35  mov     rax, rbx
0x18001cb38  mov     rbx, [rsp+68h+arg_10]
0x18001cb40  add     rsp, 60h
0x18001cb44  pop     rdi
0x18001cb45  retn
0x18001cb46  mov     [rsp+68h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x18001cb4f  call    cs:__imp_GetCurrentThread
0x18001cb55  lea     r9, [rsp+68h+TokenHandle]; TokenHandle
0x18001cb5a  mov     edx, 4; DesiredAccess
0x18001cb5f  mov     rcx, rax; ThreadHandle
0x18001cb62  mov     r8d, 1; OpenAsSelf
0x18001cb68  call    cs:__imp_OpenThreadToken
0x18001cb6e  test    eax, eax
0x18001cb70  jnz     loc_18001CC2A
0x18001cb76  mov     [rsp+68h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x18001cb7f  mov     [rsp+68h+hObject], rdi
0x18001cb84  call    cs:__imp_GetCurrentProcess
0x18001cb8a  lea     r8, [rsp+68h+hObject]; TokenHandle
0x18001cb8f  mov     edx, 8; DesiredAccess
0x18001cb94  mov     rcx, rax; ProcessHandle
0x18001cb97  call    cs:__imp_OpenProcessToken
0x18001cb9d  test    eax, eax
0x18001cb9f  jnz     short loc_18001CBEC
0x18001cba1  cmp     cs:?g_dmDiagnosticMode@@3HA, edi; int g_dmDiagnosticMode
0x18001cba7  jnz     loc_18001CC46
0x18001cbad  mov     rdx, [rsp+68h+TokenHandle]; Token
0x18001cbb2  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x18001cbb6  jnz     short loc_18001CC0C
0x18001cbb8  mov     eax, cs:dword_180306D40
0x18001cbbe  jmp     loc_18001CAD1
0x18001cbc3  call    cs:__imp_TlsAlloc
0x18001cbc9  mov     cs:?g_dwImpersonationSlot@@3KA, eax; ulong g_dwImpersonationSlot
0x18001cbcf  mov     edi, eax
0x18001cbd1  cmp     eax, 0FFFFFFFFh
0x18001cbd4  jnz     loc_18001CAFB
0x18001cbda  lea     rcx, ?g_csImpersonationLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001cbe1  call    cs:__imp_LeaveCriticalSection
0x18001cbe7  jmp     loc_18001CB35
0x18001cbec  mov     rcx, [rsp+68h+hObject]; void *
0x18001cbf1  call    ?IsLocalSystemToken@@YA_NPEAX@Z; IsLocalSystemToken(void *)
0x18001cbf6  mov     rcx, [rsp+68h+hObject]; hObject
0x18001cbfb  movzx   edi, al
0x18001cbfe  call    cs:__imp_CloseHandle
0x18001cc04  mov     cs:dword_180306D40, edi
0x18001cc0a  jmp     short loc_18001CBAD
0x18001cc0c  xor     ecx, ecx; Thread
0x18001cc0e  call    cs:__imp_SetThreadToken
0x18001cc14  test    eax, eax
0x18001cc16  jnz     short loc_18001CC1D
0x18001cc18  call    ExitProcessIfNotClient
0x18001cc1d  mov     rcx, [rsp+68h+TokenHandle]; hObject
0x18001cc22  call    cs:__imp_CloseHandle
0x18001cc28  jmp     short loc_18001CBB8
0x18001cc2a  xor     edx, edx; Token
0x18001cc2c  xor     ecx, ecx; Thread
0x18001cc2e  call    cs:__imp_SetThreadToken
0x18001cc34  test    eax, eax
0x18001cc36  jnz     loc_18001CB7F
0x18001cc3c  call    ExitProcessIfNotClient
0x18001cc41  jmp     loc_18001CB7F
0x18001cc46  mov     [rsp+68h+var_10], rdi; void *
0x18001cc4b  lea     rax, aNull; "(NULL)"
0x18001cc52  mov     [rsp+68h+var_18], edi; unsigned int
0x18001cc56  lea     r9, aCouldNotDeterm_1; "Could not determine if the process is r"...
0x18001cc5d  mov     [rsp+68h+var_20], rax; unsigned __int16 *
0x18001cc62  xor     edx, edx; unsigned __int16
0x18001cc64  mov     [rsp+68h+var_28], rax; unsigned __int16 *
0x18001cc69  xor     r8d, r8d; int
0x18001cc6c  mov     [rsp+68h+var_30], rax; unsigned __int16 *
0x18001cc71  mov     ecx, 9; int
0x18001cc76  mov     [rsp+68h+var_38], rax; unsigned __int16 *
0x18001cc7b  mov     [rsp+68h+var_40], rax; unsigned __int16 *
0x18001cc80  mov     [rsp+68h+var_48], rax; unsigned __int16 *
0x18001cc85  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18001cc8a  jmp     loc_18001CBAD
```
