# ClassInterpretSenseInfo

- ea: `0x1400084b0`
- end: `0x14000bc9a`
- name: `ClassInterpretSenseInfo`
- size: `14314`
- prototype: `BOOLEAN __stdcall(PDEVICE_OBJECT DeviceObject, PSCSI_REQUEST_BLOCK Srb, UCHAR MajorFunctionCode, ULONG IoDeviceCode, ULONG RetryCount, NTSTATUS *Status, ULONG *RetryInterval)`
- caller_count: `4`
- callee_count: `28`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400077ac`
- `0x140008360`
- `0x140025340`
- `0x140025b80`

## callees

- `0x1400018a0`
- `0x140007680`
- `0x140007788`
- `0x1400084b0`
- `0x14000bca0`
- `0x14000be64`
- `0x140016d50`
- `0x140019020`
- `0x14001fbf4`
- `0x14001fc38`
- `0x14001feac`
- `0x14002001c`
- `0x140021710`
- `0x140021a20`
- `0x140021ba4`
- `0x140026dac`
- `0x140026ebc`
- `0x140027254`
- `0x1400272c0`
- `0x14002bdd0`
- `0x14002bebc`
- `0x14002bfa8`
- `0x14002c094`
- `0x140031898`
- `0x14003e430`
- `0x14003e470`
- `0x14003e640`
- `0x14003e940`

## import_xrefs

- `ntoskrnl!IoWriteErrorLogEntry` at `0x14000bc50`
- `ntoskrnl!IoWriteErrorLogEntry` at `0x14000bc50`
- `ntoskrnl!IoAllocateErrorLogEntry` at `0x14000bbbf`
- `ntoskrnl!IoAllocateErrorLogEntry` at `0x14000bbbf`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000b92b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000b92b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b9ac`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b9ac`
- `ntoskrnl!IoInvalidateDeviceRelations` at `0x14000ac71`
- `ntoskrnl!IoInvalidateDeviceRelations` at `0x14000ac71`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
BOOLEAN __stdcall ClassInterpretSenseInfo(
        PDEVICE_OBJECT DeviceObject,
        PSCSI_REQUEST_BLOCK Srb,
        UCHAR MajorFunctionCode,
        ULONG IoDeviceCode,
        ULONG RetryCount,
        NTSTATUS *Status,
        ULONG *RetryInterval)
{
  unsigned __int8 Function; // bl
  unsigned int *p_TimeOutValue; // rdi
  NTSTATUS *v9; // r14
  void **p_SrbExtension; // rsi
  _BYTE *SenseInfoBuffer; // r13
  unsigned int v13; // r11d
  __int64 v14; // r9
  char v15; // r10
  __int64 v16; // rcx
  __int64 v17; // rdx
  int v18; // ecx
  int v19; // ecx
  unsigned int SrbExtension; // r11d
  __int64 v21; // r9
  char v22; // r10
  __int64 v23; // rcx
  __int64 v24; // rdx
  int v25; // ecx
  int v26; // ecx
  void **p_SenseInfoBuffer; // r15
  unsigned __int8 *Cdb; // r15
  unsigned __int8 CdbLength; // r8
  unsigned int v30; // r11d
  __int64 v31; // r10
  char v32; // bl
  __int64 v33; // rcx
  unsigned __int64 DataTransferLength; // r9
  __int64 v35; // rdx
  int v36; // ecx
  int v37; // ecx
  __int64 v38; // rax
  unsigned __int8 v39; // dl
  signed __int8 SrbStatus; // di
  int v41; // ecx
  int v42; // r9d
  int v43; // r10d
  __int64 v44; // rbx
  __int64 v45; // r9
  bool v46; // zf
  bool v47; // si
  _DEVICE_OBJECT *v48; // rdi
  _SCSI_REQUEST_BLOCK *v49; // rdx
  unsigned __int8 v50; // di
  unsigned __int8 *v51; // r9
  __int64 v52; // r10
  char v53; // r11
  __int64 v54; // rcx
  unsigned __int64 v55; // r8
  __int64 v56; // rdx
  int v57; // ecx
  int v58; // ecx
  void **p_DataBuffer; // r9
  unsigned __int64 v60; // rdx
  unsigned __int8 ScsiStatus; // r8
  __int64 v62; // r10
  char v63; // r11
  __int64 v64; // rcx
  unsigned __int64 v65; // r9
  __int64 v66; // rdx
  int v67; // ecx
  int v68; // ecx
  int v69; // ebx
  _BYTE *v70; // rbx
  unsigned __int8 v71; // r13
  char v72; // al
  unsigned __int8 v73; // r15
  unsigned __int8 v74; // di
  unsigned int *v75; // rcx
  unsigned __int8 SenseInfoBufferLength; // r8
  __int64 v77; // r10
  char v78; // r11
  __int64 v79; // rcx
  unsigned __int64 v80; // r9
  int v81; // ecx
  int v82; // ecx
  char v83; // cl
  unsigned int v84; // eax
  unsigned __int64 v85; // rcx
  unsigned __int8 v86; // al
  unsigned int v87; // ebx
  unsigned __int8 v88; // r8
  __int64 v89; // r10
  char v90; // r11
  __int64 v91; // rcx
  unsigned __int64 v92; // r9
  int v93; // ecx
  int v94; // ecx
  unsigned int v95; // eax
  unsigned __int64 v96; // rcx
  char v97; // si
  char v98; // al
  char v99; // r14
  bool v100; // si
  unsigned __int8 v101; // r9
  __int64 v102; // r10
  char v103; // r11
  __int64 v104; // rcx
  unsigned __int64 v105; // r8
  int v106; // ecx
  int v107; // ecx
  char *v108; // r8
  unsigned __int8 v109; // r11
  char v110; // cl
  unsigned __int8 v111; // al
  unsigned __int8 v112; // r11
  char v113; // bl
  char v114; // di
  char *v115; // r9
  __int64 i; // rcx
  char v117; // al
  unsigned __int8 v118; // cl
  char v119; // cl
  unsigned __int8 v120; // r10
  NTSTATUS *v121; // rdx
  char v122; // cl
  unsigned __int8 v123; // al
  _STORAGE_DEVICE_DESCRIPTOR *DeviceDescriptor; // rax
  unsigned __int8 v125; // si
  unsigned int *v126; // r10
  unsigned int *v127; // r11
  unsigned __int8 v128; // r8
  __int64 v129; // r10
  char v130; // r11
  __int64 v131; // rcx
  unsigned __int64 v132; // r9
  __int64 v133; // rdx
  int v134; // ecx
  int v135; // ecx
  unsigned __int8 v136; // dl
  char v137; // r9
  unsigned __int8 v138; // al
  unsigned __int8 v139; // di
  unsigned __int64 v140; // rbx
  unsigned __int8 v141; // di
  __int64 v142; // rcx
  __int64 v143; // rcx
  int v144; // ecx
  unsigned __int8 v145; // al
  unsigned int v146; // ebx
  char v147; // r10
  __int64 v148; // r9
  char v149; // r11
  __int64 v150; // rcx
  unsigned __int64 v151; // r8
  __int64 v152; // rdx
  int v153; // ecx
  int v154; // ecx
  __int64 v155; // rax
  PDEVICE_OBJECT v156; // r8
  PFUNCTIONAL_DEVICE_EXTENSION v157; // rsi
  volatile unsigned __int16 DeviceFlags; // ax
  __int64 v159; // rax
  PFUNCTIONAL_DEVICE_EXTENSION v160; // rbx
  __int64 v161; // rdx
  UCHAR Lun; // r10
  char *v163; // r8
  UCHAR TargetId; // r9
  char *v165; // r8
  UCHAR PathId; // r8
  char *v167; // rdx
  char v168; // cl
  int v169; // eax
  PDEVICE_OBJECT v170; // rsi
  __int64 v171; // rdx
  unsigned __int8 v172; // r10
  char v173; // cl
  char v174; // dl
  char v175; // r8
  UCHAR v176; // al
  unsigned __int8 v177; // cl
  unsigned __int8 v178; // dl
  UCHAR v179; // al
  int v180; // r9d
  PDEVICE_OBJECT v181; // rcx
  __int64 v182; // rdx
  PDEVICE_OBJECT v183; // rcx
  __int64 v184; // rdx
  int v185; // ecx
  int v186; // ecx
  int v187; // ecx
  int v188; // ecx
  int v189; // ecx
  int v190; // r9d
  struct _DEVICE_OBJECT *v191; // rsi
  PFUNCTIONAL_DEVICE_EXTENSION v192; // r14
  __int64 v193; // rdx
  PDEVICE_OBJECT v194; // rcx
  __int64 v195; // rdx
  PDEVICE_OBJECT v196; // rcx
  __int64 v197; // rdx
  unsigned __int8 v198; // al
  __int64 OriginalRequest_high; // rdx
  UCHAR v200; // r10
  char *v201; // r8
  UCHAR v202; // r9
  char *v203; // r8
  UCHAR v204; // r8
  char *v205; // rdx
  struct _DEVICE_OBJECT *v206; // rsi
  _VPB *Vpb; // rax
  int v208; // eax
  __int64 v209; // rcx
  unsigned __int8 v210; // al
  unsigned int v211; // ecx
  char v212; // al
  unsigned int v213; // ecx
  unsigned int v214; // ecx
  unsigned int v215; // ecx
  unsigned int v216; // ecx
  unsigned int v217; // ecx
  unsigned int v218; // ecx
  unsigned int v219; // ecx
  unsigned int *v220; // rsi
  unsigned __int8 v221; // di
  __int64 v222; // r10
  char v223; // r11
  __int64 v224; // rcx
  unsigned __int64 v225; // r9
  __int64 v226; // rdx
  int v227; // ecx
  int v228; // ecx
  unsigned __int8 v229; // r8
  __int64 v230; // r10
  char v231; // r11
  __int64 v232; // rcx
  unsigned __int64 v233; // r9
  __int64 v234; // rdx
  int v235; // ecx
  int v236; // ecx
  unsigned int v237; // ecx
  unsigned int v238; // ecx
  unsigned int v239; // ecx
  unsigned int v240; // ecx
  unsigned int v241; // ecx
  unsigned int v242; // ecx
  __int64 v243; // r8
  unsigned __int8 v244; // r9
  __int64 v245; // rcx
  unsigned int v246; // eax
  char v247; // r9
  __int64 v248; // r10
  int v249; // ebx
  unsigned __int8 v250; // al
  void **v251; // rbx
  char v252; // r11
  __int64 j; // r10
  __int64 v254; // rcx
  unsigned __int64 v255; // r8
  __int64 v256; // rdx
  int v257; // ecx
  int v258; // ecx
  unsigned __int8 v259; // bl
  __int64 v260; // rax
  unsigned int v261; // edi
  unsigned __int8 v262; // r14
  char v263; // si
  __int16 v264; // r15
  unsigned __int8 v265; // r8
  __int64 v266; // r10
  char v267; // r11
  __int64 v268; // rcx
  unsigned __int64 v269; // r9
  __int64 v270; // rdx
  int v271; // ecx
  int v272; // ecx
  char v273; // dl
  size_t v274; // rbx
  char v275; // r9
  char v276; // r11
  char v277; // r10
  char v278; // al
  char v279; // al
  unsigned __int8 v280; // dl
  char v281; // r9
  unsigned __int8 v282; // al
  unsigned int v283; // eax
  char v284; // cl
  int v285; // r8d
  __int128 v286; // xmm1
  __int128 v287; // xmm0
  __int128 v288; // xmm1
  __int128 v289; // xmm0
  __int128 *p_ExtraData; // rdx
  __int128 v291; // xmm6
  __int128 v292; // xmm7
  __int128 v293; // xmm8
  _CLASS_PRIVATE_FDO_DATA *v294; // rsi
  KIRQL v295; // al
  __int128 v296; // xmm0
  __int128 v297; // xmm1
  unsigned __int64 v298; // rcx
  __int128 v299; // xmm0
  __int128 v300; // xmm1
  __int128 v301; // xmm0
  char v302; // r14
  unsigned __int8 *v303; // r10
  __int64 v304; // r9
  char v305; // r11
  __int64 v306; // rcx
  unsigned __int64 v307; // r8
  __int64 v308; // rdx
  int v309; // ecx
  int v310; // ecx
  void **v311; // r10
  char v312; // r8
  __int64 v313; // r11
  char v314; // si
  __int64 v315; // rcx
  unsigned __int64 v316; // r9
  __int64 v317; // rdx
  int v318; // ecx
  int v319; // ecx
  _OWORD *ErrorLogEntry; // rax
  void *v321; // rbx
  __int128 v322; // xmm1
  __int128 v323; // xmm0
  __int128 v324; // xmm1
  __int128 v325; // xmm0
  __int128 v326; // xmm0
  __int128 v327; // xmm1
  __int128 v328; // xmm0
  __int16 v330; // [rsp+58h] [rbp-B0h] BYREF
  unsigned __int8 v331; // [rsp+5Ah] [rbp-AEh]
  unsigned __int8 v332; // [rsp+5Bh] [rbp-ADh]
  char v333; // [rsp+5Ch] [rbp-ACh]
  unsigned __int64 v334; // [rsp+60h] [rbp-A8h]
  __int64 v335; // [rsp+68h] [rbp-A0h]
  __int64 v336; // [rsp+70h] [rbp-98h]
  int v337; // [rsp+78h] [rbp-90h]
  char v338; // [rsp+7Ch] [rbp-8Ch]
  char v339; // [rsp+7Dh] [rbp-8Bh]
  PDEVICE_OBJECT DeviceObjecta; // [rsp+80h] [rbp-88h]
  unsigned int v341; // [rsp+88h] [rbp-80h]
  _BYTE *v342; // [rsp+90h] [rbp-78h]
  NTSTATUS *v343; // [rsp+98h] [rbp-70h]
  UCHAR Buffer[4]; // [rsp+A0h] [rbp-68h] BYREF
  unsigned __int8 v345; // [rsp+A4h] [rbp-64h]
  char v346; // [rsp+A8h] [rbp-60h]
  char v347; // [rsp+A9h] [rbp-5Fh]
  int v348; // [rsp+ACh] [rbp-5Ch]
  __int128 ExtraData; // [rsp+B0h] [rbp-58h] BYREF
  __int16 v350; // [rsp+C0h] [rbp-48h]
  unsigned int *v351; // [rsp+C8h] [rbp-40h]
  void **v352; // [rsp+D0h] [rbp-38h]
  PFUNCTIONAL_DEVICE_EXTENSION FdoExtension; // [rsp+D8h] [rbp-30h]
  UCHAR v354; // [rsp+E0h] [rbp-28h]
  _CLASS_PRIVATE_FDO_DATA *PrivateFdoData; // [rsp+E8h] [rbp-20h]
  int v356; // [rsp+F0h] [rbp-18h]
  ULONG v357; // [rsp+F4h] [rbp-14h]
  unsigned __int64 v358; // [rsp+F8h] [rbp-10h]
  ULONG *v359; // [rsp+100h] [rbp-8h]
  _OWORD v360[8]; // [rsp+108h] [rbp+0h] BYREF
  _OWORD v361[6]; // [rsp+188h] [rbp+80h] BYREF

  Function = Srb->Function;
  p_TimeOutValue = &Srb->TimeOutValue;
  v9 = Status;
  DeviceObjecta = DeviceObject;
  p_SrbExtension = &Srb->SrbExtension;
  v357 = IoDeviceCode;
  FdoExtension = (PFUNCTIONAL_DEVICE_EXTENSION)DeviceObject->DeviceExtension;
  v354 = MajorFunctionCode;
  v343 = Status;
  PrivateFdoData = FdoExtension->PrivateFdoData;
  v359 = RetryInterval;
  v351 = &Srb->TimeOutValue;
  v352 = &Srb->SrbExtension;
  if ( Function == 40 )
  {
    SenseInfoBuffer = 0;
    v342 = 0;
    if ( *p_TimeOutValue )
    {
      v352 = &Srb->SrbExtension;
    }
    else
    {
      v13 = *(_DWORD *)p_SrbExtension;
      if ( *(_DWORD *)p_SrbExtension )
      {
        v14 = 0;
        v15 = 0;
        do
        {
          v16 = *((unsigned int *)&Srb[1].SenseInfoBuffer + v14);
          if ( (unsigned int)v16 >= 0x80 )
          {
            *(_QWORD *)&MajorFunctionCode = Srb->DataTransferLength;
            if ( (unsigned int)v16 < MajorFunctionCode )
            {
              v17 = (unsigned int)v16;
              v18 = *(_DWORD *)((char *)&Srb->Length + v16) - 64;
              if ( v18 )
              {
                v19 = v18 - 1;
                if ( v19 )
                {
                  if ( v19 == 1 && (unsigned __int64)(v17 + 40) <= MajorFunctionCode )
                  {
                    SenseInfoBuffer = *(void **)((char *)&Srb->DataBuffer + v17);
                    goto LABEL_21;
                  }
                }
                else if ( (unsigned __int64)(v17 + 56) <= MajorFunctionCode )
                {
                  SenseInfoBuffer = *(_BYTE **)((char *)&Srb->DataTransferLength + v17);
                  v15 = 1;
                  v342 = SenseInfoBuffer;
                }
              }
              else if ( (unsigned __int64)(v17 + 40) <= MajorFunctionCode )
              {
                SenseInfoBuffer = *(_BYTE **)((char *)&Srb->DataTransferLength + v17);
                goto LABEL_21;
              }
              if ( v15 )
                break;
            }
          }
          v14 = (unsigned int)(v14 + 1);
        }
        while ( (unsigned int)v14 < v13 );
      }
    }
  }
  else
  {
    SenseInfoBuffer = Srb->SenseInfoBuffer;
    v351 = &Srb->TimeOutValue;
    v352 = &Srb->SrbExtension;
LABEL_21:
    v342 = SenseInfoBuffer;
  }
  HIBYTE(v330) = 1;
  v347 = 0;
  v333 = 1;
  v339 = 1;
  v358 = 0;
  v341 = 0;
  v348 = 0;
  if ( Function != 40 )
  {
    CdbLength = Srb->CdbLength;
    Cdb = Srb->Cdb;
    v332 = 0;
    goto LABEL_64;
  }
  v336 = 0;
  if ( *p_TimeOutValue || (SrbExtension = (unsigned int)Srb->SrbExtension) == 0 )
  {
    Cdb = 0;
    goto LABEL_42;
  }
  v21 = 0;
  v22 = 0;
  while ( 1 )
  {
    v23 = *((unsigned int *)&Srb[1].SenseInfoBuffer + v21);
    if ( (unsigned int)v23 >= 0x80 )
    {
      *(_QWORD *)&MajorFunctionCode = Srb->DataTransferLength;
      if ( (unsigned int)v23 < MajorFunctionCode )
        break;
    }
LABEL_40:
    v21 = (unsigned int)(v21 + 1);
    if ( (unsigned int)v21 >= SrbExtension )
      goto LABEL_41;
  }
  v24 = (unsigned int)v23;
  v25 = *(_DWORD *)((char *)&Srb->Length + v23) - 64;
  if ( v25 )
  {
    v26 = v25 - 1;
    if ( v26 )
    {
      if ( v26 == 1 && (unsigned __int64)(v24 + 40) <= MajorFunctionCode )
      {
        if ( *(unsigned int *)((char *)&Srb->SrbFlags + v24) )
        {
          p_SenseInfoBuffer = &Srb->SenseInfoBuffer;
LABEL_34:
          Cdb = (unsigned __int8 *)p_SenseInfoBuffer + v24;
          v336 = (__int64)Cdb;
          goto LABEL_42;
        }
        goto LABEL_41;
      }
    }
    else if ( (unsigned __int64)(v24 + 56) <= MajorFunctionCode )
    {
      if ( !*(&Srb->CdbLength + v24) )
        goto LABEL_41;
      v22 = 1;
      v336 = (__int64)&Srb->DataBuffer + v24;
    }
    goto LABEL_39;
  }
  if ( (unsigned __int64)(v24 + 40) > MajorFunctionCode )
  {
LABEL_39:
    if ( v22 )
      goto LABEL_41;
    goto LABEL_40;
  }
  if ( *(&Srb->CdbLength + v24) )
  {
    p_SenseInfoBuffer = &Srb->DataBuffer;
    goto LABEL_34;
  }
LABEL_41:
  Cdb = (unsigned __int8 *)v336;
LABEL_42:
  CdbLength = 0;
  if ( !*p_TimeOutValue )
  {
    v30 = (unsigned int)Srb->SrbExtension;
    if ( v30 )
    {
      v31 = 0;
      v32 = 0;
      v332 = 0;
      while ( 1 )
      {
        v33 = *((unsigned int *)&Srb[1].SenseInfoBuffer + v31);
        if ( (unsigned int)v33 >= 0x80 )
        {
          DataTransferLength = Srb->DataTransferLength;
          if ( (unsigned int)v33 < (unsigned int)DataTransferLength )
          {
            v35 = (unsigned int)v33;
            v36 = *(_DWORD *)((char *)&Srb->Length + v33) - 64;
            if ( v36 )
            {
              v37 = v36 - 1;
              if ( v37 )
              {
                if ( v37 == 1 && v35 + 40 <= DataTransferLength )
                  goto LABEL_65;
              }
              else if ( v35 + 56 <= DataTransferLength )
              {
                CdbLength = *(&Srb->CdbLength + v35);
                v32 = 1;
              }
            }
            else if ( v35 + 40 <= DataTransferLength )
            {
              CdbLength = *(&Srb->CdbLength + v35);
              goto LABEL_65;
            }
            if ( v32 )
              goto LABEL_65;
          }
        }
        v31 = (unsigned int)(v31 + 1);
        if ( (unsigned int)v31 >= v30 )
          goto LABEL_65;
      }
    }
  }
  v332 = 0;
LABEL_64:
  v336 = (__int64)Cdb;
LABEL_65:
  v356 = CdbLength;
  if ( Cdb )
    v332 = *Cdb;
  *Status = -1073741435;
  v38 = 24;
  v39 = Srb->Function;
  SrbStatus = Srb->SrbStatus;
  if ( v39 != 40 )
    v38 = 12;
  v41 = *(_DWORD *)((_BYTE *)&Srb->Length + v38) & 0x40000000;
  v42 = v41 != 0 ? -2147221453 : -1;
  LODWORD(v335) = v42;
  v43 = v41 != 0 ? 0x12D : 0;
  v337 = v43;
  MajorFunctionCode = v41 != 0;
  LOBYTE(v330) = v41 != 0;
  if ( (SrbStatus & 0x3F) == 0x30 )
  {
    v44 = 44;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v45 = 44;
      if ( v39 != 40 )
        v45 = 64;
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        76,
        WPP_9ee7907f5c473329e20561a6f3486187_Traceguids,
        *(unsigned int *)((char *)&Srb->Length + v45));
    }
    v46 = Srb->Function == 40;
    HIBYTE(v330) = 0;
    if ( !v46 )
      v44 = 64;
    *Status = *(_DWORD *)((char *)&Srb->Length + v44);
    goto LABEL_79;
  }
  v46 = v39 == 40;
  v60 = (unsigned __int64)v351;
  if ( !v46 )
  {
    ScsiStatus = Srb->ScsiStatus;
    goto LABEL_113;
  }
  if ( *v351 )
  {
    ScsiStatus = 0;
    goto LABEL_113;
  }
  if ( *(_DWORD *)p_SrbExtension )
  {
    ScsiStatus = 0;
    v62 = 0;
    v63 = 0;
    while ( 1 )
    {
      v64 = *((unsigned int *)&Srb[1].SenseInfoBuffer + v62);
      if ( (unsigned int)v64 >= 0x80 )
      {
        v65 = Srb->DataTransferLength;
        if ( (unsigned int)v64 < (unsigned int)v65 )
          break;
      }
LABEL_111:
      v62 = (unsigned int)(v62 + 1);
      if ( (unsigned int)v62 >= *(_DWORD *)p_SrbExtension )
        goto LABEL_112;
    }
    v66 = (unsigned int)v64;
    v67 = *(_DWORD *)((char *)&Srb->Length + v64) - 64;
    if ( !v67 )
      goto LABEL_109;
    v68 = v67 - 1;
    if ( v68 )
    {
      if ( v68 == 1 )
      {
LABEL_109:
        if ( v66 + 40 <= v65 )
        {
          ScsiStatus = *(&Srb->QueueTag + v66);
LABEL_112:
          v60 = (unsigned __int64)v351;
          v43 = v337;
          v42 = v335;
LABEL_113:
          if ( ScsiStatus == 24 )
          {
            v47 = 0;
            *Status = -2147483631;
            v330 = 0;
            v337 = v43;
            LODWORD(v335) = v42;
            goto LABEL_80;
          }
          MajorFunctionCode = v330;
          goto LABEL_121;
        }
      }
    }
    else if ( v66 + 56 <= v65 )
    {
      ScsiStatus = *(&Srb->QueueTag + v66);
      v63 = 1;
    }
    if ( v63 )
      goto LABEL_112;
    goto LABEL_111;
  }
LABEL_121:
  LOBYTE(v330) = MajorFunctionCode;
  v69 = -2147483626;
  if ( SrbStatus >= 0 )
    goto LABEL_881;
  v70 = v342;
  if ( !v342 )
  {
    SenseInfoBuffer = 0;
    v69 = -2147483626;
LABEL_881:
    LODWORD(v335) = v42;
    v337 = v43;
    goto LABEL_882;
  }
  v71 = 0;
  v72 = (*v342 & 0x7F) - 113;
  v331 = 0;
  v73 = 0;
  v334 = 0;
  if ( (v72 & 0xFD) == 0 )
    _InterlockedIncrement((volatile signed __int32 *)&PrivateFdoData->TotalScsiSenseDeferredErrorDataCount);
  if ( (unsigned __int8)((*v342 & 0x7F) - 112) > 3u )
    _InterlockedIncrement((volatile signed __int32 *)&PrivateFdoData->TotalScsiSenseUnknownFormatCount);
  v74 = Srb->Function;
  if ( v74 != 40 )
  {
    SenseInfoBufferLength = Srb->SenseInfoBufferLength;
    goto LABEL_140;
  }
  if ( *(_DWORD *)v60 )
  {
    SenseInfoBufferLength = 0;
    goto LABEL_140;
  }
  v75 = (unsigned int *)v352;
  if ( !*(_DWORD *)v352 )
  {
    v70 = v342;
    goto LABEL_163;
  }
  SenseInfoBufferLength = 0;
  v77 = 0;
  v78 = 0;
  while ( 1 )
  {
    v79 = *((unsigned int *)&Srb[1].SenseInfoBuffer + v77);
    if ( (unsigned int)v79 >= 0x80 )
    {
      v80 = Srb->DataTransferLength;
      if ( (unsigned int)v79 < (unsigned int)v80 )
        break;
    }
LABEL_138:
    v77 = (unsigned int)(v77 + 1);
    if ( (unsigned int)v77 >= *(_DWORD *)v352 )
      goto LABEL_139;
  }
  v60 = (unsigned int)v79;
  v81 = *(_DWORD *)((char *)&Srb->Length + v79) - 64;
  if ( v81 )
  {
    v82 = v81 - 1;
    if ( !v82 )
    {
      if ( v60 + 56 <= v80 )
      {
        SenseInfoBufferLength = *(&Srb->QueueAction + v60);
        v78 = 1;
      }
LABEL_137:
      if ( v78 )
        goto LABEL_139;
      goto LABEL_138;
    }
    if ( v82 != 1 )
      goto LABEL_137;
  }
  if ( v60 + 40 > v80 )
    goto LABEL_137;
  SenseInfoBufferLength = *(&Srb->QueueAction + v60);
LABEL_139:
  v70 = v342;
LABEL_140:
  if ( !SenseInfoBufferLength )
    goto LABEL_162;
  v83 = *v70 & 0x7F;
  if ( (unsigned __int8)(v83 - 114) <= 1u )
  {
    if ( v70 + 8 <= &v70[SenseInfoBufferLength] )
    {
      v71 = v70[2];
      v73 = v70[1] & 0xF;
      v86 = v70[3];
LABEL_150:
      v331 = v86;
      goto LABEL_157;
    }
    goto LABEL_160;
  }
  if ( (unsigned __int8)(v83 - 112) > 1u || v70 + 8 > &v70[SenseInfoBufferLength] )
  {
LABEL_160:
    LOBYTE(v60) = 0;
    goto LABEL_161;
  }
  v60 = (unsigned __int64)(v70 + 13);
  v73 = v70[2] & 0xF;
  v84 = SenseInfoBufferLength;
  if ( (unsigned int)(unsigned __int8)v70[7] + 8 <= SenseInfoBufferLength )
    v84 = (unsigned __int8)v70[7] + 8;
  v85 = (unsigned __int64)&v70[v84];
  if ( v60 <= v85 )
    v71 = v70[12];
  if ( (unsigned __int64)(v70 + 14) <= v85 )
  {
    v86 = *(_BYTE *)v60;
    goto LABEL_150;
  }
  v331 = 0;
LABEL_157:
  LOBYTE(v60) = 1;
LABEL_161:
  v338 = v60;
  if ( (_BYTE)v60 )
    goto LABEL_197;
LABEL_162:
  v60 = (unsigned __int64)v351;
  v75 = (unsigned int *)v352;
  MajorFunctionCode = v330;
LABEL_163:
  if ( (unsigned __int8)((*v70 & 0x7F) - 112) <= 3u )
    goto LABEL_879;
  if ( v74 != 40 )
  {
    v88 = Srb->SenseInfoBufferLength;
    goto LABEL_177;
  }
  if ( *(_DWORD *)v60 )
  {
    v88 = 0;
    goto LABEL_177;
  }
  v87 = *v75;
  if ( !*v75 )
    goto LABEL_194;
  v88 = 0;
  v89 = 0;
  v90 = 0;
  while ( 1 )
  {
    v91 = *((unsigned int *)&Srb[1].SenseInfoBuffer + v89);
    if ( (unsigned int)v91 >= 0x80 )
    {
      v92 = Srb->DataTransferLength;
      if ( (unsigned int)v91 < (unsigned int)v92 )
        break;
    }
LABEL_175:
    v89 = (unsigned int)(v89 + 1);
    if ( (unsigned int)v89 >= v87 )
      goto LABEL_176;
  }
  v60 = (unsigned int)v91;
  v93 = *(_DWORD *)((char *)&Srb->Length + v91) - 64;
  if ( v93 )
  {
    v94 = v93 - 1;
    if ( !v94 )
    {
      if ( v60 + 56 <= v92 )
      {
        v88 = *(&Srb->QueueAction + v60);
        v90 = 1;
      }
LABEL_174:
      if ( v90 )
        goto LABEL_176;
      goto LABEL_175;
    }
    if ( v94 != 1 )
      goto LABEL_174;
  }
  if ( v60 + 40 > v92 )
    goto LABEL_174;
  v88 = *(&Srb->QueueAction + v60);
LABEL_176:
  v70 = v342;
LABEL_177:
  if ( !v88 )
  {
LABEL_194:
    v70 = v342;
    LOBYTE(v60) = 0;
    goto LABEL_195;
  }
  LOBYTE(v60) = 0;
  v338 = 0;
  if ( v70 + 8 <= &v70[v88] )
  {
    v60 = (unsigned __int64)(v70 + 13);
    v73 = v70[2] & 0xF;
    v95 = v88;
    if ( (unsigned int)(unsigned __int8)v70[7] + 8 <= v88 )
      v95 = (unsigned __int8)v70[7] + 8;
    v96 = (unsigned __int64)&v70[v95];
    if ( v60 > v96 )
      v71 = 0;
    else
      v71 = v70[12];
    if ( (unsigned __int64)(v70 + 14) > v96 )
      v331 = 0;
    else
      v331 = *(_BYTE *)v60;
    LOBYTE(v60) = 1;
LABEL_195:
    v338 = v60;
  }
  if ( !(_BYTE)v60 )
  {
    MajorFunctionCode = v330;
LABEL_879:
    v69 = -2147483626;
    Cdb = (unsigned __int8 *)v336;
    SenseInfoBuffer = v342;
    LOBYTE(v330) = MajorFunctionCode;
LABEL_882:
    v141 = v332;
    goto LABEL_883;
  }
LABEL_197:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 77, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids, *v70 & 0x7F);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 78, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids, v73);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 79, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids, v71);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
        {
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 80, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids, v331);
        }
      }
    }
  }
  if ( (unsigned __int8)((*v70 & 0x7F) - 114) > 1u )
  {
    v97 = v70[2];
    BYTE3(v334) = v70[3];
    BYTE2(v334) = v70[4];
    BYTE1(v334) = v70[5];
    v98 = v70[6];
    v99 = 1;
    v346 = 1;
    v100 = (v97 & 0x20) != 0;
    LOBYTE(v334) = v98;
    goto LABEL_270;
  }
  v99 = 0;
  v100 = 0;
  v346 = 0;
  _InterlockedIncrement((volatile signed __int32 *)&PrivateFdoData->TotalScsiSenseDescriptorDataCount);
  if ( Srb->Function != 40 )
  {
    v101 = Srb->SenseInfoBufferLength;
    goto LABEL_228;
  }
  if ( *v351 )
  {
    v101 = 0;
    goto LABEL_228;
  }
  if ( *(_DWORD *)v352 )
  {
    v101 = 0;
    v102 = 0;
    v103 = 0;
    while ( 1 )
    {
      v104 = *((unsigned int *)&Srb[1].SenseInfoBuffer + v102);
      if ( (unsigned int)v104 >= 0x80 )
      {
        v105 = Srb->DataTransferLength;
        if ( (unsigned int)v104 < (unsigned int)v105 )
          break;
      }
LABEL_226:
      v102 = (unsigned int)(v102 + 1);
      if ( (unsigned int)v102 >= *(_DWORD *)v352 )
        goto LABEL_227;
    }
    v60 = (unsigned int)v104;
    v106 = *(_DWORD *)((char *)&Srb->Length + v104) - 64;
    if ( !v106 )
      goto LABEL_224;
    v107 = v106 - 1;
    if ( v107 )
    {
      if ( v107 == 1 )
      {
LABEL_224:
        if ( v60 + 40 <= v105 )
        {
          v101 = *(&Srb->QueueAction + v60);
LABEL_227:
          v70 = v342;
LABEL_228:
          if ( v101 && (unsigned __int8)((*v70 & 0x7F) - 114) <= 1u )
          {
            v60 = (unsigned __int64)(v70 + 8);
            v108 = 0;
            v109 = 0;
            v110 = 0;
            if ( v70 + 8 <= &v70[v101] )
            {
              v111 = v70[7];
              if ( v111 <= 0xF7u )
              {
                v112 = v111 + 8;
                if ( (unsigned __int8)(v111 + 8) > v101 )
                  v112 = v101;
                v109 = v112 - 8;
                if ( v109 )
                {
                  v108 = v70 + 8;
                  v110 = 1;
                }
              }
            }
            if ( v110 )
            {
              v113 = 0;
              *(_WORD *)Buffer = 1280;
              v114 = 0;
              while ( (!v113 || !v114) && v108 && v109 )
              {
                v115 = v108;
LABEL_248:
                if ( v109 < 2u )
                  break;
                for ( i = 0; ; i = (unsigned int)(i + 1) )
                {
                  if ( (unsigned int)i >= 2 )
                  {
                    v118 = v115[1] + 2;
                    if ( v109 <= v118 )
                      goto LABEL_270;
                    v115 += v118;
                    v109 -= v118;
                    goto LABEL_248;
                  }
                  LOBYTE(v60) = Buffer[i];
                  v117 = *v115;
                  if ( *v115 == (_BYTE)v60 )
                    break;
                }
                v119 = v115[1];
                v120 = v119 + 2;
                if ( v109 < (unsigned __int8)(v119 + 2) )
                  goto LABEL_270;
                if ( (_BYTE)v60 == 5 )
                {
                  if ( !v113 )
                  {
                    v113 = 1;
                    if ( v109 >= 4u && v117 == 5 && v119 == 2 )
                    {
                      v99 = 1;
                      v100 = (v115[3] & 0x20) != 0;
                    }
                  }
                }
                else
                {
                  if ( (_BYTE)v60 )
                    goto LABEL_270;
                  if ( !v114 )
                  {
                    v114 = 1;
                    if ( v109 >= 0xCu && !v117 && v119 == 10 && (v115[2] & 1) != 0 )
                    {
                      HIBYTE(v334) = v115[4];
                      BYTE6(v334) = v115[5];
                      BYTE5(v334) = v115[6];
                      BYTE4(v334) = v115[7];
                      BYTE3(v334) = v115[8];
                      BYTE2(v334) = v115[9];
                      BYTE1(v334) = v115[10];
                      LOBYTE(v334) = v115[11];
                      v346 = 1;
                    }
                  }
                }
                v108 = &v115[v120];
                v109 -= v120;
              }
            }
          }
          goto LABEL_270;
        }
      }
    }
    else if ( v60 + 56 <= v105 )
    {
      v101 = *(&Srb->QueueAction + v60);
      v103 = 1;
    }
    if ( v103 )
      goto LABEL_227;
    goto LABEL_226;
  }
LABEL_270:
  *(_QWORD *)&MajorFunctionCode = 133;
  if ( v73 == 5 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 99, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids);
    }
    v9 = v343;
    HIBYTE(v330) = 0;
    *v343 = -1073741808;
    if ( v71 > 0x24u )
    {
      if ( v71 == 37 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 114, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids);
        }
        *v9 = -1073741810;
        goto LABEL_694;
      }
      if ( v71 != 38 )
      {
        switch ( v71 )
        {
          case 0x6Fu:
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            {
              WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 118, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids);
            }
            v185 = v331;
            *v9 = -1073741051;
            if ( v185 )
            {
              v186 = v185 - 1;
              if ( v186 )
              {
                v187 = v186 - 1;
                if ( v187 )
                {
                  v188 = v187 - 1;
                  if ( v188 )
                  {
                    v189 = v188 - 1;
                    if ( v189 )
                    {
                      if ( v189 == 1 )
                      {
                        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                        {
                          WPP_SF_(
                            WPP_GLOBAL_Control->AttachedDevice,
                            124,
                            WPP_9ee7907f5c473329e20561a6f3486187_Traceguids);
                        }
                        *v9 = -1073741045;
                      }
                    }
                    else
                    {
                      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                      {
                        WPP_SF_(
                          WPP_GLOBAL_Control->AttachedDevice,
                          123,
                          WPP_9ee7907f5c473329e20561a6f3486187_Traceguids);
                      }
                      *v9 = -1073741046;
                    }
                  }
                  else
                  {
                    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                    {
                      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 122, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids);
                    }
                    *v9 = -1073741047;
                  }
                }
                else
                {
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                  {
                    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 121, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids);
                  }
                  *v9 = -1073741048;
                }
              }
              else
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                {
                  WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 120, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids);
                }
                *v9 = -1073741049;
              }
            }
            else
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
              {
                WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 119, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids);
              }
              *v9 = -1073741050;
            }
            goto LABEL_694;
          case 0xA0u:
            v181 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
              || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
            {
              goto LABEL_694;
            }
            v182 = 125;
            break;
          case 0xA1u:
            v181 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
              || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
            {
              goto LABEL_694;
            }
            v182 = 126;
            break;
          case 0xA7u:
            v181 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
              || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
            {
              goto LABEL_694;
            }
            v182 = 127;
            break;
          default:
            goto LABEL_694;
        }
        goto LABEL_574;
      }
      if ( v331 != 4 )
      {
        if ( v331 == 8 )
        {
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0 )
          {
            v140 = v334;
          }
          else
          {
            v140 = v334;
            if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
              WPP_SF_qDi(WPP_GLOBAL_Control->AttachedDevice, 116, MajorFunctionCode, DeviceObjecta, v332, v334);
          }
          *v9 = -1073740685;
          goto LABEL_516;
        }
        Cdb = (unsigned __int8 *)v336;
        if ( (unsigned __int8)ClasspIsOffloadDataTransferCommand(v336, v60, MajorFunctionCode) )
        {
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0 )
          {
            v140 = v334;
          }
          else
          {
            v140 = v334;
            if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
              WPP_SF_qDiDD(
                WPP_GLOBAL_Control->AttachedDevice,
                WPP_GLOBAL_Control,
                MajorFunctionCode,
                DeviceObjecta,
                v332,
                v334,
                38,
                v190);
          }
          *v9 = -1073740683;
          goto LABEL_696;
        }
LABEL_695:
        v140 = v334;
        goto LABEL_696;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_qD(
          WPP_GLOBAL_Control->AttachedDevice,
          115,
          WPP_9ee7907f5c473329e20561a6f3486187_Traceguids,
          DeviceObjecta,
          v332);
      }
      *v9 = -1073740684;
LABEL_694:
      Cdb = (unsigned __int8 *)v336;
      goto LABEL_695;
    }
    switch ( v71 )
    {
      case 0x24u:
        Cdb = (unsigned __int8 *)v336;
        if ( (unsigned __int8)ClasspIsOffloadDataTransferCommand(v336, v60, MajorFunctionCode) )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            WPP_SF_qD(
              WPP_GLOBAL_Control->AttachedDevice,
              112,
              WPP_9ee7907f5c473329e20561a6f3486187_Traceguids,
              DeviceObjecta,
              v332);
          }
          *v9 = -1073740681;
        }
        else
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 113, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids);
          }
          v348 = 3;
        }
        goto LABEL_695;
      case 0u:
        Cdb = (unsigned __int8 *)v336;
        if ( v331 == 22 && (unsigned __int8)ClasspIsOffloadDataTransferCommand(v336, v60, MajorFunctionCode) )
        {
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0 )
          {
            v140 = v334;
          }
          else
          {
            v140 = v334;
            if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
              WPP_SF_qDi(WPP_GLOBAL_Control->AttachedDevice, 100, MajorFunctionCode, DeviceObjecta, v332, v334);
          }
          *v9 = -1073740682;
          goto LABEL_696;
        }
        goto LABEL_695;
      case 8u:
        if ( v331 == 4 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            WPP_SF_qD(
              WPP_GLOBAL_Control->AttachedDevice,
              101,
              WPP_9ee7907f5c473329e20561a6f3486187_Traceguids,
              DeviceObjecta,
              v332);
          }
          *v9 = -1073740700;
        }
        goto LABEL_694;
      case 0xDu:
        if ( v331 != 4 )
          goto LABEL_694;
        v183 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_580;
        }
        v184 = 102;
        break;
      case 0x1Au:
        v183 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
LABEL_580:
          *v9 = -1073741764;
          goto LABEL_694;
        }
        v184 = 103;
        break;
      case 0x20u:
        if ( v331 == 2 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 104, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids);
          }
          *v9 = -1073741790;
          goto LABEL_694;
        }
        v181 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          v182 = 105;
LABEL_574:
          WPP_SF_(v181->AttachedDevice, v182, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids);
          goto LABEL_694;
        }
        goto LABEL_694;
      case 0x21u:
        v170 = DeviceObjecta;
        *(_DWORD *)Buffer = 0;
        *(_QWORD *)&ExtraData = 0;
        if ( !(unsigned __int8)ClasspIsManagedZonedDevice(DeviceObjecta) )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 108, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids);
          }
          Cdb = (unsigned __int8 *)v336;
          *v9 = -1073741803;
          if ( v170->DeviceType == 7 )
          {
            if ( ((v332 - 8) & 0x5D) != 0 || !Cdb )
            {
              if ( (unsigned __int8)ClasspIsOffloadDataTransferCommand(Cdb, v171, MajorFunctionCode)
                && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
              {
                v140 = v334;
                if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                  WPP_SF_qDi(WPP_GLOBAL_Control->AttachedDevice, 110, MajorFunctionCode, v170, v180, v334);
                goto LABEL_696;
              }
            }
            else
            {
              v177 = Cdb[2];
              v178 = Cdb[3];
              MajorFunctionCode = Cdb[4];
              if ( (FdoExtension->DeviceFlags & 0x20) != 0 )
              {
                BYTE4(ExtraData) = Cdb[5];
                BYTE3(ExtraData) = Cdb[6];
                BYTE2(ExtraData) = Cdb[7];
                BYTE1(ExtraData) = Cdb[8];
                LOBYTE(ExtraData) = Cdb[9];
                Buffer[3] = Cdb[10];
                Buffer[2] = Cdb[11];
                Buffer[1] = Cdb[12];
                v179 = Cdb[13];
                BYTE7(ExtraData) = v177;
                BYTE6(ExtraData) = v178;
                BYTE5(ExtraData) = MajorFunctionCode;
              }
              else
              {
                LOBYTE(ExtraData) = Cdb[5];
                Buffer[1] = Cdb[7];
                v179 = Cdb[8];
                BYTE3(ExtraData) = v177;
                BYTE2(ExtraData) = v178;
                BYTE1(ExtraData) = MajorFunctionCode;
              }
              Buffer[0] = v179;
              HIBYTE(v336) = PrivateFdoData->LastKnownDriveCapacityData.LogicalBlockAddress.LowPart;
              BYTE6(v336) = BYTE1(PrivateFdoData->LastKnownDriveCapacityData.LogicalBlockAddress.LowPart);
              BYTE5(v336) = BYTE2(PrivateFdoData->LastKnownDriveCapacityData.LogicalBlockAddress.u.LowPart);
              BYTE4(v336) = BYTE3(PrivateFdoData->LastKnownDriveCapacityData.LogicalBlockAddress.QuadPart);
              BYTE3(v336) = BYTE4(PrivateFdoData->LastKnownDriveCapacityData.LogicalBlockAddress.QuadPart);
              BYTE2(v336) = BYTE5(PrivateFdoData->LastKnownDriveCapacityData.LogicalBlockAddress.QuadPart);
              BYTE1(v336) = BYTE6(PrivateFdoData->LastKnownDriveCapacityData.LogicalBlockAddress.QuadPart);
              LOBYTE(v336) = HIBYTE(PrivateFdoData->LastKnownDriveCapacityData.LogicalBlockAddress.QuadPart);
              if ( (__int64)ExtraData > v336 || (__int64)(ExtraData + *(unsigned int *)Buffer - 1LL) > v336 )
              {
                *(_QWORD *)&MajorFunctionCode = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
                {
                  WPP_SF_iiD(WPP_GLOBAL_Control->AttachedDevice, 109);
                }
              }
              else
              {
                HIBYTE(v330) = 1;
                v348 = 5;
              }
            }
          }
          goto LABEL_695;
        }
        v172 = v332;
        *v9 = -1073741803;
        if ( ((v172 - 8) & 0x5D) == 0 )
        {
          if ( v336 )
          {
            v173 = *(_BYTE *)(v336 + 2);
            v174 = *(_BYTE *)(v336 + 3);
            v175 = *(_BYTE *)(v336 + 4);
            if ( (FdoExtension->DeviceFlags & 0x20) != 0 )
            {
              BYTE4(ExtraData) = *(_BYTE *)(v336 + 5);
              BYTE3(ExtraData) = *(_BYTE *)(v336 + 6);
              BYTE2(ExtraData) = *(_BYTE *)(v336 + 7);
              BYTE1(ExtraData) = *(_BYTE *)(v336 + 8);
              LOBYTE(ExtraData) = *(_BYTE *)(v336 + 9);
              Buffer[3] = *(_BYTE *)(v336 + 10);
              Buffer[2] = *(_BYTE *)(v336 + 11);
              Buffer[1] = *(_BYTE *)(v336 + 12);
              v176 = *(_BYTE *)(v336 + 13);
              BYTE7(ExtraData) = v173;
              BYTE6(ExtraData) = v174;
              BYTE5(ExtraData) = v175;
            }
            else
            {
              LOBYTE(ExtraData) = *(_BYTE *)(v336 + 5);
              Buffer[1] = *(_BYTE *)(v336 + 7);
              v176 = *(_BYTE *)(v336 + 8);
              BYTE3(ExtraData) = v173;
              BYTE2(ExtraData) = v174;
              BYTE1(ExtraData) = v175;
            }
            *(_QWORD *)&MajorFunctionCode = ExtraData;
            Buffer[0] = v176;
          }
          if ( ((v172 - 8) & 0x5F) == 0 && v331 == 6 )
          {
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
            {
              v140 = v334;
            }
            else
            {
              v140 = v334;
              if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
                WPP_SF_iiD(WPP_GLOBAL_Control->AttachedDevice, 106);
            }
            *v9 = -1073741392;
            goto LABEL_516;
          }
          if ( ((v172 - 10) & 0x5F) == 0 && v172 != 0x8A )
            goto LABEL_535;
        }
        if ( v172 == 0x8A )
        {
LABEL_535:
          if ( (unsigned __int8)(v331 - 4) <= 1u )
          {
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
            {
              v140 = v334;
            }
            else
            {
              v140 = v334;
              if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
                WPP_SF_iiD(WPP_GLOBAL_Control->AttachedDevice, 107);
            }
            *v9 = -1073741391;
            goto LABEL_516;
          }
        }
        break;
      case 0x23u:
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) == 0 )
        {
          v140 = v334;
        }
        else
        {
          v140 = v334;
          if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            WPP_SF_qDi(WPP_GLOBAL_Control->AttachedDevice, 111, MajorFunctionCode, DeviceObjecta, v332, v334);
        }
        *v9 = -1073740699;
LABEL_516:
        Cdb = (unsigned __int8 *)v336;
LABEL_696:
        v47 = v330;
        SenseInfoBuffer = v342;
        goto LABEL_325;
      default:
        goto LABEL_694;
    }
    WPP_SF_qD(v183->AttachedDevice, v184, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids, DeviceObjecta, v332);
    goto LABEL_580;
  }
  if ( v73 > 5u )
  {
    if ( v73 != 6 )
    {
      switch ( v73 )
      {
        case 7u:
          HIBYTE(v330) = 0;
          if ( v71 != 39 )
          {
            if ( ((v332 - 10) & 0x5F) != 0 )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
              {
                WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 142, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids);
              }
              v9 = v343;
              *v343 = -1073741790;
            }
            else
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
              {
                WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 141, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids);
              }
              v9 = v343;
              *v343 = -1073741662;
            }
            goto LABEL_494;
          }
          if ( v331 == 7 )
          {
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
            {
              v191 = DeviceObjecta;
            }
            else
            {
              v191 = DeviceObjecta;
              if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
                WPP_SF_q(
                  WPP_GLOBAL_Control->AttachedDevice,
                  140,
                  WPP_9ee7907f5c473329e20561a6f3486187_Traceguids,
                  DeviceObjecta);
            }
            ClassQueueResourceExhaustionEventWorker(v191);
            v9 = v343;
            *v343 = -1073740703;
            goto LABEL_494;
          }
          break;
        case 8u:
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 143, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids);
          }
          v9 = v343;
          HIBYTE(v330) = 0;
          *v343 = -2147483614;
          goto LABEL_494;
        case 0xAu:
          if ( v71 == 13 && v331 == 4 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
            {
              WPP_SF_qD(
                WPP_GLOBAL_Control->AttachedDevice,
                144,
                WPP_9ee7907f5c473329e20561a6f3486187_Traceguids,
                DeviceObjecta,
                v332);
            }
            v9 = v343;
            HIBYTE(v330) = 0;
            *v343 = 0;
            goto LABEL_494;
          }
          break;
        case 0xBu:
          Cdb = (unsigned __int8 *)v336;
          if ( !(unsigned __int8)ClasspIsOffloadDataTransferCommand(v336, v60, 133) )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            {
              WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 147, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids);
            }
            v9 = v343;
            v348 = 1;
            *v343 = -1073741435;
            goto LABEL_729;
          }
          if ( v71 == 13 )
          {
            if ( v331 == 4 )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
              {
                WPP_SF_qD(
                  WPP_GLOBAL_Control->AttachedDevice,
                  145,
                  WPP_9ee7907f5c473329e20561a6f3486187_Traceguids,
                  DeviceObjecta,
                  v332);
              }
              v9 = v343;
              *v343 = 0;
              goto LABEL_722;
            }
          }
          else if ( v71 == 85 && v331 == 3 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            {
              WPP_SF_qD(
                WPP_GLOBAL_Control->AttachedDevice,
                146,
                WPP_9ee7907f5c473329e20561a6f3486187_Traceguids,
                DeviceObjecta,
                *(unsigned __int8 *)v336);
            }
            v9 = v343;
            *v343 = -1073741670;
LABEL_722:
            HIBYTE(v330) = 0;
LABEL_729:
            v47 = v330;
            goto LABEL_496;
          }
          v9 = v343;
          goto LABEL_729;
        default:
LABEL_702:
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 148, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids);
          }
          v9 = v343;
          *v343 = -1073741435;
          goto LABEL_494;
      }
      v9 = v343;
LABEL_494:
      v47 = v330;
LABEL_495:
      Cdb = (unsigned __int8 *)v336;
LABEL_496:
      SenseInfoBuffer = v342;
      goto LABEL_324;
    }
    v192 = FdoExtension;
    v193 = (unsigned int)_InterlockedIncrement((volatile signed __int32 *)&FdoExtension->MediaChangeCount);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_dL(WPP_GLOBAL_Control->AttachedDevice, v193, 133, v192->DeviceNumber, v193);
      *(_QWORD *)&MajorFunctionCode = 133;
    }
    switch ( v71 )
    {
      case '(':
        v333 = 0;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 129, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids);
        }
        if ( (DeviceObjecta->Characteristics & 1) == 0
          && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_q(
            WPP_GLOBAL_Control->AttachedDevice,
            130,
            WPP_9ee7907f5c473329e20561a6f3486187_Traceguids,
            DeviceObjecta);
        }
        ClasspSetMediaChangeStateEx(v192);
        goto LABEL_853;
      case ')':
        v194 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
        {
          goto LABEL_853;
        }
        v195 = 131;
LABEL_777:
        WPP_SF_(v194->AttachedDevice, v195, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids);
LABEL_853:
        v47 = v330;
LABEL_854:
        if ( (DeviceObjecta->Characteristics & 1) != 0 )
        {
          Vpb = DeviceObjecta->Vpb;
          if ( Vpb && (Vpb->Flags & 1) != 0 )
          {
            DeviceObjecta->Flags |= 2u;
            v208 = -2147483626;
            HIBYTE(v330) = 0;
          }
          else
          {
            v208 = -1073741435;
          }
          v9 = v343;
          *v343 = v208;
        }
        else
        {
          v9 = v343;
          *v343 = -1073741435;
        }
        goto LABEL_495;
      case '*':
        v333 = 0;
        if ( v331 != 9 )
          goto LABEL_853;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 132, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids);
        }
        ClassQueueCapacityChangedEventWorker(DeviceObjecta);
        goto LABEL_815;
      case '8':
        if ( v331 == 7 )
        {
          v333 = 0;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          {
            v206 = DeviceObjecta;
          }
          else
          {
            v206 = DeviceObjecta;
            if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
              WPP_SF_q(
                WPP_GLOBAL_Control->AttachedDevice,
                133,
                WPP_9ee7907f5c473329e20561a6f3486187_Traceguids,
                DeviceObjecta);
          }
          ClassQueueThresholdEventWorker(v206);
        }
        else
        {
          HIBYTE(v330) = 0;
        }
        goto LABEL_853;
    }
    if ( v71 != 63 )
    {
      if ( v71 == 90 )
      {
        switch ( v331 )
        {
          case 1u:
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 136, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids);
            }
            ClassSendEjectionNotification(v192);
            goto LABEL_795;
          case 2u:
            v196 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
              || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
            {
              goto LABEL_795;
            }
            v197 = 137;
            break;
          case 3u:
            v196 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
              || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
            {
              goto LABEL_795;
            }
            v197 = 138;
            break;
          default:
            goto LABEL_795;
        }
        WPP_SF_(v196->AttachedDevice, v197, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids);
      }
      else if ( v71 != 93 )
      {
        v194 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
        {
          goto LABEL_853;
        }
        v195 = 139;
        goto LABEL_777;
      }
LABEL_795:
      v198 = v331;
      v47 = v192->FailurePredicted == 0;
      v192->FailureReason = v331;
      v46 = Srb->Function == 40;
      LOBYTE(v330) = v47;
      *(_DWORD *)Buffer = 1;
      v345 = v198;
      LODWORD(v335) = -2147221452;
      if ( v46 )
      {
        OriginalRequest_high = HIDWORD(Srb->OriginalRequest);
        v200 = 0;
        if ( (_DWORD)OriginalRequest_high )
        {
          v201 = (char *)Srb + (unsigned int)OriginalRequest_high;
          if ( v201 )
          {
            if ( *(_WORD *)v201 == 1 )
              v200 = v201[10];
          }
        }
        v202 = 0;
        if ( (_DWORD)OriginalRequest_high )
        {
          v203 = (char *)Srb + OriginalRequest_high;
          if ( (PSCSI_REQUEST_BLOCK)((char *)Srb + OriginalRequest_high) )
          {
            if ( *(_WORD *)v203 == 1 )
              v202 = v203[9];
          }
        }
        v204 = 0;
        if ( (_DWORD)OriginalRequest_high )
        {
          v205 = (char *)Srb + OriginalRequest_high;
          if ( v205 )
          {
            if ( *(_WORD *)v205 == 1 )
              v204 = v205[8];
          }
        }
      }
      else
      {
        v200 = Srb->Lun;
        v202 = Srb->TargetId;
        v204 = Srb->PathId;
      }
      ClassNotifyFailurePredicted(v192, Buffer, 5u, 0, 4u, v204, v202, v200);
      v192->FailurePredicted = 1;
      HIBYTE(v330) = 1;
      goto LABEL_854;
    }
    if ( v331 == 1 )
    {
      v333 = 1;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 134, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids);
      }
LABEL_815:
      v348 = 1;
      HIBYTE(v330) = 1;
      goto LABEL_853;
    }
    v333 = 0;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 135, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids);
    }
    if ( v331 == 3 )
    {
      ClassQueueProvisioningTypeChangedEventWorker(DeviceObjecta);
    }
    else if ( v331 != 2 )
    {
LABEL_824:
      IoInvalidateDeviceRelations(v192->LowerPdo, BusRelations);
      v348 = 5;
      goto LABEL_853;
    }
    _InterlockedAdd((volatile signed __int32 *)&v192->FunctionSupportInfo->ChangeRequestCount, 1u);
    goto LABEL_824;
  }
  switch ( v73 )
  {
    case 0u:
      if ( v99 && v100 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 81, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids);
        }
        v168 = 0;
        v169 = -1073741453;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 82, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids);
        }
        v168 = 1;
        v169 = -1073741435;
      }
      v9 = v343;
      *v343 = v169;
      HIBYTE(v330) = v168;
      goto LABEL_494;
    case 1u:
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 83, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids);
      }
      v330 = 1;
      *v343 = 0;
      v337 = 258;
      switch ( v71 )
      {
        case 0x14u:
        case 0x15u:
          LODWORD(v335) = -1073479674;
          break;
        case 0x17u:
        case 0x18u:
          LODWORD(v335) = -2147221471;
          break;
        case 0x5Du:
          *(_DWORD *)Buffer = 1;
          v160 = FdoExtension;
          v345 = v331;
          LODWORD(v335) = -2147221452;
          v46 = FdoExtension->FailurePredicted == 0;
          FdoExtension->FailureReason = v331;
          LOBYTE(v330) = v46;
          if ( Srb->Function == 40 )
          {
            v161 = HIDWORD(Srb->OriginalRequest);
            Lun = 0;
            if ( (_DWORD)v161 )
            {
              v163 = (char *)Srb + (unsigned int)v161;
              if ( v163 )
              {
                if ( *(_WORD *)v163 == 1 )
                  Lun = v163[10];
              }
            }
            TargetId = 0;
            if ( (_DWORD)v161 )
            {
              v165 = (char *)Srb + v161;
              if ( (PSCSI_REQUEST_BLOCK)((char *)Srb + v161) )
              {
                if ( *(_WORD *)v165 == 1 )
                  TargetId = v165[9];
              }
            }
            PathId = 0;
            if ( (_DWORD)v161 )
            {
              v167 = (char *)Srb + v161;
              if ( v167 )
              {
                if ( *(_WORD *)v167 == 1 )
                  PathId = v167[8];
              }
            }
          }
          else
          {
            Lun = Srb->Lun;
            TargetId = Srb->TargetId;
            PathId = Srb->PathId;
          }
          ClassNotifyFailurePredicted(v160, Buffer, 5u, 0, 4u, PathId, TargetId, Lun);
          v160->FailurePredicted = 1;
          break;
        default:
          LODWORD(v335) = -1073479669;
          break;
      }
      if ( !v99 || !v100 )
      {
        v47 = v330;
        goto LABEL_322;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 84, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids);
      }
      v9 = v343;
      *v343 = -1073741453;
      goto LABEL_446;
    case 2u:
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 85, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids);
      }
      v9 = v343;
      *v343 = -1073741661;
      if ( v71 != 4 )
      {
        if ( v71 == 58 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 95, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids);
          }
          v156 = DeviceObjecta;
          *v9 = -1073741805;
          HIBYTE(v330) = 0;
          if ( (v156->Characteristics & 1) == 0
            && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
          {
            WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 96, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids, v156);
          }
          ClasspSetMediaChangeStateEx(FdoExtension);
        }
        goto LABEL_446;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 86, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids);
      }
      v348 = 10;
      if ( v331 )
      {
        switch ( v331 )
        {
          case 1u:
            v333 = 0;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 87, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids);
            }
            DWORD1(ExtraData) = 1;
LABEL_430:
            LODWORD(ExtraData) = 1;
            DWORD2(ExtraData) = 100;
            ClassSendNotification(FdoExtension, &GUID_IO_DEVICE_BECOMING_READY, 0xCu, &ExtraData);
            goto LABEL_446;
          case 2u:
LABEL_436:
            v157 = FdoExtension;
LABEL_437:
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 94, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids);
            }
            DeviceFlags = v157->DeviceFlags;
            v348 = 0;
            v333 = 0;
            if ( (DeviceFlags & 4) != 0 )
            {
              v159 = 24;
              if ( Srb->Function != 40 )
                v159 = 12;
              if ( (*(_DWORD *)((_BYTE *)&Srb->Length + v159) & 0x10000000) == 0 )
                ClassSendStartUnit(DeviceObjecta);
            }
            goto LABEL_446;
          case 3u:
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 88, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids);
            }
            *v9 = -1073741805;
            break;
          case 4u:
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 89, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids);
            }
            if ( (Srb->SrbStatus & 0x3F) == 0x18 )
              *v9 = -1073740682;
            break;
          case 7u:
            v333 = 0;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 90, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids);
            }
            DWORD1(ExtraData) = 2;
            goto LABEL_430;
          case 8u:
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 91, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids);
            }
            HIBYTE(v330) = 0;
            v348 = 1;
            goto LABEL_446;
          case 0x14u:
            v333 = 0;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
            {
              WPP_SF_q(
                WPP_GLOBAL_Control->AttachedDevice,
                92,
                WPP_9ee7907f5c473329e20561a6f3486187_Traceguids,
                DeviceObjecta);
            }
            *v9 = -1073741267;
            HIBYTE(v330) = 1;
            goto LABEL_446;
          default:
            goto LABEL_436;
        }
      }
      else
      {
        v157 = FdoExtension;
        if ( (FdoExtension->ScanForSpecialFlags & 0x20) != 0 )
          goto LABEL_437;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 93, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids);
        }
      }
      HIBYTE(v330) = 0;
LABEL_446:
      Cdb = (unsigned __int8 *)v336;
      SenseInfoBuffer = v342;
      v47 = v330;
      goto LABEL_324;
    case 3u:
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 97, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids);
      }
      v9 = v343;
      v47 = 1;
      v330 = 1;
      v337 = 256;
      *v343 = -1073741668;
      LODWORD(v335) = -1073479673;
      if ( v71 == 48 )
      {
        Cdb = (unsigned __int8 *)v336;
        v140 = v334;
        SenseInfoBuffer = v342;
        if ( v331 == 1 )
        {
          v155 = 24;
          *v9 = -1073741804;
          if ( Srb->Function != 40 )
            v155 = 12;
          if ( (*(_DWORD *)((_BYTE *)&Srb->Length + v155) & 0x40000000) != 0 )
            goto LABEL_325;
        }
        else
        {
          if ( v331 != 3 )
            goto LABEL_325;
          *v9 = -2147483609;
        }
        v47 = 0;
        LOBYTE(v330) = 0;
        goto LABEL_325;
      }
      goto LABEL_495;
  }
  if ( v73 != 4 )
    goto LABEL_702;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 98, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids);
  }
  v121 = v343;
  if ( !PrivateFdoData->LegacyErrorHandling )
  {
    v47 = 0;
    v122 = 1;
    HIBYTE(v330) = 0;
    *v343 = -1073740669;
    LOBYTE(v330) = 0;
    goto LABEL_289;
  }
  v123 = v331;
  HIBYTE(v330) = 1;
  *v343 = -1073741435;
  v337 = 257;
  LODWORD(v335) = -1073479669;
  if ( v71 == 62 && v123 == 2 )
    goto LABEL_287;
  LOBYTE(v330) = 1;
  v47 = 1;
  if ( v71 == 75 )
  {
    if ( v123 == 6 )
    {
LABEL_287:
      v47 = 0;
      v330 = 0;
      v122 = 1;
      goto LABEL_289;
    }
    v9 = v121;
    goto LABEL_495;
  }
  v122 = 0;
LABEL_289:
  if ( v71 == 17 )
  {
    if ( !v331 )
    {
      DeviceDescriptor = FdoExtension->DeviceDescriptor;
      if ( DeviceDescriptor )
      {
        if ( DeviceDescriptor->BusType == BusTypeSas )
        {
          if ( RetryCount )
          {
            HIBYTE(v330) = 0;
          }
          else
          {
            HIBYTE(v330) = 1;
            v122 = 0;
          }
          v47 = 0;
          LOBYTE(v330) = 0;
        }
      }
    }
  }
  else if ( v71 == 8 && v331 == 3 )
  {
    v47 = 0;
    v330 = 256;
    v348 = 1;
    goto LABEL_322;
  }
  if ( !v122 )
  {
LABEL_322:
    SenseInfoBuffer = v342;
    Cdb = (unsigned __int8 *)v336;
    goto LABEL_323;
  }
  v125 = Srb->Function;
  v126 = v351;
  v127 = (unsigned int *)v352;
  if ( v125 != 40 )
  {
    v128 = Srb->SenseInfoBufferLength;
    goto LABEL_311;
  }
  v128 = 0;
  if ( *v351 || !*(_DWORD *)v352 )
    goto LABEL_311;
  v129 = 0;
  v130 = 0;
  while ( 1 )
  {
    v131 = *((unsigned int *)&Srb[1].SenseInfoBuffer + v129);
    if ( (unsigned int)v131 >= 0x80 )
    {
      v132 = Srb->DataTransferLength;
      if ( (unsigned int)v131 < (unsigned int)v132 )
        break;
    }
LABEL_309:
    v129 = (unsigned int)(v129 + 1);
    if ( (unsigned int)v129 >= *(_DWORD *)v352 )
      goto LABEL_310;
  }
  v133 = (unsigned int)v131;
  v134 = *(_DWORD *)((char *)&Srb->Length + v131) - 64;
  if ( v134 )
  {
    v135 = v134 - 1;
    if ( !v135 )
    {
      if ( v133 + 56 <= v132 )
      {
        v128 = *(&Srb->QueueAction + v133);
        v130 = 1;
      }
LABEL_308:
      if ( v130 )
        goto LABEL_310;
      goto LABEL_309;
    }
    if ( v135 != 1 )
      goto LABEL_308;
  }
  if ( v133 + 40 > v132 )
    goto LABEL_308;
  v128 = *(&Srb->QueueAction + v133);
LABEL_310:
  v126 = v351;
  v127 = (unsigned int *)v352;
LABEL_311:
  SenseInfoBuffer = v342;
  if ( !v128 )
    goto LABEL_338;
  v136 = 0;
  v137 = 0;
  if ( v342 + 8 <= &v342[v128] )
  {
    v138 = v342[7];
    if ( v138 <= 0xF7u )
    {
      v136 = v138 + 8;
      v137 = 1;
    }
  }
  if ( v137 )
  {
    v139 = v128;
    if ( v136 < v128 )
      v139 = v136;
  }
  else
  {
LABEL_338:
    v139 = v128;
  }
  if ( v125 == 40 )
  {
    if ( !*v126 )
    {
      v146 = *v127;
      v147 = 0;
      if ( !*v127 )
        goto LABEL_357;
      v148 = 0;
      v149 = 0;
      while ( 2 )
      {
        v150 = *((unsigned int *)&Srb[1].SenseInfoBuffer + v148);
        if ( (unsigned int)v150 >= 0x80 )
        {
          v151 = Srb->DataTransferLength;
          if ( (unsigned int)v150 < (unsigned int)v151 )
          {
            v152 = (unsigned int)v150;
            v153 = *(_DWORD *)((char *)&Srb->Length + v150) - 64;
            if ( v153 )
            {
              v154 = v153 - 1;
              if ( v154 )
              {
                if ( v154 == 1 )
                  goto LABEL_348;
              }
              else if ( v152 + 56 <= v151 )
              {
                v147 = *(&Srb->QueueTag + v152);
                v149 = 1;
              }
            }
            else
            {
LABEL_348:
              if ( v152 + 40 <= v151 )
              {
                v147 = *(&Srb->QueueTag + v152);
                goto LABEL_357;
              }
            }
            if ( v149 )
              goto LABEL_357;
          }
        }
        v148 = (unsigned int)(v148 + 1);
        if ( (unsigned int)v148 >= v146 )
          goto LABEL_357;
        continue;
      }
    }
    v147 = 0;
  }
  else
  {
    v147 = Srb->ScsiStatus;
  }
LABEL_357:
  Cdb = (unsigned __int8 *)v336;
  ClasspQueueLogIOEventWithContextWorker(DeviceObjecta, v139, v147, -1073479526, v356, v336, 0);
  v47 = v330;
LABEL_323:
  v9 = v343;
LABEL_324:
  v140 = v334;
LABEL_325:
  v141 = v332;
  if ( v332 <= 0x2Fu && (v142 = 0x850000000500LL, _bittest64(&v142, v332))
    || (unsigned __int8)(v332 + 120) <= 0x22u && (v143 = 0x500000085LL, _bittest64(&v143, (unsigned int)v332 + 120)) )
  {
    if ( Cdb && v346 )
    {
      *(_QWORD *)&ExtraData = 0;
      v358 = v140;
      if ( (unsigned __int8)(v332 + 120) <= 7u && (v144 = 133, _bittest(&v144, v332 + 120)) )
      {
        BYTE7(ExtraData) = Cdb[2];
        BYTE6(ExtraData) = Cdb[3];
        BYTE5(ExtraData) = Cdb[4];
        BYTE4(ExtraData) = Cdb[5];
        BYTE3(ExtraData) = Cdb[6];
        BYTE2(ExtraData) = Cdb[7];
        BYTE1(ExtraData) = Cdb[8];
        v145 = Cdb[9];
      }
      else
      {
        BYTE3(ExtraData) = Cdb[2];
        BYTE2(ExtraData) = Cdb[3];
        BYTE1(ExtraData) = Cdb[4];
        v145 = Cdb[5];
      }
      LOBYTE(ExtraData) = v145;
      if ( v332 <= 0x2Fu )
      {
        v209 = 0x850000000000LL;
        if ( _bittest64(&v209, v332) )
        {
          BYTE1(v341) = Cdb[7];
          v210 = Cdb[8];
          goto LABEL_871;
        }
      }
      if ( ((v332 - 8) & 0xFD) != 0 )
      {
        if ( ((v332 + 88) & 0xFD) != 0 )
        {
          HIBYTE(v341) = Cdb[10];
          BYTE2(v341) = Cdb[11];
          BYTE1(v341) = Cdb[12];
          v210 = Cdb[13];
        }
        else
        {
          HIBYTE(v341) = Cdb[6];
          BYTE2(v341) = Cdb[7];
          BYTE1(v341) = Cdb[8];
          v210 = Cdb[9];
        }
LABEL_871:
        LOBYTE(v341) = v210;
      }
      else
      {
        v341 = Cdb[4];
      }
      if ( v140 < (unsigned __int64)ExtraData || v140 >= (unsigned __int64)ExtraData + v341 )
        v358 = ExtraData;
    }
  }
  if ( v338 )
    goto LABEL_80;
  v69 = -2147483626;
LABEL_883:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      149,
      WPP_9ee7907f5c473329e20561a6f3486187_Traceguids,
      Srb->SrbStatus & 0x3F);
  }
  v211 = Srb->SrbStatus & 0x3F;
  HIBYTE(v330) = 1;
  if ( v211 > 0x38 )
    goto LABEL_984;
  if ( v211 == 56 )
  {
    v9 = v343;
    *v343 = -1073740534;
    goto LABEL_950;
  }
  if ( v211 > 0xE )
  {
    v237 = v211 - 15;
    if ( !v237 )
      goto LABEL_977;
    v238 = v237 - 2;
    if ( !v238 )
      goto LABEL_949;
    v239 = v238 - 1;
    if ( v239 )
    {
      v240 = v239 - 1;
      if ( v240 )
      {
        v241 = v240 - 1;
        if ( !v241 )
        {
          v9 = v343;
          *v343 = -1073741435;
          if ( RetryCount > 1 )
            HIBYTE(v330) = 0;
          goto LABEL_979;
        }
        v242 = v241 - 2;
        if ( v242 )
        {
          if ( v242 - 10 > 1 )
            goto LABEL_984;
          goto LABEL_949;
        }
        v48 = DeviceObjecta;
        if ( (DeviceObjecta->Flags & 2) != 0 )
        {
          HIBYTE(v330) = 0;
        }
        else
        {
          v69 = -1073741435;
          v333 = 0;
        }
        v9 = v343;
        *v343 = v69;
LABEL_955:
        v47 = v330;
        goto LABEL_81;
      }
LABEL_977:
      v212 = 1;
LABEL_978:
      v9 = v343;
      v347 = 0;
      v333 = 0;
      *v343 = -1073741435;
      if ( !v212 )
        goto LABEL_79;
      goto LABEL_979;
    }
    v9 = v343;
    v243 = 60;
    HIBYTE(v330) = 0;
    *v343 = -1073741764;
    v244 = Srb->Function;
    if ( v141 == 26 || v141 == 18 )
    {
      v245 = 60;
      if ( v244 != 40 )
        v245 = 16;
      if ( *(_DWORD *)((char *)&Srb->Length + v245) <= (unsigned int)Cdb[4] )
      {
        v47 = 0;
        *v9 = 0;
        LOBYTE(v330) = 0;
        v339 = 0;
        goto LABEL_80;
      }
    }
    else if ( v141 == 90 )
    {
      Buffer[1] = Cdb[7];
      Buffer[0] = Cdb[8];
      if ( v244 != 40 )
        v243 = 16;
      v246 = *(unsigned __int16 *)Buffer;
LABEL_968:
      v48 = DeviceObjecta;
      if ( *(_DWORD *)((char *)&Srb->Length + v243) <= v246 )
      {
        v47 = 0;
        *v9 = 0;
        LOBYTE(v330) = 0;
        v339 = 0;
        goto LABEL_81;
      }
      goto LABEL_955;
    }
    if ( !(unsigned __int8)ClasspIsReceiveTokenInformation(Cdb, 1, 60) && (v141 != 0x95 || (Cdb[1] & 0x1F) != 0) )
      goto LABEL_79;
    HIBYTE(v341) = Cdb[10];
    if ( v247 != 40 )
      v243 = v248;
    BYTE2(v341) = Cdb[11];
    BYTE1(v341) = Cdb[12];
    LOBYTE(v341) = Cdb[13];
    v246 = v341;
    goto LABEL_968;
  }
  v212 = 0;
  if ( v211 == 14 )
    goto LABEL_978;
  v213 = v211 - 2;
  if ( !v213 )
  {
    v9 = v343;
    v348 = 1;
    *v343 = -1073741643;
LABEL_982:
    ClasspPerfIncrementErrorCount(FdoExtension, 1, MajorFunctionCode);
    goto LABEL_79;
  }
  v214 = v213 - 2;
  if ( v214 )
  {
    v215 = v214 - 2;
    if ( v215 )
    {
      v216 = v215 - 1;
      if ( v216 )
      {
        v217 = v216 - 1;
        if ( v217 )
        {
          v218 = v217 - 1;
          if ( !v218 )
            goto LABEL_899;
          v219 = v218 - 1;
          if ( v219 )
          {
            if ( v219 == 1 )
            {
LABEL_899:
              v9 = v343;
              *v343 = -1073741643;
              goto LABEL_979;
            }
LABEL_984:
            v9 = v343;
            v47 = 1;
            LOBYTE(v330) = 1;
            LODWORD(v335) = -1073479669;
            v337 = 259;
            *v343 = -1073741435;
            v347 = 1;
            v333 = 0;
          }
          else
          {
            v9 = v343;
            v47 = 1;
            LOBYTE(v330) = 1;
            LODWORD(v335) = -1073479665;
            v337 = 260;
            *v343 = -1073741667;
            HIBYTE(v330) = 0;
          }
LABEL_80:
          v48 = DeviceObjecta;
          goto LABEL_81;
        }
      }
LABEL_949:
      v9 = v343;
      *v343 = -1073741810;
LABEL_950:
      HIBYTE(v330) = 0;
    }
    else
    {
      v9 = v343;
      HIBYTE(v330) = 0;
      *v343 = -1073741808;
    }
LABEL_79:
    v47 = v330;
    goto LABEL_80;
  }
  v9 = v343;
  v220 = v351;
  *v343 = -1073741435;
  v221 = Srb->Function;
  if ( v221 == 40 )
  {
    if ( !*v220 )
    {
      if ( *(_DWORD *)v352 )
      {
        MajorFunctionCode = 0;
        v222 = 0;
        v223 = 0;
        while ( 1 )
        {
          v224 = *((unsigned int *)&Srb[1].SenseInfoBuffer + v222);
          if ( (unsigned int)v224 >= 0x80 )
          {
            v225 = Srb->DataTransferLength;
            if ( (unsigned int)v224 < (unsigned int)v225 )
              break;
          }
LABEL_913:
          v222 = (unsigned int)(v222 + 1);
          if ( (unsigned int)v222 >= *(_DWORD *)v352 )
            goto LABEL_920;
        }
        v226 = (unsigned int)v224;
        v227 = *(_DWORD *)((char *)&Srb->Length + v224) - 64;
        if ( !v227 )
          goto LABEL_911;
        v228 = v227 - 1;
        if ( v228 )
        {
          if ( v228 == 1 )
          {
LABEL_911:
            if ( v226 + 40 <= v225 )
            {
              MajorFunctionCode = *(&Srb->QueueTag + v226);
              goto LABEL_920;
            }
          }
        }
        else if ( v226 + 56 <= v225 )
        {
          MajorFunctionCode = *(&Srb->QueueTag + v226);
          v223 = 1;
        }
        if ( v223 )
          goto LABEL_920;
        goto LABEL_913;
      }
      goto LABEL_979;
    }
    MajorFunctionCode = 0;
  }
  else
  {
    MajorFunctionCode = Srb->ScsiStatus;
  }
LABEL_920:
  if ( !MajorFunctionCode )
  {
LABEL_979:
    v249 = v348;
    if ( !v348 )
      v249 = 1;
    v348 = v249;
    goto LABEL_982;
  }
  if ( v221 != 40 )
  {
    v229 = Srb->ScsiStatus;
    goto LABEL_939;
  }
  if ( *v220 )
  {
    v229 = 0;
    goto LABEL_939;
  }
  if ( !*(_DWORD *)v352 )
    goto LABEL_79;
  v229 = 0;
  v230 = 0;
  v231 = 0;
  while ( 1 )
  {
    v232 = *((unsigned int *)&Srb[1].SenseInfoBuffer + v230);
    if ( (unsigned int)v232 >= 0x80 )
    {
      v233 = Srb->DataTransferLength;
      if ( (unsigned int)v232 < (unsigned int)v233 )
        break;
    }
LABEL_932:
    v230 = (unsigned int)(v230 + 1);
    if ( (unsigned int)v230 >= *(_DWORD *)v352 )
      goto LABEL_939;
  }
  v234 = (unsigned int)v232;
  v235 = *(_DWORD *)((char *)&Srb->Length + v232) - 64;
  if ( v235 )
  {
    v236 = v235 - 1;
    if ( !v236 )
    {
      if ( v234 + 56 <= v233 )
      {
        v229 = *(&Srb->QueueTag + v234);
        v231 = 1;
      }
LABEL_931:
      if ( v231 )
        goto LABEL_939;
      goto LABEL_932;
    }
    if ( v236 != 1 )
      goto LABEL_931;
  }
  if ( v234 + 40 > v233 )
    goto LABEL_931;
  v229 = *(&Srb->QueueTag + v234);
LABEL_939:
  v47 = v330;
  v48 = DeviceObjecta;
  if ( v229 == 8 )
  {
    *v9 = -1073741661;
    v333 = 0;
  }
LABEL_81:
  if ( FdoExtension->CommonExtension.DevInfo->ClassError )
  {
    memset(v361, 0, 0x58u);
    v49 = Srb;
    if ( Srb->Function == 40 && (FdoExtension->CommonExtension.DriverExtension->SrbSupport & 2) == 0 )
    {
      ClasspConvertToScsiRequestBlock(v361, Srb);
      v49 = (_SCSI_REQUEST_BLOCK *)v361;
    }
    FdoExtension->CommonExtension.DevInfo->ClassError(v48, v49, v9, (unsigned __int8 *)&v330 + 1);
  }
  if ( v359 )
    *v359 = v348;
  v50 = Srb->Function;
  if ( v50 != 40 )
  {
    v51 = Srb->Cdb;
    goto LABEL_996;
  }
  v51 = 0;
  if ( *v351 || !*(_DWORD *)v352 )
    goto LABEL_996;
  v52 = 0;
  v53 = 0;
  while ( 2 )
  {
    v54 = *((unsigned int *)&Srb[1].SenseInfoBuffer + v52);
    if ( (unsigned int)v54 < 0x80 )
      goto LABEL_990;
    v55 = Srb->DataTransferLength;
    if ( (unsigned int)v54 >= (unsigned int)v55 )
      goto LABEL_990;
    v56 = (unsigned int)v54;
    v57 = *(_DWORD *)((char *)&Srb->Length + v54) - 64;
    if ( v57 )
    {
      v58 = v57 - 1;
      if ( v58 )
      {
        if ( v58 == 1 && v56 + 40 <= v55 )
        {
          if ( !*(unsigned int *)((char *)&Srb->SrbFlags + v56) )
            goto LABEL_996;
          p_DataBuffer = &Srb->SenseInfoBuffer;
          goto LABEL_994;
        }
      }
      else if ( v56 + 56 <= v55 )
      {
        if ( !*(&Srb->CdbLength + v56) )
          goto LABEL_996;
        v53 = 1;
        v51 = (unsigned __int8 *)&Srb->DataBuffer + v56;
      }
LABEL_989:
      if ( v53 )
        goto LABEL_996;
LABEL_990:
      v52 = (unsigned int)(v52 + 1);
      if ( (unsigned int)v52 >= *(_DWORD *)v352 )
        goto LABEL_996;
      continue;
    }
    break;
  }
  if ( v56 + 40 > v55 )
    goto LABEL_989;
  if ( !*(&Srb->CdbLength + v56) )
    goto LABEL_996;
  p_DataBuffer = &Srb->DataBuffer;
LABEL_994:
  v51 = (unsigned __int8 *)p_DataBuffer + v56;
LABEL_996:
  if ( v51 )
  {
    v250 = *v51;
    v332 = *v51;
  }
  else
  {
    v250 = v332;
  }
  if ( (unsigned __int8)(v250 - 22) <= 1u && v51 && *v9 == -1073741808 )
  {
    if ( v50 == 40 )
    {
      if ( !*v351 )
      {
        v251 = v352;
        v252 = 0;
        for ( j = 0; (unsigned int)j < *(_DWORD *)v251; j = (unsigned int)(j + 1) )
        {
          v254 = *((unsigned int *)&Srb[1].SenseInfoBuffer + j);
          if ( (unsigned int)v254 >= 0x80 )
          {
            v255 = Srb->DataTransferLength;
            if ( (unsigned int)v254 < (unsigned int)v255 )
            {
              v256 = (unsigned int)v254;
              v257 = *(_DWORD *)((char *)&Srb->Length + v254) - 64;
              if ( v257 )
              {
                v258 = v257 - 1;
                if ( v258 )
                {
                  if ( v258 == 1 && v256 + 40 <= v255 )
                    break;
                }
                else if ( v256 + 56 <= v255 )
                {
                  v252 = 1;
                  *(&Srb->CdbLength + v256) = 10;
                }
              }
              else if ( v256 + 40 <= v255 )
              {
                *(&Srb->CdbLength + v256) = 10;
                break;
              }
              if ( v252 )
                break;
            }
          }
        }
      }
    }
    else
    {
      Srb->CdbLength = 10;
    }
    *v51 = (*v51 != 22) + 86;
    FdoExtension->PrivateFdoData->HackFlags |= 8u;
    HIBYTE(v330) = 1;
  }
  v259 = Srb->Function;
  v260 = 24;
  if ( v259 != 40 )
    v260 = 12;
  v359 = (ULONG *)v260;
  if ( (*(_DWORD *)((_BYTE *)&Srb->Length + v260) & 0x1000) != 0 )
    HIBYTE(v330) = 0;
  if ( !v339 && !v47 )
    return HIBYTE(v330);
  memset(v361, 0, 48);
  v261 = 0;
  memset(v360, 0, sizeof(v360));
  v262 = 0;
  v263 = 0;
  v350 = 0;
  v264 = 176;
  ExtraData = 0;
  if ( (Srb->SrbStatus & 0x80u) == 0 || !SenseInfoBuffer )
  {
    v274 = 18;
    goto LABEL_1072;
  }
  if ( v259 == 40 )
  {
    v265 = 0;
    if ( !*v351 && *(_DWORD *)v352 )
    {
      v266 = 0;
      v267 = 0;
      while ( 1 )
      {
        v268 = *((unsigned int *)&Srb[1].SenseInfoBuffer + v266);
        if ( (unsigned int)v268 >= 0x80 )
        {
          v269 = Srb->DataTransferLength;
          if ( (unsigned int)v268 < (unsigned int)v269 )
            break;
        }
LABEL_1040:
        v266 = (unsigned int)(v266 + 1);
        if ( (unsigned int)v266 >= *(_DWORD *)v352 )
          goto LABEL_1046;
      }
      v270 = (unsigned int)v268;
      v271 = *(_DWORD *)((char *)&Srb->Length + v268) - 64;
      if ( !v271 )
        goto LABEL_1038;
      v272 = v271 - 1;
      if ( v272 )
      {
        if ( v272 == 1 )
        {
LABEL_1038:
          if ( v270 + 40 <= v269 )
          {
            v265 = *(&Srb->QueueAction + v270);
            goto LABEL_1046;
          }
        }
      }
      else if ( v270 + 56 <= v269 )
      {
        v265 = *(&Srb->QueueAction + v270);
        v267 = 1;
      }
      if ( v267 )
        goto LABEL_1046;
      goto LABEL_1040;
    }
  }
  else
  {
    v265 = Srb->SenseInfoBufferLength;
  }
LABEL_1046:
  v273 = *SenseInfoBuffer & 0x7F;
  v274 = 18;
  if ( (unsigned __int8)(v273 - 114) <= 1u )
  {
    v262 = 18;
    if ( !v265 )
      goto LABEL_1067;
    if ( (unsigned __int8)(v273 - 114) <= 1u )
    {
      v275 = 0;
      v276 = 0;
      v277 = 0;
      if ( SenseInfoBuffer + 8 > &SenseInfoBuffer[v265] )
      {
        v278 = 0;
      }
      else
      {
        v275 = SenseInfoBuffer[1];
        v276 = SenseInfoBuffer[2];
        v277 = SenseInfoBuffer[3];
        v278 = 1;
      }
      if ( v278 )
      {
        if ( ((v273 - 112) & 0xFD) != 0 )
          v279 = ExtraData & 0x80 | 0x71;
        else
          v279 = ExtraData & 0x80 | 0x70;
        LOBYTE(ExtraData) = v279;
        v263 = 1;
        BYTE7(ExtraData) = 10;
        BYTE12(ExtraData) = v276;
        BYTE2(ExtraData) = BYTE2(ExtraData) & 0xF0 | v275 & 0xF;
        BYTE13(ExtraData) = v277;
      }
    }
  }
  if ( v265 )
  {
    v280 = 0;
    v281 = 0;
    if ( SenseInfoBuffer + 8 <= &SenseInfoBuffer[v265] )
    {
      v282 = SenseInfoBuffer[7];
      if ( v282 <= 0xF7u )
      {
        v280 = v282 + 8;
        v281 = 1;
      }
    }
    if ( v281 )
    {
      v283 = v280;
      if ( v280 <= 0x12u )
        v283 = 18;
      v261 = v265;
      if ( v283 < v265 )
        v261 = v283;
      goto LABEL_1068;
    }
  }
LABEL_1067:
  v261 = v265;
LABEL_1068:
  if ( v261 > 0x12 )
  {
    v264 = v261 + 158;
    if ( v261 + 158 > 0xF0 )
    {
      v261 = 82;
      v264 = 240;
    }
  }
LABEL_1072:
  v284 = BYTE12(v360[0]);
  if ( HIBYTE(v330) )
  {
    v284 = BYTE12(v360[0]) | 2;
    BYTE12(v360[0]) |= 2u;
  }
  else
  {
    DWORD1(v361[1]) = *v343;
  }
  v285 = v335;
  if ( (_DWORD)v335 == -2147221453 && (HIBYTE(v330) || *v343 >= 0) )
    LOBYTE(v330) = 0;
  if ( (*(_DWORD *)((_BYTE *)&Srb->Length + (_QWORD)v359) & 0x40000000) != 0 )
  {
    v284 |= 1u;
    BYTE12(v360[0]) = v284;
  }
  if ( v347 )
    BYTE12(v360[0]) = v284 | 4;
  DWORD2(v361[1]) = 0;
  DWORD2(v360[0]) = -1;
  *(_QWORD *)&v361[2] = v358 * FdoExtension->DiskGeometry.BytesPerSector;
  if ( (_DWORD)v335 == -1 )
    v285 = -1073741435;
  WORD1(v361[0]) = v264 - 48;
  LOBYTE(v361[0]) = v354;
  HIDWORD(v361[1]) = v357;
  BYTE1(v361[0]) = RetryCount;
  LODWORD(v361[1]) = v337;
  HIDWORD(v361[0]) = v285;
  v46 = Srb->Function == 40;
  *(_QWORD *)&v360[0] = MEMORY[0xFFFFF78000000320];
  if ( v46 )
  {
    ClasspConvertToScsiRequestBlock(&v360[1], Srb);
  }
  else
  {
    v286 = *(_OWORD *)&Srb->DataTransferLength;
    v360[1] = *(_OWORD *)&Srb->Length;
    v287 = *(_OWORD *)&Srb->SenseInfoBuffer;
    v360[2] = v286;
    v288 = *(_OWORD *)&Srb->OriginalRequest;
    v360[3] = v287;
    v289 = *(_OWORD *)&Srb->InternalStatus;
    v360[4] = v288;
    *(_QWORD *)&v288 = *(_QWORD *)&Srb->Cdb[8];
    v360[5] = v289;
    *(_QWORD *)&v360[6] = v288;
  }
  if ( v261 && SenseInfoBuffer )
  {
    if ( (unsigned __int8)((*SenseInfoBuffer & 0x7F) - 114) <= 1u )
    {
      if ( !v263 )
        goto LABEL_1099;
      if ( v262 < 0x12u )
        v274 = v262;
      p_ExtraData = &ExtraData;
    }
    else
    {
      if ( v261 < 0x12 )
        v274 = v261;
      p_ExtraData = (__int128 *)SenseInfoBuffer;
    }
    memmove((char *)&v360[6] + 8, p_ExtraData, v274);
  }
LABEL_1099:
  v291 = v360[7];
  v292 = v360[6];
  v293 = v360[0];
  v294 = PrivateFdoData;
  if ( v339 )
  {
    v295 = KeAcquireSpinLockRaiseToDpc(&PrivateFdoData->SpinLock);
    v296 = v360[1];
    v297 = v360[2];
    v298 = (unsigned __int64)v294->ErrorLogNextIndex << 7;
    *(_OWORD *)((char *)&v294->ErrorLogs[0].TickCount.LowPart + v298) = v293;
    *(_OWORD *)((char *)&v294->ErrorLogs[0].Srb.Length + v298) = v296;
    v299 = v360[3];
    *(_OWORD *)((char *)&v294->ErrorLogs[0].Srb.DataTransferLength + v298) = v297;
    v300 = v360[4];
    *(_OWORD *)((char *)&v294->ErrorLogs[0].Srb.SenseInfoBuffer + v298) = v299;
    v301 = v360[5];
    *(_OWORD *)((char *)&v294->ErrorLogs[0].Srb.OriginalRequest + v298) = v300;
    *(_OWORD *)((char *)&v294->ErrorLogs[0].Srb.InternalStatus + v298) = v301;
    *(_OWORD *)&v294->ErrorLogs[0].Srb.Cdb[v298 + 8] = v292;
    *(_OWORD *)&v294->ErrorLogs[0].SenseData.CommandSpecificInformation[v298] = v291;
    v294->ErrorLogNextIndex = ((unsigned __int8)v294->ErrorLogNextIndex + 1) & 0xF;
    KeReleaseSpinLock(&v294->SpinLock, v295);
  }
  if ( ((v332 - 8) & 0x5D) != 0 || !HIBYTE(v330) || RetryCount )
  {
    v302 = 0;
    goto LABEL_1107;
  }
  v302 = v333;
  if ( !v333 )
  {
LABEL_1107:
    if ( !(_BYTE)v330 )
      return HIBYTE(v330);
  }
  if ( Srb->Function != 40 )
  {
    v303 = Srb->Cdb;
    goto LABEL_1131;
  }
  v303 = 0;
  if ( !*v351 && *(_DWORD *)v352 )
  {
    v304 = 0;
    v305 = 0;
    do
    {
      v306 = *((unsigned int *)&Srb[1].SenseInfoBuffer + v304);
      if ( (unsigned int)v306 >= 0x80 )
      {
        v307 = Srb->DataTransferLength;
        if ( (unsigned int)v306 < (unsigned int)v307 )
        {
          v308 = (unsigned int)v306;
          v309 = *(_DWORD *)((char *)&Srb->Length + v306) - 64;
          if ( v309 )
          {
            v310 = v309 - 1;
            if ( v310 )
            {
              if ( v310 == 1 && v308 + 40 <= v307 )
              {
                if ( !*(unsigned int *)((char *)&Srb->SrbFlags + v308) )
                  break;
                v311 = &Srb->SenseInfoBuffer;
                goto LABEL_1129;
              }
            }
            else if ( v308 + 56 <= v307 )
            {
              if ( !*(&Srb->CdbLength + v308) )
                break;
              v305 = 1;
              v303 = (unsigned __int8 *)&Srb->DataBuffer + v308;
            }
          }
          else if ( v308 + 40 <= v307 )
          {
            if ( !*(&Srb->CdbLength + v308) )
              break;
            v311 = &Srb->DataBuffer;
LABEL_1129:
            v303 = (unsigned __int8 *)v311 + v308;
            break;
          }
          if ( v305 )
            break;
        }
      }
      v304 = (unsigned int)(v304 + 1);
    }
    while ( (unsigned int)v304 < *(_DWORD *)v352 );
  }
LABEL_1131:
  if ( v303 )
  {
    if ( *v303 )
    {
      if ( *v303 == 53 )
      {
        if ( v294->LoggedSYNCFailure )
          return HIBYTE(v330);
        v294->LoggedSYNCFailure = 1;
      }
    }
    else
    {
      if ( v294->LoggedTURFailureSinceLastIO )
        return HIBYTE(v330);
      v294->LoggedTURFailureSinceLastIO = 1;
    }
  }
  if ( v302 )
  {
    if ( Srb->Function == 40 )
    {
      v312 = 0;
      if ( !*v351 && *(_DWORD *)v352 )
      {
        v313 = 0;
        v314 = 0;
        while ( 1 )
        {
          v315 = *((unsigned int *)&Srb[1].SenseInfoBuffer + v313);
          if ( (unsigned int)v315 >= 0x80 )
          {
            v316 = Srb->DataTransferLength;
            if ( (unsigned int)v315 < (unsigned int)v316 )
              break;
          }
LABEL_1150:
          v313 = (unsigned int)(v313 + 1);
          if ( (unsigned int)v313 >= *(_DWORD *)v352 )
            goto LABEL_1156;
        }
        v317 = (unsigned int)v315;
        v318 = *(_DWORD *)((char *)&Srb->Length + v315) - 64;
        if ( !v318 )
          goto LABEL_1148;
        v319 = v318 - 1;
        if ( v319 )
        {
          if ( v319 == 1 )
          {
LABEL_1148:
            if ( v317 + 40 <= v316 )
            {
              v312 = *(&Srb->QueueTag + v317);
              goto LABEL_1156;
            }
          }
        }
        else if ( v317 + 56 <= v316 )
        {
          v312 = *(&Srb->QueueTag + v317);
          v314 = 1;
        }
        if ( v314 )
          goto LABEL_1156;
        goto LABEL_1150;
      }
    }
    else
    {
      v312 = Srb->ScsiStatus;
    }
LABEL_1156:
    ClasspQueueLogIOEventWithContextWorker(DeviceObjecta, v261, v312, -2147221351, v356, (__int64)v303, 0);
  }
  else
  {
    ErrorLogEntry = IoAllocateErrorLogEntry(DeviceObjecta, v264);
    v321 = ErrorLogEntry;
    if ( ErrorLogEntry )
    {
      v322 = v361[1];
      *ErrorLogEntry = v361[0];
      v323 = v361[2];
      ErrorLogEntry[1] = v322;
      v324 = v360[2];
      ErrorLogEntry[2] = v323;
      v325 = v360[1];
      *(_OWORD *)((char *)ErrorLogEntry + 40) = v293;
      *(_OWORD *)((char *)ErrorLogEntry + 56) = v325;
      v326 = v360[3];
      *(_OWORD *)((char *)ErrorLogEntry + 72) = v324;
      v327 = v360[4];
      *(_OWORD *)((char *)ErrorLogEntry + 88) = v326;
      v328 = v360[5];
      *(_OWORD *)((char *)ErrorLogEntry + 104) = v327;
      *(_OWORD *)((char *)ErrorLogEntry + 120) = v328;
      *(_OWORD *)((char *)ErrorLogEntry + 136) = v292;
      *(_OWORD *)((char *)ErrorLogEntry + 152) = v291;
      if ( v261 && SenseInfoBuffer )
        memmove(ErrorLogEntry + 9, SenseInfoBuffer, v261);
      IoWriteErrorLogEntry(v321);
    }
  }
  return HIBYTE(v330);
}

```

