# KeBugCheck2

- ea: `0x14051baf0`
- end: `0x14051cbc6`
- name: `KeBugCheck2`
- size: `4310`
- prototype: ``
- caller_count: `1`
- callee_count: `54`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140541bf0`

## callees

- `0x1402495f0`
- `0x140249660`
- `0x1402a2f90`
- `0x1402e3d90`
- `0x1402fa540`
- `0x140321760`
- `0x1403ce040`
- `0x1404de430`
- `0x14051abac`
- `0x14051baf0`
- `0x14051cbcc`
- `0x140530a40`
- `0x140532fa4`
- `0x140532fdc`
- `0x140536910`
- `0x140538a18`
- `0x1405392e0`
- `0x14053ddc4`
- `0x14054e51c`
- `0x14058cf50`
- `0x1405c3954`
- `0x1405c8e64`
- `0x1405c8eec`
- `0x1405c9320`
- `0x1405d19cc`
- `0x1405d2590`
- `0x1405d2820`
- `0x1405e996c`
- `0x1405e9dfc`
- `0x1405ebf10`
- `0x1405ec140`
- `0x1405ec20c`
- `0x1405ec27c`
- `0x1405ec2c0`
- `0x1405ec32c`
- `0x1405ec678`
- `0x1405eca04`
- `0x1405ecd94`
- `0x1405ed030`
- `0x1405ed130`
- `0x1405ed310`
- `0x1405ed64c`
- `0x1405f8f1c`
- `0x1405fa020`
- `0x1405fa110`
- `0x1405fca74`
- `0x1405fd44c`
- `0x14068e498`
- `0x1406a1690`
- `0x1406d7444`

## string_xrefs

- `0x14051bee6`: `\nA bugcheck occurred during the late stages of hibernate suspend or resume.\nDue to verification temporarily enabled by Po during this time,\nregular bugcheck processing may not work.\n\n`
- `0x14051befc`: `Memory was accessed during this time that was not properly marked\nfor the boot phase of hibernate! Check the callstack and parameters\nto find the pages that need to be marked.\n\n`

## pseudocode

```c
void __fastcall __noreturn KeBugCheck2(
        unsigned int a1,
        __int64 a2,
        unsigned __int64 a3,
        const CHAR *a4,
        unsigned __int64 a5,
        __int64 a6)
{
  unsigned __int64 v6; // r14
  const CHAR *v7; // r12
  __int64 v8; // r13
  const CHAR *v9; // rdi
  char v11; // bl
  __int64 v12; // rsi
  __int64 v13; // rax
  __int64 CurrentIrql; // rcx
  signed __int32 v15; // eax
  unsigned int v16; // edx
  signed __int32 v17; // ecx
  char v18; // bl
  signed __int32 v19; // eax
  unsigned int v20; // edx
  signed __int32 v21; // ecx
  int v22; // ecx
  unsigned __int8 v23; // r14
  PCSTR v24; // r15
  unsigned __int64 v25; // rdi
  unsigned __int64 v26; // rbx
  struct _KTHREAD *v27; // rcx
  unsigned __int64 v28; // r9
  const void *v29; // rdx
  size_t v30; // r8
  struct _KPRCB *CurrentPrcb; // r15
  unsigned int v32; // ebx
  _CONTEXT *Context; // rax
  char *v34; // rcx
  __int64 v35; // rdx
  __int64 v36; // r9
  __int128 v37; // xmm1
  __int64 v38; // rdx
  __int64 v39; // r8
  __int64 *v40; // rdx
  __int64 v41; // r14
  char v42; // r13
  __int64 v43; // rax
  __int64 v44; // rax
  __int64 v45; // rcx
  __int64 v46; // rax
  __int64 v47; // rax
  __int64 UnloadedDriver; // rax
  struct _KTHREAD *v49; // rcx
  _KPROCESS *Process; // rcx
  __int64 v51; // rcx
  bool v52; // si
  unsigned __int8 v53; // r14
  __int64 v54; // rdx
  wchar_t i; // cx
  __int64 v56; // rcx
  char v57; // bl
  char v58; // bl
  __int64 v59; // rdi
  __int64 v60; // rsi
  __int64 v61; // r14
  __int64 v62; // r15
  int v63; // r12d
  int v64; // r13d
  bool v65; // r14
  __int64 v66; // rdx
  __int64 v67; // rcx
  __int64 v68; // r8
  __int64 v69; // r9
  __int64 v70; // rdx
  __int64 v71; // r8
  __int64 v72; // rcx
  __int64 v73; // rdx
  __int64 v74; // rcx
  __int64 v75; // r8
  __int64 v76; // rcx
  __int64 v77; // rcx
  __int64 v78; // r8
  _PROC_PERF_DOMAIN *Domain; // rax
  int v80; // ecx
  unsigned int v81; // eax
  __int64 v82; // rcx
  __int64 v83; // rdi
  _CONTEXT *v84; // rax
  char *v85; // rcx
  __int128 v86; // xmm1
  char v87; // [rsp+50h] [rbp-B0h]
  char v88; // [rsp+54h] [rbp-ACh]
  char v89; // [rsp+55h] [rbp-ABh]
  bool v90; // [rsp+56h] [rbp-AAh]
  char v91; // [rsp+57h] [rbp-A9h] BYREF
  PCSTR Format; // [rsp+58h] [rbp-A8h] BYREF
  PCSTR v93; // [rsp+60h] [rbp-A0h] BYREF
  bool v94; // [rsp+68h] [rbp-98h]
  bool v95; // [rsp+69h] [rbp-97h]
  __int64 v96; // [rsp+70h] [rbp-90h]
  char v97; // [rsp+78h] [rbp-88h]
  char v98; // [rsp+7Ah] [rbp-86h]
  unsigned int v99; // [rsp+80h] [rbp-80h] BYREF
  unsigned int Number; // [rsp+88h] [rbp-78h] BYREF
  __int64 v101; // [rsp+90h] [rbp-70h]
  int v102; // [rsp+98h] [rbp-68h]
  __int64 v103; // [rsp+A0h] [rbp-60h] BYREF
  struct _KTHREAD *CurrentThread; // [rsp+A8h] [rbp-58h]
  __int64 (__fastcall *v105)(); // [rsp+B0h] [rbp-50h]
  __int64 v106; // [rsp+B8h] [rbp-48h]
  __int64 v107; // [rsp+C0h] [rbp-40h]
  __int64 v108; // [rsp+C8h] [rbp-38h]
  const CHAR *v109; // [rsp+D0h] [rbp-30h]
  struct _KAFFINITY_EX v110; // [rsp+E0h] [rbp-20h] BYREF
  char v111[1232]; // [rsp+2F0h] [rbp+1F0h] BYREF
  char pszDest[192]; // [rsp+7C0h] [rbp+6C0h] BYREF

  v6 = a3;
  v7 = (const CHAR *)a5;
  v8 = a2;
  v106 = a3;
  v9 = a4;
  v107 = a2;
  v99 = a1;
  v96 = a6;
  v109 = a4;
  memset_0(&v110, 0, sizeof(v110));
  v11 = 0;
  pszDest[0] = 0;
  v12 = 0;
  CurrentThread = KeGetCurrentThread();
  v103 = 0;
  v105 = KiBugCheckProgress;
  v95 = IopAutoReboot != 0;
  v91 = 0;
  v87 = 0;
  v98 = 0;
  v108 = 0;
  v101 = 0;
  v90 = 1;
  v94 = 1;
  v102 = 0;
  if ( !_InterlockedExchange(&KiBugCheckDataInitialized, 1) )
  {
    v13 = v99;
    if ( v99 == -1073741103 )
    {
      v13 = 195;
      v99 = 195;
    }
    KiBugCheckData[0] = v13;
    qword_140F21908 = v8;
    qword_140F21910 = v6;
    qword_140F21918 = (__int64)v9;
    qword_140F21920 = a5;
    if ( !WheapDispatchPtr.DeviceLock.Header.LockNV )
      _InterlockedExchange(&WheaIpmiHwLogLocked, 1);
    KiInvokeBugCheckEntryCallbacks(8, 0, 0);
    if ( dword_140E0E1D4 >= 0 )
      KiBugCheckSelLogDataCheckPoint(2147483757LL, &Uuid, 16);
    else
      KiBugCheckSelLogError(2147483758LL, (unsigned int)dword_140E0E1D4, 0);
    IoNotifyDumpEx(4, 0, 0);
  }
  if ( (HvlpFlags & 2) != 0 )
    HvlNotifyRootCrashdump(4);
  v93 = 0;
  Format = 0;
  Number = 0;
  if ( KeGetCurrentIrql() < 2u )
  {
    CurrentIrql = KeGetCurrentIrql();
    if ( (_BYTE)CurrentIrql != 2 )
      __writecr8(2u);
    if ( KiIrqlFlags )
      KiRaiseIrqlProcessIrqlFlags(CurrentIrql, 2);
  }
  if ( KeGetCurrentThread()->InitialStack )
  {
    v18 = KeQueryCurrentStackInformation(&Number, &Format, &v93);
    v19 = KiBugCheckActive;
    v20 = (16 * KeGetCurrentPrcb()->Number) | 3;
    do
    {
      if ( (v19 & 3) == 3 )
      {
        v11 = 0;
        LOBYTE(_R8) = 0;
        v88 = 0;
        goto LABEL_51;
      }
      v21 = v19;
      v19 = _InterlockedCompareExchange(&KiBugCheckActive, v20, v19);
    }
    while ( v19 != v21 );
    IoNotifyDumpEx(6, 0, 0);
    if ( v18 )
    {
      if ( Number > 9 || (v22 = 929, !_bittest(&v22, Number)) )
      {
        v23 = 1;
        v24 = Format;
        v25 = 147456;
        v26 = 0;
        if ( (unsigned __int64)(v93 - Format) > 0x24000 || (v25 = v93 - Format, v93 != Format) )
        {
          do
          {
            if ( (unsigned __int8)MmIsAddressValidEx(&v24[v26], 0) )
              memmove(&KiPreBugcheckStackSaveArea[v26 / 8], &v24[v26], 0x1000u);
            else
              v23 = 0;
            v26 += 4096LL;
          }
          while ( v26 < v25 );
          v8 = v107;
          v12 = v108;
        }
        IoNotifyDumpEx(7, 0, v23);
        v9 = v109;
        v6 = v106;
      }
    }
    v11 = 0;
    if ( (_BYTE)KiKernelCetEnabled )
    {
      v27 = KeGetCurrentThread();
      __asm { rdsspq  r8 }
      v28 = (v27->KernelShadowStackLimit.AllFields & 0xFFFFFFFFFFFFF000uLL) + 4096;
      if ( _R8 > v28 && (void *)_R8 < (char *)v27->KernelShadowStackBase - 4096 )
      {
        v29 = (const void *)(_R8 - 256);
        if ( _R8 - 256 < v28 )
          v29 = (const void *)((v27->KernelShadowStackLimit.AllFields & 0xFFFFFFFFFFFFF000uLL) + 4096);
        v30 = _R8 - (_QWORD)v29;
        if ( v30 > 0x100 )
          v30 = 256;
        memmove(qword_140FC0350, v29, v30);
      }
    }
    LOBYTE(_R8) = 1;
    v88 = 1;
    goto LABEL_48;
  }
  v15 = KiBugCheckActive;
  v16 = (16 * KeGetCurrentPrcb()->Number) | 3;
  while ( (v15 & 3) != 3 )
  {
    v17 = v15;
    v15 = _InterlockedCompareExchange(&KiBugCheckActive, v16, v15);
    if ( v15 == v17 )
    {
      LOBYTE(_R8) = 1;
      goto LABEL_23;
    }
  }
  LOBYTE(_R8) = 0;
LABEL_23:
  v88 = _R8;
  if ( (_BYTE)_R8 )
  {
LABEL_48:
    if ( KiRecoveryCallbackCount <= 0 )
      KiBugcheckOwnerKeepsOthersFrozen = 1;
  }
LABEL_51:
  if ( KeSmapEnabled )
    __asm { stac }
  CurrentPrcb = KeGetCurrentPrcb();
  Number = CurrentPrcb->Number;
  if ( !KiHypervisorInitiatedCrashDump || (HvlpFlags & 2) == 0 )
  {
    KeSaveSupervisorState(CurrentPrcb->ExtendedSupervisorState, KeEnabledSupervisorXStateFeatures | 0x100, _R8);
    LOBYTE(_R8) = v88;
  }
  if ( qword_140EF9DD0 )
  {
    if ( PopSimulateHiberBugcheck )
      PoPowerDownActionInProgress = 0;
    if ( *(_BYTE *)(qword_140EF9DD0 + 2) )
    {
      if ( (_BYTE)_R8 )
      {
        v32 = v99;
        DbgPrintEx(
          0x65u,
          0,
          "\n"
          "A bugcheck occurred during the late stages of hibernate suspend or resume.\n"
          "Due to verification temporarily enabled by Po during this time,\n"
          "regular bugcheck processing may not work.\n"
          "\n");
        if ( v32 == 10 )
          DbgPrintEx(
            0x65u,
            0,
            "Memory was accessed during this time that was not properly marked\n"
            "for the boot phase of hibernate! Check the callstack and parameters\n"
            "to find the pages that need to be marked.\n"
            "\n");
        LOBYTE(_R8) = v88;
      }
      v105 = 0;
      v11 = 1;
      v88 = _R8;
    }
  }
  Context = CurrentPrcb->Context;
  v34 = v111;
  v35 = 9;
  v89 = v11;
  v36 = 128;
  do
  {
    *(_OWORD *)v34 = *(_OWORD *)&Context->P1Home;
    *((_OWORD *)v34 + 1) = *(_OWORD *)&Context->P3Home;
    *((_OWORD *)v34 + 2) = *(_OWORD *)&Context->P5Home;
    *((_OWORD *)v34 + 3) = *(_OWORD *)&Context->ContextFlags;
    *((_OWORD *)v34 + 4) = *(_OWORD *)&Context->SegGs;
    *((_OWORD *)v34 + 5) = *(_OWORD *)&Context->Dr1;
    *((_OWORD *)v34 + 6) = *(_OWORD *)&Context->Dr3;
    v37 = *(_OWORD *)&Context->Dr7;
    Context = (_CONTEXT *)((char *)Context + 128);
    *((_OWORD *)v34 + 7) = v37;
    v34 += 128;
    --v35;
  }
  while ( v35 );
  *(_OWORD *)v34 = *(_OWORD *)&Context->P1Home;
  *((_OWORD *)v34 + 1) = *(_OWORD *)&Context->P3Home;
  *((_OWORD *)v34 + 2) = *(_OWORD *)&Context->P5Home;
  *((_OWORD *)v34 + 3) = *(_OWORD *)&Context->ContextFlags;
  *((_OWORD *)v34 + 4) = *(_OWORD *)&Context->SegGs;
  if ( !(_BYTE)_R8 )
  {
    v52 = v94;
    v53 = 0;
    goto LABEL_186;
  }
  v97 = 0;
  Format = 0;
  if ( ViVerifierEnabled )
    VfNotifyVerifierOfEvent(2);
  if ( v99 == 229 )
  {
    KiScanBugCheckCallbackList(229, v35, _R8, v36);
    guard_dispatch_icall_no_overrides(0, v38, v39);
    HalReturnToFirmware(3);
  }
  v40 = KiBugCheckData;
  if ( v99 > 0xD1 )
  {
    switch ( v99 )
    {
      case 0xD8u:
        *(_QWORD *)&KiBugCheckDriver = v8 + 88;
        goto LABEL_84;
      case 0xE6u:
        if ( (_DWORD)v8 == 39 )
          IoAddTriageDumpDataBlock(v6, (PVOID)8);
        goto LABEL_84;
      case 0xEAu:
        *(_QWORD *)&KiBugCheckDriver = v9;
        goto LABEL_84;
      case 0xEFu:
        v9 = Format;
        v42 = 1;
        v41 = v96;
        v7 = Format;
        v87 = 1;
        goto LABEL_88;
    }
    if ( v99 != 252 )
    {
      switch ( v99 )
      {
        case 0x139u:
          v9 = Format;
          if ( v96 )
          {
            v41 = v96;
            v12 = *(_QWORD *)(v96 + 360);
            v101 = v12;
          }
          else
          {
            v12 = v6;
            v41 = 0;
            if ( v8 == 10 )
              v12 = a5;
            v101 = v12;
          }
          goto LABEL_86;
        case 0x13Du:
          v102 = 8;
          goto LABEL_84;
        case 0x14Fu:
          if ( v6 < 0x100 && a5 )
          {
            v49 = CurrentThread;
            if ( *(_QWORD *)(a5 + 8) )
              v49 = *(struct _KTHREAD **)(a5 + 8);
            CurrentThread = v49;
          }
          Process = KeGetCurrentThread()->ApcState.Process;
          v40 = (__int64 *)(HIDWORD(Process[3].ActiveGroupsMask.Masks[1]) >> 12);
          LOBYTE(v40) = (Process[3].ActiveGroupsMask.Masks[1] & 0x100000000000LL) == 0;
          v87 = (char)v40;
          goto LABEL_84;
        case 0x1C8u:
          v98 = 1;
          goto LABEL_84;
      }
      goto LABEL_126;
    }
    goto LABEL_141;
  }
  switch ( v99 )
  {
    case 0xD1u:
    case 0xAu:
      v12 = a5;
      v101 = a5;
      if ( a5 >= ExPoolCodeStart && a5 < ExPoolCodeEnd )
      {
        KiBugCheckData[0] = 197;
        goto LABEL_84;
      }
      v46 = KiPcToFileHeader(a5, &v103, 0, &v91);
      if ( v91 )
      {
        KiBugCheckDriverOffset = a5 - v46;
        *(_QWORD *)&KiBugCheckDriver = v103 + 88;
        v47 = KiPcToFileHeader(v8, &v103, 1, &v91);
        if ( !v47 )
        {
          UnloadedDriver = MmLocateUnloadedDriver(v8);
          v9 = Format;
          v41 = v96;
          v7 = Format;
          if ( UnloadedDriver )
          {
            KiBugCheckDriverOffset = v8 - *(_DWORD *)(UnloadedDriver + 16);
            *(_QWORD *)&KiBugCheckDriver = UnloadedDriver;
            KiBugCheckData[0] = 212;
          }
          goto LABEL_87;
        }
        KiBugCheckData[0] = 211;
        KiBugCheckDriverOffset = v8 - v47;
        *(_QWORD *)&KiBugCheckDriver = v103 + 88;
        goto LABEL_84;
      }
      v9 = Format;
      v41 = v96;
      v42 = 0;
      KiBugCheckData[0] = 209;
      if ( v46 )
      {
        KiBugCheckDriverOffset = a5 - v46;
        *(_QWORD *)&KiBugCheckDriver = v103 + 88;
      }
      goto LABEL_116;
    case 0x3Bu:
      v12 = a5;
      v101 = a5;
      goto LABEL_84;
    case 0x4Cu:
      v45 = 0;
      KiBugCheckData[0] = (unsigned int)v8;
      v87 = 1;
      v97 = 1;
      do
      {
        KiBugCheckData[v45 + 1] = *(_QWORD *)(v6 + 8 * v45);
        ++v45;
      }
      while ( v45 != 4 );
      v41 = v96;
      goto LABEL_87;
    case 0x50u:
      v41 = v96;
      if ( !v96 )
      {
        v43 = 0;
        if ( !v9 || ((unsigned __int8)v9 & 3) != 0 )
        {
LABEL_99:
          if ( !v43 )
          {
            v44 = MmLocateUnloadedDriver(v8);
            v9 = Format;
            v7 = Format;
            if ( v44 )
            {
              KiBugCheckDriverOffset = v8 - *(_DWORD *)(v44 + 16);
              *(_QWORD *)&KiBugCheckDriver = v44;
              KiBugCheckData[0] = 206;
            }
            goto LABEL_87;
          }
          goto LABEL_85;
        }
        v41 = (__int64)v9;
        v96 = (__int64)v9;
      }
      v101 = *(_QWORD *)(v41 + 360);
      v12 = v101;
      qword_140F21918 = v101;
      v43 = KiPcToFileHeader(v101, &v103, 0, &v91);
      goto LABEL_99;
    case 0x7Bu:
      v90 = ((unsigned __int8)v9 & 1) == 0;
      v94 = ((unsigned __int8)v9 & 2) == 0;
      goto LABEL_84;
  }
  if ( v99 != 142 )
  {
    if ( v99 != 160 )
    {
      if ( v99 != 190 )
      {
        if ( v99 == 203 )
        {
          v12 = v8;
          v101 = v8;
LABEL_84:
          v41 = v96;
LABEL_85:
          v9 = Format;
LABEL_86:
          v7 = v9;
LABEL_87:
          v42 = v87;
          goto LABEL_88;
        }
LABEL_126:
        v41 = v96;
        if ( v96 )
        {
          v12 = *(_QWORD *)(v96 + 360);
          v101 = v12;
        }
        goto LABEL_85;
      }
      goto LABEL_141;
    }
    v9 = Format;
    v41 = v96;
    if ( (KeGetCurrentThread()->ApcState.Process[3].ActiveGroupsMask.Masks[1] & 0x100000000000LL) == 0 )
    {
      v7 = Format;
      if ( (unsigned __int64)(v8 - 240) <= 1 )
        v87 = 1;
      goto LABEL_87;
    }
    v42 = 0;
LABEL_116:
    v7 = v9;
    goto LABEL_88;
  }
LABEL_141:
  v41 = v96;
  if ( !v96 )
  {
    if ( !v9 || ((unsigned __int8)v9 & 3) != 0 )
      goto LABEL_85;
    v41 = (__int64)v9;
    v96 = (__int64)v9;
  }
  v9 = Format;
  v42 = 0;
  v7 = Format;
  if ( v99 != 142 )
  {
    v12 = *(_QWORD *)(v41 + 360);
    v101 = v12;
  }
LABEL_88:
  if ( *(_QWORD *)&KiBugCheckDriver )
  {
    KiBugCheckUnicodeToAnsi(*(_QWORD *)&KiBugCheckDriver, pszDest, _R8, v36);
  }
  else if ( v12 )
  {
    KiDumpParameterImages(pszDest);
  }
  if ( !WheapDispatchPtr.DeviceLock.Header.LockNV )
  {
    WheapSelLogSetNtSchedulerAvailabilityNoLock();
    if ( (int)EnterWheaIpmiContextNoLock() >= 0 )
      IpmiLibAddSelBugcheckRecord();
  }
  v51 = KiBugCheckData[0];
  v52 = v94;
  BugCheckProgressEfiSafeToCall = LODWORD(KiBugCheckData[0]) != 265;
  if ( v94 )
  {
    LOBYTE(v40) = v11;
    KiCollectTriageDumpDataBlocks(KiBugCheckData[0], v40);
  }
  if ( v95 && (PartialDumpControl & 4) != 0 )
  {
    qword_140F21978 = v41;
    KiCrashDumpContext = (__int64)v111;
    qword_140F21968 = (__int64)CurrentThread;
    qword_140F21970 = (__int64)v105;
    byte_140F21980 = v42;
    byte_140F21981 = v11;
    KiAttemptBugcheckRecovery();
  }
  v53 = 1;
  KiBugcheckOwnerKeepsOthersFrozen = 1;
  guard_dispatch_icall_no_overrides(v51, v40, _R8);
  HvlEnlightenments &= 0x2000u;
  IoSaveBugCheckProgress(96);
  v54 = 0;
  for ( i = 0; i < KiNmiInProgress[0]; ++i )
  {
    if ( qword_140E0E288[i] )
    {
      v54 = 1;
      break;
    }
  }
  guard_dispatch_icall_no_overrides((unsigned int)v54, v54, 0x140000000uLL);
  KiFilterBugCheckInfo(&v99, KiBugCheckData);
  if ( CrashdmpDumpBlock && v52 )
    v53 = 0;
  HvlLogGuestCrashInformation(
    KiBugCheckData[0],
    qword_140F21908,
    qword_140F21910,
    qword_140F21918,
    qword_140F21920,
    v53);
  if ( !KdPitchDebugger )
    qword_140E010A8 = (__int64)v111;
  if ( (unsigned __int8)KiBugCheckShouldEnterPostBugCheckDebugger(v99, 0) )
  {
    if ( !CurrentPrcb->NmiActive )
    {
      DbgPrintEx(
        0x65u,
        0,
        "\n*** Fatal System Error: 0x%08lx\n                       (0x%p,0x%p,0x%p,0x%p)\n\n",
        LODWORD(KiBugCheckData[0]),
        (const void *)qword_140F21908,
        (const void *)qword_140F21910,
        (const void *)qword_140F21918,
        (const void *)qword_140F21920);
      if ( *(_QWORD *)&KiBugCheckDriver )
        DbgPrintEx(0x65u, 0, "Driver at fault: %s.\n", pszDest);
      if ( v97 )
      {
        if ( v9 )
          DbgPrintEx(0x65u, 0, v9);
        if ( v7 )
          DbgPrintEx(0x65u, 0, v7);
      }
    }
    if ( (_BYTE)KdDebuggerEnabled && !(_BYTE)KdDebuggerNotPresent )
      KiBugCheckDebugBreak(3u);
  }
LABEL_186:
  _disable();
  v56 = KeGetCurrentIrql();
  if ( (_BYTE)v56 != 15 )
    __writecr8(0xFu);
  if ( KiIrqlFlags )
    KiRaiseIrqlProcessIrqlFlags(v56, 15);
  if ( v88 )
    goto LABEL_217;
  if ( (unsigned __int8)KiHandleMultipleBugchecksDuringRecovery((unsigned int)KiBugCheckActive) )
  {
    KiBugcheckOwnerKeepsOthersFrozen = 1;
LABEL_217:
    if ( (unsigned int)KeNumberProcessors_0 > 1 && !KiHypervisorInitiatedCrashDump )
    {
      KiSetDebuggerOwner(CurrentPrcb);
      *(_QWORD *)&v110.Count = 4194305;
      memset_0(&v110.8, 0, sizeof(v110.8));
      RtlpCopyAffinityEx(&v110, v110.Size, &KeActiveProcessors);
      KeRemoveProcessorAffinityEx(&v110, CurrentPrcb->Number);
      KiSendFreeze(&v110, 0);
      KeStallExecutionProcessor(0xF4240u);
    }
    IoSaveInitialBugCheckProgress(LODWORD(KiBugCheckData[0]), qword_140F21908);
    IoSaveBugCheckProgress(1);
    LOBYTE(v76) = v53;
    KiBugCheckProgressCpusFrozen(v76);
    if ( CurrentPrcb->PowerState.ResolvedQosClass )
    {
      if ( PpmPerfVmQosSupported )
      {
        PpmHvSetVirtualProcessorQos(CurrentPrcb, 0);
      }
      else if ( PpmPerfSchedulerDirectedPerfStatesSupported )
      {
        Domain = CurrentPrcb->PowerState.CheckContext.Domain;
        if ( Domain )
        {
          LOBYTE(v78) = 1;
          guard_dispatch_icall_no_overrides(
            CurrentPrcb->PowerState.CheckContext.Constraint->PerfContext,
            Domain->QosSelection,
            v78);
        }
      }
    }
    if ( v11 )
    {
      v65 = v90;
    }
    else
    {
      v80 = v102;
      if ( v53 )
        v80 = v102 | 4;
      v65 = v90;
      v81 = v80 | 2;
      if ( v95 )
        v81 = v80;
      v82 = v81 | 1;
      if ( v90 )
        v82 = v81;
      KiDisplayBlueScreen(v82);
    }
    LOBYTE(v77) = 1;
    HvlPrepareForRootCrashdump(v77);
    if ( v11 )
    {
      v83 = 9;
    }
    else
    {
      IoSaveBugCheckProgress(2);
      KiInvokeBugCheckEntryCallbacks(1, 0, 0);
      v83 = 9;
      KiInvokeBugCheckEntryCallbacks(9, 0, 0);
      IoSaveBugCheckProgress(5);
      KiInvokeBugCheckAddTriageDumpDataCallbacks();
    }
    if ( !(_BYTE)KdDebuggerEnabled && !KdPitchDebugger )
      KdEnableDebuggerWithLock(0);
    v84 = CurrentPrcb->Context;
    v85 = v111;
    do
    {
      *(_OWORD *)&v84->P1Home = *(_OWORD *)v85;
      *(_OWORD *)&v84->P3Home = *((_OWORD *)v85 + 1);
      *(_OWORD *)&v84->P5Home = *((_OWORD *)v85 + 2);
      *(_OWORD *)&v84->ContextFlags = *((_OWORD *)v85 + 3);
      *(_OWORD *)&v84->SegGs = *((_OWORD *)v85 + 4);
      *(_OWORD *)&v84->Dr1 = *((_OWORD *)v85 + 5);
      *(_OWORD *)&v84->Dr3 = *((_OWORD *)v85 + 6);
      v86 = *((_OWORD *)v85 + 7);
      v85 += 128;
      *(_OWORD *)&v84->Dr7 = v86;
      v84 = (_CONTEXT *)((char *)v84 + 128);
      --v83;
    }
    while ( v83 );
    *(_OWORD *)&v84->P1Home = *(_OWORD *)v85;
    *(_OWORD *)&v84->P3Home = *((_OWORD *)v85 + 1);
    *(_OWORD *)&v84->P5Home = *((_OWORD *)v85 + 2);
    *(_OWORD *)&v84->ContextFlags = *((_OWORD *)v85 + 3);
    *(_OWORD *)&v84->SegGs = *((_OWORD *)v85 + 4);
    if ( v52 )
    {
      KdDecodeDataBlock(v85, 128);
      qword_140F21968 = (__int64)CurrentThread;
      qword_140F21970 = (__int64)v105;
      qword_140F21978 = v96;
      byte_140F21980 = v87;
      KiCrashDumpContext = (__int64)v111;
      byte_140F21981 = v11;
      KiBugCheckWriteCrashDump(&KiCrashDumpContext);
    }
    goto LABEL_203;
  }
  v57 = KiBugCheckActive;
  if ( Number != (unsigned int)KiBugCheckActive >> 4 )
  {
    KiYieldWaitForDebugger();
    __debugbreak();
  }
  if ( KiHypervisorInitiatedCrashDump || (KiBugCheckActive & 0xCu) >= 8 )
  {
    IoEscalateBugCheck(16);
    while ( 1 )
      guard_dispatch_icall_no_overrides(v74, v73, v75);
  }
  IoSetBugCheckProgressFlag(0x20000);
  _InterlockedAdd(&KiBugCheckActive, 4u);
  if ( (v57 & 0xC) != 0 )
  {
    IoEscalateBugCheck(8);
    KiBugCheckDebugBreak(4u);
  }
  else
  {
    KiCrashDumpContext = (__int64)v111;
    qword_140F21968 = (__int64)CurrentThread;
    qword_140F21970 = (__int64)v105;
    qword_140F21978 = v96;
    byte_140F21980 = v87;
    byte_140F21981 = v89;
    IoEscalateBugCheck(4);
    v58 = byte_140F21980;
    v59 = qword_140F21970;
    v60 = qword_140F21968;
    v61 = KiCrashDumpContext;
    v62 = qword_140F21920;
    v63 = qword_140F21918;
    v64 = qword_140F21910;
    v106 = qword_140F21908;
    Number = KiBugCheckData[0];
    if ( qword_140E4C0E0 )
      guard_dispatch_icall_no_overrides(10, 0, 0);
    if ( !(unsigned __int8)IoWriteCrashDump(Number, v106, v64, v63, v62, v61, v60, v59, v58) )
      IoSetBugCheckProgressFlag(0x2000000);
  }
  v11 = v89;
  v65 = v90;
LABEL_203:
  HvlResumeFromRootCrashdump(0);
  IoSaveBugCheckProgress(99);
  if ( !v11 )
    KiScanBugCheckCallbackList(v67, v66, v68, v69);
  guard_dispatch_icall_no_overrides(v67, v66, v68);
  IoSaveBugCheckProgress(4);
  IoEscalateBugCheck(32);
  if ( v95 )
  {
    KiResumeForReboot = 1;
    KiSendThawExecution(0);
    KiBugcheckUnloadDebugSymbols();
    guard_dispatch_icall_no_overrides(0, v70, v71);
    if ( PoPowerDownActionInProgress && !PoPowerResetActionInProgress
      || PoModernStandbyActionInProgress
      || v98
      || (v72 = 3, !v65) )
    {
      v72 = 1;
    }
    HalReturnToFirmware(v72);
  }
  KiBugCheckDebugBreak(4u);
}

