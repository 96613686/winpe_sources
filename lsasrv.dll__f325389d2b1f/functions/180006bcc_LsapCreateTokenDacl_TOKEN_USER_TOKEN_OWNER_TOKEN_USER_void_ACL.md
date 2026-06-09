# LsapCreateTokenDacl(_TOKEN_USER *,_TOKEN_OWNER *,_TOKEN_USER *,void *,_ACL * *)

- ea: `0x180006bcc`
- end: `0x180006f50`
- name: `?LsapCreateTokenDacl@@YAJPEAU_TOKEN_USER@@PEAU_TOKEN_OWNER@@0PEAXPEAPEAU_ACL@@@Z`
- size: `900`
- prototype: `int(struct _TOKEN_USER *, struct _TOKEN_OWNER *, struct _TOKEN_USER *, void *, struct _ACL **)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180006240`
- `0x1800f0860`

## callees

- `0x180006bcc`
- `0x180016f70`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180006c2e`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180006c2e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180006bf8`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180006bf8`
- `ntdll!RtlCreateSecurityDescriptor` at `0x180006e66`
- `ntdll!RtlCreateSecurityDescriptor` at `0x180006e66`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x180006e7d`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x180006e7d`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x180006f3f`
- `ntdll!RtlSetOwnerSecurityDescriptor` at `0x180006f3f`
- `ntdll!NtClose` at `0x180006cad`
- `ntdll!NtClose` at `0x180006cad`
- `ntdll!RtlAddAccessAllowedAce` at `0x180006dec`
- `ntdll!RtlAddAccessAllowedAce` at `0x180006e11`
- `ntdll!RtlAddAccessAllowedAce` at `0x180006e36`
- `ntdll!RtlAddAccessAllowedAce` at `0x180006e52`
- `ntdll!RtlAddAccessAllowedAce` at `0x180006f25`
- `ntdll!RtlAddAccessAllowedAce` at `0x180006dec`
- `ntdll!RtlAddAccessAllowedAce` at `0x180006e11`
- `ntdll!RtlAddAccessAllowedAce` at `0x180006e36`
- `ntdll!RtlAddAccessAllowedAce` at `0x180006e52`
- `ntdll!RtlAddAccessAllowedAce` at `0x180006f25`
- `ntdll!RtlCreateAcl` at `0x180006dc5`
- `ntdll!RtlCreateAcl` at `0x180006dc5`
- `ntdll!RtlLengthSid` at `0x180006d58`
- `ntdll!RtlLengthSid` at `0x180006d69`
- `ntdll!RtlLengthSid` at `0x180006d94`
- `ntdll!RtlLengthSid` at `0x180006eeb`
- `ntdll!RtlLengthSid` at `0x180006f04`
- `ntdll!RtlLengthSid` at `0x180006d58`
- `ntdll!RtlLengthSid` at `0x180006d69`
- `ntdll!RtlLengthSid` at `0x180006d94`
- `ntdll!RtlLengthSid` at `0x180006eeb`
- `ntdll!RtlLengthSid` at `0x180006f04`
- `ntdll!RtlEqualSid` at `0x180006cc9`
- `ntdll!RtlEqualSid` at `0x180006cea`
- `ntdll!RtlEqualSid` at `0x180006d11`
- `ntdll!RtlEqualSid` at `0x180006ec2`
- `ntdll!RtlEqualSid` at `0x180006cc9`
- `ntdll!RtlEqualSid` at `0x180006cea`
- `ntdll!RtlEqualSid` at `0x180006d11`
- `ntdll!RtlEqualSid` at `0x180006ec2`
- `ntdll!NtQueryInformationToken` at `0x180006c66`
- `ntdll!NtQueryInformationToken` at `0x180006c93`
- `ntdll!NtQueryInformationToken` at `0x180006c66`
- `ntdll!NtQueryInformationToken` at `0x180006c93`

## pseudocode

