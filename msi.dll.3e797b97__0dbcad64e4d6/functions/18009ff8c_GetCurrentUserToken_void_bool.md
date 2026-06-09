# GetCurrentUserToken(void * &,bool &)

- ea: `0x18009ff8c`
- end: `0x1800a02af`
- name: `?GetCurrentUserToken@@YAKAEAPEAXAEA_N@Z`
- size: `803`
- prototype: `unsigned int __fastcall(PHANDLE TokenHandle, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, installer_update`

## callers

- `0x18009fea8`
- `0x18015b608`

## callees

- `0x18000c4bc`
- `0x180045ba4`
- `0x18009ff8c`
- `0x1800bfc6c`
- `0x18014b72c`
- `0x18015383c`
- `0x18015cbac`

## import_xrefs

- `ADVAPI32!SetThreadToken` at `0x1800a020f`
- `ADVAPI32!SetThreadToken` at `0x1800a0241`
- `ADVAPI32!SetThreadToken` at `0x1800a020f`
- `ADVAPI32!SetThreadToken` at `0x1800a0241`
- `ADVAPI32!OpenThreadToken` at `0x1800a0073`
- `ADVAPI32!OpenThreadToken` at `0x1800a00ff`
- `ADVAPI32!OpenThreadToken` at `0x1800a0073`
- `ADVAPI32!OpenThreadToken` at `0x1800a00ff`
- `ADVAPI32!OpenProcessToken` at `0x1800a00af`
- `ADVAPI32!OpenProcessToken` at `0x1800a0147`
- `ADVAPI32!OpenProcessToken` at `0x1800a00af`
- `ADVAPI32!OpenProcessToken` at `0x1800a0147`
- `KERNEL32!CloseHandle` at `0x1800a01f6`
- `KERNEL32!CloseHandle` at `0x1800a022c`
- `KERNEL32!CloseHandle` at `0x1800a01f6`
- `KERNEL32!CloseHandle` at `0x1800a022c`
- `KERNEL32!LeaveCriticalSection` at `0x18009fff9`
- `KERNEL32!LeaveCriticalSection` at `0x18009fff9`
- `KERNEL32!GetLastError` at `0x1800a0083`
- `KERNEL32!GetLastError` at `0x1800a01cb`
- `KERNEL32!GetLastError` at `0x1800a0083`
- `KERNEL32!GetLastError` at `0x1800a01cb`
- `KERNEL32!EnterCriticalSection` at `0x18009ffc9`
- `KERNEL32!EnterCriticalSection` at `0x18009ffc9`
- `KERNEL32!GetCurrentThread` at `0x1800a005a`
- `KERNEL32!GetCurrentThread` at `0x1800a00df`
- `KERNEL32!GetCurrentThread` at `0x1800a005a`
- `KERNEL32!GetCurrentThread` at `0x1800a00df`
- `KERNEL32!GetCurrentProcess` at `0x1800a009a`
- `KERNEL32!GetCurrentProcess` at `0x1800a012b`
- `KERNEL32!GetCurrentProcess` at `0x1800a009a`
- `KERNEL32!GetCurrentProcess` at `0x1800a012b`
- `KERNEL32!TlsGetValue` at `0x18009ffe0`
- `KERNEL32!TlsGetValue` at `0x18009ffe0`

## pseudocode

