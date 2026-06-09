# ClfsCreateAuthRegistrySecurityDescriptor

- ea: `0x140071e8c`
- end: `0x140072379`
- name: `ClfsCreateAuthRegistrySecurityDescriptor`
- size: `1261`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14004ddb4`
- `0x1400753f0`

## callees

- `0x140017e40`
- `0x140071e8c`

## import_xrefs

- `ntoskrnl!RtlLengthRequiredSid` at `0x140071f07`
- `ntoskrnl!RtlLengthRequiredSid` at `0x140071f3a`
- `ntoskrnl!RtlLengthRequiredSid` at `0x140071f64`
- `ntoskrnl!RtlLengthRequiredSid` at `0x140071f07`
- `ntoskrnl!RtlLengthRequiredSid` at `0x140071f3a`
- `ntoskrnl!RtlLengthRequiredSid` at `0x140071f64`
- `ntoskrnl!RtlInitializeSid` at `0x140071fb4`
- `ntoskrnl!RtlInitializeSid` at `0x140071ffc`
- `ntoskrnl!RtlInitializeSid` at `0x14007202d`
- `ntoskrnl!RtlInitializeSid` at `0x140071fb4`
- `ntoskrnl!RtlInitializeSid` at `0x140071ffc`
- `ntoskrnl!RtlInitializeSid` at `0x14007202d`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140071fc5`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140071fdc`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14007200d`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14007203e`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140072055`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14007206d`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140072085`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14007209d`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400720b5`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140071fc5`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140071fdc`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14007200d`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14007203e`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140072055`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14007206d`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140072085`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14007209d`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400720b5`
- `ntoskrnl!RtlCreateAcl` at `0x140072118`
- `ntoskrnl!RtlCreateAcl` at `0x140072118`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1400721cb`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1400721cb`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1400721f2`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1400721f2`
- `ntoskrnl!RtlSetOwnerSecurityDescriptor` at `0x140072217`
- `ntoskrnl!RtlSetOwnerSecurityDescriptor` at `0x140072217`
- `ntoskrnl!RtlSetGroupSecurityDescriptor` at `0x14007223c`
- `ntoskrnl!RtlSetGroupSecurityDescriptor` at `0x14007223c`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x14007225e`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x1400722ab`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x14007225e`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x1400722ab`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x140072148`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x140072178`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1400721a8`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x140072148`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x140072178`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1400721a8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400722db`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400722f1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007233c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140072355`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007236b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007bf8b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007bfa9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007bfc8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007bfe7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007c006`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400722db`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400722f1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007233c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140072355`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007236b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007bf8b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007bfa9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007bfc8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007bfe7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007c006`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140071f24`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140071f4d`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140071f77`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400720f2`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14007228a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140071f24`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140071f4d`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140071f77`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400720f2`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14007228a`

## pseudocode

```c
__int64 __fastcall ClfsCreateAuthRegistrySecurityDescriptor(__int64 a1, PVOID *a2)
{
  struct _ACL *v3; // rdi
  ULONG v4; // eax
  unsigned __int8 *Sid; // r12
  ULONG v6; // eax
  unsigned __int8 *PoolWithTag; // rsi
  ULONG v8; // eax
  unsigned __int8 *v9; // rax
  unsigned __int8 *v10; // r14
  ULONG v11; // ebx
  struct _ACL *v12; // rax
  NTSTATUS Acl; // ebx
  PVOID v14; // rax
  ULONG BufferLength; // [rsp+34h] [rbp-94h] BYREF
  struct _ACL *v17; // [rsp+38h] [rbp-90h]
  unsigned __int8 *v18; // [rsp+40h] [rbp-88h]
  unsigned __int8 *v19; // [rsp+48h] [rbp-80h]
  unsigned __int8 *v20; // [rsp+50h] [rbp-78h]
  PVOID *v21; // [rsp+58h] [rbp-70h]
  _OWORD SecurityDescriptor[2]; // [rsp+60h] [rbp-68h] BYREF
  __int64 v23; // [rsp+80h] [rbp-48h]
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+88h] [rbp-40h] BYREF

  v21 = a2;
  v3 = 0;
  v17 = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  v23 = 0;
  BufferLength = 0;
  *a2 = 0;
  v4 = RtlLengthRequiredSid(2u);
  Sid = (unsigned __int8 *)ExAllocatePoolWithTag(PagedPool, v4, 0x73666C43u);
  v18 = Sid;
  v6 = RtlLengthRequiredSid(1u);
  PoolWithTag = (unsigned __int8 *)ExAllocatePoolWithTag(PagedPool, v6, 0x73666C43u);
  v20 = PoolWithTag;
  v8 = RtlLengthRequiredSid(6u);
  v9 = (unsigned __int8 *)ExAllocatePoolWithTag(PagedPool, v8, 0x73666C43u);
  v10 = v9;
  v19 = v9;
  if ( !Sid )
    goto LABEL_16;
  if ( !PoolWithTag )
    goto LABEL_16;
  if ( !v9 )
    goto LABEL_16;
  RtlInitializeSid(Sid, &IdentifierAuthority, 2u);
  *RtlSubAuthoritySid(Sid, 0) = 32;
  *RtlSubAuthoritySid(Sid, 1u) = 544;
  RtlInitializeSid(PoolWithTag, &IdentifierAuthority, 1u);
  *RtlSubAuthoritySid(PoolWithTag, 0) = 18;
  RtlInitializeSid(v10, &IdentifierAuthority, 6u);
  *RtlSubAuthoritySid(v10, 0) = 80;
  *RtlSubAuthoritySid(v10, 1u) = 956008885;
  *RtlSubAuthoritySid(v10, 2u) = -876444647;
  *RtlSubAuthoritySid(v10, 3u) = 1831038044;
  *RtlSubAuthoritySid(v10, 4u) = 1853292631;
  *RtlSubAuthoritySid(v10, 5u) = -2023488832;
  v11 = (4 * (Sid[1] + PoolWithTag[1] + v10[1]) + 75) & 0xFFFFFFF8;
  v12 = (struct _ACL *)ExAllocatePoolWithTag(PagedPool, v11, 0x73666C43u);
  v3 = v12;
  v17 = v12;
  if ( !v12 )
    goto LABEL_16;
  Acl = RtlCreateAcl(v12, v11, 2u);
  if ( Acl >= 0 )
  {
    Acl = RtlAddAccessAllowedAceEx(v3, 2u, 3u, 0xF003Fu, Sid);
    if ( Acl >= 0 )
    {
      Acl = RtlAddAccessAllowedAceEx(v3, 2u, 3u, 0xF003Fu, PoolWithTag);
      if ( Acl >= 0 )
      {
        Acl = RtlAddAccessAllowedAceEx(v3, 2u, 3u, 0xF003Fu, v10);
        if ( Acl >= 0 )
        {
          Acl = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
          if ( Acl >= 0 )
          {
            Acl = RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, v3, 0);
            if ( Acl >= 0 )
            {
              Acl = RtlSetOwnerSecurityDescriptor(SecurityDescriptor, PoolWithTag, 0);
              if ( Acl >= 0 )
              {
                Acl = RtlSetGroupSecurityDescriptor(SecurityDescriptor, PoolWithTag, 0);
                if ( Acl >= 0 )
                {
                  Acl = RtlAbsoluteToSelfRelativeSD(SecurityDescriptor, 0, &BufferLength);
                  if ( Acl == -1073741789 )
                  {
                    v14 = ExAllocatePoolWithTag(PagedPool, BufferLength, 0x73666C43u);
                    *a2 = v14;
                    if ( v14 )
                    {
                      Acl = RtlAbsoluteToSelfRelativeSD(SecurityDescriptor, v14, &BufferLength);
                      goto LABEL_17;
                    }
LABEL_16:
                    Acl = -1073741670;
                  }
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_17:
  if ( Acl < 0 && *a2 )
  {
    ExFreePoolWithTag(*a2, 0);
    *a2 = 0;
  }
  if ( v3 )
    ExFreePoolWithTag(v3, 0);
  if ( Sid )
    ExFreePoolWithTag(Sid, 0);
  if ( v10 )
    ExFreePoolWithTag(v10, 0);
  if ( PoolWithTag )
    ExFreePoolWithTag(PoolWithTag, 0);
  return (unsigned int)Acl;
}

```

## disassembly

```asm
0x140071e8c  mov     r11, rsp
0x140071e8f  mov     [r11+8], rbx
0x140071e93  mov     [r11+18h], rsi
0x140071e97  push    rdi
0x140071e98  push    r12
0x140071e9a  push    r13
0x140071e9c  push    r14
0x140071e9e  push    r15
0x140071ea0  sub     rsp, 0A0h
0x140071ea7  mov     rax, cs:__security_cookie
0x140071eae  xor     rax, rsp
0x140071eb1  mov     [rsp+0C8h+var_38], rax
0x140071eb9  mov     r15, rdx
0x140071ebc  mov     [rsp+0C8h+var_70], rdx
0x140071ec1  xor     r13d, r13d
0x140071ec4  mov     [rsp+0C8h+var_98], r13d
0x140071ec9  mov     [rsp+0C8h+var_88], r13
0x140071ece  mov     [r11-78h], r13
0x140071ed2  mov     [r11-80h], r13
0x140071ed6  mov     edi, r13d
0x140071ed9  mov     [rsp+0C8h+var_90], r13
0x140071ede  mov     [r11-40h], r13d
0x140071ee2  mov     word ptr [r11-3Ch], 500h
0x140071ee9  xorps   xmm0, xmm0
0x140071eec  xor     eax, eax
0x140071eee  movups  [rsp+0C8h+SecurityDescriptor], xmm0
0x140071ef3  movups  [rsp+0C8h+var_58], xmm0
0x140071ef8  mov     [r11-48h], rax
0x140071efc  mov     [rsp+0C8h+BufferLength], r13d
0x140071f01  mov     [rdx], r13
0x140071f04  lea     ecx, [rax+2]; SubAuthorityCount
0x140071f07  call    cs:__imp_RtlLengthRequiredSid
0x140071f0e  nop     dword ptr [rax+rax+00h]
0x140071f13  mov     edx, eax; NumberOfBytes
0x140071f15  mov     r14d, 73666C43h
0x140071f1b  mov     r8d, r14d; Tag
0x140071f1e  lea     ebx, [r13+1]
0x140071f22  mov     ecx, ebx; PoolType
0x140071f24  call    cs:__imp_ExAllocatePoolWithTag
0x140071f2b  nop     dword ptr [rax+rax+00h]
0x140071f30  mov     r12, rax
0x140071f33  mov     [rsp+0C8h+var_88], rax
0x140071f38  mov     ecx, ebx; SubAuthorityCount
0x140071f3a  call    cs:__imp_RtlLengthRequiredSid
0x140071f41  nop     dword ptr [rax+rax+00h]
0x140071f46  mov     edx, eax; NumberOfBytes
0x140071f48  mov     r8d, r14d; Tag
0x140071f4b  mov     ecx, ebx; PoolType
0x140071f4d  call    cs:__imp_ExAllocatePoolWithTag
0x140071f54  nop     dword ptr [rax+rax+00h]
0x140071f59  mov     rsi, rax
0x140071f5c  mov     [rsp+0C8h+var_78], rax
0x140071f61  lea     ecx, [rbx+5]; SubAuthorityCount
0x140071f64  call    cs:__imp_RtlLengthRequiredSid
0x140071f6b  nop     dword ptr [rax+rax+00h]
0x140071f70  mov     edx, eax; NumberOfBytes
0x140071f72  mov     r8d, r14d; Tag
0x140071f75  mov     ecx, ebx; PoolType
0x140071f77  call    cs:__imp_ExAllocatePoolWithTag
0x140071f7e  nop     dword ptr [rax+rax+00h]
0x140071f83  mov     r14, rax
0x140071f86  mov     [rsp+0C8h+var_80], rax
0x140071f8b  test    r12, r12
0x140071f8e  jz      loc_1400722BF
0x140071f94  test    rsi, rsi
0x140071f97  jz      loc_1400722BF
0x140071f9d  test    rax, rax
0x140071fa0  jz      loc_1400722BF
0x140071fa6  mov     r8b, 2; SubAuthorityCount
0x140071fa9  lea     rdx, [rsp+0C8h+IdentifierAuthority]; IdentifierAuthority
0x140071fb1  mov     rcx, r12; Sid
0x140071fb4  call    cs:__imp_RtlInitializeSid
0x140071fbb  nop     dword ptr [rax+rax+00h]
0x140071fc0  xor     edx, edx; SubAuthority
0x140071fc2  mov     rcx, r12; Sid
0x140071fc5  call    cs:__imp_RtlSubAuthoritySid
0x140071fcc  nop     dword ptr [rax+rax+00h]
0x140071fd1  mov     dword ptr [rax], 20h ; ' '
0x140071fd7  mov     edx, ebx; SubAuthority
0x140071fd9  mov     rcx, r12; Sid
0x140071fdc  call    cs:__imp_RtlSubAuthoritySid
0x140071fe3  nop     dword ptr [rax+rax+00h]
0x140071fe8  mov     dword ptr [rax], 220h
0x140071fee  mov     r8b, bl; SubAuthorityCount
0x140071ff1  lea     rdx, [rsp+0C8h+IdentifierAuthority]; IdentifierAuthority
0x140071ff9  mov     rcx, rsi; Sid
0x140071ffc  call    cs:__imp_RtlInitializeSid
0x140072003  nop     dword ptr [rax+rax+00h]
0x140072008  xor     edx, edx; SubAuthority
0x14007200a  mov     rcx, rsi; Sid
0x14007200d  call    cs:__imp_RtlSubAuthoritySid
0x140072014  nop     dword ptr [rax+rax+00h]
0x140072019  mov     dword ptr [rax], 12h
0x14007201f  mov     r8b, 6; SubAuthorityCount
0x140072022  lea     rdx, [rsp+0C8h+IdentifierAuthority]; IdentifierAuthority
0x14007202a  mov     rcx, r14; Sid
0x14007202d  call    cs:__imp_RtlInitializeSid
0x140072034  nop     dword ptr [rax+rax+00h]
0x140072039  xor     edx, edx; SubAuthority
0x14007203b  mov     rcx, r14; Sid
0x14007203e  call    cs:__imp_RtlSubAuthoritySid
0x140072045  nop     dword ptr [rax+rax+00h]
0x14007204a  mov     dword ptr [rax], 50h ; 'P'
0x140072050  mov     edx, ebx; SubAuthority
0x140072052  mov     rcx, r14; Sid
0x140072055  call    cs:__imp_RtlSubAuthoritySid
0x14007205c  nop     dword ptr [rax+rax+00h]
0x140072061  mov     dword ptr [rax], 38FB89B5h
0x140072067  lea     edx, [rbx+1]; SubAuthority
0x14007206a  mov     rcx, r14; Sid
0x14007206d  call    cs:__imp_RtlSubAuthoritySid
0x140072074  nop     dword ptr [rax+rax+00h]
0x140072079  mov     dword ptr [rax], 0CBC28419h
0x14007207f  lea     edx, [rbx+2]; SubAuthority
0x140072082  mov     rcx, r14; Sid
0x140072085  call    cs:__imp_RtlSubAuthoritySid
0x14007208c  nop     dword ptr [rax+rax+00h]
0x140072091  mov     dword ptr [rax], 6D236C5Ch
0x140072097  lea     edx, [rbx+3]; SubAuthority
0x14007209a  mov     rcx, r14; Sid
0x14007209d  call    cs:__imp_RtlSubAuthoritySid
0x1400720a4  nop     dword ptr [rax+rax+00h]
0x1400720a9  mov     dword ptr [rax], 6E770057h
0x1400720af  lea     edx, [rbx+4]; SubAuthority
0x1400720b2  mov     rcx, r14; Sid
0x1400720b5  call    cs:__imp_RtlSubAuthoritySid
0x1400720bc  nop     dword ptr [rax+rax+00h]
0x1400720c1  mov     dword ptr [rax], 876402C0h
0x1400720c7  movzx   ecx, byte ptr [r14+1]
0x1400720cc  movzx   eax, byte ptr [rsi+1]
0x1400720d0  add     ecx, eax
0x1400720d2  movzx   eax, byte ptr [r12+1]
0x1400720d8  add     ecx, eax
0x1400720da  lea     eax, ds:4Bh[rcx*4]
0x1400720e1  and     eax, 0FFFFFFF8h
0x1400720e4  mov     ebx, eax
0x1400720e6  mov     edx, eax; NumberOfBytes
0x1400720e8  lea     ecx, [r13+1]; PoolType
0x1400720ec  mov     r8d, 73666C43h; Tag
0x1400720f2  call    cs:__imp_ExAllocatePoolWithTag
0x1400720f9  nop     dword ptr [rax+rax+00h]
0x1400720fe  mov     rdi, rax
0x140072101  mov     [rsp+0C8h+var_90], rax
0x140072106  test    rax, rax
0x140072109  jz      loc_1400722BF
0x14007210f  lea     r8d, [r13+2]; AclRevision
0x140072113  mov     edx, ebx; AclLength
0x140072115  mov     rcx, rax; Acl
0x140072118  call    cs:__imp_RtlCreateAcl
0x14007211f  nop     dword ptr [rax+rax+00h]
0x140072124  mov     ebx, eax
0x140072126  mov     [rsp+0C8h+var_98], eax
0x14007212a  test    eax, eax
0x14007212c  js      loc_1400722C8
0x140072132  mov     [rsp+0C8h+Sid], r12; Sid
0x140072137  lea     edx, [r13+2]; AceRevision
0x14007213b  mov     r9d, 0F003Fh; AccessMask
0x140072141  lea     r8d, [r13+3]; AceFlags
0x140072145  mov     rcx, rdi; Acl
0x140072148  call    cs:__imp_RtlAddAccessAllowedAceEx
0x14007214f  nop     dword ptr [rax+rax+00h]
0x140072154  mov     ebx, eax
0x140072156  mov     [rsp+0C8h+var_98], eax
0x14007215a  test    eax, eax
0x14007215c  js      loc_1400722C8
0x140072162  mov     [rsp+0C8h+Sid], rsi; Sid
0x140072167  lea     edx, [r13+2]; AceRevision
0x14007216b  mov     r9d, 0F003Fh; AccessMask
0x140072171  lea     r8d, [r13+3]; AceFlags
0x140072175  mov     rcx, rdi; Acl
0x140072178  call    cs:__imp_RtlAddAccessAllowedAceEx
0x14007217f  nop     dword ptr [rax+rax+00h]
0x140072184  mov     ebx, eax
0x140072186  mov     [rsp+0C8h+var_98], eax
0x14007218a  test    eax, eax
0x14007218c  js      loc_1400722C8
0x140072192  mov     [rsp+0C8h+Sid], r14; Sid
0x140072197  lea     edx, [r13+2]; AceRevision
0x14007219b  mov     r9d, 0F003Fh; AccessMask
0x1400721a1  lea     r8d, [r13+3]; AceFlags
0x1400721a5  mov     rcx, rdi; Acl
0x1400721a8  call    cs:__imp_RtlAddAccessAllowedAceEx
0x1400721af  nop     dword ptr [rax+rax+00h]
0x1400721b4  mov     ebx, eax
0x1400721b6  mov     [rsp+0C8h+var_98], eax
0x1400721ba  test    eax, eax
0x1400721bc  js      loc_1400722C8
0x1400721c2  lea     edx, [r13+1]; Revision
0x1400721c6  lea     rcx, [rsp+0C8h+SecurityDescriptor]; SecurityDescriptor
0x1400721cb  call    cs:__imp_RtlCreateSecurityDescriptor
0x1400721d2  nop     dword ptr [rax+rax+00h]
0x1400721d7  mov     ebx, eax
0x1400721d9  mov     [rsp+0C8h+var_98], eax
0x1400721dd  test    eax, eax
0x1400721df  js      loc_1400722C8
0x1400721e5  xor     r9d, r9d; DaclDefaulted
0x1400721e8  mov     r8, rdi; Dacl
0x1400721eb  mov     dl, 1; DaclPresent
0x1400721ed  lea     rcx, [rsp+0C8h+SecurityDescriptor]; SecurityDescriptor
0x1400721f2  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x1400721f9  nop     dword ptr [rax+rax+00h]
0x1400721fe  mov     ebx, eax
0x140072200  mov     [rsp+0C8h+var_98], eax
0x140072204  test    eax, eax
0x140072206  js      loc_1400722C8
0x14007220c  xor     r8d, r8d; OwnerDefaulted
0x14007220f  mov     rdx, rsi; Owner
0x140072212  lea     rcx, [rsp+0C8h+SecurityDescriptor]; SecurityDescriptor
0x140072217  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x14007221e  nop     dword ptr [rax+rax+00h]
0x140072223  mov     ebx, eax
0x140072225  mov     [rsp+0C8h+var_98], eax
0x140072229  test    eax, eax
0x14007222b  js      loc_1400722C8
0x140072231  xor     r8d, r8d; GroupDefaulted
0x140072234  mov     rdx, rsi; Group
0x140072237  lea     rcx, [rsp+0C8h+SecurityDescriptor]; SecurityDescriptor
0x14007223c  call    cs:__imp_RtlSetGroupSecurityDescriptor
0x140072243  nop     dword ptr [rax+rax+00h]
0x140072248  mov     ebx, eax
0x14007224a  mov     [rsp+0C8h+var_98], eax
0x14007224e  test    eax, eax
0x140072250  js      short loc_1400722C8
0x140072252  lea     r8, [rsp+0C8h+BufferLength]; BufferLength
0x140072257  xor     edx, edx; SelfRelativeSecurityDescriptor
0x140072259  lea     rcx, [rsp+0C8h+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x14007225e  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x140072265  nop     dword ptr [rax+rax+00h]
0x14007226a  mov     ebx, eax
0x14007226c  mov     [rsp+0C8h+var_98], eax
0x140072270  cmp     eax, 0C0000023h
0x140072275  jnz     short loc_1400722C8
0x140072277  mov     [rsp+0C8h+var_98], r13d
0x14007227c  mov     edx, [rsp+0C8h+BufferLength]; NumberOfBytes
0x140072280  lea     ecx, [r13+1]; PoolType
0x140072284  mov     r8d, 73666C43h; Tag
0x14007228a  call    cs:__imp_ExAllocatePoolWithTag
0x140072291  nop     dword ptr [rax+rax+00h]
0x140072296  mov     [r15], rax
0x140072299  test    rax, rax
0x14007229c  jz      short loc_1400722BF
0x14007229e  lea     r8, [rsp+0C8h+BufferLength]; BufferLength
0x1400722a3  mov     rdx, rax; SelfRelativeSecurityDescriptor
0x1400722a6  lea     rcx, [rsp+0C8h+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x1400722ab  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x1400722b2  nop     dword ptr [rax+rax+00h]
0x1400722b7  mov     ebx, eax
0x1400722b9  mov     [rsp+0C8h+var_98], eax
0x1400722bd  jmp     short loc_1400722C8
0x1400722bf  mov     ebx, 0C000009Ah
0x1400722c4  mov     [rsp+0C8h+var_98], ebx
0x1400722c8  test    ebx, ebx
0x1400722ca  js      short loc_140072332
0x1400722cc  test    rdi, rdi
0x1400722cf  jnz     short loc_140072350
0x1400722d1  test    r12, r12
0x1400722d4  jz      short loc_1400722E7
0x1400722d6  xor     edx, edx; Tag
0x1400722d8  mov     rcx, r12; P
0x1400722db  call    cs:__imp_ExFreePoolWithTag
0x1400722e2  nop     dword ptr [rax+rax+00h]
0x1400722e7  test    r14, r14
0x1400722ea  jz      short loc_1400722FD
0x1400722ec  xor     edx, edx; Tag
0x1400722ee  mov     rcx, r14; P
0x1400722f1  call    cs:__imp_ExFreePoolWithTag
0x1400722f8  nop     dword ptr [rax+rax+00h]
0x1400722fd  test    rsi, rsi
0x140072300  jnz     short loc_140072366
0x140072302  mov     eax, ebx
0x140072304  mov     rcx, [rsp+0C8h+var_38]
0x14007230c  xor     rcx, rsp; StackCookie
0x14007230f  call    __security_check_cookie
0x140072314  lea     r11, [rsp+0C8h+var_28]
0x14007231c  mov     rbx, [r11+30h]
0x140072320  mov     rsi, [r11+40h]
0x140072324  mov     rsp, r11
0x140072327  pop     r15
0x140072329  pop     r14
0x14007232b  pop     r13
0x14007232d  pop     r12
0x14007232f  pop     rdi
0x140072330  retn
0x140072332  mov     rcx, [r15]; P
0x140072335  test    rcx, rcx
0x140072338  jz      short loc_1400722CC
0x14007233a  xor     edx, edx; Tag
0x14007233c  call    cs:__imp_ExFreePoolWithTag
0x140072343  nop     dword ptr [rax+rax+00h]
0x140072348  mov     [r15], r13
0x14007234b  jmp     loc_1400722CC
0x140072350  xor     edx, edx; Tag
0x140072352  mov     rcx, rdi; P
0x140072355  call    cs:__imp_ExFreePoolWithTag
0x14007235c  nop     dword ptr [rax+rax+00h]
0x140072361  jmp     loc_1400722D1
0x140072366  xor     edx, edx; Tag
0x140072368  mov     rcx, rsi; P
0x14007236b  call    cs:__imp_ExFreePoolWithTag
0x140072372  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
