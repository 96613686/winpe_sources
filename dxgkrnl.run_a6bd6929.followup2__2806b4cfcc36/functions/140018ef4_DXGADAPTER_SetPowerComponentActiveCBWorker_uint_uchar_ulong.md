# DXGADAPTER::SetPowerComponentActiveCBWorker(uint,uchar,ulong)

- ea: `0x140018ef4`
- end: `0x1400194cf`
- name: `?SetPowerComponentActiveCBWorker@DXGADAPTER@@QEAAXIEK@Z`
- size: `1499`
- prototype: `void __fastcall(DXGADAPTER *__hidden this, unsigned int, unsigned __int8, unsigned int)`
- caller_count: `3`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1400188f8`
- `0x140018ca8`
- `0x140018d20`

## callees

- `0x140013ff8`
- `0x140018ef4`
- `0x140019834`
- `0x14001b0a0`
- `0x14001bffc`
- `0x14001d884`
- `0x14004f678`
- `0x140079d0c`

## import_xrefs

- `ntoskrnl!PoFxIdleComponent` at `0x1400191b7`
- `ntoskrnl!PoFxIdleComponent` at `0x1400191b7`
- `ntoskrnl!PoFxActivateComponent` at `0x140019177`
- `ntoskrnl!PoFxActivateComponent` at `0x1400192ed`
- `ntoskrnl!PoFxActivateComponent` at `0x140019177`
- `ntoskrnl!PoFxActivateComponent` at `0x1400192ed`
- `ntoskrnl!KeSetTimer` at `0x140019412`
- `ntoskrnl!KeSetTimer` at `0x140019412`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140019090`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140019090`
- `ntoskrnl!KeCancelTimer` at `0x1400190e6`
- `ntoskrnl!KeCancelTimer` at `0x1400190e6`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1400190fc`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1400191cc`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1400190fc`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1400191cc`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400192b7`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400192b7`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140018fa5`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140019132`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140019422`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140018fa5`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140019132`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140019422`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140018f80`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14001903f`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400193c2`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140018f80`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14001903f`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400193c2`
- `watchdog!WdLogSingleEntry5` at `0x140019490`
- `watchdog!WdLogSingleEntry5` at `0x140019490`

## pseudocode

```c
void __fastcall DXGADAPTER::SetPowerComponentActiveCBWorker(
        DXGADAPTER *this,
        unsigned int a2,
        __int64 a3,
        unsigned int a4)
{
  char v4; // r12
  __int64 v5; // r15
  char v6; // bl
  __int64 v8; // r14
  __int64 v9; // rsi
  __int64 v10; // rcx
  char v11; // r13
  char v12; // bl
  int v13; // ecx
  __int64 v14; // r8
  __int64 v15; // r12
  __int64 v16; // rax
  __int64 *v17; // rax
  __int64 v18; // rcx
  __int64 v19; // r12
  __int64 *v20; // rax
  __int64 *v21; // rdx
  __int64 **v22; // rcx
  unsigned int v23; // esi
  int v24; // ecx
  __int64 v25; // rcx
  __int64 v26; // rax
  __int64 **v27; // rdx
  __int64 v28; // rcx
  int v29; // ecx
  int v30; // r8d
  unsigned int i; // edx
  struct _KLOCK_QUEUE_HANDLE v32; // [rsp+40h] [rbp-41h] BYREF
  __int64 v33; // [rsp+58h] [rbp-29h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+60h] [rbp-21h] BYREF
  char *v35; // [rsp+80h] [rbp-1h]
  struct _KLOCK_QUEUE_HANDLE v36; // [rsp+88h] [rbp+7h] BYREF
  char v37; // [rsp+A0h] [rbp+1Fh]
  char v38; // [rsp+F8h] [rbp+77h]

  v38 = a3;
  v4 = 0;
  v5 = a2;
  v6 = a3;
  if ( !*((_QWORD *)this + 420) )
    return;
  if ( bTracingEnabled && (Microsoft_Windows_DxgKrnlEnableBits & 0x20000) != 0 )
    McTemplateK0pt_EtwWriteTransfer(&DxgkControlGuid_Context, Dxgk_SetPowerComponentActiveCB, a3, this, a2);
  v8 = *((_QWORD *)this + 419);
  v9 = 520 * v5;
  v10 = *(_QWORD *)(520 * v5 + v8 + 512);
  if ( v10 )
  {
    DXGPOWERSTATISTICSTRANSITIONENGINE::RecordActivity((DXGPOWERSTATISTICSTRANSITIONENGINE *)(v10 + 136));
    if ( (*((_DWORD *)this + 776) & 0x10) != 0 )
    {
      for ( i = 0; i < *((_DWORD *)this + 496); ++i )
      {
        if ( !*(_DWORD *)(*((_QWORD *)this + 554) + 4LL * i) )
          goto LABEL_4;
      }
    }
    else if ( !**((_DWORD **)this + 554) )
    {
      goto LABEL_4;
    }
    memset(&v32, 0, sizeof(v32));
    KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)this + 594, &v32);
    *(_BYTE *)(*(_QWORD *)(v9 + v8 + 512) + 240LL) = 1;
    if ( !*((_BYTE *)this + 4760) )
    {
      *((_BYTE *)this + 4760) = 1;
      _InterlockedIncrement64((volatile signed __int64 *)this + 3);
      *((_QWORD *)this + 577) = -1;
      KeSetTimer((PKTIMER)((char *)this + 4624), (LARGE_INTEGER)-120000LL, (PKDPC)((char *)this + 4688));
    }
    KeReleaseInStackQueuedSpinLock(&v32);
  }
