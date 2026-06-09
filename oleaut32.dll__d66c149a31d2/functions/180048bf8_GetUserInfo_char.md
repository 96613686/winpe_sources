# GetUserInfo(char * *)

- ea: `0x180048bf8`
- end: `0x180048d2e`
- name: `?GetUserInfo@@YAXPEAPEAD@Z`
- size: `310`
- prototype: `void __fastcall(char **)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180004890`
- `0x1800057e0`
- `0x18002ac34`

## callees

- `0x180048bf8`
- `0x18004d924`
- `0x18004dd00`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180048c48`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180048c48`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180048c2b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180048c2b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180048c16`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180048c16`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180048c59`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180048c59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048c37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048ca6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048c37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048ca6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180048d1d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180048d1d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180048c9c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180048cfc`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180048c9c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180048cfc`

## pseudocode

```c
void __fastcall GetUserInfo(char **a1)
{
  HANDLE CurrentThread; // rax
  char *v3; // rbx
  unsigned __int64 v4; // rdx
  HANDLE CurrentProcess; // rax
  DWORD ReturnLength; // [rsp+48h] [rbp+10h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp+18h] BYREF

  ReturnLength = 0;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( (OpenThreadToken(CurrentThread, 8u, 0, &TokenHandle)
     || (v3 = 0, GetLastError() == 1008)
     && (CurrentProcess = GetCurrentProcess(), OpenProcessToken(CurrentProcess, 8u, &TokenHandle)))
    && (v3 = (char *)operator new[](TokenInformationLength)) != 0
    && (GetTokenInformation(TokenHandle, TokenUser, v3, TokenInformationLength, &ReturnLength)
     || GetLastError() == 122
     && ReturnLength > TokenInformationLength
     && (TokenInformationLength = ReturnLength,
         operator delete(v3, v4),
         (v3 = (char *)operator new[](TokenInformationLength)) != 0)
     && GetTokenInformation(TokenHandle, TokenUser, v3, TokenInformationLength, &ReturnLength)) )
  {
    *a1 = v3;
  }
  else
  {
    operator delete(v3, v4);
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
}

```

## disassembly

```asm
0x180048bf8  mov     [rsp+arg_0], rbx
0x180048bfd  push    rdi
0x180048bfe  sub     rsp, 30h
0x180048c02  mov     rdi, rcx
0x180048c05  mov     [rsp+38h+arg_8], 0
0x180048c0d  mov     [rsp+38h+TokenHandle], 0
0x180048c16  call    cs:__imp_GetCurrentThread
0x180048c1c  xor     r8d, r8d; OpenAsSelf
0x180048c1f  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x180048c24  mov     rcx, rax; ThreadHandle
0x180048c27  lea     edx, [r8+8]; DesiredAccess
0x180048c2b  call    cs:__imp_OpenThreadToken
0x180048c31  test    eax, eax
0x180048c33  jnz     short loc_180048C67
0x180048c35  xor     ebx, ebx
0x180048c37  call    cs:__imp_GetLastError
0x180048c3d  cmp     eax, 3F0h
0x180048c42  jnz     loc_180048D0B
0x180048c48  call    cs:__imp_GetCurrentProcess
0x180048c4e  mov     rcx, rax; ProcessHandle
0x180048c51  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x180048c56  lea     edx, [rbx+8]; DesiredAccess
0x180048c59  call    cs:__imp_OpenProcessToken
0x180048c5f  test    eax, eax
0x180048c61  jz      loc_180048D0B
0x180048c67  mov     ecx, cs:TokenInformationLength; unsigned __int64
0x180048c6d  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180048c72  mov     rbx, rax
0x180048c75  test    rax, rax
0x180048c78  jz      loc_180048D0B
0x180048c7e  mov     r9d, cs:TokenInformationLength; TokenInformationLength
0x180048c85  lea     rax, [rsp+38h+arg_8]
0x180048c8a  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x180048c8f  mov     r8, rbx; TokenInformation
0x180048c92  mov     edx, 1; TokenInformationClass
0x180048c97  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180048c9c  call    cs:__imp_GetTokenInformation
0x180048ca2  test    eax, eax
0x180048ca4  jnz     short loc_180048D06
0x180048ca6  call    cs:__imp_GetLastError
0x180048cac  cmp     eax, 7Ah ; 'z'
0x180048caf  jnz     short loc_180048D0B
0x180048cb1  mov     eax, [rsp+38h+arg_8]
0x180048cb5  cmp     eax, cs:TokenInformationLength
0x180048cbb  jbe     short loc_180048D0B
0x180048cbd  mov     rcx, rbx; void *
0x180048cc0  mov     cs:TokenInformationLength, eax
0x180048cc6  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180048ccb  mov     ecx, cs:TokenInformationLength; unsigned __int64
0x180048cd1  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180048cd6  mov     rbx, rax
0x180048cd9  test    rax, rax
0x180048cdc  jz      short loc_180048D0B
0x180048cde  mov     r9d, cs:TokenInformationLength; TokenInformationLength
0x180048ce5  lea     rax, [rsp+38h+arg_8]
0x180048cea  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x180048cef  mov     r8, rbx; TokenInformation
0x180048cf2  mov     edx, 1; TokenInformationClass
0x180048cf7  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180048cfc  call    cs:__imp_GetTokenInformation
0x180048d02  test    eax, eax
0x180048d04  jz      short loc_180048D0B
0x180048d06  mov     [rdi], rbx
0x180048d09  jmp     short loc_180048D13
0x180048d0b  mov     rcx, rbx; void *
0x180048d0e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180048d13  mov     rcx, [rsp+38h+TokenHandle]; hObject
0x180048d18  test    rcx, rcx
0x180048d1b  jz      short loc_180048D23
0x180048d1d  call    cs:__imp_CloseHandle
0x180048d23  mov     rbx, [rsp+38h+arg_0]
0x180048d28  add     rsp, 30h
0x180048d2c  pop     rdi
0x180048d2d  retn
```
