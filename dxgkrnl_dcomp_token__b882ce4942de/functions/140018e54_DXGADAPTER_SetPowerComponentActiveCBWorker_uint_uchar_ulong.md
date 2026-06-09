# DXGADAPTER::SetPowerComponentActiveCBWorker(uint,uchar,ulong)

- ea: `0x140018e54`
- end: `0x14001942f`
- name: `?SetPowerComponentActiveCBWorker@DXGADAPTER@@QEAAXIEK@Z`
- size: `1499`
- prototype: `void __fastcall(DXGADAPTER *__hidden this, unsigned int, unsigned __int8, unsigned int)`
- caller_count: `3`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x140018858`
- `0x140018c08`
- `0x140018c80`

## callees

- `0x140013e38`
- `0x140018e54`
- `0x140019794`
- `0x14001af70`
- `0x14001becc`
- `0x14001d6b4`
- `0x14004f478`
- `0x1400795fc`

## import_xrefs

- `ntoskrnl!PoFxIdleComponent` at `0x140019117`
- `ntoskrnl!PoFxIdleComponent` at `0x140019117`
- `ntoskrnl!PoFxActivateComponent` at `0x1400190d7`
- `ntoskrnl!PoFxActivateComponent` at `0x14001924d`
- `ntoskrnl!PoFxActivateComponent` at `0x1400190d7`
- `ntoskrnl!PoFxActivateComponent` at `0x14001924d`
- `ntoskrnl!KeSetTimer` at `0x140019372`
- `ntoskrnl!KeSetTimer` at `0x140019372`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140018ff0`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140018ff0`
- `ntoskrnl!KeCancelTimer` at `0x140019046`
- `ntoskrnl!KeCancelTimer` at `0x140019046`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14001905c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14001912c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14001905c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14001912c`
- `ntoskrnl!KeGetCurrentIrql` at `0x140019217`
- `ntoskrnl!KeGetCurrentIrql` at `0x140019217`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140018f05`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140019092`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140019382`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140018f05`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140019092`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140019382`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140018ee0`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140018f9f`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140019322`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140018ee0`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140018f9f`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140019322`
- `watchdog!WdLogSingleEntry5` at `0x1400193f0`
- `watchdog!WdLogSingleEntry5` at `0x1400193f0`

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
  if ( !*((_QWORD *)this + 418) )
    return;
  if ( bTracingEnabled && (Microsoft_Windows_DxgKrnlEnableBits & 0x20000) != 0 )
    McTemplateK0pt_EtwWriteTransfer(&DxgkControlGuid_Context, Dxgk_SetPowerComponentActiveCB, a3, this, a2);
  v8 = *((_QWORD *)this + 417);
  v9 = 520 * v5;
  v10 = *(_QWORD *)(520 * v5 + v8 + 512);
  if ( v10 )
  {
    DXGPOWERSTATISTICSTRANSITIONENGINE::RecordActivity((DXGPOWERSTATISTICSTRANSITIONENGINE *)(v10 + 136));
    if ( (*((_DWORD *)this + 772) & 0x10) != 0 )
    {
      for ( i = 0; i < *((_DWORD *)this + 492); ++i )
      {
        if ( !*(_DWORD *)(*((_QWORD *)this + 552) + 4LL * i) )
          goto LABEL_4;
      }
    }
    else if ( !**((_DWORD **)this + 552) )
    {
      goto LABEL_4;
    }
    memset(&v32, 0, sizeof(v32));
    KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)this + 592, &v32);
    *(_BYTE *)(*(_QWORD *)(v9 + v8 + 512) + 240LL) = 1;
    if ( !*((_BYTE *)this + 4744) )
    {
      *((_BYTE *)this + 4744) = 1;
      _InterlockedIncrement64((volatile signed __int64 *)this + 3);
      *((_QWORD *)this + 575) = -1;
      KeSetTimer((PKTIMER)this + 72, (LARGE_INTEGER)-120000LL, (PKDPC)this + 73);
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
    v35 = (char *)this + 3800;
    KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)this + 475, &v36);
    *((_QWORD *)this + 476) = KeGetCurrentThread();
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
      if ( *((DXGADAPTER **)this + 473) == (DXGADAPTER *)((char *)this + 3784) && *((_BYTE *)this + 3772) )
      {
        v28 = *((_QWORD *)this + 405);
        *((_BYTE *)this + 3772) = 0;
        VIDSCH_EXPORT::VidSchEnableLatencyToleranceTimer(
          *(VIDSCH_EXPORT **)(v28 + 736),
          *(struct _VIDSCH_GLOBAL **)(v28 + 744),
          0);
      }
    }
    v19 = v15 - v33;
    memset(&v32, 0, sizeof(v32));
    KeAcquireInStackQueuedSpinLockAtDpcLevel((PKSPIN_LOCK)this + 484, &v32);
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
        if ( *((DXGADAPTER **)this + 478) == (DXGADAPTER *)((char *)this + 3824) )
        {
          KeCancelTimer((PKTIMER)((char *)this + 3888));
          *((_BYTE *)this + 3773) = 0;
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
      PoFxActivateComponent(*((_QWORD *)this + 418), (unsigned int)v5, 1);
      v23 = a4;
    }
    else
    {
      if ( bTracingEnabled && (Microsoft_Windows_DxgKrnlEnableBits & 0x20000) != 0 )
        McTemplateK0pqq_EtwWriteTransfer(v13, (unsigned int)Dxgk_ReportPowerComponentState, v14, (_DWORD)this, v5, 1);
      v23 = a4;
      PoFxActivateComponent(*((_QWORD *)this + 418), (unsigned int)v5, a4);
    }
    if ( v12 )
    {
      if ( bTracingEnabled && (Microsoft_Windows_DxgKrnlEnableBits & 0x20000) != 0 )
        McTemplateK0pqq_EtwWriteTransfer(v24, (unsigned int)Dxgk_ReportPowerComponentState, v14, (_DWORD)this, v5, 0);
      v25 = *((_QWORD *)this + 418);
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
0x140018e54  mov     rax, rsp
0x140018e57  mov     [rax+10h], rbx
0x140018e5b  mov     [rax+20h], r9d
0x140018e5f  mov     [rax+18h], r8b
0x140018e63  push    rbp
0x140018e64  push    rsi
0x140018e65  push    rdi
0x140018e66  push    r12
0x140018e68  push    r13
0x140018e6a  push    r14
0x140018e6c  push    r15
0x140018e6e  lea     rbp, [rax-5Fh]
0x140018e72  sub     rsp, 0A0h
0x140018e79  xor     r12d, r12d
0x140018e7c  mov     r15d, edx
0x140018e7f  mov     bl, r8b
0x140018e82  mov     rdi, rcx
0x140018e85  cmp     [rcx+0D10h], r12
0x140018e8c  jz      loc_140018F42
0x140018e92  cmp     cs:bTracingEnabled, r12b
0x140018e99  jnz     loc_1400191B6
0x140018e9f  mov     r14, [rdi+0D08h]
0x140018ea6  imul    rsi, r15, 208h
0x140018ead  mov     rcx, [rsi+r14+200h]
0x140018eb5  test    rcx, rcx
0x140018eb8  jnz     loc_1400192BE
0x140018ebe  xorps   xmm0, xmm0
0x140018ec1  mov     [rbp+57h+arg_0], r12b
0x140018ec5  xor     eax, eax
0x140018ec7  lea     rcx, [r14+1F8h]
0x140018ece  add     rcx, rsi; SpinLock
0x140018ed1  mov     qword ptr [rbp+57h+LockHandle.OldIrql], rax
0x140018ed5  lea     rdx, [rbp+57h+LockHandle]; LockHandle
0x140018ed9  mov     r13b, bl
0x140018edc  movups  xmmword ptr [rbp+57h+LockHandle.LockQueue.Next], xmm0
0x140018ee0  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140018ee7  nop     dword ptr [rax+rax+00h]
0x140018eec  inc     dword ptr [rsi+r14+160h]
0x140018ef4  cmp     dword ptr [rsi+r14+160h], 1
0x140018efd  jle     short loc_140018F5E
0x140018eff  mov     bl, 1
0x140018f01  lea     rcx, [rbp+57h+LockHandle]; LockHandle
0x140018f05  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140018f0c  nop     dword ptr [rax+rax+00h]
0x140018f11  cmp     dword ptr [rsi+r14+0D0h], 7
0x140018f1a  jz      loc_1400193C0
0x140018f20  xor     r14d, r14d
0x140018f23  test    r13b, r13b
0x140018f26  jnz     loc_1400190A7
0x140018f2c  test    r12b, r12b
0x140018f2f  jnz     loc_14001940B
0x140018f35  cmp     cs:bTracingEnabled, r14b
0x140018f3c  jnz     loc_1400191E3
0x140018f42  mov     rbx, [rsp+0D0h+arg_8]
0x140018f4a  add     rsp, 0A0h
0x140018f51  pop     r15
0x140018f53  pop     r14
0x140018f55  pop     r13
0x140018f57  pop     r12
0x140018f59  pop     rdi
0x140018f5a  pop     rsi
0x140018f5b  pop     rbp
0x140018f5c  retn
0x140018f5e  xor     ecx, ecx
0x140018f60  mov     r12, 0FFFFF78000000014h
0x140018f6a  mov     bl, cl
0x140018f6c  mov     r12, [r12]
0x140018f70  cmp     [rsi+r14+168h], cl
0x140018f78  jnz     loc_140019393
0x140018f7e  mov     rax, [rsi+r14+1E0h]
0x140018f86  lea     rbx, [rdi+0ED8h]
0x140018f8d  mov     [rbp+57h+var_38], cl
0x140018f90  lea     rdx, [rbp+57h+var_50]; LockHandle
0x140018f94  mov     rcx, rbx; SpinLock
0x140018f97  mov     [rbp+57h+var_80], rax
0x140018f9b  mov     [rbp+57h+var_58], rbx
0x140018f9f  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140018fa6  nop     dword ptr [rax+rax+00h]
0x140018fab  mov     rax, gs:188h
0x140018fb4  mov     [rbx+8], rax
0x140018fb8  lea     rax, [r14+190h]
0x140018fbf  add     rax, rsi
0x140018fc2  mov     [rbp+57h+var_38], 1
0x140018fc6  xor     ebx, ebx
0x140018fc8  mov     rcx, [rax]
0x140018fcb  test    rcx, rcx
0x140018fce  jnz     loc_140019151
0x140018fd4  sub     r12, [rbp+57h+var_80]
0x140018fd8  lea     rcx, [rdi+0F20h]; SpinLock
0x140018fdf  xorps   xmm0, xmm0
0x140018fe2  lea     rdx, [rbp+57h+var_98]; LockHandle
0x140018fe6  xor     eax, eax
0x140018fe8  movups  xmmword ptr [rbp+57h+var_98.LockQueue.Next], xmm0
0x140018fec  mov     qword ptr [rbp+57h+var_98.OldIrql], rax
0x140018ff0  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x140018ff7  nop     dword ptr [rax+rax+00h]
0x140018ffc  lea     rax, [r14+1B8h]
0x140019003  add     rax, rsi
0x140019006  mov     rdx, [rax]
0x140019009  test    rdx, rdx
0x14001900c  jz      loc_140019128
0x140019012  cmp     [rdx+8], rax
0x140019016  jnz     loc_140019210
0x14001901c  mov     rcx, [rax+8]
0x140019020  cmp     [rcx], rax
0x140019023  jnz     loc_140019210
0x140019029  mov     [rcx], rdx
0x14001902c  mov     [rdx+8], rcx
0x140019030  mov     [rax], rbx
0x140019033  lea     rax, [rdi+0EF0h]
0x14001903a  cmp     [rax], rax
0x14001903d  jnz     short loc_140019058
0x14001903f  lea     rcx, [rdi+0F30h]; PKTIMER
0x140019046  call    cs:__imp_KeCancelTimer
0x14001904d  nop     dword ptr [rax+rax+00h]
0x140019052  mov     [rdi+0EBDh], bl
0x140019058  lea     rcx, [rbp+57h+var_98]; LockHandle
0x14001905c  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x140019063  nop     dword ptr [rax+rax+00h]
0x140019068  cmp     r12, [rsi+r14+1F0h]
0x140019070  jg      loc_14001939E
0x140019076  mov     bl, 1
0x140019078  xor     ecx, ecx
0x14001907a  cmp     [rbp+57h+var_38], cl
0x14001907d  jz      loc_1400193B8
0x140019083  mov     rax, [rbp+57h+var_58]
0x140019087  mov     [rbp+57h+var_38], cl
0x14001908a  mov     [rax+8], rcx
0x14001908e  lea     rcx, [rbp+57h+var_50]; LockHandle
0x140019092  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140019099  nop     dword ptr [rax+rax+00h]
0x14001909e  mov     r12b, [rbp+57h+arg_0]
0x1400190a2  jmp     loc_140018F01
0x1400190a7  cmp     [rbp+57h+arg_10], r14b
0x1400190ab  jnz     loc_140019217
0x1400190b1  cmp     cs:bTracingEnabled, r14b
0x1400190b8  jz      short loc_1400190C7
0x1400190ba  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, 2
0x1400190c1  jnz     loc_140019261
0x1400190c7  mov     esi, [rbp+57h+arg_18]
0x1400190ca  mov     edx, r15d
0x1400190cd  mov     rcx, [rdi+0D10h]
0x1400190d4  mov     r8d, esi
0x1400190d7  call    cs:__imp_PoFxActivateComponent
0x1400190de  nop     dword ptr [rax+rax+00h]
0x1400190e3  test    bl, bl
0x1400190e5  jz      loc_140018F2C
0x1400190eb  cmp     cs:bTracingEnabled, r14b
0x1400190f2  jz      short loc_140019101
0x1400190f4  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, 2
0x1400190fb  jnz     loc_1400192A0
0x140019101  mov     rcx, [rdi+0D10h]
0x140019108  test    rcx, rcx
0x14001910b  jz      loc_140018F2C
0x140019111  mov     r8d, esi
0x140019114  mov     edx, r15d
0x140019117  call    cs:__imp_PoFxIdleComponent
0x14001911e  nop     dword ptr [rax+rax+00h]
0x140019123  jmp     loc_140018F2C
0x140019128  lea     rcx, [rbp+57h+var_98]; LockHandle
0x14001912c  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x140019133  nop     dword ptr [rax+rax+00h]
0x140019138  mov     rax, [rsi+r14+1F0h]
0x140019140  cmp     r12, rax
0x140019143  jl      loc_1400193AB
0x140019149  mov     r13b, 1
0x14001914c  jmp     loc_140019078
0x140019151  cmp     [rcx+8], rax
0x140019155  jnz     loc_140019210
0x14001915b  mov     rdx, [rax+8]
0x14001915f  cmp     [rdx], rax
0x140019162  jnz     loc_140019210
0x140019168  mov     [rdx], rcx
0x14001916b  mov     [rcx+8], rdx
0x14001916f  mov     [rax], rbx
0x140019172  lea     rax, [rdi+0EC8h]
0x140019179  cmp     [rax], rax
0x14001917c  jnz     loc_140018FD4
0x140019182  cmp     [rdi+0EBCh], bl
0x140019188  jz      loc_140018FD4
0x14001918e  mov     rcx, [rdi+0CA8h]
0x140019195  xor     r8d, r8d; unsigned __int8
0x140019198  mov     [rdi+0EBCh], bl
0x14001919e  mov     rdx, [rcx+2E8h]; struct _VIDSCH_GLOBAL *
0x1400191a5  mov     rcx, [rcx+2E0h]; this
0x1400191ac  call    ?VidSchEnableLatencyToleranceTimer@VIDSCH_EXPORT@@QEAAXPEAU_VIDSCH_GLOBAL@@E@Z; VIDSCH_EXPORT::VidSchEnableLatencyToleranceTimer(_VIDSCH_GLOBAL *,uchar)
0x1400191b1  jmp     loc_140018FD4
0x1400191b6  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, 2
0x1400191bd  jz      loc_140018E9F
0x1400191c3  mov     r9, rdi
0x1400191c6  mov     dword ptr [rsp+0D0h+var_B0], r15d
0x1400191cb  lea     rdx, Dxgk_SetPowerComponentActiveCB
0x1400191d2  lea     rcx, DxgkControlGuid_Context
0x1400191d9  call    McTemplateK0pt_EtwWriteTransfer
0x1400191de  jmp     loc_140018E9F
0x1400191e3  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, 2
0x1400191ea  jz      loc_140018F42
0x1400191f0  mov     r9, rdi
0x1400191f3  mov     dword ptr [rsp+0D0h+var_B0], r15d
0x1400191f8  lea     rdx, Dxgk_SetPowerComponentActiveCBEnd
0x1400191ff  lea     rcx, DxgkControlGuid_Context
0x140019206  call    McTemplateK0pt_EtwWriteTransfer
0x14001920b  jmp     loc_140018F42
0x140019210  mov     ecx, 3
0x140019215  int     29h; Win8: RtlFailFast(ecx)
0x140019217  call    cs:__imp_KeGetCurrentIrql
0x14001921e  nop     dword ptr [rax+rax+00h]
0x140019223  cmp     al, 2
0x140019225  jnb     loc_1400193D8
0x14001922b  cmp     cs:bTracingEnabled, r14b
0x140019232  jz      short loc_14001923D
0x140019234  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, 2
0x14001923b  jnz     short loc_140019282
0x14001923d  mov     rcx, [rdi+0D10h]
0x140019244  mov     r8d, 1
0x14001924a  mov     edx, r15d
0x14001924d  call    cs:__imp_PoFxActivateComponent
0x140019254  nop     dword ptr [rax+rax+00h]
0x140019259  mov     esi, [rbp+57h+arg_18]
0x14001925c  jmp     loc_1400190E3
0x140019261  mov     dword ptr [rsp+28h], 1
0x140019269  lea     rdx, Dxgk_ReportPowerComponentState
0x140019270  mov     r9, rdi
0x140019273  mov     dword ptr [rsp+0D0h+var_B0], r15d
0x140019278  call    McTemplateK0pqq_EtwWriteTransfer
0x14001927d  jmp     loc_1400190C7
0x140019282  mov     dword ptr [rsp+28h], 1
0x14001928a  lea     rdx, Dxgk_ReportPowerComponentState
0x140019291  mov     r9, rdi
0x140019294  mov     dword ptr [rsp+0D0h+var_B0], r15d
0x140019299  call    McTemplateK0pqq_EtwWriteTransfer
0x14001929e  jmp     short loc_14001923D
0x1400192a0  mov     [rsp+28h], r14d
0x1400192a5  lea     rdx, Dxgk_ReportPowerComponentState
0x1400192ac  mov     r9, rdi
0x1400192af  mov     dword ptr [rsp+0D0h+var_B0], r15d
0x1400192b4  call    McTemplateK0pqq_EtwWriteTransfer
0x1400192b9  jmp     loc_140019101
0x1400192be  add     rcx, 88h; this
0x1400192c5  call    ?RecordActivity@DXGPOWERSTATISTICSTRANSITIONENGINE@@QEAAXXZ; DXGPOWERSTATISTICSTRANSITIONENGINE::RecordActivity(void)
0x1400192ca  mov     eax, [rdi+0C10h]
0x1400192d0  test    al, 10h
0x1400192d2  jz      short loc_1400192FA
0x1400192d4  mov     r8d, [rdi+7B0h]
0x1400192db  mov     edx, r12d
0x1400192de  cmp     edx, r8d
0x1400192e1  jnb     short loc_14001930A
0x1400192e3  mov     rax, [rdi+1140h]
0x1400192ea  mov     ecx, edx
0x1400192ec  cmp     [rax+rcx*4], r12d
0x1400192f0  jz      loc_140018EBE
0x1400192f6  inc     edx
0x1400192f8  jmp     short loc_1400192DE
0x1400192fa  mov     rax, [rdi+1140h]
0x140019301  cmp     [rax], r12d
0x140019304  jz      loc_140018EBE
0x14001930a  xorps   xmm0, xmm0
0x14001930d  lea     rcx, [rdi+1280h]; SpinLock
0x140019314  xor     eax, eax
0x140019316  lea     rdx, [rbp+57h+var_98]; LockHandle
0x14001931a  movups  xmmword ptr [rbp+57h+var_98.LockQueue.Next], xmm0
0x14001931e  mov     qword ptr [rbp+57h+var_98.OldIrql], rax
0x140019322  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140019329  nop     dword ptr [rax+rax+00h]
0x14001932e  mov     rax, [rsi+r14+200h]
0x140019336  mov     byte ptr [rax+0F0h], 1
0x14001933d  cmp     [rdi+1288h], r12b
0x140019344  jnz     short loc_14001937E
0x140019346  mov     byte ptr [rdi+1288h], 1
0x14001934d  lock inc qword ptr [rdi+18h]
0x140019352  lea     r8, [rdi+1240h]; Dpc
0x140019359  mov     qword ptr [rdi+11F8h], 0FFFFFFFFFFFFFFFFh
0x140019364  lea     rcx, [rdi+1200h]; Timer
0x14001936b  mov     rdx, 0FFFFFFFFFFFE2B40h; DueTime
0x140019372  call    cs:__imp_KeSetTimer
0x140019379  nop     dword ptr [rax+rax+00h]
0x14001937e  lea     rcx, [rbp+57h+var_98]; LockHandle
0x140019382  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140019389  nop     dword ptr [rax+rax+00h]
0x14001938e  jmp     loc_140018EBE
0x140019393  mov     r13b, cl
0x140019396  mov     r12b, 1
0x140019399  jmp     loc_140018F01
0x14001939e  mov     [rsi+r14+1D8h], rbx
0x1400193a6  jmp     loc_140019076
0x1400193ab  mov     [rsi+r14+1D8h], rax
0x1400193b3  jmp     loc_140019149
0x1400193b8  mov     r12b, cl
0x1400193bb  jmp     loc_140018F01
0x1400193c0  mov     edx, [rsi+r14+4]; unsigned int
0x1400193c5  mov     r9b, 1; char
0x1400193c8  xor     r8d, r8d; unsigned int
0x1400193cb  mov     rcx, rdi; void *
0x1400193ce  call    DxgkNotifySharedPowerGraphicsFStateTransition
0x1400193d3  jmp     loc_140018F20
0x1400193d8  xor     ecx, ecx
0x1400193da  mov     [rsp+28h], r14
0x1400193df  mov     r9, rdi
0x1400193e2  mov     [rsp+0D0h+var_B0], r14
0x1400193e7  mov     edx, 113h
  ... truncated ...
```
