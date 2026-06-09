# CiInstrumentSiPolicyInfo

- ea: `0x180066330`
- end: `0x180067b46`
- name: `CiInstrumentSiPolicyInfo`
- size: `6166`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18006b780`

## callees

- `0x180001008`
- `0x18000f3bc`
- `0x18000fb30`
- `0x18001d2f8`
- `0x18001d350`
- `0x18002bef0`
- `0x1800585d8`
- `0x180066330`
- `0x18006bd24`
- `0x1800714cc`
- `0x180078398`
- `0x180079120`
- `0x18007ba9c`
- `0x18009f370`
- `0x1800e18f8`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x18006793d`
- `ntoskrnl!RtlFreeUnicodeString` at `0x180067955`
- `ntoskrnl!RtlFreeUnicodeString` at `0x180067965`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1800679b5`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1800679c5`
- `ntoskrnl!RtlFreeUnicodeString` at `0x18006793d`
- `ntoskrnl!RtlFreeUnicodeString` at `0x180067955`
- `ntoskrnl!RtlFreeUnicodeString` at `0x180067965`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1800679b5`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1800679c5`
- `ntoskrnl!RtlInitUnicodeString` at `0x18006761e`
- `ntoskrnl!RtlInitUnicodeString` at `0x180067635`
- `ntoskrnl!RtlInitUnicodeString` at `0x18006761e`
- `ntoskrnl!RtlInitUnicodeString` at `0x180067635`
- `ntoskrnl!ExFreePoolWithTag` at `0x18006799d`
- `ntoskrnl!ExFreePoolWithTag` at `0x18006799d`

## string_xrefs

- `0x180066444`: `\Registry\MACHINE\System\CurrentControlSet\Control\CI`
- `0x180066420`: `\Registry\MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Update\TargetingInfo\PersistentDynamicInstalled\RevocationList.amd64`
- `0x180066439`: `RevocationUpdateVersion`

## pseudocode

