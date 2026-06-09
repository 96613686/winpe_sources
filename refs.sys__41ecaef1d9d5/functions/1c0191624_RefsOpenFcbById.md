# RefsOpenFcbById

- ea: `0x1c0191624`
- end: `0x1c019305c`
- name: `RefsOpenFcbById`
- size: `6712`
- prototype: ``
- caller_count: `2`
- callee_count: `38`
- tags: `reparse_path, installer_update`

## callers

- `0x1c015eb64`
- `0x1c0161594`

## callees

- `0x1c00028dc`
- `0x1c0002b1c`
- `0x1c0002bac`
- `0x1c0002c84`
- `0x1c0002ce0`
- `0x1c0003fb0`
- `0x1c00040f8`
- `0x1c0004484`
- `0x1c00046d4`
- `0x1c0005818`
- `0x1c000f770`
- `0x1c003b25c`
- `0x1c0063db0`
- `0x1c0068168`
- `0x1c0068960`
- `0x1c006af80`
- `0x1c0092414`
- `0x1c00a2b70`
- `0x1c00a2d2c`
- `0x1c014fc14`
- `0x1c015043c`
- `0x1c0151cec`
- `0x1c0152188`
- `0x1c0153508`
- `0x1c0153d80`
- `0x1c0156b80`
- `0x1c015ac58`
- `0x1c015e134`
- `0x1c01632d4`
- `0x1c0165b54`
- `0x1c0165d18`
- `0x1c016995c`
- `0x1c0178228`
- `0x1c0190898`
- `0x1c01909c8`
- `0x1c0191624`
- `0x1c0196914`
- `0x1c01d55c8`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1c0192801`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0192f6e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0192801`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c0192f6e`
- `ntoskrnl!ExAcquireFastMutex` at `0x1c0191888`
- `ntoskrnl!ExAcquireFastMutex` at `0x1c0192060`
- `ntoskrnl!ExAcquireFastMutex` at `0x1c019278b`
- `ntoskrnl!ExAcquireFastMutex` at `0x1c0192ef9`
- `ntoskrnl!ExAcquireFastMutex` at `0x1c0191888`
- `ntoskrnl!ExAcquireFastMutex` at `0x1c0192060`
- `ntoskrnl!ExAcquireFastMutex` at `0x1c019278b`
- `ntoskrnl!ExAcquireFastMutex` at `0x1c0192ef9`
- `ntoskrnl!ExReleaseFastMutex` at `0x1c01918ba`
- `ntoskrnl!ExReleaseFastMutex` at `0x1c0192091`
- `ntoskrnl!ExReleaseFastMutex` at `0x1c01927d6`
- `ntoskrnl!ExReleaseFastMutex` at `0x1c0192f45`
- `ntoskrnl!ExReleaseFastMutex` at `0x1c01918ba`
- `ntoskrnl!ExReleaseFastMutex` at `0x1c0192091`
- `ntoskrnl!ExReleaseFastMutex` at `0x1c01927d6`
- `ntoskrnl!ExReleaseFastMutex` at `0x1c0192f45`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1c0191a02`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1c0191b32`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1c0191eb3`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1c0191fc0`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1c0191a02`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1c0191b32`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1c0191eb3`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1c0191fc0`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1c0191b01`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1c0191b56`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1c0191f95`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1c0191fe2`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1c0192757`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1c0192eb6`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1c0191b01`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1c0191b56`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1c0191f95`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1c0191fe2`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1c0192757`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1c0192eb6`

## string_xrefs

- `0x1c0191799`: `Create.c`
- `0x1c019180a`: `Create.c`
- `0x1c01919a2`: `Create.c`
- `0x1c019291a`: `Create.c`

## pseudocode

```c
__int64 __fastcall RefsOpenFcbById(
        __int64 a1,
        IRP *a2,
        __int64 a3,
        _QWORD *a4,
        const UNICODE_STRING *a5,
        int a6,
        _QWORD *a7)
{
  _QWORD *v10; // r13
  __int64 *v11; // r12
  __int64 v12; // rsi
  __int128 v13; // xmm6
  __int16 v14; // dx
  char v15; // r8
  __int64 result; // rax
  __int64 v17; // rcx
  NTSTATUS v18; // ebx
  __int64 v19; // r8
  __int64 Fcb; // rax
  char v21; // al
  __int64 v22; // rcx
  int v23; // eax
  __int64 v24; // rax
  __int64 Scb; // rdx
  __int64 v26; // rcx
  unsigned int v27; // eax
  __int64 v28; // r9
  __int64 v29; // rax
  int *v30; // rdx
  int v31; // ecx
  int FileId; // eax
  __int64 v33; // r9
  int *v34; // rcx
  __int64 v35; // rsi
  __int64 v36; // rbx
  int v37; // ebx
  __int64 v38; // rax
  char v39; // al
  __int64 v40; // rcx
  int v41; // eax
  __int64 v42; // rdx
  __int64 Lcb; // rbx
  unsigned int v44; // eax
  __int64 v45; // r9
  int v46; // eax
  __int64 v47; // rbx
  unsigned int v48; // eax
  __int64 v49; // rcx
  __int128 v50; // rax
  __int64 v51; // rax
  int v52; // eax
  __int64 v53; // rax
  __int64 v54; // rcx
  __int64 v55; // rcx
  int v56; // ecx
  _QWORD *v57; // rax
  __int64 v58; // rdx
  __int64 v59; // rcx
  __int64 v60; // r8
  int v61; // r14d
  int v62; // eax
  __int64 v63; // r9
  __int64 v64; // rdx
  __int64 v65; // r8
  __int64 v66; // rcx
  __int64 v67; // rcx
  __int64 v68; // r14
  __int64 v69; // rdx
  unsigned int v70; // eax
  unsigned int v71; // eax
  unsigned int v72; // eax
  unsigned int v73; // eax
  unsigned int v74; // eax
  int v75; // [rsp+20h] [rbp-208h]
  char v76; // [rsp+50h] [rbp-1D8h]
  NTSTATUS Status; // [rsp+54h] [rbp-1D4h]
  unsigned int Statusa; // [rsp+54h] [rbp-1D4h]
  unsigned int Statusb; // [rsp+54h] [rbp-1D4h]
  unsigned int Statusc; // [rsp+54h] [rbp-1D4h]
  unsigned int Statusd; // [rsp+54h] [rbp-1D4h]
  unsigned int Statuse; // [rsp+54h] [rbp-1D4h]
  char v83; // [rsp+58h] [rbp-1D0h] BYREF
  char v84; // [rsp+59h] [rbp-1CFh] BYREF
  char v85; // [rsp+5Ah] [rbp-1CEh]
  char updated; // [rsp+5Bh] [rbp-1CDh]
  int v87; // [rsp+5Ch] [rbp-1CCh] BYREF
  __int64 v88; // [rsp+60h] [rbp-1C8h]
  __int64 v89; // [rsp+68h] [rbp-1C0h]
  char v90[8]; // [rsp+70h] [rbp-1B8h] BYREF
  _QWORD *v91; // [rsp+78h] [rbp-1B0h]
  __int64 v92; // [rsp+80h] [rbp-1A8h]
  __int64 v93; // [rsp+88h] [rbp-1A0h]
  _QWORD *v94; // [rsp+90h] [rbp-198h]
  int v95; // [rsp+98h] [rbp-190h] BYREF
  int *v96; // [rsp+A0h] [rbp-188h]
  int v97; // [rsp+A8h] [rbp-180h]
  int v98; // [rsp+ACh] [rbp-17Ch]
  __int128 v99; // [rsp+B0h] [rbp-178h] BYREF
  PCUNICODE_STRING v100; // [rsp+C0h] [rbp-168h] BYREF
  __int64 v101; // [rsp+C8h] [rbp-160h] BYREF
  PVOID P; // [rsp+D0h] [rbp-158h]
  IRP *v103; // [rsp+D8h] [rbp-150h]
  __int64 v104; // [rsp+E0h] [rbp-148h]
  __int64 v105; // [rsp+E8h] [rbp-140h]
  __int128 v106; // [rsp+F0h] [rbp-138h]
  _QWORD v107[2]; // [rsp+100h] [rbp-128h] BYREF
  __int64 v108; // [rsp+110h] [rbp-118h]
  __int128 v109; // [rsp+120h] [rbp-108h] BYREF
  __int128 v110; // [rsp+130h] [rbp-F8h] BYREF
  _OWORD v111[2]; // [rsp+140h] [rbp-E8h] BYREF
  __int64 v112; // [rsp+160h] [rbp-C8h]
  _BYTE v113[96]; // [rsp+170h] [rbp-B8h] BYREF

  v94 = a4;
  v108 = a3;
  v103 = a2;
  v105 = a1;
  v100 = a5;
  v10 = a7;
  v91 = a7;
  v104 = (__int64)a7;
  v11 = 0;
  v83 = 0;
  v12 = 0;
  v88 = 0;
  v89 = 0;
  v93 = 0;
  v87 = 0;
  v101 = 0;
  P = 0;
  v95 = 0;
  v97 = 0;
  memset(v111, 0, sizeof(v111));
  v112 = 0;
  updated = 0;
  v76 = 0;
  v13 = *(_OWORD *)a4;
  if ( *(_OWORD *)a4 == __PAIR128__(1312, 256) )
  {
    if ( a5->Length || (a7[19] & 0x8000) != 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 66, WPP_cd49aa686cfe3d14e1a2820d5064b336_Traceguids, 3221225485LL);
      }
      if ( !RefsStatusDebugEnabled )
        return 3221225485LL;
      goto LABEL_22;
    }
    *(_DWORD *)(a1 + 8) |= 0x300u;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 67, WPP_cd49aa686cfe3d14e1a2820d5064b336_Traceguids, 3221225688LL);
    }
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741608);
    v23 = RefsRaiseStatusInternal(a1, 3221225688LL);
