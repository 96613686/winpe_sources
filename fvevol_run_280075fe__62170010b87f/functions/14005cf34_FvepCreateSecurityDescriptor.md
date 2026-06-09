# FvepCreateSecurityDescriptor

- ea: `0x14005cf34`
- end: `0x14005d0d6`
- name: `FvepCreateSecurityDescriptor`
- size: `418`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140063140`
- `0x140094a08`

## callees

- `0x140021a00`
- `0x14005cf34`

## import_xrefs

- `ntoskrnl!SeExports` at `0x14005cf43`
- `ntoskrnl!RtlLengthSid` at `0x14005cf61`
- `ntoskrnl!RtlLengthSid` at `0x14005cf74`
- `ntoskrnl!RtlLengthSid` at `0x14005d036`
- `ntoskrnl!RtlLengthSid` at `0x14005d09c`
- `ntoskrnl!RtlLengthSid` at `0x14005cf61`
- `ntoskrnl!RtlLengthSid` at `0x14005cf74`
- `ntoskrnl!RtlLengthSid` at `0x14005d036`
- `ntoskrnl!RtlLengthSid` at `0x14005d09c`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14005cfbb`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14005cfbb`
- `ntoskrnl!RtlCreateAcl` at `0x14005cfe1`
- `ntoskrnl!RtlCreateAcl` at `0x14005cfe1`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14005d004`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14005d004`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14005d021`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14005d021`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x14005d047`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x14005d088`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x14005d047`
- `ntoskrnl!RtlLengthSecurityDescriptor` at `0x14005d088`
- `ntoskrnl!RtlSetOwnerSecurityDescriptor` at `0x14005d0bf`
- `ntoskrnl!RtlSetOwnerSecurityDescriptor` at `0x14005d0bf`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005d067`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005d067`
- `ntoskrnl!ExAllocatePool2` at `0x14005cf95`
- `ntoskrnl!ExAllocatePool2` at `0x14005cf95`

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
0x14005cf34  push    rbx
0x14005cf36  push    rbp
0x14005cf37  push    rsi
0x14005cf38  push    rdi
0x14005cf39  push    r12
0x14005cf3b  push    r14
0x14005cf3d  push    r15
0x14005cf3f  sub     rsp, 20h
0x14005cf43  mov     rax, cs:__imp_SeExports
0x14005cf4a  mov     r14, rcx
0x14005cf4d  mov     qword ptr [rcx], 0
0x14005cf54  mov     rdx, [rax]
0x14005cf57  mov     rsi, [rdx+108h]
0x14005cf5e  mov     rcx, rsi; Sid
0x14005cf61  call    cs:__imp_RtlLengthSid
0x14005cf68  nop     dword ptr [rax+rax+00h]
0x14005cf6d  mov     rcx, rsi; Sid
0x14005cf70  lea     r15d, [rax+14h]
0x14005cf74  call    cs:__imp_RtlLengthSid
0x14005cf7b  nop     dword ptr [rax+rax+00h]
0x14005cf80  mov     ecx, 100h
0x14005cf85  mov     r8d, 30455646h
0x14005cf8b  lea     r12d, [rax+28h]
0x14005cf8f  add     r12d, r15d
0x14005cf92  mov     edx, r12d
0x14005cf95  call    cs:__imp_ExAllocatePool2
0x14005cf9c  nop     dword ptr [rax+rax+00h]
0x14005cfa1  mov     rdi, rax
0x14005cfa4  test    rax, rax
0x14005cfa7  jnz     short loc_14005CFB3
0x14005cfa9  mov     ebx, 0C000009Ah
0x14005cfae  jmp     loc_14005D073
0x14005cfb3  mov     edx, 1; Revision
0x14005cfb8  mov     rcx, rdi; SecurityDescriptor
0x14005cfbb  call    cs:__imp_RtlCreateSecurityDescriptor
0x14005cfc2  nop     dword ptr [rax+rax+00h]
0x14005cfc7  mov     ebx, eax
0x14005cfc9  test    eax, eax
0x14005cfcb  js      loc_14005D05F
0x14005cfd1  lea     rbp, [rdi+28h]
0x14005cfd5  mov     r8d, 2; AclRevision
0x14005cfdb  mov     rcx, rbp; Acl
0x14005cfde  mov     edx, r15d; AclLength
0x14005cfe1  call    cs:__imp_RtlCreateAcl
0x14005cfe8  nop     dword ptr [rax+rax+00h]
0x14005cfed  mov     ebx, eax
0x14005cfef  test    eax, eax
0x14005cff1  js      short loc_14005D05F
0x14005cff3  mov     r9, rsi; Sid
0x14005cff6  mov     edx, 2; AceRevision
0x14005cffb  mov     r8d, 0F003Fh; AccessMask
0x14005d001  mov     rcx, rbp; Acl
0x14005d004  call    cs:__imp_RtlAddAccessAllowedAce
0x14005d00b  nop     dword ptr [rax+rax+00h]
0x14005d010  mov     ebx, eax
0x14005d012  test    eax, eax
0x14005d014  js      short loc_14005D05F
0x14005d016  xor     r9d, r9d; DaclDefaulted
0x14005d019  mov     r8, rbp; Dacl
0x14005d01c  mov     dl, 1; DaclPresent
0x14005d01e  mov     rcx, rdi; SecurityDescriptor
0x14005d021  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x14005d028  nop     dword ptr [rax+rax+00h]
0x14005d02d  mov     ebx, eax
0x14005d02f  test    eax, eax
0x14005d031  js      short loc_14005D05F
0x14005d033  mov     rcx, rsi; Sid
0x14005d036  call    cs:__imp_RtlLengthSid
0x14005d03d  nop     dword ptr [rax+rax+00h]
0x14005d042  mov     rcx, rdi; SecurityDescriptor
0x14005d045  mov     ebx, eax
0x14005d047  call    cs:__imp_RtlLengthSecurityDescriptor
0x14005d04e  nop     dword ptr [rax+rax+00h]
0x14005d053  add     ebx, eax
0x14005d055  cmp     ebx, r12d
0x14005d058  jbe     short loc_14005D085
0x14005d05a  mov     ebx, 0C0000023h
0x14005d05f  mov     edx, 30455646h; Tag
0x14005d064  mov     rcx, rdi; P
0x14005d067  call    cs:__imp_ExFreePoolWithTag
0x14005d06e  nop     dword ptr [rax+rax+00h]
0x14005d073  mov     eax, ebx
0x14005d075  add     rsp, 20h
0x14005d079  pop     r15
0x14005d07b  pop     r14
0x14005d07d  pop     r12
0x14005d07f  pop     rdi
0x14005d080  pop     rsi
0x14005d081  pop     rbp
0x14005d082  pop     rbx
0x14005d083  retn
0x14005d085  mov     rcx, rdi; SecurityDescriptor
0x14005d088  call    cs:__imp_RtlLengthSecurityDescriptor
0x14005d08f  nop     dword ptr [rax+rax+00h]
0x14005d094  mov     ebx, eax
0x14005d096  mov     rcx, rsi; Sid
0x14005d099  add     rbx, rdi
0x14005d09c  call    cs:__imp_RtlLengthSid
0x14005d0a3  nop     dword ptr [rax+rax+00h]
0x14005d0a8  mov     r8d, eax; Size
0x14005d0ab  mov     rdx, rsi; Src
0x14005d0ae  mov     rcx, rbx; void *
0x14005d0b1  call    memmove
0x14005d0b6  xor     r8d, r8d; OwnerDefaulted
0x14005d0b9  mov     rdx, rbx; Owner
0x14005d0bc  mov     rcx, rdi; SecurityDescriptor
0x14005d0bf  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x14005d0c6  nop     dword ptr [rax+rax+00h]
0x14005d0cb  mov     ebx, eax
0x14005d0cd  test    eax, eax
0x14005d0cf  js      short loc_14005D05F
0x14005d0d1  mov     [r14], rdi
0x14005d0d4  jmp     short loc_14005D073
```