```c
__int64 __fastcall CiInstrumentSiPolicyInfo(char a1, const GUID *a2, const GUID *a3, char a4)
{
  unsigned int v5; // edi
  char v8; // si
  __int64 v9; // rdx
  __int64 v10; // rdx
  __int64 v11; // rdx
  char v12; // al
  int v13; // r15d
  __int64 v14; // rdx
  int v15; // edx
  int v16; // r14d
  __int64 v17; // rcx
  __int64 v18; // rcx
  int IsEnabledDeviceUsageNoInline; // eax
  __int64 v20; // rdx
  __int64 v21; // rcx
  __int64 v22; // r8
  PVOID v23; // r14
  unsigned int v24; // r9d
  int v25; // eax
  unsigned __int8 *v26; // rdx
  __int64 v27; // r10
  unsigned int v28; // ebx
  __int64 v29; // rdi
  unsigned __int64 v30; // r14
  unsigned int v31; // r9d
  int PolicyOptionsV2; // eax
  __int64 v33; // rdx
  __int64 v34; // r9
  __int64 v35; // rcx
  __int64 v36; // r9
  __int64 v37; // rcx
  int v38; // eax
  __int64 v39; // rcx
  bool v40; // cf
  bool v41; // zf
  unsigned int v42; // edx
  USHORT Length; // cx
  PWSTR v44; // rax
  char v45; // al
  ULONG v47; // [rsp+20h] [rbp-E0h]
  char IsPolicyActive; // [rsp+30h] [rbp-D0h] BYREF
  char v49; // [rsp+31h] [rbp-CFh] BYREF
  char v50; // [rsp+32h] [rbp-CEh] BYREF
  char v51; // [rsp+33h] [rbp-CDh] BYREF
  char v52; // [rsp+34h] [rbp-CCh] BYREF
  char v53; // [rsp+35h] [rbp-CBh] BYREF
  char v54; // [rsp+36h] [rbp-CAh] BYREF
  char v55; // [rsp+37h] [rbp-C9h] BYREF
  char v56; // [rsp+38h] [rbp-C8h] BYREF
  char v57; // [rsp+39h] [rbp-C7h] BYREF
  char v58; // [rsp+3Ah] [rbp-C6h] BYREF
  char v59; // [rsp+3Bh] [rbp-C5h] BYREF
  char v60; // [rsp+3Ch] [rbp-C4h] BYREF
  char v61; // [rsp+3Dh] [rbp-C3h] BYREF
  char v62; // [rsp+3Eh] [rbp-C2h] BYREF
  char v63; // [rsp+3Fh] [rbp-C1h] BYREF
  char v64; // [rsp+40h] [rbp-C0h] BYREF
  char v65; // [rsp+41h] [rbp-BFh] BYREF
  char v66; // [rsp+42h] [rbp-BEh] BYREF
  char v67; // [rsp+43h] [rbp-BDh] BYREF
  char v68; // [rsp+44h] [rbp-BCh] BYREF
  char v69; // [rsp+45h] [rbp-BBh] BYREF
  char v70; // [rsp+46h] [rbp-BAh] BYREF
  char v71; // [rsp+47h] [rbp-B9h] BYREF
  char v72; // [rsp+48h] [rbp-B8h] BYREF
  char v73; // [rsp+49h] [rbp-B7h] BYREF
  char v74; // [rsp+4Ah] [rbp-B6h] BYREF
  char v75; // [rsp+4Bh] [rbp-B5h] BYREF
  char v76; // [rsp+4Ch] [rbp-B4h] BYREF
  char v77; // [rsp+4Dh] [rbp-B3h] BYREF
  char v78; // [rsp+4Eh] [rbp-B2h] BYREF
  char v79; // [rsp+4Fh] [rbp-B1h] BYREF
  char v80; // [rsp+50h] [rbp-B0h] BYREF
  char v81; // [rsp+51h] [rbp-AFh] BYREF
  char v82; // [rsp+52h] [rbp-AEh] BYREF
  char v83; // [rsp+53h] [rbp-ADh] BYREF
  char v84; // [rsp+54h] [rbp-ACh] BYREF
  char v85; // [rsp+55h] [rbp-ABh]
  char v86; // [rsp+56h] [rbp-AAh]
  bool v87; // [rsp+57h] [rbp-A9h]
  bool v88; // [rsp+58h] [rbp-A8h] BYREF
  char IsBasePolicy; // [rsp+59h] [rbp-A7h]
  char v90; // [rsp+5Ah] [rbp-A6h] BYREF
  char IsLegacyPolicyID; // [rsp+5Bh] [rbp-A5h]
  char v92; // [rsp+5Ch] [rbp-A4h] BYREF
  bool v93; // [rsp+5Dh] [rbp-A3h] BYREF
  char v94; // [rsp+5Eh] [rbp-A2h]
  int v95; // [rsp+60h] [rbp-A0h] BYREF
  int v96; // [rsp+64h] [rbp-9Ch] BYREF
  int v97; // [rsp+68h] [rbp-98h] BYREF
  int v98; // [rsp+6Ch] [rbp-94h] BYREF
  int v99; // [rsp+70h] [rbp-90h] BYREF
  __int64 v100; // [rsp+78h] [rbp-88h] BYREF
  PVOID P; // [rsp+80h] [rbp-80h] BYREF
  int v102; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v103; // [rsp+8Ch] [rbp-74h] BYREF
  int v104; // [rsp+90h] [rbp-70h]
  int v105; // [rsp+94h] [rbp-6Ch] BYREF
  int v106; // [rsp+98h] [rbp-68h]
  int v107; // [rsp+9Ch] [rbp-64h] BYREF
  int v108; // [rsp+A0h] [rbp-60h]
  int v109; // [rsp+A4h] [rbp-5Ch] BYREF
  int v110; // [rsp+A8h] [rbp-58h] BYREF
  int v111; // [rsp+ACh] [rbp-54h]
  int v112; // [rsp+B0h] [rbp-50h]
  _QWORD v113[2]; // [rsp+B8h] [rbp-48h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+C8h] [rbp-38h] BYREF
  struct _UNICODE_STRING v115; // [rsp+D8h] [rbp-28h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v117; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v118; // [rsp+100h] [rbp+0h] BYREF
  __int64 v119; // [rsp+108h] [rbp+8h]
  __int64 v120; // [rsp+110h] [rbp+10h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v121[2]; // [rsp+120h] [rbp+20h] BYREF
  __int64 *v122; // [rsp+140h] [rbp+40h]
  __int64 v123; // [rsp+148h] [rbp+48h]
  char *v124; // [rsp+150h] [rbp+50h]
  __int64 v125; // [rsp+158h] [rbp+58h]
  int *v126; // [rsp+160h] [rbp+60h]
  __int64 v127; // [rsp+168h] [rbp+68h]
  char *v128; // [rsp+170h] [rbp+70h]
  __int64 v129; // [rsp+178h] [rbp+78h]
  char *v130; // [rsp+180h] [rbp+80h]
  __int64 v131; // [rsp+188h] [rbp+88h]
  int *v132; // [rsp+190h] [rbp+90h]
  __int64 v133; // [rsp+198h] [rbp+98h]
  char *v134; // [rsp+1A0h] [rbp+A0h]
  __int64 v135; // [rsp+1A8h] [rbp+A8h]
  char *v136; // [rsp+1B0h] [rbp+B0h]
  __int64 v137; // [rsp+1B8h] [rbp+B8h]
  char *v138; // [rsp+1C0h] [rbp+C0h]
  __int64 v139; // [rsp+1C8h] [rbp+C8h]
  char *v140; // [rsp+1D0h] [rbp+D0h]
  __int64 v141; // [rsp+1D8h] [rbp+D8h]
  char *v142; // [rsp+1E0h] [rbp+E0h]
  __int64 v143; // [rsp+1E8h] [rbp+E8h]
  char *v144; // [rsp+1F0h] [rbp+F0h]
  __int64 v145; // [rsp+1F8h] [rbp+F8h]
  char *v146; // [rsp+200h] [rbp+100h]
  __int64 v147; // [rsp+208h] [rbp+108h]
  char *v148; // [rsp+210h] [rbp+110h]
  __int64 v149; // [rsp+218h] [rbp+118h]
  char *v150; // [rsp+220h] [rbp+120h]
  __int64 v151; // [rsp+228h] [rbp+128h]
  char *v152; // [rsp+230h] [rbp+130h]
  __int64 v153; // [rsp+238h] [rbp+138h]
  char *v154; // [rsp+240h] [rbp+140h]
  __int64 v155; // [rsp+248h] [rbp+148h]
  char *v156; // [rsp+250h] [rbp+150h]
  __int64 v157; // [rsp+258h] [rbp+158h]
  char *v158; // [rsp+260h] [rbp+160h]
  __int64 v159; // [rsp+268h] [rbp+168h]
  char *v160; // [rsp+270h] [rbp+170h]
  __int64 v161; // [rsp+278h] [rbp+178h]
  char *v162; // [rsp+280h] [rbp+180h]
  __int64 v163; // [rsp+288h] [rbp+188h]
  char *v164; // [rsp+290h] [rbp+190h]
  __int64 v165; // [rsp+298h] [rbp+198h]
  char *v166; // [rsp+2A0h] [rbp+1A0h]
  __int64 v167; // [rsp+2A8h] [rbp+1A8h]
  char *v168; // [rsp+2B0h] [rbp+1B0h]
  __int64 v169; // [rsp+2B8h] [rbp+1B8h]
  char *v170; // [rsp+2C0h] [rbp+1C0h]
  __int64 v171; // [rsp+2C8h] [rbp+1C8h]
  char *v172; // [rsp+2D0h] [rbp+1D0h]
  __int64 v173; // [rsp+2D8h] [rbp+1D8h]
  char *v174; // [rsp+2E0h] [rbp+1E0h]
  __int64 v175; // [rsp+2E8h] [rbp+1E8h]
  char *v176; // [rsp+2F0h] [rbp+1F0h]
  __int64 v177; // [rsp+2F8h] [rbp+1F8h]
  char *v178; // [rsp+300h] [rbp+200h]
  __int64 v179; // [rsp+308h] [rbp+208h]
  char *v180; // [rsp+310h] [rbp+210h]
  __int64 v181; // [rsp+318h] [rbp+218h]
  char *v182; // [rsp+320h] [rbp+220h]
  __int64 v183; // [rsp+328h] [rbp+228h]
  char *v184; // [rsp+330h] [rbp+230h]
  __int64 v185; // [rsp+338h] [rbp+238h]
  char *v186; // [rsp+340h] [rbp+240h]
  __int64 v187; // [rsp+348h] [rbp+248h]
  char *v188; // [rsp+350h] [rbp+250h]
  __int64 v189; // [rsp+358h] [rbp+258h]
  char *v190; // [rsp+360h] [rbp+260h]
  __int64 v191; // [rsp+368h] [rbp+268h]
  char *v192; // [rsp+370h] [rbp+270h]
  __int64 v193; // [rsp+378h] [rbp+278h]
  char *v194; // [rsp+380h] [rbp+280h]
  __int64 v195; // [rsp+388h] [rbp+288h]
  char *v196; // [rsp+390h] [rbp+290h]
  __int64 v197; // [rsp+398h] [rbp+298h]
  char *p_IsPolicyActive; // [rsp+3A0h] [rbp+2A0h]
  __int64 v199; // [rsp+3A8h] [rbp+2A8h]
  __int64 *v200; // [rsp+3B0h] [rbp+2B0h]
  __int64 v201; // [rsp+3B8h] [rbp+2B8h]
  __int64 *v202; // [rsp+3C0h] [rbp+2C0h]
  __int64 v203; // [rsp+3C8h] [rbp+2C8h]
  __int64 *v204; // [rsp+3D0h] [rbp+2D0h]
  __int64 v205; // [rsp+3D8h] [rbp+2D8h]
  __int64 *v206; // [rsp+3E0h] [rbp+2E0h]
  __int64 v207; // [rsp+3E8h] [rbp+2E8h]
  __int64 *v208; // [rsp+3F0h] [rbp+2F0h]
  __int64 v209; // [rsp+3F8h] [rbp+2F8h]
  _BYTE v210[16]; // [rsp+400h] [rbp+300h] BYREF
  _BYTE v211[16]; // [rsp+410h] [rbp+310h] BYREF
  int *v212; // [rsp+420h] [rbp+320h]
  __int64 v213; // [rsp+428h] [rbp+328h]
  int *v214; // [rsp+430h] [rbp+330h]
  __int64 v215; // [rsp+438h] [rbp+338h]
  __int64 *v216; // [rsp+440h] [rbp+340h]
  __int64 v217; // [rsp+448h] [rbp+348h]
  struct _EVENT_DATA_DESCRIPTOR v218[2]; // [rsp+450h] [rbp+350h] BYREF
  _QWORD *v219; // [rsp+470h] [rbp+370h]
  __int64 v220; // [rsp+478h] [rbp+378h]
  const char *v221; // [rsp+480h] [rbp+380h]
  __int64 v222; // [rsp+488h] [rbp+388h]
  struct _EVENT_DATA_DESCRIPTOR v223; // [rsp+490h] [rbp+390h] BYREF
  __int64 *v224; // [rsp+4B0h] [rbp+3B0h]
  __int64 v225; // [rsp+4B8h] [rbp+3B8h]
  int *v226; // [rsp+4C0h] [rbp+3C0h]
  __int64 v227; // [rsp+4C8h] [rbp+3C8h]
  unsigned int *v228; // [rsp+4D0h] [rbp+3D0h]
  __int64 v229; // [rsp+4D8h] [rbp+3D8h]
  int *v230; // [rsp+4E0h] [rbp+3E0h]
  __int64 v231; // [rsp+4E8h] [rbp+3E8h]
  int *v232; // [rsp+4F0h] [rbp+3F0h]
  __int64 v233; // [rsp+4F8h] [rbp+3F8h]
  int *v234; // [rsp+500h] [rbp+400h]
  __int64 v235; // [rsp+508h] [rbp+408h]
  __int64 *v236; // [rsp+510h] [rbp+410h]
  __int64 v237; // [rsp+518h] [rbp+418h]
  int *v238; // [rsp+520h] [rbp+420h]
  __int64 v239; // [rsp+528h] [rbp+428h]
  bool *v240; // [rsp+530h] [rbp+430h]
  __int64 v241; // [rsp+538h] [rbp+438h]
  _DWORD *v242; // [rsp+540h] [rbp+440h]
  __int64 v243; // [rsp+548h] [rbp+448h]
  PWSTR Buffer; // [rsp+550h] [rbp+450h]
  _DWORD v245[2]; // [rsp+558h] [rbp+458h] BYREF
  _DWORD *v246; // [rsp+560h] [rbp+460h]
  __int64 v247; // [rsp+568h] [rbp+468h]
  PWSTR v248; // [rsp+570h] [rbp+470h]
  _DWORD v249[2]; // [rsp+578h] [rbp+478h] BYREF
  __int64 v250; // [rsp+580h] [rbp+480h]
  __int64 v251; // [rsp+588h] [rbp+488h]
  __int64 v252; // [rsp+590h] [rbp+490h]
  __int64 v253; // [rsp+598h] [rbp+498h]
  char *v254; // [rsp+5A0h] [rbp+4A0h]
  __int64 v255; // [rsp+5A8h] [rbp+4A8h]
  char *v256; // [rsp+5B0h] [rbp+4B0h]
  __int64 v257; // [rsp+5B8h] [rbp+4B8h]
  bool *v258; // [rsp+5C0h] [rbp+4C0h]
  __int64 v259; // [rsp+5C8h] [rbp+4C8h]
  _DWORD *v260; // [rsp+5D0h] [rbp+4D0h]
  __int64 v261; // [rsp+5D8h] [rbp+4D8h]
  PWSTR v262; // [rsp+5E0h] [rbp+4E0h]
  _DWORD v263[2]; // [rsp+5E8h] [rbp+4E8h] BYREF

  v86 = a1;
  v84 = 0;
  HIDWORD(v113[0]) = 0;
  v5 = 0;
  DestinationString = 0;
  v8 = 1;
  v115 = 0;
  UnicodeString = 0;
  IsPolicyActive = SIPolicyIsPolicyActive(&SiPolicyIDEModeBase, 0);
  v49 = SIPolicyIsPolicyActive(&SiPolicyIDNightsWatchDesktop, v9);
  v50 = SIPolicyIsPolicyActive(&SiPolicyIDNightsWatchDesktopEval, v10);
  v12 = SIPolicyIsPolicyActive(&qword_180032830, v11);
  v13 = g_CiOptions & 0x8000;
  v85 = v12;
  v112 = v13;
  v94 = SIPolicyIsPolicyActive(&qword_180032800, v14);
  v95 = 0;
  P = 0;
  v16 = v15 + 2;
  CipGetRegistryValue2(
    v17,
    L"\\Registry\\MACHINE\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Update\\TargetingInfo\\PersistentDynamicInstal"
     "led\\RevocationList.amd64",
    (__int64)L"Version",
    v15 + 2,
    &P,
    &v95);
  CipGetRegistryValue2(
    v18,
    L"\\Registry\\MACHINE\\System\\CurrentControlSet\\Control\\CI",
    (__int64)L"RevocationUpdateVersion",
    v16,
    &P,
    &v95);
  IsEnabledDeviceUsageNoInline = Feature_SAC_LocalLogging__private_IsEnabledDeviceUsageNoInline();
  v23 = P;
  v24 = 0;
  if ( IsEnabledDeviceUsageNoInline )
  {
    if ( (unsigned int)dword_180048128 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180048128, 0x800000000000LL) )
    {
      v117 = 2048;
      v123 = 8;
      v122 = &v117;
      v52 = IsPolicyActive;
      v124 = &v52;
      v99 = g_NumberOfSiPolicies;
      v126 = &v99;
      v51 = v49;
      v128 = &v51;
      v83 = v50;
      v130 = &v83;
      v98 = g_NightsWatchDesktopMinValueSeenDuringThisBootSession;
      v132 = &v98;
      v125 = 1;
      v82 = g_CiDeveloperMode & 1;
      v134 = &v82;
      v127 = 4;
      v81 = (g_CiDeveloperMode & 2) != 0;
      v136 = &v81;
      v129 = 1;
      v80 = (g_CiDeveloperMode & 4) != 0;
      v138 = &v80;
      v131 = 1;
      v79 = (g_CiDeveloperMode & 8) != 0;
      v140 = &v79;
      v133 = 4;
      v78 = (g_CiDeveloperMode & 0x10) != 0;
      v142 = &v78;
      v135 = 1;
      v77 = (g_CiDeveloperMode & 0x20) != 0;
      v144 = &v77;
      v137 = 1;
      v76 = (g_CiDeveloperMode & 0x40) != 0;
      v146 = &v76;
      v139 = 1;
      v141 = 1;
      v143 = 1;
      v145 = 1;
      v147 = 1;
      v149 = 1;
      v75 = (g_CiDeveloperMode & 0x80) != 0;
      v148 = &v75;
      v151 = 1;
      v74 = BYTE1(g_CiDeveloperMode) & 1;
      v150 = &v74;
      v153 = 1;
      v73 = (g_CiDeveloperMode & 0x200) != 0;
      v152 = &v73;
      v155 = 1;
      v72 = (g_CiDeveloperMode & 0x400) != 0;
      v154 = &v72;
      v157 = 1;
      v71 = (g_CiDeveloperMode & 0x800) != 0;
      v156 = &v71;
      v70 = (g_CiDeveloperMode & 0x1000) != 0;
      v69 = (g_CiDeveloperMode & 0x2000) != 0;
      v158 = &v70;
      v160 = &v69;
      v159 = 1;
      v68 = (g_CiPolicyState & 0x800000) != 0;
      v162 = &v68;
      v161 = 1;
      v67 = BYTE2(g_CiDeveloperMode) & 1;
      v164 = &v67;
      v163 = 1;
      v66 = BYTE2(g_CiPolicyState) & 1;
      v166 = &v66;
      v165 = 1;
      v65 = g_CiPolicyState & 1;
      v168 = &v65;
      v167 = 1;
      v64 = (g_CiPolicyState & 2) != 0;
      v170 = &v64;
      v169 = 1;
      v171 = 1;
      v173 = 1;
      v63 = (g_CiPolicyState & 4) != 0;
      v172 = &v63;
      v175 = 1;
      v62 = (g_CiPolicyState & 8) != 0;
      v174 = &v62;
      v177 = 1;
      v61 = (g_CiPolicyState & 0x10) != 0;
      v176 = &v61;
      v179 = 1;
      v60 = (g_CiPolicyState & 0x40) != 0;
      v178 = &v60;
      v181 = 1;
      v59 = (g_CiPolicyState & 0x20) != 0;
      v180 = &v59;
      v183 = 1;
      v58 = (g_CiPolicyState & 0x800) != 0;
      v182 = &v58;
      v185 = 1;
      v57 = (g_CiPolicyState & 0x1000) != 0;
      v184 = &v57;
      v187 = 1;
      v56 = (g_CiPolicyState & 0x2000) != 0;
      v186 = &v56;
      v189 = 1;
      v55 = (g_CiPolicyState & 0x4000) != 0;
      v188 = &v55;
      v191 = 1;
      v54 = (g_CiPolicyState & 0x8000) != 0;
      v190 = &v54;
      v53 = (g_CiPolicyState & 0x20000) != 0;
      v50 = (g_CiPolicyState & 0x80000) != 0;
      v192 = &v53;
      v194 = &v50;
      v193 = 1;
      v195 = 1;
      v197 = 1;
      v196 = &v49;
      IsPolicyActive = g_CiRevocationListInfo;
      p_IsPolicyActive = &IsPolicyActive;
      v199 = 1;
      v49 = a4;
      v200 = &qword_180048E50[g_CiRevocationListInfo];
      v201 = 8;
      v202 = qword_180048E50;
      v203 = 8;
      v204 = &qword_180048E58;
      v206 = &qword_180048E60;
      v208 = &qword_180048E68;
      v205 = 8;
      v207 = 8;
      v209 = 8;
      tlgCreate1Sz_wchar_t(v210, v23);
      tlgCreate1Sz_wchar_t(v211, 0);
      v212 = &v97;
      v26 = (unsigned __int8 *)&word_18003DF46;
      v96 = g_SmartAppControlPreviousState;
      v214 = &v96;
      v216 = &v100;
      v47 = 51;
      v97 = g_SmartAppControlEnforcementReason;
      v215 = 4;
      LODWORD(v100) = 5;
      v217 = 4;
      goto LABEL_12;
    }
  }
  else
  {
    v25 = Feature_SAC_ClientSideEnable__private_IsEnabledDeviceUsageNoInline(v21, v20, v22, 0);
    v24 = 0;
    if ( v25 )
    {
      if ( (unsigned int)dword_180048128 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180048128, 0x800000000000LL) )
      {
        v100 = 2048;
        v123 = 8;
        v122 = &v100;
        v52 = IsPolicyActive;
        v125 = 1;
        v124 = &v52;
        v98 = g_NumberOfSiPolicies;
        v126 = &v98;
        v51 = v49;
        v128 = &v51;
        v83 = v50;
        v130 = &v83;
        v97 = g_NightsWatchDesktopMinValueSeenDuringThisBootSession;
        v132 = &v97;
        v127 = 4;
        v82 = g_CiDeveloperMode & 1;
        v134 = &v82;
        v129 = 1;
        v81 = (g_CiDeveloperMode & 2) != 0;
        v136 = &v81;
        v131 = 1;
        v80 = (g_CiDeveloperMode & 4) != 0;
        v138 = &v80;
        v133 = 4;
        v79 = (g_CiDeveloperMode & 8) != 0;
        v140 = &v79;
        v135 = 1;
        v78 = (g_CiDeveloperMode & 0x10) != 0;
        v142 = &v78;
        v137 = 1;
        v77 = (g_CiDeveloperMode & 0x20) != 0;
        v144 = &v77;
        v139 = 1;
        v76 = (g_CiDeveloperMode & 0x40) != 0;
        v146 = &v76;
        v141 = 1;
        v143 = 1;
        v145 = 1;
        v147 = 1;
        v149 = 1;
        v75 = (g_CiDeveloperMode & 0x80) != 0;
        v148 = &v75;
        v151 = 1;
        v74 = BYTE1(g_CiDeveloperMode) & 1;
        v150 = &v74;
        v153 = 1;
        v73 = (g_CiDeveloperMode & 0x200) != 0;
        v152 = &v73;
        v155 = 1;
        v72 = (g_CiDeveloperMode & 0x400) != 0;
        v154 = &v72;
        v157 = 1;
        v71 = (g_CiDeveloperMode & 0x800) != 0;
        v156 = &v71;
        v70 = (g_CiDeveloperMode & 0x1000) != 0;
        v69 = (g_CiDeveloperMode & 0x2000) != 0;
        v158 = &v70;
        v160 = &v69;
        v159 = 1;
        v68 = (g_CiPolicyState & 0x800000) != 0;
        v162 = &v68;
        v161 = 1;
        v67 = BYTE2(g_CiDeveloperMode) & 1;
        v164 = &v67;
        v163 = 1;
        v66 = BYTE2(g_CiPolicyState) & 1;
        v166 = &v66;
        v165 = 1;
        v65 = g_CiPolicyState & 1;
        v168 = &v65;
        v167 = 1;
        v64 = (g_CiPolicyState & 2) != 0;
        v170 = &v64;
        v169 = 1;
        v171 = 1;
        v173 = 1;
        v63 = (g_CiPolicyState & 4) != 0;
        v172 = &v63;
        v175 = 1;
        v62 = (g_CiPolicyState & 8) != 0;
        v174 = &v62;
        v177 = 1;
        v61 = (g_CiPolicyState & 0x10) != 0;
        v176 = &v61;
        v179 = 1;
        v60 = (g_CiPolicyState & 0x40) != 0;
        v178 = &v60;
        v181 = 1;
        v59 = (g_CiPolicyState & 0x20) != 0;
        v180 = &v59;
        v183 = 1;
        v58 = (g_CiPolicyState & 0x800) != 0;
        v182 = &v58;
        v185 = 1;
        v57 = (g_CiPolicyState & 0x1000) != 0;
        v184 = &v57;
        v187 = 1;
        v56 = (g_CiPolicyState & 0x2000) != 0;
        v186 = &v56;
        v189 = 1;
        v55 = (g_CiPolicyState & 0x4000) != 0;
        v188 = &v55;
        v191 = 1;
        v54 = (g_CiPolicyState & 0x8000) != 0;
        v190 = &v54;
        v53 = (g_CiPolicyState & 0x20000) != 0;
        v50 = (g_CiPolicyState & 0x80000) != 0;
        v192 = &v53;
        v194 = &v50;
        v193 = 1;
        v195 = 1;
        v196 = &v49;
        IsPolicyActive = g_CiRevocationListInfo;
        p_IsPolicyActive = &IsPolicyActive;
        v197 = 1;
        v199 = 1;
        v200 = &qword_180048E50[g_CiRevocationListInfo];
        v49 = a4;
        v202 = qword_180048E50;
        v201 = 8;
        v204 = &qword_180048E58;
        v206 = &qword_180048E60;
        v208 = &qword_180048E68;
        v203 = 8;
        v205 = 8;
        v207 = 8;
        v209 = 8;
        tlgCreate1Sz_wchar_t(v210, v23);
        tlgCreate1Sz_wchar_t(v211, 0);
        v212 = &v96;
        v96 = g_SmartAppControlEnforcementReason;
        v214 = &v99;
        v213 = v27;
        v99 = v27;
        v215 = v27;
        tlgWriteTransfer_EtwWriteTransfer(
          (__int64)&dword_180048128,
          (unsigned __int8 *)byte_18003EAA1,
          a2,
          a3,
          0x32u,
          v121);
LABEL_13:
        v24 = 0;
      }
    }
    else if ( (unsigned int)dword_180048128 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180048128, 0x800000000000LL) )
    {
      v100 = 2048;
      v123 = 8;
      v122 = &v100;
      v124 = &IsPolicyActive;
      v96 = g_NumberOfSiPolicies;
      v126 = &v96;
      v128 = &v49;
      v130 = &v50;
      v97 = g_NightsWatchDesktopMinValueSeenDuringThisBootSession;
      v132 = &v97;
      v125 = v24 + 1;
      v53 = (v24 + 1) & g_CiDeveloperMode;
      v134 = &v53;
      v127 = 4;
      v54 = (v24 + 1) & ((unsigned int)g_CiDeveloperMode >> 1);
      v136 = &v54;
      v129 = v125;
      v55 = (v24 + 1) & ((unsigned int)g_CiDeveloperMode >> 2);
      v138 = &v55;
      v131 = v125;
      v56 = (v24 + 1) & ((unsigned int)g_CiDeveloperMode >> 3);
      v140 = &v56;
      v133 = 4;
      v57 = (v24 + 1) & ((unsigned int)g_CiDeveloperMode >> 4);
      v142 = &v57;
      v135 = v125;
      v58 = (v24 + 1) & ((unsigned int)g_CiDeveloperMode >> 5);
      v144 = &v58;
      v137 = v125;
      v59 = (v24 + 1) & ((unsigned int)g_CiDeveloperMode >> 6);
      v146 = &v59;
      v139 = v125;
      v141 = v125;
      v143 = v125;
      v145 = v125;
      v147 = v125;
      v149 = v125;
      v60 = (v24 + 1) & ((unsigned int)g_CiDeveloperMode >> 7);
      v148 = &v60;
      v151 = v125;
      v61 = (v24 + 1) & BYTE1(g_CiDeveloperMode);
      v150 = &v61;
      v153 = v125;
      v62 = (v24 + 1) & ((unsigned int)g_CiDeveloperMode >> 9);
      v152 = &v62;
      v155 = v125;
      v63 = (v24 + 1) & ((unsigned int)g_CiDeveloperMode >> 10);
      v154 = &v63;
      v157 = v125;
      v64 = (v24 + 1) & ((unsigned int)g_CiDeveloperMode >> 11);
      v156 = &v64;
      v65 = (v24 + 1) & ((unsigned int)g_CiDeveloperMode >> 12);
      v66 = (v24 + 1) & ((unsigned int)g_CiDeveloperMode >> 13);
      v158 = &v65;
      v160 = &v66;
      v159 = v125;
      v67 = (v24 + 1) & ((unsigned int)g_CiPolicyState >> 23);
      v162 = &v67;
      v161 = v125;
      v68 = (v24 + 1) & BYTE2(g_CiDeveloperMode);
      v164 = &v68;
      v163 = v125;
      v69 = (v24 + 1) & BYTE2(g_CiPolicyState);
      v166 = &v69;
      v165 = v125;
      v70 = (v24 + 1) & g_CiPolicyState;
      v168 = &v70;
      v167 = v125;
      v71 = (v24 + 1) & ((unsigned int)g_CiPolicyState >> 1);
      v170 = &v71;
      v169 = v125;
      v171 = v125;
      v173 = v125;
      v72 = (v24 + 1) & ((unsigned int)g_CiPolicyState >> 2);
      v172 = &v72;
      v175 = v125;
      v73 = (v24 + 1) & ((unsigned int)g_CiPolicyState >> 3);
      v174 = &v73;
      v177 = v125;
      v74 = (v24 + 1) & ((unsigned int)g_CiPolicyState >> 4);
      v176 = &v74;
      v179 = v125;
      v75 = (v24 + 1) & ((unsigned int)g_CiPolicyState >> 6);
      v178 = &v75;
      v181 = v125;
      v76 = (v24 + 1) & ((unsigned int)g_CiPolicyState >> 5);
      v180 = &v76;
      v183 = v125;
      v77 = (v24 + 1) & ((unsigned int)g_CiPolicyState >> 11);
      v182 = &v77;
      v185 = v125;
      v78 = (v24 + 1) & ((unsigned int)g_CiPolicyState >> 12);
      v184 = &v78;
      v187 = v125;
      v79 = (v24 + 1) & ((unsigned int)g_CiPolicyState >> 13);
      v186 = &v79;
      v189 = v125;
      v80 = (v24 + 1) & ((unsigned int)g_CiPolicyState >> 14);
      v188 = &v80;
      v191 = v125;
      v81 = (v24 + 1) & ((unsigned int)g_CiPolicyState >> 15);
      v190 = &v81;
      v82 = (v24 + 1) & ((unsigned int)g_CiPolicyState >> 17);
      v83 = (v24 + 1) & ((unsigned int)g_CiPolicyState >> 19);
      v192 = &v82;
      v194 = &v83;
      v193 = v125;
      v195 = v125;
      v197 = v125;
      v196 = &v51;
      v52 = g_CiRevocationListInfo;
      p_IsPolicyActive = &v52;
      v199 = v125;
      v51 = a4;
      v200 = &qword_180048E50[g_CiRevocationListInfo];
      v201 = 8;
      v202 = qword_180048E50;
      v203 = 8;
      v204 = &qword_180048E58;
      v206 = &qword_180048E60;
      v208 = &qword_180048E68;
      v205 = 8;
      v207 = 8;
      v209 = 8;
      tlgCreate1Sz_wchar_t(v210, v23);
      tlgCreate1Sz_wchar_t(v211, 0);
      v98 = 3;
      v212 = &v98;
      v26 = (unsigned __int8 *)&unk_18003FDB0;
      v47 = 49;
LABEL_12:
      v213 = 4;
      tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_180048128, v26, a2, a3, v47, v121);
      goto LABEL_13;
    }
  }
  v28 = v24;
  if ( g_NumberOfSiPolicies > v24 )
  {
    do
    {
      v29 = *((_QWORD *)g_SiPolicyHandles + v28);
      v30 = (-(__int64)(*(_DWORD *)(v29 + 40) < 6u) & 0xFFFFFFFFFFFFFD40uLL) + 720;
      IsBasePolicy = SIPolicyIsBasePolicy(v29);
      v113[0] = v29 + (-(__int64)(v31 < 6) & 0xFFFFFFFFFFFFFD50uLL) + 704;
      IsLegacyPolicyID = SIPolicyIsLegacyPolicyID(v113[0]);
      v104 = *(_DWORD *)(v29 + 44);
      PolicyOptionsV2 = SIPolicyGetPolicyOptionsV2(v29);
      LOBYTE(v33) = v86;
      v106 = PolicyOptionsV2;
      v34 = *((_QWORD *)g_SiPolicyHandles + v28);
      v35 = *(unsigned int *)(v34 + 768);
      v108 = *(_DWORD *)(v34 + 48);
      v95 = v35;
      v87 = (unsigned __int8)SIPolicyCheckCustomKernelSignersAllowed(v35, v33) != 0;
      v8 = 1;
      if ( (int)CiLogSIPolicyGetPolicyIDs(v36, &DestinationString, &v115) < 0 )
      {
        RtlInitUnicodeString(&DestinationString, L"Default");
        RtlInitUnicodeString(&v115, L"Default");
        v8 = 0;
      }
      v37 = *((_QWORD *)g_SiPolicyHandles + v28);
      v119 = *(_QWORD *)(v37 + 32);
      v38 = CipSerializeWindowsLockdownPolicySettingValue(v37, &v95, &UnicodeString, &v84);
      LOBYTE(v24) = 0;
      v111 = v38;
      if ( v38 < 0 )
        break;
      if ( (unsigned int)dword_180048128 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180048128, 0x800000000000LL) )
      {
        v118 = 2048;
        v224 = &v118;
        v102 = g_NumberOfSiPolicies;
        v226 = &v102;
        v228 = &v103;
        v105 = v104;
        v230 = &v105;
        v107 = v106;
        v232 = &v107;
        v109 = v108;
        v234 = &v109;
        v120 = v119;
        v236 = &v120;
        v110 = v95;
        v238 = &v110;
        v88 = v87;
        v240 = &v88;
        v242 = v245;
        Buffer = DestinationString.Buffer;
        v245[0] = DestinationString.Length;
        v246 = v249;
        v248 = v115.Buffer;
        v249[0] = v115.Length;
        v250 = v113[0];
        v252 = v29 + v30;
        v90 = IsBasePolicy;
        v254 = &v90;
        v92 = IsLegacyPolicyID;
        v256 = &v92;
        v225 = 8;
        v227 = 4;
        v103 = v28;
        v39 = *((_QWORD *)g_SiPolicyHandles + v28);
        v229 = 4;
        v231 = 4;
        v233 = 4;
        v235 = 4;
        v237 = 8;
        v239 = 4;
        v241 = 1;
        v243 = 2;
        v245[1] = v24;
        v247 = 2;
        v249[1] = v24;
        v251 = 16;
        v253 = 16;
        v255 = 1;
        v257 = 1;
        v40 = *(_DWORD *)(v39 + 752) < v24;
        v41 = *(_DWORD *)(v39 + 752) == v24;
        v258 = &v93;
        v93 = !v40 && !v41;
        v259 = 1;
        if ( v84 == (_BYTE)v24 )
        {
          v42 = v24 + 1;
          Length = 0;
        }
        else
        {
          Length = UnicodeString.Length;
          v42 = v24;
        }
        v263[1] = v24;
        v261 = 2;
        v260 = v263;
        v44 = (PWSTR)qword_180033520;
        if ( !v42 )
          v44 = UnicodeString.Buffer;
        v262 = v44;
        v263[0] = Length;
        tlgWriteTransfer_EtwWriteTransfer(
          (__int64)&dword_180048128,
          (unsigned __int8 *)byte_18003CB83,
          a2,
          a3,
          0x16u,
          &v223);
        LOBYTE(v24) = 0;
      }
      if ( v84 != (_BYTE)v24 )
      {
        RtlFreeUnicodeString(&UnicodeString);
        LOBYTE(v24) = 0;
      }
      if ( v8 )
      {
        RtlFreeUnicodeString(&DestinationString);
        RtlFreeUnicodeString(&v115);
        LOBYTE(v24) = 0;
      }
      ++v28;
      v8 = 1;
    }
    while ( v28 < g_NumberOfSiPolicies );
    v5 = v111;
    v23 = P;
    v13 = v112;
  }
  if ( v23 )
  {
    ExFreePoolWithTag(v23, 0x63734943u);
    LOBYTE(v24) = 0;
  }
  if ( v8 )
  {
    RtlFreeUnicodeString(&DestinationString);
    RtlFreeUnicodeString(&v115);
    LOBYTE(v24) = 0;
  }
  v45 = v85;
  if ( v13 && !v85 )
  {
    if ( (unsigned int)dword_180048128 > 5 && (unsigned __int8)tlgKeywordOn(&dword_180048128, 0x400000000000LL) )
    {
      v113[0] = 2048;
      v219 = v113;
      v220 = 8;
      v221 = "HVCI";
      v222 = 5;
      tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_180048128, (unsigned __int8 *)byte_18003D3DF, a2, a3, 4u, v218);
      LOBYTE(v24) = 0;
    }
    v45 = v85;
  }
  if ( v94 != (_BYTE)v24
    && !v45
    && (unsigned int)dword_180048128 > 5
    && (unsigned __int8)tlgKeywordOn(&dword_180048128, 0x400000000000LL) )
  {
    v113[0] = 2048;
    v219 = v113;
    v220 = 8;
    v221 = "10S";
    v222 = 4;
    tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_180048128, (unsigned __int8 *)byte_18003CD0B, a2, a3, 4u, v218);
  }
  return v5;
}

```

