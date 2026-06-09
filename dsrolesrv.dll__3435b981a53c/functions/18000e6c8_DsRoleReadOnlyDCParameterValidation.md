# DsRoleReadOnlyDCParameterValidation

- ea: `0x18000e6c8`
- end: `0x18000e812`
- name: `DsRoleReadOnlyDCParameterValidation`
- size: `330`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180012460`

## callees

- `0x18000e6c8`
- `0x180016538`
- `0x18001e624`
- `0x18001e6b0`
- `0x180020dbc`

## import_xrefs

- `WLDAP32!__imp_ldap_unbind` at `0x18000e7fc`
- `WLDAP32!__imp_ldap_unbind` at `0x18002c490`
- `WLDAP32!__imp_ldap_unbind` at `0x18000e7fc`
- `WLDAP32!__imp_ldap_unbind` at `0x18002c490`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18000e736`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18000e774`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18000e736`
- `WLDAP32!__imp_LdapMapErrorToWin32` at `0x18000e774`

## string_xrefs

- `0x18000e723`: `Promoting Read only DC failed with ldap error %d. Couldn't connect to replica server %ws\n`
- `0x18000e7a1`: `Promoting Read only DC failed with ldap error %d. Searching for supportedCapabilities failed on server %ws\n`
- `0x18000e7ca`: `Promoting Read only DC failed with ldap error %d. Helper DC %ws is not a Windows Server 2008 writeable DC\n`

## pseudocode

```c
__int64 __fastcall DsRoleReadOnlyDCParameterValidation(__int64 a1, _WORD *a2)
{
  _WORD *v2; // rbx
  unsigned __int64 v3; // rax
  ULONG LdapHandle; // eax
  ULONG v5; // esi
  ULONG v6; // eax
  unsigned int v7; // edi
  __int64 v8; // rdx
  __int64 v9; // rcx
  ULONG HasSupportedCapability; // eax
  ULONG v11; // esi
  ULONG v12; // eax
  LDAP *ld; // [rsp+70h] [rbp+18h] BYREF

  v2 = a2;
  ld = 0;
  v3 = -1;
  do
    ++v3;
  while ( a2[v3] );
  if ( v3 > 2 && *a2 == 92 )
    v2 = a2 + 2;
  LdapHandle = DsRoleGetLdapHandle(v2, &ld);
  v5 = LdapHandle;
  if ( LdapHandle )
  {
    DsRolepLogPrintRoutine(
      1,
      "Promoting Read only DC failed with ldap error %d. Couldn't connect to replica server %ws\n",
      LdapHandle,
      v2);
    v6 = LdapMapErrorToWin32(v5);
    v7 = v6;
    if ( !v6 )
      goto LABEL_15;
    v8 = 2147512891LL;
    v9 = v6;
    goto LABEL_14;
  }
  HasSupportedCapability = DsRoleServerHasSupportedCapability(ld);
  v11 = HasSupportedCapability;
  if ( !HasSupportedCapability )
  {
    v7 = 1355;
    DsRolepLogPrintRoutine(
      1,
      "Promoting Read only DC failed with ldap error %d. Helper DC %ws is not a Windows Server 2008 writeable DC\n",
      0,
      v2);
    v8 = 2147512892LL;
    v9 = 1355;
LABEL_14:
    DsRolepSetFailureMessage(v9, v8, v2, 0, 0);
    goto LABEL_15;
  }
  v12 = LdapMapErrorToWin32(HasSupportedCapability);
  v7 = v12;
  if ( v12 )
    DsRolepSetFailureMessage(v12, 2147512891LL, v2, 0, 0);
  DsRolepLogPrintRoutine(
    1,
    "Promoting Read only DC failed with ldap error %d. Searching for supportedCapabilities failed on server %ws\n",
    v11,
    v2);
LABEL_15:
  if ( ld )
    ldap_unbind(ld);
  return v7;
}

```

## disassembly

