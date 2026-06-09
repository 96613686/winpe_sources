# RefsOpenAttribute

- ea: `0x1c0152814`
- end: `0x1c0153315`
- name: `RefsOpenAttribute`
- size: `2817`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, POPLOCK_FS_PREPOST_IRP PostIrpRoutine, __int64, int, int, int, int, int, __int64, __int64, __int64)`
- caller_count: `5`
- callee_count: `17`
- tags: `file_ops, installer_update`

## callers

- `0x1c01540e0`
- `0x1c0166c84`
- `0x1c016752c`
- `0x1c0179bd4`
- `0x1c0194f50`

## callees

- `0x1c0002bac`
- `0x1c0002c44`
- `0x1c0003fb0`
- `0x1c0004330`
- `0x1c000f770`
- `0x1c0061878`
- `0x1c0063db0`
- `0x1c0068168`
- `0x1c00689d4`
- `0x1c00b13b0`
- `0x1c0151130`
- `0x1c0152814`
- `0x1c015331c`
- `0x1c0153394`
- `0x1c0156b80`
- `0x1c01632d4`
- `0x1c017bb64`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c0152e28`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1c0152e28`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c0152e7e`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c0152ec1`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c0152e7e`
- `ntoskrnl!ExReleasePushLockEx` at `0x1c0152ec1`
- `ntoskrnl!ExAcquireFastMutex` at `0x1c0152f4e`
- `ntoskrnl!ExAcquireFastMutex` at `0x1c0152f4e`
- `ntoskrnl!ExReleaseFastMutex` at `0x1c0152fa6`
- `ntoskrnl!ExReleaseFastMutex` at `0x1c0152fa6`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x1c0153205`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x1c0153205`
- `ntoskrnl!MmCanFileBeTruncated` at `0x1c01530a8`
- `ntoskrnl!MmCanFileBeTruncated` at `0x1c01530a8`
- `ntoskrnl!IoRemoveShareAccess` at `0x1c017df90`
- `ntoskrnl!IoRemoveShareAccess` at `0x1c017df90`
- `ntoskrnl!MmDoesFileHaveUserWritableReferences` at `0x1c0152abe`
- `ntoskrnl!MmDoesFileHaveUserWritableReferences` at `0x1c0152c48`
- `ntoskrnl!MmDoesFileHaveUserWritableReferences` at `0x1c0152abe`
- `ntoskrnl!MmDoesFileHaveUserWritableReferences` at `0x1c0152c48`
- `ntoskrnl!IoUpdateShareAccess` at `0x1c0152d9e`
- `ntoskrnl!IoUpdateShareAccess` at `0x1c0152d9e`
- `ntoskrnl!IoSetShareAccessEx` at `0x1c0152d85`
- `ntoskrnl!IoSetShareAccessEx` at `0x1c0152d85`
- `ntoskrnl!IoCheckShareAccessEx` at `0x1c0152c06`
- `ntoskrnl!IoCheckShareAccessEx` at `0x1c0152c06`
- `ntoskrnl!FsRtlOplockFsctrl` at `0x1c0153232`
- `ntoskrnl!FsRtlOplockFsctrl` at `0x1c015325b`
- `ntoskrnl!FsRtlOplockFsctrl` at `0x1c0153232`
- `ntoskrnl!FsRtlOplockFsctrl` at `0x1c015325b`

## string_xrefs

- `0x1c01528f9`: `Create.c`
- `0x1c01532f5`: `Create.c`

## pseudocode

