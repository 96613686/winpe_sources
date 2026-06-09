# ScopedPrivilege::AcquirePrivilege(long)

- ea: `0x18002b970`
- end: `0x18002bc1e`
- name: `?AcquirePrivilege@ScopedPrivilege@@QEAAJJ@Z`
- size: `686`
- prototype: `__int64 __fastcall(ScopedPrivilege *this)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180032844`

## callees

- `0x180003270`
- `0x180009c44`
- `0x180009c64`
- `0x18002b970`
- `0x18002d15c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ba67`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002ba67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b9db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ba48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bb7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b9db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ba48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bb7e`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002ba93`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18002ba93`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18002bbb4`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18002bbb4`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002b9c7`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002b9c7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002b9ad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002b9ad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002ba7b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002ba7b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ba27`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ba59`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002bb24`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002bbe0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002bbfa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ba27`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002ba59`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002bb24`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002bbe0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002bbfa`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18002bb67`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18002bb67`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18002baeb`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18002baeb`

## string_xrefs

- `0x18002bb8e`: `AdjustTokenPrivileges non-fatal error`

## pseudocode

```c
// Hidden C++ exception states: #wind=54
__int64 __fastcall ScopedPrivilege::AcquirePrivilege(ScopedPrivilege *this)
{
  char v2; // bl
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  unsigned int v5; // ebx
  void *v7; // rdi
  DWORD v8; // ebx
  HANDLE CurrentProcess; // rax
  const char *v10; // r9
  const char *v11; // r9
  __int64 v12; // rdx
  DWORD v13; // eax
  char *v14; // rcx
  int TokenType; // [rsp+20h] [rbp-48h]
  const char *phNewToken; // [rsp+28h] [rbp-40h]
  void *TokenHandle; // [rsp+30h] [rbp-38h] BYREF
  HANDLE hObject; // [rsp+38h] [rbp-30h] BYREF
  _TOKEN_PRIVILEGES NewState; // [rsp+40h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+20h]

  NewState.PrivilegeCount = 1;
  NewState.Privileges[0].Attributes = 2;
  v2 = 0;
  NewState.Privileges[0].Luid = (LUID)22LL;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 6u, 0, &TokenHandle) )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError != 1008 )
    {
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      if ( (v5 & 0x80000000) != 0 )
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xE1,
          (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.cpp",
          (const char *)v5,
          TokenType);
      goto LABEL_7;
    }
    v7 = TokenHandle;
    if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      v8 = GetLastError();
      CloseHandle(v7);
      SetLastError(v8);
    }
    TokenHandle = 0;
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 2u, &TokenHandle) )
    {
      v5 = wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0xE2,
             (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.cpp",
             v10);
LABEL_7:
      if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        CloseHandle(TokenHandle);
      return v5;
    }
    v2 = 1;
  }
  hObject = 0;
  if ( !DuplicateTokenEx(TokenHandle, 0x2Cu, 0, SecurityImpersonation, TokenImpersonation, &hObject) )
  {
    v12 = 233;
    goto LABEL_17;
  }
  if ( !v2 )
  {
    *(_QWORD *)this = TokenHandle;
    TokenHandle = 0;
  }
  if ( !AdjustTokenPrivileges(hObject, 0, &NewState, 0, 0, 0) )
  {
    v12 = 241;
    goto LABEL_17;
  }
  v13 = GetLastError();
  wil::details::in1diag3::Log_IfWin32ErrorMsg(
    retaddr,
    (void *)0xF4,
    (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.cpp",
    (const char *)v13,
    (unsigned int)"AdjustTokenPrivileges non-fatal error",
    phNewToken);
  if ( !SetThreadToken(0, hObject) )
  {
    v12 = 246;
LABEL_17:
    v5 = wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)v12,
           (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.cpp",
           v11);
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      CloseHandle(hObject);
    goto LABEL_7;
  }
  v14 = (char *)hObject;
  *((_BYTE *)this + 8) = 1;
  if ( (unsigned __int64)(v14 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v14);
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(TokenHandle);
  return 0;
}

