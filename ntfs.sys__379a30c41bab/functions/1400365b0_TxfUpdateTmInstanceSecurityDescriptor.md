# TxfUpdateTmInstanceSecurityDescriptor

- ea: `0x1400365b0`
- end: `0x140036ca9`
- name: `TxfUpdateTmInstanceSecurityDescriptor`
- size: `1785`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14025a318`

## callees

- `0x1400365b0`
- `0x1400592c0`
- `0x140059440`
- `0x140059740`

## import_xrefs

- `ntoskrnl!RtlLengthRequiredSid` at `0x1400367b9`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1400367b9`
- `ntoskrnl!RtlInitializeSid` at `0x1400367fb`
- `ntoskrnl!RtlInitializeSid` at `0x1400367fb`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140036823`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140036823`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1400368c3`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1400368c3`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140036b31`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140036b31`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x14003679c`
- `ntoskrnl!RtlGetDaclSecurityDescriptor` at `0x14003679c`
- `ntoskrnl!ZwQuerySecurityObject` at `0x1400366e0`
- `ntoskrnl!ZwQuerySecurityObject` at `0x140036771`
- `ntoskrnl!ZwQuerySecurityObject` at `0x1400366e0`
- `ntoskrnl!ZwQuerySecurityObject` at `0x140036771`
- `ntoskrnl!RtlValidRelativeSecurityDescriptor` at `0x1400368e3`
- `ntoskrnl!RtlValidRelativeSecurityDescriptor` at `0x1400368e3`
- `ntoskrnl!RtlSelfRelativeToAbsoluteSD` at `0x14003693d`
- `ntoskrnl!RtlSelfRelativeToAbsoluteSD` at `0x140036ad3`
- `ntoskrnl!RtlSelfRelativeToAbsoluteSD` at `0x14003693d`
- `ntoskrnl!RtlSelfRelativeToAbsoluteSD` at `0x140036ad3`
- `ntoskrnl!ZwSetSecurityObject` at `0x140036b62`
- `ntoskrnl!ZwSetSecurityObject` at `0x140036b62`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400366fe`
- `ntoskrnl!ExFreePoolWithTag` at `0x140036aee`
- `ntoskrnl!ExFreePoolWithTag` at `0x140036c01`
- `ntoskrnl!ExFreePoolWithTag` at `0x140036c17`
- `ntoskrnl!ExFreePoolWithTag` at `0x140036c2d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140036c43`
- `ntoskrnl!ExFreePoolWithTag` at `0x140036c56`
- `ntoskrnl!ExFreePoolWithTag` at `0x140036c6c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140036c82`
- `ntoskrnl!ExFreePoolWithTag` at `0x140036c98`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005b98e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005b9a9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005b9c4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005b9df`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005b9fa`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005ba15`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005ba30`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005ba4b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400366fe`
- `ntoskrnl!ExFreePoolWithTag` at `0x140036aee`
- `ntoskrnl!ExFreePoolWithTag` at `0x140036c01`
- `ntoskrnl!ExFreePoolWithTag` at `0x140036c17`
- `ntoskrnl!ExFreePoolWithTag` at `0x140036c2d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140036c43`
- `ntoskrnl!ExFreePoolWithTag` at `0x140036c56`
- `ntoskrnl!ExFreePoolWithTag` at `0x140036c6c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140036c82`
- `ntoskrnl!ExFreePoolWithTag` at `0x140036c98`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005b98e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005b9a9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005b9c4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005b9df`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005b9fa`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005ba15`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005ba30`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005ba4b`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003669c`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140036725`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400367d6`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003686d`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003696b`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400369a7`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400369e3`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140036a1f`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140036a68`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003669c`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140036725`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400367d6`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003686d`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003696b`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400369a7`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400369e3`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140036a1f`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140036a68`

## pseudocode

