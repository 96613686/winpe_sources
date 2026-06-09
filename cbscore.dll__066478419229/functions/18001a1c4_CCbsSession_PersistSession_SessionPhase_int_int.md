# CCbsSession::PersistSession(SessionPhase *,int,int)

- ea: `0x18001a1c4`
- end: `0x18001d158`
- name: `?PersistSession@CCbsSession@@QEAAJPEAUSessionPhase@@HH@Z`
- size: `12180`
- prototype: `__int64 __fastcall(CCbsSession *__hidden this, struct SessionPhase *, int, int)`
- caller_count: `16`
- callee_count: `36`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800aea00`
- `0x1800e23c4`
- `0x1800e43ec`
- `0x1801d13c8`
- `0x1801d14e8`
- `0x1801d1668`
- `0x1801d1784`
- `0x1801d1838`
- `0x1801d1b14`
- `0x1801d1bd0`
- `0x1801d1c90`
- `0x1801d1d44`
- `0x1801d1f78`
- `0x1801d203c`
- `0x1801d2174`
- `0x1801d23c0`

## callees

- `0x180010b60`
- `0x180013250`
- `0x180019bdc`
- `0x18001a160`
- `0x18001a1c4`
- `0x18001d160`
- `0x180042130`
- `0x180043840`
- `0x18004b304`
- `0x18004bf9c`
- `0x18004d564`
- `0x180051c8c`
- `0x18005a2a0`
- `0x1800653d8`
- `0x18006a764`
- `0x18008f908`
- `0x180093c4c`
- `0x180098538`
- `0x180099390`
- `0x180099548`
- `0x18009cf78`
- `0x1800a26b0`
- `0x1800a8678`
- `0x1800ad504`
- `0x1800b2990`
- `0x1800b851c`
- `0x1800d0588`
- `0x1800eb920`
- `0x1800ec920`
- `0x1800fe364`
- `0x180128c10`
- `0x18012b5e4`
- `0x1801d5f70`
- `0x1801d6150`
- `0x1801fc814`
- `0x1802d5010`

## string_xrefs

- `0x18001c15c`: `update`
- `0x18001b6c2`: `Complete`
- `0x18001cbd0`: `Failed to open actions.`
- `0x18001ccd4`: `Failed to open actions.`
- `0x18001ba61`: `Failed to open tasks element.`
- `0x18001ba16`: `Tasks`
- `0x18001cc18`: `Tasks`
- `0x18001b9cf`: `Failed to close update element.`
- `0x18001bad0`: `Failed to close update element.`
- `0x18001c758`: `Failed to close update element.`
- `0x18001a53d`: `Failed to open session element.`
- `0x18001a4a3`: `Failed to create XML writter.`
- `0x18001a41b`: `Failed to create string builder.`
- `0x18001c808`: `Failed to emit update name.`
- `0x18001c860`: `Failed to open update element.`
- `0x18001c6a8`: `Failed to open package element.`
- `0x18001ca70`: `Failed to open package element.`
- `0x18001cc46`: `Failed to close tasks.`
- `0x18001b0fd`: `Failed to emit finalize WinRE Command.`
- `0x18001b0bb`: `finalizeWinRECommand`
- `0x18001a390`: `Failed to mark session complete on session: {}`

## pseudocode

```c
__int64 __fastcall CCbsSession::PersistSession(CCbsSession *this, struct SessionPhase *a2, int a3, int a4)
{
  unsigned __int64 v7; // r15
  __int64 v9; // r9
  unsigned int v10; // eax
  __int64 v11; // r8
  int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // rcx
  unsigned int v15; // edi
  int v16; // edx
  int v18; // eax
  int v19; // edx
  __int64 v20; // rdx
  unsigned __int64 v21; // r9
  int v22; // eax
  int v23; // edi
  int v24; // edx
  __int64 v25; // rdx
  int v26; // eax
  int v27; // edx
  struct Windows::Microdom::Rtl::IRtlXmlWriter *v28; // rbx
  __int64 v29; // rax
  int v30; // eax
  int v31; // edx
  __int64 (__fastcall *v32)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *); // rdi
  __int64 v33; // rax
  __int64 v34; // xmm1_8
  int v35; // eax
  int v36; // edx
  __int64 (__fastcall *v37)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *); // rdi
  __int64 v38; // rax
  __int64 v39; // xmm1_8
  int v40; // eax
  int v41; // edx
  __int64 (__fastcall *v42)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *); // rdi
  __int64 v43; // rax
  __int64 v44; // xmm1_8
  int v45; // eax
  int v46; // edx
  __int64 (__fastcall *v47)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *); // rdi
  wchar_t *v48; // rax
  __int64 v49; // rax
  __int64 v50; // xmm1_8
  int v51; // eax
  int v52; // edx
  __int64 (__fastcall *v53)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *); // rdi
  wchar_t *v54; // rax
  __int64 v55; // rax
  __int64 v56; // xmm1_8
  int v57; // eax
  int v58; // edx
  __int64 (__fastcall *v59)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *); // rdi
  __int64 v60; // rax
  __int64 v61; // rax
  __int64 v62; // xmm1_8
  int v63; // eax
  int v64; // edx
  const wchar_t *v65; // rdx
  __int64 (__fastcall *v66)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *); // rdi
  __int64 v67; // rax
  __int64 v68; // xmm1_8
  int v69; // eax
  int v70; // edx
  const wchar_t *v71; // rdx
  __int64 (__fastcall *v72)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *); // rdi
  __int64 v73; // rax
  __int64 v74; // xmm1_8
  int v75; // eax
  int v76; // edx
  unsigned int v77; // ecx
  __int64 (__fastcall *v78)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *); // rdi
  wchar_t *v79; // rax
  __int64 v80; // rax
  __int64 v81; // xmm1_8
  int v82; // eax
  int v83; // edx
  int v84; // eax
  int v85; // edx
  __int64 (__fastcall *v86)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *); // rdi
  __int64 v87; // rax
  __int64 v88; // xmm1_8
  int v89; // eax
  unsigned int v90; // edi
  int v91; // edx
  __int64 (__fastcall *v92)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *); // rdi
  wchar_t *v93; // rax
  __int64 v94; // rax
  __int64 v95; // xmm1_8
  int v96; // eax
  int v97; // edx
  volatile signed __int64 *v98; // rcx
  int v99; // eax
  __int64 (__fastcall *v100)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *); // rdi
  __int64 v101; // rax
  __int64 v102; // xmm1_8
  int v103; // eax
  int v104; // edx
  __int64 v105; // rdx
  struct Windows::Microdom::Rtl::IRtlXmlWriter *v106; // rsi
  __int64 (__fastcall *v107)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *); // rdi
  __int64 v108; // rax
  __int64 v109; // xmm1_8
  int v110; // eax
  int v111; // edx
  __int64 v112; // rdx
  __int64 (__fastcall *v113)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *); // rdi
  __int64 v114; // rax
  __int64 v115; // xmm1_8
  int v116; // eax
  int v117; // edx
  __int64 (__fastcall *v118)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *); // rdi
  __int64 v119; // rax
  __int64 v120; // xmm1_8
  int v121; // eax
  int v122; // edx
  __int64 (__fastcall *v123)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *); // rdi
  __int64 v124; // rax
  __int64 v125; // xmm1_8
  int v126; // eax
  int v127; // edx
  __int64 (__fastcall *v128)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *); // rdi
  __int64 v129; // rax
  __int64 v130; // xmm1_8
  int v131; // eax
  int v132; // edx
  __int64 (__fastcall *v133)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *); // rdi
  wchar_t *v134; // rax
  __int64 v135; // rax
  __int64 v136; // xmm1_8
  int v137; // eax
  int v138; // edx
  __int64 v139; // rdx
  __int64 (__fastcall *v140)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *); // rdi
  __int64 v141; // rax
  __int64 v142; // xmm1_8
  int v143; // eax
  int v144; // edx
  __int64 v145; // rdx
  __int64 (__fastcall *v146)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *); // rdi
  __int64 v147; // rax
  __int64 v148; // xmm1_8
  int v149; // eax
  int v150; // edx
  int v151; // edx
  const wchar_t *v152; // rax
  const wchar_t *v153; // rax
  int LocalTimeString; // edi
  __int64 (__fastcall *v155)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *); // rdi
  __int64 v156; // rax
  __int64 v157; // xmm1_8
  int v158; // eax
  int v159; // edx
  __int64 (__fastcall *v160)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *); // rdi
  wchar_t *v161; // rax
  __int64 v162; // rax
  __int64 v163; // xmm1_8
  int v164; // eax
  int v165; // edx
  __int64 v166; // rdx
  __int64 (__fastcall *v167)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *); // rdi
  __int64 v168; // rax
  __int64 v169; // xmm1_8
  int v170; // eax
  int v171; // edx
  __int64 v172; // rdx
  __int64 (__fastcall *v173)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *); // rdi
  __int64 v174; // rax
  __int64 v175; // xmm1_8
  int v176; // eax
  int v177; // edx
  int v178; // eax
  int v179; // edx
  __int64 v180; // rax
  int v181; // eax
  int v182; // edx
  int v183; // eax
  int v184; // edx
  unsigned __int64 i; // r13
  __int64 v186; // rax
  __int64 (__fastcall *v187)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *); // rax
  __int64 (__fastcall *v188)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *); // rdi
  wchar_t *v189; // rax
  __int64 v190; // rax
  __int64 v191; // xmm1_8
  unsigned __int64 v192; // rdx
  __int64 v193; // rax
  __int64 v194; // rsi
  __int64 v195; // rax
  __int64 v196; // rcx
  __int64 (__fastcall *v197)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *); // rdi
  wchar_t *FastCbsIdentityString; // rax
  __int64 v199; // rax
  __int64 v200; // xmm1_8
  __int64 v201; // rdx
  __int64 (__fastcall *v202)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *); // rdi
  __int64 v203; // rax
  __int64 v204; // xmm1_8
  __int64 v205; // rdx
  __int64 (__fastcall *v206)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *); // rdi
  __int64 v207; // rax
  __int64 v208; // xmm1_8
  __int64 (__fastcall *v209)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *); // rdi
  __int64 v210; // rax
  __int64 v211; // rax
  __int64 v212; // xmm1_8
  __int64 (__fastcall *v213)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *); // rdi
  wchar_t *v214; // rax
  __int64 v215; // rax
  __int64 v216; // xmm1_8
  wchar_t *v217; // r12
  unsigned __int64 v218; // rdx
  __int64 v219; // rax
  __int64 v220; // rsi
  __int64 v221; // rax
  __int64 (__fastcall *v222)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *); // rdi
  __int64 v223; // rax
  const wchar_t *v224; // rdx
  __int64 v225; // rax
  __int64 v226; // xmm1_8
  const wchar_t **v227; // r15
  __int64 v228; // rcx
  const wchar_t *v229; // rdx
  __int64 (__fastcall *v230)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *); // rdi
  __int64 v231; // rax
  __int64 v232; // xmm1_8
  __int64 (__fastcall *v233)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *); // rdi
  __int64 v234; // rax
  __int64 v235; // rax
  __int64 v236; // xmm1_8
  __int64 (__fastcall *v237)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *); // rdi
  wchar_t *v238; // rax
  __int64 v239; // rax
  __int64 v240; // xmm1_8
  unsigned __int64 j; // r15
  unsigned __int64 v242; // rax
  __int64 v243; // r12
  __int64 v244; // rax
  __int64 (__fastcall *v245)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *); // rdi
  __int64 v246; // rax
  __int64 v247; // xmm1_8
  __int64 (__fastcall *v248)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *); // rdi
  __int64 v249; // rax
  __int64 v250; // rax
  __int64 v251; // xmm1_8
  unsigned int v252; // ecx
  __int64 (__fastcall *v253)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *); // rdi
  wchar_t *v254; // rax
  __int64 v255; // rax
  __int64 v256; // xmm1_8
  int v257; // eax
  int v258; // edx
  bool v259; // zf
  __int64 v260; // rax
  __int64 (__fastcall *v261)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *); // rax
  int v262; // eax
  int v263; // edx
  __int64 v264; // rax
  int v265; // edx
  int v266; // edx
  int v267; // edx
  int v268; // edx
  int v269; // edx
  int v270; // edx
  int v271; // edx
  int v272; // edx
  int v273; // edx
  int v274; // edx
  int v275; // edx
  int v276; // edx
  int v277; // edx
  int v278; // edx
  int v279; // edx
  int v280; // edx
  int v281; // edx
  int v282; // edx
  int v283; // edx
  int v284; // edx
  int v285; // edx
  int v286; // edx
  __int64 (__fastcall *v287)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *); // rax
  int v288; // eax
  int v289; // edx
  __int64 v290; // rax
  int v291; // eax
  int v292; // edx
  int v293; // eax
  int v294; // edx
  int v295; // r12d
  unsigned __int64 k; // rsi
  struct SessionPhase *v297; // r15
  struct SessionPhase *v298; // r8
  int v299; // edx
  int v300; // edx
  struct SessionPhase *v301; // r8
  int v302; // eax
  int v303; // edx
  __int64 v304; // rax
  int v305; // eax
  int v306; // edx
  __int64 v307; // rax
  int v308; // eax
  int v309; // edx
  int v310; // eax
  int v311; // edx
  int v312; // eax
  int v313; // edx
  int v314; // [rsp+20h] [rbp-E0h]
  int *v315; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v316; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v317; // [rsp+40h] [rbp-C0h]
  const wchar_t *v318; // [rsp+48h] [rbp-B8h]
  wchar_t *v319; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v320; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v321; // [rsp+68h] [rbp-98h]
  _BYTE v322[24]; // [rsp+70h] [rbp-90h] BYREF
  wchar_t *v323; // [rsp+88h] [rbp-78h] BYREF
  struct Windows::Microdom::Rtl::IRtlXmlWriter *v324; // [rsp+90h] [rbp-70h] BYREF
  __int64 v325; // [rsp+98h] [rbp-68h] BYREF
  __int64 v326; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v327; // [rsp+A8h] [rbp-58h] BYREF
  int *v328; // [rsp+B0h] [rbp-50h] BYREF
  int v329; // [rsp+B8h] [rbp-48h] BYREF
  int v330[2]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int64 v331[2]; // [rsp+C8h] [rbp-38h] BYREF
  unsigned __int8 *v332; // [rsp+D8h] [rbp-28h]
  char v333[144]; // [rsp+E0h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+B8h]

  v330[0] = a4;
  v7 = 0;
  v323 = 0;
  v327 = 0;
  memset_0(v333, 0, 0x81u);
  v326 = 0;
  v325 = 0;
  v324 = 0;
  v9 = 208;
  v332 = 0;
  *(_OWORD *)v331 = 0;
  if ( !a4 )
    v9 = *((unsigned int *)this + 192);
  v10 = *((_DWORD *)a2 + 80);
  v11 = v10 + 10000;
  if ( !*((_DWORD *)a2 + 82) )
    v11 = v10;
  v12 = PackageStorePersistSessionState(this, 0, v11, v9);
  v15 = v12;
  if ( v12 >= 0 )
  {
    if ( a3 )
    {
      if ( !a4 )
      {
LABEL_12:
        v15 = 0;
LABEL_13:
        Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(v331);
        Windows::Auto<Windows::Rtl::IRtlIniFile *>::~Auto<Windows::Rtl::IRtlIniFile *>(&v324);
        Windows::Auto<Windows::Rtl::IRtlIniFile *>::~Auto<Windows::Rtl::IRtlIniFile *>(&v325);
        Windows::Auto<Windows::Rtl::IRtlIniFile *>::~Auto<Windows::Rtl::IRtlIniFile *>(&v326);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v327);
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v323);
        return v15;
      }
    }
    else if ( !a4 )
    {
      goto LABEL_22;
    }
    v18 = PackageStoreMarkSessionComplete(this, 0);
    v15 = v18;
    if ( v18 < 0 )
    {
      v329 = v18;
      if ( LogAdapter::g_Logger )
      {
        v319 = (wchar_t *)*((_QWORD *)this + 80);
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (_DWORD)LogAdapter::g_Logger,
          0,
          3,
          (unsigned int)"Failed to mark session complete on session: {}",
          (__int64)&v319);
        *(_QWORD *)v330 = &v329;
        LOBYTE(v19) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v19,
          3,
          (unsigned int)": {}",
          (__int64)v330);
      }
      v20 = 415;
      goto LABEL_20;
    }
