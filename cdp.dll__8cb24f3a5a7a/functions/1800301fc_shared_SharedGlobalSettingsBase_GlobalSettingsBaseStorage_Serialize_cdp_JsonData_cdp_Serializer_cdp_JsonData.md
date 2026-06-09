# shared::SharedGlobalSettingsBase::GlobalSettingsBaseStorage::Serialize<cdp::JsonData>(cdp::Serializer<cdp::JsonData> &)

- ea: `0x1800301fc`
- end: `0x180033155`
- name: `??$Serialize@UJsonData@cdp@@@GlobalSettingsBaseStorage@SharedGlobalSettingsBase@shared@@QEBAXAEAV?$Serializer@UJsonData@cdp@@@cdp@@@Z`
- size: `12121`
- prototype: ``
- caller_count: `1`
- callee_count: `41`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180100950`

## callees

- `0x180010ee0`
- `0x1800113bc`
- `0x1800117f8`
- `0x18002ead4`
- `0x180030190`
- `0x1800301fc`
- `0x18003315c`
- `0x1800332b8`
- `0x1800334ac`
- `0x1800336a0`
- `0x180033978`
- `0x1800344dc`
- `0x18007e71c`
- `0x1800b1cf0`
- `0x1800b46a0`
- `0x1800ca314`
- `0x1800d2db0`
- `0x1800dd158`
- `0x1800e4068`
- `0x1800e5184`
- `0x1800e75d8`
- `0x1800ea91c`
- `0x1800f513c`
- `0x1800fbd70`
- `0x180102d38`
- `0x1801073e0`
- `0x18011d5d0`
- `0x18011d808`
- `0x18017258c`
- `0x18017b334`
- `0x180184d00`
- `0x180184da0`
- `0x180184e98`
- `0x180190fa4`
- `0x1801a03b8`
- `0x1801f6fb0`
- `0x1801fd770`
- `0x1801fdcc0`
- `0x1801fde00`
- `0x1801fdeb0`
- `0x180200c20`

## string_xrefs

- `0x180030d8b`: `onecoreuap\windows\cdp\common\internal\JsonSerializer.h`
- `0x1800310b4`: `onecoreuap\windows\cdp\common\internal\JsonSerializer.h`
- `0x1800311bb`: `onecoreuap\windows\cdp\common\internal\JsonSerializer.h`
- `0x1800312d0`: `onecoreuap\windows\cdp\common\internal\JsonSerializer.h`
- `0x180031477`: `onecoreuap\windows\cdp\common\internal\JsonSerializer.h`
- `0x1800318b8`: `onecoreuap\windows\cdp\common\internal\JsonSerializer.h`
- `0x1800319b4`: `onecoreuap\windows\cdp\common\internal\JsonSerializer.h`
- `0x180032695`: `onecoreuap\windows\cdp\common\internal\JsonSerializer.h`
- `0x180032bfa`: `onecoreuap\windows\cdp\common\internal\JsonSerializer.h`
- `0x180032d20`: `onecoreuap\windows\cdp\common\internal\JsonSerializer.h`
- `0x180032fd4`: `onecoreuap\windows\cdp\common\internal\JsonSerializer.h`
- `0x180032e52`: `FastPathSequencingEnabled`
- `0x1800327e2`: `InboundMessageThreadPoolCount`
- `0x180032859`: `OutboundMessageThreadPoolCount`
- `0x180032331`: `ProtocolVersionBrokerEnabled`
- `0x1800315b4`: `CcsSeenRequestIdsLastUpdatedTime`
- `0x180032fa3`: `ProtocolLiveTraceServer`
- `0x180030aac`: `NotificationUri`
- `0x180030adf`: `NotificationUriLastSynced`
- `0x18003035b`: `TraceLog.ComponentFlags`

## pseudocode

```c
// Hidden C++ exception states: #wind=108
void __fastcall shared::SharedGlobalSettingsBase::GlobalSettingsBaseStorage::Serialize<cdp::JsonData>(
        __int64 a1,
        _DWORD *a2)
{
  int v4; // eax
  _DWORD *v5; // rcx
  __int64 v6; // rax
  __int64 v7; // r14
  __int64 v8; // rax
  int v9; // eax
  _DWORD *v10; // rcx
  __int64 v11; // rax
  __int64 v12; // r14
  __int64 v13; // rax
  int v14; // eax
  _DWORD *v15; // rcx
  __int64 v16; // rax
  __int64 v17; // r14
  __int64 v18; // rax
  __int64 v19; // rdx
  __int64 v20; // rax
  int v21; // eax
  _DWORD *v22; // rcx
  __int64 v23; // rax
  __int64 v24; // r14
  __int64 v25; // rax
  __int64 v26; // rdx
  __int64 v27; // rax
  int v28; // eax
  _DWORD *v29; // rcx
  __int64 v30; // rax
  __int64 v31; // r14
  __int64 v32; // rax
  __int64 v33; // rdx
  __int64 v34; // rax
  int v35; // eax
  _DWORD *v36; // rcx
  __int64 v37; // rax
  __int64 v38; // r14
  __int64 v39; // rax
  __int64 v40; // rdx
  __int64 v41; // rax
  int v42; // eax
  _DWORD *v43; // rcx
  __int64 v44; // rax
  __int64 v45; // r14
  __int64 v46; // rax
  int v47; // eax
  _DWORD *v48; // rcx
  __int64 v49; // rax
  __int64 v50; // r14
  __int64 v51; // rax
  __int64 v52; // rdx
  __int64 v53; // rax
  int v54; // eax
  _DWORD *v55; // rcx
  __int64 v56; // rax
  __int64 v57; // r14
  __int64 v58; // rax
  __int64 v59; // rdx
  __int64 v60; // rax
  int v61; // eax
  _DWORD *v62; // rcx
  __int64 v63; // rax
  __int64 v64; // r14
  __int64 v65; // rax
  __int64 v66; // rdx
  __int64 v67; // rax
  int v68; // eax
  _DWORD *v69; // rcx
  __int64 v70; // rax
  __int64 v71; // r14
  __int64 v72; // rax
  int v73; // eax
  _DWORD *v74; // rcx
  __int64 v75; // rax
  __int64 v76; // r14
  __int64 v77; // rax
  int v78; // eax
  _DWORD *v79; // rcx
  __int64 v80; // rax
  __int64 v81; // r14
  __int64 v82; // rax
  __int64 v83; // rdx
  _BYTE *v84; // rax
  _BYTE *v85; // rcx
  char v86; // al
  __int64 v87; // rdx
  _BYTE *v88; // rax
  _BYTE *v89; // rcx
  char v90; // al
  __int64 v91; // rdx
  _BYTE *v92; // rax
  _BYTE *v93; // rcx
  char v94; // al
  __int64 v95; // rdx
  _BYTE *v96; // rax
  _BYTE *v97; // rcx
  char v98; // al
  __int64 v99; // rdx
  _BYTE *v100; // rax
  _BYTE *v101; // rcx
  char v102; // al
  __int64 v103; // rdx
  _BYTE *v104; // rax
  _BYTE *v105; // rcx
  char v106; // al
  __int64 v107; // rdx
  _BYTE *v108; // rax
  _BYTE *v109; // rcx
  char v110; // al
  __int64 v111; // rdx
  _BYTE *v112; // rax
  _BYTE *v113; // rcx
  char v114; // al
  __int64 v115; // rdx
  _BYTE *v116; // rax
  _BYTE *v117; // rcx
  char v118; // al
  __int64 v119; // rdx
  _BYTE *v120; // rax
  _BYTE *v121; // rcx
  char v122; // al
  int v123; // eax
  _DWORD *v124; // rcx
  Json::Value *v125; // rax
  int v126; // eax
  _DWORD *v127; // rcx
  Json::Value *v128; // rax
  int v129; // eax
  _DWORD *v130; // rcx
  __int64 v131; // rax
  __int64 v132; // r14
  __int64 v133; // rax
  const char *v134; // rdx
  __int64 v135; // rdx
  __int64 v136; // rax
  int v137; // eax
  _DWORD *v138; // rcx
  __int64 v139; // rax
  __int64 v140; // r14
  __int64 v141; // rax
  __int64 v142; // rdx
  __int64 v143; // rax
  int v144; // eax
  _DWORD *v145; // rcx
  Json::Value *v146; // rax
  __int64 v147; // rdx
  __int64 v148; // rax
  int v149; // eax
  _DWORD *v150; // rcx
  Json::Value *v151; // rax
  __int64 v152; // rdx
  __int64 v153; // rax
  int v154; // eax
  _DWORD *v155; // rcx
  __int64 v156; // rax
  __int64 v157; // rdi
  __int64 v158; // rax
  __int64 v159; // rdx
  __int64 v160; // rax
  __int64 v161; // rax
  _BYTE v162[8]; // [rsp+50h] [rbp-B0h] BYREF
  const char *v163; // [rsp+58h] [rbp-A8h] BYREF
  int v164; // [rsp+60h] [rbp-A0h]
  _BYTE v165[40]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v166[40]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v167[40]; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v168[40]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v169[40]; // [rsp+108h] [rbp+8h] BYREF
  _BYTE v170[40]; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v171[40]; // [rsp+158h] [rbp+58h] BYREF
  _BYTE v172[40]; // [rsp+180h] [rbp+80h] BYREF
  _BYTE v173[40]; // [rsp+1A8h] [rbp+A8h] BYREF
  _BYTE v174[40]; // [rsp+1D0h] [rbp+D0h] BYREF
  _BYTE v175[40]; // [rsp+1F8h] [rbp+F8h] BYREF
  _BYTE v176[40]; // [rsp+220h] [rbp+120h] BYREF
  _BYTE v177[40]; // [rsp+248h] [rbp+148h] BYREF
  _BYTE v178[40]; // [rsp+270h] [rbp+170h] BYREF
  _BYTE v179[40]; // [rsp+298h] [rbp+198h] BYREF
  _BYTE v180[40]; // [rsp+2C0h] [rbp+1C0h] BYREF
  _BYTE v181[24]; // [rsp+2E8h] [rbp+1E8h] BYREF
  _BYTE v182[24]; // [rsp+300h] [rbp+200h] BYREF
  _BYTE v183[24]; // [rsp+318h] [rbp+218h] BYREF
  _BYTE v184[24]; // [rsp+330h] [rbp+230h] BYREF
  _BYTE v185[24]; // [rsp+348h] [rbp+248h] BYREF
  _BYTE v186[24]; // [rsp+360h] [rbp+260h] BYREF
  _BYTE v187[24]; // [rsp+378h] [rbp+278h] BYREF
  _BYTE v188[24]; // [rsp+390h] [rbp+290h] BYREF
  _BYTE v189[24]; // [rsp+3A8h] [rbp+2A8h] BYREF
  _BYTE v190[24]; // [rsp+3C0h] [rbp+2C0h] BYREF
  _BYTE v191[24]; // [rsp+3D8h] [rbp+2D8h] BYREF
  _BYTE v192[14]; // [rsp+3F0h] [rbp+2F0h] BYREF
  __int16 v193; // [rsp+3FEh] [rbp+2FEh]
  __int64 v194; // [rsp+400h] [rbp+300h]
  __int64 v195; // [rsp+408h] [rbp+308h]
  __int128 v196; // [rsp+410h] [rbp+310h] BYREF
  __int64 v197; // [rsp+420h] [rbp+320h]
  __int64 v198; // [rsp+428h] [rbp+328h]
  __int128 v199; // [rsp+430h] [rbp+330h] BYREF
  __int64 v200; // [rsp+440h] [rbp+340h]
  __int64 v201; // [rsp+448h] [rbp+348h]
  __int128 v202; // [rsp+450h] [rbp+350h] BYREF
  __int64 v203; // [rsp+460h] [rbp+360h]
  __int64 v204; // [rsp+468h] [rbp+368h]
  __int128 v205; // [rsp+470h] [rbp+370h] BYREF
  __int64 v206; // [rsp+480h] [rbp+380h]
  __int64 v207; // [rsp+488h] [rbp+388h]
  __int128 v208; // [rsp+490h] [rbp+390h] BYREF
  __int64 v209; // [rsp+4A0h] [rbp+3A0h]
  __int64 v210; // [rsp+4A8h] [rbp+3A8h]
  __int128 v211; // [rsp+4B0h] [rbp+3B0h] BYREF
  __int64 v212; // [rsp+4C0h] [rbp+3C0h]
  __int64 v213; // [rsp+4C8h] [rbp+3C8h]
  _BYTE v214[14]; // [rsp+4D0h] [rbp+3D0h] BYREF
  __int16 v215; // [rsp+4DEh] [rbp+3DEh]
  __int64 v216; // [rsp+4E0h] [rbp+3E0h]
  __int64 v217; // [rsp+4E8h] [rbp+3E8h]
  _BYTE v218[14]; // [rsp+4F0h] [rbp+3F0h] BYREF
  __int16 v219; // [rsp+4FEh] [rbp+3FEh]
  __int64 v220; // [rsp+500h] [rbp+400h]
  __int64 v221; // [rsp+508h] [rbp+408h]
  __int128 v222; // [rsp+510h] [rbp+410h] BYREF
  __int64 v223; // [rsp+520h] [rbp+420h]
  __int64 v224; // [rsp+528h] [rbp+428h]
  __int128 v225; // [rsp+530h] [rbp+430h] BYREF
  __int64 v226; // [rsp+540h] [rbp+440h]
  __int64 v227; // [rsp+548h] [rbp+448h]
  __int128 v228; // [rsp+550h] [rbp+450h] BYREF
  __int64 v229; // [rsp+560h] [rbp+460h]
  __int64 v230; // [rsp+568h] [rbp+468h]
  __int128 v231; // [rsp+570h] [rbp+470h] BYREF
  __int64 v232; // [rsp+580h] [rbp+480h]
  __int64 v233; // [rsp+588h] [rbp+488h]
  __int128 v234; // [rsp+590h] [rbp+490h] BYREF
  __int64 v235; // [rsp+5A0h] [rbp+4A0h]
  __int64 v236; // [rsp+5A8h] [rbp+4A8h]
  _BYTE v237[12]; // [rsp+5B0h] [rbp+4B0h] BYREF
  int v238; // [rsp+5BCh] [rbp+4BCh]
  __int64 v239; // [rsp+5C0h] [rbp+4C0h]
  __int64 v240; // [rsp+5C8h] [rbp+4C8h]
  _BYTE v241[12]; // [rsp+5D0h] [rbp+4D0h] BYREF
  int v242; // [rsp+5DCh] [rbp+4DCh]
  __int64 v243; // [rsp+5E0h] [rbp+4E0h]
  __int64 v244; // [rsp+5E8h] [rbp+4E8h]
  _BYTE v245[12]; // [rsp+5F0h] [rbp+4F0h] BYREF
  int v246; // [rsp+5FCh] [rbp+4FCh]
  __int64 v247; // [rsp+600h] [rbp+500h]
  __int64 v248; // [rsp+608h] [rbp+508h]
  _BYTE v249[6]; // [rsp+610h] [rbp+510h] BYREF
  __int64 v250; // [rsp+616h] [rbp+516h]
  __int16 v251; // [rsp+61Eh] [rbp+51Eh]
  __int64 v252; // [rsp+620h] [rbp+520h]
  __int64 v253; // [rsp+628h] [rbp+528h]
  _BYTE v254[14]; // [rsp+630h] [rbp+530h] BYREF
  __int16 v255; // [rsp+63Eh] [rbp+53Eh]
  __m128i v256; // [rsp+640h] [rbp+540h]
  _BYTE v257[12]; // [rsp+650h] [rbp+550h] BYREF
  int v258; // [rsp+65Ch] [rbp+55Ch]
  __m128i si128; // [rsp+660h] [rbp+560h]
  _BYTE v260[12]; // [rsp+670h] [rbp+570h] BYREF
  int v261; // [rsp+67Ch] [rbp+57Ch]
  __m128i v262; // [rsp+680h] [rbp+580h]
  char v263[14]; // [rsp+690h] [rbp+590h] BYREF
  __int16 v264; // [rsp+69Eh] [rbp+59Eh]
  __int64 v265; // [rsp+6A0h] [rbp+5A0h]
  __int64 v266; // [rsp+6A8h] [rbp+5A8h]
  __int128 v267; // [rsp+6B0h] [rbp+5B0h] BYREF
  __int64 v268; // [rsp+6C0h] [rbp+5C0h]
  __int64 v269; // [rsp+6C8h] [rbp+5C8h]
  _BYTE v270[12]; // [rsp+6D0h] [rbp+5D0h] BYREF
  int v271; // [rsp+6DCh] [rbp+5DCh]
  __m128i v272; // [rsp+6E0h] [rbp+5E0h]
  _BYTE v273[12]; // [rsp+6F0h] [rbp+5F0h] BYREF
  int v274; // [rsp+6FCh] [rbp+5FCh]
  __m128i v275; // [rsp+700h] [rbp+600h]
  __int128 v276; // [rsp+710h] [rbp+610h] BYREF
  __m128i v277; // [rsp+720h] [rbp+620h]
  __int128 v278; // [rsp+730h] [rbp+630h] BYREF
  __m128i v279; // [rsp+740h] [rbp+640h]
  __int128 v280; // [rsp+750h] [rbp+650h] BYREF
  __m128i v281; // [rsp+760h] [rbp+660h]
  __int128 v282; // [rsp+770h] [rbp+670h] BYREF
  __m128i v283; // [rsp+780h] [rbp+680h]
  __int128 v284; // [rsp+790h] [rbp+690h] BYREF
  __m128i v285; // [rsp+7A0h] [rbp+6A0h]
  __int128 v286; // [rsp+7B0h] [rbp+6B0h] BYREF
  __m128i v287; // [rsp+7C0h] [rbp+6C0h]
  __int128 v288; // [rsp+7D0h] [rbp+6D0h] BYREF
  __m128i v289; // [rsp+7E0h] [rbp+6E0h]
  __int128 v290; // [rsp+7F0h] [rbp+6F0h] BYREF
  __m128i v291; // [rsp+800h] [rbp+700h]
  __int128 v292; // [rsp+810h] [rbp+710h] BYREF
  __m128i v293; // [rsp+820h] [rbp+720h]
  __int128 v294; // [rsp+830h] [rbp+730h] BYREF
  __m128i v295; // [rsp+840h] [rbp+740h]
  __int128 v296; // [rsp+850h] [rbp+750h] BYREF
  __m128i v297; // [rsp+860h] [rbp+760h]
  __int128 v298; // [rsp+870h] [rbp+770h] BYREF
  __m128i v299; // [rsp+880h] [rbp+780h]
  __int128 v300; // [rsp+890h] [rbp+790h] BYREF
  __m128i v301; // [rsp+8A0h] [rbp+7A0h]
  __int128 v302; // [rsp+8B0h] [rbp+7B0h] BYREF
  __m128i v303; // [rsp+8C0h] [rbp+7C0h]
  __int128 v304; // [rsp+8D0h] [rbp+7D0h] BYREF
  __m128i v305; // [rsp+8E0h] [rbp+7E0h]
  __int128 v306; // [rsp+8F0h] [rbp+7F0h] BYREF
  __m128i v307; // [rsp+900h] [rbp+800h]
  __int128 v308; // [rsp+910h] [rbp+810h] BYREF
  __m128i v309; // [rsp+920h] [rbp+820h]
  __int128 v310; // [rsp+930h] [rbp+830h] BYREF
  __m128i v311; // [rsp+940h] [rbp+840h]
  __int128 v312; // [rsp+950h] [rbp+850h] BYREF
  __m128i v313; // [rsp+960h] [rbp+860h]
  __int128 v314; // [rsp+970h] [rbp+870h] BYREF
  __m128i v315; // [rsp+980h] [rbp+880h]
  __int128 v316; // [rsp+990h] [rbp+890h] BYREF
  __m128i v317; // [rsp+9A0h] [rbp+8A0h]
  __int128 v318; // [rsp+9B0h] [rbp+8B0h] BYREF
  __m128i v319; // [rsp+9C0h] [rbp+8C0h]
  __int128 v320; // [rsp+9D0h] [rbp+8D0h] BYREF
  __m128i v321; // [rsp+9E0h] [rbp+8E0h]
  __int128 v322; // [rsp+9F0h] [rbp+8F0h] BYREF
  __m128i v323; // [rsp+A00h] [rbp+900h]
  __int128 v324; // [rsp+A10h] [rbp+910h] BYREF
  __m128i v325; // [rsp+A20h] [rbp+920h]
  __int128 v326; // [rsp+A30h] [rbp+930h] BYREF
  __m128i v327; // [rsp+A40h] [rbp+940h]
  __int128 v328; // [rsp+A50h] [rbp+950h] BYREF
  __m128i v329; // [rsp+A60h] [rbp+960h]
  __int128 v330; // [rsp+A70h] [rbp+970h] BYREF
  __m128i v331; // [rsp+A80h] [rbp+980h]
  __int128 v332; // [rsp+A90h] [rbp+990h] BYREF
  __m128i v333; // [rsp+AA0h] [rbp+9A0h]
  __int128 v334; // [rsp+AB0h] [rbp+9B0h] BYREF
  __m128i v335; // [rsp+AC0h] [rbp+9C0h]
  __int128 v336; // [rsp+AD0h] [rbp+9D0h] BYREF
  __m128i v337; // [rsp+AE0h] [rbp+9E0h]
  __int128 v338; // [rsp+AF0h] [rbp+9F0h] BYREF
  __m128i v339; // [rsp+B00h] [rbp+A00h]
  __int128 v340; // [rsp+B10h] [rbp+A10h] BYREF
  __m128i v341; // [rsp+B20h] [rbp+A20h]
  __int128 v342; // [rsp+B30h] [rbp+A30h] BYREF
  __m128i v343; // [rsp+B40h] [rbp+A40h]
  __int128 v344; // [rsp+B58h] [rbp+A58h] BYREF
  __m128i v345; // [rsp+B68h] [rbp+A68h]
  __int128 v346; // [rsp+B80h] [rbp+A80h] BYREF
  __m128i v347; // [rsp+B90h] [rbp+A90h]
  __int128 v348; // [rsp+BA8h] [rbp+AA8h] BYREF
  __m128i v349; // [rsp+BB8h] [rbp+AB8h]
  __int128 v350; // [rsp+BD0h] [rbp+AD0h] BYREF
  __m128i v351; // [rsp+BE0h] [rbp+AE0h]
  __int128 v352; // [rsp+BF8h] [rbp+AF8h] BYREF
  __m128i v353; // [rsp+C08h] [rbp+B08h]
  __int128 v354; // [rsp+C20h] [rbp+B20h] BYREF
  __m128i v355; // [rsp+C30h] [rbp+B30h]
  _BYTE v356[32]; // [rsp+C48h] [rbp+B48h] BYREF
  _BYTE v357[32]; // [rsp+C68h] [rbp+B68h] BYREF
  _BYTE v358[32]; // [rsp+C88h] [rbp+B88h] BYREF
  _BYTE v359[32]; // [rsp+CA8h] [rbp+BA8h] BYREF
  _BYTE v360[32]; // [rsp+CC8h] [rbp+BC8h] BYREF
  _BYTE v361[32]; // [rsp+CE8h] [rbp+BE8h] BYREF
  _BYTE v362[32]; // [rsp+D08h] [rbp+C08h] BYREF
  _BYTE v363[32]; // [rsp+D28h] [rbp+C28h] BYREF
  _BYTE v364[32]; // [rsp+D48h] [rbp+C48h] BYREF
  _BYTE v365[32]; // [rsp+D68h] [rbp+C68h] BYREF
  _BYTE v366[32]; // [rsp+D88h] [rbp+C88h] BYREF
  _BYTE v367[32]; // [rsp+DA8h] [rbp+CA8h] BYREF
  _BYTE v368[32]; // [rsp+DC8h] [rbp+CC8h] BYREF
  _BYTE v369[32]; // [rsp+DE8h] [rbp+CE8h] BYREF
  _BYTE v370[32]; // [rsp+E08h] [rbp+D08h] BYREF
  _BYTE v371[32]; // [rsp+E28h] [rbp+D28h] BYREF
  _BYTE v372[32]; // [rsp+E48h] [rbp+D48h] BYREF
  _BYTE v373[32]; // [rsp+E68h] [rbp+D68h] BYREF
  _BYTE v374[32]; // [rsp+E88h] [rbp+D88h] BYREF
  _BYTE v375[32]; // [rsp+EA8h] [rbp+DA8h] BYREF
  _BYTE v376[32]; // [rsp+EC8h] [rbp+DC8h] BYREF
  _BYTE v377[32]; // [rsp+EE8h] [rbp+DE8h] BYREF
  _BYTE v378[32]; // [rsp+F08h] [rbp+E08h] BYREF

  si128 = _mm_load_si128((const __m128i *)&_xmm);
  qmemcpy(v257, "FormatVersio", sizeof(v257));
  v258 = (unsigned __int8)aFormatversion[12];
  cdp::Serializer<cdp::JsonData>::AddValue<unsigned int,unsigned int>(
    a2,
    &shared::SharedGlobalSettingsBase::GlobalSettingsBaseStorage::FormatVersion,
    v257);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v257);
  v194 = 15;
  v195 = 15;
  qmemcpy(v192, "VirtualDeviceI", sizeof(v192));
  v193 = (unsigned __int8)aVirtualdevicei[14];
  v4 = Json::Value::type(a2 + 2);
  v5 = a2 + 2;
  if ( v4 == 7 )
  {
    v6 = Json::Value::operator[](v5, v192);
  }
  else
  {
    ++*a2;
    v6 = Json::Value::operator[](v5);
  }
  v7 = v6;
  v8 = Json::Value::Value(v178, a1);
  Json::Value::operator=(v7, v8);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v192);
  if ( *(_DWORD *)(a1 + 40) != -1 )
  {
    std::string::string(v366, "TraceLog.ComponentFlags");
    cdp::Serializer<cdp::JsonData>::AddValue<enum shared::TraceComponents,enum shared::TraceComponents>(
      a2,
      a1 + 40,
      v366);
    std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v366);
  }
  v262 = _mm_load_si128((const __m128i *)&_xmm);
  qmemcpy(v260, "TraceLog.Lev", sizeof(v260));
  v261 = *(unsigned __int16 *)"el";
  cdp::Serializer<cdp::JsonData>::AddValue<enum CDPLogLevel,enum CDPLogLevel>(a2, a1 + 32, v260);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v260);
  v276 = 0;
  v277 = 0;
  *(_QWORD *)&v276 = std::allocator<char>::allocate(&v276, 32);
  v277 = _mm_load_si128((const __m128i *)&_xmm);
  strcpy((char *)v276, "TraceLog.EnabledHandlerTypes");
  cdp::Serializer<cdp::JsonData>::AddValue<enum shared::TraceHandlers,enum shared::TraceHandlers>(a2, a1 + 36, &v276);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v276);
  if ( *(_BYTE *)(a1 + 44) )
  {
    std::string::string(v365, "TraceLog.RemoteViewerEnabled");
    cdp::Serializer<cdp::JsonData>::AddValue<bool,bool>(a2, a1 + 44, v365);
    std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v365);
  }
  if ( *(_QWORD *)(a1 + 64) )
  {
    std::string::string(v364, "TraceLog.RemoteViewerAddress");
    cdp::Serializer<cdp::JsonData>::AddValue<std::string,std::string>(a2, a1 + 48, v364);
    std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v364);
  }
  if ( *(_BYTE *)(a1 + 80) && *(_WORD *)(a1 + 82) != 11 )
  {
    std::string::string(v363, "ChaosMonkey.SessionMessageReceivedDropRate.Enabled");
    cdp::Serializer<cdp::JsonData>::AddValue<bool,bool>(a2, a1 + 80, v363);
    std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v363);
    std::string::string(v361, "ChaosMonkey.SessionMessageReceivedDropRate.Value");
    cdp::Serializer<cdp::JsonData>::AddValue<unsigned short,unsigned short>(a2, a1 + 82, v361);
    std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v361);
  }
  if ( *(_DWORD *)(a1 + 84) != 3000 )
  {
    std::string::string(v360, "Heartbeat.IdleTimeOut");
    cdp::Serializer<cdp::JsonData>::AddValue<unsigned int,unsigned int>(a2, a1 + 84, v360);
    std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v360);
  }
  v352 = 0;
  v353 = 0;
  *(_QWORD *)&v352 = std::allocator<char>::allocate(&v352, 48);
  v353 = _mm_load_si128((const __m128i *)&_xmm);
  strcpy((char *)v352, "Cloud.SessionIdleTimeoutIntervalSecs");
  cdp::Serializer<cdp::JsonData>::AddValue<unsigned int,unsigned int>(a2, a1 + 92, &v352);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v352);
  v342 = 0;
  v343 = 0;
  *(_QWORD *)&v342 = std::allocator<char>::allocate(&v342, 48);
  v343 = _mm_load_si128((const __m128i *)&_xmm);
  strcpy((char *)v342, "LargePayload.ExtendedTimeoutSecs");
  cdp::Serializer<cdp::JsonData>::AddValue<unsigned int,unsigned int>(a2, a1 + 100, &v342);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v342);
  v278 = 0;
  v279 = 0;
  *(_QWORD *)&v278 = std::allocator<char>::allocate(&v278, 32);
  v279 = _mm_load_si128((const __m128i *)&_xmm);
  strcpy((char *)v278, "LargePayload.ThresholdBytes");
  cdp::Serializer<cdp::JsonData>::AddValue<unsigned int,unsigned int>(a2, a1 + 96, &v278);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v278);
  if ( *(_DWORD *)(a1 + 88) != 300000 )
  {
    std::string::string(v359, "Idle.TimeOut");
    cdp::Serializer<cdp::JsonData>::AddValue<unsigned int,unsigned int>(a2, a1 + 88, v359);
    std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v359);
  }
  if ( *(_WORD *)(a1 + 106) != 100 )
  {
    std::string::string(v374, "MessagePolicy.Priority");
    cdp::Serializer<cdp::JsonData>::AddValue<unsigned short,unsigned short>(a2, a1 + 106, v374);
    std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v374);
  }
  if ( *(_WORD *)(a1 + 104) != 10 )
  {
    std::string::string(v369, "MessagePolicy.RetryCount");
    cdp::Serializer<cdp::JsonData>::AddValue<unsigned short,unsigned short>(a2, a1 + 104, v369);
    std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v369);
  }
  if ( *(_DWORD *)(a1 + 108) != 750 )
  {
    std::string::string(v362, "MessagePolicy.TimeOut");
    cdp::Serializer<cdp::JsonData>::AddValue<unsigned int,unsigned int>(a2, a1 + 108, v362);
    std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v362);
  }
  if ( *(_BYTE *)(a1 + 112) != 1 )
  {
    std::string::string(v367, "MessagePolicy.ReliableDelivery");
    cdp::Serializer<cdp::JsonData>::AddValue<bool,bool>(a2, a1 + 112, v367);
    std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v367);
  }
  if ( *(_DWORD *)(a1 + 116) != 3 )
  {
    std::string::string(v368, "FlowControl.PriorityMultiplier");
    cdp::Serializer<cdp::JsonData>::AddValue<unsigned int,unsigned int>(a2, a1 + 116, v368);
    std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v368);
  }
  if ( *(_DWORD *)(a1 + 120) != 1 )
  {
    std::string::string(v370, "FlowControl.PriorityOffsetGrowthRate");
    cdp::Serializer<cdp::JsonData>::AddValue<unsigned int,unsigned int>(a2, a1 + 120, v370);
    std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v370);
  }
  if ( *(_DWORD *)(a1 + 124) != 10000 )
  {
    std::string::string(v371, "FlowControl.MaxPriorityOffset");
    cdp::Serializer<cdp::JsonData>::AddValue<unsigned int,unsigned int>(a2, a1 + 124, v371);
    std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v371);
  }
  if ( *(_DWORD *)(a1 + 124) != 100 )
  {
    v280 = 0;
    v281 = 0;
    *(_QWORD *)&v280 = std::allocator<char>::allocate(&v280, 32);
    v281 = _mm_load_si128((const __m128i *)&_xmm);
    strcpy((char *)v280, "FlowControl.AckSendInterval");
    cdp::Serializer<cdp::JsonData>::AddValue<unsigned int,unsigned int>(a2, a1 + 128, &v280);
    std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v280);
  }
  if ( !*(_BYTE *)(a1 + 132) )
  {
    std::string::string(v372, "Metrics.AdministerCllEnabled");
    cdp::Serializer<cdp::JsonData>::AddValue<bool,bool>(a2, a1 + 132, v372);
    std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v372);
  }
  if ( !*(_BYTE *)(a1 + 133) )
  {
    std::string::string(v373, "Metrics.Enabled");
    cdp::Serializer<cdp::JsonData>::AddValue<bool,bool>(a2, a1 + 133, v373);
    std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v373);
  }
  v265 = 12;
  v266 = 15;
  strcpy(v263, "Metrics.iKey");
  v263[13] = 0;
  v264 = 0;
  v9 = Json::Value::type(a2 + 2);
  v10 = a2 + 2;
  if ( v9 == 7 )
  {
    v11 = Json::Value::operator[](v10, v263);
  }
  else
  {
    ++*a2;
    v11 = Json::Value::operator[](v10);
  }
  v12 = v11;
  v13 = Json::Value::Value(v179, a1 + 136);
  Json::Value::operator=(v12, v13);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v263);
  if ( *(_QWORD *)(a1 + 864) )
  {
    std::string::string(v378, "NotificationUri");
    cdp::Serializer<cdp::JsonData>::AddValue<std::string,std::string>(a2, a1 + 848, v378);
    std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v378);
    std::string::string(v375, "NotificationUriLastSynced");
    cdp::Serializer<cdp::JsonData>::AddValue<CDP_DATE_TIME,CDP_DATE_TIME>(a2, a1 + 880, v375);
    std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v375);
  }
  v282 = 0;
  v283 = 0;
  *(_QWORD *)&v282 = std::allocator<char>::allocate(&v282, 32);
  v283 = _mm_load_si128((const __m128i *)&_xmm);
  strcpy((char *)v282, "Authentication.Environment");
  cdp::Serializer<cdp::JsonData>::AddValue<enum shared::EnvironmentType,enum shared::EnvironmentType>(
    a2,
    a1 + 168,
    &v282);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v282);
  v267 = 0;
  v268 = 6;
  v269 = 15;
  strcpy((char *)&v267, "AFSUrl");
  v14 = Json::Value::type(a2 + 2);
  v15 = a2 + 2;
  if ( v14 == 7 )
  {
    v16 = Json::Value::operator[](v15, &v267);
  }
  else
  {
    ++*a2;
    v16 = Json::Value::operator[](v15);
  }
  v17 = v16;
  v18 = Json::Value::Value(v177, a1 + 176);
  Json::Value::operator=(v17, v18);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v267);
  v272 = _mm_load_si128((const __m128i *)&_xmm);
  qmemcpy(v270, "AFSEnvironme", sizeof(v270));
  v271 = *(unsigned __int16 *)"nt";
  cdp::Serializer<cdp::JsonData>::AddValue<enum shared::AFSEnvironment,enum shared::AFSEnvironment>(a2, a1 + 208, v270);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v270);
  v284 = 0;
  v285 = 0;
  *(_QWORD *)&v284 = std::allocator<char>::allocate(&v284, 32);
  v285 = _mm_load_si128((const __m128i *)&_xmm);
  strcpy((char *)v284, "ActivityAssetEnvironment");
  cdp::Serializer<cdp::JsonData>::AddValue<enum shared::ActivityAssetEnvironment,enum shared::ActivityAssetEnvironment>(
    a2,
    a1 + 212,
    &v284);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v284);
  v234 = 0;
  v235 = 0;
  v236 = 0;
  *(_QWORD *)&v234 = std::allocator<char>::allocate(&v234, 32);
  v235 = 16;
  v236 = 31;
  strcpy((char *)v234, "ActivityAssetUrl");
  if ( !v235 && (unsigned int)Json::Value::type(a2 + 2) != 6 )
  {
    v163 = "onecoreuap\\windows\\cdp\\common\\internal\\JsonSerializer.h";
    v164 = 55;
    v20 = cdp::MakeException<std::invalid_argument,>(
            v181,
            v19,
            "Failed to add value, name required for object serialization");
    cdp::CdpThrow<std::invalid_argument>(&v163, v20);
  }
  v21 = Json::Value::type(a2 + 2);
  v22 = a2 + 2;
  if ( v21 == 7 )
  {
    v23 = Json::Value::operator[](v22, &v234);
  }
  else
  {
    ++*a2;
    v23 = Json::Value::operator[](v22);
  }
  v24 = v23;
  v25 = Json::Value::Value(v176, a1 + 216);
  Json::Value::operator=(v24, v25);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v234);
  v340 = 0;
  v341 = 0;
  *(_QWORD *)&v340 = std::allocator<char>::allocate(&v340, 32);
  v341 = _mm_load_si128((const __m128i *)&_xmm);
  strcpy((char *)v340, "ActivityAssetBatchingEnabled");
  cdp::Serializer<cdp::JsonData>::AddValue<bool,bool>(a2, a1 + 344, &v340);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v340);
  v338 = 0;
  v339 = 0;
  *(_QWORD *)&v338 = std::allocator<char>::allocate(&v338, 48);
  v339 = _mm_load_si128((const __m128i *)&_xmm);
  strcpy((char *)v338, "ActivityAssetBatchRequestPayloadSizeLimit");
  cdp::Serializer<cdp::JsonData>::AddValue<unsigned int,unsigned int>(a2, a1 + 348, &v338);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v338);
  v336 = 0;
  v337 = 0;
  *(_QWORD *)&v336 = std::allocator<char>::allocate(&v336, 32);
  v337 = _mm_load_si128((const __m128i *)&_xmm);
  strcpy((char *)v336, "ActivityAssetBatchWaitTimeInMS");
  cdp::Serializer<cdp::JsonData>::AddValue<unsigned int,unsigned int>(a2, a1 + 352, &v336);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v336);
  v354 = 0;
  v355 = 0;
  *(_QWORD *)&v354 = std::allocator<char>::allocate(&v354, 48);
  v355 = _mm_load_si128((const __m128i *)&_xmm);
  strcpy((char *)v354, "ActivityAssetBatchRequestNumberLimit");
  cdp::Serializer<cdp::JsonData>::AddValue<unsigned int,unsigned int>(a2, a1 + 356, &v354);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v354);
  v196 = 0;
  v197 = 0;
  v198 = 0;
  *(_QWORD *)&v196 = std::allocator<char>::allocate(&v196, 32);
  v197 = 21;
  v198 = 31;
  strcpy((char *)v196, "ActivityAssetBatchUrl");
  if ( !v197 && (unsigned int)Json::Value::type(a2 + 2) != 6 )
  {
    v163 = "onecoreuap\\windows\\cdp\\common\\internal\\JsonSerializer.h";
    v164 = 55;
    v27 = cdp::MakeException<std::invalid_argument,>(
            v182,
            v26,
            "Failed to add value, name required for object serialization");
    cdp::CdpThrow<std::invalid_argument>(&v163, v27);
  }
  v28 = Json::Value::type(a2 + 2);
  v29 = a2 + 2;
  if ( v28 == 7 )
  {
    v30 = Json::Value::operator[](v29, &v196);
  }
  else
  {
    ++*a2;
    v30 = Json::Value::operator[](v29);
  }
  v31 = v30;
  v32 = Json::Value::Value(v175, a1 + 248);
  Json::Value::operator=(v31, v32);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v196);
  v199 = 0;
  v200 = 0;
  v201 = 0;
  *(_QWORD *)&v199 = std::allocator<char>::allocate(&v199, 32);
  v200 = 29;
  v201 = 31;
  strcpy((char *)v199, "ActivityAssetMsaScopeEndPoint");
  if ( !v200 && (unsigned int)Json::Value::type(a2 + 2) != 6 )
  {
    v163 = "onecoreuap\\windows\\cdp\\common\\internal\\JsonSerializer.h";
    v164 = 55;
    v34 = cdp::MakeException<std::invalid_argument,>(
            v183,
            v33,
            "Failed to add value, name required for object serialization");
    cdp::CdpThrow<std::invalid_argument>(&v163, v34);
  }
  v35 = Json::Value::type(a2 + 2);
  v36 = a2 + 2;
  if ( v35 == 7 )
  {
    v37 = Json::Value::operator[](v36, &v199);
  }
  else
  {
    ++*a2;
    v37 = Json::Value::operator[](v36);
  }
  v38 = v37;
  v39 = Json::Value::Value(v174, a1 + 280);
  Json::Value::operator=(v38, v39);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v199);
  v202 = 0;
  v203 = 0;
  v204 = 0;
  *(_QWORD *)&v202 = std::allocator<char>::allocate(&v202, 32);
  v203 = 24;
  v204 = 31;
  strcpy((char *)v202, "ActivityAssetAadAudience");
  if ( !v203 && (unsigned int)Json::Value::type(a2 + 2) != 6 )
  {
    v163 = "onecoreuap\\windows\\cdp\\common\\internal\\JsonSerializer.h";
    v164 = 55;
    v41 = cdp::MakeException<std::invalid_argument,>(
            v184,
            v40,
            "Failed to add value, name required for object serialization");
    cdp::CdpThrow<std::invalid_argument>(&v163, v41);
  }
  v42 = Json::Value::type(a2 + 2);
  v43 = a2 + 2;
  if ( v42 == 7 )
  {
    v44 = Json::Value::operator[](v43, &v202);
  }
  else
  {
    ++*a2;
    v44 = Json::Value::operator[](v43);
  }
  v45 = v44;
  v46 = Json::Value::Value(v173, a1 + 312);
  Json::Value::operator=(v45, v46);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v202);
  v239 = 13;
  v240 = 15;
  qmemcpy(v237, "CcsApiVersio", sizeof(v237));
  v238 = (unsigned __int8)aCcsapiversion_0[12];
  v47 = Json::Value::type(a2 + 2);
  v48 = a2 + 2;
  if ( v47 == 7 )
  {
    v49 = Json::Value::operator[](v48, v237);
  }
  else
  {
    ++*a2;
    v49 = Json::Value::operator[](v48);
  }
  v50 = v49;
  v51 = Json::Value::Value(v172, a1 + 360);
  Json::Value::operator=(v50, v51);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v237);
  v205 = 0;
  v206 = 0;
  v207 = 0;
  *(_QWORD *)&v205 = std::allocator<char>::allocate(&v205, 32);
  v206 = 20;
  v207 = 31;
  strcpy((char *)v205, "CcsDefaultServerName");
  if ( !v206 && (unsigned int)Json::Value::type(a2 + 2) != 6 )
  {
    v163 = "onecoreuap\\windows\\cdp\\common\\internal\\JsonSerializer.h";
    v164 = 55;
    v53 = cdp::MakeException<std::invalid_argument,>(
            v185,
            v52,
            "Failed to add value, name required for object serialization");
    cdp::CdpThrow<std::invalid_argument>(&v163, v53);
  }
  v54 = Json::Value::type(a2 + 2);
  v55 = a2 + 2;
  if ( v54 == 7 )
  {
    v56 = Json::Value::operator[](v55, &v205);
  }
  else
  {
    ++*a2;
    v56 = Json::Value::operator[](v55);
  }
  v57 = v56;
  v58 = Json::Value::Value(v171, a1 + 392);
  Json::Value::operator=(v57, v58);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v205);
  v334 = 0;
  v335 = 0;
  *(_QWORD *)&v334 = std::allocator<char>::allocate(&v334, 32);
  v335 = _mm_load_si128((const __m128i *)&_xmm);
  strcpy((char *)v334, "CcsSeenRequestIds");
  cdp::Serializer<cdp::JsonData>::AddValue<std::vector<std::string>,std::vector<std::string>>(a2, a1 + 448, &v334);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v334);
  v346 = 0;
  v347 = 0;
  *(_QWORD *)&v346 = std::allocator<char>::allocate(&v346, 48);
  v347 = _mm_load_si128((const __m128i *)&_xmm);
  strcpy((char *)v346, "CcsSeenRequestIdsLastUpdatedTime");
  cdp::Serializer<cdp::JsonData>::AddValue<CDP_DATE_TIME,CDP_DATE_TIME>(a2, a1 + 472, &v346);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v346);
  v275 = _mm_load_si128((const __m128i *)&_xmm);
  qmemcpy(v273, "CcsPollingMo", sizeof(v273));
  v274 = *(unsigned __int16 *)"de";
  cdp::Serializer<cdp::JsonData>::AddValue<enum shared::CCSPollingMode,enum shared::CCSPollingMode>(a2, a1 + 424, v273);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v273);
  v332 = 0;
  v333 = 0;
  *(_QWORD *)&v332 = std::allocator<char>::allocate(&v332, 32);
  v333 = _mm_load_si128((const __m128i *)&_xmm);
  strcpy((char *)v332, "CcsExtendedPollingMode");
  cdp::Serializer<cdp::JsonData>::AddValue<enum shared::CCSExtendedPollingMode,enum shared::CCSExtendedPollingMode>(
    a2,
    a1 + 428,
    &v332);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v332);
  v330 = 0;
  v331 = 0;
  *(_QWORD *)&v330 = std::allocator<char>::allocate(&v330, 32);
  v331 = _mm_load_si128((const __m128i *)&_xmm);
  strcpy((char *)v330, "CcsPollingInterval");
  cdp::Serializer<cdp::JsonData>::AddValue<unsigned int,unsigned int>(a2, a1 + 432, &v330);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v330);
  v328 = 0;
  v329 = 0;
  *(_QWORD *)&v328 = std::allocator<char>::allocate(&v328, 32);
  v329 = _mm_load_si128((const __m128i *)&_xmm);
  strcpy((char *)v328, "CcsPollingMaxIntervalCount");
  cdp::Serializer<cdp::JsonData>::AddValue<unsigned int,unsigned int>(a2, a1 + 436, &v328);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v328);
  v326 = 0;
  v327 = 0;
  *(_QWORD *)&v326 = std::allocator<char>::allocate(&v326, 32);
  v327 = _mm_load_si128((const __m128i *)&_xmm);
  strcpy((char *)v326, "CcsPollingBackoffEnabled");
  cdp::Serializer<cdp::JsonData>::AddValue<bool,bool>(a2, a1 + 440, &v326);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v326);
  v208 = 0;
  v209 = 0;
  v210 = 0;
  *(_QWORD *)&v208 = std::allocator<char>::allocate(&v208, 32);
  v209 = 17;
  v210 = 31;
  strcpy((char *)v208, "DdsMsaRegisterUrl");
  if ( !v209 && (unsigned int)Json::Value::type(a2 + 2) != 6 )
  {
    v163 = "onecoreuap\\windows\\cdp\\common\\internal\\JsonSerializer.h";
    v164 = 55;
    v60 = cdp::MakeException<std::invalid_argument,>(
            v186,
            v59,
            "Failed to add value, name required for object serialization");
    cdp::CdpThrow<std::invalid_argument>(&v163, v60);
  }
  v61 = Json::Value::type(a2 + 2);
  v62 = a2 + 2;
  if ( v61 == 7 )
  {
    v63 = Json::Value::operator[](v62, &v208);
  }
  else
  {
    ++*a2;
    v63 = Json::Value::operator[](v62);
  }
  v64 = v63;
  v65 = Json::Value::Value(v170, a1 + 504);
  Json::Value::operator=(v64, v65);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v208);
  v211 = 0;
  v212 = 0;
  v213 = 0;
  *(_QWORD *)&v211 = std::allocator<char>::allocate(&v211, 32);
  v212 = 17;
  v213 = 31;
  strcpy((char *)v211, "DdsAadRegisterUrl");
  if ( !v212 && (unsigned int)Json::Value::type(a2 + 2) != 6 )
  {
    v163 = "onecoreuap\\windows\\cdp\\common\\internal\\JsonSerializer.h";
    v164 = 55;
    v67 = cdp::MakeException<std::invalid_argument,>(
            v187,
            v66,
            "Failed to add value, name required for object serialization");
    cdp::CdpThrow<std::invalid_argument>(&v163, v67);
  }
  v68 = Json::Value::type(a2 + 2);
  v69 = a2 + 2;
  if ( v68 == 7 )
  {
    v70 = Json::Value::operator[](v69, &v211);
  }
  else
  {
    ++*a2;
    v70 = Json::Value::operator[](v69);
  }
  v71 = v70;
  v72 = Json::Value::Value(v169, a1 + 536);
  Json::Value::operator=(v71, v72);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v211);
  v243 = 13;
  v244 = 15;
  qmemcpy(v241, "DdsMsaSyncUr", sizeof(v241));
  v242 = (unsigned __int8)aDdsmsasyncurl[12];
  v73 = Json::Value::type(a2 + 2);
  v74 = a2 + 2;
  if ( v73 == 7 )
  {
    v75 = Json::Value::operator[](v74, v241);
  }
  else
  {
    ++*a2;
    v75 = Json::Value::operator[](v74);
  }
  v76 = v75;
  v77 = Json::Value::Value(v168, a1 + 568);
  Json::Value::operator=(v76, v77);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v241);
  v247 = 13;
  v248 = 15;
  qmemcpy(v245, "DdsAadSyncUr", sizeof(v245));
  v246 = (unsigned __int8)aDdsaadsyncurl[12];
  v78 = Json::Value::type(a2 + 2);
  v79 = a2 + 2;
  if ( v78 == 7 )
  {
    v80 = Json::Value::operator[](v79, v245);
  }
  else
  {
    ++*a2;
    v80 = Json::Value::operator[](v79);
  }
  v81 = v80;
  v82 = Json::Value::Value(v167, a1 + 600);
  Json::Value::operator=(v81, v82);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v245);
  v318 = 0;
  v319 = 0;
  *(_QWORD *)&v318 = std::allocator<char>::allocate(&v318, 32);
  v319 = _mm_load_si128((const __m128i *)&_xmm);
  strcpy((char *)v318, "CloudTransportEnabled");
  v83 = *(_QWORD *)(a1 + 696);
  v84 = *(_BYTE **)(v83 + 8);
  v85 = (_BYTE *)v83;
  while ( !v84[25] )
  {
    if ( v84[26] >= 3u )
      v85 = v84;
    else
      v84 += 16;
    v84 = *(_BYTE **)v84;
  }
  if ( v85[25] || v85[26] > 3u || v85 == (_BYTE *)v83 )
    v86 = 0;
  else
    v86 = v85[27];
  v162[0] = v86;
  cdp::Serializer<cdp::JsonData>::AddValue<bool,bool>(a2, v162, &v318);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v318);
  v324 = 0;
  v325 = 0;
  *(_QWORD *)&v324 = std::allocator<char>::allocate(&v324, 32);
  v325 = _mm_load_si128((const __m128i *)&_xmm);
  strcpy((char *)v324, "UdpTransportEnabled");
  v87 = *(_QWORD *)(a1 + 696);
  v88 = *(_BYTE **)(v87 + 8);
  v89 = (_BYTE *)v87;
  while ( !v88[25] )
  {
    if ( v88[26] )
      v89 = v88;
    else
      v88 += 16;
    v88 = *(_BYTE **)v88;
  }
  if ( v89[25] || v89[26] > 1u || v89 == (_BYTE *)v87 )
    v90 = 0;
  else
    v90 = v89[27];
  v162[0] = v90;
  cdp::Serializer<cdp::JsonData>::AddValue<bool,bool>(a2, v162, &v324);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v324);
  v322 = 0;
  v323 = 0;
  *(_QWORD *)&v322 = std::allocator<char>::allocate(&v322, 32);
  v323 = _mm_load_si128((const __m128i *)&_xmm);
  strcpy((char *)v322, "BluetoothTransportEnabled");
  v91 = *(_QWORD *)(a1 + 696);
  v92 = *(_BYTE **)(v91 + 8);
  v93 = (_BYTE *)v91;
  while ( !v92[25] )
  {
    if ( v92[26] >= 4u )
      v93 = v92;
    else
      v92 += 16;
    v92 = *(_BYTE **)v92;
  }
  if ( v93[25] || v93[26] > 4u || v93 == (_BYTE *)v91 )
    v94 = 0;
  else
    v94 = v93[27];
  v162[0] = v94;
  cdp::Serializer<cdp::JsonData>::AddValue<bool,bool>(a2, v162, &v322);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v322);
  v310 = 0;
  v311 = 0;
  *(_QWORD *)&v310 = std::allocator<char>::allocate(&v310, 32);
  v311 = _mm_load_si128((const __m128i *)&_xmm);
  strcpy((char *)v310, "WifiDirectTransportEnabled");
  v95 = *(_QWORD *)(a1 + 696);
  v96 = *(_BYTE **)(v95 + 8);
  v97 = (_BYTE *)v95;
  while ( !v96[25] )
  {
    if ( v96[26] >= 5u )
      v97 = v96;
    else
      v96 += 16;
    v96 = *(_BYTE **)v96;
  }
  if ( v97[25] || v97[26] > 5u || v97 == (_BYTE *)v95 )
    v98 = 0;
  else
    v98 = v97[27];
  v162[0] = v98;
  cdp::Serializer<cdp::JsonData>::AddValue<bool,bool>(a2, v162, &v310);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v310);
  v312 = 0;
  v313 = 0;
  *(_QWORD *)&v312 = std::allocator<char>::allocate(&v312, 32);
  v313 = _mm_load_si128((const __m128i *)&_xmm);
  strcpy((char *)v312, "TcpTransportEnabled");
  v99 = *(_QWORD *)(a1 + 696);
  v100 = *(_BYTE **)(v99 + 8);
  v101 = (_BYTE *)v99;
  while ( !v100[25] )
  {
    if ( v100[26] >= 2u )
      v101 = v100;
    else
      v100 += 16;
    v100 = *(_BYTE **)v100;
  }
  if ( v101[25] || v101[26] > 2u || v101 == (_BYTE *)v99 )
    v102 = 0;
  else
    v102 = v101[27];
  v162[0] = v102;
  cdp::Serializer<cdp::JsonData>::AddValue<bool,bool>(a2, v162, &v312);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v312);
  v316 = 0;
  v317 = 0;
  *(_QWORD *)&v316 = std::allocator<char>::allocate(&v316, 32);
  v317 = _mm_load_si128((const __m128i *)&_xmm);
  strcpy((char *)v316, "CloudTransportHostingAllowed");
  v103 = *(_QWORD *)(a1 + 712);
  v104 = *(_BYTE **)(v103 + 8);
  v105 = (_BYTE *)v103;
  while ( !v104[25] )
  {
    if ( v104[26] >= 3u )
      v105 = v104;
    else
      v104 += 16;
    v104 = *(_BYTE **)v104;
  }
  if ( v105[25] || v105[26] > 3u || v105 == (_BYTE *)v103 )
    v106 = 0;
  else
    v106 = v105[27];
  v162[0] = v106;
  cdp::Serializer<cdp::JsonData>::AddValue<bool,bool>(a2, v162, &v316);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v316);
  v320 = 0;
  v321 = 0;
  *(_QWORD *)&v320 = std::allocator<char>::allocate(&v320, 32);
  v321 = _mm_load_si128((const __m128i *)&_xmm);
  strcpy((char *)v320, "UdpTransportHostingAllowed");
  v107 = *(_QWORD *)(a1 + 712);
  v108 = *(_BYTE **)(v107 + 8);
  v109 = (_BYTE *)v107;
  while ( !v108[25] )
  {
    if ( v108[26] )
      v109 = v108;
    else
      v108 += 16;
    v108 = *(_BYTE **)v108;
  }
  if ( v109[25] || v109[26] > 1u || v109 == (_BYTE *)v107 )
    v110 = 0;
  else
    v110 = v109[27];
  v162[0] = v110;
  cdp::Serializer<cdp::JsonData>::AddValue<bool,bool>(a2, v162, &v320);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v320);
  v344 = 0;
  v345 = 0;
  *(_QWORD *)&v344 = std::allocator<char>::allocate(&v344, 48);
  v345 = _mm_load_si128((const __m128i *)&_xmm);
  strcpy((char *)v344, "BluetoothTransportHostingAllowed");
  v111 = *(_QWORD *)(a1 + 712);
  v112 = *(_BYTE **)(v111 + 8);
  v113 = (_BYTE *)v111;
  while ( !v112[25] )
  {
    if ( v112[26] >= 4u )
      v113 = v112;
    else
      v112 += 16;
    v112 = *(_BYTE **)v112;
  }
  if ( v113[25] || v113[26] > 4u || v113 == (_BYTE *)v111 )
    v114 = 0;
  else
    v114 = v113[27];
  v162[0] = v114;
  cdp::Serializer<cdp::JsonData>::AddValue<bool,bool>(a2, v162, &v344);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v344);
  v350 = 0;
  v351 = 0;
  *(_QWORD *)&v350 = std::allocator<char>::allocate(&v350, 48);
  v351 = _mm_load_si128((const __m128i *)&_xmm);
  strcpy((char *)v350, "WifiDirectTransportHostingAllowed");
  v115 = *(_QWORD *)(a1 + 712);
  v116 = *(_BYTE **)(v115 + 8);
  v117 = (_BYTE *)v115;
  while ( !v116[25] )
  {
    if ( v116[26] >= 5u )
      v117 = v116;
    else
      v116 += 16;
    v116 = *(_BYTE **)v116;
  }
  if ( v117[25] || v117[26] > 5u || v117 == (_BYTE *)v115 )
    v118 = 0;
  else
    v118 = v117[27];
  v162[0] = v118;
  cdp::Serializer<cdp::JsonData>::AddValue<bool,bool>(a2, v162, &v350);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v350);
  v314 = 0;
  v315 = 0;
  *(_QWORD *)&v314 = std::allocator<char>::allocate(&v314, 32);
  v315 = _mm_load_si128((const __m128i *)&_xmm);
  strcpy((char *)v314, "TcpTransportHostingAllowed");
  v119 = *(_QWORD *)(a1 + 712);
  v120 = *(_BYTE **)(v119 + 8);
  v121 = (_BYTE *)v119;
  while ( !v120[25] )
  {
    if ( v120[26] >= 2u )
      v121 = v120;
    else
      v120 += 16;
    v120 = *(_BYTE **)v120;
  }
  if ( v121[25] || v121[26] > 2u || v121 == (_BYTE *)v119 )
    v122 = 0;
  else
    v122 = v121[27];
  v162[0] = v122;
  cdp::Serializer<cdp::JsonData>::AddValue<bool,bool>(a2, v162, &v314);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v314);
  v286 = 0;
  v287 = 0;
  *(_QWORD *)&v286 = std::allocator<char>::allocate(&v286, 32);
  v287 = _mm_load_si128((const __m128i *)&_xmm);
  strcpy((char *)v286, "ProtocolVersionBrokerEnabled");
  cdp::Serializer<cdp::JsonData>::AddValue<bool,bool>(a2, a1 + 728, &v286);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v286);
  v288 = 0;
  v289 = 0;
  *(_QWORD *)&v288 = std::allocator<char>::allocate(&v288, 32);
  v289 = _mm_load_si128((const __m128i *)&_xmm);
  strcpy((char *)v288, "TcpTransportUpgradeRequired");
  cdp::Serializer<cdp::JsonData>::AddValue<bool,bool>(a2, a1 + 729, &v288);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v288);
  v251 = 0;
  v252 = 7;
  v253 = 15;
  qmemcpy(v249, "POBoxe", sizeof(v249));
  v250 = (unsigned __int8)aPoboxes[6];
  v123 = Json::Value::type(a2 + 2);
  v124 = a2 + 2;
  if ( v123 == 7 )
  {
    v125 = (Json::Value *)Json::Value::operator[](v124, v249);
  }
  else
  {
    ++*a2;
    v125 = (Json::Value *)Json::Value::operator[](v124);
  }
  cdp::JsonContainer<std::vector<shared::POBoxInfo>>::Set(v125);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v249);
  v216 = 15;
  v217 = 15;
  qmemcpy(v214, "AccountSetting", sizeof(v214));
  v215 = (unsigned __int8)aAccountsetting[14];
  v126 = Json::Value::type(a2 + 2);
  v127 = a2 + 2;
  if ( v126 == 7 )
  {
    v128 = (Json::Value *)Json::Value::operator[](v127, v214);
  }
  else
  {
    ++*a2;
    v128 = (Json::Value *)Json::Value::operator[](v127);
  }
  cdp::JsonContainer<std::vector<shared::AccountSettings>>::Set(v128);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v214);
  v220 = 15;
  v221 = 15;
  qmemcpy(v218, "CustomAuthClsi", sizeof(v218));
  v219 = (unsigned __int8)aCustomauthclsi[14];
  v129 = Json::Value::type(a2 + 2);
  v130 = a2 + 2;
  if ( v129 == 7 )
  {
    v131 = Json::Value::operator[](v130, v218);
  }
  else
  {
    ++*a2;
    v131 = Json::Value::operator[](v130);
  }
  v132 = v131;
  v133 = Json::Value::Value(v165, a1 + 816);
  Json::Value::operator=(v132, v133);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v218);
  v222 = 0;
  v223 = 0;
  v224 = 0;
  *(_QWORD *)&v222 = std::allocator<char>::allocate(&v222, 32);
  v223 = 17;
  v224 = 31;
  strcpy((char *)v222, "LatestCdpUsedTime");
  v134 = "%04u-%02u-%02uT%02u:%02u:%02u.%03uZ";
  if ( !*(_BYTE *)(a1 + 940) )
    v134 = "%04u-%02u-%02uT%02u:%02u:%02u.%03u";
  cdp::detail::StringFormat(
    v376,
    v134,
    *(unsigned int *)(a1 + 920),
    *(unsigned int *)(a1 + 912),
    *(_DWORD *)(a1 + 916),
    *(_DWORD *)(a1 + 924),
    *(_DWORD *)(a1 + 928),
    *(_DWORD *)(a1 + 932),
    *(_DWORD *)(a1 + 936));
  if ( !v223 && (unsigned int)Json::Value::type(a2 + 2) != 6 )
  {
    v163 = "onecoreuap\\windows\\cdp\\common\\internal\\JsonSerializer.h";
    v164 = 55;
    v136 = cdp::MakeException<std::invalid_argument,>(
             v188,
             v135,
             "Failed to add value, name required for object serialization");
    cdp::CdpThrow<std::invalid_argument>(&v163, v136);
  }
  v137 = Json::Value::type(a2 + 2);
  v138 = a2 + 2;
  if ( v137 == 7 )
  {
    v139 = Json::Value::operator[](v138, &v222);
  }
  else
  {
    ++*a2;
    v139 = Json::Value::operator[](v138);
  }
  v140 = v139;
  v141 = Json::Value::Value(v180, v376);
  Json::Value::operator=(v140, v141);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v376);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v222);
  v290 = 0;
  v291 = 0;
  *(_QWORD *)&v290 = std::allocator<char>::allocate(&v290, 32);
  v291 = _mm_load_si128((const __m128i *)&_xmm);
  strcpy((char *)v290, "LatestFixAccountToastTime");
  cdp::Serializer<cdp::JsonData>::AddValue<std::map<std::string,CDP_DATE_TIME>,std::map<std::string,CDP_DATE_TIME>>(
    a2,
    a1 + 944,
    &v290);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v290);
  v292 = 0;
  v293 = 0;
  *(_QWORD *)&v292 = std::allocator<char>::allocate(&v292, 32);
  v293 = _mm_load_si128((const __m128i *)&_xmm);
  strcpy((char *)v292, "InboundMessageThreadPoolCount");
  cdp::Serializer<cdp::JsonData>::AddValue<unsigned char,unsigned char>(a2, a1 + 960, &v292);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v292);
  v294 = 0;
  v295 = 0;
  *(_QWORD *)&v294 = std::allocator<char>::allocate(&v294, 32);
  v295 = _mm_load_si128((const __m128i *)&_xmm);
  strcpy((char *)v294, "OutboundMessageThreadPoolCount");
  cdp::Serializer<cdp::JsonData>::AddValue<unsigned char,unsigned char>(a2, a1 + 961, &v294);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v294);
  v296 = 0;
  v297 = 0;
  *(_QWORD *)&v296 = std::allocator<char>::allocate(&v296, 32);
  v297 = _mm_load_si128((const __m128i *)&_xmm);
  strcpy((char *)v296, "AfsPostInitializeSyncWaitMs");
  cdp::Serializer<cdp::JsonData>::AddValue<unsigned int,unsigned int>(a2, a1 + 964, &v296);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v296);
  v298 = 0;
  v299 = 0;
  *(_QWORD *)&v298 = std::allocator<char>::allocate(&v298, 32);
  v299 = _mm_load_si128((const __m128i *)&_xmm);
  strcpy((char *)v298, "AfsSyncFrequencyMs");
  cdp::Serializer<cdp::JsonData>::AddValue<unsigned int,unsigned int>(a2, a1 + 968, &v298);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v298);
  v300 = 0;
  v301 = 0;
  *(_QWORD *)&v300 = std::allocator<char>::allocate(&v300, 32);
  v301 = _mm_load_si128((const __m128i *)&_xmm);
  strcpy((char *)v300, "MaximumSocketBuffers");
  cdp::Serializer<cdp::JsonData>::AddValue<unsigned int,unsigned int>(a2, a1 + 972, &v300);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v300);
  v302 = 0;
  v303 = 0;
  *(_QWORD *)&v302 = std::allocator<char>::allocate(&v302, 32);
  v303 = _mm_load_si128((const __m128i *)&_xmm);
  strcpy((char *)v302, "MaximumConcurrentBluetoothSends");
  cdp::Serializer<cdp::JsonData>::AddValue<unsigned int,unsigned int>(a2, a1 + 976, &v302);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v302);
  v348 = 0;
  v349 = 0;
  *(_QWORD *)&v348 = std::allocator<char>::allocate(&v348, 48);
  v349 = _mm_load_si128((const __m128i *)&_xmm);
  strcpy((char *)v348, "MaximumUnreliableMessageQueueSize");
  cdp::Serializer<cdp::JsonData>::AddValue<unsigned int,unsigned int>(a2, a1 + 980, &v348);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v348);
  v304 = 0;
  v305 = 0;
  *(_QWORD *)&v304 = std::allocator<char>::allocate(&v304, 32);
  v305 = _mm_load_si128((const __m128i *)&_xmm);
  strcpy((char *)v304, "AfcPrivacySettings");
  cdp::Serializer<cdp::JsonData>::AddValue<shared::ActivityFeedPrivacySettings,shared::ActivityFeedPrivacySettings>(
    a2,
    a1 + 992,
    &v304);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v304);
  v225 = 0;
  v226 = 0;
  v227 = 0;
  *(_QWORD *)&v225 = std::allocator<char>::allocate(&v225, 32);
  v226 = 29;
  v227 = 31;
  strcpy((char *)v225, "CloudDataMDMActivitiyPolicies");
  if ( !v226 && (unsigned int)Json::Value::type(a2 + 2) != 6 )
  {
    v163 = "onecoreuap\\windows\\cdp\\common\\internal\\JsonSerializer.h";
    v164 = 55;
    v143 = cdp::MakeException<std::invalid_argument,>(
             v189,
             v142,
             "Failed to add value, name required for object serialization");
    cdp::CdpThrow<std::invalid_argument>(&v163, v143);
  }
  v144 = Json::Value::type(a2 + 2);
  v145 = a2 + 2;
  if ( v144 == 7 )
  {
    v146 = (Json::Value *)Json::Value::operator[](v145, &v225);
  }
  else
  {
    ++*a2;
    v146 = (Json::Value *)Json::Value::operator[](v145);
  }
  cdp::JsonContainer<std::set<shared::ActivityPolicy>>::Set(v146);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v225);
  v228 = 0;
  v229 = 0;
  v230 = 0;
  *(_QWORD *)&v228 = std::allocator<char>::allocate(&v228, 48);
  v229 = 37;
  v230 = 47;
  strcpy((char *)v228, "CloudDataGroupPolicyActivitiyPolicies");
  if ( !v229 && (unsigned int)Json::Value::type(a2 + 2) != 6 )
  {
    v163 = "onecoreuap\\windows\\cdp\\common\\internal\\JsonSerializer.h";
    v164 = 55;
    v148 = cdp::MakeException<std::invalid_argument,>(
             v190,
             v147,
             "Failed to add value, name required for object serialization");
    cdp::CdpThrow<std::invalid_argument>(&v163, v148);
  }
  v149 = Json::Value::type(a2 + 2);
  v150 = a2 + 2;
  if ( v149 == 7 )
  {
    v151 = (Json::Value *)Json::Value::operator[](v150, &v228);
  }
  else
  {
    ++*a2;
    v151 = (Json::Value *)Json::Value::operator[](v150);
  }
  cdp::JsonContainer<std::set<shared::ActivityPolicy>>::Set(v151);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v228);
  v256 = _mm_load_si128((const __m128i *)&_xmm);
  qmemcpy(v254, "FastPathEnable", sizeof(v254));
  v255 = (unsigned __int8)aFastpathenable[14];
  cdp::Serializer<cdp::JsonData>::AddValue<bool,bool>(a2, a1 + 1040, v254);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v254);
  v306 = 0;
  v307 = 0;
  *(_QWORD *)&v306 = std::allocator<char>::allocate(&v306, 32);
  v307 = _mm_load_si128((const __m128i *)&_xmm);
  strcpy((char *)v306, "FastPathSequencingEnabled");
  cdp::Serializer<cdp::JsonData>::AddValue<bool,bool>(a2, a1 + 1041, &v306);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v306);
  if ( !(unsigned __int8)std::vector<shared::ActivityStoreInfo>::empty(a1 + 1048) )
  {
    std::string::string(v377, "ActivityStoreInfo");
    cdp::Serializer<cdp::JsonData>::AddValue<std::vector<shared::ActivityStoreInfo>,std::vector<shared::ActivityStoreInfo>>(
      a2,
      a1 + 1048,
      v377);
    std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v377);
  }
  v308 = 0;
  v309 = 0;
  *(_QWORD *)&v308 = std::allocator<char>::allocate(&v308, 32);
  v309 = _mm_load_si128((const __m128i *)&_xmm);
  strcpy((char *)v308, "ProtocolLiveTraceEnabled");
  cdp::Serializer<cdp::JsonData>::AddValue<bool,bool>(a2, a1 + 730, &v308);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v308);
  v231 = 0;
  v232 = 0;
  v233 = 0;
  *(_QWORD *)&v231 = std::allocator<char>::allocate(&v231, 32);
  v232 = 23;
  v233 = 31;
  strcpy((char *)v231, "ProtocolLiveTraceServer");
  if ( !v232 && (unsigned int)Json::Value::type(a2 + 2) != 6 )
  {
    v163 = "onecoreuap\\windows\\cdp\\common\\internal\\JsonSerializer.h";
    v164 = 55;
    v153 = cdp::MakeException<std::invalid_argument,>(
             v191,
             v152,
             "Failed to add value, name required for object serialization");
    cdp::CdpThrow<std::invalid_argument>(&v163, v153);
  }
  v154 = Json::Value::type(a2 + 2);
  v155 = a2 + 2;
  if ( v154 == 7 )
  {
    v156 = Json::Value::operator[](v155, &v231);
  }
  else
  {
    ++*a2;
    v156 = Json::Value::operator[](v155);
  }
  v157 = v156;
  v158 = Json::Value::Value(v166, a1 + 736);
  Json::Value::operator=(v157, v158);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(&v231);
  LOBYTE(v159) = v162[0];
  std::_Compressed_pair<std::allocator<char>,std::_String_val<std::_Simple_types<char>>,1>::_Compressed_pair<std::allocator<char>,std::_String_val<std::_Simple_types<char>>,1>(
    v356,
    v159);
  v160 = std::_Narrow_char_traits<char,int>::length("AfsConnectivityEnabled");
  v161 = std::_Convert_size<unsigned __int64,unsigned __int64>(v160);
  std::string::_Construct<1,char const *>(v356, "AfsConnectivityEnabled", v161);
  cdp::Serializer<cdp::JsonData>::AddValue<bool>(a2, a1 + 732, v356);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v356);
  std::string::string(v357, "DdsRegistrationEnabled");
  cdp::Serializer<cdp::JsonData>::AddValue<bool>(a2, a1 + 731, v357);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v357);
  std::string::string(v358, "LowestRssiAllowedForBleDiscovery");
  cdp::Serializer<cdp::JsonData>::AddValue<short>(a2, a1 + 734, v358);
  std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(v358);
}

