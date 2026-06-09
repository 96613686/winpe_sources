# SmbCeSendCompleteInd

- ea: `0x140006150`
- end: `0x140006658`
- name: `SmbCeSendCompleteInd`
- size: `1288`
- prototype: ``
- caller_count: `3`
- callee_count: `19`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140006130`
- `0x14008d270`
- `0x14008d3d0`

## callees

- `0x1400060bc`
- `0x140006150`
- `0x140006680`
- `0x140006bb0`
- `0x1400093a0`
- `0x140009fc0`
- `0x14000c030`
- `0x14000d910`
- `0x14000df60`
- `0x14000fbe0`
- `0x140014370`
- `0x1400147b0`
- `0x1400148f0`
- `0x1400149d0`
- `0x14001b2a0`
- `0x14001c050`
- `0x140028960`
- `0x140037fa4`
- `0x140059ea0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006277`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400063f9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006277`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400063f9`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000649a`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000649a`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005b7e3`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005b7e3`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005b80b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005b80b`
- `ntoskrnl!IofCompleteRequest` at `0x140006647`
- `ntoskrnl!IofCompleteRequest` at `0x140006647`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006392`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006392`
- `ntoskrnl!KeBugCheckEx` at `0x140006635`
- `ntoskrnl!KeBugCheckEx` at `0x140006635`
- `rdbss!RxAttemptTurboIoCompletion` at `0x140006331`
- `rdbss!RxAttemptTurboIoCompletion` at `0x140006331`
- `rdbss!RxPostToWorkerThread` at `0x140006587`
- `rdbss!RxPostToWorkerThread` at `0x140006587`

## pseudocode