LABEL_22:
    v22 = RtlCreateUtf8UCSStringBuilder(v14, v13, &v326, &v325);
    v23 = v22;
    if ( v22 < 0 )
    {
      v329 = v22;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to create string builder.");
        v319 = (wchar_t *)&v329;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v24,
          3,
          (unsigned int)": {}",
          (__int64)&v319);
      }
      v25 = 420;
      goto LABEL_26;
    }
    v26 = RtlCreateDefaultXmlWriter(10, v325, &v324);
    v23 = v26;
    if ( v26 < 0 )
    {
      v329 = v26;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to create XML writter.");
        v319 = (wchar_t *)&v329;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v27,
          3,
          (unsigned int)": {}",
          (__int64)&v319);
      }
      v25 = 427;
      goto LABEL_26;
    }
    v28 = v324;
    v29 = *(_QWORD *)v324;
    v318 = L"Session";
    v316 = 14;
    v317 = 16;
    v30 = (*(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *))(v29 + 16))(
            v324,
            0,
            &v316);
    v23 = v30;
    if ( v30 < 0 )
    {
      v329 = v30;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to open session element.");
        v319 = (wchar_t *)&v329;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v31,
          3,
          (unsigned int)": {}",
          (__int64)&v319);
      }
      v25 = 464;
      goto LABEL_26;
    }
    v32 = *(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *))(*(_QWORD *)v28 + 88LL);
    v33 = StringToUnicodeString(v322, L"8.0");
    v320 = *(_OWORD *)v33;
    v34 = *(_QWORD *)(v33 + 16);
    v318 = L"version";
    v321 = v34;
    v316 = 14;
    v317 = 16;
    v35 = v32(v28, 0, &v316, &v320);
    v23 = v35;
    if ( v35 < 0 )
    {
      v329 = v35;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to emit version.");
        v319 = (wchar_t *)&v329;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v36,
          3,
          (unsigned int)": {}",
          (__int64)&v319);
      }
      v25 = 468;
      goto LABEL_26;
    }
    v37 = *(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *))(*(_QWORD *)v28 + 88LL);
    v38 = StringToUnicodeString(v322, *((_QWORD *)this + 80));
    v320 = *(_OWORD *)v38;
    v39 = *(_QWORD *)(v38 + 16);
    v318 = L"id";
    v321 = v39;
    v316 = 4;
    v317 = 6;
    v40 = v37(v28, 0, &v316, &v320);
    v23 = v40;
    if ( v40 < 0 )
    {
      v329 = v40;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to emit session id.");
        v319 = (wchar_t *)&v329;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v41,
          3,
          (unsigned int)": {}",
          (__int64)&v319);
      }
      v25 = 471;
      goto LABEL_26;
    }
    v42 = *(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *))(*(_QWORD *)v28 + 88LL);
    v43 = StringToUnicodeString(v322, *((_QWORD *)this + 81));
    v320 = *(_OWORD *)v43;
    v44 = *(_QWORD *)(v43 + 16);
    v318 = L"client";
    v321 = v44;
    v316 = 12;
    v317 = 14;
    v45 = v42(v28, 0, &v316, &v320);
    v23 = v45;
    if ( v45 < 0 )
    {
      v329 = v45;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to emit client.");
        v319 = (wchar_t *)&v329;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v46,
          3,
          (unsigned int)": {}",
          (__int64)&v319);
      }
      v25 = 475;
      goto LABEL_26;
    }
    v47 = *(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *))(*(_QWORD *)v28 + 88LL);
    v48 = numToString(*((_DWORD *)this + 172));
    v49 = StringToUnicodeString(v322, v48);
    v320 = *(_OWORD *)v49;
    v50 = *(_QWORD *)(v49 + 16);
    v318 = L"options";
    v321 = v50;
    v316 = 14;
    v317 = 16;
    v51 = v47(v28, 0, &v316, &v320);
    v23 = v51;
    if ( v51 < 0 )
    {
      v329 = v51;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to emit options.");
        v319 = (wchar_t *)&v329;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v52,
          3,
          (unsigned int)": {}",
          (__int64)&v319);
      }
      v25 = 479;
      goto LABEL_26;
    }
    v53 = *(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *))(*(_QWORD *)v28 + 88LL);
    v54 = numToString(*((_DWORD *)this + 254));
    v55 = StringToUnicodeString(v322, v54);
    v320 = *(_OWORD *)v55;
    v56 = *(_QWORD *)(v55 + 16);
    v318 = L"currentPhase";
    v321 = v56;
    v316 = 24;
    v317 = 26;
    v57 = v53(v28, 0, &v316, &v320);
    v23 = v57;
    if ( v57 < 0 )
    {
      v329 = v57;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to emit currentPhase.");
        v319 = (wchar_t *)&v329;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v58,
          3,
          (unsigned int)": {}",
          (__int64)&v319);
      }
      v25 = 486;
      goto LABEL_26;
    }
    v59 = *(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *))(*(_QWORD *)v28 + 88LL);
    v60 = CbsSessionStateToString(*((unsigned int *)this + 192));
    v61 = StringToUnicodeString(v322, v60);
    v320 = *(_OWORD *)v61;
    v62 = *(_QWORD *)(v61 + 16);
    v318 = L"lastSuccessfulState";
    v321 = v62;
    v316 = 38;
    v317 = 40;
    v63 = v59(v28, 0, &v316, &v320);
    v23 = v63;
    if ( v63 < 0 )
    {
      v329 = v63;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to emit lastSuccessfulState.");
        v319 = (wchar_t *)&v329;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v64,
          3,
          (unsigned int)": {}",
          (__int64)&v319);
      }
      v25 = 493;
      goto LABEL_26;
    }
    v65 = L"true";
    if ( !*((_DWORD *)this + 220) )
      v65 = L"false";
    v66 = *(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *))(*(_QWORD *)v28 + 88LL);
    v67 = StringToUnicodeString(v322, v65);
    v320 = *(_OWORD *)v67;
    v68 = *(_QWORD *)(v67 + 16);
    v318 = L"pendingFollower";
    v321 = v68;
    v316 = 30;
    v317 = 32;
    v69 = v66(v28, 0, &v316, &v320);
    v23 = v69;
    if ( v69 < 0 )
    {
      v329 = v69;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to emit pendingFollower.");
        v319 = (wchar_t *)&v329;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v70,
          3,
          (unsigned int)": {}",
          (__int64)&v319);
      }
      v25 = 500;
      goto LABEL_26;
    }
    v71 = L"true";
    if ( !*((_DWORD *)this + 264) )
      v71 = L"false";
    v72 = *(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *))(*(_QWORD *)v28 + 88LL);
    v73 = StringToUnicodeString(v322, v71);
    v320 = *(_OWORD *)v73;
    v74 = *(_QWORD *)(v73 + 16);
    v318 = L"retry";
    v321 = v74;
    v316 = 10;
    v317 = 12;
    v75 = v72(v28, 0, &v316, &v320);
    v23 = v75;
    if ( v75 < 0 )
    {
      v329 = v75;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to emit retry.");
        v319 = (wchar_t *)&v329;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v76,
          3,
          (unsigned int)": {}",
          (__int64)&v319);
      }
      v25 = 507;
      goto LABEL_26;
    }
    v77 = *((_DWORD *)this + 553);
    if ( v77 )
    {
      v78 = *(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *))(*(_QWORD *)v28 + 88LL);
      v79 = numToString(v77);
      v80 = StringToUnicodeString(v322, v79);
      v320 = *(_OWORD *)v80;
      v81 = *(_QWORD *)(v80 + 16);
      v318 = L"UUPOperation";
      v321 = v81;
      v316 = 24;
      v317 = 26;
      v82 = v78(v28, 0, &v316, &v320);
      v23 = v82;
      if ( v82 < 0 )
      {
        v329 = v82;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to emit UUP operation.");
          v319 = (wchar_t *)&v329;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v83,
            3,
            (unsigned int)": {}",
            (__int64)&v319);
        }
        v25 = 516;
        goto LABEL_26;
      }
    }
    if ( *((_QWORD *)this + 231) )
    {
      v319 = 0;
      v84 = CCbsStringArray::SaveAsStringList((CCbsSession *)((char *)this + 1824), L";", &v319);
      v15 = v84;
      if ( v84 < 0 )
      {
        v329 = v84;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Out of memory");
          *(_QWORD *)v330 = &v329;
          LOBYTE(v85) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v85,
            3,
            (unsigned int)": {}",
            (__int64)v330);
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x20A,
          (unsigned int)"onecore\\base\\cbs\\core\\cbssessionpersistence.cpp",
          (const char *)v15,
          v314);
