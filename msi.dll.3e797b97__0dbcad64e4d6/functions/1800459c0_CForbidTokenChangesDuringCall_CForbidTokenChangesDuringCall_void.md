# CForbidTokenChangesDuringCall::~CForbidTokenChangesDuringCall(void)

- ea: `0x1800459c0`
- end: `0x180045b9b`
- name: `??1CForbidTokenChangesDuringCall@@QEAA@XZ`
- size: `475`
- prototype: `void __fastcall(CForbidTokenChangesDuringCall *__hidden this)`
- caller_count: `165`
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
- `0x180044bb0`
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

## callees

- `0x18000c4bc`
- `0x1800459c0`
- `0x180045ba4`
- `0x18015cbac`

## import_xrefs

- `ADVAPI32!SetThreadToken` at `0x180045b0a`
- `ADVAPI32!SetThreadToken` at `0x180045b36`
- `ADVAPI32!SetThreadToken` at `0x180045b0a`
- `ADVAPI32!SetThreadToken` at `0x180045b36`
- `ADVAPI32!OpenThreadToken` at `0x180045a6a`
- `ADVAPI32!OpenThreadToken` at `0x180045a6a`
- `ADVAPI32!OpenProcessToken` at `0x180045aab`
- `ADVAPI32!OpenProcessToken` at `0x180045aab`
- `KERNEL32!CloseHandle` at `0x180045af4`
- `KERNEL32!CloseHandle` at `0x180045b24`
- `KERNEL32!CloseHandle` at `0x180045af4`
- `KERNEL32!CloseHandle` at `0x180045b24`
- `KERNEL32!LeaveCriticalSection` at `0x180045a0d`
- `KERNEL32!LeaveCriticalSection` at `0x180045a0d`
- `KERNEL32!EnterCriticalSection` at `0x1800459f8`
- `KERNEL32!EnterCriticalSection` at `0x1800459f8`
- `KERNEL32!GetCurrentThread` at `0x180045a4d`
- `KERNEL32!GetCurrentThread` at `0x180045a4d`
- `KERNEL32!GetCurrentProcess` at `0x180045a8f`
- `KERNEL32!GetCurrentProcess` at `0x180045a8f`
- `KERNEL32!TlsSetValue` at `0x180045a29`
- `KERNEL32!TlsSetValue` at `0x180045a29`

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

  v1 = dword_180310D00;
  if ( dword_180310D00 == -1 )
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
      dword_180310D00 = v6;
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
0x1800459c0  mov     [rsp+arg_0], rbx
0x1800459c5  mov     [rsp+arg_18], rbp
0x1800459ca  push    rdi
0x1800459cb  sub     rsp, 60h
0x1800459cf  mov     eax, cs:dword_180310D00
0x1800459d5  or      rbp, 0FFFFFFFFFFFFFFFFh
0x1800459d9  mov     rdi, rcx
0x1800459dc  cmp     eax, ebp
0x1800459de  jz      short loc_180045A48
0x1800459e0  cmp     eax, 1
0x1800459e3  jnz     short loc_180045A35
0x1800459e5  cmp     cs:?g_scServerContext@@3W4scEnum@@A, 2; scEnum g_scServerContext
0x1800459ec  jz      short loc_180045A35
0x1800459ee  lea     rbp, ?g_csImpersonationLock@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION g_csImpersonationLock
0x1800459f5  mov     rcx, rbp; lpCriticalSection
0x1800459f8  call    cs:__imp_EnterCriticalSection
0x1800459ff  nop     dword ptr [rax+rax+00h]
0x180045a04  mov     ebx, cs:?g_dwImpersonationSlot@@3KA; ulong g_dwImpersonationSlot
0x180045a0a  mov     rcx, rbp; lpCriticalSection
0x180045a0d  call    cs:__imp_LeaveCriticalSection
0x180045a14  nop     dword ptr [rax+rax+00h]
0x180045a19  cmp     ebx, 0FFFFFFFFh
0x180045a1c  jz      short loc_180045A35
0x180045a1e  cmp     byte ptr [rdi+8], 0
0x180045a22  jz      short loc_180045A35
0x180045a24  mov     rdx, [rdi]; lpTlsValue
0x180045a27  mov     ecx, ebx; dwTlsIndex
0x180045a29  call    cs:__imp_TlsSetValue
0x180045a30  nop     dword ptr [rax+rax+00h]
0x180045a35  lea     r11, [rsp+68h+var_8]
0x180045a3a  mov     rbx, [r11+10h]
0x180045a3e  mov     rbp, [r11+28h]
0x180045a42  mov     rsp, r11
0x180045a45  pop     rdi
0x180045a46  retn
0x180045a48  mov     [rsp+68h+TokenHandle], rbp
0x180045a4d  call    cs:__imp_GetCurrentThread
0x180045a54  nop     dword ptr [rax+rax+00h]
0x180045a59  mov     edx, 4; DesiredAccess
0x180045a5e  lea     r9, [rsp+68h+TokenHandle]; TokenHandle
0x180045a63  mov     rcx, rax; ThreadHandle
0x180045a66  lea     r8d, [rdx-3]; OpenAsSelf
0x180045a6a  call    cs:__imp_OpenThreadToken
0x180045a71  nop     dword ptr [rax+rax+00h]
0x180045a76  test    eax, eax
0x180045a78  jnz     loc_180045B32
0x180045a7e  mov     [rsp+68h+TokenHandle], rbp
0x180045a83  mov     [rsp+68h+hObject], 0
0x180045a8f  call    cs:__imp_GetCurrentProcess
0x180045a96  nop     dword ptr [rax+rax+00h]
0x180045a9b  lea     r8, [rsp+68h+hObject]; TokenHandle
0x180045aa3  mov     edx, 8; DesiredAccess
0x180045aa8  mov     rcx, rax; ProcessHandle
0x180045aab  call    cs:__imp_OpenProcessToken
0x180045ab2  nop     dword ptr [rax+rax+00h]
0x180045ab7  test    eax, eax
0x180045ab9  jnz     short loc_180045ADC
0x180045abb  cmp     cs:?g_dmDiagnosticMode@@3HA, eax; int g_dmDiagnosticMode
0x180045ac1  jnz     loc_180045B54
0x180045ac7  mov     rdx, [rsp+68h+TokenHandle]; Token
0x180045acc  cmp     rdx, rbp
0x180045acf  jnz     short loc_180045B08
0x180045ad1  mov     eax, cs:dword_180310D00
0x180045ad7  jmp     loc_1800459E0
0x180045adc  mov     rcx, [rsp+68h+hObject]; void *
0x180045ae4  call    ?IsLocalSystemToken@@YA_NPEAX@Z; IsLocalSystemToken(void *)
0x180045ae9  mov     rcx, [rsp+68h+hObject]; hObject
0x180045af1  movzx   ebx, al
0x180045af4  call    cs:__imp_CloseHandle
0x180045afb  nop     dword ptr [rax+rax+00h]
0x180045b00  mov     cs:dword_180310D00, ebx
0x180045b06  jmp     short loc_180045AC7
0x180045b08  xor     ecx, ecx; Thread
0x180045b0a  call    cs:__imp_SetThreadToken
0x180045b11  nop     dword ptr [rax+rax+00h]
0x180045b16  test    eax, eax
0x180045b18  jnz     short loc_180045B1F
0x180045b1a  call    ExitProcessIfNotClient
0x180045b1f  mov     rcx, [rsp+68h+TokenHandle]; hObject
0x180045b24  call    cs:__imp_CloseHandle
0x180045b2b  nop     dword ptr [rax+rax+00h]
0x180045b30  jmp     short loc_180045AD1
0x180045b32  xor     edx, edx; Token
0x180045b34  xor     ecx, ecx; Thread
0x180045b36  call    cs:__imp_SetThreadToken
0x180045b3d  nop     dword ptr [rax+rax+00h]
0x180045b42  test    eax, eax
0x180045b44  jnz     loc_180045A83
0x180045b4a  call    ExitProcessIfNotClient
0x180045b4f  jmp     loc_180045A83
0x180045b54  lea     rax, aNull; "(NULL)"
0x180045b5b  xor     edx, edx; unsigned __int16
0x180045b5d  mov     [rsp+68h+var_10], rdx; void *
0x180045b62  lea     r9, aCouldNotDeterm_1; "Could not determine if the process is r"...
0x180045b69  mov     [rsp+68h+var_18], edx; unsigned int
0x180045b6d  xor     r8d, r8d; int
0x180045b70  mov     [rsp+68h+var_20], rax; unsigned __int16 *
0x180045b75  mov     [rsp+68h+var_28], rax; unsigned __int16 *
0x180045b7a  lea     ecx, [rdx+9]; int
0x180045b7d  mov     [rsp+68h+var_30], rax; unsigned __int16 *
0x180045b82  mov     [rsp+68h+var_38], rax; unsigned __int16 *
0x180045b87  mov     [rsp+68h+var_40], rax; unsigned __int16 *
0x180045b8c  mov     [rsp+68h+var_48], rax; unsigned __int16 *
0x180045b91  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x180045b96  jmp     loc_180045AC7
```
