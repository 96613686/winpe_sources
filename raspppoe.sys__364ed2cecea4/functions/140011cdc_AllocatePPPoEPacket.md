# AllocatePPPoEPacket

- ea: `0x140011cdc`
- end: `0x140011e41`
- name: `AllocatePPPoEPacket`
- size: `357`
- prototype: ``
- caller_count: `6`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140012854`
- `0x140012aa8`
- `0x140012dc8`
- `0x1400130a4`
- `0x140013344`
- `0x1400152f4`

## callees

- `0x14000110c`
- `0x1400024dc`
- `0x140007040`
- `0x140011cdc`

## import_xrefs

- `NDIS!NdisFreeNetBufferList` at `0x140011ded`
- `NDIS!NdisFreeNetBufferList` at `0x140011ded`
- `NDIS!NdisGetDataBuffer` at `0x140011d97`
- `NDIS!NdisGetDataBuffer` at `0x140011d97`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x140011d75`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x140011d75`
- `NDIS!NdisAllocateNetBufferList` at `0x140011d2f`
- `NDIS!NdisAllocateNetBufferList` at `0x140011d2f`

## pseudocode

```c
UCHAR *AllocatePPPoEPacket()
{
  PNET_BUFFER_LIST NetBufferList; // rax
  struct _NET_BUFFER_LIST *v1; // rdi
  UCHAR *v2; // rbx
  _DWORD *DataBuffer; // rax
  __int64 v4; // rax

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0x1Bu,
      (__int64)WPP_9a9b27d68b0f3b5d3a4b6d6ff9c7dc3d_Traceguids);
  }
  NetBufferList = NdisAllocateNetBufferList(gl_NblPoolHandle, 0xA0u, 0);
  v1 = NetBufferList;
  if ( !NetBufferList )
    goto LABEL_10;
  v2 = &NetBufferList->Context->ContextData[NetBufferList->Context->Offset];
  memset(v2, 0, 0xA0u);
  if ( NdisRetreatNetBufferDataStart(v1->FirstNetBuffer, 0x5EAu, 0, 0)
    || (DataBuffer = NdisGetDataBuffer(v1->FirstNetBuffer, 0x14u, 0, 1u, 0), (*((_QWORD *)v2 + 14) = DataBuffer) == 0) )
  {
    NdisFreeNetBufferList(v1);
LABEL_10:
    v2 = 0;
    goto LABEL_11;
  }
  *(_OWORD *)DataBuffer = 0;
  DataBuffer[4] = 0;
  v4 = *((_QWORD *)v2 + 14);
  *((_DWORD *)v2 + 32) = 2;
  *((_QWORD *)v2 + 15) = v4 + 20;
  v1->ProtocolReserved[0] = v2;
  *((_QWORD *)v2 + 1) = DerefPppoePacket;
  *((_QWORD *)v2 + 17) = v1;
  *(_DWORD *)v2 = 0;
  _InterlockedIncrement((volatile signed __int32 *)v2);
LABEL_11:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_q(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0x1Cu,
      (__int64)WPP_9a9b27d68b0f3b5d3a4b6d6ff9c7dc3d_Traceguids,
      v2);
  }
  return v2;
}

