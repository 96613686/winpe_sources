# BwcFlushDelay

- ea: `0x140012570`
- end: `0x1400127e7`
- name: `BwcFlushDelay`
- size: `631`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x140012b0c`

## callees

- `0x140009368`
- `0x140011da8`
- `0x1400123bc`
- `0x1400123e4`
- `0x140012570`
- `0x140012ddc`
- `0x140013f48`
- `0x140013fb8`
- `0x140014010`
- `0x140014050`
- `0x140014384`
- `0x1400143d0`
- `0x140014fb4`
- `0x140016230`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x1400126fe`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400126fe`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400125f9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400125f9`
- `NDIS!NdisReleaseRWLock` at `0x1400126a1`
- `NDIS!NdisReleaseRWLock` at `0x140012765`
- `NDIS!NdisReleaseRWLock` at `0x1400126a1`
- `NDIS!NdisReleaseRWLock` at `0x140012765`
- `NDIS!NdisAcquireRWLockWrite` at `0x140012664`
- `NDIS!NdisAcquireRWLockWrite` at `0x140012747`
- `NDIS!NdisAcquireRWLockWrite` at `0x140012664`
- `NDIS!NdisAcquireRWLockWrite` at `0x140012747`

## pseudocode

```c
__int64 __fastcall BwcFlushDelay(unsigned int a1, __int64 a2, __int64 a3)
{
  unsigned __int64 v4; // rcx
  PNDIS_RW_LOCK_EX *v5; // rbx
  __int64 v6; // r12
  char *v7; // rax
  __int64 v8; // rdi
  __int64 result; // rax
  __int64 v10; // rsi
  KIRQL v11; // al
  __int64 v12; // r14
  bool v13; // zf
  __int64 v14; // rdx
  int v15; // edx
  int v16; // r9d
  __int64 v17; // [rsp+30h] [rbp-39h] BYREF
  __int64 v18; // [rsp+38h] [rbp-31h] BYREF
  __int64 v19; // [rsp+40h] [rbp-29h]
  __int64 v20; // [rsp+48h] [rbp-21h]
  _OWORD v21[2]; // [rsp+50h] [rbp-19h] BYREF
  int v22; // [rsp+70h] [rbp+7h]
  struct _LOCK_STATE_EX LockState; // [rsp+D0h] [rbp+67h] BYREF
  __int64 v24; // [rsp+D8h] [rbp+6Fh] BYREF
  __int64 v25; // [rsp+E0h] [rbp+77h] BYREF
  __int64 v26; // [rsp+E8h] [rbp+7Fh] BYREF

  v4 = (unsigned __int64)a1 << 6;
  v5 = 0;
  v22 = 0;
  v6 = 0;
  *(_WORD *)&LockState.OldIrql = 0;
  LOBYTE(a3) = 1;
  LockState.Flags = 0;
  v18 = 0;
  v7 = (char *)BwcDelayQueue;
  memset(v21, 0, sizeof(v21));
  v17 = 0;
  v8 = *(_QWORD *)((char *)BwcDelayQueue + v4);
  *(_QWORD *)((char *)BwcDelayQueue + v4) = 0;
  *(_QWORD *)&v7[v4 + 8] = 0;
  result = QosTimerGetCurrentTime(a1, 0, a3);
  v19 = result;
  if ( v8 )
  {
    do
    {
      v20 = *(_QWORD *)v8;
      v10 = v8 - 32;
      v11 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v8 + 440));
      *(_DWORD *)(v8 + 460) &= ~4u;
      v12 = 0;
      v13 = (*(_BYTE *)(v8 + 456) & 1) == 0;
      *(_BYTE *)(v8 + 448) = v11;
      v25 = 0;
      v26 = 0;
      LODWORD(v24) = 0;
      if ( v13 )
      {
        if ( !*(_DWORD *)(v10 + 464) )
          v5 = (PNDIS_RW_LOCK_EX *)BwcVirtualLine;
        if ( (unsigned __int8)QosFlowNeedQueueFeedback(v10 + 40, v19, v21) && v5 )
        {
          NdisAcquireRWLockWrite(*v5, &LockState, 0);
          if ( (unsigned __int8)QosLineNeedSignal(v5 + 1, a1) )
            QosLineSignalExternalEvent(v5 + 1, a1);
          QosLineQueryQueueFeedback(v5 + 1, v14, v21);
          NdisReleaseRWLock(*v5, &LockState);
          QosTbcAdjustSendWindow(v10 + 40, v21);
        }
        QosFlowProcessQueuedNetBufferLists(v10 + 40, a1, (unsigned int)&v25, (unsigned int)&v24, (__int64)&v26);
        if ( v26 )
        {
          BwcDropNbls(v10, v5, v26, &v17);
          v6 = v17;
        }
        v12 = v25;
      }
      KeReleaseSpinLock((PKSPIN_LOCK)(v8 + 440), *(_BYTE *)(v10 + 480));
      if ( v6 )
        ((void (__fastcall *)(__int64, __int64))DropQueuedNonConformantNbls)(v10, v6);
      if ( v12 )
      {
        if ( (unsigned __int8)QosLineNeedSignal(v5 + 1, a1) )
        {
          NdisAcquireRWLockWrite(*v5, &LockState, 1u);
          QosLineSignalExternalEvent(v5 + 1, a1);
          NdisReleaseRWLock(*v5, &LockState);
        }
        QosLineSendNetBufferLists((_DWORD)v5 + 8, v15, v12, v16, (__int64)&v18, (__int64)&v26);
        v24 = 0;
        BwcCompleteNbls(v10, v5, v18, &v24);
        if ( v24 )
          BwcSendProcessedNbls(v10, v24);
      }
      BwcDereferenceFlow(v10);
      result = v20;
      v8 = v20;
    }
    while ( v20 );
  }
  return result;
}

```

