# CClfsAuthContainer::CreateTempContainerSecurityDescriptor(void * &)

- ea: `0x140001474`
- end: `0x14000182d`
- name: `?CreateTempContainerSecurityDescriptor@CClfsAuthContainer@@CAJAEAPEAX@Z`
- size: `953`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14003b7d0`

## callees

- `0x140001474`
- `0x140017e40`

## import_xrefs

- `ntoskrnl!RtlLengthRequiredSid` at `0x1400014e9`
- `ntoskrnl!RtlLengthRequiredSid` at `0x14000151e`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1400014e9`
- `ntoskrnl!RtlLengthRequiredSid` at `0x14000151e`
- `ntoskrnl!RtlInitializeSid` at `0x140001566`
- `ntoskrnl!RtlInitializeSid` at `0x1400015af`
- `ntoskrnl!RtlInitializeSid` at `0x140001566`
- `ntoskrnl!RtlInitializeSid` at `0x1400015af`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140001577`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14000158f`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400015c0`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140001577`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14000158f`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400015c0`
- `ntoskrnl!RtlCreateAcl` at `0x14000161b`
- `ntoskrnl!RtlCreateAcl` at `0x14000161b`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1400016a1`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1400016a1`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1400016c9`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1400016c9`
- `ntoskrnl!RtlSetOwnerSecurityDescriptor` at `0x1400016ee`
- `ntoskrnl!RtlSetOwnerSecurityDescriptor` at `0x1400016ee`
- `ntoskrnl!RtlSetGroupSecurityDescriptor` at `0x140001713`
- `ntoskrnl!RtlSetGroupSecurityDescriptor` at `0x140001713`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x140001735`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x140001781`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x140001735`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x140001781`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x14000164d`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x14000167f`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x14000164d`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x14000167f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400017ac`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400017c5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400017db`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400017f1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019598`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400195b6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400195d5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400195f4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400017ac`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400017c5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400017db`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400017f1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140019598`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400195b6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400195d5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400195f4`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140001507`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140001532`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400015f4`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140001760`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140001507`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140001532`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400015f4`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140001760`

## pseudocode

```c
__int64 __fastcall CClfsAuthContainer::CreateTempContainerSecurityDescriptor(void **a1)
{
  struct _ACL *v2; // rdi
  ULONG v3; // eax
  unsigned __int8 *Sid; // r15
  ULONG v5; // eax
  unsigned __int8 *PoolWithTag; // rax
  unsigned __int8 *v7; // rsi
  ULONG v8; // ebx
  struct _ACL *v9; // rax
  NTSTATUS Acl; // ebx
  PVOID v11; // rax
  ULONG BufferLength; // [rsp+34h] [rbp-84h] BYREF
  struct _ACL *v14; // [rsp+38h] [rbp-80h]
  unsigned __int8 *v15; // [rsp+40h] [rbp-78h]
  unsigned __int8 *v16; // [rsp+48h] [rbp-70h]
  void **v17; // [rsp+50h] [rbp-68h]
  _OWORD SecurityDescriptor[2]; // [rsp+58h] [rbp-60h] BYREF
  __int64 v19; // [rsp+78h] [rbp-40h]
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+80h] [rbp-38h] BYREF

  v17 = a1;
  v2 = 0;
  v14 = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  v19 = 0;
  BufferLength = 0;
  *a1 = 0;
  v3 = RtlLengthRequiredSid(2u);
  Sid = (unsigned __int8 *)ExAllocatePoolWithTag(PagedPool, v3, 0x73666C43u);
  v15 = Sid;
  v5 = RtlLengthRequiredSid(1u);
  PoolWithTag = (unsigned __int8 *)ExAllocatePoolWithTag(PagedPool, v5, 0x73666C43u);
  v7 = PoolWithTag;
  v16 = PoolWithTag;
  if ( !Sid )
    goto LABEL_14;
  if ( !PoolWithTag )
    goto LABEL_14;
  RtlInitializeSid(Sid, &IdentifierAuthority, 2u);
  *RtlSubAuthoritySid(Sid, 0) = 32;
  *RtlSubAuthoritySid(Sid, 1u) = 544;
  RtlInitializeSid(v7, &IdentifierAuthority, 1u);
  *RtlSubAuthoritySid(v7, 0) = 18;
  v8 = (4 * (Sid[1] + v7[1]) + 55) & 0xFFFFFFF8;
  v9 = (struct _ACL *)ExAllocatePoolWithTag(PagedPool, v8, 0x73666C43u);
  v2 = v9;
  v14 = v9;
  if ( !v9 )
    goto LABEL_14;
  Acl = RtlCreateAcl(v9, v8, 2u);
  if ( Acl >= 0 )
  {
    Acl = RtlAddAccessAllowedAceEx(v2, 2u, 3u, 0x10000000u, Sid);
    if ( Acl >= 0 )
    {
      Acl = RtlAddAccessAllowedAceEx(v2, 2u, 3u, 0x10000000u, v7);
      if ( Acl >= 0 )
      {
        Acl = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
        if ( Acl >= 0 )
        {
          Acl = RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, v2, 0);
          if ( Acl >= 0 )
          {
            Acl = RtlSetOwnerSecurityDescriptor(SecurityDescriptor, v7, 0);
            if ( Acl >= 0 )
            {
              Acl = RtlSetGroupSecurityDescriptor(SecurityDescriptor, v7, 0);
              if ( Acl >= 0 )
              {
                Acl = RtlAbsoluteToSelfRelativeSD(SecurityDescriptor, 0, &BufferLength);
                if ( Acl == -1073741789 )
                {
                  v11 = ExAllocatePoolWithTag(PagedPool, BufferLength, 0x73666C43u);
                  *a1 = v11;
                  if ( v11 )
                  {
                    Acl = RtlAbsoluteToSelfRelativeSD(SecurityDescriptor, v11, &BufferLength);
                    goto LABEL_15;
                  }
LABEL_14:
                  Acl = -1073741670;
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_15:
  if ( Acl < 0 && *a1 )
  {
    ExFreePoolWithTag(*a1, 0);
    *a1 = 0;
  }
  if ( v2 )
    ExFreePoolWithTag(v2, 0);
  if ( Sid )
    ExFreePoolWithTag(Sid, 0);
  if ( v7 )
    ExFreePoolWithTag(v7, 0);
  return (unsigned int)Acl;
}

```

