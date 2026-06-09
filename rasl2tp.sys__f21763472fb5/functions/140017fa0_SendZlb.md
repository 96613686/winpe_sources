# SendZlb

- ea: `0x140017fa0`
- end: `0x1400181a0`
- name: `SendZlb`
- size: `512`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x140017190`
- `0x1400174f0`
- `0x140017550`

## callees

- `0x140003050`
- `0x140003080`
- `0x140017fa0`
- `0x14001b830`
- `0x14001c1b0`
- `0x14001c620`

## import_xrefs

- `NDIS!NdisAllocateNetBufferList` at `0x140018046`
- `NDIS!NdisAllocateNetBufferList` at `0x140018046`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x1400180a6`
- `NDIS!NdisRetreatNetBufferDataStart` at `0x1400180a6`
- `NDIS!NdisGetDataBuffer` at `0x1400180c8`
- `NDIS!NdisGetDataBuffer` at `0x1400180c8`

## pseudocode

```c
void __fastcall SendZlb(__int64 a1, __int64 a2, __int16 a3, __int16 a4, char a5)
{
  int v7; // edi
  char v8; // bp
  __int64 v9; // r14
  PNET_BUFFER_LIST NetBufferList; // rax
  PNET_BUFFER_LIST v11; // rsi
  _OWORD *DataBuffer; // rax
  int v13; // r8d
  int v14; // edx
  int v15; // r9d
  __int16 v16; // [rsp+70h] [rbp+8h] BYREF
  __int16 v17; // [rsp+80h] [rbp+18h] BYREF

  v17 = a3;
  v7 = a1;
  if ( !a2 )
  {
    v16 = 0;
    goto LABEL_11;
  }
  v16 = *(_WORD *)(a2 + 58);
  if ( !v16 )
  {
LABEL_11:
    v8 = 1;
    goto LABEL_12;
  }
  v8 = 0;
  if ( (*(_DWORD *)(a1 + 120) & 0x10) == 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
    {
      if ( BYTE1(WPP_GLOBAL_Control->Timer) )
        WPP_SF_(
          (__int64)WPP_GLOBAL_Control->AttachedDevice,
          0x2Bu,
          (__int64)WPP_b05af37f07f737f49b91eab4cb6eaae9_Traceguids);
    }
    ++g_ulSendZlbWithoutHostRoute;
LABEL_9:
    DereferenceCall(a2);
    return;
  }
LABEL_12:
  v9 = *(_QWORD *)(a1 + 24);
  NetBufferList = NdisAllocateNetBufferList(*(NDIS_HANDLE *)(v9 + 224), 0, 0);
  v11 = NetBufferList;
  if ( NetBufferList )
  {
    NdisRetreatNetBufferDataStart(NetBufferList->FirstNetBuffer, 0x2Au, 0, 0);
    DataBuffer = NdisGetDataBuffer(v11->FirstNetBuffer, 0x2Au, 0, 1u, 0);
    LOBYTE(v13) = a5;
    *DataBuffer = 0;
    LOBYTE(v14) = v8;
    DataBuffer[1] = 0;
    *(_OWORD *)((char *)DataBuffer + 26) = 0;
    *(_DWORD *)(v11->Link.Region + 24) = BuildL2tpHeader(
                                           (_DWORD)DataBuffer,
                                           v14,
                                           v13,
                                           v7 + 116,
                                           (__int64)&v16,
                                           (__int64)&v17,
                                           a4);
    *(_QWORD *)(v11->Link.Region + 128) = v11;
    *(_QWORD *)(v11->Link.Region + 144) = a2;
    v15 = L2tpSendDatagram(v7, v9, v11->Link.Region, 4, (__int64)v11->FirstNetBuffer);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(
        (__int64)WPP_GLOBAL_Control->AttachedDevice,
        0x2Du,
        (__int64)WPP_b05af37f07f737f49b91eab4cb6eaae9_Traceguids,
        v15);
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_(
        (__int64)WPP_GLOBAL_Control->AttachedDevice,
        0x2Cu,
        (__int64)WPP_b05af37f07f737f49b91eab4cb6eaae9_Traceguids);
    }
    if ( a2 )
      goto LABEL_9;
  }
}

```

## disassembly

