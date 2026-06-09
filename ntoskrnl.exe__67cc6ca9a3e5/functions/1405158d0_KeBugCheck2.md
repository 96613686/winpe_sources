# KeBugCheck2

- ea: `0x1405158d0`
- end: `0x1405169a6`
- name: `KeBugCheck2`
- size: `4310`
- prototype: ``
- caller_count: `1`
- callee_count: `54`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14053a530`

## callees

- `0x14020fe90`
- `0x140272e40`
- `0x140293840`
- `0x1402938b0`
- `0x1402d1690`
- `0x140394ce0`
- `0x1403fd570`
- `0x1404ced30`
- `0x1405149ac`
- `0x1405158d0`
- `0x1405169ac`
- `0x140529924`
- `0x14052be84`
- `0x14052bebc`
- `0x14052f850`
- `0x140531958`
- `0x140532220`
- `0x140536714`
- `0x140546e5c`
- `0x1405859e0`
- `0x1405bcc64`
- `0x1405c2174`
- `0x1405c21fc`
- `0x1405c2630`
- `0x1405cacdc`
- `0x1405cb890`
- `0x1405cbb20`
- `0x1405e2d8c`
- `0x1405e321c`
- `0x1405e5330`
- `0x1405e5560`
- `0x1405e562c`
- `0x1405e569c`
- `0x1405e56e0`
- `0x1405e574c`
- `0x1405e5a98`
- `0x1405e5e24`
- `0x1405e61b4`
- `0x1405e6450`
- `0x1405e6550`
- `0x1405e6730`
- `0x1405e6a6c`
- `0x1405f233c`
- `0x1405f3440`
- `0x1405f3530`
- `0x1405f5fd8`
- `0x1405f69ac`
- `0x140688ac8`
- `0x14069c56c`
- `0x1406d47e4`

## string_xrefs

- `0x140515cc6`: `\nA bugcheck occurred during the late stages of hibernate suspend or resume.\nDue to verification temporarily enabled by Po during this time,\nregular bugcheck processing may not work.\n\n`
- `0x140515cdc`: `Memory was accessed during this time that was not properly marked\nfor the boot phase of hibernate! Check the callstack and parameters\nto find the pages that need to be marked.\n\n`

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
  __int64 *v38; // rdx
  __int64 v39; // r14
  char v40; // r13
  __int64 v41; // rax
  __int64 v42; // rax
  __int64 v43; // rcx
  __int64 v44; // rax
  __int64 v45; // rax
  __int64 UnloadedDriver; // rax
  struct _KTHREAD *v47; // rcx
  _KPROCESS *Process; // rcx
  __int64 v49; // rcx
  bool v50; // si
  unsigned __int8 v51; // r14
  unsigned int v52; // edx
  wchar_t i; // cx
  __int64 v54; // rcx
  char v55; // bl
  char v56; // bl
  __int64 v57; // rdi
  __int64 v58; // rsi
  __int64 v59; // r14
  __int64 v60; // r15
  int v61; // r12d
  int v62; // r13d
  bool v63; // r14
  __int64 v64; // rdx
  __int64 v65; // rcx
  __int64 v66; // r8
  __int64 v67; // r9
  __int64 v68; // rcx
  __int64 v69; // rcx
  __int64 v70; // rcx
  __int64 v71; // rcx
  int v72; // ecx
  unsigned int v73; // eax
  __int64 v74; // rcx
  __int64 v75; // rdi
  _CONTEXT *v76; // rax
  char *v77; // rcx
  __int128 v78; // xmm1
  bool v79; // [rsp+50h] [rbp-B0h]
  char v80; // [rsp+54h] [rbp-ACh]
  char v81; // [rsp+55h] [rbp-ABh]
  bool v82; // [rsp+56h] [rbp-AAh]
  char v83; // [rsp+57h] [rbp-A9h] BYREF
  PCSTR Format; // [rsp+58h] [rbp-A8h] BYREF
  PCSTR v85; // [rsp+60h] [rbp-A0h] BYREF
  bool v86; // [rsp+68h] [rbp-98h]
  bool v87; // [rsp+69h] [rbp-97h]
  __int64 v88; // [rsp+70h] [rbp-90h]
  char v89; // [rsp+78h] [rbp-88h]
  char v90; // [rsp+7Ah] [rbp-86h]
  unsigned int v91; // [rsp+80h] [rbp-80h] BYREF
  unsigned int Number; // [rsp+88h] [rbp-78h] BYREF
  __int64 v93; // [rsp+90h] [rbp-70h]
  int v94; // [rsp+98h] [rbp-68h]
  __int64 v95; // [rsp+A0h] [rbp-60h] BYREF
  struct _KTHREAD *CurrentThread; // [rsp+A8h] [rbp-58h]
  __int64 (__fastcall *v97)(); // [rsp+B0h] [rbp-50h]
  __int64 v98; // [rsp+B8h] [rbp-48h]
  __int64 v99; // [rsp+C0h] [rbp-40h]
  __int64 v100; // [rsp+C8h] [rbp-38h]
  const CHAR *v101; // [rsp+D0h] [rbp-30h]
  struct _KAFFINITY_EX v102; // [rsp+E0h] [rbp-20h] BYREF
  char v103[1232]; // [rsp+2F0h] [rbp+1F0h] BYREF
  char pszDest[192]; // [rsp+7C0h] [rbp+6C0h] BYREF

  v6 = a3;
  v7 = (const CHAR *)a5;
  v8 = a2;
  v98 = a3;
  v9 = a4;
  v99 = a2;
  v91 = a1;
  v88 = a6;
  v101 = a4;
  memset_0(&v102, 0, sizeof(v102));
  v11 = 0;
  pszDest[0] = 0;
  v12 = 0;
  CurrentThread = KeGetCurrentThread();
  v95 = 0;
  v97 = KiBugCheckProgress;
  v87 = IopAutoReboot != 0;
  v83 = 0;
  v79 = 0;
  v90 = 0;
  v100 = 0;
  v93 = 0;
  v82 = 1;
  v86 = 1;
  v94 = 0;
  if ( !_InterlockedExchange(&KiBugCheckDataInitialized, 1) )
  {
    v13 = v91;
    if ( v91 == -1073741103 )
    {
      v13 = 195;
      v91 = 195;
    }
    KiBugCheckData[0] = v13;
    qword_140F45C48 = v8;
    qword_140F45C50 = v6;
    qword_140F45C58 = (__int64)v9;
    qword_140F45C60 = a5;
    if ( !(_DWORD)WheapHighIrqlLogSelHandler )
      _InterlockedExchange((volatile __int32 *)&WheapConfigTableLock.ApcStateFill[36], 1);
    KiInvokeBugCheckEntryCallbacks(8, 0, 0);
    if ( dword_140E0E1D4 >= 0 )
      KiBugCheckSelLogDataCheckPoint(2147483757LL, &Uuid, 16);
    else
      KiBugCheckSelLogError(2147483758LL, (unsigned int)dword_140E0E1D4, 0);
    IoNotifyDumpEx(4, 0, 0);
  }
  if ( (HvlpFlags & 2) != 0 )
    HvlNotifyRootCrashdump(4);
  v85 = 0;
  Format = 0;
  Number = 0;
  if ( KeGetCurrentIrql() < 2u )
  {
    CurrentIrql = KeGetCurrentIrql();
    if ( (_BYTE)CurrentIrql != 2 )
      __writecr8(2u);
    if ( KiIrqlFlags )
      KiRaiseIrqlProcessIrqlFlags(CurrentIrql);
  }
  if ( KeGetCurrentThread()->InitialStack )
  {
    v18 = KeQueryCurrentStackInformation(&Number, &Format, &v85);
    v19 = KiBugCheckActive;
    v20 = (16 * KeGetCurrentPrcb()->Number) | 3;
    do
    {
      if ( (v19 & 3) == 3 )
      {
        v11 = 0;
        LOBYTE(_R8) = 0;
        v80 = 0;
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
        if ( (unsigned __int64)(v85 - Format) > 0x24000 || (v25 = v85 - Format, v85 != Format) )
        {
          do
          {
            if ( (unsigned __int8)MmIsAddressValidEx(&v24[v26], 0) )
              memmove((char *)&KiSystemAvailableCpusSubscriptionLock.Timer + v26, &v24[v26], 0x1000u);
            else
              v23 = 0;
            v26 += 4096LL;
          }
          while ( v26 < v25 );
          v8 = v99;
          v12 = v100;
        }
        IoNotifyDumpEx(7, 0, v23);
        v9 = v101;
        v6 = v98;
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
    v80 = 1;
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
  v80 = _R8;
  if ( (_BYTE)_R8 )
  {
LABEL_48:
    if ( *(int *)&KsepShimDbLock.SchedulerApcFill5[80] <= 0 )
      LOBYTE(KiSystemAvailableCpusSubscriptionLock.Queue) = 1;
  }
LABEL_51:
  if ( KeSmapEnabled )
    __asm { stac }
  CurrentPrcb = KeGetCurrentPrcb();
  Number = CurrentPrcb->Number;
  if ( !KiHypervisorInitiatedCrashDump || (HvlpFlags & 2) == 0 )
  {
    KeSaveSupervisorState(CurrentPrcb->ExtendedSupervisorState, KeEnabledSupervisorXStateFeatures | 0x100, _R8);
    LOBYTE(_R8) = v80;
  }
  if ( qword_140EFA190 )
  {
    if ( PopSimulateHiberBugcheck )
      BYTE5(PopBlackBoxLock.ForegroundDpcStackListEntry.Next) = 0;
    if ( *(_BYTE *)(qword_140EFA190 + 2) )
    {
      if ( (_BYTE)_R8 )
      {
        v32 = v91;
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
        LOBYTE(_R8) = v80;
      }
      v97 = 0;
      v11 = 1;
      v80 = _R8;
    }
  }
  Context = CurrentPrcb->Context;
  v34 = v103;
  v35 = 9;
  v81 = v11;
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
    v50 = v86;
    v51 = 0;
    goto LABEL_186;
  }
  v89 = 0;
  Format = 0;
  if ( ViVerifierEnabled )
    VfNotifyVerifierOfEvent(2);
  if ( v91 == 229 )
  {
    KiScanBugCheckCallbackList(229, v35, _R8, v36);
    guard_dispatch_icall_no_overrides(0);
    HalReturnToFirmware(3);
  }
  v38 = KiBugCheckData;
  if ( v91 > 0xD1 )
  {
    switch ( v91 )
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
        v40 = 1;
        v39 = v88;
        v7 = Format;
        v79 = 1;
        goto LABEL_88;
    }
    if ( v91 != 252 )
    {
      switch ( v91 )
      {
        case 0x139u:
          v9 = Format;
          if ( v88 )
          {
            v39 = v88;
            v12 = *(_QWORD *)(v88 + 360);
            v93 = v12;
          }
          else
          {
            v12 = v6;
            v39 = 0;
            if ( v8 == 10 )
              v12 = a5;
            v93 = v12;
          }
          goto LABEL_86;
        case 0x13Du:
          v94 = 8;
          goto LABEL_84;
        case 0x14Fu:
          if ( v6 < 0x100 && a5 )
          {
            v47 = CurrentThread;
            if ( *(_QWORD *)(a5 + 8) )
              v47 = *(struct _KTHREAD **)(a5 + 8);
            CurrentThread = v47;
          }
          Process = KeGetCurrentThread()->ApcState.Process;
          v38 = (__int64 *)(HIDWORD(Process[3].ActiveGroupsMask.Masks[1]) >> 12);
          v79 = (Process[3].ActiveGroupsMask.Masks[1] & 0x100000000000LL) == 0;
          goto LABEL_84;
        case 0x1C8u:
          v90 = 1;
          goto LABEL_84;
      }
      goto LABEL_126;
    }
    goto LABEL_141;
  }
  switch ( v91 )
  {
    case 0xD1u:
    case 0xAu:
      v12 = a5;
      v93 = a5;
      if ( a5 >= ExPoolCodeStart && a5 < ExPoolCodeEnd )
      {
        KiBugCheckData[0] = 197;
        goto LABEL_84;
      }
      v44 = KiPcToFileHeader(a5, &v95, 0, &v83);
      if ( v83 )
      {
        KiBugCheckDriverOffset = a5 - v44;
        *(_QWORD *)&KiBugCheckDriver = v95 + 88;
        v45 = KiPcToFileHeader(v8, &v95, 1, &v83);
        if ( !v45 )
        {
          UnloadedDriver = MmLocateUnloadedDriver(v8);
          v9 = Format;
          v39 = v88;
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
        KiBugCheckDriverOffset = v8 - v45;
        *(_QWORD *)&KiBugCheckDriver = v95 + 88;
        goto LABEL_84;
      }
      v9 = Format;
      v39 = v88;
      v40 = 0;
      KiBugCheckData[0] = 209;
      if ( v44 )
      {
        KiBugCheckDriverOffset = a5 - v44;
        *(_QWORD *)&KiBugCheckDriver = v95 + 88;
      }
      goto LABEL_116;
    case 0x3Bu:
      v12 = a5;
      v93 = a5;
      goto LABEL_84;
    case 0x4Cu:
      v43 = 0;
      KiBugCheckData[0] = (unsigned int)v8;
      v79 = 1;
      v89 = 1;
      do
      {
        KiBugCheckData[v43 + 1] = *(_QWORD *)(v6 + 8 * v43);
        ++v43;
      }
      while ( v43 != 4 );
      v39 = v88;
      goto LABEL_87;
    case 0x50u:
      v39 = v88;
      if ( !v88 )
      {
        v41 = 0;
        if ( !v9 || ((unsigned __int8)v9 & 3) != 0 )
        {
LABEL_99:
          if ( !v41 )
          {
            v42 = MmLocateUnloadedDriver(v8);
            v9 = Format;
            v7 = Format;
            if ( v42 )
            {
              KiBugCheckDriverOffset = v8 - *(_DWORD *)(v42 + 16);
              *(_QWORD *)&KiBugCheckDriver = v42;
              KiBugCheckData[0] = 206;
            }
            goto LABEL_87;
          }
          goto LABEL_85;
        }
        v39 = (__int64)v9;
        v88 = (__int64)v9;
      }
      v93 = *(_QWORD *)(v39 + 360);
      v12 = v93;
      qword_140F45C58 = v93;
      v41 = KiPcToFileHeader(v93, &v95, 0, &v83);
      goto LABEL_99;
    case 0x7Bu:
      v82 = ((unsigned __int8)v9 & 1) == 0;
      v86 = ((unsigned __int8)v9 & 2) == 0;
      goto LABEL_84;
  }
  if ( v91 != 142 )
  {
    if ( v91 != 160 )
    {
      if ( v91 != 190 )
      {
        if ( v91 == 203 )
        {
          v12 = v8;
          v93 = v8;
LABEL_84:
          v39 = v88;
LABEL_85:
          v9 = Format;
LABEL_86:
          v7 = v9;
LABEL_87:
          v40 = v79;
          goto LABEL_88;
        }
LABEL_126:
        v39 = v88;
        if ( v88 )
        {
          v12 = *(_QWORD *)(v88 + 360);
          v93 = v12;
        }
        goto LABEL_85;
      }
      goto LABEL_141;
    }
    v9 = Format;
    v39 = v88;
    if ( (KeGetCurrentThread()->ApcState.Process[3].ActiveGroupsMask.Masks[1] & 0x100000000000LL) == 0 )
    {
      v7 = Format;
      if ( (unsigned __int64)(v8 - 240) <= 1 )
        v79 = 1;
      goto LABEL_87;
    }
    v40 = 0;
LABEL_116:
    v7 = v9;
    goto LABEL_88;
  }
LABEL_141:
  v39 = v88;
  if ( !v88 )
  {
    if ( !v9 || ((unsigned __int8)v9 & 3) != 0 )
      goto LABEL_85;
    v39 = (__int64)v9;
    v88 = (__int64)v9;
  }
  v9 = Format;
  v40 = 0;
  v7 = Format;
  if ( v91 != 142 )
  {
    v12 = *(_QWORD *)(v39 + 360);
    v93 = v12;
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
  if ( !(_DWORD)WheapHighIrqlLogSelHandler )
  {
    WheapSelLogSetNtSchedulerAvailabilityNoLock();
    if ( (int)EnterWheaIpmiContextNoLock() >= 0 )
      IpmiLibAddSelBugcheckRecord();
  }
  v49 = KiBugCheckData[0];
  v50 = v86;
  BugCheckProgressEfiSafeToCall = LODWORD(KiBugCheckData[0]) != 265;
  if ( v86 )
  {
    LOBYTE(v38) = v11;
    KiCollectTriageDumpDataBlocks(KiBugCheckData[0], v38);
  }
  if ( v87 && (PartialDumpControl & 4) != 0 )
  {
    qword_140F45C18 = v39;
    KiCrashDumpContext = (__int64)v103;
    qword_140F45C08 = (__int64)CurrentThread;
    qword_140F45C10 = (__int64)v97;
    byte_140F45C20 = v40;
    byte_140F45C21 = v11;
    KiAttemptBugcheckRecovery();
  }
  v51 = 1;
  LOBYTE(KiSystemAvailableCpusSubscriptionLock.Queue) = 1;
  guard_dispatch_icall_no_overrides(v49);
  HvlEnlightenments &= 0x2000u;
  IoSaveBugCheckProgress(96);
  v52 = 0;
  for ( i = 0; i < KiNmiInProgress[0]; ++i )
  {
    if ( qword_140E0E288[i] )
    {
      v52 = 1;
      break;
    }
  }
  guard_dispatch_icall_no_overrides(v52);
  KiFilterBugCheckInfo(&v91, KiBugCheckData);
  if ( CrashdmpDumpBlock && v50 )
    v51 = 0;
  HvlLogGuestCrashInformation(
    KiBugCheckData[0],
    qword_140F45C48,
    qword_140F45C50,
    qword_140F45C58,
    qword_140F45C60,
    v51);
  if ( !KdPitchDebugger )
    qword_140E010A8 = (__int64)v103;
  if ( (unsigned __int8)KiBugCheckShouldEnterPostBugCheckDebugger(v91, 0) )
  {
    if ( !CurrentPrcb->NmiActive )
    {
      DbgPrintEx(
        0x65u,
        0,
        "\n*** Fatal System Error: 0x%08lx\n                       (0x%p,0x%p,0x%p,0x%p)\n\n",
        LODWORD(KiBugCheckData[0]),
        (const void *)qword_140F45C48,
        (const void *)qword_140F45C50,
        (const void *)qword_140F45C58,
        (const void *)qword_140F45C60);
      if ( *(_QWORD *)&KiBugCheckDriver )
        DbgPrintEx(0x65u, 0, "Driver at fault: %s.\n", pszDest);
      if ( v89 )
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
  v54 = KeGetCurrentIrql();
  if ( (_BYTE)v54 != 15 )
    __writecr8(0xFu);
  if ( KiIrqlFlags )
    KiRaiseIrqlProcessIrqlFlags(v54);
  if ( v80 )
    goto LABEL_217;
  if ( (unsigned __int8)KiHandleMultipleBugchecksDuringRecovery((unsigned int)KiBugCheckActive) )
  {
    LOBYTE(KiSystemAvailableCpusSubscriptionLock.Queue) = 1;
LABEL_217:
    if ( (unsigned int)KeNumberProcessors_0 > 1 && !KiHypervisorInitiatedCrashDump )
    {
      KiSetDebuggerOwner(CurrentPrcb);
      *(_QWORD *)&v102.Count = 4194305;
      memset_0(&v102.8, 0, sizeof(v102.8));
      RtlpCopyAffinityEx(&v102, v102.Size, (struct _KAFFINITY_EX *)&stru_140FBF218.SavedApcStateFill[16]);
      KeRemoveProcessorAffinityEx(&v102, CurrentPrcb->Number);
      KiSendFreeze(&v102, 0);
      KeStallExecutionProcessor(0xF4240u);
    }
    IoSaveInitialBugCheckProgress(LODWORD(KiBugCheckData[0]), qword_140F45C48);
    IoSaveBugCheckProgress(1);
    LOBYTE(v70) = v51;
    KiBugCheckProgressCpusFrozen(v70);
    if ( CurrentPrcb->PowerState.ResolvedQosClass )
    {
      if ( PpmPerfVmQosSupported )
      {
        PpmHvSetVirtualProcessorQos(CurrentPrcb, 0);
      }
      else if ( PpmPerfSchedulerDirectedPerfStatesSupported && CurrentPrcb->PowerState.CheckContext.Domain )
      {
        guard_dispatch_icall_no_overrides(CurrentPrcb->PowerState.CheckContext.Constraint->PerfContext);
      }
    }
    if ( v11 )
    {
      v63 = v82;
    }
    else
    {
      v72 = v94;
      if ( v51 )
        v72 = v94 | 4;
      v63 = v82;
      v73 = v72 | 2;
      if ( v87 )
        v73 = v72;
      v74 = v73 | 1;
      if ( v82 )
        v74 = v73;
      KiDisplayBlueScreen(v74);
    }
    LOBYTE(v71) = 1;
    HvlPrepareForRootCrashdump(v71);
    if ( v11 )
    {
      v75 = 9;
    }
    else
    {
      IoSaveBugCheckProgress(2);
      KiInvokeBugCheckEntryCallbacks(1, 0, 0);
      v75 = 9;
      KiInvokeBugCheckEntryCallbacks(9, 0, 0);
      IoSaveBugCheckProgress(5);
      KiInvokeBugCheckAddTriageDumpDataCallbacks();
    }
    if ( !(_BYTE)KdDebuggerEnabled && !KdPitchDebugger )
      KdEnableDebuggerWithLock(0);
    v76 = CurrentPrcb->Context;
    v77 = v103;
    do
    {
      *(_OWORD *)&v76->P1Home = *(_OWORD *)v77;
      *(_OWORD *)&v76->P3Home = *((_OWORD *)v77 + 1);
      *(_OWORD *)&v76->P5Home = *((_OWORD *)v77 + 2);
      *(_OWORD *)&v76->ContextFlags = *((_OWORD *)v77 + 3);
      *(_OWORD *)&v76->SegGs = *((_OWORD *)v77 + 4);
      *(_OWORD *)&v76->Dr1 = *((_OWORD *)v77 + 5);
      *(_OWORD *)&v76->Dr3 = *((_OWORD *)v77 + 6);
      v78 = *((_OWORD *)v77 + 7);
      v77 += 128;
      *(_OWORD *)&v76->Dr7 = v78;
      v76 = (_CONTEXT *)((char *)v76 + 128);
      --v75;
    }
    while ( v75 );
    *(_OWORD *)&v76->P1Home = *(_OWORD *)v77;
    *(_OWORD *)&v76->P3Home = *((_OWORD *)v77 + 1);
    *(_OWORD *)&v76->P5Home = *((_OWORD *)v77 + 2);
    *(_OWORD *)&v76->ContextFlags = *((_OWORD *)v77 + 3);
    *(_OWORD *)&v76->SegGs = *((_OWORD *)v77 + 4);
    if ( v50 )
    {
      KdDecodeDataBlock(v77, 128);
      qword_140F45C08 = (__int64)CurrentThread;
      qword_140F45C10 = (__int64)v97;
      qword_140F45C18 = v88;
      byte_140F45C20 = v79;
      KiCrashDumpContext = (__int64)v103;
      byte_140F45C21 = v11;
      KiBugCheckWriteCrashDump(&KiCrashDumpContext);
    }
    goto LABEL_203;
  }
  v55 = KiBugCheckActive;
  if ( Number != (unsigned int)KiBugCheckActive >> 4 )
  {
    KiYieldWaitForDebugger();
    __debugbreak();
  }
  if ( KiHypervisorInitiatedCrashDump || (KiBugCheckActive & 0xCu) >= 8 )
  {
    IoEscalateBugCheck(16);
    while ( 1 )
      guard_dispatch_icall_no_overrides(v69);
  }
  IoSetBugCheckProgressFlag(0x20000);
  _InterlockedAdd(&KiBugCheckActive, 4u);
  if ( (v55 & 0xC) != 0 )
  {
    IoEscalateBugCheck(8);
    KiBugCheckDebugBreak(4u);
  }
  else
  {
    KiCrashDumpContext = (__int64)v103;
    qword_140F45C08 = (__int64)CurrentThread;
    qword_140F45C10 = (__int64)v97;
    qword_140F45C18 = v88;
    byte_140F45C20 = v79;
    byte_140F45C21 = v81;
    IoEscalateBugCheck(4);
    v56 = byte_140F45C20;
    v57 = qword_140F45C10;
    v58 = qword_140F45C08;
    v59 = KiCrashDumpContext;
    v60 = qword_140F45C60;
    v61 = qword_140F45C58;
    v62 = qword_140F45C50;
    v98 = qword_140F45C48;
    Number = KiBugCheckData[0];
    if ( qword_140E4C120 )
      guard_dispatch_icall_no_overrides(10);
    if ( !(unsigned __int8)IoWriteCrashDump(Number, v98, v62, v61, v60, v59, v58, v57, v56) )
      IoSetBugCheckProgressFlag(0x2000000);
  }
  v11 = v81;
  v63 = v82;
LABEL_203:
  HvlResumeFromRootCrashdump(0);
  IoSaveBugCheckProgress(99);
  if ( !v11 )
    KiScanBugCheckCallbackList(v65, v64, v66, v67);
  guard_dispatch_icall_no_overrides(v65);
  IoSaveBugCheckProgress(4);
  IoEscalateBugCheck(32);
  if ( v87 )
  {
    KiResumeForReboot = 1;
    KiSendThawExecution(0);
    KiBugcheckUnloadDebugSymbols();
    guard_dispatch_icall_no_overrides(0);
    if ( BYTE5(PopBlackBoxLock.ForegroundDpcStackListEntry.Next)
      && !BYTE6(PopBlackBoxLock.ForegroundDpcStackListEntry.Next)
      || BYTE4(PopBlackBoxLock.ForegroundDpcStackListEntry.Next)
      || v90
      || (v68 = 3, !v63) )
    {
      v68 = 1;
    }
    HalReturnToFirmware(v68);
  }
  KiBugCheckDebugBreak(4u);
}

```

