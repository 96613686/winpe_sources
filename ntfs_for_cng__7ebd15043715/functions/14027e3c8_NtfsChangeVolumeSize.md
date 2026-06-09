# NtfsChangeVolumeSize

- ea: `0x14027e3c8`
- end: `0x140280cc3`
- name: `NtfsChangeVolumeSize`
- size: `10491`
- prototype: `__int64 __fastcall(__int64, IRP *, char)`
- caller_count: `1`
- callee_count: `60`
- tags: `file_ops, reparse_path, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1401f5890`

## callees

- `0x140007ea0`
- `0x1400082b0`
- `0x14000c290`
- `0x14000cb00`
- `0x14000d1e0`
- `0x14000d510`
- `0x140012e70`
- `0x14001c910`
- `0x14001e810`
- `0x140020de0`
- `0x140021590`
- `0x140021c30`
- `0x140021e60`
- `0x14002b680`
- `0x14002bc00`
- `0x140031410`
- `0x14003e734`
- `0x14004062c`
- `0x1400410a8`
- `0x140047c74`
- `0x140047fac`
- `0x140059250`
- `0x1400596c0`
- `0x1400c3090`
- `0x1400cc568`
- `0x1400d1da8`
- `0x1400f70d4`
- `0x1401250b0`
- `0x14012c1ec`
- `0x140137a5c`
- `0x14013c2d0`
- `0x14013cde0`
- `0x140140380`
- `0x14014dde0`
- `0x140150bc0`
- `0x140150c80`
- `0x14015ec38`
- `0x140160be0`
- `0x1401620c0`
- `0x140162370`
- `0x14016da60`
- `0x140174520`
- `0x140174afc`
- `0x14017517c`
- `0x1401aab20`
- `0x1401c00e0`
- `0x1401cb2c4`
- `0x1401d24d8`
- `0x1401d2c34`
- `0x1401d2cec`

## import_xrefs

