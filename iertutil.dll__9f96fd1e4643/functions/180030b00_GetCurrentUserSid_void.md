# GetCurrentUserSid(void * *)

- ea: `0x180030b00`
- end: `0x180030b5b`
- name: `?GetCurrentUserSid@@YAKPEAPEAX@Z`
- size: `91`
- prototype: `unsigned int __fastcall(void **)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180030114`
- `0x1800306b0`

## callees

- `0x180030b00`
- `0x1800327b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030b51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030b51`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180030b12`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180030b12`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180030b25`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180030b25`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030b43`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180030b43`

## pseudocode

```c
__int64 __fastcall GetCurrentUserSid(void **a1)
{
  HANDLE CurrentProcess; // rax
  unsigned int UserSid; // ebx
  void *TokenHandle; // [rsp+38h] [rbp+10h] BYREF

  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
  {
    UserSid = GetUserSid(TokenHandle, a1);
    CloseHandle(TokenHandle);
  }
  else
  {
    return GetLastError();
  }
  return UserSid;
}

```

## disassembly

```asm
0x180030b00  push    rbx
0x180030b02  sub     rsp, 20h
0x180030b06  mov     rbx, rcx
0x180030b09  mov     [rsp+28h+TokenHandle], 0
0x180030b12  call    cs:__imp_GetCurrentProcess
0x180030b18  lea     r8, [rsp+28h+TokenHandle]; TokenHandle
0x180030b1d  mov     edx, 8; DesiredAccess
0x180030b22  mov     rcx, rax; ProcessHandle
0x180030b25  call    cs:__imp_OpenProcessToken
0x180030b2b  test    eax, eax
0x180030b2d  jz      short loc_180030B51
0x180030b2f  mov     rcx, [rsp+28h+TokenHandle]; TokenHandle
0x180030b34  mov     rdx, rbx; void **
0x180030b37  call    ?GetUserSid@@YAKPEAXPEAPEAX@Z; GetUserSid(void *,void * *)
0x180030b3c  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x180030b41  mov     ebx, eax
0x180030b43  call    cs:__imp_CloseHandle
0x180030b49  mov     eax, ebx
0x180030b4b  add     rsp, 20h
0x180030b4f  pop     rbx
0x180030b50  retn
0x180030b51  call    cs:__imp_GetLastError
0x180030b57  mov     ebx, eax
0x180030b59  jmp     short loc_180030B49
```
