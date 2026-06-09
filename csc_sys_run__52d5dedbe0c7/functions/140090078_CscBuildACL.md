# CscBuildACL

- ea: `0x140090078`
- end: `0x1400901ba`
- name: `CscBuildACL`
- size: `322`
- prototype: `__int64 __fastcall(PSID Sid, struct _ACL **)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140090740`

## callees

- `0x140018930`
- `0x140090078`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400900a8`
- `ntoskrnl!ExAllocatePool2` at `0x1400900a8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140090169`
- `ntoskrnl!ExFreePoolWithTag` at `0x140090169`
- `ntoskrnl!RtlSetOwnerSecurityDescriptor` at `0x1400900e7`
- `ntoskrnl!RtlSetOwnerSecurityDescriptor` at `0x1400900e7`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140090152`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x140090152`
- `ntoskrnl!RtlLengthSid` at `0x140090089`
- `ntoskrnl!RtlLengthSid` at `0x140090089`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140090135`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140090135`
- `ntoskrnl!RtlCreateAcl` at `0x140090114`
- `ntoskrnl!RtlCreateAcl` at `0x140090114`
- `ntoskrnl!RtlSetGroupSecurityDescriptor` at `0x1400900fc`
- `ntoskrnl!RtlSetGroupSecurityDescriptor` at `0x1400900fc`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1400900d2`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1400900d2`

## pseudocode

```c
__int64 __fastcall CscBuildACL(PSID Sid, struct _ACL **a2)
{
  ULONG v4; // ebx
  __int64 v5; // r9
  struct _ACL *Pool2; // rax
  struct _ACL *v7; // rdi
  NTSTATUS Acl; // ebx
  struct _ACL *v9; // rbp

  v4 = 3 * (RtlLengthSid(Sid) + 20);
  Pool2 = (struct _ACL *)ExAllocatePool2(258, v4, 1061124178, v5);
  v7 = Pool2;
  if ( Pool2 )
  {
    v9 = Pool2 + 5;
    RtlCreateSecurityDescriptor(Pool2, 1u);
    RtlSetOwnerSecurityDescriptor(v7, Sid, 0);
    RtlSetGroupSecurityDescriptor(v7, Sid, 0);
    Acl = RtlCreateAcl(v9, v4 - 40, 2u);
    if ( Acl < 0
      || (Acl = RtlAddAccessAllowedAce(v9, 2u, 1u, Sid), Acl < 0)
      || (Acl = RtlSetDaclSecurityDescriptor(v7, 1u, v9, 0), Acl < 0) )
    {
      ExFreePoolWithTag(v7, 0);
      v7 = 0;
    }
  }
  else
  {
    Acl = -1073741670;
  }
  *a2 = v7;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_0148477061aa3f6f7a18a21d9bb78afb_Traceguids, (unsigned int)Acl);
  return (unsigned int)Acl;
}

```

## disassembly

```asm
0x140090078  push    rbx
0x14009007a  push    rbp
0x14009007b  push    rsi
0x14009007c  push    rdi
0x14009007d  push    r14
0x14009007f  sub     rsp, 20h
0x140090083  mov     r14, rdx
0x140090086  mov     rsi, rcx
0x140090089  call    cs:__imp_RtlLengthSid
0x140090090  nop     dword ptr [rax+rax+00h]
0x140090095  mov     ecx, 102h
0x14009009a  mov     r8d, 3F3F7852h
0x1400900a0  add     eax, 14h
0x1400900a3  lea     ebx, [rax+rax*2]
0x1400900a6  mov     edx, ebx
0x1400900a8  call    cs:__imp_ExAllocatePool2
0x1400900af  nop     dword ptr [rax+rax+00h]
0x1400900b4  mov     rdi, rax
0x1400900b7  test    rax, rax
0x1400900ba  jnz     short loc_1400900C6
0x1400900bc  mov     ebx, 0C000009Ah
0x1400900c1  jmp     loc_140090177
0x1400900c6  mov     edx, 1; Revision
0x1400900cb  lea     rbp, [rax+28h]
0x1400900cf  mov     rcx, rdi; SecurityDescriptor
0x1400900d2  call    cs:__imp_RtlCreateSecurityDescriptor
0x1400900d9  nop     dword ptr [rax+rax+00h]
0x1400900de  xor     r8d, r8d; OwnerDefaulted
0x1400900e1  mov     rdx, rsi; Owner
0x1400900e4  mov     rcx, rdi; SecurityDescriptor
0x1400900e7  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x1400900ee  nop     dword ptr [rax+rax+00h]
0x1400900f3  xor     r8d, r8d; GroupDefaulted
0x1400900f6  mov     rdx, rsi; Group
0x1400900f9  mov     rcx, rdi; SecurityDescriptor
0x1400900fc  call    cs:__imp_RtlSetGroupSecurityDescriptor
0x140090103  nop     dword ptr [rax+rax+00h]
0x140090108  lea     edx, [rbx-28h]; AclLength
0x14009010b  mov     r8d, 2; AclRevision
0x140090111  mov     rcx, rbp; Acl
0x140090114  call    cs:__imp_RtlCreateAcl
0x14009011b  nop     dword ptr [rax+rax+00h]
0x140090120  mov     ebx, eax
0x140090122  test    eax, eax
0x140090124  js      short loc_140090164
0x140090126  mov     edx, 2; AceRevision
0x14009012b  mov     r9, rsi; Sid
0x14009012e  mov     rcx, rbp; Acl
0x140090131  lea     r8d, [rdx-1]; AccessMask
0x140090135  call    cs:__imp_RtlAddAccessAllowedAce
0x14009013c  nop     dword ptr [rax+rax+00h]
0x140090141  mov     ebx, eax
0x140090143  test    eax, eax
0x140090145  js      short loc_140090164
0x140090147  xor     r9d, r9d; DaclDefaulted
0x14009014a  mov     r8, rbp; Dacl
0x14009014d  mov     dl, 1; DaclPresent
0x14009014f  mov     rcx, rdi; SecurityDescriptor
0x140090152  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x140090159  nop     dword ptr [rax+rax+00h]
0x14009015e  mov     ebx, eax
0x140090160  test    eax, eax
0x140090162  jns     short loc_140090177
0x140090164  xor     edx, edx; Tag
0x140090166  mov     rcx, rdi; P
0x140090169  call    cs:__imp_ExFreePoolWithTag
0x140090170  nop     dword ptr [rax+rax+00h]
0x140090175  xor     edi, edi
0x140090177  mov     [r14], rdi
0x14009017a  mov     rcx, cs:WPP_GLOBAL_Control
0x140090181  lea     rax, WPP_GLOBAL_Control
0x140090188  cmp     rcx, rax
0x14009018b  jz      short loc_1400901AC
0x14009018d  mov     eax, [rcx+2Ch]
0x140090190  test    al, 20h
0x140090192  jz      short loc_1400901AC
0x140090194  mov     rcx, [rcx+18h]
0x140090198  lea     r8, WPP_0148477061aa3f6f7a18a21d9bb78afb_Traceguids
0x14009019f  mov     edx, 1Ah
0x1400901a4  mov     r9d, ebx
0x1400901a7  call    WPP_SF_d
0x1400901ac  mov     eax, ebx
0x1400901ae  add     rsp, 20h
0x1400901b2  pop     r14
0x1400901b4  pop     rdi
0x1400901b5  pop     rsi
0x1400901b6  pop     rbp
0x1400901b7  pop     rbx
0x1400901b8  retn
```
