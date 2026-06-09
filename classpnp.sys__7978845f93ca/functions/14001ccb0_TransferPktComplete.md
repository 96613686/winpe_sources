# TransferPktComplete

- ea: `0x14001ccb0`
- end: `0x14001e2e9`
- name: `TransferPktComplete`
- size: `5689`
- prototype: ``
- caller_count: `0`
- callee_count: `31`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x1400020f0`
- `0x140002450`
- `0x140002fb0`
- `0x140005190`
- `0x140005560`
- `0x1400076b0`
- `0x1400077ac`
- `0x14000be64`
- `0x1400134a0`
- `0x140015120`
- `0x140015550`
- `0x140015890`
- `0x140015b00`
- `0x140015c50`
- `0x140016730`
- `0x140016880`
- `0x1400176f8`
- `0x1400188b4`
- `0x140018af0`
- `0x14001ccb0`
- `0x14001f450`
- `0x14001fbf4`
- `0x14001fc38`
- `0x14001fc7c`
- `0x14001feac`
- `0x140020070`
- `0x140029ff4`
- `0x14002a090`
- `0x14003dac8`
- `0x14003e430`
- `0x14003e470`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x14001dbd6`
- `ntoskrnl!EtwWriteTransfer` at `0x14001dbd6`
- `ntoskrnl!KeSetEvent` at `0x14001e104`
- `ntoskrnl!KeSetEvent` at `0x14001e104`
- `ntoskrnl!IoStartNextPacket` at `0x14001e0d8`
- `ntoskrnl!IoStartNextPacket` at `0x14001e0d8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001df41`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001e173`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001df41`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001e173`
- `ntoskrnl!KeQueryUnbiasedInterruptTimePrecise` at `0x14001cd51`
- `ntoskrnl!KeQueryUnbiasedInterruptTimePrecise` at `0x14001d2ce`
- `ntoskrnl!KeQueryUnbiasedInterruptTimePrecise` at `0x14001d63c`
- `ntoskrnl!KeQueryUnbiasedInterruptTimePrecise` at `0x14001cd51`
- `ntoskrnl!KeQueryUnbiasedInterruptTimePrecise` at `0x14001d2ce`
- `ntoskrnl!KeQueryUnbiasedInterruptTimePrecise` at `0x14001d63c`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14001d9b1`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14001d9b1`
- `ntoskrnl!IoGetPagingIoPriority` at `0x14001de08`
- `ntoskrnl!IoGetPagingIoPriority` at `0x14001de08`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14001e280`
- `ntoskrnl!IoGetActivityIdIrp` at `0x14001e280`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001dfaf`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001e19f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001e24d`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001dfaf`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001e19f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001e24d`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x14001d597`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x14001d597`
- `ntoskrnl!KeLowerIrql` at `0x14001e0e7`
- `ntoskrnl!KeLowerIrql` at `0x14001e0e7`
- `ntoskrnl!IoSetHardErrorOrVerifyDevice` at `0x14001ddb6`
- `ntoskrnl!IoSetHardErrorOrVerifyDevice` at `0x14001ddb6`
- `ntoskrnl!KfRaiseIrql` at `0x14001e0c4`
- `ntoskrnl!KfRaiseIrql` at `0x14001e0c4`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14001d1fd`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14001d1fd`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14001e1df`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14001e1df`
- `ntoskrnl!IoSetMasterIrpStatus` at `0x14001dd61`
- `ntoskrnl!IoSetMasterIrpStatus` at `0x14001dd61`
- `ntoskrnl!MmUnmapLockedPages` at `0x14001d3b8`
- `ntoskrnl!MmUnmapLockedPages` at `0x14001d3b8`
- `ntoskrnl!IoGetIoAttributionHandle` at `0x14001d303`
- `ntoskrnl!IoGetIoAttributionHandle` at `0x14001d303`
- `ntoskrnl!IoSetGenericIrpExtension` at `0x14001df0c`
- `ntoskrnl!IoSetGenericIrpExtension` at `0x14001df0c`
- `ntoskrnl!IoGetGenericIrpExtension` at `0x14001de99`
- `ntoskrnl!IoGetGenericIrpExtension` at `0x14001de99`

## pseudocode

