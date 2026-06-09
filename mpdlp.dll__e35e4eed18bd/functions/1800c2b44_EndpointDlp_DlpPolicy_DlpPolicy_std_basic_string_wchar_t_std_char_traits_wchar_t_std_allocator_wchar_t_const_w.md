# EndpointDlp::DlpPolicy::DlpPolicy(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,web::json::value const &,bool)

- ea: `0x1800c2b44`
- end: `0x1800c783a`
- name: `??0DlpPolicy@EndpointDlp@@QEAA@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBVvalue@json@web@@_N@Z`
- size: `19702`
- prototype: `__int64 __fastcall(EndpointDlp::DlpPolicy *this)`
- caller_count: `1`
- callee_count: `104`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800673ac`

## callees

- `0x180004ccc`
- `0x180005c28`
- `0x1800249f0`
- `0x18002c150`
- `0x18002d608`
- `0x1800301a0`
- `0x1800323d0`
- `0x180033424`
- `0x180034420`
- `0x1800376e0`
- `0x180038450`
- `0x1800398a0`
- `0x18003ac68`
- `0x18003c940`
- `0x18004b3bc`
- `0x18004de90`
- `0x18005550c`
- `0x180055fa0`
- `0x180056cf0`
- `0x1800577cc`
- `0x180059d8c`
- `0x18005e088`
- `0x18005ee68`
- `0x18005ef40`
- `0x18005ef9c`
- `0x18005f008`
- `0x18005f084`
- `0x18005f134`
- `0x180061988`
- `0x180067288`
- `0x18006729c`
- `0x1800672b0`
- `0x180067334`
- `0x180067384`
- `0x1800677f8`
- `0x1800683fc`
- `0x18006ee30`
- `0x18006f3e4`
- `0x180070054`
- `0x180070110`
- `0x18007036c`
- `0x180070b3c`
- `0x180070cd4`
- `0x180070cf8`
- `0x180071c58`
- `0x180080a30`
- `0x180083a80`
- `0x180083b10`
- `0x180087964`
- `0x18008acf0`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800c3179`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800c3179`

## string_xrefs

- `0x1800c341d`: `OcrPathExclusions`
- `0x1800c346e`: `OcrPathExclusions`
- `0x1800c31be`: `PathExclusions`
- `0x1800c320f`: `PathExclusions`
- `0x1800c3297`: `NetworkPathExclusions`
- `0x1800c32e8`: `NetworkPathExclusions`
- `0x1800c305c`: `LastDlpPolicyUpdateTimeUtc`
- `0x1800c308a`: `LastDlpPolicyUpdateTimeUtc`
- `0x1800c47a1`: `TakeCloudAppDomainsFromSeparateConfig`
- `0x1800c47e5`: `TakeCloudAppDomainsFromSeparateConfig`
- `0x1800c3ef5`: `ShouldReplaceFile`
- `0x1800c3def`: `QuarantinePath`
- `0x1800c3ff3`: `FileReplacementText`
- `0x1800c5118`: `BlobUri`

## pseudocode

```c
// Hidden C++ exception states: #wind=168
EndpointDlp::DlpPolicy *__fastcall EndpointDlp::DlpPolicy::DlpPolicy(
        EndpointDlp::DlpPolicy *this,
        __int64 a2,
        __int64 a3,
        bool a4)
{
  EndpointDlp::DlpPolicy *v5; // r14
  int v6; // r13d
  _QWORD *v7; // rax
  __int64 size_of; // rax
  __int64 v9; // rax
  _QWORD *v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  _QWORD *v13; // rax
  __int64 v14; // rax
  void *v15; // rax
  const struct web::json::value *v16; // rax
  char v17; // si
  __int64 v18; // rax
  __int64 v19; // rax
  void *v20; // rax
  int v21; // r12d
  char v22; // bl
  const struct web::json::value *v23; // rax
  __int64 v24; // rax
  char v25; // bl
  const struct web::json::value *v26; // rax
  __int64 v27; // rax
  char has_boolean_field; // bl
  web::json::value *v29; // rax
  bool v30; // bl
  char v31; // bl
  const struct web::json::value *v32; // rax
  __int64 v33; // rax
  char v34; // bl
  const struct web::json::value *v35; // rax
  const struct web::json::array *v36; // rbx
  web::json::value *v37; // rbx
  web::json::value *v38; // rdi
  __int64 v39; // rax
  __int64 v40; // rax
  web::json::value *v41; // rax
  web::json::value *v42; // rax
  bool v43; // si
  char v44; // bl
  const struct web::json::value *v45; // rax
  const struct web::json::array *v46; // rbx
  web::json::value *v47; // rbx
  web::json::value *v48; // rdi
  __int64 v49; // rax
  __int64 v50; // rax
  char v51; // bl
  const struct web::json::value *v52; // rax
  const struct web::json::array *v53; // rbx
  web::json::value *v54; // rbx
  web::json::value *v55; // rdi
  __int64 v56; // rax
  __int64 v57; // rax
  char v58; // bl
  const struct web::json::value *v59; // rax
  web::json::value *v60; // rax
  char v61; // bl
  web::json::value *v62; // rax
  int v63; // r12d
  web::json::value *v64; // rax
  char v65; // bl
  __int64 v66; // rax
  void *v67; // rax
  int v68; // r12d
  web::json::value *v69; // rax
  char v70; // bl
  web::json::value *v71; // rax
  web::json::value *v72; // rax
  char v73; // bl
  __int64 v74; // rax
  void *v75; // rax
  char v76; // bl
  const struct web::json::value *v77; // rax
  const struct web::json::array *v78; // rax
  web::json::value *v79; // rbx
  web::json::value *v80; // rdi
  __int64 v81; // rax
  __int64 v82; // rax
  char v83; // bl
  const struct web::json::value *v84; // rax
  web::json::value *v85; // rax
  web::json::number *v86; // rax
  unsigned int v87; // eax
  char v88; // bl
  const struct web::json::value *v89; // rax
  const struct web::json::array *v90; // rax
  web::json::value *v91; // rbx
  web::json::value *v92; // rdi
  web::json::value *v93; // rax
  web::json::number *v94; // rax
  __int64 v95; // rax
  __int64 v96; // rax
  __int64 v97; // r8
  char IsPrefix; // si
  int v99; // esi
  int v100; // esi
  char v101; // bl
  const struct web::json::value *v102; // rax
  char v103; // bl
  const struct web::json::value *v104; // rax
  char *v105; // rdi
  __int64 v106; // rbx
  char *v107; // r8
  __int64 v108; // r14
  char v109; // bl
  const struct web::json::value *v110; // rax
  char v111; // bl
  const struct web::json::value *v112; // rax
  char v113; // bl
  web::json::value *v114; // rax
  char v115; // bl
  const struct web::json::value *v116; // rax
  void *v117; // rax
  char v118; // bl
  web::json::value *v119; // rax
  int v120; // ebx
  char v121; // bl
  const struct web::json::value *v122; // rax
  void *v123; // rax
  char v124; // bl
  const struct web::json::value *v125; // rax
  void *v126; // rax
  char v127; // bl
  const struct web::json::value *v128; // rax
  void *v129; // rax
  char v130; // bl
  const struct web::json::value *v131; // rax
  void *v132; // rax
  int v133; // r12d
  web::json::value *v134; // rax
  char v135; // bl
  const struct web::json::value *v136; // rax
  char v137; // bl
  const struct web::json::value *v138; // rax
  char v139; // bl
  const struct web::json::value *v140; // rax
  const struct web::json::array *v141; // rax
  web::json::value *v142; // rbx
  web::json::value *v143; // rdi
  __int64 v144; // rax
  __int64 v145; // rax
  __int64 v146; // rax
  __int64 v147; // rax
  __int64 v148; // rax
  EndpointDlp::DlpPolicy *v149; // rcx
  web::json::value *v150; // rax
  char v151; // bl
  web::json::value *v152; // rax
  web::json::number *v153; // rax
  unsigned int v154; // edx
  EndpointDlp::DlpPolicy::DeviceIdentifiersHint *v155; // rdi
  EndpointDlp::DlpPolicy::DeviceIdentifiersHint *v156; // rbx
  int v157; // r12d
  web::json::value *v158; // rax
  char v159; // bl
  const struct web::json::value *v160; // rax
  web::json::value *v161; // rax
  const struct web::json::value *v162; // rax
  const struct web::json::array *v163; // rax
  web::json::value *v164; // rsi
  web::json::value *v165; // r14
  __m128i si128; // xmm8
  bool v167; // bl
  __int64 v168; // rax
  void *v169; // rax
  __int128 *v170; // rbx
  _QWORD *v171; // rax
  __int128 *v172; // rdx
  char v173; // al
  char v174; // cl
  __int64 v175; // rax
  __int64 v176; // rax
  __int64 v177; // rdi
  __int64 v178; // rbx
  _QWORD *v179; // rax
  char v180; // al
  char v181; // cl
  __int64 v182; // rax
  __int64 v183; // rax
  __int64 v184; // r11
  EndpointDlp::DlpPolicy *v185; // r14
  char v186; // bl
  const struct web::json::value *v187; // rax
  const struct web::json::array *v188; // rax
  const struct web::json::value *v189; // rbx
  web::json::value *v190; // rdi
  __int64 v191; // rax
  char v192; // bl
  const struct web::json::value *v193; // rax
  __int64 v194; // rax
  __int64 v195; // rax
  __int64 v196; // rax
  EndpointDlp::DlpPolicy *v197; // rbx
  char v198; // si
  const struct web::json::array *v199; // rax
  _QWORD *v200; // r14
  _QWORD *i; // rdi
  web::json::value *v202; // rax
  __int64 v203; // rax
  void *v204; // rax
  int v205; // r12d
  web::json::value *v206; // rax
  __int64 v207; // rax
  void *v208; // rax
  int v209; // r12d
  web::json::value *v210; // rax
  __int64 v211; // rax
  void *v212; // rax
  web::json::value *v213; // rax
  web::json::value *v214; // rax
  const struct web::json::array *v215; // rax
  web::json::value *v216; // rbx
  web::json::value *v217; // rsi
  EndpointDlp::DlpPolicy *v218; // r14
  web::json::value *v219; // rax
  __int64 v220; // rax
  void *v221; // rax
  int v222; // r13d
  web::json::value *v223; // rax
  __int64 v224; // rax
  void *v225; // rax
  int v226; // r13d
  web::json::value *v227; // rax
  web::json::value *v228; // rax
  web::json::value *v229; // rax
  web::json::value *v230; // rax
  _QWORD *v231; // rax
  struct EndpointDlp::TraceLoggingProvider *v232; // rax
  int v233; // r8d
  int v234; // r9d
  _DWORD *v235; // rcx
  _QWORD *v236; // rax
  struct EndpointDlp::TraceLoggingProvider *v237; // rax
  int v238; // r8d
  int v239; // r9d
  _DWORD *v240; // rcx
  char v241; // bl
  const struct web::json::value *v242; // rax
  const struct web::json::array *v243; // rax
  web::json::value *v244; // rbx
  web::json::value *v245; // rdi
  __int64 v246; // rax
  __int64 v247; // rax
  char v248; // si
  const struct web::json::value *v249; // rax
  __int64 v250; // rax
  __int64 v251; // rax
  char v252; // al
  __int128 v253; // xmm7
  char v254; // si
  const struct web::json::value *v255; // rax
  __int64 v256; // rax
  __int64 v257; // rax
  char v258; // al
  __m128i v259; // xmm6
  __int64 v260; // rcx
  char v261; // bl
  const struct web::json::value *v262; // rax
  char v263; // bl
  const struct web::json::value *v264; // rax
  __int64 v265; // rax
  __int64 v266; // rax
  __int64 v267; // rax
  EndpointDlp::DlpPolicy *v268; // r12
  char v269; // di
  const struct web::json::array *v270; // rax
  _QWORD *v271; // rbx
  _QWORD *v272; // r14
  web::json::value *v273; // rax
  char v274; // si
  struct EndpointDlp::TraceLoggingProvider *v275; // rax
  int v276; // ecx
  int v277; // r8d
  int v278; // r9d
  __int64 v279; // rax
  __int64 v280; // rax
  int v281; // r13d
  web::json::value *v282; // rax
  char v283; // si
  web::json::value *v284; // rax
  web::json::value *v285; // rax
  web::json::value *v286; // rax
  const struct web::json::array *v287; // rax
  web::json::value *v288; // rdi
  web::json::value *v289; // rsi
  __int64 v290; // rax
  __int64 v291; // rax
  struct EndpointDlp::TraceLoggingProvider *v292; // rax
  int v293; // ecx
  int v294; // r8d
  int v295; // r9d
  __int64 v296; // rax
  struct EndpointDlp::TraceLoggingProvider *v297; // rax
  int v298; // ecx
  int v299; // r8d
  int v300; // r9d
  void *v301; // rax
  struct EndpointDlp::TraceLoggingProvider *v302; // rax
  int v303; // ecx
  int v304; // r8d
  int v305; // r9d
  __int64 v306; // rcx
  __int64 v307; // rdi
  char has_field; // bl
  const struct web::json::value *v309; // rax
  char v310; // bl
  const struct web::json::value *v311; // rax
  void *v312; // rax
  char v313; // bl
  const struct web::json::value *v314; // rax
  void *v315; // rax
  char v316; // bl
  const struct web::json::value *v317; // rax
  struct EndpointDlp::TraceLoggingProvider *v319; // rax
  _DWORD *v320; // rbx
  struct EndpointDlp::TraceLoggingProvider *v321; // rax
  _DWORD *v322; // rbx
  struct EndpointDlp::TraceLoggingProvider *v323; // rax
  _DWORD *v324; // rbx
  struct EndpointDlp::TraceLoggingProvider *v325; // rax
  _DWORD *v326; // rbx
  struct EndpointDlp::TraceLoggingProvider *v327; // rax
  _DWORD *v328; // rbx
  struct EndpointDlp::TraceLoggingProvider *v329; // rax
  _DWORD *v330; // rbx
  struct EndpointDlp::TraceLoggingProvider *v331; // rax
  _DWORD *v332; // rbx
  struct EndpointDlp::TraceLoggingProvider *v333; // rax
  _DWORD *v334; // rbx
  struct EndpointDlp::TraceLoggingProvider *v335; // rax
  _DWORD *v336; // rbx
  const char *v337; // [rsp+30h] [rbp-758h]
  char v338; // [rsp+40h] [rbp-748h]
  char v339; // [rsp+40h] [rbp-748h]
  char v340; // [rsp+40h] [rbp-748h]
  char v341; // [rsp+40h] [rbp-748h]
  char v342; // [rsp+40h] [rbp-748h]
  char v343; // [rsp+40h] [rbp-748h]
  char v344; // [rsp+40h] [rbp-748h]
  char v345; // [rsp+40h] [rbp-748h]
  bool v346; // [rsp+40h] [rbp-748h]
  int v347; // [rsp+44h] [rbp-744h]
  unsigned int v348; // [rsp+44h] [rbp-744h]
  int v349; // [rsp+44h] [rbp-744h]
  _BYTE v350[32]; // [rsp+48h] [rbp-740h] BYREF
  int v351; // [rsp+68h] [rbp-720h]
  EndpointDlp::DlpPolicy *v352; // [rsp+70h] [rbp-718h] BYREF
  bool v353; // [rsp+78h] [rbp-710h]
  const wchar_t *v354; // [rsp+80h] [rbp-708h] BYREF
  EndpointDlp::DlpPolicy *v355; // [rsp+88h] [rbp-700h]
  void *v356; // [rsp+90h] [rbp-6F8h] BYREF
  char *v357; // [rsp+98h] [rbp-6F0h] BYREF
  void *v358; // [rsp+A0h] [rbp-6E8h] BYREF
  _QWORD v359[2]; // [rsp+A8h] [rbp-6E0h] BYREF
  char *v360; // [rsp+B8h] [rbp-6D0h]
  char *v361; // [rsp+C0h] [rbp-6C8h]
  void *v362; // [rsp+C8h] [rbp-6C0h]
  void *v363; // [rsp+D0h] [rbp-6B8h]
  char *v364; // [rsp+D8h] [rbp-6B0h]
  void *v365; // [rsp+E0h] [rbp-6A8h]
  char *v366; // [rsp+E8h] [rbp-6A0h] BYREF
  const std::invalid_argument *v367; // [rsp+F8h] [rbp-690h] BYREF
  const std::out_of_range *v368; // [rsp+100h] [rbp-688h] BYREF
  const std::exception *v369; // [rsp+108h] [rbp-680h] BYREF
  web::json::json_exception *v370; // [rsp+110h] [rbp-678h] BYREF
  const std::exception *v371; // [rsp+118h] [rbp-670h] BYREF
  web::json::json_exception *v372; // [rsp+120h] [rbp-668h] BYREF
  std::exception *v373; // [rsp+128h] [rbp-660h] BYREF
  web::json::json_exception *v374; // [rsp+130h] [rbp-658h] BYREF
  std::exception *v375; // [rsp+138h] [rbp-650h] BYREF
  _BYTE v376[32]; // [rsp+140h] [rbp-648h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+160h] [rbp-628h] BYREF
  const wchar_t *v378; // [rsp+168h] [rbp-620h] BYREF
  __int64 v379; // [rsp+170h] [rbp-618h] BYREF
  _BYTE v380[32]; // [rsp+178h] [rbp-610h] BYREF
  web::json::value *v381[2]; // [rsp+198h] [rbp-5F0h] BYREF
  __int64 v382; // [rsp+1A8h] [rbp-5E0h]
  void *v383[2]; // [rsp+1B8h] [rbp-5D0h] BYREF
  _BYTE Src[40]; // [rsp+1C8h] [rbp-5C0h] BYREF
  __int128 v385; // [rsp+1F0h] [rbp-598h] BYREF
  __m128i v386; // [rsp+200h] [rbp-588h]
  __int16 v387; // [rsp+210h] [rbp-578h]
  char v388; // [rsp+212h] [rbp-576h]
  int v389; // [rsp+213h] [rbp-575h]
  char v390; // [rsp+217h] [rbp-571h]
  __int64 v391; // [rsp+218h] [rbp-570h] BYREF
  __int128 v392; // [rsp+220h] [rbp-568h]
  void *v393[2]; // [rsp+230h] [rbp-558h] BYREF
  void *v394[2]; // [rsp+250h] [rbp-538h] BYREF
  __m128i v395; // [rsp+260h] [rbp-528h]
  __int128 v396; // [rsp+270h] [rbp-518h] BYREF
  __m128i v397; // [rsp+280h] [rbp-508h]
  void *v398[4]; // [rsp+290h] [rbp-4F8h] BYREF
  void *v399[2]; // [rsp+2B0h] [rbp-4D8h] BYREF
  __int64 v400; // [rsp+2C0h] [rbp-4C8h]
  void *v401[4]; // [rsp+2C8h] [rbp-4C0h] BYREF
  bool v402[8]; // [rsp+2E8h] [rbp-4A0h] BYREF
  _BYTE v403[16]; // [rsp+2F0h] [rbp-498h] BYREF
  _QWORD v404[4]; // [rsp+300h] [rbp-488h] BYREF
  _OWORD v405[2]; // [rsp+320h] [rbp-468h] BYREF
  _OWORD v406[2]; // [rsp+340h] [rbp-448h] BYREF
  __int16 v407; // [rsp+360h] [rbp-428h]
  _BYTE v408[32]; // [rsp+370h] [rbp-418h] BYREF
  _BYTE v409[32]; // [rsp+390h] [rbp-3F8h] BYREF
  char v410[32]; // [rsp+3B0h] [rbp-3D8h] BYREF
  char v411[8]; // [rsp+3D0h] [rbp-3B8h] BYREF
  EndpointDlp::DlpPolicy::ConditionalAppInfo *v412; // [rsp+3D8h] [rbp-3B0h]
  EndpointDlp::DlpPolicy::ConditionalAppInfo *v413; // [rsp+3E0h] [rbp-3A8h]
  _BYTE v414[800]; // [rsp+3F0h] [rbp-398h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+788h] [rbp+0h]

  v5 = this;
  v352 = this;
  v355 = this;
  v353 = a4;
  v6 = 0;
  v351 = 0;
  std::wstring::wstring(this, a2);
  *((_OWORD *)v5 + 2) = 0;
  *((_QWORD *)v5 + 6) = 0;
  *((_QWORD *)v5 + 7) = 7;
  *((_WORD *)v5 + 16) = 0;
  *((_OWORD *)v5 + 4) = 0;
  *((_QWORD *)v5 + 10) = 0;
  *((_QWORD *)v5 + 11) = 7;
  *((_WORD *)v5 + 32) = 0;
  v362 = (char *)v5 + 112;
  v365 = (char *)v5 + 112;
  *((_OWORD *)v5 + 7) = 0;
  *((_QWORD *)v5 + 16) = 0;
  *((_QWORD *)v5 + 17) = 7;
  *((_WORD *)v5 + 56) = 0;
  v363 = (char *)v5 + 144;
  v398[0] = (char *)v5 + 144;
  *((_OWORD *)v5 + 9) = 0;
  *((_QWORD *)v5 + 20) = 0;
  *((_QWORD *)v5 + 21) = 7;
  *((_WORD *)v5 + 72) = 0;
  *((_WORD *)v5 + 89) = 0;
  *((_DWORD *)v5 + 45) = 0;
  v357 = (char *)v5 + 184;
  *((_QWORD *)v5 + 23) = 0;
  v366 = (char *)v5 + 192;
  *((_QWORD *)v5 + 24) = 0;
  v359[0] = (char *)v5 + 200;
  *((_QWORD *)v5 + 25) = 0;
  v364 = (char *)v5 + 208;
  ((void (*)(void))std::set<std::wstring,EndpointDlp::Common::wstringOrdinalCompareInsensitive,std::allocator<std::wstring>>::set<std::wstring,EndpointDlp::Common::wstringOrdinalCompareInsensitive,std::allocator<std::wstring>>)();
  v404[0] = (char *)v5 + 224;
  ((void (*)(void))std::set<std::wstring,EndpointDlp::Common::wstringOrdinalCompareInsensitive,std::allocator<std::wstring>>::set<std::wstring,EndpointDlp::Common::wstringOrdinalCompareInsensitive,std::allocator<std::wstring>>)();
  *(_QWORD *)&v396 = (char *)v5 + 240;
  ((void (*)(void))std::set<std::wstring,EndpointDlp::Common::wstringOrdinalCompareInsensitive,std::allocator<std::wstring>>::set<std::wstring,EndpointDlp::Common::wstringOrdinalCompareInsensitive,std::allocator<std::wstring>>)();
  v360 = (char *)v5 + 256;
  ((void (*)(void))std::set<std::wstring,EndpointDlp::Common::wstringOrdinalCompareInsensitive,std::allocator<std::wstring>>::set<std::wstring,EndpointDlp::Common::wstringOrdinalCompareInsensitive,std::allocator<std::wstring>>)();
  v361 = (char *)v5 + 272;
  ((void (*)(void))std::set<std::wstring,EndpointDlp::Common::wstringOrdinalCompareInsensitive,std::allocator<std::wstring>>::set<std::wstring,EndpointDlp::Common::wstringOrdinalCompareInsensitive,std::allocator<std::wstring>>)();
  v401[0] = (char *)v5 + 288;
  v356 = (char *)v5 + 288;
  *((_OWORD *)v5 + 18) = 0;
  *((_QWORD *)v5 + 38) = 0;
  *((_QWORD *)v5 + 39) = 7;
  *((_WORD *)v5 + 144) = 0;
  *((_QWORD *)v5 + 40) = 0;
  *((_QWORD *)v5 + 41) = 0;
  v7 = operator new(0xB8u);
  *v7 = v7;
  v7[1] = v7;
  v7[2] = v7;
  *((_WORD *)v7 + 12) = 257;
  *((_QWORD *)v5 + 40) = v7;
  *((_QWORD *)v5 + 42) = 0;
  *((_QWORD *)v5 + 43) = 0;
  *((_QWORD *)v5 + 42) = std::_Tree_node<std::pair<std::wstring const,std::vector<std::wstring>>,void *>::_Buyheadnode<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::vector<std::wstring>>,void *>>>();
  *((_QWORD *)v5 + 44) = 0;
  *((_QWORD *)v5 + 45) = 0;
  size_of = std::_Get_size_of_n<96>(1);
  v9 = std::_Allocate<16,std::_Default_allocate_traits>(size_of);
  *(_QWORD *)v9 = v9;
  *(_QWORD *)(v9 + 8) = v9;
  *(_QWORD *)(v9 + 16) = v9;
  *(_WORD *)(v9 + 24) = 257;
  *((_QWORD *)v5 + 44) = v9;
  *((_DWORD *)v5 + 92) = -2;
  *((_DWORD *)v5 + 93) = -2;
  *((_DWORD *)v5 + 94) = 0;
  *((_QWORD *)v5 + 48) = 0;
  *((_QWORD *)v5 + 49) = 0;
  *((_QWORD *)v5 + 48) = std::_Tree_node<std::pair<std::wstring const,enum EndpointDlp::DlpPolicy::DomainAccessType>,void *>::_Buyheadnode<std::allocator<std::_Tree_node<std::pair<std::wstring const,enum EndpointDlp::DlpPolicy::DomainAccessType>,void *>>>();
  *((_QWORD *)v5 + 50) = 0;
  *((_QWORD *)v5 + 51) = 0;
  *((_QWORD *)v5 + 50) = std::_Tree_node<std::pair<std::wstring const,enum EndpointDlp::DlpPolicy::DomainAccessType>,void *>::_Buyheadnode<std::allocator<std::_Tree_node<std::pair<std::wstring const,enum EndpointDlp::DlpPolicy::DomainAccessType>,void *>>>();
  *(_DWORD *)((char *)v5 + 417) = 0;
  *((_BYTE *)v5 + 421) = 0;
  *((_DWORD *)v5 + 111) = 2;
  v358 = (char *)v5 + 448;
  std::wstring::wstring((char *)v5 + 448, L"6abb5bf8-7ae6-4f97-9c9a-9fcb60c0f230:00573cd5-48f0-4fc1-8ea0-4ee0e749f9b7");
  std::wstring::wstring((char *)v5 + 480, L"6abb5bf8-7ae6-4f97-9c9a-9fcb60c0f230:6b2c3c43-f1fd-4949-97e8-f93e3c3a91e4");
  v394[0] = (char *)v5 + 512;
  std::wstring::wstring((char *)v5 + 512, L"6abb5bf8-7ae6-4f97-9c9a-9fcb60c0f230:3ce7845d-0521-43c9-befb-546dbbbafc2b");
  v399[0] = (char *)v5 + 544;
  std::wstring::wstring((char *)v5 + 544, L"6abb5bf8-7ae6-4f97-9c9a-9fcb60c0f230:2e2ec439-b89b-41d0-9851-a86388eb3bbd");
  v393[0] = (char *)v5 + 576;
  std::wstring::wstring((char *)v5 + 576, L"6abb5bf8-7ae6-4f97-9c9a-9fcb60c0f230:3cfeb5f6-aba4-40e7-b5be-3b4e13c81d96");
  v383[0] = (char *)v5 + 608;
  std::wstring::wstring((char *)v5 + 608, L"6abb5bf8-7ae6-4f97-9c9a-9fcb60c0f230:16083bd6-ea78-4291-8115-9b6748933dd0");
  *((_QWORD *)v5 + 81) = 0;
  *((_QWORD *)v5 + 82) = 0;
  v10 = operator new(0x360u);
  *v10 = v10;
  v10[1] = v10;
  v10[2] = v10;
  *((_WORD *)v10 + 12) = 257;
  *((_QWORD *)v5 + 81) = v10;
  *((_QWORD *)v5 + 83) = 0;
  *((_QWORD *)v5 + 84) = 0;
  v11 = std::_Get_size_of_n<80>(1);
  v12 = std::_Allocate<16,std::_Default_allocate_traits>(v11);
  *(_QWORD *)v12 = v12;
  *(_QWORD *)(v12 + 8) = v12;
  *(_QWORD *)(v12 + 16) = v12;
  *(_WORD *)(v12 + 24) = 257;
  *((_QWORD *)v5 + 83) = v12;
  std::map<std::wstring,std::vector<std::wstring>,EndpointDlp::Common::wstringCompareInsensitive,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>>::map<std::wstring,std::vector<std::wstring>,EndpointDlp::Common::wstringCompareInsensitive,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>>((char *)v5 + 680);
  std::map<std::wstring,std::vector<std::wstring>,EndpointDlp::Common::wstringCompareInsensitive,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>>::map<std::wstring,std::vector<std::wstring>,EndpointDlp::Common::wstringCompareInsensitive,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>>((char *)v5 + 696);
  *((_QWORD *)v5 + 89) = 0;
  *((_QWORD *)v5 + 90) = 0;
  v13 = operator new(0x58u);
  *v13 = v13;
  v13[1] = v13;
  v13[2] = v13;
  *((_WORD *)v13 + 12) = 257;
  *((_QWORD *)v5 + 89) = v13;
  *(_OWORD *)((char *)v5 + 728) = 0;
  *((_QWORD *)v5 + 93) = 0;
  *((_QWORD *)v5 + 94) = 7;
  *((_WORD *)v5 + 364) = 0;
  *(_OWORD *)((char *)v5 + 760) = 0;
  *((_QWORD *)v5 + 97) = 0;
  *((_QWORD *)v5 + 98) = 7;
  *((_WORD *)v5 + 380) = 0;
  *((_QWORD *)v5 + 99) = 0;
  *((_QWORD *)v5 + 100) = 0;
  *((_QWORD *)v5 + 99) = std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>::_Buyheadnode<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>();
  std::set<std::wstring,EndpointDlp::Common::wstringOrdinalCompareInsensitive,std::allocator<std::wstring>>::set<std::wstring,EndpointDlp::Common::wstringOrdinalCompareInsensitive,std::allocator<std::wstring>>((char *)v5 + 808);
  std::set<std::wstring,EndpointDlp::Common::wstringOrdinalCompareInsensitive,std::allocator<std::wstring>>::set<std::wstring,EndpointDlp::Common::wstringOrdinalCompareInsensitive,std::allocator<std::wstring>>((char *)v5 + 824);
  *((_QWORD *)v5 + 105) = 0;
  std::set<std::wstring,EndpointDlp::Common::wstringOrdinalCompareInsensitive,std::allocator<std::wstring>>::set<std::wstring,EndpointDlp::Common::wstringOrdinalCompareInsensitive,std::allocator<std::wstring>>((char *)v5 + 848);
  std::set<std::wstring,EndpointDlp::Common::wstringOrdinalCompareInsensitive,std::allocator<std::wstring>>::set<std::wstring,EndpointDlp::Common::wstringOrdinalCompareInsensitive,std::allocator<std::wstring>>((char *)v5 + 864);
  *((_QWORD *)v5 + 110) = 0;
  *((_QWORD *)v5 + 111) = 0;
  *((_QWORD *)v5 + 112) = 0;
  *((_BYTE *)v5 + 904) = 0;
  *(_WORD *)((char *)v5 + 907) = 0;
  std::wstring::wstring(Src, L"AadTenantId");
  v14 = web::json::value::at(a3, Src);
  v15 = (void *)web::json::value::as_string(v14);
  std::wstring::operator=((char *)v5 + 32, v15);
  std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(Src);
  v379 = 0;
  std::wstring::wstring(v376, L"Policy");
  v16 = (const struct web::json::value *)web::json::value::at(a3, v376);
  web::json::value::value((web::json::value *)&v379, v16);
  std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v376);
  std::wstring::wstring(v381, L"LastDlpPolicyUpdateTimeUtc");
  if ( (unsigned __int8)web::json::value::has_string_field(&v379, v381) )
  {
    std::wstring::wstring(Src, L"LastDlpPolicyUpdateTimeUtc");
    v17 = 1;
    v18 = web::json::value::at(&v379, Src);
    v19 = web::json::value::as_string(v18);
    v20 = (void *)std::wstring::wstring(v380, v19);
    v21 = 3;
  }
  else
  {
    v20 = (void *)std::wstring::wstring(v350, &qword_18025C818);
    v21 = 4;
    v17 = 1;
  }
  v347 = v21;
  std::wstring::operator=((char *)v5 + 64, v20);
  if ( (v21 & 4) != 0 )
  {
    v21 &= ~4u;
    v347 = v21;
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v350);
  }
  if ( (v21 & 2) != 0 )
  {
    v21 &= ~2u;
    v347 = v21;
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v380);
  }
  if ( (v21 & 1) != 0 )
  {
    v21 &= ~1u;
    v347 = v21;
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(Src);
  }
  std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v381);
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  *((struct _FILETIME *)v5 + 12) = SystemTimeAsFileTime;
  if ( *((_QWORD *)v5 + 10) )
  {
    try
    {
      *((_QWORD *)v5 + 12) = std::stoull((wchar_t *)v5 + 32);
    }
    catch ( const std::invalid_argument *v367 )
    {
      v319 = EndpointDlp::TraceLoggingProvider::Instance();
      v320 = *(_DWORD **)v319;
      if ( **(_DWORD **)v319 > 2u )
      {
        v378 = (const wchar_t *)(*(__int64 (__fastcall **)(const std::invalid_argument *))(*(_QWORD *)v367 + 8LL))(v367);
        v354 = L"Failed to parse LastDlpPolicyUpdateTimeUtc string into u64";
        LODWORD(v352) = -2147418113;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>>(
          (int)v320,
          (int)&word_1802C8452,
          (__int64)&v352,
          (__int64)&v354,
          (__int64)&v378);
      }
      v5 = v355;
      v17 = 1;
      v21 = v347;
      v6 = v351;
      v352 = v355;
    }
    catch ( const std::out_of_range *v368 )
    {
      v321 = EndpointDlp::TraceLoggingProvider::Instance();
      v322 = *(_DWORD **)v321;
      if ( **(_DWORD **)v321 > 2u )
      {
        v354 = (const wchar_t *)(*(__int64 (__fastcall **)(const std::out_of_range *))(*(_QWORD *)v368 + 8LL))(v368);
        v378 = L"LastDlpPolicyUpdateTimeUtc out of range";
        LODWORD(v352) = -2147418113;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>>(
          (int)v322,
          (int)&word_1802C8A0E,
          (__int64)&v352,
          (__int64)&v378,
          (__int64)&v354);
      }
      v5 = v355;
      v17 = 1;
      v21 = v347;
      v6 = v351;
      v352 = v355;
    }
    catch ( const std::exception *v369 )
    {
      v323 = EndpointDlp::TraceLoggingProvider::Instance();
      v324 = *(_DWORD **)v323;
      if ( **(_DWORD **)v323 > 2u )
      {
        v354 = (const wchar_t *)(*(__int64 (__fastcall **)(const std::exception *))(*(_QWORD *)v369 + 8LL))(v369);
        v378 = L"Failed to parse LastDlpPolicyUpdateTimeUtc string into u64";
        LODWORD(v352) = -2147418113;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>>(
          (int)v324,
          (int)&byte_1802C8611,
          (__int64)&v352,
          (__int64)&v378,
          (__int64)&v354);
      }
      v5 = v355;
      v17 = 1;
      v21 = v347;
      v6 = v351;
      v352 = v355;
    }
  }
  std::wstring::wstring(Src, L"PathExclusions");
  v22 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v379 + 8LL))(v379, Src);
  std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(Src);
  if ( v22 )
  {
    SystemTimeAsFileTime = 0;
    std::wstring::wstring(Src, L"PathExclusions");
    v23 = (const struct web::json::value *)web::json::value::at(&v379, Src);
    web::json::value::value((web::json::value *)&SystemTimeAsFileTime, v23);
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(Src);
    v24 = std::make_unique<EndpointDlp::DlpExclusion,web::json::value &,0>(&v354, &SystemTimeAsFileTime);
    std::unique_ptr<EndpointDlp::DlpExclusion>::operator=<std::default_delete<EndpointDlp::DlpExclusion>,0>(v357, v24);
    std::unique_ptr<EndpointDlp::DlpExclusion>::~unique_ptr<EndpointDlp::DlpExclusion>(&v354);
    std::unique_ptr<web::json::details::_Null>::~unique_ptr<web::json::details::_Null>(&SystemTimeAsFileTime);
  }
  std::wstring::wstring(Src, L"NetworkPathExclusions");
  v25 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v379 + 8LL))(v379, Src);
  std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(Src);
  if ( v25 )
  {
    SystemTimeAsFileTime = 0;
    std::wstring::wstring(Src, L"NetworkPathExclusions");
    v26 = (const struct web::json::value *)web::json::value::at(&v379, Src);
    web::json::value::value((web::json::value *)&SystemTimeAsFileTime, v26);
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(Src);
    v27 = std::make_unique<EndpointDlp::DlpExclusion,web::json::value &,0>(&v357, &SystemTimeAsFileTime);
    std::unique_ptr<EndpointDlp::DlpExclusion>::operator=<std::default_delete<EndpointDlp::DlpExclusion>,0>(
      v359[0],
      v27);
    std::unique_ptr<EndpointDlp::DlpExclusion>::~unique_ptr<EndpointDlp::DlpExclusion>(&v357);
    std::unique_ptr<web::json::details::_Null>::~unique_ptr<web::json::details::_Null>(&SystemTimeAsFileTime);
  }
  EndpointDlp::DlpPolicy::ProcessExtExclusions(v5, (const struct web::json::value *)&v379);
  *((_BYTE *)v5 + 177) = (unsigned int)EndpointDlp::Common::OsVersionInfo::GetProductType() - 2 <= 1;
  std::wstring::wstring(Src, L"IsServerDlpEnabled");
  has_boolean_field = web::json::value::has_boolean_field(&v379, Src);
  std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(Src);
  if ( has_boolean_field )
  {
    std::wstring::wstring(Src, L"IsServerDlpEnabled");
    v29 = (web::json::value *)web::json::value::at(&v379, Src);
    v30 = web::json::value::as_bool(v29);
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(Src);
    if ( v30 )
      *((_BYTE *)v5 + 177) = 0;
  }
  std::wstring::wstring(Src, L"OcrPathExclusions");
  v31 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v379 + 8LL))(v379, Src);
  std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(Src);
  if ( v31 )
  {
    SystemTimeAsFileTime = 0;
    std::wstring::wstring(Src, L"OcrPathExclusions");
    v32 = (const struct web::json::value *)web::json::value::at(&v379, Src);
    web::json::value::value((web::json::value *)&SystemTimeAsFileTime, v32);
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(Src);
    v33 = std::make_unique<EndpointDlp::DlpExclusion,web::json::value &,0>(v359, &SystemTimeAsFileTime);
    std::unique_ptr<EndpointDlp::DlpExclusion>::operator=<std::default_delete<EndpointDlp::DlpExclusion>,0>(v366, v33);
    std::unique_ptr<EndpointDlp::DlpExclusion>::~unique_ptr<EndpointDlp::DlpExclusion>(v359);
    std::unique_ptr<web::json::details::_Null>::~unique_ptr<web::json::details::_Null>(&SystemTimeAsFileTime);
  }
  std::wstring::wstring(Src, L"UnallowedApplications");
  v34 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v379 + 8LL))(v379, Src);
  std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(Src);
  if ( v34 )
  {
    SystemTimeAsFileTime = 0;
    std::wstring::wstring(Src, L"UnallowedApplications");
    v35 = (const struct web::json::value *)web::json::value::at(&v379, Src);
    web::json::value::value((web::json::value *)&SystemTimeAsFileTime, v35);
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(Src);
    if ( !web::json::value::is_null((web::json::value *)&SystemTimeAsFileTime) )
    {
      *(_OWORD *)v381 = 0;
      v382 = 0;
      v36 = web::json::value::as_array((web::json::value *)&SystemTimeAsFileTime);
      *(_OWORD *)v381 = 0;
      v382 = 0;
      if ( (__int64)(*((_QWORD *)v36 + 1) - *(_QWORD *)v36) >> 3 )
      {
        std::vector<wchar_t const *>::_Buy_nonzero(v381);
        v378 = (const wchar_t *)v381;
        v381[1] = (web::json::value *)std::_Uninitialized_copy<web::json::value *,web::json::value *,std::allocator<web::json::value>>(*(struct web::json::value **)v36);
        v378 = 0;
        std::_Tidy_guard<std::vector<web::json::value>>::~_Tidy_guard<std::vector<web::json::value>>(&v378);
      }
      v37 = v381[0];
      v38 = v381[1];
      while ( v37 != v38 )
      {
        std::wstring::wstring(&v385, L"ProcessName");
        v39 = web::json::value::at(v37, &v385);
        v40 = web::json::value::as_string(v39);
        std::wstring::wstring(Src, v40);
        std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(&v385);
        std::_Tree<std::_Tset_traits<std::wstring,EndpointDlp::Common::wstringOrdinalCompareInsensitive,std::allocator<std::wstring>,0>>::insert<0,0>(
          v364,
          &v366,
          Src);
        std::wstring::wstring(v350, L"FfeEnabled");
        v21 |= 8u;
        if ( !(*(unsigned __int8 (__fastcall **)(_QWORD, _BYTE *))(**(_QWORD **)v37 + 8LL))(*(_QWORD *)v37, v350)
          || (std::wstring::wstring(v380, L"FfeEnabled"),
              v21 |= 0x10u,
              v41 = (web::json::value *)web::json::value::at(v37, v380),
              v338 = 1,
              web::json::value::is_null(v41)) )
        {
          v338 = 0;
        }
        if ( (v21 & 0x10) != 0 )
        {
          v21 &= ~0x10u;
          std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v380);
        }
        if ( (v21 & 8) != 0 )
        {
          v21 &= ~8u;
          std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v350);
        }
        if ( v338 )
        {
          std::wstring::wstring(v350, L"FfeEnabled");
          v42 = (web::json::value *)web::json::value::at(v37, v350);
          v43 = web::json::value::as_bool(v42);
          std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v350);
          if ( v43 )
            std::_Tree<std::_Tset_traits<std::wstring,EndpointDlp::Common::wstringOrdinalCompareInsensitive,std::allocator<std::wstring>,0>>::insert<0,0>(
              v404[0],
              v359,
              Src);
          v17 = 1;
        }
        std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(Src);
        v37 = (web::json::value *)((char *)v37 + 8);
      }
      std::vector<web::json::value>::_Tidy(v381);
    }
    std::unique_ptr<web::json::details::_Null>::~unique_ptr<web::json::details::_Null>(&SystemTimeAsFileTime);
  }
  std::wstring::wstring(v350, L"UnallowedBluetoothApps");
  v44 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v379 + 8LL))(v379, v350);
  std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v350);
  if ( v44 )
  {
    SystemTimeAsFileTime = 0;
    std::wstring::wstring(v350, L"UnallowedBluetoothApps");
    v45 = (const struct web::json::value *)web::json::value::at(&v379, v350);
    web::json::value::value((web::json::value *)&SystemTimeAsFileTime, v45);
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v350);
    if ( !web::json::value::is_null((web::json::value *)&SystemTimeAsFileTime) )
    {
      *(_OWORD *)v381 = 0;
      v382 = 0;
      v46 = web::json::value::as_array((web::json::value *)&SystemTimeAsFileTime);
      *(_OWORD *)v381 = 0;
      v382 = 0;
      if ( (__int64)(*((_QWORD *)v46 + 1) - *(_QWORD *)v46) >> 3 )
      {
        std::vector<wchar_t const *>::_Buy_nonzero(v381);
        v378 = (const wchar_t *)v381;
        v381[1] = (web::json::value *)std::_Uninitialized_copy<web::json::value *,web::json::value *,std::allocator<web::json::value>>(*(struct web::json::value **)v46);
        v378 = 0;
        std::_Tidy_guard<std::vector<web::json::value>>::~_Tidy_guard<std::vector<web::json::value>>(&v378);
      }
      v47 = v381[0];
      v48 = v381[1];
      while ( v47 != v48 )
      {
        std::wstring::wstring(v350, L"ProcessName");
        v49 = web::json::value::at(v47, v350);
        v50 = web::json::value::as_string(v49);
        std::wstring::wstring(v380, v50);
        std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v350);
        std::_Tree<std::_Tset_traits<std::wstring,EndpointDlp::Common::wstringOrdinalCompareInsensitive,std::allocator<std::wstring>,0>>::insert<0,0>(
          v360,
          v404,
          v380);
        std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v380);
        v47 = (web::json::value *)((char *)v47 + 8);
      }
      std::vector<web::json::value>::_Tidy(v381);
    }
    std::unique_ptr<web::json::details::_Null>::~unique_ptr<web::json::details::_Null>(&SystemTimeAsFileTime);
  }
  std::wstring::wstring(v350, L"UnallowedCloudSyncApps");
  v51 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v379 + 8LL))(v379, v350);
  std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v350);
  if ( v51 )
  {
    SystemTimeAsFileTime = 0;
    std::wstring::wstring(v350, L"UnallowedCloudSyncApps");
    v52 = (const struct web::json::value *)web::json::value::at(&v379, v350);
    web::json::value::value((web::json::value *)&SystemTimeAsFileTime, v52);
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v350);
    if ( !web::json::value::is_null((web::json::value *)&SystemTimeAsFileTime) )
    {
      *(_OWORD *)v381 = 0;
      v382 = 0;
      v53 = web::json::value::as_array((web::json::value *)&SystemTimeAsFileTime);
      *(_OWORD *)v381 = 0;
      v382 = 0;
      if ( (__int64)(*((_QWORD *)v53 + 1) - *(_QWORD *)v53) >> 3 )
      {
        std::vector<wchar_t const *>::_Buy_nonzero(v381);
        v378 = (const wchar_t *)v381;
        v381[1] = (web::json::value *)std::_Uninitialized_copy<web::json::value *,web::json::value *,std::allocator<web::json::value>>(*(struct web::json::value **)v53);
        v378 = 0;
        std::_Tidy_guard<std::vector<web::json::value>>::~_Tidy_guard<std::vector<web::json::value>>(&v378);
      }
      std::wstring::assign(v401[0], (void *)L"|");
      v54 = v381[0];
      v55 = v381[1];
      while ( v54 != v55 )
      {
        std::wstring::wstring(v350, L"ProcessName");
        v56 = web::json::value::at(v54, v350);
        v57 = web::json::value::as_string(v56);
        std::wstring::wstring(v404, v57);
        std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v350);
        if ( v404[2] && *(_WORD *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v404) != 47 )
        {
          std::wstring::append(v356, v404);
          std::wstring::append(v356, (void *)L"|");
        }
        std::_Tree<std::_Tset_traits<std::wstring,EndpointDlp::Common::wstringOrdinalCompareInsensitive,std::allocator<std::wstring>,0>>::insert<0,0>(
          v361,
          v401,
          v404);
        std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v404);
        v54 = (web::json::value *)((char *)v54 + 8);
      }
      std::vector<web::json::value>::_Tidy(v381);
    }
    std::unique_ptr<web::json::details::_Null>::~unique_ptr<web::json::details::_Null>(&SystemTimeAsFileTime);
  }
  *((_BYTE *)v5 + 104) = 0;
  std::wstring::assign(v362, (void *)&qword_18025C818);
  *((_BYTE *)v5 + 176) = 0;
  std::wstring::assign(v363, (void *)&qword_18025C818);
  std::wstring::wstring(v350, L"QuarantineSettings");
  v58 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v379 + 8LL))(v379, v350);
  std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v350);
  if ( v58 )
  {
    v378 = 0;
    std::wstring::wstring(v350, L"QuarantineSettings");
    v59 = (const struct web::json::value *)web::json::value::at(&v379, v350);
    web::json::value::value((web::json::value *)&v378, v59);
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v350);
    if ( !web::json::value::is_null((web::json::value *)&v378) )
    {
      std::wstring::wstring(&v385, L"EnableForCloudSyncApps");
      v21 |= 0x20u;
      if ( !(*(unsigned __int8 (__fastcall **)(const wchar_t *, __int128 *))(*(_QWORD *)v378 + 8LL))(v378, &v385)
        || (std::wstring::wstring(v380, L"EnableForCloudSyncApps"),
            v21 |= 0x40u,
            v60 = (web::json::value *)web::json::value::at(&v378, v380),
            v61 = 1,
            web::json::value::is_null(v60)) )
      {
        v61 = 0;
      }
      if ( (v21 & 0x40) != 0 )
      {
        v21 &= ~0x40u;
        std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v380);
      }
      if ( (v21 & 0x20) != 0 )
      {
        v21 &= ~0x20u;
        std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(&v385);
      }
      if ( v61 )
      {
        std::wstring::wstring(v380, L"EnableForCloudSyncApps");
        v62 = (web::json::value *)web::json::value::at(&v378, v380);
        *((_BYTE *)v5 + 104) = web::json::value::as_bool(v62);
        std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v380);
      }
      if ( *((_BYTE *)v5 + 104) == 1 )
      {
        std::wstring::wstring(&v385, L"QuarantinePath");
        v63 = v21 | 0x80;
        if ( !(*(unsigned __int8 (__fastcall **)(const wchar_t *, __int128 *))(*(_QWORD *)v378 + 8LL))(v378, &v385)
          || (std::wstring::wstring(v380, L"QuarantinePath"),
              v63 |= 0x100u,
              v64 = (web::json::value *)web::json::value::at(&v378, v380),
              v65 = 1,
              web::json::value::is_null(v64)) )
        {
          v65 = 0;
        }
        if ( (v63 & 0x100) != 0 )
        {
          v63 &= ~0x100u;
          std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v380);
        }
        if ( (v63 & 0x80u) != 0 )
        {
          v63 &= ~0x80u;
          std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(&v385);
        }
        if ( v65 )
        {
          std::wstring::wstring(v380, L"QuarantinePath");
          v66 = web::json::value::at(&v378, v380);
          v67 = (void *)web::json::value::as_string(v66);
          std::wstring::operator=(v365, v67);
          std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v380);
        }
        std::wstring::wstring(&v385, L"ShouldReplaceFile");
        v68 = v63 | 0x200;
        if ( !(*(unsigned __int8 (__fastcall **)(const wchar_t *, __int128 *))(*(_QWORD *)v378 + 8LL))(v378, &v385)
          || (std::wstring::wstring(v380, L"ShouldReplaceFile"),
              v68 |= 0x400u,
              v69 = (web::json::value *)web::json::value::at(&v378, v380),
              v70 = 1,
              web::json::value::is_null(v69)) )
        {
          v70 = 0;
        }
        if ( (v68 & 0x400) != 0 )
        {
          v68 &= ~0x400u;
          std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v380);
        }
        if ( (v68 & 0x200) != 0 )
        {
          v68 &= ~0x200u;
          std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(&v385);
        }
        if ( v70 )
        {
          std::wstring::wstring(v380, L"ShouldReplaceFile");
          v71 = (web::json::value *)web::json::value::at(&v378, v380);
          *((_BYTE *)v5 + 176) = web::json::value::as_bool(v71);
          std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v380);
        }
        std::wstring::wstring(&v385, L"FileReplacementText");
        v21 = v68 | 0x800;
        if ( !(*(unsigned __int8 (__fastcall **)(const wchar_t *, __int128 *))(*(_QWORD *)v378 + 8LL))(v378, &v385)
          || (std::wstring::wstring(v380, L"FileReplacementText"),
              v21 |= 0x1000u,
              v72 = (web::json::value *)web::json::value::at(&v378, v380),
              v73 = 1,
              web::json::value::is_null(v72)) )
        {
          v73 = 0;
        }
        if ( (v21 & 0x1000) != 0 )
        {
          v21 &= ~0x1000u;
          std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v380);
        }
        if ( (v21 & 0x800) != 0 )
        {
          v21 &= ~0x800u;
          std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(&v385);
        }
        if ( v73 )
        {
          std::wstring::wstring(v380, L"FileReplacementText");
          v74 = web::json::value::at(&v378, v380);
          v75 = (void *)web::json::value::as_string(v74);
          std::wstring::operator=(v398[0], v75);
          std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v380);
        }
      }
    }
    std::unique_ptr<web::json::details::_Null>::~unique_ptr<web::json::details::_Null>(&v378);
  }
  std::wstring::wstring(v350, L"UnallowedBrowsers");
  v76 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v379 + 8LL))(v379, v350);
  std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v350);
  if ( v76 )
  {
    SystemTimeAsFileTime = 0;
    std::wstring::wstring(v350, L"UnallowedBrowsers");
    v77 = (const struct web::json::value *)web::json::value::at(&v379, v350);
    web::json::value::value((web::json::value *)&SystemTimeAsFileTime, v77);
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v350);
    if ( !web::json::value::is_null((web::json::value *)&SystemTimeAsFileTime) )
    {
      *(_OWORD *)v381 = 0;
      v382 = 0;
      v78 = web::json::value::as_array((web::json::value *)&SystemTimeAsFileTime);
      web::json::array::array((web::json::array *)v381, v78);
      v79 = v381[0];
      v80 = v381[1];
      while ( v79 != v80 )
      {
        std::wstring::wstring(v350, L"ProcessName");
        v81 = web::json::value::at(v79, v350);
        v82 = web::json::value::as_string(v81);
        std::wstring::wstring(v380, v82);
        std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v350);
        std::_Tree<std::_Tset_traits<std::wstring,EndpointDlp::Common::wstringOrdinalCompareInsensitive,std::allocator<std::wstring>,0>>::insert<0,0>(
          v396,
          v398,
          v380);
        std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v380);
        v79 = (web::json::value *)((char *)v79 + 8);
      }
      std::vector<web::json::value>::_Tidy(v381);
    }
    std::unique_ptr<web::json::details::_Null>::~unique_ptr<web::json::details::_Null>(&SystemTimeAsFileTime);
  }
  std::wstring::wstring(v350, L"CloudAppDomains");
  v83 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v379 + 8LL))(v379, v350);
  std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v350);
  if ( v83 )
  {
    v378 = 0;
    std::wstring::wstring(v350, L"CloudAppDomains");
    v84 = (const struct web::json::value *)web::json::value::at(&v379, v350);
    web::json::value::value((web::json::value *)&v378, v84);
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v350);
    std::wstring::wstring(v380, L"DefaultBehavior");
    v85 = (web::json::value *)web::json::value::at(&v378, v380);
    v86 = web::json::value::as_number(v85);
    v87 = web::json::number::to_uint32(v86);
    *((_DWORD *)v5 + 94) = EndpointDlp::DlpPolicy::DlpTypeCheck::ToDomainAccessType(v87);
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v380);
    std::wstring::wstring(v380, L"Domains");
    v88 = (*(__int64 (__fastcall **)(const wchar_t *, _BYTE *))(*(_QWORD *)v378 + 8LL))(v378, v380);
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v380);
    if ( v88 )
    {
      SystemTimeAsFileTime = 0;
      std::wstring::wstring(v380, L"Domains");
      v89 = (const struct web::json::value *)web::json::value::at(&v378, v380);
      web::json::value::value((web::json::value *)&SystemTimeAsFileTime, v89);
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v380);
      if ( !web::json::value::is_null((web::json::value *)&SystemTimeAsFileTime) )
      {
        *(_OWORD *)v381 = 0;
        v382 = 0;
        v90 = web::json::value::as_array((web::json::value *)&SystemTimeAsFileTime);
        web::json::array::array((web::json::array *)v381, v90);
        v91 = v381[0];
        v92 = v381[1];
        while ( v91 != v92 )
        {
          std::wstring::wstring(v350, L"Behavior");
          v93 = (web::json::value *)web::json::value::at(v91, v350);
          v94 = web::json::value::as_number(v93);
          v348 = web::json::number::to_uint32(v94);
          std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v350);
          std::wstring::wstring(v350, L"DomainName");
          v95 = web::json::value::at(v91, v350);
          v96 = web::json::value::as_string(v95);
          std::wstring::wstring(v401, v96);
          std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v350);
          std::wstring::wstring(v380, L"*.");
          IsPrefix = EndpointDlp::Common::IsPrefix(v401, v380, v97, 0);
          std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v380);
          if ( IsPrefix )
          {
            std::wstring::substr(v401, v380, 2, -1);
            v99 = EndpointDlp::DlpPolicy::DlpTypeCheck::ToDomainAccessType(v348);
            *(_DWORD *)(*(_QWORD *)std::map<std::wstring,enum EndpointDlp::Policy::Domains::DomainAccessType>::_Try_emplace<std::wstring const &,>(
                                     (char *)v5 + 400,
                                     &v396,
                                     v380)
                      + 64LL) = v99;
            std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v380);
          }
          else
          {
            v100 = EndpointDlp::DlpPolicy::DlpTypeCheck::ToDomainAccessType(v348);
            *(_DWORD *)(*(_QWORD *)std::map<std::wstring,enum EndpointDlp::DlpPolicy::DomainAccessType,EndpointDlp::Common::wstringOrdinalCompareInsensitive,std::allocator<std::pair<std::wstring const,enum EndpointDlp::DlpPolicy::DomainAccessType>>>::_Try_emplace<std::wstring const &,>(
                                     (char *)v5 + 384,
                                     v398,
                                     v401)
                      + 64LL) = v100;
          }
          std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v401);
          v91 = (web::json::value *)((char *)v91 + 8);
        }
        std::vector<web::json::value>::_Tidy(v381);
        v17 = 1;
      }
      std::unique_ptr<web::json::details::_Null>::~unique_ptr<web::json::details::_Null>(&SystemTimeAsFileTime);
    }
    std::unique_ptr<web::json::details::_Null>::~unique_ptr<web::json::details::_Null>(&v378);
  }
  *((_BYTE *)v5 + 640) = 0;
  std::wstring::wstring(v350, L"CollectBrowsingHistory");
  v101 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v379 + 8LL))(v379, v350);
  std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v350);
  if ( v101 )
  {
    SystemTimeAsFileTime = 0;
    std::wstring::wstring(v350, L"CollectBrowsingHistory");
    v102 = (const struct web::json::value *)web::json::value::at(&v379, v350);
    web::json::value::value((web::json::value *)&SystemTimeAsFileTime, v102);
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v350);
    if ( !web::json::value::is_null((web::json::value *)&SystemTimeAsFileTime) )
      *((_BYTE *)v5 + 640) = web::json::value::as_bool((web::json::value *)&SystemTimeAsFileTime);
    std::unique_ptr<web::json::details::_Null>::~unique_ptr<web::json::details::_Null>(&SystemTimeAsFileTime);
  }
  std::wstring::wstring(v350, L"IncludePredefinedUnallowedBluetoothApps");
  v103 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v379 + 8LL))(v379, v350);
  std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v350);
  if ( v103 )
  {
    SystemTimeAsFileTime = 0;
    std::wstring::wstring(v350, L"IncludePredefinedUnallowedBluetoothApps");
    v104 = (const struct web::json::value *)web::json::value::at(&v379, v350);
    web::json::value::value((web::json::value *)&SystemTimeAsFileTime, v104);
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v350);
    if ( !web::json::value::is_null((web::json::value *)&SystemTimeAsFileTime)
      && web::json::value::as_bool((web::json::value *)&SystemTimeAsFileTime) )
    {
      v105 = (char *)v5 + 256;
      v106 = qword_180312398;
      v107 = *(char **)qword_180312398;
      v356 = *(void **)qword_180312398;
      v108 = *((_QWORD *)v5 + 32);
      while ( v107 != (char *)v106 )
      {
        std::_Tree<std::_Tset_traits<std::wstring,EndpointDlp::Common::wstringOrdinalCompareInsensitive,std::allocator<std::wstring>,0>>::_Emplace_hint<std::wstring const &>(
          v105,
          v108,
          v107 + 32);
        std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::wstring>>,std::_Iterator_base0>::operator++(&v356);
        v107 = (char *)v356;
      }
      v5 = v352;
    }
    std::unique_ptr<web::json::details::_Null>::~unique_ptr<web::json::details::_Null>(&SystemTimeAsFileTime);
  }
  *((_BYTE *)v5 + 416) = 0;
  std::wstring::wstring(v350, L"TakeCloudAppDomainsFromSeparateConfig");
  v109 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v379 + 8LL))(v379, v350);
  std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v350);
  if ( v109 )
  {
    SystemTimeAsFileTime = 0;
    std::wstring::wstring(v350, L"TakeCloudAppDomainsFromSeparateConfig");
    v110 = (const struct web::json::value *)web::json::value::at(&v379, v350);
    web::json::value::value((web::json::value *)&SystemTimeAsFileTime, v110);
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v350);
    if ( !web::json::value::is_null((web::json::value *)&SystemTimeAsFileTime) )
      *((_BYTE *)v5 + 416) = web::json::value::as_bool((web::json::value *)&SystemTimeAsFileTime);
    std::unique_ptr<web::json::details::_Null>::~unique_ptr<web::json::details::_Null>(&SystemTimeAsFileTime);
  }
  *((_BYTE *)v5 + 421) = 0;
  std::wstring::wstring(v350, L"IsJitEnforcementEnabled");
  v111 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v379 + 8LL))(v379, v350);
  std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v350);
  if ( v111 )
  {
    SystemTimeAsFileTime = 0;
    std::wstring::wstring(v350, L"IsJitEnforcementEnabled");
    v112 = (const struct web::json::value *)web::json::value::at(&v379, v350);
    web::json::value::value((web::json::value *)&SystemTimeAsFileTime, v112);
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v350);
    if ( !web::json::value::is_null((web::json::value *)&SystemTimeAsFileTime) )
      *((_BYTE *)v5 + 421) = web::json::value::as_bool((web::json::value *)&SystemTimeAsFileTime);
    std::unique_ptr<web::json::details::_Null>::~unique_ptr<web::json::details::_Null>(&SystemTimeAsFileTime);
  }
  *((_BYTE *)v5 + 178) = 0;
  std::wstring::wstring(v350, L"IsLLMScanEnabled");
  v113 = web::json::value::has_boolean_field(&v379, v350);
  std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v350);
  if ( v113 )
  {
    std::wstring::wstring(v350, L"IsLLMScanEnabled");
    v114 = (web::json::value *)web::json::value::at(&v379, v350);
    *((_BYTE *)v5 + 178) = web::json::value::as_bool(v114);
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v350);
  }
  EndpointDlp::DlpPolicy::ProcessJitEnforcementModeArray(v5, (const struct web::json::value *)&v379);
  EndpointDlp::DlpPolicy::ProcessJitExclusions(v5, (const struct web::json::value *)&v379);
  std::wstring::wstring(v350, L"CandidatePolicyRuleId");
  v115 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v379 + 8LL))(v379, v350);
  std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v350);
  if ( v115 )
  {
    SystemTimeAsFileTime = 0;
    std::wstring::wstring(v350, L"CandidatePolicyRuleId");
    v116 = (const struct web::json::value *)web::json::value::at(&v379, v350);
    web::json::value::value((web::json::value *)&SystemTimeAsFileTime, v116);
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v350);
    if ( !web::json::value::is_null((web::json::value *)&SystemTimeAsFileTime) )
    {
      v117 = (void *)web::json::value::as_string(&SystemTimeAsFileTime);
      std::wstring::operator=(v358, v117);
    }
    std::unique_ptr<web::json::details::_Null>::~unique_ptr<web::json::details::_Null>(&SystemTimeAsFileTime);
  }
  *((_DWORD *)v5 + 111) = 2;
  std::wstring::wstring(v350, L"JitFallbackAction");
  v118 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v379 + 8LL))(v379, v350);
  std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v350);
  if ( v118 )
  {
    std::wstring::wstring(v350, L"JitFallbackAction");
    v119 = (web::json::value *)web::json::value::at(&v379, v350);
    v120 = web::json::value::as_integer(v119);
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v350);
    if ( v120 == 3 )
      *((_DWORD *)v5 + 111) = 3;
  }
  std::wstring::wstring(v350, L"SyncClassificationBlockBlanketPolicyRuleId");
  v121 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v379 + 8LL))(v379, v350);
  std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v350);
  if ( v121 )
  {
    SystemTimeAsFileTime = 0;
    std::wstring::wstring(v350, L"SyncClassificationBlockBlanketPolicyRuleId");
    v122 = (const struct web::json::value *)web::json::value::at(&v379, v350);
    web::json::value::value((web::json::value *)&SystemTimeAsFileTime, v122);
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v350);
    if ( !web::json::value::is_null((web::json::value *)&SystemTimeAsFileTime) )
    {
      v123 = (void *)web::json::value::as_string(&SystemTimeAsFileTime);
      std::wstring::operator=(v394[0], v123);
    }
    std::unique_ptr<web::json::details::_Null>::~unique_ptr<web::json::details::_Null>(&SystemTimeAsFileTime);
  }
  std::wstring::wstring(v350, L"SyncClassificationAllowBlanketPolicyRuleId");
  v124 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v379 + 8LL))(v379, v350);
  std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v350);
  if ( v124 )
  {
    SystemTimeAsFileTime = 0;
    std::wstring::wstring(v350, L"SyncClassificationAllowBlanketPolicyRuleId");
    v125 = (const struct web::json::value *)web::json::value::at(&v379, v350);
    web::json::value::value((web::json::value *)&SystemTimeAsFileTime, v125);
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v350);
    if ( !web::json::value::is_null((web::json::value *)&SystemTimeAsFileTime) )
    {
      v126 = (void *)web::json::value::as_string(&SystemTimeAsFileTime);
      std::wstring::operator=(v399[0], v126);
    }
    std::unique_ptr<web::json::details::_Null>::~unique_ptr<web::json::details::_Null>(&SystemTimeAsFileTime);
  }
  std::wstring::wstring(v350, L"AsyncClassificationPolicyRuleId");
  v127 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v379 + 8LL))(v379, v350);
  std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v350);
  if ( v127 )
  {
    SystemTimeAsFileTime = 0;
    std::wstring::wstring(v350, L"AsyncClassificationPolicyRuleId");
    v128 = (const struct web::json::value *)web::json::value::at(&v379, v350);
    web::json::value::value((web::json::value *)&SystemTimeAsFileTime, v128);
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v350);
    if ( !web::json::value::is_null((web::json::value *)&SystemTimeAsFileTime) )
    {
      v129 = (void *)web::json::value::as_string(&SystemTimeAsFileTime);
      std::wstring::operator=(v393[0], v129);
    }
    std::unique_ptr<web::json::details::_Null>::~unique_ptr<web::json::details::_Null>(&SystemTimeAsFileTime);
  }
  std::wstring::wstring(v350, L"RmsLabelingPolicyRuleId");
  v130 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v379 + 8LL))(v379, v350);
  std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v350);
  if ( v130 )
  {
    SystemTimeAsFileTime = 0;
    std::wstring::wstring(v350, L"RmsLabelingPolicyRuleId");
    v131 = (const struct web::json::value *)web::json::value::at(&v379, v350);
    web::json::value::value((web::json::value *)&SystemTimeAsFileTime, v131);
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v350);
    if ( !web::json::value::is_null((web::json::value *)&SystemTimeAsFileTime) )
    {
      v132 = (void *)web::json::value::as_string(&SystemTimeAsFileTime);
      std::wstring::operator=(v383[0], v132);
    }
    std::unique_ptr<web::json::details::_Null>::~unique_ptr<web::json::details::_Null>(&SystemTimeAsFileTime);
  }
  std::wstring::wstring(v380, L"EvidenceStoreSettings");
  v133 = v21 | 0x2000;
  if ( !(*(unsigned __int8 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v379 + 8LL))(v379, v380)
    || (std::wstring::wstring(v350, L"EvidenceStoreSettings"),
        v133 |= 0x4000u,
        v134 = (web::json::value *)web::json::value::at(&v379, v350),
        v135 = 1,
        web::json::value::is_null(v134)) )
  {
    v135 = 0;
  }
  if ( (v133 & 0x4000) != 0 )
  {
    v133 &= ~0x4000u;
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v350);
  }
  if ( (v133 & 0x2000) != 0 )
  {
    v133 &= ~0x2000u;
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v380);
  }
  if ( v135 )
  {
    v378 = 0;
    std::wstring::wstring(v350, L"EvidenceStoreSettings");
    v136 = (const struct web::json::value *)web::json::value::at(&v379, v350);
    web::json::value::value((web::json::value *)&v378, v136);
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v350);
    std::wstring::wstring(v380, L"FileEvidenceIsEnabled");
    v137 = (*(__int64 (__fastcall **)(const wchar_t *, _BYTE *))(*(_QWORD *)v378 + 8LL))(v378, v380);
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v380);
    if ( v137 )
    {
      SystemTimeAsFileTime = 0;
      std::wstring::wstring(v380, L"FileEvidenceIsEnabled");
      v138 = (const struct web::json::value *)web::json::value::at(&v378, v380);
      web::json::value::value((web::json::value *)&SystemTimeAsFileTime, v138);
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v380);
      if ( !web::json::value::is_null((web::json::value *)&SystemTimeAsFileTime) )
        *((_BYTE *)v5 + 179) = web::json::value::as_bool((web::json::value *)&SystemTimeAsFileTime);
      std::unique_ptr<web::json::details::_Null>::~unique_ptr<web::json::details::_Null>(&SystemTimeAsFileTime);
    }
    std::wstring::wstring(v380, L"StorageAccounts");
    v139 = (*(__int64 (__fastcall **)(const wchar_t *, _BYTE *))(*(_QWORD *)v378 + 8LL))(v378, v380);
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v380);
    if ( v139 )
    {
      SystemTimeAsFileTime = 0;
      std::wstring::wstring(v380, L"StorageAccounts");
      v140 = (const struct web::json::value *)web::json::value::at(&v378, v380);
      web::json::value::value((web::json::value *)&SystemTimeAsFileTime, v140);
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v380);
      if ( !web::json::value::is_null((web::json::value *)&SystemTimeAsFileTime) )
      {
        *(_OWORD *)v381 = 0;
        v382 = 0;
        v141 = web::json::value::as_array((web::json::value *)&SystemTimeAsFileTime);
        web::json::array::array((web::json::array *)v381, v141);
        v142 = v381[0];
        v143 = v381[1];
        while ( v142 != v143 )
        {
          std::wstring::wstring(v380, L"Name");
          v144 = web::json::value::at(v142, v380);
          v145 = web::json::value::as_string(v144);
          std::wstring::wstring(v393, v145);
          std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v380);
          std::wstring::wstring(&v385, L"BlobUri");
          v146 = web::json::value::at(v142, &v385);
          v147 = web::json::value::as_string(v146);
          std::wstring::wstring(Src, v147);
          std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(&v385);
          v148 = std::map<std::wstring,std::wstring,EndpointDlp::Common::wstringOrdinalCompareInsensitive,std::allocator<std::pair<std::wstring const,std::wstring>>>::_Try_emplace<std::wstring const &,>(
                   (char *)v5 + 792,
                   v383,
                   v393);
          std::wstring::operator=((void *)(*(_QWORD *)v148 + 64LL), Src);
          std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(Src);
          std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v393);
          v142 = (web::json::value *)((char *)v142 + 8);
        }
        std::vector<web::json::value>::_Tidy(v381);
      }
      std::unique_ptr<web::json::details::_Null>::~unique_ptr<web::json::details::_Null>(&SystemTimeAsFileTime);
    }
    std::wstring::wstring(&v385, L"NumberOfDaysToRetain");
    v133 |= 0x8000u;
    if ( !(*(unsigned __int8 (__fastcall **)(const wchar_t *, __int128 *))(*(_QWORD *)v378 + 8LL))(v378, &v385)
      || (std::wstring::wstring(v380, L"NumberOfDaysToRetain"),
          v133 |= 0x10000u,
          v150 = (web::json::value *)web::json::value::at(&v378, v380),
          v151 = 1,
          web::json::value::is_null(v150)) )
    {
      v151 = 0;
    }
    if ( (v133 & 0x10000) != 0 )
    {
      v133 &= ~0x10000u;
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v380);
    }
    if ( (v133 & 0x8000) != 0 )
    {
      v133 &= ~0x8000u;
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(&v385);
    }
    if ( v151 )
    {
      std::wstring::wstring(v380, L"NumberOfDaysToRetain");
      v152 = (web::json::value *)web::json::value::at(&v378, v380);
      v153 = web::json::value::as_number(v152);
      *((_DWORD *)v5 + 45) = web::json::number::to_uint32(v153);
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v380);
      v154 = *((_DWORD *)v5 + 45);
    }
    else
    {
      v154 = 0;
    }
    EndpointDlp::DlpPolicy::SetRetentionDaysInRegistry(v149, v154);
    std::unique_ptr<web::json::details::_Null>::~unique_ptr<web::json::details::_Null>(&v378);
  }
  v155 = (EndpointDlp::DlpPolicy::DeviceIdentifiersHint *)*((_QWORD *)v5 + 111);
  v156 = (EndpointDlp::DlpPolicy::DeviceIdentifiersHint *)*((_QWORD *)v5 + 110);
  if ( v156 != v155 )
  {
    do
    {
      EndpointDlp::DlpPolicy::DeviceIdentifiersHint::~DeviceIdentifiersHint(v156);
      v156 = (EndpointDlp::DlpPolicy::DeviceIdentifiersHint *)((char *)v156 + 64);
    }
    while ( v156 != v155 );
    *((_QWORD *)v5 + 111) = *((_QWORD *)v5 + 110);
  }
  try
  {
    std::wstring::wstring(v380, L"ContentEvaluationHints");
    v157 = v133 | 0x20000;
    v349 = v157;
    if ( !(*(unsigned __int8 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v379 + 8LL))(v379, v380)
      || (std::wstring::wstring(v350, L"ContentEvaluationHints"),
          v157 |= 0x40000u,
          v349 = v157,
          v158 = (web::json::value *)web::json::value::at(&v379, v350),
          v159 = 1,
          web::json::value::is_null(v158)) )
    {
      v159 = 0;
    }
    if ( (v157 & 0x40000) != 0 )
    {
      v157 &= ~0x40000u;
      v349 = v157;
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v350);
    }
    if ( (v157 & 0x20000) != 0 )
    {
      v157 &= ~0x20000u;
      v349 = v157;
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v380);
    }
    if ( v159 )
    {
      v378 = 0;
      std::wstring::wstring(v350, L"ContentEvaluationHints");
      v160 = (const struct web::json::value *)web::json::value::at(&v379, v350);
      web::json::value::value((web::json::value *)&v378, v160);
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v350);
      std::wstring::wstring(&v385, L"DeviceIdentifiers");
      v157 |= 0x80000u;
      v349 = v157;
      if ( !(*(unsigned __int8 (__fastcall **)(const wchar_t *, __int128 *))(*(_QWORD *)v378 + 8LL))(v378, &v385)
        || (std::wstring::wstring(v380, L"DeviceIdentifiers"),
            v157 |= 0x100000u,
            v349 = v157,
            v161 = (web::json::value *)web::json::value::at(&v378, v380),
            web::json::value::is_null(v161)) )
      {
        v17 = 0;
      }
      if ( (v157 & 0x100000) != 0 )
      {
        v157 &= ~0x100000u;
        v349 = v157;
        std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v380);
      }
      if ( (v157 & 0x80000) != 0 )
      {
        v157 &= ~0x80000u;
        v349 = v157;
        std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(&v385);
      }
      if ( v17 )
      {
        SystemTimeAsFileTime = 0;
        std::wstring::wstring(v380, L"DeviceIdentifiers");
        v162 = (const struct web::json::value *)web::json::value::at(&v378, v380);
        web::json::value::value((web::json::value *)&SystemTimeAsFileTime, v162);
        std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v380);
        if ( web::json::value::is_array((web::json::value *)&SystemTimeAsFileTime) )
        {
          *(_OWORD *)v381 = 0;
          v382 = 0;
          v163 = web::json::value::as_array((web::json::value *)&SystemTimeAsFileTime);
          web::json::array::array((web::json::array *)v381, v163);
          v164 = v381[0];
          v165 = v381[1];
          si128 = _mm_load_si128((const __m128i *)&_xmm);
          while ( v164 != v165 )
          {
            std::wstring::wstring(&v385, L"Id");
            v157 |= 0x200000u;
            v349 = v157;
            v167 = 0;
            if ( (unsigned __int8)web::json::value::has_string_field(v164, &v385) )
            {
              std::wstring::wstring(v380, L"Scope");
              v157 |= 0x400000u;
              v349 = v157;
              if ( (unsigned __int8)web::json::value::has_string_field(v164, v380) )
              {
                std::wstring::wstring(v350, L"PolicyId");
                v157 |= 0x800000u;
                v349 = v157;
                if ( (unsigned __int8)web::json::value::has_string_field(v164, v350) )
                  v167 = 1;
              }
            }
            if ( (v157 & 0x800000) != 0 )
            {
              v157 &= ~0x800000u;
              v349 = v157;
              std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v350);
            }
            if ( (v157 & 0x400000) != 0 )
            {
              v157 &= ~0x400000u;
              v349 = v157;
              std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v380);
            }
            if ( (v157 & 0x200000) != 0 )
            {
              v157 &= ~0x200000u;
              v349 = v157;
              std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(&v385);
            }
            if ( v167 )
            {
              v385 = 0;
              v386 = si128;
              LOWORD(v385) = 0;
              v387 = 0;
              v388 = 0;
              v389 = 0;
              v390 = 0;
              v391 = 0;
              v392 = 0;
              std::wstring::wstring(v350, L"Id");
              v168 = web::json::value::at(v164, v350);
              v169 = (void *)web::json::value::as_string(v168);
              std::wstring::operator=(&v385, v169);
              std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v350);
              v170 = &v385;
              if ( v386.m128i_i64[1] > 7uLL )
                LODWORD(v170) = v385;
              v171 = (_QWORD *)std::wstring::end(&v385, v383);
              v172 = &v385;
              if ( v386.m128i_i64[1] > 7uLL )
                LODWORD(v172) = v385;
              std::transform<std::_String_iterator<std::_String_val<std::_Simple_types<wchar_t>>>,std::_String_iterator<std::_String_val<std::_Simple_types<wchar_t>>>,unsigned short (*)(unsigned short)>(
                (unsigned int)v393,
                (_DWORD)v172,
                *v171,
                (_DWORD)v170,
                (__int64)towlower);
              v173 = std::operator==<wchar_t>(&v385, L"all");
              v174 = v388;
              if ( v173 )
                v174 = 1;
              v388 = v174;
              std::wstring::wstring(v350, L"Scope");
              v175 = web::json::value::at(v164, v350);
              v176 = web::json::value::as_string(v175);
              std::wstring::wstring(v398, v176);
              std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v350);
              v177 = *(_QWORD *)std::wstring::begin(v398, v399);
              v178 = *(_QWORD *)std::wstring::end(v398, v394);
              v179 = (_QWORD *)std::wstring::begin(v398, &v358);
              std::transform<std::_String_iterator<std::_String_val<std::_Simple_types<wchar_t>>>,std::_String_iterator<std::_String_val<std::_Simple_types<wchar_t>>>,unsigned short (*)(unsigned short)>(
                (unsigned int)&v396,
                *v179,
                v178,
                v177,
                (__int64)towlower);
              if ( (unsigned __int8)std::operator==<wchar_t>(v398, L"inclusion") )
              {
                HIBYTE(v387) = 1;
              }
              else
              {
                v180 = std::operator==<wchar_t>(v398, L"exclusion");
                v181 = v387;
                if ( v180 )
                  v181 = 1;
                LOBYTE(v387) = v181;
              }
              std::wstring::wstring(v380, L"PolicyId");
              v182 = web::json::value::at(v164, v380);
              v183 = web::json::value::as_string(v182);
              std::vector<std::wstring>::_Emplace_one_at_back<std::wstring const &>(&v391, v183);
              std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v380);
              if ( *((_QWORD *)v352 + 111) == *((_QWORD *)v352 + 112) )
              {
                std::vector<EndpointDlp::DlpPolicy::DeviceIdentifiersHint>::_Emplace_reallocate<EndpointDlp::DlpPolicy::DeviceIdentifiersHint>(
                  (char *)v352 + 880,
                  *((_QWORD *)v352 + 111),
                  &v385);
              }
              else
              {
                EndpointDlp::DlpPolicy::DeviceIdentifiersHint::DeviceIdentifiersHint(*((_QWORD *)v352 + 111), &v385);
                *(_QWORD *)(v184 + 888) += 64LL;
              }
              std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v398);
              EndpointDlp::DlpPolicy::DeviceIdentifiersHint::~DeviceIdentifiersHint((EndpointDlp::DlpPolicy::DeviceIdentifiersHint *)&v385);
            }
            v164 = (web::json::value *)((char *)v164 + 8);
          }
          std::vector<web::json::value>::_Tidy(v381);
        }
        else
        {
          si128 = _mm_load_si128((const __m128i *)&_xmm);
        }
        std::unique_ptr<web::json::details::_Null>::~unique_ptr<web::json::details::_Null>(&SystemTimeAsFileTime);
      }
      else
      {
        si128 = _mm_load_si128((const __m128i *)&_xmm);
      }
      std::unique_ptr<web::json::details::_Null>::~unique_ptr<web::json::details::_Null>(&v378);
    }
    else
    {
      si128 = _mm_load_si128((const __m128i *)&_xmm);
    }
    v185 = v352;
  }
  catch ( web::json::json_exception *v370 )
  {
    v325 = EndpointDlp::TraceLoggingProvider::Instance();
    v326 = *(_DWORD **)v325;
    if ( **(_DWORD **)v325 > 2u )
    {
      v383[0] = (void *)(*(__int64 (__fastcall **)(web::json::json_exception *))(*(_QWORD *)v370 + 8LL))(v370);
      v393[0] = L"Failed to parse DeviceIdentifiers Json";
      LODWORD(v352) = -2089484281;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>>(
        (int)v326,
        (int)&byte_1802C8CCF,
        (__int64)&v352,
        (__int64)v393,
        (__int64)v383);
    }
    goto LABEL_252;
  }
  catch ( const std::exception *v371 )
  {
    v327 = EndpointDlp::TraceLoggingProvider::Instance();
    v328 = *(_DWORD **)v327;
    if ( **(_DWORD **)v327 > 2u )
    {
      v383[0] = (void *)(*(__int64 (__fastcall **)(const std::exception *))(*(_QWORD *)v371 + 8LL))(v371);
      v393[0] = L"Exception while parsing DeviceIdentifiers entry";
      LODWORD(v352) = -2147418113;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>>(
        (int)v328,
        (int)&byte_1802C8569,
        (__int64)&v352,
        (__int64)v393,
        (__int64)v383);
    }
LABEL_252:
    v185 = v355;
    v352 = v355;
    v6 = v351;
    v157 = v349;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
  }
  std::wstring::wstring(v350, L"Policies");
  v186 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v379 + 8LL))(v379, v350);
  std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v350);
  if ( v186 )
  {
    SystemTimeAsFileTime = 0;
    std::wstring::wstring(v350, L"Policies");
    v187 = (const struct web::json::value *)web::json::value::at(&v379, v350);
    web::json::value::value((web::json::value *)&SystemTimeAsFileTime, v187);
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v350);
    if ( !web::json::value::is_null((web::json::value *)&SystemTimeAsFileTime) )
    {
      *((_BYTE *)v185 + 908) = 0;
      *(_OWORD *)v381 = 0;
      v382 = 0;
      v188 = web::json::value::as_array((web::json::value *)&SystemTimeAsFileTime);
      web::json::array::array((web::json::array *)v381, v188);
      v189 = v381[0];
      v190 = v381[1];
      while ( v189 != v190 )
      {
        EndpointDlp::DlpPolicy::RuleActions::RuleActions((EndpointDlp::DlpPolicy::RuleActions *)v414);
        EndpointDlp::DlpPolicy::ProcessRuleJson(v185, v189, (struct EndpointDlp::DlpPolicy::RuleActions *)v414, v353);
        v191 = std::map<std::wstring,EndpointDlp::DlpPolicy::RuleActions,EndpointDlp::Common::wstringCompareInsensitive,std::allocator<std::pair<std::wstring const,EndpointDlp::DlpPolicy::RuleActions>>>::operator[](
                 (char *)v185 + 648,
                 v414);
        EndpointDlp::DlpPolicy::RuleActions::operator=(v191, v414);
        EndpointDlp::DlpPolicy::RuleActions::~RuleActions((EndpointDlp::DlpPolicy::RuleActions *)v414);
        v189 = (const struct web::json::value *)((char *)v189 + 8);
      }
      std::vector<web::json::value>::_Tidy(v381);
    }
    std::unique_ptr<web::json::details::_Null>::~unique_ptr<web::json::details::_Null>(&SystemTimeAsFileTime);
  }
  EndpointDlp::DlpPolicy::GenerateJitClassificationNeededArray(v185);
  EndpointDlp::DlpPolicy::AdjustJITPolicyByEnforcementMode(v185);
  std::wstring::wstring(v350, L"ApplicationGroupsSettings");
  v192 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v379 + 8LL))(v379, v350);
  std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v350);
  if ( v192 )
  {
    SystemTimeAsFileTime = 0;
    std::wstring::wstring(v350, L"ApplicationGroupsSettings");
    v193 = (const struct web::json::value *)web::json::value::at(&v379, v350);
    web::json::value::value((web::json::value *)&SystemTimeAsFileTime, v193);
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v350);
    if ( !web::json::value::is_null((web::json::value *)&SystemTimeAsFileTime)
      && web::json::value::is_string((web::json::value *)&SystemTimeAsFileTime) )
    {
      v194 = web::json::value::as_string(&SystemTimeAsFileTime);
      std::wstring::wstring(&v385, v194);
      v378 = 0;
      web::json::value::value((web::json::value *)&v378);
      try
      {
        v195 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(&v385);
        std::wstring::wstring(v350, v195);
        v196 = web::json::value::parse(v383, v350);
        web::json::value::operator=(&v378, v196);
        std::unique_ptr<web::json::details::_Null>::~unique_ptr<web::json::details::_Null>(v383);
        std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v350);
        v197 = v352;
      }
      catch ( web::json::json_exception *v372 )
      {
        v329 = EndpointDlp::TraceLoggingProvider::Instance();
        v330 = *(_DWORD **)v329;
        if ( **(_DWORD **)v329 > 2u )
        {
          v383[0] = (void *)(*(__int64 (__fastcall **)(web::json::json_exception *))(*(_QWORD *)v372 + 8LL))(v372);
          v393[0] = L"Failed to parse ApplicationGroupsSettings Json";
          LODWORD(v352) = -2089484281;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>>(
            (int)v330,
            (int)&word_1802C813A,
            (__int64)&v352,
            (__int64)v393,
            (__int64)v383);
        }
        goto LABEL_264;
      }
      catch ( std::exception *v373 )
      {
        v331 = EndpointDlp::TraceLoggingProvider::Instance();
        v332 = *(_DWORD **)v331;
        if ( **(_DWORD **)v331 > 2u )
        {
          v383[0] = (void *)(*(__int64 (__fastcall **)(std::exception *))(*(_QWORD *)v373 + 8LL))(v373);
          v393[0] = L"Failed to parse ApplicationGroupsSettings Json";
          LODWORD(v352) = -2147418113;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>>(
            (int)v332,
            (int)&byte_1802C8273,
            (__int64)&v352,
            (__int64)v393,
            (__int64)v383);
        }
LABEL_264:
        v197 = v355;
        v352 = v355;
        v6 = v351;
        v157 = v349;
        si128 = _mm_load_si128((const __m128i *)&_xmm);
      }
      v198 = 1;
      if ( !web::json::value::is_null((web::json::value *)&v378)
        && web::json::value::is_array((web::json::value *)&v378) )
      {
        v396 = 0;
        v397.m128i_i64[0] = 0;
        v199 = web::json::value::as_array((web::json::value *)&v378);
        web::json::array::array((web::json::array *)&v396, v199);
        v200 = (_QWORD *)*((_QWORD *)&v396 + 1);
        v393[0] = *((void **)&v396 + 1);
        for ( i = (_QWORD *)v396; ; ++i )
        {
          v356 = i;
          if ( i == v200 )
            break;
          EndpointDlp::DlpPolicy::ConditionalAppsGroupInfo::ConditionalAppsGroupInfo((EndpointDlp::DlpPolicy::ConditionalAppsGroupInfo *)v408);
          std::wstring::wstring(v380, L"Id");
          v157 |= 0x1000000u;
          if ( !(*(unsigned __int8 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*i + 8LL))(*i, v380)
            || (std::wstring::wstring(v350, L"Id"),
                v157 |= 0x2000000u,
                v202 = (web::json::value *)web::json::value::at(i, v350),
                v339 = 1,
                web::json::value::is_null(v202)) )
          {
            v339 = 0;
          }
          if ( (v157 & 0x2000000) != 0 )
          {
            v157 &= ~0x2000000u;
            std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v350);
          }
          if ( (v157 & 0x1000000) != 0 )
          {
            v157 &= ~0x1000000u;
            std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v380);
          }
          if ( v339 )
          {
            std::wstring::wstring(v350, L"Id");
            v203 = web::json::value::at(i, v350);
            v204 = (void *)web::json::value::as_string(v203);
            std::wstring::operator=(v408, v204);
            std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v350);
            std::wstring::wstring(v380, L"Name");
            v205 = v157 | 0x4000000;
            if ( !(*(unsigned __int8 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*i + 8LL))(*i, v380)
              || (std::wstring::wstring(v350, L"Name"),
                  v205 |= 0x8000000u,
                  v206 = (web::json::value *)web::json::value::at(i, v350),
                  v340 = 1,
                  web::json::value::is_null(v206)) )
            {
              v340 = 0;
            }
            if ( (v205 & 0x8000000) != 0 )
            {
              v205 &= ~0x8000000u;
              std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v350);
            }
            if ( (v205 & 0x4000000) != 0 )
            {
              v205 &= ~0x4000000u;
              std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v380);
            }
            if ( v340 )
            {
              std::wstring::wstring(v350, L"Name");
              v207 = web::json::value::at(i, v350);
              v208 = (void *)web::json::value::as_string(v207);
              std::wstring::operator=(v409, v208);
              std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v350);
            }
            else
            {
              std::wstring::operator=(v409, L"N/A");
            }
            std::wstring::wstring(v380, L"Description");
            v209 = v205 | 0x10000000;
            if ( !(*(unsigned __int8 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*i + 8LL))(*i, v380)
              || (std::wstring::wstring(v350, L"Description"),
                  v209 |= 0x20000000u,
                  v210 = (web::json::value *)web::json::value::at(i, v350),
                  v341 = 1,
                  web::json::value::is_null(v210)) )
            {
              v341 = 0;
            }
            if ( (v209 & 0x20000000) != 0 )
            {
              v209 &= ~0x20000000u;
              std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v350);
            }
            if ( (v209 & 0x10000000) != 0 )
            {
              v209 &= ~0x10000000u;
              std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v380);
            }
            if ( v341 )
            {
              std::wstring::wstring(v350, L"Description");
              v211 = web::json::value::at(i, v350);
              v212 = (void *)web::json::value::as_string(v211);
              std::wstring::operator=(v410, v212);
              std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v350);
            }
            else
            {
              std::wstring::operator=(v409, L"N/A");
            }
            std::wstring::wstring(v380, L"Apps");
            v157 = v209 | 0x40000000;
            if ( !(*(unsigned __int8 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*i + 8LL))(*i, v380)
              || (std::wstring::wstring(v350, L"Apps"),
                  v157 |= 0x80000000,
                  v213 = (web::json::value *)web::json::value::at(i, v350),
                  web::json::value::is_null(v213)) )
            {
              v198 = 0;
            }
            if ( v157 < 0 )
            {
              v157 &= ~0x80000000;
              std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v350);
            }
            if ( (v157 & 0x40000000) != 0 )
            {
              v157 &= ~0x40000000u;
              std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v380);
            }
            if ( v198 )
            {
              *(_OWORD *)v381 = 0;
              v382 = 0;
              std::wstring::wstring(v350, L"Apps");
              v214 = (web::json::value *)web::json::value::at(i, v350);
              v215 = web::json::value::as_array(v214);
              web::json::array::array((web::json::array *)v381, v215);
              std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v350);
              v216 = v381[0];
              v217 = v381[1];
              v218 = v352;
              while ( v216 != v217 )
              {
                v405[0] = 0;
                v405[1] = si128;
                LOWORD(v405[0]) = 0;
                v406[0] = 0;
                v406[1] = si128;
                LOWORD(v406[0]) = 0;
                v407 = 0;
                std::wstring::wstring(v380, L"ExecutableName");
                v6 |= 1u;
                v351 = v6;
                if ( !(*(unsigned __int8 (__fastcall **)(_QWORD, _BYTE *))(**(_QWORD **)v216 + 8LL))(
                        *(_QWORD *)v216,
                        v380)
                  || (std::wstring::wstring(v350, L"ExecutableName"),
                      v6 |= 2u,
                      v351 = v6,
                      v219 = (web::json::value *)web::json::value::at(v216, v350),
                      v342 = 1,
                      web::json::value::is_null(v219)) )
                {
                  v342 = 0;
                }
                if ( (v6 & 2) != 0 )
                {
                  v6 &= ~2u;
                  v351 = v6;
                  std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v350);
                }
                if ( (v6 & 1) != 0 )
                {
                  v6 &= ~1u;
                  v351 = v6;
                  std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v380);
                }
                if ( v342 )
                {
                  std::wstring::wstring(v350, L"ExecutableName");
                  v220 = web::json::value::at(v216, v350);
                  v221 = (void *)web::json::value::as_string(v220);
                  std::wstring::operator=(v406, v221);
                  std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v350);
                  std::wstring::wstring(v380, L"Name");
                  v222 = v6 | 4;
                  v351 = v222;
                  if ( !(*(unsigned __int8 (__fastcall **)(_QWORD, _BYTE *))(**(_QWORD **)v216 + 8LL))(
                          *(_QWORD *)v216,
                          v380)
                    || (std::wstring::wstring(v350, L"Name"),
                        v222 |= 8u,
                        v351 = v222,
                        v223 = (web::json::value *)web::json::value::at(v216, v350),
                        v343 = 1,
                        web::json::value::is_null(v223)) )
                  {
                    v343 = 0;
                  }
                  if ( (v222 & 8) != 0 )
                  {
                    v222 &= ~8u;
                    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v350);
                  }
                  if ( (v222 & 4) != 0 )
                  {
                    v222 &= ~4u;
                    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v380);
                  }
                  if ( v343 )
                  {
                    std::wstring::wstring(v350, L"Name");
                    v224 = web::json::value::at(v216, v350);
                    v225 = (void *)web::json::value::as_string(v224);
                    std::wstring::operator=(v405, v225);
                    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v350);
                  }
                  else
                  {
                    std::wstring::operator=(v405, L"N/A");
                  }
                  std::wstring::wstring(v380, L"Quarantine");
                  v226 = v222 | 0x10;
                  v351 = v226;
                  if ( !(*(unsigned __int8 (__fastcall **)(_QWORD, _BYTE *))(**(_QWORD **)v216 + 8LL))(
                          *(_QWORD *)v216,
                          v380)
                    || (std::wstring::wstring(v350, L"Quarantine"),
                        v226 |= 0x20u,
                        v351 = v226,
                        v227 = (web::json::value *)web::json::value::at(v216, v350),
                        v344 = 1,
                        web::json::value::is_null(v227)) )
                  {
                    v344 = 0;
                  }
                  if ( (v226 & 0x20) != 0 )
                  {
                    v226 &= ~0x20u;
                    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v350);
                  }
                  if ( (v226 & 0x10) != 0 )
                  {
                    v226 &= ~0x10u;
                    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v380);
                  }
                  if ( v344 )
                  {
                    std::wstring::wstring(v350, L"Quarantine");
                    v228 = (web::json::value *)web::json::value::at(v216, v350);
                    LOBYTE(v407) = web::json::value::as_bool(v228);
                    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v350);
                  }
                  else
                  {
                    LOBYTE(v407) = 0;
                  }
                  std::wstring::wstring(v380, L"FfeEnabled");
                  v6 = v226 | 0x40;
                  v351 = v6;
                  if ( !(*(unsigned __int8 (__fastcall **)(_QWORD, _BYTE *))(**(_QWORD **)v216 + 8LL))(
                          *(_QWORD *)v216,
                          v380)
                    || (std::wstring::wstring(v350, L"FfeEnabled"),
                        v6 |= 0x80u,
                        v351 = v6,
                        v229 = (web::json::value *)web::json::value::at(v216, v350),
                        v345 = 1,
                        web::json::value::is_null(v229)) )
                  {
                    v345 = 0;
                  }
                  if ( (v6 & 0x80u) != 0 )
                  {
                    v6 &= ~0x80u;
                    v351 = v6;
                    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v350);
                  }
                  if ( (v6 & 0x40) != 0 )
                  {
                    v6 &= ~0x40u;
                    v351 = v6;
                    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v380);
                  }
                  if ( v345 )
                  {
                    std::wstring::wstring(v350, L"FfeEnabled");
                    v230 = (web::json::value *)web::json::value::at(v216, v350);
                    HIBYTE(v407) = web::json::value::as_bool(v230);
                    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v350);
                  }
                  else
                  {
                    HIBYTE(v407) = 0;
                  }
                  if ( v412 == v413 )
                  {
                    std::vector<EndpointDlp::DlpPolicy::ConditionalAppInfo>::_Emplace_reallocate<EndpointDlp::DlpPolicy::ConditionalAppInfo const &>(
                      v411,
                      v412,
                      v405);
                  }
                  else
                  {
                    EndpointDlp::DlpPolicy::ConditionalAppInfo::ConditionalAppInfo(
                      v412,
                      (const struct EndpointDlp::DlpPolicy::ConditionalAppInfo *)v405);
                    v412 = (EndpointDlp::DlpPolicy::ConditionalAppInfo *)((char *)v412 + 72);
                  }
                  v231 = (_QWORD *)std::map<std::wstring,std::vector<std::wstring>,EndpointDlp::Common::wstringOrdinalCompareInsensitive,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>>::_Try_emplace<std::wstring const &,>(
                                     (char *)v218 + 336,
                                     v399,
                                     v406);
                  std::vector<std::wstring>::_Emplace_one_at_back<std::wstring const &>(*v231 + 64LL, v408);
                }
                else
                {
                  v232 = EndpointDlp::TraceLoggingProvider::Instance();
                  v235 = *(_DWORD **)v232;
                  if ( **(_DWORD **)v232 > 5u )
                  {
                    v383[0] = L"App exe name is missing in AppGroup entry";
                    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
                      (_DWORD)v235,
                      (unsigned int)byte_1802C82B1,
                      v233,
                      v234,
                      (__int64)v383);
                  }
                }
                RealtimeProtection::DlpThrottle::DlpThrottleUnallowedAppsEvent::~DlpThrottleUnallowedAppsEvent((RealtimeProtection::DlpThrottle::DlpThrottleUnallowedAppsEvent *)v405);
                v216 = (web::json::value *)((char *)v216 + 8);
              }
              std::vector<web::json::value>::_Tidy(v381);
              i = v356;
              v200 = v393[0];
              v197 = v352;
            }
            v236 = (_QWORD *)std::map<std::wstring,EndpointDlp::DlpPolicy::ConditionalAppsGroupInfo,EndpointDlp::Common::wstringOrdinalCompareInsensitive,std::allocator<std::pair<std::wstring const,EndpointDlp::DlpPolicy::ConditionalAppsGroupInfo>>>::_Try_emplace<std::wstring const &,>(
                               (char *)v197 + 320,
                               v394,
                               v408);
            EndpointDlp::DlpPolicy::ConditionalAppsGroupInfo::operator=(*v236 + 64LL, v408);
          }
          else
          {
            v237 = EndpointDlp::TraceLoggingProvider::Instance();
            v240 = *(_DWORD **)v237;
            if ( **(_DWORD **)v237 > 5u )
            {
              v383[0] = L"App group id is missing from ApplicationGroupsSettings";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
                (_DWORD)v240,
                (unsigned int)&word_1802C836E,
                v238,
                v239,
                (__int64)v383);
            }
          }
          EndpointDlp::DlpPolicy::ConditionalAppsGroupInfo::~ConditionalAppsGroupInfo((EndpointDlp::DlpPolicy::ConditionalAppsGroupInfo *)v408);
          v198 = 1;
        }
        std::vector<web::json::value>::_Tidy(&v396);
      }
      std::unique_ptr<web::json::details::_Null>::~unique_ptr<web::json::details::_Null>(&v378);
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(&v385);
      v185 = v352;
    }
    std::unique_ptr<web::json::details::_Null>::~unique_ptr<web::json::details::_Null>(&SystemTimeAsFileTime);
  }
  std::wstring::wstring(v350, L"EnlightenedApplications");
  v241 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v379 + 8LL))(v379, v350);
  std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v350);
  if ( v241 )
  {
    SystemTimeAsFileTime = 0;
    std::wstring::wstring(v350, L"EnlightenedApplications");
    v242 = (const struct web::json::value *)web::json::value::at(&v379, v350);
    web::json::value::value((web::json::value *)&SystemTimeAsFileTime, v242);
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v350);
    if ( !web::json::value::is_null((web::json::value *)&SystemTimeAsFileTime) )
    {
      *(_OWORD *)v381 = 0;
      v382 = 0;
      v243 = web::json::value::as_array((web::json::value *)&SystemTimeAsFileTime);
      web::json::array::array((web::json::array *)v381, v243);
      v244 = v381[0];
      v245 = v381[1];
      while ( v244 != v245 )
      {
        v394[0] = 0;
        v394[1] = 0;
        v395.m128i_i64[0] = -1;
        v395.m128i_i64[1] = -1;
        std::wstring::wstring(v350, L"ProcessName");
        v246 = web::json::value::at(v244, v350);
        v247 = web::json::value::as_string(v246);
        std::wstring::wstring(Src, v247);
        std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v350);
        std::wstring::wstring(v380, L"MinVersion");
        v248 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**(_QWORD **)v244 + 8LL))(*(_QWORD *)v244, v380);
        std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v380);
        if ( v248 )
        {
          v378 = 0;
          std::wstring::wstring(v380, L"MinVersion");
          v249 = (const struct web::json::value *)web::json::value::at(v244, v380);
          web::json::value::value((web::json::value *)&v378, v249);
          std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v380);
          if ( web::json::value::is_null((web::json::value *)&v378) )
          {
            v253 = *(_OWORD *)v394;
          }
          else
          {
            std::wstring::wstring(&v385, L"MinVersion");
            v250 = web::json::value::at(v244, &v385);
            v251 = web::json::value::as_string(v250);
            std::wstring::wstring(v380, v251);
            std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(&v385);
            v383[0] = 0;
            v383[1] = 0;
            v252 = EndpointDlp::Common::VersionInfo::TryParse(v383, v380);
            wil::details::in1diag3::Throw_HrIfMsg(
              retaddr,
              (void *)0x2D2,
              (unsigned int)"src\\epp\\Dlp\\EndpointDlp\\Policy\\src\\dlpPolicy.cpp",
              (const char *)0x80004005LL,
              v252 ^ 1,
              (bool)"EnlightenedApplications has invalid min version format",
              v337);
            v253 = *(_OWORD *)v383;
            std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v380);
          }
          std::unique_ptr<web::json::details::_Null>::~unique_ptr<web::json::details::_Null>(&v378);
        }
        else
        {
          v253 = *(_OWORD *)v394;
        }
        std::wstring::wstring(v380, L"MaxVersion");
        v254 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**(_QWORD **)v244 + 8LL))(*(_QWORD *)v244, v380);
        std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v380);
        if ( v254 )
        {
          v378 = 0;
          std::wstring::wstring(v380, L"MaxVersion");
          v255 = (const struct web::json::value *)web::json::value::at(v244, v380);
          web::json::value::value((web::json::value *)&v378, v255);
          std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v380);
          if ( web::json::value::is_null((web::json::value *)&v378) )
          {
            v259 = v395;
          }
          else
          {
            std::wstring::wstring(&v385, L"MaxVersion");
            v256 = web::json::value::at(v244, &v385);
            v257 = web::json::value::as_string(v256);
            std::wstring::wstring(v380, v257);
            std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(&v385);
            v393[0] = 0;
            v393[1] = 0;
            v258 = EndpointDlp::Common::VersionInfo::TryParse(v393, v380);
            wil::details::in1diag3::Throw_HrIfMsg(
              retaddr,
              (void *)0x2E1,
              (unsigned int)"src\\epp\\Dlp\\EndpointDlp\\Policy\\src\\dlpPolicy.cpp",
              (const char *)0x80004005LL,
              v258 ^ 1,
              (bool)"EnlightenedApplications has invalid max version format",
              v337);
            v259 = *(__m128i *)v393;
            std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v380);
          }
          std::unique_ptr<web::json::details::_Null>::~unique_ptr<web::json::details::_Null>(&v378);
        }
        else
        {
          v259 = v395;
        }
        v260 = *(_QWORD *)std::map<std::wstring,EndpointDlp::DlpPolicy::EnlightenApplicationInfo>::_Try_emplace<std::wstring const &,>(
                            (char *)v185 + 352,
                            v399,
                            Src);
        *(_OWORD *)(v260 + 64) = v253;
        *(__m128i *)(v260 + 80) = v259;
        std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(Src);
        v244 = (web::json::value *)((char *)v244 + 8);
      }
      std::vector<web::json::value>::_Tidy(v381);
    }
    std::unique_ptr<web::json::details::_Null>::~unique_ptr<web::json::details::_Null>(&SystemTimeAsFileTime);
  }
  *((_DWORD *)v185 + 92) = -2;
  std::wstring::wstring(v350, L"ShowPredefinedBusinessJustificationMenu");
  v261 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v379 + 8LL))(v379, v350);
  std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v350);
  if ( v261 )
  {
    SystemTimeAsFileTime = 0;
    std::wstring::wstring(v350, L"ShowPredefinedBusinessJustificationMenu");
    v262 = (const struct web::json::value *)web::json::value::at(&v379, v350);
    web::json::value::value((web::json::value *)&SystemTimeAsFileTime, v262);
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v350);
    if ( web::json::value::is_integer((web::json::value *)&SystemTimeAsFileTime) )
      *((_DWORD *)v185 + 92) = web::json::value::as_integer((web::json::value *)&SystemTimeAsFileTime);
    std::unique_ptr<web::json::details::_Null>::~unique_ptr<web::json::details::_Null>(&SystemTimeAsFileTime);
  }
  std::wstring::wstring(v350, L"BusinessJustificationSettings");
  v263 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v379 + 8LL))(v379, v350);
  std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v350);
  if ( v263 )
  {
    SystemTimeAsFileTime = 0;
    std::wstring::wstring(v350, L"BusinessJustificationSettings");
    v264 = (const struct web::json::value *)web::json::value::at(&v379, v350);
    web::json::value::value((web::json::value *)&SystemTimeAsFileTime, v264);
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v350);
    if ( !web::json::value::is_null((web::json::value *)&SystemTimeAsFileTime)
      && web::json::value::is_string((web::json::value *)&SystemTimeAsFileTime) )
    {
      v265 = web::json::value::as_string(&SystemTimeAsFileTime);
      std::wstring::wstring(v401, v265);
      v378 = 0;
      web::json::value::value((web::json::value *)&v378);
      try
      {
        v266 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(v401);
        std::wstring::wstring(v350, v266);
        v267 = web::json::value::parse(v383, v350);
        web::json::value::operator=(&v378, v267);
        std::unique_ptr<web::json::details::_Null>::~unique_ptr<web::json::details::_Null>(v383);
        std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v350);
        v268 = v352;
      }
      catch ( web::json::json_exception *v374 )
      {
        v333 = EndpointDlp::TraceLoggingProvider::Instance();
        v334 = *(_DWORD **)v333;
        if ( **(_DWORD **)v333 > 2u )
        {
          v383[0] = (void *)(*(__int64 (__fastcall **)(web::json::json_exception *))(*(_QWORD *)v374 + 8LL))(v374);
          v393[0] = L"BusinessJustificationSettings Failed Parse";
          LODWORD(v352) = -2089484281;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>>(
            (int)v334,
            (int)&byte_1802C85D3,
            (__int64)&v352,
            (__int64)v393,
            (__int64)v383);
        }
        goto LABEL_387;
      }
      catch ( std::exception *v375 )
      {
        v335 = EndpointDlp::TraceLoggingProvider::Instance();
        v336 = *(_DWORD **)v335;
        if ( **(_DWORD **)v335 > 2u )
        {
          v383[0] = (void *)(*(__int64 (__fastcall **)(std::exception *))(*(_QWORD *)v375 + 8LL))(v375);
          v393[0] = L"BusinessJustificationSettings Failed Parse";
          LODWORD(v352) = -2147418113;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<char>>(
            (int)v336,
            (int)&dword_1802C8ADC,
            (__int64)&v352,
            (__int64)v393,
            (__int64)v383);
        }
LABEL_387:
        v268 = v355;
        v352 = v355;
        v6 = v351;
        si128 = _mm_load_si128((const __m128i *)&_xmm);
      }
      v269 = 1;
      if ( !web::json::value::is_null((web::json::value *)&v378)
        && web::json::value::is_array((web::json::value *)&v378) )
      {
        *(_OWORD *)v399 = 0;
        v400 = 0;
        v270 = web::json::value::as_array((web::json::value *)&v378);
        web::json::array::array((web::json::array *)v399, v270);
        v271 = v399[0];
        v272 = v399[1];
        while ( v271 != v272 )
        {
          std::wstring::wstring(v380, L"Id");
          v6 |= 0x100u;
          v351 = v6;
          if ( !(*(unsigned __int8 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*v271 + 8LL))(*v271, v380)
            || (std::wstring::wstring(v350, L"Id"),
                v6 |= 0x200u,
                v351 = v6,
                v273 = (web::json::value *)web::json::value::at(v271, v350),
                v274 = 0,
                web::json::value::is_null(v273)) )
          {
            v274 = 1;
          }
          if ( (v6 & 0x200) != 0 )
          {
            v6 &= ~0x200u;
            std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v350);
          }
          if ( (v6 & 0x100) != 0 )
          {
            v6 &= ~0x100u;
            std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v380);
          }
          if ( v274 )
          {
            v275 = EndpointDlp::TraceLoggingProvider::Instance();
            if ( **(_DWORD **)v275 > 5u && (unsigned __int8)tlgKeywordOn(*(_QWORD *)v275, 0) )
            {
              v383[0] = L"Dlp policy entry for BusinessJustificationSettings missing Id";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
                v276,
                (unsigned int)&word_1802C842E,
                v277,
                v278,
                (__int64)v383);
            }
          }
          else
          {
            std::wstring::wstring(v350, L"Id");
            v279 = web::json::value::at(v271, v350);
            v280 = web::json::value::as_string(v279);
            std::wstring::wstring(Src, v280);
            std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v350);
            v346 = 0;
            std::wstring::wstring(&v385, L"Enable");
            v281 = v6 | 0x400;
            v351 = v281;
            if ( !(*(unsigned __int8 (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)*v271 + 8LL))(*v271, &v385)
              || (std::wstring::wstring(v380, L"Enable"),
                  v281 |= 0x800u,
                  v351 = v281,
                  v282 = (web::json::value *)web::json::value::at(v271, v380),
                  v283 = 1,
                  web::json::value::is_null(v282)) )
            {
              v283 = 0;
            }
            if ( (v281 & 0x800) != 0 )
            {
              v281 &= ~0x800u;
              std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v380);
            }
            if ( (v281 & 0x400) != 0 )
            {
              v281 &= ~0x400u;
              std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(&v385);
            }
            if ( v283 )
            {
              std::wstring::wstring(v380, L"Enable");
              v284 = (web::json::value *)web::json::value::at(v271, v380);
              v346 = web::json::value::as_bool(v284);
              std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v380);
            }
            EndpointDlp::DlpPolicy::BusinessJustificationOption::BusinessJustificationOption((EndpointDlp::DlpPolicy::BusinessJustificationOption *)v402);
            v402[0] = v346;
            std::wstring::wstring(v380, L"justificationText");
            v6 = v281 | 0x1000;
            v351 = v6;
            if ( !(*(unsigned __int8 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*v271 + 8LL))(*v271, v380)
              || (std::wstring::wstring(v350, L"justificationText"),
                  v6 |= 0x2000u,
                  v351 = v6,
                  v285 = (web::json::value *)web::json::value::at(v271, v350),
                  web::json::value::is_null(v285)) )
            {
              v269 = 0;
            }
            if ( (v6 & 0x2000) != 0 )
            {
              v6 &= ~0x2000u;
              std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v350);
            }
            if ( (v6 & 0x1000) != 0 )
            {
              v6 &= ~0x1000u;
              std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v380);
            }
            if ( v269 )
            {
              *(_OWORD *)v381 = 0;
              v382 = 0;
              std::wstring::wstring(v350, L"justificationText");
              v286 = (web::json::value *)web::json::value::at(v271, v350);
              v287 = web::json::value::as_array(v286);
              web::json::array::array((web::json::array *)v381, v287);
              std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v350);
              v288 = v381[0];
              v289 = v381[1];
              while ( v288 != v289 )
              {
                if ( web::json::value::is_null(v288) || !web::json::value::is_string(v288) )
                {
                  v302 = EndpointDlp::TraceLoggingProvider::Instance();
                  if ( **(_DWORD **)v302 > 5u && (unsigned __int8)tlgKeywordOn(*(_QWORD *)v302, 0) )
                  {
                    v383[0] = L"Dlp policy entry for justificationText was unexpected type";
                    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
                      v303,
                      (unsigned int)&byte_1802C8BB7,
                      v304,
                      v305,
                      (__int64)v383);
                  }
                }
                else
                {
                  v290 = web::json::value::as_string(v288);
                  std::wstring::wstring(v398, v290);
                  memset(v414, 0, 0xF8u);
                  std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(
                    v414,
                    v398);
                  *(_OWORD *)v394 = 0;
                  v395 = si128;
                  LOWORD(v394[0]) = 0;
                  v291 = std::getline<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(v414, v394, 58);
                  if ( (*(_BYTE *)(*(int *)(*(_QWORD *)v291 + 4LL) + v291 + 16) & 6) != 0 )
                  {
                    v292 = EndpointDlp::TraceLoggingProvider::Instance();
                    if ( **(_DWORD **)v292 > 5u && (unsigned __int8)tlgKeywordOn(*(_QWORD *)v292, 0) )
                    {
                      v383[0] = L"Dlp policy entry for justificationText ill-formatted";
                      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
                        v293,
                        (unsigned int)byte_1802C8BDB,
                        v294,
                        v295,
                        (__int64)v383);
                    }
                  }
                  else
                  {
                    v396 = 0;
                    v397 = si128;
                    LOWORD(v396) = 0;
                    v296 = std::getline<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>(v414, &v396);
                    if ( (*(_BYTE *)(*(int *)(*(_QWORD *)v296 + 4LL) + v296 + 16) & 6) != 0 )
                    {
                      v297 = EndpointDlp::TraceLoggingProvider::Instance();
                      if ( **(_DWORD **)v297 > 5u && (unsigned __int8)tlgKeywordOn(*(_QWORD *)v297, 0) )
                      {
                        v383[0] = L"Dlp policy entry for justificationText ill-formatted";
                        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
                          v298,
                          (unsigned int)word_1802C834A,
                          v299,
                          v300,
                          (__int64)v383);
                      }
                    }
                    else
                    {
                      v301 = (void *)std::map<std::wstring,std::wstring,EndpointDlp::Common::wstringCompareInsensitive,std::allocator<std::pair<std::wstring const,std::wstring>>>::operator[](
                                       v403,
                                       v394);
                      std::wstring::operator=(v301, &v396);
                    }
                    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(&v396);
                  }
                  std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v394);
                  std::basic_stringstream<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::`vbase destructor'(v414);
                  std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v398);
                }
                v288 = (web::json::value *)((char *)v288 + 8);
              }
              std::vector<web::json::value>::_Tidy(v381);
              v268 = v352;
            }
            v306 = *(_QWORD *)std::map<std::wstring,EndpointDlp::DlpPolicy::BusinessJustificationOption,EndpointDlp::Common::wstringCompareInsensitive,std::allocator<std::pair<std::wstring const,EndpointDlp::DlpPolicy::BusinessJustificationOption>>>::_Try_emplace<std::wstring const &,>(
                                (char *)v268 + 712,
                                v393,
                                Src);
            *(_BYTE *)(v306 + 64) = v402[0];
            v307 = v306 + 72;
            if ( (_BYTE *)(v306 + 72) != v403 )
            {
              std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,EndpointDlp::Common::wstringCompareInsensitive,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::clear(v306 + 72);
              std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,EndpointDlp::Common::wstringCompareInsensitive,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Copy<0>(
                v307,
                v403);
            }
            std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,EndpointDlp::Common::wstringCompareInsensitive,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,EndpointDlp::Common::wstringCompareInsensitive,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(v403);
            std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(Src);
          }
          ++v271;
          v269 = 1;
        }
        std::vector<web::json::value>::_Tidy(v399);
      }
      std::unique_ptr<web::json::details::_Null>::~unique_ptr<web::json::details::_Null>(&v378);
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v401);
      v185 = v352;
    }
    std::unique_ptr<web::json::details::_Null>::~unique_ptr<web::json::details::_Null>(&SystemTimeAsFileTime);
  }
  std::wstring::wstring(v350, L"JitNotificationSettings");
  has_field = web::json::value::has_field(&v379, v350);
  std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v350);
  if ( has_field )
  {
    v378 = 0;
    std::wstring::wstring(v350, L"JitNotificationSettings");
    v309 = (const struct web::json::value *)web::json::value::at(&v379, v350);
    web::json::value::value((web::json::value *)&v378, v309);
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v350);
    std::wstring::wstring(v380, L"JitNotificationTitle");
    v310 = web::json::value::has_field(&v378, v380);
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v380);
    if ( v310 )
    {
      SystemTimeAsFileTime = 0;
      std::wstring::wstring(v380, L"JitNotificationTitle");
      v311 = (const struct web::json::value *)web::json::value::at(&v378, v380);
      web::json::value::value((web::json::value *)&SystemTimeAsFileTime, v311);
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v380);
      if ( web::json::value::is_string((web::json::value *)&SystemTimeAsFileTime) )
      {
        v312 = (void *)web::json::value::as_string(&SystemTimeAsFileTime);
        std::wstring::operator=((char *)v185 + 728, v312);
      }
      std::unique_ptr<web::json::details::_Null>::~unique_ptr<web::json::details::_Null>(&SystemTimeAsFileTime);
    }
    std::wstring::wstring(v380, L"JitNotificationContent");
    v313 = web::json::value::has_field(&v378, v380);
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v380);
    if ( v313 )
    {
      SystemTimeAsFileTime = 0;
      std::wstring::wstring(v380, L"JitNotificationContent");
      v314 = (const struct web::json::value *)web::json::value::at(&v378, v380);
      web::json::value::value((web::json::value *)&SystemTimeAsFileTime, v314);
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v380);
      if ( web::json::value::is_string((web::json::value *)&SystemTimeAsFileTime) )
      {
        v315 = (void *)web::json::value::as_string(&SystemTimeAsFileTime);
        std::wstring::operator=((char *)v185 + 760, v315);
      }
      std::unique_ptr<web::json::details::_Null>::~unique_ptr<web::json::details::_Null>(&SystemTimeAsFileTime);
    }
    std::unique_ptr<web::json::details::_Null>::~unique_ptr<web::json::details::_Null>(&v378);
  }
  *((_DWORD *)v185 + 93) = -2;
  std::wstring::wstring(v350, L"IconOverlay");
  v316 = web::json::value::has_field(&v379, v350);
  std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v350);
  if ( v316 )
  {
    SystemTimeAsFileTime = 0;
    std::wstring::wstring(v350, L"IconOverlay");
    v317 = (const struct web::json::value *)web::json::value::at(&v379, v350);
    web::json::value::value((web::json::value *)&SystemTimeAsFileTime, v317);
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v350);
    if ( web::json::value::is_integer((web::json::value *)&SystemTimeAsFileTime) )
      *((_DWORD *)v185 + 93) = web::json::value::as_integer((web::json::value *)&SystemTimeAsFileTime);
    std::unique_ptr<web::json::details::_Null>::~unique_ptr<web::json::details::_Null>(&SystemTimeAsFileTime);
  }
  std::unique_ptr<web::json::details::_Null>::~unique_ptr<web::json::details::_Null>(&v379);
  return v185;
}

```

