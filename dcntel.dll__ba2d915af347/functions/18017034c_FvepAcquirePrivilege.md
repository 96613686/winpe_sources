# FvepAcquirePrivilege

- ea: `0x18017034c`
- end: `0x1801704b2`
- name: `FvepAcquirePrivilege`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1801704b8`

## callees

- `0x180008dc0`
- `0x18017034c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801703ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801703d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180170421`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801703ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801703d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180170421`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1801703bc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1801703bc`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180170467`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180170467`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1801703cb`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1801703cb`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1801703a3`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1801703a3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180170390`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180170390`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180170485`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180170495`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180170485`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180170495`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180170417`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180170417`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180170457`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x180170457`

## pseudocode

```c
__int64 __fastcall FvepAcquirePrivilege(__int64 a1, _QWORD *a2)
{
  HANDLE CurrentThread; // rax
  void *v4; // rdi
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  unsigned int v7; // ebx
  void *v8; // rcx
  signed int v9; // eax
  void *TokenHandle; // [rsp+30h] [rbp-38h] BYREF
  HANDLE Token; // [rsp+38h] [rbp-30h] BYREF
  _TOKEN_PRIVILEGES NewState; // [rsp+40h] [rbp-28h] BYREF

  TokenHandle = (void *)-1LL;
  NewState.Privileges[0].Attributes = 2;
  Token = (HANDLE)-1LL;
  NewState.PrivilegeCount = 1;
  NewState.Privileges[0].Luid = (LUID)17LL;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 6u, 0, &TokenHandle) )
  {
    v8 = TokenHandle;
    v4 = TokenHandle;
  }
  else
  {
    if ( GetLastError() != 1008
      || (v4 = 0, CurrentProcess = GetCurrentProcess(), !OpenProcessToken(CurrentProcess, 2u, &TokenHandle)) )
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
LABEL_15:
      if ( TokenHandle != (void *)-1LL )
        CloseHandle(TokenHandle);
      goto LABEL_17;
    }
    v8 = TokenHandle;
  }
  if ( DuplicateTokenEx(v8, 0x2Cu, 0, SecurityImpersonation, TokenImpersonation, &Token)
    && AdjustTokenPrivileges(Token, 0, &NewState, 0, 0, 0)
    && SetThreadToken(0, Token) )
  {
    v7 = 0;
    *a2 = v4;
  }
  else
  {
    v9 = GetLastError();
    v7 = v9;
    if ( v9 > 0 )
      v7 = (unsigned __int16)v9 | 0x80070000;
  }
  if ( !v4 )
    goto LABEL_15;
LABEL_17:
  if ( Token != (HANDLE)-1LL )
    CloseHandle(Token);
  return v7;
}

```

## disassembly

