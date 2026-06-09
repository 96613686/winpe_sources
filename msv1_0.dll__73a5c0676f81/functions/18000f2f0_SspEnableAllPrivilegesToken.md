# SspEnableAllPrivilegesToken

- ea: `0x18000f2f0`
- end: `0x18000f43e`
- name: `SspEnableAllPrivilegesToken`
- size: `334`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800268dc`

## callees

- `0x180006c50`
- `0x180007700`
- `0x18000f2f0`
- `0x18002fb50`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18000f396`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18000f396`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000f33c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000f408`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000f33c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000f408`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f3d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f3df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f3d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f3df`

## pseudocode

```c
__int64 __fastcall SspEnableAllPrivilegesToken(HANDLE TokenHandle)
{
  unsigned int v2; // edi
  struct _TOKEN_PRIVILEGES *v3; // r8
  struct _TOKEN_PRIVILEGES *v4; // rsi
  struct _TOKEN_PRIVILEGES *v5; // rbx
  DWORD v6; // eax
  __int64 v7; // rdx
  BOOL v9; // eax
  DWORD TokenInformationLength[4]; // [rsp+30h] [rbp-238h] BYREF
  _BYTE TokenInformation[512]; // [rsp+40h] [rbp-228h] BYREF

  TokenInformationLength[0] = 512;
  v2 = GetTokenInformation(TokenHandle, TokenPrivileges, TokenInformation, 0x200u, TokenInformationLength);
  if ( v2 )
  {
    v3 = (struct _TOKEN_PRIVILEGES *)TokenInformation;
    v4 = 0;
    v5 = (struct _TOKEN_PRIVILEGES *)TokenInformation;
    goto LABEL_3;
  }
  if ( GetLastError() == 122 )
  {
    v5 = (struct _TOKEN_PRIVILEGES *)NtLmAllocate(TokenInformationLength[0]);
    if ( v5 )
    {
      v9 = GetTokenInformation(TokenHandle, TokenPrivileges, v5, TokenInformationLength[0], TokenInformationLength);
      v3 = v5;
      v4 = v5;
      v2 = v9;
      if ( !v9 )
      {
LABEL_15:
        NtLmFree(v4);
        return v2;
      }
LABEL_3:
      if ( v3->PrivilegeCount )
      {
        v6 = 0;
        do
        {
          v7 = v6++;
          v5->Privileges[v7].Attributes |= 2u;
        }
        while ( v6 < v3->PrivilegeCount );
        v2 = AdjustTokenPrivileges(TokenHandle, 0, v3, 0, 0, 0);
        if ( v2 )
        {
          if ( GetLastError() )
            v2 = 0;
        }
      }
      if ( !v4 )
        return v2;
      goto LABEL_15;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000f2f0  mov     [rsp+arg_8], rbx
0x18000f2f5  mov     [rsp+arg_10], rbp
0x18000f2fa  push    rsi
0x18000f2fb  push    rdi
0x18000f2fc  push    r14
0x18000f2fe  sub     rsp, 250h
0x18000f305  mov     rax, cs:__security_cookie
0x18000f30c  xor     rax, rsp
0x18000f30f  mov     [rsp+268h+var_28], rax
0x18000f317  lea     rax, [rsp+268h+TokenInformationLength]
0x18000f31c  mov     [rsp+268h+TokenInformationLength], 200h
0x18000f324  mov     r9d, 200h; TokenInformationLength
0x18000f32a  mov     [rsp+268h+ReturnLength], rax; ReturnLength
0x18000f32f  lea     r8, [rsp+268h+TokenInformation]; TokenInformation
0x18000f334  mov     edx, 3; TokenInformationClass
0x18000f339  mov     rbp, rcx
0x18000f33c  call    cs:__imp_GetTokenInformation
0x18000f342  xor     r14d, r14d
0x18000f345  mov     edi, eax
0x18000f347  test    eax, eax
0x18000f349  jz      loc_18000F3DF
0x18000f34f  lea     r8, [rsp+268h+TokenInformation]; NewState
0x18000f354  mov     esi, r14d
0x18000f357  mov     rbx, r8
0x18000f35a  mov     ecx, [r8]
0x18000f35d  test    ecx, ecx
0x18000f35f  jz      short loc_18000F3A2
0x18000f361  mov     eax, r14d
0x18000f364  nop     dword ptr [rax+00h]
0x18000f368  nop     dword ptr [rax+rax+00000000h]
0x18000f370  mov     edx, eax
0x18000f372  inc     eax
0x18000f374  inc     rdx
0x18000f377  lea     rdx, [rdx+rdx*2]
0x18000f37b  or      dword ptr [rbx+rdx*4], 2
0x18000f37f  cmp     eax, [r8]
0x18000f382  jb      short loc_18000F370
0x18000f384  mov     [rsp+268h+var_240], r14; ReturnLength
0x18000f389  xor     r9d, r9d; BufferLength
0x18000f38c  xor     edx, edx; DisableAllPrivileges
0x18000f38e  mov     [rsp+268h+ReturnLength], r14; PreviousState
0x18000f393  mov     rcx, rbp; TokenHandle
0x18000f396  call    cs:__imp_AdjustTokenPrivileges
0x18000f39c  mov     edi, eax
0x18000f39e  test    eax, eax
0x18000f3a0  jnz     short loc_18000F3D1
0x18000f3a2  test    rsi, rsi
0x18000f3a5  jnz     short loc_18000F41E
0x18000f3a7  mov     eax, edi
0x18000f3a9  mov     rcx, [rsp+268h+var_28]
0x18000f3b1  xor     rcx, rsp; StackCookie
0x18000f3b4  call    __security_check_cookie
0x18000f3b9  lea     r11, [rsp+268h+var_18]
0x18000f3c1  mov     rbx, [r11+28h]
0x18000f3c5  mov     rbp, [r11+30h]
0x18000f3c9  mov     rsp, r11
0x18000f3cc  pop     r14
0x18000f3ce  pop     rdi
0x18000f3cf  pop     rsi
0x18000f3d0  retn
0x18000f3d1  call    cs:__imp_GetLastError
0x18000f3d7  test    eax, eax
0x18000f3d9  cmovnz  edi, r14d
0x18000f3dd  jmp     short loc_18000F3A2
0x18000f3df  call    cs:__imp_GetLastError
0x18000f3e5  cmp     eax, 7Ah ; 'z'
0x18000f3e8  jz      short loc_18000F42B
0x18000f3ea  xor     eax, eax
0x18000f3ec  jmp     short loc_18000F3A9
0x18000f3ee  mov     r9d, [rsp+268h+TokenInformationLength]; TokenInformationLength
0x18000f3f3  lea     rax, [rsp+268h+TokenInformationLength]
0x18000f3f8  mov     r8, rbx; TokenInformation
0x18000f3fb  mov     [rsp+268h+ReturnLength], rax; ReturnLength
0x18000f400  mov     edx, 3; TokenInformationClass
0x18000f405  mov     rcx, rbp; TokenHandle
0x18000f408  call    cs:__imp_GetTokenInformation
0x18000f40e  mov     r8, rbx
0x18000f411  mov     rsi, rbx
0x18000f414  mov     edi, eax
0x18000f416  test    eax, eax
0x18000f418  jnz     loc_18000F35A
0x18000f41e  mov     rcx, rsi
0x18000f421  call    NtLmFree
0x18000f426  jmp     loc_18000F3A7
0x18000f42b  mov     ecx, [rsp+268h+TokenInformationLength]; uBytes
0x18000f42f  call    NtLmAllocate
0x18000f434  mov     rbx, rax
0x18000f437  test    rax, rax
0x18000f43a  jz      short loc_18000F3EA
0x18000f43c  jmp     short loc_18000F3EE
```
