# Microsoft::Basix::Dct::SmilesV3::OnDataReceived(std::shared_ptr<Microsoft::Basix::Dct::IAsyncTransport::InBuffer> const &,std::weak_ptr<Microsoft::Basix::Dct::LinkDataV3>)

- ea: `0x18026da30`
- end: `0x180273931`
- name: `?OnDataReceived@SmilesV3@Dct@Basix@Microsoft@@UEAAXAEBV?$shared_ptr@VInBuffer@IAsyncTransport@Dct@Basix@Microsoft@@@std@@V?$weak_ptr@VLinkDataV3@Dct@Basix@Microsoft@@@6@@Z`
- size: `24321`
- prototype: `void __fastcall(size_t, _QWORD *, __int64)`
- caller_count: `0`
- callee_count: `118`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180008f80`
- `0x180010a60`
- `0x1800111fc`
- `0x180015bb8`
- `0x180017338`
- `0x180017380`
- `0x180018b94`
- `0x180018d1c`
- `0x18001902c`
- `0x1800191b4`
- `0x18001979c`
- `0x18001a208`
- `0x18001ab4c`
- `0x18001acb8`
- `0x18001ae64`
- `0x18001bbdc`
- `0x18001bed4`
- `0x18001dad8`
- `0x18001db78`
- `0x180024700`
- `0x180024760`
- `0x180028100`
- `0x180029b34`
- `0x18002a8f4`
- `0x1800334a8`
- `0x18003da74`
- `0x18003f0f4`
- `0x18004e1dc`
- `0x1800bb210`
- `0x1800bee54`
- `0x1800c3524`
- `0x1800c3bc8`
- `0x1800c4238`
- `0x1800d34ac`
- `0x1800d3af0`
- `0x1800d621c`
- `0x1800d65f4`
- `0x18010587c`
- `0x180105cb0`
- `0x18012b8f0`
- `0x18015b234`
- `0x1801825a8`
- `0x1801b3cbc`
- `0x1801b408c`
- `0x1801cda84`
- `0x1801d43a4`
- `0x1801d7308`
- `0x1801fe67c`
- `0x180223b60`
- `0x18024774c`

## string_xrefs

- `0x1802712d2`: `LinkSwitch`
- `0x18027154d`: `LinkSwitch`
- `0x180271fa2`: `LinkSwitch`
- `0x180272766`: `LinkSwitch`
- `0x180272899`: `LinkSwitch`
- `0x1802729f8`: `LinkSwitch`
- `0x180272b34`: `LinkSwitch`
- `0x180272d12`: `LinkSwitch`
- `0x18026db87`: `SmilesV3: Location %d m_primaryOutLink == nullptr`
- `0x18026dfc2`: `SmilesV3: Location %d m_primaryOutLink == nullptr`
- `0x18026ec82`: `SmilesV3: Location %d m_primaryOutLink == nullptr`
- `0x18026f12c`: `SmilesV3: Location %d m_primaryOutLink == nullptr`
- `0x18026fd0a`: `SmilesV3: Location %d m_primaryOutLink == nullptr`
- `0x1802710d1`: `SmilesV3: Location %d m_primaryOutLink == nullptr`
- `0x1802719bd`: `SmilesV3: Location %d m_primaryOutLink == nullptr`
- `0x180271db6`: `SmilesV3: Location %d m_primaryOutLink == nullptr`
- `0x1802722ae`: `SmilesV3: Location %d m_primaryOutLink == nullptr`
- `0x180272e55`: `SmilesV3: Location %d m_primaryOutLink == nullptr`
- `0x180273256`: `SmilesV3: Location %d m_primaryOutLink == nullptr`
- `0x1802734f8`: `SmilesV3: Location %d m_primaryOutLink == nullptr`
- `0x18026dcad`: `TestPrimaryOutLinkNull`
- `0x18026e0e2`: `TestPrimaryOutLinkNull`
- `0x18026eda6`: `TestPrimaryOutLinkNull`
- `0x18026f258`: `TestPrimaryOutLinkNull`
- `0x18026fe36`: `TestPrimaryOutLinkNull`
- `0x1802711f1`: `TestPrimaryOutLinkNull`
- `0x180271ae3`: `TestPrimaryOutLinkNull`
- `0x180271ed6`: `TestPrimaryOutLinkNull`
- `0x1802723d3`: `TestPrimaryOutLinkNull`
- `0x180272f7b`: `TestPrimaryOutLinkNull`
- `0x1802733af`: `TestPrimaryOutLinkNull`
- `0x180273651`: `TestPrimaryOutLinkNull`
- `0x18026f9a2`: `linkSwitch`
- `0x180270119`: `NewLinkId`
- `0x180270a5d`: `NewLinkId`
- `0x1802701c7`: `OldLinkId`
- `0x180270b17`: `OldLinkId`
- `0x18026de60`: `Initial primaryInLink OnDataReceived`
- `0x18026e29b`: `SmilesV3::OnDataReceived() CLOCK_OFFSET: linkId=%d, peerClockOffsetInMs=%d, finalClockOffset=%d`
- `0x18026e3b7`: `SmilesV3::OnDataReceived() SYNC_EX: linkId=%d, peerLinkId=%d, cntSendsInLastNMs=%d, delay=%d`
- `0x18026e50b`: `SmilesV3::OnDataReceived() INFORM_PEER_SWITCHINFO_EX: linkId=%d, switchInfo.reason=%d, contextCnt=%d`
- `0x1802738cb`: `received INFORM_PEER_OPERATION_EX when sideband is used`
- `0x18026e64f`: `SmilesV3::OnDataReceived() INFORM_PEER_PRIMARY_LINKID_EX: currentLinkId=%d, newOutPrimaryLinkId=%d`
- `0x18026e733`: `SmilesV3::OnDataReceived() INFORM_PEER_PRIMARY_EPOCH_EX: currentLinkId=%d, epoch=%d, m_currentSwitchEpoch=%d`
- `0x18026e7d6`: `SmilesV3 extension header corrupted! drop the packet`
- `0x18026eb2a`: `SmilesV3:  link(%d)%p unsuspend now`
- `0x18026ebe5`: `SmilesV3:  link(%d)%p unsuspend pending count %d`
- `0x18026ef83`: `SmilesV3::OnDataReceived: received packet(size=%d) with counter(%d) on link(%d), delay(%f), minDelay=%f, %s codedSendTime(%d), sendTimeInMs(%llu), receiveTimeInMs(%llu), clockoffset=%d`
- `0x18026f450`: `SmilesV3: primaryOutLink from InformPeerPrimaryLinkId doesn't exist in m_links: id=(%d)`
- `0x18026f4ed`: `SmilesV3: primaryOutLink from InformPeerPrimaryLinkId has different epoch(%d), m_currentSwitchEpoch(%d)`
- `0x18026f561`: `SmilesV3: primaryOutLink from InformPeerPrimaryLinkId has first time different epoch(%d), m_currentSwitchEpoch(%d)`
- `0x18026f5e5`: `SmilesV3: received same primaryOutLinkId(%d) from InformPeerPrimaryLinkId, ignore`
- `0x18026f702`: `SmilesV3: primaryOutLink switching from link (%d, '%s') to link (%d, '%s')`
- `0x18026f847`: `SmilesV3: primaryOutLink switching from null link to link (%d, '%s')`
- `0x18026f894`: `Initial primaryOutLink Set in OnDataReceived`
- `0x18026fc65`: `SmilesV3: WARNING: m_primaryOutLink doesn't have minimal delay: primaryLinkId=%d, minDelayLinkId=%d, primaryLinkDelay=%f, minLinkDelay=%f`
- `0x180270038`: `SmilesV3: peer has just switched its outPrimary Link from link (%d) to link (%d)`
- `0x180270983`: `SmilesV3: peer has just switched its outPrimary Link from link (%d) to link (%d)`
- `0x180270344`: `LinkSwitchConfirmed`
- `0x180270c85`: `LinkSwitchConfirmed`
- `0x1802704d5`: `SmilesV3: peer has just set its outPrimary link to link (%d) for the first time`
- `0x180270e18`: `SmilesV3: peer has just set its outPrimary link to link (%d) for the first time`
- `0x18027060c`: `SmilesV3: the link the peer switched to (%d) does not match with what is intended(%d), force unblocking the markSwitch with epoch(%d)`
- `0x1802706f7`: `SmilesV3: m_switchInfo is set for too long (%dms) before a valid linkSwitchConfirmation, force to unblock MarkSwitch (to(%d), epoch(%d))`
- `0x180270ecc`: `SmilesV3: peer has just switched to a link with Id (%d) which is different from the linkId intended(%d)`
- `0x1802713b1`: `ExpiredCounter:%lld,linkId:%d(%s),IsPrimary:(%s),delay:%d`
- `0x18027145c`: `SmilesV3: on link(%d) received sync with older counter(%d), compared to the current sync counter(%d), ignore`
- `0x18027162c`: `SameCounter:%lld,linkId:%d(%s),IsPrimary:(%s),delay:%d`
- `0x1802716ed`: `SmilesV3: on peer-primary link(%d) received sync with same current counter(%d)`
- `0x1802718df`: `SmilesV3: would be timer not off, stay on the primary link(%d). already delayedCount=%d `
- `0x180271c21`: `SmilesV3: on peer-secondary link(%d) received sync with same current counter(%d)`
- `0x180271cb4`: `SmilesV3: received packets for the secondary link before primary link packets were ever received. Mark switching peer primary link to this link (%d) `
- `0x180272087`: `NewCounter:%lld,linkId:%d(%s),IsPrimary:(%s),delay:%d`
- `0x180272165`: `SmilesV3:  peer-primary link(%d) receives new sync counter(%d)`
- `0x1802721eb`: `SmilesV3: peer-secondary link(%d) receives new sync counter(%d)`
- `0x180272553`: `SmilesV3: attempting markSwitch due to primary link gap is too big: peer-secondary link(%d) receives new sync counter(%d), `
- `0x180272704`: `SmilesV3: primary link gap is too big. switch immediately and putting the current primaryInLink(%d) into suspended state: counterGap(%d), counterReceived(%d), lastPrimaryCounterReceived(%d)`
- `0x180272824`: `linkid:%lld,linkId:%d(%s),IsPrimary:(%s),SmilesV3: primary link gap is too big. switch immediately `
- `0x180272911`: `SmilesV3: primary link is tardy for a consecutive %d times, switch now`
- `0x180272ac4`: `linkid:%lld,linkId:%d(%s),IsPrimary:(%s),primary link is tardy for a consecutive %d times - switch now `
- `0x180272c76`: `SmilesV3: Set timer: finalTimeoutInMs(%d), timeoutInMs(%d), timeoutAdjustment(%f), adjustedTimeoutInMs(%d), now(%lld), receivedSendTime(%lld), PeerPrimaryLinkAveVar(%f), currentlinkAveVar(%f)`
- `0x180272da0`: `WouldbeTimerStart:%lld,linkId:%d(%s),finalTimeoutInMs:%d`

## pseudocode