```c
__int64 __fastcall TxfUpdateTmInstanceSecurityDescriptor(__int64 a1)
{
  PVOID v2; // rsi
  unsigned __int8 *v3; // r14
  struct _ACL *v4; // r15
  struct _ACL *Sacl; // r13
  PVOID PrimaryGroup; // r12
  PVOID PoolWithTag; // rdi
  NTSTATUS DaclSecurityDescriptor; // ebx
  ULONG v9; // eax
  unsigned __int16 i; // bx
  unsigned int v11; // ebx
  struct _ACL *v12; // rax
  PVOID Owner; // rbx
  ULONG Size; // [rsp+60h] [rbp-C8h] BYREF
  _WORD Size_4[2]; // [rsp+64h] [rbp-C4h] BYREF
  ULONG AbsoluteSecurityDescriptorSize; // [rsp+68h] [rbp-C0h] BYREF
  ULONG PrimaryGroupSize; // [rsp+6Ch] [rbp-BCh] BYREF
  ULONG OwnerSize; // [rsp+70h] [rbp-B8h] BYREF
  ULONG SaclSize; // [rsp+74h] [rbp-B4h] BYREF
  ULONG DaclSize; // [rsp+78h] [rbp-B0h] BYREF
  PACL Acl; // [rsp+80h] [rbp-A8h]
  PVOID v23; // [rsp+88h] [rbp-A0h]
  PVOID v24; // [rsp+90h] [rbp-98h]
  PVOID P; // [rsp+98h] [rbp-90h]
  PACL Dacl; // [rsp+A0h] [rbp-88h] BYREF
  __int64 v27; // [rsp+A8h] [rbp-80h]
  struct _ACL *v28; // [rsp+B0h] [rbp-78h]
  struct _ACL *v29; // [rsp+B8h] [rbp-70h]
  PVOID v30; // [rsp+C0h] [rbp-68h]
  unsigned __int8 *v31; // [rsp+C8h] [rbp-60h]
  _DWORD v32[6]; // [rsp+D0h] [rbp-58h]
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+E8h] [rbp-40h] BYREF

  v27 = a1;
  v2 = 0;
  v24 = 0;
  AbsoluteSecurityDescriptorSize = 0;
  Dacl = 0;
  Size_4[0] = 0;
  Acl = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  v3 = 0;
  v31 = 0;
  v32[0] = 80;
  v32[1] = -1476609712;
  v32[2] = -907901543;
  v32[3] = -294573354;
  v32[4] = 342927828;
  v32[5] = 138088443;
  v4 = 0;
  v28 = 0;
  Sacl = 0;
  v29 = 0;
  P = 0;
  PrimaryGroup = 0;
  v30 = 0;
  DaclSize = 0;
  SaclSize = 0;
  OwnerSize = 0;
  PrimaryGroupSize = 0;
  Size = 40;
  PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), 0x28u, 0x30667854u);
  v23 = PoolWithTag;
  memset(PoolWithTag, 0, 0x28u);
  DaclSecurityDescriptor = ZwQuerySecurityObject(*(HANDLE *)(a1 + 664), 4u, PoolWithTag, 0x28u, &Size);
  if ( DaclSecurityDescriptor == -1073741789 )
  {
    ExFreePoolWithTag(PoolWithTag, 0);
    v23 = 0;
    PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), Size, 0x30667854u);
    v23 = PoolWithTag;
    memset(PoolWithTag, 0, Size);
    DaclSecurityDescriptor = ZwQuerySecurityObject(*(HANDLE *)(v27 + 664), 4u, PoolWithTag, Size, &Size);
  }
  if ( DaclSecurityDescriptor >= 0 )
  {
    DaclSecurityDescriptor = RtlGetDaclSecurityDescriptor(PoolWithTag, (PBOOLEAN)Size_4 + 1, &Dacl, (PBOOLEAN)Size_4);
    if ( DaclSecurityDescriptor >= 0 )
    {
      v9 = RtlLengthRequiredSid(6u);
      v3 = (unsigned __int8 *)ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), v9, 0x30667854u);
      v31 = v3;
      DaclSecurityDescriptor = RtlInitializeSid(v3, &IdentifierAuthority, 6u);
      if ( DaclSecurityDescriptor >= 0 )
      {
        for ( i = 0; i < 6u; ++i )
          *RtlSubAuthoritySid(v3, i) = v32[i];
        v11 = (unsigned __int16)(Dacl->AclSize + 4 * (v3[1] + 5));
        Acl = (PACL)ExAllocatePoolWithTag(
                      (POOL_TYPE)(PoolType | 0x10),
                      (unsigned __int16)(Dacl->AclSize + 4 * (v3[1] + 5)),
                      0x30667854u);
        memset(Acl, 0, v11);
        memmove(Acl, Dacl, Dacl->AclSize);
        v12 = Acl;
        Acl->AclSize = v11;
        DaclSecurityDescriptor = RtlAddAccessAllowedAce(v12, v12->AclRevision, 0x10000000u, v3);
        if ( DaclSecurityDescriptor >= 0 )
        {
          if ( !RtlValidRelativeSecurityDescriptor(PoolWithTag, Size, 0) )
            goto LABEL_23;
          DaclSecurityDescriptor = RtlSelfRelativeToAbsoluteSD(
                                     PoolWithTag,
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
          if ( DaclSecurityDescriptor == -1073741789 )
          {
            v2 = ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), AbsoluteSecurityDescriptorSize, 0x30667854u);
            v24 = v2;
            memset(v2, 0, AbsoluteSecurityDescriptorSize);
            if ( DaclSize )
            {
              v4 = (struct _ACL *)ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), DaclSize, 0x30667854u);
              v28 = v4;
              memset(v4, 0, DaclSize);
            }
            if ( SaclSize )
            {
              Sacl = (struct _ACL *)ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), SaclSize, 0x30667854u);
              v29 = Sacl;
              memset(Sacl, 0, SaclSize);
            }
            if ( OwnerSize )
            {
              Owner = ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), OwnerSize, 0x30667854u);
              P = Owner;
              memset(Owner, 0, OwnerSize);
            }
            else
            {
              Owner = P;
            }
            if ( PrimaryGroupSize )
            {
              PrimaryGroup = ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), PrimaryGroupSize, 0x30667854u);
              v30 = PrimaryGroup;
              memset(PrimaryGroup, 0, PrimaryGroupSize);
            }
            DaclSecurityDescriptor = RtlSelfRelativeToAbsoluteSD(
                                       PoolWithTag,
                                       v2,
                                       &AbsoluteSecurityDescriptorSize,
                                       v4,
                                       &DaclSize,
                                       Sacl,
                                       &SaclSize,
                                       Owner,
                                       &OwnerSize,
                                       PrimaryGroup,
                                       &PrimaryGroupSize);
            if ( DaclSecurityDescriptor >= 0 )
            {
              ExFreePoolWithTag(PoolWithTag, 0);
              PoolWithTag = v2;
              v23 = v2;
              Size = AbsoluteSecurityDescriptorSize;
              v24 = 0;
              AbsoluteSecurityDescriptorSize = 0;
LABEL_23:
              DaclSecurityDescriptor = RtlSetDaclSecurityDescriptor(PoolWithTag, 1u, Acl, 0);
              v2 = 0;
              v24 = 0;
              if ( DaclSecurityDescriptor >= 0 )
              {
                DaclSecurityDescriptor = ZwSetSecurityObject(*(HANDLE *)(v27 + 664), 4u, PoolWithTag);
                v24 = 0;
              }
            }
          }
        }
      }
    }
  }
  if ( PoolWithTag )
    ExFreePoolWithTag(PoolWithTag, 0);
  if ( v2 )
    ExFreePoolWithTag(v2, 0);
  if ( v4 )
    ExFreePoolWithTag(v4, 0);
  if ( Sacl )
    ExFreePoolWithTag(Sacl, 0);
  if ( P )
    ExFreePoolWithTag(P, 0);
  if ( PrimaryGroup )
    ExFreePoolWithTag(PrimaryGroup, 0);
  if ( v3 )
    ExFreePoolWithTag(v3, 0);
  if ( Acl )
    ExFreePoolWithTag(Acl, 0);
  return (unsigned int)DaclSecurityDescriptor;
}

```

