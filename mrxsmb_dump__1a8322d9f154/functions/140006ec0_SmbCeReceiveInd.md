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
  ULONG_PTR v16; // r13
  __int64 v17; // rax
  __int64 v18; // rdi
  int v19; // eax
  unsigned __int16 v20; // r9
  unsigned int v21; // edx
  int v22; // r8d
  int v23; // ecx
  ULONG_PTR pContext; // rsi
  unsigned __int64 v25; // rdx
  char v26; // r9
  __int64 v27; // r8
  _QWORD *v28; // rbx
  _QWORD *v29; // r12
  unsigned int *v30; // r12
  __int64 v31; // r12
  __int64 v32; // rax
  signed __int32 v33; // r8d
  void *v34; // rcx
  bool v35; // zf
  int v36; // eax
  __int64 v37; // rdx
  __int64 v38; // rax
  int v39; // eax
  unsigned int v40; // eax
  __int64 v41; // r12
  signed __int32 v42; // r9d
  unsigned int *v43; // rcx
  __int64 v44; // r12
  __int64 v45; // rax
  unsigned int v46; // eax
  __int64 v47; // rax
  int v48; // eax
  char v49; // cl
  int v50; // edx
  int v51; // ecx
  unsigned int v52; // r8d
  unsigned __int64 v53; // rax
  bool v54; // cl
  unsigned __int64 v55; // rcx
  __int64 v56; // r8
  __int64 v57; // r9
  __int64 v58; // r10
  __int64 v59; // r8
  __int64 v60; // rcx
  int v61; // edx
  int v62; // r8d
  int v63; // r9d
  int v64; // ecx
  int v65; // edx
  KIRQL v66; // di
  volatile LONG *v67; // rcx
  __int64 v68; // r9
  KIRQL v69; // al
  __int64 v70; // rcx
  KIRQL v71; // di
  __int64 v72; // rbx
  KIRQL v73; // al
  __int64 v74; // rcx
  KIRQL v75; // di
  int v76; // eax
  _QWORD *v77; // rax
  _QWORD *v78; // r8
  unsigned int v79; // edx
  unsigned int v80; // eax
  IRP *v81; // rbx
  int v82; // eax
  int v83; // ecx
  ULONG v84; // ecx
  unsigned int v85; // edx
  _QWORD *v86; // rcx
  _QWORD *j; // rdx
  int v88; // eax
  __int64 v89; // rcx
  __int64 v90; // rax
  __int64 v91; // rdx
  __int64 v92; // rcx
  int v93; // ecx
  int v94; // eax
  __int64 v95; // rax
  unsigned __int64 v96; // rcx
  unsigned __int64 v97; // rdx
  __int64 v98; // rax
  __int64 i; // rcx
  __int64 v100; // rdx
  __int64 v101; // rcx
  IRP *TopLevelIrp; // rax
  IRP *v103; // rcx
  unsigned int v104; // eax
  unsigned int v105; // r12d
  __int64 v106; // rdx
  __int64 v107; // rax
  __int64 (__fastcall *v108)(ULONG_PTR); // rax
  int v109; // ecx
  __int64 v110; // rax
  KIRQL v111; // al
  KIRQL v112; // di
  __int64 v113; // rdx
  __int64 v114; // rcx
  _QWORD *v115; // r8
  _QWORD *k; // rax
  __int64 v117; // rcx
  unsigned __int64 v118; // rax
  __int64 v119; // rax
  __int128 v121; // xmm0
  ADDRESS_FAMILY v122; // cx
  UCHAR v123; // al
  __int16 v124; // r8
  __int64 v125; // r10
  char v126; // r11
  bool v127; // cf
  int v128; // r8d
  __int128 v129; // xmm0
  __int128 v130; // xmm0
  ADDRESS_FAMILY v131; // cx
  __int128 v132; // xmm0
  ADDRESS_FAMILY v133; // cx
  __int16 v134; // r8
  __int64 v135; // r10
  char v136; // r11
  int v137; // r8d
  __int128 v138; // xmm0
  ADDRESS_FAMILY v139; // cx
  UCHAR v140; // al
  __int16 v141; // r8
  __int64 v142; // r10
  char v143; // r11
  int v144; // r8d
  __int128 v145; // xmm0
  __int128 v146; // xmm0
  ADDRESS_FAMILY v147; // cx
  __int128 v148; // xmm0
  ADDRESS_FAMILY v149; // cx
  UCHAR v150; // al
  __int16 v151; // r8
  __int64 v152; // r10
  char v153; // r11
  int v154; // r8d
  __int128 v155; // xmm0
  ADDRESS_FAMILY v156; // cx
  UCHAR v157; // al
  __int16 v158; // r8
  __int64 v159; // r10
  char v160; // r11
  int v161; // r8d
  __int128 v162; // xmm0
  __int128 v163; // xmm0
  ADDRESS_FAMILY v164; // cx
  __int128 v165; // xmm0
  ADDRESS_FAMILY v166; // cx
  __int16 v167; // r8
  __int64 v168; // r10
  char v169; // r11
  int v170; // r8d
  volatile LONG *v171; // rcx
  volatile LONG *v172; // rcx
  ULONG v173; // eax
  IRP *Mdl; // rax
  PIRP *v175; // rcx
  int v176; // [rsp+38h] [rbp-128h]
  PIRP v177[2]; // [rsp+E0h] [rbp-80h] BYREF
  char v178; // [rsp+F0h] [rbp-70h]
  char v179; // [rsp+F1h] [rbp-6Fh]
  char v180; // [rsp+F2h] [rbp-6Eh]
  KIRQL v181; // [rsp+F3h] [rbp-6Dh]
  char v182; // [rsp+F4h] [rbp-6Ch]
  __int128 v183; // [rsp+F8h] [rbp-68h] BYREF
  __int128 v184; // [rsp+108h] [rbp-58h]
  const char *v185; // [rsp+118h] [rbp-48h]
  __int64 v186; // [rsp+120h] [rbp-40h]
  __int128 v187; // [rsp+130h] [rbp-30h] BYREF
  __int128 v188; // [rsp+140h] [rbp-20h] BYREF
  int v189; // [rsp+150h] [rbp-10h]
  __int64 v190; // [rsp+158h] [rbp-8h]
  PIRP Irp; // [rsp+160h] [rbp+0h]
  __int128 v192; // [rsp+170h] [rbp+10h] BYREF
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+180h] [rbp+20h] BYREF
  __int128 v194; // [rsp+1A0h] [rbp+40h] BYREF
  __int128 v195; // [rsp+1B0h] [rbp+50h] BYREF
  PEX_RUNDOWN_REF RunRef; // [rsp+1C0h] [rbp+60h]
  __int128 v197[4]; // [rsp+1D0h] [rbp+70h] BYREF
  char v198; // [rsp+220h] [rbp+C0h]
  int v199; // [rsp+220h] [rbp+C0h]
  __int64 v200; // [rsp+220h] [rbp+C0h]
  __int64 v201; // [rsp+220h] [rbp+C0h]
  int v202; // [rsp+220h] [rbp+C0h]
  ULONG v203; // [rsp+220h] [rbp+C0h]
  unsigned int v204; // [rsp+228h] [rbp+C8h]
  ULONG v206; // [rsp+248h] [rbp+E8h]

  v204 = a2;
  v10 = *(_QWORD *)(a1 + 24);
  v11 = (struct _EX_RUNDOWN_REF *)(a1 + 496);
  v186 = v10;
  RunRef = (PEX_RUNDOWN_REF)(a1 + 496);
  v185 = 0;
  v13 = 0;
  *(_QWORD *)&v187 = 0;
  v15 = a2;
  v183 = 0;
  v184 = 0;
  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( !ExAcquireRundownProtection((PEX_RUNDOWN_REF)(a1 + 496)) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_1ffd7df1a0ca364e8ae776b5c429ef78_Traceguids, a1);
    }
    v30 = a5;
    goto LABEL_87;
  }
  v16 = *(_QWORD *)(a1 + 504);
  if ( v16 )
  {
    v182 = 0;
  }
  else
  {
    v111 = SmbCeAcquireSpinLock(v10);
    v112 = v111;
    v113 = *(_QWORD *)(a1 + 520);
    if ( v113 == a1 + 520 || v113 == 416 || (v114 = *(_QWORD *)(v113 - 416 + 384)) == 0 )
    {
      *(_DWORD *)(v10 + 2352) = -1;
      ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(v10 + 1920), v111);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_1ffd7df1a0ca364e8ae776b5c429ef78_Traceguids, a1);
      }
      v13 = 0;
      ExReleaseRundownProtection(v11);
      v30 = a5;
      goto LABEL_87;
    }
    if ( *(_WORD *)v114 == 0xE200 )
    {
      v16 = *(_QWORD *)(v113 - 416 + 384);
    }
    else
    {
      v16 = 0;
      if ( *(_WORD *)v114 == 0xE202 )
        v16 = *(_QWORD *)(v114 + 384);
    }
    SmbCeReferenceServerEntry(v16);
    v182 = 1;
    *(_DWORD *)(v10 + 2352) = -1;
    ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(v10 + 1920), v112);
  }
  v17 = *(_QWORD *)(v16 + 192);
  Irp = 0;
  v18 = *(_QWORD *)(a1 + 512);
  v19 = (*(__int64 (__fastcall **)(ULONG_PTR, __int64, _QWORD, _QWORD, __int128 *))(v17 + 32))(v16, a6, v15, a3, &v183);
  if ( v19 == -1073741802 )
  {
    v118 = *(_QWORD *)(v18 + 64);
    v20 = 1;
    WORD6(v184) = 1;
    v22 = 0;
    v23 = 0;
    v183 = v118;
    v21 = 0;
    DWORD2(v184) = 0;
    *(_QWORD *)&v184 = 0;
    BYTE14(v184) = 0;
    v185 = "NEG_MP  ";
    v178 = 1;
  }
  else
  {
    v178 = 0;
    if ( v19 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_1ffd7df1a0ca364e8ae776b5c429ef78_Traceguids, a1);
      }
      v30 = a5;
      v13 = 0;
      goto LABEL_82;
    }
    v20 = WORD6(v184);
    v21 = DWORD2(v184);
    v22 = DWORD1(v184);
    v23 = v184;
  }
  if ( (*(_BYTE *)(v16 + 764) & 1) == 0 )
    v23 = v22;
  LODWORD(v184) = v23;
  if ( v21 )
  {
    a3 = v21;
    if ( v15 >= v21 )
    {
      v15 = v21;
      v204 = v21;
    }
  }
  _InterlockedAdd((volatile signed __int32 *)(v18 + 88), v20);
  if ( (*(unsigned int (__fastcall **)(ULONG_PTR, __int64, _QWORD, _QWORD, __int128 *))(*(_QWORD *)(v16 + 192) + 40LL))(
         v16,
         a6,
         v15,
         a3,
         &v183) != -1073741802 )
  {
    v30 = a5;
    v13 = 0;
    goto LABEL_82;
  }
  pContext = 0;
  LOBYTE(v189) = 0;
  v179 = 0;
  v181 = KfRaiseIrql(2u);
  while ( 1 )
  {
    KeAcquireInStackQueuedSpinLockAtDpcLevel((PKSPIN_LOCK)(v18 + 256), &LockHandle);
    v26 = 1;
    v198 = 1;
    v27 = v183;
    if ( (unsigned __int64)v183 < *(_QWORD *)(v18 + 64) || (unsigned __int64)v183 >= *(_QWORD *)(v18 + 72) )
    {
      v29 = 0;
      v28 = 0;
      *(_QWORD *)&v192 = 0;
LABEL_15:
      if ( BYTE14(v184) )
        goto LABEL_23;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_iq(WPP_GLOBAL_Control->AttachedDevice, v25, v183, v183, a1);
      }
      v30 = a5;
      v13 = 0;
      *a5 = a3;
      KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
      goto LABEL_138;
    }
    v25 = (unsigned __int64)v183 % *(unsigned int *)(v18 + 96);
    v28 = *(_QWORD **)(*(_QWORD *)(v18 + 104) + 8 * v25);
    *(_QWORD *)&v192 = v28;
    v29 = v28;
    if ( !v28 )
      goto LABEL_15;
    v31 = v28[7];
    v32 = *(_QWORD *)(v31 + 56);
    v177[0] = (PIRP)v32;
    if ( !v32 )
      break;
    if ( KeTryToAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(v32 + 8)) )
    {
      _InterlockedIncrement((volatile signed __int32 *)(&v177[0]->Size + 1));
      goto LABEL_22;
    }
