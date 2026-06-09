# DXGADAPTER::PowerRuntimeComponentIdleStateCallback_Worker(ulong,ulong,uchar)

- ea: `0x140012c50`
- end: `0x140013481`
- name: `?PowerRuntimeComponentIdleStateCallback_Worker@DXGADAPTER@@QEAAXKKE@Z`
- size: `2097`
- prototype: `void __fastcall(DXGADAPTER *__hidden this, unsigned int, unsigned int, unsigned __int8)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1401ebd78`

## callees

- `0x140012c50`
- `0x140013c80`
- `0x14001b890`
- `0x14001becc`
- `0x14001d070`
- `0x14001d0e4`
- `0x14001d6b4`
- `0x1400796f8`
- `0x1400a0100`
- `0x1400a01e0`
- `0x140310f10`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140012f28`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140012f28`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140012f60`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140012f60`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140013470`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140013470`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140013464`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140013464`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140012de9`
- `ntoskrnl!KeUnstackDetachProcess` at `0x140012de9`
- `ntoskrnl!PoFxCompleteIdleState` at `0x140012ea0`
- `ntoskrnl!PoFxCompleteIdleState` at `0x140012fbb`
- `ntoskrnl!PoFxCompleteIdleState` at `0x140012ea0`
- `ntoskrnl!PoFxCompleteIdleState` at `0x140012fbb`
- `ntoskrnl!KeGetCurrentIrql` at `0x140012d67`
- `ntoskrnl!KeGetCurrentIrql` at `0x140012d82`
- `ntoskrnl!KeGetCurrentIrql` at `0x140012df5`
- `ntoskrnl!KeGetCurrentIrql` at `0x140012f08`
- `ntoskrnl!KeGetCurrentIrql` at `0x140012f47`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400131f8`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400133bf`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400133ed`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400133ff`
- `ntoskrnl!KeGetCurrentIrql` at `0x140012d67`
- `ntoskrnl!KeGetCurrentIrql` at `0x140012d82`
- `ntoskrnl!KeGetCurrentIrql` at `0x140012df5`
- `ntoskrnl!KeGetCurrentIrql` at `0x140012f08`
- `ntoskrnl!KeGetCurrentIrql` at `0x140012f47`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400131f8`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400133bf`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400133ed`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400133ff`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140013024`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140013024`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140012ffd`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140012ffd`
- `watchdog!WdLogSingleEntry0` at `0x140013178`
- `watchdog!WdLogSingleEntry0` at `0x1400132b3`
- `watchdog!WdLogSingleEntry0` at `0x140013340`
- `watchdog!WdLogSingleEntry0` at `0x140013178`
- `watchdog!WdLogSingleEntry0` at `0x1400132b3`
- `watchdog!WdLogSingleEntry0` at `0x140013340`
- `watchdog!WdLogSingleEntry5` at `0x1400130b3`
- `watchdog!WdLogSingleEntry5` at `0x140013226`
- `watchdog!WdLogSingleEntry5` at `0x14001342d`
- `watchdog!WdLogSingleEntry5` at `0x1400130b3`
- `watchdog!WdLogSingleEntry5` at `0x140013226`
- `watchdog!WdLogSingleEntry5` at `0x14001342d`
- `watchdog!WdLogSingleEntry1` at `0x14001324c`
- `watchdog!WdLogSingleEntry1` at `0x14001324c`

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
    v8 = *((_QWORD *)this + 417);
    v9 = 520 * v5;
    if ( !a4 && *(_BYTE *)(v9 + v8 + 360) )
    {
      v15 = 0;
      v11 = (_BYTE *)(v9 + v8 + 359);
    }
    else
    {
      if ( (*((int *)this + 712) >= 0x2000 || *((_BYTE *)this + 3148)) && *(_DWORD *)(v9 + v8 + 208) == 3 )
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
        v37 = qword_14015C500 & 2;
        v33 = 0;
        if ( (qword_14015C500 & 2) != 0 )
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
        _InterlockedIncrement((volatile signed __int32 *)this + 1229);
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
        _InterlockedDecrement((volatile signed __int32 *)this + 1229);
        if ( v30 != -1071775466 && v30 )
        {
          WdLogSingleEntry1(2);
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
        PoFxCompleteIdleState(*((_QWORD *)this + 418), (unsigned int)v5);
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
    PoFxCompleteIdleState(*((_QWORD *)this + 418), a2);
  }
}

```

## disassembly

