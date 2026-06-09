# RefsOpenFileHighLevel

- ea: `0x1c0193064`
- end: `0x1c019456c`
- name: `RefsOpenFileHighLevel`
- size: `5384`
- prototype: ``
- caller_count: `1`
- callee_count: `40`
- tags: `reparse_path, installer_update`

## callers

- `0x1c015eb64`

## callees

- `0x1c0002c84`
- `0x1c0002ce0`
- `0x1c0003fb0`
- `0x1c0004484`
- `0x1c0005490`
- `0x1c0005818`
- `0x1c000f770`
- `0x1c003b27c`
- `0x1c0063db0`
- `0x1c0064c64`
- `0x1c0068168`
- `0x1c0068960`
- `0x1c006aba0`
- `0x1c00a066c`
- `0x1c00a2d2c`
- `0x1c00b3be4`
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
- `0x1c0165b9c`
- `0x1c0165d18`
- `0x1c0168964`
- `0x1c016995c`
- `0x1c0178228`
- `0x1c018cbe8`
- `0x1c0190898`
- `0x1c01909c8`
- `0x1c0191178`
- `0x1c0193064`
- `0x1c0196774`
- `0x1c0196914`
- `0x1c01c7c08`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutex` at `0x1c0193699`
- `ntoskrnl!ExAcquireFastMutex` at `0x1c01937b2`
- `ntoskrnl!ExAcquireFastMutex` at `0x1c0193a09`
- `ntoskrnl!ExAcquireFastMutex` at `0x1c0194237`
- `ntoskrnl!ExAcquireFastMutex` at `0x1c019444a`
- `ntoskrnl!ExAcquireFastMutex` at `0x1c0193699`
- `ntoskrnl!ExAcquireFastMutex` at `0x1c01937b2`
- `ntoskrnl!ExAcquireFastMutex` at `0x1c0193a09`
- `ntoskrnl!ExAcquireFastMutex` at `0x1c0194237`
- `ntoskrnl!ExAcquireFastMutex` at `0x1c019444a`
- `ntoskrnl!ExReleaseFastMutex` at `0x1c01936d0`
- `ntoskrnl!ExReleaseFastMutex` at `0x1c01937e8`
- `ntoskrnl!ExReleaseFastMutex` at `0x1c0193a40`
- `ntoskrnl!ExReleaseFastMutex` at `0x1c0194282`
- `ntoskrnl!ExReleaseFastMutex` at `0x1c0194496`
- `ntoskrnl!ExReleaseFastMutex` at `0x1c01936d0`
- `ntoskrnl!ExReleaseFastMutex` at `0x1c01937e8`
- `ntoskrnl!ExReleaseFastMutex` at `0x1c0193a40`
- `ntoskrnl!ExReleaseFastMutex` at `0x1c0194282`
- `ntoskrnl!ExReleaseFastMutex` at `0x1c0194496`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1c01932f8`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1c0193454`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1c0193609`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1c01941d6`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1c0194368`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1c01943db`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1c01932f8`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1c0193454`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1c0193609`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1c01941d6`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1c0194368`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1c01943db`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1c0193425`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1c0193480`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1c0193580`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1c0194203`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1c019440a`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1c0193425`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1c0193480`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1c0193580`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1c0194203`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1c019440a`

## string_xrefs

- `0x1c01931e3`: `Create.c`
- `0x1c019324c`: `Create.c`
- `0x1c0193517`: `Create.c`
- `0x1c01938e4`: `Create.c`
- `0x1c0193990`: `Create.c`
- `0x1c0193b53`: `Create.c`

## pseudocode

```c
__int64 __fastcall RefsOpenFileHighLevel(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _OWORD *a4,
        __int64 a5,
        _WORD *a6,
        int a7,
        int a8,
        __int64 a9,
        __int64 *a10)
{
  __int64 Scb; // r13
  __int64 v13; // r15
  __int64 v14; // r8
  __int64 Lcb; // r14
  __int64 v16; // rdx
  __int64 v17; // r12
  __int64 result; // rax
  int v19; // ebx
  __int128 v20; // xmm6
  __int64 Fcb; // rax
  __int64 v22; // rdi
  char v23; // bl
  int v24; // ecx
  __int64 v25; // rax
  __int64 v26; // r8
  unsigned int v27; // eax
  __int64 v28; // r14
  __int64 v29; // rdi
  struct _FAST_MUTEX *v30; // r13
  char v31; // bl
  __int64 v32; // rdx
  __int64 v33; // rcx
  char v34; // bl
  const UNICODE_STRING *v35; // r9
  int v36; // r8d
  int v37; // eax
  __int64 v38; // r9
  int v39; // eax
  unsigned int v40; // eax
  int v41; // ebx
  char IsStillPresent; // al
  __int64 v43; // rcx
  NTSTATUS v44; // ebx
  unsigned __int8 v45; // r12
  _DWORD *v46; // r14
  _DWORD *v47; // rbx
  char v48; // al
  char IsMinstoreTransactionActive; // al
  __int64 v50; // rcx
  int v51; // ebx
  __int64 v52; // rcx
  int v53; // ecx
  _DWORD *v54; // r8
  _OWORD *v55; // rdx
  bool v56; // zf
  __int64 v57; // rdx
  __int64 v58; // r8
  __int64 v59; // rdx
  __int64 v60; // rax
  __int64 v61; // r9
  __int64 v62; // r13
  __int64 v63; // r8
  __int64 v64; // rcx
  __int64 v65; // r8
  __int64 v66; // rcx
  __int64 v67; // r8
  __int64 v68; // r13
  __int64 v69; // rax
  __int64 v70; // r14
  __int64 v71; // rax
  __int64 v72; // rcx
  _DWORD *v73; // rcx
  int v74; // [rsp+20h] [rbp-1B8h]
  char v75; // [rsp+50h] [rbp-188h]
  unsigned int Status; // [rsp+54h] [rbp-184h]
  unsigned int Statusa; // [rsp+54h] [rbp-184h]
  NTSTATUS Statusb; // [rsp+54h] [rbp-184h]
  char v79; // [rsp+58h] [rbp-180h] BYREF
  char v80; // [rsp+59h] [rbp-17Fh]
  char v81[6]; // [rsp+5Ah] [rbp-17Eh] BYREF
  _DWORD *v82; // [rsp+60h] [rbp-178h]
  char v83; // [rsp+68h] [rbp-170h]
  __int64 v84; // [rsp+70h] [rbp-168h]
  __int64 v85; // [rsp+78h] [rbp-160h]
  int v86; // [rsp+80h] [rbp-158h] BYREF
  __int64 v87; // [rsp+88h] [rbp-150h]
  int v88; // [rsp+90h] [rbp-148h] BYREF
  int v89; // [rsp+94h] [rbp-144h]
  __int64 v90; // [rsp+98h] [rbp-140h]
  __int64 v91; // [rsp+A0h] [rbp-138h]
  PKGUARDED_MUTEX Mutex; // [rsp+A8h] [rbp-130h]
  __int64 v93; // [rsp+B0h] [rbp-128h]
  _OWORD *v94; // [rsp+B8h] [rbp-120h]
  __int64 v95; // [rsp+C0h] [rbp-118h]
  __int64 *v96; // [rsp+C8h] [rbp-110h]
  _OWORD *v97; // [rsp+D0h] [rbp-108h]
  __int64 v98[4]; // [rsp+D8h] [rbp-100h] BYREF
  _DWORD *v99; // [rsp+F8h] [rbp-E0h]
  _QWORD v100[2]; // [rsp+100h] [rbp-D8h] BYREF
  int v101; // [rsp+110h] [rbp-C8h]
  __int64 v102; // [rsp+118h] [rbp-C0h]
  _QWORD *v103; // [rsp+120h] [rbp-B8h]
  _DWORD *v104; // [rsp+128h] [rbp-B0h]
  __int128 v105; // [rsp+130h] [rbp-A8h] BYREF
  _OWORD v106[2]; // [rsp+140h] [rbp-98h] BYREF
  _BYTE v107[32]; // [rsp+160h] [rbp-78h] BYREF
  __int64 v108; // [rsp+180h] [rbp-58h]

  Scb = (__int64)a4;
  v94 = a4;
  v85 = a3;
  v91 = a2;
  v13 = a9;
  v98[3] = a1;
  v102 = a3;
  v97 = a4;
  v90 = a5;
  v98[0] = (__int64)a6;
  v98[2] = a9;
  v96 = a10;
  v88 = 0;
  memset(v107, 0, sizeof(v107));
  v108 = 0;
  v14 = *(_QWORD *)(a3 + 128);
  v95 = v14;
  v98[1] = v14;
  v93 = 0;
  v84 = 0;
  Lcb = 0;
  v87 = 0;
  v81[0] = 0;
  v86 = 0;
  v16 = *(_QWORD *)(a9 + 168);
  v83 = *(_BYTE *)(v16 + 19);
  v17 = 256;
  if ( *a4 == __PAIR128__(1312, 256) )
  {
    if ( !*a6 && (*(_DWORD *)(a9 + 152) & 0x8000) == 0 )
    {
      *(_DWORD *)(a1 + 8) |= 0x300u;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 99, WPP_cd49aa686cfe3d14e1a2820d5064b336_Traceguids, 3221225688LL);
      }
      if ( RefsStatusDebugEnabled )
        RefsStatusDebug(-1073741608);
      RefsRaiseStatusInternal(a1, 3221225688LL);
      __debugbreak();
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 98, WPP_cd49aa686cfe3d14e1a2820d5064b336_Traceguids, 3221225485LL);
    }
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741811);
    return 3221225485LL;
  }
  v103 = a4 + 1;
  result = RefsCheckValidAttributeAccess(
             a1,
             v16,
             v14,
             (int)a4 + 16,
             (__int64)v98,
             (__int64)&a7,
             *(_DWORD *)(a9 + 152),
             (__int64)&v88,
             (__int64)v81);
  if ( (int)result < 0 )
    return result;
  v104 = (_DWORD *)(Scb + 64);
  v19 = *(_DWORD *)(Scb + 64);
  v20 = *(_OWORD *)Scb;
  v106[1] = *(_OWORD *)Scb;
  Mutex = (PKGUARDED_MUTEX)(v95 + 536);
  KeAcquireGuardedMutex((PKGUARDED_MUTEX)(v95 + 536));
  if ( (v19 & 0x10000000) != 0 )
  {
    v105 = v20;
    Fcb = RefsCreateFcb(a1, v95, (unsigned int)&v105, 2, 0, 0, (__int64)&v86);
  }
  else
  {
    v106[0] = v20;
    Fcb = RefsCreateFcb(
            a1,
            v95,
            (unsigned int)v106,
            (*(unsigned __int8 *)(*(_QWORD *)(v13 + 168) + 2LL) >> 1) & 1,
            a3,
            v90,
            (__int64)&v86);
  }
  v84 = Fcb;
  v22 = Fcb;
  v99 = (_DWORD *)(Fcb + 32);
  ++*(_DWORD *)(Fcb + 32);
  v23 = HIBYTE(v19) & 0x10 | 0x21;
  v89 = v86 & 1;
  if ( (v86 & 1) != 0 )
  {
    *v96 = 0;
    *(_QWORD *)(v13 + 104) = Fcb;
  }
  else
  {
    v93 = Fcb;
  }
  v82 = (_DWORD *)(Fcb + 4);
  v24 = *(_DWORD *)(Fcb + 4);
  if ( (v24 & 0x100) == 0 || (v25 = *(_QWORD *)(v85 + 120), *(_QWORD *)(v25 + 16) != 1536) || *(_QWORD *)(v25 + 8) )
  {
    if ( (v24 & 0x8000) == 0 )
      goto LABEL_39;
  }
  KeReleaseGuardedMutex(Mutex);
  RefsAcquireFcbWithPaging(a1, v22, 0, 1);
  KeAcquireGuardedMutex(Mutex);
  v23 = HIBYTE(v19) & 0x10 | 0x21;
  while ( 1 )
  {
    --*v99;
    KeReleaseGuardedMutex(Mutex);
    v23 &= 0xDEu;
    v75 = v23;
    *(_DWORD *)(a1 + 4) |= 0x20000000u;
    v80 = v23 & 4;
    if ( (v23 & 4) != 0 )
      break;
    if ( (*v82 & 1) == 0 )
    {
      Lcb = RefsCreateLcb(a1, v85, v22, v90, 0, 0);
      v87 = Lcb;
      v93 = 0;
      *v96 = Lcb;
      *(_QWORD *)(v13 + 104) = v22;
      v33 = *(_QWORD *)(Lcb + 24);
      if ( v33 )
      {
        ExAcquireFastMutex(*(PFAST_MUTEX *)(v33 + 48));
        _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(Lcb + 24) + 156LL));
        ++*(_DWORD *)(v87 + 184);
        _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(Lcb + 24) + 156LL));
        ExReleaseFastMutex(*(PFAST_MUTEX *)(*(_QWORD *)(Lcb + 24) + 48LL));
        Lcb = v87;
        *(_QWORD *)(v13 + 128) = v87;
        v22 = v84;
        Scb = (__int64)v97;
        v94 = v97;
      }
      break;
    }
    v27 = RefsQueueTriageForDeadLink(a1, v85, v90);
    Status = v27;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 100, WPP_cd49aa686cfe3d14e1a2820d5064b336_Traceguids, v27);
    }
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(Status);
    RefsRaiseStatusInternal(a1, Status);