```c
void __fastcall Microsoft::Basix::Dct::SmilesV3::OnDataReceived(size_t a1, _QWORD *a2, __int64 a3)
{
  _QWORD *v4; // rbx
  size_t v5; // r13
  __int64 v6; // rdx
  volatile signed __int32 *v7; // rcx
  bool v8; // zf
  int v9; // r8d
  __int64 v10; // rdi
  __int64 v11; // rbx
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rdx
  __int64 v15; // rdx
  __int64 v16; // rdx
  __m128i v17; // xmm10
  size_t CurrentTimeInMsFromBase; // rax
  double v19; // xmm9_8
  double v20; // xmm8_8
  Microsoft::Basix::Instrumentation::DelayedTraceManager::DelayedTraceRecord **v21; // rsi
  __int64 v22; // r14
  __m128i v23; // xmm12
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // rax
  int v27; // r8d
  __int64 v28; // rdi
  __int64 v29; // rbx
  __int64 v30; // rax
  __int64 v31; // rax
  __int64 v32; // rdx
  __int64 v33; // rdx
  __int64 v34; // rdx
  Microsoft::Basix::Dct::LinkDataV3 *v35; // r15
  unsigned __int64 v36; // rdi
  __int64 v37; // rax
  __int64 v38; // rax
  __int64 v39; // rax
  __int64 v40; // rax
  double v41; // xmm6_8
  char v42; // r14
  double v43; // xmm6_8
  int v44; // r8d
  int v45; // r9d
  int v46; // ebx
  __int64 v47; // rax
  __int64 v48; // rax
  __int64 v49; // rax
  int v50; // r8d
  int v51; // r9d
  char v52; // bl
  __int16 v53; // r14
  int v54; // r15d
  __int64 v55; // rax
  __int64 v56; // rax
  __int64 v57; // rbx
  _QWORD *v58; // r14
  __int64 v59; // rax
  int v60; // r8d
  int v61; // r9d
  __int64 v62; // r14
  int v63; // ebx
  _QWORD *v64; // r14
  __int64 v65; // rax
  __int64 v66; // rax
  unsigned __int64 v67; // rcx
  bool v68; // cc
  __int64 v69; // rax
  int v70; // r8d
  int v71; // r9d
  int v72; // ebx
  __int64 v73; // rax
  int v74; // r8d
  int v75; // r9d
  int v76; // ebx
  int v77; // r14d
  __int64 v78; // rax
  char *v79; // rbx
  const struct std::nothrow_t *v80; // rdx
  const char *v81; // rcx
  char v82; // di
  __int64 v83; // rax
  bool v84; // al
  int v85; // r8d
  const void *v86; // r9
  int v87; // ebx
  __int64 v88; // rdx
  int v89; // r8d
  const void *v90; // r9
  int v91; // ebx
  int v92; // r14d
  int v93; // r8d
  __int64 v94; // r14
  __int64 v95; // rbx
  __int64 v96; // rax
  __int64 v97; // rax
  __int64 v98; // rdx
  __int64 v99; // rdx
  __int64 v100; // rdx
  size_t *v101; // rcx
  size_t v102; // rax
  __int64 v103; // rbx
  double v104; // xmm0_8
  double v105; // xmm9_8
  double v106; // xmm13_8
  double v107; // xmm7_8
  double MinDelayIn; // xmm0_8
  int v109; // r14d
  __int64 v110; // rax
  __int64 v111; // rbx
  int v112; // r8d
  int v113; // r9d
  const char *v114; // rcx
  unsigned __int64 v115; // rax
  unsigned __int64 v116; // r14
  bool ShouldSendLinkUpdate; // al
  __int64 v118; // rbx
  _QWORD *v119; // rdx
  unsigned __int64 v120; // r8
  int v121; // r8d
  __int64 v122; // r14
  __int64 v123; // rbx
  __int64 v124; // rax
  __int64 v125; // rax
  __int64 v126; // rdx
  __int64 v127; // rdx
  __int64 v128; // rdx
  __m128i si128; // xmm6
  int v130; // ebx
  char *v131; // rdx
  __int64 v133; // rdx
  char v134; // al
  char *v135; // r14
  int v136; // r8d
  int v137; // r8d
  int v138; // r9d
  int v139; // ebx
  int v140; // r14d
  int v141; // r8d
  int v142; // r9d
  int v143; // ebx
  int v144; // r14d
  int v145; // r8d
  _QWORD *v146; // rax
  __int64 v147; // r12
  int v148; // r15d
  __int64 v149; // r14
  int v150; // ebx
  int v151; // r8d
  const char *v152; // r9
  __m128i *v153; // rcx
  __int64 v154; // rax
  __int64 v155; // rax
  __int64 *v156; // rcx
  __int64 v157; // r14
  int v158; // ebx
  int v159; // r8d
  const char *v160; // r9
  __int64 v161; // rax
  int v162; // ecx
  Microsoft::Basix::Dct::LinkDataV3 *v163; // rdx
  __m256i *v164; // rax
  char v165; // bl
  __int64 v166; // rax
  int v167; // eax
  char v168; // bl
  double AveDelayOut; // xmm7_8
  double v170; // xmm0_8
  Microsoft::Basix::Dct::LinkDataV3 **v171; // r14
  __int64 v172; // rbx
  __int64 v174; // rbx
  Microsoft::Basix::Dct::LinkDataV3 **v175; // rbx
  __int64 v176; // r14
  double v177; // xmm0_8
  int v178; // r14d
  int v179; // ebx
  int v180; // r8d
  int v181; // r9d
  int v182; // r8d
  __int64 v183; // r14
  __int64 v184; // rbx
  __int64 v185; // rax
  __int64 v186; // rax
  __int64 v187; // rdx
  __int64 v188; // rdx
  __int64 v189; // rdx
  volatile signed __int32 *v190; // rbx
  volatile signed __int32 *v191; // rbx
  unsigned __int64 v192; // rcx
  bool v193; // cc
  size_t v194; // r12
  int v195; // r8d
  int v196; // r9d
  int v197; // ebx
  int v198; // r14d
  __int64 v199; // r14
  __int64 v200; // rbx
  __int64 v201; // rax
  __int64 v202; // rax
  __int64 v203; // rdx
  __int64 v204; // rdx
  __int64 v205; // rdx
  __int64 v206; // r14
  __int64 v207; // rbx
  __int64 v208; // rax
  __int64 v209; // rax
  __int64 v210; // rdx
  __int64 v211; // rdx
  __int64 v212; // rdx
  __int64 v213; // r12
  __int64 v214; // r15
  __int64 v215; // r14
  __int64 v216; // rbx
  __int64 v217; // rax
  __int64 v218; // rax
  __int64 v219; // rdx
  __int64 v220; // rdx
  __int64 v221; // rdx
  __int64 v222; // rax
  __int64 v223; // rdx
  int v224; // r8d
  unsigned int v225; // ebx
  __int64 v226; // r8
  std::_Ref_count_base *v227; // r15
  std::_Ref_count_base *v228; // rax
  int v229; // r8d
  int v230; // r9d
  char v231; // bl
  int v232; // r14d
  __int16 v233; // bx
  __int64 v234; // rbx
  unsigned __int64 v235; // r14
  int v236; // r8d
  int v237; // r9d
  char v238; // bl
  int v239; // r14d
  __int16 v240; // bx
  __int64 v241; // rdx
  __int64 v243; // rdx
  unsigned __int64 v244; // rdx
  bool v245; // cc
  int v246; // r8d
  int v247; // r9d
  __int64 v248; // rbx
  unsigned __int64 v249; // rcx
  bool v250; // cc
  size_t v251; // r12
  int v252; // r8d
  int v253; // r9d
  int v254; // ebx
  int v255; // r14d
  __int64 v256; // r14
  __int64 v257; // rbx
  __int64 v258; // rax
  __int64 v259; // rax
  __int64 v260; // rdx
  __int64 v261; // rdx
  __int64 v262; // rdx
  __int64 v263; // r14
  __int64 v264; // rbx
  __int64 v265; // rax
  __int64 v266; // rax
  __int64 v267; // rdx
  __int64 v268; // rdx
  __int64 v269; // rdx
  __int64 v270; // r12
  __int64 v271; // r15
  __int64 v272; // r14
  __int64 v273; // rbx
  __int64 v274; // rax
  __int64 v275; // rax
  __int64 v276; // rdx
  __int64 v277; // rdx
  __int64 v278; // rdx
  __int64 v279; // rax
  __int64 v280; // rdx
  int v281; // r8d
  unsigned int v282; // ebx
  unsigned __int16 v283; // r14
  unsigned __int16 *v284; // rax
  __int64 v285; // r8
  unsigned __int16 v286; // r14
  unsigned __int16 v287; // tt
  size_t v288; // r12
  int v289; // r8d
  int v290; // r9d
  int v291; // ebx
  __int64 v292; // rdx
  __int64 v294; // rdx
  unsigned __int64 v295; // rcx
  bool v296; // cc
  int v297; // ecx
  char *v298; // rax
  int v299; // r8d
  __int64 v300; // r14
  __int64 v301; // rbx
  __int64 v302; // rax
  __int64 v303; // rax
  __int64 v304; // rdx
  __int64 v305; // rdx
  __int64 v306; // rdx
  unsigned __int64 v307; // rcx
  bool v308; // cc
  __int64 v309; // rbx
  Microsoft::Basix::Instrumentation::DelayedTraceManager::DelayedTraceRecord **DelayedTraceRecord; // r15
  const char *v311; // rbx
  double v312; // xmm6_8
  __int64 v313; // rax
  int v314; // r8d
  int v315; // r9d
  __int64 v316; // rbx
  int v317; // r14d
  volatile signed __int32 *v318; // rbx
  volatile signed __int32 *v319; // rbx
  __int64 v320; // r15
  __int64 v321; // rbx
  Microsoft::Basix::Instrumentation::DelayedTraceManager::DelayedTraceRecord **v322; // r15
  const char *v323; // rbx
  double v324; // xmm6_8
  __int64 v325; // rax
  char v326; // al
  int v327; // r8d
  int v328; // r9d
  int v329; // ebx
  size_t v330; // rbx
  unsigned __int64 v331; // rbx
  __int64 v332; // rax
  int v333; // r8d
  int v334; // r9d
  int v335; // ebx
  int v336; // edi
  int v337; // r8d
  __int64 v338; // rdi
  __int64 v339; // rbx
  __int64 v340; // rax
  __int64 v341; // rax
  __int64 v342; // rdx
  __int64 v343; // rdx
  __int64 v344; // rdx
  volatile signed __int32 *v345; // rbx
  int v346; // r8d
  int v347; // r9d
  int v348; // ebx
  int v349; // r8d
  unsigned int v350; // ebx
  __int64 v351; // rax
  int v352; // r8d
  __int64 v353; // rdi
  __int64 v354; // rbx
  __int64 v355; // rax
  __int64 v356; // rax
  __int64 v357; // rdx
  __int64 v358; // rdx
  __int64 v359; // rdx
  __int64 v360; // rbx
  __int64 v361; // r8
  const char *v362; // r14
  int v363; // esi
  char v364; // al
  const char *v365; // rcx
  const char *v366; // rbx
  Microsoft::Basix::Instrumentation::DelayedTraceManager::DelayedTraceRecord **v367; // r15
  __int64 v368; // rax
  char v369; // al
  int v370; // r8d
  int v371; // r9d
  int v372; // ebx
  std::_Ref_count_base *v373; // rcx
  int v374; // r8d
  int v375; // r9d
  int v376; // ebx
  __int64 v377; // rbx
  __int16 v378; // r15
  int v379; // r8d
  __int64 v380; // r15
  __int64 v381; // r14
  __int64 v382; // rax
  __int64 v383; // rax
  __int64 v384; // rdx
  __int64 v385; // rdx
  __int64 v386; // rdx
  int v387; // r8d
  int v388; // r9d
  int v389; // r14d
  int v390; // r14d
  __int16 *v391; // rdx
  __int16 v392; // ax
  __int64 v393; // rax
  int v394; // r8d
  int v395; // r9d
  int v396; // r14d
  __int64 v397; // rbx
  _QWORD *v398; // rbx
  const char *v399; // rbx
  __int64 v400; // rax
  __int64 v401; // rbx
  __int64 v402; // r8
  int v403; // r8d
  unsigned int v404; // ebx
  __int64 v405; // rax
  __int64 v406; // rbx
  _QWORD *v407; // rbx
  int v408; // ebx
  __int64 v409; // rax
  __int64 v410; // rbx
  __int64 v411; // r8
  double v412; // xmm6_8
  double v413; // xmm0_8
  char v414; // xmm7_1
  double v415; // xmm1_8
  unsigned __int64 v416; // rax
  unsigned __int64 v417; // rsi
  double v418; // xmm9_8
  unsigned __int64 v419; // rax
  double v420; // xmm0_8
  unsigned __int64 v421; // rcx
  unsigned __int64 v422; // r14
  int v423; // r8d
  int v424; // r9d
  __int64 v425; // rbx
  __int64 v426; // rbx
  Microsoft::Basix::Instrumentation::DelayedTraceManager::DelayedTraceRecord **v427; // rsi
  int i; // ebx
  char *v429; // r15
  __int64 v430; // rax
  size_t v431; // r15
  int v432; // r8d
  __int64 v433; // rdi
  __int64 v434; // rbx
  __int64 v435; // rax
  __int64 v436; // rax
  __int64 v437; // rdx
  __int64 v438; // rdx
  __int64 v439; // rdx
  __int64 v440; // rax
  __int64 v441; // rax
  volatile signed __int32 *v442; // r14
  volatile signed __int32 *v443; // rsi
  __int64 v444; // rbx
  int v445; // r8d
  volatile signed __int32 *v446; // rbx
  __int64 v447; // rdi
  __int64 v448; // rbx
  __int64 v449; // rax
  __int64 v450; // rax
  __int64 v451; // rdx
  __int64 v452; // rdx
  __int64 v453; // rdx
  volatile signed __int32 *v454; // rbx
  _QWORD *v455; // rbx
  __int64 v456; // rax
  int v457; // r8d
  volatile signed __int32 *v458; // rbx
  __int64 v459; // rdi
  __int64 v460; // rbx
  __int64 v461; // rax
  __int64 v462; // rax
  __int64 v463; // rdx
  __int64 v464; // rdx
  __int64 v465; // rdx
  volatile signed __int32 *v466; // rdi
  volatile signed __int32 *v467; // rdi
  volatile signed __int32 *v468; // rdi
  int v469; // [rsp+20h] [rbp-E0h]
  char *v470; // [rsp+20h] [rbp-E0h]
  char *Str; // [rsp+28h] [rbp-D8h]
  __int64 v472; // [rsp+30h] [rbp-D0h]
  const char *v473; // [rsp+38h] [rbp-C8h]
  __int64 v474; // [rsp+40h] [rbp-C0h]
  double v475; // [rsp+48h] [rbp-B8h]
  __int64 v476; // [rsp+50h] [rbp-B0h]
  int v477; // [rsp+58h] [rbp-A8h]
  char v478; // [rsp+70h] [rbp-90h] BYREF
  char v479; // [rsp+71h] [rbp-8Fh] BYREF
  char v480; // [rsp+72h] [rbp-8Eh]
  char v481[4]; // [rsp+74h] [rbp-8Ch] BYREF
  unsigned __int8 v482[2]; // [rsp+78h] [rbp-88h] BYREF
  char *Buffer; // [rsp+80h] [rbp-80h] BYREF
  __int64 v484[4]; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int8 v485; // [rsp+A8h] [rbp-58h] BYREF
  char v486; // [rsp+A9h] [rbp-57h]
  int v487; // [rsp+ACh] [rbp-54h] BYREF
  __int64 v488; // [rsp+B0h] [rbp-50h] BYREF
  void *v489; // [rsp+B8h] [rbp-48h]
  __int64 v490; // [rsp+C0h] [rbp-40h]
  char v491; // [rsp+C8h] [rbp-38h]
  bool v492; // [rsp+D0h] [rbp-30h]
  char v493; // [rsp+D1h] [rbp-2Fh]
  int v494; // [rsp+D4h] [rbp-2Ch] BYREF
  int v495; // [rsp+D8h] [rbp-28h] BYREF
  volatile signed __int32 *v496; // [rsp+E0h] [rbp-20h]
  int v497; // [rsp+E8h] [rbp-18h] BYREF
  _QWORD *v498; // [rsp+F0h] [rbp-10h]
  __int64 v499[4]; // [rsp+F8h] [rbp-8h] BYREF
  _Mtx_t v500; // [rsp+118h] [rbp+18h] BYREF
  _BYTE v501[32]; // [rsp+120h] [rbp+20h] BYREF
  __int64 v502[4]; // [rsp+140h] [rbp+40h] BYREF
  __m128i v503; // [rsp+160h] [rbp+60h] BYREF
  std::_Ref_count_base *v504[2]; // [rsp+170h] [rbp+70h] BYREF
  __int64 v505; // [rsp+180h] [rbp+80h]
  char v506; // [rsp+188h] [rbp+88h]
  _OWORD v507[2]; // [rsp+190h] [rbp+90h] BYREF
  _BYTE v508[32]; // [rsp+1B0h] [rbp+B0h] BYREF
  _BYTE v509[32]; // [rsp+1D0h] [rbp+D0h] BYREF
  __int64 v510[4]; // [rsp+1F0h] [rbp+F0h] BYREF
  __int64 v511; // [rsp+210h] [rbp+110h]
  char v512[8]; // [rsp+218h] [rbp+118h] BYREF
  __int128 v513; // [rsp+220h] [rbp+120h] BYREF
  __int64 v514; // [rsp+230h] [rbp+130h]
  __int16 v515; // [rsp+238h] [rbp+138h]
  char v516; // [rsp+23Ah] [rbp+13Ah]
  __int64 v517; // [rsp+240h] [rbp+140h]
  _BYTE v518[32]; // [rsp+248h] [rbp+148h] BYREF
  _BYTE v519[32]; // [rsp+268h] [rbp+168h] BYREF
  _BYTE v520[32]; // [rsp+288h] [rbp+188h] BYREF
  _BYTE v521[32]; // [rsp+2A8h] [rbp+1A8h] BYREF
  _BYTE v522[32]; // [rsp+2C8h] [rbp+1C8h] BYREF
  _BYTE v523[32]; // [rsp+2E8h] [rbp+1E8h] BYREF
  _BYTE v524[32]; // [rsp+308h] [rbp+208h] BYREF
  _BYTE v525[32]; // [rsp+328h] [rbp+228h] BYREF
  _BYTE v526[32]; // [rsp+348h] [rbp+248h] BYREF
  _BYTE v527[32]; // [rsp+368h] [rbp+268h] BYREF
  _BYTE v528[32]; // [rsp+388h] [rbp+288h] BYREF
  _BYTE v529[32]; // [rsp+3A8h] [rbp+2A8h] BYREF
  __int64 v530; // [rsp+3C8h] [rbp+2C8h]
  _BYTE v531[32]; // [rsp+3D0h] [rbp+2D0h] BYREF
  _BYTE v532[128]; // [rsp+3F0h] [rbp+2F0h] BYREF
  __m128i pExceptionObject; // [rsp+470h] [rbp+370h] BYREF
  __int64 v534; // [rsp+480h] [rbp+380h]
  char v535; // [rsp+488h] [rbp+388h]
  void *v536[2]; // [rsp+490h] [rbp+390h] BYREF
  __int64 v537; // [rsp+4A0h] [rbp+3A0h]
  char v538; // [rsp+4A8h] [rbp+3A8h]
  char v539[16]; // [rsp+4B0h] [rbp+3B0h] BYREF
  size_t v540[2]; // [rsp+4C0h] [rbp+3C0h] BYREF
  size_t v541[2]; // [rsp+4D0h] [rbp+3D0h] BYREF
  size_t BufferCount; // [rsp+4E0h] [rbp+3E0h] BYREF
  _OWORD v543[2]; // [rsp+4E8h] [rbp+3E8h] BYREF
  __m128i v544; // [rsp+510h] [rbp+410h] BYREF
  struct std::nothrow_t *v545[2]; // [rsp+520h] [rbp+420h] BYREF
  __int64 v546; // [rsp+530h] [rbp+430h]
  char v547; // [rsp+538h] [rbp+438h]
  size_t v548; // [rsp+540h] [rbp+440h] BYREF
  __m256i v549; // [rsp+548h] [rbp+448h] BYREF
  size_t v550; // [rsp+568h] [rbp+468h] BYREF
  char *v551[2]; // [rsp+570h] [rbp+470h] BYREF
  __int64 v552; // [rsp+580h] [rbp+480h]
  char v553; // [rsp+588h] [rbp+488h]
  char v554[8]; // [rsp+590h] [rbp+490h] BYREF
  __int128 v555; // [rsp+598h] [rbp+498h] BYREF
  __int16 *v556; // [rsp+5A8h] [rbp+4A8h]
  __int16 v557; // [rsp+5B0h] [rbp+4B0h]
  char v558; // [rsp+5B2h] [rbp+4B2h]
  __int64 v559; // [rsp+5B8h] [rbp+4B8h]
  char v560[8]; // [rsp+5C0h] [rbp+4C0h] BYREF
  __int128 v561; // [rsp+5C8h] [rbp+4C8h] BYREF
  __int64 v562; // [rsp+5D8h] [rbp+4D8h]
  __int16 v563; // [rsp+5E0h] [rbp+4E0h]
  char v564; // [rsp+5E2h] [rbp+4E2h]
  __int64 v565; // [rsp+5E8h] [rbp+4E8h]
  unsigned __int8 v566[8]; // [rsp+5F0h] [rbp+4F0h] BYREF
  __int128 v567; // [rsp+5F8h] [rbp+4F8h] BYREF
  __int64 v568; // [rsp+608h] [rbp+508h]
  __int16 v569; // [rsp+610h] [rbp+510h]
  char v570; // [rsp+612h] [rbp+512h]
  __int64 v571; // [rsp+618h] [rbp+518h]
  __int128 v572; // [rsp+620h] [rbp+520h] BYREF
  __int128 v573; // [rsp+630h] [rbp+530h]
  __int128 v574; // [rsp+640h] [rbp+540h] BYREF
  __int128 v575; // [rsp+650h] [rbp+550h]

  v511 = a3;
  v4 = a2;
  v498 = a2;
  v5 = a1;
  v550 = a1;
  v530 = a3;
  v494 = 0;
  LODWORD(v543[0]) = 0;
  v544 = 0;
  std::weak_ptr<Microsoft::Basix::Dct::ICE::IAgentDelegate>::lock(a3, &v544);
  if ( (unsigned __int8)std::operator==<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceCheckpoint>>(
                          &v544,
                          0) )
  {
    std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(&v544);
    v7 = *(volatile signed __int32 **)(a3 + 8);
    if ( !v7 )
      return;
    v8 = _InterlockedExchangeAdd(v7 + 3, 0xFFFFFFFF) == 1;
    goto LABEL_675;
  }
  if ( *(_BYTE *)(v5 + 1524)
    && (unsigned __int8)std::operator==<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceCheckpoint>>(
                          *(_QWORD *)(v5 + 1816),
                          0) )
  {
    *(_OWORD *)v536 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(v536);
    if ( v536[0] && *((_BYTE *)v536[0] + 128) )
    {
      std::string::string(&v488, "SmilesV3: Location %d m_primaryOutLink == nullptr", v9);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,int>(
        v536,
        "BASIX_DCT",
        &v488,
        7);
      std::string::_Tidy_deallocate(&v488);
    }
    std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(v536);
    *(_OWORD *)v536 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceCheckpoint>(v536);
    if ( v536[0] && *((_BYTE *)v536[0] + 128) )
    {
      std::_Integral_to_string<char,int>(&v572, 7);
      v10 = std::string::string(v501, ":");
      v11 = std::string::string(v502, "\"");
      v12 = std::string::string(v499, "\"");
      v13 = std::operator+<char>(v484, v12, "Location");
      LOBYTE(v14) = v478;
      std::string::string(&v549, v14, v13, v11);
      LOBYTE(v15) = v478;
      std::string::string(&v574, v15, &v549, v10);
      LOBYTE(v16) = v478;
      std::string::string(&v488, v16, &v574, &v572);
      Microsoft::Basix::Instrumentation::TraceManager::TraceCheckpointMessage<Microsoft::Basix::TraceCheckpoint,std::string>(
        (int)v536,
        (int)"RD_CHECKPOINT",
        0,
        (int)"Smiles",
        "TestPrimaryOutLinkNull",
        "TestPrimaryOutLinkNull",
        (__int64)&v488);
      std::string::_Tidy_deallocate(&v574);
      std::string::_Tidy_deallocate(&v549);
      std::string::_Tidy_deallocate(v484);
      std::string::_Tidy_deallocate(v499);
      std::string::_Tidy_deallocate(v502);
      std::string::_Tidy_deallocate(v501);
      std::string::_Tidy_deallocate(&v572);
      v4 = v498;
    }
    std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(v536);
  }
  v17 = 0;
  v503 = 0;
  v572 = 0;
  v573 = 0;
  pExceptionObject = 0;
  LOBYTE(v6) = 1;
  Microsoft::Basix::Dct::OperationOnLinkId::OperationOnLinkId(&v572, v6, 0, &pExceptionObject);
  v574 = 0;
  v575 = 0;
  pExceptionObject = 0;
  Microsoft::Basix::Dct::OperationOnLinkId::OperationOnLinkId(&v574, 0, 0, &pExceptionObject);
  v478 = 0;
  v493 = 0;
  CurrentTimeInMsFromBase = Microsoft::Basix::Dct::SmilesV3::GetCurrentTimeInMsFromBase((Microsoft::Basix::Dct::SmilesV3 *)v5);
  BufferCount = CurrentTimeInMsFromBase;
  if ( (CurrentTimeInMsFromBase & 0x8000000000000000uLL) != 0LL )
    v19 = (double)(int)(CurrentTimeInMsFromBase & 1 | (CurrentTimeInMsFromBase >> 1))
        + (double)(int)(CurrentTimeInMsFromBase & 1 | (CurrentTimeInMsFromBase >> 1));
  else
    v19 = (double)(int)CurrentTimeInMsFromBase;
  v20 = v19 * 0.001;
  v486 = 1;
  v480 = 1;
  LODWORD(v21) = -1;
  v548 = 0xFFFFFFFFLL;
  v479 = 0;
  std::lock_guard<std::mutex>::lock_guard<std::mutex>(&v500, v5 + 1832);
  pExceptionObject = 0;
  v22 = v544.m128i_i64[1];
  if ( v544.m128i_i64[1] )
    _InterlockedIncrement((volatile signed __int32 *)(v544.m128i_i64[1] + 8));
  v23 = v544;
  pExceptionObject = v544;
  if ( (unsigned __int8)Microsoft::Basix::Dct::Smiles<Microsoft::Basix::Dct::LinkDataDisabled>::SetInitialPrimaryInLink(
                          v5,
                          &pExceptionObject) )
  {
    std::string::string(&v488, "Initial primaryInLink OnDataReceived");
    pExceptionObject = 0;
    if ( v22 )
      _InterlockedIncrement((volatile signed __int32 *)(v22 + 8));
    pExceptionObject = v23;
    Microsoft::Basix::Dct::SmilesV3::LogInitialLinkSwitchOn(
      v5,
      (unsigned int)v484,
      (unsigned int)&pExceptionObject,
      (unsigned int)&v488,
      1);
    std::string::_Tidy_deallocate(v484);
    std::string::_Tidy_deallocate(&v488);
  }
  LOWORD(v507[0]) = 0;
  LOWORD(v487) = 0;
  LOWORD(v497) = 0;
  v495 = 0xFFFF;
  *(_WORD *)v481 = -1;
  v566[0] = 0;
  v567 = 0;
  v568 = 0;
  v569 = 0;
  v570 = 0;
  v571 = 0;
  v24 = std::_Func_impl_no_alloc<_lambda_8fe06ae25614185e6bdd0a582616d3ae_,void,>::_Get(*v4);
  Microsoft::Basix::Containers::FlexIBuffer::Extract<unsigned char>(v24, &v479);
  v25 = std::_Func_impl_no_alloc<_lambda_8fe06ae25614185e6bdd0a582616d3ae_,void,>::_Get(*v4);
  Microsoft::Basix::Containers::FlexIBuffer::Extract<enum Microsoft::Basix::Dct::ICE::STUNMessage::Type>(v25, &v487);
  v26 = std::_Func_impl_no_alloc<_lambda_8fe06ae25614185e6bdd0a582616d3ae_,void,>::_Get(*v4);
  Microsoft::Basix::Containers::FlexIBuffer::Extract<enum Microsoft::Basix::Dct::ICE::STUNMessage::Type>(v26, &v497);
  LOWORD(v543[0]) = v487;
  Microsoft::Basix::Algorithm::SequenceNumberGeneratorWithRolloverCounter<16,48,unsigned short,unsigned __int64,unsigned __int64>::DecodeSequenceNumberAndUpdateCurrent(
    v5 + 2952,
    v539,
    v543);
  if ( *(_BYTE *)(v5 + 1524)
    && (unsigned __int8)std::operator==<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceCheckpoint>>(
                          *(_QWORD *)(v5 + 1816),
                          0) )
  {
    *(_OWORD *)v536 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(v536);
    if ( v536[0] && *((_BYTE *)v536[0] + 128) )
    {
      std::string::string(&v488, "SmilesV3: Location %d m_primaryOutLink == nullptr", v27);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,int>(
        v536,
        "BASIX_DCT",
        &v488,
        8);
      std::string::_Tidy_deallocate(&v488);
    }
    std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(v536);
    *(_OWORD *)v536 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceCheckpoint>(v536);
    if ( v536[0] && *((_BYTE *)v536[0] + 128) )
    {
      std::_Integral_to_string<char,int>(v504, 8);
      v28 = std::string::string(v501, ":");
      v29 = std::string::string(v502, "\"");
      v30 = std::string::string(v499, "\"");
      v31 = std::operator+<char>(v484, v30, "Location");
      LOBYTE(v32) = v478;
      std::string::string(&pExceptionObject, v32, v31, v29);
      LOBYTE(v33) = v478;
      std::string::string(&v549, v33, &pExceptionObject, v28);
      LOBYTE(v34) = v478;
      std::string::string(&v488, v34, &v549, v504);
      Microsoft::Basix::Instrumentation::TraceManager::TraceCheckpointMessage<Microsoft::Basix::TraceCheckpoint,std::string>(
        (int)v536,
        (int)"RD_CHECKPOINT",
        0,
        (int)"Smiles",
        "TestPrimaryOutLinkNull",
        "TestPrimaryOutLinkNull",
        (__int64)&v488);
      std::string::_Tidy_deallocate(&v549);
      std::string::_Tidy_deallocate(&pExceptionObject);
      std::string::_Tidy_deallocate(v484);
      std::string::_Tidy_deallocate(v499);
      std::string::_Tidy_deallocate(v502);
      std::string::_Tidy_deallocate(v501);
      std::string::_Tidy_deallocate(v504);
      v4 = v498;
    }
    std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(v536);
  }
  v492 = (v479 & 8) != 0;
  v35 = (Microsoft::Basix::Dct::LinkDataV3 *)v23.m128i_i64[0];
  v540[0] = v23.m128i_i64[0];
  v36 = *(_QWORD *)v539;
  if ( v479 >= 0 )
    goto LABEL_112;
  v485 = 0;
  v37 = std::_Func_impl_no_alloc<_lambda_8fe06ae25614185e6bdd0a582616d3ae_,void,>::_Get(*v4);
  Microsoft::Basix::Containers::FlexIBuffer::Extract<unsigned char>(v37, &v485);
  v38 = std::_Func_impl_no_alloc<_lambda_8fe06ae25614185e6bdd0a582616d3ae_,void,>::_Get(*v4);
  Buffer = (char *)(*(_QWORD *)(v38 + 24) - *(_QWORD *)(v38 + 16));
  if ( !v485 )
    goto LABEL_112;
  LOWORD(v487) = 0;
  v39 = std::_Func_impl_no_alloc<_lambda_8fe06ae25614185e6bdd0a582616d3ae_,void,>::_Get(*v4);
  Microsoft::Basix::Containers::FlexIBuffer::Extract<enum Microsoft::Basix::Dct::ICE::STUNMessage::Type>(v39, &v487);
  if ( (v487 & 2) != 0 )
  {
    v40 = std::_Func_impl_no_alloc<_lambda_8fe06ae25614185e6bdd0a582616d3ae_,void,>::_Get(*v4);
    Microsoft::Basix::Containers::FlexIBuffer::Extract<enum Microsoft::Basix::Dct::ICE::STUNMessage::Type>(v40, v482);
    if ( (unsigned int)Microsoft::Basix::Algorithm::SlidingStats<double,20,1,1>::num(*(_QWORD *)(v5 + 2896)) )
      v41 = Microsoft::Basix::Algorithm::SlidingStats<double,20,1,1>::nmin(*(_QWORD *)(v5 + 2896));
    else
      v41 = (double)-*(__int16 *)v482;
    v42 = v482[0];
    v43 = (v41 - (double)*(__int16 *)v482) * 0.5;
    Microsoft::Basix::Algorithm::SlidingStats<double,5,1,1>::add(*(_QWORD *)(v5 + 2904));
    *(_OWORD *)v536 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceDebug>(v536);
    if ( v536[0] && *((_BYTE *)v536[0] + 128) )
    {
      v46 = *(_DWORD *)(v23.m128i_i64[0] + 152);
      std::string::string(
        &v488,
        "SmilesV3::OnDataReceived() CLOCK_OFFSET: linkId=%d, peerClockOffsetInMs=%d, finalClockOffset=%d",
        v44,
        v45,
        v469);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceDebug,unsigned int,int,int>(
        (unsigned int)v536,
        (unsigned int)"BASIX_DCT",
        (unsigned int)&v488,
        v46,
        v42,
        (int)v43);
      std::string::_Tidy_deallocate(&v488);
      v4 = v498;
    }
    std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(v536);
  }
  if ( (v487 & 1) != 0 )
  {
    v492 = 1;
    v47 = std::_Func_impl_no_alloc<_lambda_8fe06ae25614185e6bdd0a582616d3ae_,void,>::_Get(*v4);
    Microsoft::Basix::Containers::FlexIBuffer::Extract<enum Microsoft::Basix::Dct::ICE::STUNMessage::Type>(v47, v481);
    v48 = std::_Func_impl_no_alloc<_lambda_8fe06ae25614185e6bdd0a582616d3ae_,void,>::_Get(*v4);
    Microsoft::Basix::Containers::FlexIBuffer::Extract<enum Microsoft::Basix::Dct::ICE::STUNMessage::Type>(v48, v543);
    Microsoft::Basix::Algorithm::SlidingStats<double,5,1,0>::add(*(_QWORD *)(v23.m128i_i64[0] + 200));
    *(_WORD *)v482 = 0;
    v49 = std::_Func_impl_no_alloc<_lambda_8fe06ae25614185e6bdd0a582616d3ae_,void,>::_Get(*v4);
    Microsoft::Basix::Containers::FlexIBuffer::Extract<enum Microsoft::Basix::Dct::ICE::STUNMessage::Type>(v49, v482);
    *(_WORD *)(v23.m128i_i64[0] + 242) = *(_WORD *)v482;
    *(_OWORD *)v536 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceDebug>(v536);
    v495 = *(unsigned __int16 *)v481;
    if ( v536[0] && *((_BYTE *)v536[0] + 128) )
    {
      v52 = v481[0];
      v53 = *(_WORD *)(v23.m128i_i64[0] + 242);
      v54 = *(_DWORD *)(v23.m128i_i64[0] + 152);
      std::string::string(
        &v488,
        "SmilesV3::OnDataReceived() SYNC_EX: linkId=%d, peerLinkId=%d, cntSendsInLastNMs=%d, delay=%d",
        v50,
        v51,
        v469,
        (_DWORD)Str);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceDebug,unsigned int,unsigned short,int,int>(
        (unsigned int)v536,
        (unsigned int)"BASIX_DCT",
        (unsigned int)&v488,
        v54,
        v53,
        v52,
        v543[0]);
      std::string::_Tidy_deallocate(&v488);
      v35 = (Microsoft::Basix::Dct::LinkDataV3 *)v540[0];
      v4 = v498;
    }
    std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(v536);
  }
  if ( (v487 & 4) != 0 )
  {
    v481[0] = 0;
    v55 = std::_Func_impl_no_alloc<_lambda_8fe06ae25614185e6bdd0a582616d3ae_,void,>::_Get(*v4);
    Microsoft::Basix::Containers::FlexIBuffer::Extract<unsigned char>(v55, v482);
    v56 = std::_Func_impl_no_alloc<_lambda_8fe06ae25614185e6bdd0a582616d3ae_,void,>::_Get(*v4);
    Microsoft::Basix::Containers::FlexIBuffer::Extract<unsigned char>(v56, v481);
    v566[0] = v482[0];
    if ( v481[0] )
    {
      v57 = (unsigned __int8)v481[0];
      v58 = v498;
      do
      {
        v59 = std::_Func_impl_no_alloc<_lambda_8fe06ae25614185e6bdd0a582616d3ae_,void,>::_Get(*v58);
        Microsoft::Basix::Containers::FlexIBuffer::Extract<enum Microsoft::Basix::Dct::ICE::STUNMessage::Type>(
          v59,
          v543);
        *(_WORD *)v481 = v543[0];
        if ( *((_QWORD *)&v567 + 1) == v568 )
        {
          std::vector<short>::_Emplace_reallocate<short>(&v567, *((_QWORD *)&v567 + 1), v481);
        }
        else
        {
          **((_WORD **)&v567 + 1) = v543[0];
          *((_QWORD *)&v567 + 1) += 2LL;
        }
        --v57;
      }
      while ( v57 );
    }
    *(_OWORD *)v536 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceDebug>(v536);
    if ( v536[0] && *((_BYTE *)v536[0] + 128) )
    {
      v62 = (__int64)(*((_QWORD *)&v567 + 1) - v567) >> 1;
      v63 = *((_DWORD *)v35 + 38);
      std::string::string(
        &v488,
        "SmilesV3::OnDataReceived() INFORM_PEER_SWITCHINFO_EX: linkId=%d, switchInfo.reason=%d, contextCnt=%d",
        v60,
        v61,
        v469);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceDebug,unsigned int,unsigned char,unsigned __int64>(
        (unsigned int)v536,
        (unsigned int)"BASIX_DCT",
        (unsigned int)&v488,
        v63,
        v482[0],
        v62);
      std::string::_Tidy_deallocate(&v488);
    }
    std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(v536);
  }
  v64 = v498;
  if ( (v487 & 8) != 0 )
  {
    v65 = std::_Func_impl_no_alloc<_lambda_8fe06ae25614185e6bdd0a582616d3ae_,void,>::_Get(*v498);
    Microsoft::Basix::Containers::FlexIBuffer::Extract<unsigned char>(v65, v482);
    v66 = std::_Func_impl_no_alloc<_lambda_8fe06ae25614185e6bdd0a582616d3ae_,void,>::_Get(*v64);
    Microsoft::Basix::Containers::FlexIBuffer::Extract<enum Microsoft::Basix::Dct::ICE::STUNMessage::Type>(v66, v543);
    if ( *(_BYTE *)(v5 + 3177) )
    {
      std::string::string(v484, "C:\\__w\\1\\s\\src\\libbasix-network\\dct\\smilesv3.cpp");
      std::string::string(v499, "received INFORM_PEER_OPERATION_EX when sideband is used");
      Microsoft::Basix::Exception::Exception(v532, v499, v484, 1381);
      throw (Microsoft::Basix::Exception *)v532;
    }
    v67 = *(_QWORD *)(v5 + 3160);
    v68 = v36 <= v67;
    if ( v36 != v67 )
    {
      if ( v36 >= v67 )
      {
LABEL_63:
        if ( v68 || v36 - v67 <= 0x8000000000000000uLL )
        {
          Microsoft::Basix::Dct::SmilesV3::ProcessOutOperationNoLock(
            (Microsoft::Basix::Dct::SmilesV3 *)v5,
            v543[0],
            v482[0],
            (struct Microsoft::Basix::Dct::OperationOnLinkId *)&v574);
          *(_QWORD *)(v5 + 3160) = v36;
        }
        goto LABEL_66;
      }
      if ( v67 - v36 >= 0x8000000000000000uLL )
      {
        v68 = v36 <= v67;
        goto LABEL_63;
      }
    }
  }
LABEL_66:
  if ( (v487 & 0x10) != 0 )
  {
    v69 = std::_Func_impl_no_alloc<_lambda_8fe06ae25614185e6bdd0a582616d3ae_,void,>::_Get(*v64);
    Microsoft::Basix::Containers::FlexIBuffer::Extract<enum Microsoft::Basix::Dct::ICE::STUNMessage::Type>(v69, v507);
    *(_OWORD *)v536 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceDebug>(v536);
    if ( v536[0] && *((_BYTE *)v536[0] + 128) )
    {
      v72 = *((_DWORD *)v35 + 38);
      std::string::string(
        &v488,
        "SmilesV3::OnDataReceived() INFORM_PEER_PRIMARY_LINKID_EX: currentLinkId=%d, newOutPrimaryLinkId=%d",
        v70,
        v71);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceDebug,unsigned int,unsigned short>(
        (unsigned int)v536,
        (unsigned int)"BASIX_DCT",
        (unsigned int)&v488,
        v72,
        v507[0]);
      std::string::_Tidy_deallocate(&v488);
    }
    std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(v536);
  }
  if ( (v487 & 0x20) != 0 )
  {
    v481[0] = 0;
    v73 = std::_Func_impl_no_alloc<_lambda_8fe06ae25614185e6bdd0a582616d3ae_,void,>::_Get(*v64);
    Microsoft::Basix::Containers::FlexIBuffer::Extract<unsigned char>(v73, v481);
    if ( (unsigned int)(unsigned __int8)v481[0] < *(_DWORD *)(v5 + 3104) )
    {
      if ( (unsigned __int8)v481[0] == *(_DWORD *)(v5 + 3108) )
      {
        v480 = 0;
      }
      else
      {
        *(_DWORD *)(v5 + 3108) = (unsigned __int8)v481[0];
        v480 = 1;
      }
      v486 = 0;
    }
    else
    {
      *(_DWORD *)(v5 + 3104) = (unsigned __int8)v481[0];
      v486 = 1;
    }
    *(_OWORD *)v536 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceDebug>(v536);
    if ( v536[0] && *((_BYTE *)v536[0] + 128) )
    {
      v76 = *(_DWORD *)(v5 + 3104);
      v77 = *((_DWORD *)v35 + 38);
      std::string::string(
        &v488,
        "SmilesV3::OnDataReceived() INFORM_PEER_PRIMARY_EPOCH_EX: currentLinkId=%d, epoch=%d, m_currentSwitchEpoch=%d",
        v74,
        v75,
        v469);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceDebug,unsigned int,unsigned char,unsigned int>(
        (unsigned int)v536,
        (unsigned int)"BASIX_DCT",
        (unsigned int)&v488,
        v77,
        v481[0],
        v76);
      std::string::_Tidy_deallocate(&v488);
      v64 = v498;
    }
    std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(v536);
  }
  v78 = std::_Func_impl_no_alloc<_lambda_8fe06ae25614185e6bdd0a582616d3ae_,void,>::_Get(*v64);
  v79 = &Buffer[v485];
  if ( (unsigned __int64)v79 < *(_QWORD *)(v78 + 24) - *(_QWORD *)(v78 + 16) )
  {
    *(_OWORD *)v536 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceWarning>(v536);
    if ( v536[0] && *((_BYTE *)v536[0] + 128) )
    {
      std::string::string(&v488, "SmilesV3 extension header corrupted! drop the packet");
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceWarning,>(
        v536,
        "BASIX_DCT",
        &v488);
      std::string::_Tidy_deallocate(&v488);
    }
    std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(v536);
    if ( *(_BYTE *)(v5 + 2688) )
    {
      LODWORD(v545[0]) = 2;
      v545[1] = (struct std::nothrow_t *)&Str1;
      v546 = 0;
      v547 = 0;
      v478 = 0;
      LODWORD(v551[0]) = 2;
      v551[1] = "ProcessSmilesPacketReceived";
      v552 = 27;
      v553 = 0;
      LODWORD(v504[0]) = 2;
      v504[1] = (std::_Ref_count_base *)"smiles";
      v505 = 6;
      v506 = 0;
      LODWORD(v536[0]) = 2;
      v536[1] = "Received packet with corrupted smiles header";
      v537 = 44;
      v538 = 0;
      pExceptionObject.m128i_i32[0] = 2;
      pExceptionObject.m128i_i64[1] = (__int64)"InvalidSmilesPacket";
      v534 = 19;
      v535 = 0;
      v495 = 13;
      v81 = "client";
      if ( *(_BYTE *)(v5 + 1112) )
        v81 = "stack";
      v549.m256i_i32[0] = 2;
      v549.m256i_i64[1] = (__int64)v81;
      v549.m256i_i64[2] = strlen(v81);
      v549.m256i_i8[24] = 0;
      v82 = 63;
      v494 = *((_DWORD *)v35 + 38);
      Microsoft::Basix::Instrumentation::MultiLinkError::LogInterface::operator()<boost::container::small_vector<std::shared_ptr<Microsoft::Basix::Instrumentation::EventLogger>,4,void,void> const &>(
        v5 + 2816,
        v5 + 2696,
        (unsigned int)&v494,
        (unsigned int)&v549,
        (__int64)&v495,
        (__int64)&pExceptionObject,
        (__int64)v536,
        (__int64)v504,
        (__int64)v551,
        (__int64)&v478,
        (__int64)v545);
    }
    else
    {
      v82 = v494;
    }
    if ( (v82 & 0x20) != 0 )
    {
      v82 &= ~0x20u;
      if ( v549.m256i_i8[24] )
        operator delete((void *)v549.m256i_i64[1], v80);
    }
    if ( (v82 & 0x10) != 0 )
    {
      v82 &= ~0x10u;
      if ( v535 )
        operator delete((void *)pExceptionObject.m128i_i64[1], v80);
    }
    if ( (v82 & 8) != 0 )
    {
      v82 &= ~8u;
      if ( v538 )
        operator delete(v536[1], v80);
    }
    if ( (v82 & 4) != 0 )
    {
      v82 &= ~4u;
      if ( v506 )
        operator delete(v504[1], v80);
    }
    if ( (v82 & 2) != 0 )
    {
      v82 &= ~2u;
      if ( v553 )
        operator delete(v551[1], v80);
    }
    if ( (v82 & 1) != 0 && v547 )
      operator delete(v545[1], v80);
    std::vector<short>::_Tidy(&v567);
    Mtx_unlock(v500);
    std::pair<unsigned __int64 const,Microsoft::Basix::Dct::Rcp::PacketResendInfo>::~pair<unsigned __int64 const,Microsoft::Basix::Dct::Rcp::PacketResendInfo>(&v574);
    std::pair<unsigned __int64 const,Microsoft::Basix::Dct::Rcp::PacketResendInfo>::~pair<unsigned __int64 const,Microsoft::Basix::Dct::Rcp::PacketResendInfo>(&v572);
    std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(&v503);
    std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(&v544);
    v7 = *(volatile signed __int32 **)(v511 + 8);
    if ( v7 )
    {
      v8 = _InterlockedExchangeAdd(v7 + 3, 0xFFFFFFFF) == 1;
      goto LABEL_675;
    }
    return;
  }
  v83 = std::_Func_impl_no_alloc<_lambda_8fe06ae25614185e6bdd0a582616d3ae_,void,>::_Get(*v64);
  *(_QWORD *)(v83 + 24) = &v79[*(_QWORD *)(v83 + 16)];
  v22 = v544.m128i_i64[1];
LABEL_112:
  if ( *((_DWORD *)v35 + 70) == 1 )
  {
    v84 = Microsoft::Basix::Dct::LinkDataV3::SetInUnsuspend(v35);
    *(_OWORD *)v536 = 0;
    if ( v84 )
    {
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceDebug>(v536);
      if ( v536[0] && *((_BYTE *)v536[0] + 128) )
      {
        v87 = *((_DWORD *)v35 + 38);
        std::string::string(&v488, "SmilesV3:  link(%d)%p unsuspend now", v85, v86);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceDebug,unsigned int,Microsoft::Basix::Dct::LinkDataV3 *>(
          (unsigned int)v536,
          (unsigned int)"BASIX_DCT",
          (unsigned int)&v488,
          v87,
          (__int64)v35);
        std::string::_Tidy_deallocate(&v488);
      }
      std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(v536);
      if ( v22 )
        _InterlockedIncrement((volatile signed __int32 *)(v22 + 8));
      pExceptionObject = v23;
      LOBYTE(v88) = 1;
      Microsoft::Basix::Dct::OperationOnLinkId::Set(&v572, v88, &pExceptionObject);
      std::deque<Microsoft::Basix::Dct::OperationOnLinkId>::_Emplace_back_internal<Microsoft::Basix::Dct::OperationOnLinkId const &>(
        v5 + 3120,
        &v572);
      if ( *((_DWORD *)v35 + 20) != 9 )
        Microsoft::Basix::Dct::SmilesV3::CheckLinkSwitchDueToFirstICELinkActivated((Microsoft::Basix::Dct::SmilesV3 *)v5);
    }
    else
    {
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceDebug>(v536);
      if ( v536[0] && *((_BYTE *)v536[0] + 128) )
      {
        v91 = *((_DWORD *)v35 + 61);
        v92 = *((_DWORD *)v35 + 38);
        std::string::string(&v488, "SmilesV3:  link(%d)%p unsuspend pending count %d", v89, v90, v469);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceDebug,unsigned int,Microsoft::Basix::Dct::LinkDataV3 *,unsigned int>(
          (unsigned int)v536,
          (unsigned int)"BASIX_DCT",
          (unsigned int)&v488,
          v92,
          (__int64)v35,
          v91);
        std::string::_Tidy_deallocate(&v488);
      }
      std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(v536);
    }
  }
  if ( *(_BYTE *)(v5 + 1524)
    && (unsigned __int8)std::operator==<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceCheckpoint>>(
                          *(_QWORD *)(v5 + 1816),
                          0) )
  {
    *(_OWORD *)v536 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(v536);
    if ( v536[0] && *((_BYTE *)v536[0] + 128) )
    {
      std::string::string(&v488, "SmilesV3: Location %d m_primaryOutLink == nullptr", v93);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,int>(
        v536,
        "BASIX_DCT",
        &v488,
        9);
      std::string::_Tidy_deallocate(&v488);
    }
    std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(v536);
    *(_OWORD *)v536 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceCheckpoint>(v536);
    if ( v536[0] && *((_BYTE *)v536[0] + 128) )
    {
      std::_Integral_to_string<char,int>(v504, 9);
      v94 = std::string::string(v501, ":");
      v95 = std::string::string(v502, "\"");
      v96 = std::string::string(v499, "\"");
      v97 = std::operator+<char>(v484, v96, "Location");
      LOBYTE(v98) = v478;
      std::string::string(&pExceptionObject, v98, v97, v95);
      LOBYTE(v99) = v478;
      std::string::string(&v549, v99, &pExceptionObject, v94);
      LOBYTE(v100) = v478;
      std::string::string(&v488, v100, &v549, v504);
      Microsoft::Basix::Instrumentation::TraceManager::TraceCheckpointMessage<Microsoft::Basix::TraceCheckpoint,std::string>(
        (int)v536,
        (int)"RD_CHECKPOINT",
        0,
        (int)"Smiles",
        "TestPrimaryOutLinkNull",
        "TestPrimaryOutLinkNull",
        (__int64)&v488);
      std::string::_Tidy_deallocate(&v549);
      std::string::_Tidy_deallocate(&pExceptionObject);
      std::string::_Tidy_deallocate(v484);
      std::string::_Tidy_deallocate(v499);
      std::string::_Tidy_deallocate(v502);
      std::string::_Tidy_deallocate(v501);
      std::string::_Tidy_deallocate(v504);
    }
    std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(v536);
  }
  *(_OWORD *)v504 = 0;
  v101 = *(size_t **)(v5 + 1824);
  v102 = v101[1];
  if ( v102 )
    _InterlockedIncrement((volatile signed __int32 *)(v102 + 8));
  v541[0] = *v101;
  v504[0] = (std::_Ref_count_base *)v541[0];
  v496 = (volatile signed __int32 *)v101[1];
  v504[1] = (std::_Ref_count_base *)v496;
  LOWORD(v543[0]) = v497;
  v103 = *(_QWORD *)Microsoft::Basix::Algorithm::SequenceNumberGeneratorWithRolloverCounter<16,48,unsigned short,unsigned __int64,unsigned __int64>::DecodeSequenceNumberAndUpdateCurrent(
                      v5 + 2960,
                      &Buffer,
                      v543);
  Buffer = (char *)v103;
  if ( v103 < 0 )
    v104 = (double)(int)(v103 & 1 | ((unsigned __int64)v103 >> 1))
         + (double)(int)(v103 & 1 | ((unsigned __int64)v103 >> 1));
  else
    v104 = (double)(int)v103;
  v105 = v19 - v104;
  Microsoft::Basix::Algorithm::SlidingStats<double,20,1,1>::add(*(_QWORD *)(v5 + 2896));
  v106 = 0.0;
  if ( (unsigned int)Microsoft::Basix::Algorithm::SlidingStats<double,5,1,1>::num(*(_QWORD *)(v5 + 2904)) )
  {
    v106 = Microsoft::Basix::Algorithm::SlidingStats<double,5,1,1>::navg(*(_QWORD *)(v5 + 2904));
    v107 = fmax(v105 - v106, 0.0);
  }
  else
  {
    *(_QWORD *)&v107 = *(_QWORD *)&v105 & _xmm;
  }
  Microsoft::Basix::Dct::LinkDataV3::AddCounter((_DWORD)v35, v103, BufferCount, v36, *(__int64 *)&v107);
  *(_OWORD *)v536 = 0;
  Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceDebug>(v536);
  if ( v536[0] && *((_BYTE *)v536[0] + 128) )
  {
    MinDelayIn = Microsoft::Basix::Dct::LinkDataV3::GetMinDelayIn(v35);
    v109 = *((_DWORD *)v35 + 38);
    v110 = std::_Func_impl_no_alloc<_lambda_8fe06ae25614185e6bdd0a582616d3ae_,void,>::_Get(*v498);
    v111 = *(_QWORD *)(v110 + 32) - *(_QWORD *)(v110 + 24);
    std::string::string(
      &v488,
      "SmilesV3::OnDataReceived: received packet(size=%d) with counter(%d) on link(%d), delay(%f), minDelay=%f, %s codedS"
      "endTime(%d), sendTimeInMs(%llu), receiveTimeInMs(%llu), clockoffset=%d",
      v112,
      v113,
      (_DWORD)v470,
      *(double *)&Str,
      *(double *)&v472,
      v473,
      v474,
      v475,
      v476,
      v477);
    v114 = (const char *)&Str1;
    if ( v492 )
      v114 = "S,";
    Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceDebug,unsigned __int64,Microsoft::Basix::Algorithm::SequenceNumber<64,unsigned __int64>,unsigned int,double,double,char const *,unsigned short,unsigned __int64,unsigned __int64,double>(
      (unsigned int)v536,
      (unsigned int)"BASIX_DCT",
      (unsigned int)&v488,
      v111,
      v36,
      v109,
      SLOBYTE(v107),
      SLOBYTE(MinDelayIn),
      (__int64)v114,
      v497,
      (char)Buffer,
      BufferCount,
      SLOBYTE(v106));
    std::string::_Tidy_deallocate(&v488);
  }
  std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(v536);
  v115 = 0;
  if ( v20 >= 9.223372036854776e18 )
  {
    v20 = v20 - 9.223372036854776e18;
    if ( v20 < 9.223372036854776e18 )
      v115 = 0x8000000000000000uLL;
  }
  v116 = v115 + (unsigned int)(int)v20;
  ShouldSendLinkUpdate = Microsoft::Basix::Dct::LinkDataV3::ShouldSendLinkUpdate(v35, v116, 0);
  v118 = v544.m128i_i64[1];
  if ( ShouldSendLinkUpdate )
  {
    pExceptionObject = 0;
    if ( v544.m128i_i64[1] )
      _InterlockedIncrement((volatile signed __int32 *)(v544.m128i_i64[1] + 8));
    pExceptionObject = v23;
    Microsoft::Basix::Dct::SmilesV3::LogLinkUpdate(v5, &pExceptionObject, 0);
  }
  if ( Microsoft::Basix::Dct::LinkDataV3::ShouldSendLinkUpdate(v35, v116, 1u) )
  {
    pExceptionObject = 0;
    if ( v118 )
      _InterlockedIncrement((volatile signed __int32 *)(v118 + 8));
    pExceptionObject = v23;
    LOBYTE(v120) = 1;
    Microsoft::Basix::Dct::SmilesV3::LogLinkUpdate(v5, &pExceptionObject, v120);
  }
  if ( *(_BYTE *)(v5 + 1524)
    && (unsigned __int8)std::operator==<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceCheckpoint>>(
                          *(_QWORD *)(v5 + 1816),
                          0) )
  {
    *(_OWORD *)v536 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(v536);
    if ( v536[0] && *((_BYTE *)v536[0] + 128) )
    {
      std::string::string(&v488, "SmilesV3: Location %d m_primaryOutLink == nullptr", v121);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,int>(
        v536,
        "BASIX_DCT",
        &v488,
        19);
      std::string::_Tidy_deallocate(&v488);
    }
    std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(v536);
    *(_OWORD *)v536 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceCheckpoint>(v536);
    if ( v536[0] && *((_BYTE *)v536[0] + 128) )
    {
      std::_Integral_to_string<char,int>(v551, 19);
      v122 = std::string::string(v501, ":");
      v123 = std::string::string(v502, "\"");
      v124 = std::string::string(v499, "\"");
      v125 = std::operator+<char>(v484, v124, "Location");
      LOBYTE(v126) = v478;
      std::string::string(&pExceptionObject, v126, v125, v123);
      LOBYTE(v127) = v478;
      std::string::string(&v549, v127, &pExceptionObject, v122);
      LOBYTE(v128) = v478;
      std::string::string(&v488, v128, &v549, v551);
      Microsoft::Basix::Instrumentation::TraceManager::TraceCheckpointMessage<Microsoft::Basix::TraceCheckpoint,std::string>(
        (int)v536,
        (int)"RD_CHECKPOINT",
        0,
        (int)"Smiles",
        "TestPrimaryOutLinkNull",
        "TestPrimaryOutLinkNull",
        (__int64)&v488);
      std::string::_Tidy_deallocate(&v549);
      std::string::_Tidy_deallocate(&pExceptionObject);
      std::string::_Tidy_deallocate(v484);
      std::string::_Tidy_deallocate(v499);
      std::string::_Tidy_deallocate(v502);
      std::string::_Tidy_deallocate(v501);
      std::string::_Tidy_deallocate(v551);
    }
    std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(v536);
  }
  if ( (v479 & 2) != 0 )
  {
    si128 = 0;
    *(_OWORD *)v536 = 0;
    v130 = LOWORD(v507[0]);
    if ( LOWORD(v507[0]) )
    {
      *(_OWORD *)v551 = 0;
      Microsoft::Basix::Containers::IterationSafeStore<std::shared_ptr<Microsoft::Basix::Dct::FailoverBridge::Transport>,std::equal_to<std::shared_ptr<Microsoft::Basix::Dct::FailoverBridge::Transport>>>::iterator::iterator(
        v551,
        v5 + 1528);
      *(_OWORD *)v545 = 0;
      Microsoft::Basix::Containers::IterationSafeStore<std::shared_ptr<Microsoft::Basix::Dct::FailoverBridge::Transport>,std::equal_to<std::shared_ptr<Microsoft::Basix::Dct::FailoverBridge::Transport>>>::iterator::iterator(
        v545,
        0);
      v494 = 201326592;
      while ( 1 )
      {
        v131 = v551[1];
        if ( v551[0] == (char *)v545[0] && (!v551[0] || v551[1] == (char *)v545[1]) )
          break;
        if ( *(_DWORD *)(*(_QWORD *)v551[1] + 152LL) == v130 )
        {
          std::shared_ptr<Microsoft::RdpNano::RendezvousSource::RendezvousContext>::operator=(v536, v551[1]);
          si128 = _mm_load_si128((const __m128i *)v536);
          break;
        }
        Microsoft::Basix::Containers::IterationSafeStore<std::weak_ptr<Microsoft::Basix::Instrumentation::IActivityListener>,Microsoft::Basix::Algorithm::owner_equals<std::weak_ptr<Microsoft::Basix::Instrumentation::IActivityListener>>>::iterator::operator++(v551);
      }
      Microsoft::Basix::Containers::IterationSafeStore<std::weak_ptr<Microsoft::Basix::Pattern::Factory<std::shared_ptr<Microsoft::Basix::Dct::IChannel>,Microsoft::Basix::Pattern::BasicNameAndType<std::string>,std::shared_ptr<Microsoft::Basix::Dct::IChannel> const &,boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>> const &>>,Microsoft::Basix::Algorithm::owner_equals<std::weak_ptr<Microsoft::Basix::Pattern::Factory<std::shared_ptr<Microsoft::Basix::Dct::IChannel>,Microsoft::Basix::Pattern::BasicNameAndType<std::string>,std::shared_ptr<Microsoft::Basix::Dct::IChannel> const &,boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>> const &>>>>::iterator::~iterator(
        v545,
        v131);
      Microsoft::Basix::Containers::IterationSafeStore<std::weak_ptr<Microsoft::Basix::Pattern::Factory<std::shared_ptr<Microsoft::Basix::Dct::IChannel>,Microsoft::Basix::Pattern::BasicNameAndType<std::string>,std::shared_ptr<Microsoft::Basix::Dct::IChannel> const &,boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>> const &>>,Microsoft::Basix::Algorithm::owner_equals<std::weak_ptr<Microsoft::Basix::Pattern::Factory<std::shared_ptr<Microsoft::Basix::Dct::IChannel>,Microsoft::Basix::Pattern::BasicNameAndType<std::string>,std::shared_ptr<Microsoft::Basix::Dct::IChannel> const &,boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>> const &>>>>::iterator::~iterator(
        v551,
        v133);
    }
    else
    {
      std::shared_ptr<Microsoft::RdpNano::RendezvousSource::RendezvousContext>::operator=(v536, &v544);
      si128 = _mm_load_si128((const __m128i *)v536);
    }
    v134 = std::operator==<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceCheckpoint>>(v536, 0);
    v135 = (char *)_mm_srli_si128(si128, 8).m128i_u64[0];
    v551[0] = v135;
    if ( !v134 || *(_WORD *)(v5 + 3112) == (_WORD)v130 )
    {
      if ( v486 )
      {
        if ( !(unsigned __int8)boost::multi_index::detail::operator==<boost::multi_index::detail::ordered_index_node<boost::multi_index::detail::null_augment_policy,boost::multi_index::detail::index_node_base<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>,std::allocator<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>>>>>(
                                 v536,
                                 *(_QWORD *)(v5 + 1816)) )
        {
          *(_OWORD *)v549.m256i_i8 = 0;
          *(__m128i *)&v549.m256i_u64[2] = _mm_load_si128((const __m128i *)&_xmm);
          v549.m256i_i8[0] = 0;
          v146 = *(_QWORD **)(v5 + 1816);
          pExceptionObject = 0;
          if ( *v146 )
          {
            Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(&pExceptionObject);
            v545[0] = (struct std::nothrow_t *)si128.m128i_i64[0];
            if ( pExceptionObject.m128i_i64[0] && *(_BYTE *)(pExceptionObject.m128i_i64[0] + 128) )
            {
              *(_QWORD *)&v543[0] = v484;
              v147 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)(si128.m128i_i64[0] + 104) + 104LL))(
                       *(_QWORD *)(si128.m128i_i64[0] + 104),
                       v484);
              v148 = *(_DWORD *)(si128.m128i_i64[0] + 152);
              *(_QWORD *)&v507[0] = v499;
              v149 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)(**(_QWORD **)(v5 + 1816) + 104LL)
                                                                  + 104LL))(
                       *(_QWORD *)(**(_QWORD **)(v5 + 1816) + 104LL),
                       v499);
              v150 = *(_DWORD *)(**(_QWORD **)(v5 + 1816) + 152LL);
              std::string::string(
                &v488,
                "SmilesV3: primaryOutLink switching from link (%d, '%s') to link (%d, '%s')",
                v151,
                v152,
                (_DWORD)v470,
                Str);
              Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,unsigned int,std::string,unsigned int,std::string>(
                (unsigned int)&pExceptionObject,
                (unsigned int)"BASIX_DCT",
                (unsigned int)&v488,
                v150,
                v149,
                v148,
                v147);
              std::string::_Tidy_deallocate(&v488);
              v35 = (Microsoft::Basix::Dct::LinkDataV3 *)v540[0];
              v135 = v551[0];
            }
            std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(&pExceptionObject);
            v507[0] = 0;
            if ( v135 )
              _InterlockedIncrement((volatile signed __int32 *)v135 + 2);
            v507[0] = si128;
            v153 = *(__m128i **)(v5 + 1816);
            pExceptionObject = 0;
            v154 = v153->m128i_i64[1];
            if ( v154 )
              _InterlockedIncrement((volatile signed __int32 *)(v154 + 8));
            pExceptionObject = *v153;
            v155 = Microsoft::Basix::Dct::SmilesV3::LogLinkSwitch(
                     v5,
                     (unsigned int)v484,
                     (unsigned int)&pExceptionObject,
                     (unsigned int)v507,
                     (__int64)v566,
                     0);
            std::string::operator=(&v549, v155);
            v156 = v484;
          }
          else
          {
            Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(&pExceptionObject);
            v545[0] = (struct std::nothrow_t *)si128.m128i_i64[0];
            if ( pExceptionObject.m128i_i64[0] && *(_BYTE *)(pExceptionObject.m128i_i64[0] + 128) )
            {
              *(_QWORD *)&v543[0] = v484;
              v157 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)(si128.m128i_i64[0] + 104) + 104LL))(
                       *(_QWORD *)(si128.m128i_i64[0] + 104),
                       v484);
              v158 = *(_DWORD *)(si128.m128i_i64[0] + 152);
              std::string::string(
                &v488,
                "SmilesV3: primaryOutLink switching from null link to link (%d, '%s')",
                v159,
                v160);
              Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,unsigned int,std::string>(
                (unsigned int)&pExceptionObject,
                (unsigned int)"BASIX_DCT",
                (unsigned int)&v488,
                v158,
                v157);
              std::string::_Tidy_deallocate(&v488);
              v135 = v551[0];
            }
            std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(&pExceptionObject);
            std::string::string(&v488, "Initial primaryOutLink Set in OnDataReceived");
            pExceptionObject = 0;
            if ( v135 )
              _InterlockedIncrement((volatile signed __int32 *)v135 + 2);
            pExceptionObject = si128;
            v161 = Microsoft::Basix::Dct::SmilesV3::LogInitialLinkSwitchOn(
                     v5,
                     (unsigned int)v484,
                     (unsigned int)&pExceptionObject,
                     (unsigned int)&v488,
                     0);
            std::string::operator=(&v549, v161);
            std::string::_Tidy_deallocate(v484);
            v156 = &v488;
          }
          std::string::_Tidy_deallocate(v156);
          v162 = *(_DWORD *)(v5 + 2216);
          *(_DWORD *)(v5 + 2216) = v162 + 1;
          v163 = v545[0];
          *((_DWORD *)v545[0] + 65) = v162;
          if ( *(_BYTE *)(v5 + 2368) )
          {
            LODWORD(v488) = 2;
            v164 = &v549;
            if ( v549.m256i_i64[3] > 0xFuLL )
              v164 = (__m256i *)v549.m256i_i64[0];
            v489 = v164;
            v490 = v549.m256i_i64[2];
            v491 = 0;
            v165 = v494 | 0x40;
            LODWORD(v543[0]) = v494 | 0x40;
            v166 = *(_QWORD *)(v5 + 1816);
            if ( *(_QWORD *)v166 )
              v167 = *(_DWORD *)(*(_QWORD *)v166 + 260LL);
            else
              v167 = -1;
            v494 = v167;
            LODWORD(v507[0]) = (int)Microsoft::Basix::Dct::LinkDataV3::GetAveDelayOut(v163);
            pExceptionObject.m128i_i32[0] = 2;
            pExceptionObject.m128i_i64[1] = (__int64)"linkSwitch";
            v534 = 10;
            v535 = 0;
            v168 = v165 | 0x80;
            v497 = *((_DWORD *)v545[0] + 65);
            v487 = *((_DWORD *)v545[0] + 38);
            Microsoft::Basix::Instrumentation::MultiLinkActivity::LogInterface::operator()<boost::container::small_vector<std::shared_ptr<Microsoft::Basix::Instrumentation::EventLogger>,4,void,void> const &>(
              v5 + 2496,
              v5 + 2376,
              (unsigned int)&v487,
              (unsigned int)&v497,
              (__int64)&pExceptionObject,
              (__int64)v507,
              (__int64)&v494,
              v5 + 2212,
              (__int64)&v488);
          }
          else
          {
            v168 = v494;
          }
          if ( v168 < 0 )
          {
            v168 &= ~0x80u;
            if ( v535 )
              operator delete((void *)pExceptionObject.m128i_i64[1], v163);
          }
          if ( (v168 & 0x40) != 0 && v491 )
            operator delete(v489, v163);
          pExceptionObject = 0;
          if ( v135 )
            _InterlockedIncrement((volatile signed __int32 *)v135 + 2);
          pExceptionObject = si128;
          Microsoft::Basix::Dct::Smiles<Microsoft::Basix::Dct::LinkDataDisabled>::ChangePrimary(
            v5,
            &pExceptionObject,
            0);
          v493 = 1;
          AveDelayOut = DOUBLE_1000_0;
          v543[0] = 0;
          pExceptionObject = 0;
          Microsoft::Basix::Containers::IterationSafeStore<std::shared_ptr<Microsoft::Basix::Dct::FailoverBridge::Transport>,std::equal_to<std::shared_ptr<Microsoft::Basix::Dct::FailoverBridge::Transport>>>::iterator::iterator(
            &pExceptionObject,
            v5 + 1528);
          v170 = 0.0;
          *(_OWORD *)v545 = 0;
          Microsoft::Basix::Containers::IterationSafeStore<std::shared_ptr<Microsoft::Basix::Dct::FailoverBridge::Transport>,std::equal_to<std::shared_ptr<Microsoft::Basix::Dct::FailoverBridge::Transport>>>::iterator::iterator(
            v545,
            0);
          v21 = (Microsoft::Basix::Instrumentation::DelayedTraceManager::DelayedTraceRecord **)v545[0];
          while ( 1 )
          {
            v171 = (Microsoft::Basix::Dct::LinkDataV3 **)pExceptionObject.m128i_i64[1];
            v172 = pExceptionObject.m128i_i64[0];
            if ( (Microsoft::Basix::Instrumentation::DelayedTraceManager::DelayedTraceRecord **)pExceptionObject.m128i_i64[0] == v21
              && (!pExceptionObject.m128i_i64[0] || (struct std::nothrow_t *)pExceptionObject.m128i_i64[1] == v545[1]) )
            {
              break;
            }
            v174 = *(_QWORD *)pExceptionObject.m128i_i64[1];
            if ( (int)Microsoft::Basix::Algorithm::SlidingStats<double,5,0,0>::num(*(_QWORD *)(*(_QWORD *)pExceptionObject.m128i_i64[1]
                                                                                             + 200LL)) <= 0 )
              v170 = DOUBLE_1000_0;
            else
              Microsoft::Basix::Algorithm::SlidingStats<double,5,1,0>::navg(*(_QWORD *)(v174 + 200));
            if ( AveDelayOut > v170 )
            {
              AveDelayOut = Microsoft::Basix::Dct::LinkDataV3::GetAveDelayOut(*v171);
              v170 = std::shared_ptr<Microsoft::RdpNano::RendezvousSource::RendezvousContext>::operator=(v543, v171);
            }
            Microsoft::Basix::Containers::IterationSafeStore<std::weak_ptr<Microsoft::Basix::Instrumentation::IActivityListener>,Microsoft::Basix::Algorithm::owner_equals<std::weak_ptr<Microsoft::Basix::Instrumentation::IActivityListener>>>::iterator::operator++(&pExceptionObject);
          }
          v8 = v21 == 0;
          v36 = *(_QWORD *)v539;
          LODWORD(v21) = v548;
          if ( !v8
            && _InterlockedExchangeAdd(
                 (volatile signed __int32 *)(*(__int64 (__fastcall **)(char *))&boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>.Data1)((char *)v545[0] + 80),
                 0xFFFFFFFF) == -1 )
          {
            std::runtime_error::runtime_error((std::runtime_error *)v551, "Unbalanced endIteration()");
            throw (std::runtime_error *)v551;
          }
          if ( v172
            && _InterlockedExchangeAdd(
                 (volatile signed __int32 *)(*(__int64 (__fastcall **)(__int64))&boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>.Data1)(v172 + 80),
                 0xFFFFFFFF) == -1 )
          {
            std::runtime_error::runtime_error((std::runtime_error *)&pExceptionObject, "Unbalanced endIteration()");
            throw (std::runtime_error *)&pExceptionObject;
          }
          v175 = *(Microsoft::Basix::Dct::LinkDataV3 ***)(v5 + 1816);
          if ( (unsigned __int8)std::operator!=<Microsoft::Basix::Dct::LinkDataV3,Microsoft::Basix::Dct::LinkDataV3>(
                                  v543,
                                  v175) )
          {
            if ( *v175 )
            {
              v176 = *(_QWORD *)&v543[0];
              if ( *(_QWORD *)&v543[0] )
              {
                if ( Microsoft::Basix::Dct::LinkDataV3::GetAveDelayOut(*v175) > AveDelayOut )
                {
                  pExceptionObject = 0;
                  Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceWarning>(&pExceptionObject);
                  if ( pExceptionObject.m128i_i64[0] && *(_BYTE *)(pExceptionObject.m128i_i64[0] + 128) )
                  {
                    v177 = Microsoft::Basix::Dct::LinkDataV3::GetAveDelayOut(**(Microsoft::Basix::Dct::LinkDataV3 ***)(v5 + 1816));
                    v178 = *(_DWORD *)(v176 + 152);
                    v179 = *(_DWORD *)(**(_QWORD **)(v5 + 1816) + 152LL);
                    std::string::string(
                      &v488,
                      "SmilesV3: WARNING: m_primaryOutLink doesn't have minimal delay: primaryLinkId=%d, minDelayLinkId=%"
                      "d, primaryLinkDelay=%f, minLinkDelay=%f",
                      v180,
                      v181,
                      *(double *)&v470,
                      *(double *)&Str);
                    Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceWarning,unsigned int,unsigned int,double,double>(
                      (unsigned int)&pExceptionObject,
                      (unsigned int)"BASIX_DCT",
                      (unsigned int)&v488,
                      v179,
                      v178,
                      SLOBYTE(v177),
                      SLOBYTE(AveDelayOut));
                    std::string::_Tidy_deallocate(&v488);
                  }
                  std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(&pExceptionObject);
                }
              }
            }
          }
          if ( *(_BYTE *)(v5 + 1524)
            && (unsigned __int8)std::operator==<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceCheckpoint>>(
                                  *(_QWORD *)(v5 + 1816),
                                  0) )
          {
            pExceptionObject = 0;
            Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(&pExceptionObject);
            if ( pExceptionObject.m128i_i64[0] && *(_BYTE *)(pExceptionObject.m128i_i64[0] + 128) )
            {
              std::string::string(&v488, "SmilesV3: Location %d m_primaryOutLink == nullptr", v182);
              Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,int>(
                &pExceptionObject,
                "BASIX_DCT",
                &v488,
                10);
              std::string::_Tidy_deallocate(&v488);
            }
            std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(&pExceptionObject);
            pExceptionObject = 0;
            Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceCheckpoint>(&pExceptionObject);
            if ( pExceptionObject.m128i_i64[0] && *(_BYTE *)(pExceptionObject.m128i_i64[0] + 128) )
            {
              std::_Integral_to_string<char,int>(v510, 10);
              v183 = std::string::string(v501, ":");
              v184 = std::string::string(v502, "\"");
              v185 = std::string::string(v499, "\"");
              v186 = std::operator+<char>(v484, v185, "Location");
              LOBYTE(v187) = v478;
              std::string::string(v507, v187, v186, v184);
              LOBYTE(v188) = v478;
              std::string::string(v545, v188, v507, v183);
              LOBYTE(v189) = v478;
              std::string::string(&v488, v189, v545, v510);
              Microsoft::Basix::Instrumentation::TraceManager::TraceCheckpointMessage<Microsoft::Basix::TraceCheckpoint,std::string>(
                (int)&pExceptionObject,
                (int)"RD_CHECKPOINT",
                0,
                (int)"Smiles",
                "TestPrimaryOutLinkNull",
                "TestPrimaryOutLinkNull",
                (__int64)&v488);
              std::string::_Tidy_deallocate(v545);
              std::string::_Tidy_deallocate(v507);
              std::string::_Tidy_deallocate(v484);
              std::string::_Tidy_deallocate(v499);
              std::string::_Tidy_deallocate(v502);
              std::string::_Tidy_deallocate(v501);
              std::string::_Tidy_deallocate(v510);
            }
            std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(&pExceptionObject);
          }
          v190 = (volatile signed __int32 *)*((_QWORD *)&v543[0] + 1);
          if ( *((_QWORD *)&v543[0] + 1) )
          {
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v543[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v190)(v190);
              if ( _InterlockedExchangeAdd(v190 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v190 + 8LL))(v190);
            }
          }
          std::string::_Tidy_deallocate(&v549);
          goto LABEL_272;
        }
        *(_OWORD *)v545 = 0;
        Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceDebug>(v545);
        if ( v545[0] && *((_BYTE *)v545[0] + 128) )
        {
          std::string::string(
            &v488,
            "SmilesV3: received same primaryOutLinkId(%d) from InformPeerPrimaryLinkId, ignore",
            v145);
          Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceDebug,unsigned short>(
            v545,
            "BASIX_DCT",
            &v488,
            (unsigned __int16)v130);
          std::string::_Tidy_deallocate(&v488);
        }
      }
      else
      {
        *(_OWORD *)v545 = 0;
        if ( v480 )
        {
          Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(v545);
          if ( v545[0] && *((_BYTE *)v545[0] + 128) )
          {
            v139 = *(_DWORD *)(v5 + 3104);
            v140 = *(_DWORD *)(v5 + 3108);
            std::string::string(
              &v488,
              "SmilesV3: primaryOutLink from InformPeerPrimaryLinkId has different epoch(%d), m_currentSwitchEpoch(%d)",
              v137,
              v138);
            Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,unsigned int,unsigned int>(
              (unsigned int)v545,
              (unsigned int)"BASIX_DCT",
              (unsigned int)&v488,
              v140,
              v139);
            std::string::_Tidy_deallocate(&v488);
          }
        }
        else
        {
          Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceDebug>(v545);
          if ( v545[0] && *((_BYTE *)v545[0] + 128) )
          {
            v143 = *(_DWORD *)(v5 + 3104);
            v144 = *(_DWORD *)(v5 + 3108);
            std::string::string(
              &v488,
              "SmilesV3: primaryOutLink from InformPeerPrimaryLinkId has first time different epoch(%d), m_currentSwitchEpoch(%d)",
              v141,
              v142);
            Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceDebug,unsigned int,unsigned int>(
              (unsigned int)v545,
              (unsigned int)"BASIX_DCT",
              (unsigned int)&v488,
              v144,
              v143);
            std::string::_Tidy_deallocate(&v488);
          }
        }
      }
      std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(v545);
    }
    else
    {
      *(_OWORD *)v545 = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceWarning>(v545);
      if ( v545[0] && *((_BYTE *)v545[0] + 128) )
      {
        std::string::string(
          &v488,
          "SmilesV3: primaryOutLink from InformPeerPrimaryLinkId doesn't exist in m_links: id=(%d)",
          v136);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceWarning,unsigned short>(
          v545,
          "BASIX_DCT",
          &v488,
          (unsigned __int16)v130);
        std::string::_Tidy_deallocate(&v488);
      }
      std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(v545);
      *(_WORD *)(v5 + 3112) = v130;
    }
LABEL_272:
    v191 = (volatile signed __int32 *)v551[0];
    if ( v551[0] )
    {
      if ( !_InterlockedDecrement((volatile signed __int32 *)v551[0] + 2) )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v191)(v191);
        if ( !_InterlockedDecrement(v191 + 3) )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v191 + 8LL))(v191);
      }
    }
  }
  if ( (v479 & 1) == 0 )
  {
    v288 = v540[0];
    v227 = (std::_Ref_count_base *)v496;
    v239 = 0;
    goto LABEL_382;
  }
  if ( Microsoft::Basix::Dct::s_bugfixenabled_LinkSwitchStopped_61492275 )
  {
    v192 = *(_QWORD *)(v5 + 2968);
    v193 = v192 <= v36;
    if ( v192 < v36 )
    {
      if ( v36 - v192 < 0x8000000000000000uLL )
        goto LABEL_283;
      v193 = v192 <= v36;
    }
    if ( !v193 && v192 - v36 > 0x8000000000000000uLL )
    {
LABEL_283:
      v507[0] = 0;
      if ( v496 )
        _InterlockedIncrement(v496 + 2);
      v507[0] = *(_OWORD *)v504;
      if ( (unsigned __int8)std::operator!=<Microsoft::Basix::Dct::LinkDataV3,Microsoft::Basix::Dct::LinkDataV3>(
                              v504,
                              &v544) )
      {
        v194 = v541[0];
        pExceptionObject = 0;
        if ( v541[0] )
        {
          Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(&pExceptionObject);
          if ( pExceptionObject.m128i_i64[0] && *(_BYTE *)(pExceptionObject.m128i_i64[0] + 128) )
          {
            v197 = *((_DWORD *)v35 + 38);
            v198 = *(_DWORD *)(v194 + 152);
            std::string::string(
              v510,
              "SmilesV3: peer has just switched its outPrimary Link from link (%d) to link (%d)",
              v195,
              v196);
            Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,unsigned int,unsigned int>(
              (unsigned int)&pExceptionObject,
              (unsigned int)"BASIX_DCT",
              (unsigned int)v510,
              v198,
              v197);
            std::string::_Tidy_deallocate(v510);
          }
          std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(&pExceptionObject);
          pExceptionObject = 0;
          Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceCheckpoint>(&pExceptionObject);
          if ( pExceptionObject.m128i_i64[0] && *(_BYTE *)(pExceptionObject.m128i_i64[0] + 128) )
          {
            v551[0] = (char *)v510;
            std::_Integral_to_string<char,unsigned int>(v484, *((unsigned int *)v35 + 38));
            v199 = std::string::string(v560, ":");
            v200 = std::string::string(v554, "\"");
            v201 = std::string::string(v508, "\"");
            v202 = std::operator+<char>(v509, v201, "NewLinkId");
            LOBYTE(v203) = v478;
            std::string::string(v499, v203, v202, v200);
            LOBYTE(v204) = v478;
            std::string::string(v502, v204, v499, v199);
            LOBYTE(v205) = v478;
            std::string::string(v510, v205, v502, v484);
            v545[0] = (struct std::nothrow_t *)&v488;
            std::_Integral_to_string<char,unsigned int>(v501, *(unsigned int *)(v194 + 152));
            v206 = std::string::string(v512, ":");
            v207 = std::string::string(v524, "\"");
            v208 = std::string::string(v525, "\"");
            v209 = std::operator+<char>(v526, v208, "OldLinkId");
            LOBYTE(v210) = v478;
            std::string::string(v520, v210, v209, v207);
            LOBYTE(v211) = v478;
            std::string::string(v519, v211, v520, v206);
            LOBYTE(v212) = v478;
            std::string::string(&v488, v212, v519, v501);
            v213 = std::string::string(v527, "\"");
            v214 = std::string::string(v528, "\"");
            v215 = std::string::string(v529, ":");
            v216 = std::string::string(v531, "\"");
            v217 = std::string::string(v522, "\"");
            v218 = std::operator+<char>(v523, v217, "Direction");
            LOBYTE(v219) = v478;
            std::string::string(v518, v219, v218, v216);
            LOBYTE(v220) = v478;
            std::string::string(v543, v220, v518, v215);
            LOBYTE(v221) = v478;
            std::string::string(v536, v221, v543, v214);
            v222 = std::operator+<char>(v521, v536, "In");
            LOBYTE(v223) = v478;
            std::string::string(&v549, v223, v222, v213);
            Microsoft::Basix::Instrumentation::TraceManager::TraceCheckpointMessage<Microsoft::Basix::TraceCheckpoint,std::string,std::string,std::string>(
              (int)&pExceptionObject,
              (int)"RD_CHECKPOINT",
              0,
              (int)"Smiles",
              "LinkSwitchConfirmed",
              "LinkSwitchConfirmed",
              (__int64)&v549,
              (__int64)&v488,
              (__int64)v510);
            std::string::_Tidy_deallocate(v521);
            std::string::_Tidy_deallocate(v536);
            std::string::_Tidy_deallocate(v543);
            std::string::_Tidy_deallocate(v518);
            std::string::_Tidy_deallocate(v523);
            std::string::_Tidy_deallocate(v522);
            std::string::_Tidy_deallocate(v531);
            std::string::_Tidy_deallocate(v529);
            std::string::_Tidy_deallocate(v528);
            std::string::_Tidy_deallocate(v527);
            std::string::_Tidy_deallocate(v519);
            std::string::_Tidy_deallocate(v520);
            std::string::_Tidy_deallocate(v526);
            std::string::_Tidy_deallocate(v525);
            std::string::_Tidy_deallocate(v524);
            std::string::_Tidy_deallocate(v512);
            std::string::_Tidy_deallocate(v501);
            std::string::_Tidy_deallocate(v502);
            std::string::_Tidy_deallocate(v499);
            std::string::_Tidy_deallocate(v509);
            std::string::_Tidy_deallocate(v508);
            std::string::_Tidy_deallocate(v554);
            std::string::_Tidy_deallocate(v560);
            std::string::_Tidy_deallocate(v484);
          }
        }
        else
        {
          Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceWarning>(&pExceptionObject);
          if ( pExceptionObject.m128i_i64[0] && *(_BYTE *)(pExceptionObject.m128i_i64[0] + 128) )
          {
            v225 = *((_DWORD *)v35 + 38);
            std::string::string(
              v484,
              "SmilesV3: peer has just set its outPrimary link to link (%d) for the first time",
              v224);
            Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceWarning,unsigned long>(
              &pExceptionObject,
              "BASIX_DCT",
              v484,
              v225);
            std::string::_Tidy_deallocate(v484);
          }
        }
        std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(&pExceptionObject);
        pExceptionObject = 0;
        if ( v544.m128i_i64[1] )
          _InterlockedIncrement((volatile signed __int32 *)(v544.m128i_i64[1] + 8));
        pExceptionObject = v23;
        LOBYTE(v226) = 1;
        Microsoft::Basix::Dct::Smiles<Microsoft::Basix::Dct::LinkDataDisabled>::ChangePrimary(
          v5,
          &pExceptionObject,
          v226);
        std::shared_ptr<Microsoft::RdpNano::RendezvousSource::RendezvousContext>::operator=(v504, &v544);
        v227 = v504[1];
        v496 = (volatile signed __int32 *)v504[1];
        v228 = v504[0];
        v541[0] = (size_t)v504[0];
      }
      else
      {
        v227 = (std::_Ref_count_base *)v496;
        v228 = (std::_Ref_count_base *)v541[0];
      }
      LOWORD(v543[0]) = *((_WORD *)v228 + 76);
      v480 = 0;
      if ( !(unsigned __int8)std::_Atomic_storage<unsigned short,2>::compare_exchange_strong(v5 + 3088, v543, 0, 5) )
      {
        if ( !(unsigned __int8)std::operator!=<Microsoft::Basix::Dct::LinkDataV3,Microsoft::Basix::Dct::LinkDataV3>(
                                 v507,
                                 v504) )
        {
LABEL_308:
          v234 = *(_QWORD *)(v5 + 3096);
          v235 = Microsoft::Basix::Dct::SmilesV3::GetCurrentTimeInMsFromBase((Microsoft::Basix::Dct::SmilesV3 *)v5)
               - v234;
          LOWORD(v543[0]) = *(_WORD *)(*(__int64 (__fastcall **)(size_t))&boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>.Data1)(v5 + 3088);
          if ( LOWORD(v543[0]) && v235 > 0x7D0 )
          {
            pExceptionObject = 0;
            Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(&pExceptionObject);
            if ( pExceptionObject.m128i_i64[0] && *(_BYTE *)(pExceptionObject.m128i_i64[0] + 128) )
            {
              v238 = *(_BYTE *)(v5 + 3090);
              std::string::string(
                v484,
                "SmilesV3: m_switchInfo is set for too long (%dms) before a valid linkSwitchConfirmation, force to unbloc"
                "k MarkSwitch (to(%d), epoch(%d))",
                v236,
                v237,
                (_DWORD)v470);
              Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,unsigned int,unsigned short,unsigned char>(
                (unsigned int)&pExceptionObject,
                (unsigned int)"BASIX_DCT",
                (unsigned int)v484,
                v235,
                v543[0],
                v238);
              std::string::_Tidy_deallocate(v484);
            }
            std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(&pExceptionObject);
            v239 = 0;
            LOWORD(v543[0]) = 0;
            v240 = std::_Atomic_reinterpret_as<short,unsigned short>(v543);
            *(_WORD *)(*(__int64 (__fastcall **)(size_t))&boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>.Data1)(v5 + 3088) = v240;
          }
          else
          {
            v239 = 0;
            if ( !v480 )
            {
LABEL_324:
              std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(v507);
LABEL_370:
              v288 = v540[0];
              goto LABEL_371;
            }
          }
          *(_OWORD *)v536 = 0;
          Microsoft::Basix::Containers::IterationSafeStore<std::shared_ptr<Microsoft::Basix::Dct::FailoverBridge::Transport>,std::equal_to<std::shared_ptr<Microsoft::Basix::Dct::FailoverBridge::Transport>>>::iterator::iterator(
            v536,
            v5 + 1528);
          pExceptionObject = 0;
          Microsoft::Basix::Containers::IterationSafeStore<std::shared_ptr<Microsoft::Basix::Dct::FailoverBridge::Transport>,std::equal_to<std::shared_ptr<Microsoft::Basix::Dct::FailoverBridge::Transport>>>::iterator::iterator(
            &pExceptionObject,
            0);
          while ( v536[0] != (void *)pExceptionObject.m128i_i64[0]
               || v536[0] && v536[1] != (void *)pExceptionObject.m128i_i64[1] )
          {
            *(_WORD *)(*(_QWORD *)v536[1] + 240LL) = 0;
            Microsoft::Basix::Containers::IterationSafeStore<std::weak_ptr<Microsoft::Basix::Instrumentation::IActivityListener>,Microsoft::Basix::Algorithm::owner_equals<std::weak_ptr<Microsoft::Basix::Instrumentation::IActivityListener>>>::iterator::operator++(v536);
          }
          Microsoft::Basix::Containers::IterationSafeStore<std::weak_ptr<Microsoft::Basix::Pattern::Factory<std::shared_ptr<Microsoft::Basix::Dct::IChannel>,Microsoft::Basix::Pattern::BasicNameAndType<std::string>,std::shared_ptr<Microsoft::Basix::Dct::IChannel> const &,boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>> const &>>,Microsoft::Basix::Algorithm::owner_equals<std::weak_ptr<Microsoft::Basix::Pattern::Factory<std::shared_ptr<Microsoft::Basix::Dct::IChannel>,Microsoft::Basix::Pattern::BasicNameAndType<std::string>,std::shared_ptr<Microsoft::Basix::Dct::IChannel> const &,boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>> const &>>>>::iterator::~iterator(
            &pExceptionObject,
            v241);
          Microsoft::Basix::Containers::IterationSafeStore<std::weak_ptr<Microsoft::Basix::Pattern::Factory<std::shared_ptr<Microsoft::Basix::Dct::IChannel>,Microsoft::Basix::Pattern::BasicNameAndType<std::string>,std::shared_ptr<Microsoft::Basix::Dct::IChannel> const &,boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>> const &>>,Microsoft::Basix::Algorithm::owner_equals<std::weak_ptr<Microsoft::Basix::Pattern::Factory<std::shared_ptr<Microsoft::Basix::Dct::IChannel>,Microsoft::Basix::Pattern::BasicNameAndType<std::string>,std::shared_ptr<Microsoft::Basix::Dct::IChannel> const &,boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>> const &>>>>::iterator::~iterator(
            v536,
            v243);
          goto LABEL_324;
        }
        pExceptionObject = 0;
        Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(&pExceptionObject);
        if ( pExceptionObject.m128i_i64[0] && *(_BYTE *)(pExceptionObject.m128i_i64[0] + 128) )
        {
          v231 = *(_BYTE *)(v5 + 3090);
          v232 = *(_DWORD *)(v541[0] + 152);
          std::string::string(
            v484,
            "SmilesV3: the link the peer switched to (%d) does not match with what is intended(%d), force unblocking the "
            "markSwitch with epoch(%d)",
            v229,
            v230,
            (_DWORD)v470);
          Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,unsigned int,unsigned short,unsigned char>(
            (unsigned int)&pExceptionObject,
            (unsigned int)"BASIX_DCT",
            (unsigned int)v484,
            v232,
            v543[0],
            v231);
          std::string::_Tidy_deallocate(v484);
        }
        std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(&pExceptionObject);
        LOWORD(v543[0]) = 0;
        v233 = std::_Atomic_reinterpret_as<short,unsigned short>(v543);
        *(_WORD *)(*(__int64 (__fastcall **)(size_t))&boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>.Data1)(v5 + 3088) = v233;
      }
      v480 = 1;
      goto LABEL_308;
    }
    v244 = v36 + 100;
    v245 = v192 <= v36 + 100;
    if ( v192 != v36 + 100 )
    {
      if ( v192 >= v36 + 100 )
      {
LABEL_329:
        if ( v245 || v192 - v244 <= 0x8000000000000000uLL )
        {
          pExceptionObject = 0;
          Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceWarning>(&pExceptionObject);
          v239 = 0;
          if ( pExceptionObject.m128i_i64[0] && *(_BYTE *)(pExceptionObject.m128i_i64[0] + 128) )
          {
            v248 = *(_QWORD *)(v5 + 2968);
            std::string::string(
              v484,
              "SmilesV3: received primaryIn packet with counter(%d) which is much smaller than current top primary counte"
              "r(%d), reset it so it doesn't log endlessly",
              v246,
              v247);
            Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceWarning,Microsoft::Basix::Algorithm::SequenceNumber<64,unsigned __int64>,Microsoft::Basix::Algorithm::SequenceNumber<64,unsigned __int64>>(
              (unsigned int)&pExceptionObject,
              (unsigned int)"BASIX_DCT",
              (unsigned int)v484,
              v36,
              v248);
            std::string::_Tidy_deallocate(v484);
          }
          std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(&pExceptionObject);
          *(_QWORD *)(v5 + 2968) = v36;
          goto LABEL_369;
        }
        goto LABEL_368;
      }
      if ( v244 - v192 >= 0x8000000000000000uLL )
      {
        v245 = v192 <= v244;
        goto LABEL_329;
      }
    }
LABEL_368:
    v239 = 0;
    goto LABEL_369;
  }
  v239 = 0;
  if ( !(unsigned __int8)std::operator!=<Microsoft::Basix::Dct::LinkDataV3,Microsoft::Basix::Dct::LinkDataV3>(
                           v504,
                           &v544) )
  {
LABEL_369:
    v227 = (std::_Ref_count_base *)v496;
    goto LABEL_370;
  }
  v249 = *(_QWORD *)(v5 + 2968);
  v250 = v249 <= v36;
  if ( v249 < v36 )
  {
    if ( v36 - v249 < 0x8000000000000000uLL )
      goto LABEL_341;
    v250 = v249 <= v36;
  }
  if ( v250 || v249 - v36 <= 0x8000000000000000uLL )
    goto LABEL_369;
LABEL_341:
  v251 = v541[0];
  pExceptionObject = 0;
  if ( v541[0] )
  {
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(&pExceptionObject);
    if ( pExceptionObject.m128i_i64[0] && *(_BYTE *)(pExceptionObject.m128i_i64[0] + 128) )
    {
      v254 = *((_DWORD *)v35 + 38);
      v255 = *(_DWORD *)(v251 + 152);
      std::string::string(
        v484,
        "SmilesV3: peer has just switched its outPrimary Link from link (%d) to link (%d)",
        v252,
        v253);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,unsigned int,unsigned int>(
        (unsigned int)&pExceptionObject,
        (unsigned int)"BASIX_DCT",
        (unsigned int)v484,
        v255,
        v254);
      std::string::_Tidy_deallocate(v484);
    }
    std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(&pExceptionObject);
    pExceptionObject = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceCheckpoint>(&pExceptionObject);
    if ( pExceptionObject.m128i_i64[0] && *(_BYTE *)(pExceptionObject.m128i_i64[0] + 128) )
    {
      v551[0] = (char *)v484;
      std::_Integral_to_string<char,unsigned int>(v543, *((unsigned int *)v35 + 38));
      v256 = std::string::string(v521, ":");
      v257 = std::string::string(v523, "\"");
      v258 = std::string::string(v522, "\"");
      v259 = std::operator+<char>(v531, v258, "NewLinkId");
      LOBYTE(v260) = v478;
      std::string::string(v536, v260, v259, v257);
      LOBYTE(v261) = v478;
      std::string::string(&v549, v261, v536, v256);
      LOBYTE(v262) = v478;
      std::string::string(v484, v262, &v549, v543);
      v545[0] = (struct std::nothrow_t *)v499;
      std::_Integral_to_string<char,unsigned int>(&v488, *(unsigned int *)(v251 + 152));
      v263 = std::string::string(v529, ":");
      v264 = std::string::string(v528, "\"");
      v265 = std::string::string(v527, "\"");
      v266 = std::operator+<char>(v526, v265, "OldLinkId");
      LOBYTE(v267) = v478;
      std::string::string(v510, v267, v266, v264);
      LOBYTE(v268) = v478;
      std::string::string(v518, v268, v510, v263);
      LOBYTE(v269) = v478;
      std::string::string(v499, v269, v518, &v488);
      v270 = std::string::string(v525, "\"");
      v271 = std::string::string(v524, "\"");
      v272 = std::string::string(v512, ":");
      v273 = std::string::string(v509, "\"");
      v274 = std::string::string(v508, "\"");
      v275 = std::operator+<char>(v554, v274, "Direction");
      LOBYTE(v276) = v478;
      std::string::string(v519, v276, v275, v273);
      LOBYTE(v277) = v478;
      std::string::string(v520, v277, v519, v272);
      LOBYTE(v278) = v478;
      std::string::string(v501, v278, v520, v271);
      v279 = std::operator+<char>(v560, v501, "In");
      LOBYTE(v280) = v478;
      std::string::string(v502, v280, v279, v270);
      Microsoft::Basix::Instrumentation::TraceManager::TraceCheckpointMessage<Microsoft::Basix::TraceCheckpoint,std::string,std::string,std::string>(
        (int)&pExceptionObject,
        (int)"RD_CHECKPOINT",
        0,
        (int)"Smiles",
        "LinkSwitchConfirmed",
        "LinkSwitchConfirmed",
        (__int64)v502,
        (__int64)v499,
        (__int64)v484);
      std::string::_Tidy_deallocate(v560);
      std::string::_Tidy_deallocate(v501);
      std::string::_Tidy_deallocate(v520);
      std::string::_Tidy_deallocate(v519);
      std::string::_Tidy_deallocate(v554);
      std::string::_Tidy_deallocate(v508);
      std::string::_Tidy_deallocate(v509);
      std::string::_Tidy_deallocate(v512);
      std::string::_Tidy_deallocate(v524);
      std::string::_Tidy_deallocate(v525);
      std::string::_Tidy_deallocate(v518);
      std::string::_Tidy_deallocate(v510);
      std::string::_Tidy_deallocate(v526);
      std::string::_Tidy_deallocate(v527);
      std::string::_Tidy_deallocate(v528);
      std::string::_Tidy_deallocate(v529);
      std::string::_Tidy_deallocate(&v488);
      std::string::_Tidy_deallocate(&v549);
      std::string::_Tidy_deallocate(v536);
      std::string::_Tidy_deallocate(v531);
      std::string::_Tidy_deallocate(v522);
      std::string::_Tidy_deallocate(v523);
      std::string::_Tidy_deallocate(v521);
      std::string::_Tidy_deallocate(v543);
    }
  }
  else
  {
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceWarning>(&pExceptionObject);
    if ( pExceptionObject.m128i_i64[0] && *(_BYTE *)(pExceptionObject.m128i_i64[0] + 128) )
    {
      v282 = *((_DWORD *)v35 + 38);
      std::string::string(v484, "SmilesV3: peer has just set its outPrimary link to link (%d) for the first time", v281);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceWarning,unsigned long>(
        &pExceptionObject,
        "BASIX_DCT",
        v484,
        v282);
      std::string::_Tidy_deallocate(v484);
    }
  }
  std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(&pExceptionObject);
  LOWORD(v543[0]) = 0;
  v283 = std::_Atomic_reinterpret_as<short,unsigned short>(v543);
  v284 = (unsigned __int16 *)(*(__int64 (__fastcall **)(size_t))&boost::core::launder<Microsoft::RdpNano::SecurityCookieHash>.Data1)(v5 + 3088);
  v287 = v283;
  v286 = *v284;
  *v284 = v287;
  v288 = v540[0];
  if ( *(_DWORD *)(v540[0] + 152) != v286 )
  {
    pExceptionObject = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(&pExceptionObject);
    if ( pExceptionObject.m128i_i64[0] && *(_BYTE *)(pExceptionObject.m128i_i64[0] + 128) )
    {
      v291 = *(_DWORD *)(v288 + 152);
      std::string::string(
        v484,
        "SmilesV3: peer has just switched to a link with Id (%d) which is different from the linkId intended(%d)",
        v289,
        v290);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,unsigned int,unsigned short>(
        (unsigned int)&pExceptionObject,
        (unsigned int)"BASIX_DCT",
        (unsigned int)v484,
        v291,
        v286);
      std::string::_Tidy_deallocate(v484);
    }
    std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(&pExceptionObject);
  }
  pExceptionObject = 0;
  v239 = 0;
  if ( v544.m128i_i64[1] )
    _InterlockedIncrement((volatile signed __int32 *)(v544.m128i_i64[1] + 8));
  pExceptionObject = v23;
  LOBYTE(v285) = 1;
  Microsoft::Basix::Dct::Smiles<Microsoft::Basix::Dct::LinkDataDisabled>::ChangePrimary(v5, &pExceptionObject, v285);
  std::shared_ptr<Microsoft::RdpNano::RendezvousSource::RendezvousContext>::operator=(v504, &v544);
  *(_OWORD *)v536 = 0;
  Microsoft::Basix::Containers::IterationSafeStore<std::shared_ptr<Microsoft::Basix::Dct::FailoverBridge::Transport>,std::equal_to<std::shared_ptr<Microsoft::Basix::Dct::FailoverBridge::Transport>>>::iterator::iterator(
    v536,
    v5 + 1528);
  pExceptionObject = 0;
  Microsoft::Basix::Containers::IterationSafeStore<std::shared_ptr<Microsoft::Basix::Dct::FailoverBridge::Transport>,std::equal_to<std::shared_ptr<Microsoft::Basix::Dct::FailoverBridge::Transport>>>::iterator::iterator(
    &pExceptionObject,
    0);
  while ( v536[0] != (void *)pExceptionObject.m128i_i64[0]
       || v536[0] && v536[1] != (void *)pExceptionObject.m128i_i64[1] )
  {
    *(_WORD *)(*(_QWORD *)v536[1] + 240LL) = 0;
    Microsoft::Basix::Containers::IterationSafeStore<std::weak_ptr<Microsoft::Basix::Instrumentation::IActivityListener>,Microsoft::Basix::Algorithm::owner_equals<std::weak_ptr<Microsoft::Basix::Instrumentation::IActivityListener>>>::iterator::operator++(v536);
  }
  Microsoft::Basix::Containers::IterationSafeStore<std::weak_ptr<Microsoft::Basix::Pattern::Factory<std::shared_ptr<Microsoft::Basix::Dct::IChannel>,Microsoft::Basix::Pattern::BasicNameAndType<std::string>,std::shared_ptr<Microsoft::Basix::Dct::IChannel> const &,boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>> const &>>,Microsoft::Basix::Algorithm::owner_equals<std::weak_ptr<Microsoft::Basix::Pattern::Factory<std::shared_ptr<Microsoft::Basix::Dct::IChannel>,Microsoft::Basix::Pattern::BasicNameAndType<std::string>,std::shared_ptr<Microsoft::Basix::Dct::IChannel> const &,boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>> const &>>>>::iterator::~iterator(
    &pExceptionObject,
    v292);
  Microsoft::Basix::Containers::IterationSafeStore<std::weak_ptr<Microsoft::Basix::Pattern::Factory<std::shared_ptr<Microsoft::Basix::Dct::IChannel>,Microsoft::Basix::Pattern::BasicNameAndType<std::string>,std::shared_ptr<Microsoft::Basix::Dct::IChannel> const &,boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>> const &>>,Microsoft::Basix::Algorithm::owner_equals<std::weak_ptr<Microsoft::Basix::Pattern::Factory<std::shared_ptr<Microsoft::Basix::Dct::IChannel>,Microsoft::Basix::Pattern::BasicNameAndType<std::string>,std::shared_ptr<Microsoft::Basix::Dct::IChannel> const &,boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>> const &>>>>::iterator::~iterator(
    v536,
    v294);
  v227 = v504[1];
  v496 = (volatile signed __int32 *)v504[1];
  v541[0] = (size_t)v504[0];
LABEL_371:
  v119 = (_QWORD *)(v5 + 2968);
  v295 = *(_QWORD *)(v5 + 2968);
  v120 = 0x8000000000000000uLL;
  v296 = v295 <= v36;
  if ( v295 < v36 )
  {
    if ( v36 - v295 < 0x8000000000000000uLL )
      goto LABEL_376;
    v296 = v295 <= v36;
  }
  if ( v296 || v295 - v36 <= 0x8000000000000000uLL )
  {
    v297 = 0;
    goto LABEL_378;
  }
LABEL_376:
  v297 = 1;
LABEL_378:
  v298 = v539;
  if ( !v297 )
    v298 = (char *)(v5 + 2968);
  *v119 = *(_QWORD *)v298;
LABEL_382:
  if ( *(_BYTE *)(v5 + 1524)
    && (unsigned __int8)std::operator==<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceCheckpoint>>(
                          *(_QWORD *)(v5 + 1816),
                          0) )
  {
    pExceptionObject = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(&pExceptionObject);
    if ( pExceptionObject.m128i_i64[0] && *(_BYTE *)(pExceptionObject.m128i_i64[0] + 128) )
    {
      std::string::string(v484, "SmilesV3: Location %d m_primaryOutLink == nullptr", v299);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,int>(
        &pExceptionObject,
        "BASIX_DCT",
        v484,
        12);
      std::string::_Tidy_deallocate(v484);
    }
    std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(&pExceptionObject);
    pExceptionObject = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceCheckpoint>(&pExceptionObject);
    if ( pExceptionObject.m128i_i64[0] && *(_BYTE *)(pExceptionObject.m128i_i64[0] + 128) )
    {
      std::_Integral_to_string<char,int>(v501, 12);
      v300 = std::string::string(v509, ":");
      v301 = std::string::string(v508, "\"");
      v302 = std::string::string(v554, "\"");
      v303 = std::operator+<char>(v560, v302, "Location");
      LOBYTE(v304) = v478;
      std::string::string(v502, v304, v303, v301);
      LOBYTE(v305) = v478;
      std::string::string(v499, v305, v502, v300);
      LOBYTE(v306) = v478;
      std::string::string(v484, v306, v499, v501);
      Microsoft::Basix::Instrumentation::TraceManager::TraceCheckpointMessage<Microsoft::Basix::TraceCheckpoint,std::string>(
        (int)&pExceptionObject,
        (int)"RD_CHECKPOINT",
        0,
        (int)"Smiles",
        "TestPrimaryOutLinkNull",
        "TestPrimaryOutLinkNull",
        (__int64)v484);
      std::string::_Tidy_deallocate(v499);
      std::string::_Tidy_deallocate(v502);
      std::string::_Tidy_deallocate(v560);
      std::string::_Tidy_deallocate(v554);
      std::string::_Tidy_deallocate(v508);
      std::string::_Tidy_deallocate(v509);
      std::string::_Tidy_deallocate(v501);
      v239 = 0;
    }
    std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(&pExceptionObject);
  }
  if ( (v479 & 8) == 0 )
    goto LABEL_463;
  v307 = *(_QWORD *)(v5 + 2976);
  v308 = v307 <= v36;
  LOBYTE(v119) = v307 == v36;
  if ( v307 != v36 )
  {
    v120 = 0x8000000000000000uLL;
    if ( v307 < v36 )
    {
      if ( v36 - v307 < 0x8000000000000000uLL )
        goto LABEL_421;
      v308 = v307 <= v36;
    }
    if ( v308 || (v307 -= v36, v307 <= 0x8000000000000000uLL) )
    {
      v309 = *(_QWORD *)Microsoft::Basix::Instrumentation::TraceManager::s_delayedTraceManager(
                          v307,
                          v119,
                          0x8000000000000000uLL);
      std::string::string(v484, "LinkSwitch");
      DelayedTraceRecord = (Microsoft::Basix::Instrumentation::DelayedTraceManager::DelayedTraceRecord **)Microsoft::Basix::Instrumentation::DelayedTraceManager::GetDelayedTraceRecord(v309, v484, 0);
      std::string::_Tidy_deallocate(v484);
      if ( *DelayedTraceRecord )
      {
        BufferCount = 0;
        v311 = "false";
        if ( (unsigned __int8)boost::multi_index::detail::operator==<boost::multi_index::detail::ordered_index_node<boost::multi_index::detail::null_augment_policy,boost::multi_index::detail::index_node_base<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>,std::allocator<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>>>>>(
                                &v544,
                                v504) )
          v311 = "true";
        do
        {
          Buffer = Microsoft::Basix::Instrumentation::DelayedTraceManager::DelayedTraceRecord::GetBuffer(
                     *DelayedTraceRecord,
                     &BufferCount);
          if ( (unsigned int)Microsoft::Basix::Algorithm::SlidingStats<double,5,1,1>::num(*(_QWORD *)(v288 + 192)) )
            v312 = Microsoft::Basix::Algorithm::SlidingStats<double,20,1,1>::nmin(*(_QWORD *)(v288 + 192));
          else
            v312 = DOUBLE_1000_0;
          v313 = Microsoft::Basix::ToString<enum Microsoft::Basix::Dct::ISmiles::LinkType>(v560, v288 + 80, 0, 6);
          if ( *(_QWORD *)(v313 + 24) > 0xFu )
            v313 = *(_QWORD *)v313;
          Buffer = (char *)snprintf(
                             Buffer,
                             BufferCount,
                             "ExpiredCounter:%lld,linkId:%d(%s),IsPrimary:(%s),delay:%d",
                             v36,
                             *(_DWORD *)(v288 + 152),
                             (const char *)v313,
                             v311,
                             (int)v312);
          std::string::_Tidy_deallocate(v560);
          if ( (unsigned __int64)Buffer < BufferCount )
            break;
          BufferCount = (size_t)Buffer;
          ++v239;
        }
        while ( v239 < 2 );
        Microsoft::Basix::Instrumentation::DelayedTraceManager::DelayedTraceRecord::Finalize(
          *DelayedTraceRecord,
          4,
          "BASIX_DCT");
        LODWORD(v21) = v548;
        v5 = v550;
      }
      pExceptionObject = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceDebug>(&pExceptionObject);
      if ( pExceptionObject.m128i_i64[0] && *(_BYTE *)(pExceptionObject.m128i_i64[0] + 128) )
      {
        v316 = *(_QWORD *)(v5 + 2976);
        v317 = *(_DWORD *)(v288 + 152);
        std::string::string(
          v484,
          "SmilesV3: on link(%d) received sync with older counter(%d), compared to the current sync counter(%d), ignore",
          v314,
          v315,
          (_DWORD)v470);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceDebug,unsigned int,Microsoft::Basix::Algorithm::SequenceNumber<64,unsigned __int64>,Microsoft::Basix::Algorithm::SequenceNumber<64,unsigned __int64>>(
          (unsigned int)&pExceptionObject,
          (unsigned int)"BASIX_DCT",
          (unsigned int)v484,
          v317,
          v36,
          v316);
        std::string::_Tidy_deallocate(v484);
      }
      v318 = (volatile signed __int32 *)pExceptionObject.m128i_i64[1];
      if ( pExceptionObject.m128i_i64[1] )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(pExceptionObject.m128i_i64[1] + 8), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v318)(v318);
          if ( _InterlockedExchangeAdd(v318 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v318 + 8LL))(v318);
        }
      }
      v319 = v496;
      if ( v496 )
      {
        if ( _InterlockedExchangeAdd(v496 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v319)(v319);
          if ( _InterlockedExchangeAdd(v319 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v319 + 8LL))(v319);
        }
      }
      goto LABEL_420;
    }
  }
LABEL_421:
  if ( (_BYTE)v119 )
  {
    v321 = *(_QWORD *)Microsoft::Basix::Instrumentation::TraceManager::s_delayedTraceManager(v307, v119, v120);
    std::string::string(v484, "LinkSwitch");
    v322 = (Microsoft::Basix::Instrumentation::DelayedTraceManager::DelayedTraceRecord **)Microsoft::Basix::Instrumentation::DelayedTraceManager::GetDelayedTraceRecord(
                                                                                            v321,
                                                                                            v484,
                                                                                            0);
    std::string::_Tidy_deallocate(v484);
    if ( *v322 )
    {
      v541[0] = 0;
      v323 = "false";
      if ( (unsigned __int8)boost::multi_index::detail::operator==<boost::multi_index::detail::ordered_index_node<boost::multi_index::detail::null_augment_policy,boost::multi_index::detail::index_node_base<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>,std::allocator<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>>>>>(
                              &v544,
                              v504) )
        v323 = "true";
      do
      {
        Buffer = Microsoft::Basix::Instrumentation::DelayedTraceManager::DelayedTraceRecord::GetBuffer(*v322, v541);
        if ( (unsigned int)Microsoft::Basix::Algorithm::SlidingStats<double,5,1,1>::num(*(_QWORD *)(v288 + 192)) )
          v324 = Microsoft::Basix::Algorithm::SlidingStats<double,20,1,1>::nmin(*(_QWORD *)(v288 + 192));
        else
          v324 = DOUBLE_1000_0;
        v325 = Microsoft::Basix::ToString<enum Microsoft::Basix::Dct::ISmiles::LinkType>(v560, v288 + 80, 0, 6);
        if ( *(_QWORD *)(v325 + 24) > 0xFu )
          v325 = *(_QWORD *)v325;
        Buffer = (char *)snprintf(
                           Buffer,
                           v541[0],
                           "SameCounter:%lld,linkId:%d(%s),IsPrimary:(%s),delay:%d",
                           v36,
                           *(_DWORD *)(v288 + 152),
                           (const char *)v325,
                           v323,
                           (int)v324);
        std::string::_Tidy_deallocate(v560);
        if ( (unsigned __int64)Buffer < v541[0] )
          break;
        v541[0] = (size_t)Buffer;
        ++v239;
      }
      while ( v239 < 2 );
      Microsoft::Basix::Instrumentation::DelayedTraceManager::DelayedTraceRecord::Finalize(*v322, 4, "BASIX_DCT");
      LODWORD(v21) = v548;
      v5 = v550;
    }
    v478 = 1;
    v326 = boost::multi_index::detail::operator==<boost::multi_index::detail::ordered_index_node<boost::multi_index::detail::null_augment_policy,boost::multi_index::detail::index_node_base<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>,std::allocator<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>>>>>(
             &v544,
             v504);
    pExceptionObject = 0;
    if ( v326 )
    {
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceDebug>(&pExceptionObject);
      if ( pExceptionObject.m128i_i64[0] && *(_BYTE *)(pExceptionObject.m128i_i64[0] + 128) )
      {
        v329 = *(_DWORD *)(v288 + 152);
        std::string::string(
          v484,
          "SmilesV3: on peer-primary link(%d) received sync with same current counter(%d)",
          v327,
          v328);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceDebug,unsigned int,Microsoft::Basix::Algorithm::SequenceNumber<64,unsigned __int64>>(
          (unsigned int)&pExceptionObject,
          (unsigned int)"BASIX_DCT",
          (unsigned int)v484,
          v329,
          v36);
        std::string::_Tidy_deallocate(v484);
      }
      std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(&pExceptionObject);
      v330 = BufferCount;
      if ( BufferCount <= *(_QWORD *)(v5 + 2992) )
      {
        pExceptionObject = 0;
        Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceDebug>(&pExceptionObject);
        if ( pExceptionObject.m128i_i64[0] && *(_BYTE *)(pExceptionObject.m128i_i64[0] + 128) )
        {
          _mm_lfence();
          v335 = *(_DWORD *)(v5 + 3016);
          v336 = *(_DWORD *)(v288 + 152);
          std::string::string(
            v484,
            "SmilesV3: would be timer not off, stay on the primary link(%d). already delayedCount=%d ",
            v333,
            v334);
          Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceDebug,unsigned int,unsigned int>(
            (unsigned int)&pExceptionObject,
            (unsigned int)"BASIX_DCT",
            (unsigned int)v484,
            v336,
            v335);
          std::string::_Tidy_deallocate(v484);
        }
        std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(&pExceptionObject);
        ++*(_DWORD *)(v5 + 3016);
      }
      else
      {
        _mm_lfence();
        pExceptionObject = 0;
        Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(&pExceptionObject);
        if ( pExceptionObject.m128i_i64[0] && *(_BYTE *)(pExceptionObject.m128i_i64[0] + 128) )
        {
          std::string::string(v484, "SmilesV3: would be timer off, calling MarkSwitchToNoLock()");
          Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,>(
            &pExceptionObject,
            "BASIX_DCT",
            v484);
          std::string::_Tidy_deallocate(v484);
        }
        std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(&pExceptionObject);
        v560[0] = 2;
        v561 = 0;
        v562 = 0;
        v563 = 0;
        v564 = 0;
        v565 = 0;
        LOWORD(v543[0]) = *(_WORD *)(v5 + 3000);
        std::vector<short>::_Emplace_reallocate<short>(&v561, 0, v543);
        v331 = v330 - *(_QWORD *)(v5 + 2992);
        if ( v331 > 0x7FFF )
          LOWORD(v331) = 0x7FFF;
        LOWORD(v543[0]) = v331;
        if ( *((_QWORD *)&v561 + 1) == v562 )
        {
          std::vector<short>::_Emplace_reallocate<short>(&v561, *((_QWORD *)&v561 + 1), v543);
        }
        else
        {
          **((_WORD **)&v561 + 1) = v331;
          *((_QWORD *)&v561 + 1) += 2LL;
        }
        pExceptionObject = 0;
        v332 = Microsoft::Basix::Dct::SmilesV3::MarkSwitchToNoLock(v5, v536, v560, &pExceptionObject);
        std::shared_ptr<Microsoft::Basix::Dct::AsioEndpointAddress<boost::asio::ip::udp>>::operator=(&v503, v332);
        std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(v536);
        std::vector<short>::_Tidy(&v561);
        v17 = _mm_load_si128(&v503);
      }
      *(_QWORD *)(v5 + 2992) = -1;
      *(_DWORD *)(v5 + 2208) = 0;
      if ( *(_QWORD *)Microsoft::Basix::Chrono::GetCurrentTimeInMs(&Buffer) >= *(_QWORD *)(v5 + 3048) )
        LODWORD(v21) = 0;
      else
        v21 = (Microsoft::Basix::Instrumentation::DelayedTraceManager::DelayedTraceRecord **)(*(_QWORD *)(v5 + 3048)
                                                                                            - *(_QWORD *)Microsoft::Basix::Chrono::GetCurrentTimeInMs(v539));
      if ( !*(_BYTE *)(v5 + 1524)
        || !(unsigned __int8)std::operator==<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceCheckpoint>>(
                               *(_QWORD *)(v5 + 1816),
                               0) )
      {
        goto LABEL_463;
      }
      pExceptionObject = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(&pExceptionObject);
      if ( pExceptionObject.m128i_i64[0] && *(_BYTE *)(pExceptionObject.m128i_i64[0] + 128) )
      {
        std::string::string(v484, "SmilesV3: Location %d m_primaryOutLink == nullptr", v337);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,int>(
          &pExceptionObject,
          "BASIX_DCT",
          v484,
          13);
        std::string::_Tidy_deallocate(v484);
      }
      std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(&pExceptionObject);
      pExceptionObject = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceCheckpoint>(&pExceptionObject);
      if ( pExceptionObject.m128i_i64[0] && *(_BYTE *)(pExceptionObject.m128i_i64[0] + 128) )
      {
        std::_Integral_to_string<char,int>(v501, 13);
        v338 = std::string::string(v509, ":");
        v339 = std::string::string(v508, "\"");
        v340 = std::string::string(v554, "\"");
        v341 = std::operator+<char>(v560, v340, "Location");
        LOBYTE(v342) = v478;
        std::string::string(v502, v342, v341, v339);
        LOBYTE(v343) = v478;
        std::string::string(v499, v343, v502, v338);
        LOBYTE(v344) = v478;
        std::string::string(v484, v344, v499, v501);
        Microsoft::Basix::Instrumentation::TraceManager::TraceCheckpointMessage<Microsoft::Basix::TraceCheckpoint,std::string>(
          (int)&pExceptionObject,
          (int)"RD_CHECKPOINT",
          0,
          (int)"Smiles",
          "TestPrimaryOutLinkNull",
          "TestPrimaryOutLinkNull",
          (__int64)v484);
        std::string::_Tidy_deallocate(v499);
        std::string::_Tidy_deallocate(v502);
        std::string::_Tidy_deallocate(v560);
        std::string::_Tidy_deallocate(v554);
        std::string::_Tidy_deallocate(v508);
        std::string::_Tidy_deallocate(v509);
        std::string::_Tidy_deallocate(v501);
      }
    }
    else
    {
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceDebug>(&pExceptionObject);
      if ( pExceptionObject.m128i_i64[0] && *(_BYTE *)(pExceptionObject.m128i_i64[0] + 128) )
      {
        v348 = *(_DWORD *)(v288 + 152);
        std::string::string(
          v484,
          "SmilesV3: on peer-secondary link(%d) received sync with same current counter(%d)",
          v346,
          v347);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceDebug,unsigned int,Microsoft::Basix::Algorithm::SequenceNumber<64,unsigned __int64>>(
          (unsigned int)&pExceptionObject,
          (unsigned int)"BASIX_DCT",
          (unsigned int)v484,
          v348,
          v36);
        std::string::_Tidy_deallocate(v484);
      }
    }
    std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(&pExceptionObject);
LABEL_463:
    v320 = v17.m128i_i64[0];
LABEL_464:
    v345 = v496;
    if ( v496 )
    {
      if ( _InterlockedExchangeAdd(v496 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *, _QWORD *, unsigned __int64))v345)(v345, v119, v120);
        if ( _InterlockedExchangeAdd(v345 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v345 + 8LL))(v345);
      }
    }
    std::vector<short>::_Tidy(&v567);
    goto LABEL_469;
  }
  if ( !(unsigned __int8)std::operator==<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceCheckpoint>>(
                           v504,
                           0) )
  {
    v360 = *(_QWORD *)((__int64 (*)(void))Microsoft::Basix::Instrumentation::TraceManager::s_delayedTraceManager)();
    std::string::string(v484, "LinkSwitch");
    LOBYTE(v361) = 1;
    *(_QWORD *)v539 = Microsoft::Basix::Instrumentation::DelayedTraceManager::GetDelayedTraceRecord(v360, v484, v361);
    std::string::_Tidy_deallocate(v484);
    v362 = "false";
    if ( **(_QWORD **)v539 )
    {
      v540[0] = 0;
      v363 = 0;
      v364 = boost::multi_index::detail::operator==<boost::multi_index::detail::ordered_index_node<boost::multi_index::detail::null_augment_policy,boost::multi_index::detail::index_node_base<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>,std::allocator<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>>>>>(
               &v544,
               v504);
      v365 = "false";
      if ( v364 )
        v365 = "true";
      v366 = v365;
      v367 = *(Microsoft::Basix::Instrumentation::DelayedTraceManager::DelayedTraceRecord ***)v539;
      do
      {
        v551[0] = Microsoft::Basix::Instrumentation::DelayedTraceManager::DelayedTraceRecord::GetBuffer(*v367, v540);
        v494 = (int)Microsoft::Basix::Dct::LinkDataV3::GetMinDelayIn((Microsoft::Basix::Dct::LinkDataV3 *)v288);
        v368 = Microsoft::Basix::ToString<enum Microsoft::Basix::Dct::ISmiles::LinkType>(v560, v288 + 80, 0, 6);
        if ( *(_QWORD *)(v368 + 24) > 0xFu )
          v368 = *(_QWORD *)v368;
        v551[0] = (char *)snprintf(
                            v551[0],
                            v540[0],
                            "NewCounter:%lld,linkId:%d(%s),IsPrimary:(%s),delay:%d",
                            v36,
                            *(_DWORD *)(v288 + 152),
                            (const char *)v368,
                            v366,
                            v494);
        std::string::_Tidy_deallocate(v560);
        if ( v551[0] < (char *)v540[0] )
          break;
        v540[0] = (size_t)v551[0];
        ++v363;
      }
      while ( v363 < 2 );
      Microsoft::Basix::Instrumentation::DelayedTraceManager::DelayedTraceRecord::Finalize(*v367, 4, "BASIX_DCT");
      LODWORD(v21) = v548;
      v5 = v550;
      v227 = (std::_Ref_count_base *)v496;
    }
    *(_QWORD *)(v5 + 2976) = v36;
    *(_QWORD *)(v5 + 2984) = BufferCount;
    v369 = boost::multi_index::detail::operator==<boost::multi_index::detail::ordered_index_node<boost::multi_index::detail::null_augment_policy,boost::multi_index::detail::index_node_base<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>,std::allocator<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>>>>>(
             &v544,
             v504);
    pExceptionObject = 0;
    if ( v369 )
    {
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceDebug>(&pExceptionObject);
      if ( pExceptionObject.m128i_i64[0] && *(_BYTE *)(pExceptionObject.m128i_i64[0] + 128) )
      {
        v372 = *(_DWORD *)(v288 + 152);
        std::string::string(v484, "SmilesV3:  peer-primary link(%d) receives new sync counter(%d)", v370, v371);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceDebug,unsigned int,Microsoft::Basix::Algorithm::SequenceNumber<64,unsigned __int64>>(
          (unsigned int)&pExceptionObject,
          (unsigned int)"BASIX_DCT",
          (unsigned int)v484,
          v372,
          v36);
        std::string::_Tidy_deallocate(v484);
      }
      std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(&pExceptionObject);
      *(_DWORD *)(v5 + 3016) = 0;
      if ( !v227 )
        goto LABEL_420;
      v373 = v227;
      goto LABEL_508;
    }
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceDebug>(&pExceptionObject);
    if ( pExceptionObject.m128i_i64[0] && *(_BYTE *)(pExceptionObject.m128i_i64[0] + 128) )
    {
      v376 = *(_DWORD *)(v288 + 152);
      std::string::string(v484, "SmilesV3: peer-secondary link(%d) receives new sync counter(%d)", v374, v375);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceDebug,unsigned int,Microsoft::Basix::Algorithm::SequenceNumber<64,unsigned __int64>>(
        (unsigned int)&pExceptionObject,
        (unsigned int)"BASIX_DCT",
        (unsigned int)v484,
        v376,
        v36);
      std::string::_Tidy_deallocate(v484);
    }
    std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(&pExceptionObject);
    v119 = (_QWORD *)v541[0];
    v377 = *(_QWORD *)(v541[0] + 344);
    v551[0] = *(char **)(v541[0] + 336);
    v378 = v36 - v377;
    *(_QWORD *)v539 = v36 - v377;
    v120 = 0;
    if ( *(_BYTE *)(v5 + 1524) )
    {
      if ( (unsigned __int8)std::operator==<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceCheckpoint>>(
                              *(_QWORD *)(v5 + 1816),
                              0) )
      {
        pExceptionObject = 0;
        Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(&pExceptionObject);
        if ( pExceptionObject.m128i_i64[0] && *(_BYTE *)(pExceptionObject.m128i_i64[0] + 128) )
        {
          std::string::string(v484, "SmilesV3: Location %d m_primaryOutLink == nullptr", v379);
          Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,int>(
            &pExceptionObject,
            "BASIX_DCT",
            v484,
            15);
          std::string::_Tidy_deallocate(v484);
        }
        std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(&pExceptionObject);
        pExceptionObject = 0;
        Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceCheckpoint>(&pExceptionObject);
        if ( pExceptionObject.m128i_i64[0] && *(_BYTE *)(pExceptionObject.m128i_i64[0] + 128) )
        {
          std::_Integral_to_string<char,int>(v501, 15);
          v380 = std::string::string(v509, ":");
          v381 = std::string::string(v508, "\"");
          v382 = std::string::string(v554, "\"");
          v383 = std::operator+<char>(v560, v382, "Location");
          LOBYTE(v384) = v478;
          std::string::string(v502, v384, v383, v381);
          LOBYTE(v385) = v478;
          std::string::string(v499, v385, v502, v380);
          LOBYTE(v386) = v478;
          std::string::string(v484, v386, v499, v501);
          Microsoft::Basix::Instrumentation::TraceManager::TraceCheckpointMessage<Microsoft::Basix::TraceCheckpoint,std::string>(
            (int)&pExceptionObject,
            (int)"RD_CHECKPOINT",
            0,
            (int)"Smiles",
            "TestPrimaryOutLinkNull",
            "TestPrimaryOutLinkNull",
            (__int64)v484);
          std::string::_Tidy_deallocate(v499);
          std::string::_Tidy_deallocate(v502);
          std::string::_Tidy_deallocate(v560);
          std::string::_Tidy_deallocate(v554);
          std::string::_Tidy_deallocate(v508);
          std::string::_Tidy_deallocate(v509);
          std::string::_Tidy_deallocate(v501);
          v362 = "false";
          v378 = *(_WORD *)v539;
        }
        std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(&pExceptionObject);
      }
      v119 = (_QWORD *)v541[0];
    }
    if ( v378 < 0 )
    {
      pExceptionObject = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceDebug>(&pExceptionObject);
      if ( pExceptionObject.m128i_i64[0] && *(_BYTE *)(pExceptionObject.m128i_i64[0] + 128) )
      {
        std::string::string(v484, "SmilesV3: primary sync packet is missing, but the gap is negative. ignored");
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceDebug,>(
          &pExceptionObject,
          "BASIX_DCT",
          v484);
        std::string::_Tidy_deallocate(v484);
      }
      std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(&pExceptionObject);
      if ( !v496 )
        goto LABEL_420;
      v373 = (std::_Ref_count_base *)v496;
LABEL_508:
      std::_Ref_count_base::_Decref(v373);
LABEL_420:
      std::vector<short>::_Tidy(&v567);
      v320 = 0;
      goto LABEL_469;
    }
    if ( v378 <= (unsigned __int16)v495 + *(__int16 *)(v5 + 2912) )
    {
      if ( *(_DWORD *)(v5 + 3016) <= *(_DWORD *)(v5 + 2916) )
      {
        if ( !*(_DWORD *)(v5 + 2208) )
        {
          v412 = Microsoft::Basix::Algorithm::SlidingStats<double,5,1,0>::navg(v119[23]);
          v413 = Microsoft::Basix::Algorithm::SlidingStats<double,5,1,0>::navg(*(_QWORD *)(v288 + 184));
          v414 = LOBYTE(v413);
          v415 = v413 + v412;
          v416 = 0;
          if ( v413 + v412 >= 9.223372036854776e18 )
          {
            v415 = v415 - 9.223372036854776e18;
            if ( v415 < 9.223372036854776e18 )
              v416 = 0x8000000000000000uLL;
          }
          v417 = *(unsigned int *)(v5 + 2920) * (v416 + (unsigned int)(int)v415);
          v418 = v105
               - v106
               - Microsoft::Basix::Dct::LinkDataV3::GetAveDelayIn((Microsoft::Basix::Dct::LinkDataV3 *)v288);
          v419 = 0;
          v420 = v418;
          if ( v418 >= 9.223372036854776e18 )
          {
            v420 = v418 - 9.223372036854776e18;
            if ( v418 - 9.223372036854776e18 < 9.223372036854776e18 )
              v419 = 0x8000000000000000uLL;
          }
          v421 = v419 + (unsigned int)(int)v420;
          v422 = 5;
          if ( v417 > v421 )
            v422 = v417 - v421;
          *(_QWORD *)(v5 + 3000) = v422;
          if ( v422 < 0x14 )
            LODWORD(v422) = 20;
          pExceptionObject = 0;
          Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceDebug>(&pExceptionObject);
          if ( pExceptionObject.m128i_i64[0] && *(_BYTE *)(pExceptionObject.m128i_i64[0] + 128) )
          {
            v425 = *(_QWORD *)(v5 + 3000);
            std::string::string(
              v484,
              "SmilesV3: Set timer: finalTimeoutInMs(%d), timeoutInMs(%d), timeoutAdjustment(%f), adjustedTimeoutInMs(%d)"
              ", now(%lld), receivedSendTime(%lld), PeerPrimaryLinkAveVar(%f), currentlinkAveVar(%f)",
              v423,
              v424,
              *(double *)&v470,
              (_DWORD)Str,
              v472,
              v473,
              *(double *)&v474,
              v475);
            Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceDebug,unsigned __int64,unsigned __int64,double,unsigned __int64,unsigned __int64,unsigned __int64,double,double>(
              (unsigned int)&pExceptionObject,
              (unsigned int)"BASIX_DCT",
              (unsigned int)v484,
              v422,
              v417,
              SLOBYTE(v418),
              v425,
              BufferCount,
              (char)Buffer,
              SLOBYTE(v412),
              v414);
            std::string::_Tidy_deallocate(v484);
          }
          std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(&pExceptionObject);
          *(_QWORD *)(v5 + 2992) = *(_QWORD *)(v5 + 3000) + BufferCount;
          *(_DWORD *)(v5 + 2208) = 1;
          v426 = *(_QWORD *)((__int64 (*)(void))Microsoft::Basix::Instrumentation::TraceManager::s_delayedTraceManager)();
          std::string::string(v484, "LinkSwitch");
          v427 = (Microsoft::Basix::Instrumentation::DelayedTraceManager::DelayedTraceRecord **)Microsoft::Basix::Instrumentation::DelayedTraceManager::GetDelayedTraceRecord(
                                                                                                  v426,
                                                                                                  v484,
                                                                                                  0);
          std::string::_Tidy_deallocate(v484);
          if ( *v427 )
          {
            v548 = 0;
            for ( i = 0; i < 2; ++i )
            {
              v429 = Microsoft::Basix::Instrumentation::DelayedTraceManager::DelayedTraceRecord::GetBuffer(*v427, &v548);
              v430 = Microsoft::Basix::ToString<enum Microsoft::Basix::Dct::ISmiles::LinkType>(v560, v288 + 80, 0, 6);
              if ( *(_QWORD *)(v430 + 24) > 0xFu )
                v430 = *(_QWORD *)v430;
              v431 = snprintf(
                       v429,
                       v548,
                       "WouldbeTimerStart:%lld,linkId:%d(%s),finalTimeoutInMs:%d",
                       v36,
                       *(_DWORD *)(v288 + 152),
                       (const char *)v430,
                       v422);
              std::string::_Tidy_deallocate(v560);
              if ( v431 < v548 )
                break;
              v548 = v431;
            }
            Microsoft::Basix::Instrumentation::DelayedTraceManager::DelayedTraceRecord::Finalize(*v427, 4, "BASIX_DCT");
            v5 = v550;
          }
          LODWORD(v21) = v422;
        }
        v320 = 0;
        goto LABEL_594;
      }
      pExceptionObject = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(&pExceptionObject);
      if ( pExceptionObject.m128i_i64[0] && *(_BYTE *)(pExceptionObject.m128i_i64[0] + 128) )
      {
        v404 = *(_DWORD *)(v5 + 3016);
        std::string::string(v484, "SmilesV3: primary link is tardy for a consecutive %d times, switch now", v403);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,unsigned int>(
          &pExceptionObject,
          "BASIX_DCT",
          v484,
          v404);
        std::string::_Tidy_deallocate(v484);
      }
      std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(&pExceptionObject);
      v554[0] = 1;
      v555 = 0;
      v556 = 0;
      v557 = 0;
      v558 = 0;
      v559 = 0;
      LOWORD(v543[0]) = *(_WORD *)(v5 + 3000);
      std::vector<short>::_Emplace_one_at_back<short>(&v555, v543);
      pExceptionObject = 0;
      v405 = Microsoft::Basix::Dct::SmilesV3::MarkSwitchToNoLock(v5, v536, v554, &pExceptionObject);
      std::shared_ptr<Microsoft::Basix::Dct::AsioEndpointAddress<boost::asio::ip::udp>>::operator=(&v503, v405);
      std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(v536);
      v320 = v503.m128i_i64[0];
      if ( v503.m128i_i64[0] )
      {
        v406 = *(_QWORD *)((__int64 (*)(void))Microsoft::Basix::Instrumentation::TraceManager::s_delayedTraceManager)();
        std::string::string(v484, "LinkSwitch");
        v407 = (_QWORD *)Microsoft::Basix::Instrumentation::DelayedTraceManager::GetDelayedTraceRecord(v406, v484, 0);
        *(_QWORD *)v539 = v407;
        std::string::_Tidy_deallocate(v484);
        if ( *v407 )
        {
          v550 = 0;
          v408 = 0;
          if ( (unsigned __int8)boost::multi_index::detail::operator==<boost::multi_index::detail::ordered_index_node<boost::multi_index::detail::null_augment_policy,boost::multi_index::detail::index_node_base<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>,std::allocator<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>>>>>(
                                  &v544,
                                  v504) )
            v362 = "true";
          v21 = *(Microsoft::Basix::Instrumentation::DelayedTraceManager::DelayedTraceRecord ***)v539;
          do
          {
            Buffer = Microsoft::Basix::Instrumentation::DelayedTraceManager::DelayedTraceRecord::GetBuffer(*v21, &v550);
            v495 = *(_DWORD *)(v5 + 3016);
            v409 = Microsoft::Basix::ToString<enum Microsoft::Basix::Dct::ISmiles::LinkType>(v560, v288 + 80, 0, 6);
            if ( *(_QWORD *)(v409 + 24) > 0xFu )
              v409 = *(_QWORD *)v409;
            Buffer = (char *)snprintf(
                               Buffer,
                               v550,
                               "linkid:%lld,linkId:%d(%s),IsPrimary:(%s),primary link is tardy for a consecutive %d times - switch now ",
                               v36,
                               *(_DWORD *)(v288 + 152),
                               (const char *)v409,
                               v362,
                               v495);
            std::string::_Tidy_deallocate(v560);
            if ( (unsigned __int64)Buffer < v550 )
              break;
            v550 = (size_t)Buffer;
            ++v408;
          }
          while ( v408 < 2 );
          Microsoft::Basix::Instrumentation::DelayedTraceManager::DelayedTraceRecord::Finalize(*v21, 4, "BASIX_DCT");
          LODWORD(v21) = v548;
          v320 = v503.m128i_i64[0];
        }
        v410 = *(_QWORD *)((__int64 (*)(void))Microsoft::Basix::Instrumentation::TraceManager::s_delayedTraceManager)();
        std::string::string(v484, "LinkSwitch");
        LOBYTE(v411) = 1;
        Microsoft::Basix::Instrumentation::DelayedTraceManager::complete(v410, v484, v411);
        std::string::_Tidy_deallocate(v484);
      }
    }
    else
    {
      pExceptionObject = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(&pExceptionObject);
      v389 = 0;
      if ( pExceptionObject.m128i_i64[0] && *(_BYTE *)(pExceptionObject.m128i_i64[0] + 128) )
      {
        v390 = *(_DWORD *)(v288 + 152);
        std::string::string(
          v484,
          "SmilesV3: attempting markSwitch due to primary link gap is too big: peer-secondary link(%d) receives new sync counter(%d), ",
          v387,
          v388);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,unsigned int,Microsoft::Basix::Algorithm::SequenceNumber<64,unsigned __int64>>(
          (unsigned int)&pExceptionObject,
          (unsigned int)"BASIX_DCT",
          (unsigned int)v484,
          v390,
          v36);
        std::string::_Tidy_deallocate(v484);
        v389 = 0;
      }
      std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(&pExceptionObject);
      v554[0] = 3;
      v555 = 0;
      v556 = 0;
      v557 = 0;
      v558 = 0;
      v559 = 0;
      LOWORD(v543[0]) = v378;
      std::vector<short>::_Emplace_reallocate<short>(&v555, 0, v543);
      LOWORD(v543[0]) = v495;
      if ( *((__int16 **)&v555 + 1) == v556 )
      {
        std::vector<short>::_Emplace_reallocate<short>(&v555, *((_QWORD *)&v555 + 1), v543);
        v391 = (__int16 *)*((_QWORD *)&v555 + 1);
      }
      else
      {
        **((_WORD **)&v555 + 1) = v495;
        v391 = (__int16 *)(*((_QWORD *)&v555 + 1) + 2LL);
        *((_QWORD *)&v555 + 1) += 2LL;
      }
      v392 = BufferCount - LOWORD(v551[0]);
      if ( BufferCount - (unsigned __int64)v551[0] > 0x7FFF )
        v392 = 0x7FFF;
      LOWORD(v543[0]) = v392;
      if ( v391 == v556 )
      {
        std::vector<short>::_Emplace_reallocate<short>(&v555, v391, v543);
      }
      else
      {
        *v391 = v392;
        *((_QWORD *)&v555 + 1) += 2LL;
      }
      pExceptionObject = 0;
      v393 = Microsoft::Basix::Dct::SmilesV3::MarkSwitchToNoLock(v5, v536, v554, &pExceptionObject);
      std::shared_ptr<Microsoft::Basix::Dct::AsioEndpointAddress<boost::asio::ip::udp>>::operator=(&v503, v393);
      std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(v536);
      v320 = v503.m128i_i64[0];
      if ( v503.m128i_i64[0] )
      {
        pExceptionObject = 0;
        Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(&pExceptionObject);
        if ( pExceptionObject.m128i_i64[0] && *(_BYTE *)(pExceptionObject.m128i_i64[0] + 128) )
        {
          v396 = *(_DWORD *)(v541[0] + 152);
          std::string::string(
            v484,
            "SmilesV3: primary link gap is too big. switch immediately and putting the current primaryInLink(%d) into sus"
            "pended state: counterGap(%d), counterReceived(%d), lastPrimaryCounterReceived(%d)",
            v394,
            v395,
            (_DWORD)v470,
            (_DWORD)Str);
          Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,unsigned int,short,Microsoft::Basix::Algorithm::SequenceNumber<64,unsigned __int64>,Microsoft::Basix::Algorithm::SequenceNumber<64,unsigned __int64>>(
            (unsigned int)&pExceptionObject,
            (unsigned int)"BASIX_DCT",
            (unsigned int)v484,
            v396,
            v539[0],
            v36,
            v377);
          std::string::_Tidy_deallocate(v484);
          v389 = 0;
        }
        std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(&pExceptionObject);
        v397 = *(_QWORD *)((__int64 (*)(void))Microsoft::Basix::Instrumentation::TraceManager::s_delayedTraceManager)();
        std::string::string(v484, "LinkSwitch");
        v398 = (_QWORD *)Microsoft::Basix::Instrumentation::DelayedTraceManager::GetDelayedTraceRecord(v397, v484, 0);
        *(_QWORD *)v539 = v398;
        std::string::_Tidy_deallocate(v484);
        if ( *v398 )
        {
          BufferCount = 0;
          v399 = "false";
          if ( (unsigned __int8)boost::multi_index::detail::operator==<boost::multi_index::detail::ordered_index_node<boost::multi_index::detail::null_augment_policy,boost::multi_index::detail::index_node_base<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>,std::allocator<std::pair<std::string const,boost::property_tree::basic_ptree<std::string,std::string,std::less<std::string>>>>>>>(
                                  &v544,
                                  v504) )
            v399 = "true";
          v21 = *(Microsoft::Basix::Instrumentation::DelayedTraceManager::DelayedTraceRecord ***)v539;
          do
          {
            Buffer = Microsoft::Basix::Instrumentation::DelayedTraceManager::DelayedTraceRecord::GetBuffer(
                       *v21,
                       &BufferCount);
            v400 = Microsoft::Basix::ToString<enum Microsoft::Basix::Dct::ISmiles::LinkType>(v560, v288 + 80, 0, 6);
            if ( *(_QWORD *)(v400 + 24) > 0xFu )
              v400 = *(_QWORD *)v400;
            Buffer = (char *)snprintf(
                               Buffer,
                               BufferCount,
                               "linkid:%lld,linkId:%d(%s),IsPrimary:(%s),SmilesV3: primary link gap is too big. switch immediately ",
                               v36,
                               *(_DWORD *)(v288 + 152),
                               (const char *)v400,
                               v399);
            std::string::_Tidy_deallocate(v560);
            if ( (unsigned __int64)Buffer < BufferCount )
              break;
            BufferCount = (size_t)Buffer;
            ++v389;
          }
          while ( v389 < 2 );
          Microsoft::Basix::Instrumentation::DelayedTraceManager::DelayedTraceRecord::Finalize(*v21, 4, "BASIX_DCT");
          LODWORD(v21) = v548;
          v5 = v550;
        }
        v401 = *(_QWORD *)((__int64 (*)(void))Microsoft::Basix::Instrumentation::TraceManager::s_delayedTraceManager)();
        std::string::string(v484, "LinkSwitch");
        LOBYTE(v402) = 1;
        Microsoft::Basix::Instrumentation::DelayedTraceManager::complete(v401, v484, v402);
        std::string::_Tidy_deallocate(v484);
      }
    }
    std::vector<short>::_Tidy(&v555);
    v17 = _mm_load_si128(&v503);
LABEL_594:
    if ( *(_BYTE *)(v5 + 1524)
      && (unsigned __int8)std::operator==<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceCheckpoint>>(
                            *(_QWORD *)(v5 + 1816),
                            0) )
    {
      pExceptionObject = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(&pExceptionObject);
      if ( pExceptionObject.m128i_i64[0] && *(_BYTE *)(pExceptionObject.m128i_i64[0] + 128) )
      {
        std::string::string(v484, "SmilesV3: Location %d m_primaryOutLink == nullptr", v432);
        Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,int>(
          &pExceptionObject,
          "BASIX_DCT",
          v484,
          16);
        std::string::_Tidy_deallocate(v484);
      }
      std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(&pExceptionObject);
      pExceptionObject = 0;
      Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceCheckpoint>(&pExceptionObject);
      if ( pExceptionObject.m128i_i64[0] && *(_BYTE *)(pExceptionObject.m128i_i64[0] + 128) )
      {
        std::_Integral_to_string<char,int>(v501, 16);
        v433 = std::string::string(v509, ":");
        v434 = std::string::string(v508, "\"");
        v435 = std::string::string(v554, "\"");
        v436 = std::operator+<char>(v560, v435, "Location");
        LOBYTE(v437) = v478;
        std::string::string(v502, v437, v436, v434);
        LOBYTE(v438) = v478;
        std::string::string(v499, v438, v502, v433);
        LOBYTE(v439) = v478;
        std::string::string(v484, v439, v499, v501);
        Microsoft::Basix::Instrumentation::TraceManager::TraceCheckpointMessage<Microsoft::Basix::TraceCheckpoint,std::string>(
          (int)&pExceptionObject,
          (int)"RD_CHECKPOINT",
          0,
          (int)"Smiles",
          "TestPrimaryOutLinkNull",
          "TestPrimaryOutLinkNull",
          (__int64)v484);
        std::string::_Tidy_deallocate(v499);
        std::string::_Tidy_deallocate(v502);
        std::string::_Tidy_deallocate(v560);
        std::string::_Tidy_deallocate(v554);
        std::string::_Tidy_deallocate(v508);
        std::string::_Tidy_deallocate(v509);
        std::string::_Tidy_deallocate(v501);
      }
      std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(&pExceptionObject);
    }
    goto LABEL_464;
  }
  pExceptionObject = 0;
  Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(&pExceptionObject);
  if ( pExceptionObject.m128i_i64[0] && *(_BYTE *)(pExceptionObject.m128i_i64[0] + 128) )
  {
    v350 = *(_DWORD *)(v288 + 152);
    std::string::string(
      v484,
      "SmilesV3: received packets for the secondary link before primary link packets were ever received. Mark switching p"
      "eer primary link to this link (%d) ",
      v349);
    Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,unsigned int>(
      &pExceptionObject,
      "BASIX_DCT",
      v484,
      v350);
    std::string::_Tidy_deallocate(v484);
  }
  std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(&pExceptionObject);
  v512[0] = 4;
  v513 = 0;
  v514 = 0;
  v515 = 0;
  v516 = 0;
  v517 = 0;
  pExceptionObject = 0;
  v351 = Microsoft::Basix::Dct::SmilesV3::MarkSwitchToNoLock(v5, v536, v512, &pExceptionObject);
  std::shared_ptr<Microsoft::Basix::Dct::AsioEndpointAddress<boost::asio::ip::udp>>::operator=(&v503, v351);
  std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(v536);
  if ( *(_BYTE *)(v5 + 1524)
    && (unsigned __int8)std::operator==<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceCheckpoint>>(
                          *(_QWORD *)(v5 + 1816),
                          0) )
  {
    pExceptionObject = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(&pExceptionObject);
    if ( pExceptionObject.m128i_i64[0] && *(_BYTE *)(pExceptionObject.m128i_i64[0] + 128) )
    {
      std::string::string(v484, "SmilesV3: Location %d m_primaryOutLink == nullptr", v352);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,int>(
        &pExceptionObject,
        "BASIX_DCT",
        v484,
        14);
      std::string::_Tidy_deallocate(v484);
    }
    std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(&pExceptionObject);
    pExceptionObject = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceCheckpoint>(&pExceptionObject);
    if ( pExceptionObject.m128i_i64[0] && *(_BYTE *)(pExceptionObject.m128i_i64[0] + 128) )
    {
      std::_Integral_to_string<char,int>(v501, 14);
      v353 = std::string::string(v509, ":");
      v354 = std::string::string(v508, "\"");
      v355 = std::string::string(v554, "\"");
      v356 = std::operator+<char>(v560, v355, "Location");
      LOBYTE(v357) = v478;
      std::string::string(v502, v357, v356, v354);
      LOBYTE(v358) = v478;
      std::string::string(v499, v358, v502, v353);
      LOBYTE(v359) = v478;
      std::string::string(v484, v359, v499, v501);
      Microsoft::Basix::Instrumentation::TraceManager::TraceCheckpointMessage<Microsoft::Basix::TraceCheckpoint,std::string>(
        (int)&pExceptionObject,
        (int)"RD_CHECKPOINT",
        0,
        (int)"Smiles",
        "TestPrimaryOutLinkNull",
        "TestPrimaryOutLinkNull",
        (__int64)v484);
      std::string::_Tidy_deallocate(v499);
      std::string::_Tidy_deallocate(v502);
      std::string::_Tidy_deallocate(v560);
      std::string::_Tidy_deallocate(v554);
      std::string::_Tidy_deallocate(v508);
      std::string::_Tidy_deallocate(v509);
      std::string::_Tidy_deallocate(v501);
    }
    std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(&pExceptionObject);
  }
  std::vector<short>::_Tidy(&v513);
  if ( v227 )
    std::_Ref_count_base::_Decref(v227);
  std::vector<short>::_Tidy(&v567);
  v320 = v503.m128i_i64[0];
  v17 = _mm_load_si128(&v503);
LABEL_469:
  if ( *(_BYTE *)(v5 + 3177) && *(_QWORD *)(v5 + 3152) && !*(_DWORD *)(v5 + 2208) )
  {
    LODWORD(v21) = 0;
    *(_DWORD *)(v5 + 2208) = 2;
LABEL_604:
    v440 = Microsoft::Basix::SharedFromThisVirtualBase::GetWeakPtr<Microsoft::Basix::ITimerCallback>(
             v5 + *(int *)(*(_QWORD *)(v5 + 8) + 4LL) + 8LL,
             &pExceptionObject);
    Buffer = (char *)(unsigned int)v21;
    Microsoft::Basix::Timer::Setup(v5 + 3024, &Buffer, v440);
    goto LABEL_605;
  }
  if ( (int)v21 >= 0 )
    goto LABEL_604;
LABEL_605:
  if ( Microsoft::Basix::Dct::s_bugfixenabled_RendezvousLinkSwitch_61430490 && *(_BYTE *)(v5 + 3020) && !v320 )
  {
    *(_BYTE *)(v5 + 3020) = 0;
    v566[0] = 8;
    v567 = 0;
    v568 = 0;
    v569 = 0;
    v570 = 0;
    v571 = 0;
    pExceptionObject = 0;
    v441 = Microsoft::Basix::Dct::SmilesV3::MarkSwitchToNoLock(v5, v536, v566, &pExceptionObject);
    std::shared_ptr<Microsoft::Basix::Dct::AsioEndpointAddress<boost::asio::ip::udp>>::operator=(&v503, v441);
    std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(v536);
    std::vector<short>::_Tidy(&v567);
    v320 = v503.m128i_i64[0];
    v17 = _mm_load_si128(&v503);
  }
  Mtx_unlock(v500);
  v442 = (volatile signed __int32 *)_mm_srli_si128(v17, 8).m128i_u64[0];
  v443 = (volatile signed __int32 *)v573;
  v444 = *((_QWORD *)&v572 + 1);
  if ( v320 )
  {
    v549.m256i_i8[0] = v572;
    *(__int32 *)((char *)v549.m256i_i32 + 2) = *(_DWORD *)((char *)&v572 + 2);
    *(_OWORD *)&v549.m256i_u64[1] = 0;
    if ( (_QWORD)v573 )
      _InterlockedIncrement((volatile signed __int32 *)(v573 + 8));
    v549.m256i_i64[1] = v444;
    v549.m256i_i64[2] = (__int64)v443;
    v549.m256i_i16[12] = WORD4(v573);
    pExceptionObject = 0;
    if ( v442 )
      _InterlockedIncrement(v442 + 2);
    pExceptionObject = v17;
    Microsoft::Basix::Dct::SmilesV3::SendMarkSwitch(v5, &pExceptionObject, &v549);
  }
  if ( v444 )
  {
    Microsoft::Basix::Dct::SmilesV3::ProcessLinkOperation(
      (Microsoft::Basix::Dct::SmilesV3 *)v5,
      (const struct Microsoft::Basix::Dct::OperationOnLinkId *)&v572);
    v443 = (volatile signed __int32 *)v573;
  }
  if ( *((_QWORD *)&v574 + 1) )
    Microsoft::Basix::Dct::SmilesV3::ProcessLinkOperation(
      (Microsoft::Basix::Dct::SmilesV3 *)v5,
      (const struct Microsoft::Basix::Dct::OperationOnLinkId *)&v574);
  if ( v493 )
  {
    Microsoft::Basix::Dct::SmilesV3::FlushOutPrimaryLink((Microsoft::Basix::Dct::SmilesV3 *)v5);
    Microsoft::Basix::Dct::DCTBaseChannelImplNoProp::FireOnStackLayoutChanged(
      (Microsoft::Basix::Dct::DCTBaseChannelImplNoProp *)v5,
      0);
  }
  if ( *(_BYTE *)(v5 + 1524)
    && (unsigned __int8)std::operator==<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceCheckpoint>>(
                          *(_QWORD *)(v5 + 1816),
                          0) )
  {
    pExceptionObject = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(&pExceptionObject);
    if ( pExceptionObject.m128i_i64[0] && *(_BYTE *)(pExceptionObject.m128i_i64[0] + 128) )
    {
      std::string::string(v484, "SmilesV3: Location %d m_primaryOutLink == nullptr", v445);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,int>(
        &pExceptionObject,
        "BASIX_DCT",
        v484,
        17);
      std::string::_Tidy_deallocate(v484);
    }
    v446 = (volatile signed __int32 *)pExceptionObject.m128i_i64[1];
    if ( pExceptionObject.m128i_i64[1] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(pExceptionObject.m128i_i64[1] + 8), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v446)(v446);
        if ( _InterlockedExchangeAdd(v446 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v446 + 8LL))(v446);
      }
    }
    pExceptionObject = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceCheckpoint>(&pExceptionObject);
    if ( pExceptionObject.m128i_i64[0] && *(_BYTE *)(pExceptionObject.m128i_i64[0] + 128) )
    {
      std::_Integral_to_string<char,int>(v501, 17);
      v447 = std::string::string(v509, ":");
      v448 = std::string::string(v508, "\"");
      v449 = std::string::string(v554, "\"");
      v450 = std::operator+<char>(v560, v449, "Location");
      LOBYTE(v451) = v478;
      std::string::string(v502, v451, v450, v448);
      LOBYTE(v452) = v478;
      std::string::string(v499, v452, v502, v447);
      LOBYTE(v453) = v478;
      std::string::string(v484, v453, v499, v501);
      Microsoft::Basix::Instrumentation::TraceManager::TraceCheckpointMessage<Microsoft::Basix::TraceCheckpoint,std::string>(
        (int)&pExceptionObject,
        (int)"RD_CHECKPOINT",
        0,
        (int)"Smiles",
        "TestPrimaryOutLinkNull",
        "TestPrimaryOutLinkNull",
        (__int64)v484);
      std::string::_Tidy_deallocate(v499);
      std::string::_Tidy_deallocate(v502);
      std::string::_Tidy_deallocate(v560);
      std::string::_Tidy_deallocate(v554);
      std::string::_Tidy_deallocate(v508);
      std::string::_Tidy_deallocate(v509);
      std::string::_Tidy_deallocate(v501);
    }
    v454 = (volatile signed __int32 *)pExceptionObject.m128i_i64[1];
    if ( pExceptionObject.m128i_i64[1] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(pExceptionObject.m128i_i64[1] + 8), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v454)(v454);
        if ( _InterlockedExchangeAdd(v454 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v454 + 8LL))(v454);
      }
    }
  }
  if ( (v479 & 4) == 0 && !v478 )
  {
    v455 = v498;
    v456 = std::_Func_impl_no_alloc<_lambda_8fe06ae25614185e6bdd0a582616d3ae_,void,>::_Get(*v498);
    if ( *(_QWORD *)(v456 + 32) != *(_QWORD *)(v456 + 24) )
      Microsoft::Basix::Dct::DCTBaseChannelImplNoProp::FireOnDataReceived(v5, v455);
  }
  if ( *(_BYTE *)(v5 + 1524)
    && (unsigned __int8)std::operator==<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceCheckpoint>>(
                          *(_QWORD *)(v5 + 1816),
                          0) )
  {
    pExceptionObject = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(&pExceptionObject);
    if ( pExceptionObject.m128i_i64[0] && *(_BYTE *)(pExceptionObject.m128i_i64[0] + 128) )
    {
      std::string::string(v484, "SmilesV3: Location %d m_primaryOutLink == nullptr", v457);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,int>(
        &pExceptionObject,
        "BASIX_DCT",
        v484,
        18);
      std::string::_Tidy_deallocate(v484);
    }
    v458 = (volatile signed __int32 *)pExceptionObject.m128i_i64[1];
    if ( pExceptionObject.m128i_i64[1] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(pExceptionObject.m128i_i64[1] + 8), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v458)(v458);
        if ( _InterlockedExchangeAdd(v458 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v458 + 8LL))(v458);
      }
    }
    pExceptionObject = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceCheckpoint>(&pExceptionObject);
    if ( pExceptionObject.m128i_i64[0] && *(_BYTE *)(pExceptionObject.m128i_i64[0] + 128) )
    {
      std::_Integral_to_string<char,int>(v501, 18);
      v459 = std::string::string(v509, ":");
      v460 = std::string::string(v508, "\"");
      v461 = std::string::string(v554, "\"");
      v462 = std::operator+<char>(v560, v461, "Location");
      LOBYTE(v463) = v478;
      std::string::string(v502, v463, v462, v460);
      LOBYTE(v464) = v478;
      std::string::string(v499, v464, v502, v459);
      LOBYTE(v465) = v478;
      std::string::string(v484, v465, v499, v501);
      Microsoft::Basix::Instrumentation::TraceManager::TraceCheckpointMessage<Microsoft::Basix::TraceCheckpoint,std::string>(
        (int)&pExceptionObject,
        (int)"RD_CHECKPOINT",
        0,
        (int)"Smiles",
        "TestPrimaryOutLinkNull",
        "TestPrimaryOutLinkNull",
        (__int64)v484);
      std::string::_Tidy_deallocate(v499);
      std::string::_Tidy_deallocate(v502);
      std::string::_Tidy_deallocate(v560);
      std::string::_Tidy_deallocate(v554);
      std::string::_Tidy_deallocate(v508);
      std::string::_Tidy_deallocate(v509);
      std::string::_Tidy_deallocate(v501);
    }
    v466 = (volatile signed __int32 *)pExceptionObject.m128i_i64[1];
    if ( pExceptionObject.m128i_i64[1] )
    {
      if ( !_InterlockedDecrement((volatile signed __int32 *)(pExceptionObject.m128i_i64[1] + 8)) )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v466)(v466);
        if ( !_InterlockedDecrement(v466 + 3) )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v466 + 8LL))(v466);
      }
    }
  }
  v467 = (volatile signed __int32 *)v575;
  if ( (_QWORD)v575 )
  {
    if ( !_InterlockedDecrement((volatile signed __int32 *)(v575 + 8)) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v467)(v467);
      if ( !_InterlockedDecrement(v467 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v467 + 8LL))(v467);
    }
  }
  if ( v443 )
  {
    if ( !_InterlockedDecrement(v443 + 2) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v443)(v443);
      if ( !_InterlockedDecrement(v443 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v443 + 8LL))(v443);
    }
  }
  if ( v442 )
  {
    if ( !_InterlockedDecrement(v442 + 2) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v442)(v442);
      if ( !_InterlockedDecrement(v442 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v442 + 8LL))(v442);
    }
  }
  v468 = (volatile signed __int32 *)v544.m128i_i64[1];
  if ( v544.m128i_i64[1] )
  {
    if ( !_InterlockedDecrement((volatile signed __int32 *)(v544.m128i_i64[1] + 8)) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v468)(v468);
      if ( !_InterlockedDecrement(v468 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v468 + 8LL))(v468);
    }
  }
  v7 = *(volatile signed __int32 **)(v511 + 8);
  if ( v7 )
  {
    v8 = _InterlockedExchangeAdd(v7 + 3, 0xFFFFFFFF) == 1;
LABEL_675:
    if ( v8 )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 8LL))(v7);
  }
}

```

