# _OpenCallerToken

- ea: `0x18000875c`
- end: `0x180008852`
- name: `_OpenCallerToken`
- size: `246`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800081ec`
- `0x180008690`

## callees

- `0x18000875c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800087c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000883a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800087c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000883a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800087d0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800087d0`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180008789`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180008789`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800087e3`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800087e3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180008772`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180008772`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000882a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008847`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000882a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180008847`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18000881b`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18000881b`

## pseudocode

```c
__int64 __fastcall OpenCallerToken(__int64 a1, _QWORD *a2)
{
  HANDLE CurrentThread; // rax
  void *v4; // rax
  DWORD LastError; // ebx
  HANDLE CurrentProcess; // rax
  void *TokenHandle; // [rsp+50h] [rbp+18h] BYREF
  void *phNewToken; // [rsp+58h] [rbp+20h] BYREF

  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    v4 = TokenHandle;
LABEL_3:
    *a2 = v4;
    LastError = 0;
    TokenHandle = 0;
    goto LABEL_4;
  }
  LastError = GetLastError();
  if ( LastError == 1008 )
  {
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 0xAu, &TokenHandle) )
    {
      phNewToken = 0;
      if ( DuplicateTokenEx(TokenHandle, 0x2000000u, 0, SecurityIdentification, TokenImpersonation, &phNewToken) )
      {
        CloseHandle(TokenHandle);
        v4 = phNewToken;
        goto LABEL_3;
      }
    }
    LastError = GetLastError();
  }
LABEL_4:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return LastError;
}

```

## disassembly

```asm
0x18000875c  mov     [rsp+arg_0], rbx
0x180008761  push    rdi
0x180008762  sub     rsp, 30h
0x180008766  mov     rdi, rdx
0x180008769  mov     [rsp+38h+TokenHandle], 0
0x180008772  call    cs:__imp_GetCurrentThread
0x180008778  mov     edx, 8; DesiredAccess
0x18000877d  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x180008782  mov     rcx, rax; ThreadHandle
0x180008785  lea     r8d, [rdx-7]; OpenAsSelf
0x180008789  call    cs:__imp_OpenThreadToken
0x18000878f  test    eax, eax
0x180008791  jz      short loc_1800087C1
0x180008793  mov     rax, [rsp+38h+TokenHandle]
0x180008798  mov     [rdi], rax
0x18000879b  xor     ebx, ebx
0x18000879d  mov     [rsp+38h+TokenHandle], 0
0x1800087a6  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x1800087ab  test    rcx, rcx
0x1800087ae  jnz     loc_180008847
0x1800087b4  mov     eax, ebx
0x1800087b6  mov     rbx, [rsp+38h+arg_0]
0x1800087bb  add     rsp, 30h
0x1800087bf  pop     rdi
0x1800087c0  retn
0x1800087c1  call    cs:__imp_GetLastError
0x1800087c7  mov     ebx, eax
0x1800087c9  cmp     eax, 3F0h
0x1800087ce  jnz     short loc_1800087A6
0x1800087d0  call    cs:__imp_GetCurrentProcess
0x1800087d6  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x1800087db  mov     edx, 0Ah; DesiredAccess
0x1800087e0  mov     rcx, rax; ProcessHandle
0x1800087e3  call    cs:__imp_OpenProcessToken
0x1800087e9  test    eax, eax
0x1800087eb  jz      short loc_18000883A
0x1800087ed  mov     rcx, [rsp+38h+TokenHandle]; hExistingToken
0x1800087f2  lea     rax, [rsp+38h+arg_18]
0x1800087f7  mov     [rsp+38h+phNewToken], rax; phNewToken
0x1800087fc  mov     r9d, 1; ImpersonationLevel
0x180008802  xor     r8d, r8d; lpTokenAttributes
0x180008805  mov     [rsp+38h+TokenType], 2; TokenType
0x18000880d  mov     edx, 2000000h; dwDesiredAccess
0x180008812  mov     [rsp+38h+arg_18], 0
0x18000881b  call    cs:__imp_DuplicateTokenEx
0x180008821  test    eax, eax
0x180008823  jz      short loc_18000883A
0x180008825  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x18000882a  call    cs:__imp_CloseHandle
0x180008830  mov     rax, [rsp+38h+arg_18]
0x180008835  jmp     loc_180008798
0x18000883a  call    cs:__imp_GetLastError
0x180008840  mov     ebx, eax
0x180008842  jmp     loc_1800087A6
0x180008847  call    cs:__imp_CloseHandle
0x18000884d  jmp     loc_1800087B4
```