LABEL_39:
    if ( !(unsigned __int8)RefsAcquireFcbWithPaging(a1, v22, 0, 3) )
    {
      v28 = v85;
      ++*(_DWORD *)(*(_QWORD *)(v85 + 120) + 32LL);
      _InterlockedIncrement((volatile signed __int32 *)(v28 + 144));
      v29 = v84;
      if ( *(_QWORD *)(v84 + 104) )
        *(_DWORD *)(a1 + 4) |= 0x10000u;
      v30 = Mutex;
      KeReleaseGuardedMutex(Mutex);
      RefsReleaseScbWithPaging(a1);
      *(_DWORD *)(v13 + 152) &= ~0x400u;
      v31 = v23 & 0xFA | 4;
      RefsAcquireFcbWithPaging(a1, v29, 0, 1);
      RefsAcquireSharedFcb(a1, *(_QWORD *)(v28 + 120), v28, 1);
      v32 = *(_QWORD *)(v28 + 120);
      if ( (*(_DWORD *)(v32 + 4) & 8) != 0 )
      {
        *(_DWORD *)(v13 + 152) |= 0x400u;
      }
      else
      {
        RefsReleaseFcb(a1, v32);
        RefsAcquireExclusiveScbWithFlags(a1, v28, 1);
      }
      KeAcquireGuardedMutex(v30);
      v23 = v31 | 1;
      _InterlockedDecrement((volatile signed __int32 *)(v28 + 144));
      --*(_DWORD *)(*(_QWORD *)(v28 + 120) + 32LL);
      v22 = v84;
      Lcb = v87;
      Scb = (__int64)v97;
      v94 = v97;
    }
  }
  if ( (*v82 & 1) == 0 )
  {
    v79 = 0;
    v34 = v23 & 0x10;
    if ( v34 )
    {
      v35 = &RefsFileNameIndex;
      v36 = 160;
    }
    else
    {
      v100[0] = 0;
      v100[1] = 0;
      v35 = (const UNICODE_STRING *)v100;
      v36 = 128;
    }
    Scb = RefsCreateScb(a1, v22, v36, (_DWORD)v35, 0, (__int64)&v79);
    v37 = RefsInitializeFileFromDisk(a1, Scb, 2);
    v17 = (unsigned int)v37;
    Statusa = v37;
    v38 = 0;
    if ( v37 >= 0 )
    {
      Scb = (__int64)v94;
      v17 = 256;
      goto LABEL_74;
    }
    if ( (v37 == -1073741772 || v37 == -1073741809 || v37 == -1073741275) && !v80 )
    {
      ExAcquireFastMutex(*(PFAST_MUTEX *)(*(_QWORD *)(Lcb + 24) + 48LL));
      _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(Lcb + 24) + 156LL));
      RefsRemovePrefixSafe(v87);
      _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(Lcb + 24) + 156LL));
      ExReleaseFastMutex(*(PFAST_MUTEX *)(*(_QWORD *)(Lcb + 24) + 48LL));
      Lcb = v87;
      v39 = *(_DWORD *)(v87 + 4);
      if ( (v39 & 0x20) != 0 )
      {
        RefsRemoveHashEntry(*(_QWORD *)(*(_QWORD *)(v87 + 32) + 88LL) + 2696LL, *(unsigned int *)(v87 + 192), v87);
        v22 = 0;
        *(_DWORD *)(Lcb + 192) = 0;
        *(_DWORD *)(Lcb + 4) &= ~0x20u;
        v39 = *(_DWORD *)(Lcb + 4);
      }
      else
      {
        v22 = 0;
      }
      *(_DWORD *)(Lcb + 4) = v39 | 2;
      *(_DWORD *)(Lcb + 188) = 0;
      *(_DWORD *)(Lcb + 172) = 0;
      v40 = RefsQueueTriageForDeadLink(a1, v85, v90);
      v17 = v40;
      Statusa = v40;
    }
    if ( (unsigned __int8)RefsIsTriagePending(a1) && Lcb && v34 )
    {
      _InterlockedIncrement((volatile signed __int32 *)(Scb + 152));
      MsTriageSetContextForName(*(_QWORD *)(a1 + 160), Scb);
      v17 = Statusa;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(
        WPP_GLOBAL_Control->AttachedDevice,
        101,
        WPP_cd49aa686cfe3d14e1a2820d5064b336_Traceguids,
        (unsigned int)v17);
    }
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(Statusa);
    RefsRaiseStatusInternal(a1, Statusa);
  }
  v38 = 0;