LABEL_4:
  v11 = v6;
  memset(&LockHandle, 0, sizeof(LockHandle));
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v9 + v8 + 504), &LockHandle);
  if ( (int)++*(_DWORD *)(v9 + v8 + 352) <= 1 )
  {
    v12 = 0;
    v15 = MEMORY[0xFFFFF78000000014];
    if ( *(_BYTE *)(v9 + v8 + 360) )
    {
      v11 = 0;
      v4 = 1;
      goto LABEL_6;
    }
    v16 = *(_QWORD *)(v9 + v8 + 480);
    v37 = 0;
    v33 = v16;
    v35 = (char *)this + 3816;
    KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)this + 477, &v36);
    *((_QWORD *)this + 478) = KeGetCurrentThread();
    v17 = (__int64 *)(v9 + v8 + 400);
    v37 = 1;
    v12 = 0;
    v18 = *v17;
    if ( *v17 )
    {
      if ( *(__int64 **)(v18 + 8) != v17 )
        goto LABEL_49;
      v27 = (__int64 **)v17[1];
      if ( *v27 != v17 )
        goto LABEL_49;
      *v27 = (__int64 *)v18;
      *(_QWORD *)(v18 + 8) = v27;
      *v17 = 0;
      if ( *((DXGADAPTER **)this + 475) == (DXGADAPTER *)((char *)this + 3800) && *((_BYTE *)this + 3788) )
      {
        v28 = *((_QWORD *)this + 407);
        *((_BYTE *)this + 3788) = 0;
        VIDSCH_EXPORT::VidSchEnableLatencyToleranceTimer(
          *(VIDSCH_EXPORT **)(v28 + 736),
          *(struct _VIDSCH_GLOBAL **)(v28 + 744),
          0);
      }
    }
    v19 = v15 - v33;
    memset(&v32, 0, sizeof(v32));
    KeAcquireInStackQueuedSpinLockAtDpcLevel((PKSPIN_LOCK)this + 486, &v32);
    v20 = (__int64 *)(v9 + v8 + 440);
    v21 = (__int64 *)*v20;
    if ( !*v20 )
    {
      KeReleaseInStackQueuedSpinLockFromDpcLevel(&v32);
      v26 = *(_QWORD *)(v9 + v8 + 496);
      if ( v19 < v26 )
        *(_QWORD *)(v9 + v8 + 472) = v26;
      v11 = 1;
      goto LABEL_23;
    }
    if ( (__int64 *)v21[1] == v20 )
    {
      v22 = (__int64 **)v20[1];
      if ( *v22 == v20 )
      {
        *v22 = v21;
        v21[1] = (__int64)v22;
        *v20 = 0;
        if ( *((DXGADAPTER **)this + 480) == (DXGADAPTER *)((char *)this + 3840) )
        {
          KeCancelTimer((PKTIMER)this + 61);
          *((_BYTE *)this + 3789) = 0;
        }
        KeReleaseInStackQueuedSpinLockFromDpcLevel(&v32);
        if ( v19 > *(_QWORD *)(v9 + v8 + 496) )
          *(_QWORD *)(v9 + v8 + 472) = 0;
        v12 = 1;
LABEL_23:
        if ( v37 )
        {
          v37 = 0;
          *((_QWORD *)v35 + 1) = 0;
          KeReleaseInStackQueuedSpinLock(&v36);
        }
        v4 = 0;
        goto LABEL_6;
      }
    }
