# CFveApi::ChooseProtectionType(ulong,bool *,bool *)

- ea: `0x180051b20`
- end: `0x180053a18`
- name: `?ChooseProtectionType@CFveApi@@IEAAJKPEA_N0@Z`
- size: `7928`
- prototype: `__int64 __fastcall(CFveApi *this, char, bool *, bool *)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800c5324`

## callees

- `0x1800090c0`
- `0x1800091a0`
- `0x180009650`
- `0x18000ba30`
- `0x180018b10`
- `0x180018c68`
- `0x18003e7a8`
- `0x18004e140`
- `0x180051b20`
- `0x180053a20`
- `0x180053a80`
- `0x180053b5c`
- `0x180053bac`
- `0x180053e64`
- `0x1800bcd78`
- `0x1800c763c`
- `0x18011efce`
- `0x18011f010`
- `0x180129010`

## string_xrefs

- `0x180051e97`: `VolumePath`
- `0x18005212d`: `VolumePath`
- `0x18005237d`: `VolumePath`
- `0x1800525c4`: `VolumePath`
- `0x180052815`: `VolumePath`
- `0x180052bcd`: `VolumePath`
- `0x180052fbe`: `VolumePath`
- `0x18005328a`: `VolumePath`
- `0x1800534d6`: `VolumePath`
- `0x180053769`: `VolumePath`
- `0x180053913`: `VolumePath`
- `0x180120ef0`: `VolumePath`
- `0x18012106c`: `VolumePath`

## pseudocode

