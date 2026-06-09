# PcpIndicateDelayQueueConsumerEnd

- ea: `0x140007f90`
- end: `0x14000827c`
- name: `PcpIndicateDelayQueueConsumerEnd`
- size: `748`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x14000cce0`

## callees

- `0x140003770`
- `0x140007e10`
- `0x140007f90`
- `0x140008290`
- `0x140009100`
- `0x140009b80`
- `0x14000a8c4`
- `0x140011154`
- `0x140011904`
- `0x140011a34`
- `0x140012410`

## import_xrefs

- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14000821f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14000821f`
- `NDIS!NdisReleaseRWLock` at `0x1400081d6`
- `NDIS!NdisReleaseRWLock` at `0x1400081d6`
- `NDIS!NdisAcquireRWLockWrite` at `0x1400081b5`
- `NDIS!NdisAcquireRWLockWrite` at `0x1400081b5`
- `HAL!KeQueryPerformanceCounter` at `0x140008061`
- `HAL!KeQueryPerformanceCounter` at `0x140008061`

## pseudocode

```c
__int64 __fastcall PcpIndicateDelayQueueConsumerEnd(unsigned int a1)
{
  __int64 result; // rax
  unsigned __int64 v2; // r8
  __int64 *v5; // r14
  __int64 v6; // rbx
  unsigned __int64 v7; // rsi
  __int64 v8; // rbx
  LARGE_INTEGER v9; // rax
  union _LARGE_INTEGER v10; // r8
  LARGE_INTEGER v11; // r9
  __int64 v12; // rdx
  unsigned __int64 v13; // rcx
  unsigned __int8 v14; // al
  unsigned __int8 v15; // al
  unsigned __int8 v16; // r8
  __int64 *v17; // r12
  struct _NET_BUFFER_LIST *v18; // r15
  int v19; // eax
  struct _NET_BUFFER_LIST *v20; // rsi
  PVOID *v21; // rax
  PNDIS_RW_LOCK_EX *v22; // rsi
  __int64 v23; // rdx
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+38h] [rbp-29h] BYREF
  _OWORD v25[2]; // [rsp+50h] [rbp-11h] BYREF
  int v26; // [rsp+70h] [rbp+Fh]
  struct _LOCK_STATE_EX LockState; // [rsp+C8h] [rbp+67h] BYREF
  union _LARGE_INTEGER PerformanceFrequency; // [rsp+D0h] [rbp+6Fh] BYREF
  struct _NET_BUFFER_LIST *v29; // [rsp+D8h] [rbp+77h] BYREF
  struct _NET_BUFFER_LIST *v30; // [rsp+E0h] [rbp+7Fh] BYREF

  result = (__int64)PcgDelayQueue;
  v2 = (unsigned __int64)a1 << 6;
  if ( (*(_DWORD *)((char *)PcgDelayQueue + v2 + 16))-- == 1 )
  {
    memset(&LockHandle, 0, sizeof(LockHandle));
    *(_WORD *)&LockState.OldIrql = 0;
    LockState.Flags = 0;
    *(_QWORD *)(v2 + result + 8) = 0;
    v5 = *(__int64 **)(v2 + result);
    *(_QWORD *)(v2 + result) = 0;
    result = QosgTimerTable;
    v6 = MEMORY[0xFFFFF78000000008];
    memset(v25, 0, sizeof(v25));
    v26 = 0;
    v7 = ((unsigned __int64)a1 << 7) + *(_QWORD *)QosgTimerTable;
    if ( MEMORY[0xFFFFF78000000008] != *(_QWORD *)(v7 + 8) )
    {
      PerformanceFrequency.QuadPart = 0;
      v9 = KeQueryPerformanceCounter(&PerformanceFrequency);
      v10 = PerformanceFrequency;
      v11 = v9;
      v12 = *(unsigned __int8 *)(v7 + 112);
      v13 = ((1000000 * HIDWORD(v9.QuadPart) / (unsigned __int64)PerformanceFrequency.QuadPart) << 32)
          + (1000000LL * v9.LowPart
           + ((1000000 * HIDWORD(v9.QuadPart) % (unsigned __int64)PerformanceFrequency.QuadPart) << 32))
          / PerformanceFrequency.QuadPart;
      if ( (_BYTE)v12 )
        v14 = v12 - 1;
      else
        v14 = 2;
      if ( (__int64)(*(_QWORD *)(v7 + 8LL * v14 + 64) - v13) > 0 )
      {
        *(_QWORD *)(v7 + 8 * v12 + 16) = *(_QWORD *)(v7 + 8LL * v14 + 16);
        *(_QWORD *)(v7 + 8 * v12 + 40) = *(_QWORD *)(v7 + 8LL * v14 + 40);
        *(_QWORD *)(v7 + 8 * v12 + 64) = *(_QWORD *)(v7 + 8LL * v14 + 64);
        v13 = *(_QWORD *)(v7 + 8LL * v14 + 64);
      }
      else
      {
        *(LARGE_INTEGER *)(v7 + 8 * v12 + 16) = v11;
        *(union _LARGE_INTEGER *)(v7 + 8 * v12 + 40) = v10;
        *(_QWORD *)(v7 + 8 * v12 + 64) = v13;
      }
      *(_QWORD *)(v7 + 8 * v12 + 88) = v6;
      v15 = *(_BYTE *)(v7 + 112) + 1;
      *(_QWORD *)v7 = v13;
      v16 = v15;
      *(_QWORD *)(v7 + 8) = v6;
      result = 3 * (v15 / 3u);
      *(_BYTE *)(v7 + 112) = v16 - result;
    }
    v8 = *(_QWORD *)v7;
    if ( v5 )
    {
      do
      {
        v17 = (__int64 *)*v5;
        RtlAcquireWriteLockAtDpcLevel(v5 + 7, &LockHandle);
        *((_DWORD *)v5 + 144) &= ~4u;
        v18 = 0;
        v19 = *((_DWORD *)v5 + 144);
        v20 = 0;
        v29 = 0;
        v30 = 0;
        PerformanceFrequency.LowPart = 0;
        if ( (v19 & 8) == 0 )
        {
          if ( (unsigned __int8)QosFlowNeedQueueFeedback(v5 + 12, v8, v25) )
          {
            v21 = PcpLineFindByLuid((PVOID)v5[6]);
            v22 = (PNDIS_RW_LOCK_EX *)v21;
            if ( v21 )
            {
              PcpLineSignalExternalEvent(v21, a1);
              NdisAcquireRWLockWrite(v22[2], &LockState, 0);
              QosLineQueryQueueFeedback(v22 + 3, v23, v25);
              NdisReleaseRWLock(v22[2], &LockState);
              PcpLineDereference(v22);
              QosTbcAdjustSendWindow(v5 + 12, v25);
            }
          }
          QosFlowProcessQueuedNetBufferLists(
            (_DWORD)v5 + 96,
            a1,
            (unsigned int)&v29,
            (unsigned int)&PerformanceFrequency,
            (__int64)&v30);
          v18 = v29;
          v20 = v30;
        }
        KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
        if ( v18 )
          PcpSchedulerBatchAndSendOrDropNblChain(v18, a1, 0, 1);
        if ( v20 )
          PcpSchedulerBatchAndSendOrDropNblChain(v20, a1, 0, 0);
        result = PcpDereferenceFlow(v5 - 5);
        v5 = v17;
      }
      while ( v17 );
    }
  }
  return result;
}

```

