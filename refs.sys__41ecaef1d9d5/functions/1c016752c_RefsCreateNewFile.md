# RefsCreateNewFile

- ea: `0x1c016752c`
- end: `0x1c016895c`
- name: `RefsCreateNewFile`
- size: `5168`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, __int64, __int64, __int64, int, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `53`
- tags: `reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1c015eb64`

## callees

- `0x1c0002ce0`
- `0x1c0002ef8`
- `0x1c0003280`
- `0x1c0003610`
- `0x1c000384c`
- `0x1c0003be0`
- `0x1c0004300`
- `0x1c0004484`
- `0x1c0005818`
- `0x1c000f770`
- `0x1c000f980`
- `0x1c003a41c`
- `0x1c003a500`
- `0x1c003adcc`
- `0x1c003af28`
- `0x1c003b27c`
- `0x1c003b62c`
- `0x1c003b830`
- `0x1c0063db0`
- `0x1c00656a4`
- `0x1c0068168`
- `0x1c0068960`
- `0x1c006af80`
- `0x1c009f2c8`
- `0x1c014fc14`
- `0x1c014fc98`
- `0x1c014fe2c`
- `0x1c015043c`
- `0x1c0150f84`
- `0x1c0151cec`
- `0x1c0152188`
- `0x1c0152814`
- `0x1c0153508`
- `0x1c0156b80`
- `0x1c015ac58`
- `0x1c015c914`
- `0x1c015dfe8`
- `0x1c015e134`
- `0x1c01632d4`
- `0x1c0165b54`
- `0x1c0165b9c`
- `0x1c0165d18`
- `0x1c0166584`
- `0x1c0166c84`
- `0x1c016752c`
- `0x1c0168964`
- `0x1c0168afc`
- `0x1c0168b50`
- `0x1c016995c`
- `0x1c018cbe8`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutex` at `0x1c017fa17`
- `ntoskrnl!ExAcquireFastMutex` at `0x1c0186212`
- `ntoskrnl!ExAcquireFastMutex` at `0x1c017fa17`
- `ntoskrnl!ExAcquireFastMutex` at `0x1c0186212`
- `ntoskrnl!ExReleaseFastMutex` at `0x1c017fa4d`
- `ntoskrnl!ExReleaseFastMutex` at `0x1c018624b`
- `ntoskrnl!ExReleaseFastMutex` at `0x1c017fa4d`
- `ntoskrnl!ExReleaseFastMutex` at `0x1c018624b`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1c0167897`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1c017f94f`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1c017fab7`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1c018616f`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1c01862bd`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1c0167897`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1c017f94f`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1c017fab7`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1c018616f`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x1c01862bd`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1c016793b`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1c017f8fa`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1c017f96a`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1c017fad5`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1c018618b`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1c01862d7`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1c016793b`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1c017f8fa`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1c017f96a`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1c017fad5`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1c018618b`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x1c01862d7`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x1c0167e31`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x1c0167e31`
- `ntoskrnl!FsRtlIsNonEmptyDirectoryReparsePointAllowed` at `0x1c018605e`
- `ntoskrnl!FsRtlIsNonEmptyDirectoryReparsePointAllowed` at `0x1c018605e`

## string_xrefs

- `0x1c016813e`: `Create.c`
- `0x1c01681a4`: `Create.c`
- `0x1c01685af`: `Create.c`
- `0x1c01686be`: `Create.c`
- `0x1c0185fc4`: `Create.c`
- `0x1c018603d`: `Create.c`
- `0x1c01860ba`: `Create.c`
- `0x1c0186134`: `Create.c`

## pseudocode

```c
__int64 __fastcall RefsCreateNewFile(
        __int64 a1,
        IRP *a2,
        __int64 a3,
        __int64 a4,
        unsigned __int16 *a5,
        unsigned __int16 *a6,
        __int64 a7,
        int a8,
        __int64 *a9,
        __int64 a10,
        _QWORD *a11)
{
  __int64 v13; // rdx
  int v14; // r14d
  __int64 v15; // rbx
  __int64 result; // rax
  __int64 v17; // rcx
  __int64 v18; // r8
  _DWORD *v19; // rbx
  int v20; // ecx
  int v21; // edx
  int v22; // eax
  int v23; // r8d
  __int64 v24; // r9
  __int64 v25; // rax
  __int64 v26; // rbx
  __int64 Fcb; // rax
  __int64 v28; // r15
  _QWORD *v29; // rcx
  const UNICODE_STRING *v30; // r9
  int v31; // r8d
  __int64 Scb; // rax
  __int64 v33; // rbx
  int v34; // ecx
  int v35; // r14d
  __int16 StreamChecksumType; // ax
  int v37; // eax
  char v38; // r14
  int DataStream; // eax
  __int64 v40; // r9
  int v41; // r9d
  __int64 v42; // r15
  __int64 v43; // rcx
  __int64 v44; // rcx
  int v45; // r12d
  __int64 v46; // rdx
  __int64 v47; // r8
  __int64 v48; // rbx
  int v49; // r8d
  __int64 v50; // rcx
  int v51; // edx
  __int64 v52; // rbx
  int v53; // eax
  int v54; // ecx
  __int64 v55; // r14
  int v56; // eax
  __int64 *v57; // r12
  __int64 v58; // rbx
  CmsStream *v59; // rdx
  __int64 v60; // rcx
  __int64 v61; // rcx
  __int64 v62; // r12
  void (__stdcall *v63)(PVOID, PIRP); // r9
  char v64; // cl
  __int64 v65; // rdx
  __int64 v66; // rcx
  int v67; // r9d
  _QWORD *v68; // rbx
  __int64 v69; // rax
  _WORD *v70; // r8
  __int16 *v71; // rdx
  __int64 v72; // rax
  __int64 v73; // r8
  __int64 v74; // rax
  __int64 v75; // rax
  __int64 v76; // rdx
  __int64 v77; // r8
  int v78; // eax
  __int64 v79; // rdx
  __int64 v80; // rax
  __int64 v81; // rcx
  __int16 v82; // cx
  char v83; // al
  __int64 v84; // rdx
  __int64 v85; // r10
  int v86; // r8d
  int v87; // r11d
  __int16 v88; // ax
  int v89; // ecx
  int v90; // eax
  int v91; // eax
  unsigned __int16 v92; // ax
  __int64 v93; // r14
  __int64 v94; // rcx
  __int64 v95; // rax
  PVOID *v96; // rbx
  __int64 v97; // rbx
  _DWORD *v98; // rbx
  unsigned int v99; // eax
  __int64 v100; // rbx
  __int64 v101; // r8
  __int64 v102; // r9
  __int64 i; // rax
  int CompletionRoutine; // [rsp+20h] [rbp-2C8h]
  void (__stdcall *CompletionRoutinea)(PVOID, PIRP); // [rsp+20h] [rbp-2C8h]
  int CompletionRoutineb; // [rsp+20h] [rbp-2C8h]
  void (__stdcall *PostIrpRoutine)(PVOID, PIRP); // [rsp+28h] [rbp-2C0h]
  int PostIrpRoutinea; // [rsp+28h] [rbp-2C0h]
  int v109; // [rsp+30h] [rbp-2B8h]
  int v110; // [rsp+48h] [rbp-2A0h]
  char v111; // [rsp+80h] [rbp-268h] BYREF
  NTSTATUS Status[2]; // [rsp+81h] [rbp-267h] BYREF
  char v113; // [rsp+89h] [rbp-25Fh]
  char v114; // [rsp+8Ah] [rbp-25Eh]
  char v115; // [rsp+8Bh] [rbp-25Dh] BYREF
  char v116; // [rsp+8Ch] [rbp-25Ch]
  int v117; // [rsp+90h] [rbp-258h] BYREF
  __int64 v118; // [rsp+98h] [rbp-250h]
  char v119; // [rsp+A0h] [rbp-248h]
  int v120; // [rsp+A4h] [rbp-244h]
  int v121[2]; // [rsp+A8h] [rbp-240h]
  __int16 v122; // [rsp+B0h] [rbp-238h]
  int v123; // [rsp+B8h] [rbp-230h] BYREF
  __int64 v124; // [rsp+C0h] [rbp-228h]
  int v125[2]; // [rsp+C8h] [rbp-220h]
  PIRP Irp; // [rsp+D0h] [rbp-218h]
  __int64 v127; // [rsp+D8h] [rbp-210h] BYREF
  int v128; // [rsp+E0h] [rbp-208h]
  __int64 v129; // [rsp+E8h] [rbp-200h]
  __int64 v130; // [rsp+F0h] [rbp-1F8h] BYREF
  __int64 v131; // [rsp+F8h] [rbp-1F0h]
  __int64 v132; // [rsp+100h] [rbp-1E8h]
  PVOID P; // [rsp+108h] [rbp-1E0h] BYREF
  unsigned __int16 *v134; // [rsp+110h] [rbp-1D8h]
  __int64 v135; // [rsp+118h] [rbp-1D0h]
  __int64 v136; // [rsp+120h] [rbp-1C8h]
  __int64 v137; // [rsp+128h] [rbp-1C0h]
  unsigned __int16 *v138; // [rsp+130h] [rbp-1B8h]
  __int64 *v139; // [rsp+138h] [rbp-1B0h]
  __int64 v140; // [rsp+140h] [rbp-1A8h]
  __int64 v141; // [rsp+148h] [rbp-1A0h]
  _QWORD v142[5]; // [rsp+150h] [rbp-198h] BYREF
  _QWORD *v143; // [rsp+178h] [rbp-170h]
  __int128 v144; // [rsp+180h] [rbp-168h] BYREF
  _DWORD *v145; // [rsp+190h] [rbp-158h]
  __int128 v146; // [rsp+1A0h] [rbp-148h] BYREF
  __int128 v147; // [rsp+1B0h] [rbp-138h] BYREF
  __int128 v148; // [rsp+1C0h] [rbp-128h]
  _QWORD v149[26]; // [rsp+1D0h] [rbp-118h] BYREF

  v131 = a4;
  v132 = a3;
  Irp = a2;
  v140 = a1;
  v142[3] = a3;
  v138 = a5;
  v134 = a6;
  v130 = a7;
  v123 = a8;
  v139 = a9;
  v142[2] = a9;
  v136 = a10;
  v143 = a11;
  v142[4] = a11;
  v117 = 0;
  v144 = 0;
  *(_QWORD *)v121 = 0;
  v118 = 0;
  v127 = 0;
  v114 = 0;
  v116 = 0;
  v111 = 0;
  v113 = 0;
  HIBYTE(Status[1]) = 0;
  LOWORD(Status[0]) = 0;
  v115 = 0;
  v129 = 0;
  memset(v149, 0, sizeof(v149));
  P = 0;
  v13 = *(_QWORD *)(a10 + 168);
  v14 = *(unsigned __int16 *)(v13 + 24);
  v120 = v14;
  v15 = *(_QWORD *)(a3 + 128);
  *(_QWORD *)v125 = v15;
  v135 = v15;
  result = RefsCheckValidAttributeAccess(
             a1,
             v13,
             v15,
             0,
             (__int64)&v130,
             (__int64)&v123,
             *(_DWORD *)(a10 + 152),
             (__int64)&v117,
             (__int64)&v111);
  *(NTSTATUS *)((char *)Status + 3) = result;
  if ( (int)result < 0 )
    return result;
  if ( v111 )
  {
    if ( (v14 & 0x100) != 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 106, WPP_cd49aa686cfe3d14e1a2820d5064b336_Traceguids, 3221225485LL);
      }
      if ( !RefsStatusDebugEnabled )
        return 3221225485LL;
    }
    else
    {
      v95 = *(_QWORD *)(a10 + 200);
      if ( !v95 || (*(_BYTE *)(v95 + 2) & 0xD) == 0 )
        goto LABEL_3;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 107, WPP_cd49aa686cfe3d14e1a2820d5064b336_Traceguids, 3221225485LL);
      }
      if ( !RefsStatusDebugEnabled )
        return 3221225485LL;
    }
    RefsStatusDebug(-1073741811);
    return 3221225485LL;
  }
