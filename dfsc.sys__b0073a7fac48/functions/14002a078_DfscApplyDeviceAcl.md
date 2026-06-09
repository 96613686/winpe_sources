# DfscApplyDeviceAcl

- ea: `0x14002a078`
- end: `0x14002a481`
- name: `DfscApplyDeviceAcl`
- size: `1033`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14002a904`

## callees

- `0x140005f70`
- `0x14002a078`

## import_xrefs

- `ntoskrnl!RtlLengthRequiredSid` at `0x14002a0c9`
- `ntoskrnl!RtlLengthRequiredSid` at `0x14002a114`
- `ntoskrnl!RtlLengthRequiredSid` at `0x14002a150`
- `ntoskrnl!RtlLengthRequiredSid` at `0x14002a182`
- `ntoskrnl!RtlLengthRequiredSid` at `0x14002a0c9`
- `ntoskrnl!RtlLengthRequiredSid` at `0x14002a114`
- `ntoskrnl!RtlLengthRequiredSid` at `0x14002a150`
- `ntoskrnl!RtlLengthRequiredSid` at `0x14002a182`
- `ntoskrnl!RtlInitializeSid` at `0x14002a1bc`
- `ntoskrnl!RtlInitializeSid` at `0x14002a1d7`
- `ntoskrnl!RtlInitializeSid` at `0x14002a1ed`
- `ntoskrnl!RtlInitializeSid` at `0x14002a203`
- `ntoskrnl!RtlInitializeSid` at `0x14002a1bc`
- `ntoskrnl!RtlInitializeSid` at `0x14002a1d7`
- `ntoskrnl!RtlInitializeSid` at `0x14002a1ed`
- `ntoskrnl!RtlInitializeSid` at `0x14002a203`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14002a214`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14002a22b`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14002a243`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14002a25b`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14002a273`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14002a28b`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14002a2a2`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14002a2b9`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14002a2d0`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14002a2e7`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14002a214`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14002a22b`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14002a243`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14002a25b`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14002a273`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14002a28b`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14002a2a2`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14002a2b9`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14002a2d0`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14002a2e7`
- `ntoskrnl!RtlCreateAcl` at `0x14002a339`
- `ntoskrnl!RtlCreateAcl` at `0x14002a339`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14002a358`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14002a372`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14002a38e`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14002a3a8`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14002a358`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14002a372`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14002a38e`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14002a3a8`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14002a3bb`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14002a3bb`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14002a3d3`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14002a3d3`
- `ntoskrnl!ObSetSecurityObjectByPointer` at `0x14002a3ea`
- `ntoskrnl!ObSetSecurityObjectByPointer` at `0x14002a3ea`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002a3fd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002a413`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002a429`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002a43f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002a455`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002a3fd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002a413`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002a429`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002a43f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002a455`
- `ntoskrnl!ExAllocatePool2` at `0x14002a0eb`
- `ntoskrnl!ExAllocatePool2` at `0x14002a12a`
- `ntoskrnl!ExAllocatePool2` at `0x14002a169`
- `ntoskrnl!ExAllocatePool2` at `0x14002a19e`
- `ntoskrnl!ExAllocatePool2` at `0x14002a316`
- `ntoskrnl!ExAllocatePool2` at `0x14002a0eb`
- `ntoskrnl!ExAllocatePool2` at `0x14002a12a`
- `ntoskrnl!ExAllocatePool2` at `0x14002a169`
- `ntoskrnl!ExAllocatePool2` at `0x14002a19e`
- `ntoskrnl!ExAllocatePool2` at `0x14002a316`

## pseudocode

```c
__int64 __fastcall DfscApplyDeviceAcl(__int64 a1)
{
  void *Pool2; // r12
  unsigned int v2; // ebx
  void *v3; // r14
  struct _ACL *v4; // rdi
  ULONG v5; // ebx
  void *v6; // r15
  void *v7; // rsi
  __int64 v8; // r13
  __int64 v9; // rbx
  struct _ACL *v10; // rax
  ULONG v12; // [rsp+20h] [rbp-58h]
  ULONG v13; // [rsp+24h] [rbp-54h]
  _OWORD SecurityDescriptor[2]; // [rsp+30h] [rbp-48h] BYREF
  __int64 v16; // [rsp+50h] [rbp-28h]
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+58h] [rbp-20h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v18; // [rsp+60h] [rbp-18h] BYREF

  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  *(_WORD *)&v18.Value[4] = 256;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_DWORD *)v18.Value = 0;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  v16 = 0;
  v13 = RtlLengthRequiredSid(6u);
  Pool2 = (void *)ExAllocatePool2(258, v13, 1229153860);
  if ( !Pool2 )
    return (unsigned int)-1073741670;
  v3 = 0;
  v4 = 0;
  v5 = RtlLengthRequiredSid(1u);
  v6 = (void *)ExAllocatePool2(258, v5, 1229153860);
  if ( v6 )
  {
    v12 = RtlLengthRequiredSid(2u);
    v7 = (void *)ExAllocatePool2(258, v12, 1229153860);
    if ( v7 )
    {
      v8 = RtlLengthRequiredSid(1u);
      v3 = (void *)ExAllocatePool2(258, v8, 1229153860);
      if ( v3 )
      {
        RtlInitializeSid(Pool2, &IdentifierAuthority, 6u);
        RtlInitializeSid(v6, &IdentifierAuthority, 1u);
        RtlInitializeSid(v7, &IdentifierAuthority, 2u);
        RtlInitializeSid(v3, &v18, 1u);
        *RtlSubAuthoritySid(Pool2, 0) = 80;
        *RtlSubAuthoritySid(Pool2, 1u) = 719998295;
        *RtlSubAuthoritySid(Pool2, 2u) = -1461267253;
        *RtlSubAuthoritySid(Pool2, 3u) = 1566817583;
        *RtlSubAuthoritySid(Pool2, 4u) = -201024527;
        *RtlSubAuthoritySid(Pool2, 5u) = 1414026312;
        *RtlSubAuthoritySid(v6, 0) = 18;
        *RtlSubAuthoritySid(v7, 0) = 32;
        *RtlSubAuthoritySid(v7, 1u) = 544;
        *RtlSubAuthoritySid(v3, 0) = 0;
        v9 = v5 + (_DWORD)v8 + v12 + v13 + 48;
        v10 = (struct _ACL *)ExAllocatePool2(258, v9, 1229153860);
        v4 = v10;
        if ( v10 )
        {
          RtlCreateAcl(v10, v9, 2u);
          RtlAddAccessAllowedAce(v4, 2u, 0x1F01FFu, Pool2);
          RtlAddAccessAllowedAce(v4, 2u, 0x1F01FFu, v6);
          RtlAddAccessAllowedAce(v4, 2u, 0x1F01FFu, v7);
          RtlAddAccessAllowedAce(v4, 2u, 0x1200A0u, v3);
          RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
          RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, v4, 0);
          v2 = ObSetSecurityObjectByPointer(a1, 4, SecurityDescriptor);
          goto LABEL_10;
        }
      }
    }
  }
  else
  {
    v7 = 0;
  }
  v2 = -1073741670;