LABEL_81:
        Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v319);
        goto LABEL_13;
      }
      v86 = *(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *))(*(_QWORD *)v28 + 88LL);
      v87 = StringToUnicodeString(v322, v319);
      v320 = *(_OWORD *)v87;
      v88 = *(_QWORD *)(v87 + 16);
      v318 = L"onDemandFeatureList";
      v321 = v88;
      v316 = 38;
      v317 = 40;
      v89 = v86(v28, 0, &v316, &v320);
      v90 = v89;
      if ( v89 < 0 )
      {
        v329 = v89;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to emit client.");
          *(_QWORD *)v330 = &v329;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v91,
            3,
            (unsigned int)": {}",
            (__int64)v330);
        }
        v15 = wil::details::in1diag3::Return_NtStatus(
                retaddr,
                (void *)0x20D,
                (unsigned int)"onecore\\base\\cbs\\core\\cbssessionpersistence.cpp",
                (const char *)v90,
                v314);
        goto LABEL_81;
      }
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&v319);
    }
    v92 = *(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *))(*(_QWORD *)v28 + 88LL);
    v93 = numToString(*((_DWORD *)this + 552));
    v94 = StringToUnicodeString(v322, v93);
    v320 = *(_OWORD *)v94;
    v95 = *(_QWORD *)(v94 + 16);
    v318 = L"operationCovered";
    v321 = v95;
    v316 = 32;
    v317 = 34;
    v96 = v92(v28, 0, &v316, &v320);
    v23 = v96;
    if ( v96 < 0 )
    {
      v329 = v96;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to emit operation covered.");
        v319 = (wchar_t *)&v329;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v97,
          3,
          (unsigned int)": {}",
          (__int64)&v319);
      }
      v25 = 533;
      goto LABEL_26;
    }
    v98 = (volatile signed __int64 *)*((_QWORD *)this + 82);
    if ( v98
      && TraceLoggingCorrelationVector::ToStringImpl(
           (TraceLoggingCorrelationVector *)v98,
           _InterlockedExchangeAdd64(v98 + 17, 0),
           v333) )
    {
      v99 = SczAllocFromAnsiSz(&v327, v333);
      v15 = v99;
      if ( v99 < 0 )
      {
        v21 = (unsigned int)v99;
        v20 = 537;
        goto LABEL_21;
      }
      v100 = *(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *))(*(_QWORD *)v28 + 88LL);
      v101 = StringToUnicodeString(v322, v327);
      v320 = *(_OWORD *)v101;
      v102 = *(_QWORD *)(v101 + 16);
      v318 = L"correlationVector";
      v321 = v102;
      v316 = 34;
      v317 = 36;
      v103 = v100(v28, 0, &v316, &v320);
      v23 = v103;
      if ( v103 < 0 )
      {
        v329 = v103;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to emit correlationVector.");
          v319 = (wchar_t *)&v329;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v104,
            3,
            (unsigned int)": {}",
            (__int64)&v319);
        }
        v25 = 541;
        goto LABEL_26;
      }
    }
    else
    {
      LogAdapter::TraceAtLevel<>(1, "Unable to get correlation vector string");
    }
    v105 = *((_QWORD *)this + 277);
    v106 = v28;
    if ( v105 )
    {
      v107 = *(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *))(*(_QWORD *)v28 + 88LL);
      v108 = StringToUnicodeString(v322, v105);
      v320 = *(_OWORD *)v108;
      v109 = *(_QWORD *)(v108 + 16);
      v318 = L"usoCorrelationVector";
      v321 = v109;
      v316 = 40;
      v317 = 42;
      v110 = v107(v28, 0, &v316, &v320);
      v23 = v110;
      if ( v110 < 0 )
      {
        v329 = v110;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to emit correlationVector.");
          v319 = (wchar_t *)&v329;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v111,
            3,
            (unsigned int)": {}",
            (__int64)&v319);
        }
        v25 = 555;
        goto LABEL_26;
      }
    }
    v112 = *((_QWORD *)this + 216);
    if ( v112 )
    {
      v113 = *(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *))(*(_QWORD *)v28 + 88LL);
      v114 = StringToUnicodeString(v322, v112);
      v320 = *(_OWORD *)v114;
      v115 = *(_QWORD *)(v114 + 16);
      v318 = L"finalizeWinRECommand";
      v321 = v115;
      v316 = 40;
      v317 = 42;
      v116 = v113(v28, 0, &v316, &v320);
      v23 = v116;
      if ( v116 < 0 )
      {
        v329 = v116;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to emit finalize WinRE Command.");
          v319 = (wchar_t *)&v329;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v117,
            3,
            (unsigned int)": {}",
            (__int64)&v319);
        }
        v25 = 566;
        goto LABEL_26;
      }
    }
    if ( *((_BYTE *)this + 2272) )
    {
      v118 = *(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *))(*(_QWORD *)v28 + 88LL);
      v119 = StringToUnicodeString(v322, L"true");
      v320 = *(_OWORD *)v119;
      v120 = *(_QWORD *)(v119 + 16);
      v318 = L"onePackageSession";
      v321 = v120;
      v316 = 34;
      v317 = 36;
      v121 = v118(v28, 0, &v316, &v320);
      v23 = v121;
      if ( v121 < 0 )
      {
        v329 = v121;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to emit Onepackage session.");
          v319 = (wchar_t *)&v329;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v122,
            3,
            (unsigned int)": {}",
            (__int64)&v319);
        }
        v25 = 575;
        goto LABEL_26;
      }
      v123 = *(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *))(*(_QWORD *)v28 + 88LL);
      v124 = StringToUnicodeString(v322, *((_QWORD *)this + 288));
      v320 = *(_OWORD *)v124;
      v125 = *(_QWORD *)(v124 + 16);
      v318 = L"onePackageSandbox";
      v321 = v125;
      v316 = 34;
      v317 = 36;
      v126 = v123(v28, 0, &v316, &v320);
      v23 = v126;
      if ( v126 < 0 )
      {
        v329 = v126;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to emit Onepackage sandbox.");
          v319 = (wchar_t *)&v329;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v127,
            3,
            (unsigned int)": {}",
            (__int64)&v319);
        }
        v25 = 582;
        goto LABEL_26;
      }
      v128 = *(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *))(*(_QWORD *)v28 + 88LL);
      v129 = StringToUnicodeString(v322, *((_QWORD *)this + 287));
      v320 = *(_OWORD *)v129;
      v130 = *(_QWORD *)(v129 + 16);
      v318 = L"onePackageCab";
      v321 = v130;
      v316 = 26;
      v317 = 28;
      v131 = v128(v28, 0, &v316, &v320);
      v23 = v131;
      if ( v131 < 0 )
      {
        v329 = v131;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to emit Onepackage cab location.");
          v319 = (wchar_t *)&v329;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v132,
            3,
            (unsigned int)": {}",
            (__int64)&v319);
        }
        v25 = 589;
        goto LABEL_26;
      }
      v133 = *(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *))(*(_QWORD *)v28 + 88LL);
      v134 = numToString(*((_DWORD *)this + 572));
      v135 = StringToUnicodeString(v322, v134);
      v320 = *(_OWORD *)v135;
      v136 = *(_QWORD *)(v135 + 16);
      v318 = L"onePackagePackageType";
      v321 = v136;
      v316 = 42;
      v317 = 44;
      v137 = v133(v28, 0, &v316, &v320);
      v23 = v137;
      if ( v137 < 0 )
      {
        v329 = v137;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to emit Onepackage package type.");
          v319 = (wchar_t *)&v329;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v138,
            3,
            (unsigned int)": {}",
            (__int64)&v319);
        }
        v25 = 596;
        goto LABEL_26;
      }
    }
    v139 = *((_QWORD *)this + 289);
    if ( v139 )
    {
      v140 = *(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *))(*(_QWORD *)v28 + 88LL);
      v141 = StringToUnicodeString(v322, v139);
      v320 = *(_OWORD *)v141;
      v142 = *(_QWORD *)(v141 + 16);
      v318 = L"childMuV6SessionId";
      v321 = v142;
      v316 = 36;
      v317 = 38;
      v143 = v140(v28, 0, &v316, &v320);
      v23 = v143;
      if ( v143 < 0 )
      {
        v329 = v143;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to emit child MuV6 session id.");
          v319 = (wchar_t *)&v329;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v144,
            3,
            (unsigned int)": {}",
            (__int64)&v319);
        }
        v25 = 605;
        goto LABEL_26;
      }
    }
    v145 = *((_QWORD *)this + 292);
    if ( v145 )
    {
      v146 = *(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *))(*(_QWORD *)v28 + 88LL);
      v147 = StringToUnicodeString(v322, v145);
      v320 = *(_OWORD *)v147;
      v148 = *(_QWORD *)(v147 + 16);
      v318 = L"containerTransactionId";
      v321 = v148;
      v316 = 44;
      v317 = 46;
      v149 = v146(v28, 0, &v316, &v320);
      v23 = v149;
      if ( v149 < 0 )
      {
        v329 = v149;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            LogAdapter::g_Logger,
            0,
            3,
            "Failed to emit child container transaction id.");
          v319 = (wchar_t *)&v329;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v151,
            3,
            (unsigned int)": {}",
            (__int64)&v319);
        }
        v25 = 614;
        goto LABEL_26;
      }
      v328 = (int *)*((_QWORD *)this + 80);
      v315 = (int *)*((_QWORD *)this + 292);
      if ( LogAdapter::g_Logger )
      {
        LOBYTE(v150) = 1;
        LogAdapter::Logger::LogNumObjects<wchar_t const *,wchar_t *>(
          (_DWORD)LogAdapter::g_Logger,
          v150,
          1,
          (unsigned int)"Preserving '{}' as the container transaction id for session '{}'",
          (__int64)&v315,
          (__int64)&v328);
      }
    }
    if ( a4 )
    {
      v152 = (const wchar_t *)CbsSessionStateToString(32);
      CCbsSession::EmitAttribute(this, v28, v152, 1u, 0);
      v153 = (const wchar_t *)CbsSessionStateToString(48);
      CCbsSession::EmitAttribute(this, v28, v153, 1u, 0);
      LocalTimeString = GetLocalTimeString(&v323);
      LogAdapter::TraceAtLevelIfFailed<long,>(1, (unsigned int)LocalTimeString, "Unable to get local time");
      if ( LocalTimeString >= 0 )
      {
        v155 = *(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *))(*(_QWORD *)v28 + 88LL);
        v156 = StringToUnicodeString(v322, v323);
        v320 = *(_OWORD *)v156;
        v157 = *(_QWORD *)(v156 + 16);
        v318 = L"Complete";
        v321 = v157;
        v316 = 16;
        v317 = 18;
        v158 = v155(v28, 0, &v316, &v320);
        v23 = v158;
        if ( v158 < 0 )
        {
          v329 = v158;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to emit version.");
            v315 = &v329;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v159,
              3,
              (unsigned int)": {}",
              (__int64)&v315);
          }
          v25 = 634;
          goto LABEL_26;
        }
      }
      v160 = *(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *))(*(_QWORD *)v28 + 88LL);
      v161 = numToHexString(*((_DWORD *)this + 258));
      v162 = StringToUnicodeString(v322, v161);
      v320 = *(_OWORD *)v162;
      v163 = *(_QWORD *)(v162 + 16);
      v318 = L"status";
      v321 = v163;
      v316 = 12;
      v317 = 14;
      v164 = v160(v28, 0, &v316, &v320);
      v23 = v164;
      if ( v164 < 0 )
      {
        v329 = v164;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to persist status.");
          v315 = &v329;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v165,
            3,
            (unsigned int)": {}",
            (__int64)&v315);
        }
        v25 = 639;
        goto LABEL_26;
      }
      v166 = *((_QWORD *)this + 133);
      if ( v166 )
      {
        v167 = *(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *))(*(_QWORD *)v28 + 88LL);
        v168 = StringToUnicodeString(v322, v166);
        v320 = *(_OWORD *)v168;
        v169 = *(_QWORD *)(v168 + 16);
        v318 = L"Culprit";
        v321 = v169;
        v316 = 14;
        v317 = 16;
        v170 = v167(v28, 0, &v316, &v320);
        v23 = v170;
        if ( v170 < 0 )
        {
          v329 = v170;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to emit culprit package.");
            v315 = &v329;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v171,
              3,
              (unsigned int)": {}",
              (__int64)&v315);
          }
          v25 = 645;
          goto LABEL_26;
        }
      }
      v172 = *((_QWORD *)this + 134);
      if ( v172 )
      {
        v173 = *(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *))(*(_QWORD *)v28 + 88LL);
        v174 = StringToUnicodeString(v322, v172);
        v320 = *(_OWORD *)v174;
        v175 = *(_QWORD *)(v174 + 16);
        v318 = L"ErrorDetail";
        v321 = v175;
        v316 = 22;
        v317 = 24;
        v176 = v173(v28, 0, &v316, &v320);
        v23 = v176;
        if ( v176 < 0 )
        {
          v329 = v176;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to emit error detail.");
            v315 = &v329;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v177,
              3,
              (unsigned int)": {}",
              (__int64)&v315);
          }
          v25 = 652;
          goto LABEL_26;
        }
      }
    }
    v178 = (*(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD))(*(_QWORD *)v28 + 48LL))(
             v28,
             0);
    v23 = v178;
    if ( v178 < 0 )
    {
      v329 = v178;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to close update element.");
        v315 = &v329;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v179,
          3,
          (unsigned int)": {}",
          (__int64)&v315);
      }
      v25 = 656;
      goto LABEL_26;
    }
    v180 = *(_QWORD *)v28;
    v318 = L"Tasks";
    v316 = 10;
    v317 = 12;
    v181 = (*(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *))(v180 + 16))(
             v28,
             0,
             &v316);
    v23 = v181;
    if ( v181 < 0 )
    {
      v329 = v181;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to open tasks element.");
        v315 = &v329;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v182,
          3,
          (unsigned int)": {}",
          (__int64)&v315);
      }
      v25 = 659;
      goto LABEL_26;
    }
    v183 = (*(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD))(*(_QWORD *)v28 + 48LL))(
             v28,
             0);
    v23 = v183;
    if ( v183 < 0 )
    {
      v329 = v183;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to close update element.");
        v315 = &v329;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v184,
          3,
          (unsigned int)": {}",
          (__int64)&v315);
      }
      v25 = 661;
      goto LABEL_26;
    }
    for ( i = 0; ; ++i )
    {
      v186 = *(_QWORD *)v106;
      v316 = 10;
      v317 = 12;
      if ( i >= *((_QWORD *)this + 122) )
        break;
      v187 = *(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *))(v186 + 16);
      v318 = L"Phase";
      v23 = v187(v106, 0, &v316);
      if ( v23 < 0 )
      {
        v329 = v23;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to open actions.");
          v315 = &v329;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v286,
            3,
            (unsigned int)": {}",
            (__int64)&v315);
        }
        v25 = 665;
        goto LABEL_26;
      }
      v188 = *(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *))(*(_QWORD *)v106 + 88LL);
      v189 = numToString((int)i + 1);
      v190 = StringToUnicodeString(v322, v189);
      v320 = *(_OWORD *)v190;
      v191 = *(_QWORD *)(v190 + 16);
      v318 = L"seq";
      v321 = v191;
      v316 = 6;
      v317 = 8;
      v23 = v188(v106, 0, &v316, &v320);
      if ( v23 < 0 )
      {
        v329 = v23;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to emit phase.");
          v315 = &v329;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v285,
            3,
            (unsigned int)": {}",
            (__int64)&v315);
        }
        v25 = 672;
        goto LABEL_26;
      }
      v23 = (*(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD))(*(_QWORD *)v106 + 48LL))(
              v106,
              0);
      if ( v23 < 0 )
      {
        v329 = v23;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to end phase.");
          v315 = &v329;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v284,
            3,
            (unsigned int)": {}",
            (__int64)&v315);
        }
        v25 = 674;
        goto LABEL_26;
      }
      while ( 1 )
      {
        v192 = *((_QWORD *)this + 122);
        if ( i >= v192 )
          __fastfail(8u);
        v193 = *(_QWORD *)(*((_QWORD *)this + 124) + 8 * i);
        if ( v7 >= *(_QWORD *)(v193 + 88) )
          break;
        if ( i >= v192 )
          __fastfail(8u);
        v194 = *(_QWORD *)(*(_QWORD *)(v193 + 104) + 8 * v7);
        v195 = *(_QWORD *)v28;
        v318 = L"capability";
        v316 = 20;
        v317 = 22;
        v23 = (*(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *))(v195 + 16))(
                v28,
                0,
                &v316);
        if ( v23 < 0 )
        {
          v329 = v23;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to open package element.");
            v315 = &v329;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v271,
              3,
              (unsigned int)": {}",
              (__int64)&v315);
          }
          v25 = 681;
          goto LABEL_26;
        }
        v196 = *(_QWORD *)(v194 + 16);
        v197 = *(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *))(*(_QWORD *)v28 + 88LL);
        if ( v196 )
          FastCbsIdentityString = GetFastCbsIdentityString(*(const struct CCbsIdentity **)(v196 + 136));
        else
          FastCbsIdentityString = *(wchar_t **)(v194 + 8);
        v199 = StringToUnicodeString(v322, FastCbsIdentityString);
        v320 = *(_OWORD *)v199;
        v200 = *(_QWORD *)(v199 + 16);
        v318 = L"id";
        v321 = v200;
        v316 = 4;
        v317 = 6;
        v23 = v197(v28, 0, &v316, &v320);
        if ( v23 < 0 )
        {
          v329 = v23;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to emit package id.");
            v315 = &v329;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v270,
              3,
              (unsigned int)": {}",
              (__int64)&v315);
          }
          v25 = 691;
          goto LABEL_26;
        }
        v201 = *(_QWORD *)(v194 + 32);
        if ( v201 )
        {
          v202 = *(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *))(*(_QWORD *)v28 + 88LL);
          v203 = StringToUnicodeString(v322, v201);
          v320 = *(_OWORD *)v203;
          v204 = *(_QWORD *)(v203 + 16);
          v318 = L"displayName";
          v321 = v204;
          v316 = 22;
          v317 = 24;
          v23 = v202(v28, 0, &v316, &v320);
          if ( v23 < 0 )
          {
            v329 = v23;
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to emit package displayName.");
              v315 = &v329;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
                (_DWORD)LogAdapter::g_Logger,
                v265,
                3,
                (unsigned int)": {}",
                (__int64)&v315);
            }
            v25 = 700;
            goto LABEL_26;
          }
        }
        v205 = *(_QWORD *)(v194 + 40);
        if ( v205 )
        {
          v206 = *(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *))(*(_QWORD *)v28 + 88LL);
          v207 = StringToUnicodeString(v322, v205);
          v320 = *(_OWORD *)v207;
          v208 = *(_QWORD *)(v207 + 16);
          v318 = L"description";
          v321 = v208;
          v316 = 22;
          v317 = 24;
          v23 = v206(v28, 0, &v316, &v320);
          if ( v23 < 0 )
          {
            v329 = v23;
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to emit package description.");
              v315 = &v329;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
                (_DWORD)LogAdapter::g_Logger,
                v266,
                3,
                (unsigned int)": {}",
                (__int64)&v315);
            }
            v25 = 710;
            goto LABEL_26;
          }
        }
        v209 = *(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *))(*(_QWORD *)v28 + 88LL);
        v210 = CbsStateToString(*(unsigned int *)(v194 + 24));
        v211 = StringToUnicodeString(v322, v210);
        v320 = *(_OWORD *)v211;
        v212 = *(_QWORD *)(v211 + 16);
        v318 = L"targetState";
        v321 = v212;
        v316 = 22;
        v317 = 24;
        v23 = v209(v28, 0, &v316, &v320);
        if ( v23 < 0 )
        {
          v329 = v23;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to emit target state.");
            v315 = &v329;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v269,
              3,
              (unsigned int)": {}",
              (__int64)&v315);
          }
          v25 = 719;
          goto LABEL_26;
        }
        v213 = *(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *))(*(_QWORD *)v28 + 88LL);
        v214 = numToString(*(_DWORD *)v194);
        v215 = StringToUnicodeString(v322, v214);
        v320 = *(_OWORD *)v215;
        v216 = *(_QWORD *)(v215 + 16);
        v318 = L"options";
        v321 = v216;
        v316 = 14;
        v317 = 16;
        v23 = v213(v28, 0, &v316, &v320);
        if ( v23 < 0 )
        {
          v329 = v23;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to emit package option.");
            v315 = &v329;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v268,
              3,
              (unsigned int)": {}",
              (__int64)&v315);
          }
          v25 = 726;
          goto LABEL_26;
        }
        v23 = (*(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, __int64))(*(_QWORD *)v28 + 48LL))(
                v28,
                1);
        if ( v23 < 0 )
        {
          v329 = v23;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to close capability element.");
            v315 = &v329;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v267,
              3,
              (unsigned int)": {}",
              (__int64)&v315);
          }
          v25 = 730;
          goto LABEL_26;
        }
        ++v7;
      }
      v7 = 0;
      v217 = 0;
      while ( 2 )
      {
        v218 = *((_QWORD *)this + 122);
        v319 = v217;
        if ( i >= v218 )
          __fastfail(8u);
        v219 = *(_QWORD *)(*((_QWORD *)this + 124) + 8 * i);
        if ( (unsigned __int64)v217 < *(_QWORD *)(v219 + 24) )
        {
          if ( i >= v218 )
            __fastfail(8u);
          v220 = *(_QWORD *)(*(_QWORD *)(v219 + 40) + 8LL * (_QWORD)v217);
          v221 = *(_QWORD *)v28;
          v318 = L"package";
          v316 = 14;
          v317 = 16;
          v23 = (*(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *))(v221 + 16))(
                  v28,
                  0,
                  &v316);
          if ( v23 < 0 )
          {
            v329 = v23;
            if ( LogAdapter::g_Logger )
            {
              LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to open package element.");
              v315 = &v329;
              LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
                (_DWORD)LogAdapter::g_Logger,
                v282,
                3,
                (unsigned int)": {}",
                (__int64)&v315);
            }
            v25 = 738;
          }
          else
          {
            v222 = *(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *))(*(_QWORD *)v28 + 88LL);
            v223 = *(_QWORD *)(v220 + 24);
            if ( v223 )
            {
              v224 = &qword_1802EB518;
              if ( *(_QWORD *)(v223 + 120) )
                v224 = *(const wchar_t **)(v223 + 120);
            }
            else
            {
              v224 = *(const wchar_t **)(v220 + 8);
            }
            v225 = StringToUnicodeString(v322, v224);
            v320 = *(_OWORD *)v225;
            v226 = *(_QWORD *)(v225 + 16);
            v318 = L"id";
            v321 = v226;
            v316 = 4;
            v317 = 6;
            v23 = v222(v28, 0, &v316, &v320);
            if ( v23 < 0 )
            {
              v329 = v23;
              if ( LogAdapter::g_Logger )
              {
                LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to emit package id.");
                v315 = &v329;
                LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
                  (_DWORD)LogAdapter::g_Logger,
                  v281,
                  3,
                  (unsigned int)": {}",
                  (__int64)&v315);
              }
              v25 = 748;
            }
            else
            {
              v227 = (const wchar_t **)(v220 + 16);
              if ( !*(_QWORD *)(v220 + 16) )
              {
                v228 = *(_QWORD *)(v220 + 24);
                if ( v228 )
                {
                  v314 = v220 + 16;
                  CCbsPackage::GetPropertyInternal(v228, 7, 0, 0);
                }
              }
              v229 = &qword_1802EB518;
              if ( *v227 )
                v229 = *v227;
              v230 = *(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *))(*(_QWORD *)v28 + 88LL);
              v231 = StringToUnicodeString(v322, v229);
              v320 = *(_OWORD *)v231;
              v232 = *(_QWORD *)(v231 + 16);
              v318 = L"name";
              v321 = v232;
              v316 = 8;
              v317 = 10;
              v23 = v230(v28, 0, &v316, &v320);
              if ( v23 < 0 )
              {
                v329 = v23;
                if ( LogAdapter::g_Logger )
                {
                  LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to emit package name.");
                  v315 = &v329;
                  LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
                    (_DWORD)LogAdapter::g_Logger,
                    v280,
                    3,
                    (unsigned int)": {}",
                    (__int64)&v315);
                }
                v25 = 766;
              }
              else
              {
                v233 = *(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *))(*(_QWORD *)v28 + 88LL);
                v234 = CbsStateToString(*(unsigned int *)(v220 + 32));
                v235 = StringToUnicodeString(v322, v234);
                v320 = *(_OWORD *)v235;
                v236 = *(_QWORD *)(v235 + 16);
                v318 = L"targetState";
                v321 = v236;
                v316 = 22;
                v317 = 24;
                v23 = v233(v28, 0, &v316, &v320);
                if ( v23 < 0 )
                {
                  v329 = v23;
                  if ( LogAdapter::g_Logger )
                  {
                    LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to emit target state.");
                    v315 = &v329;
                    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
                      (_DWORD)LogAdapter::g_Logger,
                      v279,
                      3,
                      (unsigned int)": {}",
                      (__int64)&v315);
                  }
                  v25 = 774;
                }
                else
                {
                  v237 = *(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *))(*(_QWORD *)v28 + 88LL);
                  v238 = numToString(*(_DWORD *)v220);
                  v239 = StringToUnicodeString(v322, v238);
                  v320 = *(_OWORD *)v239;
                  v240 = *(_QWORD *)(v239 + 16);
                  v318 = L"options";
                  v321 = v240;
                  v316 = 14;
                  v317 = 16;
                  v23 = v237(v28, 0, &v316, &v320);
                  if ( v23 < 0 )
                  {
                    v329 = v23;
                    if ( LogAdapter::g_Logger )
                    {
                      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to emit package option.");
                      v315 = &v329;
                      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
                        (_DWORD)LogAdapter::g_Logger,
                        v278,
                        3,
                        (unsigned int)": {}",
                        (__int64)&v315);
                    }
                    v25 = 781;
                  }
                  else if ( *(_QWORD *)(v220 + 64)
                         && (v23 = (*(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD))(*(_QWORD *)v28 + 48LL))(
                                     v28,
                                     0),
                             v23 < 0) )
                  {
                    v329 = v23;
                    if ( LogAdapter::g_Logger )
                    {
                      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to end phase.");
                      v315 = &v329;
                      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
                        (_DWORD)LogAdapter::g_Logger,
                        v272,
                        3,
                        (unsigned int)": {}",
                        (__int64)&v315);
                    }
                    v25 = 785;
                  }
                  else
                  {
                    for ( j = 0; ; ++j )
                    {
                      v242 = *(_QWORD *)(v220 + 64);
                      if ( j >= v242 )
                        break;
                      v243 = *(_QWORD *)(*(_QWORD *)(v220 + 80) + 8 * j);
                      v244 = *(_QWORD *)v28;
                      v318 = L"update";
                      v316 = 12;
                      v317 = 14;
                      v23 = (*(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *))(v244 + 16))(
                              v28,
                              0,
                              &v316);
                      if ( v23 < 0 )
                      {
                        v329 = v23;
                        if ( LogAdapter::g_Logger )
                        {
                          LogAdapter::Logger::LogNumObjects<>(
                            LogAdapter::g_Logger,
                            0,
                            3,
                            "Failed to open update element.");
                          v315 = &v329;
                          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
                            (_DWORD)LogAdapter::g_Logger,
                            v276,
                            3,
                            (unsigned int)": {}",
                            (__int64)&v315);
                        }
                        v25 = 795;
                        goto LABEL_26;
                      }
                      v245 = *(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *))(*(_QWORD *)v28 + 88LL);
                      v246 = StringToUnicodeString(v322, *(_QWORD *)v243);
                      v320 = *(_OWORD *)v246;
                      v247 = *(_QWORD *)(v246 + 16);
                      v318 = L"name";
                      v321 = v247;
                      v316 = 8;
                      v317 = 10;
                      v23 = v245(v28, 0, &v316, &v320);
                      if ( v23 < 0 )
                      {
                        v329 = v23;
                        if ( LogAdapter::g_Logger )
                        {
                          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to emit update name.");
                          v315 = &v329;
                          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
                            (_DWORD)LogAdapter::g_Logger,
                            v275,
                            3,
                            (unsigned int)": {}",
                            (__int64)&v315);
                        }
                        v25 = 802;
                        goto LABEL_26;
                      }
                      v248 = *(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *))(*(_QWORD *)v28 + 88LL);
                      v249 = CbsSelectionToString(*(unsigned int *)(v243 + 8));
                      v250 = StringToUnicodeString(v322, v249);
                      v320 = *(_OWORD *)v250;
                      v251 = *(_QWORD *)(v250 + 16);
                      v318 = L"select";
                      v321 = v251;
                      v316 = 12;
                      v317 = 14;
                      v23 = v248(v28, 0, &v316, &v320);
                      if ( v23 < 0 )
                      {
                        v329 = v23;
                        if ( LogAdapter::g_Logger )
                        {
                          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to select.");
                          v315 = &v329;
                          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
                            (_DWORD)LogAdapter::g_Logger,
                            v274,
                            3,
                            (unsigned int)": {}",
                            (__int64)&v315);
                        }
                        v25 = 809;
                        goto LABEL_26;
                      }
                      v252 = *(_DWORD *)(v243 + 12);
                      if ( v252 )
                      {
                        v253 = *(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *, __int128 *))(*(_QWORD *)v28 + 88LL);
                        v254 = numToString(v252);
                        v255 = StringToUnicodeString(v322, v254);
                        v320 = *(_OWORD *)v255;
                        v256 = *(_QWORD *)(v255 + 16);
                        v318 = L"options";
                        v321 = v256;
                        v316 = 14;
                        v317 = 16;
                        v257 = v253(v28, 0, &v316, &v320);
                        v23 = v257;
                        if ( v257 < 0 )
                        {
                          v329 = v257;
                          if ( LogAdapter::g_Logger )
                          {
                            LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to emit option.");
                            v315 = &v329;
                            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
                              (_DWORD)LogAdapter::g_Logger,
                              v258,
                              3,
                              (unsigned int)": {}",
                              (__int64)&v315);
                          }
                          v25 = 819;
                          goto LABEL_26;
                        }
                      }
                      v23 = (*(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, __int64))(*(_QWORD *)v28 + 48LL))(
                              v28,
                              1);
                      if ( v23 < 0 )
                      {
                        v329 = v23;
                        if ( LogAdapter::g_Logger )
                        {
                          LogAdapter::Logger::LogNumObjects<>(
                            LogAdapter::g_Logger,
                            0,
                            3,
                            "Failed to close update element.");
                          v315 = &v329;
                          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
                            (_DWORD)LogAdapter::g_Logger,
                            v273,
                            3,
                            (unsigned int)": {}",
                            (__int64)&v315);
                        }
                        v25 = 824;
                        goto LABEL_26;
                      }
                    }
                    v7 = 0;
                    v259 = v242 == 0;
                    v260 = *(_QWORD *)v28;
                    if ( !v259 )
                    {
                      v261 = *(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *))(v260 + 56);
                      v318 = L"package";
                      v316 = 14;
                      v317 = 16;
                      v262 = v261(v28, 0, &v316);
                      v23 = v262;
                      if ( v262 < 0 )
                      {
                        v329 = v262;
                        if ( LogAdapter::g_Logger )
                        {
                          LogAdapter::Logger::LogNumObjects<>(
                            LogAdapter::g_Logger,
                            0,
                            3,
                            "Failed to close package element.");
                          v315 = &v329;
                          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
                            (_DWORD)LogAdapter::g_Logger,
                            v263,
                            3,
                            (unsigned int)": {}",
                            (__int64)&v315);
                        }
                        v25 = 830;
                        goto LABEL_26;
                      }