LABEL_3:
  if ( (v14 & 1) != 0 && (*(_DWORD *)(*(_QWORD *)(a10 + 168) + 16LL) & 0x1000) != 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 108, WPP_cd49aa686cfe3d14e1a2820d5064b336_Traceguids, 3221225761LL);
    }
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741535);
    return 3221225761LL;
  }
  v17 = *(_QWORD *)(a3 + 120);
  if ( (*(_DWORD *)(v17 + 160) & 0x10000400) == 0x10000400
    && !(unsigned __int8)FsRtlIsNonEmptyDirectoryReparsePointAllowed(*(unsigned int *)(v17 + 164)) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 109, WPP_cd49aa686cfe3d14e1a2820d5064b336_Traceguids, 3221226113LL);
    }
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741183);
    return 3221226113LL;
  }
  v18 = *(_QWORD *)(a3 + 120);
  if ( ((*(_DWORD *)(v18 + 4) & 0x100) == 0 || a3 == *(_QWORD *)(v15 + 32))
    && ((v123 - 128) & 0xFFFFFFCF) == 0
    && v123 != 144 )
  {
    v19 = *(_DWORD **)(*(_QWORD *)(*(_QWORD *)(a10 + 168) + 8LL) + 8LL);
    v145 = v19;
    v20 = v111 != 0 ? 4 : 2;
    v128 = v20;
    v21 = v19[4];
    if ( (v21 & 0x1000000) != 0 )
    {
      v20 |= 0x1000000u;
      v128 = v20;
    }
    if ( (v19[3] & 4) != 0 )
    {
      v19[5] |= v21 & 0xFEFFFFFF;
      v19[4] &= ~v19[5];
      v20 = 0;
      v128 = 0;
      v18 = *(_QWORD *)(a3 + 120);
    }
    RefsAccessCheck(a1, a10, v18, 0, (__int64)Irp, v20, 1, 1, 0);
    v19[5] |= v19[4];
    v22 = v19[5];
    if ( (v22 & 0x2000000) != 0 )
    {
      v78 = v22 | 0x1F01FF;
      v19[5] = v78;
      v19[5] = v78 & 0xFDFFFFFF;
    }
    v19[4] = 0;
    v127 = RefsCacheSharedSecurityForCreate(a1, *(_QWORD *)(a3 + 120));
    if ( v123 == 160 )
    {
      v24 = a3 + 360;
      if ( !*(_WORD *)(a3 + 360) )
        RefsBuildNormalizedNameImplementation(a1, *(_QWORD *)(a3 + 120), a3, v24);
    }
    v25 = *(_QWORD *)(a10 + 200);
    v26 = *(_QWORD *)v125;
    if ( v25 )
    {
      if ( (*(_BYTE *)(v25 + 2) & 2) != 0 )
      {
        v79 = *(_QWORD *)(*(_QWORD *)v125 + 48LL);
        if ( v79 )
        {
          RefsAcquireExclusiveScbWithFlags(a1, v79, 0);
          LOBYTE(Status[0]) = 1;
        }
      }
    }
    LOBYTE(v24) = 1;
    LOBYTE(v23) = 1;
    RefsEditFileBegin(a1, v26, v23, v24, (__int64)&v144, v111, a3, (__int64)a6, (__int64)&P);
    KeAcquireGuardedMutex((PKGUARDED_MUTEX)(v26 + 536));
    v114 = 1;
    if ( v111 )
    {
      v146 = v144;
      Fcb = RefsCreateFcb(a1, v125[0], (unsigned int)&v146, 2, 0, 0, 0);
    }
    else
    {
      v147 = v144;
      Fcb = RefsCreateFcb(
              a1,
              v125[0],
              (unsigned int)&v147,
              (*(unsigned __int8 *)(*(_QWORD *)(a10 + 168) + 2LL) >> 1) & 1,
              a3,
              (__int64)a6,
              0);
    }
    v118 = Fcb;
    v124 = Fcb;
    v28 = Fcb;
    *(_DWORD *)(a1 + 4) |= 0x10000u;
    RefsAcquireFcbWithPaging(a1, Fcb, 0, 3);
    KeReleaseGuardedMutex((PKGUARDED_MUTEX)(v26 + 536));
    v114 = 0;
    *(_QWORD *)v121 = RefsCreateLcb(a1, a3, v28, (_DWORD)v134, 0, 0);
    if ( v111 || (v29 = P, *(_QWORD *)(v28 + 240) = *((_QWORD *)P + 14), v29[14] = 0, v111) )
    {
      v30 = &RefsFileNameIndex;
      v31 = 160;
    }
    else
    {
      v142[0] = 0;
      v142[1] = 0;
      v30 = (const UNICODE_STRING *)v142;
      v31 = 128;
    }
    Scb = RefsCreateScb(a1, v28, v31, (_DWORD)v30, 0, (__int64)&Status[1] + 3);
    v137 = Scb;
    v33 = Scb;
    v34 = *(_DWORD *)(*(_QWORD *)(a3 + 120) + 160LL) & 0x28000;
    v35 = v34 | v14;
    v120 = v35;
    *(_DWORD *)(v28 + 160) |= v34;
    *(_WORD *)(Scb + 256) = *(_WORD *)(a3 + 256);
    StreamChecksumType = *(_WORD *)(a3 + 258);
    *(_WORD *)(v33 + 258) = StreamChecksumType;
    if ( (v35 & 0x8000) != 0 && !*(_WORD *)(a3 + 258) )
    {
      StreamChecksumType = RefsGetStreamChecksumType(*(_QWORD *)(*(_QWORD *)(a3 + 120) + 88LL));
      *(_WORD *)(v33 + 258) = StreamChecksumType;
    }
    if ( StreamChecksumType )
    {
      v120 = v35 | 0x8000;
      *(_DWORD *)(v28 + 160) |= 0x8000u;
    }
    v37 = RefsInitializeFileFromDisk(a1, v33, 0);
    *(NTSTATUS *)((char *)Status + 3) = v37;
    v38 = 0;
    if ( v37 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_D(
          WPP_GLOBAL_Control->AttachedDevice,
          111,
          WPP_cd49aa686cfe3d14e1a2820d5064b336_Traceguids,
          (unsigned int)v37);
      }
      if ( RefsStatusDebugEnabled )
        RefsStatusDebug(*(NTSTATUS *)((char *)Status + 3));
      RefsRaiseStatusInternal(a1, *(unsigned int *)((char *)Status + 3));
    }
    else
    {
      if ( v111 )
        goto LABEL_109;
      RefsBindMinstoreTransaction(a1);
      DataStream = RefsCreateDataStream(a1, v33, 1);
      v40 = (unsigned int)DataStream;
      *(NTSTATUS *)((char *)Status + 3) = DataStream;
      if ( DataStream >= 0 )
      {
        if ( !v111 && !*(_WORD *)v130 )
        {
          *(_QWORD *)(a10 + 112) = v33;
          goto LABEL_30;
        }
LABEL_109:
        v80 = RefsCreateScb(a1, v28, v123, v130, 0, (__int64)&Status[1] + 3);
        *(_QWORD *)(a10 + 112) = v80;
        *(_WORD *)(v80 + 256) = *(_WORD *)(v33 + 256);
        *(_WORD *)(*(_QWORD *)(a10 + 112) + 258LL) = *(_WORD *)(v33 + 258);
LABEL_30:
        v41 = 1;
        _InterlockedAdd((volatile signed __int32 *)(v28 + 28), 1u);
        v116 = 1;
        v42 = v118;
        if ( *(_QWORD *)(*(_QWORD *)(v118 + 88) + 64LL) )
        {
          v43 = v127;
          *(_QWORD *)(v118 + 196) = *(_QWORD *)(v127 + 8);
          *(_QWORD *)(v42 + 184) = v43;
          v127 = 0;
        }
        v44 = *(_QWORD *)(a3 + 120);
        if ( (*(_DWORD *)(v44 + 4) & 8) == 0 )
        {
          RefsUpdateFcbInfoFromDisk(a1, 0, *(_QWORD *)(a3 + 120), 0);
          v44 = *(_QWORD *)(a3 + 120);
          v41 = 1;
        }
        v120 &= ~0x2000u;
        v45 = *(_DWORD *)(v44 + 160) & 0x2000 | v120;
        v120 = v45;
        if ( !*(_BYTE *)(v132 + 252)
          || (v81 = *(_QWORD *)(a10 + 168), (*(_DWORD *)(v81 + 16) & 0x8000) != 0)
          || (*(_BYTE *)(v81 + 2) & 2) != 0 )
        {
          v119 = 0;
        }
        else
        {
          v38 = 1;
          v119 = 1;
        }
        v46 = *(_QWORD *)(a10 + 200);
        LODWORD(v47) = 0;
        if ( v46 )
        {
          v82 = *(_WORD *)(v46 + 2);
          v83 = v113;
          if ( (v82 & 1) != 0 )
            v83 = 1;
          v113 = v83;
          if ( (v82 & 0x10) != 0 )
            v129 = *(_QWORD *)(v46 + 32);
        }
        LOBYTE(v41) = v111;
        if ( v111 )
          v47 = *(_QWORD *)(a10 + 112);
        v48 = v129;
        RefsInitializeFcbAndStdInfo(a1, v42, v47, v41, CompletionRoutine, v38, v113, v45, v129);
        v50 = *(_QWORD *)(a10 + 200);
        if ( v50 && (*(_BYTE *)(v50 + 2) & 0x10) != 0 )
        {
          if ( *(_QWORD *)(v48 + 8) == -1 )
            v117 |= 0x40u;
          if ( *(_QWORD *)(v129 + 16) == -1 )
            v117 |= 0x10u;
          if ( *(_QWORD *)(v129 + 24) == -1 )
            v117 |= 0x20u;
          *(_WORD *)(v50 + 4) |= 0x10u;
        }
        if ( v111 )
        {
          if ( v38 )
            v88 = (unsigned __int8)*(_WORD *)(v132 + 252);
          else
            v88 = 0;
          RefsCreateIndex(a1, v42, v49, 0, (_DWORD)CompletionRoutinea, v88);
          v52 = v124;
        }
        else
        {
          v51 = v117;
          if ( (v117 & 2) != 0 )
          {
            v52 = v124;
            goto LABEL_43;
          }
          v84 = 0;
          v122 = 0;
          if ( (v45 & 0x200) != 0 )
          {
            v84 = 0x8000;
            v122 = 0x8000;
          }
          LODWORD(v85) = v137;
          v86 = *(_DWORD *)(v137 + 200);
          if ( v86 == 128
            && (v86 = 128, RefsMakeAllFilesSMRBlob)
            && (*(_DWORD *)(*(_QWORD *)(v137 + 120) + 4LL) & 0x100) == 0
            && (unsigned __int8)MsIsVolumeOnSmr(*(_QWORD *)(*(_QWORD *)(v137 + 128) + 104LL), v84, 128)
            && (v84 & 0x8000) == 0 )
          {
            LOWORD(v84) = v84 | 0x2000;
            v122 = v84;
            v120 = v45 | 0x20000000;
            v52 = v124;
            *(_DWORD *)(v124 + 160) |= 0x20000000u;
            *(_DWORD *)(v42 + 4) |= v87;
            *(_DWORD *)(v42 + 168) |= 4u;
            v86 = *(_DWORD *)(v85 + 200);
          }
          else
          {
            v52 = v124;
          }
          RefsAllocateAttribute(a1, v85, v86, v85 + 208, v84, (_DWORD)PostIrpRoutine, v109, 0);
          *(_DWORD *)(a10 + 180) |= 0x200000u;
        }
        v51 = v117;
LABEL_43:
        v53 = *(_DWORD *)(a10 + 152) & 0x40;
        if ( v123 == 160 )
        {
          if ( v53 )
          {
            v51 |= 8u;
            v89 = 0;
          }
          else
          {
            v89 = *v138 - *v134;
          }
          v57 = (__int64 *)(a10 + 112);
          LODWORD(PostIrpRoutine) = v89;
          v55 = *(_QWORD *)v121;
          v56 = RefsOpenAttribute(
                  a1,
                  *(_QWORD *)(a10 + 168),
                  *(__int64 *)v125,
                  *(__int64 *)v121,
                  v42,
                  PostIrpRoutine,
                  (__int64)&RefsFileNameIndex,
                  160,
                  2,
                  3u,
                  1,
                  v51,
                  0,
                  (__int64 *)(a10 + 112),
                  (_QWORD *)(a10 + 120));
        }
        else
        {
          if ( v53 )
            v54 = 0;
          else
            v54 = *v138 - *v134;
          LOBYTE(v110) = 0;
          LODWORD(CompletionRoutinea) = v54;
          v55 = *(_QWORD *)v121;
          v56 = RefsOpenNewAttr(a1, CompletionRoutinea, v130, v123, 1, v51, v110, a10);
          v57 = (__int64 *)(a10 + 112);
        }
        *(NTSTATUS *)((char *)Status + 3) = v56;
        if ( v56 < 0 )
        {
          v62 = v132;
LABEL_190:
          v93 = *(_QWORD *)v125;
          if ( LOBYTE(Status[0]) )
            RefsReleaseFcb(a1, *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v125 + 48LL) + 120LL));
          if ( P )
            RefsEditFileEnd(P);
          _InterlockedDecrement((volatile signed __int32 *)(v52 + 28));
          if ( v127 )
          {
            KeAcquireGuardedMutex((PKGUARDED_MUTEX)(v93 + 592));
            RemoveReferenceSharedSecurityUnsafe(&v127);
            KeReleaseGuardedMutex((PKGUARDED_MUTEX)(v93 + 592));
          }
          result = *(unsigned int *)((char *)Status + 3);
          if ( *(NTSTATUS *)((char *)Status + 3) < 0 )
          {
            v96 = (PVOID *)v139;
            if ( *v139 )
            {
              RefsCleanupIndexContext(a1, *v139);
              ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)&RefsIndexContextLookasideList, *v96);
              *v96 = 0;
            }
            if ( *(_QWORD *)(a10 + 112) && *(_QWORD *)(a10 + 120) )
              RefsBackoutFailedOpensPriv(a1, *(_QWORD *)(*(_QWORD *)(a10 + 168) + 48LL), v118);
            v97 = *(_QWORD *)v121;
            if ( *(_QWORD *)v121 )
            {
              ExAcquireFastMutex(*(PFAST_MUTEX *)(*(_QWORD *)(*(_QWORD *)v121 + 24LL) + 48LL));
              _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(v97 + 24) + 156LL));
              RefsRemovePrefixSafe(*(_QWORD *)v121);
              _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(v97 + 24) + 156LL));
              ExReleaseFastMutex(*(PFAST_MUTEX *)(*(_QWORD *)(v97 + 24) + 48LL));
              v98 = *(_DWORD **)v121;
              v99 = *(_DWORD *)(*(_QWORD *)v121 + 4LL);
              if ( (v99 & 0x20) != 0 )
              {
                RefsRemoveHashEntry(
                  *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v121 + 32LL) + 88LL) + 2696LL,
                  *(unsigned int *)(*(_QWORD *)v121 + 192LL),
                  *(_QWORD *)v121);
                v98[48] = 0;
                v99 = v98[1] & 0xFFFFFFDF;
              }
              v98[1] = v99 | 2;
              v98[47] = 0;
              v98[43] = 0;
            }
            v100 = v118;
            *(_DWORD *)(v118 + 4) &= ~8u;
            KeAcquireGuardedMutex((PKGUARDED_MUTEX)(*(_QWORD *)(a1 + 64) + 536LL));
            *(_DWORD *)(v100 + 4) |= 0x2000001u;
            KeReleaseGuardedMutex((PKGUARDED_MUTEX)(*(_QWORD *)(a1 + 64) + 536LL));
            *(_DWORD *)(a1 + 12) |= 0x20u;
            for ( i = 0; ; *(_DWORD *)(i + 200) = 0 )
            {
              i = RefsGetNextChildScb(v118, i, v101, v102);
              v141 = i;
              if ( !i )
                break;
              *(_QWORD *)(i + 24) = 0;
              *(_QWORD *)(i + 32) = 0;
              *(_QWORD *)(i + 40) = 0;
              *(_DWORD *)(i + 304) |= 0x40u;
            }
            *(_QWORD *)(a10 + 112) = 0;
            _InterlockedAdd((volatile signed __int32 *)(v62 + 144), 1u);
            RefsTeardownStructures(a1, v118, 0, (char *)Status + 1);
            if ( BYTE1(Status[0]) )
            {
              v118 = 0;
              *(_QWORD *)v121 = 0;
            }
            _InterlockedDecrement((volatile signed __int32 *)(v62 + 144));
            result = *(unsigned int *)((char *)Status + 3);
          }
          v94 = v118;
          if ( v118 )
          {
            if ( *(_QWORD *)v121 )
            {
              *v143 = *(_QWORD *)v121;
              *(_QWORD *)(a10 + 104) = v94;
            }
          }
          return result;
        }
        v58 = *v57;
        v141 = v58;
        if ( *(_WORD *)v58 == 2053 )
        {
          v59 = *(CmsStream **)(v58 + 360);
          if ( v59 )
            *(NTSTATUS *)((char *)Status + 3) = MsInitializeEmptyStream(
                                                  *(struct CmsTransactionContext **)(a1 + 24),
                                                  v59);
        }
        if ( !v111 )
        {
          if ( (*(_DWORD *)(v58 + 136) & 0x20) == 0 )
            RefsUpdateScbFromAttribute(a1, v58, 0);
          v60 = *(_QWORD *)(a10 + 168);
          if ( (*(_DWORD *)(v60 + 16) & 8) == 0 )
            *(_DWORD *)(*(_QWORD *)(v60 + 48) + 80LL) |= 0x40u;
          if ( (*(_DWORD *)(v58 + 136) & 0x10) != 0 )
          {
            v61 = *(_QWORD *)(v58 + 264);
            if ( *(_QWORD *)(v42 + 144) != v61 || *(_QWORD *)(v42 + 152) != *(_QWORD *)(v58 + 32) )
            {
              *(_QWORD *)(v42 + 144) = v61;
              *(_QWORD *)(v42 + 152) = *(_QWORD *)(v58 + 32);
              RefsUpdateStandardInformation(a1, v42);
              *(_DWORD *)(*(_QWORD *)(a10 + 120) + 4LL) |= 0x10000u;
            }
          }
        }
        v62 = v132;
        RefsAddLink(a1, v132, v42, v131, (__int64)&v115, PostIrpRoutinea, *v139);
        v63 = 0;
        if ( v111 )
        {
          v148 = 0;
          RefsBindMinstoreTransaction(a1);
          *((_QWORD *)&v148 + 1) = *(_QWORD *)(v131 + 8);
          v90 = MsSetDurableTableObjectParentId(
                  *(struct CmsTransactionContext **)(a1 + 24),
                  *(CmsBPlusTable **)(*(_QWORD *)(v42 + 248) + 384LL));
          *(NTSTATUS *)((char *)Status + 3) = v90;
          if ( v90 < 0 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              WPP_SF_D(
                WPP_GLOBAL_Control->AttachedDevice,
                113,
                WPP_cd49aa686cfe3d14e1a2820d5064b336_Traceguids,
                (unsigned int)v90);
            }
            if ( RefsStatusDebugEnabled )
              RefsStatusDebug(*(NTSTATUS *)((char *)Status + 3));
            RefsRaiseStatusInternal(a1, *(unsigned int *)((char *)Status + 3));
          }
          v63 = 0;
        }
        v64 = v115;
        *(_BYTE *)(*(_QWORD *)(v55 + 200) + 74LL) = v115;
        *(_BYTE *)(v131 + 74) = v64;
        if ( (*(_DWORD *)(v124 + 160) & 0x20000000) != 0 )
        {
          if ( (*(_DWORD *)(v124 + 168) & 4) != 0 )
            *(_DWORD *)(v42 + 168) = *(_DWORD *)(v124 + 168) & 4;
          else
            *(_DWORD *)(v124 + 168) = 0;
        }
        else
        {
          *(_DWORD *)(v124 + 168) = 0;
          *(_DWORD *)(v42 + 4) &= ~0x10u;
        }
        *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a10 + 168) + 48LL) + 80LL) &= 0xFFF7CFFF;
        *(_DWORD *)(*(_QWORD *)(a10 + 120) + 4LL) &= 0xFF8FFFFF;
        v65 = *(_QWORD *)(a10 + 200);
        v66 = v65;
        if ( v65 && (*(_BYTE *)(v65 + 2) & 2) != 0 )
        {
          v91 = RefsSetReparsePointInternal(
                  (_DWORD *)a1,
                  Irp,
                  v58,
                  *(_QWORD *)(a10 + 120),
                  *(_WORD *)(v65 + 6),
                  *(PREPARSE_DATA_BUFFER *)(v65 + 8),
                  Status);
          *(NTSTATUS *)((char *)Status + 3) = v91;
          v66 = *(_QWORD *)(a10 + 200);
          if ( v91 < 0 )
          {
            if ( (*(_WORD *)(v66 + 2) & 0x100) == 0 )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
              {
                WPP_SF_D(
                  WPP_GLOBAL_Control->AttachedDevice,
                  114,
                  WPP_cd49aa686cfe3d14e1a2820d5064b336_Traceguids,
                  (unsigned int)v91);
              }
              if ( RefsStatusDebugEnabled )
                RefsStatusDebug(*(NTSTATUS *)((char *)Status + 3));
              RefsRaiseStatusInternal(a1, *(unsigned int *)((char *)Status + 3));
              goto LABEL_170;
            }
          }
          else
          {
            *(_WORD *)(v66 + 4) |= 2u;
            *(_DWORD *)(a10 + 180) |= 0x100000u;
            v66 = *(_QWORD *)(a10 + 200);
          }
          v63 = 0;
        }
        if ( !v66 )
        {
LABEL_64:
          RefsUpdateFcb(*(_QWORD *)(v62 + 120), *(_QWORD *)(a10 + 120), 2684354576LL);
LABEL_65:
          if ( (*(_DWORD *)(v42 + 4) & 4) != 0 )
          {
            RefsPrepareForCriticalIo(a1, Irp, v58, 3);
            v63 = 0;
          }
          *(NTSTATUS *)((char *)Status + 3) = FsRtlCheckOplockEx((POPLOCK)(v62 + 88), Irp, 0x10u, 0, v63, v63);
          if ( *(NTSTATUS *)((char *)Status + 3) < 0 )
          {
            v52 = v124;
          }
          else
          {
            *(_QWORD *)(a10 + 104) = v42;
            v68 = (_QWORD *)(a10 + 112);
            RefsEncryptionCreateCallback(a1, (_DWORD)Irp, *(_QWORD *)(a10 + 112), v67, CompletionRoutineb, a10, 1);
            *(_QWORD *)(a10 + 104) = 0;
            *(_DWORD *)(a10 + 180) |= 0x100u;
            RefsPostUsnChangeWithOverrideOption(a1, *(_QWORD *)(a10 + 112), *(unsigned int *)(a10 + 180));
            v69 = *(_QWORD *)(a10 + 200);
            if ( v69 && *(int *)(a10 + 180) < 0 )
              *(_WORD *)(v69 + 4) |= 0x800u;
            v70 = (_WORD *)*v68;
            if ( *(_WORD *)*v68 == 2051 && !v70[180] && *(_WORD *)(v62 + 360) )
              RefsUpdateNormalizedName(a1, v62, (_DWORD)v70, v131, 0);
            if ( *(_QWORD *)(a1 + 176) )
            {
              RefsWriteUsnJournalChanges(a1);
              RefsCheckpointCurrentTransaction(a1);
            }
            v71 = *(__int16 **)(a10 + 200);
            if ( v71 )
            {
              if ( (v71[1] & 0x10) != 0 )
              {
                **((_QWORD **)v71 + 4) = *(_QWORD *)(v42 + 112);
                *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a10 + 200) + 32LL) + 8LL) = *(_QWORD *)(v42 + 136);
                *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a10 + 200) + 32LL) + 16LL) = *(_QWORD *)(v42 + 120);
                *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a10 + 200) + 32LL) + 24LL) = *(_QWORD *)(v42 + 128);
                *(_WORD *)(*(_QWORD *)(a10 + 200) + 4LL) |= 0x100u;
                v71 = *(__int16 **)(a10 + 200);
              }
              v92 = *v71;
              v52 = v124;
              if ( (unsigned __int16)*v71 >= 0x2Cu )
              {
                *((_DWORD *)v71 + 10) = *(_DWORD *)(v124 + 160);
                *(_WORD *)(*(_QWORD *)(a10 + 200) + 4LL) |= 0x200u;
                v71 = *(__int16 **)(a10 + 200);
                v92 = *v71;
              }
              if ( v92 >= 0x38u )
              {
                *((_QWORD *)v71 + 6) = *(_QWORD *)(v42 + 208);
                *(_WORD *)(*(_QWORD *)(a10 + 200) + 4LL) |= 0x1000u;
              }
            }
            else
            {
              v52 = v124;
            }
            if ( (*(_DWORD *)(a10 + 152) & 0x40) == 0 )
            {
              v72 = *(_QWORD *)(a10 + 200);
              if ( !v72 || (*(_WORD *)(v72 + 2) & 0x400) == 0 )
              {
                v73 = *(_QWORD *)(a10 + 120);
                v74 = *(_QWORD *)(v73 + 72);
                if ( !v74 || (v75 = *(_QWORD *)(v74 + 24), v76 = v75 + 360, !*(_QWORD *)(v75 + 368)) )
                  v76 = 0;
                RefsReportDirNotify(
                  (v111 != 0) + 1,
                  *(_QWORD *)(v42 + 88),
                  v73 + 16,
                  *(unsigned __int16 *)(v73 + 32),
                  0,
                  v76,
                  (v111 != 0) + 1,
                  1u,
                  *(_QWORD *)(v62 + 120));
              }
            }
            if ( (*(_DWORD *)(v52 + 160) & 0x20000000) != 0 && (*(_DWORD *)(v42 + 168) & 4) != 0 )
              *(_DWORD *)(v42 + 168) &= 4u;
            else
              *(_DWORD *)(v42 + 168) = 0;
            v77 = *(unsigned int *)(a10 + 92);
            if ( (_DWORD)v77 )
            {
              if ( (*(_BYTE *)(v55 + 4) & 0x20) != 0 )
              {
                RefsRemoveHashEntry(
                  *(_QWORD *)(*(_QWORD *)(v55 + 32) + 88LL) + 2696LL,
                  *(unsigned int *)(v55 + 192),
                  v55);
                *(_DWORD *)(v55 + 192) = 0;
                *(_DWORD *)(v55 + 4) &= ~0x20u;
                v77 = *(unsigned int *)(a10 + 92);
              }
              RefsInsertPrefixHashEntry(*(_QWORD *)v125 + 2696LL, v55, v77, *(unsigned int *)(a10 + 88));
            }
            RefsInsertPrefix(v55, *(unsigned int *)(a10 + 152));
            Irp->IoStatus.Information = 2;
          }
          goto LABEL_190;
        }