```c
__int64 __fastcall LsapCreateTokenDacl(
        struct _TOKEN_USER *a1,
        struct _TOKEN_OWNER *a2,
        struct _TOKEN_USER *a3,
        PSID *a4,
        struct _ACL **a5)
{
  struct _ACL *v7; // rbp
  HANDLE *Value; // rax
  struct _ACL **v9; // r12
  PSID *v10; // r15
  PSID *v11; // r14
  void *v12; // rbx
  ULONG v13; // edi
  ULONG v14; // ebx
  struct _ACL *v15; // rax
  __int64 result; // rax
  void *TokenHandle; // [rsp+70h] [rbp+8h] BYREF
  struct _TOKEN_OWNER *ReturnLength; // [rsp+78h] [rbp+10h] BYREF

  ReturnLength = a2;
  TokenHandle = a1;
  v7 = 0;
  Value = (HANDLE *)TlsGetValue(dwSession);
  v9 = a5;
  TokenHandle = 0;
  LODWORD(ReturnLength) = 0;
  *a5 = 0;
  if ( Value )
  {
    if ( OpenProcessToken(Value[5], 8u, &TokenHandle) )
    {
      v10 = 0;
      if ( NtQueryInformationToken(TokenHandle, TokenUser, a4 + 5, 0x40u, (PULONG)&ReturnLength) >= 0 )
        v10 = a4 + 5;
      v11 = 0;
      if ( NtQueryInformationToken(TokenHandle, TokenOwner, a4 + 13, 0x40u, (PULONG)&ReturnLength) >= 0 )
        v11 = a4 + 13;
      NtClose(TokenHandle);
      if ( v10 )
      {
        if ( v11 && RtlEqualSid(*v11, *v10) )
          v11 = 0;
        if ( a3 && RtlEqualSid(a3->User.Sid, *v10) )
          a3 = 0;
        if ( RtlEqualSid(*v10, *((PSID *)WellKnownSids + 90)) )
        {
          v10 = 0;
          v11 = 0;
        }
      }
    }
    else
    {
      v11 = 0;
      v10 = 0;
    }
    if ( a3 && RtlEqualSid(a3->User.Sid, *((PSID *)WellKnownSids + 90)) )
      a3 = 0;
    if ( v10 || v11 || a3 )
    {
      v12 = (void *)*((_QWORD *)WellKnownSids + 90);
      v13 = RtlLengthSid(*((PSID *)WellKnownSids + 96));
      v14 = v13 + RtlLengthSid(v12) + 24;
      if ( v11 )
        v14 += RtlLengthSid(*v11) + 8;
      if ( v10 )
        v14 += RtlLengthSid(*v10) + 8;
      if ( a3 )
        v14 += RtlLengthSid(a3->User.Sid) + 8;
      v15 = (struct _ACL *)LsapAllocate(v14);
      v7 = v15;
      if ( v15 )
      {
        RtlCreateAcl(v15, v14, 2u);
        RtlAddAccessAllowedAce(v7, 2u, 0xF01FFu, *((PSID *)WellKnownSids + 90));
        RtlAddAccessAllowedAce(v7, 2u, 0x20008u, *((PSID *)WellKnownSids + 96));
        if ( v11 )
          RtlAddAccessAllowedAce(v7, 2u, 0xF01FFu, *v11);
        if ( v10 )
          RtlAddAccessAllowedAce(v7, 2u, 0xF01FFu, *v10);
        if ( a3 )
          RtlAddAccessAllowedAce(v7, 2u, 0xF01FFu, a3->User.Sid);
        RtlCreateSecurityDescriptor(a4, 1u);
        RtlSetDaclSecurityDescriptor(a4, 1u, v7, 0);
        if ( v11 )
          RtlSetOwnerSecurityDescriptor(a4, *v11, 0);
      }
    }
  }
  result = 0;
  *v9 = v7;
  return result;
}

```

## disassembly