```c
__int64 __fastcall CFveApi::ChooseProtectionType(CFveApi *this, char a2, bool *a3, bool *a4)
{
  __int64 v8; // r8
  __int64 v9; // rdx
  char v10; // al
  unsigned int v11; // r15d
  int Policy; // ebx
  struct CFvePolicy *v13; // rsi
  int v14; // ecx
  int v15; // eax
  __int64 v16; // rax
  const unsigned __int16 *LoggingVolumePath; // rax
  const unsigned __int16 *v18; // rdx
  const unsigned __int16 *LoggingVolumeDriveLetter; // rax
  const unsigned __int16 *v20; // rdx
  CFveApi *v21; // rcx
  __int64 v22; // rax
  const unsigned __int16 *v23; // rax
  const unsigned __int16 *v24; // rdx
  const unsigned __int16 *v25; // rax
  const unsigned __int16 *v26; // rdx
  __int64 v27; // rax
  const unsigned __int16 *v28; // rax
  const unsigned __int16 *v29; // rdx
  const unsigned __int16 *v30; // rax
  const unsigned __int16 *v31; // rdx
  __int64 v32; // rax
  const unsigned __int16 *v33; // rax
  const unsigned __int16 *v34; // rdx
  const unsigned __int16 *v35; // rax
  const unsigned __int16 *v36; // rdx
  int v37; // r15d
  __int64 v38; // rax
  const unsigned __int16 *v39; // rax
  const unsigned __int16 *v40; // rdx
  const unsigned __int16 *v41; // rax
  const unsigned __int16 *v42; // rdx
  int v43; // r15d
  __int64 v44; // rax
  const unsigned __int16 *v45; // rax
  const unsigned __int16 *v46; // rdx
  const unsigned __int16 *v47; // rax
  const unsigned __int16 *v48; // rdx
  __int64 v49; // rax
  const unsigned __int16 *v50; // rax
  const unsigned __int16 *v51; // rdx
  const unsigned __int16 *v52; // rax
  const unsigned __int16 *v53; // rdx
  __int64 v54; // rax
  const unsigned __int16 *v55; // rax
  const unsigned __int16 *v56; // rdx
  const unsigned __int16 *v57; // rax
  const unsigned __int16 *v58; // rdx
  __int64 v59; // rax
  const unsigned __int16 *v60; // rax
  const unsigned __int16 *v61; // rdx
  const unsigned __int16 *v62; // rax
  const unsigned __int16 *v63; // rdx
  __int64 v65; // rax
  const unsigned __int16 *v66; // rax
  const unsigned __int16 *v67; // rdx
  const unsigned __int16 *v68; // rax
  const unsigned __int16 *v69; // rdx
  struct _FVEAPI_EVENT_DATA_COLLECTION *v70; // rdx
  const unsigned __int16 *v71; // rax
  const unsigned __int16 *v72; // rdx
  const unsigned __int16 *v73; // rax
  const unsigned __int16 *v74; // rdx
  unsigned int v75; // [rsp+20h] [rbp-D88h]
  unsigned int v76; // [rsp+20h] [rbp-D88h]
  unsigned int v77; // [rsp+20h] [rbp-D88h]
  unsigned int v78; // [rsp+20h] [rbp-D88h]
  unsigned int v79; // [rsp+20h] [rbp-D88h]
  unsigned int v80; // [rsp+20h] [rbp-D88h]
  unsigned int v81; // [rsp+20h] [rbp-D88h]
  unsigned int v82; // [rsp+20h] [rbp-D88h]
  unsigned int v83; // [rsp+20h] [rbp-D88h]
  unsigned int v84; // [rsp+20h] [rbp-D88h]
  unsigned int v85; // [rsp+20h] [rbp-D88h]
  unsigned int v86; // [rsp+20h] [rbp-D88h]
  bool v87; // [rsp+48h] [rbp-D60h] BYREF
  bool v88; // [rsp+49h] [rbp-D5Fh] BYREF
  _WORD v89[3]; // [rsp+4Ah] [rbp-D5Eh] BYREF
  bool v90; // [rsp+50h] [rbp-D58h] BYREF
  enum _FIRMWARE_TYPE v91; // [rsp+54h] [rbp-D54h] BYREF
  __int64 v92; // [rsp+58h] [rbp-D50h] BYREF
  __int64 v93; // [rsp+60h] [rbp-D48h]
  __int64 v94; // [rsp+68h] [rbp-D40h]
  CFveApi *v95; // [rsp+70h] [rbp-D38h]
  void *lpMem[3]; // [rsp+78h] [rbp-D30h] BYREF
  _QWORD v97[3]; // [rsp+90h] [rbp-D18h] BYREF
  _QWORD v98[3]; // [rsp+A8h] [rbp-D00h] BYREF
  _QWORD v99[3]; // [rsp+C0h] [rbp-CE8h] BYREF
  _QWORD v100[3]; // [rsp+D8h] [rbp-CD0h] BYREF
  _QWORD v101[3]; // [rsp+F0h] [rbp-CB8h] BYREF
  _QWORD v102[3]; // [rsp+108h] [rbp-CA0h] BYREF
  _QWORD v103[3]; // [rsp+120h] [rbp-C88h] BYREF
  _QWORD v104[5]; // [rsp+138h] [rbp-C70h] BYREF
  __int128 v105; // [rsp+160h] [rbp-C48h]
  __int128 v106; // [rsp+170h] [rbp-C38h]
  __int128 v107; // [rsp+190h] [rbp-C18h]
  __int128 v108; // [rsp+1A0h] [rbp-C08h]
  __int128 v109; // [rsp+1B0h] [rbp-BF8h]
  const wchar_t *v110; // [rsp+1C0h] [rbp-BE8h]
  const wchar_t *v111; // [rsp+1C8h] [rbp-BE0h]
  __int64 v112; // [rsp+1D0h] [rbp-BD8h]
  int v113; // [rsp+1D8h] [rbp-BD0h]
  __int128 v114; // [rsp+1E0h] [rbp-BC8h]
  const wchar_t *v115; // [rsp+1F0h] [rbp-BB8h]
  const unsigned __int16 *v116; // [rsp+1F8h] [rbp-BB0h]
  int *v117; // [rsp+200h] [rbp-BA8h]
  int v118; // [rsp+208h] [rbp-BA0h]
  __int128 v119; // [rsp+210h] [rbp-B98h]
  const wchar_t *v120; // [rsp+220h] [rbp-B88h]
  const wchar_t *v121; // [rsp+228h] [rbp-B80h]
  __int64 v122; // [rsp+230h] [rbp-B78h]
  int v123; // [rsp+238h] [rbp-B70h]
  __int128 v124; // [rsp+240h] [rbp-B68h]
  const wchar_t *v125; // [rsp+250h] [rbp-B58h]
  const wchar_t *v126; // [rsp+258h] [rbp-B50h]
  __int64 v127; // [rsp+260h] [rbp-B48h]
  int v128; // [rsp+268h] [rbp-B40h]
  __int128 v129; // [rsp+270h] [rbp-B38h]
  const wchar_t *v130; // [rsp+280h] [rbp-B28h]
  const wchar_t *v131; // [rsp+288h] [rbp-B20h]
  __int64 v132; // [rsp+290h] [rbp-B18h]
  int v133; // [rsp+298h] [rbp-B10h]
  __int128 v134; // [rsp+2A0h] [rbp-B08h]
  const wchar_t *v135; // [rsp+2B0h] [rbp-AF8h]
  const wchar_t *v136; // [rsp+2B8h] [rbp-AF0h]
  __int64 v137; // [rsp+2C0h] [rbp-AE8h]
  int v138; // [rsp+2C8h] [rbp-AE0h]
  __int128 v139; // [rsp+2D0h] [rbp-AD8h]
  const wchar_t *v140; // [rsp+2E0h] [rbp-AC8h]
  const wchar_t *v141; // [rsp+2E8h] [rbp-AC0h]
  __int64 v142; // [rsp+2F0h] [rbp-AB8h]
  int v143; // [rsp+2F8h] [rbp-AB0h]
  __int128 v144; // [rsp+300h] [rbp-AA8h]
  const wchar_t *v145; // [rsp+310h] [rbp-A98h]
  const wchar_t *v146; // [rsp+318h] [rbp-A90h]
  __int64 v147; // [rsp+320h] [rbp-A88h]
  int v148; // [rsp+328h] [rbp-A80h]
  __int128 v149; // [rsp+330h] [rbp-A78h]
  const wchar_t *v150; // [rsp+340h] [rbp-A68h]
  const unsigned __int16 *v151; // [rsp+348h] [rbp-A60h]
  struct CFvePolicy **v152; // [rsp+350h] [rbp-A58h]
  int v153; // [rsp+358h] [rbp-A50h]
  __int128 v154; // [rsp+360h] [rbp-A48h]
  const wchar_t *v155; // [rsp+370h] [rbp-A38h]
  const wchar_t *v156; // [rsp+378h] [rbp-A30h]
  __int64 v157; // [rsp+380h] [rbp-A28h]
  int v158; // [rsp+388h] [rbp-A20h]
  __int128 v159; // [rsp+390h] [rbp-A18h]
  const wchar_t *v160; // [rsp+3A0h] [rbp-A08h]
  const wchar_t *v161; // [rsp+3A8h] [rbp-A00h]
  __int64 v162; // [rsp+3B0h] [rbp-9F8h]
  int v163; // [rsp+3B8h] [rbp-9F0h]
  __int64 v164; // [rsp+3C0h] [rbp-9E8h] BYREF
  __int64 *v165; // [rsp+3C8h] [rbp-9E0h]
  _QWORD *v166; // [rsp+3D0h] [rbp-9D8h] BYREF
  _QWORD *v167; // [rsp+3D8h] [rbp-9D0h]
  __int64 v168; // [rsp+3E0h] [rbp-9C8h] BYREF
  __int64 *v169; // [rsp+3E8h] [rbp-9C0h]
  _QWORD *v170; // [rsp+3F0h] [rbp-9B8h] BYREF
  _QWORD *v171; // [rsp+3F8h] [rbp-9B0h]
  __int128 v172; // [rsp+400h] [rbp-9A8h] BYREF
  _QWORD *v173; // [rsp+410h] [rbp-998h] BYREF
  _QWORD *v174; // [rsp+418h] [rbp-990h]
  __int128 v175; // [rsp+420h] [rbp-988h] BYREF
  _QWORD *v176; // [rsp+430h] [rbp-978h] BYREF
  _QWORD *v177; // [rsp+438h] [rbp-970h]
  __int128 v178; // [rsp+440h] [rbp-968h] BYREF
  _QWORD *v179; // [rsp+450h] [rbp-958h] BYREF
  _QWORD **v180; // [rsp+458h] [rbp-950h]
  __int128 v181; // [rsp+460h] [rbp-948h] BYREF
  _QWORD *v182; // [rsp+470h] [rbp-938h] BYREF
  _QWORD *v183; // [rsp+478h] [rbp-930h]
  __int128 v184; // [rsp+480h] [rbp-928h] BYREF
  _QWORD *v185; // [rsp+490h] [rbp-918h] BYREF
  _QWORD *v186; // [rsp+498h] [rbp-910h]
  __int128 v187; // [rsp+4A0h] [rbp-908h] BYREF
  _QWORD *v188; // [rsp+4B0h] [rbp-8F8h] BYREF
  _QWORD *v189; // [rsp+4B8h] [rbp-8F0h]
  __int128 v190; // [rsp+4C0h] [rbp-8E8h] BYREF
  _QWORD *v191; // [rsp+4D0h] [rbp-8D8h] BYREF
  _QWORD *v192; // [rsp+4D8h] [rbp-8D0h]
  __int128 v193; // [rsp+4E0h] [rbp-8C8h] BYREF
  _QWORD *v194; // [rsp+4F0h] [rbp-8B8h] BYREF
  _QWORD *v195; // [rsp+4F8h] [rbp-8B0h]
  __int128 v196; // [rsp+500h] [rbp-8A8h] BYREF
  _QWORD *v197; // [rsp+510h] [rbp-898h] BYREF
  _QWORD *v198; // [rsp+518h] [rbp-890h]
  int v199; // [rsp+520h] [rbp-888h] BYREF
  int v200; // [rsp+524h] [rbp-884h] BYREF
  int v201; // [rsp+528h] [rbp-880h] BYREF
  int v202; // [rsp+52Ch] [rbp-87Ch] BYREF
  struct CFvePolicy *v203; // [rsp+530h] [rbp-878h] BYREF
  int v204; // [rsp+538h] [rbp-870h] BYREF
  int v205; // [rsp+53Ch] [rbp-86Ch] BYREF
  int v206; // [rsp+540h] [rbp-868h] BYREF
  unsigned int v207; // [rsp+544h] [rbp-864h] BYREF
  _QWORD v208[6]; // [rsp+548h] [rbp-860h] BYREF
  _QWORD v209[6]; // [rsp+578h] [rbp-830h] BYREF
  _OWORD v210[3]; // [rsp+5A8h] [rbp-800h] BYREF
  _OWORD v211[3]; // [rsp+5D8h] [rbp-7D0h] BYREF
  _OWORD v212[3]; // [rsp+608h] [rbp-7A0h] BYREF
  _OWORD v213[3]; // [rsp+638h] [rbp-770h] BYREF
  _OWORD v214[3]; // [rsp+668h] [rbp-740h] BYREF
  _OWORD v215[3]; // [rsp+698h] [rbp-710h] BYREF
  __int128 v216; // [rsp+6C8h] [rbp-6E0h] BYREF
  __int128 v217; // [rsp+6D8h] [rbp-6D0h]
  __int64 v218; // [rsp+6E8h] [rbp-6C0h]
  _QWORD v219[6]; // [rsp+6F0h] [rbp-6B8h] BYREF
  _QWORD v220[6]; // [rsp+720h] [rbp-688h] BYREF
  _QWORD v221[6]; // [rsp+750h] [rbp-658h] BYREF
  _QWORD v222[6]; // [rsp+780h] [rbp-628h] BYREF
  _QWORD v223[6]; // [rsp+7B0h] [rbp-5F8h] BYREF
  _QWORD v224[6]; // [rsp+7E0h] [rbp-5C8h] BYREF
  _QWORD v225[6]; // [rsp+810h] [rbp-598h] BYREF
  _QWORD v226[6]; // [rsp+840h] [rbp-568h] BYREF
  _OWORD v227[3]; // [rsp+870h] [rbp-538h] BYREF
  _QWORD v228[6]; // [rsp+8A0h] [rbp-508h] BYREF
  _QWORD v229[6]; // [rsp+8D0h] [rbp-4D8h] BYREF
  _OWORD v230[3]; // [rsp+900h] [rbp-4A8h] BYREF
  _QWORD v231[6]; // [rsp+930h] [rbp-478h] BYREF
  _OWORD v232[3]; // [rsp+960h] [rbp-448h] BYREF
  _OWORD v233[3]; // [rsp+990h] [rbp-418h] BYREF
  _OWORD v234[3]; // [rsp+9C0h] [rbp-3E8h] BYREF
  _OWORD v235[3]; // [rsp+9F0h] [rbp-3B8h] BYREF
  _OWORD v236[3]; // [rsp+A20h] [rbp-388h] BYREF
  _OWORD v237[3]; // [rsp+A50h] [rbp-358h] BYREF
  _OWORD v238[3]; // [rsp+A80h] [rbp-328h] BYREF
  _OWORD v239[3]; // [rsp+AB0h] [rbp-2F8h] BYREF
  _OWORD v240[3]; // [rsp+AE0h] [rbp-2C8h] BYREF
  _OWORD v241[3]; // [rsp+B10h] [rbp-298h] BYREF
  _OWORD v242[3]; // [rsp+B40h] [rbp-268h] BYREF
  _OWORD v243[3]; // [rsp+B70h] [rbp-238h] BYREF
  _OWORD v244[3]; // [rsp+BA0h] [rbp-208h] BYREF
  _OWORD v245[3]; // [rsp+BD0h] [rbp-1D8h] BYREF
  _OWORD v246[3]; // [rsp+C00h] [rbp-1A8h] BYREF
  _OWORD v247[3]; // [rsp+C30h] [rbp-178h] BYREF
  CHAR MultiByteStr[256]; // [rsp+C60h] [rbp-148h] BYREF

  v95 = this;
  lpMem[1] = a3;
  lpMem[2] = a4;
  v216 = 0;
  v217 = 0;
  v218 = 0;
  v207 = 0;
  v90 = 0;
  v88 = 0;
  memset(v89, 0, sizeof(v89));
  memset_0(MultiByteStr, 0, sizeof(MultiByteStr));
  v9 = 0;
  v203 = 0;
  v201 = 0;
  v202 = 0;
  v199 = 0;
  lpMem[0] = 0;
  v91 = FirmwareTypeUnknown;
  v10 = 0;
  v11 = 0;
  v87 = 0;
  v200 = 0;
  if ( !a3 || !a4 )
  {
    Policy = -2147024809;
    goto LABEL_73;
  }
  *a3 = 0;
  *a4 = 0;
  Policy = CFveApiBase::GetPolicy(this, &v203);
  v9 = 0;
  if ( Policy < 0 )
    goto LABEL_13;
  v13 = v203;
  Policy = (*(__int64 (__fastcall **)(__int64, int *, _QWORD))(*(_QWORD *)(*((_QWORD *)v203 + 1) + 104LL) + 8LL))(
             *((_QWORD *)v203 + 1) + 104LL,
             &v202,
             0);
  v9 = 0;
  if ( Policy < 0 )
    goto LABEL_13;
  v14 = v202;
  *a4 = v202 != 0;
  if ( (a2 & 1) != 0 )
  {
    if ( v14 )
      *a3 = 0;
    else
      Policy = -2144272209;
    goto LABEL_9;
  }
  v15 = CFveApiBase::FsVolIoctl(this, 0x2D1480u, v8, 0, 0, &v216, 0x28u, &v207);
  v9 = 0;
  if ( v15 < 0 )
  {
    if ( v15 != -2147024895 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          163,
          &WPP_e2677893b9163e8423a47779f4b931d1_Traceguids,
          (unsigned int)v15);
      v9 = 0;
    }
    Policy = 0;
    goto LABEL_13;
  }
  Policy = (**(__int64 (__fastcall ***)(__int64, int *, int *))(*((_QWORD *)v13 + 1) + 104LL))(
             *((_QWORD *)v13 + 1) + 104LL,
             &v201,
             &v200);
  v9 = 0;
  if ( Policy < 0 )
    goto LABEL_13;
  if ( v200 )
  {
    if ( v201 )
      goto LABEL_27;
LABEL_23:
    v187 = 0;
    v92 = 0;
    v93 = 0;
    v94 = 0;
    v189 = &v188;
    v188 = &v188;
    v16 = *((_QWORD *)this + 146);
    v139 = 0;
    v140 = L"ProtectorGuid";
    v141 = L"GUID";
    v142 = v16 + 16;
    v143 = 16;
    v222[2] = L"ProtectorGuid";
    v222[3] = L"GUID";
    v222[4] = v16 + 16;
    v222[5] = 16;
    v222[0] = &v188;
    v222[1] = &v188;
    v188 = v222;
    v189 = v222;
    memset(v235, 0, sizeof(v235));
    LoggingVolumePath = CFveApiBase::GetLoggingVolumePath(this);
    FveApiEventLogDeclareWSTRING((struct _FVEAPI_EVENT_DATA *)v235, v18, L"VolumePath", LoggingVolumePath, v75);
    if ( (_QWORD **)*v189 == &v188 )
    {
      *(_QWORD *)&v235[0] = &v188;
      *((_QWORD *)&v235[0] + 1) = v189;
      *v189 = v235;
      v189 = v235;
      memset(v236, 0, sizeof(v236));
      LoggingVolumeDriveLetter = CFveApiBase::GetLoggingVolumeDriveLetter(this);
      FveApiEventLogDeclareWSTRING(
        (struct _FVEAPI_EVENT_DATA *)v236,
        v20,
        L"VolumeDriveLetter",
        LoggingVolumeDriveLetter,
        v76);
      if ( (_QWORD **)*v189 == &v188 )
      {
        *(_QWORD *)&v236[0] = &v188;
        *((_QWORD *)&v236[0] + 1) = v189;
        *v189 = v236;
        v189 = v236;
        *((_QWORD *)&v187 + 1) = FVEAPI_OP_INITIALIZATION_HW_DISABLED;
        FveEventLogHandle::LogFveApiEvent((FveEventLogHandle *)&v92, (struct _FVEAPI_EVENT_DATA_COLLECTION *)&v187);
        FveEventLogHandle::EventLogCleanup((FveEventLogHandle *)&v92);
        v10 = 1;
        v11 = 2;
        *(_DWORD *)&v89[1] = 2;
LABEL_26:
        v9 = 0;
        goto LABEL_73;
      }
    }
    goto LABEL_71;
  }
  if ( (a2 & 2) == 0 )
    goto LABEL_23;
LABEL_27:
  if ( (*((_DWORD *)this + 27) & 0x10000001) != 0 )
  {
    Policy = FveGetFirmwareType(&v91);
    v9 = 0;
    if ( Policy < 0 )
      goto LABEL_13;
    if ( v91 == FirmwareTypeUefi )
    {
      Policy = CFveApi::EDriveSupportedInBoot(v21, &v87);
      v9 = 0;
      if ( Policy < 0 )
        goto LABEL_13;
    }
    if ( !v87 )
    {
      *a3 = 0;
      v190 = 0;
      memset(v98, 0, sizeof(v98));
      v192 = &v191;
      v191 = &v191;
      v22 = *((_QWORD *)this + 146);
      v134 = 0;
      v135 = L"ProtectorGuid";
      v136 = L"GUID";
      v137 = v22 + 16;
      v138 = 16;
      v223[2] = L"ProtectorGuid";
      v223[3] = L"GUID";
      v223[4] = v22 + 16;
      v223[5] = 16;
      v223[0] = &v191;
      v223[1] = &v191;
      v191 = v223;
      v192 = v223;
      memset(v238, 0, sizeof(v238));
      v23 = CFveApiBase::GetLoggingVolumePath(this);
      FveApiEventLogDeclareWSTRING((struct _FVEAPI_EVENT_DATA *)v238, v24, L"VolumePath", v23, v75);
      if ( (_QWORD **)*v192 == &v191 )
      {
        *(_QWORD *)&v238[0] = &v191;
        *((_QWORD *)&v238[0] + 1) = v192;
        *v192 = v238;
        v192 = v238;
        memset(v239, 0, sizeof(v239));
        v25 = CFveApiBase::GetLoggingVolumeDriveLetter(this);
        FveApiEventLogDeclareWSTRING((struct _FVEAPI_EVENT_DATA *)v239, v26, L"VolumeDriveLetter", v25, v77);
        if ( (_QWORD **)*v192 == &v191 )
        {
          *(_QWORD *)&v239[0] = &v191;
          *((_QWORD *)&v239[0] + 1) = v192;
          *v192 = v239;
          v192 = v239;
          *((_QWORD *)&v190 + 1) = FVEAPI_OP_INITIALIZATION_HW_INCOMPATIBLE_FIRMWARE;
          FveEventLogHandle::LogFveApiEvent((FveEventLogHandle *)v98, (struct _FVEAPI_EVENT_DATA_COLLECTION *)&v190);
          FveEventLogHandle::EventLogCleanup((FveEventLogHandle *)v98);
          v11 = 1;
LABEL_35:
          *(_DWORD *)&v89[1] = v11;
          v10 = 0;
          goto LABEL_26;
        }
      }
      goto LABEL_71;
    }
  }
  if ( (BYTE4(v216) & 1) == 0 )
  {
    v193 = 0;
    memset(v99, 0, sizeof(v99));
    v195 = &v194;
    v194 = &v194;
    v27 = *((_QWORD *)this + 146);
    v129 = 0;
    v130 = L"ProtectorGuid";
    v131 = L"GUID";
    v132 = v27 + 16;
    v133 = 16;
    v224[2] = L"ProtectorGuid";
    v224[3] = L"GUID";
    v224[4] = v27 + 16;
    v224[5] = 16;
    v224[0] = &v194;
    v224[1] = &v194;
    v194 = v224;
    v195 = v224;
    memset(v240, 0, sizeof(v240));
    v28 = CFveApiBase::GetLoggingVolumePath(this);
    FveApiEventLogDeclareWSTRING((struct _FVEAPI_EVENT_DATA *)v240, v29, L"VolumePath", v28, v75);
    if ( (_QWORD **)*v195 == &v194 )
    {
      *(_QWORD *)&v240[0] = &v194;
      *((_QWORD *)&v240[0] + 1) = v195;
      *v195 = v240;
      v195 = v240;
      memset(v241, 0, sizeof(v241));
      v30 = CFveApiBase::GetLoggingVolumeDriveLetter(this);
      FveApiEventLogDeclareWSTRING((struct _FVEAPI_EVENT_DATA *)v241, v31, L"VolumeDriveLetter", v30, v78);
      if ( (_QWORD **)*v195 == &v194 )
      {
        *(_QWORD *)&v241[0] = &v194;
        *((_QWORD *)&v241[0] + 1) = v195;
        *v195 = v241;
        v195 = v241;
        *((_QWORD *)&v193 + 1) = FVEAPI_OP_INITIALIZATION_HW_NOT_ACTIVATED;
        FveEventLogHandle::LogFveApiEvent((FveEventLogHandle *)v99, (struct _FVEAPI_EVENT_DATA_COLLECTION *)&v193);
        FveEventLogHandle::EventLogCleanup((FveEventLogHandle *)v99);
        v11 = 3;
        goto LABEL_35;
      }
    }
LABEL_71:
    __fastfail(3u);
  }
  if ( (BYTE8(v216) & 2) == 0 )
  {
    v196 = 0;
    memset(v100, 0, sizeof(v100));
    v198 = &v197;
    v197 = &v197;
    v32 = *((_QWORD *)this + 146);
    v124 = 0;
    v125 = L"ProtectorGuid";
    v126 = L"GUID";
    v127 = v32 + 16;
    v128 = 16;
    v225[2] = L"ProtectorGuid";
    v225[3] = L"GUID";
    v225[4] = v32 + 16;
    v225[5] = 16;
    v225[0] = &v197;
    v225[1] = &v197;
    v197 = v225;
    v198 = v225;
    memset(v242, 0, sizeof(v242));
    v33 = CFveApiBase::GetLoggingVolumePath(this);
    FveApiEventLogDeclareWSTRING((struct _FVEAPI_EVENT_DATA *)v242, v34, L"VolumePath", v33, v75);
    if ( (_QWORD **)*v198 == &v197 )
    {
      *(_QWORD *)&v242[0] = &v197;
      *((_QWORD *)&v242[0] + 1) = v198;
      *v198 = v242;
      v198 = v242;
      memset(v237, 0, sizeof(v237));
      v35 = CFveApiBase::GetLoggingVolumeDriveLetter(this);
      FveApiEventLogDeclareWSTRING((struct _FVEAPI_EVENT_DATA *)v237, v36, L"VolumeDriveLetter", v35, v79);
      if ( (_QWORD **)*v198 == &v197 )
      {
        *(_QWORD *)&v237[0] = &v197;
        *((_QWORD *)&v237[0] + 1) = v198;
        *v198 = v237;
        v198 = v237;
        *((_QWORD *)&v196 + 1) = FVEAPI_OP_INITIALIZATION_HW_KEY_NOT_PROTECTED;
        FveEventLogHandle::LogFveApiEvent((FveEventLogHandle *)v100, (struct _FVEAPI_EVENT_DATA_COLLECTION *)&v196);
        FveEventLogHandle::EventLogCleanup((FveEventLogHandle *)v100);
        v11 = 5;
        goto LABEL_35;
      }
    }
    goto LABEL_71;
  }
  if ( (unsigned int)v217 > 0x20 )
  {
    v37 = 8 * v217;
    v172 = 0;
    memset(v101, 0, sizeof(v101));
    v174 = &v173;
    v173 = &v173;
    v38 = *((_QWORD *)this + 146);
    v119 = 0;
    v120 = L"ProtectorGuid";
    v121 = L"GUID";
    v122 = v38 + 16;
    v123 = 16;
    v226[2] = L"ProtectorGuid";
    v226[3] = L"GUID";
    v226[4] = v38 + 16;
    v226[5] = 16;
    v226[0] = &v173;
    v226[1] = &v173;
    v173 = v226;
    v174 = v226;
    memset(v243, 0, sizeof(v243));
    v39 = CFveApiBase::GetLoggingVolumePath(this);
    FveApiEventLogDeclareWSTRING((struct _FVEAPI_EVENT_DATA *)v243, v40, L"VolumePath", v39, v75);
    if ( (_QWORD **)*v174 == &v173 )
    {
      *(_QWORD *)&v243[0] = &v173;
      *((_QWORD *)&v243[0] + 1) = v174;
      *v174 = v243;
      v174 = v243;
      memset(v214, 0, sizeof(v214));
      v41 = CFveApiBase::GetLoggingVolumeDriveLetter(this);
      FveApiEventLogDeclareWSTRING((struct _FVEAPI_EVENT_DATA *)v214, v42, L"VolumeDriveLetter", v41, v80);
      if ( (_QWORD **)*v174 == &v173 )
      {
        *(_QWORD *)&v214[0] = &v173;
        *((_QWORD *)&v214[0] + 1) = v174;
        *v174 = v214;
        v174 = v214;
        v206 = 256;
        *(_QWORD *)&v107 = L"ExpectedKeyLength";
        *((_QWORD *)&v107 + 1) = L"ULONG";
        *(_QWORD *)&v108 = &v206;
        *((_QWORD *)&v108 + 1) = 4;
        v227[0] = 0;
        v227[1] = v107;
        v227[2] = v108;
        if ( *(_QWORD ***)&v214[0] == &v173 )
        {
          *((_QWORD *)&v227[0] + 1) = v214;
          *(_QWORD *)&v214[0] = v227;
          v205 = v37;
          v114 = 0;
          v115 = L"ActualKeyLength";
          v116 = L"ULONG";
          v117 = &v205;
          v118 = 4;
          v228[2] = L"ActualKeyLength";
          v228[3] = L"ULONG";
          v228[4] = &v205;
          v228[5] = 4;
          v228[0] = &v173;
          v228[1] = v227;
          *(_QWORD *)&v227[0] = v228;
          v174 = v228;
          *((_QWORD *)&v172 + 1) = FVEAPI_OP_INITIALIZATION_HW_INVALID_MIN_KEY_LENGTH;
          FveEventLogHandle::LogFveApiEvent((FveEventLogHandle *)v101, (struct _FVEAPI_EVENT_DATA_COLLECTION *)&v172);
          FveEventLogHandle::EventLogCleanup((FveEventLogHandle *)v101);
          v11 = 6;
          goto LABEL_35;
        }
      }
    }
    goto LABEL_71;
  }
  if ( DWORD1(v217) < 0x20 )
  {
    v43 = 8 * v217;
    v175 = 0;
    memset(v102, 0, sizeof(v102));
    v177 = &v176;
    v176 = &v176;
    v44 = *((_QWORD *)this + 146);
    v144 = 0;
    v145 = L"ProtectorGuid";
    v146 = L"GUID";
    v147 = v44 + 16;
    v148 = 16;
    v229[2] = L"ProtectorGuid";
    v229[3] = L"GUID";
    v229[4] = v44 + 16;
    v229[5] = 16;
    v229[0] = &v176;
    v229[1] = &v176;
    v176 = v229;
    v177 = v229;
    memset(v244, 0, sizeof(v244));
    v45 = CFveApiBase::GetLoggingVolumePath(this);
    FveApiEventLogDeclareWSTRING((struct _FVEAPI_EVENT_DATA *)v244, v46, L"VolumePath", v45, v75);
    if ( (_QWORD **)*v177 == &v176 )
    {
      *(_QWORD *)&v244[0] = &v176;
      *((_QWORD *)&v244[0] + 1) = v177;
      *v177 = v244;
      v177 = v244;
      memset(v215, 0, sizeof(v215));
      v47 = CFveApiBase::GetLoggingVolumeDriveLetter(this);
      FveApiEventLogDeclareWSTRING((struct _FVEAPI_EVENT_DATA *)v215, v48, L"VolumeDriveLetter", v47, v81);
      if ( (_QWORD **)*v177 == &v176 )
      {
        *(_QWORD *)&v215[0] = &v176;
        *((_QWORD *)&v215[0] + 1) = v177;
        *v177 = v215;
        v177 = v215;
        v204 = 256;
        *(_QWORD *)&v105 = L"ExpectedKeyLength";
        *((_QWORD *)&v105 + 1) = L"ULONG";
        *(_QWORD *)&v106 = &v204;
        *((_QWORD *)&v106 + 1) = 4;
        v230[0] = 0;
        v230[1] = v105;
        v230[2] = v106;
        if ( *(_QWORD ***)&v215[0] == &v176 )
        {
          *((_QWORD *)&v230[0] + 1) = v215;
          *(_QWORD *)&v215[0] = v230;
          LODWORD(v203) = v43;
          v149 = 0;
          v150 = L"ActualKeyLength";
          v151 = L"ULONG";
          v152 = &v203;
          v153 = 4;
          v231[2] = L"ActualKeyLength";
          v231[3] = L"ULONG";
          v231[4] = &v203;
          v231[5] = 4;
          v231[0] = &v176;
          v231[1] = v230;
          *(_QWORD *)&v230[0] = v231;
          v177 = v231;
          *((_QWORD *)&v175 + 1) = FVEAPI_OP_INITIALIZATION_HW_INVALID_MAX_KEY_LENGTH;
          FveEventLogHandle::LogFveApiEvent((FveEventLogHandle *)v102, (struct _FVEAPI_EVENT_DATA_COLLECTION *)&v175);
          FveEventLogHandle::EventLogCleanup((FveEventLogHandle *)v102);
          v11 = 7;
          goto LABEL_35;
        }
      }
    }
    goto LABEL_71;
  }
  Policy = CFveApiBase::GetBandProperties(this, 1, &v90, &v88, (bool *)v89, (bool *)v89 + 1, MultiByteStr);
  if ( Policy == (unsigned int)FromNtStatus(-1073741275) )
  {
    v178 = 0;
    memset(v103, 0, sizeof(v103));
    v180 = &v179;
    v179 = &v179;
    v49 = *((_QWORD *)this + 146);
    v154 = 0;
    v155 = L"ProtectorGuid";
    v156 = L"GUID";
    v157 = v49 + 16;
    v158 = 16;
    v219[2] = L"ProtectorGuid";
    v219[3] = L"GUID";
    v219[4] = v49 + 16;
    v219[5] = 16;
    v219[0] = &v179;
    v219[1] = &v179;
    v179 = v219;
    v180 = (_QWORD **)v219;
    memset(v245, 0, sizeof(v245));
    v50 = CFveApiBase::GetLoggingVolumePath(this);
    FveApiEventLogDeclareWSTRING((struct _FVEAPI_EVENT_DATA *)v245, v51, L"VolumePath", v50, v75);
    if ( *v180 != &v179 )
      goto LABEL_71;
    *(_QWORD *)&v245[0] = &v179;
    *((_QWORD *)&v245[0] + 1) = v180;
    *v180 = v245;
    v180 = (_QWORD **)v245;
    memset(v246, 0, sizeof(v246));
    v52 = CFveApiBase::GetLoggingVolumeDriveLetter(this);
    FveApiEventLogDeclareWSTRING((struct _FVEAPI_EVENT_DATA *)v246, v53, L"VolumeDriveLetter", v52, v82);
    if ( *v180 != &v179 )
      goto LABEL_71;
    *(_QWORD *)&v246[0] = &v179;
    *((_QWORD *)&v246[0] + 1) = v180;
    *v180 = v246;
    v180 = (_QWORD **)v246;
    *((_QWORD *)&v178 + 1) = FVEAPI_OP_INITIALIZATION_HW_VOLUME_NOT_CONFIGURED;
    FveEventLogHandle::LogFveApiEvent((FveEventLogHandle *)v103, (struct _FVEAPI_EVENT_DATA_COLLECTION *)&v178);
    FveEventLogHandle::EventLogCleanup((FveEventLogHandle *)v103);
    v11 = 8;
    *(_DWORD *)&v89[1] = 8;
    v9 = 0;
    Policy = 0;
    goto LABEL_9;
  }
  v9 = 0;
  if ( Policy < 0 )
    goto LABEL_13;
  if ( v88 || __PAIR16__(v89[0], 0) != HIBYTE(v89[0]) )
  {
    Policy = -2144272208;
    v184 = 0;
    memset(v97, 0, sizeof(v97));
    v186 = &v185;
    v185 = &v185;
    v59 = *((_QWORD *)this + 146);
    v109 = 0;
    v110 = L"ProtectorGuid";
    v111 = L"GUID";
    v112 = v59 + 16;
    v113 = 16;
    v221[2] = L"ProtectorGuid";
    v221[3] = L"GUID";
    v221[4] = v59 + 16;
    v221[5] = 16;
    v221[0] = &v185;
    v221[1] = &v185;
    v185 = v221;
    v186 = v221;
    memset(v233, 0, sizeof(v233));
    v60 = CFveApiBase::GetLoggingVolumePath(this);
    FveApiEventLogDeclareWSTRING((struct _FVEAPI_EVENT_DATA *)v233, v61, L"VolumePath", v60, v75);
    if ( (_QWORD **)*v186 == &v185 )
    {
      *(_QWORD *)&v233[0] = &v185;
      *((_QWORD *)&v233[0] + 1) = v186;
      *v186 = v233;
      v186 = v233;
      memset(v234, 0, sizeof(v234));
      v62 = CFveApiBase::GetLoggingVolumeDriveLetter(this);
      FveApiEventLogDeclareWSTRING((struct _FVEAPI_EVENT_DATA *)v234, v63, L"VolumeDriveLetter", v62, v84);
      if ( (_QWORD **)*v186 == &v185 )
      {
        *(_QWORD *)&v234[0] = &v185;
        *((_QWORD *)&v234[0] + 1) = v186;
        *v186 = v234;
        v186 = v234;
        *((_QWORD *)&v184 + 1) = FVEAPI_OP_INITIALIZATION_HW_BAND_IN_USE;
        FveEventLogHandle::LogFveApiEvent((FveEventLogHandle *)v97, (struct _FVEAPI_EVENT_DATA_COLLECTION *)&v184);
        FveEventLogHandle::EventLogCleanup((FveEventLogHandle *)v97);
        v11 = 9;
        goto LABEL_35;
      }
    }
    goto LABEL_71;
  }
  Policy = CFveApiBase::OidToWStr(MultiByteStr, (unsigned __int16 **)lpMem);
  v9 = 0;
  if ( Policy < 0
    || (Policy = (*(__int64 (__fastcall **)(struct CFvePolicy *, void *, int *, _QWORD))(*(_QWORD *)v13 + 40LL))(
                   v13,
                   lpMem[0],
                   &v199,
                   0),
        v9 = 0,
        Policy < 0) )
  {
LABEL_13:
    v10 = 0;
    goto LABEL_73;
  }
  if ( !v199 )
  {
    v181 = 0;
    memset(v104, 0, 24);
    v183 = &v182;
    v182 = &v182;
    v54 = *((_QWORD *)this + 146);
    v159 = 0;
    v160 = L"ProtectorGuid";
    v161 = L"GUID";
    v162 = v54 + 16;
    v163 = 16;
    v220[2] = L"ProtectorGuid";
    v220[3] = L"GUID";
    v220[4] = v54 + 16;
    v220[5] = 16;
    v220[0] = &v182;
    v220[1] = &v182;
    v182 = v220;
    v183 = v220;
    memset(v247, 0, sizeof(v247));
    v55 = CFveApiBase::GetLoggingVolumePath(this);
    FveApiEventLogDeclareWSTRING((struct _FVEAPI_EVENT_DATA *)v247, v56, L"VolumePath", v55, v75);
    if ( (_QWORD **)*v183 == &v182 )
    {
      *(_QWORD *)&v247[0] = &v182;
      *((_QWORD *)&v247[0] + 1) = v183;
      *v183 = v247;
      v183 = v247;
      memset(v232, 0, sizeof(v232));
      v57 = CFveApiBase::GetLoggingVolumeDriveLetter(this);
      FveApiEventLogDeclareWSTRING((struct _FVEAPI_EVENT_DATA *)v232, v58, L"VolumeDriveLetter", v57, v83);
      if ( (_QWORD **)*v183 == &v182 )
      {
        *(_QWORD *)&v232[0] = &v182;
        *((_QWORD *)&v232[0] + 1) = v183;
        *v183 = v232;
        v183 = v232;
        *((_QWORD *)&v181 + 1) = FVEAPI_OP_INITIALIZATION_HW_ALGO_NOT_ALLOWED;
        FveEventLogHandle::LogFveApiEvent((FveEventLogHandle *)v104, (struct _FVEAPI_EVENT_DATA_COLLECTION *)&v181);
        FveEventLogHandle::EventLogCleanup((FveEventLogHandle *)v104);
        v11 = 10;
        goto LABEL_35;
      }
    }
    goto LABEL_71;
  }
  *a3 = 1;
LABEL_9:
  v10 = 0;
LABEL_73:
  if ( Policy < 0 || *a3 )
    goto LABEL_78;
  if ( (a2 & 2) == 0 )
  {
    v65 = *((_QWORD *)this + 146) + 16LL;
    v92 = 0;
    v93 = 0;
    v94 = 0;
    if ( *a4 )
    {
      v164 = 0;
      v165 = 0;
      v208[2] = L"ProtectorGuid";
      v208[3] = L"GUID";
      v208[4] = v65;
      v208[5] = 16;
      v208[0] = &v166;
      v208[1] = &v166;
      v166 = v208;
      v167 = v208;
      memset(v210, 0, sizeof(v210));
      v66 = CFveApiBase::GetLoggingVolumePath(this);
      FveApiEventLogDeclareWSTRING((struct _FVEAPI_EVENT_DATA *)v210, v67, L"VolumePath", v66, v75);
      if ( (_QWORD **)*v167 == &v166 )
      {
        *(_QWORD *)&v210[0] = &v166;
        *((_QWORD *)&v210[0] + 1) = v167;
        *v167 = v210;
        v167 = v210;
        memset(v211, 0, sizeof(v211));
        v68 = CFveApiBase::GetLoggingVolumeDriveLetter(this);
        FveApiEventLogDeclareWSTRING((struct _FVEAPI_EVENT_DATA *)v211, v69, L"VolumeDriveLetter", v68, v85);
        if ( (_QWORD **)*v167 == &v166 )
        {
          *(_QWORD *)&v211[0] = &v166;
          *((_QWORD *)&v211[0] + 1) = v167;
          *v167 = v211;
          v167 = v211;
          v165 = FVEAPI_OP_INITIALIZATION_HW_FAILOVER;
          v70 = (struct _FVEAPI_EVENT_DATA_COLLECTION *)&v164;
LABEL_93:
          FveEventLogHandle::LogFveApiEvent((FveEventLogHandle *)&v92, v70);
          FveEventLogHandle::EventLogCleanup((FveEventLogHandle *)&v92);
          goto LABEL_78;
        }
      }
    }
    else
    {
      v168 = 0;
      v169 = 0;
      v209[2] = L"ProtectorGuid";
      v209[3] = L"GUID";
      v209[4] = v65;
      v209[5] = 16;
      v209[0] = &v170;
      v209[1] = &v170;
      v170 = v209;
      v171 = v209;
      memset(v212, 0, sizeof(v212));
      v71 = CFveApiBase::GetLoggingVolumePath(this);
      FveApiEventLogDeclareWSTRING((struct _FVEAPI_EVENT_DATA *)v212, v72, L"VolumePath", v71, v75);
      if ( (_QWORD **)*v171 == &v170 )
      {
        *(_QWORD *)&v212[0] = &v170;
        *((_QWORD *)&v212[0] + 1) = v171;
        *v171 = v212;
        v171 = v212;
        memset(v213, 0, sizeof(v213));
        v73 = CFveApiBase::GetLoggingVolumeDriveLetter(this);
        FveApiEventLogDeclareWSTRING((struct _FVEAPI_EVENT_DATA *)v213, v74, L"VolumeDriveLetter", v73, v86);
        if ( (_QWORD **)*v171 == &v170 )
        {
          *(_QWORD *)&v213[0] = &v170;
          *((_QWORD *)&v213[0] + 1) = v171;
          *v171 = v213;
          v171 = v213;
          v169 = FVEAPI_OP_INITIALIZATION_HW_NO_FAILOVER;
          v70 = (struct _FVEAPI_EVENT_DATA_COLLECTION *)&v168;
          goto LABEL_93;
        }
      }
    }
    __fastfail(3u);
  }
  if ( v10 )
  {
    Policy = -2144272207;
  }
  else if ( (*((_DWORD *)this + 27) & 0x10000001) != 0 && (v91 & 0xFFFFFFFD) != 0 )
  {
    Policy = -2144272193;
  }
  else
  {
    Policy = -2144272206;
  }
LABEL_78:
  if ( a3 && a4 && v11 )
  {
    LOBYTE(v8) = *a4;
    LOBYTE(v9) = *a3;
    CFveApi::SqmLogEDriveConfig(this, v9, v8, v11);
  }
  if ( lpMem[0] )
    CFveApiBase::FastFree(lpMem[0]);
  return (unsigned int)Policy;
}

```

