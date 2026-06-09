# Jot::CNativeReplicator_InboundReplication::OnPoll(uint *)

- ea: `0x180206900`
- end: `0x180209cf8`
- name: `?OnPoll@CNativeReplicator_InboundReplication@Jot@@MEAAXPEAI@Z`
- size: `13304`
- prototype: `void __fastcall(Jot::CNativeReplicator_InboundReplication *__hidden this, unsigned int *)`
- caller_count: `0`
- callee_count: `142`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callees

- `0x18002efb0`
- `0x18002fdcc`
- `0x180030ef0`
- `0x180032260`
- `0x18004f8cc`
- `0x180054864`
- `0x18005ac04`
- `0x18005fdcc`
- `0x180062a34`
- `0x18006bb90`
- `0x18006f0e0`
- `0x180071c90`
- `0x18007293c`
- `0x180073ca0`
- `0x180074020`
- `0x18007685c`
- `0x180078d30`
- `0x18007b2e4`
- `0x18007c280`
- `0x18007c4e0`
- `0x18007cad0`
- `0x18007cdf0`
- `0x18007d0a0`
- `0x18007d478`
- `0x18007d75c`
- `0x18007d810`
- `0x1800806c4`
- `0x180090cb0`
- `0x180092a8c`
- `0x180092ac4`
- `0x1800933c0`
- `0x18009342c`
- `0x1800982ed`
- `0x180098690`
- `0x18009cd7c`
- `0x18009dcf0`
- `0x18009dec0`
- `0x1800aeef0`
- `0x1800af7bc`
- `0x1800afb94`
- `0x1800b051c`
- `0x1800b0a50`
- `0x1800b0d70`
- `0x1800b50d0`
- `0x1800c4978`
- `0x1800c49e0`
- `0x1800c5b10`
- `0x1800c5d60`
- `0x1800c6068`
- `0x1800c60c0`

## import_xrefs

