# UlCreateSecurityDescriptor

- ea: `0x1c00d5afc`
- end: `0x1c00d5c37`
- name: `UlCreateSecurityDescriptor`
- size: `315`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR SecurityDescriptor)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1c0018040`
- `0x1c013bb6c`

## callees

- `0x1c00d5afc`

## import_xrefs

- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1c00d5b26`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x1c00d5b26`
- `ntoskrnl!RtlLengthSid` at `0x1c00d5b4f`
- `ntoskrnl!RtlLengthSid` at `0x1c00d5b4f`
- `ntoskrnl!RtlCreateAcl` at `0x1c00d5b9c`
- `ntoskrnl!RtlCreateAcl` at `0x1c00d5b9c`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1c00d5bd1`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x1c00d5bd1`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1c00d5bfa`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x1c00d5bfa`
- `ntoskrnl!ExAllocatePoolWithTagPriority` at `0x1c00d5b79`
- `ntoskrnl!ExAllocatePoolWithTagPriority` at `0x1c00d5b79`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00fd5f3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c00fd5f3`

## pseudocode

```c
__int64 __fastcall UlCreateSecurityDescriptor(PSECURITY_DESCRIPTOR SecurityDescriptor, __int64 a2, unsigned int a3)
{
  NTSTATUS Acl; // edi
  ULONG v7; // edi
  PSID *v8; // rbx
  __int64 v9; // rsi
  ULONG v10; // eax
  struct _ACL *PoolWithTagPriority; // rax
  struct _ACL *v12; // rbx
  unsigned int v13; // r14d
  ULONG *v14; // rsi

  Acl = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
  if ( Acl >= 0 )
  {
    v7 = 8;
    if ( a3 )
    {
      v8 = (PSID *)a2;
      v9 = a3;
      do
      {
        v10 = RtlLengthSid(*v8);
        v8 += 2;
        v7 += v10 + 12;
        --v9;
      }
      while ( v9 );
    }
    PoolWithTagPriority = (struct _ACL *)ExAllocatePoolWithTagPriority(PagedPool, v7, 0x44536C55u, LowPoolPriority);
    v12 = PoolWithTagPriority;
    if ( PoolWithTagPriority )
    {
      Acl = RtlCreateAcl(PoolWithTagPriority, v7, 2u);
      if ( Acl >= 0 )
      {
        v13 = 0;
        if ( a3 )
        {
          v14 = (ULONG *)(a2 + 12);
          while ( 1 )
          {
            Acl = RtlAddAccessAllowedAceEx(v12, 2u, *v14, *(v14 - 1), *(PSID *)(v14 - 3));
            if ( Acl < 0 )
              break;
            ++v13;
            v14 += 4;
            if ( v13 >= a3 )
              goto LABEL_11;
          }
        }
        else
        {
LABEL_11:
          Acl = RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, v12, 0);
          if ( Acl >= 0 )
            v12 = 0;
        }
      }
      if ( v12 )
        ExFreePoolWithTag(v12, 0);
    }
    else
    {
      return (unsigned int)-1073741670;
    }
  }
  return (unsigned int)Acl;
}

```

## disassembly