LABEL_266:
    KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
  }
  if ( !KeTryToAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(v31 + 24)) )
    goto LABEL_266;
  v33 = _InterlockedIncrement((volatile signed __int32 *)(v31 + 4));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qDD(
      WPP_GLOBAL_Control->AttachedDevice,
      33,
      WPP_d39beb3e593835eae73483c3886eb046_Traceguids,
      v31,
      v33 - 1,
      v33);
  }
LABEL_22:
  _InterlockedIncrement((volatile signed __int32 *)(v28[7] + 36LL));
  v34 = *(void **)(a1 + 512);
  v179 = 1;
  SmbCseDissociateMidFromBufferContextLite(v34);
  v26 = 1;
  v27 = v183;
  v29 = v28;
LABEL_23:
  v35 = *(_DWORD *)(a1 + 320) == 2;
  v180 = 1;
  if ( !v35 )
  {
    if ( !v29 )
      goto LABEL_28;
    if ( v29[105] )
    {
      v52 = *(_DWORD *)(v18 + 80);
      if ( v52 < 8 )
        v52 = 8;
      v53 = (*(_QWORD *)(a1 + 304) * v52 + (MEMORY[0xFFFFF78000000008] - v29[105]) / 0xAuLL)
          / (*((_DWORD *)v29 + 20) + v52);
      v27 = v183;
      *(_QWORD *)(a1 + 304) = v53;
    }
    v54 = (*(_BYTE *)(v16 + 765) & 1) != 0 || *(_DWORD *)(a1 + 320) == 2 || (*(_BYTE *)(v16 + 736) & 1) != 0;
    if ( (byte_14007D0C0 & 2) != 0 || v54 )
    {
      *(_DWORD *)(v18 + 144) = *(_DWORD *)(v18 + 96);
    }
    else
    {
      v55 = v29[5];
      if ( v55 < *(_QWORD *)(v18 + 136) )
        goto LABEL_26;
      v56 = *(_QWORD *)(a1 + 280);
      v57 = *(_QWORD *)(a1 + 304);
      v58 = (unsigned int)dword_14007D08C;
      *(_QWORD *)(v18 + 136) = *(_QWORD *)(v18 + 72);
      if ( v56 )
      {
        if ( v56 >= 500000 )
          goto LABEL_110;
        goto LABEL_170;
      }
      if ( v55 >= 0x32 )
      {
LABEL_170:
        v56 = 500000;
LABEL_110:
        v59 = 2 * v57 / v56;
        if ( (int)v59 > 17 || v57 > 1000000 * v58 / 6 )
          LODWORD(v59) = 17;
        v60 = 3LL * (int)v59;
        v61 = *((_DWORD *)qword_1400702E0 + 3 * (int)v59);
        v62 = *((_DWORD *)qword_1400702E0 + 3 * (int)v59 + 1);
        v63 = *((_DWORD *)&qword_1400702E0[1] + v60);
        v64 = 2;
        if ( *(_DWORD *)(v18 + 144) > 2u )
          v64 = *(_DWORD *)(v18 + 144);
        if ( v61 )
        {
          if ( v61 == 1 )
            v64 += v62 - v63;
        }
        else
        {
          v64 = v64 * v62 / v63;
        }
        v65 = *(_DWORD *)(v18 + 96);
        if ( v64 <= 2 )
          v64 = 2;
        if ( v64 <= v65 )
          v65 = v64;
        if ( v65 > dbgRestrictWindowSize )
          v65 = dbgRestrictWindowSize;
        if ( v65 <= dbgWindowSizeThresholdLo )
          __debugbreak();
        *(_DWORD *)(v18 + 144) = v65;
      }
    }
LABEL_25:
    v27 = v183;
LABEL_26:
    if ( BYTE14(v184) && DWORD1(v184) == 259 )
    {
      pContext = v29[7];
      v176 = *(_DWORD *)(a6 + 8);
      v190 = *(_QWORD *)(pContext + 56);
      RxDiagnosticTrace(
        *(_QWORD *)(v18 + 16),
        1,
        "RECV: [%s] (Mid/[AsyncId]) (%I64x/[%lx]) Creds %lx Status %lx",
        v185,
        v27,
        DWORD2(v183),
        WORD6(v184),
        v176);
      v89 = *((_QWORD *)&v183 + 1);
      v90 = *(_QWORD *)(a1 + 512);
      *((_DWORD *)v29 + 1) |= 2u;
      v29[5] = v89;
      v91 = 16LL * ((unsigned __int8)v89 >> 2) + *(_QWORD *)(v90 + 112);
      v92 = *(_QWORD *)v91;
      if ( *(_QWORD *)(*(_QWORD *)v91 + 8LL) != v91 )
        __fastfail(3u);
      v29[3] = v92;
      v29[4] = v91;
      *(_QWORD *)(v92 + 8) = v29 + 3;
      *(_QWORD *)v91 = v29 + 3;
      KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
      v93 = a10;
      if ( a10 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          v177[1] = (PIRP)16;
          v177[0] = (PIRP)(a10 + 32);
          v129 = *(_OWORD *)v177;
          v177[1] = (PIRP)16;
          v177[0] = (PIRP)(a10 + 16);
          v188 = v129;
          v130 = *(_OWORD *)v177;
          v177[1] = 0;
          v177[0] = (PIRP)(a1 + 428);
          v131 = *(_WORD *)(a1 + 428);
          v192 = v130;
          v177[1] = (PIRP)SOCKADDR_SIZE(v131);
          v132 = *(_OWORD *)v177;
          v177[1] = 0;
          v177[0] = (PIRP)(a1 + 400);
          v133 = *(_WORD *)(a1 + 400);
          v187 = v132;
          v177[1] = (PIRP)SOCKADDR_SIZE(v133);
          v136 = 69;
          if ( (v134 & 0x8000) == 0 )
            v136 = 32;
          v127 = (v134 & 0x1000) != 0;
          v137 = 83;
          if ( !v127 )
            v137 = 32;
          WPP_SF_d_SOCKADDR__SOCKADDR_ccsDDiDDDLqqqqqqLqq_zb__zb_(
            *(_QWORD *)(v135 + 24),
            WORD6(v184),
            v137,
            *(unsigned __int8 *)(*(_QWORD *)(*(_QWORD *)(pContext + 72) + 24LL) + 1312LL),
            (__int64)v177,
            (__int64)&v187,
            v137,
            v136,
            (__int64)v185,
            v204,
            a3,
            v183,
            *((_DWORD *)v29 + 20),
            SBYTE12(v184),
            SBYTE8(v183),
            *(_DWORD *)(a6 + 8),
            pContext,
            (char)v29,
            *(_QWORD *)(pContext + 48),
            a1,
            *(_QWORD *)(pContext + 96),
            *(_QWORD *)(pContext + 80),
            *(_DWORD *)(a6 + 36),
            *(_QWORD *)(pContext + 88),
            v16,
            (__int64)&v192,
            (__int64)&v188);
        }
      }
      else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
             && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
             && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v177[1] = 0;
        v177[0] = (PIRP)(a1 + 428);
        v177[1] = (PIRP)SOCKADDR_SIZE(*(_WORD *)(a1 + 428));
        v121 = *(_OWORD *)v177;
        v177[1] = 0;
        v177[0] = (PIRP)(a1 + 400);
        v122 = *(_WORD *)(a1 + 400);
        v188 = v121;
        v123 = SOCKADDR_SIZE(v122);
        v126 = 69;
        v177[1] = (PIRP)v123;
        if ( (v124 & 0x8000) == 0 )
          v126 = 32;
        v127 = (v124 & 0x1000) != 0;
        v128 = 83;
        if ( !v127 )
          v128 = 32;
        WPP_SF_d_SOCKADDR__SOCKADDR_ccsDDiDDDLqqqqqqLqq(
          *(_QWORD *)(v125 + 24),
          WORD6(v184),
          v128,
          *(unsigned __int8 *)(*(_QWORD *)(*(_QWORD *)(pContext + 72) + 24LL) + 1312LL),
          (__int64)v177,
          (__int64)&v188,
          v128,
          v126,
          (__int64)v185,
          v204,
          a3,
          v183,
          *((_DWORD *)v29 + 20),
          SBYTE12(v184),
          SBYTE8(v183),
          *(_DWORD *)(a6 + 8),
          pContext,
          (char)v29,
          *(_QWORD *)(pContext + 48),
          a1,
          *(_QWORD *)(pContext + 96),
          *(_QWORD *)(pContext + 80),
          *(_DWORD *)(a6 + 36),
          *(_QWORD *)(pContext + 88),
          v16);
      }
      if ( (byte_1400712A1 & 1) != 0 )
        McTemplateK0sxxxqhqp_EtwWriteTransfer(
          v93,
          (unsigned int)SmbReceiveInterim,
          pContext + 312,
          (_DWORD)v185,
          v183,
          SBYTE8(v183),
          *(_QWORD *)(a6 + 40),
          *(_DWORD *)(a6 + 36),
          SBYTE12(v184),
          0,
          *(_QWORD *)(*(_QWORD *)(pContext + 96) + 392LL));
      v13 = 0;
      if ( (*(_DWORD *)(pContext + 68) & 0x40) != 0 )
      {
        *(_QWORD *)(pContext + 208) = 0x7FFFFFFFFFFFFFFFLL;
LABEL_158:
        v49 = 0;
        goto LABEL_75;
      }
      v94 = dword_14007D08C;
      if ( *(_DWORD *)(*(_QWORD *)(pContext + 72) + 768LL) )
        v94 = *(_DWORD *)(*(_QWORD *)(pContext + 72) + 768LL);
      if ( *(_DWORD *)(pContext + 216) )
      {
        v95 = *(unsigned int *)(pContext + 216);
      }
      else if ( dword_14007D090 )
      {
        v95 = (unsigned int)dword_14007D090;
      }
      else
      {
        v95 = (unsigned int)(4 * v94);
      }
      v96 = *(_QWORD *)(pContext + 208);
      v97 = 10000000 * v95 + MEMORY[0xFFFFF78000000008];
      if ( v97 <= v96 && v96 != 0x7FFFFFFFFFFFFFFFLL )
        goto LABEL_158;
      *(_QWORD *)(pContext + 208) = v97;
      v49 = 0;
