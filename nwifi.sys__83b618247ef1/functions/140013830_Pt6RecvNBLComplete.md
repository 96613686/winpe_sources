# Pt6RecvNBLComplete

- ea: `0x140013830`
- end: `0x14001393f`
- name: `Pt6RecvNBLComplete`
- size: `271`
- prototype: `__int64 __fastcall(PNET_BUFFER_LIST NetBufferList)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140013830`
- `0x140013b90`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001388c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400138f8`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001388c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400138f8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001389d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013909`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001389d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013909`
- `NDIS!NdisFReturnNetBufferLists` at `0x140013857`
- `NDIS!NdisFReturnNetBufferLists` at `0x140013857`
- `NDIS!NdisFreeNetBufferList` at `0x140013918`
- `NDIS!NdisFreeNetBufferList` at `0x140013918`
- `NDIS!NdisFreeNetBuffer` at `0x1400138ac`
- `NDIS!NdisFreeNetBuffer` at `0x1400138ac`

## pseudocode

```c
void __fastcall Pt6RecvNBLComplete(PNET_BUFFER_LIST NetBufferList, __int64 a2, struct _NET_BUFFER_LIST *a3)
{
  __int64 v3; // rbp
  _NET_BUFFER *FirstNetBuffer; // rbx
  _MDL *MdlChain; // rcx
  _NET_BUFFER *Alignment; // rsi
  ULONG *p_StartVa; // rcx
  __int64 v10; // rbx

  v3 = *(_QWORD *)(a2 + 16);
  if ( a3 )
  {
    NdisFReturnNetBufferLists(*(NDIS_HANDLE *)(v3 + 80), a3, 0);
  }
  else
  {
    FirstNetBuffer = NetBufferList->FirstNetBuffer;
    if ( FirstNetBuffer )
    {
      do
      {
        MdlChain = FirstNetBuffer->MdlChain;
        Alignment = (_NET_BUFFER *)FirstNetBuffer->Link.Alignment;
        if ( MdlChain )
        {
          p_StartVa = (ULONG *)&MdlChain[-1].StartVa;
          if ( *(_QWORD *)p_StartVa )
            ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)p_StartVa, p_StartVa);
          else
            ExFreePoolWithTag(p_StartVa, p_StartVa[2]);
        }
        NdisFreeNetBuffer(FirstNetBuffer);
        FirstNetBuffer = Alignment;
      }
      while ( Alignment );
    }
  }
  if ( NetBufferList )
  {
    v10 = *(_QWORD *)&NetBufferList->Context->ContextData[NetBufferList->Context->Offset];
    if ( *(_QWORD *)(v10 + 8) )
      Dot11ReleaseMacState((struct DOT11_MAC_STATE_ENTRY **)(v10 + 8));
    if ( v10 )
    {
      if ( *(_QWORD *)(v10 - 16) )
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v10 - 16), (PVOID)(v10 - 16));
      else
        ExFreePoolWithTag((PVOID)(v10 - 16), *(_DWORD *)(v10 - 16 + 8));
    }
    NdisFreeNetBufferList(NetBufferList);
  }
  _InterlockedDecrement((volatile signed __int32 *)(v3 + 236));
  _InterlockedDecrement((volatile signed __int32 *)(a2 + 4956));
}

```

## disassembly

```asm
0x140013830  push    rbx
0x140013832  push    rbp
0x140013833  push    rsi
0x140013834  push    rdi
0x140013835  push    r14
0x140013837  sub     rsp, 20h
0x14001383b  mov     rbp, [rdx+10h]
0x14001383f  mov     rax, r8
0x140013842  mov     r14, rdx
0x140013845  mov     rdi, rcx
0x140013848  test    r8, r8
0x14001384b  jz      short loc_140013865
0x14001384d  mov     rcx, [rbp+50h]; NdisFilterHandle
0x140013851  xor     r8d, r8d; ReturnFlags
0x140013854  mov     rdx, rax; NetBufferLists
0x140013857  call    cs:__imp_NdisFReturnNetBufferLists
0x14001385e  nop     dword ptr [rax+rax+00h]
0x140013863  jmp     short loc_1400138C0
0x140013865  mov     rbx, [rcx+8]
0x140013869  test    rbx, rbx
0x14001386c  jz      short loc_1400138C0
0x14001386e  mov     rcx, [rbx+20h]
0x140013872  mov     rsi, [rbx]
0x140013875  test    rcx, rcx
0x140013878  jz      short loc_1400138A9
0x14001387a  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x14001387e  mov     rax, [rcx]
0x140013881  test    rax, rax
0x140013884  jz      short loc_14001389A
0x140013886  mov     rdx, rcx; Entry
0x140013889  mov     rcx, rax; Lookaside
0x14001388c  call    cs:__imp_ExFreeToNPagedLookasideList
0x140013893  nop     dword ptr [rax+rax+00h]
0x140013898  jmp     short loc_1400138A9
0x14001389a  mov     edx, [rcx+8]; Tag
0x14001389d  call    cs:__imp_ExFreePoolWithTag
0x1400138a4  nop     dword ptr [rax+rax+00h]
0x1400138a9  mov     rcx, rbx; NetBuffer
0x1400138ac  call    cs:__imp_NdisFreeNetBuffer
0x1400138b3  nop     dword ptr [rax+rax+00h]
0x1400138b8  mov     rbx, rsi
0x1400138bb  test    rsi, rsi
0x1400138be  jnz     short loc_14001386E
0x1400138c0  test    rdi, rdi
0x1400138c3  jz      short loc_140013924
0x1400138c5  mov     rcx, [rdi+10h]
0x1400138c9  movzx   eax, word ptr [rcx+0Ah]
0x1400138cd  mov     rbx, [rax+rcx+10h]
0x1400138d2  lea     rcx, [rbx+8]; struct DOT11_MAC_STATE_ENTRY **
0x1400138d6  cmp     qword ptr [rcx], 0
0x1400138da  jz      short loc_1400138E1
0x1400138dc  call    ?Dot11ReleaseMacState@@YAXPEAPEAUDOT11_MAC_STATE_ENTRY@@@Z; Dot11ReleaseMacState(DOT11_MAC_STATE_ENTRY * *)
0x1400138e1  test    rbx, rbx
0x1400138e4  jz      short loc_140013915
0x1400138e6  lea     rcx, [rbx-10h]; P
0x1400138ea  mov     rax, [rcx]
0x1400138ed  test    rax, rax
0x1400138f0  jz      short loc_140013906
0x1400138f2  mov     rdx, rcx; Entry
0x1400138f5  mov     rcx, rax; Lookaside
0x1400138f8  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400138ff  nop     dword ptr [rax+rax+00h]
0x140013904  jmp     short loc_140013915
0x140013906  mov     edx, [rcx+8]; Tag
0x140013909  call    cs:__imp_ExFreePoolWithTag
0x140013910  nop     dword ptr [rax+rax+00h]
0x140013915  mov     rcx, rdi; NetBufferList
0x140013918  call    cs:__imp_NdisFreeNetBufferList
0x14001391f  nop     dword ptr [rax+rax+00h]
0x140013924  lock dec dword ptr [rbp+0ECh]
0x14001392b  lock dec dword ptr [r14+135Ch]
0x140013933  add     rsp, 20h
0x140013937  pop     r14
0x140013939  pop     rdi
0x14001393a  pop     rsi
0x14001393b  pop     rbp
0x14001393c  pop     rbx
0x14001393d  retn
```