```c
__int64 __fastcall GetCurrentUserToken(PHANDLE TokenHandle, bool *a2)
{
  int v2; // eax
  bool *v3; // rsi
  int v5; // ecx
  unsigned int v6; // ebx
  struct IUnknownVtbl *lpVtbl; // rax
  DWORD LastError; // ebx
  HANDLE v10; // rax
  HANDLE v11; // rax
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  bool *v14; // rdx
  BOOL v15; // ebx
  void *TokenHandlea; // [rsp+80h] [rbp+18h] BYREF
  HANDLE hObject; // [rsp+88h] [rbp+20h] BYREF

  v2 = dword_180310D00;
  v3 = a2;
  if ( dword_180310D00 != -1 )
    goto LABEL_2;
  TokenHandlea = (void *)-1LL;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 4u, 1, &TokenHandlea) )
  {
    if ( !SetThreadToken(0, 0) )
      ExitProcessIfNotClient();
  }
  else
  {
    TokenHandlea = (void *)-1LL;
  }
  hObject = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 8u, &hObject) )
  {
    v15 = IsLocalSystemToken(hObject);
    CloseHandle(hObject);
    dword_180310D00 = v15;
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
  LOBYTE(a2) = (_BYTE)TokenHandlea;
  if ( TokenHandlea != (void *)-1LL )
  {
    if ( !SetThreadToken(0, TokenHandlea) )
      ExitProcessIfNotClient();
    CloseHandle(TokenHandlea);
  }
  v2 = dword_180310D00;
  if ( dword_180310D00 != -1 )
  {
LABEL_2:
    v5 = g_scServerContext;
    v6 = 0;
    if ( g_scServerContext == 2 || v2 == 1 )
    {
      EnterCriticalSection(&g_csImpersonationLock);
      if ( g_dwImpersonationSlot != -1 )
        v6 = (unsigned int)TlsGetValue(g_dwImpersonationSlot) >> 29;
      LeaveCriticalSection(&g_csImpersonationLock);
      v5 = g_scServerContext;
    }
    *v3 = 0;
    if ( v5 == 2 && v6 == 1 )
    {
      CCoImpersonate::CCoImpersonate((CCoImpersonate *)&TokenHandlea, (bool)a2);
      LastError = OpenUserToken(TokenHandle, v14);
      if ( !LastError )
        *v3 = 1;
      CCoImpersonate::~CCoImpersonate((CCoImpersonate *)&TokenHandlea);
      return LastError;
    }
    lpVtbl = (struct IUnknownVtbl *)Token;
    if ( !Token && v5 == 2 )
    {
      if ( !CMsiTransaction::m_pMsiTransaction )
      {
        *TokenHandle = 0;
        goto LABEL_14;
      }
      lpVtbl = CMsiTransaction::m_pMsiTransaction[5].lpVtbl;
    }
    LastError = 0;
    *TokenHandle = lpVtbl;
    if ( lpVtbl )
      return LastError;
LABEL_14:
    LastError = 0;
    v10 = GetCurrentThread();
    if ( !OpenThreadToken(v10, 0xCu, 1, TokenHandle) )
    {
      LastError = GetLastError();
      if ( LastError == 1008 )
      {
        LastError = 0;
        v11 = GetCurrentProcess();
        if ( !OpenProcessToken(v11, 0xCu, TokenHandle) )
          LastError = GetLastError();
      }
    }
    if ( !LastError )
      *v3 = 1;
    return LastError;
  }
  return 5;
}

```

## disassembly