LABEL_235:
                      v217 = (wchar_t *)((char *)v319 + 1);
                      continue;
                    }
                    v23 = (*(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, __int64))(v260 + 48))(
                            v28,
                            1);
                    if ( v23 >= 0 )
                      goto LABEL_235;
                    v329 = v23;
                    if ( LogAdapter::g_Logger )
                    {
                      LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to end package element.");
                      v315 = &v329;
                      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
                        (_DWORD)LogAdapter::g_Logger,
                        v277,
                        3,
                        (unsigned int)": {}",
                        (__int64)&v315);
                    }
                    v25 = 835;
                  }
                }
              }
            }
          }
          goto LABEL_26;
        }
        break;
      }
      v264 = *(_QWORD *)v28;
      v318 = L"Phase";
      v316 = 10;
      v317 = 12;
      v106 = v28;
      v23 = (*(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *))(v264 + 56))(
              v28,
              0,
              &v316);
      if ( v23 < 0 )
      {
        v329 = v23;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to close Phase");
          v315 = &v329;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v283,
            3,
            (unsigned int)": {}",
            (__int64)&v315);
        }
        v25 = 839;
LABEL_26:
        v15 = wil::details::in1diag3::Return_NtStatus(
                retaddr,
                (void *)v25,
                (unsigned int)"onecore\\base\\cbs\\core\\cbssessionpersistence.cpp",
                (const char *)(unsigned int)v23,
                v314);
        goto LABEL_13;
      }
    }
    v287 = *(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *))(v186 + 56);
    v318 = L"Tasks";
    v288 = v287(v106, 0, &v316);
    v23 = v288;
    if ( v288 < 0 )
    {
      v329 = v288;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to close tasks.");
        v315 = &v329;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v289,
          3,
          (unsigned int)": {}",
          (__int64)&v315);
      }
      v25 = 842;
      goto LABEL_26;
    }
    v290 = *(_QWORD *)v106;
    v316 = 14;
    v317 = 16;
    v318 = L"Actions";
    v291 = (*(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *))(v290 + 16))(
             v106,
             0,
             &v316);
    v23 = v291;
    if ( v291 < 0 )
    {
      v329 = v291;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to open actions.");
        v315 = &v329;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v292,
          3,
          (unsigned int)": {}",
          (__int64)&v315);
      }
      v25 = 846;
      goto LABEL_26;
    }
    v293 = (*(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD))(*(_QWORD *)v106 + 48LL))(
             v106,
             0);
    v23 = v293;
    if ( v293 < 0 )
    {
      v329 = v293;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to end action.");
        v315 = &v329;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v294,
          3,
          (unsigned int)": {}",
          (__int64)&v315);
      }
      v25 = 848;
      goto LABEL_26;
    }
    v295 = v330[0];
    for ( k = 0; k < *((_QWORD *)this + 114) && k < *((unsigned int *)this + 254); ++k )
    {
      v297 = *(struct SessionPhase **)(*((_QWORD *)this + 116) + 8 * k);
      v15 = CCbsSession::PersistActionPhase(this, v28, v297, v295, 0);
      if ( (v15 & 0x80000000) != 0 )
      {
        v330[0] = v15;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to persist action phase");
          v315 = v330;
          LOBYTE(v300) = 1;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v300,
            3,
            (unsigned int)": {}",
            (__int64)&v315);
        }
        v20 = 855;
        goto LABEL_20;
      }
      v298 = (struct SessionPhase *)*((_QWORD *)v297 + 42);
      if ( v298 )
      {
        v15 = CCbsSession::PersistActionPhase(this, v28, v298, v295, 1);
        if ( (v15 & 0x80000000) != 0 )
        {
          v330[0] = v15;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to persist retry action phase");
            v315 = v330;
            LOBYTE(v299) = 1;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v299,
              3,
              (unsigned int)": {}",
              (__int64)&v315);
          }
          v20 = 860;
          goto LABEL_20;
        }
      }
    }
    if ( v295
      && (v301 = (struct SessionPhase *)*((_QWORD *)this + 139)) != 0
      && (v302 = CCbsSession::PersistActionPhase(this, v28, v301, v295, 0), v15 = v302, v302 < 0) )
    {
      v330[0] = v302;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to persist post transaction phase.");
        v315 = v330;
        LOBYTE(v303) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v303,
          3,
          (unsigned int)": {}",
          (__int64)&v315);
      }
      v20 = 868;
    }
    else
    {
      v304 = *(_QWORD *)v28;
      v317 = 16;
      v316 = 14;
      v318 = L"Actions";
      v305 = (*(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *))(v304 + 56))(
               v28,
               0,
               &v316);
      v23 = v305;
      if ( v305 < 0 )
      {
        v330[0] = v305;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to close Actions");
          v315 = v330;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v306,
            3,
            (unsigned int)": {}",
            (__int64)&v315);
        }
        v25 = 871;
        goto LABEL_26;
      }
      v307 = *(_QWORD *)v28;
      v318 = L"Session";
      v316 = 14;
      v317 = 16;
      v308 = (*(__int64 (__fastcall **)(struct Windows::Microdom::Rtl::IRtlXmlWriter *, _QWORD, __int64 *))(v307 + 56))(
               v28,
               0,
               &v316);
      v23 = v308;
      if ( v308 < 0 )
      {
        v330[0] = v308;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to close session.");
          v315 = v330;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v309,
            3,
            (unsigned int)": {}",
            (__int64)&v315);
        }
        v25 = 874;
        goto LABEL_26;
      }
      v310 = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned __int64 *))(*(_QWORD *)v326 + 16LL))(v326, 0, v331);
      v23 = v310;
      if ( v310 < 0 )
      {
        v330[0] = v310;
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to get data out of builder.");
          v315 = v330;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(
            (_DWORD)LogAdapter::g_Logger,
            v311,
            3,
            (unsigned int)": {}",
            (__int64)&v315);
        }
        v25 = 876;
        goto LABEL_26;
      }
      v312 = PackageStorePersistSession(this, v295, v332, v331[0]);
      v15 = v312;
      if ( v312 >= 0 )
        goto LABEL_12;
      v330[0] = v312;
      if ( LogAdapter::g_Logger )
      {
        v315 = (int *)*((_QWORD *)this + 80);
        LogAdapter::Logger::LogNumObjects<wchar_t const *>(
          (_DWORD)LogAdapter::g_Logger,
          0,
          3,
          (unsigned int)"Failed to store persist session: {}",
          (__int64)&v315);
        v328 = v330;
        LOBYTE(v313) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (_DWORD)LogAdapter::g_Logger,
          v313,
          3,
          (unsigned int)": {}",
          (__int64)&v328);
      }
      v20 = 879;
    }