LABEL_75:
      if ( (!v179 || _InterlockedExchangeAdd((volatile signed __int32 *)(pContext + 36), 0xFFFFFFFF) == 1)
        && v49
        && (unsigned __int8)SmbCepCheckExchangeForDeferredAbortOrIfFinalizable(pContext) )
      {
        v68 = *(_QWORD *)(pContext + 48);
        if ( (*(_DWORD *)(pContext + 68) & 0x100000) == 0 )
        {
          Irp = 0;
          goto LABEL_161;
        }
        v81 = 0;
        Irp = 0;
        if ( !*(_QWORD *)(pContext + 56) && !*(_DWORD *)(pContext + 16) )
        {
          for ( i = *(_QWORD *)(pContext + 160); ; i = *(_QWORD *)(v100 + 8) )
          {
            v100 = 0;
            if ( i != pContext + 160 )
              v100 = i - 8;
            if ( !v100 )
            {
              v81 = (IRP *)RxAttemptTurboIoCompletion(v68, SmbCepPrepareExchangeForTurboCompletionLite, pContext);
              Irp = v81;
              goto LABEL_160;
            }
            if ( *(_DWORD *)(v100 + 48) )
              break;
          }
          Irp = 0;
          goto LABEL_161;
        }
LABEL_160:
        if ( !v81 )
        {
LABEL_161:
          v82 = SmbCepCompleteExchangeLiteEx((PVOID)pContext);
          v83 = (unsigned __int8)v189;
          if ( v82 == -1073741802 )
            v83 = 1;
          v189 = v83;
        }
      }
      if ( v180 )
      {
        v72 = v190;
        if ( v190 )
        {
          KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(v190 + 8));
          SmbCseDereferenceCompoundingKey(v72);
        }
        else
        {
          KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(pContext + 24));
          SmbCeDereferenceExchange((PVOID)pContext);
        }
        v30 = a5;
        goto LABEL_138;
      }
      if ( v190 )
      {
        SmbCeReleaseCompoundingKeyLock(v190);
      }
      else
      {
        KeReleaseSpinLock((PKSPIN_LOCK)(pContext + 24), *(_BYTE *)(pContext + 32));
        SmbCeDereferenceExchange((PVOID)pContext);
      }
      v30 = a5;
      goto LABEL_81;
    }
    KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
