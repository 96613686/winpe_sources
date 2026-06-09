# FvepCreateSecurityDescriptor

- ea: `0x14005efb4`
- end: `0x14005f156`
- name: `FvepCreateSecurityDescriptor`
- size: `418`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400651c0`
- `0x140096ab8`

## callees

- `0x140022d40`
- `0x14005efb4`

## import_xrefs

- `ntoskrnl!SeExports` at `0x14005efc3`
- `ntoskrnl!RtlLengthSid` at `0x14005efe1`
- `ntoskrnl!RtlLengthSid` at `0x14005eff4`
- `ntoskrnl!RtlLengthSid` at `0x14005f0b6`
- `ntoskrnl!RtlLengthSid` at `0x14005f11c`
- `ntoskrnl!RtlLengthSid` at `0x14005efe1`
- `ntoskrnl!RtlLengthSid` at `0x14005eff4`
- `ntoskrnl!RtlLengthSid` at `0x14005f0b6`
- `ntoskrnl!RtlLengthSid` at `0x14005f11c`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14005f03b`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14005f03b`
- `ntoskrnl!RtlCreateAcl` at `0x14005f061`
- `ntoskrnl!RtlCreateAcl` at `0x14005f061`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14005f084`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14005f084`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14005f0a1`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14005f0a1`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x14005f0c7`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x14005f108`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x14005f0c7`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x14005f108`
- `ntoskrnl!RtlSetOwnerSecurityDescriptor` at `0x14005f13f`
- `ntoskrnl!RtlSetOwnerSecurityDescriptor` at `0x14005f13f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005f0e7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005f0e7`
- `ntoskrnl!ExAllocatePool2` at `0x14005f015`
- `ntoskrnl!ExAllocatePool2` at `0x14005f015`

## pseudocode

```c
__int64 __fastcall FvepCreateSecurityDescriptor(struct _ACL **a1)
{
  PSID SeLocalSystemSid; // rsi
  ULONG v3; // r15d
  ULONG v4; // r12d
  struct _ACL *Pool2; // rax
  struct _ACL *v6; // rdi
  NTSTATUS SecurityDescriptor; // ebx
  ULONG v8; // ebx
  char *v10; // rbx
  ULONG v11; // eax

  *a1 = 0;
  SeLocalSystemSid = SeExports->SeLocalSystemSid;
  v3 = RtlLengthSid(SeLocalSystemSid) + 20;
  v4 = v3 + RtlLengthSid(SeLocalSystemSid) + 40;
  Pool2 = (struct _ACL *)ExAllocatePool2(256, v4, 809850438);
  v6 = Pool2;
  if ( Pool2 )
  {
    SecurityDescriptor = RtlCreateSecurityDescriptor(Pool2, 1u);
    if ( SecurityDescriptor >= 0 )
    {
      SecurityDescriptor = RtlCreateAcl(v6 + 5, v3, 2u);
      if ( SecurityDescriptor >= 0 )
      {
        SecurityDescriptor = RtlAddAccessAllowedAce(v6 + 5, 2u, 0xF003Fu, SeLocalSystemSid);
        if ( SecurityDescriptor >= 0 )
        {
          SecurityDescriptor = RtlSetDaclSecurityDescriptor(v6, 1u, v6 + 5, 0);
          if ( SecurityDescriptor >= 0 )
          {
            v8 = RtlLengthSid(SeLocalSystemSid);
            if ( RtlLengthSecurityDescriptor(v6) + v8 <= v4 )
            {
              v10 = (char *)v6 + RtlLengthSecurityDescriptor(v6);
              v11 = RtlLengthSid(SeLocalSystemSid);
              memmove(v10, SeLocalSystemSid, v11);
              SecurityDescriptor = RtlSetOwnerSecurityDescriptor(v6, v10, 0);
              if ( SecurityDescriptor >= 0 )
              {
                *a1 = v6;
                return (unsigned int)SecurityDescriptor;
              }
            }
            else
            {
              SecurityDescriptor = -1073741789;
            }
          }
        }
      }
    }
    ExFreePoolWithTag(v6, 0x30455646u);
  }
  else
  {
    return (unsigned int)-1073741670;
  }
  return (unsigned int)SecurityDescriptor;
}