- `ntoskrnl!IoGetActivityIdIrp` at `0x14027e4e5`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14027e4e5`
- `ntoskrnl!RtlSetBit` at `0x14027fb9c`
- `ntoskrnl!RtlSetBit` at `0x14027fbc5`
- `ntoskrnl!RtlSetBit` at `0x14027fb9c`
- `ntoskrnl!RtlSetBit` at `0x14027fbc5`
- `ntoskrnl!RtlSetBits` at `0x14027fd50`
- `ntoskrnl!RtlSetBits` at `0x14027fd50`
- `ntoskrnl!RtlNumberOfClearBitsInRange` at `0x14027fcd2`
- `ntoskrnl!RtlNumberOfClearBitsInRange` at `0x14027fcd2`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x140280044`
- `ntoskrnl!FsRtlNotifyVolumeEvent` at `0x140280044`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14027e4aa`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14027e9d3`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14027f062`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x140280087`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x1402bba14`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14027e4aa`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14027e9d3`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14027f062`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x140280087`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x1402bba14`
- `ntoskrnl!RtlClearBit` at `0x14027f9bb`
- `ntoskrnl!RtlClearBit` at `0x14027f9bb`
- `ntoskrnl!RtlNumberOfSetBitsInRange` at `0x14027fa19`
- `ntoskrnl!RtlNumberOfSetBitsInRange` at `0x14027fa19`
- `ntoskrnl!RtlExtractBitMap` at `0x14027fb4a`
- `ntoskrnl!RtlExtractBitMap` at `0x14027fb4a`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14028079d`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402bc1de`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402bc36a`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402bc3aa`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14028079d`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402bc1de`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402bc36a`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1402bc3aa`
- `ntoskrnl!IoGetActivityIdThread` at `0x14027e576`
- `ntoskrnl!IoGetActivityIdThread` at `0x14027e576`
- `ntoskrnl!KeWaitForSingleObject` at `0x14027e785`
- `ntoskrnl!KeWaitForSingleObject` at `0x14027e785`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x14027f1e8`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x14027f1e8`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14027f1d5`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14027f1d5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14027fb5f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402807b8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402807d3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402bc204`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402bc24e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14027fb5f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402807b8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402807d3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402bc204`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402bc24e`
- `ntoskrnl!RtlInitializeBitMap` at `0x14027fb1e`
- `ntoskrnl!RtlInitializeBitMap` at `0x14027fb1e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14027f832`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14027f913`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14027f832`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14027f913`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14027f0ec`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14027f0ec`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x14027f0d9`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x14027f0d9`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14027ebc3`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14027ebc3`
- `ntoskrnl!CcFlushCache` at `0x14027f25c`
- `ntoskrnl!CcFlushCache` at `0x14027f25c`

## pseudocode

```c
__int64 __fastcall NtfsChangeVolumeSize(__int64 a1, IRP *a2, char a3)
{
  unsigned int IsClearOrSet; // esi
  __int64 v7; // rcx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rcx
  unsigned int Options; // eax
  unsigned int v10; // r8d
  _QWORD *ActivityIdThread; // rax
  struct _IRP *MasterIrp; // rbx
  __int64 v13; // r15
  __int64 v14; // rdi
  unsigned int v15; // ebx
  unsigned int v16; // r8d
  __int64 v17; // r12
  __int64 v18; // rdx
  __int64 v19; // rbx
  unsigned int v20; // r8d
  __int64 v21; // rcx
  __int64 v22; // rcx
  struct _IO_STACK_LOCATION *v23; // rcx
  struct _IRP *v24; // r15
  __int64 v25; // rbx
  __int64 v26; // r15
  __int64 v27; // r9
  int v28; // eax
  __int64 v29; // rcx
  int v30; // edx
  signed __int64 v31; // r9
  signed __int64 v32; // r8
  __int64 v33; // rbx
  __int64 v34; // r15
  __int64 v35; // rax
  signed __int64 v36; // r15
  char v37; // cl
  __int64 v38; // r9
  _QWORD *v39; // r11
  __int64 v40; // r8
  __int64 v41; // rdx
  __int64 v42; // r9
  __int64 v43; // r9
  signed __int64 v44; // r8
  signed __int64 v45; // rcx
  signed __int64 v46; // rcx
  int v47; // edx
  signed __int64 v48; // r9
  signed __int64 v49; // r8
  __int64 v50; // r9
  __int64 v51; // r8
  __int64 v52; // rcx
  _QWORD *v53; // r15
  unsigned __int64 v54; // rax
  unsigned __int64 v55; // rcx
  __int64 v56; // rax
  SIZE_T v57; // rbx
  __int64 v58; // rax
  struct _RTL_BITMAP *v59; // r15
  unsigned int v60; // r13d
  ULONG v61; // ebx
  ULONG *v62; // r10
  ULONG v63; // r9d
  __int64 v64; // rdx
  __int64 v65; // r9
  __int64 v66; // rax
  unsigned __int64 v67; // rax
  unsigned __int64 v68; // r8
  ULONG v69; // r15d
  unsigned __int64 v70; // rax
  unsigned int v71; // ebx
  __int64 v72; // r9
  __int64 v73; // rdx
  __int64 v74; // rax
  __int64 v75; // rdx
  signed __int64 v76; // rcx
  __int64 v77; // rax
  int v78; // edx
  signed __int64 v79; // r9
  signed __int64 v80; // r8
  __int64 v81; // rax
  int v82; // edx
  signed __int64 v83; // rcx
  signed __int64 v84; // r8
  __int64 v85; // rcx
  unsigned __int64 v86; // rax
  __int64 v87; // r10
  char v88; // r12
  ULONGLONG v89; // rbx
  char v90; // al
  const wchar_t *v91; // r13
  unsigned __int64 v92; // r13
  CSHORT v93; // r15
  const wchar_t *v94; // r11
  const wchar_t *v95; // rcx
  int v96; // r12d
  int v97; // edx
  const wchar_t *v98; // rcx
  const WCHAR *v99; // rcx
  const WCHAR *v100; // rcx
  const wchar_t *v101; // rcx
  __int64 v102; // rax
  __int64 v103; // rbx
  int v104; // ebx
  __int128 v105; // rax
  unsigned __int64 v106; // r13
  CSHORT v107; // r15
  const wchar_t *v108; // r11
  const wchar_t *v109; // rcx
  int v110; // r12d
  int v111; // edx
  const wchar_t *v112; // rcx
  const WCHAR *v113; // rcx
  const WCHAR *v114; // rcx
  const wchar_t *v115; // rcx
  __int64 v116; // rax
  __int64 v117; // rbx
  int v118; // ebx
  __int128 v119; // rax
  PVOID v120; // rcx
  __int64 v121; // rcx
  unsigned __int16 v123; // cx
  int v124; // [rsp+120h] [rbp-2D0h]
  int v125[2]; // [rsp+120h] [rbp-2D0h]
  char v126; // [rsp+1D8h] [rbp-218h]
  char v127; // [rsp+1D9h] [rbp-217h] BYREF
  char v128; // [rsp+1DAh] [rbp-216h]
  char v129; // [rsp+1DBh] [rbp-215h]
  int v130; // [rsp+1DCh] [rbp-214h]
  char v131; // [rsp+1E0h] [rbp-210h]
  char v132; // [rsp+1E1h] [rbp-20Fh]
  char v133; // [rsp+1E2h] [rbp-20Eh]
  int v134; // [rsp+1E4h] [rbp-20Ch]
  __int16 v135; // [rsp+1ECh] [rbp-204h]
  struct _IRP *v136; // [rsp+1F0h] [rbp-200h]
  int Type; // [rsp+1F8h] [rbp-1F8h]
  int v138[2]; // [rsp+200h] [rbp-1F0h] BYREF
  unsigned __int64 v139; // [rsp+208h] [rbp-1E8h]
  const wchar_t *v140; // [rsp+210h] [rbp-1E0h]
  int v141[2]; // [rsp+218h] [rbp-1D8h] BYREF
  unsigned __int64 v142; // [rsp+220h] [rbp-1D0h] BYREF
  __int16 v143; // [rsp+228h] [rbp-1C8h]
  int v144[2]; // [rsp+230h] [rbp-1C0h]
  struct _RTL_BITMAP BitMapHeader; // [rsp+238h] [rbp-1B8h] BYREF
  __int64 v146; // [rsp+248h] [rbp-1A8h]
  const wchar_t *UnbiasedInterruptTime; // [rsp+250h] [rbp-1A0h]
  ULONG SizeOfBitMap[2]; // [rsp+258h] [rbp-198h]
  unsigned __int64 v149; // [rsp+260h] [rbp-190h]
  __int64 v150; // [rsp+268h] [rbp-188h]
  PULONG BitMapBuffer; // [rsp+270h] [rbp-180h]
  const wchar_t *v152; // [rsp+278h] [rbp-178h] BYREF
  __int64 v153; // [rsp+280h] [rbp-170h]
  struct _IO_STACK_LOCATION *v154; // [rsp+288h] [rbp-168h]
  __int64 v155; // [rsp+290h] [rbp-160h]
  struct _UNICODE_STRING UnicodeString; // [rsp+298h] [rbp-158h] BYREF
  __int64 v157; // [rsp+2A8h] [rbp-148h]
  PVOID P; // [rsp+2B0h] [rbp-140h]
  ULONG v159; // [rsp+2B8h] [rbp-138h]
  int v160; // [rsp+2BCh] [rbp-134h]
  __int64 v161; // [rsp+2C0h] [rbp-130h]
  __int64 v162; // [rsp+2C8h] [rbp-128h]
  __int64 v163; // [rsp+2D0h] [rbp-120h] BYREF
  __int64 v164; // [rsp+2D8h] [rbp-118h]
  __int64 v165; // [rsp+2E0h] [rbp-110h]
  struct _IO_STATUS_BLOCK IoStatus; // [rsp+2E8h] [rbp-108h] BYREF
  __int64 v167[11]; // [rsp+2F8h] [rbp-F8h] BYREF
  __int128 v168; // [rsp+358h] [rbp-98h] BYREF
  __int64 v169; // [rsp+368h] [rbp-88h]
  _OWORD v170[2]; // [rsp+370h] [rbp-80h] BYREF
  __int128 v171; // [rsp+390h] [rbp-60h] BYREF
  __int128 v172; // [rsp+3A0h] [rbp-50h]

  v162 = (__int64)a2;
  v140 = (const wchar_t *)a1;
  IsClearOrSet = 0;
  v130 = 0;
  *(_QWORD *)v141 = 0;
  v142 = 0;
  v153 = 0;
  v157 = 0;
  IoStatus = 0;
  memset(v167, 0, sizeof(v167));
  memset(v170, 0, 28);
  *(_QWORD *)v138 = 0;
  UnicodeString = 0;
  v127 = 0;
  v168 = 0;
  v169 = 0;
  v171 = 0;
  v172 = 0;
  UnbiasedInterruptTime = (const wchar_t *)KeQueryUnbiasedInterruptTime();
  *(_QWORD *)&v171 = UnbiasedInterruptTime;
  v135 = 1;
  if ( a2 )
  {
    if ( (int)IoGetActivityIdIrp(a2, (char *)&v168 + 8) < 0 )
    {
LABEL_3:
      *(_QWORD *)&v168 = 0;
      goto LABEL_4;
    }
  }
  else
  {
    ActivityIdThread = (_QWORD *)IoGetActivityIdThread(v7);
    if ( !ActivityIdThread )
      goto LABEL_3;
    *((_QWORD *)&v168 + 1) = *ActivityIdThread;
    v169 = ActivityIdThread[1];
  }
  *(_QWORD *)&v168 = (char *)&v168 + 8;
LABEL_4:
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v154 = CurrentStackLocation;
  Options = CurrentStackLocation->Parameters.Create.Options;
  if ( a3 )
  {
    if ( Options < 0x18 )
    {
      IsClearOrSet = -1073741811;
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(a1, 0xC000000D, 0x125B3Fu);
      NtfsExtendedCompleteRequestInternal(a1, a2, -1073741811, a2 != 0, 0);
      if ( !NtfsStatusDebugFlags )
        return IsClearOrSet;
      v10 = 1203008;
LABEL_373:
      NtfsStatusTraceAndDebugInternal(0, 0xC000000D, v10);
      return IsClearOrSet;
    }
    MasterIrp = a2->AssociatedIrp.MasterIrp;
    v13 = *(_QWORD *)&MasterIrp->Flags;
    Type = (unsigned __int16)MasterIrp->Type;
    v143 = Type;
  }
  else
  {
    if ( Options < 8 )
    {
      IsClearOrSet = -1073741811;
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(a1, 0xC000000D, 0x125B4Cu);
      NtfsExtendedCompleteRequestInternal(a1, a2, -1073741811, a2 != 0, 0);
      if ( !NtfsStatusDebugFlags )
        return IsClearOrSet;
      v10 = 1203021;
      goto LABEL_373;
    }
    MasterIrp = 0;
    Type = 0;
    v143 = 0;
    v13 = *(_QWORD *)a2->AssociatedIrp.MasterIrp;
  }
  *(_QWORD *)&BitMapHeader.SizeOfBitMap = v13;
  v139 = (unsigned __int64)MasterIrp;
  v136 = MasterIrp;
  if ( (unsigned int)NtfsDecodeFileObject(a1, (__int64)CurrentStackLocation->FileObject, v141, &v163, &v152, &v142, 1) != 4 )
  {
    IsClearOrSet = -1073741811;
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(a1, 0xC000000D, 0x125B61u);
    NtfsExtendedCompleteRequestInternal(a1, a2, -1073741811, a2 != 0, 0);
    if ( !NtfsStatusDebugFlags )
      return IsClearOrSet;
    v10 = 1203042;
    goto LABEL_373;
  }
  if ( !v142 || !_bittest16((const signed __int16 *)(v142 + 104), 9u) )
  {
    if ( (!a1 || (*(_DWORD *)(a1 + 16) & 0x100000) == 0)
      && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x20) != 0 )
    {
      v123 = *(_WORD *)(*(_QWORD *)(*(_QWORD *)v141 + 248LL) + 6LL);
      if ( v123 > 0x40u || (v123 & 1) != 0 )
        v123 = 0;
      McTemplateU0ppwwd_EtwWriteTransfer(v123 >> 1, (const EVENT_DESCRIPTOR *)fsctrl_c23405, KeGetCurrentThread());
    }
    v15 = -1073741790;
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(a1, 0xC0000022, 0x125B78u);
    NtfsExtendedCompleteRequestInternal(a1, a2, -1073741790, a2 != 0, 0);
    if ( !NtfsStatusDebugFlags )
      return v15;
    v16 = 1203065;
    goto LABEL_386;
  }
  v14 = *(_QWORD *)v141;
  if ( (*(_DWORD *)(*(_QWORD *)v141 + 4LL) & 0x2000000) == 0 )
  {
    KeWaitForSingleObject((PVOID)(*(_QWORD *)v141 + 6632LL), Executive, 0, 0, 0);
    if ( !a3 )
      goto LABEL_45;
    if ( MasterIrp->MdlAddress )
    {
      IsClearOrSet = -1073741811;
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(a1, 0xC000000D, 0x125B9Au);
      NtfsExtendedCompleteRequestInternal(a1, a2, -1073741811, a2 != 0, 0);
      if ( !NtfsStatusDebugFlags )
        return IsClearOrSet;
      v10 = 1203099;
      goto LABEL_373;
    }
    if ( *(_DWORD *)&MasterIrp->Type == 1 )
    {
LABEL_45:
      if ( v13 <= 0 )
      {
        IsClearOrSet = -1073741811;
        if ( NtfsStatusDebugFlags )
          NtfsStatusTraceAndDebugInternal(a1, 0xC000000D, 0x125BACu);
        NtfsExtendedCompleteRequestInternal(a1, a2, -1073741811, a2 != 0, 0);
        if ( !NtfsStatusDebugFlags )
          return IsClearOrSet;
        v10 = 1203117;
        goto LABEL_373;
      }
      v18 = (v13 - 1) * *(unsigned int *)(v14 + 364);
      v153 = v18;
      v157 = v18;
      if ( v18 < v13 || (v17 = v18 >> *(_BYTE *)(v14 + 488), v17 > 4294967294LL) )
      {
        IsClearOrSet = -1073741811;
        if ( NtfsStatusDebugFlags )
          NtfsStatusTraceAndDebugInternal(a1, 0xC000000D, 0x125BBEu);
        NtfsExtendedCompleteRequestInternal(a1, a2, -1073741811, a2 != 0, 0);
        if ( !NtfsStatusDebugFlags )
          return IsClearOrSet;
        v10 = 1203135;
        goto LABEL_373;
      }
    }
    else
    {
      if ( v13 )
      {
        IsClearOrSet = -1073741811;
        if ( NtfsStatusDebugFlags )
          NtfsStatusTraceAndDebugInternal(a1, 0xC000000D, 0x125BC6u);
        NtfsExtendedCompleteRequestInternal(a1, a2, -1073741811, a2 != 0, 0);
        if ( !NtfsStatusDebugFlags )
          return IsClearOrSet;
        v10 = 1203143;
        goto LABEL_373;
      }
      v17 = 0;
    }
    v161 = 0;
    v150 = 0;
    v155 = 0;
    P = 0;
    v131 = 0;
    v129 = 0;
    v133 = 0;
    v126 = 0;
    v132 = 0;
    BitMapBuffer = 0;
    *(_QWORD *)SizeOfBitMap = 0;
    *(_DWORD *)(a1 + 12) |= 1u;
    memset(v167, 0, sizeof(v167));
    if ( (*(_DWORD *)(a1 + 12) & 0x100) != 0 )
      NtfsAcquireExclusiveVcb(a1, v14, 1);
    else
      NtfsAcquireSharedVcb(a1, v14, 1);
    v128 = 1;
    v19 = *(_QWORD *)(v14 + 88);
    v146 = v19;
    v152 = (const wchar_t *)v19;
    v149 = *(_QWORD *)(v14 + 424);
    v142 = v149;
    v163 = *(_QWORD *)(v14 + 432);
    *((_QWORD *)&v171 + 1) = KeQueryUnbiasedInterruptTime();
    v134 = 2;
    v135 = 2;
    if ( (*(_DWORD *)(v14 + 4) & 1) == 0 )
    {
      IsClearOrSet = -1073741202;
      if ( NtfsStatusDebugFlags )
      {
        v20 = 1203192;
LABEL_258:
        NtfsStatusTraceAndDebugInternal(0, IsClearOrSet, v20);
        goto LABEL_259;
      }
      goto LABEL_259;
    }
    if ( a3 )
    {
      NtfsAcquireExclusiveFcb(a1, *(_QWORD *)(*(_QWORD *)(v14 + 72) + 184LL), 0, 9);
      if ( *(_DWORD *)&v136->Type == 1 )
      {
        v23 = v154;
        if ( *(_QWORD *)(v14 + 5368) == 0x7FFFFFFFFFFFFFFFLL || v154->FileObject == *(PFILE_OBJECT *)(v14 + 1480) )
        {
          if ( *(_QWORD *)(v14 + 296) > v17 )
          {
            *(_QWORD *)(v14 + 5368) = v17;
            *(_QWORD *)(v14 + 5376) = v13;
            *(_QWORD *)(v14 + 1480) = v23->FileObject;
            NtfsRemoveCachedRun(a1, v14, *(_QWORD *)(v14 + 5368), *(_QWORD *)(v14 + 296) - *(_QWORD *)(v14 + 5368));
            v24 = v136;
            if ( *(_QWORD *)(v14 + 4960) >= *(_QWORD *)(v14 + 5368) )
              *(_QWORD *)(v14 + 4960) = 0;
            goto LABEL_261;
          }
          IsClearOrSet = -1073741811;
          if ( !NtfsStatusDebugFlags )
            goto LABEL_259;
          v20 = 1203264;
          goto LABEL_258;
        }
        IsClearOrSet = -2147483631;
        if ( NtfsStatusDebugFlags )
        {
          v20 = 1203243;
          goto LABEL_258;
        }
        goto LABEL_259;
      }
      if ( *(_DWORD *)&v136->Type != 2 )
      {
        if ( *(_DWORD *)&v136->Type != 3 )
        {
          IsClearOrSet = -1073741811;
          if ( NtfsStatusDebugFlags )
          {
            v20 = 1203411;
            goto LABEL_258;
          }
LABEL_259:
          v130 = IsClearOrSet;
          goto LABEL_260;
        }
        if ( v154->FileObject != *(PFILE_OBJECT *)(v14 + 1480) )
        {
          IsClearOrSet = -1073741811;
          if ( NtfsStatusDebugFlags )
          {
            v20 = 1203372;
            goto LABEL_258;
          }
          goto LABEL_259;
        }
        *(_QWORD *)(v14 + 5368) = 0x7FFFFFFFFFFFFFFFLL;
        *(_QWORD *)(v14 + 5376) = 0;
        *(_QWORD *)(v14 + 1480) = 0;
        NtfsScanEntireBitmap(a1, v14, 10, 5);
LABEL_260:
        v24 = v136;
LABEL_261:
        v88 = a3;
LABEL_262:
        v89 = KeQueryUnbiasedInterruptTime();
        *((_QWORD *)&v172 + 1) = v89;
        NtfsTelemetryFillVcbVolumeState(v14);
        v90 = NtfsTelemetryGuard(0x800u);
        v91 = UnbiasedInterruptTime;
        if ( v90 )
          NtfsTelemetryVolumeSizeChange(
            (__int128 **)&v168,
            v14,
            IsClearOrSet,
            Type,
            v89 - (_QWORD)UnbiasedInterruptTime,
            v124,
            (__int64)&v171);
        NtfsRepairGetVolumeId(a1, v14, 1, (__int64)&UnicodeString, &v127);
        if ( (IsClearOrSet & 0x80000000) != 0 )
        {
          if ( (Microsoft_Windows_NtfsEnableBits & 0x10000) != 0 )
          {
            if ( *((_QWORD *)&v172 + 1) && (_QWORD)v172 )
              v142 = (unsigned __int64)(1000 * (*((_QWORD *)&v172 + 1) - v172)) / NtfsPerformanceFrequency.QuadPart;
            else
              v142 = 0;
            if ( (_QWORD)v172 && *((_QWORD *)&v171 + 1) )
              v139 = (unsigned __int64)(1000 * (v172 - *((_QWORD *)&v171 + 1))) / NtfsPerformanceFrequency.QuadPart;
            else
              v139 = 0;
            if ( *((_QWORD *)&v171 + 1) && (_QWORD)v171 )
              *(_QWORD *)&BitMapHeader.SizeOfBitMap = (unsigned __int64)(1000 * (*((_QWORD *)&v171 + 1) - v171))
                                                    / NtfsPerformanceFrequency.QuadPart;
            else
              *(_QWORD *)&BitMapHeader.SizeOfBitMap = 0;
            if ( v89 && v91 )
              v106 = 1000 * (v89 - (unsigned __int64)v91) / NtfsPerformanceFrequency.QuadPart;
            else
              LOBYTE(v106) = 0;
            if ( v88 )
              v107 = v24->Type;
            else
              LOBYTE(v107) = 0;
            v108 = &word_140064400;
            v109 = &word_140064400;
            if ( *(_QWORD *)(v14 + 6736) )
              v109 = *(const wchar_t **)(v14 + 6736);
            v152 = v109;
            v110 = (*(_DWORD *)(v14 + 28) >> 2) & 1;
            v111 = *(_DWORD *)(v14 + 6660);
            if ( (unsigned int)(v111 - 1) > 0x13 )
              v111 = 0;
            v144[0] = v111;
            v112 = &word_140064400;
            if ( *(_QWORD *)(v14 + 6720) )
              v112 = *(const wchar_t **)(v14 + 6720);
            v140 = v112;
            v113 = &word_140064400;
            if ( *(_QWORD *)(v14 + 6704) )
              v113 = *(const WCHAR **)(v14 + 6704);
            *(_QWORD *)v138 = v113;
            v114 = &word_140064400;
            if ( *(_QWORD *)(v14 + 6688) )
              v114 = *(const WCHAR **)(v14 + 6688);
            *(_QWORD *)v141 = v114;
            v115 = &word_140064400;
            if ( *(_QWORD *)(v14 + 6672) )
              v115 = *(const wchar_t **)(v14 + 6672);
            UnbiasedInterruptTime = v115;
            if ( *(_QWORD *)(v14 + 7864) )
              v108 = *(const wchar_t **)(v14 + 7864);
            if ( (*(_DWORD *)(v14 + 4) & 0xC00) != 0x800
              && (v116 = *(_QWORD *)(v14 + 248)) != 0
              && (v117 = *(_QWORD *)(v116 + 16)) != 0 )
            {
              v118 = (*(_DWORD *)(v117 + 48) >> 8) & 1;
            }
            else
            {
              LOBYTE(v118) = 0;
            }
            v119 = (__int64)(v149 * *(unsigned int *)(v14 + 364));
            McTemplateK0jmztzzzzzqjqtzxxhhxxxxhqd_EtwWriteTransfer(
              v14 + 7808,
              v14 + 8528,
              v153 / 0x100000,
              v14 + 7824,
              v14 + 8528,
              UnicodeString.Buffer,
              v118,
              v108,
              UnbiasedInterruptTime,
              *(const wchar_t **)v141,
              *(const wchar_t **)v138,
              v140,
              v144[0],
              v14 + 7808,
              *(_DWORD *)(v14 + 6792),
              v110,
              v152,
              ((*((_QWORD *)&v119 + 1) & 0xFFFFFLL) + (__int64)v119) >> 20,
              v153 / 0x100000,
              a3 != 0,
              v107,
              v106,
              BitMapHeader.SizeOfBitMap,
              v139,
              v142,
              v134,
              IsClearOrSet,
              IsClearOrSet);
          }
        }
        else if ( (Microsoft_Windows_NtfsEnableBits & 0x800) != 0 )
        {
          if ( *((_QWORD *)&v172 + 1) && (_QWORD)v172 )
            v142 = (unsigned __int64)(1000 * (*((_QWORD *)&v172 + 1) - v172)) / NtfsPerformanceFrequency.QuadPart;
          else
            v142 = 0;
          if ( (_QWORD)v172 && *((_QWORD *)&v171 + 1) )
            v139 = (unsigned __int64)(1000 * (v172 - *((_QWORD *)&v171 + 1))) / NtfsPerformanceFrequency.QuadPart;
          else
            v139 = 0;
          if ( *((_QWORD *)&v171 + 1) && (_QWORD)v171 )
            *(_QWORD *)&BitMapHeader.SizeOfBitMap = (unsigned __int64)(1000 * (*((_QWORD *)&v171 + 1) - v171))
                                                  / NtfsPerformanceFrequency.QuadPart;
          else
            *(_QWORD *)&BitMapHeader.SizeOfBitMap = 0;
          if ( v89 && v91 )
            v92 = 1000 * (v89 - (unsigned __int64)v91) / NtfsPerformanceFrequency.QuadPart;
          else
            LOBYTE(v92) = 0;
          if ( v88 )
            v93 = v24->Type;
          else
            LOBYTE(v93) = 0;
          v94 = &word_140064400;
          v95 = &word_140064400;
          if ( *(_QWORD *)(v14 + 6736) )
            v95 = *(const wchar_t **)(v14 + 6736);
          v152 = v95;
          v96 = (*(_DWORD *)(v14 + 28) >> 2) & 1;
          v97 = *(_DWORD *)(v14 + 6660);
          if ( (unsigned int)(v97 - 1) > 0x13 )
            v97 = 0;
          v144[0] = v97;
          v98 = &word_140064400;
          if ( *(_QWORD *)(v14 + 6720) )
            v98 = *(const wchar_t **)(v14 + 6720);
          v140 = v98;
          v99 = &word_140064400;
          if ( *(_QWORD *)(v14 + 6704) )
            v99 = *(const WCHAR **)(v14 + 6704);
          *(_QWORD *)v138 = v99;
          v100 = &word_140064400;
          if ( *(_QWORD *)(v14 + 6688) )
            v100 = *(const WCHAR **)(v14 + 6688);
          *(_QWORD *)v141 = v100;
          v101 = &word_140064400;
          if ( *(_QWORD *)(v14 + 6672) )
            v101 = *(const wchar_t **)(v14 + 6672);
          UnbiasedInterruptTime = v101;
          if ( *(_QWORD *)(v14 + 7864) )
            v94 = *(const wchar_t **)(v14 + 7864);
          if ( (*(_DWORD *)(v14 + 4) & 0xC00) != 0x800
            && (v102 = *(_QWORD *)(v14 + 248)) != 0
            && (v103 = *(_QWORD *)(v102 + 16)) != 0 )
          {
            v104 = (*(_DWORD *)(v103 + 48) >> 8) & 1;
          }
          else
          {
            LOBYTE(v104) = 0;
          }
          v105 = (__int64)(v149 * *(unsigned int *)(v14 + 364));
          McTemplateK0jmztzzzzzqjqtzxxhhxxxx_EtwWriteTransfer(
            v14 + 7808,
            v14 + 8528,
            v153 / 0x100000,
            v14 + 7824,
            v14 + 8528,
            UnicodeString.Buffer,
            v104,
            v94,
            UnbiasedInterruptTime,
            *(const wchar_t **)v141,
            *(const wchar_t **)v138,
            v140,
            v144[0],
            v14 + 7808,
            *(_DWORD *)(v14 + 6792),
            v96,
            v152,
            ((*((_QWORD *)&v105 + 1) & 0xFFFFFLL) + (__int64)v105) >> 20,
            v153 / 0x100000,
            a3 != 0,
            v93,
            v92,
            BitMapHeader.SizeOfBitMap,
            v139,
            v142);
        }
        if ( v127 )
          RtlFreeUnicodeString(&UnicodeString);
        if ( BitMapBuffer )
          ExFreePoolWithTag(BitMapBuffer, 0);
        v120 = P;
        if ( P )
          ExFreePoolWithTag(P, 0);
        if ( v133 )
          NtfsReleasePagingResourcePriv((__int64)v120, *(_QWORD *)(v14 + 72));
        if ( v126 )
          NtfsReleaseFcbEx(a1, *(_QWORD *)(v146 + 184), 0);
        if ( v132 )
        {
          NtfsReleaseFcbEx(a1, *(_QWORD *)(*(_QWORD *)(v14 + 48) + 184LL), 0);
          NtfsReleaseFcbEx(a1, *(_QWORD *)(*(_QWORD *)(v14 + 192) + 184LL), 0);
        }
        NtfsReleaseVcb(a1, v14);
        NtfsCleanupAttributeContext(v121, v167);
        if ( NtfsStatusDebugFlags
          && IsClearOrSet
          && IsClearOrSet != 294
          && IsClearOrSet - 298 > 1
          && IsClearOrSet < 0xFFFFFFED
          && IsClearOrSet != -1073741802
          && IsClearOrSet + 2147483643 > 1
          && IsClearOrSet != -1073741807
          && IsClearOrSet != 259
          && IsClearOrSet != -1073741608 )
        {
          NtfsStatusTraceAndDebugInternal(a1, IsClearOrSet, 0x12612Au);
        }
        NtfsExtendedCompleteRequestInternal(a1, (IRP *)v162, IsClearOrSet, v162 != 0, (IsClearOrSet & 0x80000000) == 0);
        return IsClearOrSet;
      }
      if ( v154->FileObject != *(PFILE_OBJECT *)(v14 + 1480) )
      {
        IsClearOrSet = -1073741811;
        if ( NtfsStatusDebugFlags )
        {
          v20 = 1203332;
          goto LABEL_258;
        }
        goto LABEL_259;
      }
      v17 = *(_QWORD *)(v14 + 5368);
      *(_QWORD *)&BitMapHeader.SizeOfBitMap = *(_QWORD *)(v14 + 5376);
      v153 = (*(_QWORD *)&BitMapHeader.SizeOfBitMap - 1LL) * *(unsigned int *)(v14 + 364);
      v157 = v153;
      IsClearOrSet = NtfsRunIsClearOrSet(a1, v14, v17, *(_QWORD *)(v14 + 296) - v17, 0, 0);
      v130 = IsClearOrSet;
      NtfsReleaseFcbEx(a1, *(_QWORD *)(*(_QWORD *)(v14 + 72) + 184LL), 0);
      if ( IsClearOrSet == -1073741791 || IsClearOrSet == -1073741267 )
      {
        if ( !ExIsResourceAcquiredExclusiveLite((PERESOURCE)(v14 + 2160)) )
        {
          NtfsReleaseVcb(a1, v14);
          NtfsAcquireExclusiveVcb(a1, v14, 1);
          v128 = 1;
        }
        if ( (*(_DWORD *)(v14 + 4) & 1) == 0 )
        {
          IsClearOrSet = -1073741202;
          if ( NtfsStatusDebugFlags )
          {
            v20 = 1203458;
            goto LABEL_258;
          }
          goto LABEL_259;
        }
        NtfsAcquireAllFiles(a1, v14, 6);
        v129 = 1;
        LfsFlushToLsn(*(_QWORD *)(*(_QWORD *)(a1 + 104) + 232LL), NtfsLargeMax);
        if ( (*(_DWORD *)(a1 + 16) & 0x100000) == 0
          && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x40) != 0 )
        {
          McTemplateU0p_EtwWriteTransfer(v21, (const EVENT_DESCRIPTOR *)fsctrl_c23834, v14);
        }
        NtfsFreeRecentlyDeallocated((int *)a1, *(_QWORD *)(a1 + 104), &NtfsLargeMax, 1u);
        if ( (*(_DWORD *)(a1 + 16) & 0x100000) == 0
          && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x40) != 0 )
        {
          McTemplateU0p_EtwWriteTransfer(v22, (const EVENT_DESCRIPTOR *)fsctrl_c23843, v14);
        }
        NtfsReleaseAllFiles(a1, v14, 6);
        v129 = 0;
        NtfsMarkUnusedContextPreTrimProcessing(a1);
        NtfsWaitForDeallocatedClustersToDrain(*(_QWORD *)(a1 + 104), 1u);
        NtfsAcquireExclusiveFcb(a1, *(_QWORD *)(*(_QWORD *)(v14 + 72) + 184LL), 0, 9);
        IsClearOrSet = NtfsRunIsClearOrSet(a1, v14, v17, *(_QWORD *)(v14 + 296) - v17, 0, 0);
        v130 = IsClearOrSet;
        NtfsReleaseFcbEx(a1, *(_QWORD *)(*(_QWORD *)(v14 + 72) + 184LL), 0);
        v19 = v146;
      }
      v128 = 1;
      if ( (IsClearOrSet & 0x80000000) != 0 )
      {
        v128 = 1;
        goto LABEL_260;
      }
    }
    NtfsAcquireExclusiveFcb(a1, *(_QWORD *)(*(_QWORD *)(v14 + 192) + 184LL), 0, 1);
    if ( a3 )
    {
      NtfsAcquireExclusiveScbEx(a1, v19, 0);
      v126 = 1;
      if ( (unsigned __int64)(v17 << *(_BYTE *)(v14 + 488)) >= *(_QWORD *)(v19 + 24) )
      {
        NtfsReleaseFcbEx(a1, *(_QWORD *)(v19 + 184), 0);
        v126 = 0;
      }
      else
      {
        NtfsDeleteAllocation(a1, 0, v19, v17, 0x7FFFFFFFFFFFFFFFLL, 1u, 0);
      }
LABEL_117:
      NtfsAcquireExclusiveFcb(a1, *(_QWORD *)(*(_QWORD *)(v14 + 48) + 184LL), 0, 1);
      v132 = 1;
      *(_QWORD *)&v172 = KeQueryUnbiasedInterruptTime();
      v134 = 3;
      v135 = 3;
      v33 = *(_QWORD *)(v14 + 72);
      v161 = v33;
      NtfsAcquirePagingResourceExclusive(a1, v33, 1u);
      v133 = 1;
      NtfsAcquireExclusiveFcb(a1, *(_QWORD *)(v33 + 184), 0, 9);
      if ( a3 )
      {
        KeAcquireGuardedMutex((PKGUARDED_MUTEX)(v14 + 720));
        ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v14 + 6376));
        v34 = *(_QWORD *)(v14 + 296) - v17;
        *(_QWORD *)v144 = *(_QWORD *)(v14 + 328) + (*(__int64 *)(v14 + 328) >> 8) + *(_QWORD *)(v14 + 6368);
        if ( v34 > *(_QWORD *)(v14 + 304) )
        {
          NtfsAllocateDiskFullContext(a1, v34 << *(_BYTE *)(v14 + 488), 0x27700125DDDLL);
          if ( NtfsStatusDebugFlags )
            NtfsStatusTraceAndDebugInternal(0, 0xC000007F, 0x125DDEu);
          IsClearOrSet = -1073741697;
          v130 = -1073741697;
        }
        if ( *(__int64 *)v144 >= *(_QWORD *)(v14 + 304) - v34 )
        {
          NtfsAllocateDiskFullContext(a1, v34 << *(_BYTE *)(v14 + 488), 0x27800125DE5LL);
          if ( NtfsStatusDebugFlags )
            NtfsStatusTraceAndDebugInternal(0, 0xC000007F, 0x125DE6u);
          IsClearOrSet = -1073741697;
          v130 = -1073741697;
        }
        ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v14 + 6376));
        KeReleaseGuardedMutex((PKGUARDED_MUTEX)(v14 + 720));
        if ( (IsClearOrSet & 0x80000000) != 0 )
          goto LABEL_260;
      }
      else
      {
        if ( *(_QWORD *)(v14 + 296) > v17 )
        {
          IsClearOrSet = -1073741811;
          if ( NtfsStatusDebugFlags )
          {
            v20 = 1203705;
            goto LABEL_258;
          }
          goto LABEL_259;
        }
        if ( *(_QWORD *)(v14 + 296) == v17 )
        {
          IsClearOrSet = 0;
          goto LABEL_259;
        }
      }
      NtfsGetDiskGeometry(a1, *(_QWORD *)(v14 + 224), (__int64)v170, v138);
      v35 = *(unsigned int *)(v14 + 364);
      if ( (_DWORD)v35 != LODWORD(v170[0]) || v153 + v35 > *(__int64 *)v138 )
      {
        IsClearOrSet = -1073741811;
        if ( NtfsStatusDebugFlags )
        {
          v20 = 1203729;
          goto LABEL_258;
        }
        goto LABEL_259;
      }
      CcFlushCache((PSECTION_OBJECT_POINTERS)(*(_QWORD *)(v33 + 288) + 16LL), 0, 0, &IoStatus);
      NtfsNormalizeAndCleanupTransaction(a1, (NTSTATUS *)&IoStatus.0);
      if ( !NtfsPurgeCacheSection(a1, (__int64 *)v33, 0, 0, 0) )
      {
        if ( NtfsStatusDebugFlags )
          NtfsStatusTraceAndDebugInternal(a1, 0xC000001B, 0x125E27u);
        NtfsRaiseStatusInternal(a1, -1073741797, 0, 0, 1203751);
      }
      NtfsSnapshotScb(a1, v33);
      *(_QWORD *)(*(_QWORD *)(v33 + 496) + 64LL) = 0;
      *(_QWORD *)(*(_QWORD *)(v33 + 496) + 72LL) = 0x7FFFFFFFFFFFFFFFLL;
      v36 = (((v17 + 7) >> 3) + 7) & 0xFFFFFFFFFFFFFFF8uLL;
      v37 = *(_BYTE *)(v14 + 488);
      v38 = (v36 + *(unsigned int *)(v14 + 480)) >> v37 << v37;
      v39 = (_QWORD *)(v33 + 24);
      v40 = *(_QWORD *)(v33 + 24);
      *(_QWORD *)v138 = v40;
      if ( v38 <= v40 )
      {
        *(_QWORD *)(v14 + 296) = 8 * v36;
        if ( v38 >= v40 )
          goto LABEL_151;
        NtfsDeleteAllocation(a1, 0, v33, v38 >> *(_BYTE *)(v14 + 488), 0x7FFFFFFFFFFFFFFFLL, 1u, 0);
      }
      else
      {
        v144[0] = v38 - v40;
        v150 = (v38 - v40) >> v37;
        v165 = v150;
        v41 = *(_QWORD *)(v14 + 336);
        v42 = v41 + 1;
        v164 = v41 + 1;
        if ( v41 + 1 + v150 > v17 )
          v42 = v41;
        v155 = v42;
        v164 = v42;
        NtfsPreloadAllocationInternal(a1, v33, 0, 0, v40 >> v37, 0);
        if ( (*(_DWORD *)(a1 + 12) & 0x20000) != 0 )
        {
          if ( *(_QWORD *)(v14 + 8144) )
          {
            IsClearOrSet = NtfsSetTPMap(a1, v155, v150, v134);
            v130 = IsClearOrSet;
            if ( (IsClearOrSet & 0x80000000) != 0 )
            {
              if ( NtfsStatusDebugFlags
                && IsClearOrSet < 0xFFFFFFED
                && IsClearOrSet != -1073741802
                && IsClearOrSet + 2147483643 > 1
                && IsClearOrSet != -1073741807
                && IsClearOrSet != -1073741608 )
              {
                NtfsStatusTraceAndDebugInternal(a1, IsClearOrSet, 0x125EA3u);
              }
              NtfsRaiseStatusInternal(a1, IsClearOrSet, 0, 0, 1203875);
            }
          }
          if ( !NtfsAddNtfsMcbEntry(v33 + 400, *(__int64 *)v138 >> *(_BYTE *)(v14 + 488), v155, v150, 0, 1u) )
          {
            if ( NtfsStatusDebugFlags )
              NtfsStatusTraceAndDebugInternal(a1, 0xC000009A, 0x125EAEu);
            NtfsRaiseStatusInternal(a1, -1073741670, 0, 0, 1203886);
          }
          v131 = 1;
          NtfsWriteBytes(
            a1,
            v14,
            v33,
            *(union _LARGE_INTEGER *)v138,
            0,
            v144[0],
            ((unsigned int)dword_1400956B8 >> 19) & 4);
          *(_QWORD *)(v14 + 296) = 8 * v36;
          if ( !NtfsLookupInFileRecord(
                  a1,
                  *(_QWORD *)(v33 + 184),
                  (_DWORD *)(*(_QWORD *)(v33 + 184) + 8LL),
                  *(_DWORD *)(v33 + 256),
                  (const UNICODE_STRING *)(v33 + 264),
                  0,
                  0,
                  0,
                  0,
                  (__int64)v167)
            && (*(_DWORD *)(v33 + 512) & 4) == 0 )
          {
            NtfsAttachCorruption_BadOrOrphanFRS(
              a1,
              2,
              1203920,
              v43,
              (_DWORD *)(*(_QWORD *)(v33 + 184) + 8LL),
              *(_QWORD *)(v33 + 184),
              0);
            NtfsAttachRepairInfoPriv(a1, 512, 0, (struct _LIST_ENTRY *)0xA900125ED0LL);
            if ( NtfsStatusDebugFlags )
              NtfsStatusTraceAndDebugInternal(a1, 0xC0000102, 0x125ED0u);
            NtfsRaiseStatusInternal(a1, -1073741566, *(_QWORD *)(v33 + 184) + 8, *(_QWORD *)(v33 + 184), 1203920);
          }
          NtfsAddAttributeAllocation(a1, v33, v167, 0, 0, 0);
          v131 = 0;
        }
        else
        {
          v125[0] = 0;
          NtfsAddAllocation(a1, 0, v33, *(__int64 *)v138 >> *(_BYTE *)(v14 + 488), v150, *(_QWORD *)v125, 0);
          *(_QWORD *)(v14 + 296) = 8 * v36;
          v150 = 0;
          v165 = 0;
        }
        NtfsSetCcFileSizes(*(struct _FILE_OBJECT **)(v33 + 280), v33, (struct _CC_FILE_SIZES *)(v33 + 24));
      }
      v39 = (_QWORD *)(v33 + 24);