```asm
0x140012c50  mov     r11, rsp
0x140012c53  push    rbp
0x140012c54  push    r12
0x140012c56  push    r13
0x140012c58  push    r15
0x140012c5a  sub     rsp, 0E8h
0x140012c61  mov     rax, cs:__security_cookie
0x140012c68  xor     rax, rsp
0x140012c6b  mov     [rsp+108h+var_40], rax
0x140012c73  mov     eax, [rcx+0C8h]
0x140012c79  movzx   r12d, r9b
0x140012c7d  mov     r13d, edx
0x140012c80  mov     r15d, r8d
0x140012c83  mov     rbp, rcx
0x140012c86  cmp     eax, 1
0x140012c89  jnz     loc_140012FAC
0x140012c8f  cmp     cs:bTracingEnabled, 0
0x140012c96  mov     [r11+20h], rbx
0x140012c9a  mov     [r11-30h], rdi
0x140012c9e  jz      short loc_140012CAD
0x140012ca0  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, 2
0x140012ca7  jnz     loc_1400130E9
0x140012cad  mov     rbx, [rbp+0D08h]
0x140012cb4  imul    rdi, r13, 208h
0x140012cbb  mov     [rsp+108h+var_28], rsi
0x140012cc3  mov     [rsp+108h+var_38], r14
0x140012ccb  test    r12b, r12b
0x140012cce  jnz     short loc_140012CDE
0x140012cd0  cmp     [rdi+rbx+168h], r12b
0x140012cd8  jnz     loc_140013066
0x140012cde  cmp     dword ptr [rbp+0B20h], 2000h
0x140012ce8  jl      loc_1400130D7
0x140012cee  cmp     dword ptr [rdi+rbx+0D0h], 3
0x140012cf6  jz      loc_140013154
0x140012cfc  mov     sil, 1
0x140012cff  mov     [rdi+rbx+158h], r15d
0x140012d07  lea     r14, [rbx+167h]
0x140012d0e  add     r14, rdi
0x140012d11  mov     byte ptr [r14], 1
0x140012d15  test    r15d, r15d
0x140012d18  jnz     loc_140012FC9
0x140012d1e  test    sil, sil
0x140012d21  jz      loc_140012E65
0x140012d27  mov     eax, [rdi+rbx+4]
0x140012d2b  xor     esi, esi
0x140012d2d  mov     [rsp+108h+var_B4], eax
0x140012d31  mov     rax, cs:qword_14015C500
0x140012d38  and     eax, 2
0x140012d3b  mov     [rsp+108h+var_AC], 0FFFFFFFFh
0x140012d43  mov     [rsp+108h+var_80], rax
0x140012d4b  mov     [rsp+108h+var_A8], rsi
0x140012d50  jz      short loc_140012D67
0x140012d52  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, 1
0x140012d59  mov     [rsp+108h+var_AC], 1404h
0x140012d61  jnz     loc_14001315C
0x140012d67  call    cs:__imp_KeGetCurrentIrql
0x140012d6e  nop     dword ptr [rax+rax+00h]
0x140012d73  cmp     al, 2
0x140012d75  jb      loc_140013035
0x140012d7b  lock inc dword ptr [rbp+1334h]
0x140012d82  call    cs:__imp_KeGetCurrentIrql
0x140012d89  nop     dword ptr [rax+rax+00h]
0x140012d8e  xor     ecx, ecx
0x140012d90  mov     [rsp+108h+var_B8], al
0x140012d94  mov     [rsp+108h+var_A0], rcx
0x140012d99  cmp     al, 2
0x140012d9b  jb      loc_1400131D9
0x140012da1  mov     [rsp+108h+var_B0], 0
0x140012da9  mov     rdx, rbp; struct DXGADAPTER *
0x140012dac  lea     rcx, [rsp+108h+var_78]; this
0x140012db4  call    ??0DXGVALIDATIONPROCESSATTACH@@QEAA@PEAVDXGADAPTER@@@Z; DXGVALIDATIONPROCESSATTACH::DXGVALIDATIONPROCESSATTACH(DXGADAPTER *)
0x140012db9  mov     rax, [rbp+348h]
0x140012dc0  mov     r8d, r15d
0x140012dc3  mov     edx, [rsp+108h+var_B4]
0x140012dc7  mov     rcx, [rbp+120h]
0x140012dce  call    _guard_dispatch_icall
0x140012dd3  cmp     [rsp+108h+var_78], 0
0x140012ddb  mov     [rsp+108h+var_B4], eax
0x140012ddf  jz      short loc_140012DF5
0x140012de1  lea     rcx, [rsp+108h+ApcState]; ApcState
0x140012de9  call    cs:__imp_KeUnstackDetachProcess
0x140012df0  nop     dword ptr [rax+rax+00h]
0x140012df5  call    cs:__imp_KeGetCurrentIrql
0x140012dfc  nop     dword ptr [rax+rax+00h]
0x140012e01  cmp     [rsp+108h+var_B8], al
0x140012e05  jnz     loc_1400131F8
0x140012e0b  mov     rax, [rsp+108h+var_A0]
0x140012e10  test    rax, rax
0x140012e13  jnz     loc_140013084
0x140012e19  lock dec dword ptr [rbp+1334h]
0x140012e20  movsxd  rax, [rsp+108h+var_B4]
0x140012e25  cmp     eax, 0C01E0116h
0x140012e2a  jz      short loc_140012E34
0x140012e2c  test    eax, eax
0x140012e2e  jnz     loc_140013241
0x140012e34  test    rsi, rsi
0x140012e37  jz      short loc_140012E4D
0x140012e39  cmp     dword ptr [rsi+2Ch], 0
0x140012e3d  jle     loc_1400132AE
0x140012e43  sub     dword ptr [rsi+2Ch], 1
0x140012e47  jz      loc_140013078
0x140012e4d  cmp     [rsp+108h+var_80], 0
0x140012e56  jz      short loc_140012E65
0x140012e58  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, 1
0x140012e5f  jnz     loc_140013314
0x140012e65  mov     sil, 1
0x140012e68  cmp     cs:bTracingEnabled, 0
0x140012e6f  jz      short loc_140012E7E
0x140012e71  test    byte ptr cs:Microsoft_Windows_DxgKrnlEnableBits+2, 2
0x140012e78  jnz     loc_140013107
0x140012e7e  mov     eax, [rdi+rbx+0D8h]
0x140012e85  test    al, 2
0x140012e87  jnz     loc_140012F6C
0x140012e8d  mov     byte ptr [r14], 0
0x140012e91  test    r12b, r12b
0x140012e94  jnz     short loc_140012EAC
0x140012e96  mov     rcx, [rbp+0D10h]
0x140012e9d  mov     edx, r13d
0x140012ea0  call    cs:__imp_PoFxCompleteIdleState
0x140012ea7  nop     dword ptr [rax+rax+00h]
0x140012eac  test    sil, sil
0x140012eaf  jz      loc_140012F6C
0x140012eb5  test    r15d, r15d
0x140012eb8  jnz     short loc_140012ECB
0x140012eba  mov     rcx, [rdi+rbx+200h]
0x140012ec2  test    rcx, rcx
0x140012ec5  jnz     loc_14001332A
0x140012ecb  cmp     dword ptr [rdi+rbx+0D0h], 7
0x140012ed3  jnz     loc_140012F6C
0x140012ed9  cmp     cs:?m_pGlobal@DXGGLOBAL@@0PEAV1@EA, 0; DXGGLOBAL * DXGGLOBAL::m_pGlobal
0x140012ee1  mov     r12d, [rdi+rbx+4]
0x140012ee6  jz      loc_14001333B
0x140012eec  mov     rbx, cs:?m_pGlobal@DXGGLOBAL@@0PEAV1@EA; DXGGLOBAL * DXGGLOBAL::m_pGlobal
0x140012ef3  xorps   xmm0, xmm0
0x140012ef6  xor     eax, eax
0x140012ef8  xor     r13b, r13b
0x140012efb  movups  xmmword ptr [rsp+108h+LockHandle.LockQueue.Next], xmm0
0x140012f00  mov     qword ptr [rsp+108h+LockHandle.OldIrql], rax
0x140012f08  call    cs:__imp_KeGetCurrentIrql
0x140012f0f  nop     dword ptr [rax+rax+00h]
0x140012f14  cmp     al, 2
0x140012f16  jb      loc_140013127
0x140012f1c  lea     rcx, [rbx+6E8h]; SpinLock
0x140012f23  lea     rdx, [rsp+108h+LockHandle]; LockHandle
0x140012f28  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x140012f2f  nop     dword ptr [rax+rax+00h]
0x140012f34  lea     rdi, [rbx+710h]
0x140012f3b  mov     r14, [rdi]
0x140012f3e  cmp     r14, rdi
0x140012f41  jnz     loc_1400133A1
0x140012f47  call    cs:__imp_KeGetCurrentIrql
0x140012f4e  nop     dword ptr [rax+rax+00h]
0x140012f53  cmp     al, 2
0x140012f55  jb      loc_14001344B
0x140012f5b  lea     rcx, [rsp+108h+LockHandle]; LockHandle
0x140012f60  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x140012f67  nop     dword ptr [rax+rax+00h]
0x140012f6c  mov     rsi, [rsp+108h+var_28]
0x140012f74  mov     r14, [rsp+108h+var_38]
0x140012f7c  mov     rbx, [rsp+108h+arg_18]
0x140012f84  mov     rdi, [rsp+108h+var_30]
0x140012f8c  mov     rcx, [rsp+108h+var_40]
0x140012f94  xor     rcx, rsp; StackCookie
0x140012f97  call    __security_check_cookie
0x140012f9c  add     rsp, 0E8h
0x140012fa3  pop     r15
0x140012fa5  pop     r13
0x140012fa7  pop     r12
0x140012fa9  pop     rbp
0x140012faa  retn
0x140012fac  test    r12b, r12b
0x140012faf  jnz     short loc_140012F8C
0x140012fb1  mov     rcx, [rcx+0D10h]
0x140012fb8  mov     edx, r13d
0x140012fbb  call    cs:__imp_PoFxCompleteIdleState
0x140012fc2  nop     dword ptr [rax+rax+00h]
0x140012fc7  jmp     short loc_140012F8C
0x140012fc9  mov     rax, [rdi+rbx+200h]
0x140012fd1  mov     [rsp+108h+var_A8], rax
0x140012fd6  test    rax, rax
0x140012fd9  jz      loc_140012D1E
0x140012fdf  xor     ecx, ecx
0x140012fe1  lea     rdx, [rsp+108h+LockHandle]; LockHandle
0x140012fe6  mov     qword ptr [rsp+108h+LockHandle.OldIrql], rcx
0x140012fee  xorps   xmm0, xmm0
0x140012ff1  lea     rcx, [rax+0A0h]; SpinLock
0x140012ff8  movups  xmmword ptr [rsp+108h+LockHandle.LockQueue.Next], xmm0
0x140012ffd  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140013004  nop     dword ptr [rax+rax+00h]
0x140013009  mov     rax, [rsp+108h+var_A8]
0x14001300e  lea     rcx, [rsp+108h+LockHandle]; LockHandle
0x140013013  mov     byte ptr [rax+0E0h], 1
0x14001301a  mov     dword ptr [rax+0C4h], 0FFFFFFFFh
0x140013024  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14001302b  nop     dword ptr [rax+rax+00h]
0x140013030  jmp     loc_140012D1E
0x140013035  call    ?GetCurrent@DXGTHREAD@@SAPEAV1@XZ; DXGTHREAD::GetCurrent(void)
0x14001303a  mov     [rsp+108h+var_A8], rax
0x14001303f  mov     rsi, rax
0x140013042  test    rax, rax
0x140013045  jz      loc_140012D7B
0x14001304b  cmp     dword ptr [rax+2Ch], 0
0x14001304f  jl      loc_140013173
0x140013055  mov     eax, [rsi+2Ch]
0x140013058  test    eax, eax
0x14001305a  jz      short loc_1400130CE
0x14001305c  inc     eax
0x14001305e  mov     [rsi+2Ch], eax
0x140013061  jmp     loc_140012D7B
0x140013066  xor     sil, sil
0x140013069  lea     r14, [rbx+167h]
0x140013070  add     r14, rdi
0x140013073  jmp     loc_140012E68
0x140013078  mov     dword ptr [rsi+30h], 0FFFFFFFFh
0x14001307f  jmp     loc_140012E4D
0x140013084  movsxd  rcx, dword ptr [rax+28h]
0x140013088  movsxd  rax, [rsp+108h+var_B0]
0x14001308d  cmp     ecx, eax
0x14001308f  jz      loc_140012E19
0x140013095  mov     r9, rcx
0x140013098  mov     [rsp+108h+var_E0], 0
0x1400130a1  xor     ecx, ecx
0x1400130a3  mov     [rsp+108h+var_E8], rax
0x1400130a8  mov     edx, 113h
0x1400130ad  mov     r8d, 26h ; '&'
0x1400130b3  call    cs:__imp_WdLogSingleEntry5
0x1400130ba  nop     dword ptr [rax+rax+00h]
0x1400130bf  mov     cs:WdLogGlobalForLineNumber, 49h ; 'I'
0x1400130c9  jmp     loc_140012E19
0x1400130ce  mov     dword ptr [rsi+30h], 1404h
0x1400130d5  jmp     short loc_14001305C
0x1400130d7  cmp     byte ptr [rbp+0C4Ch], 0
0x1400130de  jnz     loc_140012CEE
0x1400130e4  jmp     loc_140012CFC
0x1400130e9  mov     dword ptr [rsp+108h+var_E0], r15d
0x1400130ee  lea     rdx, Dxgk_SetPowerComponentFState
0x1400130f5  mov     r9, rbp
0x1400130f8  mov     dword ptr [rsp+108h+var_E8], r13d
0x1400130fd  call    McTemplateK0pqq_EtwWriteTransfer
0x140013102  jmp     loc_140012CAD
0x140013107  mov     r9, rbp
0x14001310a  mov     dword ptr [rsp+108h+var_E8], r13d
0x14001310f  lea     rdx, Dxgk_SetPowerComponentFStateEnd
0x140013116  lea     rcx, DxgkControlGuid_Context
0x14001311d  call    McTemplateK0pt_EtwWriteTransfer
0x140013122  jmp     loc_140012E7E
0x140013127  mov     rcx, [rbx+6F8h]
0x14001312e  mov     rax, gs:188h
0x140013137  cmp     rcx, rax
0x14001313a  jz      loc_140012F34
0x140013140  lea     rcx, [rbx+6F0h]; this
0x140013147  call    ?AcquireShared@DXGPUSHLOCK@@QEAAXXZ; DXGPUSHLOCK::AcquireShared(void)
0x14001314c  mov     r13b, 1
0x14001314f  jmp     loc_140012F34
0x140013154  xor     sil, sil
0x140013157  jmp     loc_140012D07
0x14001315c  mov     r9d, 1404h
0x140013162  lea     rdx, EventProfilerEnter
0x140013169  call    McTemplateK0q_EtwWriteTransfer
0x14001316e  jmp     loc_140012D67
0x140013173  mov     ecx, 1
0x140013178  call    cs:__imp_WdLogSingleEntry0
0x14001317f  nop     dword ptr [rax+rax+00h]
0x140013184  mov     [rsp+108h+var_C8], 0
0x14001318d  lea     r9, aMProfilerentry; "m_ProfilerEntryCount >= 0"
0x140013194  mov     [rsp+108h+var_D0], 0
0x14001319d  mov     edx, 40002h
0x1400131a2  mov     [rsp+108h+var_D8], 0
0x1400131ab  xor     ecx, ecx
0x1400131ad  mov     [rsp+108h+var_E0], 0
0x1400131b6  mov     r8d, 0FFFFFFFFh
0x1400131bc  mov     [rsp+108h+var_E8], 0B7h
0x1400131c5  mov     cs:WdLogGlobalForLineNumber, 0B7h
0x1400131cf  call    DxgkLogInternalTriageEvent
0x1400131d4  jmp     loc_140013055
0x1400131d9  call    ?GetCurrent@DXGTHREAD@@SAPEAV1@XZ; DXGTHREAD::GetCurrent(void)
0x1400131de  mov     [rsp+108h+var_A0], rax
0x1400131e3  test    rax, rax
0x1400131e6  jz      loc_140012DA1
0x1400131ec  mov     eax, [rax+28h]
0x1400131ef  mov     [rsp+108h+var_B0], eax
0x1400131f3  jmp     loc_140012DA9
0x1400131f8  call    cs:__imp_KeGetCurrentIrql
0x1400131ff  nop     dword ptr [rax+rax+00h]
0x140013204  movzx   ecx, [rsp+108h+var_B8]
0x140013209  mov     r9, rbp
0x14001320c  movzx   eax, al
0x14001320f  mov     edx, 113h
0x140013214  mov     [rsp+108h+var_E0], rax
0x140013219  mov     r8d, 10h
0x14001321f  mov     [rsp+108h+var_E8], rcx
0x140013224  xor     ecx, ecx
0x140013226  call    cs:__imp_WdLogSingleEntry5
0x14001322d  nop     dword ptr [rax+rax+00h]
0x140013232  mov     cs:WdLogGlobalForLineNumber, 0A13h
0x14001323c  jmp     loc_140012E0B
0x140013241  mov     rdx, rax
0x140013244  mov     ecx, 2
0x140013249  mov     rsi, rax
0x14001324c  call    cs:__imp_WdLogSingleEntry1
  ... truncated ...
```
