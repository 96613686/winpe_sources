# CscCreate

- ea: `0x140062b70`
- end: `0x1400683a4`
- name: `CscCreate`
- size: `22580`
- prototype: `__int64 __fastcall(PRX_CONTEXT RxContext)`
- caller_count: `0`
- callee_count: `95`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1400017c0`
- `0x140003a00`
- `0x14000492c`
- `0x140004e6c`
- `0x14000a4f0`
- `0x14000a634`
- `0x14000dedc`
- `0x14000dfc0`
- `0x14000e030`
- `0x14000e100`
- `0x14000f460`
- `0x14000f890`
- `0x14000f8b0`
- `0x140010040`
- `0x140010180`
- `0x1400109e0`
- `0x140010ae8`
- `0x1400111f8`
- `0x1400119d0`
- `0x140012118`
- `0x1400125ec`
- `0x140012838`
- `0x1400128b0`
- `0x140012c48`
- `0x140012dc8`
- `0x14001328c`
- `0x140013324`
- `0x140013614`
- `0x14001362c`
- `0x14001404c`
- `0x140014da4`
- `0x1400169d4`
- `0x140016a04`
- `0x140018930`
- `0x140018b50`
- `0x140018fd0`
- `0x1400190ec`
- `0x140019140`
- `0x1400197a0`
- `0x14001a494`
- `0x14001a624`
- `0x14001ac1c`
- `0x14001b568`
- `0x14001b710`
- `0x14001baf4`
- `0x14001bb14`
- `0x14001c008`
- `0x14001c214`
- `0x14001c33c`
- `0x14001c460`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x1400631b5`
- `ntoskrnl!ExAllocatePool2` at `0x1400631b5`
- `ntoskrnl!SeTokenIsAdmin` at `0x140064884`
- `ntoskrnl!SeTokenIsAdmin` at `0x140064884`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140063965`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140063965`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140066ab3`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140066ab3`
- `rdbss!RxCreateNetFobx` at `0x140065b5d`
- `rdbss!RxCreateNetFobx` at `0x140065b5d`
- `rdbss!RxSubjectContextFromRxContext` at `0x14006378b`
- `rdbss!RxSubjectContextFromRxContext` at `0x14006378b`
- `rdbss!RxFinishFcbInitialization` at `0x140065b40`
- `rdbss!RxFinishFcbInitialization` at `0x140065b40`
- `rdbss!RxSidFromRxContext` at `0x140063000`
- `rdbss!RxSidFromRxContext` at `0x140063000`
- `rdbss!RxSetBasicInfoInFcb` at `0x14006782a`
- `rdbss!RxSetBasicInfoInFcb` at `0x14006782a`
- `rdbss!RxSetFcbDispatchTable` at `0x14006315f`
- `rdbss!RxSetFcbDispatchTable` at `0x14006315f`
- `rdbss!RxInitNetInfoFromFcb` at `0x140063e9a`
- `rdbss!RxInitNetInfoFromFcb` at `0x140063e9a`

## string_xrefs

- `0x14006711c`: `dirty deleted`

## pseudocode