```c
__int64 __fastcall SmbCeSendCompleteInd(unsigned __int64 Flink_low, __int64 a2, __int64 a3, unsigned int a4)
{
  __int64 v4; // r15
  char v5; // si
  IRP *v6; // r12
  __int64 v8; // rbx
  PDEVICE_OBJECT v9; // r9
  __int64 v10; // rbp
  __int64 v11; // rdi
  __int64 v12; // r14
  __int64 v13; // rdi
  signed __int32 v14; // r8d
  __int64 v15; // r14
  ULONG_PTR pContext; // rdi
  __int64 v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // rcx
  __int64 v20; // rbx
  __int64 v22; // rdx
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // rbx
  struct _RDBSS_DEVICE_OBJECT *v26; // rsi
  __int64 v27; // rdx
  __int64 v28; // rax
  __int64 (__fastcall *v29)(ULONG_PTR); // rax
  int v30; // ecx
  __int64 v31; // rax
  int v32; // eax
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+30h] [rbp-58h] BYREF
  PDEVICE_OBJECT v34; // [rsp+90h] [rbp+8h]
  unsigned __int8 v36; // [rsp+A8h] [rbp+20h]

  v34 = (PDEVICE_OBJECT)Flink_low;
  v4 = a4;
  v5 = 0;
  v6 = 0;
  v8 = a2;
  v9 = (PDEVICE_OBJECT)Flink_low;
  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( (int)v4 < 0 )
  {
    Flink_low = (unsigned __int64)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_qqD(
        WPP_GLOBAL_Control->AttachedDevice,
        26,
        &WPP_1ffd7df1a0ca364e8ae776b5c429ef78_Traceguids,
        a2,
        *(_QWORD *)(a2 + 56),
        v4);
      v9 = v34;
    }
  }
  if ( (*(_DWORD *)(v8 + 4) & 0x40) != 0 )
  {
    v36 = 0;
    v10 = *(_QWORD *)(*(_QWORD *)(v8 + 56) + 56LL);
    SmbCeAcquireCompoundingKeyLock(v10);
    SmbCseUnchainCompoundedBufferContextsLite(v10);
    SmbCeReleaseCompoundingKeyLock(v24);
    v9 = v34;
  }
  else
  {
    v10 = 0;
    v36 = 1;
  }
  if ( *(_QWORD *)(v8 + 840) )
  {
    Flink_low = LODWORD(v9[1].DeviceQueue.DeviceListHead.Blink[5].Flink);
    v9->DeviceLock.Header.WaitListHead.Blink = (struct _LIST_ENTRY *)(((MEMORY[0xFFFFF78000000008]
                                                                      - *(_QWORD *)(v8 + 840))
                                                                     / 0xAuLL
                                                                     + (unsigned __int64)v9->DeviceLock.Header.WaitListHead.Blink
                                                                     * Flink_low)
                                                                    / (unsigned int)(Flink_low + 1));
  }
  v11 = v8;
  while ( 1 )
  {
    v12 = *(_QWORD *)(v11 + 56);
    if ( (Microsoft_Windows_SMBClientEnableBits & 4) != 0 )
      McTemplateK0qp_EtwWriteTransfer(
        Flink_low,
        &SmbSendCompletion,
        v12 + 312,
        (unsigned int)v4,
        *(_QWORD *)(*(_QWORD *)(v12 + 96) + 392LL));
    (*(void (__fastcall **)(__int64, __int64, __int64, _QWORD))(*(_QWORD *)(v12 + 232) + 24LL))(
      v12,
      v11,
      a3,
      (unsigned int)v4);
    if ( !v10 )
      break;
    v22 = *(_QWORD *)(v11 + 64);
    Flink_low = v10 + 48;
    v11 = 0;
    if ( v22 != v10 + 48 )
      v11 = v22 - 64;
    if ( !v11 )
    {
      _InterlockedIncrement((volatile signed __int32 *)(v10 + 4));
      *(_BYTE *)(v10 + 16) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v10 + 8));
      goto LABEL_13;
    }
  }
  v13 = *(_QWORD *)(v8 + 56);
  v14 = _InterlockedIncrement((volatile signed __int32 *)(v13 + 4));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qDD(
      WPP_GLOBAL_Control->AttachedDevice,
      33,
      &WPP_d39beb3e593835eae73483c3886eb046_Traceguids,
      v13,
      v14 - 1,
      v14);
  }
  *(_BYTE *)(v13 + 32) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v13 + 24));
LABEL_13:
  v15 = v8;
  do
  {
    pContext = *(_QWORD *)(v15 + 56);
    if ( (int)v4 < 0 )
    {
      v32 = SmbCseInvalidateMemoryRegistrationAsync(v15);
      if ( v32 != -1073741816 && v32 != 259 )
      {
        *(_BYTE *)(v8 + 87) = 0;
        *(_BYTE *)(v15 + 86) = 0;
LABEL_64:
        if ( !*(_DWORD *)(v15 + 48) )
          SmbCseUpdateBufferContextStatus(v15, v4 | 0x12E00000000LL);
        *(_BYTE *)(v15 + 85) = 0;
        KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)&v34[1].DeviceQueue.DeviceListHead.Blink[16], &LockHandle);
        SmbCseDissociateMidFromBufferContextLite(v34[1].DeviceQueue.DeviceListHead.Blink);
        KeReleaseInStackQueuedSpinLock(&LockHandle);
        goto LABEL_16;
      }
    }
    *(_BYTE *)(v15 + 86) = 0;
    if ( (int)v4 < 0 )
      goto LABEL_64;
LABEL_16:
    if ( v10 )
    {
      v23 = *(_QWORD *)(v15 + 64);
      v15 = 0;
      if ( v23 != v10 + 48 )
        v15 = v23 - 64;
    }
    else
    {
      v15 = 0;
    }
    if ( (unsigned __int8)SmbCepCheckExchangeForDeferredAbortOrIfFinalizable(pContext) )
    {
      v6 = 0;
      if ( (*(_DWORD *)(pContext + 68) & 0x100000) == 0 )
        goto LABEL_31;
      if ( !*(_QWORD *)(pContext + 56) && !*(_DWORD *)(pContext + 16) )
      {
        v17 = *(_QWORD *)(pContext + 160);
        v18 = v17 - 8;
        if ( v17 == pContext + 160 )
          v18 = 0;
        while ( v18 )
        {
          if ( *(_DWORD *)(v18 + 48) )
            goto LABEL_31;
          v19 = *(_QWORD *)(v18 + 8);
          v18 = 0;
          if ( v19 != pContext + 160 )
            v18 = v19 - 8;
        }
        v6 = (IRP *)RxAttemptTurboIoCompletion(
                      *(_QWORD *)(pContext + 48),
                      SmbCepPrepareExchangeForTurboCompletionLite,
                      pContext);
      }
      if ( !v6 )
      {
LABEL_31:
        if ( (unsigned int)SmbCepCompleteExchangeLiteEx((char *)pContext, (char *)v36) == -1073741802 )
          v5 = 1;
        v8 = a2;
      }
    }
  }
  while ( v15 );
  if ( v10 )
  {
    SmbCeReleaseCompoundingKeyLock(v10);
  }
  else
  {
    v20 = *(_QWORD *)(v8 + 56);
    KeReleaseSpinLock((PKSPIN_LOCK)(v20 + 24), *(_BYTE *)(v20 + 32));
    SmbCeDereferenceExchange((PVOID)v20);
  }
  if ( v5 )
  {
    v25 = *(_QWORD *)(pContext + 72);
    v26 = *(struct _RDBSS_DEVICE_OBJECT **)(v25 + 24);
    if ( KeGetCurrentIrql() >= 2u )
    {
      v30 = 0;
      if ( (*(_DWORD *)(pContext + 68) & 0x40000) == 0 )
        goto LABEL_57;
    }
    if ( (v28 = *(_QWORD *)(v25 + 56)) != 0
      && (v29 = *(__int64 (__fastcall **)(ULONG_PTR))(v28 + 912)) != 0
      && (v30 = v29(pContext), v30 == -1069481981)
      || (v31 = *(_QWORD *)(pContext + 232),
          *(_QWORD *)(pContext + 208) = 0,
          *(_DWORD *)(pContext + 40) = 8,
          v30 = (*(__int64 (__fastcall **)(ULONG_PTR))(v31 + 32))(pContext),
          v30 == -1069481981) )
    {
LABEL_57:
      if ( (*(_DWORD *)(pContext + 68) & 1) != 0 )
        KeBugCheckEx(0x27u, 0x43584D5Fu, pContext, v30, 0);
      LOBYTE(v27) = 20;
      RDR_PERF_ENTER(pContext + 512, v27);
      SmbCeIncrementTeardownOpCounter(v26, pContext, 7);
      RxPostToWorkerThread(
        v26,
        NormalWorkQueue,
        (PRX_WORK_QUEUE_ITEM)(pContext + 240),
        SmbCepFinalizeExchangeWorker,
        (PVOID)pContext);
    }
    else
    {
      RDR_PERF_EXIT(pContext + 512);
      RDR_PERF_OUTPUT_ETW(pContext + 512);
      RDR_PERF_FREE(pContext + 512);
      SmbCeDereferenceExchange((PVOID)pContext);
    }
  }
  if ( v6 )
    IofCompleteRequest(v6, 1);
  return 0;
}

```

