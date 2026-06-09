# RefsProcessException

- ea: `0x1c00588cc`
- end: `0x1c0059032`
- name: `RefsProcessException`
- size: `1894`
- prototype: ``
- caller_count: `24`
- callee_count: `23`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1c0001010`
- `0x1c0002e00`
- `0x1c0003e60`
- `0x1c0008060`
- `0x1c00098f0`
- `0x1c000d400`
- `0x1c003b850`
- `0x1c003c820`
- `0x1c0098760`
- `0x1c0099ba0`
- `0x1c00aacb0`
- `0x1c015b480`
- `0x1c015be10`
- `0x1c015d870`
- `0x1c015dbc0`
- `0x1c0162180`
- `0x1c0174590`
- `0x1c0174d50`
- `0x1c0175ab0`
- `0x1c0178500`
- `0x1c017b0b0`
- `0x1c017d550`
- `0x1c01912f0`
- `0x1c01a4fe0`

## callees

- `0x1c0008a14`
- `0x1c000f480`
- `0x1c000f770`
- `0x1c0013f90`
- `0x1c0014110`
- `0x1c003f35c`
- `0x1c00588cc`
- `0x1c0059038`
- `0x1c0059254`
- `0x1c00592b0`
- `0x1c0068168`
- `0x1c0092d08`
- `0x1c009dfa0`
- `0x1c009e030`
- `0x1c00a097c`
- `0x1c00a19bc`
- `0x1c00b3400`
- `0x1c00b37c0`
- `0x1c016556c`
- `0x1c017759c`
- `0x1c018fa30`
- `0x1c01c6744`
- `0x1c01cd240`

## import_xrefs

- `ntoskrnl!ExReleaseResourceLite` at `0x1c008a94b`
- `ntoskrnl!ExReleaseResourceLite` at `0x1c008a94b`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x1c0058ad6`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x1c0058d4b`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x1c0058ad6`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x1c0058d4b`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1c008a8ff`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1c008ac34`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1c008a8ff`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1c008ac34`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1c006c2ef`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1c008a934`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1c008ac6a`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1c006c2ef`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1c008a934`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1c008ac6a`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1c006c31b`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x1c006c31b`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1c0058dda`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1c008ab59`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1c008abcf`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1c008abe2`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1c008ad4f`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1c008ae73`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1c008ae88`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1c0058dda`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1c008ab59`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1c008abcf`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1c008abe2`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1c008ad4f`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1c008ae73`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1c008ae88`
- `ntoskrnl!FsRtlIsTotalDeviceFailure` at `0x1c008aa7d`
- `ntoskrnl!FsRtlIsTotalDeviceFailure` at `0x1c008aa7d`
- `ntoskrnl!CcMdlWriteAbort` at `0x1c00589f5`
- `ntoskrnl!CcMdlWriteAbort` at `0x1c008ad2a`
- `ntoskrnl!CcMdlWriteAbort` at `0x1c00589f5`
- `ntoskrnl!CcMdlWriteAbort` at `0x1c008ad2a`

## pseudocode

```c
__int64 __fastcall RefsProcessException(__int64 a1, struct _MDL *a2, unsigned int a3)
{
  __int64 v3; // rbx
  _DWORD *v4; // r13
  __int64 Context; // rax
  __int64 v6; // r12
  __int64 v7; // r14
  NTSTATUS v8; // edi
  __int64 v9; // rcx
  _QWORD *v10; // rdx
  __int64 v11; // r8
  _QWORD *v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // rdx
  __int64 *v16; // r12
  __int64 v17; // r8
  char v18; // al
  NTSTATUS v19; // eax
  struct _MDL *v21; // rcx
  char v22; // r13
  struct _MDL *v23; // rdx
  _QWORD *i; // rcx
  _QWORD *v25; // r15
  char v26; // al
  char v27; // r9
  __int64 v28; // r15
  PIRP TopLevelIrp; // rax
  __int64 v30; // rdi
  int v31; // eax
  struct _MDL *v32; // rdx
  PDEVICE_OBJECT v33; // rcx
  __int64 v34; // rcx
  __int64 v35; // rdx
  __int64 v36; // rcx
  __int64 v37; // rdx
  int v38; // eax
  __int64 v39; // r14
  NTSTATUS v40; // r14d
  char v41; // cl
  int v42; // eax
  char v43[4]; // [rsp+50h] [rbp-78h] BYREF
  int v44; // [rsp+54h] [rbp-74h]
  _QWORD v45[2]; // [rsp+58h] [rbp-70h] BYREF
  NTSTATUS v46; // [rsp+68h] [rbp-60h]
  _QWORD *v47; // [rsp+70h] [rbp-58h] BYREF
  _UNKNOWN *retaddr; // [rsp+C8h] [rbp+0h] BYREF
  __int64 v49; // [rsp+D0h] [rbp+8h]
  struct _MDL *v50; // [rsp+D8h] [rbp+10h]
  NTSTATUS Statusa; // [rsp+E0h] [rbp+18h]

  Context = (__int64)&retaddr;
  v50 = a2;
  v49 = a1;
  v3 = a1;
  v4 = 0;
  v45[0] = 0;
  LOBYTE(Context) = 0;
  v44 = Context;
  if ( a1 )
  {
    v6 = a1 + 64;
    v7 = *(_QWORD *)(a1 + 64);
    v45[1] = v7;
    if ( a3 == -1073741432 )
    {
      RefsSqmLogFileFull(*(_DWORD *)(a1 + 224), v7);
      if ( v7 )
      {
        Context = *(int *)(v3 + 224);
        if ( (unsigned int)Context <= 0xE )
        {
          _InterlockedIncrement64((volatile signed __int64 *)(v7 + 8 * Context + 5880));
          v3 = v49;
          v4 = (_DWORD *)v45[0];
        }
      }
    }
    v8 = *(_DWORD *)(v3 + 16);
    Statusa = v8;
    if ( *(_BYTE *)(v3 + 40) == 4 && (*(_BYTE *)(v3 + 41) & 6) == 2 )
    {
      if ( v50 )
      {
        a2 = *(struct _MDL **)&v50->Size;
        if ( a2 )
        {
          CcMdlWriteAbort(*(PFILE_OBJECT *)(*(_QWORD *)&v50[3].ByteCount + 48LL), a2);
          *(_QWORD *)&v50->Size = 0;
        }
      }
    }
    if ( v7 )
    {
      LOBYTE(a2) = 1;
      RefsRestoreScbSnapshots(v3, a2);
      RefsAbortPendingUsnReasons(v3);
      v9 = *(_QWORD *)(v3 + 24);
      if ( v9 )
      {
        if ( !*(_QWORD *)(v3 + 160) )
        {
          MsTriageGetContext(v9);
          v9 = *(_QWORD *)(v3 + 24);
        }
        if ( (*(_QWORD *)(v9 + 16) & 0x4000000000000LL) != 0 )
        {
          *(_DWORD *)(v3 + 4) |= 0x80000u;
          v9 = *(_QWORD *)(v3 + 24);
        }
        if ( (*(_QWORD *)(v9 + 16) & 0x8000000000000LL) != 0 )
          *(_DWORD *)(v3 + 4) |= 0x100000u;
        if ( *(_BYTE *)(v3 + 40) == 4
          && (*(_DWORD *)(*(_QWORD *)(v7 + 104) + 3116LL) & 0x800000) != 0
          && (*(_DWORD *)(v3 + 4) & 0x8000000) == 0 )
        {
          MsSetOkayToResyncSMRBands(*(_QWORD *)(v3 + 24));
        }
        RefsAbortTransaction(v3);
      }
      else
      {
        v10 = (_QWORD *)(v3 + 208);
        if ( (_QWORD *)*v10 != v10 )
        {
          v11 = 4;
          if ( v8 >= 0 )
            v11 = 1;
          RefsProcessRollbackListPriv(0, v10, v11);
        }
        if ( (*(_DWORD *)(v3 + 8) & 0x20000000) != 0 )
        {
          v12 = *(_QWORD **)v6;
          v12[111] = *(_QWORD *)(*(_QWORD *)v6 + 944LL);
          v12[116] = v12[119];
          v12[117] = v12[120];
          *(_DWORD *)(v3 + 8) &= ~0x20000000u;
        }
      }
      RefsRestoreScbSnapshots(v3, 0);
      Context = *(_QWORD *)(v7 + 264);
      if ( *(_QWORD *)(v7 + 240) != Context )
      {
        Context = *(_QWORD *)(v7 + 72);
        if ( Context )
        {
          if ( ExIsResourceAcquiredExclusiveLite((PERESOURCE)(*(_QWORD *)(*(_QWORD *)(Context + 120) + 96LL) + 64LL)) )
          {
            Context = *(_QWORD *)(v7 + 264);
            *(_QWORD *)(v7 + 240) = Context;
          }
        }
      }
    }
    else
    {
      if ( v8 == -1073741400 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        {
          LODWORD(Context) = HIDWORD(WPP_GLOBAL_Control->Timer);
          if ( (Context & 0x100) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            Context = WPP_SF_D(
                        WPP_GLOBAL_Control->AttachedDevice,
                        19,
                        WPP_131e0feb7650361cda1841a2e3a8b13d_Traceguids,
                        3221227528LL);
        }
        if ( RefsStatusDebugEnabled )
          Context = RefsStatusDebug(-1073739768);
        v8 = -1073739768;
        Statusa = -1073739768;
        v3 = v49;
        v4 = (_DWORD *)v45[0];
      }
      v13 = *(_QWORD *)(v3 + 24);
      if ( v13 && !*(_QWORD *)(v3 + 160) )
        Context = MsTriageGetContext(v13);
      v14 = *(_QWORD *)(v3 + 160);
      if ( v14 )
      {
        Context = RefsDeleteTriageContextInternal(v13, v14);
        *(_QWORD *)(v3 + 160) = 0;
      }
    }
    v15 = *(unsigned int *)(v3 + 12);
    if ( (v15 & 0x20) != 0 )
    {
      for ( i = *(_QWORD **)(v3 + 112); i != (_QWORD *)(v3 + 112); i = (_QWORD *)*i )
      {
        v25 = i - 9;
        v47 = i - 9;
        if ( (*((_DWORD *)i - 17) & 0x4000000) != 0 )
        {
          *(_DWORD *)(v3 + 12) = v15 & 0xFFFFFFDF;
          KeAcquireGuardedMutex((PKGUARDED_MUTEX)(v7 + 536));
          v26 = 1;
          v43[0] = 1;
          if ( !*((_DWORD *)v25 + 8) )
          {
            RefsDeleteFcb(v3, &v47, v43);
            v26 = v43[0];
          }
          if ( v26 )
            KeReleaseGuardedMutex((PKGUARDED_MUTEX)(v7 + 536));
          break;
        }
      }
      *(_DWORD *)(v3 + 12) &= ~0x20u;
      ExReleaseResourceLite((PERESOURCE)(v7 + 1424));
    }
    v16 = (__int64 *)(v3 + 104);
    v17 = *(_QWORD *)(v3 + 104);
    if ( v3 != v17 )
    {
      v27 = *(_BYTE *)(v3 + 40);
      if ( v27 != 3
        || !*(_QWORD *)(v3 + 232)
        && (v15 = *(_QWORD *)(*(_QWORD *)&v50[3].ByteCount + 48LL),
            Context = *(_QWORD *)(v3 + 64),
            *(_QWORD *)(v15 + 24) != *(_QWORD *)(Context + 40)) )
      {
        if ( *(int *)(v17 + 16) >= 0 || v8 == -1073741400 )
        {
          if ( v8 == -1073741740 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              WPP_SF_D(
                WPP_GLOBAL_Control->AttachedDevice,
                22,
                WPP_131e0feb7650361cda1841a2e3a8b13d_Traceguids,
                3221225688LL);
            }
            if ( RefsStatusDebugEnabled )
              RefsStatusDebug(-1073741608);
            Context = *v16;
            *(_DWORD *)(*v16 + 16) = -1073741608;
            v8 = Statusa;
            v3 = v49;
            v4 = (_DWORD *)v45[0];
          }
          else if ( v8 < 0 )
          {
            if ( (v28 = *(_QWORD *)&v50[3].ByteCount, v27 != 4)
              || v8 != -1073741670
              && v8 != -1073741663
              && v8 != -1073741801
              && (*(_DWORD *)(v28 + 8) <= 0x1000u || FsRtlIsTotalDeviceFailure(v8))
              || (LODWORD(Context) = (_DWORD)v50, ((__int64)v50->Process & 2) == 0)
              || *(_DWORD *)(v28 + 8) <= 0x1000u )
            {
              Context = *v16;
              *(_DWORD *)(*v16 + 16) = v8;
            }
          }
        }
      }
    }
    if ( v8 != -1073741608 && v8 != -1073741432 && v8 != -1073741400 )
    {
LABEL_55:
      if ( v4 )
      {
        v4[4] = 0;
        v19 = RefsPostRequest(v4);
        v46 = v19;
        if ( v4 == (_DWORD *)v3 )
        {
          v50 = 0;
          v3 = 0;
          v49 = 0;
          v8 = v19;
          Statusa = v19;
        }
        if ( v3 )
        {
LABEL_63:
          v21 = v50;
          if ( (*(_BYTE *)(v3 + 8) & 0x42) == 2 )
            v21 = 0;
          v50 = v21;
LABEL_66:
          v22 = v44;
          if ( v50 )
          {
            if ( !(_BYTE)v44 && *(_BYTE *)(v3 + 40) == 4 && (*(_BYTE *)(v3 + 41) & 6) == 6 )
            {
              v32 = *(struct _MDL **)&v50->Size;
              if ( v32 )
              {
                CcMdlWriteAbort(*(PFILE_OBJECT *)(*(_QWORD *)&v50[3].ByteCount + 48LL), v32);
                *(_QWORD *)&v50->Size = 0;
              }
            }
          }
          if ( !v3 || !*(_QWORD *)(v3 + 160) )
            goto LABEL_69;
          if ( *(_BYTE *)(v3 + 40) != 2 || v3 == *(_QWORD *)(v3 + 104) && LOBYTE(IoGetTopLevelIrp()->Type) )
          {
            v34 = *(_QWORD *)(v3 + 104);
            if ( v3 == v34 )
            {
              if ( !LOBYTE(IoGetTopLevelIrp()->Type) )
              {
                if ( IoGetTopLevelIrp()->AssociatedIrp.MasterIrp == (struct _IRP *)7
                  || (*(_DWORD *)(v3 + 8) & 0x400000) != 0
                  || (LOBYTE(v35) = 1, RefsInitializeIrpContext(0, v35, 0, v45), (v37 = v45[0]) == 0) )
                {
                  RefsDeleteTriageContextInternal(v36, *(_QWORD *)(v3 + 160));
                  *(_QWORD *)(v3 + 160) = 0;
                }
                else
                {
                  *(_QWORD *)(v45[0] + 64LL) = *(_QWORD *)(v3 + 64);
                  *(_QWORD *)(v37 + 160) = *(_QWORD *)(v3 + 160);
                  *(_QWORD *)(v3 + 160) = 0;
                  _InterlockedAdd((volatile signed __int32 *)(*(_QWORD *)(v3 + 64) + 468LL), 1u);
                  RefsPostSpecial(
                    v45[0],
                    *(_QWORD *)(v37 + 64),
                    (unsigned int)RefsPerformTriageWorkItem,
                    *(_QWORD *)(v37 + 160),
                    1,
                    0);
                }
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                {
                  WPP_SF_D(
                    WPP_GLOBAL_Control->AttachedDevice,
                    28,
                    WPP_131e0feb7650361cda1841a2e3a8b13d_Traceguids,
                    3221227528LL);
                }
                if ( RefsStatusDebugEnabled )
                  RefsStatusDebug(-1073739768);
                v8 = -1073739768;
                Statusa = -1073739768;
                v3 = v49;
                goto LABEL_185;
              }
              v39 = *(_QWORD *)(v3 + 160);
              *(_QWORD *)(v3 + 160) = 0;
              if ( (*(_DWORD *)(v3 + 8) & 0x10000) == 0 )
                *(_DWORD *)(v3 + 4) |= 0x400u;
              RefsCleanupIrpContext(v3, 1);
              v40 = RefsPerformTriage(v3, v39);
              if ( v40 >= 0 )
                goto LABEL_69;
              v41 = *(_BYTE *)(v3 + 40);
              if ( v41 == 2 )
              {
                v42 = *(_DWORD *)(v3 + 8);
                if ( (v42 & 4) == 0 )
                {
                  *(_DWORD *)(v3 + 8) = v42 | 4;
                  goto LABEL_69;
                }
              }
              if ( v41 == 18 && v40 == -1073741202 )
              {
LABEL_69:
                if ( v22 )
                {
                  *(_DWORD *)(v3 + 4) |= 0x400u;
                  *(_DWORD *)(v3 + 16) = 0;
                  if ( v50 && (dword_1C012E0B0 & 0x400) != 0 )
                    RefsRemoveDebugInfoIrpImplementation(v50, 0);
                  v8 = Statusa;
                  if ( RefsStatusDebugEnabled )
                    RefsStatusDebug(Statusa);
                  v23 = 0;
LABEL_74:
                  RefsExtendedCompleteRequestInternal(v49, v23, (unsigned int)v8);
                  return (unsigned int)v8;
                }
LABEL_185:
                if ( v3 )
                {
                  if ( v50 )
                  {
                    v38 = *(_DWORD *)(v3 + 12);
                    if ( (v38 & 1) != 0 )
                    {
                      *(_DWORD *)(v3 + 12) = v38 | 2;
                      return (unsigned int)v8;
                    }
                  }
                }
                v8 = Statusa;
                if ( RefsStatusDebugEnabled )
                  RefsStatusDebug(Statusa);
                v23 = v50;
                goto LABEL_74;
              }
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
              {
                WPP_SF_D(
                  WPP_GLOBAL_Control->AttachedDevice,
                  29,
                  WPP_131e0feb7650361cda1841a2e3a8b13d_Traceguids,
                  (unsigned int)v40);
              }
              if ( RefsStatusDebugEnabled )
                RefsStatusDebug(v40);
              v8 = v40;
              Statusa = v40;
              if ( v40 != -1073741608 && v40 != -1073741432 )
                v22 = 0;
            }
            else
            {
              *(_QWORD *)(v34 + 160) = *(_QWORD *)(v3 + 160);
              *(_QWORD *)(v3 + 160) = 0;
              *(_DWORD *)(*(_QWORD *)(v3 + 104) + 16LL) = -1073741400;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
              {
                WPP_SF_D(
                  WPP_GLOBAL_Control->AttachedDevice,
                  27,
                  WPP_131e0feb7650361cda1841a2e3a8b13d_Traceguids,
                  3221227528LL);
              }
              if ( RefsStatusDebugEnabled )
                RefsStatusDebug(-1073739768);
              v8 = -1073739768;
              Statusa = -1073739768;
            }
          }
          else
          {
            v22 = 1;
            v33 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
            {
              WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_131e0feb7650361cda1841a2e3a8b13d_Traceguids, 259);
            }
            if ( RefsStatusDebugEnabled )
              RefsStatusDebug(259);
            v8 = 259;
            Statusa = 259;
            RefsDeleteTriageContextInternal(v33, *(_QWORD *)(v3 + 160));
            *(_QWORD *)(v3 + 160) = 0;
          }
          v3 = v49;
          goto LABEL_69;
        }
        if ( !v50 )
          return (unsigned int)v8;
      }
      if ( !v3 )
        goto LABEL_66;
      goto LABEL_63;
    }
    v18 = *(_BYTE *)(v3 + 40);
    if ( v18 == 2 )
    {
      LOBYTE(Context) = 1;
      v44 = Context;
      if ( (*(_DWORD *)(v3 + 4) & 0x800) == 0 )
        goto LABEL_55;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_131e0feb7650361cda1841a2e3a8b13d_Traceguids, 259);
      }
      if ( RefsStatusDebugEnabled )
        RefsStatusDebug(259);
      v8 = 259;
    }
    else
    {
      if ( v18 == 3 )
      {
        if ( v3 != *v16
          || (Context = (__int64)IoGetTopLevelIrp(), !*(_BYTE *)Context)
          || (LODWORD(Context) = (_DWORD)v50, ((__int64)v50->Process & 2) != 0) )
        {
          if ( v8 == -1073741400 && v3 != *v16 )
            goto LABEL_55;
LABEL_61:
          LOBYTE(Context) = 1;
          v44 = Context;
          goto LABEL_55;
        }
      }
      if ( v3 == *v16 && LOBYTE(IoGetTopLevelIrp()->Type) )
      {
        LODWORD(Context) = *(_DWORD *)(v3 + 4);
        if ( (Context & 0x800) != 0 && !*(_QWORD *)(v3 + 160) )
        {
          v4 = (_DWORD *)v3;
          v45[0] = v3;
          goto LABEL_55;
        }
        goto LABEL_61;
      }
      if ( v8 == -1073741432 )
      {
        ++*(_DWORD *)(v7 + 2600);
        if ( *v16 == v3 && (*(_DWORD *)(v7 + 472) & 1) == 0 )
        {
          if ( *(_BYTE *)(v3 + 40) == 4 && IoGetTopLevelIrp()->AssociatedIrp.MasterIrp == (struct _IRP *)2 )
          {
            TopLevelIrp = IoGetTopLevelIrp();
            TopLevelIrp->AssociatedIrp.MasterIrp = (struct _IRP *)((unsigned __int64)TopLevelIrp->AssociatedIrp.MasterIrp
                                                                 | 0x80000000);
          }
          else
          {
            v45[0] = 0;
            LOBYTE(v15) = 1;
            RefsInitializeIrpContext(0, v15, 0, v45);
            v30 = v45[0];
            if ( v45[0] )
            {
              *(_QWORD *)(v45[0] + 64LL) = v7;
              *(_DWORD *)(v30 + 224) = *(_DWORD *)(v3 + 224);
              KeAcquireGuardedMutex((PKGUARDED_MUTEX)(v7 + 480));
              v31 = *(_DWORD *)(v7 + 472);
              if ( (v31 & 1) != 0 )
              {
                RefsCleanupIrpContext(v30, 0);
                v45[0] = 0;
              }
              else
              {
                *(_DWORD *)(v7 + 472) = v31 | 1;
              }
              KeReleaseGuardedMutex((PKGUARDED_MUTEX)(v7 + 480));
            }
          }
        }
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 24, WPP_131e0feb7650361cda1841a2e3a8b13d_Traceguids, 3221225556LL);
      }
      if ( RefsStatusDebugEnabled )
        RefsStatusDebug(-1073741740);
      v8 = -1073741740;
    }
    Statusa = v8;
    v4 = (_DWORD *)v45[0];
    v3 = v49;
    goto LABEL_55;
  }
  if ( RefsStatusDebugEnabled )
    RefsStatusDebug(a3);
  RefsExtendedCompleteRequestInternal(0, v50, a3);
  return a3;
}

