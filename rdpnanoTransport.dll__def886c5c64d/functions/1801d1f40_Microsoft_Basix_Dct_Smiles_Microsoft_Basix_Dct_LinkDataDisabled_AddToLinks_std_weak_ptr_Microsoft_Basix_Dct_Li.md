# Microsoft::Basix::Dct::Smiles<Microsoft::Basix::Dct::LinkDataDisabled>::AddToLinks(std::weak_ptr<Microsoft::Basix::Dct::LinkData>)

- ea: `0x1801d1f40`
- end: `0x1801d43a4`
- name: `?AddToLinks@?$Smiles@VLinkDataDisabled@Dct@Basix@Microsoft@@@Dct@Basix@Microsoft@@MEAAXV?$weak_ptr@VLinkData@Dct@Basix@Microsoft@@@std@@@Z`
- size: `9316`
- prototype: ``
- caller_count: `0`
- callee_count: `41`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000d9c0`
- `0x180015bb8`
- `0x180017380`
- `0x180018b94`
- `0x18001902c`
- `0x1800199ec`
- `0x18001dad8`
- `0x18001db78`
- `0x18001dc00`
- `0x18001fd8c`
- `0x180024568`
- `0x180024700`
- `0x180024760`
- `0x180024c14`
- `0x180028820`
- `0x1800c5a90`
- `0x1800dc4bc`
- `0x1800dc750`
- `0x1800dcae4`
- `0x1800f91d0`
- `0x180107b08`
- `0x18010d048`
- `0x180122f6c`
- `0x18018c684`
- `0x1801ad754`
- `0x1801b0ab4`
- `0x1801b205c`
- `0x1801cd178`
- `0x1801cda84`
- `0x1801cdb94`
- `0x1801cf6f8`
- `0x1801cf8d4`
- `0x1801d1f40`
- `0x18031215c`
- `0x180312164`
- `0x180312404`
- `0x18032f050`
- `0x18032f0b0`
- `0x18032f100`
- `0x18032f140`
- `0x180375c40`

## string_xrefs

- `0x1801d20fc`: `Microsoft::Basix::Dct.Smiles.LinkPoolSize`
- `0x1801d2743`: `LinkId`
- `0x1801d2212`: `Microsoft::Basix::Dct.Smiles.LinkType`
- `0x1801d21a4`: `Microsoft::Basix::Dct.Smiles.AddLinkInfo`
- `0x1801d25d4`: `LinkType`
- `0x1801d268b`: `linksSize`
- `0x1801d27ea`: `AddLink`
- `0x1801d2af8`: `Components`
- `0x1801d2d17`: `Checkpoint.SMILES.LinkAdded(%d),IceDoR(%d)|nonIceDor(%d):%s, TransportTypeOnServer=%s, TransportTypeOnClient=%s, TransportIPOnServer=%s, TransportIPOnClient=%s`

## pseudocode

```c
// Hidden C++ exception states: #wind=180
__int64 __fastcall Microsoft::Basix::Dct::Smiles<Microsoft::Basix::Dct::LinkDataDisabled>::AddToLinks(
        __int64 *a1,
        __int64 a2)
{
  __int64 *v3; // r15
  int v4; // r12d
  __int64 v5; // rdx
  signed __int32 v6; // eax
  signed __int32 v7; // ett
  volatile signed __int32 *v8; // rbx
  __int64 result; // rax
  volatile signed __int32 *v10; // rbx
  volatile signed __int32 *v11; // rcx
  __int128 *v12; // rax
  __int64 v13; // rsi
  __int64 v14; // rbx
  __int64 Property; // rax
  __int64 v16; // r8
  int v17; // r13d
  __int64 v18; // rbx
  __int64 v19; // rax
  __int128 *v20; // rax
  __int64 v21; // r15
  _QWORD *v22; // r14
  __int64 v23; // rsi
  __int64 v24; // rdi
  __int64 v25; // rbx
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // rdx
  __int64 v29; // rdx
  __int64 v30; // rdx
  __int64 v31; // rax
  __int64 v32; // rdx
  __int64 v33; // rdi
  __int64 v34; // rbx
  __int64 v35; // rax
  __int64 v36; // rax
  __int64 v37; // rdx
  __int64 v38; // rdx
  __int64 v39; // rdx
  __int64 v40; // rdi
  __int64 v41; // rbx
  __int64 v42; // rax
  __int64 v43; // rax
  __int64 v44; // rdx
  __int64 v45; // rdx
  __int64 v46; // rdx
  __int64 v47; // rdi
  __int64 v48; // rbx
  __int64 v49; // rax
  __int64 v50; // rax
  __int64 v51; // rdx
  __int64 v52; // rdx
  __int64 v53; // rdx
  __int64 v54; // rax
  __int64 v55; // rdi
  __int64 v56; // rbx
  __int64 v57; // rax
  __int64 v58; // rax
  __int64 v59; // rdx
  __int64 v60; // rdx
  __int64 v61; // rdx
  __int64 v62; // rdi
  __int64 v63; // rbx
  __int64 v64; // rax
  __int64 v65; // rax
  __int64 v66; // rdx
  __int64 v67; // rdx
  __int64 v68; // rdx
  volatile signed __int32 *v69; // rbx
  void *v70; // rax
  __int64 v71; // rax
  __int128 *v72; // rax
  __int64 child; // rax
  const struct std::nothrow_t *v74; // rdx
  __int64 v75; // r9
  __int64 v76; // r8
  __int64 *v77; // rax
  __int64 v78; // r9
  __int64 v79; // r8
  __int64 *v80; // rax
  __int64 v81; // r9
  __int64 v82; // r8
  __int64 *v83; // rax
  __int64 v84; // r9
  __int64 v85; // r8
  __int64 *v86; // rax
  int v87; // r8d
  int v88; // r9d
  _QWORD *v89; // r14
  int v90; // ebx
  int v91; // edi
  int v92; // esi
  volatile signed __int32 *v93; // rbx
  __int128 *v94; // rax
  __int64 v95; // rax
  void *v96; // rcx
  __int128 *v97; // rax
  __int64 v98; // rax
  void *v99; // rcx
  __int128 *v100; // rax
  __int64 v101; // rax
  void *v102; // rcx
  __int128 *v103; // rax
  __int64 v104; // rax
  void *v105; // rcx
  __int64 v106; // rax
  void *v107; // rcx
  __int128 *v108; // rax
  __int64 v109; // rax
  void *v110; // rcx
  __int64 v111; // r9
  __int64 v112; // r8
  __int64 v113; // rax
  void *v114; // rcx
  __int128 *v115; // rax
  __int64 v116; // rax
  void *v117; // rcx
  __int128 *v118; // rax
  __int64 v119; // rax
  void *v120; // rcx
  __int128 *v121; // rax
  __int64 v122; // rax
  void *v123; // rcx
  __int128 *v124; // rax
  __int64 v125; // rax
  void *v126; // rcx
  __int128 *v127; // rax
  __int64 v128; // rax
  void *v129; // rcx
  __int128 *v130; // rax
  __int64 v131; // rax
  void *v132; // rcx
  __int128 *v133; // rax
  __int128 *v134; // rax
  __int64 v135; // rax
  void *v136; // rcx
  __int128 *v137; // rax
  __int64 v138; // rax
  void *v139; // rcx
  __int64 v140; // rax
  void *v141; // rcx
  volatile signed __int32 *v142; // rbx
  int v143; // [rsp+20h] [rbp-110h]
  char *Str; // [rsp+28h] [rbp-108h]
  const char *v145; // [rsp+30h] [rbp-100h]
  const char *v146; // [rsp+38h] [rbp-F8h]
  const char *v147; // [rsp+40h] [rbp-F0h]
  const char *v148; // [rsp+48h] [rbp-E8h]
  _BYTE v149[8]; // [rsp+B0h] [rbp-80h] BYREF
  __int64 *v150; // [rsp+B8h] [rbp-78h]
  __int64 *v151; // [rsp+C0h] [rbp-70h]
  _BYTE v152[4]; // [rsp+C8h] [rbp-68h] BYREF
  unsigned int v153; // [rsp+CCh] [rbp-64h] BYREF
  __int64 *v154; // [rsp+D0h] [rbp-60h] BYREF
  __int64 *v155; // [rsp+D8h] [rbp-58h] BYREF
  __int128 v156; // [rsp+E0h] [rbp-50h] BYREF
  __int128 v157; // [rsp+F0h] [rbp-40h]
  char v158; // [rsp+100h] [rbp-30h]
  __int128 *v159; // [rsp+108h] [rbp-28h]
  void *v160[2]; // [rsp+110h] [rbp-20h] BYREF
  __int64 v161; // [rsp+120h] [rbp-10h]
  char v162; // [rsp+128h] [rbp-8h]
  void *v163[2]; // [rsp+130h] [rbp+0h] BYREF
  __int128 v164; // [rsp+140h] [rbp+10h]
  void *v165[2]; // [rsp+150h] [rbp+20h] BYREF
  __int128 v166; // [rsp+160h] [rbp+30h]
  __int64 *v167; // [rsp+170h] [rbp+40h]
  __int64 v168[2]; // [rsp+178h] [rbp+48h] BYREF
  __int128 v169; // [rsp+188h] [rbp+58h]
  __int64 v170[2]; // [rsp+198h] [rbp+68h] BYREF
  __int128 v171; // [rsp+1A8h] [rbp+78h]
  __int64 v172[2]; // [rsp+1B8h] [rbp+88h] BYREF
  __int128 v173; // [rsp+1C8h] [rbp+98h]
  __int64 v174[2]; // [rsp+1D8h] [rbp+A8h] BYREF
  __int128 v175; // [rsp+1E8h] [rbp+B8h]
  __int64 v176[2]; // [rsp+1F8h] [rbp+C8h] BYREF
  __int128 v177; // [rsp+208h] [rbp+D8h]
  int v178; // [rsp+218h] [rbp+E8h] BYREF
  void *v179; // [rsp+220h] [rbp+F0h]
  __int64 v180; // [rsp+228h] [rbp+F8h]
  char v181; // [rsp+230h] [rbp+100h]
  int v182; // [rsp+238h] [rbp+108h] BYREF
  void *v183; // [rsp+240h] [rbp+110h]
  __int64 v184; // [rsp+248h] [rbp+118h]
  char v185; // [rsp+250h] [rbp+120h]
  int v186; // [rsp+258h] [rbp+128h] BYREF
  void *v187; // [rsp+260h] [rbp+130h]
  __int64 v188; // [rsp+268h] [rbp+138h]
  char v189; // [rsp+270h] [rbp+140h]
  int v190; // [rsp+278h] [rbp+148h] BYREF
  void *v191; // [rsp+280h] [rbp+150h]
  __int64 v192; // [rsp+288h] [rbp+158h]
  char v193; // [rsp+290h] [rbp+160h]
  int v194; // [rsp+298h] [rbp+168h] BYREF
  void *v195; // [rsp+2A0h] [rbp+170h]
  __int64 v196; // [rsp+2A8h] [rbp+178h]
  char v197; // [rsp+2B0h] [rbp+180h]
  int v198; // [rsp+2B8h] [rbp+188h] BYREF
  void *v199; // [rsp+2C0h] [rbp+190h]
  __int64 v200; // [rsp+2C8h] [rbp+198h]
  char v201; // [rsp+2D0h] [rbp+1A0h]
  int v202; // [rsp+2D8h] [rbp+1A8h] BYREF
  void *v203; // [rsp+2E0h] [rbp+1B0h]
  __int64 v204; // [rsp+2E8h] [rbp+1B8h]
  char v205; // [rsp+2F0h] [rbp+1C0h]
  int v206; // [rsp+2F8h] [rbp+1C8h] BYREF
  void *v207; // [rsp+300h] [rbp+1D0h]
  __int64 v208; // [rsp+308h] [rbp+1D8h]
  char v209; // [rsp+310h] [rbp+1E0h]
  int v210; // [rsp+318h] [rbp+1E8h] BYREF
  void *v211; // [rsp+320h] [rbp+1F0h]
  __int64 v212; // [rsp+328h] [rbp+1F8h]
  char v213; // [rsp+330h] [rbp+200h]
  int v214; // [rsp+338h] [rbp+208h] BYREF
  void *v215; // [rsp+340h] [rbp+210h]
  __int64 v216; // [rsp+348h] [rbp+218h]
  char v217; // [rsp+350h] [rbp+220h]
  int v218; // [rsp+358h] [rbp+228h] BYREF
  void *v219; // [rsp+360h] [rbp+230h]
  __int64 v220; // [rsp+368h] [rbp+238h]
  char v221; // [rsp+370h] [rbp+240h]
  int v222; // [rsp+378h] [rbp+248h] BYREF
  void *v223; // [rsp+380h] [rbp+250h]
  __int64 v224; // [rsp+388h] [rbp+258h]
  char v225; // [rsp+390h] [rbp+260h]
  int v226; // [rsp+398h] [rbp+268h] BYREF
  void *v227; // [rsp+3A0h] [rbp+270h]
  __int64 v228; // [rsp+3A8h] [rbp+278h]
  char v229; // [rsp+3B0h] [rbp+280h]
  __int128 v230; // [rsp+3B8h] [rbp+288h] BYREF
  __int128 v231; // [rsp+3C8h] [rbp+298h]
  char v232; // [rsp+3D8h] [rbp+2A8h]
  __int128 *v233; // [rsp+3E0h] [rbp+2B0h]
  __int128 v234; // [rsp+3E8h] [rbp+2B8h] BYREF
  __int128 v235; // [rsp+3F8h] [rbp+2C8h]
  char v236; // [rsp+408h] [rbp+2D8h]
  __int128 *v237; // [rsp+410h] [rbp+2E0h]
  __int128 v238; // [rsp+418h] [rbp+2E8h] BYREF
  __int128 v239; // [rsp+428h] [rbp+2F8h]
  char v240; // [rsp+438h] [rbp+308h]
  __int128 *v241; // [rsp+440h] [rbp+310h]
  __int128 v242; // [rsp+448h] [rbp+318h] BYREF
  __int128 v243; // [rsp+458h] [rbp+328h]
  char v244; // [rsp+468h] [rbp+338h]
  __int128 *v245; // [rsp+470h] [rbp+340h]
  _OWORD v246[2]; // [rsp+478h] [rbp+348h] BYREF
  _OWORD v247[2]; // [rsp+498h] [rbp+368h] BYREF
  _OWORD v248[2]; // [rsp+4B8h] [rbp+388h] BYREF
  _OWORD v249[2]; // [rsp+4D8h] [rbp+3A8h] BYREF
  _OWORD v250[2]; // [rsp+4F8h] [rbp+3C8h] BYREF
  _OWORD v251[2]; // [rsp+518h] [rbp+3E8h] BYREF
  __int64 v252[2]; // [rsp+538h] [rbp+408h] BYREF
  __int128 v253; // [rsp+548h] [rbp+418h]
  __int128 v254; // [rsp+558h] [rbp+428h] BYREF
  __int128 v255; // [rsp+568h] [rbp+438h]
  char v256; // [rsp+578h] [rbp+448h]
  __int128 *v257; // [rsp+580h] [rbp+450h]
  __int128 v258; // [rsp+588h] [rbp+458h] BYREF
  __int128 v259; // [rsp+598h] [rbp+468h]
  char v260; // [rsp+5A8h] [rbp+478h]
  __int128 *v261; // [rsp+5B0h] [rbp+480h]
  __int128 v262; // [rsp+5B8h] [rbp+488h] BYREF
  __int128 v263; // [rsp+5C8h] [rbp+498h]
  char v264; // [rsp+5D8h] [rbp+4A8h]
  __int128 *v265; // [rsp+5E0h] [rbp+4B0h]
  __int128 v266; // [rsp+5E8h] [rbp+4B8h] BYREF
  __int128 v267; // [rsp+5F8h] [rbp+4C8h]
  char v268; // [rsp+608h] [rbp+4D8h]
  __int128 *v269; // [rsp+610h] [rbp+4E0h]
  __int128 v270; // [rsp+618h] [rbp+4E8h] BYREF
  __int128 v271; // [rsp+628h] [rbp+4F8h]
  char v272; // [rsp+638h] [rbp+508h]
  __int128 *v273; // [rsp+640h] [rbp+510h]
  __int128 v274; // [rsp+648h] [rbp+518h] BYREF
  __int128 v275; // [rsp+658h] [rbp+528h]
  char v276; // [rsp+668h] [rbp+538h]
  __int128 *v277; // [rsp+670h] [rbp+540h]
  __int64 v278; // [rsp+678h] [rbp+548h]
  _OWORD v279[2]; // [rsp+680h] [rbp+550h] BYREF
  _OWORD v280[2]; // [rsp+6A0h] [rbp+570h] BYREF
  __int128 v281; // [rsp+6C0h] [rbp+590h] BYREF
  __int128 v282; // [rsp+6D0h] [rbp+5A0h]
  char v283; // [rsp+6E0h] [rbp+5B0h]
  __int128 *v284; // [rsp+6E8h] [rbp+5B8h]
  __int128 v285; // [rsp+6F0h] [rbp+5C0h] BYREF
  __int128 v286; // [rsp+700h] [rbp+5D0h]
  char v287; // [rsp+710h] [rbp+5E0h]
  __int128 *v288; // [rsp+718h] [rbp+5E8h]
  __int128 v289; // [rsp+720h] [rbp+5F0h] BYREF
  __int128 v290; // [rsp+730h] [rbp+600h]
  char v291; // [rsp+740h] [rbp+610h]
  __int128 *v292; // [rsp+748h] [rbp+618h]
  __int128 v293; // [rsp+750h] [rbp+620h] BYREF
  __int128 v294; // [rsp+760h] [rbp+630h]
  char v295; // [rsp+770h] [rbp+640h]
  __int128 *v296; // [rsp+778h] [rbp+648h]
  _BYTE v297[32]; // [rsp+780h] [rbp+650h] BYREF
  _BYTE v298[32]; // [rsp+7A0h] [rbp+670h] BYREF
  _BYTE v299[32]; // [rsp+7C0h] [rbp+690h] BYREF
  __int64 v300; // [rsp+7E0h] [rbp+6B0h]
  _BYTE v301[32]; // [rsp+7E8h] [rbp+6B8h] BYREF
  _BYTE v302[32]; // [rsp+808h] [rbp+6D8h] BYREF
  _BYTE v303[32]; // [rsp+828h] [rbp+6F8h] BYREF
  _BYTE v304[32]; // [rsp+848h] [rbp+718h] BYREF
  _BYTE v305[32]; // [rsp+868h] [rbp+738h] BYREF
  _BYTE v306[32]; // [rsp+888h] [rbp+758h] BYREF
  _BYTE v307[32]; // [rsp+8A8h] [rbp+778h] BYREF
  _BYTE v308[32]; // [rsp+8C8h] [rbp+798h] BYREF
  _BYTE v309[32]; // [rsp+8E8h] [rbp+7B8h] BYREF
  _BYTE v310[32]; // [rsp+908h] [rbp+7D8h] BYREF
  _BYTE v311[32]; // [rsp+928h] [rbp+7F8h] BYREF
  _BYTE v312[32]; // [rsp+948h] [rbp+818h] BYREF
  _BYTE v313[48]; // [rsp+968h] [rbp+838h] BYREF
  __int128 v314; // [rsp+998h] [rbp+868h] BYREF
  __int128 v315; // [rsp+9A8h] [rbp+878h] BYREF
  void *v316[2]; // [rsp+9B8h] [rbp+888h] BYREF
  __int64 v317; // [rsp+9C8h] [rbp+898h]
  char v318; // [rsp+9D0h] [rbp+8A0h]
  __int128 v319; // [rsp+9D8h] [rbp+8A8h] BYREF
  __int128 v320; // [rsp+9E8h] [rbp+8B8h] BYREF
  _QWORD v321[3]; // [rsp+9F8h] [rbp+8C8h] BYREF
  unsigned __int64 v322; // [rsp+A10h] [rbp+8E0h]

  v278 = a2;
  v3 = a1;
  v167 = a1;
  v300 = a2;
  v4 = 0;
  LODWORD(v150) = 0;
  LODWORD(v151) = 0;
  v315 = 0;
  *(_OWORD *)v160 = 0;
  v5 = *(_QWORD *)(a2 + 8);
  if ( v5 )
  {
    v6 = *(_DWORD *)(v5 + 8);
    while ( v6 )
    {
      v7 = v6;
      v6 = _InterlockedCompareExchange((volatile signed __int32 *)(v5 + 8), v6 + 1, v6);
      if ( v7 == v6 )
      {
        v160[0] = *(void **)a2;
        v160[1] = *(void **)(a2 + 8);
        break;
      }
    }
  }
  std::dynamic_pointer_cast<Microsoft::Basix::Dct::LinkDataDisabled,Microsoft::Basix::Dct::LinkData>(&v315, v160);
  v8 = (volatile signed __int32 *)v160[1];
  if ( v160[1] )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v160[1] + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v8)(v8);
      if ( _InterlockedExchangeAdd(v8 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 8LL))(v8);
    }
  }
  if ( Microsoft::Basix::Dct::detail::BasicStateManagement::IsClosed((Microsoft::Basix::Dct::detail::BasicStateManagement *)v3) )
  {
    result = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v315 + 104) + 16LL))(*(_QWORD *)(v315 + 104));
    v10 = (volatile signed __int32 *)*((_QWORD *)&v315 + 1);
    if ( *((_QWORD *)&v315 + 1) )
    {
      result = (unsigned int)_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v315 + 1) + 8LL));
      if ( !(_DWORD)result )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v10)(v10);
        result = (unsigned int)_InterlockedDecrement(v10 + 3);
        if ( !(_DWORD)result )
          result = (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
      }
    }
    v11 = *(volatile signed __int32 **)(a2 + 8);
  }
  else
  {
    v154 = v3 + 229;
    if ( Mtx_lock((_Mtx_t)(v3 + 229)) )
      std::_Throw_Cpp_error(5);
    if ( *((_DWORD *)v3 + 477) == 0x7FFFFFFF )
    {
      *((_DWORD *)v3 + 477) = 2147483646;
      std::_Throw_Cpp_error(6);
    }
    Microsoft::Basix::Containers::IterationSafeStore<std::shared_ptr<Microsoft::Basix::Dct::LinkDataDisabled>,std::equal_to<std::shared_ptr<Microsoft::Basix::Dct::LinkDataDisabled>>>::insert(
      v3 + 191,
      &v315);
    v155 = (__int64 *)Microsoft::Basix::Containers::IterationSafeStore<std::shared_ptr<Microsoft::Basix::Dct::LinkDataDisabled>,std::equal_to<std::shared_ptr<Microsoft::Basix::Dct::LinkDataDisabled>>>::size(v3 + 191);
    v156 = 0;
    v157 = 0;
    std::string::_Construct<1,char const *>(&v156, "Microsoft::Basix::Dct.Smiles.LinkPoolSize", 41);
    v158 = 46;
    v12 = &v156;
    if ( *((_QWORD *)&v157 + 1) > 0xFu )
      v12 = (__int128 *)v156;
    v159 = v12;
    boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::put<unsigned __int64>(
      v3 + 120,
      &v156,
      &v155);
    std::string::_Tidy_deallocate(&v156);
    *(_DWORD *)(v315 + 152) = ++*((_DWORD *)v3 + 380);
    Microsoft::Basix::Containers::IterationSafeStore<std::shared_ptr<Microsoft::Basix::Dct::LinkDataV3>,std::equal_to<std::shared_ptr<Microsoft::Basix::Dct::LinkDataV3>>>::erase(
      v3 + 209,
      &v315);
    *((_BYTE *)v3 + 1505) = 0;
    Mtx_unlock((_Mtx_t)(v3 + 229));
    v319 = 0;
    v13 = v315;
    v14 = *(_QWORD *)(v315 + 104);
    *(_OWORD *)v163 = 0;
    v164 = 0;
    std::string::_Construct<1,char const *>(v163, "Microsoft::Basix::Dct.Smiles.AddLinkInfo", 40);
    Property = Microsoft::Basix::Dct::detail::IPropertyAware::GetProperty(v14 + 40, v316, v163);
    LOBYTE(v16) = v149[0];
    Microsoft::Basix::Containers::PTreeResult<boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>>::As(
      Property,
      &v319,
      v16);
    v17 = 0x40000000;
    boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(v316);
    std::string::_Tidy_deallocate(v163);
    v18 = *(_QWORD *)(v13 + 104);
    *(_OWORD *)v165 = 0;
    v166 = 0;
    std::string::_Construct<1,char const *>(v165, "Microsoft::Basix::Dct.Smiles.LinkType", 37);
    v19 = Microsoft::Basix::Dct::detail::IPropertyAware::GetProperty(v18 + 40, v160, v165);
    v153 = 0;
    LODWORD(v18) = boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get_value<enum Microsoft::Basix::Dct::ISmiles::LinkType>(
                     *(_QWORD *)(v19 + 16),
                     &v153);
    v153 = v18;
    boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(v160);
    std::string::_Tidy_deallocate(v165);
    *(_DWORD *)(v13 + 80) = v18;
    v156 = 0;
    v157 = 0;
    std::string::_Construct<1,char const *>(&v156, "Summary", 7);
    v158 = 46;
    v20 = &v156;
    if ( *((_QWORD *)&v157 + 1) > 0xFu )
      v20 = (__int128 *)v156;
    v159 = v20;
    boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get<char>(
      &v319,
      v321,
      &v156,
      &Str1);
    std::string::_Tidy_deallocate(&v156);
    *(_OWORD *)v316 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceCheckpoint>(v316);
    if ( v316[0] && *((_BYTE *)v316[0] + 128) )
    {
      v155 = v172;
      v21 = std::string::string(&v156, "\"");
      v22 = v321;
      if ( v322 > 0xF )
        v22 = (_QWORD *)v321[0];
      v23 = std::string::string(v299, "\"");
      v24 = std::string::string(v298, ":");
      v25 = std::string::string(v297, "\"");
      v26 = std::string::string(v311, "\"");
      v27 = std::operator+<char>(v310, v26, "AdditionalInfo");
      LOBYTE(v28) = v149[0];
      std::string::string(&v178, v28, v27, v25);
      LOBYTE(v29) = v149[0];
      std::string::string(&v182, v29, &v178, v24);
      LOBYTE(v30) = v149[0];
      std::string::string(&v186, v30, &v182, v23);
      v31 = std::operator+<char>(v309, &v186, v22);
      LOBYTE(v32) = v149[0];
      std::string::string(v172, v32, v31, v21);
      v154 = v174;
      v3 = v167;
      std::_Integral_to_string<char,unsigned int>(&v190, *((unsigned int *)v167 + 373));
      v33 = std::string::string(v308, ":");
      v34 = std::string::string(v307, "\"");
      v35 = std::string::string(v312, "\"");
      v36 = std::operator+<char>(v306, v35, "NonIceDoR");
      LOBYTE(v37) = v149[0];
      std::string::string(&v194, v37, v36, v34);
      LOBYTE(v38) = v149[0];
      std::string::string(&v198, v38, &v194, v33);
      LOBYTE(v39) = v149[0];
      std::string::string(v174, v39, &v198, &v190);
      v167 = v176;
      std::_Integral_to_string<char,unsigned int>(&v202, *((unsigned int *)v3 + 372));
      v40 = std::string::string(v305, ":");
      v41 = std::string::string(v304, "\"");
      v42 = std::string::string(v303, "\"");
      v43 = std::operator+<char>(v302, v42, "IceDoR");
      LOBYTE(v44) = v149[0];
      std::string::string(&v206, v44, v43, v41);
      LOBYTE(v45) = v149[0];
      std::string::string(v165, v45, &v206, v40);
      LOBYTE(v46) = v149[0];
      std::string::string(v176, v46, v165, &v202);
      v151 = v168;
      std::_Integral_to_string<char,int>(v163, v153);
      v47 = std::string::string(v301, ":");
      v48 = std::string::string(&v274, "\"");
      v49 = std::string::string(&v270, "\"");
      v50 = std::operator+<char>(&v266, v49, "LinkType");
      LOBYTE(v51) = v149[0];
      std::string::string(v279, v51, v50, v48);
      LOBYTE(v52) = v149[0];
      std::string::string(v280, v52, v279, v47);
      LOBYTE(v53) = v149[0];
      std::string::string(v168, v53, v280, v163);
      v150 = v170;
      v54 = Microsoft::Basix::Containers::IterationSafeStore<std::shared_ptr<Microsoft::Basix::Dct::LinkDataDisabled>,std::equal_to<std::shared_ptr<Microsoft::Basix::Dct::LinkDataDisabled>>>::size(v3 + 191);
      std::_Integral_to_string<char,unsigned __int64>(v246, v54);
      v55 = std::string::string(&v262, ":");
      v56 = std::string::string(&v258, "\"");
      v57 = std::string::string(&v254, "\"");
      v58 = std::operator+<char>(&v218, v57, "linksSize");
      LOBYTE(v59) = v149[0];
      std::string::string(v247, v59, v58, v56);
      LOBYTE(v60) = v149[0];
      std::string::string(v248, v60, v247, v55);
      LOBYTE(v61) = v149[0];
      std::string::string(v170, v61, v248, v246);
      v13 = v315;
      std::_Integral_to_string<char,unsigned int>(v249, *(unsigned int *)(v315 + 152));
      v62 = std::string::string(&v214, ":");
      v63 = std::string::string(&v222, "\"");
      v64 = std::string::string(&v226, "\"");
      v65 = std::operator+<char>(&v210, v64, "LinkId");
      LOBYTE(v66) = v149[0];
      std::string::string(v250, v66, v65, v63);
      LOBYTE(v67) = v149[0];
      std::string::string(v251, v67, v250, v62);
      LOBYTE(v68) = v149[0];
      std::string::string(v252, v68, v251, v249);
      Microsoft::Basix::Instrumentation::TraceManager::TraceCheckpointMessage<Microsoft::Basix::TraceCheckpoint,std::string,std::string,std::string,std::string,std::string,std::string>(
        (int)v316,
        (int)"RD_CHECKPOINT",
        0,
        (int)"Smiles",
        "AddLink",
        "AddLink",
        (__int64)v252,
        (__int64)v170,
        (__int64)v168,
        (__int64)v176,
        (__int64)v174,
        (__int64)v172);
      std::string::_Tidy_deallocate(v251);
      std::string::_Tidy_deallocate(v250);
      std::string::_Tidy_deallocate(&v210);
      std::string::_Tidy_deallocate(&v226);
      std::string::_Tidy_deallocate(&v222);
      std::string::_Tidy_deallocate(&v214);
      std::string::_Tidy_deallocate(v249);
      std::string::_Tidy_deallocate(v248);
      std::string::_Tidy_deallocate(v247);
      std::string::_Tidy_deallocate(&v218);
      std::string::_Tidy_deallocate(&v254);
      std::string::_Tidy_deallocate(&v258);
      std::string::_Tidy_deallocate(&v262);
      std::string::_Tidy_deallocate(v246);
      std::string::_Tidy_deallocate(v280);
      std::string::_Tidy_deallocate(v279);
      std::string::_Tidy_deallocate(&v266);
      std::string::_Tidy_deallocate(&v270);
      std::string::_Tidy_deallocate(&v274);
      std::string::_Tidy_deallocate(v301);
      std::string::_Tidy_deallocate(v163);
      std::string::_Tidy_deallocate(v165);
      std::string::_Tidy_deallocate(&v206);
      std::string::_Tidy_deallocate(v302);
      std::string::_Tidy_deallocate(v303);
      std::string::_Tidy_deallocate(v304);
      std::string::_Tidy_deallocate(v305);
      std::string::_Tidy_deallocate(&v202);
      std::string::_Tidy_deallocate(&v198);
      std::string::_Tidy_deallocate(&v194);
      std::string::_Tidy_deallocate(v306);
      std::string::_Tidy_deallocate(v312);
      std::string::_Tidy_deallocate(v307);
      std::string::_Tidy_deallocate(v308);
      std::string::_Tidy_deallocate(&v190);
      std::string::_Tidy_deallocate(v309);
      std::string::_Tidy_deallocate(&v186);
      std::string::_Tidy_deallocate(&v182);
      std::string::_Tidy_deallocate(&v178);
      std::string::_Tidy_deallocate(v310);
      std::string::_Tidy_deallocate(v311);
      std::string::_Tidy_deallocate(v297);
      std::string::_Tidy_deallocate(v298);
      std::string::_Tidy_deallocate(v299);
      std::string::_Tidy_deallocate(&v156);
    }
    v69 = (volatile signed __int32 *)v316[1];
    if ( v316[1] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v316[1] + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v69)(v69);
        if ( _InterlockedExchangeAdd(v69 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v69 + 8LL))(v69);
      }
    }
    v320 = 0u;
    v70 = operator new(0x20u);
    v160[0] = v70;
    if ( v70 )
      v71 = __0__multi_index_container_U__pair___CBV__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__V__basic_ptree_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__Vany_boost__U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___2__property_tree_boost___std__U__indexed_by_U__sequenced_U__tag_Una_mpl_boost__U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123__multi_index_boost___multi_index_boost__U__ordered_non_unique_U__tag_Uby_name_subs___basic_ptree_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__Vany_boost__U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___2__property_tree_boost__Una_mpl_5_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675__multi_index_boost__U__member_U__pair___CBV__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__V__basic_ptree_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__Vany_boost__U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___2__property_tree_boost___std____CBV__basic_string_DU__char_traits_D_std__V__allocator_D_2__2__0A__23_U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___std___23_Una_mpl_3_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563__multi_index_boost__V__allocator_U__pair___CBV__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__V__basic_ptree_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__Vany_boost__U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___2__property_tree_boost___std___2__multi_index_boost__QEAA_XZ(v70);
    else
      v71 = 0;
    *((_QWORD *)&v320 + 1) = v71;
    v314 = 0;
    v156 = 0;
    v157 = 0;
    std::string::_Construct<1,char const *>(&v156, "Components", 10);
    v158 = 46;
    v72 = &v156;
    if ( *((_QWORD *)&v157 + 1) > 0xFu )
      v72 = (__int128 *)v156;
    v159 = v72;
    child = boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get_child(
              &v319,
              &v156,
              &v320);
    boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::basic_ptree<std::string,boost::any,std::less<std::string>>(
      &v314,
      child);
    std::string::_Tidy_deallocate(&v156);
    *(_OWORD *)v316 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(v316);
    if ( v316[0] && *((_BYTE *)v316[0] + 128) )
    {
      std::string::string(v170, (const char *)&Str1);
      LOBYTE(v75) = v149[0];
      LOBYTE(v76) = 46;
      boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>>::string_path<std::string,boost::property_tree::id_translator<std::string>>(
        &v230,
        "TransportIPClient",
        v76,
        v75);
      v77 = (__int64 *)boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get<std::string>(
                         &v314,
                         v297,
                         &v230,
                         v170);
      v154 = v77;
      if ( (unsigned __int64)v77[3] > 0xF )
        v154 = (__int64 *)*v77;
      std::string::string(v168, (const char *)&Str1);
      LOBYTE(v78) = v149[0];
      LOBYTE(v79) = 46;
      boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>>::string_path<std::string,boost::property_tree::id_translator<std::string>>(
        &v234,
        "TransportIPServer",
        v79,
        v78);
      v80 = (__int64 *)boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get<std::string>(
                         &v314,
                         v298,
                         &v234,
                         v168);
      v151 = v80;
      if ( (unsigned __int64)v80[3] > 0xF )
        v151 = (__int64 *)*v80;
      std::string::string(v176, (const char *)&Str1);
      LOBYTE(v81) = v149[0];
      LOBYTE(v82) = 46;
      boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>>::string_path<std::string,boost::property_tree::id_translator<std::string>>(
        &v238,
        "TransportTypeClient",
        v82,
        v81);
      v83 = (__int64 *)boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get<std::string>(
                         &v314,
                         v299,
                         &v238,
                         v176);
      v150 = v83;
      if ( (unsigned __int64)v83[3] > 0xF )
        v150 = (__int64 *)*v83;
      std::string::string(v174, (const char *)&Str1);
      LOBYTE(v84) = v149[0];
      LOBYTE(v85) = 46;
      boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>>::string_path<std::string,boost::property_tree::id_translator<std::string>>(
        &v242,
        "TransportTypeServer",
        v85,
        v84);
      v86 = (__int64 *)boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get<std::string>(
                         &v314,
                         &v156,
                         &v242,
                         v174);
      v155 = v86;
      if ( (unsigned __int64)v86[3] > 0xF )
        v155 = (__int64 *)*v86;
      v89 = v321;
      if ( v322 > 0xF )
        v89 = (_QWORD *)v321[0];
      v90 = *((_DWORD *)v3 + 373);
      v91 = *((_DWORD *)v3 + 372);
      v92 = *(_DWORD *)(v13 + 152);
      std::string::string(
        v172,
        "Checkpoint.SMILES.LinkAdded(%d),IceDoR(%d)|nonIceDor(%d):%s, TransportTypeOnServer=%s, TransportTypeOnClient=%s,"
        " TransportIPOnServer=%s, TransportIPOnClient=%s",
        v87,
        v88,
        v143,
        Str,
        v145,
        v146,
        v147,
        v148);
      Microsoft::Basix::Instrumentation::TraceManager::TraceMessage<Microsoft::Basix::TraceNormal,unsigned int,unsigned int,unsigned int,char const *,char const *,char const *,char const *,char const *>(
        (unsigned int)v316,
        (unsigned int)"BASIX_DCT",
        (unsigned int)v172,
        v92,
        v91,
        v90,
        (__int64)v89,
        (__int64)v155,
        (__int64)v150,
        (__int64)v151,
        (__int64)v154);
      std::string::_Tidy_deallocate(v172);
      std::string::_Tidy_deallocate(&v156);
      std::string::_Tidy_deallocate(&v242);
      std::string::_Tidy_deallocate(v174);
      std::string::_Tidy_deallocate(v299);
      std::string::_Tidy_deallocate(&v238);
      std::string::_Tidy_deallocate(v176);
      std::string::_Tidy_deallocate(v298);
      std::string::_Tidy_deallocate(&v234);
      std::string::_Tidy_deallocate(v168);
      std::string::_Tidy_deallocate(v297);
      std::string::_Tidy_deallocate(&v230);
      std::string::_Tidy_deallocate(v170);
    }
    v93 = (volatile signed __int32 *)v316[1];
    if ( v316[1] )
    {
      if ( !_InterlockedDecrement((volatile signed __int32 *)v316[1] + 2) )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v93)(v93);
        if ( !_InterlockedDecrement(v93 + 3) )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v93 + 8LL))(v93);
      }
    }
    if ( *((_BYTE *)v3 + 1280) )
    {
      LODWORD(v163[0]) = 2;
      v163[1] = (void *)&Str1;
      *(_QWORD *)&v164 = 0;
      BYTE8(v164) = 0;
      *(_OWORD *)v172 = 0;
      v173 = 0;
      std::string::_Construct<1,char const *>(v172, (const char *)&Str1, 0);
      LODWORD(v150) = 3;
      v242 = 0;
      v243 = 0;
      std::string::_Construct<1,char const *>(&v242, "NatIPServer", 11);
      v244 = 46;
      v94 = &v242;
      if ( *((_QWORD *)&v243 + 1) > 0xFu )
        v94 = (__int128 *)v242;
      v245 = v94;
      LODWORD(v150) = 7;
      v95 = boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get<std::string>(
              &v314,
              v301,
              &v242,
              v172);
      LODWORD(v165[0]) = 2;
      v96 = (void *)v95;
      if ( *(_QWORD *)(v95 + 24) > 0xFu )
        v96 = *(void **)v95;
      v165[1] = v96;
      *(_QWORD *)&v166 = *(_QWORD *)(v95 + 16);
      BYTE8(v166) = 0;
      *(_OWORD *)v174 = 0;
      v175 = 0;
      std::string::_Construct<1,char const *>(v174, (const char *)&Str1, 0);
      LODWORD(v150) = 63;
      v238 = 0;
      v239 = 0;
      std::string::_Construct<1,char const *>(&v238, "NatIPClient", 11);
      v240 = 46;
      v97 = &v238;
      if ( *((_QWORD *)&v239 + 1) > 0xFu )
        v97 = (__int128 *)v238;
      v241 = v97;
      LODWORD(v150) = 127;
      v98 = boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get<std::string>(
              &v314,
              v302,
              &v238,
              v174);
      v206 = 2;
      v99 = (void *)v98;
      if ( *(_QWORD *)(v98 + 24) > 0xFu )
        v99 = *(void **)v98;
      v207 = v99;
      v208 = *(_QWORD *)(v98 + 16);
      v209 = 0;
      *(_OWORD *)v176 = 0;
      v177 = 0;
      std::string::_Construct<1,char const *>(v176, (const char *)&Str1, 0);
      LODWORD(v150) = 1023;
      v234 = 0;
      v235 = 0;
      std::string::_Construct<1,char const *>(&v234, "TransportIPServer", 17);
      v236 = 46;
      v100 = &v234;
      if ( *((_QWORD *)&v235 + 1) > 0xFu )
        v100 = (__int128 *)v234;
      v237 = v100;
      LODWORD(v150) = 2047;
      v101 = boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get<std::string>(
               &v314,
               v303,
               &v234,
               v176);
      v202 = 2;
      v102 = (void *)v101;
      if ( *(_QWORD *)(v101 + 24) > 0xFu )
        v102 = *(void **)v101;
      v203 = v102;
      v204 = *(_QWORD *)(v101 + 16);
      v205 = 0;
      *(_OWORD *)v168 = 0;
      v169 = 0;
      std::string::_Construct<1,char const *>(v168, (const char *)&Str1, 0);
      LODWORD(v150) = 0x3FFF;
      v230 = 0;
      v231 = 0;
      std::string::_Construct<1,char const *>(&v230, "TransportIPClient", 17);
      v232 = 46;
      v103 = &v230;
      if ( *((_QWORD *)&v231 + 1) > 0xFu )
        v103 = (__int128 *)v230;
      v233 = v103;
      LODWORD(v150) = 0x7FFF;
      v104 = boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get<std::string>(
               &v314,
               v304,
               &v230,
               v168);
      v198 = 2;
      v105 = (void *)v104;
      if ( *(_QWORD *)(v104 + 24) > 0xFu )
        v105 = *(void **)v104;
      v199 = v105;
      v200 = *(_QWORD *)(v104 + 16);
      v201 = 0;
      LODWORD(v150) = 0x1FFFF;
      v106 = boost::lexical_cast<std::string,unsigned int>(v305, v3 + 241);
      v194 = 2;
      v107 = (void *)v106;
      if ( *(_QWORD *)(v106 + 24) > 0xFu )
        v107 = *(void **)v106;
      v195 = v107;
      v196 = *(_QWORD *)(v106 + 16);
      v197 = 0;
      *(_OWORD *)v170 = 0;
      v171 = 0;
      std::string::_Construct<1,char const *>(v170, (const char *)&Str1, 0);
      LODWORD(v150) = 0xFFFFF;
      v293 = 0;
      v294 = 0;
      std::string::_Construct<1,char const *>(&v293, "GatewayRegion", 13);
      v295 = 46;
      v108 = &v293;
      if ( *((_QWORD *)&v294 + 1) > 0xFu )
        v108 = (__int128 *)v293;
      v296 = v108;
      LODWORD(v150) = 0x1FFFFF;
      v109 = boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get<std::string>(
               &v314,
               v306,
               &v293,
               v170);
      v190 = 2;
      v110 = (void *)v109;
      if ( *(_QWORD *)(v109 + 24) > 0xFu )
        v110 = *(void **)v109;
      v191 = v110;
      v192 = *(_QWORD *)(v109 + 16);
      v193 = 0;
      *(_OWORD *)v252 = 0;
      v253 = 0;
      std::string::_Construct<1,char const *>(v252, (const char *)&Str1, 0);
      LOBYTE(v111) = v149[0];
      LOBYTE(v112) = 46;
      boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>>::string_path<std::string,boost::property_tree::id_translator<std::string>>(
        v313,
        "GatewayCluster",
        v112,
        v111);
      LODWORD(v150) = 0x1FFFFFF;
      v113 = boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get<std::string>(
               &v314,
               v312,
               v313,
               v252);
      v186 = 2;
      v114 = (void *)v113;
      if ( *(_QWORD *)(v113 + 24) > 0xFu )
        v114 = *(void **)v113;
      v187 = v114;
      v188 = *(_QWORD *)(v113 + 16);
      v189 = 0;
      memset(v251, 0, sizeof(v251));
      std::string::_Construct<1,char const *>(v251, (const char *)&Str1, 0);
      LODWORD(v150) = 0xFFFFFFF;
      v289 = 0;
      v290 = 0;
      std::string::_Construct<1,char const *>(&v289, "GatewayInstanceID", 17);
      v291 = 46;
      v115 = &v289;
      if ( *((_QWORD *)&v290 + 1) > 0xFu )
        v115 = (__int128 *)v289;
      v292 = v115;
      LODWORD(v150) = 0x1FFFFFFF;
      v116 = boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get<std::string>(
               &v314,
               v307,
               &v289,
               v251);
      v182 = 2;
      v117 = (void *)v116;
      if ( *(_QWORD *)(v116 + 24) > 0xFu )
        v117 = *(void **)v116;
      v183 = v117;
      v184 = *(_QWORD *)(v116 + 16);
      v185 = 0;
      memset(v250, 0, sizeof(v250));
      std::string::_Construct<1,char const *>(v250, (const char *)&Str1, 0);
      v4 = -1;
      LODWORD(v150) = -1;
      v285 = 0;
      v286 = 0;
      std::string::_Construct<1,char const *>(&v285, "GatewayConnectionID", 19);
      v287 = 46;
      v118 = &v285;
      if ( *((_QWORD *)&v286 + 1) > 0xFu )
        v118 = (__int128 *)v285;
      v288 = v118;
      LODWORD(v151) = 1073741825;
      v119 = boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get<std::string>(
               &v314,
               v308,
               &v285,
               v250);
      v178 = 2;
      v120 = (void *)v119;
      if ( *(_QWORD *)(v119 + 24) > 0xFu )
        v120 = *(void **)v119;
      v179 = v120;
      v180 = *(_QWORD *)(v119 + 16);
      v181 = 0;
      memset(v249, 0, sizeof(v249));
      std::string::_Construct<1,char const *>(v249, (const char *)&Str1, 0);
      LODWORD(v151) = 1073741839;
      v281 = 0;
      v282 = 0;
      std::string::_Construct<1,char const *>(&v281, "TurnServerRegionClient", 22);
      v283 = 46;
      v121 = &v281;
      if ( *((_QWORD *)&v282 + 1) > 0xFu )
        v121 = (__int128 *)v281;
      v284 = v121;
      LODWORD(v151) = 1073741855;
      v122 = boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get<std::string>(
               &v314,
               v309,
               &v281,
               v249);
      v210 = 2;
      v123 = (void *)v122;
      if ( *(_QWORD *)(v122 + 24) > 0xFu )
        v123 = *(void **)v122;
      v211 = v123;
      v212 = *(_QWORD *)(v122 + 16);
      v213 = 0;
      memset(v248, 0, sizeof(v248));
      std::string::_Construct<1,char const *>(v248, (const char *)&Str1, 0);
      LODWORD(v151) = 1073742079;
      v254 = 0;
      v255 = 0;
      std::string::_Construct<1,char const *>(&v254, "TurnServerIPClient", 18);
      v256 = 46;
      v124 = &v254;
      if ( *((_QWORD *)&v255 + 1) > 0xFu )
        v124 = (__int128 *)v254;
      v257 = v124;
      LODWORD(v151) = 1073742335;
      v125 = boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get<std::string>(
               &v314,
               v310,
               &v254,
               v248);
      v226 = 2;
      v126 = (void *)v125;
      if ( *(_QWORD *)(v125 + 24) > 0xFu )
        v126 = *(void **)v125;
      v227 = v126;
      v228 = *(_QWORD *)(v125 + 16);
      v229 = 0;
      memset(v247, 0, sizeof(v247));
      std::string::_Construct<1,char const *>(v247, (const char *)&Str1, 0);
      LODWORD(v151) = 1073745919;
      v258 = 0;
      v259 = 0;
      std::string::_Construct<1,char const *>(&v258, "TurnServerRegionServer", 22);
      v260 = 46;
      v127 = &v258;
      if ( *((_QWORD *)&v259 + 1) > 0xFu )
        v127 = (__int128 *)v258;
      v261 = v127;
      LODWORD(v151) = 1073750015;
      v128 = boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get<std::string>(
               &v314,
               v311,
               &v258,
               v247);
      v222 = 2;
      v129 = (void *)v128;
      if ( *(_QWORD *)(v128 + 24) > 0xFu )
        v129 = *(void **)v128;
      v223 = v129;
      v224 = *(_QWORD *)(v128 + 16);
      v225 = 0;
      memset(v246, 0, sizeof(v246));
      std::string::_Construct<1,char const *>(v246, (const char *)&Str1, 0);
      LODWORD(v151) = 1073807359;
      v262 = 0;
      v263 = 0;
      std::string::_Construct<1,char const *>(&v262, "TurnServerIPServer", 18);
      v264 = 46;
      v130 = &v262;
      if ( *((_QWORD *)&v263 + 1) > 0xFu )
        v130 = (__int128 *)v262;
      v265 = v130;
      LODWORD(v151) = 1073872895;
      v131 = boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get<std::string>(
               &v314,
               v297,
               &v262,
               v246);
      v214 = 2;
      v132 = (void *)v131;
      if ( *(_QWORD *)(v131 + 24) > 0xFu )
        v132 = *(void **)v131;
      v215 = v132;
      v216 = *(_QWORD *)(v131 + 16);
      v217 = 0;
      LODWORD(v151) = 1074266111;
      v152[0] = 0;
      v266 = 0;
      v267 = 0;
      std::string::_Construct<1,char const *>(&v266, "UPNP", 4);
      v268 = 46;
      v133 = &v266;
      if ( *((_QWORD *)&v267 + 1) > 0xFu )
        v133 = (__int128 *)v266;
      v269 = v133;
      v149[0] = boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get<bool>(
                  &v314,
                  &v266,
                  v152);
      memset(v280, 0, sizeof(v280));
      std::string::_Construct<1,char const *>(v280, (const char *)&Str1, 0);
      LODWORD(v151) = 1075838975;
      v270 = 0;
      v271 = 0;
      std::string::_Construct<1,char const *>(&v270, "TransportTypeServer", 19);
      v272 = 46;
      v134 = &v270;
      if ( *((_QWORD *)&v271 + 1) > 0xFu )
        v134 = (__int128 *)v270;
      v273 = v134;
      LODWORD(v151) = 1077936127;
      v135 = boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get<std::string>(
               &v314,
               v298,
               &v270,
               v280);
      v218 = 2;
      v136 = (void *)v135;
      if ( *(_QWORD *)(v135 + 24) > 0xFu )
        v136 = *(void **)v135;
      v219 = v136;
      v220 = *(_QWORD *)(v135 + 16);
      v221 = 0;
      memset(v279, 0, sizeof(v279));
      std::string::_Construct<1,char const *>(v279, (const char *)&Str1, 0);
      LODWORD(v151) = 1107296255;
      v274 = 0;
      v275 = 0;
      std::string::_Construct<1,char const *>(&v274, "TransportTypeClient", 19);
      v276 = 46;
      v137 = &v274;
      if ( *((_QWORD *)&v275 + 1) > 0xFu )
        v137 = (__int128 *)v274;
      v277 = v137;
      LODWORD(v151) = 1140850687;
      v138 = boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get<std::string>(
               &v314,
               v299,
               &v274,
               v279);
      LODWORD(v160[0]) = 2;
      v139 = (void *)v138;
      if ( *(_QWORD *)(v138 + 24) > 0xFu )
        v139 = *(void **)v138;
      v160[1] = v139;
      v161 = *(_QWORD *)(v138 + 16);
      v162 = 0;
      LODWORD(v151) = 1342177279;
      v140 = Microsoft::Basix::ToString<enum Microsoft::Basix::Dct::ISmiles::LinkType>(&v156, &v153, 0, 6);
      LODWORD(v316[0]) = 2;
      v141 = (void *)v140;
      if ( *(_QWORD *)(v140 + 24) > 0xFu )
        v141 = *(void **)v140;
      v316[1] = v141;
      v317 = *(_QWORD *)(v140 + 16);
      v318 = 0;
      v17 = 0x7FFFFFFF;
      LODWORD(v154) = *(_DWORD *)(v315 + 152);
      Microsoft::Basix::Instrumentation::MultiLinkAdd::LogInterface::operator()<boost::container::small_vector<std::shared_ptr<Microsoft::Basix::Instrumentation::EventLogger>,4,void,void> const &>(
        (_DWORD)v3 + 1408,
        (_DWORD)v3 + 1288,
        (unsigned int)&v154,
        (unsigned int)v316,
        (__int64)v160,
        (__int64)&v218,
        (__int64)v149,
        (__int64)&v214,
        (__int64)&v222,
        (__int64)&v226,
        (__int64)&v210,
        (__int64)&v178,
        (__int64)&v182,
        (__int64)&v186,
        (__int64)&v190,
        (__int64)&v194,
        (__int64)&v198,
        (__int64)&v202,
        (__int64)&v206,
        (__int64)v165,
        (__int64)v163);
    }
    if ( (v17 & 0x20000000) != 0 )
    {
      v17 &= ~0x20000000u;
      if ( v318 )
        operator delete(v316[1], v74);
    }
    if ( (v17 & 0x10000000) != 0 )
    {
      v17 &= ~0x10000000u;
      std::string::_Tidy_deallocate(&v156);
    }
    if ( (v17 & 0x8000000) != 0 )
    {
      v17 &= ~0x8000000u;
      if ( v162 )
        operator delete(v160[1], v74);
    }
    if ( (v17 & 0x4000000) != 0 )
    {
      v17 &= ~0x4000000u;
      std::string::_Tidy_deallocate(v299);
    }
    if ( (v17 & 0x2000000) != 0 )
    {
      v17 &= ~0x2000000u;
      std::string::_Tidy_deallocate(&v274);
    }
    if ( (v17 & 0x1000000) != 0 )
    {
      v17 &= ~0x1000000u;
      std::string::_Tidy_deallocate(v279);
    }
    if ( (v17 & 0x800000) != 0 )
    {
      v17 &= ~0x800000u;
      if ( v221 )
        operator delete(v219, v74);
    }
    if ( (v17 & 0x400000) != 0 )
    {
      v17 &= ~0x400000u;
      std::string::_Tidy_deallocate(v298);
    }
    if ( (v17 & 0x200000) != 0 )
    {
      v17 &= ~0x200000u;
      std::string::_Tidy_deallocate(&v270);
    }
    if ( (v17 & 0x100000) != 0 )
    {
      v17 &= ~0x100000u;
      std::string::_Tidy_deallocate(v280);
    }
    if ( (v17 & 0x80000) != 0 )
    {
      v17 &= ~0x80000u;
      std::string::_Tidy_deallocate(&v266);
    }
    if ( (v17 & 0x40000) != 0 )
    {
      v17 &= ~0x40000u;
      if ( v217 )
        operator delete(v215, v74);
    }
    if ( (v17 & 0x20000) != 0 )
    {
      v17 &= ~0x20000u;
      std::string::_Tidy_deallocate(v297);
    }
    if ( (v17 & 0x10000) != 0 )
      std::string::_Tidy_deallocate(&v262);
    if ( (v17 & 0x8000) != 0 )
    {
      LOWORD(v17) = v17 & 0x7FFF;
      std::string::_Tidy_deallocate(v246);
    }
    if ( (v17 & 0x4000) != 0 )
    {
      LOWORD(v17) = v17 & 0xBFFF;
      if ( v225 )
        operator delete(v223, v74);
    }
    if ( (v17 & 0x2000) != 0 )
    {
      LOWORD(v17) = v17 & 0xDFFF;
      std::string::_Tidy_deallocate(v311);
    }
    if ( (v17 & 0x1000) != 0 )
    {
      LOWORD(v17) = v17 & 0xEFFF;
      std::string::_Tidy_deallocate(&v258);
    }
    if ( (v17 & 0x800) != 0 )
    {
      LOWORD(v17) = v17 & 0xF7FF;
      std::string::_Tidy_deallocate(v247);
    }
    if ( (v17 & 0x400) != 0 )
    {
      LOWORD(v17) = v17 & 0xFBFF;
      if ( v229 )
        operator delete(v227, v74);
    }
    if ( (v17 & 0x200) != 0 )
    {
      LOWORD(v17) = v17 & 0xFDFF;
      std::string::_Tidy_deallocate(v310);
    }
    if ( (v17 & 0x100) != 0 )
      std::string::_Tidy_deallocate(&v254);
    if ( (v17 & 0x80u) != 0 )
    {
      LOBYTE(v17) = v17 & 0x7F;
      std::string::_Tidy_deallocate(v248);
    }
    if ( (v17 & 0x40) != 0 )
    {
      LOBYTE(v17) = v17 & 0xBF;
      if ( v213 )
        operator delete(v211, v74);
    }
    if ( (v17 & 0x20) != 0 )
    {
      LOBYTE(v17) = v17 & 0xDF;
      std::string::_Tidy_deallocate(v309);
    }
    if ( (v17 & 0x10) != 0 )
    {
      LOBYTE(v17) = v17 & 0xEF;
      std::string::_Tidy_deallocate(&v281);
    }
    if ( (v17 & 8) != 0 )
    {
      LOBYTE(v17) = v17 & 0xF7;
      std::string::_Tidy_deallocate(v249);
    }
    if ( (v17 & 4) != 0 )
    {
      LOBYTE(v17) = v17 & 0xFB;
      if ( v181 )
        operator delete(v179, v74);
    }
    if ( (v17 & 2) != 0 )
    {
      LOBYTE(v17) = v17 & 0xFD;
      std::string::_Tidy_deallocate(v308);
    }
    if ( (v17 & 1) != 0 )
      std::string::_Tidy_deallocate(&v285);
    if ( v4 < 0 )
    {
      v4 &= ~0x80000000;
      std::string::_Tidy_deallocate(v250);
    }
    if ( (v4 & 0x40000000) != 0 )
    {
      v4 &= ~0x40000000u;
      if ( v185 )
        operator delete(v183, v74);
    }
    if ( (v4 & 0x20000000) != 0 )
    {
      v4 &= ~0x20000000u;
      std::string::_Tidy_deallocate(v307);
    }
    if ( (v4 & 0x10000000) != 0 )
    {
      v4 &= ~0x10000000u;
      std::string::_Tidy_deallocate(&v289);
    }
    if ( (v4 & 0x8000000) != 0 )
    {
      v4 &= ~0x8000000u;
      std::string::_Tidy_deallocate(v251);
    }
    if ( (v4 & 0x4000000) != 0 )
    {
      v4 &= ~0x4000000u;
      if ( v189 )
        operator delete(v187, v74);
    }
    if ( (v4 & 0x2000000) != 0 )
    {
      v4 &= ~0x2000000u;
      std::string::_Tidy_deallocate(v312);
    }
    if ( (v4 & 0x1000000) != 0 )
    {
      v4 &= ~0x1000000u;
      std::string::_Tidy_deallocate(v313);
    }
    if ( (v4 & 0x800000) != 0 )
    {
      v4 &= ~0x800000u;
      std::string::_Tidy_deallocate(v252);
    }
    if ( (v4 & 0x400000) != 0 )
    {
      v4 &= ~0x400000u;
      if ( v193 )
        operator delete(v191, v74);
    }
    if ( (v4 & 0x200000) != 0 )
    {
      v4 &= ~0x200000u;
      std::string::_Tidy_deallocate(v306);
    }
    if ( (v4 & 0x100000) != 0 )
    {
      v4 &= ~0x100000u;
      std::string::_Tidy_deallocate(&v293);
    }
    if ( (v4 & 0x80000) != 0 )
    {
      v4 &= ~0x80000u;
      std::string::_Tidy_deallocate(v170);
    }
    if ( (v4 & 0x40000) != 0 )
    {
      v4 &= ~0x40000u;
      if ( v197 )
        operator delete(v195, v74);
    }
    if ( (v4 & 0x20000) != 0 )
    {
      v4 &= ~0x20000u;
      std::string::_Tidy_deallocate(v305);
    }
    if ( (v4 & 0x10000) != 0 && v201 )
      operator delete(v199, v74);
    if ( (v4 & 0x8000) != 0 )
    {
      LOWORD(v4) = v4 & 0x7FFF;
      std::string::_Tidy_deallocate(v304);
    }
    if ( (v4 & 0x4000) != 0 )
    {
      LOWORD(v4) = v4 & 0xBFFF;
      std::string::_Tidy_deallocate(&v230);
    }
    if ( (v4 & 0x2000) != 0 )
    {
      LOWORD(v4) = v4 & 0xDFFF;
      std::string::_Tidy_deallocate(v168);
    }
    if ( (v4 & 0x1000) != 0 )
    {
      LOWORD(v4) = v4 & 0xEFFF;
      if ( v205 )
        operator delete(v203, v74);
    }
    if ( (v4 & 0x800) != 0 )
    {
      LOWORD(v4) = v4 & 0xF7FF;
      std::string::_Tidy_deallocate(v303);
    }
    if ( (v4 & 0x400) != 0 )
    {
      LOWORD(v4) = v4 & 0xFBFF;
      std::string::_Tidy_deallocate(&v234);
    }
    if ( (v4 & 0x200) != 0 )
    {
      LOWORD(v4) = v4 & 0xFDFF;
      std::string::_Tidy_deallocate(v176);
    }
    if ( (v4 & 0x100) != 0 && v209 )
      operator delete(v207, v74);
    if ( (v4 & 0x80u) != 0 )
    {
      LOBYTE(v4) = v4 & 0x7F;
      std::string::_Tidy_deallocate(v302);
    }
    if ( (v4 & 0x40) != 0 )
    {
      LOBYTE(v4) = v4 & 0xBF;
      std::string::_Tidy_deallocate(&v238);
    }
    if ( (v4 & 0x20) != 0 )
    {
      LOBYTE(v4) = v4 & 0xDF;
      std::string::_Tidy_deallocate(v174);
    }
    if ( (v4 & 0x10) != 0 )
    {
      LOBYTE(v4) = v4 & 0xEF;
      if ( BYTE8(v166) )
        operator delete(v165[1], v74);
    }
    if ( (v4 & 8) != 0 )
    {
      LOBYTE(v4) = v4 & 0xF7;
      std::string::_Tidy_deallocate(v301);
    }
    if ( (v4 & 4) != 0 )
    {
      LOBYTE(v4) = v4 & 0xFB;
      std::string::_Tidy_deallocate(&v242);
    }
    if ( (v4 & 2) != 0 )
    {
      LOBYTE(v4) = v4 & 0xFD;
      std::string::_Tidy_deallocate(v172);
    }
    if ( (v4 & 1) != 0 && BYTE8(v164) )
      operator delete(v163[1], v74);
    boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(&v314);
    boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(&v320);
    std::string::_Tidy_deallocate(v321);
    result = boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(&v319);
    v142 = (volatile signed __int32 *)*((_QWORD *)&v315 + 1);
    if ( *((_QWORD *)&v315 + 1) )
    {
      result = (unsigned int)_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v315 + 1) + 8LL));
      if ( !(_DWORD)result )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v142)(v142);
        result = (unsigned int)_InterlockedDecrement(v142 + 3);
        if ( !(_DWORD)result )
          result = (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v142 + 8LL))(v142);
      }
    }
    v11 = *(volatile signed __int32 **)(v278 + 8);
  }
  if ( v11 )
  {
    result = (unsigned int)_InterlockedDecrement(v11 + 3);
    if ( !(_DWORD)result )
      return (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
  }
  return result;
}

