# HsmiOsBuildAppPolicyKeyAcl

- ea: `0x140013798`
- end: `0x1400138ab`
- name: `HsmiOsBuildAppPolicyKeyAcl`
- size: `275`
- prototype: `__int64 __fastcall(PSID Sid)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, installer_update`

## callers

- `0x140014180`

## callees

- `0x140013798`

## import_xrefs

- `ntoskrnl!RtlCreateAcl` at `0x1400137ec`
- `ntoskrnl!RtlCreateAcl` at `0x1400137ec`
- `ntoskrnl!RtlLengthSid` at `0x1400137a7`
- `ntoskrnl!RtlLengthSid` at `0x1400137a7`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140013813`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140013846`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140013874`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140013813`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140013846`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140013874`
- `ntoskrnl!SeExports` at `0x140013825`
- `ntoskrnl!SeExports` at `0x140013858`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013893`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013893`
- `ntoskrnl!ExAllocatePool2` at `0x1400137c3`
- `ntoskrnl!ExAllocatePool2` at `0x1400137c3`

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
0x140013798  push    rbx
0x14001379a  push    rbp
0x14001379b  push    rsi
0x14001379c  push    rdi
0x14001379d  sub     rsp, 28h
0x1400137a1  mov     rsi, rdx
0x1400137a4  mov     rbp, rcx
0x1400137a7  call    cs:__imp_RtlLengthSid
0x1400137ae  nop     dword ptr [rax+rax+00h]
0x1400137b3  mov     ecx, 100h
0x1400137b8  mov     r8d, 636C6148h
0x1400137be  lea     ebx, [rax+3Ch]
0x1400137c1  mov     edx, ebx
0x1400137c3  call    cs:__imp_ExAllocatePool2
0x1400137ca  nop     dword ptr [rax+rax+00h]
0x1400137cf  mov     rdi, rax
0x1400137d2  test    rax, rax
0x1400137d5  jnz     short loc_1400137E1
0x1400137d7  mov     ebx, 0C000009Ah
0x1400137dc  jmp     loc_14001389F
0x1400137e1  mov     r8d, 2; AclRevision
0x1400137e7  mov     edx, ebx; AclLength
0x1400137e9  mov     rcx, rdi; Acl
0x1400137ec  call    cs:__imp_RtlCreateAcl
0x1400137f3  nop     dword ptr [rax+rax+00h]
0x1400137f8  mov     ebx, eax
0x1400137fa  test    eax, eax
0x1400137fc  js      loc_14001388B
0x140013802  mov     r9, rbp; Sid
0x140013805  mov     edx, 2; AceRevision
0x14001380a  mov     r8d, 2001Fh; AccessMask
0x140013810  mov     rcx, rdi; Acl
0x140013813  call    cs:__imp_RtlAddAccessAllowedAce
0x14001381a  nop     dword ptr [rax+rax+00h]
0x14001381f  mov     ebx, eax
0x140013821  test    eax, eax
0x140013823  js      short loc_14001388B
0x140013825  mov     rax, cs:__imp_SeExports
0x14001382c  mov     ebp, 0F003Fh
0x140013831  mov     r8d, ebp; AccessMask
0x140013834  mov     edx, 2; AceRevision
0x140013839  mov     rcx, rdi; Acl
0x14001383c  mov     r9, [rax]
0x14001383f  mov     r9, [r9+110h]; Sid
0x140013846  call    cs:__imp_RtlAddAccessAllowedAce
0x14001384d  nop     dword ptr [rax+rax+00h]
0x140013852  mov     ebx, eax
0x140013854  test    eax, eax
0x140013856  js      short loc_14001388B
0x140013858  mov     rax, cs:__imp_SeExports
0x14001385f  mov     r8d, ebp; AccessMask
0x140013862  mov     edx, 2; AceRevision
0x140013867  mov     rcx, rdi; Acl
0x14001386a  mov     r9, [rax]
0x14001386d  mov     r9, [r9+108h]; Sid
0x140013874  call    cs:__imp_RtlAddAccessAllowedAce
0x14001387b  nop     dword ptr [rax+rax+00h]
0x140013880  mov     ebx, eax
0x140013882  test    eax, eax
0x140013884  js      short loc_14001388B
0x140013886  mov     [rsi], rdi
0x140013889  jmp     short loc_14001389F
0x14001388b  mov     edx, 636C6148h; Tag
0x140013890  mov     rcx, rdi; P
0x140013893  call    cs:__imp_ExFreePoolWithTag
0x14001389a  nop     dword ptr [rax+rax+00h]
0x14001389f  mov     eax, ebx
0x1400138a1  add     rsp, 28h
0x1400138a5  pop     rdi
0x1400138a6  pop     rsi
0x1400138a7  pop     rbp
0x1400138a8  pop     rbx
0x1400138a9  retn
```
