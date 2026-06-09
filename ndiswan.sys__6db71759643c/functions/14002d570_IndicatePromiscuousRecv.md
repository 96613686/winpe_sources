# IndicatePromiscuousRecv

- ea: `0x14002d570`
- end: `0x14002d72a`
- name: `IndicatePromiscuousRecv`
- size: `442`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x140004be0`
- `0x140007710`
- `0x1400242d4`
- `0x14002f620`
- `0x140032cd0`

## callees

- `0x14000e208`
- `0x14002d570`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x14002d698`
- `ntoskrnl!KfRaiseIrql` at `0x14002d698`
- `ntoskrnl!KeLowerIrql` at `0x14002d6cc`
- `ntoskrnl!KeLowerIrql` at `0x14002d6cc`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002d5b3`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002d68a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002d5b3`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002d68a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002d591`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002d6db`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002d591`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002d6db`
- `NDIS!NdisAllocateCloneNetBufferList` at `0x14002d5e4`
- `NDIS!NdisAllocateCloneNetBufferList` at `0x14002d5e4`
- `NDIS!NdisAdvanceNetBufferListDataStart` at `0x14002d6ff`
- `NDIS!NdisAdvanceNetBufferListDataStart` at `0x14002d6ff`
- `NDIS!NdisRetreatNetBufferListDataStart` at `0x14002d617`
- `NDIS!NdisRetreatNetBufferListDataStart` at `0x14002d617`
- `NDIS!NdisFreeCloneNetBufferList` at `0x14002d710`
- `NDIS!NdisFreeCloneNetBufferList` at `0x14002d710`
- `NDIS!NdisMIndicateReceiveNetBufferLists` at `0x14002d6be`
- `NDIS!NdisMIndicateReceiveNetBufferLists` at `0x14002d6be`
- `NDIS!NdisGetDataBuffer` at `0x14002d643`
- `NDIS!NdisGetDataBuffer` at `0x14002d643`

## pseudocode

```c
void __fastcall IndicatePromiscuousRecv(__int64 a1, __int64 a2, struct _NET_BUFFER_LIST *a3, int a4)
{
  __int64 v4; // rdi
  KIRQL v8; // al
  __int64 v9; // r15
  struct _NET_BUFFER_LIST *CloneNetBufferList; // rax
  struct _NET_BUFFER_LIST *v11; // rsi
  struct _NET_BUFFER *FirstNetBuffer; // rcx
  int v13; // ebx
  _DWORD *DataBuffer; // rcx
  char v15; // al
  KIRQL v16; // bl

  v4 = *(_QWORD *)(a2 + 24);
  v8 = KeAcquireSpinLockRaiseToDpc(&NdisWanCB);
  v9 = qword_14001E2D8;
  byte_14001E288 = v8;
  KeReleaseSpinLock(&NdisWanCB, v8);
  TraceNBL(a1, a3, 1);
  if ( v9 )
  {
    CloneNetBufferList = NdisAllocateCloneNetBufferList(a3, 0, 0, 0);
    v11 = CloneNetBufferList;
    if ( CloneNetBufferList )
    {
      if ( !a4 )
      {
        if ( NdisRetreatNetBufferListDataStart(CloneNetBufferList, 0xEu, 0, 0, 0) )
        {
LABEL_8:
          NdisFreeCloneNetBufferList(v11, 0);
          return;
        }
        FirstNetBuffer = v11->FirstNetBuffer;
        v13 = FirstNetBuffer->DataLength - 14;
        DataBuffer = NdisGetDataBuffer(FirstNetBuffer, 0xEu, 0, 1u, 0);
        *DataBuffer = 1312904992;
        DataBuffer[1] = 1461780306;
        DataBuffer[2] = -11383231;
        v15 = *(_BYTE *)(v4 + 40);
        *((_BYTE *)DataBuffer + 11) = v15;
        *((_BYTE *)DataBuffer + 5) = v15;
        *((_BYTE *)DataBuffer + 12) = BYTE1(v13);
        *((_BYTE *)DataBuffer + 13) = v13;
      }
      KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 1768), *(_BYTE *)(a1 + 1776));
      v16 = KfRaiseIrql(2u);
      NdisMIndicateReceiveNetBufferLists(*(NDIS_HANDLE *)(v9 + 40), v11, 0, 1u, 3u);
      KeLowerIrql(v16);
      *(_BYTE *)(a1 + 1776) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 1768));
      if ( !a4 )
        NdisAdvanceNetBufferListDataStart(v11, 0xEu, 1u, 0);
      goto LABEL_8;
    }
  }
}

```

## disassembly