## disassembly

```asm
0x18026da30  mov     [rsp-8+arg_18], rbx
0x18026da35  push    rbp
0x18026da36  push    rsi
0x18026da37  push    rdi
0x18026da38  push    r12
0x18026da3a  push    r13
0x18026da3c  push    r14
0x18026da3e  push    r15
0x18026da40  lea     rbp, [rsp-5F0h]
0x18026da48  mov     eax, 6F0h
0x18026da4d  call    _alloca_probe
0x18026da52  sub     rsp, rax
0x18026da55  movaps  [rsp+720h+var_40], xmm6
0x18026da5d  movaps  [rsp+720h+var_50], xmm7
0x18026da65  movaps  [rsp+720h+var_60], xmm8
0x18026da6e  movaps  [rsp+720h+var_70], xmm9
0x18026da77  movaps  [rsp+720h+var_80], xmm10
0x18026da80  movaps  [rsp+720h+var_90], xmm11
0x18026da89  movaps  [rsp+720h+var_A0], xmm12
0x18026da92  movaps  [rsp+720h+var_B0], xmm13
0x18026da9b  mov     rax, cs:__security_cookie
0x18026daa2  xor     rax, rsp
0x18026daa5  mov     [rbp+620h+var_C0], rax
0x18026daac  mov     rdi, r8
0x18026daaf  mov     [rbp+620h+var_510], r8
0x18026dab6  mov     rbx, rdx
0x18026dab9  mov     [rbp+620h+var_630], rdx
0x18026dabd  mov     r13, rcx
0x18026dac0  mov     [rbp+620h+var_1B8], rcx
0x18026dac7  mov     [rbp+620h+var_358], r8
0x18026dace  xor     r15d, r15d
0x18026dad1  mov     eax, r15d
0x18026dad4  mov     [rbp+620h+var_64C], eax
0x18026dad7  mov     dword ptr [rbp+620h+var_238], eax
0x18026dadd  xorps   xmm0, xmm0
0x18026dae0  movups  [rbp+620h+var_210], xmm0
0x18026dae7  lea     rdx, [rbp+620h+var_210]
0x18026daee  mov     rcx, r8
0x18026daf1  call    ?lock@?$weak_ptr@VIAgentDelegate@ICE@Dct@Basix@Microsoft@@@std@@QEBA?AV?$shared_ptr@VIAgentDelegate@ICE@Dct@Basix@Microsoft@@@2@XZ; std::weak_ptr<Microsoft::Basix::Dct::ICE::IAgentDelegate>::lock(void)
0x18026daf6  nop
0x18026daf7  xor     edx, edx
0x18026daf9  lea     rcx, [rbp+620h+var_210]
0x18026db00  call    ??$?8V?$Event@VTraceCheckpoint@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@YA_NAEBV?$shared_ptr@V?$Event@VTraceCheckpoint@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@0@$$T@Z; std::operator==<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceCheckpoint>>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceCheckpoint>> const &,std::nullptr_t)
0x18026db05  test    al, al
0x18026db07  jz      short loc_18026DB33
0x18026db09  lea     rcx, [rbp+620h+var_210]; void *
0x18026db10  call    ??1?$shared_ptr@VMicrosoft_Basix_Instrumentation_RioBuffersReceive_Logger@Microsoft_Streaming_Nano_Network@GlobalProviderList@@@std@@QEAA@XZ; std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(void)
0x18026db15  nop
0x18026db16  mov     rcx, [rdi+8]
0x18026db1a  test    rcx, rcx
0x18026db1d  jz      loc_180273841
0x18026db23  or      eax, 0FFFFFFFFh
0x18026db26  lock xadd [rcx+0Ch], eax
0x18026db2b  cmp     eax, 1
0x18026db2e  jmp     loc_180273832
0x18026db33  cmp     [r13+5F4h], r15b
0x18026db3a  jz      loc_18026DD3A
0x18026db40  xor     edx, edx
0x18026db42  mov     rcx, [r13+718h]
0x18026db49  call    ??$?8V?$Event@VTraceCheckpoint@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@YA_NAEBV?$shared_ptr@V?$Event@VTraceCheckpoint@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@0@$$T@Z; std::operator==<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceCheckpoint>>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceCheckpoint>> const &,std::nullptr_t)
0x18026db4e  test    al, al
0x18026db50  jz      loc_18026DD3A
0x18026db56  xorps   xmm0, xmm0
0x18026db59  movups  xmmword ptr [rbp+620h+var_290], xmm0
0x18026db60  lea     rcx, [rbp+620h+var_290]
0x18026db67  call    ??$SelectEvent@VTraceNormal@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(void)
0x18026db6c  nop
0x18026db6d  mov     edi, 7
0x18026db72  mov     rax, [rbp+620h+var_290]
0x18026db79  test    rax, rax
0x18026db7c  jz      short loc_18026DBBD
0x18026db7e  cmp     [rax+80h], r15b
0x18026db85  jz      short loc_18026DBBD
0x18026db87  lea     rdx, aSmilesv3Locati; "SmilesV3: Location %d m_primaryOutLink "...
0x18026db8e  lea     rcx, [rbp+620h+var_670]
0x18026db92  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18026db97  nop
0x18026db98  mov     r9d, edi
0x18026db9b  lea     r8, [rbp+620h+var_670]
0x18026db9f  lea     rdx, aBasixDct; "BASIX_DCT"
0x18026dba6  lea     rcx, [rbp+620h+var_290]
0x18026dbad  call    ??$TraceMessage@VTraceNormal@Basix@Microsoft@@H@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@H@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,int>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceNormal>> const &,char const *,std::string const &,int)
0x18026dbb2  nop
0x18026dbb3  lea     rcx, [rbp+620h+var_670]
0x18026dbb7  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18026dbbc  nop
0x18026dbbd  lea     rcx, [rbp+620h+var_290]; void *
0x18026dbc4  call    ??1?$shared_ptr@VMicrosoft_Basix_Instrumentation_RioBuffersReceive_Logger@Microsoft_Streaming_Nano_Network@GlobalProviderList@@@std@@QEAA@XZ; std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(void)
0x18026dbc9  xorps   xmm0, xmm0
0x18026dbcc  movups  xmmword ptr [rbp+620h+var_290], xmm0
0x18026dbd3  lea     rcx, [rbp+620h+var_290]
0x18026dbda  call    ??$SelectEvent@VTraceCheckpoint@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceCheckpoint@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceCheckpoint>(void)
0x18026dbdf  nop
0x18026dbe0  mov     rax, [rbp+620h+var_290]
0x18026dbe7  test    rax, rax
0x18026dbea  jz      loc_18026DD2E
0x18026dbf0  cmp     [rax+80h], r15b
0x18026dbf7  jz      loc_18026DD2E
0x18026dbfd  mov     edx, edi
0x18026dbff  lea     rcx, [rbp+620h+var_100]
0x18026dc06  call    ??$_Integral_to_string@DH@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@H@Z; std::_Integral_to_string<char,int>(int)
0x18026dc0b  nop
0x18026dc0c  lea     rdx, asc_1803D71C4; ":"
0x18026dc13  lea     rcx, [rbp+620h+var_600]
0x18026dc17  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18026dc1c  mov     rdi, rax
0x18026dc1f  lea     rdx, asc_1803D71C8; "\""
0x18026dc26  lea     rcx, [rbp+620h+var_5E0]
0x18026dc2a  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18026dc2f  mov     rbx, rax
0x18026dc32  lea     rdx, asc_1803D71C8; "\""
0x18026dc39  lea     rcx, [rbp+620h+var_628]
0x18026dc3d  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18026dc42  nop
0x18026dc43  lea     r8, aLocation_0; "Location"
0x18026dc4a  mov     rdx, rax
0x18026dc4d  lea     rcx, [rbp+620h+var_698]
0x18026dc51  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@QEBD@Z; std::operator+<char>(std::string &&,char const * const)
0x18026dc56  nop
0x18026dc57  mov     r9, rbx
0x18026dc5a  mov     r8, rax
0x18026dc5d  mov     dl, [rsp+720h+var_6B0]
0x18026dc61  lea     rcx, [rbp+620h+var_1D8]
0x18026dc68  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::string::string(std::_String_constructor_concat_tag,std::string &,std::string &)
0x18026dc6d  nop
0x18026dc6e  mov     r9, rdi
0x18026dc71  lea     r8, [rbp+620h+var_1D8]
0x18026dc78  mov     dl, [rsp+720h+var_6B0]
0x18026dc7c  lea     rcx, [rbp+620h+var_E0]
0x18026dc83  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::string::string(std::_String_constructor_concat_tag,std::string &,std::string &)
0x18026dc88  nop
0x18026dc89  lea     r9, [rbp+620h+var_100]
0x18026dc90  lea     r8, [rbp+620h+var_E0]
0x18026dc97  mov     dl, [rsp+720h+var_6B0]
0x18026dc9b  lea     rcx, [rbp+620h+var_670]
0x18026dc9f  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::string::string(std::_String_constructor_concat_tag,std::string &,std::string &)
0x18026dca4  lea     rax, [rbp+620h+var_670]
0x18026dca8  mov     [rsp+720h+var_6F0], rax; __int64
0x18026dcad  lea     rdi, aTestprimaryout; "TestPrimaryOutLinkNull"
0x18026dcb4  mov     [rsp+720h+Str], rdi; Str
0x18026dcb9  mov     [rsp+720h+var_700], rdi; char *
0x18026dcbe  lea     r9, aSmiles; "Smiles"
0x18026dcc5  xor     r8d, r8d; int
0x18026dcc8  lea     rdx, aRdCheckpoint; "RD_CHECKPOINT"
0x18026dccf  lea     rcx, [rbp+620h+var_290]; int
0x18026dcd6  call    ??$TraceCheckpointMessage@VTraceCheckpoint@Basix@Microsoft@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@TraceManager@Instrumentation@Basix@Microsoft@@SAXAEBV?$shared_ptr@V?$Event@VTraceCheckpoint@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@PEBDI111V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@@Z; Microsoft::Basix::Instrumentation::TraceManager::TraceCheckpointMessage<Microsoft::Basix::TraceCheckpoint,std::string>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceCheckpoint>> const &,char const *,uint,char const *,char const *,char const *,std::string)
0x18026dcdb  nop
0x18026dcdc  lea     rcx, [rbp+620h+var_E0]
0x18026dce3  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18026dce8  nop
0x18026dce9  lea     rcx, [rbp+620h+var_1D8]
0x18026dcf0  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18026dcf5  nop
0x18026dcf6  lea     rcx, [rbp+620h+var_698]
0x18026dcfa  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18026dcff  nop
0x18026dd00  lea     rcx, [rbp+620h+var_628]
0x18026dd04  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18026dd09  nop
0x18026dd0a  lea     rcx, [rbp+620h+var_5E0]
0x18026dd0e  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18026dd13  nop
0x18026dd14  lea     rcx, [rbp+620h+var_600]
0x18026dd18  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18026dd1d  nop
0x18026dd1e  lea     rcx, [rbp+620h+var_100]
0x18026dd25  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18026dd2a  mov     rbx, [rbp+620h+var_630]
0x18026dd2e  lea     rcx, [rbp+620h+var_290]; void *
0x18026dd35  call    ??1?$shared_ptr@VMicrosoft_Basix_Instrumentation_RioBuffersReceive_Logger@Microsoft_Streaming_Nano_Network@GlobalProviderList@@@std@@QEAA@XZ; std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(void)
0x18026dd3a  xorps   xmm0, xmm0
0x18026dd3d  xorps   xmm10, xmm10
0x18026dd41  movdqa  [rbp+620h+var_5C0], xmm10
0x18026dd47  movups  [rbp+620h+var_100], xmm0
0x18026dd4e  movups  [rbp+620h+var_F0], xmm0
0x18026dd55  movdqu  [rbp+620h+pExceptionObject], xmm0
0x18026dd5d  lea     r9, [rbp+620h+pExceptionObject]
0x18026dd64  xor     r8d, r8d
0x18026dd67  mov     dl, 1
0x18026dd69  lea     rcx, [rbp+620h+var_100]
0x18026dd70  call    ??0OperationOnLinkId@Dct@Basix@Microsoft@@QEAA@W4Direction@LinkData@123@W4Mode@0123@V?$shared_ptr@VLinkDataV3@Dct@Basix@Microsoft@@@std@@@Z; Microsoft::Basix::Dct::OperationOnLinkId::OperationOnLinkId(Microsoft::Basix::Dct::LinkData::Direction,Microsoft::Basix::Dct::OperationOnLinkId::Mode,std::shared_ptr<Microsoft::Basix::Dct::LinkDataV3>)
0x18026dd75  nop
0x18026dd76  xorps   xmm0, xmm0
0x18026dd79  movups  [rbp+620h+var_E0], xmm0
0x18026dd80  movups  [rbp+620h+var_D0], xmm0
0x18026dd87  movdqu  [rbp+620h+pExceptionObject], xmm0
0x18026dd8f  lea     r9, [rbp+620h+pExceptionObject]
0x18026dd96  xor     r8d, r8d
0x18026dd99  xor     edx, edx
0x18026dd9b  lea     rcx, [rbp+620h+var_E0]
0x18026dda2  call    ??0OperationOnLinkId@Dct@Basix@Microsoft@@QEAA@W4Direction@LinkData@123@W4Mode@0123@V?$shared_ptr@VLinkDataV3@Dct@Basix@Microsoft@@@std@@@Z; Microsoft::Basix::Dct::OperationOnLinkId::OperationOnLinkId(Microsoft::Basix::Dct::LinkData::Direction,Microsoft::Basix::Dct::OperationOnLinkId::Mode,std::shared_ptr<Microsoft::Basix::Dct::LinkDataV3>)
0x18026dda7  nop
0x18026dda8  mov     [rsp+720h+var_6B0], r15b
0x18026ddad  mov     [rbp+620h+var_64F], r15b
0x18026ddb1  mov     rcx, r13; this
0x18026ddb4  call    ?GetCurrentTimeInMsFromBase@SmilesV3@Dct@Basix@Microsoft@@QEAA_KXZ; Microsoft::Basix::Dct::SmilesV3::GetCurrentTimeInMsFromBase(void)
0x18026ddb9  mov     [rbp+620h+BufferCount], rax
0x18026ddc0  xorps   xmm9, xmm9
0x18026ddc4  test    rax, rax
0x18026ddc7  js      short loc_18026DDD0
0x18026ddc9  cvtsi2sd xmm9, rax
0x18026ddce  jmp     short loc_18026DDE6
0x18026ddd0  mov     rcx, rax
0x18026ddd3  shr     rcx, 1
0x18026ddd6  and     eax, 1
0x18026ddd9  or      rcx, rax
0x18026dddc  cvtsi2sd xmm9, rcx
0x18026dde1  addsd   xmm9, xmm9
0x18026dde6  movaps  xmm8, xmm9
0x18026ddea  mulsd   xmm8, cs:__real@3f50624dd2f1a9fc
0x18026ddf3  mov     [rbp+620h+var_677], 1
0x18026ddf7  mov     [rsp+720h+var_6AE], 1
0x18026ddfc  or      r12, 0FFFFFFFFFFFFFFFFh
0x18026de00  mov     esi, r12d
0x18026de03  mov     [rbp+620h+var_1E0], rsi
0x18026de0a  mov     [rsp+720h+var_6AF], r15b
0x18026de0f  lea     rdx, [r13+728h]
0x18026de16  lea     rcx, [rbp+620h+var_608]
0x18026de1a  call    ??0?$lock_guard@Vmutex@std@@@std@@QEAA@AEAVmutex@1@@Z; std::lock_guard<std::mutex>::lock_guard<std::mutex>(std::mutex &)
0x18026de1f  nop
0x18026de20  xorps   xmm0, xmm0
0x18026de23  movdqa  [rbp+620h+pExceptionObject], xmm0
0x18026de2b  mov     r14, qword ptr [rbp+620h+var_210+8]
0x18026de32  test    r14, r14
0x18026de35  jz      short loc_18026DE3C
0x18026de37  lock inc dword ptr [r14+8]
0x18026de3c  movaps  xmm12, [rbp+620h+var_210]
0x18026de44  movdqa  [rbp+620h+pExceptionObject], xmm12
0x18026de4d  lea     rdx, [rbp+620h+pExceptionObject]
0x18026de54  mov     rcx, r13
0x18026de57  call    ?SetInitialPrimaryInLink@?$Smiles@VLinkDataDisabled@Dct@Basix@Microsoft@@@Dct@Basix@Microsoft@@IEAA_NV?$shared_ptr@VLinkDataDisabled@Dct@Basix@Microsoft@@@std@@@Z; Microsoft::Basix::Dct::Smiles<Microsoft::Basix::Dct::LinkDataDisabled>::SetInitialPrimaryInLink(std::shared_ptr<Microsoft::Basix::Dct::LinkDataDisabled>)
0x18026de5c  test    al, al
0x18026de5e  jz      short loc_18026DEBE
0x18026de60  lea     rdx, aInitialPrimary_1; "Initial primaryInLink OnDataReceived"
0x18026de67  lea     rcx, [rbp+620h+var_670]
0x18026de6b  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18026de70  nop
0x18026de71  xorps   xmm0, xmm0
0x18026de74  movdqa  [rbp+620h+pExceptionObject], xmm0
0x18026de7c  test    r14, r14
0x18026de7f  jz      short loc_18026DE86
0x18026de81  lock inc dword ptr [r14+8]
0x18026de86  movdqa  [rbp+620h+pExceptionObject], xmm12
0x18026de8f  mov     byte ptr [rsp+720h+var_700], 1
0x18026de94  lea     r9, [rbp+620h+var_670]
0x18026de98  lea     r8, [rbp+620h+pExceptionObject]
0x18026de9f  lea     rdx, [rbp+620h+var_698]
0x18026dea3  mov     rcx, r13
0x18026dea6  call    ?LogInitialLinkSwitchOn@SmilesV3@Dct@Basix@Microsoft@@AEAA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@VLinkDataV3@Dct@Basix@Microsoft@@@6@AEBV56@W4Direction@LinkData@234@@Z; Microsoft::Basix::Dct::SmilesV3::LogInitialLinkSwitchOn(std::shared_ptr<Microsoft::Basix::Dct::LinkDataV3>,std::string const &,Microsoft::Basix::Dct::LinkData::Direction)
0x18026deab  lea     rcx, [rbp+620h+var_698]
0x18026deaf  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18026deb4  nop
0x18026deb5  lea     rcx, [rbp+620h+var_670]
0x18026deb9  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18026debe  mov     word ptr [rbp+620h+var_590], r15w
0x18026dec6  mov     word ptr [rbp+620h+var_674], r15w
0x18026decb  mov     word ptr [rbp+620h+var_638], r15w
0x18026ded0  mov     eax, 0FFFFh
0x18026ded5  mov     [rbp+620h+var_648], eax
0x18026ded8  mov     word ptr [rsp+720h+var_6AC], ax
0x18026dedd  mov     [rbp+620h+var_130], r15b
0x18026dee4  xorps   xmm0, xmm0
0x18026dee7  movdqu  [rbp+620h+var_128], xmm0
0x18026deef  mov     [rbp+620h+var_118], r15
0x18026def6  mov     [rbp+620h+var_110], r15w
0x18026defe  mov     [rbp+620h+var_10E], r15b
0x18026df05  mov     [rbp+620h+var_108], r15
0x18026df0c  mov     rcx, [rbx]
0x18026df0f  call    ?_Get@?$_Func_impl_no_alloc@V_lambda_8fe06ae25614185e6bdd0a582616d3ae_@@X$$V@std@@EEBAPEBXXZ; std::_Func_impl_no_alloc<_lambda_8fe06ae25614185e6bdd0a582616d3ae_,void,>::_Get(void)
0x18026df14  lea     rdx, [rsp+720h+var_6AF]
0x18026df19  mov     rcx, rax
0x18026df1c  call    ??$Extract@E@FlexIBuffer@Containers@Basix@Microsoft@@QEAAXAEAE@Z; Microsoft::Basix::Containers::FlexIBuffer::Extract<uchar>(uchar &)
0x18026df21  mov     rcx, [rbx]
0x18026df24  call    ?_Get@?$_Func_impl_no_alloc@V_lambda_8fe06ae25614185e6bdd0a582616d3ae_@@X$$V@std@@EEBAPEBXXZ; std::_Func_impl_no_alloc<_lambda_8fe06ae25614185e6bdd0a582616d3ae_,void,>::_Get(void)
0x18026df29  lea     rdx, [rbp+620h+var_674]
0x18026df2d  mov     rcx, rax
0x18026df30  call    ??$Extract@W4Type@STUNMessage@ICE@Dct@Basix@Microsoft@@@FlexIBuffer@Containers@Basix@Microsoft@@QEAAXAEAW4Type@STUNMessage@ICE@Dct@23@@Z; Microsoft::Basix::Containers::FlexIBuffer::Extract<Microsoft::Basix::Dct::ICE::STUNMessage::Type>(Microsoft::Basix::Dct::ICE::STUNMessage::Type &)
0x18026df35  mov     rcx, [rbx]
0x18026df38  call    ?_Get@?$_Func_impl_no_alloc@V_lambda_8fe06ae25614185e6bdd0a582616d3ae_@@X$$V@std@@EEBAPEBXXZ; std::_Func_impl_no_alloc<_lambda_8fe06ae25614185e6bdd0a582616d3ae_,void,>::_Get(void)
0x18026df3d  lea     rdx, [rbp+620h+var_638]
0x18026df41  mov     rcx, rax
0x18026df44  call    ??$Extract@W4Type@STUNMessage@ICE@Dct@Basix@Microsoft@@@FlexIBuffer@Containers@Basix@Microsoft@@QEAAXAEAW4Type@STUNMessage@ICE@Dct@23@@Z; Microsoft::Basix::Containers::FlexIBuffer::Extract<Microsoft::Basix::Dct::ICE::STUNMessage::Type>(Microsoft::Basix::Dct::ICE::STUNMessage::Type &)
0x18026df49  movzx   eax, word ptr [rbp+620h+var_674]
0x18026df4d  mov     word ptr [rbp+620h+var_238], ax
0x18026df54  lea     rcx, [r13+0B88h]
0x18026df5b  lea     r8, [rbp+620h+var_238]
0x18026df62  lea     rdx, [rbp+620h+var_270]
0x18026df69  call    ?DecodeSequenceNumberAndUpdateCurrent@?$SequenceNumberGeneratorWithRolloverCounter@$0BA@$0DA@G_K_K@Algorithm@Basix@Microsoft@@QEAA?AV?$SequenceNumber@$0EA@_K@234@AEBV?$SequenceNumber@$0BA@G@234@@Z; Microsoft::Basix::Algorithm::SequenceNumberGeneratorWithRolloverCounter<16,48,ushort,unsigned __int64,unsigned __int64>::DecodeSequenceNumberAndUpdateCurrent(Microsoft::Basix::Algorithm::SequenceNumber<16,ushort> const &)
0x18026df6e  mov     edi, 8
0x18026df73  cmp     [r13+5F4h], r15b
0x18026df7a  jz      loc_18026E16C
0x18026df80  xor     edx, edx
0x18026df82  mov     rcx, [r13+718h]
0x18026df89  call    ??$?8V?$Event@VTraceCheckpoint@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@YA_NAEBV?$shared_ptr@V?$Event@VTraceCheckpoint@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@0@$$T@Z; std::operator==<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceCheckpoint>>(std::shared_ptr<Microsoft::Basix::Instrumentation::Event<Microsoft::Basix::TraceCheckpoint>> const &,std::nullptr_t)
0x18026df8e  test    al, al
0x18026df90  jz      loc_18026E16C
0x18026df96  xorps   xmm0, xmm0
0x18026df99  movups  xmmword ptr [rbp+620h+var_290], xmm0
0x18026dfa0  lea     rcx, [rbp+620h+var_290]
0x18026dfa7  call    ??$SelectEvent@VTraceNormal@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceNormal@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(void)
  ... truncated ...
```
