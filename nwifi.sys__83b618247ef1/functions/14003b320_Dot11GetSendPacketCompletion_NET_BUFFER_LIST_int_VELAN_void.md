# Dot11GetSendPacketCompletion(_NET_BUFFER_LIST *,int,_VELAN *,void *)

- ea: `0x14003b320`
- end: `0x14003b3ae`
- name: `?Dot11GetSendPacketCompletion@@YAXPEAU_NET_BUFFER_LIST@@HPEAU_VELAN@@PEAX@Z`
- size: `142`
- prototype: `void __fastcall(struct _NET_BUFFER_LIST *, int, struct _VELAN *, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14003b110`

## callees

- `0x140013adc`
- `0x14003b320`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14003b37e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14003b37e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003b38f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003b38f`
- `NDIS!NdisFreeNetBuffer` at `0x14003b351`
- `NDIS!NdisFreeNetBuffer` at `0x14003b351`

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
0x14003b320  test    rcx, rcx
0x14003b323  jz      locret_14003B3AC
0x14003b329  mov     [rsp+arg_8], rbx
0x14003b32e  mov     [rsp+arg_0], rcx
0x14003b333  push    rdi
0x14003b334  sub     rsp, 20h
0x14003b338  mov     rax, [rcx+8]
0x14003b33c  xor     ebx, ebx
0x14003b33e  mov     [rcx+8], rbx
0x14003b342  mov     rdi, r8
0x14003b345  test    rax, rax
0x14003b348  jz      short loc_14003B35D
0x14003b34a  mov     rbx, [rax+20h]
0x14003b34e  mov     rcx, rax; NetBuffer
0x14003b351  call    cs:__imp_NdisFreeNetBuffer
0x14003b358  nop     dword ptr [rax+rax+00h]
0x14003b35d  lea     rcx, [rsp+28h+arg_0]; struct _NET_BUFFER_LIST **
0x14003b362  call    ?Dot11FreeSendPacket@@YAXPEAPEAU_NET_BUFFER_LIST@@@Z; Dot11FreeSendPacket(_NET_BUFFER_LIST * *)
0x14003b367  test    rbx, rbx
0x14003b36a  jz      short loc_14003B39B
0x14003b36c  lea     rcx, [rbx-10h]; P
0x14003b370  mov     rax, [rcx]
0x14003b373  test    rax, rax
0x14003b376  jz      short loc_14003B38C
0x14003b378  mov     rdx, rcx; Entry
0x14003b37b  mov     rcx, rax; Lookaside
0x14003b37e  call    cs:__imp_ExFreeToNPagedLookasideList
0x14003b385  nop     dword ptr [rax+rax+00h]
0x14003b38a  jmp     short loc_14003B39B
0x14003b38c  mov     edx, [rcx+8]; Tag
0x14003b38f  call    cs:__imp_ExFreePoolWithTag
0x14003b396  nop     dword ptr [rax+rax+00h]
0x14003b39b  lock dec dword ptr [rdi+1358h]
0x14003b3a2  mov     rbx, [rsp+28h+arg_8]
0x14003b3a7  add     rsp, 20h
0x14003b3ab  pop     rdi
0x14003b3ac  retn
```
