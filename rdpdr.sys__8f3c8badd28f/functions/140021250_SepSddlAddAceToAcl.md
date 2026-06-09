# SepSddlAddAceToAcl

- ea: `0x140021250`
- end: `0x14002133b`
- name: `SepSddlAddAceToAcl`
- size: `235`
- prototype: `__int64 __fastcall(int, int, int, int, ACCESS_MASK AccessMask, int, PSID Sid)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x140021428`

## callees

- `0x1400065c0`
- `0x1400068c0`
- `0x140021250`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400212ee`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400212ee`
- `ntoskrnl!RtlLengthSid` at `0x140021274`
- `ntoskrnl!RtlLengthSid` at `0x140021274`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14002131d`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x14002131d`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400212ae`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400212ae`

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
0x140021250  push    rbx
0x140021252  push    rbp
0x140021253  push    rsi
0x140021254  push    rdi
0x140021255  push    r12
0x140021257  push    r13
0x140021259  push    r14
0x14002125b  push    r15
0x14002125d  sub     rsp, 28h
0x140021261  mov     rdi, [rcx]
0x140021264  mov     r15, rcx
0x140021267  mov     rcx, [rsp+68h+Sid]; Sid
0x14002126f  mov     r14, rdx
0x140021272  mov     esi, [rdx]
0x140021274  call    cs:__imp_RtlLengthSid
0x14002127b  nop     dword ptr [rax+rax+00h]
0x140021280  lea     r8d, [rax+8]
0x140021284  movzx   eax, word ptr [rdi+2]
0x140021288  lea     ebp, [r8+rsi]
0x14002128c  cmp     ebp, eax
0x14002128e  jbe     short loc_1400212FF
0x140021290  imul    r8d, [rsp+68h+arg_28]
0x140021299  mov     ecx, 1; PoolType
0x14002129e  lea     r12d, [r8+rsi]
0x1400212a2  mov     r8d, 6C416553h; Tag
0x1400212a8  mov     edx, r12d; NumberOfBytes
0x1400212ab  mov     r13d, r12d
0x1400212ae  call    cs:__imp_ExAllocatePoolWithTag
0x1400212b5  nop     dword ptr [rax+rax+00h]
0x1400212ba  mov     rbx, rax
0x1400212bd  test    rax, rax
0x1400212c0  jnz     short loc_1400212C9
0x1400212c2  mov     eax, 0C000009Ah
0x1400212c7  jmp     short loc_140021329
0x1400212c9  mov     r8, r13; Size
0x1400212cc  xor     edx, edx; Val
0x1400212ce  mov     rcx, rbx; void *
0x1400212d1  call    memset
0x1400212d6  mov     rdx, [r15]; Src
0x1400212d9  mov     r8, rsi; Size
0x1400212dc  mov     rcx, rbx; void *
0x1400212df  call    memmove
0x1400212e4  xor     edx, edx; Tag
0x1400212e6  mov     [rbx+2], r12w
0x1400212eb  mov     rcx, rdi; P
0x1400212ee  call    cs:__imp_ExFreePoolWithTag
0x1400212f5  nop     dword ptr [rax+rax+00h]
0x1400212fa  mov     [r15], rbx
0x1400212fd  jmp     short loc_140021302
0x1400212ff  mov     rbx, rdi
0x140021302  mov     r9, [rsp+68h+Sid]; Sid
0x14002130a  mov     edx, 2; AceRevision
0x14002130f  mov     r8d, [rsp+68h+AccessMask]; AccessMask
0x140021317  mov     rcx, rbx; Acl
0x14002131a  mov     [r14], ebp
0x14002131d  call    cs:__imp_RtlAddAccessAllowedAce
0x140021324  nop     dword ptr [rax+rax+00h]
0x140021329  add     rsp, 28h
0x14002132d  pop     r15
0x14002132f  pop     r14
0x140021331  pop     r13
0x140021333  pop     r12
0x140021335  pop     rdi
0x140021336  pop     rsi
0x140021337  pop     rbp
0x140021338  pop     rbx
0x140021339  retn
```