## disassembly

```asm
0x1400365b0  mov     r11, rsp
0x1400365b3  mov     [r11+10h], rbx
0x1400365b7  mov     [r11+18h], rsi
0x1400365bb  push    rdi
0x1400365bc  push    r12
0x1400365be  push    r13
0x1400365c0  push    r14
0x1400365c2  push    r15
0x1400365c4  sub     rsp, 100h
0x1400365cb  mov     rax, cs:__security_cookie
0x1400365d2  xor     rax, rsp
0x1400365d5  mov     [rsp+128h+var_38], rax
0x1400365dd  mov     rbx, rcx
0x1400365e0  mov     [rsp+128h+var_80], rcx
0x1400365e8  xor     eax, eax
0x1400365ea  mov     [r11-0A0h], rax
0x1400365f1  mov     dword ptr [rsp+128h+Size], eax
0x1400365f5  mov     esi, eax
0x1400365f7  mov     [r11-98h], rax
0x1400365fe  mov     [rsp+128h+AbsoluteSecurityDescriptorSize], eax
0x140036602  mov     byte ptr [rsp+128h+Size+5], al
0x140036606  mov     [r11-88h], rax
0x14003660d  mov     byte ptr [rsp+128h+Size+4], al
0x140036611  mov     [r11-0A8h], rax
0x140036618  mov     [r11-40h], eax
0x14003661c  mov     word ptr [r11-3Ch], 500h
0x140036623  mov     r14d, eax
0x140036626  mov     [r11-60h], rax
0x14003662a  mov     dword ptr [r11-58h], 50h ; 'P'
0x140036632  mov     dword ptr [r11-54h], 0A7FCB950h
0x14003663a  mov     dword ptr [r11-50h], 0C9E28599h
0x140036642  mov     dword ptr [r11-4Ch], 0EE712AD6h
0x14003664a  mov     dword ptr [r11-48h], 1470A9D4h
0x140036652  mov     dword ptr [r11-44h], 83B0FFBh
0x14003665a  mov     r15d, eax
0x14003665d  mov     [r11-78h], rax
0x140036661  mov     r13d, eax
0x140036664  mov     [r11-70h], rax
0x140036668  mov     [r11-90h], rax
0x14003666f  mov     r12d, eax
0x140036672  mov     [r11-68h], rax
0x140036676  mov     [rsp+128h+DaclSize], eax
0x14003667a  mov     [rsp+128h+var_B4], eax
0x14003667e  mov     [rsp+128h+var_B8], eax
0x140036682  mov     [rsp+128h+var_BC], eax
0x140036686  lea     edx, [rax+28h]; NumberOfBytes
0x140036689  mov     dword ptr [rsp+128h+Size], edx
0x14003668d  mov     ecx, cs:PoolType
0x140036693  or      ecx, 10h; PoolType
0x140036696  mov     r8d, 30667854h; Tag
0x14003669c  call    cs:__imp_ExAllocatePoolWithTag
0x1400366a3  nop     dword ptr [rax+rax+00h]
0x1400366a8  mov     rdi, rax
0x1400366ab  mov     [rsp+128h+var_A0], rax
0x1400366b3  mov     r8d, dword ptr [rsp+128h+Size]; Size
0x1400366b8  xor     edx, edx; Val
0x1400366ba  mov     rcx, rax; void *
0x1400366bd  call    memset
0x1400366c2  lea     rax, [rsp+128h+Size]
0x1400366c7  mov     [rsp+128h+LengthNeeded], rax; LengthNeeded
0x1400366cc  mov     r9d, dword ptr [rsp+128h+Size]; Length
0x1400366d1  mov     r8, rdi; SecurityDescriptor
0x1400366d4  lea     edx, [r12+4]; SecurityInformation
0x1400366d9  mov     rcx, [rbx+298h]; Handle
0x1400366e0  call    cs:__imp_ZwQuerySecurityObject
0x1400366e7  nop     dword ptr [rax+rax+00h]
0x1400366ec  mov     ebx, eax
0x1400366ee  cmp     eax, 0C0000023h
0x1400366f3  jnz     loc_14003677F
0x1400366f9  xor     edx, edx; Tag
0x1400366fb  mov     rcx, rdi; P
0x1400366fe  call    cs:__imp_ExFreePoolWithTag
0x140036705  nop     dword ptr [rax+rax+00h]
0x14003670a  mov     [rsp+128h+var_A0], r12
0x140036712  mov     edx, dword ptr [rsp+128h+Size]; NumberOfBytes
0x140036716  mov     ecx, cs:PoolType
0x14003671c  or      ecx, 10h; PoolType
0x14003671f  mov     r8d, 30667854h; Tag
0x140036725  call    cs:__imp_ExAllocatePoolWithTag
0x14003672c  nop     dword ptr [rax+rax+00h]
0x140036731  mov     rdi, rax
0x140036734  mov     [rsp+128h+var_A0], rax
0x14003673c  mov     r8d, dword ptr [rsp+128h+Size]; Size
0x140036741  xor     edx, edx; Val
0x140036743  mov     rcx, rax; void *
0x140036746  call    memset
0x14003674b  lea     rax, [rsp+128h+Size]
0x140036750  mov     [rsp+128h+LengthNeeded], rax; LengthNeeded
0x140036755  mov     r9d, dword ptr [rsp+128h+Size]; Length
0x14003675a  mov     r8, rdi; SecurityDescriptor
0x14003675d  lea     edx, [r12+4]; SecurityInformation
0x140036762  mov     rcx, [rsp+128h+var_80]
0x14003676a  mov     rcx, [rcx+298h]; Handle
0x140036771  call    cs:__imp_ZwQuerySecurityObject
0x140036778  nop     dword ptr [rax+rax+00h]
0x14003677d  mov     ebx, eax
0x14003677f  test    ebx, ebx
0x140036781  js      loc_140036B78
0x140036787  lea     r9, [rsp+128h+Size+4]; DaclDefaulted
0x14003678c  lea     r8, [rsp+128h+Dacl]; Dacl
0x140036794  lea     rdx, [rsp+128h+Size+5]; DaclPresent
0x140036799  mov     rcx, rdi; SecurityDescriptor
0x14003679c  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x1400367a3  nop     dword ptr [rax+rax+00h]
0x1400367a8  mov     ebx, eax
0x1400367aa  test    eax, eax
0x1400367ac  js      loc_140036B78
0x1400367b2  mov     ebx, 6
0x1400367b7  mov     ecx, ebx; SubAuthorityCount
0x1400367b9  call    cs:__imp_RtlLengthRequiredSid
0x1400367c0  nop     dword ptr [rax+rax+00h]
0x1400367c5  mov     edx, eax; NumberOfBytes
0x1400367c7  mov     ecx, cs:PoolType
0x1400367cd  or      ecx, 10h; PoolType
0x1400367d0  mov     r8d, 30667854h; Tag
0x1400367d6  call    cs:__imp_ExAllocatePoolWithTag
0x1400367dd  nop     dword ptr [rax+rax+00h]
0x1400367e2  mov     r14, rax
0x1400367e5  mov     [rsp+128h+var_60], rax
0x1400367ed  mov     r8b, bl; SubAuthorityCount
0x1400367f0  lea     rdx, [rsp+128h+IdentifierAuthority]; IdentifierAuthority
0x1400367f8  mov     rcx, rax; Sid
0x1400367fb  call    cs:__imp_RtlInitializeSid
0x140036802  nop     dword ptr [rax+rax+00h]
0x140036807  mov     ebx, eax
0x140036809  test    eax, eax
0x14003680b  js      loc_140036B78
0x140036811  xor     ebx, ebx
0x140036813  mov     eax, 6
0x140036818  cmp     bx, ax
0x14003681b  jnb     short loc_140036840
0x14003681d  movzx   edx, bx; SubAuthority
0x140036820  mov     rcx, r14; Sid
0x140036823  call    cs:__imp_RtlSubAuthoritySid
0x14003682a  nop     dword ptr [rax+rax+00h]
0x14003682f  movzx   ecx, bx
0x140036832  mov     edx, [rsp+rcx*4+128h+var_58]
0x140036839  mov     [rax], edx
0x14003683b  inc     bx
0x14003683e  jmp     short loc_140036813
0x140036840  movzx   ecx, byte ptr [r14+1]
0x140036845  add     cx, 5
0x140036849  shl     cx, 2
0x14003684d  mov     rax, [rsp+128h+Dacl]
0x140036855  add     cx, [rax+2]
0x140036859  movzx   ebx, cx
0x14003685c  mov     ecx, cs:PoolType
0x140036862  or      ecx, 10h; PoolType
0x140036865  mov     r8d, 30667854h; Tag
0x14003686b  mov     edx, ebx; NumberOfBytes
0x14003686d  call    cs:__imp_ExAllocatePoolWithTag
0x140036874  nop     dword ptr [rax+rax+00h]
0x140036879  mov     [rsp+128h+Acl], rax
0x140036881  mov     r8d, ebx; Size
0x140036884  xor     edx, edx; Val
0x140036886  mov     rcx, rax; void *
0x140036889  call    memset
0x14003688e  mov     rdx, [rsp+128h+Dacl]; Src
0x140036896  movzx   r8d, word ptr [rdx+2]; Size
0x14003689b  mov     rcx, [rsp+128h+Acl]; void *
0x1400368a3  call    memmove
0x1400368a8  mov     rax, [rsp+128h+Acl]
0x1400368b0  mov     [rax+2], bx
0x1400368b4  movzx   edx, byte ptr [rax]; AceRevision
0x1400368b7  mov     r9, r14; Sid
0x1400368ba  mov     r8d, 10000000h; AccessMask
0x1400368c0  mov     rcx, rax; Acl
0x1400368c3  call    cs:__imp_RtlAddAccessAllowedAce
0x1400368ca  nop     dword ptr [rax+rax+00h]
0x1400368cf  mov     ebx, eax
0x1400368d1  test    eax, eax
0x1400368d3  js      loc_140036B78
0x1400368d9  xor     r8d, r8d; RequiredInformation
0x1400368dc  mov     edx, dword ptr [rsp+128h+Size]; SecurityDescriptorLength
0x1400368e0  mov     rcx, rdi; SecurityDescriptorInput
0x1400368e3  call    cs:__imp_RtlValidRelativeSecurityDescriptor
0x1400368ea  nop     dword ptr [rax+rax+00h]
0x1400368ef  xor     ecx, ecx
0x1400368f1  test    al, al
0x1400368f3  jz      loc_140036B21
0x1400368f9  lea     rax, [rsp+128h+var_BC]
0x1400368fe  mov     [rsp+128h+PrimaryGroupSize], rax; PrimaryGroupSize
0x140036903  mov     [rsp+128h+PrimaryGroup], rcx; PrimaryGroup
0x140036908  lea     rax, [rsp+128h+var_B8]
0x14003690d  mov     [rsp+128h+OwnerSize], rax; OwnerSize
0x140036912  mov     [rsp+128h+Owner], rcx; Owner
0x140036917  lea     rax, [rsp+128h+var_B4]
0x14003691c  mov     [rsp+128h+SaclSize], rax; SaclSize
0x140036921  mov     [rsp+128h+Sacl], rcx; Sacl
0x140036926  lea     rax, [rsp+128h+DaclSize]
0x14003692b  mov     [rsp+128h+LengthNeeded], rax; DaclSize
0x140036930  xor     r9d, r9d; Dacl
0x140036933  lea     r8, [rsp+128h+AbsoluteSecurityDescriptorSize]; AbsoluteSecurityDescriptorSize
0x140036938  xor     edx, edx; AbsoluteSecurityDescriptor
0x14003693a  mov     rcx, rdi; SelfRelativeSecurityDescriptor
0x14003693d  call    cs:__imp_RtlSelfRelativeToAbsoluteSD
0x140036944  nop     dword ptr [rax+rax+00h]
0x140036949  mov     ebx, eax
0x14003694b  cmp     eax, 0C0000023h
0x140036950  jnz     loc_140036B78
0x140036956  mov     edx, [rsp+128h+AbsoluteSecurityDescriptorSize]; NumberOfBytes
0x14003695a  mov     ecx, cs:PoolType
0x140036960  or      ecx, 10h; PoolType
0x140036963  mov     ebx, 30667854h
0x140036968  mov     r8d, ebx; Tag
0x14003696b  call    cs:__imp_ExAllocatePoolWithTag
0x140036972  nop     dword ptr [rax+rax+00h]
0x140036977  mov     rsi, rax
0x14003697a  mov     [rsp+128h+var_98], rax
0x140036982  mov     r8d, [rsp+128h+AbsoluteSecurityDescriptorSize]; Size
0x140036987  xor     edx, edx; Val
0x140036989  mov     rcx, rax; void *
0x14003698c  call    memset
0x140036991  mov     eax, [rsp+128h+DaclSize]
0x140036995  test    eax, eax
0x140036997  jz      short loc_1400369CD
0x140036999  mov     edx, eax; NumberOfBytes
0x14003699b  mov     ecx, cs:PoolType
0x1400369a1  or      ecx, 10h; PoolType
0x1400369a4  mov     r8d, ebx; Tag
0x1400369a7  call    cs:__imp_ExAllocatePoolWithTag
0x1400369ae  nop     dword ptr [rax+rax+00h]
0x1400369b3  mov     r15, rax
0x1400369b6  mov     [rsp+128h+var_78], rax
0x1400369be  mov     r8d, [rsp+128h+DaclSize]; Size
0x1400369c3  xor     edx, edx; Val
0x1400369c5  mov     rcx, rax; void *
0x1400369c8  call    memset
0x1400369cd  mov     eax, [rsp+128h+var_B4]
0x1400369d1  test    eax, eax
0x1400369d3  jz      short loc_140036A09
0x1400369d5  mov     edx, eax; NumberOfBytes
0x1400369d7  mov     ecx, cs:PoolType
0x1400369dd  or      ecx, 10h; PoolType
0x1400369e0  mov     r8d, ebx; Tag
0x1400369e3  call    cs:__imp_ExAllocatePoolWithTag
0x1400369ea  nop     dword ptr [rax+rax+00h]
0x1400369ef  mov     r13, rax
0x1400369f2  mov     [rsp+128h+var_70], rax
0x1400369fa  mov     r8d, [rsp+128h+var_B4]; Size
0x1400369ff  xor     edx, edx; Val
0x140036a01  mov     rcx, rax; void *
0x140036a04  call    memset
0x140036a09  mov     eax, [rsp+128h+var_B8]
0x140036a0d  test    eax, eax
0x140036a0f  jz      short loc_140036A47
0x140036a11  mov     edx, eax; NumberOfBytes
0x140036a13  mov     ecx, cs:PoolType
0x140036a19  or      ecx, 10h; PoolType
0x140036a1c  mov     r8d, ebx; Tag
0x140036a1f  call    cs:__imp_ExAllocatePoolWithTag
0x140036a26  nop     dword ptr [rax+rax+00h]
0x140036a2b  mov     rbx, rax
0x140036a2e  mov     [rsp+128h+P], rax
0x140036a36  mov     r8d, [rsp+128h+var_B8]; Size
0x140036a3b  xor     edx, edx; Val
0x140036a3d  mov     rcx, rax; void *
0x140036a40  call    memset
0x140036a45  jmp     short loc_140036A4F
0x140036a47  mov     rbx, [rsp+128h+P]
0x140036a4f  mov     eax, [rsp+128h+var_BC]
0x140036a53  test    eax, eax
0x140036a55  jz      short loc_140036A8E
0x140036a57  mov     edx, eax; NumberOfBytes
0x140036a59  mov     ecx, cs:PoolType
0x140036a5f  or      ecx, 10h; PoolType
0x140036a62  mov     r8d, 30667854h; Tag
0x140036a68  call    cs:__imp_ExAllocatePoolWithTag
0x140036a6f  nop     dword ptr [rax+rax+00h]
0x140036a74  mov     r12, rax
0x140036a77  mov     [rsp+128h+var_68], rax
0x140036a7f  mov     r8d, [rsp+128h+var_BC]; Size
0x140036a84  xor     edx, edx; Val
0x140036a86  mov     rcx, rax; void *
0x140036a89  call    memset
0x140036a8e  lea     rax, [rsp+128h+var_BC]
0x140036a93  mov     [rsp+128h+PrimaryGroupSize], rax; PrimaryGroupSize
0x140036a98  mov     [rsp+128h+PrimaryGroup], r12; PrimaryGroup
0x140036a9d  lea     rax, [rsp+128h+var_B8]
0x140036aa2  mov     [rsp+128h+OwnerSize], rax; OwnerSize
0x140036aa7  mov     [rsp+128h+Owner], rbx; Owner
0x140036aac  lea     rax, [rsp+128h+var_B4]
0x140036ab1  mov     [rsp+128h+SaclSize], rax; SaclSize
0x140036ab6  mov     [rsp+128h+Sacl], r13; Sacl
0x140036abb  lea     rax, [rsp+128h+DaclSize]
0x140036ac0  mov     [rsp+128h+LengthNeeded], rax; DaclSize
0x140036ac5  mov     r9, r15; Dacl
0x140036ac8  lea     r8, [rsp+128h+AbsoluteSecurityDescriptorSize]; AbsoluteSecurityDescriptorSize
0x140036acd  mov     rdx, rsi; AbsoluteSecurityDescriptor
0x140036ad0  mov     rcx, rdi; SelfRelativeSecurityDescriptor
0x140036ad3  call    cs:__imp_RtlSelfRelativeToAbsoluteSD
0x140036ada  nop     dword ptr [rax+rax+00h]
0x140036adf  mov     ebx, eax
0x140036ae1  test    eax, eax
0x140036ae3  js      loc_140036B78
0x140036ae9  xor     edx, edx; Tag
0x140036aeb  mov     rcx, rdi; P
0x140036aee  call    cs:__imp_ExFreePoolWithTag
0x140036af5  nop     dword ptr [rax+rax+00h]
0x140036afa  mov     rdi, rsi
  ... truncated ...
```