```asm
0x18017034c  push    rbp
0x18017034e  push    rbx
0x18017034f  push    rsi
0x180170350  push    rdi
0x180170351  mov     rbp, rsp
0x180170354  sub     rsp, 68h
0x180170358  mov     rax, cs:__security_cookie
0x18017035f  xor     rax, rsp
0x180170362  mov     [rbp+var_18], rax
0x180170366  mov     ebx, 2
0x18017036b  mov     [rbp+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x180170373  mov     [rbp+NewState.Privileges.Attributes], ebx
0x180170376  mov     rsi, rdx
0x180170379  mov     [rbp+Token], 0FFFFFFFFFFFFFFFFh
0x180170381  mov     [rbp+NewState.PrivilegeCount], 1
0x180170388  mov     qword ptr [rbp+NewState.Privileges.Luid.LowPart], 11h
0x180170390  call    cs:__imp_GetCurrentThread
0x180170396  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18017039a  xor     r8d, r8d; OpenAsSelf
0x18017039d  mov     rcx, rax; ThreadHandle
0x1801703a0  lea     edx, [rbx+4]; DesiredAccess
0x1801703a3  call    cs:__imp_OpenThreadToken
0x1801703a9  test    eax, eax
0x1801703ab  jnz     short loc_1801703F9
0x1801703ad  call    cs:__imp_GetLastError
0x1801703b3  cmp     eax, 3F0h
0x1801703b8  jnz     short loc_1801703D5
0x1801703ba  xor     edi, edi
0x1801703bc  call    cs:__imp_GetCurrentProcess
0x1801703c2  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1801703c6  mov     edx, ebx; DesiredAccess
0x1801703c8  mov     rcx, rax; ProcessHandle
0x1801703cb  call    cs:__imp_OpenProcessToken
0x1801703d1  test    eax, eax
0x1801703d3  jnz     short loc_1801703F3
0x1801703d5  call    cs:__imp_GetLastError
0x1801703db  mov     ebx, eax
0x1801703dd  test    eax, eax
0x1801703df  jle     loc_18017047B
0x1801703e5  movzx   ebx, ax
0x1801703e8  or      ebx, 80070000h
0x1801703ee  jmp     loc_18017047B
0x1801703f3  mov     rcx, [rbp+TokenHandle]
0x1801703f7  jmp     short loc_180170400
0x1801703f9  mov     rcx, [rbp+TokenHandle]; hExistingToken
0x1801703fd  mov     rdi, rcx
0x180170400  xor     r8d, r8d; lpTokenAttributes
0x180170403  lea     rax, [rbp+Token]
0x180170407  mov     [rsp+68h+phNewToken], rax; phNewToken
0x18017040c  mov     r9d, ebx; ImpersonationLevel
0x18017040f  mov     [rsp+68h+TokenType], ebx; TokenType
0x180170413  lea     edx, [r8+2Ch]; dwDesiredAccess
0x180170417  call    cs:__imp_DuplicateTokenEx
0x18017041d  test    eax, eax
0x18017041f  jnz     short loc_180170438
0x180170421  call    cs:__imp_GetLastError
0x180170427  mov     ebx, eax
0x180170429  test    eax, eax
0x18017042b  jle     short loc_180170476
0x18017042d  movzx   ebx, ax
0x180170430  or      ebx, 80070000h
0x180170436  jmp     short loc_180170476
0x180170438  mov     rcx, [rbp+Token]; TokenHandle
0x18017043c  lea     r8, [rbp+NewState]; NewState
0x180170440  mov     [rsp+68h+phNewToken], 0; ReturnLength
0x180170449  xor     r9d, r9d; BufferLength
0x18017044c  xor     edx, edx; DisableAllPrivileges
0x18017044e  mov     qword ptr [rsp+68h+TokenType], 0; PreviousState
0x180170457  call    cs:__imp_AdjustTokenPrivileges
0x18017045d  test    eax, eax
0x18017045f  jz      short loc_180170421
0x180170461  mov     rdx, [rbp+Token]; Token
0x180170465  xor     ecx, ecx; Thread
0x180170467  call    cs:__imp_SetThreadToken
0x18017046d  test    eax, eax
0x18017046f  jz      short loc_180170421
0x180170471  xor     ebx, ebx
0x180170473  mov     [rsi], rdi
0x180170476  test    rdi, rdi
0x180170479  jnz     short loc_18017048B
0x18017047b  mov     rcx, [rbp+TokenHandle]; hObject
0x18017047f  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180170483  jz      short loc_18017048B
0x180170485  call    cs:__imp_CloseHandle
0x18017048b  mov     rcx, [rbp+Token]; hObject
0x18017048f  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180170493  jz      short loc_18017049B
0x180170495  call    cs:__imp_CloseHandle
0x18017049b  mov     eax, ebx
0x18017049d  mov     rcx, [rbp+var_18]
0x1801704a1  xor     rcx, rsp; StackCookie
0x1801704a4  call    __security_check_cookie
0x1801704a9  add     rsp, 68h
0x1801704ad  pop     rdi
0x1801704ae  pop     rsi
0x1801704af  pop     rbx
0x1801704b0  pop     rbp
0x1801704b1  retn
```
