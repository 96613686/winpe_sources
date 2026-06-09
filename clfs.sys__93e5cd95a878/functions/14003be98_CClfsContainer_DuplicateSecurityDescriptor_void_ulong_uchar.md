# CClfsContainer::DuplicateSecurityDescriptor(void * &,ulong &,uchar)

- ea: `0x14003be98`
- end: `0x14003c563`
- name: `?DuplicateSecurityDescriptor@CClfsContainer@@QEAAJAEAPEAXAEAKE@Z`
- size: `1739`
- prototype: `__int64 __fastcall(CClfsContainer *__hidden this, void **, unsigned int *, unsigned __int8)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14005ed70`
- `0x140062ef8`
- `0x140078d5c`

## callees

- `0x140017f80`
- `0x14003be98`
- `0x14003f09c`
- `0x140070b5c`

## import_xrefs

- `ntoskrnl!RtlValidSecurityDescriptor` at `0x14003bf64`
- `ntoskrnl!RtlValidSecurityDescriptor` at `0x14003bf64`
- `ntoskrnl!SeCaptureSubjectContext` at `0x14003c262`
- `ntoskrnl!SeCaptureSubjectContext` at `0x14003c262`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14003c326`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14003c441`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14007dd2c`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14003c326`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14003c441`
- `ntoskrnl!SeReleaseSubjectContext` at `0x14007dd2c`
- `ntoskrnl!RtlGetControlSecurityDescriptor` at `0x14003bf95`
- `ntoskrnl!RtlGetControlSecurityDescriptor` at `0x14003bf95`
- `ntoskrnl!RtlSelfRelativeToAbsoluteSD` at `0x14003c01e`
- `ntoskrnl!RtlSelfRelativeToAbsoluteSD` at `0x14003c1ba`
- `ntoskrnl!RtlSelfRelativeToAbsoluteSD` at `0x14003c01e`
- `ntoskrnl!RtlSelfRelativeToAbsoluteSD` at `0x14003c1ba`
- `ntoskrnl!SeTokenType` at `0x14003c29d`
- `ntoskrnl!SeTokenType` at `0x14003c29d`
- `ntoskrnl!SeTokenImpersonationLevel` at `0x14003c2b1`
- `ntoskrnl!SeTokenImpersonationLevel` at `0x14003c2b1`
- `ntoskrnl!SeQueryInformationToken` at `0x14003c2da`
- `ntoskrnl!SeQueryInformationToken` at `0x14003c304`
- `ntoskrnl!SeQueryInformationToken` at `0x14003c2da`
- `ntoskrnl!SeQueryInformationToken` at `0x14003c304`
- `ntoskrnl!RtlSetOwnerSecurityDescriptor` at `0x14003c353`
- `ntoskrnl!RtlSetOwnerSecurityDescriptor` at `0x14003c353`
- `ntoskrnl!RtlSetGroupSecurityDescriptor` at `0x14003c37e`
- `ntoskrnl!RtlSetGroupSecurityDescriptor` at `0x14003c37e`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x14003c3af`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x14003c40e`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x14003c3af`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x14003c40e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003c45c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003c483`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003c4a9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003c4ce`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003c4e4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003c4ff`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003c515`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003c52b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003c541`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007dd4a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007dd6f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007dd9e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007ddc0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007dddb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007ddf6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007de1b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007de3d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007de5c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003c45c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003c483`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003c4a9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003c4ce`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003c4e4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003c4ff`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003c515`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003c52b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003c541`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007dd4a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007dd6f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007dd9e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007ddc0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007dddb`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007ddf6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007de1b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007de3d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007de5c`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003c052`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003c07c`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003c0a6`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003c0d0`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003c0fb`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003c203`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003c3c5`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003c052`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003c07c`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003c0a6`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003c0d0`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003c0fb`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003c203`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003c3c5`

## pseudocode

