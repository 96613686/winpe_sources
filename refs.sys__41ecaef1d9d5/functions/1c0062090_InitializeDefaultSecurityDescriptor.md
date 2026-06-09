# InitializeDefaultSecurityDescriptor

- ea: `0x1c0062090`
- end: `0x1c00623e8`
- name: `InitializeDefaultSecurityDescriptor`
- size: `856`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1c01d97ac`

## callees

- `0x1c000f770`
- `0x1c0062090`
- `0x1c0068168`
- `0x1c0068960`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c0062105`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c006214a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c00621bc`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c0062220`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c0062105`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c006214a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c00621bc`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1c0062220`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c006236d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0062383`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0062394`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00623a5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c006c490`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c006c4a8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c006c4c0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c006c4d8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c006236d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0062383`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0062394`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00623a5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c006c490`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c006c4a8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c006c4c0`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c006c4d8`
- `ntoskrnl!ExRaiseStatus` at `0x1c008eb3e`
- `ntoskrnl!ExRaiseStatus` at `0x1c008eb3e`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1c006211c`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1c006211c`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1c0062357`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1c006c478`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1c0062357`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1c006c478`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1c0062134`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1c00621a6`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1c0062134`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1c00621a6`
- `ntoskrnl!RtlInitializeSid` at `0x1c006216c`
- `ntoskrnl!RtlInitializeSid` at `0x1c00621de`
- `ntoskrnl!RtlInitializeSid` at `0x1c006216c`
- `ntoskrnl!RtlInitializeSid` at `0x1c00621de`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1c006217d`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1c0062191`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1c00621ef`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1c006217d`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1c0062191`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1c00621ef`
- `ntoskrnl!RtlCreateAcl` at `0x1c006223f`
- `ntoskrnl!RtlCreateAcl` at `0x1c006223f`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1c006226a`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1c0062295`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1c006226a`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1c0062295`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1c00622b9`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1c00622b9`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1c00622e0`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1c00622e0`
- `ntoskrnl!SeAssignSecurity` at `0x1c0062325`
- `ntoskrnl!SeAssignSecurity` at `0x1c0062325`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1c00622f6`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1c00622f6`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x1c0062342`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x1c0062342`

## pseudocode

```c
void InitializeDefaultSecurityDescriptor()
{
  struct _SECURITY_SUBJECT_CONTEXT *SubjectContext; // rsi
  ULONG v1; // eax
  unsigned __int8 *PoolWithTag; // r14
  ULONG v3; // eax
  unsigned __int8 *v4; // r15
  ULONG v5; // ebx
  struct _ACL *v6; // rdi
  NTSTATUS Acl; // ebx
  struct _GENERIC_MAPPING *GenericMapping; // rax
  NTSTATUS Status; // [rsp+44h] [rbp-64h]
  _OWORD SecurityDescriptor[2]; // [rsp+68h] [rbp-40h] BYREF
  __int64 v11; // [rsp+88h] [rbp-20h]
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+90h] [rbp-18h] BYREF

  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  v11 = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  SubjectContext = (struct _SECURITY_SUBJECT_CONTEXT *)ExAllocatePoolWithTag((POOL_TYPE)17, 0x20u, 0x4A666552u);
  SeCaptureSubjectContext(SubjectContext);
  v1 = RtlLengthRequiredSid(2u);
  PoolWithTag = (unsigned __int8 *)ExAllocatePoolWithTag((POOL_TYPE)17, v1, 0x4A666552u);
  RtlInitializeSid(PoolWithTag, &IdentifierAuthority, 2u);
  *RtlSubAuthoritySid(PoolWithTag, 0) = 32;
  *RtlSubAuthoritySid(PoolWithTag, 1u) = 544;
  v3 = RtlLengthRequiredSid(1u);
  v4 = (unsigned __int8 *)ExAllocatePoolWithTag((POOL_TYPE)17, v3, 0x4A666552u);
  RtlInitializeSid(v4, &IdentifierAuthority, 1u);
  *RtlSubAuthoritySid(v4, 0) = 18;
  v5 = 4 * (PoolWithTag[1] + v4[1]) + 56;
  v6 = (struct _ACL *)ExAllocatePoolWithTag((POOL_TYPE)17, v5, 0x4A666552u);
  Acl = RtlCreateAcl(v6, v5, 2u);
  Status = Acl;
  if ( Acl >= 0 )
  {
    Acl = RtlAddAccessAllowedAce(v6, 2u, 0x10000000u, v4);
    Status = Acl;
    if ( Acl >= 0 )
    {
      Acl = RtlAddAccessAllowedAce(v6, 2u, 0x10000000u, PoolWithTag);
      Status = Acl;
      if ( Acl >= 0 )
      {
        Acl = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
        Status = Acl;
        if ( Acl >= 0 )
        {
          Acl = RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, v6, 0);
          Status = Acl;
          if ( Acl >= 0 )
          {
            GenericMapping = IoGetFileObjectGenericMapping();
            Acl = SeAssignSecurity(0, SecurityDescriptor, &NewDescriptor, 0, SubjectContext, GenericMapping, PagedPool);
            Status = Acl;
            if ( Acl >= 0 )
              Length = RtlLengthSecurityDescriptor(NewDescriptor);
          }
        }
      }
    }
  }
  SeReleaseSubjectContext(SubjectContext);
  if ( SubjectContext )
    ExFreePoolWithTag(SubjectContext, 0);
  if ( v6 )
    ExFreePoolWithTag(v6, 0);
  ExFreePoolWithTag(PoolWithTag, 0);
  ExFreePoolWithTag(v4, 0);
  if ( Acl < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(
        WPP_GLOBAL_Control->AttachedDevice,
        18,
        WPP_2bcc4d02ea773ee5fd3d1fc8b1a95a7b_Traceguids,
        (unsigned int)Acl);
    }
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(Status);
    ExRaiseStatus(Status);
  }
}

