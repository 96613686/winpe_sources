# Pt6RecvNBLComplete

- ea: `0x140013820`
- end: `0x14001392f`
- name: `Pt6RecvNBLComplete`
- size: `271`
- prototype: `__int64 __fastcall(PNET_BUFFER_LIST NetBufferList)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140013820`
- `0x140013b80`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001387c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400138e8`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14001387c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400138e8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001388d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400138f9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001388d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400138f9`
- `NDIS!NdisFReturnNetBufferLists` at `0x140013847`
- `NDIS!NdisFReturnNetBufferLists` at `0x140013847`
- `NDIS!NdisFreeNetBufferList` at `0x140013908`
- `NDIS!NdisFreeNetBufferList` at `0x140013908`
- `NDIS!NdisFreeNetBuffer` at `0x14001389c`
- `NDIS!NdisFreeNetBuffer` at `0x14001389c`

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
0x140013820  push    rbx
0x140013822  push    rbp
0x140013823  push    rsi
0x140013824  push    rdi
0x140013825  push    r14
0x140013827  sub     rsp, 20h
0x14001382b  mov     rbp, [rdx+10h]
0x14001382f  mov     rax, r8
0x140013832  mov     r14, rdx
0x140013835  mov     rdi, rcx
0x140013838  test    r8, r8
0x14001383b  jz      short loc_140013855
0x14001383d  mov     rcx, [rbp+50h]; NdisFilterHandle
0x140013841  xor     r8d, r8d; ReturnFlags
0x140013844  mov     rdx, rax; NetBufferLists
0x140013847  call    cs:__imp_NdisFReturnNetBufferLists
0x14001384e  nop     dword ptr [rax+rax+00h]
0x140013853  jmp     short loc_1400138B0
0x140013855  mov     rbx, [rcx+8]
0x140013859  test    rbx, rbx
0x14001385c  jz      short loc_1400138B0
0x14001385e  mov     rcx, [rbx+20h]
0x140013862  mov     rsi, [rbx]
0x140013865  test    rcx, rcx
0x140013868  jz      short loc_140013899
0x14001386a  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x14001386e  mov     rax, [rcx]
0x140013871  test    rax, rax
0x140013874  jz      short loc_14001388A
0x140013876  mov     rdx, rcx; Entry
0x140013879  mov     rcx, rax; Lookaside
0x14001387c  call    cs:__imp_ExFreeToNPagedLookasideList
0x140013883  nop     dword ptr [rax+rax+00h]
0x140013888  jmp     short loc_140013899
0x14001388a  mov     edx, [rcx+8]; Tag
0x14001388d  call    cs:__imp_ExFreePoolWithTag
0x140013894  nop     dword ptr [rax+rax+00h]
0x140013899  mov     rcx, rbx; NetBuffer
0x14001389c  call    cs:__imp_NdisFreeNetBuffer
0x1400138a3  nop     dword ptr [rax+rax+00h]
0x1400138a8  mov     rbx, rsi
0x1400138ab  test    rsi, rsi
0x1400138ae  jnz     short loc_14001385E
0x1400138b0  test    rdi, rdi
0x1400138b3  jz      short loc_140013914
0x1400138b5  mov     rcx, [rdi+10h]
0x1400138b9  movzx   eax, word ptr [rcx+0Ah]
0x1400138bd  mov     rbx, [rax+rcx+10h]
0x1400138c2  lea     rcx, [rbx+8]; struct DOT11_MAC_STATE_ENTRY **
0x1400138c6  cmp     qword ptr [rcx], 0
0x1400138ca  jz      short loc_1400138D1
0x1400138cc  call    ?Dot11ReleaseMacState@@YAXPEAPEAUDOT11_MAC_STATE_ENTRY@@@Z; Dot11ReleaseMacState(DOT11_MAC_STATE_ENTRY * *)
0x1400138d1  test    rbx, rbx
0x1400138d4  jz      short loc_140013905
0x1400138d6  lea     rcx, [rbx-10h]; P
0x1400138da  mov     rax, [rcx]
0x1400138dd  test    rax, rax
0x1400138e0  jz      short loc_1400138F6
0x1400138e2  mov     rdx, rcx; Entry
0x1400138e5  mov     rcx, rax; Lookaside
0x1400138e8  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400138ef  nop     dword ptr [rax+rax+00h]
0x1400138f4  jmp     short loc_140013905
0x1400138f6  mov     edx, [rcx+8]; Tag
0x1400138f9  call    cs:__imp_ExFreePoolWithTag
0x140013900  nop     dword ptr [rax+rax+00h]
0x140013905  mov     rcx, rdi; NetBufferList
0x140013908  call    cs:__imp_NdisFreeNetBufferList
0x14001390f  nop     dword ptr [rax+rax+00h]
0x140013914  lock dec dword ptr [rbp+0ECh]
0x14001391b  lock dec dword ptr [r14+135Ch]
0x140013923  add     rsp, 20h
0x140013927  pop     r14
0x140013929  pop     rdi
0x14001392a  pop     rsi
0x14001392b  pop     rbp
0x14001392c  pop     rbx
0x14001392d  retn
```