LABEL_31:
    pContext = v28[7];
    v36 = 0;
    v37 = *(_QWORD *)(pContext + 56);
    v190 = v37;
    *((_DWORD *)v28 + 184) = a3;
    *((_BYTE *)v28 + 85) = 0;
    if ( a10 )
    {
      v36 = *(_DWORD *)a10;
      if ( *(int *)a10 < 0 )
      {
        *((_DWORD *)v28 + 195) = a4;
        *((_BYTE *)v28 + 786) = 1;
      }
    }
    if ( (v28[109] & 0x40000000) != 0 && (v36 & 0x10000000) == 0 )
    {
      v13 = -1073700864;
      *(_QWORD *)&v187 = 3221266432LL;
      SmbCseUpdateBufferContextStatus(v28, 3221266432LL);
      if ( (byte_1400712A4 & 2) != 0 )
        McTemplateK0hxxqhzr4qhzr7qqqbr11qbr13_EtwWriteTransfer(
          a6,
          (MEMORY[0xFFFFF78000000008] - *(_QWORD *)(pContext + 200)) / 0x2710uLL,
          *(_WORD *)(v186 + 360) >> 1,
          *(unsigned __int16 *)(a6 + 12),
          v183,
          *(_QWORD *)(a6 + 40),
          *(_DWORD *)(a6 + 36),
          *(_WORD *)(v16 + 80) >> 1,
          *(_QWORD *)(v16 + 88));
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_qq(
          WPP_GLOBAL_Control->AttachedDevice,
          17,
          WPP_1ffd7df1a0ca364e8ae776b5c429ef78_Traceguids,
          v28,
          pContext);
      }
      v76 = SmbCseInvalidateMemoryRegistrationAsync(v28);
      if ( v76 != -1073741816 )
      {
        v49 = 1;
        if ( v76 != 259 )
          *((_BYTE *)v28 + 87) = 0;
        goto LABEL_75;
      }
      goto LABEL_74;
    }
    if ( v37 )
    {
      KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(v37 + 8));
      SmbCseDereferenceCompoundingKey(v190);
    }
    else
    {
      KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(pContext + 24));
      SmbCeDereferenceExchange((PVOID)pContext);
    }
    KeLowerIrql(v181);
    v180 = 0;
    if ( BYTE14(v184) )
    {
      if ( a10 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          v177[1] = (PIRP)16;
          v177[0] = (PIRP)(a10 + 32);
          v145 = *(_OWORD *)v177;
          v177[1] = (PIRP)16;
          v177[0] = (PIRP)(a10 + 16);
          v188 = v145;
          v146 = *(_OWORD *)v177;
          v177[1] = 0;
          v177[0] = (PIRP)(a1 + 428);
          v147 = *(_WORD *)(a1 + 428);
          v194 = v146;
          v177[1] = (PIRP)SOCKADDR_SIZE(v147);
          v148 = *(_OWORD *)v177;
          v177[1] = 0;
          v177[0] = (PIRP)(a1 + 400);
          v149 = *(_WORD *)(a1 + 400);
          v195 = v148;
          v150 = SOCKADDR_SIZE(v149);
          v177[1] = (PIRP)v150;
          v153 = 69;
          if ( (v151 & 0x8000) == 0 )
            v153 = 32;
          v127 = (v151 & 0x1000) != 0;
          v154 = 83;
          if ( !v127 )
            v154 = 32;
          WPP_SF_d_SOCKADDR__SOCKADDR_ccsDDDLqqqqqiqLqq_zb__zb_(
            *(_QWORD *)(v152 + 24),
            v150,
            v154,
            *(unsigned __int8 *)(*(_QWORD *)(*(_QWORD *)(pContext + 72) + 24LL) + 1312LL),
            (__int64)v177,
            (__int64)&v195,
            v154,
            v153,
            (__int64)v185,
            v204,
            a3,
            SBYTE8(v183),
            SBYTE4(v184),
            pContext,
            (char)v28,
            *(_QWORD *)(pContext + 48),
            a1,
            *(_QWORD *)(pContext + 96),
            *(_QWORD *)(a6 + 40),
            *(_QWORD *)(pContext + 80),
            *(_DWORD *)(a6 + 36),
            *(_QWORD *)(pContext + 88),
            v16,
            (__int64)&v194,
            (__int64)&v188);
        }
      }
      else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
             && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
             && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v177[1] = 0;
        v177[0] = (PIRP)(a1 + 428);
        v177[1] = (PIRP)SOCKADDR_SIZE(*(_WORD *)(a1 + 428));
        v138 = *(_OWORD *)v177;
        v177[1] = 0;
        v177[0] = (PIRP)(a1 + 400);
        v139 = *(_WORD *)(a1 + 400);
        v188 = v138;
        v140 = SOCKADDR_SIZE(v139);
        v143 = 69;
        v177[1] = (PIRP)v140;
        if ( (v141 & 0x8000) == 0 )
          v143 = 32;
        v127 = (v141 & 0x1000) != 0;
        v144 = 83;
        if ( !v127 )
          v144 = 32;
        WPP_SF_d_SOCKADDR__SOCKADDR_ccsDDDLqqqqqiqLqq(
          *(_QWORD *)(v142 + 24),
          v140,
          v144,
          *(unsigned __int8 *)(*(_QWORD *)(*(_QWORD *)(pContext + 72) + 24LL) + 1312LL),
          (__int64)v177,
          (__int64)&v188,
          v144,
          v143,
          (__int64)v185,
          v204,
          a3,
          SBYTE8(v183),
          SBYTE4(v184),
          pContext,
          (char)v28,
          *(_QWORD *)(pContext + 48),
          a1,
          *(_QWORD *)(pContext + 96),
          *(_QWORD *)(a6 + 40),
          *(_QWORD *)(pContext + 80),
          *(_DWORD *)(a6 + 36),
          *(_QWORD *)(pContext + 88),
          v16);
      }
      RxDiagnosticTrace(
        *(_QWORD *)(v18 + 16),
        1,
        "RECV: [%s] ([AsyncId]) ([%lx]) Creds %lx Status %lx",
        v185,
        DWORD2(v183),
        WORD6(v184),
        DWORD1(v184));
      if ( (byte_1400712A1 & 1) != 0 )
        McTemplateK0sxxxqhqp_EtwWriteTransfer(
          a6,
          (unsigned int)SmbReceiveAsync,
          pContext + 312,
          (_DWORD)v185,
          v183,
          SBYTE8(v183),
          *(_QWORD *)(a6 + 40),
          *(_DWORD *)(a6 + 36),
          SBYTE12(v184),
          0,
          *(_QWORD *)(*(_QWORD *)(pContext + 96) + 392LL));
    }
    else
    {
      if ( (_DWORD)v184 == 259 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_1ffd7df1a0ca364e8ae776b5c429ef78_Traceguids, 259);
        }
        LODWORD(v184) = -1073741629;
      }
      if ( a10 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          if ( v178 )
          {
            v119 = 0;
            LOBYTE(v202) = 0;
          }
          else
          {
            v119 = *(_QWORD *)(a6 + 40);
            v202 = *(_DWORD *)(a6 + 36);
          }
          *(_QWORD *)&v188 = v119;
          v177[1] = (PIRP)16;
          v177[0] = (PIRP)(a10 + 32);
          v162 = *(_OWORD *)v177;
          v177[1] = (PIRP)16;
          v177[0] = (PIRP)(a10 + 16);
          v195 = v162;
          v163 = *(_OWORD *)v177;
          v177[1] = 0;
          v177[0] = (PIRP)(a1 + 428);
          v164 = *(_WORD *)(a1 + 428);
          v194 = v163;
          v177[1] = (PIRP)SOCKADDR_SIZE(v164);
          v165 = *(_OWORD *)v177;
          v177[1] = 0;
          v177[0] = (PIRP)(a1 + 400);
          v166 = *(_WORD *)(a1 + 400);
          v197[0] = v165;
          v177[1] = (PIRP)SOCKADDR_SIZE(v166);
          v169 = 69;
          if ( (v167 & 0x8000) == 0 )
            v169 = 32;
          v127 = (v167 & 0x1000) != 0;
          v170 = 83;
          if ( !v127 )
            v170 = 32;
          WPP_SF_d_SOCKADDR__SOCKADDR_ccsDDiDDLqqqqqiqLqq_zb__zb_(
            *(_QWORD *)(v168 + 24),
            WORD6(v184),
            v170,
            *(unsigned __int8 *)(*(_QWORD *)(*(_QWORD *)(pContext + 72) + 24LL) + 1312LL),
            (__int64)v177,
            (__int64)v197,
            v170,
            v169,
            (__int64)v185,
            v204,
            a3,
            v183,
            *((_DWORD *)v28 + 20),
            SBYTE12(v184),
            SBYTE4(v184),
            pContext,
            (char)v28,
            *(_QWORD *)(pContext + 48),
            a1,
            *(_QWORD *)(pContext + 96),
            v188,
            *(_QWORD *)(pContext + 80),
            v202,
            *(_QWORD *)(pContext + 88),
            v16,
            (__int64)&v194,
            (__int64)&v195);
        }
      }
      else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
             && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
             && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        if ( v178 )
        {
          v98 = 0;
          LOBYTE(v199) = 0;
        }
        else
        {
          v98 = *(_QWORD *)(a6 + 40);
          v199 = *(_DWORD *)(a6 + 36);
        }
        *(_QWORD *)&v188 = v98;
        v177[1] = 0;
        v177[0] = (PIRP)(a1 + 428);
        v177[1] = (PIRP)SOCKADDR_SIZE(*(_WORD *)(a1 + 428));
        v155 = *(_OWORD *)v177;
        v177[1] = 0;
        v177[0] = (PIRP)(a1 + 400);
        v156 = *(_WORD *)(a1 + 400);
        v195 = v155;
        v157 = SOCKADDR_SIZE(v156);
        v160 = 69;
        v177[1] = (PIRP)v157;
        if ( (v158 & 0x8000) == 0 )
          v160 = 32;
        v127 = (v158 & 0x1000) != 0;
        v194 = *(_OWORD *)v177;
        v161 = 83;
        if ( !v127 )
          v161 = 32;
        WPP_SF_d_SOCKADDR__SOCKADDR_ccsDDiDDLqqqqqiqLqq(
          *(_QWORD *)(v159 + 24),
          WORD6(v184),
          v161,
          *(unsigned __int8 *)(*(_QWORD *)(*(_QWORD *)(pContext + 72) + 24LL) + 1312LL),
          (__int64)&v194,
          (__int64)&v195,
          v161,
          v160,
          (__int64)v185,
          v204,
          a3,
          v183,
          *((_DWORD *)v28 + 20),
          SBYTE12(v184),
          SBYTE4(v184),
          pContext,
          (char)v28,
          *(_QWORD *)(pContext + 48),
          a1,
          *(_QWORD *)(pContext + 96),
          v188,
          *(_QWORD *)(pContext + 80),
          v199,
          *(_QWORD *)(pContext + 88),
          v16);
      }
      RxDiagnosticTrace(
        *(_QWORD *)(v18 + 16),
        1,
        "RECV: [%s] (Mid) (%I64x) Creds %lx Status %lx",
        v185,
        (_QWORD)v183,
        WORD6(v184),
        DWORD1(v184));
      if ( (byte_1400712A1 & 1) != 0 )
      {
        if ( v178 )
        {
          LOBYTE(v50) = 0;
          v51 = 0;
        }
        else
        {
          v50 = *(_DWORD *)(a6 + 36);
          v51 = *(_DWORD *)(a6 + 40);
        }
        McTemplateK0sxxxqhqp_EtwWriteTransfer(
          v51,
          (unsigned int)SmbReceive,
          pContext + 312,
          (_DWORD)v185,
          v183,
          SBYTE8(v183),
          v51,
          v50,
          SBYTE12(v184),
          SBYTE4(v184),
          *(_QWORD *)(*(_QWORD *)(pContext + 96) + 392LL));
      }
    }
    _InterlockedAdd64(
      (volatile signed __int64 *)MRxSmbLegacyPerfCtrs + 32 * (unsigned __int64)HIDWORD(KeGetPcr()[1].LockArray),
      a3);
    if ( (unsigned __int8)RxPerProcessCountersEnabled() )
    {
      v38 = *(_QWORD *)(pContext + 48);
      if ( v38 && *(int *)(v38 + 120) >= 0 )
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
    v39 = v184;
    if ( *(_QWORD *)(pContext + 80) && (_DWORD)v184 == -1073741309 )
    {
      v73 = SmbCeAcquireSpinLock(v186);
      v74 = *(_QWORD *)(pContext + 80);
      v75 = v73;
      if ( *(_DWORD *)(pContext + 108) == *(_DWORD *)(v74 + 264) )
      {
        *(_QWORD *)&v187 = (unsigned int)v184;
        SmbCeDisconnectSessionEntryLite(v74, 0, (unsigned int)v184);
      }
      v171 = (volatile LONG *)(v186 + 1920);
      *(_DWORD *)(v186 + 2352) = -1;
      ExReleaseSpinLockExclusive(v171, v75);
      v39 = v184;
    }
    if ( *(_QWORD *)(pContext + 88) && (v39 == -1073741623 || v39 == -1073741620) )
    {
      v69 = SmbCeAcquireSpinLock(v186);
      v70 = *(_QWORD *)(pContext + 88);
      v71 = v69;
      if ( *(_DWORD *)(pContext + 112) == *(_DWORD *)(v70 + 264) )
      {
        *(_QWORD *)&v187 = (unsigned int)v184;
        SmbCeDisconnectVNetRootContextLite(v70, 0, (unsigned int)v184);
      }
      v172 = (volatile LONG *)(v186 + 1920);
      *(_DWORD *)(v186 + 2352) = -1;
      ExReleaseSpinLockExclusive(v172, v71);
      v39 = v184;
    }
    if ( *(_QWORD *)(pContext + 80) && v39 == -1073740964 )
    {
      v66 = SmbCeAcquireSpinLock(v186);
      SmbCeRecoverSessionEntryLite(*(_QWORD *)(pContext + 80), (unsigned int)v184);
      v67 = (volatile LONG *)(v186 + 1920);
      *(_DWORD *)(v186 + 2352) = -1;
      ExReleaseSpinLockExclusive(v67, v66);
    }
    v40 = (*(__int64 (__fastcall **)(ULONG_PTR, _QWORD *, __int128 *, _QWORD, unsigned int, unsigned int *, __int64, __int64))(*(_QWORD *)(pContext + 232) + 8LL))(
            pContext,
            v28,
            &v183,
            v204,
            a3,
            a5,
            a6,
            a10);
    v41 = v190;
    v13 = v40;
    if ( v190 )
    {
      _InterlockedIncrement((volatile signed __int32 *)(v190 + 4));
      *(_BYTE *)(v41 + 16) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v41 + 8));
    }
    else
    {
      v42 = _InterlockedIncrement((volatile signed __int32 *)(pContext + 4));
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_qDD(
          WPP_GLOBAL_Control->AttachedDevice,
          33,
          WPP_d39beb3e593835eae73483c3886eb046_Traceguids,
          pContext,
          v42 - 1,
          v42);
      }
      *(_BYTE *)(pContext + 32) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(pContext + 24));
    }
    v43 = a5;
    if ( v13 != -1073741802 )
    {
      *((_DWORD *)v28 + 1) |= 0x400u;
      *a5 = a3;
    }
    *((_DWORD *)v28 + 185) = *a5;
    v44 = _InterlockedExchange64(v28 + 95, 0);
    if ( !v44 )
    {
LABEL_58:
      *a9 = 0;
      v45 = v28[94];
      if ( v45 )
      {
        v46 = *(_DWORD *)(v45 + 40);
      }
      else
      {
        if ( !v28[90] )
        {
LABEL_62:
          if ( *v43 > a3 )
            *v43 = a3;
          if ( *a9 > a3 )
            *a9 = a3;
          v47 = *(_QWORD *)(v16 + 56);
          if ( v47 )
          {
            v48 = (*(__int64 (__fastcall **)(_QWORD *, __int128 *, __int64, _QWORD, unsigned int, unsigned int *))(v47 + 880))(
                    v28,
                    &v183,
                    a6,
                    v204,
                    a3,
                    v43);
            if ( v48 != -1073741822 && v48 != -1073741802 && v48 < 0 )
            {
              *(_QWORD *)&v187 = (unsigned int)v48;
              SmbCseUpdateBufferContextStatus(v28, (unsigned int)v48);
              v43 = a5;
              v13 = 0;
              *a5 = a3;
              goto LABEL_72;
            }
            v43 = a5;
          }
          if ( v13 != -1073741802 )
          {
LABEL_72:
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              WPP_SF_LLL(
                WPP_GLOBAL_Control->AttachedDevice,
                25,
                WPP_1ffd7df1a0ca364e8ae776b5c429ef78_Traceguids,
                v204,
                a3,
                *v43);
            }
            goto LABEL_74;
          }
          v77 = (_QWORD *)v28[94];
          if ( !v77 )
            v77 = (_QWORD *)v28[90];
          v78 = a7;
          *a7 = v77;
          v79 = a3 - *v43;
          v80 = *a9;
          if ( *a9 >= v79 )
          {
            *a9 = v79;
LABEL_156:
            ++*((_BYTE *)v28 + 87);
            *a8 = v28;
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
              (_DWORD)v28,
              *v43,
              *v78,
              *a9);
            v49 = 0;
            goto LABEL_75;
          }
          LODWORD(v186) = v79 - v80;
          v84 = v79 - v80;
          *(_QWORD *)&v188 = 0;
          *(_QWORD *)&v192 = 0;
          v85 = 0x2000;
          while ( 1 )
          {
            v206 = v84;
            if ( !v84 )
            {
              v78 = a7;
              v86 = *a7;
              for ( j = (_QWORD *)**a7; j; j = (_QWORD *)*j )
                v86 = j;
              v88 = v186;
              *v86 = v188;
              *a9 += v88;
              v43 = a5;
              goto LABEL_156;
            }
            v173 = v84;
            if ( v84 >= v85 )
              v173 = v85;
            v203 = v173;
            Mdl = (IRP *)IoAllocateMdl(GlobalTrashBuffer, v173, 0, 0, 0);
            v177[0] = Mdl;
            if ( !Mdl )
              break;
            MmBuildMdlForNonPagedPool((PMDL)Mdl);
            v175 = (PIRP *)v192;
            *(PIRP *)&v192 = v177[0];
            if ( v175 )
              *v175 = v177[0];
            else
              *(PIRP *)&v188 = v177[0];
            v85 = v203;
            v84 = v206 - v203;
          }
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_e7b6edac773635936dfdf853ea49dd93_Traceguids);
          }
          RxFreeMdlChain(v188);
          *(_QWORD *)&v187 = 3221225626LL;
          SmbCseUpdateBufferContextStatus(v28, 3221225626LL);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_1ffd7df1a0ca364e8ae776b5c429ef78_Traceguids);
          }
