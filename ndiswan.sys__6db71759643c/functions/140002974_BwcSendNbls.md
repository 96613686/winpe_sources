# BwcSendNbls

- ea: `0x140002974`
- end: `0x140002cb3`
- name: `BwcSendNbls`
- size: `831`
- prototype: ``
- caller_count: `2`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x140001be0`
- `0x140003620`

## callees

- `0x140002974`
- `0x14000917c`
- `0x1400091d0`
- `0x140009368`
- `0x140011da8`
- `0x1400123e4`
- `0x140012480`
- `0x140012df8`
- `0x140012e70`
- `0x140013a04`
- `0x140013f48`
- `0x140013fb8`
- `0x140014010`
- `0x140014050`
- `0x140014384`
- `0x140014fb4`

## import_xrefs

- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140002b8d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140002b8d`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400029f5`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400029f5`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002c77`
- `ntoskrnl!KeReleaseSpinLock` at `0x140002c77`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002a17`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002a17`
- `NDIS!NdisReleaseRWLock` at `0x140002b04`
- `NDIS!NdisReleaseRWLock` at `0x140002bf3`
- `NDIS!NdisReleaseRWLock` at `0x140002b04`
- `NDIS!NdisReleaseRWLock` at `0x140002bf3`
- `NDIS!NdisAcquireRWLockWrite` at `0x140002aca`
- `NDIS!NdisAcquireRWLockWrite` at `0x140002bd4`
- `NDIS!NdisAcquireRWLockWrite` at `0x140002aca`
- `NDIS!NdisAcquireRWLockWrite` at `0x140002bd4`

## pseudocode

```c
_QWORD *__fastcall BwcSendNbls(unsigned int *a1, _QWORD *a2, __int64 a3, _QWORD *a4, _QWORD *a5)
{
  PNDIS_RW_LOCK_EX *v5; // r13
  _QWORD *v7; // rbx
  ULONG CurrentProcessorNumber; // r15d
  KSPIN_LOCK *v10; // rbx
  __int64 v11; // rdx
  __int64 v12; // r8
  unsigned int *v13; // rdi
  _QWORD *v14; // rax
  __int64 CurrentTime; // rax
  __int64 v16; // rbx
  __int64 v17; // rdx
  __int64 v18; // rdx
  char *v19; // rdi
  __int64 v20; // rbx
  int v21; // edx
  int v22; // r9d
  _QWORD *result; // rax
  int v24; // [rsp+20h] [rbp-A1h]
  unsigned int *v25; // [rsp+40h] [rbp-81h]
  __int64 v26; // [rsp+48h] [rbp-79h] BYREF
  __int64 v27; // [rsp+50h] [rbp-71h] BYREF
  __int64 v28; // [rsp+58h] [rbp-69h] BYREF
  _QWORD *v29; // [rsp+60h] [rbp-61h] BYREF
  __int64 v30; // [rsp+68h] [rbp-59h] BYREF
  _QWORD *v31; // [rsp+70h] [rbp-51h]
  __int64 v32; // [rsp+78h] [rbp-49h]
  __int64 *v33; // [rsp+80h] [rbp-41h] BYREF
  _QWORD *v34; // [rsp+88h] [rbp-39h] BYREF
  _OWORD v35[2]; // [rsp+90h] [rbp-31h] BYREF
  int v36; // [rsp+B0h] [rbp-11h]
  _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+B8h] [rbp-9h] BYREF
  __int64 v38; // [rsp+120h] [rbp+5Fh] BYREF
  __int64 v39; // [rsp+128h] [rbp+67h] BYREF
  struct _LOCK_STATE_EX LockState; // [rsp+130h] [rbp+6Fh] BYREF
  _QWORD *v41; // [rsp+138h] [rbp+77h]

  v41 = a4;
  v5 = (PNDIS_RW_LOCK_EX *)BwcVirtualLine;
  v36 = 0;
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  v39 = 0;
  v34 = &v29;
  v7 = a4;
  v38 = 0;
  v33 = &v28;
  memset(v35, 0, sizeof(v35));
  v26 = 0;
  v27 = 0;
  memset(&LockHandle, 0, sizeof(LockHandle));
  v29 = 0;
  v28 = 0;
  v30 = 0;
  CurrentProcessorNumber = KeGetCurrentProcessorNumberEx(0);
  if ( a1 )
  {
    v10 = (KSPIN_LOCK *)(a1 + 118);
    *((_BYTE *)a1 + 480) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)a1 + 59);
    if ( a2 )
    {
      v25 = 0;
      v13 = a1 + 10;
      do
      {
        v14 = a2;
        v39 = 0;
        v38 = 0;
        LOBYTE(v12) = 1;
        v31 = a2;
        LOBYTE(v11) = 1;
        a2 = (_QWORD *)*a2;
        *v14 = 0;
        CurrentTime = QosTimerGetCurrentTime(CurrentProcessorNumber, v11, v12);
        v16 = CurrentTime;
        v32 = CurrentTime;
        if ( a1 != v25 )
        {
          v25 = a1;
          if ( *a1 != CurrentProcessorNumber )
          {
            v17 = *((_QWORD *)a1 + 17);
            if ( (unsigned int *)v17 != a1 + 34 && *(_QWORD *)(v17 + 24) - CurrentTime <= 0 )
              BwcFlowDelay(a1, CurrentProcessorNumber);
          }
        }
        if ( (unsigned __int8)QosFlowNeedQueueFeedback(v13, v16, v35) )
        {
          NdisAcquireRWLockWrite(*v5, &LockState, 0);
          if ( (unsigned __int8)QosLineNeedSignal(v5 + 1, CurrentProcessorNumber) )
            QosLineSignalExternalEvent(v5 + 1, CurrentProcessorNumber);
          QosLineQueryQueueFeedback(v5 + 1, v18, v35);
          NdisReleaseRWLock(*v5, &LockState);
          QosTbcAdjustSendWindow(v13, v35);
        }
        if ( (unsigned __int8)QosFlowSendNetBufferLists(
                                (_DWORD)v13,
                                CurrentProcessorNumber,
                                (int)v5 + 8,
                                (_DWORD)v31,
                                v24,
                                (__int64)&v39,
                                (__int64)&v38) )
        {
          v19 = (char *)BwcTimerUnits + 192 * *a1;
          v20 = *(_QWORD *)(*((_QWORD *)a1 + 17) + 24LL);
          RtlAcquireWriteLockAtDpcLevel(v19, &LockHandle);
          BwcSetTimer(v19, v32, v20);
          BwcSetFlowTimer(v19, a1, v20);
          KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
          v13 = a1 + 10;
        }
        v11 = v38;
        if ( v38 )
          BwcNblAppendNblsMoveLast(&v33);
        if ( v39 )
        {
          if ( (unsigned __int8)QosLineNeedSignal(v5 + 1, CurrentProcessorNumber) )
          {
            NdisAcquireRWLockWrite(*v5, &LockState, 1u);
            QosLineSignalExternalEvent(v5 + 1, CurrentProcessorNumber);
            NdisReleaseRWLock(*v5, &LockState);
          }
          QosLineSendNetBufferLists((_DWORD)v5 + 8, v21, v39, v22, (__int64)&v26, (__int64)&v38);
          if ( !a1[116] )
          {
            BwcCompleteNbls(a1, v5, v26, &v27);
            BwcNblAppendNblsMoveLast(&v34);
          }
        }
      }
      while ( a2 );
      v10 = (KSPIN_LOCK *)(a1 + 118);
    }
    if ( v28 )
      BwcDropNbls(a1, v5, v28, &v30);
    KeReleaseSpinLock(v10, *((_BYTE *)a1 + 480));
    a2 = v29;
    v7 = v41;
  }
  result = a5;
  *a5 = v30;
  if ( a2 )
    *v7 = a2;
  return result;
}

