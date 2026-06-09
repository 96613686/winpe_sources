# NfsInitialiseServiceSecDesc

- ea: `0x140039b90`
- end: `0x140039db0`
- name: `NfsInitialiseServiceSecDesc`
- size: `544`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14002d428`

## callees

- `0x140039b90`
- `0x14003aba0`

## import_xrefs

- `ntoskrnl!RtlLengthRequiredSid` at `0x140039bc9`
- `ntoskrnl!RtlLengthRequiredSid` at `0x140039bc9`
- `ntoskrnl!RtlInitializeSid` at `0x140039c31`
- `ntoskrnl!RtlInitializeSid` at `0x140039c31`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140039c4c`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140039c66`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140039c82`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140039c9a`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140039cb2`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140039cca`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140039c4c`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140039c66`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140039c82`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140039c9a`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140039cb2`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140039cca`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140039d22`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140039d22`
- `ntoskrnl!RtlCreateAcl` at `0x140039ce5`
- `ntoskrnl!RtlCreateAcl` at `0x140039ce5`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140039d08`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140039d08`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140039d3f`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140039d3f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140039d65`
- `ntoskrnl!ExFreePoolWithTag` at `0x140039d80`
- `ntoskrnl!ExFreePoolWithTag` at `0x140039d65`
- `ntoskrnl!ExFreePoolWithTag` at `0x140039d80`
- `ntoskrnl!ExAllocatePool2` at `0x140039be7`
- `ntoskrnl!ExAllocatePool2` at `0x140039c05`
- `ntoskrnl!ExAllocatePool2` at `0x140039be7`
- `ntoskrnl!ExAllocatePool2` at `0x140039c05`

## pseudocode

```c
__int64 __fastcall NfsInitialiseServiceSecDesc(struct _ACL **a1, void *a2)
{
  ULONG v4; // r15d
  __int64 Pool2; // rax
  ULONG v6; // r15d
  void *v7; // rsi
  __int64 v8; // rax
  struct _ACL *v9; // rdi
  NTSTATUS Acl; // ebx
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+20h] [rbp-38h] BYREF

  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  v4 = RtlLengthRequiredSid(6u);
  Pool2 = ExAllocatePool2(258, v4, 1400071758);
  v6 = v4 + 16;
  v7 = (void *)Pool2;
  v8 = ExAllocatePool2(258, v6, 1400071758);
  v9 = (struct _ACL *)v8;
  if ( !v7 || !v8 )
  {
    Acl = -1073741670;
    goto LABEL_10;
  }
  Acl = RtlInitializeSid(v7, &IdentifierAuthority, 6u);
  if ( Acl >= 0 )
  {
    *RtlSubAuthoritySid(v7, 0) = 80;
    *RtlSubAuthoritySid(v7, 1u) = -2106816541;
    *RtlSubAuthoritySid(v7, 2u) = 1016705677;
    *RtlSubAuthoritySid(v7, 3u) = 731116528;
    *RtlSubAuthoritySid(v7, 4u) = 1274462162;
    *RtlSubAuthoritySid(v7, 5u) = 1514473938;
    Acl = RtlCreateAcl(v9, v6, 2u);
    if ( Acl >= 0 )
    {
      Acl = RtlAddAccessAllowedAce(v9, 2u, 0x1F01FFu, v7);
      if ( Acl >= 0 )
      {
        Acl = RtlCreateSecurityDescriptor(a2, 1u);
        if ( Acl >= 0 )
        {
          Acl = RtlSetDaclSecurityDescriptor(a2, 1u, v9, 0);
          if ( Acl >= 0 )
          {
LABEL_13:
            ExFreePoolWithTag(v7, 0x5373664Eu);
            goto LABEL_14;
          }
LABEL_10:
          if ( !v9 )
            goto LABEL_12;
        }
      }
    }
  }
  ExFreePoolWithTag(v9, 0x5373664Eu);
  v9 = 0;