LABEL_170:
        if ( (*(_WORD *)(v66 + 2) & 0x200) != 0 )
          goto LABEL_65;
        goto LABEL_64;
      }
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 112, WPP_cd49aa686cfe3d14e1a2820d5064b336_Traceguids, v40);
    }
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(*(NTSTATUS *)((char *)Status + 3));
    RefsRaiseStatusInternal(a1, *(unsigned int *)((char *)Status + 3));
    goto LABEL_109;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 110, WPP_cd49aa686cfe3d14e1a2820d5064b336_Traceguids, 3221225506LL);
  }
  if ( RefsStatusDebugEnabled )
    RefsStatusDebug(-1073741790);
  return 3221225506LL;
}

```

## disassembly

```asm
0x1c016752c  mov     r11, rsp
0x1c016752f  push    rbx
0x1c0167530  push    rsi
0x1c0167531  push    rdi
0x1c0167532  push    r12
0x1c0167534  push    r13
0x1c0167536  push    r14
0x1c0167538  push    r15
0x1c016753a  sub     rsp, 2B0h
0x1c0167541  mov     rax, cs:__security_cookie
0x1c0167548  xor     rax, rsp
0x1c016754b  mov     [rsp+2E8h+var_48], rax
0x1c0167553  mov     [rsp+2E8h+var_1F0], r9
0x1c016755b  mov     r12, r8
0x1c016755e  mov     [rsp+2E8h+var_1E8], r8
0x1c0167566  mov     [rsp+2E8h+Irp], rdx
0x1c016756e  mov     rdi, rcx
0x1c0167571  mov     rsi, [rsp+2E8h+arg_48]
0x1c0167579  mov     [rsp+2E8h+var_1A8], rcx
0x1c0167581  mov     [rsp+2E8h+var_180], r8
0x1c0167589  mov     rax, [rsp+2E8h+arg_20]
0x1c0167591  mov     [rsp+2E8h+var_1B8], rax
0x1c0167599  mov     r15, [rsp+2E8h+arg_28]
0x1c01675a1  mov     [rsp+2E8h+var_1D8], r15
0x1c01675a9  mov     rax, [rsp+2E8h+arg_30]
0x1c01675b1  mov     [r11-1F8h], rax
0x1c01675b8  mov     eax, [rsp+2E8h+arg_38]
0x1c01675bf  mov     [rsp+2E8h+var_230], eax
0x1c01675c6  mov     rax, [rsp+2E8h+arg_40]
0x1c01675ce  mov     [rsp+2E8h+var_1B0], rax
0x1c01675d6  mov     [rsp+2E8h+var_188], rax
0x1c01675de  mov     [rsp+2E8h+var_1C8], rsi
0x1c01675e6  mov     rax, [rsp+2E8h+arg_50]
0x1c01675ee  mov     [rsp+2E8h+var_170], rax
0x1c01675f6  mov     [rsp+2E8h+var_178], rax
0x1c01675fe  xor     r13d, r13d
0x1c0167601  mov     [r11-258h], r13d
0x1c0167608  xorps   xmm0, xmm0
0x1c016760b  movups  [rsp+2E8h+var_168], xmm0
0x1c0167613  mov     [r11-240h], r13
0x1c016761a  mov     [r11-250h], r13
0x1c0167621  mov     [r11-210h], r13
0x1c0167628  mov     [r11-25Eh], r13b
0x1c016762f  mov     [r11-266h], r13b
0x1c0167636  mov     [r11-25Ch], r13b
0x1c016763d  mov     [r11-268h], r13b
0x1c0167644  mov     [r11-25Fh], r13b
0x1c016764b  mov     [r11-260h], r13b
0x1c0167652  mov     [r11-267h], r13b
0x1c0167659  mov     [r11-25Dh], r13b
0x1c0167660  mov     [r11-200h], r13
0x1c0167667  xor     edx, edx; Val
0x1c0167669  mov     r8d, 0D0h; Size
0x1c016766f  lea     rcx, [r11-118h]; void *
0x1c0167676  call    memset
0x1c016767b  mov     [rsp+2E8h+P], r13
0x1c0167683  mov     rdx, [rsi+0A8h]
0x1c016768a  movzx   r14d, word ptr [rdx+18h]
0x1c016768f  mov     [rsp+2E8h+var_244], r14d
0x1c0167697  mov     rbx, [r12+80h]
0x1c016769f  mov     qword ptr [rsp+2E8h+var_220], rbx
0x1c01676a7  mov     [rsp+2E8h+var_1D0], rbx
0x1c01676af  lea     rax, [rsp+2E8h+var_268]
0x1c01676b7  mov     [rsp+2E8h+var_2A8], rax
0x1c01676bc  lea     rax, [rsp+2E8h+var_258]
0x1c01676c4  mov     qword ptr [rsp+2E8h+var_2B0], rax
0x1c01676c9  mov     eax, [rsi+98h]
0x1c01676cf  mov     [rsp+2E8h+var_2B8], eax
0x1c01676d3  lea     rax, [rsp+2E8h+var_230]
0x1c01676db  mov     [rsp+2E8h+PostIrpRoutine], rax
0x1c01676e0  lea     rax, [rsp+2E8h+var_1F8]
0x1c01676e8  mov     [rsp+2E8h+CompletionRoutine], rax
0x1c01676ed  xor     r9d, r9d
0x1c01676f0  mov     r8, rbx
0x1c01676f3  mov     rcx, rdi
0x1c01676f6  call    RefsCheckValidAttributeAccess
0x1c01676fb  mov     [rsp+2E8h+Status+3], eax
0x1c0167702  test    eax, eax
0x1c0167704  js      loc_1C0168938
0x1c016770a  cmp     [rsp+2E8h+var_268], r13b
0x1c0167712  mov     r13d, 100h
0x1c0167718  jnz     loc_1C0185F08
0x1c016771e  xor     r9d, r9d
0x1c0167721  mov     r10d, 1
0x1c0167727  test    r10b, r14b
0x1c016772a  jnz     loc_1C0185FDF
0x1c0167730  mov     rcx, [r12+78h]
0x1c0167735  mov     eax, [rcx+0A0h]
0x1c016773b  mov     edx, 10000400h
0x1c0167740  and     eax, edx
0x1c0167742  cmp     eax, edx
0x1c0167744  jz      loc_1C0186058
0x1c016774a  mov     r8, [r12+78h]
0x1c016774f  test    [r8+4], r13d
0x1c0167753  jnz     loc_1C01860E0
0x1c0167759  mov     ecx, [rsp+2E8h+var_230]
0x1c0167760  lea     eax, [rcx-80h]
0x1c0167763  test    eax, 0FFFFFFCFh
0x1c0167768  jnz     loc_1C01860EA
0x1c016776e  cmp     ecx, 90h
0x1c0167774  jz      loc_1C01860EA
0x1c016777a  mov     rax, [rsi+0A8h]
0x1c0167781  mov     rcx, [rax+8]
0x1c0167785  mov     rbx, [rcx+8]
0x1c0167789  mov     [rsp+2E8h+var_158], rbx
0x1c0167791  mov     al, [rsp+2E8h+var_268]
0x1c0167798  neg     al
0x1c016779a  sbb     ecx, ecx
0x1c016779c  mov     eax, 2
0x1c01677a1  and     ecx, eax
0x1c01677a3  add     ecx, eax
0x1c01677a5  mov     [rsp+2E8h+var_208], ecx
0x1c01677ac  mov     edx, [rbx+10h]
0x1c01677af  mov     eax, 1000000h
0x1c01677b4  test    eax, edx
0x1c01677b6  jnz     loc_1C0167FD8
0x1c01677bc  mov     eax, [rbx+0Ch]
0x1c01677bf  test    al, 4
0x1c01677c1  jnz     loc_1C0167FE6
0x1c01677c7  mov     byte ptr [rsp+2E8h+var_2A8], r9b
0x1c01677cc  mov     byte ptr [rsp+2E8h+var_2B0], r10b
0x1c01677d1  mov     byte ptr [rsp+2E8h+var_2B8], r10b
0x1c01677d6  mov     dword ptr [rsp+2E8h+PostIrpRoutine], ecx
0x1c01677da  mov     rax, [rsp+2E8h+Irp]
0x1c01677e2  mov     [rsp+2E8h+CompletionRoutine], rax
0x1c01677e7  xor     r9d, r9d
0x1c01677ea  mov     rdx, rsi
0x1c01677ed  mov     rcx, rdi
0x1c01677f0  call    RefsAccessCheck
0x1c01677f5  mov     eax, [rbx+10h]
0x1c01677f8  or      [rbx+14h], eax
0x1c01677fb  mov     eax, [rbx+14h]
0x1c01677fe  bt      eax, 19h
0x1c0167802  jb      loc_1C0168009
0x1c0167808  xor     edx, edx
0x1c016780a  mov     [rbx+10h], edx
0x1c016780d  mov     rdx, [r12+78h]
0x1c0167812  mov     rcx, rdi
0x1c0167815  call    RefsCacheSharedSecurityForCreate
0x1c016781a  mov     [rsp+2E8h+var_210], rax
0x1c0167822  cmp     [rsp+2E8h+var_230], 0A0h
0x1c016782d  jz      loc_1C016801D
0x1c0167833  mov     rax, [rsi+0C8h]
0x1c016783a  mov     rbx, qword ptr [rsp+2E8h+var_220]
0x1c0167842  test    rax, rax
0x1c0167845  jnz     loc_1C0168046
0x1c016784b  lea     rax, [rsp+2E8h+P]
0x1c0167853  mov     [rsp+2E8h+var_2A8], rax
0x1c0167858  mov     qword ptr [rsp+2E8h+var_2B0], r15
0x1c016785d  mov     qword ptr [rsp+2E8h+var_2B8], r12
0x1c0167862  mov     al, [rsp+2E8h+var_268]
0x1c0167869  mov     byte ptr [rsp+2E8h+PostIrpRoutine], al
0x1c016786d  lea     rax, [rsp+2E8h+var_168]
0x1c0167875  mov     [rsp+2E8h+CompletionRoutine], rax
0x1c016787a  mov     eax, 1
0x1c016787f  mov     r9b, al
0x1c0167882  mov     r8b, al
0x1c0167885  mov     rdx, rbx
0x1c0167888  mov     rcx, rdi
0x1c016788b  call    RefsEditFileBegin
0x1c0167890  lea     rcx, [rbx+218h]; Mutex
0x1c0167897  call    cs:__imp_KeAcquireGuardedMutex
0x1c016789e  nop     dword ptr [rax+rax+00h]
0x1c01678a3  mov     edx, 1
0x1c01678a8  mov     [rsp+2E8h+var_25E], dl
0x1c01678af  xor     ecx, ecx
0x1c01678b1  movaps  xmm0, [rsp+2E8h+var_168]
0x1c01678b9  mov     qword ptr [rsp+2E8h+var_2B8], rcx
0x1c01678be  cmp     [rsp+2E8h+var_268], cl
0x1c01678c5  jnz     loc_1C016807A
0x1c01678cb  movdqa  [rsp+2E8h+var_138], xmm0
0x1c01678d4  mov     rax, [rsi+0A8h]
0x1c01678db  movzx   r9d, byte ptr [rax+2]
0x1c01678e0  shr     r9d, 1
0x1c01678e3  and     r9d, edx
0x1c01678e6  mov     [rsp+2E8h+PostIrpRoutine], r15
0x1c01678eb  mov     [rsp+2E8h+CompletionRoutine], r12
0x1c01678f0  lea     r8, [rsp+2E8h+var_138]
0x1c01678f8  mov     rdx, qword ptr [rsp+2E8h+var_220]
0x1c0167900  mov     rcx, rdi
0x1c0167903  call    RefsCreateFcb
0x1c0167908  mov     [rsp+2E8h+var_250], rax
0x1c0167910  mov     [rsp+2E8h+var_228], rax
0x1c0167918  mov     r15, rax
0x1c016791b  bts     dword ptr [rdi+4], 10h
0x1c0167920  mov     r9d, 3
0x1c0167926  xor     r8d, r8d
0x1c0167929  mov     rdx, rax
0x1c016792c  mov     rcx, rdi
0x1c016792f  call    RefsAcquireFcbWithPaging
0x1c0167934  lea     rcx, [rbx+218h]; Mutex
0x1c016793b  call    cs:__imp_KeReleaseGuardedMutex
0x1c0167942  nop     dword ptr [rax+rax+00h]
0x1c0167947  xor     ebx, ebx
0x1c0167949  mov     [rsp+2E8h+var_25E], bl
0x1c0167950  mov     [rsp+2E8h+PostIrpRoutine], rbx
0x1c0167955  mov     byte ptr [rsp+2E8h+CompletionRoutine], bl
0x1c0167959  mov     r9, [rsp+2E8h+var_1D8]
0x1c0167961  mov     r8, r15
0x1c0167964  mov     rdx, r12
0x1c0167967  mov     rcx, rdi
0x1c016796a  call    RefsCreateLcb
0x1c016796f  mov     qword ptr [rsp+2E8h+var_240], rax
0x1c0167977  mov     al, [rsp+2E8h+var_268]
0x1c016797e  test    al, al
0x1c0167980  jnz     loc_1C01680A0
0x1c0167986  mov     rcx, [rsp+2E8h+P]
0x1c016798e  mov     rax, [rcx+70h]
0x1c0167992  mov     [r15+0F0h], rax
0x1c0167999  mov     [rcx+70h], rbx
0x1c016799d  mov     al, [rsp+2E8h+var_268]
0x1c01679a4  test    al, al
0x1c01679a6  jnz     loc_1C01680A0
0x1c01679ac  mov     [rsp+2E8h+var_198], rbx
0x1c01679b4  mov     [rsp+2E8h+var_190], rbx
0x1c01679bc  lea     r9, [rsp+2E8h+var_198]
0x1c01679c4  mov     r8d, 80h
0x1c01679ca  lea     rax, [rsp+2E8h+Status+7]
0x1c01679d2  mov     [rsp+2E8h+PostIrpRoutine], rax
0x1c01679d7  mov     dword ptr [rsp+2E8h+CompletionRoutine], ebx
0x1c01679db  mov     rdx, r15
0x1c01679de  mov     rcx, rdi
0x1c01679e1  call    RefsCreateScb
0x1c01679e6  mov     [rsp+2E8h+var_1C0], rax
0x1c01679ee  mov     rbx, rax
0x1c01679f1  mov     rax, [r12+78h]
0x1c01679f6  mov     ecx, [rax+0A0h]
0x1c01679fc  and     ecx, 28000h
0x1c0167a02  or      r14d, ecx
0x1c0167a05  mov     [rsp+2E8h+var_244], r14d
0x1c0167a0d  or      [r15+0A0h], ecx
0x1c0167a14  movzx   eax, word ptr [r12+100h]
0x1c0167a1d  mov     [rbx+100h], ax
0x1c0167a24  movzx   eax, word ptr [r12+102h]
0x1c0167a2d  mov     [rbx+102h], ax
0x1c0167a34  mov     ecx, 8000h
0x1c0167a39  test    ecx, r14d
0x1c0167a3c  jnz     loc_1C01680B2
0x1c0167a42  test    ax, ax
0x1c0167a45  jnz     loc_1C01680E2
0x1c0167a4b  xor     r8d, r8d
0x1c0167a4e  mov     rdx, rbx
0x1c0167a51  mov     rcx, rdi
0x1c0167a54  call    RefsInitializeFileFromDisk
0x1c0167a59  mov     r9d, eax
0x1c0167a5c  mov     [rsp+2E8h+Status+3], eax
0x1c0167a63  xor     r14d, r14d
0x1c0167a66  test    eax, eax
0x1c0167a68  js      loc_1C01680F9
0x1c0167a6e  cmp     [rsp+2E8h+var_268], r14b
0x1c0167a76  jnz     loc_1C01681C6
0x1c0167a7c  mov     rcx, rdi
0x1c0167a7f  call    RefsBindMinstoreTransaction
0x1c0167a84  lea     r8d, [r14+1]
0x1c0167a88  mov     rdx, rbx
0x1c0167a8b  mov     rcx, rdi
0x1c0167a8e  call    RefsCreateDataStream
0x1c0167a93  mov     r9d, eax
0x1c0167a96  mov     [rsp+2E8h+Status+3], eax
0x1c0167a9d  test    eax, eax
0x1c0167a9f  js      loc_1C0168160
0x1c0167aa5  cmp     [rsp+2E8h+var_268], r14b
0x1c0167aad  jnz     loc_1C01681C6
0x1c0167ab3  mov     rax, [rsp+2E8h+var_1F8]
0x1c0167abb  cmp     [rax], r14w
0x1c0167abf  jnz     loc_1C01681C6
0x1c0167ac5  mov     [rsi+70h], rbx
0x1c0167ac9  mov     r9d, 1
0x1c0167acf  lock add [r15+1Ch], r9d
0x1c0167ad4  mov     [rsp+2E8h+var_25C], r9b
0x1c0167adc  mov     r15, [rsp+2E8h+var_250]
0x1c0167ae4  mov     rax, [r15+58h]
0x1c0167ae8  cmp     [rax+40h], r14
0x1c0167aec  jz      short loc_1C0167B10
0x1c0167aee  mov     rcx, [rsp+2E8h+var_210]
0x1c0167af6  mov     rax, [rcx+8]
0x1c0167afa  mov     [r15+0C4h], rax
0x1c0167b01  mov     [r15+0B8h], rcx
0x1c0167b08  mov     [rsp+2E8h+var_210], r14
0x1c0167b10  mov     rcx, [r12+78h]
0x1c0167b15  mov     eax, [rcx+4]
0x1c0167b18  test    al, 8
0x1c0167b1a  jz      loc_1C016821C
0x1c0167b20  mov     r12d, [rsp+2E8h+var_244]
0x1c0167b28  btr     r12d, 0Dh
0x1c0167b2d  mov     [rsp+2E8h+var_244], r12d
0x1c0167b35  mov     eax, [rcx+0A0h]
0x1c0167b3b  mov     ecx, 2000h
0x1c0167b40  and     eax, ecx
0x1c0167b42  or      r12d, eax
0x1c0167b45  mov     [rsp+2E8h+var_244], r12d
0x1c0167b4d  mov     rax, [rsp+2E8h+var_1E8]
0x1c0167b55  mov     al, [rax+0FCh]
0x1c0167b5b  test    al, al
0x1c0167b5d  jnz     loc_1C016823C
0x1c0167b63  mov     [rsp+2E8h+var_248], r14b
0x1c0167b6b  mov     rdx, [rsi+0C8h]
0x1c0167b72  xor     r8d, r8d
0x1c0167b75  test    rdx, rdx
0x1c0167b78  jnz     loc_1C016826A
  ... truncated ...
```