LABEL_151:
      if ( (*(_DWORD *)(v33 + 200) & 0x20000) != 0 )
      {
        v44 = *(_QWORD *)(v33 + 464);
        if ( v44 >= v36 )
        {
          if ( *(_QWORD *)(v33 + 40) > v36 )
          {
            if ( *(_QWORD *)(*(_QWORD *)(v33 + 288) + 16LL) )
            {
              v45 = (v36 + 4095) & 0xFFFFFFFFFFFFF000uLL;
              if ( v45 < v44 )
                *(_QWORD *)(v33 + 464) = v45;
            }
            else
            {
              *(_QWORD *)(v33 + 464) = v36;
            }
          }
        }
        else
        {
          *(_QWORD *)(v33 + 464) = v36;
        }
      }
      *(_QWORD *)(v33 + 40) = v36;
      if ( (*(_DWORD *)(v33 + 200) & 0x20000) == 0 || *(_QWORD *)(v33 + 32) >= v36 )
        goto LABEL_173;
      v46 = *(_QWORD *)(v33 + 464);
      if ( v36 < v46 )
        v46 = (((v17 + 7) >> 3) + 7) & 0xFFFFFFFFFFFFFFF8uLL;
      if ( v46 <= v36 )
      {
LABEL_173:
        *(_QWORD *)(v33 + 32) = v36;
        *(_QWORD *)(v33 + 472) = *v39;
        NtfsWriteFileSizes(a1, v33, 0, 1, 1, 1);
        NtfsSetCcFileSizes(*(struct _FILE_OBJECT **)(v33 + 280), v33, (struct _CC_FILE_SIZES *)(v33 + 24));
        if ( !a3 )
        {
          v50 = 8LL * *(_QWORD *)v138;
          if ( *(_QWORD *)(v14 + 296) < 8LL * *(_QWORD *)v138 )
            v50 = *(_QWORD *)(v14 + 296);
          v51 = *(_QWORD *)(v14 + 336);
          if ( v50 != v51 )
            NtfsModifyBitsInBitmap(a1, v14, v51, v50, 22, 21);
          if ( v150 )
            NtfsModifyBitsInBitmap(a1, v14, v155, v155 + v150, 21, 22);
        }
        if ( 8 * v36 != v17 )
          NtfsModifyBitsInBitmap(a1, v14, v17, 8 * v36, 21, 0);
        P = ExAllocatePoolWithTag(
              (POOL_TYPE)528,
              (unsigned int)(*(_DWORD *)(v14 + 364) + *(_DWORD *)(*(_QWORD *)(v14 + 224) + 152LL)),
              0x6646744Eu);
        v52 = *(int *)(*(_QWORD *)(v14 + 224) + 152LL);
        v53 = (_QWORD *)(~(_DWORD)v52 & ((unsigned __int64)P + v52));
        NtfsReadBootSector(a1, a2, v14, v53, v134);
        if ( !NtfsIsBootSectorNtfs((__int64)v53) )
        {
          v162 = 0xDD00125F5BLL;
          NtfsAttachCorruptionSimple(a1, 1u, 2050, 1204059, 0);
          NtfsAttachRepairInfoPriv(a1, 0, 0, (struct _LIST_ENTRY *)0xDD00125F5BLL);
          if ( NtfsStatusDebugFlags )
            NtfsStatusTraceAndDebugInternal(a1, 0xC0000032, 0x125F5Bu);
          NtfsRaiseStatusInternal(a1, -1073741774, 0, 0, 1204059);
        }
        if ( *(_QWORD *)(v14 + 8144) )
        {
          v54 = v17 << *(_BYTE *)(v14 + 488);
          v55 = *(_QWORD *)(v14 + 8176);
          v56 = v54 < v55 ? 1LL : (v55 != 0) + 1 + (unsigned int)((v54 - v55) / *(_QWORD *)(v14 + 8152));
          v160 = v56;
          *(_QWORD *)SizeOfBitMap = v56;
          if ( (_DWORD)v56 != *(_DWORD *)(v14 + 8136) )
          {
            v57 = (v134 + ((unsigned int)(v56 + 7) >> 3)) & 0xFFFFFFFC;
            BitMapBuffer = (PULONG)ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), v57, 0x6646744Eu);
            memset(BitMapBuffer, 0, v57);
          }
        }
        *(_QWORD *)(v14 + 296) = v17;
        v58 = *(_QWORD *)&BitMapHeader.SizeOfBitMap;
        *(_QWORD *)(v14 + 432) = *(_QWORD *)&BitMapHeader.SizeOfBitMap;
        *(_QWORD *)(v14 + 424) = --v58;
        v53[5] = v58;
        NtfsWriteBootSector(a1, a2, v14, v53, v134);
        NtfsCheckpointCurrentTransaction(a1);
        if ( !*(_QWORD *)(v14 + 8144) )
        {
LABEL_225:
          NtfsUpdateTieringInfo(a1);
          NtfsScanEntireBitmap(a1, v14, 10, 5);
          LfsFlushToLsn(*(_QWORD *)(v14 + 232), NtfsLargeMax);
          *(_QWORD *)(v14 + 336) = *(_QWORD *)(v14 + 296);
          v73 = *(_QWORD *)(v14 + 296) << *(_BYTE *)(v14 + 488);
          v74 = *(_QWORD *)(v14 + 192);
          if ( (*(_DWORD *)(v74 + 200) & 0x20000) != 0 && *(_QWORD *)(v74 + 24) > v73 && *(_QWORD *)(v74 + 464) > v73 )
            *(_QWORD *)(*(_QWORD *)(v14 + 192) + 464LL) = v73;
          *(_QWORD *)(*(_QWORD *)(v14 + 192) + 24LL) = v73;
          v75 = *(_QWORD *)(v14 + 192);
          if ( (*(_DWORD *)(v75 + 200) & 0x20000) == 0 )
            goto LABEL_244;
          v76 = *(_QWORD *)(v75 + 24);
          if ( *(_QWORD *)(v75 + 32) >= v76 )
            goto LABEL_244;
          if ( v76 >= *(_QWORD *)(v75 + 464) )
            v76 = *(_QWORD *)(v75 + 464);
          if ( v76 <= *(_QWORD *)(v75 + 40) )
          {
LABEL_244:
            *(_QWORD *)(*(_QWORD *)(v14 + 192) + 32LL) = *(_QWORD *)(*(_QWORD *)(v14 + 192) + 24LL);
            v81 = *(_QWORD *)(v14 + 192);
            v82 = *(_DWORD *)(v81 + 200);
            if ( (v82 & 0x20000) != 0 )
            {
              v83 = *(_QWORD *)(v81 + 32);
              v84 = *(_QWORD *)(v81 + 464);
              if ( v84 < v83 )
                goto LABEL_251;
              if ( *(_QWORD *)(v81 + 40) <= v83 )
                goto LABEL_253;
              if ( !*(_QWORD *)(*(_QWORD *)(v81 + 288) + 16LL) || v83 == 0x7FFFFFFFFFFFFFFFLL )
              {
LABEL_251:
                v85 = *(_QWORD *)(v14 + 192);
                v86 = *(_QWORD *)(v85 + 32);
                goto LABEL_252;
              }
              if ( (__int64)((v83 + 4095) & 0xFFFFFFFFFFFFF000uLL) < v84 )
              {
                v85 = *(_QWORD *)(v14 + 192);
                v86 = (*(_QWORD *)(v85 + 32) + 4095LL) & 0xFFFFFFFFFFFFF000uLL;
LABEL_252:
                *(_QWORD *)(v85 + 464) = v86;
              }
            }
LABEL_253:
            *(_QWORD *)(*(_QWORD *)(v14 + 192) + 40LL) = *(_QWORD *)(*(_QWORD *)(v14 + 192) + 32LL);
            SetFlagInterlocked((unsigned int *)(v14 + 4), 0x80u);
            v88 = a3;
            v24 = v136;
            if ( !a3
              || (*(_QWORD *)(v14 + 5368) = v87,
                  *(_QWORD *)(v14 + 5376) = 0,
                  *(_QWORD *)(v14 + 1480) = 0,
                  *(_DWORD *)&v24->Type == 2) )
            {
              FsRtlNotifyVolumeEvent(v154->FileObject, 0xDu);
            }
            goto LABEL_262;
          }
          v77 = *(_QWORD *)(v14 + 192);
          v78 = *(_DWORD *)(v77 + 200);
          if ( (v78 & 0x20000) != 0 )
          {
            v79 = *(_QWORD *)(v77 + 464);
            if ( v79 < v76 )
            {
LABEL_242:
              *(_QWORD *)(*(_QWORD *)(v14 + 192) + 464LL) = v76;
              goto LABEL_243;
            }
            if ( *(_QWORD *)(v77 + 40) > v76 )
            {
              if ( *(_QWORD *)(*(_QWORD *)(v77 + 288) + 16LL) )
              {
                if ( v76 == 0x7FFFFFFFFFFFFFFFLL )
                {
                  *(_QWORD *)(*(_QWORD *)(v14 + 192) + 464LL) = 0x7FFFFFFFFFFFFFFFLL;
                }
                else
                {
                  v80 = (v76 + 4095) & 0xFFFFFFFFFFFFF000uLL;
                  if ( v80 < v79 )
                    *(_QWORD *)(*(_QWORD *)(v14 + 192) + 464LL) = v80;
                }
                goto LABEL_243;
              }
              goto LABEL_242;
            }
          }
LABEL_243:
          *(_QWORD *)(*(_QWORD *)(v14 + 192) + 40LL) = v76;
          goto LABEL_244;
        }
        v59 = (struct _RTL_BITMAP *)(v14 + 8136);
        v60 = *(_DWORD *)(v14 + 8136);
        v61 = 0;
        v159 = 0;
        if ( _bittest64(*(const signed __int64 **)(v14 + 8144), v60 - 1) && v60 > 1 )
        {
          RtlClearBit((PRTL_BITMAP)(v14 + 8136), v60 - 1);
          *(_QWORD *)(v14 + 288) -= (__int64)(*(unsigned int *)(v14 + 480) + *(_QWORD *)(v14 + 0x2000)) >> *(_BYTE *)(v14 + 488);
          v61 = v59->SizeOfBitMap - 1;
          v159 = v61;
        }
        v62 = BitMapBuffer;
        v63 = SizeOfBitMap[0];
        if ( BitMapBuffer && v60 > SizeOfBitMap[0] )
        {
          *(_QWORD *)(v14 + 288) -= *(_DWORD *)(v14 + 8160)
                                  * (unsigned int)RtlNumberOfSetBitsInRange(
                                                    v14 + 8136,
                                                    SizeOfBitMap[0],
                                                    v60 - SizeOfBitMap[0]);
          v63 = SizeOfBitMap[0];
          v62 = BitMapBuffer;
        }
        if ( v63 <= 1 )
        {
          *(_QWORD *)(v14 + 0x2000) = 0;
          *(_QWORD *)(v14 + 288) = *(_QWORD *)(v14 + 296);
          *(_QWORD *)(v14 + 8184) = *(_QWORD *)(v14 + 296) << *(_BYTE *)(v14 + 488);
        }
        else
        {
          v64 = *(_QWORD *)(v14 + 8184);
          if ( v64 != *(_QWORD *)(v14 + 8176) )
          {
            *(_QWORD *)(v14 + 288) -= (v64 + *(unsigned int *)(v14 + 480)) >> *(_BYTE *)(v14 + 488);
            *(_QWORD *)(v14 + 288) += (__int64)(*(_QWORD *)(v14 + 8176) + *(unsigned int *)(v14 + 480)) >> *(_BYTE *)(v14 + 488);
            v64 = *(_QWORD *)(v14 + 8176);
            *(_QWORD *)(v14 + 8184) = v64;
          }
          *(_QWORD *)(v14 + 0x2000) = (unsigned __int64)((v17 << *(_BYTE *)(v14 + 488)) - v64) % *(_QWORD *)(v14 + 8152);
        }
        if ( v62 )
        {
          LODWORD(BitMapHeader.Buffer) = 0;
          *(_QWORD *)&BitMapHeader.SizeOfBitMap = 0;
          RtlInitializeBitMap(&BitMapHeader, v62, v63);
          v65 = SizeOfBitMap[0];
          if ( v60 < SizeOfBitMap[0] )
            v65 = v60;
          RtlExtractBitMap(v14 + 8136, &BitMapHeader, 0, v65);
          ExFreePoolWithTag(*(PVOID *)(v14 + 8144), 0);
          *v59 = BitMapHeader;
          BitMapBuffer = 0;
          v63 = SizeOfBitMap[0];
        }
        if ( v61 )
        {
          if ( v61 < v63 - 1 )
          {
            RtlSetBit((PRTL_BITMAP)(v14 + 8136), v61);
            v66 = *(unsigned int *)(v14 + 8160);
LABEL_210:
            *(_QWORD *)(v14 + 288) += v66;
LABEL_214:
            if ( v150 )
            {
              v67 = v155 << *(_BYTE *)(v14 + 488);
              v68 = *(_QWORD *)(v14 + 8184);
              if ( v67 < v68 )
                v69 = 0;
              else
                v69 = (v68 != 0) + (unsigned int)((v67 - v68) / *(_QWORD *)(v14 + 8152));
              v70 = (v155 + v150 - 1) << *(_BYTE *)(v14 + 488);
              if ( v70 < v68 )
                v71 = 0;
              else
                v71 = (v68 != 0) + (unsigned int)((v70 - v68) / *(_QWORD *)(v14 + 8152));
              *(_QWORD *)(v14 + 288) += *(_DWORD *)(v14 + 8160)
                                      * (unsigned int)RtlNumberOfClearBitsInRange(v14 + 8136, v69, v71 - v69 + 1);
              if ( v71 == SizeOfBitMap[0] - 1 && !_bittest64(*(const signed __int64 **)(v14 + 8144), v71) )
              {
                v72 = *(_QWORD *)(v14 + 288) - *(unsigned int *)(v14 + 8160);
                *(_QWORD *)(v14 + 288) = v72;
                *(_QWORD *)(v14 + 288) = v72
                                       + *(_QWORD *)(v14 + 0x2000) / (unsigned __int64)*(unsigned int *)(v14 + 356);
              }
              RtlSetBits((PRTL_BITMAP)(v14 + 8136), v69, v71 - v69 + 1);
            }
            goto LABEL_225;
          }
          if ( v61 == v63 - 1 )
          {
            RtlSetBit((PRTL_BITMAP)(v14 + 8136), v61);
            v66 = (__int64)(*(_QWORD *)(v14 + 0x2000) + *(unsigned int *)(v14 + 480)) >> *(_BYTE *)(v14 + 488);
            goto LABEL_210;
          }
        }
        if ( _bittest64(*(const signed __int64 **)(v14 + 8144), v63 - 1) && v63 > 1 )
        {
          *(_QWORD *)(v14 + 288) -= *(unsigned int *)(v14 + 8160);
          *(_QWORD *)(v14 + 288) += (__int64)(*(_QWORD *)(v14 + 0x2000) + *(unsigned int *)(v14 + 480)) >> *(_BYTE *)(v14 + 488);
        }
        goto LABEL_214;
      }
      v47 = *(_DWORD *)(v33 + 200);
      if ( (v47 & 0x20000) != 0 )
      {
        v48 = *(_QWORD *)(v33 + 464);
        if ( v48 < v46 )
        {
LABEL_171:
          *(_QWORD *)(v33 + 464) = v46;
          goto LABEL_172;
        }
        if ( *(_QWORD *)(v33 + 40) > v46 )
        {
          if ( *(_QWORD *)(*(_QWORD *)(v33 + 288) + 16LL) && v46 != 0x7FFFFFFFFFFFFFFFLL )
          {
            v49 = (v46 + 4095) & 0xFFFFFFFFFFFFF000uLL;
            if ( v49 < v48 )
              *(_QWORD *)(v33 + 464) = v49;
            goto LABEL_172;
          }
          goto LABEL_171;
        }
      }
