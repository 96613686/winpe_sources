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
  unsigned __int64 v9; // r8
  int inited; // r12d
  char *v11; // rdx
  char v12; // al
  _QWORD *v13; // r15
  unsigned __int8 *v14; // rdi
  char v15; // al
  __int64 Buffer; // rdx
  signed __int64 v17; // rbx
  __int64 v18; // rdi
  _QWORD *v19; // rbx
  char v20; // dl
  int v21; // r9d
  PMRX_SRV_OPEN v22; // rbx
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
  __int64 v33; // r9
  char v34; // cl
  unsigned int v35; // eax
  __int64 v36; // rax
  int v37; // ebx
  ULONG v38; // eax
  int v39; // ecx
  struct _UNICODE_STRING *Pool2; // rax
  PMRX_SRV_OPEN v41; // rbx
  char v42; // dl
  char v43; // cl
  __int64 v44; // rax
  __int64 v45; // rax
  char v46; // r11
  char v47; // r10
  char v48; // r8
  char v49; // cl
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
  __int64 v70; // rcx
  struct _LIST_ENTRY *v71; // r9
  __int64 v72; // rcx
  int PagingIoResource; // ecx
  __int64 v75; // rax
  __int64 v76; // r9
  __int64 v77; // r8
  int v78; // edi
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
  unsigned __int64 v95; // r9
  int v96; // eax
  bool v97; // dl
  unsigned __int8 v98; // cl
  unsigned __int8 v99; // cl
  __int64 v100; // rax
  int SlashDotOpen; // eax
  int v102; // eax
  bool v103; // zf
  __int64 v104; // rcx
  char v105; // al
  __int64 v106; // rcx
  ULONG v107; // eax
  int v108; // ecx
  int v109; // ecx
  int v110; // eax
  int v111; // eax
  unsigned int v112; // eax
  int v113; // r9d
  char v114; // cl
  bool v115; // cl
  __int64 v116; // rax
  __int64 v117; // rax
  ULONG v118; // eax
  int v119; // ecx
  char IsRootGhosted; // di
  char v121; // dl
  int CanSidDecryptEntry; // eax
  int v123; // ebx
  ULONG v124; // eax
  int v125; // ecx
  PMRX_SRV_OPEN v126; // r11
  ULONG v127; // eax
  int v128; // ecx
  int v129; // ecx
  __int64 v130; // rdx
  void *v131; // rcx
  PMRX_SRV_OPEN v132; // r10
  bool v133; // dl
  unsigned __int8 v134; // al
  char v135; // cl
  __int64 p_Context2; // rax
  int v137; // eax
  PMRX_SRV_OPEN v138; // rsi
  int v139; // eax
  _BYTE *v140; // rdx
  unsigned int v141; // esi
  int v142; // eax
  char v143; // si
  int v144; // ecx
  int v145; // eax
  unsigned __int8 v146; // al
  char v147; // al
  char v148; // r8
  __int64 v149; // r9
  char v150; // r8
  char v151; // r11
  char v152; // r10
  char v153; // cl
  char v154; // r8
  char v155; // cl
  unsigned int v156; // r8d
  int v157; // eax
  unsigned int v158; // eax
  int v159; // r9d
  int v160; // eax
  int v161; // ecx
  char v162; // al
  int v163; // eax
  __int64 v164; // rcx
  int v165; // eax
  __int64 v166; // r9
  char v167; // al
  int v168; // eax
  ULONG v169; // eax
  char v170; // al
  int v171; // eax
  __int64 v172; // r9
  char v173; // al
  __int64 v174; // rdx
  int v175; // ecx
  ULONG v176; // ecx
  __int64 v177; // rax
  PVOID v178; // rdx
  __int64 v179; // rcx
  struct _LIST_ENTRY *v180; // rax
  struct _MRX_FOBX_ *NetFobx; // rax
  ULONG v182; // ecx
  RX_FCBTRACKER_CALLINFO *v183; // rbx
  char *v184; // rdx
  int v185; // eax
  __int64 v186; // r9
  __int64 v187; // rcx
  char *v188; // r8
  int v189; // eax
  int v190; // eax
  int v191; // eax
  char v192; // al
  __int64 v193; // r9
  unsigned __int8 v194; // di
  __int64 v195; // rsi
  char v196; // bl
  char GlobalNewlyCachedEpoch; // al
  char v198; // r14
  char v199; // r8
  char v200; // cl
  char v201; // r11
  char v202; // r10
  char v203; // bl
  int v204; // r9d
  __int64 v205; // rax
  int v206; // eax
  char v207; // al
  PDEVICE_OBJECT v208; // rcx
  __int64 v209; // rdx
  ULONG v210; // eax
  int v211; // eax
  __int64 v212; // rax
  __int64 v213; // r9
  int v214; // eax
  unsigned int v215; // eax
  char v216; // al
  int v217; // ecx
  int v218; // eax
  __int64 v219; // rdx
  int v220; // ecx
  PDEVICE_OBJECT v221; // rcx
  __int64 v222; // rdx
  int v223; // eax
  _OWORD *v224; // rax
  int v225; // eax
  ULONG v226; // eax
  const char *v227; // r9
  int v228; // eax
  int v229; // eax
  __int64 v230; // rcx
  int v231; // eax
  _DWORD *v232; // rax
  int v233; // eax
  ULONG v234; // eax
  int v235; // eax
  __int64 v236; // rcx
  int Blink_high; // eax
  __int64 v238; // rax
  __int64 v239; // r10
  ULONG AcquireRelease; // eax
  char v241; // al
  char *v242; // rdx
  _OWORD *v243; // rax
  int v244; // eax
  char *v245; // r9
  char v246; // al
  _BYTE *v247; // r8
  __int64 v248; // rdx
  __int64 v249; // rcx
  int v250; // eax
  int DatabaseInformation; // eax
  char v252; // cl
  __int64 v253; // rax
  __int64 v254; // rax
  int v255; // eax
  __int64 v256; // rax
  int v257; // eax
  unsigned int v258; // edi
  struct _LIST_ENTRY *Flink; // rax
  int v260; // eax
  char v261; // [rsp+20h] [rbp-110h]
  int v262; // [rsp+20h] [rbp-110h]
  int String2; // [rsp+28h] [rbp-108h]
  int v264; // [rsp+30h] [rbp-100h]
  char v265; // [rsp+A0h] [rbp-90h]
  PVOID Entry; // [rsp+B0h] [rbp-80h] BYREF
  unsigned __int8 v267; // [rsp+B8h] [rbp-78h] BYREF
  _BYTE v268[15]; // [rsp+B9h] [rbp-77h] BYREF
  struct _LIST_ENTRY *v269; // [rsp+C8h] [rbp-68h] BYREF
  __int64 v270; // [rsp+D0h] [rbp-60h] BYREF
  PMRX_SRV_OPEN MrxSrvOpen; // [rsp+D8h] [rbp-58h]
  char v272; // [rsp+E0h] [rbp-50h] BYREF
  unsigned __int8 v273; // [rsp+E1h] [rbp-4Fh] BYREF
  char v274; // [rsp+E2h] [rbp-4Eh]
  int updated; // [rsp+E4h] [rbp-4Ch] BYREF
  char v276; // [rsp+E8h] [rbp-48h]
  unsigned int v277; // [rsp+ECh] [rbp-44h] BYREF
  unsigned int v278; // [rsp+F0h] [rbp-40h]
  unsigned int v279; // [rsp+F4h] [rbp-3Ch]
  char v280; // [rsp+F8h] [rbp-38h] BYREF
  char v281; // [rsp+F9h] [rbp-37h] BYREF
  char v282; // [rsp+FAh] [rbp-36h] BYREF
  unsigned int v283; // [rsp+FCh] [rbp-34h]
  __int64 v284; // [rsp+100h] [rbp-30h] BYREF
  __int64 v285; // [rsp+108h] [rbp-28h] BYREF
  PMRX_FCB v286; // [rsp+110h] [rbp-20h] BYREF
  unsigned __int64 v287; // [rsp+118h] [rbp-18h]
  ULONG v288; // [rsp+120h] [rbp-10h]
  PSZ *p_FileName; // [rsp+128h] [rbp-8h]
  UNICODE_STRING String1; // [rsp+130h] [rbp+0h] BYREF
  int v291[4]; // [rsp+140h] [rbp+10h] BYREF
  _DWORD v292[20]; // [rsp+150h] [rbp+20h] BYREF

  pFcb = RxContext->pFcb;
  MrxSrvOpen = RxContext->pRelevantSrvOpen;
  v286 = pFcb;
  v287 = *(_QWORD *)(*(_QWORD *)&pFcb->UncleanCount + 32LL);
  v3 = *(_QWORD *)&RxContext->TrackerHistory[0].Flags;
  NonPagedFcb = RxContext->NonPagedFcb;
  v285 = v3;
  v269 = 0;
  String1 = 0;
  v5 = CscProcessRequestAsFilter(NonPagedFcb);
  Blink = (unsigned int)RxContext->WorkQueueItem.List.Blink;
  v7 = v5;
  v267 = v5;
  PipeCompletionMode = RxContext->Create.PipeCompletionMode;
  *(_OWORD *)v291 = 0;
  v288 = PipeCompletionMode;
  Entry = 0;
  LODWORD(v270) = 0;
  v277 = Blink;
  v284 = 0;
  inited = CscAllocateCreateContext(&Entry);
  if ( inited < 0 )
  {
    v66 = 4752;
    goto LABEL_193;
  }
  v11 = (char *)Entry;
  p_FileName = &RxContext->TrackerHistory[7].FileName;
  *(_DWORD *)&v268[3] = 0;
  v12 = *((_BYTE *)Entry + 533) & 0xFD;
  v283 = 0;
  v274 = 0;
  *((_BYTE *)Entry + 533) = v12 | (Blink >> 2) & 2;
  v276 = 0;
  v13 = v11 + 344;
  v278 = Blink;
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
  v14 = (unsigned __int8 *)Entry;
  v15 = *((_BYTE *)Entry + 533);
  if ( (v15 & 0x20) != 0 )
  {
    *((_BYTE *)Entry + 533) = v15 | 0x10;
    v14 = (unsigned __int8 *)Entry;
  }
  Buffer = *(_QWORD *)&pFcb->OpenCount;
  if ( Buffer && *(_QWORD *)(Buffer + 48) )
  {
    CscAcquireLViewLock(*(_QWORD *)&pFcb->OpenCount);
    CscSetLViewIsDfs(*(_QWORD *)&pFcb->OpenCount, *((_BYTE *)Entry + 528) & 1);
    CscReleaseLViewLock(*(_QWORD *)&pFcb->OpenCount);
    Buffer = *(_QWORD *)&pFcb->OpenCount;
    v14 = (unsigned __int8 *)Entry;
  }
  if ( !v7 )
  {
    if ( (*((_DWORD *)&RxContext->9 + 35) & 0x400) != 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 72, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids);
        v14 = (unsigned __int8 *)Entry;
      }
      v66 = 4798;
      inited = -1073741108;
      goto LABEL_175;
    }
    v100 = *(_QWORD *)(v287 + 40);
    if ( v100 )
    {
      if ( (*(_BYTE *)(v100 + 4) & 1) != 0 )
      {
        SlashDotOpen = CscCreateSlashDotOpen(RxContext, (__int64)v14);
        v14 = (unsigned __int8 *)Entry;
        inited = SlashDotOpen;
        v66 = 4823;
        goto LABEL_175;
      }
    }
  }
  if ( (Blink & 0x1C0) != 0 )
  {
    v66 = 4837;
    inited = -1073741811;
    goto LABEL_175;
  }
  v17 = 0;
  *(_DWORD *)&v268[7] = -1073741811;
  v272 = 0;
  if ( !Buffer )
    goto LABEL_8;
  v56 = _InterlockedCompareExchange64((volatile signed __int64 *)(*(_QWORD *)(Buffer + 48) + 40LL), 0, 0);
  v17 = v56;
  if ( !v56 )
  {
    *((_BYTE *)Entry + 535) |= 4u;
    v14 = (unsigned __int8 *)Entry;
LABEL_8:
    v9 = (unsigned __int64)&WPP_GLOBAL_Control;
    goto LABEL_9;
  }
  CscStoreEntryIsTransparentlyCached(v56, &v272);
  IsRootGhosted = CscLViewIsRootGhosted(*(_QWORD *)&pFcb->OpenCount);
  v9 = (unsigned __int64)&WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
  {
    v192 = 89;
    v193 = 78;
    if ( v272 )
      v193 = 89;
    if ( !IsRootGhosted )
      v192 = 78;
    v261 = v192;
    WPP_SF_cc(WPP_GLOBAL_Control->AttachedDevice, 73, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids, v193);
    v9 = (unsigned __int64)&WPP_GLOBAL_Control;
  }
  if ( IsRootGhosted || v272 )
    v121 = 0;
  else
    v121 = 4;
  *((_BYTE *)Entry + 535) = v121 | *((_BYTE *)Entry + 535) & 0xFB;
  v14 = (unsigned __int8 *)Entry;
