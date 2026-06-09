# CsrCreateLocalSystemSD

- ea: `0x180007ee0`
- end: `0x1800080a7`
- name: `CsrCreateLocalSystemSD`
- size: `455`
- prototype: `NTSTATUS __fastcall(struct _ACL **, ACCESS_MASK)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180005180`
- `0x180008540`

## callees

- `0x180007ee0`
- `0x18000ab80`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180007f98`
- `ntdll!RtlAllocateHeap` at `0x180007f98`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x180008026`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x180008026`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180007f48`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180007f48`
- `ntdll!RtlLengthSid` at `0x180007f79`
- `ntdll!RtlLengthSid` at `0x180007f79`
- `ntdll!RtlAddAccessAllowedAce` at `0x180008008`
- `ntdll!RtlAddAccessAllowedAce` at `0x180008008`
- `ntdll!RtlFreeSid` at `0x180008077`
- `ntdll!RtlFreeSid` at `0x180008077`
- `ntdll!RtlFreeHeap` at `0x180008049`
- `ntdll!RtlFreeHeap` at `0x180008049`
- `ntdll!RtlCreateAcl` at `0x180007fe5`
- `ntdll!RtlCreateAcl` at `0x180007fe5`
- `ntdll!RtlCreateSecurityDescriptor` at `0x180007fc6`
- `ntdll!RtlCreateSecurityDescriptor` at `0x180007fc6`

## pseudocode

```c
NTSTATUS __fastcall CsrCreateLocalSystemSD(struct _ACL **a1, ACCESS_MASK a2)
{
  NTSTATUS result; // eax
  ULONG v5; // ebp
  struct _ACL *Heap; // rax
  struct _ACL *v7; // rdi
  NTSTATUS SecurityDescriptor; // ebx
  PSID Sid; // [rsp+60h] [rbp-48h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+68h] [rbp-40h] BYREF

  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  Sid = 0;
  result = RtlAllocateAndInitializeSid(&IdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &Sid);
  if ( result >= 0 )
  {
    v5 = RtlLengthSid(Sid) + 60;
    Heap = (struct _ACL *)RtlAllocateHeap(CsrHeap, CsrBaseTag, v5);
    v7 = Heap;
    if ( Heap )
    {
      SecurityDescriptor = RtlCreateSecurityDescriptor(Heap, 1u);
      if ( SecurityDescriptor < 0
        || (SecurityDescriptor = RtlCreateAcl(v7 + 5, v5 - 40, 2u), SecurityDescriptor < 0)
        || (SecurityDescriptor = RtlAddAccessAllowedAce(v7 + 5, 2u, a2, Sid), SecurityDescriptor < 0)
        || (SecurityDescriptor = RtlSetDaclSecurityDescriptor(v7, 1u, v7 + 5, 0), SecurityDescriptor < 0) )
      {
        RtlFreeHeap(CsrHeap, 0, v7);
      }
      else
      {
        *a1 = v7;
      }
    }
    else
    {
      SecurityDescriptor = -1073741801;
    }
    if ( Sid )
      RtlFreeSid(Sid);
    return SecurityDescriptor;
  }
  return result;
}

