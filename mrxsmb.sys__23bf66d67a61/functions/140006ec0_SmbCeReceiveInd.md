# SmbCeReceiveInd

- ea: `0x140006ec0`
- end: `0x140008660`
- name: `SmbCeReceiveInd`
- size: `6048`
- prototype: `__int64 __fastcall(__int64, unsigned int, unsigned int, int, unsigned int *, __int64, _QWORD **, _QWORD *, unsigned int *, __int64)`
- caller_count: `1`
- callee_count: `41`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140011910`

## callees

- `0x140001630`
- `0x140002750`
- `0x140003480`
- `0x140005e00`
- `0x140006680`
- `0x140006bb0`
- `0x140006ec0`
- `0x1400093a0`
- `0x140009fc0`
- `0x14000a000`
- `0x14000c030`
- `0x14000d910`
- `0x14000fbe0`
- `0x140013540`
- `0x140014370`
- `0x140014400`
- `0x1400147b0`
- `0x1400148f0`
- `0x1400149d0`
- `0x1400179f0`
- `0x14001b2a0`
- `0x1400267f0`
- `0x140026950`
- `0x140037f44`
- `0x140037fa4`
- `0x140038068`
- `0x14003838c`
- `0x1400383d0`
- `0x140038460`
- `0x140039fa8`
- `0x14003e714`
- `0x14003e994`
- `0x14003ebdc`
- `0x14003eebc`
- `0x14003f134`
- `0x14003f444`
- `0x14003f6bc`
- `0x14003f9cc`
- `0x14003fa24`
- `0x140055f6c`
- `0x140059ea0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400073dc`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400079ea`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400073dc`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400079ea`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14005c48a`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14005c48a`
- `ntoskrnl!IoAllocateMdl` at `0x14005c472`
- `ntoskrnl!IoAllocateMdl` at `0x14005c472`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140007227`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400078e8`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140007a11`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140007b57`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140007227`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400078e8`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140007a11`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140007b57`
- `ntoskrnl!KeGetCurrentIrql` at `0x140008007`
- `ntoskrnl!KeGetCurrentIrql` at `0x140008007`
- `ntoskrnl!KeTryToAcquireSpinLockAtDpcLevel` at `0x1400070e3`
- `ntoskrnl!KeTryToAcquireSpinLockAtDpcLevel` at `0x140007ae2`
- `ntoskrnl!KeTryToAcquireSpinLockAtDpcLevel` at `0x1400070e3`
- `ntoskrnl!KeTryToAcquireSpinLockAtDpcLevel` at `0x140007ae2`
- `ntoskrnl!KfRaiseIrql` at `0x14000700d`
- `ntoskrnl!KfRaiseIrql` at `0x14000700d`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14000702f`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14005bc85`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14000702f`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14005bc85`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1400070b7`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140007199`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1400071b5`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140007c6d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140008323`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14005bca1`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1400070b7`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140007199`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1400071b5`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140007c6d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140008323`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14005bca1`
- `ntoskrnl!KeLowerIrql` at `0x14000723f`
- `ntoskrnl!KeLowerIrql` at `0x140007907`
- `ntoskrnl!KeLowerIrql` at `0x14000723f`
- `ntoskrnl!KeLowerIrql` at `0x140007907`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140007eb5`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140007eb5`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140007ec9`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140007f78`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140007ec9`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140007f78`
- `ntoskrnl!IofCompleteRequest` at `0x140007e00`
- `ntoskrnl!IofCompleteRequest` at `0x140007e00`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000751e`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000751e`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14000754c`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14005b8ca`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14000754c`
- `ntoskrnl!ExReleaseRundownProtection` at `0x14005b8ca`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140006f22`
- `ntoskrnl!ExAcquireRundownProtection` at `0x140006f22`
- `ntoskrnl!KeBugCheckEx` at `0x140008627`
- `ntoskrnl!KeBugCheckEx` at `0x140008627`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140007841`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14005b856`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14005b881`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14005c407`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14005c434`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140007841`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14005b856`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14005b881`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14005c407`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14005c434`
- `rdbss!RxCeTrackTransportOpEx` at `0x140007f12`
- `rdbss!RxCeTrackTransportOpEx` at `0x140007f12`
- `rdbss!RxCeUntrackTransportOpEx` at `0x140008529`
- `rdbss!RxCeUntrackTransportOpEx` at `0x140008529`
- `rdbss!RxPerProcessCountersEnabled` at `0x1400072e4`
- `rdbss!RxPerProcessCountersEnabled` at `0x1400072e4`
- `rdbss!RxAttemptTurboIoCompletion` at `0x140007a9d`
- `rdbss!RxAttemptTurboIoCompletion` at `0x140007a9d`
- `rdbss!RxDiagnosticTrace` at `0x1400072a3`
- `rdbss!RxDiagnosticTrace` at `0x1400075e6`
- `rdbss!RxDiagnosticTrace` at `0x140007c15`
- `rdbss!RxDiagnosticTrace` at `0x1400072a3`
- `rdbss!RxDiagnosticTrace` at `0x1400075e6`
- `rdbss!RxDiagnosticTrace` at `0x140007c15`
- `rdbss!RxPostToWorkerThread` at `0x140008129`
- `rdbss!RxPostToWorkerThread` at `0x140008129`
- `rdbss!RxFreeMdlChain` at `0x14005c4ff`
- `rdbss!RxFreeMdlChain` at `0x14005c4ff`

## pseudocode