LABEL_172:
      *(_QWORD *)(v33 + 40) = v46;
      goto LABEL_173;
    }
    v25 = v17 << *(_BYTE *)(v14 + 488);
    v26 = v146;
    NtfsAcquireExclusiveScbEx(a1, v146, 0);
    v126 = 1;
    v27 = *(_QWORD *)(v26 + 24);
    if ( v25 <= v27 )
    {
      NtfsReleaseFcbEx(a1, *(_QWORD *)(v26 + 184), 0);
      v126 = 0;
      goto LABEL_117;
    }
    NtfsAddSparseAllocation(a1, 0, v26, v27, v25 - v27);
    v28 = *(_DWORD *)(v26 + 200);
    if ( (v28 & 0x20000) == 0 || *(_QWORD *)(v26 + 32) >= v25 )
      goto LABEL_115;
    v29 = *(_QWORD *)(v26 + 464);
    if ( v25 < v29 )
      v29 = v25;
    if ( v29 <= *(_QWORD *)(v26 + 40) )
    {
LABEL_115:
      *(_QWORD *)(v26 + 32) = v25;
      NtfsWriteFileSizes(a1, v26, 0, 0, 1, 1);
      goto LABEL_117;
    }
    v30 = *(_DWORD *)(v26 + 200);
    if ( (v30 & 0x20000) != 0 )
    {
      v31 = *(_QWORD *)(v26 + 464);
      if ( v31 < v29 )
      {
LABEL_113:
        *(_QWORD *)(v26 + 464) = v29;
        goto LABEL_114;
      }
      if ( *(_QWORD *)(v26 + 40) > v29 )
      {
        if ( *(_QWORD *)(*(_QWORD *)(v26 + 288) + 16LL) && v29 != 0x7FFFFFFFFFFFFFFFLL )
        {
          v32 = (v29 + 4095) & 0xFFFFFFFFFFFFF000uLL;
          if ( v32 < v31 )
            *(_QWORD *)(v26 + 464) = v32;
          goto LABEL_114;
        }
        goto LABEL_113;
      }
    }
