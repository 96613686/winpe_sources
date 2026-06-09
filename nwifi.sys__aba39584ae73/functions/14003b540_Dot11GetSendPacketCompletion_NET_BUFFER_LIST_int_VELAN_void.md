# Dot11GetSendPacketCompletion(_NET_BUFFER_LIST *,int,_VELAN *,void *)

- ea: `0x14003b540`
- end: `0x14003b5ce`
- name: `?Dot11GetSendPacketCompletion@@YAXPEAU_NET_BUFFER_LIST@@HPEAU_VELAN@@PEAX@Z`
- size: `142`
- prototype: `void __fastcall(struct _NET_BUFFER_LIST *, int, struct _VELAN *, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14003b330`

## callees

- `0x140013acc`
- `0x14003b540`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14003b59e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14003b59e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003b5af`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003b5af`
- `NDIS!NdisFreeNetBuffer` at `0x14003b571`
- `NDIS!NdisFreeNetBuffer` at `0x14003b571`

## pseudocode

```c
void __fastcall Dot11GetSendPacketCompletion(struct _NET_BUFFER_LIST *a1, __int64 a2, struct _VELAN *a3, void *a4)
{
  _NET_BUFFER *FirstNetBuffer; // rax
  _MDL *MdlChain; // rbx
  struct _NET_BUFFER_LIST *v7; // [rsp+30h] [rbp+8h] BYREF

  if ( a1 )
  {
    v7 = a1;
    FirstNetBuffer = a1->FirstNetBuffer;
    MdlChain = 0;
    a1->Link.Region = 0;
    if ( FirstNetBuffer )
    {
      MdlChain = FirstNetBuffer->MdlChain;
      NdisFreeNetBuffer(FirstNetBuffer);
    }
    Dot11FreeSendPacket(&v7);
    if ( MdlChain )
    {
      if ( MdlChain[-1].StartVa )
        ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)MdlChain[-1].StartVa, &MdlChain[-1].StartVa);
      else
        ExFreePoolWithTag(&MdlChain[-1].StartVa, MdlChain[-1].ByteCount);
    }
    _InterlockedDecrement((volatile signed __int32 *)&a3->OutstandingSends);
  }
}

```

## disassembly

```asm
0x14003b540  test    rcx, rcx
0x14003b543  jz      locret_14003B5CC
0x14003b549  mov     [rsp+arg_8], rbx
0x14003b54e  mov     [rsp+arg_0], rcx
0x14003b553  push    rdi
0x14003b554  sub     rsp, 20h
0x14003b558  mov     rax, [rcx+8]
0x14003b55c  xor     ebx, ebx
0x14003b55e  mov     [rcx+8], rbx
0x14003b562  mov     rdi, r8
0x14003b565  test    rax, rax
0x14003b568  jz      short loc_14003B57D
0x14003b56a  mov     rbx, [rax+20h]
0x14003b56e  mov     rcx, rax; NetBuffer
0x14003b571  call    cs:__imp_NdisFreeNetBuffer
0x14003b578  nop     dword ptr [rax+rax+00h]
0x14003b57d  lea     rcx, [rsp+28h+arg_0]; struct _NET_BUFFER_LIST **
0x14003b582  call    ?Dot11FreeSendPacket@@YAXPEAPEAU_NET_BUFFER_LIST@@@Z; Dot11FreeSendPacket(_NET_BUFFER_LIST * *)
0x14003b587  test    rbx, rbx
0x14003b58a  jz      short loc_14003B5BB
0x14003b58c  lea     rcx, [rbx-10h]; P
0x14003b590  mov     rax, [rcx]
0x14003b593  test    rax, rax
0x14003b596  jz      short loc_14003B5AC
0x14003b598  mov     rdx, rcx; Entry
0x14003b59b  mov     rcx, rax; Lookaside
0x14003b59e  call    cs:__imp_ExFreeToNPagedLookasideList
0x14003b5a5  nop     dword ptr [rax+rax+00h]
0x14003b5aa  jmp     short loc_14003B5BB
0x14003b5ac  mov     edx, [rcx+8]; Tag
0x14003b5af  call    cs:__imp_ExFreePoolWithTag
0x14003b5b6  nop     dword ptr [rax+rax+00h]
0x14003b5bb  lock dec dword ptr [rdi+1358h]
0x14003b5c2  mov     rbx, [rsp+28h+arg_8]
0x14003b5c7  add     rsp, 20h
0x14003b5cb  pop     rdi
0x14003b5cc  retn
```