## disassembly

```asm
0x140001474  mov     r11, rsp
0x140001477  mov     [r11+10h], rbx
0x14000147b  mov     [r11+18h], rsi
0x14000147f  push    rdi
0x140001480  push    r12
0x140001482  push    r13
0x140001484  push    r14
0x140001486  push    r15
0x140001488  sub     rsp, 90h
0x14000148f  mov     rax, cs:__security_cookie
0x140001496  xor     rax, rsp
0x140001499  mov     [rsp+0B8h+var_30], rax
0x1400014a1  mov     r14, rcx
0x1400014a4  mov     [rsp+0B8h+var_68], rcx
0x1400014a9  xor     r12d, r12d
0x1400014ac  mov     [rsp+0B8h+var_88], r12d
0x1400014b1  mov     [r11-78h], r12
0x1400014b5  mov     [r11-70h], r12
0x1400014b9  mov     edi, r12d
0x1400014bc  mov     [r11-80h], r12
0x1400014c0  mov     [r11-38h], r12d
0x1400014c4  mov     word ptr [r11-34h], 500h
0x1400014cb  xorps   xmm0, xmm0
0x1400014ce  xor     eax, eax
0x1400014d0  movups  [rsp+0B8h+SecurityDescriptor], xmm0
0x1400014d5  movups  [rsp+0B8h+var_50], xmm0
0x1400014da  mov     [r11-40h], rax
0x1400014de  mov     [rsp+0B8h+BufferLength], r12d
0x1400014e3  mov     [rcx], r12
0x1400014e6  lea     ecx, [rax+2]; SubAuthorityCount
0x1400014e9  call    cs:__imp_RtlLengthRequiredSid
0x1400014f0  nop     dword ptr [rax+rax+00h]
0x1400014f5  mov     edx, eax; NumberOfBytes
0x1400014f7  mov     ebx, 73666C43h
0x1400014fc  mov     r8d, ebx; Tag
0x1400014ff  lea     r13d, [r12+1]
0x140001504  mov     ecx, r13d; PoolType
0x140001507  call    cs:__imp_ExAllocatePoolWithTag
0x14000150e  nop     dword ptr [rax+rax+00h]
0x140001513  mov     r15, rax
0x140001516  mov     [rsp+0B8h+var_78], rax
0x14000151b  mov     ecx, r13d; SubAuthorityCount
0x14000151e  call    cs:__imp_RtlLengthRequiredSid
0x140001525  nop     dword ptr [rax+rax+00h]
0x14000152a  mov     edx, eax; NumberOfBytes
0x14000152c  mov     r8d, ebx; Tag
0x14000152f  mov     ecx, r13d; PoolType
0x140001532  call    cs:__imp_ExAllocatePoolWithTag
0x140001539  nop     dword ptr [rax+rax+00h]
0x14000153e  mov     rsi, rax
0x140001541  mov     [rsp+0B8h+var_70], rax
0x140001546  test    r15, r15
0x140001549  jz      loc_140001795
0x14000154f  test    rax, rax
0x140001552  jz      loc_140001795
0x140001558  mov     r8b, 2; SubAuthorityCount
0x14000155b  lea     rdx, [rsp+0B8h+IdentifierAuthority]; IdentifierAuthority
0x140001563  mov     rcx, r15; Sid
0x140001566  call    cs:__imp_RtlInitializeSid
0x14000156d  nop     dword ptr [rax+rax+00h]
0x140001572  xor     edx, edx; SubAuthority
0x140001574  mov     rcx, r15; Sid
0x140001577  call    cs:__imp_RtlSubAuthoritySid
0x14000157e  nop     dword ptr [rax+rax+00h]
0x140001583  mov     dword ptr [rax], 20h ; ' '
0x140001589  mov     edx, r13d; SubAuthority
0x14000158c  mov     rcx, r15; Sid
0x14000158f  call    cs:__imp_RtlSubAuthoritySid
0x140001596  nop     dword ptr [rax+rax+00h]
0x14000159b  mov     dword ptr [rax], 220h
0x1400015a1  mov     r8b, r13b; SubAuthorityCount
0x1400015a4  lea     rdx, [rsp+0B8h+IdentifierAuthority]; IdentifierAuthority
0x1400015ac  mov     rcx, rsi; Sid
0x1400015af  call    cs:__imp_RtlInitializeSid
0x1400015b6  nop     dword ptr [rax+rax+00h]
0x1400015bb  xor     edx, edx; SubAuthority
0x1400015bd  mov     rcx, rsi; Sid
0x1400015c0  call    cs:__imp_RtlSubAuthoritySid
0x1400015c7  nop     dword ptr [rax+rax+00h]
0x1400015cc  mov     dword ptr [rax], 12h
0x1400015d2  movzx   ecx, byte ptr [rsi+1]
0x1400015d6  movzx   eax, byte ptr [r15+1]
0x1400015db  add     ecx, eax
0x1400015dd  lea     eax, ds:37h[rcx*4]
0x1400015e4  and     eax, 0FFFFFFF8h
0x1400015e7  mov     ebx, eax
0x1400015e9  mov     edx, eax; NumberOfBytes
0x1400015eb  mov     r8d, 73666C43h; Tag
0x1400015f1  mov     ecx, r13d; PoolType
0x1400015f4  call    cs:__imp_ExAllocatePoolWithTag
0x1400015fb  nop     dword ptr [rax+rax+00h]
0x140001600  mov     rdi, rax
0x140001603  mov     [rsp+0B8h+var_80], rax
0x140001608  test    rax, rax
0x14000160b  jz      loc_140001795
0x140001611  lea     r8d, [r12+2]; AclRevision
0x140001616  mov     edx, ebx; AclLength
0x140001618  mov     rcx, rax; Acl
0x14000161b  call    cs:__imp_RtlCreateAcl
0x140001622  nop     dword ptr [rax+rax+00h]
0x140001627  mov     ebx, eax
0x140001629  mov     [rsp+0B8h+var_88], eax
0x14000162d  test    eax, eax
0x14000162f  js      loc_14000179E
0x140001635  mov     [rsp+0B8h+Sid], r15; Sid
0x14000163a  lea     edx, [r12+2]; AceRevision
0x14000163f  mov     r9d, 10000000h; AccessMask
0x140001645  lea     r8d, [r12+3]; AceFlags
0x14000164a  mov     rcx, rdi; Acl
0x14000164d  call    cs:__imp_RtlAddAccessAllowedAceEx
0x140001654  nop     dword ptr [rax+rax+00h]
0x140001659  mov     ebx, eax
0x14000165b  mov     [rsp+0B8h+var_88], eax
0x14000165f  test    eax, eax
0x140001661  js      loc_14000179E
0x140001667  mov     [rsp+0B8h+Sid], rsi; Sid
0x14000166c  lea     edx, [r12+2]; AceRevision
0x140001671  mov     r9d, 10000000h; AccessMask
0x140001677  lea     r8d, [r12+3]; AceFlags
0x14000167c  mov     rcx, rdi; Acl
0x14000167f  call    cs:__imp_RtlAddAccessAllowedAceEx
0x140001686  nop     dword ptr [rax+rax+00h]
0x14000168b  mov     ebx, eax
0x14000168d  mov     [rsp+0B8h+var_88], eax
0x140001691  test    eax, eax
0x140001693  js      loc_14000179E
0x140001699  mov     edx, r13d; Revision
0x14000169c  lea     rcx, [rsp+0B8h+SecurityDescriptor]; SecurityDescriptor
0x1400016a1  call    cs:__imp_RtlCreateSecurityDescriptor
0x1400016a8  nop     dword ptr [rax+rax+00h]
0x1400016ad  mov     ebx, eax
0x1400016af  mov     [rsp+0B8h+var_88], eax
0x1400016b3  test    eax, eax
0x1400016b5  js      loc_14000179E
0x1400016bb  xor     r9d, r9d; DaclDefaulted
0x1400016be  mov     r8, rdi; Dacl
0x1400016c1  mov     dl, r13b; DaclPresent
0x1400016c4  lea     rcx, [rsp+0B8h+SecurityDescriptor]; SecurityDescriptor
0x1400016c9  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x1400016d0  nop     dword ptr [rax+rax+00h]
0x1400016d5  mov     ebx, eax
0x1400016d7  mov     [rsp+0B8h+var_88], eax
0x1400016db  test    eax, eax
0x1400016dd  js      loc_14000179E
0x1400016e3  xor     r8d, r8d; OwnerDefaulted
0x1400016e6  mov     rdx, rsi; Owner
0x1400016e9  lea     rcx, [rsp+0B8h+SecurityDescriptor]; SecurityDescriptor
0x1400016ee  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x1400016f5  nop     dword ptr [rax+rax+00h]
0x1400016fa  mov     ebx, eax
0x1400016fc  mov     [rsp+0B8h+var_88], eax
0x140001700  test    eax, eax
0x140001702  js      loc_14000179E
0x140001708  xor     r8d, r8d; GroupDefaulted
0x14000170b  mov     rdx, rsi; Group
0x14000170e  lea     rcx, [rsp+0B8h+SecurityDescriptor]; SecurityDescriptor
0x140001713  call    cs:__imp_RtlSetGroupSecurityDescriptor
0x14000171a  nop     dword ptr [rax+rax+00h]
0x14000171f  mov     ebx, eax
0x140001721  mov     [rsp+0B8h+var_88], eax
0x140001725  test    eax, eax
0x140001727  js      short loc_14000179E
0x140001729  lea     r8, [rsp+0B8h+BufferLength]; BufferLength
0x14000172e  xor     edx, edx; SelfRelativeSecurityDescriptor
0x140001730  lea     rcx, [rsp+0B8h+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x140001735  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x14000173c  nop     dword ptr [rax+rax+00h]
0x140001741  mov     ebx, eax
0x140001743  mov     [rsp+0B8h+var_88], eax
0x140001747  cmp     eax, 0C0000023h
0x14000174c  jnz     short loc_14000179E
0x14000174e  mov     [rsp+0B8h+var_88], r12d
0x140001753  mov     edx, [rsp+0B8h+BufferLength]; NumberOfBytes
0x140001757  mov     r8d, 73666C43h; Tag
0x14000175d  mov     ecx, r13d; PoolType
0x140001760  call    cs:__imp_ExAllocatePoolWithTag
0x140001767  nop     dword ptr [rax+rax+00h]
0x14000176c  mov     [r14], rax
0x14000176f  test    rax, rax
0x140001772  jz      short loc_140001795
0x140001774  lea     r8, [rsp+0B8h+BufferLength]; BufferLength
0x140001779  mov     rdx, rax; SelfRelativeSecurityDescriptor
0x14000177c  lea     rcx, [rsp+0B8h+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x140001781  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x140001788  nop     dword ptr [rax+rax+00h]
0x14000178d  mov     ebx, eax
0x14000178f  mov     [rsp+0B8h+var_88], eax
0x140001793  jmp     short loc_14000179E
0x140001795  mov     ebx, 0C000009Ah
0x14000179a  mov     [rsp+0B8h+var_88], ebx
0x14000179e  test    ebx, ebx
0x1400017a0  jns     short loc_1400017BB
0x1400017a2  mov     rcx, [r14]; P
0x1400017a5  test    rcx, rcx
0x1400017a8  jz      short loc_1400017BB
0x1400017aa  xor     edx, edx; Tag
0x1400017ac  call    cs:__imp_ExFreePoolWithTag
0x1400017b3  nop     dword ptr [rax+rax+00h]
0x1400017b8  mov     [r14], r12
0x1400017bb  test    rdi, rdi
0x1400017be  jz      short loc_1400017D1
0x1400017c0  xor     edx, edx; Tag
0x1400017c2  mov     rcx, rdi; P
0x1400017c5  call    cs:__imp_ExFreePoolWithTag
0x1400017cc  nop     dword ptr [rax+rax+00h]
0x1400017d1  test    r15, r15
0x1400017d4  jz      short loc_1400017E7
0x1400017d6  xor     edx, edx; Tag
0x1400017d8  mov     rcx, r15; P
0x1400017db  call    cs:__imp_ExFreePoolWithTag
0x1400017e2  nop     dword ptr [rax+rax+00h]
0x1400017e7  test    rsi, rsi
0x1400017ea  jz      short loc_1400017FD
0x1400017ec  xor     edx, edx; Tag
0x1400017ee  mov     rcx, rsi; P
0x1400017f1  call    cs:__imp_ExFreePoolWithTag
0x1400017f8  nop     dword ptr [rax+rax+00h]
0x1400017fd  mov     eax, ebx
0x1400017ff  mov     rcx, [rsp+0B8h+var_30]
0x140001807  xor     rcx, rsp; StackCookie
0x14000180a  call    __security_check_cookie
0x14000180f  lea     r11, [rsp+0B8h+var_28]
0x140001817  mov     rbx, [r11+38h]
0x14000181b  mov     rsi, [r11+40h]
0x14000181f  mov     rsp, r11
0x140001822  pop     r15
0x140001824  pop     r14
0x140001826  pop     r13
0x140001828  pop     r12
0x14000182a  pop     rdi
0x14000182b  retn
0x140019579  push    rbx
0x14001957b  push    rbp
0x14001957c  sub     rsp, 38h
0x140019580  mov     rbp, rdx
0x140019583  cmp     dword ptr [rbp+30h], 0
0x140019587  jge     short loc_1400195AB
0x140019589  mov     rbx, [rbp+50h]
0x14001958d  cmp     qword ptr [rbx], 0
0x140019591  jz      short loc_1400195AB
0x140019593  xor     edx, edx; Tag
0x140019595  mov     rcx, [rbx]; P
0x140019598  call    cs:__imp_ExFreePoolWithTag
0x14001959f  nop     dword ptr [rax+rax+00h]
0x1400195a4  mov     qword ptr [rbx], 0
0x1400195ab  mov     rcx, [rbp+38h]; P
0x1400195af  test    rcx, rcx
0x1400195b2  jz      short loc_1400195CA
0x1400195b4  xor     edx, edx; Tag
0x1400195b6  call    cs:__imp_ExFreePoolWithTag
0x1400195bd  nop     dword ptr [rax+rax+00h]
0x1400195c2  mov     qword ptr [rbp+38h], 0
0x1400195ca  mov     rcx, [rbp+40h]; P
0x1400195ce  test    rcx, rcx
0x1400195d1  jz      short loc_1400195E9
0x1400195d3  xor     edx, edx; Tag
0x1400195d5  call    cs:__imp_ExFreePoolWithTag
0x1400195dc  nop     dword ptr [rax+rax+00h]
0x1400195e1  mov     qword ptr [rbp+40h], 0
0x1400195e9  mov     rcx, [rbp+48h]; P
0x1400195ed  test    rcx, rcx
0x1400195f0  jz      short loc_140019608
0x1400195f2  xor     edx, edx; Tag
0x1400195f4  call    cs:__imp_ExFreePoolWithTag
0x1400195fb  nop     dword ptr [rax+rax+00h]
0x140019600  mov     qword ptr [rbp+48h], 0
0x140019608  add     rsp, 38h
0x14001960c  pop     rbp
0x14001960d  pop     rbx
0x14001960e  retn
```
