# IsUserHiveOK(int *)

- ea: `0x180058ce8`
- end: `0x180058d6d`
- name: `?IsUserHiveOK@@YAJPEAH@Z`
- size: `133`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x180040d20`

## callees

- `0x180011f84`
- `0x180011fb4`
- `0x1800304f0`
- `0x180058ce8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180058d0d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180058d0d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180058d20`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180058d20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058d46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058d46`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180058d3e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180058d3e`

## pseudocode

```c
__int64 __fastcall IsUserHiveOK(int *a1)
{
  HANDLE CurrentProcess; // rax
  unsigned int v3; // ebx
  signed int LastError; // eax
  void *TokenHandle; // [rsp+38h] [rbp+10h] BYREF
  HANDLE Token; // [rsp+40h] [rbp+18h] BYREF

  Token = 0;
  TokenHandle = 0;
  SuspendImpersonate(&Token);
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
  {
    v3 = IsUserHiveOK(TokenHandle, a1);
    CloseHandle(TokenHandle);
  }
  else
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
  }
  ResumeImpersonate(Token);
  return v3;
}

```

## disassembly

```asm
0x180058ce8  push    rbx
0x180058cea  sub     rsp, 20h
0x180058cee  mov     rbx, rcx
0x180058cf1  mov     [rsp+28h+Token], 0
0x180058cfa  lea     rcx, [rsp+28h+Token]; TokenHandle
0x180058cff  mov     [rsp+28h+TokenHandle], 0
0x180058d08  call    ?SuspendImpersonate@@YAJPEAPEAX@Z; SuspendImpersonate(void * *)
0x180058d0d  call    cs:__imp_GetCurrentProcess
0x180058d13  lea     r8, [rsp+28h+TokenHandle]; TokenHandle
0x180058d18  mov     edx, 8; DesiredAccess
0x180058d1d  mov     rcx, rax; ProcessHandle
0x180058d20  call    cs:__imp_OpenProcessToken
0x180058d26  test    eax, eax
0x180058d28  jz      short loc_180058D46
0x180058d2a  mov     rcx, [rsp+28h+TokenHandle]; TokenHandle
0x180058d2f  mov     rdx, rbx; int *
0x180058d32  call    ?IsUserHiveOK@@YAJPEAXPEAH@Z; IsUserHiveOK(void *,int *)
0x180058d37  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x180058d3c  mov     ebx, eax
0x180058d3e  call    cs:__imp_CloseHandle
0x180058d44  jmp     short loc_180058D5B
0x180058d46  call    cs:__imp_GetLastError
0x180058d4c  mov     ebx, eax
0x180058d4e  test    eax, eax
0x180058d50  jle     short loc_180058D5B
0x180058d52  movzx   ebx, ax
0x180058d55  or      ebx, 80070000h
0x180058d5b  mov     rcx, [rsp+28h+Token]; Token
0x180058d60  call    ?ResumeImpersonate@@YAXPEAX@Z; ResumeImpersonate(void *)
0x180058d65  mov     eax, ebx
0x180058d67  add     rsp, 20h
0x180058d6b  pop     rbx
0x180058d6c  retn
```