## disassembly

```asm
0x180066330  mov     [rsp-8+arg_0], rbx
0x180066335  push    rbp
0x180066336  push    rsi
0x180066337  push    rdi
0x180066338  push    r12
0x18006633a  push    r13
0x18006633c  push    r14
0x18006633e  push    r15
0x180066340  lea     rbp, [rsp-500h]
0x180066348  sub     rsp, 600h
0x18006634f  mov     rax, cs:__security_cookie
0x180066356  xor     rax, rsp
0x180066359  mov     [rbp+530h+var_40], rax
0x180066360  mov     [rsp+630h+var_5DA], cl
0x180066364  xor     r14d, r14d
0x180066367  xorps   xmm0, xmm0
0x18006636a  mov     [rsp+630h+var_5DC], r14b
0x18006636f  xor     eax, eax
0x180066371  lea     rcx, SiPolicyIDEModeBase
0x180066378  mov     r12, rdx
0x18006637b  mov     dword ptr [rbp+530h+var_578+4], eax
0x18006637e  xorps   xmm1, xmm1
0x180066381  xor     edx, edx
0x180066383  mov     edi, r14d
0x180066386  mov     bl, r9b
0x180066389  movups  xmmword ptr [rbp+530h+DestinationString.Length], xmm0
0x18006638d  mov     r13, r8
0x180066390  mov     sil, 1
0x180066393  movups  xmmword ptr [rbp+530h+var_558.Length], xmm1
0x180066397  movups  xmmword ptr [rbp+530h+UnicodeString.Length], xmm0
0x18006639b  call    SIPolicyIsPolicyActive
0x1800663a0  lea     rcx, SiPolicyIDNightsWatchDesktop
0x1800663a7  mov     [rsp+630h+var_600], al
0x1800663ab  call    SIPolicyIsPolicyActive
0x1800663b0  lea     rcx, SiPolicyIDNightsWatchDesktopEval
0x1800663b7  mov     [rsp+630h+var_5FF], al
0x1800663bb  call    SIPolicyIsPolicyActive
0x1800663c0  lea     rcx, qword_180032830
0x1800663c7  mov     [rsp+630h+var_5FE], al
0x1800663cb  call    SIPolicyIsPolicyActive
0x1800663d0  mov     r15d, cs:g_CiOptions
0x1800663d7  lea     rcx, qword_180032800
0x1800663de  and     r15d, 8000h
0x1800663e5  mov     [rsp+630h+var_5DB], al
0x1800663e9  mov     [rbp+530h+var_580], r15d
0x1800663ed  call    SIPolicyIsPolicyActive
0x1800663f2  mov     [rsp+630h+var_5D2], al
0x1800663f6  lea     r8, aVersion; "Version"
0x1800663fd  lea     rax, [rsp+630h+var_5D0]
0x180066402  mov     [rsp+630h+var_5D0], r14d
0x180066407  mov     [rsp+630h+var_608], rax
0x18006640c  lea     rax, [rbp+530h+P]
0x180066410  mov     [rbp+530h+P], r14
0x180066414  lea     r14d, [rdx+2]
0x180066418  mov     r9d, r14d
0x18006641b  mov     [rsp+630h+var_610], rax
0x180066420  lea     rdx, aRegistryMachin_12; "\\Registry\\MACHINE\\SOFTWARE\\Microsof"...
0x180066427  call    CipGetRegistryValue2
0x18006642c  lea     rax, [rsp+630h+var_5D0]
0x180066431  mov     r9d, r14d
0x180066434  mov     [rsp+630h+var_608], rax
0x180066439  lea     r8, aRevocationupda; "RevocationUpdateVersion"
0x180066440  lea     rax, [rbp+530h+P]
0x180066444  lea     rdx, aRegistryMachin_17; "\\Registry\\MACHINE\\System\\CurrentCon"...
0x18006644b  mov     [rsp+630h+var_610], rax
0x180066450  call    CipGetRegistryValue2
0x180066455  call    Feature_SAC_LocalLogging__private_IsEnabledDeviceUsageNoInline
0x18006645a  mov     r14, [rbp+530h+P]
0x18006645e  xor     r9d, r9d
0x180066461  test    eax, eax
0x180066463  jnz     loc_180066F81
0x180066469  call    Feature_SAC_ClientSideEnable__private_IsEnabledDeviceUsageNoInline
0x18006646e  xor     r9d, r9d
0x180066471  test    eax, eax
0x180066473  mov     eax, cs:dword_180048128
0x180066479  jnz     loc_1800669F1
0x18006647f  cmp     eax, 5
0x180066482  jbe     loc_180067555
0x180066488  mov     rdx, 800000000000h
0x180066492  lea     rcx, dword_180048128
0x180066499  call    _tlgKeywordOn
0x18006649e  test    al, al
0x1800664a0  jz      loc_180067555
0x1800664a6  lea     edx, [r9+1]
0x1800664aa  mov     [rsp+630h+var_5B8], 800h
0x1800664b3  lea     rax, [rsp+630h+var_5B8]
0x1800664b8  mov     [rbp+530h+var_4E8], 8
0x1800664c0  mov     [rbp+530h+var_4F0], rax
0x1800664c4  mov     al, [rsp+630h+var_600]
0x1800664c8  mov     [rsp+630h+var_600], al
0x1800664cc  lea     rax, [rsp+630h+var_600]
0x1800664d1  mov     [rbp+530h+var_4E0], rax
0x1800664d5  mov     eax, cs:g_NumberOfSiPolicies
0x1800664db  mov     [rsp+630h+var_5CC], eax
0x1800664df  lea     rax, [rsp+630h+var_5CC]
0x1800664e4  mov     [rbp+530h+var_4D0], rax
0x1800664e8  mov     al, [rsp+630h+var_5FF]
0x1800664ec  mov     [rsp+630h+var_5FF], al
0x1800664f0  lea     rax, [rsp+630h+var_5FF]
0x1800664f5  mov     [rbp+530h+var_4C0], rax
0x1800664f9  mov     al, [rsp+630h+var_5FE]
0x1800664fd  mov     [rsp+630h+var_5FE], al
0x180066501  lea     rax, [rsp+630h+var_5FE]
0x180066506  mov     [rbp+530h+var_4B0], rax
0x18006650d  mov     eax, cs:g_NightsWatchDesktopMinValueSeenDuringThisBootSession
0x180066513  mov     [rsp+630h+var_5C8], eax
0x180066517  lea     rax, [rsp+630h+var_5C8]
0x18006651c  mov     [rbp+530h+var_4A0], rax
0x180066523  mov     eax, cs:g_CiDeveloperMode
0x180066529  mov     cl, al
0x18006652b  and     cl, dl
0x18006652d  mov     [rbp+530h+var_4D8], rdx
0x180066531  mov     [rsp+630h+var_5FB], cl
0x180066535  lea     rcx, [rsp+630h+var_5FB]
0x18006653a  mov     [rbp+530h+var_490], rcx
0x180066541  mov     ecx, eax
0x180066543  shr     ecx, 1
0x180066545  and     cl, dl
0x180066547  mov     [rbp+530h+var_4C8], 4
0x18006654f  mov     [rsp+630h+var_5FA], cl
0x180066553  lea     rcx, [rsp+630h+var_5FA]
0x180066558  mov     [rbp+530h+var_480], rcx
0x18006655f  mov     ecx, eax
0x180066561  shr     ecx, 2
0x180066564  and     cl, dl
0x180066566  mov     [rbp+530h+var_4B8], rdx
0x18006656a  mov     [rsp+630h+var_5F9], cl
0x18006656e  lea     rcx, [rsp+630h+var_5F9]
0x180066573  mov     [rbp+530h+var_470], rcx
0x18006657a  mov     ecx, eax
0x18006657c  shr     ecx, 3
0x18006657f  and     cl, dl
0x180066581  mov     [rbp+530h+var_4A8], rdx
0x180066588  mov     [rsp+630h+var_5F8], cl
0x18006658c  lea     rcx, [rsp+630h+var_5F8]
0x180066591  mov     [rbp+530h+var_460], rcx
0x180066598  mov     ecx, eax
0x18006659a  shr     ecx, 4
0x18006659d  and     cl, dl
0x18006659f  mov     [rbp+530h+var_498], 4
0x1800665aa  mov     [rsp+630h+var_5F7], cl
0x1800665ae  lea     rcx, [rsp+630h+var_5F7]
0x1800665b3  mov     [rbp+530h+var_450], rcx
0x1800665ba  mov     ecx, eax
0x1800665bc  shr     ecx, 5
0x1800665bf  and     cl, dl
0x1800665c1  mov     [rbp+530h+var_488], rdx
0x1800665c8  mov     [rsp+630h+var_5F6], cl
0x1800665cc  lea     rcx, [rsp+630h+var_5F6]
0x1800665d1  mov     [rbp+530h+var_440], rcx
0x1800665d8  mov     ecx, eax
0x1800665da  shr     ecx, 6
0x1800665dd  and     cl, dl
0x1800665df  mov     [rbp+530h+var_478], rdx
0x1800665e6  mov     [rsp+630h+var_5F5], cl
0x1800665ea  lea     rcx, [rsp+630h+var_5F5]
0x1800665ef  mov     [rbp+530h+var_430], rcx
0x1800665f6  mov     ecx, eax
0x1800665f8  shr     ecx, 7
0x1800665fb  mov     [rbp+530h+var_468], rdx
0x180066602  mov     [rbp+530h+var_458], rdx
0x180066609  mov     [rbp+530h+var_448], rdx
0x180066610  mov     [rbp+530h+var_438], rdx
0x180066617  mov     [rbp+530h+var_428], rdx
0x18006661e  and     cl, dl
0x180066620  mov     [rbp+530h+var_418], rdx
0x180066627  mov     [rsp+630h+var_5F4], cl
0x18006662b  lea     rcx, [rsp+630h+var_5F4]
0x180066630  mov     [rbp+530h+var_420], rcx
0x180066637  mov     ecx, eax
0x180066639  shr     ecx, 8
0x18006663c  and     cl, dl
0x18006663e  mov     [rbp+530h+var_408], rdx
0x180066645  mov     [rsp+630h+var_5F3], cl
0x180066649  lea     rcx, [rsp+630h+var_5F3]
0x18006664e  mov     [rbp+530h+var_410], rcx
0x180066655  mov     ecx, eax
0x180066657  shr     ecx, 9
0x18006665a  and     cl, dl
0x18006665c  mov     [rbp+530h+var_3F8], rdx
0x180066663  mov     [rsp+630h+var_5F2], cl
0x180066667  lea     rcx, [rsp+630h+var_5F2]
0x18006666c  mov     [rbp+530h+var_400], rcx
0x180066673  mov     ecx, eax
0x180066675  shr     ecx, 0Ah
0x180066678  and     cl, dl
0x18006667a  mov     [rbp+530h+var_3E8], rdx
0x180066681  mov     [rsp+630h+var_5F1], cl
0x180066685  lea     rcx, [rsp+630h+var_5F1]
0x18006668a  mov     [rbp+530h+var_3F0], rcx
0x180066691  mov     ecx, eax
0x180066693  shr     ecx, 0Bh
0x180066696  and     cl, dl
0x180066698  mov     [rbp+530h+var_3D8], rdx
0x18006669f  mov     [rsp+630h+var_5F0], cl
0x1800666a3  lea     rcx, [rsp+630h+var_5F0]
0x1800666a8  mov     [rbp+530h+var_3E0], rcx
0x1800666af  mov     ecx, eax
0x1800666b1  shr     ecx, 0Ch
0x1800666b4  and     cl, dl
0x1800666b6  shr     eax, 0Dh
0x1800666b9  mov     [rsp+630h+var_5EF], cl
0x1800666bd  and     al, dl
0x1800666bf  lea     rcx, [rsp+630h+var_5EF]
0x1800666c4  mov     [rsp+630h+var_5EE], al
0x1800666c8  mov     [rbp+530h+var_3D0], rcx
0x1800666cf  lea     rax, [rsp+630h+var_5EE]
0x1800666d4  mov     [rbp+530h+var_3C0], rax
0x1800666db  mov     eax, cs:g_CiPolicyState
0x1800666e1  mov     ecx, eax
0x1800666e3  shr     ecx, 17h
0x1800666e6  and     cl, dl
0x1800666e8  mov     [rbp+530h+var_3C8], rdx
0x1800666ef  mov     [rsp+630h+var_5ED], cl
0x1800666f3  lea     rcx, [rsp+630h+var_5ED]
0x1800666f8  mov     [rbp+530h+var_3B0], rcx
0x1800666ff  mov     cl, byte ptr cs:g_CiDeveloperMode+2
0x180066705  and     cl, dl
0x180066707  mov     [rbp+530h+var_3B8], rdx
0x18006670e  mov     [rsp+630h+var_5EC], cl
0x180066712  lea     rcx, [rsp+630h+var_5EC]
0x180066717  mov     [rbp+530h+var_3A0], rcx
0x18006671e  mov     cl, byte ptr cs:g_CiPolicyState+2
0x180066724  and     cl, dl
0x180066726  mov     [rbp+530h+var_3A8], rdx
0x18006672d  mov     [rsp+630h+var_5EB], cl
0x180066731  lea     rcx, [rsp+630h+var_5EB]
0x180066736  mov     [rbp+530h+var_390], rcx
0x18006673d  mov     cl, al
0x18006673f  and     cl, dl
0x180066741  mov     [rbp+530h+var_398], rdx
0x180066748  mov     [rsp+630h+var_5EA], cl
0x18006674c  lea     rcx, [rsp+630h+var_5EA]
0x180066751  mov     [rbp+530h+var_380], rcx
0x180066758  mov     ecx, eax
0x18006675a  shr     ecx, 1
0x18006675c  and     cl, dl
0x18006675e  mov     [rbp+530h+var_388], rdx
0x180066765  mov     [rsp+630h+var_5E9], cl
0x180066769  lea     rcx, [rsp+630h+var_5E9]
0x18006676e  mov     [rbp+530h+var_370], rcx
0x180066775  mov     ecx, eax
0x180066777  shr     ecx, 2
0x18006677a  mov     [rbp+530h+var_378], rdx
0x180066781  mov     [rbp+530h+var_368], rdx
0x180066788  and     cl, dl
0x18006678a  mov     [rbp+530h+var_358], rdx
0x180066791  mov     [rsp+630h+var_5E8], cl
0x180066795  lea     rcx, [rsp+630h+var_5E8]
0x18006679a  mov     [rbp+530h+var_360], rcx
0x1800667a1  mov     ecx, eax
0x1800667a3  shr     ecx, 3
0x1800667a6  and     cl, dl
0x1800667a8  mov     [rbp+530h+var_348], rdx
0x1800667af  mov     [rsp+630h+var_5E7], cl
0x1800667b3  lea     rcx, [rsp+630h+var_5E7]
0x1800667b8  mov     [rbp+530h+var_350], rcx
0x1800667bf  mov     ecx, eax
0x1800667c1  shr     ecx, 4
0x1800667c4  and     cl, dl
0x1800667c6  mov     [rbp+530h+var_338], rdx
0x1800667cd  mov     [rsp+630h+var_5E6], cl
0x1800667d1  lea     rcx, [rsp+630h+var_5E6]
0x1800667d6  mov     [rbp+530h+var_340], rcx
0x1800667dd  mov     ecx, eax
0x1800667df  shr     ecx, 6
0x1800667e2  and     cl, dl
0x1800667e4  mov     [rbp+530h+var_328], rdx
0x1800667eb  mov     [rsp+630h+var_5E5], cl
0x1800667ef  lea     rcx, [rsp+630h+var_5E5]
0x1800667f4  mov     [rbp+530h+var_330], rcx
0x1800667fb  mov     ecx, eax
0x1800667fd  shr     ecx, 5
0x180066800  and     cl, dl
0x180066802  mov     [rbp+530h+var_318], rdx
0x180066809  mov     [rsp+630h+var_5E4], cl
0x18006680d  lea     rcx, [rsp+630h+var_5E4]
0x180066812  mov     [rbp+530h+var_320], rcx
0x180066819  mov     ecx, eax
0x18006681b  shr     ecx, 0Bh
0x18006681e  and     cl, dl
0x180066820  mov     [rbp+530h+var_308], rdx
0x180066827  mov     [rsp+630h+var_5E3], cl
0x18006682b  lea     rcx, [rsp+630h+var_5E3]
0x180066830  mov     [rbp+530h+var_310], rcx
0x180066837  mov     ecx, eax
0x180066839  shr     ecx, 0Ch
0x18006683c  and     cl, dl
0x18006683e  mov     [rbp+530h+var_2F8], rdx
0x180066845  mov     [rsp+630h+var_5E2], cl
0x180066849  lea     rcx, [rsp+630h+var_5E2]
0x18006684e  mov     [rbp+530h+var_300], rcx
0x180066855  mov     ecx, eax
0x180066857  shr     ecx, 0Dh
0x18006685a  and     cl, dl
0x18006685c  mov     [rbp+530h+var_2E8], rdx
0x180066863  mov     [rsp+630h+var_5E1], cl
0x180066867  lea     rcx, [rsp+630h+var_5E1]
0x18006686c  mov     [rbp+530h+var_2F0], rcx
0x180066873  mov     ecx, eax
  ... truncated ...
```
