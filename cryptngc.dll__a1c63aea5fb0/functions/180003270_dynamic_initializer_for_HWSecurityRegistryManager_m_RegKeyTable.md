# _dynamic_initializer_for__HWSecurityRegistryManager::m_RegKeyTable__

- ea: `0x180003270`
- end: `0x1800046d8`
- name: `_dynamic_initializer_for__HWSecurityRegistryManager::m_RegKeyTable__`
- size: `5224`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180001c50`
- `0x180001f70`
- `0x1800020c0`
- `0x180002d10`
- `0x180003270`
- `0x180004720`
- `0x18002cc98`
- `0x18002dfd0`
- `0x18002e1f4`
- `0x180046c70`
- `0x180046ce0`

## string_xrefs

- `0x180003439`: `System\CurrentControlSet\Services\TPM\WMI`
- `0x180003b98`: `System\CurrentControlSet\Services\TPM\WMI`
- `0x180003dfe`: `System\CurrentControlSet\Services\TPM\WMI`
- `0x18000405f`: `System\CurrentControlSet\Services\TPM\WMI`
- `0x180003688`: `System\CurrentControlSet\Services\TPM`
- `0x180003903`: `System\CurrentControlSet\Services\TPM`
- `0x180003cce`: `System\CurrentControlSet\Services\TPM\WMI\HealthCert`
- `0x180003dcf`: `TaskStates`
- `0x18000451e`: `System\CurrentControlSet\Control\IntegrityServices`
- `0x180003557`: `System\CurrentControlSet\Services`
- `0x180004192`: `System\CurrentControlSet\Services\TPM\WMI\Endorsement`
- `0x180003f2f`: `System\CurrentControlSet\Services\TPM\WMI\TaskStates`

## pseudocode

```c
// Hidden C++ exception states: #wind=96
int dynamic_initializer_for__HWSecurityRegistryManager::m_RegKeyTable__()
{
  __int64 v0; // rbx
  __int64 v1; // r8
  __int64 v2; // r8
  __int64 v3; // r8
  __int64 v4; // r8
  __int64 v5; // r8
  __int64 v6; // rcx
  _QWORD v8[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v9; // [rsp+70h] [rbp-90h] BYREF
  __int64 v10; // [rsp+80h] [rbp-80h]
  __int64 v11; // [rsp+88h] [rbp-78h]
  __int128 v12; // [rsp+90h] [rbp-70h] BYREF
  __int64 v13; // [rsp+A0h] [rbp-60h]
  __int64 v14; // [rsp+A8h] [rbp-58h]
  __int128 v15; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v16; // [rsp+C0h] [rbp-40h]
  __int64 v17; // [rsp+C8h] [rbp-38h]
  __int128 v18; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v19; // [rsp+E0h] [rbp-20h]
  __int64 v20; // [rsp+E8h] [rbp-18h]
  __int128 v21; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v22; // [rsp+100h] [rbp+0h]
  __int64 v23; // [rsp+108h] [rbp+8h]
  __int128 v24; // [rsp+110h] [rbp+10h] BYREF
  __int64 v25; // [rsp+120h] [rbp+20h]
  __int64 v26; // [rsp+128h] [rbp+28h]
  __int128 v27; // [rsp+130h] [rbp+30h] BYREF
  __int64 v28; // [rsp+140h] [rbp+40h]
  __int64 v29; // [rsp+148h] [rbp+48h]
  __int128 v30; // [rsp+150h] [rbp+50h] BYREF
  __int64 v31; // [rsp+160h] [rbp+60h]
  __int64 v32; // [rsp+168h] [rbp+68h]
  __int128 v33; // [rsp+170h] [rbp+70h] BYREF
  __int64 v34; // [rsp+180h] [rbp+80h]
  __int64 v35; // [rsp+188h] [rbp+88h]
  __int128 v36; // [rsp+190h] [rbp+90h] BYREF
  __int64 v37; // [rsp+1A0h] [rbp+A0h]
  __int64 v38; // [rsp+1A8h] [rbp+A8h]
  __int128 v39; // [rsp+1B0h] [rbp+B0h] BYREF
  __int64 v40; // [rsp+1C0h] [rbp+C0h]
  __int64 v41; // [rsp+1C8h] [rbp+C8h]
  __int128 v42; // [rsp+1D0h] [rbp+D0h] BYREF
  __int64 v43; // [rsp+1E0h] [rbp+E0h]
  __int64 v44; // [rsp+1E8h] [rbp+E8h]
  __int128 v45; // [rsp+1F0h] [rbp+F0h] BYREF
  __int64 v46; // [rsp+200h] [rbp+100h]
  __int64 v47; // [rsp+208h] [rbp+108h]
  __int128 v48; // [rsp+210h] [rbp+110h] BYREF
  __int64 v49; // [rsp+220h] [rbp+120h]
  __int64 v50; // [rsp+228h] [rbp+128h]
  __int128 v51; // [rsp+230h] [rbp+130h] BYREF
  __int64 v52; // [rsp+240h] [rbp+140h]
  __int64 v53; // [rsp+248h] [rbp+148h]
  __int128 v54; // [rsp+250h] [rbp+150h] BYREF
  __int64 v55; // [rsp+260h] [rbp+160h]
  __int64 v56; // [rsp+268h] [rbp+168h]
  __int128 v57; // [rsp+270h] [rbp+170h] BYREF
  __int64 v58; // [rsp+280h] [rbp+180h]
  __int64 v59; // [rsp+288h] [rbp+188h]
  __int128 v60; // [rsp+290h] [rbp+190h] BYREF
  __int64 v61; // [rsp+2A0h] [rbp+1A0h]
  __int64 v62; // [rsp+2A8h] [rbp+1A8h]
  __int128 v63; // [rsp+2B0h] [rbp+1B0h] BYREF
  __int64 v64; // [rsp+2C0h] [rbp+1C0h]
  __int64 v65; // [rsp+2C8h] [rbp+1C8h]
  __int128 v66; // [rsp+2D0h] [rbp+1D0h] BYREF
  __int64 v67; // [rsp+2E0h] [rbp+1E0h]
  __int64 v68; // [rsp+2E8h] [rbp+1E8h]
  __int128 v69; // [rsp+2F0h] [rbp+1F0h] BYREF
  __int64 v70; // [rsp+300h] [rbp+200h]
  __int64 v71; // [rsp+308h] [rbp+208h]
  __int128 v72; // [rsp+310h] [rbp+210h] BYREF
  __int64 v73; // [rsp+320h] [rbp+220h]
  __int64 v74; // [rsp+328h] [rbp+228h]
  __int128 v75; // [rsp+330h] [rbp+230h] BYREF
  __int64 v76; // [rsp+340h] [rbp+240h]
  __int64 v77; // [rsp+348h] [rbp+248h]
  __int128 v78; // [rsp+350h] [rbp+250h] BYREF
  __int64 v79; // [rsp+360h] [rbp+260h]
  __int64 v80; // [rsp+368h] [rbp+268h]
  __int128 v81; // [rsp+370h] [rbp+270h] BYREF
  __int64 v82; // [rsp+380h] [rbp+280h]
  __int64 v83; // [rsp+388h] [rbp+288h]
  __int128 v84; // [rsp+390h] [rbp+290h] BYREF
  __int64 v85; // [rsp+3A0h] [rbp+2A0h]
  __int64 v86; // [rsp+3A8h] [rbp+2A8h]
  __int128 v87; // [rsp+3B0h] [rbp+2B0h] BYREF
  __int64 v88; // [rsp+3C0h] [rbp+2C0h]
  __int64 v89; // [rsp+3C8h] [rbp+2C8h]
  __int128 v90; // [rsp+3D0h] [rbp+2D0h] BYREF
  __int64 v91; // [rsp+3E0h] [rbp+2E0h]
  __int64 v92; // [rsp+3E8h] [rbp+2E8h]
  __int128 v93; // [rsp+3F0h] [rbp+2F0h] BYREF
  __int64 v94; // [rsp+400h] [rbp+300h]
  __int64 v95; // [rsp+408h] [rbp+308h]
  __int128 v96; // [rsp+410h] [rbp+310h] BYREF
  __int64 v97; // [rsp+420h] [rbp+320h]
  __int64 v98; // [rsp+428h] [rbp+328h]
  __int128 v99; // [rsp+430h] [rbp+330h] BYREF
  __int64 v100; // [rsp+440h] [rbp+340h]
  __int64 v101; // [rsp+448h] [rbp+348h]
  __int128 v102; // [rsp+450h] [rbp+350h] BYREF
  __int64 v103; // [rsp+460h] [rbp+360h]
  __int64 v104; // [rsp+468h] [rbp+368h]
  __int128 v105; // [rsp+470h] [rbp+370h] BYREF
  __int64 v106; // [rsp+480h] [rbp+380h]
  __int64 v107; // [rsp+488h] [rbp+388h]
  __int128 v108; // [rsp+490h] [rbp+390h] BYREF
  __int64 v109; // [rsp+4A0h] [rbp+3A0h]
  __int64 v110; // [rsp+4A8h] [rbp+3A8h]
  __int128 v111; // [rsp+4B0h] [rbp+3B0h] BYREF
  __int64 v112; // [rsp+4C0h] [rbp+3C0h]
  __int64 v113; // [rsp+4C8h] [rbp+3C8h]
  __int128 v114; // [rsp+4D0h] [rbp+3D0h] BYREF
  __int64 v115; // [rsp+4E0h] [rbp+3E0h]
  __int64 v116; // [rsp+4E8h] [rbp+3E8h]
  __int128 v117; // [rsp+4F0h] [rbp+3F0h] BYREF
  __int64 v118; // [rsp+500h] [rbp+400h]
  __int64 v119; // [rsp+508h] [rbp+408h]
  __int128 v120; // [rsp+510h] [rbp+410h] BYREF
  __int64 v121; // [rsp+520h] [rbp+420h]
  __int64 v122; // [rsp+528h] [rbp+428h]
  __int128 v123; // [rsp+530h] [rbp+430h] BYREF
  __int64 v124; // [rsp+540h] [rbp+440h]
  __int64 v125; // [rsp+548h] [rbp+448h]
  __int128 v126; // [rsp+550h] [rbp+450h] BYREF
  __int64 v127; // [rsp+560h] [rbp+460h]
  __int64 v128; // [rsp+568h] [rbp+468h]
  __int128 v129; // [rsp+570h] [rbp+470h] BYREF
  __int64 v130; // [rsp+580h] [rbp+480h]
  __int64 v131; // [rsp+588h] [rbp+488h]
  __int128 v132; // [rsp+590h] [rbp+490h] BYREF
  __int64 v133; // [rsp+5A0h] [rbp+4A0h]
  __int64 v134; // [rsp+5A8h] [rbp+4A8h]
  __int128 v135; // [rsp+5B0h] [rbp+4B0h] BYREF
  __int64 v136; // [rsp+5C0h] [rbp+4C0h]
  __int64 v137; // [rsp+5C8h] [rbp+4C8h]
  __int128 v138; // [rsp+5D0h] [rbp+4D0h] BYREF
  __int64 v139; // [rsp+5E0h] [rbp+4E0h]
  __int64 v140; // [rsp+5E8h] [rbp+4E8h]
  __int128 v141; // [rsp+5F0h] [rbp+4F0h] BYREF
  __int64 v142; // [rsp+600h] [rbp+500h]
  __int64 v143; // [rsp+608h] [rbp+508h]
  __int128 v144; // [rsp+610h] [rbp+510h] BYREF
  __int64 v145; // [rsp+620h] [rbp+520h]
  __int64 v146; // [rsp+628h] [rbp+528h]
  __int128 v147; // [rsp+630h] [rbp+530h] BYREF
  __int64 v148; // [rsp+640h] [rbp+540h]
  __int64 v149; // [rsp+648h] [rbp+548h]
  __int128 v150; // [rsp+650h] [rbp+550h] BYREF
  __int64 v151; // [rsp+660h] [rbp+560h]
  __int64 v152; // [rsp+668h] [rbp+568h]
  __int128 v153; // [rsp+670h] [rbp+570h] BYREF
  __int64 v154; // [rsp+680h] [rbp+580h]
  __int64 v155; // [rsp+688h] [rbp+588h]
  __int128 v156; // [rsp+690h] [rbp+590h] BYREF
  __int64 v157; // [rsp+6A0h] [rbp+5A0h]
  __int64 v158; // [rsp+6A8h] [rbp+5A8h]
  __int128 v159; // [rsp+6B0h] [rbp+5B0h] BYREF
  __int64 v160; // [rsp+6C0h] [rbp+5C0h]
  __int64 v161; // [rsp+6C8h] [rbp+5C8h]
  __int128 v162; // [rsp+6D0h] [rbp+5D0h] BYREF
  __int64 v163; // [rsp+6E0h] [rbp+5E0h]
  __int64 v164; // [rsp+6E8h] [rbp+5E8h]
  __int128 v165; // [rsp+6F0h] [rbp+5F0h] BYREF
  __int64 v166; // [rsp+700h] [rbp+600h]
  __int64 v167; // [rsp+708h] [rbp+608h]
  __int128 v168; // [rsp+710h] [rbp+610h] BYREF
  __int64 v169; // [rsp+720h] [rbp+620h]
  __int64 v170; // [rsp+728h] [rbp+628h]
  __int128 v171; // [rsp+730h] [rbp+630h] BYREF
  __int64 v172; // [rsp+740h] [rbp+640h]
  __int64 v173; // [rsp+748h] [rbp+648h]
  __int128 v174; // [rsp+750h] [rbp+650h] BYREF
  __int64 v175; // [rsp+760h] [rbp+660h]
  __int64 v176; // [rsp+768h] [rbp+668h]
  __int128 v177; // [rsp+770h] [rbp+670h] BYREF
  __int64 v178; // [rsp+780h] [rbp+680h]
  __int64 v179; // [rsp+788h] [rbp+688h]
  __int128 v180; // [rsp+790h] [rbp+690h] BYREF
  __int64 v181; // [rsp+7A0h] [rbp+6A0h]
  __int64 v182; // [rsp+7A8h] [rbp+6A8h]
  __int128 v183; // [rsp+7B0h] [rbp+6B0h] BYREF
  __int64 v184; // [rsp+7C0h] [rbp+6C0h]
  __int64 v185; // [rsp+7C8h] [rbp+6C8h]
  __int128 v186; // [rsp+7D0h] [rbp+6D0h] BYREF
  __int64 v187; // [rsp+7E0h] [rbp+6E0h]
  __int64 v188; // [rsp+7E8h] [rbp+6E8h]
  __int128 v189; // [rsp+7F0h] [rbp+6F0h] BYREF
  __int64 v190; // [rsp+800h] [rbp+700h]
  __int64 v191; // [rsp+808h] [rbp+708h]
  __int128 v192; // [rsp+810h] [rbp+710h] BYREF
  __int64 v193; // [rsp+820h] [rbp+720h]
  __int64 v194; // [rsp+828h] [rbp+728h]
  __int128 v195; // [rsp+830h] [rbp+730h] BYREF
  __int64 v196; // [rsp+840h] [rbp+740h]
  __int64 v197; // [rsp+848h] [rbp+748h]
  __int128 v198; // [rsp+850h] [rbp+750h] BYREF
  __int64 v199; // [rsp+860h] [rbp+760h]
  __int64 v200; // [rsp+868h] [rbp+768h]
  _BYTE v201[144]; // [rsp+870h] [rbp+770h] BYREF
  _BYTE v202[144]; // [rsp+900h] [rbp+800h] BYREF
  _BYTE v203[144]; // [rsp+990h] [rbp+890h] BYREF
  _BYTE v204[144]; // [rsp+A20h] [rbp+920h] BYREF
  _BYTE v205[144]; // [rsp+AB0h] [rbp+9B0h] BYREF
  _BYTE v206[144]; // [rsp+B40h] [rbp+A40h] BYREF
  _BYTE v207[144]; // [rsp+BD0h] [rbp+AD0h] BYREF
  _BYTE v208[144]; // [rsp+C60h] [rbp+B60h] BYREF
  _BYTE v209[144]; // [rsp+CF0h] [rbp+BF0h] BYREF
  _BYTE v210[144]; // [rsp+D80h] [rbp+C80h] BYREF
  _BYTE v211[144]; // [rsp+E10h] [rbp+D10h] BYREF
  _BYTE v212[144]; // [rsp+EA0h] [rbp+DA0h] BYREF
  _BYTE v213[144]; // [rsp+F30h] [rbp+E30h] BYREF
  _BYTE v214[144]; // [rsp+FC0h] [rbp+EC0h] BYREF
  _BYTE v215[144]; // [rsp+1050h] [rbp+F50h] BYREF
  _BYTE v216[144]; // [rsp+10E0h] [rbp+FE0h] BYREF
  int v217; // [rsp+1170h] [rbp+1070h] BYREF
  _BYTE v218[136]; // [rsp+1178h] [rbp+1078h] BYREF
  int v219; // [rsp+1200h] [rbp+1100h]
  _BYTE v220[136]; // [rsp+1208h] [rbp+1108h] BYREF
  int v221; // [rsp+1290h] [rbp+1190h]
  _BYTE v222[136]; // [rsp+1298h] [rbp+1198h] BYREF
  int v223; // [rsp+1320h] [rbp+1220h]
  _BYTE v224[136]; // [rsp+1328h] [rbp+1228h] BYREF
  int v225; // [rsp+13B0h] [rbp+12B0h]
  _BYTE v226[136]; // [rsp+13B8h] [rbp+12B8h] BYREF
  int v227; // [rsp+1440h] [rbp+1340h]
  _BYTE v228[136]; // [rsp+1448h] [rbp+1348h] BYREF
  int v229; // [rsp+14D0h] [rbp+13D0h]
  _BYTE v230[136]; // [rsp+14D8h] [rbp+13D8h] BYREF
  int v231; // [rsp+1560h] [rbp+1460h]
  _BYTE v232[136]; // [rsp+1568h] [rbp+1468h] BYREF
  int v233; // [rsp+15F0h] [rbp+14F0h]
  _BYTE v234[136]; // [rsp+15F8h] [rbp+14F8h] BYREF
  int v235; // [rsp+1680h] [rbp+1580h]
  _BYTE v236[136]; // [rsp+1688h] [rbp+1588h] BYREF
  int v237; // [rsp+1710h] [rbp+1610h]
  _BYTE v238[136]; // [rsp+1718h] [rbp+1618h] BYREF
  int v239; // [rsp+17A0h] [rbp+16A0h]
  _BYTE v240[136]; // [rsp+17A8h] [rbp+16A8h] BYREF
  int v241; // [rsp+1830h] [rbp+1730h]
  _BYTE v242[136]; // [rsp+1838h] [rbp+1738h] BYREF
  int v243; // [rsp+18C0h] [rbp+17C0h]
  _BYTE v244[136]; // [rsp+18C8h] [rbp+17C8h] BYREF
  int v245; // [rsp+1950h] [rbp+1850h]
  _BYTE v246[136]; // [rsp+1958h] [rbp+1858h] BYREF
  int v247; // [rsp+19E0h] [rbp+18E0h]
  _BYTE v248[136]; // [rsp+19E8h] [rbp+18E8h] BYREF
  __int64 v249; // [rsp+1A70h] [rbp+1970h] BYREF

  v9 = 0;
  v10 = 0;
  v11 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v9, &LocaleName, 0);
  v12 = 0;
  v13 = 0;
  v14 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v12, L"TpmRegDriverGroupPolicyData", 27);
  v15 = 0;
  v16 = 0;
  v17 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v15, L"TPM", 3);
  v18 = 0;
  v19 = 0;
  v20 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v18, L"Software\\Policies\\Microsoft", 27);
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(
    (unsigned int)v216,
    (unsigned int)&v18,
    (unsigned int)&v15,
    (unsigned int)&v12,
    0,
    131103,
    (__int64)&v9);
  v217 = 0;
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(
    (HWSecurityRegistryManager::RegistryKeyEntry *)v218,
    (const struct HWSecurityRegistryManager::RegistryKeyEntry *)v216);
  v21 = 0;
  v22 = 0;
  v23 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v21, &LocaleName, 0);
  v24 = 0;
  v25 = 0;
  v26 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v24, &LocaleName, 0);
  v27 = 0;
  v28 = 0;
  v29 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v27, L"PcrInfo", 7);
  v30 = 0;
  v31 = 0;
  v32 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v30, L"System\\CurrentControlSet\\Services\\TPM\\WMI", 41);
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(
    (unsigned int)v215,
    (unsigned int)&v30,
    (unsigned int)&v27,
    (unsigned int)&v24,
    0,
    131103,
    (__int64)&v21);
  v219 = 14;
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(
    (HWSecurityRegistryManager::RegistryKeyEntry *)v220,
    (const struct HWSecurityRegistryManager::RegistryKeyEntry *)v215);
  v33 = 0;
  v34 = 0;
  v35 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v33, &LocaleName, 0);
  v36 = 0;
  v37 = 0;
  v38 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v36, L"TpmRegDriverTpm", 15);
  v39 = 0;
  v40 = 0;
  v41 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v39, L"TPM", 3);
  v42 = 0;
  v43 = 0;
  v44 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v42, L"System\\CurrentControlSet\\Services", 33);
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(
    (unsigned int)v214,
    (unsigned int)&v42,
    (unsigned int)&v39,
    (unsigned int)&v36,
    0,
    131103,
    (__int64)&v33);
  v221 = 1;
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(
    (HWSecurityRegistryManager::RegistryKeyEntry *)v222,
    (const struct HWSecurityRegistryManager::RegistryKeyEntry *)v214);
  v45 = 0;
  v46 = 0;
  v47 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v45, &LocaleName, 0);
  v48 = 0;
  v49 = 0;
  v50 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v48, L"TpmRegPlatformQuoteKeysKey", 26);
  v51 = 0;
  v52 = 0;
  v53 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v51, L"PlatformQuoteKeys", 17);
  v54 = 0;
  v55 = 0;
  v56 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v54, L"System\\CurrentControlSet\\Services\\TPM", 37);
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(
    (unsigned int)v213,
    (unsigned int)&v54,
    (unsigned int)&v51,
    (unsigned int)&v48,
    0,
    131103,
    (__int64)&v45);
  v223 = 2;
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(
    (HWSecurityRegistryManager::RegistryKeyEntry *)v224,
    (const struct HWSecurityRegistryManager::RegistryKeyEntry *)v213);
  v57 = 0;
  v58 = 0;
  v59 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v57, &LocaleName, 0);
  v60 = 0;
  v61 = 0;
  v62 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v60, L"TpmRegProvisioningKey", 21);
  v63 = 0;
  v64 = 0;
  v65 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v63, L"ProvisionInfo", 13);
  v66 = 0;
  v67 = 0;
  v68 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v66, L"System\\CurrentControlSet\\Services\\TPM\\WMI", 41);
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(
    (unsigned int)v212,
    (unsigned int)&v66,
    (unsigned int)&v63,
    (unsigned int)&v60,
    0,
    131103,
    (__int64)&v57);
  v225 = 3;
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(
    (HWSecurityRegistryManager::RegistryKeyEntry *)v226,
    (const struct HWSecurityRegistryManager::RegistryKeyEntry *)v212);
  v8[0] = &v69;
  v69 = 0;
  v70 = 0;
  v71 = 0;
  v0 = -1;
  v1 = -1;
  do
    ++v1;
  while ( aOSydAiarAKrAuA[v1] );
  std::wstring::_Construct<1,unsigned short const *>(
    &v69,
    L"O:SYD:AIAR(A;;KR;;;AU)(A;CIIO;GR;;;AU)(A;;KR;;;S-1-15-3-9)(A;CIIO;GR;;;S-1-15-3-9)(A;;KA;;;LS)(A;CIIO;GA;;;LS)(A;;KA"
     ";;;NS)(A;CIIO;GA;;;NS)",
    v1);
  v72 = 0;
  v73 = 0;
  v74 = 0;
  v2 = -1;
  do
    ++v2;
  while ( aTpmregdriverpe[v2] );
  std::wstring::_Construct<1,unsigned short const *>(&v72, L"TpmRegDriverPersistedData", v2);
  v75 = 0;
  v76 = 0;
  v77 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v75, L"WMI", 3);
  v78 = 0;
  v79 = 0;
  v80 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v78, L"System\\CurrentControlSet\\Services\\TPM", 37);
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(
    (unsigned int)v211,
    (unsigned int)&v78,
    (unsigned int)&v75,
    (unsigned int)&v72,
    0,
    131103,
    (__int64)&v69);
  v227 = 4;
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(
    (HWSecurityRegistryManager::RegistryKeyEntry *)v228,
    (const struct HWSecurityRegistryManager::RegistryKeyEntry *)v211);
  v8[0] = &v81;
  v81 = 0;
  v82 = 0;
  v83 = 0;
  v3 = -1;
  do
    ++v3;
  while ( aOSydPaiAKaBaAC[v3] );
  std::wstring::_Construct<1,unsigned short const *>(
    &v81,
    L"O:SYD:PAI(A;;KA;;;BA)(A;CIIO;GA;;;BA)(A;;KA;;;SY)(A;CIIO;GA;;;SY)(A;;KA;;;LS)(A;CIIO;GA;;;LS)(A;;KA;;;NS)(A;CIIO;GA;;;NS)",
    v3);
  v84 = 0;
  v85 = 0;
  v86 = 0;
  v4 = -1;
  do
    ++v4;
  while ( aTpmregdriverpe_0[v4] );
  std::wstring::_Construct<1,unsigned short const *>(&v84, L"TpmRegDriverPersistedDataAdmin", v4);
  v87 = 0;
  v88 = 0;
  v89 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v87, L"Admin", 5);
  v90 = 0;
  v91 = 0;
  v92 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v90, L"System\\CurrentControlSet\\Services\\TPM\\WMI", 41);
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(
    (unsigned int)v210,
    (unsigned int)&v90,
    (unsigned int)&v87,
    (unsigned int)&v84,
    0,
    131103,
    (__int64)&v81);
  v229 = 5;
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(
    (HWSecurityRegistryManager::RegistryKeyEntry *)v230,
    (const struct HWSecurityRegistryManager::RegistryKeyEntry *)v210);
  v8[0] = &v93;
  v93 = 0;
  v94 = 0;
  v95 = 0;
  v5 = -1;
  do
    ++v5;
  while ( aOSydPaiAKaBaAC_0[v5] );
  std::wstring::_Construct<1,unsigned short const *>(
    &v93,
    L"O:SYD:PAI(A;;KA;;;BA)(A;CIIO;GA;;;BA)(A;;KA;;;SY)(A;CIIO;GA;;;SY)(A;;KA;;;LS)(A;CIIO;GA;;;LS)(A;;KA;;;NS)(A;CIIO;GA;"
     ";;NS)(A;;KR;;;S-1-15-3-9)(A;CIIO;GR;;;S-1-15-3-9)(A;;KR;;;S-1-5-4)(A;CIIO;GR;;;S-1-5-4)(A;;KR;;;S-1-5-11)(A;CIIO;GR;;;S-1-5-11)",
    v5);
  v96 = 0;
  v97 = 0;
  v98 = 0;
  do
    ++v0;
  while ( aTpmregdriverpe_1[v0] );
  std::wstring::_Construct<1,unsigned short const *>(&v96, L"TpmRegDriverPersistedDataEndorsement", v0);
  v99 = 0;
  v100 = 0;
  v101 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v99, L"Endorsement", 11);
  v102 = 0;
  v103 = 0;
  v104 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v102, L"System\\CurrentControlSet\\Services\\TPM\\WMI", 41);
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(
    (unsigned int)v209,
    (unsigned int)&v102,
    (unsigned int)&v99,
    (unsigned int)&v96,
    0,
    131103,
    (__int64)&v93);
  v231 = 6;
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(
    (HWSecurityRegistryManager::RegistryKeyEntry *)v232,
    (const struct HWSecurityRegistryManager::RegistryKeyEntry *)v209);
  v105 = 0;
  v106 = 0;
  v107 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v105, &LocaleName, 0);
  v108 = 0;
  v109 = 0;
  v110 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v108, L"TPMCoreProvisioningHealthCertStore", 34);
  v111 = 0;
  v112 = 0;
  v113 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v111, L"Store", 5);
  v114 = 0;
  v115 = 0;
  v116 = 0;
  std::wstring::_Construct<1,unsigned short const *>(
    &v114,
    L"System\\CurrentControlSet\\Services\\TPM\\WMI\\HealthCert",
    52);
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(
    (unsigned int)v208,
    (unsigned int)&v114,
    (unsigned int)&v111,
    (unsigned int)&v108,
    0,
    131103,
    (__int64)&v105);
  v233 = 7;
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(
    (HWSecurityRegistryManager::RegistryKeyEntry *)v234,
    (const struct HWSecurityRegistryManager::RegistryKeyEntry *)v208);
  v117 = 0;
  v118 = 0;
  v119 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v117, &LocaleName, 0);
  v120 = 0;
  v121 = 0;
  v122 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v120, &LocaleName, 0);
  v123 = 0;
  v124 = 0;
  v125 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v123, L"TaskStates", 10);
  v126 = 0;
  v127 = 0;
  v128 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v126, L"System\\CurrentControlSet\\Services\\TPM\\WMI", 41);
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(
    (unsigned int)v207,
    (unsigned int)&v126,
    (unsigned int)&v123,
    (unsigned int)&v120,
    1,
    131103,
    (__int64)&v117);
  v235 = 8;
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(
    (HWSecurityRegistryManager::RegistryKeyEntry *)v236,
    (const struct HWSecurityRegistryManager::RegistryKeyEntry *)v207);
  v129 = 0;
  v130 = 0;
  v131 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v129, &LocaleName, 0);
  v132 = 0;
  v133 = 0;
  v134 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v132, &LocaleName, 0);
  v135 = 0;
  v136 = 0;
  v137 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v135, L"AttestationInfo", 15);
  v138 = 0;
  v139 = 0;
  v140 = 0;
  std::wstring::_Construct<1,unsigned short const *>(
    &v138,
    L"System\\CurrentControlSet\\Services\\TPM\\WMI\\TaskStates",
    52);
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(
    (unsigned int)v206,
    (unsigned int)&v138,
    (unsigned int)&v135,
    (unsigned int)&v132,
    1,
    131103,
    (__int64)&v129);
  v237 = 9;
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(
    (HWSecurityRegistryManager::RegistryKeyEntry *)v238,
    (const struct HWSecurityRegistryManager::RegistryKeyEntry *)v206);
  v141 = 0;
  v142 = 0;
  v143 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v141, &LocaleName, 0);
  v144 = 0;
  v145 = 0;
  v146 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v144, &LocaleName, 0);
  v147 = 0;
  v148 = 0;
  v149 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v147, L"Volatile-AIKCertEnroll-EXCLUSIVE", 32);
  v150 = 0;
  v151 = 0;
  v152 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v150, L"System\\CurrentControlSet\\Services\\TPM\\WMI", 41);
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(
    (unsigned int)v205,
    (unsigned int)&v150,
    (unsigned int)&v147,
    (unsigned int)&v144,
    1,
    131103,
    (__int64)&v141);
  v239 = 10;
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(
    (HWSecurityRegistryManager::RegistryKeyEntry *)v240,
    (const struct HWSecurityRegistryManager::RegistryKeyEntry *)v205);
  v153 = 0;
  v154 = 0;
  v155 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v153, &LocaleName, 0);
  v156 = 0;
  v157 = 0;
  v158 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v156, L"TPMCoreProvisioningEKCertificates", 33);
  v159 = 0;
  v160 = 0;
  v161 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v159, L"EkCertStore", 11);
  v162 = 0;
  v163 = 0;
  v164 = 0;
  std::wstring::_Construct<1,unsigned short const *>(
    &v162,
    L"System\\CurrentControlSet\\Services\\TPM\\WMI\\Endorsement",
    53);
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(
    (unsigned int)v204,
    (unsigned int)&v162,
    (unsigned int)&v159,
    (unsigned int)&v156,
    0,
    983103,
    (__int64)&v153);
  v241 = 11;
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(
    (HWSecurityRegistryManager::RegistryKeyEntry *)v242,
    (const struct HWSecurityRegistryManager::RegistryKeyEntry *)v204);
  v165 = 0;
  v166 = 0;
  v167 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v165, &LocaleName, 0);
  v168 = 0;
  v169 = 0;
  v170 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v168, L"TPMCoreProvisioningEKCertificates", 33);
  v171 = 0;
  v172 = 0;
  v173 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v171, L"EkCertStoreECC", 14);
  v174 = 0;
  v175 = 0;
  v176 = 0;
  std::wstring::_Construct<1,unsigned short const *>(
    &v174,
    L"System\\CurrentControlSet\\Services\\TPM\\WMI\\Endorsement",
    53);
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(
    (unsigned int)v203,
    (unsigned int)&v174,
    (unsigned int)&v171,
    (unsigned int)&v168,
    0,
    983103,
    (__int64)&v165);
  v243 = 12;
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(
    (HWSecurityRegistryManager::RegistryKeyEntry *)v244,
    (const struct HWSecurityRegistryManager::RegistryKeyEntry *)v203);
  v177 = 0;
  v178 = 0;
  v179 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v177, &LocaleName, 0);
  v180 = 0;
  v181 = 0;
  v182 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v180, L"TPMCoreProvisioningIntermediateCACerts", 38);
  v183 = 0;
  v184 = 0;
  v185 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v183, L"IntermediateCACertStore", 23);
  v186 = 0;
  v187 = 0;
  v188 = 0;
  std::wstring::_Construct<1,unsigned short const *>(
    &v186,
    L"System\\CurrentControlSet\\Services\\TPM\\WMI\\Endorsement",
    53);
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(
    (unsigned int)v202,
    (unsigned int)&v186,
    (unsigned int)&v183,
    (unsigned int)&v180,
    0,
    983103,
    (__int64)&v177);
  v245 = 13;
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(
    (HWSecurityRegistryManager::RegistryKeyEntry *)v246,
    (const struct HWSecurityRegistryManager::RegistryKeyEntry *)v202);
  v189 = 0;
  v190 = 0;
  v191 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v189, &LocaleName, 0);
  v192 = 0;
  v193 = 0;
  v194 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v192, &LocaleName, 0);
  v195 = 0;
  v196 = 0;
  v197 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v195, &LocaleName, 0);
  v198 = 0;
  v199 = 0;
  v200 = 0;
  std::wstring::_Construct<1,unsigned short const *>(
    &v198,
    L"System\\CurrentControlSet\\Control\\IntegrityServices",
    50);
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(
    (unsigned int)v201,
    (unsigned int)&v198,
    (unsigned int)&v195,
    (unsigned int)&v192,
    0,
    131097,
    (__int64)&v189);
  v247 = 15;
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(
    (HWSecurityRegistryManager::RegistryKeyEntry *)v248,
    (const struct HWSecurityRegistryManager::RegistryKeyEntry *)v201);
  *(_OWORD *)&HWSecurityRegistryManager::m_RegKeyTable = 0;
  std::_Tree<std::_Tmap_traits<enum HWSecurityRegistryManager::RegKeys,HWSecurityRegistryManager::RegistryKeyEntry,std::less<enum HWSecurityRegistryManager::RegKeys>,std::allocator<std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>>,0>>::_Alloc_sentinel_and_proxy();
  v8[0] = &v217;
  v8[1] = &v249;
  std::_Tree<std::_Tmap_traits<enum HWSecurityRegistryManager::RegKeys,HWSecurityRegistryManager::RegistryKeyEntry,std::less<enum HWSecurityRegistryManager::RegKeys>,std::allocator<std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>>,0>>::insert(
    v6,
    v8);
  `eh vector destructor iterator'(
    &v217,
    0x90u,
    0x10u,
    std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::~pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>);
  HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry((HWSecurityRegistryManager::RegistryKeyEntry *)v201);
  HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry((HWSecurityRegistryManager::RegistryKeyEntry *)v202);
  HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry((HWSecurityRegistryManager::RegistryKeyEntry *)v203);
  HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry((HWSecurityRegistryManager::RegistryKeyEntry *)v204);
  HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry((HWSecurityRegistryManager::RegistryKeyEntry *)v205);
  HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry((HWSecurityRegistryManager::RegistryKeyEntry *)v206);
  HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry((HWSecurityRegistryManager::RegistryKeyEntry *)v207);
  HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry((HWSecurityRegistryManager::RegistryKeyEntry *)v208);
  HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry((HWSecurityRegistryManager::RegistryKeyEntry *)v209);
  HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry((HWSecurityRegistryManager::RegistryKeyEntry *)v210);
  HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry((HWSecurityRegistryManager::RegistryKeyEntry *)v211);
  HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry((HWSecurityRegistryManager::RegistryKeyEntry *)v212);
  HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry((HWSecurityRegistryManager::RegistryKeyEntry *)v213);
  HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry((HWSecurityRegistryManager::RegistryKeyEntry *)v214);
  HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry((HWSecurityRegistryManager::RegistryKeyEntry *)v215);
  HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry((HWSecurityRegistryManager::RegistryKeyEntry *)v216);
  return atexit(dynamic_atexit_destructor_for__HWSecurityRegistryManager::m_RegKeyTable__);
}

```

