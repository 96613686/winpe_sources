# NdisWanCopyNetBufferList

- ea: `0x1400052e0`
- end: `0x1400053ef`
- name: `NdisWanCopyNetBufferList`
- size: `271`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140004be0`
- `0x14000bdb0`

## callees

- `0x1400052e0`
- `0x140005400`

## import_xrefs

- `NDIS!NdisFreeNetBufferList` at `0x1400053a5`
- `NDIS!NdisFreeNetBufferList` at `0x1400053d6`
- `NDIS!NdisFreeNetBufferList` at `0x1400053a5`
- `NDIS!NdisFreeNetBufferList` at `0x1400053d6`
- `NDIS!NdisCopyFromNetBufferToNetBuffer` at `0x140005378`
- `NDIS!NdisCopyFromNetBufferToNetBuffer` at `0x140005378`

## pseudocode

```c
__int64 __fastcall NdisWanCopyNetBufferList(__int64 a1, PNET_BUFFER_LIST *a2)
{
  struct _NET_BUFFER *Alignment; // rbx
  PNET_BUFFER_LIST *p_NetBufferList; // r15
  unsigned int v6; // ebp
  __int64 RecvNetBufferList; // rax
  struct _NET_BUFFER_LIST *v9; // rdi
  struct _NET_BUFFER *v10; // rcx
  PNET_BUFFER_LIST v11; // rdi
  struct _NET_BUFFER_LIST *v12; // rcx
  ULONG BytesCopied; // [rsp+60h] [rbp+8h] BYREF
  PNET_BUFFER_LIST NetBufferList; // [rsp+68h] [rbp+10h] BYREF

  Alignment = *(struct _NET_BUFFER **)(a1 + 8);
  p_NetBufferList = &NetBufferList;
  NetBufferList = 0;
  *a2 = 0;
  v6 = -1073741823;
  while ( 1 )
  {
    if ( !Alignment )
    {
      *a2 = NetBufferList;
      return v6;
    }
    BytesCopied = 0;
    RecvNetBufferList = NdisWanAllocateRecvNetBufferList();
    v9 = (struct _NET_BUFFER_LIST *)RecvNetBufferList;
    if ( !RecvNetBufferList )
      break;
    v10 = *(struct _NET_BUFFER **)(RecvNetBufferList + 8);
    *(_QWORD *)(RecvNetBufferList + 208) = *(unsigned int *)(a1 + 208);
    v6 = NdisCopyFromNetBufferToNetBuffer(v10, 0, Alignment->DataLength, Alignment, 0, &BytesCopied);
    if ( v6 )
    {
      NdisFreeNetBufferList(v9);
      goto LABEL_10;
    }
    *(_DWORD *)(v9->Link.Region + 24) = Alignment->DataLength;
    *p_NetBufferList = v9;
    p_NetBufferList = &v9->Next;
    Alignment = (struct _NET_BUFFER *)Alignment->Link.Alignment;
  }
  v6 = -1073741670;
LABEL_10:
  v11 = NetBufferList;
  if ( NetBufferList )
  {
    do
    {
      v12 = v11;
      v11 = (PNET_BUFFER_LIST)v11->Link.Alignment;
      v12->Link.Alignment = 0;
      NdisFreeNetBufferList(v12);
    }
    while ( v11 );
    *a2 = 0;
  }
  else
  {
    *a2 = 0;
  }
  return v6;
}

```

## disassembly

```asm
0x1400052e0  mov     [rsp+arg_18], rbx
0x1400052e5  push    rbp
0x1400052e6  push    rsi
0x1400052e7  push    r12
0x1400052e9  push    r14
0x1400052eb  push    r15
0x1400052ed  sub     rsp, 30h
0x1400052f1  mov     rbx, [rcx+8]
0x1400052f5  lea     r15, [rsp+58h+NetBufferList]
0x1400052fa  xor     r12d, r12d
0x1400052fd  mov     [rsp+58h+arg_10], rdi
0x140005302  mov     [rsp+58h+NetBufferList], r12
0x140005307  mov     rsi, rdx
0x14000530a  mov     [rdx], r12
0x14000530d  mov     r14, rcx
0x140005310  mov     ebp, 0C0000001h
0x140005315  test    rbx, rbx
0x140005318  jnz     short loc_14000533C
0x14000531a  mov     rax, [rsp+58h+NetBufferList]
0x14000531f  mov     [rsi], rax
0x140005322  mov     eax, ebp
0x140005324  mov     rdi, [rsp+58h+arg_10]
0x140005329  mov     rbx, [rsp+58h+arg_18]
0x14000532e  add     rsp, 30h
0x140005332  pop     r15
0x140005334  pop     r14
0x140005336  pop     r12
0x140005338  pop     rsi
0x140005339  pop     rbp
0x14000533a  retn
0x14000533c  mov     [rsp+58h+arg_0], r12d
0x140005341  call    NdisWanAllocateRecvNetBufferList
0x140005346  mov     rdi, rax
0x140005349  test    rax, rax
0x14000534c  jz      short loc_1400053B3
0x14000534e  mov     eax, [r14+0D0h]
0x140005355  mov     r9, rbx; Source
0x140005358  mov     rcx, [rdi+8]; Destination
0x14000535c  xor     edx, edx; DestinationOffset
0x14000535e  mov     [rdi+0D0h], rax
0x140005365  lea     rax, [rsp+58h+arg_0]
0x14000536a  mov     r8d, [rbx+18h]; BytesToCopy
0x14000536e  mov     [rsp+58h+BytesCopied], rax; BytesCopied
0x140005373  mov     [rsp+58h+SourceOffset], r12d; SourceOffset
0x140005378  call    cs:__imp_NdisCopyFromNetBufferToNetBuffer
0x14000537f  nop     dword ptr [rax+rax+00h]
0x140005384  mov     ebp, eax
0x140005386  test    eax, eax
0x140005388  jnz     short loc_1400053A2
0x14000538a  mov     ecx, [rbx+18h]
0x14000538d  mov     rdx, [rdi+8]
0x140005391  mov     [rdx+18h], ecx
0x140005394  mov     [r15], rdi
0x140005397  mov     r15, rdi
0x14000539a  mov     rbx, [rbx]
0x14000539d  jmp     loc_140005315
0x1400053a2  mov     rcx, rdi; NetBufferList
0x1400053a5  call    cs:__imp_NdisFreeNetBufferList
0x1400053ac  nop     dword ptr [rax+rax+00h]
0x1400053b1  jmp     short loc_1400053B8
0x1400053b3  mov     ebp, 0C000009Ah
0x1400053b8  mov     rdi, [rsp+58h+NetBufferList]
0x1400053bd  test    rdi, rdi
0x1400053c0  jnz     short loc_1400053CA
0x1400053c2  mov     [rsi], rdi
0x1400053c5  jmp     loc_140005322
0x1400053ca  mov     rbx, [rdi]
0x1400053cd  mov     rcx, rdi; NetBufferList
0x1400053d0  mov     rdi, rbx
0x1400053d3  mov     [rcx], r12
0x1400053d6  call    cs:__imp_NdisFreeNetBufferList
0x1400053dd  nop     dword ptr [rax+rax+00h]
0x1400053e2  test    rbx, rbx
0x1400053e5  jnz     short loc_1400053CA
0x1400053e7  mov     [rsi], rbx
0x1400053ea  jmp     loc_140005322
```
