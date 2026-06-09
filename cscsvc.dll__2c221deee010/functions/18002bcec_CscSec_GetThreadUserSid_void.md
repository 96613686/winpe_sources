# CscSec_GetThreadUserSid(void * *)

- ea: `0x18002bcec`
- end: `0x18002bd97`
- name: `?CscSec_GetThreadUserSid@@YAJPEAPEAX@Z`
- size: `171`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `5`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x180019204`
- `0x18002bb58`
- `0x180045448`
- `0x180045594`
- `0x18004a15c`

## callees

- `0x18002bcec`
- `0x18002f10c`
- `0x18003598c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bd2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bd2a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002bd84`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002bd84`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002bd09`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002bd09`
- `KERNEL32!GetCurrentProcess` at `0x18002bd39`
- `KERNEL32!GetCurrentProcess` at `0x18002bd39`
- `ADVAPI32!OpenProcessToken` at `0x18002bd4c`
- `ADVAPI32!OpenProcessToken` at `0x18002bd4c`
- `ADVAPI32!OpenThreadToken` at `0x18002bd20`
- `ADVAPI32!OpenThreadToken` at `0x18002bd20`

## pseudocode

```c
__int64 __fastcall CscSec_GetThreadUserSid(void **a1)
{
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  unsigned int SidFromToken; // ebx
  HANDLE CurrentProcess; // rax
  void *TokenHandle; // [rsp+30h] [rbp+8h] BYREF

  *a1 = 0;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
    goto LABEL_8;
  LastError = GetLastError();
  SidFromToken = LastError;
  if ( LastError == 1008 )
  {
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
    {
LABEL_8:
      SidFromToken = CscSec_GetSidFromToken(TokenHandle, a1);
      CloseHandle(TokenHandle);
      return SidFromToken;
    }
    SidFromToken = ResultFromLastError();
  }
  else if ( LastError > 0 )
  {
    SidFromToken = (unsigned __int16)LastError | 0x80070000;
  }
  if ( (SidFromToken & 0x80000000) == 0 )
    goto LABEL_8;
  return SidFromToken;
}

```

## disassembly

```asm
0x18002bcec  mov     [rsp+arg_8], rbx
0x18002bcf1  push    rdi
0x18002bcf2  sub     rsp, 20h
0x18002bcf6  mov     rdi, rcx
0x18002bcf9  mov     qword ptr [rcx], 0
0x18002bd00  mov     [rsp+28h+TokenHandle], 0
0x18002bd09  call    cs:__imp_GetCurrentThread
0x18002bd0f  mov     edx, 8; DesiredAccess
0x18002bd14  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x18002bd19  mov     rcx, rax; ThreadHandle
0x18002bd1c  lea     r8d, [rdx-7]; OpenAsSelf
0x18002bd20  call    cs:__imp_OpenThreadToken
0x18002bd26  test    eax, eax
0x18002bd28  jnz     short loc_18002BD70
0x18002bd2a  call    cs:__imp_GetLastError
0x18002bd30  mov     ebx, eax
0x18002bd32  cmp     eax, 3F0h
0x18002bd37  jnz     short loc_18002BD5F
0x18002bd39  call    cs:__imp_GetCurrentProcess
0x18002bd3f  lea     r8, [rsp+28h+TokenHandle]; TokenHandle
0x18002bd44  mov     edx, 8; DesiredAccess
0x18002bd49  mov     rcx, rax; ProcessHandle
0x18002bd4c  call    cs:__imp_OpenProcessToken
0x18002bd52  test    eax, eax
0x18002bd54  jnz     short loc_18002BD70
0x18002bd56  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18002bd5b  mov     ebx, eax
0x18002bd5d  jmp     short loc_18002BD6C
0x18002bd5f  test    eax, eax
0x18002bd61  jle     short loc_18002BD6C
0x18002bd63  movzx   ebx, ax
0x18002bd66  or      ebx, 80070000h
0x18002bd6c  test    ebx, ebx
0x18002bd6e  js      short loc_18002BD8A
0x18002bd70  mov     rcx, [rsp+28h+TokenHandle]; TokenHandle
0x18002bd75  mov     rdx, rdi; void **
0x18002bd78  call    ?CscSec_GetSidFromToken@@YAJPEAXPEAPEAX@Z; CscSec_GetSidFromToken(void *,void * *)
0x18002bd7d  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x18002bd82  mov     ebx, eax
0x18002bd84  call    cs:__imp_CloseHandle
0x18002bd8a  mov     eax, ebx
0x18002bd8c  mov     rbx, [rsp+28h+arg_8]
0x18002bd91  add     rsp, 20h
0x18002bd95  pop     rdi
0x18002bd96  retn
```
