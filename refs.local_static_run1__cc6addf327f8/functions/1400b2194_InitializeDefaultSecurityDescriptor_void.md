# InitializeDefaultSecurityDescriptor(void)

- ea: `0x1400b2194`
- end: `0x1400b2551`
- name: `?InitializeDefaultSecurityDescriptor@@YAXXZ`
- size: `957`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14034f36c`

## callees

- `0x1400862c0`
- `0x1400b2194`
- `0x1400d0fd8`
- `0x1401f3fb0`

## import_xrefs

- `ntoskrnl!ExRaiseStatus` at `0x1400b2524`
- `ntoskrnl!ExRaiseStatus` at `0x1400b2524`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1400b2227`
- `ntoskrnl!SeCaptureSubjectContext` at `0x1400b2227`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1400b246a`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1401f5d82`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1400b246a`
- `ntoskrnl!SeReleaseSubjectContext` at `0x1401f5d82`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1400b240d`
- `ntoskrnl!IoGetFileObjectGenericMapping` at `0x1400b240d`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1400b223b`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1400b22b1`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1400b223b`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1400b22b1`
- `ntoskrnl!RtlInitializeSid` at `0x1400b2277`
- `ntoskrnl!RtlInitializeSid` at `0x1400b22ed`
- `ntoskrnl!RtlInitializeSid` at `0x1400b2277`
- `ntoskrnl!RtlInitializeSid` at `0x1400b22ed`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400b2288`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400b229c`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400b22fe`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400b2288`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400b229c`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400b22fe`
- `ntoskrnl!RtlCreateAcl` at `0x1400b2350`
- `ntoskrnl!RtlCreateAcl` at `0x1400b2350`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1400b237b`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1400b23a6`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1400b237b`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1400b23a6`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1400b23ca`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1400b23ca`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1400b23f1`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1400b23f1`
- `ntoskrnl!SeAssignSecurity` at `0x1400b2438`
- `ntoskrnl!SeAssignSecurity` at `0x1400b2438`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x1400b2455`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x1400b2455`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b2480`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b2496`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b24a7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b24b8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401f5d9a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401f5db2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401f5dca`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401f5de2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b2480`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b2496`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b24a7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b24b8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401f5d9a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401f5db2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401f5dca`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401f5de2`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400b2210`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400b2255`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400b22cb`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400b2331`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400b2210`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400b2255`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400b22cb`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400b2331`

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
        WPP_823e6dba7932309d1ad2e841189c99ac_Traceguids,
        (unsigned int)Acl);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
      RefsStatusDebug(Acl, 0, "NtfsInit.c", 0x1766u);
    ExRaiseStatus(Acl);
  }
}

```

## disassembly