```c
__int64 __fastcall CscCreate(PRX_CONTEXT RxContext)
{
  PMRX_FCB pFcb; // r14
  __int64 v3; // rax
  PNON_PAGED_FCB NonPagedFcb; // rcx
  unsigned __int8 v5; // al
  unsigned int Blink; // ebx
  unsigned __int8 v7; // si
  ULONG PipeCompletionMode; // eax
  int inited; // r12d
  char *v10; // rdx
  char v11; // al
  _QWORD *v12; // r15
  unsigned __int8 *v13; // rdi
  char v14; // al
  __int64 Buffer; // rdx
  signed __int64 v16; // rbx
  __int64 v17; // rdi
  _QWORD *v18; // rbx
  char v19; // dl
  int v20; // r9d
  PMRX_SRV_OPEN v21; // rbx
  unsigned __int64 v22; // r8
  __int64 Timer_high; // rcx
  char v24; // al
  __int64 v25; // rax
  __int64 v26; // r9
  unsigned __int8 v27; // al
  __int64 v28; // rax
  __int64 v29; // rcx
  unsigned __int8 v30; // al
  char v31; // al
  int v32; // eax
  char v33; // cl
  unsigned int v34; // eax
  __int64 v35; // rax
  int v36; // ebx
  ULONG v37; // eax
  int v38; // ecx
  struct _UNICODE_STRING *Pool2; // rax
  PMRX_SRV_OPEN v40; // rbx
  char v41; // dl
  char v42; // cl
  __int64 v43; // rax
  __int64 v44; // rax
  char v45; // r11
  char v46; // r10
  char v47; // r8
  char v48; // cl
  __int64 v49; // r8
  int v50; // eax
  int v51; // ebx
  __int64 v52; // rax
  char v53; // cl
  PMRX_SRV_OPEN v54; // rbx
  int v55; // eax
  signed __int64 v56; // rax
  int v57; // ebx
  __int64 v58; // r8
  int v59; // edi
  char *v60; // rcx
  char v61; // al
  unsigned __int8 v62; // bl
  char HasStoreEntry; // al
  __int64 v64; // rax
  int v65; // ebx
  int v66; // ebx
  PVOID *p_EaBuffer; // rsi
  int v68; // eax
  PMRX_SRV_OPEN v69; // rdi
  __int64 v70; // r9
  __int64 v71; // rcx
  int PagingIoResource; // ecx
  __int64 v74; // rax
  __int64 v75; // r9
  __int64 v76; // r8
  int v77; // edi
  __int64 v78; // r8
  __int64 v79; // r9
  PDEVICE_OBJECT v80; // rcx
  __int64 v81; // rax
  bool v82; // si
  __int64 v83; // rbx
  int v84; // eax
  __int64 v85; // rax
  int v86; // edx
  __int64 v87; // rax
  __int64 v88; // rcx
  char v89; // al
  char v90; // cl
  __int64 v91; // rax
  int InformationEntry; // eax
  unsigned __int8 v93; // cl
  int v94; // eax
  __int64 v95; // r8
  unsigned __int64 v96; // r9
  int v97; // eax
  bool v98; // dl
  unsigned __int8 v99; // cl
  unsigned __int8 v100; // cl
  __int64 v101; // rax
  int SlashDotOpen; // eax
  int v103; // eax
  bool v104; // zf
  __int64 v105; // rcx
  char v106; // al
  __int64 v107; // rcx
  ULONG v108; // eax
  int v109; // ecx
  int v110; // ecx
  int v111; // eax
  int v112; // eax
  unsigned int v113; // eax
  int v114; // r9d
  char v115; // cl
  unsigned __int8 v116; // r8
  bool v117; // cl
  __int64 v118; // rax
  __int64 v119; // rax
  ULONG v120; // eax
  int v121; // ecx
  char IsRootGhosted; // di
  char v123; // dl
  int CanSidDecryptEntry; // eax
  int v125; // ebx
  ULONG v126; // eax
  int v127; // ecx
  PMRX_SRV_OPEN v128; // r11
  ULONG v129; // eax
  int v130; // ecx
  int v131; // ecx
  __int64 v132; // rdx
  void *v133; // rcx
  PMRX_SRV_OPEN v134; // r10
  bool v135; // dl
  unsigned __int8 v136; // al
  char v137; // cl
  __int64 p_Context2; // rax
  int v139; // eax
  __int64 v140; // r8
  PMRX_SRV_OPEN v141; // rsi
  int v142; // eax
  _BYTE *v143; // rdx
  int v144; // edx
  unsigned int v145; // esi
  int v146; // eax
  char v147; // si
  int v148; // ecx
  int v149; // eax
  unsigned __int8 v150; // al
  char v151; // al
  char v152; // r8
  __int64 v153; // r9
  char v154; // r8
  char v155; // r11
  char v156; // r10
  char v157; // cl
  char v158; // r8
  char v159; // cl
  unsigned int v160; // r8d
  int v161; // eax
  unsigned int v162; // eax
  int v163; // r9d
  int v164; // eax
  int v165; // ecx
  char v166; // al
  int v167; // eax
  __int64 v168; // rcx
  int v169; // eax
  char v170; // al
  int v171; // eax
  ULONG v172; // eax
  char v173; // al
  int v174; // eax
  __int64 v175; // r9
  char v176; // al
  __int64 v177; // rdx
  int v178; // ecx
  ULONG v179; // ecx
  __int64 v180; // rax
  PVOID v181; // rdx
  __int64 v182; // rcx
  __int64 v183; // r8
  struct _LIST_ENTRY *v184; // rax
  struct _MRX_FOBX_ *NetFobx; // rax
  ULONG v186; // ecx
  RX_FCBTRACKER_CALLINFO *v187; // rbx
  char *v188; // rdx
  int v189; // eax
  __int64 v190; // r8
  __int64 v191; // r9
  __int64 v192; // rcx
  char *v193; // r8
  int v194; // eax
  bool v195; // si
  int v196; // eax
  int v197; // eax
  char v198; // al
  unsigned __int8 v199; // di
  __int64 v200; // rsi
  char v201; // bl
  char GlobalNewlyCachedEpoch; // al
  char v203; // r14
  char v204; // r8
  char v205; // cl
  char v206; // r11
  char v207; // r10
  char v208; // bl
  int v209; // r9d
  __int64 v210; // rax
  int v211; // eax
  char v212; // al
  PDEVICE_OBJECT v213; // rcx
  __int64 v214; // rdx
  ULONG v215; // eax
  int v216; // r8d
  int v217; // eax
  __int64 v218; // rax
  __int64 v219; // r9
  int v220; // eax
  unsigned int v221; // eax
  char v222; // al
  int v223; // r8d
  int v224; // ecx
  __int64 v225; // rdx
  int v226; // eax
  __int64 v227; // rdx
  int v228; // ecx
  PDEVICE_OBJECT v229; // rcx
  __int64 v230; // rdx
  int v231; // eax
  _OWORD *v232; // rax
  int v233; // eax
  ULONG v234; // eax
  const char *v235; // r9
  int v236; // eax
  int v237; // eax
  __int64 v238; // rcx
  int v239; // eax
  _DWORD *v240; // rax
  int v241; // eax
  ULONG v242; // eax
  int v243; // eax
  __int64 v244; // rcx
  int Blink_high; // eax
  __int64 v246; // rax
  __int64 v247; // r10
  ULONG AcquireRelease; // eax
  char v249; // al
  char *v250; // rdx
  _OWORD *v251; // rax
  int v252; // eax
  char *v253; // r9
  char v254; // al
  _BYTE *v255; // r8
  __int64 v256; // rdx
  __int64 v257; // rcx
  int v258; // eax
  int DatabaseInformation; // eax
  char v260; // cl
  __int64 v261; // rax
  __int64 v262; // rax
  int v263; // eax
  __int64 v264; // rax
  int v265; // eax
  unsigned int v266; // edi
  struct _LIST_ENTRY *Flink; // rax
  int v268; // eax
  char v269; // [rsp+20h] [rbp-110h]
  int v270; // [rsp+20h] [rbp-110h]
  int String2; // [rsp+28h] [rbp-108h]
  int v272; // [rsp+30h] [rbp-100h]
  char v273; // [rsp+A0h] [rbp-90h]
  PVOID Entry; // [rsp+B0h] [rbp-80h] BYREF
  unsigned __int8 v275; // [rsp+B8h] [rbp-78h] BYREF
  _BYTE v276[15]; // [rsp+B9h] [rbp-77h] BYREF
  struct _LIST_ENTRY *v277; // [rsp+C8h] [rbp-68h] BYREF
  __int64 v278; // [rsp+D0h] [rbp-60h] BYREF
  PMRX_SRV_OPEN MrxSrvOpen; // [rsp+D8h] [rbp-58h]
  char v280; // [rsp+E0h] [rbp-50h] BYREF
  unsigned __int8 v281; // [rsp+E1h] [rbp-4Fh] BYREF
  char v282; // [rsp+E2h] [rbp-4Eh]
  int updated; // [rsp+E4h] [rbp-4Ch] BYREF
  char v284; // [rsp+E8h] [rbp-48h]
  unsigned int v285; // [rsp+ECh] [rbp-44h] BYREF
  unsigned int v286; // [rsp+F0h] [rbp-40h]
  unsigned int v287; // [rsp+F4h] [rbp-3Ch]
  char v288; // [rsp+F8h] [rbp-38h] BYREF
  char v289; // [rsp+F9h] [rbp-37h] BYREF
  char v290; // [rsp+FAh] [rbp-36h] BYREF
  unsigned int v291; // [rsp+FCh] [rbp-34h]
  __int64 v292; // [rsp+100h] [rbp-30h] BYREF
  __int64 v293; // [rsp+108h] [rbp-28h] BYREF
  PMRX_FCB v294; // [rsp+110h] [rbp-20h] BYREF
  __int64 v295; // [rsp+118h] [rbp-18h]
  ULONG v296; // [rsp+120h] [rbp-10h]
  PSZ *p_FileName; // [rsp+128h] [rbp-8h]
  UNICODE_STRING String1; // [rsp+130h] [rbp+0h] BYREF
  int v299[4]; // [rsp+140h] [rbp+10h] BYREF
  _DWORD v300[20]; // [rsp+150h] [rbp+20h] BYREF

  pFcb = RxContext->pFcb;
  MrxSrvOpen = RxContext->pRelevantSrvOpen;
  v294 = pFcb;
  v295 = *(_QWORD *)(*(_QWORD *)&pFcb->UncleanCount + 32LL);
  v3 = *(_QWORD *)&RxContext->TrackerHistory[0].Flags;
  NonPagedFcb = RxContext->NonPagedFcb;
  v293 = v3;
  v277 = 0;
  String1 = 0;
  v5 = CscProcessRequestAsFilter(NonPagedFcb);
  Blink = (unsigned int)RxContext->WorkQueueItem.List.Blink;
  v7 = v5;
  v275 = v5;
  PipeCompletionMode = RxContext->Create.PipeCompletionMode;
  *(_OWORD *)v299 = 0;
  v296 = PipeCompletionMode;
  Entry = 0;
  LODWORD(v278) = 0;
  v285 = Blink;
  v292 = 0;
  inited = CscAllocateCreateContext(&Entry);
  if ( inited < 0 )
  {
    v66 = 4752;
    goto LABEL_192;
  }
  v10 = (char *)Entry;
  p_FileName = &RxContext->TrackerHistory[7].FileName;
  *(_DWORD *)&v276[3] = 0;
  v11 = *((_BYTE *)Entry + 533) & 0xFD;
  v291 = 0;
  v282 = 0;
  *((_BYTE *)Entry + 533) = v11 | (Blink >> 2) & 2;
  v284 = 0;
  v12 = v10 + 344;
  v286 = Blink;
  *((_BYTE *)Entry + 533) = *((_BYTE *)Entry + 533) & 0xF7 | (Blink >> 1) & 8;
  *((_BYTE *)Entry + 533) = *((_BYTE *)Entry + 533) & 0xEF | (4 * (Blink & 4));
  *((_BYTE *)Entry + 533) = *((_BYTE *)Entry + 533) & 0xDF | (Blink >> 11) & 0x20;
  *((_BYTE *)Entry + 533) = *((_BYTE *)Entry + 533) & 0xBF | (2 * (Blink & 0x20));
  *((_BYTE *)Entry + 533) = *((_BYTE *)Entry + 533) & 0x7F | (Blink >> 2) & 0x80;
  *((_BYTE *)Entry + 534) = *((_BYTE *)Entry + 534) & 0xFE | ((Blink & 0x400) != 0);
  *((_BYTE *)Entry + 534) = *((_BYTE *)Entry + 534) & 0xFD | (Blink >> 10) & 2;
  *((_BYTE *)Entry + 534) = *((_BYTE *)Entry + 534) & 0xEF | (Blink >> 10) & 0x10;
  *((_BYTE *)Entry + 534) = *((_BYTE *)Entry + 534) & 0x7F | (Blink >> 10) & 0x80;
  *((_BYTE *)Entry + 533) = *((_BYTE *)Entry + 533) & 0xFB | BYTE2(Blink) & 4;
  *((_BYTE *)Entry + 537) = 0;
  *((_BYTE *)Entry + 528) = *((_BYTE *)Entry + 528) & 0xFE | (*((_QWORD *)&RxContext->9 + 21) != 0);
  v13 = (unsigned __int8 *)Entry;
  v14 = *((_BYTE *)Entry + 533);
  if ( (v14 & 0x20) != 0 )
  {
    *((_BYTE *)Entry + 533) = v14 | 0x10;
    v13 = (unsigned __int8 *)Entry;
  }
  Buffer = *(_QWORD *)&pFcb->OpenCount;
  if ( Buffer && *(_QWORD *)(Buffer + 48) )
  {
    CscAcquireLViewLock(*(_QWORD *)&pFcb->OpenCount);
    CscSetLViewIsDfs(*(_QWORD *)&pFcb->OpenCount, *((_BYTE *)Entry + 528) & 1);
    CscReleaseLViewLock(*(_QWORD *)&pFcb->OpenCount);
    Buffer = *(_QWORD *)&pFcb->OpenCount;
    v13 = (unsigned __int8 *)Entry;
  }
  if ( !v7 )
  {
    if ( (*((_DWORD *)&RxContext->9 + 35) & 0x400) != 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 72, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids);
        v13 = (unsigned __int8 *)Entry;
      }
      v66 = 4798;
      inited = -1073741108;
      goto LABEL_174;
    }
    v101 = *(_QWORD *)(v295 + 40);
    if ( v101 )
    {
      if ( (*(_BYTE *)(v101 + 4) & 1) != 0 )
      {
        SlashDotOpen = CscCreateSlashDotOpen(RxContext);
        v13 = (unsigned __int8 *)Entry;
        inited = SlashDotOpen;
        v66 = 4823;
        goto LABEL_174;
      }
    }
  }
  if ( (Blink & 0x1C0) != 0 )
  {
    v66 = 4837;
    inited = -1073741811;
    goto LABEL_174;
  }
  v16 = 0;
  *(_DWORD *)&v276[7] = -1073741811;
  v280 = 0;
  if ( Buffer )
  {
    v56 = _InterlockedCompareExchange64((volatile signed __int64 *)(*(_QWORD *)(Buffer + 48) + 40LL), 0, 0);
    v16 = v56;
    if ( v56 )
    {
      CscStoreEntryIsTransparentlyCached(v56, &v280);
      IsRootGhosted = CscLViewIsRootGhosted(*(_QWORD *)&pFcb->OpenCount);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
      {
        v198 = 89;
        if ( !IsRootGhosted )
          v198 = 78;
        v269 = v198;
        WPP_SF_cc(WPP_GLOBAL_Control->AttachedDevice, 73, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids);
      }
      if ( IsRootGhosted || v280 )
        v123 = 0;
      else
        v123 = 4;
      *((_BYTE *)Entry + 535) = v123 | *((_BYTE *)Entry + 535) & 0xFB;
      v13 = (unsigned __int8 *)Entry;
    }
    else
    {
      *((_BYTE *)Entry + 535) |= 4u;
      v13 = (unsigned __int8 *)Entry;
    }
  }
  if ( !v7 )
  {
    Buffer = (__int64)RxContext->Create.UserName.Buffer;
    inited = *(_DWORD *)(Buffer + 16);
    if ( !*(_QWORD *)&pFcb->OpenCount )
    {
      v66 = 4908;
      goto LABEL_174;
    }
    *(_DWORD *)&v276[7] = *(_DWORD *)(Buffer + 16);
    if ( v16 )
    {
      BYTE1(v299[0]) = BYTE1(v299[0]) & 0xFD | (2 * (v280 & 1));
      if ( (v13[535] & 4) == 0 && !*(_BYTE *)(Buffer + 20) && (v13[533] & 2) == 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
        {
          WPP_SF_qqcD(
            WPP_GLOBAL_Control->AttachedDevice,
            74,
            WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
            pFcb,
            *(_QWORD *)&pFcb->OpenCount,
            78,
            inited);
          v13 = (unsigned __int8 *)Entry;
        }
        v66 = 4931;
        goto LABEL_174;
      }
    }
  }
  inited = CscPathUtilsInitParentPathFromFullPath(&String1, &RxContext->TrackerHistory[7].FileName, &WPP_GLOBAL_Control);
  if ( inited < 0 )
  {
    v13 = (unsigned __int8 *)Entry;
    v66 = 4954;
    goto LABEL_174;
  }
  if ( (unsigned int)CscExclusionListCheckCreate((char *)&RxContext->9 + 112, pFcb, MrxSrvOpen, &String1, v269) == -1073739772 )
  {
    v104 = RxContext->Create.PipeCompletionMode == 3;
    v284 = 1;
    if ( !v104 )
    {
      v13 = (unsigned __int8 *)Entry;
      v66 = 4983;
      inited = -1073739772;
      goto LABEL_174;
    }
    RxContext->Create.PipeCompletionMode = 1;
  }
  v17 = v293;
  if ( !v7
    && (*(_DWORD *)(v293 + 56) & 0x40) == 0
    && !(unsigned __int8)CscEcpGetTypeValue(RxContext->CurrentIrp, 1)
    && (*((_BYTE *)Entry + 535) & 4) != 0 )
  {
    _InterlockedCompareExchange64(
      (volatile signed __int64 *)(*(_QWORD *)(*(_QWORD *)&pFcb->OpenCount + 48LL) + 40LL),
      0,
      0);
    CscOfflineLviewCacheAddEntryEx((PERESOURCE)(CscDevExtn + 384), 0);
  }
  CscGetContexts(RxContext, v12);
  v18 = v12 + 3;
  if ( (v285 & 0x2000) != 0 && (*(_DWORD *)(*v18 + 4LL) & 0x20) != 0
    || (v285 & 0x8000) != 0 && (v18 = v12 + 3, (*(_DWORD *)(v12[3] + 4LL) & 1) != 0) )
  {
    v19 = 4;
  }
  else
  {
    v19 = 0;
  }
  *((_BYTE *)Entry + 534) = v19 | *((_BYTE *)Entry + 534) & 0xFB;
  if ( !v7 && RxContext->Create.UserName.Buffer && *(_BYTE *)(*v18 + 48LL) && *(_BYTE *)(*v18 + 49LL) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 75, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids);
    *(_BYTE *)(*v18 + 48LL) = 0;
    *(_BYTE *)(*v18 + 49LL) = 0;
  }
  if ( (*(_DWORD *)(v17 + 56) & 0x10) != 0 || !v7 && (unsigned __int8)CscEcpGetTypeValue(RxContext->CurrentIrp, 2) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    {
      v175 = 89;
      v176 = 89;
      if ( (*((_BYTE *)Entry + 535) & 4) == 0 )
        v176 = 78;
      if ( !v7 )
        v175 = 78;
      WPP_SF_cDc(
        WPP_GLOBAL_Control->AttachedDevice,
        76,
        WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
        v175,
        *(_DWORD *)(v17 + 56),
        v176);
    }
    if ( (*((_BYTE *)Entry + 535) & 4) != 0 )
      CscTransitionLViewOffline(*(_QWORD *)&pFcb->OpenCount, 2);
  }
  inited = CscCreatepUpdateStateForAdminOpen(RxContext, Entry);
  if ( inited < 0 )
  {
    v13 = (unsigned __int8 *)Entry;
    v66 = 5069;
    goto LABEL_174;
  }
  v21 = MrxSrvOpen;
  LOBYTE(v20) = 1;
  CscUpdateAndCaptureConnectionStateEx((_DWORD)pFcb, (_DWORD)MrxSrvOpen, (_DWORD)RxContext, v20, (__int64)v299, 0);
  Timer_high = LOBYTE(v299[0]);
  Buffer = BYTE1(v299[0]);
  v13 = (unsigned __int8 *)Entry;
  v24 = v299[0] & 0xFB | (LOBYTE(v299[0]) | (LOBYTE(v299[0]) >> 3)) & 4;
  LOBYTE(v299[0]) = v24;
  if ( (v299[0] & 0x1000) != 0 || (*((_BYTE *)Entry + 534) & 4) != 0 )
    LOBYTE(Timer_high) = 16;
  else
    LOBYTE(Timer_high) = 0;
  LOBYTE(Buffer) = Timer_high | BYTE1(v299[0]) & 0xEF;
  BYTE1(v299[0]) = Buffer;
  if ( ((v24 & 0x40) != 0 || !v12[2]) && (v24 & 0x10) == 0 && (*((_BYTE *)Entry + 533) & 0x12) == 0 )
  {
    v55 = CscCheckConnectionProperties(
            *(_QWORD *)(*(_QWORD *)&pFcb->OpenCount + 32LL),
            v293,
            (unsigned int)v299,
            (int)Entry + 539,
            (__int64)Entry + 540);
    if ( v55 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        Timer_high = HIDWORD(WPP_GLOBAL_Control->Timer);
        if ( (Timer_high & 0x20) != 0 )
          WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 77, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids, pFcb, v55);
      }
      *((_BYTE *)Entry + 539) = 0;
      *((_BYTE *)Entry + 540) = 0;
      v13 = (unsigned __int8 *)Entry;
    }
    else
    {
      v13 = (unsigned __int8 *)Entry;
    }
  }
  v25 = v12[1];
  if ( v25
    && *(_DWORD *)(v25 + 8)
    && (Timer_high = v13[533], (Timer_high & 4) != 0)
    && ((__int64)pFcb[1].Header.FilterContexts.Flink & 0x10) == 0 )
  {
    v26 = v285;
    LOBYTE(Timer_high) = Timer_high & 0xFB;
    LODWORD(v26) = v285 & 0xFFFBFFFF;
    v13[533] = Timer_high;
    v13 = (unsigned __int8 *)Entry;
    v286 = v26;
  }
  else
  {
    v26 = v286;
  }
  v27 = v13[533];
  if ( (v27 & 4) != 0 )
  {
    v22 = *((unsigned int *)&RxContext->9 + 28);
    if ( (v22 & 0xFFEFFF7F) != 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
      {
        WPP_SF_DqD(
          WPP_GLOBAL_Control->AttachedDevice,
          78,
          WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
          v26,
          pFcb,
          v22);
        v13 = (unsigned __int8 *)Entry;
      }
      v66 = 5125;
      inited = -1073741811;
      goto LABEL_174;
    }
    v13[533] = v27 | 2;
    *((_BYTE *)Entry + 533) |= 0x40u;
    v13 = (unsigned __int8 *)Entry;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
  {
    v281 = v13[540];
    v276[0] = v13[539];
    v85 = v12[1];
    if ( v85 )
      updated = *(_DWORD *)(v85 + 72);
    else
      updated = -1;
    v199 = v13[533];
    v200 = v12[2];
    v201 = BYTE1(v299[0]) >> 4;
    GlobalNewlyCachedEpoch = CscQueryGlobalNewlyCachedEpoch(Timer_high, Buffer, v22, v26);
    v203 = 89;
    if ( !v281 )
      v203 = 78;
    v204 = 89;
    v205 = 89;
    v206 = 89;
    v207 = 89;
    if ( !v276[0] )
      v204 = 78;
    v104 = (v201 & 1) == 0;
    v208 = 89;
    if ( v104 )
      v205 = 78;
    if ( (v199 & 4) == 0 )
      v208 = 78;
    if ( (v199 & 8) == 0 )
      v206 = 78;
    v273 = v203;
    v104 = v200 == 0;
    pFcb = v294;
    v7 = v275;
    if ( !v104 )
      v207 = 78;
    v209 = 89;
    if ( !v275 )
      v209 = 78;
    WPP_SF_cDDcccqqqDDDdcddccZ(
      WPP_GLOBAL_Control->AttachedDevice,
      79,
      (unsigned int)WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
      v209,
      v286,
      v285,
      v207,
      v206,
      v208,
      (char)v294,
      *(_QWORD *)&v294->OpenCount,
      (char)MrxSrvOpen,
      HIDWORD(v294->SrvOpenList.Flink),
      HIDWORD(v294->SrvOpenList.Blink),
      (char)v294->SrvOpenList.Blink,
      RxContext->Create.PipeCompletionMode,
      v205,
      updated,
      GlobalNewlyCachedEpoch,
      v204,
      v273,
      (__int64)&RxContext->TrackerHistory[7].FileName);
    v13 = (unsigned __int8 *)Entry;
    v21 = MrxSrvOpen;
  }
  v28 = v12[1];
  if ( v28 && *(_QWORD *)(v28 + 64) )
  {
    v107 = v12[1];
    if ( MEMORY[0xFFFFF78000000014] <= *(_QWORD *)(v107 + 64) )
    {
      if ( (*(_DWORD *)(v107 + 4) & 0x1166F) == 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 81, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids);
        }
        LOBYTE(v299[0]) |= 0x12u;
        CscTransitionFcbOffline(pFcb, 0, 8, 0);
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 80, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids);
      *(_QWORD *)(v12[1] + 64LL) = 0;
    }
    v13 = (unsigned __int8 *)Entry;
  }
  Buffer = v13[533];
  if ( (Buffer & 8) != 0 )
    goto LABEL_356;
  v29 = v12[1];
  if ( v29 && (v299[0] & 0x40) == 0 && v7 )
  {
    if ( (v299[0] & 1) != 0 )
    {
      if ( (v299[0] & 0x400) == 0 || (v299[0] & 0x1000) == 0 || (v299[0] & 0x800) == 0 )
        goto LABEL_30;
    }
    else
    {
      v111 = *(_DWORD *)(v29 + 4);
      if ( (v111 & 0x200) == 0 && (v111 & 0x80000) == 0 && v299[2] <= *(_DWORD *)(v29 + 40) )
        goto LABEL_30;
    }
    v112 = *(_DWORD *)(v29 + 4);
    if ( (v112 & 0x1166F) != 0
      && ((unsigned __int8)~((unsigned __int8)Buffer >> 6) & ((v112 & 0x1000060) == 0)) != 0
      && !*(_QWORD *)(v29 + 64) )
    {
LABEL_356:
      if ( (v13[534] & 4) != 0 )
        ++*(_DWORD *)(v12[1] + 76LL);
      v113 = CscBackPatchObject((__int64)RxContext, (char *)v299, (__int64)v12);
      v13 = (unsigned __int8 *)Entry;
      Buffer = v113;
      if ( (*((_BYTE *)Entry + 533) & 8) != 0 || v113 == -1073741225 )
      {
        if ( (*((_BYTE *)Entry + 534) & 4) != 0 )
        {
          --*(_DWORD *)(v12[1] + 76LL);
          v13 = (unsigned __int8 *)Entry;
        }
        inited = v113;
        v66 = 5268;
        goto LABEL_174;
      }
      CscUpdateFcbContextOnBackpatch(v12[1], v299, v113);
      LOBYTE(v114) = 1;
      CscUpdateAndCaptureConnectionStateEx((_DWORD)pFcb, (_DWORD)v21, (_DWORD)RxContext, v114, (__int64)v299, 0);
      v13 = (unsigned __int8 *)Entry;
      v115 = v299[0] & 0xFB | (LOBYTE(v299[0]) | (LOBYTE(v299[0]) >> 3)) & 4;
      LOBYTE(v299[0]) = v115;
      if ( (*((_BYTE *)Entry + 534) & 4) != 0 )
      {
        --*(_DWORD *)(v12[1] + 76LL);
        v115 = v299[0];
        v13 = (unsigned __int8 *)Entry;
      }
      if ( (v115 & 0x10) == 0
        && (HIBYTE(pFcb[2].Header.NodeByteSize) & 0x3C) == 0xC
        && (*((_DWORD *)&RxContext->9 + 35) & 0x200000) != 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 82, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids);
          v13 = (unsigned __int8 *)Entry;
        }
        v66 = 5312;
        inited = -1069481983;
        goto LABEL_174;
      }
      v13[534] |= 8u;
      v13 = (unsigned __int8 *)Entry;
    }
  }
LABEL_30:
  v30 = v13[534];
  if ( (v30 & 4) != 0
    && (v30 & 8) == 0
    && v7
    && (v299[0] & 0x400) != 0
    && (!v12[1] || (v299[0] & 0x800) != 0)
    && (v13[533] & 0x40) == 0 )
  {
    LOBYTE(v299[0]) &= 0xEDu;
    v210 = v12[1];
    if ( v210 )
    {
      *(_DWORD *)(v210 + 4) &= 0xFFFEFFFE;
      v13 = (unsigned __int8 *)Entry;
    }
  }
  if ( (v299[0] & 4) != 0 )
  {
    v88 = v12[1];
    if ( v88 )
    {
      v13[528] = v13[528] & 0xEF | (*(_DWORD *)(v88 + 4) >> 18) & 0x10;
      *((_OWORD *)Entry + 24) = *(_OWORD *)&RxContext->TrackerHistory[7].FileName;
      *((_WORD *)Entry + 192) = *(_WORD *)(v12[1] + 80LL);
    }
    else
    {
      v89 = CscOkToCacheFileName(&RxContext->TrackerHistory[7].FileName, v13 + 384, v22, v26);
      Buffer = (__int64)Entry;
      v90 = 0;
      v22 = 16;
      if ( !v89 )
        v90 = 16;
      *((_BYTE *)Entry + 528) = *((_BYTE *)Entry + 528) & 0xEF | v90;
    }
    v13 = (unsigned __int8 *)Entry;
    if ( (*((_BYTE *)Entry + 528) & 0x10) != 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 83, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids);
        v13 = (unsigned __int8 *)Entry;
      }
      LOBYTE(v299[0]) &= ~0x10u;
      if ( (v299[0] & 1) != 0 )
      {
        v66 = 5408;
        inited = -1073741108;
        goto LABEL_174;
      }
      v91 = *((unsigned __int16 *)v13 + 192);
      if ( (_WORD)v91 )
      {
        v22 = *((unsigned __int16 *)v13 + 193);
        if ( (unsigned __int16)v91 < (unsigned __int16)v22
          && v91 + 2 < v22
          && *(_WORD *)(*((_QWORD *)v13 + 49) + 2 * ((unsigned __int64)*((unsigned __int16 *)v13 + 192) >> 1)) == 58 )
        {
          InformationEntry = CscStoreRelativeQueryInformationEntry(0, v13 + 384, v13 + 120, v13 + 56);
          v13 = (unsigned __int8 *)Entry;
          if ( InformationEntry >= 0
            && (*((_DWORD *)Entry + 26) & 0x10) == 0
            && (*((_DWORD *)Entry + 30) & 0x80417) != 0 )
          {
            v66 = 5440;
            inited = -1073741108;
            goto LABEL_174;
          }
        }
      }
    }
  }
  v31 = v13[533];
  v287 = 0;
  if ( (v299[0] & 4) == 0 )
  {
    if ( (v31 & 0x5A) != 0 || v31 < 0 || (v13[534] & 4) != 0 )
    {
      v265 = CscStoreFindEntry(&v277, 0, &RxContext->TrackerHistory[7].FileName, v26);
      v13 = (unsigned __int8 *)Entry;
      inited = -1073741772;
      v66 = 6018;
      if ( v265 < 0 )
        inited = v265;
      goto LABEL_174;
    }
    v276[0] = 0;
    goto LABEL_77;
  }
  if ( (v31 & 6) == 2 )
    LOBYTE(v299[0]) |= 0x10u;
  if ( v7 )
  {
    v93 = v13[533];
    if ( (v93 & 0x40) != 0 )
    {
      if ( (v299[0] & 0x10) != 0 )
      {
        v13[533] = v93 & 0xBF;
        v13 = (unsigned __int8 *)Entry;
      }
      else
      {
        LOBYTE(v299[0]) |= 0x10u;
      }
    }
  }
  if ( (v299[0] & 0x20) != 0 )
  {
    v13[529] |= 0x80u;
    v13 = (unsigned __int8 *)Entry;
  }
  v32 = RxSidFromRxContext(RxContext, v13 + 200, v22, v26);
  v13 = (unsigned __int8 *)Entry;
  if ( v32 < 0 )
  {
    inited = v32;
    v66 = 5499;
    goto LABEL_174;
  }
  v33 = 0;
  v104 = (*((_BYTE *)Entry + 528) & 0x10) == 0;
  v276[0] = 0;
  if ( v104 && v7 && (v299[0] & 0x10) == 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 84, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids);
      v13 = (unsigned __int8 *)Entry;
    }
    v34 = CscStoreFindEntryEx((unsigned int)&v277, 0, (int)RxContext + 816, (int)v13 + 537, (__int64)(v13 + 538));
    if ( v34 )
    {
      v13 = (unsigned __int8 *)Entry;
      v33 = 0;
      v276[0] = 0;
      Buffer = v34;
      v287 = v34;
      goto LABEL_45;
    }
    v281 = 0;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
      WPP_SF_qqq(
        WPP_GLOBAL_Control->AttachedDevice,
        85,
        WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
        v277,
        pFcb,
        v21);
    *((_BYTE *)Entry + 529) |= 0x80u;
    CanSidDecryptEntry = CscStoreQueryCanSidDecryptEntry(v277, (char *)Entry + 200, &v281);
    if ( CanSidDecryptEntry < 0 )
    {
      v13 = (unsigned __int8 *)Entry;
      inited = CanSidDecryptEntry;
      v66 = 5537;
      goto LABEL_174;
    }
    if ( !v281 )
    {
      CscStoreDereferenceEntry(&v277);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
        WPP_SF_qqq(
          WPP_GLOBAL_Control->AttachedDevice,
          86,
          WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
          v277,
          pFcb,
          v21);
      v211 = CscCreateReparseToRemoteCreate(RxContext);
      v13 = (unsigned __int8 *)Entry;
      inited = v211;
      v66 = 5556;
      goto LABEL_174;
    }
    v125 = CscStoreQueryInformationEntryEx(
             (_DWORD)v277,
             0,
             (int)Entry + 120,
             (int)Entry + 56,
             (__int64)Entry + 536,
             0,
             0);
    if ( v125 < 0 )
    {
      CscStoreDereferenceEntry(&v277);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
        WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 87, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids, v277, v125);
      v13 = (unsigned __int8 *)Entry;
      inited = v125;
      v66 = 5573;
      goto LABEL_174;
    }
    v33 = 1;
    v21 = MrxSrvOpen;
    v276[0] = 1;
    *((_BYTE *)Entry + 535) |= 1u;
    v13 = (unsigned __int8 *)Entry;
  }
  Buffer = v287;
LABEL_45:
  v35 = v12[1];
  if ( !v35 )
  {
    v36 = 0;
LABEL_47:
    if ( (v13[528] & 0x10) != 0 || !v7 || (v299[0] & 0x10) != 0 )
    {
LABEL_58:
      if ( !v12[1] )
      {
        inited = CscAllocateAndApplyFcbContext(pFcb, v12);
        if ( inited )
        {
          v13 = (unsigned __int8 *)Entry;
          v66 = 5824;
          goto LABEL_174;
        }
      }
      *(_DWORD *)(v12[1] + 4LL) = v36;
      Buffer = (__int64)Entry;
      if ( (*((_BYTE *)Entry + 528) & 0x10) != 0 )
      {
        *(_DWORD *)(v12[1] + 4LL) |= 0x400000u;
        Buffer = (__int64)Entry;
      }
      *(_WORD *)(v12[1] + 80LL) = *(_WORD *)(Buffer + 384);
      if ( v7 )
        RxSetFcbDispatchTable(pFcb, CscDeviceObject[1].NextDevice);
      goto LABEL_63;
    }
    if ( (v13[534] & 0x10) == 0 && v13[537] )
    {
      LOBYTE(v299[0]) |= 0x12u;
      v36 |= 0x1000u;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 88, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids);
        Buffer = v287;
        v13 = (unsigned __int8 *)Entry;
      }
      v33 = v276[0];
    }
    if ( v13[538] )
    {
      v212 = v13[533];
      if ( (v212 & 0x12) == 0 && v212 >= 0 )
      {
        v66 = 5644;
        inited = -1073741766;
        goto LABEL_174;
      }
    }
    if ( !v33 )
    {
      if ( (v13[534] & 0x10) == 0 && ((_DWORD)Buffer == -1073741766 || (_DWORD)Buffer == -1073741772) )
      {
        v37 = RxContext->Create.PipeCompletionMode;
        if ( v37 <= 5 )
        {
          v38 = 45;
          if ( _bittest(&v38, v37) )
          {
            if ( (unsigned __int8)CscCreatepCheckIfLongestPrefixInCacheIsDirty(&RxContext->TrackerHistory[7].FileName) )
            {
              LOBYTE(v299[0]) |= 0x12u;
              v36 |= 8u;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
              {
                WPP_SF_d(
                  WPP_GLOBAL_Control->AttachedDevice,
                  94,
                  WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
                  RxContext->Create.PipeCompletionMode);
              }
            }
          }
        }
      }
      goto LABEL_58;
    }
    v164 = CscStoreQueryInformationEntryEx((_DWORD)v277, 0, (int)v13 + 120, (int)v13 + 56, (__int64)(v13 + 536), 0, 0);
    v13 = (unsigned __int8 *)Entry;
    if ( v164 < 0 )
    {
      inited = v164;
      v66 = 5769;
      goto LABEL_174;
    }
    v165 = *((_DWORD *)Entry + 30);
    Buffer = v165 & 0x10;
    if ( (v165 & 0x10) != 0 && (*((_BYTE *)Entry + 533) & 2) != 0 && (*((_DWORD *)Entry + 26) & 0x10) != 0 )
    {
      LOBYTE(v299[0]) |= 2u;
      *((_BYTE *)Entry + 532) |= 1u;
      *((_BYTE *)Entry + 533) |= 0x10u;
      v213 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
      {
        v214 = 89;
LABEL_918:
        WPP_SF_(v213->AttachedDevice, v214, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids);
      }
    }
    else
    {
      v166 = *((_BYTE *)Entry + 533);
      if ( ((v166 & 0x10) == 0 || (v165 & 0x30) == 0) && ((v166 & 0x20) == 0 || (v165 & 0x10000) == 0) )
      {
        if ( (v165 & 0x10) != 0 )
        {
          v215 = RxContext->Create.PipeCompletionMode;
          if ( v215 > 5 || (v216 = 45, !_bittest(&v216, v215)) )
          {
            v66 = 5710;
            inited = -1073741772;
            goto LABEL_174;
          }
        }
        if ( RxContext->Create.PipeCompletionMode == 2 && (v165 & 0x10) == 0 && (v165 & 0x800000) == 0 )
        {
          *((_QWORD *)&RxContext->9 + 25) = 4;
          v66 = 5725;
          inited = -1073741771;
          goto LABEL_174;
        }
        if ( (v165 & 0x400) != 0
          || (v167 = *((_DWORD *)Entry + 26), (v165 & 0x80417) != 0) && (v167 & 0x10) == 0
          || ((unsigned __int8)v167 & (unsigned __int8)v165 & 0x10) != 0 )
        {
          LOBYTE(v299[0]) |= 0x12u;
          v36 |= 8u;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
          {
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              91,
              WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
              *((unsigned int *)Entry + 30));
            v13 = (unsigned __int8 *)Entry;
          }
        }
        if ( (*((_DWORD *)v13 + 30) & 0x10) == 0 )
          goto LABEL_570;
        if ( RxContext->Create.PipeCompletionMode != 3 )
          goto LABEL_570;
        LOBYTE(v299[0]) |= 0x12u;
        v36 |= 8u;
        v213 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) == 0 )
        {
          goto LABEL_570;
        }
        v214 = 92;
        goto LABEL_918;
      }
      LOBYTE(v299[0]) |= 0x12u;
      *((_BYTE *)Entry + 532) |= 1u;
      v213 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
      {
        v214 = 90;
        goto LABEL_918;
      }
    }
LABEL_570:
    CscStoreDereferenceEntry(&v277);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
      WPP_SF_qqq(
        WPP_GLOBAL_Control->AttachedDevice,
        93,
        WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
        v277,
        pFcb,
        MrxSrvOpen);
    goto LABEL_58;
  }
  if ( (v299[0] & 0x40) != 0 )
  {
    v36 = *(_DWORD *)(v35 + 4);
    goto LABEL_47;
  }
  if ( !v33 )
    goto LABEL_64;
  CscStoreDereferenceEntry(&v277);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    WPP_SF_qqq(WPP_GLOBAL_Control->AttachedDevice, 95, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids, v277, pFcb, v21);
LABEL_63:
  v13 = (unsigned __int8 *)Entry;
LABEL_64:
  if ( (v299[0] & 0x10) != 0 && (*((_DWORD *)v13 + 30) & 0x800000) != 0 )
  {
    v116 = v13[533];
    if ( (v116 & 2) == 0 )
    {
      v117 = 0;
      if ( (v116 & 0x10) == 0 )
        v117 = (v13[532] & 1) == 0;
      if ( v117 && (*(_DWORD *)(v12[1] + 4LL) & 8) == 0 && (v116 & 0x40) == 0 )
      {
        if ( !v7 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 96, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids);
            v13 = (unsigned __int8 *)Entry;
          }
          p_EaBuffer = &RxContext->Create.EaBuffer;
          v66 = 5894;
          inited = *((_DWORD *)RxContext->Create.UserName.Buffer + 4);
          goto LABEL_175;
        }
        if ( (*(_DWORD *)(v293 + 56) & 0x10) == 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 97, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids);
            v13 = (unsigned __int8 *)Entry;
          }
          LOBYTE(v299[0]) &= ~0x10u;
        }
      }
    }
  }
  if ( (v13[528] & 0x10) == 0
    && (*(_DWORD *)(v12[1] + 4LL) & 0x2000) != 0
    && (*((_DWORD *)&RxContext->9 + 28) & 0xFFEFFF7F) != 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 98, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids);
      v13 = (unsigned __int8 *)Entry;
    }
    v66 = 5922;
    inited = -1073741757;
    goto LABEL_174;
  }
  if ( v12[2] )
  {
    v40 = MrxSrvOpen;
  }
  else
  {
    Pool2 = (struct _UNICODE_STRING *)ExAllocatePool2(256, 48, 1061124178);
    v12[2] = Pool2;
    if ( !Pool2 )
    {
      v13 = (unsigned __int8 *)Entry;
      v66 = 5940;
      inited = -1073741670;
      goto LABEL_174;
    }
    v40 = MrxSrvOpen;
    MrxSrvOpen->pAlreadyPrefixedName = Pool2;
    *(_DWORD *)&Pool2->Length = 3205794;
    *((_BYTE *)Entry + 528) |= 0x40u;
  }
  v41 = v286;
  *(_DWORD *)(v12[2] + 32LL) = v286;
  if ( (*((_BYTE *)Entry + 533) & 2) != 0 )
    *(_DWORD *)(v12[2] + 24LL) |= 1u;
  if ( (v41 & 1) != 0 )
    LODWORD(v40->Key) |= 0x1080u;
  if ( *((_BYTE *)Entry + 539) && (v299[0] & 0x100) != 0 )
    *(_DWORD *)(v12[1] + 4LL) |= 0x4000000u;
  else
    *(_DWORD *)(v12[1] + 4LL) &= ~0x4000000u;
  v13 = (unsigned __int8 *)Entry;
LABEL_77:
  v275 = 0;
  if ( !v7 || (v299[0] & 0x10) != 0 )
    v42 = 0;
  else
    v42 = 8;
  v13[528] = v42 | v13[528] & 0xF7;
  v13 = (unsigned __int8 *)Entry;
  if ( (*((_BYTE *)Entry + 528) & 8) == 0 )
    goto LABEL_119;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 99, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids);
    v13 = (unsigned __int8 *)Entry;
  }
  v43 = v12[1];
  if ( v43 )
  {
    ++*(_DWORD *)(v43 + 32);
    PagingIoResource = (int)pFcb[1].Header.PagingIoResource;
    if ( PagingIoResource )
    {
      if ( PagingIoResource == *(_DWORD *)(v12[1] + 20LL) )
      {
        HIDWORD(pFcb->SrvOpenList.Flink) &= ~0x40000u;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 100, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids);
        }
      }
    }
    v13 = (unsigned __int8 *)Entry;
  }
  Buffer = LOBYTE(v299[0]);
  if ( (v299[0] & 0x20) != 0 && (v299[0] & 0x200) == 0 )
    goto LABEL_100;
  if ( (v299[0] & 0x40) != 0 )
  {
    if ( !v13[539] )
      goto LABEL_85;
    if ( (v13[535] & 1) == 0 || (*((_DWORD *)v13 + 30) & 0x800000) == 0 )
      goto LABEL_100;
  }
  if ( v13[539] && (v299[0] & 0x20) == 0 )
    goto LABEL_100;
LABEL_85:
  if ( ((v299[3] - 4) & 0xFFFFFFFB) == 0
    || (v44 = v12[3]) != 0 && *(_QWORD *)(v44 + 40) && (*(_DWORD *)(v44 + 4) & 0x2000) == 0 )
  {
LABEL_100:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    {
      v154 = 89;
      v155 = 89;
      if ( (v13[535] & 1) == 0 )
        v155 = 78;
      v156 = 89;
      v157 = 89;
      if ( (v299[0] & 0x200) == 0 )
        v156 = 78;
      if ( (v299[0] & 0x40) == 0 )
        v154 = 78;
      if ( (v299[0] & 0x20) == 0 )
        v157 = 78;
      WPP_SF_ZccccDcD(
        WPP_GLOBAL_Control->AttachedDevice,
        101,
        (unsigned int)WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
        (_DWORD)RxContext + 816,
        v157,
        v154,
        (((char)v13[529] >> 7) & 0xB) + 78,
        v156,
        v299[3],
        v155,
        *((_DWORD *)v13 + 30));
      Buffer = LOBYTE(v299[0]);
      v13 = (unsigned __int8 *)Entry;
    }
    LODWORD(RxContext->RdbssDbgExtension) |= 0x20000000u;
    goto LABEL_102;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
  {
    v45 = 89;
    v46 = 89;
    if ( (v13[535] & 1) == 0 )
      v45 = 78;
    v47 = 89;
    v48 = 89;
    if ( (v299[0] & 0x200) == 0 )
      v46 = 78;
    if ( (v299[0] & 0x40) == 0 )
      v47 = 78;
    if ( (v299[0] & 0x20) == 0 )
      v48 = 78;
    WPP_SF_ZccccDcD(
      WPP_GLOBAL_Control->AttachedDevice,
      102,
      (unsigned int)WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
      (_DWORD)RxContext + 816,
      v48,
      v47,
      (((char)v13[529] >> 7) & 0xB) + 78,
      v46,
      v299[3],
      v45,
      *((_DWORD *)v13 + 30));
    Buffer = LOBYTE(v299[0]);
    v13 = (unsigned __int8 *)Entry;
  }
LABEL_102:
  v49 = v295;
  if ( *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v295 + 48) + 352LL) + 56LL) )
  {
    if ( ((__int64)RxContext->ScavengerEntry.List.Flink & 2) == 0 )
    {
      *(_OWORD *)&RxContext->MRxContext[2] = 0;
      *(_OWORD *)&RxContext->WriteOnlyOpenRetryContext = 0;
      RxContext->ResumeRoutine = 0;
      v50 = (*(__int64 (__fastcall **)(PRX_CONTEXT, __int64, __int64, __int64))(*(_QWORD *)(*(_QWORD *)(v49 + 48) + 352LL)
                                                                              + 56LL))(
              RxContext,
              Buffer,
              v49,
              32);
      Buffer = LOBYTE(v299[0]);
      v49 = v295;
      v51 = v50;
      v13 = (unsigned __int8 *)Entry;
      *(_DWORD *)&v276[3] = v50;
      goto LABEL_105;
    }
    v51 = -1073741536;
  }
  else
  {
    v51 = -1073741822;
  }
  *(_DWORD *)&v276[3] = v51;
LABEL_105:
  v52 = v12[1];
  if ( v52 )
  {
    --*(_DWORD *)(v52 + 32);
    Buffer = LOBYTE(v299[0]);
    v13 = (unsigned __int8 *)Entry;
  }
  inited = v51;
  if ( (Buffer & 4) != 0 )
  {
    *(_DWORD *)(v12[2] + 24LL) |= 4u;
    *(_QWORD *)(v12[2] + 40LL) = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v49 + 48) + 352LL) + 136LL);
    *(_DWORD *)(v12[1] + 4LL) |= 0x10u;
    *(_QWORD *)(v12[1] + 88LL) = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v49 + 48) + 352LL) + 128LL);
    v53 = 0;
    if ( !*(_DWORD *)(v12[1] + 8LL) )
      v53 = 32;
    *((_BYTE *)Entry + 528) = *((_BYTE *)Entry + 528) & 0xDF | v53;
    if ( v51 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          104,
          WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
          (unsigned int)v51);
      if ( !(unsigned __int8)CscTransitnOKToGoOffline((unsigned int)v51) || (v275 = 1, (v299[0] & 0x200) != 0) )
      {
        Buffer = LOBYTE(v299[0]);
      }
      else
      {
        Buffer = LOBYTE(v299[0]);
        LOBYTE(Buffer) = LOBYTE(v299[0]) | 0x12;
        LOBYTE(v299[0]) |= 0x12u;
      }
      if ( (Buffer & 0x10) == 0 )
      {
        if ( (unsigned int)(v51 + 1073741790) > 0x18 || (v110 = 17039361, !_bittest(&v110, v51 + 1073741790)) )
        {
          if ( (Buffer & 0x40) == 0 || v51 != -1073741565 && v51 != -1073741638 )
          {
            v13 = (unsigned __int8 *)Entry;
            v66 = 6181;
            goto LABEL_174;
          }
        }
      }
      v13 = (unsigned __int8 *)Entry;
      goto LABEL_134;
    }
    v54 = MrxSrvOpen;
    CscUpdateRdrOpenCount(v12[1], MrxSrvOpen, 1);
    *((_BYTE *)Entry + 532) |= 0x40u;
    *(_DWORD *)(v12[1] + 36LL) = *(_DWORD *)(v12[3] + 8LL);
    *(_DWORD *)(v12[2] + 24LL) |= 2u;
    if ( ((__int64)v54->Key & 0x100000) == 0 )
      *((_BYTE *)Entry + 532) |= 0x20u;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
      WPP_SF_Dd(
        WPP_GLOBAL_Control->AttachedDevice,
        103,
        WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
        *(unsigned int *)(v12[1] + 8LL),
        RxContext->TrackerHistory[4].AcquireRelease);
    Buffer = LOBYTE(v299[0]);
    v13 = (unsigned __int8 *)Entry;
  }
  else
  {
    v275 = 0;
    if ( v51 < 0 )
      goto LABEL_134;
  }
  if ( *(_DWORD *)(v12[3] + 8LL) > *(_DWORD *)(v12[3] + 12LL) )
  {
    CscNotifyLViewReconnect(RxContext, pFcb, v12);
    v13 = (unsigned __int8 *)Entry;
LABEL_119:
    Buffer = LOBYTE(v299[0]);
  }
LABEL_134:
  if ( (Buffer & 0x10) != 0 )
  {
    v119 = *((_QWORD *)&RxContext->9 + 18);
    if ( v119 )
    {
      if ( *(_QWORD *)(*(_QWORD *)(v119 + 8) + 64LL) )
      {
        if ( !v276[0] && (Buffer & 4) != 0 )
        {
          v120 = RxContext->Create.PipeCompletionMode;
          if ( v120 <= 5 )
          {
            v121 = 45;
            if ( _bittest(&v121, v120) )
            {
              v66 = 6217;
              inited = -1073741108;
              goto LABEL_174;
            }
          }
        }
      }
    }
  }
  if ( (HIBYTE(pFcb[2].Header.NodeByteSize) & 0x3C) == 8 )
  {
    v103 = inited;
    v66 = 6246;
    if ( (v13[528] & 8) == 0 )
      v103 = -1073741108;
    inited = v103;
    goto LABEL_174;
  }
  if ( (Buffer & 4) != 0 && (v13[528] & 0x10) == 0 )
  {
    if ( (Buffer & 0x40) != 0 )
      goto LABEL_140;
    if ( (Buffer & 0x10) != 0 )
      goto LABEL_140;
    v118 = v12[1];
    if ( !v118 || *(_QWORD *)(v118 + 56) )
      goto LABEL_140;
  }
  if ( v7 || (Buffer & 4) != 0 )
  {
    if ( (v13[528] & 8) == 0 )
    {
      v104 = inited == 0;
      if ( inited >= 0 )
      {
        inited = -1073741108;
LABEL_324:
        v66 = 6301;
        goto LABEL_174;
      }
      goto LABEL_318;
    }
  }
  else
  {
    inited = *(_DWORD *)&v276[7];
  }
  v104 = inited == 0;
LABEL_318:
  if ( !v104 )
    goto LABEL_324;
  if ( (Buffer & 4) == 0 )
    goto LABEL_324;
  if ( (Buffer & 0x10) != 0 )
    goto LABEL_324;
  v105 = v12[1];
  if ( !v105 )
    goto LABEL_324;
  if ( (v13[528] & 0x10) != 0 )
    goto LABEL_324;
  v106 = CscMatchesGlobalNewlyCachedEpoch(*(unsigned int *)(v105 + 72));
  v13 = (unsigned __int8 *)Entry;
  if ( v106 )
    goto LABEL_324;
  LOBYTE(Buffer) = v299[0];
LABEL_140:
  v57 = 8 * ((Buffer & 0x10) != 0);
  if ( (Buffer & 0x10) == 0 && !v299[3] && (Buffer & 0x40) == 0
    || (v58 = v275, (v13[528] & 8) != 0) && !v275 && *(int *)&v276[3] < 0
    || (Buffer & 0x10) != 0
    && ((v108 = RxContext->Create.PipeCompletionMode, v108 > 5) || (v109 = 45, !_bittest(&v109, v108))) )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) == 0 )
      goto LABEL_157;
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 107, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids);
LABEL_253:
    v13 = (unsigned __int8 *)Entry;
    LOBYTE(Buffer) = v299[0];
    goto LABEL_157;
  }
  if ( (Buffer & 0x10) != 0 || v299[3] || (*(_DWORD *)(v12[1] + 4LL) & 0x80u) != 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 106, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids);
      LOBYTE(Buffer) = v299[0];
      v58 = v275;
      v13 = (unsigned __int8 *)Entry;
    }
    if ( (Buffer & 0x10) == 0 )
      v57 |= 1u;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 105, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids);
      LOBYTE(Buffer) = v299[0];
      v58 = v275;
      v13 = (unsigned __int8 *)Entry;
    }
    v57 |= 0x401u;
    if ( v13[539] )
      v57 |= 0x40000u;
  }
  v57 |= 2u;
  if ( (v13[528] & 8) == 0 || (_BYTE)v58 )
  {
    v217 = CscInitNetInfoFromRxContext(RxContext, v13, v58);
    if ( v217 < 0 )
    {
      v13 = (unsigned __int8 *)Entry;
      inited = v217;
      v66 = 6402;
      goto LABEL_174;
    }
    *((_BYTE *)Entry + 528) |= 2u;
    goto LABEL_253;
  }
LABEL_157:
  if ( (Buffer & 0x10) == 0 && *(int *)&v276[3] >= 0 && *((_QWORD *)&RxContext->9 + 25) == 2 )
    v57 |= 0x10000u;
  v13[528] = v13[528] & 0xFB | ((v57 & 0x402) != 0 ? 4 : 0);
  v59 = v57 | 4;
  if ( (v299[0] & 0x10) == 0 )
    v59 = v57;
  *(_DWORD *)&v276[7] = v59;
  RxSubjectContextFromRxContext(RxContext, &v292);
  v60 = (char *)Entry;
  v61 = *((_BYTE *)Entry + 528);
  if ( (v61 & 4) != 0 || *((char *)Entry + 529) < 0 )
  {
    v62 = v275;
    if ( (v299[0] & 0x10) == 0 || v275 )
    {
      v276[0] = v61 & 1;
      v86 = v59 | (*((char *)Entry + 529) >> 7) & 0x800;
      if ( !v299[3] || v299[3] == 12 )
        v86 = v59 & 0xFFFFFFFC | (*((char *)Entry + 529) >> 7) & 0x800;
      v87 = 0;
      if ( (v59 & 8) != 0 )
        v87 = v292;
      CscUpdateShareInfoForLogicalView(
        (int)RxContext,
        v86,
        (_DWORD)Entry + 200,
        v299[3],
        (__int64)v276,
        (PCUNICODE_STRING)&RxContext->TrackerHistory[7].FileName,
        (__int64)&v278,
        v87);
      v60 = (char *)Entry;
    }
  }
  else
  {
    v62 = v275;
  }
  if ( v60[529] >= 0 )
  {
    HasStoreEntry = CscLViewContextHasStoreEntry(*(_QWORD *)&pFcb->OpenCount);
    *((_BYTE *)Entry + 529) = *((_BYTE *)Entry + 529) & 0x7F | (HasStoreEntry << 7);
    v60 = (char *)Entry;
  }
  if ( (v60[528] & 8) != 0 && !v62 || (v299[0] & 0x40) == 0 )
  {
    RxInitNetInfoFromFcb(pFcb, v60);
    *((_BYTE *)Entry + 528) |= 2u;
    v60 = (char *)Entry;
  }
  v64 = v12[1];
  if ( *(_QWORD *)(v64 + 56) )
  {
    v277 = *(struct _LIST_ENTRY **)(v64 + 56);
    CscStoreReferenceEntry(v277);
    v65 = *(_DWORD *)&v276[7];
    if ( (*(_DWORD *)(v12[1] + 4LL) & 0x800000) != 0 )
      LODWORD(v278) = v278 | 0x40;
    goto LABEL_170;
  }
  v74 = *(_QWORD *)&pFcb->OpenCount;
  LODWORD(v294) = 0;
  v75 = 0;
  v76 = 0;
  if ( (v59 & 8) != 0 )
    v75 = v292;
  if ( (v60[528] & 4) != 0 )
    v76 = (__int64)v60;
  v77 = CscStoreFindOrCreateEntry(
          (unsigned int)&v277,
          (unsigned int)&v294,
          0,
          (int)RxContext + 816,
          v59,
          v76,
          _InterlockedCompareExchange64((volatile signed __int64 *)(*(_QWORD *)(v74 + 48) + 40LL), 0, 0),
          v75);
  updated = v77;
  LODWORD(v278) = (unsigned int)v294 | v278;
  if ( v77 < 0 )
  {
LABEL_211:
    v80 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        109,
        WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
        (unsigned int)v77);
    if ( (v299[0] & 0x10) == 0 )
    {
      if ( (v299[0] & 0x200) != 0 )
      {
        inited = *(_DWORD *)&v276[3];
        v66 = 6652;
        v13 = (unsigned __int8 *)Entry;
        goto LABEL_174;
      }
      Buffer = *(unsigned int *)&v276[3];
      v82 = 0;
      if ( (v278 & 0x40) == 0 && (*(int *)&v276[3] >= 0 || (v81 = v12[1]) == 0 || !*(_QWORD *)(v81 + 56)) )
        v82 = 1;
      if ( *(_DWORD *)&v276[3] == -1073741766 )
      {
        if ( (v278 & 0x20) != 0 && String1.Length )
        {
          if ( !RtlEqualUnicodeString(&String1, *(PCUNICODE_STRING *)(*(_QWORD *)&pFcb->OpenCount + 56LL), 1u) )
            goto LABEL_970;
          Buffer = *(unsigned int *)&v276[3];
        }
      }
      else if ( *(int *)&v276[3] >= 0 && v12[1] )
      {
        if ( v77 == -1073741766 || v77 == -1073741809 || v77 == -1073741772 )
        {
          v83 = v12[1];
          v84 = CscQueryGlobalNewlyCachedEpoch(v80, *(unsigned int *)&v276[3], v78, v79);
          Buffer = *(unsigned int *)&v276[3];
          *(_DWORD *)(v83 + 72) = v84;
        }
        *(_DWORD *)(v12[1] + 24LL) = v77;
      }
      if ( v82 )
      {
        inited = Buffer;
LABEL_229:
        v13 = (unsigned __int8 *)Entry;
        v66 = 6724;
        goto LABEL_174;
      }
LABEL_970:
      inited = v77;
      goto LABEL_229;
    }
    if ( !v275 )
    {
      inited = v77;
LABEL_683:
      v13 = (unsigned __int8 *)Entry;
      goto LABEL_626;
    }
    if ( v7 )
    {
      v13 = (unsigned __int8 *)Entry;
      if ( *((char *)Entry + 529) >= 0 || (*(_DWORD *)(v12[3] + 4LL) & 0x2000) != 0 )
        goto LABEL_625;
      if ( !(unsigned __int8)CscLViewIsRootGhosted(*(_QWORD *)&pFcb->OpenCount) )
      {
        LOBYTE(Buffer) = 1;
        CscTransitionFcbOffline(pFcb, Buffer, 2, 2);
        inited = updated;
        goto LABEL_683;
      }
    }
    v13 = (unsigned __int8 *)Entry;
LABEL_625:
    inited = *(_DWORD *)&v276[3];
LABEL_626:
    v66 = 6647;
    goto LABEL_174;
  }
  if ( ((unsigned __int8)v294 & 1) == 0 && ((unsigned __int8)v294 & 2) == 0 )
  {
    v65 = *(_DWORD *)&v276[7];
    goto LABEL_790;
  }
  LODWORD(v293) = 0;
  v65 = *(_DWORD *)&v276[7];
  v288 = *((_BYTE *)Entry + 528) & 1;
  v218 = 0;
  if ( (v276[7] & 8) != 0 )
    v218 = v292;
  updated = CscUpdateShareInfoForLogicalView(
              (int)RxContext,
              *(_DWORD *)&v276[7] | (*((char *)Entry + 529) >> 7) & 0x800u,
              (int)Entry + 200,
              v299[3],
              (__int64)&v288,
              (PCUNICODE_STRING)&RxContext->TrackerHistory[7].FileName,
              (__int64)&v293,
              v218);
  v77 = updated;
  if ( updated < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        108,
        WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
        (unsigned int)updated);
LABEL_790:
    if ( v77 >= 0 )
      goto LABEL_170;
    goto LABEL_211;
  }
LABEL_170:
  v276[0] = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    WPP_SF_qqq(
      WPP_GLOBAL_Control->AttachedDevice,
      110,
      WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
      v277,
      pFcb,
      MrxSrvOpen);
  CscStoreEntryIsTransparentlyCached(v277, v276);
  BYTE1(v299[0]) = BYTE1(v299[0]) & 0xFD | (2 * (v276[0] & 1));
  if ( (v299[0] & 0x200) == 0 )
  {
    *(_DWORD *)(v12[1] + 4LL) &= ~0x1000000u;
    v13 = (unsigned __int8 *)Entry;
    goto LABEL_277;
  }
  v13 = (unsigned __int8 *)Entry;
  if ( (*((_BYTE *)Entry + 533) & 4) != 0 )
  {
    v66 = 6768;
    inited = -1073741766;
LABEL_174:
    p_EaBuffer = &RxContext->Create.EaBuffer;
    goto LABEL_175;
  }
  *(_DWORD *)(v12[1] + 4LL) |= 0x1000000u;
  v13 = (unsigned __int8 *)Entry;
  if ( (v299[0] & 1) == 0 || (*(_DWORD *)(v12[2] + 24LL) & 1) != 0 || (*((_BYTE *)Entry + 533) & 0x52) != 0 )
  {
    if ( (v299[0] & 0x10) != 0 )
    {
      v219 = RxContext->Create.PipeCompletionMode;
      if ( (unsigned int)v219 > 5 || (v220 = 45, !_bittest(&v220, v219)) )
      {
        if ( (*(_DWORD *)(v12[2] + 24LL) & 1) == 0 && (*((_BYTE *)Entry + 533) & 0x52) == 0 )
        {
          inited = -1073741300;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
          {
            WPP_SF_Dd(
              WPP_GLOBAL_Control->AttachedDevice,
              112,
              WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
              v219,
              -1073741300);
            v13 = (unsigned __int8 *)Entry;
          }
          v66 = 6834;
          goto LABEL_174;
        }
      }
    }
LABEL_277:
    if ( (v278 & 2) != 0 )
    {
      v221 = CscBumpGlobalNewlyCachedEpoch();
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 113, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids, v221);
      v13 = (unsigned __int8 *)Entry;
    }
    if ( (v278 & 0x40) != 0 )
    {
      *(_DWORD *)(v12[1] + 4LL) |= 0x800000u;
      v13 = (unsigned __int8 *)Entry;
      v222 = *((_BYTE *)Entry + 533);
      if ( (v222 & 0x12) == 0 && v222 >= 0 )
      {
        v66 = 6872;
        inited = -1073741766;
        goto LABEL_174;
      }
    }
    updated = 0;
    if ( *(int *)&v276[3] >= 0 && (v299[0] & 0x10) == 0 && (v299[0] & 0x200) == 0 )
    {
      updated = CscFcbForceFlowOpens(RxContext, pFcb);
      v160 = updated;
      if ( updated < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            114,
            WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
            (unsigned int)updated);
          v160 = updated;
        }
        if ( (unsigned __int8)CscTransitnOKToGoOffline(v160) )
        {
          LOBYTE(v299[0]) |= 0x12u;
          v275 = 1;
        }
        v223 = updated;
        inited = updated;
        *((_BYTE *)Entry + 532) |= 2u;
        *((_BYTE *)Entry + 535) |= 2u;
        if ( (v299[0] & 0x10) == 0 && v223 != -1073741638 )
        {
          if ( (unsigned int)(v223 + 1073741790) > 0x18 || (v224 = 17039361, !_bittest(&v224, v223 + 1073741790)) )
          {
            if ( v223 != -1073741565 )
            {
              v13 = (unsigned __int8 *)Entry;
              v66 = 6925;
              goto LABEL_174;
            }
          }
        }
      }
      v13 = (unsigned __int8 *)Entry;
    }
    if ( v275 && v7 && (v299[0] & 0x200) == 0 )
    {
      if ( !(unsigned __int8)CscLViewIsRootGhosted(*(_QWORD *)&pFcb->OpenCount) )
      {
        LOBYTE(v225) = 1;
        CscTransitionFcbOffline(pFcb, v225, 2, 2);
      }
      v13 = (unsigned __int8 *)Entry;
    }
    v94 = CscStoreQueryInformationEntryEx((_DWORD)v277, 0, (int)v13 + 120, (int)v13 + 56, (__int64)(v13 + 536), 0, 0);
    v13 = (unsigned __int8 *)Entry;
    v96 = (unsigned int)v94;
    *(_DWORD *)&v276[7] = v94;
    if ( v94 < 0 )
    {
      inited = v94;
      v66 = 6979;
      goto LABEL_174;
    }
    if ( (v299[0] & 4) != 0 && (*((_BYTE *)Entry + 528) & 0x10) == 0 && (*((_DWORD *)Entry + 30) & 0x20) != 0 )
    {
      HIDWORD(pFcb->SrvOpenList.Flink) |= 0xA000000u;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) == 0 )
      {
        v13 = (unsigned __int8 *)Entry;
      }
      else
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 115, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids);
        v96 = *(unsigned int *)&v276[7];
        v13 = (unsigned __int8 *)Entry;
      }
    }
    if ( (v299[0] & 0x10) != 0 && (v278 & 1) == 0 )
    {
      v97 = *((_DWORD *)v13 + 30);
      if ( (v97 & 0x20) == 0 && (v97 & 0x10) == 0 && RxContext->Create.PipeCompletionMode == 2 )
      {
        *((_QWORD *)&RxContext->9 + 25) = 4;
        v66 = 7016;
        inited = -1073741771;
        goto LABEL_174;
      }
    }
    Buffer = v287;
    if ( (v287 & 0x80000000) != 0 && (v299[0] & 0x10) == 0 )
    {
      v226 = *((_DWORD *)v13 + 30);
      if ( (v226 & 0x400) != 0 || (v226 & 0x80417) != 0 && (*((_DWORD *)v13 + 26) & 0x10) == 0 )
      {
        LODWORD(v140) = v287;
        *(_DWORD *)&v276[7] = v287;
        v66 = 7039;
        goto LABEL_784;
      }
    }
    v98 = (*((_DWORD *)v13 + 26) & 0x10) != 0;
    v13[531] = v98;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    {
      v152 = 89;
      v153 = 89;
      if ( (v278 & 1) == 0 )
        v152 = 78;
      if ( !v98 )
        v153 = 78;
      LOBYTE(v270) = v152;
      WPP_SF_ccDi(
        WPP_GLOBAL_Control->AttachedDevice,
        116,
        WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
        v153,
        v270,
        *((_DWORD *)Entry + 30),
        *((_QWORD *)Entry + 12));
      v96 = *(unsigned int *)&v276[7];
    }
    v13 = (unsigned __int8 *)Entry;
    if ( (*((_DWORD *)Entry + 30) & 0x20000) != 0 )
    {
      if ( (*((_BYTE *)Entry + 534) & 0x10) != 0 )
      {
        LODWORD(MrxSrvOpen->Key) |= 0x1080u;
        v13 = (unsigned __int8 *)Entry;
      }
      if ( (*((_DWORD *)v13 + 30) & 0x20000) != 0 )
      {
        v227 = v12[1];
        v228 = *(_DWORD *)(v227 + 4);
        if ( (v228 & 0x1000) == 0 && (v299[0] & 0x40) != 0 && (v299[0] & 0x10) != 0 && (v13[534] & 0x10) == 0 )
        {
          *(_DWORD *)(v227 + 4) = v228 | 0x1000;
          v13 = (unsigned __int8 *)Entry;
        }
      }
    }
    if ( (*((_DWORD *)v13 + 30) & 0x4000) != 0 )
    {
      *(_DWORD *)(v12[1] + 4LL) |= 0x800u;
      v13 = (unsigned __int8 *)Entry;
    }
    v99 = v13[528];
    Buffer = *(unsigned int *)&v276[3];
    if ( (v99 & 8) == 0 || v275 || *(int *)&v276[3] >= 0 && (v13[535] & 2) == 0 || (v99 & 0x20) == 0 )
      goto LABEL_296;
    v161 = *(_DWORD *)&v276[3];
    if ( (v13[535] & 2) != 0 )
      v161 = updated;
    if ( v161 == -1073741772 )
    {
      if ( (v299[0] & 0x40) != 0 && !v13[531] )
      {
        v289 = 1;
        v162 = CscStoreSetInformationEntry((__int64)v277, 0, 0, 0, 0, &v289, 0);
        v163 = v162;
        *(_DWORD *)&v276[7] = v162;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
        {
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 117, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids, v162);
          v163 = *(_DWORD *)&v276[7];
        }
        v13 = (unsigned __int8 *)Entry;
        if ( v163 >= 0 )
        {
          inited = -1073741772;
LABEL_1052:
          v66 = 7237;
          goto LABEL_174;
        }
      }
      if ( (v299[0] & 0x200) != 0 )
      {
        v282 = 1;
        inited = -1073741772;
        goto LABEL_1052;
      }
      v229 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) == 0 )
        goto LABEL_1033;
      v230 = 118;
      goto LABEL_1032;
    }
    if ( v161 == -1073741790 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 119, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids);
        LODWORD(v13) = (_DWORD)Entry;
      }
      CscStoreSetExplicitAccessEntry((_DWORD)v277, 0, (_DWORD)v13 + 200, 0, 1);
      v13 = (unsigned __int8 *)Entry;
      inited = -1073741790;
      goto LABEL_1052;
    }
    if ( *(_DWORD *)&v276[3] == -1073741766 )
      goto LABEL_1046;
    if ( v161 == -1073741638 )
    {
      if ( !v13[531] )
      {
LABEL_1046:
        if ( (v299[0] & 0x200) == 0 )
        {
          v229 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) == 0 )
          {
            goto LABEL_1033;
          }
          v230 = 120;
LABEL_1032:
          WPP_SF_(v229->AttachedDevice, v230, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids);
LABEL_1033:
          LOBYTE(v299[0]) |= 0x12u;
          CscTransitionFcbOffline(pFcb, 0, 8, 0);
          v96 = *(unsigned int *)&v276[7];
          Buffer = *(unsigned int *)&v276[3];
          inited = 0;
          v13 = (unsigned __int8 *)Entry;
          goto LABEL_296;
        }
        v282 = 1;
        inited = v161;
      }
    }
    else if ( v161 == -1073741565 && v13[531] )
    {
      goto LABEL_1046;
    }
    if ( inited < 0 )
      goto LABEL_1052;
LABEL_296:
    v100 = v13[528];
    if ( (v100 & 8) != 0 && (int)Buffer >= 0 && (v278 & 1) == 0 )
    {
      v95 = v13[531];
      Buffer = *((_DWORD *)v13 + 12) & 0x10;
      if ( (_BYTE)v95 != ((*((_DWORD *)v13 + 12) & 0x10) != 0) )
      {
        if ( (v100 & 0x20) == 0 )
        {
          v66 = 7346;
          inited = -1073741595;
          goto LABEL_174;
        }
        if ( (v299[0] & 0x40) == 0 )
          goto LABEL_1058;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
        {
          v170 = 89;
          if ( !(_DWORD)Buffer )
            v170 = 78;
          LOBYTE(v270) = v170;
          WPP_SF_cc(WPP_GLOBAL_Control->AttachedDevice, 121, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids);
          v13 = (unsigned __int8 *)Entry;
        }
        v171 = CscStoreChangeEntryTypeForCreate(&v277, 0, v13, 0, v270);
        v96 = (unsigned int)v171;
        if ( v171 >= 0 )
        {
          v231 = CscStoreQueryInformationEntryEx(
                   (_DWORD)v277,
                   0,
                   (int)Entry + 120,
                   (int)Entry + 56,
                   (__int64)Entry + 536,
                   0,
                   0);
          v96 = (unsigned int)v231;
          if ( v231 < 0 )
          {
            v13 = (unsigned __int8 *)Entry;
            inited = v231;
            v66 = 7295;
            goto LABEL_174;
          }
          *((_BYTE *)Entry + 531) = (*((_DWORD *)Entry + 26) & 0x10) != 0;
          v13 = (unsigned __int8 *)Entry;
          LODWORD(v278) = 1;
        }
        else
        {
          v13 = (unsigned __int8 *)Entry;
          if ( !v277 )
          {
            inited = v171;
            v66 = 7283;
            goto LABEL_174;
          }
        }
        if ( (v299[0] & 0x40) == 0 || (v96 & 0x80000000) != 0LL )
        {
LABEL_1058:
          LOBYTE(v299[0]) |= 0x12u;
          v13[532] |= 2u;
          CscTransitionFcbOffline(pFcb, 0, 8, 0);
          v232 = Entry;
          *(_OWORD *)Entry = *(_OWORD *)((char *)Entry + 56);
          v232[1] = *(_OWORD *)((char *)v232 + 72);
          v232[2] = *(_OWORD *)((char *)v232 + 88);
          *((_QWORD *)v232 + 6) = *((_QWORD *)v232 + 13);
          *((_BYTE *)Entry + 534) |= 0x20u;
          v13 = (unsigned __int8 *)Entry;
        }
      }
    }
    if ( (v299[0] & 0x10) == 0 )
    {
LABEL_298:
      *((_QWORD *)v13 + 14) = v13 + 136;
      v13 = (unsigned __int8 *)Entry;
      if ( !*((_BYTE *)Entry + 531) && (*(_DWORD *)(v12[2] + 24LL) & 1) != 0 && (*((_BYTE *)Entry + 533) & 4) == 0 )
      {
        v66 = 7554;
        inited = -1073741565;
        goto LABEL_174;
      }
      if ( (v278 & 0x80u) != 0LL )
      {
LABEL_419:
        *((_BYTE *)Entry + 529) |= 2u;
        *((_BYTE *)Entry + 529) |= 0x10u;
        *((_DWORD *)Entry + 84) |= 0x800000u;
        *(_DWORD *)(v12[1] + 4LL) |= 0x1000000u;
        v13 = (unsigned __int8 *)Entry;
        BYTE1(v299[0]) |= 2u;
        if ( (*((_DWORD *)Entry + 30) & 0x4000) != 0 && (v278 & 0x80u) == 0LL )
        {
          *((_BYTE *)Entry + 529) |= 0x40u;
          goto LABEL_803;
        }
        goto LABEL_420;
      }
      if ( (v65 & 0x40000) != 0 && (*((_DWORD *)Entry + 30) & 0x1000000) == 0 )
      {
        if ( v299[3] == 4 )
        {
LABEL_302:
          if ( (*((_DWORD *)Entry + 30) & 0x800000) != 0 )
          {
            *((_BYTE *)Entry + 529) |= 2u;
            *((_BYTE *)Entry + 529) |= 0x10u;
            *((_DWORD *)Entry + 83) |= 0x800000u;
            *(_DWORD *)(v12[1] + 4LL) &= ~0x1000000u;
            BYTE1(v299[0]) &= ~2u;
LABEL_803:
            v13 = (unsigned __int8 *)Entry;
          }
LABEL_420:
          if ( v13[540] )
          {
            v238 = v12[1];
            v239 = *(_DWORD *)(v238 + 4);
            if ( (v239 & 0x1000000) != 0 )
            {
              *(_DWORD *)(v238 + 4) = v239 | 0x2000000;
              v13 = (unsigned __int8 *)Entry;
            }
          }
          v126 = RxContext->Create.PipeCompletionMode;
          if ( v126 > 5 || (v127 = 45, !_bittest(&v127, v126)) || (v278 & 1) != 0 || (v299[0] & 0x10) == 0 )
          {
            v128 = MrxSrvOpen;
            goto LABEL_424;
          }
          Buffer = *((_DWORD *)v13 + 30) & 0x30;
          if ( (*((_DWORD *)v13 + 30) & 0x30) != 0 && (v299[0] & 0x40) == 0 )
          {
            v66 = 7648;
            inited = -1073741108;
            goto LABEL_174;
          }
          if ( v126 != 3 || (_DWORD)Buffer )
          {
            v13[529] |= 8u;
            *((_BYTE *)Entry + 534) |= 0x20u;
            *((_QWORD *)Entry + 12) = 0;
            v240 = Entry;
            if ( !*((_BYTE *)Entry + 531) )
            {
              *((_DWORD *)Entry + 84) |= 1u;
              v240 = Entry;
            }
            v240[84] |= 6u;
            *((_DWORD *)Entry + 83) |= 0x30u;
            *((_BYTE *)Entry + 529) |= 2u;
            v13 = (unsigned __int8 *)Entry;
          }
          if ( (*((_DWORD *)v13 + 30) & 0x20) != 0 )
          {
            v13[532] |= 0x80u;
            v13 = (unsigned __int8 *)Entry;
          }
          if ( (*((_DWORD *)v13 + 30) & 0x30) != 0 )
          {
            v291 = (v13[531] != 0) + 1;
            CscNotifyReportChange(RxContext, v291, 1);
            v13 = (unsigned __int8 *)Entry;
          }
          if ( (*((_DWORD *)v13 + 30) & 0x10010) != 0 )
          {
            v241 = CscStoreCheckAccessToOverwriteFile(v277, v292, v95, v96);
            if ( v241 < 0 )
            {
              v13 = (unsigned __int8 *)Entry;
              inited = v241;
              v66 = 7724;
              goto LABEL_174;
            }
            v128 = MrxSrvOpen;
            LODWORD(MrxSrvOpen[1].Context2) = 2032127;
            *((_BYTE *)Entry + 532) |= 0x20u;
            *((_BYTE *)Entry + 529) |= 0x20u;
            *((_BYTE *)Entry + 534) |= 0x40u;
          }
          else
          {
            v242 = RxContext->Create.PipeCompletionMode;
            v128 = MrxSrvOpen;
            if ( v242 )
            {
              if ( v242 - 4 > 1 )
              {
LABEL_1108:
                v243 = v291;
                if ( !v291 )
                  v243 = 28;
                v291 = v243;
LABEL_424:
                v129 = RxContext->Create.PipeCompletionMode;
                if ( v129 <= 5 )
                {
                  v130 = 53;
                  if ( _bittest(&v130, v129) )
                  {
                    if ( (v299[0] & 0x10) == 0 || (v299[0] & 0x200) == 0 )
                    {
                      v13[529] = v13[529] & 0xFE | ((v299[0] & 0x10) == 0);
                      v13 = (unsigned __int8 *)Entry;
                      if ( !*((_BYTE *)Entry + 531) && (v278 & 1) == 0 )
                      {
                        *((_BYTE *)Entry + 532) |= 0x80u;
                        v13 = (unsigned __int8 *)Entry;
                      }
                    }
                  }
                }
                if ( (v299[0] & 0x40) != 0 && (v13[529] & 8) == 0 && (v299[0] & 0x10) != 0 )
                {
                  *(_OWORD *)v13 = *(_OWORD *)(v13 + 56);
                  *((_OWORD *)v13 + 1) = *(_OWORD *)(v13 + 72);
                  *((_OWORD *)v13 + 2) = *(_OWORD *)(v13 + 88);
                  *((_QWORD *)v13 + 6) = *((_QWORD *)v13 + 13);
                  *((_BYTE *)Entry + 528) |= 2u;
                  v13 = (unsigned __int8 *)Entry;
                }
                if ( (v278 & 1) == 0 )
                {
LABEL_428:
                  v131 = *(_DWORD *)&v276[3];
                  if ( (v299[0] & 0x10) == 0 && *(int *)&v276[3] >= 0 )
                  {
                    if ( ((__int64)v128->Key & 0x200) != 0
                      || (v174 = *(&RxContext->TrackerHistory[3].Flags + 1), (v174 & 2) == 0) && (v174 & 1) == 0 )
                    {
                      *(_DWORD *)(v12[2] + 24LL) |= 0x10000u;
                      v13 = (unsigned __int8 *)Entry;
                    }
                  }
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
                  {
                    v158 = 89;
                    v159 = 89;
                    if ( (*(_DWORD *)(v12[2] + 24LL) & 0x10000) != 0 )
                      v159 = 78;
                    LOBYTE(v272) = v159;
                    if ( ((__int64)v128->Key & 0x200) != 0 )
                      v158 = 78;
                    LOBYTE(String2) = v158;
                    WPP_SF_DDcc(
                      WPP_GLOBAL_Control->AttachedDevice,
                      126,
                      WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
                      RxContext->TrackerHistory[4].AcquireRelease,
                      *(&RxContext->TrackerHistory[3].Flags + 1),
                      String2,
                      v272);
                    v128 = MrxSrvOpen;
                    v131 = *(_DWORD *)&v276[3];
                    v13 = (unsigned __int8 *)Entry;
                  }
                  if ( (v299[0] & 0x10) != 0 )
                    goto LABEL_431;
                  if ( !v13[531] && !v128[1].NodeReferenceCount )
                  {
                    if ( (*(_DWORD *)(v12[2] + 24LL) & 0x10000) == 0
                      && ((__int64)v128->Key & 3) == 0
                      && !RxContext->TrackerHistory[4].AcquireRelease
                      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
                    {
                      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 127, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids);
                      v128 = MrxSrvOpen;
                      v13 = (unsigned __int8 *)Entry;
                    }
                    v131 = *(_DWORD *)&v276[3];
                  }
                  if ( (v299[0] & 0x10) != 0 || v131 < 0 || v13[531] )
                  {
LABEL_431:
                    if ( (v13[532] & 1) == 0 && (*((_DWORD *)v13 + 30) & 0x10) != 0 )
                    {
                      *((_DWORD *)v13 + 83) |= 0x10u;
                      *((_BYTE *)Entry + 529) |= 4u;
                      *((_BYTE *)Entry + 529) |= 2u;
                      *((_BYTE *)Entry + 536) = 0;
                      if ( (v278 & 1) == 0 && (v299[0] & 0x10) != 0 )
                      {
                        *((_DWORD *)Entry + 83) |= 0x20u;
                        *((_DWORD *)Entry + 84) &= ~0x20u;
                      }
                      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
                      {
                        WPP_SF_(
                          WPP_GLOBAL_Control->AttachedDevice,
                          130,
                          WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids);
                        v128 = MrxSrvOpen;
                      }
                      v131 = *(_DWORD *)&v276[3];
                      v13 = (unsigned __int8 *)Entry;
                    }
                    if ( (v299[0] & 0x10) != 0 || v131 < 0 || (v278 & 1) != 0 )
                    {
LABEL_433:
                      v132 = *(_QWORD *)(*((_QWORD *)&RxContext->9 + 18) + 8LL);
                      v133 = *(void **)(v132 + 32);
                      if ( !v133 )
                        v133 = *(void **)(v132 + 48);
                      if ( SeTokenIsAdmin(v133) )
                        *(_DWORD *)(v12[2] + 24LL) |= 0x4000u;
                      v13 = (unsigned __int8 *)Entry;
                      if ( *((char *)Entry + 533) < 0 )
                      {
                        if ( (*(_DWORD *)(v12[2] + 24LL) & 0x4000) == 0 )
                        {
                          v66 = 8277;
                          inited = -1073741790;
                          goto LABEL_174;
                        }
                        v134 = MrxSrvOpen;
                        LODWORD(MrxSrvOpen->Key) |= 0x1080u;
                        *(_DWORD *)(v12[2] + 24LL) |= 0x800u;
                        v13 = (unsigned __int8 *)Entry;
                      }
                      else
                      {
                        v134 = MrxSrvOpen;
                      }
                      v135 = (v299[0] & 0x10) == 0
                          || (v13[533] & 0x80u) != 0
                          || (v13[534] & 0x40) != 0
                          || (v278 & 1) != 0;
                      v136 = v13[533];
                      v137 = (v136 & 0x20) != 0;
                      if ( (v136 & 2) != 0 )
                        v137 |= 2u;
                      if ( v135 || (v13[532] & 0x20) != 0 )
                        p_Context2 = 0;
                      else
                        p_Context2 = (__int64)&v134[1].Context2;
                      v139 = CscSrvOpenOpenObtainStoreHandle(
                               (_DWORD)pFcb,
                               (_DWORD)v134,
                               (_DWORD)v277,
                               v13[531],
                               v137,
                               !v135,
                               v292,
                               p_Context2);
                      *(_DWORD *)&v276[7] = v139;
                      v140 = (unsigned int)v139;
                      if ( v139 < 0 )
                      {
                        if ( v139 != -1073741436 && v139 != -1073741756 || !v7 )
                        {
                          v13 = (unsigned __int8 *)Entry;
                          inited = v139;
                          v66 = 8351;
                          goto LABEL_174;
                        }
                        v13 = (unsigned __int8 *)Entry;
                        inited = 0;
                        v147 = 0;
                        v66 = 8346;
                        goto LABEL_766;
                      }
                      v13 = (unsigned __int8 *)Entry;
                      if ( (*((_BYTE *)Entry + 529) & 0x20) != 0 )
                      {
                        v141 = MrxSrvOpen;
                        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
                        {
                          WPP_SF_Dd(
                            WPP_GLOBAL_Control->AttachedDevice,
                            137,
                            WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
                            LODWORD(MrxSrvOpen[1].Context2),
                            MrxSrvOpen->Key);
                          v13 = (unsigned __int8 *)Entry;
                        }
                        if ( ((__int64)v141->Key & 0x100000) == 0 )
                        {
                          v169 = CscStoreSetExplicitAccessEntry((_DWORD)v277, 0, (int)v13 + 200, v141[1].Context2, 3);
                          v13 = (unsigned __int8 *)Entry;
                          v140 = (unsigned int)v169;
                          *(_DWORD *)&v276[7] = v169;
                          if ( v169 < 0 )
                          {
                            v66 = 8384;
                            goto LABEL_784;
                          }
                        }
                      }
                      else
                      {
                        v141 = MrxSrvOpen;
                      }
                      if ( (*(_DWORD *)(v12[1] + 4LL) & 0x80u) == 0 )
                      {
                        v275 = 0;
                        v142 = CscStoreQueryPinInformationEntry(v277, v13 + 200, v13 + 328, &v275);
                        *(_DWORD *)&v276[7] = v142;
                        if ( v142 < 0 )
                        {
                          v13 = (unsigned __int8 *)Entry;
                          inited = v142;
                          v66 = 8408;
                          goto LABEL_174;
                        }
                        v143 = Entry;
                        v140 = *((unsigned __int8 *)Entry + 328);
                        if ( *((_WORD *)Entry + 164) )
                        {
                          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
                          {
                            WPP_SF_Dd(
                              WPP_GLOBAL_Control->AttachedDevice,
                              138,
                              WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
                              *((unsigned __int8 *)Entry + 328),
                              *((unsigned __int8 *)Entry + 329));
                          }
                          *(_DWORD *)(v12[1] + 4LL) |= 0x80u;
                          v143 = Entry;
                        }
                        v143[533] = v143[533] & 0xFE | v275 & 1;
                        v13 = (unsigned __int8 *)Entry;
                      }
                      Buffer = *(unsigned int *)&v276[3];
                      if ( (v299[0] & 0x10) != 0 || *(int *)&v276[3] < 0 || v13[531] )
                      {
LABEL_457:
                        if ( (v13[532] & 0x80u) != 0
                          || (v13[529] & 2) != 0
                          && (*((_DWORD *)v13 + 30) & 0x20) != 0
                          && (*((_DWORD *)v13 + 83) & 0x20) != 0
                          && (*((_DWORD *)v13 + 84) & 0x20) == 0 )
                        {
                          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
                          {
                            WPP_SF_(
                              WPP_GLOBAL_Control->AttachedDevice,
                              139,
                              WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids);
                          }
                          v252 = CscStoreInvalidateDataEntry(v277, (v299[0] & 0x10) != 0, v140);
                          v13 = (unsigned __int8 *)Entry;
                          LODWORD(v140) = v252;
                          *(_DWORD *)&v276[7] = v252;
                          if ( v252 < 0 )
                          {
                            v66 = 8485;
                            goto LABEL_784;
                          }
                          Buffer = *(unsigned int *)&v276[3];
                        }
                        if ( (v13[529] & 3) == 0 )
                          goto LABEL_723;
                        memset(v300, 0, sizeof(v300));
                        v285 = CscConvertSmbCacheModeToStoreCacheMode(v299[3]);
                        LOBYTE(v144) = 1;
                        v145 = v285;
                        v146 = CscStoreQueryInformationEntryEx((_DWORD)v277, v144, (unsigned int)v300, 0, 0, 0, 0);
                        *(_DWORD *)&v276[7] = v146;
                        LODWORD(v140) = v146;
                        if ( v146 < 0 )
                        {
                          v147 = 1;
                          v13 = (unsigned __int8 *)Entry;
                          v66 = 8523;
                          if ( (v299[0] & 0x10) != 0 )
                            inited = v146;
                          goto LABEL_785;
                        }
                        v253 = (char *)Entry;
                        if ( (*((_BYTE *)Entry + 529) & 2) != 0
                          && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
                        {
                          WPP_SF_DDd(
                            WPP_GLOBAL_Control->AttachedDevice,
                            140,
                            WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
                            *((unsigned int *)Entry + 30),
                            *((_DWORD *)Entry + 84),
                            *((_DWORD *)Entry + 83));
                          v253 = (char *)Entry;
                        }
                        if ( (v253[529] & 1) != 0
                          && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
                        {
                          WPP_SF_(
                            WPP_GLOBAL_Control->AttachedDevice,
                            141,
                            WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids);
                          v253 = (char *)Entry;
                        }
                        v254 = v253[529];
                        v255 = v253 + 536;
                        if ( (v254 & 4) == 0 )
                          v255 = 0;
                        v256 = (__int64)(v253 + 332);
                        v257 = 0;
                        if ( (v254 & 1) != 0 )
                          v257 = (__int64)v253;
                        if ( (v254 & 2) == 0 )
                          v256 = 0;
                        v258 = CscStoreSetInformationEntry((__int64)v277, v256, 0, (__int64)(v253 + 128), v257, v255, 0);
                        v13 = (unsigned __int8 *)Entry;
                        LODWORD(v140) = v258;
                        *(_DWORD *)&v276[7] = v258;
                        if ( v258 < 0 )
                        {
                          v147 = 1;
                          v66 = 8568;
                          if ( (v299[0] & 0x10) != 0 )
                            inited = v258;
LABEL_785:
                          if ( inited < 0 )
                            goto LABEL_174;
LABEL_765:
                          if ( (int)v140 >= 0 )
                            goto LABEL_174;
LABEL_766:
                          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
                          {
                            WPP_SF_Dd(
                              WPP_GLOBAL_Control->AttachedDevice,
                              150,
                              WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
                              (unsigned int)v140,
                              inited);
                            LODWORD(v140) = *(_DWORD *)&v276[7];
                            v13 = (unsigned __int8 *)Entry;
                          }
                          if ( (v299[0] & 0x10) != 0 )
                          {
                            inited = v140;
                            goto LABEL_174;
                          }
                          if ( v147 && v277 && (*((_DWORD *)v13 + 26) & 0x10) == 0 )
                          {
                            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
                            {
                              WPP_SF_(
                                WPP_GLOBAL_Control->AttachedDevice,
                                151,
                                WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids);
                              v13 = (unsigned __int8 *)Entry;
                            }
                            *((_DWORD *)v13 + 84) = 32;
                            *((_DWORD *)Entry + 83) = 0;
                            if ( (int)CscStoreSetInformationEntry((__int64)v277, (__int64)Entry + 332, 0, 0, 0, 0, 0) < 0 )
                            {
                              if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                              {
LABEL_1283:
                                v263 = CscForceFcbStoreEntryClosed(RxContext, (v299[0] & 0x10) != 0);
                                v13 = (unsigned __int8 *)Entry;
                                if ( v263 >= 0 )
                                {
                                  if ( v277 && (*((_BYTE *)Entry + 532) & 0x10) == 0 )
                                  {
                                    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                                      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
                                    {
                                      WPP_SF_qqq(
                                        WPP_GLOBAL_Control->AttachedDevice,
                                        154,
                                        WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
                                        v277,
                                        pFcb,
                                        MrxSrvOpen);
                                    }
                                    CscStoreDereferenceEntry(&v277);
                                    *((_BYTE *)Entry + 532) |= 0x10u;
                                    v13 = (unsigned __int8 *)Entry;
                                  }
                                  v264 = v12[1];
                                  if ( v264 )
                                  {
                                    *(_DWORD *)(v264 + 24) = *(_DWORD *)&v276[7];
                                    v13 = (unsigned __int8 *)Entry;
                                  }
                                }
                                else
                                {
                                  inited = *(_DWORD *)&v276[7];
                                }
                                goto LABEL_174;
                              }
                              if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
                                WPP_SF_d(
                                  WPP_GLOBAL_Control->AttachedDevice,
                                  152,
                                  WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
                                  v287);
                            }
                            LODWORD(v140) = *(_DWORD *)&v276[7];
                          }
                          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
                          {
                            WPP_SF_d(
                              WPP_GLOBAL_Control->AttachedDevice,
                              153,
                              WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
                              (unsigned int)v140);
                          }
                          goto LABEL_1283;
                        }
                        if ( (*((_BYTE *)Entry + 529) & 1) != 0
                          && (*((_BYTE *)Entry + 528) & 0x20) != 0
                          && (v299[0] & 0x10) == 0
                          && !*((_BYTE *)Entry + 531) )
                        {
                          DatabaseInformation = CscStoreQueryDatabaseInformation((char *)Entry + 272, 0, 0, 0);
                          v13 = (unsigned __int8 *)Entry;
                          *(_DWORD *)&v276[7] = DatabaseInformation;
                          if ( !DatabaseInformation && (*((_DWORD *)Entry + 68) & 1) == 0 )
                          {
                            v195 = ((__int64)pFcb[1].Header.FilterContexts.Flink & 0x4000) != 0;
                            if ( (v278 & 1) == 0 && v195 != ((*((_DWORD *)Entry + 30) & 0x80) != 0) )
                            {
                              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
                              {
                                WPP_SF_(
                                  WPP_GLOBAL_Control->AttachedDevice,
                                  142,
                                  WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids);
                              }
                              v196 = CscStoreEncryptDecryptEntry(v277, v195);
                              v13 = (unsigned __int8 *)Entry;
                              *(_DWORD *)&v276[7] = v196;
                            }
                            v145 = v285;
                          }
                        }
                        if ( (v13[529] & 0x10) != 0 )
                        {
                          v197 = CscStoreUpdateShareProperty(v277, v145, v300[2]);
                          v13 = (unsigned __int8 *)Entry;
                          LODWORD(v140) = v197;
                          *(_DWORD *)&v276[7] = v197;
                          if ( v197 < 0 )
                          {
                            v66 = 8626;
                            goto LABEL_784;
                          }
                        }
                        v260 = v13[529];
                        if ( (v260 & 0x40) != 0 )
                        {
                          v285 = 0;
                          v290 = v13[528] & 1;
                          v261 = 0;
                          if ( (v65 & 8) != 0 )
                            v261 = v292;
                          *(_DWORD *)&v276[7] = CscUpdateShareInfoForLogicalView(
                                                  (int)RxContext,
                                                  v65 | (v260 >> 7) & 0x800u,
                                                  (int)v13 + 200,
                                                  v299[3],
                                                  (__int64)&v290,
                                                  (PCUNICODE_STRING)&RxContext->TrackerHistory[7].FileName,
                                                  (__int64)&v285,
                                                  v261);
                          if ( *(int *)&v276[7] >= 0
                            || WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) == 0 )
                          {
                            v13 = (unsigned __int8 *)Entry;
                            v141 = MrxSrvOpen;
                            Buffer = *(unsigned int *)&v276[3];
LABEL_723:
                            if ( (v13[529] & 8) == 0 )
                              goto LABEL_724;
                            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
                            {
                              WPP_SF_d(
                                WPP_GLOBAL_Control->AttachedDevice,
                                144,
                                WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
                                *((unsigned int *)v13 + 12));
                              v13 = (unsigned __int8 *)Entry;
                            }
                            *(_OWORD *)(v13 + 408) = *(_OWORD *)v13;
                            *(_OWORD *)(v13 + 424) = *((_OWORD *)v13 + 1);
                            *((_QWORD *)v13 + 55) = *((_QWORD *)v13 + 4);
                            *((_DWORD *)Entry + 110) = *((_DWORD *)Entry + 12);
                            v193 = (char *)Entry;
                            if ( !*((_DWORD *)Entry + 110) )
                            {
                              *((_DWORD *)Entry + 110) = 128;
                              v193 = (char *)Entry;
                            }
                            v194 = CscStoreUpdateLocalBasicInformationEntry(v277, (v299[0] & 0x10) != 0, v193 + 408, 0);
                            v13 = (unsigned __int8 *)Entry;
                            LODWORD(v140) = v194;
                            *(_DWORD *)&v276[7] = v194;
                            if ( v194 >= 0 )
                            {
                              Buffer = *(unsigned int *)&v276[3];
LABEL_724:
                              if ( (v299[0] & 0x10) == 0 )
                              {
                                if ( (int)Buffer < 0 )
                                {
                                  v66 = 8825;
                                  goto LABEL_174;
                                }
                                goto LABEL_742;
                              }
                              updated = 1;
                              if ( (v299[0] & 0x40) != 0 || (v13[534] & 0x20) != 0 )
                              {
                                *((_DWORD *)v13 + 112) = 1;
                                *((_QWORD *)Entry + 57) = (char *)Entry + 48;
                                *((_QWORD *)Entry + 58) = &updated;
                                *((_QWORD *)Entry + 59) = Entry;
                                *((_QWORD *)Entry + 60) = (char *)Entry + 8;
                                *((_QWORD *)Entry + 61) = (char *)Entry + 16;
                                *((_QWORD *)Entry + 62) = (char *)Entry + 24;
                                *((_QWORD *)Entry + 63) = (char *)Entry + 32;
                                *((_QWORD *)Entry + 64) = (char *)Entry + 40;
                                *((_QWORD *)Entry + 65) = (char *)Entry + 40;
                                RxFinishFcbInitialization(
                                  pFcb,
                                  (RX_FILE_TYPE)(60450 - (*((_BYTE *)Entry + 531) != 0)),
                                  (PFCB_INIT_PACKET)((char *)Entry + 448));
                                v13 = (unsigned __int8 *)Entry;
                              }
                              if ( !RxContext->pFobx )
                              {
                                NetFobx = RxCreateNetFobx(RxContext, v141);
                                RxContext->pFobx = NetFobx;
                                if ( !NetFobx )
                                {
                                  v13 = (unsigned __int8 *)Entry;
                                  v66 = 8744;
                                  inited = -1073741670;
                                  goto LABEL_174;
                                }
                                *((_BYTE *)Entry + 528) |= 0x80u;
                                v13 = (unsigned __int8 *)Entry;
                              }
                              if ( (v278 & 1) != 0 || (v186 = RxContext->Create.PipeCompletionMode, v186 == 2) )
                              {
                                *((_QWORD *)&RxContext->9 + 25) = 2;
                              }
                              else if ( v186 - 4 <= 1 )
                              {
                                *((_QWORD *)&RxContext->9 + 25) = 3;
                              }
                              else
                              {
                                *((_QWORD *)&RxContext->9 + 25) = v186 != 0;
                              }
                              if ( v13[531] || (*((_DWORD *)&RxContext->9 + 28) & 0x23) == 0 )
                              {
                                LODWORD(v141->Key) |= 0x200u;
                                v187 = &RxContext->TrackerHistory[4];
                                *(_DWORD *)(v12[2] + 24LL) |= 0x10000u;
                                RxContext->TrackerHistory[4].AcquireRelease = 0;
                                if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                                {
LABEL_741:
                                  v13 = (unsigned __int8 *)Entry;
LABEL_742:
                                  if ( (v13[532] & 1) != 0
                                    || (v13[533] & 0x40) != 0 && (*(_DWORD *)(v12[2] + 24LL) & 1) == 0 )
                                  {
                                    *(_DWORD *)(v12[2] + 24LL) |= 8u;
                                  }
                                  inited = CscCreateAndInitializeFobxContext(RxContext->pFobx, v12, 0, 0);
                                  if ( inited )
                                  {
                                    v13 = (unsigned __int8 *)Entry;
                                    v66 = 8860;
                                    goto LABEL_174;
                                  }
                                  v188 = (char *)Entry;
                                  if ( (*((_BYTE *)Entry + 534) & 4) != 0 && (*((_BYTE *)Entry + 532) & 0x40) != 0 )
                                  {
                                    *(_DWORD *)(*v12 + 4LL) |= 0x40u;
                                    ++*(_DWORD *)(v12[1] + 76LL);
                                    v188 = (char *)Entry;
                                  }
                                  if ( v188[534] < 0 )
                                  {
                                    *(_DWORD *)(*v12 + 4LL) |= 0x200u;
                                    v188 = (char *)Entry;
                                  }
                                  if ( v188[528] >= 0 && (v188[532] & 4) == 0 )
                                  {
                                    *(_DWORD *)(*v12 + 4LL) |= 2u;
                                    *(_QWORD *)(*v12 + 64LL) = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v295 + 48) + 352LL)
                                                                         + 144LL);
                                    v188 = (char *)Entry;
                                  }
                                  if ( (v188[532] & 0x40) != 0 )
                                  {
                                    *(_DWORD *)(*v12 + 4LL) |= 1u;
                                    v188 = (char *)Entry;
                                  }
                                  if ( (v299[0] & 0x200) == 0
                                    || v188[539]
                                    || (*(_DWORD *)(v12[2] + 24LL) & 1) != 0
                                    || (v188[533] & 0x52) != 0
                                    || (v188[528] & 0x40) != 0 )
                                  {
                                    v189 = CscApplyStoreHandleToFcbOrDeref((PMRX_FCB)RxContext, v277);
                                    v192 = (unsigned int)v189;
                                    *(_DWORD *)&v276[7] = v189;
                                    *((_BYTE *)Entry + 532) |= 0x10u;
                                    if ( v189 < 0 )
                                    {
                                      v13 = (unsigned __int8 *)Entry;
                                      inited = v189;
                                      v66 = 8952;
                                      goto LABEL_174;
                                    }
                                  }
                                  else
                                  {
                                    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                                      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
                                    {
                                      WPP_SF_q(
                                        WPP_GLOBAL_Control->AttachedDevice,
                                        147,
                                        WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
                                        v12[1]);
                                    }
                                    v262 = v12[2];
                                    if ( *(_QWORD *)(v262 + 8) )
                                    {
                                      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                                        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
                                      {
                                        WPP_SF_qqq(
                                          WPP_GLOBAL_Control->AttachedDevice,
                                          148,
                                          WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
                                          v277,
                                          pFcb,
                                          v141);
                                      }
                                      *(_DWORD *)&v276[7] = CscStoreCloseEntryHandle(*(_QWORD *)(v12[2] + 8LL), 0, 0);
                                      *(_QWORD *)(v12[2] + 8LL) = 0;
                                    }
                                    else if ( *(_QWORD *)(v262 + 16) )
                                    {
                                      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                                        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
                                      {
                                        WPP_SF_qqq(
                                          WPP_GLOBAL_Control->AttachedDevice,
                                          149,
                                          WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
                                          v277,
                                          pFcb,
                                          v141);
                                      }
                                      *(_DWORD *)&v276[7] = CscStoreCloseEntryHandle(*(_QWORD *)(v12[2] + 16LL), 0, 0);
                                      *(_QWORD *)(v12[2] + 16LL) = 0;
                                    }
                                    CscStoreDereferenceEntry(&v277);
                                    *((_BYTE *)Entry + 532) |= 0x10u;
                                  }
                                  v66 = 0;
                                  *(_DWORD *)(v12[1] + 72LL) = CscQueryGlobalNewlyCachedEpoch(v192, Buffer, v190, v191);
                                  v277 = 0;
                                  if ( (*(_DWORD *)(v12[2] + 24LL) & 1) != 0 )
                                    ++*(_DWORD *)(v12[1] + 20LL);
                                  LODWORD(v140) = *(_DWORD *)&v276[7];
                                  if ( (*(_DWORD *)(v12[2] + 24LL) & 8) != 0 )
                                    *(_DWORD *)(v12[1] + 4LL) |= 0x20u;
                                  v13 = (unsigned __int8 *)Entry;
                                  v147 = 0;
                                  goto LABEL_765;
                                }
                                if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
                                  WPP_SF_q(
                                    WPP_GLOBAL_Control->AttachedDevice,
                                    145,
                                    WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
                                    v141);
                              }
                              else
                              {
                                v187 = &RxContext->TrackerHistory[4];
                                v141->SrvOpenQLinks.Flink = (struct _LIST_ENTRY *)v141;
                                v141->SrvOpenQLinks.Blink = 0;
                                RxContext->TrackerHistory[4].AcquireRelease = 15;
                              }
                              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
                              {
                                WPP_SF_Dq(
                                  WPP_GLOBAL_Control->AttachedDevice,
                                  146,
                                  WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
                                  v187->AcquireRelease,
                                  v141);
                              }
                              goto LABEL_741;
                            }
                            v66 = 8684;
LABEL_784:
                            v147 = 0;
                            goto LABEL_785;
                          }
                          WPP_SF_d(
                            WPP_GLOBAL_Control->AttachedDevice,
                            143,
                            WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
                            *(unsigned int *)&v276[7]);
                          v13 = (unsigned __int8 *)Entry;
                        }
                        Buffer = *(unsigned int *)&v276[3];
                        v141 = MrxSrvOpen;
                        goto LABEL_723;
                      }
                      v177 = v12[1];
                      v178 = *(_DWORD *)(v177 + 4);
                      if ( (v178 & 0x1040080) == 0 && ((LOWORD(v299[3]) - 4) & 0xFFFFFFFB) != 0 )
                      {
                        if ( (v13[533] & 1) != 0 && *((_QWORD *)&RxContext->9 + 25) == 2 )
                        {
                          *(_DWORD *)(v177 + 4) = v178 | 0x40000;
                        }
                        else
                        {
                          if ( (*((_DWORD *)v13 + 30) & 0x20) != 0
                            && ((v13[529] & 2) == 0 || (*((_DWORD *)v13 + 83) & 0x20) == 0) )
                          {
                            goto LABEL_1201;
                          }
                          *((_DWORD *)v13 + 84) |= 0x20u;
                          *((_DWORD *)Entry + 83) &= ~0x20u;
                          *((_BYTE *)Entry + 529) |= 2u;
                        }
                        v13 = (unsigned __int8 *)Entry;
                      }
LABEL_1201:
                      Buffer = *(unsigned int *)&v276[3];
                      goto LABEL_457;
                    }
                    if ( v13[531] )
                    {
                      if ( (*((_DWORD *)v13 + 30) & 0x40400) != 0 )
                        goto LABEL_493;
                      v13[529] |= 1u;
                      *((_BYTE *)Entry + 529) |= 8u;
                    }
                    else
                    {
                      v244 = v12[1];
                      if ( (*(_DWORD *)(v244 + 8) != 1
                         && (*(_DWORD *)(v244 + 8) <= 1u
                          || (v285 & 0x40000) != 0
                          || (*((_DWORD *)&RxContext->9 + 28) & 0xFFEFFF7F) == 0)
                         || *(_DWORD *)(v244 + 28))
                        && ((Blink_high = HIDWORD(pFcb->SrvOpenList.Blink), (Blink_high & 2) != 0)
                         || (Blink_high & 1) != 0)
                        || (v246 = *((_QWORD *)v13 + 14),
                            v95 = *((_QWORD *)v13 + 5),
                            v247 = *(_QWORD *)(v246 + 40),
                            v96 = v246 + 16,
                            v247 == v95)
                        && *(_QWORD *)v96 == *((_QWORD *)v13 + 2) )
                      {
LABEL_493:
                        if ( (v299[0] & 0x10) != 0 )
                        {
                          v13[529] &= ~0x20u;
                          *((_BYTE *)Entry + 529) &= ~1u;
                        }
                        else
                        {
                          if ( (*((_DWORD *)v13 + 30) & 0x40000) == 0
                            || (v168 = *((_QWORD *)v13 + 14), !*(_QWORD *)v168)
                            || *(_QWORD *)(v168 + 24) != *((_QWORD *)v13 + 3)
                            || *(_DWORD *)(v168 + 48) != *((_DWORD *)v13 + 12) )
                          {
                            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
                            {
                              WPP_SF_qq(
                                WPP_GLOBAL_Control->AttachedDevice,
                                133,
                                WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
                                *((_QWORD *)v13 + 10),
                                *((_QWORD *)v13 + 3));
                              v13 = (unsigned __int8 *)Entry;
                            }
                            v13[529] |= 0x20u;
                            v250 = (char *)Entry;
                            if ( *((_BYTE *)Entry + 531) && (*((_DWORD *)Entry + 30) & 6) != 0 )
                            {
                              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
                              {
                                WPP_SF_(
                                  WPP_GLOBAL_Control->AttachedDevice,
                                  134,
                                  WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids);
                                v250 = (char *)Entry;
                              }
                              RxSetBasicInfoInFcb(pFcb, v250 + 56, v95, v96);
                              v251 = Entry;
                              *(_OWORD *)Entry = *(_OWORD *)((char *)Entry + 56);
                              v251[1] = *(_OWORD *)((char *)v251 + 72);
                              v251[2] = *(_OWORD *)((char *)v251 + 88);
                              *((_QWORD *)v251 + 6) = *((_QWORD *)v251 + 13);
                              *((_BYTE *)Entry + 529) &= ~1u;
                              *((_BYTE *)Entry + 529) &= ~8u;
                            }
                            else
                            {
                              *((_BYTE *)Entry + 529) |= 1u;
                              *((_BYTE *)Entry + 529) |= 8u;
                            }
                            v13 = (unsigned __int8 *)Entry;
                          }
                          if ( (v13[529] & 1) != 0
                            && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
                          {
                            WPP_SF_qq(
                              WPP_GLOBAL_Control->AttachedDevice,
                              135,
                              WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
                              *((_QWORD *)v13 + 7),
                              *(_QWORD *)v13);
                          }
                          if ( (*(_DWORD *)(v12[2] + 24LL) & 0x40) == 0 )
                          {
                            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
                            {
                              WPP_SF_(
                                WPP_GLOBAL_Control->AttachedDevice,
                                136,
                                WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids);
                            }
                            *(_DWORD *)(v12[2] + 24LL) |= 0x40u;
                            *((_BYTE *)Entry + 529) |= 0x20u;
                          }
                        }
                        goto LABEL_433;
                      }
                      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
                      {
                        WPP_SF_iiii(
                          WPP_GLOBAL_Control->AttachedDevice,
                          131,
                          WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
                          *(_QWORD *)v96,
                          *((_QWORD *)v13 + 2),
                          v247,
                          *((_QWORD *)v13 + 5));
                        v128 = MrxSrvOpen;
                        v13 = (unsigned __int8 *)Entry;
                      }
                      if ( !*((_QWORD *)v13 + 5)
                        && ((AcquireRelease = RxContext->TrackerHistory[4].AcquireRelease, (AcquireRelease & 2) != 0)
                         || (AcquireRelease & 1) != 0) )
                      {
                        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
                        {
                          WPP_SF_(
                            WPP_GLOBAL_Control->AttachedDevice,
                            132,
                            WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids);
                          v13 = (unsigned __int8 *)Entry;
                        }
                        v13[532] |= 0x80u;
                        *((_DWORD *)Entry + 83) |= 0x20u;
                        *((_DWORD *)Entry + 84) &= ~0x20u;
                        *((_BYTE *)Entry + 529) |= 2u;
                      }
                      else if ( (*((_DWORD *)v13 + 30) & 0x20) != 0
                             || (*((_DWORD *)v13 + 84) & 0x20) != 0
                             || (v286 & 0x2000) != 0
                             || (v249 = CscOKToMarkSparseOnOplockBreak(*(_QWORD *)&v128->DesiredAccess, v12[1]),
                                 v13 = (unsigned __int8 *)Entry,
                                 v249)
                             || (*((_DWORD *)Entry + 30) & 0x800000) != 0
                             || (*((_DWORD *)Entry + 84) & 0x800000) != 0 )
                      {
                        *((_DWORD *)v13 + 84) |= 0x20u;
                        *((_DWORD *)Entry + 83) &= ~0x20u;
                        *((_BYTE *)Entry + 529) |= 2u;
                      }
                      else
                      {
                        CscCreatepChangeStateToAvoidMarkingFileSparse(RxContext, v299, Entry, v12);
                      }
                    }
                    v13 = (unsigned __int8 *)Entry;
                    goto LABEL_493;
                  }
                  if ( (*(_DWORD *)(v12[2] + 24LL) & 0x10000) == 0 )
                  {
                    v172 = RxContext->TrackerHistory[4].AcquireRelease;
                    if ( (v172 & 2) == 0 && (v172 & 1) == 0 )
                    {
                      if ( (*((_DWORD *)v13 + 30) & 0x20) == 0 )
                      {
                        v173 = CscOKToMarkSparseOnOplockBreak(*(_QWORD *)&v128->DesiredAccess, v12[1]);
                        v13 = (unsigned __int8 *)Entry;
                        if ( !v173 && (*((_DWORD *)Entry + 30) & 0x800000) == 0 )
                        {
                          CscCreatepChangeStateToAvoidMarkingFileSparse(RxContext, v299, Entry, v12);
                          v128 = MrxSrvOpen;
                          *((_BYTE *)Entry + 529) &= ~1u;
LABEL_1144:
                          v13 = (unsigned __int8 *)Entry;
                          goto LABEL_1145;
                        }
                        v128 = MrxSrvOpen;
                      }
                      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
                      {
                        WPP_SF_(
                          WPP_GLOBAL_Control->AttachedDevice,
                          129,
                          WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids);
                        v128 = MrxSrvOpen;
                        v13 = (unsigned __int8 *)Entry;
                      }
                      *((_DWORD *)v13 + 84) |= 0x20u;
                      *((_DWORD *)Entry + 83) &= ~0x20u;
LABEL_1143:
                      *((_BYTE *)Entry + 529) |= 2u;
                      goto LABEL_1144;
                    }
                    if ( !*((_QWORD *)v13 + 5) )
                    {
                      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
                      {
                        WPP_SF_(
                          WPP_GLOBAL_Control->AttachedDevice,
                          128,
                          WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids);
                        v128 = MrxSrvOpen;
                        v13 = (unsigned __int8 *)Entry;
                      }
                      *((_DWORD *)v13 + 83) |= 0x20u;
                      *((_DWORD *)Entry + 84) &= ~0x20u;
                      goto LABEL_1143;
                    }
                  }
LABEL_1145:
                  v131 = *(_DWORD *)&v276[3];
                  goto LABEL_431;
                }
                if ( (v299[0] & 0x10) != 0 || v13[531] )
                {
                  *((_DWORD *)v13 + 83) |= 0x20u;
                  v13 = (unsigned __int8 *)Entry;
                }
                if ( (v299[0] & 0x10) != 0 )
                {
                  *((_DWORD *)v13 + 84) |= 0x400u;
                  LODWORD(v128[1].Context2) = 2032127;
                  *((_BYTE *)Entry + 532) |= 0x20u;
                  v291 = (*((_BYTE *)Entry + 531) != 0) + 1;
                  CscNotifyReportChange(RxContext, v291, 1);
                  v128 = MrxSrvOpen;
                }
                else
                {
                  if ( *((_QWORD *)v13 + 5) || v13[531] )
                    goto LABEL_1124;
                  *((_DWORD *)v13 + 83) |= 0x20u;
                }
                v13 = (unsigned __int8 *)Entry;
LABEL_1124:
                v13[529] |= 2u;
                *((_BYTE *)Entry + 529) |= 0x20u;
                v13 = (unsigned __int8 *)Entry;
                goto LABEL_428;
              }
              *((_DWORD *)v13 + 100) |= ~(unsigned __int16)*(_DWORD *)&MrxSrvOpen[1].NodeTypeCode & 0x112;
              *(_DWORD *)&v128[1].NodeTypeCode |= 0x112u;
            }
            else
            {
              *((_DWORD *)v13 + 100) |= ~*(_DWORD *)&MrxSrvOpen[1].NodeTypeCode & 0x10000;
              *(_DWORD *)&v128[1].NodeTypeCode |= 0x10000u;
            }
          }
          v13 = (unsigned __int8 *)Entry;
          goto LABEL_1108;
        }
        if ( v299[3] != 8 && !*((_BYTE *)Entry + 193) && !*((_BYTE *)Entry + 192) )
          goto LABEL_419;
      }
      if ( ((v299[3] - 4) & 0xFFFFFFFB) != 0 )
        goto LABEL_420;
      goto LABEL_302;
    }
    v148 = CscCheckNetInfoFromRxContext(RxContext, v13 + 56, (unsigned int)v278, v96);
    if ( v148 >= 0 )
    {
LABEL_465:
      v13 = (unsigned __int8 *)Entry;
      v149 = *((_DWORD *)Entry + 30);
      if ( ((v149 & 0x20) != 0 || (v149 & 0x10) != 0)
        && ((v179 = RxContext->Create.PipeCompletionMode, v179 > 5)
         || (Buffer = 45, !_bittest((const int *)&Buffer, v179))) )
      {
        if ( (*((_BYTE *)Entry + 533) & 0x10) == 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 124, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids);
            v13 = (unsigned __int8 *)Entry;
          }
          *((_QWORD *)&RxContext->9 + 25) = 5;
          v66 = 7462;
          inited = -1073741209;
          goto LABEL_174;
        }
        *((_BYTE *)Entry + 532) |= 1u;
        v13 = (unsigned __int8 *)Entry;
      }
      else
      {
        if ( !*((_BYTE *)Entry + 531) )
        {
LABEL_468:
          v150 = v13[533];
          if ( (v150 & 4) == 0 )
          {
            Buffer = v13[532];
            if ( (Buffer & 1) != 0 || (v150 & 0x40) != 0 && (*(_DWORD *)(v12[2] + 24LL) & 1) == 0 )
            {
              v13[532] = Buffer | 8;
              v151 = _CscObtainFcbMostlyExclusive(RxContext, 0);
              v13 = (unsigned __int8 *)Entry;
              if ( !v151 )
              {
                if ( (*((_BYTE *)Entry + 533) & 0x40) == 0 || (v299[0] & 0x10) != 0 )
                {
                  inited = -1073741757;
                }
                else if ( (v299[0] & 0x20) != 0 && (*((_DWORD *)Entry + 30) & 0x20) != 0 )
                {
                  inited = -1073741641;
                }
                else
                {
                  inited = -1073741640;
                }
                v66 = 7535;
                goto LABEL_174;
              }
            }
          }
          goto LABEL_298;
        }
        if ( (v149 & 0x10000) != 0 && (*((_BYTE *)Entry + 533) & 0x12) == 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 125, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids);
            v13 = (unsigned __int8 *)Entry;
          }
          *((_QWORD *)&RxContext->9 + 25) = 5;
          v66 = 7483;
          inited = -1073741209;
          goto LABEL_174;
        }
      }
      if ( v13[531] )
        goto LABEL_298;
      goto LABEL_468;
    }
    v13 = (unsigned __int8 *)Entry;
    v233 = *((_DWORD *)Entry + 30);
    if ( ((v233 & 0x20) != 0 || (v233 & 0x10) != 0) && (v299[0] & 0x40) != 0 )
    {
      v234 = RxContext->Create.PipeCompletionMode;
      if ( v234 <= 5 )
      {
        Buffer = 45;
        if ( _bittest((const int *)&Buffer, v234) )
        {
          if ( (*((_BYTE *)Entry + 528) & 4) != 0 )
          {
            if ( v148 == -1073741565 )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
              {
                v235 = "sparse";
                if ( (*((_DWORD *)Entry + 30) & 0x20) == 0 )
                  v235 = "dirty deleted";
                WPP_SF_s(WPP_GLOBAL_Control->AttachedDevice, 122, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids, v235);
                v13 = (unsigned __int8 *)Entry;
              }
              LOBYTE(Buffer) = 1;
              v236 = CscStoreChangeEntryTypeForCreate(&v277, Buffer, v13, v292, v270);
              if ( v236 < 0 )
              {
                v13 = (unsigned __int8 *)Entry;
                inited = v236;
                v66 = 7394;
                goto LABEL_174;
              }
              *((_BYTE *)Entry + 534) |= 0x40u;
              v237 = CscStoreQueryInformationEntryEx(
                       (_DWORD)v277,
                       0,
                       (int)Entry + 120,
                       (int)Entry + 56,
                       (__int64)Entry + 536,
                       0,
                       0);
              if ( v237 < 0 )
              {
                v13 = (unsigned __int8 *)Entry;
                inited = v237;
                v66 = 7410;
                goto LABEL_174;
              }
              *((_BYTE *)Entry + 531) = 1;
              LODWORD(v278) = 1;
              goto LABEL_465;
            }
            if ( v148 == -1073741638 )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
              {
                WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 123, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids);
                v13 = (unsigned __int8 *)Entry;
              }
              v148 = -1073741108;
            }
          }
        }
      }
    }
    inited = v148;
    v66 = 7438;
    goto LABEL_174;
  }
  v104 = v7 == 0;
  p_EaBuffer = &RxContext->Create.EaBuffer;
  if ( v104 )
    inited = *((_DWORD *)RxContext->Create.UserName.Buffer + 4);
  else
    inited = -1073741300;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      111,
      WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
      (unsigned int)inited);
  CscStoreDereferenceEntry(&v277);
  v66 = 6811;
  *((_BYTE *)Entry + 532) |= 0x10u;
  v13 = (unsigned __int8 *)Entry;
  v277 = 0;
LABEL_175:
  v68 = *((_DWORD *)v13 + 100);
  v69 = MrxSrvOpen;
  *(_DWORD *)&MrxSrvOpen[1].NodeTypeCode &= ~v68;
  if ( *(_QWORD *)&pFcb->OpenCount )
    CscFlushLViewWasPreviouslyOffline();
  if ( v282 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
      WPP_SF_qqqD(
        WPP_GLOBAL_Control->AttachedDevice,
        155,
        WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
        v277,
        pFcb,
        v69,
        inited);
    LOBYTE(Buffer) = 1;
    v266 = CscStoreSetPurgeEntry(v277, Buffer);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 156, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids, v266);
    if ( v266 == -1073741567 )
      CscEnDeleteTransparentlyCachedDir(v277);
    CscStoreDereferenceEntry(&v277);
    v69 = MrxSrvOpen;
    *((_BYTE *)Entry + 532) |= 0x10u;
    v70 = 0;
    v277 = 0;
  }
  else
  {
    v70 = (__int64)v277;
  }
  if ( v291 && (v291 & 3) == 0 )
  {
    CscNotifyReportChange(RxContext, v291, 3);
    v70 = (__int64)v277;
  }
  if ( inited >= 0 )
  {
    if ( (*((_BYTE *)Entry + 532) & 2) == 0 )
      goto LABEL_182;
    goto LABEL_703;
  }
  if ( v70 )
  {
    v180 = v12[2];
    if ( !v180 )
      goto LABEL_700;
    if ( *(_QWORD *)(v180 + 8) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
        WPP_SF_qqq(
          WPP_GLOBAL_Control->AttachedDevice,
          157,
          WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
          v70,
          pFcb,
          v69);
      CscStoreCloseEntryHandle(*(_QWORD *)(v12[2] + 8LL), 0, 0);
      *(_QWORD *)(v12[2] + 8LL) = 0;
    }
    else
    {
      if ( !*(_QWORD *)(v180 + 16) )
        goto LABEL_700;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
        WPP_SF_qqq(
          WPP_GLOBAL_Control->AttachedDevice,
          158,
          WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
          v70,
          pFcb,
          v69);
      CscStoreCloseEntryHandle(*(_QWORD *)(v12[2] + 16LL), 0, 0);
      *(_QWORD *)(v12[2] + 16LL) = 0;
    }
    v70 = (__int64)v277;
LABEL_700:
    if ( (*((_BYTE *)Entry + 532) & 0x10) == 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
        WPP_SF_qqq(
          WPP_GLOBAL_Control->AttachedDevice,
          159,
          WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
          v70,
          pFcb,
          v69);
      CscStoreDereferenceEntry(&v277);
      *((_BYTE *)Entry + 532) |= 0x10u;
    }
  }
LABEL_703:
  v181 = Entry;
  if ( (*((_BYTE *)Entry + 528) & 8) != 0 && *(int *)&v276[3] >= 0 )
  {
    v183 = *((unsigned __int8 *)Entry + 532);
    if ( (v183 & 4) == 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          160,
          WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
          ((unsigned int)v183 >> 1) & 1);
      v184 = RxContext->NonPagedFcb->AdvancedFcbHeaderMutex.Event.Header.WaitListHead.Blink[6].Blink;
      if ( v184 )
        ((void (__fastcall *)(PRX_CONTEXT, PVOID, __int64, __int64))v184)(RxContext, v181, v183, v70);
      if ( *v12 )
      {
        if ( inited >= 0 )
        {
          *(_DWORD *)(*v12 + 4LL) &= ~1u;
        }
        else
        {
          CscInternalDeallocateForFobx(RxContext->pFobx, v181, v183, v70);
          *v12 = 0;
        }
      }
      Flink = RxContext->NonPagedFcb->AdvancedFcbHeaderMutex.Event.Header.WaitListHead.Blink[7].Flink;
      if ( Flink )
        ((void (__fastcall *)(PRX_CONTEXT, PVOID, __int64, __int64))Flink)(RxContext, v181, v183, v70);
      *(_DWORD *)(v12[2] + 24LL) &= ~2u;
      CscUpdateRdrOpenCount(v12[1], v69, 0xFFFFFFFFLL);
      *((_BYTE *)Entry + 532) &= ~0x40u;
    }
  }
  if ( inited < 0 )
  {
    CscCleanupFcbContextFlags(pFcb, v181);
    v182 = v12[1];
    if ( v182
      && (*(_DWORD *)(v182 + 4) & 0x1166F) != 0
      && !*(_QWORD *)(v182 + 56)
      && LODWORD(pFcb[1].Header.PagingIoResource) )
    {
      _InterlockedOr8((volatile signed __int8 *)&pFcb[1].Header.FileContextSupportPointer, 2u);
    }
    goto LABEL_188;
  }
LABEL_182:
  if ( v12[2] )
  {
    v71 = v12[1];
    if ( v71 )
    {
      if ( (*((_DWORD *)&RxContext->9 + 28) & 0xFFEFFF7F) != 0 )
      {
        ++*(_DWORD *)(v71 + 16);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
        {
          WPP_SF_qDD(WPP_GLOBAL_Control->AttachedDevice, 161, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids);
        }
      }
      if ( (*((_BYTE *)Entry + 532) & 8) != 0 )
        _CscObtainFcbMostlyExclusive(RxContext, 1);
      if ( (*((_BYTE *)Entry + 534) & 2) != 0 && *v12 )
        *(_DWORD *)(*v12 + 4LL) |= 8u;
    }
  }
LABEL_188:
  if ( (v286 & 0x4002C) != 0 && inited == -1073741766 )
  {
    v70 = 3221225530LL;
    inited = -1073741605;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
      WPP_SF_Dd(
        WPP_GLOBAL_Control->AttachedDevice,
        162,
        WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
        3221225530LL,
        -1073741605);
  }
  if ( v284 )
  {
    *((_DWORD *)p_EaBuffer + 6) = v296;
    if ( inited == -1073741772 || inited == -1073741209 || inited == -1073739772 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
        WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 163, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids, p_FileName);
      v268 = CscDclNotifyExcludedFileType(0, p_FileName, 0, v70);
      if ( v268 < 0
        && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          164,
          WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
          (unsigned int)v268);
      }
      inited = -1073739772;
    }
  }
  if ( Entry )
  {
    ExFreeToPagedLookasideList((PPAGED_LOOKASIDE_LIST)(CscDevExtn + 128), Entry);
    Entry = 0;
  }
LABEL_192:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_Dd(
      WPP_GLOBAL_Control->AttachedDevice,
      165,
      WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
      (unsigned int)inited,
      v66);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x140062b70  push    rbp
0x140062b72  push    rbx
0x140062b73  push    rsi
0x140062b74  push    rdi
0x140062b75  push    r12
0x140062b77  push    r13
0x140062b79  push    r14
0x140062b7b  push    r15
0x140062b7d  lea     rbp, [rsp-88h]
0x140062b85  sub     rsp, 1B8h
0x140062b8c  mov     rax, cs:__security_cookie
0x140062b93  xor     rax, rsp
0x140062b96  mov     [rbp+0C0h+var_50], rax
0x140062b9a  mov     r14, [rcx+38h]
0x140062b9e  mov     r13, rcx
0x140062ba1  mov     rax, [rcx+48h]
0x140062ba5  xorps   xmm0, xmm0
0x140062ba8  mov     [rbp+0C0h+MrxSrvOpen], rax
0x140062bac  xor     r15d, r15d
0x140062baf  mov     [rbp+0C0h+var_E0], r14
0x140062bb3  mov     rax, [r14+78h]
0x140062bb7  mov     rax, [rax+20h]
0x140062bbb  mov     [rbp+0C0h+var_D8], rax
0x140062bbf  mov     rax, [rcx+290h]
0x140062bc6  mov     rcx, [rcx+50h]
0x140062bca  mov     [rbp+0C0h+var_E8], rax
0x140062bce  mov     [rbp+0C0h+var_128], r15
0x140062bd2  movups  xmmword ptr [rbp+0C0h+String1.Length], xmm0
0x140062bd6  call    CscProcessRequestAsFilter
0x140062bdb  mov     ebx, [r13+100h]
0x140062be2  lea     rcx, [rbp+0C0h+Entry]
0x140062be6  movzx   esi, al
0x140062be9  mov     [rbp+0C0h+var_138], al
0x140062bec  mov     eax, [r13+218h]
0x140062bf3  xorps   xmm0, xmm0
0x140062bf6  movups  xmmword ptr [rbp+0C0h+var_B0], xmm0
0x140062bfa  mov     [rbp+0C0h+var_D0], eax
0x140062bfd  mov     [rbp+0C0h+Entry], r15
0x140062c01  mov     dword ptr [rbp+0C0h+var_120], r15d
0x140062c05  mov     dword ptr [rbp+0C0h+var_104], ebx
0x140062c08  mov     [rbp+0C0h+var_F0], r15
0x140062c0c  call    CscAllocateCreateContext
0x140062c11  mov     r12d, eax
0x140062c14  test    eax, eax
0x140062c16  js      loc_140066069
0x140062c1c  mov     rdx, [rbp+0C0h+Entry]
0x140062c20  lea     rax, [r13+330h]
0x140062c27  mov     [rbp+0C0h+var_C8], rax
0x140062c2b  mov     ecx, ebx
0x140062c2d  shr     ecx, 2
0x140062c30  and     cl, 2
0x140062c33  mov     dword ptr [rbp+0C0h+var_137+3], r15d
0x140062c37  movzx   eax, byte ptr [rdx+215h]
0x140062c3e  and     al, 0FDh
0x140062c40  mov     dword ptr [rbp+0C0h+var_F8+4], r15d
0x140062c44  or      cl, al
0x140062c46  mov     [rbp+0C0h+var_10E], r15b
0x140062c4a  mov     [rdx+215h], cl
0x140062c50  mov     ecx, ebx
0x140062c52  shr     ecx, 1
0x140062c54  and     cl, 8
0x140062c57  mov     [rbp+0C0h+var_108], r15b
0x140062c5b  lea     r15, [rdx+158h]
0x140062c62  mov     dword ptr [rbp+0C0h+var_104+4], ebx
0x140062c65  mov     rdx, [rbp+0C0h+Entry]
0x140062c69  movzx   eax, byte ptr [rdx+215h]
0x140062c70  and     al, 0F7h
0x140062c72  or      cl, al
0x140062c74  mov     [rdx+215h], cl
0x140062c7a  movzx   ecx, bl
0x140062c7d  mov     rdx, [rbp+0C0h+Entry]
0x140062c81  and     cl, 4
0x140062c84  shl     cl, 2
0x140062c87  movzx   eax, byte ptr [rdx+215h]
0x140062c8e  and     al, 0EFh
0x140062c90  or      cl, al
0x140062c92  mov     [rdx+215h], cl
0x140062c98  mov     ecx, ebx
0x140062c9a  mov     rdx, [rbp+0C0h+Entry]
0x140062c9e  shr     ecx, 0Bh
0x140062ca1  and     cl, 20h
0x140062ca4  movzx   eax, byte ptr [rdx+215h]
0x140062cab  and     al, 0DFh
0x140062cad  or      cl, al
0x140062caf  mov     [rdx+215h], cl
0x140062cb5  movzx   ecx, bl
0x140062cb8  mov     rdx, [rbp+0C0h+Entry]
0x140062cbc  and     cl, 20h
0x140062cbf  add     cl, cl
0x140062cc1  movzx   eax, byte ptr [rdx+215h]
0x140062cc8  and     al, 0BFh
0x140062cca  or      cl, al
0x140062ccc  mov     [rdx+215h], cl
0x140062cd2  mov     ecx, ebx
0x140062cd4  mov     rdx, [rbp+0C0h+Entry]
0x140062cd8  shr     ecx, 2
0x140062cdb  and     cl, 80h
0x140062cde  movzx   eax, byte ptr [rdx+215h]
0x140062ce5  and     al, 7Fh
0x140062ce7  or      cl, al
0x140062ce9  mov     [rdx+215h], cl
0x140062cef  mov     ecx, ebx
0x140062cf1  mov     rdx, [rbp+0C0h+Entry]
0x140062cf5  shr     ecx, 0Ah
0x140062cf8  and     cl, 1
0x140062cfb  movzx   eax, byte ptr [rdx+216h]
0x140062d02  and     al, 0FEh
0x140062d04  or      cl, al
0x140062d06  mov     [rdx+216h], cl
0x140062d0c  mov     ecx, ebx
0x140062d0e  mov     rdx, [rbp+0C0h+Entry]
0x140062d12  shr     ecx, 0Ah
0x140062d15  and     cl, 2
0x140062d18  movzx   eax, byte ptr [rdx+216h]
0x140062d1f  and     al, 0FDh
0x140062d21  or      cl, al
0x140062d23  mov     [rdx+216h], cl
0x140062d29  mov     ecx, ebx
0x140062d2b  mov     rdx, [rbp+0C0h+Entry]
0x140062d2f  shr     ecx, 0Ah
0x140062d32  and     cl, 10h
0x140062d35  movzx   eax, byte ptr [rdx+216h]
0x140062d3c  and     al, 0EFh
0x140062d3e  or      cl, al
0x140062d40  mov     [rdx+216h], cl
0x140062d46  mov     rdx, [rbp+0C0h+Entry]
0x140062d4a  movzx   eax, byte ptr [rdx+216h]
0x140062d51  mov     ecx, ebx
0x140062d53  shr     ecx, 0Ah
0x140062d56  and     al, 7Fh
0x140062d58  and     cl, 80h
0x140062d5b  or      cl, al
0x140062d5d  mov     [rdx+216h], cl
0x140062d63  mov     ecx, ebx
0x140062d65  mov     rdx, [rbp+0C0h+Entry]
0x140062d69  shr     ecx, 10h
0x140062d6c  and     cl, 4
0x140062d6f  movzx   eax, byte ptr [rdx+215h]
0x140062d76  and     al, 0FBh
0x140062d78  or      cl, al
0x140062d7a  mov     [rdx+215h], cl
0x140062d80  mov     rax, [rbp+0C0h+Entry]
0x140062d84  mov     byte ptr [rax+219h], 0
0x140062d8b  cmp     qword ptr [r13+238h], 0
0x140062d93  mov     rdx, [rbp+0C0h+Entry]
0x140062d97  setnz   cl
0x140062d9a  movzx   eax, byte ptr [rdx+210h]
0x140062da1  and     al, 0FEh
0x140062da3  or      cl, al
0x140062da5  mov     [rdx+210h], cl
0x140062dab  mov     rdi, [rbp+0C0h+Entry]
0x140062daf  movzx   eax, byte ptr [rdi+215h]
0x140062db6  test    al, 20h
0x140062db8  jz      short loc_140062DC6
0x140062dba  or      al, 10h
0x140062dbc  mov     [rdi+215h], al
0x140062dc2  mov     rdi, [rbp+0C0h+Entry]
0x140062dc6  mov     rdx, [r14+80h]
0x140062dcd  test    rdx, rdx
0x140062dd0  jnz     loc_1400639DB
0x140062dd6  test    sil, sil
0x140062dd9  jz      loc_140064078
0x140062ddf  test    ebx, 1C0h
0x140062de5  jnz     loc_1400660BD
0x140062deb  xor     ebx, ebx
0x140062ded  mov     dword ptr [rbp+0C0h+var_137+7], 0C000000Dh
0x140062df4  mov     [rbp+0C0h+var_110], 0
0x140062df8  mov     r12d, 59h ; 'Y'
0x140062dfe  test    rdx, rdx
0x140062e01  jnz     loc_140063625
0x140062e07  lea     r8, WPP_GLOBAL_Control
0x140062e0e  test    sil, sil
0x140062e11  jz      loc_140065810
0x140062e17  lea     rdx, [r13+330h]
0x140062e1e  lea     rcx, [rbp+0C0h+String1]
0x140062e22  call    CscPathUtilsInitParentPathFromFullPath
0x140062e27  mov     r12d, eax
0x140062e2a  test    eax, eax
0x140062e2c  js      loc_140066115
0x140062e32  mov     r8, [rbp+0C0h+MrxSrvOpen]
0x140062e36  lea     r9, [rbp+0C0h+String1]
0x140062e3a  mov     rdx, r14
0x140062e3d  lea     rcx, [r13+200h]
0x140062e44  call    CscExclusionListCheckCreate
0x140062e49  cmp     eax, 0C0000804h
0x140062e4e  jz      loc_140066123
0x140062e54  mov     rdi, [rbp+0C0h+var_E8]
0x140062e58  test    sil, sil
0x140062e5b  jz      loc_14006574A
0x140062e61  mov     rdx, r15
0x140062e64  mov     rcx, r13
0x140062e67  call    CscGetContexts
0x140062e6c  mov     edx, dword ptr [rbp+0C0h+var_104]
0x140062e6f  lea     rbx, [r15+18h]
0x140062e73  bt      edx, 0Dh
0x140062e77  jb      loc_140066155
0x140062e7d  bt      edx, 0Fh
0x140062e81  jb      loc_140066165
0x140062e87  xor     dl, dl
0x140062e89  mov     rcx, [rbp+0C0h+Entry]
0x140062e8d  movzx   eax, byte ptr [rcx+216h]
0x140062e94  and     al, 0FBh
0x140062e96  or      al, dl
0x140062e98  mov     [rcx+216h], al
0x140062e9e  test    sil, sil
0x140062ea1  jz      loc_14006548D
0x140062ea7  lea     r12, WPP_GLOBAL_Control
0x140062eae  mov     eax, [rdi+38h]
0x140062eb1  test    al, 10h
0x140062eb3  jnz     loc_14006550A
0x140062eb9  test    sil, sil
0x140062ebc  jz      loc_1400654F4
0x140062ec2  mov     rdx, [rbp+0C0h+Entry]
0x140062ec6  mov     rcx, r13
0x140062ec9  call    CscCreatepUpdateStateForAdminOpen
0x140062ece  mov     r12d, eax
0x140062ed1  test    eax, eax
0x140062ed3  js      loc_140066180
0x140062ed9  mov     rbx, [rbp+0C0h+MrxSrvOpen]
0x140062edd  lea     rax, [rbp+0C0h+var_B0]
0x140062ee1  mov     rdx, rbx
0x140062ee4  mov     byte ptr [rsp+1F0h+String2], 0
0x140062ee9  mov     r9b, 1
0x140062eec  mov     [rsp+1F0h+var_1D0], rax
0x140062ef1  mov     r8, r13
0x140062ef4  mov     rcx, r14
0x140062ef7  call    CscUpdateAndCaptureConnectionStateEx
0x140062efc  movzx   ecx, byte ptr [rbp+0C0h+var_B0]
0x140062f00  movzx   edx, byte ptr [rbp+0C0h+var_B0+1]
0x140062f04  movzx   eax, cl
0x140062f07  mov     rdi, [rbp+0C0h+Entry]
0x140062f0b  shr     al, 3
0x140062f0e  or      al, cl
0x140062f10  and     cl, 0FBh
0x140062f13  and     al, 4
0x140062f15  or      al, cl
0x140062f17  mov     byte ptr [rbp+0C0h+var_B0], al
0x140062f1a  test    dl, 10h
0x140062f1d  jz      loc_1400635C0
0x140062f23  mov     cl, 10h
0x140062f25  and     dl, 0EFh
0x140062f28  or      dl, cl
0x140062f2a  mov     byte ptr [rbp+0C0h+var_B0+1], dl
0x140062f2d  test    al, 40h
0x140062f2f  jnz     loc_1400635D4
0x140062f35  cmp     qword ptr [r15+10h], 0
0x140062f3a  jz      loc_1400635D4
0x140062f40  lea     r11, WPP_GLOBAL_Control
0x140062f47  mov     rax, [r15+8]
0x140062f4b  test    rax, rax
0x140062f4e  jnz     loc_1400641C8
0x140062f54  mov     r9d, dword ptr [rbp+0C0h+var_104+4]
0x140062f58  movzx   eax, byte ptr [rdi+215h]
0x140062f5f  test    al, 4
0x140062f61  jnz     loc_1400653CA
0x140062f67  mov     rax, cs:WPP_GLOBAL_Control
0x140062f6e  cmp     rax, r11
0x140062f71  jnz     loc_140063C55
0x140062f77  mov     rax, [r15+8]
0x140062f7b  test    rax, rax
0x140062f7e  jnz     loc_140064162
0x140062f84  movzx   edx, byte ptr [rdi+215h]
0x140062f8b  test    dl, 8
0x140062f8e  jnz     loc_1400642F0
0x140062f94  mov     rcx, [r15+8]
0x140062f98  test    rcx, rcx
0x140062f9b  jnz     loc_140064288
0x140062fa1  movzx   eax, byte ptr [rdi+216h]
0x140062fa8  test    al, 4
0x140062faa  jnz     loc_1400663B1
0x140062fb0  test    byte ptr [rbp+0C0h+var_B0], 4
0x140062fb4  jnz     loc_140063D52
0x140062fba  test    byte ptr [rbp+0C0h+var_B0], 4
0x140062fbe  movzx   eax, byte ptr [rdi+215h]
0x140062fc5  mov     [rbp+0C0h+var_FC], 0
0x140062fcc  jz      loc_140064E4F
0x140062fd2  and     al, 6
0x140062fd4  cmp     al, 2
0x140062fd6  jz      loc_14006503C
0x140062fdc  test    sil, sil
0x140062fdf  jnz     loc_140063E69
0x140062fe5  test    byte ptr [rbp+0C0h+var_B0], 20h
0x140062fe9  jz      short loc_140062FF6
0x140062feb  or      byte ptr [rdi+211h], 80h
0x140062ff2  mov     rdi, [rbp+0C0h+Entry]
0x140062ff6  lea     rdx, [rdi+0C8h]
0x140062ffd  mov     rcx, r13
0x140063000  call    cs:__imp_RxSidFromRxContext
0x140063007  nop     dword ptr [rax+rax+00h]
0x14006300c  mov     rdi, [rbp+0C0h+Entry]
0x140063010  test    eax, eax
0x140063012  js      loc_140066439
0x140063018  xor     cl, cl
0x14006301a  test    byte ptr [rdi+210h], 10h
0x140063021  mov     [rbp+0C0h+var_137], cl
0x140063024  jnz     loc_14006474A
0x14006302a  test    sil, sil
0x14006302d  jz      loc_14006474A
0x140063033  test    byte ptr [rbp+0C0h+var_B0], 10h
0x140063037  jnz     loc_14006474A
  ... truncated ...
```