```

## disassembly

```asm
0x180007ee0  push    r14
0x180007ee2  push    r15
0x180007ee4  sub     rsp, 98h
0x180007eeb  mov     rax, cs:__security_cookie
0x180007ef2  xor     rax, rsp
0x180007ef5  mov     [rsp+0A8h+var_38], rax
0x180007efa  mov     r15, rcx
0x180007efd  mov     dword ptr [rsp+0A8h+IdentifierAuthority.Value], 0
0x180007f05  xor     ecx, ecx
0x180007f07  mov     word ptr [rsp+0A8h+IdentifierAuthority.Value+4], 500h
0x180007f0e  lea     rax, [rsp+0A8h+var_48]
0x180007f13  mov     [rsp+0A8h+var_48], rcx
0x180007f18  mov     [rsp+0A8h+Sid], rax; Sid
0x180007f1d  mov     r14d, edx
0x180007f20  mov     [rsp+0A8h+SubAuthority7], ecx; SubAuthority7
0x180007f24  xor     r9d, r9d; SubAuthority1
0x180007f27  mov     [rsp+0A8h+SubAuthority6], ecx; SubAuthority6
0x180007f2b  mov     r8d, 12h; SubAuthority0
0x180007f31  mov     [rsp+0A8h+SubAuthority5], ecx; SubAuthority5
0x180007f35  mov     dl, 1; SubAuthorityCount
0x180007f37  mov     [rsp+0A8h+SubAuthority4], ecx; SubAuthority4
0x180007f3b  mov     [rsp+0A8h+SubAuthority3], ecx; SubAuthority3
0x180007f3f  mov     [rsp+0A8h+SubAuthority2], ecx; SubAuthority2
0x180007f43  lea     rcx, [rsp+0A8h+IdentifierAuthority]; IdentifierAuthority
0x180007f48  call    cs:__imp_RtlAllocateAndInitializeSid
0x180007f4f  nop     dword ptr [rax+rax+00h]
0x180007f54  test    eax, eax
0x180007f56  js      loc_18000808D
0x180007f5c  mov     rcx, [rsp+0A8h+var_48]; Sid
0x180007f61  mov     [rsp+0A8h+var_18], rbp
0x180007f69  mov     [rsp+0A8h+var_28], rdi
0x180007f71  mov     [rsp+0A8h+arg_10], rbx
0x180007f79  call    cs:__imp_RtlLengthSid
0x180007f80  nop     dword ptr [rax+rax+00h]
0x180007f85  mov     edx, cs:CsrBaseTag; Flags
0x180007f8b  mov     rcx, cs:CsrHeap; HeapHandle
0x180007f92  lea     ebp, [rax+3Ch]
0x180007f95  mov     r8d, ebp; Size
0x180007f98  call    cs:__imp_RtlAllocateHeap
0x180007f9f  nop     dword ptr [rax+rax+00h]
0x180007fa4  mov     rdi, rax
0x180007fa7  test    rax, rax
0x180007faa  jnz     short loc_180007FB6
0x180007fac  mov     ebx, 0C0000017h
0x180007fb1  jmp     loc_18000805D
0x180007fb6  mov     edx, 1; Revision
0x180007fbb  mov     [rsp+0A8h+var_20], rsi
0x180007fc3  mov     rcx, rdi; SecurityDescriptor
0x180007fc6  call    cs:__imp_RtlCreateSecurityDescriptor
0x180007fcd  nop     dword ptr [rax+rax+00h]
0x180007fd2  mov     ebx, eax
0x180007fd4  test    eax, eax
0x180007fd6  js      short loc_18000803D
0x180007fd8  lea     edx, [rbp-28h]; AclLength
0x180007fdb  mov     r8d, 2; AclRevision
0x180007fe1  lea     rcx, [rdi+28h]; Acl
0x180007fe5  call    cs:__imp_RtlCreateAcl
0x180007fec  nop     dword ptr [rax+rax+00h]
0x180007ff1  mov     ebx, eax
0x180007ff3  test    eax, eax
0x180007ff5  js      short loc_18000803D
0x180007ff7  mov     r9, [rsp+0A8h+var_48]; Sid
0x180007ffc  lea     rcx, [rdi+28h]; Acl
0x180008000  mov     r8d, r14d; AccessMask
0x180008003  mov     edx, 2; AceRevision
0x180008008  call    cs:__imp_RtlAddAccessAllowedAce
0x18000800f  nop     dword ptr [rax+rax+00h]
0x180008014  mov     ebx, eax
0x180008016  test    eax, eax
0x180008018  js      short loc_18000803D
0x18000801a  xor     r9d, r9d; DaclDefaulted
0x18000801d  lea     r8, [rdi+28h]; Dacl
0x180008021  mov     dl, 1; DaclPresent
0x180008023  mov     rcx, rdi; SecurityDescriptor
0x180008026  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x18000802d  nop     dword ptr [rax+rax+00h]
0x180008032  mov     ebx, eax
0x180008034  test    eax, eax
0x180008036  js      short loc_18000803D
0x180008038  mov     [r15], rdi
0x18000803b  jmp     short loc_180008055
0x18000803d  mov     rcx, cs:CsrHeap; HeapHandle
0x180008044  mov     r8, rdi; BaseAddress
0x180008047  xor     edx, edx; Flags
0x180008049  call    cs:__imp_RtlFreeHeap
0x180008050  nop     dword ptr [rax+rax+00h]
0x180008055  mov     rsi, [rsp+0A8h+var_20]
0x18000805d  mov     rcx, [rsp+0A8h+var_48]; Sid
0x180008062  mov     rdi, [rsp+0A8h+var_28]
0x18000806a  mov     rbp, [rsp+0A8h+var_18]
0x180008072  test    rcx, rcx
0x180008075  jz      short loc_180008083
0x180008077  call    cs:__imp_RtlFreeSid
0x18000807e  nop     dword ptr [rax+rax+00h]
0x180008083  mov     eax, ebx
0x180008085  mov     rbx, [rsp+0A8h+arg_10]
0x18000808d  mov     rcx, [rsp+0A8h+var_38]
0x180008092  xor     rcx, rsp; StackCookie
0x180008095  call    __security_check_cookie
0x18000809a  add     rsp, 98h
0x1800080a1  pop     r15
0x1800080a3  pop     r14
0x1800080a5  retn
```