```c
__int64 __fastcall RefsOpenAttribute(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        POPLOCK_FS_PREPOST_IRP PostIrpRoutine,
        __int64 a7,
        int a8,
        int a9,
        unsigned int a10,
        int a11,
        int a12,
        __int64 a13,
        __int64 *a14,
        _QWORD *a15)
{
  int v17; // ebx
  char v18; // r12
  ACCESS_MASK v19; // r8d
  __int64 Scb; // rdx
  unsigned __int16 v21; // cx
  int v22; // r8d
  __int64 v23; // rcx
  __int64 v24; // r12
  __int64 v25; // rdx
  _QWORD *v26; // rax
  _QWORD *v27; // rdx
  __int64 v28; // r8
  __int64 v29; // rdx
  __int64 v30; // rdx
  int v31; // eax
  __int64 v32; // rax
  int IsEnabledDeviceUsage; // eax
  __int64 v34; // rdx
  int v35; // r8d
  int v36; // eax
  char v38; // [rsp+30h] [rbp-48h] BYREF
  char v39; // [rsp+31h] [rbp-47h]
  char v40; // [rsp+32h] [rbp-46h]
  char IsMinstoreTransactionActive; // [rsp+33h] [rbp-45h]
  int v42; // [rsp+34h] [rbp-44h]
  ACCESS_MASK DesiredAccess; // [rsp+38h] [rbp-40h]

  v17 = 0;
  v39 = 0;
  v38 = 0;
  v18 = 0;
  v19 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a2 + 8) + 8LL) + 20LL);
  DesiredAccess = v19;
  Scb = *a14;
  if ( !*a14 )
  {
    Scb = RefsCreateScb(a1, a5, a8, a7, 0, 0);
    *a14 = Scb;
    v19 = DesiredAccess;
  }
  if ( (*(_DWORD *)(Scb + 136) & 2) != 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
    {
      v17 = -1073741738;
    }
    else
    {
      v17 = -1073741738;
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 164, WPP_cd49aa686cfe3d14e1a2820d5064b336_Traceguids, 3221225558LL);
    }
    if ( !RefsStatusDebugEnabled )
      goto LABEL_11;
    goto LABEL_10;
  }
  if ( *(_DWORD *)(Scb + 320) && (*(_DWORD *)(*(_QWORD *)(a2 + 8) + 16LL) & 6) != 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
    {
      v17 = -1073741790;
    }
    else
    {
      v17 = -1073741790;
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 165, WPP_cd49aa686cfe3d14e1a2820d5064b336_Traceguids, 3221225506LL);
    }
    if ( !RefsStatusDebugEnabled )
      goto LABEL_11;
    goto LABEL_10;
  }
  if ( !a13 )
  {
    if ( (*(_DWORD *)(a2 + 16) & 0x100000) != 0 )
    {
      if ( *(_WORD *)Scb != 2053 )
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
        {
          v17 = -1073741811;
        }
        else
        {
          v17 = -1073741811;
          WPP_SF_D(
            WPP_GLOBAL_Control->AttachedDevice,
            166,
            WPP_cd49aa686cfe3d14e1a2820d5064b336_Traceguids,
            3221225485LL);
        }
        if ( !RefsStatusDebugEnabled )
          goto LABEL_11;
        goto LABEL_10;
      }
      if ( *(_DWORD *)(Scb + 144)
        || (*(_DWORD *)(*(_QWORD *)(a2 + 8) + 16LL) & 0xFFFFFF7F) != 0
        || (*(_BYTE *)(a2 + 26) & 7) != 7 )
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
        {
          v17 = -1073741598;
        }
        else
        {
          v17 = -1073741598;
          WPP_SF_D(
            WPP_GLOBAL_Control->AttachedDevice,
            167,
            WPP_cd49aa686cfe3d14e1a2820d5064b336_Traceguids,
            3221225698LL);
        }
        if ( !RefsStatusDebugEnabled )
          goto LABEL_11;
        goto LABEL_10;
      }
    }
    if ( a9 == 1 )
    {
      IoUpdateShareAccess(*(PFILE_OBJECT *)(a2 + 48), (PSHARE_ACCESS)(Scb + 172));
      goto LABEL_88;
    }
    if ( a9 != 2 )
    {
      if ( (*(_BYTE *)(a2 + 26) & 2) == 0
        && (v19 & 0x10027) != 0
        && MmDoesFileHaveUserWritableReferences((PSECTION_OBJECT_POINTERS)(*(_QWORD *)(Scb + 240) + 8LL)) )
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
        {
          v17 = -1073741757;
        }
        else
        {
          v17 = -1073741757;
          WPP_SF_D(
            WPP_GLOBAL_Control->AttachedDevice,
            170,
            WPP_cd49aa686cfe3d14e1a2820d5064b336_Traceguids,
            3221225539LL);
        }
        if ( !RefsStatusDebugEnabled )
          goto LABEL_11;
        goto LABEL_10;
      }
      v21 = *(_WORD *)(a2 + 26);
      if ( (v21 & 1) == 0 )
      {
        v38 = RefsWriteCheck(a1, a5, *(_QWORD *)(a1 + 72));
        if ( !v38 && (*(_DWORD *)(*(_QWORD *)(a2 + 48) + 80LL) & 0x2000000) != 0 )
        {
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
          {
            v17 = -1073741790;
          }
          else
          {
            v17 = -1073741790;
            WPP_SF_D(
              WPP_GLOBAL_Control->AttachedDevice,
              171,
              WPP_cd49aa686cfe3d14e1a2820d5064b336_Traceguids,
              3221225506LL);
          }
          if ( !RefsStatusDebugEnabled )
            goto LABEL_11;
          goto LABEL_10;
        }
        v18 = 1;
        v40 = 1;
        v21 = *(_WORD *)(a2 + 26);
      }
      v17 = IoCheckShareAccessEx(
              DesiredAccess,
              v21,
              *(PFILE_OBJECT *)(a2 + 48),
              (PSHARE_ACCESS)(*a14 + 172),
              1u,
              (PBOOLEAN)((unsigned __int64)&v38 & -(__int64)(v18 != 0)));
      v42 = v17;
      if ( v17 < 0 )
        return (unsigned int)v17;
LABEL_88:
      v39 = 1;
      if ( *(_BYTE *)(*(_QWORD *)(a2 + 48) + 75LL) )
      {
        v23 = *a14;
        if ( (*(_DWORD *)(*a14 + 304) & 0x2000) == 0 && *(_WORD *)v23 == 2053 )
        {
          if ( *(_QWORD *)(v23 + 328) )
          {
            IsMinstoreTransactionActive = RefsIsMinstoreTransactionActive(a1);
            v17 = RefsBindMinstoreTransactionNoRaise();
            v42 = v17;
            if ( v17 < 0 )
              return (unsigned int)v17;
            v24 = a3 + 648;
            ExAcquirePushLockExclusiveEx(a3 + 648, 0);
            v17 = MsAddReservationForSparseWrite(
                    *(struct CmsTransactionContext **)(a1 + 24),
                    *(CmsStream **)(*a14 + 360));
            v42 = v17;
            if ( !IsMinstoreTransactionActive )
              RefsCheckpointCurrentTransaction(a1);
            if ( v17 < 0 )
            {
              ExReleasePushLockEx(v24, 0);
              return (unsigned int)v17;
            }
            *(_QWORD *)(a3 + 256) += (__int64)(*(unsigned int *)(a3 + 456) + *(_QWORD *)(*a14 + 328)) >> *(_BYTE *)(a3 + 464);
            ExReleasePushLockEx(v24, 0);
            v23 = *a14;
          }
          *(_DWORD *)(v23 + 304) |= 0x2000u;
        }
      }
      if ( a8 == 160 || (a12 & 0x20000) != 0 )
        LOBYTE(v22) = 1;
      else
        v22 = 0;
      *a15 = RefsCreateCcb(a5, *a14, v22, a12, *(_QWORD *)(a2 + 48), (__int16)PostIrpRoutine);
      v25 = a4;
      if ( a4 )
      {
        ExAcquireFastMutex((PFAST_MUTEX)(*(_QWORD *)(a5 + 96) + 8LL));
        v26 = (_QWORD *)(*a15 + 56LL);
        v27 = *(_QWORD **)(a4 + 144);
        if ( *v27 != a4 + 136 )
          __fastfail(3u);
        *v26 = a4 + 136;
        v26[1] = v27;
        *v27 = v26;
        *(_QWORD *)(a4 + 144) = v26;
        *(_QWORD *)(*a15 + 72LL) = a4;
        ExReleaseFastMutex((PFAST_MUTEX)(*(_QWORD *)(a5 + 96) + 8LL));
        v25 = a4;
      }
      v39 = 0;
      RefsIncrementCleanupCounts(*a14, v25, *(_DWORD *)(*(_QWORD *)(a2 + 48) + 80LL) & 8);
      LOBYTE(v28) = *(_WORD *)(*(_QWORD *)(a2 + 48) + 75LL) == 0;
      v29 = *(_DWORD *)(a5 + 4) >> 2;
      LOBYTE(v29) = (*(_DWORD *)(a5 + 4) & 4) != 0;
      RefsIncrementCloseCounts(*a14, v29, v28);
      if ( (a12 & 0x20000) != 0 )
        *(_DWORD *)(*a14 + 304) |= 0x80u;
      RefsSetFileObject(*(_QWORD *)(a2 + 48), a10, *a14, *a15);
      if ( !a11 && (DesiredAccess & 7) != 0 )
      {
        v30 = *a14;
        v31 = *(_DWORD *)(*a14 + 200);
        if ( (v31 == 128 || v31 == 176)
          && (*(_DWORD *)(*(_QWORD *)(a2 + 48) + 80LL) & 8) != 0
          && *(_DWORD *)(v30 + 144) == *(_DWORD *)(v30 + 140)
          && !*(_DWORD *)(v30 + 248) )
        {
          v32 = *(_QWORD *)(v30 + 240);
          if ( *(_QWORD *)(v32 + 8) )
          {
            if ( !*(_QWORD *)(v32 + 24)
              && MmCanFileBeTruncated((PSECTION_OBJECT_POINTERS)(v32 + 8), 0)
              && (*(_DWORD *)(*a14 + 136) & 0x20) != 0
              && (*(_DWORD *)(*(_QWORD *)(*a14 + 120) + 4LL) & 0x100) == 0 )
            {
              if ( *(_QWORD *)(a5 + 104)
                && (*(_DWORD *)(a1 + 4) & 0x10000) == 0
                && !(unsigned __int8)MsIsFastResourceHeldExclusive() )
              {
                *(_DWORD *)(a1 + 4) |= 0x10000u;
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                {
                  WPP_SF_D(
                    WPP_GLOBAL_Control->AttachedDevice,
                    172,
                    WPP_cd49aa686cfe3d14e1a2820d5064b336_Traceguids,
                    3221225688LL);
                }
                if ( RefsStatusDebugEnabled )
                  RefsStatusDebug(-1073741608);
                RefsRaiseStatusInternal(a1, 3221225688LL);
                __debugbreak();
                JUMPOUT(0x1C0153315LL);
              }
              RefsFlushAndPurgeScb(a1, *a14);
            }
          }
        }
      }
      IsEnabledDeviceUsage = Feature_Servicing_REFSDisallowDASDOplock__private_IsEnabledDeviceUsage();
      v34 = *a14;
      v35 = *(_DWORD *)(*a14 + 200);
      if ( IsEnabledDeviceUsage )
      {
        if ( (v35 != 128 && v35 != 176 || *(_WORD *)v34 != 2053 || *(_QWORD *)(*(_QWORD *)(v34 + 128) + 72LL) == v34)
          && (v35 != 160
           || *(_WORD *)(v34 + 208) != 8
           || **(_QWORD **)(v34 + 216) != 0x30003300490024LL
           || (unsigned __int16)(*(_WORD *)v34 - 2051) > 1u) )
        {
          v36 = 0;
LABEL_143:
          if ( v36 )
          {
            v17 = FsRtlCheckOplockEx((POPLOCK)(v34 + 88), *(PIRP *)(a1 + 72), 2u, 0, 0, 0);
            v42 = v17;
            if ( (*(_DWORD *)(a2 + 16) & 0x10000) != 0 )
            {
              v17 = FsRtlOplockFsctrl((POPLOCK)(*a14 + 88), *(PIRP *)(a1 + 72), *(_DWORD *)(*a14 + 144));
              v42 = v17;
            }
          }
          goto LABEL_146;
        }
      }
      else if ( (v35 != 128 && v35 != 176 || *(_WORD *)v34 != 2053)
             && (v35 != 160
              || *(_WORD *)(v34 + 208) != 8
              || **(_QWORD **)(v34 + 216) != 0x30003300490024LL
              || (unsigned __int16)(*(_WORD *)v34 - 2051) > 1u) )
      {
LABEL_146:
        if ( (*(_DWORD *)(a2 + 16) & 0x100000) != 0 )
          FsRtlOplockFsctrl((POPLOCK)(*a14 + 88), *(PIRP *)(a1 + 72), 1u);
        goto LABEL_148;
      }
      v36 = 1;
      goto LABEL_143;
    }
    if ( (*(_BYTE *)(a2 + 26) & 2) == 0
      && (v19 & 0x10027) != 0
      && MmDoesFileHaveUserWritableReferences((PSECTION_OBJECT_POINTERS)(*(_QWORD *)(Scb + 240) + 8LL)) )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      {
        v17 = -1073741757;
      }
      else
      {
        v17 = -1073741757;
        WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 168, WPP_cd49aa686cfe3d14e1a2820d5064b336_Traceguids, 3221225539LL);
      }
      if ( !RefsStatusDebugEnabled )
        goto LABEL_11;
    }
    else
    {
      if ( (*(_BYTE *)(a2 + 26) & 1) != 0
        || (v38 = RefsWriteCheck(a1, a5, *(_QWORD *)(a1 + 72)), v18 = 1, v40 = 1, v38)
        || (*(_DWORD *)(*(_QWORD *)(a2 + 48) + 80LL) & 0x2000000) == 0 )
      {
        IoSetShareAccessEx(
          DesiredAccess,
          *(unsigned __int16 *)(a2 + 26),
          *(PFILE_OBJECT *)(a2 + 48),
          (PSHARE_ACCESS)(*a14 + 172),
          (PBOOLEAN)((unsigned __int64)&v38 & -(__int64)(v18 != 0)));
        goto LABEL_88;
      }
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      {
        v17 = -1073741790;
      }
      else
      {
        v17 = -1073741790;
        WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 169, WPP_cd49aa686cfe3d14e1a2820d5064b336_Traceguids, 3221225506LL);
      }
      if ( !RefsStatusDebugEnabled )
        goto LABEL_11;
    }
LABEL_10:
    RefsStatusDebug(v17);
LABEL_11:
    v42 = v17;
    return (unsigned int)v17;
  }
LABEL_148:
  if ( (*(_DWORD *)(a5 + 160) & 0x100) != 0 )
  {
    *(_DWORD *)(*a14 + 304) |= 0x100u;
    *(_DWORD *)(*(_QWORD *)(a2 + 48) + 80LL) |= 0x8000u;
  }
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x1c0152814  mov     rax, rsp
0x1c0152817  mov     [rax+20h], r9
0x1c015281b  mov     [rax+18h], r8
0x1c015281f  mov     [rax+10h], rdx
0x1c0152823  push    rbx
0x1c0152824  push    rsi
0x1c0152825  push    rdi
0x1c0152826  push    r12
0x1c0152828  push    r13
0x1c015282a  push    r14
0x1c015282c  push    r15
0x1c015282e  sub     rsp, 40h
0x1c0152832  mov     rdi, rdx
0x1c0152835  mov     r14, rcx
0x1c0152838  xor     esi, esi
0x1c015283a  mov     ebx, esi
0x1c015283c  mov     [rax-47h], sil
0x1c0152840  mov     [rax-48h], sil
0x1c0152844  mov     r12b, sil
0x1c0152847  mov     rax, [rdx+8]
0x1c015284b  mov     rdx, [rax+8]
0x1c015284f  mov     r8d, [rdx+14h]
0x1c0152853  mov     [rsp+78h+DesiredAccess], r8d
0x1c0152858  mov     r15, [rsp+78h+arg_68]
0x1c0152860  mov     rdx, [r15]
0x1c0152863  test    rdx, rdx
0x1c0152866  jnz     short loc_1C0152899
0x1c0152868  mov     [rsp+78h+WritePermission], rsi
0x1c015286d  mov     dword ptr [rsp+78h+Update], esi
0x1c0152871  mov     r9, [rsp+78h+arg_30]
0x1c0152879  mov     r8d, [rsp+78h+arg_38]
0x1c0152881  mov     rdx, [rsp+78h+arg_20]
0x1c0152889  call    RefsCreateScb
0x1c015288e  mov     rdx, rax
0x1c0152891  mov     [r15], rax
0x1c0152894  mov     r8d, [rsp+78h+DesiredAccess]
0x1c0152899  mov     eax, [rdx+88h]
0x1c015289f  test    al, 2
0x1c01528a1  jz      short loc_1C0152910
0x1c01528a3  lea     rax, WPP_GLOBAL_Control
0x1c01528aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1c01528b1  cmp     rcx, rax
0x1c01528b4  jz      short loc_1C01528E4
0x1c01528b6  test    dword ptr [rcx+2Ch], 100h
0x1c01528bd  jz      short loc_1C01528E4
0x1c01528bf  cmp     byte ptr [rcx+29h], 4
0x1c01528c3  jb      short loc_1C01528E4
0x1c01528c5  mov     edx, 0A4h
0x1c01528ca  mov     ebx, 0C0000056h
0x1c01528cf  mov     r9d, ebx
0x1c01528d2  lea     r8, WPP_cd49aa686cfe3d14e1a2820d5064b336_Traceguids
0x1c01528d9  mov     rcx, [rcx+18h]
0x1c01528dd  call    WPP_SF_D
0x1c01528e2  jmp     short loc_1C01528E9
0x1c01528e4  mov     ebx, 0C0000056h
0x1c01528e9  mov     al, cs:RefsStatusDebugEnabled
0x1c01528ef  test    al, al
0x1c01528f1  jz      short loc_1C0152907
0x1c01528f3  mov     r8d, 3A59h
0x1c01528f9  lea     rdx, aCreateC; "Create.c"
0x1c0152900  mov     ecx, ebx; Status
0x1c0152902  call    RefsStatusDebug
0x1c0152907  mov     [rsp+78h+var_44], ebx
0x1c015290b  jmp     loc_1C015328F
0x1c0152910  cmp     [rdx+140h], esi
0x1c0152916  jz      short loc_1C015297F
0x1c0152918  mov     rax, [rdi+8]
0x1c015291c  mov     ecx, [rax+10h]
0x1c015291f  test    cl, 6
0x1c0152922  jz      short loc_1C015297F
0x1c0152924  lea     rax, WPP_GLOBAL_Control
0x1c015292b  mov     rcx, cs:WPP_GLOBAL_Control
0x1c0152932  cmp     rcx, rax
0x1c0152935  jz      short loc_1C0152965
0x1c0152937  test    dword ptr [rcx+2Ch], 100h
0x1c015293e  jz      short loc_1C0152965
0x1c0152940  cmp     byte ptr [rcx+29h], 4
0x1c0152944  jb      short loc_1C0152965
0x1c0152946  mov     edx, 0A5h
0x1c015294b  mov     ebx, 0C0000022h
0x1c0152950  mov     r9d, ebx
0x1c0152953  lea     r8, WPP_cd49aa686cfe3d14e1a2820d5064b336_Traceguids
0x1c015295a  mov     rcx, [rcx+18h]
0x1c015295e  call    WPP_SF_D
0x1c0152963  jmp     short loc_1C015296A
0x1c0152965  mov     ebx, 0C0000022h
0x1c015296a  mov     al, cs:RefsStatusDebugEnabled
0x1c0152970  test    al, al
0x1c0152972  jz      short loc_1C0152907
0x1c0152974  mov     r8d, 3A65h
0x1c015297a  jmp     loc_1C01528F9
0x1c015297f  cmp     [rsp+78h+arg_60], rsi
0x1c0152987  jnz     loc_1C0153267
0x1c015298d  test    dword ptr [rdi+10h], 100000h
0x1c0152994  jz      loc_1C0152A82
0x1c015299a  mov     r9d, 805h
0x1c01529a0  cmp     [rdx], r9w
0x1c01529a4  jz      short loc_1C0152A05
0x1c01529a6  lea     rax, WPP_GLOBAL_Control
0x1c01529ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1c01529b4  cmp     rcx, rax
0x1c01529b7  jz      short loc_1C01529E7
0x1c01529b9  test    dword ptr [rcx+2Ch], 100h
0x1c01529c0  jz      short loc_1C01529E7
0x1c01529c2  cmp     byte ptr [rcx+29h], 4
0x1c01529c6  jb      short loc_1C01529E7
0x1c01529c8  mov     edx, 0A6h
0x1c01529cd  mov     ebx, 0C000000Dh
0x1c01529d2  mov     r9d, ebx
0x1c01529d5  lea     r8, WPP_cd49aa686cfe3d14e1a2820d5064b336_Traceguids
0x1c01529dc  mov     rcx, [rcx+18h]
0x1c01529e0  call    WPP_SF_D
0x1c01529e5  jmp     short loc_1C01529EC
0x1c01529e7  mov     ebx, 0C000000Dh
0x1c01529ec  mov     al, cs:RefsStatusDebugEnabled
0x1c01529f2  test    al, al
0x1c01529f4  jz      loc_1C0152907
0x1c01529fa  mov     r8d, 3A79h
0x1c0152a00  jmp     loc_1C01528F9
0x1c0152a05  cmp     [rdx+90h], esi
0x1c0152a0b  jnz     short loc_1C0152A23
0x1c0152a0d  mov     rax, [rdi+8]
0x1c0152a11  test    dword ptr [rax+10h], 0FFFFFF7Fh
0x1c0152a18  jnz     short loc_1C0152A23
0x1c0152a1a  mov     al, [rdi+1Ah]
0x1c0152a1d  and     al, 7
0x1c0152a1f  cmp     al, 7
0x1c0152a21  jz      short loc_1C0152A82
0x1c0152a23  lea     rax, WPP_GLOBAL_Control
0x1c0152a2a  mov     rcx, cs:WPP_GLOBAL_Control
0x1c0152a31  cmp     rcx, rax
0x1c0152a34  jz      short loc_1C0152A64
0x1c0152a36  test    dword ptr [rcx+2Ch], 100h
0x1c0152a3d  jz      short loc_1C0152A64
0x1c0152a3f  cmp     byte ptr [rcx+29h], 4
0x1c0152a43  jb      short loc_1C0152A64
0x1c0152a45  mov     edx, 0A7h
0x1c0152a4a  mov     ebx, 0C00000E2h
0x1c0152a4f  mov     r9d, ebx
0x1c0152a52  lea     r8, WPP_cd49aa686cfe3d14e1a2820d5064b336_Traceguids
0x1c0152a59  mov     rcx, [rcx+18h]
0x1c0152a5d  call    WPP_SF_D
0x1c0152a62  jmp     short loc_1C0152A69
0x1c0152a64  mov     ebx, 0C00000E2h
0x1c0152a69  mov     al, cs:RefsStatusDebugEnabled
0x1c0152a6f  test    al, al
0x1c0152a71  jz      loc_1C0152907
0x1c0152a77  mov     r8d, 3A88h
0x1c0152a7d  jmp     loc_1C01528F9
0x1c0152a82  mov     ecx, [rsp+78h+arg_40]
0x1c0152a89  sub     ecx, 1
0x1c0152a8c  jz      loc_1C0152D93
0x1c0152a92  cmp     ecx, 1
0x1c0152a95  jz      loc_1C0152C25
0x1c0152a9b  test    byte ptr [rdi+1Ah], 2
0x1c0152a9f  jnz     loc_1C0152B2D
0x1c0152aa5  test    r8d, 10027h
0x1c0152aac  jz      short loc_1C0152B2D
0x1c0152aae  mov     rcx, [rdx+0F0h]
0x1c0152ab5  mov     r13d, 8
0x1c0152abb  add     rcx, r13; SectionPointer
0x1c0152abe  call    cs:__imp_MmDoesFileHaveUserWritableReferences
0x1c0152ac5  nop     dword ptr [rax+rax+00h]
0x1c0152aca  test    eax, eax
0x1c0152acc  jz      short loc_1C0152B33
0x1c0152ace  lea     rax, WPP_GLOBAL_Control
0x1c0152ad5  mov     rcx, cs:WPP_GLOBAL_Control
0x1c0152adc  cmp     rcx, rax
0x1c0152adf  jz      short loc_1C0152B0F
0x1c0152ae1  test    dword ptr [rcx+2Ch], 100h
0x1c0152ae8  jz      short loc_1C0152B0F
0x1c0152aea  cmp     byte ptr [rcx+29h], 4
0x1c0152aee  jb      short loc_1C0152B0F
0x1c0152af0  mov     edx, 0AAh
0x1c0152af5  mov     ebx, 0C0000043h
0x1c0152afa  mov     r9d, ebx
0x1c0152afd  lea     r8, WPP_cd49aa686cfe3d14e1a2820d5064b336_Traceguids
0x1c0152b04  mov     rcx, [rcx+18h]
0x1c0152b08  call    WPP_SF_D
0x1c0152b0d  jmp     short loc_1C0152B14
0x1c0152b0f  mov     ebx, 0C0000043h
0x1c0152b14  mov     al, cs:RefsStatusDebugEnabled
0x1c0152b1a  test    al, al
0x1c0152b1c  jz      loc_1C0152907
0x1c0152b22  mov     r8d, 3AE9h
0x1c0152b28  jmp     loc_1C01528F9
0x1c0152b2d  mov     r13d, 8
0x1c0152b33  movzx   ecx, word ptr [rdi+1Ah]
0x1c0152b37  mov     esi, 1
0x1c0152b3c  test    sil, cl
0x1c0152b3f  jnz     loc_1C0152BD9
0x1c0152b45  mov     r8, [r14+48h]
0x1c0152b49  mov     rdx, [rsp+78h+arg_20]
0x1c0152b51  mov     rcx, r14
0x1c0152b54  call    RefsWriteCheck
0x1c0152b59  mov     [rsp+78h+var_48], al
0x1c0152b5d  test    al, al
0x1c0152b5f  jnz     short loc_1C0152BCD
0x1c0152b61  mov     rax, [rdi+30h]
0x1c0152b65  test    dword ptr [rax+50h], 2000000h
0x1c0152b6c  jz      short loc_1C0152BCD
0x1c0152b6e  lea     rax, WPP_GLOBAL_Control
0x1c0152b75  mov     rcx, cs:WPP_GLOBAL_Control
0x1c0152b7c  cmp     rcx, rax
0x1c0152b7f  jz      short loc_1C0152BAF
0x1c0152b81  test    dword ptr [rcx+2Ch], 100h
0x1c0152b88  jz      short loc_1C0152BAF
0x1c0152b8a  cmp     byte ptr [rcx+29h], 4
0x1c0152b8e  jb      short loc_1C0152BAF
0x1c0152b90  mov     edx, 0ABh
0x1c0152b95  mov     ebx, 0C0000022h
0x1c0152b9a  mov     r9d, ebx
0x1c0152b9d  lea     r8, WPP_cd49aa686cfe3d14e1a2820d5064b336_Traceguids
0x1c0152ba4  mov     rcx, [rcx+18h]
0x1c0152ba8  call    WPP_SF_D
0x1c0152bad  jmp     short loc_1C0152BB4
0x1c0152baf  mov     ebx, 0C0000022h
0x1c0152bb4  mov     al, cs:RefsStatusDebugEnabled
0x1c0152bba  test    al, al
0x1c0152bbc  jz      loc_1C0152907
0x1c0152bc2  mov     r8d, 3AFDh
0x1c0152bc8  jmp     loc_1C01528F9
0x1c0152bcd  mov     r12b, sil
0x1c0152bd0  mov     [rsp+78h+var_46], sil
0x1c0152bd5  movzx   ecx, word ptr [rdi+1Ah]
0x1c0152bd9  neg     r12b
0x1c0152bdc  sbb     rax, rax
0x1c0152bdf  lea     rdx, [rsp+78h+var_48]
0x1c0152be4  and     rax, rdx
0x1c0152be7  mov     r9, [r15]
0x1c0152bea  add     r9, 0ACh; ShareAccess
0x1c0152bf1  movzx   edx, cx; DesiredShareAccess
0x1c0152bf4  mov     [rsp+78h+WritePermission], rax; WritePermission
0x1c0152bf9  mov     [rsp+78h+Update], sil; Update
0x1c0152bfe  mov     r8, [rdi+30h]; FileObject
0x1c0152c02  mov     ecx, [rsp+78h+DesiredAccess]; DesiredAccess
0x1c0152c06  call    cs:__imp_IoCheckShareAccessEx
0x1c0152c0d  nop     dword ptr [rax+rax+00h]
0x1c0152c12  mov     ebx, eax
0x1c0152c14  mov     [rsp+78h+var_44], eax
0x1c0152c18  test    eax, eax
0x1c0152c1a  jns     loc_1C0152DB3
0x1c0152c20  jmp     loc_1C015328F
0x1c0152c25  test    byte ptr [rdi+1Ah], 2
0x1c0152c29  jnz     loc_1C0152CB7
0x1c0152c2f  test    r8d, 10027h
0x1c0152c36  jz      short loc_1C0152CB7
0x1c0152c38  mov     rcx, [rdx+0F0h]
0x1c0152c3f  mov     r13d, 8
0x1c0152c45  add     rcx, r13; SectionPointer
0x1c0152c48  call    cs:__imp_MmDoesFileHaveUserWritableReferences
0x1c0152c4f  nop     dword ptr [rax+rax+00h]
0x1c0152c54  test    eax, eax
0x1c0152c56  jz      short loc_1C0152CBD
0x1c0152c58  lea     rax, WPP_GLOBAL_Control
0x1c0152c5f  mov     rcx, cs:WPP_GLOBAL_Control
0x1c0152c66  cmp     rcx, rax
0x1c0152c69  jz      short loc_1C0152C99
0x1c0152c6b  test    dword ptr [rcx+2Ch], 100h
0x1c0152c72  jz      short loc_1C0152C99
0x1c0152c74  cmp     byte ptr [rcx+29h], 4
0x1c0152c78  jb      short loc_1C0152C99
0x1c0152c7a  mov     edx, 0A8h
0x1c0152c7f  mov     ebx, 0C0000043h
0x1c0152c84  mov     r9d, ebx
0x1c0152c87  lea     r8, WPP_cd49aa686cfe3d14e1a2820d5064b336_Traceguids
0x1c0152c8e  mov     rcx, [rcx+18h]
0x1c0152c92  call    WPP_SF_D
0x1c0152c97  jmp     short loc_1C0152C9E
0x1c0152c99  mov     ebx, 0C0000043h
0x1c0152c9e  mov     al, cs:RefsStatusDebugEnabled
0x1c0152ca4  test    al, al
0x1c0152ca6  jz      loc_1C0152907
0x1c0152cac  mov     r8d, 3AADh
0x1c0152cb2  jmp     loc_1C01528F9
0x1c0152cb7  mov     r13d, 8
0x1c0152cbd  mov     esi, 1
0x1c0152cc2  test    [rdi+1Ah], sil
0x1c0152cc6  jnz     loc_1C0152D5C
0x1c0152ccc  mov     r8, [r14+48h]
0x1c0152cd0  mov     rdx, [rsp+78h+arg_20]
0x1c0152cd8  mov     rcx, r14
0x1c0152cdb  call    RefsWriteCheck
0x1c0152ce0  mov     [rsp+78h+var_48], al
0x1c0152ce4  mov     r12b, sil
0x1c0152ce7  mov     [rsp+78h+var_46], sil
0x1c0152cec  test    al, al
0x1c0152cee  jnz     short loc_1C0152D5C
0x1c0152cf0  mov     rax, [rdi+30h]
0x1c0152cf4  test    dword ptr [rax+50h], 2000000h
0x1c0152cfb  jz      short loc_1C0152D5C
0x1c0152cfd  lea     rax, WPP_GLOBAL_Control
0x1c0152d04  mov     rcx, cs:WPP_GLOBAL_Control
0x1c0152d0b  cmp     rcx, rax
0x1c0152d0e  jz      short loc_1C0152D3E
0x1c0152d10  test    dword ptr [rcx+2Ch], 100h
0x1c0152d17  jz      short loc_1C0152D3E
0x1c0152d19  cmp     byte ptr [rcx+29h], 4
0x1c0152d1d  jb      short loc_1C0152D3E
0x1c0152d1f  mov     edx, 0A9h
  ... truncated ...
```
