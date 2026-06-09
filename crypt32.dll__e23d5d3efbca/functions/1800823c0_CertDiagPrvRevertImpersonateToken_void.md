# CertDiagPrvRevertImpersonateToken(void)

- ea: `0x1800823c0`
- end: `0x180082449`
- name: `?CertDiagPrvRevertImpersonateToken@@YAPEAXXZ`
- size: `137`
- prototype: `void *(void)`
- caller_count: `5`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x180010af4`
- `0x180082228`
- `0x1800c15a4`
- `0x1800c165c`
- `0x1800c19fc`

## callees

- `0x1800823c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800823f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008241f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800823f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008241f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18011b8ce`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18011b8ce`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800823e6`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800823e6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800823cf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800823cf`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180082415`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180082415`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008242c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18008242c`

## pseudocode

```c
void *CertDiagPrvRevertImpersonateToken(void)
{
  HANDLE CurrentThread; // rax
  DWORD v1; // eax
  DWORD LastError; // ebx
  DWORD v4; // ecx
  void *TokenHandle; // [rsp+30h] [rbp+8h] BYREF

  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0xEu, 1, &TokenHandle) )
  {
    if ( SetThreadToken(0, 0) )
      return TokenHandle;
    LastError = GetLastError();
    CloseHandle(TokenHandle);
    TokenHandle = 0;
    v4 = LastError;
LABEL_7:
    SetLastError(v4);
    return TokenHandle;
  }
  v1 = GetLastError();
  TokenHandle = 0;
  if ( v1 != 1008 )
  {
    v4 = v1;
    goto LABEL_7;
  }
  return TokenHandle;
}

```

## disassembly

```asm
0x1800823c0  push    rbx
0x1800823c2  sub     rsp, 20h
0x1800823c6  mov     [rsp+28h+TokenHandle], 0
0x1800823cf  call    cs:__imp_GetCurrentThread
0x1800823d5  mov     edx, 0Eh; DesiredAccess
0x1800823da  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x1800823df  mov     rcx, rax; ThreadHandle
0x1800823e2  lea     r8d, [rdx-0Dh]; OpenAsSelf
0x1800823e6  call    cs:__imp_OpenThreadToken
0x1800823ec  test    eax, eax
0x1800823ee  jnz     short loc_180082411
0x1800823f0  call    cs:__imp_GetLastError
0x1800823f6  mov     [rsp+28h+TokenHandle], 0
0x1800823ff  cmp     eax, 3F0h
0x180082404  jnz     short loc_180082442
0x180082406  mov     rax, [rsp+28h+TokenHandle]
0x18008240b  add     rsp, 20h
0x18008240f  pop     rbx
0x180082410  retn
0x180082411  xor     edx, edx; Token
0x180082413  xor     ecx, ecx; Thread
0x180082415  call    cs:__imp_SetThreadToken
0x18008241b  test    eax, eax
0x18008241d  jnz     short loc_180082406
0x18008241f  call    cs:__imp_GetLastError
0x180082425  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x18008242a  mov     ebx, eax
0x18008242c  call    cs:__imp_CloseHandle
0x180082432  mov     [rsp+28h+TokenHandle], 0
0x18008243b  mov     ecx, ebx; dwErrCode
0x18008243d  jmp     loc_18011B8CE
0x180082442  mov     ecx, eax
0x180082444  jmp     loc_18011B8CE
0x18011b8ce  call    cs:__imp_SetLastError
0x18011b8d4  nop
0x18011b8d5  jmp     loc_180082406
```