LABEL_9:
  if ( !v7 )
  {
    Buffer = (__int64)RxContext->Create.UserName.Buffer;
    inited = *(_DWORD *)(Buffer + 16);
    if ( !*(_QWORD *)&pFcb->OpenCount )
    {
      v66 = 4908;
      goto LABEL_175;
    }
    *(_DWORD *)&v268[7] = *(_DWORD *)(Buffer + 16);
    if ( v17 )
    {
      BYTE1(v291[0]) = BYTE1(v291[0]) & 0xFD | (2 * (v272 & 1));
      if ( (v14[535] & 4) == 0 && !*(_BYTE *)(Buffer + 20) && (v14[533] & 2) == 0 )
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
          v14 = (unsigned __int8 *)Entry;
        }
        v66 = 4931;
        goto LABEL_175;
      }
    }
  }
  inited = CscPathUtilsInitParentPathFromFullPath(&String1, &RxContext->TrackerHistory[7].FileName);
  if ( inited < 0 )
  {
    v14 = (unsigned __int8 *)Entry;
    v66 = 4954;
    goto LABEL_175;
  }
  if ( (unsigned int)CscExclusionListCheckCreate((char *)&RxContext->9 + 112, pFcb, MrxSrvOpen, &String1, v261) == -1073739772 )
  {
    v103 = RxContext->Create.PipeCompletionMode == 3;
    v276 = 1;
    if ( !v103 )
    {
      v14 = (unsigned __int8 *)Entry;
      v66 = 4983;
      inited = -1073739772;
      goto LABEL_175;
    }
    RxContext->Create.PipeCompletionMode = 1;
  }
  v18 = v285;
  if ( !v7
    && (*(_DWORD *)(v285 + 56) & 0x40) == 0
    && !(unsigned __int8)CscEcpGetTypeValue(RxContext->CurrentIrp, 1)
    && (*((_BYTE *)Entry + 535) & 4) != 0 )
  {
    _InterlockedCompareExchange64(
      (volatile signed __int64 *)(*(_QWORD *)(*(_QWORD *)&pFcb->OpenCount + 48LL) + 40LL),
      0,
      0);
    CscOfflineLviewCacheAddEntryEx((PERESOURCE)(CscDevExtn + 384), 0);
  }
  CscGetContexts(RxContext, v13);
  v19 = v13 + 3;
  if ( (v277 & 0x2000) != 0 && (*(_DWORD *)(*v19 + 4LL) & 0x20) != 0
    || (v277 & 0x8000) != 0 && (v19 = v13 + 3, (*(_DWORD *)(v13[3] + 4LL) & 1) != 0) )
  {
    v20 = 4;
  }
  else
  {
    v20 = 0;
  }
  *((_BYTE *)Entry + 534) = v20 | *((_BYTE *)Entry + 534) & 0xFB;
  if ( !v7 && RxContext->Create.UserName.Buffer && *(_BYTE *)(*v19 + 48LL) && *(_BYTE *)(*v19 + 49LL) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 75, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids);
    *(_BYTE *)(*v19 + 48LL) = 0;
    *(_BYTE *)(*v19 + 49LL) = 0;
  }
  if ( (*(_DWORD *)(v18 + 56) & 0x10) != 0 || !v7 && (unsigned __int8)CscEcpGetTypeValue(RxContext->CurrentIrp, 2) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    {
      v172 = 89;
      v173 = 89;
      if ( (*((_BYTE *)Entry + 535) & 4) == 0 )
        v173 = 78;
      if ( !v7 )
        v172 = 78;
      WPP_SF_cDc(
        WPP_GLOBAL_Control->AttachedDevice,
        76,
        WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
        v172,
        *(_DWORD *)(v18 + 56),
        v173);
    }
    if ( (*((_BYTE *)Entry + 535) & 4) != 0 )
      CscTransitionLViewOffline(*(_QWORD *)&pFcb->OpenCount, 2);
  }
  inited = CscCreatepUpdateStateForAdminOpen(RxContext, Entry);
  if ( inited < 0 )
  {
    v14 = (unsigned __int8 *)Entry;
    v66 = 5069;
    goto LABEL_175;
  }
  v22 = MrxSrvOpen;
  LOBYTE(v21) = 1;
  CscUpdateAndCaptureConnectionStateEx((_DWORD)pFcb, (_DWORD)MrxSrvOpen, (_DWORD)RxContext, v21, (__int64)v291, 0);
  Timer_high = LOBYTE(v291[0]);
  Buffer = BYTE1(v291[0]);
  v14 = (unsigned __int8 *)Entry;
  v24 = v291[0] & 0xFB | (LOBYTE(v291[0]) | (LOBYTE(v291[0]) >> 3)) & 4;
  LOBYTE(v291[0]) = v24;
  if ( (v291[0] & 0x1000) != 0 || (*((_BYTE *)Entry + 534) & 4) != 0 )
    LOBYTE(Timer_high) = 16;
  else
    LOBYTE(Timer_high) = 0;
  LOBYTE(Buffer) = Timer_high | BYTE1(v291[0]) & 0xEF;
  BYTE1(v291[0]) = Buffer;
  if ( ((v24 & 0x40) != 0 || !v13[2]) && (v24 & 0x10) == 0 && (*((_BYTE *)Entry + 533) & 0x12) == 0 )
  {
    v55 = CscCheckConnectionProperties(
            *(_QWORD *)(*(_QWORD *)&pFcb->OpenCount + 32LL),
            v285,
            (unsigned int)v291,
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
      v14 = (unsigned __int8 *)Entry;
    }
    else
    {
      v14 = (unsigned __int8 *)Entry;
    }
  }
  v25 = v13[1];
  if ( v25
    && *(_DWORD *)(v25 + 8)
    && (Timer_high = v14[533], (Timer_high & 4) != 0)
    && ((__int64)pFcb[1].Header.FilterContexts.Flink & 0x10) == 0 )
  {
    v26 = v277;
    LOBYTE(Timer_high) = Timer_high & 0xFB;
    LODWORD(v26) = v277 & 0xFFFBFFFF;
    v14[533] = Timer_high;
    v14 = (unsigned __int8 *)Entry;
    v278 = v26;
  }
  else
  {
    v26 = v278;
  }
  v27 = v14[533];
  if ( (v27 & 4) != 0 )
  {
    v9 = *((unsigned int *)&RxContext->9 + 28);
    if ( (v9 & 0xFFEFFF7F) != 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
      {
        WPP_SF_DqD(
          WPP_GLOBAL_Control->AttachedDevice,
          78,
          WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
          v26,
          pFcb,
          v9);
        v14 = (unsigned __int8 *)Entry;
      }
      v66 = 5125;
      inited = -1073741811;
      goto LABEL_175;
    }
    v14[533] = v27 | 2;
    *((_BYTE *)Entry + 533) |= 0x40u;
    v14 = (unsigned __int8 *)Entry;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
  {
    v273 = v14[540];
    v268[0] = v14[539];
    v85 = v13[1];
    if ( v85 )
      updated = *(_DWORD *)(v85 + 72);
    else
      updated = -1;
    v194 = v14[533];
    v195 = v13[2];
    v196 = BYTE1(v291[0]) >> 4;
    GlobalNewlyCachedEpoch = CscQueryGlobalNewlyCachedEpoch(Timer_high, Buffer, v9, v26);
    v198 = 89;
    if ( !v273 )
      v198 = 78;
    v199 = 89;
    v200 = 89;
    v201 = 89;
    v202 = 89;
    if ( !v268[0] )
      v199 = 78;
    v103 = (v196 & 1) == 0;
    v203 = 89;
    if ( v103 )
      v200 = 78;
    if ( (v194 & 4) == 0 )
      v203 = 78;
    if ( (v194 & 8) == 0 )
      v201 = 78;
    v265 = v198;
    v103 = v195 == 0;
    pFcb = v286;
    v7 = v267;
    if ( !v103 )
      v202 = 78;
    v204 = 89;
    if ( !v267 )
      v204 = 78;
    WPP_SF_cDDcccqqqDDDdcddccZ(
      WPP_GLOBAL_Control->AttachedDevice,
      79,
      (unsigned int)WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
      v204,
      v278,
      v277,
      v202,
      v201,
      v203,
      (char)v286,
      *(_QWORD *)&v286->OpenCount,
      (char)MrxSrvOpen,
      HIDWORD(v286->SrvOpenList.Flink),
      HIDWORD(v286->SrvOpenList.Blink),
      (char)v286->SrvOpenList.Blink,
      RxContext->Create.PipeCompletionMode,
      v200,
      updated,
      GlobalNewlyCachedEpoch,
      v199,
      v265,
      (__int64)&RxContext->TrackerHistory[7].FileName);
    v14 = (unsigned __int8 *)Entry;
    v22 = MrxSrvOpen;
  }
  v28 = v13[1];
  if ( v28 && *(_QWORD *)(v28 + 64) )
  {
    v106 = v13[1];
    if ( MEMORY[0xFFFFF78000000014] <= *(_QWORD *)(v106 + 64) )
    {
      if ( (*(_DWORD *)(v106 + 4) & 0x1166F) == 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 81, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids);
        }
        LOBYTE(v291[0]) |= 0x12u;
        CscTransitionFcbOffline((__int64)pFcb, 0, 8, 0);
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 80, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids);
      *(_QWORD *)(v13[1] + 64LL) = 0;
    }
    v14 = (unsigned __int8 *)Entry;
  }
  Buffer = v14[533];
  if ( (Buffer & 8) != 0 )
    goto LABEL_357;
  v29 = v13[1];
  if ( v29 && (v291[0] & 0x40) == 0 && v7 )
  {
    if ( (v291[0] & 1) != 0 )
    {
      if ( (v291[0] & 0x400) == 0 || (v291[0] & 0x1000) == 0 || (v291[0] & 0x800) == 0 )
        goto LABEL_31;
    }
    else
    {
      v110 = *(_DWORD *)(v29 + 4);
      if ( (v110 & 0x200) == 0 && (v110 & 0x80000) == 0 && v291[2] <= *(_DWORD *)(v29 + 40) )
        goto LABEL_31;
    }
    v111 = *(_DWORD *)(v29 + 4);
    if ( (v111 & 0x1166F) != 0
      && ((unsigned __int8)~((unsigned __int8)Buffer >> 6) & ((v111 & 0x1000060) == 0)) != 0
      && !*(_QWORD *)(v29 + 64) )
    {
LABEL_357:
      if ( (v14[534] & 4) != 0 )
        ++*(_DWORD *)(v13[1] + 76LL);
      v112 = CscBackPatchObject((__int64)RxContext, (char *)v291, (__int64)v13);
      v14 = (unsigned __int8 *)Entry;
      Buffer = v112;
      if ( (*((_BYTE *)Entry + 533) & 8) != 0 || v112 == -1073741225 )
      {
        if ( (*((_BYTE *)Entry + 534) & 4) != 0 )
        {
          --*(_DWORD *)(v13[1] + 76LL);
          v14 = (unsigned __int8 *)Entry;
        }
        inited = v112;
        v66 = 5268;
        goto LABEL_175;
      }
      CscUpdateFcbContextOnBackpatch(v13[1], v291, v112);
      LOBYTE(v113) = 1;
      CscUpdateAndCaptureConnectionStateEx((_DWORD)pFcb, (_DWORD)v22, (_DWORD)RxContext, v113, (__int64)v291, 0);
      v14 = (unsigned __int8 *)Entry;
      v114 = v291[0] & 0xFB | (LOBYTE(v291[0]) | (LOBYTE(v291[0]) >> 3)) & 4;
      LOBYTE(v291[0]) = v114;
      if ( (*((_BYTE *)Entry + 534) & 4) != 0 )
      {
        --*(_DWORD *)(v13[1] + 76LL);
        v114 = v291[0];
        v14 = (unsigned __int8 *)Entry;
      }
      if ( (v114 & 0x10) == 0
        && (HIBYTE(pFcb[2].Header.NodeByteSize) & 0x3C) == 0xC
        && (*((_DWORD *)&RxContext->9 + 35) & 0x200000) != 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 82, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids);
          v14 = (unsigned __int8 *)Entry;
        }
        v66 = 5312;
        inited = -1069481983;
        goto LABEL_175;
      }
      v14[534] |= 8u;
      v14 = (unsigned __int8 *)Entry;
    }
  }
LABEL_31:
  v30 = v14[534];
  if ( (v30 & 4) != 0
    && (v30 & 8) == 0
    && v7
    && (v291[0] & 0x400) != 0
    && (!v13[1] || (v291[0] & 0x800) != 0)
    && (v14[533] & 0x40) == 0 )
  {
    LOBYTE(v291[0]) &= 0xEDu;
    v205 = v13[1];
    if ( v205 )
    {
      *(_DWORD *)(v205 + 4) &= 0xFFFEFFFE;
      v14 = (unsigned __int8 *)Entry;
    }
  }
  if ( (v291[0] & 4) != 0 )
  {
    v88 = v13[1];
    if ( v88 )
    {
      v14[528] = v14[528] & 0xEF | (*(_DWORD *)(v88 + 4) >> 18) & 0x10;
      *((_OWORD *)Entry + 24) = *(_OWORD *)&RxContext->TrackerHistory[7].FileName;
      *((_WORD *)Entry + 192) = *(_WORD *)(v13[1] + 80LL);
    }
    else
    {
      v89 = CscOkToCacheFileName((__int64)&RxContext->TrackerHistory[7].FileName, (__int64)(v14 + 384));
      Buffer = (__int64)Entry;
      v90 = 0;
      v9 = 16;
      if ( !v89 )
        v90 = 16;
      *((_BYTE *)Entry + 528) = *((_BYTE *)Entry + 528) & 0xEF | v90;
    }
    v14 = (unsigned __int8 *)Entry;
    if ( (*((_BYTE *)Entry + 528) & 0x10) != 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 83, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids);
        v14 = (unsigned __int8 *)Entry;
      }
      LOBYTE(v291[0]) &= ~0x10u;
      if ( (v291[0] & 1) != 0 )
      {
        v66 = 5408;
        inited = -1073741108;
        goto LABEL_175;
      }
      v91 = *((unsigned __int16 *)v14 + 192);
      if ( (_WORD)v91 )
      {
        v9 = *((unsigned __int16 *)v14 + 193);
        if ( (unsigned __int16)v91 < (unsigned __int16)v9
          && v91 + 2 < v9
          && *(_WORD *)(*((_QWORD *)v14 + 49) + 2 * ((unsigned __int64)*((unsigned __int16 *)v14 + 192) >> 1)) == 58 )
        {
          InformationEntry = CscStoreRelativeQueryInformationEntry(0, v14 + 384, v14 + 120, v14 + 56);
          v14 = (unsigned __int8 *)Entry;
          if ( InformationEntry >= 0
            && (*((_DWORD *)Entry + 26) & 0x10) == 0
            && (*((_DWORD *)Entry + 30) & 0x80417) != 0 )
          {
            v66 = 5440;
            inited = -1073741108;
            goto LABEL_175;
          }
        }
      }
    }
  }
  v31 = v14[533];
  v279 = 0;
  if ( (v291[0] & 4) == 0 )
  {
    if ( (v31 & 0x5A) != 0 || v31 < 0 || (v14[534] & 4) != 0 )
    {
      v257 = CscStoreFindEntry(&v269, 0, &RxContext->TrackerHistory[7].FileName);
      v14 = (unsigned __int8 *)Entry;
      inited = -1073741772;
      v66 = 6018;
      if ( v257 < 0 )
        inited = v257;
      goto LABEL_175;
    }
    v268[0] = 0;
    goto LABEL_78;
  }
  if ( (v31 & 6) == 2 )
    LOBYTE(v291[0]) |= 0x10u;
  if ( v7 )
  {
    v93 = v14[533];
    if ( (v93 & 0x40) != 0 )
    {
      if ( (v291[0] & 0x10) != 0 )
      {
        v14[533] = v93 & 0xBF;
        v14 = (unsigned __int8 *)Entry;
      }
      else
      {
        LOBYTE(v291[0]) |= 0x10u;
      }
    }
  }
  if ( (v291[0] & 0x20) != 0 )
  {
    v14[529] |= 0x80u;
    v14 = (unsigned __int8 *)Entry;
  }
  v32 = RxSidFromRxContext(RxContext, v14 + 200, v9, v26);
  v14 = (unsigned __int8 *)Entry;
  if ( v32 < 0 )
  {
    inited = v32;
    v66 = 5499;
    goto LABEL_175;
  }
  v34 = 0;
  v103 = (*((_BYTE *)Entry + 528) & 0x10) == 0;
  v268[0] = 0;
  if ( v103 && v7 && (v291[0] & 0x10) == 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 84, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids);
      v14 = (unsigned __int8 *)Entry;
    }
    v35 = CscStoreFindEntryEx((unsigned int)&v269, 0, (int)RxContext + 816, (int)v14 + 537, (__int64)(v14 + 538));
    if ( v35 )
    {
      v14 = (unsigned __int8 *)Entry;
      v34 = 0;
      v268[0] = 0;
      Buffer = v35;
      v279 = v35;
      goto LABEL_46;
    }
    v273 = 0;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
      WPP_SF_qqq(
        WPP_GLOBAL_Control->AttachedDevice,
        85,
        WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
        v269,
        pFcb,
        v22);
    *((_BYTE *)Entry + 529) |= 0x80u;
    CanSidDecryptEntry = CscStoreQueryCanSidDecryptEntry(v269, (char *)Entry + 200, &v273);
    if ( CanSidDecryptEntry < 0 )
    {
      v14 = (unsigned __int8 *)Entry;
      inited = CanSidDecryptEntry;
      v66 = 5537;
      goto LABEL_175;
    }
    if ( !v273 )
    {
      CscStoreDereferenceEntry(&v269);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
        WPP_SF_qqq(
          WPP_GLOBAL_Control->AttachedDevice,
          86,
          WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
          v269,
          pFcb,
          v22);
      v206 = CscCreateReparseToRemoteCreate(RxContext);
      v14 = (unsigned __int8 *)Entry;
      inited = v206;
      v66 = 5556;
      goto LABEL_175;
    }
    v123 = CscStoreQueryInformationEntryEx(
             (__int64)v269,
             0,
             (__int64)Entry + 120,
             (__int64)Entry + 56,
             (_BYTE *)Entry + 536,
             0,
             0);
    if ( v123 < 0 )
    {
      CscStoreDereferenceEntry(&v269);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
        WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 87, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids, v269, v123);
      v14 = (unsigned __int8 *)Entry;
      inited = v123;
      v66 = 5573;
      goto LABEL_175;
    }
    v34 = 1;
    v22 = MrxSrvOpen;
    v268[0] = 1;
    *((_BYTE *)Entry + 535) |= 1u;
    v14 = (unsigned __int8 *)Entry;
  }
  Buffer = v279;