```

## disassembly

```asm
0x18002b970  push    rbp
0x18002b972  push    rbx
0x18002b973  push    rsi
0x18002b974  push    rdi
0x18002b975  mov     rbp, rsp
0x18002b978  sub     rsp, 68h
0x18002b97c  mov     rax, cs:__security_cookie
0x18002b983  xor     rax, rsp
0x18002b986  mov     [rbp+var_18], rax
0x18002b98a  mov     rsi, rcx
0x18002b98d  mov     [rbp+NewState.PrivilegeCount], 1
0x18002b994  mov     [rbp+NewState.Privileges.Attributes], 2
0x18002b99b  xor     bl, bl
0x18002b99d  mov     qword ptr [rbp+NewState.Privileges.Luid.LowPart], 16h
0x18002b9a5  mov     [rbp+TokenHandle], 0
0x18002b9ad  call    cs:__imp_GetCurrentThread
0x18002b9b4  nop     dword ptr [rax+rax+00h]
0x18002b9b9  xor     r8d, r8d; OpenAsSelf
0x18002b9bc  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18002b9c0  mov     rcx, rax; ThreadHandle
0x18002b9c3  lea     edx, [r8+6]; DesiredAccess
0x18002b9c7  call    cs:__imp_OpenThreadToken
0x18002b9ce  nop     dword ptr [rax+rax+00h]
0x18002b9d3  test    eax, eax
0x18002b9d5  jnz     loc_18002BAC1
0x18002b9db  call    cs:__imp_GetLastError
0x18002b9e2  nop     dword ptr [rax+rax+00h]
0x18002b9e7  mov     ebx, eax
0x18002b9e9  cmp     eax, 3F0h
0x18002b9ee  jz      short loc_18002BA3A
0x18002b9f0  test    eax, eax
0x18002b9f2  jle     short loc_18002B9FD
0x18002b9f4  movzx   ebx, ax
0x18002b9f7  or      ebx, 80070000h
0x18002b9fd  test    ebx, ebx
0x18002b9ff  jns     short loc_18002BA19
0x18002ba01  mov     rcx, [rbp+20h]; this
0x18002ba05  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18002ba0c  mov     r9d, ebx; char *
0x18002ba0f  mov     edx, 0E1h; void *
0x18002ba14  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ba19  mov     rcx, [rbp+TokenHandle]; hObject
0x18002ba1d  lea     rdx, [rcx-1]
0x18002ba21  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18002ba25  ja      short loc_18002BA33
0x18002ba27  call    cs:__imp_CloseHandle
0x18002ba2e  nop     dword ptr [rax+rax+00h]
0x18002ba33  mov     eax, ebx
0x18002ba35  jmp     loc_18002BC08
0x18002ba3a  mov     rdi, [rbp+TokenHandle]
0x18002ba3e  lea     rax, [rdi-1]
0x18002ba42  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002ba46  ja      short loc_18002BA73
0x18002ba48  call    cs:__imp_GetLastError
0x18002ba4f  nop     dword ptr [rax+rax+00h]
0x18002ba54  mov     rcx, rdi; hObject
0x18002ba57  mov     ebx, eax
0x18002ba59  call    cs:__imp_CloseHandle
0x18002ba60  nop     dword ptr [rax+rax+00h]
0x18002ba65  mov     ecx, ebx; dwErrCode
0x18002ba67  call    cs:__imp_SetLastError
0x18002ba6e  nop     dword ptr [rax+rax+00h]
0x18002ba73  mov     [rbp+TokenHandle], 0
0x18002ba7b  call    cs:__imp_GetCurrentProcess
0x18002ba82  nop     dword ptr [rax+rax+00h]
0x18002ba87  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18002ba8b  mov     edx, 2; DesiredAccess
0x18002ba90  mov     rcx, rax; ProcessHandle
0x18002ba93  call    cs:__imp_OpenProcessToken
0x18002ba9a  nop     dword ptr [rax+rax+00h]
0x18002ba9f  test    eax, eax
0x18002baa1  jnz     short loc_18002BABF
0x18002baa3  mov     rcx, [rbp+20h]; this
0x18002baa7  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18002baae  mov     edx, 0E2h; void *
0x18002bab3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002bab8  mov     ebx, eax
0x18002baba  jmp     loc_18002BA19
0x18002babf  mov     bl, 1
0x18002bac1  mov     rcx, [rbp+TokenHandle]; hExistingToken
0x18002bac5  lea     rax, [rbp+hObject]
0x18002bac9  mov     r9d, 2; ImpersonationLevel
0x18002bacf  mov     [rsp+68h+phNewToken], rax; phNewToken
0x18002bad4  xor     r8d, r8d; lpTokenAttributes
0x18002bad7  mov     [rbp+hObject], 0
0x18002badf  mov     [rsp+68h+TokenType], 2; TokenType
0x18002bae7  lea     edx, [r9+2Ah]; dwDesiredAccess
0x18002baeb  call    cs:__imp_DuplicateTokenEx
0x18002baf2  nop     dword ptr [rax+rax+00h]
0x18002baf7  test    eax, eax
0x18002baf9  jnz     short loc_18002BB35
0x18002bafb  mov     edx, 0E9h; void *
0x18002bb00  mov     rcx, [rbp+20h]; this
0x18002bb04  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18002bb0b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002bb10  mov     rcx, [rbp+hObject]; hObject
0x18002bb14  mov     ebx, eax
0x18002bb16  lea     rdx, [rcx-1]
0x18002bb1a  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18002bb1e  ja      loc_18002BA19
0x18002bb24  call    cs:__imp_CloseHandle
0x18002bb2b  nop     dword ptr [rax+rax+00h]
0x18002bb30  jmp     loc_18002BA19
0x18002bb35  test    bl, bl
0x18002bb37  jnz     short loc_18002BB48
0x18002bb39  mov     rax, [rbp+TokenHandle]
0x18002bb3d  mov     [rsi], rax
0x18002bb40  mov     [rbp+TokenHandle], 0
0x18002bb48  mov     rcx, [rbp+hObject]; TokenHandle
0x18002bb4c  lea     r8, [rbp+NewState]; NewState
0x18002bb50  mov     [rsp+68h+phNewToken], 0; char *
0x18002bb59  xor     r9d, r9d; BufferLength
0x18002bb5c  xor     edx, edx; DisableAllPrivileges
0x18002bb5e  mov     qword ptr [rsp+68h+TokenType], 0; PreviousState
0x18002bb67  call    cs:__imp_AdjustTokenPrivileges
0x18002bb6e  nop     dword ptr [rax+rax+00h]
0x18002bb73  test    eax, eax
0x18002bb75  jnz     short loc_18002BB7E
0x18002bb77  mov     edx, 0F1h
0x18002bb7c  jmp     short loc_18002BB00
0x18002bb7e  call    cs:__imp_GetLastError
0x18002bb85  nop     dword ptr [rax+rax+00h]
0x18002bb8a  mov     rcx, [rbp+20h]; this
0x18002bb8e  lea     rdx, aAdjusttokenpri; "AdjustTokenPrivileges non-fatal error"
0x18002bb95  mov     qword ptr [rsp+68h+TokenType], rdx; unsigned int
0x18002bb9a  lea     r8, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18002bba1  mov     edx, 0F4h; void *
0x18002bba6  mov     r9d, eax; char *
0x18002bba9  call    ?Log_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Log_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x18002bbae  mov     rdx, [rbp+hObject]; Token
0x18002bbb2  xor     ecx, ecx; Thread
0x18002bbb4  call    cs:__imp_SetThreadToken
0x18002bbbb  nop     dword ptr [rax+rax+00h]
0x18002bbc0  test    eax, eax
0x18002bbc2  jnz     short loc_18002BBCE
0x18002bbc4  mov     edx, 0F6h
0x18002bbc9  jmp     loc_18002BB00
0x18002bbce  mov     rcx, [rbp+hObject]; hObject
0x18002bbd2  mov     byte ptr [rsi+8], 1
0x18002bbd6  lea     rax, [rcx-1]
0x18002bbda  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002bbde  ja      short loc_18002BBEC
0x18002bbe0  call    cs:__imp_CloseHandle
0x18002bbe7  nop     dword ptr [rax+rax+00h]
0x18002bbec  mov     rcx, [rbp+TokenHandle]; hObject
0x18002bbf0  lea     rax, [rcx-1]
0x18002bbf4  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002bbf8  ja      short loc_18002BC06
0x18002bbfa  call    cs:__imp_CloseHandle
0x18002bc01  nop     dword ptr [rax+rax+00h]
0x18002bc06  xor     eax, eax
0x18002bc08  mov     rcx, [rbp+var_18]
0x18002bc0c  xor     rcx, rsp; StackCookie
0x18002bc0f  call    __security_check_cookie
0x18002bc14  add     rsp, 68h
0x18002bc18  pop     rdi
0x18002bc19  pop     rsi
0x18002bc1a  pop     rbx
0x18002bc1b  pop     rbp
0x18002bc1c  retn
```
