# TxfSecureMetadata

- ea: `0x14003a498`
- end: `0x14003a8cc`
- name: `TxfSecureMetadata`
- size: `1076`
- prototype: `void __fastcall(int, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1401f5088`

## callees

- `0x140025a40`
- `0x14003a498`
- `0x140059250`
- `0x1401419ec`
- `0x1401ef280`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14003a791`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14003a791`
- `ntoskrnl!SeCaptureSubjectContext` at `0x14003a54a`
- `ntoskrnl!SeCaptureSubjectContext` at `0x14003a54a`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14003a77c`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14003a77c`
- `ntoskrnl!SeDeassignSecurity` at `0x14003a80e`
- `ntoskrnl!SeDeassignSecurity` at `0x14005bda0`
- `ntoskrnl!SeDeassignSecurity` at `0x14003a80e`
- `ntoskrnl!SeDeassignSecurity` at `0x14005bda0`
- `ntoskrnl!RtlLengthRequiredSid` at `0x14003a559`
- `ntoskrnl!RtlLengthRequiredSid` at `0x14003a5d4`
- `ntoskrnl!RtlLengthRequiredSid` at `0x14003a559`
- `ntoskrnl!RtlLengthRequiredSid` at `0x14003a5d4`
- `ntoskrnl!RtlInitializeSid` at `0x14003a595`
- `ntoskrnl!RtlInitializeSid` at `0x14003a613`
- `ntoskrnl!RtlInitializeSid` at `0x14003a595`
- `ntoskrnl!RtlInitializeSid` at `0x14003a613`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14003a5a6`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14003a5bf`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14003a624`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14003a5a6`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14003a5bf`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14003a624`
- `ntoskrnl!RtlCreateAcl` at `0x14003a676`
- `ntoskrnl!RtlCreateAcl` at `0x14003a676`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14003a69b`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14003a6c3`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14003a69b`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14003a6c3`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14003a6e2`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14003a6e2`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14003a706`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14003a706`
- `ntoskrnl!SeAssignSecurity` at `0x14003a74c`
- `ntoskrnl!SeAssignSecurity` at `0x14003a74c`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x14003a76b`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x14003a76b`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14003a71a`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x14003a71a`
- `ntoskrnl!ExReleasePushLockEx` at `0x14003a892`
- `ntoskrnl!ExReleasePushLockEx` at `0x14005be71`
- `ntoskrnl!ExReleasePushLockEx` at `0x14003a892`
- `ntoskrnl!ExReleasePushLockEx` at `0x14005be71`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003a824`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003a83a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003a84b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003a85e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005bdb8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005bdd0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005bde8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005be00`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003a824`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003a83a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003a84b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003a85e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005bdb8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005bdd0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005bde8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005be00`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003a533`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003a573`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003a5f1`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003a659`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003a533`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003a573`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003a5f1`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003a659`

## pseudocode