LABEL_46:
  v36 = v13[1];
  if ( !v36 )
  {
    v37 = 0;
LABEL_48:
    if ( (v14[528] & 0x10) != 0 || !v7 || (v291[0] & 0x10) != 0 )
    {
LABEL_59:
      if ( !v13[1] )
      {
        inited = CscAllocateAndApplyFcbContext((__int64)pFcb, (__int64)v13, v9, v33);
        if ( inited )
        {
          v14 = (unsigned __int8 *)Entry;
          v66 = 5824;
          goto LABEL_175;
        }
      }
      *(_DWORD *)(v13[1] + 4LL) = v37;
      Buffer = (__int64)Entry;
      if ( (*((_BYTE *)Entry + 528) & 0x10) != 0 )
      {
        *(_DWORD *)(v13[1] + 4LL) |= 0x400000u;
        Buffer = (__int64)Entry;
      }
      *(_WORD *)(v13[1] + 80LL) = *(_WORD *)(Buffer + 384);
      if ( v7 )
        RxSetFcbDispatchTable(pFcb, CscDeviceObject[1].NextDevice);
      goto LABEL_64;
    }
    if ( (v14[534] & 0x10) == 0 && v14[537] )
    {
      LOBYTE(v291[0]) |= 0x12u;
      v37 |= 0x1000u;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 88, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids);
        Buffer = v279;
        v14 = (unsigned __int8 *)Entry;
      }
      v34 = v268[0];
    }
    if ( v14[538] )
    {
      v207 = v14[533];
      if ( (v207 & 0x12) == 0 && v207 >= 0 )
      {
        v66 = 5644;
        inited = -1073741766;
        goto LABEL_175;
      }
    }
    if ( !v34 )
    {
      if ( (v14[534] & 0x10) == 0 && ((_DWORD)Buffer == -1073741766 || (_DWORD)Buffer == -1073741772) )
      {
        v38 = RxContext->Create.PipeCompletionMode;
        if ( v38 <= 5 )
        {
          v39 = 45;
          if ( _bittest(&v39, v38) )
          {
            if ( (unsigned __int8)CscCreatepCheckIfLongestPrefixInCacheIsDirty(&RxContext->TrackerHistory[7].FileName) )
            {
              LOBYTE(v291[0]) |= 0x12u;
              v37 |= 8u;
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
      goto LABEL_59;
    }
    v160 = CscStoreQueryInformationEntryEx((__int64)v269, 0, (__int64)(v14 + 120), (__int64)(v14 + 56), v14 + 536, 0, 0);
    v14 = (unsigned __int8 *)Entry;
    if ( v160 < 0 )
    {
      inited = v160;
      v66 = 5769;
      goto LABEL_175;
    }
    v161 = *((_DWORD *)Entry + 30);
    Buffer = v161 & 0x10;
    if ( (v161 & 0x10) != 0 && (*((_BYTE *)Entry + 533) & 2) != 0 && (*((_DWORD *)Entry + 26) & 0x10) != 0 )
    {
      LOBYTE(v291[0]) |= 2u;
      *((_BYTE *)Entry + 532) |= 1u;
      *((_BYTE *)Entry + 533) |= 0x10u;
      v208 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
      {
        v209 = 89;
LABEL_923:
        WPP_SF_(v208->AttachedDevice, v209, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids);
      }
    }
    else
    {
      v162 = *((_BYTE *)Entry + 533);
      if ( ((v162 & 0x10) == 0 || (v161 & 0x30) == 0) && ((v162 & 0x20) == 0 || (v161 & 0x10000) == 0) )
      {
        if ( (v161 & 0x10) != 0 )
        {
          v210 = RxContext->Create.PipeCompletionMode;
          if ( v210 > 5 || (v9 = 45, !_bittest((const int *)&v9, v210)) )
          {
            v66 = 5710;
            inited = -1073741772;
            goto LABEL_175;
          }
        }
        if ( RxContext->Create.PipeCompletionMode == 2 && (v161 & 0x10) == 0 && (v161 & 0x800000) == 0 )
        {
          *((_QWORD *)&RxContext->9 + 25) = 4;
          v66 = 5725;
          inited = -1073741771;
          goto LABEL_175;
        }
        if ( (v161 & 0x400) != 0
          || (v163 = *((_DWORD *)Entry + 26), (v161 & 0x80417) != 0) && (v163 & 0x10) == 0
          || ((unsigned __int8)v163 & (unsigned __int8)v161 & 0x10) != 0 )
        {
          LOBYTE(v291[0]) |= 0x12u;
          v37 |= 8u;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
          {
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              91,
              WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
              *((unsigned int *)Entry + 30));
            v14 = (unsigned __int8 *)Entry;
          }
        }
        if ( (*((_DWORD *)v14 + 30) & 0x10) == 0 )
          goto LABEL_571;
        if ( RxContext->Create.PipeCompletionMode != 3 )
          goto LABEL_571;
        LOBYTE(v291[0]) |= 0x12u;
        v37 |= 8u;
        v208 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) == 0 )
        {
          goto LABEL_571;
        }
        v209 = 92;
        goto LABEL_923;
      }
      LOBYTE(v291[0]) |= 0x12u;
      *((_BYTE *)Entry + 532) |= 1u;
      v208 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
      {
        v209 = 90;
        goto LABEL_923;
      }
    }
LABEL_571:
    CscStoreDereferenceEntry(&v269);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
      WPP_SF_qqq(
        WPP_GLOBAL_Control->AttachedDevice,
        93,
        WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
        v269,
        pFcb,
        MrxSrvOpen);
    goto LABEL_59;
  }
  if ( (v291[0] & 0x40) != 0 )
  {
    v37 = *(_DWORD *)(v36 + 4);
    goto LABEL_48;
  }
  if ( !v34 )
    goto LABEL_65;
  CscStoreDereferenceEntry(&v269);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    WPP_SF_qqq(WPP_GLOBAL_Control->AttachedDevice, 95, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids, v269, pFcb, v22);
LABEL_64:
  v14 = (unsigned __int8 *)Entry;
LABEL_65:
  if ( (v291[0] & 0x10) != 0 && (*((_DWORD *)v14 + 30) & 0x800000) != 0 )
  {
    v9 = v14[533];
    if ( (v9 & 2) == 0 )
    {
      v115 = 0;
      if ( (v9 & 0x10) == 0 )
        v115 = (v14[532] & 1) == 0;
      if ( v115 && (*(_DWORD *)(v13[1] + 4LL) & 8) == 0 && (v9 & 0x40) == 0 )
      {
        if ( !v7 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 96, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids);
            v14 = (unsigned __int8 *)Entry;
          }
          p_EaBuffer = &RxContext->Create.EaBuffer;
          v66 = 5894;
          inited = *((_DWORD *)RxContext->Create.UserName.Buffer + 4);
          goto LABEL_176;
        }
        if ( (*(_DWORD *)(v285 + 56) & 0x10) == 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 97, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids);
            v14 = (unsigned __int8 *)Entry;
          }
          LOBYTE(v291[0]) &= ~0x10u;
        }
      }
    }
  }
  if ( (v14[528] & 0x10) == 0
    && (*(_DWORD *)(v13[1] + 4LL) & 0x2000) != 0
    && (*((_DWORD *)&RxContext->9 + 28) & 0xFFEFFF7F) != 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 98, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids);
      v14 = (unsigned __int8 *)Entry;
    }
    v66 = 5922;
    inited = -1073741757;
    goto LABEL_175;
  }
  if ( v13[2] )
  {
    v41 = MrxSrvOpen;
  }
  else
  {
    Pool2 = (struct _UNICODE_STRING *)ExAllocatePool2(256, 48, 1061124178, v33);
    v13[2] = Pool2;
    if ( !Pool2 )
    {
      v14 = (unsigned __int8 *)Entry;
      v66 = 5940;
      inited = -1073741670;
      goto LABEL_175;
    }
    v41 = MrxSrvOpen;
    MrxSrvOpen->pAlreadyPrefixedName = Pool2;
    *(_DWORD *)&Pool2->Length = 3205794;
    *((_BYTE *)Entry + 528) |= 0x40u;
  }
  v42 = v278;
  *(_DWORD *)(v13[2] + 32LL) = v278;
  if ( (*((_BYTE *)Entry + 533) & 2) != 0 )
    *(_DWORD *)(v13[2] + 24LL) |= 1u;
  if ( (v42 & 1) != 0 )
    LODWORD(v41->Key) |= 0x1080u;
  if ( *((_BYTE *)Entry + 539) && (v291[0] & 0x100) != 0 )
    *(_DWORD *)(v13[1] + 4LL) |= 0x4000000u;
  else
    *(_DWORD *)(v13[1] + 4LL) &= ~0x4000000u;
  v14 = (unsigned __int8 *)Entry;
LABEL_78:
  v267 = 0;
  if ( !v7 || (v291[0] & 0x10) != 0 )
    v43 = 0;
  else
    v43 = 8;
  v14[528] = v43 | v14[528] & 0xF7;
  v14 = (unsigned __int8 *)Entry;
  if ( (*((_BYTE *)Entry + 528) & 8) == 0 )
    goto LABEL_120;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 99, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids);
    v14 = (unsigned __int8 *)Entry;
  }
  v44 = v13[1];
  if ( v44 )
  {
    ++*(_DWORD *)(v44 + 32);
    PagingIoResource = (int)pFcb[1].Header.PagingIoResource;
    if ( PagingIoResource )
    {
      if ( PagingIoResource == *(_DWORD *)(v13[1] + 20LL) )
      {
        HIDWORD(pFcb->SrvOpenList.Flink) &= ~0x40000u;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 100, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids);
        }
      }
    }
    v14 = (unsigned __int8 *)Entry;
  }
  Buffer = LOBYTE(v291[0]);
  if ( (v291[0] & 0x20) != 0 && (v291[0] & 0x200) == 0 )
    goto LABEL_101;
  if ( (v291[0] & 0x40) != 0 )
  {
    if ( !v14[539] )
      goto LABEL_86;
    if ( (v14[535] & 1) == 0 || (*((_DWORD *)v14 + 30) & 0x800000) == 0 )
      goto LABEL_101;
  }
  if ( v14[539] && (v291[0] & 0x20) == 0 )
    goto LABEL_101;
LABEL_86:
  if ( ((v291[3] - 4) & 0xFFFFFFFB) == 0
    || (v45 = v13[3]) != 0 && *(_QWORD *)(v45 + 40) && (*(_DWORD *)(v45 + 4) & 0x2000) == 0 )
  {
LABEL_101:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    {
      v150 = 89;
      v151 = 89;
      if ( (v14[535] & 1) == 0 )
        v151 = 78;
      v152 = 89;
      v153 = 89;
      if ( (v291[0] & 0x200) == 0 )
        v152 = 78;
      if ( (v291[0] & 0x40) == 0 )
        v150 = 78;
      if ( (v291[0] & 0x20) == 0 )
        v153 = 78;
      WPP_SF_ZccccDcD(
        WPP_GLOBAL_Control->AttachedDevice,
        101,
        (unsigned int)WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
        (_DWORD)RxContext + 816,
        v153,
        v150,
        (((char)v14[529] >> 7) & 0xB) + 78,
        v152,
        v291[3],
        v151,
        *((_DWORD *)v14 + 30));
      Buffer = LOBYTE(v291[0]);
      v14 = (unsigned __int8 *)Entry;
    }
    LODWORD(RxContext->RdbssDbgExtension) |= 0x20000000u;
    goto LABEL_103;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
  {
    v46 = 89;
    v47 = 89;
    if ( (v14[535] & 1) == 0 )
      v46 = 78;
    v48 = 89;
    v49 = 89;
    if ( (v291[0] & 0x200) == 0 )
      v47 = 78;
    if ( (v291[0] & 0x40) == 0 )
      v48 = 78;
    if ( (v291[0] & 0x20) == 0 )
      v49 = 78;
    WPP_SF_ZccccDcD(
      WPP_GLOBAL_Control->AttachedDevice,
      102,
      (unsigned int)WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
      (_DWORD)RxContext + 816,
      v49,
      v48,
      (((char)v14[529] >> 7) & 0xB) + 78,
      v47,
      v291[3],
      v46,
      *((_DWORD *)v14 + 30));
    Buffer = LOBYTE(v291[0]);
    v14 = (unsigned __int8 *)Entry;
  }
LABEL_103:
  v9 = v287;
  if ( *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v287 + 48) + 352LL) + 56LL) )
  {
    if ( ((__int64)RxContext->ScavengerEntry.List.Flink & 2) == 0 )
    {
      *(_OWORD *)&RxContext->MRxContext[2] = 0;
      *(_OWORD *)&RxContext->WriteOnlyOpenRetryContext = 0;
      RxContext->ResumeRoutine = 0;
      v50 = (*(__int64 (__fastcall **)(PRX_CONTEXT, __int64, unsigned __int64, __int64))(*(_QWORD *)(*(_QWORD *)(v9 + 48) + 352LL)
                                                                                       + 56LL))(
              RxContext,
              Buffer,
              v9,
              32);
      Buffer = LOBYTE(v291[0]);
      v9 = v287;
      v51 = v50;
      v14 = (unsigned __int8 *)Entry;
      *(_DWORD *)&v268[3] = v50;
      goto LABEL_106;
    }
    v51 = -1073741536;
  }
  else
  {
    v51 = -1073741822;
  }
  *(_DWORD *)&v268[3] = v51;
LABEL_106:
  v52 = v13[1];
  if ( v52 )
  {
    --*(_DWORD *)(v52 + 32);
    Buffer = LOBYTE(v291[0]);
    v14 = (unsigned __int8 *)Entry;
  }
  inited = v51;
  if ( (Buffer & 4) != 0 )
  {
    *(_DWORD *)(v13[2] + 24LL) |= 4u;
    *(_QWORD *)(v13[2] + 40LL) = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v9 + 48) + 352LL) + 136LL);
    *(_DWORD *)(v13[1] + 4LL) |= 0x10u;
    *(_QWORD *)(v13[1] + 88LL) = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v9 + 48) + 352LL) + 128LL);
    v53 = 0;
    if ( !*(_DWORD *)(v13[1] + 8LL) )
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
      if ( !(unsigned __int8)CscTransitnOKToGoOffline((unsigned int)v51) || (v267 = 1, (v291[0] & 0x200) != 0) )
      {
        Buffer = LOBYTE(v291[0]);
      }
      else
      {
        Buffer = LOBYTE(v291[0]);
        LOBYTE(Buffer) = LOBYTE(v291[0]) | 0x12;
        LOBYTE(v291[0]) |= 0x12u;
      }
      if ( (Buffer & 0x10) == 0 )
      {
        if ( (unsigned int)(v51 + 1073741790) > 0x18 || (v109 = 17039361, !_bittest(&v109, v51 + 1073741790)) )
        {
          if ( (Buffer & 0x40) == 0 || v51 != -1073741565 && v51 != -1073741638 )
          {
            v14 = (unsigned __int8 *)Entry;
            v66 = 6181;
            goto LABEL_175;
          }
        }
      }
      v14 = (unsigned __int8 *)Entry;
      goto LABEL_135;
    }
    v54 = MrxSrvOpen;
    CscUpdateRdrOpenCount(v13[1], MrxSrvOpen, 1, 32);
    *((_BYTE *)Entry + 532) |= 0x40u;
    *(_DWORD *)(v13[1] + 36LL) = *(_DWORD *)(v13[3] + 8LL);
    *(_DWORD *)(v13[2] + 24LL) |= 2u;
    if ( ((__int64)v54->Key & 0x100000) == 0 )
      *((_BYTE *)Entry + 532) |= 0x20u;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
      WPP_SF_Dd(
        WPP_GLOBAL_Control->AttachedDevice,
        103,
        WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
        *(unsigned int *)(v13[1] + 8LL),
        RxContext->TrackerHistory[4].AcquireRelease);
    Buffer = LOBYTE(v291[0]);
    v14 = (unsigned __int8 *)Entry;
  }
  else
  {
    v267 = 0;
    if ( v51 < 0 )
      goto LABEL_135;
  }
  if ( *(_DWORD *)(v13[3] + 8LL) > *(_DWORD *)(v13[3] + 12LL) )
  {
    CscNotifyLViewReconnect(RxContext, pFcb, v13);
    v14 = (unsigned __int8 *)Entry;
LABEL_120:
    Buffer = LOBYTE(v291[0]);
  }
