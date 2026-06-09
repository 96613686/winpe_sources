# CDrawingContext::PreSubgraph(CVisualTree const *,bool *)

- ea: `0x180037020`
- end: `0x18003c0ff`
- name: `?PreSubgraph@CDrawingContext@@QEAAJPEBVCVisualTree@@PEA_N@Z`
- size: `20703`
- prototype: `__int64 __fastcall(CDrawingContext *__hidden this, const struct CVisualTree *, bool *)`
- caller_count: `1`
- callee_count: `107`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180036210`

## callees

- `0x18000fb70`
- `0x180027788`
- `0x1800286b8`
- `0x18002874c`
- `0x18002b2ac`
- `0x18002c048`
- `0x18002c2d4`
- `0x180037020`
- `0x18003eb70`
- `0x18003fdc0`
- `0x18004061c`
- `0x180042b00`
- `0x18004df10`
- `0x18004fce4`
- `0x180050270`
- `0x180050580`
- `0x180051680`
- `0x1800516b0`
- `0x1800616c8`
- `0x180061ab0`
- `0x180062b28`
- `0x180063dc0`
- `0x18008c040`
- `0x18008c810`
- `0x18008cd20`
- `0x18009bf90`
- `0x1800ac440`
- `0x1800ae670`
- `0x1800ae8a0`
- `0x1800b7a80`
- `0x1800b9ddc`
- `0x1800ba8e0`
- `0x1800de160`
- `0x1800ecfc0`
- `0x1800f27e0`
- `0x1800f75c8`
- `0x1800f78c0`
- `0x1800fcaf8`
- `0x1800fcb60`
- `0x1800fcbb8`
- `0x18011a810`
- `0x180128fd0`
- `0x180129aac`
- `0x180131650`
- `0x18013d930`
- `0x18013ed00`
- `0x18013f160`
- `0x1801456c8`
- `0x180149254`
- `0x18014ee58`

## import_xrefs

- `msvcp_win!?_Xoverflow_error@std@@YAXPEBD@Z` at `0x18003a483`
- `msvcp_win!?_Xoverflow_error@std@@YAXPEBD@Z` at `0x18003a483`
- `api-ms-win-eventing-provider-l1-1-0!EventEnabled` at `0x180039ca3`
- `api-ms-win-eventing-provider-l1-1-0!EventEnabled` at `0x180039ca3`

## string_xrefs

- `0x18003776e`: `onecoreuap\windows\DWM\dwmcore\common\WatermarkStack.inl`
- `0x180037784`: `onecoreuap\windows\DWM\dwmcore\common\WatermarkStack.inl`
- `0x180037c13`: `onecoreuap\windows\DWM\dwmcore\common\WatermarkStack.inl`
- `0x18003af1c`: `onecoreuap\windows\DWM\dwmcore\common\WatermarkStack.inl`
- `0x18003bd9c`: `onecoreuap\windows\DWM\dwmcore\common\WatermarkStack.inl`

## pseudocode

```c
__int64 __fastcall CDrawingContext::PreSubgraph(CDrawingContext *this, const struct CVisualTree *a2, bool *j)
{
  int v3; // edi
  CDrawingContext *v5; // rsi
  struct CVisual *v6; // rax
  __int64 v7; // r14
  _DWORD *v8; // rdx
  bool v9; // zf
  char v10; // bl
  unsigned int v11; // r9d
  unsigned int v12; // eax
  int v13; // eax
  unsigned int v14; // r9d
  unsigned __int64 i2; // rcx
  unsigned int v16; // eax
  bool *v17; // rbx
  int v18; // eax
  int v19; // r13d
  int v20; // eax
  _QWORD *v22; // r12
  CProcessAttribution *v23; // r13
  __int64 v24; // rax
  __int64 v25; // rax
  CProcessAttribution *v26; // rbx
  int v27; // ebx
  int v28; // eax
  void *v29; // rcx
  __int64 v30; // rax
  __int64 v31; // rdx
  __int64 v32; // rdx
  unsigned int *v33; // r8
  float v34; // xmm9_4
  __m128 v35; // xmm6
  float v36; // xmm7_4
  float v37; // xmm8_4
  int v38; // eax
  float v39; // xmm0_4
  __m128 si128; // xmm2
  float v41; // xmm3_4
  float v42; // xmm1_4
  float v43; // xmm0_4
  const struct CVisualTreePath *CurrentVisualTreePath; // rax
  __int64 v45; // r12
  __int64 v46; // rbx
  _QWORD *v47; // r13
  __int64 v48; // rax
  _QWORD *v49; // rcx
  _QWORD *v50; // rax
  __int64 v51; // rax
  __int64 v52; // r13
  unsigned __int64 v53; // rax
  __int64 v54; // rdx
  unsigned int v55; // r13d
  unsigned int v56; // ebx
  __int64 v57; // rcx
  __int64 v58; // rdx
  bool *v59; // rdx
  __int64 v60; // rbx
  __int64 p_Blink; // rax
  __int64 v62; // rax
  unsigned __int64 v63; // rcx
  unsigned __int64 v64; // r13
  void *v65; // rax
  __int64 v66; // rcx
  __int64 v67; // rdx
  bool *v68; // rdx
  _QWORD *v69; // rcx
  _QWORD *k; // rax
  int v71; // eax
  __int64 v72; // rax
  int v73; // edx
  __int64 v74; // rcx
  unsigned int v75; // eax
  unsigned int v76; // eax
  unsigned int v77; // edx
  int v78; // r13d
  unsigned int v79; // eax
  __int64 v80; // rcx
  __int64 v81; // r8
  CProjectedShadowReceiver **v82; // r12
  CProjectedShadowReceiver **v83; // rax
  CProjectedShadowReceiver *v84; // r13
  CProcessAttribution *v85; // rax
  CProcessAttribution *v86; // rbx
  CProjectedShadowScene *v87; // rdi
  __int64 ***v88; // rdi
  __int64 **i; // rbx
  CVisual *v90; // rcx
  const void *v91; // rdi
  const char *v92; // rbx
  const char **v93; // rax
  __int64 v94; // rdi
  const struct CVisualTreePath *v95; // rbx
  CDrawingContext *v96; // rcx
  bool IsBackdropWalk; // al
  const char *v98; // rdx
  __int64 v99; // rax
  int v100; // eax
  struct CVisual *v101; // rax
  __int64 **v102; // r12
  unsigned int v103; // ecx
  __int64 n; // rbx
  __int64 v105; // rax
  __int64 v106; // rax
  __int64 v107; // rax
  _BYTE *v108; // rbx
  int v109; // eax
  int v110; // eax
  __int64 v111; // rcx
  __int64 v112; // rax
  __m128 v113; // xmm0
  float v114; // xmm4_4
  float v115; // xmm5_4
  float v116; // xmm10_4
  unsigned int v117; // eax
  _DWORD *v118; // rbx
  int v119; // ebx
  _QWORD *v120; // r13
  __int64 *v121; // rdi
  __int64 v122; // r12
  __int64 ii; // rax
  int v124; // edi
  _QWORD *v125; // rbx
  __int64 v126; // r12
  __m128 v127; // xmm6
  __m128 v128; // xmm6
  unsigned int v129; // r13d
  __m128 v130; // xmm6
  float v131; // xmm5_4
  float v132; // xmm6_4
  float v133; // xmm7_4
  float v134; // xmm8_4
  __int64 v135; // rax
  char v136; // al
  __int64 v137; // r12
  void (__fastcall ****v138)(_QWORD, __int64); // rbx
  __int64 *v139; // r13
  CProcessAttribution **v140; // rax
  CProcessAttribution *v141; // r9
  int v142; // eax
  __int64 v143; // rax
  float v144; // xmm0_4
  float v145; // xmm1_4
  float v146; // xmm6_4
  _DWORD *v147; // rdx
  float v148; // xmm1_4
  int v149; // eax
  float v150; // xmm0_4
  char v151; // al
  _DWORD *v152; // rdx
  bool v153; // al
  float v154; // xmm1_4
  unsigned __int32 v155; // xmm6_4
  __int64 v156; // rax
  int v157; // eax
  CGeometry *v158; // rbx
  _BYTE *v159; // rdi
  __m128 *v160; // rbx
  __int64 v161; // r8
  const char *v162; // r9
  __m128 v163; // xmm2
  __m128 v164; // xmm3
  __m128 v165; // xmm10
  __m128 v166; // xmm11
  __int8 v167; // cl
  unsigned __int64 v168; // rax
  __int32 v169; // eax
  CCpuClippingData *CpuClippingData; // rbx
  enum D2D1_ANTIALIAS_MODE D2DAntialiasMode; // eax
  __int64 v172; // rax
  int v173; // edx
  int v174; // eax
  int ScopeMode; // r13d
  CCpuClippingData *v176; // rcx
  bool CanIgnoreAncestorCpuClips; // bl
  __int64 v178; // rax
  char v179; // r13
  CVisual *v180; // rcx
  CVisual *v181; // rcx
  struct CVisual *v182; // rbx
  int v183; // eax
  __m128 v184; // xmm1
  __int64 v185; // rcx
  __int64 v186; // rdx
  __int64 *kk; // rax
  float v188; // xmm3_4
  float v189; // xmm2_4
  float v190; // xmm1_4
  float v191; // xmm0_4
  float v192; // xmm4_4
  float v193; // xmm4_4
  float v194; // xmm4_4
  float v195; // xmm4_4
  int v196; // eax
  int v197; // r12d
  int v198; // ecx
  _DWORD *v199; // rax
  int v200; // edx
  int v201; // eax
  int v202; // eax
  int v203; // eax
  unsigned int v204; // r9d
  char v205; // cl
  __int64 v206; // rdx
  float v207; // xmm13_4
  float v208; // xmm5_4
  float v209; // xmm9_4
  float v210; // xmm4_4
  float v211; // xmm7_4
  float v212; // xmm8_4
  char v213; // r10
  char v214; // r8
  int v215; // eax
  int *v216; // r8
  unsigned int v217; // ecx
  __int64 i5; // rdx
  __int64 v219; // rax
  int *v220; // rdx
  __int64 ***v221; // rcx
  __int64 **i6; // rax
  __int64 v223; // r9
  unsigned int v224; // ecx
  __int64 mm; // rdx
  __int64 v226; // rax
  __int64 *nn; // rax
  int v228; // eax
  int v229; // eax
  int ShapeData; // eax
  __int64 v231; // r13
  int v232; // ebx
  int v233; // eax
  unsigned int v234; // eax
  char v235; // cl
  char v236; // dl
  char v237; // cl
  __int64 v238; // r8
  float v239; // xmm2_4
  float v240; // xmm10_4
  float v241; // xmm3_4
  bool v242; // al
  char v243; // dl
  char v244; // cl
  __m128 v245; // xmm4
  float v246; // xmm8_4
  float v247; // xmm9_4
  float v248; // xmm10_4
  __m128 v249; // xmm7
  __m128 v250; // xmm3
  float v251; // xmm3_4
  char v252; // al
  int v253; // eax
  __int64 v254; // r10
  char v255; // r10
  char v256; // r8
  char v257; // al
  char v258; // r8
  float v259; // xmm3_4
  unsigned int v260; // xmm1_4
  float v261; // xmm11_4
  float v262; // xmm15_4
  float v263; // xmm2_4
  float v264; // xmm10_4
  bool v265; // al
  float v266; // xmm0_4
  bool HasContextDependentClip; // al
  __int64 *v268; // rcx
  int v269; // eax
  int v270; // eax
  const struct CMILMatrix *TopByReference; // rax
  __int64 v272; // rdx
  __int64 InputBounds; // rax
  float v274; // edx
  float *v275; // rcx
  int v276; // eax
  unsigned int v277; // r9d
  unsigned int v278; // ecx
  __int64 i3; // r8
  __int64 v280; // rax
  float **v281; // rbx
  float *v282; // rbx
  char v283; // al
  char v284; // dl
  char v285; // cl
  __m128 v286; // xmm11
  __m128 v287; // xmm6
  __m128 v288; // xmm12
  float v289; // xmm7_4
  __m128 v290; // xmm1
  __m128 v291; // xmm9
  __m128 v292; // xmm2
  float v293; // xmm13_4
  float v294; // xmm5_4
  char v295; // r8
  unsigned int v296; // ecx
  __int64 i4; // r8
  __int64 v298; // rax
  _QWORD *v299; // r8
  char v300; // al
  char v301; // cl
  char v302; // dl
  char v303; // r10
  char v304; // r8
  CWindowBackgroundTreatment *WindowBackgroundTreatmentInternal; // rbx
  const struct CMILMatrix *v306; // rax
  __int64 v307; // rdx
  __int64 v308; // r8
  __int64 v309; // rax
  __int64 v310; // r9
  struct Microsoft::BamoImpl::BamoPrincipalImpl *v311; // rax
  const struct RenderTargetInfo *v312; // rax
  unsigned int v313; // ecx
  int BitmapForEffectInput; // eax
  const struct CMILMatrix *v315; // rax
  int v316; // eax
  int v317; // eax
  char v318; // dl
  char v319; // cl
  char v320; // al
  char v321; // dl
  CTreeEffectLayer *v322; // r8
  struct CVisualTree *FlatteningVisualTree; // rax
  __int64 Bounds; // rax
  __int64 v325; // rcx
  int v326; // eax
  __int64 v327; // r9
  __int64 v328; // rdx
  unsigned __int64 v329; // r8
  char v330; // al
  int v331; // eax
  float v332; // xmm0_4
  char v333; // dl
  char v334; // al
  __m128 v335; // xmm8
  __m128 v336; // xmm6
  __m128 v337; // xmm7
  __m128 v338; // xmm5
  unsigned int v339; // r13d
  _QWORD *v340; // rbx
  CProcessAttribution *v341; // r9
  __int64 v342; // rax
  _QWORD *v343; // r10
  unsigned __int64 *v344; // rax
  int v345; // eax
  int v346; // eax
  unsigned int v347; // r9d
  char v348; // dl
  char v349; // cl
  char v350; // r8
  char v351; // dl
  char v352; // cl
  char v353; // al
  char v354; // r10
  char v355; // r8
  unsigned __int8 v356; // r8
  char v357; // al
  unsigned __int64 *v358; // rax
  char v359; // al
  __int64 v360; // r11
  __int64 v361; // rcx
  unsigned __int64 v362; // rdx
  __int64 *v363; // r10
  __int64 *v364; // rbx
  __int64 v365; // r8
  bool v366; // cc
  _QWORD *i1; // rcx
  __int64 v368; // rax
  void (__fastcall ***v369)(_QWORD, __int64); // r8
  char v370; // r8
  char v371; // r10
  char v372; // al
  char v373; // al
  char v374; // cl
  char v375; // dl
  char v376; // r8
  char v377; // r10
  struct _LIST_ENTRY *TreeDataListHead; // rax
  struct _LIST_ENTRY *v379; // r9
  struct _LIST_ENTRY *m; // rcx
  bool v381; // al
  char v382; // cl
  unsigned __int8 v383; // r8
  char v384; // al
  char v385; // r10
  char v386; // r8
  char v387; // al
  char v388; // dl
  char v389; // cl
  char v390; // dl
  char v391; // cl
  unsigned __int8 v392; // r8
  char v393; // al
  char v394; // r10
  char v395; // r8
  char v396; // r8
  char v397; // r10
  char v398; // al
  char v399; // cl
  char v400; // dl
  char v401; // r8
  char v402; // r10
  char v403; // al
  char v404; // r10
  char v405; // r8
  unsigned __int8 v406; // r8
  char v407; // al
  char v408; // r10
  char v409; // r8
  char v410; // dl
  char v411; // cl
  char v412; // r8
  char v413; // cl
  char v414; // dl
  char v415; // bl
  char v416; // cl
  int v417; // eax
  enum DXGI_COLOR_SPACE_TYPE ColorSpace; // eax
  __int64 v419; // r11
  char v420; // dl
  char v421; // cl
  char v422; // al
  char v423; // r8
  char v424; // r8
  char v425; // r10
  char v426; // dl
  char v427; // cl
  char v428; // dl
  char v429; // r8
  char v430; // r10
  int v431; // eax
  _QWORD *v432; // rax
  unsigned __int64 **v433; // rax
  _QWORD *v434; // rbx
  __int64 v435; // rdx
  __int64 *v436; // rbx
  __int64 v437; // rcx
  void (__fastcall ***v438)(_QWORD, __int64); // rax
  void (__fastcall ***v439)(_QWORD, __int64); // r8
  void (__fastcall ****jj)(_QWORD, __int64); // rcx
  _QWORD *v441; // rbx
  __int64 v442; // rcx
  bool v443; // cc
  _QWORD *v444; // r14
  int v445; // eax
  bool v446; // cf
  int v447; // eax
  int v448; // [rsp+20h] [rbp-E0h]
  unsigned int v449; // [rsp+20h] [rbp-E0h]
  int v450; // [rsp+20h] [rbp-E0h]
  int v451; // [rsp+20h] [rbp-E0h]
  int v452; // [rsp+20h] [rbp-E0h]
  _BYTE v453[4]; // [rsp+50h] [rbp-B0h] BYREF
  int v454; // [rsp+54h] [rbp-ACh] BYREF
  char v455; // [rsp+58h] [rbp-A8h] BYREF
  bool v456; // [rsp+59h] [rbp-A7h]
  unsigned int v457[2]; // [rsp+60h] [rbp-A0h] BYREF
  int v458; // [rsp+68h] [rbp-98h]
  bool v459; // [rsp+6Ch] [rbp-94h] BYREF
  bool v460; // [rsp+6Dh] [rbp-93h]
  bool *v461; // [rsp+70h] [rbp-90h]
  unsigned int v462[2]; // [rsp+78h] [rbp-88h] BYREF
  __int128 v463; // [rsp+80h] [rbp-80h] BYREF
  char v464; // [rsp+90h] [rbp-70h]
  CCpuClippingData *v465; // [rsp+98h] [rbp-68h]
  int v466; // [rsp+A0h] [rbp-60h]
  float v467; // [rsp+A4h] [rbp-5Ch]
  __int64 v468[2]; // [rsp+A8h] [rbp-58h] BYREF
  __m128 v469; // [rsp+B8h] [rbp-48h]
  _BYTE v470[40]; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v471; // [rsp+F0h] [rbp-10h]
  __int128 v472; // [rsp+100h] [rbp+0h]
  __int128 v473; // [rsp+110h] [rbp+10h]
  __int64 v474; // [rsp+120h] [rbp+20h]
  __int64 v475; // [rsp+128h] [rbp+28h]
  __int64 v476; // [rsp+130h] [rbp+30h]
  _DWORD v477[2]; // [rsp+138h] [rbp+38h] BYREF
  CProcessAttribution *v478; // [rsp+140h] [rbp+40h]
  CProcessAttribution *v479; // [rsp+148h] [rbp+48h] BYREF
  void *v480; // [rsp+150h] [rbp+50h] BYREF
  void *Src[2]; // [rsp+158h] [rbp+58h] BYREF
  int v482; // [rsp+168h] [rbp+68h]
  int v483; // [rsp+16Ch] [rbp+6Ch]
  __m128 v484; // [rsp+170h] [rbp+70h]
  struct CVisual *v485; // [rsp+180h] [rbp+80h] BYREF
  unsigned __int64 v486; // [rsp+188h] [rbp+88h] BYREF
  unsigned __int64 v487; // [rsp+190h] [rbp+90h]
  __int64 v488; // [rsp+198h] [rbp+98h] BYREF
  char v489; // [rsp+1A0h] [rbp+A0h]
  __int64 v490; // [rsp+1A8h] [rbp+A8h]
  __int64 v491; // [rsp+1B0h] [rbp+B0h]
  _DWORD v492[2]; // [rsp+1B8h] [rbp+B8h] BYREF
  __int64 *v493; // [rsp+1C0h] [rbp+C0h] BYREF
  _DWORD v494[2]; // [rsp+1C8h] [rbp+C8h] BYREF
  __int128 v495; // [rsp+1D0h] [rbp+D0h] BYREF
  unsigned __int64 *v496; // [rsp+1E0h] [rbp+E0h] BYREF
  char v497[8]; // [rsp+1E8h] [rbp+E8h] BYREF
  char v498[8]; // [rsp+1F0h] [rbp+F0h] BYREF
  CProcessAttribution *v499; // [rsp+1F8h] [rbp+F8h] BYREF
  int v500; // [rsp+200h] [rbp+100h] BYREF
  __int128 v501; // [rsp+204h] [rbp+104h]
  int v502; // [rsp+214h] [rbp+114h]
  char v503[8]; // [rsp+220h] [rbp+120h] BYREF
  char v504[8]; // [rsp+228h] [rbp+128h] BYREF
  char v505[8]; // [rsp+230h] [rbp+130h] BYREF
  _BYTE v506[24]; // [rsp+238h] [rbp+138h] BYREF
  _BYTE v507[80]; // [rsp+250h] [rbp+150h] BYREF
  __int128 v508; // [rsp+2A0h] [rbp+1A0h] BYREF
  __int64 v509; // [rsp+2B0h] [rbp+1B0h]
  __int64 v510[2]; // [rsp+2B8h] [rbp+1B8h] BYREF
  struct D2D_RECT_F v511; // [rsp+2C8h] [rbp+1C8h] BYREF
  __int128 v512; // [rsp+2D8h] [rbp+1D8h] BYREF
  __int128 v513; // [rsp+2E8h] [rbp+1E8h] BYREF
  __int64 v514; // [rsp+2F8h] [rbp+1F8h]
  __int128 v515; // [rsp+300h] [rbp+200h] BYREF
  __int128 v516; // [rsp+310h] [rbp+210h] BYREF
  char v517[16]; // [rsp+320h] [rbp+220h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+418h] [rbp+318h]

  v461 = j;
  v3 = 0;
  *(_QWORD *)&v512 = this;
  v509 = 0;
  v514 = 0;
  v508 = 0;
  v5 = this;
  v458 = 0;
  v513 = 0;
  v454 = 0;
  v515 = 0;
  v6 = (struct CVisual *)*((_QWORD *)this + 402);
  v7 = *((_QWORD *)this + 401);
  v475 = 0x2A993F800000LL;
  v485 = v6;
  v463 = 0;
  v464 = 0;
  v465 = 0;
  v466 = 0;
  v467 = 1.0;
  *(_QWORD *)&v470[32] = 0;
  v476 = 0;
  memset(v477, 0, 6);
  v471 = 0;
  v472 = 0;
  v473 = 0;
  v474 = 0;
  v8 = *(_DWORD **)(v7 + 224);
  v495 = 0;
  v510[0] = v7;
  v511 = 0;
  v9 = (*v8 & 0x80000) == 0;
  v493 = v468;
  if ( v9 )
    goto LABEL_2;
  v80 = (unsigned int)v8[1];
  v81 = 0;
  if ( (_DWORD)v80 )
  {
    while ( *((_BYTE *)v8 + v81 + 8) != 13 )
    {
      v81 = (unsigned int)(v81 + 1);
      if ( (unsigned int)v81 >= (unsigned int)v80 )
        goto LABEL_783;
    }
    goto LABEL_130;
  }
LABEL_783:
  if ( (unsigned int)v81 < (unsigned int)v80 )
  {
LABEL_130:
    j = (bool *)v8 + 8 * v81 - (((_BYTE)v80 + 15) & 7) + v80 + 15;
    goto LABEL_131;
  }
  j = 0;
LABEL_131:
  v82 = **(CProjectedShadowReceiver ****)j;
  v83 = *(CProjectedShadowReceiver ***)(*(_QWORD *)j + 8LL);
  Src[0] = v83;
LABEL_132:
  if ( v82 == v83 )
  {
    v3 = v458;
LABEL_2:
    v10 = 0;
    goto LABEL_3;
  }
  v84 = *v82;
  v85 = (CProcessAttribution *)*((_QWORD *)*v82 + 11);
  v86 = (CProcessAttribution *)*((_QWORD *)*v82 + 10);
  v478 = v85;
  while ( 1 )
  {
    v479 = v86;
    if ( v86 == v85 )
    {
      v83 = (CProjectedShadowReceiver **)Src[0];
      ++v82;
      goto LABEL_132;
    }
    if ( !CCommonRegistryData::DisableProjectedShadows )
      break;
LABEL_144:
    v86 = (CProcessAttribution *)((char *)v86 + 8);
  }
  v87 = *(CProjectedShadowScene **)v86;
  if ( CProjectedShadowScene::IsEmptyProjection(*(CProjectedShadowScene **)v86)
    || CProjectedShadowReceiver::IsEmptyMaskContent(v84) )
  {
LABEL_143:
    v85 = v478;
    goto LABEL_144;
  }
  v88 = (__int64 ***)*((_QWORD *)v87 + 9);
  for ( i = *v88; ; i = (__int64 **)*i )
  {
    if ( i == (__int64 **)v88 )
    {
      v86 = v479;
      goto LABEL_143;
    }
    if ( !CProjectedShadowCaster::IsEmptyMaskContent((CProjectedShadowCaster *)i[2]) )
      break;
  }
  v3 = v458;
  v10 = 1;
LABEL_3:
  v11 = *((_DWORD *)v5 + 797);
  if ( *((_DWORD *)v5 + 796) == v11 )
  {
    v462[0] = 0;
    v479 = 0;
    v71 = Grow(1u, 0x40u, (unsigned int)j, v11, *((void **)v5 + 397), v462, (void **)&v479);
    if ( v71 >= 0 )
    {
      operator delete(*((void **)v5 + 397));
      *((_QWORD *)v5 + 397) = v479;
      *((_DWORD *)v5 + 797) = v462[0];
      goto LABEL_4;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8B,
      (unsigned int)"onecoreuap\\windows\\DWM\\dwmcore\\common\\WatermarkStack.inl",
      (const char *)(unsigned int)v71,
      v448);
  }
  else
  {
LABEL_4:
    *(_BYTE *)((unsigned int)(*((_DWORD *)v5 + 796))++ + *((_QWORD *)v5 + 397)) = v10;
    v12 = *((_DWORD *)v5 + 799);
    if ( v12 <= *((_DWORD *)v5 + 796) )
      v12 = *((_DWORD *)v5 + 796);
    *((_DWORD *)v5 + 799) = v12;
  }
  if ( *((_QWORD *)v5 + 24) )
  {
    v45 = *((_QWORD *)v5 + 996);
    v46 = *(_QWORD *)(*(_QWORD *)(v45 + 8) - 8LL);
    if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v46 + 192LL))(v46) )
    {
      v47 = (_QWORD *)(v7 + 320);
LABEL_60:
      if ( v47 )
      {
        for ( j = (bool *)v47[18]; j != (bool *)v47[19]; j += 8 )
        {
          v49 = *(_QWORD **)v45;
          v50 = *(_QWORD **)(*(_QWORD *)j + 1600LL);
          if ( *(_QWORD *)(*(_QWORD *)j + 1608LL) - (_QWORD)v50 == *(_QWORD *)(v45 + 8) - *(_QWORD *)v45 )
          {
            while ( v50 != *(_QWORD **)(*(_QWORD *)j + 1608LL) )
            {
              if ( *v50 != *v49 || v50[1] != v49[1] )
                goto LABEL_115;
              v50 += 2;
              v49 += 2;
            }
            *(_QWORD *)(*(_QWORD *)j + 1760LL) = *(_QWORD *)(*(_QWORD *)(v47[31] + 24LL) + 880LL);
            v48 = *(_QWORD *)j;
            goto LABEL_70;
          }
LABEL_115:
          ;
        }
      }
      goto LABEL_63;
    }
    j = *(bool **)(v7 + 224);
    if ( *(int *)j >= 0 )
    {
LABEL_63:
      v48 = 0;
LABEL_70:
      if ( v48 == *((_QWORD *)v5 + 24) )
        *((_BYTE *)v5 + 185) = 1;
      goto LABEL_8;
    }
    v66 = *((unsigned int *)j + 1);
    v67 = 0;
    if ( (_DWORD)v66 )
    {
      while ( !j[v67 + 8] )
      {
        v67 = (unsigned int)(v67 + 1);
        if ( (unsigned int)v67 >= (unsigned int)v66 )
          goto LABEL_159;
      }
    }
    else
    {
LABEL_159:
      if ( (unsigned int)v67 >= (unsigned int)v66 )
      {
        v68 = 0;
LABEL_108:
        v69 = *(_QWORD **)v68;
        if ( *(_QWORD *)v68 )
        {
          for ( k = (_QWORD *)*v69; k != v69; k = (_QWORD *)*k )
          {
            v47 = k - 43;
            if ( k[4] == v46 )
              goto LABEL_60;
          }
        }
        goto LABEL_63;
      }
    }
    v68 = &j[v66 + 15 + 8 * v67 - (((_BYTE)v66 + 15) & 7)];
    goto LABEL_108;
  }