```c
__int64 __fastcall TransferPktComplete(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rax
  char v4; // r12
  __int64 QuadPart; // r13
  _CLASS_PRIVATE_FDO_DATA *PrivateFdoData; // r15
  unsigned __int64 v8; // rbx
  ULONG64 v9; // rax
  unsigned __int64 v10; // rcx
  bool v11; // zf
  _LARGE_INTEGER DegradedIoThresholdTime; // rax
  __int64 v13; // r9
  unsigned int v14; // ebx
  unsigned int v15; // r11d
  __int64 v16; // rcx
  unsigned __int64 v17; // rdx
  __int64 v18; // r10
  __int64 v19; // r8
  int v20; // ecx
  int v21; // ecx
  unsigned __int64 v22; // rcx
  unsigned __int8 v23; // si
  unsigned int v24; // ebx
  unsigned int i; // r10d
  __int64 v26; // rcx
  unsigned __int64 v27; // rdx
  __int64 v28; // r11
  __int64 v29; // r8
  int v30; // ecx
  int v31; // ecx
  unsigned __int64 v32; // rcx
  __int64 v33; // r15
  int v34; // r12d
  unsigned int v35; // ebx
  unsigned int v36; // r10d
  __int64 v37; // rcx
  unsigned __int64 v38; // rdx
  __int64 v39; // r11
  __int64 v40; // r8
  int v41; // ecx
  int v42; // ecx
  unsigned __int64 v43; // rcx
  unsigned int v44; // r10d
  unsigned __int8 v45; // bl
  __int64 v46; // rcx
  unsigned __int64 v47; // rdx
  __int64 v48; // r11
  __int64 v49; // r8
  int v50; // ecx
  int v51; // ecx
  unsigned __int64 v52; // rcx
  unsigned __int8 v53; // dl
  char v54; // r8
  unsigned __int8 v55; // al
  unsigned __int8 v56; // r14
  char v57; // bl
  unsigned int v58; // esi
  __int64 v59; // r10
  __int64 v60; // rcx
  unsigned __int64 v61; // rdx
  __int64 v62; // r11
  __int64 v63; // r8
  int v64; // ecx
  int v65; // ecx
  unsigned __int64 v66; // rcx
  __int64 v67; // r10
  __int64 v68; // r14
  char v69; // r15
  char *v70; // rbx
  unsigned int v71; // esi
  __int64 v72; // r11
  __int64 v73; // rcx
  unsigned __int64 v74; // rdx
  __int64 v75; // r9
  __int64 v76; // r8
  int v77; // ecx
  int v78; // ecx
  unsigned __int64 v79; // rcx
  __int64 v80; // rdx
  PFUNCTIONAL_DEVICE_EXTENSION v81; // r11
  int v82; // esi
  __int64 v83; // rcx
  __int64 v84; // r9
  PVOID v85; // rax
  char v86; // cl
  char v87; // dl
  char v88; // r8
  char v89; // al
  volatile unsigned __int8 SectorShift; // cl
  ULONG64 v91; // rbx
  unsigned __int64 QosMaxNumberOfTimeoutRetries; // r8
  __int64 v93; // rcx
  __int64 v94; // rcx
  unsigned int v95; // edx
  __int64 v96; // r12
  _BYTE *v97; // r15
  unsigned __int64 v98; // r13
  char v99; // r15
  char v100; // al
  char v101; // si
  __int64 v102; // rax
  __int64 v103; // rbx
  __int64 v104; // rbx
  __int64 v105; // r14
  char *v106; // rcx
  char v107; // si
  ULONG64 v108; // r9
  __int64 v109; // rdx
  unsigned __int8 v110; // r12
  _BYTE *v111; // r10
  unsigned int v112; // esi
  unsigned int j; // r11d
  __int64 v114; // rcx
  __int64 v115; // rbx
  __int64 v116; // r9
  int v117; // ecx
  int v118; // ecx
  unsigned __int64 v119; // rcx
  unsigned __int8 v120; // si
  unsigned int v121; // r14d
  unsigned int v122; // r11d
  __int64 v123; // rcx
  __int64 v124; // rbx
  __int64 v125; // r9
  int v126; // ecx
  int v127; // ecx
  unsigned __int64 v128; // rcx
  char v129; // cl
  _BYTE *v130; // rax
  unsigned __int8 v131; // r14
  unsigned __int8 v132; // r13
  unsigned __int8 *v133; // rdx
  unsigned int v134; // eax
  unsigned __int64 v135; // rcx
  char v136; // al
  __int64 v137; // rdx
  __int64 v138; // r10
  char *v139; // rsi
  unsigned int v140; // ebx
  __int64 v141; // r11
  __int64 v142; // rcx
  unsigned __int64 v143; // rdx
  __int64 v144; // r9
  int v145; // ecx
  int v146; // ecx
  unsigned __int64 v147; // rcx
  char v148; // r15
  signed __int64 v149; // rbx
  ULONGLONG UnbiasedInterruptTime; // rdx
  __int64 v151; // rcx
  __int64 v152; // rax
  char v153; // al
  PFUNCTIONAL_DEVICE_EXTENSION v154; // r12
  __int64 v155; // r10
  __int64 v156; // rsi
  unsigned int v157; // ebx
  __int64 k; // r9
  __int64 v159; // rcx
  unsigned __int64 v160; // rdx
  __int64 v161; // r11
  __int64 v162; // r8
  int v163; // ecx
  int v164; // ecx
  unsigned __int64 v165; // rcx
  __int64 v166; // r9
  unsigned int v167; // ebx
  __int64 v168; // r10
  __int64 v169; // rcx
  unsigned __int64 v170; // rdx
  __int64 v171; // r11
  __int64 v172; // r8
  int v173; // ecx
  int v174; // ecx
  unsigned __int64 v175; // rcx
  __int64 v176; // rbx
  int v177; // ecx
  _BYTE *v178; // rbx
  struct _DEVICE_OBJECT *v179; // r13
  IRP *v180; // rcx
  char v181; // si
  __int64 v182; // rcx
  IRP *v183; // rcx
  IO_PAGING_PRIORITY PagingIoPriority; // r14d
  __int64 v185; // rcx
  _BYTE *v186; // rbx
  char v187; // si
  unsigned int v188; // r15d
  char v189; // r12
  __int64 v190; // rcx
  int GenericIrpExtension; // eax
  char v192; // si
  __int64 v193; // r9
  char v194; // dl
  _CLASS_PRIVATE_FDO_DATA *v195; // rsi
  KIRQL v196; // al
  unsigned int MaxInterleavedNormalIo; // r8d
  unsigned int v198; // edx
  KIRQL v199; // r9
  __int64 v200; // rdx
  _LARGE_INTEGER LongestThrottlePeriod; // rax
  _LARGE_INTEGER v202; // rdx
  _CLASS_PRIVATE_FDO_DATA *v203; // rbx
  __int64 v204; // rax
  __int64 v205; // rcx
  __int64 v206; // rax
  KIRQL v207; // bl
  struct _KEVENT *v208; // rcx
  void (__fastcall *v209)(_QWORD); // rax
  _QWORD *DeviceExtension; // r14
  __int64 v211; // rdi
  KIRQL v212; // al
  _QWORD *v213; // rdx
  KIRQL v214; // cl
  _QWORD *v215; // rbx
  _DWORD **v216; // r8
  signed __int32 v217; // eax
  signed __int32 v218; // ett
  __int64 v220; // rax
  int v221; // edx
  int v222; // ecx
  unsigned int v223; // [rsp+50h] [rbp-B0h] BYREF
  char v224; // [rsp+54h] [rbp-ACh]
  char v225; // [rsp+55h] [rbp-ABh]
  unsigned __int64 v226; // [rsp+58h] [rbp-A8h] BYREF
  char v227; // [rsp+60h] [rbp-A0h] BYREF
  char v228; // [rsp+61h] [rbp-9Fh] BYREF
  char v229; // [rsp+62h] [rbp-9Eh] BYREF
  char v230; // [rsp+63h] [rbp-9Dh] BYREF
  unsigned __int8 v231; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned __int8 v232; // [rsp+65h] [rbp-9Bh] BYREF
  unsigned __int8 v233; // [rsp+66h] [rbp-9Ah] BYREF
  _BYTE *v234; // [rsp+68h] [rbp-98h]
  unsigned __int64 QpcTimeStamp; // [rsp+70h] [rbp-90h] BYREF
  PFUNCTIONAL_DEVICE_EXTENSION FdoExtension; // [rsp+78h] [rbp-88h]
  __int64 v237; // [rsp+80h] [rbp-80h]
  _CLASS_PRIVATE_FDO_DATA *v238; // [rsp+88h] [rbp-78h]
  __int64 v239; // [rsp+90h] [rbp-70h] BYREF
  char v240; // [rsp+A5h] [rbp-5Bh] BYREF
  char v241; // [rsp+A6h] [rbp-5Ah] BYREF
  _BYTE v242[6]; // [rsp+AAh] [rbp-56h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+B0h] [rbp-50h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+C0h] [rbp-40h] BYREF
  char *v245; // [rsp+D0h] [rbp-30h]
  int v246; // [rsp+D8h] [rbp-28h]
  int v247; // [rsp+DCh] [rbp-24h]
  _GUID *p_DeviceGuid; // [rsp+E0h] [rbp-20h]
  __int64 v249; // [rsp+E8h] [rbp-18h]
  char *v250; // [rsp+F0h] [rbp-10h]
  __int64 v251; // [rsp+F8h] [rbp-8h]
  unsigned __int64 *v252; // [rsp+100h] [rbp+0h]
  __int64 v253; // [rsp+108h] [rbp+8h]
  char *v254; // [rsp+110h] [rbp+10h]
  __int64 v255; // [rsp+118h] [rbp+18h]
  char *v256; // [rsp+120h] [rbp+20h]
  __int64 v257; // [rsp+128h] [rbp+28h]
  char *v258; // [rsp+130h] [rbp+30h]
  __int64 v259; // [rsp+138h] [rbp+38h]
  char *v260; // [rsp+140h] [rbp+40h]
  __int64 v261; // [rsp+148h] [rbp+48h]
  char *v262; // [rsp+150h] [rbp+50h]
  __int64 v263; // [rsp+158h] [rbp+58h]
  char *v264; // [rsp+160h] [rbp+60h]
  __int64 v265; // [rsp+168h] [rbp+68h]

  v3 = *(_QWORD *)(a3 + 40);
  v4 = 0;
  v237 = a2;
  v225 = 0;
  QuadPart = 0;
  v234 = 0;
  FdoExtension = *(PFUNCTIONAL_DEVICE_EXTENSION *)(v3 + 64);
  PrivateFdoData = FdoExtension->PrivateFdoData;
  v238 = PrivateFdoData;
  v239 = 0;
  if ( *(_QWORD *)(a3 + 312) )
    HistoryLogReturnedPacket(a3);
  if ( ClassPnPPerfSensitiveEtwEventsEnabled || PrivateFdoData->DegradedIoThresholdTime.QuadPart )
  {
    v8 = *(_QWORD *)(a3 + 320);
    if ( v8 )
    {
      QpcTimeStamp = 0;
      v9 = KeQueryUnbiasedInterruptTimePrecise(&QpcTimeStamp);
      v10 = v9 - v8 - 1;
      if ( v9 >= v8 )
        v10 = v9 - v8;
      v11 = ClassPnPPerfSensitiveEtwEventsEnabled == 0;
      QpcTimeStamp = v10;
      *(_QWORD *)(a3 + 368) = v10;
      if ( !v11 )
        ClasspWriteIOPerformanceMeasurementEvent(a3);
      DegradedIoThresholdTime = PrivateFdoData->DegradedIoThresholdTime;
      if ( DegradedIoThresholdTime.QuadPart )
      {
        if ( *(_QWORD *)(a3 + 368) > DegradedIoThresholdTime.QuadPart && !*(_BYTE *)(a3 + 376) )
        {
          v13 = *(_QWORD *)(a3 + 288);
          if ( *(_BYTE *)(v13 + 2) == 40 )
          {
            if ( *(_DWORD *)(v13 + 20) )
              goto LABEL_32;
            v14 = *(_DWORD *)(v13 + 56);
            if ( !v14 )
              goto LABEL_32;
            v15 = 0;
            while ( 1 )
            {
              v16 = *(unsigned int *)(v13 + 4LL * v15 + 120);
              if ( (unsigned int)v16 < 0x80 )
                goto LABEL_28;
              v17 = *(unsigned int *)(v13 + 16);
              if ( (unsigned int)v16 >= (unsigned int)v17 )
                goto LABEL_28;
              v18 = v16 + v13;
              v19 = (unsigned int)v16;
              v20 = *(_DWORD *)(v16 + v13) - 64;
              if ( !v20 )
                break;
              v21 = v20 - 1;
              if ( !v21 )
              {
                v22 = v19 + 56;
                goto LABEL_27;
              }
              if ( v21 == 1 && v19 + 40 <= v17 )
              {
                if ( *(_DWORD *)(v18 + 12) )
                  QuadPart = v18 + 32;
                goto LABEL_32;
              }
LABEL_28:
              if ( ++v15 >= v14 )
                goto LABEL_32;
            }
            v22 = v19 + 40;
LABEL_27:
            if ( v22 > v17 )
              goto LABEL_28;
            if ( *(_BYTE *)(v18 + 10) )
              QuadPart = v18 + 24;
LABEL_32:
            v23 = 0;
            if ( !*(_DWORD *)(v13 + 20) )
            {
              v24 = *(_DWORD *)(v13 + 56);
              if ( v24 )
              {
                for ( i = 0; i < v24; ++i )
                {
                  v26 = *(unsigned int *)(v13 + 4LL * i + 120);
                  if ( (unsigned int)v26 < 0x80 )
                    continue;
                  v27 = *(unsigned int *)(v13 + 16);
                  if ( (unsigned int)v26 >= (unsigned int)v27 )
                    continue;
                  v28 = v26 + v13;
                  v29 = (unsigned int)v26;
                  v30 = *(_DWORD *)(v26 + v13) - 64;
                  if ( v30 )
                  {
                    v31 = v30 - 1;
                    if ( v31 )
                    {
                      if ( v31 == 1 && v29 + 40 <= v27 )
                        break;
                      continue;
                    }
                    v32 = v29 + 56;
                  }
                  else
                  {
                    v32 = v29 + 40;
                  }
                  if ( v32 <= v27 )
                  {
                    v23 = *(_BYTE *)(v28 + 10);
                    break;
                  }
                }
              }
            }
            v33 = 0;
            v34 = v23;
            if ( !*(_DWORD *)(v13 + 20) )
            {
              v35 = *(_DWORD *)(v13 + 56);
              if ( !v35 )
                goto LABEL_64;
              v36 = 0;
              while ( 1 )
              {
                v37 = *(unsigned int *)(v13 + 4LL * v36 + 120);
                if ( (unsigned int)v37 < 0x80 )
                  goto LABEL_61;
                v38 = *(unsigned int *)(v13 + 16);
                if ( (unsigned int)v37 >= (unsigned int)v38 )
                  goto LABEL_61;
                v39 = v37 + v13;
                v40 = (unsigned int)v37;
                v41 = *(_DWORD *)(v37 + v13) - 64;
                if ( !v41 )
                  break;
                v42 = v41 - 1;
                if ( !v42 )
                {
                  v43 = v40 + 56;
                  goto LABEL_60;
                }
                if ( v42 == 1 && v40 + 40 <= v38 )
                {
                  v33 = *(_QWORD *)(v39 + 24);
                  goto LABEL_64;
                }
LABEL_61:
                if ( ++v36 >= v35 )
                  goto LABEL_64;
              }
              v43 = v40 + 40;
LABEL_60:
              if ( v43 > v38 )
                goto LABEL_61;
              v33 = *(_QWORD *)(v39 + 16);
LABEL_64:
              if ( v35 )
              {
                v44 = 0;
                v45 = 0;
                while ( 1 )
                {
                  v46 = *(unsigned int *)(v13 + 4LL * v44 + 120);
                  if ( (unsigned int)v46 < 0x80 )
                    goto LABEL_73;
                  v47 = *(unsigned int *)(v13 + 16);
                  if ( (unsigned int)v46 >= (unsigned int)v47 )
                    goto LABEL_73;
                  v48 = v46 + v13;
                  v49 = (unsigned int)v46;
                  v50 = *(_DWORD *)(v46 + v13) - 64;
                  if ( !v50 )
                    goto LABEL_71;
                  v51 = v50 - 1;
                  if ( v51 )
                    break;
                  v52 = v49 + 56;
LABEL_72:
                  if ( v52 <= v47 )
                  {
                    v45 = *(_BYTE *)(v48 + 9);
                    goto LABEL_79;
                  }
LABEL_73:
                  if ( ++v44 >= *(_DWORD *)(v13 + 56) )
                    goto LABEL_79;
                }
                if ( v51 != 1 )
                  goto LABEL_73;
LABEL_71:
                v52 = v49 + 40;
                goto LABEL_72;
              }
            }
            v45 = 0;
          }
          else
          {
            v33 = *(_QWORD *)(v13 + 32);
            QuadPart = v13 + 72;
            v45 = *(_BYTE *)(v13 + 11);
            v34 = *(unsigned __int8 *)(v13 + 10);
          }
LABEL_79:
          if ( !v33 || !v45 )
            goto LABEL_88;
          v53 = 0;
          v54 = 0;
          if ( v33 + 8 <= v33 + (unsigned __int64)v45 )
          {
            v55 = *(_BYTE *)(v33 + 7);
            if ( v55 <= 0xF7u )
            {
              v53 = v55 + 8;
              v54 = 1;
            }
          }
          if ( v54 )
          {
            v56 = v45;
            if ( v53 < v45 )
              v56 = v53;
          }
          else
          {
LABEL_88:
            v56 = v45;
          }
          *(_BYTE *)(a3 + 376) = 1;
          if ( *(_BYTE *)(v13 + 2) == 40 )
          {
            v57 = 0;
            if ( !*(_DWORD *)(v13 + 20) )
            {
              v58 = *(_DWORD *)(v13 + 56);
              if ( v58 )
              {
                v59 = 0;
                while ( 1 )
                {
                  v60 = *(unsigned int *)(v13 + 4 * v59 + 120);
                  if ( (unsigned int)v60 < 0x80 )
                    goto LABEL_100;
                  v61 = *(unsigned int *)(v13 + 16);
                  if ( (unsigned int)v60 >= (unsigned int)v61 )
                    goto LABEL_100;
                  v62 = v60 + v13;
                  v63 = (unsigned int)v60;
                  v64 = *(_DWORD *)(v60 + v13) - 64;
                  if ( !v64 )
                    goto LABEL_98;
                  v65 = v64 - 1;
                  if ( v65 )
                    break;
                  v66 = v63 + 56;
LABEL_99:
                  if ( v66 <= v61 )
                  {
                    v57 = *(_BYTE *)(v62 + 8);
                    goto LABEL_105;
                  }
LABEL_100:
                  v59 = (unsigned int)(v59 + 1);
                  if ( (unsigned int)v59 >= v58 )
                    goto LABEL_105;
                }
                if ( v65 != 1 )
                  goto LABEL_100;
LABEL_98:
                v66 = v63 + 40;
                goto LABEL_99;
              }
            }
          }
          else
          {
            v57 = *(_BYTE *)(v13 + 4);
          }
LABEL_105:
          ClasspQueueLogIOEventWithContextWorker(*(PDEVICE_OBJECT *)(a3 + 40), v56, v57, -2147221349, v34, QuadPart, a3);
          QuadPart = (__int64)v234;
          v4 = 0;
          PrivateFdoData = v238;
        }
      }
    }
  }
  v67 = *(_QWORD *)(a3 + 288);
  v68 = 60;
  if ( (*(_BYTE *)(v67 + 3) & 0x3F) == 1 )
  {
    v69 = *(_BYTE *)(v67 + 2);
    if ( v69 != 40 )
    {
      v70 = (char *)(v67 + 72);
      goto LABEL_127;
    }
    v70 = 0;
    if ( !*(_DWORD *)(v67 + 20) )
    {
      v71 = *(_DWORD *)(v67 + 56);
      if ( v71 )
      {
        v72 = 0;
        do
        {
          v73 = *(unsigned int *)(v67 + 4 * v72 + 120);
          if ( (unsigned int)v73 < 0x80 )
            goto LABEL_122;
          v74 = *(unsigned int *)(v67 + 16);
          if ( (unsigned int)v73 >= (unsigned int)v74 )
            goto LABEL_122;
          v75 = v73 + v67;
          v76 = (unsigned int)v73;
          v77 = *(_DWORD *)(v73 + v67) - 64;
          if ( v77 )
          {
            v78 = v77 - 1;
            if ( v78 )
            {
              if ( v78 == 1 && v76 + 40 <= v74 )
              {
                if ( *(_DWORD *)(v75 + 12) )
                  v70 = (char *)(v75 + 32);
                break;
              }
              goto LABEL_122;
            }
            v79 = v76 + 56;
          }
          else
          {
            v79 = v76 + 40;
          }
          if ( v79 <= v74 )
          {
            if ( *(_BYTE *)(v75 + 10) )
              v70 = (char *)(v75 + 24);
            break;
          }
LABEL_122:
          v72 = (unsigned int)(v72 + 1);
        }
        while ( (unsigned int)v72 < v71 );
      }
    }
LABEL_127:
    v80 = 60;
    v11 = v69 == 40;
    v226 = 0;
    PrivateFdoData = v238;
    if ( !v11 )
      v80 = 16;
    if ( v238->PageHashErrorLog )
    {
      v81 = FdoExtension;
      if ( FdoExtension->CommonExtension.PagingPathCount )
      {
        if ( (*(_DWORD *)(*(_QWORD *)(a3 + 48) + 16LL) & 0x42) != 0 )
        {
          v82 = *(_DWORD *)(v67 + v80);
          if ( (v82 & 0xFFF) == 0 )
          {
            v83 = *(_QWORD *)(*(_QWORD *)(a3 + 32) + 8LL);
            if ( (*(_BYTE *)(v83 + 10) & 5) != 0 )
            {
              v84 = *(_QWORD *)(v83 + 24);
            }
            else
            {
              v85 = MmMapLockedPagesSpecifyCache((PMDL)v83, 0, MmCached, 0, 0, 0x40000020u);
              v81 = FdoExtension;
              v84 = (__int64)v85;
            }
            if ( v84 )
            {
              if ( v70 )
              {
                v86 = *v70;
                if ( *v70 == 40 || v86 == -120 )
                {
                  v87 = v70[3];
                  v88 = v70[4];
                  if ( v86 == 40 )
                  {
                    BYTE3(v226) = v70[2];
                    v89 = v70[5];
                    BYTE2(v226) = v87;
                    BYTE1(v226) = v88;
                  }
                  else
                  {
                    HIBYTE(v226) = v70[2];
                    BYTE4(v226) = v70[5];
                    BYTE3(v226) = v70[6];
                    BYTE2(v226) = v70[7];
                    BYTE1(v226) = v70[8];
                    v89 = v70[9];
                    BYTE6(v226) = v87;
                    BYTE5(v226) = v88;
                  }
                  SectorShift = v81->SectorShift;
                  LOBYTE(v226) = v89;
                  ComputePageWriteHashes(
                    (__int64)PrivateFdoData,
                    v226 << SectorShift,
                    v82,
                    v84,
                    0,
                    *(_QWORD *)(*(_QWORD *)(a3 + 32) + 8LL));
                }
              }
            }
          }
        }
      }
    }
  }
  QpcTimeStamp = 0;
  v91 = KeQueryUnbiasedInterruptTimePrecise(&QpcTimeStamp);
  QpcTimeStamp = v91;
  if ( PrivateFdoData->AttributedIoCount )
  {
    QuadPart = PrivateFdoData->LastIoCompletionTime.QuadPart;
    PrivateFdoData->LastIoCompletionTime.QuadPart = v91;
  }
  if ( (int)IoGetIoAttributionHandle(*(_QWORD *)(a3 + 48), &v239) >= 0 )
  {
    _InterlockedDecrement(&PrivateFdoData->AttributedIoCount);
    v4 = 1;
  }
  if ( (PrivateFdoData->FdoDataFlags.AsUlong & 1) != 0 )
  {
    v225 = *(_BYTE *)(*(_QWORD *)(a3 + 48) + 128LL);
    if ( v225 )
    {
      _InterlockedDecrement(&PrivateFdoData->ActiveIdleIoCount);
    }
    else
    {
      QosMaxNumberOfTimeoutRetries = 0x346DC5D63886594BLL;
      if ( v91 / 0x2710 > PrivateFdoData->LastNonIdleIoTime.QuadPart )
        PrivateFdoData->LastNonIdleIoTime.QuadPart = (__int64)v91 / 10000;
      _InterlockedDecrement(&PrivateFdoData->PerProcessorData[(unsigned __int64)HIDWORD(KeGetPcr()[1].LockArray)].ActiveIoCount);
    }
  }
  if ( *(_BYTE *)(a3 + 296) )
  {
    v93 = *(_QWORD *)(a3 + 304);
    if ( (*(_BYTE *)(v93 + 10) & 0x20) != 0 )
      MmUnmapLockedPages(*(PVOID *)(v93 + 24), *(PMDL *)(a3 + 304));
  }
  v94 = *(_QWORD *)(a3 + 288);
  if ( (*(_BYTE *)(v94 + 3) & 0x3F) == 1 )
  {
    if ( *(_BYTE *)(v94 + 2) != 40 )
      v68 = 16;
    v95 = *(_DWORD *)(v68 + v94);
    if ( PrivateFdoData->LoggedTURFailureSinceLastIO )
      PrivateFdoData->LoggedTURFailureSinceLastIO = 0;
    _InterlockedAdd((volatile signed __int32 *)(*(_QWORD *)(a3 + 48) + 56LL), v95);
    if ( v4 )
      TransferPktRecordIoAttribution(a3, v91, QuadPart, 0);
    if ( !*(_BYTE *)(a3 + 209) && (!*(_BYTE *)(a3 + 208) || !*(_DWORD *)(a3 + 224)) )
    {
      v96 = v237;
      v97 = (_BYTE *)(a3 + 56);
LABEL_168:
      v234 = v97;
      goto LABEL_169;
    }
    v100 = StepLowMemRetry((PVOID)a3);
    v96 = v237;
    v97 = (_BYTE *)(a3 + 56);
  }
  else
  {
    if ( *(int *)(v237 + 48) >= 0 )
      *(_DWORD *)(v237 + 48) = -1073741823;
    v11 = *(_BYTE *)(a3 + 56) == 0;
    v97 = (_BYTE *)(a3 + 56);
    v234 = (_BYTE *)(a3 + 56);
    if ( !v11 )
      *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(a3 + 48) + 184LL) + 3LL) |= 1u;
    v101 = InterpretTransferPacketError(a3);
    if ( (*(_BYTE *)(*(_QWORD *)(a3 + 288) + 3LL) & 0x40) != 0 )
      ClasspReleaseQueue(*(_QWORD *)(a3 + 40), 0);
    if ( v4 )
      TransferPktRecordIoAttribution(a3, v91, QuadPart, 0);
    v96 = v237;
    if ( *(int *)(v237 + 48) < 0 )
    {
      if ( !v101 || !*(_BYTE *)(a3 + 57) && !*(_QWORD *)(a3 + 312) )
        goto LABEL_168;
      v100 = RetryTransferPacket((PVOID)a3);
    }
    else
    {
      v102 = *(_QWORD *)(a3 + 288);
      if ( *(_BYTE *)(v102 + 2) != 40 )
        v68 = 16;
      _InterlockedAdd((volatile signed __int32 *)(*(_QWORD *)(a3 + 48) + 56LL), *(_DWORD *)(v68 + v102));
      if ( !*(_BYTE *)(a3 + 209) && (!*(_BYTE *)(a3 + 208) || !*(_DWORD *)(a3 + 224)) )
        goto LABEL_169;
      v100 = StepLowMemRetry((PVOID)a3);
    }
  }
  v234 = v97;
  if ( !v100 )
    return 3221225494LL;
LABEL_169:
  v11 = *(_BYTE *)(a3 + 296) == 0;
  v98 = *(_QWORD *)(a3 + 40);
  QpcTimeStamp = v98;
  if ( v11 && *v97 )
  {
    v99 = 1;
    v224 = 1;
  }
  else
  {
    v103 = *(_QWORD *)(v98 + 64);
    v99 = 0;
    v224 = 0;
    if ( !ExAcquireRundownProtectionCacheAware((PEX_RUNDOWN_REF_CACHE_AWARE)(*(_QWORD *)(v103 + 440) + 8LL)) )
    {
      _InterlockedIncrement(*(volatile signed __int32 **)(v103 + 440));
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          14,
          WPP_a22cc05f221e30b8049471910da99059_Traceguids,
          **(unsigned int **)(v103 + 440));
      }
    }
  }
  if ( ClassPnPPerfSensitiveEtwEventsEnabled )
  {
    v104 = *(_QWORD *)(a3 + 320);
    if ( v104 )
    {
      v105 = *(_QWORD *)(*(_QWORD *)(a3 + 40) + 64LL);
      v106 = *(char **)(*(_QWORD *)(a3 + 48) + 184LL);
      v226 = 0;
      if ( v106 )
      {
        v107 = *v106;
        if ( (unsigned __int8)(*v106 - 3) <= 1u )
        {
          v108 = (KeQueryUnbiasedInterruptTimePrecise(&v226) - v104) / 0xA;
          v226 = v108;
          if ( ((__int64)WPP_MAIN_CB.Queue.Wcb.CurrentIrp & 1) != 0 )
            McTemplateK0xppuuuq_EtwWriteTransfer(
              *(_QWORD *)(a3 + 288),
              *(_QWORD *)(a3 + 48),
              QosMaxNumberOfTimeoutRetries,
              v108,
              *(_QWORD *)(a3 + 48),
              *(_QWORD *)(a3 + 32),
              v107,
              *(_BYTE *)(*(_QWORD *)(a3 + 48) + 128LL),
              *(_BYTE *)(*(_QWORD *)(a3 + 288) + 3LL),
              *(_DWORD *)(v105 + 588));
        }
      }
    }
  }
  if ( ClassPnPETWEnabled )
    ClasspWriteIOResultEvent(v98, a3, v96);
  v109 = *(_QWORD *)(a3 + 288);
  v110 = 0;
  *(_QWORD *)(a3 + 320) = 0;
  if ( *(_BYTE *)(v109 + 2) != 40 )
  {
    v120 = *(_BYTE *)(v109 + 11);
    v111 = *(_BYTE **)(v109 + 32);
    goto LABEL_239;
  }
  v111 = 0;
  if ( !*(_DWORD *)(v109 + 20) )
  {
    v112 = *(_DWORD *)(v109 + 56);
    if ( v112 )
    {
      for ( j = 0; j < v112; ++j )
      {
        v114 = *(unsigned int *)(v109 + 4LL * j + 120);
        if ( (unsigned int)v114 < 0x80 )
          continue;
        QosMaxNumberOfTimeoutRetries = *(unsigned int *)(v109 + 16);
        if ( (unsigned int)v114 >= (unsigned int)QosMaxNumberOfTimeoutRetries )
          continue;
        v115 = v109 + v114;
        v116 = (unsigned int)v114;
        v117 = *(_DWORD *)(v109 + v114) - 64;
        if ( v117 )
        {
          v118 = v117 - 1;
          if ( v118 )
          {
            if ( v118 == 1 && v116 + 40 <= QosMaxNumberOfTimeoutRetries )
            {
              v111 = *(_BYTE **)(v115 + 24);
              break;
            }
            continue;
          }
          v119 = v116 + 56;
        }
        else
        {
          v119 = v116 + 40;
        }
        if ( v119 <= QosMaxNumberOfTimeoutRetries )
        {
          v111 = *(_BYTE **)(v115 + 16);
          break;
        }
      }
    }
  }
  v120 = 0;
  if ( !*(_DWORD *)(v109 + 20) )
  {
    v121 = *(_DWORD *)(v109 + 56);
    if ( v121 )
    {
      v122 = 0;
      while ( 1 )
      {
        v123 = *(unsigned int *)(v109 + 4LL * v122 + 120);
        if ( (unsigned int)v123 < 0x80 )
          goto LABEL_234;
        QosMaxNumberOfTimeoutRetries = *(unsigned int *)(v109 + 16);
        if ( (unsigned int)v123 >= (unsigned int)QosMaxNumberOfTimeoutRetries )
          goto LABEL_234;
        v124 = v109 + v123;
        v125 = (unsigned int)v123;
        v126 = *(_DWORD *)(v109 + v123) - 64;
        if ( !v126 )
          goto LABEL_232;
        v127 = v126 - 1;
        if ( v127 )
          break;
        v128 = v125 + 56;
LABEL_233:
        if ( v128 <= QosMaxNumberOfTimeoutRetries )
        {
          v120 = *(_BYTE *)(v124 + 9);
          goto LABEL_239;
        }
LABEL_234:
        if ( ++v122 >= v121 )
          goto LABEL_239;
      }
      if ( v127 != 1 )
        goto LABEL_234;
LABEL_232:
      v128 = v125 + 40;
      goto LABEL_233;
    }
  }
LABEL_239:
  v223 = 0;
  if ( !v111 )
    goto LABEL_258;
  if ( !v120 )
    goto LABEL_258;
  v129 = *v111 & 0x7F;
  if ( (unsigned __int8)(v129 - 112) > 3u )
    goto LABEL_258;
  v130 = v111 + 8;
  v131 = 0;
  v132 = 0;
  if ( (unsigned __int8)(v129 - 114) <= 1u )
  {
    if ( v130 <= &v111[v120] )
    {
      v132 = v111[2];
      v131 = v111[1] & 0xF;
      v110 = v111[3];
LABEL_252:
      v136 = 1;
      goto LABEL_254;
    }
  }
  else if ( v130 <= &v111[v120] )
  {
    v133 = v111 + 13;
    v131 = v111[2] & 0xF;
    v134 = v120;
    if ( (unsigned int)(unsigned __int8)v111[7] + 8 <= v120 )
      v134 = (unsigned __int8)v111[7] + 8;
    v135 = (unsigned __int64)&v111[v134];
    if ( (unsigned __int64)v133 <= v135 )
      v132 = v111[12];
    if ( (unsigned __int64)(v111 + 14) <= v135 )
    {
      v110 = *v133;
      v136 = 1;
      goto LABEL_254;
    }
    goto LABEL_252;
  }
  v136 = 0;
LABEL_254:
  if ( v136 )
  {
    v137 = *(_QWORD *)(a3 + 48);
    LOBYTE(v223) = 1;
    BYTE1(v223) = v131;
    BYTE2(v223) = v132;
    HIBYTE(v223) = v110;
    if ( v99 )
      *(_DWORD *)(v137 + 136) = v223;
    else
      _InterlockedExchange((volatile __int32 *)(v137 + 136), ((v131 | ((v132 | (v110 << 8)) << 8)) << 8) | 1);
    goto LABEL_259;
  }
LABEL_258:
  v110 = HIBYTE(v223);
  v132 = BYTE2(v223);
  v131 = BYTE1(v223);
LABEL_259:
  v138 = *(_QWORD *)(a3 + 288);
  if ( *(_BYTE *)(v138 + 2) != 40 )
  {
    v139 = (char *)(v138 + 72);
    goto LABEL_279;
  }
  v139 = 0;
  if ( !*(_DWORD *)(v138 + 20) )
  {
    v140 = *(_DWORD *)(v138 + 56);
    if ( v140 )
    {
      v141 = 0;
      do
      {
        v142 = *(unsigned int *)(v138 + 4 * v141 + 120);
        if ( (unsigned int)v142 < 0x80 )
          goto LABEL_274;
        v143 = *(unsigned int *)(v138 + 16);
        if ( (unsigned int)v142 >= (unsigned int)v143 )
          goto LABEL_274;
        v144 = v138 + v142;
        QosMaxNumberOfTimeoutRetries = (unsigned int)v142;
        v145 = *(_DWORD *)(v138 + v142) - 64;
        if ( v145 )
        {
          v146 = v145 - 1;
          if ( v146 )
          {
            if ( v146 == 1 && QosMaxNumberOfTimeoutRetries + 40 <= v143 )
            {
              if ( *(_DWORD *)(v144 + 12) )
                v139 = (char *)(v144 + 32);
              break;
            }
            goto LABEL_274;
          }
          v147 = QosMaxNumberOfTimeoutRetries + 56;
        }
        else
        {
          v147 = QosMaxNumberOfTimeoutRetries + 40;
        }
        if ( v147 <= v143 )
        {
          if ( *(_BYTE *)(v144 + 10) )
            v139 = (char *)(v144 + 24);
          break;
        }
LABEL_274:
        v141 = (unsigned int)(v141 + 1);
      }
      while ( (unsigned int)v141 < v140 );
    }
  }
LABEL_279:
  if ( v139 )
  {
    if ( (*((_BYTE *)&FdoExtension->CommonExtension + 104) & 1) != 0 )
    {
      v223 = 0;
      ClasspTransferPacketGetNumberOfRetriesDone(a3, v139, &v223);
      v148 = v223;
      if ( v223 )
      {
        v149 = TelemetryRetryLastResetTimestamp;
        UnbiasedInterruptTime = KeQueryUnbiasedInterruptTime();
        if ( UnbiasedInterruptTime - TelemetryRetryLastResetTimestamp > 0x861C46800LL
          && v149 == _InterlockedCompareExchange64(&TelemetryRetryLastResetTimestamp, UnbiasedInterruptTime, v149) )
        {
          TelemetryRetryCountSinceReset = 0;
        }
        if ( _InterlockedIncrement64(&TelemetryRetryCountSinceReset) <= 60 )
        {
          if ( (unsigned __int8)ClasspQosSupportedCommand((unsigned __int8)*v139) )
          {
            QosMaxNumberOfTimeoutRetries = v238->QosMaxNumberOfTimeoutRetries;
            LOBYTE(QosMaxNumberOfTimeoutRetries) = QosMaxNumberOfTimeoutRetries - *(_BYTE *)(a3 + 59);
          }
          if ( (unsigned int)dword_14004D060 > 5
            && (qword_14004D070 & 0x400000000000LL) != 0
            && (qword_14004D078 & 0x400000000000LL) == qword_14004D078 )
          {
            v151 = *(_QWORD *)(a3 + 288);
            v249 = 16;
            v251 = 1;
            p_DeviceGuid = &FdoExtension->AdditionalFdoData->DeviceGuid;
            v227 = *v139;
            v250 = &v227;
            v152 = 40;
            if ( *(_BYTE *)(v151 + 2) != 40 )
              v152 = 20;
            LODWORD(v226) = *(_DWORD *)(v152 + v151);
            v252 = &v226;
            v254 = &v228;
            v256 = &v229;
            v229 = QosMaxNumberOfTimeoutRetries;
            v253 = 4;
            v228 = v148;
            v255 = 1;
            v257 = 1;
            v153 = *(_BYTE *)(v151 + 3);
            EventDescriptor.Keyword = 0x400000000000LL;
            v230 = v153 & 0x3F;
            v259 = 1;
            v258 = &v230;
            v260 = (char *)&v231;
            v262 = (char *)&v232;
            v264 = (char *)&v233;
            *(_DWORD *)&EventDescriptor.Level = 5;
            UserData.Ptr = (unsigned __int64)EventInformation;
            v231 = v131;
            v261 = 1;
            v232 = v132;
            v263 = 1;
            v233 = v110;
            v265 = 1;
            *(_DWORD *)&EventDescriptor.Id = 184549376;
            UserData.Size = *(unsigned __int16 *)EventInformation;
            v245 = &byte_14004898F;
            UserData.Reserved = 2;
            v246 = 188;
            v247 = 1;
            v223 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
            EtwWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 0xBu, &UserData);
          }
        }
      }
    }
  }
  v154 = FdoExtension;
  if ( (unsigned __int8)PORT_ALLOCATED_SENSE_EX(FdoExtension, *(_QWORD *)(a3 + 288), QosMaxNumberOfTimeoutRetries) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_f06639bbdb9b35d83c2ad903c5194624_Traceguids, a3);
    }
    FREE_PORT_ALLOCATED_SENSE_BUFFER_EX(v154);
    v155 = *(_QWORD *)(a3 + 288);
    v156 = a3 + 264;
    if ( *(_BYTE *)(v155 + 2) == 40 )
    {
      if ( !*(_DWORD *)(v155 + 20) )
      {
        v157 = *(_DWORD *)(v155 + 56);
        for ( k = 0; (unsigned int)k < v157; k = (unsigned int)(k + 1) )
        {
          v159 = *(unsigned int *)(v155 + 4 * k + 120);
          if ( (unsigned int)v159 < 0x80 )
            continue;
          v160 = *(unsigned int *)(v155 + 16);
          if ( (unsigned int)v159 >= (unsigned int)v160 )
            continue;
          v161 = v159 + v155;
          v162 = (unsigned int)v159;
          v163 = *(_DWORD *)(v159 + v155) - 64;
          if ( v163 )
          {
            v164 = v163 - 1;
            if ( v164 )
            {
              if ( v164 == 1 && v162 + 40 <= v160 )
              {
                *(_QWORD *)(v161 + 24) = v156;
                break;
              }
              continue;
            }
            v165 = v162 + 56;
          }
          else
          {
            v165 = v162 + 40;
          }
          if ( v165 <= v160 )
          {
            *(_QWORD *)(v161 + 16) = v156;
            break;
          }
        }
      }
    }
    else
    {
      *(_QWORD *)(v155 + 32) = v156;
    }
    v166 = *(_QWORD *)(a3 + 288);
    if ( *(_BYTE *)(v166 + 2) != 40 )
    {
      *(_BYTE *)(v166 + 11) = 18;
      goto LABEL_331;
    }
    if ( !*(_DWORD *)(v166 + 20) )
    {
      v167 = *(_DWORD *)(v166 + 56);
      v168 = 0;
      if ( v167 )
      {
        while ( 1 )
        {
          v169 = *(unsigned int *)(v166 + 4 * v168 + 120);
          if ( (unsigned int)v169 < 0x80 )
            goto LABEL_326;
          v170 = *(unsigned int *)(v166 + 16);
          if ( (unsigned int)v169 >= (unsigned int)v170 )
            goto LABEL_326;
          v171 = v166 + v169;
          v172 = (unsigned int)v169;
          v173 = *(_DWORD *)(v166 + v169) - 64;
          if ( !v173 )
            goto LABEL_324;
          v174 = v173 - 1;
          if ( v174 )
            break;
          v175 = v172 + 56;
LABEL_325:
          if ( v175 <= v170 )
          {
            *(_BYTE *)(v171 + 9) = 18;
            goto LABEL_331;
          }
LABEL_326:
          v168 = (unsigned int)(v168 + 1);
          if ( (unsigned int)v168 >= v167 )
            goto LABEL_331;
        }
        if ( v174 != 1 )
          goto LABEL_326;
LABEL_324:
        v175 = v172 + 40;
        goto LABEL_325;
      }
    }
  }
LABEL_331:
  v176 = v237;
  *(_OWORD *)(a3 + 264) = 0;
  *(_WORD *)(a3 + 280) = 0;
  IoSetMasterIrpStatus(*(_QWORD *)(a3 + 48), *(unsigned int *)(v176 + 48));
  v177 = *(_DWORD *)(v176 + 48);
  if ( (unsigned int)(v177 + 1073741662) <= 1
    || v177 == -1073741643
    || (unsigned int)(v177 + 1073741806) <= 2
    || v177 == -2147483626 )
  {
    v178 = v234;
    v179 = (struct _DEVICE_OBJECT *)QpcTimeStamp;
    if ( *v234 )
    {
      v180 = *(IRP **)(a3 + 48);
      if ( v180->Tail.Overlay.Thread )
        IoSetHardErrorOrVerifyDevice(v180, (PDEVICE_OBJECT)QpcTimeStamp);
    }
  }
  else
  {
    v178 = v234;
    v179 = (struct _DEVICE_OBJECT *)QpcTimeStamp;
  }
  v181 = v224;
  v182 = *(_QWORD *)(a3 + 48);
  if ( v224 )
  {
    --*(_DWORD *)(v182 + 120);
  }
  else if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v182 + 120), 0xFFFFFFFF) > 1 )
  {
    goto LABEL_390;
  }
  if ( *v178 )
  {
    v183 = *(IRP **)(a3 + 48);
    if ( (v183->Flags & 2) != 0 )
      PagingIoPriority = IoGetPagingIoPriority(v183);
    else
      PagingIoPriority = IoPagingPriorityInvalid;
    v185 = *(_QWORD *)(a3 + 48);
    if ( *(int *)(v185 + 48) >= 0 )
    {
      ClasspPerfIncrementSuccessfulIo(v154);
      v185 = *(_QWORD *)(a3 + 48);
    }
    if ( !v181 )
    {
      ClassReleaseRemoveLock(v179, (PVOID)v185);
      v185 = *(_QWORD *)(a3 + 48);
    }
    if ( *(_BYTE *)(*(_QWORD *)(a3 + 32) + 65LL) )
      *(_BYTE *)(*(_QWORD *)(v185 + 184) + 3LL) |= 1u;
    v186 = *(_BYTE **)(a3 + 48);
    if ( (v186[136] & 1) != 0 )
    {
      v187 = v186[137];
      v188 = (unsigned __int8)v186[138];
      v189 = v186[139];
      v190 = *(_QWORD *)(a3 + 48);
      v223 = 0;
      GenericIrpExtension = IoGetGenericIrpExtension(v190, &v223, 4);
      if ( (int)(GenericIrpExtension + 0x80000000) < 0 || GenericIrpExtension == -1073741275 )
      {
        v192 = v187 & 0xF;
        v193 = 0;
        if ( &v240 <= v242 )
          v193 = v188;
        v194 = 0;
        BYTE2(v223) = v193;
        LOBYTE(v193) = 1;
        if ( &v241 <= v242 )
          v194 = v189;
        HIBYTE(v223) = v194;
        BYTE1(v223) = BYTE1(v223) & 3 | (16 * v192) | 8;
        IoSetGenericIrpExtension(v186, &v223, 4, v193);
      }
      v154 = FdoExtension;
    }
    ClassCompleteRequest(v179, *(PIRP *)(a3 + 48), 1);
    if ( PagingIoPriority == IoPagingPriorityHigh )
    {
      v195 = v238;
      v196 = KeAcquireSpinLockRaiseToDpc(&v238->SpinLock);
      MaxInterleavedNormalIo = v195->MaxInterleavedNormalIo;
      v198 = 0;
      v199 = v196;
      if ( MaxInterleavedNormalIo >= 4 )
        v198 = MaxInterleavedNormalIo - 4;
      v11 = v195->NumHighPriorityPagingIo-- == 1;
      v195->MaxInterleavedNormalIo = v198;
      if ( v11 )
      {
        v200 = MEMORY[0xFFFFF78000000014];
        LongestThrottlePeriod = v195->LongestThrottlePeriod;
        v195->ThrottleStopTime.QuadPart = MEMORY[0xFFFFF78000000014];
        v202.QuadPart = v200 - v195->ThrottleStartTime.QuadPart;
        if ( LongestThrottlePeriod.QuadPart <= v202.QuadPart )
          LongestThrottlePeriod = v202;
        v195->LongestThrottlePeriod = LongestThrottlePeriod;
      }
      KeReleaseSpinLock(&v195->SpinLock, v199);
    }
    if ( v225 )
    {
      v203 = v154->PrivateFdoData;
      if ( v203->IdleIoCount )
      {
        if ( v203->ActiveIdleIoCount < v203->IdleActiveIoMax
          && (int)ClasspGetActiveIoCount(v154->PrivateFdoData) <= 0
          && (unsigned int)ClasspIdleDurationSufficient(v203, 0) )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80u) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_dee7c8ca8cd5355db7ab7a1f63361bba_Traceguids);
          }
          v204 = ClasspDequeueIdleRequest(v154);
          if ( v204 )
            ServiceTransferRequest((__int64)v154->DeviceObject, v204, 1);
        }
      }
    }
    if ( v154->CommonExtension.DriverExtension->InitData.ClassStartIo )
    {
      v205 = *(_QWORD *)(a3 + 288);
      v206 = 24;
      if ( *(_BYTE *)(v205 + 2) != 40 )
        v206 = 12;
      if ( (*(_DWORD *)(v206 + v205) & 0x800000) != 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_f06639bbdb9b35d83c2ad903c5194624_Traceguids);
        }
      }
      else
      {
        v207 = KfRaiseIrql(2u);
        IoStartNextPacket(v179, 1u);
        KeLowerIrql(v207);
      }
    }
  }
LABEL_390:
  v208 = *(struct _KEVENT **)(a3 + 200);
  if ( v208 )
  {
    KeSetEvent(v208, 0, 0);
    *(_QWORD *)(a3 + 200) = 0;
  }
  v209 = *(void (__fastcall **)(_QWORD))(a3 + 344);
  if ( v209 )
  {
    v209(*(_QWORD *)(a3 + 352));
    *(_QWORD *)(a3 + 344) = 0;
  }
  *(_BYTE *)(a3 + 296) = 0;
  *(_BYTE *)(a3 + 209) = 0;
  EnqueueFreeTransferPacket(v179, a3);
  DeviceExtension = v179->DeviceExtension;
  v211 = DeviceExtension[143];
  if ( (*(_DWORD *)(v211 + 664) & 4) != 0 )
  {
    v212 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v211 + 1560));
    v213 = (_QWORD *)(v211 + 1544);
    v214 = v212;
    v215 = *(_QWORD **)(v211 + 1544);
    if ( v215 == (_QWORD *)(v211 + 1544) )
    {
      KeReleaseSpinLock((PKSPIN_LOCK)(v211 + 1560), v212);
    }
    else
    {
      if ( (_QWORD *)v215[1] != v213 || (v220 = *v215, *(_QWORD **)(*v215 + 8LL) != v215) )
        __fastfail(3u);
      *v213 = v220;
      *(_QWORD *)(v220 + 8) = v213;
      if ( (_QWORD *)*v213 == v213 )
        _InterlockedAnd((volatile signed __int32 *)(v211 + 664), 0xFFFFFFFB);
      KeReleaseSpinLock((PKSPIN_LOCK)(v211 + 1560), v214);
      if ( v215 )
      {
        if ( ClassPnPETWEnabled )
        {
          EventDescriptor = 0;
          IoGetActivityIdIrp(v215 - 21, &EventDescriptor);
          if ( (BYTE2(WPP_MAIN_CB.Queue.Wcb.CurrentIrp) & 0x40) != 0 )
            McTemplateK0qdud_EtwWriteTransfer(
              v222,
              v221,
              (unsigned int)&EventDescriptor,
              *((_DWORD *)DeviceExtension + 147),
              2,
              5);
        }
        ClasspRecordIoAttributionForQueueTime(v215 - 21, 0, 0);
        v215[1] = v215;
        *v215 = v215;
        if ( v215 != (_QWORD *)168 )
          ServiceTransferRequest((__int64)v179, (__int64)(v215 - 21), 1);
      }
    }
  }
  v216 = (_DWORD **)v179->DeviceExtension;
  v217 = *v216[55];
  if ( v217 )
  {
    while ( 1 )
    {
      v218 = v217;
      v217 = _InterlockedCompareExchange(v216[55], v217 - 1, v217);
      if ( v218 == v217 )
        break;
      if ( !v217 )
        goto LABEL_400;
    }
  }
  else
  {
LABEL_400:
    ExReleaseRundownProtectionCacheAware((PEX_RUNDOWN_REF_CACHE_AWARE)(v216[55] + 2));
  }
  return 3221225494LL;
}

```

