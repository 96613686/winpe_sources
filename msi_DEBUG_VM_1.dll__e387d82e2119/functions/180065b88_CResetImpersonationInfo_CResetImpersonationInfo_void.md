# CResetImpersonationInfo::CResetImpersonationInfo(void)

- ea: `0x180065b88`
- end: `0x180065c33`
- name: `??0CResetImpersonationInfo@@QEAA@XZ`
- size: `171`
- prototype: `CResetImpersonationInfo *__fastcall(CResetImpersonationInfo *__hidden this)`
- caller_count: `82`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180056860`
- `0x1800569a0`
- `0x180056d60`
- `0x1800574e0`
- `0x1800575b0`
- `0x180057b50`
- `0x180057c20`
- `0x180058780`
- `0x180059360`
- `0x180064150`
- `0x1800659c0`
- `0x180066250`
- `0x1800f10b0`
- `0x18010dbe0`
- `0x18010ea00`
- `0x180114f70`
- `0x180115bb0`
- `0x180116380`
- `0x180118b10`
- `0x18011c3b0`
- `0x180129720`
- `0x18012c3e0`
- `0x180134ac0`
- `0x180145390`
- `0x180145520`
- `0x1801559e0`
- `0x1801592e0`
- `0x180159610`
- `0x18015bc20`
- `0x18015c3f0`
- `0x18015cad0`
- `0x18015d500`
- `0x18015e2d0`
- `0x18015e520`
- `0x18015eef0`
- `0x18015f5d0`
- `0x18015f750`
- `0x180162bf0`
- `0x180164370`
- `0x180166320`
- `0x18016e280`
- `0x1801703e0`
- `0x180170520`
- `0x180170710`
- `0x180170840`
- `0x180170980`
- `0x180170a60`
- `0x180170b30`
- `0x180170c00`
- `0x180170cc0`

## callees

- `0x180065b88`
- `0x180157094`

## import_xrefs

- `ADVAPI32!SetThreadToken` at `0x180065c1b`
- `ADVAPI32!SetThreadToken` at `0x180065c1b`
- `ADVAPI32!OpenThreadToken` at `0x180065bdb`
- `ADVAPI32!OpenThreadToken` at `0x180065bdb`
- `KERNEL32!LeaveCriticalSection` at `0x180065be8`
- `KERNEL32!LeaveCriticalSection` at `0x180065be8`
- `KERNEL32!EnterCriticalSection` at `0x180065bb4`
- `KERNEL32!EnterCriticalSection` at `0x180065bb4`
- `KERNEL32!GetCurrentThread` at `0x180065bc5`
- `KERNEL32!GetCurrentThread` at `0x180065bc5`
- `KERNEL32!TlsSetValue` at `0x180065c0d`
- `KERNEL32!TlsSetValue` at `0x180065c0d`
- `KERNEL32!TlsGetValue` at `0x180065bfc`
- `KERNEL32!TlsGetValue` at `0x180065bfc`

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
0x180065b88  mov     [rsp+arg_0], rbx
0x180065b8d  push    rdi
0x180065b8e  sub     rsp, 20h
0x180065b92  cmp     cs:?g_scServerContext@@3W4scEnum@@A, 2; scEnum g_scServerContext
0x180065b99  mov     rbx, rcx
0x180065b9c  mov     qword ptr [rcx], 0
0x180065ba3  mov     qword ptr [rcx+8], 0
0x180065bab  jnz     short loc_180065BEE
0x180065bad  lea     rcx, ?g_csImpersonationLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180065bb4  call    cs:__imp_EnterCriticalSection
0x180065bba  mov     ecx, cs:?g_dwImpersonationSlot@@3KA; dwTlsIndex
0x180065bc0  cmp     ecx, 0FFFFFFFFh
0x180065bc3  jnz     short loc_180065BFC
0x180065bc5  call    cs:__imp_GetCurrentThread
0x180065bcb  mov     edx, 4; DesiredAccess
0x180065bd0  lea     r9, [rbx+8]; TokenHandle
0x180065bd4  mov     rcx, rax; ThreadHandle
0x180065bd7  lea     r8d, [rdx-3]; OpenAsSelf
0x180065bdb  call    cs:__imp_OpenThreadToken
0x180065be1  lea     rcx, ?g_csImpersonationLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180065be8  call    cs:__imp_LeaveCriticalSection
0x180065bee  mov     rax, rbx
0x180065bf1  mov     rbx, [rsp+28h+arg_0]
0x180065bf6  add     rsp, 20h
0x180065bfa  pop     rdi
0x180065bfb  retn
0x180065bfc  call    cs:__imp_TlsGetValue
0x180065c02  mov     ecx, cs:?g_dwImpersonationSlot@@3KA; dwTlsIndex
0x180065c08  xor     edx, edx; lpTlsValue
0x180065c0a  mov     [rbx], rax
0x180065c0d  call    cs:__imp_TlsSetValue
0x180065c13  test    eax, eax
0x180065c15  jz      short loc_180065C2C
0x180065c17  xor     edx, edx; Token
0x180065c19  xor     ecx, ecx; Thread
0x180065c1b  call    cs:__imp_SetThreadToken
0x180065c21  test    eax, eax
0x180065c23  jnz     short loc_180065BC5
0x180065c25  call    ExitProcessIfNotClient
0x180065c2a  jmp     short loc_180065BC5
0x180065c2c  call    ExitProcessIfNotClient
0x180065c31  jmp     short loc_180065C17
```
