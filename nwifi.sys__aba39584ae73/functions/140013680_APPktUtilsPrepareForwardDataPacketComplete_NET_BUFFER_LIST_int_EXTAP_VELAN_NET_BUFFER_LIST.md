# APPktUtilsPrepareForwardDataPacketComplete(_NET_BUFFER_LIST *,int,_EXTAP_VELAN *,_NET_BUFFER_LIST *)

- ea: `0x140013680`
- end: `0x14001370f`
- name: `?APPktUtilsPrepareForwardDataPacketComplete@@YAXPEAU_NET_BUFFER_LIST@@HPEAU_EXTAP_VELAN@@0@Z`
- size: `143`
- prototype: `void(struct _NET_BUFFER_LIST *, int, struct _EXTAP_VELAN *, struct _NET_BUFFER_LIST *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140013680`
- `0x140013720`
- `0x140013acc`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400136ca`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400136ca`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400136db`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400136db`
- `ntoskrnl!IoFreeMdl` at `0x1400136ea`
- `ntoskrnl!IoFreeMdl` at `0x1400136ea`
- `NDIS!NdisFreeNetBuffer` at `0x1400136a2`
- `NDIS!NdisFreeNetBuffer` at `0x1400136a2`

## pseudocode

```c
void __fastcall APPktUtilsPrepareForwardDataPacketComplete(
        struct _NET_BUFFER_LIST *a1,
        __int64 a2,
        struct _EXTAP_VELAN *a3,
        struct _NET_BUFFER_LIST *a4)
{
  _NET_BUFFER *FirstNetBuffer; // rcx
  struct _MDL **p_Next; // rbx
  struct _MDL *v7; // rsi
  struct _ADAPT *v8; // rcx
  unsigned int v9; // r8d
  struct _NET_BUFFER_LIST *v10; // [rsp+30h] [rbp+8h] BYREF

  v10 = a1;
  FirstNetBuffer = a1->FirstNetBuffer;
  p_Next = &FirstNetBuffer->MdlChain->$2B32BF05D450FAC80B24E3AD8AA9CFC0::$66F4520F2EE7490CF03BA23FE18496AB::Next;
  v7 = *p_Next;
  NdisFreeNetBuffer(FirstNetBuffer);
  Dot11FreeSendPacket(&v10);
  if ( *(p_Next - 2) )
    ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)*(p_Next - 2), p_Next - 2);
  else
    ExFreePoolWithTag(p_Next - 2, *((_DWORD *)p_Next - 2));
  IoFreeMdl(v7);
  FilterReturnNetBufferLists(v8, a4, v9);
}

```

## disassembly

```asm
0x140013680  mov     [rsp+arg_8], rbx
0x140013685  mov     [rsp+arg_10], rsi
0x14001368a  mov     [rsp+arg_0], rcx
0x14001368f  push    rdi
0x140013690  sub     rsp, 20h
0x140013694  mov     rcx, [rcx+8]; NetBuffer
0x140013698  mov     rdi, r9
0x14001369b  mov     rbx, [rcx+20h]
0x14001369f  mov     rsi, [rbx]
0x1400136a2  call    cs:__imp_NdisFreeNetBuffer
0x1400136a9  nop     dword ptr [rax+rax+00h]
0x1400136ae  lea     rcx, [rsp+28h+arg_0]; struct _NET_BUFFER_LIST **
0x1400136b3  call    ?Dot11FreeSendPacket@@YAXPEAPEAU_NET_BUFFER_LIST@@@Z; Dot11FreeSendPacket(_NET_BUFFER_LIST * *)
0x1400136b8  lea     rcx, [rbx-10h]; P
0x1400136bc  mov     rax, [rcx]
0x1400136bf  test    rax, rax
0x1400136c2  jz      short loc_1400136D8
0x1400136c4  mov     rdx, rcx; Entry
0x1400136c7  mov     rcx, rax; Lookaside
0x1400136ca  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400136d1  nop     dword ptr [rax+rax+00h]
0x1400136d6  jmp     short loc_1400136E7
0x1400136d8  mov     edx, [rcx+8]; Tag
0x1400136db  call    cs:__imp_ExFreePoolWithTag
0x1400136e2  nop     dword ptr [rax+rax+00h]
0x1400136e7  mov     rcx, rsi; Mdl
0x1400136ea  call    cs:__imp_IoFreeMdl
0x1400136f1  nop     dword ptr [rax+rax+00h]
0x1400136f6  mov     rdx, rdi; struct _NET_BUFFER_LIST *
0x1400136f9  call    ?FilterReturnNetBufferLists@@YAXPEAU_ADAPT@@PEAU_NET_BUFFER_LIST@@K@Z; FilterReturnNetBufferLists(_ADAPT *,_NET_BUFFER_LIST *,ulong)
0x1400136fe  mov     rbx, [rsp+28h+arg_8]
0x140013703  mov     rsi, [rsp+28h+arg_10]
0x140013708  add     rsp, 20h
0x14001370c  pop     rdi
0x14001370d  retn
```
