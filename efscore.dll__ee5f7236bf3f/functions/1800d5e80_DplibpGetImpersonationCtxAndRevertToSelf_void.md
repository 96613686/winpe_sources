# DplibpGetImpersonationCtxAndRevertToSelf(void * *)

- ea: `0x1800d5e80`
- end: `0x1800d5f39`
- name: `?DplibpGetImpersonationCtxAndRevertToSelf@@YAJPEAPEAX@Z`
- size: `185`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800d5f40`

## callees

- `0x1800d5e80`
- `0x1800dca3c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d5ed6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d5ed6`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800d5ecc`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800d5ecc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800d5eb5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800d5eb5`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800d5efc`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800d5efc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d5f1f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d5f1f`

## pseudocode

```c
__int64 __fastcall DplibpGetImpersonationCtxAndRevertToSelf(void **a1)
{
  signed int v2; // ebx
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  void *v5; // rcx
  __int64 v6; // rcx
  void *TokenHandle; // [rsp+30h] [rbp+8h] BYREF

  TokenHandle = 0;
  if ( !a1 )
    return (unsigned int)-2147467261;
  *a1 = 0;
  if ( NtCurrentTeb()->IsImpersonating )
  {
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 4u, 1, &TokenHandle) )
    {
      v2 = 0;
      if ( !SetThreadToken(0, 0) )
        MicrosoftTelemetryAssertTriggeredNoArgs(v6);
    }
    else
    {
      LastError = GetLastError();
      v2 = LastError;
      if ( LastError > 0 )
        v2 = (unsigned __int16)LastError | 0x80070000;
      if ( v2 < 0 )
      {
        v5 = TokenHandle;
        goto LABEL_12;
      }
    }
  }
  else
  {
    v2 = 1;
  }
  v5 = 0;
  *a1 = TokenHandle;
  TokenHandle = 0;
LABEL_12:
  if ( v5 )
    CloseHandle(v5);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800d5e80  mov     [rsp+arg_8], rbx
0x1800d5e85  push    rdi
0x1800d5e86  sub     rsp, 20h
0x1800d5e8a  mov     [rsp+28h+TokenHandle], 0
0x1800d5e93  mov     rdi, rcx
0x1800d5e96  test    rcx, rcx
0x1800d5e99  jz      loc_1800D5F27
0x1800d5e9f  xor     eax, eax
0x1800d5ea1  mov     [rcx], rax
0x1800d5ea4  mov     eax, gs:179Ch
0x1800d5eac  test    eax, eax
0x1800d5eae  jnz     short loc_1800D5EB5
0x1800d5eb0  lea     ebx, [rax+1]
0x1800d5eb3  jmp     short loc_1800D5F0B
0x1800d5eb5  call    cs:__imp_GetCurrentThread
0x1800d5ebb  mov     edx, 4; DesiredAccess
0x1800d5ec0  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x1800d5ec5  mov     rcx, rax; ThreadHandle
0x1800d5ec8  lea     r8d, [rdx-3]; OpenAsSelf
0x1800d5ecc  call    cs:__imp_OpenThreadToken
0x1800d5ed2  test    eax, eax
0x1800d5ed4  jnz     short loc_1800D5EF6
0x1800d5ed6  call    cs:__imp_GetLastError
0x1800d5edc  mov     ebx, eax
0x1800d5ede  test    eax, eax
0x1800d5ee0  jle     short loc_1800D5EEB
0x1800d5ee2  movzx   ebx, ax
0x1800d5ee5  or      ebx, 80070000h
0x1800d5eeb  test    ebx, ebx
0x1800d5eed  jns     short loc_1800D5F0B
0x1800d5eef  mov     rcx, [rsp+28h+TokenHandle]
0x1800d5ef4  jmp     short loc_1800D5F1A
0x1800d5ef6  xor     edx, edx; Token
0x1800d5ef8  xor     ecx, ecx; Thread
0x1800d5efa  xor     ebx, ebx
0x1800d5efc  call    cs:__imp_SetThreadToken
0x1800d5f02  test    eax, eax
0x1800d5f04  jnz     short loc_1800D5F0B
0x1800d5f06  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "Success != FALSE")
0x1800d5f0b  mov     rax, [rsp+28h+TokenHandle]
0x1800d5f10  xor     ecx, ecx; hObject
0x1800d5f12  mov     [rdi], rax
0x1800d5f15  mov     [rsp+28h+TokenHandle], rcx
0x1800d5f1a  test    rcx, rcx
0x1800d5f1d  jz      short loc_1800D5F2C
0x1800d5f1f  call    cs:__imp_CloseHandle
0x1800d5f25  jmp     short loc_1800D5F2C
0x1800d5f27  mov     ebx, 80004003h
0x1800d5f2c  mov     eax, ebx
0x1800d5f2e  mov     rbx, [rsp+28h+arg_8]
0x1800d5f33  add     rsp, 20h
0x1800d5f37  pop     rdi
0x1800d5f38  retn
```
