# APPktUtilsPrepareForwardDataPacketComplete(_NET_BUFFER_LIST *,int,_EXTAP_VELAN *,_NET_BUFFER_LIST *)

- ea: `0x140013690`
- end: `0x14001371f`
- name: `?APPktUtilsPrepareForwardDataPacketComplete@@YAXPEAU_NET_BUFFER_LIST@@HPEAU_EXTAP_VELAN@@0@Z`
- size: `143`
- prototype: `void(struct _NET_BUFFER_LIST *, int, struct _EXTAP_VELAN *, struct _NET_BUFFER_LIST *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140013690`
- `0x140013730`
- `0x140013adc`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400136da`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400136da`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400136eb`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400136eb`
- `ntoskrnl!IoFreeMdl` at `0x1400136fa`
- `ntoskrnl!IoFreeMdl` at `0x1400136fa`
- `NDIS!NdisFreeNetBuffer` at `0x1400136b2`
- `NDIS!NdisFreeNetBuffer` at `0x1400136b2`

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
0x140013690  mov     [rsp+arg_8], rbx
0x140013695  mov     [rsp+arg_10], rsi
0x14001369a  mov     [rsp+arg_0], rcx
0x14001369f  push    rdi
0x1400136a0  sub     rsp, 20h
0x1400136a4  mov     rcx, [rcx+8]; NetBuffer
0x1400136a8  mov     rdi, r9
0x1400136ab  mov     rbx, [rcx+20h]
0x1400136af  mov     rsi, [rbx]
0x1400136b2  call    cs:__imp_NdisFreeNetBuffer
0x1400136b9  nop     dword ptr [rax+rax+00h]
0x1400136be  lea     rcx, [rsp+28h+arg_0]; struct _NET_BUFFER_LIST **
0x1400136c3  call    ?Dot11FreeSendPacket@@YAXPEAPEAU_NET_BUFFER_LIST@@@Z; Dot11FreeSendPacket(_NET_BUFFER_LIST * *)
0x1400136c8  lea     rcx, [rbx-10h]; P
0x1400136cc  mov     rax, [rcx]
0x1400136cf  test    rax, rax
0x1400136d2  jz      short loc_1400136E8
0x1400136d4  mov     rdx, rcx; Entry
0x1400136d7  mov     rcx, rax; Lookaside
0x1400136da  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400136e1  nop     dword ptr [rax+rax+00h]
0x1400136e6  jmp     short loc_1400136F7
0x1400136e8  mov     edx, [rcx+8]; Tag
0x1400136eb  call    cs:__imp_ExFreePoolWithTag
0x1400136f2  nop     dword ptr [rax+rax+00h]
0x1400136f7  mov     rcx, rsi; Mdl
0x1400136fa  call    cs:__imp_IoFreeMdl
0x140013701  nop     dword ptr [rax+rax+00h]
0x140013706  mov     rdx, rdi; struct _NET_BUFFER_LIST *
0x140013709  call    ?FilterReturnNetBufferLists@@YAXPEAU_ADAPT@@PEAU_NET_BUFFER_LIST@@K@Z; FilterReturnNetBufferLists(_ADAPT *,_NET_BUFFER_LIST *,ulong)
0x14001370e  mov     rbx, [rsp+28h+arg_8]
0x140013713  mov     rsi, [rsp+28h+arg_10]
0x140013718  add     rsp, 20h
0x14001371c  pop     rdi
0x14001371d  retn
```