LABEL_12:
  if ( v7 )
    goto LABEL_13;
LABEL_14:
  *a1 = v9;
  return (unsigned int)Acl;
}

```

## disassembly

```asm
0x140039b90  mov     [rsp+arg_10], rbx
0x140039b95  push    rbp
0x140039b96  push    rsi
0x140039b97  push    rdi
0x140039b98  push    r14
0x140039b9a  push    r15
0x140039b9c  sub     rsp, 30h
0x140039ba0  mov     rax, cs:__security_cookie
0x140039ba7  xor     rax, rsp
0x140039baa  mov     [rsp+58h+var_30], rax
0x140039baf  mov     r14, rcx
0x140039bb2  mov     dword ptr [rsp+58h+IdentifierAuthority.Value], 0
0x140039bba  mov     ecx, 6; SubAuthorityCount
0x140039bbf  mov     word ptr [rsp+58h+IdentifierAuthority.Value+4], 500h
0x140039bc6  mov     rbp, rdx
0x140039bc9  call    cs:__imp_RtlLengthRequiredSid
0x140039bd0  nop     dword ptr [rax+rax+00h]
0x140039bd5  mov     edi, 102h
0x140039bda  mov     edx, eax
0x140039bdc  mov     r8d, 5373664Eh
0x140039be2  mov     r15d, eax
0x140039be5  mov     ecx, edi
0x140039be7  call    cs:__imp_ExAllocatePool2
0x140039bee  nop     dword ptr [rax+rax+00h]
0x140039bf3  add     r15d, 10h
0x140039bf7  mov     r8d, 5373664Eh
0x140039bfd  mov     edx, r15d
0x140039c00  mov     ecx, edi
0x140039c02  mov     rsi, rax
0x140039c05  call    cs:__imp_ExAllocatePool2
0x140039c0c  nop     dword ptr [rax+rax+00h]
0x140039c11  mov     rdi, rax
0x140039c14  test    rsi, rsi
0x140039c17  jz      loc_140039D53
0x140039c1d  test    rax, rax
0x140039c20  jz      loc_140039D53
0x140039c26  mov     r8b, 6; SubAuthorityCount
0x140039c29  lea     rdx, [rsp+58h+IdentifierAuthority]; IdentifierAuthority
0x140039c2e  mov     rcx, rsi; Sid
0x140039c31  call    cs:__imp_RtlInitializeSid
0x140039c38  nop     dword ptr [rax+rax+00h]
0x140039c3d  mov     ebx, eax
0x140039c3f  test    eax, eax
0x140039c41  js      loc_140039D5D
0x140039c47  xor     edx, edx; SubAuthority
0x140039c49  mov     rcx, rsi; Sid
0x140039c4c  call    cs:__imp_RtlSubAuthoritySid
0x140039c53  nop     dword ptr [rax+rax+00h]
0x140039c58  mov     edx, 1; SubAuthority
0x140039c5d  mov     rcx, rsi; Sid
0x140039c60  mov     dword ptr [rax], 50h ; 'P'
0x140039c66  call    cs:__imp_RtlSubAuthoritySid
0x140039c6d  nop     dword ptr [rax+rax+00h]
0x140039c72  mov     ebx, 2
0x140039c77  mov     rcx, rsi; Sid
0x140039c7a  mov     edx, ebx; SubAuthority
0x140039c7c  mov     dword ptr [rax], 826C87E3h
0x140039c82  call    cs:__imp_RtlSubAuthoritySid
0x140039c89  nop     dword ptr [rax+rax+00h]
0x140039c8e  lea     edx, [rbx+1]; SubAuthority
0x140039c91  mov     rcx, rsi; Sid
0x140039c94  mov     dword ptr [rax], 3C99B28Dh
0x140039c9a  call    cs:__imp_RtlSubAuthoritySid
0x140039ca1  nop     dword ptr [rax+rax+00h]
0x140039ca6  lea     edx, [rbx+2]; SubAuthority
0x140039ca9  mov     rcx, rsi; Sid
0x140039cac  mov     dword ptr [rax], 2B93F3F0h
0x140039cb2  call    cs:__imp_RtlSubAuthoritySid
0x140039cb9  nop     dword ptr [rax+rax+00h]
0x140039cbe  lea     edx, [rbx+3]; SubAuthority
0x140039cc1  mov     rcx, rsi; Sid
0x140039cc4  mov     dword ptr [rax], 4BF6BFD2h
0x140039cca  call    cs:__imp_RtlSubAuthoritySid
0x140039cd1  nop     dword ptr [rax+rax+00h]
0x140039cd6  mov     r8d, ebx; AclRevision
0x140039cd9  mov     edx, r15d; AclLength
0x140039cdc  mov     rcx, rdi; Acl
0x140039cdf  mov     dword ptr [rax], 5A4509D2h
0x140039ce5  call    cs:__imp_RtlCreateAcl
0x140039cec  nop     dword ptr [rax+rax+00h]
0x140039cf1  mov     ebx, eax
0x140039cf3  test    eax, eax
0x140039cf5  js      short loc_140039D5D
0x140039cf7  mov     r9, rsi; Sid
0x140039cfa  mov     edx, 2; AceRevision
0x140039cff  mov     r8d, 1F01FFh; AccessMask
0x140039d05  mov     rcx, rdi; Acl
0x140039d08  call    cs:__imp_RtlAddAccessAllowedAce
0x140039d0f  nop     dword ptr [rax+rax+00h]
0x140039d14  mov     ebx, eax
0x140039d16  test    eax, eax
0x140039d18  js      short loc_140039D5D
0x140039d1a  mov     edx, 1; Revision
0x140039d1f  mov     rcx, rbp; SecurityDescriptor
0x140039d22  call    cs:__imp_RtlCreateSecurityDescriptor
0x140039d29  nop     dword ptr [rax+rax+00h]
0x140039d2e  mov     ebx, eax
0x140039d30  test    eax, eax
0x140039d32  js      short loc_140039D5D
0x140039d34  xor     r9d, r9d; DaclDefaulted
0x140039d37  mov     r8, rdi; Dacl
0x140039d3a  mov     dl, 1; DaclPresent
0x140039d3c  mov     rcx, rbp; SecurityDescriptor
0x140039d3f  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x140039d46  nop     dword ptr [rax+rax+00h]
0x140039d4b  mov     ebx, eax
0x140039d4d  test    eax, eax
0x140039d4f  jns     short loc_140039D78
0x140039d51  jmp     short loc_140039D58
0x140039d53  mov     ebx, 0C000009Ah
0x140039d58  test    rdi, rdi
0x140039d5b  jz      short loc_140039D73
0x140039d5d  mov     edx, 5373664Eh; Tag
0x140039d62  mov     rcx, rdi; P
0x140039d65  call    cs:__imp_ExFreePoolWithTag
0x140039d6c  nop     dword ptr [rax+rax+00h]
0x140039d71  xor     edi, edi
0x140039d73  test    rsi, rsi
0x140039d76  jz      short loc_140039D8C
0x140039d78  mov     edx, 5373664Eh; Tag
0x140039d7d  mov     rcx, rsi; P
0x140039d80  call    cs:__imp_ExFreePoolWithTag
0x140039d87  nop     dword ptr [rax+rax+00h]
0x140039d8c  mov     [r14], rdi
0x140039d8f  mov     eax, ebx
0x140039d91  mov     rcx, [rsp+58h+var_30]
0x140039d96  xor     rcx, rsp; StackCookie
0x140039d99  call    __security_check_cookie
0x140039d9e  mov     rbx, [rsp+58h+arg_10]
0x140039da3  add     rsp, 30h
0x140039da7  pop     r15
0x140039da9  pop     r14
0x140039dab  pop     rdi
0x140039dac  pop     rsi
0x140039dad  pop     rbp
0x140039dae  retn
```
