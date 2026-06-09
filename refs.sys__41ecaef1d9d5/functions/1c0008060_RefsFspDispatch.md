# RefsFspDispatch

- ea: `0x1c0008060`
- end: `0x1c0008a0e`
- name: `RefsFspDispatch`
- size: `2478`
- prototype: `KSTART_ROUTINE`
- caller_count: `1`
- callee_count: `36`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x1c01cdfdc`

## callees

- `0x1c0008060`
- `0x1c0009230`
- `0x1c000a190`
- `0x1c000dc80`
- `0x1c000f770`
- `0x1c00133b0`
- `0x1c0013f90`
- `0x1c003aa60`
- `0x1c003fd04`
- `0x1c004d164`
- `0x1c00588cc`
- `0x1c00592b0`
- `0x1c005bb10`
- `0x1c0062ce0`
- `0x1c0068960`
- `0x1c006af80`
- `0x1c009d564`
- `0x1c00a7c98`
- `0x1c00b3dc8`
- `0x1c014d9fc`
- `0x1c01572e0`
- `0x1c015c010`
- `0x1c015eb64`
- `0x1c0161d70`
- `0x1c0162414`
- `0x1c016aed4`
- `0x1c0174858`
- `0x1c0179bd4`
- `0x1c017b25c`
- `0x1c0196bc8`
- `0x1c01a3f68`
- `0x1c01a40d0`
- `0x1c01bea90`
- `0x1c01c5714`
- `0x1c01cd29c`
- `0x1c01d3c80`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x1c0008570`
- `ntoskrnl!KeInitializeEvent` at `0x1c0008570`
- `ntoskrnl!ObfDereferenceObject` at `0x1c00089b2`
- `ntoskrnl!ObfDereferenceObject` at `0x1c00089b2`
- `ntoskrnl!KeBugCheckEx` at `0x1c00084ee`
- `ntoskrnl!KeBugCheckEx` at `0x1c00084ee`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1c00081a3`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1c0008297`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1c00082d2`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1c00081a3`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1c0008297`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1c00082d2`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1c0008236`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1c0008236`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c0008168`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1c0008168`
- `ntoskrnl!IoClearActivityIdThread` at `0x1c000888a`
- `ntoskrnl!IoClearActivityIdThread` at `0x1c000888a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c0008896`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1c0008896`
- `ntoskrnl!KeSetEvent` at `0x1c006fccf`
- `ntoskrnl!KeSetEvent` at `0x1c006fccf`
- `ntoskrnl!ObfReferenceObject` at `0x1c00088f4`
- `ntoskrnl!ObfReferenceObject` at `0x1c00088f4`
- `ntoskrnl!IoSetActivityIdThread` at `0x1c000818c`
- `ntoskrnl!IoSetActivityIdThread` at `0x1c000818c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1c0008935`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1c006fc52`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1c0008935`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1c006fc52`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c00089a1`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c006fc43`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c006fcb0`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c00089a1`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c006fc43`
- `ntoskrnl!KeReleaseSpinLock` at `0x1c006fcb0`
- `ntoskrnl!KeReleaseSemaphore` at `0x1c00089f4`
- `ntoskrnl!KeReleaseSemaphore` at `0x1c00089f4`
- `ntoskrnl!CcCanIWrite` at `0x1c000838b`
- `ntoskrnl!CcCanIWrite` at `0x1c000838b`
- `ntoskrnl!IoClearFsTrackOffsetState` at `0x1c000844d`
- `ntoskrnl!IoClearFsTrackOffsetState` at `0x1c000844d`
- `ntoskrnl!IoWithinStackLimits` at `0x1c00081ba`
- `ntoskrnl!IoWithinStackLimits` at `0x1c00081ba`

## pseudocode

```c
void __fastcall RefsFspDispatch(char *StartContext)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rcx
  IRP *v3; // rdi
  int v4; // eax
  int v5; // r12d
  int v6; // r13d
  PDEVICE_OBJECT v7; // rcx
  _OWORD *v8; // rax
  _QWORD *v9; // rcx
  bool v10; // r15
  ULONG_PTR TopLevelIrp; // rsi
  __int64 v12; // r8
  __int64 v13; // r9
  __int64 v14; // rcx
  IRP *v15; // rax
  __int64 v16; // rsi
  __int64 v17; // rcx
  char v18; // cl
  int v19; // eax
  __int64 v20; // rax
  __int64 v21; // rax
  unsigned int v22; // ecx
  int v23; // eax
  __int64 v24; // rsi
  __int64 v25; // r8
  __int64 v26; // r8
  PDEVICE_OBJECT DeviceObject; // rsi
  _DWORD *v28; // r15
  KSPIN_LOCK *v29; // rsi
  KIRQL v30; // r12
  _QWORD *v31; // r15
  _DWORD *v32; // r13
  int v33; // eax
  __int64 v34; // rcx
  _QWORD *v35; // rax
  bool v36; // [rsp+30h] [rbp-348h]
  char v37; // [rsp+31h] [rbp-347h]
  bool v38; // [rsp+32h] [rbp-346h]
  int v39; // [rsp+34h] [rbp-344h]
  int v40; // [rsp+38h] [rbp-340h]
  int v41; // [rsp+3Ch] [rbp-33Ch]
  int v42; // [rsp+40h] [rbp-338h]
  char *v43; // [rsp+48h] [rbp-330h]
  char *v44; // [rsp+50h] [rbp-328h]
  PDEVICE_OBJECT Object; // [rsp+58h] [rbp-320h]
  int v46; // [rsp+60h] [rbp-318h]
  _BYTE Irp[400]; // [rsp+70h] [rbp-308h] BYREF
  _QWORD v48[41]; // [rsp+200h] [rbp-178h] BYREF

  memset(Irp, 0, 40);
  CurrentStackLocation = 0;
  v42 = 0;
  v41 = 0;
  Object = 0;
  v38 = 0;
  v39 = 0;
  memset(&Irp[64], 0, 24);
  v43 = StartContext;
  *((_QWORD *)StartContext + 15) = StartContext + 112;
  *((_QWORD *)StartContext + 14) = StartContext + 112;
  v3 = (IRP *)*((_QWORD *)StartContext + 9);
  *(_QWORD *)&Irp[40] = v3;
  if ( v3 )
    CurrentStackLocation = v3->Tail.Overlay.CurrentStackLocation;
  v4 = *((_DWORD *)StartContext + 1);
  v5 = v4 & 0x4000000;
  v46 = v4 & 0x4000000;
  v6 = *((_DWORD *)StartContext + 2) & 0x1000;
  v40 = v6;
  v36 = (v4 & 1) != 0;
  *((_DWORD *)StartContext + 1) = v4 & 0xFFFFFFFE;
  *((_DWORD *)StartContext + 2) |= 1u;
  if ( (v4 & 0x4000000) != 0 )
  {
    v7 = 0;
  }
  else
  {
    if ( v3 && CurrentStackLocation->FileObject )
    {
      DeviceObject = CurrentStackLocation->DeviceObject;
      Object = DeviceObject;
      ObfReferenceObject(DeviceObject);
      v7 = DeviceObject;
    }
    else
    {
      v7 = 0;
      Object = 0;
    }
    v38 = (*((_DWORD *)StartContext + 1) & 0x400000) != 0;
  }
  v44 = (char *)v7;
  do
  {
    memset(&v48[38], 0, 24);
    KeEnterCriticalRegion();
    v8 = (_OWORD *)*((_QWORD *)StartContext + 10);
    if ( v8 )
    {
      *(_OWORD *)&v48[39] = *v8;
      v9 = &v48[39];
    }
    else
    {
      v9 = 0;
    }
    v48[38] = v9;
    *(_QWORD *)&Irp[56] = IoSetActivityIdThread(v9);
    v10 = 0;
    TopLevelIrp = (ULONG_PTR)IoGetTopLevelIrp();
    if ( IoWithinStackLimits(TopLevelIrp, 0x28u) && (TopLevelIrp & 3) == 0 )
      v10 = *(_DWORD *)(TopLevelIrp + 4) == 1397140410;
    *(_DWORD *)&Irp[4] = 0;
    *(_QWORD *)&Irp[24] = TopLevelIrp;
    v14 = 0;
    *(_QWORD *)&Irp[32] = 0;
    Irp[0] = 1;
    if ( v10 )
    {
      *(_QWORD *)&Irp[8] = *(_QWORD *)(TopLevelIrp + 8);
      *(_QWORD *)&Irp[16] = *(_QWORD *)(TopLevelIrp + 16);
      Irp[1] = 1;
      Irp[2] = *(_BYTE *)(TopLevelIrp + 2);
    }
    else
    {
      *(_OWORD *)&Irp[8] = 0;
      *(_WORD *)&Irp[1] = 0;
    }
    v15 = (IRP *)Irp;
    *(_QWORD *)&Irp[48] = Irp;
    ++RefsPostRequests;
    while ( 1 )
    {
      if ( !v14 )
      {
        *(_DWORD *)&Irp[4] = 1397140410;
        *(_QWORD *)&Irp[32] = StartContext;
        *((_DWORD *)StartContext + 2) |= 0x100000u;
        IoSetTopLevelIrp(v15);
        v14 = *(_QWORD *)&Irp[32];
      }
      *((_QWORD *)StartContext + 13) = v14;
      if ( (*((_DWORD *)StartContext + 2) & 0x2000) != 0 )
        Irp[0] = 0;
      v37 = 0;
      *((_DWORD *)StartContext + 4) = 0;
      *((_DWORD *)StartContext + 2) |= 0x40u;
      if ( v6 && !v5 )
        *((_DWORD *)StartContext + 1) |= 0x8000000u;
      if ( v39 == -1073741432 || !v3 )
      {
        RefsCheckpointForLogFileFull(StartContext);
        if ( (unsigned int)++v42 >= 2 )
          *((_DWORD *)StartContext + 1) |= 0x10u;
        v39 = 0;
      }
      v16 = *((_QWORD *)StartContext + 9);
      if ( StartContext == *((char **)StartContext + 13) )
      {
        if ( LOBYTE(IoGetTopLevelIrp()->Type) )
        {
          v17 = *((_QWORD *)StartContext + 8);
          if ( v17 )
          {
            if ( v16 && *(_QWORD *)(v17 + 104) && (unsigned __int8)MsVolumeHasReadCache() )
              IoClearFsTrackOffsetState(v16);
          }
        }
        if ( StartContext == *((char **)StartContext + 13) )
        {
          if ( LOBYTE(IoGetTopLevelIrp()->Type) )
          {
            v18 = StartContext[40];
            if ( !v18 || v18 == 13 )
            {
              v20 = *((_QWORD *)StartContext + 8);
              if ( v20 )
              {
                if ( (*(_DWORD *)(v20 + 4) & 1) != 0 )
                {
                  v21 = *(_QWORD *)(v16 + 184);
                  if ( v18 )
                  {
                    if ( *(_DWORD *)(v21 + 24) == 589988 )
                      goto LABEL_45;
                  }
                  else
                  {
                    v22 = *(unsigned __int8 *)(v21 + 19);
                    if ( (*(_DWORD *)(v21 + 16) & 1) != 0
                      && (*((_DWORD *)StartContext + 2) & 8) == 0
                      && (unsigned __int8)v22 <= 5u )
                    {
                      v23 = 53;
                      if ( _bittest(&v23, v22) )
LABEL_45:
                        CcCanIWrite(0, 0x80000u, 1u, 0);
                    }
                  }
                }
              }
            }
          }
        }
      }
      v19 = *((_DWORD *)StartContext + 1);
      if ( (v19 & 0x200000) != 0 )
      {
        *((_DWORD *)StartContext + 1) = v19 & 0xFFDFFFFF;
        RefsPerformVerify(StartContext, v16);
      }
      if ( v3 )
      {
        if ( StartContext[40] == 4 )
        {
          if ( (*((_DWORD *)StartContext + 2) & 0x1000) != 0 )
          {
LABEL_37:
            RefsCommonIoCompletionWorker(StartContext, v3);
          }
          else
          {
            memset(v48, 0, 0x130u);
            v26 = v3->Flags >> 1;
            LOBYTE(v26) = (v3->Flags & 2) != 0;
            RefsInitializeIoContext(StartContext, v48, v26);
            RefsCommonWrite((LARGE_INTEGER *)StartContext, v3);
          }
        }
        else
        {
          switch ( StartContext[40] )
          {
            case 0:
              *((_DWORD *)StartContext + 2) &= ~2u;
              v24 = *((_QWORD *)StartContext + 18);
              if ( (*((_DWORD *)StartContext + 2) & 0x200) != 0 )
              {
                v39 = RefsCommonVolumeOpen((__int64)StartContext, (__int64)v3, v12, v13);
              }
              else
              {
                memset(*((void **)StartContext + 18), 0, 0xD0u);
                *(_QWORD *)(v24 + 168) = v3->Tail.Overlay.CurrentStackLocation;
                v39 = RefsCommonCreate((__int64)StartContext, v3, v24);
              }
              break;
            case 2:
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
              {
                WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_62cfa6b095873b3bbf6f1190074bbaa9_Traceguids);
              }
              KeBugCheckEx(0x149u, 0x130149u, 0, 0, 0);
            case 3:
              if ( (*((_DWORD *)StartContext + 2) & 0x1000) != 0 )
                goto LABEL_37;
              memset(&Irp[96], 0, 0x130u);
              v25 = v3->Flags >> 1;
              LOBYTE(v25) = (v3->Flags & 2) != 0;
              RefsInitializeIoContext(StartContext, &Irp[96], v25);
              RefsCommonRead((__int64)StartContext, v3);
              break;
            case 5:
              RefsCommonQueryInformation(StartContext, v3);
              break;
            case 6:
              KeInitializeEvent((PRKEVENT)&Irp[64], NotificationEvent, 0);
              *((_QWORD *)StartContext + 19) = &Irp[64];
              v39 = RefsCommonSetInformation(StartContext);
              if ( v39 == 871 )
              {
                RefsWaitForOplockCompletionEvent(v3, (PRKEVENT)&Irp[64]);
                v37 = 1;
              }
              break;
            case 9:
              RefsCommonFlushBuffers(StartContext, v3);
              break;
            case 10:
              RefsCommonQueryVolumeInfo(StartContext, v3);
              break;
            case 11:
              RefsCommonSetVolumeInfo(StartContext, v3);
              break;
            case 12:
              RefsCommonDirectoryControl((_DWORD)StartContext, (_DWORD)v3);
              break;
            case 13:
              RefsCommonFileSystemControl(StartContext, v3);
              break;
            case 14:
              RefsCommonDeviceControl(StartContext, v3);
              break;
            case 17:
              RefsCommonLockControl(StartContext, v3);
              break;
            case 18:
              RefsCommonCleanup(StartContext, v3);
              break;
            case 20:
              RefsCommonQuerySecurityInfo(StartContext, v3);
              break;
            case 21:
              RefsCommonSetSecurityInfo(StartContext, v3);
              break;
            default:
              if ( RefsStatusDebugEnabled )
                RefsStatusDebug(-1073741808);
              StartContext = v43;
              RefsExtendedCompleteRequestInternal(v43, v3, 3221225488LL);
              break;
          }
        }
      }
      else
      {
        if ( RefsStatusDebugEnabled )
          RefsStatusDebug(0);
        RefsExtendedCompleteRequestInternal(v43, 0, 0);
        StartContext = 0;
        v43 = 0;
      }
      if ( !v37 )
        break;
      v14 = *(_QWORD *)&Irp[32];
      v15 = *(IRP **)&Irp[48];
    }
    IoClearActivityIdThread(*(_QWORD *)&Irp[56]);
    KeLeaveCriticalRegion();
    if ( v5 )
      return;
    if ( !Object )
    {
      if ( v38 )
        KeReleaseSemaphore(&RefsGlobalPostThrottle, 0, 1, 0);
      return;
    }
    v28 = v44;
    v29 = (KSPIN_LOCK *)(v44 + 3568);
    v30 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v44 + 446);
    if ( v36 )
      --*((_DWORD *)v44 + 853);
    while ( 2 )
    {
      if ( v6 || !v28[856] && !v28[868] )
      {
        v31 = 0;
        v32 = 0;
        v33 = v40;
        if ( !v40 || !*((_DWORD *)v44 + 880) )
          goto LABEL_96;
        v6 = v40;
        v28 = v44;
      }
      if ( v6 )
      {
        v32 = 0;
        if ( v28[880] )
          v32 = v28 + 880;
      }
      else
      {
        v32 = v28 + 868;
        if ( !v28[868] || v28[853] )
        {
          v41 = 0;
          v32 = 0;
          if ( v28[856] )
            v32 = v28 + 856;
        }
        else
        {
          if ( (unsigned int)++v41 > 0x14 || !v28[856] )
          {
            v41 = 0;
            v28[853] = 1;
            v36 = 1;
            goto LABEL_124;
          }
          v32 = v28 + 856;
        }
        v36 = 0;
      }
LABEL_124:
      if ( !v32 )
      {
        v33 = v40;
        goto LABEL_98;
      }
      v31 = (_QWORD *)*((_QWORD *)v32 + 4);
      StartContext = (char *)(v31 - 14);
      v43 = (char *)(v31 - 14);
      v3 = (IRP *)*(v31 - 5);
      *(_QWORD *)&Irp[40] = v3;
      if ( !v40 && !(unsigned __int8)RefsClearCancelRoutine(v3) )
      {
        v28 = v44;
        if ( v36 )
          --*((_DWORD *)v44 + 853);
        KeReleaseSpinLock(v29, v30);
        v30 = KeAcquireSpinLockRaiseToDpc(v29);
        v6 = 0;
        continue;
      }
      break;
    }
    --*v32;
    v34 = *v31;
    v35 = (_QWORD *)v31[1];
    if ( *(_QWORD **)(*v31 + 8LL) != v31 || (_QWORD *)*v35 != v31 )
      __fastfail(3u);
    *v35 = v34;
    *(_QWORD *)(v34 + 8) = v35;
    v31[1] = v31;
    *v31 = v31;
    v33 = v40;