```

## disassembly

```asm
0x1c0062090  mov     r11, rsp
0x1c0062093  mov     [r11+8], rbx
0x1c0062097  mov     [r11+10h], rsi
0x1c006209b  mov     [r11+18h], rdi
0x1c006209f  mov     [r11+20h], r14
0x1c00620a3  push    r15
0x1c00620a5  sub     rsp, 0A0h
0x1c00620ac  mov     rax, cs:__security_cookie
0x1c00620b3  xor     rax, rsp
0x1c00620b6  mov     [rsp+0A8h+var_10], rax
0x1c00620be  and     qword ptr [r11-60h], 0
0x1c00620c3  mov     [rsp+0A8h+var_68], 0
0x1c00620c8  and     qword ptr [r11-58h], 0
0x1c00620cd  and     qword ptr [r11-50h], 0
0x1c00620d2  and     qword ptr [r11-48h], 0
0x1c00620d7  xorps   xmm0, xmm0
0x1c00620da  xor     eax, eax
0x1c00620dc  movups  [rsp+0A8h+SecurityDescriptor], xmm0
0x1c00620e1  movups  [rsp+0A8h+var_30], xmm0
0x1c00620e6  mov     [r11-20h], rax
0x1c00620ea  mov     [r11-18h], eax
0x1c00620ee  mov     word ptr [r11-14h], 500h
0x1c00620f5  lea     ebx, [rax+20h]
0x1c00620f8  mov     r8d, 4A666552h; Tag
0x1c00620fe  mov     edx, ebx; NumberOfBytes
0x1c0062100  lea     edi, [rax+11h]
0x1c0062103  mov     ecx, edi; PoolType
0x1c0062105  call    cs:__imp_ExAllocatePoolWithTag
0x1c006210c  nop     dword ptr [rax+rax+00h]
0x1c0062111  mov     rsi, rax
0x1c0062114  mov     [rsp+0A8h+var_60], rax
0x1c0062119  mov     rcx, rax; SubjectContext
0x1c006211c  call    cs:__imp_SeCaptureSubjectContext
0x1c0062123  nop     dword ptr [rax+rax+00h]
0x1c0062128  lea     r15d, [rbx-1Fh]
0x1c006212c  mov     [rsp+0A8h+var_68], r15b
0x1c0062131  lea     ecx, [rbx-1Eh]; SubAuthorityCount
0x1c0062134  call    cs:__imp_RtlLengthRequiredSid
0x1c006213b  nop     dword ptr [rax+rax+00h]
0x1c0062140  mov     edx, eax; NumberOfBytes
0x1c0062142  mov     r8d, 4A666552h; Tag
0x1c0062148  mov     ecx, edi; PoolType
0x1c006214a  call    cs:__imp_ExAllocatePoolWithTag
0x1c0062151  nop     dword ptr [rax+rax+00h]
0x1c0062156  mov     r14, rax
0x1c0062159  mov     [rsp+0A8h+var_50], rax
0x1c006215e  mov     r8b, 2; SubAuthorityCount
0x1c0062161  lea     rdx, [rsp+0A8h+IdentifierAuthority]; IdentifierAuthority
0x1c0062169  mov     rcx, rax; Sid
0x1c006216c  call    cs:__imp_RtlInitializeSid
0x1c0062173  nop     dword ptr [rax+rax+00h]
0x1c0062178  xor     edx, edx; SubAuthority
0x1c006217a  mov     rcx, r14; Sid
0x1c006217d  call    cs:__imp_RtlSubAuthoritySid
0x1c0062184  nop     dword ptr [rax+rax+00h]
0x1c0062189  mov     [rax], ebx
0x1c006218b  mov     edx, r15d; SubAuthority
0x1c006218e  mov     rcx, r14; Sid
0x1c0062191  call    cs:__imp_RtlSubAuthoritySid
0x1c0062198  nop     dword ptr [rax+rax+00h]
0x1c006219d  mov     dword ptr [rax], 220h
0x1c00621a3  mov     ecx, r15d; SubAuthorityCount
0x1c00621a6  call    cs:__imp_RtlLengthRequiredSid
0x1c00621ad  nop     dword ptr [rax+rax+00h]
0x1c00621b2  mov     edx, eax; NumberOfBytes
0x1c00621b4  mov     r8d, 4A666552h; Tag
0x1c00621ba  mov     ecx, edi; PoolType
0x1c00621bc  call    cs:__imp_ExAllocatePoolWithTag
0x1c00621c3  nop     dword ptr [rax+rax+00h]
0x1c00621c8  mov     r15, rax
0x1c00621cb  mov     [rsp+0A8h+var_48], rax
0x1c00621d0  mov     r8b, 1; SubAuthorityCount
0x1c00621d3  lea     rdx, [rsp+0A8h+IdentifierAuthority]; IdentifierAuthority
0x1c00621db  mov     rcx, rax; Sid
0x1c00621de  call    cs:__imp_RtlInitializeSid
0x1c00621e5  nop     dword ptr [rax+rax+00h]
0x1c00621ea  xor     edx, edx; SubAuthority
0x1c00621ec  mov     rcx, r15; Sid
0x1c00621ef  call    cs:__imp_RtlSubAuthoritySid
0x1c00621f6  nop     dword ptr [rax+rax+00h]
0x1c00621fb  mov     dword ptr [rax], 12h
0x1c0062201  movzx   r9d, byte ptr [r15+1]
0x1c0062206  movzx   edx, byte ptr [r14+1]
0x1c006220b  add     r9d, edx
0x1c006220e  lea     ebx, ds:38h[r9*4]
0x1c0062216  mov     edx, ebx; NumberOfBytes
0x1c0062218  mov     r8d, 4A666552h; Tag
0x1c006221e  mov     ecx, edi; PoolType
0x1c0062220  call    cs:__imp_ExAllocatePoolWithTag
0x1c0062227  nop     dword ptr [rax+rax+00h]
0x1c006222c  mov     rdi, rax
0x1c006222f  mov     [rsp+0A8h+var_58], rax
0x1c0062234  mov     r8d, 2; AclRevision
0x1c006223a  mov     edx, ebx; AclLength
0x1c006223c  mov     rcx, rax; Acl
0x1c006223f  call    cs:__imp_RtlCreateAcl
0x1c0062246  nop     dword ptr [rax+rax+00h]
0x1c006224b  mov     ebx, eax
0x1c006224d  mov     [rsp+0A8h+Status], eax
0x1c0062251  test    eax, eax
0x1c0062253  js      loc_1C0062354
0x1c0062259  mov     r9, r15; Sid
0x1c006225c  mov     edx, 2; AceRevision
0x1c0062261  mov     r8d, 10000000h; AccessMask
0x1c0062267  mov     rcx, rdi; Acl
0x1c006226a  call    cs:__imp_RtlAddAccessAllowedAce
0x1c0062271  nop     dword ptr [rax+rax+00h]
0x1c0062276  mov     ebx, eax
0x1c0062278  mov     [rsp+0A8h+Status], eax
0x1c006227c  test    eax, eax
0x1c006227e  js      loc_1C0062354
0x1c0062284  mov     r9, r14; Sid
0x1c0062287  mov     edx, 2; AceRevision
0x1c006228c  mov     r8d, 10000000h; AccessMask
0x1c0062292  mov     rcx, rdi; Acl
0x1c0062295  call    cs:__imp_RtlAddAccessAllowedAce
0x1c006229c  nop     dword ptr [rax+rax+00h]
0x1c00622a1  mov     ebx, eax
0x1c00622a3  mov     [rsp+0A8h+Status], eax
0x1c00622a7  test    eax, eax
0x1c00622a9  js      loc_1C0062354
0x1c00622af  mov     edx, 1; Revision
0x1c00622b4  lea     rcx, [rsp+0A8h+SecurityDescriptor]; SecurityDescriptor
0x1c00622b9  call    cs:__imp_RtlCreateSecurityDescriptor
0x1c00622c0  nop     dword ptr [rax+rax+00h]
0x1c00622c5  mov     ebx, eax
0x1c00622c7  mov     [rsp+0A8h+Status], eax
0x1c00622cb  test    eax, eax
0x1c00622cd  js      loc_1C0062354
0x1c00622d3  xor     r9d, r9d; DaclDefaulted
0x1c00622d6  mov     r8, rdi; Dacl
0x1c00622d9  mov     dl, 1; DaclPresent
0x1c00622db  lea     rcx, [rsp+0A8h+SecurityDescriptor]; SecurityDescriptor
0x1c00622e0  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x1c00622e7  nop     dword ptr [rax+rax+00h]
0x1c00622ec  mov     ebx, eax
0x1c00622ee  mov     [rsp+0A8h+Status], eax
0x1c00622f2  test    eax, eax
0x1c00622f4  js      short loc_1C0062354
0x1c00622f6  call    cs:__imp_IoGetFileObjectGenericMapping
0x1c00622fd  nop     dword ptr [rax+rax+00h]
0x1c0062302  mov     [rsp+0A8h+PoolType], 1; PoolType
0x1c006230a  mov     [rsp+0A8h+GenericMapping], rax; GenericMapping
0x1c006230f  mov     [rsp+0A8h+SubjectContext], rsi; SubjectContext
0x1c0062314  xor     r9d, r9d; IsDirectoryObject
0x1c0062317  lea     r8, NewDescriptor; NewDescriptor
0x1c006231e  lea     rdx, [rsp+0A8h+SecurityDescriptor]; ExplicitDescriptor
0x1c0062323  xor     ecx, ecx; ParentDescriptor
0x1c0062325  call    cs:__imp_SeAssignSecurity
0x1c006232c  nop     dword ptr [rax+rax+00h]
0x1c0062331  mov     ebx, eax
0x1c0062333  mov     [rsp+0A8h+Status], eax
0x1c0062337  test    eax, eax
0x1c0062339  js      short loc_1C0062354
0x1c006233b  mov     rcx, cs:NewDescriptor; SecurityDescriptor
0x1c0062342  call    cs:__imp_RtlLengthSecurityDescriptor
0x1c0062349  nop     dword ptr [rax+rax+00h]
0x1c006234e  mov     cs:Length, eax
0x1c0062354  mov     rcx, rsi; SubjectContext
0x1c0062357  call    cs:__imp_SeReleaseSubjectContext
0x1c006235e  nop     dword ptr [rax+rax+00h]
0x1c0062363  test    rsi, rsi
0x1c0062366  jz      short loc_1C0062379
0x1c0062368  xor     edx, edx; Tag
0x1c006236a  mov     rcx, rsi; P
0x1c006236d  call    cs:__imp_ExFreePoolWithTag
0x1c0062374  nop     dword ptr [rax+rax+00h]
0x1c0062379  test    rdi, rdi
0x1c006237c  jz      short loc_1C006238F
0x1c006237e  xor     edx, edx; Tag
0x1c0062380  mov     rcx, rdi; P
0x1c0062383  call    cs:__imp_ExFreePoolWithTag
0x1c006238a  nop     dword ptr [rax+rax+00h]
0x1c006238f  xor     edx, edx; Tag
0x1c0062391  mov     rcx, r14; P
0x1c0062394  call    cs:__imp_ExFreePoolWithTag
0x1c006239b  nop     dword ptr [rax+rax+00h]
0x1c00623a0  xor     edx, edx; Tag
0x1c00623a2  mov     rcx, r15; P
0x1c00623a5  call    cs:__imp_ExFreePoolWithTag
0x1c00623ac  nop     dword ptr [rax+rax+00h]
0x1c00623b1  test    ebx, ebx
0x1c00623b3  js      loc_1C008EAE0
0x1c00623b9  mov     rcx, [rsp+0A8h+var_10]
0x1c00623c1  xor     rcx, rsp; StackCookie
0x1c00623c4  call    __security_check_cookie
0x1c00623c9  lea     r11, [rsp+0A8h+var_8]
0x1c00623d1  mov     rbx, [r11+10h]
0x1c00623d5  mov     rsi, [r11+18h]
0x1c00623d9  mov     rdi, [r11+20h]
0x1c00623dd  mov     r14, [r11+28h]
0x1c00623e1  mov     rsp, r11
0x1c00623e4  pop     r15
0x1c00623e6  retn
0x1c006c465  push    rbp
0x1c006c467  sub     rsp, 40h
0x1c006c46b  mov     rbp, rdx
0x1c006c46e  cmp     byte ptr [rbp+40h], 0
0x1c006c472  jz      short loc_1C006C485
0x1c006c474  mov     rcx, [rbp+48h]; SubjectContext
0x1c006c478  call    cs:__imp_SeReleaseSubjectContext
0x1c006c47f  nop     dword ptr [rax+rax+00h]
0x1c006c484  nop
0x1c006c485  mov     rcx, [rbp+48h]; P
0x1c006c489  test    rcx, rcx
0x1c006c48c  jz      short loc_1C006C49D
0x1c006c48e  xor     edx, edx; Tag
0x1c006c490  call    cs:__imp_ExFreePoolWithTag
0x1c006c497  nop     dword ptr [rax+rax+00h]
0x1c006c49c  nop
0x1c006c49d  mov     rcx, [rbp+50h]; P
0x1c006c4a1  test    rcx, rcx
0x1c006c4a4  jz      short loc_1C006C4B5
0x1c006c4a6  xor     edx, edx; Tag
0x1c006c4a8  call    cs:__imp_ExFreePoolWithTag
0x1c006c4af  nop     dword ptr [rax+rax+00h]
0x1c006c4b4  nop
0x1c006c4b5  mov     rcx, [rbp+58h]; P
0x1c006c4b9  test    rcx, rcx
0x1c006c4bc  jz      short loc_1C006C4CD
0x1c006c4be  xor     edx, edx; Tag
0x1c006c4c0  call    cs:__imp_ExFreePoolWithTag
0x1c006c4c7  nop     dword ptr [rax+rax+00h]
0x1c006c4cc  nop
0x1c006c4cd  mov     rcx, [rbp+60h]; P
0x1c006c4d1  test    rcx, rcx
0x1c006c4d4  jz      short loc_1C006C4E5
0x1c006c4d6  xor     edx, edx; Tag
0x1c006c4d8  call    cs:__imp_ExFreePoolWithTag
0x1c006c4df  nop     dword ptr [rax+rax+00h]
0x1c006c4e4  nop
0x1c006c4e5  add     rsp, 40h
0x1c006c4e9  pop     rbp
0x1c006c4ea  retn
0x1c008eae0  lea     rax, WPP_GLOBAL_Control
0x1c008eae7  mov     rcx, cs:WPP_GLOBAL_Control
0x1c008eaee  cmp     rcx, rax
0x1c008eaf1  jz      short loc_1C008EB1A
0x1c008eaf3  test    dword ptr [rcx+2Ch], 100h
0x1c008eafa  jz      short loc_1C008EB1A
0x1c008eafc  cmp     byte ptr [rcx+29h], 4
0x1c008eb00  jb      short loc_1C008EB1A
0x1c008eb02  mov     edx, 12h
0x1c008eb07  mov     r9d, ebx
0x1c008eb0a  lea     r8, WPP_2bcc4d02ea773ee5fd3d1fc8b1a95a7b_Traceguids
0x1c008eb11  mov     rcx, [rcx+18h]
0x1c008eb15  call    WPP_SF_D
0x1c008eb1a  mov     al, cs:RefsStatusDebugEnabled
0x1c008eb20  test    al, al
0x1c008eb22  jz      short loc_1C008EB3A
0x1c008eb24  mov     r8d, 177Fh
0x1c008eb2a  lea     rdx, aNtfsinitC; "NtfsInit.c"
0x1c008eb31  mov     ecx, [rsp+0A8h+Status]; Status
0x1c008eb35  call    RefsStatusDebug
0x1c008eb3a  mov     ecx, [rsp+0A8h+Status]; Status
0x1c008eb3e  call    cs:__imp_ExRaiseStatus
```