## disassembly

```asm
0x1405158d0  push    rbp
0x1405158d2  push    rbx
0x1405158d3  push    rsi
0x1405158d4  push    rdi
0x1405158d5  push    r12
0x1405158d7  push    r13
0x1405158d9  push    r14
0x1405158db  push    r15
0x1405158dd  lea     rbp, [rsp-748h]
0x1405158e5  sub     rsp, 848h
0x1405158ec  mov     rax, [rbp+780h+arg_28]
0x1405158f3  mov     r14, r8
0x1405158f6  mov     r12, [rbp+780h+arg_20]
0x1405158fd  mov     r13, rdx
0x140515900  mov     [rbp+780h+var_7C8], r8
0x140515904  mov     rdi, r9
0x140515907  mov     [rbp+780h+var_7C0], rdx
0x14051590b  mov     r8d, 208h; Size
0x140515911  mov     [rbp+780h+var_800], ecx
0x140515914  xor     edx, edx; Val
0x140515916  lea     rcx, [rbp+780h+var_7A0]; void *
0x14051591a  mov     [rsp+880h+var_810], rax
0x14051591f  mov     [rbp+780h+var_7B0], r9
0x140515923  call    memset_0
0x140515928  xor     ebx, ebx
0x14051592a  mov     [rbp+780h+pszDest], bl
0x140515930  mov     esi, ebx
0x140515932  mov     rax, gs:188h
0x14051593b  cmp     cs:IopAutoReboot, ebx
0x140515941  mov     [rbp+780h+var_7D8], rax
0x140515945  lea     r15d, [rbx+1]
0x140515949  lea     rax, KiBugCheckProgress
0x140515950  mov     [rbp+780h+var_7E0], rbx
0x140515954  mov     [rbp+780h+var_7D0], rax
0x140515958  setnz   [rsp+880h+var_817]
0x14051595d  mov     eax, r15d
0x140515960  mov     [rsp+880h+var_829], bl
0x140515964  xchg    eax, cs:KiBugCheckDataInitialized
0x14051596a  mov     byte ptr [rsp+880h+var_830], bl
0x14051596e  mov     [rsp+880h+var_806], bl
0x140515972  mov     [rbp+780h+var_7B8], rbx
0x140515976  mov     [rbp+780h+var_7F0], rbx
0x14051597a  mov     [rsp+880h+var_82A], r15b
0x14051597f  mov     [rsp+880h+var_818], r15b
0x140515984  mov     [rbp+780h+var_7E8], ebx
0x140515987  test    eax, eax
0x140515989  jnz     loc_140515A1F
0x14051598f  mov     eax, [rbp+780h+var_800]
0x140515992  cmp     eax, 0C00002D1h
0x140515997  jnz     short loc_1405159A1
0x140515999  mov     eax, 0C3h
0x14051599e  mov     [rbp+780h+var_800], eax
0x1405159a1  cmp     dword ptr cs:WheapHighIrqlLogSelHandler, ebx
0x1405159a7  mov     cs:KiBugCheckData, rax
0x1405159ae  mov     cs:qword_140F45C48, r13
0x1405159b5  mov     cs:qword_140F45C50, r14
0x1405159bc  mov     cs:qword_140F45C58, rdi
0x1405159c3  mov     cs:qword_140F45C60, r12
0x1405159ca  jnz     short loc_1405159D5
0x1405159cc  mov     eax, r15d
0x1405159cf  xchg    eax, dword ptr cs:WheapConfigTableLock.___u25+24h
0x1405159d5  xor     edx, edx
0x1405159d7  xor     r8d, r8d
0x1405159da  lea     ecx, [rdx+8]
0x1405159dd  call    KiInvokeBugCheckEntryCallbacks
0x1405159e2  mov     edx, cs:dword_140E0E1D4
0x1405159e8  test    edx, edx
0x1405159ea  jns     short loc_1405159FB
0x1405159ec  xor     r8d, r8d
0x1405159ef  mov     ecx, 8000006Eh
0x1405159f4  call    KiBugCheckSelLogError
0x1405159f9  jmp     short loc_140515A12
0x1405159fb  mov     r8d, 10h
0x140515a01  lea     rdx, Uuid
0x140515a08  mov     ecx, 8000006Dh
0x140515a0d  call    KiBugCheckSelLogDataCheckPoint
0x140515a12  xor     edx, edx
0x140515a14  xor     r8d, r8d
0x140515a17  lea     ecx, [rdx+4]
0x140515a1a  call    IoNotifyDumpEx
0x140515a1f  mov     eax, cs:HvlpFlags
0x140515a25  mov     edx, 2
0x140515a2a  test    dl, al
0x140515a2c  jz      short loc_140515A3B
0x140515a2e  lea     ecx, [rdx+2]
0x140515a31  call    HvlNotifyRootCrashdump
0x140515a36  mov     edx, 2
0x140515a3b  mov     [rsp+880h+var_820], rbx
0x140515a40  mov     [rsp+880h+Format], rbx
0x140515a45  mov     [rbp+780h+var_7F8], ebx
0x140515a48  mov     rax, cr8
0x140515a4c  cmp     al, dl
0x140515a4e  jnb     short loc_140515A69
0x140515a50  mov     rcx, cr8
0x140515a54  cmp     cl, dl
0x140515a56  jz      short loc_140515A5C
0x140515a58  mov     cr8, rdx
0x140515a5c  cmp     cs:KiIrqlFlags, ebx
0x140515a62  jz      short loc_140515A69
0x140515a64  call    KiRaiseIrqlProcessIrqlFlags
0x140515a69  mov     rax, gs:188h
0x140515a72  cmp     [rax+28h], rbx
0x140515a76  jnz     short loc_140515AC3
0x140515a78  mov     rdx, gs:20h
0x140515a81  mov     eax, cs:KiBugCheckActive
0x140515a87  mov     edx, [rdx+24h]
0x140515a8a  shl     edx, 4
0x140515a8d  or      edx, 3
0x140515a90  mov     ecx, eax
0x140515a92  and     ecx, 3
0x140515a95  cmp     cl, 3
0x140515a98  jz      short loc_140515AAD
0x140515a9a  mov     ecx, eax
0x140515a9c  lock cmpxchg cs:KiBugCheckActive, edx
0x140515aa4  cmp     eax, ecx
0x140515aa6  jnz     short loc_140515A90
0x140515aa8  mov     r8b, r15b
0x140515aab  jmp     short loc_140515AB0
0x140515aad  mov     r8b, bl
0x140515ab0  mov     [rsp+880h+var_82C], r8b
0x140515ab5  test    r8b, r8b
0x140515ab8  jz      loc_140515C55
0x140515abe  jmp     loc_140515C39
0x140515ac3  lea     r8, [rsp+880h+var_820]
0x140515ac8  lea     rdx, [rsp+880h+Format]
0x140515acd  lea     rcx, [rbp+780h+var_7F8]
0x140515ad1  call    KeQueryCurrentStackInformation
0x140515ad6  mov     rdx, gs:20h
0x140515adf  mov     bl, al
0x140515ae1  mov     eax, cs:KiBugCheckActive
0x140515ae7  mov     edx, [rdx+24h]
0x140515aea  shl     edx, 4
0x140515aed  or      edx, 3
0x140515af0  mov     ecx, eax
0x140515af2  and     ecx, 3
0x140515af5  cmp     cl, 3
0x140515af8  jz      loc_140515C4C
0x140515afe  mov     ecx, eax
0x140515b00  lock cmpxchg cs:KiBugCheckActive, edx
0x140515b08  cmp     eax, ecx
0x140515b0a  jnz     short loc_140515AF0
0x140515b0c  xor     edx, edx
0x140515b0e  xor     r8d, r8d
0x140515b11  lea     ecx, [rdx+6]
0x140515b14  call    IoNotifyDumpEx
0x140515b19  test    bl, bl
0x140515b1b  jz      loc_140515BC1
0x140515b21  mov     eax, [rbp+780h+var_7F8]
0x140515b24  cmp     eax, 9
0x140515b27  ja      short loc_140515B37
0x140515b29  mov     ecx, 3A1h
0x140515b2e  bt      ecx, eax
0x140515b31  jb      loc_140515BC1
0x140515b37  mov     rax, [rsp+880h+var_820]
0x140515b3c  mov     r14b, r15b
0x140515b3f  mov     r15, [rsp+880h+Format]
0x140515b44  mov     edi, 24000h
0x140515b49  sub     rax, r15
0x140515b4c  xor     ebx, ebx
0x140515b4e  cmp     rax, rdi
0x140515b51  ja      short loc_140515B5B
0x140515b53  mov     rdi, rax
0x140515b56  test    rax, rax
0x140515b59  jz      short loc_140515BA5
0x140515b5b  lea     r13, cs:140000000h
0x140515b62  lea     rsi, [rbx+r15]
0x140515b66  xor     edx, edx
0x140515b68  mov     rcx, rsi
0x140515b6b  call    MmIsAddressValidEx
0x140515b70  test    al, al
0x140515b72  jz      short loc_140515B8E
0x140515b74  lea     rcx, rva KiSystemAvailableCpusSubscriptionLock.Timer.Header[r13]
0x140515b7b  mov     r8d, 1000h; Size
0x140515b81  add     rcx, rbx; void *
0x140515b84  mov     rdx, rsi; Src
0x140515b87  call    memmove
0x140515b8c  jmp     short loc_140515B91
0x140515b8e  xor     r14b, r14b
0x140515b91  add     rbx, 1000h
0x140515b98  cmp     rbx, rdi
0x140515b9b  jb      short loc_140515B62
0x140515b9d  mov     r13, [rbp+780h+var_7C0]
0x140515ba1  mov     rsi, [rbp+780h+var_7B8]
0x140515ba5  xor     edx, edx
0x140515ba7  movzx   r8d, r14b
0x140515bab  lea     ecx, [rdx+7]
0x140515bae  call    IoNotifyDumpEx
0x140515bb3  mov     rdi, [rbp+780h+var_7B0]
0x140515bb7  mov     r15d, 1
0x140515bbd  mov     r14, [rbp+780h+var_7C8]
0x140515bc1  xor     ebx, ebx
0x140515bc3  cmp     cs:KiKernelCetEnabled, bl
0x140515bc9  jz      short loc_140515C31
0x140515bcb  mov     rcx, gs:188h
0x140515bd4  xor     r8d, r8d
0x140515bd7  rdsspq  r8
0x140515bdc  mov     r9, [rcx+420h]
0x140515be3  and     r9, 0FFFFFFFFFFFFF000h
0x140515bea  add     r9, 1000h
0x140515bf1  cmp     r8, r9
0x140515bf4  jbe     short loc_140515C31
0x140515bf6  mov     rax, [rcx+418h]
0x140515bfd  sub     rax, 1000h
0x140515c03  cmp     r8, rax
0x140515c06  jnb     short loc_140515C31
0x140515c08  lea     rdx, [r8-100h]
0x140515c0f  mov     eax, 100h
0x140515c14  cmp     rdx, r9
0x140515c17  lea     rcx, qword_140FC0350; void *
0x140515c1e  cmovb   rdx, r9; Src
0x140515c22  sub     r8, rdx
0x140515c25  cmp     r8, rax
0x140515c28  cmova   r8, rax; Size
0x140515c2c  call    memmove
0x140515c31  mov     r8b, r15b
0x140515c34  mov     [rsp+880h+var_82C], r15b
0x140515c39  mov     eax, dword ptr cs:KsepShimDbLock.___u58+50h
0x140515c3f  test    eax, eax
0x140515c41  jg      short loc_140515C55
0x140515c43  mov     byte ptr cs:KiSystemAvailableCpusSubscriptionLock.Queue, r15b
0x140515c4a  jmp     short loc_140515C55
0x140515c4c  xor     ebx, ebx
0x140515c4e  mov     r8b, bl
0x140515c51  mov     [rsp+880h+var_82C], bl
0x140515c55  cmp     cs:KeSmapEnabled, ebx
0x140515c5b  jz      short loc_140515C60
0x140515c5d  stac
0x140515c60  mov     r15, gs:20h
0x140515c69  cmp     cs:KiHypervisorInitiatedCrashDump, bl
0x140515c6f  mov     eax, [r15+24h]
0x140515c73  mov     [rbp+780h+var_7F8], eax
0x140515c76  jz      short loc_140515C82
0x140515c78  mov     eax, cs:HvlpFlags
0x140515c7e  test    al, 2
0x140515c80  jnz     short loc_140515C9F
0x140515c82  mov     rdx, cs:KeEnabledSupervisorXStateFeatures
0x140515c89  mov     rcx, [r15+700h]
0x140515c90  bts     rdx, 8
0x140515c95  call    KeSaveSupervisorState
0x140515c9a  mov     r8b, [rsp+880h+var_82C]
0x140515c9f  mov     rax, cs:qword_140EFA190
0x140515ca6  test    rax, rax
0x140515ca9  jz      short loc_140515CFF
0x140515cab  cmp     cs:PopSimulateHiberBugcheck, ebx
0x140515cb1  jz      short loc_140515CB9
0x140515cb3  mov     byte ptr cs:PopBlackBoxLock.___u77+5, bl
0x140515cb9  cmp     [rax+2], bl
0x140515cbc  jz      short loc_140515CFF
0x140515cbe  test    r8b, r8b
0x140515cc1  jz      short loc_140515CF4
0x140515cc3  mov     ebx, [rbp+780h+var_800]
0x140515cc6  lea     r8, aABugcheckOccur; "\nA bugcheck occurred during the late s"...
0x140515ccd  xor     edx, edx; Level
0x140515ccf  lea     ecx, [rdx+65h]; ComponentId
0x140515cd2  call    DbgPrintEx
0x140515cd7  cmp     ebx, 0Ah
0x140515cda  jnz     short loc_140515CED
0x140515cdc  lea     r8, aMemoryWasAcces; "Memory was accessed during this time th"...
0x140515ce3  xor     edx, edx; Level
0x140515ce5  lea     ecx, [rbx+5Bh]; ComponentId
0x140515ce8  call    DbgPrintEx
0x140515ced  mov     r8b, [rsp+880h+var_82C]
0x140515cf2  xor     ebx, ebx
0x140515cf4  mov     [rbp+780h+var_7D0], rbx
0x140515cf8  mov     bl, 1
0x140515cfa  mov     [rsp+880h+var_82C], r8b
0x140515cff  mov     rax, [r15+6400h]
0x140515d06  lea     rcx, [rbp+780h+var_590]
0x140515d0d  mov     edx, 9
0x140515d12  mov     [rsp+880h+var_82B], bl
0x140515d16  lea     r9d, [rdx+77h]
0x140515d1a  movups  xmm0, xmmword ptr [rax]
0x140515d1d  movups  xmmword ptr [rcx], xmm0
0x140515d20  movups  xmm1, xmmword ptr [rax+10h]
0x140515d24  movups  xmmword ptr [rcx+10h], xmm1
0x140515d28  movups  xmm0, xmmword ptr [rax+20h]
0x140515d2c  movups  xmmword ptr [rcx+20h], xmm0
0x140515d30  movups  xmm1, xmmword ptr [rax+30h]
0x140515d34  movups  xmmword ptr [rcx+30h], xmm1
0x140515d38  movups  xmm0, xmmword ptr [rax+40h]
0x140515d3c  movups  xmmword ptr [rcx+40h], xmm0
0x140515d40  movups  xmm1, xmmword ptr [rax+50h]
0x140515d44  movups  xmmword ptr [rcx+50h], xmm1
0x140515d48  movups  xmm0, xmmword ptr [rax+60h]
0x140515d4c  movups  xmmword ptr [rcx+60h], xmm0
0x140515d50  movups  xmm1, xmmword ptr [rax+70h]
0x140515d54  add     rax, r9
0x140515d57  movups  xmmword ptr [rcx+70h], xmm1
0x140515d5b  add     rcx, r9
0x140515d5e  sub     rdx, 1
0x140515d62  jnz     short loc_140515D1A
0x140515d64  movups  xmm0, xmmword ptr [rax]
0x140515d67  movups  xmmword ptr [rcx], xmm0
0x140515d6a  movups  xmm1, xmmword ptr [rax+10h]
0x140515d6e  movups  xmmword ptr [rcx+10h], xmm1
0x140515d72  movups  xmm0, xmmword ptr [rax+20h]
0x140515d76  movups  xmmword ptr [rcx+20h], xmm0
0x140515d7a  movups  xmm1, xmmword ptr [rax+30h]
0x140515d7e  movups  xmmword ptr [rcx+30h], xmm1
0x140515d82  movups  xmm0, xmmword ptr [rax+40h]
  ... truncated ...
```