LABEL_135:
  if ( (Buffer & 0x10) != 0 )
  {
    v117 = *((_QWORD *)&RxContext->9 + 18);
    if ( v117 )
    {
      if ( *(_QWORD *)(*(_QWORD *)(v117 + 8) + 64LL) )
      {
        if ( !v268[0] && (Buffer & 4) != 0 )
        {
          v118 = RxContext->Create.PipeCompletionMode;
          if ( v118 <= 5 )
          {
            v119 = 45;
            if ( _bittest(&v119, v118) )
            {
              v66 = 6217;
              inited = -1073741108;
              goto LABEL_175;
            }
          }
        }
      }
    }
  }
  if ( (HIBYTE(pFcb[2].Header.NodeByteSize) & 0x3C) == 8 )
  {
    v102 = inited;
    v66 = 6246;
    if ( (v14[528] & 8) == 0 )
      v102 = -1073741108;
    inited = v102;
    goto LABEL_175;
  }
  if ( (Buffer & 4) != 0 && (v14[528] & 0x10) == 0 )
  {
    if ( (Buffer & 0x40) != 0 )
      goto LABEL_141;
    if ( (Buffer & 0x10) != 0 )
      goto LABEL_141;
    v116 = v13[1];
    if ( !v116 || *(_QWORD *)(v116 + 56) )
      goto LABEL_141;
  }
  if ( v7 || (Buffer & 4) != 0 )
  {
    if ( (v14[528] & 8) == 0 )
    {
      v103 = inited == 0;
      if ( inited >= 0 )
      {
        inited = -1073741108;
LABEL_325:
        v66 = 6301;
        goto LABEL_175;
      }
      goto LABEL_319;
    }
  }
  else
  {
    inited = *(_DWORD *)&v268[7];
  }
  v103 = inited == 0;
LABEL_319:
  if ( !v103 )
    goto LABEL_325;
  if ( (Buffer & 4) == 0 )
    goto LABEL_325;
  if ( (Buffer & 0x10) != 0 )
    goto LABEL_325;
  v104 = v13[1];
  if ( !v104 )
    goto LABEL_325;
  if ( (v14[528] & 0x10) != 0 )
    goto LABEL_325;
  v105 = CscMatchesGlobalNewlyCachedEpoch(*(unsigned int *)(v104 + 72));
  v14 = (unsigned __int8 *)Entry;
  if ( v105 )
    goto LABEL_325;
  LOBYTE(Buffer) = v291[0];
LABEL_141:
  v57 = 8 * ((Buffer & 0x10) != 0);
  if ( (Buffer & 0x10) == 0 && !v291[3] && (Buffer & 0x40) == 0
    || (v58 = v267, (v14[528] & 8) != 0) && !v267 && *(int *)&v268[3] < 0
    || (Buffer & 0x10) != 0
    && ((v107 = RxContext->Create.PipeCompletionMode, v107 > 5) || (v108 = 45, !_bittest(&v108, v107))) )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) == 0 )
      goto LABEL_158;
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 107, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids);
LABEL_254:
    v14 = (unsigned __int8 *)Entry;
    LOBYTE(Buffer) = v291[0];
    goto LABEL_158;
  }
  if ( (Buffer & 0x10) != 0 || v291[3] || (*(_DWORD *)(v13[1] + 4LL) & 0x80u) != 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 106, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids);
      LOBYTE(Buffer) = v291[0];
      v58 = v267;
      v14 = (unsigned __int8 *)Entry;
    }
    if ( (Buffer & 0x10) == 0 )
      v57 |= 1u;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 105, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids);
      LOBYTE(Buffer) = v291[0];
      v58 = v267;
      v14 = (unsigned __int8 *)Entry;
    }
    v57 |= 0x401u;
    if ( v14[539] )
      v57 |= 0x40000u;
  }
  v57 |= 2u;
  if ( (v14[528] & 8) == 0 || (_BYTE)v58 )
  {
    v211 = CscInitNetInfoFromRxContext(RxContext, v14, v58);
    if ( v211 < 0 )
    {
      v14 = (unsigned __int8 *)Entry;
      inited = v211;
      v66 = 6402;
      goto LABEL_175;
    }
    *((_BYTE *)Entry + 528) |= 2u;
    goto LABEL_254;
  }
LABEL_158:
  if ( (Buffer & 0x10) == 0 && *(int *)&v268[3] >= 0 && *((_QWORD *)&RxContext->9 + 25) == 2 )
    v57 |= 0x10000u;
  v14[528] = v14[528] & 0xFB | ((v57 & 0x402) != 0 ? 4 : 0);
  v59 = v57 | 4;
  if ( (v291[0] & 0x10) == 0 )
    v59 = v57;
  *(_DWORD *)&v268[7] = v59;
  RxSubjectContextFromRxContext(RxContext, &v284);
  v60 = (char *)Entry;
  v61 = *((_BYTE *)Entry + 528);
  if ( (v61 & 4) != 0 || *((char *)Entry + 529) < 0 )
  {
    v62 = v267;
    if ( (v291[0] & 0x10) == 0 || v267 )
    {
      v268[0] = v61 & 1;
      v86 = v59 | (*((char *)Entry + 529) >> 7) & 0x800;
      if ( !v291[3] || v291[3] == 12 )
        v86 = v59 & 0xFFFFFFFC | (*((char *)Entry + 529) >> 7) & 0x800;
      v87 = 0;
      if ( (v59 & 8) != 0 )
        v87 = v284;
      CscUpdateShareInfoForLogicalView(
        (int)RxContext,
        v86,
        (_DWORD)Entry + 200,
        v291[3],
        (__int64)v268,
        (PCUNICODE_STRING)&RxContext->TrackerHistory[7].FileName,
        (__int64)&v270,
        v87);
      v60 = (char *)Entry;
    }
  }
  else
  {
    v62 = v267;
  }
  if ( v60[529] >= 0 )
  {
    HasStoreEntry = CscLViewContextHasStoreEntry(*(_QWORD *)&pFcb->OpenCount);
    *((_BYTE *)Entry + 529) = *((_BYTE *)Entry + 529) & 0x7F | (HasStoreEntry << 7);
    v60 = (char *)Entry;
  }
  if ( (v60[528] & 8) != 0 && !v62 || (v291[0] & 0x40) == 0 )
  {
    RxInitNetInfoFromFcb(pFcb, v60);
    *((_BYTE *)Entry + 528) |= 2u;
    v60 = (char *)Entry;
  }
  v64 = v13[1];
  if ( *(_QWORD *)(v64 + 56) )
  {
    v269 = *(struct _LIST_ENTRY **)(v64 + 56);
    CscStoreReferenceEntry(v269);
    v65 = *(_DWORD *)&v268[7];
    if ( (*(_DWORD *)(v13[1] + 4LL) & 0x800000) != 0 )
      LODWORD(v270) = v270 | 0x40;
    goto LABEL_171;
  }
  v75 = *(_QWORD *)&pFcb->OpenCount;
  LODWORD(v286) = 0;
  v76 = 0;
  v77 = 0;
  if ( (v59 & 8) != 0 )
    v76 = v284;
  if ( (v60[528] & 4) != 0 )
    v77 = (__int64)v60;
  v78 = CscStoreFindOrCreateEntry(
          (unsigned int)&v269,
          (unsigned int)&v286,
          0,
          (int)RxContext + 816,
          v59,
          v77,
          _InterlockedCompareExchange64((volatile signed __int64 *)(*(_QWORD *)(v75 + 48) + 40LL), 0, 0),
          v76);
  updated = v78;
  LODWORD(v270) = (unsigned int)v286 | v270;
  if ( v78 < 0 )
  {
LABEL_212:
    v80 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        109,
        WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
        (unsigned int)v78);
    if ( (v291[0] & 0x10) == 0 )
    {
      if ( (v291[0] & 0x200) != 0 )
      {
        inited = *(_DWORD *)&v268[3];
        v66 = 6652;
        v14 = (unsigned __int8 *)Entry;
        goto LABEL_175;
      }
      Buffer = *(unsigned int *)&v268[3];
      v82 = 0;
      if ( (v270 & 0x40) == 0 && (*(int *)&v268[3] >= 0 || (v81 = v13[1]) == 0 || !*(_QWORD *)(v81 + 56)) )
        v82 = 1;
      if ( *(_DWORD *)&v268[3] == -1073741766 )
      {
        if ( (v270 & 0x20) != 0 && String1.Length )
        {
          if ( !RtlEqualUnicodeString(&String1, *(PCUNICODE_STRING *)(*(_QWORD *)&pFcb->OpenCount + 56LL), 1u) )
            goto LABEL_975;
          Buffer = *(unsigned int *)&v268[3];
        }
      }
      else if ( *(int *)&v268[3] >= 0 && v13[1] )
      {
        if ( v78 == -1073741766 || v78 == -1073741809 || v78 == -1073741772 )
        {
          v83 = v13[1];
          v84 = CscQueryGlobalNewlyCachedEpoch(v80, *(unsigned int *)&v268[3], v9, v79);
          Buffer = *(unsigned int *)&v268[3];
          *(_DWORD *)(v83 + 72) = v84;
        }
        *(_DWORD *)(v13[1] + 24LL) = v78;
      }
      if ( v82 )
      {
        inited = Buffer;
LABEL_230:
        v14 = (unsigned __int8 *)Entry;
        v66 = 6724;
        goto LABEL_175;
      }
LABEL_975:
      inited = v78;
      goto LABEL_230;
    }
    if ( !v267 )
    {
      inited = v78;
LABEL_686:
      v14 = (unsigned __int8 *)Entry;
      goto LABEL_629;
    }
    if ( v7 )
    {
      v14 = (unsigned __int8 *)Entry;
      if ( *((char *)Entry + 529) >= 0 || (*(_DWORD *)(v13[3] + 4LL) & 0x2000) != 0 )
        goto LABEL_628;
      if ( !(unsigned __int8)CscLViewIsRootGhosted(*(_QWORD *)&pFcb->OpenCount) )
      {
        CscTransitionFcbOffline((__int64)pFcb, 1, 2, 2u);
        inited = updated;
        goto LABEL_686;
      }
    }
    v14 = (unsigned __int8 *)Entry;
LABEL_628:
    inited = *(_DWORD *)&v268[3];
LABEL_629:
    v66 = 6647;
    goto LABEL_175;
  }
  if ( ((unsigned __int8)v286 & 1) == 0 && ((unsigned __int8)v286 & 2) == 0 )
  {
    v65 = *(_DWORD *)&v268[7];
    goto LABEL_793;
  }
  LODWORD(v285) = 0;
  v65 = *(_DWORD *)&v268[7];
  v280 = *((_BYTE *)Entry + 528) & 1;
  v212 = 0;
  if ( (v268[7] & 8) != 0 )
    v212 = v284;
  updated = CscUpdateShareInfoForLogicalView(
              (int)RxContext,
              *(_DWORD *)&v268[7] | (*((char *)Entry + 529) >> 7) & 0x800u,
              (int)Entry + 200,
              v291[3],
              (__int64)&v280,
              (PCUNICODE_STRING)&RxContext->TrackerHistory[7].FileName,
              (__int64)&v285,
              v212);
  v78 = updated;
  if ( updated < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        108,
        WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
        (unsigned int)updated);
LABEL_793:
    if ( v78 >= 0 )
      goto LABEL_171;
    goto LABEL_212;
  }