```asm
0x18009ff8c  mov     [rsp+arg_0], rbx
0x18009ff91  mov     [rsp+arg_8], rsi
0x18009ff96  push    rdi
0x18009ff97  sub     rsp, 60h
0x18009ff9b  mov     eax, cs:dword_180310D00
0x18009ffa1  mov     rsi, rdx
0x18009ffa4  mov     rdi, rcx
0x18009ffa7  cmp     eax, 0FFFFFFFFh
0x18009ffaa  jz      loc_1800A00D3
0x18009ffb0  mov     ecx, cs:?g_scServerContext@@3W4scEnum@@A; scEnum g_scServerContext
0x18009ffb6  xor     ebx, ebx
0x18009ffb8  cmp     ecx, 2
0x18009ffbb  jz      short loc_18009FFC2
0x18009ffbd  cmp     eax, 1
0x18009ffc0  jnz     short loc_1800A000B
0x18009ffc2  lea     rcx, ?g_csImpersonationLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18009ffc9  call    cs:__imp_EnterCriticalSection
0x18009ffd0  nop     dword ptr [rax+rax+00h]
0x18009ffd5  mov     ecx, cs:?g_dwImpersonationSlot@@3KA; dwTlsIndex
0x18009ffdb  cmp     ecx, 0FFFFFFFFh
0x18009ffde  jz      short loc_18009FFF2
0x18009ffe0  call    cs:__imp_TlsGetValue
0x18009ffe7  nop     dword ptr [rax+rax+00h]
0x18009ffec  mov     rbx, rax
0x18009ffef  shr     ebx, 1Dh
0x18009fff2  lea     rcx, ?g_csImpersonationLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18009fff9  call    cs:__imp_LeaveCriticalSection
0x1800a0000  nop     dword ptr [rax+rax+00h]
0x1800a0005  mov     ecx, cs:?g_scServerContext@@3W4scEnum@@A; scEnum g_scServerContext
0x1800a000b  mov     byte ptr [rsi], 0
0x1800a000e  cmp     ecx, 2
0x1800a0011  jz      loc_1800A0192
0x1800a0017  mov     rax, cs:Token
0x1800a001e  test    rax, rax
0x1800a0021  jnz     short loc_1800A0028
0x1800a0023  cmp     ecx, 2
0x1800a0026  jz      short loc_1800A0045
0x1800a0028  xor     ebx, ebx
0x1800a002a  mov     [rdi], rax
0x1800a002d  test    rax, rax
0x1800a0030  jz      short loc_1800A0058
0x1800a0032  mov     eax, ebx
0x1800a0034  mov     rbx, [rsp+68h+arg_0]
0x1800a0039  mov     rsi, [rsp+68h+arg_8]
0x1800a003e  add     rsp, 60h
0x1800a0042  pop     rdi
0x1800a0043  retn
0x1800a0045  mov     rax, cs:?m_pMsiTransaction@CMsiTransaction@@0PEAV1@EA; CMsiTransaction * CMsiTransaction::m_pMsiTransaction
0x1800a004c  test    rax, rax
0x1800a004f  jnz     loc_1800A02A6
0x1800a0055  mov     [rdi], rax
0x1800a0058  xor     ebx, ebx
0x1800a005a  call    cs:__imp_GetCurrentThread
0x1800a0061  nop     dword ptr [rax+rax+00h]
0x1800a0066  mov     r9, rdi; TokenHandle
0x1800a0069  lea     edx, [rbx+0Ch]; DesiredAccess
0x1800a006c  mov     rcx, rax; ThreadHandle
0x1800a006f  lea     r8d, [rbx+1]; OpenAsSelf
0x1800a0073  call    cs:__imp_OpenThreadToken
0x1800a007a  nop     dword ptr [rax+rax+00h]
0x1800a007f  test    eax, eax
0x1800a0081  jnz     short loc_1800A00C3
0x1800a0083  call    cs:__imp_GetLastError
0x1800a008a  nop     dword ptr [rax+rax+00h]
0x1800a008f  mov     ebx, eax
0x1800a0091  cmp     eax, 3F0h
0x1800a0096  jnz     short loc_1800A00C3
0x1800a0098  xor     ebx, ebx
0x1800a009a  call    cs:__imp_GetCurrentProcess
0x1800a00a1  nop     dword ptr [rax+rax+00h]
0x1800a00a6  mov     r8, rdi; TokenHandle
0x1800a00a9  lea     edx, [rbx+0Ch]; DesiredAccess
0x1800a00ac  mov     rcx, rax; ProcessHandle
0x1800a00af  call    cs:__imp_OpenProcessToken
0x1800a00b6  nop     dword ptr [rax+rax+00h]
0x1800a00bb  test    eax, eax
0x1800a00bd  jz      loc_1800A01CB
0x1800a00c3  test    ebx, ebx
0x1800a00c5  jnz     loc_1800A0032
0x1800a00cb  mov     byte ptr [rsi], 1
0x1800a00ce  jmp     loc_1800A0032
0x1800a00d3  mov     [rsp+68h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x1800a00df  call    cs:__imp_GetCurrentThread
0x1800a00e6  nop     dword ptr [rax+rax+00h]
0x1800a00eb  mov     edx, 4; DesiredAccess
0x1800a00f0  lea     r9, [rsp+68h+TokenHandle]; TokenHandle
0x1800a00f8  mov     rcx, rax; ThreadHandle
0x1800a00fb  lea     r8d, [rdx-3]; OpenAsSelf
0x1800a00ff  call    cs:__imp_OpenThreadToken
0x1800a0106  nop     dword ptr [rax+rax+00h]
0x1800a010b  test    eax, eax
0x1800a010d  jnz     loc_1800A023D
0x1800a0113  mov     [rsp+68h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x1800a011f  mov     [rsp+68h+hObject], 0
0x1800a012b  call    cs:__imp_GetCurrentProcess
0x1800a0132  nop     dword ptr [rax+rax+00h]
0x1800a0137  lea     r8, [rsp+68h+hObject]; TokenHandle
0x1800a013f  mov     edx, 8; DesiredAccess
0x1800a0144  mov     rcx, rax; ProcessHandle
0x1800a0147  call    cs:__imp_OpenProcessToken
0x1800a014e  nop     dword ptr [rax+rax+00h]
0x1800a0153  test    eax, eax
0x1800a0155  jnz     loc_1800A01DE
0x1800a015b  cmp     cs:?g_dmDiagnosticMode@@3HA, eax; int g_dmDiagnosticMode
0x1800a0161  jnz     loc_1800A025F
0x1800a0167  mov     rdx, [rsp+68h+TokenHandle]; Token
0x1800a016f  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x1800a0173  jnz     loc_1800A020D
0x1800a0179  mov     eax, cs:dword_180310D00
0x1800a017f  cmp     eax, 0FFFFFFFFh
0x1800a0182  jnz     loc_18009FFB0
0x1800a0188  mov     eax, 5
0x1800a018d  jmp     loc_1800A0034
0x1800a0192  cmp     ebx, 1
0x1800a0195  jnz     loc_1800A0017
0x1800a019b  lea     rcx, [rsp+68h+TokenHandle]; this
0x1800a01a3  call    ??0CCoImpersonate@@QEAA@_N@Z; CCoImpersonate::CCoImpersonate(bool)
0x1800a01a8  mov     rcx, rdi; TokenHandle
0x1800a01ab  call    ?OpenUserToken@@YAKAEAPEAXPEA_N@Z; OpenUserToken(void * &,bool *)
0x1800a01b0  mov     ebx, eax
0x1800a01b2  test    eax, eax
0x1800a01b4  jnz     short loc_1800A01B9
0x1800a01b6  mov     byte ptr [rsi], 1
0x1800a01b9  lea     rcx, [rsp+68h+TokenHandle]; this
0x1800a01c1  call    ??1CCoImpersonate@@QEAA@XZ; CCoImpersonate::~CCoImpersonate(void)
0x1800a01c6  jmp     loc_1800A0032
0x1800a01cb  call    cs:__imp_GetLastError
0x1800a01d2  nop     dword ptr [rax+rax+00h]
0x1800a01d7  mov     ebx, eax
0x1800a01d9  jmp     loc_1800A00C3
0x1800a01de  mov     rcx, [rsp+68h+hObject]; void *
0x1800a01e6  call    ?IsLocalSystemToken@@YA_NPEAX@Z; IsLocalSystemToken(void *)
0x1800a01eb  mov     rcx, [rsp+68h+hObject]; hObject
0x1800a01f3  movzx   ebx, al
0x1800a01f6  call    cs:__imp_CloseHandle
0x1800a01fd  nop     dword ptr [rax+rax+00h]
0x1800a0202  mov     cs:dword_180310D00, ebx
0x1800a0208  jmp     loc_1800A0167
0x1800a020d  xor     ecx, ecx; Thread
0x1800a020f  call    cs:__imp_SetThreadToken
0x1800a0216  nop     dword ptr [rax+rax+00h]
0x1800a021b  test    eax, eax
0x1800a021d  jnz     short loc_1800A0224
0x1800a021f  call    ExitProcessIfNotClient
0x1800a0224  mov     rcx, [rsp+68h+TokenHandle]; hObject
0x1800a022c  call    cs:__imp_CloseHandle
0x1800a0233  nop     dword ptr [rax+rax+00h]
0x1800a0238  jmp     loc_1800A0179
0x1800a023d  xor     edx, edx; Token
0x1800a023f  xor     ecx, ecx; Thread
0x1800a0241  call    cs:__imp_SetThreadToken
0x1800a0248  nop     dword ptr [rax+rax+00h]
0x1800a024d  test    eax, eax
0x1800a024f  jnz     loc_1800A011F
0x1800a0255  call    ExitProcessIfNotClient
0x1800a025a  jmp     loc_1800A011F
0x1800a025f  lea     rax, aNull; "(NULL)"
0x1800a0266  xor     edx, edx; unsigned __int16
0x1800a0268  mov     [rsp+68h+var_10], rdx; void *
0x1800a026d  lea     r9, aCouldNotDeterm_1; "Could not determine if the process is r"...
0x1800a0274  mov     [rsp+68h+var_18], edx; unsigned int
0x1800a0278  xor     r8d, r8d; int
0x1800a027b  mov     [rsp+68h+var_20], rax; unsigned __int16 *
0x1800a0280  mov     [rsp+68h+var_28], rax; unsigned __int16 *
0x1800a0285  lea     ecx, [rdx+9]; int
0x1800a0288  mov     [rsp+68h+var_30], rax; unsigned __int16 *
0x1800a028d  mov     [rsp+68h+var_38], rax; unsigned __int16 *
0x1800a0292  mov     [rsp+68h+var_40], rax; unsigned __int16 *
0x1800a0297  mov     [rsp+68h+var_48], rax; unsigned __int16 *
0x1800a029c  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1800a02a1  jmp     loc_1800A0167
0x1800a02a6  mov     rax, [rax+28h]
0x1800a02aa  jmp     loc_1800A0028
```
