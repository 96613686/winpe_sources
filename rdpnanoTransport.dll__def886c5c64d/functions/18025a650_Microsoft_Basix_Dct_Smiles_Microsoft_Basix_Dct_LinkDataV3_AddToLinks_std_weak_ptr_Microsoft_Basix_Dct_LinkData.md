# Microsoft::Basix::Dct::Smiles<Microsoft::Basix::Dct::LinkDataV3>::AddToLinks(std::weak_ptr<Microsoft::Basix::Dct::LinkData>)

- ea: `0x18025a650`
- end: `0x18025cac1`
- name: `?AddToLinks@?$Smiles@VLinkDataV3@Dct@Basix@Microsoft@@@Dct@Basix@Microsoft@@MEAAXV?$weak_ptr@VLinkData@Dct@Basix@Microsoft@@@std@@@Z`
- size: `9329`
- prototype: ``
- caller_count: `1`
- callee_count: `41`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18025cad0`

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
- `0x1801cf8d4`
- `0x1802533f8`
- `0x18025a650`
- `0x18031215c`
- `0x180312164`
- `0x180312404`
- `0x18032f050`
- `0x18032f0b0`
- `0x18032f100`
- `0x18032f140`
- `0x180375c40`

## string_xrefs

- `0x18025a80c`: `Microsoft::Basix::Dct.Smiles.LinkPoolSize`
- `0x18025ae5d`: `LinkId`
- `0x18025a922`: `Microsoft::Basix::Dct.Smiles.LinkType`
- `0x18025a8b4`: `Microsoft::Basix::Dct.Smiles.AddLinkInfo`
- `0x18025acee`: `LinkType`
- `0x18025ada5`: `linksSize`
- `0x18025af04`: `AddLink`
- `0x18025b212`: `Components`
- `0x18025b431`: `Checkpoint.SMILES.LinkAdded(%d),IceDoR(%d)|nonIceDor(%d):%s, TransportTypeOnServer=%s, TransportTypeOnClient=%s, TransportIPOnServer=%s, TransportIPOnClient=%s`

## pseudocode

```c
// Hidden C++ exception states: #wind=180
__int64 __fastcall Microsoft::Basix::Dct::Smiles<Microsoft::Basix::Dct::LinkDataV3>::AddToLinks(
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
  __int64 *v151; // [rsp+C0h] [rbp-70h] BYREF
  _BYTE v152[8]; // [rsp+C8h] [rbp-68h] BYREF
  __int64 *v153; // [rsp+D0h] [rbp-60h] BYREF
  __int64 *v154; // [rsp+D8h] [rbp-58h] BYREF
  __int128 v155; // [rsp+E0h] [rbp-50h] BYREF
  __int128 v156; // [rsp+F0h] [rbp-40h]
  char v157; // [rsp+100h] [rbp-30h]
  __int128 *v158; // [rsp+108h] [rbp-28h]
  void *v159[2]; // [rsp+110h] [rbp-20h] BYREF
  __int64 v160; // [rsp+120h] [rbp-10h]
  char v161; // [rsp+128h] [rbp-8h]
  void *v162[2]; // [rsp+130h] [rbp+0h] BYREF
  __int128 v163; // [rsp+140h] [rbp+10h]
  void *v164[2]; // [rsp+150h] [rbp+20h] BYREF
  __int128 v165; // [rsp+160h] [rbp+30h]
  __int64 *v166; // [rsp+170h] [rbp+40h]
  __int64 v167[2]; // [rsp+178h] [rbp+48h] BYREF
  __int128 v168; // [rsp+188h] [rbp+58h]
  __int64 v169[2]; // [rsp+198h] [rbp+68h] BYREF
  __int128 v170; // [rsp+1A8h] [rbp+78h]
  __int64 v171[2]; // [rsp+1B8h] [rbp+88h] BYREF
  __int128 v172; // [rsp+1C8h] [rbp+98h]
  __int64 v173[2]; // [rsp+1D8h] [rbp+A8h] BYREF
  __int128 v174; // [rsp+1E8h] [rbp+B8h]
  __int64 v175[2]; // [rsp+1F8h] [rbp+C8h] BYREF
  __int128 v176; // [rsp+208h] [rbp+D8h]
  int v177; // [rsp+218h] [rbp+E8h] BYREF
  void *v178; // [rsp+220h] [rbp+F0h]
  __int64 v179; // [rsp+228h] [rbp+F8h]
  char v180; // [rsp+230h] [rbp+100h]
  int v181; // [rsp+238h] [rbp+108h] BYREF
  void *v182; // [rsp+240h] [rbp+110h]
  __int64 v183; // [rsp+248h] [rbp+118h]
  char v184; // [rsp+250h] [rbp+120h]
  int v185; // [rsp+258h] [rbp+128h] BYREF
  void *v186; // [rsp+260h] [rbp+130h]
  __int64 v187; // [rsp+268h] [rbp+138h]
  char v188; // [rsp+270h] [rbp+140h]
  int v189; // [rsp+278h] [rbp+148h] BYREF
  void *v190; // [rsp+280h] [rbp+150h]
  __int64 v191; // [rsp+288h] [rbp+158h]
  char v192; // [rsp+290h] [rbp+160h]
  int v193; // [rsp+298h] [rbp+168h] BYREF
  void *v194; // [rsp+2A0h] [rbp+170h]
  __int64 v195; // [rsp+2A8h] [rbp+178h]
  char v196; // [rsp+2B0h] [rbp+180h]
  int v197; // [rsp+2B8h] [rbp+188h] BYREF
  void *v198; // [rsp+2C0h] [rbp+190h]
  __int64 v199; // [rsp+2C8h] [rbp+198h]
  char v200; // [rsp+2D0h] [rbp+1A0h]
  int v201; // [rsp+2D8h] [rbp+1A8h] BYREF
  void *v202; // [rsp+2E0h] [rbp+1B0h]
  __int64 v203; // [rsp+2E8h] [rbp+1B8h]
  char v204; // [rsp+2F0h] [rbp+1C0h]
  int v205; // [rsp+2F8h] [rbp+1C8h] BYREF
  void *v206; // [rsp+300h] [rbp+1D0h]
  __int64 v207; // [rsp+308h] [rbp+1D8h]
  char v208; // [rsp+310h] [rbp+1E0h]
  int v209; // [rsp+318h] [rbp+1E8h] BYREF
  void *v210; // [rsp+320h] [rbp+1F0h]
  __int64 v211; // [rsp+328h] [rbp+1F8h]
  char v212; // [rsp+330h] [rbp+200h]
  int v213; // [rsp+338h] [rbp+208h] BYREF
  void *v214; // [rsp+340h] [rbp+210h]
  __int64 v215; // [rsp+348h] [rbp+218h]
  char v216; // [rsp+350h] [rbp+220h]
  int v217; // [rsp+358h] [rbp+228h] BYREF
  void *v218; // [rsp+360h] [rbp+230h]
  __int64 v219; // [rsp+368h] [rbp+238h]
  char v220; // [rsp+370h] [rbp+240h]
  int v221; // [rsp+378h] [rbp+248h] BYREF
  void *v222; // [rsp+380h] [rbp+250h]
  __int64 v223; // [rsp+388h] [rbp+258h]
  char v224; // [rsp+390h] [rbp+260h]
  int v225; // [rsp+398h] [rbp+268h] BYREF
  void *v226; // [rsp+3A0h] [rbp+270h]
  __int64 v227; // [rsp+3A8h] [rbp+278h]
  char v228; // [rsp+3B0h] [rbp+280h]
  __int128 v229; // [rsp+3B8h] [rbp+288h] BYREF
  __int128 v230; // [rsp+3C8h] [rbp+298h]
  char v231; // [rsp+3D8h] [rbp+2A8h]
  __int128 *v232; // [rsp+3E0h] [rbp+2B0h]
  __int128 v233; // [rsp+3E8h] [rbp+2B8h] BYREF
  __int128 v234; // [rsp+3F8h] [rbp+2C8h]
  char v235; // [rsp+408h] [rbp+2D8h]
  __int128 *v236; // [rsp+410h] [rbp+2E0h]
  __int128 v237; // [rsp+418h] [rbp+2E8h] BYREF
  __int128 v238; // [rsp+428h] [rbp+2F8h]
  char v239; // [rsp+438h] [rbp+308h]
  __int128 *v240; // [rsp+440h] [rbp+310h]
  __int128 v241; // [rsp+448h] [rbp+318h] BYREF
  __int128 v242; // [rsp+458h] [rbp+328h]
  char v243; // [rsp+468h] [rbp+338h]
  __int128 *v244; // [rsp+470h] [rbp+340h]
  _OWORD v245[2]; // [rsp+478h] [rbp+348h] BYREF
  _OWORD v246[2]; // [rsp+498h] [rbp+368h] BYREF
  _OWORD v247[2]; // [rsp+4B8h] [rbp+388h] BYREF
  _OWORD v248[2]; // [rsp+4D8h] [rbp+3A8h] BYREF
  _OWORD v249[2]; // [rsp+4F8h] [rbp+3C8h] BYREF
  _OWORD v250[2]; // [rsp+518h] [rbp+3E8h] BYREF
  _OWORD v251[2]; // [rsp+538h] [rbp+408h] BYREF
  __int64 v252[2]; // [rsp+558h] [rbp+428h] BYREF
  __int128 v253; // [rsp+568h] [rbp+438h]
  __int128 v254; // [rsp+578h] [rbp+448h] BYREF
  __int128 v255; // [rsp+588h] [rbp+458h]
  char v256; // [rsp+598h] [rbp+468h]
  __int128 *v257; // [rsp+5A0h] [rbp+470h]
  __int128 v258; // [rsp+5A8h] [rbp+478h] BYREF
  __int128 v259; // [rsp+5B8h] [rbp+488h]
  char v260; // [rsp+5C8h] [rbp+498h]
  __int128 *v261; // [rsp+5D0h] [rbp+4A0h]
  __int128 v262; // [rsp+5D8h] [rbp+4A8h] BYREF
  __int128 v263; // [rsp+5E8h] [rbp+4B8h]
  char v264; // [rsp+5F8h] [rbp+4C8h]
  __int128 *v265; // [rsp+600h] [rbp+4D0h]
  __int128 v266; // [rsp+608h] [rbp+4D8h] BYREF
  __int128 v267; // [rsp+618h] [rbp+4E8h]
  char v268; // [rsp+628h] [rbp+4F8h]
  __int128 *v269; // [rsp+630h] [rbp+500h]
  __int128 v270; // [rsp+638h] [rbp+508h] BYREF
  __int128 v271; // [rsp+648h] [rbp+518h]
  char v272; // [rsp+658h] [rbp+528h]
  __int128 *v273; // [rsp+660h] [rbp+530h]
  __int128 v274; // [rsp+668h] [rbp+538h] BYREF
  __int128 v275; // [rsp+678h] [rbp+548h]
  char v276; // [rsp+688h] [rbp+558h]
  __int128 *v277; // [rsp+690h] [rbp+560h]
  __int64 v278; // [rsp+698h] [rbp+568h]
  _OWORD v279[2]; // [rsp+6A0h] [rbp+570h] BYREF
  __int128 v280; // [rsp+6C0h] [rbp+590h] BYREF
  __int128 v281; // [rsp+6D0h] [rbp+5A0h]
  char v282; // [rsp+6E0h] [rbp+5B0h]
  __int128 *v283; // [rsp+6E8h] [rbp+5B8h]
  __int128 v284; // [rsp+6F0h] [rbp+5C0h] BYREF
  __int128 v285; // [rsp+700h] [rbp+5D0h]
  char v286; // [rsp+710h] [rbp+5E0h]
  __int128 *v287; // [rsp+718h] [rbp+5E8h]
  __int128 v288; // [rsp+720h] [rbp+5F0h] BYREF
  __int128 v289; // [rsp+730h] [rbp+600h]
  char v290; // [rsp+740h] [rbp+610h]
  __int128 *v291; // [rsp+748h] [rbp+618h]
  __int128 v292; // [rsp+750h] [rbp+620h] BYREF
  __int128 v293; // [rsp+760h] [rbp+630h]
  char v294; // [rsp+770h] [rbp+640h]
  __int128 *v295; // [rsp+778h] [rbp+648h]
  _BYTE v296[32]; // [rsp+780h] [rbp+650h] BYREF
  _BYTE v297[32]; // [rsp+7A0h] [rbp+670h] BYREF
  _BYTE v298[32]; // [rsp+7C0h] [rbp+690h] BYREF
  __int64 v299; // [rsp+7E0h] [rbp+6B0h]
  _BYTE v300[32]; // [rsp+7E8h] [rbp+6B8h] BYREF
  _BYTE v301[32]; // [rsp+808h] [rbp+6D8h] BYREF
  _BYTE v302[32]; // [rsp+828h] [rbp+6F8h] BYREF
  _BYTE v303[32]; // [rsp+848h] [rbp+718h] BYREF
  _BYTE v304[32]; // [rsp+868h] [rbp+738h] BYREF
  _BYTE v305[32]; // [rsp+888h] [rbp+758h] BYREF
  _BYTE v306[32]; // [rsp+8A8h] [rbp+778h] BYREF
  _BYTE v307[32]; // [rsp+8C8h] [rbp+798h] BYREF
  _BYTE v308[32]; // [rsp+8E8h] [rbp+7B8h] BYREF
  _BYTE v309[32]; // [rsp+908h] [rbp+7D8h] BYREF
  _BYTE v310[32]; // [rsp+928h] [rbp+7F8h] BYREF
  _BYTE v311[32]; // [rsp+948h] [rbp+818h] BYREF
  _BYTE v312[48]; // [rsp+968h] [rbp+838h] BYREF
  unsigned int v313; // [rsp+998h] [rbp+868h] BYREF
  __int128 v314; // [rsp+9A0h] [rbp+870h] BYREF
  __int128 v315; // [rsp+9B0h] [rbp+880h] BYREF
  void *v316[2]; // [rsp+9C0h] [rbp+890h] BYREF
  __int64 v317; // [rsp+9D0h] [rbp+8A0h]
  char v318; // [rsp+9D8h] [rbp+8A8h]
  __int128 v319; // [rsp+9E0h] [rbp+8B0h] BYREF
  __int128 v320; // [rsp+9F0h] [rbp+8C0h] BYREF
  _QWORD v321[3]; // [rsp+A00h] [rbp+8D0h] BYREF
  unsigned __int64 v322; // [rsp+A18h] [rbp+8E8h]

  v278 = a2;
  v3 = a1;
  v166 = a1;
  v299 = a2;
  v4 = 0;
  LODWORD(v150) = 0;
  LODWORD(v151) = 0;
  v315 = 0;
  *(_OWORD *)v159 = 0;
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
        v159[0] = *(void **)a2;
        v159[1] = *(void **)(a2 + 8);
        break;
      }
    }
  }
  std::dynamic_pointer_cast<Microsoft::Basix::Dct::LinkDataV3,Microsoft::Basix::Dct::LinkData>(&v315, v159);
  v8 = (volatile signed __int32 *)v159[1];
  if ( v159[1] )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v159[1] + 2, 0xFFFFFFFF) == 1 )
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
    v153 = v3 + 229;
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
    v154 = (__int64 *)Microsoft::Basix::Containers::IterationSafeStore<std::shared_ptr<Microsoft::Basix::Dct::LinkDataDisabled>,std::equal_to<std::shared_ptr<Microsoft::Basix::Dct::LinkDataDisabled>>>::size(v3 + 191);
    v155 = 0;
    v156 = 0;
    std::string::_Construct<1,char const *>(&v155, "Microsoft::Basix::Dct.Smiles.LinkPoolSize", 41);
    v157 = 46;
    v12 = &v155;
    if ( *((_QWORD *)&v156 + 1) > 0xFu )
      v12 = (__int128 *)v155;
    v158 = v12;
    boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::put<unsigned __int64>(
      v3 + 120,
      &v155,
      &v154);
    std::string::_Tidy_deallocate(&v155);
    *(_DWORD *)(v315 + 152) = ++*((_DWORD *)v3 + 380);
    Microsoft::Basix::Containers::IterationSafeStore<std::shared_ptr<Microsoft::Basix::Dct::LinkDataV3>,std::equal_to<std::shared_ptr<Microsoft::Basix::Dct::LinkDataV3>>>::erase(
      v3 + 209,
      &v315);
    *((_BYTE *)v3 + 1505) = 0;
    Mtx_unlock((_Mtx_t)(v3 + 229));
    v320 = 0;
    v13 = v315;
    v14 = *(_QWORD *)(v315 + 104);
    *(_OWORD *)v164 = 0;
    v165 = 0;
    std::string::_Construct<1,char const *>(v164, "Microsoft::Basix::Dct.Smiles.AddLinkInfo", 40);
    Property = Microsoft::Basix::Dct::detail::IPropertyAware::GetProperty(v14 + 40, v316, v164);
    LOBYTE(v16) = v149[0];
    Microsoft::Basix::Containers::PTreeResult<boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>>::As(
      Property,
      &v320,
      v16);
    v17 = 0x40000000;
    boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(v316);
    std::string::_Tidy_deallocate(v164);
    v18 = *(_QWORD *)(v13 + 104);
    *(_OWORD *)v162 = 0;
    v163 = 0;
    std::string::_Construct<1,char const *>(v162, "Microsoft::Basix::Dct.Smiles.LinkType", 37);
    v19 = Microsoft::Basix::Dct::detail::IPropertyAware::GetProperty(v18 + 40, v159, v162);
    LODWORD(v151) = 0;
    v313 = boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get_value<enum Microsoft::Basix::Dct::ISmiles::LinkType>(
             *(_QWORD *)(v19 + 16),
             &v151);
    boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(v159);
    std::string::_Tidy_deallocate(v162);
    *(_DWORD *)(v13 + 80) = v313;
    v155 = 0;
    v156 = 0;
    std::string::_Construct<1,char const *>(&v155, "Summary", 7);
    v157 = 46;
    v20 = &v155;
    if ( *((_QWORD *)&v156 + 1) > 0xFu )
      v20 = (__int128 *)v155;
    v158 = v20;
    boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get<char>(
      &v320,
      v321,
      &v155,
      &Str1);
    std::string::_Tidy_deallocate(&v155);
    *(_OWORD *)v316 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceCheckpoint>(v316);
    if ( v316[0] && *((_BYTE *)v316[0] + 128) )
    {
      v154 = v171;
      v21 = std::string::string(&v155, "\"");
      v22 = v321;
      if ( v322 > 0xF )
        v22 = (_QWORD *)v321[0];
      v23 = std::string::string(v298, "\"");
      v24 = std::string::string(v297, ":");
      v25 = std::string::string(v296, "\"");
      v26 = std::string::string(v310, "\"");
      v27 = std::operator+<char>(v309, v26, "AdditionalInfo");
      LOBYTE(v28) = v149[0];
      std::string::string(&v177, v28, v27, v25);
      LOBYTE(v29) = v149[0];
      std::string::string(&v181, v29, &v177, v24);
      LOBYTE(v30) = v149[0];
      std::string::string(&v185, v30, &v181, v23);
      v31 = std::operator+<char>(v308, &v185, v22);
      LOBYTE(v32) = v149[0];
      std::string::string(v171, v32, v31, v21);
      v153 = v173;
      v3 = v166;
      std::_Integral_to_string<char,unsigned int>(&v189, *((unsigned int *)v166 + 373));
      v33 = std::string::string(v307, ":");
      v34 = std::string::string(v306, "\"");
      v35 = std::string::string(v311, "\"");
      v36 = std::operator+<char>(v305, v35, "NonIceDoR");
      LOBYTE(v37) = v149[0];
      std::string::string(&v193, v37, v36, v34);
      LOBYTE(v38) = v149[0];
      std::string::string(&v197, v38, &v193, v33);
      LOBYTE(v39) = v149[0];
      std::string::string(v173, v39, &v197, &v189);
      v166 = v175;
      std::_Integral_to_string<char,unsigned int>(&v201, *((unsigned int *)v3 + 372));
      v40 = std::string::string(v304, ":");
      v41 = std::string::string(v303, "\"");
      v42 = std::string::string(v302, "\"");
      v43 = std::operator+<char>(v301, v42, "IceDoR");
      LOBYTE(v44) = v149[0];
      std::string::string(&v205, v44, v43, v41);
      LOBYTE(v45) = v149[0];
      std::string::string(v162, v45, &v205, v40);
      LOBYTE(v46) = v149[0];
      std::string::string(v175, v46, v162, &v201);
      v151 = v167;
      std::_Integral_to_string<char,int>(v164, v313);
      v47 = std::string::string(v300, ":");
      v48 = std::string::string(&v274, "\"");
      v49 = std::string::string(&v270, "\"");
      v50 = std::operator+<char>(&v266, v49, "LinkType");
      LOBYTE(v51) = v149[0];
      std::string::string(v279, v51, v50, v48);
      LOBYTE(v52) = v149[0];
      std::string::string(v245, v52, v279, v47);
      LOBYTE(v53) = v149[0];
      std::string::string(v167, v53, v245, v164);
      v150 = v169;
      v54 = Microsoft::Basix::Containers::IterationSafeStore<std::shared_ptr<Microsoft::Basix::Dct::LinkDataDisabled>,std::equal_to<std::shared_ptr<Microsoft::Basix::Dct::LinkDataDisabled>>>::size(v3 + 191);
      std::_Integral_to_string<char,unsigned __int64>(v246, v54);
      v55 = std::string::string(&v262, ":");
      v56 = std::string::string(&v258, "\"");
      v57 = std::string::string(&v254, "\"");
      v58 = std::operator+<char>(&v213, v57, "linksSize");
      LOBYTE(v59) = v149[0];
      std::string::string(v247, v59, v58, v56);
      LOBYTE(v60) = v149[0];
      std::string::string(v248, v60, v247, v55);
      LOBYTE(v61) = v149[0];
      std::string::string(v169, v61, v248, v246);
      v13 = v315;
      std::_Integral_to_string<char,unsigned int>(v249, *(unsigned int *)(v315 + 152));
      v62 = std::string::string(&v209, ":");
      v63 = std::string::string(&v217, "\"");
      v64 = std::string::string(&v221, "\"");
      v65 = std::operator+<char>(&v225, v64, "LinkId");
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
        (__int64)v169,
        (__int64)v167,
        (__int64)v175,
        (__int64)v173,
        (__int64)v171);
      std::string::_Tidy_deallocate(v251);
      std::string::_Tidy_deallocate(v250);
      std::string::_Tidy_deallocate(&v225);
      std::string::_Tidy_deallocate(&v221);
      std::string::_Tidy_deallocate(&v217);
      std::string::_Tidy_deallocate(&v209);
      std::string::_Tidy_deallocate(v249);
      std::string::_Tidy_deallocate(v248);
      std::string::_Tidy_deallocate(v247);
      std::string::_Tidy_deallocate(&v213);
      std::string::_Tidy_deallocate(&v254);
      std::string::_Tidy_deallocate(&v258);
      std::string::_Tidy_deallocate(&v262);
      std::string::_Tidy_deallocate(v246);
      std::string::_Tidy_deallocate(v245);
      std::string::_Tidy_deallocate(v279);
      std::string::_Tidy_deallocate(&v266);
      std::string::_Tidy_deallocate(&v270);
      std::string::_Tidy_deallocate(&v274);
      std::string::_Tidy_deallocate(v300);
      std::string::_Tidy_deallocate(v164);
      std::string::_Tidy_deallocate(v162);
      std::string::_Tidy_deallocate(&v205);
      std::string::_Tidy_deallocate(v301);
      std::string::_Tidy_deallocate(v302);
      std::string::_Tidy_deallocate(v303);
      std::string::_Tidy_deallocate(v304);
      std::string::_Tidy_deallocate(&v201);
      std::string::_Tidy_deallocate(&v197);
      std::string::_Tidy_deallocate(&v193);
      std::string::_Tidy_deallocate(v305);
      std::string::_Tidy_deallocate(v311);
      std::string::_Tidy_deallocate(v306);
      std::string::_Tidy_deallocate(v307);
      std::string::_Tidy_deallocate(&v189);
      std::string::_Tidy_deallocate(v308);
      std::string::_Tidy_deallocate(&v185);
      std::string::_Tidy_deallocate(&v181);
      std::string::_Tidy_deallocate(&v177);
      std::string::_Tidy_deallocate(v309);
      std::string::_Tidy_deallocate(v310);
      std::string::_Tidy_deallocate(v296);
      std::string::_Tidy_deallocate(v297);
      std::string::_Tidy_deallocate(v298);
      std::string::_Tidy_deallocate(&v155);
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
    v319 = 0u;
    v70 = operator new(0x20u);
    v159[0] = v70;
    if ( v70 )
      v71 = __0__multi_index_container_U__pair___CBV__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__V__basic_ptree_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__Vany_boost__U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___2__property_tree_boost___std__U__indexed_by_U__sequenced_U__tag_Una_mpl_boost__U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123_U123__multi_index_boost___multi_index_boost__U__ordered_non_unique_U__tag_Uby_name_subs___basic_ptree_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__Vany_boost__U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___2__property_tree_boost__Una_mpl_5_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675_U675__multi_index_boost__U__member_U__pair___CBV__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__V__basic_ptree_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__Vany_boost__U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___2__property_tree_boost___std____CBV__basic_string_DU__char_traits_D_std__V__allocator_D_2__2__0A__23_U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___std___23_Una_mpl_3_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563_U563__multi_index_boost__V__allocator_U__pair___CBV__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__V__basic_ptree_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std__Vany_boost__U__less_V__basic_string_DU__char_traits_D_std__V__allocator_D_2__std___2__property_tree_boost___std___2__multi_index_boost__QEAA_XZ(v70);
    else
      v71 = 0;
    *((_QWORD *)&v319 + 1) = v71;
    v314 = 0;
    v155 = 0;
    v156 = 0;
    std::string::_Construct<1,char const *>(&v155, "Components", 10);
    v157 = 46;
    v72 = &v155;
    if ( *((_QWORD *)&v156 + 1) > 0xFu )
      v72 = (__int128 *)v155;
    v158 = v72;
    child = boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get_child(
              &v320,
              &v155,
              &v319);
    boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::basic_ptree<std::string,boost::any,std::less<std::string>>(
      &v314,
      child);
    std::string::_Tidy_deallocate(&v155);
    *(_OWORD *)v316 = 0;
    Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceNormal>(v316);
    if ( v316[0] && *((_BYTE *)v316[0] + 128) )
    {
      std::string::string(v169, (const char *)&Str1);
      LOBYTE(v75) = v149[0];
      LOBYTE(v76) = 46;
      boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>>::string_path<std::string,boost::property_tree::id_translator<std::string>>(
        &v233,
        "TransportIPClient",
        v76,
        v75);
      v77 = (__int64 *)boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get<std::string>(
                         &v314,
                         v296,
                         &v233,
                         v169);
      v153 = v77;
      if ( (unsigned __int64)v77[3] > 0xF )
        v153 = (__int64 *)*v77;
      std::string::string(v167, (const char *)&Str1);
      LOBYTE(v78) = v149[0];
      LOBYTE(v79) = 46;
      boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>>::string_path<std::string,boost::property_tree::id_translator<std::string>>(
        &v229,
        "TransportIPServer",
        v79,
        v78);
      v80 = (__int64 *)boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get<std::string>(
                         &v314,
                         v297,
                         &v229,
                         v167);
      v151 = v80;
      if ( (unsigned __int64)v80[3] > 0xF )
        v151 = (__int64 *)*v80;
      std::string::string(v175, (const char *)&Str1);
      LOBYTE(v81) = v149[0];
      LOBYTE(v82) = 46;
      boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>>::string_path<std::string,boost::property_tree::id_translator<std::string>>(
        &v237,
        "TransportTypeClient",
        v82,
        v81);
      v83 = (__int64 *)boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get<std::string>(
                         &v314,
                         v298,
                         &v237,
                         v175);
      v150 = v83;
      if ( (unsigned __int64)v83[3] > 0xF )
        v150 = (__int64 *)*v83;
      std::string::string(v173, (const char *)&Str1);
      LOBYTE(v84) = v149[0];
      LOBYTE(v85) = 46;
      boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>>::string_path<std::string,boost::property_tree::id_translator<std::string>>(
        &v241,
        "TransportTypeServer",
        v85,
        v84);
      v86 = (__int64 *)boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get<std::string>(
                         &v314,
                         &v155,
                         &v241,
                         v173);
      v154 = v86;
      if ( (unsigned __int64)v86[3] > 0xF )
        v154 = (__int64 *)*v86;
      v89 = v321;
      if ( v322 > 0xF )
        v89 = (_QWORD *)v321[0];
      v90 = *((_DWORD *)v3 + 373);
      v91 = *((_DWORD *)v3 + 372);
      v92 = *(_DWORD *)(v13 + 152);
      std::string::string(
        v171,
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
        (unsigned int)v171,
        v92,
        v91,
        v90,
        (__int64)v89,
        (__int64)v154,
        (__int64)v150,
        (__int64)v151,
        (__int64)v153);
      std::string::_Tidy_deallocate(v171);
      std::string::_Tidy_deallocate(&v155);
      std::string::_Tidy_deallocate(&v241);
      std::string::_Tidy_deallocate(v173);
      std::string::_Tidy_deallocate(v298);
      std::string::_Tidy_deallocate(&v237);
      std::string::_Tidy_deallocate(v175);
      std::string::_Tidy_deallocate(v297);
      std::string::_Tidy_deallocate(&v229);
      std::string::_Tidy_deallocate(v167);
      std::string::_Tidy_deallocate(v296);
      std::string::_Tidy_deallocate(&v233);
      std::string::_Tidy_deallocate(v169);
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
      LODWORD(v164[0]) = 2;
      v164[1] = (void *)&Str1;
      *(_QWORD *)&v165 = 0;
      BYTE8(v165) = 0;
      *(_OWORD *)v171 = 0;
      v172 = 0;
      std::string::_Construct<1,char const *>(v171, (const char *)&Str1, 0);
      LODWORD(v150) = 3;
      v241 = 0;
      v242 = 0;
      std::string::_Construct<1,char const *>(&v241, "NatIPServer", 11);
      v243 = 46;
      v94 = &v241;
      if ( *((_QWORD *)&v242 + 1) > 0xFu )
        v94 = (__int128 *)v241;
      v244 = v94;
      LODWORD(v150) = 7;
      v95 = boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get<std::string>(
              &v314,
              v300,
              &v241,
              v171);
      LODWORD(v162[0]) = 2;
      v96 = (void *)v95;
      if ( *(_QWORD *)(v95 + 24) > 0xFu )
        v96 = *(void **)v95;
      v162[1] = v96;
      *(_QWORD *)&v163 = *(_QWORD *)(v95 + 16);
      BYTE8(v163) = 0;
      *(_OWORD *)v173 = 0;
      v174 = 0;
      std::string::_Construct<1,char const *>(v173, (const char *)&Str1, 0);
      LODWORD(v150) = 63;
      v237 = 0;
      v238 = 0;
      std::string::_Construct<1,char const *>(&v237, "NatIPClient", 11);
      v239 = 46;
      v97 = &v237;
      if ( *((_QWORD *)&v238 + 1) > 0xFu )
        v97 = (__int128 *)v237;
      v240 = v97;
      LODWORD(v150) = 127;
      v98 = boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get<std::string>(
              &v314,
              v301,
              &v237,
              v173);
      v205 = 2;
      v99 = (void *)v98;
      if ( *(_QWORD *)(v98 + 24) > 0xFu )
        v99 = *(void **)v98;
      v206 = v99;
      v207 = *(_QWORD *)(v98 + 16);
      v208 = 0;
      *(_OWORD *)v175 = 0;
      v176 = 0;
      std::string::_Construct<1,char const *>(v175, (const char *)&Str1, 0);
      LODWORD(v150) = 1023;
      v229 = 0;
      v230 = 0;
      std::string::_Construct<1,char const *>(&v229, "TransportIPServer", 17);
      v231 = 46;
      v100 = &v229;
      if ( *((_QWORD *)&v230 + 1) > 0xFu )
        v100 = (__int128 *)v229;
      v232 = v100;
      LODWORD(v150) = 2047;
      v101 = boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get<std::string>(
               &v314,
               v302,
               &v229,
               v175);
      v201 = 2;
      v102 = (void *)v101;
      if ( *(_QWORD *)(v101 + 24) > 0xFu )
        v102 = *(void **)v101;
      v202 = v102;
      v203 = *(_QWORD *)(v101 + 16);
      v204 = 0;
      *(_OWORD *)v167 = 0;
      v168 = 0;
      std::string::_Construct<1,char const *>(v167, (const char *)&Str1, 0);
      LODWORD(v150) = 0x3FFF;
      v233 = 0;
      v234 = 0;
      std::string::_Construct<1,char const *>(&v233, "TransportIPClient", 17);
      v235 = 46;
      v103 = &v233;
      if ( *((_QWORD *)&v234 + 1) > 0xFu )
        v103 = (__int128 *)v233;
      v236 = v103;
      LODWORD(v150) = 0x7FFF;
      v104 = boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get<std::string>(
               &v314,
               v303,
               &v233,
               v167);
      v197 = 2;
      v105 = (void *)v104;
      if ( *(_QWORD *)(v104 + 24) > 0xFu )
        v105 = *(void **)v104;
      v198 = v105;
      v199 = *(_QWORD *)(v104 + 16);
      v200 = 0;
      LODWORD(v150) = 0x1FFFF;
      v106 = boost::lexical_cast<std::string,unsigned int>(v304, v3 + 241);
      v193 = 2;
      v107 = (void *)v106;
      if ( *(_QWORD *)(v106 + 24) > 0xFu )
        v107 = *(void **)v106;
      v194 = v107;
      v195 = *(_QWORD *)(v106 + 16);
      v196 = 0;
      *(_OWORD *)v169 = 0;
      v170 = 0;
      std::string::_Construct<1,char const *>(v169, (const char *)&Str1, 0);
      LODWORD(v150) = 0xFFFFF;
      v292 = 0;
      v293 = 0;
      std::string::_Construct<1,char const *>(&v292, "GatewayRegion", 13);
      v294 = 46;
      v108 = &v292;
      if ( *((_QWORD *)&v293 + 1) > 0xFu )
        v108 = (__int128 *)v292;
      v295 = v108;
      LODWORD(v150) = 0x1FFFFF;
      v109 = boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get<std::string>(
               &v314,
               v305,
               &v292,
               v169);
      v189 = 2;
      v110 = (void *)v109;
      if ( *(_QWORD *)(v109 + 24) > 0xFu )
        v110 = *(void **)v109;
      v190 = v110;
      v191 = *(_QWORD *)(v109 + 16);
      v192 = 0;
      *(_OWORD *)v252 = 0;
      v253 = 0;
      std::string::_Construct<1,char const *>(v252, (const char *)&Str1, 0);
      LOBYTE(v111) = v149[0];
      LOBYTE(v112) = 46;
      boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>>::string_path<std::string,boost::property_tree::id_translator<std::string>>(
        v312,
        "GatewayCluster",
        v112,
        v111);
      LODWORD(v150) = 0x1FFFFFF;
      v113 = boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get<std::string>(
               &v314,
               v311,
               v312,
               v252);
      v185 = 2;
      v114 = (void *)v113;
      if ( *(_QWORD *)(v113 + 24) > 0xFu )
        v114 = *(void **)v113;
      v186 = v114;
      v187 = *(_QWORD *)(v113 + 16);
      v188 = 0;
      memset(v251, 0, sizeof(v251));
      std::string::_Construct<1,char const *>(v251, (const char *)&Str1, 0);
      LODWORD(v150) = 0xFFFFFFF;
      v288 = 0;
      v289 = 0;
      std::string::_Construct<1,char const *>(&v288, "GatewayInstanceID", 17);
      v290 = 46;
      v115 = &v288;
      if ( *((_QWORD *)&v289 + 1) > 0xFu )
        v115 = (__int128 *)v288;
      v291 = v115;
      LODWORD(v150) = 0x1FFFFFFF;
      v116 = boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get<std::string>(
               &v314,
               v306,
               &v288,
               v251);
      v181 = 2;
      v117 = (void *)v116;
      if ( *(_QWORD *)(v116 + 24) > 0xFu )
        v117 = *(void **)v116;
      v182 = v117;
      v183 = *(_QWORD *)(v116 + 16);
      v184 = 0;
      memset(v250, 0, sizeof(v250));
      std::string::_Construct<1,char const *>(v250, (const char *)&Str1, 0);
      v4 = -1;
      LODWORD(v150) = -1;
      v284 = 0;
      v285 = 0;
      std::string::_Construct<1,char const *>(&v284, "GatewayConnectionID", 19);
      v286 = 46;
      v118 = &v284;
      if ( *((_QWORD *)&v285 + 1) > 0xFu )
        v118 = (__int128 *)v284;
      v287 = v118;
      LODWORD(v151) = 1073741825;
      v119 = boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get<std::string>(
               &v314,
               v307,
               &v284,
               v250);
      v177 = 2;
      v120 = (void *)v119;
      if ( *(_QWORD *)(v119 + 24) > 0xFu )
        v120 = *(void **)v119;
      v178 = v120;
      v179 = *(_QWORD *)(v119 + 16);
      v180 = 0;
      LODWORD(v151) = 1073741831;
      memset(v249, 0, sizeof(v249));
      std::string::_Construct<1,char const *>(v249, (const char *)&Str1, 0);
      LODWORD(v151) = 1073741839;
      v280 = 0;
      v281 = 0;
      std::string::_Construct<1,char const *>(&v280, "TurnServerRegionClient", 22);
      v282 = 46;
      v121 = &v280;
      if ( *((_QWORD *)&v281 + 1) > 0xFu )
        v121 = (__int128 *)v280;
      v283 = v121;
      LODWORD(v151) = 1073741855;
      v122 = boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get<std::string>(
               &v314,
               v308,
               &v280,
               v249);
      v225 = 2;
      v123 = (void *)v122;
      if ( *(_QWORD *)(v122 + 24) > 0xFu )
        v123 = *(void **)v122;
      v226 = v123;
      v227 = *(_QWORD *)(v122 + 16);
      v228 = 0;
      LODWORD(v151) = 1073741951;
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
               v309,
               &v254,
               v248);
      v221 = 2;
      v126 = (void *)v125;
      if ( *(_QWORD *)(v125 + 24) > 0xFu )
        v126 = *(void **)v125;
      v222 = v126;
      v223 = *(_QWORD *)(v125 + 16);
      v224 = 0;
      LODWORD(v151) = 1073743871;
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
               v310,
               &v258,
               v247);
      v217 = 2;
      v129 = (void *)v128;
      if ( *(_QWORD *)(v128 + 24) > 0xFu )
        v129 = *(void **)v128;
      v218 = v129;
      v219 = *(_QWORD *)(v128 + 16);
      v220 = 0;
      LODWORD(v151) = 1073774591;
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
               v296,
               &v262,
               v246);
      v209 = 2;
      v132 = (void *)v131;
      if ( *(_QWORD *)(v131 + 24) > 0xFu )
        v132 = *(void **)v131;
      v210 = v132;
      v211 = *(_QWORD *)(v131 + 16);
      v212 = 0;
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
      LODWORD(v151) = 1074790399;
      v149[0] = boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get<bool>(
                  &v314,
                  &v266,
                  v152);
      memset(v245, 0, sizeof(v245));
      std::string::_Construct<1,char const *>(v245, (const char *)&Str1, 0);
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
               v297,
               &v270,
               v245);
      v213 = 2;
      v136 = (void *)v135;
      if ( *(_QWORD *)(v135 + 24) > 0xFu )
        v136 = *(void **)v135;
      v214 = v136;
      v215 = *(_QWORD *)(v135 + 16);
      v216 = 0;
      LODWORD(v151) = 1090519039;
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
               v298,
               &v274,
               v279);
      LODWORD(v159[0]) = 2;
      v139 = (void *)v138;
      if ( *(_QWORD *)(v138 + 24) > 0xFu )
        v139 = *(void **)v138;
      v159[1] = v139;
      v160 = *(_QWORD *)(v138 + 16);
      v161 = 0;
      LODWORD(v151) = 1342177279;
      v140 = Microsoft::Basix::ToString<enum Microsoft::Basix::Dct::ISmiles::LinkType>(&v155, &v313, 0, 6);
      LODWORD(v316[0]) = 2;
      v141 = (void *)v140;
      if ( *(_QWORD *)(v140 + 24) > 0xFu )
        v141 = *(void **)v140;
      v316[1] = v141;
      v317 = *(_QWORD *)(v140 + 16);
      v318 = 0;
      v17 = 0x7FFFFFFF;
      LODWORD(v153) = *(_DWORD *)(v315 + 152);
      Microsoft::Basix::Instrumentation::MultiLinkAdd::LogInterface::operator()<boost::container::small_vector<std::shared_ptr<Microsoft::Basix::Instrumentation::EventLogger>,4,void,void> const &>(
        (_DWORD)v3 + 1408,
        (_DWORD)v3 + 1288,
        (unsigned int)&v153,
        (unsigned int)v316,
        (__int64)v159,
        (__int64)&v213,
        (__int64)v149,
        (__int64)&v209,
        (__int64)&v217,
        (__int64)&v221,
        (__int64)&v225,
        (__int64)&v177,
        (__int64)&v181,
        (__int64)&v185,
        (__int64)&v189,
        (__int64)&v193,
        (__int64)&v197,
        (__int64)&v201,
        (__int64)&v205,
        (__int64)v162,
        (__int64)v164);
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
      std::string::_Tidy_deallocate(&v155);
    }
    if ( (v17 & 0x8000000) != 0 )
    {
      v17 &= ~0x8000000u;
      if ( v161 )
        operator delete(v159[1], v74);
    }
    if ( (v17 & 0x4000000) != 0 )
    {
      v17 &= ~0x4000000u;
      std::string::_Tidy_deallocate(v298);
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
      if ( v216 )
        operator delete(v214, v74);
    }
    if ( (v17 & 0x400000) != 0 )
    {
      v17 &= ~0x400000u;
      std::string::_Tidy_deallocate(v297);
    }
    if ( (v17 & 0x200000) != 0 )
    {
      v17 &= ~0x200000u;
      std::string::_Tidy_deallocate(&v270);
    }
    if ( (v17 & 0x100000) != 0 )
    {
      v17 &= ~0x100000u;
      std::string::_Tidy_deallocate(v245);
    }
    if ( (v17 & 0x80000) != 0 )
    {
      v17 &= ~0x80000u;
      std::string::_Tidy_deallocate(&v266);
    }
    if ( (v17 & 0x40000) != 0 )
    {
      v17 &= ~0x40000u;
      if ( v212 )
        operator delete(v210, v74);
    }
    if ( (v17 & 0x20000) != 0 )
    {
      v17 &= ~0x20000u;
      std::string::_Tidy_deallocate(v296);
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
      if ( v220 )
        operator delete(v218, v74);
    }
    if ( (v17 & 0x2000) != 0 )
    {
      LOWORD(v17) = v17 & 0xDFFF;
      std::string::_Tidy_deallocate(v310);
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
      if ( v224 )
        operator delete(v222, v74);
    }
    if ( (v17 & 0x200) != 0 )
    {
      LOWORD(v17) = v17 & 0xFDFF;
      std::string::_Tidy_deallocate(v309);
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
      if ( v228 )
        operator delete(v226, v74);
    }
    if ( (v17 & 0x20) != 0 )
    {
      LOBYTE(v17) = v17 & 0xDF;
      std::string::_Tidy_deallocate(v308);
    }
    if ( (v17 & 0x10) != 0 )
    {
      LOBYTE(v17) = v17 & 0xEF;
      std::string::_Tidy_deallocate(&v280);
    }
    if ( (v17 & 8) != 0 )
    {
      LOBYTE(v17) = v17 & 0xF7;
      std::string::_Tidy_deallocate(v249);
    }
    if ( (v17 & 4) != 0 )
    {
      LOBYTE(v17) = v17 & 0xFB;
      if ( v180 )
        operator delete(v178, v74);
    }
    if ( (v17 & 2) != 0 )
    {
      LOBYTE(v17) = v17 & 0xFD;
      std::string::_Tidy_deallocate(v307);
    }
    if ( (v17 & 1) != 0 )
      std::string::_Tidy_deallocate(&v284);
    if ( v4 < 0 )
    {
      v4 &= ~0x80000000;
      std::string::_Tidy_deallocate(v250);
    }
    if ( (v4 & 0x40000000) != 0 )
    {
      v4 &= ~0x40000000u;
      if ( v184 )
        operator delete(v182, v74);
    }
    if ( (v4 & 0x20000000) != 0 )
    {
      v4 &= ~0x20000000u;
      std::string::_Tidy_deallocate(v306);
    }
    if ( (v4 & 0x10000000) != 0 )
    {
      v4 &= ~0x10000000u;
      std::string::_Tidy_deallocate(&v288);
    }
    if ( (v4 & 0x8000000) != 0 )
    {
      v4 &= ~0x8000000u;
      std::string::_Tidy_deallocate(v251);
    }
    if ( (v4 & 0x4000000) != 0 )
    {
      v4 &= ~0x4000000u;
      if ( v188 )
        operator delete(v186, v74);
    }
    if ( (v4 & 0x2000000) != 0 )
    {
      v4 &= ~0x2000000u;
      std::string::_Tidy_deallocate(v311);
    }
    if ( (v4 & 0x1000000) != 0 )
    {
      v4 &= ~0x1000000u;
      std::string::_Tidy_deallocate(v312);
    }
    if ( (v4 & 0x800000) != 0 )
    {
      v4 &= ~0x800000u;
      std::string::_Tidy_deallocate(v252);
    }
    if ( (v4 & 0x400000) != 0 )
    {
      v4 &= ~0x400000u;
      if ( v192 )
        operator delete(v190, v74);
    }
    if ( (v4 & 0x200000) != 0 )
    {
      v4 &= ~0x200000u;
      std::string::_Tidy_deallocate(v305);
    }
    if ( (v4 & 0x100000) != 0 )
    {
      v4 &= ~0x100000u;
      std::string::_Tidy_deallocate(&v292);
    }
    if ( (v4 & 0x80000) != 0 )
    {
      v4 &= ~0x80000u;
      std::string::_Tidy_deallocate(v169);
    }
    if ( (v4 & 0x40000) != 0 )
    {
      v4 &= ~0x40000u;
      if ( v196 )
        operator delete(v194, v74);
    }
    if ( (v4 & 0x20000) != 0 )
    {
      v4 &= ~0x20000u;
      std::string::_Tidy_deallocate(v304);
    }
    if ( (v4 & 0x10000) != 0 && v200 )
      operator delete(v198, v74);
    if ( (v4 & 0x8000) != 0 )
    {
      LOWORD(v4) = v4 & 0x7FFF;
      std::string::_Tidy_deallocate(v303);
    }
    if ( (v4 & 0x4000) != 0 )
    {
      LOWORD(v4) = v4 & 0xBFFF;
      std::string::_Tidy_deallocate(&v233);
    }
    if ( (v4 & 0x2000) != 0 )
    {
      LOWORD(v4) = v4 & 0xDFFF;
      std::string::_Tidy_deallocate(v167);
    }
    if ( (v4 & 0x1000) != 0 )
    {
      LOWORD(v4) = v4 & 0xEFFF;
      if ( v204 )
        operator delete(v202, v74);
    }
    if ( (v4 & 0x800) != 0 )
    {
      LOWORD(v4) = v4 & 0xF7FF;
      std::string::_Tidy_deallocate(v302);
    }
    if ( (v4 & 0x400) != 0 )
    {
      LOWORD(v4) = v4 & 0xFBFF;
      std::string::_Tidy_deallocate(&v229);
    }
    if ( (v4 & 0x200) != 0 )
    {
      LOWORD(v4) = v4 & 0xFDFF;
      std::string::_Tidy_deallocate(v175);
    }
    if ( (v4 & 0x100) != 0 && v208 )
      operator delete(v206, v74);
    if ( (v4 & 0x80u) != 0 )
    {
      LOBYTE(v4) = v4 & 0x7F;
      std::string::_Tidy_deallocate(v301);
    }
    if ( (v4 & 0x40) != 0 )
    {
      LOBYTE(v4) = v4 & 0xBF;
      std::string::_Tidy_deallocate(&v237);
    }
    if ( (v4 & 0x20) != 0 )
    {
      LOBYTE(v4) = v4 & 0xDF;
      std::string::_Tidy_deallocate(v173);
    }
    if ( (v4 & 0x10) != 0 )
    {
      LOBYTE(v4) = v4 & 0xEF;
      if ( BYTE8(v163) )
        operator delete(v162[1], v74);
    }
    if ( (v4 & 8) != 0 )
    {
      LOBYTE(v4) = v4 & 0xF7;
      std::string::_Tidy_deallocate(v300);
    }
    if ( (v4 & 4) != 0 )
    {
      LOBYTE(v4) = v4 & 0xFB;
      std::string::_Tidy_deallocate(&v241);
    }
    if ( (v4 & 2) != 0 )
    {
      LOBYTE(v4) = v4 & 0xFD;
      std::string::_Tidy_deallocate(v171);
    }
    if ( (v4 & 1) != 0 && BYTE8(v165) )
      operator delete(v164[1], v74);
    boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(&v314);
    boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(&v319);
    std::string::_Tidy_deallocate(v321);
    result = boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(&v320);
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
0x18025a650  mov     [rsp-8+arg_10], rbx
0x18025a655  push    rbp
0x18025a656  push    rsi
0x18025a657  push    rdi
0x18025a658  push    r12
0x18025a65a  push    r13
0x18025a65c  push    r14
0x18025a65e  push    r15
0x18025a660  lea     rbp, [rsp-900h]
0x18025a668  mov     eax, 0A30h
0x18025a66d  call    _alloca_probe
0x18025a672  sub     rsp, rax
0x18025a675  mov     rax, cs:__security_cookie
0x18025a67c  xor     rax, rsp
0x18025a67f  mov     [rbp+930h+var_40], rax
0x18025a686  mov     rdi, rdx
0x18025a689  mov     [rbp+930h+var_3C8], rdx
0x18025a690  mov     r15, rcx
0x18025a693  mov     [rbp+930h+var_8F0], rcx
0x18025a697  mov     [rbp+930h+var_280], rdx
0x18025a69e  xor     r14d, r14d
0x18025a6a1  mov     r12d, r14d
0x18025a6a4  mov     dword ptr [rbp+930h+var_9A8], r14d
0x18025a6a8  mov     dword ptr [rbp+930h+var_9A0], r14d
0x18025a6ac  xorps   xmm0, xmm0
0x18025a6af  movups  [rbp+930h+var_B0], xmm0
0x18025a6b6  xorps   xmm1, xmm1
0x18025a6b9  movdqu  xmmword ptr [rbp+930h+var_950], xmm1
0x18025a6be  mov     rdx, [rdx+8]
0x18025a6c2  test    rdx, rdx
0x18025a6c5  jz      short loc_18025A6EB
0x18025a6c7  mov     eax, [rdx+8]
0x18025a6ca  jmp     short loc_18025A6D6
0x18025a6cc  lea     ecx, [rax+1]
0x18025a6cf  lock cmpxchg [rdx+8], ecx
0x18025a6d4  jz      short loc_18025A6DC
0x18025a6d6  test    eax, eax
0x18025a6d8  jnz     short loc_18025A6CC
0x18025a6da  jmp     short loc_18025A6EB
0x18025a6dc  mov     rax, [rdi]
0x18025a6df  mov     [rbp+930h+var_950], rax
0x18025a6e3  mov     rax, [rdi+8]
0x18025a6e7  mov     [rbp+930h+var_950+8], rax
0x18025a6eb  lea     rdx, [rbp+930h+var_950]
0x18025a6ef  lea     rcx, [rbp+930h+var_B0]
0x18025a6f6  call    ??$dynamic_pointer_cast@VLinkDataV3@Dct@Basix@Microsoft@@VLinkData@234@@std@@YA?AV?$shared_ptr@VLinkDataV3@Dct@Basix@Microsoft@@@0@$$QEAV?$shared_ptr@VLinkData@Dct@Basix@Microsoft@@@0@@Z; std::dynamic_pointer_cast<Microsoft::Basix::Dct::LinkDataV3,Microsoft::Basix::Dct::LinkData>(std::shared_ptr<Microsoft::Basix::Dct::LinkData> &&)
0x18025a6fb  nop
0x18025a6fc  or      esi, 0FFFFFFFFh
0x18025a6ff  mov     rbx, [rbp+930h+var_950+8]
0x18025a703  test    rbx, rbx
0x18025a706  jz      short loc_18025A73D
0x18025a708  mov     eax, esi
0x18025a70a  lock xadd [rbx+8], eax
0x18025a70f  add     eax, esi
0x18025a711  jnz     short loc_18025A73D
0x18025a713  mov     rax, [rbx]
0x18025a716  mov     rcx, rbx
0x18025a719  mov     rax, [rax]
0x18025a71c  call    cs:__guard_dispatch_icall_fptr
0x18025a722  mov     eax, esi
0x18025a724  lock xadd [rbx+0Ch], eax
0x18025a729  add     eax, esi
0x18025a72b  jnz     short loc_18025A73D
0x18025a72d  mov     rax, [rbx]
0x18025a730  mov     rcx, rbx
0x18025a733  mov     rax, [rax+8]
0x18025a737  call    cs:__guard_dispatch_icall_fptr
0x18025a73d  mov     rcx, r15; this
0x18025a740  call    ?IsClosed@BasicStateManagement@detail@Dct@Basix@Microsoft@@QEBA_NXZ; Microsoft::Basix::Dct::detail::BasicStateManagement::IsClosed(void)
0x18025a745  test    al, al
0x18025a747  jz      short loc_18025A7AD
0x18025a749  mov     rax, qword ptr [rbp+930h+var_B0]
0x18025a750  mov     rcx, [rax+68h]
0x18025a754  mov     rax, [rcx]
0x18025a757  mov     rax, [rax+10h]
0x18025a75b  call    cs:__guard_dispatch_icall_fptr
0x18025a761  nop
0x18025a762  mov     rbx, qword ptr [rbp+930h+var_B0+8]
0x18025a769  test    rbx, rbx
0x18025a76c  jz      short loc_18025A7A4
0x18025a76e  mov     eax, esi
0x18025a770  lock xadd [rbx+8], eax
0x18025a775  add     eax, esi
0x18025a777  jnz     short loc_18025A7A4
0x18025a779  mov     rax, [rbx]
0x18025a77c  mov     rcx, rbx
0x18025a77f  mov     rax, [rax]
0x18025a782  call    cs:__guard_dispatch_icall_fptr
0x18025a788  mov     eax, esi
0x18025a78a  lock xadd [rbx+0Ch], eax
0x18025a78f  add     eax, esi
0x18025a791  jnz     short loc_18025A7A4
0x18025a793  mov     rax, [rbx]
0x18025a796  mov     rcx, rbx
0x18025a799  mov     rax, [rax+8]
0x18025a79d  call    cs:__guard_dispatch_icall_fptr
0x18025a7a3  nop
0x18025a7a4  mov     rcx, [rdi+8]
0x18025a7a8  jmp     loc_18025CA5D
0x18025a7ad  lea     rbx, [r15+728h]
0x18025a7b4  mov     [rbp+930h+var_990], rbx
0x18025a7b8  mov     rcx, rbx; _Mtx_t
0x18025a7bb  call    _Mtx_lock
0x18025a7c0  test    eax, eax
0x18025a7c2  jnz     loc_18025CAB6
0x18025a7c8  cmp     dword ptr [rbx+4Ch], 7FFFFFFFh
0x18025a7cf  jz      loc_18025CAA4
0x18025a7d5  lea     rsi, [r15+5F8h]
0x18025a7dc  lea     rdx, [rbp+930h+var_B0]
0x18025a7e3  mov     rcx, rsi
0x18025a7e6  call    ?insert@?$IterationSafeStore@V?$shared_ptr@VLinkDataDisabled@Dct@Basix@Microsoft@@@std@@U?$equal_to@V?$shared_ptr@VLinkDataDisabled@Dct@Basix@Microsoft@@@std@@@2@@Containers@Basix@Microsoft@@QEAAXAEBV?$shared_ptr@VLinkDataDisabled@Dct@Basix@Microsoft@@@std@@@Z; Microsoft::Basix::Containers::IterationSafeStore<std::shared_ptr<Microsoft::Basix::Dct::LinkDataDisabled>,std::equal_to<std::shared_ptr<Microsoft::Basix::Dct::LinkDataDisabled>>>::insert(std::shared_ptr<Microsoft::Basix::Dct::LinkDataDisabled> const &)
0x18025a7eb  mov     rcx, rsi
0x18025a7ee  call    ?size@?$IterationSafeStore@V?$shared_ptr@VLinkDataDisabled@Dct@Basix@Microsoft@@@std@@U?$equal_to@V?$shared_ptr@VLinkDataDisabled@Dct@Basix@Microsoft@@@std@@@2@@Containers@Basix@Microsoft@@QEBA_KXZ; Microsoft::Basix::Containers::IterationSafeStore<std::shared_ptr<Microsoft::Basix::Dct::LinkDataDisabled>,std::equal_to<std::shared_ptr<Microsoft::Basix::Dct::LinkDataDisabled>>>::size(void)
0x18025a7f3  mov     [rbp+930h+var_988], rax
0x18025a7f7  xorps   xmm0, xmm0
0x18025a7fa  movups  [rbp+930h+var_980], xmm0
0x18025a7fe  xorps   xmm1, xmm1
0x18025a801  movdqu  [rbp+930h+var_970], xmm1
0x18025a806  mov     r8d, 29h ; ')'
0x18025a80c  lea     rdx, aMicrosoftBasix_330; "Microsoft::Basix::Dct.Smiles.LinkPoolSi"...
0x18025a813  lea     rcx, [rbp+930h+var_980]
0x18025a817  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18025a81c  mov     [rbp+930h+var_960], 2Eh ; '.'
0x18025a820  lea     rax, [rbp+930h+var_980]
0x18025a824  cmp     qword ptr [rbp+930h+var_970+8], 0Fh
0x18025a829  cmova   rax, qword ptr [rbp+930h+var_980]
0x18025a82e  mov     [rbp+930h+var_958], rax
0x18025a832  lea     r8, [rbp+930h+var_988]
0x18025a836  lea     rdx, [rbp+930h+var_980]
0x18025a83a  lea     rcx, [r15+3C0h]
0x18025a841  call    ??$put@_K@?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEAAAEAV012@AEBV?$string_path@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$id_translator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@property_tree@boost@@@12@AEB_K@Z; boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::put<unsigned __int64>(boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>> const &,unsigned __int64 const &)
0x18025a846  nop
0x18025a847  lea     rcx, [rbp+930h+var_980]
0x18025a84b  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18025a850  inc     dword ptr [r15+5F0h]
0x18025a857  mov     ecx, [r15+5F0h]
0x18025a85e  mov     rax, qword ptr [rbp+930h+var_B0]
0x18025a865  mov     [rax+98h], ecx
0x18025a86b  lea     rcx, [r15+688h]
0x18025a872  lea     rdx, [rbp+930h+var_B0]
0x18025a879  call    ?erase@?$IterationSafeStore@V?$shared_ptr@VLinkDataV3@Dct@Basix@Microsoft@@@std@@U?$equal_to@V?$shared_ptr@VLinkDataV3@Dct@Basix@Microsoft@@@std@@@2@@Containers@Basix@Microsoft@@QEAAXAEBV?$shared_ptr@VLinkDataV3@Dct@Basix@Microsoft@@@std@@@Z; Microsoft::Basix::Containers::IterationSafeStore<std::shared_ptr<Microsoft::Basix::Dct::LinkDataV3>,std::equal_to<std::shared_ptr<Microsoft::Basix::Dct::LinkDataV3>>>::erase(std::shared_ptr<Microsoft::Basix::Dct::LinkDataV3> const &)
0x18025a87e  mov     [r15+5E1h], r14b
0x18025a885  mov     rcx, rbx; _Mtx_t
0x18025a888  call    _Mtx_unlock
0x18025a88d  xorps   xmm0, xmm0
0x18025a890  movups  [rbp+930h+var_70], xmm0
0x18025a897  mov     rsi, qword ptr [rbp+930h+var_B0]
0x18025a89e  mov     rbx, [rsi+68h]
0x18025a8a2  movups  xmmword ptr [rbp+930h+var_910], xmm0
0x18025a8a6  xorps   xmm1, xmm1
0x18025a8a9  movdqu  [rbp+930h+var_900], xmm1
0x18025a8ae  mov     r8d, 28h ; '('
0x18025a8b4  lea     rdx, aMicrosoftBasix_183; "Microsoft::Basix::Dct.Smiles.AddLinkInf"...
0x18025a8bb  lea     rcx, [rbp+930h+var_910]
0x18025a8bf  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18025a8c4  nop
0x18025a8c5  lea     r8, [rbp+930h+var_910]
0x18025a8c9  lea     rdx, [rbp+930h+var_A0]
0x18025a8d0  lea     rcx, [rbx+28h]
0x18025a8d4  call    ?GetProperty@IPropertyAware@detail@Dct@Basix@Microsoft@@QEBA?AV?$PTreeResult@V?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@Containers@45@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Microsoft::Basix::Dct::detail::IPropertyAware::GetProperty(std::string const &)
0x18025a8d9  nop
0x18025a8da  mov     r8b, [rbp+930h+var_9B0]
0x18025a8de  lea     rdx, [rbp+930h+var_70]
0x18025a8e5  mov     rcx, rax
0x18025a8e8  call    ?As@?$PTreeResult@V?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@Containers@Basix@Microsoft@@AEAA?AV?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@U?$identity@V?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@1234@@Z; Microsoft::Basix::Containers::PTreeResult<boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>>::As(Microsoft::Basix::Containers::PTreeResult<boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>>::identity<boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>>)
0x18025a8ed  mov     r13d, 40000000h
0x18025a8f3  lea     rcx, [rbp+930h+var_A0]
0x18025a8fa  call    ??1?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEAA@XZ; boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(void)
0x18025a8ff  nop
0x18025a900  lea     rcx, [rbp+930h+var_910]
0x18025a904  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18025a909  mov     rbx, [rsi+68h]
0x18025a90d  xorps   xmm0, xmm0
0x18025a910  movups  xmmword ptr [rbp+930h+var_930], xmm0
0x18025a914  xorps   xmm1, xmm1
0x18025a917  movdqu  [rbp+930h+var_920], xmm1
0x18025a91c  mov     r8d, 25h ; '%'
0x18025a922  lea     rdx, aMicrosoftBasix_102; "Microsoft::Basix::Dct.Smiles.LinkType"
0x18025a929  lea     rcx, [rbp+930h+var_930]
0x18025a92d  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18025a932  nop
0x18025a933  lea     r8, [rbp+930h+var_930]
0x18025a937  lea     rdx, [rbp+930h+var_950]
0x18025a93b  lea     rcx, [rbx+28h]
0x18025a93f  call    ?GetProperty@IPropertyAware@detail@Dct@Basix@Microsoft@@QEBA?AV?$PTreeResult@V?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@@Containers@45@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; Microsoft::Basix::Dct::detail::IPropertyAware::GetProperty(std::string const &)
0x18025a944  nop
0x18025a945  mov     dword ptr [rbp+930h+var_9A0], r14d
0x18025a949  lea     rdx, [rbp+930h+var_9A0]
0x18025a94d  mov     rcx, [rax+10h]
0x18025a951  call    ??$get_value@W4LinkType@ISmiles@Dct@Basix@Microsoft@@@?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEBA?AW4LinkType@ISmiles@Dct@Basix@Microsoft@@AEBW434567@@Z; boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get_value<Microsoft::Basix::Dct::ISmiles::LinkType>(Microsoft::Basix::Dct::ISmiles::LinkType const &)
0x18025a956  mov     [rbp+930h+var_C8], eax
0x18025a95c  lea     rcx, [rbp+930h+var_950]
0x18025a960  call    ??1?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEAA@XZ; boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::~basic_ptree<std::string,boost::any,std::less<std::string>>(void)
0x18025a965  nop
0x18025a966  lea     rcx, [rbp+930h+var_930]
0x18025a96a  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18025a96f  mov     eax, [rbp+930h+var_C8]
0x18025a975  mov     [rsi+50h], eax
0x18025a978  xorps   xmm0, xmm0
0x18025a97b  movups  [rbp+930h+var_980], xmm0
0x18025a97f  xorps   xmm1, xmm1
0x18025a982  movdqu  [rbp+930h+var_970], xmm1
0x18025a987  mov     r8d, 7
0x18025a98d  lea     rdx, aSummary; "Summary"
0x18025a994  lea     rcx, [rbp+930h+var_980]
0x18025a998  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x18025a99d  mov     [rbp+930h+var_960], 2Eh ; '.'
0x18025a9a1  lea     rax, [rbp+930h+var_980]
0x18025a9a5  mov     edi, 0Fh
0x18025a9aa  cmp     qword ptr [rbp+930h+var_970+8], rdi
0x18025a9ae  cmova   rax, qword ptr [rbp+930h+var_980]
0x18025a9b3  mov     [rbp+930h+var_958], rax
0x18025a9b7  lea     r9, Str1
0x18025a9be  lea     r8, [rbp+930h+var_980]
0x18025a9c2  lea     rdx, [rbp+930h+var_60]
0x18025a9c9  lea     rcx, [rbp+930h+var_70]
0x18025a9d0  call    ??$get@D@?$basic_ptree@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@Vany@boost@@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@property_tree@boost@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$string_path@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$id_translator@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@property_tree@boost@@@12@PEBD@Z; boost::property_tree::basic_ptree<std::string,boost::any,std::less<std::string>>::get<char>(boost::property_tree::string_path<std::string,boost::property_tree::id_translator<std::string>> const &,char const *)
0x18025a9d5  nop
0x18025a9d6  lea     rcx, [rbp+930h+var_980]
0x18025a9da  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18025a9df  xorps   xmm0, xmm0
0x18025a9e2  movups  xmmword ptr [rbp+930h+var_A0], xmm0
0x18025a9e9  lea     rcx, [rbp+930h+var_A0]
0x18025a9f0  call    ??$SelectEvent@VTraceCheckpoint@Basix@Microsoft@@@TraceManager@Instrumentation@Basix@Microsoft@@SA?AV?$shared_ptr@V?$Event@VTraceCheckpoint@Basix@Microsoft@@@Instrumentation@Basix@Microsoft@@@std@@XZ; Microsoft::Basix::Instrumentation::TraceManager::SelectEvent<Microsoft::Basix::TraceCheckpoint>(void)
0x18025a9f5  nop
0x18025a9f6  mov     rax, [rbp+930h+var_A0]
0x18025a9fd  test    rax, rax
0x18025aa00  jz      loc_18025B179
0x18025aa06  cmp     [rax+80h], r14b
0x18025aa0d  jz      loc_18025B179
0x18025aa13  lea     rax, [rbp+930h+var_8A8]
0x18025aa1a  mov     [rbp+930h+var_988], rax
0x18025aa1e  lea     rbx, asc_1803D71C8; "\""
0x18025aa25  mov     rdx, rbx
0x18025aa28  lea     rcx, [rbp+930h+var_980]
0x18025aa2c  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18025aa31  mov     r15, rax
0x18025aa34  lea     r14, [rbp+930h+var_60]
0x18025aa3b  cmp     [rbp+930h+var_48], rdi
0x18025aa42  cmova   r14, [rbp+930h+var_60]
0x18025aa4a  mov     rdx, rbx
0x18025aa4d  lea     rcx, [rbp+930h+var_2A0]
0x18025aa54  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18025aa59  mov     rsi, rax
0x18025aa5c  lea     rdx, asc_1803D71C4; ":"
0x18025aa63  lea     rcx, [rbp+930h+var_2C0]
0x18025aa6a  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18025aa6f  mov     rdi, rax
0x18025aa72  mov     rdx, rbx
0x18025aa75  lea     rcx, [rbp+930h+var_2E0]
0x18025aa7c  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18025aa81  mov     rbx, rax
0x18025aa84  lea     rdx, asc_1803D71C8; "\""
0x18025aa8b  lea     rcx, [rbp+930h+var_138]
0x18025aa92  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18025aa97  nop
0x18025aa98  lea     r8, aAdditionalinfo; "AdditionalInfo"
0x18025aa9f  mov     rdx, rax
0x18025aaa2  lea     rcx, [rbp+930h+var_158]
0x18025aaa9  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@QEBD@Z; std::operator+<char>(std::string &&,char const * const)
0x18025aaae  nop
0x18025aaaf  mov     r9, rbx
0x18025aab2  mov     r8, rax
0x18025aab5  mov     dl, [rbp+930h+var_9B0]
0x18025aab8  lea     rcx, [rbp+930h+var_848]
0x18025aabf  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::string::string(std::_String_constructor_concat_tag,std::string &,std::string &)
0x18025aac4  nop
0x18025aac5  mov     r9, rdi
0x18025aac8  lea     r8, [rbp+930h+var_848]
0x18025aacf  mov     dl, [rbp+930h+var_9B0]
0x18025aad2  lea     rcx, [rbp+930h+var_828]
0x18025aad9  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::string::string(std::_String_constructor_concat_tag,std::string &,std::string &)
0x18025aade  nop
0x18025aadf  mov     r9, rsi
0x18025aae2  lea     r8, [rbp+930h+var_828]
0x18025aae9  mov     dl, [rbp+930h+var_9B0]
0x18025aaec  lea     rcx, [rbp+930h+var_808]
0x18025aaf3  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::string::string(std::_String_constructor_concat_tag,std::string &,std::string &)
0x18025aaf8  nop
0x18025aaf9  mov     r8, r14
0x18025aafc  lea     rdx, [rbp+930h+var_808]
0x18025ab03  lea     rcx, [rbp+930h+var_178]
0x18025ab0a  call    ??$?HDU?$char_traits@D@std@@V?$allocator@D@1@@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAV10@QEBD@Z; std::operator+<char>(std::string &&,char const * const)
0x18025ab0f  nop
0x18025ab10  mov     r9, r15
0x18025ab13  mov     r8, rax
0x18025ab16  mov     dl, [rbp+930h+var_9B0]
0x18025ab19  lea     rcx, [rbp+930h+var_8A8]
0x18025ab20  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::string::string(std::_String_constructor_concat_tag,std::string &,std::string &)
0x18025ab25  nop
0x18025ab26  lea     rax, [rbp+930h+var_888]
0x18025ab2d  mov     [rbp+930h+var_990], rax
0x18025ab31  mov     r15, [rbp+930h+var_8F0]
0x18025ab35  mov     edx, [r15+5D4h]
0x18025ab3c  lea     rcx, [rbp+930h+var_7E8]
0x18025ab43  call    ??$_Integral_to_string@DI@std@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@I@Z; std::_Integral_to_string<char,uint>(uint)
0x18025ab48  nop
0x18025ab49  lea     r14, asc_1803D71C4; ":"
0x18025ab50  mov     rdx, r14
0x18025ab53  lea     rcx, [rbp+930h+var_198]
  ... truncated ...
```
