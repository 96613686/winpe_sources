# MsiUIMessageContext::SetUserToken(bool)

- ea: `0x18004e85c`
- end: `0x18004eb15`
- name: `?SetUserToken@MsiUIMessageContext@@QEAAI_N@Z`
- size: `697`
- prototype: `unsigned int __fastcall(MsiUIMessageContext *__hidden this, bool)`
- caller_count: `3`
- callee_count: `6`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x18004ccbc`
- `0x18004d644`
- `0x1801ce694`

## callees

- `0x18000c4bc`
- `0x180013fe4`
- `0x180027634`
- `0x18004e85c`
- `0x18004eb1c`
- `0x1801bce9c`

## import_xrefs

- `ADVAPI32!DuplicateTokenEx` at `0x18004e918`
- `ADVAPI32!DuplicateTokenEx` at `0x18004e941`
- `ADVAPI32!DuplicateTokenEx` at `0x18004e918`
- `ADVAPI32!DuplicateTokenEx` at `0x18004e941`
- `ADVAPI32!OpenThreadToken` at `0x18004e9eb`
- `ADVAPI32!OpenThreadToken` at `0x18004e9eb`
- `KERNEL32!CloseHandle` at `0x18004e894`
- `KERNEL32!CloseHandle` at `0x18004e894`
- `KERNEL32!GetLastError` at `0x18004e9fb`
- `KERNEL32!GetLastError` at `0x18004e9fb`
- `KERNEL32!GetCurrentThread` at `0x18004e9d0`
- `KERNEL32!GetCurrentThread` at `0x18004e9d0`

## string_xrefs

- `0x18004e8d3`: `Trying to set user token in service, with no Transaction object present`
- `0x18004e8f4`: `Transaction object missing User Token`
- `0x18004e959`: `Unable to Duplicate Transaction Token in SetUserToken`
- `0x18004ea21`: `Failed to open thread token (error %d): we're not impersonated`
- `0x18004ea80`: `Opened thread token: we're impersonated`
- `0x18004ead6`: `Failed to determine if we are impersonated`

## pseudocode

```c
__int64 __fastcall MsiUIMessageContext::SetUserToken(MsiUIMessageContext *this, char a2)
{
  void **phNewToken; // rdi
  void *v5; // rcx
  const unsigned __int16 *v6; // r9
  struct IUnknownVtbl *lpVtbl; // rsi
  int v9; // eax
  HANDLE CurrentThread; // rax
  const unsigned __int16 *LastError; // rbx
  unsigned int v12; // [rsp+50h] [rbp-38h]
  void *v13; // [rsp+58h] [rbp-30h]

  *((_BYTE *)this + 306) = 0;
  if ( a2 && *((_QWORD *)this + 29) )
    return 0;
  phNewToken = (void **)((char *)this + 152);
  v5 = (void *)*((_QWORD *)this + 19);
  if ( v5 )
  {
    CloseHandle(v5);
    *phNewToken = 0;
  }
  if ( a2 )
    return 0;
  if ( g_scServerContext == 2 )
  {
    if ( !CMsiTransaction::m_pMsiTransaction )
    {
      if ( g_dmDiagnosticMode )
      {
        v6 = L"Trying to set user token in service, with no Transaction object present";
LABEL_17:
        DebugString(10, 0, 0, v6, L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", L"(NULL)", 0, 0);
        return 1601;
      }
      return 1601;
    }
    lpVtbl = CMsiTransaction::m_pMsiTransaction[5].lpVtbl;
    if ( !lpVtbl )
    {
      if ( g_dmDiagnosticMode )
      {
        v6 = L"Transaction object missing User Token";
        goto LABEL_17;
      }
      return 1601;
    }
    if ( !DuplicateTokenEx(lpVtbl, 0, 0, SecurityImpersonation, TokenImpersonation, phNewToken)
      && !DuplicateTokenEx(lpVtbl, 0, 0, SecurityIdentification, TokenImpersonation, phNewToken) )
    {
      if ( g_dmDiagnosticMode )
      {
        v6 = L"Unable to Duplicate Transaction Token in SetUserToken";
        goto LABEL_17;
      }
      return 1601;
    }
    *((_BYTE *)this + 306) = !IsTokenOnTerminalServerConsole(*phNewToken);
    return 0;
  }
  if ( g_scServerContext )
    return 0;
  v9 = RunningAsLocalSystem();
  if ( v9 == 1 )
  {
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 0xFu, 1, phNewToken) )
    {
      LastError = (const unsigned __int16 *)GetLastError();
      if ( g_dmDiagnosticMode )
        DebugString(
          10,
          0,
          0,
          L"Failed to open thread token (error %d): we're not impersonated",
          LastError,
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          0,
          0);
      *phNewToken = 0;
      return (_DWORD)LastError != 1008 ? 0x65F : 0;
    }
    if ( g_dmDiagnosticMode )
      DebugString(
        10,
        0,
        0,
        "Opened thread token: we're impersonated",
        "(NULL)",
        "(NULL)",
        "(NULL)",
        "(NULL)",
        "(NULL)",
        "(NULL)",
        v12,
        v13);
    SetEngineInitialImpersonationCount();
    return 0;
  }
  if ( v9 != -1 )
    return 0;
  if ( g_dmDiagnosticMode )
    DebugString(
      10,
      0,
      0,
      L"Failed to determine if we are impersonated",
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      0,
      0);
  *phNewToken = 0;
  return 1631;
}

```