```

## disassembly

```asm
0x1801d1f40  mov     [rsp-8+arg_10], rbx
0x1801d1f45  push    rbp
0x1801d1f46  push    rsi
0x1801d1f47  push    rdi
0x1801d1f48  push    r12
0x1801d1f4a  push    r13
0x1801d1f4c  push    r14
0x1801d1f4e  push    r15
0x1801d1f50  lea     rbp, [rsp-8F0h]
0x1801d1f58  mov     eax, 0A20h
0x1801d1f5d  call    _alloca_probe
0x1801d1f62  sub     rsp, rax
0x1801d1f65  mov     rax, cs:__security_cookie
0x1801d1f6c  xor     rax, rsp
0x1801d1f6f  mov     [rbp+920h+var_38], rax
0x1801d1f76  mov     rdi, rdx
0x1801d1f79  mov     [rbp+920h+var_3D8], rdx
0x1801d1f80  mov     r15, rcx
0x1801d1f83  mov     [rbp+920h+var_8E0], rcx
0x1801d1f87  mov     [rbp+920h+var_270], rdx
0x1801d1f8e  xor     r14d, r14d
0x1801d1f91  mov     r12d, r14d
0x1801d1f94  mov     dword ptr [rbp+920h+var_998], r14d
0x1801d1f98  mov     dword ptr [rbp+920h+var_990], r14d
0x1801d1f9c  xorps   xmm0, xmm0
0x1801d1f9f  movups  [rbp+920h+var_A8], xmm0
0x1801d1fa6  xorps   xmm1, xmm1
0x1801d1fa9  movdqu  xmmword ptr [rbp+920h+var_940], xmm1
0x1801d1fae  mov     rdx, [rdx+8]
0x1801d1fb2  test    rdx, rdx
0x1801d1fb5  jz      short loc_1801D1FDB
0x1801d1fb7  mov     eax, [rdx+8]
0x1801d1fba  jmp     short loc_1801D1FC6
0x1801d1fbc  lea     ecx, [rax+1]
0x1801d1fbf  lock cmpxchg [rdx+8], ecx
0x1801d1fc4  jz      short loc_1801D1FCC
0x1801d1fc6  test    eax, eax
0x1801d1fc8  jnz     short loc_1801D1FBC
0x1801d1fca  jmp     short loc_1801D1FDB
0x1801d1fcc  mov     rax, [rdi]
0x1801d1fcf  mov     [rbp+920h+var_940], rax
0x1801d1fd3  mov     rax, [rdi+8]
0x1801d1fd7  mov     [rbp+920h+var_940+8], rax
0x1801d1fdb  lea     rdx, [rbp+920h+var_940]
0x1801d1fdf  lea     rcx, [rbp+920h+var_A8]
0x1801d1fe6  call    ??$dynamic_pointer_cast@VLinkDataDisabled@Dct@Basix@Microsoft@@VLinkData@234@@std@@YA?AV?$shared_ptr@VLinkDataDisabled@Dct@Basix@Microsoft@@@0@$$QEAV?$shared_ptr@VLinkData@Dct@Basix@Microsoft@@@0@@Z; std::dynamic_pointer_cast<Microsoft::Basix::Dct::LinkDataDisabled,Microsoft::Basix::Dct::LinkData>(std::shared_ptr<Microsoft::Basix::Dct::LinkData> &&)
0x1801d1feb  nop
0x1801d1fec  or      esi, 0FFFFFFFFh
0x1801d1fef  mov     rbx, [rbp+920h+var_940+8]
0x1801d1ff3  test    rbx, rbx
0x1801d1ff6  jz      short loc_1801D202D
0x1801d1ff8  mov     eax, esi
0x1801d1ffa  lock xadd [rbx+8], eax
0x1801d1fff  add     eax, esi
0x1801d2001  jnz     short loc_1801D202D
0x1801d2003  mov     rax, [rbx]
0x1801d2006  mov     rcx, rbx
0x1801d2009  mov     rax, [rax]
0x1801d200c  call    cs:__guard_dispatch_icall_fptr
0x1801d2012  mov     eax, esi
0x1801d2014  lock xadd [rbx+0Ch], eax
0x1801d2019  add     eax, esi
0x1801d201b  jnz     short loc_1801D202D
0x1801d201d  mov     rax, [rbx]
0x1801d2020  mov     rcx, rbx
0x1801d2023  mov     rax, [rax+8]
0x1801d2027  call    cs:__guard_dispatch_icall_fptr
0x1801d202d  mov     rcx, r15; this
0x1801d2030  call    ?IsClosed@BasicStateManagement@detail@Dct@Basix@Microsoft@@QEBA_NXZ; Microsoft::Basix::Dct::detail::BasicStateManagement::IsClosed(void)
0x1801d2035  test    al, al
0x1801d2037  jz      short loc_1801D209D
0x1801d2039  mov     rax, qword ptr [rbp+920h+var_A8]
0x1801d2040  mov     rcx, [rax+68h]
0x1801d2044  mov     rax, [rcx]
0x1801d2047  mov     rax, [rax+10h]
0x1801d204b  call    cs:__guard_dispatch_icall_fptr
0x1801d2051  nop
0x1801d2052  mov     rbx, qword ptr [rbp+920h+var_A8+8]
0x1801d2059  test    rbx, rbx
0x1801d205c  jz      short loc_1801D2094
0x1801d205e  mov     eax, esi
0x1801d2060  lock xadd [rbx+8], eax
0x1801d2065  add     eax, esi
0x1801d2067  jnz     short loc_1801D2094
0x1801d2069  mov     rax, [rbx]
0x1801d206c  mov     rcx, rbx
0x1801d206f  mov     rax, [rax]
0x1801d2072  call    cs:__guard_dispatch_icall_fptr
0x1801d2078  mov     eax, esi
0x1801d207a  lock xadd [rbx+0Ch], eax
0x1801d207f  add     eax, esi
0x1801d2081  jnz     short loc_1801D2094
0x1801d2083  mov     rax, [rbx]
0x1801d2086  mov     rcx, rbx
0x1801d2089  mov     rax, [rax+8]
0x1801d208d  call    cs:__guard_dispatch_icall_fptr
0x1801d2093  nop
0x1801d2094  mov     rcx, [rdi+8]
0x1801d2098  jmp     loc_1801D4340
0x1801d209d  lea     rbx, [r15+728h]
0x1801d20a4  mov     [rbp+920h+var_980], rbx
0x1801d20a8  mov     rcx, rbx; _Mtx_t
0x1801d20ab  call    _Mtx_lock
0x1801d20b0  test    eax, eax
0x1801d20b2  jnz     loc_1801D4399
0x1801d20b8  cmp     dword ptr [rbx+4Ch], 7FFFFFFFh
0x1801d20bf  jz      loc_1801D4387
0x1801d20c5  lea     rsi, [r15+5F8h]
0x1801d20cc  lea     rdx, [rbp+920h+var_A8]
0x1801d20d3  mov     rcx, rsi
0x1801d20d6  call    ?insert@?$IterationSafeStore@V?$shared_ptr@VLinkDataDisabled@Dct@Basix@Microsoft@@@std@@U?$equal_to@V?$shared_ptr@VLinkDataDisabled@Dct@Basix@Microsoft@@@std@@@2@@Containers@Basix@Microsoft@@QEAAXAEBV?$shared_ptr@VLinkDataDisabled@Dct@Basix@Microsoft@@@std@@@Z; Microsoft::Basix::Containers::IterationSafeStore<std::shared_ptr<Microsoft::Basix::Dct::LinkDataDisabled>,std::equal_to<std::shared_ptr<Microsoft::Basix::Dct::LinkDataDisabled>>>::insert(std::shared_ptr<Microsoft::Basix::Dct::LinkDataDisabled> const &)
0x1801d20db  mov     rcx, rsi
0x1801d20de  call    ?size@?$IterationSafeStore@V?$shared_ptr@VLinkDataDisabled@Dct@Basix@Microsoft@@@std@@U?$equal_to@V?$shared_ptr@VLinkDataDisabled@Dct@Basix@Microsoft@@@std@@@2@@Containers@Basix@Microsoft@@QEBA_KXZ; Microsoft::Basix::Containers::IterationSafeStore<std::shared_ptr<Microsoft::Basix::Dct::LinkDataDisabled>,std::equal_to<std::shared_ptr<Microsoft::Basix::Dct::LinkDataDisabled>>>::size(void)
0x1801d20e3  mov     [rbp+920h+var_978], rax
0x1801d20e7  xorps   xmm0, xmm0
0x1801d20ea  movups  [rbp+920h+var_970], xmm0
0x1801d20ee  xorps   xmm1, xmm1
0x1801d20f1  movdqu  [rbp+920h+var_960], xmm1
0x1801d20f6  mov     r8d, 29h ; ')'
0x1801d20fc  lea     rdx, aMicrosoftBasix_330; "Microsoft::Basix::Dct.Smiles.LinkPoolSi"...
0x1801d2103  lea     rcx, [rbp+920h+var_970]
0x1801d2107  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1801d210c  mov     [rbp+920h+var_950], 2Eh ; '.'
0x1801d2110  lea     rax, [rbp+920h+var_970]
0x1801d2114  cmp     qword ptr [rbp+920h+var_960+8], 0Fh
0x1801d2119  cmova   rax, qword ptr [rbp+920h+var_970]
0x1801d211e  mov     [rbp+920h+var_948], rax
0x1801d2122  lea     r8, [rbp+920h+var_978]
0x1801d2126  lea     rdx, [rbp+920h+var_970]
0x1801d212a  lea     rcx, [r15+3C0h]
0x1801d2131  call    ??$put@_K@?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEAAAEAV012@AEBV?$string_path@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$id_translator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@property_tree@boost@@@12@AEB_K@Z; boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::put<unsigned __int64>(boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>> const &,unsigned __int64 const &)
0x1801d2136  nop
0x1801d2137  lea     rcx, [rbp+920h+var_970]
0x1801d213b  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1801d2140  inc     dword ptr [r15+5F0h]
0x1801d2147  mov     ecx, [r15+5F0h]
0x1801d214e  mov     rax, qword ptr [rbp+920h+var_A8]
0x1801d2155  mov     [rax+98h], ecx
0x1801d215b  lea     rcx, [r15+688h]
0x1801d2162  lea     rdx, [rbp+920h+var_A8]
0x1801d2169  call    ?erase@?$IterationSafeStore@V?$shared_ptr@VLinkDataV3@Dct@Basix@Microsoft@@@std@@U?$equal_to@V?$shared_ptr@VLinkDataV3@Dct@Basix@Microsoft@@@std@@@2@@Containers@Basix@Microsoft@@QEAAXAEBV?$shared_ptr@VLinkDataV3@Dct@Basix@Microsoft@@@std@@@Z; Microsoft::Basix::Containers::IterationSafeStore<std::shared_ptr<Microsoft::Basix::Dct::LinkDataV3>,std::equal_to<std::shared_ptr<Microsoft::Basix::Dct::LinkDataV3>>>::erase(std::shared_ptr<Microsoft::Basix::Dct::LinkDataV3> const &)
0x1801d216e  mov     [r15+5E1h], r14b
0x1801d2175  mov     rcx, rbx; _Mtx_t
0x1801d2178  call    _Mtx_unlock
0x1801d217d  xorps   xmm0, xmm0
0x1801d2180  movups  [rbp+920h+var_78], xmm0
0x1801d2187  mov     rsi, qword ptr [rbp+920h+var_A8]
0x1801d218e  mov     rbx, [rsi+68h]
0x1801d2192  movups  xmmword ptr [rbp+920h+var_920], xmm0
0x1801d2196  xorps   xmm1, xmm1
0x1801d2199  movdqu  [rbp+920h+var_910], xmm1
0x1801d219e  mov     r8d, 28h ; '('
0x1801d21a4  lea     rdx, aMicrosoftBasix_183; "Microsoft::Basix::Dct.Smiles.AddLinkInf"...
0x1801d21ab  lea     rcx, [rbp+920h+var_920]
0x1801d21af  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1801d21b4  nop
0x1801d21b5  lea     r8, [rbp+920h+var_920]
0x1801d21b9  lea     rdx, [rbp+920h+var_98]
0x1801d21c0  lea     rcx, [rbx+28h]
0x1801d21c4  call    ?GetProperty@IPropertyAware@detail@Dct@Basix@Microsoft@@QEBA?AV?$PTreeResult@V?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@Containers@45@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Microsoft::Basix::Dct::detail::IPropertyAware::GetProperty(std::string const &)
0x1801d21c9  nop
0x1801d21ca  mov     r8b, [rbp+920h+var_9A0]
0x1801d21ce  lea     rdx, [rbp+920h+var_78]
0x1801d21d5  mov     rcx, rax
0x1801d21d8  call    ?As@?$PTreeResult@V?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@Containers@Basix@Microsoft@@AEAA?AV?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@U?$identity@V?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@1234@@Z; Microsoft::Basix::Containers::PTreeResult<boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>>::As(Microsoft::Basix::Containers::PTreeResult<boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>>::identity<boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>>)
0x1801d21dd  mov     r13d, 40000000h
0x1801d21e3  lea     rcx, [rbp+920h+var_98]
0x1801d21ea  call    ??1?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEAA@XZ; boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(void)
0x1801d21ef  nop
0x1801d21f0  lea     rcx, [rbp+920h+var_920]
0x1801d21f4  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1801d21f9  mov     rbx, [rsi+68h]
0x1801d21fd  xorps   xmm0, xmm0
0x1801d2200  movups  xmmword ptr [rbp+920h+var_900], xmm0
0x1801d2204  xorps   xmm1, xmm1
0x1801d2207  movdqu  [rbp+920h+var_8F0], xmm1
0x1801d220c  mov     r8d, 25h ; '%'
0x1801d2212  lea     rdx, aMicrosoftBasix_102; "Microsoft::Basix::Dct.Smiles.LinkType"
0x1801d2219  lea     rcx, [rbp+920h+var_900]
0x1801d221d  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1801d2222  nop
0x1801d2223  lea     r8, [rbp+920h+var_900]
0x1801d2227  lea     rdx, [rbp+920h+var_940]
0x1801d222b  lea     rcx, [rbx+28h]
0x1801d222f  call    ?GetProperty@IPropertyAware@detail@Dct@Basix@Microsoft@@QEBA?AV?$PTreeResult@V?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@Containers@45@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Microsoft::Basix::Dct::detail::IPropertyAware::GetProperty(std::string const &)
0x1801d2234  nop
0x1801d2235  mov     [rbp+920h+var_984], r14d
0x1801d2239  lea     rdx, [rbp+920h+var_984]
0x1801d223d  mov     rcx, [rax+10h]
0x1801d2241  call    ??$get_value@W4LinkType@ISmiles@Dct@Basix@Microsoft@@@?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEBA?AW4LinkType@ISmiles@Dct@Basix@Microsoft@@AEBW434567@@Z; boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get_value<Microsoft::Basix::Dct::ISmiles::LinkType>(Microsoft::Basix::Dct::ISmiles::LinkType const &)
0x1801d2246  mov     ebx, eax
0x1801d2248  mov     [rbp+920h+var_984], eax
0x1801d224b  lea     rcx, [rbp+920h+var_940]
0x1801d224f  call    ??1?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEAA@XZ; boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(void)
0x1801d2254  nop
0x1801d2255  lea     rcx, [rbp+920h+var_900]
0x1801d2259  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1801d225e  mov     [rsi+50h], ebx
0x1801d2261  xorps   xmm0, xmm0
0x1801d2264  movups  [rbp+920h+var_970], xmm0
0x1801d2268  xorps   xmm1, xmm1
0x1801d226b  movdqu  [rbp+920h+var_960], xmm1
0x1801d2270  mov     r8d, 7
0x1801d2276  lea     rdx, aSummary; "Summary"
0x1801d227d  lea     rcx, [rbp+920h+var_970]
0x1801d2281  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1801d2286  mov     [rbp+920h+var_950], 2Eh ; '.'
0x1801d228a  lea     rax, [rbp+920h+var_970]
0x1801d228e  mov     edi, 0Fh
0x1801d2293  cmp     qword ptr [rbp+920h+var_960+8], rdi
0x1801d2297  cmova   rax, qword ptr [rbp+920h+var_970]
0x1801d229c  mov     [rbp+920h+var_948], rax
0x1801d22a0  lea     r9, Str1
0x1801d22a7  lea     r8, [rbp+920h+var_970]
0x1801d22ab  lea     rdx, [rbp+920h+var_58]
0x1801d22b2  lea     rcx, [rbp+920h+var_78]
0x1801d22b9  call    ??$get@D@?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$string_path@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$id_translator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@property_tree@boost@@@12@PEBD@Z; boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get<char>(boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>> const &,char const *)
0x1801d22be  nop
0x1801d22bf  lea     rcx, [rbp+920h+var_970]
0x1801d22c3  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1801d22c8  xorps   xmm0, xmm0
0x1801d22cb  movups  xmmword ptr [rbp+920h+var_98], xmm0
0x1801d22d2  lea     rcx, [rbp+920h+var_98]
0x1801d22d9  call    ??$SelectEvent@VTraceCheckpoint@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceCheckpoint@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceCheckpoint>(void)
0x1801d22de  nop
0x1801d22df  mov     rax, [rbp+920h+var_98]
0x1801d22e6  test    rax, rax
0x1801d22e9  jz      loc_1801D2A5F
0x1801d22ef  cmp     [rax+80h], r14b
0x1801d22f6  jz      loc_1801D2A5F
0x1801d22fc  lea     rax, [rbp+920h+var_898]
0x1801d2303  mov     [rbp+920h+var_978], rax
0x1801d2307  lea     rbx, asc_1803D71C8; "\""
0x1801d230e  mov     rdx, rbx
0x1801d2311  lea     rcx, [rbp+920h+var_970]
0x1801d2315  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1801d231a  mov     r15, rax
0x1801d231d  lea     r14, [rbp+920h+var_58]
0x1801d2324  cmp     [rbp+920h+var_40], rdi
0x1801d232b  cmova   r14, [rbp+920h+var_58]
0x1801d2333  mov     rdx, rbx
0x1801d2336  lea     rcx, [rbp+920h+var_290]
0x1801d233d  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1801d2342  mov     rsi, rax
0x1801d2345  lea     rdx, asc_1803D71C4; ":"
0x1801d234c  lea     rcx, [rbp+920h+var_2B0]
0x1801d2353  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1801d2358  mov     rdi, rax
0x1801d235b  mov     rdx, rbx
0x1801d235e  lea     rcx, [rbp+920h+var_2D0]
0x1801d2365  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1801d236a  mov     rbx, rax
0x1801d236d  lea     rdx, asc_1803D71C8; "\""
0x1801d2374  lea     rcx, [rbp+920h+var_128]
0x1801d237b  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1801d2380  nop
0x1801d2381  lea     r8, aAdditionalinfo; "AdditionalInfo"
0x1801d2388  mov     rdx, rax
0x1801d238b  lea     rcx, [rbp+920h+var_148]
0x1801d2392  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@QEBD@Z; std::operator+<char>(std::string &&,char const * const)
0x1801d2397  nop
0x1801d2398  mov     r9, rbx
0x1801d239b  mov     r8, rax
0x1801d239e  mov     dl, [rbp+920h+var_9A0]
0x1801d23a1  lea     rcx, [rbp+920h+var_838]
0x1801d23a8  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::string::string(std::_String_constructor_concat_tag,std::string &,std::string &)
0x1801d23ad  nop
0x1801d23ae  mov     r9, rdi
0x1801d23b1  lea     r8, [rbp+920h+var_838]
0x1801d23b8  mov     dl, [rbp+920h+var_9A0]
0x1801d23bb  lea     rcx, [rbp+920h+var_818]
0x1801d23c2  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::string::string(std::_String_constructor_concat_tag,std::string &,std::string &)
0x1801d23c7  nop
0x1801d23c8  mov     r9, rsi
0x1801d23cb  lea     r8, [rbp+920h+var_818]
0x1801d23d2  mov     dl, [rbp+920h+var_9A0]
0x1801d23d5  lea     rcx, [rbp+920h+var_7F8]
0x1801d23dc  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::string::string(std::_String_constructor_concat_tag,std::string &,std::string &)
0x1801d23e1  nop
0x1801d23e2  mov     r8, r14
0x1801d23e5  lea     rdx, [rbp+920h+var_7F8]
0x1801d23ec  lea     rcx, [rbp+920h+var_168]
0x1801d23f3  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@QEBD@Z; std::operator+<char>(std::string &&,char const * const)
0x1801d23f8  nop
0x1801d23f9  mov     r9, r15
0x1801d23fc  mov     r8, rax
0x1801d23ff  mov     dl, [rbp+920h+var_9A0]
0x1801d2402  lea     rcx, [rbp+920h+var_898]
0x1801d2409  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::string::string(std::_String_constructor_concat_tag,std::string &,std::string &)
0x1801d240e  nop
0x1801d240f  lea     rax, [rbp+920h+var_878]
0x1801d2416  mov     [rbp+920h+var_980], rax
0x1801d241a  mov     r15, [rbp+920h+var_8E0]
0x1801d241e  mov     edx, [r15+5D4h]
0x1801d2425  lea     rcx, [rbp+920h+var_7D8]
0x1801d242c  call    ??$_Integral_to_string@DI@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@I@Z; std::_Integral_to_string<char,uint>(uint)
0x1801d2431  nop
0x1801d2432  lea     r14, asc_1803D71C4; ":"
0x1801d2439  mov     rdx, r14
0x1801d243c  lea     rcx, [rbp+920h+var_188]
  ... truncated ...
```