LABEL_74:
          v49 = 1;
          goto LABEL_75;
        }
        v46 = *((_DWORD *)v28 + 187);
      }
      *a9 = v46;
      goto LABEL_62;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 29, WPP_ca2d5009ac97347054a9c333c3e72a58_Traceguids, v28);
    }
    v101 = *(_QWORD *)(*(_QWORD *)(v28[7] + 96LL) + 392LL);
    v200 = v101;
    if ( *(_DWORD *)(v101 + 320) == 2 )
    {
      TopLevelIrp = IoGetTopLevelIrp();
      v103 = (IRP *)v28[7];
      v177[0] = TopLevelIrp;
      IoSetTopLevelIrp(v103);
      if ( (_QWORD *)v28[43] != v28 + 43 )
        __int2c();
      v28[68] = *(_QWORD *)(v200 + 104) & 0xFFFFFFFFFFFFFFF8uLL | 6;
      RxCeTrackTransportOpEx(v28 + 66, 1, *(_QWORD *)(v200 + 104), v44);
      v104 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD, _DWORD, _QWORD *, __int64 (__fastcall *)()))(SmbdFastDispatch + 24))(
               *(_QWORD *)(v200 + 104),
               v44,
               *((unsigned __int8 *)v28 + 786),
               *((unsigned int *)v28 + 195),
               *((_DWORD *)v28 + 187),
               v28,
               SmbCeMemoryDeregisterCompleteInd);
      v105 = v104;
      if ( v104 != 259 )
        RxCeUntrackTransportOpEx(v28 + 66, v104);
      IoSetTopLevelIrp(v177[0]);
    }
    else
    {
      if ( *(_DWORD *)(v101 + 320) != 3 )
      {
        *(_BYTE *)(v192 + 786) = 0;
LABEL_358:
        *((_BYTE *)v28 + 87) = 0;
LABEL_227:
        v43 = a5;
        goto LABEL_58;
      }
      v105 = VmbusInvalidateBufferRegistration(v101, v44);
    }
    *((_BYTE *)v28 + 786) = 0;
    if ( v105 == -1073741816 || v105 == 259 )
      goto LABEL_227;
    goto LABEL_358;
  }
  *(_DWORD *)(v18 + 144) = *(_DWORD *)(v18 + 96);
  if ( v29 )
    goto LABEL_25;
