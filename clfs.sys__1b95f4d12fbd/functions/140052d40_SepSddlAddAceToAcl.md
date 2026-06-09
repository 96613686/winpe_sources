# SepSddlAddAceToAcl

- ea: `0x140052d40`
- end: `0x140052e2b`
- name: `SepSddlAddAceToAcl`
- size: `235`
- prototype: `__int64 __fastcall(int, int, int, int, ACCESS_MASK AccessMask, int, PSID Sid)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x140052f18`

## callees

- `0x140017f80`
- `0x140018280`
- `0x140052d40`

## import_xrefs

- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140052e0d`
- `ntoskrnl!RtlAddAccessAllowedAce` at `0x140052e0d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140052dde`
- `ntoskrnl!ExFreePoolWithTag` at `0x140052dde`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140052d9e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140052d9e`
- `ntoskrnl!RtlLengthSid` at `0x140052d64`
- `ntoskrnl!RtlLengthSid` at `0x140052d64`

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
0x140052d40  push    rbx
0x140052d42  push    rbp
0x140052d43  push    rsi
0x140052d44  push    rdi
0x140052d45  push    r12
0x140052d47  push    r13
0x140052d49  push    r14
0x140052d4b  push    r15
0x140052d4d  sub     rsp, 28h
0x140052d51  mov     rdi, [rcx]
0x140052d54  mov     r15, rcx
0x140052d57  mov     rcx, [rsp+68h+Sid]; Sid
0x140052d5f  mov     r14, rdx
0x140052d62  mov     esi, [rdx]
0x140052d64  call    cs:__imp_RtlLengthSid
0x140052d6b  nop     dword ptr [rax+rax+00h]
0x140052d70  lea     r8d, [rax+8]
0x140052d74  movzx   eax, word ptr [rdi+2]
0x140052d78  lea     ebp, [r8+rsi]
0x140052d7c  cmp     ebp, eax
0x140052d7e  jbe     short loc_140052DEF
0x140052d80  imul    r8d, [rsp+68h+arg_28]
0x140052d89  mov     ecx, 1; PoolType
0x140052d8e  lea     r12d, [r8+rsi]
0x140052d92  mov     r8d, 6C416553h; Tag
0x140052d98  mov     edx, r12d; NumberOfBytes
0x140052d9b  mov     r13d, r12d
0x140052d9e  call    cs:__imp_ExAllocatePoolWithTag
0x140052da5  nop     dword ptr [rax+rax+00h]
0x140052daa  mov     rbx, rax
0x140052dad  test    rax, rax
0x140052db0  jnz     short loc_140052DB9
0x140052db2  mov     eax, 0C000009Ah
0x140052db7  jmp     short loc_140052E19
0x140052db9  mov     r8, r13; Size
0x140052dbc  xor     edx, edx; Val
0x140052dbe  mov     rcx, rbx; void *
0x140052dc1  call    memset
0x140052dc6  mov     rdx, [r15]; Src
0x140052dc9  mov     r8, rsi; Size
0x140052dcc  mov     rcx, rbx; void *
0x140052dcf  call    memmove
0x140052dd4  xor     edx, edx; Tag
0x140052dd6  mov     [rbx+2], r12w
0x140052ddb  mov     rcx, rdi; P
0x140052dde  call    cs:__imp_ExFreePoolWithTag
0x140052de5  nop     dword ptr [rax+rax+00h]
0x140052dea  mov     [r15], rbx
0x140052ded  jmp     short loc_140052DF2
0x140052def  mov     rbx, rdi
0x140052df2  mov     r9, [rsp+68h+Sid]; Sid
0x140052dfa  mov     edx, 2; AceRevision
0x140052dff  mov     r8d, [rsp+68h+AccessMask]; AccessMask
0x140052e07  mov     rcx, rbx; Acl
0x140052e0a  mov     [r14], ebp
0x140052e0d  call    cs:__imp_RtlAddAccessAllowedAce
0x140052e14  nop     dword ptr [rax+rax+00h]
0x140052e19  add     rsp, 28h
0x140052e1d  pop     r15
0x140052e1f  pop     r14
0x140052e21  pop     r13
0x140052e23  pop     r12
0x140052e25  pop     rdi
0x140052e26  pop     rsi
0x140052e27  pop     rbp
0x140052e28  pop     rbx
0x140052e29  retn
```