LABEL_8:
  if ( *(char *)(v7 + 101) < 0 || (*(_DWORD *)(v7 + 96) & 0x100) == 0 )
    goto LABEL_10;
  if ( !(*(unsigned __int8 (__fastcall **)(const struct CVisualTree *))(*(_QWORD *)a2 + 192LL))(a2)
    && v7 != *((_QWORD *)a2 + 9) )
  {
    j = *(bool **)(v7 + 224);
    if ( (*(_DWORD *)j & 0x4000000) != 0 )
    {
      v57 = *((unsigned int *)j + 1);
      v58 = 0;
      if ( (_DWORD)v57 )
      {
        while ( j[v58 + 8] != 6 )
        {
          v58 = (unsigned int)(v58 + 1);
          if ( (unsigned int)v58 >= (unsigned int)v57 )
            goto LABEL_801;
        }
LABEL_81:
        v59 = &j[v57 + 15 + 8 * v58 - (((_BYTE)v57 + 15) & 7)];
      }
      else
      {
LABEL_801:
        if ( (unsigned int)v58 < (unsigned int)v57 )
          goto LABEL_81;
        v59 = 0;
      }
      if ( *(_QWORD *)v59 )
      {
        v60 = (*(__int64 (__fastcall **)(_QWORD))(***(_QWORD ***)v59 + 192LL))(**(_QWORD **)v59);
        if ( v60 )
        {
          if ( (*(unsigned __int8 (__fastcall **)(const struct CVisualTree *))(*(_QWORD *)a2 + 192LL))(a2) )
          {
            p_Blink = v7 + 320;
LABEL_86:
            if ( p_Blink && !*(_BYTE *)(p_Blink + 12) )
            {
              v62 = v60;
              while ( v60 )
              {
                if ( v60 == *((_QWORD *)a2 + 9) )
                  goto LABEL_32;
                if ( v62 )
                {
                  v62 = *(_QWORD *)(v62 + 88);
                  if ( v62 )
                  {
                    if ( v60 == v62 )
                      break;
                    v62 = *(_QWORD *)(v62 + 88);
                    if ( v60 == v62 )
                      break;
                  }
                }
                v60 = *(_QWORD *)(v60 + 88);
              }
LABEL_10:
              v13 = *((_DWORD *)v5 + 796);
              if ( v13 )
                *((_DWORD *)v5 + 796) = --v13;
              v14 = *((_DWORD *)v5 + 797);
              if ( v13 != v14 )
                goto LABEL_13;
              v457[0] = 0;
              v485 = 0;
              v100 = Grow(1u, 0x40u, (unsigned int)j, v14, *((void **)v5 + 397), v457, (void **)&v485);
              if ( v100 >= 0 )
              {
                operator delete(*((void **)v5 + 397));
                v101 = v485;
LABEL_157:
                *((_QWORD *)v5 + 397) = v101;
                *((_DWORD *)v5 + 797) = v457[0];
                goto LABEL_13;
              }
              goto LABEL_772;
            }
          }
          else
          {
            TreeDataListHead = CVisual::GetTreeDataListHead((CVisual *)v7);
            v379 = TreeDataListHead;
            if ( TreeDataListHead )
            {
              for ( m = TreeDataListHead->Flink; m != v379; m = m->Flink )
              {
                p_Blink = (__int64)&m[-22].Blink;
                if ( (const struct CVisualTree *)m[2].Flink == a2 )
                  goto LABEL_86;
              }
            }
          }
        }
      }
    }
  }
LABEL_32:
  if ( *((_BYTE *)v5 + 185) )
    goto LABEL_10;
  if ( (unsigned int)((__int64)(*(_QWORD *)(v7 + 272) - *(_QWORD *)(v7 + 264)) >> 3)
    || (unsigned int)((__int64)(*(_QWORD *)(v7 + 296) - *(_QWORD *)(v7 + 288)) >> 3) )
  {
    v492[1] = 1;
    v102 = (__int64 **)v492;
    v492[0] = 0;
    while ( v102 != &v493 )
    {
      v103 = *(_DWORD *)v102;
      v462[0] = *(_DWORD *)v102;
      for ( n = 0; ; n = v457[0] + 1 )
      {
        v457[0] = n;
        v105 = v103 ? *(_QWORD *)(v7 + 296) - *(_QWORD *)(v7 + 288) : *(_QWORD *)(v7 + 272) - *(_QWORD *)(v7 + 264);
        if ( (unsigned int)n >= (unsigned int)(v105 >> 3) )
          break;
        if ( v103 )
          v106 = *(_QWORD *)(v7 + 296) - *(_QWORD *)(v7 + 288);
        else
          v106 = *(_QWORD *)(v7 + 272) - *(_QWORD *)(v7 + 264);
        if ( (unsigned int)n >= (unsigned int)(v106 >> 3) )
        {
          v108 = 0;
        }
        else
        {
          if ( v103 )
            v107 = *(_QWORD *)(v7 + 288);
          else
            v107 = *(_QWORD *)(v7 + 264);
          v108 = *(_BYTE **)(v107 + 8 * n);
        }
        if ( v108[80] )
        {
          if ( (*(unsigned __int8 (__fastcall **)(_BYTE *, const struct CVisualTree *, __int64))(*(_QWORD *)v108 + 248LL))(
                 v108,
                 a2,
                 v7) )
          {
            Src[0] = (void *)10;
            Src[1] = (void *)v7;
            v109 = CWatermarkStack<TMilRect_<float,D2D_RECT_F,D3D_RECT_F,D2D_POINTANDSIZE_F,RectUniqueness::NotNeeded>,64,2,10>::Push(
                     (char *)v5 + 256,
                     Src);
            v19 = v109;
            if ( v109 < 0 )
            {
              v3 = v109;
              MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v109, 0x185Bu, 0);
              goto LABEL_177;
            }
            v445 = CLightStack::Push((char *)v5 + 416, v108, v462[0]);
            v458 = v445;
            v3 = v445;
            if ( v445 < 0 )
            {
              v19 = v445;
              MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v445, 0x185Eu, 0);
              CWatermarkStack<TMilRect_<float,D2D_RECT_F,D3D_RECT_F,D2D_POINTANDSIZE_F,RectUniqueness::NotNeeded>,64,2,10>::Pop(
                (char *)v5 + 256,
                0);
LABEL_177:
              v449 = 5430;
LABEL_23:
              v454 = v3;
              MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v19, v449, 0);
              goto LABEL_24;
            }
            v454 = v445;
          }
          v103 = v462[0];
        }
      }
      v102 = (__int64 **)((char *)v102 + 4);
    }
  }
  v22 = (_QWORD *)((char *)v5 + 648);
  v23 = *(CProcessAttribution **)(*((_QWORD *)v5 + 81) + 8LL * (unsigned int)(*((_DWORD *)v5 + 168) - 1));
  v24 = *(_QWORD *)v7;
  v479 = v23;
  v25 = (*(__int64 (__fastcall **)(__int64))(v24 + 160))(v7);
  v26 = (CProcessAttribution *)v25;
  if ( v25 && (CProcessAttribution *)v25 != v23 )
  {
    v480 = 0;
    v51 = *((unsigned int *)v5 + 67);
    if ( *((_DWORD *)v5 + 66) == (_DWORD)v51 )
    {
      v52 = (unsigned int)v51;
      v53 = 2 * v51;
      if ( v53 > 0xFFFFFFFF )
      {
        v54 = 95;
LABEL_75:
        v55 = -2147024362;
        v56 = -2147024362;
        goto LABEL_76;
      }
      v63 = 64;
      if ( (unsigned int)v53 > 0x40 )
        v63 = (unsigned int)v53;
      v64 = 16 * v52;
      v457[0] = v63;
      if ( v64 > 0xFFFFFFFF )
      {
        v54 = 98;
        goto LABEL_75;
      }
      if ( 0xFFFFFFFFFFFFFFFFuLL / v63 <= 0x10 )
      {
        v56 = -2147024809;
        goto LABEL_102;
      }
      Src[0] = *((void **)v5 + 32);
      v65 = MIDL_user_allocate(16 * v63);
      v491 = (__int64)v65;
      if ( !v65 )
      {
        v56 = -2147024882;
LABEL_102:
        v54 = 101;
        v55 = v56;
LABEL_76:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v54,
          (unsigned int)"onecoreuap\\windows\\DWM\\dwmcore\\common\\WatermarkStack.inl",
          (const char *)v55,
          v448);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x8B,
          (unsigned int)"onecoreuap\\windows\\DWM\\dwmcore\\common\\WatermarkStack.inl",
          (const char *)v56,
          v450);
        ModuleFailFastForHRESULT(v56, retaddr);
      }
      if ( Src[0] && (_DWORD)v64 )
        memcpy_0(v65, Src[0], (unsigned int)v64);
      operator delete(*((void **)v5 + 32));
      *((_QWORD *)v5 + 32) = v491;
      *((_DWORD *)v5 + 67) = v457[0];
    }
    v72 = *((_QWORD *)v5 + 32);
    v73 = (int)v480;
    v74 = 2LL * *((unsigned int *)v5 + 66);
    *(_DWORD *)(v72 + 8 * v74) = 11;
    *(_DWORD *)(v72 + 8 * v74 + 4) = v73;
    *(_QWORD *)(v72 + 8 * v74 + 8) = v7;
    ++*((_DWORD *)v5 + 66);
    v75 = *((_DWORD *)v5 + 69);
    if ( v75 <= *((_DWORD *)v5 + 66) )
      v75 = *((_DWORD *)v5 + 66);
    *((_DWORD *)v5 + 69) = v75;
    v499 = v26;
    v76 = *((_DWORD *)v5 + 168);
    v77 = v76 + 1;
    if ( v76 + 1 < v76 )
    {
      v78 = -2147024362;
      v79 = 183;
    }
    else
    {
      if ( v77 <= *((_DWORD *)v5 + 167) )
      {
        *(_QWORD *)(*v22 + 8LL * v76) = v26;
        *((_DWORD *)v5 + 168) = v77;
LABEL_123:
        v479 = v26;
        if ( g_HeatMaps_TargetProcessId && g_HeatMaps_TargetProcessId == *((_DWORD *)v26 + 32) )
          CDrawingContext::SetHeatMapForCurrentNode(v5);
        goto LABEL_37;
      }
      v479 = (CProcessAttribution *)&v499;
      v78 = DynArrayImpl<0>::Grow((__int64)v5 + 648, 8u, 1, 0, (unsigned __int64 *)&v479);
      if ( v78 >= 0 )
      {
        *(_QWORD *)((unsigned int)(8 * (*((_DWORD *)v5 + 168))++) + *v22) = *(_QWORD *)v479;
        goto LABEL_123;
      }
      v79 = 194;
    }
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v78, v79, 0);
    ModuleFailFastForHRESULT(v78, retaddr);
  }
LABEL_37:
  v17 = v461;
  *v461 = 1;
  if ( (*(_BYTE *)(v7 + 101) & 6) != 0 )
  {
    CVisual::GetHeatMapProperties(v7, Src);
    v446 = (*(_BYTE *)(v7 + 101) & 2) != 0;
    v501 = *(_OWORD *)Src;
    v500 = 2 - v446;
    v502 = v482;
    v447 = CWatermarkStack<CComposition::HeatMapOptions,2,2,2>::Push((char *)g_pComposition + 6264, &v500);
    v458 = v447;
    v3 = v447;
    v454 = v447;
    if ( v447 < 0 )
    {
      MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v447, 0x155Fu, 0);
      goto LABEL_25;
    }
  }
  v27 = (*(_DWORD *)(v7 + 96) >> 23) & 0x7F;
  if ( v27 )
  {
    v197 = (int)(*(_DWORD *)(v7 + 96) << 9) >> 28;
    v9 = *((_DWORD *)g_pComposition + 1568) == 0;
    v462[0] = *(_DWORD *)(v7 + 192);
    if ( v9 )
      goto LABEL_18;
    v198 = *((_DWORD *)g_pComposition + 1568);
    v199 = 0;
    if ( v198 )
      v199 = (_DWORD *)(*((_QWORD *)g_pComposition + 783) + 24LL * (unsigned int)(v198 - 1));
    if ( *v199 != 2 )
LABEL_18:
      v457[0] = *(_DWORD *)(v7 + 196);
    else
      v457[0] = 0;
    v454 = *(_DWORD *)(v7 + 200);
    LODWORD(v478) = *(_DWORD *)(v7 + 204);
    Src[0] = (void *)9;
    Src[1] = (void *)v7;
    v18 = CWatermarkStack<TMilRect_<float,D2D_RECT_F,D3D_RECT_F,D2D_POINTANDSIZE_F,RectUniqueness::NotNeeded>,64,2,10>::Push(
            (char *)v5 + 256,
            Src);
    v19 = v18;
    if ( v18 < 0 )
    {
      MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v18, 0x11C7u, 0);
    }
    else
    {
      Src[0] = *((void **)v5 + 29);
      HIDWORD(Src[1]) = *((_DWORD *)v5 + 60);
      v482 = *((_DWORD *)v5 + 61);
      v483 = *((_DWORD *)v5 + 62);
      LODWORD(Src[1]) = 0;
      v20 = CWatermarkStack<CDrawingContext::SavedRenderOptions,64,2,10>::Push((char *)v5 + 712, Src);
      v19 = v20;
      if ( v20 >= 0 )
      {
        v458 = v20;
        v3 = v20;
        if ( (v27 & 2) != 0 )
          *((_DWORD *)v5 + 58) = v197;
        if ( (v27 & 4) != 0 )
          *((_DWORD *)v5 + 59) = v462[0];
        if ( (v27 & 8) != 0 )
          *((_DWORD *)v5 + 60) = v457[0];
        if ( (v27 & 0x10) != 0 )
          *((_DWORD *)v5 + 61) = v454;
        if ( (v27 & 0x20) != 0 )
          *((_DWORD *)v5 + 62) = (_DWORD)v478;
        else
          v458 = v20;
        v454 = v20;
        goto LABEL_39;
      }
      MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v20, 0x11D5u, 0);
      CWatermarkStack<TMilRect_<float,D2D_RECT_F,D3D_RECT_F,D2D_POINTANDSIZE_F,RectUniqueness::NotNeeded>,64,2,10>::Pop(
        (char *)v5 + 256,
        0);
    }
    v3 = v19;
    v449 = 5486;
    goto LABEL_23;
  }
