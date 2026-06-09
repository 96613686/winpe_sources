# CForbidTokenChangesDuringCall::CForbidTokenChangesDuringCall(void)

- ea: `0x180044960`
- end: `0x180044ba1`
- name: `??0CForbidTokenChangesDuringCall@@QEAA@XZ`
- size: `577`
- prototype: `CForbidTokenChangesDuringCall *__fastcall(CForbidTokenChangesDuringCall *__hidden this)`
- caller_count: `164`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180015e80`
- `0x18002be30`
- `0x180042810`
- `0x180042b60`
- `0x1800434d0`
- `0x180043e60`
- `0x180044560`
- `0x180045c60`
- `0x1800465b0`
- `0x180047200`
- `0x1800485f0`
- `0x1800490c0`
- `0x1800493f0`
- `0x180049774`
- `0x180049cf0`
- `0x18004a530`
- `0x18004bb30`
- `0x180056140`
- `0x18005a450`
- `0x180087dc0`
- `0x18009e360`
- `0x1800b3780`
- `0x1800b6790`
- `0x1800b68f0`
- `0x1800b6d60`
- `0x1800b7080`
- `0x1800b74c0`
- `0x1800b7d84`
- `0x1800d08d0`
- `0x1800e9540`
- `0x1800eb300`
- `0x1800efa10`
- `0x1800f2fa0`
- `0x1800f6630`
- `0x180129ab0`
- `0x18012e310`
- `0x18014ffe0`
- `0x180150150`
- `0x180152b00`
- `0x180154800`
- `0x180154a50`
- `0x180154d60`
- `0x180155210`
- `0x1801554b0`
- `0x180155870`
- `0x180155bd0`
- `0x180155da0`
- `0x180156a50`
- `0x180156c00`
- `0x180156da0`

## callees

- `0x18000c4bc`
- `0x180044960`
- `0x180045ba4`
- `0x18015cbac`

## import_xrefs

- `ADVAPI32!SetThreadToken` at `0x180044b0b`
- `ADVAPI32!SetThreadToken` at `0x180044b3a`
- `ADVAPI32!SetThreadToken` at `0x180044b0b`
- `ADVAPI32!SetThreadToken` at `0x180044b3a`
- `ADVAPI32!OpenThreadToken` at `0x180044a41`
- `ADVAPI32!OpenThreadToken` at `0x180044a41`
- `ADVAPI32!OpenProcessToken` at `0x180044a7c`
- `ADVAPI32!OpenProcessToken` at `0x180044a7c`
- `KERNEL32!CloseHandle` at `0x180044af5`
- `KERNEL32!CloseHandle` at `0x180044b25`
- `KERNEL32!CloseHandle` at `0x180044af5`
- `KERNEL32!CloseHandle` at `0x180044b25`
- `KERNEL32!LeaveCriticalSection` at `0x1800449bc`
- `KERNEL32!LeaveCriticalSection` at `0x180044ad2`
- `KERNEL32!LeaveCriticalSection` at `0x1800449bc`
- `KERNEL32!LeaveCriticalSection` at `0x180044ad2`
- `KERNEL32!GetLastError` at `0x1800449de`
- `KERNEL32!GetLastError` at `0x1800449de`
- `KERNEL32!EnterCriticalSection` at `0x18004499a`
- `KERNEL32!EnterCriticalSection` at `0x18004499a`
- `KERNEL32!GetCurrentThread` at `0x180044a22`
- `KERNEL32!GetCurrentThread` at `0x180044a22`
- `KERNEL32!GetCurrentProcess` at `0x180044a63`
- `KERNEL32!GetCurrentProcess` at `0x180044a63`
- `KERNEL32!TlsSetValue` at `0x1800449f7`
- `KERNEL32!TlsSetValue` at `0x1800449f7`
- `KERNEL32!TlsGetValue` at `0x1800449ca`
- `KERNEL32!TlsGetValue` at `0x1800449ca`
- `KERNEL32!TlsAlloc` at `0x180044aae`
- `KERNEL32!TlsAlloc` at `0x180044aae`

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

  v1 = dword_180310D00;
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
      dword_180310D00 = v8;
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
    v1 = dword_180310D00;
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
0x180044960  mov     [rsp+arg_10], rbx
0x180044965  push    rdi
0x180044966  sub     rsp, 60h
0x18004496a  mov     eax, cs:dword_180310D00
0x180044970  xor     edi, edi
0x180044972  mov     [rcx], rdi
0x180044975  mov     rbx, rcx
0x180044978  mov     [rcx+8], dil
0x18004497c  cmp     eax, 0FFFFFFFFh
0x18004497f  jz      loc_180044A19
0x180044985  cmp     cs:?g_scServerContext@@3W4scEnum@@A, 2; scEnum g_scServerContext
0x18004498c  jz      short loc_180044A07
0x18004498e  cmp     eax, 1
0x180044991  jnz     short loc_180044A07
0x180044993  lea     rcx, ?g_csImpersonationLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18004499a  call    cs:__imp_EnterCriticalSection
0x1800449a1  nop     dword ptr [rax+rax+00h]
0x1800449a6  mov     edi, cs:?g_dwImpersonationSlot@@3KA; ulong g_dwImpersonationSlot
0x1800449ac  cmp     edi, 0FFFFFFFFh
0x1800449af  jz      loc_180044AAE
0x1800449b5  lea     rcx, ?g_csImpersonationLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800449bc  call    cs:__imp_LeaveCriticalSection
0x1800449c3  nop     dword ptr [rax+rax+00h]
0x1800449c8  mov     ecx, edi; dwTlsIndex
0x1800449ca  call    cs:__imp_TlsGetValue
0x1800449d1  nop     dword ptr [rax+rax+00h]
0x1800449d6  mov     [rbx], rax
0x1800449d9  test    rax, rax
0x1800449dc  jnz     short loc_1800449EE
0x1800449de  call    cs:__imp_GetLastError
0x1800449e5  nop     dword ptr [rax+rax+00h]
0x1800449ea  test    eax, eax
0x1800449ec  jnz     short loc_180044A07
0x1800449ee  mov     rdx, 0FFFFFFFF80000000h; lpTlsValue
0x1800449f5  mov     ecx, edi; dwTlsIndex
0x1800449f7  call    cs:__imp_TlsSetValue
0x1800449fe  nop     dword ptr [rax+rax+00h]
0x180044a03  mov     byte ptr [rbx+8], 1
0x180044a07  mov     rax, rbx
0x180044a0a  mov     rbx, [rsp+68h+arg_10]
0x180044a12  add     rsp, 60h
0x180044a16  pop     rdi
0x180044a17  retn
0x180044a19  mov     [rsp+68h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x180044a22  call    cs:__imp_GetCurrentThread
0x180044a29  nop     dword ptr [rax+rax+00h]
0x180044a2e  lea     r9, [rsp+68h+TokenHandle]; TokenHandle
0x180044a33  mov     edx, 4; DesiredAccess
0x180044a38  mov     rcx, rax; ThreadHandle
0x180044a3b  mov     r8d, 1; OpenAsSelf
0x180044a41  call    cs:__imp_OpenThreadToken
0x180044a48  nop     dword ptr [rax+rax+00h]
0x180044a4d  test    eax, eax
0x180044a4f  jnz     loc_180044B36
0x180044a55  mov     [rsp+68h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x180044a5e  mov     [rsp+68h+hObject], rdi
0x180044a63  call    cs:__imp_GetCurrentProcess
0x180044a6a  nop     dword ptr [rax+rax+00h]
0x180044a6f  lea     r8, [rsp+68h+hObject]; TokenHandle
0x180044a74  mov     edx, 8; DesiredAccess
0x180044a79  mov     rcx, rax; ProcessHandle
0x180044a7c  call    cs:__imp_OpenProcessToken
0x180044a83  nop     dword ptr [rax+rax+00h]
0x180044a88  test    eax, eax
0x180044a8a  jnz     short loc_180044AE3
0x180044a8c  cmp     cs:?g_dmDiagnosticMode@@3HA, edi; int g_dmDiagnosticMode
0x180044a92  jnz     loc_180044B58
0x180044a98  mov     rdx, [rsp+68h+TokenHandle]; Token
0x180044a9d  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x180044aa1  jnz     short loc_180044B09
0x180044aa3  mov     eax, cs:dword_180310D00
0x180044aa9  jmp     loc_180044985
0x180044aae  call    cs:__imp_TlsAlloc
0x180044ab5  nop     dword ptr [rax+rax+00h]
0x180044aba  mov     cs:?g_dwImpersonationSlot@@3KA, eax; ulong g_dwImpersonationSlot
0x180044ac0  mov     edi, eax
0x180044ac2  cmp     eax, 0FFFFFFFFh
0x180044ac5  jnz     loc_1800449B5
0x180044acb  lea     rcx, ?g_csImpersonationLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180044ad2  call    cs:__imp_LeaveCriticalSection
0x180044ad9  nop     dword ptr [rax+rax+00h]
0x180044ade  jmp     loc_180044A07
0x180044ae3  mov     rcx, [rsp+68h+hObject]; void *
0x180044ae8  call    ?IsLocalSystemToken@@YA_NPEAX@Z; IsLocalSystemToken(void *)
0x180044aed  mov     rcx, [rsp+68h+hObject]; hObject
0x180044af2  movzx   edi, al
0x180044af5  call    cs:__imp_CloseHandle
0x180044afc  nop     dword ptr [rax+rax+00h]
0x180044b01  mov     cs:dword_180310D00, edi
0x180044b07  jmp     short loc_180044A98
0x180044b09  xor     ecx, ecx; Thread
0x180044b0b  call    cs:__imp_SetThreadToken
0x180044b12  nop     dword ptr [rax+rax+00h]
0x180044b17  test    eax, eax
0x180044b19  jnz     short loc_180044B20
0x180044b1b  call    ExitProcessIfNotClient
0x180044b20  mov     rcx, [rsp+68h+TokenHandle]; hObject
0x180044b25  call    cs:__imp_CloseHandle
0x180044b2c  nop     dword ptr [rax+rax+00h]
0x180044b31  jmp     loc_180044AA3
0x180044b36  xor     edx, edx; Token
0x180044b38  xor     ecx, ecx; Thread
0x180044b3a  call    cs:__imp_SetThreadToken
0x180044b41  nop     dword ptr [rax+rax+00h]
0x180044b46  test    eax, eax
0x180044b48  jnz     loc_180044A5E
0x180044b4e  call    ExitProcessIfNotClient
0x180044b53  jmp     loc_180044A5E
0x180044b58  mov     [rsp+68h+var_10], rdi; void *
0x180044b5d  lea     rax, aNull; "(NULL)"
0x180044b64  mov     [rsp+68h+var_18], edi; unsigned int
0x180044b68  lea     r9, aCouldNotDeterm_1; "Could not determine if the process is r"...
0x180044b6f  mov     [rsp+68h+var_20], rax; unsigned __int16 *
0x180044b74  xor     edx, edx; unsigned __int16
0x180044b76  mov     [rsp+68h+var_28], rax; unsigned __int16 *
0x180044b7b  xor     r8d, r8d; int
0x180044b7e  mov     [rsp+68h+var_30], rax; unsigned __int16 *
0x180044b83  mov     ecx, 9; int
0x180044b88  mov     [rsp+68h+var_38], rax; unsigned __int16 *
0x180044b8d  mov     [rsp+68h+var_40], rax; unsigned __int16 *
0x180044b92  mov     [rsp+68h+var_48], rax; unsigned __int16 *
0x180044b97  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x180044b9c  jmp     loc_180044A98
```
