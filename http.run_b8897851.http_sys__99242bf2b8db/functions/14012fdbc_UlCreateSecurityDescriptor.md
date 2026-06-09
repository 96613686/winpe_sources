# UlCreateSecurityDescriptor

- ea: `0x14012fdbc`
- end: `0x14012feea`
- name: `UlCreateSecurityDescriptor`
- size: `302`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR SecurityDescriptor)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400ffc60`
- `0x1401489b4`

## callees

- `0x14012fdbc`

## import_xrefs

- `ntoskrnl!RtlLengthSid` at `0x14012fe01`
- `ntoskrnl!RtlLengthSid` at `0x14012fe01`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14012feb7`
- `ntoskrnl!RtlSetDaclSecurityDescriptor` at `0x14012feb7`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x14012fe96`
- `ntoskrnl!RtlAddAccessAllowedAceEx` at `0x14012fe96`
- `ntoskrnl!RtlCreateAcl` at `0x14012fe5d`
- `ntoskrnl!RtlCreateAcl` at `0x14012fe5d`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14012fdd7`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14012fdd7`
- `ntoskrnl!ExAllocatePool3` at `0x14012fe34`
- `ntoskrnl!ExAllocatePool3` at `0x14012fe34`
- `ntoskrnl!ExFreePoolWithTag` at `0x14012fece`
- `ntoskrnl!ExFreePoolWithTag` at `0x14012fece`

## pseudocode

```c
__int64 __fastcall UlCreateSecurityDescriptor(PSECURITY_DESCRIPTOR SecurityDescriptor, __int64 a2, unsigned int a3)
{
  NTSTATUS Acl; // ebx
  unsigned int v7; // ebx
  ULONG i; // edi
  ULONG v9; // eax
  struct _ACL *Pool3; // rax
  struct _ACL *v11; // rsi
  unsigned int j; // edi

  Acl = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
  if ( Acl >= 0 )
  {
    v7 = 0;
    for ( i = 8; v7 < a3; i += v9 + 12 )
      v9 = RtlLengthSid(*(PSID *)(a2 + 16LL * v7++));
    Pool3 = (struct _ACL *)ExAllocatePool3(258, i, 1146317909, UxLowPriorityPool, 1);
    v11 = Pool3;
    if ( Pool3 )
    {
      Acl = RtlCreateAcl(Pool3, i, 2u);
      if ( Acl < 0 )
        goto LABEL_12;
      for ( j = 0; j < a3; ++j )
      {
        Acl = RtlAddAccessAllowedAceEx(
                v11,
                2u,
                *(_DWORD *)(a2 + 16LL * j + 12),
                *(_DWORD *)(a2 + 16LL * j + 8),
                *(PSID *)(a2 + 16LL * j));
        if ( Acl < 0 )
          goto LABEL_12;
      }
      Acl = RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, v11, 0);
      if ( Acl < 0 )
LABEL_12:
        ExFreePoolWithTag(v11, 0);
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
0x14012fdbc  push    rbx
0x14012fdbe  push    rbp
0x14012fdbf  push    rsi
0x14012fdc0  push    rdi
0x14012fdc1  push    r14
0x14012fdc3  push    r15
0x14012fdc5  sub     rsp, 38h
0x14012fdc9  mov     r14, rdx
0x14012fdcc  mov     ebp, r8d
0x14012fdcf  mov     edx, 1; Revision
0x14012fdd4  mov     r15, rcx
0x14012fdd7  call    cs:__imp_RtlCreateSecurityDescriptor
0x14012fdde  nop     dword ptr [rax+rax+00h]
0x14012fde3  mov     ebx, eax
0x14012fde5  test    eax, eax
0x14012fde7  js      loc_14012FEDA
0x14012fded  xor     ebx, ebx
0x14012fdef  mov     edi, 8
0x14012fdf4  test    ebp, ebp
0x14012fdf6  jz      short loc_14012FE18
0x14012fdf8  mov     ecx, ebx
0x14012fdfa  add     rcx, rcx
0x14012fdfd  mov     rcx, [r14+rcx*8]; Sid
0x14012fe01  call    cs:__imp_RtlLengthSid
0x14012fe08  nop     dword ptr [rax+rax+00h]
0x14012fe0d  add     edi, 0Ch
0x14012fe10  inc     ebx
0x14012fe12  add     edi, eax
0x14012fe14  cmp     ebx, ebp
0x14012fe16  jb      short loc_14012FDF8
0x14012fe18  mov     edx, edi
0x14012fe1a  lea     r9, UxLowPriorityPool
0x14012fe21  mov     ecx, 102h
0x14012fe26  mov     dword ptr [rsp+68h+Sid], 1
0x14012fe2e  mov     r8d, 44536C55h
0x14012fe34  call    cs:__imp_ExAllocatePool3
0x14012fe3b  nop     dword ptr [rax+rax+00h]
0x14012fe40  mov     rsi, rax
0x14012fe43  test    rax, rax
0x14012fe46  jnz     short loc_14012FE52
0x14012fe48  mov     ebx, 0C000009Ah
0x14012fe4d  jmp     loc_14012FEDA
0x14012fe52  mov     r8d, 2; AclRevision
0x14012fe58  mov     edx, edi; AclLength
0x14012fe5a  mov     rcx, rsi; Acl
0x14012fe5d  call    cs:__imp_RtlCreateAcl
0x14012fe64  nop     dword ptr [rax+rax+00h]
0x14012fe69  mov     ebx, eax
0x14012fe6b  test    eax, eax
0x14012fe6d  js      short loc_14012FEC9
0x14012fe6f  xor     edi, edi
0x14012fe71  cmp     edi, ebp
0x14012fe73  jnb     short loc_14012FEAC
0x14012fe75  mov     r8d, edi
0x14012fe78  mov     edx, 2; AceRevision
0x14012fe7d  add     r8, r8
0x14012fe80  mov     rcx, rsi; Acl
0x14012fe83  mov     rax, [r14+r8*8]
0x14012fe87  mov     r9d, [r14+r8*8+8]; AccessMask
0x14012fe8c  mov     r8d, [r14+r8*8+0Ch]; AceFlags
0x14012fe91  mov     [rsp+68h+Sid], rax; Sid
0x14012fe96  call    cs:__imp_RtlAddAccessAllowedAceEx
0x14012fe9d  nop     dword ptr [rax+rax+00h]
0x14012fea2  mov     ebx, eax
0x14012fea4  test    eax, eax
0x14012fea6  js      short loc_14012FEC9
0x14012fea8  inc     edi
0x14012feaa  jmp     short loc_14012FE71
0x14012feac  xor     r9d, r9d; DaclDefaulted
0x14012feaf  mov     r8, rsi; Dacl
0x14012feb2  mov     dl, 1; DaclPresent
0x14012feb4  mov     rcx, r15; SecurityDescriptor
0x14012feb7  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x14012febe  nop     dword ptr [rax+rax+00h]
0x14012fec3  mov     ebx, eax
0x14012fec5  test    eax, eax
0x14012fec7  jns     short loc_14012FEDA
0x14012fec9  xor     edx, edx; Tag
0x14012fecb  mov     rcx, rsi; P
0x14012fece  call    cs:__imp_ExFreePoolWithTag
0x14012fed5  nop     dword ptr [rax+rax+00h]
0x14012feda  mov     eax, ebx
0x14012fedc  add     rsp, 38h
0x14012fee0  pop     r15
0x14012fee2  pop     r14
0x14012fee4  pop     rdi
0x14012fee5  pop     rsi
0x14012fee6  pop     rbp
0x14012fee7  pop     rbx
0x14012fee8  retn
```
