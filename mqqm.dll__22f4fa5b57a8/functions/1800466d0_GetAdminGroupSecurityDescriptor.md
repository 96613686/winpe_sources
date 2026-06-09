# GetAdminGroupSecurityDescriptor

- ea: `0x1800466d0`
- end: `0x1800467e4`
- name: `GetAdminGroupSecurityDescriptor`
- size: `276`
- prototype: `__int64 __fastcall(DWORD AccessMask)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180045f34`

## callees

- `0x1800466d0`
- `0x18009bd1c`

## import_xrefs

- `msvcrt!free` at `0x1800467a6`
- `msvcrt!free` at `0x1800467af`
- `msvcrt!free` at `0x1800467be`
- `msvcrt!free` at `0x1800467c8`
- `msvcrt!free` at `0x1800467a6`
- `msvcrt!free` at `0x1800467af`
- `msvcrt!free` at `0x1800467be`
- `msvcrt!free` at `0x1800467c8`
- `ADVAPI32!AddAccessAllowedAce` at `0x180046742`
- `ADVAPI32!AddAccessAllowedAce` at `0x180046742`
- `ADVAPI32!GetLengthSid` at `0x180046703`
- `ADVAPI32!GetLengthSid` at `0x180046703`
- `ADVAPI32!InitializeAcl` at `0x180046726`
- `ADVAPI32!InitializeAcl` at `0x180046726`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x180046756`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x180046756`
- `ADVAPI32!SetSecurityDescriptorOwner` at `0x180046769`
- `ADVAPI32!SetSecurityDescriptorOwner` at `0x180046769`
- `ADVAPI32!SetSecurityDescriptorGroup` at `0x18004677c`
- `ADVAPI32!SetSecurityDescriptorGroup` at `0x18004677c`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x180046791`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x180046791`
- `mqsec!MQSec_GetAdminSid` at `0x1800466e5`
- `mqsec!MQSec_GetAdminSid` at `0x1800466e5`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void *__fastcall GetAdminGroupSecurityDescriptor(DWORD AccessMask)
{
  void *AdminSid; // rbp
  void *v3; // rsi
  DWORD v4; // edi
  struct _ACL *v5; // rbx

  AdminSid = MQSec_GetAdminSid();
  v3 = MmAllocate(0x28u);
  v4 = GetLengthSid(AdminSid) + 16;
  v5 = (struct _ACL *)MmAllocate(v4);
  if ( InitializeAcl(v5, v4, 2u)
    && AddAccessAllowedAce(v5, 2u, AccessMask, AdminSid)
    && InitializeSecurityDescriptor(v3, 1u)
    && SetSecurityDescriptorOwner(v3, AdminSid, 0)
    && SetSecurityDescriptorGroup(v3, AdminSid, 0)
    && SetSecurityDescriptorDacl(v3, 1, v5, 0) )
  {
    free(0);
    free(0);
    return v3;
  }
  else
  {
    free(v5);
    free(v3);
    return 0;
  }
}

```

## disassembly

```asm
0x1800466d0  mov     [rsp+arg_0], rbx
0x1800466d5  mov     [rsp+arg_18], rbp
0x1800466da  push    rsi
0x1800466db  push    rdi
0x1800466dc  push    r14
0x1800466de  sub     rsp, 20h
0x1800466e2  mov     r14d, ecx
0x1800466e5  call    cs:__imp_?MQSec_GetAdminSid@@YAPEAXXZ; MQSec_GetAdminSid(void)
0x1800466eb  mov     rbp, rax
0x1800466ee  mov     ecx, 28h ; '('; unsigned __int64
0x1800466f3  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x1800466f8  mov     rsi, rax
0x1800466fb  mov     [rsp+38h+arg_8], rax
0x180046700  mov     rcx, rbp; pSid
0x180046703  call    cs:__imp_GetLengthSid
0x180046709  lea     edi, [rax+10h]
0x18004670c  mov     ecx, edi; unsigned __int64
0x18004670e  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180046713  mov     rbx, rax
0x180046716  mov     [rsp+38h+arg_10], rax
0x18004671b  mov     r8d, 2; dwAclRevision
0x180046721  mov     edx, edi; nAclLength
0x180046723  mov     rcx, rax; pAcl
0x180046726  call    cs:__imp_InitializeAcl
0x18004672c  test    eax, eax
0x18004672e  jz      loc_1800467BB
0x180046734  mov     r9, rbp; pSid
0x180046737  mov     r8d, r14d; AccessMask
0x18004673a  mov     edx, 2; dwAceRevision
0x18004673f  mov     rcx, rbx; pAcl
0x180046742  call    cs:__imp_AddAccessAllowedAce
0x180046748  test    eax, eax
0x18004674a  jz      short loc_1800467BB
0x18004674c  mov     edi, 1
0x180046751  mov     edx, edi; dwRevision
0x180046753  mov     rcx, rsi; pSecurityDescriptor
0x180046756  call    cs:__imp_InitializeSecurityDescriptor
0x18004675c  test    eax, eax
0x18004675e  jz      short loc_1800467BB
0x180046760  xor     r8d, r8d; bOwnerDefaulted
0x180046763  mov     rdx, rbp; pOwner
0x180046766  mov     rcx, rsi; pSecurityDescriptor
0x180046769  call    cs:__imp_SetSecurityDescriptorOwner
0x18004676f  test    eax, eax
0x180046771  jz      short loc_1800467BB
0x180046773  xor     r8d, r8d; bGroupDefaulted
0x180046776  mov     rdx, rbp; pGroup
0x180046779  mov     rcx, rsi; pSecurityDescriptor
0x18004677c  call    cs:__imp_SetSecurityDescriptorGroup
0x180046782  test    eax, eax
0x180046784  jz      short loc_1800467BB
0x180046786  xor     r9d, r9d; bDaclDefaulted
0x180046789  mov     r8, rbx; pDacl
0x18004678c  mov     edx, edi; bDaclPresent
0x18004678e  mov     rcx, rsi; pSecurityDescriptor
0x180046791  call    cs:__imp_SetSecurityDescriptorDacl
0x180046797  test    eax, eax
0x180046799  jz      short loc_1800467BB
0x18004679b  mov     [rsp+38h+arg_8], 0
0x1800467a4  xor     ecx, ecx; Block
0x1800467a6  call    cs:__imp_free
0x1800467ac  nop
0x1800467ad  xor     ecx, ecx; Block
0x1800467af  call    cs:__imp_free
0x1800467b5  nop
0x1800467b6  mov     rax, rsi
0x1800467b9  jmp     short loc_1800467D1
0x1800467bb  mov     rcx, rbx; Block
0x1800467be  call    cs:__imp_free
0x1800467c4  nop
0x1800467c5  mov     rcx, rsi; Block
0x1800467c8  call    cs:__imp_free
0x1800467ce  nop
0x1800467cf  xor     eax, eax
0x1800467d1  mov     rbx, [rsp+38h+arg_0]
0x1800467d6  mov     rbp, [rsp+38h+arg_18]
0x1800467db  add     rsp, 20h
0x1800467df  pop     r14
0x1800467e1  pop     rdi
0x1800467e2  pop     rsi
0x1800467e3  retn
```