LABEL_171:
  v268[0] = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    WPP_SF_qqq(
      WPP_GLOBAL_Control->AttachedDevice,
      110,
      WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
      v269,
      pFcb,
      MrxSrvOpen);
  CscStoreEntryIsTransparentlyCached(v269, v268);
  BYTE1(v291[0]) = BYTE1(v291[0]) & 0xFD | (2 * (v268[0] & 1));
  if ( (v291[0] & 0x200) == 0 )
  {
    *(_DWORD *)(v13[1] + 4LL) &= ~0x1000000u;
    v14 = (unsigned __int8 *)Entry;
    goto LABEL_278;
  }
  v14 = (unsigned __int8 *)Entry;
  if ( (*((_BYTE *)Entry + 533) & 4) != 0 )
  {
    v66 = 6768;
    inited = -1073741766;
LABEL_175:
    p_EaBuffer = &RxContext->Create.EaBuffer;
    goto LABEL_176;
  }
  *(_DWORD *)(v13[1] + 4LL) |= 0x1000000u;
  v14 = (unsigned __int8 *)Entry;
  if ( (v291[0] & 1) == 0 || (*(_DWORD *)(v13[2] + 24LL) & 1) != 0 || (*((_BYTE *)Entry + 533) & 0x52) != 0 )
  {
    if ( (v291[0] & 0x10) != 0 )
    {
      v213 = RxContext->Create.PipeCompletionMode;
      if ( (unsigned int)v213 > 5 || (v214 = 45, !_bittest(&v214, v213)) )
      {
        if ( (*(_DWORD *)(v13[2] + 24LL) & 1) == 0 && (*((_BYTE *)Entry + 533) & 0x52) == 0 )
        {
          inited = -1073741300;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
          {
            WPP_SF_Dd(
              WPP_GLOBAL_Control->AttachedDevice,
              112,
              WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
              v213,
              -1073741300);
            v14 = (unsigned __int8 *)Entry;
          }
          v66 = 6834;
          goto LABEL_175;
        }
      }
    }
LABEL_278:
    if ( (v270 & 2) != 0 )
    {
      v215 = CscBumpGlobalNewlyCachedEpoch();
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 113, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids, v215);
      v14 = (unsigned __int8 *)Entry;
    }
    if ( (v270 & 0x40) != 0 )
    {
      *(_DWORD *)(v13[1] + 4LL) |= 0x800000u;
      v14 = (unsigned __int8 *)Entry;
      v216 = *((_BYTE *)Entry + 533);
      if ( (v216 & 0x12) == 0 && v216 >= 0 )
      {
        v66 = 6872;
        inited = -1073741766;
        goto LABEL_175;
      }
    }
    updated = 0;
    if ( *(int *)&v268[3] >= 0 && (v291[0] & 0x10) == 0 && (v291[0] & 0x200) == 0 )
    {
      updated = CscFcbForceFlowOpens(RxContext, pFcb, 0);
      v156 = updated;
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
          v156 = updated;
        }
        if ( (unsigned __int8)CscTransitnOKToGoOffline(v156) )
        {
          LOBYTE(v291[0]) |= 0x12u;
          v267 = 1;
        }
        v9 = (unsigned int)updated;
        inited = updated;
        *((_BYTE *)Entry + 532) |= 2u;
        *((_BYTE *)Entry + 535) |= 2u;
        if ( (v291[0] & 0x10) == 0 && (_DWORD)v9 != -1073741638 )
        {
          if ( (unsigned int)(v9 + 1073741790) > 0x18 || (v217 = 17039361, !_bittest(&v217, v9 + 1073741790)) )
          {
            if ( (_DWORD)v9 != -1073741565 )
            {
              v14 = (unsigned __int8 *)Entry;
              v66 = 6925;
              goto LABEL_175;
            }
          }
        }
      }
      v14 = (unsigned __int8 *)Entry;
    }
    if ( v267 && v7 && (v291[0] & 0x200) == 0 )
    {
      if ( !(unsigned __int8)CscLViewIsRootGhosted(*(_QWORD *)&pFcb->OpenCount) )
        CscTransitionFcbOffline((__int64)pFcb, 1, 2, 2u);
      v14 = (unsigned __int8 *)Entry;
    }
    v94 = CscStoreQueryInformationEntryEx((__int64)v269, 0, (__int64)(v14 + 120), (__int64)(v14 + 56), v14 + 536, 0, 0);
    v14 = (unsigned __int8 *)Entry;
    v95 = (unsigned int)v94;
    *(_DWORD *)&v268[7] = v94;
    if ( v94 < 0 )
    {
      inited = v94;
      v66 = 6979;
      goto LABEL_175;
    }
    if ( (v291[0] & 4) != 0 && (*((_BYTE *)Entry + 528) & 0x10) == 0 && (*((_DWORD *)Entry + 30) & 0x20) != 0 )
    {
      HIDWORD(pFcb->SrvOpenList.Flink) |= 0xA000000u;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) == 0 )
      {
        v14 = (unsigned __int8 *)Entry;
      }
      else
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 115, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids);
        v95 = *(unsigned int *)&v268[7];
        v14 = (unsigned __int8 *)Entry;
      }
    }
    if ( (v291[0] & 0x10) != 0 && (v270 & 1) == 0 )
    {
      v96 = *((_DWORD *)v14 + 30);
      if ( (v96 & 0x20) == 0 && (v96 & 0x10) == 0 && RxContext->Create.PipeCompletionMode == 2 )
      {
        *((_QWORD *)&RxContext->9 + 25) = 4;
        v66 = 7016;
        inited = -1073741771;
        goto LABEL_175;
      }
    }
    Buffer = v279;
    if ( (v279 & 0x80000000) != 0 && (v291[0] & 0x10) == 0 )
    {
      v218 = *((_DWORD *)v14 + 30);
      if ( (v218 & 0x400) != 0 || (v218 & 0x80417) != 0 && (*((_DWORD *)v14 + 26) & 0x10) == 0 )
      {
        v9 = v279;
        *(_DWORD *)&v268[7] = v279;
        v66 = 7039;
        goto LABEL_787;
      }
    }
    v97 = (*((_DWORD *)v14 + 26) & 0x10) != 0;
    v14[531] = v97;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    {
      v148 = 89;
      v149 = 89;
      if ( (v270 & 1) == 0 )
        v148 = 78;
      if ( !v97 )
        v149 = 78;
      LOBYTE(v262) = v148;
      WPP_SF_ccDi(
        WPP_GLOBAL_Control->AttachedDevice,
        116,
        WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
        v149,
        v262,
        *((_DWORD *)Entry + 30),
        *((_QWORD *)Entry + 12));
      v95 = *(unsigned int *)&v268[7];
    }
    v14 = (unsigned __int8 *)Entry;
    if ( (*((_DWORD *)Entry + 30) & 0x20000) != 0 )
    {
      if ( (*((_BYTE *)Entry + 534) & 0x10) != 0 )
      {
        LODWORD(MrxSrvOpen->Key) |= 0x1080u;
        v14 = (unsigned __int8 *)Entry;
      }
      if ( (*((_DWORD *)v14 + 30) & 0x20000) != 0 )
      {
        v219 = v13[1];
        v220 = *(_DWORD *)(v219 + 4);
        if ( (v220 & 0x1000) == 0 && (v291[0] & 0x40) != 0 && (v291[0] & 0x10) != 0 && (v14[534] & 0x10) == 0 )
        {
          *(_DWORD *)(v219 + 4) = v220 | 0x1000;
          v14 = (unsigned __int8 *)Entry;
        }
      }
    }
    if ( (*((_DWORD *)v14 + 30) & 0x4000) != 0 )
    {
      *(_DWORD *)(v13[1] + 4LL) |= 0x800u;
      v14 = (unsigned __int8 *)Entry;
    }
    v98 = v14[528];
    Buffer = *(unsigned int *)&v268[3];
    if ( (v98 & 8) == 0 || v267 || *(int *)&v268[3] >= 0 && (v14[535] & 2) == 0 || (v98 & 0x20) == 0 )
      goto LABEL_297;
    v157 = *(_DWORD *)&v268[3];
    if ( (v14[535] & 2) != 0 )
      v157 = updated;
    if ( v157 == -1073741772 )
    {
      if ( (v291[0] & 0x40) != 0 && !v14[531] )
      {
        v281 = 1;
        v158 = CscStoreSetInformationEntry((__int64)v269, 0, 0, 0, 0, &v281, 0);
        v159 = v158;
        *(_DWORD *)&v268[7] = v158;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
        {
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 117, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids, v158);
          v159 = *(_DWORD *)&v268[7];
        }
        v14 = (unsigned __int8 *)Entry;
        if ( v159 >= 0 )
        {
          inited = -1073741772;
LABEL_1057:
          v66 = 7237;
          goto LABEL_175;
        }
      }
      if ( (v291[0] & 0x200) != 0 )
      {
        v274 = 1;
        inited = -1073741772;
        goto LABEL_1057;
      }
      v221 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) == 0 )
        goto LABEL_1038;
      v222 = 118;
      goto LABEL_1037;
    }
    if ( v157 == -1073741790 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 119, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids);
        LODWORD(v14) = (_DWORD)Entry;
      }
      CscStoreSetExplicitAccessEntry((_DWORD)v269, 0, (_DWORD)v14 + 200, 0, 1);
      v14 = (unsigned __int8 *)Entry;
      inited = -1073741790;
      goto LABEL_1057;
    }
    if ( *(_DWORD *)&v268[3] == -1073741766 )
      goto LABEL_1051;
    if ( v157 == -1073741638 )
    {
      if ( !v14[531] )
      {
LABEL_1051:
        if ( (v291[0] & 0x200) == 0 )
        {
          v221 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) == 0 )
          {
            goto LABEL_1038;
          }
          v222 = 120;
LABEL_1037:
          WPP_SF_(v221->AttachedDevice, v222, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids);
LABEL_1038:
          LOBYTE(v291[0]) |= 0x12u;
          CscTransitionFcbOffline((__int64)pFcb, 0, 8, 0);
          v95 = *(unsigned int *)&v268[7];
          Buffer = *(unsigned int *)&v268[3];
          inited = 0;
          v14 = (unsigned __int8 *)Entry;
          goto LABEL_297;
        }
        v274 = 1;
        inited = v157;
      }
    }
    else if ( v157 == -1073741565 && v14[531] )
    {
      goto LABEL_1051;
    }
    if ( inited < 0 )
      goto LABEL_1057;
