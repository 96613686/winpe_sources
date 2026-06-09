# FveEowFreeSweepWorker

- ea: `0x14007dbf0`
- end: `0x14007e0f7`
- name: `FveEowFreeSweepWorker`
- size: `1287`
- prototype: `KSTART_ROUTINE`
- caller_count: `0`
- callee_count: `22`
- tags: `broker_com_uri`

## callees

- `0x140008dc0`
- `0x140008e44`
- `0x140009bf4`
- `0x14000aef4`
- `0x140021d00`
- `0x140029a38`
- `0x14002c500`
- `0x140057d94`
- `0x14007bf2c`
- `0x14007c95c`
- `0x14007d53c`
- `0x14007da44`
- `0x14007dbf0`
- `0x14007e75c`
- `0x140095190`
- `0x14009c2c0`
- `0x1400a4308`
- `0x1400a5efc`
- `0x1400bec08`
- `0x1400c2498`
- `0x1400da590`
- `0x1400da8d4`

## import_xrefs

- `ntoskrnl!KeSetActualBasePriorityThread` at `0x14007dd76`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x14007dd76`
- `ntoskrnl!KeSetEvent` at `0x14007dd43`
- `ntoskrnl!KeSetEvent` at `0x14007dd43`
- `ntoskrnl!KeWaitForSingleObject` at `0x14007dfae`
- `ntoskrnl!KeWaitForSingleObject` at `0x14007dfae`
- `ntoskrnl!KeBugCheckEx` at `0x14007deb0`
- `ntoskrnl!KeBugCheckEx` at `0x14007deb0`

## pseudocode

```c
void __fastcall FveEowFreeSweepWorker(char *StartContext)
{
  ULONG_PTR v1; // rbx
  unsigned __int64 v3; // r13
  __int64 v4; // r12
  __int64 v5; // r15
  int UsedBitmap; // esi
  __int64 *v7; // rax
  __int64 v8; // rcx
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // r8
  int v13; // edi
  _QWORD *v14; // rax
  __int64 v15; // r8
  unsigned __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // r8
  __int64 v19; // rcx
  __int64 v20; // [rsp+30h] [rbp-99h]
  __int64 *v21; // [rsp+38h] [rbp-91h] BYREF
  __int128 v22; // [rsp+40h] [rbp-89h]
  _BYTE v23[208]; // [rsp+50h] [rbp-79h] BYREF
  bool v24; // [rsp+130h] [rbp+67h]
  char v25; // [rsp+138h] [rbp+6Fh]
  char v26; // [rsp+140h] [rbp+77h]
  __int64 v27; // [rsp+148h] [rbp+7Fh]

  v1 = *(_QWORD *)StartContext;
  v20 = 0;
  memset(v23, 0, 0x90u);
  v3 = 0;
  v26 = 0;
  v4 = 0;
  v5 = 0;
  v25 = 0;
  v27 = 0;
  v24 = 1;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 230, WPP_e3882f5f78b938fff15e86bae05ee61a_Traceguids);
  }
  UsedBitmap = FvepAcquireRemoveLock(v1 + 56);
  if ( UsedBitmap >= 0 )
  {
    v26 = 1;
    if ( (*(_DWORD *)(v1 + 808) & 0x100) != 0
      && (v7 = *(__int64 **)(v1 + 736)) != 0
      && (v8 = *v7) != 0
      && (v9 = *(_QWORD *)(v1 + 976)) != 0 )
    {
      v3 = *(_QWORD *)(v9 + 56);
      v20 = v8;
      v24 = (*(_BYTE *)(v8 + 48) & 2) == 0;
      if ( (unsigned int)Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline(v8)
        && (*(_BYTE *)(v1 + 4403) & 8) != 0
        || (v10 = *(_QWORD *)(v1 + 976), *(_WORD *)(v10 + 10) == 1) )
      {
        v11 = 0;
      }
      else
      {
        v11 = *(unsigned int *)(v10 + 28);
        if ( !(_DWORD)v11 )
          v11 = 1;
      }
      v4 = v11 * *(unsigned int *)(v1 + 1308);
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
      v13 = 0;
      LOBYTE(v12) = 1;
      FvepAcquireDevFveLock(v1, v23, v12);
      if ( (*(_DWORD *)(v1 + 808) & 0x100) != 0 )
      {
        v14 = *(_QWORD **)(v1 + 736);
        if ( v14 )
        {
          if ( *v14 )
          {
            v13 = _InterlockedIncrement((volatile signed __int32 *)(v1 + 744));
            if ( v13 <= 1 )
              KeBugCheckEx(0x120u, 0xCu, 0, 0, 0);
            v5 = *(_QWORD *)(v1 + 1496);
            v27 = v5;
          }
        }
      }
      UsedBitmap = 0;
      FvepReleaseDevFveLock(v23);
      if ( v13 > 0 )
      {
        UsedBitmap = FveEowCtrlVolumeInfoInit(v1);
        if ( UsedBitmap < 0 )
          goto LABEL_57;
        if ( !v5 )
        {
          UsedBitmap = FveConvCreateUsedBitmap(*(unsigned int *)(*(_QWORD *)(v1 + 736) + 148LL));
          if ( UsedBitmap < 0 )
            goto LABEL_57;
          FveConvSetUsedBitmap(v1, v27);
        }
      }
      for ( ; *((_DWORD *)StartContext + 35) < *((_DWORD *)StartContext + 36); ++*((_DWORD *)StartContext + 35) )
      {
        if ( (int)FveEowCheckSweepStop(StartContext + 88) < 0 )
          break;
        v15 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v1 + 736) + 16LL) + 8LL * *((unsigned int *)StartContext + 35));
        if ( v24 )
        {
          if ( *(_BYTE *)(v15 + 12)
            || (*(_BYTE *)(*(_QWORD *)(v15 + 8LL * *(unsigned int *)(v15 + 20) + 48) + 28LL) & 1) != 0 )
          {
            goto LABEL_53;
          }
        }
        else if ( *(_BYTE *)(v15 + 13)
               || (*(_BYTE *)(*(_QWORD *)(v15 + 8LL * *(unsigned int *)(v15 + 20) + 48) + 28LL) & 2) != 0 )
        {
          goto LABEL_53;
        }
        v16 = *(_QWORD *)(v15 + 84);
        v17 = *(_QWORD *)(v15 + 92);
        if ( v16 < v3 || v16 >= v4 + v3 )
          goto LABEL_45;
        if ( v16 == v3 && v17 == v4 )
        {
          v16 -= v3;
LABEL_45:
          UsedBitmap = FveConvPrepareUsedBitmap(v1, v16, v17);
          if ( UsedBitmap >= 0 )
          {
            UsedBitmap = FveEowGetRegionVolumeBitmap(v1, *((unsigned int *)StartContext + 35), v3, v4);
            if ( UsedBitmap >= 0 && *((_DWORD *)StartContext + 35) == *(_DWORD *)(v20 + 524) )
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
        v25 = 1;
        *(_BYTE *)(v20 + 48) |= 8u;
      }
    }
  }