```c
__int64 __fastcall CClfsContainer::DuplicateSecurityDescriptor(
        CClfsContainer *this,
        void **a2,
        unsigned int *a3,
        char a4)
{
  struct _ACL *v4; // rdi
  struct _ACL *Sacl; // r13
  PSID v6; // r12
  PVOID v7; // r14
  char v8; // si
  NTSTATUS ControlSecurityDescriptor; // ebx
  PSECURITY_DESCRIPTOR v10; // r15
  PVOID v11; // rbx
  ULONG v12; // eax
  ULONG v13; // ecx
  PVOID PrimaryGroup; // rdx
  PVOID PoolWithTag; // rax
  PACCESS_TOKEN PrimaryToken; // rdi
  PSECURITY_DESCRIPTOR v17; // rdi
  PVOID v18; // rax
  PVOID *v19; // rdi
  ULONG AbsoluteSecurityDescriptorSize; // [rsp+68h] [rbp-C0h] BYREF
  PSID Owner; // [rsp+70h] [rbp-B8h]
  PVOID v23; // [rsp+78h] [rbp-B0h]
  ULONG OwnerSize; // [rsp+80h] [rbp-A8h] BYREF
  ULONG PrimaryGroupSize; // [rsp+84h] [rbp-A4h] BYREF
  ULONG SaclSize; // [rsp+88h] [rbp-A0h] BYREF
  ULONG DaclSize; // [rsp+8Ch] [rbp-9Ch] BYREF
  PSECURITY_DESCRIPTOR AbsoluteSecurityDescriptor; // [rsp+90h] [rbp-98h] BYREF
  PVOID TokenInformation; // [rsp+98h] [rbp-90h] BYREF
  PVOID P; // [rsp+A0h] [rbp-88h] BYREF
  SIZE_T NumberOfBytes; // [rsp+A8h] [rbp-80h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+B0h] [rbp-78h] BYREF
  PVOID v33; // [rsp+B8h] [rbp-70h]
  ULONG Revision; // [rsp+C0h] [rbp-68h] BYREF
  struct _ACL *v35; // [rsp+C8h] [rbp-60h]
  struct _SECURITY_SUBJECT_CONTEXT SubjectContext; // [rsp+D0h] [rbp-58h] BYREF
  unsigned int *Control; // [rsp+140h] [rbp+18h] BYREF
  char v39; // [rsp+148h] [rbp+20h]

  v39 = a4;
  Control = a3;
  AbsoluteSecurityDescriptor = 0;
  v4 = 0;
  v33 = 0;
  Sacl = 0;
  v35 = 0;
  v6 = 0;
  Owner = 0;
  v7 = 0;
  v23 = 0;
  TokenInformation = 0;
  P = 0;
  memset(&SubjectContext, 0, sizeof(SubjectContext));
  AbsoluteSecurityDescriptorSize = 0;
  DaclSize = 0;
  SaclSize = 0;
  OwnerSize = 0;
  PrimaryGroupSize = 0;
  v8 = 0;
  SecurityDescriptor = 0;
  LODWORD(NumberOfBytes) = 0;
  LOWORD(Control) = 0;
  Revision = 0;
  ControlSecurityDescriptor = CClfsContainer::QuerySecurityDescriptor(
                                this,
                                &SecurityDescriptor,
                                (unsigned int *)&NumberOfBytes);
  v10 = SecurityDescriptor;
  if ( ControlSecurityDescriptor < 0 )
    goto LABEL_48;
  if ( !RtlValidSecurityDescriptor(SecurityDescriptor) )
  {
    ControlSecurityDescriptor = -1073741703;
LABEL_48:
    v19 = a2;
    goto LABEL_49;
  }
  ControlSecurityDescriptor = RtlGetControlSecurityDescriptor(v10, (PSECURITY_DESCRIPTOR_CONTROL)&Control, &Revision);
  if ( ControlSecurityDescriptor < 0 )
    goto LABEL_48;
  if ( (__int16)Control >= 0 )
  {
    AbsoluteSecurityDescriptorSize = NumberOfBytes;
    PoolWithTag = ExAllocatePoolWithTag(PagedPool, (unsigned int)NumberOfBytes, 0x73666C43u);
    AbsoluteSecurityDescriptor = PoolWithTag;
    if ( PoolWithTag )
    {
      memmove(PoolWithTag, v10, AbsoluteSecurityDescriptorSize);
      goto LABEL_30;
    }
    goto LABEL_27;
  }
  ControlSecurityDescriptor = RtlSelfRelativeToAbsoluteSD(
                                v10,
                                0,
                                &AbsoluteSecurityDescriptorSize,
                                0,
                                &DaclSize,
                                0,
                                &SaclSize,
                                0,
                                &OwnerSize,
                                0,
                                &PrimaryGroupSize);
  if ( ControlSecurityDescriptor != -1073741789 )
    goto LABEL_48;
  v11 = ExAllocatePoolWithTag(PagedPool, AbsoluteSecurityDescriptorSize, 0x73666C43u);
  AbsoluteSecurityDescriptor = v11;
  if ( DaclSize )
  {
    v4 = (struct _ACL *)ExAllocatePoolWithTag(PagedPool, DaclSize, 0x73666C43u);
    v33 = v4;
  }
  if ( SaclSize )
  {
    Sacl = (struct _ACL *)ExAllocatePoolWithTag(PagedPool, SaclSize, 0x73666C43u);
    v35 = Sacl;
  }
  v12 = OwnerSize;
  if ( OwnerSize )
  {
    Owner = ExAllocatePoolWithTag(PagedPool, OwnerSize, 0x73666C43u);
    v12 = OwnerSize;
  }
  v13 = PrimaryGroupSize;
  if ( PrimaryGroupSize )
  {
    PrimaryGroup = ExAllocatePoolWithTag(PagedPool, PrimaryGroupSize, 0x73666C43u);
    v23 = PrimaryGroup;
    v12 = OwnerSize;
    v13 = PrimaryGroupSize;
  }
  else
  {
    PrimaryGroup = v23;
  }
  if ( !v11 || !Sacl && SaclSize || !v4 && DaclSize || !Owner && v12 || !PrimaryGroup && v13 )
  {
LABEL_27:
    ControlSecurityDescriptor = -1073741670;
    goto LABEL_47;
  }
  ControlSecurityDescriptor = RtlSelfRelativeToAbsoluteSD(
                                v10,
                                v11,
                                &AbsoluteSecurityDescriptorSize,
                                v4,
                                &DaclSize,
                                Sacl,
                                &SaclSize,
                                Owner,
                                &OwnerSize,
                                PrimaryGroup,
                                &PrimaryGroupSize);
  if ( ControlSecurityDescriptor < 0 )
  {
LABEL_47:
    v6 = Owner;
    v7 = v23;
    goto LABEL_48;
  }
LABEL_30:
  ControlSecurityDescriptor = CClfsContainer::SetDefaultSaclSecurityDescriptor(
                                &AbsoluteSecurityDescriptor,
                                &AbsoluteSecurityDescriptorSize);
  if ( ControlSecurityDescriptor < 0 )
    goto LABEL_47;
  if ( v39 )
  {
    SeCaptureSubjectContext(&SubjectContext);
    v8 = 1;
    PrimaryToken = SubjectContext.PrimaryToken;
    if ( SubjectContext.ClientToken )
      PrimaryToken = SubjectContext.ClientToken;
    if ( !PrimaryToken )
    {
      ControlSecurityDescriptor = 3;
      goto LABEL_47;
    }
    if ( SeTokenType(PrimaryToken) == TokenImpersonation && (int)SeTokenImpersonationLevel(PrimaryToken) < 2 )
    {
      ControlSecurityDescriptor = -1073741790;
      goto LABEL_47;
    }
    ControlSecurityDescriptor = SeQueryInformationToken(PrimaryToken, TokenUser, &TokenInformation);
    if ( ControlSecurityDescriptor < 0 )
      goto LABEL_47;
    ControlSecurityDescriptor = SeQueryInformationToken(PrimaryToken, TokenPrimaryGroup, &P);
    if ( ControlSecurityDescriptor < 0 )
      goto LABEL_47;
    SeReleaseSubjectContext(&SubjectContext);
    v8 = 0;
    v17 = AbsoluteSecurityDescriptor;
    ControlSecurityDescriptor = RtlSetOwnerSecurityDescriptor(AbsoluteSecurityDescriptor, *(PSID *)TokenInformation, 0);
    if ( ControlSecurityDescriptor < 0 )
      goto LABEL_47;
    ControlSecurityDescriptor = RtlSetGroupSecurityDescriptor(v17, *(PSID *)P, 0);
    if ( ControlSecurityDescriptor < 0 )
      goto LABEL_47;
  }
  AbsoluteSecurityDescriptorSize = 0;
  RtlAbsoluteToSelfRelativeSD(AbsoluteSecurityDescriptor, 0, &AbsoluteSecurityDescriptorSize);
  v18 = ExAllocatePoolWithTag(PagedPool, AbsoluteSecurityDescriptorSize, 0x73666C43u);
  v19 = a2;
  *a2 = v18;
  if ( v18 )
    ControlSecurityDescriptor = RtlAbsoluteToSelfRelativeSD(
                                  AbsoluteSecurityDescriptor,
                                  v18,
                                  &AbsoluteSecurityDescriptorSize);
  else
    ControlSecurityDescriptor = -1073741670;
  v8 = 0;
  v7 = v23;
  v6 = Owner;
LABEL_49:
  if ( v8 )
    SeReleaseSubjectContext(&SubjectContext);
  if ( TokenInformation )
  {
    ExFreePoolWithTag(TokenInformation, 0);
    TokenInformation = 0;
  }
  if ( P )
  {
    ExFreePoolWithTag(P, 0);
    P = 0;
  }
  if ( ControlSecurityDescriptor < 0 )
  {
    if ( *v19 )
      ExFreePoolWithTag(*v19, 0);
    *v19 = 0;
  }
  if ( AbsoluteSecurityDescriptor )
    ExFreePoolWithTag(AbsoluteSecurityDescriptor, 0);
  if ( v10 )
    ExFreePoolWithTag(v10, 0);
  if ( v33 )
    ExFreePoolWithTag(v33, 0);
  if ( Sacl )
    ExFreePoolWithTag(Sacl, 0);
  if ( v6 )
    ExFreePoolWithTag(v6, 0);
  if ( v7 )
    ExFreePoolWithTag(v7, 0);
  return (unsigned int)ControlSecurityDescriptor;
}

```

