# InitializeDefaultSecurityDescriptor(void)

- ea: `0x1400b52c0`
- end: `0x1400b567d`
- name: `?InitializeDefaultSecurityDescriptor@@YAXXZ`
- size: `957`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14034c36c`

## callees

- `0x14008dbd0`
- `0x1400b52c0`
- `0x1400ca788`
- `0x1401e9ce0`

## import_xrefs

- `ntoskrnl!ExRaiseStatus` at `0x1400b5650`
- `ntoskrnl!ExRaiseStatus` at `0x1400b5650`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1400b5353`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1400b5353`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1400b5596`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1401ebc2e`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1400b5596`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1401ebc2e`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1400b5539`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1400b5539`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1400b5367`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1400b53dd`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1400b5367`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1400b53dd`
- `ntoskrnl!RtlInitializeSid` at `0x1400b53a3`
- `ntoskrnl!RtlInitializeSid` at `0x1400b5419`
- `ntoskrnl!RtlInitializeSid` at `0x1400b53a3`
- `ntoskrnl!RtlInitializeSid` at `0x1400b5419`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400b53b4`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400b53c8`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400b542a`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400b53b4`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400b53c8`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400b542a`
- `ntoskrnl!RtlCreateAcl` at `0x1400b547c`
- `ntoskrnl!RtlCreateAcl` at `0x1400b547c`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1400b54a7`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1400b54d2`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1400b54a7`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1400b54d2`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1400b54f6`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1400b54f6`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1400b551d`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1400b551d`
- `ntoskrnl!SeAssignSecurity` at `0x1400b5564`
- `ntoskrnl!SeAssignSecurity` at `0x1400b5564`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x1400b5581`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x1400b5581`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b55ac`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b55c2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b55d3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b55e4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401ebc46`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401ebc5e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401ebc76`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401ebc8e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b55ac`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b55c2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b55d3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b55e4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401ebc46`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401ebc5e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401ebc76`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401ebc8e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400b533c`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400b5381`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400b53f7`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400b545d`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400b533c`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400b5381`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400b53f7`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400b545d`

## pseudocode

```c
void InitializeDefaultSecurityDescriptor(void)
{
  struct _SECURITY_SUBJECT_CONTEXT *SubjectContext; // rsi
  ULONG v1; // eax
  unsigned __int8 *PoolWithTag; // r14
  ULONG v3; // eax
  unsigned __int8 *v4; // r15
  ULONG v5; // ebx
  struct _ACL *v6; // rdi
  int Acl; // ebx
  POOL_TYPE PoolType; // ebx
  struct _GENERIC_MAPPING *GenericMapping; // rax
  _OWORD SecurityDescriptor[2]; // [rsp+68h] [rbp-60h] BYREF
  __int64 v11; // [rsp+88h] [rbp-40h]
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+90h] [rbp-38h] BYREF

  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  v11 = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  SubjectContext = (struct _SECURITY_SUBJECT_CONTEXT *)ExAllocatePoolWithTag(
                                                         (POOL_TYPE)(::PoolType | 0x10),
                                                         0x20u,
                                                         0x4A666552u);
  SeCaptureSubjectContext(SubjectContext);
  v1 = RtlLengthRequiredSid(2u);
  PoolWithTag = (unsigned __int8 *)ExAllocatePoolWithTag((POOL_TYPE)(::PoolType | 0x10), v1, 0x4A666552u);
  RtlInitializeSid(PoolWithTag, &IdentifierAuthority, 2u);
  *RtlSubAuthoritySid(PoolWithTag, 0) = 32;
  *RtlSubAuthoritySid(PoolWithTag, 1u) = 544;
  v3 = RtlLengthRequiredSid(1u);
  v4 = (unsigned __int8 *)ExAllocatePoolWithTag((POOL_TYPE)(::PoolType | 0x10), v3, 0x4A666552u);
  RtlInitializeSid(v4, &IdentifierAuthority, 1u);
  *RtlSubAuthoritySid(v4, 0) = 18;
  v5 = 4 * (PoolWithTag[1] + v4[1]) + 56;
  v6 = (struct _ACL *)ExAllocatePoolWithTag((POOL_TYPE)(::PoolType | 0x10), v5, 0x4A666552u);
  Acl = RtlCreateAcl(v6, v5, 2u);
  if ( Acl >= 0 )
  {
    Acl = RtlAddAccessAllowedAce(v6, 2u, 0x10000000u, v4);
    if ( Acl >= 0 )
    {
      Acl = RtlAddAccessAllowedAce(v6, 2u, 0x10000000u, PoolWithTag);
      if ( Acl >= 0 )
      {
        Acl = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
        if ( Acl >= 0 )
        {
          Acl = RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, v6, 0);
          if ( Acl >= 0 )
          {
            PoolType = ::PoolType;
            GenericMapping = IoGetFileObjectGenericMapping();
            Acl = SeAssignSecurity(
                    0,
                    SecurityDescriptor,
                    &::SecurityDescriptor,
                    0,
                    SubjectContext,
                    GenericMapping,
                    PoolType);
            if ( Acl >= 0 )
              Length = RtlLengthSecurityDescriptor(::SecurityDescriptor);
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
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        21,
        WPP_bee596de7a9331ebd70d5dc28c9a6eb9_Traceguids,
        (unsigned int)Acl);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
      RefsStatusDebug(Acl, 0, "NtfsInit.c", 0x17DEu);
    ExRaiseStatus(Acl);
  }
}

```

## disassembly

```asm
0x1400b52c0  mov     r11, rsp
0x1400b52c3  push    rbx
0x1400b52c4  push    rsi
0x1400b52c5  push    rdi
0x1400b52c6  push    r14
0x1400b52c8  push    r15
0x1400b52ca  sub     rsp, 0A0h
0x1400b52d1  mov     rax, cs:__security_cookie
0x1400b52d8  xor     rax, rsp
0x1400b52db  mov     [rsp+0C8h+var_30], rax
0x1400b52e3  mov     qword ptr [r11-80h], 0
0x1400b52eb  mov     [rsp+0C8h+var_88], 0
0x1400b52f0  mov     qword ptr [r11-78h], 0
0x1400b52f8  mov     qword ptr [r11-70h], 0
0x1400b5300  mov     qword ptr [r11-68h], 0
0x1400b5308  xorps   xmm0, xmm0
0x1400b530b  xor     eax, eax
0x1400b530d  movups  [rsp+0C8h+SecurityDescriptor], xmm0
0x1400b5312  movups  [rsp+0C8h+var_50], xmm0
0x1400b5317  mov     [r11-40h], rax
0x1400b531b  mov     [r11-38h], eax
0x1400b531f  mov     word ptr [r11-34h], 500h
0x1400b5326  mov     ecx, cs:PoolType
0x1400b532c  or      ecx, 10h; PoolType
0x1400b532f  mov     edi, 4A666552h
0x1400b5334  mov     r8d, edi; Tag
0x1400b5337  lea     ebx, [rax+20h]
0x1400b533a  mov     edx, ebx; NumberOfBytes
0x1400b533c  call    cs:__imp_ExAllocatePoolWithTag
0x1400b5343  nop     dword ptr [rax+rax+00h]
0x1400b5348  mov     rsi, rax
0x1400b534b  mov     [rsp+0C8h+var_80], rax
0x1400b5350  mov     rcx, rax; SubjectContext
0x1400b5353  call    cs:__imp_SeCaptureSubjectContext
0x1400b535a  nop     dword ptr [rax+rax+00h]
0x1400b535f  mov     [rsp+0C8h+var_88], 1
0x1400b5364  lea     ecx, [rbx-1Eh]; SubAuthorityCount
0x1400b5367  call    cs:__imp_RtlLengthRequiredSid
0x1400b536e  nop     dword ptr [rax+rax+00h]
0x1400b5373  mov     edx, eax; NumberOfBytes
0x1400b5375  mov     ecx, cs:PoolType
0x1400b537b  or      ecx, 10h; PoolType
0x1400b537e  mov     r8d, edi; Tag
0x1400b5381  call    cs:__imp_ExAllocatePoolWithTag
0x1400b5388  nop     dword ptr [rax+rax+00h]
0x1400b538d  mov     r14, rax
0x1400b5390  mov     [rsp+0C8h+var_70], rax
0x1400b5395  mov     r8b, 2; SubAuthorityCount
0x1400b5398  lea     rdx, [rsp+0C8h+IdentifierAuthority]; IdentifierAuthority
0x1400b53a0  mov     rcx, rax; Sid
0x1400b53a3  call    cs:__imp_RtlInitializeSid
0x1400b53aa  nop     dword ptr [rax+rax+00h]
0x1400b53af  xor     edx, edx; SubAuthority
0x1400b53b1  mov     rcx, r14; Sid
0x1400b53b4  call    cs:__imp_RtlSubAuthoritySid
0x1400b53bb  nop     dword ptr [rax+rax+00h]
0x1400b53c0  mov     [rax], ebx
0x1400b53c2  lea     edx, [rbx-1Fh]; SubAuthority
0x1400b53c5  mov     rcx, r14; Sid
0x1400b53c8  call    cs:__imp_RtlSubAuthoritySid
0x1400b53cf  nop     dword ptr [rax+rax+00h]
0x1400b53d4  mov     dword ptr [rax], 220h
0x1400b53da  lea     ecx, [rbx-1Fh]; SubAuthorityCount
0x1400b53dd  call    cs:__imp_RtlLengthRequiredSid
0x1400b53e4  nop     dword ptr [rax+rax+00h]
0x1400b53e9  mov     edx, eax; NumberOfBytes
0x1400b53eb  mov     ecx, cs:PoolType
0x1400b53f1  or      ecx, 10h; PoolType
0x1400b53f4  mov     r8d, edi; Tag
0x1400b53f7  call    cs:__imp_ExAllocatePoolWithTag
0x1400b53fe  nop     dword ptr [rax+rax+00h]
0x1400b5403  mov     r15, rax
0x1400b5406  mov     [rsp+0C8h+var_68], rax
0x1400b540b  mov     r8b, 1; SubAuthorityCount
0x1400b540e  lea     rdx, [rsp+0C8h+IdentifierAuthority]; IdentifierAuthority
0x1400b5416  mov     rcx, rax; Sid
0x1400b5419  call    cs:__imp_RtlInitializeSid
0x1400b5420  nop     dword ptr [rax+rax+00h]
0x1400b5425  xor     edx, edx; SubAuthority
0x1400b5427  mov     rcx, r15; Sid
0x1400b542a  call    cs:__imp_RtlSubAuthoritySid
0x1400b5431  nop     dword ptr [rax+rax+00h]
0x1400b5436  mov     dword ptr [rax], 12h
0x1400b543c  movzx   edx, byte ptr [r15+1]
0x1400b5441  movzx   ecx, byte ptr [r14+1]
0x1400b5446  add     edx, ecx
0x1400b5448  lea     ebx, ds:38h[rdx*4]
0x1400b544f  mov     edx, ebx; NumberOfBytes
0x1400b5451  mov     ecx, cs:PoolType
0x1400b5457  or      ecx, 10h; PoolType
0x1400b545a  mov     r8d, edi; Tag
0x1400b545d  call    cs:__imp_ExAllocatePoolWithTag
0x1400b5464  nop     dword ptr [rax+rax+00h]
0x1400b5469  mov     rdi, rax
0x1400b546c  mov     [rsp+0C8h+var_78], rax
0x1400b5471  mov     r8d, 2; AclRevision
0x1400b5477  mov     edx, ebx; AclLength
0x1400b5479  mov     rcx, rax; Acl
0x1400b547c  call    cs:__imp_RtlCreateAcl
0x1400b5483  nop     dword ptr [rax+rax+00h]
0x1400b5488  mov     ebx, eax
0x1400b548a  mov     [rsp+0C8h+var_84], eax
0x1400b548e  test    eax, eax
0x1400b5490  js      loc_1400B5593
0x1400b5496  mov     r9, r15; Sid
0x1400b5499  mov     edx, 2; AceRevision
0x1400b549e  mov     r8d, 10000000h; AccessMask
0x1400b54a4  mov     rcx, rdi; Acl
0x1400b54a7  call    cs:__imp_RtlAddAccessAllowedAce
0x1400b54ae  nop     dword ptr [rax+rax+00h]
0x1400b54b3  mov     ebx, eax
0x1400b54b5  mov     [rsp+0C8h+var_84], eax
0x1400b54b9  test    eax, eax
0x1400b54bb  js      loc_1400B5593
0x1400b54c1  mov     r9, r14; Sid
0x1400b54c4  mov     edx, 2; AceRevision
0x1400b54c9  mov     r8d, 10000000h; AccessMask
0x1400b54cf  mov     rcx, rdi; Acl
0x1400b54d2  call    cs:__imp_RtlAddAccessAllowedAce
0x1400b54d9  nop     dword ptr [rax+rax+00h]
0x1400b54de  mov     ebx, eax
0x1400b54e0  mov     [rsp+0C8h+var_84], eax
0x1400b54e4  test    eax, eax
0x1400b54e6  js      loc_1400B5593
0x1400b54ec  mov     edx, 1; Revision
0x1400b54f1  lea     rcx, [rsp+0C8h+SecurityDescriptor]; SecurityDescriptor
0x1400b54f6  call    cs:__imp_RtlCreateSecurityDescriptor
0x1400b54fd  nop     dword ptr [rax+rax+00h]
0x1400b5502  mov     ebx, eax
0x1400b5504  mov     [rsp+0C8h+var_84], eax
0x1400b5508  test    eax, eax
0x1400b550a  js      loc_1400B5593
0x1400b5510  xor     r9d, r9d; DaclDefaulted
0x1400b5513  mov     r8, rdi; Dacl
0x1400b5516  mov     dl, 1; DaclPresent
0x1400b5518  lea     rcx, [rsp+0C8h+SecurityDescriptor]; SecurityDescriptor
0x1400b551d  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x1400b5524  nop     dword ptr [rax+rax+00h]
0x1400b5529  mov     ebx, eax
0x1400b552b  mov     [rsp+0C8h+var_84], eax
0x1400b552f  test    eax, eax
0x1400b5531  js      short loc_1400B5593
0x1400b5533  mov     ebx, cs:PoolType
0x1400b5539  call    cs:__imp_IoGetFileObjectGenericMapping
0x1400b5540  nop     dword ptr [rax+rax+00h]
0x1400b5545  mov     [rsp+0C8h+PoolType], ebx; PoolType
0x1400b5549  mov     [rsp+0C8h+GenericMapping], rax; GenericMapping
0x1400b554e  mov     [rsp+0C8h+SubjectContext], rsi; SubjectContext
0x1400b5553  xor     r9d, r9d; IsDirectoryObject
0x1400b5556  lea     r8, SecurityDescriptor; NewDescriptor
0x1400b555d  lea     rdx, [rsp+0C8h+SecurityDescriptor]; ExplicitDescriptor
0x1400b5562  xor     ecx, ecx; ParentDescriptor
0x1400b5564  call    cs:__imp_SeAssignSecurity
0x1400b556b  nop     dword ptr [rax+rax+00h]
0x1400b5570  mov     ebx, eax
0x1400b5572  mov     [rsp+0C8h+var_84], eax
0x1400b5576  test    eax, eax
0x1400b5578  js      short loc_1400B5593
0x1400b557a  mov     rcx, cs:SecurityDescriptor; SecurityDescriptor
0x1400b5581  call    cs:__imp_RtlLengthSecurityDescriptor
0x1400b5588  nop     dword ptr [rax+rax+00h]
0x1400b558d  mov     cs:Length, eax
0x1400b5593  mov     rcx, rsi; SubjectContext
0x1400b5596  call    cs:__imp_SeReleaseSubjectContext
0x1400b559d  nop     dword ptr [rax+rax+00h]
0x1400b55a2  test    rsi, rsi
0x1400b55a5  jz      short loc_1400B55B8
0x1400b55a7  xor     edx, edx; Tag
0x1400b55a9  mov     rcx, rsi; P
0x1400b55ac  call    cs:__imp_ExFreePoolWithTag
0x1400b55b3  nop     dword ptr [rax+rax+00h]
0x1400b55b8  test    rdi, rdi
0x1400b55bb  jz      short loc_1400B55CE
0x1400b55bd  xor     edx, edx; Tag
0x1400b55bf  mov     rcx, rdi; P
0x1400b55c2  call    cs:__imp_ExFreePoolWithTag
0x1400b55c9  nop     dword ptr [rax+rax+00h]
0x1400b55ce  xor     edx, edx; Tag
0x1400b55d0  mov     rcx, r14; P
0x1400b55d3  call    cs:__imp_ExFreePoolWithTag
0x1400b55da  nop     dword ptr [rax+rax+00h]
0x1400b55df  xor     edx, edx; Tag
0x1400b55e1  mov     rcx, r15; P
0x1400b55e4  call    cs:__imp_ExFreePoolWithTag
0x1400b55eb  nop     dword ptr [rax+rax+00h]
0x1400b55f0  test    ebx, ebx
0x1400b55f2  jns     short loc_1400B565D
0x1400b55f4  lea     rax, WPP_GLOBAL_Control
0x1400b55fb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b5602  cmp     rcx, rax
0x1400b5605  jz      short loc_1400B562E
0x1400b5607  test    dword ptr [rcx+2Ch], 100h
0x1400b560e  jz      short loc_1400B562E
0x1400b5610  cmp     byte ptr [rcx+29h], 4
0x1400b5614  jb      short loc_1400B562E
0x1400b5616  mov     edx, 15h
0x1400b561b  mov     r9d, ebx
0x1400b561e  lea     r8, WPP_bee596de7a9331ebd70d5dc28c9a6eb9_Traceguids
0x1400b5625  mov     rcx, [rcx+18h]
0x1400b5629  call    WPP_SF_d
0x1400b562e  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1400b5634  test    al, al
0x1400b5636  jz      short loc_1400B564E
0x1400b5638  mov     r9d, 17DEh; unsigned int
0x1400b563e  lea     r8, aNtfsinitC; "NtfsInit.c"
0x1400b5645  xor     edx, edx; struct _IRP_CONTEXT *
0x1400b5647  mov     ecx, ebx; Status
0x1400b5649  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x1400b564e  mov     ecx, ebx; Status
0x1400b5650  call    cs:__imp_ExRaiseStatus
0x1400b565d  mov     rcx, [rsp+0C8h+var_30]
0x1400b5665  xor     rcx, rsp; StackCookie
0x1400b5668  call    __security_check_cookie
0x1400b566d  add     rsp, 0A0h
0x1400b5674  pop     r15
0x1400b5676  pop     r14
0x1400b5678  pop     rdi
0x1400b5679  pop     rsi
0x1400b567a  pop     rbx
0x1400b567b  retn
0x1401ebc1b  push    rbp
0x1401ebc1d  sub     rsp, 40h
0x1401ebc21  mov     rbp, rdx
0x1401ebc24  cmp     byte ptr [rbp+40h], 0
0x1401ebc28  jz      short loc_1401EBC3B
0x1401ebc2a  mov     rcx, [rbp+48h]; SubjectContext
0x1401ebc2e  call    cs:__imp_SeReleaseSubjectContext
0x1401ebc35  nop     dword ptr [rax+rax+00h]
0x1401ebc3a  nop
0x1401ebc3b  mov     rcx, [rbp+48h]; P
0x1401ebc3f  test    rcx, rcx
0x1401ebc42  jz      short loc_1401EBC53
0x1401ebc44  xor     edx, edx; Tag
0x1401ebc46  call    cs:__imp_ExFreePoolWithTag
0x1401ebc4d  nop     dword ptr [rax+rax+00h]
0x1401ebc52  nop
0x1401ebc53  mov     rcx, [rbp+50h]; P
0x1401ebc57  test    rcx, rcx
0x1401ebc5a  jz      short loc_1401EBC6B
0x1401ebc5c  xor     edx, edx; Tag
0x1401ebc5e  call    cs:__imp_ExFreePoolWithTag
0x1401ebc65  nop     dword ptr [rax+rax+00h]
0x1401ebc6a  nop
0x1401ebc6b  mov     rcx, [rbp+58h]; P
0x1401ebc6f  test    rcx, rcx
0x1401ebc72  jz      short loc_1401EBC83
0x1401ebc74  xor     edx, edx; Tag
0x1401ebc76  call    cs:__imp_ExFreePoolWithTag
0x1401ebc7d  nop     dword ptr [rax+rax+00h]
0x1401ebc82  nop
0x1401ebc83  mov     rcx, [rbp+60h]; P
0x1401ebc87  test    rcx, rcx
0x1401ebc8a  jz      short loc_1401EBC9B
0x1401ebc8c  xor     edx, edx; Tag
0x1401ebc8e  call    cs:__imp_ExFreePoolWithTag
0x1401ebc95  nop     dword ptr [rax+rax+00h]
0x1401ebc9a  nop
0x1401ebc9b  add     rsp, 40h
0x1401ebc9f  pop     rbp
0x1401ebca0  retn
```