## disassembly

```asm
0x14001ccb0  mov     [rsp-8+arg_0], rbx
0x14001ccb5  push    rbp
0x14001ccb6  push    rsi
0x14001ccb7  push    rdi
0x14001ccb8  push    r12
0x14001ccba  push    r13
0x14001ccbc  push    r14
0x14001ccbe  push    r15
0x14001ccc0  lea     rbp, [rsp-80h]
0x14001ccc5  sub     rsp, 180h
0x14001cccc  mov     rax, cs:__security_cookie
0x14001ccd3  xor     rax, rsp
0x14001ccd6  mov     [rbp+0B0h+var_40], rax
0x14001ccda  mov     rax, [r8+28h]
0x14001ccde  xor     r14d, r14d
0x14001cce1  xor     r12b, r12b
0x14001cce4  mov     [rbp+0B0h+var_130], rdx
0x14001cce8  mov     rdi, r8
0x14001cceb  mov     [rsp+1B0h+var_15B], 0
0x14001ccf0  mov     r13d, r14d
0x14001ccf3  mov     [rsp+1B0h+var_148], r14
0x14001ccf8  mov     rax, [rax+40h]
0x14001ccfc  mov     [rsp+1B0h+FdoExtension], rax
0x14001cd01  mov     r15, [rax+478h]
0x14001cd08  mov     [rbp+0B0h+var_128], r15
0x14001cd0c  mov     [rbp+0B0h+var_120], r14
0x14001cd10  cmp     [r8+138h], r14
0x14001cd17  jz      short loc_14001CD21
0x14001cd19  mov     rcx, r8
0x14001cd1c  call    HistoryLogReturnedPacket
0x14001cd21  cmp     cs:ClassPnPPerfSensitiveEtwEventsEnabled, r12b
0x14001cd28  jnz     short loc_14001CD37
0x14001cd2a  cmp     [r15+2B8h], r14
0x14001cd31  jz      loc_14001D0B3
0x14001cd37  mov     rbx, [rdi+140h]
0x14001cd3e  test    rbx, rbx
0x14001cd41  jz      loc_14001D0B3
0x14001cd47  lea     rcx, [rsp+1B0h+QpcTimeStamp]; QpcTimeStamp
0x14001cd4c  mov     [rsp+1B0h+QpcTimeStamp], r14
0x14001cd51  call    cs:__imp_KeQueryUnbiasedInterruptTimePrecise
0x14001cd58  nop     dword ptr [rax+rax+00h]
0x14001cd5d  mov     rdx, rax
0x14001cd60  sub     rdx, rbx
0x14001cd63  cmp     rax, rbx
0x14001cd66  lea     rcx, [rdx-1]
0x14001cd6a  cmovnb  rcx, rdx
0x14001cd6e  cmp     cs:ClassPnPPerfSensitiveEtwEventsEnabled, r12b
0x14001cd75  mov     [rsp+1B0h+QpcTimeStamp], rcx
0x14001cd7a  mov     [rdi+170h], rcx
0x14001cd81  jz      short loc_14001CD8B
0x14001cd83  mov     rcx, rdi
0x14001cd86  call    ClasspWriteIOPerformanceMeasurementEvent
0x14001cd8b  mov     rax, [r15+2B8h]
0x14001cd92  test    rax, rax
0x14001cd95  jz      loc_14001D0B3
0x14001cd9b  cmp     [rdi+170h], rax
0x14001cda2  jle     loc_14001D0B3
0x14001cda8  cmp     [rdi+178h], r12b
0x14001cdaf  jnz     loc_14001D0B3
0x14001cdb5  mov     r9, [rdi+120h]
0x14001cdbc  cmp     byte ptr [r9+2], 28h ; '('
0x14001cdc1  jnz     loc_14001CFA5
0x14001cdc7  cmp     [r9+14h], r13d
0x14001cdcb  jnz     short loc_14001CE49
0x14001cdcd  mov     ebx, [r9+38h]
0x14001cdd1  test    ebx, ebx
0x14001cdd3  jz      short loc_14001CE49
0x14001cdd5  mov     r11d, r14d
0x14001cdd8  nop     dword ptr [rax+rax+00000000h]
0x14001cde0  mov     eax, r11d
0x14001cde3  mov     ecx, [r9+rax*4+78h]
0x14001cde8  cmp     ecx, 80h
0x14001cdee  jb      short loc_14001CE35
0x14001cdf0  mov     edx, [r9+10h]
0x14001cdf4  cmp     ecx, edx
0x14001cdf6  jnb     short loc_14001CE35
0x14001cdf8  lea     r10, [rcx+r9]
0x14001cdfc  mov     r8d, ecx
0x14001cdff  mov     ecx, [r10]
0x14001ce02  sub     ecx, 40h ; '@'
0x14001ce05  jz      short loc_14001CE2C
0x14001ce07  sub     ecx, 1
0x14001ce0a  jz      short loc_14001CE26
0x14001ce0c  cmp     ecx, 1
0x14001ce0f  jnz     short loc_14001CE35
0x14001ce11  lea     rcx, [r8+28h]
0x14001ce15  cmp     rcx, rdx
0x14001ce18  ja      short loc_14001CE35
0x14001ce1a  cmp     [r10+0Ch], r13d
0x14001ce1e  jbe     short loc_14001CE49
0x14001ce20  lea     r13, [r10+20h]
0x14001ce24  jmp     short loc_14001CE49
0x14001ce26  lea     rcx, [r8+38h]
0x14001ce2a  jmp     short loc_14001CE30
0x14001ce2c  lea     rcx, [r8+28h]
0x14001ce30  cmp     rcx, rdx
0x14001ce33  jbe     short loc_14001CE3F
0x14001ce35  inc     r11d
0x14001ce38  cmp     r11d, ebx
0x14001ce3b  jb      short loc_14001CDE0
0x14001ce3d  jmp     short loc_14001CE49
0x14001ce3f  cmp     [r10+0Ah], r12b
0x14001ce43  jbe     short loc_14001CE49
0x14001ce45  lea     r13, [r10+18h]
0x14001ce49  xor     sil, sil
0x14001ce4c  cmp     [r9+14h], r14d
0x14001ce50  jnz     short loc_14001CEBA
0x14001ce52  mov     ebx, [r9+38h]
0x14001ce56  test    ebx, ebx
0x14001ce58  jz      short loc_14001CEBA
0x14001ce5a  mov     r10d, r14d
0x14001ce5d  nop     dword ptr [rax]
0x14001ce60  mov     eax, r10d
0x14001ce63  mov     ecx, [r9+rax*4+78h]
0x14001ce68  cmp     ecx, 80h
0x14001ce6e  jb      short loc_14001CEAB
0x14001ce70  mov     edx, [r9+10h]
0x14001ce74  cmp     ecx, edx
0x14001ce76  jnb     short loc_14001CEAB
0x14001ce78  lea     r11, [rcx+r9]
0x14001ce7c  mov     r8d, ecx
0x14001ce7f  mov     ecx, [r11]
0x14001ce82  sub     ecx, 40h ; '@'
0x14001ce85  jz      short loc_14001CEA2
0x14001ce87  sub     ecx, 1
0x14001ce8a  jz      short loc_14001CE9C
0x14001ce8c  cmp     ecx, 1
0x14001ce8f  jnz     short loc_14001CEAB
0x14001ce91  lea     rcx, [r8+28h]
0x14001ce95  cmp     rcx, rdx
0x14001ce98  jbe     short loc_14001CEBA
0x14001ce9a  jmp     short loc_14001CEAB
0x14001ce9c  lea     rcx, [r8+38h]
0x14001cea0  jmp     short loc_14001CEA6
0x14001cea2  lea     rcx, [r8+28h]
0x14001cea6  cmp     rcx, rdx
0x14001cea9  jbe     short loc_14001CEB5
0x14001ceab  inc     r10d
0x14001ceae  cmp     r10d, ebx
0x14001ceb1  jb      short loc_14001CE60
0x14001ceb3  jmp     short loc_14001CEBA
0x14001ceb5  movzx   esi, byte ptr [r11+0Ah]
0x14001ceba  mov     r15, r14
0x14001cebd  movzx   r12d, sil
0x14001cec1  cmp     [r9+14h], r14d
0x14001cec5  jnz     loc_14001CFA1
0x14001cecb  mov     ebx, [r9+38h]
0x14001cecf  test    ebx, ebx
0x14001ced1  jz      short loc_14001CF3D
0x14001ced3  mov     r10d, r14d
0x14001ced6  nop     word ptr [rax+rax+00000000h]
0x14001cee0  mov     eax, r10d
0x14001cee3  mov     ecx, [r9+rax*4+78h]
0x14001cee8  cmp     ecx, 80h
0x14001ceee  jb      short loc_14001CF2F
0x14001cef0  mov     edx, [r9+10h]
0x14001cef4  cmp     ecx, edx
0x14001cef6  jnb     short loc_14001CF2F
0x14001cef8  lea     r11, [rcx+r9]
0x14001cefc  mov     r8d, ecx
0x14001ceff  mov     ecx, [r11]
0x14001cf02  sub     ecx, 40h ; '@'
0x14001cf05  jz      short loc_14001CF26
0x14001cf07  sub     ecx, 1
0x14001cf0a  jz      short loc_14001CF20
0x14001cf0c  cmp     ecx, 1
0x14001cf0f  jnz     short loc_14001CF2F
0x14001cf11  lea     rcx, [r8+28h]
0x14001cf15  cmp     rcx, rdx
0x14001cf18  ja      short loc_14001CF2F
0x14001cf1a  mov     r15, [r11+18h]
0x14001cf1e  jmp     short loc_14001CF3D
0x14001cf20  lea     rcx, [r8+38h]
0x14001cf24  jmp     short loc_14001CF2A
0x14001cf26  lea     rcx, [r8+28h]
0x14001cf2a  cmp     rcx, rdx
0x14001cf2d  jbe     short loc_14001CF39
0x14001cf2f  inc     r10d
0x14001cf32  cmp     r10d, ebx
0x14001cf35  jb      short loc_14001CEE0
0x14001cf37  jmp     short loc_14001CF3D
0x14001cf39  mov     r15, [r11+10h]
0x14001cf3d  mov     esi, ebx
0x14001cf3f  test    ebx, ebx
0x14001cf41  jz      short loc_14001CFA1
0x14001cf43  mov     r10d, r14d
0x14001cf46  xor     bl, bl
0x14001cf48  nop     dword ptr [rax+rax+00000000h]
0x14001cf50  mov     eax, r10d
0x14001cf53  mov     ecx, [r9+rax*4+78h]
0x14001cf58  cmp     ecx, 80h
0x14001cf5e  jb      short loc_14001CF8A
0x14001cf60  mov     edx, [r9+10h]
0x14001cf64  cmp     ecx, edx
0x14001cf66  jnb     short loc_14001CF8A
0x14001cf68  lea     r11, [rcx+r9]
0x14001cf6c  mov     r8d, ecx
0x14001cf6f  mov     ecx, [r11]
0x14001cf72  sub     ecx, 40h ; '@'
0x14001cf75  jz      short loc_14001CF81
0x14001cf77  sub     ecx, 1
0x14001cf7a  jz      short loc_14001CF94
0x14001cf7c  cmp     ecx, 1
0x14001cf7f  jnz     short loc_14001CF8A
0x14001cf81  lea     rcx, [r8+28h]
0x14001cf85  cmp     rcx, rdx
0x14001cf88  jbe     short loc_14001CF9A
0x14001cf8a  inc     r10d
0x14001cf8d  cmp     r10d, esi
0x14001cf90  jb      short loc_14001CF50
0x14001cf92  jmp     short loc_14001CFB7
0x14001cf94  lea     rcx, [r8+38h]
0x14001cf98  jmp     short loc_14001CF85
0x14001cf9a  movzx   ebx, byte ptr [r11+9]
0x14001cf9f  jmp     short loc_14001CFB7
0x14001cfa1  xor     bl, bl
0x14001cfa3  jmp     short loc_14001CFB7
0x14001cfa5  mov     r15, [r9+20h]
0x14001cfa9  lea     r13, [r9+48h]
0x14001cfad  movzx   ebx, byte ptr [r9+0Bh]
0x14001cfb2  movzx   r12d, byte ptr [r9+0Ah]
0x14001cfb7  test    r15, r15
0x14001cfba  jz      short loc_14001CFF7
0x14001cfbc  test    bl, bl
0x14001cfbe  jz      short loc_14001CFF7
0x14001cfc0  movzx   ecx, bl
0x14001cfc3  lea     rax, [r15+8]
0x14001cfc7  add     rcx, r15
0x14001cfca  xor     dl, dl
0x14001cfcc  xor     r8b, r8b
0x14001cfcf  cmp     rax, rcx
0x14001cfd2  ja      short loc_14001CFE3
0x14001cfd4  movzx   eax, byte ptr [r15+7]
0x14001cfd9  cmp     al, 0F7h
0x14001cfdb  ja      short loc_14001CFE3
0x14001cfdd  lea     edx, [rax+8]
0x14001cfe0  mov     r8b, 1
0x14001cfe3  test    r8b, r8b
0x14001cfe6  jz      short loc_14001CFF7
0x14001cfe8  cmp     dl, bl
0x14001cfea  movzx   r14d, bl
0x14001cfee  movzx   eax, dl
0x14001cff1  cmovb   r14d, eax
0x14001cff5  jmp     short loc_14001CFFB
0x14001cff7  movzx   r14d, bl
0x14001cffb  mov     byte ptr [rdi+178h], 1
0x14001d002  cmp     byte ptr [r9+2], 28h ; '('
0x14001d007  jnz     short loc_14001D06E
0x14001d009  xor     bl, bl
0x14001d00b  cmp     dword ptr [r9+14h], 0
0x14001d010  jnz     short loc_14001D073
0x14001d012  mov     esi, [r9+38h]
0x14001d016  test    esi, esi
0x14001d018  jz      short loc_14001D073
0x14001d01a  xor     r10d, r10d
0x14001d01d  nop     dword ptr [rax]
0x14001d020  mov     ecx, [r9+r10*4+78h]
0x14001d025  cmp     ecx, 80h
0x14001d02b  jb      short loc_14001D057
0x14001d02d  mov     edx, [r9+10h]
0x14001d031  cmp     ecx, edx
0x14001d033  jnb     short loc_14001D057
0x14001d035  lea     r11, [rcx+r9]
0x14001d039  mov     r8d, ecx
0x14001d03c  mov     ecx, [r11]
0x14001d03f  sub     ecx, 40h ; '@'
0x14001d042  jz      short loc_14001D04E
0x14001d044  sub     ecx, 1
0x14001d047  jz      short loc_14001D061
0x14001d049  cmp     ecx, 1
0x14001d04c  jnz     short loc_14001D057
0x14001d04e  lea     rcx, [r8+28h]
0x14001d052  cmp     rcx, rdx
0x14001d055  jbe     short loc_14001D067
0x14001d057  inc     r10d
0x14001d05a  cmp     r10d, esi
0x14001d05d  jb      short loc_14001D020
0x14001d05f  jmp     short loc_14001D073
0x14001d061  lea     rcx, [r8+38h]
0x14001d065  jmp     short loc_14001D052
0x14001d067  movzx   ebx, byte ptr [r11+8]
0x14001d06c  jmp     short loc_14001D073
0x14001d06e  movzx   ebx, byte ptr [r9+4]
0x14001d073  movzx   r9d, byte ptr [r9+3]
0x14001d078  mov     r8, r15
0x14001d07b  mov     rcx, [rdi+28h]; DeviceObject
0x14001d07f  and     r9b, 3Fh
0x14001d083  mov     [rsp+1B0h+var_170], rdi; __int64
0x14001d088  mov     [rsp+1B0h+var_178], r13; __int64
0x14001d08d  mov     [rsp+1B0h+var_180], r12d; int
0x14001d092  mov     [rsp+1B0h+Priority], 8004009Bh; int
0x14001d09a  movzx   edx, r14b; Size
0x14001d09e  mov     byte ptr [rsp+1B0h+BugCheckOnFailure], bl; char
0x14001d0a2  call    ClasspQueueLogIOEventWithContextWorker
0x14001d0a7  mov     r13, [rsp+1B0h+var_148]
0x14001d0ac  xor     r12b, r12b
0x14001d0af  mov     r15, [rbp+0B0h+var_128]
0x14001d0b3  mov     r10, [rdi+120h]
0x14001d0ba  mov     esi, 10h
0x14001d0bf  mov     r14d, 3Ch ; '<'
  ... truncated ...
```