## disassembly

```asm
0x140007f90  mov     r11, rsp
0x140007f93  push    rbp
0x140007f94  push    rdi
0x140007f95  lea     rbp, [r11-5Fh]
0x140007f99  sub     rsp, 0A8h
0x140007fa0  mov     rax, cs:PcgDelayQueue
0x140007fa7  mov     r8d, ecx
0x140007faa  shl     r8, 6
0x140007fae  mov     edi, ecx
0x140007fb0  mov     r9d, ecx
0x140007fb3  add     dword ptr [r8+rax+10h], 0FFFFFFFFh
0x140007fb9  jnz     loc_14000804E
0x140007fbf  mov     [r11-18h], rbx
0x140007fc3  xor     ecx, ecx
0x140007fc5  mov     [r11-20h], rsi
0x140007fc9  xorps   xmm0, xmm0
0x140007fcc  movups  xmmword ptr [rbp+57h+LockHandle.LockQueue.Next], xmm0
0x140007fd0  mov     qword ptr [rbp+57h+LockHandle.OldIrql], rcx
0x140007fd4  mov     rbx, 0FFFFF78000000008h
0x140007fde  mov     word ptr [rbp+57h+LockState.OldIrql], cx
0x140007fe2  mov     [rbp+57h+LockState.Flags], cl
0x140007fe5  mov     [r11-30h], r13
0x140007fe9  xor     r13d, r13d
0x140007fec  mov     [r8+rax+8], r13
0x140007ff1  shl     r9, 7
0x140007ff5  mov     [r11-38h], r14
0x140007ff9  mov     r14, [r8+rax]
0x140007ffd  mov     [r8+rax], r13
0x140008001  mov     rax, cs:QosgTimerTable
0x140008008  mov     rbx, [rbx]
0x14000800b  movups  [rbp+57h+var_68], xmm0
0x14000800f  mov     [rbp+57h+var_48], ecx
0x140008012  mov     rsi, [rax]
0x140008015  add     rsi, r9
0x140008018  movups  [rbp+57h+var_58], xmm0
0x14000801c  cmp     rbx, [rsi+8]
0x140008020  jnz     short loc_140008059
0x140008022  mov     rbx, [rsi]
0x140008025  test    r14, r14
0x140008028  jnz     loc_140008135
0x14000802e  mov     r13, [rsp+0B0h+var_28]
0x140008036  mov     rsi, [rsp+0B0h+var_18]
0x14000803e  mov     rbx, [rsp+0A0h]
0x140008046  mov     r14, [rsp+0B0h+var_30]
0x14000804e  add     rsp, 0A8h
0x140008055  pop     rdi
0x140008056  pop     rbp
0x140008057  retn
0x140008059  lea     rcx, [rbp+57h+PerformanceFrequency]; PerformanceFrequency
0x14000805d  mov     qword ptr [rbp+57h+PerformanceFrequency], r13
0x140008061  call    cs:__imp_KeQueryPerformanceCounter
0x140008068  nop     dword ptr [rax+rax+00h]
0x14000806d  mov     r8, qword ptr [rbp+57h+PerformanceFrequency]
0x140008071  xor     edx, edx
0x140008073  mov     r9, rax
0x140008076  shr     rax, 20h
0x14000807a  imul    r10, rax, 0F4240h
0x140008081  mov     ecx, r9d
0x140008084  mov     rax, r10
0x140008087  div     r8
0x14000808a  mov     rax, rdx
0x14000808d  shl     rax, 20h
0x140008091  imul    rdx, rcx, 0F4240h
0x140008098  add     rax, rdx
0x14000809b  xor     edx, edx
0x14000809d  div     r8
0x1400080a0  xor     edx, edx
0x1400080a2  mov     rcx, rax
0x1400080a5  mov     rax, r10
0x1400080a8  div     r8
0x1400080ab  movzx   edx, byte ptr [rsi+70h]
0x1400080af  shl     rax, 20h
0x1400080b3  add     rcx, rax
0x1400080b6  test    dl, dl
0x1400080b8  jz      short loc_14000810C
0x1400080ba  lea     eax, [rdx-1]
0x1400080bd  movzx   r10d, al
0x1400080c1  mov     rax, [rsi+r10*8+40h]
0x1400080c6  sub     rax, rcx
0x1400080c9  test    rax, rax
0x1400080cc  jg      short loc_140008110
0x1400080ce  mov     [rsi+rdx*8+10h], r9
0x1400080d3  mov     [rsi+rdx*8+28h], r8
0x1400080d8  mov     [rsi+rdx*8+40h], rcx
0x1400080dd  mov     [rsi+rdx*8+58h], rbx
0x1400080e2  movzx   eax, byte ptr [rsi+70h]
0x1400080e6  inc     al
0x1400080e8  mov     [rsi], rcx
0x1400080eb  movzx   r8d, al
0x1400080ef  mov     eax, 0AAAAAAABh
0x1400080f4  mul     r8d
0x1400080f7  mov     [rsi+8], rbx
0x1400080fb  shr     edx, 1
0x1400080fd  lea     eax, [rdx+rdx*2]
0x140008100  sub     r8d, eax
0x140008103  mov     [rsi+70h], r8b
0x140008107  jmp     loc_140008022
0x14000810c  mov     al, 2
0x14000810e  jmp     short loc_1400080BD
0x140008110  mov     rax, [rsi+r10*8+10h]
0x140008115  mov     [rsi+rdx*8+10h], rax
0x14000811a  mov     rax, [rsi+r10*8+28h]
0x14000811f  mov     [rsi+rdx*8+28h], rax
0x140008124  mov     rax, [rsi+r10*8+40h]
0x140008129  mov     [rsi+rdx*8+40h], rax
0x14000812e  mov     rcx, [rsi+r10*8+40h]
0x140008133  jmp     short loc_1400080DD
0x140008135  mov     [rsp+0B0h+var_20], r12
0x14000813d  mov     [rsp+0B0h+var_38], r15
0x140008142  mov     r12, [r14]
0x140008145  lea     rcx, [r14+38h]
0x140008149  lea     rdx, [rbp+57h+LockHandle]
0x14000814d  call    RtlAcquireWriteLockAtDpcLevel
0x140008152  and     dword ptr [r14+240h], 0FFFFFFFBh
0x14000815a  mov     r15, r13
0x14000815d  mov     eax, [r14+240h]
0x140008164  mov     rsi, r13
0x140008167  mov     [rbp+57h+arg_10], r13
0x14000816b  mov     [rbp+57h+arg_18], r13
0x14000816f  mov     dword ptr [rbp+57h+PerformanceFrequency], r13d
0x140008173  test    al, 8
0x140008175  jnz     loc_14000821B
0x14000817b  lea     r8, [rbp+57h+var_68]
0x14000817f  mov     rdx, rbx
0x140008182  lea     rcx, [r14+60h]
0x140008186  call    QosFlowNeedQueueFeedback
0x14000818b  test    al, al
0x14000818d  jz      short loc_1400081F7
0x14000818f  mov     rcx, [r14+30h]
0x140008193  call    PcpLineFindByLuid
0x140008198  mov     rsi, rax
0x14000819b  test    rax, rax
0x14000819e  jz      short loc_1400081F7
0x1400081a0  mov     edx, edi
0x1400081a2  mov     rcx, rax
0x1400081a5  call    PcpLineSignalExternalEvent
0x1400081aa  mov     rcx, [rsi+10h]; Lock
0x1400081ae  lea     rdx, [rbp+57h+LockState]; LockState
0x1400081b2  xor     r8d, r8d; Flags
0x1400081b5  call    cs:__imp_NdisAcquireRWLockWrite
0x1400081bc  nop     dword ptr [rax+rax+00h]
0x1400081c1  lea     rcx, [rsi+18h]
0x1400081c5  lea     r8, [rbp+57h+var_68]
0x1400081c9  call    QosLineQueryQueueFeedback
0x1400081ce  mov     rcx, [rsi+10h]; Lock
0x1400081d2  lea     rdx, [rbp+57h+LockState]; LockState
0x1400081d6  call    cs:__imp_NdisReleaseRWLock
0x1400081dd  nop     dword ptr [rax+rax+00h]
0x1400081e2  mov     rcx, rsi; P
0x1400081e5  call    PcpLineDereference
0x1400081ea  lea     rdx, [rbp+57h+var_68]
0x1400081ee  lea     rcx, [r14+60h]
0x1400081f2  call    QosTbcAdjustSendWindow
0x1400081f7  lea     rax, [rbp+57h+arg_18]
0x1400081fb  mov     edx, edi
0x1400081fd  lea     r9, [rbp+57h+PerformanceFrequency]
0x140008201  mov     [rsp+20h], rax
0x140008206  lea     r8, [rbp+57h+arg_10]
0x14000820a  lea     rcx, [r14+60h]
0x14000820e  call    QosFlowProcessQueuedNetBufferLists
0x140008213  mov     r15, [rbp+57h+arg_10]
0x140008217  mov     rsi, [rbp+57h+arg_18]
0x14000821b  lea     rcx, [rbp+57h+LockHandle]; LockHandle
0x14000821f  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x140008226  nop     dword ptr [rax+rax+00h]
0x14000822b  test    r15, r15
0x14000822e  jz      short loc_140008240
0x140008230  mov     r9b, 1
0x140008233  xor     r8d, r8d
0x140008236  mov     edx, edi
0x140008238  mov     rcx, r15; NetBufferList
0x14000823b  call    PcpSchedulerBatchAndSendOrDropNblChain
0x140008240  test    rsi, rsi
0x140008243  jz      short loc_140008255
0x140008245  xor     r9d, r9d
0x140008248  xor     r8d, r8d
0x14000824b  mov     edx, edi
0x14000824d  mov     rcx, rsi; NetBufferList
0x140008250  call    PcpSchedulerBatchAndSendOrDropNblChain
0x140008255  lea     rcx, [r14-28h]
0x140008259  call    PcpDereferenceFlow
0x14000825e  mov     r14, r12
0x140008261  test    r12, r12
0x140008264  jnz     loc_140008142
0x14000826a  mov     r15, [rsp+0B0h+var_38]
0x14000826f  mov     r12, [rsp+0B0h+var_20]
0x140008277  jmp     loc_14000802E
```
