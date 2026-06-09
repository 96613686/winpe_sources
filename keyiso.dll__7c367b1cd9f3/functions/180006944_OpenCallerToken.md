# OpenCallerToken

- ea: `0x180006944`
- end: `0x180006a02`
- name: `OpenCallerToken`
- size: `190`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800066e0`

## callees

- `0x180003cf0`
- `0x180006944`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000697b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800069c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000697b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800069c9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800069ac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800069ac`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180006971`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180006971`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800069bf`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800069bf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000695a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000695a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800069ef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800069ef`

## string_xrefs

- `0x180006990`: `onecore\ds\security\cryptoapi\ncrypt\common\biopinhelper.c`

## pseudocode

```c
__int64 __fastcall OpenCallerToken(__int64 a1, void **a2)
{
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  DWORD v5; // ebx
  __int64 v6; // r9
  void *v7; // rcx
  HANDLE CurrentProcess; // rax
  void *TokenHandle; // [rsp+40h] [rbp+18h] BYREF

  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0x28u, 1, &TokenHandle) )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError != 1008 )
    {
      v6 = 293;
LABEL_4:
      DebugTraceError(LastError, "dwReturn", "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\biopinhelper.c", v6);
      v7 = TokenHandle;
      goto LABEL_8;
    }
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle) )
    {
      LastError = GetLastError();
      v5 = LastError;
      v6 = 301;
      goto LABEL_4;
    }
  }
  v5 = 0;
  v7 = 0;
  *a2 = TokenHandle;
  TokenHandle = 0;
LABEL_8:
  if ( v7 )
    CloseHandle(v7);
  return v5;
}

```

## disassembly

```asm
0x180006944  mov     [rsp+arg_0], rbx
0x180006949  push    rdi
0x18000694a  sub     rsp, 20h
0x18000694e  mov     rdi, rdx
0x180006951  mov     [rsp+28h+TokenHandle], 0
0x18000695a  call    cs:__imp_GetCurrentThread
0x180006960  mov     edx, 28h ; '('; DesiredAccess
0x180006965  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x18000696a  mov     rcx, rax; ThreadHandle
0x18000696d  lea     r8d, [rdx-27h]; OpenAsSelf
0x180006971  call    cs:__imp_OpenThreadToken
0x180006977  test    eax, eax
0x180006979  jnz     short loc_1800069D9
0x18000697b  call    cs:__imp_GetLastError
0x180006981  mov     ebx, eax
0x180006983  cmp     eax, 3F0h
0x180006988  jz      short loc_1800069AC
0x18000698a  mov     r9d, 125h
0x180006990  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180006997  mov     ecx, eax
0x180006999  lea     rdx, aDwreturn; "dwReturn"
0x1800069a0  call    DebugTraceError
0x1800069a5  mov     rcx, [rsp+28h+TokenHandle]
0x1800069aa  jmp     short loc_1800069EA
0x1800069ac  call    cs:__imp_GetCurrentProcess
0x1800069b2  lea     r8, [rsp+28h+TokenHandle]; TokenHandle
0x1800069b7  mov     edx, 28h ; '('; DesiredAccess
0x1800069bc  mov     rcx, rax; ProcessHandle
0x1800069bf  call    cs:__imp_OpenProcessToken
0x1800069c5  test    eax, eax
0x1800069c7  jnz     short loc_1800069D9
0x1800069c9  call    cs:__imp_GetLastError
0x1800069cf  mov     ebx, eax
0x1800069d1  mov     r9d, 12Dh
0x1800069d7  jmp     short loc_180006990
0x1800069d9  mov     rax, [rsp+28h+TokenHandle]
0x1800069de  xor     ebx, ebx
0x1800069e0  xor     ecx, ecx; hObject
0x1800069e2  mov     [rdi], rax
0x1800069e5  mov     [rsp+28h+TokenHandle], rcx
0x1800069ea  test    rcx, rcx
0x1800069ed  jz      short loc_1800069F5
0x1800069ef  call    cs:__imp_CloseHandle
0x1800069f5  mov     eax, ebx
0x1800069f7  mov     rbx, [rsp+28h+arg_0]
0x1800069fc  add     rsp, 20h
0x180006a00  pop     rdi
0x180006a01  retn
```