LABEL_238:
    v89 = v22;
    *(_DWORD *)(a1 + 8) = v23 | 0x100;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 71, v11, 3221225688LL);
    }
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741608);
    v24 = RefsRaiseStatusInternal(a1, 3221225688LL);
LABEL_245:
    v70 = RefsQueueTriageForDeadFileId(a1, v24, v94);
    Statusc = v70;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 72, v11, v70);
    }
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(Statusc);
    v29 = RefsRaiseStatusInternal(a1, Statusc);
LABEL_252:
    v71 = RefsQueueTriageForDeadFileId(a1, v29, v94);
    Statusa = v71;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 74, v11, v71);
    }
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(Statusa);
    RefsRaiseStatusInternal(a1, Statusa);
LABEL_259:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 76, v11, v28);
    }
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(Statusa);
    RefsRaiseStatusInternal(a1, Statusa);
LABEL_266:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 78, v11, v33);
    }
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(Statusa);
    RefsRaiseStatusInternal(a1, Statusa);
LABEL_273:
    v72 = RefsQueueTriageForDeadLink(a1, v92, &v101);
    Statusd = v72;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 80, v11, v72);
    }
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(Statusd);
    v41 = RefsRaiseStatusInternal(a1, Statusd);
LABEL_280:
    v88 = v40;
    *(_DWORD *)(a1 + 8) = v41 | 0x100;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 82, v11, 3221225688LL);
    }
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741608);
    RefsRaiseStatusInternal(a1, 3221225688LL);
LABEL_287:
    v73 = RefsQueueTriageForDeadFileId(a1, v42, v94);
    Statusb = v73;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 83, v11, v73);
    }
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(Statusb);
    RefsRaiseStatusInternal(a1, Statusb);
LABEL_294:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 84, v11, v45);
    }
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(Statusb);
    v52 = RefsRaiseStatusInternal(a1, Statusb);
LABEL_301:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, (unsigned int)(v19 + 87), v11, (unsigned int)v52);
    }
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(Statusb);
    v53 = RefsRaiseStatusInternal(a1, Statusb);
LABEL_308:
    v74 = RefsQueueTriageForDeadFileId(v54, v53, v94);
    Statuse = v74;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 79, v11, v74);
    }
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(Statuse);
    RefsRaiseStatusInternal(a1, Statuse);
    goto LABEL_315;
  }
  if ( (unsigned __int8)RefsIsSystemObjectId(a4, 0, 0) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 68, WPP_cd49aa686cfe3d14e1a2820d5064b336_Traceguids, 3221225485LL);
    }
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741811);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 69, WPP_cd49aa686cfe3d14e1a2820d5064b336_Traceguids, 3221225485LL);
    }
    if ( !RefsStatusDebugEnabled )
      return 3221225485LL;