LABEL_20:
    v21 = v15;
LABEL_21:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v20,
      (unsigned int)"onecore\\base\\cbs\\core\\cbssessionpersistence.cpp",
      (const char *)v21,
      v314);
    goto LABEL_13;
  }
  v329 = v12;
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to persist session state.");
    v323 = (wchar_t *)&v329;
    LOBYTE(v16) = 1;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (_DWORD)LogAdapter::g_Logger,
      v16,
      3,
      (unsigned int)": {}",
      (__int64)&v323);
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x195,
    (unsigned int)"onecore\\base\\cbs\\core\\cbssessionpersistence.cpp",
    (const char *)v15,
    v314);
  if ( v332 )
    RtlFreeLBlob(v331);
  return v15;
}

```

## disassembly

```asm
0x18001a1c4  mov     [rsp-8+arg_10], rbx
0x18001a1c9  push    rbp
0x18001a1ca  push    rsi
0x18001a1cb  push    rdi
0x18001a1cc  push    r12
0x18001a1ce  push    r13
0x18001a1d0  push    r14
0x18001a1d2  push    r15
0x18001a1d4  lea     rbp, [rsp-80h]
0x18001a1d9  sub     rsp, 180h
0x18001a1e0  mov     rax, cs:__security_cookie
0x18001a1e7  xor     rax, rsp
0x18001a1ea  mov     [rbp+0B0h+var_40], rax
0x18001a1ee  mov     esi, r8d
0x18001a1f1  mov     [rbp+0B0h+var_F0], r9d
0x18001a1f5  mov     rbx, rdx
0x18001a1f8  mov     r14, rcx
0x18001a1fb  xor     r15d, r15d
0x18001a1fe  lea     rcx, [rbp+0B0h+var_D0]; void *
0x18001a202  xor     edx, edx; Val
0x18001a204  mov     [rbp+0B0h+var_128], r15
0x18001a208  mov     r8d, 81h; Size
0x18001a20e  mov     [rbp+0B0h+var_108], r15
0x18001a212  mov     r12d, r9d
0x18001a215  call    memset_0
0x18001a21a  xor     eax, eax
0x18001a21c  mov     [rbp+0B0h+var_110], r15
0x18001a220  mov     [rbp+0B0h+var_118], r15
0x18001a224  xorps   xmm0, xmm0
0x18001a227  mov     [rbp+0B0h+var_120], r15
0x18001a22b  mov     r9d, 0D0h
0x18001a231  mov     [rbp+0B0h+var_D8], rax
0x18001a235  movups  xmmword ptr [rbp+0B0h+var_E8], xmm0
0x18001a239  test    r12d, r12d
0x18001a23c  jnz     short loc_18001A245
0x18001a23e  mov     r9d, [r14+300h]
0x18001a245  mov     eax, [rbx+140h]
0x18001a24b  mov     rcx, r14
0x18001a24e  cmp     [rbx+148h], r15d
0x18001a255  lea     r8d, [rax+2710h]
0x18001a25c  cmovz   r8d, eax
0x18001a260  xor     edx, edx
0x18001a262  call    ?PackageStorePersistSessionState@@YAJPEAVCCbsSession@@PEB_WIW4_CbsSessionState@@@Z; PackageStorePersistSessionState(CCbsSession *,wchar_t const *,uint,_CbsSessionState)
0x18001a267  mov     edi, eax
0x18001a269  test    eax, eax
0x18001a26b  jns     short loc_18001A2E7
0x18001a26d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18001a274  mov     [rbp+0B0h+var_F8], eax
0x18001a277  test    rcx, rcx
0x18001a27a  jz      short loc_18001A2BB
0x18001a27c  mov     ebx, 3
0x18001a281  lea     r9, aFailedToPersis; "Failed to persist session state."
0x18001a288  mov     r8d, ebx
0x18001a28b  xor     edx, edx
0x18001a28d  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18001a292  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18001a299  lea     rax, [rbp+0B0h+var_F8]
0x18001a29d  mov     [rbp+0B0h+var_128], rax
0x18001a2a1  lea     r9, asc_1802EE7AC; ": {}"
0x18001a2a8  lea     rax, [rbp+0B0h+var_128]
0x18001a2ac  mov     r8d, ebx
0x18001a2af  mov     dl, 1
0x18001a2b1  mov     qword ptr [rsp+1B0h+var_190], rax; int
0x18001a2b6  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18001a2bb  mov     rcx, [rbp+0B8h]; this
0x18001a2c2  lea     r8, aOnecoreBaseCbs_114; "onecore\\base\\cbs\\core\\cbssessionper"...
0x18001a2c9  mov     r9d, edi; char *
0x18001a2cc  mov     edx, 195h; void *
0x18001a2d1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a2d6  cmp     [rbp+0B0h+var_D8], r15
0x18001a2da  jz      short loc_18001A329
0x18001a2dc  lea     rcx, [rbp+0B0h+var_E8]
0x18001a2e0  call    RtlFreeLBlob
0x18001a2e5  jmp     short loc_18001A329
0x18001a2e7  test    esi, esi
0x18001a2e9  jz      short loc_18001A353
0x18001a2eb  test    r12d, r12d
0x18001a2ee  jnz     short loc_18001A35C
0x18001a2f0  mov     edi, r15d
0x18001a2f3  lea     rcx, [rbp+0B0h+var_E8]
0x18001a2f7  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x18001a2fc  lea     rcx, [rbp+0B0h+var_120]
0x18001a300  call    ??1?$Auto@PEAUIRtlIniFile@Rtl@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Rtl::IRtlIniFile *>::~Auto<Windows::Rtl::IRtlIniFile *>(void)
0x18001a305  lea     rcx, [rbp+0B0h+var_118]
0x18001a309  call    ??1?$Auto@PEAUIRtlIniFile@Rtl@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Rtl::IRtlIniFile *>::~Auto<Windows::Rtl::IRtlIniFile *>(void)
0x18001a30e  lea     rcx, [rbp+0B0h+var_110]
0x18001a312  call    ??1?$Auto@PEAUIRtlIniFile@Rtl@Windows@@@Windows@@QEAA@XZ; Windows::Auto<Windows::Rtl::IRtlIniFile *>::~Auto<Windows::Rtl::IRtlIniFile *>(void)
0x18001a317  lea     rcx, [rbp+0B0h+var_108]
0x18001a31b  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18001a320  lea     rcx, [rbp+0B0h+var_128]
0x18001a324  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18001a329  mov     eax, edi
0x18001a32b  mov     rcx, [rbp+0B0h+var_40]
0x18001a32f  xor     rcx, rsp; StackCookie
0x18001a332  call    __security_check_cookie
0x18001a337  mov     rbx, [rsp+1B0h+arg_10]
0x18001a33f  add     rsp, 180h
0x18001a346  pop     r15
0x18001a348  pop     r14
0x18001a34a  pop     r13
0x18001a34c  pop     r12
0x18001a34e  pop     rdi
0x18001a34f  pop     rsi
0x18001a350  pop     rbp
0x18001a351  retn
0x18001a353  test    r12d, r12d
0x18001a356  jz      loc_18001A3F4
0x18001a35c  xor     edx, edx; wchar_t *
0x18001a35e  mov     rcx, r14; struct CCbsSession *
0x18001a361  call    ?PackageStoreMarkSessionComplete@@YAJPEAVCCbsSession@@PEB_W@Z; PackageStoreMarkSessionComplete(CCbsSession *,wchar_t const *)
0x18001a366  mov     edi, eax
0x18001a368  test    eax, eax
0x18001a36a  jns     loc_18001A3F4
0x18001a370  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18001a377  mov     [rbp+0B0h+var_F8], eax
0x18001a37a  test    rcx, rcx
0x18001a37d  jz      short loc_18001A3D4
0x18001a37f  mov     rdx, [r14+280h]
0x18001a386  lea     rax, [rsp+1B0h+var_160]
0x18001a38b  mov     [rsp+1B0h+var_160], rdx
0x18001a390  lea     r9, aFailedToMarkSe; "Failed to mark session complete on sess"...
0x18001a397  mov     ebx, 3
0x18001a39c  mov     qword ptr [rsp+1B0h+var_190], rax
0x18001a3a1  xor     edx, edx
0x18001a3a3  mov     r8d, ebx
0x18001a3a6  call    ??$LogNumObjects@PEB_W@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBQEB_W@Z; LogAdapter::Logger::LogNumObjects<wchar_t const *>(bool,LogAdapter::LogLevel,char const * const,wchar_t const * const &)
0x18001a3ab  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18001a3b2  lea     rax, [rbp+0B0h+var_F8]
0x18001a3b6  mov     qword ptr [rbp+0B0h+var_F0], rax
0x18001a3ba  lea     r9, asc_1802EE7AC; ": {}"
0x18001a3c1  lea     rax, [rbp+0B0h+var_F0]
0x18001a3c5  mov     r8d, ebx
0x18001a3c8  mov     dl, 1
0x18001a3ca  mov     qword ptr [rsp+1B0h+var_190], rax; int
0x18001a3cf  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18001a3d4  mov     edx, 19Fh; void *
0x18001a3d9  mov     r9d, edi; char *
0x18001a3dc  mov     rcx, [rbp+0B8h]; this
0x18001a3e3  lea     r8, aOnecoreBaseCbs_114; "onecore\\base\\cbs\\core\\cbssessionper"...
0x18001a3ea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a3ef  jmp     loc_18001A2F3
0x18001a3f4  lea     r9, [rbp+0B0h+var_118]
0x18001a3f8  lea     r8, [rbp+0B0h+var_110]
0x18001a3fc  call    RtlCreateUtf8UCSStringBuilder
0x18001a401  mov     edi, eax
0x18001a403  test    eax, eax
0x18001a405  jns     short loc_18001A477
0x18001a407  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18001a40e  mov     [rbp+0B0h+var_F8], eax
0x18001a411  test    rcx, rcx
0x18001a414  jz      short loc_18001A455
0x18001a416  mov     ebx, 3
0x18001a41b  lea     r9, aFailedToCreate_90; "Failed to create string builder."
0x18001a422  mov     r8d, ebx
0x18001a425  xor     edx, edx
0x18001a427  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18001a42c  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18001a433  lea     rax, [rbp+0B0h+var_F8]
0x18001a437  mov     [rsp+1B0h+var_160], rax
0x18001a43c  lea     r9, asc_1802EE7AC; ": {}"
0x18001a443  lea     rax, [rsp+1B0h+var_160]
0x18001a448  mov     r8d, ebx
0x18001a44b  mov     qword ptr [rsp+1B0h+var_190], rax; int
0x18001a450  call    ??$LogNumObjects@U?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatNtStatusWrapper<long> const &)
0x18001a455  mov     edx, 1A4h; void *
0x18001a45a  mov     rcx, [rbp+0B8h]; this
0x18001a461  lea     r8, aOnecoreBaseCbs_114; "onecore\\base\\cbs\\core\\cbssessionper"...
0x18001a468  mov     r9d, edi; char *
0x18001a46b  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18001a470  mov     edi, eax
0x18001a472  jmp     loc_18001A2F3
0x18001a477  mov     rdx, [rbp+0B0h+var_118]
0x18001a47b  lea     r8, [rbp+0B0h+var_120]
0x18001a47f  mov     ecx, 0Ah
0x18001a484  call    RtlCreateDefaultXmlWriter
0x18001a489  mov     edi, eax
0x18001a48b  test    eax, eax
0x18001a48d  jns     short loc_18001A4E7
0x18001a48f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18001a496  mov     [rbp+0B0h+var_F8], eax
0x18001a499  test    rcx, rcx
0x18001a49c  jz      short loc_18001A4DD
0x18001a49e  mov     ebx, 3
0x18001a4a3  lea     r9, aFailedToCreate_6; "Failed to create XML writter."
0x18001a4aa  mov     r8d, ebx
0x18001a4ad  xor     edx, edx
0x18001a4af  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18001a4b4  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18001a4bb  lea     rax, [rbp+0B0h+var_F8]
0x18001a4bf  mov     [rsp+1B0h+var_160], rax
0x18001a4c4  lea     r9, asc_1802EE7AC; ": {}"
0x18001a4cb  lea     rax, [rsp+1B0h+var_160]
0x18001a4d0  mov     r8d, ebx
0x18001a4d3  mov     qword ptr [rsp+1B0h+var_190], rax
0x18001a4d8  call    ??$LogNumObjects@U?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatNtStatusWrapper<long> const &)
0x18001a4dd  mov     edx, 1ABh
0x18001a4e2  jmp     loc_18001A45A
0x18001a4e7  mov     rbx, [rbp+0B0h+var_120]
0x18001a4eb  lea     rcx, aSession; "Session"
0x18001a4f2  mov     esi, 0Eh
0x18001a4f7  lea     r8, [rsp+1B0h+var_178]
0x18001a4fc  xor     edx, edx
0x18001a4fe  mov     rax, [rbx]
0x18001a501  mov     [rsp+1B0h+var_168], rcx
0x18001a506  lea     r13d, [rsi+2]
0x18001a50a  mov     rcx, rbx
0x18001a50d  mov     [rsp+1B0h+var_178], rsi
0x18001a512  mov     [rsp+1B0h+var_170], r13
0x18001a517  mov     rax, [rax+10h]
0x18001a51b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a520  mov     edi, eax
0x18001a522  test    eax, eax
0x18001a524  jns     short loc_18001A57C
0x18001a526  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18001a52d  mov     [rbp+0B0h+var_F8], eax
0x18001a530  test    rcx, rcx
0x18001a533  jz      short loc_18001A572
0x18001a535  lea     ebx, [rsi-0Bh]
0x18001a538  xor     edx, edx
0x18001a53a  mov     r8d, ebx
0x18001a53d  lea     r9, aFailedToOpenSe_1; "Failed to open session element."
0x18001a544  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18001a549  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18001a550  lea     rax, [rbp+0B0h+var_F8]
0x18001a554  mov     [rsp+1B0h+var_160], rax
0x18001a559  lea     r9, asc_1802EE7AC; ": {}"
0x18001a560  lea     rax, [rsp+1B0h+var_160]
0x18001a565  mov     r8d, ebx
0x18001a568  mov     qword ptr [rsp+1B0h+var_190], rax
0x18001a56d  call    ??$LogNumObjects@U?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatNtStatusWrapper<long> const &)
0x18001a572  mov     edx, 1D0h
0x18001a577  jmp     loc_18001A45A
0x18001a57c  mov     rax, [rbx]
0x18001a57f  lea     rdx, a80; "8.0"
0x18001a586  lea     rcx, [rsp+1B0h+var_140]
0x18001a58b  mov     rdi, [rax+58h]
0x18001a58f  call    ?StringToUnicodeString@@YA?AU_LUNICODE_STRING@@PEB_W@Z; StringToUnicodeString(wchar_t const *)
0x18001a594  lea     r9, [rsp+1B0h+var_158]
0x18001a599  xor     edx, edx
0x18001a59b  lea     r8, [rsp+1B0h+var_178]
0x18001a5a0  mov     rcx, rbx
0x18001a5a3  movups  xmm0, xmmword ptr [rax]
0x18001a5a6  movups  [rsp+1B0h+var_158], xmm0
0x18001a5ab  movsd   xmm1, qword ptr [rax+10h]
0x18001a5b0  lea     rax, aVersion; "version"
0x18001a5b7  mov     [rsp+1B0h+var_168], rax
0x18001a5bc  mov     rax, rdi
0x18001a5bf  movsd   [rsp+1B0h+var_148], xmm1
0x18001a5c5  mov     [rsp+1B0h+var_178], rsi
0x18001a5ca  mov     [rsp+1B0h+var_170], r13
0x18001a5cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a5d4  mov     edi, eax
0x18001a5d6  test    eax, eax
0x18001a5d8  jns     short loc_18001A632
0x18001a5da  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18001a5e1  mov     [rbp+0B0h+var_F8], eax
0x18001a5e4  test    rcx, rcx
0x18001a5e7  jz      short loc_18001A628
0x18001a5e9  mov     ebx, 3
0x18001a5ee  lea     r9, aFailedToEmitVe; "Failed to emit version."
0x18001a5f5  mov     r8d, ebx
0x18001a5f8  xor     edx, edx
0x18001a5fa  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18001a5ff  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18001a606  lea     rax, [rbp+0B0h+var_F8]
0x18001a60a  mov     [rsp+1B0h+var_160], rax
0x18001a60f  lea     r9, asc_1802EE7AC; ": {}"
0x18001a616  lea     rax, [rsp+1B0h+var_160]
0x18001a61b  mov     r8d, ebx
0x18001a61e  mov     qword ptr [rsp+1B0h+var_190], rax
0x18001a623  call    ??$LogNumObjects@U?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatNtStatusWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatNtStatusWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatNtStatusWrapper<long> const &)
0x18001a628  mov     edx, 1D4h
0x18001a62d  jmp     loc_18001A45A
0x18001a632  mov     rax, [rbx]
0x18001a635  lea     rcx, [rsp+1B0h+var_140]
0x18001a63a  mov     rdx, [r14+280h]
0x18001a641  mov     rdi, [rax+58h]
0x18001a645  call    ?StringToUnicodeString@@YA?AU_LUNICODE_STRING@@PEB_W@Z; StringToUnicodeString(wchar_t const *)
0x18001a64a  lea     r9, [rsp+1B0h+var_158]
0x18001a64f  xor     edx, edx
0x18001a651  lea     r8, [rsp+1B0h+var_178]
0x18001a656  mov     rcx, rbx
0x18001a659  movups  xmm0, xmmword ptr [rax]
0x18001a65c  movups  [rsp+1B0h+var_158], xmm0
0x18001a661  movsd   xmm1, qword ptr [rax+10h]
0x18001a666  lea     rax, aId_2; "id"
0x18001a66d  mov     [rsp+1B0h+var_168], rax
0x18001a672  mov     rax, rdi
0x18001a675  movsd   [rsp+1B0h+var_148], xmm1
0x18001a67b  mov     [rsp+1B0h+var_178], 4
0x18001a684  mov     [rsp+1B0h+var_170], 6
0x18001a68d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a692  mov     edi, eax
0x18001a694  test    eax, eax
0x18001a696  jns     short loc_18001A6F0
0x18001a698  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18001a69f  mov     [rbp+0B0h+var_F8], eax
0x18001a6a2  test    rcx, rcx
0x18001a6a5  jz      short loc_18001A6E6
0x18001a6a7  mov     ebx, 3
  ... truncated ...
```