```asm
0x180006bcc  mov     [rsp+arg_10], rbx
0x180006bd1  mov     [rsp+arg_8], rdx
0x180006bd6  mov     [rsp+TokenHandle], rcx
0x180006bdb  push    rbp
0x180006bdc  push    rsi
0x180006bdd  push    rdi
0x180006bde  push    r12
0x180006be0  push    r13
0x180006be2  push    r14
0x180006be4  push    r15
0x180006be6  sub     rsp, 30h
0x180006bea  mov     ecx, cs:?dwSession@@3KA; dwTlsIndex
0x180006bf0  mov     r13, r9
0x180006bf3  mov     rsi, r8
0x180006bf6  xor     ebp, ebp
0x180006bf8  call    cs:__imp_TlsGetValue
0x180006bff  nop     dword ptr [rax+rax+00h]
0x180006c04  mov     r12, [rsp+68h+arg_20]
0x180006c0c  mov     [rsp+68h+TokenHandle], rbp
0x180006c11  mov     dword ptr [rsp+68h+arg_8], ebp
0x180006c15  mov     [r12], rbp
0x180006c19  test    rax, rax
0x180006c1c  jz      loc_180006E92
0x180006c22  mov     rcx, [rax+28h]; ProcessHandle
0x180006c26  lea     r8, [rsp+68h+TokenHandle]; TokenHandle
0x180006c2b  lea     edx, [rbp+8]; DesiredAccess
0x180006c2e  call    cs:__imp_OpenProcessToken
0x180006c35  nop     dword ptr [rax+rax+00h]
0x180006c3a  test    eax, eax
0x180006c3c  jz      loc_180006EDD
0x180006c42  mov     rcx, [rsp+68h+TokenHandle]; TokenHandle
0x180006c47  lea     rax, [rsp+68h+arg_8]
0x180006c4c  lea     rbx, [r13+28h]
0x180006c50  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x180006c55  lea     r14d, [rbp+40h]
0x180006c59  mov     r8, rbx; TokenInformation
0x180006c5c  mov     r9d, r14d; TokenInformationLength
0x180006c5f  lea     edx, [rbp+1]; TokenInformationClass
0x180006c62  lea     rdi, [r13+68h]
0x180006c66  call    cs:__imp_NtQueryInformationToken
0x180006c6d  nop     dword ptr [rax+rax+00h]
0x180006c72  mov     rcx, [rsp+68h+TokenHandle]; TokenHandle
0x180006c77  lea     edx, [rbp+4]; TokenInformationClass
0x180006c7a  xor     r15d, r15d
0x180006c7d  mov     r9d, r14d; TokenInformationLength
0x180006c80  test    eax, eax
0x180006c82  mov     r8, rdi; TokenInformation
0x180006c85  lea     rax, [rsp+68h+arg_8]
0x180006c8a  cmovns  r15, rbx
0x180006c8e  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x180006c93  call    cs:__imp_NtQueryInformationToken
0x180006c9a  nop     dword ptr [rax+rax+00h]
0x180006c9f  mov     rcx, [rsp+68h+TokenHandle]; Handle
0x180006ca4  xor     r14d, r14d
0x180006ca7  test    eax, eax
0x180006ca9  cmovns  r14, rdi
0x180006cad  call    cs:__imp_NtClose
0x180006cb4  nop     dword ptr [rax+rax+00h]
0x180006cb9  test    r15, r15
0x180006cbc  jz      short loc_180006D27
0x180006cbe  test    r14, r14
0x180006cc1  jz      short loc_180006CDF
0x180006cc3  mov     rdx, [r15]; Sid2
0x180006cc6  mov     rcx, [r14]; Sid1
0x180006cc9  call    cs:__imp_RtlEqualSid
0x180006cd0  nop     dword ptr [rax+rax+00h]
0x180006cd5  mov     cl, al
0x180006cd7  xor     eax, eax
0x180006cd9  test    cl, cl
0x180006cdb  cmovnz  r14, rax
0x180006cdf  test    rsi, rsi
0x180006ce2  jz      short loc_180006D00
0x180006ce4  mov     rdx, [r15]; Sid2
0x180006ce7  mov     rcx, [rsi]; Sid1
0x180006cea  call    cs:__imp_RtlEqualSid
0x180006cf1  nop     dword ptr [rax+rax+00h]
0x180006cf6  mov     cl, al
0x180006cf8  xor     eax, eax
0x180006cfa  test    cl, cl
0x180006cfc  cmovnz  rsi, rax
0x180006d00  mov     rdx, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x180006d07  mov     rcx, [r15]; Sid1
0x180006d0a  mov     rdx, [rdx+2D0h]; Sid2
0x180006d11  call    cs:__imp_RtlEqualSid
0x180006d18  nop     dword ptr [rax+rax+00h]
0x180006d1d  test    al, al
0x180006d1f  jz      short loc_180006D27
0x180006d21  xor     r15d, r15d
0x180006d24  xor     r14d, r14d
0x180006d27  test    rsi, rsi
0x180006d2a  jnz     loc_180006EB1
0x180006d30  test    r15, r15
0x180006d33  jnz     short loc_180006D43
0x180006d35  test    r14, r14
0x180006d38  jnz     short loc_180006D43
0x180006d3a  test    rsi, rsi
0x180006d3d  jz      loc_180006E92
0x180006d43  mov     rax, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x180006d4a  mov     rcx, [rax+300h]; Sid
0x180006d51  mov     rbx, [rax+2D0h]
0x180006d58  call    cs:__imp_RtlLengthSid
0x180006d5f  nop     dword ptr [rax+rax+00h]
0x180006d64  mov     rcx, rbx; Sid
0x180006d67  mov     edi, eax
0x180006d69  call    cs:__imp_RtlLengthSid
0x180006d70  nop     dword ptr [rax+rax+00h]
0x180006d75  lea     ebx, [rax+18h]
0x180006d78  add     ebx, edi
0x180006d7a  test    r14, r14
0x180006d7d  jnz     loc_180006EE8
0x180006d83  test    r15, r15
0x180006d86  jnz     loc_180006F01
0x180006d8c  test    rsi, rsi
0x180006d8f  jz      short loc_180006DA5
0x180006d91  mov     rcx, [rsi]; Sid
0x180006d94  call    cs:__imp_RtlLengthSid
0x180006d9b  nop     dword ptr [rax+rax+00h]
0x180006da0  add     ebx, 8
0x180006da3  add     ebx, eax
0x180006da5  mov     ecx, ebx
0x180006da7  call    LsapAllocate
0x180006dac  mov     rbp, rax
0x180006daf  test    rax, rax
0x180006db2  jz      loc_180006E92
0x180006db8  mov     edi, 2
0x180006dbd  mov     edx, ebx; AclSize
0x180006dbf  mov     r8d, edi; AclRevision
0x180006dc2  mov     rcx, rax; Acl
0x180006dc5  call    cs:__imp_RtlCreateAcl
0x180006dcc  nop     dword ptr [rax+rax+00h]
0x180006dd1  mov     r9, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x180006dd8  mov     ebx, 0F01FFh
0x180006ddd  mov     r8d, ebx; AccessMask
0x180006de0  mov     edx, edi; Revision
0x180006de2  mov     rcx, rbp; Acl
0x180006de5  mov     r9, [r9+2D0h]; Sid
0x180006dec  call    cs:__imp_RtlAddAccessAllowedAce
0x180006df3  nop     dword ptr [rax+rax+00h]
0x180006df8  mov     r9, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x180006dff  mov     r8d, 20008h; AccessMask
0x180006e05  mov     edx, edi; Revision
0x180006e07  mov     rcx, rbp; Acl
0x180006e0a  mov     r9, [r9+300h]; Sid
0x180006e11  call    cs:__imp_RtlAddAccessAllowedAce
0x180006e18  nop     dword ptr [rax+rax+00h]
0x180006e1d  test    r14, r14
0x180006e20  jnz     loc_180006F1A
0x180006e26  test    r15, r15
0x180006e29  jz      short loc_180006E42
0x180006e2b  mov     r9, [r15]; Sid
0x180006e2e  mov     r8d, ebx; AccessMask
0x180006e31  mov     edx, edi; Revision
0x180006e33  mov     rcx, rbp; Acl
0x180006e36  call    cs:__imp_RtlAddAccessAllowedAce
0x180006e3d  nop     dword ptr [rax+rax+00h]
0x180006e42  test    rsi, rsi
0x180006e45  jz      short loc_180006E5E
0x180006e47  mov     r9, [rsi]; Sid
0x180006e4a  mov     r8d, ebx; AccessMask
0x180006e4d  mov     edx, edi; Revision
0x180006e4f  mov     rcx, rbp; Acl
0x180006e52  call    cs:__imp_RtlAddAccessAllowedAce
0x180006e59  nop     dword ptr [rax+rax+00h]
0x180006e5e  mov     edx, 1; Revision
0x180006e63  mov     rcx, r13; SecurityDescriptor
0x180006e66  call    cs:__imp_RtlCreateSecurityDescriptor
0x180006e6d  nop     dword ptr [rax+rax+00h]
0x180006e72  xor     r9d, r9d; DaclDefaulted
0x180006e75  mov     r8, rbp; Dacl
0x180006e78  mov     dl, 1; DaclPresent
0x180006e7a  mov     rcx, r13; SecurityDescriptor
0x180006e7d  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x180006e84  nop     dword ptr [rax+rax+00h]
0x180006e89  test    r14, r14
0x180006e8c  jnz     loc_180006F36
0x180006e92  mov     rbx, [rsp+68h+arg_10]
0x180006e9a  xor     eax, eax
0x180006e9c  mov     [r12], rbp
0x180006ea0  add     rsp, 30h
0x180006ea4  pop     r15
0x180006ea6  pop     r14
0x180006ea8  pop     r13
0x180006eaa  pop     r12
0x180006eac  pop     rdi
0x180006ead  pop     rsi
0x180006eae  pop     rbp
0x180006eaf  retn
0x180006eb1  mov     rdx, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x180006eb8  mov     rcx, [rsi]; Sid1
0x180006ebb  mov     rdx, [rdx+2D0h]; Sid2
0x180006ec2  call    cs:__imp_RtlEqualSid
0x180006ec9  nop     dword ptr [rax+rax+00h]
0x180006ece  mov     cl, al
0x180006ed0  xor     eax, eax
0x180006ed2  test    cl, cl
0x180006ed4  cmovnz  rsi, rax
0x180006ed8  jmp     loc_180006D30
0x180006edd  xor     r14d, r14d
0x180006ee0  xor     r15d, r15d
0x180006ee3  jmp     loc_180006D27
0x180006ee8  mov     rcx, [r14]; Sid
0x180006eeb  call    cs:__imp_RtlLengthSid
0x180006ef2  nop     dword ptr [rax+rax+00h]
0x180006ef7  add     ebx, 8
0x180006efa  add     ebx, eax
0x180006efc  jmp     loc_180006D83
0x180006f01  mov     rcx, [r15]; Sid
0x180006f04  call    cs:__imp_RtlLengthSid
0x180006f0b  nop     dword ptr [rax+rax+00h]
0x180006f10  add     ebx, 8
0x180006f13  add     ebx, eax
0x180006f15  jmp     loc_180006D8C
0x180006f1a  mov     r9, [r14]; Sid
0x180006f1d  mov     r8d, ebx; AccessMask
0x180006f20  mov     edx, edi; Revision
0x180006f22  mov     rcx, rbp; Acl
0x180006f25  call    cs:__imp_RtlAddAccessAllowedAce
0x180006f2c  nop     dword ptr [rax+rax+00h]
0x180006f31  jmp     loc_180006E26
0x180006f36  mov     rdx, [r14]; Owner
0x180006f39  xor     r8d, r8d; OwnerDefaulted
0x180006f3c  mov     rcx, r13; SecurityDescriptor
0x180006f3f  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x180006f46  nop     dword ptr [rax+rax+00h]
0x180006f4b  jmp     loc_180006E92
```