## disassembly

```asm
0x1400084b0  mov     rax, rsp
0x1400084b3  mov     [rax+18h], rbx
0x1400084b7  push    rbp
0x1400084b8  push    rsi
0x1400084b9  push    rdi
0x1400084ba  push    r12
0x1400084bc  push    r13
0x1400084be  push    r14
0x1400084c0  push    r15
0x1400084c2  lea     rbp, [rax-158h]
0x1400084c9  sub     rsp, 220h
0x1400084d0  movaps  xmmword ptr [rax-48h], xmm6
0x1400084d4  movaps  xmmword ptr [rax-58h], xmm7
0x1400084d8  movaps  xmmword ptr [rax-68h], xmm8
0x1400084dd  mov     rax, cs:__security_cookie
0x1400084e4  xor     rax, rsp
0x1400084e7  mov     [rbp+150h+var_70], rax
0x1400084ee  mov     bl, [rdx+2]
0x1400084f1  lea     rdi, [rdx+14h]
0x1400084f5  mov     r14, [rbp+150h+Status]
0x1400084fc  mov     rax, rcx
0x1400084ff  mov     [rsp+250h+DeviceObject], rcx
0x140008504  lea     rsi, [rdx+38h]
0x140008508  mov     rcx, [rbp+150h+RetryInterval]
0x14000850f  mov     r12, rdx
0x140008512  mov     [rbp+150h+var_164], r9d
0x140008516  mov     r15d, 1
0x14000851c  mov     rax, [rax+40h]
0x140008520  mov     [rbp+150h+FdoExtension], rax
0x140008524  mov     [rbp+150h+var_178], r8b
0x140008528  mov     [rbp+150h+var_1C0], r14
0x14000852c  mov     rax, [rax+478h]
0x140008533  mov     [rbp+150h+var_170], rax
0x140008537  mov     [rbp+150h+var_158], rcx
0x14000853b  mov     [rbp+150h+var_190], rdi
0x14000853f  mov     [rbp+150h+var_188], rsi
0x140008543  cmp     bl, 28h ; '('
0x140008546  jnz     loc_1400085E6
0x14000854c  xor     r13d, r13d
0x14000854f  mov     [rbp+150h+var_1C8], r13
0x140008553  cmp     [rdi], r13d
0x140008556  jnz     loc_1400085E0
0x14000855c  mov     r11d, [rsi]
0x14000855f  test    r11d, r11d
0x140008562  jz      loc_1400085F6
0x140008568  xor     r9d, r9d
0x14000856b  xor     r10b, r10b
0x14000856e  mov     ecx, [r12+r9*4+78h]
0x140008573  cmp     ecx, 80h
0x140008579  jb      short loc_1400085CF
0x14000857b  mov     r8d, [r12+10h]
0x140008580  cmp     ecx, r8d
0x140008583  jnb     short loc_1400085CF
0x140008585  mov     edx, ecx
0x140008587  mov     ecx, [rcx+r12]
0x14000858b  sub     ecx, 40h ; '@'
0x14000858e  jz      short loc_1400085C1
0x140008590  sub     ecx, r15d
0x140008593  jz      short loc_1400085AA
0x140008595  cmp     ecx, r15d
0x140008598  jnz     short loc_1400085CA
0x14000859a  lea     rcx, [rdx+28h]
0x14000859e  cmp     rcx, r8
0x1400085a1  ja      short loc_1400085CA
0x1400085a3  mov     r13, [rdx+r12+18h]
0x1400085a8  jmp     short loc_1400085F2
0x1400085aa  lea     rcx, [rdx+38h]
0x1400085ae  cmp     rcx, r8
0x1400085b1  ja      short loc_1400085CA
0x1400085b3  mov     r13, [rdx+r12+10h]
0x1400085b8  mov     r10b, r15b
0x1400085bb  mov     [rbp+150h+var_1C8], r13
0x1400085bf  jmp     short loc_1400085CA
0x1400085c1  lea     rcx, [rdx+28h]
0x1400085c5  cmp     rcx, r8
0x1400085c8  jbe     short loc_1400085D9
0x1400085ca  test    r10b, r10b
0x1400085cd  jnz     short loc_1400085F6
0x1400085cf  add     r9d, r15d
0x1400085d2  cmp     r9d, r11d
0x1400085d5  jb      short loc_14000856E
0x1400085d7  jmp     short loc_1400085F6
0x1400085d9  mov     r13, [rdx+r12+10h]
0x1400085de  jmp     short loc_1400085F2
0x1400085e0  mov     [rbp+150h+var_188], rsi
0x1400085e4  jmp     short loc_1400085F6
0x1400085e6  mov     r13, [rdx+20h]
0x1400085ea  mov     [rbp+150h+var_190], rdi
0x1400085ee  mov     [rbp+150h+var_188], rsi
0x1400085f2  mov     [rbp+150h+var_1C8], r13
0x1400085f6  mov     byte ptr [rsp+250h+var_200+1], r15b
0x1400085fb  mov     [rbp+150h+var_1AF], 0
0x1400085ff  mov     byte ptr [rsp+250h+var_200+4], r15b
0x140008604  mov     byte ptr [rsp+250h+var_1E0+5], r15b
0x140008609  mov     [rbp+150h+var_160], 0
0x140008611  mov     [rbp+150h+var_1D0], 0
0x140008618  mov     [rbp+150h+var_1AC], 0
0x14000861f  cmp     bl, 28h ; '('
0x140008622  jnz     loc_140008781
0x140008628  xor     ebx, ebx
0x14000862a  mov     [rsp+250h+var_1E8], rbx
0x14000862f  cmp     [rdi], ebx
0x140008631  jnz     loc_140008745
0x140008637  mov     r11d, [r12+38h]
0x14000863c  test    r11d, r11d
0x14000863f  jz      loc_140008745
0x140008645  xor     r9d, r9d
0x140008648  xor     r10b, r10b
0x14000864b  mov     ecx, [r12+r9*4+78h]
0x140008650  cmp     ecx, 80h
0x140008656  jb      short loc_1400086C8
0x140008658  mov     r8d, [r12+10h]
0x14000865d  cmp     ecx, r8d
0x140008660  jnb     short loc_1400086C8
0x140008662  mov     edx, ecx
0x140008664  mov     ecx, [r12+rcx]
0x140008668  sub     ecx, 40h ; '@'
0x14000866b  jz      short loc_1400086BA
0x14000866d  sub     ecx, r15d
0x140008670  jz      short loc_140008697
0x140008672  cmp     ecx, r15d
0x140008675  jnz     short loc_1400086C3
0x140008677  lea     rcx, [rdx+28h]
0x14000867b  cmp     rcx, r8
0x14000867e  ja      short loc_1400086C3
0x140008680  cmp     dword ptr [r12+rdx+0Ch], 0
0x140008686  jbe     short loc_1400086D4
0x140008688  lea     r15, [r12+20h]
0x14000868d  add     r15, rdx
0x140008690  mov     [rsp+250h+var_1E8], r15
0x140008695  jmp     short loc_1400086D9
0x140008697  lea     rcx, [rdx+38h]
0x14000869b  cmp     rcx, r8
0x14000869e  ja      short loc_1400086C3
0x1400086a0  cmp     byte ptr [r12+rdx+0Ah], 0
0x1400086a6  jbe     short loc_1400086D4
0x1400086a8  lea     rbx, [r12+18h]
0x1400086ad  mov     r10b, r15b
0x1400086b0  add     rbx, rdx
0x1400086b3  mov     [rsp+250h+var_1E8], rbx
0x1400086b8  jmp     short loc_1400086C3
0x1400086ba  lea     rcx, [rdx+28h]
0x1400086be  cmp     rcx, r8
0x1400086c1  jbe     short loc_140008733
0x1400086c3  test    r10b, r10b
0x1400086c6  jnz     short loc_1400086D4
0x1400086c8  add     r9d, r15d
0x1400086cb  cmp     r9d, r11d
0x1400086ce  jb      loc_14000864B
0x1400086d4  mov     r15, [rsp+250h+var_1E8]
0x1400086d9  xor     r8b, r8b
0x1400086dc  cmp     dword ptr [rdi], 0
0x1400086df  jnz     loc_14000877A
0x1400086e5  mov     r11d, [r12+38h]
0x1400086ea  test    r11d, r11d
0x1400086ed  jz      loc_14000877A
0x1400086f3  xor     r10d, r10d
0x1400086f6  xor     bl, bl
0x1400086f8  mov     byte ptr [rsp+250h+var_200+3], bl
0x1400086fc  mov     ecx, [r12+r10*4+78h]
0x140008701  cmp     ecx, 80h
0x140008707  jb      short loc_140008769
0x140008709  mov     r9d, [r12+10h]
0x14000870e  cmp     ecx, r9d
0x140008711  jnb     short loc_140008769
0x140008713  mov     edx, ecx
0x140008715  mov     ecx, [r12+rcx]
0x140008719  sub     ecx, 40h ; '@'
0x14000871c  jz      short loc_14000875C
0x14000871e  sub     ecx, 1
0x140008721  jz      short loc_14000874A
0x140008723  cmp     ecx, 1
0x140008726  jnz     short loc_140008765
0x140008728  lea     rcx, [rdx+28h]
0x14000872c  cmp     rcx, r9
0x14000872f  ja      short loc_140008765
0x140008731  jmp     short loc_140008795
0x140008733  cmp     byte ptr [r12+rdx+0Ah], 0
0x140008739  jbe     short loc_1400086D4
0x14000873b  lea     r15, [r12+18h]
0x140008740  jmp     loc_14000868D
0x140008745  mov     r15, rbx
0x140008748  jmp     short loc_1400086D9
0x14000874a  lea     rcx, [rdx+38h]
0x14000874e  cmp     rcx, r9
0x140008751  ja      short loc_140008765
0x140008753  mov     r8b, [r12+rdx+0Ah]
0x140008758  mov     bl, 1
0x14000875a  jmp     short loc_140008765
0x14000875c  lea     rcx, [rdx+28h]
0x140008760  cmp     rcx, r9
0x140008763  jbe     short loc_140008773
0x140008765  test    bl, bl
0x140008767  jnz     short loc_140008795
0x140008769  inc     r10d
0x14000876c  cmp     r10d, r11d
0x14000876f  jb      short loc_1400086FC
0x140008771  jmp     short loc_140008795
0x140008773  mov     r8b, [r12+rdx+0Ah]
0x140008778  jmp     short loc_140008795
0x14000877a  mov     byte ptr [rsp+250h+var_200+3], r8b
0x14000877f  jmp     short loc_140008790
0x140008781  mov     r8b, [r12+0Ah]
0x140008786  lea     r15, [r12+48h]
0x14000878b  mov     byte ptr [rsp+250h+var_200+3], 0
0x140008790  mov     [rsp+250h+var_1E8], r15
0x140008795  movzx   eax, r8b
0x140008799  mov     [rbp+150h+var_168], eax
0x14000879c  test    r15, r15
0x14000879f  jz      short loc_1400087A8
0x1400087a1  mov     al, [r15]
0x1400087a4  mov     byte ptr [rsp+250h+var_200+3], al
0x1400087a8  mov     dword ptr [r14], 0C0000185h
0x1400087af  mov     eax, 18h
0x1400087b4  mov     dl, [r12+2]
0x1400087b9  movzx   edi, byte ptr [r12+3]
0x1400087bf  cmp     dl, 28h ; '('
0x1400087c2  lea     ecx, [rax-0Ch]
0x1400087c5  cmovnz  eax, ecx
0x1400087c8  mov     ecx, [rax+r12]
0x1400087cc  and     ecx, 40000000h
0x1400087d2  mov     eax, ecx
0x1400087d4  neg     eax
0x1400087d6  mov     eax, ecx
0x1400087d8  sbb     r9d, r9d
0x1400087db  and     r9d, 80040034h
0x1400087e2  dec     r9d
0x1400087e5  neg     eax
0x1400087e7  mov     dword ptr [rsp+250h+var_1F0], r9d
0x1400087ec  mov     eax, edi
0x1400087ee  sbb     r10d, r10d
0x1400087f1  and     r10d, 12Dh
0x1400087f8  test    ecx, ecx
0x1400087fa  mov     dword ptr [rsp+250h+var_1E0], r10d
0x1400087ff  setnz   r8b
0x140008803  and     eax, 0FFFFFF3Fh
0x140008808  mov     byte ptr [rsp+250h+var_200], r8b
0x14000880d  cmp     al, 30h ; '0'
0x14000880f  jnz     loc_14000899B
0x140008815  mov     rcx, cs:WPP_GLOBAL_Control
0x14000881c  lea     rsi, WPP_GLOBAL_Control
0x140008823  mov     ebx, 2Ch ; ','
0x140008828  cmp     rcx, rsi
0x14000882b  jz      short loc_14000885E
0x14000882d  mov     eax, [rcx+2Ch]
0x140008830  test    al, 1
0x140008832  jz      short loc_14000885E
0x140008834  cmp     byte ptr [rcx+29h], 2
0x140008838  jb      short loc_14000885E
0x14000883a  mov     rcx, [rcx+18h]
0x14000883e  lea     eax, [rbx+14h]
0x140008841  cmp     dl, 28h ; '('
0x140008844  lea     r8, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids
0x14000884b  mov     r9d, ebx
0x14000884e  lea     edx, [rbx+20h]
0x140008851  cmovnz  r9d, eax
0x140008855  mov     r9d, [r9+r12]
0x140008859  call    WPP_SF_d
0x14000885e  cmp     byte ptr [r12+2], 28h ; '('
0x140008864  mov     eax, 40h ; '@'
0x140008869  mov     byte ptr [rsp+250h+var_200+1], 0
0x14000886e  cmovnz  rbx, rax
0x140008872  mov     eax, [rbx+r12]
0x140008876  mov     [r14], eax
0x140008879  mov     sil, byte ptr [rsp+250h+var_200]
0x14000887e  mov     rdi, [rsp+250h+DeviceObject]
0x140008883  mov     rax, [rbp+150h+FdoExtension]
0x140008887  mov     rax, [rax+0A0h]
0x14000888e  cmp     qword ptr [rax+10h], 0
0x140008893  jz      short loc_1400088F7
0x140008895  xor     edx, edx; Val
0x140008897  lea     rcx, [rbp+150h+var_D0]; void *
0x14000889e  lea     r8d, [rdx+58h]; Size
0x1400088a2  call    memset
0x1400088a7  cmp     byte ptr [r12+2], 28h ; '('
0x1400088ad  mov     rdx, r12
0x1400088b0  jnz     short loc_1400088D8
0x1400088b2  mov     rax, [rbp+150h+FdoExtension]
0x1400088b6  mov     rax, [rax+20h]
0x1400088ba  mov     ecx, [rax+388h]
0x1400088c0  test    cl, 2
0x1400088c3  jnz     short loc_1400088D8
0x1400088c5  lea     rcx, [rbp+150h+var_D0]
0x1400088cc  call    ClasspConvertToScsiRequestBlock
0x1400088d1  lea     rdx, [rbp+150h+var_D0]
0x1400088d8  mov     rax, [rbp+150h+FdoExtension]
0x1400088dc  lea     r9, [rsp+250h+var_200+1]
0x1400088e1  mov     r8, r14
0x1400088e4  mov     rcx, rdi
0x1400088e7  mov     rax, [rax+0A0h]
0x1400088ee  mov     rax, [rax+10h]
0x1400088f2  call    _guard_dispatch_icall
0x1400088f7  mov     rcx, [rbp+150h+var_158]
0x1400088fb  test    rcx, rcx
0x1400088fe  jz      short loc_140008905
0x140008900  mov     eax, [rbp+150h+var_1AC]
0x140008903  mov     [rcx], eax
0x140008905  mov     dil, [r12+2]
0x14000890a  mov     r15, [rbp+150h+var_190]
0x14000890e  cmp     dil, 28h ; '('
  ... truncated ...
```