LABEL_96:
    if ( !v31 )
    {
      v28 = v44;
LABEL_98:
      if ( v33 )
        --v28[854];
      else
        --v28[852];
      KeReleaseSpinLock(v29, v30);
      ObfDereferenceObject(Object);
      return;
    }
    KeReleaseSpinLock(v29, v30);
    if ( *v32 < 0x3E8u )
      KeSetEvent((PRKEVENT)(v32 + 2), 0, 0);
    v42 = 0;
    *((_DWORD *)StartContext + 2) |= 1u;
    v5 = v46;
    v6 = v40;
  }
  while ( !v46 );
}

```

## disassembly

```asm
0x1c0008060  mov     [rsp+arg_8], rbx
0x1c0008065  mov     [rsp+arg_10], rsi
0x1c000806a  push    rdi
0x1c000806b  push    r12
0x1c000806d  push    r13
0x1c000806f  push    r14
0x1c0008071  push    r15
0x1c0008073  sub     rsp, 350h
0x1c000807a  mov     rax, cs:__security_cookie
0x1c0008081  xor     rax, rsp
0x1c0008084  mov     [rsp+378h+var_30], rax
0x1c000808c  mov     rbx, rcx
0x1c000808f  xorps   xmm0, xmm0
0x1c0008092  xor     eax, eax
0x1c0008094  movups  xmmword ptr [rsp+378h+Irp], xmm0
0x1c0008099  movups  xmmword ptr [rsp+378h+Irp+10h], xmm0
0x1c00080a1  mov     qword ptr [rsp+378h+Irp+20h], rax
0x1c00080a9  xor     r14d, r14d
0x1c00080ac  mov     ecx, r14d
0x1c00080af  mov     [rsp+378h+var_338], r14d
0x1c00080b4  mov     [rsp+378h+var_33C], r14d
0x1c00080b9  mov     [rsp+378h+Object], r14
0x1c00080be  mov     [rsp+378h+var_346], al
0x1c00080c2  mov     [rsp+378h+var_344], r14d
0x1c00080c7  movups  xmmword ptr [rsp+378h+Irp+40h], xmm0
0x1c00080cf  mov     qword ptr [rsp+378h+Irp+50h], rax
0x1c00080d7  mov     [rsp+378h+var_330], rbx
0x1c00080dc  lea     rax, [rbx+70h]
0x1c00080e0  mov     [rax+8], rax
0x1c00080e4  mov     [rax], rax
0x1c00080e7  mov     rdi, [rbx+48h]
0x1c00080eb  mov     qword ptr [rsp+378h+Irp+28h], rdi
0x1c00080f3  test    rdi, rdi
0x1c00080f6  jz      short loc_1C00080FF
0x1c00080f8  mov     rcx, [rdi+0B8h]
0x1c00080ff  mov     eax, [rbx+4]
0x1c0008102  mov     r12d, eax
0x1c0008105  and     r12d, 4000000h
0x1c000810c  mov     [rsp+378h+var_318], r12d
0x1c0008111  mov     [rsp+378h+var_314], r12d
0x1c0008116  mov     r13d, [rbx+8]
0x1c000811a  and     r13d, 1000h
0x1c0008121  mov     [rsp+378h+var_340], r13d
0x1c0008126  mov     [rsp+378h+var_310], r13d
0x1c000812b  test    al, 1
0x1c000812d  jnz     loc_1C006FAB6
0x1c0008133  mov     [rsp+378h+var_348], r14b
0x1c0008138  and     eax, 0FFFFFFFEh
0x1c000813b  mov     [rbx+4], eax
0x1c000813e  or      dword ptr [rbx+8], 1
0x1c0008142  test    r12d, r12d
0x1c0008145  jz      loc_1C00088D5
0x1c000814b  mov     rcx, r14
0x1c000814e  mov     [rsp+378h+var_328], rcx
0x1c0008153  xorps   xmm0, xmm0
0x1c0008156  xor     eax, eax
0x1c0008158  movups  [rsp+378h+var_48], xmm0
0x1c0008160  mov     [rsp+378h+var_38], rax
0x1c0008168  call    cs:__imp_KeEnterCriticalRegion
0x1c000816f  nop     dword ptr [rax+rax+00h]
0x1c0008174  mov     rax, [rbx+50h]
0x1c0008178  test    rax, rax
0x1c000817b  jnz     loc_1C006FAC0
0x1c0008181  mov     rcx, r14
0x1c0008184  mov     qword ptr [rsp+378h+var_48], rcx
0x1c000818c  call    cs:__imp_IoSetActivityIdThread
0x1c0008193  nop     dword ptr [rax+rax+00h]
0x1c0008198  mov     qword ptr [rsp+378h+Irp+38h], rax
0x1c00081a0  xor     r15b, r15b
0x1c00081a3  call    cs:__imp_IoGetTopLevelIrp
0x1c00081aa  nop     dword ptr [rax+rax+00h]
0x1c00081af  mov     rsi, rax
0x1c00081b2  mov     edx, 28h ; '('; RegionSize
0x1c00081b7  mov     rcx, rax; RegionStart
0x1c00081ba  call    cs:__imp_IoWithinStackLimits
0x1c00081c1  nop     dword ptr [rax+rax+00h]
0x1c00081c6  test    eax, eax
0x1c00081c8  jnz     loc_1C006FAD8
0x1c00081ce  mov     dword ptr [rsp+378h+Irp+4], r14d
0x1c00081d3  mov     qword ptr [rsp+378h+Irp+18h], rsi
0x1c00081db  mov     rcx, r14
0x1c00081de  mov     qword ptr [rsp+378h+Irp+20h], rcx
0x1c00081e6  mov     [rsp+378h+Irp], 1
0x1c00081eb  test    r15b, r15b
0x1c00081ee  jnz     loc_1C006FAFB
0x1c00081f4  xorps   xmm0, xmm0
0x1c00081f7  movdqu  xmmword ptr [rsp+378h+Irp+8], xmm0
0x1c00081fd  mov     word ptr [rsp+378h+Irp+1], 0
0x1c0008204  lea     rax, [rsp+378h+Irp]
0x1c0008209  mov     qword ptr [rsp+378h+Irp+30h], rax
0x1c0008211  inc     cs:RefsPostRequests
0x1c0008217  test    rcx, rcx
0x1c000821a  jnz     short loc_1C000824A
0x1c000821c  mov     dword ptr [rsp+378h+Irp+4], 5346ABBAh
0x1c0008224  mov     qword ptr [rsp+378h+Irp+20h], rbx
0x1c000822c  or      dword ptr [rbx+8], 100000h
0x1c0008233  mov     rcx, rax; Irp
0x1c0008236  call    cs:__imp_IoSetTopLevelIrp
0x1c000823d  nop     dword ptr [rax+rax+00h]
0x1c0008242  mov     rcx, qword ptr [rsp+378h+Irp+20h]
0x1c000824a  mov     [rbx+68h], rcx
0x1c000824e  test    dword ptr [rbx+8], 2000h
0x1c0008255  jnz     loc_1C006FB22
0x1c000825b  mov     [rsp+378h+var_347], 0
0x1c0008260  mov     [rbx+10h], r14d
0x1c0008264  or      dword ptr [rbx+8], 40h
0x1c0008268  test    r13d, r13d
0x1c000826b  jz      short loc_1C0008276
0x1c000826d  test    r12d, r12d
0x1c0008270  jz      loc_1C0008419
0x1c0008276  cmp     [rsp+378h+var_344], 0C0000188h
0x1c000827e  jz      loc_1C0008425
0x1c0008284  test    rdi, rdi
0x1c0008287  jz      loc_1C0008425
0x1c000828d  mov     rsi, [rbx+48h]
0x1c0008291  cmp     rbx, [rbx+68h]
0x1c0008295  jnz     short loc_1C00082F0
0x1c0008297  call    cs:__imp_IoGetTopLevelIrp
0x1c000829e  nop     dword ptr [rax+rax+00h]
0x1c00082a3  cmp     byte ptr [rax], 0
0x1c00082a6  jz      short loc_1C00082CC
0x1c00082a8  mov     rcx, [rbx+40h]
0x1c00082ac  test    rcx, rcx
0x1c00082af  jz      short loc_1C00082CC
0x1c00082b1  test    rsi, rsi
0x1c00082b4  jz      short loc_1C00082CC
0x1c00082b6  mov     rcx, [rcx+68h]
0x1c00082ba  test    rcx, rcx
0x1c00082bd  jz      short loc_1C00082CC
0x1c00082bf  call    MsVolumeHasReadCache
0x1c00082c4  test    al, al
0x1c00082c6  jnz     loc_1C000844A
0x1c00082cc  cmp     rbx, [rbx+68h]
0x1c00082d0  jnz     short loc_1C00082F0
0x1c00082d2  call    cs:__imp_IoGetTopLevelIrp
0x1c00082d9  nop     dword ptr [rax+rax+00h]
0x1c00082de  cmp     byte ptr [rax], 0
0x1c00082e1  jz      short loc_1C00082F0
0x1c00082e3  movzx   ecx, byte ptr [rbx+28h]
0x1c00082e7  test    cl, cl
0x1c00082e9  jz      short loc_1C0008330
0x1c00082eb  cmp     cl, 0Dh
0x1c00082ee  jz      short loc_1C0008330
0x1c00082f0  mov     eax, [rbx+4]
0x1c00082f3  bt      eax, 15h
0x1c00082f7  jb      loc_1C0008479
0x1c00082fd  test    rdi, rdi
0x1c0008300  jz      loc_1C00086CB
0x1c0008306  movzx   eax, byte ptr [rbx+28h]
0x1c000830a  cmp     eax, 4
0x1c000830d  jnz     loc_1C000839C
0x1c0008313  test    dword ptr [rbx+8], 1000h
0x1c000831a  jz      loc_1C000868E
0x1c0008320  mov     rdx, rdi
0x1c0008323  mov     rcx, rbx
0x1c0008326  call    RefsCommonIoCompletionWorker
0x1c000832b  jmp     loc_1C0008701
0x1c0008330  mov     rax, [rbx+40h]
0x1c0008334  test    rax, rax
0x1c0008337  jz      short loc_1C00082F0
0x1c0008339  mov     eax, [rax+4]
0x1c000833c  test    al, 1
0x1c000833e  jz      short loc_1C00082F0
0x1c0008340  mov     [rsp+378h+var_345], 0
0x1c0008345  mov     rax, [rsi+0B8h]
0x1c000834c  test    cl, cl
0x1c000834e  jnz     loc_1C000845E
0x1c0008354  movzx   ecx, byte ptr [rax+13h]
0x1c0008358  mov     eax, [rax+10h]
0x1c000835b  test    al, 1
0x1c000835d  jz      short loc_1C00082F0
0x1c000835f  mov     eax, [rbx+8]
0x1c0008362  test    al, 8
0x1c0008364  jnz     short loc_1C00082F0
0x1c0008366  cmp     cl, 5
0x1c0008369  ja      short loc_1C00082F0
0x1c000836b  mov     eax, 35h ; '5'
0x1c0008370  bt      eax, ecx
0x1c0008373  jnb     loc_1C00082F0
0x1c0008379  mov     [rsp+378h+var_345], 1
0x1c000837e  xor     r9d, r9d; Retrying
0x1c0008381  mov     r8b, 1; Wait
0x1c0008384  mov     edx, 80000h; BytesToWrite
0x1c0008389  xor     ecx, ecx; FileObject
0x1c000838b  call    cs:__imp_CcCanIWrite
0x1c0008392  nop     dword ptr [rax+rax+00h]
0x1c0008397  jmp     loc_1C00082F0
0x1c000839c  cmp     eax, 15h; switch 22 cases
0x1c000839f  ja      def_1C00083B6; jumptable 00000001C00083B6 default case, cases 1,4,7,8,15,16,19
0x1c00083a5  lea     rsi, cs:1C0000000h
0x1c00083ac  mov     ecx, ds:(jpt_1C00083B6 - 1C0000000h)[rsi+rax*4]
0x1c00083b3  add     rcx, rsi
0x1c00083b6  jmp     rcx; switch jump
0x1c00083bc  and     dword ptr [rbx+8], 0FFFFFFFDh; jumptable 00000001C00083B6 case 0
0x1c00083c0  mov     rsi, [rbx+90h]
0x1c00083c7  test    dword ptr [rbx+8], 200h
0x1c00083ce  jnz     loc_1C0008490
0x1c00083d4  xor     edx, edx; Val
0x1c00083d6  mov     r8d, 0D0h; Size
0x1c00083dc  mov     rcx, rsi; void *
0x1c00083df  call    memset
0x1c00083e4  mov     rax, [rdi+0B8h]
0x1c00083eb  mov     [rsi+0A8h], rax
0x1c00083f2  mov     r8, rsi
0x1c00083f5  mov     rdx, rdi
0x1c00083f8  mov     rcx, rbx
0x1c00083fb  call    RefsCommonCreate
0x1c0008400  mov     [rsp+378h+var_344], eax
0x1c0008404  jmp     loc_1C0008701
0x1c0008409  mov     rdx, rdi; jumptable 00000001C00083B6 case 13
0x1c000840c  mov     rcx, rbx
0x1c000840f  call    RefsCommonFileSystemControl
0x1c0008414  jmp     loc_1C0008701
0x1c0008419  or      dword ptr [rbx+4], 8000000h
0x1c0008420  jmp     loc_1C0008276
0x1c0008425  mov     rcx, rbx
0x1c0008428  call    RefsCheckpointForLogFileFull
0x1c000842d  mov     eax, [rsp+378h+var_338]
0x1c0008431  inc     eax
0x1c0008433  mov     [rsp+378h+var_338], eax
0x1c0008437  cmp     eax, 2
0x1c000843a  jb      short loc_1C0008440
0x1c000843c  or      dword ptr [rbx+4], 10h
0x1c0008440  mov     [rsp+378h+var_344], r14d
0x1c0008445  jmp     loc_1C000828D
0x1c000844a  mov     rcx, rsi
0x1c000844d  call    cs:__imp_IoClearFsTrackOffsetState
0x1c0008454  nop     dword ptr [rax+rax+00h]
0x1c0008459  jmp     loc_1C00082CC
0x1c000845e  cmp     cl, 0Dh
0x1c0008461  jnz     loc_1C00082F0
0x1c0008467  cmp     dword ptr [rax+18h], 900A4h
0x1c000846e  jnz     loc_1C00082F0
0x1c0008474  jmp     loc_1C0008379
0x1c0008479  btr     eax, 15h
0x1c000847d  mov     [rbx+4], eax
0x1c0008480  mov     rdx, rsi
0x1c0008483  mov     rcx, rbx
0x1c0008486  call    RefsPerformVerify
0x1c000848b  jmp     loc_1C00082FD
0x1c0008490  mov     rdx, rdi
0x1c0008493  mov     rcx, rbx; int
0x1c0008496  call    RefsCommonVolumeOpen
0x1c000849b  mov     [rsp+378h+var_344], eax
0x1c000849f  jmp     loc_1C0008701
0x1c00084a4  lea     rax, WPP_GLOBAL_Control; jumptable 00000001C00083B6 case 2
0x1c00084ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1c00084b2  cmp     rcx, rax
0x1c00084b5  jz      short loc_1C00084D9
0x1c00084b7  mov     eax, [rcx+2Ch]
0x1c00084ba  test    al, 1
0x1c00084bc  jz      short loc_1C00084D9
0x1c00084be  cmp     byte ptr [rcx+29h], 2
0x1c00084c2  jb      short loc_1C00084D9
0x1c00084c4  mov     edx, 0Ah
0x1c00084c9  lea     r8, WPP_62cfa6b095873b3bbf6f1190074bbaa9_Traceguids
0x1c00084d0  mov     rcx, [rcx+18h]
0x1c00084d4  call    WPP_SF_
0x1c00084d9  mov     [rsp+378h+BugCheckParameter4], r14; BugCheckParameter4
0x1c00084de  xor     r9d, r9d; BugCheckParameter3
0x1c00084e1  xor     r8d, r8d; BugCheckParameter2
0x1c00084e4  mov     edx, 130149h; BugCheckParameter1
0x1c00084e9  mov     ecx, 149h; BugCheckCode
0x1c00084ee  call    cs:__imp_KeBugCheckEx
0x1c00084fa  test    dword ptr [rbx+8], 1000h; jumptable 00000001C00083B6 case 3
0x1c0008501  jz      short loc_1C0008513
0x1c0008503  mov     rdx, rdi
0x1c0008506  mov     rcx, rbx
0x1c0008509  call    RefsCommonIoCompletionWorker
0x1c000850e  jmp     loc_1C0008701
0x1c0008513  xor     edx, edx; Val
0x1c0008515  mov     r8d, 130h; Size
0x1c000851b  lea     rcx, [rsp+378h+Irp+60h]; void *
0x1c0008523  call    memset
0x1c0008528  mov     r8d, [rdi+10h]
0x1c000852c  shr     r8d, 1
0x1c000852f  and     r8b, 1
0x1c0008533  lea     rdx, [rsp+378h+Irp+60h]
0x1c000853b  mov     rcx, rbx
0x1c000853e  call    RefsInitializeIoContext
0x1c0008543  mov     rdx, rdi
0x1c0008546  mov     rcx, rbx
0x1c0008549  call    RefsCommonRead
0x1c000854e  jmp     loc_1C0008701
0x1c0008553  mov     rdx, rdi; jumptable 00000001C00083B6 case 5
0x1c0008556  mov     rcx, rbx
0x1c0008559  call    RefsCommonQueryInformation
0x1c000855e  jmp     loc_1C0008701
0x1c0008563  xor     r8d, r8d; jumptable 00000001C00083B6 case 6
0x1c0008566  xor     edx, edx; Type
0x1c0008568  lea     rcx, [rsp+378h+Irp+40h]; Event
0x1c0008570  call    cs:__imp_KeInitializeEvent
0x1c0008577  nop     dword ptr [rax+rax+00h]
0x1c000857c  lea     rax, [rsp+378h+Irp+40h]
0x1c0008584  mov     [rbx+98h], rax
0x1c000858b  mov     rdx, rdi
0x1c000858e  mov     rcx, rbx; Context
0x1c0008591  call    RefsCommonSetInformation
0x1c0008596  mov     [rsp+378h+var_344], eax
0x1c000859a  cmp     eax, 367h
  ... truncated ...
```