LABEL_74:
  v41 = v85;
  if ( v80 )
  {
    IsStillPresent = RefsNameIsStillPresent(a1, v22, v90, *(_QWORD *)(v85 + 120) + 8LL);
    v38 = 0;
    if ( !IsStillPresent )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & (unsigned int)v17) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 102, WPP_cd49aa686cfe3d14e1a2820d5064b336_Traceguids, 3221225688LL);
      }
      if ( RefsStatusDebugEnabled )
        RefsStatusDebug(-1073741608);
      RefsRaiseStatusInternal(a1, 3221225688LL);
    }
  }
  if ( !Lcb )
  {
    Lcb = RefsCreateLcb(a1, v41, v22, v90, v38, v38);
    v87 = Lcb;
    LODWORD(v38) = 0;
    v93 = 0;
    *v96 = Lcb;
    *(_QWORD *)(v13 + 104) = v22;
    v43 = *(_QWORD *)(Lcb + 24);
    if ( v43 )
    {
      ExAcquireFastMutex(*(PFAST_MUTEX *)(v43 + 48));
      _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(Lcb + 24) + 156LL));
      ++*(_DWORD *)(v87 + 184);
      _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(Lcb + 24) + 156LL));
      ExReleaseFastMutex(*(PFAST_MUTEX *)(*(_QWORD *)(Lcb + 24) + 48LL));
      Lcb = v87;
      *(_QWORD *)(v13 + 128) = v87;
      v22 = v84;
      Scb = (__int64)v97;
      v94 = v97;
      LODWORD(v38) = 0;
    }
  }
  if ( v89 == (_DWORD)v38 || (v44 = RefsHandlePagingFile(a1, v91, v22), Statusb = v44, LODWORD(v38) = 0, v44 >= 0) )
  {
    v47 = v82;
    if ( ((unsigned int)v17 & *v82) != 0
      && *(_QWORD *)(v22 + 16) == 1312
      && *(_QWORD *)(v22 + 8) == v17
      && (LOBYTE(v26) = *(_BYTE *)(v91 + 64),
          v48 = RefsCheckValidFileAccess(v22, *(_QWORD *)(v13 + 168), v26, &v88),
          LODWORD(v38) = 0,
          !v48) )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & (unsigned int)v17) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      {
        v44 = -1073741790;
      }
      else
      {
        v44 = -1073741790;
        WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 103, WPP_cd49aa686cfe3d14e1a2820d5064b336_Traceguids, 3221225506LL);
      }
      if ( !RefsStatusDebugEnabled )
        goto LABEL_100;
    }
    else
    {
      if ( (*v47 & 8) != 0 )
      {
        v45 = v75;
      }
      else
      {
        v45 = (v75 ^ (8 * RefsUpdateFcbInfoFromDisk(a1, 0, v22, v107))) & 8 ^ v75;
        v75 = v45;
        *(_QWORD *)(v22 + 136) = *(_QWORD *)(Scb + 40);
        IsMinstoreTransactionActive = RefsIsMinstoreTransactionActive(a1);
        LODWORD(v38) = 0;
        if ( IsMinstoreTransactionActive )
        {
          RefsCheckpointCurrentTransaction(v50);
          LODWORD(v38) = 0;
          if ( *(_WORD *)(a1 + 42) )
          {
            RefsReleaseSharedResources(a1);
            LODWORD(v38) = 0;
          }
        }
      }
      if ( (((v86 & 1) != 0) & (v45 >> 2)) != 0 && *(_WORD *)(v22 + 172) == (_WORD)v38 )
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
        {
          v44 = -1073741738;
        }
        else
        {
          v44 = -1073741738;
          WPP_SF_D(
            WPP_GLOBAL_Control->AttachedDevice,
            104,
            WPP_cd49aa686cfe3d14e1a2820d5064b336_Traceguids,
            3221225558LL);
        }
        if ( !RefsStatusDebugEnabled )
          goto LABEL_100;
      }
      else
      {
        if ( *(_DWORD *)(v22 + 24) == (_DWORD)v38 )
        {
          v89 = *(_DWORD *)(v22 + 168);
          v101 = v89;
          v51 = v89;
          v52 = *(_QWORD *)(v22 + 112) - *v103;
          if ( !v52 )
          {
            v52 = *(_QWORD *)(v22 + 120) - v103[1];
            if ( !v52 )
              v52 = *(_QWORD *)(v22 + 128) - v103[2];
          }
          if ( v52 )
          {
            v45 |= 2u;
            v75 = v45;
            if ( *(_QWORD *)(v22 + 112) != *v103 )
            {
              v51 = v89 | 0x40;
              *(_DWORD *)(v22 + 168) = v89 | 0x40;
            }
            if ( *(_QWORD *)(v22 + 120) != *(_QWORD *)(Scb + 24) )
            {
              v51 |= 0x10u;
              *(_DWORD *)(v22 + 168) = v51;
            }
            if ( *(_QWORD *)(v22 + 128) != *(_QWORD *)(Scb + 32) )
            {
              v51 |= 0x80000000;
              *(_DWORD *)(v22 + 168) = v51;
            }
          }
          if ( memcmp((const void *)(v22 + 144), (const void *)(Scb + 48), 0x16u) )
          {
            v45 |= 2u;
            v75 = v45;
            v53 = v51;
            v54 = v82;
            if ( *(_QWORD *)(v22 + 144) != *(_QWORD *)(Scb + 48) )
            {
              *(_DWORD *)(v22 + 168) = v51 | 0x40000000;
              *v54 |= 0x40010u;
              v53 = *(_DWORD *)(v22 + 168);
            }
            v51 = v53;
            v55 = v94;
            if ( *(_QWORD *)(v22 + 152) != *((_QWORD *)v94 + 7) )
            {
              *(_DWORD *)(v22 + 168) = v53 | 8;
              *v54 |= 0x40010u;
              v51 = *(_DWORD *)(v22 + 168);
            }
            if ( *(_DWORD *)(v22 + 160) != *v104 )
            {
              v51 |= 4u;
              *(_DWORD *)(v22 + 168) = v51;
            }
            if ( *(_WORD *)(v22 + 164) != *((_WORD *)v55 + 34) )
            {
              v51 |= 0x80u;
              *(_DWORD *)(v22 + 168) = v51;
            }
          }
          v56 = v51 == v89;
          v47 = v82;
          if ( !v56 )
            *v82 |= 0x40000u;
          v57 = *(_QWORD *)(v22 + 136);
          v58 = *(_QWORD *)(v22 + 176);
          if ( v57 + RefsLastAccess < v58 || v58 < v57 )
          {
            *(_DWORD *)(v22 + 168) |= 0x20u;
            v45 |= 2u;
            v75 = v45;
          }
        }
        if ( (*(_DWORD *)(Lcb + 4) & 1) == 0 && *(_WORD *)(v22 + 172) )
        {
          v59 = v85;
          if ( !*(_WORD *)(v85 + 360) )
          {
            RefsBuildNormalizedNameImplementation(a1, *(_QWORD *)(v85 + 120), v85, v85 + 360);
            v59 = v85;
          }
          if ( ((v83 & 0xFA) != 0 || v83 == 1) && v83 != 3 )
          {
            if ( (*v47 & 0x100) == 0
              || (v60 = *(_QWORD *)(v59 + 120), *(_QWORD *)(v60 + 16) != 1536)
              || *(_QWORD *)(v60 + 8) )
            {
              if ( (*v47 & 0x8000) == 0 )
              {
                RefsReleaseScbWithPaging(a1);
                *(_DWORD *)(v13 + 152) &= ~0x400u;
                RefsCheckpointCurrentTransaction(a1);
              }
            }
          }
          v44 = RefsOpenAttributeInExistingFile(a1, v98[0], a7, v88, v13);
          Statusb = v44;
          *(_DWORD *)(a1 + 4) &= ~0x20000000u;
          if ( (unsigned int)(v44 - 259) > 1 && v44 > -1 && v44 != 871 )
          {
            v62 = *(_QWORD *)(v13 + 112);
            if ( *(_WORD *)v62 == 2051 )
            {
              v61 = v62 + 360;
              if ( !*(_WORD *)(v62 + 360) )
              {
                v63 = *(_QWORD *)(v13 + 112);
                if ( *(_WORD *)(v85 + 360) )
                  RefsUpdateNormalizedName(a1, v85, v63, *(_QWORD *)(Lcb + 200), 0);
                else
                  RefsBuildNormalizedNameImplementation(a1, *(_QWORD *)(v62 + 120), v63, v61);
              }
            }
            v64 = *(_QWORD *)(Lcb + 32);
            if ( (*(_DWORD *)(v64 + 4) & 0x100) == 0 )
            {
              v65 = *(unsigned int *)(v13 + 92);
              if ( (_DWORD)v65 )
              {
                if ( (*(_BYTE *)(Lcb + 4) & 0x20) != 0 )
                {
                  RefsRemoveHashEntry(*(_QWORD *)(v64 + 88) + 2696LL, *(unsigned int *)(Lcb + 192), Lcb);
                  *(_DWORD *)(Lcb + 192) = 0;
                  *(_DWORD *)(Lcb + 4) &= ~0x20u;
                  v65 = *(unsigned int *)(v13 + 92);
                }
                RefsInsertPrefixHashEntry(v95 + 2696, Lcb, v65, *(unsigned int *)(v13 + 88));
              }
              RefsInsertPrefix(Lcb, *(unsigned int *)(v13 + 152));
            }
            if ( !v81[0] )
            {
              if ( (*(_DWORD *)(v62 + 136) & 0x20) == 0 )
              {
                if ( (v45 & 8) == 0 || a7 != 128 || *(_WORD *)v98[0] || (*(_DWORD *)(a1 + 4) & 4) != 0 )
                  RefsUpdateScbFromAttribute(a1, v62, 0);
                else
                  RefsUpdateScbFromMemory(v62, v107);
              }
              v66 = *(_QWORD *)(v13 + 168);
              if ( (*(_DWORD *)(v66 + 16) & 8) == 0 )
                *(_DWORD *)(*(_QWORD *)(v66 + 48) + 80LL) |= 0x40u;
            }
            v46 = v82;
            if ( (*v82 & 4) != 0 && *(_QWORD *)(v62 + 24) && (*(_DWORD *)(v62 + 136) & 8) == 0 )
            {
              v67 = v62;
              v68 = v91;
              RefsPrepareForCriticalIo(a1, v91, v67, 3);
            }
            else
            {
              v68 = v91;
            }
            if ( !*(_QWORD *)(v13 + 144) )
              RefsEncryptionCreateCallback(a1, v68, *(_QWORD *)(v13 + 112), v61, v74, v13, 0);
            if ( (v45 & 2) == 0 )
            {
              v69 = *(_QWORD *)(v68 + 56);
              if ( (v69 & 0xFFFFFFFFFFFFFFFCuLL) != 0 || v69 == 1 )
                goto LABEL_200;
            }
            v56 = (*v46 & 0x100) == 0;
            v70 = v85;
            if ( v56 || (v71 = *(_QWORD *)(v85 + 120), *(_QWORD *)(v71 + 16) != 1536) || *(_QWORD *)(v71 + 8) )
            {
              if ( (*(_DWORD *)(v13 + 152) & 0x400) != 0 )
              {
                RefsReleaseFcb(a1, *(_QWORD *)(v85 + 120));
                *(_DWORD *)(v13 + 152) &= ~0x400u;
              }
              RefsUpdateAllInformation(
                a1,
                *(_QWORD *)(*(_QWORD *)(v13 + 168) + 48LL),
                v22,
                *(_QWORD *)(v13 + 112),
                *(_QWORD *)(v13 + 120),
                *v96,
                v70);
            }
          }
          goto LABEL_101;
        }
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
        {
          v44 = -1073741738;
        }
        else
        {
          v44 = -1073741738;
          WPP_SF_D(
            WPP_GLOBAL_Control->AttachedDevice,
            105,
            WPP_cd49aa686cfe3d14e1a2820d5064b336_Traceguids,
            3221225558LL);
        }
        if ( !RefsStatusDebugEnabled )
        {
LABEL_100:
          Statusb = v44;
          v22 = v84;
          v45 = v75;
LABEL_101:
          v46 = v82;
          goto LABEL_200;
        }
      }
    }
    RefsStatusDebug(v44);
    goto LABEL_100;
  }
  v45 = v75;
  v46 = v82;
