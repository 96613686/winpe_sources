# InternalSecurityContext::AdjustBuffers(SecurityContextRetrievalState const &)

- ea: `0x180016348`
- end: `0x1800163e5`
- name: `?AdjustBuffers@InternalSecurityContext@@QEAAXAEBUSecurityContextRetrievalState@@@Z`
- size: `157`
- prototype: `void __fastcall(InternalSecurityContext *__hidden this, const struct SecurityContextRetrievalState *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001b398`

## callees

- `0x180016348`
- `0x180021010`

## import_xrefs

- `msvcrt!free` at `0x180016364`
- `msvcrt!free` at `0x180016388`
- `msvcrt!free` at `0x1800163ab`
- `msvcrt!free` at `0x180016364`
- `msvcrt!free` at `0x180016388`
- `msvcrt!free` at `0x1800163ab`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall InternalSecurityContext::AdjustBuffers(void **this, const struct SecurityContextRetrievalState *a2)
{
  unsigned __int64 v4; // rax

  if ( *((_DWORD *)this + 11) < *((_DWORD *)a2 + 1) )
  {
    free(this[1]);
    this[1] = MmAllocate(*((unsigned int *)a2 + 1));
    *((_DWORD *)this + 11) = *((_DWORD *)a2 + 1);
  }
  if ( *((_DWORD *)this + 12) < *(_DWORD *)a2 )
  {
    free(this[2]);
    this[2] = MmAllocate(*(unsigned int *)a2);
    *((_DWORD *)this + 12) = *(_DWORD *)a2;
  }
  if ( *((_DWORD *)this + 13) < *((_DWORD *)a2 + 2) )
  {
    free(this[3]);
    v4 = 2LL * *((unsigned int *)a2 + 2);
    if ( !is_mul_ok(*((unsigned int *)a2 + 2), 2u) )
      v4 = -1;
    this[3] = MmAllocate(v4);
    *((_DWORD *)this + 13) = *((_DWORD *)a2 + 2);
  }
}

```

## disassembly

```asm
0x180016348  mov     [rsp+arg_0], rbx
0x18001634d  push    rdi
0x18001634e  sub     rsp, 20h
0x180016352  mov     rdi, rdx
0x180016355  mov     rbx, rcx
0x180016358  mov     eax, [rdx+4]
0x18001635b  cmp     [rcx+2Ch], eax
0x18001635e  jnb     short loc_18001637D
0x180016360  mov     rcx, [rcx+8]; Block
0x180016364  call    cs:__imp_free
0x18001636a  nop
0x18001636b  mov     ecx, [rdi+4]; unsigned __int64
0x18001636e  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180016373  mov     [rbx+8], rax
0x180016377  mov     eax, [rdi+4]
0x18001637a  mov     [rbx+2Ch], eax
0x18001637d  mov     eax, [rdi]
0x18001637f  cmp     [rbx+30h], eax
0x180016382  jnb     short loc_18001639F
0x180016384  mov     rcx, [rbx+10h]; Block
0x180016388  call    cs:__imp_free
0x18001638e  nop
0x18001638f  mov     ecx, [rdi]; unsigned __int64
0x180016391  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180016396  mov     [rbx+10h], rax
0x18001639a  mov     eax, [rdi]
0x18001639c  mov     [rbx+30h], eax
0x18001639f  mov     eax, [rdi+8]
0x1800163a2  cmp     [rbx+34h], eax
0x1800163a5  jnb     short loc_1800163DA
0x1800163a7  mov     rcx, [rbx+18h]; Block
0x1800163ab  call    cs:__imp_free
0x1800163b1  nop
0x1800163b2  mov     ecx, [rdi+8]
0x1800163b5  mov     eax, 2
0x1800163ba  mul     rcx
0x1800163bd  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800163c4  cmovb   rax, rcx
0x1800163c8  mov     rcx, rax; unsigned __int64
0x1800163cb  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x1800163d0  mov     [rbx+18h], rax
0x1800163d4  mov     eax, [rdi+8]
0x1800163d7  mov     [rbx+34h], eax
0x1800163da  mov     rbx, [rsp+28h+arg_0]
0x1800163df  add     rsp, 20h
0x1800163e3  pop     rdi
0x1800163e4  retn
```