LABEL_22:
    RefsStatusDebug(-1073741811);
    return 3221225485LL;
  }
  if ( a3 )
  {
    v17 = *(_QWORD *)(a3 + 24);
    if ( v17 )
    {
      ExAcquireFastMutex(*(PFAST_MUTEX *)(v17 + 48));
      _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(a3 + 24) + 156LL));
      ++*(_DWORD *)(a3 + 184);
      _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(a3 + 24) + 156LL));
      ExReleaseFastMutex(*(PFAST_MUTEX *)(*(_QWORD *)(a3 + 24) + 48LL));
      v10[16] = a3;
      v12 = v88;
      v14 = v97;
      v15 = v87;
    }
  }
  if ( v10[13] )
  {
    v12 = v10[13];
    v88 = v12;
    v15 = 1;
    v87 = 1;
  }
  else if ( !*a4 )
  {
    v100 = &RefsFileNameIndex;
    a6 = 160;
    v14 = 0x8000;
    v97 = 0x8000;
  }
  v18 = RefsCheckValidAttributeAccess(
          a1,
          v10[21],
          *(_QWORD *)(a1 + 64),
          (v12 + 112) & -(__int64)((v15 & 1) != 0),
          &v100,
          &a6,
          v14,
          &v95,
          &v83);
  Status = v18;
  if ( v18 >= 0 )
  {
    v19 = 0;
    if ( !v10[13] )
    {
      v99 = 0;
      *((_QWORD *)&v99 + 1) = a4[1];
      *(_QWORD *)&v99 = 0;
      v11 = WPP_cd49aa686cfe3d14e1a2820d5064b336_Traceguids;
      while ( 1 )
      {
        while ( 1 )
        {
          if ( v12 )
          {
            v55 = (__int64)v91;
            v91[13] = v12;
            v76 = 0;
            goto LABEL_147;
          }
          v98 = 6;
          v92 = 0;
          KeAcquireGuardedMutex((PKGUARDED_MUTEX)(*(_QWORD *)(a1 + 64) + 536LL));
          v76 = 1;
          v109 = v99;
          Fcb = RefsCreateFcb(a1, *(_QWORD *)(a1 + 64), (unsigned int)&v109, 6, 0, 0, (__int64)&v87);
          v89 = Fcb;
          if ( (v87 & 2) != 0 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              WPP_SF_D(
                WPP_GLOBAL_Control->AttachedDevice,
                70,
                WPP_cd49aa686cfe3d14e1a2820d5064b336_Traceguids,
                3221225485LL);
            }
            if ( !RefsStatusDebugEnabled )
              goto LABEL_42;
            goto LABEL_41;
          }
          v21 = RefsAcquireFcbWithPaging(a1, Fcb, 0, 3);
          v22 = 0;
          if ( !v21 )
          {
            if ( v93 )
            {
              v23 = *(_DWORD *)(a1 + 8);
              if ( (v23 & 0x100) == 0 )
                goto LABEL_238;
            }
            ++*(_DWORD *)(v89 + 32);
            KeReleaseGuardedMutex((PKGUARDED_MUTEX)(*(_QWORD *)(a1 + 64) + 536LL));
            RefsAcquireFcbWithPaging(a1, v89, 0, 5);
            KeAcquireGuardedMutex((PKGUARDED_MUTEX)(*(_QWORD *)(a1 + 64) + 536LL));
            --*(_DWORD *)(v89 + 32);
          }
          KeReleaseGuardedMutex((PKGUARDED_MUTEX)(*(_QWORD *)(a1 + 64) + 536LL));
          v76 = 0;
          if ( (v87 & 1) != 0 && (*(_DWORD *)(v89 + 4) & 0x8000001) == 1 )
          {
            v24 = v93;
            if ( v93 )
              goto LABEL_245;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              WPP_SF_D(
                WPP_GLOBAL_Control->AttachedDevice,
                73,
                WPP_cd49aa686cfe3d14e1a2820d5064b336_Traceguids,
                3221225485LL);
            }
            if ( !RefsStatusDebugEnabled )
              goto LABEL_42;
LABEL_41:
            RefsStatusDebug(-1073741811);
LABEL_42:
            v18 = -1073741811;
            goto LABEL_43;
          }
          Scb = RefsCreateScb(a1, v89, 160, (unsigned int)&RefsFileNameIndex, 0, 0);
          v92 = Scb;
          v26 = v89;
          v96 = (int *)(v89 + 4);
          if ( (*(_DWORD *)(v89 + 4) & 1) != 0 && (*(_DWORD *)(Scb + 304) & 0x40) == 0 )
          {
            RefsMarkAllScbsAsDeleted(a1, v89);
            v26 = v89;
          }
          v27 = RefsOpenFile(a1, v26);
          v28 = v27;
          Statusa = v27;
          if ( v27 == -1073741772 || v27 == -1073741809 || v27 == -1073741275 )
          {
            RefsMarkAllScbsAsDeleted(a1, v89);
            *v96 |= 1u;
            v29 = v93;
            if ( v93 )
              goto LABEL_252;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              WPP_SF_D(
                WPP_GLOBAL_Control->AttachedDevice,
                75,
                WPP_cd49aa686cfe3d14e1a2820d5064b336_Traceguids,
                3221225485LL);
            }
            if ( RefsStatusDebugEnabled )
              RefsStatusDebug(-1073741811);
            v28 = 3221225485LL;
            Statusa = -1073741811;
            v12 = v88;
          }
          if ( (int)v28 < 0 )
            goto LABEL_259;
          v30 = v96;
          v31 = *v96;
          if ( (*v96 & 8) == 0 )
          {
            RefsUpdateFcbInfoFromDisk(a1, 0, v89, 0);
            v30 = v96;
            v31 = *v96;
          }
          if ( (v31 & 0x8000001) == 0x8000000 )
          {
            *v30 = v31 | 1;
            RefsMarkAllScbsAsDeleted(a1, v89);
          }
          v19 = 0;
          if ( !*v94 )
            break;
          v99 = 0u;
          FileId = RefsFindFileId(a1, v92, (_DWORD)v94, (unsigned int)&v101, (__int64)&v99);
          v33 = (unsigned int)FileId;
          Statusa = FileId;
          if ( FileId == -1073741772 || FileId == -1073741809 || FileId == -1073741275 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              WPP_SF_D(
                WPP_GLOBAL_Control->AttachedDevice,
                77,
                WPP_cd49aa686cfe3d14e1a2820d5064b336_Traceguids,
                3221225485LL);
            }
            if ( !RefsStatusDebugEnabled )
              goto LABEL_42;
            goto LABEL_41;
          }
          if ( FileId < 0 )
            goto LABEL_266;
          if ( v99 == 0 )
          {
            v34 = v96;
            if ( (*v96 & 0x8000000) != 0 )
              goto LABEL_273;
            v35 = v92;
            if ( v93 )
            {
              v84 = 0;
              _InterlockedIncrement((volatile signed __int32 *)(v92 + 148));
              v36 = v93;
              RefsTeardownStructures(a1, *(_QWORD *)(v93 + 120), 0, &v84);
              _InterlockedDecrement((volatile signed __int32 *)(v35 + 148));
              if ( !v84 )
                RefsReleaseFcb(a1, *(_QWORD *)(v36 + 120));
              v93 = 0;
              v34 = v96;
            }
            v98 = 4;
            if ( !*(_WORD *)(v35 + 360) && (*v34 & 0x8000000) == 0 )
              RefsBuildNormalizedNameImplementation(a1, v89, v35, v35 + 360);
            v37 = 4;
            if ( (*(_BYTE *)(v91[21] + 2LL) & 2) != 0 )
              v37 = 5;
            v98 = v37;
            v87 = 0;
            RefsCheckpointCurrentTransaction(a1);
            KeAcquireGuardedMutex((PKGUARDED_MUTEX)(*(_QWORD *)(a1 + 64) + 536LL));
            v76 = 1;
            v110 = v13;
            v38 = RefsCreateFcb(a1, *(_QWORD *)(a1 + 64), (unsigned int)&v110, v37, v35, (__int64)&v101, (__int64)&v87);
            v12 = v38;
            v88 = v38;
            if ( (v87 & 2) != 0 )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
              {
                WPP_SF_D(
                  WPP_GLOBAL_Control->AttachedDevice,
                  81,
                  WPP_cd49aa686cfe3d14e1a2820d5064b336_Traceguids,
                  3221225485LL);
              }
              if ( !RefsStatusDebugEnabled )
                goto LABEL_42;
              goto LABEL_41;
            }
            v39 = RefsAcquireFcbWithPaging(a1, v38, 0, 3);
            v40 = 0;
            if ( !v39 )
            {
              v41 = *(_DWORD *)(a1 + 8);
              if ( (v41 & 0x100) == 0 )
                goto LABEL_280;
              ++*(_DWORD *)(v12 + 32);
              KeReleaseGuardedMutex((PKGUARDED_MUTEX)(*(_QWORD *)(a1 + 64) + 536LL));
              RefsAcquireFcbWithPaging(a1, v12, 0, 5);
              KeAcquireGuardedMutex((PKGUARDED_MUTEX)(*(_QWORD *)(a1 + 64) + 536LL));
              --*(_DWORD *)(v12 + 32);
            }
            KeReleaseGuardedMutex((PKGUARDED_MUTEX)(*(_QWORD *)(a1 + 64) + 536LL));
            v76 = 0;
            v42 = v92;
            if ( (*(_DWORD *)(v12 + 4) & 1) != 0 )
              goto LABEL_287;
            Lcb = RefsCreateLcb(a1, v92, v12, (unsigned int)&v101, 0, 0);
            v89 = 0;
            v44 = RefsOpenFile(a1, v12);
            v45 = v44;
            Statusb = v44;
            if ( v44 == -1073741772 || v44 == -1073741809 || v44 == -1073741275 )
            {
              ExAcquireFastMutex(*(PFAST_MUTEX *)(*(_QWORD *)(Lcb + 24) + 48LL));
              _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(Lcb + 24) + 156LL));
              RefsRemovePrefixSafe(Lcb);
              _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(Lcb + 24) + 156LL));
              ExReleaseFastMutex(*(PFAST_MUTEX *)(*(_QWORD *)(Lcb + 24) + 48LL));
              v46 = *(_DWORD *)(Lcb + 4);
              if ( (v46 & 0x20) != 0 )
              {
                RefsRemoveHashEntry(
                  *(_QWORD *)(*(_QWORD *)(Lcb + 32) + 88LL) + 2696LL,
                  *(unsigned int *)(Lcb + 192),
                  Lcb);
                *(_DWORD *)(Lcb + 192) = 0;
                *(_DWORD *)(Lcb + 4) &= ~0x20u;
                v46 = *(_DWORD *)(Lcb + 4);
              }
              *(_DWORD *)(Lcb + 4) = v46 | 2;
              *(_DWORD *)(Lcb + 188) = 0;
              *(_DWORD *)(Lcb + 172) = 0;
              v47 = v92;
              v48 = RefsQueueTriageForDeadFileId(a1, v92, v94);
              v45 = v48;
              Statusb = v48;
              v12 = v88;
            }
            else
            {
              v47 = v92;
            }
            if ( (int)v45 < 0 )
              goto LABEL_294;
            memset(v113, 0, sizeof(v113));
            v85 = 1;
            *(_QWORD *)&v50 = RefsMapStandardInfo(a1, v12, v113);
            v49 = *(_QWORD *)(v47 + 120);
            *((_QWORD *)&v50 + 1) = *(_QWORD *)(v49 + 16);
            if ( *(_QWORD *)(v50 + 104) && *(_QWORD *)(v50 + 88) >= *(_QWORD *)(v49 + 264) )
            {
              v106 = *(_OWORD *)(v50 + 96);
              v50 = v106;
            }
            else
            {
              *(_QWORD *)&v50 = *(_QWORD *)(v50 + 88);
              v106 = v50;
            }
            if ( *(_OWORD *)(v12 + 8) != v50 )
              v85 = 0;
            RefsUnmapStandardInfo(a1, v12, v113);
            if ( !v85 )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
              {
                WPP_SF_D(
                  WPP_GLOBAL_Control->AttachedDevice,
                  85,
                  WPP_cd49aa686cfe3d14e1a2820d5064b336_Traceguids,
                  3221225485LL);
              }
              if ( !RefsStatusDebugEnabled )
                goto LABEL_42;
              goto LABEL_41;
            }
            v107[0] = 0;
            v107[1] = 0;
            v90[0] = 0;
            v51 = RefsCreateScb(a1, v12, 128, (unsigned int)v107, 0, (__int64)v90);
            v52 = RefsInitializeFileFromDisk(a1, v51, 2);
            Statusb = v52;
            v19 = 0;
            if ( v52 < 0 )
              goto LABEL_301;
          }
          else
          {
            v53 = v93;
            v54 = a1;
            if ( v93 )
              goto LABEL_308;
            v93 = v92;
            v89 = 0;
            v92 = 0;
            *(_OWORD *)v94 = v99;
            *(_QWORD *)&v99 = 0;
            RefsCheckpointCurrentTransaction(a1);
LABEL_143:
            v19 = 0;
          }
        }
        if ( (*v96 & 0x8000000) != 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_D(
              WPP_GLOBAL_Control->AttachedDevice,
              88,
              WPP_cd49aa686cfe3d14e1a2820d5064b336_Traceguids,
              3221225485LL);
          }
          if ( !RefsStatusDebugEnabled )
            goto LABEL_42;
          goto LABEL_41;
        }
        v12 = v89;
        v88 = v89;
        if ( !*(_WORD *)(v92 + 360) )
        {
          RefsBuildNormalizedNameImplementation(a1, v89, v92, v92 + 360);
          goto LABEL_143;
        }
      }
    }
    v11 = WPP_cd49aa686cfe3d14e1a2820d5064b336_Traceguids;
    v55 = (__int64)v91;