LABEL_200:
  if ( v44 != 871 )
    *(_DWORD *)(a1 + 4) &= ~0x20000000u;
  if ( (v45 & 0x20) != 0 )
  {
    if ( (v45 & 1) == 0 )
    {
      KeAcquireGuardedMutex(Mutex);
      v45 |= 1u;
    }
    --*v99;
  }
  if ( (v45 & 1) != 0 )
    KeReleaseGuardedMutex(Mutex);
  if ( v44 != 871 && v44 != 259 )
  {
    v72 = *(_QWORD *)(v13 + 128);
    if ( v72 )
    {
      ExAcquireFastMutex(*(PFAST_MUTEX *)(*(_QWORD *)(v72 + 24) + 48LL));
      _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(*(_QWORD *)(v13 + 128) + 24LL) + 156LL));
      --*(_DWORD *)(*(_QWORD *)(v13 + 128) + 184LL);
      _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(*(_QWORD *)(v13 + 128) + 24LL) + 156LL));
      ExReleaseFastMutex(*(PFAST_MUTEX *)(*(_QWORD *)(*(_QWORD *)(v13 + 128) + 24LL) + 48LL));
      *(_QWORD *)(v13 + 128) = 0;
      v44 = Statusb;
      v22 = v84;
    }
  }
  if ( v44 < 0 )
  {
    v73 = (_DWORD *)(v13 + 176);
    if ( v13 != -176 && *v73 )
    {
      *(_DWORD *)(v22 + 160) ^= *v73;
      if ( (*v46 & 8) != 0 )
        *v46 |= 0x10u;
      *v73 = 0;
    }
    if ( *(_QWORD *)(v13 + 112) && *(_QWORD *)(v13 + 120) )
      RefsBackoutFailedOpensPriv(a1, *(_QWORD *)(*(_QWORD *)(v13 + 168) + 48LL), v22);
  }
  if ( v93 && v44 != 259 && v44 != 871 )
    RefsTeardownStructures(a1, v22, 0, 0);
  return (unsigned int)v44;
}

