# FveEowFreeSweepWorker

- ea: `0x14007fc90`
- end: `0x140080197`
- name: `FveEowFreeSweepWorker`
- size: `1287`
- prototype: `KSTART_ROUTINE`
- caller_count: `0`
- callee_count: `22`
- tags: `broker_com_uri`

## callees

- `0x140008e80`
- `0x140008f04`
- `0x140009cb4`
- `0x14000afb4`
- `0x140023040`
- `0x14002aa38`
- `0x14002d500`
- `0x140059de4`
- `0x14007dfcc`
- `0x14007e9fc`
- `0x14007f5dc`
- `0x14007fae4`
- `0x14007fc90`
- `0x1400807fc`
- `0x140097240`
- `0x14009e2c0`
- `0x1400a5258`
- `0x1400a6e54`
- `0x1400c2678`
- `0x1400c5f08`
- `0x1400dce00`
- `0x1400dd144`

## import_xrefs

- `ntoskrnl!KeSetActualBasePriorityThread` at `0x14007fe16`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x14007fe16`
- `ntoskrnl!KeSetEvent` at `0x14007fde3`
- `ntoskrnl!KeSetEvent` at `0x14007fde3`
- `ntoskrnl!KeWaitForSingleObject` at `0x14008004e`
- `ntoskrnl!KeWaitForSingleObject` at `0x14008004e`
- `ntoskrnl!KeBugCheckEx` at `0x14007ff50`
- `ntoskrnl!KeBugCheckEx` at `0x14007ff50`

## pseudocode

```c
void __fastcall FveEowFreeSweepWorker(char *StartContext)
{
  ULONG_PTR v1; // rbx
  unsigned __int64 v3; // r13
  __int64 v4; // r12
  __int64 v5; // r15
  __int64 v6; // rdx
  int UsedBitmap; // esi
  __int64 *v8; // rax
  __int64 v9; // rcx
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // r8
  int v14; // edi
  _QWORD *v15; // rax
  __int64 v16; // r8
  unsigned __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // r8
  __int64 v20; // rcx
  __int64 v21; // [rsp+30h] [rbp-99h]
  __int64 *v22; // [rsp+38h] [rbp-91h] BYREF
  __int128 v23; // [rsp+40h] [rbp-89h]
  _BYTE v24[208]; // [rsp+50h] [rbp-79h] BYREF
  bool v25; // [rsp+130h] [rbp+67h]
  char v26; // [rsp+138h] [rbp+6Fh]
  char v27; // [rsp+140h] [rbp+77h]
  __int64 v28; // [rsp+148h] [rbp+7Fh]

  v1 = *(_QWORD *)StartContext;
  v21 = 0;
  memset(v24, 0, 0x90u);
  v3 = 0;
  v27 = 0;
  v4 = 0;
  v5 = 0;
  v26 = 0;
  v28 = 0;
  v25 = 1;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 230, WPP_e3882f5f78b938fff15e86bae05ee61a_Traceguids);
  }
  UsedBitmap = FvepAcquireRemoveLock(v1 + 56);
  if ( UsedBitmap >= 0 )
  {
    v27 = 1;
    if ( (*(_DWORD *)(v1 + 808) & 0x100) != 0
      && (v8 = *(__int64 **)(v1 + 736)) != 0
      && (v9 = *v8) != 0
      && (v10 = *(_QWORD *)(v1 + 976)) != 0 )
    {
      v3 = *(_QWORD *)(v10 + 56);
      v21 = v9;
      v25 = (*(_BYTE *)(v9 + 48) & 2) == 0;
      if ( (unsigned int)Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline(v9, v6)
        && (*(_BYTE *)(v1 + 4419) & 8) != 0
        || (v11 = *(_QWORD *)(v1 + 976), *(_WORD *)(v11 + 10) == 1) )
      {
        v12 = 0;
      }
      else
      {
        v12 = *(unsigned int *)(v11 + 28);
        if ( !(_DWORD)v12 )
          v12 = 1;
      }
      v4 = v12 * *(unsigned int *)(v1 + 1308);
      *(_DWORD *)(v1 + 808) |= 0x20000u;
      *((_QWORD *)StartContext + 2) = KeGetCurrentThread();
    }
    else
    {
      UsedBitmap = -1073741823;
    }
  }
  KeSetEvent((PRKEVENT)(StartContext + 112), 0, 0);
  if ( UsedBitmap >= 0 && (int)FveEowCheckSweepStop(StartContext + 88) >= 0 )
  {
    KeSetActualBasePriorityThread(KeGetCurrentThread(), 4);
    if ( v4 + v3 < v3 )
    {
      UsedBitmap = -1073741675;
    }
    else
    {
      v14 = 0;
      LOBYTE(v13) = 1;
      FvepAcquireDevFveLock(v1, v24, v13);
      if ( (*(_DWORD *)(v1 + 808) & 0x100) != 0 )
      {
        v15 = *(_QWORD **)(v1 + 736);
        if ( v15 )
        {
          if ( *v15 )
          {
            v14 = _InterlockedIncrement((volatile signed __int32 *)(v1 + 744));
            if ( v14 <= 1 )
              KeBugCheckEx(0x120u, 0xCu, 0, 0, 0);
            v5 = *(_QWORD *)(v1 + 1496);
            v28 = v5;
          }
        }
      }
      UsedBitmap = 0;
      FvepReleaseDevFveLock(v24);
      if ( v14 > 0 )
      {
        UsedBitmap = FveEowCtrlVolumeInfoInit(v1);
        if ( UsedBitmap < 0 )
          goto LABEL_57;
        if ( !v5 )
        {
          UsedBitmap = FveConvCreateUsedBitmap(*(unsigned int *)(*(_QWORD *)(v1 + 736) + 148LL));
          if ( UsedBitmap < 0 )
            goto LABEL_57;
          FveConvSetUsedBitmap(v1, v28);
        }
      }
      for ( ; *((_DWORD *)StartContext + 35) < *((_DWORD *)StartContext + 36); ++*((_DWORD *)StartContext + 35) )
      {
        if ( (int)FveEowCheckSweepStop(StartContext + 88) < 0 )
          break;
        v16 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v1 + 736) + 16LL) + 8LL * *((unsigned int *)StartContext + 35));
        if ( v25 )
        {
          if ( *(_BYTE *)(v16 + 12)
            || (*(_BYTE *)(*(_QWORD *)(v16 + 8LL * *(unsigned int *)(v16 + 20) + 48) + 28LL) & 1) != 0 )
          {
            goto LABEL_53;
          }
        }
        else if ( *(_BYTE *)(v16 + 13)
               || (*(_BYTE *)(*(_QWORD *)(v16 + 8LL * *(unsigned int *)(v16 + 20) + 48) + 28LL) & 2) != 0 )
        {
          goto LABEL_53;
        }
        v17 = *(_QWORD *)(v16 + 84);
        v18 = *(_QWORD *)(v16 + 92);
        if ( v17 < v3 || v17 >= v4 + v3 )
          goto LABEL_45;
        if ( v17 == v3 && v18 == v4 )
        {
          v17 -= v3;
LABEL_45:
          UsedBitmap = FveConvPrepareUsedBitmap(v1, v17, v18);
          if ( UsedBitmap >= 0 )
          {
            UsedBitmap = FveEowGetRegionVolumeBitmap(v1, *((unsigned int *)StartContext + 35), v3, v4);
            if ( UsedBitmap >= 0 && *((_DWORD *)StartContext + 35) == *(_DWORD *)(v21 + 524) )
            {
              UsedBitmap = FveEowFreeSweepProcessRegion(StartContext, v3, v4);
              if ( UsedBitmap < 0
                && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
              {
                WPP_SF_Dd(
                  WPP_GLOBAL_Control->AttachedDevice,
                  231,
                  WPP_e3882f5f78b938fff15e86bae05ee61a_Traceguids,
                  *((unsigned int *)StartContext + 35),
                  UsedBitmap);
              }
            }
          }
        }
LABEL_53:
        KeWaitForSingleObject(StartContext + 112, Executive, 0, 0, 0);
      }
      if ( *((_DWORD *)StartContext + 35) >= *((_DWORD *)StartContext + 36) )
      {
        v26 = 1;
        *(_BYTE *)(v21 + 48) |= 8u;
      }
    }
  }