LABEL_147:
    if ( (*(_DWORD *)(v12 + 4) & 0x100) != 0 && (*(_QWORD *)(v12 + 16) != 1312 || *(_QWORD *)(v12 + 8) != 256) )
    {
      LOBYTE(v19) = v103->RequestorMode;
      if ( !(unsigned __int8)RefsCheckValidFileAccess(v12, *(_QWORD *)(v55 + 168), v19, &v95) )
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
        {
          v18 = -1073741790;
        }
        else
        {
          v18 = -1073741790;
          WPP_SF_D(
            WPP_GLOBAL_Control->AttachedDevice,
            89,
            WPP_cd49aa686cfe3d14e1a2820d5064b336_Traceguids,
            3221225506LL);
        }
        if ( !RefsStatusDebugEnabled )
          goto LABEL_43;
LABEL_157:
        RefsStatusDebug(v18);
        goto LABEL_43;
      }
    }
    v56 = *(_DWORD *)(v91[21] + 16LL);
    if ( (v56 & 1) != 0 || v83 )
    {
      v57 = v94;
      if ( *v94 )
      {
LABEL_315:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 90, v11, 3221225731LL);
        }
        if ( RefsStatusDebugEnabled )
          RefsStatusDebug(-1073741565);
        RefsRaiseStatusInternal(a1, 3221225731LL);
        goto LABEL_322;
      }
    }
    else
    {
      v57 = v94;
    }
    if ( ((v56 & 0x40) != 0 || !v83) && !*v57 )
    {
LABEL_322:
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 91, v11, 3221225658LL);
      }
      if ( RefsStatusDebugEnabled )
        RefsStatusDebug(-1073741638);
      result = RefsRaiseStatusInternal(a1, 3221225658LL);
      __debugbreak();
      return result;
    }
    if ( (v87 & 1) != 0 && (v18 = RefsHandlePagingFile(a1, v103, v12), Status = v18, v18 < 0) )
    {
      v10 = v91;
    }
    else
    {
      if ( (*(_DWORD *)(v12 + 4) & 8) == 0 )
        updated = RefsUpdateFcbInfoFromDisk(a1, 0, v12, v111);
      if ( (unsigned __int8)RefsIsMinstoreTransactionActive(a1) )
      {
        RefsCheckpointCurrentTransaction(v59);
        if ( *(_WORD *)(a1 + 42) )
          RefsReleaseSharedResources(a1);
      }
      if ( *(_WORD *)(v12 + 172) )
      {
        v10 = v91;
        v61 = (int)v103;
        v62 = RefsOpenAttributeInExistingFile(a1, v103, v108, 0, &v100->Length, a6, v95, (__int64)v91);
        v18 = v62;
        Status = v62;
        if ( v62 > -1 && (unsigned int)(v62 - 259) > 1 && v62 != 871 )
        {
          v63 = v10[14];
          v64 = *(_QWORD *)(v12 + 136);
          v65 = *(_QWORD *)(v12 + 176);
          if ( v64 + RefsLastAccess < v65 || v65 < v64 )
          {
            *(_DWORD *)(v12 + 4) |= 0x10u;
            *(_DWORD *)(v12 + 168) |= 0x20u;
            *(_DWORD *)(v10[15] + 4LL) |= 0x10000u;
          }
          if ( !v83 )
          {
            if ( (*(_DWORD *)(v63 + 136) & 0x20) == 0 )
            {
              if ( !updated || a6 != 128 || v100->Length || (*(_DWORD *)(a1 + 4) & 4) != 0 )
                RefsUpdateScbFromAttribute(a1, v63, 0);
              else
                RefsUpdateScbFromMemory(v63, v111);
            }
            v66 = v10[21];
            if ( (*(_DWORD *)(v66 + 16) & 8) == 0 )
              *(_DWORD *)(*(_QWORD *)(v66 + 48) + 80LL) |= 0x40u;
          }
          if ( !v10[18] )
            RefsEncryptionCreateCallback(a1, v61, v10[14], v63, v75, (__int64)v10, 0);
        }
      }
      else
      {
        if ( (unsigned __int8)RefsIsSystemObjectId(v12 + 8, v58, v60) )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_D(
              WPP_GLOBAL_Control->AttachedDevice,
              92,
              WPP_cd49aa686cfe3d14e1a2820d5064b336_Traceguids,
              3221225485LL);
          }
          if ( RefsStatusDebugEnabled )
            goto LABEL_41;
          goto LABEL_42;
        }
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
        {
          v18 = -1073741738;
        }
        else
        {
          v18 = -1073741738;
          WPP_SF_D(
            WPP_GLOBAL_Control->AttachedDevice,
            93,
            WPP_cd49aa686cfe3d14e1a2820d5064b336_Traceguids,
            3221225558LL);
        }
        if ( RefsStatusDebugEnabled )
          goto LABEL_157;