## disassembly

```asm
0x14003be98  mov     r11, rsp
0x14003be9b  mov     [r11+20h], r9b
0x14003be9f  mov     [r11+18h], r8
0x14003bea3  mov     [r11+10h], rdx
0x14003bea7  push    rbx
0x14003bea8  push    rsi
0x14003bea9  push    rdi
0x14003beaa  push    r12
0x14003beac  push    r13
0x14003beae  push    r14
0x14003beb0  push    r15
0x14003beb2  sub     rsp, 0F0h
0x14003beb9  xor     r15d, r15d
0x14003bebc  mov     [r11-98h], r15
0x14003bec3  mov     edi, r15d
0x14003bec6  mov     [r11-70h], r15
0x14003beca  mov     r13d, r15d
0x14003becd  mov     [r11-60h], r15
0x14003bed1  mov     r12d, r15d
0x14003bed4  mov     [rsp+128h+var_B8], r15
0x14003bed9  mov     r14d, r15d
0x14003bedc  mov     [rsp+128h+var_B0], r15
0x14003bee1  mov     [r11-90h], r15
0x14003bee8  mov     [r11-88h], r15
0x14003beef  xorps   xmm0, xmm0
0x14003bef2  movups  xmmword ptr [r11-58h], xmm0
0x14003bef7  movups  xmmword ptr [r11-48h], xmm0
0x14003befc  mov     [rsp+128h+AbsoluteSecurityDescriptorSize], r15d
0x14003bf01  mov     [r11-9Ch], r15d
0x14003bf08  mov     [r11-0A0h], r15d
0x14003bf0f  mov     [r11-0A8h], r15d
0x14003bf16  mov     [r11-0A4h], r15d
0x14003bf1d  mov     [rsp+128h+var_C4], r15d
0x14003bf22  mov     sil, r15b
0x14003bf25  mov     [rsp+128h+var_C8], r15b
0x14003bf2a  mov     [r11-78h], r15
0x14003bf2e  mov     [r11-80h], r15d
0x14003bf32  mov     eax, r15d
0x14003bf35  mov     [r11+18h], ax
0x14003bf3a  mov     [r11-68h], r15d
0x14003bf3e  lea     r8, [r11-80h]; unsigned int *
0x14003bf42  lea     rdx, [r11-78h]; void **
0x14003bf46  call    ?QuerySecurityDescriptor@CClfsContainer@@QEAAJAEAPEAXAEAK@Z; CClfsContainer::QuerySecurityDescriptor(void * &,ulong &)
0x14003bf4b  mov     ebx, eax
0x14003bf4d  mov     [rsp+128h+var_C4], eax
0x14003bf51  mov     r15, [rsp+128h+SecurityDescriptor]
0x14003bf59  test    eax, eax
0x14003bf5b  js      loc_14003C42C
0x14003bf61  mov     rcx, r15; SecurityDescriptor
0x14003bf64  call    cs:__imp_RtlValidSecurityDescriptor
0x14003bf6b  nop     dword ptr [rax+rax+00h]
0x14003bf70  test    al, al
0x14003bf72  jnz     short loc_14003BF82
0x14003bf74  mov     ebx, 0C0000079h
0x14003bf79  mov     [rsp+128h+var_C4], ebx
0x14003bf7d  jmp     loc_14003C42C
0x14003bf82  lea     r8, [rsp+128h+Revision]; Revision
0x14003bf8a  lea     rdx, [rsp+128h+Control]; Control
0x14003bf92  mov     rcx, r15; SecurityDescriptor
0x14003bf95  call    cs:__imp_RtlGetControlSecurityDescriptor
0x14003bf9c  nop     dword ptr [rax+rax+00h]
0x14003bfa1  mov     ebx, eax
0x14003bfa3  mov     [rsp+128h+var_C4], eax
0x14003bfa7  test    eax, eax
0x14003bfa9  js      loc_14003C42C
0x14003bfaf  mov     eax, 8000h
0x14003bfb4  test    word ptr [rsp+128h+Control], ax
0x14003bfbc  jz      loc_14003C1E4
0x14003bfc2  lea     rax, [rsp+128h+var_A4]
0x14003bfca  mov     [rsp+128h+PrimaryGroupSize], rax; PrimaryGroupSize
0x14003bfcf  mov     [rsp+128h+PrimaryGroup], 0; PrimaryGroup
0x14003bfd8  lea     rax, [rsp+128h+var_A8]
0x14003bfe0  mov     [rsp+128h+OwnerSize], rax; OwnerSize
0x14003bfe5  mov     [rsp+128h+Owner], 0; Owner
0x14003bfee  lea     rax, [rsp+128h+var_A0]
0x14003bff6  mov     [rsp+128h+SaclSize], rax; SaclSize
0x14003bffb  mov     [rsp+128h+Sacl], 0; Sacl
0x14003c004  lea     rax, [rsp+128h+var_9C]
0x14003c00c  mov     [rsp+128h+DaclSize], rax; DaclSize
0x14003c011  xor     r9d, r9d; Dacl
0x14003c014  lea     r8, [rsp+128h+AbsoluteSecurityDescriptorSize]; AbsoluteSecurityDescriptorSize
0x14003c019  xor     edx, edx; AbsoluteSecurityDescriptor
0x14003c01b  mov     rcx, r15; SelfRelativeSecurityDescriptor
0x14003c01e  call    cs:__imp_RtlSelfRelativeToAbsoluteSD
0x14003c025  nop     dword ptr [rax+rax+00h]
0x14003c02a  mov     ebx, eax
0x14003c02c  cmp     eax, 0C0000023h
0x14003c031  jz      short loc_14003C03C
0x14003c033  mov     [rsp+128h+var_C4], eax
0x14003c037  jmp     loc_14003C42C
0x14003c03c  mov     edx, [rsp+128h+AbsoluteSecurityDescriptorSize]; NumberOfBytes
0x14003c040  mov     r12d, 73666C43h
0x14003c046  mov     r8d, r12d; Tag
0x14003c049  mov     r14d, 1
0x14003c04f  mov     ecx, r14d; PoolType
0x14003c052  call    cs:__imp_ExAllocatePoolWithTag
0x14003c059  nop     dword ptr [rax+rax+00h]
0x14003c05e  mov     rbx, rax
0x14003c061  mov     [rsp+128h+AbsoluteSecurityDescriptor], rax
0x14003c069  mov     ecx, [rsp+128h+var_9C]
0x14003c070  test    ecx, ecx
0x14003c072  jz      short loc_14003C093
0x14003c074  mov     edx, ecx; NumberOfBytes
0x14003c076  mov     r8d, r12d; Tag
0x14003c079  mov     ecx, r14d; PoolType
0x14003c07c  call    cs:__imp_ExAllocatePoolWithTag
0x14003c083  nop     dword ptr [rax+rax+00h]
0x14003c088  mov     rdi, rax
0x14003c08b  mov     [rsp+128h+var_70], rax
0x14003c093  mov     eax, [rsp+128h+var_A0]
0x14003c09a  test    eax, eax
0x14003c09c  jz      short loc_14003C0BD
0x14003c09e  mov     edx, eax; NumberOfBytes
0x14003c0a0  mov     r8d, r12d; Tag
0x14003c0a3  mov     ecx, r14d; PoolType
0x14003c0a6  call    cs:__imp_ExAllocatePoolWithTag
0x14003c0ad  nop     dword ptr [rax+rax+00h]
0x14003c0b2  mov     r13, rax
0x14003c0b5  mov     [rsp+128h+var_60], rax
0x14003c0bd  mov     eax, [rsp+128h+var_A8]
0x14003c0c4  test    eax, eax
0x14003c0c6  jz      short loc_14003C0E8
0x14003c0c8  mov     edx, eax; NumberOfBytes
0x14003c0ca  mov     r8d, r12d; Tag
0x14003c0cd  mov     ecx, r14d; PoolType
0x14003c0d0  call    cs:__imp_ExAllocatePoolWithTag
0x14003c0d7  nop     dword ptr [rax+rax+00h]
0x14003c0dc  mov     [rsp+128h+var_B8], rax
0x14003c0e1  mov     eax, [rsp+128h+var_A8]
0x14003c0e8  mov     ecx, [rsp+128h+var_A4]
0x14003c0ef  test    ecx, ecx
0x14003c0f1  jz      short loc_14003C11F
0x14003c0f3  mov     edx, ecx; NumberOfBytes
0x14003c0f5  mov     r8d, r12d; Tag
0x14003c0f8  mov     ecx, r14d; PoolType
0x14003c0fb  call    cs:__imp_ExAllocatePoolWithTag
0x14003c102  nop     dword ptr [rax+rax+00h]
0x14003c107  mov     rdx, rax
0x14003c10a  mov     [rsp+128h+var_B0], rax
0x14003c10f  mov     eax, [rsp+128h+var_A8]
0x14003c116  mov     ecx, [rsp+128h+var_A4]
0x14003c11d  jmp     short loc_14003C124
0x14003c11f  mov     rdx, [rsp+128h+var_B0]
0x14003c124  test    rbx, rbx
0x14003c127  jz      loc_14003C1D6
0x14003c12d  test    r13, r13
0x14003c130  jnz     short loc_14003C140
0x14003c132  cmp     [rsp+128h+var_A0], r13d
0x14003c13a  jnz     loc_14003C1D6
0x14003c140  test    rdi, rdi
0x14003c143  jnz     short loc_14003C152
0x14003c145  cmp     [rsp+128h+var_9C], edi
0x14003c14c  jnz     loc_14003C1D6
0x14003c152  mov     r8, [rsp+128h+var_B8]
0x14003c157  test    r8, r8
0x14003c15a  jnz     short loc_14003C160
0x14003c15c  test    eax, eax
0x14003c15e  jnz     short loc_14003C1D6
0x14003c160  test    rdx, rdx
0x14003c163  jnz     short loc_14003C169
0x14003c165  test    ecx, ecx
0x14003c167  jnz     short loc_14003C1D6
0x14003c169  lea     rax, [rsp+128h+var_A4]
0x14003c171  mov     [rsp+128h+PrimaryGroupSize], rax; PrimaryGroupSize
0x14003c176  mov     [rsp+128h+PrimaryGroup], rdx; PrimaryGroup
0x14003c17b  lea     rax, [rsp+128h+var_A8]
0x14003c183  mov     [rsp+128h+OwnerSize], rax; OwnerSize
0x14003c188  mov     [rsp+128h+Owner], r8; Owner
0x14003c18d  lea     rax, [rsp+128h+var_A0]
0x14003c195  mov     [rsp+128h+SaclSize], rax; SaclSize
0x14003c19a  mov     [rsp+128h+Sacl], r13; Sacl
0x14003c19f  lea     rax, [rsp+128h+var_9C]
0x14003c1a7  mov     [rsp+128h+DaclSize], rax; DaclSize
0x14003c1ac  mov     r9, rdi; Dacl
0x14003c1af  lea     r8, [rsp+128h+AbsoluteSecurityDescriptorSize]; AbsoluteSecurityDescriptorSize
0x14003c1b4  mov     rdx, rbx; AbsoluteSecurityDescriptor
0x14003c1b7  mov     rcx, r15; SelfRelativeSecurityDescriptor
0x14003c1ba  call    cs:__imp_RtlSelfRelativeToAbsoluteSD
0x14003c1c1  nop     dword ptr [rax+rax+00h]
0x14003c1c6  mov     ebx, eax
0x14003c1c8  mov     [rsp+128h+var_C4], eax
0x14003c1cc  test    eax, eax
0x14003c1ce  js      loc_14003C422
0x14003c1d4  jmp     short loc_14003C22C
0x14003c1d6  mov     ebx, 0C000009Ah
0x14003c1db  mov     [rsp+128h+var_C4], ebx
0x14003c1df  jmp     loc_14003C422
0x14003c1e4  mov     eax, dword ptr [rsp+128h+NumberOfBytes]
0x14003c1eb  mov     [rsp+128h+AbsoluteSecurityDescriptorSize], eax
0x14003c1ef  mov     edx, eax; NumberOfBytes
0x14003c1f1  mov     r12d, 73666C43h
0x14003c1f7  mov     r8d, r12d; Tag
0x14003c1fa  mov     r14d, 1
0x14003c200  mov     ecx, r14d; PoolType
0x14003c203  call    cs:__imp_ExAllocatePoolWithTag
0x14003c20a  nop     dword ptr [rax+rax+00h]
0x14003c20f  mov     [rsp+128h+AbsoluteSecurityDescriptor], rax
0x14003c217  test    rax, rax
0x14003c21a  jz      short loc_14003C1D6
0x14003c21c  mov     r8d, [rsp+128h+AbsoluteSecurityDescriptorSize]; Size
0x14003c221  mov     rdx, r15; Src
0x14003c224  mov     rcx, rax; void *
0x14003c227  call    memmove
0x14003c22c  lea     rdx, [rsp+128h+AbsoluteSecurityDescriptorSize]; unsigned int *
0x14003c231  lea     rcx, [rsp+128h+AbsoluteSecurityDescriptor]; void **
0x14003c239  call    ?SetDefaultSaclSecurityDescriptor@CClfsContainer@@CAJAEAPEAXAEAK@Z; CClfsContainer::SetDefaultSaclSecurityDescriptor(void * &,ulong &)
0x14003c23e  mov     ebx, eax
0x14003c240  mov     [rsp+128h+var_C4], eax
0x14003c244  test    eax, eax
0x14003c246  js      loc_14003C422
0x14003c24c  cmp     [rsp+128h+arg_18], 0
0x14003c254  jz      loc_14003C398
0x14003c25a  lea     rcx, [rsp+128h+SubjectContext]; SubjectContext
0x14003c262  call    cs:__imp_SeCaptureSubjectContext
0x14003c269  nop     dword ptr [rax+rax+00h]
0x14003c26e  mov     sil, r14b
0x14003c271  mov     [rsp+128h+var_C8], r14b
0x14003c276  mov     rdi, [rsp+128h+SubjectContext.PrimaryToken]
0x14003c27e  mov     rax, [rsp+128h+SubjectContext.ClientToken]
0x14003c286  test    rax, rax
0x14003c289  cmovnz  rdi, rax
0x14003c28d  test    rdi, rdi
0x14003c290  jnz     short loc_14003C29A
0x14003c292  lea     ebx, [rdi+3]
0x14003c295  jmp     loc_14003C1DB
0x14003c29a  mov     rcx, rdi; Token
0x14003c29d  call    cs:__imp_SeTokenType
0x14003c2a4  nop     dword ptr [rax+rax+00h]
0x14003c2a9  cmp     eax, 2
0x14003c2ac  jnz     short loc_14003C2CC
0x14003c2ae  mov     rcx, rdi
0x14003c2b1  call    cs:__imp_SeTokenImpersonationLevel
0x14003c2b8  nop     dword ptr [rax+rax+00h]
0x14003c2bd  cmp     eax, 2
0x14003c2c0  jge     short loc_14003C2CC
0x14003c2c2  mov     ebx, 0C0000022h
0x14003c2c7  jmp     loc_14003C1DB
0x14003c2cc  lea     r8, [rsp+128h+TokenInformation]; TokenInformation
0x14003c2d4  mov     edx, r14d; TokenInformationClass
0x14003c2d7  mov     rcx, rdi; Token
0x14003c2da  call    cs:__imp_SeQueryInformationToken
0x14003c2e1  nop     dword ptr [rax+rax+00h]
0x14003c2e6  mov     ebx, eax
0x14003c2e8  mov     [rsp+128h+var_C4], eax
0x14003c2ec  test    eax, eax
0x14003c2ee  js      loc_14003C422
0x14003c2f4  lea     r8, [rsp+128h+P]; TokenInformation
0x14003c2fc  mov     edx, 5; TokenInformationClass
0x14003c301  mov     rcx, rdi; Token
0x14003c304  call    cs:__imp_SeQueryInformationToken
0x14003c30b  nop     dword ptr [rax+rax+00h]
0x14003c310  mov     ebx, eax
0x14003c312  mov     [rsp+128h+var_C4], eax
0x14003c316  test    eax, eax
0x14003c318  js      loc_14003C422
0x14003c31e  lea     rcx, [rsp+128h+SubjectContext]; SubjectContext
0x14003c326  call    cs:__imp_SeReleaseSubjectContext
0x14003c32d  nop     dword ptr [rax+rax+00h]
0x14003c332  xor     sil, sil
0x14003c335  mov     [rsp+128h+var_C8], sil
0x14003c33a  xor     r8d, r8d; OwnerDefaulted
0x14003c33d  mov     rdx, [rsp+128h+TokenInformation]
0x14003c345  mov     rdx, [rdx]; Owner
0x14003c348  mov     rdi, [rsp+128h+AbsoluteSecurityDescriptor]
0x14003c350  mov     rcx, rdi; SecurityDescriptor
0x14003c353  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x14003c35a  nop     dword ptr [rax+rax+00h]
0x14003c35f  mov     ebx, eax
0x14003c361  mov     [rsp+128h+var_C4], eax
0x14003c365  test    eax, eax
0x14003c367  js      loc_14003C422
0x14003c36d  xor     r8d, r8d; GroupDefaulted
0x14003c370  mov     rdx, [rsp+128h+P]
0x14003c378  mov     rdx, [rdx]; Group
0x14003c37b  mov     rcx, rdi; SecurityDescriptor
0x14003c37e  call    cs:__imp_RtlSetGroupSecurityDescriptor
0x14003c385  nop     dword ptr [rax+rax+00h]
0x14003c38a  mov     ebx, eax
0x14003c38c  mov     [rsp+128h+var_C4], eax
0x14003c390  test    eax, eax
0x14003c392  js      loc_14003C422
0x14003c398  mov     [rsp+128h+AbsoluteSecurityDescriptorSize], 0
0x14003c3a0  lea     r8, [rsp+128h+AbsoluteSecurityDescriptorSize]; BufferLength
0x14003c3a5  xor     edx, edx; SelfRelativeSecurityDescriptor
0x14003c3a7  mov     rcx, [rsp+128h+AbsoluteSecurityDescriptor]; AbsoluteSecurityDescriptor
0x14003c3af  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x14003c3b6  nop     dword ptr [rax+rax+00h]
0x14003c3bb  mov     edx, [rsp+128h+AbsoluteSecurityDescriptorSize]; NumberOfBytes
0x14003c3bf  mov     r8d, r12d; Tag
0x14003c3c2  mov     ecx, r14d; PoolType
0x14003c3c5  call    cs:__imp_ExAllocatePoolWithTag
0x14003c3cc  nop     dword ptr [rax+rax+00h]
0x14003c3d1  mov     rdi, [rsp+128h+arg_8]
0x14003c3d9  mov     [rdi], rax
0x14003c3dc  test    rax, rax
0x14003c3df  jnz     short loc_14003C3FE
0x14003c3e1  mov     ebx, 0C000009Ah
0x14003c3e6  mov     [rsp+128h+var_C4], ebx
0x14003c3ea  xor     sil, sil
0x14003c3ed  mov     [rsp+128h+var_C8], sil
  ... truncated ...
```
