# DsRolepMakeSecurityDescriptor

- ea: `0x1800157cc`
- end: `0x18001585b`
- name: `DsRolepMakeSecurityDescriptor`
- size: `143`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR pSecurityDescriptor)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001530c`

## callees

- `0x1800157cc`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorSacl` at `0x180015846`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorSacl` at `0x180015846`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18001582b`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x18001582b`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x180015814`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x180015814`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800157ea`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800157ea`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x180015801`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x180015801`

## pseudocode

```c
bool __fastcall DsRolepMakeSecurityDescriptor(
        PSECURITY_DESCRIPTOR pSecurityDescriptor,
        __int64 a2,
        struct _ACL *a3,
        struct _ACL *a4)
{
  PSID v4; // rdi

  v4 = DsRolepBuiltinAdminsSid;
  return InitializeSecurityDescriptor(pSecurityDescriptor, 1u)
      && SetSecurityDescriptorOwner(pSecurityDescriptor, v4, 0)
      && SetSecurityDescriptorGroup(pSecurityDescriptor, v4, 0)
      && SetSecurityDescriptorDacl(pSecurityDescriptor, 1, a3, 0)
      && SetSecurityDescriptorSacl(pSecurityDescriptor, a4 != 0, a4, 0);
}

```

## disassembly

```asm
0x1800157cc  push    rbx
0x1800157ce  push    rbp
0x1800157cf  push    rsi
0x1800157d0  push    rdi
0x1800157d1  sub     rsp, 28h
0x1800157d5  mov     rdi, cs:DsRolepBuiltinAdminsSid
0x1800157dc  mov     edx, 1; dwRevision
0x1800157e1  mov     rsi, r9
0x1800157e4  mov     rbp, r8
0x1800157e7  mov     rbx, rcx
0x1800157ea  call    cs:__imp_InitializeSecurityDescriptor
0x1800157f0  test    eax, eax
0x1800157f2  jnz     short loc_1800157F8
0x1800157f4  xor     al, al
0x1800157f6  jmp     short loc_180015852
0x1800157f8  xor     r8d, r8d; bOwnerDefaulted
0x1800157fb  mov     rdx, rdi; pOwner
0x1800157fe  mov     rcx, rbx; pSecurityDescriptor
0x180015801  call    cs:__imp_SetSecurityDescriptorOwner
0x180015807  test    eax, eax
0x180015809  jz      short loc_1800157F4
0x18001580b  xor     r8d, r8d; bGroupDefaulted
0x18001580e  mov     rdx, rdi; pGroup
0x180015811  mov     rcx, rbx; pSecurityDescriptor
0x180015814  call    cs:__imp_SetSecurityDescriptorGroup
0x18001581a  test    eax, eax
0x18001581c  jz      short loc_1800157F4
0x18001581e  xor     r9d, r9d; bDaclDefaulted
0x180015821  mov     r8, rbp; pDacl
0x180015824  mov     rcx, rbx; pSecurityDescriptor
0x180015827  lea     edx, [r9+1]; bDaclPresent
0x18001582b  call    cs:__imp_SetSecurityDescriptorDacl
0x180015831  test    eax, eax
0x180015833  jz      short loc_1800157F4
0x180015835  xor     edx, edx
0x180015837  mov     r8, rsi; pSacl
0x18001583a  test    rsi, rsi
0x18001583d  mov     rcx, rbx; pSecurityDescriptor
0x180015840  setnz   dl; bSaclPresent
0x180015843  xor     r9d, r9d; bSaclDefaulted
0x180015846  call    cs:__imp_SetSecurityDescriptorSacl
0x18001584c  neg     eax
0x18001584e  sbb     al, al
0x180015850  and     al, 1
0x180015852  add     rsp, 28h
0x180015856  pop     rdi
0x180015857  pop     rsi
0x180015858  pop     rbp
0x180015859  pop     rbx
0x18001585a  retn
```
