# GetProcessSid(ulong,void * *)

- ea: `0x1800329b0`
- end: `0x180032a39`
- name: `?GetProcessSid@@YAKKPEAPEAX@Z`
- size: `137`
- prototype: `unsigned int __fastcall(DWORD dwProcessId, void **)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1800624f0`
- `0x180065a60`

## callees

- `0x1800327b0`
- `0x1800329b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032a11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032a24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032a11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032a24`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800329eb`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800329eb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180032a09`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180032a1c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180032a09`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180032a1c`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800329d0`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800329d0`

## pseudocode

```c
__int64 __fastcall GetProcessSid(DWORD dwProcessId, void **a2)
{
  HANDLE v3; // rax
  void *v4; // rdi
  unsigned int UserSid; // ebx
  void *TokenHandle; // [rsp+40h] [rbp+18h] BYREF

  TokenHandle = 0;
  v3 = OpenProcess(0x400u, 0, dwProcessId);
  v4 = v3;
  if ( v3 )
  {
    if ( OpenProcessToken(v3, 8u, &TokenHandle) )
    {
      UserSid = GetUserSid(TokenHandle, a2);
      CloseHandle(TokenHandle);
    }
    else
    {
      UserSid = GetLastError();
    }
    CloseHandle(v4);
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
0x1800329b0  mov     [rsp+arg_0], rbx
0x1800329b5  push    rdi
0x1800329b6  sub     rsp, 20h
0x1800329ba  mov     rbx, rdx
0x1800329bd  mov     [rsp+28h+TokenHandle], 0
0x1800329c6  mov     r8d, ecx; dwProcessId
0x1800329c9  xor     edx, edx; bInheritHandle
0x1800329cb  mov     ecx, 400h; dwDesiredAccess
0x1800329d0  call    cs:__imp_OpenProcess
0x1800329d6  mov     rdi, rax
0x1800329d9  test    rax, rax
0x1800329dc  jz      short loc_180032A24
0x1800329de  lea     r8, [rsp+28h+TokenHandle]; TokenHandle
0x1800329e3  mov     edx, 8; DesiredAccess
0x1800329e8  mov     rcx, rax; ProcessHandle
0x1800329eb  call    cs:__imp_OpenProcessToken
0x1800329f1  test    eax, eax
0x1800329f3  jz      short loc_180032A11
0x1800329f5  mov     rcx, [rsp+28h+TokenHandle]; TokenHandle
0x1800329fa  mov     rdx, rbx; void **
0x1800329fd  call    ?GetUserSid@@YAKPEAXPEAPEAX@Z; GetUserSid(void *,void * *)
0x180032a02  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x180032a07  mov     ebx, eax
0x180032a09  call    cs:__imp_CloseHandle
0x180032a0f  jmp     short loc_180032A19
0x180032a11  call    cs:__imp_GetLastError
0x180032a17  mov     ebx, eax
0x180032a19  mov     rcx, rdi; hObject
0x180032a1c  call    cs:__imp_CloseHandle
0x180032a22  jmp     short loc_180032A2C
0x180032a24  call    cs:__imp_GetLastError
0x180032a2a  mov     ebx, eax
0x180032a2c  mov     eax, ebx
0x180032a2e  mov     rbx, [rsp+28h+arg_0]
0x180032a33  add     rsp, 20h
0x180032a37  pop     rdi
0x180032a38  retn
```