LABEL_28:
  if ( BYTE14(v184) )
  {
    while ( 1 )
    {
      if ( v26 )
        goto LABEL_253;
      while ( 1 )
      {
        KeAcquireInStackQueuedSpinLockAtDpcLevel((PKSPIN_LOCK)(v18 + 256), &LockHandle);
        v198 = 1;
LABEL_253:
        v28 = 0;
        v115 = (_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 512) + 112LL) + 16LL * (BYTE8(v183) >> 2));
        for ( k = (_QWORD *)*v115; k != v115; v28 = 0 )
        {
          v28 = k - 3;
          if ( k[2] == *((_QWORD *)&v183 + 1) )
            break;
          k = (_QWORD *)*k;
        }
        if ( !v28 )
          goto LABEL_29;
        if ( !(unsigned __int8)SmbCeTryToAcquireCompoundingKeyOrExchangeLockAtDpc(*(_QWORD *)(v28[7] + 56LL), v28[7]) )
          break;
        _InterlockedIncrement((volatile signed __int32 *)(v28[7] + 36LL));
        v179 = 1;
        SmbCseDissociateAsyncIdFromBufferContextLite(v117, v28);
        v28[105] = 0;
        if ( v198 )
          goto LABEL_29;
      }
      KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
      v26 = 0;
      v198 = 0;
    }
  }