LABEL_39:
  v28 = *((_DWORD *)v5 + 72);
  v484 = 0;
  if ( v28 )
    v29 = (void *)(*((_QWORD *)v5 + 35) + 68LL * (unsigned int)(v28 - 1));
  else
    v29 = &CMILMatrix::Identity;
  v30 = *((_QWORD *)v5 + 993);
  v31 = v30 + 80;
  if ( v7 != *(_QWORD *)(v30 + 72) )
    v31 = v7 + 144;
  CMILMatrix::Transform3DBoundsHelper<1>(v29, v31, &v508);
  v34 = *((float *)&v508 + 2);
  v35 = (__m128)(unsigned int)v508;
  v36 = *((float *)&v508 + 3);
  v37 = *((float *)&v508 + 1);
  if ( *((float *)&v508 + 2) > *(float *)&v508 && *((float *)&v508 + 3) > *((float *)&v508 + 1) )
  {
    v38 = *(int *)(v7 + 96) >> 8;
    if ( (*(_DWORD *)(v7 + 96) & 0x200) != 0 )
    {
      v39 = FLOAT_4_0;
    }
    else if ( (v38 & 4) != 0 )
    {
      v39 = FLOAT_0_5;
    }
    else
    {
      v39 = 0.0;
    }
    if ( (v38 & 8) != 0 )
      v39 = v39 + 0.5;
    if ( v39 != 0.0 )
    {
      v35.m128_f32[0] = *(float *)&v508 - v39;
      v37 = *((float *)&v508 + 1) - v39;
      v34 = *((float *)&v508 + 2) + v39;
      v36 = *((float *)&v508 + 3) + v39;
      *(float *)&v508 = *(float *)&v508 - v39;
      *((float *)&v508 + 1) = *((float *)&v508 + 1) - v39;
      *((float *)&v508 + 2) = *((float *)&v508 + 2) + v39;
      *((float *)&v508 + 3) = *((float *)&v508 + 3) + v39;
      *(float *)&v509 = *(float *)&v509 + 0.0;
      *((float *)&v509 + 1) = *((float *)&v509 + 1) + 0.0;
    }
  }
  i2 = *((_QWORD *)v5 + 93);
  if ( i2 == *((_QWORD *)v5 + 92) )
  {
    si128 = (__m128)_mm_load_si128((const __m128i *)&_xmm);
    LODWORD(v41) = _mm_shuffle_ps(si128, si128, 255).m128_u32[0];
    LODWORD(v42) = _mm_shuffle_ps(si128, si128, 170).m128_u32[0];
    LODWORD(v43) = _mm_shuffle_ps(si128, si128, 85).m128_u32[0];
  }
  else
  {
    if ( *(_QWORD *)(i2 - 184) )
    {
      v183 = *((_DWORD *)v5 + 778);
      if ( v183 )
        v184 = *(__m128 *)(*((_QWORD *)v5 + 388) + 16LL * (unsigned int)(v183 - 1));
      else
        v184 = (__m128)_mm_load_si128((const __m128i *)&_xmm);
      LODWORD(v41) = _mm_shuffle_ps(v184, v184, 255).m128_u32[0];
      v484 = v184;
      LODWORD(v42) = _mm_shuffle_ps(v184, v184, 170).m128_u32[0];
    }
    else
    {
      (*(void (__fastcall **)(_QWORD, _DWORD *))(**(_QWORD **)(i2 - 192) + 88LL))(*(_QWORD *)(i2 - 192), v494);
      v36 = *((float *)&v508 + 3);
      v34 = *((float *)&v508 + 2);
      v37 = *((float *)&v508 + 1);
      v35 = (__m128)(unsigned int)v508;
      v42 = (float)v494[0];
      v41 = (float)v494[1];
    }
    i2 = *((_QWORD *)v5 + 93);
    if ( i2 == *((_QWORD *)v5 + 92) || !*(_QWORD *)(i2 - 168) )
    {
      v43 = v484.m128_f32[1];
      si128 = (__m128)v484.m128_u32[0];
    }
    else
    {
      v110 = *((_DWORD *)v5 + 784);
      if ( v110 )
      {
        v111 = (unsigned int)(v110 - 1);
        v112 = *((_QWORD *)v5 + 391);
        i2 = 2 * v111;
        v113 = (__m128)*(unsigned int *)(v112 + 8 * i2);
        v114 = *(float *)(v112 + 8 * i2 + 4);
        v115 = *(float *)(v112 + 8 * i2 + 8);
        v116 = *(float *)(v112 + 8 * i2 + 12);
      }
      else
      {
        v113 = (__m128)LODWORD(FLOAT_N3_4028235e38);
        v115 = FLOAT_3_4028235e38;
        v114 = FLOAT_N3_4028235e38;
        v116 = FLOAT_3_4028235e38;
      }
      si128 = (__m128)v484.m128_u32[0];
      if ( v113.m128_f32[0] > v484.m128_f32[0] )
        si128 = v113;
      v43 = v484.m128_f32[1];
      if ( v114 > v484.m128_f32[1] )
        v43 = v114;
      if ( v42 > v115 )
        v42 = v115;
      if ( v41 > v116 )
        v41 = v116;
      if ( v42 <= si128.m128_f32[0] || v41 <= v43 )
      {
        v41 = 0.0;
        v42 = 0.0;
        v43 = 0.0;
        si128 = 0;
      }
    }
  }
  if ( si128.m128_f32[0] > v35.m128_f32[0] )
  {
    LODWORD(v508) = si128.m128_i32[0];
    v35 = si128;
  }
  if ( v43 > v37 )
  {
    *((float *)&v508 + 1) = v43;
    v37 = v43;
  }
  if ( v34 > v42 )
  {
    *((float *)&v508 + 2) = v42;
    v34 = v42;
  }
  if ( v36 > v41 )
  {
    *((float *)&v508 + 3) = v41;
    v36 = v41;
  }
  v117 = *((float *)&v509 + 1) <= *(float *)&v509;
  if ( v34 <= v35.m128_f32[0] )
    ++v117;
  if ( v36 <= v37 )
    ++v117;
  if ( v117 > 1 )
  {
    v36 = 0.0;
    v35 = 0;
    v508 = 0u;
    v34 = 0.0;
    v37 = 0.0;
    v509 = 0;
  }
  *(_QWORD *)&v495 = __PAIR64__(LODWORD(v37), v35.m128_u32[0]);
  *((_QWORD *)&v495 + 1) = __PAIR64__(LODWORD(v36), LODWORD(v34));
  if ( v34 <= v35.m128_f32[0] || v36 <= v37 )
  {
    v203 = *((_DWORD *)v5 + 796);
    if ( v203 )
      *((_DWORD *)v5 + 796) = --v203;
    v204 = *((_DWORD *)v5 + 797);
    if ( v203 == v204 )
    {
      v457[0] = 0;
      v485 = 0;
      v100 = Grow(1u, 0x40u, (unsigned int)v33, v204, *((void **)v5 + 397), v457, (void **)&v485);
      if ( v100 < 0 )
        goto LABEL_772;
      operator delete(*((void **)v5 + 397));
      *((_QWORD *)v5 + 397) = v485;
      *((_DWORD *)v5 + 797) = v457[0];
    }
    *(_BYTE *)((unsigned int)(*((_DWORD *)v5 + 796))++ + *((_QWORD *)v5 + 397)) = 0;
    i2 = *((unsigned int *)v5 + 796);
    goto LABEL_14;
  }
  if ( !*((_BYTE *)v5 + 7937) )
    goto LABEL_275;
  v118 = (_DWORD *)*((_QWORD *)v5 + 995);
  Src[0] = v118;
  if ( v118 )
  {
    v119 = v118[270];
    v120 = (_QWORD *)v7;
    LODWORD(v478) = v119;
    while ( 1 )
    {
      if ( !v120 )
        goto LABEL_252;
      if ( !(*(unsigned __int8 (__fastcall **)(const struct CVisualTree *))(*(_QWORD *)a2 + 192LL))(a2) )
        break;
      v121 = v120 + 40;
LABEL_230:
      if ( v121 )
      {
        v32 = v121[22];
        v122 = 0;
        for ( ii = v32; ; ii += 8 )
        {
          if ( ii == v121[23] )
            goto LABEL_237;
          if ( *(_DWORD *)(*(_QWORD *)ii + 32LL) == v119 )
            break;
        }
        v122 = *(_QWORD *)ii;
LABEL_237:
        i2 = *(_QWORD *)(*(_QWORD *)(v121[31] + 24) + 880LL);
        v480 = (void *)i2;
        if ( v121[27] != i2 )
        {
          v121[27] = i2;
          v33 = (unsigned int *)v121[23];
          if ( (unsigned __int64)(((__int64)v33 - v32) >> 3) > 1 )
          {
            while ( (unsigned int *)v32 != v33 )
            {
              if ( *(_QWORD *)v32 != v122 && (v223 = *(_QWORD *)(*(_QWORD *)v32 + 16LL)) != 0 && i2 - v223 >= 0xA )
              {
                v327 = v121[22];
                v328 = (v32 - v327) >> 3;
                v329 = ((__int64)v33 - v327) >> 3;
                v490 = v328;
                if ( v328 + 1 > v329 )
                {
LABEL_656:
                  std::_Xoverflow_error("overflow");
                  __debugbreak();
                }
                v432 = (_QWORD *)(v327 + 8 * v329);
                *(_QWORD *)v457 = v432;
                if ( v328 + 1 != v329 )
                {
                  if ( v328 && (!v327 || v328 < 0 || v329 < v328) )
                    goto LABEL_973;
                  v441 = (_QWORD *)(v327 + 8 * (v328 + 1));
                  v442 = v432 - v441;
                  v443 = v442 <= 0;
                  if ( v442 < 0 )
                  {
                    if ( v328 < (unsigned __int64)-v442 )
                      goto LABEL_973;
                    v443 = v442 <= 0;
                  }
                  if ( !v443 && v329 - v328 < v442 )
LABEL_973:
                    __fastfail(5u);
                  v444 = *(_QWORD **)v457;
                  for ( jj = (void (__fastcall ****)(_QWORD, __int64))(v327 + 8 * v328); ; ++jj )
                  {
                    *(_QWORD *)v462 = jj;
                    if ( v441 == v444 )
                      break;
                    v438 = (void (__fastcall ***)(_QWORD, __int64))*v441;
                    *v441 = 0;
                    v439 = *jj;
                    *jj = v438;
                    if ( v439 )
                    {
                      (**v439)(v439, 1);
                      jj = *(void (__fastcall *****)(_QWORD, __int64))v462;
                    }
                    ++v441;
                  }
                  v5 = (CDrawingContext *)v512;
                  v7 = v510[0];
                  v432 = *(_QWORD **)v457;
                }
                v434 = v432 - 1;
                do
                {
                  if ( *v434 )
                  {
                    (**(void (__fastcall ***)(_QWORD, __int64))*v434)(*v434, 1);
                    v432 = *(_QWORD **)v457;
                  }
                  ++v434;
                }
                while ( v434 != v432 );
                v435 = v490;
                i2 = (unsigned __int64)v480;
                v33 = (unsigned int *)(v121[23] - 8);
                v121[23] = (__int64)v33;
                v32 = v121[22] + 8 * v435;
              }
              else
              {
                v32 += 8;
              }
            }
            v119 = (int)v478;
          }
        }
        if ( v122 )
        {
          v33 = 0;
          if ( g_pComposition )
            v33 = (unsigned int *)*((_QWORD *)g_pComposition + 110);
          if ( *(unsigned int **)(v122 + 16) != v33 )
            (*(void (__fastcall **)(__int64, const struct CVisualTree *))(*(_QWORD *)v122 + 16LL))(v122, a2);
          v124 = *(_DWORD *)(v122 + 36);
          if ( !v124 )
            goto LABEL_252;
          v125 = Src[0];
          v126 = 0;
          v127 = _mm_shuffle_ps(v35, v35, 225);
          v127.m128_f32[0] = v37;
          v128 = _mm_shuffle_ps(v127, v127, 198);
          v129 = *((_DWORD *)Src[0] + 148);
          v128.m128_f32[0] = v34;
          v130 = _mm_shuffle_ps(v128, v128, 39);
          v130.m128_f32[0] = v36;
          *(__m128 *)v510 = _mm_shuffle_ps(v130, v130, 57);
          v131 = *((float *)&v510[1] + 1);
          v132 = *(float *)&v510[1];
          v133 = *((float *)v510 + 1);
          v134 = *(float *)v510;
          while ( 1 )
          {
            if ( (unsigned int)v126 >= v129
              || (v135 = v125[71], i2 = 6 * v126, *(_DWORD *)(v135 + 48 * v126 + 16) >= v124) )
            {
              v136 = 0;
              goto LABEL_251;
            }
            if ( *(float *)(v135 + 48 * v126 + 8) > *(float *)(v135 + 48 * v126)
              && *(float *)(v135 + 48 * v126 + 12) > *(float *)(v135 + 48 * v126 + 4) )
            {
              v188 = v134;
              v486 = __PAIR64__(LODWORD(v133), LODWORD(v134));
              v189 = v133;
              v487 = __PAIR64__(LODWORD(v131), LODWORD(v132));
              v190 = v132;
              v191 = v131;
              v192 = *(float *)(v135 + 48 * v126);
              if ( v192 > v134 )
              {
                LODWORD(v486) = *(_DWORD *)(v135 + 48 * v126);
                v188 = v192;
              }
              v193 = *(float *)(v135 + 48 * v126 + 4);
              if ( v193 > v133 )
              {
                HIDWORD(v486) = *(_DWORD *)(v135 + 48 * v126 + 4);
                v189 = v193;
              }
              v194 = *(float *)(v135 + 48 * v126 + 8);
              if ( v132 > v194 )
              {
                LODWORD(v487) = *(_DWORD *)(v135 + 48 * v126 + 8);
                v190 = v194;
              }
              v195 = *(float *)(v135 + 48 * v126 + 12);
              if ( v131 > v195 )
              {
                HIDWORD(v487) = *(_DWORD *)(v135 + 48 * v126 + 12);
                v191 = v195;
              }
              if ( v190 <= v188 || v191 <= v189 )
              {
                v487 = 0;
                v486 = 0;
              }
              else
              {
                v512 = 0;
                v196 = TMilRect<float,D2D_RECT_F,D3D_RECT_F,RectUniqueness::NotNeeded>::CalcSubtractionRectangles(
                         (unsigned int)v510,
                         (unsigned int)&v486,
                         (_DWORD)v33,
                         (unsigned int)&v512,
                         1);
                if ( !v196 )
                {
                  v136 = 1;
LABEL_251:
                  if ( !v136 )
                  {
LABEL_252:
                    v3 = v458;
                    goto LABEL_253;
                  }
                  v276 = *((_DWORD *)v5 + 796);
                  if ( v276 )
                    *((_DWORD *)v5 + 796) = --v276;
                  v277 = *((_DWORD *)v5 + 797);
                  if ( v276 == v277 )
                  {
                    v457[0] = 0;
                    v480 = 0;
                    v431 = Grow(1u, 0x40u, (unsigned int)v33, v277, *((void **)v5 + 397), v457, &v480);
                    if ( v431 < 0 )
                    {
                      wil::details::in1diag3::Return_Hr(
                        retaddr,
                        (void *)0x8B,
                        (unsigned int)"onecoreuap\\windows\\DWM\\dwmcore\\common\\WatermarkStack.inl",
                        (const char *)(unsigned int)v431,
                        v452);
                      v17 = v461;
                      v3 = v458;
                      *v461 = 0;
                      goto LABEL_25;
                    }
                    operator delete(*((void **)v5 + 397));
                    *((_QWORD *)v5 + 397) = v480;
                    *((_DWORD *)v5 + 797) = v457[0];
                  }
                  v3 = v458;
LABEL_13:
                  *(_BYTE *)(*((unsigned int *)v5 + 796) + *((_QWORD *)v5 + 397)) = 0;
                  i2 = (unsigned int)(*((_DWORD *)v5 + 796) + 1);
                  *((_DWORD *)v5 + 796) = i2;
LABEL_14:
                  v16 = *((_DWORD *)v5 + 799);
                  if ( v16 <= (unsigned int)i2 )
                    v16 = i2;
                  *((_DWORD *)v5 + 799) = v16;
LABEL_17:
                  v17 = v461;
                  *v461 = 0;
                  goto LABEL_25;
                }
                if ( v196 == 1 )
                {
                  LODWORD(v134) = v512;
                  v126 = (unsigned int)(v126 + 1);
                  v133 = *((float *)&v512 + 1);
                  v132 = *((float *)&v512 + 2);
                  v131 = *((float *)&v512 + 3);
                  *(_OWORD *)v510 = v512;
                  continue;
                }
              }
            }
            v126 = (unsigned int)(v126 + 1);
          }
        }
      }
LABEL_231:
      if ( v120 == *((_QWORD **)a2 + 9) )
        v120 = 0;
      else
        v120 = (_QWORD *)v120[11];
    }
    v33 = (unsigned int *)v120[28];
    if ( (*v33 & 0x80000000) == 0 )
      goto LABEL_231;
    v185 = v33[1];
    v186 = 0;
    if ( (_DWORD)v185 )
    {
      while ( *((_BYTE *)v33 + v186 + 8) != 1 )
      {
        v186 = (unsigned int)(v186 + 1);
        if ( (unsigned int)v186 >= (unsigned int)v185 )
          goto LABEL_436;
      }
LABEL_345:
      v32 = (__int64)v33 + v185 + 8 * v186 - (((_BYTE)v185 + 15) & 7) + 15;
    }
    else
    {
LABEL_436:
      if ( (unsigned int)v186 < (unsigned int)v185 )
        goto LABEL_345;
      v32 = 0;
    }
    i2 = *(_QWORD *)v32;
    if ( *(_QWORD *)v32 )
    {
      for ( kk = *(__int64 **)i2; kk != (__int64 *)i2; kk = (__int64 *)*kk )
      {
        v121 = kk - 43;
        if ( (const struct CVisualTree *)kk[4] == a2 )
          goto LABEL_230;
      }
    }
    goto LABEL_231;
  }
LABEL_253:
  if ( !*((_BYTE *)v5 + 7937) )
    goto LABEL_275;
  v137 = *((_QWORD *)v5 + 995);
  if ( !v137 )
    goto LABEL_275;
  v138 = (void (__fastcall ****)(_QWORD, __int64))v7;
  v457[0] = *(_DWORD *)(v137 + 1080);
  while ( 2 )
  {
    *(_QWORD *)v462 = v138;
    if ( !v138 )
    {
      v142 = 0;
      goto LABEL_274;
    }
    if ( !(*(unsigned __int8 (__fastcall **)(const struct CVisualTree *))(*(_QWORD *)a2 + 192LL))(a2) )
    {
      v33 = (unsigned int *)v138[28];
      if ( (*v33 & 0x80000000) != 0 )
      {
        v224 = v33[1];
        for ( mm = 0; (unsigned int)mm < v224; mm = (unsigned int)(mm + 1) )
        {
          if ( *((_BYTE *)v33 + mm + 8) == 1 )
            break;
        }
        v226 = v33[1];
        v32 = (unsigned int)mm >= (unsigned int)v226
            ? 0LL
            : (__int64)v33 + 8 * mm - (((_BYTE)v226 + 15) & 7) + v226 + 15;
        i2 = *(_QWORD *)v32;
        if ( *(_QWORD *)v32 )
        {
          for ( nn = *(__int64 **)i2; nn != (__int64 *)i2; nn = (__int64 *)*nn )
          {
            v139 = nn - 43;
            if ( (const struct CVisualTree *)nn[4] == a2 )
              goto LABEL_259;
          }
        }
      }
      goto LABEL_381;
    }
    v139 = (__int64 *)(v138 + 40);
LABEL_259:
    if ( !v139 )
      goto LABEL_381;
    v140 = (CProcessAttribution **)v139[22];
    v141 = 0;
    v32 = v457[0];
    v478 = 0;
    while ( v140 != (CProcessAttribution **)v139[23] )
    {
      if ( *((_DWORD *)*v140 + 8) == v457[0] )
      {
        v141 = *v140;
        v478 = *v140;
        break;
      }
      ++v140;
    }
    i2 = *(_QWORD *)(v139[31] + 24);
    v33 = *(unsigned int **)(i2 + 880);
    Src[0] = v33;
    if ( (unsigned int *)v139[27] != v33 )
    {
      v139[27] = (__int64)v33;
      v32 = v139[23];
      i2 = v139[22];
      if ( (unsigned __int64)((__int64)(v32 - i2) >> 3) > 1 )
      {
        while ( i2 != v32 )
        {
          if ( *(CProcessAttribution **)i2 != v141
            && (v254 = *(_QWORD *)(*(_QWORD *)i2 + 16LL)) != 0
            && (unsigned __int64)v33 - v254 >= 0xA )
          {
            v360 = v139[22];
            v361 = (__int64)(i2 - v360) >> 3;
            v362 = (v32 - v360) >> 3;
            v491 = v361;
            if ( v361 + 1 > v362 )
              goto LABEL_656;
            v363 = (__int64 *)(v360 + 8 * v362);
            v490 = (__int64)v363;
            if ( v361 + 1 != v362 )
            {
              if ( v361 && (!v360 || v361 < 0 || v362 < v361) )
                goto LABEL_973;
              v364 = (__int64 *)(v360 + 8 * (v361 + 1));
              v365 = v363 - v364;
              v366 = v365 <= 0;
              if ( v365 < 0 )
              {
                if ( v361 < (unsigned __int64)-v365 )
                  goto LABEL_973;
                v366 = v365 <= 0;
              }
              if ( !v366 && v362 - v361 < v365 )
                goto LABEL_973;
              for ( i1 = (_QWORD *)(v360 + 8 * v361); ; ++i1 )
              {
                v480 = i1;
                if ( v364 == v363 )
                  break;
                v368 = *v364;
                *v364 = 0;
                v369 = (void (__fastcall ***)(_QWORD, __int64))*i1;
                *i1 = v368;
                if ( v369 )
                {
                  (**v369)(v369, 1);
                  v363 = (__int64 *)v490;
                  i1 = v480;
                }
                ++v364;
              }
              v3 = v458;
              v141 = v478;
              v33 = (unsigned int *)Src[0];
            }
            v436 = v363 - 1;
            do
            {
              if ( *v436 )
              {
                (**(void (__fastcall ***)(__int64, __int64, void *, CProcessAttribution *))*v436)(*v436, 1, v33, v141);
                v363 = (__int64 *)v490;
              }
              ++v436;
            }
            while ( v436 != v363 );
            v141 = v478;
            v437 = v491;
            v33 = (unsigned int *)Src[0];
            v32 = v139[23] - 8;
            v139[23] = v32;
            i2 = v139[22] + 8 * v437;
          }
          else
          {
            i2 += 8LL;
          }
        }
        v138 = *(void (__fastcall *****)(_QWORD, __int64))v462;
      }
    }
    if ( !v141 )
    {
LABEL_381:
      if ( v138 == *((void (__fastcall *****)(_QWORD, __int64))a2 + 9) )
        v138 = 0;
      else
        v138 = (void (__fastcall ****)(_QWORD, __int64))v138[11];
      continue;
    }
    break;
  }
  v33 = 0;
  if ( g_pComposition )
    v33 = (unsigned int *)*((_QWORD *)g_pComposition + 110);
  if ( *((unsigned int **)v141 + 2) != v33 )
  {
    (*(void (__fastcall **)(CProcessAttribution *, const struct CVisualTree *))(*(_QWORD *)v141 + 16LL))(v141, a2);
    v141 = v478;
  }
  v142 = *((_DWORD *)v141 + 10);