LABEL_49:
    __fastfail(3u);
  }
  v12 = 1;
LABEL_6:
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  if ( *(_DWORD *)(v9 + v8 + 208) == 7 )
    DxgkNotifySharedPowerGraphicsFStateTransition(this, *(_DWORD *)(v9 + v8 + 4), 0, 1);
  if ( v11 )
  {
    if ( v38 )
    {
      if ( KeGetCurrentIrql() >= 2u )
      {
        WdLogSingleEntry5(0, 275, 20, this, 0, 0);
        WdLogGlobalForLineNumber = 1744;
      }
      if ( bTracingEnabled && (Microsoft_Windows_DxgKrnlEnableBits & 0x20000) != 0 )
        McTemplateK0pqq_EtwWriteTransfer(v29, (unsigned int)Dxgk_ReportPowerComponentState, v30, (_DWORD)this, v5, 1);
      PoFxActivateComponent(*((_QWORD *)this + 420), (unsigned int)v5, 1);
      v23 = a4;
    }
    else
    {
      if ( bTracingEnabled && (Microsoft_Windows_DxgKrnlEnableBits & 0x20000) != 0 )
        McTemplateK0pqq_EtwWriteTransfer(v13, (unsigned int)Dxgk_ReportPowerComponentState, v14, (_DWORD)this, v5, 1);
      v23 = a4;
      PoFxActivateComponent(*((_QWORD *)this + 420), (unsigned int)v5, a4);
    }
    if ( v12 )
    {
      if ( bTracingEnabled && (Microsoft_Windows_DxgKrnlEnableBits & 0x20000) != 0 )
        McTemplateK0pqq_EtwWriteTransfer(v24, (unsigned int)Dxgk_ReportPowerComponentState, v14, (_DWORD)this, v5, 0);
      v25 = *((_QWORD *)this + 420);
      if ( v25 )
        PoFxIdleComponent(v25, (unsigned int)v5, v23);
    }
  }
  if ( v4 )
  {
    DXGADAPTER::PowerRuntimeComponentIdleStateCallback(this, v5, 0, 1);
    DXGADAPTER::PowerRuntimeComponentActiveCallback(this, v5, 1u);
  }
  if ( bTracingEnabled )
  {
    if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x20000) != 0 )
      McTemplateK0pt_EtwWriteTransfer(&DxgkControlGuid_Context, Dxgk_SetPowerComponentActiveCBEnd, v14, this, v5);
  }
}