LABEL_29:
  KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
  if ( v28 )
  {
    *(_QWORD *)&v192 = v28;
    goto LABEL_31;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_1ffd7df1a0ca364e8ae776b5c429ef78_Traceguids, a1);
  }
  v30 = a5;
  v13 = 0;
  *a5 = a3;
LABEL_138:
  KeLowerIrql(v181);
LABEL_81:
  if ( (_BYTE)v189 )
  {
    v201 = *(_QWORD *)(pContext + 72);
    v177[0] = *(PIRP *)(v201 + 24);
    if ( KeGetCurrentIrql() >= 2u && (*(_DWORD *)(pContext + 68) & 0x40000) == 0 || *(_DWORD *)(a1 + 320) == 4 )
    {
      v109 = 0;
    }
    else
    {
      v107 = *(_QWORD *)(v201 + 56);
      if ( !v107
        || (v108 = *(__int64 (__fastcall **)(ULONG_PTR))(v107 + 912)) == 0
        || (v109 = v108(pContext), v109 != -1069481981) )
      {
        v110 = *(_QWORD *)(pContext + 232);
        *(_QWORD *)(pContext + 208) = 0;
        *(_DWORD *)(pContext + 40) = 8;
        v109 = (*(__int64 (__fastcall **)(ULONG_PTR))(v110 + 32))(pContext);
        if ( v109 != -1069481981 )
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
      KeBugCheckEx(0x27u, 0x43584D5Fu, pContext, v109, 0);
    LOBYTE(v106) = 20;
    RDR_PERF_ENTER(pContext + 512, v106);
    SmbCeIncrementTeardownOpCounter(v177[0], pContext, 7);
    RxPostToWorkerThread(
      (PRDBSS_DEVICE_OBJECT)v177[0],
      NormalWorkQueue,
      (PRX_WORK_QUEUE_ITEM)(pContext + 240),
      SmbCepFinalizeExchangeWorker,
      (PVOID)pContext);
  }
LABEL_82:
  ExReleaseRundownProtection(RunRef);
  if ( v182 )
    SmbCeDereferenceServerEntryEx(v16);
  if ( Irp )
    IofCompleteRequest(Irp, 1);
  if ( v13 != -1073741802 )
LABEL_87:
    *v30 = a3;
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
0x1400072af  test    cs:byte_1400712A1, 1
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