LABEL_274:
  *((_DWORD *)v5 + 1994) = v142;
  if ( v142 >= *(_DWORD *)(v137 + 1104) )
  {
    v339 = v457[0];
    v340 = (_QWORD *)v7;
    while ( 1 )
    {
      if ( !v340 )
      {
        v345 = 0;
        goto LABEL_685;
      }
      if ( (*(unsigned __int8 (__fastcall **)(const struct CVisualTree *, __int64))(*(_QWORD *)a2 + 192LL))(a2, v32) )
      {
        v341 = (CProcessAttribution *)(v340 + 40);
LABEL_668:
        v478 = v341;
      }
      else
      {
        v478 = 0;
        v358 = (unsigned __int64 *)CVisual::GetTreeDataListHead((CVisual *)v340);
        if ( v358 )
        {
          for ( i2 = *v358; (unsigned __int64 *)i2 != v358; i2 = *(_QWORD *)i2 )
          {
            if ( *(const struct CVisualTree **)(i2 + 32) == a2 )
            {
              v341 = (CProcessAttribution *)(i2 - 344);
              goto LABEL_668;
            }
          }
        }
      }
      if ( v341 )
      {
        v342 = *((_QWORD *)v341 + 22);
        v343 = 0;
        *(_QWORD *)v457 = 0;
        while ( v342 != *((_QWORD *)v341 + 23) )
        {
          if ( *(_DWORD *)(*(_QWORD *)v342 + 32LL) == v339 )
          {
            v343 = *(_QWORD **)v342;
            *(_QWORD *)v457 = *(_QWORD *)v342;
            break;
          }
          v342 += 8;
        }
        i2 = *(_QWORD *)(*((_QWORD *)v341 + 31) + 24LL);
        v32 = *(_QWORD *)(i2 + 880);
        v510[0] = v32;
        if ( *((_QWORD *)v341 + 27) != v32 )
        {
          *((_QWORD *)v341 + 27) = v32;
          v344 = (unsigned __int64 *)*((_QWORD *)v341 + 22);
          i2 = (__int64)(*((_QWORD *)v341 + 23) - (_QWORD)v344) >> 3;
          if ( i2 > 1 )
          {
            while ( v344 != *((unsigned __int64 **)v341 + 23) )
            {
              i2 = *v344;
              if ( (_QWORD *)*v344 != v343
                && (v33 = *(unsigned int **)(i2 + 16)) != 0
                && (i2 = v32 - (_QWORD)v33, (unsigned __int64)(v32 - (_QWORD)v33) >= 0xA) )
              {
                v496 = v344;
                v433 = (unsigned __int64 **)detail::vector_facade<std::unique_ptr<COcclusionInfo>,detail::buffer_impl<std::unique_ptr<COcclusionInfo>,1,1,detail::liberal_expansion_policy>>::erase(
                                              (char *)v341 + 176,
                                              v505,
                                              &v496);
                v341 = v478;
                v343 = *(_QWORD **)v457;
                v32 = v510[0];
                v344 = *v433;
              }
              else
              {
                ++v344;
              }
            }
          }
        }
        if ( v343 )
          break;
      }
      if ( v340 == *((_QWORD **)a2 + 9) )
        v340 = 0;
      else
        v340 = (_QWORD *)v340[11];
    }
    v33 = 0;
    if ( g_pComposition )
      v33 = (unsigned int *)*((_QWORD *)g_pComposition + 110);
    if ( (unsigned int *)v343[2] != v33 )
    {
      (*(void (__fastcall **)(_QWORD *, const struct CVisualTree *))(*v343 + 16LL))(v343, a2);
      v343 = *(_QWORD **)v457;
    }
    v345 = *((_DWORD *)v343 + 9);
LABEL_685:
    if ( v345 < *(_DWORD *)(v137 + 1104) )
      goto LABEL_24;
    v346 = *((_DWORD *)v5 + 796);
    if ( v346 )
      *((_DWORD *)v5 + 796) = --v346;
    v347 = *((_DWORD *)v5 + 797);
    if ( v346 != v347 )
      goto LABEL_13;
    v457[0] = 0;
    Src[0] = 0;
    v100 = Grow(1u, 0x40u, (unsigned int)v33, v347, *((void **)v5 + 397), v457, Src);
    if ( v100 >= 0 )
    {
      operator delete(*((void **)v5 + 397));
      v101 = (struct CVisual *)Src[0];
      goto LABEL_157;
    }
LABEL_772:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8B,
      (unsigned int)"onecoreuap\\windows\\DWM\\dwmcore\\common\\WatermarkStack.inl",
      (const char *)(unsigned int)v100,
      v451);
    v17 = v461;
    *v461 = 0;
    goto LABEL_25;
  }
LABEL_275:
  *(_QWORD *)&v463 = v7;
  if ( v7 == *((_QWORD *)a2 + 9) )
  {
    v145 = FLOAT_1_0;
  }
  else
  {
    v143 = *(_QWORD *)(v7 + 216);
    if ( (*(_DWORD *)(v143 + 4) & 0x8000000) != 0 )
    {
      v274 = *(float *)(v143 + 12);
      v275 = (float *)(v143 + 12);
      if ( (LODWORD(v274) & 0x7F000000) != 0x5000000 )
      {
        do
        {
          v275 = (float *)((char *)v275 + (LODWORD(v274) & 0xFFFFFF) + 4);
          v274 = *v275;
        }
        while ( (*(_DWORD *)v275 & 0x7F000000) != 0x5000000 );
      }
      v144 = v275[1];
    }
    else
    {
      v144 = FLOAT_1_0;
    }
    v145 = fminf(1.0, fmaxf(v144, 0.0));
  }
  v467 = v145;
  v146 = FLOAT_1_0;
  v147 = *(_DWORD **)(v7 + 224);
  if ( (*v147 & 0x1000000) != 0 )
  {
    v278 = v147[1];
    for ( i3 = 0; (unsigned int)i3 < v278; i3 = (unsigned int)(i3 + 1) )
    {
      if ( *((_BYTE *)v147 + i3 + 8) == 8 )
        break;
    }
    v280 = (unsigned int)v147[1];
    if ( (unsigned int)i3 >= (unsigned int)v280 )
      v281 = 0;
    else
      v281 = (float **)((char *)v147 + 8LL * (unsigned int)i3 - (((_BYTE)v280 + 15) & 7) + v280 + 15);
    v282 = *v281;
    v283 = (*(__int64 (__fastcall **)(float *, __int64))(*(_QWORD *)v282 + 64LL))(v282, 49);
    v145 = v467;
    if ( v283 )
      v146 = v282[20];
  }
  v148 = v145 * fminf(1.0, fmaxf(v146, 0.0));
  v467 = v148;
  v149 = *((_DWORD *)v5 + 790);
  if ( v149 )
    v150 = *(float *)(*((_QWORD *)v5 + 394) + 4LL * (unsigned int)(v149 - 1));
  else
    v150 = FLOAT_1_0;
  v467 = v148 * v150;
  v151 = BYTE1(v477[0]);
  if ( (*(_DWORD *)(*(_QWORD *)(v7 + 216) + 4LL) & 0x8000) != 0 )
    v151 = 1;
  BYTE1(v477[0]) = v151;
  v152 = *(_DWORD **)(v7 + 224);
  if ( (*v152 & 0x1000000) != 0 )
  {
    v296 = v152[1];
    for ( i4 = 0; (unsigned int)i4 < v296; i4 = (unsigned int)(i4 + 1) )
    {
      if ( *((_BYTE *)v152 + i4 + 8) == 8 )
        break;
    }
    v298 = (unsigned int)v152[1];
    if ( (unsigned int)i4 >= (unsigned int)v298 )
      v299 = 0;
    else
      v299 = (_QWORD *)((char *)v152 + 8 * i4 - (((_BYTE)v298 + 15) & 7) + v298 + 15);
    if ( (*(unsigned __int8 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v299 + 64LL))(*v299, 52) )
      BYTE2(v477[0]) = 1;
  }
  if ( (*(_DWORD *)(*(_QWORD *)(v7 + 216) + 4LL) & 0x4000000) != 0 )
  {
    (*(void (__fastcall **)(__int64, char *))(*(_QWORD *)(*((_QWORD *)v5 + 3) + 8LL) + 24LL))(
      *((_QWORD *)v5 + 3) + 8LL,
      v517);
    ColorSpace = CVisual::GetColorSpace((CVisual *)v7);
    if ( ColorSpace != *(_DWORD *)(v419 + 8) )
      LOBYTE(v477[1]) = 1;
  }
  if ( (*(unsigned __int8 (__fastcall **)(__int64, __int64))(*(_QWORD *)v7 + 64LL))(v7, 72) )
  {
    if ( *(_QWORD *)(v7 + 672) || *(_QWORD *)(v7 + 664) )
    {
      v153 = 1;
      if ( *(_BYTE *)(v7 + 688) )
      {
        if ( *(_BYTE *)(v7 + 689) )
        {
          if ( v7 == *(_QWORD *)(*((_QWORD *)v5 + 993) + 72LL) )
          {
            i2 = *((_QWORD *)v5 + 25);
            if ( i2 )
            {
              if ( CDrawingContext::GetCurrentVisual((CDrawingContext *)i2) == (struct CVisual *)v7 )
                v153 = 0;
            }
          }
        }
      }
    }
    else
    {
      v153 = 0;
    }
    HIBYTE(v477[0]) = v153;
  }
  v154 = v467;
  v155 = _mm_load_si128((const __m128i *)&_xmm).m128i_u32[0];
  if ( v467 < 1.0 && COERCE_FLOAT(COERCE_UNSIGNED_INT(v467 - 1.0) & v155) >= 0.0000011920929 )
  {
    if ( (*(_DWORD *)(v7 + 96) & 0x10000) == 0 && *((_DWORD *)v5 + 60) != 4
      || *((_DWORD *)v5 + 61) == 1
      || *(_DWORD *)(v7 + 104) == 1 )
    {
      BYTE1(v477[1]) = 1;
    }
    else
    {
      if ( EventEnabled(Microsoft_Windows_Dwm_Core_Provider_Context, &EVTDESC_ETWGUID_LAYEREVENT_BeginLayer_Start) )
      {
        v9 = (unsigned int)detail::vector_facade<CResource *,detail::pointer_buffer_impl<CResource *,0>>::size(v7 + 80) == 0;
        v417 = HIDWORD(v476);
        if ( !v9 )
        {
          v417 = HIDWORD(v476) | 0x20;
          HIDWORD(v476) |= 0x20u;
        }
        if ( (*(_DWORD *)(v7 + 96) & 0x10000) != 0 )
          HIDWORD(v476) = v417 | 0x40;
      }
      v154 = v467;
    }
  }
  v156 = *(_QWORD *)(v7 + 216);
  if ( (*(_DWORD *)(v156 + 4) & 0x2000000) != 0 )
  {
    v200 = *(_DWORD *)(v156 + 12);
    i2 = v156 + 12;
    if ( (v200 & 0x7F000000) != 0x7000000 )
    {
      do
      {
        i2 += (v200 & 0xFFFFFF) + 4LL;
        v200 = *(_DWORD *)i2;
      }
      while ( (*(_DWORD *)i2 & 0x7F000000) != 0x7000000 );
    }
    v157 = *(_DWORD *)(i2 + 4);
    v466 = v157;
  }
  else
  {
    v157 = v466;
  }
  if ( BYTE2(v477[0]) || *(_WORD *)((char *)v477 + 3) || v157 )
  {
    LODWORD(v476) = 3;
    if ( HIBYTE(v477[0]) )
      LODWORD(v476) = 4;
  }
  if ( COERCE_FLOAT(LODWORD(v154) & v155) < 0.0000011920929 )
    goto LABEL_17;
  v158 = *(CGeometry **)(v7 + 240);
  if ( !v158 )
    goto LABEL_299;
  v516 = 0;
  if ( v464 && *((_QWORD *)&v463 + 1) )
    (***((void (__fastcall ****)(_QWORD, __int64))&v463 + 1))(*((_QWORD *)&v463 + 1), 1);
  *((_QWORD *)&v463 + 1) = 0;
  v464 = 0;
  v488 = 0;
  v489 = 0;
  ShapeData = CGeometry::GetShapeData(v158, (const struct D2D_SIZE_F *)(v7 + 136), (struct CShapePtr *)&v488);
  v3 = ShapeData;
  if ( ShapeData < 0 )
  {
    v232 = ShapeData;
    v234 = 2384;
    goto LABEL_451;
  }
  v231 = v488;
  v232 = -2003304309;
  if ( v488 )
  {
    v233 = (*(__int64 (__fastcall **)(__int64, __int128 *, _QWORD))(*(_QWORD *)v488 + 48LL))(v488, &v516, 0);
    v232 = v233;
    if ( v233 < 0 )
    {
      MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v233, 0x137u, 0);
      v3 = v232;
      goto LABEL_450;
    }
    v231 = v488;
  }
  v3 = v232;
  if ( v232 < 0 )
  {
LABEL_450:
    v234 = 2385;
LABEL_451:
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v232, v234, 0);
    if ( v3 == -2003304438 || v3 == -2003304309 )
      v3 = 0;
    goto LABEL_453;
  }
  v415 = v489;
  if ( v464 && *((_QWORD *)&v463 + 1) )
    (***((void (__fastcall ****)(_QWORD, __int64))&v463 + 1))(*((_QWORD *)&v463 + 1), 1);
  *((_QWORD *)&v463 + 1) = v231;
  v464 = v415;
  v488 = 0;
  v489 = 0;
LABEL_453:
  if ( v489 && v488 )
    (**(void (__fastcall ***)(__int64, __int64))v488)(v488, 1);
  v488 = 0;
  v489 = 0;
  v454 = v3;
  if ( v3 < 0 )
  {
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v3, 0x15C5u, 0);
    goto LABEL_24;
  }
LABEL_299:
  v159 = &v470[36];
  if ( !*((_QWORD *)&v463 + 1) )
    v159 = 0;
  if ( !(*(unsigned __int8 (__fastcall **)(const struct CVisualTree *))(*(_QWORD *)a2 + 192LL))(a2) )
  {
    v216 = *(int **)(v7 + 224);
    if ( *v216 < 0 )
    {
      v217 = v216[1];
      for ( i5 = 0; (unsigned int)i5 < v217; i5 = (unsigned int)(i5 + 1) )
      {
        if ( *((_BYTE *)v216 + i5 + 8) == 1 )
          break;
      }
      v219 = (unsigned int)v216[1];
      v220 = (unsigned int)i5 >= (unsigned int)v219
           ? 0LL
           : (int *)((char *)v216 + 8 * i5 - (((_BYTE)v219 + 15) & 7) + v219 + 15);
      v221 = *(__int64 ****)v220;
      if ( *(_QWORD *)v220 )
      {
        for ( i6 = *v221; i6 != (__int64 **)v221; i6 = (__int64 **)*i6 )
        {
          v160 = (__m128 *)(i6 - 43);
          if ( i6[4] == (__int64 *)a2 )
            goto LABEL_303;
        }
      }
    }
    goto LABEL_419;
  }
  v160 = (__m128 *)(v7 + 320);