- `MSVCP140!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x180209572`
- `MSVCP140!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x180209572`
- `MSVCP140!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x1802081b8`
- `MSVCP140!?__ExceptionPtrToBool@@YA_NPEBX@Z` at `0x1802081b8`
- `MSVCP140!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1802076bc`
- `MSVCP140!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1802094ca`
- `MSVCP140!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1802076bc`
- `MSVCP140!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1802094ca`
- `MSVCP140!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1802096d7`
- `MSVCP140!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1802096d7`
- `MSVCP140!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18020820d`
- `MSVCP140!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180208b34`
- `MSVCP140!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1802096b5`
- `MSVCP140!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x18020820d`
- `MSVCP140!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x180208b34`
- `MSVCP140!?__ExceptionPtrCopy@@YAXPEAXPEBX@Z` at `0x1802096b5`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1802095a3`
- `Mso20Win32Client!__imp_MsoShipAssertTagProc` at `0x1802095a3`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18020878a`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180208cc8`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18020878a`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180208cc8`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180207587`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x180207587`

## pseudocode

```c
void __fastcall Jot::CNativeReplicator_InboundReplication::OnPoll(Jot::RevisionTimeLogger **this, unsigned int *a2)
{
  unsigned int *v2; // rsi
  Jot::RevisionTimeLogger *v4; // r14
  struct Jot::CNetworkStatus *OneNoteDotComNetworkStatusInstance; // rax
  Jot *v6; // rcx
  void (__fastcall ***v7)(_QWORD, GUID *, struct Jot::IGraphNode **); // rax
  unsigned int v8; // eax
  unsigned int v9; // eax
  void (__fastcall ***v10)(_QWORD, GUID *, struct Jot::IGraphNode **); // rax
  struct Jot::IGraphNode *v11; // rcx
  __int64 v12; // rax
  unsigned int v13; // eax
  unsigned int v14; // eax
  unsigned int v15; // eax
  unsigned int v16; // eax
  __int64 v17; // rax
  __int64 BackingRevisionStore; // rax
  unsigned int v19; // eax
  unsigned int v20; // eax
  _QWORD *v21; // rbx
  Jot::RevisionTimeLogger *v22; // rcx
  unsigned int v23; // eax
  unsigned int v24; // eax
  unsigned int v25; // eax
  unsigned int v26; // eax
  Jot::RevisionTimeLogger *v27; // rcx
  __int64 v28; // rax
  struct Jot::IGraphSpaceNode *v29; // rdx
  __int64 v30; // r8
  Jot::StaticContextReplication *v31; // rax
  char v32; // bl
  char v33; // di
  __int64 v34; // rax
  __int64 v35; // rax
  __int64 v36; // rax
  Jot::StaticContextReplication *v37; // rax
  struct Jot::IGraphNode *v38; // rcx
  char v39; // bl
  __m128i si128; // xmm9
  const wchar_t *v41; // xmm8_8
  __m128i *v42; // rax
  __m128i v43; // xmm6
  __m128i v44; // xmm7
  const wchar_t *v45; // rdx
  const wchar_t *v46; // r9
  bool v47; // bl
  void (__fastcall *v48)(Jot::RevisionTimeLogger **, __int64); // rbx
  __int64 v49; // rax
  unsigned int v50; // eax
  unsigned int v51; // eax
  unsigned int v52; // r9d
  __int64 v53; // rax
  unsigned int v54; // edx
  MsoCF *v55; // rcx
  struct Jot::IGraphNode *v56; // rbx
  const struct MsoCF::PropertyInfo *v57; // rax
  unsigned int v58; // edx
  struct Jot::IGraphNode *v59; // rbx
  const struct MsoCF::PropertyInfo *v60; // rdi
  __int64 v61; // r9
  char v62; // al
  unsigned __int64 v63; // r9
  _DWORD *v64; // rax
  __int64 v65; // rax
  __int64 v66; // rdx
  __int64 v67; // r8
  __int64 v68; // rax
  _DWORD *v69; // rax
  Jot::StaticContextReplication *v70; // rcx
  __int64 (*v71)(void); // rax
  Jot::StaticContextReplication *v72; // rdi
  __int64 v73; // rax
  Jot::StaticContextReplication *v74; // rbx
  __int64 v75; // rax
  _QWORD *v76; // rax
  _QWORD *v77; // rsi
  void *const *TailAddr; // rax
  __int64 *v79; // rsi
  void *v80; // rax
  void *v81; // rdx
  __int64 v82; // rax
  __int64 v83; // rax
  __int64 v84; // rax
  __int64 v85; // rdx
  __int64 v86; // r8
  struct Jot::IGraphNode *v87; // rax
  struct Jot::IGraphNode *v88; // rcx
  void (__fastcall *v89)(struct Jot::IGraphNode *, GUID *, Jot::StaticContextReplication **); // rax
  void (__fastcall *v90)(struct Jot::IGraphNode *, GUID *, Jot **); // rax
  unsigned int v91; // edx
  bool v92; // r8
  unsigned int v93; // eax
  void *v94; // rdx
  int v95; // eax
  struct Jot::IGraphNode *v96; // rbx
  bool (*v97)(MsoCF::CPropertySet *__hidden, const struct MsoCF::PropertyInfo *, void *); // r9
  char v98; // al
  unsigned int v99; // edx
  Jot *v100; // rax
  void (__fastcall *v101)(Jot::RevisionTimeLogger **, __m128i *); // rbx
  Jot::StaticContextReplication *v102; // rsi
  Jot::StaticContextReplication *v103; // rcx
  void (__fastcall *v104)(Jot::RevisionTimeLogger **, __m128i *); // rbx
  __int64 v105; // rax
  __m128i *v106; // rdx
  Jot::StaticContextReplication *v107; // rcx
  bool (*v108)(MsoCF::CPropertySet *__hidden, const struct MsoCF::PropertyInfo *, void *); // r9
  char v109; // al
  int v110; // ecx
  __int32 v111; // edx
  Jot::RevisionTimeLogger *v112; // r8
  struct Jot::IServerRevisionStore *v113; // rdi
  __int64 (__fastcall *v114)(struct Jot::IServerRevisionStore *, Jot::StaticContextReplication **, __int64, __int64); // rbx
  __int64 v115; // rax
  __int64 v116; // rax
  _QWORD *v117; // rax
  __int64 v118; // rax
  struct Jot::IServerRevisionStore *v119; // rax
  _QWORD *v120; // rax
  __int64 v121; // rax
  __int64 v122; // rax
  __int64 v123; // r8
  _QWORD *v124; // rax
  Jot::StaticContextReplication *v125; // rbx
  _QWORD *v126; // rax
  __int64 Child; // rax
  Jot::StaticContextReplication *v128; // rbx
  Jot::StaticContextReplication *v129; // rcx
  __int64 v130; // rax
  Jot *v131; // r15
  _QWORD *v132; // rbx
  __int64 v133; // rax
  __int64 v134; // rax
  __int64 ContainingSection; // rax
  __int64 v136; // rcx
  Jot::CGraphIterator *v137; // rdi
  __int64 v138; // r15
  __int64 v139; // r14
  __int64 v140; // rsi
  _QWORD *v141; // rbx
  _QWORD *v142; // rax
  Jot::CReplicatorWithBranchBase *v143; // rsi
  __int64 v144; // rax
  char v145; // bl
  __int64 v146; // r8
  struct Jot::IRevision_MayNotBeOptimal *v147; // rbx
  struct Jot::IRevision **v148; // r14
  struct Jot::IRevision_MayNotBeOptimal *v149; // r8
  struct Jot::IGraphNode *v150; // rdx
  void (__fastcall ***v151)(_QWORD, GUID *, struct Jot::IGraphNode **); // rax
  Jot::StaticContextReplication *v152; // rbx
  unsigned int v153; // edx
  bool v154; // r8
  __int64 v155; // rax
  __int64 v156; // rax
  __int64 v157; // rax
  Jot *v158; // rax
  const void *v159; // rax
  Jot *v160; // rax
  const struct std::exception_ptr *v161; // rdx
  const void *v162; // rax
  _QWORD *v163; // rax
  MsoCF::IAtom *v164; // rcx
  unsigned int v165; // ebx
  __int64 v166; // rax
  struct Jot::IGraphSpaceNode **v167; // r9
  Jot::StaticContextReplication *v168; // rbx
  void (__fastcall *v169)(Jot::StaticContextReplication *, _QWORD); // rdi
  _QWORD *v170; // rax
  void (__fastcall *v171)(Jot::RevisionTimeLogger **, __int64); // rbx
  __int64 v172; // rax
  __int64 v173; // rax
  void (__fastcall *v174)(Jot::RevisionTimeLogger **, __int64); // rbx
  __int64 v175; // rax
  __int64 v176; // rax
  unsigned int v177; // eax
  __int64 v178; // rax
  int v179; // eax
  __int64 v180; // rax
  _QWORD *v181; // rax
  Jot::StaticContextReplication *v182; // rbx
  char v183; // al
  int v184; // esi
  void (__fastcall ***v185)(_QWORD, GUID *, Jot::StaticContextReplication **); // rax
  Jot::StaticContextReplication *v186; // rax
  Jot::StaticContextReplication *v187; // rcx
  Jot::RevisionTimeLogger **v188; // rax
  Jot::RevisionTimeLogger *v189; // rdx
  Jot::RevisionTimeLogger *v190; // rcx
  __int64 v191; // rbx
  _QWORD *v192; // rax
  _QWORD *v193; // rbx
  void (__fastcall *v194)(Jot::RevisionTimeLogger **, __int64); // rbx
  __int64 v195; // rax
  __int64 v196; // rax
  __int64 v197; // rax
  __int64 v198; // rax
  __int64 v199; // rax
  Jot::StaticContextReplication *v200; // rbx
  Jot *v201; // rcx
  const struct MsoCF::ExtendedGUID *v202; // rdi
  __int64 v203; // rax
  struct Jot::IObjectSpaceRevisionCache *v204; // rax
  const struct _GUID *v205; // r9
  __int64 v206; // rax
  void (__fastcall ***v207)(_QWORD, GUID *, struct Jot::IGraphNode **); // rax
  __int64 v208; // rax
  Jot::RevisionTimeLogger *v209; // rcx
  const void *v210; // rax
  __int64 v211; // rax
  Jot::StaticContextReplication **KnowledgeFromPropertySet; // rax
  __int64 v213; // rax
  __int64 v214; // rax
  int v215; // edx
  int v216; // r8d
  int v217; // r9d
  unsigned int v218; // ebx
  Jot::GraphSpaceEditor *v219; // rax
  unsigned int v220; // r8d
  bool (*v221)(MsoCF::CPropertySet *__hidden, const struct MsoCF::PropertyInfo *, void *); // r10
  char v222; // al
  __int32 v223; // edx
  int v224; // ebx
  struct Jot::IRevision *v225; // rdx
  bool v226; // r8
  __int64 v227; // rax
  __int64 v228; // rax
  __int64 CachedFileIdentifier; // rax
  __int64 v230; // rax
  __int64 v231; // rax
  struct Jot::IGraphNode *v232; // rax
  Jot::StaticContextReplication *v233; // rcx
  unsigned int v234; // edx
  const struct MsoCF::PropertyInfo *v235; // rdx
  bool (*v236)(MsoCF::CPropertySet *__hidden, const struct MsoCF::PropertyInfo *, void *); // r9
  char v237; // al
  void (__fastcall ***v238)(_QWORD, GUID *, Jot::StaticContextReplication **); // rax
  __int64 v239; // rax
  __int64 v240; // rax
  __int64 v241; // rax
  unsigned int v242; // r8d
  unsigned int v243; // r8d
  struct Jot::IGraphNode *v244; // rdx
  _QWORD *BranchBaseRevision; // rax
  Jot::RevisionTimeLogger *v246; // rcx
  __int64 v247; // rax
  Jot::RevisionTimeLogger *v248; // rcx
  Jot::RevisionTimeLogger *v249; // rcx
  __int64 v250; // rax
  const void *v251; // rax
  unsigned int v252; // r9d
  int v253; // edx
  int v254; // ecx
  int v255; // r8d
  int v256; // r9d
  void (__fastcall *v257)(struct Jot::IGraphNode *, GUID *, Jot **); // rax
  Jot::CReplicatorWithBranchBase *v258; // rcx
  void (__fastcall *v259)(Jot::RevisionTimeLogger **, _OWORD *); // rbx
  struct Jot::IGraphSpace *v260; // rax
  __int64 v261; // rax
  __int64 v262; // rax
  __int64 v263; // rax
  struct Csi::IKnowledge *v264; // r9
  const struct MsoCF::PropertyInfo *v265; // r8
  bool v266; // r9
  __int64 v267; // rax
  char v268; // al
  unsigned int v269; // edx
  unsigned int TrackingPropertyFromReplicatorRole; // eax
  unsigned int v271; // r8d
  const struct MsoCF::ExtendedGUID *v272; // r9
  char v273; // al
  __int64 v274; // rcx
  __int64 v275; // r8
  struct Jot::IGraphSpaceNode *v276; // rdx
  void (__fastcall ***v277)(_QWORD, GUID *, Jot::CReplicatorWithBranchBase **); // rcx
  Jot *v278; // rbx
  __int64 v279; // rdx
  void (__fastcall *v280)(Jot *, __int64, __int64, Jot::CReplicatorWithBranchBase **, _DWORD); // rsi
  __int64 v281; // rdi
  __int64 v282; // rax
  unsigned int v283; // edx
  void (__fastcall ***v284)(_QWORD, GUID *, Jot::StaticContextReplication **); // rcx
  unsigned int v285; // eax
  unsigned int v286; // r8d
  const struct MsoCF::ExtendedGUID *v287; // r9
  void (__fastcall *v288)(struct Jot::IGraphNode *, GUID *, Jot **); // rax
  _QWORD *v289; // rbx
  _QWORD *v290; // rax
  struct Jot::EDP::Identity *v291; // [rsp+20h] [rbp-438h]
  struct Jot::CGraphIterator *v292; // [rsp+40h] [rbp-418h] BYREF
  Jot *v293; // [rsp+48h] [rbp-410h] BYREF
  struct Jot::IGraphNode *v294; // [rsp+50h] [rbp-408h] BYREF
  MsoCF::IAtom *v295; // [rsp+58h] [rbp-400h] BYREF
  struct Jot::IGraphNode *v296; // [rsp+60h] [rbp-3F8h] BYREF
  struct Jot::IGraphNode *v297; // [rsp+68h] [rbp-3F0h] BYREF
  Jot::StaticContextReplication *v298; // [rsp+70h] [rbp-3E8h] BYREF
  Jot::StaticContextReplication *v299[2]; // [rsp+78h] [rbp-3E0h] BYREF
  Jot::StaticContextReplication *v300; // [rsp+88h] [rbp-3D0h] BYREF
  Jot::StaticContextReplication *v301[2]; // [rsp+90h] [rbp-3C8h] BYREF
  Jot::CReplicatorWithBranchBase *v302; // [rsp+A0h] [rbp-3B8h] BYREF
  char v303; // [rsp+A8h] [rbp-3B0h]
  char v304; // [rsp+A9h] [rbp-3AFh]
  Jot::CGraphIterator *v305; // [rsp+B0h] [rbp-3A8h] BYREF
  unsigned int *v306; // [rsp+B8h] [rbp-3A0h]
  _QWORD v307[4]; // [rsp+C0h] [rbp-398h] BYREF
  Jot *v308; // [rsp+E0h] [rbp-378h] BYREF
  char v309[72]; // [rsp+E8h] [rbp-370h] BYREF
  __int128 Buf1; // [rsp+130h] [rbp-328h] BYREF
  int v311; // [rsp+140h] [rbp-318h]
  __m128i v312; // [rsp+148h] [rbp-310h] BYREF
  __m128i v313; // [rsp+158h] [rbp-300h]
  _OWORD v314[2]; // [rsp+168h] [rbp-2F0h] BYREF
  int v315[2]; // [rsp+190h] [rbp-2C8h] BYREF
  int v316; // [rsp+198h] [rbp-2C0h] BYREF
  void ***v317; // [rsp+1A0h] [rbp-2B8h] BYREF
  Mso::Memory *v318; // [rsp+1A8h] [rbp-2B0h]
  _DWORD v319[12]; // [rsp+1B0h] [rbp-2A8h] BYREF
  __int64 v320; // [rsp+1E0h] [rbp-278h] BYREF
  _BYTE v321[88]; // [rsp+1E8h] [rbp-270h] BYREF
  __int32 v322; // [rsp+240h] [rbp-218h]
  char v323; // [rsp+288h] [rbp-1D0h]
  char IsEducationNotebook; // [rsp+290h] [rbp-1C8h]
  __int64 v325; // [rsp+2E0h] [rbp-178h] BYREF
  _BYTE v326[248]; // [rsp+2E8h] [rbp-170h] BYREF

  v2 = a2;
  v306 = a2;
  v299[0] = (Jot::StaticContextReplication *)this;
  LODWORD(v295) = 0;
  v4 = this[50];
  v302 = v4;
  if ( !v4 )
  {
    v194 = (void (__fastcall *)(Jot::RevisionTimeLogger **, __int64))*((_QWORD *)*this + 12);
    v195 = Jot::ErrNativeReplicator_ReplicationNotAllowed::ErrNativeReplicator_ReplicationNotAllowed(v315, 17065680);
    v196 = std::make_exception_ptr<Jot::ErrNativeReplicator_ReplicationNotAllowed>(&v312, v195);
LABEL_309:
    v194(this, v196);
    return;
  }
  OneNoteDotComNetworkStatusInstance = Jot::GetOneNoteDotComNetworkStatusInstance((Jot *)this);
  v6 = (Jot *)(unsigned int)(*(_DWORD *)((**(__int64 (__fastcall ***)(struct Jot::CNetworkStatus *))OneNoteDotComNetworkStatusInstance)(OneNoteDotComNetworkStatusInstance)
                                       + 88)
                           - 1);
  if ( (unsigned int)v6 <= 1 && !Jot::CanSyncOnMeteredNetwork(v6) )
  {
    v194 = (void (__fastcall *)(Jot::RevisionTimeLogger **, __int64))*((_QWORD *)*this + 12);
    v197 = Jot::ErrCannotSyncOnMeteredNetwork::ErrCannotSyncOnMeteredNetwork(v315, 17377498);
    v196 = std::make_exception_ptr<Jot::ErrCannotSyncOnMeteredNetwork>(&v312, v197);
    goto LABEL_309;
  }
  v7 = (void (__fastcall ***)(_QWORD, GUID *, struct Jot::IGraphNode **))(*(__int64 (__fastcall **)(Jot::RevisionTimeLogger *))(*(_QWORD *)v4 + 64LL))(v4);
  v294 = 0;
  if ( v7 )
  {
    if ( (char *)**v7 == (char *)MsoCF::CJotComObjectForMakeComObject<Jot::CRootGraphSpace>::QueryInterface )
      MsoCF::CJotComObjectForMakeComObject<Jot::CRootGraphSpace>::QueryInterface(
        v7,
        &GUID_6975ccb9_037d_4258_ab28_9d6185f7ba75,
        &v294);
    else
      (**v7)(v7, &GUID_6975ccb9_037d_4258_ab28_9d6185f7ba75, &v294);
  }
  if ( v294 )
  {
    v8 = *v2;
    if ( *v2 <= 0x14 )
    {
      if ( v8 == 20 )
      {
        Jot::CAsyncResultCancelOnDestroyPtr<Jot::IAsyncWithResult<void>>::operator=(this + 59, 0);
        LOBYTE(v225) = Jot::CNativeReplicator::IsSyncingToOneDrive(v4);
        Jot::RevisionTimeLogger::LogLegacySyncRevisionInbound(this[52], v225, v226);
        *v2 = 22;
        goto LABEL_26;
      }
      if ( v8 <= 0xF )
      {
        if ( v8 != 15 )
        {
          v9 = v8 - 10;
          if ( !v9 )
          {
            v10 = (void (__fastcall ***)(_QWORD, GUID *, struct Jot::IGraphNode **))(*(__int64 (__fastcall **)(Jot::RevisionTimeLogger *))(*(_QWORD *)v4 + 64LL))(v4);
            v296 = 0;
            if ( v10 )
            {
              if ( (char *)**v10 == (char *)MsoCF::CJotComObjectForMakeComObject<Jot::CRootGraphSpace>::QueryInterface )
                MsoCF::CJotComObjectForMakeComObject<Jot::CRootGraphSpace>::QueryInterface(
                  v10,
                  &GUID_6975ccb9_037d_4258_ab28_9d6185f7ba75,
                  &v296);
              else
                (**v10)(v10, &GUID_6975ccb9_037d_4258_ab28_9d6185f7ba75, &v296);
            }
            if ( !(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v4 + 25) + 120LL))(*((_QWORD *)v4 + 25)) )
            {
              if ( (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v4 + 25) + 112LL))(*((_QWORD *)v4 + 25)) )
              {
                v34 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v4 + 25) + 112LL))(*((_QWORD *)v4 + 25));
                if ( (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v34 + 136LL))(v34) )
                {
                  v35 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v4 + 25) + 112LL))(*((_QWORD *)v4 + 25));
                  v36 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v35 + 136LL))(v35);
                  (*(void (__fastcall **)(__int64, struct Jot::IGraphNode **))(*(_QWORD *)v36 + 208LL))(v36, &v297);
                  v37 = 0;
                  v299[0] = 0;
                  v38 = v297;
                  if ( v297
                    && ((**(void (__fastcall ***)(struct Jot::IGraphNode *, GUID *, Jot::StaticContextReplication **))v297)(
                          v297,
                          &GUID_9f7ae2e4_9cb0_45c1_9e5a_95fdd6d001ee,
                          v299),
                        v37 = v299[0],
                        v38 = v297,
                        v39 = 1,
                        v299[0])
                    || (v39 = 0, v37) )
                  {
                    (*(void (__fastcall **)(Jot::StaticContextReplication *))(*(_QWORD *)v37 + 16LL))(v37);
                    v38 = v297;
                  }
                  if ( !v39 )
                  {
                    v312 = 0;
                    si128 = _mm_load_si128((const __m128i *)&_xmm);
                    v313 = si128;
                    v312.m128i_i16[0] = 0;
                    v41 = (const wchar_t *)v312.m128i_i64[0];
                    v314[0] = v312;
                    v314[1] = si128;
                    std::wstring::~wstring(&v312);
                    v42 = (__m128i *)std::wstring::wstring(v307, (char *)v4 + 80);
                    v43 = *v42;
                    v312 = *v42;
                    v44 = v42[1];
                    v313 = v44;
                    v42->m128i_i16[0] = 0;
                    v42[1].m128i_i64[0] = 0;
                    v42[1].m128i_i64[1] = 7;
                    std::wstring::~wstring(v42);
                    v45 = (const wchar_t *)v314;
                    if ( _mm_srli_si128(si128, 8).m128i_u64[0] > 7 )
                      v45 = v41;
                    v46 = (const wchar_t *)&v312;
                    if ( _mm_srli_si128(v44, 8).m128i_u64[0] > 7 )
                      v46 = (const wchar_t *)v43.m128i_i64[0];
                    if ( v44.m128i_i64[0] == si128.m128i_i64[0] )
                    {
                      if ( v44.m128i_i64[0] )
                        v47 = wmemcmp(v46, v45, v44.m128i_u64[0]) == 0;
                      else
                        v47 = 1;
                    }
                    else
                    {
                      v47 = 0;
                    }
                    std::wstring::~wstring(&v312);
                    std::wstring::~wstring(v314);
                    if ( !v47 )
                    {
                      v48 = (void (__fastcall *)(Jot::RevisionTimeLogger **, __int64))*((_QWORD *)*this + 12);
                      Jot::ExceptionWithErrorCode::ExceptionWithErrorCode(v315, 0);
                      *(_QWORD *)v315 = &Jot::ErrEDP_SectionSyncViaDavUnsupported::`vftable';
                      v49 = std::make_exception_ptr<Jot::ErrEDP_SectionSyncViaDavUnsupported>(&v312, v315);
                      v48(this, v49);
                      if ( v297 )
                        (*(void (__fastcall **)(struct Jot::IGraphNode *))(*(_QWORD *)v297 + 16LL))(v297);
                      if ( v296 )
                        (*(void (__fastcall **)(struct Jot::IGraphNode *))(*(_QWORD *)v296 + 16LL))(v296);
                      goto LABEL_80;
                    }
                    v38 = v297;
                  }
                  if ( v38 )
                    (*(void (__fastcall **)(struct Jot::IGraphNode *))(*(_QWORD *)v38 + 16LL))(v38);
                }
              }
            }
            if ( *((_QWORD *)v4 + 35) )
            {
              MsoCF::CIPtr<CsiCell::ICellStorage,CsiCell::ICellStorage>::Assign(this + 47, *((_QWORD *)v4 + 35));
              *((_DWORD *)this + 96) = 10;
              *((_DWORD *)this + 97) = 10;
              *((_DWORD *)this + 93) = 3;
LABEL_22:
              v11 = v296;
              goto LABEL_23;
            }
            MsoCF::CIPtr<CsiCell::ICellStorage,CsiCell::ICellStorage>::Assign((char *)v4 + 280, this + 33);
            this[62] = 0;
            if ( *((_DWORD *)v4 + 77) )
            {
              v96 = v294;
              v312.m128i_i64[0] = 0;
              if ( v294 )
              {
                v97 = *(bool (**)(MsoCF::CPropertySet *__hidden, const struct MsoCF::PropertyInfo *, void *))(*(_QWORD *)v294 + 48LL);
                if ( v97 == MsoCF::CPropertySet::FGetProperty_Imp )
                {
                  v98 = MsoCF::CPropertySet::FGetProperty_Imp(
                          v294,
                          (const struct MsoCF::PropertyInfo *)Jot::PropertySpace_Jot11::priLastModifiedTimeStamp,
                          &v312);
                }
                else if ( (char *)v97 == (char *)Jot::CStaticPropertySet<Jot::IGraphNode>::FGetProperty_Imp )
                {
                  v98 = Jot::CStaticPropertySet<Jot::IGraphNode>::FGetProperty_Imp(
                          v294,
                          Jot::PropertySpace_Jot11::priLastModifiedTimeStamp,
                          &v312);
                }
                else
                {
                  v98 = (char *)v97 == (char *)Jot::CStaticPropertySet<MsoCF::IPropertySet>::FGetProperty_Imp
                      ? Jot::CStaticPropertySet<MsoCF::IPropertySet>::FGetProperty_Imp(
                          v294,
                          Jot::PropertySpace_Jot11::priLastModifiedTimeStamp,
                          &v312)
                      : (*(unsigned __int64 (__fastcall **)(struct Jot::IGraphNode *, char *, __m128i *))(*(_QWORD *)v294 + 48LL))(
                          v294,
                          Jot::PropertySpace_Jot11::priLastModifiedTimeStamp,
                          &v312);
                }
                v99 = v98 != 0 ? dword_181548AAC : 0;
                v96 = v294;
              }
              else
              {
                v99 = 0;
              }
              v312.m128i_i32[2] = v99;
              if ( v99 )
              {
                if ( v99 != 2031647 )
                {
                  v107 = MsoCF::LookupProperty((MsoCF *)*((unsigned int *)v4 + 77), v99);
                  v301[0] = v107;
                  *(_QWORD *)&v314[0] = 0;
                  if ( v96
                    && ((v108 = *(bool (**)(MsoCF::CPropertySet *__hidden, const struct MsoCF::PropertyInfo *, void *))(*(_QWORD *)v96 + 48LL),
                         v108 != MsoCF::CPropertySet::FGetProperty_Imp)
                      ? ((char *)v108 != (char *)Jot::CStaticPropertySet<Jot::IGraphNode>::FGetProperty_Imp
                       ? ((char *)v108 != (char *)Jot::CStaticPropertySet<MsoCF::IPropertySet>::FGetProperty_Imp
                        ? (v109 = (*(__int64 (__fastcall **)(struct Jot::IGraphNode *, Jot::StaticContextReplication *, _OWORD *))(*(_QWORD *)v96 + 48LL))(
                                    v96,
                                    v107,
                                    v314))
                        : (v109 = Jot::CStaticPropertySet<MsoCF::IPropertySet>::FGetProperty_Imp(v96, v107, v314)))
                       : (v109 = Jot::CStaticPropertySet<Jot::IGraphNode>::FGetProperty_Imp(v96, v107, v314)))
                      : (v109 = MsoCF::CPropertySet::FGetProperty_Imp(v96, v107, v314)),
                        v109) )
                  {
                    v110 = *((_DWORD *)v301[0] + 1);
                  }
                  else
                  {
                    v110 = 0;
                  }
                  DWORD2(v314[0]) = v110;
                  if ( !v110 || v110 == 2031647 )
                  {
                    v111 = v312.m128i_i32[2];
                    v112 = (Jot::RevisionTimeLogger *)v312.m128i_i64[0];
                  }
                  else
                  {
                    v111 = v312.m128i_i32[2];
                    if ( v312.m128i_i32[2] != 17170499 || v110 != 17170499 )
                    {
LABEL_287:
                      CrashWithRecovery(0x65756E73u, 0);
                      __debugbreak();
                    }
                    v112 = (Jot::RevisionTimeLogger *)v312.m128i_i64[0];
                    if ( v312.m128i_i64[0] == *(_QWORD *)&v314[0] )
                      goto LABEL_18;
                  }
                  if ( v111 != 17170499 )
                    goto LABEL_287;
                  this[62] = v112;
                }
              }
            }
LABEL_18:
            if ( (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v4 + 25) + 120LL))(*((_QWORD *)v4 + 25)) )
            {
              v211 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v4 + 25) + 120LL))(*((_QWORD *)v4 + 25));
              (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v211 + 176LL))(v211, (__int64)v4 + 8);
            }
            if ( *((_BYTE *)this + 409) )
            {
              v72 = 0;
              v299[0] = 0;
              v73 = (*(__int64 (__fastcall **)(Jot::RevisionTimeLogger *))(*(_QWORD *)v4 + 64LL))(v4);
              v74 = (Jot::StaticContextReplication *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v73 + 384LL))(v73);
              MsoCF::CIPtr<Jot::IGraphNode,Jot::IGraphNode>::AddRef(v74);
              v301[0] = v74;
              while ( v74 )
              {
                if ( MsoCF::IPropertySet::HasProperty(
                       v74,
                       (const struct MsoCF::PropertyInfo *)Jot::PropertySpace_Jot11::priLastRevisionSetOnGS) )
                {
                  LOBYTE(v292) = 0;
                  if ( (unsigned __int8)MsoCF::Properties::Raw<Jot::PropertySpace_Jot14::prtidPrimaryStorageIsCellStorage>::FGet(
                                          v74,
                                          &v292) )
                  {
                    if ( (_BYTE)v292 == 1 )
                    {
                      KnowledgeFromPropertySet = (Jot::StaticContextReplication **)Jot::GetKnowledgeFromPropertySet(
                                                                                     &v293,
                                                                                     v74,
                                                                                     469775403);
                      v72 = *KnowledgeFromPropertySet;
                      *KnowledgeFromPropertySet = 0;
                      v299[0] = v72;
                      if ( v293 )
                        (*(void (__fastcall **)(Jot *))(*(_QWORD *)v293 + 16LL))(v293);
                      break;
                    }
                  }
                }
                v102 = Jot::IGraphSpaceNode::UseParentGraphSpaceGraphNodeOf(v74);
                MsoCF::CIPtr<Jot::IGraphNode,Jot::IGraphNode>::AddRef(v102);
                v103 = v74;
                v74 = v102;
                v301[0] = v102;
                (*(void (__fastcall **)(Jot::StaticContextReplication *))(*(_QWORD *)v103 + 16LL))(v103);
              }
              v75 = (*(__int64 (__fastcall **)(__int64))(*((_QWORD *)v4 + 16) + 88LL))((__int64)v4 + 128);
              v76 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, Jot **, Jot::StaticContextReplication *, _QWORD, _BYTE, _BYTE, _BYTE))(*(_QWORD *)v75 + 56LL))(
                                v75,
                                &v293,
                                v72,
                                0,
                                0,
                                0,
                                0);
              v77 = this + 53;
              Jot::CAsyncResultCancelOnDestroyPtr<Jot::IAsyncWithResult<void>>::operator=(this + 53, *v76);
              if ( v293 )
                (*(void (__fastcall **)(Jot *))(*(_QWORD *)v293 + 16LL))(v293);
              if ( *v77 )
              {
                MsoCF::CIPtr<CsiCell::ICellStorage,CsiCell::ICellStorage>::Assign(this + 47, *v77);
                *((_DWORD *)this + 96) = 13;
                *((_DWORD *)this + 97) = 11;
                *((_DWORD *)this + 93) = 3;
              }
              else
              {
                *v306 = 14;
              }
              if ( v74 )
                (*(void (__fastcall **)(Jot::StaticContextReplication *))(*(_QWORD *)v74 + 16LL))(v74);
              if ( v72 )
                (*(void (__fastcall **)(Jot::StaticContextReplication *))(*(_QWORD *)v72 + 16LL))(v72);
            }
            else
            {
              *v2 = 14;
            }
            goto LABEL_22;
          }
          v14 = v9 - 1;
          if ( v14 )
          {
            v15 = v14 - 1;
            if ( v15 )
            {
              v16 = v15 - 1;
              if ( v16 )
              {
                if ( v16 != 1 )
                  goto LABEL_26;
                v17 = (*(__int64 (__fastcall **)(Jot::RevisionTimeLogger *))(*(_QWORD *)v4 + 64LL))(v4);
                BackingRevisionStore = Jot::IGraphSpace::GetBackingRevisionStore(v17, v301);
                MsoCF::CIPtr<Jot::IServerStore,Jot::IServerStore>::operator=<Jot::IObjectSpaceStoreOnCellStorage,Jot::IObjectSpaceStoreOnCellStorage>(
                  this + 58,
                  BackingRevisionStore);
                if ( v301[0] )
                  (*(void (__fastcall **)(Jot::StaticContextReplication *))(*(_QWORD *)v301[0] + 8LL))(v301[0]);
                if ( this[58] )
                {
                  *v2 = 12;
                  goto LABEL_26;
                }
LABEL_246:
                *v2 = 16;
                goto LABEL_26;
              }
              v198 = (*(__int64 (__fastcall **)(__int64))(*((_QWORD *)v4 + 16) + 88LL))((__int64)v4 + 128);
              v199 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v198 + 120LL))(v198);
              MsoCF::CIPtr<Jot::IStoreRevisionBatch,Jot::IStoreRevisionBatch>::CIPtr<Jot::IStoreRevisionBatch,Jot::IStoreRevisionBatch>(
                v299,
                v199);
              v200 = v299[0];
              if ( *((_BYTE *)v4 + 288) && v299[0] )
              {
                (*(void (__fastcall **)(Jot::StaticContextReplication *, Jot **))(*(_QWORD *)v299[0] + 200LL))(
                  v299[0],
                  &v293);
                v201 = v293;
                if ( v293 )
                {
                  v202 = (const struct MsoCF::ExtendedGUID *)(*(__int64 (__fastcall **)(Jot::StaticContextReplication *))(*(_QWORD *)v200 + 136LL))(v200);
                  v203 = (*(__int64 (__fastcall **)(Jot::RevisionTimeLogger *))(*(_QWORD *)v4 + 64LL))(v4);
                  v204 = (struct Jot::IObjectSpaceRevisionCache *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v203 + 24LL))(v203);
                  Jot::EnsureObjectSpaceRootStoreInCellStorage(v293, v204, v202, v205);
                  v201 = v293;
                }
                MsoCF::CIPtr<Jot::IObjectSpaceRevisionCache,Jot::IObjectSpaceRevisionCache>::Release(v201);
              }
              *v2 = 14;
              if ( !v200 )
                goto LABEL_26;
              v71 = *(__int64 (**)(void))(*(_QWORD *)v200 + 8LL);
              v70 = v200;
              if ( (char *)v71 == (char *)MsoCF::IThreadSafeBaseImpl<Jot::IObjectSpaceStoreOnCellStorage>::Release )
              {
                MsoCF::IThreadSafeBaseImpl<Jot::IObjectSpaceStoreOnCellStorage>::Release(v200);
                goto LABEL_26;
              }
LABEL_320:
              ((void (__fastcall *)(Jot::StaticContextReplication *))v71)(v70);
              goto LABEL_26;
            }
            v65 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v4 + 25) + 120LL))(*((_QWORD *)v4 + 25));
            v67 = v65;
            if ( v65 )
              (*(void (__fastcall **)(__int64, struct Jot::IGraphNode **))(*(_QWORD *)v65 + 200LL))(v65, &v296);
            else
              v296 = 0;
            if ( !(*(__int64 (__fastcall **)(_QWORD, __int64, __int64))(**((_QWORD **)v4 + 25) + 120LL))(
                    *((_QWORD *)v4 + 25),
                    v66,
                    v67)
              && *((_BYTE *)this + 408)
              || (v70 = v296) != 0 )
            {
              v68 = (*(__int64 (__fastcall **)(Jot::RevisionTimeLogger *))(*(_QWORD *)v4 + 64LL))(v4);
              v69 = (_DWORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v68 + 32LL))(v68);
              if ( !v69[4] && !memcmp_0(v69, &Jot::c_gctxidRuntimeDefault, 0x10u) )
              {
                v119 = Jot::CNativeReplicator::UseRevStoreAttached(v4);
                v120 = (_QWORD *)(*(__int64 (__fastcall **)(struct Jot::IServerRevisionStore *, Jot::StaticContextReplication **, __int64, _QWORD, _BYTE))(*(_QWORD *)v119 + 80LL))(
                                   v119,
                                   v301,
                                   1,
                                   0,
                                   0);
                Jot::CAsyncResultCancelOnDestroyPtr<Jot::IAsyncResult_HierarchicalContentLoader>::operator=(
                  this + 55,
                  *v120);
                if ( v301[0] )
                  (*(void (__fastcall **)(Jot::StaticContextReplication *))(*(_QWORD *)v301[0] + 16LL))(v301[0]);
                MsoCF::CIPtr<CsiCell::ICellStorage,CsiCell::ICellStorage>::Assign(this + 47, this[55]);
                *((_DWORD *)this + 96) = 15;
                *((_DWORD *)this + 97) = 4;
                *((_DWORD *)this + 93) = 3;
                v70 = v296;
                goto LABEL_106;
              }
              v70 = v296;
            }
            *v2 = 16;
LABEL_106:
            if ( !v70 )
              goto LABEL_26;
            v71 = *(__int64 (**)(void))(*(_QWORD *)v70 + 8LL);
            if ( v71 == MsoCF::IThreadSafeBaseImpl<Jot::CObjectSpaceRevisionCacheInCellStorage>::Release )
            {
              MsoCF::IThreadSafeBaseImpl<Jot::CObjectSpaceRevisionCacheInCellStorage>::Release();
              goto LABEL_26;
            }
            goto LABEL_320;
          }
          v206 = (*(__int64 (__fastcall **)(Jot::RevisionTimeLogger *))(*(_QWORD *)this[53] + 80LL))(this[53]);
          if ( (unsigned __int8)Jot::IsError<Jot::ErrObjectSpaceStore_NoLatestRevision>(v206) )
          {
            v207 = (void (__fastcall ***)(_QWORD, GUID *, struct Jot::IGraphNode **))(*(__int64 (__fastcall **)(Jot::RevisionTimeLogger *))(*(_QWORD *)v4 + 64LL))(v4);
            v297 = 0;
            if ( v207 )
            {
              if ( (char *)**v207 == (char *)MsoCF::CJotComObjectForMakeComObject<Jot::CRootGraphSpace>::QueryInterface )
                MsoCF::CJotComObjectForMakeComObject<Jot::CRootGraphSpace>::QueryInterface(
                  v207,
                  &GUID_6975ccb9_037d_4258_ab28_9d6185f7ba75,
                  &v297);
              else
                (**v207)(v207, &GUID_6975ccb9_037d_4258_ab28_9d6185f7ba75, &v297);
            }
            if ( !MsoCF::IPropertySet::HasProperty(
                    v297,
                    (const struct MsoCF::PropertyInfo *)Jot::PropertySpace_Jot14::priPrimaryStorageLastRevGenCount) )
            {
              if ( MsoCF::IPropertySet::HasProperty(
                     v297,
                     (const struct MsoCF::PropertyInfo *)Jot::PropertySpace_Jot11::priLastRevisionSetOnGS)
                || (v208 = (*(__int64 (__fastcall **)(Jot::RevisionTimeLogger *))(*(_QWORD *)v4 + 64LL))(v4),
                    (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v208 + 40LL))(v208)) )
              {
                *v2 = 27;
                v11 = v297;
LABEL_23:
                if ( v11 )
                {
                  v12 = *(_QWORD *)v11;
LABEL_25:
                  (*(void (**)(void))(v12 + 16))();
                }
LABEL_26:
                MsoCF::CIPtr<OneNote::ProgressUI::IProgress,OneNote::ProgressUI::IProgress>::Release(v294);
                return;
              }
            }
            if ( v297 )
              (*(void (__fastcall **)(struct Jot::IGraphNode *))(*(_QWORD *)v297 + 16LL))(v297);
          }
          v209 = this[53];
          goto LABEL_333;
        }
        v188 = (Jot::RevisionTimeLogger **)sub_18020016C(v301);
        v189 = *v188;
        *v188 = 0;
        v190 = this[56];
        this[56] = v189;
        if ( v190 )
          (*(void (__fastcall **)(Jot::RevisionTimeLogger *))(*(_QWORD *)v190 + 8LL))(v190);
        if ( v301[0] )
          (*(void (__fastcall **)(Jot::StaticContextReplication *))(*(_QWORD *)v301[0] + 8LL))(v301[0]);
        v191 = (*(__int64 (__fastcall **)(Jot::RevisionTimeLogger *))(*(_QWORD *)this[55] + 96LL))(this[55]);
        MsoCF::CIPtr<Jot::COpenedFileTracker,Jot::COpenedFileTracker>::CIPtr<Jot::COpenedFileTracker,Jot::COpenedFileTracker>(
          v315,
          this + 58);
        std::vector<std::pair<MsoCF::ExtendedGUID,MsoCF::CIPtr<Jot::IRevision,Jot::IRevision>>>::vector<std::pair<MsoCF::ExtendedGUID,MsoCF::CIPtr<Jot::IRevision,Jot::IRevision>>>(
          &v316,
          v191);
        Jot::EDP::Identity::Identity((Jot::EDP::Identity *)v319, (Jot::RevisionTimeLogger *)((char *)v4 + 80));
        v192 = (_QWORD *)sub_1802127F4(v301, v315);
        v193 = this + 57;
        Jot::CAsyncResultCancelOnDestroyPtr<Jot::IAsyncWithResult<void>>::operator=(this + 57, *v192);
        if ( v301[0] )
          (*(void (__fastcall **)(Jot::StaticContextReplication *))(*(_QWORD *)v301[0] + 16LL))(v301[0]);
        std::wstring::~wstring(v319);
        std::vector<std::pair<MsoCF::ExtendedGUID,MsoCF::CIPtr<Jot::IRevision,Jot::IRevision>>>::~vector<std::pair<MsoCF::ExtendedGUID,MsoCF::CIPtr<Jot::IRevision,Jot::IRevision>>>(&v316);
        if ( *(_QWORD *)v315 )
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v315 + 8LL))(*(_QWORD *)v315);
        if ( !*v193 )
          goto LABEL_246;
        MsoCF::CIPtr<CsiCell::ICellStorage,CsiCell::ICellStorage>::Assign(this + 47, *v193);
        *((_DWORD *)this + 96) = 16;
        goto LABEL_265;
      }
      v50 = v8 - 16;
      if ( !v50 )
      {
        v113 = Jot::CNativeReplicator::UseRevStoreAttached(v4);
        v114 = *(__int64 (__fastcall **)(struct Jot::IServerRevisionStore *, Jot::StaticContextReplication **, __int64, __int64))(*(_QWORD *)v113 + 24LL);
        v115 = (*(__int64 (__fastcall **)(Jot::RevisionTimeLogger *))(*(_QWORD *)v4 + 64LL))(v4);
        v116 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v115 + 32LL))(v115);
        v117 = (_QWORD *)v114(v113, v301, 1, v116);
        Jot::CAsyncResultCancelOnDestroyPtr<Jot::IAsyncResult_HierarchicalContentLoader>::operator=(this + 54, *v117);
        if ( v301[0] )
          (*(void (__fastcall **)(Jot::StaticContextReplication *))(*(_QWORD *)v301[0] + 16LL))(v301[0]);
        MsoCF::CIPtr<CsiCell::ICellStorage,CsiCell::ICellStorage>::Assign(this + 47, this[54]);
        *((_DWORD *)this + 96) = 17;
        *((_DWORD *)this + 97) = 18;
        goto LABEL_136;
      }
      v51 = v50 - 1;
      if ( !v51 )
      {
        if ( !*(_QWORD *)(*(__int64 (__fastcall **)(Jot::RevisionTimeLogger *))(*(_QWORD *)this[54] + 96LL))(this[54]) )
        {
          if ( *((_BYTE *)v4 + 112) )
          {
            if ( Jot::ShouldLogTtid((Jot *)0x4C5292, 0x100EEu, 3u, v52) )
            {
              v214 = (*(__int64 (__fastcall **)(Jot::RevisionTimeLogger *, __m128i *))(*(_QWORD *)v4 + 112LL))(
                       v4,
                       &v312);
              Jot::Log_Impl<wchar_t [75],std::wstring,bool>((_DWORD)v4 + 288, v215, v216, v217, v214, (__int64)v4 + 288);
              std::wstring::~wstring(&v312);
            }
            (*(void (__fastcall **)(__int64))(*((_QWORD *)v4 + 16) + 40LL))((__int64)v4 + 128);
            if ( *((_DWORD *)v4 + 76) )
            {
              if ( !(*(__int64 (__fastcall **)(Jot::RevisionTimeLogger *))(*(_QWORD *)v4 + 64LL))(v4) )
              {
                CrashWithRecovery(0x11586C5u, 0);
                __debugbreak();
              }
              v218 = *((_DWORD *)v4 + 76);
              v219 = (Jot::GraphSpaceEditor *)(*(__int64 (__fastcall **)(Jot::RevisionTimeLogger *))(*(_QWORD *)v4 + 64LL))(v4);
              Jot::GraphSpaceEditor::HandleMergeOfDeletedContent(v219, (struct Jot::IGraphSpace *)v218, v220);
            }
          }
          v104 = (void (__fastcall *)(Jot::RevisionTimeLogger **, __m128i *))*((_QWORD *)*this + 12);
          v105 = Jot::ErrObjectSpaceStore_NoLatestRevision::ErrObjectSpaceStore_NoLatestRevision(v315, 18667042);
          v106 = (__m128i *)std::make_exception_ptr<Jot::ErrObjectSpaceStore_NoLatestRevision>(&v312, v105);
          goto LABEL_171;
        }
        v53 = (*(__int64 (__fastcall **)(Jot::RevisionTimeLogger *))(*(_QWORD *)this[54] + 96LL))(this[54]);
        MsoCF::CIPtr<Jot::IRevision,Jot::IRevision>::operator=(this + 52, v53);
        v55 = (MsoCF *)*((unsigned int *)v4 + 76);
        if ( !(_DWORD)v55 )
          goto LABEL_98;
        if ( !*((_BYTE *)v4 + 112) )
          goto LABEL_98;
        if ( !*((_BYTE *)this + 408) )
          goto LABEL_98;
        v56 = v294;
        v57 = MsoCF::LookupProperty(v55, v54);
        if ( !MsoCF::IPropertySet::HasProperty(v56, v57) )
          goto LABEL_98;
        Buf1 = 0;
        v311 = 0;
        v59 = v294;
        if ( !v294 )
          goto LABEL_98;
        v295 = 0;
        v60 = MsoCF::LookupProperty((MsoCF *)0x1C001DA5, v58);
        v61 = *(_QWORD *)v59;
        if ( *((_DWORD *)v60 + 1) == 117899271 )
        {
          if ( *(bool (**)(MsoCF::CPropertySet *__hidden, const struct MsoCF::PropertyInfo *, void *))(v61 + 48) == MsoCF::CPropertySet::FGetProperty_Imp )
          {
            v62 = MsoCF::CPropertySet::FGetProperty_Imp(v59, v60, &v295);
          }
          else if ( *(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(v61 + 48) == Jot::CStaticPropertySet<Jot::IGraphNode>::FGetProperty_Imp )
          {
            v62 = Jot::CStaticPropertySet<Jot::IGraphNode>::FGetProperty_Imp(v59, v60, &v295);
          }
          else if ( *(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(v61 + 48) == Jot::CStaticPropertySet<MsoCF::IPropertySet>::FGetProperty_Imp )
          {
            v62 = Jot::CStaticPropertySet<MsoCF::IPropertySet>::FGetProperty_Imp(v59, v60, &v295);
          }
          else
          {
            v62 = (*(__int64 (__fastcall **)(struct Jot::IGraphNode *, const struct MsoCF::PropertyInfo *, MsoCF::IAtom **))(v61 + 48))(
                    v59,
                    v60,
                    &v295);
          }
          goto LABEL_93;
        }
        v312.m128i_i64[0] = 0;
        v221 = *(bool (**)(MsoCF::CPropertySet *__hidden, const struct MsoCF::PropertyInfo *, void *))(v61 + 48);
        if ( v221 == MsoCF::CPropertySet::FGetProperty_Imp )
        {
          v222 = MsoCF::CPropertySet::FGetProperty_Imp(v59, v60, &v312);
        }
        else if ( (char *)v221 == (char *)Jot::CStaticPropertySet<Jot::IGraphNode>::FGetProperty_Imp )
        {
          v222 = Jot::CStaticPropertySet<Jot::IGraphNode>::FGetProperty_Imp(v59, v60, &v312);
        }
        else if ( (char *)v221 == (char *)Jot::CStaticPropertySet<MsoCF::IPropertySet>::FGetProperty_Imp )
        {
          v222 = Jot::CStaticPropertySet<MsoCF::IPropertySet>::FGetProperty_Imp(v59, v60, &v312);
        }
        else
        {
          v222 = (*(__int64 (__fastcall **)(struct Jot::IGraphNode *, const struct MsoCF::PropertyInfo *, __m128i *))(v61 + 48))(
                   v59,
                   v60,
                   &v312);
        }
        if ( v222 )
          v223 = *((_DWORD *)v60 + 1);
        else
          v223 = 0;
        v312.m128i_i32[2] = v223;
        if ( !v223 || v223 == 2031647 )
          goto LABEL_251;
        if ( v223 == 117899271 )
        {
          v295 = (MsoCF::IAtom *)v312.m128i_i64[0];
          MsoCF::CPropertyData::Copy_MakeDeep_ComplexType(&v295, 117899271);
          goto LABEL_362;
        }
        *(_QWORD *)&v314[0] = 0;
        MsoCF::CPropertyValue::WritePrvPrt_DifferentTypes(v314, &v312, 117899271);
        v224 = DWORD2(v314[0]);
        if ( !DWORD2(v314[0]) || DWORD2(v314[0]) == 2031647 )
        {
          if ( !MsoCF::CPropertyGlobals::g_fNoTypeSafety_HackHackHack )
          {
            if ( (v312.m128i_i32[2] & 0x2000000) != 0 )
              MsoCF::CPropertyData::FreeAndZero_ComplexType(&v312);
            v62 = 0;
LABEL_93:
            if ( v62 )
            {
LABEL_94:
              if ( (*((_DWORD *)v295 + 1) & 0x3FFFFFFF) == 0x14 )
              {
                MsoCF::Memory::Copy((MsoCF::IAtom *)((char *)v295 + 8), &Buf1, (void *)0x14, v63);
                if ( v295 )
                  MsoCF::IAtom::Release(v295);
                v64 = (_DWORD *)(*(__int64 (__fastcall **)(Jot::RevisionTimeLogger *))(*(_QWORD *)this[52] + 160LL))(this[52]);
                if ( v311 == v64[4] && !memcmp_0(&Buf1, v64, 0x10u) )
                {
                  Jot::CNativeReplicator_InboundReplication::EnsureBaseAndBranchInSyncWith(
                    (Jot::CNativeReplicator_InboundReplication *)this,
                    this[52]);
                  *v2 = 27;
                  goto LABEL_80;
                }
LABEL_98:
                *v2 = this[58] != 0 ? 19 : 22;
                goto LABEL_26;
              }
              v164 = v295;
LABEL_292:
              MsoCF::IAtom::Release(v164);
              goto LABEL_98;
            }
LABEL_251:
            v164 = v295;
            if ( !v295 )
              goto LABEL_98;
            goto LABEL_292;
          }
          *(_QWORD *)&v314[0] = v312.m128i_i64[0];
          MsoCF::CPropertyData::Copy_MakeDeep_ComplexType(v314, 117899271);
          DWORD2(v314[0]) = 117899271;
          v295 = *(MsoCF::IAtom **)&v314[0];
          MsoCF::CPropertyData::Copy_MakeDeep_ComplexType(&v295, 117899271);
        }
        else
        {
          v295 = *(MsoCF::IAtom **)&v314[0];
          MsoCF::CPropertyData::Copy_MakeDeep_ComplexType(&v295, 117899271);
          if ( (v224 & 0x2000000) == 0 )
          {
LABEL_362:
            if ( (v312.m128i_i32[2] & 0x2000000) != 0 )
              MsoCF::CPropertyData::FreeAndZero_ComplexType(&v312);
            goto LABEL_94;
          }
        }
        MsoCF::CPropertyData::FreeAndZero_ComplexType(v314);
        goto LABEL_362;
      }
      v177 = v51 - 1;
      if ( v177 )
      {
        if ( v177 != 1 )
          goto LABEL_26;
        v178 = (*(__int64 (__fastcall **)(Jot::RevisionTimeLogger *))(*(_QWORD *)v4 + 64LL))(v4);
        v179 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v178 + 32LL))(v178);
        v180 = sub_1808DE538(
                 (int)v315,
                 (int)this + 464,
                 (int)this + 416,
                 v179,
                 (Jot::RevisionTimeLogger *)((char *)v4 + 80));
        v181 = (_QWORD *)sub_180775CD4(v301, v180);
        Jot::CAsyncResultCancelOnDestroyPtr<Jot::IAsyncWithResult<void>>::operator=(this + 59, *v181);
        MsoCF::CIPtr<OneNote::ProgressUI::IProgress,OneNote::ProgressUI::IProgress>::Release(v301[0]);
        sub_1801AD9A4(v315);
        MsoCF::CIPtr<CsiCell::ICellStorage,CsiCell::ICellStorage>::Assign(this + 47, this[59]);
        *((_DWORD *)this + 96) = 20;
LABEL_265:
        *((_DWORD *)this + 97) = 21;
        goto LABEL_136;
      }
      v213 = (*(__int64 (__fastcall **)(Jot::RevisionTimeLogger *))(*(_QWORD *)this[54] + 80LL))(this[54]);
      if ( !(unsigned __int8)Jot::IsError<Jot::ErrObjectSpaceStore_NoNewerRevision>(v213) )
      {
        v209 = this[54];
LABEL_333:
        v104 = (void (__fastcall *)(Jot::RevisionTimeLogger **, __m128i *))*((_QWORD *)*this + 12);
        v210 = (const void *)(*(__int64 (__fastcall **)(Jot::RevisionTimeLogger *))(*(_QWORD *)v209 + 80LL))(v209);
        v312 = 0;
        __ExceptionPtrCopy(&v312, v210);
        v106 = &v312;
LABEL_171:
        v104(this, v106);
        goto LABEL_26;
      }
LABEL_188:
      *v2 = 27;
      goto LABEL_26;
    }
    if ( v8 > 0x1A )
    {
      v13 = v8 - 27;
      if ( !v13 )
      {
        if ( !*((_BYTE *)this + 408) && !*((_BYTE *)this + 411) )
        {
          *v2 = 29;
          goto LABEL_26;
        }
        v28 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v4 + 25) + 120LL))(*((_QWORD *)v4 + 25));
        v30 = v28;
        if ( v28 )
        {
          (*(void (__fastcall **)(__int64, Jot::StaticContextReplication **))(*(_QWORD *)v28 + 200LL))(v28, v299);
          v31 = v299[0];
        }
        else
        {
          v299[0] = 0;
          v31 = 0;
        }
        v32 = 32;
        if ( !v31 )
          goto LABEL_57;
        v293 = 0;
        if ( v294 )
        {
          v288 = **(void (__fastcall ***)(struct Jot::IGraphNode *, GUID *, Jot **))v294;
          if ( (char *)v288 == (char *)MsoCF::CJotComObject<Jot::CGraphSpaceNode,MsoCF::CAllocatorOnNew>::QueryInterface )
            MsoCF::CJotComObject<Jot::CGraphSpaceNode,MsoCF::CAllocatorOnNew>::QueryInterface(
              v294,
              &GUID_4c161eeb_0e6f_4c83_921d_3102a717501b,
              &v293);
          else
            v288(v294, &GUID_4c161eeb_0e6f_4c83_921d_3102a717501b, &v293);
        }
        v32 = 96;
        LODWORD(v295) = 1120;
        v33 = 1;
        if ( !Jot::StaticContextReplication::IsStaticContextParent(v293, v29) )
LABEL_57:
          v33 = 0;
        if ( (v32 & 0x40) != 0 )
        {
          v32 &= ~0x40u;
          if ( v293 )
            (*(void (__fastcall **)(Jot *, struct Jot::IGraphSpaceNode *, __int64))(*(_QWORD *)v293 + 16LL))(
              v293,
              v29,
              v30);
        }
        if ( (v32 & 0x20) != 0 )
          MsoCF::CIPtr<Jot::IObjectSpaceRevisionCache,Jot::IObjectSpaceRevisionCache>::Release(v299[0]);
        if ( !v33 )
          goto LABEL_62;
        v289 = this + 61;
        if ( !this[61] )
        {
          v290 = (_QWORD *)(***((__int64 (__fastcall ****)(_QWORD, __int128 *, __int64))v4 + 8))(
                             *((_QWORD *)v4 + 8),
                             &Buf1,
                             1);
          Jot::CAsyncResultCancelOnDestroyPtr<Jot::IAsyncWithResult<void>>::operator=(this + 61, *v290);
          MsoCF::CIPtr<OneNote::ProgressUI::IProgress,OneNote::ProgressUI::IProgress>::Release(Buf1);
        }
        if ( (*(unsigned __int8 (__fastcall **)(_QWORD, struct Jot::IGraphSpaceNode *, __int64))(*(_QWORD *)*v289 + 32LL))(
               *v289,
               v29,
               v30) )
        {
LABEL_62:
          *v2 = 28;
          goto LABEL_26;
        }
        MsoCF::CIPtr<CsiCell::ICellStorage,CsiCell::ICellStorage>::Assign(this + 47, *v289);
        *((_DWORD *)this + 96) = 28;
        *((_DWORD *)this + 97) = 29;
LABEL_136:
        *((_DWORD *)this + 93) = 3;
        goto LABEL_26;
      }
      v19 = v13 - 1;
      if ( v19 )
      {
        v20 = v19 - 1;
        if ( v20 )
        {
          if ( v20 == 1 )
          {
            v100 = 0;
            v293 = 0;
            LOBYTE(v292) = 0;
            if ( *((_BYTE *)this + 409) )
            {
              v263 = (*(__int64 (__fastcall **)(__int64))(*((_QWORD *)v4 + 16) + 88LL))((__int64)v4 + 128);
              (*(void (__fastcall **)(__int64, Jot **, struct Jot::CGraphIterator **))(*(_QWORD *)v263 + 64LL))(
                v263,
                &v293,
                &v292);
              v100 = v293;
            }
            if ( *((_BYTE *)v4 + 288) && *((_BYTE *)this + 408) )
            {
              if ( v100 && !Jot::CAsyncResultBase::HasPendingError((Jot::CAsyncResultBase *)this) )
              {
                Jot::CGraphLock::CGraphLock((Jot::CGraphLock *)&Buf1, v294, 0x3FFFu);
                Jot::SetKnowledgeInPropertySet(v294, (struct MsoCF::IPropertySet *)0x1C00342B, (unsigned int)v293, v264);
                Jot::CGraphLock::~CGraphLock((Jot::CGraphLock *)&Buf1);
              }
              if ( *((_BYTE *)this + 409) )
              {
                Jot::CGraphLock::CGraphLock((Jot::CGraphLock *)&Buf1, v294, 0x3FFFu);
                if ( (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v4 + 25) + 120LL))(*((_QWORD *)v4 + 25))
                  && (LOBYTE(v265) = (_BYTE)v292) != 0 )
                {
                  Jot::FSetBoolIfDifferent(v294, (struct MsoCF::IPropertySet *)0x80034AC, (unsigned int)v265, v266);
                }
                else
                {
                  Jot::RemovePropertyIfExist(
                    v294,
                    (struct MsoCF::IPropertySet *)Jot::PropertySpace_Jot14::priSectionHasHotboxContent,
                    v265);
                }
                Jot::CGraphLock::~CGraphLock((Jot::CGraphLock *)&Buf1);
              }
            }
            if ( !Jot::CAsyncResultBase::HasPendingError((Jot::CAsyncResultBase *)this) )
            {
              Jot::CNativeReplicator::UpdateStoreNeedOptimizeIfNeeded(v4, 0);
              v299[0] = 0;
              v165 = *((_DWORD *)v4 + 18);
              v166 = (*(__int64 (__fastcall **)(Jot::RevisionTimeLogger *))(*(_QWORD *)v4 + 64LL))(v4);
              MsoCF::QI_OrNull<Jot::IGraphSpaceNode,&__s_GUID const _GUID_4c161eeb_0e6f_4c83_921d_3102a717501b>(
                v301,
                v166);
              LOBYTE(v165) = Jot::StaticContextReplication::ShouldUseEfficientStaticContextReplicationChild(
                               v301[0],
                               (struct Jot::IGraphSpaceNode *)v165,
                               (unsigned int)v299,
                               v167);
              MsoCF::CIPtr<OneNote::ProgressUI::IProgress,OneNote::ProgressUI::IProgress>::Release(v301[0]);
              if ( (_BYTE)v165 )
              {
                Jot::CGraphLock::CGraphLock((Jot::CGraphLock *)&Buf1, v294, 0x3FFFu);
                v267 = (*(__int64 (__fastcall **)(Jot::RevisionTimeLogger *))(*(_QWORD *)v4 + 64LL))(v4);
                v268 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v267 + 32LL))(v267);
                LOBYTE(v269) = 1;
                TrackingPropertyFromReplicatorRole = Jot::StaticContextReplication::GetTrackingPropertyFromReplicatorRole(
                                                       (Jot::StaticContextReplication *)*((unsigned int *)v4 + 18),
                                                       v269,
                                                       v268);
                v168 = v299[0];
                Jot::StaticContextReplication::RemoveTrackedContext(
                  v299[0],
                  (struct Jot::IGraphSpaceNode *)TrackingPropertyFromReplicatorRole,
                  v271,
                  v272);
                Jot::CGraphLock::~CGraphLock((Jot::CGraphLock *)&Buf1);
              }
              else
              {
                v168 = v299[0];
              }
              MsoCF::CIPtr<OneNote::ProgressUI::IProgress,OneNote::ProgressUI::IProgress>::Release(v168);
            }
            v101 = (void (__fastcall *)(Jot::RevisionTimeLogger **, __m128i *))*((_QWORD *)*this + 12);
            v312 = 0;
            __ExceptionPtrCreate(&v312);
            v101(this, &v312);
            MsoCF::CIPtr<OneNote::ProgressUI::IProgress,OneNote::ProgressUI::IProgress>::Release(v293);
          }
          goto LABEL_26;
        }
        v21 = this + 65;
        v22 = this[65];
        if ( v22 )
        {
          v159 = (const void *)(*(__int64 (__fastcall **)(Jot::RevisionTimeLogger *))(*(_QWORD *)v22 + 80LL))(v22);
          if ( __ExceptionPtrToBool(v159) )
          {
            v160 = (Jot *)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v21 + 80LL))(*v21);
            if ( !Jot::FSuppressSyncError(v160, v161) )
            {
              v162 = (const void *)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v21 + 80LL))(*v21);
              v312 = 0;
              __ExceptionPtrCopy(&v312, v162);
              Jot::CAsyncResultBase::SetErrorForCompletion(this, &v312);
            }
          }
        }
        while ( 1 )
        {
          if ( !*((_DWORD *)this + 128) )
          {
            *v306 = 30;
            goto LABEL_26;
          }
          TailAddr = Ofc::CListImpl::GetTailAddr((Ofc::CListImpl *)(this + 63));
          if ( TailAddr )
            v79 = (__int64 *)*TailAddr;
          else
            v79 = 0;
          if ( v79 )
            (*(void (__fastcall **)(__int64 *))(*v79 + 8))(v79);
          *(_QWORD *)&v314[0] = v79;
          v80 = Ofc::CListImpl::RemoveTail((Ofc::CListImpl *)(this + 63));
          v81 = v80;
          if ( v80 )
            (*(void (__fastcall **)(void *))(*(_QWORD *)v80 + 16LL))(v80);
          v82 = (*(__int64 (__fastcall **)(__int64 *, void *))(*v79 + 24))(v79, v81);
          if ( (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v82 + 64LL))(v82) )
            break;
          (*(void (__fastcall **)(__int64 *))(*v79 + 16))(v79);
        }
        Jot::CAsyncResultCancelOnDestroyPtr<Jot::IAsyncWithResult<void>>::operator=(this + 65, 0);
        v121 = (*(__int64 (__fastcall **)(__int64 *))(*v79 + 24))(v79);
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v121 + 72LL))(v121, (__int64)v4 + 8);
        v122 = (*(__int64 (__fastcall **)(__int64 *))(*v79 + 24))(v79);
        LOBYTE(v123) = 1;
        v124 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, __int128 *, __int64, _QWORD, _BYTE, _BYTE))(*(_QWORD *)v122 + 80LL))(
                           v122,
                           &Buf1,
                           v123,
                           0,
                           0,
                           0);
        Jot::CAsyncResultCancelOnDestroyPtr<Jot::IAsyncWithResult<void>>::operator=(this + 65, *v124);
        MsoCF::CIPtr<OneNote::ProgressUI::IProgress,OneNote::ProgressUI::IProgress>::Release(Buf1);
        v299[0] = 0;
        (*(void (__fastcall **)(__int64 *, GUID *, Jot::StaticContextReplication **))*v79)(
          v79,
          &GUID_4408663d_efc7_4f6f_8a9b_51bf50f25979,
          v299);
        v125 = v299[0];
        if ( v299[0] )
        {
          v169 = *(void (__fastcall **)(Jot::StaticContextReplication *, _QWORD))(*(_QWORD *)v299[0] + 48LL);
          v170 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, Jot **))(*((_QWORD *)v4 + 17) + 56LL))(
                             (__int64)v4 + 136,
                             &v308);
          v169(v125, *v170);
        }
        MsoCF::CIPtr<CsiCell::ICellStorage,CsiCell::ICellStorage>::Assign(this + 47, this[65]);
        *((_DWORD *)this + 96) = 29;
        *((_DWORD *)this + 97) = 29;
        *((_DWORD *)this + 93) = 3;
        if ( v299[0] )
          (*(void (__fastcall **)(Jot::StaticContextReplication *))(*(_QWORD *)v299[0] + 16LL))(v299[0]);
        v12 = *v79;
        goto LABEL_25;
      }
      v83 = (*(__int64 (__fastcall **)(Jot::RevisionTimeLogger *))(*(_QWORD *)v4 + 64LL))(v4);
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v83 + 368LL))(v83, 1);
      Jot::CGraphIterator::CGraphIterator((Jot::CGraphIterator *)&v320, v294);
      v84 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v4 + 25) + 120LL))(*((_QWORD *)v4 + 25));
      v86 = v84;
      if ( v84 )
      {
        (*(void (__fastcall **)(__int64, struct Jot::IGraphNode **))(*(_QWORD *)v84 + 200LL))(v84, &v296);
        LODWORD(v295) = 2048;
        v87 = v296;
      }
      else
      {
        v87 = 0;
        v296 = 0;
        LODWORD(v295) = 2048;
      }
      if ( !v87 )
      {
        if ( *((_BYTE *)this + 411) )
        {
          v298 = 0;
          v88 = v294;
          if ( v294 )
          {
            v89 = **(void (__fastcall ***)(struct Jot::IGraphNode *, GUID *, Jot::StaticContextReplication **))v294;
            if ( (char *)v89 == (char *)MsoCF::CJotComObject<Jot::CGraphSpaceNode,MsoCF::CAllocatorOnNew>::QueryInterface )
              MsoCF::CJotComObject<Jot::CGraphSpaceNode,MsoCF::CAllocatorOnNew>::QueryInterface(
                v294,
                &GUID_4c161eeb_0e6f_4c83_921d_3102a717501b,
                &v298);
            else
              v89(v294, &GUID_4c161eeb_0e6f_4c83_921d_3102a717501b, &v298);
            v88 = v294;
          }
          v293 = 0;
          if ( v88 )
          {
            v90 = **(void (__fastcall ***)(struct Jot::IGraphNode *, GUID *, Jot **))v88;
            if ( (char *)v90 == (char *)MsoCF::CJotComObject<Jot::CGraphSpaceNode,MsoCF::CAllocatorOnNew>::QueryInterface )
              MsoCF::CJotComObject<Jot::CGraphSpaceNode,MsoCF::CAllocatorOnNew>::QueryInterface(
                v88,
                &GUID_2a2d3f82_1340_4eea_ae28_8eb0f2f1189b,
                &v293);
            else
              v90(v88, &GUID_2a2d3f82_1340_4eea_ae28_8eb0f2f1189b, &v293);
          }
          *(_QWORD *)v315 = &v317;
          v316 = 0;
          v317 = &off_181515648;
          v318 = 0;
          v319[0] = 0;
          ((void (__fastcall *)(void ***, void ****, __int64))*off_181515648)(&off_181515648, &v317, 80);
          LOBYTE(v91) = 1;
          v93 = Jot::StaticContextReplication::GetTrackingPropertyFromReplicatorRole(
                  (Jot::StaticContextReplication *)*((unsigned int *)v4 + 18),
                  v91,
                  v92);
          Jot::StaticContextReplication::GetTrackedContexts(v298, v93, v315);
          v95 = 0;
          LODWORD(v295) = 0;
          if ( v316 > 0 )
          {
            do
            {
              v302 = 0;
              v278 = v293;
              v279 = *(_QWORD *)v293;
              v280 = *(void (__fastcall **)(Jot *, __int64, __int64, Jot::CReplicatorWithBranchBase **, _DWORD))(*(_QWORD *)v293 + 392LL);
              v307[0] = 20LL * v95;
              v281 = v307[0] + *(_QWORD *)(*(_QWORD *)v315 + 8LL);
              v282 = (*(__int64 (__fastcall **)(Jot *))(v279 + 24))(v293);
              LOBYTE(v291) = 0;
              v280(v278, v282, v281, &v302, (_DWORD)v291);
              if ( v302 )
              {
                v284 = *(void (__fastcall ****)(_QWORD, GUID *, Jot::StaticContextReplication **))(*(__int64 (__fastcall **)(Jot::CReplicatorWithBranchBase *, __int128 *, _QWORD))(*(_QWORD *)v302 + 528LL))(
                                                                                                    v302,
                                                                                                    &Buf1,
                                                                                                    *((unsigned int *)v4 + 18));
                v299[0] = 0;
                if ( v284 )
                  (**v284)(v284, &GUID_9d4c9098_ea4a_40d4_a98a_762d383e902e, v299);
                Ofc::TCntPtrList<Jot::INativeReplicator>::InsertHead((Ofc::CListImpl *)(this + 63));
                if ( v299[0] )
                  (*(void (__fastcall **)(Jot::StaticContextReplication *))(*(_QWORD *)v299[0] + 16LL))(v299[0]);
                MsoCF::CIPtr<OneNote::ProgressUI::IProgress,OneNote::ProgressUI::IProgress>::Release(Buf1);
              }
              else
              {
                LOBYTE(v283) = 1;
                v285 = Jot::StaticContextReplication::GetTrackingPropertyFromReplicatorRole(
                         (Jot::StaticContextReplication *)*((unsigned int *)v4 + 18),
                         v283,
                         *(_BYTE *)(*(_QWORD *)v315 + 8LL) + LOBYTE(v307[0]));
                Jot::StaticContextReplication::RemoveTrackedContext(
                  v298,
                  (struct Jot::IGraphSpaceNode *)v285,
                  v286,
                  v287);
              }
              MsoCF::CIPtr<Jot::IGraphSpace,Jot::IGraphSpace>::Release(v302);
              v95 = (_DWORD)v295 + 1;
              LODWORD(v295) = v95;
            }
            while ( v95 < v316 );
            v2 = v306;
          }
          v316 = 0;
          Mso::Memory::Free(v318, v94);
          MsoCF::CIPtr<Jot::IGraphSpace,Jot::IGraphSpace>::Release(v293);
          MsoCF::CIPtr<OneNote::ProgressUI::IProgress,OneNote::ProgressUI::IProgress>::Release(v298);
        }
        else
        {
          v301[0] = 0;
          Child = Jot::CGraphIteratorImpl<Jot::CUsableAsGraphIterator<Jot::CGraphSpaceHierarchyFilter>>::PGoFirstChild((Jot::CGraphPath *)&v320);
          MsoCF::QI_OrNull<Jot::IGraphSpace,&__s_GUID const _GUID_2a2d3f82_1340_4eea_ae28_8eb0f2f1189b>(v299, Child);
          v128 = v299[0];
          v129 = 0;
          while ( 1 )
          {
            v301[0] = v128;
            v299[0] = 0;
            MsoCF::CIPtr<Jot::IGraphSpace,Jot::IGraphSpace>::Release(v129);
            MsoCF::CIPtr<Jot::IGraphSpace,Jot::IGraphSpace>::Release(v299[0]);
            if ( !v128 )
              break;
            Jot::CNativeReplicator::GetChildReplicatorForChild(v4, &Buf1, v128);
            Ofc::TCntPtrList<Jot::INativeReplicator>::InsertHead((Ofc::CListImpl *)(this + 63));
            MsoCF::CIPtr<OneNote::ProgressUI::IProgress,OneNote::ProgressUI::IProgress>::Release(Buf1);
            v130 = Jot::CGraphIteratorImpl<Jot::CUsableAsGraphIterator<Jot::CGraphSpaceHierarchyFilter>>::PGoNextSiblingOrPop(
                     &v320,
                     0);
            MsoCF::QI_OrNull<Jot::IGraphSpace,&__s_GUID const _GUID_2a2d3f82_1340_4eea_ae28_8eb0f2f1189b>(v299, v130);
            v129 = v128;
            v128 = v299[0];
          }
          MsoCF::CIPtr<Jot::IGraphSpace,Jot::IGraphSpace>::Release(0);
        }
LABEL_150:
        *v2 = 29;
        MsoCF::CIPtr<Jot::IObjectSpaceRevisionCache,Jot::IObjectSpaceRevisionCache>::Release(v296);
        Jot::CGraphIteratorBase::DisconnectFromGraph((Jot::CGraphIteratorBase *)&v320);
        Jot::CGraphPath::~CGraphPath((Jot::CGraphPath *)&v320);
        goto LABEL_26;
      }
      v312.m128i_i64[0] = (__int64)&v320;
      v312.m128i_i32[2] = v322;
      v313.m128i_i8[0] = 0;
      v182 = 0;
      *(_QWORD *)&Buf1 = 0;
      v183 = 0;
      v184 = (int)v295;
      while ( 1 )
      {
        LOBYTE(v85) = v183;
        v185 = (void (__fastcall ***)(_QWORD, GUID *, Jot::StaticContextReplication **))Jot::CPreOrderTraverser<Jot::CGraphIteratorGraphSpaceHierarchy>::UseNext(
                                                                                          &v312,
                                                                                          v85,
                                                                                          v86);
        v298 = 0;
        if ( v185 )
        {
          if ( (char *)**v185 == (char *)MsoCF::CJotComObject<Jot::CGraphSpaceNode,MsoCF::CAllocatorOnNew>::QueryInterface )
            MsoCF::CJotComObject<Jot::CGraphSpaceNode,MsoCF::CAllocatorOnNew>::QueryInterface(
              v185,
              &GUID_2a2d3f82_1340_4eea_ae28_8eb0f2f1189b,
              &v298);
          else
            (**v185)(v185, &GUID_2a2d3f82_1340_4eea_ae28_8eb0f2f1189b, &v298);
        }
        v186 = v298;
        v298 = 0;
        v187 = v182;
        v182 = v186;
        *(_QWORD *)&Buf1 = v186;
        MsoCF::CIPtr<Jot::IGraphSpace,Jot::IGraphSpace>::Release(v187);
        MsoCF::CIPtr<Jot::IGraphSpace,Jot::IGraphSpace>::Release(v298);
        if ( !v182 )
        {
          MsoCF::CIPtr<Jot::IGraphSpace,Jot::IGraphSpace>::Release(0);
          v2 = v306;
          goto LABEL_150;
        }
        v303 = 0;
        v301[0] = (Jot::StaticContextReplication *)(*(__int64 (__fastcall **)(Jot::StaticContextReplication *))(*(_QWORD *)v182 + 24LL))(v182);
        v307[0] = (*(__int64 (__fastcall **)(Jot::StaticContextReplication *))(*(_QWORD *)v182 + 32LL))(v182);
        v273 = MsoCF::ExtendedGUID::operator==(v307[0], &Jot::c_gctxidRuntimeDefault);
        v275 = v274;
        if ( v273 )
          v275 = 0;
        v304 = (*(__int64 (__fastcall **)(struct Jot::IGraphNode *, Jot::StaticContextReplication *, __int64))(*(_QWORD *)v296 + 32LL))(
                 v296,
                 v301[0],
                 v275);
        if ( v304 )
          goto LABEL_458;
        v293 = 0;
        if ( **(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v182 == MsoCF::CJotComObject<Jot::CGraphSpaceNode,MsoCF::CAllocatorOnNew>::QueryInterface )
          MsoCF::CJotComObject<Jot::CGraphSpaceNode,MsoCF::CAllocatorOnNew>::QueryInterface(
            v182,
            &GUID_4c161eeb_0e6f_4c83_921d_3102a717501b,
            &v293);
        else
          (**(void (__fastcall ***)(Jot::StaticContextReplication *, GUID *, Jot **))v182)(
            v182,
            &GUID_4c161eeb_0e6f_4c83_921d_3102a717501b,
            &v293);
        v184 |= 0x80u;
        LODWORD(v295) = v184;
        LOBYTE(v292) = 1;
        if ( !Jot::StaticContextReplication::IsStaticContextParent(v293, v276) )
LABEL_458:
          LOBYTE(v292) = 0;
        if ( (v184 & 0x80u) != 0 )
        {
          v184 &= ~0x80u;
          if ( v293 )
            (*(void (__fastcall **)(Jot *))(*(_QWORD *)v293 + 16LL))(v293);
        }
        if ( (_BYTE)v292 )
        {
          if ( (*(unsigned __int8 (__fastcall **)(struct Jot::IGraphNode *, Jot::StaticContextReplication *, void *, _QWORD))(*(_QWORD *)v296 + 40LL))(
                 v296,
                 v301[0],
                 &Jot::c_gctxidRuntimeDefault,
                 v307[0]) )
          {
            goto LABEL_467;
          }
          v183 = 1;
        }
        else
        {
          v183 = v303;
        }
        if ( v304 )
        {
LABEL_467:
          v277 = *(void (__fastcall ****)(_QWORD, GUID *, Jot::CReplicatorWithBranchBase **))(*(__int64 (__fastcall **)(Jot::StaticContextReplication *, Jot::StaticContextReplication **, _QWORD))(*(_QWORD *)v182 + 528LL))(
                                                                                               v182,
                                                                                               &v300,
                                                                                               *((unsigned int *)v4 + 18));
          v302 = 0;
          if ( v277 )
            (**v277)(v277, &GUID_9d4c9098_ea4a_40d4_a98a_762d383e902e, &v302);
          Ofc::TCntPtrList<Jot::INativeReplicator>::InsertHead((Ofc::CListImpl *)(this + 63));
          if ( v302 )
            (*(void (__fastcall **)(Jot::CReplicatorWithBranchBase *))(*(_QWORD *)v302 + 16LL))(v302);
          MsoCF::CIPtr<OneNote::ProgressUI::IProgress,OneNote::ProgressUI::IProgress>::Release(v300);
          v183 = 1;
        }
      }
    }
    if ( v8 == 26 )
    {
      v118 = (*(__int64 (__fastcall **)(__int64))(*((_QWORD *)v4 + 16) + 88LL))((__int64)v4 + 128);
      if ( (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v118 + 120LL))(v118) )
      {
        v260 = (struct Jot::IGraphSpace *)(*(__int64 (__fastcall **)(Jot::RevisionTimeLogger *))(*(_QWORD *)v4 + 64LL))(v4);
        Jot::CHandleSectionRenameByONO::CHandleSectionRenameByONO((Jot::CHandleSectionRenameByONO *)v315, v260);
        if ( v318 )
        {
          v261 = Jot::ErrFilePendingRename::ErrFilePendingRename(v309, 17065686);
          v262 = std::make_exception_ptr<Jot::ErrFilePendingRename>(&v312, v261);
          Jot::CAsyncResultBase::SetErrorForCompletion(this, v262);
          Jot::CHandleSectionRenameByONO::PerformRename((Jot::CHandleSectionRenameByONO *)v315);
          Jot::CHandleSectionRenameByONO::~CHandleSectionRenameByONO((Jot::CHandleSectionRenameByONO *)v315);
          goto LABEL_26;
        }
        Jot::CHandleSectionRenameByONO::~CHandleSectionRenameByONO((Jot::CHandleSectionRenameByONO *)v315);
      }
      goto LABEL_188;
    }
    v23 = v8 - 21;
    if ( v23 )
    {
      v24 = v23 - 1;
      if ( v24 )
      {
        v25 = v24 - 1;
        if ( v25 )
        {
          v26 = v25 - 1;
          if ( !v26 )
          {
            v27 = this[52];
            if ( v27 )
            {
              v126 = (_QWORD *)(*(__int64 (__fastcall **)(Jot::RevisionTimeLogger *, __int128 *))(*(_QWORD *)v27 + 128LL))(
                                 v27,
                                 &Buf1);
              MsoCF::CIPtr<CsiCell::ICellStorage,CsiCell::ICellStorage>::Assign(this + 47, *v126);
              *((_DWORD *)this + 96) = 25;
              *((_DWORD *)this + 97) = 4;
              *((_DWORD *)this + 93) = 3;
              MsoCF::CIPtr<OneNote::ProgressUI::IProgress,OneNote::ProgressUI::IProgress>::Release(Buf1);
            }
            else
            {
              *v2 = 25;
            }
            goto LABEL_26;
          }
          if ( v26 != 1 )
            goto LABEL_26;
          v131 = (Jot *)(*(__int64 (__fastcall **)(Jot::RevisionTimeLogger *))(*(_QWORD *)this[61] + 96LL))(this[61]);
          v293 = v131;
          MsoCF::CIPtr<Jot::IGraphSpaceContent,Jot::IGraphSpaceContent>::AddRef(v131);
          v308 = v131;
          *(_QWORD *)&Buf1 = this + 52;
          if ( !this[52] )
            goto LABEL_237;
          v323 = 0;
          IsEducationNotebook = 0;
          v296 = (Jot::RevisionTimeLogger *)((char *)v4 + 136);
          v132 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _QWORD *))(*((_QWORD *)v4 + 17) + 56LL))(
                             (__int64)v4 + 136,
                             v307);
          v320 = (*(_QWORD *)std::chrono::steady_clock::now(v301) - *v132) / 1000000LL;
          v133 = (*(__int64 (__fastcall **)(Jot::RevisionTimeLogger *))(*(_QWORD *)v4 + 64LL))(v4);
          v134 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v133 + 384LL))(v133);
          ContainingSection = Jot::SectionEditor::GetContainingSection(v307, v134);
          v305 = 0;
          Jot::CGiRef<Jot::CNodeRef<Jot::CSemNotebookTrait>,Jot::CSemNotebookTrait>::operator=(&v305, ContainingSection);
          MsoCF::CIPtr<OneNote::ProgressUI::IProgress,OneNote::ProgressUI::IProgress>::Release(v307[0]);
          v137 = v305;
          if ( v305
            && (unsigned __int8)Jot::CSemNotebookGraphSpaceTrait_RejectDeleted<Jot::ISectionMetaData,131121>::IsValidGI_CheckedAlways_Throws(
                                  v136,
                                  v305) )
          {
            v227 = Jot::CGiRef<Jot::CNodeRef<Jot::CSemFolderTrait>,Jot::CSemFolderGSTrait>::UseNode(&v305);
            Jot::NotebookEditor::GetContainingNotebook(&v300, v227);
            v228 = Jot::CNodeRef<Jot::CSemPageContentTrait>::CNodeRef<Jot::CSemPageContentTrait>(v301, &v300);
            CachedFileIdentifier = Jot::NotebookEditor::GetCachedFileIdentifier(&v325, v228);
            if ( *(_BYTE *)(CachedFileIdentifier + 160) )
            {
              v230 = std::_Optional_construct_base<Jot::InkAnalyzer::CWord>::operator*(CachedFileIdentifier);
              std::_Optional_construct_base<Jot::FileIdentifier>::_Assign<Jot::FileIdentifier>(v321, v230);
            }
            else
            {
              std::_Optional_destruct_base<Jot::FileIdentifier,0>::reset(v321);
            }
            std::_Optional_destruct_base<Jot::FileIdentifier,0>::~_Optional_destruct_base<Jot::FileIdentifier,0>(&v325);
            v231 = Jot::CNodeRef<Jot::CSemPageContentTrait>::CNodeRef<Jot::CSemPageContentTrait>(&v298, &v300);
            IsEducationNotebook = Jot::NotebookEditor::IsEducationNotebook(v231);
            MsoCF::CIPtr<OneNote::ProgressUI::IProgress,OneNote::ProgressUI::IProgress>::Release(v300);
          }
          v325 = v320;
          std::optional<Jot::FileIdentifier>::optional<Jot::FileIdentifier>((Jot::FileIdentifier *)v326);
          v326[168] = IsEducationNotebook;
          Jot::CLegacyInboundLatencyLogger::OnEvent(&v325);
          v138 = Jot::OnInboundOfBelowSectionCompletedSuccessfully();
          v139 = (*(__int64 (__fastcall **)(Jot::RevisionTimeLogger *))(*(_QWORD *)v4 + 64LL))(v4);
          v140 = (*(__int64 (__fastcall **)(Jot::RevisionTimeLogger *))(*(_QWORD *)this[52] + 160LL))(this[52]);
          v141 = (_QWORD *)(*(__int64 (__fastcall **)(struct Jot::IGraphNode *, Jot::StaticContextReplication **))(*(_QWORD *)v296 + 56LL))(
                             v296,
                             v301);
          v142 = (_QWORD *)std::chrono::steady_clock::now(&v300);
          Jot::CNotifierHelper<Jot::CNotifierSingleThreadedConfig,std::chrono::duration<__int64,std::ratio<1,1000>> const,MsoCF::ExtendedGUID const &,Jot::IGraphSpace &>::Fire(
            v138,
            (*v142 - *v141) / 1000000LL,
            v140,
            v139);
          LOBYTE(v292) = 0;
          v143 = v302;
          v144 = (*(__int64 (__fastcall **)(Jot::CReplicatorWithBranchBase *))(*(_QWORD *)v302 + 64LL))(v302);
          v145 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v144 + 40LL))(v144);
          v131 = v293;
          if ( (*(unsigned __int8 (__fastcall **)(Jot *))(*(_QWORD *)v293 + 136LL))(v293) )
          {
            v171 = (void (__fastcall *)(Jot::RevisionTimeLogger **, __int64))*((_QWORD *)*this + 12);
            v172 = Jot::ErrGraphSpace_ContentLockPresent::ErrGraphSpace_ContentLockPresent(v315, 17065685);
            v173 = std::make_exception_ptr<Jot::ErrGraphSpace_ContentLockPresent>(&v312, v172);
            v171(this, v173);
            if ( v137 )
            {
              Jot::CTextImporter::~CTextImporter(v137);
              operator delete(v137);
            }
            std::_Optional_destruct_base<Jot::FileIdentifier,0>::~_Optional_destruct_base<Jot::FileIdentifier,0>(v321);
LABEL_238:
            v12 = *(_QWORD *)v131;
            goto LABEL_25;
          }
          if ( *((_BYTE *)v143 + 112) )
          {
            v147 = (struct Jot::IRevision_MayNotBeOptimal *)*((_QWORD *)v143 + 15);
            v296 = v147;
            MsoCF::CIPtr<Jot::IRevision,Jot::IRevision>::AddRef(v147);
            *(_QWORD *)&v314[0] = v147;
            v148 = this + 52;
            if ( !Jot::AreEqualRevisions(this[52], v147, v149) )
            {
              MsoCF::CIPtr<Jot::IRevision,Jot::IRevision>::Assign((char *)v143 + 120, *v148);
              v151 = (void (__fastcall ***)(_QWORD, GUID *, struct Jot::IGraphNode **))(*(__int64 (__fastcall **)(Jot::CReplicatorWithBranchBase *))(*(_QWORD *)v143 + 64LL))(v143);
              v297 = 0;
              if ( v151 )
              {
                if ( (char *)**v151 == (char *)MsoCF::CJotComObjectForMakeComObject<Jot::CRootGraphSpace>::QueryInterface )
                  MsoCF::CJotComObjectForMakeComObject<Jot::CRootGraphSpace>::QueryInterface(
                    v151,
                    &GUID_6975ccb9_037d_4258_ab28_9d6185f7ba75,
                    &v297);
                else
                  (**v151)(v151, &GUID_6975ccb9_037d_4258_ab28_9d6185f7ba75, &v297);
              }
              v301[0] = 0;
              Jot::CGraphIterator::CGraphIterator((Jot::CGraphIterator *)&v325, v297);
              if ( Jot::CGraphIteratorBase::FRootAtMainGraphRoot((Jot::CGraphIteratorBase *)&v325) )
              {
                v232 = Jot::CGraphIteratorBase::PPopToParent((Jot::CGraphIteratorBase *)&v325);
                v233 = (Jot::StaticContextReplication *)&v325;
                if ( !v232 )
                  v233 = 0;
                v301[0] = v233;
              }
              v152 = *(Jot::StaticContextReplication **)(*(__int64 (__fastcall **)(Jot::RevisionTimeLogger *))(*(_QWORD *)this[60] + 96LL))(this[60]);
              MsoCF::CIPtr<Jot::IRevision,Jot::IRevision>::AddRef(v152);
              v298 = v152;
              v312.m128i_i64[0] = 0;
              v312.m128i_i32[2] = 0;
              if ( *((_BYTE *)this + 411) )
              {
                LOBYTE(v153) = 1;
                LODWORD(v295) = Jot::StaticContextReplication::GetTrackingPropertyFromReplicatorRole(
                                  (Jot::StaticContextReplication *)*((unsigned int *)v143 + 18),
                                  v153,
                                  v154);
                *(_QWORD *)&Buf1 = v297;
                v235 = MsoCF::LookupProperty((MsoCF *)(unsigned int)v295, v234);
                v300 = v235;
                if ( (v312.m128i_i32[2] & 0x2000000) != 0 )
                {
                  MsoCF::CPropertyData::FreeAndZero_ComplexType(&v312);
                  v235 = v300;
                }
                else
                {
                  v312.m128i_i64[0] = 0;
                }
                if ( (_QWORD)Buf1
                  && ((v236 = *(bool (**)(MsoCF::CPropertySet *__hidden, const struct MsoCF::PropertyInfo *, void *))(*(_QWORD *)Buf1 + 48LL),
                       v236 != MsoCF::CPropertySet::FGetProperty_Imp)
                    ? ((char *)v236 != (char *)Jot::CStaticPropertySet<Jot::IGraphNode>::FGetProperty_Imp
                     ? ((char *)v236 != (char *)Jot::CStaticPropertySet<MsoCF::IPropertySet>::FGetProperty_Imp
                      ? (v237 = (*(__int64 (__fastcall **)(_QWORD, const struct MsoCF::PropertyInfo *, __m128i *))(*(_QWORD *)Buf1 + 48LL))(
                                  Buf1,
                                  v235,
                                  &v312))
                      : (v237 = Jot::CStaticPropertySet<MsoCF::IPropertySet>::FGetProperty_Imp(Buf1, v235, &v312)))
                     : (v237 = Jot::CStaticPropertySet<Jot::IGraphNode>::FGetProperty_Imp(Buf1, v235, &v312)))
                    : (v237 = MsoCF::CPropertySet::FGetProperty_Imp((MsoCF::CPropertySet *)Buf1, v235, &v312)),
                      v237) )
                {
                  v312.m128i_i32[2] = *((_DWORD *)v300 + 1);
                }
                else
                {
                  v312.m128i_i32[2] = 0;
                }
                *(_QWORD *)&Buf1 = *v148;
                v238 = (void (__fastcall ***)(_QWORD, GUID *, Jot::StaticContextReplication **))(*(__int64 (__fastcall **)(Jot::CReplicatorWithBranchBase *))(*(_QWORD *)v143 + 64LL))(v143);
                v300 = 0;
                if ( v238 )
                {
                  if ( (char *)**v238 == (char *)MsoCF::CJotComObject<Jot::CGraphSpaceNode,MsoCF::CAllocatorOnNew>::QueryInterface )
                    MsoCF::CJotComObject<Jot::CGraphSpaceNode,MsoCF::CAllocatorOnNew>::QueryInterface(
                      v238,
                      &GUID_4c161eeb_0e6f_4c83_921d_3102a717501b,
                      &v300);
                  else
                    (**v238)(v238, &GUID_4c161eeb_0e6f_4c83_921d_3102a717501b, &v300);
                }
                Jot::StaticContextReplication::AddTrackedContextsFromReferenceDelta(
                  v300,
                  (struct Jot::IGraphSpaceNode *)(unsigned int)v295,
                  (unsigned int)v152,
                  (struct Jot::IRevision *)Buf1,
                  v291);
                if ( v300 )
                  (*(void (__fastcall **)(Jot::StaticContextReplication *))(*(_QWORD *)v300 + 16LL))(v300);
              }
              if ( *((_QWORD *)v143 + 23) )
              {
                v239 = MsoCF::CIPtr<Jot::IRevision,Jot::IRevision>::CIPtr<Jot::IRevision,Jot::IRevision>(
                         &Buf1,
                         this + 52);
                if ( (unsigned __int8)Jot::CNativeReplicator::IsRevisionInTransitList(v143, v239) )
                {
                  MsoCF::CIPtr<Jot::IRevision,Jot::IRevision>::operator=(&v298, this + 52);
                  v240 = MsoCF::CIPtr<Jot::IRevision,Jot::IRevision>::CIPtr<Jot::IRevision,Jot::IRevision>(
                           &Buf1,
                           this + 52);
                  Jot::CNativeReplicator::RemoveRevisionFromTransitList(v143, v240, 0);
                  v152 = v298;
                }
                else
                {
                  std::deque<MsoCF::CIPtr<Jot::IRevision,Jot::IRevision>>::_Tidy((char *)v143 + 152);
                }
              }
              *(_QWORD *)&Buf1 = *v148;
              v155 = (*(__int64 (__fastcall **)(Jot::CReplicatorWithBranchBase *))(*(_QWORD *)v143 + 64LL))(v143);
              v300 = (Jot::StaticContextReplication *)(*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v155 + 704LL))(
                                                        v155,
                                                        v315);
              v156 = (*(__int64 (__fastcall **)(Jot::CReplicatorWithBranchBase *))(*(_QWORD *)v143 + 64LL))(v143);
              v295 = (MsoCF::IAtom *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v156 + 32LL))(v156);
              v157 = (*(__int64 (__fastcall **)(Jot::CReplicatorWithBranchBase *))(*(_QWORD *)v143 + 64LL))(v143);
              v158 = (Jot *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v157 + 24LL))(v157);
              Jot::IntegrateBranchChanges(
                v158,
                v295,
                v300,
                0,
                (struct Jot::IRevision_MayNotBeOptimal *)Buf1,
                v293,
                v152,
                v301[0],
                v292);
              std::wstring::~wstring(v315);
              Jot::CReplicatorWithBranchBase::SetBranchBaseRevision(v143, *v148);
              if ( *((_BYTE *)this + 411) )
              {
                v241 = (*(__int64 (__fastcall **)(Jot::CReplicatorWithBranchBase *))(*(_QWORD *)v143 + 64LL))(v143);
                (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v241 + 368LL))(v241, 1);
              }
              LOBYTE(v292) = 1;
              if ( (v312.m128i_i32[2] & 0x2000000) != 0 )
                MsoCF::CPropertyData::FreeAndZero_ComplexType(&v312);
              if ( v152 )
                (*(void (__fastcall **)(Jot::StaticContextReplication *))(*(_QWORD *)v152 + 8LL))(v152);
              Jot::CGraphIteratorBase::DisconnectFromGraph((Jot::CGraphIteratorBase *)&v325);
              Jot::CGraphPath::~CGraphPath((Jot::CGraphPath *)&v325);
              if ( v297 )
                (*(void (__fastcall **)(struct Jot::IGraphNode *))(*(_QWORD *)v297 + 16LL))(v297);
              v147 = v296;
            }
            if ( v147 )
              (*(void (__fastcall **)(struct Jot::IRevision_MayNotBeOptimal *))(*(_QWORD *)v147 + 8LL))(v147);
          }
          else
          {
            if ( v145 )
            {
              v148 = (struct Jot::IRevision **)Buf1;
            }
            else
            {
              LOBYTE(v146) = 1;
              v148 = this + 52;
              (*(void (__fastcall **)(Jot *, Jot::RevisionTimeLogger *, __int64, _QWORD))(*(_QWORD *)v293 + 80LL))(
                v293,
                this[52],
                v146,
                0);
              LOBYTE(v292) = 1;
            }
            MsoCF::CIPtr<Jot::IRevision,Jot::IRevision>::operator=((char *)v143 + 272, v148);
          }
          if ( !(_BYTE)v292 )
          {
LABEL_234:
            if ( v137 )
            {
              Jot::CTextImporter::~CTextImporter(v137);
              operator delete(v137);
            }
            std::_Optional_destruct_base<Jot::FileIdentifier,0>::~_Optional_destruct_base<Jot::FileIdentifier,0>(v321);
            v2 = v306;
LABEL_237:
            *v2 = 26;
            if ( !v131 )
              goto LABEL_26;
            goto LABEL_238;
          }
          if ( *((_DWORD *)v143 + 76) )
          {
            if ( (*(unsigned __int8 (__fastcall **)(Jot *, struct Jot::IRevision *))(*(_QWORD *)v293 + 88LL))(
                   v293,
                   *v148) )
            {
              Jot::CGraphLock::CGraphLock((Jot::CGraphLock *)&Buf1, v294, 0x3FFFu);
              Jot::GraphSpaceEditor::SetLastGenerationAsCurrent(
                v294,
                (struct Jot::IGraphNode *)*((unsigned int *)v143 + 76),
                v243);
LABEL_414:
              Jot::CGraphLock::~CGraphLock((Jot::CGraphLock *)&Buf1);
              goto LABEL_415;
            }
            if ( Jot::GraphSpaceEditor::HasPendingChildGraphSpaceDeletes(v294, 0, v242) )
            {
              Jot::CGraphLock::CGraphLock((Jot::CGraphLock *)&Buf1, v294, 0x3FFFu);
              Jot::GraphSpaceEditor::FinalizeChildGraphSpaceDeletes(v294, v244);
              goto LABEL_414;
            }
          }
LABEL_415:
          Jot::UnreadEditor::OnGraphSpaceInbound(v294, v150);
          goto LABEL_234;
        }
        if ( !*((_BYTE *)v4 + 112) )
        {
          *v2 = 24;
          goto LABEL_26;
        }
        MsoCF::CIPtr<CsiCell::ICellStorage,CsiCell::ICellStorage>::Assign(this + 47, this[60]);
        *((_DWORD *)this + 96) = 24;
      }
      else
      {
        if ( *((_BYTE *)v4 + 112) )
        {
          BranchBaseRevision = (_QWORD *)Jot::CReplicatorWithBranchBase::GetBranchBaseRevision(v4, &Buf1);
          Jot::CAsyncResultCancelOnDestroyPtr<Jot::IAsyncResult_HierarchicalContentLoader>::operator=(
            this + 60,
            *BranchBaseRevision);
          MsoCF::CIPtr<OneNote::ProgressUI::IProgress,OneNote::ProgressUI::IProgress>::Release(Buf1);
        }
        if ( !this[61] )
        {
          v163 = (_QWORD *)(***((__int64 (__fastcall ****)(_QWORD, __int128 *, __int64))v4 + 8))(
                             *((_QWORD *)v4 + 8),
                             &Buf1,
                             1);
          Jot::CAsyncResultCancelOnDestroyPtr<Jot::IAsyncWithResult<void>>::operator=(this + 61, *v163);
          MsoCF::CIPtr<OneNote::ProgressUI::IProgress,OneNote::ProgressUI::IProgress>::Release(Buf1);
        }
        MsoCF::CIPtr<CsiCell::ICellStorage,CsiCell::ICellStorage>::Assign(this + 47, this[61]);
        *((_DWORD *)this + 96) = 23;
      }
      *((_DWORD *)this + 97) = 4;
      goto LABEL_136;
    }
    v312 = 0;
    __ExceptionPtrCreate(&v312);
    v246 = this[59];
    if ( v246
      && (*(unsigned __int8 (__fastcall **)(Jot::RevisionTimeLogger *))(*(_QWORD *)v246 + 32LL))(v246)
      && (v247 = (*(__int64 (__fastcall **)(Jot::RevisionTimeLogger *))(*(_QWORD *)this[59] + 80LL))(this[59]),
          !(unsigned __int8)std::operator==(v247)) )
    {
      v248 = this[59];
    }
    else
    {
      v249 = this[57];
      if ( !v249 )
        goto LABEL_425;
      if ( !(*(unsigned __int8 (__fastcall **)(Jot::RevisionTimeLogger *))(*(_QWORD *)v249 + 32LL))(v249) )
        goto LABEL_425;
      v250 = (*(__int64 (__fastcall **)(Jot::RevisionTimeLogger *))(*(_QWORD *)this[57] + 80LL))(this[57]);
      if ( (unsigned __int8)std::operator==(v250) )
        goto LABEL_425;
      v248 = this[57];
    }
    v251 = (const void *)(*(__int64 (__fastcall **)(Jot::RevisionTimeLogger *))(*(_QWORD *)v248 + 80LL))(v248);
    __ExceptionPtrAssign(&v312, v251);
LABEL_425:
    if ( (unsigned __int8)Jot::IsError<Jot::ErrObjectSpaceStoreInCellStorage_MissingRevisionManifest>(&v312)
      || (unsigned __int8)Jot::IsError<Jot::ErrObjectSpaceStoreInCellStorage_MissingObjectGroup>(&v312) )
    {
      MsoShipAssertTagProc(1650537061);
      if ( Jot::ShouldLogTtid((Jot *)0x40B593, 0x1008Fu, 4u, v252) )
        Jot::Log_Impl<wchar_t [90],std::exception_ptr>(v254, v253, v255, v256, (__int64)&v312);
      v293 = 0;
      if ( v294 )
      {
        v257 = **(void (__fastcall ***)(struct Jot::IGraphNode *, GUID *, Jot **))v294;
        if ( (char *)v257 == (char *)MsoCF::CJotComObject<Jot::CGraphSpaceNode,MsoCF::CAllocatorOnNew>::QueryInterface )
          MsoCF::CJotComObject<Jot::CGraphSpaceNode,MsoCF::CAllocatorOnNew>::QueryInterface(
            v294,
            &GUID_2a2d3f82_1340_4eea_ae28_8eb0f2f1189b,
            &v293);
        else
          v257(v294, &GUID_2a2d3f82_1340_4eea_ae28_8eb0f2f1189b, &v293);
      }
      sub_1803FA270(&v302, v293);
      MsoCF::CIPtr<Jot::IGraphSpace,Jot::IGraphSpace>::Release(v293);
      v258 = v302;
      if ( v302 )
      {
        Jot::CGraphLock::CGraphLock((Jot::CGraphLock *)v307, v302, 0x3FFFu);
        *(_QWORD *)&Buf1 = v302;
        MsoCF::IPropertySet::CEntryBase<Jot::PropertySpace_Jot14::prtidLastSynchedRevisionKnowledge,MsoCF::CIPtr<MsoCF::IAtom,MsoCF::IAtom>>::Remove(&Buf1);
        Jot::CGraphLock::~CGraphLock((Jot::CGraphLock *)v307);
        v258 = v302;
      }
      MsoCF::CIPtr<OneNote::ProgressUI::IProgress,OneNote::ProgressUI::IProgress>::Release(v258);
    }
    v259 = (void (__fastcall *)(Jot::RevisionTimeLogger **, _OWORD *))*((_QWORD *)*this + 12);
    v314[0] = 0;
    __ExceptionPtrCopy(v314, &v312);
    v259(this, v314);
    __ExceptionPtrDestroy(&v312);
    goto LABEL_26;
  }
  v174 = (void (__fastcall *)(Jot::RevisionTimeLogger **, __int64))*((_QWORD *)*this + 12);
  v175 = Jot::ErrNativeReplicator_ReplicationNotAllowed::ErrNativeReplicator_ReplicationNotAllowed(v315, 17065681);
  v176 = std::make_exception_ptr<Jot::ErrNativeReplicator_ReplicationNotAllowed>(&v312, v175);
  v174(this, v176);
LABEL_80:
  if ( v294 )
    (*(void (__fastcall **)(struct Jot::IGraphNode *))(*(_QWORD *)v294 + 16LL))(v294);
}

```

## disassembly

```asm
0x180206900  mov     rax, rsp
0x180206903  mov     [rax+18h], rbx
0x180206907  mov     [rax+20h], rsi
0x18020690b  push    rdi
0x18020690c  push    r12
0x18020690e  push    r13
0x180206910  push    r14
0x180206912  push    r15
0x180206914  sub     rsp, 430h
0x18020691b  movaps  xmmword ptr [rax-38h], xmm6
0x18020691f  movaps  xmmword ptr [rax-48h], xmm7
0x180206923  movaps  xmmword ptr [rax-58h], xmm8
0x180206928  movaps  xmmword ptr [rax-68h], xmm9
0x18020692d  mov     rax, cs:__security_cookie
0x180206934  xor     rax, rsp
0x180206937  mov     [rsp+458h+var_78], rax
0x18020693f  mov     rsi, rdx
0x180206942  mov     [rsp+458h+var_3A0], rdx
0x18020694a  mov     r13, rcx
0x18020694d  mov     [rsp+458h+var_3E0], rcx
0x180206952  xor     r12d, r12d
0x180206955  mov     dword ptr [rsp+458h+var_400], r12d
0x18020695a  mov     r14, [rcx+190h]
0x180206961  mov     [rsp+458h+var_3B8], r14
0x180206969  test    r14, r14
0x18020696c  jz      loc_1802088A7
0x180206972  call    ?GetOneNoteDotComNetworkStatusInstance@Jot@@YAAEAVCNetworkStatus@1@XZ; Jot::GetOneNoteDotComNetworkStatusInstance(void)
0x180206977  mov     rdx, rax
0x18020697a  mov     rcx, [rax]
0x18020697d  mov     rax, [rcx]
0x180206980  mov     rcx, rdx
0x180206983  call    cs:__guard_dispatch_icall_fptr
0x180206989  mov     ecx, [rax+58h]
0x18020698c  dec     ecx; this
0x18020698e  lea     r15d, [r12+1]
0x180206993  cmp     ecx, r15d
0x180206996  jbe     loc_180208910
0x18020699c  mov     rax, [r14]
0x18020699f  mov     rcx, r14
0x1802069a2  mov     rax, [rax+40h]
0x1802069a6  call    cs:__guard_dispatch_icall_fptr
0x1802069ac  mov     [rsp+458h+var_408], r12
0x1802069b1  lea     rbx, ?QueryInterface@?$CJotComObjectForMakeComObject@VCRootGraphSpace@Jot@@@MsoCF@@UEAAJAEBU_GUID@@PEAPEAX@Z; MsoCF::CJotComObjectForMakeComObject<Jot::CRootGraphSpace>::QueryInterface(_GUID const &,void * *)
0x1802069b8  test    rax, rax
0x1802069bb  jz      short loc_1802069E1
0x1802069bd  mov     rcx, [rax]
0x1802069c0  mov     r9, [rcx]
0x1802069c3  lea     r8, [rsp+458h+var_408]
0x1802069c8  lea     rdx, _GUID_6975ccb9_037d_4258_ab28_9d6185f7ba75
0x1802069cf  mov     rcx, rax
0x1802069d2  cmp     r9, rbx
0x1802069d5  jnz     loc_180206BF6
0x1802069db  call    ?QueryInterface@?$CJotComObjectForMakeComObject@VCRootGraphSpace@Jot@@@MsoCF@@UEAAJAEBU_GUID@@PEAPEAX@Z; MsoCF::CJotComObjectForMakeComObject<Jot::CRootGraphSpace>::QueryInterface(_GUID const &,void * *)
0x1802069e0  nop
0x1802069e1  cmp     [rsp+458h+var_408], r12
0x1802069e6  jz      loc_180208444
0x1802069ec  mov     eax, [rsi]
0x1802069ee  cmp     eax, 14h
0x1802069f1  ja      loc_180206B3B
0x1802069f7  jz      loc_180208EE9
0x1802069fd  cmp     eax, 0Fh
0x180206a00  ja      loc_180206F8C
0x180206a06  jz      loc_180208619
0x180206a0c  mov     edi, 0Ah
0x180206a11  sub     eax, edi
0x180206a13  jnz     loc_180206B6F
0x180206a19  mov     rax, [r14]
0x180206a1c  mov     rcx, r14
0x180206a1f  mov     rax, [rax+40h]
0x180206a23  call    cs:__guard_dispatch_icall_fptr
0x180206a29  mov     [rsp+458h+var_3F8], r12
0x180206a2e  test    rax, rax
0x180206a31  jz      short loc_180206A57
0x180206a33  mov     rcx, [rax]
0x180206a36  mov     r9, [rcx]
0x180206a39  lea     r8, [rsp+458h+var_3F8]
0x180206a3e  lea     rdx, _GUID_6975ccb9_037d_4258_ab28_9d6185f7ba75
0x180206a45  mov     rcx, rax
0x180206a48  cmp     r9, rbx
0x180206a4b  jnz     loc_180207310
0x180206a51  call    ?QueryInterface@?$CJotComObjectForMakeComObject@VCRootGraphSpace@Jot@@@MsoCF@@UEAAJAEBU_GUID@@PEAPEAX@Z; MsoCF::CJotComObjectForMakeComObject<Jot::CRootGraphSpace>::QueryInterface(_GUID const &,void * *)
0x180206a56  nop
0x180206a57  mov     rcx, [r14+0C8h]
0x180206a5e  mov     rax, [rcx]
0x180206a61  mov     rax, [rax+78h]
0x180206a65  call    cs:__guard_dispatch_icall_fptr
0x180206a6b  test    rax, rax
0x180206a6e  jz      loc_180206CED
0x180206a74  lea     rax, [r14+118h]
0x180206a7b  cmp     [rax], r12
0x180206a7e  jnz     loc_1802072E3
0x180206a84  lea     rdx, [r13+108h]
0x180206a8b  mov     rcx, rax
0x180206a8e  call    ?Assign@?$CIPtr@UICellStorage@CsiCell@@U12@@MsoCF@@QEAAXPEAUICellStorage@CsiCell@@@Z; MsoCF::CIPtr<CsiCell::ICellStorage,CsiCell::ICellStorage>::Assign(CsiCell::ICellStorage *)
0x180206a93  mov     [r13+1F0h], r12
0x180206a9a  cmp     [r14+134h], r12d
0x180206aa1  jnz     loc_1802075D7
0x180206aa7  mov     rcx, [r14+0C8h]
0x180206aae  mov     rax, [rcx]
0x180206ab1  mov     rax, [rax+78h]
0x180206ab5  call    cs:__guard_dispatch_icall_fptr
0x180206abb  test    rax, rax
0x180206abe  jnz     loc_180208B51
0x180206ac4  cmp     [r13+199h], r12b
0x180206acb  jnz     loc_1802071C0
0x180206ad1  mov     dword ptr [rsi], 0Eh
0x180206ad7  mov     rcx, [rsp+458h+var_3F8]
0x180206adc  test    rcx, rcx
0x180206adf  jz      short loc_180206AF0
0x180206ae1  mov     rax, [rcx]
0x180206ae4  mov     rax, [rax+10h]
0x180206ae8  call    cs:__guard_dispatch_icall_fptr
0x180206aee  nop
0x180206aef  nop
0x180206af0  mov     rcx, [rsp+458h+var_408]
0x180206af5  call    ?Release@?$CIPtr@UIProgress@ProgressUI@OneNote@@U123@@MsoCF@@CAXPEAUIProgress@ProgressUI@OneNote@@@Z; MsoCF::CIPtr<OneNote::ProgressUI::IProgress,OneNote::ProgressUI::IProgress>::Release(OneNote::ProgressUI::IProgress *)
0x180206afa  mov     rcx, [rsp+458h+var_78]
0x180206b02  xor     rcx, rsp; StackCookie
0x180206b05  call    __security_check_cookie
0x180206b0a  lea     r11, [rsp+458h+var_28]
0x180206b12  mov     rbx, [r11+40h]
0x180206b16  mov     rsi, [r11+48h]
0x180206b1a  movaps  xmm6, xmmword ptr [r11-10h]
0x180206b1f  movaps  xmm7, xmmword ptr [r11-20h]
0x180206b24  movaps  xmm8, xmmword ptr [r11-30h]
0x180206b29  movaps  xmm9, xmmword ptr [r11-40h]
0x180206b2e  mov     rsp, r11
0x180206b31  pop     r15
0x180206b33  pop     r14
0x180206b35  pop     r13
0x180206b37  pop     r12
0x180206b39  pop     rdi
0x180206b3a  retn
0x180206b3b  cmp     eax, 1Ah
0x180206b3e  jbe     loc_180206C49
0x180206b44  sub     eax, 1Bh
0x180206b47  jnz     loc_180206C04
0x180206b4d  cmp     [r13+198h], r12b
0x180206b54  jnz     loc_180206C8E
0x180206b5a  cmp     [r13+19Bh], r12b
0x180206b61  jnz     loc_180206C8E
0x180206b67  mov     dword ptr [rsi], 1Dh
0x180206b6d  jmp     short loc_180206AF0
0x180206b6f  sub     eax, 1
0x180206b72  jz      loc_180208A17
0x180206b78  sub     eax, 1
0x180206b7b  jz      loc_180207112
0x180206b81  sub     eax, 1
0x180206b84  jz      loc_18020891F
0x180206b8a  cmp     eax, 1
0x180206b8d  jnz     loc_180206AF0
0x180206b93  mov     rax, [r14]
0x180206b96  mov     rcx, r14
0x180206b99  mov     rax, [rax+40h]
0x180206b9d  call    cs:__guard_dispatch_icall_fptr
0x180206ba3  lea     rdx, [rsp+458h+var_3C8]
0x180206bab  mov     rcx, rax
0x180206bae  call    ?GetBackingRevisionStore@IGraphSpace@Jot@@QEAA?AV?$CIPtr@UICacheRevisionStore@Jot@@U12@@MsoCF@@XZ; Jot::IGraphSpace::GetBackingRevisionStore(void)
0x180206bb3  mov     rdx, rax
0x180206bb6  lea     rcx, [r13+1D0h]
0x180206bbd  call    ??$?4UIObjectSpaceStoreOnCellStorage@Jot@@U01@@?$CIPtr@UIServerStore@Jot@@U12@@MsoCF@@QEAAAEAV01@$$QEAV?$CIPtr@UIObjectSpaceStoreOnCellStorage@Jot@@U12@@1@@Z; MsoCF::CIPtr<Jot::IServerStore,Jot::IServerStore>::operator=<Jot::IObjectSpaceStoreOnCellStorage,Jot::IObjectSpaceStoreOnCellStorage>(MsoCF::CIPtr<Jot::IObjectSpaceStoreOnCellStorage,Jot::IObjectSpaceStoreOnCellStorage> &&)
0x180206bc2  nop
0x180206bc3  mov     rcx, [rsp+458h+var_3C8]
0x180206bcb  test    rcx, rcx
0x180206bce  jz      short loc_180206BDE
0x180206bd0  mov     rax, [rcx]
0x180206bd3  mov     rax, [rax+8]
0x180206bd7  call    cs:__guard_dispatch_icall_fptr
0x180206bdd  nop
0x180206bde  cmp     [r13+1D0h], r12
0x180206be5  jz      loc_180208255
0x180206beb  mov     dword ptr [rsi], 0Ch
0x180206bf1  jmp     loc_180206AF0
0x180206bf6  mov     rax, r9
0x180206bf9  call    cs:__guard_dispatch_icall_fptr
0x180206bff  jmp     loc_1802069E1
0x180206c04  sub     eax, 1
0x180206c07  jz      loc_180207403
0x180206c0d  sub     eax, 1
0x180206c10  jnz     loc_180207660
0x180206c16  lea     rbx, [r13+208h]
0x180206c1d  mov     rcx, [rbx]
0x180206c20  test    rcx, rcx
0x180206c23  jnz     loc_1802081A8
0x180206c29  cmp     [r13+200h], r12d
0x180206c30  jnz     loc_18020731E
0x180206c36  mov     rax, [rsp+458h+var_3A0]
0x180206c3e  mov     dword ptr [rax], 1Eh
0x180206c44  jmp     loc_180206AF0
0x180206c49  jz      loc_18020792D
0x180206c4f  sub     eax, 15h
0x180206c52  jz      loc_1802094B6
0x180206c58  sub     eax, 1
0x180206c5b  jz      loc_1802073B4
0x180206c61  sub     eax, 1
0x180206c64  jz      loc_180207705
0x180206c6a  sub     eax, 1
0x180206c6d  jnz     loc_180207C78
0x180206c73  mov     rcx, [r13+1A0h]
0x180206c7a  test    rcx, rcx
0x180206c7d  jnz     loc_180207B41
0x180206c83  mov     dword ptr [rsi], 19h
0x180206c89  jmp     loc_180206AF0
0x180206c8e  mov     rcx, [r14+0C8h]
0x180206c95  mov     rax, [rcx]
0x180206c98  mov     rax, [rax+78h]
0x180206c9c  call    cs:__guard_dispatch_icall_fptr
0x180206ca2  mov     r8, rax
0x180206ca5  test    rax, rax
0x180206ca8  jnz     loc_180208233
0x180206cae  mov     [rsp+458h+var_3E0], r12
0x180206cb3  mov     rax, r12
0x180206cb6  mov     ebx, 420h
0x180206cbb  test    rax, rax
0x180206cbe  jnz     loc_180209BF5
0x180206cc4  mov     dil, r12b
0x180206cc7  test    bl, 40h
0x180206cca  jnz     loc_180209C53
0x180206cd0  test    bl, 20h
0x180206cd3  jnz     loc_1802076E5
0x180206cd9  test    dil, dil
0x180206cdc  jnz     loc_180209C76
0x180206ce2  mov     dword ptr [rsi], 1Ch
0x180206ce8  jmp     loc_180206AF0
0x180206ced  mov     rcx, [r14+0C8h]
0x180206cf4  mov     rax, [rcx]
0x180206cf7  mov     rax, [rax+70h]
0x180206cfb  call    cs:__guard_dispatch_icall_fptr
0x180206d01  test    rax, rax
0x180206d04  jz      loc_180206A74
0x180206d0a  mov     rcx, [r14+0C8h]
0x180206d11  mov     rax, [rcx]
0x180206d14  mov     rax, [rax+70h]
0x180206d18  call    cs:__guard_dispatch_icall_fptr
0x180206d1e  mov     rdx, rax
0x180206d21  mov     rcx, [rax]
0x180206d24  mov     rax, [rcx+88h]
0x180206d2b  mov     rcx, rdx
0x180206d2e  call    cs:__guard_dispatch_icall_fptr
0x180206d34  test    rax, rax
0x180206d37  jz      loc_180206A74
0x180206d3d  mov     rcx, [r14+0C8h]
0x180206d44  mov     rax, [rcx]
0x180206d47  mov     rax, [rax+70h]
0x180206d4b  call    cs:__guard_dispatch_icall_fptr
0x180206d51  mov     rdx, rax
0x180206d54  mov     rcx, [rax]
0x180206d57  mov     rax, [rcx+88h]
0x180206d5e  mov     rcx, rdx
0x180206d61  call    cs:__guard_dispatch_icall_fptr
0x180206d67  mov     r8, rax
0x180206d6a  mov     rcx, [rax]
0x180206d6d  mov     rax, [rcx+0D0h]
0x180206d74  lea     rdx, [rsp+458h+var_3F0]
0x180206d79  mov     rcx, r8
0x180206d7c  call    cs:__guard_dispatch_icall_fptr
0x180206d82  nop
0x180206d83  mov     rax, r12
0x180206d86  mov     [rsp+458h+var_3E0], rax
0x180206d8b  mov     rcx, [rsp+458h+var_3F0]
0x180206d90  test    rcx, rcx
0x180206d93  jz      loc_1802076F4
0x180206d99  mov     rax, [rcx]
0x180206d9c  lea     r8, [rsp+458h+var_3E0]
0x180206da1  lea     rdx, _GUID_9f7ae2e4_9cb0_45c1_9e5a_95fdd6d001ee
0x180206da8  mov     rax, [rax]
0x180206dab  call    cs:__guard_dispatch_icall_fptr
0x180206db1  mov     rax, [rsp+458h+var_3E0]
0x180206db6  mov     rcx, [rsp+458h+var_3F0]
0x180206dbb  test    rax, rax
0x180206dbe  mov     bl, r15b
0x180206dc1  jz      loc_1802076F4
0x180206dc7  mov     rcx, [rax]
0x180206dca  mov     rdx, [rcx+10h]
0x180206dce  mov     rcx, rax
0x180206dd1  mov     rax, rdx
0x180206dd4  call    cs:__guard_dispatch_icall_fptr
0x180206dda  mov     rcx, [rsp+458h+var_3F0]
0x180206ddf  test    bl, bl
0x180206de1  jnz     loc_180207968
0x180206de7  xorps   xmm0, xmm0
0x180206dea  movups  [rsp+458h+var_310], xmm0
0x180206df2  movdqa  xmm9, cs:__xmm@00000000000000070000000000000000
0x180206dfb  movdqu  [rsp+458h+var_300], xmm9
0x180206e05  mov     word ptr [rsp+458h+var_310], r12w
0x180206e0e  movups  xmm8, [rsp+458h+var_310]
0x180206e17  movups  [rsp+458h+var_2F0], xmm8
0x180206e20  movups  [rsp+458h+var_2E0], xmm9
0x180206e29  lea     rcx, [rsp+458h+var_310]; void *
0x180206e31  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180206e36  lea     rdx, [r14+50h]
0x180206e3a  lea     rcx, [rsp+458h+var_398]
0x180206e42  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180206e47  movups  xmm6, xmmword ptr [rax]
0x180206e4a  movups  [rsp+458h+var_310], xmm6
0x180206e52  movups  xmm7, xmmword ptr [rax+10h]
0x180206e56  movups  [rsp+458h+var_300], xmm7
0x180206e5e  mov     [rax], r12w
0x180206e62  mov     [rax+10h], r12
0x180206e66  mov     qword ptr [rax+18h], 7
  ... truncated ...
```
