# MPSendNetBufferListChain

- ea: `0x1400019a0`
- end: `0x140001bd4`
- name: `MPSendNetBufferListChain`
- size: `564`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1400019a0`
- `0x140001be0`
- `0x14000a290`
- `0x14000a2c0`
- `0x14000a648`

## import_xrefs

- `NDIS!NdisMSendNetBufferListsComplete` at `0x140001b9f`
- `NDIS!NdisMSendNetBufferListsComplete` at `0x140001b9f`
- `NDIS!NdisAllocateNetBufferListContext` at `0x140001a26`
- `NDIS!NdisAllocateNetBufferListContext` at `0x140001a26`

## pseudocode

```c
void __fastcall MPSendNetBufferListChain(__int64 a1, PNET_BUFFER_LIST Alignment)
{
  __int64 v4; // r9
  PNET_BUFFER_LIST *p_NetBufferList; // rsi
  SLIST_HEADER *v6; // rax
  struct _NET_BUFFER_LIST *v7; // rbp
  char *v8; // rdx
  PNET_BUFFER_LIST v9; // rax
  PNET_BUFFER_LIST NetBufferList; // [rsp+40h] [rbp+8h] BYREF

  NetBufferList = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_57c91ebf850d312e4ec0e2452bcf32f2_Traceguids);
  }
  v4 = *(unsigned int *)(a1 + 20);
  if ( !(_DWORD)v4 )
  {
    p_NetBufferList = &NetBufferList;
    if ( !Alignment )
      goto LABEL_11;
    do
    {
      v6 = (SLIST_HEADER *)Alignment;
      v7 = Alignment;
      Alignment = (PNET_BUFFER_LIST)Alignment->Link.Alignment;
      v6->Alignment = 0;
      if ( NdisAllocateNetBufferListContext(v7, 0x80u, 0, 0x444E6157u) )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
        {
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_57c91ebf850d312e4ec0e2452bcf32f2_Traceguids, v7);
        }
        v7->Status = -1073741670;
        *p_NetBufferList = v7;
        p_NetBufferList = &v7->Next;
      }
      else
      {
        v8 = (char *)v7->Context + v7->Context->Offset;
        *((_OWORD *)v8 + 1) = 0;
        *((_OWORD *)v8 + 2) = 0;
        *((_OWORD *)v8 + 3) = 0;
        *((_OWORD *)v8 + 4) = 0;
        *((_OWORD *)v8 + 5) = 0;
        *((_OWORD *)v8 + 6) = 0;
        *((_OWORD *)v8 + 7) = 0;
        *((_OWORD *)v8 + 8) = 0;
        *((_QWORD *)v8 + 17) = v7->SourceHandle;
        *((_DWORD *)v8 + 8) = 1684956499;
        ApplyQoSAndQueueSend(a1, v7);
      }
    }
    while ( Alignment );
    Alignment = NetBufferList;
    goto LABEL_9;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 27, WPP_57c91ebf850d312e4ec0e2452bcf32f2_Traceguids, v4);
  }
  v9 = Alignment;
  if ( Alignment )
  {
    do
    {
      v9->Status = -1071448022;
      v9 = (PNET_BUFFER_LIST)v9->Link.Alignment;
    }
    while ( v9 );
LABEL_9:
    if ( Alignment )
      NdisMSendNetBufferListsComplete(*(NDIS_HANDLE *)(a1 + 40), Alignment, 0);
  }
LABEL_11:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 29, WPP_57c91ebf850d312e4ec0e2452bcf32f2_Traceguids);
  }
}