```c
__int64 __fastcall SmbCeReceiveInd(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        int a4,
        unsigned int *a5,
        __int64 a6,
        _QWORD **a7,
        _QWORD *a8,
        unsigned int *a9,
        __int64 a10)
{
  __int64 v10; // r12
  struct _EX_RUNDOWN_REF *v11; // rbx
  unsigned int v13; // edi
  unsigned int v15; // esi
  __int64 v16; // rdx
  __int64 v17; // r8
  ULONG_PTR v18; // r13
  __int64 v19; // rax
  __int64 v20; // rdi
  int v21; // eax
  unsigned __int16 v22; // r9
  unsigned int v23; // edx
  int v24; // r8d
  int v25; // ecx
  ULONG_PTR pContext; // rsi
  unsigned __int64 v27; // rdx
  char v28; // r9
  __int64 v29; // r8
  _QWORD *v30; // rbx
  _QWORD *v31; // r12
  unsigned int *v32; // r12
  __int64 v33; // r12
  __int64 v34; // rax
  signed __int32 v35; // r8d
  void *v36; // rcx
  bool v37; // zf
  int v38; // eax
  __int64 v39; // rdx
  __int64 v40; // rdx
  __int64 v41; // r8
  __int64 v42; // rax
  int v43; // eax
  unsigned int v44; // eax
  __int64 v45; // r12
  signed __int32 v46; // r9d
  unsigned int *v47; // rcx
  __int64 v48; // r12
  __int64 v49; // rax
  unsigned int v50; // eax
  __int64 v51; // rax
  int v52; // eax
  char v53; // cl
  int v54; // edx
  int v55; // ecx
  unsigned int v56; // r8d
  unsigned __int64 v57; // rax
  bool v58; // cl
  unsigned __int64 v59; // rcx
  __int64 v60; // r8
  __int64 v61; // r9
  __int64 v62; // r10
  __int64 v63; // r8
  __int64 v64; // rcx
  int v65; // edx
  int v66; // r8d
  int v67; // r9d
  int v68; // ecx
  int v69; // edx
  KIRQL v70; // di
  volatile LONG *v71; // rcx
  __int64 v72; // r9
  KIRQL v73; // al
  __int64 v74; // rcx
  KIRQL v75; // di
  __int64 v76; // rbx
  KIRQL v77; // al
  __int64 v78; // rcx
  KIRQL v79; // di
  int v80; // eax
  _QWORD *v81; // rax
  _QWORD *v82; // r8
  unsigned int v83; // edx
  unsigned int v84; // eax
  IRP *v85; // rbx
  int v86; // eax
  int v87; // ecx
  ULONG v88; // ecx
  unsigned int v89; // edx
  _QWORD *v90; // rcx
  _QWORD *j; // rdx
  int v92; // eax
  __int64 v93; // rcx
  __int64 v94; // rax
  __int64 v95; // rdx
  __int64 v96; // rcx
  int v97; // ecx
  int v98; // eax
  __int64 v99; // rax
  unsigned __int64 v100; // rcx
  unsigned __int64 v101; // rdx
  __int64 v102; // rax
  __int64 i; // rcx
  __int64 v104; // rdx
  __int64 v105; // rcx
  IRP *TopLevelIrp; // rax
  IRP *v107; // rcx
  unsigned int v108; // eax
  unsigned int v109; // r12d
  __int64 v110; // rdx
  __int64 v111; // rax
  __int64 (__fastcall *v112)(ULONG_PTR); // rax
  int v113; // ecx
  __int64 v114; // rax
  KIRQL v115; // al
  KIRQL v116; // di
  __int64 v117; // rdx
  __int64 v118; // rcx
  _QWORD *v119; // r8
  _QWORD *k; // rax
  __int64 v121; // rcx
  unsigned __int64 v122; // rax
  __int64 v123; // rax
  __int128 v125; // xmm0
  ADDRESS_FAMILY v126; // cx
  UCHAR v127; // al
  __int16 v128; // r8
  __int64 v129; // r10
  char v130; // r11
  bool v131; // cf
  int v132; // r8d
  __int128 v133; // xmm0
  __int128 v134; // xmm0
  ADDRESS_FAMILY v135; // cx
  __int128 v136; // xmm0
  ADDRESS_FAMILY v137; // cx
  __int16 v138; // r8
  __int64 v139; // r10
  char v140; // r11
  int v141; // r8d
  __int128 v142; // xmm0
  ADDRESS_FAMILY v143; // cx
  UCHAR v144; // al
  __int16 v145; // r8
  __int64 v146; // r10
  char v147; // r11
  int v148; // r8d
  __int128 v149; // xmm0
  __int128 v150; // xmm0
  ADDRESS_FAMILY v151; // cx
  __int128 v152; // xmm0
  ADDRESS_FAMILY v153; // cx
  UCHAR v154; // al
  __int16 v155; // r8
  __int64 v156; // r10
  char v157; // r11
  int v158; // r8d
  __int128 v159; // xmm0
  ADDRESS_FAMILY v160; // cx
  UCHAR v161; // al
  __int16 v162; // r8
  __int64 v163; // r10
  char v164; // r11
  int v165; // r8d
  __int128 v166; // xmm0
  __int128 v167; // xmm0
  ADDRESS_FAMILY v168; // cx
  __int128 v169; // xmm0
  ADDRESS_FAMILY v170; // cx
  __int16 v171; // r8
  __int64 v172; // r10
  char v173; // r11
  int v174; // r8d
  volatile LONG *v175; // rcx
  volatile LONG *v176; // rcx
  ULONG v177; // eax
  IRP *Mdl; // rax
  PIRP *v179; // rcx
  int v180; // [rsp+38h] [rbp-128h]
  PIRP v181[2]; // [rsp+E0h] [rbp-80h] BYREF
  char v182; // [rsp+F0h] [rbp-70h]
  char v183; // [rsp+F1h] [rbp-6Fh]
  char v184; // [rsp+F2h] [rbp-6Eh]
  KIRQL v185; // [rsp+F3h] [rbp-6Dh]
  char v186; // [rsp+F4h] [rbp-6Ch]
  __int128 v187; // [rsp+F8h] [rbp-68h] BYREF
  __int128 v188; // [rsp+108h] [rbp-58h]
  const char *v189; // [rsp+118h] [rbp-48h]
  __int64 v190; // [rsp+120h] [rbp-40h]
  __int128 v191; // [rsp+130h] [rbp-30h] BYREF
  __int128 v192; // [rsp+140h] [rbp-20h] BYREF
  int v193; // [rsp+150h] [rbp-10h]
  __int64 v194; // [rsp+158h] [rbp-8h]
  PIRP Irp; // [rsp+160h] [rbp+0h]
  __int128 v196; // [rsp+170h] [rbp+10h] BYREF
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+180h] [rbp+20h] BYREF
  __int128 v198; // [rsp+1A0h] [rbp+40h] BYREF
  __int128 v199; // [rsp+1B0h] [rbp+50h] BYREF
  PEX_RUNDOWN_REF RunRef; // [rsp+1C0h] [rbp+60h]
  __int128 v201[4]; // [rsp+1D0h] [rbp+70h] BYREF
  char v202; // [rsp+220h] [rbp+C0h]
  int v203; // [rsp+220h] [rbp+C0h]
  __int64 v204; // [rsp+220h] [rbp+C0h]
  __int64 v205; // [rsp+220h] [rbp+C0h]
  int v206; // [rsp+220h] [rbp+C0h]
  ULONG v207; // [rsp+220h] [rbp+C0h]
  unsigned int v208; // [rsp+228h] [rbp+C8h]
  ULONG v210; // [rsp+248h] [rbp+E8h]

  v208 = a2;
  v10 = *(_QWORD *)(a1 + 24);
  v11 = (struct _EX_RUNDOWN_REF *)(a1 + 496);
  v190 = v10;
  RunRef = (PEX_RUNDOWN_REF)(a1 + 496);
  v189 = 0;
  v13 = 0;
  *(_QWORD *)&v191 = 0;
  v15 = a2;
  v187 = 0;
  v188 = 0;
  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( !ExAcquireRundownProtection((PEX_RUNDOWN_REF)(a1 + 496)) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_1ffd7df1a0ca364e8ae776b5c429ef78_Traceguids, a1);
    }
    v32 = a5;
    goto LABEL_87;
  }
  v18 = *(_QWORD *)(a1 + 504);
  if ( v18 )
  {
    v186 = 0;
  }
  else
  {
    v115 = SmbCeAcquireSpinLock(v10, v16, v17);
    v116 = v115;
    v117 = *(_QWORD *)(a1 + 520);
    if ( v117 == a1 + 520 || v117 == 416 || (v118 = *(_QWORD *)(v117 - 416 + 384)) == 0 )
    {
      *(_DWORD *)(v10 + 2352) = -1;
      ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(v10 + 1920), v115);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_1ffd7df1a0ca364e8ae776b5c429ef78_Traceguids, a1);
      }
      v13 = 0;
      ExReleaseRundownProtection(v11);
      v32 = a5;
      goto LABEL_87;
    }
    if ( *(_WORD *)v118 == 0xE200 )
    {
      v18 = *(_QWORD *)(v117 - 416 + 384);
    }
    else
    {
      v18 = 0;
      if ( *(_WORD *)v118 == 0xE202 )
        v18 = *(_QWORD *)(v118 + 384);
    }
    SmbCeReferenceServerEntry(v18);
    v186 = 1;
    *(_DWORD *)(v10 + 2352) = -1;
    ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(v10 + 1920), v116);
  }
  v19 = *(_QWORD *)(v18 + 192);
  Irp = 0;
  v20 = *(_QWORD *)(a1 + 512);
  v21 = (*(__int64 (__fastcall **)(ULONG_PTR, __int64, _QWORD, _QWORD, __int128 *))(v19 + 32))(v18, a6, v15, a3, &v187);
  if ( v21 == -1073741802 )
  {
    v122 = *(_QWORD *)(v20 + 64);
    v22 = 1;
    WORD6(v188) = 1;
    v24 = 0;
    v25 = 0;
    v187 = v122;
    v23 = 0;
    DWORD2(v188) = 0;
    *(_QWORD *)&v188 = 0;
    BYTE14(v188) = 0;
    v189 = "NEG_MP  ";
    v182 = 1;
  }
  else
  {
    v182 = 0;
    if ( v21 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_1ffd7df1a0ca364e8ae776b5c429ef78_Traceguids, a1);
      }
      v32 = a5;
      v13 = 0;
      goto LABEL_82;
    }
    v22 = WORD6(v188);
    v23 = DWORD2(v188);
    v24 = DWORD1(v188);
    v25 = v188;
  }
  if ( (*(_BYTE *)(v18 + 764) & 1) == 0 )
    v25 = v24;
  LODWORD(v188) = v25;
  if ( v23 )
  {
    a3 = v23;
    if ( v15 >= v23 )
    {
      v15 = v23;
      v208 = v23;
    }
  }
  _InterlockedAdd((volatile signed __int32 *)(v20 + 88), v22);
  if ( (*(unsigned int (__fastcall **)(ULONG_PTR, __int64, _QWORD, _QWORD, __int128 *))(*(_QWORD *)(v18 + 192) + 40LL))(
         v18,
         a6,
         v15,
         a3,
         &v187) != -1073741802 )
  {
    v32 = a5;
    v13 = 0;
    goto LABEL_82;
  }
  pContext = 0;
  LOBYTE(v193) = 0;
  v183 = 0;
  v185 = KfRaiseIrql(2u);
  while ( 1 )
  {
    KeAcquireInStackQueuedSpinLockAtDpcLevel((PKSPIN_LOCK)(v20 + 256), &LockHandle);
    v28 = 1;
    v202 = 1;
    v29 = v187;
    if ( (unsigned __int64)v187 < *(_QWORD *)(v20 + 64) || (unsigned __int64)v187 >= *(_QWORD *)(v20 + 72) )
    {
      v31 = 0;
      v30 = 0;
      *(_QWORD *)&v196 = 0;
LABEL_15:
      if ( BYTE14(v188) )
        goto LABEL_23;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_iq(WPP_GLOBAL_Control->AttachedDevice, v27, v187, v187, a1);
      }
      v32 = a5;
      v13 = 0;
      *a5 = a3;
      KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
      goto LABEL_138;
    }
    v27 = (unsigned __int64)v187 % *(unsigned int *)(v20 + 96);
    v30 = *(_QWORD **)(*(_QWORD *)(v20 + 104) + 8 * v27);
    *(_QWORD *)&v196 = v30;
    v31 = v30;
    if ( !v30 )
      goto LABEL_15;
    v33 = v30[7];
    v34 = *(_QWORD *)(v33 + 56);
    v181[0] = (PIRP)v34;
    if ( !v34 )
      break;
    if ( KeTryToAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(v34 + 8)) )
    {
      _InterlockedIncrement((volatile signed __int32 *)(&v181[0]->Size + 1));
      goto LABEL_22;
    }
LABEL_266:
    KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
  }
  if ( !KeTryToAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(v33 + 24)) )
    goto LABEL_266;
  v35 = _InterlockedIncrement((volatile signed __int32 *)(v33 + 4));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qDD(
      WPP_GLOBAL_Control->AttachedDevice,
      33,
      WPP_d39beb3e593835eae73483c3886eb046_Traceguids,
      v33,
      v35 - 1,
      v35);
  }
LABEL_22:
  _InterlockedIncrement((volatile signed __int32 *)(v30[7] + 36LL));
  v36 = *(void **)(a1 + 512);
  v183 = 1;
  SmbCseDissociateMidFromBufferContextLite(v36);
  v28 = 1;
  v29 = v187;
  v31 = v30;
LABEL_23:
  v37 = *(_DWORD *)(a1 + 320) == 2;
  v184 = 1;
  if ( !v37 )
  {
    if ( !v31 )
      goto LABEL_28;
    if ( v31[105] )
    {
      v56 = *(_DWORD *)(v20 + 80);
      if ( v56 < 8 )
        v56 = 8;
      v57 = (*(_QWORD *)(a1 + 304) * v56 + (MEMORY[0xFFFFF78000000008] - v31[105]) / 0xAuLL)
          / (*((_DWORD *)v31 + 20) + v56);
      v29 = v187;
      *(_QWORD *)(a1 + 304) = v57;
    }
    v58 = (*(_BYTE *)(v18 + 765) & 1) != 0 || *(_DWORD *)(a1 + 320) == 2 || (*(_BYTE *)(v18 + 736) & 1) != 0;
    if ( (byte_14007D0C0 & 2) != 0 || v58 )
    {
      *(_DWORD *)(v20 + 144) = *(_DWORD *)(v20 + 96);
    }
    else
    {
      v59 = v31[5];
      if ( v59 < *(_QWORD *)(v20 + 136) )
        goto LABEL_26;
      v60 = *(_QWORD *)(a1 + 280);
      v61 = *(_QWORD *)(a1 + 304);
      v62 = (unsigned int)dword_14007D08C;
      *(_QWORD *)(v20 + 136) = *(_QWORD *)(v20 + 72);
      if ( v60 )
      {
        if ( v60 >= 500000 )
          goto LABEL_110;
        goto LABEL_170;
      }
      if ( v59 >= 0x32 )
      {
LABEL_170:
        v60 = 500000;
LABEL_110:
        v63 = 2 * v61 / v60;
        if ( (int)v63 > 17 || v61 > 1000000 * v62 / 6 )
          LODWORD(v63) = 17;
        v64 = 3LL * (int)v63;
        v65 = *((_DWORD *)qword_1400702E0 + 3 * (int)v63);
        v66 = *((_DWORD *)qword_1400702E0 + 3 * (int)v63 + 1);
        v67 = *((_DWORD *)&qword_1400702E0[1] + v64);
        v68 = 2;
        if ( *(_DWORD *)(v20 + 144) > 2u )
          v68 = *(_DWORD *)(v20 + 144);
        if ( v65 )
        {
          if ( v65 == 1 )
            v68 += v66 - v67;
        }
        else
        {
          v68 = v68 * v66 / v67;
        }
        v69 = *(_DWORD *)(v20 + 96);
        if ( v68 <= 2 )
          v68 = 2;
        if ( v68 <= v69 )
          v69 = v68;
        if ( v69 > dbgRestrictWindowSize )
          v69 = dbgRestrictWindowSize;
        if ( v69 <= dbgWindowSizeThresholdLo )
          __debugbreak();
        *(_DWORD *)(v20 + 144) = v69;
      }
    }
LABEL_25:
    v29 = v187;
LABEL_26:
    if ( BYTE14(v188) && DWORD1(v188) == 259 )
    {
      pContext = v31[7];
      v180 = *(_DWORD *)(a6 + 8);
      v194 = *(_QWORD *)(pContext + 56);
      RxDiagnosticTrace(
        *(_QWORD *)(v20 + 16),
        1,
        "RECV: [%s] (Mid/[AsyncId]) (%I64x/[%lx]) Creds %lx Status %lx",
        v189,
        v29,
        DWORD2(v187),
        WORD6(v188),
        v180);
      v93 = *((_QWORD *)&v187 + 1);
      v94 = *(_QWORD *)(a1 + 512);
      *((_DWORD *)v31 + 1) |= 2u;
      v31[5] = v93;
      v95 = 16LL * ((unsigned __int8)v93 >> 2) + *(_QWORD *)(v94 + 112);
      v96 = *(_QWORD *)v95;
      if ( *(_QWORD *)(*(_QWORD *)v95 + 8LL) != v95 )
        __fastfail(3u);
      v31[3] = v96;
      v31[4] = v95;
      *(_QWORD *)(v96 + 8) = v31 + 3;
      *(_QWORD *)v95 = v31 + 3;
      KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
      v97 = a10;
      if ( a10 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          v181[1] = (PIRP)16;
          v181[0] = (PIRP)(a10 + 32);
          v133 = *(_OWORD *)v181;
          v181[1] = (PIRP)16;
          v181[0] = (PIRP)(a10 + 16);
          v192 = v133;
          v134 = *(_OWORD *)v181;
          v181[1] = 0;
          v181[0] = (PIRP)(a1 + 428);
          v135 = *(_WORD *)(a1 + 428);
          v196 = v134;
          v181[1] = (PIRP)SOCKADDR_SIZE(v135);
          v136 = *(_OWORD *)v181;
          v181[1] = 0;
          v181[0] = (PIRP)(a1 + 400);
          v137 = *(_WORD *)(a1 + 400);
          v191 = v136;
          v181[1] = (PIRP)SOCKADDR_SIZE(v137);
          v140 = 69;
          if ( (v138 & 0x8000) == 0 )
            v140 = 32;
          v131 = (v138 & 0x1000) != 0;
          v141 = 83;
          if ( !v131 )
            v141 = 32;
          WPP_SF_d_SOCKADDR__SOCKADDR_ccsDDiDDDLqqqqqqLqq_zb__zb_(
            *(_QWORD *)(v139 + 24),
            WORD6(v188),
            v141,
            *(unsigned __int8 *)(*(_QWORD *)(*(_QWORD *)(pContext + 72) + 24LL) + 1312LL),
            (__int64)v181,
            (__int64)&v191,
            v141,
            v140,
            (__int64)v189,
            v208,
            a3,
            v187,
            *((_DWORD *)v31 + 20),
            SBYTE12(v188),
            SBYTE8(v187),
            *(_DWORD *)(a6 + 8),
            pContext,
            (char)v31,
            *(_QWORD *)(pContext + 48),
            a1,
            *(_QWORD *)(pContext + 96),
            *(_QWORD *)(pContext + 80),
            *(_DWORD *)(a6 + 36),
            *(_QWORD *)(pContext + 88),
            v18,
            (__int64)&v196,
            (__int64)&v192);
        }
      }
      else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
             && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
             && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v181[1] = 0;
        v181[0] = (PIRP)(a1 + 428);
        v181[1] = (PIRP)SOCKADDR_SIZE(*(_WORD *)(a1 + 428));
        v125 = *(_OWORD *)v181;
        v181[1] = 0;
        v181[0] = (PIRP)(a1 + 400);
        v126 = *(_WORD *)(a1 + 400);
        v192 = v125;
        v127 = SOCKADDR_SIZE(v126);
        v130 = 69;
        v181[1] = (PIRP)v127;
        if ( (v128 & 0x8000) == 0 )
          v130 = 32;
        v131 = (v128 & 0x1000) != 0;
        v132 = 83;
        if ( !v131 )
          v132 = 32;
        WPP_SF_d_SOCKADDR__SOCKADDR_ccsDDiDDDLqqqqqqLqq(
          *(_QWORD *)(v129 + 24),
          WORD6(v188),
          v132,
          *(unsigned __int8 *)(*(_QWORD *)(*(_QWORD *)(pContext + 72) + 24LL) + 1312LL),
          (__int64)v181,
          (__int64)&v192,
          v132,
          v130,
          (__int64)v189,
          v208,
          a3,
          v187,
          *((_DWORD *)v31 + 20),
          SBYTE12(v188),
          SBYTE8(v187),
          *(_DWORD *)(a6 + 8),
          pContext,
          (char)v31,
          *(_QWORD *)(pContext + 48),
          a1,
          *(_QWORD *)(pContext + 96),
          *(_QWORD *)(pContext + 80),
          *(_DWORD *)(a6 + 36),
          *(_QWORD *)(pContext + 88),
          v18);
      }
      if ( (byte_1400712C1 & 1) != 0 )
        McTemplateK0sxxxqhqp_EtwWriteTransfer(
          v97,
          (unsigned int)SmbReceiveInterim,
          pContext + 312,
          (_DWORD)v189,
          v187,
          SBYTE8(v187),
          *(_QWORD *)(a6 + 40),
          *(_DWORD *)(a6 + 36),
          SBYTE12(v188),
          0,
          *(_QWORD *)(*(_QWORD *)(pContext + 96) + 392LL));
      v13 = 0;
      if ( (*(_DWORD *)(pContext + 68) & 0x40) != 0 )
      {
        *(_QWORD *)(pContext + 208) = 0x7FFFFFFFFFFFFFFFLL;
LABEL_158:
        v53 = 0;
        goto LABEL_75;
      }
      v98 = dword_14007D08C;
      if ( *(_DWORD *)(*(_QWORD *)(pContext + 72) + 768LL) )
        v98 = *(_DWORD *)(*(_QWORD *)(pContext + 72) + 768LL);
      if ( *(_DWORD *)(pContext + 216) )
      {
        v99 = *(unsigned int *)(pContext + 216);
      }
      else if ( dword_14007D090 )
      {
        v99 = (unsigned int)dword_14007D090;
      }
      else
      {
        v99 = (unsigned int)(4 * v98);
      }
      v100 = *(_QWORD *)(pContext + 208);
      v101 = 10000000 * v99 + MEMORY[0xFFFFF78000000008];
      if ( v101 <= v100 && v100 != 0x7FFFFFFFFFFFFFFFLL )
        goto LABEL_158;
      *(_QWORD *)(pContext + 208) = v101;
      v53 = 0;
LABEL_75:
      if ( (!v183 || _InterlockedExchangeAdd((volatile signed __int32 *)(pContext + 36), 0xFFFFFFFF) == 1)
        && v53
        && (unsigned __int8)SmbCepCheckExchangeForDeferredAbortOrIfFinalizable(pContext) )
      {
        v72 = *(_QWORD *)(pContext + 48);
        if ( (*(_DWORD *)(pContext + 68) & 0x100000) == 0 )
        {
          Irp = 0;
          goto LABEL_161;
        }
        v85 = 0;
        Irp = 0;
        if ( !*(_QWORD *)(pContext + 56) && !*(_DWORD *)(pContext + 16) )
        {
          for ( i = *(_QWORD *)(pContext + 160); ; i = *(_QWORD *)(v104 + 8) )
          {
            v104 = 0;
            if ( i != pContext + 160 )
              v104 = i - 8;
            if ( !v104 )
            {
              v85 = (IRP *)RxAttemptTurboIoCompletion(v72, SmbCepPrepareExchangeForTurboCompletionLite, pContext);
              Irp = v85;
              goto LABEL_160;
            }
            if ( *(_DWORD *)(v104 + 48) )
              break;
          }
          Irp = 0;
          goto LABEL_161;
        }
LABEL_160:
        if ( !v85 )
        {
LABEL_161:
          v86 = SmbCepCompleteExchangeLiteEx((PVOID)pContext);
          v87 = (unsigned __int8)v193;
          if ( v86 == -1073741802 )
            v87 = 1;
          v193 = v87;
        }
      }
      if ( v184 )
      {
        v76 = v194;
        if ( v194 )
        {
          KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(v194 + 8));
          SmbCseDereferenceCompoundingKey(v76);
        }
        else
        {
          KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(pContext + 24));
          SmbCeDereferenceExchange((PVOID)pContext);
        }
        v32 = a5;
        goto LABEL_138;
      }
      if ( v194 )
      {
        SmbCeReleaseCompoundingKeyLock(v194);
      }
      else
      {
        KeReleaseSpinLock((PKSPIN_LOCK)(pContext + 24), *(_BYTE *)(pContext + 32));
        SmbCeDereferenceExchange((PVOID)pContext);
      }
      v32 = a5;
      goto LABEL_81;
    }
    KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
LABEL_31:
    pContext = v30[7];
    v38 = 0;
    v39 = *(_QWORD *)(pContext + 56);
    v194 = v39;
    *((_DWORD *)v30 + 184) = a3;
    *((_BYTE *)v30 + 85) = 0;
    if ( a10 )
    {
      v38 = *(_DWORD *)a10;
      if ( *(int *)a10 < 0 )
      {
        *((_DWORD *)v30 + 195) = a4;
        *((_BYTE *)v30 + 786) = 1;
      }
    }
    if ( (v30[109] & 0x40000000) != 0 && (v38 & 0x10000000) == 0 )
    {
      v13 = -1073700864;
      *(_QWORD *)&v191 = 3221266432LL;
      SmbCseUpdateBufferContextStatus(v30, 3221266432LL);
      if ( (byte_1400712C4 & 2) != 0 )
        McTemplateK0hxxqhzr4qhzr7qqqbr11qbr13_EtwWriteTransfer(
          a6,
          (MEMORY[0xFFFFF78000000008] - *(_QWORD *)(pContext + 200)) / 0x2710uLL,
          *(_WORD *)(v190 + 360) >> 1,
          *(unsigned __int16 *)(a6 + 12),
          v187,
          *(_QWORD *)(a6 + 40),
          *(_DWORD *)(a6 + 36),
          *(_WORD *)(v18 + 80) >> 1,
          *(_QWORD *)(v18 + 88));
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_qq(
          WPP_GLOBAL_Control->AttachedDevice,
          17,
          WPP_1ffd7df1a0ca364e8ae776b5c429ef78_Traceguids,
          v30,
          pContext);
      }
      v80 = SmbCseInvalidateMemoryRegistrationAsync(v30);
      if ( v80 != -1073741816 )
      {
        v53 = 1;
        if ( v80 != 259 )
          *((_BYTE *)v30 + 87) = 0;
        goto LABEL_75;
      }
      goto LABEL_74;
    }
    if ( v39 )
    {
      KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(v39 + 8));
      SmbCseDereferenceCompoundingKey(v194);
    }
    else
    {
      KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(pContext + 24));
      SmbCeDereferenceExchange((PVOID)pContext);
    }
    KeLowerIrql(v185);
    v184 = 0;
    if ( BYTE14(v188) )
    {
      if ( a10 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          v181[1] = (PIRP)16;
          v181[0] = (PIRP)(a10 + 32);
          v149 = *(_OWORD *)v181;
          v181[1] = (PIRP)16;
          v181[0] = (PIRP)(a10 + 16);
          v192 = v149;
          v150 = *(_OWORD *)v181;
          v181[1] = 0;
          v181[0] = (PIRP)(a1 + 428);
          v151 = *(_WORD *)(a1 + 428);
          v198 = v150;
          v181[1] = (PIRP)SOCKADDR_SIZE(v151);
          v152 = *(_OWORD *)v181;
          v181[1] = 0;
          v181[0] = (PIRP)(a1 + 400);
          v153 = *(_WORD *)(a1 + 400);
          v199 = v152;
          v154 = SOCKADDR_SIZE(v153);
          v181[1] = (PIRP)v154;
          v157 = 69;
          if ( (v155 & 0x8000) == 0 )
            v157 = 32;
          v131 = (v155 & 0x1000) != 0;
          v158 = 83;
          if ( !v131 )
            v158 = 32;
          WPP_SF_d_SOCKADDR__SOCKADDR_ccsDDDLqqqqqiqLqq_zb__zb_(
            *(_QWORD *)(v156 + 24),
            v154,
            v158,
            *(unsigned __int8 *)(*(_QWORD *)(*(_QWORD *)(pContext + 72) + 24LL) + 1312LL),
            (__int64)v181,
            (__int64)&v199,
            v158,
            v157,
            (__int64)v189,
            v208,
            a3,
            SBYTE8(v187),
            SBYTE4(v188),
            pContext,
            (char)v30,
            *(_QWORD *)(pContext + 48),
            a1,
            *(_QWORD *)(pContext + 96),
            *(_QWORD *)(a6 + 40),
            *(_QWORD *)(pContext + 80),
            *(_DWORD *)(a6 + 36),
            *(_QWORD *)(pContext + 88),
            v18,
            (__int64)&v198,
            (__int64)&v192);
        }
      }
      else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
             && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
             && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v181[1] = 0;
        v181[0] = (PIRP)(a1 + 428);
        v181[1] = (PIRP)SOCKADDR_SIZE(*(_WORD *)(a1 + 428));
        v142 = *(_OWORD *)v181;
        v181[1] = 0;
        v181[0] = (PIRP)(a1 + 400);
        v143 = *(_WORD *)(a1 + 400);
        v192 = v142;
        v144 = SOCKADDR_SIZE(v143);
        v147 = 69;
        v181[1] = (PIRP)v144;
        if ( (v145 & 0x8000) == 0 )
          v147 = 32;
        v131 = (v145 & 0x1000) != 0;
        v148 = 83;
        if ( !v131 )
          v148 = 32;
        WPP_SF_d_SOCKADDR__SOCKADDR_ccsDDDLqqqqqiqLqq(
          *(_QWORD *)(v146 + 24),
          v144,
          v148,
          *(unsigned __int8 *)(*(_QWORD *)(*(_QWORD *)(pContext + 72) + 24LL) + 1312LL),
          (__int64)v181,
          (__int64)&v192,
          v148,
          v147,
          (__int64)v189,
          v208,
          a3,
          SBYTE8(v187),
          SBYTE4(v188),
          pContext,
          (char)v30,
          *(_QWORD *)(pContext + 48),
          a1,
          *(_QWORD *)(pContext + 96),
          *(_QWORD *)(a6 + 40),
          *(_QWORD *)(pContext + 80),
          *(_DWORD *)(a6 + 36),
          *(_QWORD *)(pContext + 88),
          v18);
      }
      RxDiagnosticTrace(
        *(_QWORD *)(v20 + 16),
        1,
        "RECV: [%s] ([AsyncId]) ([%lx]) Creds %lx Status %lx",
        v189,
        DWORD2(v187),
        WORD6(v188),
        DWORD1(v188));
      if ( (byte_1400712C1 & 1) != 0 )
        McTemplateK0sxxxqhqp_EtwWriteTransfer(
          a6,
          (unsigned int)SmbReceiveAsync,
          pContext + 312,
          (_DWORD)v189,
          v187,
          SBYTE8(v187),
          *(_QWORD *)(a6 + 40),
          *(_DWORD *)(a6 + 36),
          SBYTE12(v188),
          0,
          *(_QWORD *)(*(_QWORD *)(pContext + 96) + 392LL));
    }
    else
    {
      if ( (_DWORD)v188 == 259 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_1ffd7df1a0ca364e8ae776b5c429ef78_Traceguids, 259);
        }
        LODWORD(v188) = -1073741629;
      }
      if ( a10 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          if ( v182 )
          {
            v123 = 0;
            LOBYTE(v206) = 0;
          }
          else
          {
            v123 = *(_QWORD *)(a6 + 40);
            v206 = *(_DWORD *)(a6 + 36);
          }
          *(_QWORD *)&v192 = v123;
          v181[1] = (PIRP)16;
          v181[0] = (PIRP)(a10 + 32);
          v166 = *(_OWORD *)v181;
          v181[1] = (PIRP)16;
          v181[0] = (PIRP)(a10 + 16);
          v199 = v166;
          v167 = *(_OWORD *)v181;
          v181[1] = 0;
          v181[0] = (PIRP)(a1 + 428);
          v168 = *(_WORD *)(a1 + 428);
          v198 = v167;
          v181[1] = (PIRP)SOCKADDR_SIZE(v168);
          v169 = *(_OWORD *)v181;
          v181[1] = 0;
          v181[0] = (PIRP)(a1 + 400);
          v170 = *(_WORD *)(a1 + 400);
          v201[0] = v169;
          v181[1] = (PIRP)SOCKADDR_SIZE(v170);
          v173 = 69;
          if ( (v171 & 0x8000) == 0 )
            v173 = 32;
          v131 = (v171 & 0x1000) != 0;
          v174 = 83;
          if ( !v131 )
            v174 = 32;
          WPP_SF_d_SOCKADDR__SOCKADDR_ccsDDiDDLqqqqqiqLqq_zb__zb_(
            *(_QWORD *)(v172 + 24),
            WORD6(v188),
            v174,
            *(unsigned __int8 *)(*(_QWORD *)(*(_QWORD *)(pContext + 72) + 24LL) + 1312LL),
            (__int64)v181,
            (__int64)v201,
            v174,
            v173,
            (__int64)v189,
            v208,
            a3,
            v187,
            *((_DWORD *)v30 + 20),
            SBYTE12(v188),
            SBYTE4(v188),
            pContext,
            (char)v30,
            *(_QWORD *)(pContext + 48),
            a1,
            *(_QWORD *)(pContext + 96),
            v192,
            *(_QWORD *)(pContext + 80),
            v206,
            *(_QWORD *)(pContext + 88),
            v18,
            (__int64)&v198,
            (__int64)&v199);
        }
      }
      else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
             && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
             && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        if ( v182 )
        {
          v102 = 0;
          LOBYTE(v203) = 0;
        }
        else
        {
          v102 = *(_QWORD *)(a6 + 40);
          v203 = *(_DWORD *)(a6 + 36);
        }
        *(_QWORD *)&v192 = v102;
        v181[1] = 0;
        v181[0] = (PIRP)(a1 + 428);
        v181[1] = (PIRP)SOCKADDR_SIZE(*(_WORD *)(a1 + 428));
        v159 = *(_OWORD *)v181;
        v181[1] = 0;
        v181[0] = (PIRP)(a1 + 400);
        v160 = *(_WORD *)(a1 + 400);
        v199 = v159;
        v161 = SOCKADDR_SIZE(v160);
        v164 = 69;
        v181[1] = (PIRP)v161;
        if ( (v162 & 0x8000) == 0 )
          v164 = 32;
        v131 = (v162 & 0x1000) != 0;
        v198 = *(_OWORD *)v181;
        v165 = 83;
        if ( !v131 )
          v165 = 32;
        WPP_SF_d_SOCKADDR__SOCKADDR_ccsDDiDDLqqqqqiqLqq(
          *(_QWORD *)(v163 + 24),
          WORD6(v188),
          v165,
          *(unsigned __int8 *)(*(_QWORD *)(*(_QWORD *)(pContext + 72) + 24LL) + 1312LL),
          (__int64)&v198,
          (__int64)&v199,
          v165,
          v164,
          (__int64)v189,
          v208,
          a3,
          v187,
          *((_DWORD *)v30 + 20),
          SBYTE12(v188),
          SBYTE4(v188),
          pContext,
          (char)v30,
          *(_QWORD *)(pContext + 48),
          a1,
          *(_QWORD *)(pContext + 96),
          v192,
          *(_QWORD *)(pContext + 80),
          v203,
          *(_QWORD *)(pContext + 88),
          v18);
      }
      RxDiagnosticTrace(
        *(_QWORD *)(v20 + 16),
        1,
        "RECV: [%s] (Mid) (%I64x) Creds %lx Status %lx",
        v189,
        (_QWORD)v187,
        WORD6(v188),
        DWORD1(v188));
      if ( (byte_1400712C1 & 1) != 0 )
      {
        if ( v182 )
        {
          LOBYTE(v54) = 0;
          v55 = 0;
        }
        else
        {
          v54 = *(_DWORD *)(a6 + 36);
          v55 = *(_DWORD *)(a6 + 40);
        }
        McTemplateK0sxxxqhqp_EtwWriteTransfer(
          v55,
          (unsigned int)SmbReceive,
          pContext + 312,
          (_DWORD)v189,
          v187,
          SBYTE8(v187),
          v55,
          v54,
          SBYTE12(v188),
          SBYTE4(v188),
          *(_QWORD *)(*(_QWORD *)(pContext + 96) + 392LL));
      }
    }
    _InterlockedAdd64(
      (volatile signed __int64 *)MRxSmbLegacyPerfCtrs + 32 * (unsigned __int64)HIDWORD(KeGetPcr()[1].LockArray),
      a3);
    if ( (unsigned __int8)RxPerProcessCountersEnabled() )
    {
      v42 = *(_QWORD *)(pContext + 48);
      if ( v42 && *(int *)(v42 + 120) >= 0 )
      {
        if ( *(_DWORD *)(a1 + 372) )
          _InterlockedAdd(
            (volatile signed __int32 *)(*(_QWORD *)(pContext + 48) + 196LL),
            _InterlockedExchange((volatile __int32 *)(a1 + 372), 0));
        _InterlockedAdd((volatile signed __int32 *)(*(_QWORD *)(pContext + 48) + 196LL), a3);
      }
      else
      {
        _InterlockedAdd((volatile signed __int32 *)(a1 + 372), a3);
      }
    }
    v43 = v188;
    if ( *(_QWORD *)(pContext + 80) && (_DWORD)v188 == -1073741309 )
    {
      v77 = SmbCeAcquireSpinLock(v190, v40, v41);
      v78 = *(_QWORD *)(pContext + 80);
      v79 = v77;
      if ( *(_DWORD *)(pContext + 108) == *(_DWORD *)(v78 + 264) )
      {
        *(_QWORD *)&v191 = (unsigned int)v188;
        SmbCeDisconnectSessionEntryLite(v78, 0, (unsigned int)v188);
      }
      v175 = (volatile LONG *)(v190 + 1920);
      *(_DWORD *)(v190 + 2352) = -1;
      ExReleaseSpinLockExclusive(v175, v79);
      v43 = v188;
    }
    if ( *(_QWORD *)(pContext + 88) && (v43 == -1073741623 || v43 == -1073741620) )
    {
      v73 = SmbCeAcquireSpinLock(v190, v40, v41);
      v74 = *(_QWORD *)(pContext + 88);
      v75 = v73;
      if ( *(_DWORD *)(pContext + 112) == *(_DWORD *)(v74 + 264) )
      {
        *(_QWORD *)&v191 = (unsigned int)v188;
        SmbCeDisconnectVNetRootContextLite(v74, 0, (unsigned int)v188);
      }
      v176 = (volatile LONG *)(v190 + 1920);
      *(_DWORD *)(v190 + 2352) = -1;
      ExReleaseSpinLockExclusive(v176, v75);
      v43 = v188;
    }
    if ( *(_QWORD *)(pContext + 80) && v43 == -1073740964 )
    {
      v70 = SmbCeAcquireSpinLock(v190, v40, v41);
      SmbCeRecoverSessionEntryLite(*(_QWORD *)(pContext + 80), (unsigned int)v188);
      v71 = (volatile LONG *)(v190 + 1920);
      *(_DWORD *)(v190 + 2352) = -1;
      ExReleaseSpinLockExclusive(v71, v70);
    }
    v44 = (*(__int64 (__fastcall **)(ULONG_PTR, _QWORD *, __int128 *, _QWORD, unsigned int, unsigned int *, __int64, __int64))(*(_QWORD *)(pContext + 232) + 8LL))(
            pContext,
            v30,
            &v187,
            v208,
            a3,
            a5,
            a6,
            a10);
    v45 = v194;
    v13 = v44;
    if ( v194 )
    {
      _InterlockedIncrement((volatile signed __int32 *)(v194 + 4));
      *(_BYTE *)(v45 + 16) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v45 + 8));
    }
    else
    {
      v46 = _InterlockedIncrement((volatile signed __int32 *)(pContext + 4));
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_qDD(
          WPP_GLOBAL_Control->AttachedDevice,
          33,
          WPP_d39beb3e593835eae73483c3886eb046_Traceguids,
          pContext,
          v46 - 1,
          v46);
      }
      *(_BYTE *)(pContext + 32) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(pContext + 24));
    }
    v47 = a5;
    if ( v13 != -1073741802 )
    {
      *((_DWORD *)v30 + 1) |= 0x400u;
      *a5 = a3;
    }
    *((_DWORD *)v30 + 185) = *a5;
    v48 = _InterlockedExchange64(v30 + 95, 0);
    if ( !v48 )
    {
LABEL_58:
      *a9 = 0;
      v49 = v30[94];
      if ( v49 )
      {
        v50 = *(_DWORD *)(v49 + 40);
      }
      else
      {
        if ( !v30[90] )
        {
LABEL_62:
          if ( *v47 > a3 )
            *v47 = a3;
          if ( *a9 > a3 )
            *a9 = a3;
          v51 = *(_QWORD *)(v18 + 56);
          if ( v51 )
          {
            v52 = (*(__int64 (__fastcall **)(_QWORD *, __int128 *, __int64, _QWORD, unsigned int, unsigned int *))(v51 + 880))(
                    v30,
                    &v187,
                    a6,
                    v208,
                    a3,
                    v47);
            if ( v52 != -1073741822 && v52 != -1073741802 && v52 < 0 )
            {
              *(_QWORD *)&v191 = (unsigned int)v52;
              SmbCseUpdateBufferContextStatus(v30, (unsigned int)v52);
              v13 = 0;
              *a5 = a3;
              goto LABEL_72;
            }
            v47 = a5;
          }
          if ( v13 != -1073741802 )
          {
LABEL_72:
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              WPP_SF_LLL(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_1ffd7df1a0ca364e8ae776b5c429ef78_Traceguids);
            }
            goto LABEL_74;
          }
          v81 = (_QWORD *)v30[94];
          if ( !v81 )
            v81 = (_QWORD *)v30[90];
          v82 = a7;
          *a7 = v81;
          v83 = a3 - *v47;
          v84 = *a9;
          if ( *a9 >= v83 )
          {
            *a9 = v83;
LABEL_156:
            ++*((_BYTE *)v30 + 87);
            *a8 = v30;
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
              || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
            {
              goto LABEL_158;
            }
            WPP_SF_qLqL(
              WPP_GLOBAL_Control->AttachedDevice,
              24,
              (unsigned int)WPP_1ffd7df1a0ca364e8ae776b5c429ef78_Traceguids,
              (_DWORD)v30,
              *v47,
              *v82,
              *a9);
            v53 = 0;
            goto LABEL_75;
          }
          LODWORD(v190) = v83 - v84;
          v88 = v83 - v84;
          *(_QWORD *)&v192 = 0;
          *(_QWORD *)&v196 = 0;
          v89 = 0x2000;
          while ( 1 )
          {
            v210 = v88;
            if ( !v88 )
            {
              v82 = a7;
              v90 = *a7;
              for ( j = (_QWORD *)**a7; j; j = (_QWORD *)*j )
                v90 = j;
              v92 = v190;
              *v90 = v192;
              *a9 += v92;
              v47 = a5;
              goto LABEL_156;
            }
            v177 = v88;
            if ( v88 >= v89 )
              v177 = v89;
            v207 = v177;
            Mdl = (IRP *)IoAllocateMdl(GlobalTrashBuffer, v177, 0, 0, 0);
            v181[0] = Mdl;
            if ( !Mdl )
              break;
            MmBuildMdlForNonPagedPool((PMDL)Mdl);
            v179 = (PIRP *)v196;
            *(PIRP *)&v196 = v181[0];
            if ( v179 )
              *v179 = v181[0];
            else
              *(PIRP *)&v192 = v181[0];
            v89 = v207;
            v88 = v210 - v207;
          }
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_e7b6edac773635936dfdf853ea49dd93_Traceguids);
          }
          RxFreeMdlChain(v192);
          *(_QWORD *)&v191 = 3221225626LL;
          SmbCseUpdateBufferContextStatus(v30, 3221225626LL);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_1ffd7df1a0ca364e8ae776b5c429ef78_Traceguids);
          }
LABEL_74:
          v53 = 1;
          goto LABEL_75;
        }
        v50 = *((_DWORD *)v30 + 187);
      }
      *a9 = v50;
      goto LABEL_62;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 29, WPP_ca2d5009ac97347054a9c333c3e72a58_Traceguids, v30);
    }
    v105 = *(_QWORD *)(*(_QWORD *)(v30[7] + 96LL) + 392LL);
    v204 = v105;
    if ( *(_DWORD *)(v105 + 320) == 2 )
    {
      TopLevelIrp = IoGetTopLevelIrp();
      v107 = (IRP *)v30[7];
      v181[0] = TopLevelIrp;
      IoSetTopLevelIrp(v107);
      if ( (_QWORD *)v30[43] != v30 + 43 )
        __int2c();
      v30[68] = *(_QWORD *)(v204 + 104) & 0xFFFFFFFFFFFFFFF8uLL | 6;
      RxCeTrackTransportOpEx(v30 + 66, 1, *(_QWORD *)(v204 + 104), v48);
      v108 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD, _DWORD, _QWORD *, __int64 (__fastcall *)()))(SmbdFastDispatch + 24))(
               *(_QWORD *)(v204 + 104),
               v48,
               *((unsigned __int8 *)v30 + 786),
               *((unsigned int *)v30 + 195),
               *((_DWORD *)v30 + 187),
               v30,
               SmbCeMemoryDeregisterCompleteInd);
      v109 = v108;
      if ( v108 != 259 )
        RxCeUntrackTransportOpEx(v30 + 66, v108);
      IoSetTopLevelIrp(v181[0]);
    }
    else
    {
      if ( *(_DWORD *)(v105 + 320) != 3 )
      {
        *(_BYTE *)(v196 + 786) = 0;
LABEL_358:
        *((_BYTE *)v30 + 87) = 0;
LABEL_227:
        v47 = a5;
        goto LABEL_58;
      }
      v109 = VmbusInvalidateBufferRegistration(v105, v48);
    }
    *((_BYTE *)v30 + 786) = 0;
    if ( v109 == -1073741816 || v109 == 259 )
      goto LABEL_227;
    goto LABEL_358;
  }
  *(_DWORD *)(v20 + 144) = *(_DWORD *)(v20 + 96);
  if ( v31 )
    goto LABEL_25;
LABEL_28:
  if ( BYTE14(v188) )
  {
    while ( 1 )
    {
      if ( v28 )
        goto LABEL_253;
      while ( 1 )
      {
        KeAcquireInStackQueuedSpinLockAtDpcLevel((PKSPIN_LOCK)(v20 + 256), &LockHandle);
        v202 = 1;
LABEL_253:
        v30 = 0;
        v119 = (_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 512) + 112LL) + 16LL * (BYTE8(v187) >> 2));
        for ( k = (_QWORD *)*v119; k != v119; v30 = 0 )
        {
          v30 = k - 3;
          if ( k[2] == *((_QWORD *)&v187 + 1) )
            break;
          k = (_QWORD *)*k;
        }
        if ( !v30 )
          goto LABEL_29;
        if ( !(unsigned __int8)SmbCeTryToAcquireCompoundingKeyOrExchangeLockAtDpc(*(_QWORD *)(v30[7] + 56LL), v30[7]) )
          break;
        _InterlockedIncrement((volatile signed __int32 *)(v30[7] + 36LL));
        v183 = 1;
        SmbCseDissociateAsyncIdFromBufferContextLite(v121, v30);
        v30[105] = 0;
        if ( v202 )
          goto LABEL_29;
      }
      KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
      v28 = 0;
      v202 = 0;
    }
  }
LABEL_29:
  KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
  if ( v30 )
  {
    *(_QWORD *)&v196 = v30;
    goto LABEL_31;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_1ffd7df1a0ca364e8ae776b5c429ef78_Traceguids, a1);
  }
  v32 = a5;
  v13 = 0;
  *a5 = a3;
LABEL_138:
  KeLowerIrql(v185);
LABEL_81:
  if ( (_BYTE)v193 )
  {
    v205 = *(_QWORD *)(pContext + 72);
    v181[0] = *(PIRP *)(v205 + 24);
    if ( KeGetCurrentIrql() >= 2u && (*(_DWORD *)(pContext + 68) & 0x40000) == 0 || *(_DWORD *)(a1 + 320) == 4 )
    {
      v113 = 0;
    }
    else
    {
      v111 = *(_QWORD *)(v205 + 56);
      if ( !v111
        || (v112 = *(__int64 (__fastcall **)(ULONG_PTR))(v111 + 912)) == 0
        || (v113 = v112(pContext), v113 != -1069481981) )
      {
        v114 = *(_QWORD *)(pContext + 232);
        *(_QWORD *)(pContext + 208) = 0;
        *(_DWORD *)(pContext + 40) = 8;
        v113 = (*(__int64 (__fastcall **)(ULONG_PTR))(v114 + 32))(pContext);
        if ( v113 != -1069481981 )
        {
          RDR_PERF_EXIT(pContext + 512);
          RDR_PERF_OUTPUT_ETW(pContext + 512);
          RDR_PERF_FREE(pContext + 512);
          SmbCeDereferenceExchange((PVOID)pContext);
          goto LABEL_82;
        }
      }
    }
    if ( (*(_DWORD *)(pContext + 68) & 1) != 0 )
      KeBugCheckEx(0x27u, 0x43584D5Fu, pContext, v113, 0);
    LOBYTE(v110) = 20;
    RDR_PERF_ENTER(pContext + 512, v110);
    SmbCeIncrementTeardownOpCounter(v181[0], pContext, 7);
    RxPostToWorkerThread(
      (PRDBSS_DEVICE_OBJECT)v181[0],
      NormalWorkQueue,
      (PRX_WORK_QUEUE_ITEM)(pContext + 240),
      SmbCepFinalizeExchangeWorker,
      (PVOID)pContext);
  }
LABEL_82:
  ExReleaseRundownProtection(RunRef);
  if ( v186 )
    SmbCeDereferenceServerEntryEx(v18);
  if ( Irp )
    IofCompleteRequest(Irp, 1);
  if ( v13 != -1073741802 )
LABEL_87:
    *v32 = a3;
  return v13;
}

```

