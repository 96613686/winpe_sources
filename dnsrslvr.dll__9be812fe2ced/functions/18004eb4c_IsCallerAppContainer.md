# IsCallerAppContainer

- ea: `0x18004eb4c`
- end: `0x18004ec45`
- name: `IsCallerAppContainer`
- size: `249`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180030230`

## callees

- `0x180046ec0`
- `0x18004eb4c`
- `0x180086b1c`

## import_xrefs

- `RPCRT4!RpcRevertToSelf` at `0x18004ec1a`
- `RPCRT4!RpcRevertToSelf` at `0x18004ec1a`
- `RPCRT4!RpcImpersonateClient` at `0x18004eb72`
- `RPCRT4!RpcImpersonateClient` at `0x18004eb72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ebc1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ebc1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004ec2a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004ec2a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18004ebb7`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18004ebb7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004eba2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18004eba2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18004ec09`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18004ec09`

## pseudocode

```c
__int64 IsCallerAppContainer()
{
  unsigned int v0; // ebx
  unsigned int v1; // eax
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  void *TokenHandle; // [rsp+30h] [rbp-28h] BYREF
  int TokenInformation; // [rsp+38h] [rbp-20h] BYREF
  DWORD ReturnLength; // [rsp+3Ch] [rbp-1Ch] BYREF

  v0 = 0;
  TokenHandle = 0;
  TokenInformation = 0;
  ReturnLength = 0;
  v1 = RpcImpersonateClient(0);
  if ( v1 )
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
      WPP_SF_d(1035, 88, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids, v1);
  }
  else
  {
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 8u, 0, &TokenHandle) )
    {
      if ( GetTokenInformation(TokenHandle, TokenIsAppContainer, &TokenInformation, 4u, &ReturnLength) )
        LOBYTE(v0) = TokenInformation != 0;
    }
    else
    {
      LastError = GetLastError();
      if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
        WPP_SF_d(1035, 89, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids, LastError);
    }
    RpcRevertToSelf();
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return v0;
}

```

## disassembly

```asm
0x18004eb4c  push    rbx
0x18004eb4e  sub     rsp, 50h
0x18004eb52  mov     rax, cs:__security_cookie
0x18004eb59  xor     rax, rsp
0x18004eb5c  mov     [rsp+58h+var_18], rax
0x18004eb61  xor     ebx, ebx
0x18004eb63  xor     ecx, ecx; BindingHandle
0x18004eb65  mov     [rsp+58h+TokenHandle], rbx
0x18004eb6a  mov     [rsp+58h+TokenInformation], ebx
0x18004eb6e  mov     [rsp+58h+var_1C], ebx
0x18004eb72  call    cs:__imp_RpcImpersonateClient
0x18004eb78  test    eax, eax
0x18004eb7a  jz      short loc_18004EBA2
0x18004eb7c  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18004eb83  jz      loc_18004EC20
0x18004eb89  lea     edx, [rbx+58h]
0x18004eb8c  mov     ecx, 40Bh
0x18004eb91  mov     r9d, eax
0x18004eb94  lea     r8, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids
0x18004eb9b  call    WPP_SF_d
0x18004eba0  jmp     short loc_18004EC20
0x18004eba2  call    cs:__imp_GetCurrentThread
0x18004eba8  xor     r8d, r8d; OpenAsSelf
0x18004ebab  lea     r9, [rsp+58h+TokenHandle]; TokenHandle
0x18004ebb0  mov     rcx, rax; ThreadHandle
0x18004ebb3  lea     edx, [r8+8]; DesiredAccess
0x18004ebb7  call    cs:__imp_OpenThreadToken
0x18004ebbd  test    eax, eax
0x18004ebbf  jnz     short loc_18004EBEB
0x18004ebc1  call    cs:__imp_GetLastError
0x18004ebc7  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18004ebce  jz      short loc_18004EC1A
0x18004ebd0  mov     edx, 59h ; 'Y'
0x18004ebd5  lea     r8, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids
0x18004ebdc  mov     ecx, 40Bh
0x18004ebe1  mov     r9d, eax
0x18004ebe4  call    WPP_SF_d
0x18004ebe9  jmp     short loc_18004EC1A
0x18004ebeb  mov     rcx, [rsp+58h+TokenHandle]; TokenHandle
0x18004ebf0  lea     rax, [rsp+58h+var_1C]
0x18004ebf5  mov     r9d, 4; TokenInformationLength
0x18004ebfb  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x18004ec00  lea     r8, [rsp+58h+TokenInformation]; TokenInformation
0x18004ec05  lea     edx, [r9+19h]; TokenInformationClass
0x18004ec09  call    cs:__imp_GetTokenInformation
0x18004ec0f  test    eax, eax
0x18004ec11  jz      short loc_18004EC1A
0x18004ec13  cmp     [rsp+58h+TokenInformation], ebx
0x18004ec17  setnz   bl
0x18004ec1a  call    cs:__imp_RpcRevertToSelf
0x18004ec20  mov     rcx, [rsp+58h+TokenHandle]; hObject
0x18004ec25  test    rcx, rcx
0x18004ec28  jz      short loc_18004EC30
0x18004ec2a  call    cs:__imp_CloseHandle
0x18004ec30  mov     eax, ebx
0x18004ec32  mov     rcx, [rsp+58h+var_18]
0x18004ec37  xor     rcx, rsp; StackCookie
0x18004ec3a  call    __security_check_cookie
0x18004ec3f  add     rsp, 50h
0x18004ec43  pop     rbx
0x18004ec44  retn
```