## disassembly

```asm
0x140012570  push    rbp
0x140012572  push    rbx
0x140012573  push    rsi
0x140012574  push    rdi
0x140012575  push    r12
0x140012577  push    r13
0x140012579  push    r14
0x14001257b  push    r15
0x14001257d  lea     rbp, [rsp-1Fh]
0x140012582  sub     rsp, 88h
0x140012589  xor     eax, eax
0x14001258b  mov     r15d, ecx
0x14001258e  mov     ecx, ecx
0x140012590  xorps   xmm0, xmm0
0x140012593  shl     rcx, 6
0x140012597  xor     ebx, ebx
0x140012599  mov     [rbp+57h+var_50], eax
0x14001259c  xor     r12d, r12d
0x14001259f  mov     word ptr [rbp+57h+LockState.OldIrql], ax
0x1400125a3  mov     r8b, 1
0x1400125a6  mov     [rbp+57h+LockState.Flags], al
0x1400125a9  xor     edx, edx
0x1400125ab  mov     [rbp+57h+var_88], rax
0x1400125af  mov     rax, cs:BwcDelayQueue
0x1400125b6  movups  [rbp+57h+var_70], xmm0
0x1400125ba  mov     [rbp+57h+var_90], r12
0x1400125be  movups  [rbp+57h+var_60], xmm0
0x1400125c2  mov     rdi, [rcx+rax]
0x1400125c6  mov     [rcx+rax], rbx
0x1400125ca  mov     [rcx+rax+8], rbx
0x1400125cf  mov     ecx, r15d
0x1400125d2  call    QosTimerGetCurrentTime
0x1400125d7  mov     [rbp+57h+var_80], rax
0x1400125db  test    rdi, rdi
0x1400125de  jz      loc_1400127D2
0x1400125e4  mov     rcx, [rdi]
0x1400125e7  lea     r13, [rdi+1B8h]
0x1400125ee  mov     [rbp+57h+var_78], rcx
0x1400125f2  lea     rsi, [rdi-20h]
0x1400125f6  mov     rcx, r13; SpinLock
0x1400125f9  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140012600  nop     dword ptr [rax+rax+00h]
0x140012605  and     dword ptr [rdi+1CCh], 0FFFFFFFBh
0x14001260c  xor     r14d, r14d
0x14001260f  test    byte ptr [rdi+1C8h], 1
0x140012616  mov     [rdi+1C0h], al
0x14001261c  mov     [rbp+57h+arg_10], r14
0x140012620  mov     [rbp+57h+arg_18], r14
0x140012624  mov     dword ptr [rbp+57h+arg_8], r14d
0x140012628  jnz     loc_1400126F5
0x14001262e  cmp     [rsi+1D0h], r14d
0x140012635  lea     r8, [rbp+57h+var_70]
0x140012639  mov     rdx, [rbp+57h+var_80]
0x14001263d  lea     r14, [rsi+28h]
0x140012641  cmovz   rbx, cs:BwcVirtualLine
0x140012649  mov     rcx, r14
0x14001264c  call    QosFlowNeedQueueFeedback
0x140012651  test    al, al
0x140012653  jz      short loc_1400126B9
0x140012655  test    rbx, rbx
0x140012658  jz      short loc_1400126B9
0x14001265a  mov     rcx, [rbx]; Lock
0x14001265d  lea     rdx, [rbp+57h+LockState]; LockState
0x140012661  xor     r8d, r8d; Flags
0x140012664  call    cs:__imp_NdisAcquireRWLockWrite
0x14001266b  nop     dword ptr [rax+rax+00h]
0x140012670  lea     rdi, [rbx+8]
0x140012674  mov     edx, r15d
0x140012677  mov     rcx, rdi
0x14001267a  call    QosLineNeedSignal
0x14001267f  test    al, al
0x140012681  jz      short loc_14001268E
0x140012683  mov     edx, r15d
0x140012686  mov     rcx, rdi
0x140012689  call    QosLineSignalExternalEvent
0x14001268e  lea     r8, [rbp+57h+var_70]
0x140012692  mov     rcx, rdi
0x140012695  call    QosLineQueryQueueFeedback
0x14001269a  mov     rcx, [rbx]; Lock
0x14001269d  lea     rdx, [rbp+57h+LockState]; LockState
0x1400126a1  call    cs:__imp_NdisReleaseRWLock
0x1400126a8  nop     dword ptr [rax+rax+00h]
0x1400126ad  lea     rdx, [rbp+57h+var_70]
0x1400126b1  mov     rcx, r14
0x1400126b4  call    QosTbcAdjustSendWindow
0x1400126b9  lea     rax, [rbp+57h+arg_18]
0x1400126bd  mov     edx, r15d
0x1400126c0  lea     r9, [rbp+57h+arg_8]
0x1400126c4  mov     [rsp+0C0h+var_A0], rax
0x1400126c9  lea     r8, [rbp+57h+arg_10]
0x1400126cd  mov     rcx, r14
0x1400126d0  call    QosFlowProcessQueuedNetBufferLists
0x1400126d5  mov     r8, [rbp+57h+arg_18]
0x1400126d9  test    r8, r8
0x1400126dc  jz      short loc_1400126F1
0x1400126de  lea     r9, [rbp+57h+var_90]
0x1400126e2  mov     rdx, rbx
0x1400126e5  mov     rcx, rsi
0x1400126e8  call    BwcDropNbls
0x1400126ed  mov     r12, [rbp+57h+var_90]
0x1400126f1  mov     r14, [rbp+57h+arg_10]
0x1400126f5  mov     dl, [rsi+1E0h]; NewIrql
0x1400126fb  mov     rcx, r13; SpinLock
0x1400126fe  call    cs:__imp_KeReleaseSpinLock
0x140012705  nop     dword ptr [rax+rax+00h]
0x14001270a  test    r12, r12
0x14001270d  jz      short loc_140012721
0x14001270f  mov     rax, cs:DropQueuedNonConformantNbls
0x140012716  mov     rdx, r12
0x140012719  mov     rcx, rsi
0x14001271c  call    _guard_dispatch_icall
0x140012721  test    r14, r14
0x140012724  jz      loc_1400127BA
0x14001272a  lea     rdi, [rbx+8]
0x14001272e  mov     edx, r15d
0x140012731  mov     rcx, rdi
0x140012734  call    QosLineNeedSignal
0x140012739  test    al, al
0x14001273b  jz      short loc_140012771
0x14001273d  mov     rcx, [rbx]; Lock
0x140012740  lea     rdx, [rbp+57h+LockState]; LockState
0x140012744  mov     r8b, 1; Flags
0x140012747  call    cs:__imp_NdisAcquireRWLockWrite
0x14001274e  nop     dword ptr [rax+rax+00h]
0x140012753  mov     edx, r15d
0x140012756  mov     rcx, rdi
0x140012759  call    QosLineSignalExternalEvent
0x14001275e  mov     rcx, [rbx]; Lock
0x140012761  lea     rdx, [rbp+57h+LockState]; LockState
0x140012765  call    cs:__imp_NdisReleaseRWLock
0x14001276c  nop     dword ptr [rax+rax+00h]
0x140012771  lea     rax, [rbp+57h+arg_18]
0x140012775  mov     r8, r14
0x140012778  mov     [rsp+0C0h+var_98], rax
0x14001277d  mov     rcx, rdi
0x140012780  lea     rax, [rbp+57h+var_88]
0x140012784  mov     [rsp+0C0h+var_A0], rax
0x140012789  call    QosLineSendNetBufferLists
0x14001278e  mov     r8, [rbp+57h+var_88]
0x140012792  lea     r9, [rbp+57h+arg_8]
0x140012796  mov     rdx, rbx
0x140012799  mov     [rbp+57h+arg_8], 0
0x1400127a1  mov     rcx, rsi
0x1400127a4  call    BwcCompleteNbls
0x1400127a9  mov     rdx, [rbp+57h+arg_8]
0x1400127ad  test    rdx, rdx
0x1400127b0  jz      short loc_1400127BA
0x1400127b2  mov     rcx, rsi
0x1400127b5  call    BwcSendProcessedNbls
0x1400127ba  mov     rcx, rsi
0x1400127bd  call    BwcDereferenceFlow
0x1400127c2  mov     rax, [rbp+57h+var_78]
0x1400127c6  mov     rdi, rax
0x1400127c9  test    rax, rax
0x1400127cc  jnz     loc_1400125E4
0x1400127d2  add     rsp, 88h
0x1400127d9  pop     r15
0x1400127db  pop     r14
0x1400127dd  pop     r13
0x1400127df  pop     r12
0x1400127e1  pop     rdi
0x1400127e2  pop     rsi
0x1400127e3  pop     rbx
0x1400127e4  pop     rbp
0x1400127e5  retn
```