LABEL_57:
  FveEowFreeSweepStopThread((__int64)StartContext, 0);
  *((_QWORD *)StartContext + 2) = 0;
  FveEowFreeSweepCtrlFree(StartContext);
  LOBYTE(v19) = 1;
  FvepAcquireDevFveLock(v1, v24, v19);
  *(_DWORD *)(v1 + 808) &= ~0x20000u;
  FvepReleaseDevFveLock(v24);
  FveRaiseStatusChangedEvent(v1, 22);
  if ( v26 )
  {
    FveRaiseStatusChangedEvent(v1, !v25 + 24);
    if ( (*(_DWORD *)(*(_QWORD *)(v1 + 8) + 9924LL) & 0x2000) != 0 )
    {
      v20 = *(_QWORD *)v1;
      v22 = FVE_EOW_FS_SWEEP_COMPLETE;
      v23 = 0;
      FveLogEvent(v20, &v22);
    }
    FveEowFinalSweepStart(v1, 0);
  }
  if ( v27 )
    FvepReleaseRemoveLock(v1 + 56);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      232,
      WPP_e3882f5f78b938fff15e86bae05ee61a_Traceguids,
      (unsigned int)UsedBitmap);
  }
}

```

## disassembly

```asm
0x14007fc90  push    rbp
0x14007fc92  push    rbx
0x14007fc93  push    rsi
0x14007fc94  push    rdi
0x14007fc95  push    r12
0x14007fc97  push    r13
0x14007fc99  push    r14
0x14007fc9b  push    r15
0x14007fc9d  lea     rbp, [rsp-1Fh]
0x14007fca2  sub     rsp, 0E8h
0x14007fca9  mov     rbx, [rcx]
0x14007fcac  mov     r14, rcx
0x14007fcaf  lea     rcx, [rbp+57h+var_D0]; void *
0x14007fcb3  mov     [rsp+120h+var_F0], 0
0x14007fcbc  xor     edx, edx; Val
0x14007fcbe  mov     r8d, 90h; Size
0x14007fcc4  call    memset
0x14007fcc9  xor     r13d, r13d
0x14007fccc  mov     [rbp+57h+arg_10], 0
0x14007fcd0  xor     r12d, r12d
0x14007fcd3  xor     r15d, r15d
0x14007fcd6  mov     [rbp+57h+arg_8], r12b
0x14007fcda  mov     [rbp+57h+arg_18], r15
0x14007fcde  lea     edi, [r13+1]
0x14007fce2  mov     [rbp+57h+arg_0], dil
0x14007fce6  mov     rcx, cs:WPP_GLOBAL_Control
0x14007fced  lea     rax, WPP_GLOBAL_Control
0x14007fcf4  cmp     rcx, rax
0x14007fcf7  jz      short loc_14007FD1D
0x14007fcf9  test    dword ptr [rcx+2Ch], 100h
0x14007fd00  jz      short loc_14007FD1D
0x14007fd02  cmp     byte ptr [rcx+29h], 5
0x14007fd06  jb      short loc_14007FD1D
0x14007fd08  mov     rcx, [rcx+18h]
0x14007fd0c  lea     r8, WPP_e3882f5f78b938fff15e86bae05ee61a_Traceguids
0x14007fd13  mov     edx, 0E6h
0x14007fd18  call    WPP_SF_
0x14007fd1d  lea     rcx, [rbx+38h]; BugCheckParameter2
0x14007fd21  call    FvepAcquireRemoveLock
0x14007fd26  mov     esi, eax
0x14007fd28  test    eax, eax
0x14007fd2a  js      loc_14007FDDA
0x14007fd30  test    dword ptr [rbx+328h], 100h
0x14007fd3a  mov     [rbp+57h+arg_10], dil
0x14007fd3e  jz      loc_14007FDD5
0x14007fd44  mov     rax, [rbx+2E0h]
0x14007fd4b  test    rax, rax
0x14007fd4e  jz      loc_14007FDD5
0x14007fd54  mov     rcx, [rax]
0x14007fd57  test    rcx, rcx
0x14007fd5a  jz      short loc_14007FDD5
0x14007fd5c  mov     rax, [rbx+3D0h]
0x14007fd63  test    rax, rax
0x14007fd66  jz      short loc_14007FDD5
0x14007fd68  mov     dil, [rcx+30h]
0x14007fd6c  mov     r13, [rax+38h]
0x14007fd70  shr     dil, 1
0x14007fd73  not     dil
0x14007fd76  mov     [rsp+120h+var_F0], rcx
0x14007fd7b  and     dil, 1
0x14007fd7f  mov     [rbp+57h+arg_0], dil
0x14007fd83  call    Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline
0x14007fd88  test    eax, eax
0x14007fd8a  jz      short loc_14007FD95
0x14007fd8c  test    byte ptr [rbx+1143h], 8
0x14007fd93  jnz     short loc_14007FDA7
0x14007fd95  mov     rax, [rbx+3D0h]
0x14007fd9c  mov     edi, 1
0x14007fda1  cmp     [rax+0Ah], di
0x14007fda5  jnz     short loc_14007FDAB
0x14007fda7  xor     eax, eax
0x14007fda9  jmp     short loc_14007FDB3
0x14007fdab  mov     eax, [rax+1Ch]
0x14007fdae  test    eax, eax
0x14007fdb0  cmovz   eax, edi
0x14007fdb3  mov     r12d, [rbx+51Ch]
0x14007fdba  imul    r12, rax
0x14007fdbe  bts     dword ptr [rbx+328h], 11h
0x14007fdc6  mov     rax, gs:188h
0x14007fdcf  mov     [r14+10h], rax
0x14007fdd3  jmp     short loc_14007FDDA
0x14007fdd5  mov     esi, 0C0000001h
0x14007fdda  lea     rcx, [r14+70h]; Event
0x14007fdde  xor     r8d, r8d; Wait
0x14007fde1  xor     edx, edx; Increment
0x14007fde3  call    cs:__imp_KeSetEvent
0x14007fdea  nop     dword ptr [rax+rax+00h]
0x14007fdef  test    esi, esi
0x14007fdf1  js      loc_140080099
0x14007fdf7  lea     rcx, [r14+58h]
0x14007fdfb  call    FveEowCheckSweepStop
0x14007fe00  test    eax, eax
0x14007fe02  js      loc_140080099
0x14007fe08  mov     rcx, gs:188h
0x14007fe11  mov     edx, 4
0x14007fe16  call    cs:__imp_KeSetActualBasePriorityThread
0x14007fe1d  nop     dword ptr [rax+rax+00h]
0x14007fe22  lea     rax, [r12+r13]
0x14007fe26  cmp     rax, r13
0x14007fe29  jb      loc_140080094
0x14007fe2f  xor     edi, edi
0x14007fe31  lea     rdx, [rbp+57h+var_D0]
0x14007fe35  mov     rcx, rbx
0x14007fe38  lea     esi, [rdi+1]
0x14007fe3b  mov     r8b, sil
0x14007fe3e  call    FvepAcquireDevFveLock
0x14007fe43  test    dword ptr [rbx+328h], 100h
0x14007fe4d  jz      short loc_14007FE7F
0x14007fe4f  mov     rax, [rbx+2E0h]
0x14007fe56  test    rax, rax
0x14007fe59  jz      short loc_14007FE7F
0x14007fe5b  cmp     [rax], rdi
0x14007fe5e  jz      short loc_14007FE7F
0x14007fe60  mov     edi, esi
0x14007fe62  lock xadd [rbx+2E8h], edi
0x14007fe6a  add     edi, esi
0x14007fe6c  cmp     edi, esi
0x14007fe6e  jle     loc_14007FF3C
0x14007fe74  mov     r15, [rbx+5D8h]
0x14007fe7b  mov     [rbp+57h+arg_18], r15
0x14007fe7f  lea     rcx, [rbp+57h+var_D0]
0x14007fe83  xor     esi, esi
0x14007fe85  call    FvepReleaseDevFveLock
0x14007fe8a  test    edi, edi
0x14007fe8c  jle     short loc_14007FED8
0x14007fe8e  mov     rcx, rbx; BugCheckParameter2
0x14007fe91  call    FveEowCtrlVolumeInfoInit
0x14007fe96  mov     esi, eax
0x14007fe98  test    eax, eax
0x14007fe9a  js      loc_140080099
0x14007fea0  test    r15, r15
0x14007fea3  jnz     short loc_14007FED8
0x14007fea5  mov     rax, [rbx+2E0h]
0x14007feac  lea     r8, [rbp+57h+arg_18]
0x14007feb0  mov     rdx, [rax]
0x14007feb3  mov     ecx, [rax+94h]; ullMultiplier
0x14007feb9  mov     rdx, [rdx+38h]
0x14007febd  call    FveConvCreateUsedBitmap
0x14007fec2  mov     esi, eax
0x14007fec4  test    eax, eax
0x14007fec6  js      loc_140080099
0x14007fecc  mov     rdx, [rbp+57h+arg_18]
0x14007fed0  mov     rcx, rbx
0x14007fed3  call    FveConvSetUsedBitmap
0x14007fed8  mov     eax, [r14+90h]
0x14007fedf  cmp     [r14+8Ch], eax
0x14007fee6  jnb     loc_140080075
0x14007feec  lea     rdi, [r12+r13]
0x14007fef0  lea     rcx, [r14+58h]
0x14007fef4  call    FveEowCheckSweepStop
0x14007fef9  test    eax, eax
0x14007fefb  js      loc_140080075
0x14007ff01  cmp     [rbp+57h+arg_0], 0
0x14007ff05  mov     rax, [rbx+2E0h]
0x14007ff0c  mov     edx, [r14+8Ch]
0x14007ff13  mov     rcx, [rax+10h]
0x14007ff17  mov     r8, [rcx+rdx*8]
0x14007ff1b  jz      short loc_14007FF5D
0x14007ff1d  cmp     byte ptr [r8+0Ch], 0
0x14007ff22  jnz     loc_140080039
0x14007ff28  mov     eax, [r8+14h]
0x14007ff2c  mov     rcx, [r8+rax*8+30h]
0x14007ff31  test    byte ptr [rcx+1Ch], 1
0x14007ff35  jz      short loc_14007FF7B
0x14007ff37  jmp     loc_140080039
0x14007ff3c  xor     r9d, r9d; BugCheckParameter3
0x14007ff3f  mov     [rsp+120h+BugCheckParameter4], r15; BugCheckParameter4
0x14007ff44  xor     r8d, r8d; BugCheckParameter2
0x14007ff47  mov     ecx, 120h; BugCheckCode
0x14007ff4c  lea     edx, [r9+0Ch]; BugCheckParameter1
0x14007ff50  call    cs:__imp_KeBugCheckEx
0x14007ff5d  cmp     byte ptr [r8+0Dh], 0
0x14007ff62  jnz     loc_140080039
0x14007ff68  mov     eax, [r8+14h]
0x14007ff6c  mov     rcx, [r8+rax*8+30h]
0x14007ff71  test    byte ptr [rcx+1Ch], 2
0x14007ff75  jnz     loc_140080039
0x14007ff7b  mov     rdx, [r8+54h]
0x14007ff7f  mov     r8, [r8+5Ch]
0x14007ff83  cmp     rdx, r13
0x14007ff86  jb      short loc_14007FFA2
0x14007ff88  cmp     rdx, rdi
0x14007ff8b  jnb     short loc_14007FFA2
0x14007ff8d  cmp     rdx, r13
0x14007ff90  jnz     loc_140080039
0x14007ff96  cmp     r8, r12
0x14007ff99  jnz     loc_140080039
0x14007ff9f  sub     rdx, r13
0x14007ffa2  mov     rcx, rbx
0x14007ffa5  call    FveConvPrepareUsedBitmap
0x14007ffaa  mov     esi, eax
0x14007ffac  test    eax, eax
0x14007ffae  js      loc_140080039
0x14007ffb4  mov     edx, [r14+8Ch]
0x14007ffbb  mov     r9, r12
0x14007ffbe  mov     r8, r13
0x14007ffc1  mov     rcx, rbx
0x14007ffc4  call    FveEowGetRegionVolumeBitmap
0x14007ffc9  mov     esi, eax
0x14007ffcb  test    eax, eax
0x14007ffcd  js      short loc_140080039
0x14007ffcf  mov     rax, [rsp+120h+var_F0]
0x14007ffd4  mov     eax, [rax+20Ch]
0x14007ffda  cmp     [r14+8Ch], eax
0x14007ffe1  jnz     short loc_140080039
0x14007ffe3  mov     r8, r12
0x14007ffe6  mov     rdx, r13
0x14007ffe9  mov     rcx, r14
0x14007ffec  call    FveEowFreeSweepProcessRegion
0x14007fff1  mov     esi, eax
0x14007fff3  test    eax, eax
0x14007fff5  jns     short loc_140080039
0x14007fff7  mov     rcx, cs:WPP_GLOBAL_Control
0x14007fffe  lea     rax, WPP_GLOBAL_Control
0x140080005  cmp     rcx, rax
0x140080008  jz      short loc_140080039
0x14008000a  test    dword ptr [rcx+2Ch], 100h
0x140080011  jz      short loc_140080039
0x140080013  cmp     byte ptr [rcx+29h], 2
0x140080017  jb      short loc_140080039
0x140080019  mov     r9d, [r14+8Ch]
0x140080020  lea     r8, WPP_e3882f5f78b938fff15e86bae05ee61a_Traceguids
0x140080027  mov     rcx, [rcx+18h]
0x14008002b  mov     edx, 0E7h
0x140080030  mov     dword ptr [rsp+120h+BugCheckParameter4], esi
0x140080034  call    WPP_SF_Dd
0x140080039  xor     r9d, r9d; Alertable
0x14008003c  mov     [rsp+120h+BugCheckParameter4], 0; Timeout
0x140080045  xor     r8d, r8d; WaitMode
0x140080048  lea     rcx, [r14+70h]; Object
0x14008004c  xor     edx, edx; WaitReason
0x14008004e  call    cs:__imp_KeWaitForSingleObject
0x140080055  nop     dword ptr [rax+rax+00h]
0x14008005a  inc     dword ptr [r14+8Ch]
0x140080061  mov     eax, [r14+8Ch]
0x140080068  cmp     eax, [r14+90h]
0x14008006f  jb      loc_14007FEF0
0x140080075  mov     eax, [r14+90h]
0x14008007c  cmp     [r14+8Ch], eax
0x140080083  jb      short loc_140080099
0x140080085  mov     rax, [rsp+120h+var_F0]
0x14008008a  mov     [rbp+57h+arg_8], 1
0x14008008e  or      byte ptr [rax+30h], 8
0x140080092  jmp     short loc_140080099
0x140080094  mov     esi, 0C0000095h
0x140080099  xor     edx, edx
0x14008009b  mov     rcx, r14
0x14008009e  call    FveEowFreeSweepStopThread
0x1400800a3  mov     rcx, r14; P
0x1400800a6  mov     qword ptr [r14+10h], 0
0x1400800ae  call    FveEowFreeSweepCtrlFree
0x1400800b3  mov     r14d, 1
0x1400800b9  lea     rdx, [rbp+57h+var_D0]
0x1400800bd  mov     r8b, r14b
0x1400800c0  mov     rcx, rbx
0x1400800c3  call    FvepAcquireDevFveLock
0x1400800c8  btr     dword ptr [rbx+328h], 11h
0x1400800d0  lea     rcx, [rbp+57h+var_D0]
0x1400800d4  call    FvepReleaseDevFveLock
0x1400800d9  lea     edx, [r14+15h]
0x1400800dd  mov     rcx, rbx
0x1400800e0  call    FveRaiseStatusChangedEvent
0x1400800e5  cmp     [rbp+57h+arg_8], 0
0x1400800e9  jz      short loc_140080139
0x1400800eb  movzx   edx, [rbp+57h+arg_0]
0x1400800ef  mov     rcx, rbx
0x1400800f2  xor     edx, r14d
0x1400800f5  add     edx, 18h
0x1400800f8  call    FveRaiseStatusChangedEvent
0x1400800fd  mov     rax, [rbx+8]
0x140080101  test    dword ptr [rax+26C4h], 2000h
0x14008010b  jz      short loc_14008012F
0x14008010d  mov     rcx, [rbx]
0x140080110  lea     rax, FVE_EOW_FS_SWEEP_COMPLETE
0x140080117  xorps   xmm0, xmm0
0x14008011a  mov     [rsp+120h+var_E8], rax
0x14008011f  lea     rdx, [rsp+120h+var_E8]
0x140080124  movdqu  [rsp+120h+var_E0], xmm0
0x14008012a  call    FveLogEvent
0x14008012f  xor     edx, edx
0x140080131  mov     rcx, rbx
0x140080134  call    FveEowFinalSweepStart
0x140080139  cmp     [rbp+57h+arg_10], 0
0x14008013d  jz      short loc_140080148
0x14008013f  lea     rcx, [rbx+38h]; BugCheckParameter2
0x140080143  call    FvepReleaseRemoveLock
0x140080148  mov     rcx, cs:WPP_GLOBAL_Control
0x14008014f  lea     rax, WPP_GLOBAL_Control
0x140080156  cmp     rcx, rax
0x140080159  jz      short loc_140080182
0x14008015b  test    dword ptr [rcx+2Ch], 100h
0x140080162  jz      short loc_140080182
0x140080164  cmp     byte ptr [rcx+29h], 5
0x140080168  jb      short loc_140080182
0x14008016a  mov     rcx, [rcx+18h]
0x14008016e  lea     r8, WPP_e3882f5f78b938fff15e86bae05ee61a_Traceguids
0x140080175  mov     edx, 0E8h
0x14008017a  mov     r9d, esi
0x14008017d  call    WPP_SF_d
0x140080182  add     rsp, 0E8h
  ... truncated ...
```