```

## disassembly

```asm
0x140018ef4  mov     rax, rsp
0x140018ef7  mov     [rax+10h], rbx
0x140018efb  mov     [rax+20h], r9d
0x140018eff  mov     [rax+18h], r8b
0x140018f03  push    rbp
0x140018f04  push    rsi
0x140018f05  push    rdi
0x140018f06  push    r12
0x140018f08  push    r13
0x140018f0a  push    r14
0x140018f0c  push    r15
0x140018f0e  lea     rbp, [rax-5Fh]
0x140018f12  sub     rsp, 0A0h
0x140018f19  xor     r12d, r12d
0x140018f1c  mov     r15d, edx
0x140018f1f  mov     bl, r8b
0x140018f22  mov     rdi, rcx
0x140018f25  cmp     [rcx+0D20h], r12
0x140018f2c  jz      loc_140018FE2
0x140018f32  cmp     cs:bTracingEnabled, r12b
0x140018f39  jnz     loc_140019256
0x140018f3f  mov     r14, [rdi+0D18h]
0x140018f46  imul    rsi, r15, 208h
0x140018f4d  mov     rcx, [rsi+r14+200h]
0x140018f55  test    rcx, rcx
0x140018f58  jnz     loc_14001935E
0x140018f5e  xorps   xmm0, xmm0
0x140018f61  mov     [rbp+57h+arg_0], r12b
0x140018f65  xor     eax, eax
0x140018f67  lea     rcx, [r14+1F8h]
0x140018f6e  add     rcx, rsi; SpinLock
0x140018f71  mov     qword ptr [rbp+57h+LockHandle.OldIrql], rax
0x140018f75  lea     rdx, [rbp+57h+LockHandle]; LockHandle
0x140018f79  mov     r13b, bl
0x140018f7c  movups  xmmword ptr [rbp+57h+LockHandle.LockQueue.Next], xmm0
0x140018f80  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140018f87  nop     dword ptr [rax+rax+00h]
0x140018f8c  inc     dword ptr [rsi+r14+160h]
0x140018f94  cmp     dword ptr [rsi+r14+160h], 1
0x140018f9d  jle     short loc_140018FFE
0x140018f9f  mov     bl, 1
0x140018fa1  lea     rcx, [rbp+57h+LockHandle]; LockHandle
0x140018fa5  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140018fac  nop     dword ptr [rax+rax+00h]
0x140018fb1  cmp     dword ptr [rsi+r14+0D0h], 7
0x140018fba  jz      loc_140019460
0x140018fc0  xor     r14d, r14d
0x140018fc3  test    r13b, r13b
0x140018fc6  jnz     loc_140019147
0x140018fcc  test    r12b, r12b
0x140018fcf  jnz     loc_1400194AB
0x140018fd5  cmp     cs:bTracingEnabled, r14b
0x140018fdc  jnz     loc_140019283
0x140018fe2  mov     rbx, [rsp+0D0h+arg_8]
0x140018fea  add     rsp, 0A0h
0x140018ff1  pop     r15
0x140018ff3  pop     r14
0x140018ff5  pop     r13
0x140018ff7  pop     r12
0x140018ff9  pop     rdi
0x140018ffa  pop     rsi
0x140018ffb  pop     rbp
0x140018ffc  retn
0x140018ffe  xor     ecx, ecx
0x140019000  mov     r12, 0FFFFF78000000014h
0x14001900a  mov     bl, cl
0x14001900c  mov     r12, [r12]
0x140019010  cmp     [rsi+r14+168h], cl
0x140019018  jnz     loc_140019433
0x14001901e  mov     rax, [rsi+r14+1E0h]
0x140019026  lea     rbx, [rdi+0EE8h]
0x14001902d  mov     [rbp+57h+var_38], cl
0x140019030  lea     rdx, [rbp+57h+var_50]; LockHandle
0x140019034  mov     rcx, rbx; SpinLock
0x140019037  mov     [rbp+57h+var_80], rax
0x14001903b  mov     [rbp+57h+var_58], rbx
0x14001903f  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140019046  nop     dword ptr [rax+rax+00h]
0x14001904b  mov     rax, gs:188h
0x140019054  mov     [rbx+8], rax
0x140019058  lea     rax, [r14+190h]
0x14001905f  add     rax, rsi
0x140019062  mov     [rbp+57h+var_38], 1
0x140019066  xor     ebx, ebx
0x140019068  mov     rcx, [rax]
0x14001906b  test    rcx, rcx
0x14001906e  jnz     loc_1400191F1
0x140019074  sub     r12, [rbp+57h+var_80]
0x140019078  lea     rcx, [rdi+0F30h]; SpinLock
0x14001907f  xorps   xmm0, xmm0
0x140019082  lea     rdx, [rbp+57h+var_98]; LockHandle
0x140019086  xor     eax, eax
0x140019088  movups  xmmword ptr [rbp+57h+var_98.LockQueue.Next], xmm0
0x14001908c  mov     qword ptr [rbp+57h+var_98.OldIrql], rax
0x140019090  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x140019097  nop     dword ptr [rax+rax+00h]
0x14001909c  lea     rax, [r14+1B8h]
0x1400190a3  add     rax, rsi
0x1400190a6  mov     rdx, [rax]
0x1400190a9  test    rdx, rdx
0x1400190ac  jz      loc_1400191C8
0x1400190b2  cmp     [rdx+8], rax
0x1400190b6  jnz     loc_1400192B0
0x1400190bc  mov     rcx, [rax+8]
0x1400190c0  cmp     [rcx], rax
0x1400190c3  jnz     loc_1400192B0
0x1400190c9  mov     [rcx], rdx
0x1400190cc  mov     [rdx+8], rcx
0x1400190d0  mov     [rax], rbx
0x1400190d3  lea     rax, [rdi+0F00h]
0x1400190da  cmp     [rax], rax
0x1400190dd  jnz     short loc_1400190F8
0x1400190df  lea     rcx, [rdi+0F40h]; PKTIMER
0x1400190e6  call    cs:__imp_KeCancelTimer
0x1400190ed  nop     dword ptr [rax+rax+00h]
0x1400190f2  mov     [rdi+0ECDh], bl
0x1400190f8  lea     rcx, [rbp+57h+var_98]; LockHandle
0x1400190fc  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x140019103  nop     dword ptr [rax+rax+00h]
0x140019108  cmp     r12, [rsi+r14+1F0h]
0x140019110  jg      loc_14001943E
0x140019116  mov     bl, 1
0x140019118  xor     ecx, ecx
0x14001911a  cmp     [rbp+57h+var_38], cl
0x14001911d  jz      loc_140019458
0x140019123  mov     rax, [rbp+57h+var_58]
0x140019127  mov     [rbp+57h+var_38], cl
0x14001912a  mov     [rax+8], rcx
0x14001912e  lea     rcx, [rbp+57h+var_50]; LockHandle
0x140019132  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140019139  nop     dword ptr [rax+rax+00h]
0x14001913e  mov     r12b, [rbp+57h+arg_0]
0x140019142  jmp     loc_140018FA1
0x140019147  cmp     [rbp+57h+arg_10], r14b
0x14001914b  jnz     loc_1400192B7
0x140019151  cmp     cs:bTracingEnabled, r14b
0x140019158  jz      short loc_140019167
0x14001915a  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, 2
0x140019161  jnz     loc_140019301
0x140019167  mov     esi, [rbp+57h+arg_18]
0x14001916a  mov     edx, r15d
0x14001916d  mov     rcx, [rdi+0D20h]
0x140019174  mov     r8d, esi
0x140019177  call    cs:__imp_PoFxActivateComponent
0x14001917e  nop     dword ptr [rax+rax+00h]
0x140019183  test    bl, bl
0x140019185  jz      loc_140018FCC
0x14001918b  cmp     cs:bTracingEnabled, r14b
0x140019192  jz      short loc_1400191A1
0x140019194  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, 2
0x14001919b  jnz     loc_140019340
0x1400191a1  mov     rcx, [rdi+0D20h]
0x1400191a8  test    rcx, rcx
0x1400191ab  jz      loc_140018FCC
0x1400191b1  mov     r8d, esi
0x1400191b4  mov     edx, r15d
0x1400191b7  call    cs:__imp_PoFxIdleComponent
0x1400191be  nop     dword ptr [rax+rax+00h]
0x1400191c3  jmp     loc_140018FCC
0x1400191c8  lea     rcx, [rbp+57h+var_98]; LockHandle
0x1400191cc  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x1400191d3  nop     dword ptr [rax+rax+00h]
0x1400191d8  mov     rax, [rsi+r14+1F0h]
0x1400191e0  cmp     r12, rax
0x1400191e3  jl      loc_14001944B
0x1400191e9  mov     r13b, 1
0x1400191ec  jmp     loc_140019118
0x1400191f1  cmp     [rcx+8], rax
0x1400191f5  jnz     loc_1400192B0
0x1400191fb  mov     rdx, [rax+8]
0x1400191ff  cmp     [rdx], rax
0x140019202  jnz     loc_1400192B0
0x140019208  mov     [rdx], rcx
0x14001920b  mov     [rcx+8], rdx
0x14001920f  mov     [rax], rbx
0x140019212  lea     rax, [rdi+0ED8h]
0x140019219  cmp     [rax], rax
0x14001921c  jnz     loc_140019074
0x140019222  cmp     [rdi+0ECCh], bl
0x140019228  jz      loc_140019074
0x14001922e  mov     rcx, [rdi+0CB8h]
0x140019235  xor     r8d, r8d; unsigned __int8
0x140019238  mov     [rdi+0ECCh], bl
0x14001923e  mov     rdx, [rcx+2E8h]; struct _VIDSCH_GLOBAL *
0x140019245  mov     rcx, [rcx+2E0h]; this
0x14001924c  call    ?VidSchEnableLatencyToleranceTimer@VIDSCH_EXPORT@@QEAAXPEAU_VIDSCH_GLOBAL@@E@Z; VIDSCH_EXPORT::VidSchEnableLatencyToleranceTimer(_VIDSCH_GLOBAL *,uchar)
0x140019251  jmp     loc_140019074
0x140019256  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, 2
0x14001925d  jz      loc_140018F3F
0x140019263  mov     r9, rdi
0x140019266  mov     dword ptr [rsp+0D0h+var_B0], r15d
0x14001926b  lea     rdx, Dxgk_SetPowerComponentActiveCB
0x140019272  lea     rcx, DxgkControlGuid_Context
0x140019279  call    McTemplateK0pt_EtwWriteTransfer
0x14001927e  jmp     loc_140018F3F
0x140019283  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, 2
0x14001928a  jz      loc_140018FE2
0x140019290  mov     r9, rdi
0x140019293  mov     dword ptr [rsp+0D0h+var_B0], r15d
0x140019298  lea     rdx, Dxgk_SetPowerComponentActiveCBEnd
0x14001929f  lea     rcx, DxgkControlGuid_Context
0x1400192a6  call    McTemplateK0pt_EtwWriteTransfer
0x1400192ab  jmp     loc_140018FE2
0x1400192b0  mov     ecx, 3
0x1400192b5  int     29h; Win8: RtlFailFast(ecx)
0x1400192b7  call    cs:__imp_KeGetCurrentIrql
0x1400192be  nop     dword ptr [rax+rax+00h]
0x1400192c3  cmp     al, 2
0x1400192c5  jnb     loc_140019478
0x1400192cb  cmp     cs:bTracingEnabled, r14b
0x1400192d2  jz      short loc_1400192DD
0x1400192d4  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, 2
0x1400192db  jnz     short loc_140019322
0x1400192dd  mov     rcx, [rdi+0D20h]
0x1400192e4  mov     r8d, 1
0x1400192ea  mov     edx, r15d
0x1400192ed  call    cs:__imp_PoFxActivateComponent
0x1400192f4  nop     dword ptr [rax+rax+00h]
0x1400192f9  mov     esi, [rbp+57h+arg_18]
0x1400192fc  jmp     loc_140019183
0x140019301  mov     dword ptr [rsp+28h], 1
0x140019309  lea     rdx, Dxgk_ReportPowerComponentState
0x140019310  mov     r9, rdi
0x140019313  mov     dword ptr [rsp+0D0h+var_B0], r15d
0x140019318  call    McTemplateK0pqq_EtwWriteTransfer
0x14001931d  jmp     loc_140019167
0x140019322  mov     dword ptr [rsp+28h], 1
0x14001932a  lea     rdx, Dxgk_ReportPowerComponentState
0x140019331  mov     r9, rdi
0x140019334  mov     dword ptr [rsp+0D0h+var_B0], r15d
0x140019339  call    McTemplateK0pqq_EtwWriteTransfer
0x14001933e  jmp     short loc_1400192DD
0x140019340  mov     [rsp+28h], r14d
0x140019345  lea     rdx, Dxgk_ReportPowerComponentState
0x14001934c  mov     r9, rdi
0x14001934f  mov     dword ptr [rsp+0D0h+var_B0], r15d
0x140019354  call    McTemplateK0pqq_EtwWriteTransfer
0x140019359  jmp     loc_1400191A1
0x14001935e  add     rcx, 88h; this
0x140019365  call    ?RecordActivity@DXGPOWERSTATISTICSTRANSITIONENGINE@@QEAAXXZ; DXGPOWERSTATISTICSTRANSITIONENGINE::RecordActivity(void)
0x14001936a  mov     eax, [rdi+0C20h]
0x140019370  test    al, 10h
0x140019372  jz      short loc_14001939A
0x140019374  mov     r8d, [rdi+7C0h]
0x14001937b  mov     edx, r12d
0x14001937e  cmp     edx, r8d
0x140019381  jnb     short loc_1400193AA
0x140019383  mov     rax, [rdi+1150h]
0x14001938a  mov     ecx, edx
0x14001938c  cmp     [rax+rcx*4], r12d
0x140019390  jz      loc_140018F5E
0x140019396  inc     edx
0x140019398  jmp     short loc_14001937E
0x14001939a  mov     rax, [rdi+1150h]
0x1400193a1  cmp     [rax], r12d
0x1400193a4  jz      loc_140018F5E
0x1400193aa  xorps   xmm0, xmm0
0x1400193ad  lea     rcx, [rdi+1290h]; SpinLock
0x1400193b4  xor     eax, eax
0x1400193b6  lea     rdx, [rbp+57h+var_98]; LockHandle
0x1400193ba  movups  xmmword ptr [rbp+57h+var_98.LockQueue.Next], xmm0
0x1400193be  mov     qword ptr [rbp+57h+var_98.OldIrql], rax
0x1400193c2  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400193c9  nop     dword ptr [rax+rax+00h]
0x1400193ce  mov     rax, [rsi+r14+200h]
0x1400193d6  mov     byte ptr [rax+0F0h], 1
0x1400193dd  cmp     [rdi+1298h], r12b
0x1400193e4  jnz     short loc_14001941E
0x1400193e6  mov     byte ptr [rdi+1298h], 1
0x1400193ed  lock inc qword ptr [rdi+18h]
0x1400193f2  lea     r8, [rdi+1250h]; Dpc
0x1400193f9  mov     qword ptr [rdi+1208h], 0FFFFFFFFFFFFFFFFh
0x140019404  lea     rcx, [rdi+1210h]; Timer
0x14001940b  mov     rdx, 0FFFFFFFFFFFE2B40h; DueTime
0x140019412  call    cs:__imp_KeSetTimer
0x140019419  nop     dword ptr [rax+rax+00h]
0x14001941e  lea     rcx, [rbp+57h+var_98]; LockHandle
0x140019422  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140019429  nop     dword ptr [rax+rax+00h]
0x14001942e  jmp     loc_140018F5E
0x140019433  mov     r13b, cl
0x140019436  mov     r12b, 1
0x140019439  jmp     loc_140018FA1
0x14001943e  mov     [rsi+r14+1D8h], rbx
0x140019446  jmp     loc_140019116
0x14001944b  mov     [rsi+r14+1D8h], rax
0x140019453  jmp     loc_1400191E9
0x140019458  mov     r12b, cl
0x14001945b  jmp     loc_140018FA1
0x140019460  mov     edx, [rsi+r14+4]; unsigned int
0x140019465  mov     r9b, 1; char
0x140019468  xor     r8d, r8d; unsigned int
0x14001946b  mov     rcx, rdi; void *
0x14001946e  call    DxgkNotifySharedPowerGraphicsFStateTransition
0x140019473  jmp     loc_140018FC0
0x140019478  xor     ecx, ecx
0x14001947a  mov     [rsp+28h], r14
0x14001947f  mov     r9, rdi
0x140019482  mov     [rsp+0D0h+var_B0], r14
0x140019487  mov     edx, 113h
  ... truncated ...
```
