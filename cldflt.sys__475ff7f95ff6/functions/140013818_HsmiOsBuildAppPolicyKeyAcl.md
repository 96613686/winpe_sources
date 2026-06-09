# HsmiOsBuildAppPolicyKeyAcl

- ea: `0x140013818`
- end: `0x14001392b`
- name: `HsmiOsBuildAppPolicyKeyAcl`
- size: `275`
- prototype: `__int64 __fastcall(PSID Sid, struct _ACL **)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, installer_update`

## callers

- `0x140014200`

## callees

- `0x140013818`

## import_xrefs

- `ntoskrnl!RtlCreateAcl` at `0x14001386c`
- `ntoskrnl!RtlCreateAcl` at `0x14001386c`
- `ntoskrnl!RtlLengthSid` at `0x140013827`
- `ntoskrnl!RtlLengthSid` at `0x140013827`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140013893`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1400138c6`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1400138f4`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140013893`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1400138c6`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x1400138f4`
- `ntoskrnl!SeExports` at `0x1400138a5`
- `ntoskrnl!SeExports` at `0x1400138d8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013913`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013913`
- `ntoskrnl!ExAllocatePool2` at `0x140013843`
- `ntoskrnl!ExAllocatePool2` at `0x140013843`

## pseudocode

```c
__int64 __fastcall HsmiOsBuildAppPolicyKeyAcl(PSID Sid, struct _ACL **a2)
{
  ULONG v4; // ebx
  struct _ACL *Pool2; // rax
  struct _ACL *v6; // rdi
  NTSTATUS Acl; // ebx

  v4 = RtlLengthSid(Sid) + 60;
  Pool2 = (struct _ACL *)ExAllocatePool2(256, v4, 1668047176);
  v6 = Pool2;
  if ( Pool2 )
  {
    Acl = RtlCreateAcl(Pool2, v4, 2u);
    if ( Acl < 0
      || (Acl = RtlAddAccessAllowedAce(v6, 2u, 0x2001Fu, Sid), Acl < 0)
      || (Acl = RtlAddAccessAllowedAce(v6, 2u, 0xF003Fu, SeExports->SeAliasAdminsSid), Acl < 0)
      || (Acl = RtlAddAccessAllowedAce(v6, 2u, 0xF003Fu, SeExports->SeLocalSystemSid), Acl < 0) )
    {
      ExFreePoolWithTag(v6, 0x636C6148u);
    }
    else
    {
      *a2 = v6;
    }
  }
  else
  {
    return (unsigned int)-1073741670;
  }
  return (unsigned int)Acl;
}

```

## disassembly

```asm
0x140013818  push    rbx
0x14001381a  push    rbp
0x14001381b  push    rsi
0x14001381c  push    rdi
0x14001381d  sub     rsp, 28h
0x140013821  mov     rsi, rdx
0x140013824  mov     rbp, rcx
0x140013827  call    cs:__imp_RtlLengthSid
0x14001382e  nop     dword ptr [rax+rax+00h]
0x140013833  mov     ecx, 100h
0x140013838  mov     r8d, 636C6148h
0x14001383e  lea     ebx, [rax+3Ch]
0x140013841  mov     edx, ebx
0x140013843  call    cs:__imp_ExAllocatePool2
0x14001384a  nop     dword ptr [rax+rax+00h]
0x14001384f  mov     rdi, rax
0x140013852  test    rax, rax
0x140013855  jnz     short loc_140013861
0x140013857  mov     ebx, 0C000009Ah
0x14001385c  jmp     loc_14001391F
0x140013861  mov     r8d, 2; AclRevision
0x140013867  mov     edx, ebx; AclLength
0x140013869  mov     rcx, rdi; Acl
0x14001386c  call    cs:__imp_RtlCreateAcl
0x140013873  nop     dword ptr [rax+rax+00h]
0x140013878  mov     ebx, eax
0x14001387a  test    eax, eax
0x14001387c  js      loc_14001390B
0x140013882  mov     r9, rbp; Sid
0x140013885  mov     edx, 2; AceRevision
0x14001388a  mov     r8d, 2001Fh; AccessMask
0x140013890  mov     rcx, rdi; Acl
0x140013893  call    cs:__imp_RtlAddAccessAllowedAce
0x14001389a  nop     dword ptr [rax+rax+00h]
0x14001389f  mov     ebx, eax
0x1400138a1  test    eax, eax
0x1400138a3  js      short loc_14001390B
0x1400138a5  mov     rax, cs:__imp_SeExports
0x1400138ac  mov     ebp, 0F003Fh
0x1400138b1  mov     r8d, ebp; AccessMask
0x1400138b4  mov     edx, 2; AceRevision
0x1400138b9  mov     rcx, rdi; Acl
0x1400138bc  mov     r9, [rax]
0x1400138bf  mov     r9, [r9+110h]; Sid
0x1400138c6  call    cs:__imp_RtlAddAccessAllowedAce
0x1400138cd  nop     dword ptr [rax+rax+00h]
0x1400138d2  mov     ebx, eax
0x1400138d4  test    eax, eax
0x1400138d6  js      short loc_14001390B
0x1400138d8  mov     rax, cs:__imp_SeExports
0x1400138df  mov     r8d, ebp; AccessMask
0x1400138e2  mov     edx, 2; AceRevision
0x1400138e7  mov     rcx, rdi; Acl
0x1400138ea  mov     r9, [rax]
0x1400138ed  mov     r9, [r9+108h]; Sid
0x1400138f4  call    cs:__imp_RtlAddAccessAllowedAce
0x1400138fb  nop     dword ptr [rax+rax+00h]
0x140013900  mov     ebx, eax
0x140013902  test    eax, eax
0x140013904  js      short loc_14001390B
0x140013906  mov     [rsi], rdi
0x140013909  jmp     short loc_14001391F
0x14001390b  mov     edx, 636C6148h; Tag
0x140013910  mov     rcx, rdi; P
0x140013913  call    cs:__imp_ExFreePoolWithTag
0x14001391a  nop     dword ptr [rax+rax+00h]
0x14001391f  mov     eax, ebx
0x140013921  add     rsp, 28h
0x140013925  pop     rdi
0x140013926  pop     rsi
0x140013927  pop     rbp
0x140013928  pop     rbx
0x140013929  retn
```