```

## disassembly

```asm
0x1400019a0  sub     rsp, 38h
0x1400019a4  mov     [rsp+38h+arg_8], rbx
0x1400019a9  mov     rbx, rdx
0x1400019ac  mov     [rsp+38h+var_8], rdi
0x1400019b1  mov     rdi, rcx
0x1400019b4  mov     [rsp+38h+var_10], r14
0x1400019b9  mov     [rsp+38h+var_18], r15
0x1400019be  xor     r15d, r15d
0x1400019c1  mov     [rsp+38h+NetBufferList], r15
0x1400019c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400019cd  lea     r14, WPP_GLOBAL_Control
0x1400019d4  cmp     rcx, r14
0x1400019d7  jz      short loc_1400019E4
0x1400019d9  mov     eax, [rcx+2Ch]
0x1400019dc  test    al, 8
0x1400019de  jnz     loc_140001ADA
0x1400019e4  mov     r9d, [rdi+14h]
0x1400019e8  mov     [rsp+38h+arg_18], rsi
0x1400019ed  test    r9d, r9d
0x1400019f0  jnz     loc_140001AFE
0x1400019f6  lea     rsi, [rsp+38h+NetBufferList]
0x1400019fb  test    rbx, rbx
0x1400019fe  jz      loc_140001AA4
0x140001a04  mov     [rsp+38h+arg_10], rbp
0x140001a09  mov     rax, rbx
0x140001a0c  mov     rbp, rbx
0x140001a0f  mov     rbx, [rbx]
0x140001a12  xor     r8d, r8d; ContextBackFill
0x140001a15  mov     edx, 80h; ContextSize
0x140001a1a  mov     r9d, 444E6157h; PoolTag
0x140001a20  mov     rcx, rbp; NetBufferList
0x140001a23  mov     [rax], r15
0x140001a26  call    cs:__imp_NdisAllocateNetBufferListContext
0x140001a2d  nop     dword ptr [rax+rax+00h]
0x140001a32  test    eax, eax
0x140001a34  jnz     loc_140001B4F
0x140001a3a  mov     rcx, [rbp+10h]
0x140001a3e  xorps   xmm0, xmm0
0x140001a41  movzx   edx, word ptr [rcx+0Ah]
0x140001a45  add     rdx, rcx
0x140001a48  mov     rcx, rdi
0x140001a4b  movups  xmmword ptr [rdx+10h], xmm0
0x140001a4f  movups  xmmword ptr [rdx+20h], xmm0
0x140001a53  movups  xmmword ptr [rdx+30h], xmm0
0x140001a57  movups  xmmword ptr [rdx+40h], xmm0
0x140001a5b  movups  xmmword ptr [rdx+50h], xmm0
0x140001a5f  movups  xmmword ptr [rdx+60h], xmm0
0x140001a63  movups  xmmword ptr [rdx+70h], xmm0
0x140001a67  movups  xmmword ptr [rdx+80h], xmm0
0x140001a6e  mov     rax, [rbp+78h]
0x140001a72  mov     [rdx+88h], rax
0x140001a79  mov     dword ptr [rdx+20h], 646E6553h
0x140001a80  mov     rdx, rbp
0x140001a83  call    ApplyQoSAndQueueSend
0x140001a88  test    rbx, rbx
0x140001a8b  jnz     loc_140001A09
0x140001a91  mov     rbp, [rsp+38h+arg_10]
0x140001a96  mov     rbx, [rsp+38h+NetBufferList]
0x140001a9b  test    rbx, rbx
0x140001a9e  jnz     loc_140001B95
0x140001aa4  mov     rcx, cs:WPP_GLOBAL_Control
0x140001aab  mov     r15, [rsp+38h+var_18]
0x140001ab0  cmp     rcx, r14
0x140001ab3  mov     r14, [rsp+38h+var_10]
0x140001ab8  mov     rdi, [rsp+38h+var_8]
0x140001abd  mov     rsi, [rsp+38h+arg_18]
0x140001ac2  mov     rbx, [rsp+38h+arg_8]
0x140001ac7  jz      short loc_140001AD4
0x140001ac9  mov     eax, [rcx+2Ch]
0x140001acc  test    al, 8
0x140001ace  jnz     loc_140001BB0
0x140001ad4  add     rsp, 38h
0x140001ad8  retn
0x140001ada  cmp     byte ptr [rcx+29h], 5
0x140001ade  jb      loc_1400019E4
0x140001ae4  mov     rcx, [rcx+18h]
0x140001ae8  lea     r8, WPP_57c91ebf850d312e4ec0e2452bcf32f2_Traceguids
0x140001aef  mov     edx, 1Ah
0x140001af4  call    WPP_SF_
0x140001af9  jmp     loc_1400019E4
0x140001afe  mov     rcx, cs:WPP_GLOBAL_Control
0x140001b05  cmp     rcx, r14
0x140001b08  jz      short loc_140001B2C
0x140001b0a  mov     eax, [rcx+2Ch]
0x140001b0d  test    al, 8
0x140001b0f  jz      short loc_140001B2C
0x140001b11  cmp     byte ptr [rcx+29h], 5
0x140001b15  jb      short loc_140001B2C
0x140001b17  mov     rcx, [rcx+18h]
0x140001b1b  lea     r8, WPP_57c91ebf850d312e4ec0e2452bcf32f2_Traceguids
0x140001b22  mov     edx, 1Bh
0x140001b27  call    WPP_SF_d
0x140001b2c  mov     rax, rbx
0x140001b2f  test    rbx, rbx
0x140001b32  jz      loc_140001AA4
0x140001b38  mov     dword ptr [rax+8Ch], 0C023002Ah
0x140001b42  mov     rax, [rax]
0x140001b45  test    rax, rax
0x140001b48  jnz     short loc_140001B38
0x140001b4a  jmp     loc_140001A9B
0x140001b4f  mov     rcx, cs:WPP_GLOBAL_Control
0x140001b56  cmp     rcx, r14
0x140001b59  jz      short loc_140001B80
0x140001b5b  mov     eax, [rcx+2Ch]
0x140001b5e  test    al, 8
0x140001b60  jz      short loc_140001B80
0x140001b62  cmp     byte ptr [rcx+29h], 3
0x140001b66  jb      short loc_140001B80
0x140001b68  mov     rcx, [rcx+18h]
0x140001b6c  lea     r8, WPP_57c91ebf850d312e4ec0e2452bcf32f2_Traceguids
0x140001b73  mov     edx, 1Ch
0x140001b78  mov     r9, rbp
0x140001b7b  call    WPP_SF_q
0x140001b80  mov     dword ptr [rbp+8Ch], 0C000009Ah
0x140001b8a  mov     [rsi], rbp
0x140001b8d  mov     rsi, rbp
0x140001b90  jmp     loc_140001A88
0x140001b95  mov     rcx, [rdi+28h]; MiniportAdapterHandle
0x140001b99  xor     r8d, r8d; SendCompleteFlags
0x140001b9c  mov     rdx, rbx; NetBufferList
0x140001b9f  call    cs:__imp_NdisMSendNetBufferListsComplete
0x140001ba6  nop     dword ptr [rax+rax+00h]
0x140001bab  jmp     loc_140001AA4
0x140001bb0  cmp     byte ptr [rcx+29h], 5
0x140001bb4  jb      loc_140001AD4
0x140001bba  mov     rcx, [rcx+18h]
0x140001bbe  lea     r8, WPP_57c91ebf850d312e4ec0e2452bcf32f2_Traceguids
0x140001bc5  mov     edx, 1Dh
0x140001bca  call    WPP_SF_
0x140001bcf  jmp     loc_140001AD4
```