```

## disassembly

```asm
0x140002974  mov     [rsp-8+arg_18], r9
0x140002979  mov     [rsp-8+LockState.OldIrql], r8b
0x14000297e  push    rbp
0x14000297f  push    rbx
0x140002980  push    rsi
0x140002981  push    rdi
0x140002982  push    r12
0x140002984  push    r13
0x140002986  push    r14
0x140002988  push    r15
0x14000298a  lea     rbp, [rsp-17h]
0x14000298f  sub     rsp, 0D8h
0x140002996  mov     r13, cs:BwcVirtualLine
0x14000299d  xor     eax, eax
0x14000299f  xor     edi, edi
0x1400029a1  mov     [rbp+4Fh+var_60], eax
0x1400029a4  xorps   xmm0, xmm0
0x1400029a7  mov     qword ptr [rbp+4Fh+LockHandle.OldIrql], rax
0x1400029ab  mov     word ptr [rbp+4Fh+LockState.OldIrql], ax
0x1400029af  mov     rsi, rcx
0x1400029b2  mov     [rbp+4Fh+LockState.Flags], al
0x1400029b5  xor     ecx, ecx; ProcNumber
0x1400029b7  lea     rax, [rbp+4Fh+var_B0]
0x1400029bb  mov     [rbp+4Fh+arg_8], rdi
0x1400029bf  mov     [rbp+4Fh+var_88], rax
0x1400029c3  mov     rbx, r9
0x1400029c6  lea     rax, [rbp+4Fh+var_B8]
0x1400029ca  mov     [rbp+4Fh+arg_0], rdi
0x1400029ce  mov     [rbp+4Fh+var_90], rax
0x1400029d2  mov     r14, rdx
0x1400029d5  movups  [rbp+4Fh+var_80], xmm0
0x1400029d9  mov     [rbp+4Fh+var_C8], rdi
0x1400029dd  movups  [rbp+4Fh+var_70], xmm0
0x1400029e1  mov     [rbp+4Fh+var_C0], rdi
0x1400029e5  movups  xmmword ptr [rbp+4Fh+LockHandle.LockQueue.Next], xmm0
0x1400029e9  mov     [rbp+4Fh+var_B0], rdi
0x1400029ed  mov     [rbp+4Fh+var_B8], rdi
0x1400029f1  mov     [rbp+4Fh+var_A8], rdi
0x1400029f5  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1400029fc  nop     dword ptr [rax+rax+00h]
0x140002a01  mov     r15d, eax
0x140002a04  test    rsi, rsi
0x140002a07  jz      loc_140002C8B
0x140002a0d  lea     rbx, [rsi+1D8h]
0x140002a14  mov     rcx, rbx; SpinLock
0x140002a17  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140002a1e  nop     dword ptr [rax+rax+00h]
0x140002a23  mov     [rsi+1E0h], al
0x140002a29  test    r14, r14
0x140002a2c  jz      loc_140002C56
0x140002a32  mov     [rsp+110h+var_D0], rdi
0x140002a37  lea     r12, [r13+8]
0x140002a3b  lea     rdi, [rsi+28h]
0x140002a3f  mov     rax, r14
0x140002a42  mov     [rbp+4Fh+arg_8], 0
0x140002a4a  mov     [rbp+4Fh+arg_0], 0
0x140002a52  mov     r8b, 1
0x140002a55  mov     [rbp+4Fh+var_A0], r14
0x140002a59  mov     dl, r8b
0x140002a5c  mov     r14, [r14]
0x140002a5f  mov     ecx, r15d
0x140002a62  mov     qword ptr [rax], 0
0x140002a69  call    QosTimerGetCurrentTime
0x140002a6e  mov     rbx, rax
0x140002a71  mov     [rbp+4Fh+var_98], rax
0x140002a75  cmp     rsi, [rsp+110h+var_D0]
0x140002a7a  jz      short loc_140002AAC
0x140002a7c  mov     [rsp+110h+var_D0], rsi
0x140002a81  cmp     [rsi], r15d
0x140002a84  jz      short loc_140002AAC
0x140002a86  lea     rcx, [rsi+88h]
0x140002a8d  mov     rdx, [rcx]
0x140002a90  cmp     rdx, rcx
0x140002a93  jz      short loc_140002AAC
0x140002a95  mov     rcx, [rdx+18h]
0x140002a99  sub     rcx, rax
0x140002a9c  test    rcx, rcx
0x140002a9f  jg      short loc_140002AAC
0x140002aa1  mov     edx, r15d
0x140002aa4  mov     rcx, rsi
0x140002aa7  call    BwcFlowDelay
0x140002aac  lea     r8, [rbp+4Fh+var_80]
0x140002ab0  mov     rdx, rbx
0x140002ab3  mov     rcx, rdi
0x140002ab6  call    QosFlowNeedQueueFeedback
0x140002abb  test    al, al
0x140002abd  jz      short loc_140002B1C
0x140002abf  mov     rcx, [r13+0]; Lock
0x140002ac3  lea     rdx, [rbp+4Fh+LockState]; LockState
0x140002ac7  xor     r8d, r8d; Flags
0x140002aca  call    cs:__imp_NdisAcquireRWLockWrite
0x140002ad1  nop     dword ptr [rax+rax+00h]
0x140002ad6  mov     edx, r15d
0x140002ad9  mov     rcx, r12
0x140002adc  call    QosLineNeedSignal
0x140002ae1  test    al, al
0x140002ae3  jz      short loc_140002AF0
0x140002ae5  mov     edx, r15d
0x140002ae8  mov     rcx, r12
0x140002aeb  call    QosLineSignalExternalEvent
0x140002af0  lea     r8, [rbp+4Fh+var_80]
0x140002af4  mov     rcx, r12
0x140002af7  call    QosLineQueryQueueFeedback
0x140002afc  mov     rcx, [r13+0]; Lock
0x140002b00  lea     rdx, [rbp+4Fh+LockState]; LockState
0x140002b04  call    cs:__imp_NdisReleaseRWLock
0x140002b0b  nop     dword ptr [rax+rax+00h]
0x140002b10  lea     rdx, [rbp+4Fh+var_80]
0x140002b14  mov     rcx, rdi
0x140002b17  call    QosTbcAdjustSendWindow
0x140002b1c  mov     r9, [rbp+4Fh+var_A0]
0x140002b20  lea     rax, [rbp+4Fh+arg_0]
0x140002b24  mov     [rsp+110h+var_E0], rax
0x140002b29  mov     r8, r12
0x140002b2c  lea     rax, [rbp+4Fh+arg_8]
0x140002b30  mov     edx, r15d
0x140002b33  mov     rcx, rdi
0x140002b36  mov     [rsp+110h+var_E8], rax
0x140002b3b  call    QosFlowSendNetBufferLists
0x140002b40  test    al, al
0x140002b42  jz      short loc_140002B9D
0x140002b44  mov     eax, [rsi]
0x140002b46  lea     rdx, [rbp+4Fh+LockHandle]
0x140002b4a  lea     rdi, [rax+rax*2]
0x140002b4e  mov     rax, [rsi+88h]
0x140002b55  shl     rdi, 6
0x140002b59  add     rdi, cs:BwcTimerUnits
0x140002b60  mov     rcx, rdi
0x140002b63  mov     rbx, [rax+18h]
0x140002b67  call    RtlAcquireWriteLockAtDpcLevel
0x140002b6c  mov     rdx, [rbp+4Fh+var_98]
0x140002b70  mov     r8, rbx
0x140002b73  mov     rcx, rdi
0x140002b76  call    BwcSetTimer
0x140002b7b  mov     r8, rbx
0x140002b7e  mov     rdx, rsi
0x140002b81  mov     rcx, rdi
0x140002b84  call    BwcSetFlowTimer
0x140002b89  lea     rcx, [rbp+4Fh+LockHandle]; LockHandle
0x140002b8d  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x140002b94  nop     dword ptr [rax+rax+00h]
0x140002b99  lea     rdi, [rsi+28h]
0x140002b9d  mov     rdx, [rbp+4Fh+arg_0]
0x140002ba1  test    rdx, rdx
0x140002ba4  jz      short loc_140002BAF
0x140002ba6  lea     rcx, [rbp+4Fh+var_90]
0x140002baa  call    BwcNblAppendNblsMoveLast
0x140002baf  cmp     [rbp+4Fh+arg_8], 0
0x140002bb4  jz      loc_140002C46
0x140002bba  mov     edx, r15d
0x140002bbd  mov     rcx, r12
0x140002bc0  call    QosLineNeedSignal
0x140002bc5  test    al, al
0x140002bc7  jz      short loc_140002BFF
0x140002bc9  mov     rcx, [r13+0]; Lock
0x140002bcd  lea     rdx, [rbp+4Fh+LockState]; LockState
0x140002bd1  mov     r8b, 1; Flags
0x140002bd4  call    cs:__imp_NdisAcquireRWLockWrite
0x140002bdb  nop     dword ptr [rax+rax+00h]
0x140002be0  mov     edx, r15d
0x140002be3  mov     rcx, r12
0x140002be6  call    QosLineSignalExternalEvent
0x140002beb  mov     rcx, [r13+0]; Lock
0x140002bef  lea     rdx, [rbp+4Fh+LockState]; LockState
0x140002bf3  call    cs:__imp_NdisReleaseRWLock
0x140002bfa  nop     dword ptr [rax+rax+00h]
0x140002bff  mov     r8, [rbp+4Fh+arg_8]
0x140002c03  lea     rax, [rbp+4Fh+arg_0]
0x140002c07  mov     [rsp+110h+var_E8], rax
0x140002c0c  mov     rcx, r12
0x140002c0f  lea     rax, [rbp+4Fh+var_C8]
0x140002c13  mov     [rsp+110h+var_F0], rax
0x140002c18  call    QosLineSendNetBufferLists
0x140002c1d  cmp     dword ptr [rsi+1D0h], 0
0x140002c24  jnz     short loc_140002C46
0x140002c26  mov     r8, [rbp+4Fh+var_C8]
0x140002c2a  lea     r9, [rbp+4Fh+var_C0]
0x140002c2e  mov     rdx, r13
0x140002c31  mov     rcx, rsi
0x140002c34  call    BwcCompleteNbls
0x140002c39  mov     rdx, [rbp+4Fh+var_C0]
0x140002c3d  lea     rcx, [rbp+4Fh+var_88]
0x140002c41  call    BwcNblAppendNblsMoveLast
0x140002c46  test    r14, r14
0x140002c49  jnz     loc_140002A3F
0x140002c4f  lea     rbx, [rsi+1D8h]
0x140002c56  mov     r8, [rbp+4Fh+var_B8]
0x140002c5a  test    r8, r8
0x140002c5d  jz      short loc_140002C6E
0x140002c5f  lea     r9, [rbp+4Fh+var_A8]
0x140002c63  mov     rdx, r13
0x140002c66  mov     rcx, rsi
0x140002c69  call    BwcDropNbls
0x140002c6e  mov     dl, [rsi+1E0h]; NewIrql
0x140002c74  mov     rcx, rbx; SpinLock
0x140002c77  call    cs:__imp_KeReleaseSpinLock
0x140002c7e  nop     dword ptr [rax+rax+00h]
0x140002c83  mov     r14, [rbp+4Fh+var_B0]
0x140002c87  mov     rbx, [rbp+4Fh+arg_18]
0x140002c8b  mov     rax, [rbp+4Fh+arg_20]
0x140002c8f  mov     rcx, [rbp+4Fh+var_A8]
0x140002c93  mov     [rax], rcx
0x140002c96  test    r14, r14
0x140002c99  jz      short loc_140002C9E
0x140002c9b  mov     [rbx], r14
0x140002c9e  add     rsp, 0D8h
0x140002ca5  pop     r15
0x140002ca7  pop     r14
0x140002ca9  pop     r13
0x140002cab  pop     r12
0x140002cad  pop     rdi
0x140002cae  pop     rsi
0x140002caf  pop     rbx
0x140002cb0  pop     rbp
0x140002cb1  retn
```
