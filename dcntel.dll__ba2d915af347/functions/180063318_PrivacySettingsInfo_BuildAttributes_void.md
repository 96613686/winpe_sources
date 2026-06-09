# PrivacySettingsInfo::BuildAttributes(void)

- ea: `0x180063318`
- end: `0x180066623`
- name: `?BuildAttributes@PrivacySettingsInfo@@CA?AV?$vector@U?$AttributeDefinition2@U_PRIVACY_SETTINGS_INFO_2@@VPrivacySettingsInfo@@@@V?$allocator@U?$AttributeDefinition2@U_PRIVACY_SETTINGS_INFO_2@@VPrivacySettingsInfo@@@@@std@@@std@@XZ`
- size: `13067`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180062e60`

## callees

- `0x180008dc0`
- `0x180008de4`
- `0x1800152b8`
- `0x180019288`
- `0x18001b3c0`
- `0x180184ae0`

## string_xrefs

- `0x180063371`: `SystemPrivacySettingActivity`
- `0x1800634c3`: `SystemPrivacySettingAppDiagnostics`
- `0x1800638b8`: `SystemPrivacySettingBluetoothSync`
- `0x180063a0b`: `SystemPrivacySettingBroadFileSystemAccess`
- `0x180063612`: `SystemPrivacySettingAppointments`
- `0x180063765`: `SystemPrivacySettingBluetooth`
- `0x180063e04`: `SystemPrivacySettingContacts`
- `0x180063f57`: `SystemPrivacySettingDocumentsLibrary`
- `0x180063b5e`: `SystemPrivacySettingCellularData`
- `0x180063cb1`: `SystemPrivacySettingChat`
- `0x180064350`: `SystemPrivacySettingHumanInterfaceDevice`
- `0x1800644a3`: `SystemPrivacySettingLocation`
- `0x1800640aa`: `SystemPrivacySettingEmail`
- `0x1800641fd`: `SystemPrivacySettingGazeInput`
- `0x18006489c`: `SystemPrivacySettingPhoneCall`
- `0x1800649ef`: `SystemPrivacySettingPhoneCallHistory`
- `0x1800645f6`: `SystemPrivacySettingLocationHistory`
- `0x180064749`: `SystemPrivacySettingMicrophone`
- `0x180064de8`: `SystemPrivacySettingSensorsCustom`
- `0x180064f3b`: `SystemPrivacySettingSerialCommunication`
- `0x180064b42`: `SystemPrivacySettingPicturesLibrary`
- `0x180064c95`: `SystemPrivacySettingRadios`
- `0x180065334`: `SystemPrivacySettingUserAccountInformation`
- `0x180065487`: `SystemPrivacySettingUserDataTasks`
- `0x18006508e`: `SystemPrivacySettingSms`
- `0x1800651e1`: `SystemPrivacySettingUSB`
- `0x180065877`: `SystemPrivacySettingWebcam`
- `0x1800659be`: `SystemPrivacySettingWifiData`
- `0x1800655da`: `SystemPrivacySettingUserNotificationListener`
- `0x18006572d`: `SystemPrivacySettingVideosLibrary`
- `0x180065d95`: `SystemPrivacySettingActivityHistoryCloudSync`
- `0x180065edd`: `SystemPrivacySettingAdvertisingId`
- `0x180065b06`: `SystemPrivacySettingWiFiDirect`
- `0x180065c4d`: `SystemPrivacySettingActivityHistoryCollection`
- `0x1800662b5`: `SystemPrivacySettingFindMyDevice`
- `0x180066024`: `SystemPrivacySettingSpeechPersonalization`
- `0x18006616b`: `SystemPrivacySettingInkTypeImprovement`

## pseudocode

```c
// Hidden C++ exception states: #wind=111
_QWORD *__fastcall PrivacySettingsInfo::BuildAttributes(_QWORD *a1)
{
  int v3; // [rsp+28h] [rbp-D8h] BYREF
  __int128 v4; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v5; // [rsp+40h] [rbp-C0h]
  int v6; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v7; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v8; // [rsp+60h] [rbp-A0h]
  int v9; // [rsp+68h] [rbp-98h] BYREF
  __int128 v10; // [rsp+70h] [rbp-90h] BYREF
  __int64 v11; // [rsp+80h] [rbp-80h]
  int v12; // [rsp+88h] [rbp-78h] BYREF
  __int128 v13; // [rsp+90h] [rbp-70h] BYREF
  __int64 v14; // [rsp+A0h] [rbp-60h]
  int v15; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v16; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v17; // [rsp+C0h] [rbp-40h]
  int v18; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v19; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v20; // [rsp+E0h] [rbp-20h]
  int v21; // [rsp+E8h] [rbp-18h] BYREF
  __int128 v22; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v23; // [rsp+100h] [rbp+0h]
  int v24; // [rsp+108h] [rbp+8h] BYREF
  __int128 v25; // [rsp+110h] [rbp+10h] BYREF
  __int64 v26; // [rsp+120h] [rbp+20h]
  int v27; // [rsp+128h] [rbp+28h] BYREF
  __int128 v28; // [rsp+130h] [rbp+30h] BYREF
  __int64 v29; // [rsp+140h] [rbp+40h]
  int v30; // [rsp+148h] [rbp+48h] BYREF
  __int128 v31; // [rsp+150h] [rbp+50h] BYREF
  __int64 v32; // [rsp+160h] [rbp+60h]
  int v33; // [rsp+168h] [rbp+68h] BYREF
  __int128 v34; // [rsp+170h] [rbp+70h] BYREF
  __int64 v35; // [rsp+180h] [rbp+80h]
  int v36; // [rsp+188h] [rbp+88h] BYREF
  __int128 v37; // [rsp+190h] [rbp+90h] BYREF
  __int64 v38; // [rsp+1A0h] [rbp+A0h]
  int v39; // [rsp+1A8h] [rbp+A8h] BYREF
  __int128 v40; // [rsp+1B0h] [rbp+B0h] BYREF
  __int64 v41; // [rsp+1C0h] [rbp+C0h]
  int v42; // [rsp+1C8h] [rbp+C8h] BYREF
  __int128 v43; // [rsp+1D0h] [rbp+D0h] BYREF
  __int64 v44; // [rsp+1E0h] [rbp+E0h]
  int v45; // [rsp+1E8h] [rbp+E8h] BYREF
  __int128 v46; // [rsp+1F0h] [rbp+F0h] BYREF
  __int64 v47; // [rsp+200h] [rbp+100h]
  int v48; // [rsp+208h] [rbp+108h] BYREF
  __int128 v49; // [rsp+210h] [rbp+110h] BYREF
  __int64 v50; // [rsp+220h] [rbp+120h]
  int v51; // [rsp+228h] [rbp+128h] BYREF
  __int128 v52; // [rsp+230h] [rbp+130h] BYREF
  __int64 v53; // [rsp+240h] [rbp+140h]
  int v54; // [rsp+248h] [rbp+148h] BYREF
  __int128 v55; // [rsp+250h] [rbp+150h] BYREF
  __int64 v56; // [rsp+260h] [rbp+160h]
  int v57; // [rsp+268h] [rbp+168h] BYREF
  __int128 v58; // [rsp+270h] [rbp+170h] BYREF
  __int64 v59; // [rsp+280h] [rbp+180h]
  int v60; // [rsp+288h] [rbp+188h] BYREF
  __int128 v61; // [rsp+290h] [rbp+190h] BYREF
  __int64 v62; // [rsp+2A0h] [rbp+1A0h]
  int v63; // [rsp+2A8h] [rbp+1A8h] BYREF
  __int128 v64; // [rsp+2B0h] [rbp+1B0h] BYREF
  __int64 v65; // [rsp+2C0h] [rbp+1C0h]
  int v66; // [rsp+2C8h] [rbp+1C8h] BYREF
  __int128 v67; // [rsp+2D0h] [rbp+1D0h] BYREF
  __int64 v68; // [rsp+2E0h] [rbp+1E0h]
  int v69; // [rsp+2E8h] [rbp+1E8h] BYREF
  __int128 v70; // [rsp+2F0h] [rbp+1F0h] BYREF
  __int64 v71; // [rsp+300h] [rbp+200h]
  int v72; // [rsp+308h] [rbp+208h] BYREF
  __int128 v73; // [rsp+310h] [rbp+210h] BYREF
  __int64 v74; // [rsp+320h] [rbp+220h]
  int v75; // [rsp+328h] [rbp+228h] BYREF
  __int128 v76; // [rsp+330h] [rbp+230h] BYREF
  __int64 v77; // [rsp+340h] [rbp+240h]
  int v78; // [rsp+348h] [rbp+248h] BYREF
  __int128 v79; // [rsp+350h] [rbp+250h] BYREF
  __int64 v80; // [rsp+360h] [rbp+260h]
  int v81; // [rsp+368h] [rbp+268h] BYREF
  __int128 v82; // [rsp+370h] [rbp+270h] BYREF
  __int64 v83; // [rsp+380h] [rbp+280h]
  int v84; // [rsp+388h] [rbp+288h] BYREF
  __int128 v85; // [rsp+390h] [rbp+290h] BYREF
  __int64 v86; // [rsp+3A0h] [rbp+2A0h]
  int v87; // [rsp+3A8h] [rbp+2A8h] BYREF
  __int128 v88; // [rsp+3B0h] [rbp+2B0h] BYREF
  __int64 v89; // [rsp+3C0h] [rbp+2C0h]
  int v90; // [rsp+3C8h] [rbp+2C8h] BYREF
  __int128 v91; // [rsp+3D0h] [rbp+2D0h] BYREF
  __int64 v92; // [rsp+3E0h] [rbp+2E0h]
  int v93; // [rsp+3E8h] [rbp+2E8h] BYREF
  __int128 v94; // [rsp+3F0h] [rbp+2F0h] BYREF
  __int64 v95; // [rsp+400h] [rbp+300h]
  int v96; // [rsp+408h] [rbp+308h] BYREF
  __int128 v97; // [rsp+410h] [rbp+310h] BYREF
  __int64 v98; // [rsp+420h] [rbp+320h]
  int v99; // [rsp+428h] [rbp+328h] BYREF
  __int128 v100; // [rsp+430h] [rbp+330h] BYREF
  __int64 v101; // [rsp+440h] [rbp+340h]
  int v102; // [rsp+448h] [rbp+348h] BYREF
  __int128 v103; // [rsp+450h] [rbp+350h] BYREF
  __int64 v104; // [rsp+460h] [rbp+360h]
  int v105; // [rsp+468h] [rbp+368h] BYREF
  __int128 v106; // [rsp+470h] [rbp+370h] BYREF
  __int64 v107; // [rsp+480h] [rbp+380h]
  int v108; // [rsp+488h] [rbp+388h] BYREF
  __int128 v109; // [rsp+490h] [rbp+390h] BYREF
  __int64 v110; // [rsp+4A0h] [rbp+3A0h]
  int v111; // [rsp+4A8h] [rbp+3A8h] BYREF
  __int128 v112; // [rsp+4B0h] [rbp+3B0h] BYREF
  __int64 v113; // [rsp+4C0h] [rbp+3C0h]
  _QWORD *v114; // [rsp+4C8h] [rbp+3C8h]
  const wchar_t *v115; // [rsp+4D0h] [rbp+3D0h] BYREF
  __int16 v116; // [rsp+4D8h] [rbp+3D8h]
  char v117; // [rsp+4DAh] [rbp+3DAh]
  int v118; // [rsp+4DBh] [rbp+3DBh]
  char v119; // [rsp+4DFh] [rbp+3DFh]
  int v120; // [rsp+4E0h] [rbp+3E0h]
  __int64 v121; // [rsp+4E8h] [rbp+3E8h]
  __int64 v122; // [rsp+4F0h] [rbp+3F0h]
  int v123; // [rsp+4F8h] [rbp+3F8h]
  __int64 v124; // [rsp+500h] [rbp+400h]
  __int64 v125; // [rsp+508h] [rbp+408h]
  int v126; // [rsp+510h] [rbp+410h]
  __int64 v127; // [rsp+518h] [rbp+418h]
  __int64 v128; // [rsp+520h] [rbp+420h]
  int v129; // [rsp+528h] [rbp+428h]
  __int64 v130; // [rsp+530h] [rbp+430h]
  __int64 v131; // [rsp+538h] [rbp+438h]
  int v132; // [rsp+540h] [rbp+440h]
  __int64 v133; // [rsp+548h] [rbp+448h]
  __int64 v134; // [rsp+550h] [rbp+450h]
  int v135; // [rsp+558h] [rbp+458h]
  __int64 v136; // [rsp+560h] [rbp+460h]
  __int64 v137; // [rsp+568h] [rbp+468h]
  int v138; // [rsp+570h] [rbp+470h]
  __int64 v139; // [rsp+578h] [rbp+478h]
  __int64 v140; // [rsp+580h] [rbp+480h]
  int v141; // [rsp+588h] [rbp+488h]
  __int64 v142; // [rsp+590h] [rbp+490h]
  __int64 v143; // [rsp+598h] [rbp+498h]
  int v144; // [rsp+5A0h] [rbp+4A0h]
  __int64 v145; // [rsp+5A8h] [rbp+4A8h]
  __int64 v146; // [rsp+5B0h] [rbp+4B0h]
  int v147; // [rsp+5B8h] [rbp+4B8h]
  __int16 (__fastcall *v148)(PrivacySettingsInfo *__hidden); // [rsp+5C0h] [rbp+4C0h]
  __int64 v149; // [rsp+5C8h] [rbp+4C8h]
  int v150; // [rsp+5D0h] [rbp+4D0h]
  __int64 v151; // [rsp+5D8h] [rbp+4D8h]
  __int64 v152; // [rsp+5E0h] [rbp+4E0h]
  _BYTE v153[32]; // [rsp+5E8h] [rbp+4E8h] BYREF
  int v154; // [rsp+608h] [rbp+508h]
  __int128 v155; // [rsp+610h] [rbp+510h]
  __int64 v156; // [rsp+620h] [rbp+520h]
  const wchar_t *v157; // [rsp+628h] [rbp+528h]
  __int16 v158; // [rsp+630h] [rbp+530h]
  char v159; // [rsp+632h] [rbp+532h]
  int v160; // [rsp+633h] [rbp+533h]
  char v161; // [rsp+637h] [rbp+537h]
  int v162; // [rsp+638h] [rbp+538h]
  __int64 v163; // [rsp+640h] [rbp+540h]
  __int64 v164; // [rsp+648h] [rbp+548h]
  int v165; // [rsp+650h] [rbp+550h]
  __int64 v166; // [rsp+658h] [rbp+558h]
  __int64 v167; // [rsp+660h] [rbp+560h]
  int v168; // [rsp+668h] [rbp+568h]
  __int64 v169; // [rsp+670h] [rbp+570h]
  __int64 v170; // [rsp+678h] [rbp+578h]
  int v171; // [rsp+680h] [rbp+580h]
  __int64 v172; // [rsp+688h] [rbp+588h]
  __int64 v173; // [rsp+690h] [rbp+590h]
  int v174; // [rsp+698h] [rbp+598h]
  __int64 v175; // [rsp+6A0h] [rbp+5A0h]
  __int64 v176; // [rsp+6A8h] [rbp+5A8h]
  int v177; // [rsp+6B0h] [rbp+5B0h]
  __int64 v178; // [rsp+6B8h] [rbp+5B8h]
  __int64 v179; // [rsp+6C0h] [rbp+5C0h]
  int v180; // [rsp+6C8h] [rbp+5C8h]
  __int64 v181; // [rsp+6D0h] [rbp+5D0h]
  __int64 v182; // [rsp+6D8h] [rbp+5D8h]
  int v183; // [rsp+6E0h] [rbp+5E0h]
  __int64 v184; // [rsp+6E8h] [rbp+5E8h]
  __int64 v185; // [rsp+6F0h] [rbp+5F0h]
  int v186; // [rsp+6F8h] [rbp+5F8h]
  __int64 v187; // [rsp+700h] [rbp+600h]
  __int64 v188; // [rsp+708h] [rbp+608h]
  int v189; // [rsp+710h] [rbp+610h]
  __int16 (__fastcall *v190)(PrivacySettingsInfo *__hidden); // [rsp+718h] [rbp+618h]
  __int64 v191; // [rsp+720h] [rbp+620h]
  int v192; // [rsp+728h] [rbp+628h]
  __int64 v193; // [rsp+730h] [rbp+630h]
  __int64 v194; // [rsp+738h] [rbp+638h]
  _BYTE v195[32]; // [rsp+740h] [rbp+640h] BYREF
  int v196; // [rsp+760h] [rbp+660h]
  __int64 v197; // [rsp+768h] [rbp+668h]
  __int128 v198; // [rsp+770h] [rbp+670h]
  const wchar_t *v199; // [rsp+780h] [rbp+680h]
  __int16 v200; // [rsp+788h] [rbp+688h]
  char v201; // [rsp+78Ah] [rbp+68Ah]
  int v202; // [rsp+78Bh] [rbp+68Bh]
  char v203; // [rsp+78Fh] [rbp+68Fh]
  int v204; // [rsp+790h] [rbp+690h]
  __int64 v205; // [rsp+798h] [rbp+698h]
  __int64 v206; // [rsp+7A0h] [rbp+6A0h]
  int v207; // [rsp+7A8h] [rbp+6A8h]
  __int64 v208; // [rsp+7B0h] [rbp+6B0h]
  __int64 v209; // [rsp+7B8h] [rbp+6B8h]
  int v210; // [rsp+7C0h] [rbp+6C0h]
  __int64 v211; // [rsp+7C8h] [rbp+6C8h]
  __int64 v212; // [rsp+7D0h] [rbp+6D0h]
  int v213; // [rsp+7D8h] [rbp+6D8h]
  __int64 v214; // [rsp+7E0h] [rbp+6E0h]
  __int64 v215; // [rsp+7E8h] [rbp+6E8h]
  int v216; // [rsp+7F0h] [rbp+6F0h]
  __int64 v217; // [rsp+7F8h] [rbp+6F8h]
  __int64 v218; // [rsp+800h] [rbp+700h]
  int v219; // [rsp+808h] [rbp+708h]
  __int64 v220; // [rsp+810h] [rbp+710h]
  __int64 v221; // [rsp+818h] [rbp+718h]
  int v222; // [rsp+820h] [rbp+720h]
  __int64 v223; // [rsp+828h] [rbp+728h]
  __int64 v224; // [rsp+830h] [rbp+730h]
  int v225; // [rsp+838h] [rbp+738h]
  __int64 v226; // [rsp+840h] [rbp+740h]
  __int64 v227; // [rsp+848h] [rbp+748h]
  int v228; // [rsp+850h] [rbp+750h]
  __int64 v229; // [rsp+858h] [rbp+758h]
  __int64 v230; // [rsp+860h] [rbp+760h]
  int v231; // [rsp+868h] [rbp+768h]
  __int16 (__fastcall *v232)(PrivacySettingsInfo *__hidden); // [rsp+870h] [rbp+770h]
  __int64 v233; // [rsp+878h] [rbp+778h]
  int v234; // [rsp+880h] [rbp+780h]
  __int64 v235; // [rsp+888h] [rbp+788h]
  __int64 v236; // [rsp+890h] [rbp+790h]
  _BYTE v237[32]; // [rsp+898h] [rbp+798h] BYREF
  int v238; // [rsp+8B8h] [rbp+7B8h]
  __int128 v239; // [rsp+8C0h] [rbp+7C0h]
  __int64 v240; // [rsp+8D0h] [rbp+7D0h]
  const wchar_t *v241; // [rsp+8D8h] [rbp+7D8h]
  __int16 v242; // [rsp+8E0h] [rbp+7E0h]
  char v243; // [rsp+8E2h] [rbp+7E2h]
  int v244; // [rsp+8E3h] [rbp+7E3h]
  char v245; // [rsp+8E7h] [rbp+7E7h]
  int v246; // [rsp+8E8h] [rbp+7E8h]
  __int64 v247; // [rsp+8F0h] [rbp+7F0h]
  __int64 v248; // [rsp+8F8h] [rbp+7F8h]
  int v249; // [rsp+900h] [rbp+800h]
  __int64 v250; // [rsp+908h] [rbp+808h]
  __int64 v251; // [rsp+910h] [rbp+810h]
  int v252; // [rsp+918h] [rbp+818h]
  __int64 v253; // [rsp+920h] [rbp+820h]
  __int64 v254; // [rsp+928h] [rbp+828h]
  int v255; // [rsp+930h] [rbp+830h]
  __int64 v256; // [rsp+938h] [rbp+838h]
  __int64 v257; // [rsp+940h] [rbp+840h]
  int v258; // [rsp+948h] [rbp+848h]
  __int64 v259; // [rsp+950h] [rbp+850h]
  __int64 v260; // [rsp+958h] [rbp+858h]
  int v261; // [rsp+960h] [rbp+860h]
  __int64 v262; // [rsp+968h] [rbp+868h]
  __int64 v263; // [rsp+970h] [rbp+870h]
  int v264; // [rsp+978h] [rbp+878h]
  __int64 v265; // [rsp+980h] [rbp+880h]
  __int64 v266; // [rsp+988h] [rbp+888h]
  int v267; // [rsp+990h] [rbp+890h]
  __int64 v268; // [rsp+998h] [rbp+898h]
  __int64 v269; // [rsp+9A0h] [rbp+8A0h]
  int v270; // [rsp+9A8h] [rbp+8A8h]
  __int64 v271; // [rsp+9B0h] [rbp+8B0h]
  __int64 v272; // [rsp+9B8h] [rbp+8B8h]
  int v273; // [rsp+9C0h] [rbp+8C0h]
  __int16 (__fastcall *v274)(PrivacySettingsInfo *__hidden); // [rsp+9C8h] [rbp+8C8h]
  __int64 v275; // [rsp+9D0h] [rbp+8D0h]
  int v276; // [rsp+9D8h] [rbp+8D8h]
  __int64 v277; // [rsp+9E0h] [rbp+8E0h]
  __int64 v278; // [rsp+9E8h] [rbp+8E8h]
  _BYTE v279[32]; // [rsp+9F0h] [rbp+8F0h] BYREF
  int v280; // [rsp+A10h] [rbp+910h]
  __int64 v281; // [rsp+A18h] [rbp+918h]
  __int128 v282; // [rsp+A20h] [rbp+920h]
  const wchar_t *v283; // [rsp+A30h] [rbp+930h]
  __int16 v284; // [rsp+A38h] [rbp+938h]
  char v285; // [rsp+A3Ah] [rbp+93Ah]
  int v286; // [rsp+A3Bh] [rbp+93Bh]
  char v287; // [rsp+A3Fh] [rbp+93Fh]
  int v288; // [rsp+A40h] [rbp+940h]
  __int64 v289; // [rsp+A48h] [rbp+948h]
  __int64 v290; // [rsp+A50h] [rbp+950h]
  int v291; // [rsp+A58h] [rbp+958h]
  __int64 v292; // [rsp+A60h] [rbp+960h]
  __int64 v293; // [rsp+A68h] [rbp+968h]
  int v294; // [rsp+A70h] [rbp+970h]
  __int64 v295; // [rsp+A78h] [rbp+978h]
  __int64 v296; // [rsp+A80h] [rbp+980h]
  int v297; // [rsp+A88h] [rbp+988h]
  __int64 v298; // [rsp+A90h] [rbp+990h]
  __int64 v299; // [rsp+A98h] [rbp+998h]
  int v300; // [rsp+AA0h] [rbp+9A0h]
  __int64 v301; // [rsp+AA8h] [rbp+9A8h]
  __int64 v302; // [rsp+AB0h] [rbp+9B0h]
  int v303; // [rsp+AB8h] [rbp+9B8h]
  __int64 v304; // [rsp+AC0h] [rbp+9C0h]
  __int64 v305; // [rsp+AC8h] [rbp+9C8h]
  int v306; // [rsp+AD0h] [rbp+9D0h]
  __int64 v307; // [rsp+AD8h] [rbp+9D8h]
  __int64 v308; // [rsp+AE0h] [rbp+9E0h]
  int v309; // [rsp+AE8h] [rbp+9E8h]
  __int64 v310; // [rsp+AF0h] [rbp+9F0h]
  __int64 v311; // [rsp+AF8h] [rbp+9F8h]
  int v312; // [rsp+B00h] [rbp+A00h]
  __int64 v313; // [rsp+B08h] [rbp+A08h]
  __int64 v314; // [rsp+B10h] [rbp+A10h]
  int v315; // [rsp+B18h] [rbp+A18h]
  __int16 (__fastcall *v316)(PrivacySettingsInfo *__hidden); // [rsp+B20h] [rbp+A20h]
  __int64 v317; // [rsp+B28h] [rbp+A28h]
  int v318; // [rsp+B30h] [rbp+A30h]
  __int64 v319; // [rsp+B38h] [rbp+A38h]
  __int64 v320; // [rsp+B40h] [rbp+A40h]
  _BYTE v321[32]; // [rsp+B48h] [rbp+A48h] BYREF
  int v322; // [rsp+B68h] [rbp+A68h]
  __int128 v323; // [rsp+B70h] [rbp+A70h]
  __int64 v324; // [rsp+B80h] [rbp+A80h]
  const wchar_t *v325; // [rsp+B88h] [rbp+A88h]
  __int16 v326; // [rsp+B90h] [rbp+A90h]
  char v327; // [rsp+B92h] [rbp+A92h]
  int v328; // [rsp+B93h] [rbp+A93h]
  char v329; // [rsp+B97h] [rbp+A97h]
  int v330; // [rsp+B98h] [rbp+A98h]
  __int64 v331; // [rsp+BA0h] [rbp+AA0h]
  __int64 v332; // [rsp+BA8h] [rbp+AA8h]
  int v333; // [rsp+BB0h] [rbp+AB0h]
  __int64 v334; // [rsp+BB8h] [rbp+AB8h]
  __int64 v335; // [rsp+BC0h] [rbp+AC0h]
  int v336; // [rsp+BC8h] [rbp+AC8h]
  __int64 v337; // [rsp+BD0h] [rbp+AD0h]
  __int64 v338; // [rsp+BD8h] [rbp+AD8h]
  int v339; // [rsp+BE0h] [rbp+AE0h]
  __int64 v340; // [rsp+BE8h] [rbp+AE8h]
  __int64 v341; // [rsp+BF0h] [rbp+AF0h]
  int v342; // [rsp+BF8h] [rbp+AF8h]
  __int64 v343; // [rsp+C00h] [rbp+B00h]
  __int64 v344; // [rsp+C08h] [rbp+B08h]
  int v345; // [rsp+C10h] [rbp+B10h]
  __int64 v346; // [rsp+C18h] [rbp+B18h]
  __int64 v347; // [rsp+C20h] [rbp+B20h]
  int v348; // [rsp+C28h] [rbp+B28h]
  __int64 v349; // [rsp+C30h] [rbp+B30h]
  __int64 v350; // [rsp+C38h] [rbp+B38h]
  int v351; // [rsp+C40h] [rbp+B40h]
  __int64 v352; // [rsp+C48h] [rbp+B48h]
  __int64 v353; // [rsp+C50h] [rbp+B50h]
  int v354; // [rsp+C58h] [rbp+B58h]
  __int64 v355; // [rsp+C60h] [rbp+B60h]
  __int64 v356; // [rsp+C68h] [rbp+B68h]
  int v357; // [rsp+C70h] [rbp+B70h]
  __int16 (__fastcall *v358)(PrivacySettingsInfo *__hidden); // [rsp+C78h] [rbp+B78h]
  __int64 v359; // [rsp+C80h] [rbp+B80h]
  int v360; // [rsp+C88h] [rbp+B88h]
  __int64 v361; // [rsp+C90h] [rbp+B90h]
  __int64 v362; // [rsp+C98h] [rbp+B98h]
  _BYTE v363[32]; // [rsp+CA0h] [rbp+BA0h] BYREF
  int v364; // [rsp+CC0h] [rbp+BC0h]
  __int64 v365; // [rsp+CC8h] [rbp+BC8h]
  __int128 v366; // [rsp+CD0h] [rbp+BD0h]
  const wchar_t *v367; // [rsp+CE0h] [rbp+BE0h]
  __int16 v368; // [rsp+CE8h] [rbp+BE8h]
  char v369; // [rsp+CEAh] [rbp+BEAh]
  int v370; // [rsp+CEBh] [rbp+BEBh]
  char v371; // [rsp+CEFh] [rbp+BEFh]
  int v372; // [rsp+CF0h] [rbp+BF0h]
  __int64 v373; // [rsp+CF8h] [rbp+BF8h]
  __int64 v374; // [rsp+D00h] [rbp+C00h]
  int v375; // [rsp+D08h] [rbp+C08h]
  __int64 v376; // [rsp+D10h] [rbp+C10h]
  __int64 v377; // [rsp+D18h] [rbp+C18h]
  int v378; // [rsp+D20h] [rbp+C20h]
  __int64 v379; // [rsp+D28h] [rbp+C28h]
  __int64 v380; // [rsp+D30h] [rbp+C30h]
  int v381; // [rsp+D38h] [rbp+C38h]
  __int64 v382; // [rsp+D40h] [rbp+C40h]
  __int64 v383; // [rsp+D48h] [rbp+C48h]
  int v384; // [rsp+D50h] [rbp+C50h]
  __int64 v385; // [rsp+D58h] [rbp+C58h]
  __int64 v386; // [rsp+D60h] [rbp+C60h]
  int v387; // [rsp+D68h] [rbp+C68h]
  __int64 v388; // [rsp+D70h] [rbp+C70h]
  __int64 v389; // [rsp+D78h] [rbp+C78h]
  int v390; // [rsp+D80h] [rbp+C80h]
  __int64 v391; // [rsp+D88h] [rbp+C88h]
  __int64 v392; // [rsp+D90h] [rbp+C90h]
  int v393; // [rsp+D98h] [rbp+C98h]
  __int64 v394; // [rsp+DA0h] [rbp+CA0h]
  __int64 v395; // [rsp+DA8h] [rbp+CA8h]
  int v396; // [rsp+DB0h] [rbp+CB0h]
  __int64 v397; // [rsp+DB8h] [rbp+CB8h]
  __int64 v398; // [rsp+DC0h] [rbp+CC0h]
  int v399; // [rsp+DC8h] [rbp+CC8h]
  __int16 (__fastcall *v400)(PrivacySettingsInfo *__hidden); // [rsp+DD0h] [rbp+CD0h]
  __int64 v401; // [rsp+DD8h] [rbp+CD8h]
  int v402; // [rsp+DE0h] [rbp+CE0h]
  __int64 v403; // [rsp+DE8h] [rbp+CE8h]
  __int64 v404; // [rsp+DF0h] [rbp+CF0h]
  _BYTE v405[32]; // [rsp+DF8h] [rbp+CF8h] BYREF
  int v406; // [rsp+E18h] [rbp+D18h]
  __int128 v407; // [rsp+E20h] [rbp+D20h]
  __int64 v408; // [rsp+E30h] [rbp+D30h]
  const wchar_t *v409; // [rsp+E38h] [rbp+D38h]
  __int16 v410; // [rsp+E40h] [rbp+D40h]
  char v411; // [rsp+E42h] [rbp+D42h]
  int v412; // [rsp+E43h] [rbp+D43h]
  char v413; // [rsp+E47h] [rbp+D47h]
  int v414; // [rsp+E48h] [rbp+D48h]
  __int64 v415; // [rsp+E50h] [rbp+D50h]
  __int64 v416; // [rsp+E58h] [rbp+D58h]
  int v417; // [rsp+E60h] [rbp+D60h]
  __int64 v418; // [rsp+E68h] [rbp+D68h]
  __int64 v419; // [rsp+E70h] [rbp+D70h]
  int v420; // [rsp+E78h] [rbp+D78h]
  __int64 v421; // [rsp+E80h] [rbp+D80h]
  __int64 v422; // [rsp+E88h] [rbp+D88h]
  int v423; // [rsp+E90h] [rbp+D90h]
  __int64 v424; // [rsp+E98h] [rbp+D98h]
  __int64 v425; // [rsp+EA0h] [rbp+DA0h]
  int v426; // [rsp+EA8h] [rbp+DA8h]
  __int64 v427; // [rsp+EB0h] [rbp+DB0h]
  __int64 v428; // [rsp+EB8h] [rbp+DB8h]
  int v429; // [rsp+EC0h] [rbp+DC0h]
  __int64 v430; // [rsp+EC8h] [rbp+DC8h]
  __int64 v431; // [rsp+ED0h] [rbp+DD0h]
  int v432; // [rsp+ED8h] [rbp+DD8h]
  __int64 v433; // [rsp+EE0h] [rbp+DE0h]
  __int64 v434; // [rsp+EE8h] [rbp+DE8h]
  int v435; // [rsp+EF0h] [rbp+DF0h]
  __int64 v436; // [rsp+EF8h] [rbp+DF8h]
  __int64 v437; // [rsp+F00h] [rbp+E00h]
  int v438; // [rsp+F08h] [rbp+E08h]
  __int64 v439; // [rsp+F10h] [rbp+E10h]
  __int64 v440; // [rsp+F18h] [rbp+E18h]
  int v441; // [rsp+F20h] [rbp+E20h]
  __int16 (__fastcall *v442)(PrivacySettingsInfo *__hidden); // [rsp+F28h] [rbp+E28h]
  __int64 v443; // [rsp+F30h] [rbp+E30h]
  int v444; // [rsp+F38h] [rbp+E38h]
  __int64 v445; // [rsp+F40h] [rbp+E40h]
  __int64 v446; // [rsp+F48h] [rbp+E48h]
  _BYTE v447[32]; // [rsp+F50h] [rbp+E50h] BYREF
  int v448; // [rsp+F70h] [rbp+E70h]
  __int64 v449; // [rsp+F78h] [rbp+E78h]
  __int128 v450; // [rsp+F80h] [rbp+E80h]
  const wchar_t *v451; // [rsp+F90h] [rbp+E90h]
  __int16 v452; // [rsp+F98h] [rbp+E98h]
  char v453; // [rsp+F9Ah] [rbp+E9Ah]
  int v454; // [rsp+F9Bh] [rbp+E9Bh]
  char v455; // [rsp+F9Fh] [rbp+E9Fh]
  int v456; // [rsp+FA0h] [rbp+EA0h]
  __int64 v457; // [rsp+FA8h] [rbp+EA8h]
  __int64 v458; // [rsp+FB0h] [rbp+EB0h]
  int v459; // [rsp+FB8h] [rbp+EB8h]
  __int64 v460; // [rsp+FC0h] [rbp+EC0h]
  __int64 v461; // [rsp+FC8h] [rbp+EC8h]
  int v462; // [rsp+FD0h] [rbp+ED0h]
  __int64 v463; // [rsp+FD8h] [rbp+ED8h]
  __int64 v464; // [rsp+FE0h] [rbp+EE0h]
  int v465; // [rsp+FE8h] [rbp+EE8h]
  __int64 v466; // [rsp+FF0h] [rbp+EF0h]
  __int64 v467; // [rsp+FF8h] [rbp+EF8h]
  int v468; // [rsp+1000h] [rbp+F00h]
  __int64 v469; // [rsp+1008h] [rbp+F08h]
  __int64 v470; // [rsp+1010h] [rbp+F10h]
  int v471; // [rsp+1018h] [rbp+F18h]
  __int64 v472; // [rsp+1020h] [rbp+F20h]
  __int64 v473; // [rsp+1028h] [rbp+F28h]
  int v474; // [rsp+1030h] [rbp+F30h]
  __int64 v475; // [rsp+1038h] [rbp+F38h]
  __int64 v476; // [rsp+1040h] [rbp+F40h]
  int v477; // [rsp+1048h] [rbp+F48h]
  __int64 v478; // [rsp+1050h] [rbp+F50h]
  __int64 v479; // [rsp+1058h] [rbp+F58h]
  int v480; // [rsp+1060h] [rbp+F60h]
  __int64 v481; // [rsp+1068h] [rbp+F68h]
  __int64 v482; // [rsp+1070h] [rbp+F70h]
  int v483; // [rsp+1078h] [rbp+F78h]
  __int16 (__fastcall *v484)(PrivacySettingsInfo *__hidden); // [rsp+1080h] [rbp+F80h]
  __int64 v485; // [rsp+1088h] [rbp+F88h]
  int v486; // [rsp+1090h] [rbp+F90h]
  __int64 v487; // [rsp+1098h] [rbp+F98h]
  __int64 v488; // [rsp+10A0h] [rbp+FA0h]
  _BYTE v489[32]; // [rsp+10A8h] [rbp+FA8h] BYREF
  int v490; // [rsp+10C8h] [rbp+FC8h]
  __int128 v491; // [rsp+10D0h] [rbp+FD0h]
  __int64 v492; // [rsp+10E0h] [rbp+FE0h]
  const wchar_t *v493; // [rsp+10E8h] [rbp+FE8h]
  __int16 v494; // [rsp+10F0h] [rbp+FF0h]
  char v495; // [rsp+10F2h] [rbp+FF2h]
  int v496; // [rsp+10F3h] [rbp+FF3h]
  char v497; // [rsp+10F7h] [rbp+FF7h]
  int v498; // [rsp+10F8h] [rbp+FF8h]
  __int64 v499; // [rsp+1100h] [rbp+1000h]
  __int64 v500; // [rsp+1108h] [rbp+1008h]
  int v501; // [rsp+1110h] [rbp+1010h]
  __int64 v502; // [rsp+1118h] [rbp+1018h]
  __int64 v503; // [rsp+1120h] [rbp+1020h]
  int v504; // [rsp+1128h] [rbp+1028h]
  __int64 v505; // [rsp+1130h] [rbp+1030h]
  __int64 v506; // [rsp+1138h] [rbp+1038h]
  int v507; // [rsp+1140h] [rbp+1040h]
  __int64 v508; // [rsp+1148h] [rbp+1048h]
  __int64 v509; // [rsp+1150h] [rbp+1050h]
  int v510; // [rsp+1158h] [rbp+1058h]
  __int64 v511; // [rsp+1160h] [rbp+1060h]
  __int64 v512; // [rsp+1168h] [rbp+1068h]
  int v513; // [rsp+1170h] [rbp+1070h]
  __int64 v514; // [rsp+1178h] [rbp+1078h]
  __int64 v515; // [rsp+1180h] [rbp+1080h]
  int v516; // [rsp+1188h] [rbp+1088h]
  __int64 v517; // [rsp+1190h] [rbp+1090h]
  __int64 v518; // [rsp+1198h] [rbp+1098h]
  int v519; // [rsp+11A0h] [rbp+10A0h]
  __int64 v520; // [rsp+11A8h] [rbp+10A8h]
  __int64 v521; // [rsp+11B0h] [rbp+10B0h]
  int v522; // [rsp+11B8h] [rbp+10B8h]
  __int64 v523; // [rsp+11C0h] [rbp+10C0h]
  __int64 v524; // [rsp+11C8h] [rbp+10C8h]
  int v525; // [rsp+11D0h] [rbp+10D0h]
  __int16 (__fastcall *v526)(PrivacySettingsInfo *__hidden); // [rsp+11D8h] [rbp+10D8h]
  __int64 v527; // [rsp+11E0h] [rbp+10E0h]
  int v528; // [rsp+11E8h] [rbp+10E8h]
  __int64 v529; // [rsp+11F0h] [rbp+10F0h]
  __int64 v530; // [rsp+11F8h] [rbp+10F8h]
  _BYTE v531[32]; // [rsp+1200h] [rbp+1100h] BYREF
  int v532; // [rsp+1220h] [rbp+1120h]
  __int64 v533; // [rsp+1228h] [rbp+1128h]
  __int128 v534; // [rsp+1230h] [rbp+1130h]
  const wchar_t *v535; // [rsp+1240h] [rbp+1140h]
  __int16 v536; // [rsp+1248h] [rbp+1148h]
  char v537; // [rsp+124Ah] [rbp+114Ah]
  int v538; // [rsp+124Bh] [rbp+114Bh]
  char v539; // [rsp+124Fh] [rbp+114Fh]
  int v540; // [rsp+1250h] [rbp+1150h]
  __int64 v541; // [rsp+1258h] [rbp+1158h]
  __int64 v542; // [rsp+1260h] [rbp+1160h]
  int v543; // [rsp+1268h] [rbp+1168h]
  __int64 v544; // [rsp+1270h] [rbp+1170h]
  __int64 v545; // [rsp+1278h] [rbp+1178h]
  int v546; // [rsp+1280h] [rbp+1180h]
  __int64 v547; // [rsp+1288h] [rbp+1188h]
  __int64 v548; // [rsp+1290h] [rbp+1190h]
  int v549; // [rsp+1298h] [rbp+1198h]
  __int64 v550; // [rsp+12A0h] [rbp+11A0h]
  __int64 v551; // [rsp+12A8h] [rbp+11A8h]
  int v552; // [rsp+12B0h] [rbp+11B0h]
  __int64 v553; // [rsp+12B8h] [rbp+11B8h]
  __int64 v554; // [rsp+12C0h] [rbp+11C0h]
  int v555; // [rsp+12C8h] [rbp+11C8h]
  __int64 v556; // [rsp+12D0h] [rbp+11D0h]
  __int64 v557; // [rsp+12D8h] [rbp+11D8h]
  int v558; // [rsp+12E0h] [rbp+11E0h]
  __int64 v559; // [rsp+12E8h] [rbp+11E8h]
  __int64 v560; // [rsp+12F0h] [rbp+11F0h]
  int v561; // [rsp+12F8h] [rbp+11F8h]
  __int64 v562; // [rsp+1300h] [rbp+1200h]
  __int64 v563; // [rsp+1308h] [rbp+1208h]
  int v564; // [rsp+1310h] [rbp+1210h]
  __int64 v565; // [rsp+1318h] [rbp+1218h]
  __int64 v566; // [rsp+1320h] [rbp+1220h]
  int v567; // [rsp+1328h] [rbp+1228h]
  __int16 (__fastcall *v568)(PrivacySettingsInfo *__hidden); // [rsp+1330h] [rbp+1230h]
  __int64 v569; // [rsp+1338h] [rbp+1238h]
  int v570; // [rsp+1340h] [rbp+1240h]
  __int64 v571; // [rsp+1348h] [rbp+1248h]
  __int64 v572; // [rsp+1350h] [rbp+1250h]
  _BYTE v573[32]; // [rsp+1358h] [rbp+1258h] BYREF
  int v574; // [rsp+1378h] [rbp+1278h]
  __int128 v575; // [rsp+1380h] [rbp+1280h]
  __int64 v576; // [rsp+1390h] [rbp+1290h]
  const wchar_t *v577; // [rsp+1398h] [rbp+1298h]
  __int16 v578; // [rsp+13A0h] [rbp+12A0h]
  char v579; // [rsp+13A2h] [rbp+12A2h]
  int v580; // [rsp+13A3h] [rbp+12A3h]
  char v581; // [rsp+13A7h] [rbp+12A7h]
  int v582; // [rsp+13A8h] [rbp+12A8h]
  __int64 v583; // [rsp+13B0h] [rbp+12B0h]
  __int64 v584; // [rsp+13B8h] [rbp+12B8h]
  int v585; // [rsp+13C0h] [rbp+12C0h]
  __int64 v586; // [rsp+13C8h] [rbp+12C8h]
  __int64 v587; // [rsp+13D0h] [rbp+12D0h]
  int v588; // [rsp+13D8h] [rbp+12D8h]
  __int64 v589; // [rsp+13E0h] [rbp+12E0h]
  __int64 v590; // [rsp+13E8h] [rbp+12E8h]
  int v591; // [rsp+13F0h] [rbp+12F0h]
  __int64 v592; // [rsp+13F8h] [rbp+12F8h]
  __int64 v593; // [rsp+1400h] [rbp+1300h]
  int v594; // [rsp+1408h] [rbp+1308h]
  __int64 v595; // [rsp+1410h] [rbp+1310h]
  __int64 v596; // [rsp+1418h] [rbp+1318h]
  int v597; // [rsp+1420h] [rbp+1320h]
  __int64 v598; // [rsp+1428h] [rbp+1328h]
  __int64 v599; // [rsp+1430h] [rbp+1330h]
  int v600; // [rsp+1438h] [rbp+1338h]
  __int64 v601; // [rsp+1440h] [rbp+1340h]
  __int64 v602; // [rsp+1448h] [rbp+1348h]
  int v603; // [rsp+1450h] [rbp+1350h]
  __int64 v604; // [rsp+1458h] [rbp+1358h]
  __int64 v605; // [rsp+1460h] [rbp+1360h]
  int v606; // [rsp+1468h] [rbp+1368h]
  __int64 v607; // [rsp+1470h] [rbp+1370h]
  __int64 v608; // [rsp+1478h] [rbp+1378h]
  int v609; // [rsp+1480h] [rbp+1380h]
  __int16 (__fastcall *v610)(PrivacySettingsInfo *__hidden); // [rsp+1488h] [rbp+1388h]
  __int64 v611; // [rsp+1490h] [rbp+1390h]
  int v612; // [rsp+1498h] [rbp+1398h]
  __int64 v613; // [rsp+14A0h] [rbp+13A0h]
  __int64 v614; // [rsp+14A8h] [rbp+13A8h]
  _BYTE v615[32]; // [rsp+14B0h] [rbp+13B0h] BYREF
  int v616; // [rsp+14D0h] [rbp+13D0h]
  __int64 v617; // [rsp+14D8h] [rbp+13D8h]
  __int128 v618; // [rsp+14E0h] [rbp+13E0h]
  const wchar_t *v619; // [rsp+14F0h] [rbp+13F0h]
  __int16 v620; // [rsp+14F8h] [rbp+13F8h]
  char v621; // [rsp+14FAh] [rbp+13FAh]
  int v622; // [rsp+14FBh] [rbp+13FBh]
  char v623; // [rsp+14FFh] [rbp+13FFh]
  int v624; // [rsp+1500h] [rbp+1400h]
  __int64 v625; // [rsp+1508h] [rbp+1408h]
  __int64 v626; // [rsp+1510h] [rbp+1410h]
  int v627; // [rsp+1518h] [rbp+1418h]
  __int64 v628; // [rsp+1520h] [rbp+1420h]
  __int64 v629; // [rsp+1528h] [rbp+1428h]
  int v630; // [rsp+1530h] [rbp+1430h]
  __int64 v631; // [rsp+1538h] [rbp+1438h]
  __int64 v632; // [rsp+1540h] [rbp+1440h]
  int v633; // [rsp+1548h] [rbp+1448h]
  __int64 v634; // [rsp+1550h] [rbp+1450h]
  __int64 v635; // [rsp+1558h] [rbp+1458h]
  int v636; // [rsp+1560h] [rbp+1460h]
  __int64 v637; // [rsp+1568h] [rbp+1468h]
  __int64 v638; // [rsp+1570h] [rbp+1470h]
  int v639; // [rsp+1578h] [rbp+1478h]
  __int64 v640; // [rsp+1580h] [rbp+1480h]
  __int64 v641; // [rsp+1588h] [rbp+1488h]
  int v642; // [rsp+1590h] [rbp+1490h]
  __int64 v643; // [rsp+1598h] [rbp+1498h]
  __int64 v644; // [rsp+15A0h] [rbp+14A0h]
  int v645; // [rsp+15A8h] [rbp+14A8h]
  __int64 v646; // [rsp+15B0h] [rbp+14B0h]
  __int64 v647; // [rsp+15B8h] [rbp+14B8h]
  int v648; // [rsp+15C0h] [rbp+14C0h]
  __int64 v649; // [rsp+15C8h] [rbp+14C8h]
  __int64 v650; // [rsp+15D0h] [rbp+14D0h]
  int v651; // [rsp+15D8h] [rbp+14D8h]
  __int16 (__fastcall *v652)(PrivacySettingsInfo *__hidden); // [rsp+15E0h] [rbp+14E0h]
  __int64 v653; // [rsp+15E8h] [rbp+14E8h]
  int v654; // [rsp+15F0h] [rbp+14F0h]
  __int64 v655; // [rsp+15F8h] [rbp+14F8h]
  __int64 v656; // [rsp+1600h] [rbp+1500h]
  _BYTE v657[32]; // [rsp+1608h] [rbp+1508h] BYREF
  int v658; // [rsp+1628h] [rbp+1528h]
  __int128 v659; // [rsp+1630h] [rbp+1530h]
  __int64 v660; // [rsp+1640h] [rbp+1540h]
  const wchar_t *v661; // [rsp+1648h] [rbp+1548h]
  __int16 v662; // [rsp+1650h] [rbp+1550h]
  char v663; // [rsp+1652h] [rbp+1552h]
  int v664; // [rsp+1653h] [rbp+1553h]
  char v665; // [rsp+1657h] [rbp+1557h]
  int v666; // [rsp+1658h] [rbp+1558h]
  __int64 v667; // [rsp+1660h] [rbp+1560h]
  __int64 v668; // [rsp+1668h] [rbp+1568h]
  int v669; // [rsp+1670h] [rbp+1570h]
  __int64 v670; // [rsp+1678h] [rbp+1578h]
  __int64 v671; // [rsp+1680h] [rbp+1580h]
  int v672; // [rsp+1688h] [rbp+1588h]
  __int64 v673; // [rsp+1690h] [rbp+1590h]
  __int64 v674; // [rsp+1698h] [rbp+1598h]
  int v675; // [rsp+16A0h] [rbp+15A0h]
  __int64 v676; // [rsp+16A8h] [rbp+15A8h]
  __int64 v677; // [rsp+16B0h] [rbp+15B0h]
  int v678; // [rsp+16B8h] [rbp+15B8h]
  __int64 v679; // [rsp+16C0h] [rbp+15C0h]
  __int64 v680; // [rsp+16C8h] [rbp+15C8h]
  int v681; // [rsp+16D0h] [rbp+15D0h]
  __int64 v682; // [rsp+16D8h] [rbp+15D8h]
  __int64 v683; // [rsp+16E0h] [rbp+15E0h]
  int v684; // [rsp+16E8h] [rbp+15E8h]
  __int64 v685; // [rsp+16F0h] [rbp+15F0h]
  __int64 v686; // [rsp+16F8h] [rbp+15F8h]
  int v687; // [rsp+1700h] [rbp+1600h]
  __int64 v688; // [rsp+1708h] [rbp+1608h]
  __int64 v689; // [rsp+1710h] [rbp+1610h]
  int v690; // [rsp+1718h] [rbp+1618h]
  __int64 v691; // [rsp+1720h] [rbp+1620h]
  __int64 v692; // [rsp+1728h] [rbp+1628h]
  int v693; // [rsp+1730h] [rbp+1630h]
  __int16 (__fastcall *v694)(PrivacySettingsInfo *__hidden); // [rsp+1738h] [rbp+1638h]
  __int64 v695; // [rsp+1740h] [rbp+1640h]
  int v696; // [rsp+1748h] [rbp+1648h]
  __int64 v697; // [rsp+1750h] [rbp+1650h]
  __int64 v698; // [rsp+1758h] [rbp+1658h]
  _BYTE v699[32]; // [rsp+1760h] [rbp+1660h] BYREF
  int v700; // [rsp+1780h] [rbp+1680h]
  __int64 v701; // [rsp+1788h] [rbp+1688h]
  __int128 v702; // [rsp+1790h] [rbp+1690h]
  const wchar_t *v703; // [rsp+17A0h] [rbp+16A0h]
  __int16 v704; // [rsp+17A8h] [rbp+16A8h]
  char v705; // [rsp+17AAh] [rbp+16AAh]
  int v706; // [rsp+17ABh] [rbp+16ABh]
  char v707; // [rsp+17AFh] [rbp+16AFh]
  int v708; // [rsp+17B0h] [rbp+16B0h]
  __int64 v709; // [rsp+17B8h] [rbp+16B8h]
  __int64 v710; // [rsp+17C0h] [rbp+16C0h]
  int v711; // [rsp+17C8h] [rbp+16C8h]
  __int64 v712; // [rsp+17D0h] [rbp+16D0h]
  __int64 v713; // [rsp+17D8h] [rbp+16D8h]
  int v714; // [rsp+17E0h] [rbp+16E0h]
  __int64 v715; // [rsp+17E8h] [rbp+16E8h]
  __int64 v716; // [rsp+17F0h] [rbp+16F0h]
  int v717; // [rsp+17F8h] [rbp+16F8h]
  __int64 v718; // [rsp+1800h] [rbp+1700h]
  __int64 v719; // [rsp+1808h] [rbp+1708h]
  int v720; // [rsp+1810h] [rbp+1710h]
  __int64 v721; // [rsp+1818h] [rbp+1718h]
  __int64 v722; // [rsp+1820h] [rbp+1720h]
  int v723; // [rsp+1828h] [rbp+1728h]
  __int64 v724; // [rsp+1830h] [rbp+1730h]
  __int64 v725; // [rsp+1838h] [rbp+1738h]
  int v726; // [rsp+1840h] [rbp+1740h]
  __int64 v727; // [rsp+1848h] [rbp+1748h]
  __int64 v728; // [rsp+1850h] [rbp+1750h]
  int v729; // [rsp+1858h] [rbp+1758h]
  __int64 v730; // [rsp+1860h] [rbp+1760h]
  __int64 v731; // [rsp+1868h] [rbp+1768h]
  int v732; // [rsp+1870h] [rbp+1770h]
  __int64 v733; // [rsp+1878h] [rbp+1778h]
  __int64 v734; // [rsp+1880h] [rbp+1780h]
  int v735; // [rsp+1888h] [rbp+1788h]
  __int16 (__fastcall *v736)(PrivacySettingsInfo *__hidden); // [rsp+1890h] [rbp+1790h]
  __int64 v737; // [rsp+1898h] [rbp+1798h]
  int v738; // [rsp+18A0h] [rbp+17A0h]
  __int64 v739; // [rsp+18A8h] [rbp+17A8h]
  __int64 v740; // [rsp+18B0h] [rbp+17B0h]
  _BYTE v741[32]; // [rsp+18B8h] [rbp+17B8h] BYREF
  int v742; // [rsp+18D8h] [rbp+17D8h]
  __int128 v743; // [rsp+18E0h] [rbp+17E0h]
  __int64 v744; // [rsp+18F0h] [rbp+17F0h]
  const wchar_t *v745; // [rsp+18F8h] [rbp+17F8h]
  __int16 v746; // [rsp+1900h] [rbp+1800h]
  char v747; // [rsp+1902h] [rbp+1802h]
  int v748; // [rsp+1903h] [rbp+1803h]
  char v749; // [rsp+1907h] [rbp+1807h]
  int v750; // [rsp+1908h] [rbp+1808h]
  __int64 v751; // [rsp+1910h] [rbp+1810h]
  __int64 v752; // [rsp+1918h] [rbp+1818h]
  int v753; // [rsp+1920h] [rbp+1820h]
  __int64 v754; // [rsp+1928h] [rbp+1828h]
  __int64 v755; // [rsp+1930h] [rbp+1830h]
  int v756; // [rsp+1938h] [rbp+1838h]
  __int64 v757; // [rsp+1940h] [rbp+1840h]
  __int64 v758; // [rsp+1948h] [rbp+1848h]
  int v759; // [rsp+1950h] [rbp+1850h]
  __int64 v760; // [rsp+1958h] [rbp+1858h]
  __int64 v761; // [rsp+1960h] [rbp+1860h]
  int v762; // [rsp+1968h] [rbp+1868h]
  __int64 v763; // [rsp+1970h] [rbp+1870h]
  __int64 v764; // [rsp+1978h] [rbp+1878h]
  int v765; // [rsp+1980h] [rbp+1880h]
  __int64 v766; // [rsp+1988h] [rbp+1888h]
  __int64 v767; // [rsp+1990h] [rbp+1890h]
  int v768; // [rsp+1998h] [rbp+1898h]
  __int64 v769; // [rsp+19A0h] [rbp+18A0h]
  __int64 v770; // [rsp+19A8h] [rbp+18A8h]
  int v771; // [rsp+19B0h] [rbp+18B0h]
  __int64 v772; // [rsp+19B8h] [rbp+18B8h]
  __int64 v773; // [rsp+19C0h] [rbp+18C0h]
  int v774; // [rsp+19C8h] [rbp+18C8h]
  __int64 v775; // [rsp+19D0h] [rbp+18D0h]
  __int64 v776; // [rsp+19D8h] [rbp+18D8h]
  int v777; // [rsp+19E0h] [rbp+18E0h]
  __int16 (__fastcall *v778)(PrivacySettingsInfo *__hidden); // [rsp+19E8h] [rbp+18E8h]
  __int64 v779; // [rsp+19F0h] [rbp+18F0h]
  int v780; // [rsp+19F8h] [rbp+18F8h]
  __int64 v781; // [rsp+1A00h] [rbp+1900h]
  __int64 v782; // [rsp+1A08h] [rbp+1908h]
  _BYTE v783[32]; // [rsp+1A10h] [rbp+1910h] BYREF
  int v784; // [rsp+1A30h] [rbp+1930h]
  __int64 v785; // [rsp+1A38h] [rbp+1938h]
  __int128 v786; // [rsp+1A40h] [rbp+1940h]
  const wchar_t *v787; // [rsp+1A50h] [rbp+1950h]
  __int16 v788; // [rsp+1A58h] [rbp+1958h]
  char v789; // [rsp+1A5Ah] [rbp+195Ah]
  int v790; // [rsp+1A5Bh] [rbp+195Bh]
  char v791; // [rsp+1A5Fh] [rbp+195Fh]
  int v792; // [rsp+1A60h] [rbp+1960h]
  __int64 v793; // [rsp+1A68h] [rbp+1968h]
  __int64 v794; // [rsp+1A70h] [rbp+1970h]
  int v795; // [rsp+1A78h] [rbp+1978h]
  __int64 v796; // [rsp+1A80h] [rbp+1980h]
  __int64 v797; // [rsp+1A88h] [rbp+1988h]
  int v798; // [rsp+1A90h] [rbp+1990h]
  __int64 v799; // [rsp+1A98h] [rbp+1998h]
  __int64 v800; // [rsp+1AA0h] [rbp+19A0h]
  int v801; // [rsp+1AA8h] [rbp+19A8h]
  __int64 v802; // [rsp+1AB0h] [rbp+19B0h]
  __int64 v803; // [rsp+1AB8h] [rbp+19B8h]
  int v804; // [rsp+1AC0h] [rbp+19C0h]
  __int64 v805; // [rsp+1AC8h] [rbp+19C8h]
  __int64 v806; // [rsp+1AD0h] [rbp+19D0h]
  int v807; // [rsp+1AD8h] [rbp+19D8h]
  __int64 v808; // [rsp+1AE0h] [rbp+19E0h]
  __int64 v809; // [rsp+1AE8h] [rbp+19E8h]
  int v810; // [rsp+1AF0h] [rbp+19F0h]
  __int64 v811; // [rsp+1AF8h] [rbp+19F8h]
  __int64 v812; // [rsp+1B00h] [rbp+1A00h]
  int v813; // [rsp+1B08h] [rbp+1A08h]
  __int64 v814; // [rsp+1B10h] [rbp+1A10h]
  __int64 v815; // [rsp+1B18h] [rbp+1A18h]
  int v816; // [rsp+1B20h] [rbp+1A20h]
  __int64 v817; // [rsp+1B28h] [rbp+1A28h]
  __int64 v818; // [rsp+1B30h] [rbp+1A30h]
  int v819; // [rsp+1B38h] [rbp+1A38h]
  __int16 (__fastcall *v820)(PrivacySettingsInfo *__hidden); // [rsp+1B40h] [rbp+1A40h]
  __int64 v821; // [rsp+1B48h] [rbp+1A48h]
  int v822; // [rsp+1B50h] [rbp+1A50h]
  __int64 v823; // [rsp+1B58h] [rbp+1A58h]
  __int64 v824; // [rsp+1B60h] [rbp+1A60h]
  _BYTE v825[32]; // [rsp+1B68h] [rbp+1A68h] BYREF
  int v826; // [rsp+1B88h] [rbp+1A88h]
  __int128 v827; // [rsp+1B90h] [rbp+1A90h]
  __int64 v828; // [rsp+1BA0h] [rbp+1AA0h]
  const wchar_t *v829; // [rsp+1BA8h] [rbp+1AA8h]
  __int16 v830; // [rsp+1BB0h] [rbp+1AB0h]
  char v831; // [rsp+1BB2h] [rbp+1AB2h]
  int v832; // [rsp+1BB3h] [rbp+1AB3h]
  char v833; // [rsp+1BB7h] [rbp+1AB7h]
  int v834; // [rsp+1BB8h] [rbp+1AB8h]
  __int64 v835; // [rsp+1BC0h] [rbp+1AC0h]
  __int64 v836; // [rsp+1BC8h] [rbp+1AC8h]
  int v837; // [rsp+1BD0h] [rbp+1AD0h]
  __int64 v838; // [rsp+1BD8h] [rbp+1AD8h]
  __int64 v839; // [rsp+1BE0h] [rbp+1AE0h]
  int v840; // [rsp+1BE8h] [rbp+1AE8h]
  __int64 v841; // [rsp+1BF0h] [rbp+1AF0h]
  __int64 v842; // [rsp+1BF8h] [rbp+1AF8h]
  int v843; // [rsp+1C00h] [rbp+1B00h]
  __int64 v844; // [rsp+1C08h] [rbp+1B08h]
  __int64 v845; // [rsp+1C10h] [rbp+1B10h]
  int v846; // [rsp+1C18h] [rbp+1B18h]
  __int64 v847; // [rsp+1C20h] [rbp+1B20h]
  __int64 v848; // [rsp+1C28h] [rbp+1B28h]
  int v849; // [rsp+1C30h] [rbp+1B30h]
  __int64 v850; // [rsp+1C38h] [rbp+1B38h]
  __int64 v851; // [rsp+1C40h] [rbp+1B40h]
  int v852; // [rsp+1C48h] [rbp+1B48h]
  __int64 v853; // [rsp+1C50h] [rbp+1B50h]
  __int64 v854; // [rsp+1C58h] [rbp+1B58h]
  int v855; // [rsp+1C60h] [rbp+1B60h]
  __int64 v856; // [rsp+1C68h] [rbp+1B68h]
  __int64 v857; // [rsp+1C70h] [rbp+1B70h]
  int v858; // [rsp+1C78h] [rbp+1B78h]
  __int64 v859; // [rsp+1C80h] [rbp+1B80h]
  __int64 v860; // [rsp+1C88h] [rbp+1B88h]
  int v861; // [rsp+1C90h] [rbp+1B90h]
  __int16 (__fastcall *v862)(PrivacySettingsInfo *__hidden); // [rsp+1C98h] [rbp+1B98h]
  __int64 v863; // [rsp+1CA0h] [rbp+1BA0h]
  int v864; // [rsp+1CA8h] [rbp+1BA8h]
  __int64 v865; // [rsp+1CB0h] [rbp+1BB0h]
  __int64 v866; // [rsp+1CB8h] [rbp+1BB8h]
  _BYTE v867[32]; // [rsp+1CC0h] [rbp+1BC0h] BYREF
  int v868; // [rsp+1CE0h] [rbp+1BE0h]
  __int64 v869; // [rsp+1CE8h] [rbp+1BE8h]
  __int128 v870; // [rsp+1CF0h] [rbp+1BF0h]
  const wchar_t *v871; // [rsp+1D00h] [rbp+1C00h]
  __int16 v872; // [rsp+1D08h] [rbp+1C08h]
  char v873; // [rsp+1D0Ah] [rbp+1C0Ah]
  int v874; // [rsp+1D0Bh] [rbp+1C0Bh]
  char v875; // [rsp+1D0Fh] [rbp+1C0Fh]
  int v876; // [rsp+1D10h] [rbp+1C10h]
  __int64 v877; // [rsp+1D18h] [rbp+1C18h]
  __int64 v878; // [rsp+1D20h] [rbp+1C20h]
  int v879; // [rsp+1D28h] [rbp+1C28h]
  __int64 v880; // [rsp+1D30h] [rbp+1C30h]
  __int64 v881; // [rsp+1D38h] [rbp+1C38h]
  int v882; // [rsp+1D40h] [rbp+1C40h]
  __int64 v883; // [rsp+1D48h] [rbp+1C48h]
  __int64 v884; // [rsp+1D50h] [rbp+1C50h]
  int v885; // [rsp+1D58h] [rbp+1C58h]
  __int64 v886; // [rsp+1D60h] [rbp+1C60h]
  __int64 v887; // [rsp+1D68h] [rbp+1C68h]
  int v888; // [rsp+1D70h] [rbp+1C70h]
  __int64 v889; // [rsp+1D78h] [rbp+1C78h]
  __int64 v890; // [rsp+1D80h] [rbp+1C80h]
  int v891; // [rsp+1D88h] [rbp+1C88h]
  __int64 v892; // [rsp+1D90h] [rbp+1C90h]
  __int64 v893; // [rsp+1D98h] [rbp+1C98h]
  int v894; // [rsp+1DA0h] [rbp+1CA0h]
  __int64 v895; // [rsp+1DA8h] [rbp+1CA8h]
  __int64 v896; // [rsp+1DB0h] [rbp+1CB0h]
  int v897; // [rsp+1DB8h] [rbp+1CB8h]
  __int64 v898; // [rsp+1DC0h] [rbp+1CC0h]
  __int64 v899; // [rsp+1DC8h] [rbp+1CC8h]
  int v900; // [rsp+1DD0h] [rbp+1CD0h]
  __int64 v901; // [rsp+1DD8h] [rbp+1CD8h]
  __int64 v902; // [rsp+1DE0h] [rbp+1CE0h]
  int v903; // [rsp+1DE8h] [rbp+1CE8h]
  __int16 (__fastcall *v904)(PrivacySettingsInfo *__hidden); // [rsp+1DF0h] [rbp+1CF0h]
  __int64 v905; // [rsp+1DF8h] [rbp+1CF8h]
  int v906; // [rsp+1E00h] [rbp+1D00h]
  __int64 v907; // [rsp+1E08h] [rbp+1D08h]
  __int64 v908; // [rsp+1E10h] [rbp+1D10h]
  _BYTE v909[32]; // [rsp+1E18h] [rbp+1D18h] BYREF
  int v910; // [rsp+1E38h] [rbp+1D38h]
  __int128 v911; // [rsp+1E40h] [rbp+1D40h]
  __int64 v912; // [rsp+1E50h] [rbp+1D50h]
  const wchar_t *v913; // [rsp+1E58h] [rbp+1D58h]
  __int16 v914; // [rsp+1E60h] [rbp+1D60h]
  char v915; // [rsp+1E62h] [rbp+1D62h]
  int v916; // [rsp+1E63h] [rbp+1D63h]
  char v917; // [rsp+1E67h] [rbp+1D67h]
  int v918; // [rsp+1E68h] [rbp+1D68h]
  __int64 v919; // [rsp+1E70h] [rbp+1D70h]
  __int64 v920; // [rsp+1E78h] [rbp+1D78h]
  int v921; // [rsp+1E80h] [rbp+1D80h]
  __int64 v922; // [rsp+1E88h] [rbp+1D88h]
  __int64 v923; // [rsp+1E90h] [rbp+1D90h]
  int v924; // [rsp+1E98h] [rbp+1D98h]
  __int64 v925; // [rsp+1EA0h] [rbp+1DA0h]
  __int64 v926; // [rsp+1EA8h] [rbp+1DA8h]
  int v927; // [rsp+1EB0h] [rbp+1DB0h]
  __int64 v928; // [rsp+1EB8h] [rbp+1DB8h]
  __int64 v929; // [rsp+1EC0h] [rbp+1DC0h]
  int v930; // [rsp+1EC8h] [rbp+1DC8h]
  __int64 v931; // [rsp+1ED0h] [rbp+1DD0h]
  __int64 v932; // [rsp+1ED8h] [rbp+1DD8h]
  int v933; // [rsp+1EE0h] [rbp+1DE0h]
  __int64 v934; // [rsp+1EE8h] [rbp+1DE8h]
  __int64 v935; // [rsp+1EF0h] [rbp+1DF0h]
  int v936; // [rsp+1EF8h] [rbp+1DF8h]
  __int64 v937; // [rsp+1F00h] [rbp+1E00h]
  __int64 v938; // [rsp+1F08h] [rbp+1E08h]
  int v939; // [rsp+1F10h] [rbp+1E10h]
  __int64 v940; // [rsp+1F18h] [rbp+1E18h]
  __int64 v941; // [rsp+1F20h] [rbp+1E20h]
  int v942; // [rsp+1F28h] [rbp+1E28h]
  __int64 v943; // [rsp+1F30h] [rbp+1E30h]
  __int64 v944; // [rsp+1F38h] [rbp+1E38h]
  int v945; // [rsp+1F40h] [rbp+1E40h]
  __int16 (__fastcall *v946)(PrivacySettingsInfo *__hidden); // [rsp+1F48h] [rbp+1E48h]
  __int64 v947; // [rsp+1F50h] [rbp+1E50h]
  int v948; // [rsp+1F58h] [rbp+1E58h]
  __int64 v949; // [rsp+1F60h] [rbp+1E60h]
  __int64 v950; // [rsp+1F68h] [rbp+1E68h]
  _BYTE v951[32]; // [rsp+1F70h] [rbp+1E70h] BYREF
  int v952; // [rsp+1F90h] [rbp+1E90h]
  __int64 v953; // [rsp+1F98h] [rbp+1E98h]
  __int128 v954; // [rsp+1FA0h] [rbp+1EA0h]
  const wchar_t *v955; // [rsp+1FB0h] [rbp+1EB0h]
  __int16 v956; // [rsp+1FB8h] [rbp+1EB8h]
  char v957; // [rsp+1FBAh] [rbp+1EBAh]
  int v958; // [rsp+1FBBh] [rbp+1EBBh]
  char v959; // [rsp+1FBFh] [rbp+1EBFh]
  int v960; // [rsp+1FC0h] [rbp+1EC0h]
  __int64 v961; // [rsp+1FC8h] [rbp+1EC8h]
  __int64 v962; // [rsp+1FD0h] [rbp+1ED0h]
  int v963; // [rsp+1FD8h] [rbp+1ED8h]
  __int64 v964; // [rsp+1FE0h] [rbp+1EE0h]
  __int64 v965; // [rsp+1FE8h] [rbp+1EE8h]
  int v966; // [rsp+1FF0h] [rbp+1EF0h]
  __int64 v967; // [rsp+1FF8h] [rbp+1EF8h]
  __int64 v968; // [rsp+2000h] [rbp+1F00h]
  int v969; // [rsp+2008h] [rbp+1F08h]
  __int64 v970; // [rsp+2010h] [rbp+1F10h]
  __int64 v971; // [rsp+2018h] [rbp+1F18h]
  int v972; // [rsp+2020h] [rbp+1F20h]
  __int64 v973; // [rsp+2028h] [rbp+1F28h]
  __int64 v974; // [rsp+2030h] [rbp+1F30h]
  int v975; // [rsp+2038h] [rbp+1F38h]
  __int64 v976; // [rsp+2040h] [rbp+1F40h]
  __int64 v977; // [rsp+2048h] [rbp+1F48h]
  int v978; // [rsp+2050h] [rbp+1F50h]
  __int64 v979; // [rsp+2058h] [rbp+1F58h]
  __int64 v980; // [rsp+2060h] [rbp+1F60h]
  int v981; // [rsp+2068h] [rbp+1F68h]
  __int64 v982; // [rsp+2070h] [rbp+1F70h]
  __int64 v983; // [rsp+2078h] [rbp+1F78h]
  int v984; // [rsp+2080h] [rbp+1F80h]
  __int64 v985; // [rsp+2088h] [rbp+1F88h]
  __int64 v986; // [rsp+2090h] [rbp+1F90h]
  int v987; // [rsp+2098h] [rbp+1F98h]
  __int16 (__fastcall *v988)(PrivacySettingsInfo *__hidden); // [rsp+20A0h] [rbp+1FA0h]
  __int64 v989; // [rsp+20A8h] [rbp+1FA8h]
  int v990; // [rsp+20B0h] [rbp+1FB0h]
  __int64 v991; // [rsp+20B8h] [rbp+1FB8h]
  __int64 v992; // [rsp+20C0h] [rbp+1FC0h]
  _BYTE v993[32]; // [rsp+20C8h] [rbp+1FC8h] BYREF
  int v994; // [rsp+20E8h] [rbp+1FE8h]
  __int128 v995; // [rsp+20F0h] [rbp+1FF0h]
  __int64 v996; // [rsp+2100h] [rbp+2000h]
  const wchar_t *v997; // [rsp+2108h] [rbp+2008h]
  __int16 v998; // [rsp+2110h] [rbp+2010h]
  char v999; // [rsp+2112h] [rbp+2012h]
  int v1000; // [rsp+2113h] [rbp+2013h]
  char v1001; // [rsp+2117h] [rbp+2017h]
  int v1002; // [rsp+2118h] [rbp+2018h]
  __int64 v1003; // [rsp+2120h] [rbp+2020h]
  __int64 v1004; // [rsp+2128h] [rbp+2028h]
  int v1005; // [rsp+2130h] [rbp+2030h]
  __int64 v1006; // [rsp+2138h] [rbp+2038h]
  __int64 v1007; // [rsp+2140h] [rbp+2040h]
  int v1008; // [rsp+2148h] [rbp+2048h]
  __int64 v1009; // [rsp+2150h] [rbp+2050h]
  __int64 v1010; // [rsp+2158h] [rbp+2058h]
  int v1011; // [rsp+2160h] [rbp+2060h]
  __int64 v1012; // [rsp+2168h] [rbp+2068h]
  __int64 v1013; // [rsp+2170h] [rbp+2070h]
  int v1014; // [rsp+2178h] [rbp+2078h]
  __int64 v1015; // [rsp+2180h] [rbp+2080h]
  __int64 v1016; // [rsp+2188h] [rbp+2088h]
  int v1017; // [rsp+2190h] [rbp+2090h]
  __int64 v1018; // [rsp+2198h] [rbp+2098h]
  __int64 v1019; // [rsp+21A0h] [rbp+20A0h]
  int v1020; // [rsp+21A8h] [rbp+20A8h]
  __int64 v1021; // [rsp+21B0h] [rbp+20B0h]
  __int64 v1022; // [rsp+21B8h] [rbp+20B8h]
  int v1023; // [rsp+21C0h] [rbp+20C0h]
  __int64 v1024; // [rsp+21C8h] [rbp+20C8h]
  __int64 v1025; // [rsp+21D0h] [rbp+20D0h]
  int v1026; // [rsp+21D8h] [rbp+20D8h]
  __int64 v1027; // [rsp+21E0h] [rbp+20E0h]
  __int64 v1028; // [rsp+21E8h] [rbp+20E8h]
  int v1029; // [rsp+21F0h] [rbp+20F0h]
  __int16 (__fastcall *v1030)(PrivacySettingsInfo *__hidden); // [rsp+21F8h] [rbp+20F8h]
  __int64 v1031; // [rsp+2200h] [rbp+2100h]
  int v1032; // [rsp+2208h] [rbp+2108h]
  __int64 v1033; // [rsp+2210h] [rbp+2110h]
  __int64 v1034; // [rsp+2218h] [rbp+2118h]
  _BYTE v1035[32]; // [rsp+2220h] [rbp+2120h] BYREF
  int v1036; // [rsp+2240h] [rbp+2140h]
  __int64 v1037; // [rsp+2248h] [rbp+2148h]
  __int128 v1038; // [rsp+2250h] [rbp+2150h]
  const wchar_t *v1039; // [rsp+2260h] [rbp+2160h]
  __int16 v1040; // [rsp+2268h] [rbp+2168h]
  char v1041; // [rsp+226Ah] [rbp+216Ah]
  int v1042; // [rsp+226Bh] [rbp+216Bh]
  char v1043; // [rsp+226Fh] [rbp+216Fh]
  int v1044; // [rsp+2270h] [rbp+2170h]
  __int64 v1045; // [rsp+2278h] [rbp+2178h]
  __int64 v1046; // [rsp+2280h] [rbp+2180h]
  int v1047; // [rsp+2288h] [rbp+2188h]
  __int64 v1048; // [rsp+2290h] [rbp+2190h]
  __int64 v1049; // [rsp+2298h] [rbp+2198h]
  int v1050; // [rsp+22A0h] [rbp+21A0h]
  __int64 v1051; // [rsp+22A8h] [rbp+21A8h]
  __int64 v1052; // [rsp+22B0h] [rbp+21B0h]
  int v1053; // [rsp+22B8h] [rbp+21B8h]
  __int64 v1054; // [rsp+22C0h] [rbp+21C0h]
  __int64 v1055; // [rsp+22C8h] [rbp+21C8h]
  int v1056; // [rsp+22D0h] [rbp+21D0h]
  __int64 v1057; // [rsp+22D8h] [rbp+21D8h]
  __int64 v1058; // [rsp+22E0h] [rbp+21E0h]
  int v1059; // [rsp+22E8h] [rbp+21E8h]
  __int64 v1060; // [rsp+22F0h] [rbp+21F0h]
  __int64 v1061; // [rsp+22F8h] [rbp+21F8h]
  int v1062; // [rsp+2300h] [rbp+2200h]
  __int64 v1063; // [rsp+2308h] [rbp+2208h]
  __int64 v1064; // [rsp+2310h] [rbp+2210h]
  int v1065; // [rsp+2318h] [rbp+2218h]
  __int64 v1066; // [rsp+2320h] [rbp+2220h]
  __int64 v1067; // [rsp+2328h] [rbp+2228h]
  int v1068; // [rsp+2330h] [rbp+2230h]
  __int64 v1069; // [rsp+2338h] [rbp+2238h]
  __int64 v1070; // [rsp+2340h] [rbp+2240h]
  int v1071; // [rsp+2348h] [rbp+2248h]
  __int16 (__fastcall *v1072)(PrivacySettingsInfo *__hidden); // [rsp+2350h] [rbp+2250h]
  __int64 v1073; // [rsp+2358h] [rbp+2258h]
  int v1074; // [rsp+2360h] [rbp+2260h]
  __int64 v1075; // [rsp+2368h] [rbp+2268h]
  __int64 v1076; // [rsp+2370h] [rbp+2270h]
  _BYTE v1077[32]; // [rsp+2378h] [rbp+2278h] BYREF
  int v1078; // [rsp+2398h] [rbp+2298h]
  __int128 v1079; // [rsp+23A0h] [rbp+22A0h]
  __int64 v1080; // [rsp+23B0h] [rbp+22B0h]
  const wchar_t *v1081; // [rsp+23B8h] [rbp+22B8h]
  __int16 v1082; // [rsp+23C0h] [rbp+22C0h]
  char v1083; // [rsp+23C2h] [rbp+22C2h]
  int v1084; // [rsp+23C3h] [rbp+22C3h]
  char v1085; // [rsp+23C7h] [rbp+22C7h]
  int v1086; // [rsp+23C8h] [rbp+22C8h]
  __int64 v1087; // [rsp+23D0h] [rbp+22D0h]
  __int64 v1088; // [rsp+23D8h] [rbp+22D8h]
  int v1089; // [rsp+23E0h] [rbp+22E0h]
  __int64 v1090; // [rsp+23E8h] [rbp+22E8h]
  __int64 v1091; // [rsp+23F0h] [rbp+22F0h]
  int v1092; // [rsp+23F8h] [rbp+22F8h]
  __int64 v1093; // [rsp+2400h] [rbp+2300h]
  __int64 v1094; // [rsp+2408h] [rbp+2308h]
  int v1095; // [rsp+2410h] [rbp+2310h]
  __int64 v1096; // [rsp+2418h] [rbp+2318h]
  __int64 v1097; // [rsp+2420h] [rbp+2320h]
  int v1098; // [rsp+2428h] [rbp+2328h]
  __int64 v1099; // [rsp+2430h] [rbp+2330h]
  __int64 v1100; // [rsp+2438h] [rbp+2338h]
  int v1101; // [rsp+2440h] [rbp+2340h]
  __int64 v1102; // [rsp+2448h] [rbp+2348h]
  __int64 v1103; // [rsp+2450h] [rbp+2350h]
  int v1104; // [rsp+2458h] [rbp+2358h]
  __int64 v1105; // [rsp+2460h] [rbp+2360h]
  __int64 v1106; // [rsp+2468h] [rbp+2368h]
  int v1107; // [rsp+2470h] [rbp+2370h]
  __int64 v1108; // [rsp+2478h] [rbp+2378h]
  __int64 v1109; // [rsp+2480h] [rbp+2380h]
  int v1110; // [rsp+2488h] [rbp+2388h]
  __int64 v1111; // [rsp+2490h] [rbp+2390h]
  __int64 v1112; // [rsp+2498h] [rbp+2398h]
  int v1113; // [rsp+24A0h] [rbp+23A0h]
  __int16 (__fastcall *v1114)(PrivacySettingsInfo *__hidden); // [rsp+24A8h] [rbp+23A8h]
  __int64 v1115; // [rsp+24B0h] [rbp+23B0h]
  int v1116; // [rsp+24B8h] [rbp+23B8h]
  __int64 v1117; // [rsp+24C0h] [rbp+23C0h]
  __int64 v1118; // [rsp+24C8h] [rbp+23C8h]
  _BYTE v1119[32]; // [rsp+24D0h] [rbp+23D0h] BYREF
  int v1120; // [rsp+24F0h] [rbp+23F0h]
  __int64 v1121; // [rsp+24F8h] [rbp+23F8h]
  __int128 v1122; // [rsp+2500h] [rbp+2400h]
  const wchar_t *v1123; // [rsp+2510h] [rbp+2410h]
  __int16 v1124; // [rsp+2518h] [rbp+2418h]
  char v1125; // [rsp+251Ah] [rbp+241Ah]
  int v1126; // [rsp+251Bh] [rbp+241Bh]
  char v1127; // [rsp+251Fh] [rbp+241Fh]
  int v1128; // [rsp+2520h] [rbp+2420h]
  __int64 v1129; // [rsp+2528h] [rbp+2428h]
  __int64 v1130; // [rsp+2530h] [rbp+2430h]
  int v1131; // [rsp+2538h] [rbp+2438h]
  __int64 v1132; // [rsp+2540h] [rbp+2440h]
  __int64 v1133; // [rsp+2548h] [rbp+2448h]
  int v1134; // [rsp+2550h] [rbp+2450h]
  __int64 v1135; // [rsp+2558h] [rbp+2458h]
  __int64 v1136; // [rsp+2560h] [rbp+2460h]
  int v1137; // [rsp+2568h] [rbp+2468h]
  __int64 v1138; // [rsp+2570h] [rbp+2470h]
  __int64 v1139; // [rsp+2578h] [rbp+2478h]
  int v1140; // [rsp+2580h] [rbp+2480h]
  __int64 v1141; // [rsp+2588h] [rbp+2488h]
  __int64 v1142; // [rsp+2590h] [rbp+2490h]
  int v1143; // [rsp+2598h] [rbp+2498h]
  __int64 v1144; // [rsp+25A0h] [rbp+24A0h]
  __int64 v1145; // [rsp+25A8h] [rbp+24A8h]
  int v1146; // [rsp+25B0h] [rbp+24B0h]
  __int64 v1147; // [rsp+25B8h] [rbp+24B8h]
  __int64 v1148; // [rsp+25C0h] [rbp+24C0h]
  int v1149; // [rsp+25C8h] [rbp+24C8h]
  __int64 v1150; // [rsp+25D0h] [rbp+24D0h]
  __int64 v1151; // [rsp+25D8h] [rbp+24D8h]
  int v1152; // [rsp+25E0h] [rbp+24E0h]
  __int64 v1153; // [rsp+25E8h] [rbp+24E8h]
  __int64 v1154; // [rsp+25F0h] [rbp+24F0h]
  int v1155; // [rsp+25F8h] [rbp+24F8h]
  __int16 (__fastcall *v1156)(PrivacySettingsInfo *__hidden); // [rsp+2600h] [rbp+2500h]
  __int64 v1157; // [rsp+2608h] [rbp+2508h]
  int v1158; // [rsp+2610h] [rbp+2510h]
  __int64 v1159; // [rsp+2618h] [rbp+2518h]
  __int64 v1160; // [rsp+2620h] [rbp+2520h]
  _BYTE v1161[32]; // [rsp+2628h] [rbp+2528h] BYREF
  int v1162; // [rsp+2648h] [rbp+2548h]
  __int128 v1163; // [rsp+2650h] [rbp+2550h]
  __int64 v1164; // [rsp+2660h] [rbp+2560h]
  const wchar_t *v1165; // [rsp+2668h] [rbp+2568h]
  __int16 v1166; // [rsp+2670h] [rbp+2570h]
  char v1167; // [rsp+2672h] [rbp+2572h]
  int v1168; // [rsp+2673h] [rbp+2573h]
  char v1169; // [rsp+2677h] [rbp+2577h]
  int v1170; // [rsp+2678h] [rbp+2578h]
  __int64 v1171; // [rsp+2680h] [rbp+2580h]
  __int64 v1172; // [rsp+2688h] [rbp+2588h]
  int v1173; // [rsp+2690h] [rbp+2590h]
  __int64 v1174; // [rsp+2698h] [rbp+2598h]
  __int64 v1175; // [rsp+26A0h] [rbp+25A0h]
  int v1176; // [rsp+26A8h] [rbp+25A8h]
  __int64 v1177; // [rsp+26B0h] [rbp+25B0h]
  __int64 v1178; // [rsp+26B8h] [rbp+25B8h]
  int v1179; // [rsp+26C0h] [rbp+25C0h]
  __int64 v1180; // [rsp+26C8h] [rbp+25C8h]
  __int64 v1181; // [rsp+26D0h] [rbp+25D0h]
  int v1182; // [rsp+26D8h] [rbp+25D8h]
  __int64 v1183; // [rsp+26E0h] [rbp+25E0h]
  __int64 v1184; // [rsp+26E8h] [rbp+25E8h]
  int v1185; // [rsp+26F0h] [rbp+25F0h]
  __int64 v1186; // [rsp+26F8h] [rbp+25F8h]
  __int64 v1187; // [rsp+2700h] [rbp+2600h]
  int v1188; // [rsp+2708h] [rbp+2608h]
  __int64 v1189; // [rsp+2710h] [rbp+2610h]
  __int64 v1190; // [rsp+2718h] [rbp+2618h]
  int v1191; // [rsp+2720h] [rbp+2620h]
  __int64 v1192; // [rsp+2728h] [rbp+2628h]
  __int64 v1193; // [rsp+2730h] [rbp+2630h]
  int v1194; // [rsp+2738h] [rbp+2638h]
  __int64 v1195; // [rsp+2740h] [rbp+2640h]
  __int64 v1196; // [rsp+2748h] [rbp+2648h]
  int v1197; // [rsp+2750h] [rbp+2650h]
  __int16 (__fastcall *v1198)(PrivacySettingsInfo *__hidden); // [rsp+2758h] [rbp+2658h]
  __int64 v1199; // [rsp+2760h] [rbp+2660h]
  int v1200; // [rsp+2768h] [rbp+2668h]
  __int64 v1201; // [rsp+2770h] [rbp+2670h]
  __int64 v1202; // [rsp+2778h] [rbp+2678h]
  _BYTE v1203[32]; // [rsp+2780h] [rbp+2680h] BYREF
  int v1204; // [rsp+27A0h] [rbp+26A0h]
  __int64 v1205; // [rsp+27A8h] [rbp+26A8h]
  __int128 v1206; // [rsp+27B0h] [rbp+26B0h]
  const wchar_t *v1207; // [rsp+27C0h] [rbp+26C0h]
  __int16 v1208; // [rsp+27C8h] [rbp+26C8h]
  char v1209; // [rsp+27CAh] [rbp+26CAh]
  int v1210; // [rsp+27CBh] [rbp+26CBh]
  char v1211; // [rsp+27CFh] [rbp+26CFh]
  int v1212; // [rsp+27D0h] [rbp+26D0h]
  __int64 v1213; // [rsp+27D8h] [rbp+26D8h]
  __int64 v1214; // [rsp+27E0h] [rbp+26E0h]
  int v1215; // [rsp+27E8h] [rbp+26E8h]
  __int64 v1216; // [rsp+27F0h] [rbp+26F0h]
  __int64 v1217; // [rsp+27F8h] [rbp+26F8h]
  int v1218; // [rsp+2800h] [rbp+2700h]
  __int64 v1219; // [rsp+2808h] [rbp+2708h]
  __int64 v1220; // [rsp+2810h] [rbp+2710h]
  int v1221; // [rsp+2818h] [rbp+2718h]
  __int64 v1222; // [rsp+2820h] [rbp+2720h]
  __int64 v1223; // [rsp+2828h] [rbp+2728h]
  int v1224; // [rsp+2830h] [rbp+2730h]
  __int64 v1225; // [rsp+2838h] [rbp+2738h]
  __int64 v1226; // [rsp+2840h] [rbp+2740h]
  int v1227; // [rsp+2848h] [rbp+2748h]
  __int64 v1228; // [rsp+2850h] [rbp+2750h]
  __int64 v1229; // [rsp+2858h] [rbp+2758h]
  int v1230; // [rsp+2860h] [rbp+2760h]
  __int64 v1231; // [rsp+2868h] [rbp+2768h]
  __int64 v1232; // [rsp+2870h] [rbp+2770h]
  int v1233; // [rsp+2878h] [rbp+2778h]
  __int64 v1234; // [rsp+2880h] [rbp+2780h]
  __int64 v1235; // [rsp+2888h] [rbp+2788h]
  int v1236; // [rsp+2890h] [rbp+2790h]
  __int64 v1237; // [rsp+2898h] [rbp+2798h]
  __int64 v1238; // [rsp+28A0h] [rbp+27A0h]
  int v1239; // [rsp+28A8h] [rbp+27A8h]
  __int16 (__fastcall *v1240)(PrivacySettingsInfo *__hidden); // [rsp+28B0h] [rbp+27B0h]
  __int64 v1241; // [rsp+28B8h] [rbp+27B8h]
  int v1242; // [rsp+28C0h] [rbp+27C0h]
  __int64 v1243; // [rsp+28C8h] [rbp+27C8h]
  __int64 v1244; // [rsp+28D0h] [rbp+27D0h]
  _BYTE v1245[32]; // [rsp+28D8h] [rbp+27D8h] BYREF
  int v1246; // [rsp+28F8h] [rbp+27F8h]
  __int128 v1247; // [rsp+2900h] [rbp+2800h]
  __int64 v1248; // [rsp+2910h] [rbp+2810h]
  const wchar_t *v1249; // [rsp+2918h] [rbp+2818h]
  __int16 v1250; // [rsp+2920h] [rbp+2820h]
  char v1251; // [rsp+2922h] [rbp+2822h]
  int v1252; // [rsp+2923h] [rbp+2823h]
  char v1253; // [rsp+2927h] [rbp+2827h]
  int v1254; // [rsp+2928h] [rbp+2828h]
  __int64 v1255; // [rsp+2930h] [rbp+2830h]
  __int64 v1256; // [rsp+2938h] [rbp+2838h]
  int v1257; // [rsp+2940h] [rbp+2840h]
  __int64 v1258; // [rsp+2948h] [rbp+2848h]
  __int64 v1259; // [rsp+2950h] [rbp+2850h]
  int v1260; // [rsp+2958h] [rbp+2858h]
  __int64 v1261; // [rsp+2960h] [rbp+2860h]
  __int64 v1262; // [rsp+2968h] [rbp+2868h]
  int v1263; // [rsp+2970h] [rbp+2870h]
  __int64 v1264; // [rsp+2978h] [rbp+2878h]
  __int64 v1265; // [rsp+2980h] [rbp+2880h]
  int v1266; // [rsp+2988h] [rbp+2888h]
  __int64 v1267; // [rsp+2990h] [rbp+2890h]
  __int64 v1268; // [rsp+2998h] [rbp+2898h]
  int v1269; // [rsp+29A0h] [rbp+28A0h]
  __int64 v1270; // [rsp+29A8h] [rbp+28A8h]
  __int64 v1271; // [rsp+29B0h] [rbp+28B0h]
  int v1272; // [rsp+29B8h] [rbp+28B8h]
  __int64 v1273; // [rsp+29C0h] [rbp+28C0h]
  __int64 v1274; // [rsp+29C8h] [rbp+28C8h]
  int v1275; // [rsp+29D0h] [rbp+28D0h]
  __int64 v1276; // [rsp+29D8h] [rbp+28D8h]
  __int64 v1277; // [rsp+29E0h] [rbp+28E0h]
  int v1278; // [rsp+29E8h] [rbp+28E8h]
  __int64 v1279; // [rsp+29F0h] [rbp+28F0h]
  __int64 v1280; // [rsp+29F8h] [rbp+28F8h]
  int v1281; // [rsp+2A00h] [rbp+2900h]
  __int16 (__fastcall *v1282)(PrivacySettingsInfo *__hidden); // [rsp+2A08h] [rbp+2908h]
  __int64 v1283; // [rsp+2A10h] [rbp+2910h]
  int v1284; // [rsp+2A18h] [rbp+2918h]
  __int64 v1285; // [rsp+2A20h] [rbp+2920h]
  __int64 v1286; // [rsp+2A28h] [rbp+2928h]
  _BYTE v1287[32]; // [rsp+2A30h] [rbp+2930h] BYREF
  int v1288; // [rsp+2A50h] [rbp+2950h]
  __int64 v1289; // [rsp+2A58h] [rbp+2958h]
  __int128 v1290; // [rsp+2A60h] [rbp+2960h]
  const wchar_t *v1291; // [rsp+2A70h] [rbp+2970h]
  __int16 v1292; // [rsp+2A78h] [rbp+2978h]
  char v1293; // [rsp+2A7Ah] [rbp+297Ah]
  int v1294; // [rsp+2A7Bh] [rbp+297Bh]
  char v1295; // [rsp+2A7Fh] [rbp+297Fh]
  int v1296; // [rsp+2A80h] [rbp+2980h]
  __int64 v1297; // [rsp+2A88h] [rbp+2988h]
  __int64 v1298; // [rsp+2A90h] [rbp+2990h]
  int v1299; // [rsp+2A98h] [rbp+2998h]
  __int64 v1300; // [rsp+2AA0h] [rbp+29A0h]
  __int64 v1301; // [rsp+2AA8h] [rbp+29A8h]
  int v1302; // [rsp+2AB0h] [rbp+29B0h]
  __int64 v1303; // [rsp+2AB8h] [rbp+29B8h]
  __int64 v1304; // [rsp+2AC0h] [rbp+29C0h]
  int v1305; // [rsp+2AC8h] [rbp+29C8h]
  __int64 v1306; // [rsp+2AD0h] [rbp+29D0h]
  __int64 v1307; // [rsp+2AD8h] [rbp+29D8h]
  int v1308; // [rsp+2AE0h] [rbp+29E0h]
  __int64 v1309; // [rsp+2AE8h] [rbp+29E8h]
  __int64 v1310; // [rsp+2AF0h] [rbp+29F0h]
  int v1311; // [rsp+2AF8h] [rbp+29F8h]
  __int64 v1312; // [rsp+2B00h] [rbp+2A00h]
  __int64 v1313; // [rsp+2B08h] [rbp+2A08h]
  int v1314; // [rsp+2B10h] [rbp+2A10h]
  __int64 v1315; // [rsp+2B18h] [rbp+2A18h]
  __int64 v1316; // [rsp+2B20h] [rbp+2A20h]
  int v1317; // [rsp+2B28h] [rbp+2A28h]
  __int64 v1318; // [rsp+2B30h] [rbp+2A30h]
  __int64 v1319; // [rsp+2B38h] [rbp+2A38h]
  int v1320; // [rsp+2B40h] [rbp+2A40h]
  __int64 v1321; // [rsp+2B48h] [rbp+2A48h]
  __int64 v1322; // [rsp+2B50h] [rbp+2A50h]
  int v1323; // [rsp+2B58h] [rbp+2A58h]
  __int16 (__fastcall *v1324)(PrivacySettingsInfo *__hidden); // [rsp+2B60h] [rbp+2A60h]
  __int64 v1325; // [rsp+2B68h] [rbp+2A68h]
  int v1326; // [rsp+2B70h] [rbp+2A70h]
  __int64 v1327; // [rsp+2B78h] [rbp+2A78h]
  __int64 v1328; // [rsp+2B80h] [rbp+2A80h]
  _BYTE v1329[32]; // [rsp+2B88h] [rbp+2A88h] BYREF
  int v1330; // [rsp+2BA8h] [rbp+2AA8h]
  __int128 v1331; // [rsp+2BB0h] [rbp+2AB0h]
  __int64 v1332; // [rsp+2BC0h] [rbp+2AC0h]
  const wchar_t *v1333; // [rsp+2BC8h] [rbp+2AC8h]
  __int16 v1334; // [rsp+2BD0h] [rbp+2AD0h]
  char v1335; // [rsp+2BD2h] [rbp+2AD2h]
  int v1336; // [rsp+2BD3h] [rbp+2AD3h]
  char v1337; // [rsp+2BD7h] [rbp+2AD7h]
  int v1338; // [rsp+2BD8h] [rbp+2AD8h]
  __int64 v1339; // [rsp+2BE0h] [rbp+2AE0h]
  __int64 v1340; // [rsp+2BE8h] [rbp+2AE8h]
  int v1341; // [rsp+2BF0h] [rbp+2AF0h]
  __int64 v1342; // [rsp+2BF8h] [rbp+2AF8h]
  __int64 v1343; // [rsp+2C00h] [rbp+2B00h]
  int v1344; // [rsp+2C08h] [rbp+2B08h]
  __int64 v1345; // [rsp+2C10h] [rbp+2B10h]
  __int64 v1346; // [rsp+2C18h] [rbp+2B18h]
  int v1347; // [rsp+2C20h] [rbp+2B20h]
  __int64 v1348; // [rsp+2C28h] [rbp+2B28h]
  __int64 v1349; // [rsp+2C30h] [rbp+2B30h]
  int v1350; // [rsp+2C38h] [rbp+2B38h]
  __int64 v1351; // [rsp+2C40h] [rbp+2B40h]
  __int64 v1352; // [rsp+2C48h] [rbp+2B48h]
  int v1353; // [rsp+2C50h] [rbp+2B50h]
  __int64 v1354; // [rsp+2C58h] [rbp+2B58h]
  __int64 v1355; // [rsp+2C60h] [rbp+2B60h]
  int v1356; // [rsp+2C68h] [rbp+2B68h]
  __int64 v1357; // [rsp+2C70h] [rbp+2B70h]
  __int64 v1358; // [rsp+2C78h] [rbp+2B78h]
  int v1359; // [rsp+2C80h] [rbp+2B80h]
  __int64 v1360; // [rsp+2C88h] [rbp+2B88h]
  __int64 v1361; // [rsp+2C90h] [rbp+2B90h]
  int v1362; // [rsp+2C98h] [rbp+2B98h]
  __int64 v1363; // [rsp+2CA0h] [rbp+2BA0h]
  __int64 v1364; // [rsp+2CA8h] [rbp+2BA8h]
  int v1365; // [rsp+2CB0h] [rbp+2BB0h]
  __int16 (__fastcall *v1366)(PrivacySettingsInfo *__hidden); // [rsp+2CB8h] [rbp+2BB8h]
  __int64 v1367; // [rsp+2CC0h] [rbp+2BC0h]
  int v1368; // [rsp+2CC8h] [rbp+2BC8h]
  __int64 v1369; // [rsp+2CD0h] [rbp+2BD0h]
  __int64 v1370; // [rsp+2CD8h] [rbp+2BD8h]
  _BYTE v1371[32]; // [rsp+2CE0h] [rbp+2BE0h] BYREF
  int v1372; // [rsp+2D00h] [rbp+2C00h]
  __int64 v1373; // [rsp+2D08h] [rbp+2C08h]
  __int128 v1374; // [rsp+2D10h] [rbp+2C10h]
  const wchar_t *v1375; // [rsp+2D20h] [rbp+2C20h]
  __int16 v1376; // [rsp+2D28h] [rbp+2C28h]
  char v1377; // [rsp+2D2Ah] [rbp+2C2Ah]
  int v1378; // [rsp+2D2Bh] [rbp+2C2Bh]
  char v1379; // [rsp+2D2Fh] [rbp+2C2Fh]
  int v1380; // [rsp+2D30h] [rbp+2C30h]
  __int64 v1381; // [rsp+2D38h] [rbp+2C38h]
  __int64 v1382; // [rsp+2D40h] [rbp+2C40h]
  int v1383; // [rsp+2D48h] [rbp+2C48h]
  __int64 v1384; // [rsp+2D50h] [rbp+2C50h]
  __int64 v1385; // [rsp+2D58h] [rbp+2C58h]
  int v1386; // [rsp+2D60h] [rbp+2C60h]
  __int64 v1387; // [rsp+2D68h] [rbp+2C68h]
  __int64 v1388; // [rsp+2D70h] [rbp+2C70h]
  int v1389; // [rsp+2D78h] [rbp+2C78h]
  __int64 v1390; // [rsp+2D80h] [rbp+2C80h]
  __int64 v1391; // [rsp+2D88h] [rbp+2C88h]
  int v1392; // [rsp+2D90h] [rbp+2C90h]
  __int64 v1393; // [rsp+2D98h] [rbp+2C98h]
  __int64 v1394; // [rsp+2DA0h] [rbp+2CA0h]
  int v1395; // [rsp+2DA8h] [rbp+2CA8h]
  __int64 v1396; // [rsp+2DB0h] [rbp+2CB0h]
  __int64 v1397; // [rsp+2DB8h] [rbp+2CB8h]
  int v1398; // [rsp+2DC0h] [rbp+2CC0h]
  __int64 v1399; // [rsp+2DC8h] [rbp+2CC8h]
  __int64 v1400; // [rsp+2DD0h] [rbp+2CD0h]
  int v1401; // [rsp+2DD8h] [rbp+2CD8h]
  __int64 v1402; // [rsp+2DE0h] [rbp+2CE0h]
  __int64 v1403; // [rsp+2DE8h] [rbp+2CE8h]
  int v1404; // [rsp+2DF0h] [rbp+2CF0h]
  __int64 v1405; // [rsp+2DF8h] [rbp+2CF8h]
  __int64 v1406; // [rsp+2E00h] [rbp+2D00h]
  int v1407; // [rsp+2E08h] [rbp+2D08h]
  __int16 (__fastcall *v1408)(PrivacySettingsInfo *__hidden); // [rsp+2E10h] [rbp+2D10h]
  __int64 v1409; // [rsp+2E18h] [rbp+2D18h]
  int v1410; // [rsp+2E20h] [rbp+2D20h]
  __int64 v1411; // [rsp+2E28h] [rbp+2D28h]
  __int64 v1412; // [rsp+2E30h] [rbp+2D30h]
  _BYTE v1413[32]; // [rsp+2E38h] [rbp+2D38h] BYREF
  int v1414; // [rsp+2E58h] [rbp+2D58h]
  __int128 v1415; // [rsp+2E60h] [rbp+2D60h]
  __int64 v1416; // [rsp+2E70h] [rbp+2D70h]
  const wchar_t *v1417; // [rsp+2E78h] [rbp+2D78h]
  __int16 v1418; // [rsp+2E80h] [rbp+2D80h]
  char v1419; // [rsp+2E82h] [rbp+2D82h]
  int v1420; // [rsp+2E83h] [rbp+2D83h]
  char v1421; // [rsp+2E87h] [rbp+2D87h]
  int v1422; // [rsp+2E88h] [rbp+2D88h]
  __int64 v1423; // [rsp+2E90h] [rbp+2D90h]
  __int64 v1424; // [rsp+2E98h] [rbp+2D98h]
  int v1425; // [rsp+2EA0h] [rbp+2DA0h]
  __int64 v1426; // [rsp+2EA8h] [rbp+2DA8h]
  __int64 v1427; // [rsp+2EB0h] [rbp+2DB0h]
  int v1428; // [rsp+2EB8h] [rbp+2DB8h]
  __int64 v1429; // [rsp+2EC0h] [rbp+2DC0h]
  __int64 v1430; // [rsp+2EC8h] [rbp+2DC8h]
  int v1431; // [rsp+2ED0h] [rbp+2DD0h]
  __int64 v1432; // [rsp+2ED8h] [rbp+2DD8h]
  __int64 v1433; // [rsp+2EE0h] [rbp+2DE0h]
  int v1434; // [rsp+2EE8h] [rbp+2DE8h]
  __int64 v1435; // [rsp+2EF0h] [rbp+2DF0h]
  __int64 v1436; // [rsp+2EF8h] [rbp+2DF8h]
  int v1437; // [rsp+2F00h] [rbp+2E00h]
  __int64 v1438; // [rsp+2F08h] [rbp+2E08h]
  __int64 v1439; // [rsp+2F10h] [rbp+2E10h]
  int v1440; // [rsp+2F18h] [rbp+2E18h]
  __int64 v1441; // [rsp+2F20h] [rbp+2E20h]
  __int64 v1442; // [rsp+2F28h] [rbp+2E28h]
  int v1443; // [rsp+2F30h] [rbp+2E30h]
  __int64 v1444; // [rsp+2F38h] [rbp+2E38h]
  __int64 v1445; // [rsp+2F40h] [rbp+2E40h]
  int v1446; // [rsp+2F48h] [rbp+2E48h]
  __int64 v1447; // [rsp+2F50h] [rbp+2E50h]
  __int64 v1448; // [rsp+2F58h] [rbp+2E58h]
  int v1449; // [rsp+2F60h] [rbp+2E60h]
  __int16 (__fastcall *v1450)(CPrivacySettingsInfo *__hidden); // [rsp+2F68h] [rbp+2E68h]
  __int64 v1451; // [rsp+2F70h] [rbp+2E70h]
  int v1452; // [rsp+2F78h] [rbp+2E78h]
  __int64 v1453; // [rsp+2F80h] [rbp+2E80h]
  __int64 v1454; // [rsp+2F88h] [rbp+2E88h]
  _BYTE v1455[32]; // [rsp+2F90h] [rbp+2E90h] BYREF
  int v1456; // [rsp+2FB0h] [rbp+2EB0h]
  __int64 v1457; // [rsp+2FB8h] [rbp+2EB8h]
  __int128 v1458; // [rsp+2FC0h] [rbp+2EC0h]
  const wchar_t *v1459; // [rsp+2FD0h] [rbp+2ED0h]
  __int16 v1460; // [rsp+2FD8h] [rbp+2ED8h]
  char v1461; // [rsp+2FDAh] [rbp+2EDAh]
  int v1462; // [rsp+2FDBh] [rbp+2EDBh]
  char v1463; // [rsp+2FDFh] [rbp+2EDFh]
  int v1464; // [rsp+2FE0h] [rbp+2EE0h]
  __int64 v1465; // [rsp+2FE8h] [rbp+2EE8h]
  __int64 v1466; // [rsp+2FF0h] [rbp+2EF0h]
  int v1467; // [rsp+2FF8h] [rbp+2EF8h]
  __int64 v1468; // [rsp+3000h] [rbp+2F00h]
  __int64 v1469; // [rsp+3008h] [rbp+2F08h]
  int v1470; // [rsp+3010h] [rbp+2F10h]
  __int64 v1471; // [rsp+3018h] [rbp+2F18h]
  __int64 v1472; // [rsp+3020h] [rbp+2F20h]
  int v1473; // [rsp+3028h] [rbp+2F28h]
  __int64 v1474; // [rsp+3030h] [rbp+2F30h]
  __int64 v1475; // [rsp+3038h] [rbp+2F38h]
  int v1476; // [rsp+3040h] [rbp+2F40h]
  __int64 v1477; // [rsp+3048h] [rbp+2F48h]
  __int64 v1478; // [rsp+3050h] [rbp+2F50h]
  int v1479; // [rsp+3058h] [rbp+2F58h]
  __int64 v1480; // [rsp+3060h] [rbp+2F60h]
  __int64 v1481; // [rsp+3068h] [rbp+2F68h]
  int v1482; // [rsp+3070h] [rbp+2F70h]
  __int64 v1483; // [rsp+3078h] [rbp+2F78h]
  __int64 v1484; // [rsp+3080h] [rbp+2F80h]
  int v1485; // [rsp+3088h] [rbp+2F88h]
  __int64 v1486; // [rsp+3090h] [rbp+2F90h]
  __int64 v1487; // [rsp+3098h] [rbp+2F98h]
  int v1488; // [rsp+30A0h] [rbp+2FA0h]
  __int64 v1489; // [rsp+30A8h] [rbp+2FA8h]
  __int64 v1490; // [rsp+30B0h] [rbp+2FB0h]
  int v1491; // [rsp+30B8h] [rbp+2FB8h]
  __int16 (__fastcall *v1492)(CPrivacySettingsInfo *__hidden); // [rsp+30C0h] [rbp+2FC0h]
  __int64 v1493; // [rsp+30C8h] [rbp+2FC8h]
  int v1494; // [rsp+30D0h] [rbp+2FD0h]
  __int64 v1495; // [rsp+30D8h] [rbp+2FD8h]
  __int64 v1496; // [rsp+30E0h] [rbp+2FE0h]
  _BYTE v1497[32]; // [rsp+30E8h] [rbp+2FE8h] BYREF
  int v1498; // [rsp+3108h] [rbp+3008h]
  __int128 v1499; // [rsp+3110h] [rbp+3010h]
  __int64 v1500; // [rsp+3120h] [rbp+3020h]
  const wchar_t *v1501; // [rsp+3128h] [rbp+3028h]
  __int16 v1502; // [rsp+3130h] [rbp+3030h]
  char v1503; // [rsp+3132h] [rbp+3032h]
  int v1504; // [rsp+3133h] [rbp+3033h]
  char v1505; // [rsp+3137h] [rbp+3037h]
  int v1506; // [rsp+3138h] [rbp+3038h]
  __int64 v1507; // [rsp+3140h] [rbp+3040h]
  __int64 v1508; // [rsp+3148h] [rbp+3048h]
  int v1509; // [rsp+3150h] [rbp+3050h]
  __int64 v1510; // [rsp+3158h] [rbp+3058h]
  __int64 v1511; // [rsp+3160h] [rbp+3060h]
  int v1512; // [rsp+3168h] [rbp+3068h]
  __int64 v1513; // [rsp+3170h] [rbp+3070h]
  __int64 v1514; // [rsp+3178h] [rbp+3078h]
  int v1515; // [rsp+3180h] [rbp+3080h]
  __int64 v1516; // [rsp+3188h] [rbp+3088h]
  __int64 v1517; // [rsp+3190h] [rbp+3090h]
  int v1518; // [rsp+3198h] [rbp+3098h]
  __int64 v1519; // [rsp+31A0h] [rbp+30A0h]
  __int64 v1520; // [rsp+31A8h] [rbp+30A8h]
  int v1521; // [rsp+31B0h] [rbp+30B0h]
  __int64 v1522; // [rsp+31B8h] [rbp+30B8h]
  __int64 v1523; // [rsp+31C0h] [rbp+30C0h]
  int v1524; // [rsp+31C8h] [rbp+30C8h]
  __int64 v1525; // [rsp+31D0h] [rbp+30D0h]
  __int64 v1526; // [rsp+31D8h] [rbp+30D8h]
  int v1527; // [rsp+31E0h] [rbp+30E0h]
  __int64 v1528; // [rsp+31E8h] [rbp+30E8h]
  __int64 v1529; // [rsp+31F0h] [rbp+30F0h]
  int v1530; // [rsp+31F8h] [rbp+30F8h]
  __int64 v1531; // [rsp+3200h] [rbp+3100h]
  __int64 v1532; // [rsp+3208h] [rbp+3108h]
  int v1533; // [rsp+3210h] [rbp+3110h]
  __int16 (__fastcall *v1534)(UserPrivacySettingsInfo *__hidden); // [rsp+3218h] [rbp+3118h]
  __int64 v1535; // [rsp+3220h] [rbp+3120h]
  int v1536; // [rsp+3228h] [rbp+3128h]
  __int64 v1537; // [rsp+3230h] [rbp+3130h]
  __int64 v1538; // [rsp+3238h] [rbp+3138h]
  _BYTE v1539[32]; // [rsp+3240h] [rbp+3140h] BYREF
  int v1540; // [rsp+3260h] [rbp+3160h]
  __int64 v1541; // [rsp+3268h] [rbp+3168h]
  __int128 v1542; // [rsp+3270h] [rbp+3170h]
  const wchar_t *v1543; // [rsp+3280h] [rbp+3180h]
  __int16 v1544; // [rsp+3288h] [rbp+3188h]
  char v1545; // [rsp+328Ah] [rbp+318Ah]
  int v1546; // [rsp+328Bh] [rbp+318Bh]
  char v1547; // [rsp+328Fh] [rbp+318Fh]
  int v1548; // [rsp+3290h] [rbp+3190h]
  __int64 v1549; // [rsp+3298h] [rbp+3198h]
  __int64 v1550; // [rsp+32A0h] [rbp+31A0h]
  int v1551; // [rsp+32A8h] [rbp+31A8h]
  __int64 v1552; // [rsp+32B0h] [rbp+31B0h]
  __int64 v1553; // [rsp+32B8h] [rbp+31B8h]
  int v1554; // [rsp+32C0h] [rbp+31C0h]
  __int64 v1555; // [rsp+32C8h] [rbp+31C8h]
  __int64 v1556; // [rsp+32D0h] [rbp+31D0h]
  int v1557; // [rsp+32D8h] [rbp+31D8h]
  __int64 v1558; // [rsp+32E0h] [rbp+31E0h]
  __int64 v1559; // [rsp+32E8h] [rbp+31E8h]
  int v1560; // [rsp+32F0h] [rbp+31F0h]
  __int64 v1561; // [rsp+32F8h] [rbp+31F8h]
  __int64 v1562; // [rsp+3300h] [rbp+3200h]
  int v1563; // [rsp+3308h] [rbp+3208h]
  __int64 v1564; // [rsp+3310h] [rbp+3210h]
  __int64 v1565; // [rsp+3318h] [rbp+3218h]
  int v1566; // [rsp+3320h] [rbp+3220h]
  __int64 v1567; // [rsp+3328h] [rbp+3228h]
  __int64 v1568; // [rsp+3330h] [rbp+3230h]
  int v1569; // [rsp+3338h] [rbp+3238h]
  __int64 v1570; // [rsp+3340h] [rbp+3240h]
  __int64 v1571; // [rsp+3348h] [rbp+3248h]
  int v1572; // [rsp+3350h] [rbp+3250h]
  __int64 v1573; // [rsp+3358h] [rbp+3258h]
  __int64 v1574; // [rsp+3360h] [rbp+3260h]
  int v1575; // [rsp+3368h] [rbp+3268h]
  __int16 (__fastcall *v1576)(PrivacySettingsInfo *__hidden); // [rsp+3370h] [rbp+3270h]
  __int64 v1577; // [rsp+3378h] [rbp+3278h]
  int v1578; // [rsp+3380h] [rbp+3280h]
  __int64 v1579; // [rsp+3388h] [rbp+3288h]
  __int64 v1580; // [rsp+3390h] [rbp+3290h]
  _BYTE v1581[32]; // [rsp+3398h] [rbp+3298h] BYREF
  int v1582; // [rsp+33B8h] [rbp+32B8h]
  __int128 v1583; // [rsp+33C0h] [rbp+32C0h]
  __int64 v1584; // [rsp+33D0h] [rbp+32D0h]
  const wchar_t *v1585; // [rsp+33D8h] [rbp+32D8h]
  __int16 v1586; // [rsp+33E0h] [rbp+32E0h]
  char v1587; // [rsp+33E2h] [rbp+32E2h]
  int v1588; // [rsp+33E3h] [rbp+32E3h]
  char v1589; // [rsp+33E7h] [rbp+32E7h]
  int v1590; // [rsp+33E8h] [rbp+32E8h]
  __int64 v1591; // [rsp+33F0h] [rbp+32F0h]
  __int64 v1592; // [rsp+33F8h] [rbp+32F8h]
  int v1593; // [rsp+3400h] [rbp+3300h]
  __int64 v1594; // [rsp+3408h] [rbp+3308h]
  __int64 v1595; // [rsp+3410h] [rbp+3310h]
  int v1596; // [rsp+3418h] [rbp+3318h]
  __int64 v1597; // [rsp+3420h] [rbp+3320h]
  __int64 v1598; // [rsp+3428h] [rbp+3328h]
  int v1599; // [rsp+3430h] [rbp+3330h]
  __int64 v1600; // [rsp+3438h] [rbp+3338h]
  __int64 v1601; // [rsp+3440h] [rbp+3340h]
  int v1602; // [rsp+3448h] [rbp+3348h]
  __int64 v1603; // [rsp+3450h] [rbp+3350h]
  __int64 v1604; // [rsp+3458h] [rbp+3358h]
  int v1605; // [rsp+3460h] [rbp+3360h]
  __int64 v1606; // [rsp+3468h] [rbp+3368h]
  __int64 v1607; // [rsp+3470h] [rbp+3370h]
  int v1608; // [rsp+3478h] [rbp+3378h]
  __int64 v1609; // [rsp+3480h] [rbp+3380h]
  __int64 v1610; // [rsp+3488h] [rbp+3388h]
  int v1611; // [rsp+3490h] [rbp+3390h]
  __int64 v1612; // [rsp+3498h] [rbp+3398h]
  __int64 v1613; // [rsp+34A0h] [rbp+33A0h]
  int v1614; // [rsp+34A8h] [rbp+33A8h]
  __int64 v1615; // [rsp+34B0h] [rbp+33B0h]
  __int64 v1616; // [rsp+34B8h] [rbp+33B8h]
  int v1617; // [rsp+34C0h] [rbp+33C0h]
  __int16 (__fastcall *v1618)(PrivacySettingsInfo *__hidden); // [rsp+34C8h] [rbp+33C8h]
  __int64 v1619; // [rsp+34D0h] [rbp+33D0h]
  int v1620; // [rsp+34D8h] [rbp+33D8h]
  __int64 v1621; // [rsp+34E0h] [rbp+33E0h]
  __int64 v1622; // [rsp+34E8h] [rbp+33E8h]
  _BYTE v1623[32]; // [rsp+34F0h] [rbp+33F0h] BYREF
  int v1624; // [rsp+3510h] [rbp+3410h]
  __int64 v1625; // [rsp+3518h] [rbp+3418h]
  __int128 v1626; // [rsp+3520h] [rbp+3420h]
  const wchar_t *v1627; // [rsp+3530h] [rbp+3430h]
  __int16 v1628; // [rsp+3538h] [rbp+3438h]
  char v1629; // [rsp+353Ah] [rbp+343Ah]
  int v1630; // [rsp+353Bh] [rbp+343Bh]
  char v1631; // [rsp+353Fh] [rbp+343Fh]
  int v1632; // [rsp+3540h] [rbp+3440h]
  __int64 v1633; // [rsp+3548h] [rbp+3448h]
  __int64 v1634; // [rsp+3550h] [rbp+3450h]
  int v1635; // [rsp+3558h] [rbp+3458h]
  __int64 v1636; // [rsp+3560h] [rbp+3460h]
  __int64 v1637; // [rsp+3568h] [rbp+3468h]
  int v1638; // [rsp+3570h] [rbp+3470h]
  __int64 v1639; // [rsp+3578h] [rbp+3478h]
  __int64 v1640; // [rsp+3580h] [rbp+3480h]
  int v1641; // [rsp+3588h] [rbp+3488h]
  __int64 v1642; // [rsp+3590h] [rbp+3490h]
  __int64 v1643; // [rsp+3598h] [rbp+3498h]
  int v1644; // [rsp+35A0h] [rbp+34A0h]
  __int64 v1645; // [rsp+35A8h] [rbp+34A8h]
  __int64 v1646; // [rsp+35B0h] [rbp+34B0h]
  int v1647; // [rsp+35B8h] [rbp+34B8h]
  __int64 v1648; // [rsp+35C0h] [rbp+34C0h]
  __int64 v1649; // [rsp+35C8h] [rbp+34C8h]
  int v1650; // [rsp+35D0h] [rbp+34D0h]
  __int64 v1651; // [rsp+35D8h] [rbp+34D8h]
  __int64 v1652; // [rsp+35E0h] [rbp+34E0h]
  int v1653; // [rsp+35E8h] [rbp+34E8h]
  __int64 v1654; // [rsp+35F0h] [rbp+34F0h]
  __int64 v1655; // [rsp+35F8h] [rbp+34F8h]
  int v1656; // [rsp+3600h] [rbp+3500h]
  __int64 v1657; // [rsp+3608h] [rbp+3508h]
  __int64 v1658; // [rsp+3610h] [rbp+3510h]
  int v1659; // [rsp+3618h] [rbp+3518h]
  __int16 (__fastcall *v1660)(UserPrivacySettingsInfo *__hidden); // [rsp+3620h] [rbp+3520h]
  __int64 v1661; // [rsp+3628h] [rbp+3528h]
  int v1662; // [rsp+3630h] [rbp+3530h]
  __int64 v1663; // [rsp+3638h] [rbp+3538h]
  __int64 v1664; // [rsp+3640h] [rbp+3540h]
  _BYTE v1665[32]; // [rsp+3648h] [rbp+3548h] BYREF
  int v1666; // [rsp+3668h] [rbp+3568h]
  __int128 v1667; // [rsp+3670h] [rbp+3570h]
  __int64 v1668; // [rsp+3680h] [rbp+3580h]

  v114 = a1;
  *a1 = 0;
  a1[1] = 0;
  a1[2] = 0;
  v115 = L"SystemPrivacySettingActivity";
  v116 = 0;
  v117 = 2;
  v118 = 0;
  v119 = 0;
  v120 = -1;
  v121 = 0;
  v122 = 0;
  v123 = -1;
  v124 = 0;
  v125 = 0;
  v126 = -1;
  v127 = 0;
  v128 = 0;
  v129 = -1;
  v130 = 0;
  v131 = 0;
  v132 = -1;
  v133 = 0;
  v134 = 0;
  v135 = -1;
  v136 = 0;
  v137 = 0;
  v138 = -1;
  v139 = 0;
  v140 = 0;
  v141 = -1;
  v142 = 0;
  v143 = 0;
  v144 = -1;
  v145 = 0;
  v146 = 0;
  v147 = 0;
  v148 = PrivacySettingsInfo::GetSystemPrivacySettingActivity;
  v149 = 0;
  v150 = -1;
  v151 = 0;
  v152 = 0;
  v3 = 2;
  v4 = 0;
  v5 = 0;
  SystemRequirementsExpr::Not(&v3, v153);
  v154 = 0;
  v155 = 0;
  v156 = 0;
  v157 = L"SystemPrivacySettingAppDiagnostics";
  v158 = 0;
  v159 = 2;
  v160 = 0;
  v161 = 0;
  v162 = -1;
  v163 = 0;
  v164 = 0;
  v165 = -1;
  v166 = 0;
  v167 = 0;
  v168 = -1;
  v169 = 0;
  v170 = 0;
  v171 = -1;
  v172 = 0;
  v173 = 0;
  v174 = -1;
  v175 = 0;
  v176 = 0;
  v177 = -1;
  v178 = 0;
  v179 = 0;
  v180 = -1;
  v181 = 0;
  v182 = 0;
  v183 = -1;
  v184 = 0;
  v185 = 0;
  v186 = -1;
  v187 = 0;
  v188 = 0;
  v189 = 2;
  v190 = PrivacySettingsInfo::GetSystemPrivacySettingAppDiagnostics;
  v191 = 0;
  v192 = -1;
  v193 = 0;
  v194 = 0;
  v111 = 2;
  v112 = 0;
  v113 = 0;
  SystemRequirementsExpr::Not(&v111, v195);
  v196 = 0;
  v197 = 0;
  v198 = 0;
  v199 = L"SystemPrivacySettingAppointments";
  v200 = 0;
  v201 = 2;
  v202 = 0;
  v203 = 0;
  v204 = -1;
  v205 = 0;
  v206 = 0;
  v207 = -1;
  v208 = 0;
  v209 = 0;
  v210 = -1;
  v211 = 0;
  v212 = 0;
  v213 = -1;
  v214 = 0;
  v215 = 0;
  v216 = -1;
  v217 = 0;
  v218 = 0;
  v219 = -1;
  v220 = 0;
  v221 = 0;
  v222 = -1;
  v223 = 0;
  v224 = 0;
  v225 = -1;
  v226 = 0;
  v227 = 0;
  v228 = -1;
  v229 = 0;
  v230 = 0;
  v231 = 4;
  v232 = PrivacySettingsInfo::GetSystemPrivacySettingAppointments;
  v233 = 0;
  v234 = -1;
  v235 = 0;
  v236 = 0;
  v108 = 2;
  v109 = 0;
  v110 = 0;
  SystemRequirementsExpr::Not(&v108, v237);
  v238 = 0;
  v239 = 0;
  v240 = 0;
  v241 = L"SystemPrivacySettingBluetooth";
  v242 = 0;
  v243 = 2;
  v244 = 0;
  v245 = 0;
  v246 = -1;
  v247 = 0;
  v248 = 0;
  v249 = -1;
  v250 = 0;
  v251 = 0;
  v252 = -1;
  v253 = 0;
  v254 = 0;
  v255 = -1;
  v256 = 0;
  v257 = 0;
  v258 = -1;
  v259 = 0;
  v260 = 0;
  v261 = -1;
  v262 = 0;
  v263 = 0;
  v264 = -1;
  v265 = 0;
  v266 = 0;
  v267 = -1;
  v268 = 0;
  v269 = 0;
  v270 = -1;
  v271 = 0;
  v272 = 0;
  v273 = 6;
  v274 = PrivacySettingsInfo::GetSystemPrivacySettingBluetooth;
  v275 = 0;
  v276 = -1;
  v277 = 0;
  v278 = 0;
  v105 = 2;
  v106 = 0;
  v107 = 0;
  SystemRequirementsExpr::Not(&v105, v279);
  v280 = 0;
  v281 = 0;
  v282 = 0;
  v283 = L"SystemPrivacySettingBluetoothSync";
  v284 = 0;
  v285 = 2;
  v286 = 0;
  v287 = 0;
  v288 = -1;
  v289 = 0;
  v290 = 0;
  v291 = -1;
  v292 = 0;
  v293 = 0;
  v294 = -1;
  v295 = 0;
  v296 = 0;
  v297 = -1;
  v298 = 0;
  v299 = 0;
  v300 = -1;
  v301 = 0;
  v302 = 0;
  v303 = -1;
  v304 = 0;
  v305 = 0;
  v306 = -1;
  v307 = 0;
  v308 = 0;
  v309 = -1;
  v310 = 0;
  v311 = 0;
  v312 = -1;
  v313 = 0;
  v314 = 0;
  v315 = 8;
  v316 = PrivacySettingsInfo::GetSystemPrivacySettingBluetoothSync;
  v317 = 0;
  v318 = -1;
  v319 = 0;
  v320 = 0;
  v102 = 2;
  v103 = 0;
  v104 = 0;
  SystemRequirementsExpr::Not(&v102, v321);
  v322 = 0;
  v323 = 0;
  v324 = 0;
  v325 = L"SystemPrivacySettingBroadFileSystemAccess";
  v326 = 0;
  v327 = 2;
  v328 = 0;
  v329 = 0;
  v330 = -1;
  v331 = 0;
  v332 = 0;
  v333 = -1;
  v334 = 0;
  v335 = 0;
  v336 = -1;
  v337 = 0;
  v338 = 0;
  v339 = -1;
  v340 = 0;
  v341 = 0;
  v342 = -1;
  v343 = 0;
  v344 = 0;
  v345 = -1;
  v346 = 0;
  v347 = 0;
  v348 = -1;
  v349 = 0;
  v350 = 0;
  v351 = -1;
  v352 = 0;
  v353 = 0;
  v354 = -1;
  v355 = 0;
  v356 = 0;
  v357 = 10;
  v358 = PrivacySettingsInfo::GetSystemPrivacySettingBroadFileSystemAccess;
  v359 = 0;
  v360 = -1;
  v361 = 0;
  v362 = 0;
  v99 = 2;
  v100 = 0;
  v101 = 0;
  SystemRequirementsExpr::Not(&v99, v363);
  v364 = 0;
  v365 = 0;
  v366 = 0;
  v367 = L"SystemPrivacySettingCellularData";
  v368 = 0;
  v369 = 2;
  v370 = 0;
  v371 = 0;
  v372 = -1;
  v373 = 0;
  v374 = 0;
  v375 = -1;
  v376 = 0;
  v377 = 0;
  v378 = -1;
  v379 = 0;
  v380 = 0;
  v381 = -1;
  v382 = 0;
  v383 = 0;
  v384 = -1;
  v385 = 0;
  v386 = 0;
  v387 = -1;
  v388 = 0;
  v389 = 0;
  v390 = -1;
  v391 = 0;
  v392 = 0;
  v393 = -1;
  v394 = 0;
  v395 = 0;
  v396 = -1;
  v397 = 0;
  v398 = 0;
  v399 = 12;
  v400 = PrivacySettingsInfo::GetSystemPrivacySettingCellularData;
  v401 = 0;
  v402 = -1;
  v403 = 0;
  v404 = 0;
  v96 = 2;
  v97 = 0;
  v98 = 0;
  SystemRequirementsExpr::Not(&v96, v405);
  v406 = 0;
  v407 = 0;
  v408 = 0;
  v409 = L"SystemPrivacySettingChat";
  v410 = 0;
  v411 = 2;
  v412 = 0;
  v413 = 0;
  v414 = -1;
  v415 = 0;
  v416 = 0;
  v417 = -1;
  v418 = 0;
  v419 = 0;
  v420 = -1;
  v421 = 0;
  v422 = 0;
  v423 = -1;
  v424 = 0;
  v425 = 0;
  v426 = -1;
  v427 = 0;
  v428 = 0;
  v429 = -1;
  v430 = 0;
  v431 = 0;
  v432 = -1;
  v433 = 0;
  v434 = 0;
  v435 = -1;
  v436 = 0;
  v437 = 0;
  v438 = -1;
  v439 = 0;
  v440 = 0;
  v441 = 14;
  v442 = PrivacySettingsInfo::GetSystemPrivacySettingChat;
  v443 = 0;
  v444 = -1;
  v445 = 0;
  v446 = 0;
  v93 = 2;
  v94 = 0;
  v95 = 0;
  SystemRequirementsExpr::Not(&v93, v447);
  v448 = 0;
  v449 = 0;
  v450 = 0;
  v451 = L"SystemPrivacySettingContacts";
  v452 = 0;
  v453 = 2;
  v454 = 0;
  v455 = 0;
  v456 = -1;
  v457 = 0;
  v458 = 0;
  v459 = -1;
  v460 = 0;
  v461 = 0;
  v462 = -1;
  v463 = 0;
  v464 = 0;
  v465 = -1;
  v466 = 0;
  v467 = 0;
  v468 = -1;
  v469 = 0;
  v470 = 0;
  v471 = -1;
  v472 = 0;
  v473 = 0;
  v474 = -1;
  v475 = 0;
  v476 = 0;
  v477 = -1;
  v478 = 0;
  v479 = 0;
  v480 = -1;
  v481 = 0;
  v482 = 0;
  v483 = 16;
  v484 = PrivacySettingsInfo::GetSystemPrivacySettingContacts;
  v485 = 0;
  v486 = -1;
  v487 = 0;
  v488 = 0;
  v90 = 2;
  v91 = 0;
  v92 = 0;
  SystemRequirementsExpr::Not(&v90, v489);
  v490 = 0;
  v491 = 0;
  v492 = 0;
  v493 = L"SystemPrivacySettingDocumentsLibrary";
  v494 = 0;
  v495 = 2;
  v496 = 0;
  v497 = 0;
  v498 = -1;
  v499 = 0;
  v500 = 0;
  v501 = -1;
  v502 = 0;
  v503 = 0;
  v504 = -1;
  v505 = 0;
  v506 = 0;
  v507 = -1;
  v508 = 0;
  v509 = 0;
  v510 = -1;
  v511 = 0;
  v512 = 0;
  v513 = -1;
  v514 = 0;
  v515 = 0;
  v516 = -1;
  v517 = 0;
  v518 = 0;
  v519 = -1;
  v520 = 0;
  v521 = 0;
  v522 = -1;
  v523 = 0;
  v524 = 0;
  v525 = 18;
  v526 = PrivacySettingsInfo::GetSystemPrivacySettingDocumentsLibrary;
  v527 = 0;
  v528 = -1;
  v529 = 0;
  v530 = 0;
  v87 = 2;
  v88 = 0;
  v89 = 0;
  SystemRequirementsExpr::Not(&v87, v531);
  v532 = 0;
  v533 = 0;
  v534 = 0;
  v535 = L"SystemPrivacySettingEmail";
  v536 = 0;
  v537 = 2;
  v538 = 0;
  v539 = 0;
  v540 = -1;
  v541 = 0;
  v542 = 0;
  v543 = -1;
  v544 = 0;
  v545 = 0;
  v546 = -1;
  v547 = 0;
  v548 = 0;
  v549 = -1;
  v550 = 0;
  v551 = 0;
  v552 = -1;
  v553 = 0;
  v554 = 0;
  v555 = -1;
  v556 = 0;
  v557 = 0;
  v558 = -1;
  v559 = 0;
  v560 = 0;
  v561 = -1;
  v562 = 0;
  v563 = 0;
  v564 = -1;
  v565 = 0;
  v566 = 0;
  v567 = 20;
  v568 = PrivacySettingsInfo::GetSystemPrivacySettingEmail;
  v569 = 0;
  v570 = -1;
  v571 = 0;
  v572 = 0;
  v84 = 2;
  v85 = 0;
  v86 = 0;
  SystemRequirementsExpr::Not(&v84, v573);
  v574 = 0;
  v575 = 0;
  v576 = 0;
  v577 = L"SystemPrivacySettingGazeInput";
  v578 = 0;
  v579 = 2;
  v580 = 0;
  v581 = 0;
  v582 = -1;
  v583 = 0;
  v584 = 0;
  v585 = -1;
  v586 = 0;
  v587 = 0;
  v588 = -1;
  v589 = 0;
  v590 = 0;
  v591 = -1;
  v592 = 0;
  v593 = 0;
  v594 = -1;
  v595 = 0;
  v596 = 0;
  v597 = -1;
  v598 = 0;
  v599 = 0;
  v600 = -1;
  v601 = 0;
  v602 = 0;
  v603 = -1;
  v604 = 0;
  v605 = 0;
  v606 = -1;
  v607 = 0;
  v608 = 0;
  v609 = 22;
  v610 = PrivacySettingsInfo::GetSystemPrivacySettingGazeInput;
  v611 = 0;
  v612 = -1;
  v613 = 0;
  v614 = 0;
  v81 = 2;
  v82 = 0;
  v83 = 0;
  SystemRequirementsExpr::Not(&v81, v615);
  v616 = 0;
  v617 = 0;
  v618 = 0;
  v619 = L"SystemPrivacySettingHumanInterfaceDevice";
  v620 = 0;
  v621 = 2;
  v622 = 0;
  v623 = 0;
  v624 = -1;
  v625 = 0;
  v626 = 0;
  v627 = -1;
  v628 = 0;
  v629 = 0;
  v630 = -1;
  v631 = 0;
  v632 = 0;
  v633 = -1;
  v634 = 0;
  v635 = 0;
  v636 = -1;
  v637 = 0;
  v638 = 0;
  v639 = -1;
  v640 = 0;
  v641 = 0;
  v642 = -1;
  v643 = 0;
  v644 = 0;
  v645 = -1;
  v646 = 0;
  v647 = 0;
  v648 = -1;
  v649 = 0;
  v650 = 0;
  v651 = 24;
  v652 = PrivacySettingsInfo::GetSystemPrivacySettingHumanInterfaceDevice;
  v653 = 0;
  v654 = -1;
  v655 = 0;
  v656 = 0;
  v78 = 2;
  v79 = 0;
  v80 = 0;
  SystemRequirementsExpr::Not(&v78, v657);
  v658 = 0;
  v659 = 0;
  v660 = 0;
  v661 = L"SystemPrivacySettingLocation";
  v662 = 0;
  v663 = 2;
  v664 = 0;
  v665 = 0;
  v666 = -1;
  v667 = 0;
  v668 = 0;
  v669 = -1;
  v670 = 0;
  v671 = 0;
  v672 = -1;
  v673 = 0;
  v674 = 0;
  v675 = -1;
  v676 = 0;
  v677 = 0;
  v678 = -1;
  v679 = 0;
  v680 = 0;
  v681 = -1;
  v682 = 0;
  v683 = 0;
  v684 = -1;
  v685 = 0;
  v686 = 0;
  v687 = -1;
  v688 = 0;
  v689 = 0;
  v690 = -1;
  v691 = 0;
  v692 = 0;
  v693 = 26;
  v694 = PrivacySettingsInfo::GetSystemPrivacySettingLocation;
  v695 = 0;
  v696 = -1;
  v697 = 0;
  v698 = 0;
  v75 = 2;
  v76 = 0;
  v77 = 0;
  SystemRequirementsExpr::Not(&v75, v699);
  v700 = 0;
  v701 = 0;
  v702 = 0;
  v703 = L"SystemPrivacySettingLocationHistory";
  v704 = 0;
  v705 = 2;
  v706 = 0;
  v707 = 0;
  v708 = -1;
  v709 = 0;
  v710 = 0;
  v711 = -1;
  v712 = 0;
  v713 = 0;
  v714 = -1;
  v715 = 0;
  v716 = 0;
  v717 = -1;
  v718 = 0;
  v719 = 0;
  v720 = -1;
  v721 = 0;
  v722 = 0;
  v723 = -1;
  v724 = 0;
  v725 = 0;
  v726 = -1;
  v727 = 0;
  v728 = 0;
  v729 = -1;
  v730 = 0;
  v731 = 0;
  v732 = -1;
  v733 = 0;
  v734 = 0;
  v735 = 28;
  v736 = PrivacySettingsInfo::GetSystemPrivacySettingLocationHistory;
  v737 = 0;
  v738 = -1;
  v739 = 0;
  v740 = 0;
  v72 = 2;
  v73 = 0;
  v74 = 0;
  SystemRequirementsExpr::Not(&v72, v741);
  v742 = 0;
  v743 = 0;
  v744 = 0;
  v745 = L"SystemPrivacySettingMicrophone";
  v746 = 0;
  v747 = 2;
  v748 = 0;
  v749 = 0;
  v750 = -1;
  v751 = 0;
  v752 = 0;
  v753 = -1;
  v754 = 0;
  v755 = 0;
  v756 = -1;
  v757 = 0;
  v758 = 0;
  v759 = -1;
  v760 = 0;
  v761 = 0;
  v762 = -1;
  v763 = 0;
  v764 = 0;
  v765 = -1;
  v766 = 0;
  v767 = 0;
  v768 = -1;
  v769 = 0;
  v770 = 0;
  v771 = -1;
  v772 = 0;
  v773 = 0;
  v774 = -1;
  v775 = 0;
  v776 = 0;
  v777 = 30;
  v778 = PrivacySettingsInfo::GetSystemPrivacySettingMicrophone;
  v779 = 0;
  v780 = -1;
  v781 = 0;
  v782 = 0;
  v69 = 2;
  v70 = 0;
  v71 = 0;
  SystemRequirementsExpr::Not(&v69, v783);
  v784 = 0;
  v785 = 0;
  v786 = 0;
  v787 = L"SystemPrivacySettingPhoneCall";
  v788 = 0;
  v789 = 2;
  v790 = 0;
  v791 = 0;
  v792 = -1;
  v793 = 0;
  v794 = 0;
  v795 = -1;
  v796 = 0;
  v797 = 0;
  v798 = -1;
  v799 = 0;
  v800 = 0;
  v801 = -1;
  v802 = 0;
  v803 = 0;
  v804 = -1;
  v805 = 0;
  v806 = 0;
  v807 = -1;
  v808 = 0;
  v809 = 0;
  v810 = -1;
  v811 = 0;
  v812 = 0;
  v813 = -1;
  v814 = 0;
  v815 = 0;
  v816 = -1;
  v817 = 0;
  v818 = 0;
  v819 = 32;
  v820 = PrivacySettingsInfo::GetSystemPrivacySettingPhoneCall;
  v821 = 0;
  v822 = -1;
  v823 = 0;
  v824 = 0;
  v66 = 2;
  v67 = 0;
  v68 = 0;
  SystemRequirementsExpr::Not(&v66, v825);
  v826 = 0;
  v827 = 0;
  v828 = 0;
  v829 = L"SystemPrivacySettingPhoneCallHistory";
  v830 = 0;
  v831 = 2;
  v832 = 0;
  v833 = 0;
  v834 = -1;
  v835 = 0;
  v836 = 0;
  v837 = -1;
  v838 = 0;
  v839 = 0;
  v840 = -1;
  v841 = 0;
  v842 = 0;
  v843 = -1;
  v844 = 0;
  v845 = 0;
  v846 = -1;
  v847 = 0;
  v848 = 0;
  v849 = -1;
  v850 = 0;
  v851 = 0;
  v852 = -1;
  v853 = 0;
  v854 = 0;
  v855 = -1;
  v856 = 0;
  v857 = 0;
  v858 = -1;
  v859 = 0;
  v860 = 0;
  v861 = 34;
  v862 = PrivacySettingsInfo::GetSystemPrivacySettingPhoneCallHistory;
  v863 = 0;
  v864 = -1;
  v865 = 0;
  v866 = 0;
  v63 = 2;
  v64 = 0;
  v65 = 0;
  SystemRequirementsExpr::Not(&v63, v867);
  v868 = 0;
  v869 = 0;
  v870 = 0;
  v871 = L"SystemPrivacySettingPicturesLibrary";
  v872 = 0;
  v873 = 2;
  v874 = 0;
  v875 = 0;
  v876 = -1;
  v877 = 0;
  v878 = 0;
  v879 = -1;
  v880 = 0;
  v881 = 0;
  v882 = -1;
  v883 = 0;
  v884 = 0;
  v885 = -1;
  v886 = 0;
  v887 = 0;
  v888 = -1;
  v889 = 0;
  v890 = 0;
  v891 = -1;
  v892 = 0;
  v893 = 0;
  v894 = -1;
  v895 = 0;
  v896 = 0;
  v897 = -1;
  v898 = 0;
  v899 = 0;
  v900 = -1;
  v901 = 0;
  v902 = 0;
  v903 = 36;
  v904 = PrivacySettingsInfo::GetSystemPrivacySettingPicturesLibrary;
  v905 = 0;
  v906 = -1;
  v907 = 0;
  v908 = 0;
  v60 = 2;
  v61 = 0;
  v62 = 0;
  SystemRequirementsExpr::Not(&v60, v909);
  v910 = 0;
  v911 = 0;
  v912 = 0;
  v913 = L"SystemPrivacySettingRadios";
  v914 = 0;
  v915 = 2;
  v916 = 0;
  v917 = 0;
  v918 = -1;
  v919 = 0;
  v920 = 0;
  v921 = -1;
  v922 = 0;
  v923 = 0;
  v924 = -1;
  v925 = 0;
  v926 = 0;
  v927 = -1;
  v928 = 0;
  v929 = 0;
  v930 = -1;
  v931 = 0;
  v932 = 0;
  v933 = -1;
  v934 = 0;
  v935 = 0;
  v936 = -1;
  v937 = 0;
  v938 = 0;
  v939 = -1;
  v940 = 0;
  v941 = 0;
  v942 = -1;
  v943 = 0;
  v944 = 0;
  v945 = 38;
  v946 = PrivacySettingsInfo::GetSystemPrivacySettingRadios;
  v947 = 0;
  v948 = -1;
  v949 = 0;
  v950 = 0;
  v57 = 2;
  v58 = 0;
  v59 = 0;
  SystemRequirementsExpr::Not(&v57, v951);
  v952 = 0;
  v953 = 0;
  v954 = 0;
  v955 = L"SystemPrivacySettingSensorsCustom";
  v956 = 0;
  v957 = 2;
  v958 = 0;
  v959 = 0;
  v960 = -1;
  v961 = 0;
  v962 = 0;
  v963 = -1;
  v964 = 0;
  v965 = 0;
  v966 = -1;
  v967 = 0;
  v968 = 0;
  v969 = -1;
  v970 = 0;
  v971 = 0;
  v972 = -1;
  v973 = 0;
  v974 = 0;
  v975 = -1;
  v976 = 0;
  v977 = 0;
  v978 = -1;
  v979 = 0;
  v980 = 0;
  v981 = -1;
  v982 = 0;
  v983 = 0;
  v984 = -1;
  v985 = 0;
  v986 = 0;
  v987 = 40;
  v988 = PrivacySettingsInfo::GetSystemPrivacySettingSensorsCustom;
  v989 = 0;
  v990 = -1;
  v991 = 0;
  v992 = 0;
  v54 = 2;
  v55 = 0;
  v56 = 0;
  SystemRequirementsExpr::Not(&v54, v993);
  v994 = 0;
  v995 = 0;
  v996 = 0;
  v997 = L"SystemPrivacySettingSerialCommunication";
  v998 = 0;
  v999 = 2;
  v1000 = 0;
  v1001 = 0;
  v1002 = -1;
  v1003 = 0;
  v1004 = 0;
  v1005 = -1;
  v1006 = 0;
  v1007 = 0;
  v1008 = -1;
  v1009 = 0;
  v1010 = 0;
  v1011 = -1;
  v1012 = 0;
  v1013 = 0;
  v1014 = -1;
  v1015 = 0;
  v1016 = 0;
  v1017 = -1;
  v1018 = 0;
  v1019 = 0;
  v1020 = -1;
  v1021 = 0;
  v1022 = 0;
  v1023 = -1;
  v1024 = 0;
  v1025 = 0;
  v1026 = -1;
  v1027 = 0;
  v1028 = 0;
  v1029 = 42;
  v1030 = PrivacySettingsInfo::GetSystemPrivacySettingSerialCommunication;
  v1031 = 0;
  v1032 = -1;
  v1033 = 0;
  v1034 = 0;
  v51 = 2;
  v52 = 0;
  v53 = 0;
  SystemRequirementsExpr::Not(&v51, v1035);
  v1036 = 0;
  v1037 = 0;
  v1038 = 0;
  v1039 = L"SystemPrivacySettingSms";
  v1040 = 0;
  v1041 = 2;
  v1042 = 0;
  v1043 = 0;
  v1044 = -1;
  v1045 = 0;
  v1046 = 0;
  v1047 = -1;
  v1048 = 0;
  v1049 = 0;
  v1050 = -1;
  v1051 = 0;
  v1052 = 0;
  v1053 = -1;
  v1054 = 0;
  v1055 = 0;
  v1056 = -1;
  v1057 = 0;
  v1058 = 0;
  v1059 = -1;
  v1060 = 0;
  v1061 = 0;
  v1062 = -1;
  v1063 = 0;
  v1064 = 0;
  v1065 = -1;
  v1066 = 0;
  v1067 = 0;
  v1068 = -1;
  v1069 = 0;
  v1070 = 0;
  v1071 = 44;
  v1072 = PrivacySettingsInfo::GetSystemPrivacySettingSms;
  v1073 = 0;
  v1074 = -1;
  v1075 = 0;
  v1076 = 0;
  v48 = 2;
  v49 = 0;
  v50 = 0;
  SystemRequirementsExpr::Not(&v48, v1077);
  v1078 = 0;
  v1079 = 0;
  v1080 = 0;
  v1081 = L"SystemPrivacySettingUSB";
  v1082 = 0;
  v1083 = 2;
  v1084 = 0;
  v1085 = 0;
  v1086 = -1;
  v1087 = 0;
  v1088 = 0;
  v1089 = -1;
  v1090 = 0;
  v1091 = 0;
  v1092 = -1;
  v1093 = 0;
  v1094 = 0;
  v1095 = -1;
  v1096 = 0;
  v1097 = 0;
  v1098 = -1;
  v1099 = 0;
  v1100 = 0;
  v1101 = -1;
  v1102 = 0;
  v1103 = 0;
  v1104 = -1;
  v1105 = 0;
  v1106 = 0;
  v1107 = -1;
  v1108 = 0;
  v1109 = 0;
  v1110 = -1;
  v1111 = 0;
  v1112 = 0;
  v1113 = 46;
  v1114 = PrivacySettingsInfo::GetSystemPrivacySettingUSB;
  v1115 = 0;
  v1116 = -1;
  v1117 = 0;
  v1118 = 0;
  v45 = 2;
  v46 = 0;
  v47 = 0;
  SystemRequirementsExpr::Not(&v45, v1119);
  v1120 = 0;
  v1121 = 0;
  v1122 = 0;
  v1123 = L"SystemPrivacySettingUserAccountInformation";
  v1124 = 0;
  v1125 = 2;
  v1126 = 0;
  v1127 = 0;
  v1128 = -1;
  v1129 = 0;
  v1130 = 0;
  v1131 = -1;
  v1132 = 0;
  v1133 = 0;
  v1134 = -1;
  v1135 = 0;
  v1136 = 0;
  v1137 = -1;
  v1138 = 0;
  v1139 = 0;
  v1140 = -1;
  v1141 = 0;
  v1142 = 0;
  v1143 = -1;
  v1144 = 0;
  v1145 = 0;
  v1146 = -1;
  v1147 = 0;
  v1148 = 0;
  v1149 = -1;
  v1150 = 0;
  v1151 = 0;
  v1152 = -1;
  v1153 = 0;
  v1154 = 0;
  v1155 = 48;
  v1156 = PrivacySettingsInfo::GetSystemPrivacySettingUserAccountInformation;
  v1157 = 0;
  v1158 = -1;
  v1159 = 0;
  v1160 = 0;
  v42 = 2;
  v43 = 0;
  v44 = 0;
  SystemRequirementsExpr::Not(&v42, v1161);
  v1162 = 0;
  v1163 = 0;
  v1164 = 0;
  v1165 = L"SystemPrivacySettingUserDataTasks";
  v1166 = 0;
  v1167 = 2;
  v1168 = 0;
  v1169 = 0;
  v1170 = -1;
  v1171 = 0;
  v1172 = 0;
  v1173 = -1;
  v1174 = 0;
  v1175 = 0;
  v1176 = -1;
  v1177 = 0;
  v1178 = 0;
  v1179 = -1;
  v1180 = 0;
  v1181 = 0;
  v1182 = -1;
  v1183 = 0;
  v1184 = 0;
  v1185 = -1;
  v1186 = 0;
  v1187 = 0;
  v1188 = -1;
  v1189 = 0;
  v1190 = 0;
  v1191 = -1;
  v1192 = 0;
  v1193 = 0;
  v1194 = -1;
  v1195 = 0;
  v1196 = 0;
  v1197 = 50;
  v1198 = PrivacySettingsInfo::GetSystemPrivacySettingUserDataTasks;
  v1199 = 0;
  v1200 = -1;
  v1201 = 0;
  v1202 = 0;
  v39 = 2;
  v40 = 0;
  v41 = 0;
  SystemRequirementsExpr::Not(&v39, v1203);
  v1204 = 0;
  v1205 = 0;
  v1206 = 0;
  v1207 = L"SystemPrivacySettingUserNotificationListener";
  v1208 = 0;
  v1209 = 2;
  v1210 = 0;
  v1211 = 0;
  v1212 = -1;
  v1213 = 0;
  v1214 = 0;
  v1215 = -1;
  v1216 = 0;
  v1217 = 0;
  v1218 = -1;
  v1219 = 0;
  v1220 = 0;
  v1221 = -1;
  v1222 = 0;
  v1223 = 0;
  v1224 = -1;
  v1225 = 0;
  v1226 = 0;
  v1227 = -1;
  v1228 = 0;
  v1229 = 0;
  v1230 = -1;
  v1231 = 0;
  v1232 = 0;
  v1233 = -1;
  v1234 = 0;
  v1235 = 0;
  v1236 = -1;
  v1237 = 0;
  v1238 = 0;
  v1239 = 52;
  v1240 = PrivacySettingsInfo::GetSystemPrivacySettingUserNotificationListener;
  v1241 = 0;
  v1242 = -1;
  v1243 = 0;
  v1244 = 0;
  v36 = 2;
  v37 = 0;
  v38 = 0;
  SystemRequirementsExpr::Not(&v36, v1245);
  v1246 = 0;
  v1247 = 0;
  v1248 = 0;
  v1249 = L"SystemPrivacySettingVideosLibrary";
  v1250 = 0;
  v1251 = 2;
  v1252 = 0;
  v1253 = 0;
  v1254 = -1;
  v1255 = 0;
  v1256 = 0;
  v1257 = -1;
  v1258 = 0;
  v1259 = 0;
  v1260 = -1;
  v1261 = 0;
  v1262 = 0;
  v1263 = -1;
  v1264 = 0;
  v1265 = 0;
  v1266 = -1;
  v1267 = 0;
  v1268 = 0;
  v1269 = -1;
  v1270 = 0;
  v1271 = 0;
  v1272 = -1;
  v1273 = 0;
  v1274 = 0;
  v1275 = -1;
  v1276 = 0;
  v1277 = 0;
  v1278 = -1;
  v1279 = 0;
  v1280 = 0;
  v1281 = 54;
  v1282 = PrivacySettingsInfo::GetSystemPrivacySettingVideosLibrary;
  v1283 = 0;
  v1284 = -1;
  v1285 = 0;
  v1286 = 0;
  v33 = 2;
  v34 = 0;
  v35 = 0;
  SystemRequirementsExpr::Not(&v33, v1287);
  v1288 = 0;
  v1289 = 0;
  v1290 = 0;
  v1291 = L"SystemPrivacySettingWebcam";
  v1292 = 0;
  v1293 = 2;
  v1294 = 0;
  v1295 = 0;
  v1296 = -1;
  v1297 = 0;
  v1298 = 0;
  v1299 = -1;
  v1300 = 0;
  v1301 = 0;
  v1302 = -1;
  v1303 = 0;
  v1304 = 0;
  v1305 = -1;
  v1306 = 0;
  v1307 = 0;
  v1308 = -1;
  v1309 = 0;
  v1310 = 0;
  v1311 = -1;
  v1312 = 0;
  v1313 = 0;
  v1314 = -1;
  v1315 = 0;
  v1316 = 0;
  v1317 = -1;
  v1318 = 0;
  v1319 = 0;
  v1320 = -1;
  v1321 = 0;
  v1322 = 0;
  v1323 = 56;
  v1324 = PrivacySettingsInfo::GetSystemPrivacySettingWebcam;
  v1325 = 0;
  v1326 = -1;
  v1327 = 0;
  v1328 = 0;
  v30 = 2;
  v31 = 0;
  v32 = 0;
  SystemRequirementsExpr::Not(&v30, v1329);
  v1330 = 0;
  v1331 = 0;
  v1332 = 0;
  v1333 = L"SystemPrivacySettingWifiData";
  v1334 = 256;
  v1335 = 0;
  v1336 = 0;
  v1337 = 0;
  v1338 = -1;
  v1339 = 0;
  v1340 = 0;
  v1341 = -1;
  v1342 = 0;
  v1343 = 0;
  v1344 = -1;
  v1345 = 0;
  v1346 = 0;
  v1347 = -1;
  v1348 = 0;
  v1349 = 0;
  v1350 = -1;
  v1351 = 0;
  v1352 = 0;
  v1353 = -1;
  v1354 = 0;
  v1355 = 0;
  v1356 = -1;
  v1357 = 0;
  v1358 = 0;
  v1359 = -1;
  v1360 = 0;
  v1361 = 0;
  v1362 = -1;
  v1363 = 0;
  v1364 = 0;
  v1365 = 58;
  v1366 = PrivacySettingsInfo::GetSystemPrivacySettingWifiData;
  v1367 = 0;
  v1368 = -1;
  v1369 = 0;
  v1370 = 0;
  v27 = 2;
  v28 = 0;
  v29 = 0;
  SystemRequirementsExpr::Not(&v27, v1371);
  v1372 = 0;
  v1373 = 0;
  v1374 = 0;
  v1375 = L"SystemPrivacySettingWiFiDirect";
  v1376 = 0;
  v1377 = 2;
  v1378 = 0;
  v1379 = 0;
  v1380 = -1;
  v1381 = 0;
  v1382 = 0;
  v1383 = -1;
  v1384 = 0;
  v1385 = 0;
  v1386 = -1;
  v1387 = 0;
  v1388 = 0;
  v1389 = -1;
  v1390 = 0;
  v1391 = 0;
  v1392 = -1;
  v1393 = 0;
  v1394 = 0;
  v1395 = -1;
  v1396 = 0;
  v1397 = 0;
  v1398 = -1;
  v1399 = 0;
  v1400 = 0;
  v1401 = -1;
  v1402 = 0;
  v1403 = 0;
  v1404 = -1;
  v1405 = 0;
  v1406 = 0;
  v1407 = 60;
  v1408 = PrivacySettingsInfo::GetSystemPrivacySettingWiFiDirect;
  v1409 = 0;
  v1410 = -1;
  v1411 = 0;
  v1412 = 0;
  v24 = 2;
  v25 = 0;
  v26 = 0;
  SystemRequirementsExpr::Not(&v24, v1413);
  v1414 = 0;
  v1415 = 0;
  v1416 = 0;
  v1417 = L"SystemPrivacySettingActivityHistoryCollection";
  v1418 = 257;
  v1419 = 0;
  v1420 = 0;
  v1421 = 0;
  v1422 = -1;
  v1423 = 0;
  v1424 = 0;
  v1425 = -1;
  v1426 = 0;
  v1427 = 0;
  v1428 = -1;
  v1429 = 0;
  v1430 = 0;
  v1431 = -1;
  v1432 = 0;
  v1433 = 0;
  v1434 = -1;
  v1435 = 0;
  v1436 = 0;
  v1437 = -1;
  v1438 = 0;
  v1439 = 0;
  v1440 = -1;
  v1441 = 0;
  v1442 = 0;
  v1443 = -1;
  v1444 = 0;
  v1445 = 0;
  v1446 = -1;
  v1447 = 0;
  v1448 = 0;
  v1449 = 62;
  v1450 = CPrivacySettingsInfo::GetSystemPrivacySettingActivityHistoryCloudSync;
  v1451 = 0;
  v1452 = -1;
  v1453 = 0;
  v1454 = 0;
  v21 = 2;
  v22 = 0;
  v23 = 0;
  SystemRequirementsExpr::Not(&v21, v1455);
  v1456 = 0;
  v1457 = 0;
  v1458 = 0;
  v1459 = L"SystemPrivacySettingActivityHistoryCloudSync";
  v1460 = 257;
  v1461 = 0;
  v1462 = 0;
  v1463 = 0;
  v1464 = -1;
  v1465 = 0;
  v1466 = 0;
  v1467 = -1;
  v1468 = 0;
  v1469 = 0;
  v1470 = -1;
  v1471 = 0;
  v1472 = 0;
  v1473 = -1;
  v1474 = 0;
  v1475 = 0;
  v1476 = -1;
  v1477 = 0;
  v1478 = 0;
  v1479 = -1;
  v1480 = 0;
  v1481 = 0;
  v1482 = -1;
  v1483 = 0;
  v1484 = 0;
  v1485 = -1;
  v1486 = 0;
  v1487 = 0;
  v1488 = -1;
  v1489 = 0;
  v1490 = 0;
  v1491 = 64;
  v1492 = CPrivacySettingsInfo::GetSystemPrivacySettingActivityHistoryCloudSync;
  v1493 = 0;
  v1494 = -1;
  v1495 = 0;
  v1496 = 0;
  v18 = 2;
  v19 = 0;
  v20 = 0;
  SystemRequirementsExpr::Not(&v18, v1497);
  v1498 = 0;
  v1499 = 0;
  v1500 = 0;
  v1501 = L"SystemPrivacySettingAdvertisingId";
  v1502 = 0;
  v1503 = 2;
  v1504 = 0;
  v1505 = 0;
  v1506 = -1;
  v1507 = 0;
  v1508 = 0;
  v1509 = -1;
  v1510 = 0;
  v1511 = 0;
  v1512 = -1;
  v1513 = 0;
  v1514 = 0;
  v1515 = -1;
  v1516 = 0;
  v1517 = 0;
  v1518 = -1;
  v1519 = 0;
  v1520 = 0;
  v1521 = -1;
  v1522 = 0;
  v1523 = 0;
  v1524 = -1;
  v1525 = 0;
  v1526 = 0;
  v1527 = -1;
  v1528 = 0;
  v1529 = 0;
  v1530 = -1;
  v1531 = 0;
  v1532 = 0;
  v1533 = 66;
  v1534 = UserPrivacySettingsInfo::GetUserPrivacySettingAdvertisingId;
  v1535 = 0;
  v1536 = -1;
  v1537 = 0;
  v1538 = 0;
  v15 = 2;
  v16 = 0;
  v17 = 0;
  SystemRequirementsExpr::Not(&v15, v1539);
  v1540 = 0;
  v1541 = 0;
  v1542 = 0;
  v1543 = L"SystemPrivacySettingSpeechPersonalization";
  v1544 = 0;
  v1545 = 2;
  v1546 = 0;
  v1547 = 0;
  v1548 = -1;
  v1549 = 0;
  v1550 = 0;
  v1551 = -1;
  v1552 = 0;
  v1553 = 0;
  v1554 = -1;
  v1555 = 0;
  v1556 = 0;
  v1557 = -1;
  v1558 = 0;
  v1559 = 0;
  v1560 = -1;
  v1561 = 0;
  v1562 = 0;
  v1563 = -1;
  v1564 = 0;
  v1565 = 0;
  v1566 = -1;
  v1567 = 0;
  v1568 = 0;
  v1569 = -1;
  v1570 = 0;
  v1571 = 0;
  v1572 = -1;
  v1573 = 0;
  v1574 = 0;
  v1575 = 68;
  v1576 = PrivacySettingsInfo::GetSystemPrivacySettingSpeechPersonalization;
  v1577 = 0;
  v1578 = -1;
  v1579 = 0;
  v1580 = 0;
  v12 = 2;
  v13 = 0;
  v14 = 0;
  SystemRequirementsExpr::Not(&v12, v1581);
  v1582 = 0;
  v1583 = 0;
  v1584 = 0;
  v1585 = L"SystemPrivacySettingInkTypeImprovement";
  v1586 = 0;
  v1587 = 2;
  v1588 = 0;
  v1589 = 0;
  v1590 = -1;
  v1591 = 0;
  v1592 = 0;
  v1593 = -1;
  v1594 = 0;
  v1595 = 0;
  v1596 = -1;
  v1597 = 0;
  v1598 = 0;
  v1599 = -1;
  v1600 = 0;
  v1601 = 0;
  v1602 = -1;
  v1603 = 0;
  v1604 = 0;
  v1605 = -1;
  v1606 = 0;
  v1607 = 0;
  v1608 = -1;
  v1609 = 0;
  v1610 = 0;
  v1611 = -1;
  v1612 = 0;
  v1613 = 0;
  v1614 = -1;
  v1615 = 0;
  v1616 = 0;
  v1617 = 72;
  v1618 = PrivacySettingsInfo::GetSystemPrivacySettingInkTypeImprovement;
  v1619 = 0;
  v1620 = -1;
  v1621 = 0;
  v1622 = 0;
  v9 = 2;
  v10 = 0;
  v11 = 0;
  SystemRequirementsExpr::Not(&v9, v1623);
  v1624 = 0;
  v1625 = 0;
  v1626 = 0;
  v1627 = L"SystemPrivacySettingFindMyDevice";
  v1628 = 0;
  v1629 = 2;
  v1630 = 0;
  v1631 = 0;
  v1632 = -1;
  v1633 = 0;
  v1634 = 0;
  v1635 = -1;
  v1636 = 0;
  v1637 = 0;
  v1638 = -1;
  v1639 = 0;
  v1640 = 0;
  v1641 = -1;
  v1642 = 0;
  v1643 = 0;
  v1644 = -1;
  v1645 = 0;
  v1646 = 0;
  v1647 = -1;
  v1648 = 0;
  v1649 = 0;
  v1650 = -1;
  v1651 = 0;
  v1652 = 0;
  v1653 = -1;
  v1654 = 0;
  v1655 = 0;
  v1656 = -1;
  v1657 = 0;
  v1658 = 0;
  v1659 = 74;
  v1660 = UserPrivacySettingsInfo::GetUserPrivacySettingFindMyDevice;
  v1661 = 0;
  v1662 = -1;
  v1663 = 0;
  v1664 = 0;
  v6 = 2;
  v7 = 0;
  v8 = 0;
  SystemRequirementsExpr::Not(&v6, v1665);
  v1666 = 0;
  v1667 = 0;
  v1668 = 0;
  std::vector<AttributeDefinition2<_USER_DISPLAY_INFO_2,DisplayInfo>>::_Insert_counted_range<AttributeDefinition2<_USER_DISPLAY_INFO_2,DisplayInfo> const *>(
    a1,
    a1[1],
    &v115,
    37);
  `eh vector destructor iterator'(
    &v115,
    0x158u,
    0x25u,
    (void (*)(void *))AttributeDefinition2<_AZURE_INFO_2,AzureInfo>::~AttributeDefinition2<_AZURE_INFO_2,AzureInfo>);
  std::vector<SystemRequirementsExpr>::_Tidy(&v7);
  std::vector<SystemRequirementsExpr>::_Tidy(&v10);
  std::vector<SystemRequirementsExpr>::_Tidy(&v13);
  std::vector<SystemRequirementsExpr>::_Tidy(&v16);
  std::vector<SystemRequirementsExpr>::_Tidy(&v19);
  std::vector<SystemRequirementsExpr>::_Tidy(&v22);
  std::vector<SystemRequirementsExpr>::_Tidy(&v25);
  std::vector<SystemRequirementsExpr>::_Tidy(&v28);
  std::vector<SystemRequirementsExpr>::_Tidy(&v31);
  std::vector<SystemRequirementsExpr>::_Tidy(&v34);
  std::vector<SystemRequirementsExpr>::_Tidy(&v37);
  std::vector<SystemRequirementsExpr>::_Tidy(&v40);
  std::vector<SystemRequirementsExpr>::_Tidy(&v43);
  std::vector<SystemRequirementsExpr>::_Tidy(&v46);
  std::vector<SystemRequirementsExpr>::_Tidy(&v49);
  std::vector<SystemRequirementsExpr>::_Tidy(&v52);
  std::vector<SystemRequirementsExpr>::_Tidy(&v55);
  std::vector<SystemRequirementsExpr>::_Tidy(&v58);
  std::vector<SystemRequirementsExpr>::_Tidy(&v61);
  std::vector<SystemRequirementsExpr>::_Tidy(&v64);
  std::vector<SystemRequirementsExpr>::_Tidy(&v67);
  std::vector<SystemRequirementsExpr>::_Tidy(&v70);
  std::vector<SystemRequirementsExpr>::_Tidy(&v73);
  std::vector<SystemRequirementsExpr>::_Tidy(&v76);
  std::vector<SystemRequirementsExpr>::_Tidy(&v79);
  std::vector<SystemRequirementsExpr>::_Tidy(&v82);
  std::vector<SystemRequirementsExpr>::_Tidy(&v85);
  std::vector<SystemRequirementsExpr>::_Tidy(&v88);
  std::vector<SystemRequirementsExpr>::_Tidy(&v91);
  std::vector<SystemRequirementsExpr>::_Tidy(&v94);
  std::vector<SystemRequirementsExpr>::_Tidy(&v97);
  std::vector<SystemRequirementsExpr>::_Tidy(&v100);
  std::vector<SystemRequirementsExpr>::_Tidy(&v103);
  std::vector<SystemRequirementsExpr>::_Tidy(&v106);
  std::vector<SystemRequirementsExpr>::_Tidy(&v109);
  std::vector<SystemRequirementsExpr>::_Tidy(&v112);
  std::vector<SystemRequirementsExpr>::_Tidy(&v4);
  return a1;
}

```

## disassembly

```asm
0x180063318  mov     [rsp-8+arg_8], rbx
0x18006331d  mov     [rsp-8+arg_10], rsi
0x180063322  push    rbp
0x180063323  push    rdi
0x180063324  push    r14
0x180063326  lea     rbp, [rsp-35A0h]
0x18006332e  mov     eax, 36A0h
0x180063333  call    _alloca_probe
0x180063338  sub     rsp, rax
0x18006333b  mov     rax, cs:__security_cookie
0x180063342  xor     rax, rsp
0x180063345  mov     [rbp+35B0h+var_20], rax
0x18006334c  mov     rbx, rcx
0x18006334f  mov     [rbp+35B0h+var_31E8], rcx
0x180063356  xor     r14d, r14d
0x180063359  mov     [rsp+36B0h+var_3690], r14d
0x18006335e  mov     [rcx], r14
0x180063361  mov     [rcx+8], r14
0x180063365  mov     [rcx+10h], r14
0x180063369  mov     [rsp+36B0h+var_3690], 1
0x180063371  lea     rax, aSystemprivacys_1; "SystemPrivacySettingActivity"
0x180063378  mov     [rbp+35B0h+var_31E0], rax
0x18006337f  mov     [rbp+35B0h+var_31D8], r14w
0x180063387  lea     esi, [r14+2]
0x18006338b  mov     [rbp+35B0h+var_31D6], sil
0x180063392  xor     eax, eax
0x180063394  mov     [rbp+35B0h+var_31D5], eax
0x18006339a  mov     [rbp+35B0h+var_31D1], al
0x1800633a0  or      edi, 0FFFFFFFFh
0x1800633a3  mov     [rbp+35B0h+var_31D0], edi
0x1800633a9  mov     [rbp+35B0h+var_31C8], r14
0x1800633b0  mov     [rbp+35B0h+var_31C0], r14
0x1800633b7  mov     [rbp+35B0h+var_31B8], edi
0x1800633bd  mov     [rbp+35B0h+var_31B0], r14
0x1800633c4  mov     [rbp+35B0h+var_31A8], r14
0x1800633cb  mov     [rbp+35B0h+var_31A0], edi
0x1800633d1  mov     [rbp+35B0h+var_3198], r14
0x1800633d8  mov     [rbp+35B0h+var_3190], r14
0x1800633df  mov     [rbp+35B0h+var_3188], edi
0x1800633e5  mov     [rbp+35B0h+var_3180], r14
0x1800633ec  mov     [rbp+35B0h+var_3178], r14
0x1800633f3  mov     [rbp+35B0h+var_3170], edi
0x1800633f9  mov     [rbp+35B0h+var_3168], r14
0x180063400  mov     [rbp+35B0h+var_3160], r14
0x180063407  mov     [rbp+35B0h+var_3158], edi
0x18006340d  mov     [rbp+35B0h+var_3150], r14
0x180063414  mov     [rbp+35B0h+var_3148], r14
0x18006341b  mov     [rbp+35B0h+var_3140], edi
0x180063421  mov     [rbp+35B0h+var_3138], r14
0x180063428  mov     [rbp+35B0h+var_3130], r14
0x18006342f  mov     [rbp+35B0h+var_3128], edi
0x180063435  mov     [rbp+35B0h+var_3120], r14
0x18006343c  mov     [rbp+35B0h+var_3118], r14
0x180063443  mov     [rbp+35B0h+var_3110], edi
0x180063449  mov     [rbp+35B0h+var_3108], r14
0x180063450  mov     [rbp+35B0h+var_3100], r14
0x180063457  mov     [rbp+35B0h+var_30F8], r14d
0x18006345e  lea     rax, ?GetSystemPrivacySettingActivity@PrivacySettingsInfo@@AEBAFXZ; PrivacySettingsInfo::GetSystemPrivacySettingActivity(void)
0x180063465  mov     [rbp+35B0h+var_30F0], rax
0x18006346c  mov     [rbp+35B0h+var_30E8], r14
0x180063473  mov     [rbp+35B0h+var_30E0], edi
0x180063479  mov     [rbp+35B0h+var_30D8], r14
0x180063480  mov     [rbp+35B0h+var_30D0], r14
0x180063487  mov     [rsp+36B0h+var_3688], esi
0x18006348b  xorps   xmm0, xmm0
0x18006348e  movdqu  [rsp+36B0h+var_3680], xmm0
0x180063494  mov     [rsp+36B0h+var_3670], r14
0x180063499  lea     rdx, [rbp+35B0h+var_30C8]
0x1800634a0  lea     rcx, [rsp+36B0h+var_3688]
0x1800634a5  call    ?Not@SystemRequirementsExpr@@QEBA?AU1@XZ; SystemRequirementsExpr::Not(void)
0x1800634aa  mov     [rbp+35B0h+var_30A8], r14d
0x1800634b1  xorps   xmm0, xmm0
0x1800634b4  movdqa  [rbp+35B0h+var_30A0], xmm0
0x1800634bc  mov     [rbp+35B0h+var_3090], r14
0x1800634c3  lea     rax, aSystemprivacys_9; "SystemPrivacySettingAppDiagnostics"
0x1800634ca  mov     [rbp+35B0h+var_3088], rax
0x1800634d1  mov     [rbp+35B0h+var_3080], r14w
0x1800634d9  mov     [rbp+35B0h+var_307E], sil
0x1800634e0  xor     eax, eax
0x1800634e2  mov     [rbp+35B0h+var_307D], eax
0x1800634e8  mov     [rbp+35B0h+var_3079], al
0x1800634ee  mov     [rbp+35B0h+var_3078], edi
0x1800634f4  mov     [rbp+35B0h+var_3070], r14
0x1800634fb  mov     [rbp+35B0h+var_3068], r14
0x180063502  mov     [rbp+35B0h+var_3060], edi
0x180063508  mov     [rbp+35B0h+var_3058], r14
0x18006350f  mov     [rbp+35B0h+var_3050], r14
0x180063516  mov     [rbp+35B0h+var_3048], edi
0x18006351c  mov     [rbp+35B0h+var_3040], r14
0x180063523  mov     [rbp+35B0h+var_3038], r14
0x18006352a  mov     [rbp+35B0h+var_3030], edi
0x180063530  mov     [rbp+35B0h+var_3028], r14
0x180063537  mov     [rbp+35B0h+var_3020], r14
0x18006353e  mov     [rbp+35B0h+var_3018], edi
0x180063544  mov     [rbp+35B0h+var_3010], r14
0x18006354b  mov     [rbp+35B0h+var_3008], r14
0x180063552  mov     [rbp+35B0h+var_3000], edi
0x180063558  mov     [rbp+35B0h+var_2FF8], r14
0x18006355f  mov     [rbp+35B0h+var_2FF0], r14
0x180063566  mov     [rbp+35B0h+var_2FE8], edi
0x18006356c  mov     [rbp+35B0h+var_2FE0], r14
0x180063573  mov     [rbp+35B0h+var_2FD8], r14
0x18006357a  mov     [rbp+35B0h+var_2FD0], edi
0x180063580  mov     [rbp+35B0h+var_2FC8], r14
0x180063587  mov     [rbp+35B0h+var_2FC0], r14
0x18006358e  mov     [rbp+35B0h+var_2FB8], edi
0x180063594  mov     [rbp+35B0h+var_2FB0], r14
0x18006359b  mov     [rbp+35B0h+var_2FA8], r14
0x1800635a2  mov     [rbp+35B0h+var_2FA0], esi
0x1800635a8  lea     rax, ?GetSystemPrivacySettingAppDiagnostics@PrivacySettingsInfo@@AEBAFXZ; PrivacySettingsInfo::GetSystemPrivacySettingAppDiagnostics(void)
0x1800635af  mov     [rbp+35B0h+var_2F98], rax
0x1800635b6  mov     [rbp+35B0h+var_2F90], r14
0x1800635bd  mov     [rbp+35B0h+var_2F88], edi
0x1800635c3  mov     [rbp+35B0h+var_2F80], r14
0x1800635ca  mov     [rbp+35B0h+var_2F78], r14
0x1800635d1  mov     [rbp+35B0h+var_3208], esi
0x1800635d7  movdqu  [rbp+35B0h+var_3200], xmm0
0x1800635df  mov     [rbp+35B0h+var_31F0], r14
0x1800635e6  lea     rdx, [rbp+35B0h+var_2F70]
0x1800635ed  lea     rcx, [rbp+35B0h+var_3208]
0x1800635f4  call    ?Not@SystemRequirementsExpr@@QEBA?AU1@XZ; SystemRequirementsExpr::Not(void)
0x1800635f9  mov     [rbp+35B0h+var_2F50], r14d
0x180063600  mov     [rbp+35B0h+var_2F48], r14
0x180063607  xorps   xmm0, xmm0
0x18006360a  movdqa  [rbp+35B0h+var_2F40], xmm0
0x180063612  lea     rax, aSystemprivacys_17; "SystemPrivacySettingAppointments"
0x180063619  mov     [rbp+35B0h+var_2F30], rax
0x180063620  mov     [rbp+35B0h+var_2F28], r14w
0x180063628  mov     [rbp+35B0h+var_2F26], sil
0x18006362f  xor     eax, eax
0x180063631  mov     [rbp+35B0h+var_2F25], eax
0x180063637  mov     [rbp+35B0h+var_2F21], al
0x18006363d  mov     [rbp+35B0h+var_2F20], edi
0x180063643  mov     [rbp+35B0h+var_2F18], r14
0x18006364a  mov     [rbp+35B0h+var_2F10], r14
0x180063651  mov     [rbp+35B0h+var_2F08], edi
0x180063657  mov     [rbp+35B0h+var_2F00], r14
0x18006365e  mov     [rbp+35B0h+var_2EF8], r14
0x180063665  mov     [rbp+35B0h+var_2EF0], edi
0x18006366b  mov     [rbp+35B0h+var_2EE8], r14
0x180063672  mov     [rbp+35B0h+var_2EE0], r14
0x180063679  mov     [rbp+35B0h+var_2ED8], edi
0x18006367f  mov     [rbp+35B0h+var_2ED0], r14
0x180063686  mov     [rbp+35B0h+var_2EC8], r14
0x18006368d  mov     [rbp+35B0h+var_2EC0], edi
0x180063693  mov     [rbp+35B0h+var_2EB8], r14
0x18006369a  mov     [rbp+35B0h+var_2EB0], r14
0x1800636a1  mov     [rbp+35B0h+var_2EA8], edi
0x1800636a7  mov     [rbp+35B0h+var_2EA0], r14
0x1800636ae  mov     [rbp+35B0h+var_2E98], r14
0x1800636b5  mov     [rbp+35B0h+var_2E90], edi
0x1800636bb  mov     [rbp+35B0h+var_2E88], r14
0x1800636c2  mov     [rbp+35B0h+var_2E80], r14
0x1800636c9  mov     [rbp+35B0h+var_2E78], edi
0x1800636cf  mov     [rbp+35B0h+var_2E70], r14
0x1800636d6  mov     [rbp+35B0h+var_2E68], r14
0x1800636dd  mov     [rbp+35B0h+var_2E60], edi
0x1800636e3  mov     [rbp+35B0h+var_2E58], r14
0x1800636ea  mov     [rbp+35B0h+var_2E50], r14
0x1800636f1  mov     [rbp+35B0h+var_2E48], 4
0x1800636fb  lea     rax, ?GetSystemPrivacySettingAppointments@PrivacySettingsInfo@@AEBAFXZ; PrivacySettingsInfo::GetSystemPrivacySettingAppointments(void)
0x180063702  mov     [rbp+35B0h+var_2E40], rax
0x180063709  mov     [rbp+35B0h+var_2E38], r14
0x180063710  mov     [rbp+35B0h+var_2E30], edi
0x180063716  mov     [rbp+35B0h+var_2E28], r14
0x18006371d  mov     [rbp+35B0h+var_2E20], r14
0x180063724  mov     [rbp+35B0h+var_3228], esi
0x18006372a  movdqu  [rbp+35B0h+var_3220], xmm0
0x180063732  mov     [rbp+35B0h+var_3210], r14
0x180063739  lea     rdx, [rbp+35B0h+var_2E18]
0x180063740  lea     rcx, [rbp+35B0h+var_3228]
0x180063747  call    ?Not@SystemRequirementsExpr@@QEBA?AU1@XZ; SystemRequirementsExpr::Not(void)
0x18006374c  mov     [rbp+35B0h+var_2DF8], r14d
0x180063753  xorps   xmm0, xmm0
0x180063756  movdqa  [rbp+35B0h+var_2DF0], xmm0
0x18006375e  mov     [rbp+35B0h+var_2DE0], r14
0x180063765  lea     rax, aSystemprivacys_8; "SystemPrivacySettingBluetooth"
0x18006376c  mov     [rbp+35B0h+var_2DD8], rax
0x180063773  mov     [rbp+35B0h+var_2DD0], r14w
0x18006377b  mov     [rbp+35B0h+var_2DCE], sil
0x180063782  xor     eax, eax
0x180063784  mov     [rbp+35B0h+var_2DCD], eax
0x18006378a  mov     [rbp+35B0h+var_2DC9], al
0x180063790  mov     [rbp+35B0h+var_2DC8], edi
0x180063796  mov     [rbp+35B0h+var_2DC0], r14
0x18006379d  mov     [rbp+35B0h+var_2DB8], r14
0x1800637a4  mov     [rbp+35B0h+var_2DB0], edi
0x1800637aa  mov     [rbp+35B0h+var_2DA8], r14
0x1800637b1  mov     [rbp+35B0h+var_2DA0], r14
0x1800637b8  mov     [rbp+35B0h+var_2D98], edi
0x1800637be  mov     [rbp+35B0h+var_2D90], r14
0x1800637c5  mov     [rbp+35B0h+var_2D88], r14
0x1800637cc  mov     [rbp+35B0h+var_2D80], edi
0x1800637d2  mov     [rbp+35B0h+var_2D78], r14
0x1800637d9  mov     [rbp+35B0h+var_2D70], r14
0x1800637e0  mov     [rbp+35B0h+var_2D68], edi
0x1800637e6  mov     [rbp+35B0h+var_2D60], r14
0x1800637ed  mov     [rbp+35B0h+var_2D58], r14
0x1800637f4  mov     [rbp+35B0h+var_2D50], edi
0x1800637fa  mov     [rbp+35B0h+var_2D48], r14
0x180063801  mov     [rbp+35B0h+var_2D40], r14
0x180063808  mov     [rbp+35B0h+var_2D38], edi
0x18006380e  mov     [rbp+35B0h+var_2D30], r14
0x180063815  mov     [rbp+35B0h+var_2D28], r14
0x18006381c  mov     [rbp+35B0h+var_2D20], edi
0x180063822  mov     [rbp+35B0h+var_2D18], r14
0x180063829  mov     [rbp+35B0h+var_2D10], r14
0x180063830  mov     [rbp+35B0h+var_2D08], edi
0x180063836  mov     [rbp+35B0h+var_2D00], r14
0x18006383d  mov     [rbp+35B0h+var_2CF8], r14
0x180063844  mov     [rbp+35B0h+var_2CF0], 6
0x18006384e  lea     rax, ?GetSystemPrivacySettingBluetooth@PrivacySettingsInfo@@AEBAFXZ; PrivacySettingsInfo::GetSystemPrivacySettingBluetooth(void)
0x180063855  mov     [rbp+35B0h+var_2CE8], rax
0x18006385c  mov     [rbp+35B0h+var_2CE0], r14
0x180063863  mov     [rbp+35B0h+var_2CD8], edi
0x180063869  mov     [rbp+35B0h+var_2CD0], r14
0x180063870  mov     [rbp+35B0h+var_2CC8], r14
0x180063877  mov     [rbp+35B0h+var_3248], esi
0x18006387d  movdqu  [rbp+35B0h+var_3240], xmm0
0x180063885  mov     [rbp+35B0h+var_3230], r14
0x18006388c  lea     rdx, [rbp+35B0h+var_2CC0]
0x180063893  lea     rcx, [rbp+35B0h+var_3248]
0x18006389a  call    ?Not@SystemRequirementsExpr@@QEBA?AU1@XZ; SystemRequirementsExpr::Not(void)
0x18006389f  mov     [rbp+35B0h+var_2CA0], r14d
0x1800638a6  mov     [rbp+35B0h+var_2C98], r14
0x1800638ad  xorps   xmm0, xmm0
0x1800638b0  movdqa  [rbp+35B0h+var_2C90], xmm0
0x1800638b8  lea     rax, aSystemprivacys_11; "SystemPrivacySettingBluetoothSync"
0x1800638bf  mov     [rbp+35B0h+var_2C80], rax
0x1800638c6  mov     [rbp+35B0h+var_2C78], r14w
0x1800638ce  mov     [rbp+35B0h+var_2C76], sil
0x1800638d5  xor     eax, eax
0x1800638d7  mov     [rbp+35B0h+var_2C75], eax
0x1800638dd  mov     [rbp+35B0h+var_2C71], al
0x1800638e3  mov     [rbp+35B0h+var_2C70], edi
0x1800638e9  mov     [rbp+35B0h+var_2C68], r14
0x1800638f0  mov     [rbp+35B0h+var_2C60], r14
0x1800638f7  mov     [rbp+35B0h+var_2C58], edi
0x1800638fd  mov     [rbp+35B0h+var_2C50], r14
0x180063904  mov     [rbp+35B0h+var_2C48], r14
0x18006390b  mov     [rbp+35B0h+var_2C40], edi
0x180063911  mov     [rbp+35B0h+var_2C38], r14
0x180063918  mov     [rbp+35B0h+var_2C30], r14
0x18006391f  mov     [rbp+35B0h+var_2C28], edi
0x180063925  mov     [rbp+35B0h+var_2C20], r14
0x18006392c  mov     [rbp+35B0h+var_2C18], r14
0x180063933  mov     [rbp+35B0h+var_2C10], edi
0x180063939  mov     [rbp+35B0h+var_2C08], r14
0x180063940  mov     [rbp+35B0h+var_2C00], r14
0x180063947  mov     [rbp+35B0h+var_2BF8], edi
0x18006394d  mov     [rbp+35B0h+var_2BF0], r14
0x180063954  mov     [rbp+35B0h+var_2BE8], r14
0x18006395b  mov     [rbp+35B0h+var_2BE0], edi
0x180063961  mov     [rbp+35B0h+var_2BD8], r14
0x180063968  mov     [rbp+35B0h+var_2BD0], r14
0x18006396f  mov     [rbp+35B0h+var_2BC8], edi
0x180063975  mov     [rbp+35B0h+var_2BC0], r14
0x18006397c  mov     [rbp+35B0h+var_2BB8], r14
0x180063983  mov     [rbp+35B0h+var_2BB0], edi
0x180063989  mov     [rbp+35B0h+var_2BA8], r14
0x180063990  mov     [rbp+35B0h+var_2BA0], r14
0x180063997  mov     [rbp+35B0h+var_2B98], 8
0x1800639a1  lea     rax, ?GetSystemPrivacySettingBluetoothSync@PrivacySettingsInfo@@AEBAFXZ; PrivacySettingsInfo::GetSystemPrivacySettingBluetoothSync(void)
0x1800639a8  mov     [rbp+35B0h+var_2B90], rax
0x1800639af  mov     [rbp+35B0h+var_2B88], r14
0x1800639b6  mov     [rbp+35B0h+var_2B80], edi
0x1800639bc  mov     [rbp+35B0h+var_2B78], r14
0x1800639c3  mov     [rbp+35B0h+var_2B70], r14
0x1800639ca  mov     [rbp+35B0h+var_3268], esi
0x1800639d0  movdqu  [rbp+35B0h+var_3260], xmm0
0x1800639d8  mov     [rbp+35B0h+var_3250], r14
0x1800639df  lea     rdx, [rbp+35B0h+var_2B68]
0x1800639e6  lea     rcx, [rbp+35B0h+var_3268]
0x1800639ed  call    ?Not@SystemRequirementsExpr@@QEBA?AU1@XZ; SystemRequirementsExpr::Not(void)
0x1800639f2  mov     [rbp+35B0h+var_2B48], r14d
0x1800639f9  xorps   xmm0, xmm0
0x1800639fc  movdqa  [rbp+35B0h+var_2B40], xmm0
0x180063a04  mov     [rbp+35B0h+var_2B30], r14
0x180063a0b  lea     rax, aSystemprivacys_29; "SystemPrivacySettingBroadFileSystemAcce"...
0x180063a12  mov     [rbp+35B0h+var_2B28], rax
0x180063a19  mov     [rbp+35B0h+var_2B20], r14w
0x180063a21  mov     [rbp+35B0h+var_2B1E], sil
0x180063a28  xor     eax, eax
0x180063a2a  mov     [rbp+35B0h+var_2B1D], eax
0x180063a30  mov     [rbp+35B0h+var_2B19], al
0x180063a36  mov     [rbp+35B0h+var_2B18], edi
0x180063a3c  mov     [rbp+35B0h+var_2B10], r14
0x180063a43  mov     [rbp+35B0h+var_2B08], r14
0x180063a4a  mov     [rbp+35B0h+var_2B00], edi
0x180063a50  mov     [rbp+35B0h+var_2AF8], r14
0x180063a57  mov     [rbp+35B0h+var_2AF0], r14
0x180063a5e  mov     [rbp+35B0h+var_2AE8], edi
0x180063a64  mov     [rbp+35B0h+var_2AE0], r14
0x180063a6b  mov     [rbp+35B0h+var_2AD8], r14
0x180063a72  mov     [rbp+35B0h+var_2AD0], edi
0x180063a78  mov     [rbp+35B0h+var_2AC8], r14
0x180063a7f  mov     [rbp+35B0h+var_2AC0], r14
0x180063a86  mov     [rbp+35B0h+var_2AB8], edi
0x180063a8c  mov     [rbp+35B0h+var_2AB0], r14
0x180063a93  mov     [rbp+35B0h+var_2AA8], r14
  ... truncated ...
```