## disassembly

```asm
0x1800c2b44  mov     rax, rsp
0x1800c2b47  push    rbx
0x1800c2b48  push    rsi
0x1800c2b49  push    rdi
0x1800c2b4a  push    r12
0x1800c2b4c  push    r13
0x1800c2b4e  push    r14
0x1800c2b50  push    r15
0x1800c2b52  sub     rsp, 750h
0x1800c2b59  movaps  xmmword ptr [rax-48h], xmm6
0x1800c2b5d  movaps  xmmword ptr [rax-58h], xmm7
0x1800c2b61  movaps  xmmword ptr [rax-68h], xmm8
0x1800c2b66  mov     rax, cs:__security_cookie
0x1800c2b6d  xor     rax, rsp
0x1800c2b70  mov     [rsp+788h+var_78], rax
0x1800c2b78  mov     rsi, r8
0x1800c2b7b  mov     r14, rcx
0x1800c2b7e  mov     [rsp+788h+var_718], rcx
0x1800c2b83  mov     [rsp+788h+var_700], rcx
0x1800c2b8b  mov     [rsp+788h+var_710], r9b
0x1800c2b90  xor     r15d, r15d
0x1800c2b93  mov     [rsp+788h+var_744], r15d
0x1800c2b98  mov     r13d, r15d
0x1800c2b9b  mov     [rsp+788h+var_720], r15d
0x1800c2ba0  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800c2ba5  nop
0x1800c2ba6  lea     rdi, [r14+20h]
0x1800c2baa  xorps   xmm0, xmm0
0x1800c2bad  movups  xmmword ptr [rdi], xmm0
0x1800c2bb0  mov     [rdi+10h], r15
0x1800c2bb4  lea     ebx, [r15+7]
0x1800c2bb8  mov     [rdi+18h], rbx
0x1800c2bbc  mov     [rdi], r15w
0x1800c2bc0  movups  xmmword ptr [r14+40h], xmm0
0x1800c2bc5  mov     [r14+50h], r15
0x1800c2bc9  mov     [r14+58h], rbx
0x1800c2bcd  mov     [r14+40h], r15w
0x1800c2bd2  lea     rax, [r14+70h]
0x1800c2bd6  mov     [rsp+788h+var_6C0], rax
0x1800c2bde  mov     [rsp+788h+var_6A8], rax
0x1800c2be6  movups  xmmword ptr [rax], xmm0
0x1800c2be9  mov     [rax+10h], r15
0x1800c2bed  mov     [rax+18h], rbx
0x1800c2bf1  mov     [rax], r15w
0x1800c2bf5  lea     rax, [r14+90h]
0x1800c2bfc  mov     [rsp+788h+var_6B8], rax
0x1800c2c04  mov     [rsp+788h+var_4F8], rax
0x1800c2c0c  movups  xmmword ptr [rax], xmm0
0x1800c2c0f  mov     [rax+10h], r15
0x1800c2c13  mov     [rax+18h], rbx
0x1800c2c17  mov     [rax], r15w
0x1800c2c1b  mov     [r14+0B2h], r15w
0x1800c2c23  mov     [r14+0B4h], r15d
0x1800c2c2a  lea     rax, [r14+0B8h]
0x1800c2c31  mov     [rsp+788h+var_6F0], rax
0x1800c2c39  mov     [rax], r15
0x1800c2c3c  lea     rax, [r14+0C0h]
0x1800c2c43  mov     [rsp+788h+var_6A0], rax
0x1800c2c4b  mov     [rax], r15
0x1800c2c4e  lea     rax, [r14+0C8h]
0x1800c2c55  mov     [rsp+788h+var_6E0], rax
0x1800c2c5d  mov     [rax], r15
0x1800c2c60  lea     rcx, [r14+0D0h]
0x1800c2c67  mov     [rsp+788h+var_6B0], rcx
0x1800c2c6f  call    ??0?$set@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UwstringOrdinalCompareInsensitive@Common@EndpointDlp@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::set<std::wstring,EndpointDlp::Common::wstringOrdinalCompareInsensitive,std::allocator<std::wstring>>::set<std::wstring,EndpointDlp::Common::wstringOrdinalCompareInsensitive,std::allocator<std::wstring>>(void)
0x1800c2c74  nop
0x1800c2c75  lea     rcx, [r14+0E0h]
0x1800c2c7c  mov     [rsp+788h+var_488], rcx
0x1800c2c84  call    ??0?$set@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UwstringOrdinalCompareInsensitive@Common@EndpointDlp@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::set<std::wstring,EndpointDlp::Common::wstringOrdinalCompareInsensitive,std::allocator<std::wstring>>::set<std::wstring,EndpointDlp::Common::wstringOrdinalCompareInsensitive,std::allocator<std::wstring>>(void)
0x1800c2c89  nop
0x1800c2c8a  lea     rcx, [r14+0F0h]
0x1800c2c91  mov     qword ptr [rsp+788h+var_518], rcx
0x1800c2c99  call    ??0?$set@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UwstringOrdinalCompareInsensitive@Common@EndpointDlp@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::set<std::wstring,EndpointDlp::Common::wstringOrdinalCompareInsensitive,std::allocator<std::wstring>>::set<std::wstring,EndpointDlp::Common::wstringOrdinalCompareInsensitive,std::allocator<std::wstring>>(void)
0x1800c2c9e  nop
0x1800c2c9f  lea     rcx, [r14+100h]
0x1800c2ca6  mov     [rsp+788h+var_6D0], rcx
0x1800c2cae  call    ??0?$set@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UwstringOrdinalCompareInsensitive@Common@EndpointDlp@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::set<std::wstring,EndpointDlp::Common::wstringOrdinalCompareInsensitive,std::allocator<std::wstring>>::set<std::wstring,EndpointDlp::Common::wstringOrdinalCompareInsensitive,std::allocator<std::wstring>>(void)
0x1800c2cb3  nop
0x1800c2cb4  lea     rcx, [r14+110h]
0x1800c2cbb  mov     [rsp+788h+var_6C8], rcx
0x1800c2cc3  call    ??0?$set@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UwstringOrdinalCompareInsensitive@Common@EndpointDlp@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::set<std::wstring,EndpointDlp::Common::wstringOrdinalCompareInsensitive,std::allocator<std::wstring>>::set<std::wstring,EndpointDlp::Common::wstringOrdinalCompareInsensitive,std::allocator<std::wstring>>(void)
0x1800c2cc8  nop
0x1800c2cc9  lea     rax, [r14+120h]
0x1800c2cd0  mov     [rsp+788h+var_4C0], rax
0x1800c2cd8  mov     [rsp+788h+var_6F8], rax
0x1800c2ce0  xorps   xmm0, xmm0
0x1800c2ce3  movups  xmmword ptr [rax], xmm0
0x1800c2ce6  mov     [rax+10h], r15
0x1800c2cea  mov     [rax+18h], rbx
0x1800c2cee  mov     [rax], r15w
0x1800c2cf2  lea     rbx, [r14+140h]
0x1800c2cf9  mov     [rbx], r15
0x1800c2cfc  mov     [rbx+8], r15
0x1800c2d00  mov     ecx, 0B8h; Size
0x1800c2d05  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800c2d0a  mov     [rax], rax
0x1800c2d0d  mov     [rax+8], rax
0x1800c2d11  mov     [rax+10h], rax
0x1800c2d15  lea     r12d, [r15+1]
0x1800c2d19  mov     word ptr [rax+18h], 101h
0x1800c2d1f  mov     [rbx], rax
0x1800c2d22  lea     rbx, [r14+150h]
0x1800c2d29  mov     [rbx], r15
0x1800c2d2c  mov     [rbx+8], r15
0x1800c2d30  call    ??$_Buyheadnode@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@@std@@PEAX@std@@@std@@@?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@@std@@PEAX@std@@SAPEAU01@AEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@@std@@PEAX@std@@@1@@Z; std::_Tree_node<std::pair<std::wstring const,std::vector<std::wstring>>,void *>::_Buyheadnode<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::vector<std::wstring>>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,std::vector<std::wstring>>,void *>> &)
0x1800c2d35  mov     [rbx], rax
0x1800c2d38  lea     rbx, [r14+160h]
0x1800c2d3f  mov     [rbx], r15
0x1800c2d42  mov     [rbx+8], r15
0x1800c2d46  mov     ecx, r12d
0x1800c2d49  call    ??$_Get_size_of_n@$0GA@@std@@YA_K_K@Z; std::_Get_size_of_n<96>(unsigned __int64)
0x1800c2d4e  mov     rcx, rax
0x1800c2d51  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x1800c2d56  mov     [rax], rax
0x1800c2d59  mov     [rax+8], rax
0x1800c2d5d  mov     [rax+10h], rax
0x1800c2d61  mov     word ptr [rax+18h], 101h
0x1800c2d67  mov     [rbx], rax
0x1800c2d6a  mov     dword ptr [r14+170h], 0FFFFFFFEh
0x1800c2d75  mov     dword ptr [r14+174h], 0FFFFFFFEh
0x1800c2d80  mov     [r14+178h], r15d
0x1800c2d87  lea     rbx, [r14+180h]
0x1800c2d8e  mov     [rbx], r15
0x1800c2d91  mov     [rbx+8], r15
0x1800c2d95  call    ??$_Buyheadnode@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@W4DomainAccessType@DlpPolicy@EndpointDlp@@@std@@PEAX@std@@@std@@@?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@W4DomainAccessType@DlpPolicy@EndpointDlp@@@std@@PEAX@std@@SAPEAU01@AEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@W4DomainAccessType@DlpPolicy@EndpointDlp@@@std@@PEAX@std@@@1@@Z; std::_Tree_node<std::pair<std::wstring const,EndpointDlp::DlpPolicy::DomainAccessType>,void *>::_Buyheadnode<std::allocator<std::_Tree_node<std::pair<std::wstring const,EndpointDlp::DlpPolicy::DomainAccessType>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,EndpointDlp::DlpPolicy::DomainAccessType>,void *>> &)
0x1800c2d9a  mov     [rbx], rax
0x1800c2d9d  lea     rbx, [r14+190h]
0x1800c2da4  mov     [rbx], r15
0x1800c2da7  mov     [rbx+8], r15
0x1800c2dab  call    ??$_Buyheadnode@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@W4DomainAccessType@DlpPolicy@EndpointDlp@@@std@@PEAX@std@@@std@@@?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@W4DomainAccessType@DlpPolicy@EndpointDlp@@@std@@PEAX@std@@SAPEAU01@AEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@W4DomainAccessType@DlpPolicy@EndpointDlp@@@std@@PEAX@std@@@1@@Z; std::_Tree_node<std::pair<std::wstring const,EndpointDlp::DlpPolicy::DomainAccessType>,void *>::_Buyheadnode<std::allocator<std::_Tree_node<std::pair<std::wstring const,EndpointDlp::DlpPolicy::DomainAccessType>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,EndpointDlp::DlpPolicy::DomainAccessType>,void *>> &)
0x1800c2db0  mov     [rbx], rax
0x1800c2db3  mov     [r14+1A1h], r15d
0x1800c2dba  mov     [r14+1A5h], r15b
0x1800c2dc1  mov     dword ptr [r14+1BCh], 2
0x1800c2dcc  lea     rcx, [r14+1C0h]
0x1800c2dd3  mov     [rsp+788h+var_6E8], rcx
0x1800c2ddb  lea     rdx, a6abb5bf87ae64f_2; "6abb5bf8-7ae6-4f97-9c9a-9fcb60c0f230:00"...
0x1800c2de2  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800c2de7  nop
0x1800c2de8  lea     rcx, [r14+1E0h]
0x1800c2def  lea     rdx, a6abb5bf87ae64f_3; "6abb5bf8-7ae6-4f97-9c9a-9fcb60c0f230:6b"...
0x1800c2df6  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800c2dfb  nop
0x1800c2dfc  lea     rcx, [r14+200h]
0x1800c2e03  mov     [rsp+788h+var_538], rcx
0x1800c2e0b  lea     rdx, a6abb5bf87ae64f_1; "6abb5bf8-7ae6-4f97-9c9a-9fcb60c0f230:3c"...
0x1800c2e12  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800c2e17  nop
0x1800c2e18  lea     rcx, [r14+220h]
0x1800c2e1f  mov     [rsp+788h+var_4D8], rcx
0x1800c2e27  lea     rdx, a6abb5bf87ae64f; "6abb5bf8-7ae6-4f97-9c9a-9fcb60c0f230:2e"...
0x1800c2e2e  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800c2e33  nop
0x1800c2e34  lea     rcx, [r14+240h]
0x1800c2e3b  mov     [rsp+788h+var_558], rcx
0x1800c2e43  lea     rdx, a6abb5bf87ae64f_4; "6abb5bf8-7ae6-4f97-9c9a-9fcb60c0f230:3c"...
0x1800c2e4a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800c2e4f  nop
0x1800c2e50  lea     rcx, [r14+260h]
0x1800c2e57  mov     [rsp+788h+var_5D0], rcx
0x1800c2e5f  lea     rdx, a6abb5bf87ae64f_0; "6abb5bf8-7ae6-4f97-9c9a-9fcb60c0f230:16"...
0x1800c2e66  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800c2e6b  nop
0x1800c2e6c  lea     rbx, [r14+288h]
0x1800c2e73  mov     [rbx], r15
0x1800c2e76  mov     [rbx+8], r15
0x1800c2e7a  mov     ecx, 360h; Size
0x1800c2e7f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800c2e84  mov     [rax], rax
0x1800c2e87  mov     [rax+8], rax
0x1800c2e8b  mov     [rax+10h], rax
0x1800c2e8f  mov     word ptr [rax+18h], 101h
0x1800c2e95  mov     [rbx], rax
0x1800c2e98  lea     rbx, [r14+298h]
0x1800c2e9f  mov     [rbx], r15
0x1800c2ea2  mov     [rbx+8], r15
0x1800c2ea6  mov     ecx, r12d
0x1800c2ea9  call    ??$_Get_size_of_n@$0FA@@std@@YA_K_K@Z; std::_Get_size_of_n<80>(unsigned __int64)
0x1800c2eae  mov     rcx, rax
0x1800c2eb1  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x1800c2eb6  mov     [rax], rax
0x1800c2eb9  mov     [rax+8], rax
0x1800c2ebd  mov     [rax+10h], rax
0x1800c2ec1  mov     word ptr [rax+18h], 101h
0x1800c2ec7  mov     [rbx], rax
0x1800c2eca  lea     rcx, [r14+2A8h]
0x1800c2ed1  call    ??0?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@UwstringCompareInsensitive@Common@EndpointDlp@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@@std@@@2@@std@@QEAA@XZ; std::map<std::wstring,std::vector<std::wstring>,EndpointDlp::Common::wstringCompareInsensitive,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>>::map<std::wstring,std::vector<std::wstring>,EndpointDlp::Common::wstringCompareInsensitive,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>>(void)
0x1800c2ed6  nop
0x1800c2ed7  lea     rcx, [r14+2B8h]
0x1800c2ede  call    ??0?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@UwstringCompareInsensitive@Common@EndpointDlp@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@2@@std@@@2@@std@@QEAA@XZ; std::map<std::wstring,std::vector<std::wstring>,EndpointDlp::Common::wstringCompareInsensitive,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>>::map<std::wstring,std::vector<std::wstring>,EndpointDlp::Common::wstringCompareInsensitive,std::allocator<std::pair<std::wstring const,std::vector<std::wstring>>>>(void)
0x1800c2ee3  nop
0x1800c2ee4  lea     rbx, [r14+2C8h]
0x1800c2eeb  mov     [rbx], r15
0x1800c2eee  mov     [rbx+8], r15
0x1800c2ef2  lea     ecx, [r15+58h]; Size
0x1800c2ef6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800c2efb  mov     [rax], rax
0x1800c2efe  mov     [rax+8], rax
0x1800c2f02  mov     [rax+10h], rax
0x1800c2f06  mov     word ptr [rax+18h], 101h
0x1800c2f0c  mov     [rbx], rax
0x1800c2f0f  xorps   xmm0, xmm0
0x1800c2f12  movups  xmmword ptr [r14+2D8h], xmm0
0x1800c2f1a  mov     [r14+2E8h], r15
0x1800c2f21  mov     qword ptr [r14+2F0h], 7
0x1800c2f2c  mov     [r14+2D8h], r15w
0x1800c2f34  movups  xmmword ptr [r14+2F8h], xmm0
0x1800c2f3c  mov     [r14+308h], r15
0x1800c2f43  mov     qword ptr [r14+310h], 7
0x1800c2f4e  mov     [r14+2F8h], r15w
0x1800c2f56  lea     rbx, [r14+318h]
0x1800c2f5d  mov     [rbx], r15
0x1800c2f60  mov     [rbx+8], r15
0x1800c2f64  call    ??$_Buyheadnode@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@PEAX@std@@@std@@@?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@PEAX@std@@SAPEAU01@AEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@std@@PEAX@std@@@1@@Z; std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>::_Buyheadnode<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>> &)
0x1800c2f69  mov     [rbx], rax
0x1800c2f6c  lea     rcx, [r14+328h]
0x1800c2f73  call    ??0?$set@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UwstringOrdinalCompareInsensitive@Common@EndpointDlp@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::set<std::wstring,EndpointDlp::Common::wstringOrdinalCompareInsensitive,std::allocator<std::wstring>>::set<std::wstring,EndpointDlp::Common::wstringOrdinalCompareInsensitive,std::allocator<std::wstring>>(void)
0x1800c2f78  nop
0x1800c2f79  lea     rcx, [r14+338h]
0x1800c2f80  call    ??0?$set@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UwstringOrdinalCompareInsensitive@Common@EndpointDlp@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::set<std::wstring,EndpointDlp::Common::wstringOrdinalCompareInsensitive,std::allocator<std::wstring>>::set<std::wstring,EndpointDlp::Common::wstringOrdinalCompareInsensitive,std::allocator<std::wstring>>(void)
0x1800c2f85  nop
0x1800c2f86  mov     [r14+348h], r15
0x1800c2f8d  lea     rcx, [r14+350h]
0x1800c2f94  call    ??0?$set@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UwstringOrdinalCompareInsensitive@Common@EndpointDlp@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::set<std::wstring,EndpointDlp::Common::wstringOrdinalCompareInsensitive,std::allocator<std::wstring>>::set<std::wstring,EndpointDlp::Common::wstringOrdinalCompareInsensitive,std::allocator<std::wstring>>(void)
0x1800c2f99  nop
0x1800c2f9a  lea     rcx, [r14+360h]
0x1800c2fa1  call    ??0?$set@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@UwstringOrdinalCompareInsensitive@Common@EndpointDlp@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::set<std::wstring,EndpointDlp::Common::wstringOrdinalCompareInsensitive,std::allocator<std::wstring>>::set<std::wstring,EndpointDlp::Common::wstringOrdinalCompareInsensitive,std::allocator<std::wstring>>(void)
0x1800c2fa6  nop
0x1800c2fa7  mov     [r14+370h], r15
0x1800c2fae  mov     [r14+378h], r15
0x1800c2fb5  mov     [r14+380h], r15
0x1800c2fbc  mov     [r14+388h], r15b
0x1800c2fc3  mov     [r14+38Bh], r15w
0x1800c2fcb  lea     rdx, aAadtenantid_0; "AadTenantId"
0x1800c2fd2  lea     rcx, [rsp+788h+Src]
0x1800c2fda  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800c2fdf  nop
0x1800c2fe0  lea     rdx, [rsp+788h+Src]
0x1800c2fe8  mov     rcx, rsi
0x1800c2feb  call    ?at@value@json@web@@QEBAAEBV123@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::at(std::wstring const &)
0x1800c2ff0  mov     rcx, rax
0x1800c2ff3  call    ?as_string@value@json@web@@QEBAAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; web::json::value::as_string(void)
0x1800c2ff8  mov     rdx, rax; Src
0x1800c2ffb  mov     rcx, rdi; void *
0x1800c2ffe  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800c3003  nop
0x1800c3004  lea     rcx, [rsp+788h+Src]; void *
0x1800c300c  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x1800c3011  mov     [rsp+788h+var_618], r15
0x1800c3019  lea     rdx, aPolicy; "Policy"
0x1800c3020  lea     rcx, [rsp+788h+var_648]
0x1800c3028  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800c302d  nop
0x1800c302e  lea     rdx, [rsp+788h+var_648]
0x1800c3036  mov     rcx, rsi
0x1800c3039  call    ?at@value@json@web@@QEBAAEBV123@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::at(std::wstring const &)
0x1800c303e  mov     rdx, rax; struct web::json::value *
0x1800c3041  lea     rcx, [rsp+788h+var_618]; this
0x1800c3049  call    ??0value@json@web@@QEAA@AEBV012@@Z; web::json::value::value(web::json::value const &)
0x1800c304e  nop
0x1800c304f  lea     rcx, [rsp+788h+var_648]; void *
0x1800c3057  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x1800c305c  lea     rdx, aLastdlppolicyu; "LastDlpPolicyUpdateTimeUtc"
0x1800c3063  lea     rcx, [rsp+788h+var_5F0]
0x1800c306b  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800c3070  nop
0x1800c3071  lea     rdx, [rsp+788h+var_5F0]
0x1800c3079  lea     rcx, [rsp+788h+var_618]
0x1800c3081  call    ?has_string_field@value@json@web@@QEBA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::has_string_field(std::wstring const &)
0x1800c3086  test    al, al
0x1800c3088  jz      short loc_1800C30DA
0x1800c308a  lea     rdx, aLastdlppolicyu; "LastDlpPolicyUpdateTimeUtc"
0x1800c3091  lea     rcx, [rsp+788h+Src]
0x1800c3099  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800c309e  nop
0x1800c309f  mov     esi, r12d
0x1800c30a2  mov     [rsp+788h+var_744], esi
0x1800c30a6  lea     rdx, [rsp+788h+Src]
0x1800c30ae  lea     rcx, [rsp+788h+var_618]
0x1800c30b6  call    ?at@value@json@web@@QEAAAEAV123@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; web::json::value::at(std::wstring const &)
0x1800c30bb  mov     rcx, rax
0x1800c30be  call    ?as_string@value@json@web@@QEBAAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; web::json::value::as_string(void)
0x1800c30c3  mov     rdx, rax
0x1800c30c6  lea     rcx, [rsp+788h+var_610]
0x1800c30ce  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800c30d3  nop
0x1800c30d4  lea     r12d, [r15+3]
0x1800c30d8  jmp     short loc_1800C30F7
0x1800c30da  lea     rdx, qword_18025C818
0x1800c30e1  lea     rcx, [rsp+788h+var_740]
0x1800c30e6  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x1800c30eb  nop
0x1800c30ec  mov     r12d, 4
0x1800c30f2  lea     esi, [r12-3]
0x1800c30f7  mov     [rsp+788h+var_744], r12d
0x1800c30fc  mov     rdx, rax; Src
0x1800c30ff  lea     rcx, [r14+40h]; void *
0x1800c3103  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800c3108  nop
0x1800c3109  test    r12b, 4
  ... truncated ...
```