LABEL_43:
        Status = v18;
        v12 = v88;
        v10 = v91;
      }
    }
  }
  if ( v76 )
    KeReleaseGuardedMutex((PKGUARDED_MUTEX)(*(_QWORD *)(a1 + 64) + 536LL));
  if ( v18 != 871 && v18 != 259 )
  {
    v67 = v10[16];
    if ( v67 )
    {
      ExAcquireFastMutex(*(PFAST_MUTEX *)(*(_QWORD *)(v67 + 24) + 48LL));
      _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(v10[16] + 24LL) + 156LL));
      --*(_DWORD *)(v10[16] + 184LL);
      _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(v10[16] + 24LL) + 156LL));
      ExReleaseFastMutex(*(PFAST_MUTEX *)(*(_QWORD *)(v10[16] + 24LL) + 48LL));
      v10[16] = 0;
      v18 = Status;
      v12 = v88;
    }
  }
  if ( P )
    ExFreePoolWithTag(P, 0);
  v68 = v93;
  if ( v18 != 871 && !v10[13] )
  {
    if ( v93 )
      RefsIncrementCloseCounts(v93, 0, 0);
    if ( v89 )
    {
      v69 = v89;
    }
    else
    {
      if ( !v12 )
        goto LABEL_224;
      v69 = v12;
    }
    RefsTeardownStructures(a1, v69, 0, 0);
  }