```

## disassembly

```asm
0x140011cdc  mov     [rsp+arg_0], rbx
0x140011ce1  mov     [rsp+arg_8], rsi
0x140011ce6  push    rdi
0x140011ce7  sub     rsp, 30h
0x140011ceb  mov     rcx, cs:WPP_GLOBAL_Control
0x140011cf2  lea     rsi, WPP_GLOBAL_Control
0x140011cf9  cmp     rcx, rsi
0x140011cfc  jz      short loc_140011D20
0x140011cfe  mov     eax, [rcx+2Ch]
0x140011d01  test    al, 20h
0x140011d03  jz      short loc_140011D20
0x140011d05  cmp     byte ptr [rcx+29h], 4
0x140011d09  jb      short loc_140011D20
0x140011d0b  mov     rcx, [rcx+18h]
0x140011d0f  lea     r8, WPP_9a9b27d68b0f3b5d3a4b6d6ff9c7dc3d_Traceguids
0x140011d16  mov     edx, 1Bh
0x140011d1b  call    WPP_SF_
0x140011d20  mov     rcx, cs:gl_NblPoolHandle; PoolHandle
0x140011d27  xor     r8d, r8d; ContextBackFill
0x140011d2a  mov     edx, 0A0h; ContextSize
0x140011d2f  call    cs:__imp_NdisAllocateNetBufferList
0x140011d36  nop     dword ptr [rax+rax+00h]
0x140011d3b  mov     rdi, rax
0x140011d3e  test    rax, rax
0x140011d41  jz      loc_140011DF9
0x140011d47  mov     rdx, [rax+10h]
0x140011d4b  mov     r8d, 0A0h; Size
0x140011d51  movzx   ecx, word ptr [rdx+0Ah]
0x140011d55  lea     rbx, [rdx+10h]
0x140011d59  add     rbx, rcx
0x140011d5c  xor     edx, edx; Val
0x140011d5e  mov     rcx, rbx; void *
0x140011d61  call    memset
0x140011d66  mov     rcx, [rdi+8]; NetBuffer
0x140011d6a  xor     r9d, r9d; AllocateMdlHandler
0x140011d6d  xor     r8d, r8d; DataBackFill
0x140011d70  mov     edx, 5EAh; DataOffsetDelta
0x140011d75  call    cs:__imp_NdisRetreatNetBufferDataStart
0x140011d7c  nop     dword ptr [rax+rax+00h]
0x140011d81  test    eax, eax
0x140011d83  jnz     short loc_140011DEA
0x140011d85  mov     rcx, [rdi+8]; NetBuffer
0x140011d89  lea     r9d, [rax+1]; AlignMultiple
0x140011d8d  xor     r8d, r8d; Storage
0x140011d90  mov     [rsp+38h+AlignOffset], eax; AlignOffset
0x140011d94  lea     edx, [rax+14h]; BytesNeeded
0x140011d97  call    cs:__imp_NdisGetDataBuffer
0x140011d9e  nop     dword ptr [rax+rax+00h]
0x140011da3  mov     [rbx+70h], rax
0x140011da7  test    rax, rax
0x140011daa  jz      short loc_140011DEA
0x140011dac  xor     ecx, ecx
0x140011dae  xorps   xmm0, xmm0
0x140011db1  movups  xmmword ptr [rax], xmm0
0x140011db4  mov     [rax+10h], ecx
0x140011db7  mov     rax, [rbx+70h]
0x140011dbb  add     rax, 14h
0x140011dbf  mov     dword ptr [rbx+80h], 2
0x140011dc9  mov     [rbx+78h], rax
0x140011dcd  lea     rax, DerefPppoePacket
0x140011dd4  mov     [rdi+40h], rbx
0x140011dd8  mov     [rbx+8], rax
0x140011ddc  mov     [rbx+88h], rdi
0x140011de3  mov     [rbx], ecx
0x140011de5  lock inc dword ptr [rbx]
0x140011de8  jmp     short loc_140011DFB
0x140011dea  mov     rcx, rdi; NetBufferList
0x140011ded  call    cs:__imp_NdisFreeNetBufferList
0x140011df4  nop     dword ptr [rax+rax+00h]
0x140011df9  xor     ebx, ebx
0x140011dfb  mov     rcx, cs:WPP_GLOBAL_Control
0x140011e02  cmp     rcx, rsi
0x140011e05  jz      short loc_140011E2D
0x140011e07  mov     edx, [rcx+2Ch]
0x140011e0a  test    dl, 20h
0x140011e0d  jz      short loc_140011E2D
0x140011e0f  cmp     byte ptr [rcx+29h], 4
0x140011e13  jb      short loc_140011E2D
0x140011e15  mov     rcx, [rcx+18h]
0x140011e19  lea     r8, WPP_9a9b27d68b0f3b5d3a4b6d6ff9c7dc3d_Traceguids
0x140011e20  mov     edx, 1Ch
0x140011e25  mov     r9, rbx
0x140011e28  call    WPP_SF_q
0x140011e2d  mov     rsi, [rsp+38h+arg_8]
0x140011e32  mov     rax, rbx
0x140011e35  mov     rbx, [rsp+38h+arg_0]
0x140011e3a  add     rsp, 30h
0x140011e3e  pop     rdi
0x140011e3f  retn
```
