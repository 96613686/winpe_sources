# CResetImpersonationInfo::CResetImpersonationInfo(void)

- ea: `0x1800296ac`
- end: `0x180029789`
- name: `??0CResetImpersonationInfo@@QEAA@XZ`
- size: `221`
- prototype: `CResetImpersonationInfo *__fastcall(CResetImpersonationInfo *__hidden this)`
- caller_count: `82`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18001bd70`
- `0x180029270`
- `0x180029340`
- `0x180029400`
- `0x1800294e0`
- `0x180029790`
- `0x1800298e0`
- `0x180029c90`
- `0x18002a180`
- `0x18002a250`
- `0x18002a3e0`
- `0x18002a850`
- `0x18002a9e0`
- `0x18002aaa0`
- `0x18002ade0`
- `0x18002b200`
- `0x18002b2d0`
- `0x18002b560`
- `0x18002b7b0`
- `0x18011c310`
- `0x18012f7f0`
- `0x1801319b0`
- `0x180139af0`
- `0x18014a710`
- `0x18014a8b0`
- `0x18015b480`
- `0x18015eea0`
- `0x18015f1d0`
- `0x180161830`
- `0x180162090`
- `0x180162770`
- `0x180163260`
- `0x1801640f0`
- `0x180164340`
- `0x180164d40`
- `0x180165420`
- `0x1801655b0`
- `0x180168a60`
- `0x18016a240`
- `0x18016c2b0`
- `0x1801743a0`
- `0x1801765b0`
- `0x1801766f0`
- `0x1801768e0`
- `0x180176a10`
- `0x180176af0`
- `0x180176bb0`
- `0x180176c90`
- `0x180176d70`
- `0x180176e40`

## callees

- `0x1800296ac`
- `0x18015cbac`

## import_xrefs

- `ADVAPI32!SetThreadToken` at `0x180029764`
- `ADVAPI32!SetThreadToken` at `0x180029764`
- `ADVAPI32!OpenThreadToken` at `0x18002970b`
- `ADVAPI32!OpenThreadToken` at `0x18002970b`
- `KERNEL32!LeaveCriticalSection` at `0x18002971e`
- `KERNEL32!LeaveCriticalSection` at `0x18002971e`
- `KERNEL32!EnterCriticalSection` at `0x1800296d8`
- `KERNEL32!EnterCriticalSection` at `0x1800296d8`
- `KERNEL32!GetCurrentThread` at `0x1800296ef`
- `KERNEL32!GetCurrentThread` at `0x1800296ef`
- `KERNEL32!TlsSetValue` at `0x180029750`
- `KERNEL32!TlsSetValue` at `0x180029750`
- `KERNEL32!TlsGetValue` at `0x180029739`
- `KERNEL32!TlsGetValue` at `0x180029739`

## pseudocode

```c
CResetImpersonationInfo *__fastcall CResetImpersonationInfo::CResetImpersonationInfo(CResetImpersonationInfo *this)
{
  bool v1; // zf
  HANDLE CurrentThread; // rax
  LPVOID Value; // rax
  DWORD v6; // ecx

  v1 = g_scServerContext == 2;
  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  if ( v1 )
  {
    EnterCriticalSection(&g_csImpersonationLock);
    if ( g_dwImpersonationSlot != -1 )
    {
      Value = TlsGetValue(g_dwImpersonationSlot);
      v6 = g_dwImpersonationSlot;
      *(_QWORD *)this = Value;
      if ( !TlsSetValue(v6, 0) )
        ExitProcessIfNotClient();
      if ( !SetThreadToken(0, 0) )
        ExitProcessIfNotClient();
    }
    CurrentThread = GetCurrentThread();
    OpenThreadToken(CurrentThread, 4u, 1, (PHANDLE)this + 1);
    LeaveCriticalSection(&g_csImpersonationLock);
  }
  return this;
}

```

## disassembly

```asm
0x1800296ac  mov     [rsp+arg_0], rbx
0x1800296b1  push    rdi
0x1800296b2  sub     rsp, 20h
0x1800296b6  cmp     cs:?g_scServerContext@@3W4scEnum@@A, 2; scEnum g_scServerContext
0x1800296bd  mov     rbx, rcx
0x1800296c0  mov     qword ptr [rcx], 0
0x1800296c7  mov     qword ptr [rcx+8], 0
0x1800296cf  jnz     short loc_18002972A
0x1800296d1  lea     rcx, ?g_csImpersonationLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800296d8  call    cs:__imp_EnterCriticalSection
0x1800296df  nop     dword ptr [rax+rax+00h]
0x1800296e4  mov     ecx, cs:?g_dwImpersonationSlot@@3KA; dwTlsIndex
0x1800296ea  cmp     ecx, 0FFFFFFFFh
0x1800296ed  jnz     short loc_180029739
0x1800296ef  call    cs:__imp_GetCurrentThread
0x1800296f6  nop     dword ptr [rax+rax+00h]
0x1800296fb  mov     edx, 4; DesiredAccess
0x180029700  lea     r9, [rbx+8]; TokenHandle
0x180029704  mov     rcx, rax; ThreadHandle
0x180029707  lea     r8d, [rdx-3]; OpenAsSelf
0x18002970b  call    cs:__imp_OpenThreadToken
0x180029712  nop     dword ptr [rax+rax+00h]
0x180029717  lea     rcx, ?g_csImpersonationLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18002971e  call    cs:__imp_LeaveCriticalSection
0x180029725  nop     dword ptr [rax+rax+00h]
0x18002972a  mov     rax, rbx
0x18002972d  mov     rbx, [rsp+28h+arg_0]
0x180029732  add     rsp, 20h
0x180029736  pop     rdi
0x180029737  retn
0x180029739  call    cs:__imp_TlsGetValue
0x180029740  nop     dword ptr [rax+rax+00h]
0x180029745  mov     ecx, cs:?g_dwImpersonationSlot@@3KA; dwTlsIndex
0x18002974b  xor     edx, edx; lpTlsValue
0x18002974d  mov     [rbx], rax
0x180029750  call    cs:__imp_TlsSetValue
0x180029757  nop     dword ptr [rax+rax+00h]
0x18002975c  test    eax, eax
0x18002975e  jz      short loc_180029782
0x180029760  xor     edx, edx; Token
0x180029762  xor     ecx, ecx; Thread
0x180029764  call    cs:__imp_SetThreadToken
0x18002976b  nop     dword ptr [rax+rax+00h]
0x180029770  test    eax, eax
0x180029772  jnz     loc_1800296EF
0x180029778  call    ExitProcessIfNotClient
0x18002977d  jmp     loc_1800296EF
0x180029782  call    ExitProcessIfNotClient
0x180029787  jmp     short loc_180029760
```
