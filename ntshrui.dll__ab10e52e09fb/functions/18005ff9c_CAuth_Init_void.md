# CAuth::_Init(void)

- ea: `0x18005ff9c`
- end: `0x18006004a`
- name: `?_Init@CAuth@@AEAAJXZ`
- size: `174`
- prototype: `__int64 __fastcall(PHANDLE DuplicateTokenHandle)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18005eb28`

## callees

- `0x1800098dc`
- `0x18005ff9c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ffd1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005ffd1`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18005ffc7`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18005ffc7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005ffb5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005ffb5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005ffe3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005ffe3`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18005fff4`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18005fff4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006001f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006001f`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x180060009`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x180060009`

## pseudocode

```c
__int64 __fastcall CAuth::_Init(PHANDLE DuplicateTokenHandle)
{
  unsigned int Error; // ebx
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  HANDLE CurrentProcess; // rax
  void *TokenHandle; // [rsp+30h] [rbp+8h] BYREF

  Error = 0;
  if ( *DuplicateTokenHandle != (void *)-1LL )
    return Error;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 0, DuplicateTokenHandle) )
    return Error;
  LastError = GetLastError();
  if ( LastError != 1008 )
  {
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
    return (unsigned int)LastError;
  }
  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 2u, &TokenHandle) )
    return (unsigned int)ResultFromKnownLastError();
  if ( !DuplicateToken(TokenHandle, SecurityImpersonation, DuplicateTokenHandle) )
    Error = ResultFromKnownLastError();
  CloseHandle(TokenHandle);
  return Error;
}

```

## disassembly

```asm
0x18005ff9c  mov     [rsp+arg_8], rbx
0x18005ffa1  push    rdi
0x18005ffa2  sub     rsp, 20h
0x18005ffa6  xor     ebx, ebx
0x18005ffa8  mov     rdi, rcx
0x18005ffab  cmp     qword ptr [rcx], 0FFFFFFFFFFFFFFFFh
0x18005ffaf  jnz     loc_18006003D
0x18005ffb5  call    cs:__imp_GetCurrentThread
0x18005ffbb  mov     r9, rdi; TokenHandle
0x18005ffbe  lea     edx, [rbx+8]; DesiredAccess
0x18005ffc1  mov     rcx, rax; ThreadHandle
0x18005ffc4  xor     r8d, r8d; OpenAsSelf
0x18005ffc7  call    cs:__imp_OpenThreadToken
0x18005ffcd  test    eax, eax
0x18005ffcf  jnz     short loc_18006003D
0x18005ffd1  call    cs:__imp_GetLastError
0x18005ffd7  cmp     eax, 3F0h
0x18005ffdc  jnz     short loc_180060030
0x18005ffde  mov     [rsp+28h+TokenHandle], rbx
0x18005ffe3  call    cs:__imp_GetCurrentProcess
0x18005ffe9  mov     rcx, rax; ProcessHandle
0x18005ffec  lea     r8, [rsp+28h+TokenHandle]; TokenHandle
0x18005fff1  lea     edx, [rbx+2]; DesiredAccess
0x18005fff4  call    cs:__imp_OpenProcessToken
0x18005fffa  test    eax, eax
0x18005fffc  jz      short loc_180060027
0x18005fffe  mov     rcx, [rsp+28h+TokenHandle]; ExistingTokenHandle
0x180060003  lea     edx, [rbx+2]; ImpersonationLevel
0x180060006  mov     r8, rdi; DuplicateTokenHandle
0x180060009  call    cs:__imp_DuplicateToken
0x18006000f  test    eax, eax
0x180060011  jnz     short loc_18006001A
0x180060013  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180060018  mov     ebx, eax
0x18006001a  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x18006001f  call    cs:__imp_CloseHandle
0x180060025  jmp     short loc_18006003D
0x180060027  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18006002c  mov     ebx, eax
0x18006002e  jmp     short loc_18006003D
0x180060030  test    eax, eax
0x180060032  jle     short loc_18006002C
0x180060034  movzx   ebx, ax
0x180060037  or      ebx, 80070000h
0x18006003d  mov     eax, ebx
0x18006003f  mov     rbx, [rsp+28h+arg_8]
0x180060044  add     rsp, 20h
0x180060048  pop     rdi
0x180060049  retn
```
