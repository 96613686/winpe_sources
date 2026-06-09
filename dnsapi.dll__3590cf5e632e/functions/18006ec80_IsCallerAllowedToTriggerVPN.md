# IsCallerAllowedToTriggerVPN

- ea: `0x18006ec80`
- end: `0x18006ee91`
- name: `IsCallerAllowedToTriggerVPN`
- size: `529`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004c58c`

## callees

- `0x180029d80`
- `0x18002b050`
- `0x18006ec80`
- `0x18008b5f0`
- `0x1800dc9e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ed26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ee4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ed26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006ee4a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006ee80`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006ee80`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18006ecec`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18006ecec`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006ecd2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006ecd2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18006ed1a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18006ed65`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18006ed1a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18006ed65`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18006edef`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x18006edef`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18006ee07`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x18006ee07`
- `RPCRT4!RpcRevertToSelf` at `0x18006ee62`
- `RPCRT4!RpcRevertToSelf` at `0x18006ee62`
- `RPCRT4!RpcImpersonateClient` at `0x18006edcd`
- `RPCRT4!RpcImpersonateClient` at `0x18006edcd`

## pseudocode

```c
__int64 __fastcall IsCallerAllowedToTriggerVPN(__int64 a1)
{
  unsigned int v1; // edi
  int v2; // r14d
  unsigned int *v3; // rbx
  HANDLE CurrentThread; // rax
  unsigned int i; // esi
  void *v7; // rcx
  unsigned int v8; // eax
  DWORD TokenInformationLength; // [rsp+30h] [rbp-38h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-30h] BYREF

  v1 = 1;
  TokenHandle = 0;
  TokenInformationLength = 0;
  if ( !dword_180111750 )
    return v1;
  v2 = 0;
  if ( a1 )
  {
    v7 = *(void **)(a1 + 32);
    if ( !v7 )
      return v1;
    v8 = RpcImpersonateClient(v7);
    if ( v8 )
    {
      if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
        WPP_SF_d(1035, 24, WPP_a926a247b0b234ea84f90821b2555b1e_Traceguids, v8);
      goto LABEL_13;
    }
    v2 = 1;
  }
  v3 = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 0, &TokenHandle)
    || (GetTokenInformation(TokenHandle, TokenGroups, 0, 0, &TokenInformationLength), GetLastError() != 122) )
  {
LABEL_24:
    GetLastError();
    goto LABEL_9;
  }
  v3 = (unsigned int *)Dns_Allocate(TokenInformationLength);
  if ( v3 )
  {
    if ( GetTokenInformation(TokenHandle, TokenGroups, v3, TokenInformationLength, &TokenInformationLength) )
    {
      for ( i = 0; i < *v3; ++i )
      {
        if ( *GetSidSubAuthorityCount(*(PSID *)&v3[4 * i + 2]) && *GetSidSubAuthority(*(PSID *)&v3[4 * i + 2], 0) == 80 )
        {
          v1 = 0;
          goto LABEL_9;
        }
      }
      goto LABEL_9;
    }
    goto LABEL_24;
  }
LABEL_9:
  if ( v2 )
    RpcRevertToSelf();
  if ( v3 )
    DnsApiFree(v3);
LABEL_13:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return v1;
}

```

## disassembly