LABEL_297:
    v99 = v14[528];
    if ( (v99 & 8) != 0 && (int)Buffer >= 0 && (v270 & 1) == 0 )
    {
      v9 = v14[531];
      Buffer = *((_DWORD *)v14 + 12) & 0x10;
      if ( (_BYTE)v9 != ((*((_DWORD *)v14 + 12) & 0x10) != 0) )
      {
        if ( (v99 & 0x20) == 0 )
        {
          v66 = 7346;
          inited = -1073741595;
          goto LABEL_175;
        }
        if ( (v291[0] & 0x40) == 0 )
          goto LABEL_1063;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
        {
          v166 = 89;
          v167 = 89;
          if ( !(_DWORD)Buffer )
            v167 = 78;
          LOBYTE(v262) = v167;
          if ( !(_BYTE)v9 )
            v166 = 78;
          WPP_SF_cc(WPP_GLOBAL_Control->AttachedDevice, 121, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids, v166);
          v14 = (unsigned __int8 *)Entry;
        }
        v168 = CscStoreChangeEntryTypeForCreate(&v269, 0, v14, 0, v262);
        v95 = (unsigned int)v168;
        if ( v168 >= 0 )
        {
          v223 = CscStoreQueryInformationEntryEx(
                   (__int64)v269,
                   0,
                   (__int64)Entry + 120,
                   (__int64)Entry + 56,
                   (_BYTE *)Entry + 536,
                   0,
                   0);
          v95 = (unsigned int)v223;
          if ( v223 < 0 )
          {
            v14 = (unsigned __int8 *)Entry;
            inited = v223;
            v66 = 7295;
            goto LABEL_175;
          }
          *((_BYTE *)Entry + 531) = (*((_DWORD *)Entry + 26) & 0x10) != 0;
          v14 = (unsigned __int8 *)Entry;
          LODWORD(v270) = 1;
        }
        else
        {
          v14 = (unsigned __int8 *)Entry;
          if ( !v269 )
          {
            inited = v168;
            v66 = 7283;
            goto LABEL_175;
          }
        }
        if ( (v291[0] & 0x40) == 0 || (v95 & 0x80000000) != 0LL )
        {
LABEL_1063:
          LOBYTE(v291[0]) |= 0x12u;
          v14[532] |= 2u;
          CscTransitionFcbOffline((__int64)pFcb, 0, 8, 0);
          v224 = Entry;
          *(_OWORD *)Entry = *(_OWORD *)((char *)Entry + 56);
          v224[1] = *(_OWORD *)((char *)v224 + 72);
          v224[2] = *(_OWORD *)((char *)v224 + 88);
          *((_QWORD *)v224 + 6) = *((_QWORD *)v224 + 13);
          *((_BYTE *)Entry + 534) |= 0x20u;
          v14 = (unsigned __int8 *)Entry;
        }
      }
    }
    if ( (v291[0] & 0x10) == 0 )
    {
LABEL_299:
      *((_QWORD *)v14 + 14) = v14 + 136;
      v14 = (unsigned __int8 *)Entry;
      if ( !*((_BYTE *)Entry + 531) && (*(_DWORD *)(v13[2] + 24LL) & 1) != 0 && (*((_BYTE *)Entry + 533) & 4) == 0 )
      {
        v66 = 7554;
        inited = -1073741565;
        goto LABEL_175;
      }
      if ( (v270 & 0x80u) != 0LL )
      {
LABEL_420:
        *((_BYTE *)Entry + 529) |= 2u;
        *((_BYTE *)Entry + 529) |= 0x10u;
        *((_DWORD *)Entry + 84) |= 0x800000u;
        *(_DWORD *)(v13[1] + 4LL) |= 0x1000000u;
        v14 = (unsigned __int8 *)Entry;
        BYTE1(v291[0]) |= 2u;
        if ( (*((_DWORD *)Entry + 30) & 0x4000) != 0 && (v270 & 0x80u) == 0LL )
        {
          *((_BYTE *)Entry + 529) |= 0x40u;
          goto LABEL_806;
        }
        goto LABEL_421;
      }
      if ( (v65 & 0x40000) != 0 && (*((_DWORD *)Entry + 30) & 0x1000000) == 0 )
      {
        if ( v291[3] == 4 )
        {
LABEL_303:
          if ( (*((_DWORD *)Entry + 30) & 0x800000) != 0 )
          {
            *((_BYTE *)Entry + 529) |= 2u;
            *((_BYTE *)Entry + 529) |= 0x10u;
            *((_DWORD *)Entry + 83) |= 0x800000u;
            *(_DWORD *)(v13[1] + 4LL) &= ~0x1000000u;
            BYTE1(v291[0]) &= ~2u;
LABEL_806:
            v14 = (unsigned __int8 *)Entry;
          }
LABEL_421:
          if ( v14[540] )
          {
            v230 = v13[1];
            v231 = *(_DWORD *)(v230 + 4);
            if ( (v231 & 0x1000000) != 0 )
            {
              *(_DWORD *)(v230 + 4) = v231 | 0x2000000;
              v14 = (unsigned __int8 *)Entry;
            }
          }
          v124 = RxContext->Create.PipeCompletionMode;
          if ( v124 > 5 || (v125 = 45, !_bittest(&v125, v124)) || (v270 & 1) != 0 || (v291[0] & 0x10) == 0 )
          {
            v126 = MrxSrvOpen;
            goto LABEL_425;
          }
          Buffer = *((_DWORD *)v14 + 30) & 0x30;
          if ( (*((_DWORD *)v14 + 30) & 0x30) != 0 && (v291[0] & 0x40) == 0 )
          {
            v66 = 7648;
            inited = -1073741108;
            goto LABEL_175;
          }
          if ( v124 != 3 || (_DWORD)Buffer )
          {
            v14[529] |= 8u;
            *((_BYTE *)Entry + 534) |= 0x20u;
            *((_QWORD *)Entry + 12) = 0;
            v232 = Entry;
            if ( !*((_BYTE *)Entry + 531) )
            {
              *((_DWORD *)Entry + 84) |= 1u;
              v232 = Entry;
            }
            v232[84] |= 6u;
            *((_DWORD *)Entry + 83) |= 0x30u;
            *((_BYTE *)Entry + 529) |= 2u;
            v14 = (unsigned __int8 *)Entry;
          }
          if ( (*((_DWORD *)v14 + 30) & 0x20) != 0 )
          {
            v14[532] |= 0x80u;
            v14 = (unsigned __int8 *)Entry;
          }
          if ( (*((_DWORD *)v14 + 30) & 0x30) != 0 )
          {
            v283 = (v14[531] != 0) + 1;
            CscNotifyReportChange(RxContext, v283, 1);
            v14 = (unsigned __int8 *)Entry;
          }
          if ( (*((_DWORD *)v14 + 30) & 0x10010) != 0 )
          {
            v233 = CscStoreCheckAccessToOverwriteFile(v269, v284, v9, v95);
            if ( v233 < 0 )
            {
              v14 = (unsigned __int8 *)Entry;
              inited = v233;
              v66 = 7724;
              goto LABEL_175;
            }
            v126 = MrxSrvOpen;
            LODWORD(MrxSrvOpen[1].Context2) = 2032127;
            *((_BYTE *)Entry + 532) |= 0x20u;
            *((_BYTE *)Entry + 529) |= 0x20u;
            *((_BYTE *)Entry + 534) |= 0x40u;
          }
          else
          {
            v234 = RxContext->Create.PipeCompletionMode;
            v126 = MrxSrvOpen;
            if ( v234 )
            {
              if ( v234 - 4 > 1 )
              {
LABEL_1113:
                v235 = v283;
                if ( !v283 )
                  v235 = 28;
                v283 = v235;
LABEL_425:
                v127 = RxContext->Create.PipeCompletionMode;
                if ( v127 <= 5 )
                {
                  v128 = 53;
                  if ( _bittest(&v128, v127) )
                  {
                    if ( (v291[0] & 0x10) == 0 || (v291[0] & 0x200) == 0 )
                    {
                      v14[529] = v14[529] & 0xFE | ((v291[0] & 0x10) == 0);
                      v14 = (unsigned __int8 *)Entry;
                      if ( !*((_BYTE *)Entry + 531) && (v270 & 1) == 0 )
                      {
                        *((_BYTE *)Entry + 532) |= 0x80u;
                        v14 = (unsigned __int8 *)Entry;
                      }
                    }
                  }
                }
                if ( (v291[0] & 0x40) != 0 && (v14[529] & 8) == 0 && (v291[0] & 0x10) != 0 )
                {
                  *(_OWORD *)v14 = *(_OWORD *)(v14 + 56);
                  *((_OWORD *)v14 + 1) = *(_OWORD *)(v14 + 72);
                  *((_OWORD *)v14 + 2) = *(_OWORD *)(v14 + 88);
                  *((_QWORD *)v14 + 6) = *((_QWORD *)v14 + 13);
                  *((_BYTE *)Entry + 528) |= 2u;
                  v14 = (unsigned __int8 *)Entry;
                }
                if ( (v270 & 1) == 0 )
                {
LABEL_429:
                  v129 = *(_DWORD *)&v268[3];
                  if ( (v291[0] & 0x10) == 0 && *(int *)&v268[3] >= 0 )
                  {
                    if ( ((__int64)v126->Key & 0x200) != 0
                      || (v171 = *(&RxContext->TrackerHistory[3].Flags + 1), (v171 & 2) == 0) && (v171 & 1) == 0 )
                    {
                      *(_DWORD *)(v13[2] + 24LL) |= 0x10000u;
                      v14 = (unsigned __int8 *)Entry;
                    }
                  }
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
                  {
                    v154 = 89;
                    v155 = 89;
                    if ( (*(_DWORD *)(v13[2] + 24LL) & 0x10000) != 0 )
                      v155 = 78;
                    LOBYTE(v264) = v155;
                    if ( ((__int64)v126->Key & 0x200) != 0 )
                      v154 = 78;
                    LOBYTE(String2) = v154;
                    WPP_SF_DDcc(
                      WPP_GLOBAL_Control->AttachedDevice,
                      126,
                      WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
                      RxContext->TrackerHistory[4].AcquireRelease,
                      *(&RxContext->TrackerHistory[3].Flags + 1),
                      String2,
                      v264);
                    v126 = MrxSrvOpen;
                    v129 = *(_DWORD *)&v268[3];
                    v14 = (unsigned __int8 *)Entry;
                  }
                  if ( (v291[0] & 0x10) != 0 )
                    goto LABEL_432;
                  if ( !v14[531] && !v126[1].NodeReferenceCount )
                  {
                    if ( (*(_DWORD *)(v13[2] + 24LL) & 0x10000) == 0
                      && ((__int64)v126->Key & 3) == 0
                      && !RxContext->TrackerHistory[4].AcquireRelease
                      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
                    {
                      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 127, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids);
                      v126 = MrxSrvOpen;
                      v14 = (unsigned __int8 *)Entry;
                    }
                    v129 = *(_DWORD *)&v268[3];
                  }
                  if ( (v291[0] & 0x10) != 0 || v129 < 0 || v14[531] )
                  {
LABEL_432:
                    if ( (v14[532] & 1) == 0 && (*((_DWORD *)v14 + 30) & 0x10) != 0 )
                    {
                      *((_DWORD *)v14 + 83) |= 0x10u;
                      *((_BYTE *)Entry + 529) |= 4u;
                      *((_BYTE *)Entry + 529) |= 2u;
                      *((_BYTE *)Entry + 536) = 0;
                      if ( (v270 & 1) == 0 && (v291[0] & 0x10) != 0 )
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
                        v126 = MrxSrvOpen;
                      }
                      v129 = *(_DWORD *)&v268[3];
                      v14 = (unsigned __int8 *)Entry;
                    }
                    if ( (v291[0] & 0x10) != 0 || v129 < 0 || (v270 & 1) != 0 )
                    {
LABEL_434:
                      v130 = *(_QWORD *)(*((_QWORD *)&RxContext->9 + 18) + 8LL);
                      v131 = *(void **)(v130 + 32);
                      if ( !v131 )
                        v131 = *(void **)(v130 + 48);
                      if ( SeTokenIsAdmin(v131) )
                        *(_DWORD *)(v13[2] + 24LL) |= 0x4000u;
                      v14 = (unsigned __int8 *)Entry;
                      if ( *((char *)Entry + 533) < 0 )
                      {
                        if ( (*(_DWORD *)(v13[2] + 24LL) & 0x4000) == 0 )
                        {
                          v66 = 8277;
                          inited = -1073741790;
                          goto LABEL_175;
                        }
                        v132 = MrxSrvOpen;
                        LODWORD(MrxSrvOpen->Key) |= 0x1080u;
                        *(_DWORD *)(v13[2] + 24LL) |= 0x800u;
                        v14 = (unsigned __int8 *)Entry;
                      }
                      else
                      {
                        v132 = MrxSrvOpen;
                      }
                      v133 = (v291[0] & 0x10) == 0
                          || (v14[533] & 0x80u) != 0
                          || (v14[534] & 0x40) != 0
                          || (v270 & 1) != 0;
                      v134 = v14[533];
                      v135 = (v134 & 0x20) != 0;
                      if ( (v134 & 2) != 0 )
                        v135 |= 2u;
                      if ( v133 || (v14[532] & 0x20) != 0 )
                        p_Context2 = 0;
                      else
                        p_Context2 = (__int64)&v132[1].Context2;
                      v137 = CscSrvOpenOpenObtainStoreHandle(
                               (_DWORD)pFcb,
                               (_DWORD)v132,
                               (_DWORD)v269,
                               v14[531],
                               v135,
                               !v133,
                               v284,
                               p_Context2);
                      *(_DWORD *)&v268[7] = v137;
                      v9 = (unsigned int)v137;
                      if ( v137 < 0 )
                      {
                        if ( v137 != -1073741436 && v137 != -1073741756 || !v7 )
                        {
                          v14 = (unsigned __int8 *)Entry;
                          inited = v137;
                          v66 = 8351;
                          goto LABEL_175;
                        }
                        v14 = (unsigned __int8 *)Entry;
                        inited = 0;
                        v143 = 0;
                        v66 = 8346;
                        goto LABEL_769;
                      }
                      v14 = (unsigned __int8 *)Entry;
                      if ( (*((_BYTE *)Entry + 529) & 0x20) != 0 )
                      {
                        v138 = MrxSrvOpen;
                        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
                        {
                          WPP_SF_Dd(
                            WPP_GLOBAL_Control->AttachedDevice,
                            137,
                            WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
                            LODWORD(MrxSrvOpen[1].Context2),
                            MrxSrvOpen->Key);
                          v14 = (unsigned __int8 *)Entry;
                        }
                        if ( ((__int64)v138->Key & 0x100000) == 0 )
                        {
                          v165 = CscStoreSetExplicitAccessEntry((_DWORD)v269, 0, (int)v14 + 200, v138[1].Context2, 3);
                          v14 = (unsigned __int8 *)Entry;
                          v9 = (unsigned int)v165;
                          *(_DWORD *)&v268[7] = v165;
                          if ( v165 < 0 )
                          {
                            v66 = 8384;
                            goto LABEL_787;
                          }
                        }
                      }
                      else
                      {
                        v138 = MrxSrvOpen;
                      }
                      if ( (*(_DWORD *)(v13[1] + 4LL) & 0x80u) == 0 )
                      {
                        v267 = 0;
                        v139 = CscStoreQueryPinInformationEntry(v269, v14 + 200, v14 + 328, &v267);
                        *(_DWORD *)&v268[7] = v139;
                        if ( v139 < 0 )
                        {
                          v14 = (unsigned __int8 *)Entry;
                          inited = v139;
                          v66 = 8408;
                          goto LABEL_175;
                        }
                        v140 = Entry;
                        v9 = *((unsigned __int8 *)Entry + 328);
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
                          *(_DWORD *)(v13[1] + 4LL) |= 0x80u;
                          v140 = Entry;
                        }
                        v140[533] = v140[533] & 0xFE | v267 & 1;
                        v14 = (unsigned __int8 *)Entry;
                      }
                      Buffer = *(unsigned int *)&v268[3];
                      if ( (v291[0] & 0x10) != 0 || *(int *)&v268[3] < 0 || v14[531] )
                      {
LABEL_458:
                        if ( (v14[532] & 0x80u) != 0
                          || (v14[529] & 2) != 0
                          && (*((_DWORD *)v14 + 30) & 0x20) != 0
                          && (*((_DWORD *)v14 + 83) & 0x20) != 0
                          && (*((_DWORD *)v14 + 84) & 0x20) == 0 )
                        {
                          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
                          {
                            WPP_SF_(
                              WPP_GLOBAL_Control->AttachedDevice,
                              139,
                              WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids);
                          }
                          v244 = CscStoreInvalidateDataEntry(v269, (v291[0] & 0x10) != 0, v9);
                          v14 = (unsigned __int8 *)Entry;
                          v9 = (unsigned int)v244;
                          *(_DWORD *)&v268[7] = v244;
                          if ( v244 < 0 )
                          {
                            v66 = 8485;
                            goto LABEL_787;
                          }
                          Buffer = *(unsigned int *)&v268[3];
                        }
                        if ( (v14[529] & 3) == 0 )
                          goto LABEL_726;
                        memset(v292, 0, sizeof(v292));
                        v277 = CscConvertSmbCacheModeToStoreCacheMode((unsigned int)v291[3]);
                        v141 = v277;
                        v142 = CscStoreQueryInformationEntryEx((__int64)v269, 1, (__int64)v292, 0, 0, 0, 0);
                        *(_DWORD *)&v268[7] = v142;
                        v9 = (unsigned int)v142;
                        if ( v142 < 0 )
                        {
                          v143 = 1;
                          v14 = (unsigned __int8 *)Entry;
                          v66 = 8523;
                          if ( (v291[0] & 0x10) != 0 )
                            inited = v142;
                          goto LABEL_788;
                        }
                        v245 = (char *)Entry;
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
                          v245 = (char *)Entry;
                        }
                        if ( (v245[529] & 1) != 0
                          && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
                        {
                          WPP_SF_(
                            WPP_GLOBAL_Control->AttachedDevice,
                            141,
                            WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids);
                          v245 = (char *)Entry;
                        }
                        v246 = v245[529];
                        v247 = v245 + 536;
                        if ( (v246 & 4) == 0 )
                          v247 = 0;
                        v248 = (__int64)(v245 + 332);
                        v249 = 0;
                        if ( (v246 & 1) != 0 )
                          v249 = (__int64)v245;
                        if ( (v246 & 2) == 0 )
                          v248 = 0;
                        v250 = CscStoreSetInformationEntry((__int64)v269, v248, 0, (__int64)(v245 + 128), v249, v247, 0);
                        v14 = (unsigned __int8 *)Entry;
                        v9 = (unsigned int)v250;
                        *(_DWORD *)&v268[7] = v250;
                        if ( v250 < 0 )
                        {
                          v143 = 1;
                          v66 = 8568;
                          if ( (v291[0] & 0x10) != 0 )
                            inited = v250;
LABEL_788:
                          if ( inited < 0 )
                            goto LABEL_175;
LABEL_768:
                          if ( (v9 & 0x80000000) == 0LL )
                            goto LABEL_175;
LABEL_769:
                          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
                          {
                            WPP_SF_Dd(
                              WPP_GLOBAL_Control->AttachedDevice,
                              150,
                              WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
                              (unsigned int)v9,
                              inited);
                            v9 = *(unsigned int *)&v268[7];
                            v14 = (unsigned __int8 *)Entry;
                          }
                          if ( (v291[0] & 0x10) != 0 )
                          {
                            inited = v9;
                            goto LABEL_175;
                          }
                          if ( v143 && v269 && (*((_DWORD *)v14 + 26) & 0x10) == 0 )
                          {
                            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
                            {
                              WPP_SF_(
                                WPP_GLOBAL_Control->AttachedDevice,
                                151,
                                WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids);
                              v14 = (unsigned __int8 *)Entry;
                            }
                            *((_DWORD *)v14 + 84) = 32;
                            *((_DWORD *)Entry + 83) = 0;
                            if ( (int)CscStoreSetInformationEntry((__int64)v269, (__int64)Entry + 332, 0, 0, 0, 0, 0) < 0 )
                            {
                              if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                              {
LABEL_1288:
                                v255 = CscForceFcbStoreEntryClosed(RxContext, (v291[0] & 0x10) != 0);
                                v14 = (unsigned __int8 *)Entry;
                                if ( v255 >= 0 )
                                {
                                  if ( v269 && (*((_BYTE *)Entry + 532) & 0x10) == 0 )
                                  {
                                    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                                      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
                                    {
                                      WPP_SF_qqq(
                                        WPP_GLOBAL_Control->AttachedDevice,
                                        154,
                                        WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
                                        v269,
                                        pFcb,
                                        MrxSrvOpen);
                                    }
                                    CscStoreDereferenceEntry(&v269);
                                    *((_BYTE *)Entry + 532) |= 0x10u;
                                    v14 = (unsigned __int8 *)Entry;
                                  }
                                  v256 = v13[1];
                                  if ( v256 )
                                  {
                                    *(_DWORD *)(v256 + 24) = *(_DWORD *)&v268[7];
                                    v14 = (unsigned __int8 *)Entry;
                                  }
                                }
                                else
                                {
                                  inited = *(_DWORD *)&v268[7];
                                }
                                goto LABEL_175;
                              }
                              if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
                                WPP_SF_d(
                                  WPP_GLOBAL_Control->AttachedDevice,
                                  152,
                                  WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
                                  v279);
                            }
                            LODWORD(v9) = *(_DWORD *)&v268[7];
                          }
                          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
                          {
                            WPP_SF_d(
                              WPP_GLOBAL_Control->AttachedDevice,
                              153,
                              WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
                              (unsigned int)v9);
                          }
                          goto LABEL_1288;
                        }
                        if ( (*((_BYTE *)Entry + 529) & 1) != 0
                          && (*((_BYTE *)Entry + 528) & 0x20) != 0
                          && (v291[0] & 0x10) == 0
                          && !*((_BYTE *)Entry + 531) )
                        {
                          DatabaseInformation = CscStoreQueryDatabaseInformation((__int64)Entry + 272, 0, 0, 0);
                          v14 = (unsigned __int8 *)Entry;
                          *(_DWORD *)&v268[7] = DatabaseInformation;
                          if ( !DatabaseInformation && (*((_DWORD *)Entry + 68) & 1) == 0 )
                          {
                            if ( (v270 & 1) == 0
                              && (((__int64)pFcb[1].Header.FilterContexts.Flink & 0x4000) != 0) != ((*((_DWORD *)Entry + 30) & 0x80) != 0) )
                            {
                              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
                              {
                                WPP_SF_(
                                  WPP_GLOBAL_Control->AttachedDevice,
                                  142,
                                  WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids);
                              }
                              v190 = CscStoreEncryptDecryptEntry();
                              v14 = (unsigned __int8 *)Entry;
                              *(_DWORD *)&v268[7] = v190;
                            }
                            v141 = v277;
                          }
                        }
                        if ( (v14[529] & 0x10) != 0 )
                        {
                          v191 = CscStoreUpdateShareProperty(v269, v141, v292[2]);
                          v14 = (unsigned __int8 *)Entry;
                          v9 = (unsigned int)v191;
                          *(_DWORD *)&v268[7] = v191;
                          if ( v191 < 0 )
                          {
                            v66 = 8626;
                            goto LABEL_787;
                          }
                        }
                        v252 = v14[529];
                        if ( (v252 & 0x40) != 0 )
                        {
                          v277 = 0;
                          v282 = v14[528] & 1;
                          v253 = 0;
                          if ( (v65 & 8) != 0 )
                            v253 = v284;
                          *(_DWORD *)&v268[7] = CscUpdateShareInfoForLogicalView(
                                                  (int)RxContext,
                                                  v65 | (v252 >> 7) & 0x800u,
                                                  (int)v14 + 200,
                                                  v291[3],
                                                  (__int64)&v282,
                                                  (PCUNICODE_STRING)&RxContext->TrackerHistory[7].FileName,
                                                  (__int64)&v277,
                                                  v253);
                          v9 = *(unsigned int *)&v268[7];
                          if ( *(int *)&v268[7] >= 0
                            || WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) == 0 )
                          {
                            v14 = (unsigned __int8 *)Entry;
                            v138 = MrxSrvOpen;
                            Buffer = *(unsigned int *)&v268[3];
LABEL_726:
                            if ( (v14[529] & 8) == 0 )
                              goto LABEL_727;
                            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
                            {
                              WPP_SF_d(
                                WPP_GLOBAL_Control->AttachedDevice,
                                144,
                                WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
                                *((unsigned int *)v14 + 12));
                              v14 = (unsigned __int8 *)Entry;
                            }
                            *(_OWORD *)(v14 + 408) = *(_OWORD *)v14;
                            *(_OWORD *)(v14 + 424) = *((_OWORD *)v14 + 1);
                            *((_QWORD *)v14 + 55) = *((_QWORD *)v14 + 4);
                            *((_DWORD *)Entry + 110) = *((_DWORD *)Entry + 12);
                            v188 = (char *)Entry;
                            if ( !*((_DWORD *)Entry + 110) )
                            {
                              *((_DWORD *)Entry + 110) = 128;
                              v188 = (char *)Entry;
                            }
                            v189 = CscStoreUpdateLocalBasicInformationEntry(v269, (v291[0] & 0x10) != 0, v188 + 408, 0);
                            v14 = (unsigned __int8 *)Entry;
                            v9 = (unsigned int)v189;
                            *(_DWORD *)&v268[7] = v189;
                            if ( v189 >= 0 )
                            {
                              Buffer = *(unsigned int *)&v268[3];
LABEL_727:
                              if ( (v291[0] & 0x10) == 0 )
                              {
                                if ( (int)Buffer < 0 )
                                {
                                  v66 = 8825;
                                  goto LABEL_175;
                                }
                                goto LABEL_745;
                              }
                              updated = 1;
                              if ( (v291[0] & 0x40) != 0 || (v14[534] & 0x20) != 0 )
                              {
                                *((_DWORD *)v14 + 112) = 1;
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
                                v14 = (unsigned __int8 *)Entry;
                              }
                              if ( !RxContext->pFobx )
                              {
                                NetFobx = RxCreateNetFobx(RxContext, v138);
                                RxContext->pFobx = NetFobx;
                                if ( !NetFobx )
                                {
                                  v14 = (unsigned __int8 *)Entry;
                                  v66 = 8744;
                                  inited = -1073741670;
                                  goto LABEL_175;
                                }
                                *((_BYTE *)Entry + 528) |= 0x80u;
                                v14 = (unsigned __int8 *)Entry;
                              }
                              if ( (v270 & 1) != 0 || (v182 = RxContext->Create.PipeCompletionMode, v182 == 2) )
                              {
                                *((_QWORD *)&RxContext->9 + 25) = 2;
                              }
                              else if ( v182 - 4 <= 1 )
                              {
                                *((_QWORD *)&RxContext->9 + 25) = 3;
                              }
                              else
                              {
                                *((_QWORD *)&RxContext->9 + 25) = v182 != 0;
                              }
                              if ( v14[531] || (*((_DWORD *)&RxContext->9 + 28) & 0x23) == 0 )
                              {
                                LODWORD(v138->Key) |= 0x200u;
                                v183 = &RxContext->TrackerHistory[4];
                                *(_DWORD *)(v13[2] + 24LL) |= 0x10000u;
                                RxContext->TrackerHistory[4].AcquireRelease = 0;
                                if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
                                {
LABEL_744:
                                  v14 = (unsigned __int8 *)Entry;
LABEL_745:
                                  if ( (v14[532] & 1) != 0
                                    || (v14[533] & 0x40) != 0 && (*(_DWORD *)(v13[2] + 24LL) & 1) == 0 )
                                  {
                                    *(_DWORD *)(v13[2] + 24LL) |= 8u;
                                  }
                                  inited = CscCreateAndInitializeFobxContext(RxContext->pFobx, v13, 0, 0);
                                  if ( inited )
                                  {
                                    v14 = (unsigned __int8 *)Entry;
                                    v66 = 8860;
                                    goto LABEL_175;
                                  }
                                  v184 = (char *)Entry;
                                  if ( (*((_BYTE *)Entry + 534) & 4) != 0 && (*((_BYTE *)Entry + 532) & 0x40) != 0 )
                                  {
                                    *(_DWORD *)(*v13 + 4LL) |= 0x40u;
                                    ++*(_DWORD *)(v13[1] + 76LL);
                                    v184 = (char *)Entry;
                                  }
                                  if ( v184[534] < 0 )
                                  {
                                    *(_DWORD *)(*v13 + 4LL) |= 0x200u;
                                    v184 = (char *)Entry;
                                  }
                                  if ( v184[528] >= 0 && (v184[532] & 4) == 0 )
                                  {
                                    *(_DWORD *)(*v13 + 4LL) |= 2u;
                                    *(_QWORD *)(*v13 + 64LL) = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v287 + 48) + 352LL)
                                                                         + 144LL);
                                    v184 = (char *)Entry;
                                  }
                                  if ( (v184[532] & 0x40) != 0 )
                                  {
                                    *(_DWORD *)(*v13 + 4LL) |= 1u;
                                    v184 = (char *)Entry;
                                  }
                                  if ( (v291[0] & 0x200) == 0
                                    || v184[539]
                                    || (*(_DWORD *)(v13[2] + 24LL) & 1) != 0
                                    || (v184[533] & 0x52) != 0
                                    || (v184[528] & 0x40) != 0 )
                                  {
                                    v185 = CscApplyStoreHandleToFcbOrDeref((PMRX_FCB)RxContext, v269);
                                    v187 = (unsigned int)v185;
                                    *(_DWORD *)&v268[7] = v185;
                                    *((_BYTE *)Entry + 532) |= 0x10u;
                                    if ( v185 < 0 )
                                    {
                                      v14 = (unsigned __int8 *)Entry;
                                      inited = v185;
                                      v66 = 8952;
                                      goto LABEL_175;
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
                                        v13[1]);
                                    }
                                    v254 = v13[2];
                                    if ( *(_QWORD *)(v254 + 8) )
                                    {
                                      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                                        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
                                      {
                                        WPP_SF_qqq(
                                          WPP_GLOBAL_Control->AttachedDevice,
                                          148,
                                          WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
                                          v269,
                                          pFcb,
                                          v138);
                                      }
                                      *(_DWORD *)&v268[7] = CscStoreCloseEntryHandle(*(_QWORD *)(v13[2] + 8LL), 0, 0);
                                      *(_QWORD *)(v13[2] + 8LL) = 0;
                                    }
                                    else if ( *(_QWORD *)(v254 + 16) )
                                    {
                                      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                                        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
                                      {
                                        WPP_SF_qqq(
                                          WPP_GLOBAL_Control->AttachedDevice,
                                          149,
                                          WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
                                          v269,
                                          pFcb,
                                          v138);
                                      }
                                      *(_DWORD *)&v268[7] = CscStoreCloseEntryHandle(*(_QWORD *)(v13[2] + 16LL), 0, 0);
                                      *(_QWORD *)(v13[2] + 16LL) = 0;
                                    }
                                    CscStoreDereferenceEntry(&v269);
                                    *((_BYTE *)Entry + 532) |= 0x10u;
                                  }
                                  v66 = 0;
                                  *(_DWORD *)(v13[1] + 72LL) = CscQueryGlobalNewlyCachedEpoch(v187, Buffer, v9, v186);
                                  v269 = 0;
                                  if ( (*(_DWORD *)(v13[2] + 24LL) & 1) != 0 )
                                    ++*(_DWORD *)(v13[1] + 20LL);
                                  v9 = *(unsigned int *)&v268[7];
                                  if ( (*(_DWORD *)(v13[2] + 24LL) & 8) != 0 )
                                    *(_DWORD *)(v13[1] + 4LL) |= 0x20u;
                                  v14 = (unsigned __int8 *)Entry;
                                  v143 = 0;
                                  goto LABEL_768;
                                }
                                if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
                                  WPP_SF_q(
                                    WPP_GLOBAL_Control->AttachedDevice,
                                    145,
                                    WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
                                    v138);
                              }
                              else
                              {
                                v183 = &RxContext->TrackerHistory[4];
                                v138->SrvOpenQLinks.Flink = (struct _LIST_ENTRY *)v138;
                                v138->SrvOpenQLinks.Blink = 0;
                                RxContext->TrackerHistory[4].AcquireRelease = 15;
                              }
                              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
                              {
                                WPP_SF_Dq(
                                  WPP_GLOBAL_Control->AttachedDevice,
                                  146,
                                  WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
                                  v183->AcquireRelease,
                                  v138);
                              }
                              goto LABEL_744;
                            }
                            v66 = 8684;
LABEL_787:
                            v143 = 0;
                            goto LABEL_788;
                          }
                          WPP_SF_d(
                            WPP_GLOBAL_Control->AttachedDevice,
                            143,
                            WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
                            *(unsigned int *)&v268[7]);
                          v14 = (unsigned __int8 *)Entry;
                        }
                        Buffer = *(unsigned int *)&v268[3];
                        v138 = MrxSrvOpen;
                        goto LABEL_726;
                      }
                      v174 = v13[1];
                      v175 = *(_DWORD *)(v174 + 4);
                      if ( (v175 & 0x1040080) == 0 && ((LOWORD(v291[3]) - 4) & 0xFFFFFFFB) != 0 )
                      {
                        if ( (v14[533] & 1) != 0 && *((_QWORD *)&RxContext->9 + 25) == 2 )
                        {
                          *(_DWORD *)(v174 + 4) = v175 | 0x40000;
                        }
                        else
                        {
                          if ( (*((_DWORD *)v14 + 30) & 0x20) != 0
                            && ((v14[529] & 2) == 0 || (*((_DWORD *)v14 + 83) & 0x20) == 0) )
                          {
                            goto LABEL_1206;
                          }
                          *((_DWORD *)v14 + 84) |= 0x20u;
                          *((_DWORD *)Entry + 83) &= ~0x20u;
                          *((_BYTE *)Entry + 529) |= 2u;
                        }
                        v14 = (unsigned __int8 *)Entry;
                      }
LABEL_1206:
                      Buffer = *(unsigned int *)&v268[3];
                      goto LABEL_458;
                    }
                    if ( v14[531] )
                    {
                      if ( (*((_DWORD *)v14 + 30) & 0x40400) != 0 )
                        goto LABEL_494;
                      v14[529] |= 1u;
                      *((_BYTE *)Entry + 529) |= 8u;
                    }
                    else
                    {
                      v236 = v13[1];
                      if ( (*(_DWORD *)(v236 + 8) != 1
                         && (*(_DWORD *)(v236 + 8) <= 1u
                          || (v277 & 0x40000) != 0
                          || (*((_DWORD *)&RxContext->9 + 28) & 0xFFEFFF7F) == 0)
                         || *(_DWORD *)(v236 + 28))
                        && ((Blink_high = HIDWORD(pFcb->SrvOpenList.Blink), (Blink_high & 2) != 0)
                         || (Blink_high & 1) != 0)
                        || (v238 = *((_QWORD *)v14 + 14),
                            v9 = *((_QWORD *)v14 + 5),
                            v239 = *(_QWORD *)(v238 + 40),
                            v95 = v238 + 16,
                            v239 == v9)
                        && *(_QWORD *)v95 == *((_QWORD *)v14 + 2) )
                      {
LABEL_494:
                        if ( (v291[0] & 0x10) != 0 )
                        {
                          v14[529] &= ~0x20u;
                          *((_BYTE *)Entry + 529) &= ~1u;
                        }
                        else
                        {
                          if ( (*((_DWORD *)v14 + 30) & 0x40000) == 0
                            || (v164 = *((_QWORD *)v14 + 14), !*(_QWORD *)v164)
                            || *(_QWORD *)(v164 + 24) != *((_QWORD *)v14 + 3)
                            || *(_DWORD *)(v164 + 48) != *((_DWORD *)v14 + 12) )
                          {
                            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
                            {
                              WPP_SF_qq(
                                WPP_GLOBAL_Control->AttachedDevice,
                                133,
                                WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
                                *((_QWORD *)v14 + 10),
                                *((_QWORD *)v14 + 3));
                              v14 = (unsigned __int8 *)Entry;
                            }
                            v14[529] |= 0x20u;
                            v242 = (char *)Entry;
                            if ( *((_BYTE *)Entry + 531) && (*((_DWORD *)Entry + 30) & 6) != 0 )
                            {
                              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
                              {
                                WPP_SF_(
                                  WPP_GLOBAL_Control->AttachedDevice,
                                  134,
                                  WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids);
                                v242 = (char *)Entry;
                              }
                              RxSetBasicInfoInFcb(pFcb, v242 + 56, v9, v95);
                              v243 = Entry;
                              *(_OWORD *)Entry = *(_OWORD *)((char *)Entry + 56);
                              v243[1] = *(_OWORD *)((char *)v243 + 72);
                              v243[2] = *(_OWORD *)((char *)v243 + 88);
                              *((_QWORD *)v243 + 6) = *((_QWORD *)v243 + 13);
                              *((_BYTE *)Entry + 529) &= ~1u;
                              *((_BYTE *)Entry + 529) &= ~8u;
                            }
                            else
                            {
                              *((_BYTE *)Entry + 529) |= 1u;
                              *((_BYTE *)Entry + 529) |= 8u;
                            }
                            v14 = (unsigned __int8 *)Entry;
                          }
                          if ( (v14[529] & 1) != 0
                            && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
                          {
                            WPP_SF_qq(
                              WPP_GLOBAL_Control->AttachedDevice,
                              135,
                              WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
                              *((_QWORD *)v14 + 7),
                              *(_QWORD *)v14);
                          }
                          if ( (*(_DWORD *)(v13[2] + 24LL) & 0x40) == 0 )
                          {
                            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
                            {
                              WPP_SF_(
                                WPP_GLOBAL_Control->AttachedDevice,
                                136,
                                WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids);
                            }
                            *(_DWORD *)(v13[2] + 24LL) |= 0x40u;
                            *((_BYTE *)Entry + 529) |= 0x20u;
                          }
                        }
                        goto LABEL_434;
                      }
                      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
                      {
                        WPP_SF_iiii(
                          WPP_GLOBAL_Control->AttachedDevice,
                          131,
                          WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
                          *(_QWORD *)v95,
                          *((_QWORD *)v14 + 2),
                          v239,
                          *((_QWORD *)v14 + 5));
                        v126 = MrxSrvOpen;
                        v14 = (unsigned __int8 *)Entry;
                      }
                      if ( !*((_QWORD *)v14 + 5)
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
                          v14 = (unsigned __int8 *)Entry;
                        }
                        v14[532] |= 0x80u;
                        *((_DWORD *)Entry + 83) |= 0x20u;
                        *((_DWORD *)Entry + 84) &= ~0x20u;
                        *((_BYTE *)Entry + 529) |= 2u;
                      }
                      else if ( (*((_DWORD *)v14 + 30) & 0x20) != 0
                             || (*((_DWORD *)v14 + 84) & 0x20) != 0
                             || (v278 & 0x2000) != 0
                             || (v241 = CscOKToMarkSparseOnOplockBreak(*(_QWORD *)&v126->DesiredAccess, v13[1]),
                                 v14 = (unsigned __int8 *)Entry,
                                 v241)
                             || (*((_DWORD *)Entry + 30) & 0x800000) != 0
                             || (*((_DWORD *)Entry + 84) & 0x800000) != 0 )
                      {
                        *((_DWORD *)v14 + 84) |= 0x20u;
                        *((_DWORD *)Entry + 83) &= ~0x20u;
                        *((_BYTE *)Entry + 529) |= 2u;
                      }
                      else
                      {
                        CscCreatepChangeStateToAvoidMarkingFileSparse(RxContext, v291, Entry, v13);
                      }
                    }
                    v14 = (unsigned __int8 *)Entry;
                    goto LABEL_494;
                  }
                  if ( (*(_DWORD *)(v13[2] + 24LL) & 0x10000) == 0 )
                  {
                    v169 = RxContext->TrackerHistory[4].AcquireRelease;
                    if ( (v169 & 2) == 0 && (v169 & 1) == 0 )
                    {
                      if ( (*((_DWORD *)v14 + 30) & 0x20) == 0 )
                      {
                        v170 = CscOKToMarkSparseOnOplockBreak(*(_QWORD *)&v126->DesiredAccess, v13[1]);
                        v14 = (unsigned __int8 *)Entry;
                        if ( !v170 && (*((_DWORD *)Entry + 30) & 0x800000) == 0 )
                        {
                          CscCreatepChangeStateToAvoidMarkingFileSparse(RxContext, v291, Entry, v13);
                          v126 = MrxSrvOpen;
                          *((_BYTE *)Entry + 529) &= ~1u;
LABEL_1149:
                          v14 = (unsigned __int8 *)Entry;
                          goto LABEL_1150;
                        }
                        v126 = MrxSrvOpen;
                      }
                      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
                      {
                        WPP_SF_(
                          WPP_GLOBAL_Control->AttachedDevice,
                          129,
                          WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids);
                        v126 = MrxSrvOpen;
                        v14 = (unsigned __int8 *)Entry;
                      }
                      *((_DWORD *)v14 + 84) |= 0x20u;
                      *((_DWORD *)Entry + 83) &= ~0x20u;
LABEL_1148:
                      *((_BYTE *)Entry + 529) |= 2u;
                      goto LABEL_1149;
                    }
                    if ( !*((_QWORD *)v14 + 5) )
                    {
                      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
                      {
                        WPP_SF_(
                          WPP_GLOBAL_Control->AttachedDevice,
                          128,
                          WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids);
                        v126 = MrxSrvOpen;
                        v14 = (unsigned __int8 *)Entry;
                      }
                      *((_DWORD *)v14 + 83) |= 0x20u;
                      *((_DWORD *)Entry + 84) &= ~0x20u;
                      goto LABEL_1148;
                    }
                  }