LABEL_10:
  ExFreePoolWithTag(Pool2, 0);
  if ( v6 )
    ExFreePoolWithTag(v6, 0);
  if ( v7 )
    ExFreePoolWithTag(v7, 0);
  if ( v3 )
    ExFreePoolWithTag(v3, 0);
  if ( v4 )
    ExFreePoolWithTag(v4, 0);
  return v2;
}

```

## disassembly

```asm
0x14002a078  push    rbp
0x14002a07a  push    rbx
0x14002a07b  push    rsi
0x14002a07c  push    rdi
0x14002a07d  push    r12
0x14002a07f  push    r13
0x14002a081  push    r14
0x14002a083  push    r15
0x14002a085  mov     rbp, rsp
0x14002a088  sub     rsp, 78h
0x14002a08c  mov     rax, cs:__security_cookie
0x14002a093  xor     rax, rsp
0x14002a096  mov     [rbp+var_10], rax
0x14002a09a  xor     eax, eax
0x14002a09c  mov     [rbp+var_50], rcx
0x14002a0a0  xorps   xmm0, xmm0
0x14002a0a3  mov     word ptr [rbp+IdentifierAuthority.Value+4], 500h
0x14002a0a9  xor     r13d, r13d
0x14002a0ac  mov     word ptr [rbp+var_18.Value+4], 100h
0x14002a0b2  mov     dword ptr [rbp+IdentifierAuthority.Value], r13d
0x14002a0b6  lea     ecx, [rax+6]; SubAuthorityCount
0x14002a0b9  mov     dword ptr [rbp+var_18.Value], r13d
0x14002a0bd  movups  [rbp+SecurityDescriptor], xmm0
0x14002a0c1  mov     [rbp+var_28], rax
0x14002a0c5  movups  [rbp+var_38], xmm0
0x14002a0c9  call    cs:__imp_RtlLengthRequiredSid
0x14002a0d0  nop     dword ptr [rax+rax+00h]
0x14002a0d5  mov     esi, 49436644h
0x14002a0da  mov     r15d, 102h
0x14002a0e0  mov     edx, eax
0x14002a0e2  mov     r8d, esi
0x14002a0e5  mov     ecx, r15d
0x14002a0e8  mov     [rbp+var_54], eax
0x14002a0eb  call    cs:__imp_ExAllocatePool2
0x14002a0f2  nop     dword ptr [rax+rax+00h]
0x14002a0f7  mov     r12, rax
0x14002a0fa  test    rax, rax
0x14002a0fd  jnz     short loc_14002A109
0x14002a0ff  mov     ebx, 0C000009Ah
0x14002a104  jmp     loc_14002A461
0x14002a109  mov     ecx, 1; SubAuthorityCount
0x14002a10e  mov     r14, r13
0x14002a111  mov     rdi, r13
0x14002a114  call    cs:__imp_RtlLengthRequiredSid
0x14002a11b  nop     dword ptr [rax+rax+00h]
0x14002a120  mov     edx, eax
0x14002a122  mov     r8d, esi
0x14002a125  mov     rcx, r15
0x14002a128  mov     ebx, eax
0x14002a12a  call    cs:__imp_ExAllocatePool2
0x14002a131  nop     dword ptr [rax+rax+00h]
0x14002a136  mov     r15, rax
0x14002a139  test    rax, rax
0x14002a13c  jnz     short loc_14002A14B
0x14002a13e  mov     rsi, r13
0x14002a141  mov     ebx, 0C000009Ah
0x14002a146  jmp     loc_14002A3F8
0x14002a14b  mov     ecx, 2; SubAuthorityCount
0x14002a150  call    cs:__imp_RtlLengthRequiredSid
0x14002a157  nop     dword ptr [rax+rax+00h]
0x14002a15c  mov     edx, eax
0x14002a15e  mov     r8d, esi
0x14002a161  mov     ecx, 102h
0x14002a166  mov     [rbp+var_58], eax
0x14002a169  call    cs:__imp_ExAllocatePool2
0x14002a170  nop     dword ptr [rax+rax+00h]
0x14002a175  mov     rsi, rax
0x14002a178  test    rax, rax
0x14002a17b  jz      short loc_14002A141
0x14002a17d  mov     ecx, 1; SubAuthorityCount
0x14002a182  call    cs:__imp_RtlLengthRequiredSid
0x14002a189  nop     dword ptr [rax+rax+00h]
0x14002a18e  mov     edx, eax
0x14002a190  mov     ecx, 102h
0x14002a195  mov     r8d, 49436644h
0x14002a19b  mov     r13d, eax
0x14002a19e  call    cs:__imp_ExAllocatePool2
0x14002a1a5  nop     dword ptr [rax+rax+00h]
0x14002a1aa  mov     r14, rax
0x14002a1ad  test    rax, rax
0x14002a1b0  jz      short loc_14002A141
0x14002a1b2  mov     r8b, 6; SubAuthorityCount
0x14002a1b5  lea     rdx, [rbp+IdentifierAuthority]; IdentifierAuthority
0x14002a1b9  mov     rcx, r12; Sid
0x14002a1bc  call    cs:__imp_RtlInitializeSid
0x14002a1c3  nop     dword ptr [rax+rax+00h]
0x14002a1c8  mov     edi, 1
0x14002a1cd  lea     rdx, [rbp+IdentifierAuthority]; IdentifierAuthority
0x14002a1d1  mov     r8b, dil; SubAuthorityCount
0x14002a1d4  mov     rcx, r15; Sid
0x14002a1d7  call    cs:__imp_RtlInitializeSid
0x14002a1de  nop     dword ptr [rax+rax+00h]
0x14002a1e3  mov     r8b, 2; SubAuthorityCount
0x14002a1e6  lea     rdx, [rbp+IdentifierAuthority]; IdentifierAuthority
0x14002a1ea  mov     rcx, rsi; Sid
0x14002a1ed  call    cs:__imp_RtlInitializeSid
0x14002a1f4  nop     dword ptr [rax+rax+00h]
0x14002a1f9  mov     r8b, dil; SubAuthorityCount
0x14002a1fc  lea     rdx, [rbp+var_18]; IdentifierAuthority
0x14002a200  mov     rcx, r14; Sid
0x14002a203  call    cs:__imp_RtlInitializeSid
0x14002a20a  nop     dword ptr [rax+rax+00h]
0x14002a20f  xor     edx, edx; SubAuthority
0x14002a211  mov     rcx, r12; Sid
0x14002a214  call    cs:__imp_RtlSubAuthoritySid
0x14002a21b  nop     dword ptr [rax+rax+00h]
0x14002a220  mov     edx, edi; SubAuthority
0x14002a222  mov     rcx, r12; Sid
0x14002a225  mov     dword ptr [rax], 50h ; 'P'
0x14002a22b  call    cs:__imp_RtlSubAuthoritySid
0x14002a232  nop     dword ptr [rax+rax+00h]
0x14002a237  lea     edx, [rdi+1]; SubAuthority
0x14002a23a  mov     rcx, r12; Sid
0x14002a23d  mov     dword ptr [rax], 2AEA4D57h
0x14002a243  call    cs:__imp_RtlSubAuthoritySid
0x14002a24a  nop     dword ptr [rax+rax+00h]
0x14002a24f  lea     edx, [rdi+2]; SubAuthority
0x14002a252  mov     rcx, r12; Sid
0x14002a255  mov     dword ptr [rax], 0A8E6D4CBh
0x14002a25b  call    cs:__imp_RtlSubAuthoritySid
0x14002a262  nop     dword ptr [rax+rax+00h]
0x14002a267  lea     edx, [rdi+3]; SubAuthority
0x14002a26a  mov     rcx, r12; Sid
0x14002a26d  mov     dword ptr [rax], 5D63BD2Fh
0x14002a273  call    cs:__imp_RtlSubAuthoritySid
0x14002a27a  nop     dword ptr [rax+rax+00h]
0x14002a27f  lea     edx, [rdi+4]; SubAuthority
0x14002a282  mov     rcx, r12; Sid
0x14002a285  mov     dword ptr [rax], 0F4049BF1h
0x14002a28b  call    cs:__imp_RtlSubAuthoritySid
0x14002a292  nop     dword ptr [rax+rax+00h]
0x14002a297  xor     edx, edx; SubAuthority
0x14002a299  mov     rcx, r15; Sid
0x14002a29c  mov     dword ptr [rax], 54485448h
0x14002a2a2  call    cs:__imp_RtlSubAuthoritySid
0x14002a2a9  nop     dword ptr [rax+rax+00h]
0x14002a2ae  xor     edx, edx; SubAuthority
0x14002a2b0  mov     rcx, rsi; Sid
0x14002a2b3  mov     dword ptr [rax], 12h
0x14002a2b9  call    cs:__imp_RtlSubAuthoritySid
0x14002a2c0  nop     dword ptr [rax+rax+00h]
0x14002a2c5  mov     edx, edi; SubAuthority
0x14002a2c7  mov     rcx, rsi; Sid
0x14002a2ca  mov     dword ptr [rax], 20h ; ' '
0x14002a2d0  call    cs:__imp_RtlSubAuthoritySid
0x14002a2d7  nop     dword ptr [rax+rax+00h]
0x14002a2dc  xor     edx, edx; SubAuthority
0x14002a2de  mov     rcx, r14; Sid
0x14002a2e1  mov     dword ptr [rax], 220h
0x14002a2e7  call    cs:__imp_RtlSubAuthoritySid
0x14002a2ee  nop     dword ptr [rax+rax+00h]
0x14002a2f3  mov     ecx, 102h
0x14002a2f8  mov     r8d, 49436644h
0x14002a2fe  mov     dword ptr [rax], 0
0x14002a304  mov     eax, [rbp+var_58]
0x14002a307  add     eax, r13d
0x14002a30a  add     eax, ebx
0x14002a30c  mov     ebx, [rbp+var_54]
0x14002a30f  add     ebx, 30h ; '0'
0x14002a312  add     ebx, eax
0x14002a314  mov     edx, ebx
0x14002a316  call    cs:__imp_ExAllocatePool2
0x14002a31d  nop     dword ptr [rax+rax+00h]
0x14002a322  mov     rdi, rax
0x14002a325  test    rax, rax
0x14002a328  jz      loc_14002A141
0x14002a32e  mov     r8d, 2; AclRevision
0x14002a334  mov     edx, ebx; AclLength
0x14002a336  mov     rcx, rax; Acl
0x14002a339  call    cs:__imp_RtlCreateAcl
0x14002a340  nop     dword ptr [rax+rax+00h]
0x14002a345  mov     ebx, 1F01FFh
0x14002a34a  mov     r9, r12; Sid
0x14002a34d  mov     r8d, ebx; AccessMask
0x14002a350  mov     edx, 2; AceRevision
0x14002a355  mov     rcx, rdi; Acl
0x14002a358  call    cs:__imp_RtlAddAccessAllowedAce
0x14002a35f  nop     dword ptr [rax+rax+00h]
0x14002a364  mov     r9, r15; Sid
0x14002a367  mov     r8d, ebx; AccessMask
0x14002a36a  mov     edx, 2; AceRevision
0x14002a36f  mov     rcx, rdi; Acl
0x14002a372  call    cs:__imp_RtlAddAccessAllowedAce
0x14002a379  nop     dword ptr [rax+rax+00h]
0x14002a37e  mov     r8d, ebx; AccessMask
0x14002a381  mov     r9, rsi; Sid
0x14002a384  mov     ebx, 2
0x14002a389  mov     rcx, rdi; Acl
0x14002a38c  mov     edx, ebx; AceRevision
0x14002a38e  call    cs:__imp_RtlAddAccessAllowedAce
0x14002a395  nop     dword ptr [rax+rax+00h]
0x14002a39a  mov     r9, r14; Sid
0x14002a39d  mov     r8d, 1200A0h; AccessMask
0x14002a3a3  mov     edx, ebx; AceRevision
0x14002a3a5  mov     rcx, rdi; Acl
0x14002a3a8  call    cs:__imp_RtlAddAccessAllowedAce
0x14002a3af  nop     dword ptr [rax+rax+00h]
0x14002a3b4  lea     edx, [rbx-1]; Revision
0x14002a3b7  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x14002a3bb  call    cs:__imp_RtlCreateSecurityDescriptor
0x14002a3c2  nop     dword ptr [rax+rax+00h]
0x14002a3c7  xor     r9d, r9d; DaclDefaulted
0x14002a3ca  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x14002a3ce  mov     r8, rdi; Dacl
0x14002a3d1  mov     dl, 1; DaclPresent
0x14002a3d3  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x14002a3da  nop     dword ptr [rax+rax+00h]
0x14002a3df  mov     rcx, [rbp+var_50]
0x14002a3e3  lea     r8, [rbp+SecurityDescriptor]
0x14002a3e7  lea     edx, [rbx+2]
0x14002a3ea  call    cs:__imp_ObSetSecurityObjectByPointer
0x14002a3f1  nop     dword ptr [rax+rax+00h]
0x14002a3f6  mov     ebx, eax
0x14002a3f8  xor     edx, edx; Tag
0x14002a3fa  mov     rcx, r12; P
0x14002a3fd  call    cs:__imp_ExFreePoolWithTag
0x14002a404  nop     dword ptr [rax+rax+00h]
0x14002a409  test    r15, r15
0x14002a40c  jz      short loc_14002A41F
0x14002a40e  xor     edx, edx; Tag
0x14002a410  mov     rcx, r15; P
0x14002a413  call    cs:__imp_ExFreePoolWithTag
0x14002a41a  nop     dword ptr [rax+rax+00h]
0x14002a41f  test    rsi, rsi
0x14002a422  jz      short loc_14002A435
0x14002a424  xor     edx, edx; Tag
0x14002a426  mov     rcx, rsi; P
0x14002a429  call    cs:__imp_ExFreePoolWithTag
0x14002a430  nop     dword ptr [rax+rax+00h]
0x14002a435  test    r14, r14
0x14002a438  jz      short loc_14002A44B
0x14002a43a  xor     edx, edx; Tag
0x14002a43c  mov     rcx, r14; P
0x14002a43f  call    cs:__imp_ExFreePoolWithTag
0x14002a446  nop     dword ptr [rax+rax+00h]
0x14002a44b  test    rdi, rdi
0x14002a44e  jz      short loc_14002A461
0x14002a450  xor     edx, edx; Tag
0x14002a452  mov     rcx, rdi; P
0x14002a455  call    cs:__imp_ExFreePoolWithTag
0x14002a45c  nop     dword ptr [rax+rax+00h]
0x14002a461  mov     eax, ebx
0x14002a463  mov     rcx, [rbp+var_10]
0x14002a467  xor     rcx, rsp; StackCookie
0x14002a46a  call    __security_check_cookie
0x14002a46f  add     rsp, 78h
0x14002a473  pop     r15
0x14002a475  pop     r14
0x14002a477  pop     r13
0x14002a479  pop     r12
0x14002a47b  pop     rdi
0x14002a47c  pop     rsi
0x14002a47d  pop     rbx
0x14002a47e  pop     rbp
0x14002a47f  retn
```