```asm
0x18006ec80  mov     [rsp+arg_8], rbx
0x18006ec85  mov     [rsp+arg_10], rbp
0x18006ec8a  push    rsi
0x18006ec8b  push    rdi
0x18006ec8c  push    r14
0x18006ec8e  sub     rsp, 50h
0x18006ec92  mov     rax, cs:__security_cookie
0x18006ec99  xor     rax, rsp
0x18006ec9c  mov     [rsp+68h+var_28], rax
0x18006eca1  cmp     cs:dword_180111750, 0
0x18006eca8  mov     edi, 1
0x18006ecad  mov     [rsp+68h+TokenHandle], 0
0x18006ecb6  mov     [rsp+68h+TokenInformationLength], 0
0x18006ecbe  jz      loc_18006ED9F
0x18006ecc4  xor     r14d, r14d
0x18006ecc7  test    rcx, rcx
0x18006ecca  jnz     loc_18006EDC4
0x18006ecd0  xor     ebx, ebx
0x18006ecd2  call    cs:__imp_GetCurrentThread
0x18006ecd9  nop     dword ptr [rax+rax+00h]
0x18006ecde  lea     r9, [rsp+68h+TokenHandle]; TokenHandle
0x18006ece3  xor     r8d, r8d; OpenAsSelf
0x18006ece6  mov     rcx, rax; ThreadHandle
0x18006ece9  lea     edx, [rbx+8]; DesiredAccess
0x18006ecec  call    cs:__imp_OpenThreadToken
0x18006ecf3  nop     dword ptr [rax+rax+00h]
0x18006ecf8  test    eax, eax
0x18006ecfa  jz      loc_18006EE4A
0x18006ed00  mov     rcx, [rsp+68h+TokenHandle]; TokenHandle
0x18006ed05  lea     rax, [rsp+68h+TokenInformationLength]
0x18006ed0a  lea     esi, [rbx+2]
0x18006ed0d  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x18006ed12  mov     edx, esi; TokenInformationClass
0x18006ed14  xor     r9d, r9d; TokenInformationLength
0x18006ed17  xor     r8d, r8d; TokenInformation
0x18006ed1a  call    cs:__imp_GetTokenInformation
0x18006ed21  nop     dword ptr [rax+rax+00h]
0x18006ed26  call    cs:__imp_GetLastError
0x18006ed2d  nop     dword ptr [rax+rax+00h]
0x18006ed32  cmp     eax, 7Ah ; 'z'
0x18006ed35  jnz     loc_18006EE4A
0x18006ed3b  mov     ecx, [rsp+68h+TokenInformationLength]
0x18006ed3f  call    Dns_Allocate
0x18006ed44  mov     rbx, rax
0x18006ed47  test    rax, rax
0x18006ed4a  jz      short loc_18006ED7F
0x18006ed4c  mov     r9d, [rsp+68h+TokenInformationLength]; TokenInformationLength
0x18006ed51  lea     rax, [rsp+68h+TokenInformationLength]
0x18006ed56  mov     rcx, [rsp+68h+TokenHandle]; TokenHandle
0x18006ed5b  mov     r8, rbx; TokenInformation
0x18006ed5e  mov     edx, esi; TokenInformationClass
0x18006ed60  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x18006ed65  call    cs:__imp_GetTokenInformation
0x18006ed6c  nop     dword ptr [rax+rax+00h]
0x18006ed71  test    eax, eax
0x18006ed73  jz      loc_18006EE4A
0x18006ed79  xor     esi, esi
0x18006ed7b  cmp     esi, [rbx]
0x18006ed7d  jb      short loc_18006EDE5
0x18006ed7f  test    r14d, r14d
0x18006ed82  jnz     loc_18006EE62
0x18006ed88  test    rbx, rbx
0x18006ed8b  jnz     loc_18006EE73
0x18006ed91  mov     rcx, [rsp+68h+TokenHandle]; hObject
0x18006ed96  test    rcx, rcx
0x18006ed99  jnz     loc_18006EE80
0x18006ed9f  mov     eax, edi
0x18006eda1  mov     rcx, [rsp+68h+var_28]
0x18006eda6  xor     rcx, rsp; StackCookie
0x18006eda9  call    __security_check_cookie
0x18006edae  lea     r11, [rsp+68h+var_18]
0x18006edb3  mov     rbx, [r11+28h]
0x18006edb7  mov     rbp, [r11+30h]
0x18006edbb  mov     rsp, r11
0x18006edbe  pop     r14
0x18006edc0  pop     rdi
0x18006edc1  pop     rsi
0x18006edc2  retn
0x18006edc4  mov     rcx, [rcx+20h]; BindingHandle
0x18006edc8  test    rcx, rcx
0x18006edcb  jz      short loc_18006ED9F
0x18006edcd  call    cs:__imp_RpcImpersonateClient
0x18006edd4  nop     dword ptr [rax+rax+00h]
0x18006edd9  test    eax, eax
0x18006eddb  jnz     short loc_18006EE1F
0x18006eddd  mov     r14d, edi
0x18006ede0  jmp     loc_18006ECD0
0x18006ede5  mov     ebp, esi
0x18006ede7  add     rbp, rbp
0x18006edea  mov     rcx, [rbx+rbp*8+8]; pSid
0x18006edef  call    cs:__imp_GetSidSubAuthorityCount
0x18006edf6  nop     dword ptr [rax+rax+00h]
0x18006edfb  cmp     byte ptr [rax], 0
0x18006edfe  jz      short loc_18006EE5B
0x18006ee00  mov     rcx, [rbx+rbp*8+8]; pSid
0x18006ee05  xor     edx, edx; nSubAuthority
0x18006ee07  call    cs:__imp_GetSidSubAuthority
0x18006ee0e  nop     dword ptr [rax+rax+00h]
0x18006ee13  cmp     dword ptr [rax], 50h ; 'P'
0x18006ee16  jnz     short loc_18006EE5B
0x18006ee18  xor     edi, edi
0x18006ee1a  jmp     loc_18006ED7F
0x18006ee1f  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18006ee26  jz      loc_18006ED91
0x18006ee2c  mov     edx, 18h
0x18006ee31  lea     r8, WPP_a926a247b0b234ea84f90821b2555b1e_Traceguids
0x18006ee38  mov     ecx, 40Bh
0x18006ee3d  mov     r9d, eax
0x18006ee40  call    WPP_SF_d
0x18006ee45  jmp     loc_18006ED91
0x18006ee4a  call    cs:__imp_GetLastError
0x18006ee51  nop     dword ptr [rax+rax+00h]
0x18006ee56  jmp     loc_18006ED7F
0x18006ee5b  add     esi, edi
0x18006ee5d  jmp     loc_18006ED7B
0x18006ee62  call    cs:__imp_RpcRevertToSelf
0x18006ee69  nop     dword ptr [rax+rax+00h]
0x18006ee6e  jmp     loc_18006ED88
0x18006ee73  mov     rcx, rbx; lpMem
0x18006ee76  call    DnsApiFree
0x18006ee7b  jmp     loc_18006ED91
0x18006ee80  call    cs:__imp_CloseHandle
0x18006ee87  nop     dword ptr [rax+rax+00h]
0x18006ee8c  jmp     loc_18006ED9F
```
