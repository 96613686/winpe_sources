# _dynamic_initializer_for__HWSecurityRegistryManager::m_RegKeyTable__

- ea: `0x1800031b0`
- end: `0x180003f09`
- name: `_dynamic_initializer_for__HWSecurityRegistryManager::m_RegKeyTable__`
- size: `3417`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800031b0`
- `0x180006330`
- `0x180006378`
- `0x1800067d4`
- `0x18000682c`
- `0x180017488`
- `0x18001dbac`
- `0x18001dc0c`
- `0x18001e3ec`
- `0x18001e6b0`
- `0x18001e940`

## string_xrefs

- `0x1800032e3`: `System\CurrentControlSet\Services\TPM\WMI`
- `0x1800033a2`: `System\CurrentControlSet\Services`
- `0x180003463`: `System\CurrentControlSet\Services\TPM`
- `0x1800035df`: `System\CurrentControlSet\Services\TPM`
- `0x1800038bf`: `TaskStates`
- `0x180003817`: `System\CurrentControlSet\Services\TPM\WMI\HealthCert`
- `0x18000398f`: `System\CurrentControlSet\Services\TPM\WMI\TaskStates`
- `0x180003b07`: `System\CurrentControlSet\Services\TPM\WMI\Endorsement`
- `0x180003d3d`: `System\CurrentControlSet\Control\IntegrityServices`

## pseudocode

```c
// Hidden C++ exception states: #wind=96
int dynamic_initializer_for__HWSecurityRegistryManager::m_RegKeyTable__()
{
  __int64 v0; // rsi
  __int64 v1; // rdi
  __int64 v2; // rbx
  __int64 v3; // rax
  __int64 v4; // rsi
  __int64 v5; // rdi
  __int64 v6; // rbx
  __int64 v7; // rax
  __int64 v8; // rsi
  __int64 v9; // rdi
  __int64 v10; // rbx
  __int64 v11; // rax
  __int64 v12; // rsi
  __int64 v13; // rdi
  __int64 v14; // rbx
  __int64 v15; // rax
  __int64 v16; // rsi
  __int64 v17; // rdi
  __int64 v18; // rbx
  __int64 v19; // rax
  __int64 v20; // rsi
  __int64 v21; // rdi
  __int64 v22; // rbx
  __int64 v23; // rax
  __int64 v24; // rsi
  __int64 v25; // rdi
  __int64 v26; // rbx
  __int64 v27; // rax
  __int64 v28; // rsi
  __int64 v29; // rdi
  __int64 v30; // rbx
  __int64 v31; // rax
  __int64 v32; // rsi
  __int64 v33; // rdi
  __int64 v34; // rbx
  __int64 v35; // rax
  __int64 v36; // rsi
  __int64 v37; // rdi
  __int64 v38; // rbx
  __int64 v39; // rax
  __int64 v40; // rsi
  __int64 v41; // rdi
  __int64 v42; // rbx
  __int64 v43; // rax
  __int64 v44; // rsi
  __int64 v45; // rdi
  __int64 v46; // rbx
  __int64 v47; // rax
  __int64 v48; // rsi
  __int64 v49; // rdi
  __int64 v50; // rbx
  __int64 v51; // rax
  __int64 v52; // rsi
  __int64 v53; // rdi
  __int64 v54; // rbx
  __int64 v55; // rax
  __int64 v56; // rsi
  __int64 v57; // rdi
  __int64 v58; // rbx
  __int64 v59; // rax
  __int64 v60; // rsi
  __int64 v61; // rdi
  __int64 v62; // rbx
  __int64 v63; // rax
  __int64 v64; // rcx
  _QWORD *v65; // rdi
  __int64 *v66; // rbx
  int v68; // [rsp+60h] [rbp-A0h] BYREF
  int v69; // [rsp+64h] [rbp-9Ch] BYREF
  int v70; // [rsp+68h] [rbp-98h] BYREF
  int v71; // [rsp+6Ch] [rbp-94h] BYREF
  int v72; // [rsp+70h] [rbp-90h] BYREF
  int v73; // [rsp+74h] [rbp-8Ch] BYREF
  int v74; // [rsp+78h] [rbp-88h] BYREF
  int v75; // [rsp+7Ch] [rbp-84h] BYREF
  int v76; // [rsp+80h] [rbp-80h] BYREF
  int v77; // [rsp+84h] [rbp-7Ch] BYREF
  int v78; // [rsp+88h] [rbp-78h] BYREF
  int v79; // [rsp+8Ch] [rbp-74h] BYREF
  int v80; // [rsp+90h] [rbp-70h] BYREF
  int v81; // [rsp+94h] [rbp-6Ch] BYREF
  int v82; // [rsp+98h] [rbp-68h] BYREF
  int v83; // [rsp+9Ch] [rbp-64h] BYREF
  _BYTE v84[32]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v85[32]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v86[32]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v87[32]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v88[32]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v89[32]; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v90[32]; // [rsp+160h] [rbp+60h] BYREF
  _BYTE v91[32]; // [rsp+180h] [rbp+80h] BYREF
  _BYTE v92[32]; // [rsp+1A0h] [rbp+A0h] BYREF
  _BYTE v93[32]; // [rsp+1C0h] [rbp+C0h] BYREF
  _BYTE v94[32]; // [rsp+1E0h] [rbp+E0h] BYREF
  _BYTE v95[32]; // [rsp+200h] [rbp+100h] BYREF
  _BYTE v96[32]; // [rsp+220h] [rbp+120h] BYREF
  _BYTE v97[32]; // [rsp+240h] [rbp+140h] BYREF
  _BYTE v98[32]; // [rsp+260h] [rbp+160h] BYREF
  _BYTE v99[32]; // [rsp+280h] [rbp+180h] BYREF
  _BYTE v100[32]; // [rsp+2A0h] [rbp+1A0h] BYREF
  _BYTE v101[32]; // [rsp+2C0h] [rbp+1C0h] BYREF
  _BYTE v102[32]; // [rsp+2E0h] [rbp+1E0h] BYREF
  _BYTE v103[32]; // [rsp+300h] [rbp+200h] BYREF
  _BYTE v104[32]; // [rsp+320h] [rbp+220h] BYREF
  _BYTE v105[32]; // [rsp+340h] [rbp+240h] BYREF
  _BYTE v106[32]; // [rsp+360h] [rbp+260h] BYREF
  _BYTE v107[32]; // [rsp+380h] [rbp+280h] BYREF
  _BYTE v108[32]; // [rsp+3A0h] [rbp+2A0h] BYREF
  _BYTE v109[32]; // [rsp+3C0h] [rbp+2C0h] BYREF
  _BYTE v110[32]; // [rsp+3E0h] [rbp+2E0h] BYREF
  _BYTE v111[32]; // [rsp+400h] [rbp+300h] BYREF
  _BYTE v112[32]; // [rsp+420h] [rbp+320h] BYREF
  _BYTE v113[32]; // [rsp+440h] [rbp+340h] BYREF
  _BYTE v114[32]; // [rsp+460h] [rbp+360h] BYREF
  _BYTE v115[32]; // [rsp+480h] [rbp+380h] BYREF
  _BYTE v116[32]; // [rsp+4A0h] [rbp+3A0h] BYREF
  _BYTE v117[32]; // [rsp+4C0h] [rbp+3C0h] BYREF
  _BYTE v118[32]; // [rsp+4E0h] [rbp+3E0h] BYREF
  _BYTE v119[32]; // [rsp+500h] [rbp+400h] BYREF
  _BYTE v120[32]; // [rsp+520h] [rbp+420h] BYREF
  _BYTE v121[32]; // [rsp+540h] [rbp+440h] BYREF
  _BYTE v122[32]; // [rsp+560h] [rbp+460h] BYREF
  _BYTE v123[32]; // [rsp+580h] [rbp+480h] BYREF
  _BYTE v124[32]; // [rsp+5A0h] [rbp+4A0h] BYREF
  _BYTE v125[32]; // [rsp+5C0h] [rbp+4C0h] BYREF
  _BYTE v126[32]; // [rsp+5E0h] [rbp+4E0h] BYREF
  _BYTE v127[32]; // [rsp+600h] [rbp+500h] BYREF
  _BYTE v128[32]; // [rsp+620h] [rbp+520h] BYREF
  _BYTE v129[32]; // [rsp+640h] [rbp+540h] BYREF
  _BYTE v130[32]; // [rsp+660h] [rbp+560h] BYREF
  _BYTE v131[32]; // [rsp+680h] [rbp+580h] BYREF
  _BYTE v132[32]; // [rsp+6A0h] [rbp+5A0h] BYREF
  _BYTE v133[32]; // [rsp+6C0h] [rbp+5C0h] BYREF
  _BYTE v134[32]; // [rsp+6E0h] [rbp+5E0h] BYREF
  _BYTE v135[32]; // [rsp+700h] [rbp+600h] BYREF
  _BYTE v136[32]; // [rsp+720h] [rbp+620h] BYREF
  _BYTE v137[32]; // [rsp+740h] [rbp+640h] BYREF
  _BYTE v138[32]; // [rsp+760h] [rbp+660h] BYREF
  _BYTE v139[32]; // [rsp+780h] [rbp+680h] BYREF
  _BYTE v140[32]; // [rsp+7A0h] [rbp+6A0h] BYREF
  _BYTE v141[32]; // [rsp+7C0h] [rbp+6C0h] BYREF
  _BYTE v142[32]; // [rsp+7E0h] [rbp+6E0h] BYREF
  _BYTE v143[32]; // [rsp+800h] [rbp+700h] BYREF
  _BYTE v144[32]; // [rsp+820h] [rbp+720h] BYREF
  _BYTE v145[32]; // [rsp+840h] [rbp+740h] BYREF
  _BYTE v146[32]; // [rsp+860h] [rbp+760h] BYREF
  _BYTE v147[32]; // [rsp+880h] [rbp+780h] BYREF
  _BYTE v148[144]; // [rsp+8A0h] [rbp+7A0h] BYREF
  _BYTE v149[144]; // [rsp+930h] [rbp+830h] BYREF
  _BYTE v150[144]; // [rsp+9C0h] [rbp+8C0h] BYREF
  _BYTE v151[144]; // [rsp+A50h] [rbp+950h] BYREF
  _BYTE v152[144]; // [rsp+AE0h] [rbp+9E0h] BYREF
  _BYTE v153[144]; // [rsp+B70h] [rbp+A70h] BYREF
  _BYTE v154[144]; // [rsp+C00h] [rbp+B00h] BYREF
  _BYTE v155[144]; // [rsp+C90h] [rbp+B90h] BYREF
  _BYTE v156[144]; // [rsp+D20h] [rbp+C20h] BYREF
  _BYTE v157[144]; // [rsp+DB0h] [rbp+CB0h] BYREF
  _BYTE v158[144]; // [rsp+E40h] [rbp+D40h] BYREF
  _BYTE v159[144]; // [rsp+ED0h] [rbp+DD0h] BYREF
  _BYTE v160[144]; // [rsp+F60h] [rbp+E60h] BYREF
  _BYTE v161[144]; // [rsp+FF0h] [rbp+EF0h] BYREF
  _BYTE v162[144]; // [rsp+1080h] [rbp+F80h] BYREF
  _BYTE v163[144]; // [rsp+1110h] [rbp+1010h] BYREF
  _DWORD v164[36]; // [rsp+11A0h] [rbp+10A0h] BYREF
  _DWORD v165[36]; // [rsp+1230h] [rbp+1130h] BYREF
  _DWORD v166[36]; // [rsp+12C0h] [rbp+11C0h] BYREF
  _DWORD v167[36]; // [rsp+1350h] [rbp+1250h] BYREF
  _DWORD v168[36]; // [rsp+13E0h] [rbp+12E0h] BYREF
  _DWORD v169[36]; // [rsp+1470h] [rbp+1370h] BYREF
  _DWORD v170[36]; // [rsp+1500h] [rbp+1400h] BYREF
  _DWORD v171[36]; // [rsp+1590h] [rbp+1490h] BYREF
  _DWORD v172[36]; // [rsp+1620h] [rbp+1520h] BYREF
  _DWORD v173[36]; // [rsp+16B0h] [rbp+15B0h] BYREF
  _DWORD v174[36]; // [rsp+1740h] [rbp+1640h] BYREF
  _DWORD v175[36]; // [rsp+17D0h] [rbp+16D0h] BYREF
  _DWORD v176[36]; // [rsp+1860h] [rbp+1760h] BYREF
  _DWORD v177[36]; // [rsp+18F0h] [rbp+17F0h] BYREF
  _DWORD v178[36]; // [rsp+1980h] [rbp+1880h] BYREF
  _DWORD v179[36]; // [rsp+1A10h] [rbp+1910h] BYREF
  __int64 v180; // [rsp+1AA0h] [rbp+19A0h] BYREF

  v0 = std::wstring::wstring(v84, &qword_180024840);
  v1 = std::wstring::wstring(v85, L"TpmRegDriverGroupPolicyData");
  v2 = std::wstring::wstring(v86, L"TPM");
  v3 = std::wstring::wstring(v87, L"Software\\Policies\\Microsoft");
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry((__int64)v163, v3, v2, v1, 0, 131103, v0);
  v68 = 0;
  std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(
    v164,
    &v68,
    (const struct HWSecurityRegistryManager::RegistryKeyEntry *)v163);
  v4 = std::wstring::wstring(v88, &qword_180024840);
  v5 = std::wstring::wstring(v89, &qword_180024840);
  v6 = std::wstring::wstring(v90, L"PcrInfo");
  v7 = std::wstring::wstring(v91, L"System\\CurrentControlSet\\Services\\TPM\\WMI");
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry((__int64)v162, v7, v6, v5, 0, 131103, v4);
  v69 = 14;
  std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(
    v165,
    &v69,
    (const struct HWSecurityRegistryManager::RegistryKeyEntry *)v162);
  v8 = std::wstring::wstring(v92, &qword_180024840);
  v9 = std::wstring::wstring(v93, L"TpmRegDriverTpm");
  v10 = std::wstring::wstring(v94, L"TPM");
  v11 = std::wstring::wstring(v95, L"System\\CurrentControlSet\\Services");
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry((__int64)v161, v11, v10, v9, 0, 131103, v8);
  v70 = 1;
  std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(
    v166,
    &v70,
    (const struct HWSecurityRegistryManager::RegistryKeyEntry *)v161);
  v12 = std::wstring::wstring(v96, &qword_180024840);
  v13 = std::wstring::wstring(v97, L"TpmRegPlatformQuoteKeysKey");
  v14 = std::wstring::wstring(v98, L"PlatformQuoteKeys");
  v15 = std::wstring::wstring(v99, L"System\\CurrentControlSet\\Services\\TPM");
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry((__int64)v160, v15, v14, v13, 0, 131103, v12);
  v71 = 2;
  std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(
    v167,
    &v71,
    (const struct HWSecurityRegistryManager::RegistryKeyEntry *)v160);
  v16 = std::wstring::wstring(v100, &qword_180024840);
  v17 = std::wstring::wstring(v101, L"TpmRegProvisioningKey");
  v18 = std::wstring::wstring(v102, L"ProvisionInfo");
  v19 = std::wstring::wstring(v103, L"System\\CurrentControlSet\\Services\\TPM\\WMI");
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry((__int64)v159, v19, v18, v17, 0, 131103, v16);
  v72 = 3;
  std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(
    v168,
    &v72,
    (const struct HWSecurityRegistryManager::RegistryKeyEntry *)v159);
  v20 = std::wstring::wstring(
          v104,
          L"O:SYD:AIAR(A;;KR;;;AU)(A;CIIO;GR;;;AU)(A;;KR;;;S-1-15-3-9)(A;CIIO;GR;;;S-1-15-3-9)(A;;KA;;;LS)(A;CIIO;GA;;;LS)"
           "(A;;KA;;;NS)(A;CIIO;GA;;;NS)");
  v21 = std::wstring::wstring(v105, L"TpmRegDriverPersistedData");
  v22 = std::wstring::wstring(v106, L"WMI");
  v23 = std::wstring::wstring(v107, L"System\\CurrentControlSet\\Services\\TPM");
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry((__int64)v158, v23, v22, v21, 0, 131103, v20);
  v73 = 4;
  std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(
    v169,
    &v73,
    (const struct HWSecurityRegistryManager::RegistryKeyEntry *)v158);
  v24 = std::wstring::wstring(
          v108,
          L"O:SYD:PAI(A;;KA;;;BA)(A;CIIO;GA;;;BA)(A;;KA;;;SY)(A;CIIO;GA;;;SY)(A;;KA;;;LS)(A;CIIO;GA;;;LS)(A;;KA;;;NS)(A;CIIO;GA;;;NS)");
  v25 = std::wstring::wstring(v109, L"TpmRegDriverPersistedDataAdmin");
  v26 = std::wstring::wstring(v110, L"Admin");
  v27 = std::wstring::wstring(v111, L"System\\CurrentControlSet\\Services\\TPM\\WMI");
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry((__int64)v157, v27, v26, v25, 0, 131103, v24);
  v74 = 5;
  std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(
    v170,
    &v74,
    (const struct HWSecurityRegistryManager::RegistryKeyEntry *)v157);
  v28 = std::wstring::wstring(
          v112,
          L"O:SYD:PAI(A;;KA;;;BA)(A;CIIO;GA;;;BA)(A;;KA;;;SY)(A;CIIO;GA;;;SY)(A;;KA;;;LS)(A;CIIO;GA;;;LS)(A;;KA;;;NS)(A;CI"
           "IO;GA;;;NS)(A;;KR;;;S-1-15-3-9)(A;CIIO;GR;;;S-1-15-3-9)(A;;KR;;;S-1-5-4)(A;CIIO;GR;;;S-1-5-4)(A;;KR;;;S-1-5-1"
           "1)(A;CIIO;GR;;;S-1-5-11)");
  v29 = std::wstring::wstring(v113, L"TpmRegDriverPersistedDataEndorsement");
  v30 = std::wstring::wstring(v114, L"Endorsement");
  v31 = std::wstring::wstring(v115, L"System\\CurrentControlSet\\Services\\TPM\\WMI");
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry((__int64)v156, v31, v30, v29, 0, 131103, v28);
  v75 = 6;
  std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(
    v171,
    &v75,
    (const struct HWSecurityRegistryManager::RegistryKeyEntry *)v156);
  v32 = std::wstring::wstring(v116, &qword_180024840);
  v33 = std::wstring::wstring(v117, L"TPMCoreProvisioningHealthCertStore");
  v34 = std::wstring::wstring(v118, L"Store");
  v35 = std::wstring::wstring(v119, L"System\\CurrentControlSet\\Services\\TPM\\WMI\\HealthCert");
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry((__int64)v155, v35, v34, v33, 0, 131103, v32);
  v76 = 7;
  std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(
    v172,
    &v76,
    (const struct HWSecurityRegistryManager::RegistryKeyEntry *)v155);
  v36 = std::wstring::wstring(v120, &qword_180024840);
  v37 = std::wstring::wstring(v121, &qword_180024840);
  v38 = std::wstring::wstring(v122, L"TaskStates");
  v39 = std::wstring::wstring(v123, L"System\\CurrentControlSet\\Services\\TPM\\WMI");
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry((__int64)v154, v39, v38, v37, 1, 131103, v36);
  v77 = 8;
  std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(
    v173,
    &v77,
    (const struct HWSecurityRegistryManager::RegistryKeyEntry *)v154);
  v40 = std::wstring::wstring(v124, &qword_180024840);
  v41 = std::wstring::wstring(v125, &qword_180024840);
  v42 = std::wstring::wstring(v126, L"AttestationInfo");
  v43 = std::wstring::wstring(v127, L"System\\CurrentControlSet\\Services\\TPM\\WMI\\TaskStates");
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry((__int64)v153, v43, v42, v41, 1, 131103, v40);
  v78 = 9;
  std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(
    v174,
    &v78,
    (const struct HWSecurityRegistryManager::RegistryKeyEntry *)v153);
  v44 = std::wstring::wstring(v128, &qword_180024840);
  v45 = std::wstring::wstring(v129, &qword_180024840);
  v46 = std::wstring::wstring(v130, L"Volatile-AIKCertEnroll-EXCLUSIVE");
  v47 = std::wstring::wstring(v131, L"System\\CurrentControlSet\\Services\\TPM\\WMI");
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry((__int64)v152, v47, v46, v45, 1, 131103, v44);
  v79 = 10;
  std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(
    v175,
    &v79,
    (const struct HWSecurityRegistryManager::RegistryKeyEntry *)v152);
  v48 = std::wstring::wstring(v132, &qword_180024840);
  v49 = std::wstring::wstring(v133, L"TPMCoreProvisioningEKCertificates");
  v50 = std::wstring::wstring(v134, L"EkCertStore");
  v51 = std::wstring::wstring(v135, L"System\\CurrentControlSet\\Services\\TPM\\WMI\\Endorsement");
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry((__int64)v151, v51, v50, v49, 0, 983103, v48);
  v80 = 11;
  std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(
    v176,
    &v80,
    (const struct HWSecurityRegistryManager::RegistryKeyEntry *)v151);
  v52 = std::wstring::wstring(v136, &qword_180024840);
  v53 = std::wstring::wstring(v137, L"TPMCoreProvisioningEKCertificates");
  v54 = std::wstring::wstring(v138, L"EkCertStoreECC");
  v55 = std::wstring::wstring(v139, L"System\\CurrentControlSet\\Services\\TPM\\WMI\\Endorsement");
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry((__int64)v150, v55, v54, v53, 0, 983103, v52);
  v81 = 12;
  std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(
    v177,
    &v81,
    (const struct HWSecurityRegistryManager::RegistryKeyEntry *)v150);
  v56 = std::wstring::wstring(v140, &qword_180024840);
  v57 = std::wstring::wstring(v141, L"TPMCoreProvisioningIntermediateCACerts");
  v58 = std::wstring::wstring(v142, L"IntermediateCACertStore");
  v59 = std::wstring::wstring(v143, L"System\\CurrentControlSet\\Services\\TPM\\WMI\\Endorsement");
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry((__int64)v149, v59, v58, v57, 0, 983103, v56);
  v82 = 13;
  std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(
    v178,
    &v82,
    (const struct HWSecurityRegistryManager::RegistryKeyEntry *)v149);
  v60 = std::wstring::wstring(v144, &qword_180024840);
  v61 = std::wstring::wstring(v145, &qword_180024840);
  v62 = std::wstring::wstring(v146, &qword_180024840);
  v63 = std::wstring::wstring(v147, L"System\\CurrentControlSet\\Control\\IntegrityServices");
  HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry((__int64)v148, v63, v62, v61, 0, 131097, v60);
  v83 = 15;
  std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(
    v179,
    &v83,
    (const struct HWSecurityRegistryManager::RegistryKeyEntry *)v148);
  HWSecurityRegistryManager::m_RegKeyTable = 0;
  v65 = operator new(0xB0u);
  *v65 = v65;
  v65[1] = v65;
  v65[2] = v65;
  *((_WORD *)v65 + 12) = 257;
  *(_QWORD *)&HWSecurityRegistryManager::m_RegKeyTable = v65;
  v66 = (__int64 *)v164;
  do
  {
    std::_Tree<std::_Tmap_traits<enum HWSecurityRegistryManager::RegKeys,HWSecurityRegistryManager::RegistryKeyEntry,std::less<enum HWSecurityRegistryManager::RegKeys>,std::allocator<std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>>,0>>::_Emplace_hint<std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry> const &>(
      v64,
      (__int64)v65,
      (__int64)v66);
    v66 += 18;
  }
  while ( v66 != &v180 );
  `eh vector destructor iterator'(
    v164,
    0x90u,
    0x10u,
    (void (*)(void *))std::pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::~pair<enum HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>);
  HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry((HWSecurityRegistryManager::RegistryKeyEntry *)v148);
  HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry((HWSecurityRegistryManager::RegistryKeyEntry *)v149);
  HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry((HWSecurityRegistryManager::RegistryKeyEntry *)v150);
  HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry((HWSecurityRegistryManager::RegistryKeyEntry *)v151);
  HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry((HWSecurityRegistryManager::RegistryKeyEntry *)v152);
  HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry((HWSecurityRegistryManager::RegistryKeyEntry *)v153);
  HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry((HWSecurityRegistryManager::RegistryKeyEntry *)v154);
  HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry((HWSecurityRegistryManager::RegistryKeyEntry *)v155);
  HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry((HWSecurityRegistryManager::RegistryKeyEntry *)v156);
  HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry((HWSecurityRegistryManager::RegistryKeyEntry *)v157);
  HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry((HWSecurityRegistryManager::RegistryKeyEntry *)v158);
  HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry((HWSecurityRegistryManager::RegistryKeyEntry *)v159);
  HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry((HWSecurityRegistryManager::RegistryKeyEntry *)v160);
  HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry((HWSecurityRegistryManager::RegistryKeyEntry *)v161);
  HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry((HWSecurityRegistryManager::RegistryKeyEntry *)v162);
  HWSecurityRegistryManager::RegistryKeyEntry::~RegistryKeyEntry((HWSecurityRegistryManager::RegistryKeyEntry *)v163);
  return atexit(dynamic_atexit_destructor_for__HWSecurityRegistryManager::m_RegKeyTable__);
}

```

## disassembly

```asm
0x1800031b0  push    rbp
0x1800031b2  push    rbx
0x1800031b3  push    rsi
0x1800031b4  push    rdi
0x1800031b5  push    r12
0x1800031b7  push    r13
0x1800031b9  push    r14
0x1800031bb  push    r15
0x1800031bd  lea     rbp, [rsp-19B8h]
0x1800031c5  mov     eax, 1AB8h
0x1800031ca  call    _alloca_probe
0x1800031cf  sub     rsp, rax
0x1800031d2  mov     rax, cs:__security_cookie
0x1800031d9  xor     rax, rsp
0x1800031dc  mov     [rbp+19F0h+var_50], rax
0x1800031e3  lea     rax, [rbp+19F0h+var_1A50]
0x1800031e7  mov     [rsp+1AF0h+var_1AB0], rax
0x1800031ec  lea     r12, qword_180024840
0x1800031f3  mov     rdx, r12
0x1800031f6  lea     rcx, [rbp+19F0h+var_1A50]
0x1800031fa  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800031ff  mov     rsi, rax
0x180003202  lea     rax, [rbp+19F0h+var_1A30]
0x180003206  mov     [rsp+1AF0h+var_1AA8], rax
0x18000320b  lea     rdx, aTpmregdrivergr; "TpmRegDriverGroupPolicyData"
0x180003212  lea     rcx, [rbp+19F0h+var_1A30]
0x180003216  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000321b  mov     rdi, rax
0x18000321e  lea     rax, [rbp+19F0h+var_1A10]
0x180003222  mov     [rsp+1AF0h+var_1AA0], rax
0x180003227  lea     rdx, aTpm; "TPM"
0x18000322e  lea     rcx, [rbp+19F0h+var_1A10]
0x180003232  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180003237  mov     rbx, rax
0x18000323a  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft"
0x180003241  lea     rcx, [rbp+19F0h+var_19F0]
0x180003245  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000324a  nop
0x18000324b  mov     [rsp+1AF0h+var_1AC0], rsi
0x180003250  mov     r15d, 2001Fh
0x180003256  mov     [rsp+1AF0h+var_1AC8], r15d
0x18000325b  xor     r13d, r13d
0x18000325e  mov     [rsp+1AF0h+var_1AD0], r13d
0x180003263  mov     r9, rdi
0x180003266  mov     r8, rbx
0x180003269  mov     rdx, rax
0x18000326c  lea     rcx, [rbp+19F0h+var_9E0]
0x180003273  call    ??0RegistryKeyEntry@HWSecurityRegistryManager@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00KK0@Z; HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(std::wstring,std::wstring,std::wstring,ulong,ulong,std::wstring)
0x180003278  nop
0x180003279  mov     [rsp+1AF0h+var_1A90], r13d
0x18000327e  lea     r8, [rbp+19F0h+var_9E0]
0x180003285  lea     rdx, [rsp+1AF0h+var_1A90]
0x18000328a  lea     rcx, [rbp+19F0h+var_950]
0x180003291  call    ??$?0$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@1@$0A@@?$pair@$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@@std@@QEAA@AEBW4RegKeys@HWSecurityRegistryManager@@AEBVRegistryKeyEntry@3@@Z; std::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(HWSecurityRegistryManager::RegKeys const &,HWSecurityRegistryManager::RegistryKeyEntry const &)
0x180003296  nop
0x180003297  lea     rax, [rbp+19F0h+var_19D0]
0x18000329b  mov     [rsp+1AF0h+var_1A98], rax
0x1800032a0  mov     rdx, r12
0x1800032a3  lea     rcx, [rbp+19F0h+var_19D0]
0x1800032a7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800032ac  mov     rsi, rax
0x1800032af  lea     rax, [rbp+19F0h+var_19B0]
0x1800032b3  mov     [rsp+1AF0h+var_1AA0], rax
0x1800032b8  mov     rdx, r12
0x1800032bb  lea     rcx, [rbp+19F0h+var_19B0]
0x1800032bf  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800032c4  mov     rdi, rax
0x1800032c7  lea     rax, [rbp+19F0h+var_1990]
0x1800032cb  mov     [rsp+1AF0h+var_1AA8], rax
0x1800032d0  lea     rdx, aPcrinfo; "PcrInfo"
0x1800032d7  lea     rcx, [rbp+19F0h+var_1990]
0x1800032db  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800032e0  mov     rbx, rax
0x1800032e3  lea     r14, aSystemCurrentc_5; "System\\CurrentControlSet\\Services\\TP"...
0x1800032ea  mov     rdx, r14
0x1800032ed  lea     rcx, [rbp+19F0h+var_1970]
0x1800032f4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800032f9  nop
0x1800032fa  mov     [rsp+1AF0h+var_1AC0], rsi
0x1800032ff  mov     [rsp+1AF0h+var_1AC8], r15d
0x180003304  mov     [rsp+1AF0h+var_1AD0], r13d
0x180003309  mov     r9, rdi
0x18000330c  mov     r8, rbx
0x18000330f  mov     rdx, rax
0x180003312  lea     rcx, [rbp+19F0h+var_A70]
0x180003319  call    ??0RegistryKeyEntry@HWSecurityRegistryManager@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00KK0@Z; HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(std::wstring,std::wstring,std::wstring,ulong,ulong,std::wstring)
0x18000331e  nop
0x18000331f  mov     [rsp+1AF0h+var_1A8C], 0Eh
0x180003327  lea     r8, [rbp+19F0h+var_A70]
0x18000332e  lea     rdx, [rsp+1AF0h+var_1A8C]
0x180003333  lea     rcx, [rbp+19F0h+var_8C0]
0x18000333a  call    ??$?0$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@1@$0A@@?$pair@$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@@std@@QEAA@AEBW4RegKeys@HWSecurityRegistryManager@@AEBVRegistryKeyEntry@3@@Z; std::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(HWSecurityRegistryManager::RegKeys const &,HWSecurityRegistryManager::RegistryKeyEntry const &)
0x18000333f  nop
0x180003340  lea     rax, [rbp+19F0h+var_1950]
0x180003347  mov     [rsp+1AF0h+var_1A98], rax
0x18000334c  mov     rdx, r12
0x18000334f  lea     rcx, [rbp+19F0h+var_1950]
0x180003356  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000335b  mov     rsi, rax
0x18000335e  lea     rax, [rbp+19F0h+var_1930]
0x180003365  mov     [rsp+1AF0h+var_1AA0], rax
0x18000336a  lea     rdx, aTpmregdrivertp; "TpmRegDriverTpm"
0x180003371  lea     rcx, [rbp+19F0h+var_1930]
0x180003378  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000337d  mov     rdi, rax
0x180003380  lea     rax, [rbp+19F0h+var_1910]
0x180003387  mov     [rsp+1AF0h+var_1AA8], rax
0x18000338c  lea     rdx, aTpm; "TPM"
0x180003393  lea     rcx, [rbp+19F0h+var_1910]
0x18000339a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000339f  mov     rbx, rax
0x1800033a2  lea     rdx, aSystemCurrentc_6; "System\\CurrentControlSet\\Services"
0x1800033a9  lea     rcx, [rbp+19F0h+var_18F0]
0x1800033b0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800033b5  nop
0x1800033b6  mov     [rsp+1AF0h+var_1AC0], rsi
0x1800033bb  mov     [rsp+1AF0h+var_1AC8], r15d
0x1800033c0  mov     [rsp+1AF0h+var_1AD0], r13d
0x1800033c5  mov     r9, rdi
0x1800033c8  mov     r8, rbx
0x1800033cb  mov     rdx, rax
0x1800033ce  lea     rcx, [rbp+19F0h+var_B00]
0x1800033d5  call    ??0RegistryKeyEntry@HWSecurityRegistryManager@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00KK0@Z; HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(std::wstring,std::wstring,std::wstring,ulong,ulong,std::wstring)
0x1800033da  nop
0x1800033db  lea     r12d, [r13+1]
0x1800033df  mov     [rsp+1AF0h+var_1A88], r12d
0x1800033e4  lea     r8, [rbp+19F0h+var_B00]
0x1800033eb  lea     rdx, [rsp+1AF0h+var_1A88]
0x1800033f0  lea     rcx, [rbp+19F0h+var_830]
0x1800033f7  call    ??$?0$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@1@$0A@@?$pair@$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@@std@@QEAA@AEBW4RegKeys@HWSecurityRegistryManager@@AEBVRegistryKeyEntry@3@@Z; std::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(HWSecurityRegistryManager::RegKeys const &,HWSecurityRegistryManager::RegistryKeyEntry const &)
0x1800033fc  nop
0x1800033fd  lea     rax, [rbp+19F0h+var_18D0]
0x180003404  mov     [rsp+1AF0h+var_1A98], rax
0x180003409  lea     rdx, qword_180024840
0x180003410  lea     rcx, [rbp+19F0h+var_18D0]
0x180003417  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000341c  mov     rsi, rax
0x18000341f  lea     rax, [rbp+19F0h+var_18B0]
0x180003426  mov     [rsp+1AF0h+var_1AA0], rax
0x18000342b  lea     rdx, aTpmregplatform; "TpmRegPlatformQuoteKeysKey"
0x180003432  lea     rcx, [rbp+19F0h+var_18B0]
0x180003439  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000343e  mov     rdi, rax
0x180003441  lea     rax, [rbp+19F0h+var_1890]
0x180003448  mov     [rsp+1AF0h+var_1AA8], rax
0x18000344d  lea     rdx, aPlatformquotek; "PlatformQuoteKeys"
0x180003454  lea     rcx, [rbp+19F0h+var_1890]
0x18000345b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180003460  mov     rbx, rax
0x180003463  lea     rdx, aSystemCurrentc_4; "System\\CurrentControlSet\\Services\\TP"...
0x18000346a  lea     rcx, [rbp+19F0h+var_1870]
0x180003471  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180003476  nop
0x180003477  mov     [rsp+1AF0h+var_1AC0], rsi
0x18000347c  mov     [rsp+1AF0h+var_1AC8], r15d
0x180003481  mov     [rsp+1AF0h+var_1AD0], r13d
0x180003486  mov     r9, rdi
0x180003489  mov     r8, rbx
0x18000348c  mov     rdx, rax
0x18000348f  lea     rcx, [rbp+19F0h+var_B90]
0x180003496  call    ??0RegistryKeyEntry@HWSecurityRegistryManager@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00KK0@Z; HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(std::wstring,std::wstring,std::wstring,ulong,ulong,std::wstring)
0x18000349b  nop
0x18000349c  mov     [rsp+1AF0h+var_1A84], 2
0x1800034a4  lea     r8, [rbp+19F0h+var_B90]
0x1800034ab  lea     rdx, [rsp+1AF0h+var_1A84]
0x1800034b0  lea     rcx, [rbp+19F0h+var_7A0]
0x1800034b7  call    ??$?0$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@1@$0A@@?$pair@$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@@std@@QEAA@AEBW4RegKeys@HWSecurityRegistryManager@@AEBVRegistryKeyEntry@3@@Z; std::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(HWSecurityRegistryManager::RegKeys const &,HWSecurityRegistryManager::RegistryKeyEntry const &)
0x1800034bc  nop
0x1800034bd  lea     rax, [rbp+19F0h+var_1850]
0x1800034c4  mov     [rsp+1AF0h+var_1A98], rax
0x1800034c9  lea     rdx, qword_180024840
0x1800034d0  lea     rcx, [rbp+19F0h+var_1850]
0x1800034d7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800034dc  mov     rsi, rax
0x1800034df  lea     rax, [rbp+19F0h+var_1830]
0x1800034e6  mov     [rsp+1AF0h+var_1AA0], rax
0x1800034eb  lea     rdx, aTpmregprovisio; "TpmRegProvisioningKey"
0x1800034f2  lea     rcx, [rbp+19F0h+var_1830]
0x1800034f9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800034fe  mov     rdi, rax
0x180003501  lea     rax, [rbp+19F0h+var_1810]
0x180003508  mov     [rsp+1AF0h+var_1AA8], rax
0x18000350d  lea     rdx, aProvisioninfo; "ProvisionInfo"
0x180003514  lea     rcx, [rbp+19F0h+var_1810]
0x18000351b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180003520  mov     rbx, rax
0x180003523  mov     rdx, r14
0x180003526  lea     rcx, [rbp+19F0h+var_17F0]
0x18000352d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180003532  nop
0x180003533  mov     [rsp+1AF0h+var_1AC0], rsi
0x180003538  mov     [rsp+1AF0h+var_1AC8], r15d
0x18000353d  mov     [rsp+1AF0h+var_1AD0], r13d
0x180003542  mov     r9, rdi
0x180003545  mov     r8, rbx
0x180003548  mov     rdx, rax
0x18000354b  lea     rcx, [rbp+19F0h+var_C20]
0x180003552  call    ??0RegistryKeyEntry@HWSecurityRegistryManager@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00KK0@Z; HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(std::wstring,std::wstring,std::wstring,ulong,ulong,std::wstring)
0x180003557  nop
0x180003558  mov     [rsp+1AF0h+var_1A80], 3
0x180003560  lea     r8, [rbp+19F0h+var_C20]
0x180003567  lea     rdx, [rsp+1AF0h+var_1A80]
0x18000356c  lea     rcx, [rbp+19F0h+var_710]
0x180003573  call    ??$?0$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@1@$0A@@?$pair@$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@@std@@QEAA@AEBW4RegKeys@HWSecurityRegistryManager@@AEBVRegistryKeyEntry@3@@Z; std::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(HWSecurityRegistryManager::RegKeys const &,HWSecurityRegistryManager::RegistryKeyEntry const &)
0x180003578  nop
0x180003579  lea     rax, [rbp+19F0h+var_17D0]
0x180003580  mov     [rsp+1AF0h+var_1A98], rax
0x180003585  lea     rdx, aOSydAiarAKrAuA; "O:SYD:AIAR(A;;KR;;;AU)(A;CIIO;GR;;;AU)("...
0x18000358c  lea     rcx, [rbp+19F0h+var_17D0]
0x180003593  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180003598  mov     rsi, rax
0x18000359b  lea     rax, [rbp+19F0h+var_17B0]
0x1800035a2  mov     [rsp+1AF0h+var_1AA0], rax
0x1800035a7  lea     rdx, aTpmregdriverpe; "TpmRegDriverPersistedData"
0x1800035ae  lea     rcx, [rbp+19F0h+var_17B0]
0x1800035b5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800035ba  mov     rdi, rax
0x1800035bd  lea     rax, [rbp+19F0h+var_1790]
0x1800035c4  mov     [rsp+1AF0h+var_1AA8], rax
0x1800035c9  lea     rdx, aWmi; "WMI"
0x1800035d0  lea     rcx, [rbp+19F0h+var_1790]
0x1800035d7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800035dc  mov     rbx, rax
0x1800035df  lea     rdx, aSystemCurrentc_4; "System\\CurrentControlSet\\Services\\TP"...
0x1800035e6  lea     rcx, [rbp+19F0h+var_1770]
0x1800035ed  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800035f2  nop
0x1800035f3  mov     [rsp+1AF0h+var_1AC0], rsi
0x1800035f8  mov     [rsp+1AF0h+var_1AC8], r15d
0x1800035fd  mov     [rsp+1AF0h+var_1AD0], r13d
0x180003602  mov     r9, rdi
0x180003605  mov     r8, rbx
0x180003608  mov     rdx, rax
0x18000360b  lea     rcx, [rbp+19F0h+var_CB0]
0x180003612  call    ??0RegistryKeyEntry@HWSecurityRegistryManager@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00KK0@Z; HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(std::wstring,std::wstring,std::wstring,ulong,ulong,std::wstring)
0x180003617  nop
0x180003618  mov     [rsp+1AF0h+var_1A7C], 4
0x180003620  lea     r8, [rbp+19F0h+var_CB0]
0x180003627  lea     rdx, [rsp+1AF0h+var_1A7C]
0x18000362c  lea     rcx, [rbp+19F0h+var_680]
0x180003633  call    ??$?0$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@1@$0A@@?$pair@$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@@std@@QEAA@AEBW4RegKeys@HWSecurityRegistryManager@@AEBVRegistryKeyEntry@3@@Z; std::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(HWSecurityRegistryManager::RegKeys const &,HWSecurityRegistryManager::RegistryKeyEntry const &)
0x180003638  nop
0x180003639  lea     rax, [rbp+19F0h+var_1750]
0x180003640  mov     [rsp+1AF0h+var_1A98], rax
0x180003645  lea     rdx, aOSydPaiAKaBaAC; "O:SYD:PAI(A;;KA;;;BA)(A;CIIO;GA;;;BA)(A"...
0x18000364c  lea     rcx, [rbp+19F0h+var_1750]
0x180003653  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180003658  mov     rsi, rax
0x18000365b  lea     rax, [rbp+19F0h+var_1730]
0x180003662  mov     [rsp+1AF0h+var_1AA0], rax
0x180003667  lea     rdx, aTpmregdriverpe_0; "TpmRegDriverPersistedDataAdmin"
0x18000366e  lea     rcx, [rbp+19F0h+var_1730]
0x180003675  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000367a  mov     rdi, rax
0x18000367d  lea     rax, [rbp+19F0h+var_1710]
0x180003684  mov     [rsp+1AF0h+var_1AA8], rax
0x180003689  lea     rdx, aAdmin; "Admin"
0x180003690  lea     rcx, [rbp+19F0h+var_1710]
0x180003697  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000369c  mov     rbx, rax
0x18000369f  mov     rdx, r14
0x1800036a2  lea     rcx, [rbp+19F0h+var_16F0]
0x1800036a9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800036ae  nop
0x1800036af  mov     [rsp+1AF0h+var_1AC0], rsi
0x1800036b4  mov     [rsp+1AF0h+var_1AC8], r15d
0x1800036b9  mov     [rsp+1AF0h+var_1AD0], r13d
0x1800036be  mov     r9, rdi
0x1800036c1  mov     r8, rbx
0x1800036c4  mov     rdx, rax
0x1800036c7  lea     rcx, [rbp+19F0h+var_D40]
0x1800036ce  call    ??0RegistryKeyEntry@HWSecurityRegistryManager@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00KK0@Z; HWSecurityRegistryManager::RegistryKeyEntry::RegistryKeyEntry(std::wstring,std::wstring,std::wstring,ulong,ulong,std::wstring)
0x1800036d3  nop
0x1800036d4  mov     [rsp+1AF0h+var_1A78], 5
0x1800036dc  lea     r8, [rbp+19F0h+var_D40]
0x1800036e3  lea     rdx, [rsp+1AF0h+var_1A78]
0x1800036e8  lea     rcx, [rbp+19F0h+var_5F0]
0x1800036ef  call    ??$?0$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@1@$0A@@?$pair@$$CBW4RegKeys@HWSecurityRegistryManager@@VRegistryKeyEntry@2@@std@@QEAA@AEBW4RegKeys@HWSecurityRegistryManager@@AEBVRegistryKeyEntry@3@@Z; std::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>::pair<HWSecurityRegistryManager::RegKeys const,HWSecurityRegistryManager::RegistryKeyEntry>(HWSecurityRegistryManager::RegKeys const &,HWSecurityRegistryManager::RegistryKeyEntry const &)
0x1800036f4  nop
0x1800036f5  lea     rax, [rbp+19F0h+var_16D0]
0x1800036fc  mov     [rsp+1AF0h+var_1A98], rax
0x180003701  lea     rdx, aOSydPaiAKaBaAC_0; "O:SYD:PAI(A;;KA;;;BA)(A;CIIO;GA;;;BA)(A"...
0x180003708  lea     rcx, [rbp+19F0h+var_16D0]
0x18000370f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180003714  mov     rsi, rax
0x180003717  lea     rax, [rbp+19F0h+var_16B0]
0x18000371e  mov     [rsp+1AF0h+var_1AA0], rax
0x180003723  lea     rdx, aTpmregdriverpe_1; "TpmRegDriverPersistedDataEndorsement"
0x18000372a  lea     rcx, [rbp+19F0h+var_16B0]
0x180003731  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180003736  mov     rdi, rax
0x180003739  lea     rax, [rbp+19F0h+var_1690]
0x180003740  mov     [rsp+1AF0h+var_1AA8], rax
0x180003745  lea     rdx, aEndorsement; "Endorsement"
0x18000374c  lea     rcx, [rbp+19F0h+var_1690]
0x180003753  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180003758  mov     rbx, rax
0x18000375b  mov     rdx, r14
0x18000375e  lea     rcx, [rbp+19F0h+var_1670]
0x180003765  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
  ... truncated ...
```
