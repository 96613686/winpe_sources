# _OpenCallerToken

- ea: `0x180020b9c`
- end: `0x180020c68`
- name: `_OpenCallerToken`
- size: `204`
- prototype: `__int64 __fastcall(__int64, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180020a24`

## callees

- `0x18000af80`
- `0x180020b9c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020bf5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020c3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020bf5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020c3b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180020c12`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180020c12`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180020bcf`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180020bcf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180020bb2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180020bb2`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180020c2b`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180020c2b`

## string_xrefs

- `0x180020c4f`: `onecore\ds\security\cryptoapi\ncrypt\storage\keycache.c`

## pseudocode

```c
__int64 __fastcall OpenCallerToken(__int64 a1, void **a2)
{
  HANDLE CurrentThread; // rax
  DWORD LastError; // ebx
  __int64 v6; // r9
  HANDLE CurrentProcess; // rax
  void *TokenHandle; // [rsp+40h] [rbp+18h] BYREF

  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    goto LABEL_2;
  LastError = GetLastError();
  if ( LastError == 1008 )
  {
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
    {
LABEL_2:
      *a2 = TokenHandle;
      return 0;
    }
    LastError = GetLastError();
    v6 = 256;
  }
  else
  {
    v6 = 248;
  }
  DebugTraceError(LastError, "dwReturn", "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\keycache.c", v6);
  return LastError;
}

```

## disassembly

```asm
0x180020b9c  mov     [rsp+arg_0], rbx
0x180020ba1  push    rdi
0x180020ba2  sub     rsp, 20h
0x180020ba6  mov     rdi, rdx
0x180020ba9  mov     [rsp+28h+TokenHandle], 0
0x180020bb2  call    cs:__imp_GetCurrentThread
0x180020bb9  nop     dword ptr [rax+rax+00h]
0x180020bbe  mov     edx, 8; DesiredAccess
0x180020bc3  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x180020bc8  mov     rcx, rax; ThreadHandle
0x180020bcb  lea     r8d, [rdx-7]; OpenAsSelf
0x180020bcf  call    cs:__imp_OpenThreadToken
0x180020bd6  nop     dword ptr [rax+rax+00h]
0x180020bdb  test    eax, eax
0x180020bdd  jz      short loc_180020BF5
0x180020bdf  mov     rax, [rsp+28h+TokenHandle]
0x180020be4  mov     [rdi], rax
0x180020be7  xor     eax, eax
0x180020be9  mov     rbx, [rsp+28h+arg_0]
0x180020bee  add     rsp, 20h
0x180020bf2  pop     rdi
0x180020bf3  retn
0x180020bf5  call    cs:__imp_GetLastError
0x180020bfc  nop     dword ptr [rax+rax+00h]
0x180020c01  mov     ebx, eax
0x180020c03  cmp     eax, 3F0h
0x180020c08  jz      short loc_180020C12
0x180020c0a  mov     r9d, 0F8h
0x180020c10  jmp     short loc_180020C4F
0x180020c12  call    cs:__imp_GetCurrentProcess
0x180020c19  nop     dword ptr [rax+rax+00h]
0x180020c1e  lea     r8, [rsp+28h+TokenHandle]; TokenHandle
0x180020c23  mov     edx, 8; DesiredAccess
0x180020c28  mov     rcx, rax; ProcessHandle
0x180020c2b  call    cs:__imp_OpenProcessToken
0x180020c32  nop     dword ptr [rax+rax+00h]
0x180020c37  test    eax, eax
0x180020c39  jnz     short loc_180020BDF
0x180020c3b  call    cs:__imp_GetLastError
0x180020c42  nop     dword ptr [rax+rax+00h]
0x180020c47  mov     ebx, eax
0x180020c49  mov     r9d, 100h
0x180020c4f  lea     r8, aOnecoreDsSecur_39; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180020c56  mov     ecx, ebx
0x180020c58  lea     rdx, aDwreturn; "dwReturn"
0x180020c5f  call    DebugTraceError
0x180020c64  mov     eax, ebx
0x180020c66  jmp     short loc_180020BE9
```