## disassembly

```asm
0x180051b20  mov     [rsp+arg_8], edx
0x180051b24  push    rbx
0x180051b25  push    rsi
0x180051b26  push    rdi
0x180051b27  push    r12
0x180051b29  push    r13
0x180051b2b  push    r14
0x180051b2d  push    r15
0x180051b2f  sub     rsp, 0D70h
0x180051b36  mov     rax, cs:__security_cookie
0x180051b3d  xor     rax, rsp
0x180051b40  mov     [rsp+0DA8h+var_48], rax
0x180051b48  mov     r13, r9
0x180051b4b  mov     r12, r8
0x180051b4e  mov     r14d, edx
0x180051b51  mov     rdi, rcx
0x180051b54  mov     [rsp+0DA8h+var_D38], rcx
0x180051b59  mov     [rsp+0DA8h+var_D28], r8
0x180051b61  mov     [rsp+0DA8h+var_D20], r9
0x180051b69  xor     ecx, ecx
0x180051b6b  mov     [rsp+0DA8h+var_D64], ecx
0x180051b6f  xorps   xmm0, xmm0
0x180051b72  xor     eax, eax
0x180051b74  movups  [rsp+0DA8h+var_6E0], xmm0
0x180051b7c  movups  [rsp+0DA8h+var_6D0], xmm0
0x180051b84  mov     [rsp+0DA8h+var_6C0], rax
0x180051b8c  mov     [rsp+0DA8h+var_864], ecx
0x180051b93  mov     [rsp+0DA8h+var_D58], cl
0x180051b97  mov     [rsp+0DA8h+var_D5F], cl
0x180051b9b  mov     [rsp+0DA8h+var_D5E], cl
0x180051b9f  xor     edx, edx; Val
0x180051ba1  mov     r8d, 100h; Size
0x180051ba7  lea     rcx, [rsp+0DA8h+MultiByteStr]; void *
0x180051baf  call    memset_0
0x180051bb4  xor     edx, edx
0x180051bb6  mov     [rsp+0DA8h+var_D5E+1], dl
0x180051bba  mov     [rsp+0DA8h+var_878], rdx
0x180051bc2  mov     [rsp+0DA8h+var_880], edx
0x180051bc9  mov     [rsp+0DA8h+var_87C], edx
0x180051bd0  mov     [rsp+0DA8h+var_888], edx
0x180051bd7  mov     [rsp+0DA8h+lpMem], rdx
0x180051bdc  mov     [rsp+0DA8h+var_D54], edx
0x180051be0  mov     al, dl
0x180051be2  mov     [rsp+0DA8h+var_D68], dl
0x180051be6  mov     r15d, edx
0x180051be9  mov     dword ptr [rsp+0DA8h+var_D5E+2], edx
0x180051bed  mov     [rsp+0DA8h+var_D60], dl
0x180051bf1  mov     [rsp+0DA8h+var_884], edx
0x180051bf8  test    r12, r12
0x180051bfb  jz      loc_1800535FB
0x180051c01  test    r13, r13
0x180051c04  jz      loc_1800535FB
0x180051c0a  mov     [r12], dl
0x180051c0e  mov     [r13+0], dl
0x180051c12  lea     rdx, [rsp+0DA8h+var_878]; struct CFvePolicy **
0x180051c1a  mov     rcx, rdi; this
0x180051c1d  call    ?GetPolicy@CFveApiBase@@IEAAJPEAPEAVCFvePolicy@@@Z; CFveApiBase::GetPolicy(CFvePolicy * *)
0x180051c22  mov     ebx, eax
0x180051c24  mov     [rsp+0DA8h+var_D64], eax
0x180051c28  xor     edx, edx
0x180051c2a  test    eax, eax
0x180051c2c  js      loc_180051CF6
0x180051c32  mov     rsi, [rsp+0DA8h+var_878]
0x180051c3a  mov     rcx, [rsi+8]
0x180051c3e  add     rcx, 68h ; 'h'
0x180051c42  mov     rax, [rcx]
0x180051c45  xor     r8d, r8d
0x180051c48  lea     rdx, [rsp+0DA8h+var_87C]
0x180051c50  mov     rax, [rax+8]
0x180051c54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051c59  mov     ebx, eax
0x180051c5b  mov     [rsp+0DA8h+var_D64], eax
0x180051c5f  xor     edx, edx
0x180051c61  test    eax, eax
0x180051c63  js      loc_180051CF6
0x180051c69  mov     ecx, [rsp+0DA8h+var_87C]
0x180051c70  test    ecx, ecx
0x180051c72  setnz   al
0x180051c75  mov     [r13+0], al
0x180051c79  test    r14b, 1
0x180051c7d  jz      short loc_180051CA9
0x180051c7f  lea     rsi, aProtectorguid_0; "ProtectorGuid"
0x180051c86  lea     r14, aGuid; "GUID"
0x180051c8d  test    ecx, ecx
0x180051c8f  jz      short loc_180051C97
0x180051c91  mov     [r12], dl
0x180051c95  jmp     short loc_180051CA0
0x180051c97  mov     ebx, 803100AFh
0x180051c9c  mov     [rsp+0DA8h+var_D64], ebx
0x180051ca0  mov     al, [rsp+0DA8h+var_D68]
0x180051ca4  jmp     loc_180053612
0x180051ca9  lea     rax, [rsp+0DA8h+var_864]
0x180051cb1  mov     [rsp+0DA8h+var_D70], rax; unsigned int *
0x180051cb6  mov     dword ptr [rsp+0DA8h+var_D78], 28h ; '('; unsigned int
0x180051cbe  lea     rax, [rsp+0DA8h+var_6E0]
0x180051cc6  mov     [rsp+0DA8h+var_D80], rax; void *
0x180051ccb  mov     dword ptr [rsp+0DA8h+var_D88], edx; unsigned int
0x180051ccf  xor     r9d, r9d; void *
0x180051cd2  mov     edx, 2D1480h; unsigned int
0x180051cd7  mov     rcx, rdi; this
0x180051cda  call    ?FsVolIoctl@CFveApiBase@@IEAAJKKPEAXK0KPEAK@Z; CFveApiBase::FsVolIoctl(ulong,ulong,void *,ulong,void *,ulong,ulong *)
0x180051cdf  mov     [rsp+0DA8h+var_D64], eax
0x180051ce3  xor     edx, edx
0x180051ce5  test    eax, eax
0x180051ce7  jns     short loc_180051D34
0x180051ce9  cmp     eax, 80070001h
0x180051cee  jnz     short loc_180051CFF
0x180051cf0  mov     ebx, edx
0x180051cf2  mov     [rsp+0DA8h+var_D64], edx
0x180051cf6  mov     al, [rsp+0DA8h+var_D68]
0x180051cfa  jmp     loc_180053604
0x180051cff  lea     rdx, WPP_GLOBAL_Control
0x180051d06  mov     rcx, cs:WPP_GLOBAL_Control
0x180051d0d  cmp     rcx, rdx
0x180051d10  jz      short loc_180051D30
0x180051d12  test    byte ptr [rcx+1Ch], 2
0x180051d16  jz      short loc_180051D30
0x180051d18  mov     edx, 0A3h
0x180051d1d  mov     r9d, eax
0x180051d20  lea     r8, WPP_e2677893b9163e8423a47779f4b931d1_Traceguids
0x180051d27  mov     rcx, [rcx+10h]
0x180051d2b  call    WPP_SF_d
0x180051d30  xor     edx, edx
0x180051d32  jmp     short loc_180051CF0
0x180051d34  mov     rcx, [rsi+8]
0x180051d38  add     rcx, 68h ; 'h'
0x180051d3c  mov     rax, [rcx]
0x180051d3f  lea     r8, [rsp+0DA8h+var_884]
0x180051d47  lea     rdx, [rsp+0DA8h+var_880]
0x180051d4f  mov     rax, [rax]
0x180051d52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051d57  mov     ebx, eax
0x180051d59  mov     [rsp+0DA8h+var_D64], eax
0x180051d5d  xor     edx, edx
0x180051d5f  test    eax, eax
0x180051d61  js      short loc_180051CF6
0x180051d63  mov     eax, [rsp+0DA8h+var_884]
0x180051d6a  test    eax, eax
0x180051d6c  jnz     short loc_180051D7C
0x180051d6e  test    r14b, 2
0x180051d72  jz      short loc_180051D89
0x180051d74  test    eax, eax
0x180051d76  jz      loc_180051FC0
0x180051d7c  cmp     [rsp+0DA8h+var_880], edx
0x180051d83  jnz     loc_180051FC0
0x180051d89  xorps   xmm0, xmm0
0x180051d8c  movups  [rsp+0DA8h+var_908], xmm0
0x180051d94  movups  [rsp+0DA8h+var_8F8], xmm0
0x180051d9c  mov     [rsp+0DA8h+var_D50], rdx
0x180051da1  mov     [rsp+0DA8h+var_D48], rdx
0x180051da6  mov     [rsp+0DA8h+var_D40], rdx
0x180051dab  lea     rax, [rsp+0DA8h+var_8F8]
0x180051db3  mov     qword ptr [rsp+0DA8h+var_8F8+8], rax
0x180051dbb  lea     rax, [rsp+0DA8h+var_8F8]
0x180051dc3  mov     qword ptr [rsp+0DA8h+var_8F8], rax
0x180051dcb  mov     rax, [rdi+490h]
0x180051dd2  add     rax, 10h
0x180051dd6  movdqu  [rsp+0DA8h+var_AD8], xmm0
0x180051ddf  lea     rsi, aProtectorguid_0; "ProtectorGuid"
0x180051de6  mov     [rsp+0DA8h+var_AC8], rsi
0x180051dee  lea     r14, aGuid; "GUID"
0x180051df5  mov     [rsp+0DA8h+var_AC0], r14
0x180051dfd  mov     [rsp+0DA8h+var_AB8], rax
0x180051e05  mov     [rsp+0DA8h+var_AB0], 10h
0x180051e10  mov     [rsp+0DA8h+var_618], rsi
0x180051e18  mov     [rsp+0DA8h+var_610], r14
0x180051e20  mov     [rsp+0DA8h+var_608], rax
0x180051e28  mov     [rsp+0DA8h+var_600], 10h
0x180051e34  lea     rax, [rsp+0DA8h+var_8F8]
0x180051e3c  mov     [rsp+0DA8h+var_628], rax
0x180051e44  lea     rax, [rsp+0DA8h+var_8F8]
0x180051e4c  mov     [rsp+0DA8h+var_620], rax
0x180051e54  lea     rax, [rsp+0DA8h+var_628]
0x180051e5c  mov     qword ptr [rsp+0DA8h+var_8F8], rax
0x180051e64  lea     rax, [rsp+0DA8h+var_628]
0x180051e6c  mov     qword ptr [rsp+0DA8h+var_8F8+8], rax
0x180051e74  movups  [rsp+0DA8h+var_3B8], xmm0
0x180051e7c  movups  [rsp+0DA8h+var_3A8], xmm0
0x180051e84  movups  [rsp+0DA8h+var_398], xmm0
0x180051e8c  mov     rcx, rdi; this
0x180051e8f  call    ?GetLoggingVolumePath@CFveApiBase@@QEAAPEBGXZ; CFveApiBase::GetLoggingVolumePath(void)
0x180051e94  mov     r9, rax; unsigned __int16 *
0x180051e97  lea     r8, aVolumepath; "VolumePath"
0x180051e9e  lea     rcx, [rsp+0DA8h+var_3B8]; struct _FVEAPI_EVENT_DATA *
0x180051ea6  call    ?FveApiEventLogDeclareWSTRING@@YAXAEAU_FVEAPI_EVENT_DATA@@PEBG11K@Z; FveApiEventLogDeclareWSTRING(_FVEAPI_EVENT_DATA &,ushort const *,ushort const *,ushort const *,ulong)
0x180051eab  mov     rcx, qword ptr [rsp+0DA8h+var_8F8+8]
0x180051eb3  lea     rax, [rsp+0DA8h+var_8F8]
0x180051ebb  cmp     [rcx], rax
0x180051ebe  jnz     loc_1800535F4
0x180051ec4  lea     rax, [rsp+0DA8h+var_8F8]
0x180051ecc  mov     qword ptr [rsp+0DA8h+var_3B8], rax
0x180051ed4  mov     qword ptr [rsp+0DA8h+var_3B8+8], rcx
0x180051edc  lea     rax, [rsp+0DA8h+var_3B8]
0x180051ee4  mov     [rcx], rax
0x180051ee7  lea     rax, [rsp+0DA8h+var_3B8]
0x180051eef  mov     qword ptr [rsp+0DA8h+var_8F8+8], rax
0x180051ef7  xorps   xmm0, xmm0
0x180051efa  movups  [rsp+0DA8h+var_388], xmm0
0x180051f02  movups  [rsp+0DA8h+var_378], xmm0
0x180051f0a  movups  [rsp+0DA8h+var_368], xmm0
0x180051f12  mov     rcx, rdi; this
0x180051f15  call    ?GetLoggingVolumeDriveLetter@CFveApiBase@@QEAAPEBGXZ; CFveApiBase::GetLoggingVolumeDriveLetter(void)
0x180051f1a  mov     r9, rax; unsigned __int16 *
0x180051f1d  lea     r8, aVolumedrivelet; "VolumeDriveLetter"
0x180051f24  lea     rcx, [rsp+0DA8h+var_388]; struct _FVEAPI_EVENT_DATA *
0x180051f2c  call    ?FveApiEventLogDeclareWSTRING@@YAXAEAU_FVEAPI_EVENT_DATA@@PEBG11K@Z; FveApiEventLogDeclareWSTRING(_FVEAPI_EVENT_DATA &,ushort const *,ushort const *,ushort const *,ulong)
0x180051f31  mov     rcx, qword ptr [rsp+0DA8h+var_8F8+8]
0x180051f39  lea     rax, [rsp+0DA8h+var_8F8]
0x180051f41  cmp     [rcx], rax
0x180051f44  jnz     loc_1800535F4
0x180051f4a  lea     rax, [rsp+0DA8h+var_8F8]
0x180051f52  mov     qword ptr [rsp+0DA8h+var_388], rax
0x180051f5a  mov     qword ptr [rsp+0DA8h+var_388+8], rcx
0x180051f62  lea     rax, [rsp+0DA8h+var_388]
0x180051f6a  mov     [rcx], rax
0x180051f6d  lea     rax, [rsp+0DA8h+var_388]
0x180051f75  mov     qword ptr [rsp+0DA8h+var_8F8+8], rax
0x180051f7d  lea     rax, FVEAPI_OP_INITIALIZATION_HW_DISABLED
0x180051f84  mov     qword ptr [rsp+0DA8h+var_908+8], rax
0x180051f8c  lea     rdx, [rsp+0DA8h+var_908]; struct _FVEAPI_EVENT_DATA_COLLECTION *
0x180051f94  lea     rcx, [rsp+0DA8h+var_D50]; this
0x180051f99  call    ?LogFveApiEvent@FveEventLogHandle@@QEAAJPEAU_FVEAPI_EVENT_DATA_COLLECTION@@@Z; FveEventLogHandle::LogFveApiEvent(_FVEAPI_EVENT_DATA_COLLECTION *)
0x180051f9e  lea     rcx, [rsp+0DA8h+var_D50]; this
0x180051fa3  call    ?EventLogCleanup@FveEventLogHandle@@AEAAXXZ; FveEventLogHandle::EventLogCleanup(void)
0x180051fa8  mov     al, 1
0x180051faa  mov     [rsp+0DA8h+var_D68], al
0x180051fae  mov     r15d, 2
0x180051fb4  mov     dword ptr [rsp+0DA8h+var_D5E+2], r15d
0x180051fb9  xor     edx, edx
0x180051fbb  jmp     loc_180053612
0x180051fc0  test    dword ptr [rdi+6Ch], 10000001h
0x180051fc7  jz      loc_180052258
0x180051fcd  lea     rcx, [rsp+0DA8h+var_D54]; enum _FIRMWARE_TYPE *
0x180051fd2  call    ?FveGetFirmwareType@@YAJPEAW4_FIRMWARE_TYPE@@@Z; FveGetFirmwareType(_FIRMWARE_TYPE *)
0x180051fd7  mov     ebx, eax
0x180051fd9  mov     [rsp+0DA8h+var_D64], eax
0x180051fdd  xor     edx, edx
0x180051fdf  test    eax, eax
0x180051fe1  js      loc_180051CF6
0x180051fe7  cmp     [rsp+0DA8h+var_D54], 2
0x180051fec  jnz     short loc_180052008
0x180051fee  lea     rdx, [rsp+0DA8h+var_D60]; bool *
0x180051ff3  call    ?EDriveSupportedInBoot@CFveApi@@IEAAJPEA_N@Z; CFveApi::EDriveSupportedInBoot(bool *)
0x180051ff8  mov     ebx, eax
0x180051ffa  mov     [rsp+0DA8h+var_D64], eax
0x180051ffe  xor     edx, edx
0x180052000  test    eax, eax
0x180052002  js      loc_180051CF6
0x180052008  cmp     [rsp+0DA8h+var_D60], dl
0x18005200c  jnz     loc_180052258
0x180052012  mov     [r12], dl
0x180052016  xorps   xmm0, xmm0
0x180052019  movups  [rsp+0DA8h+var_8E8], xmm0
0x180052021  movups  [rsp+0DA8h+var_8D8], xmm0
0x180052029  mov     [rsp+0DA8h+var_D00], rdx
0x180052031  mov     [rsp+0DA8h+var_CF8], rdx
0x180052039  mov     [rsp+0DA8h+var_CF0], rdx
0x180052041  lea     rax, [rsp+0DA8h+var_8D8]
0x180052049  mov     qword ptr [rsp+0DA8h+var_8D8+8], rax
0x180052051  lea     rax, [rsp+0DA8h+var_8D8]
0x180052059  mov     qword ptr [rsp+0DA8h+var_8D8], rax
0x180052061  mov     rax, [rdi+490h]
0x180052068  add     rax, 10h
0x18005206c  movdqu  [rsp+0DA8h+var_B08], xmm0
0x180052075  lea     rsi, aProtectorguid_0; "ProtectorGuid"
0x18005207c  mov     [rsp+0DA8h+var_AF8], rsi
0x180052084  lea     r14, aGuid; "GUID"
0x18005208b  mov     [rsp+0DA8h+var_AF0], r14
0x180052093  mov     [rsp+0DA8h+var_AE8], rax
0x18005209b  mov     [rsp+0DA8h+var_AE0], 10h
0x1800520a6  mov     [rsp+0DA8h+var_5E8], rsi
0x1800520ae  mov     [rsp+0DA8h+var_5E0], r14
0x1800520b6  mov     [rsp+0DA8h+var_5D8], rax
0x1800520be  mov     [rsp+0DA8h+var_5D0], 10h
0x1800520ca  lea     rax, [rsp+0DA8h+var_8D8]
0x1800520d2  mov     [rsp+0DA8h+var_5F8], rax
0x1800520da  lea     rax, [rsp+0DA8h+var_8D8]
0x1800520e2  mov     [rsp+0DA8h+var_5F0], rax
0x1800520ea  lea     rax, [rsp+0DA8h+var_5F8]
0x1800520f2  mov     qword ptr [rsp+0DA8h+var_8D8], rax
0x1800520fa  lea     rax, [rsp+0DA8h+var_5F8]
0x180052102  mov     qword ptr [rsp+0DA8h+var_8D8+8], rax
0x18005210a  movups  [rsp+0DA8h+var_328], xmm0
0x180052112  movups  [rsp+0DA8h+var_318], xmm0
0x18005211a  movups  [rsp+0DA8h+var_308], xmm0
0x180052122  mov     rcx, rdi; this
0x180052125  call    ?GetLoggingVolumePath@CFveApiBase@@QEAAPEBGXZ; CFveApiBase::GetLoggingVolumePath(void)
0x18005212a  mov     r9, rax; unsigned __int16 *
0x18005212d  lea     r8, aVolumepath; "VolumePath"
0x180052134  lea     rcx, [rsp+0DA8h+var_328]; struct _FVEAPI_EVENT_DATA *
0x18005213c  call    ?FveApiEventLogDeclareWSTRING@@YAXAEAU_FVEAPI_EVENT_DATA@@PEBG11K@Z; FveApiEventLogDeclareWSTRING(_FVEAPI_EVENT_DATA &,ushort const *,ushort const *,ushort const *,ulong)
0x180052141  mov     rcx, qword ptr [rsp+0DA8h+var_8D8+8]
0x180052149  lea     rax, [rsp+0DA8h+var_8D8]
0x180052151  cmp     [rcx], rax
0x180052154  jnz     loc_1800535F4
0x18005215a  lea     rax, [rsp+0DA8h+var_8D8]
0x180052162  mov     qword ptr [rsp+0DA8h+var_328], rax
0x18005216a  mov     qword ptr [rsp+0DA8h+var_328+8], rcx
0x180052172  lea     rax, [rsp+0DA8h+var_328]
0x18005217a  mov     [rcx], rax
  ... truncated ...
```