LABEL_303:
  if ( !v160 )
  {
LABEL_419:
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, -2003292412, 0x65Bu, 0);
    v164 = v469;
    v163 = *(__m128 *)v468;
    v166 = *(__m128 *)&v470[16];
    v165 = *(__m128 *)v470;
    goto LABEL_310;
  }
  CVisual::EnsureWorldTransform((CVisual *)v7, a2, (struct CTreeData *)v160);
  if ( !v160[14].m128_u64[0] )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xD0,
      (unsigned int)"onecoreuap\\windows\\dwm\\dwmcore\\engine\\treedata.cpp",
      v162);
  v163 = v160[17];
  *(__m128 *)v468 = v163;
  v164 = v160[18];
  v469 = v164;
  v165 = v160[19];
  *(__m128 *)v470 = v165;
  v166 = v160[20];
  *(__m128 *)&v470[16] = v166;
  *(_DWORD *)&v470[32] = v160[21].m128_i32[0];
  v167 = v160->m128_i8[11];
  if ( v159 )
  {
    v168 = v160[16].m128_u64[0];
    if ( v168 )
    {
      *(_OWORD *)v159 = *(_OWORD *)v168;
      *((_OWORD *)v159 + 1) = *(_OWORD *)(v168 + 16);
      *((_OWORD *)v159 + 2) = *(_OWORD *)(v168 + 32);
      *((_OWORD *)v159 + 3) = *(_OWORD *)(v168 + 48);
      v169 = *(_DWORD *)(v168 + 64);
    }
    else
    {
      *(__m128 *)v159 = v160[17];
      *((__m128 *)v159 + 1) = v160[18];
      *((__m128 *)v159 + 2) = v160[19];
      *((__m128 *)v159 + 3) = v160[20];
      v169 = v160[21].m128_i32[0];
    }
    *((_DWORD *)v159 + 16) = v169;
    v163 = *(__m128 *)v468;
    v164 = v469;
    v165 = *(__m128 *)v470;
    v166 = *(__m128 *)&v470[16];
  }
  if ( !v167 )
  {
LABEL_310:
    if ( v7 != *((_QWORD *)v5 + 994) )
    {
      if ( !*((_BYTE *)v5 + 8064) )
        CDrawingContext::GetWorldTransform(v5, (struct CMILMatrix *)v468);
      goto LABEL_313;
    }
  }
  if ( *((_BYTE *)v5 + 8064) )
    goto LABEL_406;
  v205 = v470[32];
  if ( (char)(v470[32] << 6) >> 6 == 1 )
  {
    v206 = v470[33];
    v207 = FLOAT_61440_0;
    v208 = FLOAT_0_000081380211;
    *(_DWORD *)&v470[24] = _mm_shuffle_ps(v166, v166, 170).m128_u32[0];
    *(_DWORD *)&v470[20] = _mm_shuffle_ps(v166, v166, 85).m128_u32[0];
    *(_DWORD *)&v470[8] = _mm_shuffle_ps(v165, v165, 170).m128_u32[0];
    *(_DWORD *)&v470[4] = _mm_shuffle_ps(v165, v165, 85).m128_u32[0];
    v469.m128_i32[2] = _mm_shuffle_ps(v164, v164, 170).m128_u32[0];
    v469.m128_i32[1] = _mm_shuffle_ps(v164, v164, 85).m128_u32[0];
    LODWORD(v468[1]) = _mm_shuffle_ps(v163, v163, 170).m128_u32[0];
    HIDWORD(v468[0]) = _mm_shuffle_ps(v163, v163, 85).m128_u32[0];
    *(_DWORD *)&v470[16] = v166.m128_i32[0];
    *(_DWORD *)v470 = v165.m128_i32[0];
    v469.m128_i32[0] = v164.m128_i32[0];
    LODWORD(v468[0]) = v163.m128_i32[0];
    LODWORD(v209) = _mm_shuffle_ps(v166, v166, 255).m128_u32[0];
    LODWORD(v210) = _mm_shuffle_ps(v165, v165, 255).m128_u32[0];
    LODWORD(v211) = _mm_shuffle_ps(v164, v164, 255).m128_u32[0];
    LODWORD(v212) = _mm_shuffle_ps(v163, v163, 255).m128_u32[0];
  }
  else
  {
    if ( (char)(v470[32] << 6) >> 6 < 0 )
      goto LABEL_405;
    v206 = v470[33];
    v207 = FLOAT_61440_0;
    v208 = FLOAT_0_000081380211;
    *(_DWORD *)&v470[24] = _mm_shuffle_ps(v166, v166, 170).m128_u32[0];
    *(_DWORD *)&v470[8] = _mm_shuffle_ps(v165, v165, 170).m128_u32[0];
    *(_DWORD *)&v470[20] = _mm_shuffle_ps(v166, v166, 85).m128_u32[0];
    HIDWORD(v468[0]) = _mm_shuffle_ps(v163, v163, 85).m128_u32[0];
    v469.m128_i32[2] = _mm_shuffle_ps(v164, v164, 170).m128_u32[0];
    v469.m128_i32[1] = _mm_shuffle_ps(v164, v164, 85).m128_u32[0];
    *(_DWORD *)&v470[4] = _mm_shuffle_ps(v165, v165, 85).m128_u32[0];
    *(_DWORD *)&v470[16] = v166.m128_i32[0];
    v469.m128_i32[0] = v164.m128_i32[0];
    LODWORD(v468[0]) = v163.m128_i32[0];
    LODWORD(v468[1]) = _mm_shuffle_ps(v163, v163, 170).m128_u32[0];
    *(_DWORD *)v470 = v165.m128_i32[0];
    LODWORD(v209) = _mm_shuffle_ps(v166, v166, 255).m128_u32[0];
    LODWORD(v210) = _mm_shuffle_ps(v165, v165, 255).m128_u32[0];
    LODWORD(v211) = _mm_shuffle_ps(v164, v164, 255).m128_u32[0];
    LODWORD(v212) = _mm_shuffle_ps(v163, v163, 255).m128_u32[0];
    if ( (char)(16 * v470[33]) >> 6 == 1 )
      goto LABEL_403;
    if ( (char)(16 * v470[33]) >> 6 >= 0 )
    {
      if ( (char)(4 * v470[33]) >> 6 == 1
        || ((char)(4 * v470[33]) >> 6 >= 0
          ? (COERCE_FLOAT(
               COERCE_UNSIGNED_INT(
                 (float)((float)((float)(COERCE_FLOAT(LODWORD(v211) & v155) * 61440.0)
                               + (float)(COERCE_FLOAT(LODWORD(v212) & v155) * 61440.0))
                       + COERCE_FLOAT(LODWORD(v209) & v155))
               - 1.0)
             & v155) >= 0.000081380211
           ? (v401 = 1, v402 = 0)
           : (v401 = -1, v402 = 1),
             LOBYTE(v206) = v470[33] & 0xCF | (16 * (v401 & 3)),
             v353 = v402
                  & (COERCE_FLOAT(COERCE_UNSIGNED_INT((float)(COERCE_FLOAT(LODWORD(v210) & v155) * 61440.0) - 0.0) & v155) < 0.000081380211))
          : (v353 = COERCE_FLOAT(COERCE_UNSIGNED_INT((float)(COERCE_FLOAT(LODWORD(v210) & v155) * 61440.0) - 0.0) & v155) < 0.000081380211),
            !v353
         || COERCE_FLOAT(COERCE_UNSIGNED_INT(*(float *)v470 - 0.0) & v155) >= 0.000081380211
         || COERCE_FLOAT(COERCE_UNSIGNED_INT(*(float *)&v470[4] - 0.0) & v155) >= 0.000081380211) )
      {
        v354 = 0;
        v355 = 1;
      }
      else
      {
        v354 = 1;
        v355 = -1;
      }
      v356 = 4 * (v355 & 3);
      v357 = v206 & 0xF3;
      v206 = v356;
      LOBYTE(v206) = v357 | v356;
      v470[33] = v357 | v356;
      if ( !v354 )
        goto LABEL_403;
    }
    if ( (char)(16 * v470[32]) >> 6 == 1 )
      goto LABEL_403;
    if ( (char)(16 * v470[32]) >> 6 >= 0 )
    {
      if ( (char)(4 * v206) >> 6 == 1 )
        goto LABEL_821;
      if ( (char)(4 * v206) >> 6 >= 0 )
      {
        if ( COERCE_FLOAT(
               COERCE_UNSIGNED_INT(
                 (float)((float)((float)(COERCE_FLOAT(LODWORD(v211) & v155) * 61440.0)
                               + (float)(COERCE_FLOAT(LODWORD(v212) & v155) * 61440.0))
                       + COERCE_FLOAT(LODWORD(v209) & v155))
               - 1.0)
             & v155) < 0.000081380211 )
        {
          v370 = -1;
          v371 = 1;
        }
        else
        {
          v370 = 1;
          v371 = 0;
        }
        v383 = 16 * (v370 & 3);
        v384 = v206 & 0xCF;
        v206 = v383;
        LOBYTE(v206) = v384 | v383;
        v470[33] = v384 | v383;
        if ( !v371 )
          goto LABEL_821;
      }
      if ( COERCE_FLOAT(COERCE_UNSIGNED_INT(*(float *)&v468[1] - 0.0) & v155) >= 0.000081380211
        || COERCE_FLOAT(COERCE_UNSIGNED_INT(v469.m128_f32[2] - 0.0) & v155) >= 0.000081380211 )
      {
LABEL_821:
        v385 = 0;
        v386 = 1;
      }
      else
      {
        v385 = 1;
        v386 = -1;
      }
      v205 = v470[32] & 0xF3 | (4 * (v386 & 3));
      if ( !v385 )
        goto LABEL_403;
    }
    if ( (char)(4 * v205) >> 6 == 1 )
      goto LABEL_403;
    if ( (char)(4 * v205) >> 6 >= 0 )
    {
      if ( v205 >> 6 == 1 )
        goto LABEL_612;
      if ( v205 >> 6 >= 0 )
      {
        if ( (char)(4 * v206) >> 6 == 1 )
          goto LABEL_849;
        if ( (char)(4 * v206) >> 6 >= 0 )
        {
          if ( COERCE_FLOAT(
                 COERCE_UNSIGNED_INT(
                   (float)((float)((float)(COERCE_FLOAT(LODWORD(v211) & v155) * 61440.0)
                                 + (float)(COERCE_FLOAT(LODWORD(v212) & v155) * 61440.0))
                         + COERCE_FLOAT(LODWORD(v209) & v155))
                 - 1.0)
               & v155) < 0.000081380211 )
          {
            v376 = -1;
            v377 = 1;
          }
          else
          {
            v376 = 1;
            v377 = 0;
          }
          v392 = 16 * (v376 & 3);
          v393 = v206 & 0xCF;
          v206 = v392;
          LOBYTE(v206) = v393 | v392;
          v470[33] = v393 | v392;
          if ( !v377 )
            goto LABEL_849;
        }
        if ( COERCE_FLOAT(COERCE_UNSIGNED_INT(*((float *)v468 + 1) - 0.0) & v155) >= 0.000081380211
          || COERCE_FLOAT(COERCE_UNSIGNED_INT(v469.m128_f32[0] - 0.0) & v155) >= 0.000081380211 )
        {
LABEL_849:
          v394 = 0;
          v395 = 1;
        }
        else
        {
          v394 = 1;
          v395 = -1;
        }
        v205 = v205 & 0x3F | (v395 << 6);
        if ( !v394 )
          goto LABEL_612;
      }
      if ( COERCE_FLOAT(COERCE_UNSIGNED_INT(*(float *)v468 - 1.0) & v155) >= 0.000081380211
        || COERCE_FLOAT(COERCE_UNSIGNED_INT(v469.m128_f32[1] - 1.0) & v155) >= 0.000081380211 )
      {
LABEL_612:
        v303 = 0;
        v304 = 1;
      }
      else
      {
        v303 = 1;
        v304 = -1;
      }
      v205 = v205 & 0xCF | (16 * (v304 & 3));
      if ( !v303 )
        goto LABEL_403;
    }
    if ( COERCE_FLOAT(COERCE_UNSIGNED_INT(*(float *)&v470[8] - 1.0) & v155) >= 0.000081380211
      || COERCE_FLOAT(COERCE_UNSIGNED_INT(*(float *)&v470[16] - 0.0) & v155) >= 0.000081380211
      || COERCE_FLOAT(COERCE_UNSIGNED_INT(*(float *)&v470[20] - 0.0) & v155) >= 0.000081380211
      || COERCE_FLOAT(COERCE_UNSIGNED_INT(*(float *)&v470[24] - 0.0) & v155) >= 0.000081380211 )
    {
LABEL_403:
      v213 = 0;
      v214 = 1;
    }
    else
    {
      v213 = 1;
      v214 = -1;
    }
    LOBYTE(v161) = v214 & 3;
    v205 = v205 & 0xFC | v161;
    v470[32] = v205;
    if ( v213 )
    {
LABEL_405:
      *(_OWORD *)v468 = *(_OWORD *)((char *)v5 + 88);
      v469 = *(__m128 *)((char *)v5 + 104);
      *(_OWORD *)v470 = *(_OWORD *)((char *)v5 + 120);
      *(_OWORD *)&v470[16] = *(_OWORD *)((char *)v5 + 136);
      *(_DWORD *)&v470[32] = *((_DWORD *)v5 + 38);
      goto LABEL_406;
    }
  }
  if ( (char)(*((_BYTE *)v5 + 152) << 6) >> 6 != 1 )
  {
    if ( (char)(*((_BYTE *)v5 + 152) << 6) >> 6 >= 0 )
    {
      v235 = *((_BYTE *)v5 + 153);
      if ( (char)(16 * v235) >> 6 == 1 )
        goto LABEL_469;
      if ( (char)(16 * v235) >> 6 >= 0 )
      {
        if ( (char)(4 * v235) >> 6 == 1
          || ((char)(4 * v235) >> 6 >= 0
            ? (v208 <= COERCE_FLOAT(
                         COERCE_UNSIGNED_INT(
                           (float)((float)((float)(COERCE_FLOAT(*((_DWORD *)v5 + 29) & v155) * v207)
                                         + (float)(COERCE_FLOAT(*((_DWORD *)v5 + 25) & v155) * v207))
                                 + COERCE_FLOAT(*((_DWORD *)v5 + 37) & v155))
                         - 1.0)
                       & v155)
             ? (v426 = 1, LOBYTE(v161) = 0)
             : (v426 = -1, LOBYTE(v161) = 1),
               *((_BYTE *)v5 + 153) = (16 * v426) ^ (v235 ^ (16 * v426)) & 0xCF,
               v381 = v161
                    & (v208 > COERCE_FLOAT(
                                COERCE_UNSIGNED_INT((float)(COERCE_FLOAT(*((_DWORD *)v5 + 33) & v155) * v207) - 0.0)
                              & v155)))
            : (v381 = v208 > COERCE_FLOAT(
                               COERCE_UNSIGNED_INT((float)(COERCE_FLOAT(*((_DWORD *)v5 + 33) & v155) * v207) - 0.0)
                             & v155)),
              !v381
           || v208 <= COERCE_FLOAT(COERCE_UNSIGNED_INT(*((float *)v5 + 30) - 0.0) & v155)
           || v208 <= COERCE_FLOAT(COERCE_UNSIGNED_INT(*((float *)v5 + 31) - 0.0) & v155)) )
        {
          LOBYTE(v206) = 0;
          v382 = 1;
        }
        else
        {
          LOBYTE(v206) = 1;
          v382 = -1;
        }
        *((_BYTE *)v5 + 153) = (4 * v382) ^ (*((_BYTE *)v5 + 153) ^ (4 * v382)) & 0xF3;
        if ( !(_BYTE)v206 )
          goto LABEL_469;
      }
      if ( (char)(16 * *((_BYTE *)v5 + 152)) >> 6 == 1 )
        goto LABEL_469;
      if ( (char)(16 * *((_BYTE *)v5 + 152)) >> 6 >= 0 )
      {
        if ( (v398 = *((_BYTE *)v5 + 153), (char)(4 * v398) >> 6 == 1)
          || (char)(4 * v398) >> 6 >= 0
          && (v208 > COERCE_FLOAT(
                       COERCE_UNSIGNED_INT(
                         (float)((float)((float)(COERCE_FLOAT(*((_DWORD *)v5 + 29) & v155) * v207)
                                       + (float)(COERCE_FLOAT(*((_DWORD *)v5 + 25) & v155) * v207))
                               + COERCE_FLOAT(*((_DWORD *)v5 + 37) & v155))
                       - 1.0)
                     & v155)
            ? (v399 = -1, v400 = 1)
            : (v399 = 1, v400 = 0),
              *((_BYTE *)v5 + 153) = (16 * v399) ^ ((16 * v399) ^ v398) & 0xCF,
              !v400)
          || v208 <= COERCE_FLOAT(COERCE_UNSIGNED_INT(*((float *)v5 + 24) - 0.0) & v155)
          || v208 <= COERCE_FLOAT(COERCE_UNSIGNED_INT(*((float *)v5 + 28) - 0.0) & v155) )
        {
          LOBYTE(v206) = 0;
          v416 = 1;
        }
        else
        {
          LOBYTE(v206) = 1;
          v416 = -1;
        }
        *((_BYTE *)v5 + 152) = (4 * v416) ^ (*((_BYTE *)v5 + 152) ^ (4 * v416)) & 0xF3;
        if ( !(_BYTE)v206 )
          goto LABEL_469;
      }
      if ( (char)(4 * *((_BYTE *)v5 + 152)) >> 6 == 1
        || (char)(4 * *((_BYTE *)v5 + 152)) >> 6 >= 0
        && (!(unsigned __int8)CMILMatrix::IsTranslateAndScaleIgnoreZ<1>((char *)v5 + 88, v206, v161, v162)
         || v208 <= COERCE_FLOAT(COERCE_UNSIGNED_INT(*((float *)v5 + 22) - 1.0) & v155)
         || v208 <= COERCE_FLOAT(COERCE_UNSIGNED_INT(*((float *)v5 + 27) - 1.0) & v155)
          ? (v351 = 0, v352 = 1)
          : (v351 = 1, v352 = -1),
            *((_BYTE *)v5 + 152) = (16 * v352) ^ (*((_BYTE *)v5 + 152) ^ (16 * v352)) & 0xCF,
            !v351)
        || v208 <= COERCE_FLOAT(COERCE_UNSIGNED_INT(*((float *)v5 + 32) - 1.0) & v155)
        || v208 <= COERCE_FLOAT(COERCE_UNSIGNED_INT(*((float *)v5 + 34) - 0.0) & v155)
        || v208 <= COERCE_FLOAT(COERCE_UNSIGNED_INT(*((float *)v5 + 35) - 0.0) & v155)
        || v208 <= COERCE_FLOAT(COERCE_UNSIGNED_INT(*((float *)v5 + 36) - 0.0) & v155) )
      {
LABEL_469:
        v236 = 0;
        v237 = 1;
      }
      else
      {
        v236 = 1;
        v237 = -1;
      }
      *((_BYTE *)v5 + 152) = v237 ^ (*((_BYTE *)v5 + 152) ^ v237) & 0xFC;
      if ( !v236 )
      {
        v206 = v470[33];
        v205 = v470[32];
        v209 = *(float *)&v470[28];
        v166 = *(__m128 *)&v470[16];
        v210 = *(float *)&v470[12];
        v165 = *(__m128 *)v470;
        v211 = v469.m128_f32[3];
        v164 = v469;
        v212 = *((float *)&v468[1] + 1);
        v163 = *(__m128 *)v468;
        goto LABEL_472;
      }
    }
    goto LABEL_406;
  }