```asm
0x14002d570  push    rbx
0x14002d572  push    rbp
0x14002d573  push    rsi
0x14002d574  push    rdi
0x14002d575  push    r14
0x14002d577  push    r15
0x14002d579  sub     rsp, 38h
0x14002d57d  mov     rdi, [rdx+18h]
0x14002d581  mov     rbp, rcx
0x14002d584  lea     rcx, NdisWanCB; SpinLock
0x14002d58b  mov     r14d, r9d
0x14002d58e  mov     rbx, r8
0x14002d591  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002d598  nop     dword ptr [rax+rax+00h]
0x14002d59d  mov     r15, cs:qword_14001E2D8
0x14002d5a4  lea     rcx, NdisWanCB; SpinLock
0x14002d5ab  mov     dl, al; NewIrql
0x14002d5ad  mov     cs:byte_14001E288, al
0x14002d5b3  call    cs:__imp_KeReleaseSpinLock
0x14002d5ba  nop     dword ptr [rax+rax+00h]
0x14002d5bf  mov     r8d, 1
0x14002d5c5  mov     rdx, rbx
0x14002d5c8  mov     rcx, rbp
0x14002d5cb  call    TraceNBL
0x14002d5d0  test    r15, r15
0x14002d5d3  jz      loc_14002D71C
0x14002d5d9  xor     r9d, r9d; AllocateCloneFlags
0x14002d5dc  xor     r8d, r8d; NetBufferPoolHandle
0x14002d5df  xor     edx, edx; NetBufferListPoolHandle
0x14002d5e1  mov     rcx, rbx; OriginalNetBufferList
0x14002d5e4  call    cs:__imp_NdisAllocateCloneNetBufferList
0x14002d5eb  nop     dword ptr [rax+rax+00h]
0x14002d5f0  mov     rsi, rax
0x14002d5f3  test    rax, rax
0x14002d5f6  jz      loc_14002D71C
0x14002d5fc  test    r14d, r14d
0x14002d5ff  jnz     short loc_14002D67A
0x14002d601  xor     r9d, r9d; AllocateMdlHandler
0x14002d604  mov     [rsp+68h+FreeMdlHandler], 0; FreeMdlHandler
0x14002d60d  xor     r8d, r8d; DataBackFill
0x14002d610  lea     edx, [r14+0Eh]; DataOffsetDelta
0x14002d614  mov     rcx, rax; NetBufferList
0x14002d617  call    cs:__imp_NdisRetreatNetBufferListDataStart
0x14002d61e  nop     dword ptr [rax+rax+00h]
0x14002d623  test    eax, eax
0x14002d625  jnz     loc_14002D70B
0x14002d62b  mov     rcx, [rsi+8]; NetBuffer
0x14002d62f  lea     r9d, [r14+1]; AlignMultiple
0x14002d633  xor     r8d, r8d; Storage
0x14002d636  mov     dword ptr [rsp+68h+FreeMdlHandler], eax; AlignOffset
0x14002d63a  lea     edx, [rax+0Eh]; BytesNeeded
0x14002d63d  mov     ebx, [rcx+18h]
0x14002d640  add     ebx, 0FFFFFFF2h
0x14002d643  call    cs:__imp_NdisGetDataBuffer
0x14002d64a  nop     dword ptr [rax+rax+00h]
0x14002d64f  mov     rcx, rax
0x14002d652  mov     dword ptr [rax], 4E415720h
0x14002d658  mov     dword ptr [rax+4], 5720FF52h
0x14002d65f  mov     dword ptr [rax+8], 0FF524E41h
0x14002d666  mov     al, [rdi+28h]
0x14002d669  mov     [rcx+0Bh], al
0x14002d66c  mov     [rcx+5], al
0x14002d66f  mov     eax, ebx
0x14002d671  shr     eax, 8
0x14002d674  mov     [rcx+0Ch], al
0x14002d677  mov     [rcx+0Dh], bl
0x14002d67a  mov     dl, [rbp+6F0h]; NewIrql
0x14002d680  lea     rdi, [rbp+6E8h]
0x14002d687  mov     rcx, rdi; SpinLock
0x14002d68a  call    cs:__imp_KeReleaseSpinLock
0x14002d691  nop     dword ptr [rax+rax+00h]
0x14002d696  mov     cl, 2; NewIrql
0x14002d698  call    cs:__imp_KfRaiseIrql
0x14002d69f  nop     dword ptr [rax+rax+00h]
0x14002d6a4  mov     rcx, [r15+28h]; MiniportAdapterHandle
0x14002d6a8  mov     r9d, 1; NumberOfNetBufferLists
0x14002d6ae  xor     r8d, r8d; PortNumber
0x14002d6b1  mov     dword ptr [rsp+68h+FreeMdlHandler], 3; ReceiveFlags
0x14002d6b9  mov     rdx, rsi; NetBufferList
0x14002d6bc  mov     bl, al
0x14002d6be  call    cs:__imp_NdisMIndicateReceiveNetBufferLists
0x14002d6c5  nop     dword ptr [rax+rax+00h]
0x14002d6ca  mov     cl, bl; NewIrql
0x14002d6cc  call    cs:__imp_KeLowerIrql
0x14002d6d3  nop     dword ptr [rax+rax+00h]
0x14002d6d8  mov     rcx, rdi; SpinLock
0x14002d6db  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002d6e2  nop     dword ptr [rax+rax+00h]
0x14002d6e7  mov     [rbp+6F0h], al
0x14002d6ed  test    r14d, r14d
0x14002d6f0  jnz     short loc_14002D70B
0x14002d6f2  xor     r9d, r9d; FreeMdlMdlHandler
0x14002d6f5  lea     edx, [r14+0Eh]; DataOffsetDelta
0x14002d6f9  mov     r8b, 1; FreeMdl
0x14002d6fc  mov     rcx, rsi; NetBufferList
0x14002d6ff  call    cs:__imp_NdisAdvanceNetBufferListDataStart
0x14002d706  nop     dword ptr [rax+rax+00h]
0x14002d70b  xor     edx, edx; FreeCloneFlags
0x14002d70d  mov     rcx, rsi; CloneNetBufferList
0x14002d710  call    cs:__imp_NdisFreeCloneNetBufferList
0x14002d717  nop     dword ptr [rax+rax+00h]
0x14002d71c  add     rsp, 38h
0x14002d720  pop     r15
0x14002d722  pop     r14
0x14002d724  pop     rdi
0x14002d725  pop     rsi
0x14002d726  pop     rbp
0x14002d727  pop     rbx
0x14002d728  retn
```
