# Microsoft::RdpNano::ICESourceAdapter::Initialize(bool,Microsoft::Basix::Guid,std::shared_ptr<Microsoft::Basix::Dct::IPortAllocator>,unsigned __int64,int,void const *,std::vector<std::basic_string<char,std::char_traits<char>,std::allocator<char>>,std::allocator<std::basic_string<char,std::char_traits<char>,std::allocator<char>>>> const &,std::vector<Microsoft::Basix::Dct::ICE::Agent::TurnServer,std::allocator<Microsoft::Basix::Dct::ICE::Agent::TurnServer>> const &,boost::property_tree::basic_ptree<std::basic_string<char,std::char_traits<char>,std::allocator<char>>,boost::any,std::less<std::basic_string<char,std::char_traits<char>,std::allocator<char>>>> &)

- ea: `0x1800fa23c`
- end: `0x1800fd3b9`
- name: `?Initialize@ICESourceAdapter@RdpNano@Microsoft@@QEAAJ_NUGuid@Basix@3@V?$shared_ptr@VIPortAllocator@Dct@Basix@Microsoft@@@std@@_KHPEBXAEBV?$vector@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$allocator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@7@AEBV?$vector@UTurnServer@Agent@ICE@Dct@Basix@Microsoft@@V?$allocator@UTurnServer@Agent@ICE@Dct@Basix@Microsoft@@@std@@@7@AEAV?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@Z`
- size: `12669`
- prototype: ``
- caller_count: `3`
- callee_count: `43`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800cab00`
- `0x1800e1a60`
- `0x1800efd68`

## callees

- `0x18000d9c0`
- `0x180010a60`
- `0x180015bb8`
- `0x180016e20`
- `0x180017380`
- `0x180018b94`
- `0x18001902c`
- `0x18001b6b8`
- `0x18001dad8`
- `0x18001db78`
- `0x1800215c8`
- `0x1800216a0`
- `0x180021778`
- `0x180021850`
- `0x180024700`
- `0x180024760`
- `0x180028820`
- `0x180029d20`
- `0x18003e2e0`
- `0x18004e1dc`
- `0x1800b94bc`
- `0x1800c0000`
- `0x1800c5f74`
- `0x1800c76d4`
- `0x1800c81d0`
- `0x1800f2f34`
- `0x1800f33a4`
- `0x1800f6bb8`
- `0x1800f6c90`
- `0x1800f6d68`
- `0x1800f6e40`
- `0x1800f6f18`
- `0x1800f6ff0`
- `0x1800f91d0`
- `0x1800fa23c`
- `0x1801b4ef8`
- `0x1802e429c`
- `0x1802f14d0`
- `0x180312e30`
- `0x18032f050`
- `0x18032f0b0`
- `0x180375c40`
- `0x180376380`

## string_xrefs

- `0x1800fafc2`: `SOFTWARE\Policies\Microsoft\Windows NT\Terminal Services`
- `0x1800fb3f8`: `SOFTWARE\Policies\Microsoft\Windows NT\Terminal Services`
- `0x1800fc7b3`: `NanoConfigurations`
- `0x1800faede`: `Microsoft::Basix::Dct.ICE.UDP.Component.Type`
- `0x1800faf65`: `Microsoft::Basix::Dct.ICE.UDP.Component.Type`
- `0x1800fc79b`: `ICE Configurations`

## pseudocode

```c
// Hidden C++ exception states: #wind=264
__int64 __fastcall Microsoft::RdpNano::ICESourceAdapter::Initialize(
        __int64 a1,
        char a2,
        __int64 a3,
        _QWORD *a4,
        __int64 a5,
        int a6,
        __int64 *a7,
        __int64 *a8,
        __int64 *a9,
        __int64 a10)
{
  __int128 *v14; // rax
  _QWORD *v15; // rdi
  __int64 v16; // rcx
  __int128 *v17; // rax
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int128 *v20; // rax
  __int64 v21; // rcx
  __int64 v22; // rcx
  volatile signed __int32 *v23; // rdi
  __int128 *v25; // rax
  __int64 v26; // r14
  __int128 *v27; // rax
  __int64 v28; // rdx
  __int64 v29; // rdx
  __int128 *v30; // rdi
  volatile signed __int32 *v31; // rdi
  char v32; // di^1
  _BYTE *v33; // rsi
  __int128 *v34; // rax
  __int64 *v35; // rsi
  __int128 *v36; // rax
  __int64 *v37; // rsi
  __int128 *v38; // rax
  __int64 *v39; // rsi
  __int128 *v40; // rax
  __int128 *v41; // rax
  __int128 *v42; // rax
  __int64 v43; // r8
  __int64 v44; // r9
  __int128 *v45; // rax
  _BYTE *v46; // rsi
  __int128 *v47; // rax
  __int128 *v48; // rax
  __int128 *v49; // rax
  int v50; // ecx
  __int128 *v51; // rax
  _DWORD *v52; // rsi
  __int128 *v53; // rax
  __int64 v54; // rdi
  __int128 *v55; // rax
  __int128 *v56; // rax
  int v57; // ecx
  __int128 *v58; // rax
  __int128 *v59; // rax
  __int128 *v60; // rax
  __int128 *v61; // rax
  __int64 v62; // rdi
  __int64 v63; // rbx
  __int64 v64; // rax
  __int64 v65; // rax
  __int64 v66; // rdx
  __int64 v67; // rdx
  __int64 v68; // rdx
  __int64 v69; // rdi
  __int64 v70; // rbx
  __int64 v71; // rax
  __int64 v72; // rax
  __int64 v73; // rdx
  __int64 v74; // rdx
  __int64 v75; // rdx
  __int64 v76; // rsi
  __int64 v77; // rdi
  __int64 v78; // rbx
  __int64 v79; // rax
  __int64 v80; // rax
  __int64 v81; // rdx
  __int64 v82; // rdx
  __int64 v83; // rdx
  _BYTE *v84; // rax
  int v85; // r14d
  int v86; // r15d
  __int64 v87; // rsi
  __int64 v88; // rdi
  __int64 v89; // rbx
  __int64 v90; // rax
  __int64 v91; // rax
  __int64 v92; // rdx
  __int64 v93; // rdx
  __int64 v94; // rdx
  __int64 v95; // rsi
  __int64 v96; // rdi
  __int64 v97; // rbx
  __int64 v98; // rax
  __int64 v99; // rax
  __int64 v100; // rdx
  __int64 v101; // rdx
  __int64 v102; // rdx
  _BYTE *v103; // rax
  int v104; // r15d
  __int64 v105; // rsi
  __int64 v106; // rdi
  __int64 v107; // rbx
  __int64 v108; // rax
  __int64 v109; // rax
  __int64 v110; // rdx
  __int64 v111; // rdx
  __int64 v112; // rdx
  __int64 v113; // rsi
  __int64 v114; // rdi
  __int64 v115; // rbx
  __int64 v116; // rax
  __int64 v117; // rax
  __int64 v118; // rdx
  __int64 v119; // rdx
  __int64 v120; // rdx
  _BYTE *v121; // rax
  int v122; // r12d
  __int64 v123; // rsi
  __int64 v124; // rdi
  __int64 v125; // rbx
  __int64 v126; // rax
  __int64 v127; // rax
  __int64 v128; // rdx
  __int64 v129; // rdx
  __int64 v130; // rdx
  __int64 v131; // rsi
  __int64 v132; // rdi
  __int64 v133; // rbx
  __int64 v134; // rax
  __int64 v135; // rax
  __int64 v136; // rdx
  __int64 v137; // rdx
  __int64 v138; // rdx
  _BYTE *v139; // rax
  int v140; // r12d
  __int64 v141; // rsi
  __int64 v142; // rdi
  __int64 v143; // rbx
  __int64 v144; // rax
  __int64 v145; // rax
  __int64 v146; // rdx
  __int64 v147; // rdx
  __int64 v148; // rdx
  __int64 v149; // rsi
  __int64 v150; // rdi
  __int64 v151; // rbx
  __int64 v152; // rax
  __int64 v153; // rax
  __int64 v154; // rdx
  __int64 v155; // rdx
  __int64 v156; // rdx
  _BYTE *v157; // rax
  __int64 v158; // rsi
  __int64 v159; // rdi
  __int64 v160; // rbx
  __int64 v161; // rax
  __int64 v162; // rax
  __int64 v163; // rdx
  __int64 v164; // rdx
  __int64 v165; // rdx
  __int64 v166; // rsi
  __int64 v167; // rdi
  __int64 v168; // rbx
  __int64 v169; // rax
  __int64 v170; // rax
  __int64 v171; // rdx
  __int64 v172; // rdx
  __int64 v173; // rdx
  _BYTE *v174; // rax
  int v175; // r14d
  __int64 v176; // rsi
  __int64 v177; // rdi
  __int64 v178; // rbx
  __int64 v179; // rax
  __int64 v180; // rax
  __int64 v181; // rdx
  __int64 v182; // rdx
  __int64 v183; // rdx
  volatile signed __int32 *v184; // rdi
  _BYTE *v185; // rsi
  __int64 ContainmentSwitches; // rdx
  __int64 v187; // rcx
  volatile signed __int32 *v188; // rdi
  __int64 v189; // rcx
  __int64 v190; // rcx
  char v191; // [rsp+70h] [rbp-1128h]
  __int128 v192; // [rsp+80h] [rbp-1118h] BYREF
  __int128 v193; // [rsp+90h] [rbp-1108h]
  char v194; // [rsp+A0h] [rbp-10F8h]
  __int128 *v195; // [rsp+A8h] [rbp-10F0h]
  __int64 *v196; // [rsp+B0h] [rbp-10E8h] BYREF
  __int64 *v197; // [rsp+B8h] [rbp-10E0h] BYREF
  _BYTE *v198; // [rsp+C0h] [rbp-10D8h]
  __int64 *v199; // [rsp+C8h] [rbp-10D0h] BYREF
  __int64 v200; // [rsp+D0h] [rbp-10C8h]
  __int128 v201; // [rsp+D8h] [rbp-10C0h] BYREF
  _QWORD *v202; // [rsp+E8h] [rbp-10B0h]
  void *v203; // [rsp+F0h] [rbp-10A8h]
  __int64 *v204; // [rsp+F8h] [rbp-10A0h]
  __int64 *v205; // [rsp+100h] [rbp-1098h]
  __int128 v206; // [rsp+108h] [rbp-1090h] BYREF
  __int128 v207; // [rsp+118h] [rbp-1080h]
  _OWORD v208[2]; // [rsp+128h] [rbp-1070h] BYREF
  __int64 v209[2]; // [rsp+148h] [rbp-1050h] BYREF
  __int128 v210; // [rsp+158h] [rbp-1040h]
  __int64 v211[2]; // [rsp+168h] [rbp-1030h] BYREF
  __int128 v212; // [rsp+178h] [rbp-1020h]
  __int64 v213[2]; // [rsp+188h] [rbp-1010h] BYREF
  __int128 v214; // [rsp+198h] [rbp-1000h]
  __int64 v215[2]; // [rsp+1A8h] [rbp-FF0h] BYREF
  __int128 v216; // [rsp+1B8h] [rbp-FE0h]
  __int64 *v217; // [rsp+1C8h] [rbp-FD0h]
  __int64 *v218; // [rsp+1D0h] [rbp-FC8h]
  __int64 v219[2]; // [rsp+1D8h] [rbp-FC0h] BYREF
  __int128 v220; // [rsp+1E8h] [rbp-FB0h]
  __int64 v221[2]; // [rsp+1F8h] [rbp-FA0h] BYREF
  __int128 v222; // [rsp+208h] [rbp-F90h]
  _BYTE v223[32]; // [rsp+218h] [rbp-F80h] BYREF
  _BYTE v224[32]; // [rsp+238h] [rbp-F60h] BYREF
  _BYTE v225[32]; // [rsp+258h] [rbp-F40h] BYREF
  _BYTE v226[32]; // [rsp+278h] [rbp-F20h] BYREF
  _BYTE v227[32]; // [rsp+298h] [rbp-F00h] BYREF
  _BYTE v228[32]; // [rsp+2B8h] [rbp-EE0h] BYREF
  __int64 v229[4]; // [rsp+2D8h] [rbp-EC0h] BYREF
  __int64 v230[4]; // [rsp+2F8h] [rbp-EA0h] BYREF
  _BYTE v231[32]; // [rsp+318h] [rbp-E80h] BYREF
  _BYTE v232[32]; // [rsp+338h] [rbp-E60h] BYREF
  _BYTE v233[32]; // [rsp+358h] [rbp-E40h] BYREF
  _BYTE v234[32]; // [rsp+378h] [rbp-E20h] BYREF
  _BYTE v235[32]; // [rsp+398h] [rbp-E00h] BYREF
  _BYTE v236[32]; // [rsp+3B8h] [rbp-DE0h] BYREF
  _BYTE v237[32]; // [rsp+3D8h] [rbp-DC0h] BYREF
  _BYTE v238[32]; // [rsp+3F8h] [rbp-DA0h] BYREF
  _BYTE v239[32]; // [rsp+418h] [rbp-D80h] BYREF
  _BYTE v240[32]; // [rsp+438h] [rbp-D60h] BYREF
  _BYTE v241[32]; // [rsp+458h] [rbp-D40h] BYREF
  _BYTE v242[32]; // [rsp+478h] [rbp-D20h] BYREF
  _BYTE v243[32]; // [rsp+498h] [rbp-D00h] BYREF
  _BYTE v244[32]; // [rsp+4B8h] [rbp-CE0h] BYREF
  _BYTE v245[32]; // [rsp+4D8h] [rbp-CC0h] BYREF
  _BYTE v246[32]; // [rsp+4F8h] [rbp-CA0h] BYREF
  _BYTE v247[32]; // [rsp+518h] [rbp-C80h] BYREF
  _BYTE v248[32]; // [rsp+538h] [rbp-C60h] BYREF
  _BYTE v249[32]; // [rsp+558h] [rbp-C40h] BYREF
  _BYTE v250[32]; // [rsp+578h] [rbp-C20h] BYREF
  _BYTE v251[32]; // [rsp+598h] [rbp-C00h] BYREF
  _BYTE v252[32]; // [rsp+5B8h] [rbp-BE0h] BYREF
  _BYTE v253[32]; // [rsp+5D8h] [rbp-BC0h] BYREF
  _BYTE v254[32]; // [rsp+5F8h] [rbp-BA0h] BYREF
  _BYTE v255[32]; // [rsp+618h] [rbp-B80h] BYREF
  _BYTE v256[32]; // [rsp+638h] [rbp-B60h] BYREF
  _BYTE v257[32]; // [rsp+658h] [rbp-B40h] BYREF
  _BYTE v258[32]; // [rsp+678h] [rbp-B20h] BYREF
  _BYTE v259[32]; // [rsp+698h] [rbp-B00h] BYREF
  _BYTE v260[32]; // [rsp+6B8h] [rbp-AE0h] BYREF
  _BYTE v261[32]; // [rsp+6D8h] [rbp-AC0h] BYREF
  _BYTE v262[32]; // [rsp+6F8h] [rbp-AA0h] BYREF
  _BYTE v263[32]; // [rsp+718h] [rbp-A80h] BYREF
  _BYTE v264[32]; // [rsp+738h] [rbp-A60h] BYREF
  _BYTE v265[32]; // [rsp+758h] [rbp-A40h] BYREF
  _BYTE v266[32]; // [rsp+778h] [rbp-A20h] BYREF
  _BYTE v267[32]; // [rsp+798h] [rbp-A00h] BYREF
  _BYTE v268[32]; // [rsp+7B8h] [rbp-9E0h] BYREF
  _BYTE v269[32]; // [rsp+7D8h] [rbp-9C0h] BYREF
  _BYTE v270[32]; // [rsp+7F8h] [rbp-9A0h] BYREF
  _BYTE v271[32]; // [rsp+818h] [rbp-980h] BYREF
  _BYTE v272[32]; // [rsp+838h] [rbp-960h] BYREF
  _BYTE v273[32]; // [rsp+858h] [rbp-940h] BYREF
  _BYTE v274[32]; // [rsp+878h] [rbp-920h] BYREF
  _BYTE v275[32]; // [rsp+898h] [rbp-900h] BYREF
  _BYTE v276[32]; // [rsp+8B8h] [rbp-8E0h] BYREF
  _BYTE v277[32]; // [rsp+8D8h] [rbp-8C0h] BYREF
  _BYTE v278[32]; // [rsp+8F8h] [rbp-8A0h] BYREF
  _BYTE v279[32]; // [rsp+918h] [rbp-880h] BYREF
  _BYTE v280[32]; // [rsp+938h] [rbp-860h] BYREF
  _BYTE v281[32]; // [rsp+958h] [rbp-840h] BYREF
  _BYTE v282[32]; // [rsp+978h] [rbp-820h] BYREF
  _BYTE v283[32]; // [rsp+998h] [rbp-800h] BYREF
  _BYTE v284[32]; // [rsp+9B8h] [rbp-7E0h] BYREF
  _BYTE v285[32]; // [rsp+9D8h] [rbp-7C0h] BYREF
  _BYTE v286[32]; // [rsp+9F8h] [rbp-7A0h] BYREF
  _BYTE v287[32]; // [rsp+A18h] [rbp-780h] BYREF
  _BYTE v288[32]; // [rsp+A38h] [rbp-760h] BYREF
  _BYTE v289[32]; // [rsp+A58h] [rbp-740h] BYREF
  _BYTE v290[32]; // [rsp+A78h] [rbp-720h] BYREF
  _BYTE v291[32]; // [rsp+A98h] [rbp-700h] BYREF
  _BYTE v292[32]; // [rsp+AB8h] [rbp-6E0h] BYREF
  _BYTE v293[32]; // [rsp+AD8h] [rbp-6C0h] BYREF
  _BYTE v294[32]; // [rsp+AF8h] [rbp-6A0h] BYREF
  _BYTE v295[32]; // [rsp+B18h] [rbp-680h] BYREF
  _BYTE v296[32]; // [rsp+B38h] [rbp-660h] BYREF
  _BYTE v297[32]; // [rsp+B58h] [rbp-640h] BYREF
  _BYTE v298[32]; // [rsp+B78h] [rbp-620h] BYREF
  _BYTE v299[32]; // [rsp+B98h] [rbp-600h] BYREF
  _BYTE v300[32]; // [rsp+BB8h] [rbp-5E0h] BYREF
  _BYTE v301[32]; // [rsp+BD8h] [rbp-5C0h] BYREF
  _BYTE v302[32]; // [rsp+BF8h] [rbp-5A0h] BYREF
  _BYTE v303[32]; // [rsp+C18h] [rbp-580h] BYREF
  _BYTE v304[32]; // [rsp+C38h] [rbp-560h] BYREF
  _BYTE v305[32]; // [rsp+C58h] [rbp-540h] BYREF
  _BYTE v306[32]; // [rsp+C78h] [rbp-520h] BYREF
  _BYTE v307[32]; // [rsp+C98h] [rbp-500h] BYREF
  _BYTE v308[32]; // [rsp+CB8h] [rbp-4E0h] BYREF
  _BYTE v309[32]; // [rsp+CD8h] [rbp-4C0h] BYREF
  _BYTE v310[32]; // [rsp+CF8h] [rbp-4A0h] BYREF
  _BYTE v311[32]; // [rsp+D18h] [rbp-480h] BYREF
  _BYTE v312[32]; // [rsp+D38h] [rbp-460h] BYREF
  _BYTE v313[32]; // [rsp+D58h] [rbp-440h] BYREF
  _BYTE v314[32]; // [rsp+D78h] [rbp-420h] BYREF
  _BYTE v315[32]; // [rsp+D98h] [rbp-400h] BYREF
  _BYTE v316[32]; // [rsp+DB8h] [rbp-3E0h] BYREF
  _BYTE v317[32]; // [rsp+DD8h] [rbp-3C0h] BYREF
  _BYTE v318[32]; // [rsp+DF8h] [rbp-3A0h] BYREF
  _BYTE v319[32]; // [rsp+E18h] [rbp-380h] BYREF
  _BYTE v320[32]; // [rsp+E38h] [rbp-360h] BYREF
  _BYTE v321[32]; // [rsp+E58h] [rbp-340h] BYREF
  _BYTE v322[32]; // [rsp+E78h] [rbp-320h] BYREF
  _BYTE v323[32]; // [rsp+E98h] [rbp-300h] BYREF
  _BYTE v324[32]; // [rsp+EB8h] [rbp-2E0h] BYREF
  _BYTE v325[32]; // [rsp+ED8h] [rbp-2C0h] BYREF
  _BYTE v326[32]; // [rsp+EF8h] [rbp-2A0h] BYREF
  _BYTE v327[32]; // [rsp+F18h] [rbp-280h] BYREF
  _BYTE v328[32]; // [rsp+F38h] [rbp-260h] BYREF
  _BYTE v329[32]; // [rsp+F58h] [rbp-240h] BYREF
  _BYTE v330[32]; // [rsp+F78h] [rbp-220h] BYREF
  _BYTE v331[32]; // [rsp+F98h] [rbp-200h] BYREF
  unsigned __int8 v332[32]; // [rsp+FB8h] [rbp-1E0h] BYREF
  unsigned __int8 v333[4]; // [rsp+FD8h] [rbp-1C0h] BYREF
  unsigned __int8 v334[4]; // [rsp+FDCh] [rbp-1BCh] BYREF
  _OWORD v335[2]; // [rsp+FE0h] [rbp-1B8h] BYREF
  unsigned int v336; // [rsp+1000h] [rbp-198h] BYREF
  unsigned int v337; // [rsp+1004h] [rbp-194h] BYREF
  int v338[4]; // [rsp+1008h] [rbp-190h] BYREF
  __int128 v339; // [rsp+1018h] [rbp-180h]
  _BYTE v340[16]; // [rsp+1028h] [rbp-170h] BYREF
  __int64 v341; // [rsp+1038h] [rbp-160h]
  _QWORD v342[32]; // [rsp+1050h] [rbp-148h] BYREF

  v202 = a4;
  v198 = (_BYTE *)a1;
  v204 = a9;
  v196 = a8;
  v203 = a4;
  v205 = a7;
  v200 = a10;
  v201 = 0;
  Microsoft::Basix::SharedFromThisVirtualBase::GetWeakPtr<Microsoft::Basix::Dct::ICEDelegate>(
    a1 + *(int *)(*(_QWORD *)(a1 + 112) + 4LL) + 112LL,
    &v201);
  v192 = 0;
  v193 = 0;
  std::string::_Construct<1,char const *>(&v192, "Microsoft::Basix::Dct.ICE.Delegate", 34);
  v194 = 46;
  v14 = &v192;
  if ( *((_QWORD *)&v193 + 1) > 0xFu )
    v14 = (__int128 *)v192;
  v195 = v14;
  boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::put<std::weak_ptr<Microsoft::Basix::Dct::ICEDelegate>>(
    a10,
    &v192,
    &v201);
  std::string::_Tidy_deallocate(&v192);
  if ( *a4 )
  {
    v15 = (_QWORD *)(a1 + 304);
    std::shared_ptr<Microsoft::RdpNano::RendezvousSource::RendezvousContext>::operator=(a1 + 304, a4);
    v335[0] = 0;
    v16 = *(_QWORD *)(a1 + 312);
    if ( v16 )
    {
      *(_QWORD *)&v335[0] = *v15;
      *((_QWORD *)&v335[0] + 1) = v16;
      _InterlockedAdd((volatile signed __int32 *)(v16 + 12), 1u);
    }
    v192 = 0;
    v193 = 0;
    std::string::_Construct<1,char const *>(&v192, "Microsoft::Basix::Dct.ICE.Port", 30);
    v194 = 46;
    v17 = &v192;
    if ( *((_QWORD *)&v193 + 1) > 0xFu )
      v17 = (__int128 *)v192;
    v195 = v17;
    boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::put<std::weak_ptr<Microsoft::Basix::Dct::IPortAllocator>>(
      a10,
      &v192,
      v335);
    std::string::_Tidy_deallocate(&v192);
    v18 = *((_QWORD *)&v335[0] + 1);
    if ( *((_QWORD *)&v335[0] + 1)
      && !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v335[0] + 1) + 12LL)) )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 8LL))(v18);
    }
    v335[0] = 0;
    v19 = *(_QWORD *)(a1 + 312);
    if ( v19 )
    {
      *(_QWORD *)&v335[0] = *v15;
      *((_QWORD *)&v335[0] + 1) = v19;
      _InterlockedAdd((volatile signed __int32 *)(v19 + 12), 1u);
    }
    v192 = 0;
    v193 = 0;
    std::string::_Construct<1,char const *>(&v192, "Microsoft::Basix::Dct.UPnP.Port", 31);
    v194 = 46;
    v20 = &v192;
    if ( *((_QWORD *)&v193 + 1) > 0xFu )
      v20 = (__int128 *)v192;
    v195 = v20;
    boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::put<std::weak_ptr<Microsoft::Basix::Dct::IPortAllocator>>(
      a10,
      &v192,
      v335);
    std::string::_Tidy_deallocate(&v192);
    v21 = *((_QWORD *)&v335[0] + 1);
    if ( *((_QWORD *)&v335[0] + 1)
      && _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v335[0] + 1) + 12LL), 0xFFFFFFFF) == 1 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 8LL))(v21);
    }
  }
  v198[320] = a2;
  if ( a6 )
  {
    switch ( a6 )
    {
      case 1:
        LODWORD(v197) = 1;
        v192 = 0;
        v193 = 0;
        std::string::_Construct<1,char const *>(&v192, "Microsoft::Basix::Dct.Ip.Family", 31);
        v194 = 46;
        v25 = &v192;
        if ( *((_QWORD *)&v193 + 1) > 0xFu )
          v25 = (__int128 *)v192;
        break;
      case 2:
        LODWORD(v197) = 2;
        v192 = 0;
        v193 = 0;
        std::string::_Construct<1,char const *>(&v192, "Microsoft::Basix::Dct.Ip.Family", 31);
        v194 = 46;
        v25 = &v192;
        if ( *((_QWORD *)&v193 + 1) > 0xFu )
          v25 = (__int128 *)v192;
        break;
      case 3:
        LODWORD(v197) = 3;
        v192 = 0;
        v193 = 0;
        std::string::_Construct<1,char const *>(&v192, "Microsoft::Basix::Dct.Ip.Family", 31);
        v194 = 46;
        v25 = &v192;
        if ( *((_QWORD *)&v193 + 1) > 0xFu )
          v25 = (__int128 *)v192;
        break;
      default:
        v22 = *((_QWORD *)&v201 + 1);
        if ( *((_QWORD *)&v201 + 1)
          && _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v201 + 1) + 12LL), 0xFFFFFFFF) == 1 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 8LL))(v22);
        }
        v23 = (volatile signed __int32 *)v202[1];
        if ( v23 && _InterlockedExchangeAdd(v23 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v23)(v23);
          if ( _InterlockedExchangeAdd(v23 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v23 + 8LL))(v23);
        }
        return 2147942487LL;
    }
  }
  else
  {
    LODWORD(v197) = 0;
    v192 = 0;
    v193 = 0;
    std::string::_Construct<1,char const *>(&v192, "Microsoft::Basix::Dct.Ip.Family", 31);
    v194 = 46;
    v25 = &v192;
    if ( *((_QWORD *)&v193 + 1) > 0xFu )
      v25 = (__int128 *)v192;
  }
  v195 = v25;
  v26 = v200;
  boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::put<int>(v200, &v192, &v197);
  std::string::_Tidy_deallocate(&v192);
  v192 = 0;
  v193 = 0;
  try
  {
    std::string::_Construct<1,char const *>(&v192, "Microsoft::Basix::Dct.ActivityId");
    v194 = 46;
    v27 = &v192;
    if ( *((_QWORD *)&v193 + 1) > 0xFu )
      v27 = (__int128 *)v192;
    v195 = v27;
    boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::put<Microsoft::Basix::Guid>(
      v26,
      &v192,
      a3);
    std::string::_Tidy_deallocate(&v192);
    memset(v342, 0, 0xF8u);
    std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(
      v342,
      1);
    LOBYTE(v28) = 123;
    std::operator<<<std::char_traits<char>>(&v342[2], v28);
    Microsoft::Basix::PrintGuidWithoutBrackets(&v342[2], a3);
    LOBYTE(v29) = 125;
    std::operator<<<std::char_traits<char>>(&v342[2], v29);
    v335[0] = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(v335);
    if ( *(_QWORD *)&v335[0] && *(_BYTE *)(*(_QWORD *)&v335[0] + 128LL) )
    {
      std::stringbuf::str(&v342[3], &v206);
      v30 = &v206;
      if ( *((_QWORD *)&v207 + 1) > 0xFu )
        v30 = (__int128 *)v206;
      *(_OWORD *)v338 = 0;
      v339 = 0;
      std::string::_Construct<1,char const *>(v338, "activityId=%s", (const char *)0xD);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,char const *>(
        v335,
        "RDPNANO",
        v338,
        v30);
      std::string::_Tidy_deallocate(v338);
      std::string::_Tidy_deallocate(&v206);
    }
    v31 = (volatile signed __int32 *)*((_QWORD *)&v335[0] + 1);
    if ( *((_QWORD *)&v335[0] + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v335[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v31)(v31);
        if ( _InterlockedExchangeAdd(v31 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v31 + 8LL))(v31);
      }
    }
    std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::~basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(&v342[19]);
    v342[19] = &std::ios_base::`vftable';
    std::ios_base::_Ios_base_dtor((struct std::ios_base *)&v342[19]);
    v32 = BYTE1(a5);
    v33 = v198;
    v198[321] = a5 & 1;
    v33[323] = (a5 & 0x10) != 0;
    v33[322] = (a5 & 0x20) != 0;
    v33[324] = (a5 & 2) != 0;
    v33[325] = (a5 & 0x40) != 0;
    if ( (a5 & 4) != 0 )
      LODWORD(v197) = 2;
    else
      LODWORD(v197) = (a5 & 8) != 0;
    v192 = 0;
    v193 = 0;
  }
  catch ( std::bad_alloc )
  {
    v189 = *((_QWORD *)&v201 + 1);
    if ( *((_QWORD *)&v201 + 1)
      && _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v201 + 1) + 12LL), 0xFFFFFFFF) == 1 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v189 + 8LL))(v189);
    }
    std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(v203);
    return 2147942414LL;
  }
  catch ( ... )
  {
    v190 = *((_QWORD *)&v201 + 1);
    if ( *((_QWORD *)&v201 + 1)
      && _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v201 + 1) + 12LL), 0xFFFFFFFF) == 1 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v190 + 8LL))(v190);
    }
    std::shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>::~shared_ptr<GlobalProviderList::Microsoft_Streaming_Nano_Network::Microsoft_Basix_Instrumentation_RioBuffersReceive_Logger>(v203);
    return 2147942974LL;
  }
  std::string::_Construct<1,char const *>(&v192, "Microsoft::Basix::Dct.ICE.PromotionMode");
  v194 = 46;
  v34 = &v192;
  if ( *((_QWORD *)&v193 + 1) > 0xFu )
    v34 = (__int128 *)v192;
  v195 = v34;
  boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::put<enum Microsoft::Basix::Dct::ICE::Agent::PairPromotionMode>(
    v26,
    &v192,
    &v197);
  std::string::_Tidy_deallocate(&v192);
  v33[326] = v32 & 1;
  v35 = v196;
  if ( (v196[1] - *v196) >> 5 )
  {
    v192 = 0;
    v193 = 0;
    std::string::_Construct<1,char const *>(&v192, "Microsoft::Basix::Dct.ICE.StunServer", 36);
    v194 = 46;
    v36 = &v192;
    if ( *((_QWORD *)&v193 + 1) > 0xFu )
      v36 = (__int128 *)v192;
    v195 = v36;
    boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::put<std::vector<std::string>>(
      v26,
      &v192,
      v35);
    std::string::_Tidy_deallocate(&v192);
  }
  v37 = v204;
  if ( (v204[1] - *v204) / 104 )
  {
    v192 = 0;
    v193 = 0;
    std::string::_Construct<1,char const *>(&v192, "Microsoft::Basix::Dct.ICE.TurnServer", 36);
    v194 = 46;
    v38 = &v192;
    if ( *((_QWORD *)&v193 + 1) > 0xFu )
      v38 = (__int128 *)v192;
    v195 = v38;
    boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::put<std::vector<Microsoft::Basix::Dct::ICE::Agent::TurnServer>>(
      v26,
      &v192,
      v37);
    std::string::_Tidy_deallocate(&v192);
  }
  v39 = v205;
  if ( v205 )
  {
    v192 = 0;
    v193 = 0;
    std::string::_Construct<1,char const *>(&v192, "Microsoft::Basix::Dct.ICE.InitialRTO", 36);
    v194 = 46;
    v40 = &v192;
    if ( *((_QWORD *)&v193 + 1) > 0xFu )
      v40 = (__int128 *)v192;
    v195 = v40;
    boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::put<unsigned int>(
      v26,
      &v192,
      (char *)v39 + 4);
    std::string::_Tidy_deallocate(&v192);
    v192 = 0;
    v193 = 0;
    std::string::_Construct<1,char const *>(&v192, "Microsoft::Basix::Dct.ICE.MaxRetries", 36);
    v194 = 46;
    v41 = &v192;
    if ( *((_QWORD *)&v193 + 1) > 0xFu )
      v41 = (__int128 *)v192;
    v195 = v41;
    boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::put<unsigned int>(
      v26,
      &v192,
      v39 + 1);
    std::string::_Tidy_deallocate(&v192);
    v192 = 0;
    v193 = 0;
    std::string::_Construct<1,char const *>(&v192, "Microsoft::Basix::Dct.ICE.SessionDescription.PacingMs", 53);
    v194 = 46;
    v42 = &v192;
    if ( *((_QWORD *)&v193 + 1) > 0xFu )
      v42 = (__int128 *)v192;
    v195 = v42;
    boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::put<unsigned int>(v26, &v192, v39);
    std::string::_Tidy_deallocate(&v192);
  }
  memset(v208, 0, sizeof(v208));
  std::string::_Construct<1,char const *>(v208, "SYSTEM\\CurrentControlSet\\Control\\Terminal Server\\WinStations", 60);
  v206 = 0;
  v207 = 0;
  std::string::_Construct<1,char const *>(&v206, "IceTransportType", 16);
  Microsoft::Basix::WinUtils::ReadRegistryString(v340, &v206, v208);
  std::string::_Tidy_deallocate(&v206);
  std::string::_Tidy_deallocate(v208);
  if ( v341 )
  {
    v192 = 0;
    v193 = 0;
    std::string::_Construct<1,char const *>(&v192, "Microsoft::Basix::Dct.ICE.UDP.Component.Type", 44);
    v194 = 46;
    v45 = &v192;
    if ( *((_QWORD *)&v193 + 1) > 0xFu )
      v45 = (__int128 *)v192;
    v195 = v45;
    boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::put<std::string>(v26, &v192, v340);
    std::string::_Tidy_deallocate(&v192);
    v46 = v198;
  }
  else
  {
    v46 = v198;
    if ( v198[325] )
    {
      LOBYTE(v44) = v191;
      LOBYTE(v43) = 46;
      boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>>::string_path<std::string,boost::property_tree::id_translator<std::string>>(
        &v192,
        "Microsoft::Basix::Dct.ICE.UDP.Component.Type",
        v43,
        v44);
      boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::put<char [4]>(v26, &v192, "rio");
      std::string::_Tidy_deallocate(&v192);
    }
  }
  *(_DWORD *)v333 = 0;
  v336 = 4;
  *(_DWORD *)v334 = 0;
  v337 = 4;
  if ( ReadRegistryValueA(
         "TEST_RELAYCLONE_MODE",
         v333,
         &v336,
         "SOFTWARE\\Policies\\Microsoft\\Windows NT\\Terminal Services") )
  {
    LODWORD(v196) = *(_DWORD *)v333 + 2;
    v192 = 0;
    v193 = 0;
    std::string::_Construct<1,char const *>(&v192, "Microsoft::Basix::Dct.ICE.RelayCloneMode", 40);
    v194 = 46;
    v47 = &v192;
    if ( *((_QWORD *)&v193 + 1) > 0xFu )
      v47 = (__int128 *)v192;
    v195 = v47;
    boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::put<unsigned long>(
      v26,
      &v192,
      &v196);
    std::string::_Tidy_deallocate(&v192);
    LODWORD(v196) = v46[320] != 0 ? 0xA : 0;
    v192 = 0;
    v193 = 0;
    std::string::_Construct<1,char const *>(&v192, "Microsoft::Basix::Dct.ICE.RelayClone.TestStartingOffset", 55);
    v194 = 46;
    v48 = &v192;
    if ( *((_QWORD *)&v193 + 1) > 0xFu )
      v48 = (__int128 *)v192;
    v195 = v48;
    boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::put<int>(v26, &v192, &v196);
    std::string::_Tidy_deallocate(&v192);
    LODWORD(v196) = 20;
    v192 = 0;
    v193 = 0;
    std::string::_Construct<1,char const *>(&v192, "Microsoft::Basix::Dct.ICE.RelayClone.TestInterval", 49);
    v194 = 46;
    v49 = &v192;
    if ( *((_QWORD *)&v193 + 1) > 0xFu )
      v49 = (__int128 *)v192;
    v195 = v49;
    boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::put<int>(v26, &v192, &v196);
    std::string::_Tidy_deallocate(&v192);
    v50 = 2;
    if ( (unsigned int)(*(_DWORD *)v333 - 3) <= 1 )
      v50 = 3;
    LODWORD(v196) = v50;
    v192 = 0;
    v193 = 0;
    std::string::_Construct<1,char const *>(&v192, "Microsoft::Basix::Dct.ICE.RelayClone.Count", 42);
    v194 = 46;
    v51 = &v192;
    if ( *((_QWORD *)&v193 + 1) > 0xFu )
      v51 = (__int128 *)v192;
    v195 = v51;
    boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::put<unsigned int>(
      v200,
      &v192,
      &v196);
    std::string::_Tidy_deallocate(&v192);
    if ( (_DWORD)v196 )
      goto LABEL_93;
  }
  if ( !ReadRegistryValueA(
          "ICE_TARGET_DOR",
          v334,
          &v337,
          "SOFTWARE\\Policies\\Microsoft\\Windows NT\\Terminal Services") )
  {
LABEL_93:
    v52 = v46 + 328;
    v192 = 0;
    v193 = 0;
    if ( !v198[326] )
    {
      *(_DWORD *)v333 = 0;
      *v52 = 0;
      LODWORD(v199) = 0;
      std::string::_Construct<1,char const *>(&v192, "Microsoft::Basix::Dct.ICE.RelayCloneMode", 40);
      v194 = 46;
      v60 = &v192;
      if ( *((_QWORD *)&v193 + 1) > 0xFu )
        v60 = (__int128 *)v192;
      v195 = v60;
      boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::put<int>(v200, &v192, &v199);
      std::string::_Tidy_deallocate(&v192);
      LODWORD(v199) = 0;
      v192 = 0;
      v193 = 0;
      std::string::_Construct<1,char const *>(&v192, "Microsoft::Basix::Dct.ICE.RelayClone.Count", 42);
      v194 = 46;
      v61 = &v192;
      if ( *((_QWORD *)&v193 + 1) > 0xFu )
        v61 = (__int128 *)v192;
      v195 = v61;
      boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::put<int>(v200, &v192, &v199);
      goto LABEL_114;
    }
    *v52 = 4;
    LODWORD(v199) = 1;
    std::string::_Construct<1,char const *>(&v192, "Microsoft::Basix::Dct.ICE.RelayCloneMode", 40);
    v194 = 46;
    v53 = &v192;
    if ( *((_QWORD *)&v193 + 1) > 0xFu )
      v53 = (__int128 *)v192;
    v195 = v53;
    v54 = v200;
    boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::put<int>(v200, &v192, &v199);
    std::string::_Tidy_deallocate(&v192);
    v192 = 0;
    v193 = 0;
    std::string::_Construct<1,char const *>(&v192, "Microsoft::Basix::Dct.ICE.RelayClone.Count", 42);
    v194 = 46;
    v55 = &v192;
    if ( *((_QWORD *)&v193 + 1) > 0xFu )
      v55 = (__int128 *)v192;
    v195 = v55;
    boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::put<unsigned int>(v54, &v192, v52);
    std::string::_Tidy_deallocate(&v192);
    v192 = 0;
    v193 = 0;
    std::string::_Construct<1,char const *>(&v192, "Microsoft::Basix::Dct.ICE.RelayClone.MaxCountGap", 48);
    v194 = 46;
    v56 = &v192;
    if ( *((_QWORD *)&v193 + 1) > 0xFu )
      v56 = (__int128 *)v192;
  }
  else
  {
    v57 = *(_DWORD *)v334;
    LODWORD(v196) = *(_DWORD *)v334;
    v52 = v46 + 328;
    *v52 = *(_DWORD *)v334;
    LODWORD(v199) = v57 != 0;
    v192 = 0;
    v193 = 0;
    std::string::_Construct<1,char const *>(&v192, "Microsoft::Basix::Dct.ICE.RelayCloneMode", 40);
    v194 = 46;
    v58 = &v192;
    if ( *((_QWORD *)&v193 + 1) > 0xFu )
      v58 = (__int128 *)v192;
    v195 = v58;
    v54 = v200;
    boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::put<int>(v200, &v192, &v199);
    std::string::_Tidy_deallocate(&v192);
    v192 = 0;
    v193 = 0;
    std::string::_Construct<1,char const *>(&v192, "Microsoft::Basix::Dct.ICE.RelayClone.Count", 42);
    v194 = 46;
    v59 = &v192;
    if ( *((_QWORD *)&v193 + 1) > 0xFu )
      v59 = (__int128 *)v192;
    v195 = v59;
    boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::put<unsigned int>(
      v54,
      &v192,
      &v196);
    std::string::_Tidy_deallocate(&v192);
    v192 = 0;
    v193 = 0;
    std::string::_Construct<1,char const *>(&v192, "Microsoft::Basix::Dct.ICE.RelayClone.MaxCountGap", 48);
    v194 = 46;
    v56 = &v192;
    if ( *((_QWORD *)&v193 + 1) > 0xFu )
      v56 = (__int128 *)v192;
  }
  v195 = v56;
  boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::put<unsigned int>(
    v54,
    &v192,
    &Microsoft::RdpNano::ICESourceAdapter::DefaultTargetDoRGap);
LABEL_114:
  std::string::_Tidy_deallocate(&v192);
  *(_OWORD *)v338 = 0;
  Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceCheckpoint>(v338);
  if ( *(_QWORD *)v338 && *(_BYTE *)(*(_QWORD *)v338 + 128LL) )
  {
    v205 = v229;
    std::_Integral_to_string<char,int>(v228, (unsigned int)v197);
    v62 = std::string::string(&v192, ":");
    v63 = std::string::string(v284, "\"");
    v64 = std::string::string(v271, "\"");
    v65 = std::operator+<char>(v270, v64, "promotionMode");
    LOBYTE(v66) = v191;
    std::string::string(v227, v66, v65, v63);
    LOBYTE(v67) = v191;
    std::string::string(v226, v67, v227, v62);
    LOBYTE(v68) = v191;
    std::string::string(v229, v68, v226, v228);
    v204 = v230;
    std::_Integral_to_string<char,unsigned int>(v225, (unsigned int)*v52);
    v69 = std::string::string(v269, ":");
    v70 = std::string::string(v268, "\"");
    v71 = std::string::string(v267, "\"");
    v72 = std::operator+<char>(v332, v71, "CloneTargetDoR");
    LOBYTE(v73) = v191;
    std::string::string(v224, v73, v72, v70);
    LOBYTE(v74) = v191;
    std::string::string(v223, v74, v224, v69);
    LOBYTE(v75) = v191;
    std::string::string(v230, v75, v223, v225);
    v199 = v221;
    if ( v198[326] )
    {
      v76 = std::string::string(v331, "true");
      v77 = std::string::string(v330, ":");
      v78 = std::string::string(v329, "\"");
      v79 = std::string::string(v328, "\"");
      v80 = std::operator+<char>(v327, v79, "enableCloning");
      LOBYTE(v81) = v191;
      std::string::string(v265, v81, v80, v78);
      LOBYTE(v82) = v191;
      std::string::string(v264, v82, v265, v77);
      LOBYTE(v83) = v191;
      std::string::string(v263, v83, v264, v76);
      v84 = v263;
      v85 = 255;
      v86 = 255;
    }
    else
    {
      v87 = std::string::string(v326, "false");
      v88 = std::string::string(v325, ":");
      v89 = std::string::string(v324, "\"");
      v90 = std::string::string(v323, "\"");
      v91 = std::operator+<char>(v322, v90, "enableCloning");
      LOBYTE(v92) = v191;
      std::string::string(v262, v92, v91, v89);
      LOBYTE(v93) = v191;
      std::string::string(v261, v93, v262, v88);
      LOBYTE(v94) = v191;
      std::string::string(v260, v94, v261, v87);
      v84 = v260;
      v86 = 65280;
      v85 = 255;
    }
    *(_OWORD *)v221 = *(_OWORD *)v84;
    v222 = *((_OWORD *)v84 + 1);
    *((_QWORD *)v84 + 2) = 0;
    *((_QWORD *)v84 + 3) = 15;
    *v84 = 0;
    v197 = v209;
    if ( v198[325] )
    {
      v95 = std::string::string(v321, "true");
      v96 = std::string::string(v320, ":");
      v97 = std::string::string(v319, "\"");
      v98 = std::string::string(v318, "\"");
      v99 = std::operator+<char>(v317, v98, "enableRIOTransport");
      LOBYTE(v100) = v191;
      std::string::string(v259, v100, v99, v97);
      LOBYTE(v101) = v191;
      std::string::string(v258, v101, v259, v96);
      LOBYTE(v102) = v191;
      std::string::string(v257, v102, v258, v95);
      v103 = v257;
      v104 = v86 | 0xFF0000;
    }
    else
    {
      v105 = std::string::string(v316, "false");
      v106 = std::string::string(v315, ":");
      v107 = std::string::string(v314, "\"");
      v108 = std::string::string(v313, "\"");
      v109 = std::operator+<char>(v312, v108, "enableRIOTransport");
      LOBYTE(v110) = v191;
      std::string::string(v256, v110, v109, v107);
      LOBYTE(v111) = v191;
      std::string::string(v255, v111, v256, v106);
      LOBYTE(v112) = v191;
      std::string::string(v254, v112, v255, v105);
      v103 = v254;
      v104 = v86 | 0xFF000000;
    }
    *(_OWORD *)v209 = *(_OWORD *)v103;
    v210 = *((_OWORD *)v103 + 1);
    *((_QWORD *)v103 + 2) = 0;
    *((_QWORD *)v103 + 3) = 15;
    *v103 = 0;
    v196 = v211;
    if ( v198[324] )
    {
      v113 = std::string::string(v311, "true");
      v114 = std::string::string(v310, ":");
      v115 = std::string::string(v309, "\"");
      v116 = std::string::string(v308, "\"");
      v117 = std::operator+<char>(v307, v116, "useUPnP");
      LOBYTE(v118) = v191;
      std::string::string(v253, v118, v117, v115);
      LOBYTE(v119) = v191;
      std::string::string(v252, v119, v253, v114);
      LOBYTE(v120) = v191;
      std::string::string(v251, v120, v252, v113);
      v121 = v251;
      v122 = 255;
    }
    else
    {
      v123 = std::string::string(v306, "false");
      v124 = std::string::string(v305, ":");
      v125 = std::string::string(v304, "\"");
      v126 = std::string::string(v303, "\"");
      v127 = std::operator+<char>(v302, v126, "useUPnP");
      LOBYTE(v128) = v191;
      std::string::string(v250, v128, v127, v125);
      LOBYTE(v129) = v191;
      std::string::string(v249, v129, v250, v124);
      LOBYTE(v130) = v191;
      std::string::string(v248, v130, v249, v123);
      v121 = v248;
      v122 = 65280;
    }
    *(_OWORD *)v211 = *(_OWORD *)v121;
    v212 = *((_OWORD *)v121 + 1);
    *((_QWORD *)v121 + 2) = 0;
    *((_QWORD *)v121 + 3) = 15;
    *v121 = 0;
    v217 = v213;
    if ( v198[322] )
    {
      v131 = std::string::string(v301, "true");
      v132 = std::string::string(v300, ":");
      v133 = std::string::string(v299, "\"");
      v134 = std::string::string(v298, "\"");
      v135 = std::operator+<char>(v297, v134, "disableLocalCandidateUsage");
      LOBYTE(v136) = v191;
      std::string::string(v247, v136, v135, v133);
      LOBYTE(v137) = v191;
      std::string::string(v246, v137, v247, v132);
      LOBYTE(v138) = v191;
      std::string::string(v245, v138, v246, v131);
      v139 = v245;
      v140 = v122 | 0xFF0000;
    }
    else
    {
      v141 = std::string::string(v296, "false");
      v142 = std::string::string(v295, ":");
      v143 = std::string::string(v294, "\"");
      v144 = std::string::string(v293, "\"");
      v145 = std::operator+<char>(v292, v144, "disableLocalCandidateUsage");
      LOBYTE(v146) = v191;
      std::string::string(v244, v146, v145, v143);
      LOBYTE(v147) = v191;
      std::string::string(v243, v147, v244, v142);
      LOBYTE(v148) = v191;
      std::string::string(v242, v148, v243, v141);
      v139 = v242;
      v140 = v122 | 0xFF000000;
    }
    *(_OWORD *)v213 = *(_OWORD *)v139;
    v214 = *((_OWORD *)v139 + 1);
    *((_QWORD *)v139 + 2) = 0;
    *((_QWORD *)v139 + 3) = 15;
    *v139 = 0;
    v218 = v215;
    if ( v198[323] )
    {
      v149 = std::string::string(v291, "true");
      v150 = std::string::string(v290, ":");
      v151 = std::string::string(v289, "\"");
      v152 = std::string::string(v288, "\"");
      v153 = std::operator+<char>(v287, v152, "disableTurnUsage");
      LOBYTE(v154) = v191;
      std::string::string(v241, v154, v153, v151);
      LOBYTE(v155) = v191;
      std::string::string(v240, v155, v241, v150);
      LOBYTE(v156) = v191;
      std::string::string(v239, v156, v240, v149);
      v157 = v239;
    }
    else
    {
      v158 = std::string::string(v286, "false");
      v159 = std::string::string(v285, ":");
      v160 = std::string::string(v275, "\"");
      v161 = std::string::string(v283, "\"");
      v162 = std::operator+<char>(v282, v161, "disableTurnUsage");
      LOBYTE(v163) = v191;
      std::string::string(v238, v163, v162, v160);
      LOBYTE(v164) = v191;
      std::string::string(v237, v164, v238, v159);
      LOBYTE(v165) = v191;
      std::string::string(v236, v165, v237, v158);
      v157 = v236;
      v85 = 65280;
    }
    *(_OWORD *)v215 = *(_OWORD *)v157;
    v216 = *((_OWORD *)v157 + 1);
    *((_QWORD *)v157 + 2) = 0;
    *((_QWORD *)v157 + 3) = 15;
    *v157 = 0;
    if ( v198[321] )
    {
      v166 = std::string::string(v281, "true");
      v167 = std::string::string(v280, ":");
      v168 = std::string::string(v279, "\"");
      v169 = std::string::string(v278, "\"");
      v170 = std::operator+<char>(v277, v169, "disableStunUsage");
      LOBYTE(v171) = v191;
      std::string::string(v235, v171, v170, v168);
      LOBYTE(v172) = v191;
      std::string::string(v234, v172, v235, v167);
      LOBYTE(v173) = v191;
      std::string::string(v233, v173, v234, v166);
      v174 = v233;
      v175 = v85 | 0xFF0000;
    }
    else
    {
      v176 = std::string::string(v276, "false");
      v177 = std::string::string(v266, ":");
      v178 = std::string::string(v274, "\"");
      v179 = std::string::string(v273, "\"");
      v180 = std::operator+<char>(v272, v179, "disableStunUsage");
      LOBYTE(v181) = v191;
      std::string::string(v232, v181, v180, v178);
      LOBYTE(v182) = v191;
      std::string::string(v231, v182, v232, v177);
      LOBYTE(v183) = v191;
      std::string::string(v335, v183, v231, v176);
      v174 = v335;
      v175 = v85 | 0xFF000000;
    }
    *(_OWORD *)v219 = *(_OWORD *)v174;
    v220 = *((_OWORD *)v174 + 1);
    *((_QWORD *)v174 + 2) = 0;
    *((_QWORD *)v174 + 3) = 15;
    *v174 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::TraceCheckpointMessage<Microsoft::Basix::TraceCheckpoint,std::string,std::string,std::string,std::string,std::string,std::string,std::string,std::string>(
      (int)v338,
      (int)"RD_CHECKPOINT",
      0,
      (int)"NanoConfigurations",
      "ICE",
      "ICE Configurations",
      (__int64)v219,
      (__int64)v215,
      (__int64)v213,
      (__int64)v211,
      (__int64)v209,
      (__int64)v221,
      (__int64)v230,
      (__int64)v229);
    if ( v175 < 0 )
    {
      v175 &= ~0x80000000;
      std::string::_Tidy_deallocate(v335);
    }
    if ( (v175 & 0x40000000) != 0 )
    {
      v175 &= ~0x40000000u;
      std::string::_Tidy_deallocate(v231);
    }
    if ( (v175 & 0x20000000) != 0 )
    {
      v175 &= ~0x20000000u;
      std::string::_Tidy_deallocate(v232);
    }
    if ( (v175 & 0x10000000) != 0 )
    {
      v175 &= ~0x10000000u;
      std::string::_Tidy_deallocate(v272);
    }
    if ( (v175 & 0x8000000) != 0 )
    {
      v175 &= ~0x8000000u;
      std::string::_Tidy_deallocate(v273);
    }
    if ( (v175 & 0x4000000) != 0 )
    {
      v175 &= ~0x4000000u;
      std::string::_Tidy_deallocate(v274);
    }
    if ( (v175 & 0x2000000) != 0 )
    {
      v175 &= ~0x2000000u;
      std::string::_Tidy_deallocate(v266);
    }
    if ( (v175 & 0x1000000) != 0 )
    {
      v175 &= ~0x1000000u;
      std::string::_Tidy_deallocate(v276);
    }
    if ( (v175 & 0x800000) != 0 )
    {
      v175 &= ~0x800000u;
      std::string::_Tidy_deallocate(v233);
    }
    if ( (v175 & 0x400000) != 0 )
    {
      v175 &= ~0x400000u;
      std::string::_Tidy_deallocate(v234);
    }
    if ( (v175 & 0x200000) != 0 )
    {
      v175 &= ~0x200000u;
      std::string::_Tidy_deallocate(v235);
    }
    if ( (v175 & 0x100000) != 0 )
    {
      v175 &= ~0x100000u;
      std::string::_Tidy_deallocate(v277);
    }
    if ( (v175 & 0x80000) != 0 )
    {
      v175 &= ~0x80000u;
      std::string::_Tidy_deallocate(v278);
    }
    if ( (v175 & 0x40000) != 0 )
    {
      v175 &= ~0x40000u;
      std::string::_Tidy_deallocate(v279);
    }
    if ( (v175 & 0x20000) != 0 )
    {
      v175 &= ~0x20000u;
      std::string::_Tidy_deallocate(v280);
    }
    if ( (v175 & 0x10000) != 0 )
      std::string::_Tidy_deallocate(v281);
    if ( (v175 & 0x8000) != 0 )
    {
      LOWORD(v175) = v175 & 0x7FFF;
      std::string::_Tidy_deallocate(v236);
    }
    if ( (v175 & 0x4000) != 0 )
    {
      LOWORD(v175) = v175 & 0xBFFF;
      std::string::_Tidy_deallocate(v237);
    }
    if ( (v175 & 0x2000) != 0 )
    {
      LOWORD(v175) = v175 & 0xDFFF;
      std::string::_Tidy_deallocate(v238);
    }
    if ( (v175 & 0x1000) != 0 )
    {
      LOWORD(v175) = v175 & 0xEFFF;
      std::string::_Tidy_deallocate(v282);
    }
    if ( (v175 & 0x800) != 0 )
    {
      LOWORD(v175) = v175 & 0xF7FF;
      std::string::_Tidy_deallocate(v283);
    }
    if ( (v175 & 0x400) != 0 )
    {
      LOWORD(v175) = v175 & 0xFBFF;
      std::string::_Tidy_deallocate(v275);
    }
    if ( (v175 & 0x200) != 0 )
    {
      LOWORD(v175) = v175 & 0xFDFF;
      std::string::_Tidy_deallocate(v285);
    }
    if ( (v175 & 0x100) != 0 )
      std::string::_Tidy_deallocate(v286);
    if ( (v175 & 0x80u) != 0 )
    {
      LOBYTE(v175) = v175 & 0x7F;
      std::string::_Tidy_deallocate(v239);
    }
    if ( (v175 & 0x40) != 0 )
    {
      LOBYTE(v175) = v175 & 0xBF;
      std::string::_Tidy_deallocate(v240);
    }
    if ( (v175 & 0x20) != 0 )
    {
      LOBYTE(v175) = v175 & 0xDF;
      std::string::_Tidy_deallocate(v241);
    }
    if ( (v175 & 0x10) != 0 )
    {
      LOBYTE(v175) = v175 & 0xEF;
      std::string::_Tidy_deallocate(v287);
    }
    if ( (v175 & 8) != 0 )
    {
      LOBYTE(v175) = v175 & 0xF7;
      std::string::_Tidy_deallocate(v288);
    }
    if ( (v175 & 4) != 0 )
    {
      LOBYTE(v175) = v175 & 0xFB;
      std::string::_Tidy_deallocate(v289);
    }
    if ( (v175 & 2) != 0 )
    {
      LOBYTE(v175) = v175 & 0xFD;
      std::string::_Tidy_deallocate(v290);
    }
    if ( (v175 & 1) != 0 )
      std::string::_Tidy_deallocate(v291);
    if ( v140 < 0 )
    {
      v140 &= ~0x80000000;
      std::string::_Tidy_deallocate(v242);
    }
    if ( (v140 & 0x40000000) != 0 )
    {
      v140 &= ~0x40000000u;
      std::string::_Tidy_deallocate(v243);
    }
    if ( (v140 & 0x20000000) != 0 )
    {
      v140 &= ~0x20000000u;
      std::string::_Tidy_deallocate(v244);
    }
    if ( (v140 & 0x10000000) != 0 )
    {
      v140 &= ~0x10000000u;
      std::string::_Tidy_deallocate(v292);
    }
    if ( (v140 & 0x8000000) != 0 )
    {
      v140 &= ~0x8000000u;
      std::string::_Tidy_deallocate(v293);
    }
    if ( (v140 & 0x4000000) != 0 )
    {
      v140 &= ~0x4000000u;
      std::string::_Tidy_deallocate(v294);
    }
    if ( (v140 & 0x2000000) != 0 )
    {
      v140 &= ~0x2000000u;
      std::string::_Tidy_deallocate(v295);
    }
    if ( (v140 & 0x1000000) != 0 )
    {
      v140 &= ~0x1000000u;
      std::string::_Tidy_deallocate(v296);
    }
    if ( (v140 & 0x800000) != 0 )
    {
      v140 &= ~0x800000u;
      std::string::_Tidy_deallocate(v245);
    }
    if ( (v140 & 0x400000) != 0 )
    {
      v140 &= ~0x400000u;
      std::string::_Tidy_deallocate(v246);
    }
    if ( (v140 & 0x200000) != 0 )
    {
      v140 &= ~0x200000u;
      std::string::_Tidy_deallocate(v247);
    }
    if ( (v140 & 0x100000) != 0 )
    {
      v140 &= ~0x100000u;
      std::string::_Tidy_deallocate(v297);
    }
    if ( (v140 & 0x80000) != 0 )
    {
      v140 &= ~0x80000u;
      std::string::_Tidy_deallocate(v298);
    }
    if ( (v140 & 0x40000) != 0 )
    {
      v140 &= ~0x40000u;
      std::string::_Tidy_deallocate(v299);
    }
    if ( (v140 & 0x20000) != 0 )
    {
      v140 &= ~0x20000u;
      std::string::_Tidy_deallocate(v300);
    }
    if ( (v140 & 0x10000) != 0 )
      std::string::_Tidy_deallocate(v301);
    if ( (v140 & 0x8000) != 0 )
    {
      LOWORD(v140) = v140 & 0x7FFF;
      std::string::_Tidy_deallocate(v248);
    }
    if ( (v140 & 0x4000) != 0 )
    {
      LOWORD(v140) = v140 & 0xBFFF;
      std::string::_Tidy_deallocate(v249);
    }
    if ( (v140 & 0x2000) != 0 )
    {
      LOWORD(v140) = v140 & 0xDFFF;
      std::string::_Tidy_deallocate(v250);
    }
    if ( (v140 & 0x1000) != 0 )
    {
      LOWORD(v140) = v140 & 0xEFFF;
      std::string::_Tidy_deallocate(v302);
    }
    if ( (v140 & 0x800) != 0 )
    {
      LOWORD(v140) = v140 & 0xF7FF;
      std::string::_Tidy_deallocate(v303);
    }
    if ( (v140 & 0x400) != 0 )
    {
      LOWORD(v140) = v140 & 0xFBFF;
      std::string::_Tidy_deallocate(v304);
    }
    if ( (v140 & 0x200) != 0 )
    {
      LOWORD(v140) = v140 & 0xFDFF;
      std::string::_Tidy_deallocate(v305);
    }
    if ( (v140 & 0x100) != 0 )
      std::string::_Tidy_deallocate(v306);
    if ( (v140 & 0x80u) != 0 )
    {
      LOBYTE(v140) = v140 & 0x7F;
      std::string::_Tidy_deallocate(v251);
    }
    if ( (v140 & 0x40) != 0 )
    {
      LOBYTE(v140) = v140 & 0xBF;
      std::string::_Tidy_deallocate(v252);
    }
    if ( (v140 & 0x20) != 0 )
    {
      LOBYTE(v140) = v140 & 0xDF;
      std::string::_Tidy_deallocate(v253);
    }
    if ( (v140 & 0x10) != 0 )
    {
      LOBYTE(v140) = v140 & 0xEF;
      std::string::_Tidy_deallocate(v307);
    }
    if ( (v140 & 8) != 0 )
    {
      LOBYTE(v140) = v140 & 0xF7;
      std::string::_Tidy_deallocate(v308);
    }
    if ( (v140 & 4) != 0 )
    {
      LOBYTE(v140) = v140 & 0xFB;
      std::string::_Tidy_deallocate(v309);
    }
    if ( (v140 & 2) != 0 )
    {
      LOBYTE(v140) = v140 & 0xFD;
      std::string::_Tidy_deallocate(v310);
    }
    if ( (v140 & 1) != 0 )
      std::string::_Tidy_deallocate(v311);
    if ( v104 < 0 )
    {
      v104 &= ~0x80000000;
      std::string::_Tidy_deallocate(v254);
    }
    if ( (v104 & 0x40000000) != 0 )
    {
      v104 &= ~0x40000000u;
      std::string::_Tidy_deallocate(v255);
    }
    if ( (v104 & 0x20000000) != 0 )
    {
      v104 &= ~0x20000000u;
      std::string::_Tidy_deallocate(v256);
    }
    if ( (v104 & 0x10000000) != 0 )
    {
      v104 &= ~0x10000000u;
      std::string::_Tidy_deallocate(v312);
    }
    if ( (v104 & 0x8000000) != 0 )
    {
      v104 &= ~0x8000000u;
      std::string::_Tidy_deallocate(v313);
    }
    if ( (v104 & 0x4000000) != 0 )
    {
      v104 &= ~0x4000000u;
      std::string::_Tidy_deallocate(v314);
    }
    if ( (v104 & 0x2000000) != 0 )
    {
      v104 &= ~0x2000000u;
      std::string::_Tidy_deallocate(v315);
    }
    if ( (v104 & 0x1000000) != 0 )
    {
      v104 &= ~0x1000000u;
      std::string::_Tidy_deallocate(v316);
    }
    if ( (v104 & 0x800000) != 0 )
    {
      v104 &= ~0x800000u;
      std::string::_Tidy_deallocate(v257);
    }
    if ( (v104 & 0x400000) != 0 )
    {
      v104 &= ~0x400000u;
      std::string::_Tidy_deallocate(v258);
    }
    if ( (v104 & 0x200000) != 0 )
    {
      v104 &= ~0x200000u;
      std::string::_Tidy_deallocate(v259);
    }
    if ( (v104 & 0x100000) != 0 )
    {
      v104 &= ~0x100000u;
      std::string::_Tidy_deallocate(v317);
    }
    if ( (v104 & 0x80000) != 0 )
    {
      v104 &= ~0x80000u;
      std::string::_Tidy_deallocate(v318);
    }
    if ( (v104 & 0x40000) != 0 )
    {
      v104 &= ~0x40000u;
      std::string::_Tidy_deallocate(v319);
    }
    if ( (v104 & 0x20000) != 0 )
    {
      v104 &= ~0x20000u;
      std::string::_Tidy_deallocate(v320);
    }
    if ( (v104 & 0x10000) != 0 )
      std::string::_Tidy_deallocate(v321);
    if ( (v104 & 0x8000) != 0 )
    {
      LOWORD(v104) = v104 & 0x7FFF;
      std::string::_Tidy_deallocate(v260);
    }
    if ( (v104 & 0x4000) != 0 )
    {
      LOWORD(v104) = v104 & 0xBFFF;
      std::string::_Tidy_deallocate(v261);
    }
    if ( (v104 & 0x2000) != 0 )
    {
      LOWORD(v104) = v104 & 0xDFFF;
      std::string::_Tidy_deallocate(v262);
    }
    if ( (v104 & 0x1000) != 0 )
    {
      LOWORD(v104) = v104 & 0xEFFF;
      std::string::_Tidy_deallocate(v322);
    }
    if ( (v104 & 0x800) != 0 )
    {
      LOWORD(v104) = v104 & 0xF7FF;
      std::string::_Tidy_deallocate(v323);
    }
    if ( (v104 & 0x400) != 0 )
    {
      LOWORD(v104) = v104 & 0xFBFF;
      std::string::_Tidy_deallocate(v324);
    }
    if ( (v104 & 0x200) != 0 )
    {
      LOWORD(v104) = v104 & 0xFDFF;
      std::string::_Tidy_deallocate(v325);
    }
    if ( (v104 & 0x100) != 0 )
      std::string::_Tidy_deallocate(v326);
    if ( (v104 & 0x80u) != 0 )
    {
      LOBYTE(v104) = v104 & 0x7F;
      std::string::_Tidy_deallocate(v263);
    }
    if ( (v104 & 0x40) != 0 )
    {
      LOBYTE(v104) = v104 & 0xBF;
      std::string::_Tidy_deallocate(v264);
    }
    if ( (v104 & 0x20) != 0 )
    {
      LOBYTE(v104) = v104 & 0xDF;
      std::string::_Tidy_deallocate(v265);
    }
    if ( (v104 & 0x10) != 0 )
    {
      LOBYTE(v104) = v104 & 0xEF;
      std::string::_Tidy_deallocate(v327);
    }
    if ( (v104 & 8) != 0 )
    {
      LOBYTE(v104) = v104 & 0xF7;
      std::string::_Tidy_deallocate(v328);
    }
    if ( (v104 & 4) != 0 )
    {
      LOBYTE(v104) = v104 & 0xFB;
      std::string::_Tidy_deallocate(v329);
    }
    if ( (v104 & 2) != 0 )
    {
      LOBYTE(v104) = v104 & 0xFD;
      std::string::_Tidy_deallocate(v330);
    }
    if ( (v104 & 1) != 0 )
      std::string::_Tidy_deallocate(v331);
    std::string::_Tidy_deallocate(v223);
    std::string::_Tidy_deallocate(v224);
    std::string::_Tidy_deallocate(v332);
    std::string::_Tidy_deallocate(v267);
    std::string::_Tidy_deallocate(v268);
    std::string::_Tidy_deallocate(v269);
    std::string::_Tidy_deallocate(v225);
    std::string::_Tidy_deallocate(v226);
    std::string::_Tidy_deallocate(v227);
    std::string::_Tidy_deallocate(v270);
    std::string::_Tidy_deallocate(v271);
    std::string::_Tidy_deallocate(v284);
    std::string::_Tidy_deallocate(&v192);
    std::string::_Tidy_deallocate(v228);
  }
  v184 = *(volatile signed __int32 **)&v338[2];
  if ( *(_QWORD *)&v338[2] )
  {
    if ( !_InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)&v338[2] + 8LL)) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v184)(v184);
      if ( !_InterlockedDecrement(v184 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v184 + 8LL))(v184);
    }
  }
  v185 = v198;
  ContainmentSwitches = Microsoft::Basix::Dct::PropertyImpl::GetContainmentSwitches(v198 + 16, v338);
  Microsoft::Basix::Containers::AnyPTreeMerge(v200, ContainmentSwitches);
  boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(v338);
  boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::operator=(v185 + 200);
  std::string::_Tidy_deallocate(v340);
  v187 = *((_QWORD *)&v201 + 1);
  if ( *((_QWORD *)&v201 + 1)
    && _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v201 + 1) + 12LL), 0xFFFFFFFF) == 1 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v187 + 8LL))(v187);
  }
  v188 = (volatile signed __int32 *)v202[1];
  if ( v188 )
  {
    if ( _InterlockedExchangeAdd(v188 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v188)(v188);
      if ( _InterlockedExchangeAdd(v188 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v188 + 8LL))(v188);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800fa23c  push    rbx
0x1800fa23e  push    rsi
0x1800fa23f  push    rdi
0x1800fa240  push    r12
0x1800fa242  push    r13
0x1800fa244  push    r14
0x1800fa246  push    r15
0x1800fa248  mov     eax, 1160h
0x1800fa24d  call    _alloca_probe
0x1800fa252  sub     rsp, rax
0x1800fa255  mov     rax, cs:__security_cookie
0x1800fa25c  xor     rax, rsp
0x1800fa25f  mov     [rsp+1198h+var_48], rax
0x1800fa267  mov     r12, r9
0x1800fa26a  mov     [rsp+1198h+var_10B0], r9
0x1800fa272  mov     rsi, r8
0x1800fa275  mov     r14b, dl
0x1800fa278  mov     rbx, rcx
0x1800fa27b  mov     [rsp+1198h+var_10D8], rcx
0x1800fa283  mov     rax, [rsp+1198h+arg_40]
0x1800fa28b  mov     [rsp+1198h+var_10A0], rax
0x1800fa293  mov     rax, [rsp+1198h+arg_38]
0x1800fa29b  mov     [rsp+1198h+var_10E8], rax
0x1800fa2a3  mov     [rsp+1198h+var_10A8], r9
0x1800fa2ab  mov     rax, [rsp+1198h+arg_30]
0x1800fa2b3  mov     [rsp+1198h+var_1098], rax
0x1800fa2bb  mov     r15, [rsp+1198h+arg_48]
0x1800fa2c3  mov     [rsp+1198h+var_10C8], r15
0x1800fa2cb  xor     r13d, r13d
0x1800fa2ce  mov     [rsp+1198h+var_1124], r13d
0x1800fa2d3  mov     [rsp+1198h+var_1120], r13d
0x1800fa2d8  mov     [rsp+1198h+var_111C], r13d
0x1800fa2dd  xorps   xmm0, xmm0
0x1800fa2e0  movups  [rsp+1198h+var_10C0], xmm0
0x1800fa2e8  mov     rax, [rcx+70h]
0x1800fa2ec  movsxd  rcx, dword ptr [rax+4]
0x1800fa2f0  add     rcx, 70h ; 'p'
0x1800fa2f4  add     rcx, rbx
0x1800fa2f7  lea     rdx, [rsp+1198h+var_10C0]
0x1800fa2ff  call    ??$GetWeakPtr@VICEDelegate@Dct@Basix@Microsoft@@@SharedFromThisVirtualBase@Basix@Microsoft@@QEAA?AV?$weak_ptr@VICEDelegate@Dct@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::SharedFromThisVirtualBase::GetWeakPtr<Microsoft::Basix::Dct::ICEDelegate>(void)
0x1800fa304  nop
0x1800fa305  xorps   xmm0, xmm0
0x1800fa308  movups  [rsp+1198h+var_1118], xmm0
0x1800fa310  xorps   xmm1, xmm1
0x1800fa313  movdqu  [rsp+1198h+var_1108], xmm1
0x1800fa31c  lea     r8d, [r13+22h]
0x1800fa320  lea     rdx, aMicrosoftBasix_7; "Microsoft::Basix::Dct.ICE.Delegate"
0x1800fa327  lea     rcx, [rsp+1198h+var_1118]
0x1800fa32f  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800fa334  mov     [rsp+1198h+var_10F8], 2Eh ; '.'
0x1800fa33c  lea     rax, [rsp+1198h+var_1118]
0x1800fa344  cmp     qword ptr [rsp+1198h+var_1108+8], 0Fh
0x1800fa34d  cmova   rax, qword ptr [rsp+1198h+var_1118]
0x1800fa356  mov     [rsp+1198h+var_10F0], rax
0x1800fa35e  lea     r8, [rsp+1198h+var_10C0]
0x1800fa366  lea     rdx, [rsp+1198h+var_1118]
0x1800fa36e  mov     rcx, r15
0x1800fa371  call    ??$put@V?$weak_ptr@VICEDelegate@Dct@Basix@Microsoft@@@std@@@?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEAAAEAV012@AEBV?$string_path@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$id_translator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@property_tree@boost@@@12@AEBV?$weak_ptr@VICEDelegate@Dct@Basix@Microsoft@@@std@@@Z; boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::put<std::weak_ptr<Microsoft::Basix::Dct::ICEDelegate>>(boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>> const &,std::weak_ptr<Microsoft::Basix::Dct::ICEDelegate> const &)
0x1800fa376  nop
0x1800fa377  lea     rcx, [rsp+1198h+var_1118]
0x1800fa37f  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800fa384  cmp     [r12], r13
0x1800fa388  jz      loc_1800FA54E
0x1800fa38e  lea     rdi, [rbx+130h]
0x1800fa395  mov     rdx, r12
0x1800fa398  mov     rcx, rdi
0x1800fa39b  call    ??4?$shared_ptr@VRendezvousContext@RendezvousSource@RdpNano@Microsoft@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<Microsoft::RdpNano::RendezvousSource::RendezvousContext>::operator=(std::shared_ptr<Microsoft::RdpNano::RendezvousSource::RendezvousContext> const &)
0x1800fa3a0  xorps   xmm0, xmm0
0x1800fa3a3  movdqu  [rsp+1198h+var_1B8], xmm0
0x1800fa3ac  mov     rcx, [rdi+8]
0x1800fa3b0  lea     r12d, [r13+1]
0x1800fa3b4  test    rcx, rcx
0x1800fa3b7  jz      short loc_1800FA3D1
0x1800fa3b9  mov     rax, [rdi]
0x1800fa3bc  mov     qword ptr [rsp+1198h+var_1B8], rax
0x1800fa3c4  mov     qword ptr [rsp+1198h+var_1B8+8], rcx
0x1800fa3cc  lock add [rcx+0Ch], r12d
0x1800fa3d1  movups  [rsp+1198h+var_1118], xmm0
0x1800fa3d9  xorps   xmm1, xmm1
0x1800fa3dc  movdqu  [rsp+1198h+var_1108], xmm1
0x1800fa3e5  mov     r8d, 1Eh
0x1800fa3eb  lea     rdx, aMicrosoftBasix_455; "Microsoft::Basix::Dct.ICE.Port"
0x1800fa3f2  lea     rcx, [rsp+1198h+var_1118]
0x1800fa3fa  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800fa3ff  mov     [rsp+1198h+var_10F8], 2Eh ; '.'
0x1800fa407  lea     rax, [rsp+1198h+var_1118]
0x1800fa40f  cmp     qword ptr [rsp+1198h+var_1108+8], 0Fh
0x1800fa418  cmova   rax, qword ptr [rsp+1198h+var_1118]
0x1800fa421  mov     [rsp+1198h+var_10F0], rax
0x1800fa429  lea     r8, [rsp+1198h+var_1B8]
0x1800fa431  lea     rdx, [rsp+1198h+var_1118]
0x1800fa439  mov     rcx, r15
0x1800fa43c  call    ??$put@V?$weak_ptr@VIPortAllocator@Dct@Basix@Microsoft@@@std@@@?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEAAAEAV012@AEBV?$string_path@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$id_translator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@property_tree@boost@@@12@AEBV?$weak_ptr@VIPortAllocator@Dct@Basix@Microsoft@@@std@@@Z; boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::put<std::weak_ptr<Microsoft::Basix::Dct::IPortAllocator>>(boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>> const &,std::weak_ptr<Microsoft::Basix::Dct::IPortAllocator> const &)
0x1800fa441  nop
0x1800fa442  lea     rcx, [rsp+1198h+var_1118]
0x1800fa44a  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800fa44f  nop
0x1800fa450  mov     rcx, qword ptr [rsp+1198h+var_1B8+8]
0x1800fa458  or      ebx, 0FFFFFFFFh
0x1800fa45b  test    rcx, rcx
0x1800fa45e  jz      short loc_1800FA478
0x1800fa460  mov     eax, ebx
0x1800fa462  lock xadd [rcx+0Ch], eax
0x1800fa467  add     eax, ebx
0x1800fa469  jnz     short loc_1800FA478
0x1800fa46b  mov     rax, [rcx]
0x1800fa46e  mov     rax, [rax+8]
0x1800fa472  call    cs:__guard_dispatch_icall_fptr
0x1800fa478  xorps   xmm0, xmm0
0x1800fa47b  movdqu  [rsp+1198h+var_1B8], xmm0
0x1800fa484  mov     rcx, [rdi+8]
0x1800fa488  test    rcx, rcx
0x1800fa48b  jz      short loc_1800FA4A5
0x1800fa48d  mov     rax, [rdi]
0x1800fa490  mov     qword ptr [rsp+1198h+var_1B8], rax
0x1800fa498  mov     qword ptr [rsp+1198h+var_1B8+8], rcx
0x1800fa4a0  lock add [rcx+0Ch], r12d
0x1800fa4a5  movups  [rsp+1198h+var_1118], xmm0
0x1800fa4ad  xorps   xmm1, xmm1
0x1800fa4b0  movdqu  [rsp+1198h+var_1108], xmm1
0x1800fa4b9  mov     r12d, 1Fh
0x1800fa4bf  mov     r8d, r12d
0x1800fa4c2  lea     rdx, aMicrosoftBasix_48; "Microsoft::Basix::Dct.UPnP.Port"
0x1800fa4c9  lea     rcx, [rsp+1198h+var_1118]
0x1800fa4d1  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800fa4d6  mov     [rsp+1198h+var_10F8], 2Eh ; '.'
0x1800fa4de  lea     rax, [rsp+1198h+var_1118]
0x1800fa4e6  cmp     qword ptr [rsp+1198h+var_1108+8], 0Fh
0x1800fa4ef  cmova   rax, qword ptr [rsp+1198h+var_1118]
0x1800fa4f8  mov     [rsp+1198h+var_10F0], rax
0x1800fa500  lea     r8, [rsp+1198h+var_1B8]
0x1800fa508  lea     rdx, [rsp+1198h+var_1118]
0x1800fa510  mov     rcx, r15
0x1800fa513  call    ??$put@V?$weak_ptr@VIPortAllocator@Dct@Basix@Microsoft@@@std@@@?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEAAAEAV012@AEBV?$string_path@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$id_translator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@property_tree@boost@@@12@AEBV?$weak_ptr@VIPortAllocator@Dct@Basix@Microsoft@@@std@@@Z; boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::put<std::weak_ptr<Microsoft::Basix::Dct::IPortAllocator>>(boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>> const &,std::weak_ptr<Microsoft::Basix::Dct::IPortAllocator> const &)
0x1800fa518  nop
0x1800fa519  lea     rcx, [rsp+1198h+var_1118]
0x1800fa521  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800fa526  nop
0x1800fa527  mov     rcx, qword ptr [rsp+1198h+var_1B8+8]
0x1800fa52f  test    rcx, rcx
0x1800fa532  jz      short loc_1800FA555
0x1800fa534  mov     eax, ebx
0x1800fa536  lock xadd [rcx+0Ch], eax
0x1800fa53b  add     eax, ebx
0x1800fa53d  jnz     short loc_1800FA555
0x1800fa53f  mov     rax, [rcx]
0x1800fa542  mov     rax, [rax+8]
0x1800fa546  call    cs:__guard_dispatch_icall_fptr
0x1800fa54c  jmp     short loc_1800FA555
0x1800fa54e  or      ebx, 0FFFFFFFFh
0x1800fa551  lea     r12d, [rbx+20h]
0x1800fa555  mov     edi, 1
0x1800fa55a  mov     rax, [rsp+1198h+var_10D8]
0x1800fa562  mov     [rax+140h], r14b
0x1800fa569  mov     eax, [rsp+1198h+arg_28]
0x1800fa570  test    eax, eax
0x1800fa572  jz      loc_1800FA7A9
0x1800fa578  sub     eax, edi
0x1800fa57a  jz      loc_1800FA724
0x1800fa580  sub     eax, edi
0x1800fa582  jz      loc_1800FA69B
0x1800fa588  cmp     eax, edi
0x1800fa58a  jz      short loc_1800FA602
0x1800fa58c  mov     rcx, qword ptr [rsp+1198h+var_10C0+8]
0x1800fa594  test    rcx, rcx
0x1800fa597  jz      short loc_1800FA5B2
0x1800fa599  mov     eax, ebx
0x1800fa59b  lock xadd [rcx+0Ch], eax
0x1800fa5a0  add     eax, ebx
0x1800fa5a2  jnz     short loc_1800FA5B2
0x1800fa5a4  mov     rax, [rcx]
0x1800fa5a7  mov     rax, [rax+8]
0x1800fa5ab  call    cs:__guard_dispatch_icall_fptr
0x1800fa5b1  nop
0x1800fa5b2  mov     rdi, [rsp+1198h+var_10B0]
0x1800fa5ba  mov     rdi, [rdi+8]
0x1800fa5be  test    rdi, rdi
0x1800fa5c1  jz      short loc_1800FA5F8
0x1800fa5c3  mov     eax, ebx
0x1800fa5c5  lock xadd [rdi+8], eax
0x1800fa5ca  add     eax, ebx
0x1800fa5cc  jnz     short loc_1800FA5F8
0x1800fa5ce  mov     rax, [rdi]
0x1800fa5d1  mov     rcx, rdi
0x1800fa5d4  mov     rax, [rax]
0x1800fa5d7  call    cs:__guard_dispatch_icall_fptr
0x1800fa5dd  mov     eax, ebx
0x1800fa5df  lock xadd [rdi+0Ch], eax
0x1800fa5e4  add     eax, ebx
0x1800fa5e6  jnz     short loc_1800FA5F8
0x1800fa5e8  mov     rax, [rdi]
0x1800fa5eb  mov     rcx, rdi
0x1800fa5ee  mov     rax, [rax+8]
0x1800fa5f2  call    cs:__guard_dispatch_icall_fptr
0x1800fa5f8  mov     eax, 80070057h
0x1800fa5fd  jmp     loc_1800FD396
0x1800fa602  mov     r15d, 3
0x1800fa608  mov     dword ptr [rsp+1198h+var_10E0], r15d
0x1800fa610  xorps   xmm0, xmm0
0x1800fa613  movups  [rsp+1198h+var_1118], xmm0
0x1800fa61b  xorps   xmm1, xmm1
0x1800fa61e  movdqu  [rsp+1198h+var_1108], xmm1
0x1800fa627  mov     r8, r12
0x1800fa62a  lea     rdx, aMicrosoftBasix_34; "Microsoft::Basix::Dct.Ip.Family"
0x1800fa631  lea     rcx, [rsp+1198h+var_1118]
0x1800fa639  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800fa63e  mov     [rsp+1198h+var_10F8], 2Eh ; '.'
0x1800fa646  lea     rax, [rsp+1198h+var_1118]
0x1800fa64e  cmp     qword ptr [rsp+1198h+var_1108+8], 0Fh
0x1800fa657  cmova   rax, qword ptr [rsp+1198h+var_1118]
0x1800fa660  mov     [rsp+1198h+var_10F0], rax
0x1800fa668  lea     r8, [rsp+1198h+var_10E0]
0x1800fa670  lea     rdx, [rsp+1198h+var_1118]
0x1800fa678  mov     r14, [rsp+1198h+var_10C8]
0x1800fa680  mov     rcx, r14
0x1800fa683  call    ??$put@H@?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEAAAEAV012@AEBV?$string_path@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$id_translator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@property_tree@boost@@@12@AEBH@Z; boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::put<int>(boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>> const &,int const &)
0x1800fa688  nop
0x1800fa689  lea     rcx, [rsp+1198h+var_1118]
0x1800fa691  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800fa696  jmp     loc_1800FA83D
0x1800fa69b  mov     dword ptr [rsp+1198h+var_10E0], 2
0x1800fa6a6  xorps   xmm0, xmm0
0x1800fa6a9  movups  [rsp+1198h+var_1118], xmm0
0x1800fa6b1  xorps   xmm1, xmm1
0x1800fa6b4  movdqu  [rsp+1198h+var_1108], xmm1
0x1800fa6bd  mov     r8, r12
0x1800fa6c0  lea     rdx, aMicrosoftBasix_34; "Microsoft::Basix::Dct.Ip.Family"
0x1800fa6c7  lea     rcx, [rsp+1198h+var_1118]
0x1800fa6cf  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800fa6d4  mov     [rsp+1198h+var_10F8], 2Eh ; '.'
0x1800fa6dc  lea     rax, [rsp+1198h+var_1118]
0x1800fa6e4  cmp     qword ptr [rsp+1198h+var_1108+8], 0Fh
0x1800fa6ed  cmova   rax, qword ptr [rsp+1198h+var_1118]
0x1800fa6f6  mov     [rsp+1198h+var_10F0], rax
0x1800fa6fe  lea     r8, [rsp+1198h+var_10E0]
0x1800fa706  lea     rdx, [rsp+1198h+var_1118]
0x1800fa70e  mov     r14, [rsp+1198h+var_10C8]
0x1800fa716  mov     rcx, r14
0x1800fa719  call    ??$put@H@?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEAAAEAV012@AEBV?$string_path@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$id_translator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@property_tree@boost@@@12@AEBH@Z; boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::put<int>(boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>> const &,int const &)
0x1800fa71e  nop
0x1800fa71f  jmp     loc_1800FA82A
0x1800fa724  mov     dword ptr [rsp+1198h+var_10E0], edi
0x1800fa72b  xorps   xmm0, xmm0
0x1800fa72e  movups  [rsp+1198h+var_1118], xmm0
0x1800fa736  xorps   xmm1, xmm1
0x1800fa739  movdqu  [rsp+1198h+var_1108], xmm1
0x1800fa742  mov     r8, r12
0x1800fa745  lea     rdx, aMicrosoftBasix_34; "Microsoft::Basix::Dct.Ip.Family"
0x1800fa74c  lea     rcx, [rsp+1198h+var_1118]
0x1800fa754  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800fa759  mov     [rsp+1198h+var_10F8], 2Eh ; '.'
0x1800fa761  lea     rax, [rsp+1198h+var_1118]
0x1800fa769  cmp     qword ptr [rsp+1198h+var_1108+8], 0Fh
0x1800fa772  cmova   rax, qword ptr [rsp+1198h+var_1118]
0x1800fa77b  mov     [rsp+1198h+var_10F0], rax
0x1800fa783  lea     r8, [rsp+1198h+var_10E0]
0x1800fa78b  lea     rdx, [rsp+1198h+var_1118]
0x1800fa793  mov     r14, [rsp+1198h+var_10C8]
0x1800fa79b  mov     rcx, r14
0x1800fa79e  call    ??$put@H@?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEAAAEAV012@AEBV?$string_path@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$id_translator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@property_tree@boost@@@12@AEBH@Z; boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::put<int>(boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>> const &,int const &)
0x1800fa7a3  nop
0x1800fa7a4  jmp     loc_1800FA82A
0x1800fa7a9  mov     dword ptr [rsp+1198h+var_10E0], r13d
0x1800fa7b1  xorps   xmm0, xmm0
0x1800fa7b4  movups  [rsp+1198h+var_1118], xmm0
0x1800fa7bc  xorps   xmm1, xmm1
0x1800fa7bf  movdqu  [rsp+1198h+var_1108], xmm1
0x1800fa7c8  mov     r8, r12
0x1800fa7cb  lea     rdx, aMicrosoftBasix_34; "Microsoft::Basix::Dct.Ip.Family"
0x1800fa7d2  lea     rcx, [rsp+1198h+var_1118]
0x1800fa7da  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800fa7df  mov     [rsp+1198h+var_10F8], 2Eh ; '.'
0x1800fa7e7  lea     rax, [rsp+1198h+var_1118]
0x1800fa7ef  cmp     qword ptr [rsp+1198h+var_1108+8], 0Fh
0x1800fa7f8  cmova   rax, qword ptr [rsp+1198h+var_1118]
0x1800fa801  mov     [rsp+1198h+var_10F0], rax
0x1800fa809  lea     r8, [rsp+1198h+var_10E0]
0x1800fa811  lea     rdx, [rsp+1198h+var_1118]
0x1800fa819  mov     r14, [rsp+1198h+var_10C8]
0x1800fa821  mov     rcx, r14
0x1800fa824  call    ??$put@H@?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEAAAEAV012@AEBV?$string_path@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$id_translator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@property_tree@boost@@@12@AEBH@Z; boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::put<int>(boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>> const &,int const &)
0x1800fa829  nop
0x1800fa82a  lea     rcx, [rsp+1198h+var_1118]
0x1800fa832  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800fa837  mov     r15d, 3
0x1800fa83d  xorps   xmm0, xmm0
0x1800fa840  movups  [rsp+1198h+var_1118], xmm0
0x1800fa848  xorps   xmm1, xmm1
0x1800fa84b  movdqu  [rsp+1198h+var_1108], xmm1
0x1800fa854  mov     r8d, 20h ; ' '
0x1800fa85a  lea     rdx, aMicrosoftBasix_226; "Microsoft::Basix::Dct.ActivityId"
0x1800fa861  lea     rcx, [rsp+1198h+var_1118]
0x1800fa869  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800fa86e  mov     [rsp+1198h+var_10F8], 2Eh ; '.'
0x1800fa876  lea     rax, [rsp+1198h+var_1118]
0x1800fa87e  cmp     qword ptr [rsp+1198h+var_1108+8], 0Fh
0x1800fa887  cmova   rax, qword ptr [rsp+1198h+var_1118]
0x1800fa890  mov     [rsp+1198h+var_10F0], rax
0x1800fa898  mov     r8, rsi
0x1800fa89b  lea     rdx, [rsp+1198h+var_1118]
  ... truncated ...
```