LABEL_472:
  v238 = *((unsigned __int8 *)v5 + 153);
  if ( (char)(16 * v238) >> 6 != 1 )
  {
    if ( (char)(16 * v238) >> 6 < 0 )
      goto LABEL_474;
    if ( (char)(4 * v238) >> 6 == 1
      || ((char)(4 * v238) >> 6 >= 0
        ? (v208 <= COERCE_FLOAT(
                     COERCE_UNSIGNED_INT(
                       (float)((float)((float)(COERCE_FLOAT(*((_DWORD *)v5 + 29) & v155) * v207)
                                     + (float)(COERCE_FLOAT(*((_DWORD *)v5 + 25) & v155) * v207))
                             + COERCE_FLOAT(*((_DWORD *)v5 + 37) & v155))
                     - 1.0)
                   & v155)
         ? (v413 = 1, v414 = 0)
         : (v413 = -1, v414 = 1),
           *((_BYTE *)v5 + 153) = (16 * v413) ^ (v238 ^ (16 * v413)) & 0xCF,
           v359 = v414
                & (v208 > COERCE_FLOAT(COERCE_UNSIGNED_INT((float)(COERCE_FLOAT(*((_DWORD *)v5 + 33) & v155) * v207) - 0.0) & v155)))
        : (v359 = v208 > COERCE_FLOAT(COERCE_UNSIGNED_INT((float)(COERCE_FLOAT(*((_DWORD *)v5 + 33) & v155) * v207) - 0.0) & v155)),
          !v359
       || v208 <= COERCE_FLOAT(COERCE_UNSIGNED_INT(*((float *)v5 + 30) - 0.0) & v155)
       || v208 <= COERCE_FLOAT(COERCE_UNSIGNED_INT(*((float *)v5 + 31) - 0.0) & v155)) )
    {
      v243 = 0;
      v244 = 1;
    }
    else
    {
      v243 = 1;
      v244 = -1;
    }
    *((_BYTE *)v5 + 153) = (4 * v244) ^ (*((_BYTE *)v5 + 153) ^ (4 * v244)) & 0xF3;
    if ( v243 )
    {
      v206 = v470[33];
      v205 = v470[32];
      v209 = *(float *)&v470[28];
      v166 = *(__m128 *)&v470[16];
      v210 = *(float *)&v470[12];
      v165 = *(__m128 *)v470;
      v211 = v469.m128_f32[3];
      v164 = v469;
      v212 = *((float *)&v468[1] + 1);
      v163 = *(__m128 *)v468;
LABEL_474:
      if ( (char)(16 * *((_BYTE *)v5 + 152)) >> 6 != 1 )
      {
        if ( (char)(16 * *((_BYTE *)v5 + 152)) >> 6 >= 0 )
        {
          v373 = *((_BYTE *)v5 + 153);
          if ( (char)(4 * v373) >> 6 == 1
            || (char)(4 * v373) >> 6 >= 0
            && (v208 > COERCE_FLOAT(
                         COERCE_UNSIGNED_INT(
                           (float)((float)((float)(COERCE_FLOAT(*((_DWORD *)v5 + 29) & v155) * v207)
                                         + (float)(COERCE_FLOAT(*((_DWORD *)v5 + 25) & v155) * v207))
                                 + COERCE_FLOAT(*((_DWORD *)v5 + 37) & v155))
                         - 1.0)
                       & v155)
              ? (v374 = -1, v375 = 1)
              : (v374 = 1, v375 = 0),
                *((_BYTE *)v5 + 153) = (16 * v374) ^ ((16 * v374) ^ v373) & 0xCF,
                !v375)
            || v208 <= COERCE_FLOAT(COERCE_UNSIGNED_INT(*((float *)v5 + 24) - 0.0) & v155)
            || v208 <= COERCE_FLOAT(COERCE_UNSIGNED_INT(*((float *)v5 + 28) - 0.0) & v155) )
          {
            v390 = 0;
            v391 = 1;
          }
          else
          {
            v390 = 1;
            v391 = -1;
          }
          *((_BYTE *)v5 + 152) = (4 * v391) ^ (*((_BYTE *)v5 + 152) ^ (4 * v391)) & 0xF3;
          if ( !v390 )
            goto LABEL_490;
          v206 = v470[33];
          v205 = v470[32];
          v209 = *(float *)&v470[28];
          v166 = *(__m128 *)&v470[16];
          v210 = *(float *)&v470[12];
          v165 = *(__m128 *)v470;
          v211 = v469.m128_f32[3];
          v164 = v469;
          v212 = *((float *)&v468[1] + 1);
          v163 = *(__m128 *)v468;
        }
        if ( (char)(4 * *((_BYTE *)v5 + 152)) >> 6 != 1 )
        {
          if ( (char)(4 * *((_BYTE *)v5 + 152)) >> 6 >= 0 )
          {
            if ( (unsigned __int8)CMILMatrix::IsTranslateAndScaleIgnoreZ<1>((char *)v5 + 88, v206, v238, v162)
              && v208 > COERCE_FLOAT(COERCE_UNSIGNED_INT(*((float *)v5 + 22) - 1.0) & v155)
              && v208 > COERCE_FLOAT(COERCE_UNSIGNED_INT(*((float *)v5 + 27) - 1.0) & v155) )
            {
              v318 = 1;
              v319 = -1;
            }
            else
            {
              v318 = 0;
              v319 = 1;
            }
            *((_BYTE *)v5 + 152) = (16 * v319) ^ (*((_BYTE *)v5 + 152) ^ (16 * v319)) & 0xCF;
            if ( !v318 )
              goto LABEL_490;
            v206 = v470[33];
            v205 = v470[32];
            v209 = *(float *)&v470[28];
            v166 = *(__m128 *)&v470[16];
            v210 = *(float *)&v470[12];
            v165 = *(__m128 *)v470;
            v211 = v469.m128_f32[3];
            v164 = v469;
            v212 = *((float *)&v468[1] + 1);
            v163 = *(__m128 *)v468;
          }
          if ( v208 > COERCE_FLOAT(COERCE_UNSIGNED_INT(*((float *)v5 + 32) - 1.0) & v155) )
          {
            v239 = *((float *)v5 + 34);
            v240 = *((float *)v5 + 36);
            v241 = *((float *)v5 + 35);
            if ( v208 <= COERCE_FLOAT(LODWORD(v239) & v155)
              || v208 <= COERCE_FLOAT(LODWORD(v241) & v155)
              || v208 <= COERCE_FLOAT(LODWORD(v240) & v155) )
            {
              if ( (char)(4 * v206) >> 6 == 1
                || ((char)(4 * v206) >> 6 >= 0
                  ? (v208 <= COERCE_FLOAT(
                               COERCE_UNSIGNED_INT(
                                 (float)((float)((float)(COERCE_FLOAT(LODWORD(v211) & v155) * v207)
                                               + (float)(COERCE_FLOAT(LODWORD(v212) & v155) * v207))
                                       + COERCE_FLOAT(LODWORD(v209) & v155))
                               - 1.0)
                             & v155)
                   ? (v295 = 1, LOBYTE(v162) = 0)
                   : (v295 = -1, LOBYTE(v162) = 1),
                     LOBYTE(v206) = v206 & 0xCF | (16 * (v295 & 3)),
                     v470[33] = v206,
                     v242 = (unsigned __int8)v162
                          & (v208 > COERCE_FLOAT(
                                      COERCE_UNSIGNED_INT((float)(COERCE_FLOAT(LODWORD(v210) & v155) * v207) - 0.0)
                                    & v155)))
                  : (v242 = v208 > COERCE_FLOAT(
                                     COERCE_UNSIGNED_INT((float)(COERCE_FLOAT(LODWORD(v210) & v155) * v207) - 0.0)
                                   & v155)),
                    !v242) )
              {
                v470[33] = v206 & 0xF3;
                *(float *)v468 = *(float *)v468 + (float)(v239 * v212);
                *((float *)v468 + 1) = *((float *)v468 + 1) + (float)(v241 * v212);
                *(float *)&v468[1] = *(float *)&v468[1] + (float)(v240 * v212);
                v469.m128_f32[0] = v469.m128_f32[0] + (float)(v239 * v211);
                v469.m128_f32[1] = v469.m128_f32[1] + (float)(v241 * v211);
                v469.m128_f32[2] = v469.m128_f32[2] + (float)(v240 * v211);
                *(float *)v470 = *(float *)v470 + (float)(v239 * v210);
                v332 = v240 * v210;
                v240 = v240 * v209;
                *(float *)&v470[4] = *(float *)&v470[4] + (float)(v241 * v210);
                *(float *)&v470[8] = *(float *)&v470[8] + v332;
                *(float *)&v470[16] = *(float *)&v470[16] + (float)(v239 * v209);
                *(float *)&v470[20] = *(float *)&v470[20] + (float)(v241 * v209);
              }
              else
              {
                *(float *)&v470[16] = *(float *)&v470[16] + v239;
                *(float *)&v470[20] = *(float *)&v470[20] + v241;
              }
              v470[32] = v205 & 0xFC;
              *(float *)&v470[24] = *(float *)&v470[24] + v240;
            }
            goto LABEL_406;
          }
        }
      }
    }
    else
    {
LABEL_490:
      v206 = v470[33];
      v205 = v470[32];
      v209 = *(float *)&v470[28];
      v166 = *(__m128 *)&v470[16];
      v210 = *(float *)&v470[12];
      v165 = *(__m128 *)v470;
      v211 = v469.m128_f32[3];
      v164 = v469;
      v212 = *((float *)&v468[1] + 1);
      v163 = *(__m128 *)v468;
    }
  }
  if ( (char)(16 * v206) >> 6 != 1 )
  {
    if ( (char)(16 * v206) >> 6 < 0 )
      goto LABEL_1021;
    if ( (char)(4 * v206) >> 6 == 1
      || ((char)(4 * v206) >> 6 >= 0
        ? (v208 <= COERCE_FLOAT(
                     COERCE_UNSIGNED_INT(
                       (float)((float)((float)(COERCE_FLOAT(LODWORD(v211) & v155) * v207)
                                     + (float)(COERCE_FLOAT(LODWORD(v212) & v155) * v207))
                             + COERCE_FLOAT(LODWORD(v209) & v155))
                     - 1.0)
                   & v155)
         ? (v424 = 1, v425 = 0)
         : (v424 = -1, v425 = 1),
           LOBYTE(v206) = v206 & 0xCF | (16 * (v424 & 3)),
           v372 = v425
                & (v208 > COERCE_FLOAT(COERCE_UNSIGNED_INT((float)(COERCE_FLOAT(LODWORD(v210) & v155) * v207) - 0.0) & v155)))
        : (v372 = v208 > COERCE_FLOAT(COERCE_UNSIGNED_INT((float)(COERCE_FLOAT(LODWORD(v210) & v155) * v207) - 0.0) & v155)),
          !v372
       || v208 <= COERCE_FLOAT(COERCE_UNSIGNED_INT(*(float *)v470 - 0.0) & v155)
       || v208 <= COERCE_FLOAT(COERCE_UNSIGNED_INT(*(float *)&v470[4] - 0.0) & v155)) )
    {
      v255 = 0;
      v256 = 1;
    }
    else
    {
      v255 = 1;
      v256 = -1;
    }
    LOBYTE(v238) = 4 * (v256 & 3);
    v257 = v206 & 0xF3;
    v206 = (unsigned __int8)v238;
    LOBYTE(v206) = v257 | v238;
    v470[33] = v257 | v238;
    if ( v255 )
    {
LABEL_1021:
      if ( (char)(16 * v205) >> 6 != 1 )
      {
        if ( (char)(16 * v205) >> 6 < 0 )
          goto LABEL_1022;
        if ( (char)(4 * v206) >> 6 == 1 )
          goto LABEL_878;
        if ( (char)(4 * v206) >> 6 >= 0 )
        {
          if ( v208 > COERCE_FLOAT(
                        COERCE_UNSIGNED_INT(
                          (float)((float)((float)(COERCE_FLOAT(LODWORD(v211) & v155) * v207)
                                        + (float)(COERCE_FLOAT(LODWORD(v212) & v155) * v207))
                                + COERCE_FLOAT(LODWORD(v209) & v155))
                        - 1.0)
                      & v155) )
          {
            v396 = -1;
            v397 = 1;
          }
          else
          {
            v396 = 1;
            v397 = 0;
          }
          v406 = 16 * (v396 & 3);
          v407 = v206 & 0xCF;
          v206 = v406;
          LOBYTE(v206) = v407 | v406;
          v470[33] = v407 | v406;
          if ( !v397 )
            goto LABEL_878;
        }
        if ( v208 <= COERCE_FLOAT(COERCE_UNSIGNED_INT(*(float *)&v468[1] - 0.0) & v155)
          || v208 <= COERCE_FLOAT(COERCE_UNSIGNED_INT(v469.m128_f32[2] - 0.0) & v155) )
        {
LABEL_878:
          v408 = 0;
          v409 = 1;
        }
        else
        {
          v408 = 1;
          v409 = -1;
        }
        LOBYTE(v238) = 4 * (v409 & 3);
        v205 = v205 & 0xF3 | v238;
        v470[32] = v205;
        if ( v408 )
        {
LABEL_1022:
          if ( (char)(4 * v205) >> 6 != 1 )
          {
            if ( (char)(4 * v205) >> 6 < 0 )
              goto LABEL_497;
            if ( (unsigned __int8)CMILMatrix::IsTranslateAndScaleIgnoreZ<1>(v468, v206, v238, v162)
              && v208 > COERCE_FLOAT(COERCE_UNSIGNED_INT(*(float *)v468 - 1.0) & v155)
              && v208 > COERCE_FLOAT(COERCE_UNSIGNED_INT(v469.m128_f32[1] - 1.0) & v155) )
            {
              v348 = 1;
              v349 = -1;
            }
            else
            {
              v348 = 0;
              v349 = 1;
            }
            v209 = *(float *)&v470[28];
            v166 = *(__m128 *)&v470[16];
            v210 = *(float *)&v470[12];
            v205 = v470[32] & 0xCF | (16 * (v349 & 3));
            v165 = *(__m128 *)v470;
            v9 = v348 == 0;
            LOBYTE(v206) = v470[33];
            v211 = v469.m128_f32[3];
            v164 = v469;
            v470[32] = v205;
            v212 = *((float *)&v468[1] + 1);
            v163 = *(__m128 *)v468;
            if ( !v9 )
            {
LABEL_497:
              if ( v208 > COERCE_FLOAT(COERCE_UNSIGNED_INT(*(float *)&v470[8] - 1.0) & v155) )
              {
                v245 = *(__m128 *)((char *)v5 + 88);
                v246 = *(float *)&v470[16];
                v247 = *(float *)&v470[20];
                v248 = *(float *)&v470[24];
                *(__m128 *)v468 = v245;
                v249 = *(__m128 *)((char *)v5 + 104);
                v469 = v249;
                v250 = *(__m128 *)((char *)v5 + 120);
                *(__m128 *)v470 = v250;
                *(_OWORD *)&v470[16] = *(_OWORD *)((char *)v5 + 136);
                *(_DWORD *)&v470[32] = *((_DWORD *)v5 + 38);
                if ( v208 <= COERCE_FLOAT(LODWORD(v246) & v155)
                  || v208 <= COERCE_FLOAT(LODWORD(v247) & v155)
                  || v208 <= COERCE_FLOAT(LODWORD(v248) & v155) )
                {
                  *(float *)&v470[16] = *(float *)&v470[16]
                                      + (float)((float)((float)(v245.m128_f32[0] * v246)
                                                      + (float)(v249.m128_f32[0] * v247))
                                              + (float)(v250.m128_f32[0] * v248));
                  *(float *)&v470[20] = *(float *)&v470[20]
                                      + (float)((float)((float)(_mm_shuffle_ps(v245, v245, 85).m128_f32[0] * v246)
                                                      + (float)(_mm_shuffle_ps(v249, v249, 85).m128_f32[0] * v247))
                                              + (float)(_mm_shuffle_ps(v250, v250, 85).m128_f32[0] * v248));
                  *(float *)&v470[24] = *(float *)&v470[24]
                                      + (float)((float)((float)(_mm_shuffle_ps(v245, v245, 170).m128_f32[0] * v246)
                                                      + (float)(_mm_shuffle_ps(v249, v249, 170).m128_f32[0] * v247))
                                              + (float)(_mm_shuffle_ps(v250, v250, 170).m128_f32[0] * v248));
                  if ( (char)(4 * v470[33]) >> 6 == 1 )
                  {
                    v251 = *(float *)&v470[12];
                  }
                  else
                  {
                    if ( (char)(4 * v470[33]) >> 6 >= 0 )
                    {
                      if ( v208 <= COERCE_FLOAT(
                                     COERCE_UNSIGNED_INT(
                                       (float)((float)((float)(COERCE_FLOAT(v469.m128_i32[3] & v155) * v207)
                                                     + (float)(COERCE_FLOAT(HIDWORD(v468[1]) & v155) * v207))
                                             + COERCE_FLOAT(*(_DWORD *)&v470[28] & v155))
                                     - 1.0)
                                   & v155) )
                      {
                        v320 = 1;
                        v321 = 0;
                      }
                      else
                      {
                        v320 = -1;
                        v321 = 1;
                      }
                      v470[33] = v470[33] & 0xCF | (16 * (v320 & 3));
                      LODWORD(v251) = _mm_shuffle_ps(v250, v250, 255).m128_u32[0];
                      v252 = v321
                           & (v208 > COERCE_FLOAT(
                                       COERCE_UNSIGNED_INT((float)(COERCE_FLOAT(LODWORD(v251) & v155) * v207) - 0.0)
                                     & v155));
                    }
                    else
                    {
                      v251 = _mm_shuffle_ps(v250, v250, 255).m128_f32[0];
                      v252 = v208 > COERCE_FLOAT(
                                      COERCE_UNSIGNED_INT((float)(COERCE_FLOAT(LODWORD(v251) & v155) * v207) - 0.0)
                                    & v155);
                    }
                    if ( v252 )
                    {
                      v470[32] &= 0xFCu;
                      goto LABEL_406;
                    }
                  }
                  *(_DWORD *)&v470[32] = 0;
                  *(float *)&v470[28] = *(float *)&v470[28]
                                      + (float)((float)((float)(*((float *)&v468[1] + 1) * v246)
                                                      + (float)(v469.m128_f32[3] * v247))
                                              + (float)(v251 * v248));
                }
                goto LABEL_406;
              }
            }
          }
        }
      }
    }
  }
  v258 = *((_BYTE *)v5 + 153);
  if ( (char)(16 * v258) >> 6 != 1 )
  {
    if ( (char)(16 * v258) >> 6 < 0 )
      goto LABEL_523;
    if ( (char)(4 * v258) >> 6 == 1
      || ((char)(4 * v258) >> 6 >= 0
        ? (v208 <= COERCE_FLOAT(
                     COERCE_UNSIGNED_INT(
                       (float)((float)((float)(COERCE_FLOAT(*((_DWORD *)v5 + 29) & v155) * v207)
                                     + (float)(COERCE_FLOAT(*((_DWORD *)v5 + 25) & v155) * v207))
                             + COERCE_FLOAT(*((_DWORD *)v5 + 37) & v155))
                     - 1.0)
                   & v155)
         ? (v427 = 1, v428 = 0)
         : (v427 = -1, v428 = 1),
           *((_BYTE *)v5 + 153) = (16 * v427) ^ (v258 ^ (16 * v427)) & 0xCF,
           v387 = v428
                & (v208 > COERCE_FLOAT(COERCE_UNSIGNED_INT((float)(COERCE_FLOAT(*((_DWORD *)v5 + 33) & v155) * v207) - 0.0) & v155)))
        : (v387 = v208 > COERCE_FLOAT(COERCE_UNSIGNED_INT((float)(COERCE_FLOAT(*((_DWORD *)v5 + 33) & v155) * v207) - 0.0) & v155)),
          !v387
       || v208 <= COERCE_FLOAT(COERCE_UNSIGNED_INT(*((float *)v5 + 30) - 0.0) & v155)
       || v208 <= COERCE_FLOAT(COERCE_UNSIGNED_INT(*((float *)v5 + 31) - 0.0) & v155)) )
    {
      v388 = 0;
      v389 = 1;
    }
    else
    {
      v388 = 1;
      v389 = -1;
    }
    *((_BYTE *)v5 + 153) = (4 * v389) ^ (*((_BYTE *)v5 + 153) ^ (4 * v389)) & 0xF3;
    if ( !v388 )
      goto LABEL_588;
    LOBYTE(v206) = v470[33];
    v205 = v470[32];
    v209 = *(float *)&v470[28];
    v166 = *(__m128 *)&v470[16];
    v210 = *(float *)&v470[12];
    v165 = *(__m128 *)v470;
    v211 = v469.m128_f32[3];
    v164 = v469;
    v212 = *((float *)&v468[1] + 1);
    v163 = *(__m128 *)v468;
LABEL_523:
    if ( (char)(16 * *((_BYTE *)v5 + 152)) >> 6 != 1 )
    {
      if ( (char)(16 * *((_BYTE *)v5 + 152)) >> 6 < 0 )
        goto LABEL_525;
      v410 = *((_BYTE *)v5 + 153);
      if ( (char)(4 * v410) >> 6 == 1
        || (char)(4 * v410) >> 6 >= 0
        && (v208 > COERCE_FLOAT(
                     COERCE_UNSIGNED_INT(
                       (float)((float)((float)(COERCE_FLOAT(*((_DWORD *)v5 + 29) & v155) * v207)
                                     + (float)(COERCE_FLOAT(*((_DWORD *)v5 + 25) & v155) * v207))
                             + COERCE_FLOAT(*((_DWORD *)v5 + 37) & v155))
                     - 1.0)
                   & v155)
          ? (v411 = -1, v412 = 1)
          : (v411 = 1, v412 = 0),
            *((_BYTE *)v5 + 153) = (16 * v411) ^ (v410 ^ (16 * v411)) & 0xCF,
            !v412)
        || v208 <= COERCE_FLOAT(COERCE_UNSIGNED_INT(*((float *)v5 + 24) - 0.0) & v155)
        || v208 <= COERCE_FLOAT(COERCE_UNSIGNED_INT(*((float *)v5 + 28) - 0.0) & v155) )
      {
        v420 = 0;
        v421 = 1;
      }
      else
      {
        v420 = 1;
        v421 = -1;
      }
      *((_BYTE *)v5 + 152) = (4 * v421) ^ (*((_BYTE *)v5 + 152) ^ (4 * v421)) & 0xF3;
      if ( !v420 )
        goto LABEL_588;
      LOBYTE(v206) = v470[33];
      v205 = v470[32];
      v209 = *(float *)&v470[28];
      v166 = *(__m128 *)&v470[16];
      v210 = *(float *)&v470[12];
      v165 = *(__m128 *)v470;
      v211 = v469.m128_f32[3];
      v164 = v469;
      v212 = *((float *)&v468[1] + 1);
      v163 = *(__m128 *)v468;
LABEL_525:
      if ( *((char *)v5 + 152) >> 6 != 1 )
      {
        if ( *((char *)v5 + 152) >> 6 < 0 )
          goto LABEL_527;
        v300 = *((_BYTE *)v5 + 153);
        if ( (char)(4 * v300) >> 6 == 1
          || (char)(4 * v300) >> 6 >= 0
          && (v208 > COERCE_FLOAT(
                       COERCE_UNSIGNED_INT(
                         (float)((float)((float)(COERCE_FLOAT(*((_DWORD *)v5 + 29) & v155) * v207)
                                       + (float)(COERCE_FLOAT(*((_DWORD *)v5 + 25) & v155) * v207))
                               + COERCE_FLOAT(*((_DWORD *)v5 + 37) & v155))
                       - 1.0)
                     & v155)
            ? (v301 = -1, v302 = 1)
            : (v301 = 1, v302 = 0),
              *((_BYTE *)v5 + 153) = (16 * v301) ^ ((16 * v301) ^ v300) & 0xCF,
              !v302)
          || v208 <= COERCE_FLOAT(COERCE_UNSIGNED_INT(*((float *)v5 + 23) - 0.0) & v155)
          || v208 <= COERCE_FLOAT(COERCE_UNSIGNED_INT(*((float *)v5 + 26) - 0.0) & v155) )
        {
          v284 = 0;
          v285 = 1;
        }
        else
        {
          v284 = 1;
          v285 = -1;
        }
        *((_BYTE *)v5 + 152) = (v285 << 6) | *((_BYTE *)v5 + 152) & 0x3F;
        if ( v284 )
        {
          LOBYTE(v206) = v470[33];
          v205 = v470[32];
          v209 = *(float *)&v470[28];
          v210 = *(float *)&v470[12];
          v211 = v469.m128_f32[3];
          v212 = *((float *)&v468[1] + 1);
LABEL_527:
          v259 = *((float *)v5 + 22);
          v260 = *((_DWORD *)v5 + 36);
          v261 = *((float *)v5 + 34);
          v262 = *((float *)v5 + 35);
          v263 = *((float *)v5 + 32);
          v264 = *((float *)v5 + 27);
          v462[0] = v260;
          if ( v208 <= COERCE_FLOAT(COERCE_UNSIGNED_INT(v259 - 1.0) & v155)
            || v208 <= COERCE_FLOAT(COERCE_UNSIGNED_INT(v264 - 1.0) & v155)
            || v208 <= COERCE_FLOAT(COERCE_UNSIGNED_INT(v263 - 1.0) & v155) )
          {
            *(float *)v468 = *(float *)v468 * v259;
            v469.m128_f32[0] = v469.m128_f32[0] * v259;
            *(float *)v470 = *(float *)v470 * v259;
            *((float *)v468 + 1) = *((float *)v468 + 1) * v264;
            *(float *)&v470[16] = *(float *)&v470[16] * v259;
            *(float *)&v470[4] = *(float *)&v470[4] * v264;
            v469.m128_f32[1] = v469.m128_f32[1] * v264;
            *(float *)&v470[20] = *(float *)&v470[20] * v264;
            if ( v208 <= COERCE_FLOAT(COERCE_UNSIGNED_INT(v263 - 1.0) & v155) )
            {
              *(float *)&v468[1] = *(float *)&v468[1] * v263;
              v469.m128_f32[2] = v469.m128_f32[2] * v263;
              *(float *)&v470[8] = *(float *)&v470[8] * v263;
              *(float *)&v470[24] = *(float *)&v470[24] * v263;
            }
            v260 = v462[0];
            v205 &= 0xCCu;
            v470[32] = v205;
          }
          if ( v208 <= COERCE_FLOAT(LODWORD(v261) & v155)
            || v208 <= COERCE_FLOAT(LODWORD(v262) & v155)
            || v208 <= COERCE_FLOAT(v260 & v155) )
          {
            if ( (char)(4 * v206) >> 6 == 1
              || ((char)(4 * v206) >> 6 >= 0
                ? (v208 <= COERCE_FLOAT(
                             COERCE_UNSIGNED_INT(
                               (float)((float)((float)(COERCE_FLOAT(LODWORD(v211) & v155) * v207)
                                             + (float)(COERCE_FLOAT(LODWORD(v212) & v155) * v207))
                                     + COERCE_FLOAT(LODWORD(v209) & v155))
                             - 1.0)
                           & v155)
                 ? (v350 = 1, LOBYTE(v162) = 0)
                 : (v350 = -1, LOBYTE(v162) = 1),
                   LOBYTE(v206) = v206 & 0xCF | (16 * (v350 & 3)),
                   v470[33] = v206,
                   v265 = (unsigned __int8)v162
                        & (v208 > COERCE_FLOAT(COERCE_UNSIGNED_INT((float)(COERCE_FLOAT(LODWORD(v210) & v155) * v207) - 0.0) & v155)))
                : (v265 = v208 > COERCE_FLOAT(COERCE_UNSIGNED_INT((float)(COERCE_FLOAT(LODWORD(v210) & v155) * v207) - 0.0) & v155)),
                  !v265) )
            {
              v470[33] = v206 & 0xF3;
              *(float *)v468 = *(float *)v468 + (float)(v261 * v212);
              *((float *)v468 + 1) = *((float *)v468 + 1) + (float)(v262 * v212);
              *(float *)&v468[1] = *(float *)&v468[1] + (float)(*(float *)v462 * v212);
              v469.m128_f32[0] = v469.m128_f32[0] + (float)(v261 * v211);
              v469.m128_f32[1] = v469.m128_f32[1] + (float)(v262 * v211);
              v469.m128_f32[2] = v469.m128_f32[2] + (float)(*(float *)v462 * v211);
              *(float *)v470 = *(float *)v470 + (float)(v261 * v210);
              *(float *)&v470[4] = *(float *)&v470[4] + (float)(v262 * v210);
              *(float *)&v470[8] = *(float *)&v470[8] + (float)(*(float *)v462 * v210);
              *(float *)&v470[16] = *(float *)&v470[16] + (float)(v261 * v209);
              *(float *)&v470[20] = *(float *)&v470[20] + (float)(v262 * v209);
              v266 = *(float *)&v470[24] + (float)(*(float *)v462 * v209);
            }
            else
            {
              *(float *)&v470[16] = *(float *)&v470[16] + v261;
              v266 = *(float *)&v470[24] + *(float *)v462;
              *(float *)&v470[20] = *(float *)&v470[20] + v262;
            }
            *(float *)&v470[24] = v266;
            v470[32] = v205 & 0xFC;
          }
          goto LABEL_406;
        }
LABEL_588:
        LOBYTE(v206) = v470[33];
        v205 = v470[32];
        v209 = *(float *)&v470[28];
        v166 = *(__m128 *)&v470[16];
        v210 = *(float *)&v470[12];
        v165 = *(__m128 *)v470;
        v211 = v469.m128_f32[3];
        v164 = v469;
        v212 = *((float *)&v468[1] + 1);
        v163 = *(__m128 *)v468;
      }
    }
  }
  if ( (char)(16 * v206) >> 6 != 1 )
  {
    if ( (char)(16 * v206) >> 6 < 0 )
      goto LABEL_591;
    if ( (char)(4 * v206) >> 6 == 1
      || ((char)(4 * v206) >> 6 >= 0
        ? (v208 <= COERCE_FLOAT(
                     COERCE_UNSIGNED_INT(
                       (float)((float)((float)(COERCE_FLOAT(LODWORD(v211) & v155) * v207)
                                     + (float)(COERCE_FLOAT(LODWORD(v212) & v155) * v207))
                             + COERCE_FLOAT(LODWORD(v209) & v155))
                     - 1.0)
                   & v155)
         ? (v429 = 1, v430 = 0)
         : (v429 = -1, v430 = 1),
           LOBYTE(v206) = v206 & 0xCF | (16 * (v429 & 3)),
           v403 = v430
                & (v208 > COERCE_FLOAT(COERCE_UNSIGNED_INT((float)(COERCE_FLOAT(LODWORD(v210) & v155) * v207) - 0.0) & v155)))
        : (v403 = v208 > COERCE_FLOAT(COERCE_UNSIGNED_INT((float)(COERCE_FLOAT(LODWORD(v210) & v155) * v207) - 0.0) & v155)),
          !v403
       || v208 <= COERCE_FLOAT(COERCE_UNSIGNED_INT(*(float *)v470 - 0.0) & v155)
       || v208 <= COERCE_FLOAT(COERCE_UNSIGNED_INT(*(float *)&v470[4] - 0.0) & v155)) )
    {
      v404 = 0;
      v405 = 1;
    }
    else
    {
      v404 = 1;
      v405 = -1;
    }
    LOBYTE(v206) = v206 & 0xF3 | (4 * (v405 & 3));
    v470[33] = v206;
    if ( v404 )
    {
LABEL_591:
      if ( (char)(16 * v205) >> 6 != 1 )
      {
        if ( (char)(16 * v205) >> 6 < 0 )
          goto LABEL_1020;
        if ( (char)(4 * v206) >> 6 == 1
          || (char)(4 * v206) >> 6 >= 0
          && (v208 > COERCE_FLOAT(
                       COERCE_UNSIGNED_INT(
                         (float)((float)((float)(COERCE_FLOAT(LODWORD(v211) & v155) * v207)
                                       + (float)(COERCE_FLOAT(LODWORD(v212) & v155) * v207))
                               + COERCE_FLOAT(LODWORD(v209) & v155))
                       - 1.0)
                     & v155)
            ? (v422 = -1, v423 = 1)
            : (v422 = 1, v423 = 0),
              v470[33] = v206 & 0xCF | (16 * (v422 & 3)),
              !v423)
          || v208 <= COERCE_FLOAT(COERCE_UNSIGNED_INT(*(float *)&v468[1] - 0.0) & v155)
          || v208 <= COERCE_FLOAT(COERCE_UNSIGNED_INT(v469.m128_f32[2] - 0.0) & v155) )
        {
          v333 = 0;
          v334 = 1;
        }
        else
        {
          v333 = 1;
          v334 = -1;
        }
        v470[32] = v205 & 0xF3 | (4 * (v334 & 3));
        if ( v333 )
        {
LABEL_1020:
          if ( (unsigned __int8)CMILMatrix::IsPure2DUniformZ<1>((char *)v5 + 88) )
          {
            v286 = (__m128)*((unsigned int *)v5 + 22);
            v287 = (__m128)*((unsigned int *)v5 + 27);
            v288 = v286;
            v289 = *((float *)v5 + 26);
            v290 = v287;
            v291 = v287;
            v292 = v286;
            v288.m128_f32[0] = (float)((float)(v286.m128_f32[0] * *(float *)&v470[16])
                                     + (float)(v289 * *(float *)&v470[20]))
                             + *((float *)v5 + 34);
            v293 = *(float *)&v470[24];
            v294 = *((float *)v5 + 23) * v469.m128_f32[0];
            v291.m128_f32[0] = (float)((float)(v287.m128_f32[0] * *(float *)&v470[20])
                                     + (float)(*((float *)v5 + 23) * *(float *)&v470[16]))
                             + *((float *)v5 + 35);
            v290.m128_f32[0] = (float)(v287.m128_f32[0] * *((float *)v468 + 1))
                             + (float)(*((float *)v5 + 23) * *(float *)v468);
            *(_QWORD *)&v470[28] = 0x28083F800000LL;
            v287.m128_f32[0] = (float)(v287.m128_f32[0] * v469.m128_f32[1]) + v294;
            *(_QWORD *)v470 = 0;
            v292.m128_f32[0] = (float)(v286.m128_f32[0] * *(float *)v468) + (float)(v289 * *((float *)v468 + 1));
            v286.m128_f32[0] = (float)(v286.m128_f32[0] * v469.m128_f32[0]) + (float)(v289 * v469.m128_f32[1]);
            *(__m128 *)&v470[12] = _mm_movelh_ps(_mm_unpacklo_ps((__m128)0LL, v288), _mm_unpacklo_ps(v291, (__m128)0LL));
            *(__m128 *)v468 = _mm_movelh_ps(_mm_unpacklo_ps(v292, v290), (__m128)0LL);
            v469 = _mm_movelh_ps(_mm_unpacklo_ps(v286, v287), (__m128)0LL);
            v290.m128_i32[0] = *((_DWORD *)v5 + 32);
            *(float *)&v470[8] = v290.m128_f32[0] * *(float *)&v470[8];
            *(float *)&v470[24] = (float)(v290.m128_f32[0] * v293) + *((float *)v5 + 36);
            goto LABEL_406;
          }
          v166 = *(__m128 *)&v470[16];
          v165 = *(__m128 *)v470;
          v164 = v469;
          v163 = *(__m128 *)v468;
        }
      }
    }
  }
  v335 = *(__m128 *)((char *)v5 + 88);
  v336 = *(__m128 *)((char *)v5 + 104);
  v337 = *(__m128 *)((char *)v5 + 120);
  v338 = *(__m128 *)((char *)v5 + 136);
  *(__m128 *)v468 = _mm_add_ps(
                      _mm_add_ps(
                        _mm_mul_ps(_mm_shuffle_ps(v163, v163, 255), v338),
                        _mm_mul_ps(_mm_shuffle_ps(v163, v163, 85), v336)),
                      _mm_add_ps(
                        _mm_mul_ps(_mm_shuffle_ps(v163, v163, 170), v337),
                        _mm_mul_ps(_mm_shuffle_ps(v163, v163, 0), v335)));
  v469 = _mm_add_ps(
           _mm_add_ps(
             _mm_mul_ps(_mm_shuffle_ps(v164, v164, 0), v335),
             _mm_mul_ps(_mm_shuffle_ps(v164, v164, 170), v337)),
           _mm_add_ps(
             _mm_mul_ps(_mm_shuffle_ps(v164, v164, 85), v336),
             _mm_mul_ps(_mm_shuffle_ps(v164, v164, 255), v338)));
  *(__m128 *)v470 = _mm_add_ps(
                      _mm_add_ps(
                        _mm_mul_ps(_mm_shuffle_ps(v165, v165, 255), v338),
                        _mm_mul_ps(_mm_shuffle_ps(v165, v165, 85), v336)),
                      _mm_add_ps(
                        _mm_mul_ps(_mm_shuffle_ps(v165, v165, 170), v337),
                        _mm_mul_ps(_mm_shuffle_ps(v165, v165, 0), v335)));
  *(__m128 *)&v470[16] = _mm_add_ps(
                           _mm_add_ps(
                             _mm_mul_ps(_mm_shuffle_ps(v166, v166, 255), v338),
                             _mm_mul_ps(_mm_shuffle_ps(v166, v166, 85), v336)),
                           _mm_add_ps(
                             _mm_mul_ps(_mm_shuffle_ps(v166, v166, 170), v337),
                             _mm_mul_ps(_mm_shuffle_ps(v166, v166, 0), v335)));
  CMILMatrix::InvalidateAllFlags((CMILMatrix *)v468);
