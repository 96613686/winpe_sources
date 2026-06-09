# NdisWanFreeSendResources

- ea: `0x14000f254`
- end: `0x14000f2c7`
- name: `NdisWanFreeSendResources`
- size: `115`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x140004ab8`

## callees

- `0x14000f254`

## import_xrefs

- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14000f28b`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x14000f28b`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14000f273`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14000f273`
- `NDIS!NdisFreeMemory` at `0x14000f2b1`
- `NDIS!NdisFreeMemory` at `0x14000f2b1`

## pseudocode

```c
void __fastcall NdisWanFreeSendResources(__int64 a1)
{
  PVOID *v1; // rdi
  PVOID v3; // rsi

  v1 = (PVOID *)(a1 + 320);
  if ( *(_DWORD *)(a1 + 188) )
  {
    v3 = *v1;
    while ( ExpInterlockedPopEntrySList((PSLIST_HEADER)(a1 + 336)) )
      ;
    if ( v3 )
      NdisFreeMemory(*v1, *(_DWORD *)(a1 + 328), *(_DWORD *)(a1 + 188));
  }
  else
  {
    ExDeleteNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(a1 + 320));
  }
}

```

## disassembly

```asm
0x14000f254  push    rbx
0x14000f256  push    rbp
0x14000f257  push    rsi
0x14000f258  push    rdi
0x14000f259  sub     rsp, 28h
0x14000f25d  cmp     dword ptr [rcx+0BCh], 0
0x14000f264  lea     rdi, [rcx+140h]
0x14000f26b  mov     rbx, rcx
0x14000f26e  jnz     short loc_14000F281
0x14000f270  mov     rcx, rdi; Lookaside
0x14000f273  call    cs:__imp_ExDeleteNPagedLookasideList
0x14000f27a  nop     dword ptr [rax+rax+00h]
0x14000f27f  jmp     short loc_14000F2BD
0x14000f281  mov     rsi, [rdi]
0x14000f284  lea     rcx, [rbx+150h]; ListHead
0x14000f28b  call    cs:__imp_ExpInterlockedPopEntrySList
0x14000f292  nop     dword ptr [rax+rax+00h]
0x14000f297  test    rax, rax
0x14000f29a  jnz     short loc_14000F284
0x14000f29c  test    rsi, rsi
0x14000f29f  jz      short loc_14000F2BD
0x14000f2a1  mov     r8d, [rbx+0BCh]; MemoryFlags
0x14000f2a8  mov     edx, [rbx+148h]; Length
0x14000f2ae  mov     rcx, [rdi]; VirtualAddress
0x14000f2b1  call    cs:__imp_NdisFreeMemory
0x14000f2b8  nop     dword ptr [rax+rax+00h]
0x14000f2bd  add     rsp, 28h
0x14000f2c1  pop     rdi
0x14000f2c2  pop     rsi
0x14000f2c3  pop     rbp
0x14000f2c4  pop     rbx
0x14000f2c5  retn
```
