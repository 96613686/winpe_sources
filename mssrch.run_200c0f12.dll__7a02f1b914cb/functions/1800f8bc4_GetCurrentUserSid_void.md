# GetCurrentUserSid(void * *)

- ea: `0x1800f8bc4`
- end: `0x1800f8cc2`
- name: `?GetCurrentUserSid@@YAJPEAPEAX@Z`
- size: `254`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800f8a84`

## callees

- `0x1800c1a80`
- `0x1800f8bc4`
- `0x18010ff58`
- `0x1801244c0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800f8c25`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800f8c25`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800f8c38`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800f8c38`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800f8bf6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800f8bf6`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800f8c0d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800f8c0d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f8c99`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f8c99`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800f8c70`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800f8c70`

## pseudocode

```c
__int64 __fastcall GetCurrentUserSid(void **a1)
{
  HANDLE CurrentThread; // rax
  int Error; // ebx
  HANDLE CurrentProcess; // rax
  void *TokenHandle; // [rsp+30h] [rbp-88h] BYREF
  DWORD ReturnLength; // [rsp+38h] [rbp-80h] BYREF
  PSID TokenInformation[12]; // [rsp+40h] [rbp-78h] BYREF

  *a1 = 0;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
  {
    Error = ResultFromKnownLastError();
    if ( Error != -2147023888 )
      goto LABEL_5;
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
    {
      Error = ResultFromKnownLastError();
LABEL_5:
      if ( Error < 0 )
        return (unsigned int)Error;
    }
  }
  ReturnLength = 88;
  if ( GetTokenInformation(TokenHandle, TokenUser, TokenInformation, 0x58u, &ReturnLength)
    || (Error = ResultFromKnownLastError(), Error >= 0) )
  {
    Error = AllocAndCopySid(TokenInformation[0], a1);
  }
  CloseHandle(TokenHandle);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1800f8bc4  mov     [rsp+arg_8], rbx
0x1800f8bc9  push    rdi
0x1800f8bca  sub     rsp, 0B0h
0x1800f8bd1  mov     rax, cs:__security_cookie
0x1800f8bd8  xor     rax, rsp
0x1800f8bdb  mov     [rsp+0B8h+var_18], rax
0x1800f8be3  mov     rdi, rcx
0x1800f8be6  mov     qword ptr [rcx], 0
0x1800f8bed  mov     [rsp+0B8h+TokenHandle], 0
0x1800f8bf6  call    cs:__imp_GetCurrentThread
0x1800f8bfc  mov     edx, 8; DesiredAccess
0x1800f8c01  lea     r9, [rsp+0B8h+TokenHandle]; TokenHandle
0x1800f8c06  mov     rcx, rax; ThreadHandle
0x1800f8c09  lea     r8d, [rdx-7]; OpenAsSelf
0x1800f8c0d  call    cs:__imp_OpenThreadToken
0x1800f8c13  test    eax, eax
0x1800f8c15  jnz     short loc_1800F8C4D
0x1800f8c17  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800f8c1c  mov     ebx, eax
0x1800f8c1e  cmp     eax, 800703F0h
0x1800f8c23  jnz     short loc_1800F8C49
0x1800f8c25  call    cs:__imp_GetCurrentProcess
0x1800f8c2b  lea     r8, [rsp+0B8h+TokenHandle]; TokenHandle
0x1800f8c30  mov     edx, 8; DesiredAccess
0x1800f8c35  mov     rcx, rax; ProcessHandle
0x1800f8c38  call    cs:__imp_OpenProcessToken
0x1800f8c3e  test    eax, eax
0x1800f8c40  jnz     short loc_1800F8C4D
0x1800f8c42  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800f8c47  mov     ebx, eax
0x1800f8c49  test    ebx, ebx
0x1800f8c4b  js      short loc_1800F8C9F
0x1800f8c4d  mov     rcx, [rsp+0B8h+TokenHandle]; TokenHandle
0x1800f8c52  lea     rax, [rsp+0B8h+var_80]
0x1800f8c57  mov     r9d, 58h ; 'X'; TokenInformationLength
0x1800f8c5d  mov     [rsp+0B8h+ReturnLength], rax; ReturnLength
0x1800f8c62  lea     r8, [rsp+0B8h+TokenInformation]; TokenInformation
0x1800f8c67  mov     [rsp+0B8h+var_80], r9d
0x1800f8c6c  lea     edx, [r9-57h]; TokenInformationClass
0x1800f8c70  call    cs:__imp_GetTokenInformation
0x1800f8c76  test    eax, eax
0x1800f8c78  jnz     short loc_1800F8C85
0x1800f8c7a  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800f8c7f  mov     ebx, eax
0x1800f8c81  test    eax, eax
0x1800f8c83  js      short loc_1800F8C94
0x1800f8c85  mov     rcx, [rsp+0B8h+TokenInformation]; pSourceSid
0x1800f8c8a  mov     rdx, rdi; void **
0x1800f8c8d  call    ?AllocAndCopySid@@YAJPEAXPEAPEAX@Z; AllocAndCopySid(void *,void * *)
0x1800f8c92  mov     ebx, eax
0x1800f8c94  mov     rcx, [rsp+0B8h+TokenHandle]; hObject
0x1800f8c99  call    cs:__imp_CloseHandle
0x1800f8c9f  mov     eax, ebx
0x1800f8ca1  mov     rcx, [rsp+0B8h+var_18]
0x1800f8ca9  xor     rcx, rsp; StackCookie
0x1800f8cac  call    __security_check_cookie
0x1800f8cb1  mov     rbx, [rsp+0B8h+arg_8]
0x1800f8cb9  add     rsp, 0B0h
0x1800f8cc0  pop     rdi
0x1800f8cc1  retn
```