## disassembly

```asm
0x140006150  mov     [rsp+arg_10], rbx
0x140006155  mov     [rsp+arg_8], rdx
0x14000615a  mov     [rsp+arg_0], rcx
0x14000615f  push    rbp
0x140006160  push    rsi
0x140006161  push    rdi
0x140006162  push    r12
0x140006164  push    r13
0x140006166  push    r14
0x140006168  push    r15
0x14000616a  sub     rsp, 50h
0x14000616e  xor     eax, eax
0x140006170  mov     r15d, r9d
0x140006173  xor     sil, sil
0x140006176  mov     qword ptr [rsp+88h+LockHandle.OldIrql], rax
0x14000617b  xor     r12d, r12d
0x14000617e  lea     rax, WPP_GLOBAL_Control
0x140006185  xorps   xmm0, xmm0
0x140006188  mov     r13, r8
0x14000618b  mov     rbx, rdx
0x14000618e  mov     r9, rcx
0x140006191  movups  xmmword ptr [rsp+88h+LockHandle.LockQueue.Next], xmm0
0x140006196  test    r15d, r15d
0x140006199  js      loc_14005B75C
0x14000619f  mov     eax, [rbx+4]
0x1400061a2  test    al, 40h
0x1400061a4  jnz     loc_140006460
0x1400061aa  xor     ebp, ebp
0x1400061ac  mov     [rsp+88h+arg_18], 1
0x1400061b4  cmp     [rbx+348h], r12
0x1400061bb  jz      short loc_140006209
0x1400061bd  mov     rcx, 0FFFFF78000000008h
0x1400061c7  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1400061d1  mov     rcx, [rcx]
0x1400061d4  sub     rcx, [rbx+348h]
0x1400061db  mul     rcx
0x1400061de  mov     rax, [r9+200h]
0x1400061e5  shr     rdx, 3
0x1400061e9  mov     ecx, [rax+50h]
0x1400061ec  mov     eax, ecx
0x1400061ee  imul    rax, [r9+128h]
0x1400061f6  lea     r8d, [rcx+1]
0x1400061fa  add     rax, rdx
0x1400061fd  xor     edx, edx
0x1400061ff  div     r8
0x140006202  mov     [r9+128h], rax
0x140006209  mov     rdi, rbx
0x14000620c  test    cs:Microsoft_Windows_SMBClientEnableBits, 4
0x140006213  mov     r14, [rdi+38h]
0x140006217  jnz     loc_14000640D
0x14000621d  mov     rax, [r14+0E8h]
0x140006224  mov     r9d, r15d
0x140006227  mov     r8, r13
0x14000622a  mov     rdx, rdi
0x14000622d  mov     rcx, r14
0x140006230  mov     rax, [rax+18h]
0x140006234  call    _guard_dispatch_icall
0x140006239  test    rbp, rbp
0x14000623c  jnz     loc_1400063D3
0x140006242  mov     rdi, [rbx+38h]
0x140006246  mov     r8d, 1
0x14000624c  lock xadd [rdi+4], r8d
0x140006252  inc     r8d
0x140006255  mov     rcx, cs:WPP_GLOBAL_Control
0x14000625c  lea     rax, WPP_GLOBAL_Control
0x140006263  cmp     rcx, rax
0x140006266  jz      short loc_140006273
0x140006268  mov     eax, [rcx+2Ch]
0x14000626b  test    al, 10h
0x14000626d  jnz     loc_140006598
0x140006273  lea     rcx, [rdi+18h]; SpinLock
0x140006277  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000627e  nop     dword ptr [rax+rax+00h]
0x140006283  mov     [rdi+20h], al
0x140006286  movzx   r13d, [rsp+88h+arg_18]
0x14000628f  mov     r14, rbx
0x140006292  mov     rax, 12E00000000h
0x14000629c  mov     rdi, [r14+38h]
0x1400062a0  test    r15d, r15d
0x1400062a3  js      loc_1400065CC
0x1400062a9  mov     byte ptr [r14+56h], 0
0x1400062ae  test    r15d, r15d
0x1400062b1  js      loc_1400065FD
0x1400062b7  test    rbp, rbp
0x1400062ba  jnz     loc_140006438
0x1400062c0  xor     r14d, r14d
0x1400062c3  mov     rcx, rdi
0x1400062c6  call    SmbCepCheckExchangeForDeferredAbortOrIfFinalizable
0x1400062cb  test    al, al
0x1400062cd  jz      loc_14000636A
0x1400062d3  mov     eax, [rdi+44h]
0x1400062d6  xor     r12d, r12d
0x1400062d9  mov     r9, [rdi+30h]
0x1400062dd  bt      eax, 14h
0x1400062e1  jnb     short loc_140006345
0x1400062e3  cmp     [rdi+38h], r12
0x1400062e7  jnz     short loc_140006340
0x1400062e9  cmp     [rdi+10h], r12d
0x1400062ed  jnz     short loc_140006340
0x1400062ef  lea     r8, [rdi+0A0h]
0x1400062f6  xor     eax, eax
0x1400062f8  mov     rcx, [r8]
0x1400062fb  cmp     rcx, r8
0x1400062fe  lea     rdx, [rcx-8]
0x140006302  cmovz   rdx, rax
0x140006306  test    rdx, rdx
0x140006309  jz      short loc_140006324
0x14000630b  cmp     [rdx+30h], r12d
0x14000630f  jnz     short loc_140006345
0x140006311  mov     rcx, [rdx+8]
0x140006315  xor     edx, edx
0x140006317  cmp     rcx, r8
0x14000631a  lea     rax, [rcx-8]
0x14000631e  cmovnz  rdx, rax
0x140006322  jmp     short loc_140006306
0x140006324  mov     r8, rdi
0x140006327  lea     rdx, SmbCepPrepareExchangeForTurboCompletionLite
0x14000632e  mov     rcx, r9
0x140006331  call    cs:__imp_RxAttemptTurboIoCompletion
0x140006338  nop     dword ptr [rax+rax+00h]
0x14000633d  mov     r12, rax
0x140006340  test    r12, r12
0x140006343  jnz     short loc_14000636A
0x140006345  movzx   edx, r13b
0x140006349  mov     rcx, rdi; pContext
0x14000634c  call    SmbCepCompleteExchangeLiteEx
0x140006351  mov     ebx, 1
0x140006356  movzx   esi, sil
0x14000635a  cmp     eax, 0C0000016h
0x14000635f  cmovz   esi, ebx
0x140006362  mov     rbx, [rsp+88h+arg_8]
0x14000636a  mov     rax, 12E00000000h
0x140006374  test    r14, r14
0x140006377  jnz     loc_14000629C
0x14000637d  test    rbp, rbp
0x140006380  jnz     loc_140006453
0x140006386  mov     rbx, [rbx+38h]
0x14000638a  movzx   edx, byte ptr [rbx+20h]; NewIrql
0x14000638e  lea     rcx, [rbx+18h]; SpinLock
0x140006392  call    cs:__imp_KeReleaseSpinLock
0x140006399  nop     dword ptr [rax+rax+00h]
0x14000639e  mov     rcx, rbx; pContext
0x1400063a1  call    SmbCeDereferenceExchange
0x1400063a6  test    sil, sil
0x1400063a9  jnz     loc_140006492
0x1400063af  test    r12, r12
0x1400063b2  jnz     loc_140006642
0x1400063b8  mov     rbx, [rsp+88h+arg_10]
0x1400063c0  xor     eax, eax
0x1400063c2  add     rsp, 50h
0x1400063c6  pop     r15
0x1400063c8  pop     r14
0x1400063ca  pop     r13
0x1400063cc  pop     r12
0x1400063ce  pop     rdi
0x1400063cf  pop     rsi
0x1400063d0  pop     rbp
0x1400063d1  retn
0x1400063d3  mov     rdx, [rdi+40h]
0x1400063d7  lea     rcx, [rbp+30h]
0x1400063db  xor     edi, edi
0x1400063dd  cmp     rdx, rcx
0x1400063e0  lea     rax, [rdx-40h]
0x1400063e4  cmovnz  rdi, rax
0x1400063e8  test    rdi, rdi
0x1400063eb  jnz     loc_14000620C
0x1400063f1  lock inc dword ptr [rbp+4]
0x1400063f5  lea     rcx, [rbp+8]; SpinLock
0x1400063f9  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140006400  nop     dword ptr [rax+rax+00h]
0x140006405  mov     [rbp+10h], al
0x140006408  jmp     loc_140006286
0x14000640d  mov     rax, [r14+60h]
0x140006411  lea     r8, [r14+138h]
0x140006418  mov     r9d, r15d
0x14000641b  lea     rdx, SmbSendCompletion
0x140006422  mov     rax, [rax+188h]
0x140006429  mov     [rsp+88h+pContext], rax
0x14000642e  call    McTemplateK0qp_EtwWriteTransfer
0x140006433  jmp     loc_14000621D
0x140006438  mov     rdx, [r14+40h]
0x14000643c  lea     rcx, [rbp+30h]
0x140006440  xor     r14d, r14d
0x140006443  cmp     rdx, rcx
0x140006446  lea     rax, [rdx-40h]
0x14000644a  cmovnz  r14, rax
0x14000644e  jmp     loc_1400062C3
0x140006453  mov     rcx, rbp
0x140006456  call    SmbCeReleaseCompoundingKeyLock
0x14000645b  jmp     loc_1400063A6
0x140006460  mov     rax, [rbx+38h]
0x140006464  mov     [rsp+88h+arg_18], sil
0x14000646c  mov     rbp, [rax+38h]
0x140006470  mov     rcx, rbp
0x140006473  call    SmbCeAcquireCompoundingKeyLock
0x140006478  mov     rcx, rbp
0x14000647b  call    SmbCseUnchainCompoundedBufferContextsLite
0x140006480  call    SmbCeReleaseCompoundingKeyLock
0x140006485  mov     r9, [rsp+88h+arg_0]
0x14000648d  jmp     loc_1400061B4
0x140006492  mov     rbx, [rdi+48h]
0x140006496  mov     rsi, [rbx+18h]
0x14000649a  call    cs:__imp_KeGetCurrentIrql
0x1400064a1  nop     dword ptr [rax+rax+00h]
0x1400064a6  cmp     al, 2
0x1400064a8  jnb     loc_140006533
0x1400064ae  mov     rax, [rbx+38h]
0x1400064b2  test    rax, rax
0x1400064b5  jz      short loc_1400064D4
0x1400064b7  mov     rax, [rax+390h]
0x1400064be  test    rax, rax
0x1400064c1  jz      short loc_1400064D4
0x1400064c3  mov     rcx, rdi
0x1400064c6  call    _guard_dispatch_icall
0x1400064cb  mov     ecx, eax
0x1400064cd  cmp     eax, 0C0410003h
0x1400064d2  jz      short loc_140006542
0x1400064d4  mov     rax, [rdi+0E8h]
0x1400064db  mov     rcx, rdi
0x1400064de  mov     qword ptr [rdi+0D0h], 0
0x1400064e9  mov     dword ptr [rdi+28h], 8
0x1400064f0  mov     rax, [rax+20h]
0x1400064f4  call    _guard_dispatch_icall
0x1400064f9  mov     ecx, eax
0x1400064fb  cmp     eax, 0C0410003h
0x140006500  jz      short loc_140006542
0x140006502  lea     rcx, [rdi+200h]
0x140006509  call    RDR_PERF_EXIT
0x14000650e  lea     rcx, [rdi+200h]
0x140006515  call    RDR_PERF_OUTPUT_ETW
0x14000651a  lea     rcx, [rdi+200h]
0x140006521  call    RDR_PERF_FREE
0x140006526  mov     rcx, rdi; pContext
0x140006529  call    SmbCeDereferenceExchange
0x14000652e  jmp     loc_1400063AF
0x140006533  mov     eax, [rdi+44h]
0x140006536  xor     ecx, ecx
0x140006538  bt      eax, 12h
0x14000653c  jb      loc_1400064AE
0x140006542  mov     eax, [rdi+44h]
0x140006545  test    al, 1
0x140006547  jnz     loc_14000661C
0x14000654d  lea     rcx, [rdi+200h]
0x140006554  mov     dl, 14h
0x140006556  call    RDR_PERF_ENTER
0x14000655b  mov     r8d, 7
0x140006561  mov     rdx, rdi
0x140006564  mov     rcx, rsi
0x140006567  call    SmbCeIncrementTeardownOpCounter
0x14000656c  lea     r8, [rdi+0F0h]; pWorkQueueItem
0x140006573  mov     [rsp+88h+pContext], rdi; pContext
0x140006578  lea     r9, SmbCepFinalizeExchangeWorker; Routine
0x14000657f  mov     edx, 3; WorkQueueType
0x140006584  mov     rcx, rsi; pMRxDeviceObject
0x140006587  call    cs:__imp_RxPostToWorkerThread
0x14000658e  nop     dword ptr [rax+rax+00h]
0x140006593  jmp     loc_1400063AF
0x140006598  cmp     byte ptr [rcx+29h], 4
0x14000659c  jb      loc_140006273
0x1400065a2  mov     rcx, [rcx+18h]
0x1400065a6  lea     eax, [r8-1]
0x1400065aa  mov     [rsp+88h+var_60], r8d
0x1400065af  mov     edx, 21h ; '!'
0x1400065b4  lea     r8, WPP_d39beb3e593835eae73483c3886eb046_Traceguids
0x1400065bb  mov     dword ptr [rsp+88h+pContext], eax
0x1400065bf  mov     r9, rdi
0x1400065c2  call    WPP_SF_qDD
0x1400065c7  jmp     loc_140006273
0x1400065cc  mov     rcx, r14
0x1400065cf  call    SmbCseInvalidateMemoryRegistrationAsync
0x1400065d4  cmp     eax, 0C0000008h
0x1400065d9  jz      loc_14005B7B4
0x1400065df  cmp     eax, 103h
0x1400065e4  mov     rax, 12E00000000h
0x1400065ee  jz      loc_1400062A9
0x1400065f4  mov     byte ptr [rbx+57h], 0
0x1400065f8  mov     byte ptr [r14+56h], 0
0x1400065fd  cmp     dword ptr [r14+30h], 0
0x140006602  jnz     loc_14005B7C3
0x140006608  mov     rdx, r15
0x14000660b  mov     rcx, r14
0x14000660e  or      rdx, rax
0x140006611  call    SmbCseUpdateBufferContextStatus
0x140006616  nop
0x140006617  jmp     loc_14005B7C3
0x14000661c  movsxd  r9, ecx; BugCheckParameter3
0x14000661f  mov     r8, rdi; BugCheckParameter2
0x140006622  mov     ecx, 27h ; '''; BugCheckCode
0x140006627  mov     [rsp+88h+pContext], 0; BugCheckParameter4
0x140006630  mov     edx, 43584D5Fh; BugCheckParameter1
0x140006635  call    cs:__imp_KeBugCheckEx
0x140006642  mov     dl, 1; PriorityBoost
0x140006644  mov     rcx, r12; Irp
0x140006647  call    cs:__imp_IofCompleteRequest
0x14000664e  nop     dword ptr [rax+rax+00h]
0x140006653  jmp     loc_1400063B8
0x14005b75c  mov     rcx, cs:WPP_GLOBAL_Control
0x14005b763  cmp     rcx, rax
0x14005b766  jz      loc_14000619F
0x14005b76c  mov     eax, [rcx+2Ch]
  ... truncated ...
```