```asm
0x140017fa0  mov     [rsp+arg_8], rbx
0x140017fa5  mov     [rsp+arg_18], rbp
0x140017faa  mov     [rsp+arg_10], r8w
0x140017fb0  push    rsi
0x140017fb1  push    rdi
0x140017fb2  push    r13
0x140017fb4  push    r14
0x140017fb6  push    r15
0x140017fb8  sub     rsp, 40h
0x140017fbc  xor     r13d, r13d
0x140017fbf  movzx   r15d, r9w
0x140017fc3  mov     rbx, rdx
0x140017fc6  mov     rdi, rcx
0x140017fc9  test    rdx, rdx
0x140017fcc  jz      short loc_14001802D
0x140017fce  movzx   eax, word ptr [rdx+3Ah]
0x140017fd2  mov     [rsp+68h+arg_0], ax
0x140017fd7  test    ax, ax
0x140017fda  jz      short loc_140018033
0x140017fdc  mov     eax, [rcx+78h]
0x140017fdf  mov     bpl, r13b
0x140017fe2  test    al, 10h
0x140017fe4  jnz     short loc_140018036
0x140017fe6  mov     rcx, cs:WPP_GLOBAL_Control
0x140017fed  lea     rax, WPP_GLOBAL_Control
0x140017ff4  cmp     rcx, rax
0x140017ff7  jz      short loc_14001801A
0x140017ff9  mov     eax, [rcx+2Ch]
0x140017ffc  test    al, 10h
0x140017ffe  jz      short loc_14001801A
0x140018000  cmp     byte ptr [rcx+29h], 1
0x140018004  jb      short loc_14001801A
0x140018006  mov     rcx, [rcx+18h]
0x14001800a  lea     edx, [r13+2Bh]
0x14001800e  lea     r8, WPP_b05af37f07f737f49b91eab4cb6eaae9_Traceguids
0x140018015  call    WPP_SF_
0x14001801a  inc     cs:g_ulSendZlbWithoutHostRoute
0x140018020  mov     rcx, rbx
0x140018023  call    DereferenceCall
0x140018028  jmp     loc_140018186
0x14001802d  mov     [rsp+68h+arg_0], r13w
0x140018033  mov     bpl, 1
0x140018036  mov     r14, [rcx+18h]
0x14001803a  xor     r8d, r8d; ContextBackFill
0x14001803d  xor     edx, edx; ContextSize
0x14001803f  mov     rcx, [r14+0E0h]; PoolHandle
0x140018046  call    cs:__imp_NdisAllocateNetBufferList
0x14001804d  nop     dword ptr [rax+rax+00h]
0x140018052  mov     rsi, rax
0x140018055  test    rax, rax
0x140018058  jnz     short loc_140018098
0x14001805a  mov     rcx, cs:WPP_GLOBAL_Control
0x140018061  lea     rax, WPP_GLOBAL_Control
0x140018068  cmp     rcx, rax
0x14001806b  jz      short loc_14001808D
0x14001806d  mov     eax, [rcx+2Ch]
0x140018070  test    al, 10h
0x140018072  jz      short loc_14001808D
0x140018074  cmp     byte ptr [rcx+29h], 1
0x140018078  jb      short loc_14001808D
0x14001807a  mov     rcx, [rcx+18h]
0x14001807e  lea     edx, [rsi+2Ch]
0x140018081  lea     r8, WPP_b05af37f07f737f49b91eab4cb6eaae9_Traceguids
0x140018088  call    WPP_SF_
0x14001808d  test    rbx, rbx
0x140018090  jz      loc_140018186
0x140018096  jmp     short loc_140018020
0x140018098  mov     rcx, [rax+8]; NetBuffer
0x14001809c  xor     r9d, r9d; AllocateMdlHandler
0x14001809f  xor     r8d, r8d; DataBackFill
0x1400180a2  lea     edx, [r9+2Ah]; DataOffsetDelta
0x1400180a6  call    cs:__imp_NdisRetreatNetBufferDataStart
0x1400180ad  nop     dword ptr [rax+rax+00h]
0x1400180b2  mov     rcx, [rsi+8]; NetBuffer
0x1400180b6  mov     r9d, 1; AlignMultiple
0x1400180bc  xor     r8d, r8d; Storage
0x1400180bf  mov     [rsp+68h+AlignOffset], r13d; AlignOffset
0x1400180c4  lea     edx, [r9+29h]; BytesNeeded
0x1400180c8  call    cs:__imp_NdisGetDataBuffer
0x1400180cf  nop     dword ptr [rax+rax+00h]
0x1400180d4  mov     r8b, [rsp+68h+arg_20]
0x1400180dc  lea     rcx, [rsp+68h+arg_10]
0x1400180e4  xorps   xmm0, xmm0
0x1400180e7  mov     [rsp+68h+var_38], r15w
0x1400180ed  mov     [rsp+68h+var_40], rcx
0x1400180f2  lea     r9, [rdi+74h]
0x1400180f6  movups  xmmword ptr [rax], xmm0
0x1400180f9  lea     rcx, [rsp+68h+arg_0]
0x1400180fe  mov     dl, bpl
0x140018101  mov     qword ptr [rsp+68h+AlignOffset], rcx
0x140018106  mov     rcx, rax
0x140018109  movups  xmmword ptr [rax+10h], xmm0
0x14001810d  movups  xmmword ptr [rax+1Ah], xmm0
0x140018111  call    BuildL2tpHeader
0x140018116  mov     rcx, [rsi+8]
0x14001811a  mov     r9d, 4
0x140018120  mov     rdx, r14
0x140018123  mov     [rcx+18h], eax
0x140018126  mov     rcx, rdi
0x140018129  mov     rax, [rsi+8]
0x14001812d  mov     [rax+80h], rsi
0x140018134  mov     rax, [rsi+8]
0x140018138  mov     [rax+90h], rbx
0x14001813f  mov     r8, [rsi+8]
0x140018143  mov     qword ptr [rsp+68h+AlignOffset], r8
0x140018148  call    L2tpSendDatagram
0x14001814d  mov     r9d, eax
0x140018150  mov     rcx, cs:WPP_GLOBAL_Control
0x140018157  lea     rax, WPP_GLOBAL_Control
0x14001815e  cmp     rcx, rax
0x140018161  jz      short loc_140018186
0x140018163  mov     edx, [rcx+2Ch]
0x140018166  test    dl, 10h
0x140018169  jz      short loc_140018186
0x14001816b  cmp     byte ptr [rcx+29h], 4
0x14001816f  jb      short loc_140018186
0x140018171  mov     rcx, [rcx+18h]
0x140018175  lea     r8, WPP_b05af37f07f737f49b91eab4cb6eaae9_Traceguids
0x14001817c  mov     edx, 2Dh ; '-'
0x140018181  call    WPP_SF_d
0x140018186  lea     r11, [rsp+68h+var_28]
0x14001818b  mov     rbx, [r11+38h]
0x14001818f  mov     rbp, [r11+48h]
0x140018193  mov     rsp, r11
0x140018196  pop     r15
0x140018198  pop     r14
0x14001819a  pop     r13
0x14001819c  pop     rdi
0x14001819d  pop     rsi
0x14001819e  retn
```