```

## disassembly

```asm
0x14051baf0  push    rbp
0x14051baf2  push    rbx
0x14051baf3  push    rsi
0x14051baf4  push    rdi
0x14051baf5  push    r12
0x14051baf7  push    r13
0x14051baf9  push    r14
0x14051bafb  push    r15
0x14051bafd  lea     rbp, [rsp-748h]
0x14051bb05  sub     rsp, 848h
0x14051bb0c  mov     rax, [rbp+780h+arg_28]
0x14051bb13  mov     r14, r8
0x14051bb16  mov     r12, [rbp+780h+arg_20]
0x14051bb1d  mov     r13, rdx
0x14051bb20  mov     [rbp+780h+var_7C8], r8
0x14051bb24  mov     rdi, r9
0x14051bb27  mov     [rbp+780h+var_7C0], rdx
0x14051bb2b  mov     r8d, 208h; Size
0x14051bb31  mov     [rbp+780h+var_800], ecx
0x14051bb34  xor     edx, edx; Val
0x14051bb36  lea     rcx, [rbp+780h+var_7A0]; void *
0x14051bb3a  mov     [rsp+880h+var_810], rax
0x14051bb3f  mov     [rbp+780h+var_7B0], r9
0x14051bb43  call    memset_0
0x14051bb48  xor     ebx, ebx
0x14051bb4a  mov     [rbp+780h+pszDest], bl
0x14051bb50  mov     esi, ebx
0x14051bb52  mov     rax, gs:188h
0x14051bb5b  cmp     cs:IopAutoReboot, ebx
0x14051bb61  mov     [rbp+780h+var_7D8], rax
0x14051bb65  lea     r15d, [rbx+1]
0x14051bb69  lea     rax, KiBugCheckProgress
0x14051bb70  mov     [rbp+780h+var_7E0], rbx
0x14051bb74  mov     [rbp+780h+var_7D0], rax
0x14051bb78  setnz   [rsp+880h+var_817]
0x14051bb7d  mov     eax, r15d
0x14051bb80  mov     [rsp+880h+var_829], bl
0x14051bb84  xchg    eax, cs:KiBugCheckDataInitialized
0x14051bb8a  mov     byte ptr [rsp+880h+var_830], bl
0x14051bb8e  mov     [rsp+880h+var_806], bl
0x14051bb92  mov     [rbp+780h+var_7B8], rbx
0x14051bb96  mov     [rbp+780h+var_7F0], rbx
0x14051bb9a  mov     [rsp+880h+var_82A], r15b
0x14051bb9f  mov     [rsp+880h+var_818], r15b
0x14051bba4  mov     [rbp+780h+var_7E8], ebx
0x14051bba7  test    eax, eax
0x14051bba9  jnz     loc_14051BC3F
0x14051bbaf  mov     eax, [rbp+780h+var_800]
0x14051bbb2  cmp     eax, 0C00002D1h
0x14051bbb7  jnz     short loc_14051BBC1
0x14051bbb9  mov     eax, 0C3h
0x14051bbbe  mov     [rbp+780h+var_800], eax
0x14051bbc1  cmp     dword ptr cs:WheapDispatchPtr.DeviceLock.Header, ebx
0x14051bbc7  mov     cs:KiBugCheckData, rax
0x14051bbce  mov     cs:qword_140F21908, r13
0x14051bbd5  mov     cs:qword_140F21910, r14
0x14051bbdc  mov     cs:qword_140F21918, rdi
0x14051bbe3  mov     cs:qword_140F21920, r12
0x14051bbea  jnz     short loc_14051BBF5
0x14051bbec  mov     eax, r15d
0x14051bbef  xchg    eax, cs:WheaIpmiHwLogLocked
0x14051bbf5  xor     edx, edx
0x14051bbf7  xor     r8d, r8d
0x14051bbfa  lea     ecx, [rdx+8]
0x14051bbfd  call    KiInvokeBugCheckEntryCallbacks
0x14051bc02  mov     edx, cs:dword_140E0E1D4
0x14051bc08  test    edx, edx
0x14051bc0a  jns     short loc_14051BC1B
0x14051bc0c  xor     r8d, r8d
0x14051bc0f  mov     ecx, 8000006Eh
0x14051bc14  call    KiBugCheckSelLogError
0x14051bc19  jmp     short loc_14051BC32
0x14051bc1b  mov     r8d, 10h
0x14051bc21  lea     rdx, Uuid
0x14051bc28  mov     ecx, 8000006Dh
0x14051bc2d  call    KiBugCheckSelLogDataCheckPoint
0x14051bc32  xor     edx, edx
0x14051bc34  xor     r8d, r8d
0x14051bc37  lea     ecx, [rdx+4]
0x14051bc3a  call    IoNotifyDumpEx
0x14051bc3f  mov     eax, cs:HvlpFlags
0x14051bc45  mov     edx, 2
0x14051bc4a  test    dl, al
0x14051bc4c  jz      short loc_14051BC5B
0x14051bc4e  lea     ecx, [rdx+2]
0x14051bc51  call    HvlNotifyRootCrashdump
0x14051bc56  mov     edx, 2
0x14051bc5b  mov     [rsp+880h+var_820], rbx
0x14051bc60  mov     [rsp+880h+Format], rbx
0x14051bc65  mov     [rbp+780h+var_7F8], ebx
0x14051bc68  mov     rax, cr8
0x14051bc6c  cmp     al, dl
0x14051bc6e  jnb     short loc_14051BC89
0x14051bc70  mov     rcx, cr8
0x14051bc74  cmp     cl, dl
0x14051bc76  jz      short loc_14051BC7C
0x14051bc78  mov     cr8, rdx
0x14051bc7c  cmp     cs:KiIrqlFlags, ebx
0x14051bc82  jz      short loc_14051BC89
0x14051bc84  call    KiRaiseIrqlProcessIrqlFlags
0x14051bc89  mov     rax, gs:188h
0x14051bc92  cmp     [rax+28h], rbx
0x14051bc96  jnz     short loc_14051BCE3
0x14051bc98  mov     rdx, gs:20h
0x14051bca1  mov     eax, cs:KiBugCheckActive
0x14051bca7  mov     edx, [rdx+24h]
0x14051bcaa  shl     edx, 4
0x14051bcad  or      edx, 3
0x14051bcb0  mov     ecx, eax
0x14051bcb2  and     ecx, 3
0x14051bcb5  cmp     cl, 3
0x14051bcb8  jz      short loc_14051BCCD
0x14051bcba  mov     ecx, eax
0x14051bcbc  lock cmpxchg cs:KiBugCheckActive, edx
0x14051bcc4  cmp     eax, ecx
0x14051bcc6  jnz     short loc_14051BCB0
0x14051bcc8  mov     r8b, r15b
0x14051bccb  jmp     short loc_14051BCD0
0x14051bccd  mov     r8b, bl
0x14051bcd0  mov     [rsp+880h+var_82C], r8b
0x14051bcd5  test    r8b, r8b
0x14051bcd8  jz      loc_14051BE75
0x14051bcde  jmp     loc_14051BE59
0x14051bce3  lea     r8, [rsp+880h+var_820]
0x14051bce8  lea     rdx, [rsp+880h+Format]
0x14051bced  lea     rcx, [rbp+780h+var_7F8]
0x14051bcf1  call    KeQueryCurrentStackInformation
0x14051bcf6  mov     rdx, gs:20h
0x14051bcff  mov     bl, al
0x14051bd01  mov     eax, cs:KiBugCheckActive
0x14051bd07  mov     edx, [rdx+24h]
0x14051bd0a  shl     edx, 4
0x14051bd0d  or      edx, 3
0x14051bd10  mov     ecx, eax
0x14051bd12  and     ecx, 3
0x14051bd15  cmp     cl, 3
0x14051bd18  jz      loc_14051BE6C
0x14051bd1e  mov     ecx, eax
0x14051bd20  lock cmpxchg cs:KiBugCheckActive, edx
0x14051bd28  cmp     eax, ecx
0x14051bd2a  jnz     short loc_14051BD10
0x14051bd2c  xor     edx, edx
0x14051bd2e  xor     r8d, r8d
0x14051bd31  lea     ecx, [rdx+6]
0x14051bd34  call    IoNotifyDumpEx
0x14051bd39  test    bl, bl
0x14051bd3b  jz      loc_14051BDE1
0x14051bd41  mov     eax, [rbp+780h+var_7F8]
0x14051bd44  cmp     eax, 9
0x14051bd47  ja      short loc_14051BD57
0x14051bd49  mov     ecx, 3A1h
0x14051bd4e  bt      ecx, eax
0x14051bd51  jb      loc_14051BDE1
0x14051bd57  mov     rax, [rsp+880h+var_820]
0x14051bd5c  mov     r14b, r15b
0x14051bd5f  mov     r15, [rsp+880h+Format]
0x14051bd64  mov     edi, 24000h
0x14051bd69  sub     rax, r15
0x14051bd6c  xor     ebx, ebx
0x14051bd6e  cmp     rax, rdi
0x14051bd71  ja      short loc_14051BD7B
0x14051bd73  mov     rdi, rax
0x14051bd76  test    rax, rax
0x14051bd79  jz      short loc_14051BDC5
0x14051bd7b  lea     r13, cs:140000000h
0x14051bd82  lea     rsi, [rbx+r15]
0x14051bd86  xor     edx, edx
0x14051bd88  mov     rcx, rsi
0x14051bd8b  call    MmIsAddressValidEx
0x14051bd90  test    al, al
0x14051bd92  jz      short loc_14051BDAE
0x14051bd94  lea     rcx, rva KiPreBugcheckStackSaveArea[r13]
0x14051bd9b  mov     r8d, 1000h; Size
0x14051bda1  add     rcx, rbx; void *
0x14051bda4  mov     rdx, rsi; Src
0x14051bda7  call    memmove
0x14051bdac  jmp     short loc_14051BDB1
0x14051bdae  xor     r14b, r14b
0x14051bdb1  add     rbx, 1000h
0x14051bdb8  cmp     rbx, rdi
0x14051bdbb  jb      short loc_14051BD82
0x14051bdbd  mov     r13, [rbp+780h+var_7C0]
0x14051bdc1  mov     rsi, [rbp+780h+var_7B8]
0x14051bdc5  xor     edx, edx
0x14051bdc7  movzx   r8d, r14b
0x14051bdcb  lea     ecx, [rdx+7]
0x14051bdce  call    IoNotifyDumpEx
0x14051bdd3  mov     rdi, [rbp+780h+var_7B0]
0x14051bdd7  mov     r15d, 1
0x14051bddd  mov     r14, [rbp+780h+var_7C8]
0x14051bde1  xor     ebx, ebx
0x14051bde3  cmp     cs:KiKernelCetEnabled, bl
0x14051bde9  jz      short loc_14051BE51
0x14051bdeb  mov     rcx, gs:188h
0x14051bdf4  xor     r8d, r8d
0x14051bdf7  rdsspq  r8
0x14051bdfc  mov     r9, [rcx+420h]
0x14051be03  and     r9, 0FFFFFFFFFFFFF000h
0x14051be0a  add     r9, 1000h
0x14051be11  cmp     r8, r9
0x14051be14  jbe     short loc_14051BE51
0x14051be16  mov     rax, [rcx+418h]
0x14051be1d  sub     rax, 1000h
0x14051be23  cmp     r8, rax
0x14051be26  jnb     short loc_14051BE51
0x14051be28  lea     rdx, [r8-100h]
0x14051be2f  mov     eax, 100h
0x14051be34  cmp     rdx, r9
0x14051be37  lea     rcx, qword_140FC0350; void *
0x14051be3e  cmovb   rdx, r9; Src
0x14051be42  sub     r8, rdx
0x14051be45  cmp     r8, rax
0x14051be48  cmova   r8, rax; Size
0x14051be4c  call    memmove
0x14051be51  mov     r8b, r15b
0x14051be54  mov     [rsp+880h+var_82C], r15b
0x14051be59  mov     eax, cs:KiRecoveryCallbackCount
0x14051be5f  test    eax, eax
0x14051be61  jg      short loc_14051BE75
0x14051be63  mov     cs:KiBugcheckOwnerKeepsOthersFrozen, r15b
0x14051be6a  jmp     short loc_14051BE75
0x14051be6c  xor     ebx, ebx
0x14051be6e  mov     r8b, bl
0x14051be71  mov     [rsp+880h+var_82C], bl
0x14051be75  cmp     cs:KeSmapEnabled, ebx
0x14051be7b  jz      short loc_14051BE80
0x14051be7d  stac
0x14051be80  mov     r15, gs:20h
0x14051be89  cmp     cs:KiHypervisorInitiatedCrashDump, bl
0x14051be8f  mov     eax, [r15+24h]
0x14051be93  mov     [rbp+780h+var_7F8], eax
0x14051be96  jz      short loc_14051BEA2
0x14051be98  mov     eax, cs:HvlpFlags
0x14051be9e  test    al, 2
0x14051bea0  jnz     short loc_14051BEBF
0x14051bea2  mov     rdx, cs:KeEnabledSupervisorXStateFeatures
0x14051bea9  mov     rcx, [r15+700h]
0x14051beb0  bts     rdx, 8
0x14051beb5  call    KeSaveSupervisorState
0x14051beba  mov     r8b, [rsp+880h+var_82C]
0x14051bebf  mov     rax, cs:qword_140EF9DD0
0x14051bec6  test    rax, rax
0x14051bec9  jz      short loc_14051BF1F
0x14051becb  cmp     cs:PopSimulateHiberBugcheck, ebx
0x14051bed1  jz      short loc_14051BED9
0x14051bed3  mov     cs:PoPowerDownActionInProgress, bl
0x14051bed9  cmp     [rax+2], bl
0x14051bedc  jz      short loc_14051BF1F
0x14051bede  test    r8b, r8b
0x14051bee1  jz      short loc_14051BF14
0x14051bee3  mov     ebx, [rbp+780h+var_800]
0x14051bee6  lea     r8, aABugcheckOccur; "\nA bugcheck occurred during the late s"...
0x14051beed  xor     edx, edx; Level
0x14051beef  lea     ecx, [rdx+65h]; ComponentId
0x14051bef2  call    DbgPrintEx
0x14051bef7  cmp     ebx, 0Ah
0x14051befa  jnz     short loc_14051BF0D
0x14051befc  lea     r8, aMemoryWasAcces; "Memory was accessed during this time th"...
0x14051bf03  xor     edx, edx; Level
0x14051bf05  lea     ecx, [rbx+5Bh]; ComponentId
0x14051bf08  call    DbgPrintEx
0x14051bf0d  mov     r8b, [rsp+880h+var_82C]
0x14051bf12  xor     ebx, ebx
0x14051bf14  mov     [rbp+780h+var_7D0], rbx
0x14051bf18  mov     bl, 1
0x14051bf1a  mov     [rsp+880h+var_82C], r8b
0x14051bf1f  mov     rax, [r15+6400h]
0x14051bf26  lea     rcx, [rbp+780h+var_590]
0x14051bf2d  mov     edx, 9
0x14051bf32  mov     [rsp+880h+var_82B], bl
0x14051bf36  lea     r9d, [rdx+77h]
0x14051bf3a  movups  xmm0, xmmword ptr [rax]
0x14051bf3d  movups  xmmword ptr [rcx], xmm0
0x14051bf40  movups  xmm1, xmmword ptr [rax+10h]
0x14051bf44  movups  xmmword ptr [rcx+10h], xmm1
0x14051bf48  movups  xmm0, xmmword ptr [rax+20h]
0x14051bf4c  movups  xmmword ptr [rcx+20h], xmm0
0x14051bf50  movups  xmm1, xmmword ptr [rax+30h]
0x14051bf54  movups  xmmword ptr [rcx+30h], xmm1
0x14051bf58  movups  xmm0, xmmword ptr [rax+40h]
0x14051bf5c  movups  xmmword ptr [rcx+40h], xmm0
0x14051bf60  movups  xmm1, xmmword ptr [rax+50h]
0x14051bf64  movups  xmmword ptr [rcx+50h], xmm1
0x14051bf68  movups  xmm0, xmmword ptr [rax+60h]
0x14051bf6c  movups  xmmword ptr [rcx+60h], xmm0
0x14051bf70  movups  xmm1, xmmword ptr [rax+70h]
0x14051bf74  add     rax, r9
0x14051bf77  movups  xmmword ptr [rcx+70h], xmm1
0x14051bf7b  add     rcx, r9
0x14051bf7e  sub     rdx, 1
0x14051bf82  jnz     short loc_14051BF3A
0x14051bf84  movups  xmm0, xmmword ptr [rax]
0x14051bf87  movups  xmmword ptr [rcx], xmm0
0x14051bf8a  movups  xmm1, xmmword ptr [rax+10h]
0x14051bf8e  movups  xmmword ptr [rcx+10h], xmm1
0x14051bf92  movups  xmm0, xmmword ptr [rax+20h]
0x14051bf96  movups  xmmword ptr [rcx+20h], xmm0
0x14051bf9a  movups  xmm1, xmmword ptr [rax+30h]
0x14051bf9e  movups  xmmword ptr [rcx+30h], xmm1
0x14051bfa2  movups  xmm0, xmmword ptr [rax+40h]
  ... truncated ...
```
