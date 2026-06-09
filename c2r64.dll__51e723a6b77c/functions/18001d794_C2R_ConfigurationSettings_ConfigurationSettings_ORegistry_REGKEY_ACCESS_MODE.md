# C2R::ConfigurationSettings::ConfigurationSettings(ORegistry::REGKEY_ACCESS_MODE)

- ea: `0x18001d794`
- end: `0x18001f1b0`
- name: `??0ConfigurationSettings@C2R@@IEAA@W4REGKEY_ACCESS_MODE@ORegistry@@@Z`
- size: `6684`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800054e0`

## callees

- `0x180005138`
- `0x180008f98`
- `0x18000c0a4`
- `0x18000c2dc`
- `0x18000c5f8`
- `0x18000c854`
- `0x18000dd68`
- `0x18001f1b0`
- `0x18003e690`
- `0x18003ec0c`

## string_xrefs

- `0x18001d8aa`: `InstallationDownloadPath`
- `0x18001ed1a`: `UpdateUrlSetByInsider`
- `0x18001dcc4`: `OfficeMgmtCOM`
- `0x18001ea95`: `SharedComputerLicensing`
- `0x18001dad0`: `DevInstall`
- `0x18001d877`: `InstallationPath`
- `0x18001ec53`: `UpdateChannel`
- `0x18001ed7e`: `UpdatesDisabledReason`
- `0x18001eac7`: `UpdatesEnabled`
- `0x18001ea02`: `UpdateUrl`
- `0x18001e6df`: `OSPPReady`
- `0x18001ddbe`: `OutlookShareAddon`
- `0x18001de54`: `UpdateDeadlineAllowedPostpones`
- `0x18001deb8`: `RegisterOEMPlugin`
- `0x18001ebef`: `SCLCacheOverride`
- `0x18001da6c`: `InstallID`
- `0x18001dc60`: `PreviousServiceName`
- `0x18001dc92`: `PreviousServiceRestoreBlocked`
- `0x18001db02`: `SkipStreamFileCompression`
- `0x18001eb5d`: `UpdateDeadline`
- `0x18001dd28`: `PackageLockerPath`
- `0x18001ed4c`: `UnmanagedUpdateUrl`
- `0x18001ec85`: `UpdateChannelChanged`
- `0x18001dc2e`: `PreviousClientPath`
- `0x18001dbca`: `UpdateDeadlineCountdown`
- `0x18001eb2b`: `UpdateToVersion`
- `0x18001eaf9`: `UpdatesFromAdminSource`
- `0x18001ec21`: `SCLCacheOverrideDirectory`

## pseudocode

```c
// Hidden C++ exception states: #wind=375
_QWORD *__fastcall C2R::ConfigurationSettings::ConfigurationSettings(_QWORD *a1)
{
  _QWORD *v2; // rax
  _QWORD v4[2]; // [rsp+28h] [rbp-E0h] BYREF
  _QWORD v5[2]; // [rsp+38h] [rbp-D0h] BYREF
  _QWORD v6[64]; // [rsp+48h] [rbp-C0h] BYREF
  _QWORD v7[2]; // [rsp+250h] [rbp+148h] BYREF
  __int64 v8; // [rsp+260h] [rbp+158h]
  __int64 v9; // [rsp+268h] [rbp+160h]
  _QWORD v10[2]; // [rsp+270h] [rbp+168h] BYREF
  __int64 v11; // [rsp+280h] [rbp+178h]
  __int64 v12; // [rsp+288h] [rbp+180h]
  _QWORD v13[2]; // [rsp+290h] [rbp+188h] BYREF
  __int64 v14; // [rsp+2A0h] [rbp+198h]
  __int64 v15; // [rsp+2A8h] [rbp+1A0h]
  _QWORD v16[2]; // [rsp+2B0h] [rbp+1A8h] BYREF
  __int64 v17; // [rsp+2C0h] [rbp+1B8h]
  __int64 v18; // [rsp+2C8h] [rbp+1C0h]
  _QWORD v19[2]; // [rsp+2D0h] [rbp+1C8h] BYREF
  __int64 v20; // [rsp+2E0h] [rbp+1D8h]
  __int64 v21; // [rsp+2E8h] [rbp+1E0h]
  _QWORD v22[2]; // [rsp+2F0h] [rbp+1E8h] BYREF
  __int64 v23; // [rsp+300h] [rbp+1F8h]
  __int64 v24; // [rsp+308h] [rbp+200h]
  _QWORD v25[2]; // [rsp+310h] [rbp+208h] BYREF
  __int64 v26; // [rsp+320h] [rbp+218h]
  __int64 v27; // [rsp+328h] [rbp+220h]
  _QWORD v28[2]; // [rsp+330h] [rbp+228h] BYREF
  __int64 v29; // [rsp+340h] [rbp+238h]
  __int64 v30; // [rsp+348h] [rbp+240h]
  _QWORD v31[4]; // [rsp+350h] [rbp+248h] BYREF
  _QWORD v32[2]; // [rsp+370h] [rbp+268h] BYREF
  __int64 v33; // [rsp+380h] [rbp+278h]
  __int64 v34; // [rsp+388h] [rbp+280h]
  _QWORD v35[2]; // [rsp+390h] [rbp+288h] BYREF
  __int64 v36; // [rsp+3A0h] [rbp+298h]
  __int64 v37; // [rsp+3A8h] [rbp+2A0h]
  _QWORD v38[2]; // [rsp+3B0h] [rbp+2A8h] BYREF
  __int64 v39; // [rsp+3C0h] [rbp+2B8h]
  __int64 v40; // [rsp+3C8h] [rbp+2C0h]
  _QWORD v41[2]; // [rsp+3D0h] [rbp+2C8h] BYREF
  __int64 v42; // [rsp+3E0h] [rbp+2D8h]
  __int64 v43; // [rsp+3E8h] [rbp+2E0h]
  _QWORD v44[2]; // [rsp+3F0h] [rbp+2E8h] BYREF
  __int64 v45; // [rsp+400h] [rbp+2F8h]
  __int64 v46; // [rsp+408h] [rbp+300h]
  _QWORD v47[2]; // [rsp+410h] [rbp+308h] BYREF
  __int64 v48; // [rsp+420h] [rbp+318h]
  __int64 v49; // [rsp+428h] [rbp+320h]
  _QWORD v50[2]; // [rsp+430h] [rbp+328h] BYREF
  __int64 v51; // [rsp+440h] [rbp+338h]
  __int64 v52; // [rsp+448h] [rbp+340h]
  _QWORD v53[2]; // [rsp+450h] [rbp+348h] BYREF
  __int64 v54; // [rsp+460h] [rbp+358h]
  __int64 v55; // [rsp+468h] [rbp+360h]
  _QWORD v56[2]; // [rsp+470h] [rbp+368h] BYREF
  __int64 v57; // [rsp+480h] [rbp+378h]
  __int64 v58; // [rsp+488h] [rbp+380h]
  _QWORD v59[2]; // [rsp+490h] [rbp+388h] BYREF
  __int64 v60; // [rsp+4A0h] [rbp+398h]
  __int64 v61; // [rsp+4A8h] [rbp+3A0h]
  _QWORD v62[4]; // [rsp+4B0h] [rbp+3A8h] BYREF
  _QWORD v63[4]; // [rsp+4D0h] [rbp+3C8h] BYREF
  _QWORD v64[4]; // [rsp+4F0h] [rbp+3E8h] BYREF
  _QWORD v65[4]; // [rsp+510h] [rbp+408h] BYREF
  _QWORD v66[4]; // [rsp+530h] [rbp+428h] BYREF
  _QWORD v67[4]; // [rsp+550h] [rbp+448h] BYREF
  _QWORD v68[4]; // [rsp+570h] [rbp+468h] BYREF
  _QWORD v69[4]; // [rsp+590h] [rbp+488h] BYREF
  _QWORD v70[4]; // [rsp+5B0h] [rbp+4A8h] BYREF
  _QWORD v71[4]; // [rsp+5D0h] [rbp+4C8h] BYREF
  _QWORD v72[4]; // [rsp+5F0h] [rbp+4E8h] BYREF
  _QWORD v73[4]; // [rsp+610h] [rbp+508h] BYREF
  _QWORD v74[4]; // [rsp+630h] [rbp+528h] BYREF
  _QWORD v75[4]; // [rsp+650h] [rbp+548h] BYREF
  _QWORD v76[4]; // [rsp+670h] [rbp+568h] BYREF
  _QWORD v77[4]; // [rsp+690h] [rbp+588h] BYREF
  _QWORD v78[5]; // [rsp+6B0h] [rbp+5A8h] BYREF
  int v79; // [rsp+6D8h] [rbp+5D0h] BYREF
  _BYTE v80[32]; // [rsp+6E0h] [rbp+5D8h] BYREF
  int v81; // [rsp+700h] [rbp+5F8h]
  _BYTE v82[32]; // [rsp+708h] [rbp+600h] BYREF
  int v83; // [rsp+728h] [rbp+620h]
  _BYTE v84[32]; // [rsp+730h] [rbp+628h] BYREF
  int v85; // [rsp+750h] [rbp+648h]
  _BYTE v86[32]; // [rsp+758h] [rbp+650h] BYREF
  int v87; // [rsp+778h] [rbp+670h]
  _BYTE v88[32]; // [rsp+780h] [rbp+678h] BYREF
  int v89; // [rsp+7A0h] [rbp+698h]
  _BYTE v90[32]; // [rsp+7A8h] [rbp+6A0h] BYREF
  int v91; // [rsp+7C8h] [rbp+6C0h]
  _BYTE v92[32]; // [rsp+7D0h] [rbp+6C8h] BYREF
  int v93; // [rsp+7F0h] [rbp+6E8h] BYREF
  _BYTE v94[32]; // [rsp+7F8h] [rbp+6F0h] BYREF
  int v95; // [rsp+818h] [rbp+710h]
  _BYTE v96[32]; // [rsp+820h] [rbp+718h] BYREF
  int v97; // [rsp+840h] [rbp+738h]
  _BYTE v98[32]; // [rsp+848h] [rbp+740h] BYREF
  int v99; // [rsp+868h] [rbp+760h]
  _BYTE v100[32]; // [rsp+870h] [rbp+768h] BYREF
  int v101; // [rsp+890h] [rbp+788h]
  _BYTE v102[32]; // [rsp+898h] [rbp+790h] BYREF
  int v103; // [rsp+8B8h] [rbp+7B0h]
  _BYTE v104[32]; // [rsp+8C0h] [rbp+7B8h] BYREF
  int v105; // [rsp+8E0h] [rbp+7D8h]
  _BYTE v106[32]; // [rsp+8E8h] [rbp+7E0h] BYREF
  int v107; // [rsp+908h] [rbp+800h]
  _BYTE v108[32]; // [rsp+910h] [rbp+808h] BYREF
  int v109; // [rsp+930h] [rbp+828h]
  _BYTE v110[32]; // [rsp+938h] [rbp+830h] BYREF
  int v111; // [rsp+958h] [rbp+850h]
  _BYTE v112[32]; // [rsp+960h] [rbp+858h] BYREF
  int v113; // [rsp+980h] [rbp+878h]
  _BYTE v114[32]; // [rsp+988h] [rbp+880h] BYREF
  int v115; // [rsp+9A8h] [rbp+8A0h]
  _BYTE v116[32]; // [rsp+9B0h] [rbp+8A8h] BYREF
  int v117; // [rsp+9D0h] [rbp+8C8h] BYREF
  _BYTE v118[32]; // [rsp+9D8h] [rbp+8D0h] BYREF
  int v119; // [rsp+9F8h] [rbp+8F0h]
  _BYTE v120[32]; // [rsp+A00h] [rbp+8F8h] BYREF
  int v121; // [rsp+A20h] [rbp+918h]
  _BYTE v122[32]; // [rsp+A28h] [rbp+920h] BYREF
  int v123; // [rsp+A48h] [rbp+940h]
  _BYTE v124[32]; // [rsp+A50h] [rbp+948h] BYREF
  int v125; // [rsp+A70h] [rbp+968h]
  _BYTE v126[32]; // [rsp+A78h] [rbp+970h] BYREF
  int v127; // [rsp+A98h] [rbp+990h]
  _BYTE v128[32]; // [rsp+AA0h] [rbp+998h] BYREF
  int v129; // [rsp+AC0h] [rbp+9B8h]
  _BYTE v130[32]; // [rsp+AC8h] [rbp+9C0h] BYREF
  int v131; // [rsp+AE8h] [rbp+9E0h]
  _BYTE v132[32]; // [rsp+AF0h] [rbp+9E8h] BYREF
  int v133; // [rsp+B10h] [rbp+A08h]
  _BYTE v134[32]; // [rsp+B18h] [rbp+A10h] BYREF
  int v135; // [rsp+B38h] [rbp+A30h]
  _BYTE v136[32]; // [rsp+B40h] [rbp+A38h] BYREF
  int v137; // [rsp+B60h] [rbp+A58h]
  _BYTE v138[32]; // [rsp+B68h] [rbp+A60h] BYREF
  int v139; // [rsp+B88h] [rbp+A80h]
  _BYTE v140[32]; // [rsp+B90h] [rbp+A88h] BYREF
  int v141; // [rsp+BB0h] [rbp+AA8h]
  _BYTE v142[32]; // [rsp+BB8h] [rbp+AB0h] BYREF
  int v143; // [rsp+BD8h] [rbp+AD0h]
  _BYTE v144[32]; // [rsp+BE0h] [rbp+AD8h] BYREF
  int v145; // [rsp+C00h] [rbp+AF8h]
  _BYTE v146[32]; // [rsp+C08h] [rbp+B00h] BYREF
  int v147; // [rsp+C28h] [rbp+B20h]
  _BYTE v148[32]; // [rsp+C30h] [rbp+B28h] BYREF
  int v149; // [rsp+C50h] [rbp+B48h]
  _BYTE v150[32]; // [rsp+C58h] [rbp+B50h] BYREF
  __int64 v151; // [rsp+C78h] [rbp+B70h] BYREF

  v6[2] = a1;
  C2R::Settings<enum C2R::ConfigurationSettingTypes,enum C2R::ConfigurationVersionSettingTypes>::Settings<enum C2R::ConfigurationSettingTypes,enum C2R::ConfigurationVersionSettingTypes>();
  *a1 = &C2R::ConfigurationSettings::`vftable';
  v6[3] = a1 + 7;
  v6[4] = a1 + 7;
  a1[7] = 0;
  a1[8] = 0;
  v2 = std::_Default_allocate_traits::_Allocate(0x48u);
  *v2 = v2;
  v2[1] = v2;
  v2[2] = v2;
  *((_WORD *)v2 + 12) = 257;
  a1[7] = v2;
  std::wstring::wstring(v25, L"WatcherInterval");
  v79 = 0;
  std::wstring::wstring(v80, v25);
  std::wstring::wstring(v22, L"PipelineServerName");
  v81 = 1;
  std::wstring::wstring(v82, v22);
  std::wstring::wstring(v19, L"InstallationPath");
  v83 = 2;
  std::wstring::wstring(v84, v19);
  std::wstring::wstring(v16, L"InstallationDownloadPath");
  v85 = 3;
  std::wstring::wstring(v86, v16);
  std::wstring::wstring(v13, L"ClientFolder");
  v87 = 4;
  std::wstring::wstring(v88, v13);
  std::wstring::wstring(v10, L"ClientCulture");
  v89 = 5;
  std::wstring::wstring(v90, v10);
  std::wstring::wstring(v7, L"Platform");
  v91 = 6;
  std::wstring::wstring(v92, v7);
  std::wstring::wstring(v59, L"RSODReset");
  v93 = 7;
  std::wstring::wstring(v94, v59);
  std::wstring::wstring(v56, L"recoverydata");
  v95 = 8;
  std::wstring::wstring(v96, v56);
  std::wstring::wstring(v53, L"ProductKeys");
  v97 = 9;
  std::wstring::wstring(v98, v53);
  std::wstring::wstring(v50, L"Activate");
  v99 = 10;
  std::wstring::wstring(v100, v50);
  std::wstring::wstring(v32, L"TimerInterval");
  v101 = 11;
  std::wstring::wstring(v102, v32);
  std::wstring::wstring(v47, L"InstallID");
  v103 = 12;
  std::wstring::wstring(v104, v47);
  std::wstring::wstring(v44, L"Flavor");
  v105 = 13;
  std::wstring::wstring(v106, v44);
  std::wstring::wstring(v41, L"DevInstall");
  v107 = 14;
  std::wstring::wstring(v108, v41);
  std::wstring::wstring(v38, L"SkipStreamFileCompression");
  v109 = 15;
  std::wstring::wstring(v110, v38);
  std::wstring::wstring(v35, L"ClientVersionToReport");
  v111 = 16;
  std::wstring::wstring(v112, v35);
  std::wstring::wstring(v28, L"ClientXnoneVersion");
  v113 = 17;
  std::wstring::wstring(v114, v28);
  std::wstring::wstring(v31, L"ClientXnoneHash");
  v115 = 18;
  std::wstring::wstring(v116, v31);
  std::wstring::wstring(v77, L"UpdateDeadlineCountdown");
  v117 = 19;
  std::wstring::wstring(v118, v77);
  std::wstring::wstring(v76, L"ScenarioCulture");
  v119 = 20;
  std::wstring::wstring(v120, v76);
  std::wstring::wstring(v75, L"PreviousClientPath");
  v121 = 21;
  std::wstring::wstring(v122, v75);
  std::wstring::wstring(v74, L"PreviousServiceName");
  v123 = 22;
  std::wstring::wstring(v124, v74);
  std::wstring::wstring(v67, L"PreviousServiceRestoreBlocked");
  v125 = 23;
  std::wstring::wstring(v126, v67);
  std::wstring::wstring(v73, L"OfficeMgmtCOM");
  v127 = 24;
  std::wstring::wstring(v128, v73);
  std::wstring::wstring(v72, L"AllowCdnFallback");
  v129 = 25;
  std::wstring::wstring(v130, v72);
  std::wstring::wstring(v71, L"PackageLockerPath");
  v131 = 26;
  std::wstring::wstring(v132, v71);
  std::wstring::wstring(v70, L"OfficeHelperAddon");
  v133 = 27;
  std::wstring::wstring(v134, v70);
  std::wstring::wstring(v69, L"OneDriveClientAddon");
  v135 = 28;
  std::wstring::wstring(v136, v69);
  std::wstring::wstring(v68, L"OutlookShareAddon");
  v137 = 29;
  std::wstring::wstring(v138, v68);
  std::wstring::wstring(v66, L"VCRedistAddon");
  v139 = 30;
  std::wstring::wstring(v140, v66);
  std::wstring::wstring(v65, L"BlockVersion");
  v141 = 31;
  std::wstring::wstring(v142, v65);
  std::wstring::wstring(v64, L"UpdateDeadlineAllowedPostpones");
  v143 = 32;
  std::wstring::wstring(v144, v64);
  std::wstring::wstring(v63, L"OfficeWDAGInUse");
  v145 = 33;
  std::wstring::wstring(v146, v63);
  std::wstring::wstring(v62, L"RegisterOEMPlugin");
  v147 = 34;
  std::wstring::wstring(v148, v62);
  std::wstring::wstring(v78, L"DeployedInAuditMode");
  v149 = 35;
  std::wstring::wstring(v150, v78);
  v4[0] = &v79;
  v4[1] = &v151;
  std::map<enum C2R::ConfigurationSettingTypes,std::wstring>::operator=(a1 + 1, v4);
  `eh vector destructor iterator'(
    &v79,
    0x28u,
    0x24u,
    std::pair<enum C2R::ConfigurationVersionSettingTypes const,std::wstring>::~pair<enum C2R::ConfigurationVersionSettingTypes const,std::wstring>);
  std::wstring::_Tidy_deallocate(v78);
  v6[5] = v78;
  v78[0] = 19937;
  v78[2] = 0;
  v78[3] = 15;
  std::wstring::_Tidy_deallocate(v62);
  v6[6] = v62;
  v62[0] = 19937;
  v62[2] = 0;
  v62[3] = 15;
  std::wstring::_Tidy_deallocate(v63);
  v6[7] = v63;
  v63[0] = 19937;
  v63[2] = 0;
  v63[3] = 15;
  std::wstring::_Tidy_deallocate(v64);
  v6[8] = v64;
  v64[0] = 19937;
  v64[2] = 0;
  v64[3] = 15;
  std::wstring::_Tidy_deallocate(v65);
  v6[9] = v65;
  v65[0] = 19937;
  v65[2] = 0;
  v65[3] = 15;
  std::wstring::_Tidy_deallocate(v66);
  v6[10] = v66;
  v66[0] = 19937;
  v66[2] = 0;
  v66[3] = 15;
  std::wstring::_Tidy_deallocate(v68);
  v6[11] = v68;
  v68[0] = 19937;
  v68[2] = 0;
  v68[3] = 15;
  std::wstring::_Tidy_deallocate(v69);
  v6[12] = v69;
  v69[0] = 19937;
  v69[2] = 0;
  v69[3] = 15;
  std::wstring::_Tidy_deallocate(v70);
  v6[13] = v70;
  v70[0] = 19937;
  v70[2] = 0;
  v70[3] = 15;
  std::wstring::_Tidy_deallocate(v71);
  v6[14] = v71;
  v71[0] = 19937;
  v71[2] = 0;
  v71[3] = 15;
  std::wstring::_Tidy_deallocate(v72);
  v6[15] = v72;
  v72[0] = 19937;
  v72[2] = 0;
  v72[3] = 15;
  std::wstring::_Tidy_deallocate(v73);
  v6[16] = v73;
  v73[0] = 19937;
  v73[2] = 0;
  v73[3] = 15;
  std::wstring::_Tidy_deallocate(v67);
  v6[17] = v67;
  v67[0] = 19937;
  v67[2] = 0;
  v67[3] = 15;
  std::wstring::_Tidy_deallocate(v74);
  v6[18] = v74;
  v74[0] = 19937;
  v74[2] = 0;
  v74[3] = 15;
  std::wstring::_Tidy_deallocate(v75);
  v6[19] = v75;
  v75[0] = 19937;
  v75[2] = 0;
  v75[3] = 15;
  std::wstring::_Tidy_deallocate(v76);
  v6[20] = v76;
  v76[0] = 19937;
  v76[2] = 0;
  v76[3] = 15;
  std::wstring::_Tidy_deallocate(v77);
  v6[21] = v77;
  v77[0] = 19937;
  v77[2] = 0;
  v77[3] = 15;
  std::wstring::_Tidy_deallocate(v31);
  v6[22] = v31;
  v31[0] = 19937;
  v31[2] = 0;
  v31[3] = 15;
  std::wstring::_Tidy_deallocate(v28);
  v6[23] = v28;
  v28[0] = 19937;
  v29 = 0;
  v30 = 15;
  std::wstring::_Tidy_deallocate(v35);
  v6[24] = v35;
  v35[0] = 19937;
  v36 = 0;
  v37 = 15;
  std::wstring::_Tidy_deallocate(v38);
  v6[25] = v38;
  v38[0] = 19937;
  v39 = 0;
  v40 = 15;
  std::wstring::_Tidy_deallocate(v41);
  v6[26] = v41;
  v41[0] = 19937;
  v42 = 0;
  v43 = 15;
  std::wstring::_Tidy_deallocate(v44);
  v6[27] = v44;
  v44[0] = 19937;
  v45 = 0;
  v46 = 15;
  std::wstring::_Tidy_deallocate(v47);
  v6[28] = v47;
  v47[0] = 19937;
  v48 = 0;
  v49 = 15;
  std::wstring::_Tidy_deallocate(v32);
  v6[29] = v32;
  v32[0] = 19937;
  v33 = 0;
  v34 = 15;
  std::wstring::_Tidy_deallocate(v50);
  v6[30] = v50;
  v50[0] = 19937;
  v51 = 0;
  v52 = 15;
  std::wstring::_Tidy_deallocate(v53);
  v6[31] = v53;
  v53[0] = 19937;
  v54 = 0;
  v55 = 15;
  std::wstring::_Tidy_deallocate(v56);
  v6[32] = v56;
  v56[0] = 19937;
  v57 = 0;
  v58 = 15;
  std::wstring::_Tidy_deallocate(v59);
  v6[33] = v59;
  v59[0] = 19937;
  v60 = 0;
  v61 = 15;
  std::wstring::_Tidy_deallocate(v7);
  v6[34] = v7;
  v7[0] = 19937;
  v8 = 0;
  v9 = 15;
  std::wstring::_Tidy_deallocate(v10);
  v6[35] = v10;
  v10[0] = 19937;
  v11 = 0;
  v12 = 15;
  std::wstring::_Tidy_deallocate(v13);
  v6[36] = v13;
  v13[0] = 19937;
  v14 = 0;
  v15 = 15;
  std::wstring::_Tidy_deallocate(v16);
  v6[37] = v16;
  v16[0] = 19937;
  v17 = 0;
  v18 = 15;
  std::wstring::_Tidy_deallocate(v19);
  v6[38] = v19;
  v19[0] = 19937;
  v20 = 0;
  v21 = 15;
  std::wstring::_Tidy_deallocate(v22);
  v6[39] = v22;
  v22[0] = 19937;
  v23 = 0;
  v24 = 15;
  std::wstring::_Tidy_deallocate(v25);
  v6[0] = v25;
  v25[0] = 19937;
  v26 = 0;
  v27 = 15;
  std::wstring::wstring(v7, L"OSPPReady");
  v79 = 0;
  std::wstring::wstring(v80, v7);
  std::wstring::wstring(v10, L"MediaType");
  v81 = 1;
  std::wstring::wstring(v82, v10);
  std::wstring::wstring(v13, L"ExcludedApps");
  v83 = 2;
  std::wstring::wstring(v84, v13);
  std::wstring::wstring(v16, L"EmailAddress");
  v85 = 3;
  std::wstring::wstring(v86, v16);
  std::wstring::wstring(v19, L"TenantId");
  v87 = 4;
  std::wstring::wstring(v88, v19);
  std::wstring::wstring(v22, L"OneNoteInUse");
  v89 = 5;
  std::wstring::wstring(v90, v22);
  std::wstring::wstring(v25, L"DeviceBasedLicensing");
  v91 = 6;
  std::wstring::wstring(v92, v25);
  v6[0] = &v79;
  v6[1] = &v93;
  std::map<enum C2R::ConfigurationWildcardSettingTypes,std::wstring>::operator=(a1 + 7, v6);
  `eh vector destructor iterator'(
    &v79,
    0x28u,
    7u,
    std::pair<enum C2R::ConfigurationVersionSettingTypes const,std::wstring>::~pair<enum C2R::ConfigurationVersionSettingTypes const,std::wstring>);
  std::wstring::_Tidy_deallocate(v25);
  v6[40] = v25;
  v25[0] = 19937;
  v26 = 0;
  v27 = 15;
  std::wstring::_Tidy_deallocate(v22);
  v6[41] = v22;
  v22[0] = 19937;
  v23 = 0;
  v24 = 15;
  std::wstring::_Tidy_deallocate(v19);
  v6[42] = v19;
  v19[0] = 19937;
  v20 = 0;
  v21 = 15;
  std::wstring::_Tidy_deallocate(v16);
  v6[43] = v16;
  v16[0] = 19937;
  v17 = 0;
  v18 = 15;
  std::wstring::_Tidy_deallocate(v13);
  v6[44] = v13;
  v13[0] = 19937;
  v14 = 0;
  v15 = 15;
  std::wstring::_Tidy_deallocate(v10);
  v6[45] = v10;
  v10[0] = 19937;
  v11 = 0;
  v12 = 15;
  std::wstring::_Tidy_deallocate(v7);
  v5[0] = v7;
  v7[0] = 19937;
  v8 = 0;
  v9 = 15;
  std::wstring::wstring(v31, L"UpdateUrl");
  v79 = 1;
  std::wstring::wstring(v80, v31);
  std::wstring::wstring(v28, L"ProductReleaseIds");
  v81 = 2;
  std::wstring::wstring(v82, v28);
  std::wstring::wstring(v35, L"CDNBaseUrl");
  v83 = 0;
  std::wstring::wstring(v84, v35);
  std::wstring::wstring(v38, L"SharedComputerLicensing");
  v85 = 3;
  std::wstring::wstring(v86, v38);
  std::wstring::wstring(v41, L"UpdatesEnabled");
  v87 = 4;
  std::wstring::wstring(v88, v41);
  std::wstring::wstring(v44, L"UpdatesFromAdminSource");
  v89 = 5;
  std::wstring::wstring(v90, v44);
  std::wstring::wstring(v47, L"UpdateToVersion");
  v91 = 6;
  std::wstring::wstring(v92, v47);
  std::wstring::wstring(v32, L"UpdateDeadline");
  v93 = 7;
  std::wstring::wstring(v94, v32);
  std::wstring::wstring(v50, L"VersionToReport");
  v95 = 8;
  std::wstring::wstring(v96, v50);
  std::wstring::wstring(v53, L"HosterIdentity");
  v97 = 9;
  std::wstring::wstring(v98, v53);
  std::wstring::wstring(v56, L"SCLCacheOverride");
  v99 = 10;
  std::wstring::wstring(v100, v56);
  std::wstring::wstring(v59, L"SCLCacheOverrideDirectory");
  v101 = 11;
  std::wstring::wstring(v102, v59);
  std::wstring::wstring(v7, L"UpdateChannel");
  v103 = 12;
  std::wstring::wstring(v104, v7);
  std::wstring::wstring(v10, L"UpdateChannelChanged");
  v105 = 13;
  std::wstring::wstring(v106, v10);
  std::wstring::wstring(v13, L"AudienceId");
  v107 = 14;
  std::wstring::wstring(v108, v13);
  std::wstring::wstring(v16, L"AudienceData");
  v109 = 15;
  std::wstring::wstring(v110, v16);
  std::wstring::wstring(v19, L"UpdateUrlSetByInsider");
  v111 = 16;
  std::wstring::wstring(v112, v19);
  std::wstring::wstring(v22, L"UnmanagedUpdateUrl");
  v113 = 17;
  std::wstring::wstring(v114, v22);
  std::wstring::wstring(v25, L"UpdatesDisabledReason");
  v115 = 18;
  std::wstring::wstring(v116, v25);
  v5[0] = &v79;
  v5[1] = &v117;
  std::map<enum C2R::ConfigurationVersionSettingTypes,std::wstring>::operator=(a1 + 3, v5);
  `eh vector destructor iterator'(
    &v79,
    0x28u,
    0x13u,
    std::pair<enum C2R::ConfigurationVersionSettingTypes const,std::wstring>::~pair<enum C2R::ConfigurationVersionSettingTypes const,std::wstring>);
  std::wstring::_Tidy_deallocate(v25);
  v6[46] = v25;
  v25[0] = 19937;
  v26 = 0;
  v27 = 15;
  std::wstring::_Tidy_deallocate(v22);
  v6[47] = v22;
  v22[0] = 19937;
  v23 = 0;
  v24 = 15;
  std::wstring::_Tidy_deallocate(v19);
  v6[48] = v19;
  v19[0] = 19937;
  v20 = 0;
  v21 = 15;
  std::wstring::_Tidy_deallocate(v16);
  v6[49] = v16;
  v16[0] = 19937;
  v17 = 0;
  v18 = 15;
  std::wstring::_Tidy_deallocate(v13);
  v6[50] = v13;
  v13[0] = 19937;
  v14 = 0;
  v15 = 15;
  std::wstring::_Tidy_deallocate(v10);
  v6[51] = v10;
  v10[0] = 19937;
  v11 = 0;
  v12 = 15;
  std::wstring::_Tidy_deallocate(v7);
  v6[52] = v7;
  v7[0] = 19937;
  v8 = 0;
  v9 = 15;
  std::wstring::_Tidy_deallocate(v59);
  v6[53] = v59;
  v59[0] = 19937;
  v60 = 0;
  v61 = 15;
  std::wstring::_Tidy_deallocate(v56);
  v6[54] = v56;
  v56[0] = 19937;
  v57 = 0;
  v58 = 15;
  std::wstring::_Tidy_deallocate(v53);
  v6[55] = v53;
  v53[0] = 19937;
  v54 = 0;
  v55 = 15;
  std::wstring::_Tidy_deallocate(v50);
  v6[56] = v50;
  v50[0] = 19937;
  v51 = 0;
  v52 = 15;
  std::wstring::_Tidy_deallocate(v32);
  v6[57] = v32;
  v32[0] = 19937;
  v33 = 0;
  v34 = 15;
  std::wstring::_Tidy_deallocate(v47);
  v6[58] = v47;
  v47[0] = 19937;
  v48 = 0;
  v49 = 15;
  std::wstring::_Tidy_deallocate(v44);
  v6[59] = v44;
  v44[0] = 19937;
  v45 = 0;
  v46 = 15;
  std::wstring::_Tidy_deallocate(v41);
  v6[60] = v41;
  v41[0] = 19937;
  v42 = 0;
  v43 = 15;
  std::wstring::_Tidy_deallocate(v38);
  v6[61] = v38;
  v38[0] = 19937;
  v39 = 0;
  v40 = 15;
  std::wstring::_Tidy_deallocate(v35);
  v6[62] = v35;
  v35[0] = 19937;
  v36 = 0;
  v37 = 15;
  std::wstring::_Tidy_deallocate(v28);
  v6[63] = v28;
  v28[0] = 19937;
  v29 = 0;
  v30 = 15;
  std::wstring::_Tidy_deallocate(v31);
  return a1;
}