```c
void __fastcall TxfSecureMetadata(int a1, __int64 a2)
{
  volatile signed __int32 *v4; // rsi
  char v5; // r15
  struct _SECURITY_SUBJECT_CONTEXT *SubjectContext; // r12
  ULONG v7; // eax
  unsigned __int8 *PoolWithTag; // rbx
  ULONG v9; // eax
  unsigned __int8 *v10; // r14
  struct _ACL *v11; // r14
  PSID v12; // rbx
  struct _GENERIC_MAPPING *GenericMapping; // rax
  ULONG v14; // ebx
  __int64 v15; // rax
  PSECURITY_DESCRIPTOR NewDescriptor; // [rsp+48h] [rbp-A0h] BYREF
  PSID P; // [rsp+50h] [rbp-98h]
  int v18; // [rsp+58h] [rbp-90h]
  PSID Sid; // [rsp+60h] [rbp-88h]
  struct _SECURITY_SUBJECT_CONTEXT *v20; // [rsp+68h] [rbp-80h]
  struct _ACL *v21; // [rsp+70h] [rbp-78h]
  volatile signed __int32 *v22; // [rsp+78h] [rbp-70h]
  __int64 v23; // [rsp+80h] [rbp-68h]
  _BYTE SecurityDescriptor[32]; // [rsp+88h] [rbp-60h] BYREF
  __int64 v25; // [rsp+A8h] [rbp-40h]
  volatile signed __int32 *IdentifierAuthority; // [rsp+B0h] [rbp-38h] BYREF

  v23 = a2;
  v21 = 0;
  NewDescriptor = 0;
  v4 = 0;
  v22 = 0;
  v18 = 0;
  v5 = 0;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  v25 = 0;
  LODWORD(IdentifierAuthority) = 0;
  WORD2(IdentifierAuthority) = 1280;
  SubjectContext = (struct _SECURITY_SUBJECT_CONTEXT *)ExAllocatePoolWithTag(
                                                         (POOL_TYPE)(PoolType | 0x10),
                                                         0x20u,
                                                         0x3066744Eu);
  v20 = SubjectContext;
  SeCaptureSubjectContext(SubjectContext);
  v7 = RtlLengthRequiredSid(2u);
  PoolWithTag = (unsigned __int8 *)ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), v7, 0x3066744Eu);
  P = PoolWithTag;
  RtlInitializeSid(PoolWithTag, (PSID_IDENTIFIER_AUTHORITY)&IdentifierAuthority, 2u);
  *RtlSubAuthoritySid(PoolWithTag, 0) = 32;
  *RtlSubAuthoritySid(PoolWithTag, 1u) = 544;
  v9 = RtlLengthRequiredSid(1u);
  v10 = (unsigned __int8 *)ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), v9, 0x3066744Eu);
  Sid = v10;
  RtlInitializeSid(v10, (PSID_IDENTIFIER_AUTHORITY)&IdentifierAuthority, 1u);
  *RtlSubAuthoritySid(v10, 0) = 18;
  LODWORD(PoolWithTag) = 4 * (PoolWithTag[1] + v10[1]) + 56;
  v11 = (struct _ACL *)ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), (unsigned int)PoolWithTag, 0x3066744Eu);
  v21 = v11;
  if ( RtlCreateAcl(v11, (ULONG)PoolWithTag, 2u) < 0 )
  {
LABEL_9:
    v12 = P;
    goto LABEL_10;
  }
  v12 = P;
  if ( RtlAddAccessAllowedAce(v11, 2u, 0x10000000u, Sid) >= 0
    && RtlAddAccessAllowedAce(v11, 2u, 0x80000000, P) >= 0
    && RtlCreateSecurityDescriptor(SecurityDescriptor, 1u) >= 0
    && RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, v11, 0) >= 0 )
  {
    GenericMapping = IoGetFileObjectGenericMapping();
    if ( SeAssignSecurity(0, SecurityDescriptor, &NewDescriptor, 0, SubjectContext, GenericMapping, PoolType) < 0 )
    {
      NewDescriptor = 0;
      goto LABEL_10;
    }
    v14 = RtlLengthSecurityDescriptor(NewDescriptor);
    SeReleaseSubjectContext(SubjectContext);
    ExAcquirePushLockExclusiveEx(a2 + 216, 0);
    v5 = 1;
    v4 = *(volatile signed __int32 **)(a2 + 208);
    v22 = v4;
    v18 = *(_DWORD *)(a2 + 280);
    *(_QWORD *)(a2 + 208) = 0;
    v15 = NtfsCacheSharedSecurityByDescriptor(a1, NewDescriptor, v14, 1);
    *(_QWORD *)(a2 + 208) = v15;
    *(_DWORD *)(a2 + 280) = *(_DWORD *)(v15 + 12);
    NtfsUpdateStandardInformation(a1, a2);
    goto LABEL_9;
  }
LABEL_10:
  if ( NewDescriptor )
    SeDeassignSecurity(&NewDescriptor);
  if ( SubjectContext )
    ExFreePoolWithTag(SubjectContext, 0);
  if ( v11 )
    ExFreePoolWithTag(v11, 0);
  ExFreePoolWithTag(v12, 0);
  ExFreePoolWithTag(Sid, 0);
  if ( v4 )
  {
    IdentifierAuthority = v4;
    NtfsDereferenceSharedSecurity(&IdentifierAuthority);
  }
  if ( v5 )
    ExReleasePushLockEx(a2 + 216, 0);
}

```

## disassembly

