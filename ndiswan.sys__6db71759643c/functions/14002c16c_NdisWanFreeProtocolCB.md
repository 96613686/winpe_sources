# NdisWanFreeProtocolCB

- ea: `0x14002c16c`
- end: `0x14002c1f7`
- name: `NdisWanFreeProtocolCB`
- size: `139`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000d0c0`
- `0x1400254c8`
- `0x140026c80`
- `0x140027a50`

## callees

- `0x140005728`
- `0x14002c16c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14002c18d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002c1c9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002c18d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002c1c9`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14002c1df`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14002c1df`

## pseudocode

```c
void __fastcall NdisWanFreeProtocolCB(PVOID *Entry)
{
  PVOID v2; // rcx

  if ( *((_WORD *)Entry + 136) )
    ExFreePoolWithTag(Entry[35], 0);
  if ( *((_WORD *)Entry + 144) )
    NdisWanFreeNdisString();
  if ( *((_WORD *)Entry + 128) )
    NdisWanFreeNdisString();
  v2 = Entry[42];
  if ( v2 )
    ExFreePoolWithTag(v2, 0);
  ExFreeToNPagedLookasideList(&LinkProtoCBList, Entry);
}

```

## disassembly

```asm
0x14002c16c  mov     [rsp+arg_0], rbx
0x14002c171  push    rdi
0x14002c172  sub     rsp, 20h
0x14002c176  xor     edi, edi
0x14002c178  mov     rbx, rcx
0x14002c17b  cmp     [rcx+110h], di
0x14002c182  jz      short loc_14002C199
0x14002c184  mov     rcx, [rcx+118h]; P
0x14002c18b  xor     edx, edx; Tag
0x14002c18d  call    cs:__imp_ExFreePoolWithTag
0x14002c194  nop     dword ptr [rax+rax+00h]
0x14002c199  lea     rcx, [rbx+120h]
0x14002c1a0  cmp     [rcx], di
0x14002c1a3  jz      short loc_14002C1AA
0x14002c1a5  call    NdisWanFreeNdisString
0x14002c1aa  lea     rcx, [rbx+100h]
0x14002c1b1  cmp     [rcx], di
0x14002c1b4  jz      short loc_14002C1BB
0x14002c1b6  call    NdisWanFreeNdisString
0x14002c1bb  mov     rcx, [rbx+150h]; P
0x14002c1c2  test    rcx, rcx
0x14002c1c5  jz      short loc_14002C1D5
0x14002c1c7  xor     edx, edx; Tag
0x14002c1c9  call    cs:__imp_ExFreePoolWithTag
0x14002c1d0  nop     dword ptr [rax+rax+00h]
0x14002c1d5  mov     rdx, rbx; Entry
0x14002c1d8  lea     rcx, LinkProtoCBList; Lookaside
0x14002c1df  call    cs:__imp_ExFreeToNPagedLookasideList
0x14002c1e6  nop     dword ptr [rax+rax+00h]
0x14002c1eb  mov     rbx, [rsp+28h+arg_0]
0x14002c1f0  add     rsp, 20h
0x14002c1f4  pop     rdi
0x14002c1f5  retn
```