LABEL_114:
    *(_QWORD *)(v26 + 40) = v29;
    goto LABEL_115;
  }
  v15 = -1073741662;
  if ( NtfsStatusDebugFlags )
    NtfsStatusTraceAndDebugInternal(a1, 0xC00000A2, 0x125B82u);
  NtfsExtendedCompleteRequestInternal(a1, a2, -1073741662, a2 != 0, 0);
  if ( !NtfsStatusDebugFlags )
    return v15;
  v16 = 1203075;
LABEL_386:
  NtfsStatusTraceAndDebugInternal(0, v15, v16);
  return v15;
}

```

## disassembly

```asm
0x14027e3c8  mov     r11, rsp
0x14027e3cb  mov     [r11+18h], r8b
0x14027e3cf  push    rbx
0x14027e3d0  push    rsi
0x14027e3d1  push    rdi
0x14027e3d2  push    r12
0x14027e3d4  push    r13
0x14027e3d6  push    r14
0x14027e3d8  push    r15
0x14027e3da  sub     rsp, 2C0h
0x14027e3e1  mov     rax, cs:__security_cookie
0x14027e3e8  xor     rax, rsp
0x14027e3eb  mov     [rsp+2F8h+var_40], rax
0x14027e3f3  mov     r12b, r8b
0x14027e3f6  mov     r13, rdx
0x14027e3f9  mov     [rsp+2F8h+var_128], rdx
0x14027e401  mov     r14, rcx
0x14027e404  mov     [rsp+2F8h+var_1E0], rcx
0x14027e40c  xor     edi, edi
0x14027e40e  mov     esi, edi
0x14027e410  mov     [rsp+2F8h+var_214], edi
0x14027e417  mov     [r11-1D8h], rdi
0x14027e41e  mov     [r11-1D0h], rdi
0x14027e425  mov     eax, edi
0x14027e427  mov     [r11-170h], rax
0x14027e42e  mov     [r11-148h], rax
0x14027e435  xorps   xmm0, xmm0
0x14027e438  movups  xmmword ptr [rsp+2F8h+IoStatus], xmm0
0x14027e440  xor     edx, edx; Val
0x14027e442  lea     r8d, [rdi+58h]; Size
0x14027e446  lea     rcx, [r11-0F8h]; void *
0x14027e44d  call    memset
0x14027e452  xorps   xmm0, xmm0
0x14027e455  xor     eax, eax
0x14027e457  movups  [rsp+2F8h+var_80], xmm0
0x14027e45f  movups  [rsp+2F8h+var_80+0Ch], xmm0
0x14027e467  mov     qword ptr [rsp+2F8h+var_1F0], rdi
0x14027e46f  movups  xmmword ptr [rsp+2F8h+UnicodeString.Length], xmm0
0x14027e477  mov     [rsp+2F8h+var_217], dil
0x14027e47f  xorps   xmm1, xmm1
0x14027e482  movups  [rsp+2F8h+var_98], xmm1
0x14027e48a  mov     [rsp+2F8h+var_88], rax
0x14027e492  mov     [rsp+2F8h+var_204], di
0x14027e49a  movups  [rsp+2F8h+var_60], xmm0
0x14027e4a2  movups  [rsp+2F8h+var_50], xmm0
0x14027e4aa  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x14027e4b1  nop     dword ptr [rax+rax+00h]
0x14027e4b6  mov     [rsp+2F8h+var_1A0], rax
0x14027e4be  mov     qword ptr [rsp+2F8h+var_60], rax
0x14027e4c6  lea     eax, [rdi+1]
0x14027e4c9  mov     [rsp+2F8h+var_204], ax
0x14027e4d1  test    r13, r13
0x14027e4d4  jz      loc_14027E576
0x14027e4da  lea     rdx, [rsp+2F8h+var_98+8]
0x14027e4e2  mov     rcx, r13
0x14027e4e5  call    cs:__imp_IoGetActivityIdIrp
0x14027e4ec  nop     dword ptr [rax+rax+00h]
0x14027e4f1  test    eax, eax
0x14027e4f3  jns     loc_14027E5A5
0x14027e4f9  mov     qword ptr [rsp+2F8h+var_98], rdi
0x14027e501  mov     rcx, [r13+0B8h]
0x14027e508  mov     [rsp+2F8h+var_168], rcx
0x14027e510  mov     eax, [rcx+10h]
0x14027e513  test    r12b, r12b
0x14027e516  jz      loc_14027E5D8
0x14027e51c  cmp     eax, 18h
0x14027e51f  jnb     loc_14027E5BA
0x14027e525  mov     al, cs:NtfsStatusDebugFlags
0x14027e52b  mov     esi, 0C000000Dh
0x14027e530  test    al, al
0x14027e532  jz      short loc_14027E544
0x14027e534  mov     r8d, 125B3Fh
0x14027e53a  mov     edx, esi
0x14027e53c  mov     rcx, r14
0x14027e53f  call    NtfsStatusTraceAndDebugInternal
0x14027e544  test    r13, r13
0x14027e547  setnz   r9b
0x14027e54b  mov     dword ptr [rsp+2F8h+Timeout], edi
0x14027e54f  mov     r8d, esi
0x14027e552  mov     rdx, r13
0x14027e555  mov     rcx, r14
0x14027e558  call    NtfsExtendedCompleteRequestInternal
0x14027e55d  mov     al, cs:NtfsStatusDebugFlags
0x14027e563  test    al, al
0x14027e565  jz      loc_140280944
0x14027e56b  mov     r8d, 125B40h
0x14027e571  jmp     loc_14028093B
0x14027e576  call    cs:__imp_IoGetActivityIdThread
0x14027e57d  nop     dword ptr [rax+rax+00h]
0x14027e582  mov     rcx, rax
0x14027e585  test    rax, rax
0x14027e588  jz      loc_14027E4F9
0x14027e58e  mov     rax, [rax]
0x14027e591  mov     qword ptr [rsp+2F8h+var_98+8], rax
0x14027e599  mov     rax, [rcx+8]
0x14027e59d  mov     [rsp+2F8h+var_88], rax
0x14027e5a5  lea     rax, [rsp+2F8h+var_98+8]
0x14027e5ad  mov     qword ptr [rsp+2F8h+var_98], rax
0x14027e5b5  jmp     loc_14027E501
0x14027e5ba  mov     rbx, [r13+18h]
0x14027e5be  mov     r15, [rbx+10h]
0x14027e5c2  movzx   edi, word ptr [rbx]
0x14027e5c5  mov     [rsp+2F8h+var_1F8], edi
0x14027e5cc  mov     [rsp+2F8h+var_1C8], di
0x14027e5d4  xor     edi, edi
0x14027e5d6  jmp     short loc_14027E649
0x14027e5d8  cmp     eax, 8
0x14027e5db  jnb     short loc_14027E62E
0x14027e5dd  mov     al, cs:NtfsStatusDebugFlags
0x14027e5e3  mov     esi, 0C000000Dh
0x14027e5e8  test    al, al
0x14027e5ea  jz      short loc_14027E5FC
0x14027e5ec  mov     r8d, 125B4Ch
0x14027e5f2  mov     edx, esi
0x14027e5f4  mov     rcx, r14
0x14027e5f7  call    NtfsStatusTraceAndDebugInternal
0x14027e5fc  test    r13, r13
0x14027e5ff  setnz   r9b
0x14027e603  mov     dword ptr [rsp+2F8h+Timeout], edi
0x14027e607  mov     r8d, esi
0x14027e60a  mov     rdx, r13
0x14027e60d  mov     rcx, r14
0x14027e610  call    NtfsExtendedCompleteRequestInternal
0x14027e615  mov     al, cs:NtfsStatusDebugFlags
0x14027e61b  test    al, al
0x14027e61d  jz      loc_140280944
0x14027e623  mov     r8d, 125B4Dh
0x14027e629  jmp     loc_14028093B
0x14027e62e  mov     rbx, rdi
0x14027e631  mov     eax, edi
0x14027e633  mov     [rsp+2F8h+var_1F8], eax
0x14027e63a  mov     [rsp+2F8h+var_1C8], ax
0x14027e642  mov     rax, [r13+18h]
0x14027e646  mov     r15, [rax]
0x14027e649  mov     qword ptr [rsp+2F8h+BitMapHeader.SizeOfBitMap], r15
0x14027e651  mov     [rsp+2F8h+var_1E8], rbx
0x14027e659  mov     [rsp+2F8h+var_200], rbx
0x14027e661  mov     byte ptr [rsp+2F8h+var_2C8], 1
0x14027e666  lea     rax, [rsp+2F8h+var_1D0]
0x14027e66e  mov     qword ptr [rsp+2F8h+var_2D0], rax
0x14027e673  lea     rax, [rsp+2F8h+var_178]
0x14027e67b  mov     [rsp+2F8h+Timeout], rax
0x14027e680  lea     r9, [rsp+2F8h+var_120]
0x14027e688  lea     r8, [rsp+2F8h+var_1D8]
0x14027e690  mov     rdx, [rcx+30h]
0x14027e694  mov     rcx, r14
0x14027e697  call    NtfsDecodeFileObject
0x14027e69c  cmp     eax, 4
0x14027e69f  jz      short loc_14027E6F2
0x14027e6a1  mov     al, cs:NtfsStatusDebugFlags
0x14027e6a7  mov     esi, 0C000000Dh
0x14027e6ac  test    al, al
0x14027e6ae  jz      short loc_14027E6C0
0x14027e6b0  mov     r8d, 125B61h
0x14027e6b6  mov     edx, esi
0x14027e6b8  mov     rcx, r14
0x14027e6bb  call    NtfsStatusTraceAndDebugInternal
0x14027e6c0  test    r13, r13
0x14027e6c3  setnz   r9b
0x14027e6c7  mov     dword ptr [rsp+2F8h+Timeout], edi
0x14027e6cb  mov     r8d, esi
0x14027e6ce  mov     rdx, r13
0x14027e6d1  mov     rcx, r14
0x14027e6d4  call    NtfsExtendedCompleteRequestInternal
0x14027e6d9  mov     al, cs:NtfsStatusDebugFlags
0x14027e6df  test    al, al
0x14027e6e1  jz      loc_140280944
0x14027e6e7  mov     r8d, 125B62h
0x14027e6ed  jmp     loc_14028093B
0x14027e6f2  mov     rcx, [rsp+2F8h+var_1D0]
0x14027e6fa  test    rcx, rcx
0x14027e6fd  jz      loc_14028094B
0x14027e703  bt      word ptr [rcx+68h], 9
0x14027e709  jnb     loc_14028094B
0x14027e70f  mov     rdi, qword ptr [rsp+2F8h+var_1D8]
0x14027e717  test    dword ptr [rdi+4], 2000000h
0x14027e71e  jz      short loc_14027E771
0x14027e720  mov     al, cs:NtfsStatusDebugFlags
0x14027e726  mov     ebx, 0C00000A2h
0x14027e72b  test    al, al
0x14027e72d  jz      short loc_14027E73F
0x14027e72f  mov     r8d, 125B82h
0x14027e735  mov     edx, ebx
0x14027e737  mov     rcx, r14
0x14027e73a  call    NtfsStatusTraceAndDebugInternal
0x14027e73f  test    r13, r13
0x14027e742  setnz   r9b
0x14027e746  mov     dword ptr [rsp+2F8h+Timeout], esi
0x14027e74a  mov     r8d, ebx
0x14027e74d  mov     rdx, r13
0x14027e750  mov     rcx, r14
0x14027e753  call    NtfsExtendedCompleteRequestInternal
0x14027e758  mov     al, cs:NtfsStatusDebugFlags
0x14027e75e  test    al, al
0x14027e760  jz      loc_140280A30
0x14027e766  mov     r8d, 125B83h
0x14027e76c  jmp     loc_140280A27
0x14027e771  lea     rcx, [rdi+19E8h]; Object
0x14027e778  mov     [rsp+2F8h+Timeout], rsi; Timeout
0x14027e77d  xor     r9d, r9d; Alertable
0x14027e780  xor     r8d, r8d; WaitMode
0x14027e783  xor     edx, edx; WaitReason
0x14027e785  call    cs:__imp_KeWaitForSingleObject
0x14027e78c  nop     dword ptr [rax+rax+00h]
0x14027e791  xor     r8d, r8d
0x14027e794  test    r12b, r12b
0x14027e797  jz      loc_14027E864
0x14027e79d  cmp     [rbx+8], r8
0x14027e7a1  jz      short loc_14027E7F8
0x14027e7a3  mov     al, cs:NtfsStatusDebugFlags
0x14027e7a9  mov     esi, 0C000000Dh
0x14027e7ae  test    al, al
0x14027e7b0  jz      short loc_14027E7C5
0x14027e7b2  mov     r8d, 125B9Ah
0x14027e7b8  mov     edx, esi
0x14027e7ba  mov     rcx, r14
0x14027e7bd  call    NtfsStatusTraceAndDebugInternal
0x14027e7c2  xor     r8d, r8d
0x14027e7c5  test    r13, r13
0x14027e7c8  setnz   r9b
0x14027e7cc  mov     dword ptr [rsp+2F8h+Timeout], r8d
0x14027e7d1  mov     r8d, esi
0x14027e7d4  mov     rdx, r13
0x14027e7d7  mov     rcx, r14
0x14027e7da  call    NtfsExtendedCompleteRequestInternal
0x14027e7df  mov     al, cs:NtfsStatusDebugFlags
0x14027e7e5  test    al, al
0x14027e7e7  jz      loc_140280944
0x14027e7ed  mov     r8d, 125B9Bh
0x14027e7f3  jmp     loc_14028093B
0x14027e7f8  test    r12b, r12b
0x14027e7fb  jz      short loc_14027E864
0x14027e7fd  cmp     dword ptr [rbx], 1
0x14027e800  jz      short loc_14027E864
0x14027e802  test    r15, r15
0x14027e805  jz      short loc_14027E85C
0x14027e807  mov     al, cs:NtfsStatusDebugFlags
0x14027e80d  mov     esi, 0C000000Dh
0x14027e812  test    al, al
0x14027e814  jz      short loc_14027E829
0x14027e816  mov     r8d, 125BC6h
0x14027e81c  mov     edx, esi
0x14027e81e  mov     rcx, r14
0x14027e821  call    NtfsStatusTraceAndDebugInternal
0x14027e826  xor     r8d, r8d
0x14027e829  test    r13, r13
0x14027e82c  setnz   r9b
0x14027e830  mov     dword ptr [rsp+2F8h+Timeout], r8d
0x14027e835  mov     r8d, esi
0x14027e838  mov     rdx, r13
0x14027e83b  mov     rcx, r14
0x14027e83e  call    NtfsExtendedCompleteRequestInternal
0x14027e843  mov     al, cs:NtfsStatusDebugFlags
0x14027e849  test    al, al
0x14027e84b  jz      loc_140280944
0x14027e851  mov     r8d, 125BC7h
0x14027e857  jmp     loc_14028093B
0x14027e85c  mov     r12, r8
0x14027e85f  jmp     loc_14027E8FF
0x14027e864  test    r15, r15
0x14027e867  jg      short loc_14027E8BE
0x14027e869  mov     al, cs:NtfsStatusDebugFlags
0x14027e86f  mov     esi, 0C000000Dh
0x14027e874  test    al, al
0x14027e876  jz      short loc_14027E88B
0x14027e878  mov     r8d, 125BACh
0x14027e87e  mov     edx, esi
0x14027e880  mov     rcx, r14
0x14027e883  call    NtfsStatusTraceAndDebugInternal
0x14027e888  xor     r8d, r8d
0x14027e88b  test    r13, r13
0x14027e88e  setnz   r9b
0x14027e892  mov     dword ptr [rsp+2F8h+Timeout], r8d
0x14027e897  mov     r8d, esi
0x14027e89a  mov     rdx, r13
0x14027e89d  mov     rcx, r14
0x14027e8a0  call    NtfsExtendedCompleteRequestInternal
0x14027e8a5  mov     al, cs:NtfsStatusDebugFlags
0x14027e8ab  test    al, al
0x14027e8ad  jz      loc_140280944
0x14027e8b3  mov     r8d, 125BADh
0x14027e8b9  jmp     loc_14028093B
0x14027e8be  mov     edx, [rdi+16Ch]
0x14027e8c4  lea     rax, [r15-1]
0x14027e8c8  imul    rdx, rax
0x14027e8cc  mov     [rsp+2F8h+var_170], rdx
0x14027e8d4  mov     [rsp+2F8h+var_148], rdx
0x14027e8dc  cmp     rdx, r15
0x14027e8df  jl      loc_1402808EF
0x14027e8e5  mov     cl, [rdi+1E8h]
0x14027e8eb  mov     r12, rdx
0x14027e8ee  sar     r12, cl
0x14027e8f1  mov     eax, 0FFFFFFFEh
0x14027e8f6  cmp     r12, rax
0x14027e8f9  jg      loc_1402808EF
0x14027e8ff  mov     [rsp+2F8h+var_130], r8
0x14027e907  mov     [rsp+2F8h+var_188], r8
0x14027e90f  mov     [rsp+2F8h+var_160], r8
0x14027e917  mov     [rsp+2F8h+P], r8
0x14027e91f  mov     [rsp+2F8h+var_210], r8b
  ... truncated ...
```
