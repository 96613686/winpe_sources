# NpCreateDefaultRootSecurity

- ea: `0x140015f4c`
- end: `0x140016123`
- name: `NpCreateDefaultRootSecurity`
- size: `471`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140015bf8`

## callees

- `0x140015f4c`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140015faf`
- `ntoskrnl!ExAllocatePool2` at `0x14001609a`
- `ntoskrnl!ExAllocatePool2` at `0x140015faf`
- `ntoskrnl!ExAllocatePool2` at `0x14001609a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400160b3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400160e0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001610b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400160b3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400160e0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001610b`
- `ntoskrnl!SeExports` at `0x140015f82`
- `ntoskrnl!SeExports` at `0x140015fe4`
- `ntoskrnl!SeExports` at `0x140016027`
- `ntoskrnl!SeExports` at `0x14001604b`
- `ntoskrnl!ObLogSecurityDescriptor` at `0x1400160f8`
- `ntoskrnl!ObLogSecurityDescriptor` at `0x1400160f8`
- `ntoskrnl!RtlSetOwnerSecurityDescriptor` at `0x14001603f`
- `ntoskrnl!RtlSetOwnerSecurityDescriptor` at `0x14001603f`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14001601b`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14001601b`
- `ntoskrnl!RtlLengthSid` at `0x140015f93`
- `ntoskrnl!RtlLengthSid` at `0x140015f93`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140016003`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140016003`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x140016080`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x1400160cf`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x140016080`
- `ntoskrnl!RtlAbsoluteToSelfRelativeSD` at `0x1400160cf`
- `ntoskrnl!RtlCreateAcl` at `0x140015fd8`
- `ntoskrnl!RtlCreateAcl` at `0x140015fd8`
- `ntoskrnl!RtlSetGroupSecurityDescriptor` at `0x140016063`
- `ntoskrnl!RtlSetGroupSecurityDescriptor` at `0x140016063`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140015f76`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x140015f76`

## pseudocode

```c
__int64 __fastcall NpCreateDefaultRootSecurity(__int64 a1)
{
  ULONG v2; // edi
  struct _ACL *Pool2; // rax
  struct _ACL *v4; // rbx
  void *v6; // rax
  void *v7; // rdi
  unsigned int v8; // ebx
  _OWORD SecurityDescriptor[2]; // [rsp+20h] [rbp-38h] BYREF
  __int64 v10; // [rsp+40h] [rbp-18h]
  ULONG BufferLength; // [rsp+88h] [rbp+30h] BYREF

  v10 = 0;
  BufferLength = 0;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
  v2 = RtlLengthSid(SeExports->SeWorldSid) + 20;
  Pool2 = (struct _ACL *)ExAllocatePool2(256, v2, 1818452292);
  v4 = Pool2;
  if ( !Pool2 )
    return 3221225626LL;
  RtlCreateAcl(Pool2, v2, 2u);
  RtlAddAccessAllowedAce(v4, 2u, 0x1F01FBu, SeExports->SeWorldSid);
  RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, v4, 0);
  RtlSetOwnerSecurityDescriptor(SecurityDescriptor, SeExports->SeLocalSystemSid, 0);
  RtlSetGroupSecurityDescriptor(SecurityDescriptor, SeExports->SeLocalSystemSid, 0);
  BufferLength = 0;
  RtlAbsoluteToSelfRelativeSD(SecurityDescriptor, 0, &BufferLength);
  v6 = (void *)ExAllocatePool2(256, BufferLength, 1683189838);
  v7 = v6;
  if ( !v6 )
  {
    ExFreePoolWithTag(v4, 0);
    return 3221225626LL;
  }
  RtlAbsoluteToSelfRelativeSD(SecurityDescriptor, v6, &BufferLength);
  ExFreePoolWithTag(v4, 0);
  v8 = ObLogSecurityDescriptor(v7, a1, 1);
  ExFreePoolWithTag(v7, 0);
  return v8;
}

