# CscSeCreateAcl

- ea: `0x14008da04`
- end: `0x14008dae1`
- name: `CscSeCreateAcl`
- size: `221`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1400173e8`

## callees

- `0x140019284`
- `0x14008da04`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14008da51`
- `ntoskrnl!ExAllocatePool2` at `0x14008da51`
- `ntoskrnl!RtlLengthSid` at `0x14008da27`
- `ntoskrnl!RtlLengthSid` at `0x14008da27`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14008dac1`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14008dac1`
- `ntoskrnl!RtlCreateAcl` at `0x14008da9e`
- `ntoskrnl!RtlCreateAcl` at `0x14008da9e`

## pseudocode

```c
__int64 __fastcall CscSeCreateAcl(struct _ACL **a1, void **a2)
{
  void *v2; // rax
  void **v3; // rdi
  ULONG v5; // esi
  void **v6; // rbx
  struct _ACL *Pool2; // rax
  struct _ACL *v8; // rbx
  NTSTATUS Acl; // esi
  struct _ACL *v11; // [rsp+50h] [rbp+8h] BYREF

  v2 = *a2;
  v3 = a2;
  v5 = 8;
  if ( *a2 )
  {
    v6 = a2;
    do
    {
      v6 += 2;
      v5 += RtlLengthSid(v2) + 8;
      v2 = *v6;
    }
    while ( *v6 );
  }
  Pool2 = (struct _ACL *)ExAllocatePool2(258, v5, 557871939);
  v11 = Pool2;
  v8 = Pool2;
  if ( !Pool2 )
  {
    Acl = -1073741670;
    goto LABEL_6;
  }
  Acl = RtlCreateAcl(Pool2, v5, 2u);
  if ( Acl < 0 )
  {
LABEL_6:
    if ( v8 )
    {
      CscSeDestroySid(&v11);
      v8 = v11;
    }
    goto LABEL_8;
  }
  while ( *v3 )
  {
    Acl = RtlAddAccessAllowedAce(v8, 2u, *((_DWORD *)v3 + 2), *v3);
    if ( Acl < 0 )
      goto LABEL_6;
    v3 += 2;
  }
LABEL_8:
  *a1 = v8;
  return (unsigned int)Acl;
}

```

## disassembly

```asm
0x14008da04  push    rbx
0x14008da06  push    rsi
0x14008da07  push    rdi
0x14008da08  push    r14
0x14008da0a  sub     rsp, 28h
0x14008da0e  mov     rax, [rdx]
0x14008da11  mov     rdi, rdx
0x14008da14  mov     r14, rcx
0x14008da17  mov     esi, 8
0x14008da1c  test    rax, rax
0x14008da1f  jz      short loc_14008DA44
0x14008da21  mov     rbx, rdx
0x14008da24  mov     rcx, rax; Sid
0x14008da27  call    cs:__imp_RtlLengthSid
0x14008da2e  nop     dword ptr [rax+rax+00h]
0x14008da33  add     eax, 8
0x14008da36  lea     rbx, [rbx+10h]
0x14008da3a  add     esi, eax
0x14008da3c  mov     rax, [rbx]
0x14008da3f  test    rax, rax
0x14008da42  jnz     short loc_14008DA24
0x14008da44  mov     edx, esi
0x14008da46  mov     ecx, 102h
0x14008da4b  mov     r8d, 21407343h
0x14008da51  call    cs:__imp_ExAllocatePool2
0x14008da58  nop     dword ptr [rax+rax+00h]
0x14008da5d  mov     [rsp+48h+arg_0], rax
0x14008da62  mov     rbx, rax
0x14008da65  test    rax, rax
0x14008da68  jnz     short loc_14008DA93
0x14008da6a  mov     esi, 0C000009Ah
0x14008da6f  test    rbx, rbx
0x14008da72  jz      short loc_14008DA83
0x14008da74  lea     rcx, [rsp+48h+arg_0]
0x14008da79  call    CscSeDestroySid
0x14008da7e  mov     rbx, [rsp+48h+arg_0]
0x14008da83  mov     [r14], rbx
0x14008da86  mov     eax, esi
0x14008da88  add     rsp, 28h
0x14008da8c  pop     r14
0x14008da8e  pop     rdi
0x14008da8f  pop     rsi
0x14008da90  pop     rbx
0x14008da91  retn
0x14008da93  mov     r8d, 2; AclRevision
0x14008da99  mov     edx, esi; AclLength
0x14008da9b  mov     rcx, rbx; Acl
0x14008da9e  call    cs:__imp_RtlCreateAcl
0x14008daa5  nop     dword ptr [rax+rax+00h]
0x14008daaa  mov     esi, eax
0x14008daac  test    eax, eax
0x14008daae  jns     short loc_14008DAD7
0x14008dab0  jmp     short loc_14008DA6F
0x14008dab2  mov     r8d, [rdi+8]; AccessMask
0x14008dab6  mov     r9, rax; Sid
0x14008dab9  mov     edx, 2; AceRevision
0x14008dabe  mov     rcx, rbx; Acl
0x14008dac1  call    cs:__imp_RtlAddAccessAllowedAce
0x14008dac8  nop     dword ptr [rax+rax+00h]
0x14008dacd  mov     esi, eax
0x14008dacf  test    eax, eax
0x14008dad1  js      short loc_14008DA6F
0x14008dad3  add     rdi, 10h
0x14008dad7  mov     rax, [rdi]
0x14008dada  test    rax, rax
0x14008dadd  jnz     short loc_14008DAB2
0x14008dadf  jmp     short loc_14008DA83
```
