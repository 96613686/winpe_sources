# DXGADAPTER::PowerRuntimeComponentIdleStateCallback_Worker(ulong,ulong,uchar)

- ea: `0x140012e10`
- end: `0x140013641`
- name: `?PowerRuntimeComponentIdleStateCallback_Worker@DXGADAPTER@@QEAAXKKE@Z`
- size: `2097`
- prototype: `void __fastcall(DXGADAPTER *__hidden this, unsigned int, unsigned int, unsigned __int8)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1401ee148`

## callees

- `0x140012e10`
- `0x140013e40`
- `0x14001b9c0`
- `0x14001bffc`
- `0x14001d1a0`
- `0x14001d214`
- `0x14001d884`
- `0x140079e08`
- `0x1400a0bd0`
- `0x1400a0cb0`
- `0x140317c80`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x1400130e8`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x1400130e8`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140013120`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140013120`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140013630`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140013630`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140013624`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140013624`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140012fa9`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140012fa9`
- `ntoskrnl!PoFxCompleteIdleState` at `0x140013060`
- `ntoskrnl!PoFxCompleteIdleState` at `0x14001317b`
- `ntoskrnl!PoFxCompleteIdleState` at `0x140013060`
- `ntoskrnl!PoFxCompleteIdleState` at `0x14001317b`
- `ntoskrnl!KeGetCurrentIrql` at `0x140012f27`
- `ntoskrnl!KeGetCurrentIrql` at `0x140012f42`
- `ntoskrnl!KeGetCurrentIrql` at `0x140012fb5`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400130c8`
- `ntoskrnl!KeGetCurrentIrql` at `0x140013107`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400133b8`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001357f`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400135ad`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400135bf`
- `ntoskrnl!KeGetCurrentIrql` at `0x140012f27`
- `ntoskrnl!KeGetCurrentIrql` at `0x140012f42`
- `ntoskrnl!KeGetCurrentIrql` at `0x140012fb5`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400130c8`
- `ntoskrnl!KeGetCurrentIrql` at `0x140013107`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400133b8`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001357f`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400135ad`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400135bf`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400131e4`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400131e4`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400131bd`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400131bd`
- `watchdog!WdLogSingleEntry0` at `0x140013338`
- `watchdog!WdLogSingleEntry0` at `0x140013473`
- `watchdog!WdLogSingleEntry0` at `0x140013500`
- `watchdog!WdLogSingleEntry0` at `0x140013338`
- `watchdog!WdLogSingleEntry0` at `0x140013473`
- `watchdog!WdLogSingleEntry0` at `0x140013500`
- `watchdog!WdLogSingleEntry5` at `0x140013273`
- `watchdog!WdLogSingleEntry5` at `0x1400133e6`
- `watchdog!WdLogSingleEntry5` at `0x1400135ed`
- `watchdog!WdLogSingleEntry5` at `0x140013273`
- `watchdog!WdLogSingleEntry5` at `0x1400133e6`
- `watchdog!WdLogSingleEntry5` at `0x1400135ed`
- `watchdog!WdLogSingleEntry1` at `0x14001340c`
- `watchdog!WdLogSingleEntry1` at `0x14001340c`

## pseudocode

