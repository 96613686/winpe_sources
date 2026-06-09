# AllocateAndCopyNetBufferList

- ea: `0x1400052b8`
- end: `0x14000536e`
- name: `AllocateAndCopyNetBufferList`
- size: `182`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140015660`

## callees

- `0x1400052b8`

## import_xrefs

- `NDIS!NdisFreeNetBufferList` at `0x140005350`
- `NDIS!NdisFreeNetBufferList` at `0x140005350`
- `NDIS!NdisCopyFromNetBufferToNetBuffer` at `0x140005332`
- `NDIS!NdisCopyFromNetBufferToNetBuffer` at `0x140005332`
- `NDIS!NdisAllocateNetBufferList` at `0x1400052e0`
- `NDIS!NdisAllocateNetBufferList` at `0x1400052e0`

## pseudocode

```c
__int64 __fastcall AllocateAndCopyNetBufferList(__int64 a1, struct _NET_BUFFER_LIST **a2)
{
  struct _NET_BUFFER *v2; // rdi
  PNET_BUFFER_LIST NetBufferList; // rax
  struct _NET_BUFFER_LIST *v5; // rbx
  unsigned int v6; // edi
  struct _NET_BUFFER *FirstNetBuffer; // rsi
  ULONG BytesCopied; // [rsp+60h] [rbp+8h] BYREF

  v2 = *(struct _NET_BUFFER **)(a1 + 8);
  BytesCopied = 0;
  NetBufferList = NdisAllocateNetBufferList(gl_NblPoolHandle, 0xA0u, 0);
  v5 = NetBufferList;
  if ( NetBufferList )
  {
    FirstNetBuffer = NetBufferList->FirstNetBuffer;
    FirstNetBuffer->DataOffset = 0;
    FirstNetBuffer->CurrentMdlOffset = 0;
    FirstNetBuffer->DataLength = 1514;
    v6 = NdisCopyFromNetBufferToNetBuffer(FirstNetBuffer, 0, v2->DataLength, v2, 0, &BytesCopied);
    if ( v6 )
    {
      NdisFreeNetBufferList(v5);
      v5 = 0;
    }
    else
    {
      FirstNetBuffer->DataLength = BytesCopied;
    }
  }
  else
  {
    v6 = -1073741670;
  }
  *a2 = v5;
  return v6;
}

```

## disassembly

```asm
0x1400052b8  push    rbx
0x1400052ba  push    rsi
0x1400052bb  push    rdi
0x1400052bc  push    r14
0x1400052be  sub     rsp, 38h
0x1400052c2  mov     rdi, [rcx+8]
0x1400052c6  mov     r14, rdx
0x1400052c9  mov     rcx, cs:gl_NblPoolHandle; PoolHandle
0x1400052d0  mov     edx, 0A0h; ContextSize
0x1400052d5  xor     r8d, r8d; ContextBackFill
0x1400052d8  mov     [rsp+58h+arg_0], 0
0x1400052e0  call    cs:__imp_NdisAllocateNetBufferList
0x1400052e7  nop     dword ptr [rax+rax+00h]
0x1400052ec  mov     rbx, rax
0x1400052ef  test    rax, rax
0x1400052f2  jnz     short loc_1400052FB
0x1400052f4  mov     edi, 0C000009Ah
0x1400052f9  jmp     short loc_14000535E
0x1400052fb  mov     rsi, [rax+8]
0x1400052ff  mov     r9, rdi; Source
0x140005302  lea     rax, [rsp+58h+arg_0]
0x140005307  xor     edx, edx; DestinationOffset
0x140005309  mov     [rsp+58h+BytesCopied], rax; BytesCopied
0x14000530e  mov     rcx, rsi; Destination
0x140005311  mov     [rsp+58h+SourceOffset], 0; SourceOffset
0x140005319  mov     dword ptr [rsi+28h], 0
0x140005320  mov     dword ptr [rsi+10h], 0
0x140005327  mov     dword ptr [rsi+18h], 5EAh
0x14000532e  mov     r8d, [rdi+18h]; BytesToCopy
0x140005332  call    cs:__imp_NdisCopyFromNetBufferToNetBuffer
0x140005339  nop     dword ptr [rax+rax+00h]
0x14000533e  mov     edi, eax
0x140005340  test    eax, eax
0x140005342  jnz     short loc_14000534D
0x140005344  mov     ecx, [rsp+58h+arg_0]
0x140005348  mov     [rsi+18h], ecx
0x14000534b  jmp     short loc_14000535E
0x14000534d  mov     rcx, rbx; NetBufferList
0x140005350  call    cs:__imp_NdisFreeNetBufferList
0x140005357  nop     dword ptr [rax+rax+00h]
0x14000535c  xor     ebx, ebx
0x14000535e  mov     [r14], rbx
0x140005361  mov     eax, edi
0x140005363  add     rsp, 38h
0x140005367  pop     r14
0x140005369  pop     rdi
0x14000536a  pop     rsi
0x14000536b  pop     rbx
0x14000536c  retn
```
