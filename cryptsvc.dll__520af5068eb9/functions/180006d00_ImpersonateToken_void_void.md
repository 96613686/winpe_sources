# ImpersonateToken(void *,void * *)

- ea: `0x180006d00`
- end: `0x180006da1`
- name: `?ImpersonateToken@@YAHPEAXPEAPEAX@Z`
- size: `161`
- prototype: `__int64 __fastcall(HANDLE Token, void **)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180005700`
- `0x180006aa0`
- `0x18000fe44`

## callees

- `0x180004180`
- `0x180006d00`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006d3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006d7d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006d3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006d7d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006d85`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006d85`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180006d35`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180006d35`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180006d56`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180006d56`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180006d1c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180006d1c`

## pseudocode

```c
__int64 __fastcall ImpersonateToken(HANDLE Token, void **a2)
{
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  void *v6; // rcx
  __int64 result; // rax
  void *TokenHandle; // [rsp+38h] [rbp+10h] BYREF

  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0xCu, 1, &TokenHandle)
    || (LastError = GetLastError(), TokenHandle = 0, LastError == 1008) )
  {
    if ( SetThreadToken(0, Token) )
    {
      v6 = TokenHandle;
      result = 1;
      goto LABEL_5;
    }
    LastError = GetLastError();
  }
  SetLastError(LastError);
  v6 = TokenHandle;
  if ( TokenHandle )
  {
    I_UrlCacheCloseHandle(TokenHandle);
    v6 = 0;
  }
  result = 0;
LABEL_5:
  *a2 = v6;
  return result;
}

```

## disassembly

```asm
0x180006d00  mov     [rsp+arg_0], rbx
0x180006d05  mov     [rsp+arg_10], rsi
0x180006d0a  push    rdi
0x180006d0b  sub     rsp, 20h
0x180006d0f  xor     esi, esi
0x180006d11  mov     rbx, rdx
0x180006d14  mov     [rsp+28h+TokenHandle], rsi
0x180006d19  mov     rdi, rcx
0x180006d1c  call    cs:__imp_GetCurrentThread
0x180006d22  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x180006d27  mov     edx, 0Ch; DesiredAccess
0x180006d2c  mov     rcx, rax; ThreadHandle
0x180006d2f  mov     r8d, 1; OpenAsSelf
0x180006d35  call    cs:__imp_OpenThreadToken
0x180006d3b  test    eax, eax
0x180006d3d  jnz     short loc_180006D51
0x180006d3f  call    cs:__imp_GetLastError
0x180006d45  mov     [rsp+28h+TokenHandle], rsi
0x180006d4a  cmp     eax, 3F0h
0x180006d4f  jnz     short loc_180006D83
0x180006d51  mov     rdx, rdi; Token
0x180006d54  xor     ecx, ecx; Thread
0x180006d56  call    cs:__imp_SetThreadToken
0x180006d5c  test    eax, eax
0x180006d5e  jz      short loc_180006D7D
0x180006d60  mov     rcx, [rsp+28h+TokenHandle]
0x180006d65  mov     eax, 1
0x180006d6a  mov     [rbx], rcx
0x180006d6d  mov     rbx, [rsp+28h+arg_0]
0x180006d72  mov     rsi, [rsp+28h+arg_10]
0x180006d77  add     rsp, 20h
0x180006d7b  pop     rdi
0x180006d7c  retn
0x180006d7d  call    cs:__imp_GetLastError
0x180006d83  mov     ecx, eax; dwErrCode
0x180006d85  call    cs:__imp_SetLastError
0x180006d8b  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x180006d90  test    rcx, rcx
0x180006d93  jz      short loc_180006D9D
0x180006d95  call    I_UrlCacheCloseHandle
0x180006d9a  mov     rcx, rsi
0x180006d9d  mov     eax, esi
0x180006d9f  jmp     short loc_180006D6A
```
