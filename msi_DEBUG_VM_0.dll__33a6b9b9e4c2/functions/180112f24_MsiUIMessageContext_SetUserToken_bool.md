# MsiUIMessageContext::SetUserToken(bool)

- ea: `0x180112f24`
- end: `0x1801131b5`
- name: `?SetUserToken@MsiUIMessageContext@@QEAAI_N@Z`
- size: `657`
- prototype: `unsigned int __fastcall(MsiUIMessageContext *__hidden this, bool)`
- caller_count: `3`
- callee_count: `6`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180111454`
- `0x180111d80`
- `0x1801c5f70`

## callees

- `0x18000a150`
- `0x180024f9c`
- `0x180025a18`
- `0x180112f24`
- `0x1801131bc`
- `0x1801b5050`

## import_xrefs

- `ADVAPI32!DuplicateTokenEx` at `0x180112fd7`
- `ADVAPI32!DuplicateTokenEx` at `0x180112ffa`
- `ADVAPI32!DuplicateTokenEx` at `0x180112fd7`
- `ADVAPI32!DuplicateTokenEx` at `0x180112ffa`
- `ADVAPI32!OpenThreadToken` at `0x180113097`
- `ADVAPI32!OpenThreadToken` at `0x180113097`
- `KERNEL32!CloseHandle` at `0x180112f5c`
- `KERNEL32!CloseHandle` at `0x180112f5c`
- `KERNEL32!GetLastError` at `0x1801130a1`
- `KERNEL32!GetLastError` at `0x1801130a1`
- `KERNEL32!GetCurrentThread` at `0x180113082`
- `KERNEL32!GetCurrentThread` at `0x180113082`

## string_xrefs

- `0x180112f95`: `Trying to set user token in service, with no Transaction object present`
- `0x180112fb3`: `Transaction object missing User Token`
- `0x18011300c`: `Unable to Duplicate Transaction Token in SetUserToken`
- `0x1801130c1`: `Failed to open thread token (error %d): we're not impersonated`
- `0x180113120`: `Opened thread token: we're impersonated`
- `0x180113176`: `Failed to determine if we are impersonated`

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
0x180112f24  push    rbx
0x180112f26  push    rbp
0x180112f27  push    rsi
0x180112f28  push    rdi
0x180112f29  sub     rsp, 68h
0x180112f2d  xor     ebp, ebp
0x180112f2f  mov     sil, dl
0x180112f32  mov     [rcx+132h], bpl
0x180112f39  mov     rbx, rcx
0x180112f3c  test    dl, dl
0x180112f3e  jz      short loc_180112F4D
0x180112f40  cmp     [rcx+0E8h], rbp
0x180112f47  jnz     loc_180113065
0x180112f4d  lea     rdi, [rcx+98h]
0x180112f54  mov     rcx, [rdi]; hObject
0x180112f57  test    rcx, rcx
0x180112f5a  jz      short loc_180112F65
0x180112f5c  call    cs:__imp_CloseHandle
0x180112f62  mov     [rdi], rbp
0x180112f65  test    sil, sil
0x180112f68  jnz     loc_180113065
0x180112f6e  mov     eax, cs:?g_scServerContext@@3W4scEnum@@A; scEnum g_scServerContext
0x180112f74  cmp     eax, 2
0x180112f77  jnz     loc_180113070
0x180112f7d  mov     rax, cs:?m_pMsiTransaction@CMsiTransaction@@0PEAV1@EA; CMsiTransaction * CMsiTransaction::m_pMsiTransaction
0x180112f84  test    rax, rax
0x180112f87  jnz     short loc_180112F9E
0x180112f89  cmp     cs:?g_dmDiagnosticMode@@3HA, ebp; int g_dmDiagnosticMode
0x180112f8f  jz      loc_18011304E
0x180112f95  lea     r9, aTryingToSetUse; "Trying to set user token in service, wi"...
0x180112f9c  jmp     short loc_180113013
0x180112f9e  mov     rsi, [rax+28h]
0x180112fa2  test    rsi, rsi
0x180112fa5  jnz     short loc_180112FBC
0x180112fa7  cmp     cs:?g_dmDiagnosticMode@@3HA, ebp; int g_dmDiagnosticMode
0x180112fad  jz      loc_18011304E
0x180112fb3  lea     r9, aTransactionObj; "Transaction object missing User Token"
0x180112fba  jmp     short loc_180113013
0x180112fbc  mov     [rsp+88h+phNewToken], rdi; phNewToken
0x180112fc1  mov     r9d, 2; ImpersonationLevel
0x180112fc7  xor     r8d, r8d; lpTokenAttributes
0x180112fca  mov     [rsp+88h+TokenType], 2; TokenType
0x180112fd2  xor     edx, edx; dwDesiredAccess
0x180112fd4  mov     rcx, rsi; hExistingToken
0x180112fd7  call    cs:__imp_DuplicateTokenEx
0x180112fdd  test    eax, eax
0x180112fdf  jnz     short loc_180113055
0x180112fe1  mov     [rsp+88h+phNewToken], rdi; phNewToken
0x180112fe6  lea     r9d, [rax+1]; ImpersonationLevel
0x180112fea  xor     r8d, r8d; lpTokenAttributes
0x180112fed  mov     [rsp+88h+TokenType], 2; TokenType
0x180112ff5  xor     edx, edx; dwDesiredAccess
0x180112ff7  mov     rcx, rsi; hExistingToken
0x180112ffa  call    cs:__imp_DuplicateTokenEx
0x180113000  test    eax, eax
0x180113002  jnz     short loc_180113055
0x180113004  cmp     cs:?g_dmDiagnosticMode@@3HA, ebp; int g_dmDiagnosticMode
0x18011300a  jz      short loc_18011304E
0x18011300c  lea     r9, aUnableToDuplic; "Unable to Duplicate Transaction Token i"...
0x180113013  mov     [rsp+88h+var_30], rbp; void *
0x180113018  lea     rax, aNull; "(NULL)"
0x18011301f  mov     [rsp+88h+var_38], ebp; unsigned int
0x180113023  xor     edx, edx; unsigned __int16
0x180113025  mov     [rsp+88h+var_40], rax; unsigned __int16 *
0x18011302a  xor     r8d, r8d; int
0x18011302d  mov     [rsp+88h+var_48], rax; unsigned __int16 *
0x180113032  mov     [rsp+88h+var_50], rax; unsigned __int16 *
0x180113037  mov     [rsp+88h+var_58], rax; unsigned __int16 *
0x18011303c  lea     ecx, [rdx+0Ah]; int
0x18011303f  mov     [rsp+88h+phNewToken], rax; unsigned __int16 *
0x180113044  mov     qword ptr [rsp+88h+TokenType], rax; unsigned __int16 *
0x180113049  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18011304e  mov     eax, 641h
0x180113053  jmp     short loc_180113067
0x180113055  mov     rcx, [rdi]; void *
0x180113058  call    ?IsTokenOnTerminalServerConsole@@YA_NPEAX@Z; IsTokenOnTerminalServerConsole(void *)
0x18011305d  xor     al, 1
0x18011305f  mov     [rbx+132h], al
0x180113065  xor     eax, eax
0x180113067  add     rsp, 68h
0x18011306b  pop     rdi
0x18011306c  pop     rsi
0x18011306d  pop     rbp
0x18011306e  pop     rbx
0x18011306f  retn
0x180113070  test    eax, eax
0x180113072  jnz     short loc_180113065
0x180113074  call    ?RunningAsLocalSystem@@YA?AW4TRI@@XZ; RunningAsLocalSystem(void)
0x180113079  cmp     eax, 1
0x18011307c  jnz     loc_180113155
0x180113082  call    cs:__imp_GetCurrentThread
0x180113088  mov     edx, 0Fh; DesiredAccess
0x18011308d  mov     r9, rdi; TokenHandle
0x180113090  mov     rcx, rax; ThreadHandle
0x180113093  lea     r8d, [rdx-0Eh]; OpenAsSelf
0x180113097  call    cs:__imp_OpenThreadToken
0x18011309d  test    eax, eax
0x18011309f  jnz     short loc_18011310A
0x1801130a1  call    cs:__imp_GetLastError
0x1801130a7  cmp     cs:?g_dmDiagnosticMode@@3HA, ebp; int g_dmDiagnosticMode
0x1801130ad  mov     ebx, eax
0x1801130af  jz      short loc_1801130F3
0x1801130b1  mov     [rsp+88h+var_30], rbp; void *
0x1801130b6  lea     rax, aNull; "(NULL)"
0x1801130bd  mov     [rsp+88h+var_38], ebp; unsigned int
0x1801130c1  lea     r9, aFailedToOpenTh; "Failed to open thread token (error %d):"...
0x1801130c8  mov     [rsp+88h+var_40], rax; unsigned __int16 *
0x1801130cd  xor     edx, edx; unsigned __int16
0x1801130cf  mov     [rsp+88h+var_48], rax; unsigned __int16 *
0x1801130d4  xor     r8d, r8d; int
0x1801130d7  mov     [rsp+88h+var_50], rax; unsigned __int16 *
0x1801130dc  mov     [rsp+88h+var_58], rax; unsigned __int16 *
0x1801130e1  mov     [rsp+88h+phNewToken], rax; unsigned __int16 *
0x1801130e6  lea     ecx, [rdx+0Ah]; int
0x1801130e9  mov     qword ptr [rsp+88h+TokenType], rbx; unsigned __int16 *
0x1801130ee  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1801130f3  sub     ebx, 3F0h
0x1801130f9  mov     [rdi], rbp
0x1801130fc  neg     ebx
0x1801130fe  sbb     eax, eax
0x180113100  and     eax, 65Fh
0x180113105  jmp     loc_180113067
0x18011310a  cmp     cs:?g_dmDiagnosticMode@@3HA, ebp; int g_dmDiagnosticMode
0x180113110  jz      short loc_18011314B
0x180113112  lea     rax, aNull_0; "(NULL)"
0x180113119  xor     edx, edx; unsigned __int16
0x18011311b  mov     [rsp+88h+var_40], rax; char *
0x180113120  lea     r9, aOpenedThreadTo; "Opened thread token: we're impersonated"
0x180113127  mov     [rsp+88h+var_48], rax; char *
0x18011312c  xor     r8d, r8d; int
0x18011312f  mov     [rsp+88h+var_50], rax; char *
0x180113134  mov     [rsp+88h+var_58], rax; char *
0x180113139  lea     ecx, [rdx+0Ah]; int
0x18011313c  mov     [rsp+88h+phNewToken], rax; char *
0x180113141  mov     qword ptr [rsp+88h+TokenType], rax; char *
0x180113146  call    ?DebugString@@YAXHGHPEBD000000KPEAX@Z; DebugString(int,ushort,int,char const *,char const *,char const *,char const *,char const *,char const *,char const *,ulong,void *)
0x18011314b  call    ?SetEngineInitialImpersonationCount@@YAXXZ; SetEngineInitialImpersonationCount(void)
0x180113150  jmp     loc_180113065
0x180113155  cmp     eax, 0FFFFFFFFh
0x180113158  jnz     loc_180113065
0x18011315e  cmp     cs:?g_dmDiagnosticMode@@3HA, ebp; int g_dmDiagnosticMode
0x180113164  jz      short loc_1801131A8
0x180113166  mov     [rsp+88h+var_30], rbp; void *
0x18011316b  lea     rax, aNull; "(NULL)"
0x180113172  mov     [rsp+88h+var_38], ebp; unsigned int
0x180113176  lea     r9, aFailedToDeterm; "Failed to determine if we are impersona"...
0x18011317d  mov     [rsp+88h+var_40], rax; unsigned __int16 *
0x180113182  xor     edx, edx; unsigned __int16
0x180113184  mov     [rsp+88h+var_48], rax; unsigned __int16 *
0x180113189  xor     r8d, r8d; int
0x18011318c  mov     [rsp+88h+var_50], rax; unsigned __int16 *
0x180113191  mov     [rsp+88h+var_58], rax; unsigned __int16 *
0x180113196  mov     [rsp+88h+phNewToken], rax; unsigned __int16 *
0x18011319b  lea     ecx, [rdx+0Ah]; int
0x18011319e  mov     qword ptr [rsp+88h+TokenType], rax; unsigned __int16 *
0x1801131a3  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1801131a8  mov     [rdi], rbp
0x1801131ab  mov     eax, 65Fh
0x1801131b0  jmp     loc_180113067
```