LABEL_406:
  v215 = CDrawingContext::PushTransformForNode(
           v5,
           (const struct CVisual *)v7,
           (const struct CMILMatrix *)v468,
           (char)v162);
  v3 = v215;
  v454 = v215;
  if ( v215 < 0 )
  {
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v215, 0x15DBu, 0);
    goto LABEL_24;
  }
LABEL_313:
  if ( CCpuClip::HasContextDependentClip((CCpuClip *)((char *)&v463 + 8)) && !*((_BYTE *)v5 + 8064) )
    CMILMatrix::Multiply((CMILMatrix *)&v470[36], (CDrawingContext *)((char *)v5 + 88));
  CpuClippingData = CVisual::GetCpuClippingData((CVisual *)v7, a2);
  D2DAntialiasMode = CDrawingContext::GetD2DAntialiasMode(v5);
  v172 = std::unique_ptr<CCpuClippingData::CpuClipRealization>::operator->(
           (char *)&v463 + 8,
           (unsigned int)D2DAntialiasMode);
  v174 = CCpuClippingData::Update(
           CpuClippingData,
           a2,
           v7,
           (char *)v5 + 736,
           v172,
           &v470[36],
           *((_QWORD *)v5 + 26),
           v173,
           v476);
  v454 = v174;
  v3 = v174;
  if ( v174 < 0 )
  {
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v174, 0x15F8u, 0);
    goto LABEL_24;
  }
  if ( CCpuClippingData::HasCpuClip(CpuClippingData) )
  {
    LOBYTE(v477[0]) = 1;
    v465 = CpuClippingData;
  }
  ScopeMode = CCpuClippingData::GetScopeMode();
  CanIgnoreAncestorCpuClips = CCpuClippingData::CanIgnoreAncestorCpuClips(v176);
  if ( CanIgnoreAncestorCpuClips )
  {
LABEL_320:
    if ( ScopeMode == 2 || CanIgnoreAncestorCpuClips )
      goto LABEL_538;
    goto LABEL_322;
  }
  if ( ScopeMode <= 2
    || CCpuClip::HasContextDependentClip((CCpuClip *)((char *)&v463 + 8))
    || (TopByReference = CMatrixStack::GetTopByReference((CDrawingContext *)((char *)v5 + 280)),
        InputBounds = CVisual::GetInputBounds(v7, v272, TopByReference),
        !(unsigned __int8)CDrawingContext::DoesCpuClipFullyContainRect(v5, InputBounds)) )
  {
    CanIgnoreAncestorCpuClips = 0;
    goto LABEL_320;
  }
LABEL_538:
  TMilRect_<int,tagRECT,Mil3DRectL,D2D_POINTANDSIZE_L,RectUniqueness::_CMilRectL_>::TMilRect_<int,tagRECT,Mil3DRectL,D2D_POINTANDSIZE_L,RectUniqueness::_CMilRectL_>(v510);
  HasContextDependentClip = CCpuClip::HasContextDependentClip((CCpuClip *)((char *)&v463 + 8));
  v268 = v468;
  if ( HasContextDependentClip )
    v268 = (__int64 *)&v470[36];
  v269 = CDrawingContext::PushClippingScope(v5, (__int64)v268, (__int64)v510);
  v454 = v269;
  v3 = v269;
  if ( v269 < 0 )
  {
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v269, 0x161Fu, 0);
    goto LABEL_24;
  }
  v270 = CDrawingContext::PushGpuClipRectInternal((_DWORD)v5, v7, (unsigned int)v510, 0, 1);
  v454 = v270;
  v3 = v270;
  if ( v270 < 0 )
  {
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v270, 0x1625u, 0);
    goto LABEL_24;
  }
LABEL_322:
  if ( !CDrawingContext::NodeEffects::HasEffects((CDrawingContext::NodeEffects *)&v463)
    || CComposition::IsTextureMemoryHeatMapEnabled(g_pComposition) )
  {
    goto LABEL_323;
  }
  CDrawingContext::CalcNodeWorldSpaceInputBounds(v5, v7, &v513);
  v228 = CDrawingContext::CalcInversedWorldInputBoundsFromVisibleWorldOutputBounds(
           (_DWORD)v5,
           v7,
           (unsigned int)&v508,
           (unsigned int)&v513,
           (__int64)&v515,
           (__int64)&v511);
  v454 = v228;
  v3 = v228;
  if ( v228 < 0 )
  {
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v228, 0x163Au, 0);
    goto LABEL_24;
  }
  v453[0] = 0;
  v229 = CDrawingContext::PushEffects(
           v5,
           (CDrawingContext::NodeEffects *)&v463,
           (__int64)&v511,
           (__int64)&v495,
           (__int64)v453);
  v454 = v229;
  v3 = v229;
  if ( v229 < 0 )
  {
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v229, 0x1641u, 0);
    goto LABEL_24;
  }
  if ( v453[0] )
  {
    v17 = v461;
    *v461 = 0;
    goto LABEL_25;
  }
LABEL_323:
  if ( ScopeMode != 4 )
  {
    if ( ScopeMode != 3 )
      goto LABEL_325;
    TMilRect_<int,tagRECT,Mil3DRectL,D2D_POINTANDSIZE_L,RectUniqueness::_CMilRectL_>::TMilRect_<int,tagRECT,Mil3DRectL,D2D_POINTANDSIZE_L,RectUniqueness::_CMilRectL_>(&v511);
    v201 = CDrawingContext::PushClippingScope(v5, (__int64)v468, (__int64)&v511);
    v454 = v201;
    v3 = v201;
    if ( v201 >= 0 )
    {
      v202 = CDrawingContext::PushGpuClipRectInternal((_DWORD)v5, v7, (unsigned int)&v511, 0, 1);
      v454 = v202;
      v3 = v202;
      if ( v202 < 0 )
      {
        MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v202, 0x166Du, 0);
        goto LABEL_24;
      }
      goto LABEL_325;
    }
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v201, 0x1667u, 0);
    goto LABEL_24;
  }
  if ( !CScopedClipStack::UseCpuClippingInScope((CDrawingContext *)((char *)v5 + 736)) )
    goto LABEL_325;
  TMilRect_<int,tagRECT,Mil3DRectL,D2D_POINTANDSIZE_L,RectUniqueness::_CMilRectL_>::TMilRect_<int,tagRECT,Mil3DRectL,D2D_POINTANDSIZE_L,RectUniqueness::_CMilRectL_>(&v511);
  v316 = CDrawingContext::PushClippingScope(v5, 0, (__int64)&v511);
  v454 = v316;
  v3 = v316;
  if ( v316 < 0 )
  {
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v316, 0x1657u, 0);
    goto LABEL_24;
  }
  v317 = CDrawingContext::PushGpuClipRectInternal((_DWORD)v5, v7, (unsigned int)&v511, 0, 1);
  v454 = v317;
  v3 = v317;
  if ( v317 < 0 )
  {
    MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v317, 0x165Du, 0);
    goto LABEL_24;
  }
LABEL_325:
  v178 = CWatermarkStack<CDrawingContext::StackBackfaceVisibilityEntry,64,2,10>::GetTopByReference((char *)v5 + 3272);
  v453[0] = 0;
  v179 = *(_BYTE *)(v178 + 8);
  if ( CVisual::HasNonDefaultEffectInternal((CVisual *)v7) || CVisual::IsSimple3DRootOrHasEffects(v180, v485) )
  {
    v330 = CDrawingContext::PreSubgraph_::_2_::_lambda_1_::operator()(&v493, v453);
    CDrawingContext::StackBackfaceVisibilityEntry::StackBackfaceVisibilityEntry(
      (CDrawingContext::StackBackfaceVisibilityEntry *)&v511,
      (const struct CVisual *)v7,
      v330);
    v331 = CWatermarkStack<CDrawingContext::StackBackfaceVisibilityEntry,64,2,10>::Push((char *)v5 + 3272, &v511);
    v454 = v331;
    v3 = v331;
    if ( v331 < 0 )
    {
      MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v331, 0x167Au, 0);
      goto LABEL_24;
    }
  }
  if ( !CVisual::HasNonDefaultWindowBackgroundTreatmentInternal((CVisual *)v7) )
    goto LABEL_328;
  WindowBackgroundTreatmentInternal = CVisual::GetWindowBackgroundTreatmentInternal(v181);
  if ( !CWindowBackgroundTreatment::HasValidBounds(WindowBackgroundTreatmentInternal)
    || (TMilRect_<int,tagRECT,Mil3DRectL,D2D_POINTANDSIZE_L,RectUniqueness::_CMilRectL_>::TMilRect_<int,tagRECT,Mil3DRectL,D2D_POINTANDSIZE_L,RectUniqueness::_CMilRectL_>(&v511),
        CDrawingContext::GetClipBoundsWorld(v5, &v511),
        TMil3DRect<float,TMilRect_<float,D2D_RECT_F,D3D_RECT_F,D2D_POINTANDSIZE_F,RectUniqueness::NotNeeded>,D3D_RECT_F,MilPointAndSizeF,RectUniqueness::NotNeeded>::TMil3DRect<float,TMilRect_<float,D2D_RECT_F,D3D_RECT_F,D2D_POINTANDSIZE_F,RectUniqueness::NotNeeded>,D3D_RECT_F,MilPointAndSizeF,RectUniqueness::NotNeeded>(v506),
        v306 = CMatrixStack::GetTopByReference((CDrawingContext *)((char *)v5 + 280)),
        v309 = CWindowBackgroundTreatment::GetBounds(WindowBackgroundTreatmentInternal, v307, v308, v306),
        CMILMatrix::Transform3DBounds(v310, v309, v506),
        v311 = Microsoft::BamoImpl::BamoPrincipalImpl::AsPrincipal((Microsoft::BamoImpl::BamoPrincipalImpl *)v506),
        !(unsigned __int8)TMilRect<float,D2D_RECT_F,D3D_RECT_F,RectUniqueness::NotNeeded>::DoesIntersect(&v511, v311)) )
  {
LABEL_328:
    v182 = v485;
    if ( CVisual::IsPreserve3DRoot((CVisual *)v7, v485) )
    {
      if ( !CVisual::HasBspPolygonList((CVisual *)v7) )
        goto LABEL_24;
      if ( (Microsoft_Windows_Dwm_CoreEnableBits & 0x20) != 0 )
        McTemplateU0_EventWriteTransfer(&Microsoft_Windows_Dwm_Core_Provider_Context, EVTDESC_P3D_RENDERING_Start);
      v253 = CDrawingContext::DrawBspPolygonList(v5, (struct CVisual *)v7, v182);
      v454 = v253;
      v3 = v253;
      if ( v253 < 0 )
      {
        MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v253, 0x1708u, 0);
        goto LABEL_24;
      }
      if ( (Microsoft_Windows_Dwm_CoreEnableBits & 0x20) != 0 )
        McTemplateU0_EventWriteTransfer(&Microsoft_Windows_Dwm_Core_Provider_Context, EVTDESC_P3D_RENDERING_Stop);
      CProcessAttribution::MarkCompositorRendered(v479);
      v17 = v461;
      *v461 = 0;
      goto LABEL_25;
    }
    v455 = 0;
    if ( !*((_DWORD *)v5 + 62)
      || v179 == (unsigned __int8)CDrawingContext::PreSubgraph_::_2_::_lambda_1_::operator()(&v493, v453) )
    {
      if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v7 + 264LL))(v7) )
      {
        (*(void (__fastcall **)(__int64, CDrawingContext *, char *))(*(_QWORD *)v7 + 256LL))(v7, v5, &v455);
        CProcessAttribution::MarkCompositorRendered(v479);
        goto LABEL_332;
      }
      if ( !CVisual::HasProtectedContent((CVisual *)v7) )
        goto LABEL_332;
      CDrawingContext::NotifyFrameContainsProtectedContent(v5);
      if ( !CComposition::IsScreenReadBack(g_pComposition) )
        goto LABEL_332;
    }
    else if ( !CVisual::HasNonDefaultEffectInternal((CVisual *)v7) && !(*(__int64 (**)(void))(*(_QWORD *)v7 + 232LL))()
           || !(unsigned __int8)CDrawingContext::PreSubgraph_::_2_::_lambda_1_::operator()(&v493, v453)
           || *(_BYTE *)(CWatermarkStack<CDrawingContext::StackBackfaceVisibilityEntry,64,2,10>::GetTopByReference((char *)v5 + 3272)
                       + 8) == v179 )
    {
      goto LABEL_332;
    }
    v455 = 1;
LABEL_332:
    if ( HIBYTE(v477[0])
      && (*(unsigned __int8 (__fastcall **)(__int64, __int64))(*(_QWORD *)v7 + 64LL))(v7, 72)
      && CLayerVisual::IsAutomaticBoundsToLocalSpaceEnabled((CLayerVisual *)v7) )
    {
      CLayerStack::Top((CDrawingContext *)((char *)v5 + 352));
      CMILMatrix::CMILMatrix((CMILMatrix *)v507);
      CTreeEffectLayer::GetTransformToLayerSpace(v322, (struct CMILMatrix *)v507);
      FlatteningVisualTree = CLayerVisual::GetFlatteningVisualTree((CLayerVisual *)v7);
      Bounds = CVisualTree::GetBounds(FlatteningVisualTree);
      v326 = CDrawingContext::DrawSubVisualTree(v5, v325, Bounds, v507);
      v454 = v326;
      v3 = v326;
      if ( v326 >= 0 )
      {
        v17 = v461;
        v455 = 1;
        *v461 = 0;
        goto LABEL_25;
      }
      MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, v326, 0x16F8u, 0);
      goto LABEL_24;
    }
    if ( !v455 )
      goto LABEL_24;
    v17 = v461;
    *v461 = 0;
    goto LABEL_25;
  }
  v456 = 0;
  v460 = 1;
  v459 = 0;
  if ( CWindowBackgroundTreatment::GetBackdropBrushNoRef(WindowBackgroundTreatmentInternal, &v459) )
    v456 = v459;
  v312 = (const struct RenderTargetInfo *)(*(__int64 (__fastcall **)(__int64))(*((_QWORD *)v5 + 2) + 16LL))((__int64)v5 + 16);
  if ( CWindowBackgroundTreatment::HasValidRenderingRealization(WindowBackgroundTreatmentInternal, v312) )
  {
LABEL_625:
    if ( v456 && !v460 )
      CTelemetryFrames::IncrementWindowBackdropBrushCacheMisses(v313);
    v315 = CMatrixStack::GetTopByReference((CDrawingContext *)((char *)v5 + 280));
    CWindowBackgroundTreatment::SetWorldTransform(WindowBackgroundTreatmentInternal, v315, 3);
    goto LABEL_328;
  }
  v460 = !v456;
  BitmapForEffectInput = CWindowBackgroundTreatment::GenerateBitmapForEffectInput(WindowBackgroundTreatmentInternal, v5);
  v454 = BitmapForEffectInput;
  v3 = BitmapForEffectInput;
  if ( BitmapForEffectInput >= 0 )
  {
    CWindowBackgroundTreatment::SetCacheInvalidationRequired(WindowBackgroundTreatmentInternal, 1);
    goto LABEL_625;
  }
  MilInstrumentationCheckHR_MaybeFailFast(0x14u, 0, 0, BitmapForEffectInput, 0x16A3u, 0);
LABEL_24:
  v17 = v461;