```

## disassembly

```asm
0x1c0193064  mov     r11, rsp
0x1c0193067  push    rbx
0x1c0193068  push    rsi
0x1c0193069  push    rdi
0x1c019306a  push    r12
0x1c019306c  push    r13
0x1c019306e  push    r14
0x1c0193070  push    r15
0x1c0193072  sub     rsp, 1A0h
0x1c0193079  movaps  xmmword ptr [r11-48h], xmm6
0x1c019307e  mov     rax, cs:__security_cookie
0x1c0193085  xor     rax, rsp
0x1c0193088  mov     [rsp+1D8h+var_50], rax
0x1c0193090  mov     r13, r9
0x1c0193093  mov     [r11-120h], r9
0x1c019309a  mov     rdi, r8
0x1c019309d  mov     [rsp+1D8h+var_160], r8
0x1c01930a2  mov     [rsp+1D8h+var_138], rdx
0x1c01930aa  mov     rsi, rcx
0x1c01930ad  mov     r15, [rsp+1D8h+arg_40]
0x1c01930b5  mov     [rsp+1D8h+var_E8], rcx
0x1c01930bd  mov     [rsp+1D8h+var_C0], r8
0x1c01930c5  mov     [r11-108h], r9
0x1c01930cc  mov     rax, [rsp+1D8h+arg_20]
0x1c01930d4  mov     [rsp+1D8h+var_140], rax
0x1c01930dc  mov     rax, [rsp+1D8h+arg_28]
0x1c01930e4  mov     [r11-100h], rax
0x1c01930eb  mov     [rsp+1D8h+var_F0], r15
0x1c01930f3  mov     rcx, [rsp+1D8h+arg_48]
0x1c01930fb  mov     [rsp+1D8h+var_110], rcx
0x1c0193103  xor     ebx, ebx
0x1c0193105  mov     [rsp+1D8h+var_148], ebx
0x1c019310c  xorps   xmm0, xmm0
0x1c019310f  xor     ecx, ecx
0x1c0193111  movups  xmmword ptr [r11-78h], xmm0
0x1c0193116  movups  xmmword ptr [r11-68h], xmm0
0x1c019311b  mov     [r11-58h], rcx
0x1c019311f  mov     r8, [r8+80h]
0x1c0193126  mov     [rsp+1D8h+var_118], r8
0x1c019312e  mov     [rsp+1D8h+var_F8], r8
0x1c0193136  mov     [r11-128h], rbx
0x1c019313d  mov     [rsp+1D8h+var_168], rbx
0x1c0193142  mov     r14d, ebx
0x1c0193145  mov     [r11-150h], rbx
0x1c019314c  mov     [rsp+1D8h+var_17E], bl
0x1c0193150  mov     [rsp+1D8h+var_158], ebx
0x1c0193157  mov     rdx, [r15+0A8h]
0x1c019315e  mov     cl, [rdx+13h]
0x1c0193161  mov     [rsp+1D8h+var_170], cl
0x1c0193165  mov     r12d, 100h
0x1c019316b  cmp     qword ptr [r9+8], 520h
0x1c0193173  jnz     loc_1C0193268
0x1c0193179  cmp     [r9], r12
0x1c019317c  jnz     loc_1C0193268
0x1c0193182  cmp     [rax], bx
0x1c0193185  jnz     short loc_1C0193202
0x1c0193187  test    dword ptr [r15+98h], 8000h
0x1c0193192  jnz     short loc_1C0193202
0x1c0193194  or      dword ptr [rsi+8], 300h
0x1c019319b  lea     rax, WPP_GLOBAL_Control
0x1c01931a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1c01931a9  cmp     rcx, rax
0x1c01931ac  jz      short loc_1C01931D3
0x1c01931ae  test    [rcx+2Ch], r12d
0x1c01931b2  jz      short loc_1C01931D3
0x1c01931b4  cmp     byte ptr [rcx+29h], 4
0x1c01931b8  jb      short loc_1C01931D3
0x1c01931ba  lea     edx, [rbx+63h]
0x1c01931bd  mov     r9d, 0C00000D8h
0x1c01931c3  lea     r8, WPP_cd49aa686cfe3d14e1a2820d5064b336_Traceguids
0x1c01931ca  mov     rcx, [rcx+18h]
0x1c01931ce  call    WPP_SF_D
0x1c01931d3  mov     al, cs:RefsStatusDebugEnabled
0x1c01931d9  test    al, al
0x1c01931db  jz      short loc_1C01931F4
0x1c01931dd  mov     r8d, 1D08h
0x1c01931e3  lea     rdx, aCreateC; "Create.c"
0x1c01931ea  mov     ecx, 0C00000D8h; Status
0x1c01931ef  call    RefsStatusDebug
0x1c01931f4  mov     edx, 0C00000D8h
0x1c01931f9  mov     rcx, rsi
0x1c01931fc  call    RefsRaiseStatusInternal
0x1c0193201  int     3; Trap to Debugger
0x1c0193202  lea     rax, WPP_GLOBAL_Control
0x1c0193209  mov     rcx, cs:WPP_GLOBAL_Control
0x1c0193210  cmp     rcx, rax
0x1c0193213  jz      short loc_1C019323C
0x1c0193215  test    [rcx+2Ch], r12d
0x1c0193219  jz      short loc_1C019323C
0x1c019321b  cmp     byte ptr [rcx+29h], 4
0x1c019321f  jb      short loc_1C019323C
0x1c0193221  mov     edx, 62h ; 'b'
0x1c0193226  mov     r9d, 0C000000Dh
0x1c019322c  lea     r8, WPP_cd49aa686cfe3d14e1a2820d5064b336_Traceguids
0x1c0193233  mov     rcx, [rcx+18h]
0x1c0193237  call    WPP_SF_D
0x1c019323c  mov     al, cs:RefsStatusDebugEnabled
0x1c0193242  test    al, al
0x1c0193244  jz      short loc_1C019325D
0x1c0193246  mov     r8d, 1D01h
0x1c019324c  lea     rdx, aCreateC; "Create.c"
0x1c0193253  mov     ecx, 0C000000Dh; Status
0x1c0193258  call    RefsStatusDebug
0x1c019325d  mov     eax, 0C000000Dh
0x1c0193262  jmp     loc_1C0194326
0x1c0193268  add     r9, 10h
0x1c019326c  mov     [rsp+1D8h+var_B8], r9
0x1c0193274  lea     rax, [rsp+1D8h+var_17E]
0x1c0193279  mov     [rsp+1D8h+var_198], rax
0x1c019327e  lea     rax, [rsp+1D8h+var_148]
0x1c0193286  mov     [rsp+1D8h+var_1A0], rax
0x1c019328b  mov     eax, [r15+98h]
0x1c0193292  mov     dword ptr [rsp+1D8h+var_1A8], eax
0x1c0193296  lea     rax, [rsp+1D8h+arg_30]
0x1c019329e  mov     [rsp+1D8h+var_1B0], rax
0x1c01932a3  lea     rax, [rsp+1D8h+var_100]
0x1c01932ab  mov     [rsp+1D8h+var_1B8], rax
0x1c01932b0  mov     rcx, rsi
0x1c01932b3  call    RefsCheckValidAttributeAccess
0x1c01932b8  mov     [rsp+1D8h+Status], eax
0x1c01932bc  test    eax, eax
0x1c01932be  js      loc_1C0194326
0x1c01932c4  lea     rax, [r13+40h]
0x1c01932c8  mov     [rsp+1D8h+var_B0], rax
0x1c01932d0  mov     ebx, [rax]
0x1c01932d2  movups  xmm6, xmmword ptr [r13+0]
0x1c01932d7  movaps  [rsp+1D8h+var_88], xmm6
0x1c01932df  mov     rax, [rsp+1D8h+var_118]
0x1c01932e7  add     rax, 218h
0x1c01932ed  mov     [rsp+1D8h+Mutex], rax
0x1c01932f5  mov     rcx, rax; Mutex
0x1c01932f8  call    cs:__imp_KeAcquireGuardedMutex
0x1c01932ff  nop     dword ptr [rax+rax+00h]
0x1c0193304  shr     ebx, 18h
0x1c0193307  and     bl, 10h
0x1c019330a  or      bl, 1
0x1c019330d  mov     [rsp+1D8h+var_188], bl
0x1c0193311  mov     rdx, [rsp+1D8h+var_118]
0x1c0193319  mov     rcx, rsi
0x1c019331c  test    bl, 0F0h
0x1c019331f  jz      short loc_1C0193351
0x1c0193321  movdqa  [rsp+1D8h+var_A8], xmm6
0x1c019332a  lea     rax, [rsp+1D8h+var_158]
0x1c0193332  mov     [rsp+1D8h+var_1A8], rax
0x1c0193337  xor     eax, eax
0x1c0193339  mov     [rsp+1D8h+var_1B0], rax
0x1c019333e  mov     [rsp+1D8h+var_1B8], rax
0x1c0193343  lea     r9d, [rax+2]
0x1c0193347  lea     r8, [rsp+1D8h+var_A8]
0x1c019334f  jmp     short loc_1C0193394
0x1c0193351  movdqa  [rsp+1D8h+var_98], xmm6
0x1c019335a  mov     rax, [r15+0A8h]
0x1c0193361  movzx   r9d, byte ptr [rax+2]
0x1c0193366  shr     r9d, 1
0x1c0193369  and     r9d, 1
0x1c019336d  lea     rax, [rsp+1D8h+var_158]
0x1c0193375  mov     [rsp+1D8h+var_1A8], rax
0x1c019337a  mov     rax, [rsp+1D8h+var_140]
0x1c0193382  mov     [rsp+1D8h+var_1B0], rax
0x1c0193387  mov     [rsp+1D8h+var_1B8], rdi
0x1c019338c  lea     r8, [rsp+1D8h+var_98]
0x1c0193394  call    RefsCreateFcb
0x1c0193399  mov     [rsp+1D8h+var_168], rax
0x1c019339e  mov     rdi, rax
0x1c01933a1  lea     rax, [rax+20h]
0x1c01933a5  mov     [rsp+1D8h+var_E0], rax
0x1c01933ad  inc     dword ptr [rax]
0x1c01933af  or      bl, 20h
0x1c01933b2  mov     [rsp+1D8h+var_188], bl
0x1c01933b6  mov     eax, [rsp+1D8h+var_158]
0x1c01933bd  and     eax, 1
0x1c01933c0  mov     [rsp+1D8h+var_144], eax
0x1c01933c7  jnz     short loc_1C01933D5
0x1c01933c9  mov     [rsp+1D8h+var_128], rdi
0x1c01933d1  xor     edx, edx
0x1c01933d3  jmp     short loc_1C01933E6
0x1c01933d5  mov     rax, [rsp+1D8h+var_110]
0x1c01933dd  xor     edx, edx
0x1c01933df  mov     [rax], rdx
0x1c01933e2  mov     [r15+68h], rdi
0x1c01933e6  mov     [rsp+1D8h+Status], edx
0x1c01933ea  lea     rax, [rdi+4]
0x1c01933ee  mov     [rsp+1D8h+var_178], rax
0x1c01933f3  mov     ecx, [rax]
0x1c01933f5  test    r12d, ecx
0x1c01933f8  jz      short loc_1C0193413
0x1c01933fa  mov     rax, [rsp+1D8h+var_160]
0x1c01933ff  mov     rax, [rax+78h]
0x1c0193403  cmp     qword ptr [rax+10h], 600h
0x1c019340b  jnz     short loc_1C0193413
0x1c019340d  cmp     [rax+8], rdx
0x1c0193411  jz      short loc_1C019341D
0x1c0193413  bt      ecx, 0Fh
0x1c0193417  jnb     loc_1C0193533
0x1c019341d  mov     rcx, [rsp+1D8h+Mutex]; Mutex
0x1c0193425  call    cs:__imp_KeReleaseGuardedMutex
0x1c019342c  nop     dword ptr [rax+rax+00h]
0x1c0193431  and     bl, 0FEh
0x1c0193434  mov     [rsp+1D8h+var_188], bl
0x1c0193438  mov     r9d, 1
0x1c019343e  xor     r8d, r8d
0x1c0193441  mov     rdx, rdi
0x1c0193444  mov     rcx, rsi
0x1c0193447  call    RefsAcquireFcbWithPaging
0x1c019344c  mov     rcx, [rsp+1D8h+Mutex]; Mutex
0x1c0193454  call    cs:__imp_KeAcquireGuardedMutex
0x1c019345b  nop     dword ptr [rax+rax+00h]
0x1c0193460  or      bl, 1
0x1c0193463  mov     [rsp+1D8h+var_188], bl
0x1c0193467  mov     rax, [rsp+1D8h+var_E0]
0x1c019346f  dec     dword ptr [rax]
0x1c0193471  and     bl, 0DFh
0x1c0193474  mov     [rsp+1D8h+var_188], bl
0x1c0193478  mov     rcx, [rsp+1D8h+Mutex]; Mutex
0x1c0193480  call    cs:__imp_KeReleaseGuardedMutex
0x1c0193487  nop     dword ptr [rax+rax+00h]
0x1c019348c  and     bl, 0FEh
0x1c019348f  mov     [rsp+1D8h+var_188], bl
0x1c0193493  bts     dword ptr [rsi+4], 1Dh
0x1c0193498  mov     al, bl
0x1c019349a  and     al, 4
0x1c019349c  mov     [rsp+1D8h+var_17F], al
0x1c01934a0  jnz     loc_1C0193700
0x1c01934a6  mov     rax, [rsp+1D8h+var_178]
0x1c01934ab  mov     eax, [rax]
0x1c01934ad  mov     rdx, [rsp+1D8h+var_160]
0x1c01934b2  mov     rcx, rsi
0x1c01934b5  test    al, 1
0x1c01934b7  jz      loc_1C019364D
0x1c01934bd  mov     r8, [rsp+1D8h+var_140]
0x1c01934c5  call    RefsQueueTriageForDeadLink
0x1c01934ca  mov     r9d, eax
0x1c01934cd  mov     [rsp+1D8h+Status], eax
0x1c01934d1  lea     rax, WPP_GLOBAL_Control
0x1c01934d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1c01934df  cmp     rcx, rax
0x1c01934e2  jz      short loc_1C0193507
0x1c01934e4  mov     eax, [rcx+2Ch]
0x1c01934e7  test    r12d, eax
0x1c01934ea  jz      short loc_1C0193507
0x1c01934ec  cmp     byte ptr [rcx+29h], 4
0x1c01934f0  jb      short loc_1C0193507
0x1c01934f2  mov     edx, 64h ; 'd'
0x1c01934f7  lea     r8, WPP_cd49aa686cfe3d14e1a2820d5064b336_Traceguids
0x1c01934fe  mov     rcx, [rcx+18h]
0x1c0193502  call    WPP_SF_D
0x1c0193507  mov     al, cs:RefsStatusDebugEnabled
0x1c019350d  test    al, al
0x1c019350f  jz      short loc_1C0193527
0x1c0193511  mov     r8d, 1DCFh
0x1c0193517  lea     rdx, aCreateC; "Create.c"
0x1c019351e  mov     ecx, [rsp+1D8h+Status]; Status
0x1c0193522  call    RefsStatusDebug
0x1c0193527  mov     edx, [rsp+1D8h+Status]
0x1c019352b  mov     rcx, rsi
0x1c019352e  call    RefsRaiseStatusInternal
0x1c0193533  mov     r9d, 3
0x1c0193539  xor     r8d, r8d
0x1c019353c  mov     rdx, rdi
0x1c019353f  mov     rcx, rsi
0x1c0193542  call    RefsAcquireFcbWithPaging
0x1c0193547  xor     ecx, ecx
0x1c0193549  test    al, al
0x1c019354b  jnz     loc_1C0193467
0x1c0193551  mov     r14, [rsp+1D8h+var_160]
0x1c0193556  mov     rax, [r14+78h]
0x1c019355a  inc     dword ptr [rax+20h]
0x1c019355d  lock inc dword ptr [r14+90h]
0x1c0193565  mov     rdi, [rsp+1D8h+var_168]
0x1c019356a  cmp     [rdi+68h], rcx
0x1c019356e  jz      short loc_1C0193575
0x1c0193570  bts     dword ptr [rsi+4], 10h
0x1c0193575  mov     r13, [rsp+1D8h+Mutex]
0x1c019357d  mov     rcx, r13; Mutex
0x1c0193580  call    cs:__imp_KeReleaseGuardedMutex
0x1c0193587  nop     dword ptr [rax+rax+00h]
0x1c019358c  and     bl, 0FEh
0x1c019358f  mov     [rsp+1D8h+var_188], bl
0x1c0193593  mov     rdx, r14
0x1c0193596  mov     rcx, rsi
0x1c0193599  call    RefsReleaseScbWithPaging
0x1c019359e  btr     dword ptr [r15+98h], 0Ah
0x1c01935a7  or      bl, 4
0x1c01935aa  mov     [rsp+1D8h+var_188], bl
0x1c01935ae  mov     r9d, 1
0x1c01935b4  xor     r8d, r8d
0x1c01935b7  mov     rdx, rdi
0x1c01935ba  mov     rcx, rsi
0x1c01935bd  call    RefsAcquireFcbWithPaging
0x1c01935c2  mov     r9d, 1
0x1c01935c8  mov     r8, r14
0x1c01935cb  mov     rdx, [r14+78h]
0x1c01935cf  mov     rcx, rsi
0x1c01935d2  call    RefsAcquireSharedFcb
0x1c01935d7  mov     rdx, [r14+78h]
0x1c01935db  mov     eax, [rdx+4]
0x1c01935de  test    al, 8
0x1c01935e0  jnz     short loc_1C01935FD
0x1c01935e2  mov     rcx, rsi
0x1c01935e5  call    RefsReleaseFcb
  ... truncated ...
```