## disassembly

```asm
0x180003270  push    rbp
0x180003272  push    rbx
0x180003273  push    rsi
0x180003274  push    rdi
0x180003275  push    r12
0x180003277  push    r13
0x180003279  push    r14
0x18000327b  push    r15
0x18000327d  lea     rbp, [rsp-1988h]
0x180003285  mov     eax, 1A88h
0x18000328a  call    _alloca_probe
0x18000328f  sub     rsp, rax
0x180003292  mov     rax, cs:__security_cookie
0x180003299  xor     rax, rsp
0x18000329c  mov     [rbp+19C0h+var_50], rax
0x1800032a3  lea     rax, [rsp+1AC0h+var_1A50]
0x1800032a8  mov     [rsp+1AC0h+var_1A80], rax
0x1800032ad  xorps   xmm0, xmm0
0x1800032b0  movups  [rsp+1AC0h+var_1A50], xmm0
0x1800032b5  xor     r15d, r15d
0x1800032b8  mov     [rbp+19C0h+var_1A40], r15
0x1800032bc  mov     [rbp+19C0h+var_1A38], r15
0x1800032c0  xor     r8d, r8d
0x1800032c3  lea     r12, LocaleName
0x1800032ca  mov     rdx, r12
0x1800032cd  lea     rcx, [rsp+1AC0h+var_1A50]
0x1800032d2  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800032d7  nop
0x1800032d8  lea     rax, [rbp+19C0h+var_1A30]
0x1800032dc  mov     [rsp+1AC0h+var_1A78], rax
0x1800032e1  xorps   xmm0, xmm0
0x1800032e4  movups  [rbp+19C0h+var_1A30], xmm0
0x1800032e8  mov     [rbp+19C0h+var_1A20], r15
0x1800032ec  mov     [rbp+19C0h+var_1A18], r15
0x1800032f0  lea     ebx, [r15+1Bh]
0x1800032f4  mov     r8d, ebx
0x1800032f7  lea     rdx, aTpmregdrivergr; "TpmRegDriverGroupPolicyData"
0x1800032fe  lea     rcx, [rbp+19C0h+var_1A30]
0x180003302  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180003307  nop
0x180003308  lea     rax, [rbp+19C0h+var_1A10]
0x18000330c  mov     [rsp+1AC0h+var_1A70], rax
0x180003311  xorps   xmm0, xmm0
0x180003314  movups  [rbp+19C0h+var_1A10], xmm0
0x180003318  mov     [rbp+19C0h+var_1A00], r15
0x18000331c  mov     [rbp+19C0h+var_19F8], r15
0x180003320  lea     edi, [rbx-18h]
0x180003323  mov     r8d, edi
0x180003326  lea     rdx, aTpm; "TPM"
0x18000332d  lea     rcx, [rbp+19C0h+var_1A10]
0x180003331  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180003336  nop
0x180003337  xorps   xmm0, xmm0
0x18000333a  movups  [rbp+19C0h+var_19F0], xmm0
0x18000333e  mov     [rbp+19C0h+var_19E0], r15
0x180003342  mov     [rbp+19C0h+var_19D8], r15
0x180003346  mov     r8d, ebx
0x180003349  lea     rdx, aSoftwarePolici_1; "Software\\Policies\\Microsoft"
0x180003350  lea     rcx, [rbp+19C0h+var_19F0]
0x180003354  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180003359  nop
0x18000335a  lea     rax, [rsp+1AC0h+var_1A50]
0x18000335f  mov     [rsp+1AC0h+var_1A90], rax
0x180003364  mov     esi, 2001Fh
0x180003369  mov     [rsp+1AC0h+var_1A98], esi
0x18000336d  mov     [rsp+1AC0h+var_1AA0], r15d
0x180003372  lea     r9, [rbp+19C0h+var_1A30]
0x180003376  lea     r8, [rbp+19C0h+var_1A10]
0x18000337a  lea     rdx, [rbp+19C0h+var_19F0]
0x18000337e  lea     rcx, [rbp+19C0h+var_9E0]
0x180003385  call    ??0RegistryKeyEntry@HWSecurityRegistryManager@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00KK0@Z; HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(std::wstring,std::wstring,std::wstring,ulong,ulong,std::wstring)
0x18000338a  nop
0x18000338b  mov     [rbp+19C0h+var_950], r15d
0x180003392  lea     rdx, [rbp+19C0h+var_9E0]; struct HWSecurityRegistryManager::RegistryKeyEntry *
0x180003399  lea     rcx, [rbp+19C0h+var_948]; this
0x1800033a0  call    ??0RegistryKeyEntry@HWSecurityRegistryManager@@QEAA@AEBV01@@Z; HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(HWSecurityRegistryManager::RegistryKeyEntry const &)
0x1800033a5  nop
0x1800033a6  lea     rax, [rbp+19C0h+var_19D0]
0x1800033aa  mov     [rsp+1AC0h+var_1A60], rax
0x1800033af  xorps   xmm0, xmm0
0x1800033b2  movups  [rbp+19C0h+var_19D0], xmm0
0x1800033b6  mov     [rbp+19C0h+var_19C0], r15
0x1800033ba  mov     [rbp+19C0h+var_19B8], r15
0x1800033be  xor     r8d, r8d
0x1800033c1  mov     rdx, r12
0x1800033c4  lea     rcx, [rbp+19C0h+var_19D0]
0x1800033c8  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800033cd  nop
0x1800033ce  lea     rax, [rbp+19C0h+var_19B0]
0x1800033d2  mov     [rsp+1AC0h+var_1A70], rax
0x1800033d7  xorps   xmm0, xmm0
0x1800033da  movups  [rbp+19C0h+var_19B0], xmm0
0x1800033de  mov     [rbp+19C0h+var_19A0], r15
0x1800033e2  mov     [rbp+19C0h+var_1998], r15
0x1800033e6  xor     r8d, r8d
0x1800033e9  mov     rdx, r12
0x1800033ec  lea     rcx, [rbp+19C0h+var_19B0]
0x1800033f0  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800033f5  nop
0x1800033f6  lea     rax, [rbp+19C0h+var_1990]
0x1800033fa  mov     [rsp+1AC0h+var_1A78], rax
0x1800033ff  xorps   xmm0, xmm0
0x180003402  movups  [rbp+19C0h+var_1990], xmm0
0x180003406  mov     [rbp+19C0h+var_1980], r15
0x18000340a  mov     [rbp+19C0h+var_1978], r15
0x18000340e  lea     r8d, [r15+7]
0x180003412  lea     rdx, aPcrinfo; "PcrInfo"
0x180003419  lea     rcx, [rbp+19C0h+var_1990]
0x18000341d  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180003422  nop
0x180003423  xorps   xmm0, xmm0
0x180003426  movups  [rbp+19C0h+var_1970], xmm0
0x18000342a  mov     [rbp+19C0h+var_1960], r15
0x18000342e  mov     [rbp+19C0h+var_1958], r15
0x180003432  lea     r13d, [r15+29h]
0x180003436  mov     r8d, r13d
0x180003439  lea     r14, aSystemCurrentc_9; "System\\CurrentControlSet\\Services\\TP"...
0x180003440  mov     rdx, r14
0x180003443  lea     rcx, [rbp+19C0h+var_1970]
0x180003447  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000344c  nop
0x18000344d  lea     rax, [rbp+19C0h+var_19D0]
0x180003451  mov     [rsp+1AC0h+var_1A90], rax
0x180003456  mov     [rsp+1AC0h+var_1A98], esi
0x18000345a  mov     [rsp+1AC0h+var_1AA0], r15d
0x18000345f  lea     r9, [rbp+19C0h+var_19B0]
0x180003463  lea     r8, [rbp+19C0h+var_1990]
0x180003467  lea     rdx, [rbp+19C0h+var_1970]
0x18000346b  lea     rcx, [rbp+19C0h+var_A70]
0x180003472  call    ??0RegistryKeyEntry@HWSecurityRegistryManager@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00KK0@Z; HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(std::wstring,std::wstring,std::wstring,ulong,ulong,std::wstring)
0x180003477  nop
0x180003478  mov     [rbp+19C0h+var_8C0], 0Eh
0x180003482  lea     rdx, [rbp+19C0h+var_A70]; struct HWSecurityRegistryManager::RegistryKeyEntry *
0x180003489  lea     rcx, [rbp+19C0h+var_8B8]; this
0x180003490  call    ??0RegistryKeyEntry@HWSecurityRegistryManager@@QEAA@AEBV01@@Z; HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(HWSecurityRegistryManager::RegistryKeyEntry const &)
0x180003495  nop
0x180003496  lea     rax, [rbp+19C0h+var_1950]
0x18000349a  mov     [rsp+1AC0h+var_1A60], rax
0x18000349f  xorps   xmm0, xmm0
0x1800034a2  movups  [rbp+19C0h+var_1950], xmm0
0x1800034a6  mov     [rbp+19C0h+var_1940], r15
0x1800034ad  mov     [rbp+19C0h+var_1938], r15
0x1800034b4  xor     r8d, r8d
0x1800034b7  mov     rdx, r12
0x1800034ba  lea     rcx, [rbp+19C0h+var_1950]
0x1800034be  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800034c3  nop
0x1800034c4  lea     rax, [rbp+19C0h+var_1930]
0x1800034cb  mov     [rsp+1AC0h+var_1A70], rax
0x1800034d0  xorps   xmm0, xmm0
0x1800034d3  movups  [rbp+19C0h+var_1930], xmm0
0x1800034da  mov     [rbp+19C0h+var_1920], r15
0x1800034e1  mov     [rbp+19C0h+var_1918], r15
0x1800034e8  lea     r8d, [r15+0Fh]
0x1800034ec  lea     rdx, aTpmregdrivertp; "TpmRegDriverTpm"
0x1800034f3  lea     rcx, [rbp+19C0h+var_1930]
0x1800034fa  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800034ff  nop
0x180003500  lea     rax, [rbp+19C0h+var_1910]
0x180003507  mov     [rsp+1AC0h+var_1A78], rax
0x18000350c  xorps   xmm0, xmm0
0x18000350f  movups  [rbp+19C0h+var_1910], xmm0
0x180003516  mov     [rbp+19C0h+var_1900], r15
0x18000351d  mov     [rbp+19C0h+var_18F8], r15
0x180003524  mov     r8d, edi
0x180003527  lea     rdx, aTpm; "TPM"
0x18000352e  lea     rcx, [rbp+19C0h+var_1910]
0x180003535  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000353a  nop
0x18000353b  xorps   xmm0, xmm0
0x18000353e  movups  [rbp+19C0h+var_18F0], xmm0
0x180003545  mov     [rbp+19C0h+var_18E0], r15
0x18000354c  mov     [rbp+19C0h+var_18D8], r15
0x180003553  lea     r8d, [r15+21h]
0x180003557  lea     rdx, aSystemCurrentc_10; "System\\CurrentControlSet\\Services"
0x18000355e  lea     rcx, [rbp+19C0h+var_18F0]
0x180003565  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000356a  nop
0x18000356b  lea     rax, [rbp+19C0h+var_1950]
0x18000356f  mov     [rsp+1AC0h+var_1A90], rax
0x180003574  mov     [rsp+1AC0h+var_1A98], esi
0x180003578  mov     [rsp+1AC0h+var_1AA0], r15d
0x18000357d  lea     r9, [rbp+19C0h+var_1930]
0x180003584  lea     r8, [rbp+19C0h+var_1910]
0x18000358b  lea     rdx, [rbp+19C0h+var_18F0]
0x180003592  lea     rcx, [rbp+19C0h+var_B00]
0x180003599  call    ??0RegistryKeyEntry@HWSecurityRegistryManager@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00KK0@Z; HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(std::wstring,std::wstring,std::wstring,ulong,ulong,std::wstring)
0x18000359e  nop
0x18000359f  mov     [rbp+19C0h+var_830], 1
0x1800035a9  lea     rdx, [rbp+19C0h+var_B00]; struct HWSecurityRegistryManager::RegistryKeyEntry *
0x1800035b0  lea     rcx, [rbp+19C0h+var_828]; this
0x1800035b7  call    ??0RegistryKeyEntry@HWSecurityRegistryManager@@QEAA@AEBV01@@Z; HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(HWSecurityRegistryManager::RegistryKeyEntry const &)
0x1800035bc  nop
0x1800035bd  lea     rax, [rbp+19C0h+var_18D0]
0x1800035c4  mov     [rsp+1AC0h+var_1A60], rax
0x1800035c9  xorps   xmm0, xmm0
0x1800035cc  movups  [rbp+19C0h+var_18D0], xmm0
0x1800035d3  mov     [rbp+19C0h+var_18C0], r15
0x1800035da  mov     [rbp+19C0h+var_18B8], r15
0x1800035e1  xor     r8d, r8d
0x1800035e4  mov     rdx, r12
0x1800035e7  lea     rcx, [rbp+19C0h+var_18D0]
0x1800035ee  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800035f3  nop
0x1800035f4  lea     rax, [rbp+19C0h+var_18B0]
0x1800035fb  mov     [rsp+1AC0h+var_1A70], rax
0x180003600  xorps   xmm0, xmm0
0x180003603  movups  [rbp+19C0h+var_18B0], xmm0
0x18000360a  mov     [rbp+19C0h+var_18A0], r15
0x180003611  mov     [rbp+19C0h+var_1898], r15
0x180003618  lea     r8d, [r15+1Ah]
0x18000361c  lea     rdx, aTpmregplatform; "TpmRegPlatformQuoteKeysKey"
0x180003623  lea     rcx, [rbp+19C0h+var_18B0]
0x18000362a  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000362f  nop
0x180003630  lea     rax, [rbp+19C0h+var_1890]
0x180003637  mov     [rsp+1AC0h+var_1A78], rax
0x18000363c  xorps   xmm0, xmm0
0x18000363f  movups  [rbp+19C0h+var_1890], xmm0
0x180003646  mov     [rbp+19C0h+var_1880], r15
0x18000364d  mov     [rbp+19C0h+var_1878], r15
0x180003654  lea     r8d, [r15+11h]
0x180003658  lea     rdx, aPlatformquotek; "PlatformQuoteKeys"
0x18000365f  lea     rcx, [rbp+19C0h+var_1890]
0x180003666  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000366b  nop
0x18000366c  xorps   xmm0, xmm0
0x18000366f  movups  [rbp+19C0h+var_1870], xmm0
0x180003676  mov     [rbp+19C0h+var_1860], r15
0x18000367d  mov     [rbp+19C0h+var_1858], r15
0x180003684  lea     r8d, [r15+25h]
0x180003688  lea     rdx, aSystemCurrentc_6; "System\\CurrentControlSet\\Services\\TP"...
0x18000368f  lea     rcx, [rbp+19C0h+var_1870]
0x180003696  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000369b  nop
0x18000369c  lea     rax, [rbp+19C0h+var_18D0]
0x1800036a3  mov     [rsp+1AC0h+var_1A90], rax
0x1800036a8  mov     [rsp+1AC0h+var_1A98], esi
0x1800036ac  mov     [rsp+1AC0h+var_1AA0], r15d
0x1800036b1  lea     r9, [rbp+19C0h+var_18B0]
0x1800036b8  lea     r8, [rbp+19C0h+var_1890]
0x1800036bf  lea     rdx, [rbp+19C0h+var_1870]
0x1800036c6  lea     rcx, [rbp+19C0h+var_B90]
0x1800036cd  call    ??0RegistryKeyEntry@HWSecurityRegistryManager@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00KK0@Z; HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(std::wstring,std::wstring,std::wstring,ulong,ulong,std::wstring)
0x1800036d2  nop
0x1800036d3  mov     [rbp+19C0h+var_7A0], 2
0x1800036dd  lea     rdx, [rbp+19C0h+var_B90]; struct HWSecurityRegistryManager::RegistryKeyEntry *
0x1800036e4  lea     rcx, [rbp+19C0h+var_798]; this
0x1800036eb  call    ??0RegistryKeyEntry@HWSecurityRegistryManager@@QEAA@AEBV01@@Z; HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(HWSecurityRegistryManager::RegistryKeyEntry const &)
0x1800036f0  nop
0x1800036f1  lea     rax, [rbp+19C0h+var_1850]
0x1800036f8  mov     [rsp+1AC0h+var_1A60], rax
0x1800036fd  xorps   xmm0, xmm0
0x180003700  movups  [rbp+19C0h+var_1850], xmm0
0x180003707  mov     [rbp+19C0h+var_1840], r15
0x18000370e  mov     [rbp+19C0h+var_1838], r15
0x180003715  xor     r8d, r8d
0x180003718  mov     rdx, r12
0x18000371b  lea     rcx, [rbp+19C0h+var_1850]
0x180003722  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180003727  nop
0x180003728  lea     rax, [rbp+19C0h+var_1830]
0x18000372f  mov     [rsp+1AC0h+var_1A70], rax
0x180003734  xorps   xmm0, xmm0
0x180003737  movups  [rbp+19C0h+var_1830], xmm0
0x18000373e  mov     [rbp+19C0h+var_1820], r15
0x180003745  mov     [rbp+19C0h+var_1818], r15
0x18000374c  lea     r8d, [r15+15h]
0x180003750  lea     rdx, aTpmregprovisio; "TpmRegProvisioningKey"
0x180003757  lea     rcx, [rbp+19C0h+var_1830]
0x18000375e  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180003763  nop
0x180003764  lea     rax, [rbp+19C0h+var_1810]
0x18000376b  mov     [rsp+1AC0h+var_1A78], rax
0x180003770  xorps   xmm0, xmm0
0x180003773  movups  [rbp+19C0h+var_1810], xmm0
0x18000377a  mov     [rbp+19C0h+var_1800], r15
0x180003781  mov     [rbp+19C0h+var_17F8], r15
0x180003788  lea     r8d, [r15+0Dh]
0x18000378c  lea     rdx, aProvisioninfo; "ProvisionInfo"
0x180003793  lea     rcx, [rbp+19C0h+var_1810]
0x18000379a  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000379f  nop
0x1800037a0  xorps   xmm0, xmm0
0x1800037a3  movups  [rbp+19C0h+var_17F0], xmm0
0x1800037aa  mov     [rbp+19C0h+var_17E0], r15
0x1800037b1  mov     [rbp+19C0h+var_17D8], r15
0x1800037b8  mov     r8d, r13d
0x1800037bb  mov     rdx, r14
0x1800037be  lea     rcx, [rbp+19C0h+var_17F0]
0x1800037c5  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800037ca  nop
0x1800037cb  lea     rax, [rbp+19C0h+var_1850]
0x1800037d2  mov     [rsp+1AC0h+var_1A90], rax
0x1800037d7  mov     [rsp+1AC0h+var_1A98], esi
0x1800037db  mov     [rsp+1AC0h+var_1AA0], r15d
0x1800037e0  lea     r9, [rbp+19C0h+var_1830]
0x1800037e7  lea     r8, [rbp+19C0h+var_1810]
0x1800037ee  lea     rdx, [rbp+19C0h+var_17F0]
0x1800037f5  lea     rcx, [rbp+19C0h+var_C20]
  ... truncated ...
```
