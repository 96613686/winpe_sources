# OpenCallerToken

- ea: `0x180011e00`
- end: `0x180011eff`
- name: `OpenCallerToken`
- size: `255`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180011240`

## callees

- `0x18000b594`
- `0x18000b654`
- `0x180011e00`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011e39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011ed2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011e39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011ed2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011ef7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011ef7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180011e48`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180011e48`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180011e2f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180011e2f`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180011e5b`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180011e5b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180011e16`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180011e16`

## string_xrefs

- `0x180011e97`: `onecore\ds\security\cryptoapi\ncrypt\common\biopinhelper.c`
- `0x180011ede`: `onecore\ds\security\cryptoapi\ncrypt\common\biopinhelper.c`

## pseudocode

```c
__int64 __fastcall OpenCallerToken(__int64 a1, void **a2)
{
  HANDLE CurrentThread; // rax
  int v4; // edx
  DWORD LastError; // edi
  HANDLE CurrentProcess; // rax
  __int64 result; // rax
  void *TokenHandle; // [rsp+60h] [rbp+18h] BYREF

  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 0xCu, 1, &TokenHandle) )
    goto LABEL_4;
  LastError = GetLastError();
  if ( LastError == 1008 )
  {
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 0xCu, &TokenHandle) )
    {
LABEL_4:
      result = 0;
      *a2 = TokenHandle;
      return result;
    }
    LastError = GetLastError();
    DebugTraceError(LastError, "dwReturn", "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\biopinhelper.c", 301);
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v4,
      (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\biopinhelper.c",
      (unsigned int)"dwReturn",
      LastError,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\biopinhelper.c",
      37);
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return LastError;
}

```

## disassembly

```asm
0x180011e00  mov     [rsp+arg_0], rbx
0x180011e05  push    rdi
0x180011e06  sub     rsp, 40h
0x180011e0a  mov     rbx, rdx
0x180011e0d  mov     [rsp+48h+TokenHandle], 0
0x180011e16  call    cs:__imp_GetCurrentThread
0x180011e1c  lea     r9, [rsp+48h+TokenHandle]; TokenHandle
0x180011e21  mov     edx, 0Ch; DesiredAccess
0x180011e26  mov     rcx, rax; ThreadHandle
0x180011e29  mov     r8d, 1; OpenAsSelf
0x180011e2f  call    cs:__imp_OpenThreadToken
0x180011e35  test    eax, eax
0x180011e37  jnz     short loc_180011E65
0x180011e39  call    cs:__imp_GetLastError
0x180011e3f  mov     edi, eax
0x180011e41  cmp     eax, 3F0h
0x180011e46  jnz     short loc_180011E7A
0x180011e48  call    cs:__imp_GetCurrentProcess
0x180011e4e  lea     r8, [rsp+48h+TokenHandle]; TokenHandle
0x180011e53  mov     edx, 0Ch; DesiredAccess
0x180011e58  mov     rcx, rax; ProcessHandle
0x180011e5b  call    cs:__imp_OpenProcessToken
0x180011e61  test    eax, eax
0x180011e63  jz      short loc_180011ED2
0x180011e65  mov     rcx, [rsp+48h+TokenHandle]
0x180011e6a  xor     eax, eax
0x180011e6c  mov     [rbx], rcx
0x180011e6f  mov     rbx, [rsp+48h+arg_0]
0x180011e74  add     rsp, 40h
0x180011e78  pop     rdi
0x180011e79  retn
0x180011e7a  mov     rcx, cs:WPP_GLOBAL_Control
0x180011e81  lea     rax, WPP_GLOBAL_Control
0x180011e88  cmp     rcx, rax
0x180011e8b  jz      short loc_180011EBB
0x180011e8d  test    byte ptr [rcx+1Ch], 1
0x180011e91  jz      short loc_180011EBB
0x180011e93  mov     rcx, [rcx+10h]
0x180011e97  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180011e9e  mov     [rsp+48h+var_18], 125h
0x180011ea6  lea     r9, aDwreturn; "dwReturn"
0x180011ead  mov     [rsp+48h+var_20], r8
0x180011eb2  mov     [rsp+48h+var_28], edi
0x180011eb6  call    WPP_SF_sDsd
0x180011ebb  mov     rcx, [rsp+48h+TokenHandle]; hObject
0x180011ec0  test    rcx, rcx
0x180011ec3  jnz     short loc_180011EF7
0x180011ec5  mov     rbx, [rsp+48h+arg_0]
0x180011eca  mov     eax, edi
0x180011ecc  add     rsp, 40h
0x180011ed0  pop     rdi
0x180011ed1  retn
0x180011ed2  call    cs:__imp_GetLastError
0x180011ed8  mov     r9d, 12Dh
0x180011ede  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180011ee5  mov     ecx, eax
0x180011ee7  lea     rdx, aDwreturn; "dwReturn"
0x180011eee  mov     edi, eax
0x180011ef0  call    DebugTraceError
0x180011ef5  jmp     short loc_180011EBB
0x180011ef7  call    cs:__imp_CloseHandle
0x180011efd  jmp     short loc_180011EC5
```
