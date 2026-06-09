# LsapSetDefaultDacl(_LSA_TOKEN_INFORMATION_TYPE,void *,_LSA_TOKEN_INFORMATION_V3 *)

- ea: `0x18007b900`
- end: `0x18007bab3`
- name: `?LsapSetDefaultDacl@@YAJW4_LSA_TOKEN_INFORMATION_TYPE@@PEAXPEAU_LSA_TOKEN_INFORMATION_V3@@@Z`
- size: `435`
- prototype: `__int64 __fastcall(enum _LSA_TOKEN_INFORMATION_TYPE, void *, struct _LSA_TOKEN_INFORMATION_V3 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180059a94`

## callees

- `0x18007b900`
- `0x1800b86d0`
- `0x1800bd6e0`

## import_xrefs

- `ntdll!RtlQueryInformationAcl` at `0x18007b94a`
- `ntdll!RtlQueryInformationAcl` at `0x18007b94a`
- `ntdll!RtlAddAccessAllowedAce` at `0x18007ba44`
- `ntdll!RtlAddAccessAllowedAce` at `0x18007ba6e`
- `ntdll!RtlAddAccessAllowedAce` at `0x18007ba99`
- `ntdll!RtlAddAccessAllowedAce` at `0x18007ba44`
- `ntdll!RtlAddAccessAllowedAce` at `0x18007ba6e`
- `ntdll!RtlAddAccessAllowedAce` at `0x18007ba99`
- `ntdll!RtlCreateAcl` at `0x18007ba20`
- `ntdll!RtlCreateAcl` at `0x18007ba20`
- `ntdll!RtlLengthSid` at `0x18007b9b0`
- `ntdll!RtlLengthSid` at `0x18007b9c2`
- `ntdll!RtlLengthSid` at `0x18007b9ff`
- `ntdll!RtlLengthSid` at `0x18007b9b0`
- `ntdll!RtlLengthSid` at `0x18007b9c2`
- `ntdll!RtlLengthSid` at `0x18007b9ff`

## pseudocode

