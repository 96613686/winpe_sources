# SepSddlAddAceToAcl

- ea: `0x140017b10`
- end: `0x140017bfb`
- name: `SepSddlAddAceToAcl`
- size: `235`
- prototype: `__int64 __fastcall(int, int, int, int, ACCESS_MASK AccessMask, int, PSID Sid)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x140017ce8`

## callees

- `0x1400081c0`
- `0x1400084c0`
- `0x140017b10`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140017bae`
- `ntoskrnl!ExFreePoolWithTag` at `0x140017bae`
- `ntoskrnl!RtlLengthSid` at `0x140017b34`
- `ntoskrnl!RtlLengthSid` at `0x140017b34`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140017bdd`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140017bdd`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140017b6e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140017b6e`

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
0x140017b10  push    rbx
0x140017b12  push    rbp
0x140017b13  push    rsi
0x140017b14  push    rdi
0x140017b15  push    r12
0x140017b17  push    r13
0x140017b19  push    r14
0x140017b1b  push    r15
0x140017b1d  sub     rsp, 28h
0x140017b21  mov     rdi, [rcx]
0x140017b24  mov     r15, rcx
0x140017b27  mov     rcx, [rsp+68h+Sid]; Sid
0x140017b2f  mov     r14, rdx
0x140017b32  mov     esi, [rdx]
0x140017b34  call    cs:__imp_RtlLengthSid
0x140017b3b  nop     dword ptr [rax+rax+00h]
0x140017b40  lea     r8d, [rax+8]
0x140017b44  movzx   eax, word ptr [rdi+2]
0x140017b48  lea     ebp, [r8+rsi]
0x140017b4c  cmp     ebp, eax
0x140017b4e  jbe     short loc_140017BBF
0x140017b50  imul    r8d, [rsp+68h+arg_28]
0x140017b59  mov     ecx, 1; PoolType
0x140017b5e  lea     r12d, [r8+rsi]
0x140017b62  mov     r8d, 6C416553h; Tag
0x140017b68  mov     edx, r12d; NumberOfBytes
0x140017b6b  mov     r13d, r12d
0x140017b6e  call    cs:__imp_ExAllocatePoolWithTag
0x140017b75  nop     dword ptr [rax+rax+00h]
0x140017b7a  mov     rbx, rax
0x140017b7d  test    rax, rax
0x140017b80  jnz     short loc_140017B89
0x140017b82  mov     eax, 0C000009Ah
0x140017b87  jmp     short loc_140017BE9
0x140017b89  mov     r8, r13; Size
0x140017b8c  xor     edx, edx; Val
0x140017b8e  mov     rcx, rbx; void *
0x140017b91  call    memset
0x140017b96  mov     rdx, [r15]; Src
0x140017b99  mov     r8, rsi; Size
0x140017b9c  mov     rcx, rbx; void *
0x140017b9f  call    memmove
0x140017ba4  xor     edx, edx; Tag
0x140017ba6  mov     [rbx+2], r12w
0x140017bab  mov     rcx, rdi; P
0x140017bae  call    cs:__imp_ExFreePoolWithTag
0x140017bb5  nop     dword ptr [rax+rax+00h]
0x140017bba  mov     [r15], rbx
0x140017bbd  jmp     short loc_140017BC2
0x140017bbf  mov     rbx, rdi
0x140017bc2  mov     r9, [rsp+68h+Sid]; Sid
0x140017bca  mov     edx, 2; AceRevision
0x140017bcf  mov     r8d, [rsp+68h+AccessMask]; AccessMask
0x140017bd7  mov     rcx, rbx; Acl
0x140017bda  mov     [r14], ebp
0x140017bdd  call    cs:__imp_RtlAddAccessAllowedAce
0x140017be4  nop     dword ptr [rax+rax+00h]
0x140017be9  add     rsp, 28h
0x140017bed  pop     r15
0x140017bef  pop     r14
0x140017bf1  pop     r13
0x140017bf3  pop     r12
0x140017bf5  pop     rdi
0x140017bf6  pop     rsi
0x140017bf7  pop     rbp
0x140017bf8  pop     rbx
0x140017bf9  retn
```