```

## disassembly

```asm
0x140015f4c  push    rbp
0x140015f4e  push    rbx
0x140015f4f  push    rsi
0x140015f50  push    rdi
0x140015f51  mov     rbp, rsp
0x140015f54  sub     rsp, 58h
0x140015f58  xor     eax, eax
0x140015f5a  xorps   xmm0, xmm0
0x140015f5d  mov     rsi, rcx
0x140015f60  mov     [rbp+var_18], rax
0x140015f64  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x140015f68  mov     [rbp+BufferLength], eax
0x140015f6b  movups  [rbp+SecurityDescriptor], xmm0
0x140015f6f  lea     edx, [rax+1]; Revision
0x140015f72  movups  [rbp+var_28], xmm0
0x140015f76  call    cs:__imp_RtlCreateSecurityDescriptor
0x140015f7d  nop     dword ptr [rax+rax+00h]
0x140015f82  mov     rax, cs:__imp_SeExports
0x140015f89  mov     rcx, [rax]
0x140015f8c  mov     rcx, [rcx+0C0h]; Sid
0x140015f93  call    cs:__imp_RtlLengthSid
0x140015f9a  nop     dword ptr [rax+rax+00h]
0x140015f9f  mov     ecx, 100h
0x140015fa4  mov     r8d, 6C636144h
0x140015faa  lea     edi, [rax+14h]
0x140015fad  mov     edx, edi
0x140015faf  call    cs:__imp_ExAllocatePool2
0x140015fb6  nop     dword ptr [rax+rax+00h]
0x140015fbb  mov     rbx, rax
0x140015fbe  test    rax, rax
0x140015fc1  jnz     short loc_140015FCD
0x140015fc3  mov     eax, 0C000009Ah
0x140015fc8  jmp     loc_140016119
0x140015fcd  mov     r8d, 2; AclRevision
0x140015fd3  mov     edx, edi; AclLength
0x140015fd5  mov     rcx, rbx; Acl
0x140015fd8  call    cs:__imp_RtlCreateAcl
0x140015fdf  nop     dword ptr [rax+rax+00h]
0x140015fe4  mov     rax, cs:__imp_SeExports
0x140015feb  mov     edx, 2; AceRevision
0x140015ff0  mov     r8d, 1F01FBh; AccessMask
0x140015ff6  mov     rcx, rbx; Acl
0x140015ff9  mov     r9, [rax]
0x140015ffc  mov     r9, [r9+0C0h]; Sid
0x140016003  call    cs:__imp_RtlAddAccessAllowedAce
0x14001600a  nop     dword ptr [rax+rax+00h]
0x14001600f  xor     r9d, r9d; DaclDefaulted
0x140016012  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x140016016  mov     r8, rbx; Dacl
0x140016019  mov     dl, 1; DaclPresent
0x14001601b  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x140016022  nop     dword ptr [rax+rax+00h]
0x140016027  mov     rax, cs:__imp_SeExports
0x14001602e  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x140016032  xor     r8d, r8d; OwnerDefaulted
0x140016035  mov     rdx, [rax]
0x140016038  mov     rdx, [rdx+108h]; Owner
0x14001603f  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x140016046  nop     dword ptr [rax+rax+00h]
0x14001604b  mov     rax, cs:__imp_SeExports
0x140016052  lea     rcx, [rbp+SecurityDescriptor]; SecurityDescriptor
0x140016056  xor     r8d, r8d; GroupDefaulted
0x140016059  mov     rdx, [rax]
0x14001605c  mov     rdx, [rdx+108h]; Group
0x140016063  call    cs:__imp_RtlSetGroupSecurityDescriptor
0x14001606a  nop     dword ptr [rax+rax+00h]
0x14001606f  lea     r8, [rbp+BufferLength]; BufferLength
0x140016073  mov     [rbp+BufferLength], 0
0x14001607a  xor     edx, edx; SelfRelativeSecurityDescriptor
0x14001607c  lea     rcx, [rbp+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x140016080  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x140016087  nop     dword ptr [rax+rax+00h]
0x14001608c  mov     edx, [rbp+BufferLength]
0x14001608f  mov     ecx, 100h
0x140016094  mov     r8d, 6453704Eh
0x14001609a  call    cs:__imp_ExAllocatePool2
0x1400160a1  nop     dword ptr [rax+rax+00h]
0x1400160a6  mov     rdi, rax
0x1400160a9  test    rax, rax
0x1400160ac  jnz     short loc_1400160C4
0x1400160ae  xor     edx, edx; Tag
0x1400160b0  mov     rcx, rbx; P
0x1400160b3  call    cs:__imp_ExFreePoolWithTag
0x1400160ba  nop     dword ptr [rax+rax+00h]
0x1400160bf  jmp     loc_140015FC3
0x1400160c4  lea     r8, [rbp+BufferLength]; BufferLength
0x1400160c8  mov     rdx, rdi; SelfRelativeSecurityDescriptor
0x1400160cb  lea     rcx, [rbp+SecurityDescriptor]; AbsoluteSecurityDescriptor
0x1400160cf  call    cs:__imp_RtlAbsoluteToSelfRelativeSD
0x1400160d6  nop     dword ptr [rax+rax+00h]
0x1400160db  xor     edx, edx; Tag
0x1400160dd  mov     rcx, rbx; P
0x1400160e0  call    cs:__imp_ExFreePoolWithTag
0x1400160e7  nop     dword ptr [rax+rax+00h]
0x1400160ec  mov     r8d, 1
0x1400160f2  mov     rdx, rsi
0x1400160f5  mov     rcx, rdi
0x1400160f8  call    cs:__imp_ObLogSecurityDescriptor
0x1400160ff  nop     dword ptr [rax+rax+00h]
0x140016104  xor     edx, edx; Tag
0x140016106  mov     rcx, rdi; P
0x140016109  mov     ebx, eax
0x14001610b  call    cs:__imp_ExFreePoolWithTag
0x140016112  nop     dword ptr [rax+rax+00h]
0x140016117  mov     eax, ebx
0x140016119  add     rsp, 58h
0x14001611d  pop     rdi
0x14001611e  pop     rsi
0x14001611f  pop     rbx
0x140016120  pop     rbp
0x140016121  retn
```