## disassembly

```asm
0x140006ec0  mov     [rsp-8+arg_10], rbx
0x140006ec5  mov     [rsp-8+arg_18], r9
0x140006eca  mov     [rsp-8+arg_8], edx
0x140006ece  push    rbp
0x140006ecf  push    rsi
0x140006ed0  push    rdi
0x140006ed1  push    r12
0x140006ed3  push    r13
0x140006ed5  push    r14
0x140006ed7  push    r15
0x140006ed9  lea     rbp, [rsp-80h]
0x140006ede  sub     rsp, 1E0h
0x140006ee5  mov     r12, [rcx+18h]
0x140006ee9  lea     rbx, [rcx+1F0h]
0x140006ef0  xorps   xmm0, xmm0
0x140006ef3  mov     [rbp+0B0h+var_F0], r12
0x140006ef7  xor     eax, eax
0x140006ef9  mov     [rbp+0B0h+RunRef], rbx
0x140006efd  mov     r15, rcx
0x140006f00  mov     [rbp+0B0h+var_F8], rax
0x140006f04  xor     edi, edi
0x140006f06  mov     qword ptr [rbp+0B0h+LockHandle.OldIrql], rax
0x140006f0a  mov     rcx, rbx; RunRef
0x140006f0d  mov     qword ptr [rbp+0B0h+var_E0], rdi
0x140006f11  mov     r14d, r8d
0x140006f14  mov     esi, edx
0x140006f16  movups  [rbp+0B0h+var_118], xmm0
0x140006f1a  movups  [rbp+0B0h+var_108], xmm0
0x140006f1e  movups  xmmword ptr [rbp+0B0h+LockHandle.LockQueue.Next], xmm0
0x140006f22  call    cs:__imp_ExAcquireRundownProtection
0x140006f29  nop     dword ptr [rax+rax+00h]
0x140006f2e  test    al, al
0x140006f30  jz      loc_140007D8D
0x140006f36  mov     r13, [r15+1F8h]
0x140006f3d  test    r13, r13
0x140006f40  jz      loc_14000817F
0x140006f46  mov     [rbp+0B0h+var_11C], dil
0x140006f4a  mov     rax, [r13+0C0h]
0x140006f51  lea     rcx, [rbp+0B0h+var_118]
0x140006f55  mov     rbx, [rbp+0B0h+arg_28]
0x140006f5c  mov     r9d, r14d
0x140006f5f  mov     qword ptr [rsp+210h+pContext], rcx
0x140006f64  mov     r8d, esi
0x140006f67  mov     [rbp+0B0h+Irp], rdi
0x140006f6b  mov     rdx, rbx
0x140006f6e  mov     rax, [rax+20h]
0x140006f72  mov     rcx, r13
0x140006f75  mov     rdi, [r15+200h]
0x140006f7c  call    _guard_dispatch_icall
0x140006f81  mov     ecx, 1
0x140006f86  cmp     eax, 0C0000016h
0x140006f8b  jz      loc_140008281
0x140006f91  mov     [rbp+0B0h+var_120], 0
0x140006f95  test    eax, eax
0x140006f97  js      loc_1400082BE
0x140006f9d  movzx   r9d, word ptr [rbp+0B0h+var_108+0Ch]
0x140006fa2  mov     edx, dword ptr [rbp+0B0h+var_108+8]
0x140006fa5  mov     r8d, dword ptr [rbp+0B0h+var_108+4]
0x140006fa9  mov     ecx, dword ptr [rbp+0B0h+var_108]
0x140006fac  test    byte ptr [r13+2FCh], 1
0x140006fb4  cmovz   ecx, r8d
0x140006fb8  mov     dword ptr [rbp+0B0h+var_108], ecx
0x140006fbb  test    edx, edx
0x140006fbd  jnz     loc_140007CE8
0x140006fc3  movzx   eax, r9w
0x140006fc7  lock add [rdi+58h], eax
0x140006fcb  mov     rax, [r13+0C0h]
0x140006fd2  lea     rcx, [rbp+0B0h+var_118]
0x140006fd6  mov     qword ptr [rsp+210h+pContext], rcx
0x140006fdb  mov     r9d, r14d
0x140006fde  mov     r8d, esi
0x140006fe1  mov     rdx, rbx
0x140006fe4  mov     rcx, r13
0x140006fe7  mov     rax, [rax+28h]
0x140006feb  call    _guard_dispatch_icall
0x140006ff0  cmp     eax, 0C0000016h
0x140006ff5  jnz     loc_140008308
0x140006ffb  xor     bl, bl
0x140006ffd  xor     esi, esi
0x140006fff  mov     cl, 2; NewIrql
0x140007001  mov     byte ptr [rbp+0B0h+arg_0], bl
0x140007007  mov     byte ptr [rbp+0B0h+var_C0], bl
0x14000700a  mov     [rbp+0B0h+var_11F], bl
0x14000700d  call    cs:__imp_KfRaiseIrql
0x140007014  nop     dword ptr [rax+rax+00h]
0x140007019  mov     [rbp+0B0h+var_11D], al
0x14000701c  test    bl, bl
0x14000701e  jnz     loc_140007FA4
0x140007024  lea     rcx, [rdi+100h]; SpinLock
0x14000702b  lea     rdx, [rbp+0B0h+LockHandle]; LockHandle
0x14000702f  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x140007036  nop     dword ptr [rax+rax+00h]
0x14000703b  mov     r9b, 1
0x14000703e  mov     byte ptr [rbp+0B0h+arg_0], r9b
0x140007045  mov     r8, qword ptr [rbp+0B0h+var_118]
0x140007049  cmp     r8, [rdi+40h]
0x14000704d  jb      loc_140007E59
0x140007053  cmp     r8, [rdi+48h]
0x140007057  jnb     loc_140007E59
0x14000705d  mov     ecx, [rdi+60h]
0x140007060  xor     edx, edx
0x140007062  mov     rbx, [rdi+68h]
0x140007066  mov     rax, r8
0x140007069  div     rcx
0x14000706c  mov     rbx, [rbx+rdx*8]
0x140007070  mov     qword ptr [rbp+0B0h+var_A0], rbx
0x140007074  mov     r12, rbx
0x140007077  test    rbx, rbx
0x14000707a  jnz     short loc_1400070C8
0x14000707c  cmp     byte ptr [rbp+0B0h+var_108+0Eh], sil
0x140007080  jnz     loc_140007158
0x140007086  mov     rcx, cs:WPP_GLOBAL_Control
0x14000708d  lea     rax, WPP_GLOBAL_Control
0x140007094  cmp     rcx, rax
0x140007097  jnz     loc_14000833C
0x14000709d  mov     r12, [rbp+0B0h+arg_20]
0x1400070a4  xor     edi, edi
0x1400070a6  mov     [r12], r14d
0x1400070aa  test    r9b, r9b
0x1400070ad  jz      loc_140007903
0x1400070b3  lea     rcx, [rbp+0B0h+LockHandle]; LockHandle
0x1400070b7  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x1400070be  nop     dword ptr [rax+rax+00h]
0x1400070c3  jmp     loc_140007903
0x1400070c8  mov     r12, [rbx+38h]
0x1400070cc  mov     rax, [r12+38h]
0x1400070d1  mov     [rbp+0B0h+var_130], rax
0x1400070d5  test    rax, rax
0x1400070d8  jnz     loc_140007ADE
0x1400070de  lea     rcx, [r12+18h]; SpinLock
0x1400070e3  call    cs:__imp_KeTryToAcquireSpinLockAtDpcLevel
0x1400070ea  nop     dword ptr [rax+rax+00h]
0x1400070ef  test    al, al
0x1400070f1  jz      loc_14000831F
0x1400070f7  mov     r8d, 1
0x1400070fd  lock xadd [r12+4], r8d
0x140007104  inc     r8d
0x140007107  mov     rcx, cs:WPP_GLOBAL_Control
0x14000710e  lea     rax, WPP_GLOBAL_Control
0x140007115  cmp     rcx, rax
0x140007118  jz      short loc_140007125
0x14000711a  mov     eax, [rcx+2Ch]
0x14000711d  test    al, 10h
0x14000711f  jnz     loc_14000814B
0x140007125  mov     rax, [rbx+38h]
0x140007129  lock inc dword ptr [rax+24h]
0x14000712d  mov     rcx, [r15+200h]; pContext
0x140007134  mov     rdx, rbx
0x140007137  mov     [rbp+0B0h+var_11F], 1
0x14000713b  call    SmbCseDissociateMidFromBufferContextLite
0x140007140  movzx   r9d, byte ptr [rbp+0B0h+arg_0]
0x140007148  test    r9b, r9b
0x14000714b  jz      loc_140008316
0x140007151  mov     r8, qword ptr [rbp+0B0h+var_118]
0x140007155  mov     r12, rbx
0x140007158  cmp     dword ptr [r15+140h], 2
0x140007160  mov     eax, 8
0x140007165  mov     [rbp+0B0h+var_11E], 1
0x140007169  mov     rcx, 0FFFFF78000000008h
0x140007173  jnz     loc_140007664
0x140007179  mov     eax, [rdi+60h]
0x14000717c  mov     [rdi+90h], eax
0x140007182  test    r12, r12
0x140007185  jz      short loc_1400071A7
0x140007187  mov     r8, qword ptr [rbp+0B0h+var_118]
0x14000718b  cmp     byte ptr [rbp+0B0h+var_108+0Eh], sil
0x14000718f  jnz     loc_140007BC5
0x140007195  lea     rcx, [rbp+0B0h+LockHandle]; LockHandle
0x140007199  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x1400071a0  nop     dword ptr [rax+rax+00h]
0x1400071a5  jmp     short loc_1400071CE
0x1400071a7  cmp     byte ptr [rbp+0B0h+var_108+0Eh], sil
0x1400071ab  jnz     loc_14000839A
0x1400071b1  lea     rcx, [rbp+0B0h+LockHandle]; LockHandle
0x1400071b5  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x1400071bc  nop     dword ptr [rax+rax+00h]
0x1400071c1  test    rbx, rbx
0x1400071c4  jz      loc_1400083A8
0x1400071ca  mov     qword ptr [rbp+0B0h+var_A0], rbx
0x1400071ce  mov     rsi, [rbx+38h]
0x1400071d2  xor     eax, eax
0x1400071d4  mov     r12, [rbp+0B0h+arg_48]
0x1400071db  mov     rdx, [rsi+38h]
0x1400071df  mov     [rbp+0B0h+var_B8], rdx
0x1400071e3  mov     [rbx+2E0h], r14d
0x1400071ea  mov     [rbx+55h], al
0x1400071ed  test    r12, r12
0x1400071f0  jz      short loc_1400071FE
0x1400071f2  mov     eax, [r12]
0x1400071f6  test    eax, eax
0x1400071f8  js      loc_140007B0A
0x1400071fe  test    dword ptr [rbx+368h], 40000000h
0x140007208  setnz   cl
0x14000720b  bt      eax, 1Ch
0x14000720f  setnb   al
0x140007212  test    al, cl
0x140007214  jnz     loc_140007977
0x14000721a  test    rdx, rdx
0x14000721d  jnz     loc_140007A0D
0x140007223  lea     rcx, [rsi+18h]; SpinLock
0x140007227  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14000722e  nop     dword ptr [rax+rax+00h]
0x140007233  mov     rcx, rsi; pContext
0x140007236  call    SmbCeDereferenceExchange
0x14000723b  movzx   ecx, [rbp+0B0h+var_11D]; NewIrql
0x14000723f  call    cs:__imp_KeLowerIrql
0x140007246  nop     dword ptr [rax+rax+00h]
0x14000724b  cmp     byte ptr [rbp+0B0h+var_108+0Eh], 0
0x14000724f  mov     [rbp+0B0h+var_11E], 0
0x140007253  jz      loc_140007585
0x140007259  test    r12, r12
0x14000725c  jz      loc_14005BDAA
0x140007262  mov     r10, cs:WPP_GLOBAL_Control
0x140007269  lea     rax, WPP_GLOBAL_Control
0x140007270  cmp     r10, rax
0x140007273  jnz     loc_140007D00
0x140007279  movzx   ecx, word ptr [rbp+0B0h+var_108+0Ch]
0x14000727d  lea     r8, aRecvSAsyncidLx; "RECV: [%s] ([AsyncId]) ([%lx]) Creds %l"...
0x140007284  mov     eax, dword ptr [rbp+0B0h+var_108+4]
0x140007287  mov     edx, 1
0x14000728c  mov     r9, [rbp+0B0h+var_F8]
0x140007290  mov     dword ptr [rsp+210h+var_1E0], eax
0x140007294  mov     eax, dword ptr [rbp+0B0h+var_118+8]
0x140007297  mov     dword ptr [rsp+210h+pContext+8], ecx
0x14000729b  mov     rcx, [rdi+10h]
0x14000729f  mov     dword ptr [rsp+210h+pContext], eax
0x1400072a3  call    cs:__imp_RxDiagnosticTrace
0x1400072aa  nop     dword ptr [rax+rax+00h]
0x1400072af  test    cs:byte_1400712C1, 1
0x1400072b6  jnz     loc_140008429
0x1400072bc  mov     eax, dword ptr [rbp+0B0h+var_108]
0x1400072bf  cmp     eax, 0FFFFFFFFh
0x1400072c2  jnz     loc_140007918
0x1400072c8  mov     eax, gs:1A4h
0x1400072d0  mov     ecx, eax
0x1400072d2  shl     rcx, 8
0x1400072d6  add     rcx, cs:MRxSmbLegacyPerfCtrs
0x1400072dd  mov     edx, r14d
0x1400072e0  lock add [rcx], rdx
0x1400072e4  call    cs:__imp_RxPerProcessCountersEnabled
0x1400072eb  nop     dword ptr [rax+rax+00h]
0x1400072f0  test    al, al
0x1400072f2  jz      short loc_140007335
0x1400072f4  mov     rax, [rsi+30h]
0x1400072f8  test    rax, rax
0x1400072fb  jz      loc_140007A00
0x140007301  cmp     dword ptr [rax+78h], 0
0x140007305  jl      loc_140007A00
0x14000730b  cmp     dword ptr [r15+174h], 0
0x140007313  jz      short loc_140007329
0x140007315  xor     ecx, ecx
0x140007317  xchg    ecx, [r15+174h]
0x14000731e  mov     rax, [rsi+30h]
0x140007322  lock add [rax+0C4h], ecx
0x140007329  mov     rax, [rsi+30h]
0x14000732d  lock add [rax+0C4h], r14d
0x140007335  cmp     qword ptr [rsi+50h], 0
0x14000733a  mov     eax, dword ptr [rbp+0B0h+var_108]
0x14000733d  jnz     loc_140007927
0x140007343  cmp     qword ptr [rsi+58h], 0
0x140007348  jnz     loc_140007888
0x14000734e  cmp     qword ptr [rsi+50h], 0
0x140007353  jnz     loc_140007805
0x140007359  mov     rax, [rsi+0E8h]
0x140007360  lea     r8, [rbp+0B0h+var_118]
0x140007364  mov     rcx, [rbp+0B0h+arg_28]
0x14000736b  mov     rdx, rbx
0x14000736e  mov     r9d, [rbp+0B0h+arg_8]
0x140007375  mov     [rsp+210h+var_1D8], r12
0x14000737a  mov     r12, [rbp+0B0h+arg_20]
0x140007381  mov     rax, [rax+8]
0x140007385  mov     [rsp+210h+var_1E0], rcx
0x14000738a  mov     rcx, rsi
0x14000738d  mov     qword ptr [rsp+210h+pContext+8], r12
0x140007392  mov     dword ptr [rsp+210h+pContext], r14d
0x140007397  call    _guard_dispatch_icall
0x14000739c  mov     r12, [rbp+0B0h+var_B8]
0x1400073a0  mov     edi, eax
0x1400073a2  test    r12, r12
0x1400073a5  jnz     loc_1400079DF
0x1400073ab  mov     r9d, 1
0x1400073b1  lock xadd [rsi+4], r9d
0x1400073b7  inc     r9d
0x1400073ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1400073c1  lea     rax, WPP_GLOBAL_Control
0x1400073c8  cmp     rcx, rax
0x1400073cb  jz      short loc_1400073D8
0x1400073cd  mov     eax, [rcx+2Ch]
0x1400073d0  test    al, 10h
0x1400073d2  jnz     loc_1400084DC
0x1400073d8  lea     rcx, [rsi+18h]; SpinLock
0x1400073dc  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400073e3  nop     dword ptr [rax+rax+00h]
0x1400073e8  mov     [rsi+20h], al
0x1400073eb  mov     rcx, [rbp+0B0h+arg_20]
0x1400073f2  cmp     edi, 0C0000016h
0x1400073f8  jz      short loc_140007404
0x1400073fa  or      dword ptr [rbx+4], 400h
0x140007401  mov     [rcx], r14d
0x140007404  mov     eax, [rcx]
  ... truncated ...
```