LABEL_57:
  FveEowFreeSweepStopThread((__int64)StartContext, 0);
  *((_QWORD *)StartContext + 2) = 0;
  FveEowFreeSweepCtrlFree(StartContext);
  LOBYTE(v18) = 1;
  FvepAcquireDevFveLock(v1, v23, v18);
  *(_DWORD *)(v1 + 808) &= ~0x20000u;
  FvepReleaseDevFveLock(v23);
  FveRaiseStatusChangedEvent(v1, 22);
  if ( v25 )
  {
    FveRaiseStatusChangedEvent(v1, !v24 + 24);
    if ( (*(_DWORD *)(*(_QWORD *)(v1 + 8) + 9676LL) & 0x2000) != 0 )
    {
      v19 = *(_QWORD *)v1;
      v21 = FVE_EOW_FS_SWEEP_COMPLETE;
      v22 = 0;
      FveLogEvent(v19, &v21);
    }
    FveEowFinalSweepStart(v1, 0);
  }
  if ( v26 )
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
0x14007dbf0  push    rbp
0x14007dbf2  push    rbx
0x14007dbf3  push    rsi
0x14007dbf4  push    rdi
0x14007dbf5  push    r12
0x14007dbf7  push    r13
0x14007dbf9  push    r14
0x14007dbfb  push    r15
0x14007dbfd  lea     rbp, [rsp-1Fh]
0x14007dc02  sub     rsp, 0E8h
0x14007dc09  mov     rbx, [rcx]
0x14007dc0c  mov     r14, rcx
0x14007dc0f  lea     rcx, [rbp+57h+var_D0]; void *
0x14007dc13  mov     [rsp+120h+var_F0], 0
0x14007dc1c  xor     edx, edx; Val
0x14007dc1e  mov     r8d, 90h; Size
0x14007dc24  call    memset
0x14007dc29  xor     r13d, r13d
0x14007dc2c  mov     [rbp+57h+arg_10], 0
0x14007dc30  xor     r12d, r12d
0x14007dc33  xor     r15d, r15d
0x14007dc36  mov     [rbp+57h+arg_8], r12b
0x14007dc3a  mov     [rbp+57h+arg_18], r15
0x14007dc3e  lea     edi, [r13+1]
0x14007dc42  mov     [rbp+57h+arg_0], dil
0x14007dc46  mov     rcx, cs:WPP_GLOBAL_Control
0x14007dc4d  lea     rax, WPP_GLOBAL_Control
0x14007dc54  cmp     rcx, rax
0x14007dc57  jz      short loc_14007DC7D
0x14007dc59  test    dword ptr [rcx+2Ch], 100h
0x14007dc60  jz      short loc_14007DC7D
0x14007dc62  cmp     byte ptr [rcx+29h], 5
0x14007dc66  jb      short loc_14007DC7D
0x14007dc68  mov     rcx, [rcx+18h]
0x14007dc6c  lea     r8, WPP_e3882f5f78b938fff15e86bae05ee61a_Traceguids
0x14007dc73  mov     edx, 0E6h
0x14007dc78  call    WPP_SF_
0x14007dc7d  lea     rcx, [rbx+38h]; BugCheckParameter2
0x14007dc81  call    FvepAcquireRemoveLock
0x14007dc86  mov     esi, eax
0x14007dc88  test    eax, eax
0x14007dc8a  js      loc_14007DD3A
0x14007dc90  test    dword ptr [rbx+328h], 100h
0x14007dc9a  mov     [rbp+57h+arg_10], dil
0x14007dc9e  jz      loc_14007DD35
0x14007dca4  mov     rax, [rbx+2E0h]
0x14007dcab  test    rax, rax
0x14007dcae  jz      loc_14007DD35
0x14007dcb4  mov     rcx, [rax]
0x14007dcb7  test    rcx, rcx
0x14007dcba  jz      short loc_14007DD35
0x14007dcbc  mov     rax, [rbx+3D0h]
0x14007dcc3  test    rax, rax
0x14007dcc6  jz      short loc_14007DD35
0x14007dcc8  mov     dil, [rcx+30h]
0x14007dccc  mov     r13, [rax+38h]
0x14007dcd0  shr     dil, 1
0x14007dcd3  not     dil
0x14007dcd6  mov     [rsp+120h+var_F0], rcx
0x14007dcdb  and     dil, 1
0x14007dcdf  mov     [rbp+57h+arg_0], dil
0x14007dce3  call    Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline
0x14007dce8  test    eax, eax
0x14007dcea  jz      short loc_14007DCF5
0x14007dcec  test    byte ptr [rbx+1133h], 8
0x14007dcf3  jnz     short loc_14007DD07
0x14007dcf5  mov     rax, [rbx+3D0h]
0x14007dcfc  mov     edi, 1
0x14007dd01  cmp     [rax+0Ah], di
0x14007dd05  jnz     short loc_14007DD0B
0x14007dd07  xor     eax, eax
0x14007dd09  jmp     short loc_14007DD13
0x14007dd0b  mov     eax, [rax+1Ch]
0x14007dd0e  test    eax, eax
0x14007dd10  cmovz   eax, edi
0x14007dd13  mov     r12d, [rbx+51Ch]
0x14007dd1a  imul    r12, rax
0x14007dd1e  bts     dword ptr [rbx+328h], 11h
0x14007dd26  mov     rax, gs:188h
0x14007dd2f  mov     [r14+10h], rax
0x14007dd33  jmp     short loc_14007DD3A
0x14007dd35  mov     esi, 0C0000001h
0x14007dd3a  lea     rcx, [r14+70h]; Event
0x14007dd3e  xor     r8d, r8d; Wait
0x14007dd41  xor     edx, edx; Increment
0x14007dd43  call    cs:__imp_KeSetEvent
0x14007dd4a  nop     dword ptr [rax+rax+00h]
0x14007dd4f  test    esi, esi
0x14007dd51  js      loc_14007DFF9
0x14007dd57  lea     rcx, [r14+58h]
0x14007dd5b  call    FveEowCheckSweepStop
0x14007dd60  test    eax, eax
0x14007dd62  js      loc_14007DFF9
0x14007dd68  mov     rcx, gs:188h
0x14007dd71  mov     edx, 4
0x14007dd76  call    cs:__imp_KeSetActualBasePriorityThread
0x14007dd7d  nop     dword ptr [rax+rax+00h]
0x14007dd82  lea     rax, [r12+r13]
0x14007dd86  cmp     rax, r13
0x14007dd89  jb      loc_14007DFF4
0x14007dd8f  xor     edi, edi
0x14007dd91  lea     rdx, [rbp+57h+var_D0]
0x14007dd95  mov     rcx, rbx
0x14007dd98  lea     esi, [rdi+1]
0x14007dd9b  mov     r8b, sil
0x14007dd9e  call    FvepAcquireDevFveLock
0x14007dda3  test    dword ptr [rbx+328h], 100h
0x14007ddad  jz      short loc_14007DDDF
0x14007ddaf  mov     rax, [rbx+2E0h]
0x14007ddb6  test    rax, rax
0x14007ddb9  jz      short loc_14007DDDF
0x14007ddbb  cmp     [rax], rdi
0x14007ddbe  jz      short loc_14007DDDF
0x14007ddc0  mov     edi, esi
0x14007ddc2  lock xadd [rbx+2E8h], edi
0x14007ddca  add     edi, esi
0x14007ddcc  cmp     edi, esi
0x14007ddce  jle     loc_14007DE9C
0x14007ddd4  mov     r15, [rbx+5D8h]
0x14007dddb  mov     [rbp+57h+arg_18], r15
0x14007dddf  lea     rcx, [rbp+57h+var_D0]
0x14007dde3  xor     esi, esi
0x14007dde5  call    FvepReleaseDevFveLock
0x14007ddea  test    edi, edi
0x14007ddec  jle     short loc_14007DE38
0x14007ddee  mov     rcx, rbx; BugCheckParameter2
0x14007ddf1  call    FveEowCtrlVolumeInfoInit
0x14007ddf6  mov     esi, eax
0x14007ddf8  test    eax, eax
0x14007ddfa  js      loc_14007DFF9
0x14007de00  test    r15, r15
0x14007de03  jnz     short loc_14007DE38
0x14007de05  mov     rax, [rbx+2E0h]
0x14007de0c  lea     r8, [rbp+57h+arg_18]
0x14007de10  mov     rdx, [rax]
0x14007de13  mov     ecx, [rax+94h]; ullMultiplier
0x14007de19  mov     rdx, [rdx+38h]
0x14007de1d  call    FveConvCreateUsedBitmap
0x14007de22  mov     esi, eax
0x14007de24  test    eax, eax
0x14007de26  js      loc_14007DFF9
0x14007de2c  mov     rdx, [rbp+57h+arg_18]
0x14007de30  mov     rcx, rbx
0x14007de33  call    FveConvSetUsedBitmap
0x14007de38  mov     eax, [r14+90h]
0x14007de3f  cmp     [r14+8Ch], eax
0x14007de46  jnb     loc_14007DFD5
0x14007de4c  lea     rdi, [r12+r13]
0x14007de50  lea     rcx, [r14+58h]
0x14007de54  call    FveEowCheckSweepStop
0x14007de59  test    eax, eax
0x14007de5b  js      loc_14007DFD5
0x14007de61  cmp     [rbp+57h+arg_0], 0
0x14007de65  mov     rax, [rbx+2E0h]
0x14007de6c  mov     edx, [r14+8Ch]
0x14007de73  mov     rcx, [rax+10h]
0x14007de77  mov     r8, [rcx+rdx*8]
0x14007de7b  jz      short loc_14007DEBD
0x14007de7d  cmp     byte ptr [r8+0Ch], 0
0x14007de82  jnz     loc_14007DF99
0x14007de88  mov     eax, [r8+14h]
0x14007de8c  mov     rcx, [r8+rax*8+30h]
0x14007de91  test    byte ptr [rcx+1Ch], 1
0x14007de95  jz      short loc_14007DEDB
0x14007de97  jmp     loc_14007DF99
0x14007de9c  xor     r9d, r9d; BugCheckParameter3
0x14007de9f  mov     [rsp+120h+BugCheckParameter4], r15; BugCheckParameter4
0x14007dea4  xor     r8d, r8d; BugCheckParameter2
0x14007dea7  mov     ecx, 120h; BugCheckCode
0x14007deac  lea     edx, [r9+0Ch]; BugCheckParameter1
0x14007deb0  call    cs:__imp_KeBugCheckEx
0x14007debd  cmp     byte ptr [r8+0Dh], 0
0x14007dec2  jnz     loc_14007DF99
0x14007dec8  mov     eax, [r8+14h]
0x14007decc  mov     rcx, [r8+rax*8+30h]
0x14007ded1  test    byte ptr [rcx+1Ch], 2
0x14007ded5  jnz     loc_14007DF99
0x14007dedb  mov     rdx, [r8+54h]
0x14007dedf  mov     r8, [r8+5Ch]
0x14007dee3  cmp     rdx, r13
0x14007dee6  jb      short loc_14007DF02
0x14007dee8  cmp     rdx, rdi
0x14007deeb  jnb     short loc_14007DF02
0x14007deed  cmp     rdx, r13
0x14007def0  jnz     loc_14007DF99
0x14007def6  cmp     r8, r12
0x14007def9  jnz     loc_14007DF99
0x14007deff  sub     rdx, r13
0x14007df02  mov     rcx, rbx
0x14007df05  call    FveConvPrepareUsedBitmap
0x14007df0a  mov     esi, eax
0x14007df0c  test    eax, eax
0x14007df0e  js      loc_14007DF99
0x14007df14  mov     edx, [r14+8Ch]
0x14007df1b  mov     r9, r12
0x14007df1e  mov     r8, r13
0x14007df21  mov     rcx, rbx
0x14007df24  call    FveEowGetRegionVolumeBitmap
0x14007df29  mov     esi, eax
0x14007df2b  test    eax, eax
0x14007df2d  js      short loc_14007DF99
0x14007df2f  mov     rax, [rsp+120h+var_F0]
0x14007df34  mov     eax, [rax+20Ch]
0x14007df3a  cmp     [r14+8Ch], eax
0x14007df41  jnz     short loc_14007DF99
0x14007df43  mov     r8, r12
0x14007df46  mov     rdx, r13
0x14007df49  mov     rcx, r14
0x14007df4c  call    FveEowFreeSweepProcessRegion
0x14007df51  mov     esi, eax
0x14007df53  test    eax, eax
0x14007df55  jns     short loc_14007DF99
0x14007df57  mov     rcx, cs:WPP_GLOBAL_Control
0x14007df5e  lea     rax, WPP_GLOBAL_Control
0x14007df65  cmp     rcx, rax
0x14007df68  jz      short loc_14007DF99
0x14007df6a  test    dword ptr [rcx+2Ch], 100h
0x14007df71  jz      short loc_14007DF99
0x14007df73  cmp     byte ptr [rcx+29h], 2
0x14007df77  jb      short loc_14007DF99
0x14007df79  mov     r9d, [r14+8Ch]
0x14007df80  lea     r8, WPP_e3882f5f78b938fff15e86bae05ee61a_Traceguids
0x14007df87  mov     rcx, [rcx+18h]
0x14007df8b  mov     edx, 0E7h
0x14007df90  mov     dword ptr [rsp+120h+BugCheckParameter4], esi
0x14007df94  call    WPP_SF_Dd
0x14007df99  xor     r9d, r9d; Alertable
0x14007df9c  mov     [rsp+120h+BugCheckParameter4], 0; Timeout
0x14007dfa5  xor     r8d, r8d; WaitMode
0x14007dfa8  lea     rcx, [r14+70h]; Object
0x14007dfac  xor     edx, edx; WaitReason
0x14007dfae  call    cs:__imp_KeWaitForSingleObject
0x14007dfb5  nop     dword ptr [rax+rax+00h]
0x14007dfba  inc     dword ptr [r14+8Ch]
0x14007dfc1  mov     eax, [r14+8Ch]
0x14007dfc8  cmp     eax, [r14+90h]
0x14007dfcf  jb      loc_14007DE50
0x14007dfd5  mov     eax, [r14+90h]
0x14007dfdc  cmp     [r14+8Ch], eax
0x14007dfe3  jb      short loc_14007DFF9
0x14007dfe5  mov     rax, [rsp+120h+var_F0]
0x14007dfea  mov     [rbp+57h+arg_8], 1
0x14007dfee  or      byte ptr [rax+30h], 8
0x14007dff2  jmp     short loc_14007DFF9
0x14007dff4  mov     esi, 0C0000095h
0x14007dff9  xor     edx, edx
0x14007dffb  mov     rcx, r14
0x14007dffe  call    FveEowFreeSweepStopThread
0x14007e003  mov     rcx, r14; P
0x14007e006  mov     qword ptr [r14+10h], 0
0x14007e00e  call    FveEowFreeSweepCtrlFree
0x14007e013  mov     r14d, 1
0x14007e019  lea     rdx, [rbp+57h+var_D0]
0x14007e01d  mov     r8b, r14b
0x14007e020  mov     rcx, rbx
0x14007e023  call    FvepAcquireDevFveLock
0x14007e028  btr     dword ptr [rbx+328h], 11h
0x14007e030  lea     rcx, [rbp+57h+var_D0]
0x14007e034  call    FvepReleaseDevFveLock
0x14007e039  lea     edx, [r14+15h]
0x14007e03d  mov     rcx, rbx
0x14007e040  call    FveRaiseStatusChangedEvent
0x14007e045  cmp     [rbp+57h+arg_8], 0
0x14007e049  jz      short loc_14007E099
0x14007e04b  movzx   edx, [rbp+57h+arg_0]
0x14007e04f  mov     rcx, rbx
0x14007e052  xor     edx, r14d
0x14007e055  add     edx, 18h
0x14007e058  call    FveRaiseStatusChangedEvent
0x14007e05d  mov     rax, [rbx+8]
0x14007e061  test    dword ptr [rax+25CCh], 2000h
0x14007e06b  jz      short loc_14007E08F
0x14007e06d  mov     rcx, [rbx]
0x14007e070  lea     rax, FVE_EOW_FS_SWEEP_COMPLETE
0x14007e077  xorps   xmm0, xmm0
0x14007e07a  mov     [rsp+120h+var_E8], rax
0x14007e07f  lea     rdx, [rsp+120h+var_E8]
0x14007e084  movdqu  [rsp+120h+var_E0], xmm0
0x14007e08a  call    FveLogEvent
0x14007e08f  xor     edx, edx
0x14007e091  mov     rcx, rbx
0x14007e094  call    FveEowFinalSweepStart
0x14007e099  cmp     [rbp+57h+arg_10], 0
0x14007e09d  jz      short loc_14007E0A8
0x14007e09f  lea     rcx, [rbx+38h]; BugCheckParameter2
0x14007e0a3  call    FvepReleaseRemoveLock
0x14007e0a8  mov     rcx, cs:WPP_GLOBAL_Control
0x14007e0af  lea     rax, WPP_GLOBAL_Control
0x14007e0b6  cmp     rcx, rax
0x14007e0b9  jz      short loc_14007E0E2
0x14007e0bb  test    dword ptr [rcx+2Ch], 100h
0x14007e0c2  jz      short loc_14007E0E2
0x14007e0c4  cmp     byte ptr [rcx+29h], 5
0x14007e0c8  jb      short loc_14007E0E2
0x14007e0ca  mov     rcx, [rcx+18h]
0x14007e0ce  lea     r8, WPP_e3882f5f78b938fff15e86bae05ee61a_Traceguids
0x14007e0d5  mov     edx, 0E8h
0x14007e0da  mov     r9d, esi
0x14007e0dd  call    WPP_SF_d
0x14007e0e2  add     rsp, 0E8h
  ... truncated ...
```