LABEL_1150:
                  v129 = *(_DWORD *)&v268[3];
                  goto LABEL_432;
                }
                if ( (v291[0] & 0x10) != 0 || v14[531] )
                {
                  *((_DWORD *)v14 + 83) |= 0x20u;
                  v14 = (unsigned __int8 *)Entry;
                }
                if ( (v291[0] & 0x10) != 0 )
                {
                  *((_DWORD *)v14 + 84) |= 0x400u;
                  LODWORD(v126[1].Context2) = 2032127;
                  *((_BYTE *)Entry + 532) |= 0x20u;
                  v283 = (*((_BYTE *)Entry + 531) != 0) + 1;
                  CscNotifyReportChange(RxContext, v283, 1);
                  v126 = MrxSrvOpen;
                }
                else
                {
                  if ( *((_QWORD *)v14 + 5) || v14[531] )
                    goto LABEL_1129;
                  *((_DWORD *)v14 + 83) |= 0x20u;
                }
                v14 = (unsigned __int8 *)Entry;
LABEL_1129:
                v14[529] |= 2u;
                *((_BYTE *)Entry + 529) |= 0x20u;
                v14 = (unsigned __int8 *)Entry;
                goto LABEL_429;
              }
              *((_DWORD *)v14 + 100) |= ~(unsigned __int16)*(_DWORD *)&MrxSrvOpen[1].NodeTypeCode & 0x112;
              *(_DWORD *)&v126[1].NodeTypeCode |= 0x112u;
            }
            else
            {
              *((_DWORD *)v14 + 100) |= ~*(_DWORD *)&MrxSrvOpen[1].NodeTypeCode & 0x10000;
              *(_DWORD *)&v126[1].NodeTypeCode |= 0x10000u;
            }
          }
          v14 = (unsigned __int8 *)Entry;
          goto LABEL_1113;
        }
        if ( v291[3] != 8 && !*((_BYTE *)Entry + 193) && !*((_BYTE *)Entry + 192) )
          goto LABEL_420;
      }
      if ( ((v291[3] - 4) & 0xFFFFFFFB) != 0 )
        goto LABEL_421;
      goto LABEL_303;
    }
    v144 = CscCheckNetInfoFromRxContext(RxContext, v14 + 56, (unsigned int)v270, v95);
    if ( v144 >= 0 )
    {
LABEL_466:
      v14 = (unsigned __int8 *)Entry;
      v145 = *((_DWORD *)Entry + 30);
      if ( ((v145 & 0x20) != 0 || (v145 & 0x10) != 0)
        && ((v176 = RxContext->Create.PipeCompletionMode, v176 > 5)
         || (Buffer = 45, !_bittest((const int *)&Buffer, v176))) )
      {
        if ( (*((_BYTE *)Entry + 533) & 0x10) == 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 124, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids);
            v14 = (unsigned __int8 *)Entry;
          }
          *((_QWORD *)&RxContext->9 + 25) = 5;
          v66 = 7462;
          inited = -1073741209;
          goto LABEL_175;
        }
        *((_BYTE *)Entry + 532) |= 1u;
        v14 = (unsigned __int8 *)Entry;
      }
      else
      {
        if ( !*((_BYTE *)Entry + 531) )
        {
LABEL_469:
          v146 = v14[533];
          if ( (v146 & 4) == 0 )
          {
            Buffer = v14[532];
            if ( (Buffer & 1) != 0 || (v146 & 0x40) != 0 && (*(_DWORD *)(v13[2] + 24LL) & 1) == 0 )
            {
              v14[532] = Buffer | 8;
              v147 = _CscObtainFcbMostlyExclusive(RxContext, 0);
              v14 = (unsigned __int8 *)Entry;
              if ( !v147 )
              {
                if ( (*((_BYTE *)Entry + 533) & 0x40) == 0 || (v291[0] & 0x10) != 0 )
                {
                  inited = -1073741757;
                }
                else if ( (v291[0] & 0x20) != 0 && (*((_DWORD *)Entry + 30) & 0x20) != 0 )
                {
                  inited = -1073741641;
                }
                else
                {
                  inited = -1073741640;
                }
                v66 = 7535;
                goto LABEL_175;
              }
            }
          }
          goto LABEL_299;
        }
        if ( (v145 & 0x10000) != 0 && (*((_BYTE *)Entry + 533) & 0x12) == 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 125, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids);
            v14 = (unsigned __int8 *)Entry;
          }
          *((_QWORD *)&RxContext->9 + 25) = 5;
          v66 = 7483;
          inited = -1073741209;
          goto LABEL_175;
        }
      }
      if ( v14[531] )
        goto LABEL_299;
      goto LABEL_469;
    }
    v14 = (unsigned __int8 *)Entry;
    v225 = *((_DWORD *)Entry + 30);
    if ( ((v225 & 0x20) != 0 || (v225 & 0x10) != 0) && (v291[0] & 0x40) != 0 )
    {
      v226 = RxContext->Create.PipeCompletionMode;
      if ( v226 <= 5 )
      {
        Buffer = 45;
        if ( _bittest((const int *)&Buffer, v226) )
        {
          if ( (*((_BYTE *)Entry + 528) & 4) != 0 )
          {
            if ( v144 == -1073741565 )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
              {
                v227 = "sparse";
                if ( (*((_DWORD *)Entry + 30) & 0x20) == 0 )
                  v227 = "dirty deleted";
                WPP_SF_s(WPP_GLOBAL_Control->AttachedDevice, 122, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids, v227);
                v14 = (unsigned __int8 *)Entry;
              }
              LOBYTE(Buffer) = 1;
              v228 = CscStoreChangeEntryTypeForCreate(&v269, Buffer, v14, v284, v262);
              if ( v228 < 0 )
              {
                v14 = (unsigned __int8 *)Entry;
                inited = v228;
                v66 = 7394;
                goto LABEL_175;
              }
              *((_BYTE *)Entry + 534) |= 0x40u;
              v229 = CscStoreQueryInformationEntryEx(
                       (__int64)v269,
                       0,
                       (__int64)Entry + 120,
                       (__int64)Entry + 56,
                       (_BYTE *)Entry + 536,
                       0,
                       0);
              if ( v229 < 0 )
              {
                v14 = (unsigned __int8 *)Entry;
                inited = v229;
                v66 = 7410;
                goto LABEL_175;
              }
              *((_BYTE *)Entry + 531) = 1;
              LODWORD(v270) = 1;
              goto LABEL_466;
            }
            if ( v144 == -1073741638 )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
              {
                WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 123, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids);
                v14 = (unsigned __int8 *)Entry;
              }
              v144 = -1073741108;
            }
          }
        }
      }
    }
    inited = v144;
    v66 = 7438;
    goto LABEL_175;
  }
  v103 = v7 == 0;
  p_EaBuffer = &RxContext->Create.EaBuffer;
  if ( v103 )
    inited = *((_DWORD *)RxContext->Create.UserName.Buffer + 4);
  else
    inited = -1073741300;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      111,
      WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
      (unsigned int)inited);
  CscStoreDereferenceEntry(&v269);
  v66 = 6811;
  *((_BYTE *)Entry + 532) |= 0x10u;
  v14 = (unsigned __int8 *)Entry;
  v269 = 0;
