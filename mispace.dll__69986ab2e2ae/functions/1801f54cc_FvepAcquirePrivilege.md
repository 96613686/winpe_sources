# FvepAcquirePrivilege

- ea: `0x1801f54cc`
- end: `0x1801f567b`
- name: `FvepAcquirePrivilege`
- size: `431`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1801f5684`

## callees

- `0x180006350`
- `0x1801f54cc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801f5539`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801f5573`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801f55cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801f5539`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801f5573`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801f55cb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1801f554e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1801f554e`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1801f5563`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1801f5563`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1801f5510`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1801f5510`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1801f5529`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1801f5529`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1801f561d`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1801f561d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801f5641`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801f5657`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801f5641`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801f5657`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1801f55bb`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1801f55bb`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x1801f5607`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x1801f5607`

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
0x1801f54cc  push    rbp
0x1801f54ce  push    rbx
0x1801f54cf  push    rsi
0x1801f54d0  push    rdi
0x1801f54d1  mov     rbp, rsp
0x1801f54d4  sub     rsp, 68h
0x1801f54d8  mov     rax, cs:__security_cookie
0x1801f54df  xor     rax, rsp
0x1801f54e2  mov     [rbp+var_18], rax
0x1801f54e6  mov     ebx, 2
0x1801f54eb  mov     [rbp+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x1801f54f3  mov     [rbp+NewState.Privileges.Attributes], ebx
0x1801f54f6  mov     rsi, rdx
0x1801f54f9  mov     [rbp+Token], 0FFFFFFFFFFFFFFFFh
0x1801f5501  mov     [rbp+NewState.PrivilegeCount], 1
0x1801f5508  mov     qword ptr [rbp+NewState.Privileges.Luid.LowPart], 11h
0x1801f5510  call    cs:__imp_GetCurrentThread
0x1801f5517  nop     dword ptr [rax+rax+00h]
0x1801f551c  lea     r9, [rbp+TokenHandle]; TokenHandle
0x1801f5520  xor     r8d, r8d; OpenAsSelf
0x1801f5523  mov     rcx, rax; ThreadHandle
0x1801f5526  lea     edx, [rbx+4]; DesiredAccess
0x1801f5529  call    cs:__imp_OpenThreadToken
0x1801f5530  nop     dword ptr [rax+rax+00h]
0x1801f5535  test    eax, eax
0x1801f5537  jnz     short loc_1801F559D
0x1801f5539  call    cs:__imp_GetLastError
0x1801f5540  nop     dword ptr [rax+rax+00h]
0x1801f5545  cmp     eax, 3F0h
0x1801f554a  jnz     short loc_1801F5573
0x1801f554c  xor     edi, edi
0x1801f554e  call    cs:__imp_GetCurrentProcess
0x1801f5555  nop     dword ptr [rax+rax+00h]
0x1801f555a  lea     r8, [rbp+TokenHandle]; TokenHandle
0x1801f555e  mov     edx, ebx; DesiredAccess
0x1801f5560  mov     rcx, rax; ProcessHandle
0x1801f5563  call    cs:__imp_OpenProcessToken
0x1801f556a  nop     dword ptr [rax+rax+00h]
0x1801f556f  test    eax, eax
0x1801f5571  jnz     short loc_1801F5597
0x1801f5573  call    cs:__imp_GetLastError
0x1801f557a  nop     dword ptr [rax+rax+00h]
0x1801f557f  mov     ebx, eax
0x1801f5581  test    eax, eax
0x1801f5583  jle     loc_1801F5637
0x1801f5589  movzx   ebx, ax
0x1801f558c  or      ebx, 80070000h
0x1801f5592  jmp     loc_1801F5637
0x1801f5597  mov     rcx, [rbp+TokenHandle]
0x1801f559b  jmp     short loc_1801F55A4
0x1801f559d  mov     rcx, [rbp+TokenHandle]; hExistingToken
0x1801f55a1  mov     rdi, rcx
0x1801f55a4  xor     r8d, r8d; lpTokenAttributes
0x1801f55a7  lea     rax, [rbp+Token]
0x1801f55ab  mov     [rsp+68h+phNewToken], rax; phNewToken
0x1801f55b0  mov     r9d, ebx; ImpersonationLevel
0x1801f55b3  mov     [rsp+68h+TokenType], ebx; TokenType
0x1801f55b7  lea     edx, [r8+2Ch]; dwDesiredAccess
0x1801f55bb  call    cs:__imp_DuplicateTokenEx
0x1801f55c2  nop     dword ptr [rax+rax+00h]
0x1801f55c7  test    eax, eax
0x1801f55c9  jnz     short loc_1801F55E8
0x1801f55cb  call    cs:__imp_GetLastError
0x1801f55d2  nop     dword ptr [rax+rax+00h]
0x1801f55d7  mov     ebx, eax
0x1801f55d9  test    eax, eax
0x1801f55db  jle     short loc_1801F5632
0x1801f55dd  movzx   ebx, ax
0x1801f55e0  or      ebx, 80070000h
0x1801f55e6  jmp     short loc_1801F5632
0x1801f55e8  mov     rcx, [rbp+Token]; TokenHandle
0x1801f55ec  lea     r8, [rbp+NewState]; NewState
0x1801f55f0  mov     [rsp+68h+phNewToken], 0; ReturnLength
0x1801f55f9  xor     r9d, r9d; BufferLength
0x1801f55fc  xor     edx, edx; DisableAllPrivileges
0x1801f55fe  mov     qword ptr [rsp+68h+TokenType], 0; PreviousState
0x1801f5607  call    cs:__imp_AdjustTokenPrivileges
0x1801f560e  nop     dword ptr [rax+rax+00h]
0x1801f5613  test    eax, eax
0x1801f5615  jz      short loc_1801F55CB
0x1801f5617  mov     rdx, [rbp+Token]; Token
0x1801f561b  xor     ecx, ecx; Thread
0x1801f561d  call    cs:__imp_SetThreadToken
0x1801f5624  nop     dword ptr [rax+rax+00h]
0x1801f5629  test    eax, eax
0x1801f562b  jz      short loc_1801F55CB
0x1801f562d  xor     ebx, ebx
0x1801f562f  mov     [rsi], rdi
0x1801f5632  test    rdi, rdi
0x1801f5635  jnz     short loc_1801F564D
0x1801f5637  mov     rcx, [rbp+TokenHandle]; hObject
0x1801f563b  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1801f563f  jz      short loc_1801F564D
0x1801f5641  call    cs:__imp_CloseHandle
0x1801f5648  nop     dword ptr [rax+rax+00h]
0x1801f564d  mov     rcx, [rbp+Token]; hObject
0x1801f5651  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1801f5655  jz      short loc_1801F5663
0x1801f5657  call    cs:__imp_CloseHandle
0x1801f565e  nop     dword ptr [rax+rax+00h]
0x1801f5663  mov     eax, ebx
0x1801f5665  mov     rcx, [rbp+var_18]
0x1801f5669  xor     rcx, rsp; StackCookie
0x1801f566c  call    __security_check_cookie
0x1801f5671  add     rsp, 68h
0x1801f5675  pop     rdi
0x1801f5676  pop     rsi
0x1801f5677  pop     rbx
0x1801f5678  pop     rbp
0x1801f5679  retn
```