```asm
0x1c00d5afc  mov     [rsp+arg_0], rbx
0x1c00d5b01  mov     [rsp+arg_8], rbp
0x1c00d5b06  mov     [rsp+arg_10], rsi
0x1c00d5b0b  push    rdi
0x1c00d5b0c  push    r12
0x1c00d5b0e  push    r13
0x1c00d5b10  push    r14
0x1c00d5b12  push    r15
0x1c00d5b14  sub     rsp, 30h
0x1c00d5b18  mov     r15, rdx
0x1c00d5b1b  mov     ebp, r8d
0x1c00d5b1e  mov     edx, 1; Revision
0x1c00d5b23  mov     r12, rcx
0x1c00d5b26  call    cs:__imp_RtlCreateSecurityDescriptor
0x1c00d5b2d  nop     dword ptr [rax+rax+00h]
0x1c00d5b32  xor     r13d, r13d
0x1c00d5b35  mov     edi, eax
0x1c00d5b37  test    eax, eax
0x1c00d5b39  js      loc_1C00D5C17
0x1c00d5b3f  lea     edi, [r13+8]
0x1c00d5b43  test    ebp, ebp
0x1c00d5b45  jz      short loc_1C00D5B6A
0x1c00d5b47  mov     rbx, r15
0x1c00d5b4a  mov     esi, ebp
0x1c00d5b4c  mov     rcx, [rbx]; Sid
0x1c00d5b4f  call    cs:__imp_RtlLengthSid
0x1c00d5b56  nop     dword ptr [rax+rax+00h]
0x1c00d5b5b  add     edi, 0Ch
0x1c00d5b5e  lea     rbx, [rbx+10h]
0x1c00d5b62  add     edi, eax
0x1c00d5b64  sub     rsi, 1
0x1c00d5b68  jnz     short loc_1C00D5B4C
0x1c00d5b6a  xor     r9d, r9d; Priority
0x1c00d5b6d  mov     edx, edi; NumberOfBytes
0x1c00d5b6f  mov     r8d, 44536C55h; Tag
0x1c00d5b75  lea     ecx, [r9+1]; PoolType
0x1c00d5b79  call    cs:__imp_ExAllocatePoolWithTagPriority
0x1c00d5b80  nop     dword ptr [rax+rax+00h]
0x1c00d5b85  mov     rbx, rax
0x1c00d5b88  test    rax, rax
0x1c00d5b8b  jz      loc_1C00FD5E4
0x1c00d5b91  mov     r8d, 2; AclRevision
0x1c00d5b97  mov     edx, edi; AclLength
0x1c00d5b99  mov     rcx, rax; Acl
0x1c00d5b9c  call    cs:__imp_RtlCreateAcl
0x1c00d5ba3  nop     dword ptr [rax+rax+00h]
0x1c00d5ba8  mov     edi, eax
0x1c00d5baa  test    eax, eax
0x1c00d5bac  js      short loc_1C00D5C0E
0x1c00d5bae  mov     r14d, r13d
0x1c00d5bb1  test    ebp, ebp
0x1c00d5bb3  jz      short loc_1C00D5BEF
0x1c00d5bb5  lea     rsi, [r15+0Ch]
0x1c00d5bb9  mov     rax, [rsi-0Ch]
0x1c00d5bbd  mov     edx, 2; AceRevision
0x1c00d5bc2  mov     r9d, [rsi-4]; AccessMask
0x1c00d5bc6  mov     rcx, rbx; Acl
0x1c00d5bc9  mov     r8d, [rsi]; AceFlags
0x1c00d5bcc  mov     [rsp+58h+Sid], rax; Sid
0x1c00d5bd1  call    cs:__imp_RtlAddAccessAllowedAceEx
0x1c00d5bd8  nop     dword ptr [rax+rax+00h]
0x1c00d5bdd  mov     edi, eax
0x1c00d5bdf  test    eax, eax
0x1c00d5be1  js      short loc_1C00D5C0E
0x1c00d5be3  inc     r14d
0x1c00d5be6  add     rsi, 10h
0x1c00d5bea  cmp     r14d, ebp
0x1c00d5bed  jb      short loc_1C00D5BB9
0x1c00d5bef  xor     r9d, r9d; DaclDefaulted
0x1c00d5bf2  mov     r8, rbx; Dacl
0x1c00d5bf5  mov     dl, 1; DaclPresent
0x1c00d5bf7  mov     rcx, r12; SecurityDescriptor
0x1c00d5bfa  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x1c00d5c01  nop     dword ptr [rax+rax+00h]
0x1c00d5c06  test    eax, eax
0x1c00d5c08  mov     edi, eax
0x1c00d5c0a  cmovns  rbx, r13
0x1c00d5c0e  test    rbx, rbx
0x1c00d5c11  jnz     loc_1C00FD5EE
0x1c00d5c17  mov     rbx, [rsp+58h+arg_0]
0x1c00d5c1c  mov     eax, edi
0x1c00d5c1e  mov     rbp, [rsp+58h+arg_8]
0x1c00d5c23  mov     rsi, [rsp+58h+arg_10]
0x1c00d5c28  add     rsp, 30h
0x1c00d5c2c  pop     r15
0x1c00d5c2e  pop     r14
0x1c00d5c30  pop     r13
0x1c00d5c32  pop     r12
0x1c00d5c34  pop     rdi
0x1c00d5c35  retn
0x1c00fd5e4  mov     edi, 0C000009Ah
0x1c00fd5e9  jmp     loc_1C00D5C17
0x1c00fd5ee  xor     edx, edx; Tag
0x1c00fd5f0  mov     rcx, rbx; P
0x1c00fd5f3  call    cs:__imp_ExFreePoolWithTag
0x1c00fd5fa  nop     dword ptr [rax+rax+00h]
0x1c00fd5ff  nop
0x1c00fd600  jmp     loc_1C00D5C17
```