LABEL_176:
  v68 = *((_DWORD *)v14 + 100);
  v69 = MrxSrvOpen;
  *(_DWORD *)&MrxSrvOpen[1].NodeTypeCode &= ~v68;
  v70 = *(_QWORD *)&pFcb->OpenCount;
  if ( v70 )
    CscFlushLViewWasPreviouslyOffline(v70);
  if ( v274 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
      WPP_SF_qqqD(
        WPP_GLOBAL_Control->AttachedDevice,
        155,
        WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
        v269,
        pFcb,
        v69,
        inited);
    LOBYTE(Buffer) = 1;
    v258 = CscStoreSetPurgeEntry(v269, Buffer);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 156, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids, v258);
    if ( v258 == -1073741567 )
      CscEnDeleteTransparentlyCachedDir(v269);
    CscStoreDereferenceEntry(&v269);
    v69 = MrxSrvOpen;
    *((_BYTE *)Entry + 532) |= 0x10u;
    v71 = 0;
    v269 = 0;
  }
  else
  {
    v71 = v269;
  }
  if ( v283 && (v283 & 3) == 0 )
  {
    CscNotifyReportChange(RxContext, v283, 3);
    v71 = v269;
  }
  if ( inited >= 0 )
  {
    if ( (*((_BYTE *)Entry + 532) & 2) == 0 )
      goto LABEL_183;
    goto LABEL_706;
  }
  if ( v71 )
  {
    v177 = v13[2];
    if ( !v177 )
      goto LABEL_703;
    if ( *(_QWORD *)(v177 + 8) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
        WPP_SF_qqq(
          WPP_GLOBAL_Control->AttachedDevice,
          157,
          WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
          v71,
          pFcb,
          v69);
      CscStoreCloseEntryHandle(*(_QWORD *)(v13[2] + 8LL), 0, 0);
      *(_QWORD *)(v13[2] + 8LL) = 0;
    }
    else
    {
      if ( !*(_QWORD *)(v177 + 16) )
        goto LABEL_703;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
        WPP_SF_qqq(
          WPP_GLOBAL_Control->AttachedDevice,
          158,
          WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
          v71,
          pFcb,
          v69);
      CscStoreCloseEntryHandle(*(_QWORD *)(v13[2] + 16LL), 0, 0);
      *(_QWORD *)(v13[2] + 16LL) = 0;
    }
    v71 = v269;
LABEL_703:
    if ( (*((_BYTE *)Entry + 532) & 0x10) == 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
        WPP_SF_qqq(
          WPP_GLOBAL_Control->AttachedDevice,
          159,
          WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
          v71,
          pFcb,
          v69);
      CscStoreDereferenceEntry(&v269);
      *((_BYTE *)Entry + 532) |= 0x10u;
    }
  }
LABEL_706:
  v178 = Entry;
  if ( (*((_BYTE *)Entry + 528) & 8) != 0 && *(int *)&v268[3] >= 0 )
  {
    v9 = *((unsigned __int8 *)Entry + 532);
    if ( (v9 & 4) == 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          160,
          WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
          ((unsigned int)v9 >> 1) & 1);
      v180 = RxContext->NonPagedFcb->AdvancedFcbHeaderMutex.Event.Header.WaitListHead.Blink[6].Blink;
      if ( v180 )
        ((void (__fastcall *)(PRX_CONTEXT, PVOID, unsigned __int64, struct _LIST_ENTRY *))v180)(
          RxContext,
          v178,
          v9,
          v71);
      if ( *v13 )
      {
        if ( inited >= 0 )
        {
          *(_DWORD *)(*v13 + 4LL) &= ~1u;
        }
        else
        {
          CscInternalDeallocateForFobx(RxContext->pFobx, v178, v9, v71);
          *v13 = 0;
        }
      }
      Flink = RxContext->NonPagedFcb->AdvancedFcbHeaderMutex.Event.Header.WaitListHead.Blink[7].Flink;
      if ( Flink )
        ((void (__fastcall *)(PRX_CONTEXT, PVOID, unsigned __int64, struct _LIST_ENTRY *))Flink)(
          RxContext,
          v178,
          v9,
          v71);
      *(_DWORD *)(v13[2] + 24LL) &= ~2u;
      CscUpdateRdrOpenCount(v13[1], v69, 0xFFFFFFFFLL, v71);
      *((_BYTE *)Entry + 532) &= ~0x40u;
    }
  }
  if ( inited < 0 )
  {
    CscCleanupFcbContextFlags(pFcb, v178, v9, v71);
    v179 = v13[1];
    if ( v179
      && (*(_DWORD *)(v179 + 4) & 0x1166F) != 0
      && !*(_QWORD *)(v179 + 56)
      && LODWORD(pFcb[1].Header.PagingIoResource) )
    {
      _InterlockedOr8((volatile signed __int8 *)&pFcb[1].Header.FileContextSupportPointer, 2u);
    }
    goto LABEL_189;
  }
LABEL_183:
  if ( v13[2] )
  {
    v72 = v13[1];
    if ( v72 )
    {
      if ( (*((_DWORD *)&RxContext->9 + 28) & 0xFFEFFF7F) != 0 )
      {
        ++*(_DWORD *)(v72 + 16);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
        {
          WPP_SF_qDD(
            WPP_GLOBAL_Control->AttachedDevice,
            161,
            WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
            pFcb,
            *(_DWORD *)(v13[1] + 16LL) - 1,
            *(_DWORD *)(v13[1] + 16LL));
        }
      }
      if ( (*((_BYTE *)Entry + 532) & 8) != 0 )
        _CscObtainFcbMostlyExclusive(RxContext, 1);
      if ( (*((_BYTE *)Entry + 534) & 2) != 0 && *v13 )
        *(_DWORD *)(*v13 + 4LL) |= 8u;
    }
  }
LABEL_189:
  if ( (v278 & 0x4002C) != 0 && inited == -1073741766 )
  {
    inited = -1073741605;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
      WPP_SF_Dd(
        WPP_GLOBAL_Control->AttachedDevice,
        162,
        WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
        3221225530LL,
        -1073741605);
  }
  if ( v276 )
  {
    *((_DWORD *)p_EaBuffer + 6) = v288;
    if ( inited == -1073741772 || inited == -1073741209 || inited == -1073739772 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 )
        WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 163, WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids, p_FileName);
      v260 = CscDclNotifyExcludedFileType(0, p_FileName, 0);
      if ( v260 < 0
        && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          164,
          WPP_ca0a7eae54f23d5230966a35b6deed8b_Traceguids,
          (unsigned int)v260);
      }
      inited = -1073739772;
    }
  }
  if ( Entry )
  {
    ExFreeToPagedLookasideList((PPAGED_LOOKASIDE_LIST)(CscDevExtn + 128), Entry);
    Entry = 0;
  }
LABEL_193:
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