```asm
0x1400b2194  mov     r11, rsp
0x1400b2197  push    rbx
0x1400b2198  push    rsi
0x1400b2199  push    rdi
0x1400b219a  push    r14
0x1400b219c  push    r15
0x1400b219e  sub     rsp, 0A0h
0x1400b21a5  mov     rax, cs:__security_cookie
0x1400b21ac  xor     rax, rsp
0x1400b21af  mov     [rsp+0C8h+var_30], rax
0x1400b21b7  mov     qword ptr [r11-80h], 0
0x1400b21bf  mov     [rsp+0C8h+var_88], 0
0x1400b21c4  mov     qword ptr [r11-78h], 0
0x1400b21cc  mov     qword ptr [r11-70h], 0
0x1400b21d4  mov     qword ptr [r11-68h], 0
0x1400b21dc  xorps   xmm0, xmm0
0x1400b21df  xor     eax, eax
0x1400b21e1  movups  [rsp+0C8h+SecurityDescriptor], xmm0
0x1400b21e6  movups  [rsp+0C8h+var_50], xmm0
0x1400b21eb  mov     [r11-40h], rax
0x1400b21ef  mov     [r11-38h], eax
0x1400b21f3  mov     word ptr [r11-34h], 500h
0x1400b21fa  mov     ecx, cs:PoolType
0x1400b2200  or      ecx, 10h; PoolType
0x1400b2203  mov     edi, 4A666552h
0x1400b2208  mov     r8d, edi; Tag
0x1400b220b  lea     ebx, [rax+20h]
0x1400b220e  mov     edx, ebx; NumberOfBytes
0x1400b2210  call    cs:__imp_ExAllocatePoolWithTag
0x1400b2217  nop     dword ptr [rax+rax+00h]
0x1400b221c  mov     rsi, rax
0x1400b221f  mov     [rsp+0C8h+var_80], rax
0x1400b2224  mov     rcx, rax; SubjectContext
0x1400b2227  call    cs:__imp_SeCaptureSubjectContext
0x1400b222e  nop     dword ptr [rax+rax+00h]
0x1400b2233  mov     [rsp+0C8h+var_88], 1
0x1400b2238  lea     ecx, [rbx-1Eh]; SubAuthorityCount
0x1400b223b  call    cs:__imp_RtlLengthRequiredSid
0x1400b2242  nop     dword ptr [rax+rax+00h]
0x1400b2247  mov     edx, eax; NumberOfBytes
0x1400b2249  mov     ecx, cs:PoolType
0x1400b224f  or      ecx, 10h; PoolType
0x1400b2252  mov     r8d, edi; Tag
0x1400b2255  call    cs:__imp_ExAllocatePoolWithTag
0x1400b225c  nop     dword ptr [rax+rax+00h]
0x1400b2261  mov     r14, rax
0x1400b2264  mov     [rsp+0C8h+var_70], rax
0x1400b2269  mov     r8b, 2; SubAuthorityCount
0x1400b226c  lea     rdx, [rsp+0C8h+IdentifierAuthority]; IdentifierAuthority
0x1400b2274  mov     rcx, rax; Sid
0x1400b2277  call    cs:__imp_RtlInitializeSid
0x1400b227e  nop     dword ptr [rax+rax+00h]
0x1400b2283  xor     edx, edx; SubAuthority
0x1400b2285  mov     rcx, r14; Sid
0x1400b2288  call    cs:__imp_RtlSubAuthoritySid
0x1400b228f  nop     dword ptr [rax+rax+00h]
0x1400b2294  mov     [rax], ebx
0x1400b2296  lea     edx, [rbx-1Fh]; SubAuthority
0x1400b2299  mov     rcx, r14; Sid
0x1400b229c  call    cs:__imp_RtlSubAuthoritySid
0x1400b22a3  nop     dword ptr [rax+rax+00h]
0x1400b22a8  mov     dword ptr [rax], 220h
0x1400b22ae  lea     ecx, [rbx-1Fh]; SubAuthorityCount
0x1400b22b1  call    cs:__imp_RtlLengthRequiredSid
0x1400b22b8  nop     dword ptr [rax+rax+00h]
0x1400b22bd  mov     edx, eax; NumberOfBytes
0x1400b22bf  mov     ecx, cs:PoolType
0x1400b22c5  or      ecx, 10h; PoolType
0x1400b22c8  mov     r8d, edi; Tag
0x1400b22cb  call    cs:__imp_ExAllocatePoolWithTag
0x1400b22d2  nop     dword ptr [rax+rax+00h]
0x1400b22d7  mov     r15, rax
0x1400b22da  mov     [rsp+0C8h+var_68], rax
0x1400b22df  mov     r8b, 1; SubAuthorityCount
0x1400b22e2  lea     rdx, [rsp+0C8h+IdentifierAuthority]; IdentifierAuthority
0x1400b22ea  mov     rcx, rax; Sid
0x1400b22ed  call    cs:__imp_RtlInitializeSid
0x1400b22f4  nop     dword ptr [rax+rax+00h]
0x1400b22f9  xor     edx, edx; SubAuthority
0x1400b22fb  mov     rcx, r15; Sid
0x1400b22fe  call    cs:__imp_RtlSubAuthoritySid
0x1400b2305  nop     dword ptr [rax+rax+00h]
0x1400b230a  mov     dword ptr [rax], 12h
0x1400b2310  movzx   edx, byte ptr [r15+1]
0x1400b2315  movzx   ecx, byte ptr [r14+1]
0x1400b231a  add     edx, ecx
0x1400b231c  lea     ebx, ds:38h[rdx*4]
0x1400b2323  mov     edx, ebx; NumberOfBytes
0x1400b2325  mov     ecx, cs:PoolType
0x1400b232b  or      ecx, 10h; PoolType
0x1400b232e  mov     r8d, edi; Tag
0x1400b2331  call    cs:__imp_ExAllocatePoolWithTag
0x1400b2338  nop     dword ptr [rax+rax+00h]
0x1400b233d  mov     rdi, rax
0x1400b2340  mov     [rsp+0C8h+var_78], rax
0x1400b2345  mov     r8d, 2; AclRevision
0x1400b234b  mov     edx, ebx; AclLength
0x1400b234d  mov     rcx, rax; Acl
0x1400b2350  call    cs:__imp_RtlCreateAcl
0x1400b2357  nop     dword ptr [rax+rax+00h]
0x1400b235c  mov     ebx, eax
0x1400b235e  mov     [rsp+0C8h+var_84], eax
0x1400b2362  test    eax, eax
0x1400b2364  js      loc_1400B2467
0x1400b236a  mov     r9, r15; Sid
0x1400b236d  mov     edx, 2; AceRevision
0x1400b2372  mov     r8d, 10000000h; AccessMask
0x1400b2378  mov     rcx, rdi; Acl
0x1400b237b  call    cs:__imp_RtlAddAccessAllowedAce
0x1400b2382  nop     dword ptr [rax+rax+00h]
0x1400b2387  mov     ebx, eax
0x1400b2389  mov     [rsp+0C8h+var_84], eax
0x1400b238d  test    eax, eax
0x1400b238f  js      loc_1400B2467
0x1400b2395  mov     r9, r14; Sid
0x1400b2398  mov     edx, 2; AceRevision
0x1400b239d  mov     r8d, 10000000h; AccessMask
0x1400b23a3  mov     rcx, rdi; Acl
0x1400b23a6  call    cs:__imp_RtlAddAccessAllowedAce
0x1400b23ad  nop     dword ptr [rax+rax+00h]
0x1400b23b2  mov     ebx, eax
0x1400b23b4  mov     [rsp+0C8h+var_84], eax
0x1400b23b8  test    eax, eax
0x1400b23ba  js      loc_1400B2467
0x1400b23c0  mov     edx, 1; Revision
0x1400b23c5  lea     rcx, [rsp+0C8h+SecurityDescriptor]; SecurityDescriptor
0x1400b23ca  call    cs:__imp_RtlCreateSecurityDescriptor
0x1400b23d1  nop     dword ptr [rax+rax+00h]
0x1400b23d6  mov     ebx, eax
0x1400b23d8  mov     [rsp+0C8h+var_84], eax
0x1400b23dc  test    eax, eax
0x1400b23de  js      loc_1400B2467
0x1400b23e4  xor     r9d, r9d; DaclDefaulted
0x1400b23e7  mov     r8, rdi; Dacl
0x1400b23ea  mov     dl, 1; DaclPresent
0x1400b23ec  lea     rcx, [rsp+0C8h+SecurityDescriptor]; SecurityDescriptor
0x1400b23f1  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x1400b23f8  nop     dword ptr [rax+rax+00h]
0x1400b23fd  mov     ebx, eax
0x1400b23ff  mov     [rsp+0C8h+var_84], eax
0x1400b2403  test    eax, eax
0x1400b2405  js      short loc_1400B2467
0x1400b2407  mov     ebx, cs:PoolType
0x1400b240d  call    cs:__imp_IoGetFileObjectGenericMapping
0x1400b2414  nop     dword ptr [rax+rax+00h]
0x1400b2419  mov     [rsp+0C8h+PoolType], ebx; PoolType
0x1400b241d  mov     [rsp+0C8h+GenericMapping], rax; GenericMapping
0x1400b2422  mov     [rsp+0C8h+SubjectContext], rsi; SubjectContext
0x1400b2427  xor     r9d, r9d; IsDirectoryObject
0x1400b242a  lea     r8, SecurityDescriptor; NewDescriptor
0x1400b2431  lea     rdx, [rsp+0C8h+SecurityDescriptor]; ExplicitDescriptor
0x1400b2436  xor     ecx, ecx; ParentDescriptor
0x1400b2438  call    cs:__imp_SeAssignSecurity
0x1400b243f  nop     dword ptr [rax+rax+00h]
0x1400b2444  mov     ebx, eax
0x1400b2446  mov     [rsp+0C8h+var_84], eax
0x1400b244a  test    eax, eax
0x1400b244c  js      short loc_1400B2467
0x1400b244e  mov     rcx, cs:SecurityDescriptor; SecurityDescriptor
0x1400b2455  call    cs:__imp_RtlLengthSecurityDescriptor
0x1400b245c  nop     dword ptr [rax+rax+00h]
0x1400b2461  mov     cs:Length, eax
0x1400b2467  mov     rcx, rsi; SubjectContext
0x1400b246a  call    cs:__imp_SeReleaseSubjectContext
0x1400b2471  nop     dword ptr [rax+rax+00h]
0x1400b2476  test    rsi, rsi
0x1400b2479  jz      short loc_1400B248C
0x1400b247b  xor     edx, edx; Tag
0x1400b247d  mov     rcx, rsi; P
0x1400b2480  call    cs:__imp_ExFreePoolWithTag
0x1400b2487  nop     dword ptr [rax+rax+00h]
0x1400b248c  test    rdi, rdi
0x1400b248f  jz      short loc_1400B24A2
0x1400b2491  xor     edx, edx; Tag
0x1400b2493  mov     rcx, rdi; P
0x1400b2496  call    cs:__imp_ExFreePoolWithTag
0x1400b249d  nop     dword ptr [rax+rax+00h]
0x1400b24a2  xor     edx, edx; Tag
0x1400b24a4  mov     rcx, r14; P
0x1400b24a7  call    cs:__imp_ExFreePoolWithTag
0x1400b24ae  nop     dword ptr [rax+rax+00h]
0x1400b24b3  xor     edx, edx; Tag
0x1400b24b5  mov     rcx, r15; P
0x1400b24b8  call    cs:__imp_ExFreePoolWithTag
0x1400b24bf  nop     dword ptr [rax+rax+00h]
0x1400b24c4  test    ebx, ebx
0x1400b24c6  jns     short loc_1400B2531
0x1400b24c8  lea     rax, WPP_GLOBAL_Control
0x1400b24cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b24d6  cmp     rcx, rax
0x1400b24d9  jz      short loc_1400B2502
0x1400b24db  test    dword ptr [rcx+2Ch], 100h
0x1400b24e2  jz      short loc_1400B2502
0x1400b24e4  cmp     byte ptr [rcx+29h], 4
0x1400b24e8  jb      short loc_1400B2502
0x1400b24ea  mov     edx, 15h
0x1400b24ef  mov     r9d, ebx
0x1400b24f2  lea     r8, WPP_823e6dba7932309d1ad2e841189c99ac_Traceguids
0x1400b24f9  mov     rcx, [rcx+18h]
0x1400b24fd  call    WPP_SF_d
0x1400b2502  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x1400b2508  test    al, al
0x1400b250a  jz      short loc_1400B2522
0x1400b250c  mov     r9d, 1766h; unsigned int
0x1400b2512  lea     r8, aNtfsinitC; "NtfsInit.c"
0x1400b2519  xor     edx, edx; struct _IRP_CONTEXT *
0x1400b251b  mov     ecx, ebx; Status
0x1400b251d  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x1400b2522  mov     ecx, ebx; Status
0x1400b2524  call    cs:__imp_ExRaiseStatus
0x1400b2531  mov     rcx, [rsp+0C8h+var_30]
0x1400b2539  xor     rcx, rsp; StackCookie
0x1400b253c  call    __security_check_cookie
0x1400b2541  add     rsp, 0A0h
0x1400b2548  pop     r15
0x1400b254a  pop     r14
0x1400b254c  pop     rdi
0x1400b254d  pop     rsi
0x1400b254e  pop     rbx
0x1400b254f  retn
0x1401f5d6f  push    rbp
0x1401f5d71  sub     rsp, 40h
0x1401f5d75  mov     rbp, rdx
0x1401f5d78  cmp     byte ptr [rbp+40h], 0
0x1401f5d7c  jz      short loc_1401F5D8F
0x1401f5d7e  mov     rcx, [rbp+48h]; SubjectContext
0x1401f5d82  call    cs:__imp_SeReleaseSubjectContext
0x1401f5d89  nop     dword ptr [rax+rax+00h]
0x1401f5d8e  nop
0x1401f5d8f  mov     rcx, [rbp+48h]; P
0x1401f5d93  test    rcx, rcx
0x1401f5d96  jz      short loc_1401F5DA7
0x1401f5d98  xor     edx, edx; Tag
0x1401f5d9a  call    cs:__imp_ExFreePoolWithTag
0x1401f5da1  nop     dword ptr [rax+rax+00h]
0x1401f5da6  nop
0x1401f5da7  mov     rcx, [rbp+50h]; P
0x1401f5dab  test    rcx, rcx
0x1401f5dae  jz      short loc_1401F5DBF
0x1401f5db0  xor     edx, edx; Tag
0x1401f5db2  call    cs:__imp_ExFreePoolWithTag
0x1401f5db9  nop     dword ptr [rax+rax+00h]
0x1401f5dbe  nop
0x1401f5dbf  mov     rcx, [rbp+58h]; P
0x1401f5dc3  test    rcx, rcx
0x1401f5dc6  jz      short loc_1401F5DD7
0x1401f5dc8  xor     edx, edx; Tag
0x1401f5dca  call    cs:__imp_ExFreePoolWithTag
0x1401f5dd1  nop     dword ptr [rax+rax+00h]
0x1401f5dd6  nop
0x1401f5dd7  mov     rcx, [rbp+60h]; P
0x1401f5ddb  test    rcx, rcx
0x1401f5dde  jz      short loc_1401F5DEF
0x1401f5de0  xor     edx, edx; Tag
0x1401f5de2  call    cs:__imp_ExFreePoolWithTag
0x1401f5de9  nop     dword ptr [rax+rax+00h]
0x1401f5dee  nop
0x1401f5def  add     rsp, 40h
0x1401f5df3  pop     rbp
0x1401f5df4  retn
```