LABEL_224:
  if ( v18 < 0 && v10[14] && v10[15] )
    RefsBackoutFailedOpensPriv(a1, *(_QWORD *)(v10[21] + 48LL), v12);
  if ( v68 )
  {
    RefsTeardownStructures(a1, *(_QWORD *)(v68 + 120), 0, 0);
    RefsDecrementCloseCounts(a1, v68, 0, 0, 0, 0, 0);
  }
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x1c0191624  mov     r11, rsp
0x1c0191627  push    rbx
0x1c0191628  push    rsi
0x1c0191629  push    rdi
0x1c019162a  push    r12
0x1c019162c  push    r13
0x1c019162e  push    r14
0x1c0191630  push    r15
0x1c0191632  sub     rsp, 1F0h
0x1c0191639  movaps  xmmword ptr [r11-48h], xmm6
0x1c019163e  mov     rax, cs:__security_cookie
0x1c0191645  xor     rax, rsp
0x1c0191648  mov     [rsp+228h+var_58], rax
0x1c0191650  mov     r14, r9
0x1c0191653  mov     [rsp+228h+var_198], r9
0x1c019165b  mov     rbx, r8
0x1c019165e  mov     [rsp+228h+var_118], rbx
0x1c0191666  mov     [rsp+228h+var_150], rdx
0x1c019166e  mov     rdi, rcx
0x1c0191671  mov     [rsp+228h+var_140], rcx
0x1c0191679  mov     rax, [rsp+228h+arg_20]
0x1c0191681  mov     [r11-168h], rax
0x1c0191688  mov     r13, [rsp+228h+arg_30]
0x1c0191690  mov     [rsp+228h+var_1B0], r13
0x1c0191695  mov     [rsp+228h+var_148], r13
0x1c019169d  xor     r12d, r12d
0x1c01916a0  mov     [rsp+228h+Status], r12d
0x1c01916a5  mov     [rsp+228h+var_1D0], r12b
0x1c01916aa  mov     esi, r12d
0x1c01916ad  mov     [rsp+228h+var_1C8], r12
0x1c01916b2  mov     [rsp+228h+var_1C0], r12
0x1c01916b7  mov     [r11-1A0h], r12
0x1c01916be  mov     r8d, r12d
0x1c01916c1  mov     [rsp+228h+var_1CC], r12d
0x1c01916c6  mov     [r11-160h], r12
0x1c01916cd  mov     [r11-158h], r12
0x1c01916d4  mov     [r11-190h], r12d
0x1c01916db  mov     edx, r12d
0x1c01916de  mov     [rsp+228h+var_180], edx
0x1c01916e5  xorps   xmm0, xmm0
0x1c01916e8  xor     ecx, ecx
0x1c01916ea  movups  [rsp+228h+var_E8], xmm0
0x1c01916f2  movups  [rsp+228h+var_D8], xmm0
0x1c01916fa  mov     [r11-0C8h], rcx
0x1c0191701  mov     [rsp+228h+var_1CD], r12b
0x1c0191706  mov     [rsp+228h+var_1D8], r12b
0x1c019170b  movaps  xmm6, xmmword ptr [r9]
0x1c019170f  mov     r15d, 100h
0x1c0191715  cmp     qword ptr [r9+8], 520h
0x1c019171d  jnz     loc_1C01917A5
0x1c0191723  cmp     [r9], r15
0x1c0191726  jnz     short loc_1C01917A5
0x1c0191728  cmp     [rax], r12w
0x1c019172c  jnz     short loc_1C0191740
0x1c019172e  mov     edx, 8000h
0x1c0191733  test    [r13+98h], edx
0x1c019173a  jz      loc_1C01928C9
0x1c0191740  lea     rbx, WPP_GLOBAL_Control
0x1c0191747  mov     rcx, cs:WPP_GLOBAL_Control
0x1c019174e  cmp     rcx, rbx
0x1c0191751  jz      short loc_1C019177F
0x1c0191753  test    [rcx+2Ch], r15d
0x1c0191757  jz      short loc_1C019177F
0x1c0191759  cmp     byte ptr [rcx+29h], 4
0x1c019175d  jb      short loc_1C019177F
0x1c019175f  mov     edx, 42h ; 'B'
0x1c0191764  mov     r14d, 0C000000Dh
0x1c019176a  mov     r9d, r14d
0x1c019176d  lea     r8, WPP_cd49aa686cfe3d14e1a2820d5064b336_Traceguids
0x1c0191774  mov     rcx, [rcx+18h]
0x1c0191778  call    WPP_SF_D
0x1c019177d  jmp     short loc_1C0191785
0x1c019177f  mov     r14d, 0C000000Dh
0x1c0191785  mov     al, cs:RefsStatusDebugEnabled
0x1c019178b  test    al, al
0x1c019178d  jz      loc_1C019186D
0x1c0191793  mov     r8d, 160Dh
0x1c0191799  lea     rdx, aCreateC; "Create.c"
0x1c01917a0  jmp     loc_1C0191865
0x1c01917a5  mov     rcx, r14
0x1c01917a8  call    RefsIsSystemObjectId
0x1c01917ad  test    al, al
0x1c01917af  jz      loc_1C0191876
0x1c01917b5  lea     rbx, WPP_GLOBAL_Control
0x1c01917bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1c01917c3  cmp     rcx, rbx
0x1c01917c6  jz      short loc_1C01917F7
0x1c01917c8  test    [rcx+2Ch], r15d
0x1c01917cc  jz      short loc_1C01917F7
0x1c01917ce  mov     r14d, 0C000000Dh
0x1c01917d4  lea     r12, WPP_cd49aa686cfe3d14e1a2820d5064b336_Traceguids
0x1c01917db  cmp     byte ptr [rcx+29h], 4
0x1c01917df  jb      short loc_1C0191804
0x1c01917e1  mov     edx, 44h ; 'D'
0x1c01917e6  mov     r9d, r14d
0x1c01917e9  mov     r8, r12
0x1c01917ec  mov     rcx, [rcx+18h]
0x1c01917f0  call    WPP_SF_D
0x1c01917f5  jmp     short loc_1C0191804
0x1c01917f7  mov     r14d, 0C000000Dh
0x1c01917fd  lea     r12, WPP_cd49aa686cfe3d14e1a2820d5064b336_Traceguids
0x1c0191804  mov     al, cs:RefsStatusDebugEnabled
0x1c019180a  lea     r13, aCreateC; "Create.c"
0x1c0191811  test    al, al
0x1c0191813  jz      short loc_1C0191826
0x1c0191815  mov     r8d, 161Dh
0x1c019181b  mov     rdx, r13
0x1c019181e  mov     ecx, r14d; Status
0x1c0191821  call    RefsStatusDebug
0x1c0191826  mov     rcx, cs:WPP_GLOBAL_Control
0x1c019182d  cmp     rcx, rbx
0x1c0191830  jz      short loc_1C0191852
0x1c0191832  test    [rcx+2Ch], r15d
0x1c0191836  jz      short loc_1C0191852
0x1c0191838  cmp     byte ptr [rcx+29h], 4
0x1c019183c  jb      short loc_1C0191852
0x1c019183e  mov     edx, 45h ; 'E'
0x1c0191843  mov     r9d, r14d
0x1c0191846  mov     r8, r12
0x1c0191849  mov     rcx, [rcx+18h]
0x1c019184d  call    WPP_SF_D
0x1c0191852  mov     al, cs:RefsStatusDebugEnabled
0x1c0191858  test    al, al
0x1c019185a  jz      short loc_1C019186D
0x1c019185c  mov     r8d, 161Eh
0x1c0191862  mov     rdx, r13
0x1c0191865  mov     ecx, r14d; Status
0x1c0191868  call    RefsStatusDebug
0x1c019186d  mov     eax, r14d
0x1c0191870  jmp     loc_1C0192E41
0x1c0191876  test    rbx, rbx
0x1c0191879  jz      short loc_1C01918E1
0x1c019187b  mov     rcx, [rbx+18h]
0x1c019187f  test    rcx, rcx
0x1c0191882  jz      short loc_1C01918E1
0x1c0191884  mov     rcx, [rcx+30h]; FastMutex
0x1c0191888  call    cs:__imp_ExAcquireFastMutex
0x1c019188f  nop     dword ptr [rax+rax+00h]
0x1c0191894  mov     rax, [rbx+18h]
0x1c0191898  mov     r12d, 9Ch
0x1c019189e  lock inc dword ptr [rax+r12]
0x1c01918a3  inc     dword ptr [rbx+0B8h]
0x1c01918a9  mov     rax, [rbx+18h]
0x1c01918ad  lock inc dword ptr [rax+r12]
0x1c01918b2  mov     rcx, [rbx+18h]
0x1c01918b6  mov     rcx, [rcx+30h]; FastMutex
0x1c01918ba  call    cs:__imp_ExReleaseFastMutex
0x1c01918c1  nop     dword ptr [rax+rax+00h]
0x1c01918c6  mov     [r13+80h], rbx
0x1c01918cd  mov     rsi, [rsp+228h+var_1C8]
0x1c01918d2  mov     edx, [rsp+228h+var_180]
0x1c01918d9  mov     r8d, [rsp+228h+var_1CC]
0x1c01918de  xor     r12d, r12d
0x1c01918e1  mov     rax, [r13+68h]
0x1c01918e5  test    rax, rax
0x1c01918e8  jnz     short loc_1C019191A
0x1c01918ea  cmp     [r14], r12
0x1c01918ed  jnz     short loc_1C019192D
0x1c01918ef  lea     r12, RefsFileNameIndex
0x1c01918f6  mov     [rsp+228h+var_168], r12
0x1c01918fe  mov     [rsp+228h+arg_28], 0A0h
0x1c0191909  mov     edx, 8000h
0x1c019190e  mov     [rsp+228h+var_180], edx
0x1c0191915  xor     r12d, r12d
0x1c0191918  jmp     short loc_1C019192D
0x1c019191a  mov     rsi, rax
0x1c019191d  mov     [rsp+228h+var_1C8], rax
0x1c0191922  mov     r8d, 1
0x1c0191928  mov     [rsp+228h+var_1CC], r8d
0x1c019192d  mov     eax, r8d
0x1c0191930  and     al, 1
0x1c0191932  lea     rcx, [rsi+70h]
0x1c0191936  neg     al
0x1c0191938  sbb     r9, r9
0x1c019193b  and     r9, rcx
0x1c019193e  lea     rax, [rsp+228h+var_1D0]
0x1c0191943  mov     [rsp+228h+var_1E8], rax
0x1c0191948  lea     rax, [rsp+228h+var_190]
0x1c0191950  mov     [rsp+228h+var_1F0], rax
0x1c0191955  mov     dword ptr [rsp+228h+var_1F8], edx
0x1c0191959  lea     rax, [rsp+228h+arg_28]
0x1c0191961  mov     [rsp+228h+var_200], rax
0x1c0191966  lea     rax, [rsp+228h+var_168]
0x1c019196e  mov     [rsp+228h+var_208], rax
0x1c0191973  mov     r8, [rdi+40h]
0x1c0191977  mov     rdx, [r13+0A8h]
0x1c019197e  mov     rcx, rdi
0x1c0191981  call    RefsCheckValidAttributeAccess
0x1c0191986  mov     ebx, eax
0x1c0191988  mov     [rsp+228h+Status], eax
0x1c019198c  test    eax, eax
0x1c019198e  js      loc_1C0192745
0x1c0191994  lea     rbx, WPP_GLOBAL_Control
0x1c019199b  xor     r8d, r8d
0x1c019199e  cmp     [r13+68h], r12
0x1c01919a2  lea     r13, aCreateC; "Create.c"
0x1c01919a9  jnz     loc_1C01923BF
0x1c01919af  xorps   xmm0, xmm0
0x1c01919b2  movups  [rsp+228h+var_178], xmm0
0x1c01919ba  mov     rax, [r14+8]
0x1c01919be  mov     qword ptr [rsp+228h+var_178+8], rax
0x1c01919c6  mov     qword ptr [rsp+228h+var_178], r12
0x1c01919ce  lea     r12, WPP_cd49aa686cfe3d14e1a2820d5064b336_Traceguids
0x1c01919d5  mov     r14d, 0C000000Dh
0x1c01919db  test    rsi, rsi
0x1c01919de  jnz     loc_1C01923AF
0x1c01919e4  mov     [rsp+228h+var_17C], 6
0x1c01919ef  mov     [rsp+228h+var_1A8], r8
0x1c01919f7  mov     rcx, [rdi+40h]
0x1c01919fb  add     rcx, 218h; Mutex
0x1c0191a02  call    cs:__imp_KeAcquireGuardedMutex
0x1c0191a09  nop     dword ptr [rax+rax+00h]
0x1c0191a0e  mov     [rsp+228h+var_1D8], 1
0x1c0191a13  movaps  xmm0, [rsp+228h+var_178]
0x1c0191a1b  movdqa  [rsp+228h+var_108], xmm0
0x1c0191a24  lea     rax, [rsp+228h+var_1CC]
0x1c0191a29  mov     [rsp+228h+var_1F8], rax
0x1c0191a2e  xor     eax, eax
0x1c0191a30  mov     [rsp+228h+var_200], rax
0x1c0191a35  mov     [rsp+228h+var_208], rax
0x1c0191a3a  lea     r9d, [rsi+6]
0x1c0191a3e  lea     r8, [rsp+228h+var_108]
0x1c0191a46  mov     rdx, [rdi+40h]
0x1c0191a4a  mov     rcx, rdi
0x1c0191a4d  call    RefsCreateFcb
0x1c0191a52  mov     [rsp+228h+var_1C0], rax
0x1c0191a57  test    byte ptr [rsp+228h+var_1CC], 2
0x1c0191a5c  jz      short loc_1C0191ABE
0x1c0191a5e  mov     rcx, cs:WPP_GLOBAL_Control
0x1c0191a65  cmp     rcx, rbx
0x1c0191a68  jz      short loc_1C0191A8A
0x1c0191a6a  mov     eax, [rcx+2Ch]
0x1c0191a6d  test    r15d, eax
0x1c0191a70  jz      short loc_1C0191A8A
0x1c0191a72  cmp     byte ptr [rcx+29h], 4
0x1c0191a76  jb      short loc_1C0191A8A
0x1c0191a78  lea     edx, [rsi+46h]
0x1c0191a7b  mov     r9d, r14d
0x1c0191a7e  mov     r8, r12
0x1c0191a81  mov     rcx, [rcx+18h]
0x1c0191a85  call    WPP_SF_D
0x1c0191a8a  mov     al, cs:RefsStatusDebugEnabled
0x1c0191a90  xor     r12d, r12d
0x1c0191a93  test    al, al
0x1c0191a95  jz      short loc_1C0191AA8
0x1c0191a97  mov     r8d, 16A5h
0x1c0191a9d  mov     rdx, r13
0x1c0191aa0  mov     ecx, r14d; Status
0x1c0191aa3  call    RefsStatusDebug
0x1c0191aa8  mov     ebx, r14d
0x1c0191aab  mov     [rsp+228h+Status], ebx
0x1c0191aaf  mov     rsi, [rsp+228h+var_1C8]
0x1c0191ab4  mov     r13, [rsp+228h+var_1B0]
0x1c0191ab9  jmp     loc_1C0192745
0x1c0191abe  mov     r9d, 3
0x1c0191ac4  xor     r8d, r8d
0x1c0191ac7  mov     rdx, rax
0x1c0191aca  mov     rcx, rdi
0x1c0191acd  call    RefsAcquireFcbWithPaging
0x1c0191ad2  xor     ecx, ecx
0x1c0191ad4  test    al, al
0x1c0191ad6  jnz     short loc_1C0191B4B
0x1c0191ad8  cmp     [rsp+228h+var_1A0], rcx
0x1c0191ae0  jz      short loc_1C0191AEE
0x1c0191ae2  mov     eax, [rdi+8]
0x1c0191ae5  test    r15d, eax
0x1c0191ae8  jz      loc_1C0192939
0x1c0191aee  mov     rax, [rsp+228h+var_1C0]
0x1c0191af3  inc     dword ptr [rax+20h]
0x1c0191af6  mov     rcx, [rdi+40h]
0x1c0191afa  add     rcx, 218h; Mutex
0x1c0191b01  call    cs:__imp_KeReleaseGuardedMutex
0x1c0191b08  nop     dword ptr [rax+rax+00h]
0x1c0191b0d  xor     ecx, ecx
0x1c0191b0f  mov     [rsp+228h+var_1D8], cl
0x1c0191b13  lea     r9d, [rcx+5]
0x1c0191b17  xor     r8d, r8d
0x1c0191b1a  mov     rdx, [rsp+228h+var_1C0]
0x1c0191b1f  mov     rcx, rdi
0x1c0191b22  call    RefsAcquireFcbWithPaging
0x1c0191b27  mov     rcx, [rdi+40h]
0x1c0191b2b  add     rcx, 218h; Mutex
0x1c0191b32  call    cs:__imp_KeAcquireGuardedMutex
0x1c0191b39  nop     dword ptr [rax+rax+00h]
0x1c0191b3e  mov     [rsp+228h+var_1D8], 1
0x1c0191b43  mov     rax, [rsp+228h+var_1C0]
0x1c0191b48  dec     dword ptr [rax+20h]
0x1c0191b4b  mov     rcx, [rdi+40h]
0x1c0191b4f  add     rcx, 218h; Mutex
0x1c0191b56  call    cs:__imp_KeReleaseGuardedMutex
0x1c0191b5d  nop     dword ptr [rax+rax+00h]
0x1c0191b62  xor     edx, edx
0x1c0191b64  mov     [rsp+228h+var_1D8], dl
0x1c0191b68  mov     rcx, [rsp+228h+var_1C0]
0x1c0191b6d  test    byte ptr [rsp+228h+var_1CC], 1
0x1c0191b72  jz      short loc_1C0191BDC
0x1c0191b74  mov     eax, [rcx+4]
0x1c0191b77  and     eax, 8000001h
0x1c0191b7c  cmp     eax, 1
0x1c0191b7f  jnz     short loc_1C0191BDC
  ... truncated ...
```