## disassembly

```asm
0x18004e85c  push    rbx
0x18004e85e  push    rbp
0x18004e85f  push    rsi
0x18004e860  push    rdi
0x18004e861  sub     rsp, 68h
0x18004e865  xor     ebp, ebp
0x18004e867  mov     sil, dl
0x18004e86a  mov     [rcx+132h], bpl
0x18004e871  mov     rbx, rcx
0x18004e874  test    dl, dl
0x18004e876  jz      short loc_18004E885
0x18004e878  cmp     [rcx+0E8h], rbp
0x18004e87f  jnz     loc_18004E9B2
0x18004e885  lea     rdi, [rcx+98h]
0x18004e88c  mov     rcx, [rdi]; hObject
0x18004e88f  test    rcx, rcx
0x18004e892  jz      short loc_18004E8A3
0x18004e894  call    cs:__imp_CloseHandle
0x18004e89b  nop     dword ptr [rax+rax+00h]
0x18004e8a0  mov     [rdi], rbp
0x18004e8a3  test    sil, sil
0x18004e8a6  jnz     loc_18004E9B2
0x18004e8ac  mov     eax, cs:?g_scServerContext@@3W4scEnum@@A; scEnum g_scServerContext
0x18004e8b2  cmp     eax, 2
0x18004e8b5  jnz     loc_18004E9BE
0x18004e8bb  mov     rax, cs:?m_pMsiTransaction@CMsiTransaction@@0PEAV1@EA; CMsiTransaction * CMsiTransaction::m_pMsiTransaction
0x18004e8c2  test    rax, rax
0x18004e8c5  jnz     short loc_18004E8DF
0x18004e8c7  cmp     cs:?g_dmDiagnosticMode@@3HA, ebp; int g_dmDiagnosticMode
0x18004e8cd  jz      loc_18004E99B
0x18004e8d3  lea     r9, aTryingToSetUse; "Trying to set user token in service, wi"...
0x18004e8da  jmp     loc_18004E960
0x18004e8df  mov     rsi, [rax+28h]
0x18004e8e3  test    rsi, rsi
0x18004e8e6  jnz     short loc_18004E8FD
0x18004e8e8  cmp     cs:?g_dmDiagnosticMode@@3HA, ebp; int g_dmDiagnosticMode
0x18004e8ee  jz      loc_18004E99B
0x18004e8f4  lea     r9, aTransactionObj; "Transaction object missing User Token"
0x18004e8fb  jmp     short loc_18004E960
0x18004e8fd  mov     [rsp+88h+phNewToken], rdi; phNewToken
0x18004e902  mov     r9d, 2; ImpersonationLevel
0x18004e908  xor     r8d, r8d; lpTokenAttributes
0x18004e90b  mov     [rsp+88h+TokenType], 2; TokenType
0x18004e913  xor     edx, edx; dwDesiredAccess
0x18004e915  mov     rcx, rsi; hExistingToken
0x18004e918  call    cs:__imp_DuplicateTokenEx
0x18004e91f  nop     dword ptr [rax+rax+00h]
0x18004e924  test    eax, eax
0x18004e926  jnz     short loc_18004E9A2
0x18004e928  mov     [rsp+88h+phNewToken], rdi; phNewToken
0x18004e92d  lea     r9d, [rax+1]; ImpersonationLevel
0x18004e931  xor     r8d, r8d; lpTokenAttributes
0x18004e934  mov     [rsp+88h+TokenType], 2; TokenType
0x18004e93c  xor     edx, edx; dwDesiredAccess
0x18004e93e  mov     rcx, rsi; hExistingToken
0x18004e941  call    cs:__imp_DuplicateTokenEx
0x18004e948  nop     dword ptr [rax+rax+00h]
0x18004e94d  test    eax, eax
0x18004e94f  jnz     short loc_18004E9A2
0x18004e951  cmp     cs:?g_dmDiagnosticMode@@3HA, ebp; int g_dmDiagnosticMode
0x18004e957  jz      short loc_18004E99B
0x18004e959  lea     r9, aUnableToDuplic; "Unable to Duplicate Transaction Token i"...
0x18004e960  mov     [rsp+88h+var_30], rbp; void *
0x18004e965  lea     rax, aNull; "(NULL)"
0x18004e96c  mov     [rsp+88h+var_38], ebp; unsigned int
0x18004e970  xor     edx, edx; unsigned __int16
0x18004e972  mov     [rsp+88h+var_40], rax; unsigned __int16 *
0x18004e977  xor     r8d, r8d; int
0x18004e97a  mov     [rsp+88h+var_48], rax; unsigned __int16 *
0x18004e97f  mov     [rsp+88h+var_50], rax; unsigned __int16 *
0x18004e984  mov     [rsp+88h+var_58], rax; unsigned __int16 *
0x18004e989  lea     ecx, [rdx+0Ah]; int
0x18004e98c  mov     [rsp+88h+phNewToken], rax; unsigned __int16 *
0x18004e991  mov     qword ptr [rsp+88h+TokenType], rax; unsigned __int16 *
0x18004e996  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18004e99b  mov     eax, 641h
0x18004e9a0  jmp     short loc_18004E9B4
0x18004e9a2  mov     rcx, [rdi]; void *
0x18004e9a5  call    ?IsTokenOnTerminalServerConsole@@YA_NPEAX@Z; IsTokenOnTerminalServerConsole(void *)
0x18004e9aa  xor     al, 1
0x18004e9ac  mov     [rbx+132h], al
0x18004e9b2  xor     eax, eax
0x18004e9b4  add     rsp, 68h
0x18004e9b8  pop     rdi
0x18004e9b9  pop     rsi
0x18004e9ba  pop     rbp
0x18004e9bb  pop     rbx
0x18004e9bc  retn
0x18004e9be  test    eax, eax
0x18004e9c0  jnz     short loc_18004E9B2
0x18004e9c2  call    ?RunningAsLocalSystem@@YA?AW4TRI@@XZ; RunningAsLocalSystem(void)
0x18004e9c7  cmp     eax, 1
0x18004e9ca  jnz     loc_18004EAB5
0x18004e9d0  call    cs:__imp_GetCurrentThread
0x18004e9d7  nop     dword ptr [rax+rax+00h]
0x18004e9dc  mov     edx, 0Fh; DesiredAccess
0x18004e9e1  mov     r9, rdi; TokenHandle
0x18004e9e4  mov     rcx, rax; ThreadHandle
0x18004e9e7  lea     r8d, [rdx-0Eh]; OpenAsSelf
0x18004e9eb  call    cs:__imp_OpenThreadToken
0x18004e9f2  nop     dword ptr [rax+rax+00h]
0x18004e9f7  test    eax, eax
0x18004e9f9  jnz     short loc_18004EA6A
0x18004e9fb  call    cs:__imp_GetLastError
0x18004ea02  nop     dword ptr [rax+rax+00h]
0x18004ea07  cmp     cs:?g_dmDiagnosticMode@@3HA, ebp; int g_dmDiagnosticMode
0x18004ea0d  mov     ebx, eax
0x18004ea0f  jz      short loc_18004EA53
0x18004ea11  mov     [rsp+88h+var_30], rbp; void *
0x18004ea16  lea     rax, aNull; "(NULL)"
0x18004ea1d  mov     [rsp+88h+var_38], ebp; unsigned int
0x18004ea21  lea     r9, aFailedToOpenTh; "Failed to open thread token (error %d):"...
0x18004ea28  mov     [rsp+88h+var_40], rax; unsigned __int16 *
0x18004ea2d  xor     edx, edx; unsigned __int16
0x18004ea2f  mov     [rsp+88h+var_48], rax; unsigned __int16 *
0x18004ea34  xor     r8d, r8d; int
0x18004ea37  mov     [rsp+88h+var_50], rax; unsigned __int16 *
0x18004ea3c  mov     [rsp+88h+var_58], rax; unsigned __int16 *
0x18004ea41  mov     [rsp+88h+phNewToken], rax; unsigned __int16 *
0x18004ea46  lea     ecx, [rdx+0Ah]; int
0x18004ea49  mov     qword ptr [rsp+88h+TokenType], rbx; unsigned __int16 *
0x18004ea4e  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18004ea53  sub     ebx, 3F0h
0x18004ea59  mov     [rdi], rbp
0x18004ea5c  neg     ebx
0x18004ea5e  sbb     eax, eax
0x18004ea60  and     eax, 65Fh
0x18004ea65  jmp     loc_18004E9B4
0x18004ea6a  cmp     cs:?g_dmDiagnosticMode@@3HA, ebp; int g_dmDiagnosticMode
0x18004ea70  jz      short loc_18004EAAB
0x18004ea72  lea     rax, aNull_0; "(NULL)"
0x18004ea79  xor     edx, edx; unsigned __int16
0x18004ea7b  mov     [rsp+88h+var_40], rax; char *
0x18004ea80  lea     r9, aOpenedThreadTo; "Opened thread token: we're impersonated"
0x18004ea87  mov     [rsp+88h+var_48], rax; char *
0x18004ea8c  xor     r8d, r8d; int
0x18004ea8f  mov     [rsp+88h+var_50], rax; char *
0x18004ea94  mov     [rsp+88h+var_58], rax; char *
0x18004ea99  lea     ecx, [rdx+0Ah]; int
0x18004ea9c  mov     [rsp+88h+phNewToken], rax; char *
0x18004eaa1  mov     qword ptr [rsp+88h+TokenType], rax; char *
0x18004eaa6  call    ?DebugString@@YAXHGHPEBD000000KPEAX@Z; DebugString(int,ushort,int,char const *,char const *,char const *,char const *,char const *,char const *,char const *,ulong,void *)
0x18004eaab  call    ?SetEngineInitialImpersonationCount@@YAXXZ; SetEngineInitialImpersonationCount(void)
0x18004eab0  jmp     loc_18004E9B2
0x18004eab5  cmp     eax, 0FFFFFFFFh
0x18004eab8  jnz     loc_18004E9B2
0x18004eabe  cmp     cs:?g_dmDiagnosticMode@@3HA, ebp; int g_dmDiagnosticMode
0x18004eac4  jz      short loc_18004EB08
0x18004eac6  mov     [rsp+88h+var_30], rbp; void *
0x18004eacb  lea     rax, aNull; "(NULL)"
0x18004ead2  mov     [rsp+88h+var_38], ebp; unsigned int
0x18004ead6  lea     r9, aFailedToDeterm; "Failed to determine if we are impersona"...
0x18004eadd  mov     [rsp+88h+var_40], rax; unsigned __int16 *
0x18004eae2  xor     edx, edx; unsigned __int16
0x18004eae4  mov     [rsp+88h+var_48], rax; unsigned __int16 *
0x18004eae9  xor     r8d, r8d; int
0x18004eaec  mov     [rsp+88h+var_50], rax; unsigned __int16 *
0x18004eaf1  mov     [rsp+88h+var_58], rax; unsigned __int16 *
0x18004eaf6  mov     [rsp+88h+phNewToken], rax; unsigned __int16 *
0x18004eafb  lea     ecx, [rdx+0Ah]; int
0x18004eafe  mov     qword ptr [rsp+88h+TokenType], rax; unsigned __int16 *
0x18004eb03  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18004eb08  mov     [rdi], rbp
0x18004eb0b  mov     eax, 65Fh
0x18004eb10  jmp     loc_18004E9B4
```
