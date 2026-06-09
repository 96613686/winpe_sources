# InsertContextEntry

- ea: `0x18004f898`
- end: `0x18004f995`
- name: `InsertContextEntry`
- size: `253`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x18004f6c4`

## callees

- `0x18004f898`

## import_xrefs

- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x18004f921`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x18004f921`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x18004f957`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x18004f957`

## pseudocode

```c
__int64 __fastcall InsertContextEntry(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v5; // esi

  *(_QWORD *)a2 = a1;
  *(_QWORD *)(a2 + 8) = *(_QWORD *)(a3 + 8);
  *(_WORD *)(a2 + 24) = *(_WORD *)a3;
  if ( *(_QWORD *)(a3 + 32) )
  {
    *(_BYTE *)(a2 + 27) = 3;
    *(_QWORD *)(a2 + 32) = *(_QWORD *)(a3 + 32);
    *(_QWORD *)(a2 + 40) = *(_QWORD *)(a3 + 40);
    return 48;
  }
  if ( *(_QWORD *)(a3 + 16) == -1 )
  {
    *(_BYTE *)(a2 + 27) = 2;
    *(_DWORD *)(a2 + 32) = *(_DWORD *)(a3 + 24);
    return 48;
  }
  *(_BYTE *)(a2 + 27) = 1;
  v5 = 320;
  if ( (*(_BYTE *)(a3 + 2) & 1) != 0 )
    *(_BYTE *)(a2 + 26) |= 2u;
  ExInitializeNPagedLookasideList(
    (PNPAGED_LOOKASIDE_LIST)(a2 + 64),
    0,
    0,
    0x200u,
    *(_QWORD *)(a3 + 16) + 96LL,
    *(_DWORD *)(a3 + 24),
    0);
  ExInitializePagedLookasideList(
    (PPAGED_LOOKASIDE_LIST)(a2 + 192),
    0,
    0,
    0,
    *(_QWORD *)(a3 + 16) + 96LL,
    *(_DWORD *)(a3 + 24),
    0);
  *(_BYTE *)(a2 + 26) |= 1u;
  return v5;
}

```

## disassembly

```asm
0x18004f898  mov     [rsp+arg_0], rbx
0x18004f89d  mov     [rsp+arg_8], rsi
0x18004f8a2  push    rdi
0x18004f8a3  sub     rsp, 40h
0x18004f8a7  mov     [rdx], rcx
0x18004f8aa  mov     rdi, r8
0x18004f8ad  mov     rax, [r8+8]
0x18004f8b1  mov     rbx, rdx
0x18004f8b4  mov     [rdx+8], rax
0x18004f8b8  movzx   eax, word ptr [r8]
0x18004f8bc  mov     [rdx+18h], ax
0x18004f8c0  cmp     qword ptr [r8+20h], 0
0x18004f8c5  jnz     loc_18004F969
0x18004f8cb  cmp     qword ptr [r8+10h], 0FFFFFFFFFFFFFFFFh
0x18004f8d0  jnz     short loc_18004F8E2
0x18004f8d2  mov     byte ptr [rdx+1Bh], 2
0x18004f8d6  mov     eax, [r8+18h]
0x18004f8da  mov     [rdx+20h], eax
0x18004f8dd  jmp     loc_18004F97D
0x18004f8e2  mov     byte ptr [rdx+1Bh], 1
0x18004f8e6  mov     esi, 140h
0x18004f8eb  test    byte ptr [r8+2], 1
0x18004f8f0  jz      short loc_18004F8F6
0x18004f8f2  or      byte ptr [rdx+1Ah], 2
0x18004f8f6  mov     rdx, [r8+10h]
0x18004f8fa  lea     rcx, [rbx+40h]; Lookaside
0x18004f8fe  xor     eax, eax
0x18004f900  add     rdx, 60h ; '`'
0x18004f904  mov     [rsp+48h+Depth], ax; Depth
0x18004f909  mov     r9d, 200h; Flags
0x18004f90f  mov     eax, [r8+18h]
0x18004f913  xor     r8d, r8d; Free
0x18004f916  mov     [rsp+48h+Tag], eax; Tag
0x18004f91a  mov     [rsp+48h+Size], rdx; Size
0x18004f91f  xor     edx, edx; Allocate
0x18004f921  call    cs:__imp_ExInitializeNPagedLookasideList
0x18004f928  nop     dword ptr [rax+rax+00h]
0x18004f92d  mov     rdx, [rdi+10h]
0x18004f931  lea     rcx, [rbx+0C0h]; Lookaside
0x18004f938  xor     eax, eax
0x18004f93a  add     rdx, 60h ; '`'
0x18004f93e  mov     [rsp+48h+Depth], ax; Depth
0x18004f943  xor     r9d, r9d; Flags
0x18004f946  mov     eax, [rdi+18h]
0x18004f949  xor     r8d, r8d; Free
0x18004f94c  mov     [rsp+48h+Tag], eax; Tag
0x18004f950  mov     [rsp+48h+Size], rdx; Size
0x18004f955  xor     edx, edx; Allocate
0x18004f957  call    cs:__imp_ExInitializePagedLookasideList
0x18004f95e  nop     dword ptr [rax+rax+00h]
0x18004f963  or      byte ptr [rbx+1Ah], 1
0x18004f967  jmp     short loc_18004F982
0x18004f969  mov     byte ptr [rdx+1Bh], 3
0x18004f96d  mov     rcx, [r8+20h]
0x18004f971  mov     [rdx+20h], rcx
0x18004f975  mov     rcx, [r8+28h]
0x18004f979  mov     [rdx+28h], rcx
0x18004f97d  mov     esi, 30h ; '0'
0x18004f982  mov     rbx, [rsp+48h+arg_0]
0x18004f987  mov     eax, esi
0x18004f989  mov     rsi, [rsp+48h+arg_8]
0x18004f98e  add     rsp, 40h
0x18004f992  pop     rdi
0x18004f993  retn
```