```c
int __fastcall LsapSetDefaultDacl(
        enum _LSA_TOKEN_INFORMATION_TYPE a1,
        _QWORD *a2,
        struct _LSA_TOKEN_INFORMATION_V3 *a3)
{
  struct _ACL *Sid; // rsi
  int result; // eax
  PSID Owner; // rbp
  struct _ACL *DefaultDacl; // r14
  ULONG v8; // r15d
  ULONG v9; // eax
  PTOKEN_GROUPS Groups; // rdx
  ULONG v11; // r15d
  DWORD i; // ecx
  __int64 Information; // [rsp+20h] [rbp-48h] BYREF
  int v14; // [rsp+28h] [rbp-40h]

  if ( a1 == LsaTokenInformationNull )
    return 0;
  Sid = (struct _ACL *)a2[7];
  if ( Sid )
  {
    Information = 0;
    v14 = 0;
    result = RtlQueryInformationAcl(Sid, &Information, 0xCu, AclSizeInformation);
    if ( result < 0 )
      return result;
    memcpy_0(a3->DefaultDacl.DefaultDacl, Sid, (unsigned int)(HIDWORD(Information) + v14));
    return 0;
  }
  Owner = a3->Owner.Owner;
  DefaultDacl = a3->DefaultDacl.DefaultDacl;
  if ( !Owner )
    Owner = a3->User.User.Sid;
  v8 = RtlLengthSid(*((PSID *)WellKnownSids + 90));
  v9 = RtlLengthSid(Owner);
  Groups = a3->Groups;
  v11 = v9 + v8 + 24;
  for ( i = 0; i < Groups->GroupCount; ++i )
  {
    if ( (Groups->Groups[i].Attributes & 0xC0000000) != 0 )
    {
      Sid = (struct _ACL *)Groups->Groups[i].Sid;
      if ( Sid )
        v11 += RtlLengthSid(Groups->Groups[i].Sid) + 8;
      break;
    }
  }
  result = RtlCreateAcl(DefaultDacl, v11, 2u);
  if ( result >= 0 )
  {
    result = RtlAddAccessAllowedAce(DefaultDacl, 2u, 0x10000000u, Owner);
    if ( result >= 0 )
    {
      result = RtlAddAccessAllowedAce(DefaultDacl, 2u, 0x10000000u, *((PSID *)WellKnownSids + 90));
      if ( result >= 0 )
      {
        if ( Sid )
          return RtlAddAccessAllowedAce(DefaultDacl, 2u, 0xA0000000, Sid);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18007b900  mov     [rsp+arg_0], rbx
0x18007b905  push    rbp
0x18007b906  push    rsi
0x18007b907  push    rdi
0x18007b908  push    r14
0x18007b90a  push    r15
0x18007b90c  sub     rsp, 40h
0x18007b910  mov     rax, cs:__security_cookie
0x18007b917  xor     rax, rsp
0x18007b91a  mov     [rsp+68h+var_38], rax
0x18007b91f  mov     rdi, r8
0x18007b922  test    ecx, ecx
0x18007b924  jz      short loc_18007B970
0x18007b926  mov     rsi, [rdx+38h]
0x18007b92a  test    rsi, rsi
0x18007b92d  jz      short loc_18007B991
0x18007b92f  xor     eax, eax
0x18007b931  lea     rdx, [rsp+68h+Information]; Information
0x18007b936  mov     rcx, rsi; Acl
0x18007b939  mov     [rsp+68h+Information], rax
0x18007b93e  mov     [rsp+68h+var_40], eax
0x18007b942  lea     r9d, [rax+2]; InformationClass
0x18007b946  lea     r8d, [rax+0Ch]; InformationLength
0x18007b94a  call    cs:__imp_RtlQueryInformationAcl
0x18007b951  nop     dword ptr [rax+rax+00h]
0x18007b956  test    eax, eax
0x18007b958  js      short loc_18007B972
0x18007b95a  mov     r8d, [rsp+68h+var_40]
0x18007b95f  mov     rdx, rsi; Src
0x18007b962  add     r8d, dword ptr [rsp+68h+Information+4]; Size
0x18007b967  mov     rcx, [rdi+38h]; void *
0x18007b96b  call    memcpy_0
0x18007b970  xor     eax, eax
0x18007b972  mov     rcx, [rsp+68h+var_38]
0x18007b977  xor     rcx, rsp; StackCookie
0x18007b97a  call    __security_check_cookie
0x18007b97f  mov     rbx, [rsp+68h+arg_0]
0x18007b984  add     rsp, 40h
0x18007b988  pop     r15
0x18007b98a  pop     r14
0x18007b98c  pop     rdi
0x18007b98d  pop     rsi
0x18007b98e  pop     rbp
0x18007b98f  retn
0x18007b991  mov     rbp, [r8+30h]
0x18007b995  mov     r14, [r8+38h]
0x18007b999  test    rbp, rbp
0x18007b99c  jz      loc_18007BAAA
0x18007b9a2  mov     rax, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x18007b9a9  mov     rcx, [rax+2D0h]; Sid
0x18007b9b0  call    cs:__imp_RtlLengthSid
0x18007b9b7  nop     dword ptr [rax+rax+00h]
0x18007b9bc  mov     rcx, rbp; Sid
0x18007b9bf  mov     r15d, eax
0x18007b9c2  call    cs:__imp_RtlLengthSid
0x18007b9c9  nop     dword ptr [rax+rax+00h]
0x18007b9ce  mov     rdx, [rdi+18h]
0x18007b9d2  add     r15d, 18h
0x18007b9d6  add     r15d, eax
0x18007b9d9  xor     ecx, ecx
0x18007b9db  cmp     ecx, [rdx]
0x18007b9dd  jnb     short loc_18007BA12
0x18007b9df  mov     eax, ecx
0x18007b9e1  add     rax, rax
0x18007b9e4  test    dword ptr [rdx+rax*8+10h], 0C0000000h
0x18007b9ec  jnz     short loc_18007B9F2
0x18007b9ee  inc     ecx
0x18007b9f0  jmp     short loc_18007B9DB
0x18007b9f2  mov     rsi, [rdx+rax*8+8]
0x18007b9f7  test    rsi, rsi
0x18007b9fa  jz      short loc_18007BA12
0x18007b9fc  mov     rcx, rsi; Sid
0x18007b9ff  call    cs:__imp_RtlLengthSid
0x18007ba06  nop     dword ptr [rax+rax+00h]
0x18007ba0b  add     r15d, 8
0x18007ba0f  add     r15d, eax
0x18007ba12  mov     ebx, 2
0x18007ba17  mov     edx, r15d; AclSize
0x18007ba1a  mov     r8d, ebx; AclRevision
0x18007ba1d  mov     rcx, r14; Acl
0x18007ba20  call    cs:__imp_RtlCreateAcl
0x18007ba27  nop     dword ptr [rax+rax+00h]
0x18007ba2c  test    eax, eax
0x18007ba2e  js      loc_18007B972
0x18007ba34  mov     edi, 10000000h
0x18007ba39  mov     r9, rbp; Sid
0x18007ba3c  mov     r8d, edi; AccessMask
0x18007ba3f  mov     edx, ebx; Revision
0x18007ba41  mov     rcx, r14; Acl
0x18007ba44  call    cs:__imp_RtlAddAccessAllowedAce
0x18007ba4b  nop     dword ptr [rax+rax+00h]
0x18007ba50  test    eax, eax
0x18007ba52  js      loc_18007B972
0x18007ba58  mov     r9, cs:?WellKnownSids@@3PEAU_LSAP_WELL_KNOWN_SID_ENTRY@@EA; _LSAP_WELL_KNOWN_SID_ENTRY * WellKnownSids
0x18007ba5f  mov     r8d, edi; AccessMask
0x18007ba62  mov     edx, ebx; Revision
0x18007ba64  mov     rcx, r14; Acl
0x18007ba67  mov     r9, [r9+2D0h]; Sid
0x18007ba6e  call    cs:__imp_RtlAddAccessAllowedAce
0x18007ba75  nop     dword ptr [rax+rax+00h]
0x18007ba7a  test    eax, eax
0x18007ba7c  js      loc_18007B972
0x18007ba82  test    rsi, rsi
0x18007ba85  jz      loc_18007B972
0x18007ba8b  mov     r9, rsi; Sid
0x18007ba8e  mov     r8d, 0A0000000h; AccessMask
0x18007ba94  mov     edx, ebx; Revision
0x18007ba96  mov     rcx, r14; Acl
0x18007ba99  call    cs:__imp_RtlAddAccessAllowedAce
0x18007baa0  nop     dword ptr [rax+rax+00h]
0x18007baa5  jmp     loc_18007B972
0x18007baaa  mov     rbp, [r8+8]
0x18007baae  jmp     loc_18007B9A2
```
