# SepSddlAddAceToAcl

- ea: `0x140150380`
- end: `0x14015046b`
- name: `SepSddlAddAceToAcl`
- size: `235`
- prototype: `__int64 __fastcall(int, int, int, int, ACCESS_MASK AccessMask, int, PSID Sid)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x140150558`

## callees

- `0x1400e62c0`
- `0x1400e65c0`
- `0x140150380`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x1401503de`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1401503de`
- `ntoskrnl!RtlLengthSid` at `0x1401503a4`
- `ntoskrnl!RtlLengthSid` at `0x1401503a4`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14015044d`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14015044d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14015041e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14015041e`

## pseudocode

```c
NTSTATUS __fastcall SepSddlAddAceToAcl(
        const void **a1,
        _DWORD *a2,
        __int64 a3,
        __int64 a4,
        ACCESS_MASK AccessMask,
        int a6,
        PSID Sid)
{
  unsigned __int16 *v7; // rdi
  size_t v10; // rsi
  ULONG v11; // r8d
  int v12; // ebp
  unsigned int v13; // r12d
  struct _ACL *PoolWithTag; // rax
  struct _ACL *v15; // rbx

  v7 = (unsigned __int16 *)*a1;
  v10 = (unsigned int)*a2;
  v11 = RtlLengthSid(Sid) + 8;
  v12 = v11 + v10;
  if ( v11 + (unsigned int)v10 <= v7[1] )
  {
    v15 = (struct _ACL *)v7;
  }
  else
  {
    v13 = a6 * v11 + v10;
    PoolWithTag = (struct _ACL *)ExAllocatePoolWithTag(PagedPool, v13, 0x6C416553u);
    v15 = PoolWithTag;
    if ( !PoolWithTag )
      return -1073741670;
    memset(PoolWithTag, 0, v13);
    memmove(v15, *a1, v10);
    v15->AclSize = v13;
    ExFreePoolWithTag(v7, 0);
    *a1 = v15;
  }
  *a2 = v12;
  return RtlAddAccessAllowedAce(v15, 2u, AccessMask, Sid);
}

```

## disassembly

```asm
0x140150380  push    rbx
0x140150382  push    rbp
0x140150383  push    rsi
0x140150384  push    rdi
0x140150385  push    r12
0x140150387  push    r13
0x140150389  push    r14
0x14015038b  push    r15
0x14015038d  sub     rsp, 28h
0x140150391  mov     rdi, [rcx]
0x140150394  mov     r15, rcx
0x140150397  mov     rcx, [rsp+68h+Sid]; Sid
0x14015039f  mov     r14, rdx
0x1401503a2  mov     esi, [rdx]
0x1401503a4  call    cs:__imp_RtlLengthSid
0x1401503ab  nop     dword ptr [rax+rax+00h]
0x1401503b0  lea     r8d, [rax+8]
0x1401503b4  movzx   eax, word ptr [rdi+2]
0x1401503b8  lea     ebp, [r8+rsi]
0x1401503bc  cmp     ebp, eax
0x1401503be  jbe     short loc_14015042F
0x1401503c0  imul    r8d, [rsp+68h+arg_28]
0x1401503c9  mov     ecx, 1; PoolType
0x1401503ce  lea     r12d, [r8+rsi]
0x1401503d2  mov     r8d, 6C416553h; Tag
0x1401503d8  mov     edx, r12d; NumberOfBytes
0x1401503db  mov     r13d, r12d
0x1401503de  call    cs:__imp_ExAllocatePoolWithTag
0x1401503e5  nop     dword ptr [rax+rax+00h]
0x1401503ea  mov     rbx, rax
0x1401503ed  test    rax, rax
0x1401503f0  jnz     short loc_1401503F9
0x1401503f2  mov     eax, 0C000009Ah
0x1401503f7  jmp     short loc_140150459
0x1401503f9  mov     r8, r13; Size
0x1401503fc  xor     edx, edx; Val
0x1401503fe  mov     rcx, rbx; void *
0x140150401  call    memset
0x140150406  mov     rdx, [r15]; Src
0x140150409  mov     r8, rsi; Size
0x14015040c  mov     rcx, rbx; void *
0x14015040f  call    memmove
0x140150414  xor     edx, edx; Tag
0x140150416  mov     [rbx+2], r12w
0x14015041b  mov     rcx, rdi; P
0x14015041e  call    cs:__imp_ExFreePoolWithTag
0x140150425  nop     dword ptr [rax+rax+00h]
0x14015042a  mov     [r15], rbx
0x14015042d  jmp     short loc_140150432
0x14015042f  mov     rbx, rdi
0x140150432  mov     r9, [rsp+68h+Sid]; Sid
0x14015043a  mov     edx, 2; AceRevision
0x14015043f  mov     r8d, [rsp+68h+AccessMask]; AccessMask
0x140150447  mov     rcx, rbx; Acl
0x14015044a  mov     [r14], ebp
0x14015044d  call    cs:__imp_RtlAddAccessAllowedAce
0x140150454  nop     dword ptr [rax+rax+00h]
0x140150459  add     rsp, 28h
0x14015045d  pop     r15
0x14015045f  pop     r14
0x140150461  pop     r13
0x140150463  pop     r12
0x140150465  pop     rdi
0x140150466  pop     rsi
0x140150467  pop     rbp
0x140150468  pop     rbx
0x140150469  retn
```
