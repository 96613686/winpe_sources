# PcpSchedulerCompletePacket

- ea: `0x140008440`
- end: `0x1400085ac`
- name: `PcpSchedulerCompletePacket`
- size: `364`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1400110d8`

## callees

- `0x14000298c`
- `0x140003770`
- `0x140008440`
- `0x140009100`
- `0x140011ae8`

## import_xrefs

- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400084af`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400084af`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140008476`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140008476`
- `NDIS!NdisFreeNetBufferListContext` at `0x140008588`
- `NDIS!NdisFreeNetBufferListContext` at `0x140008588`
- `NDIS!NdisFSendNetBufferListsComplete` at `0x1400084f7`
- `NDIS!NdisFSendNetBufferListsComplete` at `0x1400084f7`

## pseudocode

```c
void __fastcall PcpSchedulerCompletePacket(__int64 a1, _QWORD *a2, struct _NET_BUFFER_LIST *a3, ULONG a4)
{
  NDIS_HANDLE v8; // rax
  unsigned int v9; // edi
  __int64 v10; // rax
  PVOID v11; // rcx
  __int64 v12; // r8
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+20h] [rbp-38h] BYREF
  struct _NET_BUFFER_LIST *v14; // [rsp+60h] [rbp+8h] BYREF

  memset(&LockHandle, 0, sizeof(LockHandle));
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(a1 + 96), &LockHandle);
  while ( *(_DWORD *)(a1 + 104) )
    ;
  v8 = (NDIS_HANDLE)a2[7];
  v9 = 0;
  v14 = a3;
  if ( a3->SourceHandle == v8 && !*(_DWORD *)&a3->Context->ContextData[a3->Context->Offset + 40] )
  {
    v12 = a4;
    LOBYTE(v12) = a4 & 1;
    QosNblCadComplete(a3, &v14, v12);
    a3 = v14;
    v9 = 1;
  }
  if ( a3 )
    _InterlockedIncrement((volatile signed __int32 *)(a1 + 172));
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  if ( a3 )
  {
    v10 = a2[32];
    if ( *(_DWORD *)(v10 + 16) == 3 && *(_WORD *)(v10 + 212) == 2048 )
    {
      PcpLineDereference(a2);
      NdisFreeNetBufferListContext(a3, 8u);
    }
    v11 = a3->NetBufferListInfo[3];
    if ( v11 && v11 == *(PVOID *)&WPP_MAIN_CB.DeviceLock.Header.Lock )
    {
      PcpDereferenceFlow(v11);
      a3->NetBufferListInfo[3] = 0;
    }
    NdisFSendNetBufferListsComplete(*(NDIS_HANDLE *)(a2[32] + 40LL), a3, a4);
  }
  if ( v9 )
    PcpFilterDecrementPauseCount(a2[32], v9);
}

```

## disassembly

```asm
0x140008440  mov     [rsp+arg_8], rbx
0x140008445  mov     [rsp+arg_10], rbp
0x14000844a  push    rsi
0x14000844b  push    rdi
0x14000844c  push    r14
0x14000844e  sub     rsp, 40h
0x140008452  mov     rsi, rdx
0x140008455  mov     rbp, rcx
0x140008458  xorps   xmm0, xmm0
0x14000845b  lea     rdx, [rsp+58h+LockHandle]; LockHandle
0x140008460  xor     eax, eax
0x140008462  add     rcx, 60h ; '`'; SpinLock
0x140008466  movups  xmmword ptr [rsp+58h+LockHandle.LockQueue.Next], xmm0
0x14000846b  mov     qword ptr [rsp+58h+LockHandle.OldIrql], rax
0x140008470  mov     r14d, r9d
0x140008473  mov     rbx, r8
0x140008476  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14000847d  nop     dword ptr [rax+rax+00h]
0x140008482  mov     eax, [rbp+68h]
0x140008485  test    eax, eax
0x140008487  jnz     short loc_140008482
0x140008489  mov     rax, [rsi+38h]
0x14000848d  xor     edi, edi
0x14000848f  mov     [rsp+58h+arg_0], rbx
0x140008494  cmp     [rbx+78h], rax
0x140008498  jz      loc_140008531
0x14000849e  test    rbx, rbx
0x1400084a1  jz      short loc_1400084AA
0x1400084a3  lock inc dword ptr [rbp+0ACh]
0x1400084aa  lea     rcx, [rsp+58h+LockHandle]; LockHandle
0x1400084af  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400084b6  nop     dword ptr [rax+rax+00h]
0x1400084bb  test    rbx, rbx
0x1400084be  jz      short loc_140008503
0x1400084c0  mov     rax, [rsi+100h]
0x1400084c7  cmp     dword ptr [rax+10h], 3
0x1400084cb  jz      loc_140008566
0x1400084d1  mov     rcx, [rbx+0A8h]
0x1400084d8  test    rcx, rcx
0x1400084db  jz      short loc_1400084E6
0x1400084dd  cmp     rcx, qword ptr cs:WPP_MAIN_CB.DeviceLock.Header
0x1400084e4  jz      short loc_14000851F
0x1400084e6  mov     rcx, [rsi+100h]
0x1400084ed  mov     r8d, r14d; SendCompleteFlags
0x1400084f0  mov     rdx, rbx; NetBufferList
0x1400084f3  mov     rcx, [rcx+28h]; NdisFilterHandle
0x1400084f7  call    cs:__imp_NdisFSendNetBufferListsComplete
0x1400084fe  nop     dword ptr [rax+rax+00h]
0x140008503  test    edi, edi
0x140008505  jnz     loc_140008599
0x14000850b  mov     rbx, [rsp+58h+arg_8]
0x140008510  mov     rbp, [rsp+58h+arg_10]
0x140008515  add     rsp, 40h
0x140008519  pop     r14
0x14000851b  pop     rdi
0x14000851c  pop     rsi
0x14000851d  retn
0x14000851f  call    PcpDereferenceFlow
0x140008524  mov     qword ptr [rbx+0A8h], 0
0x14000852f  jmp     short loc_1400084E6
0x140008531  mov     rcx, [rbx+10h]
0x140008535  movzx   eax, word ptr [rcx+0Ah]
0x140008539  cmp     [rax+rcx+38h], edi
0x14000853d  jnz     loc_14000849E
0x140008543  mov     r8d, r14d
0x140008546  lea     rdx, [rsp+58h+arg_0]
0x14000854b  and     r8b, 1
0x14000854f  mov     rcx, rbx
0x140008552  call    QosNblCadComplete
0x140008557  mov     rbx, [rsp+58h+arg_0]
0x14000855c  mov     edi, 1
0x140008561  jmp     loc_14000849E
0x140008566  mov     ecx, 800h
0x14000856b  cmp     [rax+0D4h], cx
0x140008572  jnz     loc_1400084D1
0x140008578  mov     rcx, rsi; P
0x14000857b  call    PcpLineDereference
0x140008580  mov     edx, 8; ContextSize
0x140008585  mov     rcx, rbx; NetBufferList
0x140008588  call    cs:__imp_NdisFreeNetBufferListContext
0x14000858f  nop     dword ptr [rax+rax+00h]
0x140008594  jmp     loc_1400084D1
0x140008599  mov     rcx, [rsi+100h]
0x1400085a0  mov     edx, edi
0x1400085a2  call    PcpFilterDecrementPauseCount
0x1400085a7  jmp     loc_14000850B
```