```asm
0x18000e6c8  mov     rax, rsp
0x18000e6cb  mov     [rax+10h], rbx
0x18000e6cf  mov     [rax+8], rcx
0x18000e6d3  push    rsi
0x18000e6d4  push    rdi
0x18000e6d5  push    r14
0x18000e6d7  sub     rsp, 40h
0x18000e6db  mov     rbx, rdx
0x18000e6de  xor     r14d, r14d
0x18000e6e1  mov     [rax+18h], r14
0x18000e6e5  mov     [rax+8], r14d
0x18000e6e9  mov     edi, r14d
0x18000e6ec  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000e6f0  inc     rax
0x18000e6f3  cmp     [rdx+rax*2], r14w
0x18000e6f8  jnz     short loc_18000E6F0
0x18000e6fa  cmp     rax, 2
0x18000e6fe  jbe     short loc_18000E70A
0x18000e700  cmp     word ptr [rdx], 5Ch ; '\'
0x18000e704  jnz     short loc_18000E70A
0x18000e706  add     rbx, 4
0x18000e70a  lea     rdx, [rsp+58h+ld]
0x18000e70f  mov     rcx, rbx
0x18000e712  call    DsRoleGetLdapHandle
0x18000e717  mov     esi, eax
0x18000e719  test    eax, eax
0x18000e71b  jz      short loc_18000E756
0x18000e71d  mov     r9, rbx
0x18000e720  mov     r8d, eax
0x18000e723  lea     rdx, aPromotingReadO_1; "Promoting Read only DC failed with ldap"...
0x18000e72a  mov     ecx, 1
0x18000e72f  call    DsRolepLogPrintRoutine
0x18000e734  mov     ecx, esi; LdapError
0x18000e736  call    cs:__imp_LdapMapErrorToWin32
0x18000e73c  mov     edi, eax
0x18000e73e  mov     [rsp+58h+var_28], eax
0x18000e742  test    eax, eax
0x18000e744  jz      loc_18000E7F2
0x18000e74a  mov     edx, 8000723Bh
0x18000e74f  mov     ecx, eax
0x18000e751  jmp     loc_18000E7E1
0x18000e756  lea     r8, [rsp+58h+arg_0]
0x18000e75b  lea     rdx, a12840113556141; "1.2.840.113556.1.4.1935"
0x18000e762  mov     rcx, [rsp+58h+ld]; ld
0x18000e767  call    DsRoleServerHasSupportedCapability
0x18000e76c  mov     esi, eax
0x18000e76e  test    eax, eax
0x18000e770  jz      short loc_18000E7B4
0x18000e772  mov     ecx, eax; LdapError
0x18000e774  call    cs:__imp_LdapMapErrorToWin32
0x18000e77a  mov     edi, eax
0x18000e77c  mov     [rsp+58h+var_28], eax
0x18000e780  test    eax, eax
0x18000e782  jz      short loc_18000E79B
0x18000e784  mov     [rsp+58h+var_38], r14
0x18000e789  xor     r9d, r9d
0x18000e78c  mov     r8, rbx
0x18000e78f  mov     edx, 8000723Bh
0x18000e794  mov     ecx, eax
0x18000e796  call    DsRolepSetFailureMessage
0x18000e79b  mov     r9, rbx
0x18000e79e  mov     r8d, esi
0x18000e7a1  lea     rdx, aPromotingReadO; "Promoting Read only DC failed with ldap"...
0x18000e7a8  mov     ecx, 1
0x18000e7ad  call    DsRolepLogPrintRoutine
0x18000e7b2  jmp     short loc_18000E7F2
0x18000e7b4  cmp     [rsp+58h+arg_0], r14d
0x18000e7b9  jnz     short loc_18000E7F2
0x18000e7bb  mov     edi, 54Bh
0x18000e7c0  mov     [rsp+58h+var_28], edi
0x18000e7c4  mov     r9, rbx
0x18000e7c7  xor     r8d, r8d
0x18000e7ca  lea     rdx, aPromotingReadO_0; "Promoting Read only DC failed with ldap"...
0x18000e7d1  lea     ecx, [r8+1]
0x18000e7d5  call    DsRolepLogPrintRoutine
0x18000e7da  mov     edx, 8000723Ch
0x18000e7df  mov     ecx, edi
0x18000e7e1  mov     [rsp+58h+var_38], r14
0x18000e7e6  xor     r9d, r9d
0x18000e7e9  mov     r8, rbx
0x18000e7ec  call    DsRolepSetFailureMessage
0x18000e7f1  nop
0x18000e7f2  mov     rcx, [rsp+58h+ld]; ld
0x18000e7f7  test    rcx, rcx
0x18000e7fa  jz      short loc_18000E802
0x18000e7fc  call    cs:__imp_ldap_unbind
0x18000e802  mov     eax, edi
0x18000e804  mov     rbx, [rsp+58h+arg_8]
0x18000e809  add     rsp, 40h
0x18000e80d  pop     r14
0x18000e80f  pop     rdi
0x18000e810  pop     rsi
0x18000e811  retn
0x18002c47e  push    rbp
0x18002c480  sub     rsp, 30h
0x18002c484  mov     rbp, rdx
0x18002c487  mov     rcx, [rbp+70h]; ld
0x18002c48b  test    rcx, rcx
0x18002c48e  jz      short loc_18002C497
0x18002c490  call    cs:__imp_ldap_unbind
0x18002c496  nop
0x18002c497  add     rsp, 30h
0x18002c49b  pop     rbp
0x18002c49c  retn
```
