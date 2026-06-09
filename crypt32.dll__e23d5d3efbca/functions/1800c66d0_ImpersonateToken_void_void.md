# ImpersonateToken(void *,void * *)

- ea: `0x1800c66d0`
- end: `0x1800c678c`
- name: `?ImpersonateToken@@YAHPEAXPEAPEAX@Z`
- size: `188`
- prototype: `__int64 __fastcall(HANDLE Token, void **)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1800be40c`

## callees

- `0x1800c66d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c6714`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c6739`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c6751`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c6714`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c6739`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c6751`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c6741`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c6766`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c6741`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c6766`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800c670a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800c670a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800c66f1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800c66f1`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800c672f`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800c672f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c675e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800c675e`

## pseudocode

```c
__int64 __fastcall ImpersonateToken(HANDLE Token, void **a2)
{
  void *v2; // rax
  HANDLE CurrentThread; // rax
  unsigned int v6; // ebx
  DWORD LastError; // eax
  DWORD v8; // ebx
  void *TokenHandle; // [rsp+30h] [rbp+8h] BYREF

  v2 = 0;
  TokenHandle = 0;
  if ( Token )
  {
    CurrentThread = GetCurrentThread();
    v6 = 1;
    if ( OpenThreadToken(CurrentThread, 0xCu, 1, &TokenHandle)
      || (LastError = GetLastError(), TokenHandle = 0, LastError == 1008) )
    {
      if ( SetThreadToken(0, Token) )
      {
        v2 = TokenHandle;
        goto LABEL_10;
      }
      LastError = GetLastError();
    }
    SetLastError(LastError);
    v2 = TokenHandle;
    if ( TokenHandle )
    {
      v8 = GetLastError();
      CloseHandle(TokenHandle);
      SetLastError(v8);
      v2 = 0;
    }
  }
  v6 = 0;
LABEL_10:
  *a2 = v2;
  return v6;
}

```

## disassembly

```asm
0x1800c66d0  mov     [rsp+arg_8], rbx
0x1800c66d5  mov     [rsp+arg_10], rsi
0x1800c66da  push    rdi
0x1800c66db  sub     rsp, 20h
0x1800c66df  xor     eax, eax
0x1800c66e1  mov     rsi, rdx
0x1800c66e4  mov     [rsp+28h+TokenHandle], rax
0x1800c66e9  mov     rdi, rcx
0x1800c66ec  test    rcx, rcx
0x1800c66ef  jz      short loc_1800C676E
0x1800c66f1  call    cs:__imp_GetCurrentThread
0x1800c66f7  mov     ebx, 1
0x1800c66fc  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x1800c6701  mov     rcx, rax; ThreadHandle
0x1800c6704  mov     r8d, ebx; OpenAsSelf
0x1800c6707  lea     edx, [rbx+0Bh]; DesiredAccess
0x1800c670a  call    cs:__imp_OpenThreadToken
0x1800c6710  test    eax, eax
0x1800c6712  jnz     short loc_1800C672A
0x1800c6714  call    cs:__imp_GetLastError
0x1800c671a  mov     [rsp+28h+TokenHandle], 0
0x1800c6723  cmp     eax, 3F0h
0x1800c6728  jnz     short loc_1800C673F
0x1800c672a  mov     rdx, rdi; Token
0x1800c672d  xor     ecx, ecx; Thread
0x1800c672f  call    cs:__imp_SetThreadToken
0x1800c6735  test    eax, eax
0x1800c6737  jnz     short loc_1800C6772
0x1800c6739  call    cs:__imp_GetLastError
0x1800c673f  mov     ecx, eax; dwErrCode
0x1800c6741  call    cs:__imp_SetLastError
0x1800c6747  mov     rax, [rsp+28h+TokenHandle]
0x1800c674c  test    rax, rax
0x1800c674f  jz      short loc_1800C676E
0x1800c6751  call    cs:__imp_GetLastError
0x1800c6757  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x1800c675c  mov     ebx, eax
0x1800c675e  call    cs:__imp_CloseHandle
0x1800c6764  mov     ecx, ebx; dwErrCode
0x1800c6766  call    cs:__imp_SetLastError
0x1800c676c  xor     eax, eax
0x1800c676e  xor     ebx, ebx
0x1800c6770  jmp     short loc_1800C6777
0x1800c6772  mov     rax, [rsp+28h+TokenHandle]
0x1800c6777  mov     [rsi], rax
0x1800c677a  mov     eax, ebx
0x1800c677c  mov     rbx, [rsp+28h+arg_8]
0x1800c6781  mov     rsi, [rsp+28h+arg_10]
0x1800c6786  add     rsp, 20h
0x1800c678a  pop     rdi
0x1800c678b  retn
```
