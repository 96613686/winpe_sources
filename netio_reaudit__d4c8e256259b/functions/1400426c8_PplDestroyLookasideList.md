# PplDestroyLookasideList

- ea: `0x1400426c8`
- end: `0x140042730`
- name: `PplDestroyLookasideList`
- size: `104`
- prototype: `__int64 __fastcall(PVOID P, ULONG Tag)`
- caller_count: `7`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1400426b0`
- `0x1400527f4`
- `0x1400529ec`
- `0x1400737d4`
- `0x140073fe0`
- `0x1400742d0`
- `0x140074d0c`

## callees

- `0x1400426c8`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140042713`
- `ntoskrnl!ExFreePoolWithTag` at `0x140042713`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x140042700`
- `ntoskrnl!ExDeleteLookasideListEx` at `0x140042700`

## pseudocode

```c
void __fastcall PplDestroyLookasideList(char *P, ULONG Tag)
{
  unsigned int v2; // edi
  unsigned __int64 v5; // rcx

  if ( P )
  {
    v2 = *(_DWORD *)P;
    while ( (--v2 & 0x80000000) == 0 )
    {
      v5 = (unsigned __int64)v2 << 7;
      if ( P[v5 + 176] )
        ExDeleteLookasideListEx((PLOOKASIDE_LIST_EX)&P[v5 + 64]);
    }
    ExFreePoolWithTag(P, Tag);
  }
}

```

## disassembly

```asm
0x1400426c8  test    rcx, rcx
0x1400426cb  jz      short locret_14004272E
0x1400426cd  mov     [rsp+arg_0], rbx
0x1400426d2  mov     [rsp+arg_8], rsi
0x1400426d7  push    rdi
0x1400426d8  sub     rsp, 20h
0x1400426dc  mov     edi, [rcx]
0x1400426de  mov     esi, edx
0x1400426e0  mov     rbx, rcx
0x1400426e3  sub     edi, 1
0x1400426e6  js      short loc_14004270E
0x1400426e8  mov     ecx, edi
0x1400426ea  shl     rcx, 7
0x1400426ee  mov     al, [rcx+rbx+0B0h]
0x1400426f5  test    al, al
0x1400426f7  jz      short loc_1400426E3
0x1400426f9  add     rcx, 40h ; '@'
0x1400426fd  add     rcx, rbx; Lookaside
0x140042700  call    cs:__imp_ExDeleteLookasideListEx
0x140042707  nop     dword ptr [rax+rax+00h]
0x14004270c  jmp     short loc_1400426E3
0x14004270e  mov     edx, esi; Tag
0x140042710  mov     rcx, rbx; P
0x140042713  call    cs:__imp_ExFreePoolWithTag
0x14004271a  nop     dword ptr [rax+rax+00h]
0x14004271f  mov     rbx, [rsp+28h+arg_0]
0x140042724  mov     rsi, [rsp+28h+arg_8]
0x140042729  add     rsp, 20h
0x14004272d  pop     rdi
0x14004272e  retn
```
