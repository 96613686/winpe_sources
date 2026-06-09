# _ImpersonateToken

- ea: `0x18001f054`
- end: `0x18001f0fa`
- name: `_ImpersonateToken`
- size: `166`
- prototype: `__int64 __fastcall(HANDLE Token, _QWORD *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001f480`

## callees

- `0x180005900`
- `0x18001f054`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001f0c2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001f0c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f095`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f0ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f095`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f0ba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001f072`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001f072`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001f08b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001f08b`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001f0b0`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001f0b0`

## pseudocode

```c
__int64 __fastcall ImpersonateToken(HANDLE Token, _QWORD *a2)
{
  HANDLE CurrentThread; // rax
  unsigned int v5; // ebx
  DWORD LastError; // eax
  void *v7; // rax
  void *TokenHandle; // [rsp+38h] [rbp+10h] BYREF

  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  v5 = 1;
  if ( OpenThreadToken(CurrentThread, 0xCu, 1, &TokenHandle)
    || (LastError = GetLastError(), TokenHandle = 0, LastError == 1008) )
  {
    if ( SetThreadToken(0, Token) )
    {
      v7 = TokenHandle;
      goto LABEL_9;
    }
    LastError = GetLastError();
  }
  SetLastError(LastError);
  v7 = TokenHandle;
  if ( TokenHandle )
  {
    I_UrlCacheCloseHandle(TokenHandle);
    v7 = 0;
  }
  v5 = 0;
LABEL_9:
  *a2 = v7;
  return v5;
}

```

## disassembly

```asm
0x18001f054  mov     [rsp+arg_0], rbx
0x18001f059  mov     [rsp+arg_10], rsi
0x18001f05e  push    rdi
0x18001f05f  sub     rsp, 20h
0x18001f063  mov     rdi, rdx
0x18001f066  mov     [rsp+28h+TokenHandle], 0
0x18001f06f  mov     rsi, rcx
0x18001f072  call    cs:__imp_GetCurrentThread
0x18001f078  mov     ebx, 1
0x18001f07d  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x18001f082  mov     rcx, rax; ThreadHandle
0x18001f085  mov     r8d, ebx; OpenAsSelf
0x18001f088  lea     edx, [rbx+0Bh]; DesiredAccess
0x18001f08b  call    cs:__imp_OpenThreadToken
0x18001f091  test    eax, eax
0x18001f093  jnz     short loc_18001F0AB
0x18001f095  call    cs:__imp_GetLastError
0x18001f09b  mov     [rsp+28h+TokenHandle], 0
0x18001f0a4  cmp     eax, 3F0h
0x18001f0a9  jnz     short loc_18001F0C0
0x18001f0ab  mov     rdx, rsi; Token
0x18001f0ae  xor     ecx, ecx; Thread
0x18001f0b0  call    cs:__imp_SetThreadToken
0x18001f0b6  test    eax, eax
0x18001f0b8  jnz     short loc_18001F0E0
0x18001f0ba  call    cs:__imp_GetLastError
0x18001f0c0  mov     ecx, eax; dwErrCode
0x18001f0c2  call    cs:__imp_SetLastError
0x18001f0c8  mov     rax, [rsp+28h+TokenHandle]
0x18001f0cd  test    rax, rax
0x18001f0d0  jz      short loc_18001F0DC
0x18001f0d2  mov     rcx, rax; hObject
0x18001f0d5  call    I_UrlCacheCloseHandle
0x18001f0da  xor     eax, eax
0x18001f0dc  xor     ebx, ebx
0x18001f0de  jmp     short loc_18001F0E5
0x18001f0e0  mov     rax, [rsp+28h+TokenHandle]
0x18001f0e5  mov     rsi, [rsp+28h+arg_10]
0x18001f0ea  mov     [rdi], rax
0x18001f0ed  mov     eax, ebx
0x18001f0ef  mov     rbx, [rsp+28h+arg_0]
0x18001f0f4  add     rsp, 20h
0x18001f0f8  pop     rdi
0x18001f0f9  retn
```