```asm
0x14003a498  mov     r11, rsp
0x14003a49b  mov     [r11+18h], rbx
0x14003a49f  mov     [r11+20h], rsi
0x14003a4a3  push    rdi
0x14003a4a4  push    r12
0x14003a4a6  push    r13
0x14003a4a8  push    r14
0x14003a4aa  push    r15
0x14003a4ac  sub     rsp, 0C0h
0x14003a4b3  mov     rax, cs:__security_cookie
0x14003a4ba  xor     rax, rsp
0x14003a4bd  mov     [rsp+0E8h+var_30], rax
0x14003a4c5  mov     rdi, rdx
0x14003a4c8  mov     r13, rcx
0x14003a4cb  mov     [rsp+0E8h+var_68], rdx
0x14003a4d3  xor     ecx, ecx
0x14003a4d5  mov     [r11-80h], rcx
0x14003a4d9  mov     [r11-78h], rcx
0x14003a4dd  mov     [rsp+0E8h+P], rcx
0x14003a4e2  mov     [rsp+0E8h+Sid], rcx
0x14003a4e7  mov     [rsp+0E8h+NewDescriptor], rcx
0x14003a4ec  mov     esi, ecx
0x14003a4ee  mov     [r11-70h], rcx
0x14003a4f2  mov     [rsp+0E8h+var_90], ecx
0x14003a4f6  mov     r15b, cl
0x14003a4f9  mov     [rsp+0E8h+var_A8], cl
0x14003a4fd  xorps   xmm0, xmm0
0x14003a500  xor     eax, eax
0x14003a502  movups  xmmword ptr [r11-60h], xmm0
0x14003a507  movups  xmmword ptr [r11-50h], xmm0
0x14003a50c  mov     [r11-40h], rax
0x14003a510  mov     [r11-38h], ecx
0x14003a514  mov     word ptr [r11-34h], 500h
0x14003a51b  mov     ecx, cs:PoolType
0x14003a521  or      ecx, 10h; PoolType
0x14003a524  mov     ebx, 3066744Eh
0x14003a529  mov     r8d, ebx; Tag
0x14003a52c  lea     r14d, [rsi+20h]
0x14003a530  mov     edx, r14d; NumberOfBytes
0x14003a533  call    cs:__imp_ExAllocatePoolWithTag
0x14003a53a  nop     dword ptr [rax+rax+00h]
0x14003a53f  mov     r12, rax
0x14003a542  mov     [rsp+0E8h+var_80], rax
0x14003a547  mov     rcx, rax; SubjectContext
0x14003a54a  call    cs:__imp_SeCaptureSubjectContext
0x14003a551  nop     dword ptr [rax+rax+00h]
0x14003a556  lea     ecx, [rsi+2]; SubAuthorityCount
0x14003a559  call    cs:__imp_RtlLengthRequiredSid
0x14003a560  nop     dword ptr [rax+rax+00h]
0x14003a565  mov     edx, eax; NumberOfBytes
0x14003a567  mov     ecx, cs:PoolType
0x14003a56d  or      ecx, 10h; PoolType
0x14003a570  mov     r8d, ebx; Tag
0x14003a573  call    cs:__imp_ExAllocatePoolWithTag
0x14003a57a  nop     dword ptr [rax+rax+00h]
0x14003a57f  mov     rbx, rax
0x14003a582  mov     [rsp+0E8h+P], rax
0x14003a587  mov     r8b, 2; SubAuthorityCount
0x14003a58a  lea     rdx, [rsp+0E8h+IdentifierAuthority]; IdentifierAuthority
0x14003a592  mov     rcx, rax; Sid
0x14003a595  call    cs:__imp_RtlInitializeSid
0x14003a59c  nop     dword ptr [rax+rax+00h]
0x14003a5a1  xor     edx, edx; SubAuthority
0x14003a5a3  mov     rcx, rbx; Sid
0x14003a5a6  call    cs:__imp_RtlSubAuthoritySid
0x14003a5ad  nop     dword ptr [rax+rax+00h]
0x14003a5b2  mov     [rax], r14d
0x14003a5b5  lea     r14d, [rsi+1]
0x14003a5b9  mov     edx, r14d; SubAuthority
0x14003a5bc  mov     rcx, rbx; Sid
0x14003a5bf  call    cs:__imp_RtlSubAuthoritySid
0x14003a5c6  nop     dword ptr [rax+rax+00h]
0x14003a5cb  mov     dword ptr [rax], 220h
0x14003a5d1  mov     ecx, r14d; SubAuthorityCount
0x14003a5d4  call    cs:__imp_RtlLengthRequiredSid
0x14003a5db  nop     dword ptr [rax+rax+00h]
0x14003a5e0  mov     edx, eax; NumberOfBytes
0x14003a5e2  mov     ecx, cs:PoolType
0x14003a5e8  or      ecx, 10h; PoolType
0x14003a5eb  mov     r8d, 3066744Eh; Tag
0x14003a5f1  call    cs:__imp_ExAllocatePoolWithTag
0x14003a5f8  nop     dword ptr [rax+rax+00h]
0x14003a5fd  mov     r14, rax
0x14003a600  mov     [rsp+0E8h+Sid], rax
0x14003a605  mov     r8b, 1; SubAuthorityCount
0x14003a608  lea     rdx, [rsp+0E8h+IdentifierAuthority]; IdentifierAuthority
0x14003a610  mov     rcx, rax; Sid
0x14003a613  call    cs:__imp_RtlInitializeSid
0x14003a61a  nop     dword ptr [rax+rax+00h]
0x14003a61f  xor     edx, edx; SubAuthority
0x14003a621  mov     rcx, r14; Sid
0x14003a624  call    cs:__imp_RtlSubAuthoritySid
0x14003a62b  nop     dword ptr [rax+rax+00h]
0x14003a630  mov     dword ptr [rax], 12h
0x14003a636  movzx   edx, byte ptr [r14+1]
0x14003a63b  movzx   ecx, byte ptr [rbx+1]
0x14003a63f  add     edx, ecx
0x14003a641  lea     ebx, ds:38h[rdx*4]
0x14003a648  mov     edx, ebx; NumberOfBytes
0x14003a64a  mov     ecx, cs:PoolType
0x14003a650  or      ecx, 10h; PoolType
0x14003a653  mov     r8d, 3066744Eh; Tag
0x14003a659  call    cs:__imp_ExAllocatePoolWithTag
0x14003a660  nop     dword ptr [rax+rax+00h]
0x14003a665  mov     r14, rax
0x14003a668  mov     [rsp+0E8h+var_78], rax
0x14003a66d  lea     r8d, [rsi+2]; AclRevision
0x14003a671  mov     edx, ebx; AclLength
0x14003a673  mov     rcx, rax; Acl
0x14003a676  call    cs:__imp_RtlCreateAcl
0x14003a67d  nop     dword ptr [rax+rax+00h]
0x14003a682  test    eax, eax
0x14003a684  js      loc_14003A7FC
0x14003a68a  mov     r9, [rsp+0E8h+Sid]; Sid
0x14003a68f  lea     edx, [rsi+2]; AceRevision
0x14003a692  mov     r8d, 10000000h; AccessMask
0x14003a698  mov     rcx, r14; Acl
0x14003a69b  call    cs:__imp_RtlAddAccessAllowedAce
0x14003a6a2  nop     dword ptr [rax+rax+00h]
0x14003a6a7  mov     rbx, [rsp+0E8h+P]
0x14003a6ac  test    eax, eax
0x14003a6ae  js      loc_14003A801
0x14003a6b4  mov     r9, rbx; Sid
0x14003a6b7  lea     edx, [rsi+2]; AceRevision
0x14003a6ba  mov     r8d, 80000000h; AccessMask
0x14003a6c0  mov     rcx, r14; Acl
0x14003a6c3  call    cs:__imp_RtlAddAccessAllowedAce
0x14003a6ca  nop     dword ptr [rax+rax+00h]
0x14003a6cf  test    eax, eax
0x14003a6d1  js      loc_14003A801
0x14003a6d7  lea     edx, [rsi+1]; Revision
0x14003a6da  lea     rcx, [rsp+0E8h+SecurityDescriptor]; SecurityDescriptor
0x14003a6e2  call    cs:__imp_RtlCreateSecurityDescriptor
0x14003a6e9  nop     dword ptr [rax+rax+00h]
0x14003a6ee  test    eax, eax
0x14003a6f0  js      loc_14003A801
0x14003a6f6  xor     r9d, r9d; DaclDefaulted
0x14003a6f9  mov     r8, r14; Dacl
0x14003a6fc  mov     dl, 1; DaclPresent
0x14003a6fe  lea     rcx, [rsp+0E8h+SecurityDescriptor]; SecurityDescriptor
0x14003a706  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x14003a70d  nop     dword ptr [rax+rax+00h]
0x14003a712  test    eax, eax
0x14003a714  js      loc_14003A801
0x14003a71a  call    cs:__imp_IoGetFileObjectGenericMapping
0x14003a721  nop     dword ptr [rax+rax+00h]
0x14003a726  mov     ecx, cs:PoolType
0x14003a72c  mov     [rsp+0E8h+PoolType], ecx; PoolType
0x14003a730  mov     [rsp+0E8h+GenericMapping], rax; GenericMapping
0x14003a735  mov     [rsp+0E8h+SubjectContext], r12; SubjectContext
0x14003a73a  xor     r9d, r9d; IsDirectoryObject
0x14003a73d  lea     r8, [rsp+0E8h+NewDescriptor]; NewDescriptor
0x14003a742  lea     rdx, [rsp+0E8h+SecurityDescriptor]; ExplicitDescriptor
0x14003a74a  xor     ecx, ecx; ParentDescriptor
0x14003a74c  call    cs:__imp_SeAssignSecurity
0x14003a753  nop     dword ptr [rax+rax+00h]
0x14003a758  test    eax, eax
0x14003a75a  jns     short loc_14003A766
0x14003a75c  mov     [rsp+0E8h+NewDescriptor], rsi
0x14003a761  jmp     loc_14003A801
0x14003a766  mov     rcx, [rsp+0E8h+NewDescriptor]; SecurityDescriptor
0x14003a76b  call    cs:__imp_RtlLengthSecurityDescriptor
0x14003a772  nop     dword ptr [rax+rax+00h]
0x14003a777  mov     ebx, eax
0x14003a779  mov     rcx, r12; SubjectContext
0x14003a77c  call    cs:__imp_SeReleaseSubjectContext
0x14003a783  nop     dword ptr [rax+rax+00h]
0x14003a788  lea     rcx, [rdi+0D8h]
0x14003a78f  xor     edx, edx
0x14003a791  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14003a798  nop     dword ptr [rax+rax+00h]
0x14003a79d  mov     r15b, 1
0x14003a7a0  mov     [rsp+0E8h+var_A8], r15b
0x14003a7a5  mov     rsi, [rdi+0D0h]
0x14003a7ac  mov     [rsp+0E8h+var_70], rsi
0x14003a7b1  mov     ecx, [rdi+118h]
0x14003a7b7  mov     [rsp+0E8h+var_90], ecx
0x14003a7bb  mov     qword ptr [rdi+0D0h], 0
0x14003a7c6  mov     byte ptr [rsp+0E8h+SubjectContext], r15b; char
0x14003a7cb  mov     r9b, r15b
0x14003a7ce  mov     r8d, ebx; Length
0x14003a7d1  mov     rdx, [rsp+0E8h+NewDescriptor]; SecurityDescriptor
0x14003a7d6  mov     rcx, r13; int
0x14003a7d9  call    NtfsCacheSharedSecurityByDescriptor
0x14003a7de  mov     [rdi+0D0h], rax
0x14003a7e5  mov     eax, [rax+0Ch]
0x14003a7e8  mov     [rdi+118h], eax
0x14003a7ee  xor     r8d, r8d
0x14003a7f1  mov     rdx, rdi
0x14003a7f4  mov     rcx, r13
0x14003a7f7  call    NtfsUpdateStandardInformation
0x14003a7fc  mov     rbx, [rsp+0E8h+P]
0x14003a801  cmp     [rsp+0E8h+NewDescriptor], 0
0x14003a807  jz      short loc_14003A81A
0x14003a809  lea     rcx, [rsp+0E8h+NewDescriptor]; SecurityDescriptor
0x14003a80e  call    cs:__imp_SeDeassignSecurity
0x14003a815  nop     dword ptr [rax+rax+00h]
0x14003a81a  test    r12, r12
0x14003a81d  jz      short loc_14003A830
0x14003a81f  xor     edx, edx; Tag
0x14003a821  mov     rcx, r12; P
0x14003a824  call    cs:__imp_ExFreePoolWithTag
0x14003a82b  nop     dword ptr [rax+rax+00h]
0x14003a830  test    r14, r14
0x14003a833  jz      short loc_14003A846
0x14003a835  xor     edx, edx; Tag
0x14003a837  mov     rcx, r14; P
0x14003a83a  call    cs:__imp_ExFreePoolWithTag
0x14003a841  nop     dword ptr [rax+rax+00h]
0x14003a846  xor     edx, edx; Tag
0x14003a848  mov     rcx, rbx; P
0x14003a84b  call    cs:__imp_ExFreePoolWithTag
0x14003a852  nop     dword ptr [rax+rax+00h]
0x14003a857  xor     edx, edx; Tag
0x14003a859  mov     rcx, [rsp+0E8h+Sid]; P
0x14003a85e  call    cs:__imp_ExFreePoolWithTag
0x14003a865  nop     dword ptr [rax+rax+00h]
0x14003a86a  test    rsi, rsi
0x14003a86d  jz      short loc_14003A884
0x14003a86f  mov     [rsp+0E8h+IdentifierAuthority], rsi
0x14003a877  lea     rcx, [rsp+0E8h+IdentifierAuthority]
0x14003a87f  call    NtfsDereferenceSharedSecurity
0x14003a884  test    r15b, r15b
0x14003a887  jz      short loc_14003A89E
0x14003a889  lea     rcx, [rdi+0D8h]
0x14003a890  xor     edx, edx
0x14003a892  call    cs:__imp_ExReleasePushLockEx
0x14003a899  nop     dword ptr [rax+rax+00h]
0x14003a89e  mov     rcx, [rsp+0E8h+var_30]
0x14003a8a6  xor     rcx, rsp; StackCookie
0x14003a8a9  call    __security_check_cookie
0x14003a8ae  lea     r11, [rsp+0E8h+var_28]
0x14003a8b6  mov     rbx, [r11+40h]
0x14003a8ba  mov     rsi, [r11+48h]
0x14003a8be  mov     rsp, r11
0x14003a8c1  pop     r15
0x14003a8c3  pop     r14
0x14003a8c5  pop     r13
0x14003a8c7  pop     r12
0x14003a8c9  pop     rdi
0x14003a8ca  retn
0x14005bd7f  push    rbx
0x14005bd81  push    rbp
0x14005bd82  sub     rsp, 48h
0x14005bd86  mov     rbp, rdx
0x14005bd89  mov     bl, cl
0x14005bd8b  test    cl, cl
0x14005bd8d  jz      short loc_14005BD95
0x14005bd8f  mov     al, cs:NtfsStatusDebugFlags
0x14005bd95  cmp     qword ptr [rbp+48h], 0
0x14005bd9a  jz      short loc_14005BDAD
0x14005bd9c  lea     rcx, [rbp+48h]; SecurityDescriptor
0x14005bda0  call    cs:__imp_SeDeassignSecurity
0x14005bda7  nop     dword ptr [rax+rax+00h]
0x14005bdac  nop
0x14005bdad  mov     rcx, [rbp+68h]; P
0x14005bdb1  test    rcx, rcx
0x14005bdb4  jz      short loc_14005BDC5
0x14005bdb6  xor     edx, edx; Tag
0x14005bdb8  call    cs:__imp_ExFreePoolWithTag
0x14005bdbf  nop     dword ptr [rax+rax+00h]
0x14005bdc4  nop
0x14005bdc5  mov     rcx, [rbp+70h]; P
0x14005bdc9  test    rcx, rcx
0x14005bdcc  jz      short loc_14005BDDD
0x14005bdce  xor     edx, edx; Tag
0x14005bdd0  call    cs:__imp_ExFreePoolWithTag
0x14005bdd7  nop     dword ptr [rax+rax+00h]
0x14005bddc  nop
0x14005bddd  mov     rcx, [rbp+50h]; P
0x14005bde1  test    rcx, rcx
0x14005bde4  jz      short loc_14005BDF5
0x14005bde6  xor     edx, edx; Tag
0x14005bde8  call    cs:__imp_ExFreePoolWithTag
0x14005bdef  nop     dword ptr [rax+rax+00h]
0x14005bdf4  nop
0x14005bdf5  mov     rcx, [rbp+60h]; P
0x14005bdf9  test    rcx, rcx
0x14005bdfc  jz      short loc_14005BE0D
0x14005bdfe  xor     edx, edx; Tag
0x14005be00  call    cs:__imp_ExFreePoolWithTag
0x14005be07  nop     dword ptr [rax+rax+00h]
0x14005be0c  nop
0x14005be0d  mov     r8, [rbp+78h]
0x14005be11  test    r8, r8
0x14005be14  jz      short loc_14005BE5B
0x14005be16  mov     rdx, r8
0x14005be19  mov     [rbp+0B0h], rdx
0x14005be20  test    bl, bl
0x14005be22  jz      short loc_14005BE49
0x14005be24  mov     rcx, [rbp+80h]
0x14005be2b  mov     rdx, [rcx+0D0h]
0x14005be32  mov     [rbp+0B0h], rdx
0x14005be39  mov     [rcx+0D0h], r8
0x14005be40  mov     eax, [rbp+58h]
0x14005be43  mov     [rcx+118h], eax
0x14005be49  test    rdx, rdx
0x14005be4c  jz      short loc_14005BE5B
0x14005be4e  lea     rcx, [rbp+0B0h]
0x14005be55  call    NtfsDereferenceSharedSecurity
  ... truncated ...
```