```

## disassembly

```asm
0x1c00588cc  mov     rax, rsp
0x1c00588cf  mov     [rax+18h], r8d
0x1c00588d3  mov     [rax+10h], rdx
0x1c00588d7  mov     [rax+8], rcx
0x1c00588db  push    rbx
0x1c00588dc  push    rsi
0x1c00588dd  push    rdi
0x1c00588de  push    r12
0x1c00588e0  push    r13
0x1c00588e2  push    r14
0x1c00588e4  push    r15
0x1c00588e6  sub     rsp, 90h
0x1c00588ed  mov     rbx, rcx
0x1c00588f0  xor     esi, esi
0x1c00588f2  mov     r13d, esi
0x1c00588f5  mov     [rax-70h], rsi
0x1c00588f9  mov     al, sil
0x1c00588fc  mov     [rsp+0C8h+var_74], eax
0x1c0058900  mov     [rsp+0C8h+arg_18], al
0x1c0058907  test    rcx, rcx
0x1c005890a  jz      loc_1C008A848
0x1c0058910  lea     r12, [rcx+40h]
0x1c0058914  mov     r14, [r12]
0x1c0058918  mov     [rsp+0C8h+var_68], r14
0x1c005891d  cmp     r8d, 0C0000188h
0x1c0058924  jz      loc_1C008A88E
0x1c005892a  mov     edi, [rbx+10h]
0x1c005892d  mov     [rsp+0C8h+Status], edi
0x1c0058934  cmp     byte ptr [rbx+28h], 4
0x1c0058938  jz      loc_1C00589BF
0x1c005893e  test    r14, r14
0x1c0058941  jz      loc_1C0058AFD
0x1c0058947  mov     r15d, 1
0x1c005894d  mov     dl, r15b
0x1c0058950  mov     rcx, rbx
0x1c0058953  call    RefsRestoreScbSnapshots
0x1c0058958  mov     rcx, rbx
0x1c005895b  call    RefsAbortPendingUsnReasons
0x1c0058960  mov     rcx, [rbx+18h]
0x1c0058964  test    rcx, rcx
0x1c0058967  jnz     loc_1C0058A0A
0x1c005896d  lea     rdx, [rbx+0D0h]
0x1c0058974  cmp     [rdx], rdx
0x1c0058977  jz      short loc_1C0058988
0x1c0058979  lea     r8d, [r15+3]
0x1c005897d  test    edi, edi
0x1c005897f  cmovns  r8d, r15d
0x1c0058983  call    RefsProcessRollbackListPriv
0x1c0058988  test    dword ptr [rbx+8], 20000000h
0x1c005898f  jnz     loc_1C0058A85
0x1c0058995  xor     edx, edx
0x1c0058997  mov     rcx, rbx
0x1c005899a  call    RefsRestoreScbSnapshots
0x1c005899f  mov     rax, [r14+108h]
0x1c00589a6  cmp     [r14+0F0h], rax
0x1c00589ad  jnz     loc_1C0058ABD
0x1c00589b3  lea     r15, WPP_GLOBAL_Control
0x1c00589ba  jmp     loc_1C0058BB7
0x1c00589bf  mov     al, [rbx+29h]
0x1c00589c2  and     al, 6
0x1c00589c4  cmp     al, 2
0x1c00589c6  jnz     loc_1C005893E
0x1c00589cc  mov     r15, [rsp+0C8h+arg_8]
0x1c00589d4  test    r15, r15
0x1c00589d7  jz      loc_1C005893E
0x1c00589dd  mov     rdx, [r15+8]; MdlChain
0x1c00589e1  test    rdx, rdx
0x1c00589e4  jz      loc_1C005893E
0x1c00589ea  mov     rcx, [r15+0B8h]
0x1c00589f1  mov     rcx, [rcx+30h]; FileObject
0x1c00589f5  call    cs:__imp_CcMdlWriteAbort
0x1c00589fc  nop     dword ptr [rax+rax+00h]
0x1c0058a01  mov     [r15+8], rsi
0x1c0058a05  jmp     loc_1C005893E
0x1c0058a0a  lea     rdx, [rbx+0A0h]
0x1c0058a11  cmp     [rdx], rsi
0x1c0058a14  jnz     short loc_1C0058A1F
0x1c0058a16  call    MsTriageGetContext
0x1c0058a1b  mov     rcx, [rbx+18h]
0x1c0058a1f  mov     rdx, 4000000000000h
0x1c0058a29  test    [rcx+10h], rdx
0x1c0058a2d  jz      short loc_1C0058A38
0x1c0058a2f  bts     dword ptr [rbx+4], 13h
0x1c0058a34  mov     rcx, [rbx+18h]
0x1c0058a38  mov     rax, [rcx+10h]
0x1c0058a3c  mov     rcx, 8000000000000h
0x1c0058a46  test    rcx, rax
0x1c0058a49  jz      short loc_1C0058A50
0x1c0058a4b  bts     dword ptr [rbx+4], 14h
0x1c0058a50  cmp     byte ptr [rbx+28h], 4
0x1c0058a54  jnz     short loc_1C0058A78
0x1c0058a56  mov     rax, [r14+68h]
0x1c0058a5a  test    dword ptr [rax+0C2Ch], 800000h
0x1c0058a64  jz      short loc_1C0058A78
0x1c0058a66  test    dword ptr [rbx+4], 8000000h
0x1c0058a6d  jnz     short loc_1C0058A78
0x1c0058a6f  mov     rcx, [rbx+18h]
0x1c0058a73  call    MsSetOkayToResyncSMRBands
0x1c0058a78  mov     rcx, rbx
0x1c0058a7b  call    RefsAbortTransaction
0x1c0058a80  jmp     loc_1C0058995
0x1c0058a85  mov     rcx, [r12]
0x1c0058a89  mov     rax, [rcx+3B0h]
0x1c0058a90  mov     [rcx+378h], rax
0x1c0058a97  mov     rax, [rcx+3B8h]
0x1c0058a9e  mov     [rcx+3A0h], rax
0x1c0058aa5  mov     rax, [rcx+3C0h]
0x1c0058aac  mov     [rcx+3A8h], rax
0x1c0058ab3  btr     dword ptr [rbx+8], 1Dh
0x1c0058ab8  jmp     loc_1C0058995
0x1c0058abd  mov     rax, [r14+48h]
0x1c0058ac1  test    rax, rax
0x1c0058ac4  jz      loc_1C00589B3
0x1c0058aca  mov     rax, [rax+78h]
0x1c0058ace  mov     rcx, [rax+60h]
0x1c0058ad2  add     rcx, 40h ; '@'; Resource
0x1c0058ad6  call    cs:__imp_ExIsResourceAcquiredExclusiveLite
0x1c0058add  nop     dword ptr [rax+rax+00h]
0x1c0058ae2  test    al, al
0x1c0058ae4  jz      loc_1C00589B3
0x1c0058aea  mov     rax, [r14+108h]
0x1c0058af1  mov     [r14+0F0h], rax
0x1c0058af8  jmp     loc_1C00589B3
0x1c0058afd  cmp     edi, 0C00001A8h
0x1c0058b03  jnz     short loc_1C0058B7E
0x1c0058b05  lea     r15, WPP_GLOBAL_Control
0x1c0058b0c  mov     rcx, cs:WPP_GLOBAL_Control
0x1c0058b13  cmp     rcx, r15
0x1c0058b16  jz      short loc_1C0058B42
0x1c0058b18  mov     eax, [rcx+2Ch]
0x1c0058b1b  bt      eax, 8
0x1c0058b1f  jnb     short loc_1C0058B42
0x1c0058b21  cmp     byte ptr [rcx+29h], 4
0x1c0058b25  jb      short loc_1C0058B42
0x1c0058b27  mov     edx, 13h
0x1c0058b2c  mov     r9d, 0C0000808h
0x1c0058b32  lea     r8, WPP_131e0feb7650361cda1841a2e3a8b13d_Traceguids
0x1c0058b39  mov     rcx, [rcx+18h]
0x1c0058b3d  call    WPP_SF_D
0x1c0058b42  mov     al, cs:RefsStatusDebugEnabled
0x1c0058b48  test    al, al
0x1c0058b4a  jz      short loc_1C0058B63
0x1c0058b4c  mov     r8d, 633h
0x1c0058b52  lea     rdx, aNtfsdataC; "NtfsData.c"
0x1c0058b59  mov     ecx, 0C0000808h; Status
0x1c0058b5e  call    RefsStatusDebug
0x1c0058b63  mov     edi, 0C0000808h
0x1c0058b68  mov     [rsp+0C8h+Status], edi
0x1c0058b6f  mov     rbx, [rsp+0C8h+arg_0]
0x1c0058b77  mov     r13, [rsp+0C8h+var_70]
0x1c0058b7c  jmp     short loc_1C0058B85
0x1c0058b7e  lea     r15, WPP_GLOBAL_Control
0x1c0058b85  mov     rcx, [rbx+18h]
0x1c0058b89  test    rcx, rcx
0x1c0058b8c  jz      short loc_1C0058B9F
0x1c0058b8e  lea     rdx, [rbx+0A0h]
0x1c0058b95  cmp     [rdx], rsi
0x1c0058b98  jnz     short loc_1C0058B9F
0x1c0058b9a  call    MsTriageGetContext
0x1c0058b9f  mov     rdx, [rbx+0A0h]
0x1c0058ba6  test    rdx, rdx
0x1c0058ba9  jz      short loc_1C0058BB7
0x1c0058bab  call    RefsDeleteTriageContextInternal
0x1c0058bb0  mov     [rbx+0A0h], rsi
0x1c0058bb7  jmp     loc_1C0058D8E
0x1c0058bbc  inc     cs:RefsFailedAborts
0x1c0058bc2  lea     rdx, WPP_GLOBAL_Control
0x1c0058bc9  mov     rcx, cs:WPP_GLOBAL_Control
0x1c0058bd0  cmp     rcx, rdx
0x1c0058bd3  jz      short loc_1C0058C13
0x1c0058bd5  mov     edx, [rcx+2Ch]
0x1c0058bd8  test    dl, 4
0x1c0058bdb  jz      short loc_1C0058C13
0x1c0058bdd  cmp     byte ptr [rcx+29h], 2
0x1c0058be1  jb      short loc_1C0058C13
0x1c0058be3  mov     dword ptr [rsp+0C8h+var_90], eax
0x1c0058be7  mov     rbx, [rsp+0C8h+arg_0]
0x1c0058bef  mov     rax, [rbx+40h]
0x1c0058bf3  mov     [rsp+0C8h+var_A0], rax
0x1c0058bf8  mov     rax, [rsp+0C8h+arg_8]
0x1c0058c00  mov     [rsp+0C8h+var_A8], rax
0x1c0058c05  mov     r9, rbx
0x1c0058c08  mov     rcx, [rcx+18h]
0x1c0058c0c  call    WPP_SF_qqqDd
0x1c0058c11  jmp     short loc_1C0058C1B
0x1c0058c13  mov     rbx, [rsp+0C8h+arg_0]
0x1c0058c1b  lea     r14, [rbx+0D0h]
0x1c0058c22  xor     r8d, r8d
0x1c0058c25  mov     rcx, r14
0x1c0058c28  call    RefsFindRollbackStructByType
0x1c0058c2d  mov     rsi, rax
0x1c0058c30  test    rax, rax
0x1c0058c33  jz      loc_1C0058D1C
0x1c0058c39  mov     rdi, [rax+38h]
0x1c0058c3d  test    rdi, rdi
0x1c0058c40  jz      loc_1C0058D14
0x1c0058c46  lea     rax, WPP_GLOBAL_Control
0x1c0058c4d  mov     rcx, cs:WPP_GLOBAL_Control
0x1c0058c54  cmp     rcx, rax
0x1c0058c57  jz      short loc_1C0058CA3
0x1c0058c59  mov     eax, [rcx+2Ch]
0x1c0058c5c  test    al, 4
0x1c0058c5e  jz      short loc_1C0058CA3
0x1c0058c60  cmp     byte ptr [rcx+29h], 2
0x1c0058c64  jb      short loc_1C0058CA3
0x1c0058c66  mov     rdx, [rdi+78h]
0x1c0058c6a  mov     rax, [rdx+8]
0x1c0058c6e  mov     [rsp+0C8h+var_88], rax
0x1c0058c73  mov     rax, [rdx+10h]
0x1c0058c77  mov     [rsp+0C8h+var_90], rax
0x1c0058c7c  mov     [rsp+0C8h+var_98], rdi
0x1c0058c81  mov     rax, [rbx+40h]
0x1c0058c85  mov     [rsp+0C8h+var_A0], rax
0x1c0058c8a  mov     rax, [rsp+0C8h+arg_8]
0x1c0058c92  mov     [rsp+0C8h+var_A8], rax
0x1c0058c97  mov     r9, rbx
0x1c0058c9a  mov     rcx, [rcx+18h]
0x1c0058c9e  call    WPP_SF_qqqqii
0x1c0058ca3  mov     rax, [rdi+78h]
0x1c0058ca7  test    dword ptr [rax+4], 104h
0x1c0058cae  jnz     short loc_1C0058CEC
0x1c0058cb0  lock and dword ptr [rdi+88h], 0FFFFFDDFh
0x1c0058cbb  and     qword ptr [rdi+18h], 0
0x1c0058cc0  and     qword ptr [rdi+20h], 0
0x1c0058cc5  and     qword ptr [rdi+28h], 0
0x1c0058cca  cmp     qword ptr [rdi+0E0h], 0
0x1c0058cd2  jz      short loc_1C0058CE2
0x1c0058cd4  mov     r8d, 1
0x1c0058cda  mov     rdx, rdi
0x1c0058cdd  call    RefsDeleteInternalAttributeStream
0x1c0058ce2  mov     rbx, [rsp+0C8h+arg_0]
0x1c0058cea  jmp     short loc_1C0058D10
0x1c0058cec  mov     rax, [rsi+18h]
0x1c0058cf0  cmp     rax, [rdi+18h]
0x1c0058cf4  jge     short loc_1C0058CFA
0x1c0058cf6  mov     [rdi+18h], rax
0x1c0058cfa  mov     rax, [rsi+20h]
0x1c0058cfe  cmp     rax, [rdi+20h]
0x1c0058d02  jge     short loc_1C0058D10
0x1c0058d04  mov     [rdi+20h], rax
0x1c0058d08  mov     rax, [rsi+20h]
0x1c0058d0c  mov     [rdi+28h], rax
0x1c0058d10  mov     byte ptr [rdi+5], 0
0x1c0058d14  mov     r8, rsi
0x1c0058d17  jmp     loc_1C0058C25
0x1c0058d1c  mov     r14, [rsp+0C8h+var_68]
0x1c0058d21  test    r14, r14
0x1c0058d24  jz      short loc_1C0058D69
0x1c0058d26  mov     rax, [r14+108h]
0x1c0058d2d  cmp     [r14+0F0h], rax
0x1c0058d34  jz      short loc_1C0058D69
0x1c0058d36  mov     rax, [r14+48h]
0x1c0058d3a  test    rax, rax
0x1c0058d3d  jz      short loc_1C0058D69
0x1c0058d3f  mov     rax, [rax+78h]
0x1c0058d43  mov     rcx, [rax+60h]
0x1c0058d47  add     rcx, 40h ; '@'; Resource
0x1c0058d4b  call    cs:__imp_ExIsResourceAcquiredExclusiveLite
0x1c0058d52  nop     dword ptr [rax+rax+00h]
0x1c0058d57  test    al, al
0x1c0058d59  jz      short loc_1C0058D69
0x1c0058d5b  mov     rax, [r14+108h]
0x1c0058d62  mov     [r14+0F0h], rax
0x1c0058d69  and     qword ptr [rbx+18h], 0
0x1c0058d6e  xor     esi, esi
0x1c0058d70  lea     r15, WPP_GLOBAL_Control
0x1c0058d77  mov     edi, [rsp+0C8h+Status]
0x1c0058d7e  mov     r13, [rsp+0C8h+var_70]
0x1c0058d83  mov     al, [rsp+0C8h+arg_18]
0x1c0058d8a  mov     [rsp+0C8h+var_74], eax
0x1c0058d8e  mov     edx, [rbx+0Ch]
0x1c0058d91  test    dl, 20h
0x1c0058d94  jnz     loc_1C008A8D0
0x1c0058d9a  lea     r12, [rbx+68h]
0x1c0058d9e  mov     r8, [r12]
0x1c0058da2  cmp     rbx, r8
0x1c0058da5  jnz     loc_1C008A96B
0x1c0058dab  mov     r15d, 0C0000188h
0x1c0058db1  cmp     edi, 0C00000D8h
0x1c0058db7  jnz     loc_1C008AAB7
0x1c0058dbd  mov     al, [rbx+28h]
0x1c0058dc0  cmp     al, 2
0x1c0058dc2  jz      loc_1C008AAD1
0x1c0058dc8  cmp     al, 3
0x1c0058dca  jz      loc_1C008AB53
0x1c0058dd0  cmp     rbx, [r12]
0x1c0058dd4  jnz     loc_1C008AB99
0x1c0058dda  call    cs:__imp_IoGetTopLevelIrp
0x1c0058de1  nop     dword ptr [rax+rax+00h]
0x1c0058de6  cmp     [rax], sil
0x1c0058de9  jz      loc_1C008AB99
0x1c0058def  mov     eax, [rbx+4]
0x1c0058df2  bt      eax, 0Bh
0x1c0058df6  jnb     loc_1C0058F6C
0x1c0058dfc  cmp     [rbx+0A0h], rsi
0x1c0058e03  jnz     loc_1C0058F6C
0x1c0058e09  mov     r13, rbx
0x1c0058e0c  mov     [rsp+0C8h+var_70], rbx
0x1c0058e11  lea     r12, WPP_GLOBAL_Control
0x1c0058e18  mov     r14d, 1
  ... truncated ...
```