```c
void __fastcall DXGADAPTER::PowerRuntimeComponentIdleStateCallback_Worker(
        DXGADAPTER *this,
        unsigned int a2,
        __int64 a3,
        char a4)
{
  __int64 v5; // r13
  unsigned int v6; // r15d
  __int64 v8; // rbx
  __int64 v9; // rdi
  char v10; // si
  _BYTE *v11; // r14
  struct DXGTHREAD *v12; // rsi
  __int64 v13; // rcx
  char v15; // si
  __int64 v16; // rcx
  unsigned int v17; // r12d
  __int64 v18; // rbx
  char v19; // r13
  __int64 *i; // r14
  __int64 v21; // rax
  struct DXGTHREAD *Current; // rax
  int v23; // eax
  struct DXGTHREAD *v24; // rax
  KIRQL v25; // al
  KIRQL v26; // al
  KIRQL CurrentIrql; // [rsp+50h] [rbp-B8h]
  KIRQL v28; // [rsp+50h] [rbp-B8h]
  unsigned int v29; // [rsp+54h] [rbp-B4h]
  int v30; // [rsp+54h] [rbp-B4h]
  int v31; // [rsp+58h] [rbp-B0h]
  unsigned int v32; // [rsp+5Ch] [rbp-ACh]
  struct DXGTHREAD *v33; // [rsp+60h] [rbp-A8h]
  __int64 v34; // [rsp+60h] [rbp-A8h]
  struct DXGTHREAD *v35; // [rsp+68h] [rbp-A0h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+70h] [rbp-98h] BYREF
  __int64 v37; // [rsp+88h] [rbp-80h]
  _BYTE v38[8]; // [rsp+90h] [rbp-78h] BYREF
  struct _KAPC_STATE ApcState; // [rsp+98h] [rbp-70h] BYREF

  v5 = a2;
  v6 = a3;
  if ( *((_DWORD *)this + 50) == 1 )
  {
    if ( bTracingEnabled && (Microsoft_Windows_DxgKrnlEnableBits & 0x20000) != 0 )
      McTemplateK0pqq_EtwWriteTransfer(
        (_DWORD)this,
        (unsigned int)Dxgk_SetPowerComponentFState,
        a3,
        (_DWORD)this,
        a2,
        a3);
    v8 = *((_QWORD *)this + 419);
    v9 = 520 * v5;
    if ( !a4 && *(_BYTE *)(v9 + v8 + 360) )
    {
      v15 = 0;
      v11 = (_BYTE *)(v9 + v8 + 359);
    }
    else
    {
      if ( (*((int *)this + 716) >= 0x2000 || *((_BYTE *)this + 3164)) && *(_DWORD *)(v9 + v8 + 208) == 3 )
      {
        v10 = 0;
      }
      else
      {
        v10 = 1;
        *(_DWORD *)(v9 + v8 + 344) = v6;
      }
      v11 = (_BYTE *)(v9 + v8 + 359);
      *v11 = 1;
      if ( v6 )
      {
        v21 = *(_QWORD *)(v9 + v8 + 512);
        v34 = v21;
        if ( v21 )
        {
          memset(&LockHandle, 0, sizeof(LockHandle));
          KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v21 + 160), &LockHandle);
          *(_BYTE *)(v34 + 224) = 1;
          *(_DWORD *)(v34 + 196) = -1;
          KeReleaseInStackQueuedSpinLock(&LockHandle);
        }
      }
      if ( v10 )
      {
        v12 = 0;
        v29 = *(_DWORD *)(v9 + v8 + 4);
        v32 = -1;
        v37 = qword_1401604F0 & 2;
        v33 = 0;
        if ( (qword_1401604F0 & 2) != 0 )
        {
          v32 = 5124;
          if ( (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
            McTemplateK0q_EtwWriteTransfer(this, EventProfilerEnter, a3, 5124);
        }
        if ( KeGetCurrentIrql() < 2u )
        {
          Current = DXGTHREAD::GetCurrent();
          v33 = Current;
          v12 = Current;
          if ( Current )
          {
            if ( *((int *)Current + 11) < 0 )
            {
              WdLogSingleEntry0(1);
              WdLogGlobalForLineNumber = 183;
              DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"m_ProfilerEntryCount >= 0", 183, 0, 0, 0, 0);
            }
            v23 = *((_DWORD *)v12 + 11);
            if ( !v23 )
              *((_DWORD *)v12 + 12) = 5124;
            *((_DWORD *)v12 + 11) = v23 + 1;
          }
        }
        _InterlockedIncrement((volatile signed __int32 *)this + 1233);
        CurrentIrql = KeGetCurrentIrql();
        v35 = 0;
        if ( CurrentIrql < 2u && (v24 = DXGTHREAD::GetCurrent(), (v35 = v24) != 0) )
          v31 = *((_DWORD *)v24 + 10);
        else
          v31 = 0;
        DXGVALIDATIONPROCESSATTACH::DXGVALIDATIONPROCESSATTACH((DXGVALIDATIONPROCESSATTACH *)v38, this);
        v30 = (*((__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))this + 105))(*((_QWORD *)this + 36), v29, v6);
        if ( v38[0] )
          KeUnstackDetachProcess(&ApcState);
        if ( CurrentIrql != KeGetCurrentIrql() )
        {
          v25 = KeGetCurrentIrql();
          WdLogSingleEntry5(0, 275, 16, this, CurrentIrql, v25);
          WdLogGlobalForLineNumber = 2579;
        }
        if ( v35 )
        {
          v13 = *((int *)v35 + 10);
          if ( (_DWORD)v13 != v31 )
          {
            WdLogSingleEntry5(0, 275, 38, v13, v31, 0);
            WdLogGlobalForLineNumber = 73;
          }
        }
        _InterlockedDecrement((volatile signed __int32 *)this + 1233);
        if ( v30 != -1071775466 && v30 )
        {
          WdLogSingleEntry1(2, v30);
          WdLogGlobalForLineNumber = 2581;
          DxgkLogInternalTriageEvent(
            0,
            0x40000,
            -1,
            (unsigned int)L"Driver returned an invalid NTSTATUS code: 0x%I64x",
            v30,
            0,
            0,
            0,
            0);
          v12 = v33;
        }
        if ( v12 )
        {
          if ( *((int *)v12 + 11) <= 0 )
          {
            WdLogSingleEntry0(1);
            WdLogGlobalForLineNumber = 193;
            DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"m_ProfilerEntryCount > 0", 193, 0, 0, 0, 0);
          }
          if ( (*((_DWORD *)v12 + 11))-- == 1 )
            *((_DWORD *)v12 + 12) = -1;
        }
        if ( v37 && (Microsoft_Windows_DxgKrnlEnableBits & 0x10000) != 0 )
          McTemplateK0q_EtwWriteTransfer(v13, EventProfilerExit, a3, v32);
      }
      v15 = 1;
    }
    if ( bTracingEnabled && (Microsoft_Windows_DxgKrnlEnableBits & 0x20000) != 0 )
      McTemplateK0pt_EtwWriteTransfer(&DxgkControlGuid_Context, Dxgk_SetPowerComponentFStateEnd, a3, this, v5);
    if ( (*(_DWORD *)(v9 + v8 + 216) & 2) == 0 )
    {
      *v11 = 0;
      if ( !a4 )
        PoFxCompleteIdleState(*((_QWORD *)this + 420), (unsigned int)v5);
      if ( v15 )
      {
        if ( !v6 )
        {
          v16 = *(_QWORD *)(v9 + v8 + 512);
          if ( v16 )
            DXGPOWERSTATISTICSTRANSITIONENGINE::RecordLeavingIdleFState((DXGPOWERSTATISTICSTRANSITIONENGINE *)(v16 + 136));
        }
        if ( *(_DWORD *)(v9 + v8 + 208) == 7 )
        {
          v17 = *(_DWORD *)(v9 + v8 + 4);
          if ( !*(_QWORD *)&DXGGLOBAL::m_pGlobal )
          {
            WdLogSingleEntry0(1);
            WdLogGlobalForLineNumber = 2650;
            DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"m_pGlobal != NULL", 2650, 0, 0, 0, 0);
          }
          v18 = *(_QWORD *)&DXGGLOBAL::m_pGlobal;
          v19 = 0;
          memset(&LockHandle, 0, sizeof(LockHandle));
          if ( KeGetCurrentIrql() < 2u )
          {
            if ( *(struct _KTHREAD **)(v18 + 1784) != KeGetCurrentThread() )
            {
              DXGPUSHLOCK::AcquireShared((DXGPUSHLOCK *)(v18 + 1776));
              v19 = 1;
            }
          }
          else
          {
            KeAcquireInStackQueuedSpinLockAtDpcLevel((PKSPIN_LOCK)(v18 + 1768), &LockHandle);
          }
          for ( i = *(__int64 **)(v18 + 1808); i != (__int64 *)(v18 + 1808) && i; i = (__int64 *)*i )
          {
            if ( (DXGADAPTER *)i[4] == this )
            {
              if ( i[7] )
              {
                v28 = KeGetCurrentIrql();
                ((void (__fastcall *)(DXGADAPTER *, _QWORD, _QWORD, _QWORD, __int64))i[7])(this, v17, v6, 0, i[3]);
                if ( v28 != KeGetCurrentIrql() )
                {
                  v26 = KeGetCurrentIrql();
                  WdLogSingleEntry5(0, 275, 16, v18, v28, v26);
                  WdLogGlobalForLineNumber = 7174;
                }
              }
            }
          }
          if ( KeGetCurrentIrql() < 2u )
          {
            if ( v19 )
            {
              _InterlockedDecrement((volatile signed __int32 *)(v18 + 1792));
              ExReleasePushLockSharedEx(v18 + 1776, 0);
              KeLeaveCriticalRegion();
            }
          }
          else
          {
            KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
          }
        }
      }
    }
  }
  else if ( !a4 )
  {
    PoFxCompleteIdleState(*((_QWORD *)this + 420), a2);
  }
}

```