```

## disassembly

```asm
0x14005efb4  push    rbx
0x14005efb6  push    rbp
0x14005efb7  push    rsi
0x14005efb8  push    rdi
0x14005efb9  push    r12
0x14005efbb  push    r14
0x14005efbd  push    r15
0x14005efbf  sub     rsp, 20h
0x14005efc3  mov     rax, cs:__imp_SeExports
0x14005efca  mov     r14, rcx
0x14005efcd  mov     qword ptr [rcx], 0
0x14005efd4  mov     rdx, [rax]
0x14005efd7  mov     rsi, [rdx+108h]
0x14005efde  mov     rcx, rsi; Sid
0x14005efe1  call    cs:__imp_RtlLengthSid
0x14005efe8  nop     dword ptr [rax+rax+00h]
0x14005efed  mov     rcx, rsi; Sid
0x14005eff0  lea     r15d, [rax+14h]
0x14005eff4  call    cs:__imp_RtlLengthSid
0x14005effb  nop     dword ptr [rax+rax+00h]
0x14005f000  mov     ecx, 100h
0x14005f005  mov     r8d, 30455646h
0x14005f00b  lea     r12d, [rax+28h]
0x14005f00f  add     r12d, r15d
0x14005f012  mov     edx, r12d
0x14005f015  call    cs:__imp_ExAllocatePool2
0x14005f01c  nop     dword ptr [rax+rax+00h]
0x14005f021  mov     rdi, rax
0x14005f024  test    rax, rax
0x14005f027  jnz     short loc_14005F033
0x14005f029  mov     ebx, 0C000009Ah
0x14005f02e  jmp     loc_14005F0F3
0x14005f033  mov     edx, 1; Revision
0x14005f038  mov     rcx, rdi; SecurityDescriptor
0x14005f03b  call    cs:__imp_RtlCreateSecurityDescriptor
0x14005f042  nop     dword ptr [rax+rax+00h]
0x14005f047  mov     ebx, eax
0x14005f049  test    eax, eax
0x14005f04b  js      loc_14005F0DF
0x14005f051  lea     rbp, [rdi+28h]
0x14005f055  mov     r8d, 2; AclRevision
0x14005f05b  mov     rcx, rbp; Acl
0x14005f05e  mov     edx, r15d; AclLength
0x14005f061  call    cs:__imp_RtlCreateAcl
0x14005f068  nop     dword ptr [rax+rax+00h]
0x14005f06d  mov     ebx, eax
0x14005f06f  test    eax, eax
0x14005f071  js      short loc_14005F0DF
0x14005f073  mov     r9, rsi; Sid
0x14005f076  mov     edx, 2; AceRevision
0x14005f07b  mov     r8d, 0F003Fh; AccessMask
0x14005f081  mov     rcx, rbp; Acl
0x14005f084  call    cs:__imp_RtlAddAccessAllowedAce
0x14005f08b  nop     dword ptr [rax+rax+00h]
0x14005f090  mov     ebx, eax
0x14005f092  test    eax, eax
0x14005f094  js      short loc_14005F0DF
0x14005f096  xor     r9d, r9d; DaclDefaulted
0x14005f099  mov     r8, rbp; Dacl
0x14005f09c  mov     dl, 1; DaclPresent
0x14005f09e  mov     rcx, rdi; SecurityDescriptor
0x14005f0a1  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x14005f0a8  nop     dword ptr [rax+rax+00h]
0x14005f0ad  mov     ebx, eax
0x14005f0af  test    eax, eax
0x14005f0b1  js      short loc_14005F0DF
0x14005f0b3  mov     rcx, rsi; Sid
0x14005f0b6  call    cs:__imp_RtlLengthSid
0x14005f0bd  nop     dword ptr [rax+rax+00h]
0x14005f0c2  mov     rcx, rdi; SecurityDescriptor
0x14005f0c5  mov     ebx, eax
0x14005f0c7  call    cs:__imp_RtlLengthSecurityDescriptor
0x14005f0ce  nop     dword ptr [rax+rax+00h]
0x14005f0d3  add     ebx, eax
0x14005f0d5  cmp     ebx, r12d
0x14005f0d8  jbe     short loc_14005F105
0x14005f0da  mov     ebx, 0C0000023h
0x14005f0df  mov     edx, 30455646h; Tag
0x14005f0e4  mov     rcx, rdi; P
0x14005f0e7  call    cs:__imp_ExFreePoolWithTag
0x14005f0ee  nop     dword ptr [rax+rax+00h]
0x14005f0f3  mov     eax, ebx
0x14005f0f5  add     rsp, 20h
0x14005f0f9  pop     r15
0x14005f0fb  pop     r14
0x14005f0fd  pop     r12
0x14005f0ff  pop     rdi
0x14005f100  pop     rsi
0x14005f101  pop     rbp
0x14005f102  pop     rbx
0x14005f103  retn
0x14005f105  mov     rcx, rdi; SecurityDescriptor
0x14005f108  call    cs:__imp_RtlLengthSecurityDescriptor
0x14005f10f  nop     dword ptr [rax+rax+00h]
0x14005f114  mov     ebx, eax
0x14005f116  mov     rcx, rsi; Sid
0x14005f119  add     rbx, rdi
0x14005f11c  call    cs:__imp_RtlLengthSid
0x14005f123  nop     dword ptr [rax+rax+00h]
0x14005f128  mov     r8d, eax; Size
0x14005f12b  mov     rdx, rsi; Src
0x14005f12e  mov     rcx, rbx; void *
0x14005f131  call    memmove
0x14005f136  xor     r8d, r8d; OwnerDefaulted
0x14005f139  mov     rdx, rbx; Owner
0x14005f13c  mov     rcx, rdi; SecurityDescriptor
0x14005f13f  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x14005f146  nop     dword ptr [rax+rax+00h]
0x14005f14b  mov     ebx, eax
0x14005f14d  test    eax, eax
0x14005f14f  js      short loc_14005F0DF
0x14005f151  mov     [r14], rdi
0x14005f154  jmp     short loc_14005F0F3
```
