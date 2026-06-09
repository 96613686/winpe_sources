# FreeAdapter

- ea: `0x14001d39c`
- end: `0x14001d4fa`
- name: `FreeAdapter`
- size: `350`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140001870`
- `0x1400018a0`
- `0x140001920`
- `0x14001d600`
- `0x14001ddf0`

## callees

- `0x14001d39c`

## import_xrefs

- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14001d3d7`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14001d3ea`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14001d3fd`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14001d410`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14001d423`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14001d436`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14001d449`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14001d3d7`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14001d3ea`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14001d3fd`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14001d410`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14001d423`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14001d436`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14001d449`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001d3ba`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001d494`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001d4af`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001d4ca`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001d4e2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001d3ba`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001d494`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001d4af`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001d4ca`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001d4e2`
- `NDIS!NdisFreeNetBufferListPool` at `0x14001d461`
- `NDIS!NdisFreeNetBufferListPool` at `0x14001d479`
- `NDIS!NdisFreeNetBufferListPool` at `0x14001d461`
- `NDIS!NdisFreeNetBufferListPool` at `0x14001d479`

## pseudocode

```c
void __fastcall FreeAdapter(__int64 a1)
{
  __int64 v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx

  v2 = *(_QWORD *)(a1 + 88);
  if ( v2 )
    ExFreePoolWithTag((PVOID)(v2 - 16), 0);
  if ( *(_WORD *)(a1 + 96) )
  {
    ExDeleteNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(a1 + 448));
    ExDeleteNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(a1 + 576));
    ExDeleteNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(a1 + 704));
    ExDeleteNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(a1 + 832));
    ExDeleteNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(a1 + 960));
    ExDeleteNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(a1 + 1088));
    ExDeleteNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(a1 + 1216));
    v3 = *(void **)(a1 + 208);
    if ( v3 )
      NdisFreeNetBufferListPool(v3);
    v4 = *(void **)(a1 + 224);
    if ( v4 )
      NdisFreeNetBufferListPool(v4);
  }
  v5 = *(_QWORD *)(a1 + 48);
  if ( v5 )
    ExFreePoolWithTag((PVOID)(v5 - 16), 0);
  v6 = *(_QWORD *)(a1 + 56);
  if ( v6 )
    ExFreePoolWithTag((PVOID)(v6 - 16), 0);
  v7 = *(_QWORD *)(a1 + 72);
  if ( v7 )
    ExFreePoolWithTag((PVOID)(v7 - 16), 0);
  *(_DWORD *)a1 = 810824268;
  ExFreePoolWithTag((PVOID)(a1 - 16), 0);
}

```

## disassembly

```asm
0x14001d39c  mov     [rsp+arg_0], rbx
0x14001d3a1  push    rdi
0x14001d3a2  sub     rsp, 20h
0x14001d3a6  mov     rbx, rcx
0x14001d3a9  xor     edi, edi
0x14001d3ab  mov     rcx, [rcx+58h]
0x14001d3af  test    rcx, rcx
0x14001d3b2  jz      short loc_14001D3C6
0x14001d3b4  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x14001d3b8  xor     edx, edx; Tag
0x14001d3ba  call    cs:__imp_ExFreePoolWithTag
0x14001d3c1  nop     dword ptr [rax+rax+00h]
0x14001d3c6  cmp     [rbx+60h], di
0x14001d3ca  jz      loc_14001D485
0x14001d3d0  lea     rcx, [rbx+1C0h]; Lookaside
0x14001d3d7  call    cs:__imp_ExDeleteNPagedLookasideList
0x14001d3de  nop     dword ptr [rax+rax+00h]
0x14001d3e3  lea     rcx, [rbx+240h]; Lookaside
0x14001d3ea  call    cs:__imp_ExDeleteNPagedLookasideList
0x14001d3f1  nop     dword ptr [rax+rax+00h]
0x14001d3f6  lea     rcx, [rbx+2C0h]; Lookaside
0x14001d3fd  call    cs:__imp_ExDeleteNPagedLookasideList
0x14001d404  nop     dword ptr [rax+rax+00h]
0x14001d409  lea     rcx, [rbx+340h]; Lookaside
0x14001d410  call    cs:__imp_ExDeleteNPagedLookasideList
0x14001d417  nop     dword ptr [rax+rax+00h]
0x14001d41c  lea     rcx, [rbx+3C0h]; Lookaside
0x14001d423  call    cs:__imp_ExDeleteNPagedLookasideList
0x14001d42a  nop     dword ptr [rax+rax+00h]
0x14001d42f  lea     rcx, [rbx+440h]; Lookaside
0x14001d436  call    cs:__imp_ExDeleteNPagedLookasideList
0x14001d43d  nop     dword ptr [rax+rax+00h]
0x14001d442  lea     rcx, [rbx+4C0h]; Lookaside
0x14001d449  call    cs:__imp_ExDeleteNPagedLookasideList
0x14001d450  nop     dword ptr [rax+rax+00h]
0x14001d455  mov     rcx, [rbx+0D0h]; PoolHandle
0x14001d45c  test    rcx, rcx
0x14001d45f  jz      short loc_14001D46D
0x14001d461  call    cs:__imp_NdisFreeNetBufferListPool
0x14001d468  nop     dword ptr [rax+rax+00h]
0x14001d46d  mov     rcx, [rbx+0E0h]; PoolHandle
0x14001d474  test    rcx, rcx
0x14001d477  jz      short loc_14001D485
0x14001d479  call    cs:__imp_NdisFreeNetBufferListPool
0x14001d480  nop     dword ptr [rax+rax+00h]
0x14001d485  mov     rcx, [rbx+30h]
0x14001d489  test    rcx, rcx
0x14001d48c  jz      short loc_14001D4A0
0x14001d48e  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x14001d492  xor     edx, edx; Tag
0x14001d494  call    cs:__imp_ExFreePoolWithTag
0x14001d49b  nop     dword ptr [rax+rax+00h]
0x14001d4a0  mov     rcx, [rbx+38h]
0x14001d4a4  test    rcx, rcx
0x14001d4a7  jz      short loc_14001D4BB
0x14001d4a9  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x14001d4ad  xor     edx, edx; Tag
0x14001d4af  call    cs:__imp_ExFreePoolWithTag
0x14001d4b6  nop     dword ptr [rax+rax+00h]
0x14001d4bb  mov     rcx, [rbx+48h]
0x14001d4bf  test    rcx, rcx
0x14001d4c2  jz      short loc_14001D4D6
0x14001d4c4  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x14001d4c8  xor     edx, edx; Tag
0x14001d4ca  call    cs:__imp_ExFreePoolWithTag
0x14001d4d1  nop     dword ptr [rax+rax+00h]
0x14001d4d6  lea     rcx, [rbx-10h]; P
0x14001d4da  mov     dword ptr [rbx], 3054324Ch
0x14001d4e0  xor     edx, edx; Tag
0x14001d4e2  call    cs:__imp_ExFreePoolWithTag
0x14001d4e9  nop     dword ptr [rax+rax+00h]
0x14001d4ee  mov     rbx, [rsp+28h+arg_0]
0x14001d4f3  add     rsp, 20h
0x14001d4f7  pop     rdi
0x14001d4f8  retn
```