```

## disassembly

```asm
0x1800301fc  mov     [rsp-8+arg_10], rbx
0x180030201  push    rbp
0x180030202  push    rsi
0x180030203  push    rdi
0x180030204  push    r12
0x180030206  push    r13
0x180030208  push    r14
0x18003020a  push    r15
0x18003020c  lea     rbp, [rsp-0E30h]
0x180030214  sub     rsp, 0F30h
0x18003021b  mov     rax, cs:__security_cookie
0x180030222  xor     rax, rsp
0x180030225  mov     [rbp+0E60h+var_38], rax
0x18003022c  mov     rbx, rdx
0x18003022f  mov     rsi, rcx
0x180030232  xor     r12d, r12d
0x180030235  xorps   xmm0, xmm0
0x180030238  movups  [rbp+0E60h+var_910], xmm0
0x18003023f  movdqa  xmm1, cs:__xmm@000000000000000f000000000000000d
0x180030247  movdqu  [rbp+0E60h+var_900], xmm1
0x18003024f  mov     rax, 655674616D726F46h
0x180030259  mov     qword ptr [rbp+0E60h+var_910], rax
0x180030260  mov     eax, dword ptr cs:aFormatversion+8; "rsion"
0x180030266  mov     dword ptr [rbp+0E60h+var_910+8], eax
0x18003026c  mov     al, byte ptr cs:aFormatversion+0Ch; "n"
0x180030272  mov     byte ptr [rbp+0E60h+var_910+0Ch], al
0x180030278  mov     byte ptr [rbp+0E60h+var_910+0Dh], r12b
0x18003027f  lea     r8, [rbp+0E60h+var_910]
0x180030286  lea     rdx, ?FormatVersion@GlobalSettingsBaseStorage@SharedGlobalSettingsBase@shared@@2IB; uint const shared::SharedGlobalSettingsBase::GlobalSettingsBaseStorage::FormatVersion
0x18003028d  mov     rcx, rbx
0x180030290  call    ??$AddValue@II@?$Serializer@UJsonData@cdp@@@cdp@@QEAAXAEBIAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; cdp::Serializer<cdp::JsonData>::AddValue<uint,uint>(uint const &,std::string const &)
0x180030295  nop
0x180030296  lea     rcx, [rbp+0E60h+var_910]; void *
0x18003029d  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x1800302a2  xorps   xmm0, xmm0
0x1800302a5  movups  [rbp+0E60h+var_B70], xmm0
0x1800302ac  lea     eax, [r12+0Fh]
0x1800302b1  mov     [rbp+0E60h+var_B60], rax
0x1800302b8  mov     [rbp+0E60h+var_B58], rax
0x1800302bf  mov     rax, 446C617574726956h
0x1800302c9  mov     qword ptr [rbp+0E60h+var_B70], rax
0x1800302d0  mov     eax, dword ptr cs:aVirtualdevicei+8; "eviceId"
0x1800302d6  mov     dword ptr [rbp+0E60h+var_B70+8], eax
0x1800302dc  movzx   eax, word ptr cs:aVirtualdevicei+0Ch; "eId"
0x1800302e3  mov     word ptr [rbp+0E60h+var_B70+0Ch], ax
0x1800302ea  mov     al, byte ptr cs:aVirtualdevicei+0Eh; "d"
0x1800302f0  mov     byte ptr [rbp+0E60h+var_B70+0Eh], al
0x1800302f6  mov     byte ptr [rbp+0E60h+var_B70+0Fh], r12b
0x1800302fd  lea     rdi, [rbx+8]
0x180030301  mov     rcx, rdi
0x180030304  call    ?type@Value@Json@@QEBA?AW4ValueType@2@XZ; Json::Value::type(void)
0x180030309  mov     rcx, rdi
0x18003030c  cmp     eax, 7
0x18003030f  jnz     short loc_18003031F
0x180030311  lea     rdx, [rbp+0E60h+var_B70]
0x180030318  call    ??AValue@Json@@QEAAAEAV01@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Json::Value::operator[](std::string const &)
0x18003031d  jmp     short loc_18003032B
0x18003031f  mov     edx, [rbx]
0x180030321  lea     eax, [rdx+1]
0x180030324  mov     [rbx], eax
0x180030326  call    ??AValue@Json@@QEAAAEAV01@I@Z; Json::Value::operator[](uint)
0x18003032b  mov     r14, rax
0x18003032e  mov     rdx, rsi
0x180030331  lea     rcx, [rbp+0E60h+var_CF0]
0x180030338  call    ??0Value@Json@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Json::Value::Value(std::string const &)
0x18003033d  mov     rdx, rax
0x180030340  mov     rcx, r14
0x180030343  call    ??4Value@Json@@QEAAAEAV01@V01@@Z; Json::Value::operator=(Json::Value)
0x180030348  nop
0x180030349  lea     rcx, [rbp+0E60h+var_B70]; void *
0x180030350  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x180030355  cmp     dword ptr [rsi+28h], 0FFFFFFFFh
0x180030359  jz      short loc_18003038F
0x18003035b  lea     rdx, aTracelogCompon; "TraceLog.ComponentFlags"
0x180030362  lea     rcx, [rbp+0E60h+var_1D8]
0x180030369  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18003036e  nop
0x18003036f  lea     r8, [rbp+0E60h+var_1D8]
0x180030376  lea     rdx, [rsi+28h]
0x18003037a  mov     rcx, rbx
0x18003037d  call    ??$AddValue@W4TraceComponents@shared@@W412@@?$Serializer@UJsonData@cdp@@@cdp@@QEAAXAEBW4TraceComponents@shared@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; cdp::Serializer<cdp::JsonData>::AddValue<shared::TraceComponents,shared::TraceComponents>(shared::TraceComponents const &,std::string const &)
0x180030382  nop
0x180030383  lea     rcx, [rbp+0E60h+var_1D8]; void *
0x18003038a  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x18003038f  xorps   xmm0, xmm0
0x180030392  movups  [rbp+0E60h+var_8F0], xmm0
0x180030399  movdqa  xmm1, cs:__xmm@000000000000000f000000000000000e
0x1800303a1  movdqu  [rbp+0E60h+var_8E0], xmm1
0x1800303a9  mov     rax, 676F4C6563617254h
0x1800303b3  mov     qword ptr [rbp+0E60h+var_8F0], rax
0x1800303ba  mov     eax, dword ptr cs:aTracelogLevel+8; ".Level"
0x1800303c0  mov     dword ptr [rbp+0E60h+var_8F0+8], eax
0x1800303c6  movzx   eax, word ptr cs:aTracelogLevel+0Ch; "el"
0x1800303cd  mov     word ptr [rbp+0E60h+var_8F0+0Ch], ax
0x1800303d4  mov     byte ptr [rbp+0E60h+var_8F0+0Eh], r12b
0x1800303db  lea     rdx, [rsi+20h]
0x1800303df  lea     r8, [rbp+0E60h+var_8F0]
0x1800303e6  mov     rcx, rbx
0x1800303e9  call    ??$AddValue@W4CDPLogLevel@@W41@@?$Serializer@UJsonData@cdp@@@cdp@@QEAAXAEBW4CDPLogLevel@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; cdp::Serializer<cdp::JsonData>::AddValue<CDPLogLevel,CDPLogLevel>(CDPLogLevel const &,std::string const &)
0x1800303ee  nop
0x1800303ef  lea     rcx, [rbp+0E60h+var_8F0]; void *
0x1800303f6  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x1800303fb  xorps   xmm0, xmm0
0x1800303fe  movups  [rbp+0E60h+var_850], xmm0
0x180030405  xorps   xmm1, xmm1
0x180030408  movdqu  [rbp+0E60h+var_840], xmm1
0x180030410  mov     r13d, 20h ; ' '
0x180030416  mov     edx, r13d
0x180030419  lea     rcx, [rbp+0E60h+var_850]
0x180030420  call    ?allocate@?$allocator@D@std@@QEAAPEAD_K@Z; std::allocator<char>::allocate(unsigned __int64)
0x180030425  mov     qword ptr [rbp+0E60h+var_850], rax
0x18003042c  movdqa  xmm0, cs:__xmm@000000000000001f000000000000001c
0x180030434  movdqu  [rbp+0E60h+var_840], xmm0
0x18003043c  movups  xmm0, xmmword ptr cs:aTracelogEnable; "TraceLog.EnabledHandlerTypes"
0x180030443  movups  xmmword ptr [rax], xmm0
0x180030446  movups  xmm1, xmmword ptr cs:aTracelogEnable+0Ch; "bledHandlerTypes"
0x18003044d  movups  xmmword ptr [rax+0Ch], xmm1
0x180030451  mov     [rax+1Ch], r12b
0x180030455  lea     rdx, [rsi+24h]
0x180030459  lea     r8, [rbp+0E60h+var_850]
0x180030460  mov     rcx, rbx
0x180030463  call    ??$AddValue@W4TraceHandlers@shared@@W412@@?$Serializer@UJsonData@cdp@@@cdp@@QEAAXAEBW4TraceHandlers@shared@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; cdp::Serializer<cdp::JsonData>::AddValue<shared::TraceHandlers,shared::TraceHandlers>(shared::TraceHandlers const &,std::string const &)
0x180030468  nop
0x180030469  lea     rcx, [rbp+0E60h+var_850]; void *
0x180030470  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x180030475  cmp     [rsi+2Ch], r12b
0x180030479  jz      short loc_1800304AF
0x18003047b  lea     rdx, aTracelogRemote; "TraceLog.RemoteViewerEnabled"
0x180030482  lea     rcx, [rbp+0E60h+var_1F8]
0x180030489  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18003048e  nop
0x18003048f  lea     r8, [rbp+0E60h+var_1F8]
0x180030496  lea     rdx, [rsi+2Ch]
0x18003049a  mov     rcx, rbx
0x18003049d  call    ??$AddValue@_N_N@?$Serializer@UJsonData@cdp@@@cdp@@QEAAXAEB_NAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; cdp::Serializer<cdp::JsonData>::AddValue<bool,bool>(bool const &,std::string const &)
0x1800304a2  nop
0x1800304a3  lea     rcx, [rbp+0E60h+var_1F8]; void *
0x1800304aa  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x1800304af  cmp     [rsi+40h], r12
0x1800304b3  jz      short loc_1800304E9
0x1800304b5  lea     rdx, aTracelogRemote_0; "TraceLog.RemoteViewerAddress"
0x1800304bc  lea     rcx, [rbp+0E60h+var_218]
0x1800304c3  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800304c8  nop
0x1800304c9  lea     r8, [rbp+0E60h+var_218]
0x1800304d0  lea     rdx, [rsi+30h]
0x1800304d4  mov     rcx, rbx
0x1800304d7  call    ??$AddValue@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@?$Serializer@UJsonData@cdp@@@cdp@@QEAAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@0@Z; cdp::Serializer<cdp::JsonData>::AddValue<std::string,std::string>(std::string const &,std::string const &)
0x1800304dc  nop
0x1800304dd  lea     rcx, [rbp+0E60h+var_218]; void *
0x1800304e4  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x1800304e9  cmp     [rsi+50h], r12b
0x1800304ed  jz      short loc_18003055E
0x1800304ef  cmp     word ptr [rsi+52h], 0Bh
0x1800304f4  jz      short loc_18003055E
0x1800304f6  lea     rdx, aChaosmonkeySes; "ChaosMonkey.SessionMessageReceivedDropR"...
0x1800304fd  lea     rcx, [rbp+0E60h+var_238]
0x180030504  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180030509  nop
0x18003050a  lea     r8, [rbp+0E60h+var_238]
0x180030511  lea     rdx, [rsi+50h]
0x180030515  mov     rcx, rbx
0x180030518  call    ??$AddValue@_N_N@?$Serializer@UJsonData@cdp@@@cdp@@QEAAXAEB_NAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; cdp::Serializer<cdp::JsonData>::AddValue<bool,bool>(bool const &,std::string const &)
0x18003051d  nop
0x18003051e  lea     rcx, [rbp+0E60h+var_238]; void *
0x180030525  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x18003052a  lea     rdx, aChaosmonkeySes_0; "ChaosMonkey.SessionMessageReceivedDropR"...
0x180030531  lea     rcx, [rbp+0E60h+var_278]
0x180030538  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18003053d  nop
0x18003053e  lea     r8, [rbp+0E60h+var_278]
0x180030545  lea     rdx, [rsi+52h]
0x180030549  mov     rcx, rbx
0x18003054c  call    ??$AddValue@GG@?$Serializer@UJsonData@cdp@@@cdp@@QEAAXAEBGAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; cdp::Serializer<cdp::JsonData>::AddValue<ushort,ushort>(ushort const &,std::string const &)
0x180030551  nop
0x180030552  lea     rcx, [rbp+0E60h+var_278]; void *
0x180030559  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x18003055e  cmp     dword ptr [rsi+54h], 0BB8h
0x180030565  jz      short loc_18003059B
0x180030567  lea     rdx, aHeartbeatIdlet; "Heartbeat.IdleTimeOut"
0x18003056e  lea     rcx, [rbp+0E60h+var_298]
0x180030575  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18003057a  nop
0x18003057b  lea     r8, [rbp+0E60h+var_298]
0x180030582  lea     rdx, [rsi+54h]
0x180030586  mov     rcx, rbx
0x180030589  call    ??$AddValue@II@?$Serializer@UJsonData@cdp@@@cdp@@QEAAXAEBIAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; cdp::Serializer<cdp::JsonData>::AddValue<uint,uint>(uint const &,std::string const &)
0x18003058e  nop
0x18003058f  lea     rcx, [rbp+0E60h+var_298]; void *
0x180030596  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x18003059b  xorps   xmm0, xmm0
0x18003059e  movups  [rbp+0E60h+var_368], xmm0
0x1800305a5  xorps   xmm1, xmm1
0x1800305a8  movdqu  [rbp+0E60h+var_358], xmm1
0x1800305b0  mov     r14d, 30h ; '0'
0x1800305b6  mov     edx, r14d
0x1800305b9  lea     rcx, [rbp+0E60h+var_368]
0x1800305c0  call    ?allocate@?$allocator@D@std@@QEAAPEAD_K@Z; std::allocator<char>::allocate(unsigned __int64)
0x1800305c5  mov     qword ptr [rbp+0E60h+var_368], rax
0x1800305cc  movdqa  xmm0, cs:__xmm@000000000000002f0000000000000024
0x1800305d4  movdqu  [rbp+0E60h+var_358], xmm0
0x1800305dc  mov     rcx, 65532E64756F6C43h
0x1800305e6  mov     [rax], rcx
0x1800305e9  mov     rcx, 6C64496E6F697373h
0x1800305f3  mov     [rax+8], rcx
0x1800305f7  mov     rcx, 74756F656D695465h
0x180030601  mov     [rax+10h], rcx
0x180030605  mov     rcx, 6C61767265746E49h
0x18003060f  mov     [rax+18h], rcx
0x180030613  mov     dword ptr [rax+20h], 73636553h
0x18003061a  mov     [rax+24h], r12b
0x18003061e  lea     rdx, [rsi+5Ch]
0x180030622  lea     r8, [rbp+0E60h+var_368]
0x180030629  mov     rcx, rbx
0x18003062c  call    ??$AddValue@II@?$Serializer@UJsonData@cdp@@@cdp@@QEAAXAEBIAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; cdp::Serializer<cdp::JsonData>::AddValue<uint,uint>(uint const &,std::string const &)
0x180030631  nop
0x180030632  lea     rcx, [rbp+0E60h+var_368]; void *
0x180030639  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x18003063e  xorps   xmm0, xmm0
0x180030641  movups  [rbp+0E60h+var_430], xmm0
0x180030648  xorps   xmm1, xmm1
0x18003064b  movdqu  [rbp+0E60h+var_420], xmm1
0x180030653  mov     edx, r14d
0x180030656  lea     rcx, [rbp+0E60h+var_430]
0x18003065d  call    ?allocate@?$allocator@D@std@@QEAAPEAD_K@Z; std::allocator<char>::allocate(unsigned __int64)
0x180030662  mov     qword ptr [rbp+0E60h+var_430], rax
0x180030669  movdqa  xmm0, cs:__xmm@000000000000002f0000000000000020
0x180030671  movdqu  [rbp+0E60h+var_420], xmm0
0x180030679  movups  xmm0, xmmword ptr cs:aLargepayloadEx; "LargePayload.ExtendedTimeoutSecs"
0x180030680  movups  xmmword ptr [rax], xmm0
0x180030683  movups  xmm1, xmmword ptr cs:aLargepayloadEx+10h; "endedTimeoutSecs"
0x18003068a  movups  xmmword ptr [rax+10h], xmm1
0x18003068e  mov     [rax+20h], r12b
0x180030692  lea     rdx, [rsi+64h]
0x180030696  lea     r8, [rbp+0E60h+var_430]
0x18003069d  mov     rcx, rbx
0x1800306a0  call    ??$AddValue@II@?$Serializer@UJsonData@cdp@@@cdp@@QEAAXAEBIAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; cdp::Serializer<cdp::JsonData>::AddValue<uint,uint>(uint const &,std::string const &)
0x1800306a5  nop
0x1800306a6  lea     rcx, [rbp+0E60h+var_430]; void *
0x1800306ad  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x1800306b2  xorps   xmm0, xmm0
0x1800306b5  movups  [rbp+0E60h+var_830], xmm0
0x1800306bc  xorps   xmm1, xmm1
0x1800306bf  movdqu  [rbp+0E60h+var_820], xmm1
0x1800306c7  mov     rdx, r13
0x1800306ca  lea     rcx, [rbp+0E60h+var_830]
0x1800306d1  call    ?allocate@?$allocator@D@std@@QEAAPEAD_K@Z; std::allocator<char>::allocate(unsigned __int64)
0x1800306d6  mov     qword ptr [rbp+0E60h+var_830], rax
0x1800306dd  movdqa  xmm0, cs:__xmm@000000000000001f000000000000001b
0x1800306e5  movdqu  [rbp+0E60h+var_820], xmm0
0x1800306ed  movups  xmm0, xmmword ptr cs:aLargepayloadTh; "LargePayload.ThresholdBytes"
0x1800306f4  movups  xmmword ptr [rax], xmm0
0x1800306f7  movups  xmm1, xmmword ptr cs:aLargepayloadTh+0Bh; "d.ThresholdBytes"
0x1800306fe  movups  xmmword ptr [rax+0Bh], xmm1
0x180030702  mov     [rax+1Bh], r12b
0x180030706  lea     rdx, [rsi+60h]
0x18003070a  lea     r8, [rbp+0E60h+var_830]
0x180030711  mov     rcx, rbx
0x180030714  call    ??$AddValue@II@?$Serializer@UJsonData@cdp@@@cdp@@QEAAXAEBIAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; cdp::Serializer<cdp::JsonData>::AddValue<uint,uint>(uint const &,std::string const &)
0x180030719  nop
0x18003071a  lea     rcx, [rbp+0E60h+var_830]; void *
0x180030721  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x180030726  cmp     dword ptr [rsi+58h], 493E0h
0x18003072d  jz      short loc_180030763
0x18003072f  lea     rdx, aIdleTimeout; "Idle.TimeOut"
0x180030736  lea     rcx, [rbp+0E60h+var_2B8]
0x18003073d  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180030742  nop
0x180030743  lea     r8, [rbp+0E60h+var_2B8]
0x18003074a  lea     rdx, [rsi+58h]
0x18003074e  mov     rcx, rbx
0x180030751  call    ??$AddValue@II@?$Serializer@UJsonData@cdp@@@cdp@@QEAAXAEBIAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; cdp::Serializer<cdp::JsonData>::AddValue<uint,uint>(uint const &,std::string const &)
0x180030756  nop
0x180030757  lea     rcx, [rbp+0E60h+var_2B8]; void *
0x18003075e  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x180030763  mov     eax, 64h ; 'd'
0x180030768  cmp     [rsi+6Ah], ax
0x18003076c  jz      short loc_1800307A2
0x18003076e  lea     rdx, aMessagepolicyP; "MessagePolicy.Priority"
0x180030775  lea     rcx, [rbp+0E60h+var_D8]
0x18003077c  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180030781  nop
0x180030782  lea     r8, [rbp+0E60h+var_D8]
0x180030789  lea     rdx, [rsi+6Ah]
0x18003078d  mov     rcx, rbx
0x180030790  call    ??$AddValue@GG@?$Serializer@UJsonData@cdp@@@cdp@@QEAAXAEBGAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; cdp::Serializer<cdp::JsonData>::AddValue<ushort,ushort>(ushort const &,std::string const &)
0x180030795  nop
0x180030796  lea     rcx, [rbp+0E60h+var_D8]; void *
0x18003079d  call    ??1?$tuple@UDiscoveryResponseSeenEntry@UdpDiscoverer@cdp@@@std@@QEAA@XZ; std::tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>::~tuple<cdp::UdpDiscoverer::DiscoveryResponseSeenEntry>(void)
0x1800307a2  cmp     word ptr [rsi+68h], 0Ah
0x1800307a7  jz      short loc_1800307DD
0x1800307a9  lea     rdx, aMessagepolicyR_0; "MessagePolicy.RetryCount"
0x1800307b0  lea     rcx, [rbp+0E60h+var_178]
0x1800307b7  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800307bc  nop
0x1800307bd  lea     r8, [rbp+0E60h+var_178]
0x1800307c4  lea     rdx, [rsi+68h]
0x1800307c8  mov     rcx, rbx
0x1800307cb  call    ??$AddValue@GG@?$Serializer@UJsonData@cdp@@@cdp@@QEAAXAEBGAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; cdp::Serializer<cdp::JsonData>::AddValue<ushort,ushort>(ushort const &,std::string const &)
0x1800307d0  nop
  ... truncated ...
```