LABEL_25:
  if ( *((_BYTE *)v5 + 8068) && (unsigned __int8)CWatermarkStack<bool,64,2,10>::TopOrDefault((char *)v5 + 3176) )
    CVisual::RenderProjectedShadows(v7, v5, 1);
  if ( !*v17 && CDrawingContext::IsBackdropWalk(v5) && !*((_BYTE *)v5 + 185) )
  {
    CurrentVisualTreePath = CDrawingContext::GetCurrentVisualTreePath((CDrawingContext *)i2);
    if ( CBackdropVisualImage::IsVisualInAncestorList(
           *((CBackdropVisualImage **)v5 + 24),
           (const struct CVisual *)v7,
           CurrentVisualTreePath) )
    {
      *((_BYTE *)v5 + 185) = 1;
    }
  }
  if ( DwmDbg::Backdrops::IsEtwEnabled((DwmDbg::Backdrops *)i2)
    && !*v17
    && (CVisual::SubgraphHasBackdropInput((CVisual *)v7) || CVisual::SubgraphHasWindowBackdropInput(v90)) )
  {
    TMilRect_<int,tagRECT,Mil3DRectL,D2D_POINTANDSIZE_L,RectUniqueness::_CMilRectL_>::TMilRect_<int,tagRECT,Mil3DRectL,D2D_POINTANDSIZE_L,RectUniqueness::_CMilRectL_>(&v511);
    CDrawingContext::GetClipBoundsWorld(v5, &v511);
    v91 = (const void *)*((_QWORD *)v5 + 24);
    v92 = *(const char **)DwmDbg::DbgString::DbgString((DwmDbg::DbgString *)v498, &v511);
    v93 = (const char **)DwmDbg::DbgString::DbgString((DwmDbg::DbgString *)v497, &v454);
    v94 = DwmDbg::DbgString::DbgString(
            (DwmDbg::DbgString *)v503,
            "hr=%s, clipBoundsWorld=[%s], m_pCutoffBVI=0x%p",
            *v93,
            v92,
            v91);
    v95 = CDrawingContext::GetCurrentVisualTreePath(v5);
    IsBackdropWalk = CDrawingContext::IsBackdropWalk(v96);
    v98 = "Render-BailWithBackdropsStillInSubtree-Backdrop";
    if ( !IsBackdropWalk )
      v98 = "Render-BailWithBackdropsStillInSubtree-Normal";
    v99 = DwmDbg::DbgString::DbgString((DwmDbg::DbgString *)v504, v98);
    DwmDbg::Backdrops::LogTreeWalkEtwEvent(v99, v7, a2, v95, v94);
    DwmDbg::DbgString::~DbgString((DwmDbg::DbgString *)v497);
    DwmDbg::DbgString::~DbgString((DwmDbg::DbgString *)v498);
    v3 = v454;
  }
  CDrawingContext::NodeEffects::~NodeEffects((CDrawingContext::NodeEffects *)&v463);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180037020  mov     [rsp-8+arg_18], rbx
0x180037025  push    rbp
0x180037026  push    rsi
0x180037027  push    rdi
0x180037028  push    r12
0x18003702a  push    r13
0x18003702c  push    r14
0x18003702e  push    r15
0x180037030  lea     rbp, [rsp-2E0h]
0x180037038  sub     rsp, 3E0h
0x18003703f  movaps  [rsp+410h+var_A0], xmm12
0x180037048  movaps  [rsp+410h+var_C0], xmm14
0x180037051  mov     rax, cs:__security_cookie
0x180037058  xor     rax, rsp
0x18003705b  mov     [rbp+310h+var_E0], rax
0x180037062  movss   xmm12, cs:__real@3f800000
0x18003706b  xor     r13d, r13d
0x18003706e  xorps   xmm0, xmm0
0x180037071  mov     [rsp+410h+var_3A0], r8
0x180037076  mov     edi, r13d
0x180037079  mov     qword ptr [rbp+310h+var_138], rcx
0x180037080  mov     [rbp+310h+var_160], rdi
0x180037087  xorps   xmm1, xmm1
0x18003708a  mov     [rbp+310h+var_118], rdi
0x180037091  mov     r15, rdx
0x180037094  movups  [rbp+310h+var_170], xmm1
0x18003709b  mov     rsi, rcx
0x18003709e  mov     [rsp+410h+var_3A8], r13d
0x1800370a3  movups  [rbp+310h+var_128], xmm0
0x1800370aa  mov     [rsp+410h+var_3BC], r13d
0x1800370af  movups  [rbp+310h+var_110], xmm0
0x1800370b6  mov     rax, [rcx+0C90h]
0x1800370bd  mov     r14, [rcx+0C88h]
0x1800370c4  xorps   xmm14, xmm14
0x1800370c8  mov     [rbp+310h+var_2E8], 3F800000h
0x1800370d0  mov     [rbp+310h+var_290], rax
0x1800370d7  movzx   eax, byte ptr [rbp+310h+var_2E8+5]
0x1800370db  and     al, 0EAh
0x1800370dd  movdqu  [rbp+310h+var_390], xmm0
0x1800370e2  or      al, 2Ah
0x1800370e4  mov     [rbp+310h+var_380], dil
0x1800370e8  mov     byte ptr [rbp+310h+var_2E8+5], al
0x1800370eb  lea     rax, [rbp+310h+var_368]
0x1800370ef  mov     [rbp+310h+var_378], r13
0x1800370f3  mov     [rbp+310h+var_370], r13d
0x1800370f7  mov     [rbp+310h+var_36C], 3F800000h
0x1800370fe  mov     [rbp+310h+var_328], r13
0x180037102  mov     [rbp+310h+var_2E0], r13
0x180037106  mov     [rbp+310h+var_2D8], r13d
0x18003710a  mov     [rbp+310h+var_2D4], di
0x18003710e  movups  [rbp+310h+var_320], xmm0
0x180037112  movups  [rbp+310h+var_310], xmm1
0x180037116  movups  [rbp+310h+var_300], xmm0
0x18003711a  mov     [rbp+310h+var_2F0], rdi
0x18003711e  mov     byte ptr [rbp+310h+var_2E8+4], 99h
0x180037122  mov     rdx, [r14+0E0h]
0x180037129  movups  [rbp+310h+var_240], xmm0
0x180037130  mov     [rbp+310h+var_158], r14
0x180037137  movups  xmmword ptr [rbp+310h+var_148.left], xmm1
0x18003713e  test    dword ptr [rdx], 80000h
0x180037144  mov     [rbp+310h+var_250], rax
0x18003714b  jnz     loc_180037AF6
0x180037151  xor     bl, bl
0x180037153  mov     r9d, [rsi+0C74h]; unsigned int
0x18003715a  mov     r12d, 1
0x180037160  cmp     [rsi+0C70h], r9d
0x180037167  jz      loc_180037984
0x18003716d  mov     ecx, [rsi+0C70h]
0x180037173  mov     rax, [rsi+0C68h]
0x18003717a  mov     [rcx+rax], bl
0x18003717d  inc     dword ptr [rsi+0C70h]
0x180037183  mov     ecx, [rsi+0C70h]
0x180037189  mov     eax, [rsi+0C7Ch]
0x18003718f  cmp     eax, ecx
0x180037191  cmovbe  eax, ecx
0x180037194  mov     [rsi+0C7Ch], eax
0x18003719a  cmp     qword ptr [rsi+0C0h], 0
0x1800371a2  jnz     loc_180037644
0x1800371a8  cmp     byte ptr [r14+65h], 0
0x1800371ad  movaps  [rsp+410h+var_40], xmm6
0x1800371b5  movaps  [rsp+410h+var_50], xmm7
0x1800371bd  movaps  [rsp+410h+var_60], xmm8
0x1800371c6  movaps  [rsp+410h+var_70], xmm9
0x1800371cf  movaps  [rsp+410h+var_80], xmm10
0x1800371d8  movaps  [rsp+410h+var_90], xmm11
0x1800371e1  jl      short loc_1800371F1
0x1800371e3  test    dword ptr [r14+60h], 100h
0x1800371eb  jnz     loc_1800373FE
0x1800371f1  mov     eax, [rsi+0C70h]
0x1800371f7  test    eax, eax
0x1800371f9  jz      short loc_180037203
0x1800371fb  dec     eax
0x1800371fd  mov     [rsi+0C70h], eax
0x180037203  mov     r9d, [rsi+0C74h]; unsigned int
0x18003720a  cmp     eax, r9d
0x18003720d  jz      loc_180037D1F
0x180037213  mov     ecx, [rsi+0C70h]
0x180037219  mov     rax, [rsi+0C68h]
0x180037220  mov     byte ptr [rcx+rax], 0
0x180037224  mov     ecx, [rsi+0C70h]
0x18003722a  inc     ecx
0x18003722c  mov     [rsi+0C70h], ecx
0x180037232  mov     eax, [rsi+0C7Ch]
0x180037238  cmp     eax, ecx
0x18003723a  cmovbe  eax, ecx
0x18003723d  mov     [rsi+0C7Ch], eax
0x180037243  mov     rbx, [rsp+410h+var_3A0]
0x180037248  mov     byte ptr [rbx], 0
0x18003724b  jmp     loc_180037348
0x180037250  mov     eax, [r14+0C4h]
0x180037257  mov     [rsp+410h+var_3B0], eax
0x18003725b  mov     eax, [r14+0C8h]
0x180037262  lea     rdx, [rbp+310h+Src]
0x180037266  mov     [rsp+410h+var_3BC], eax
0x18003726a  lea     rcx, [rsi+100h]
0x180037271  mov     eax, [r14+0CCh]
0x180037278  mov     dword ptr [rbp+310h+var_2D0], eax
0x18003727b  mov     [rbp+310h+Src], 9
0x180037283  mov     [rbp+310h+Src+8], r14
0x180037287  call    ?Push@?$CWatermarkStack@V?$TMilRect_@MUD2D_RECT_F@@UD3D_RECT_F@@UD2D_POINTANDSIZE_F@@UNotNeeded@RectUniqueness@@@@$0EA@$01$09@@QEAAJAEBV?$TMilRect_@MUD2D_RECT_F@@UD3D_RECT_F@@UD2D_POINTANDSIZE_F@@UNotNeeded@RectUniqueness@@@@@Z; CWatermarkStack<TMilRect_<float,D2D_RECT_F,D3D_RECT_F,D2D_POINTANDSIZE_F,RectUniqueness::NotNeeded>,64,2,10>::Push(TMilRect_<float,D2D_RECT_F,D3D_RECT_F,D2D_POINTANDSIZE_F,RectUniqueness::NotNeeded> const &)
0x18003728c  mov     r13d, eax
0x18003728f  test    eax, eax
0x180037291  js      loc_18003C074
0x180037297  mov     eax, [rsi+0E8h]
0x18003729d  lea     rcx, [rsi+2C8h]
0x1800372a4  mov     dword ptr [rbp+310h+Src], eax
0x1800372a7  lea     rdx, [rbp+310h+Src]
0x1800372ab  mov     eax, [rsi+0ECh]
0x1800372b1  mov     dword ptr [rbp+310h+Src+4], eax
0x1800372b4  mov     eax, [rsi+0F0h]
0x1800372ba  mov     dword ptr [rbp+310h+Src+0Ch], eax
0x1800372bd  mov     eax, [rsi+0F4h]
0x1800372c3  mov     [rbp+310h+var_2A8], eax
0x1800372c6  mov     eax, [rsi+0F8h]
0x1800372cc  mov     [rbp+310h+var_2A4], eax
0x1800372cf  mov     dword ptr [rbp+310h+Src+8], 0
0x1800372d6  call    ?Push@?$CWatermarkStack@USavedRenderOptions@CDrawingContext@@$0EA@$01$09@@QEAAJAEBUSavedRenderOptions@CDrawingContext@@@Z; CWatermarkStack<CDrawingContext::SavedRenderOptions,64,2,10>::Push(CDrawingContext::SavedRenderOptions const &)
0x1800372db  mov     r13d, eax
0x1800372de  test    eax, eax
0x1800372e0  jns     loc_180037F0A
0x1800372e6  mov     r12d, 14h
0x1800372ec  mov     [rsp+410h+var_3E8], 0; void *
0x1800372f5  mov     ecx, r12d; unsigned int
0x1800372f8  mov     dword ptr [rsp+410h+var_3F0], 11D5h; unsigned int
0x180037300  mov     r9d, eax; int
0x180037303  xor     r8d, r8d; unsigned int
0x180037306  xor     edx, edx; int *
0x180037308  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18003730d  xor     edx, edx
0x18003730f  lea     rcx, [rsi+100h]
0x180037316  call    ?Pop@?$CWatermarkStack@V?$TMilRect_@MUD2D_RECT_F@@UD3D_RECT_F@@UD2D_POINTANDSIZE_F@@UNotNeeded@RectUniqueness@@@@$0EA@$01$09@@QEAA_NPEAV?$TMilRect_@MUD2D_RECT_F@@UD3D_RECT_F@@UD2D_POINTANDSIZE_F@@UNotNeeded@RectUniqueness@@@@@Z; CWatermarkStack<TMilRect_<float,D2D_RECT_F,D3D_RECT_F,D2D_POINTANDSIZE_F,RectUniqueness::NotNeeded>,64,2,10>::Pop(TMilRect_<float,D2D_RECT_F,D3D_RECT_F,D2D_POINTANDSIZE_F,RectUniqueness::NotNeeded> *)
0x18003731b  mov     [rsp+410h+var_3E8], 0; void *
0x180037324  mov     edi, r13d
0x180037327  mov     dword ptr [rsp+410h+var_3F0], 156Eh; unsigned int
0x18003732f  mov     [rsp+410h+var_3BC], edi
0x180037333  mov     r9d, r13d; int
0x180037336  xor     r8d, r8d; unsigned int
0x180037339  xor     edx, edx; int *
0x18003733b  mov     ecx, r12d; unsigned int
0x18003733e  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x180037343  mov     rbx, [rsp+410h+var_3A0]
0x180037348  cmp     byte ptr [rsi+1F84h], 0
0x18003734f  jz      short loc_180037372
0x180037351  lea     rcx, [rsi+0C68h]
0x180037358  call    ?TopOrDefault@?$CWatermarkStack@_N$0EA@$01$09@@QEBA_N_N@Z; CWatermarkStack<bool,64,2,10>::TopOrDefault(bool)
0x18003735d  test    al, al
0x18003735f  jz      short loc_180037372
0x180037361  mov     r8d, 1
0x180037367  mov     rdx, rsi
0x18003736a  mov     rcx, r14
0x18003736d  call    ?RenderProjectedShadows@CVisual@@QEAAXPEAVCDrawingContext@@W4Enum@ProjectedShadowDrawOrder@@@Z; CVisual::RenderProjectedShadows(CDrawingContext *,ProjectedShadowDrawOrder::Enum)
0x180037372  cmp     byte ptr [rbx], 0
0x180037375  jz      loc_1800375FC
0x18003737b  call    ?IsEtwEnabled@Backdrops@DwmDbg@@YA_NXZ; DwmDbg::Backdrops::IsEtwEnabled(void)
0x180037380  test    al, al
0x180037382  jnz     loc_180037C2C
0x180037388  lea     rcx, [rbp+310h+var_390]; this
0x18003738c  call    ??1NodeEffects@CDrawingContext@@QEAA@XZ; CDrawingContext::NodeEffects::~NodeEffects(void)
0x180037391  movaps  xmm11, [rsp+410h+var_90]
0x18003739a  mov     eax, edi
0x18003739c  movaps  xmm10, [rsp+410h+var_80]
0x1800373a5  movaps  xmm9, [rsp+410h+var_70]
0x1800373ae  movaps  xmm8, [rsp+410h+var_60]
0x1800373b7  movaps  xmm7, [rsp+410h+var_50]
0x1800373bf  movaps  xmm6, [rsp+410h+var_40]
0x1800373c7  mov     rcx, [rbp+310h+var_E0]
0x1800373ce  xor     rcx, rsp; StackCookie
0x1800373d1  call    __security_check_cookie
0x1800373d6  lea     r11, [rsp+410h+var_30]
0x1800373de  mov     rbx, [r11+58h]
0x1800373e2  movaps  xmm12, xmmword ptr [r11-70h]
0x1800373e7  movaps  xmm14, xmmword ptr [r11-90h]
0x1800373ef  mov     rsp, r11
0x1800373f2  pop     r15
0x1800373f4  pop     r14
0x1800373f6  pop     r13
0x1800373f8  pop     r12
0x1800373fa  pop     rdi
0x1800373fb  pop     rsi
0x1800373fc  pop     rbp
0x1800373fd  retn
0x1800373fe  mov     rax, [r15]
0x180037401  mov     rcx, r15
0x180037404  mov     rax, [rax+0C0h]
0x18003740b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037410  test    al, al
0x180037412  jz      loc_1800377A7
0x180037418  cmp     byte ptr [rsi+0B9h], 0
0x18003741f  jnz     loc_1800371F1
0x180037425  mov     rax, [r14+110h]
0x18003742c  sub     rax, [r14+108h]
0x180037433  sar     rax, 3
0x180037437  test    eax, eax
0x180037439  jnz     loc_180037DA5
0x18003743f  mov     rax, [r14+128h]
0x180037446  sub     rax, [r14+120h]
0x18003744d  sar     rax, 3
0x180037451  test    eax, eax
0x180037453  jnz     loc_180037DA5
0x180037459  lea     r12, [rsi+288h]
0x180037460  mov     ecx, [r12+18h]
0x180037465  mov     rax, [r12]
0x180037469  dec     ecx
0x18003746b  mov     r13, [rax+rcx*8]
0x18003746f  mov     rcx, r14
0x180037472  mov     rax, [r14]
0x180037475  mov     [rbp+310h+var_2C8], r13
0x180037479  mov     rax, [rax+0A0h]
0x180037480  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037485  mov     rbx, rax
0x180037488  test    rax, rax
0x18003748b  jz      short loc_180037496
0x18003748d  cmp     rax, r13
0x180037490  jnz     loc_180037728
0x180037496  mov     rbx, [rsp+410h+var_3A0]
0x18003749b  mov     byte ptr [rbx], 1
0x18003749e  test    byte ptr [r14+65h], 6
0x1800374a3  jnz     loc_18029CDAE
0x1800374a9  mov     r12d, [r14+60h]
0x1800374ad  mov     ebx, r12d
0x1800374b0  shr     ebx, 17h
0x1800374b3  and     ebx, 7Fh
0x1800374b6  jnz     loc_180038A35
0x1800374bc  mov     eax, [rsi+120h]
0x1800374c2  xorps   xmm0, xmm0
0x1800374c5  movups  [rbp+310h+var_2A0], xmm0
0x1800374c9  test    eax, eax
0x1800374cb  jz      loc_180039B34
0x1800374d1  lea     ecx, [rax-1]
0x1800374d4  imul    rcx, 44h ; 'D'
0x1800374d8  add     rcx, [rsi+118h]
0x1800374df  mov     rax, [rsi+1F08h]
0x1800374e6  lea     rdx, [rax+50h]
0x1800374ea  cmp     r14, [rax+48h]
0x1800374ee  jz      short loc_1800374F7
0x1800374f0  lea     rdx, [r14+90h]
0x1800374f7  lea     r8, [rbp+310h+var_170]
0x1800374fe  call    ??$Transform3DBoundsHelper@$00@CMILMatrix@@AEBAXAEBV?$TMil3DRect@MV?$TMilRect_@MUD2D_RECT_F@@UD3D_RECT_F@@UD2D_POINTANDSIZE_F@@UNotNeeded@RectUniqueness@@@@UD3D_RECT_F@@UMilPointAndSizeF@@UNotNeeded@RectUniqueness@@@@AEAV1@@Z; CMILMatrix::Transform3DBoundsHelper<1>(TMil3DRect<float,TMilRect_<float,D2D_RECT_F,D3D_RECT_F,D2D_POINTANDSIZE_F,RectUniqueness::NotNeeded>,D3D_RECT_F,MilPointAndSizeF,RectUniqueness::NotNeeded> const &,TMil3DRect<float,TMilRect_<float,D2D_RECT_F,D3D_RECT_F,D2D_POINTANDSIZE_F,RectUniqueness::NotNeeded>,D3D_RECT_F,MilPointAndSizeF,RectUniqueness::NotNeeded> &)
0x180037503  movss   xmm9, dword ptr [rbp+310h+var_170+8]
0x18003750c  movss   xmm6, dword ptr [rbp+310h+var_170]
0x180037514  comiss  xmm9, xmm6
0x180037518  movss   xmm7, dword ptr [rbp+310h+var_170+0Ch]
0x180037520  movss   xmm8, dword ptr [rbp+310h+var_170+4]
0x180037529  jbe     loc_1800375C6
0x18003752f  comiss  xmm7, xmm8
0x180037533  jbe     loc_1800375C6
0x180037539  mov     eax, [r14+60h]
0x18003753d  sar     eax, 8
0x180037540  test    al, 2
0x180037542  jnz     loc_180039A7D
0x180037548  test    al, 4
0x18003754a  jz      loc_180038866
0x180037550  movss   xmm0, cs:__real@3f000000
0x180037558  test    al, 8
0x18003755a  jnz     loc_180037F67
0x180037560  ucomiss xmm0, xmm14
0x180037564  jp      short loc_180037568
0x180037566  jz      short loc_1800375C6
0x180037568  movss   xmm1, dword ptr [rbp+310h+var_160+4]
0x180037570  subss   xmm6, xmm0
0x180037574  subss   xmm8, xmm0
0x180037579  addss   xmm9, xmm0
0x18003757e  addss   xmm7, xmm0
0x180037582  movss   xmm0, dword ptr [rbp+310h+var_160]
0x18003758a  addss   xmm0, xmm14
0x18003758f  addss   xmm1, xmm14
0x180037594  movss   dword ptr [rbp+310h+var_170], xmm6
0x18003759c  movss   dword ptr [rbp+310h+var_170+4], xmm8
0x1800375a5  movss   dword ptr [rbp+310h+var_170+8], xmm9
0x1800375ae  movss   dword ptr [rbp+310h+var_170+0Ch], xmm7
0x1800375b6  movss   dword ptr [rbp+310h+var_160], xmm0
0x1800375be  movss   dword ptr [rbp+310h+var_160+4], xmm1
0x1800375c6  mov     rcx, [rsi+2E8h]
0x1800375cd  cmp     rcx, [rsi+2E0h]
0x1800375d4  jnz     loc_180038807
0x1800375da  movdqa  xmm2, cs:__xmm@7f7fffff7f7fffffff7fffffff7fffff
0x1800375e2  movaps  xmm3, xmm2
0x1800375e5  movaps  xmm1, xmm2
0x1800375e8  movaps  xmm0, xmm2
0x1800375eb  shufps  xmm3, xmm2, 0FFh
  ... truncated ...
```