## disassembly

```asm
0x140012e10  mov     r11, rsp
0x140012e13  push    rbp
0x140012e14  push    r12
0x140012e16  push    r13
0x140012e18  push    r15
0x140012e1a  sub     rsp, 0E8h
0x140012e21  mov     rax, cs:__security_cookie
0x140012e28  xor     rax, rsp
0x140012e2b  mov     [rsp+108h+var_40], rax
0x140012e33  mov     eax, [rcx+0C8h]
0x140012e39  movzx   r12d, r9b
0x140012e3d  mov     r13d, edx
0x140012e40  mov     r15d, r8d
0x140012e43  mov     rbp, rcx
0x140012e46  cmp     eax, 1
0x140012e49  jnz     loc_14001316C
0x140012e4f  cmp     cs:bTracingEnabled, 0
0x140012e56  mov     [r11+20h], rbx
0x140012e5a  mov     [r11-30h], rdi
0x140012e5e  jz      short loc_140012E6D
0x140012e60  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, 2
0x140012e67  jnz     loc_1400132A9
0x140012e6d  mov     rbx, [rbp+0D18h]
0x140012e74  imul    rdi, r13, 208h
0x140012e7b  mov     [rsp+108h+var_28], rsi
0x140012e83  mov     [rsp+108h+var_38], r14
0x140012e8b  test    r12b, r12b
0x140012e8e  jnz     short loc_140012E9E
0x140012e90  cmp     [rdi+rbx+168h], r12b
0x140012e98  jnz     loc_140013226
0x140012e9e  cmp     dword ptr [rbp+0B30h], 2000h
0x140012ea8  jl      loc_140013297
0x140012eae  cmp     dword ptr [rdi+rbx+0D0h], 3
0x140012eb6  jz      loc_140013314
0x140012ebc  mov     sil, 1
0x140012ebf  mov     [rdi+rbx+158h], r15d
0x140012ec7  lea     r14, [rbx+167h]
0x140012ece  add     r14, rdi
0x140012ed1  mov     byte ptr [r14], 1
0x140012ed5  test    r15d, r15d
0x140012ed8  jnz     loc_140013189
0x140012ede  test    sil, sil
0x140012ee1  jz      loc_140013025
0x140012ee7  mov     eax, [rdi+rbx+4]
0x140012eeb  xor     esi, esi
0x140012eed  mov     [rsp+108h+var_B4], eax
0x140012ef1  mov     rax, cs:qword_1401604F0
0x140012ef8  and     eax, 2
0x140012efb  mov     [rsp+108h+var_AC], 0FFFFFFFFh
0x140012f03  mov     [rsp+108h+var_80], rax
0x140012f0b  mov     [rsp+108h+var_A8], rsi
0x140012f10  jz      short loc_140012F27
0x140012f12  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, 1
0x140012f19  mov     [rsp+108h+var_AC], 1404h
0x140012f21  jnz     loc_14001331C
0x140012f27  call    cs:__imp_KeGetCurrentIrql
0x140012f2e  nop     dword ptr [rax+rax+00h]
0x140012f33  cmp     al, 2
0x140012f35  jb      loc_1400131F5
0x140012f3b  lock inc dword ptr [rbp+1344h]
0x140012f42  call    cs:__imp_KeGetCurrentIrql
0x140012f49  nop     dword ptr [rax+rax+00h]
0x140012f4e  xor     ecx, ecx
0x140012f50  mov     [rsp+108h+var_B8], al
0x140012f54  mov     [rsp+108h+var_A0], rcx
0x140012f59  cmp     al, 2
0x140012f5b  jb      loc_140013399
0x140012f61  mov     [rsp+108h+var_B0], 0
0x140012f69  mov     rdx, rbp; struct DXGADAPTER *
0x140012f6c  lea     rcx, [rsp+108h+var_78]; this
0x140012f74  call    ??0DXGVALIDATIONPROCESSATTACH@@QEAA@PEAVDXGADAPTER@@@Z; DXGVALIDATIONPROCESSATTACH::DXGVALIDATIONPROCESSATTACH(DXGADAPTER *)
0x140012f79  mov     rax, [rbp+348h]
0x140012f80  mov     r8d, r15d
0x140012f83  mov     edx, [rsp+108h+var_B4]
0x140012f87  mov     rcx, [rbp+120h]
0x140012f8e  call    _guard_dispatch_icall
0x140012f93  cmp     [rsp+108h+var_78], 0
0x140012f9b  mov     [rsp+108h+var_B4], eax
0x140012f9f  jz      short loc_140012FB5
0x140012fa1  lea     rcx, [rsp+108h+ApcState]; ApcState
0x140012fa9  call    cs:__imp_KeUnstackDetachProcess
0x140012fb0  nop     dword ptr [rax+rax+00h]
0x140012fb5  call    cs:__imp_KeGetCurrentIrql
0x140012fbc  nop     dword ptr [rax+rax+00h]
0x140012fc1  cmp     [rsp+108h+var_B8], al
0x140012fc5  jnz     loc_1400133B8
0x140012fcb  mov     rax, [rsp+108h+var_A0]
0x140012fd0  test    rax, rax
0x140012fd3  jnz     loc_140013244
0x140012fd9  lock dec dword ptr [rbp+1344h]
0x140012fe0  movsxd  rax, [rsp+108h+var_B4]
0x140012fe5  cmp     eax, 0C01E0116h
0x140012fea  jz      short loc_140012FF4
0x140012fec  test    eax, eax
0x140012fee  jnz     loc_140013401
0x140012ff4  test    rsi, rsi
0x140012ff7  jz      short loc_14001300D
0x140012ff9  cmp     dword ptr [rsi+2Ch], 0
0x140012ffd  jle     loc_14001346E
0x140013003  sub     dword ptr [rsi+2Ch], 1
0x140013007  jz      loc_140013238
0x14001300d  cmp     [rsp+108h+var_80], 0
0x140013016  jz      short loc_140013025
0x140013018  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, 1
0x14001301f  jnz     loc_1400134D4
0x140013025  mov     sil, 1
0x140013028  cmp     cs:bTracingEnabled, 0
0x14001302f  jz      short loc_14001303E
0x140013031  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, 2
0x140013038  jnz     loc_1400132C7
0x14001303e  mov     eax, [rdi+rbx+0D8h]
0x140013045  test    al, 2
0x140013047  jnz     loc_14001312C
0x14001304d  mov     byte ptr [r14], 0
0x140013051  test    r12b, r12b
0x140013054  jnz     short loc_14001306C
0x140013056  mov     rcx, [rbp+0D20h]
0x14001305d  mov     edx, r13d
0x140013060  call    cs:__imp_PoFxCompleteIdleState
0x140013067  nop     dword ptr [rax+rax+00h]
0x14001306c  test    sil, sil
0x14001306f  jz      loc_14001312C
0x140013075  test    r15d, r15d
0x140013078  jnz     short loc_14001308B
0x14001307a  mov     rcx, [rdi+rbx+200h]
0x140013082  test    rcx, rcx
0x140013085  jnz     loc_1400134EA
0x14001308b  cmp     dword ptr [rdi+rbx+0D0h], 7
0x140013093  jnz     loc_14001312C
0x140013099  cmp     cs:?m_pGlobal@DXGGLOBAL@@0PEAV1@EA, 0; DXGGLOBAL * DXGGLOBAL::m_pGlobal
0x1400130a1  mov     r12d, [rdi+rbx+4]
0x1400130a6  jz      loc_1400134FB
0x1400130ac  mov     rbx, cs:?m_pGlobal@DXGGLOBAL@@0PEAV1@EA; DXGGLOBAL * DXGGLOBAL::m_pGlobal
0x1400130b3  xorps   xmm0, xmm0
0x1400130b6  xor     eax, eax
0x1400130b8  xor     r13b, r13b
0x1400130bb  movups  xmmword ptr [rsp+108h+LockHandle.LockQueue.Next], xmm0
0x1400130c0  mov     qword ptr [rsp+108h+LockHandle.OldIrql], rax
0x1400130c8  call    cs:__imp_KeGetCurrentIrql
0x1400130cf  nop     dword ptr [rax+rax+00h]
0x1400130d4  cmp     al, 2
0x1400130d6  jb      loc_1400132E7
0x1400130dc  lea     rcx, [rbx+6E8h]; SpinLock
0x1400130e3  lea     rdx, [rsp+108h+LockHandle]; LockHandle
0x1400130e8  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x1400130ef  nop     dword ptr [rax+rax+00h]
0x1400130f4  lea     rdi, [rbx+710h]
0x1400130fb  mov     r14, [rdi]
0x1400130fe  cmp     r14, rdi
0x140013101  jnz     loc_140013561
0x140013107  call    cs:__imp_KeGetCurrentIrql
0x14001310e  nop     dword ptr [rax+rax+00h]
0x140013113  cmp     al, 2
0x140013115  jb      loc_14001360B
0x14001311b  lea     rcx, [rsp+108h+LockHandle]; LockHandle
0x140013120  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x140013127  nop     dword ptr [rax+rax+00h]
0x14001312c  mov     rsi, [rsp+108h+var_28]
0x140013134  mov     r14, [rsp+108h+var_38]
0x14001313c  mov     rbx, [rsp+108h+arg_18]
0x140013144  mov     rdi, [rsp+108h+var_30]
0x14001314c  mov     rcx, [rsp+108h+var_40]
0x140013154  xor     rcx, rsp; StackCookie
0x140013157  call    __security_check_cookie
0x14001315c  add     rsp, 0E8h
0x140013163  pop     r15
0x140013165  pop     r13
0x140013167  pop     r12
0x140013169  pop     rbp
0x14001316a  retn
0x14001316c  test    r12b, r12b
0x14001316f  jnz     short loc_14001314C
0x140013171  mov     rcx, [rcx+0D20h]
0x140013178  mov     edx, r13d
0x14001317b  call    cs:__imp_PoFxCompleteIdleState
0x140013182  nop     dword ptr [rax+rax+00h]
0x140013187  jmp     short loc_14001314C
0x140013189  mov     rax, [rdi+rbx+200h]
0x140013191  mov     [rsp+108h+var_A8], rax
0x140013196  test    rax, rax
0x140013199  jz      loc_140012EDE
0x14001319f  xor     ecx, ecx
0x1400131a1  lea     rdx, [rsp+108h+LockHandle]; LockHandle
0x1400131a6  mov     qword ptr [rsp+108h+LockHandle.OldIrql], rcx
0x1400131ae  xorps   xmm0, xmm0
0x1400131b1  lea     rcx, [rax+0A0h]; SpinLock
0x1400131b8  movups  xmmword ptr [rsp+108h+LockHandle.LockQueue.Next], xmm0
0x1400131bd  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400131c4  nop     dword ptr [rax+rax+00h]
0x1400131c9  mov     rax, [rsp+108h+var_A8]
0x1400131ce  lea     rcx, [rsp+108h+LockHandle]; LockHandle
0x1400131d3  mov     byte ptr [rax+0E0h], 1
0x1400131da  mov     dword ptr [rax+0C4h], 0FFFFFFFFh
0x1400131e4  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400131eb  nop     dword ptr [rax+rax+00h]
0x1400131f0  jmp     loc_140012EDE
0x1400131f5  call    ?GetCurrent@DXGTHREAD@@SAPEAV1@XZ; DXGTHREAD::GetCurrent(void)
0x1400131fa  mov     [rsp+108h+var_A8], rax
0x1400131ff  mov     rsi, rax
0x140013202  test    rax, rax
0x140013205  jz      loc_140012F3B
0x14001320b  cmp     dword ptr [rax+2Ch], 0
0x14001320f  jl      loc_140013333
0x140013215  mov     eax, [rsi+2Ch]
0x140013218  test    eax, eax
0x14001321a  jz      short loc_14001328E
0x14001321c  inc     eax
0x14001321e  mov     [rsi+2Ch], eax
0x140013221  jmp     loc_140012F3B
0x140013226  xor     sil, sil
0x140013229  lea     r14, [rbx+167h]
0x140013230  add     r14, rdi
0x140013233  jmp     loc_140013028
0x140013238  mov     dword ptr [rsi+30h], 0FFFFFFFFh
0x14001323f  jmp     loc_14001300D
0x140013244  movsxd  rcx, dword ptr [rax+28h]
0x140013248  movsxd  rax, [rsp+108h+var_B0]
0x14001324d  cmp     ecx, eax
0x14001324f  jz      loc_140012FD9
0x140013255  mov     r9, rcx
0x140013258  mov     [rsp+108h+var_E0], 0
0x140013261  xor     ecx, ecx
0x140013263  mov     [rsp+108h+var_E8], rax
0x140013268  mov     edx, 113h
0x14001326d  mov     r8d, 26h ; '&'
0x140013273  call    cs:__imp_WdLogSingleEntry5
0x14001327a  nop     dword ptr [rax+rax+00h]
0x14001327f  mov     cs:WdLogGlobalForLineNumber, 49h ; 'I'
0x140013289  jmp     loc_140012FD9
0x14001328e  mov     dword ptr [rsi+30h], 1404h
0x140013295  jmp     short loc_14001321C
0x140013297  cmp     byte ptr [rbp+0C5Ch], 0
0x14001329e  jnz     loc_140012EAE
0x1400132a4  jmp     loc_140012EBC
0x1400132a9  mov     dword ptr [rsp+108h+var_E0], r15d
0x1400132ae  lea     rdx, Dxgk_SetPowerComponentFState
0x1400132b5  mov     r9, rbp
0x1400132b8  mov     dword ptr [rsp+108h+var_E8], r13d
0x1400132bd  call    McTemplateK0pqq_EtwWriteTransfer
0x1400132c2  jmp     loc_140012E6D
0x1400132c7  mov     r9, rbp
0x1400132ca  mov     dword ptr [rsp+108h+var_E8], r13d
0x1400132cf  lea     rdx, Dxgk_SetPowerComponentFStateEnd
0x1400132d6  lea     rcx, DxgkControlGuid_Context
0x1400132dd  call    McTemplateK0pt_EtwWriteTransfer
0x1400132e2  jmp     loc_14001303E
0x1400132e7  mov     rcx, [rbx+6F8h]
0x1400132ee  mov     rax, gs:188h
0x1400132f7  cmp     rcx, rax
0x1400132fa  jz      loc_1400130F4
0x140013300  lea     rcx, [rbx+6F0h]; this
0x140013307  call    ?AcquireShared@DXGPUSHLOCK@@QEAAXXZ; DXGPUSHLOCK::AcquireShared(void)
0x14001330c  mov     r13b, 1
0x14001330f  jmp     loc_1400130F4
0x140013314  xor     sil, sil
0x140013317  jmp     loc_140012EC7
0x14001331c  mov     r9d, 1404h
0x140013322  lea     rdx, EventProfilerEnter
0x140013329  call    McTemplateK0q_EtwWriteTransfer
0x14001332e  jmp     loc_140012F27
0x140013333  mov     ecx, 1
0x140013338  call    cs:__imp_WdLogSingleEntry0
0x14001333f  nop     dword ptr [rax+rax+00h]
0x140013344  mov     [rsp+108h+var_C8], 0
0x14001334d  lea     r9, aMProfilerentry; "m_ProfilerEntryCount >= 0"
0x140013354  mov     [rsp+108h+var_D0], 0
0x14001335d  mov     edx, 40002h
0x140013362  mov     [rsp+108h+var_D8], 0
0x14001336b  xor     ecx, ecx
0x14001336d  mov     [rsp+108h+var_E0], 0
0x140013376  mov     r8d, 0FFFFFFFFh
0x14001337c  mov     [rsp+108h+var_E8], 0B7h
0x140013385  mov     cs:WdLogGlobalForLineNumber, 0B7h
0x14001338f  call    DxgkLogInternalTriageEvent
0x140013394  jmp     loc_140013215
0x140013399  call    ?GetCurrent@DXGTHREAD@@SAPEAV1@XZ; DXGTHREAD::GetCurrent(void)
0x14001339e  mov     [rsp+108h+var_A0], rax
0x1400133a3  test    rax, rax
0x1400133a6  jz      loc_140012F61
0x1400133ac  mov     eax, [rax+28h]
0x1400133af  mov     [rsp+108h+var_B0], eax
0x1400133b3  jmp     loc_140012F69
0x1400133b8  call    cs:__imp_KeGetCurrentIrql
0x1400133bf  nop     dword ptr [rax+rax+00h]
0x1400133c4  movzx   ecx, [rsp+108h+var_B8]
0x1400133c9  mov     r9, rbp
0x1400133cc  movzx   eax, al
0x1400133cf  mov     edx, 113h
0x1400133d4  mov     [rsp+108h+var_E0], rax
0x1400133d9  mov     r8d, 10h
0x1400133df  mov     [rsp+108h+var_E8], rcx
0x1400133e4  xor     ecx, ecx
0x1400133e6  call    cs:__imp_WdLogSingleEntry5
0x1400133ed  nop     dword ptr [rax+rax+00h]
0x1400133f2  mov     cs:WdLogGlobalForLineNumber, 0A13h
0x1400133fc  jmp     loc_140012FCB
0x140013401  mov     rdx, rax
0x140013404  mov     ecx, 2
0x140013409  mov     rsi, rax
0x14001340c  call    cs:__imp_WdLogSingleEntry1
  ... truncated ...
```