```

## disassembly

```asm
0x18001d794  mov     rax, rsp
0x18001d797  mov     [rax+10h], rbx
0x18001d79b  mov     [rax+18h], rsi
0x18001d79f  mov     [rax+20h], rdi
0x18001d7a3  push    rbp
0x18001d7a4  push    r13
0x18001d7a6  push    r14
0x18001d7a8  lea     rbp, [rax-0B98h]
0x18001d7af  sub     rsp, 0C80h
0x18001d7b6  mov     rax, cs:__security_cookie
0x18001d7bd  xor     rax, rsp
0x18001d7c0  mov     [rbp+0B90h+var_20], rax
0x18001d7c7  mov     rdi, rcx
0x18001d7ca  mov     [rsp+0C90h+var_C40], rcx
0x18001d7cf  call    ??0?$Settings@W4ConfigurationSettingTypes@C2R@@W4ConfigurationVersionSettingTypes@2@@C2R@@QEAA@W4REGKEY_ACCESS_MODE@ORegistry@@@Z; C2R::Settings<C2R::ConfigurationSettingTypes,C2R::ConfigurationVersionSettingTypes>::Settings<C2R::ConfigurationSettingTypes,C2R::ConfigurationVersionSettingTypes>(ORegistry::REGKEY_ACCESS_MODE)
0x18001d7d4  nop
0x18001d7d5  lea     rax, ??_7ConfigurationSettings@C2R@@6B@; const C2R::ConfigurationSettings::`vftable'
0x18001d7dc  mov     [rdi], rax
0x18001d7df  lea     rbx, [rdi+38h]
0x18001d7e3  mov     [rsp+0C90h+var_C38], rbx
0x18001d7e8  mov     [rsp+0C90h+var_C30], rbx
0x18001d7ed  mov     [rsp+0C90h+var_C70], rbx
0x18001d7f2  xor     esi, esi
0x18001d7f4  mov     [rbx], rsi
0x18001d7f7  mov     [rbx+8], rsi
0x18001d7fb  lea     ecx, [rsi+48h]; unsigned __int64
0x18001d7fe  call    ?_Allocate@_Default_allocate_traits@std@@SAPEAX_K@Z; std::_Default_allocate_traits::_Allocate(unsigned __int64)
0x18001d803  mov     [rax], rax
0x18001d806  mov     [rax+8], rax
0x18001d80a  mov     [rax+10h], rax
0x18001d80e  mov     word ptr [rax+18h], 101h
0x18001d814  mov     [rbx], rax
0x18001d817  lea     rdx, aWatcherinterva; "WatcherInterval"
0x18001d81e  lea     rcx, [rbp+0B90h+var_988]
0x18001d825  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001d82a  nop
0x18001d82b  mov     [rbp+0B90h+var_5C0], esi
0x18001d831  lea     rdx, [rbp+0B90h+var_988]
0x18001d838  lea     rcx, [rbp+0B90h+var_5B8]
0x18001d83f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001d844  nop
0x18001d845  lea     rdx, aPipelineserver; "PipelineServerName"
0x18001d84c  lea     rcx, [rbp+0B90h+var_9A8]
0x18001d853  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001d858  nop
0x18001d859  mov     [rbp+0B90h+var_598], 1
0x18001d863  lea     rdx, [rbp+0B90h+var_9A8]
0x18001d86a  lea     rcx, [rbp+0B90h+var_590]
0x18001d871  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001d876  nop
0x18001d877  lea     rdx, aInstallationpa; "InstallationPath"
0x18001d87e  lea     rcx, [rbp+0B90h+var_9C8]
0x18001d885  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001d88a  nop
0x18001d88b  lea     r13d, [rsi+2]
0x18001d88f  mov     [rbp+0B90h+var_570], r13d
0x18001d896  lea     rdx, [rbp+0B90h+var_9C8]
0x18001d89d  lea     rcx, [rbp+0B90h+var_568]
0x18001d8a4  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001d8a9  nop
0x18001d8aa  lea     rdx, aInstallationdo; "InstallationDownloadPath"
0x18001d8b1  lea     rcx, [rbp+0B90h+var_9E8]
0x18001d8b8  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001d8bd  nop
0x18001d8be  mov     [rbp+0B90h+var_548], 3
0x18001d8c8  lea     rdx, [rbp+0B90h+var_9E8]
0x18001d8cf  lea     rcx, [rbp+0B90h+var_540]
0x18001d8d6  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001d8db  nop
0x18001d8dc  lea     rdx, aClientfolder; "ClientFolder"
0x18001d8e3  lea     rcx, [rbp+0B90h+var_A08]
0x18001d8ea  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001d8ef  nop
0x18001d8f0  mov     [rbp+0B90h+var_520], 4
0x18001d8fa  lea     rdx, [rbp+0B90h+var_A08]
0x18001d901  lea     rcx, [rbp+0B90h+var_518]
0x18001d908  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001d90d  nop
0x18001d90e  lea     rdx, aClientculture; "ClientCulture"
0x18001d915  lea     rcx, [rbp+0B90h+var_A28]
0x18001d91c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001d921  nop
0x18001d922  mov     [rbp+0B90h+var_4F8], 5
0x18001d92c  lea     rdx, [rbp+0B90h+var_A28]
0x18001d933  lea     rcx, [rbp+0B90h+var_4F0]
0x18001d93a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001d93f  nop
0x18001d940  lea     rdx, aPlatform; "Platform"
0x18001d947  lea     rcx, [rbp+0B90h+var_A48]
0x18001d94e  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001d953  nop
0x18001d954  mov     [rbp+0B90h+var_4D0], 6
0x18001d95e  lea     rdx, [rbp+0B90h+var_A48]
0x18001d965  lea     rcx, [rbp+0B90h+var_4C8]
0x18001d96c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001d971  nop
0x18001d972  lea     rdx, aRsodreset; "RSODReset"
0x18001d979  lea     rcx, [rbp+0B90h+var_808]
0x18001d980  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001d985  nop
0x18001d986  mov     [rbp+0B90h+var_4A8], 7
0x18001d990  lea     rdx, [rbp+0B90h+var_808]
0x18001d997  lea     rcx, [rbp+0B90h+var_4A0]
0x18001d99e  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001d9a3  nop
0x18001d9a4  lea     rdx, aRecoverydata; "recoverydata"
0x18001d9ab  lea     rcx, [rbp+0B90h+var_828]
0x18001d9b2  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001d9b7  nop
0x18001d9b8  mov     [rbp+0B90h+var_480], 8
0x18001d9c2  lea     rdx, [rbp+0B90h+var_828]
0x18001d9c9  lea     rcx, [rbp+0B90h+var_478]
0x18001d9d0  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001d9d5  nop
0x18001d9d6  lea     rdx, aProductkeys; "ProductKeys"
0x18001d9dd  lea     rcx, [rbp+0B90h+var_848]
0x18001d9e4  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001d9e9  nop
0x18001d9ea  mov     [rbp+0B90h+var_458], 9
0x18001d9f4  lea     rdx, [rbp+0B90h+var_848]
0x18001d9fb  lea     rcx, [rbp+0B90h+var_450]
0x18001da02  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001da07  nop
0x18001da08  lea     rdx, aActivate; "Activate"
0x18001da0f  lea     rcx, [rbp+0B90h+var_868]
0x18001da16  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001da1b  nop
0x18001da1c  mov     [rbp+0B90h+var_430], 0Ah
0x18001da26  lea     rdx, [rbp+0B90h+var_868]
0x18001da2d  lea     rcx, [rbp+0B90h+var_428]
0x18001da34  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001da39  nop
0x18001da3a  lea     rdx, aTimerinterval; "TimerInterval"
0x18001da41  lea     rcx, [rbp+0B90h+var_928]
0x18001da48  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001da4d  nop
0x18001da4e  mov     [rbp+0B90h+var_408], 0Bh
0x18001da58  lea     rdx, [rbp+0B90h+var_928]
0x18001da5f  lea     rcx, [rbp+0B90h+var_400]
0x18001da66  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001da6b  nop
0x18001da6c  lea     rdx, aInstallid; "InstallID"
0x18001da73  lea     rcx, [rbp+0B90h+var_888]
0x18001da7a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001da7f  nop
0x18001da80  mov     [rbp+0B90h+var_3E0], 0Ch
0x18001da8a  lea     rdx, [rbp+0B90h+var_888]
0x18001da91  lea     rcx, [rbp+0B90h+var_3D8]
0x18001da98  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001da9d  nop
0x18001da9e  lea     rdx, aFlavor; "Flavor"
0x18001daa5  lea     rcx, [rbp+0B90h+var_8A8]
0x18001daac  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001dab1  nop
0x18001dab2  mov     [rbp+0B90h+var_3B8], 0Dh
0x18001dabc  lea     rdx, [rbp+0B90h+var_8A8]
0x18001dac3  lea     rcx, [rbp+0B90h+var_3B0]
0x18001daca  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001dacf  nop
0x18001dad0  lea     rdx, aDevinstall; "DevInstall"
0x18001dad7  lea     rcx, [rbp+0B90h+var_8C8]
0x18001dade  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001dae3  nop
0x18001dae4  mov     [rbp+0B90h+var_390], 0Eh
0x18001daee  lea     rdx, [rbp+0B90h+var_8C8]
0x18001daf5  lea     rcx, [rbp+0B90h+var_388]
0x18001dafc  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001db01  nop
0x18001db02  lea     rdx, aSkipstreamfile; "SkipStreamFileCompression"
0x18001db09  lea     rcx, [rbp+0B90h+var_8E8]
0x18001db10  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001db15  nop
0x18001db16  mov     [rbp+0B90h+var_368], 0Fh
0x18001db20  lea     rdx, [rbp+0B90h+var_8E8]
0x18001db27  lea     rcx, [rbp+0B90h+var_360]
0x18001db2e  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001db33  nop
0x18001db34  lea     rdx, aClientversiont; "ClientVersionToReport"
0x18001db3b  lea     rcx, [rbp+0B90h+var_908]
0x18001db42  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001db47  nop
0x18001db48  mov     [rbp+0B90h+var_340], 10h
0x18001db52  lea     rdx, [rbp+0B90h+var_908]
0x18001db59  lea     rcx, [rbp+0B90h+var_338]
0x18001db60  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001db65  nop
0x18001db66  lea     rdx, aClientxnonever; "ClientXnoneVersion"
0x18001db6d  lea     rcx, [rbp+0B90h+var_968]
0x18001db74  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001db79  nop
0x18001db7a  mov     [rbp+0B90h+var_318], 11h
0x18001db84  lea     rdx, [rbp+0B90h+var_968]
0x18001db8b  lea     rcx, [rbp+0B90h+var_310]
0x18001db92  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001db97  nop
0x18001db98  lea     rdx, aClientxnonehas; "ClientXnoneHash"
0x18001db9f  lea     rcx, [rbp+0B90h+var_948]
0x18001dba6  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001dbab  nop
0x18001dbac  mov     [rbp+0B90h+var_2F0], 12h
0x18001dbb6  lea     rdx, [rbp+0B90h+var_948]
0x18001dbbd  lea     rcx, [rbp+0B90h+var_2E8]
0x18001dbc4  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001dbc9  nop
0x18001dbca  lea     rdx, aUpdatedeadline_0; "UpdateDeadlineCountdown"
0x18001dbd1  lea     rcx, [rbp+0B90h+var_608]
0x18001dbd8  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001dbdd  nop
0x18001dbde  mov     [rbp+0B90h+var_2C8], 13h
0x18001dbe8  lea     rdx, [rbp+0B90h+var_608]
0x18001dbef  lea     rcx, [rbp+0B90h+var_2C0]
0x18001dbf6  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001dbfb  nop
0x18001dbfc  lea     rdx, aScenariocultur; "ScenarioCulture"
0x18001dc03  lea     rcx, [rbp+0B90h+var_628]
0x18001dc0a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001dc0f  nop
0x18001dc10  mov     [rbp+0B90h+var_2A0], 14h
0x18001dc1a  lea     rdx, [rbp+0B90h+var_628]
0x18001dc21  lea     rcx, [rbp+0B90h+var_298]
0x18001dc28  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001dc2d  nop
0x18001dc2e  lea     rdx, aPreviousclient; "PreviousClientPath"
0x18001dc35  lea     rcx, [rbp+0B90h+var_648]
0x18001dc3c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001dc41  nop
0x18001dc42  mov     [rbp+0B90h+var_278], 15h
0x18001dc4c  lea     rdx, [rbp+0B90h+var_648]
0x18001dc53  lea     rcx, [rbp+0B90h+var_270]
0x18001dc5a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001dc5f  nop
0x18001dc60  lea     rdx, aPreviousservic_0; "PreviousServiceName"
0x18001dc67  lea     rcx, [rbp+0B90h+var_668]
0x18001dc6e  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001dc73  nop
0x18001dc74  mov     [rbp+0B90h+var_250], 16h
0x18001dc7e  lea     rdx, [rbp+0B90h+var_668]
0x18001dc85  lea     rcx, [rbp+0B90h+var_248]
0x18001dc8c  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001dc91  nop
0x18001dc92  lea     rdx, aPreviousservic; "PreviousServiceRestoreBlocked"
0x18001dc99  lea     rcx, [rbp+0B90h+var_748]
0x18001dca0  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001dca5  nop
0x18001dca6  mov     [rbp+0B90h+var_228], 17h
0x18001dcb0  lea     rdx, [rbp+0B90h+var_748]
0x18001dcb7  lea     rcx, [rbp+0B90h+var_220]
0x18001dcbe  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001dcc3  nop
0x18001dcc4  lea     rdx, aOfficemgmtcom; "OfficeMgmtCOM"
0x18001dccb  lea     rcx, [rbp+0B90h+var_688]
0x18001dcd2  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001dcd7  nop
0x18001dcd8  mov     [rbp+0B90h+var_200], 18h
0x18001dce2  lea     rdx, [rbp+0B90h+var_688]
0x18001dce9  lea     rcx, [rbp+0B90h+var_1F8]
0x18001dcf0  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001dcf5  nop
0x18001dcf6  lea     rdx, aAllowcdnfallba; "AllowCdnFallback"
0x18001dcfd  lea     rcx, [rbp+0B90h+var_6A8]
0x18001dd04  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001dd09  nop
0x18001dd0a  mov     [rbp+0B90h+var_1D8], 19h
0x18001dd14  lea     rdx, [rbp+0B90h+var_6A8]
0x18001dd1b  lea     rcx, [rbp+0B90h+var_1D0]
0x18001dd22  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001dd27  nop
0x18001dd28  lea     rdx, aPackagelockerp; "PackageLockerPath"
0x18001dd2f  lea     rcx, [rbp+0B90h+var_6C8]
0x18001dd36  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001dd3b  nop
0x18001dd3c  mov     [rbp+0B90h+var_1B0], 1Ah
0x18001dd46  lea     rdx, [rbp+0B90h+var_6C8]
0x18001dd4d  lea     rcx, [rbp+0B90h+var_1A8]
0x18001dd54  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001dd59  nop
0x18001dd5a  lea     rdx, aOfficehelperad; "OfficeHelperAddon"
0x18001dd61  lea     rcx, [rbp+0B90h+var_6E8]
0x18001dd68  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001dd6d  nop
0x18001dd6e  mov     [rbp+0B90h+var_188], 1Bh
0x18001dd78  lea     rdx, [rbp+0B90h+var_6E8]
0x18001dd7f  lea     rcx, [rbp+0B90h+var_180]
0x18001dd86  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001dd8b  nop
0x18001dd8c  lea     rdx, aOnedriveclient; "OneDriveClientAddon"
0x18001dd93  lea     rcx, [rbp+0B90h+var_708]
0x18001dd9a  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001dd9f  nop
0x18001dda0  mov     [rbp+0B90h+var_160], 1Ch
0x18001ddaa  lea     rdx, [rbp+0B90h+var_708]
0x18001ddb1  lea     rcx, [rbp+0B90h+var_158]
0x18001ddb8  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001ddbd  nop
0x18001ddbe  lea     rdx, aOutlooksharead; "OutlookShareAddon"
0x18001ddc5  lea     rcx, [rbp+0B90h+var_728]
0x18001ddcc  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18001ddd1  nop
0x18001ddd2  mov     [rbp+0B90h+var_138], 1Dh
0x18001dddc  lea     rdx, [rbp+0B90h+var_728]
  ... truncated ...
```
