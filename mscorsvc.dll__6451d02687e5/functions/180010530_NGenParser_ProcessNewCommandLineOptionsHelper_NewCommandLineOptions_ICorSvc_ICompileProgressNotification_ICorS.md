# NGenParser::ProcessNewCommandLineOptionsHelper(NewCommandLineOptions &,ICorSvc *,ICompileProgressNotification *,ICorSvcLogger *)

- ea: `0x180010530`
- end: `0x180011af1`
- name: `?ProcessNewCommandLineOptionsHelper@NGenParser@@AEAAXAEAUNewCommandLineOptions@@PEAUICorSvc@@PEAUICompileProgressNotification@@PEAUICorSvcLogger@@@Z`
- size: `5569`
- prototype: `void __usercall(NGenParser *__hidden this@<rcx>, struct NewCommandLineOptions *@<rdx>, struct ICorSvc *@<r8>, struct ICompileProgressNotification *@<r9>, struct ICorSvcLogger *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180011e5c`

## callees

- `0x180001da0`
- `0x18000da0c`
- `0x18000da70`
- `0x180010530`
- `0x180030568`
- `0x180030ab8`
- `0x180034fd4`
- `0x1800350c4`
- `0x1800366a8`
- `0x180037c10`
- `0x18003dc30`
- `0x18003f280`

## string_xrefs

- `0x180011001`: `The .NET Runtime Optimization Service continue is pending.\n`
- `0x180010ff8`: `The .NET Runtime Optimization Service pause is pending.\n`
- `0x180010fef`: `The .NET Runtime Optimization Service is started and paused.\n`
- `0x18001100a`: `The .NET Runtime Optimization Service is running.\n`
- `0x18001101c`: `The .NET Runtime Optimization Service is starting.\n`
- `0x180011013`: `The .NET Runtime Optimization Service is stopping.\n`
- `0x180011025`: `The .NET Runtime Optimization Service is stopped.\n`
- `0x1800116fc`: `Error: /NoRoot can only be used with Install or Uninstall or CreatePDB commands.`
- `0x18001171c`: `Error: Scenario, /ExeConfig or /AppBase not allowed with Uninstall /NoRoot command.`
- `0x180011814`: `Error: Install /Package requires /NoDependencies.`
- `0x180011834`: `Error: /Version, /LocalAppData and /Package can only be used with Install or Uninstall or CreatePDB commands.`
- `0x180011784`: `Error: You must specify an assembly to install.`
- `0x180011aa1`: `Error: You must specify an assembly to uninstall.`
- `0x180011a4b`: `Error: Cannot queue an uninstall action`
- `0x180011997`: `Error: The specified assembly is not installed.`
- `0x180011a25`: `Error: The specified assembly is not installed.`
- `0x180011a7b`: `Error: The specified assembly is not installed.`
- `0x180011a05`: `Error: Cannot specify an assembly name to update`
- `0x180011907`: `Error: Cannot interact with the service when using the offline ngen feature`
- `0x180010f93`: `Service name is: `
- `0x1800118e7`: `Error: insufficient number of arguments to createpdb`
- `0x180010ced`: `Task boot trigger removed\n`
- `0x180010c60`: `Task delay start trigger removed\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=132
void __fastcall NGenParser::ProcessNewCommandLineOptionsHelper(
        NGenParser *this,
        struct NewCommandLineOptions *a2,
        struct ICorSvc *a3,
        GUID *a4,
        struct ICorSvcLogger *a5)
{
  int v9; // eax
  int v10; // eax
  int v11; // eax
  int v12; // eax
  bool v13; // dl
  __int64 v14; // rdx
  __int64 v15; // r9
  __int64 v16; // r8
  int v17; // eax
  int v18; // eax
  int v19; // eax
  int v20; // eax
  int v21; // eax
  int v22; // eax
  __int64 v23; // rcx
  int v24; // eax
  int v25; // eax
  int v26; // eax
  __int64 v27; // rcx
  int v28; // eax
  int v29; // eax
  int v30; // eax
  __int64 v31; // rcx
  int v32; // eax
  int v33; // eax
  int v34; // eax
  int v35; // eax
  int v36; // eax
  int v37; // eax
  const unsigned __int16 *v38; // rdx
  __int64 v39; // rdx
  int v40; // eax
  int v41; // eax
  int v42; // eax
  int v43; // eax
  int v44; // eax
  int v45; // eax
  __int64 (__fastcall ***v46)(_QWORD, GUID *, __int64 *); // rsi
  int v47; // eax
  int v48; // eax
  int v49; // eax
  __int64 v50; // rdx
  __int64 v51; // rdx
  int v52; // eax
  const char *v53; // rdx
  __int64 (__fastcall ***v54)(_QWORD, GUID *, __int64 *); // rsi
  int v55; // eax
  int v56; // eax
  int v57; // eax
  int v58; // eax
  int v59; // eax
  int v60; // eax
  __int64 (__fastcall ***v61)(_QWORD, GUID *, __int64 *); // r14
  int v62; // eax
  int v63; // eax
  int v64; // ebx
  __int64 v65; // rdx
  __int64 (__fastcall ***v66)(_QWORD, GUID *, __int64 *); // rsi
  int v67; // eax
  int v68; // eax
  __int64 (__fastcall ***v69)(_QWORD, GUID *, __int64 *); // rsi
  int v70; // eax
  __int64 v71; // rdx
  int v72; // eax
  __int64 v73; // r8
  int v74; // eax
  __int64 v75; // rdx
  int v76; // eax
  int v77; // eax
  __int64 (__fastcall ***v78)(_QWORD, GUID *, __int64 *); // rsi
  int v79; // eax
  int v80; // eax
  __int64 (__fastcall ***v81)(_QWORD, GUID *, __int64 *); // rsi
  int v82; // eax
  int v83; // eax
  int v84; // eax
  __int64 v85; // rdx
  int v86; // eax
  int v87; // eax
  __int64 (__fastcall ***v88)(_QWORD, GUID *, __int64 *); // rsi
  int v89; // eax
  int v90; // eax
  __int64 (__fastcall ***v91)(_QWORD, GUID *, __int64 *); // rsi
  int v92; // eax
  int v93; // eax
  int v94; // eax
  int v95; // eax
  int v96; // eax
  const struct SString *v97; // rax
  const struct SString *v98; // rax
  const struct SString *v99; // rax
  const struct SString *v100; // rax
  const struct SString *v101; // rax
  const struct SString *v102; // rax
  const struct SString *v103; // rax
  const struct SString *v104; // rax
  const struct SString *v105; // rax
  const struct SString *v106; // rax
  const struct SString *v107; // rax
  const struct SString *v108; // rax
  const struct SString *v109; // rax
  int v110; // r9d
  const struct SString *v111; // rax
  const struct SString *v112; // rax
  const struct SString *v113; // rax
  const struct SString *v114; // rax
  int v115; // r9d
  const struct SString *v116; // rax
  const struct SString *v117; // rax
  int v118; // r9d
  const struct SString *v119; // rax
  const struct SString *v120; // rax
  __int128 v121; // [rsp+50h] [rbp-B0h] BYREF
  void *lpMem; // [rsp+60h] [rbp-A0h]
  __int64 *v123; // [rsp+70h] [rbp-90h]
  __int64 v124; // [rsp+78h] [rbp-88h] BYREF
  int v125; // [rsp+80h] [rbp-80h]
  __int64 v126; // [rsp+88h] [rbp-78h] BYREF
  int v127; // [rsp+90h] [rbp-70h]
  __int64 v128; // [rsp+98h] [rbp-68h] BYREF
  int v129; // [rsp+A0h] [rbp-60h]
  bool v130; // [rsp+A8h] [rbp-58h] BYREF
  __int64 (__fastcall ***v131)(_QWORD, GUID *, __int64 *); // [rsp+B0h] [rbp-50h] BYREF
  int v132; // [rsp+B8h] [rbp-48h]
  __int64 v133; // [rsp+C0h] [rbp-40h] BYREF
  int v134; // [rsp+C8h] [rbp-38h]
  __int64 v135; // [rsp+D0h] [rbp-30h] BYREF
  int v136; // [rsp+D8h] [rbp-28h]
  __int64 (__fastcall ***v137)(_QWORD, GUID *, __int64 *); // [rsp+E0h] [rbp-20h] BYREF
  int v138; // [rsp+E8h] [rbp-18h]
  __int64 v139; // [rsp+F0h] [rbp-10h] BYREF
  int v140; // [rsp+F8h] [rbp-8h]
  __int64 v141; // [rsp+100h] [rbp+0h] BYREF
  int v142; // [rsp+108h] [rbp+8h]
  unsigned __int16 v143[66]; // [rsp+110h] [rbp+10h] BYREF
  int v144; // [rsp+194h] [rbp+94h]
  unsigned int v145; // [rsp+1B0h] [rbp+B0h] BYREF
  __int64 v146; // [rsp+1B4h] [rbp+B4h]
  void *v147; // [rsp+1C0h] [rbp+C0h]
  __int16 v148; // [rsp+1C8h] [rbp+C8h] BYREF

  if ( !CLRConfig::GetConfigValue(
          (const struct CLRConfig::ConfigDWORDInfo *)&CLRConfig::EXTERNAL_NGENUseService,
          (bool)a2,
          &v130) )
    *((_DWORD *)a2 + 36) = 0;
  v138 = 0;
  v123 = (__int64 *)&v137;
  v137 = 0;
  v9 = (*(__int64 (__fastcall **)(struct ICorSvc *, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)a3 + 24LL))(
         a3,
         &v137);
  if ( v9 < 0 )
    ThrowHR(v9);
  v10 = v138;
  if ( v137 )
    v10 = 1;
  v138 = v10;
  v132 = 0;
  v123 = (__int64 *)&v131;
  v131 = 0;
  v11 = (**v137)(v137, &IID_ICorSvcInstaller, (__int64 *)&v131);
  if ( v11 < 0 )
    ThrowHR(v11);
  v12 = v132;
  if ( v131 )
    v12 = 1;
  v132 = v12;
  ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), struct ICorSvcLogger *))(*v131)[6])(
    v131,
    a5);
  v133 = 0;
  v134 = 0;
  v128 = 0;
  v129 = 0;
  v135 = 0;
  v136 = 0;
  v126 = 0;
  v127 = 0;
  v124 = 0;
  v125 = 0;
  if ( !*((_DWORD *)a2 + 39) && *((int *)a2 + 41) >= 2 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)this + 8LL))(*(_QWORD *)this);
  if ( CLRConfig::GetConfigValue((const struct CLRConfig::ConfigDWORDInfo *)&CLRConfig::EXTERNAL_ZapDisable, v13, &v130) )
  {
    if ( *(_DWORD *)a2 != 3 )
    {
      *(_QWORD *)&v121 = 0x200000002LL;
      DWORD2(v121) = 16;
      lpMem = (void *)&SString::s_EmptyBuffer;
      SString::Set((SString *)&v121, L"Warning: ZapDisable is turned on.\n");
      (***(void (__fastcall ****)(_QWORD, __int128 *))this)(*(_QWORD *)this, &v121);
      if ( (BYTE8(v121) & 8) != 0 )
        operator delete(lpMem);
    }
  }
  v14 = *((_DWORD *)a2 + 8) & 4;
  if ( (*((_DWORD *)a2 + 8) & 4) != 0 )
  {
    if ( *((_DWORD *)a2 + 36) )
    {
      v100 = (const struct SString *)SString::SString(&v121, v14, L"Error: Cannot use /NoRoot with /Queue.");
      ThrowHR(-2147024736, v100);
    }
    if ( *(_DWORD *)a2 )
    {
      if ( *(_DWORD *)a2 == 1 )
      {
        if ( *((_DWORD *)a2 + 6) != 1 || *((_QWORD *)a2 + 5) )
        {
          v98 = (const struct SString *)SString::SString(
                                          &v121,
                                          v14,
                                          L"Error: Scenario, /ExeConfig or /AppBase not allowed with Uninstall /NoRoot command.");
          ThrowHR(-2147024736, v98);
        }
      }
      else if ( *(_DWORD *)a2 != 6 )
      {
        v97 = (const struct SString *)SString::SString(
                                        &v121,
                                        v14,
                                        L"Error: /NoRoot can only be used with Install or Uninstall or CreatePDB commands.");
        ThrowHR(-2147024736, v97);
      }
    }
  }
  v15 = *((_QWORD *)a2 + 14);
  v16 = *((_QWORD *)a2 + 12);
  if ( (v16 == 0) != (v15 == 0) )
  {
    v101 = (const struct SString *)SString::SString(
                                     &v121,
                                     v14,
                                     L"Error: If either /Package or /LocalAppData is specified, then BOTH must be specified.");
    ThrowHR(-2147024736, v101);
  }
  if ( v16 )
  {
    if ( !(_DWORD)v14 )
    {
      v102 = (const struct SString *)SString::SString(&v121, v14, L"Error: Cannot use /Package without /NoRoot.");
      ThrowHR(-2147024736, v102);
    }
    if ( !*(_DWORD *)a2 && (*((_BYTE *)a2 + 24) & 0x20) == 0 )
    {
      v103 = (const struct SString *)SString::SString(&v121, v14, L"Error: Install /Package requires /NoDependencies.");
      ThrowHR(-2147024736, v103);
    }
  }
  if ( (*((_QWORD *)a2 + 10) || v16 || v15) && *(_DWORD *)a2 > 1u && *(_DWORD *)a2 != 6 )
  {
    v104 = (const struct SString *)SString::SString(
                                     &v121,
                                     v14,
                                     L"Error: /Version, /LocalAppData and /Package can only be used with Install or Uninst"
                                      "all or CreatePDB commands.");
    ThrowHR(-2147024736, v104);
  }
  v142 = 0;
  v123 = &v141;
  v141 = 0;
  v17 = (**v131)(v131, &IID_ICorSvcRepository, &v141);
  if ( v17 < 0 )
    ThrowHR(v17);
  v18 = v142;
  if ( v141 )
    v18 = 1;
  v142 = v18;
  v19 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v141 + 24LL))(
          v141,
          *((_QWORD *)a2 + 7),
          *((unsigned int *)a2 + 18));
  if ( v19 < 0 )
    ThrowHR(v19);
  v140 = 0;
  v123 = &v139;
  v139 = 0;
  v20 = (**v131)(v131, &IID_ICorSvcSetPrivateAttributes, &v139);
  if ( v20 < 0 )
    ThrowHR(v20);
  v21 = v140;
  if ( v139 )
    v21 = 1;
  v140 = v21;
  v121 = *((_OWORD *)a2 + 8);
  v22 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v139 + 24LL))(v139, &v121);
  if ( v22 < 0 )
    ThrowHR(v22);
  if ( *((_QWORD *)a2 + 10) )
  {
    v23 = v124;
    if ( !v124 )
    {
      v123 = &v124;
      if ( v125 )
        v125 = 0;
      v124 = 0;
      v24 = (**v131)(v131, &IID_ICorSvcManager2, &v124);
      if ( v24 < 0 )
        ThrowHR(v24);
      v25 = v125;
      v23 = v124;
      if ( v124 )
        v25 = 1;
      v125 = v25;
    }
    v26 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v23 + 24LL))(v23, *((_QWORD *)a2 + 10));
    if ( v26 < 0 )
      ThrowHR(v26);
  }
  if ( *((_QWORD *)a2 + 12) )
  {
    v27 = v124;
    if ( !v124 )
    {
      v123 = &v124;
      if ( v125 )
        v125 = 0;
      v124 = 0;
      v28 = (**v131)(v131, &IID_ICorSvcManager2, &v124);
      if ( v28 < 0 )
        ThrowHR(v28);
      v29 = v125;
      v27 = v124;
      if ( v124 )
        v29 = 1;
      v125 = v29;
    }
    v30 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v27 + 32LL))(v27, *((_QWORD *)a2 + 12));
    if ( v30 < 0 )
      ThrowHR(v30);
  }
  if ( *((_QWORD *)a2 + 14) )
  {
    v31 = v124;
    if ( !v124 )
    {
      v123 = &v124;
      if ( v125 )
        v125 = 0;
      v124 = 0;
      v32 = (**v131)(v131, &IID_ICorSvcManager2, &v124);
      if ( v32 < 0 )
        ThrowHR(v32);
      v33 = v125;
      v31 = v124;
      if ( v124 )
        v33 = 1;
      v125 = v33;
    }
    v34 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v31 + 40LL))(v31, *((_QWORD *)a2 + 14));
    if ( v34 < 0 )
      ThrowHR(v34);
  }
  if ( *((_DWORD *)a2 + 40) )
  {
    DWORD2(v121) = 0;
    v123 = (__int64 *)&v121;
    *(_QWORD *)&v121 = 0;
    v35 = (**v131)(v131, &IID_ICorSvcSetLegacyServiceBehavior, (__int64 *)&v121);
    if ( v35 < 0 )
      ThrowHR(v35);
    v36 = DWORD2(v121);
    if ( (_QWORD)v121 )
      v36 = 1;
    DWORD2(v121) = v36;
    v37 = (*(__int64 (**)(void))(*(_QWORD *)v121 + 24LL))();
    if ( v37 < 0 )
      ThrowHR(v37);
    if ( DWORD2(v121) )
    {
      if ( (_QWORD)v121 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v121 + 16LL))(v121);
      DWORD2(v121) = 0;
    }
  }
  v38 = (const unsigned __int16 *)*((_QWORD *)a2 + 1);
  v146 = 512;
  v147 = &v148;
  v145 = 2;
  v148 = 0;
  SString::Set((SString *)&v145, v38);
  if ( *(_DWORD *)a2 )
  {
    if ( *(_DWORD *)a2 == 1 )
    {
      if ( !*((_QWORD *)a2 + 1) || v145 >> ((v146 & 0x100000000LL) == 0) == 1 )
      {
        v119 = (const struct SString *)SString::SString(
                                         &v121,
                                         v39,
                                         L"Error: You must specify an assembly to uninstall.");
        ThrowHR(-2147024894, v119);
      }
      if ( *((_DWORD *)a2 + 36) && !*((_DWORD *)a2 + 38) )
      {
        v116 = (const struct SString *)SString::SString(&v121, v39, L"Error: Cannot queue an uninstall action");
        ThrowHR(-2147024736, v116);
      }
      v78 = v131;
      v123 = &v126;
      if ( v127 )
      {
        if ( v126 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v126 + 16LL))(v126);
        v127 = 0;
      }
      v126 = 0;
      v79 = (**v78)(v78, &IID_ICorSvcManager, &v126);
      if ( v79 < 0 )
        ThrowHR(v79);
      v80 = v127;
      if ( v126 )
        v80 = 1;
      v127 = v80;
      v81 = v131;
      v123 = &v133;
      if ( v134 )
      {
        if ( v133 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v133 + 16LL))(v133);
        v134 = 0;
      }
      v133 = 0;
      v82 = (**v81)(v81, &IID_ICorSvcAdvancedInstaller, &v133);
      if ( v82 < 0 )
        ThrowHR(v82);
      v83 = v134;
      if ( v133 )
        v83 = 1;
      v134 = v83;
      v84 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _DWORD))(*(_QWORD *)v133 + 32LL))(
              v133,
              *((_QWORD *)a2 + 1),
              *((unsigned int *)a2 + 6),
              *((_QWORD *)a2 + 5),
              *((_DWORD *)a2 + 8));
      if ( v84 == -2147024894 )
      {
        v117 = (const struct SString *)SString::SString(&v121, v85, L"Error: The specified assembly is not installed.");
        ThrowHR(v118, v117);
      }
      if ( v84 < 0 )
        ThrowHR(v84);
      if ( *((_DWORD *)a2 + 36) )
      {
        v86 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v126 + 40LL))(v126, 0);
        if ( v86 < 0 )
          ThrowHR(v86);
      }
      else
      {
        v87 = (*v131)[5](v131, a4, 0);
        if ( v87 < 0 )
          ThrowHR(v87);
      }
    }
    else if ( *(_DWORD *)a2 == 2 )
    {
      v66 = v131;
      v123 = &v128;
      if ( v129 )
      {
        if ( v128 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v128 + 16LL))(v128);
        v129 = 0;
      }
      v128 = 0;
      v67 = (**v66)(v66, &IID_ICorSvcOptimizer, &v128);
      if ( v67 < 0 )
        ThrowHR(v67);
      v68 = v129;
      if ( v128 )
        v68 = 1;
      v129 = v68;
      v69 = v131;
      v123 = &v126;
      if ( v127 )
      {
        if ( v126 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v126 + 16LL))(v126);
        v127 = 0;
      }
      v126 = 0;
      v70 = (**v69)(v69, &IID_ICorSvcManager, &v126);
      if ( v70 < 0 )
        ThrowHR(v70);
      v72 = v127;
      if ( v126 )
        v72 = 1;
      v127 = v72;
      v73 = *((unsigned int *)a2 + 7);
      if ( (v73 & 2) != 0 && !*((_DWORD *)a2 + 36) )
      {
        v111 = (const struct SString *)SString::SString(
                                         &v121,
                                         v71,
                                         L"Error: /postreboot requires the use of /queue option.");
        ThrowHR(-2147024736, v111);
      }
      if ( *((_DWORD *)a2 + 37) && !*((_DWORD *)a2 + 36) )
      {
        v112 = (const struct SString *)SString::SString(&v121, v71, L"Error: /delay requires the use of /queue option.");
        ThrowHR(-2147024736, v112);
      }
      if ( *((_QWORD *)a2 + 1) )
      {
        v113 = (const struct SString *)SString::SString(&v121, v71, L"Error: Cannot specify an assembly name to update");
        ThrowHR(-2147024736, v113);
      }
      v74 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD))(*(_QWORD *)v128 + 24LL))(
              v128,
              0,
              v73,
              *((unsigned int *)a2 + 8));
      if ( v74 == -2147024894 )
      {
        v114 = (const struct SString *)SString::SString(&v121, v75, L"Error: The specified assembly is not installed.");
        ThrowHR(v115, v114);
      }
      if ( v74 < 0 )
        ThrowHR(v74);
      if ( *((_DWORD *)a2 + 36) )
      {
        v76 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v126 + 40LL))(
                v126,
                *((_DWORD *)a2 + 37) != 0 ? 4 : 0);
        if ( v76 < 0 )
          ThrowHR(v76);
      }
      else
      {
        v77 = (*v131)[5](v131, a4, (__int64 *)1);
        if ( v77 < 0 )
          ThrowHR(v77);
      }
    }
    else if ( *(_DWORD *)a2 == 3 )
    {
      v61 = v131;
      v123 = &v128;
      if ( v129 )
      {
        if ( v128 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v128 + 16LL))(v128);
        v129 = 0;
      }
      v128 = 0;
      v62 = (**v61)(v61, &IID_ICorSvcOptimizer, &v128);
      if ( v62 < 0 )
        ThrowHR(v62);
      v63 = v129;
      if ( v128 )
        v63 = 1;
      v129 = v63;
      (*(void (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)this + 24LL))(*(_QWORD *)this, 0);
      v64 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v128 + 32LL))(
              v128,
              *((_QWORD *)a2 + 1),
              *((unsigned int *)a2 + 8));
      (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)this + 24LL))(*(_QWORD *)this, 1);
      if ( v64 == -2147024894 )
      {
        v109 = (const struct SString *)SString::SString(&v121, v65, L"Error: The specified assembly is not installed.");
        ThrowHR(v110, v109);
      }
      if ( v64 < 0 )
        ThrowHR(v64);
    }
    else if ( *(_DWORD *)a2 == 4 )
    {
      if ( *((_DWORD *)a2 + 36) )
      {
        v108 = (const struct SString *)SString::SString(&v121, v39, L"Error: Cannot queue an ExecuteQueuedItems action");
        ThrowHR(-2147024736, v108);
      }
      v54 = v131;
      v123 = &v128;
      if ( v129 )
      {
        if ( v128 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v128 + 16LL))(v128);
        v129 = 0;
      }
      v128 = 0;
      v55 = (**v54)(v54, &IID_ICorSvcOptimizer, &v128);
      if ( v55 < 0 )
        ThrowHR(v55);
      v56 = v129;
      if ( v128 )
        v56 = 1;
      v129 = v56;
      v57 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v128 + 40LL))(v128, 0);
      if ( v57 < 0 )
        ThrowHR(v57);
      v58 = (*v131)[5](v131, a4, (__int64 *)3);
      if ( v58 < 0 )
        ThrowHR(v58);
      v59 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v128 + 40LL))(v128, *((unsigned int *)a2 + 42));
      if ( v59 < 0 )
        ThrowHR(v59);
      v60 = (*v131)[5](v131, a4, (__int64 *)1);
      if ( v60 < 0 )
        ThrowHR(v60);
    }
    else if ( *(_DWORD *)a2 == 5 )
    {
      NGenParser::Output(this, "\n");
      if ( IsNgenOffline() )
      {
        v106 = (const struct SString *)SString::SString(
                                         &v121,
                                         v50,
                                         L"Error: Cannot interact with the service when using the offline ngen feature");
        ThrowHR(-2147024736, v106);
      }
      v51 = *((unsigned int *)a2 + 43);
      if ( (_DWORD)v51 == -1 )
      {
        v107 = (const struct SString *)SString::SString(
                                         &v121,
                                         v51,
                                         L"Error: queue action must be pause|continue|status");
        ThrowHR(-2147024736, v107);
      }
      v52 = (*(__int64 (__fastcall **)(struct ICorSvc *, __int64, unsigned __int16 *))(*(_QWORD *)a3 + 48LL))(
              a3,
              v51,
              v143);
      if ( v52 < 0 )
        ThrowHR(v52);
      if ( *((_DWORD *)a2 + 43) == 4 )
      {
        NGenParser::Output(this, "Service name is: ");
        NGenParser::Output(this, v143);
        NGenParser::Output(this, "\n");
      }
      switch ( v144 )
      {
        case 1:
          v53 = "The .NET Runtime Optimization Service is stopped.\n";
          break;
        case 2:
          v53 = "The .NET Runtime Optimization Service is starting.\n";
          break;
        case 3:
          v53 = "The .NET Runtime Optimization Service is stopping.\n";
          break;
        case 4:
          v53 = "The .NET Runtime Optimization Service is running.\n";
          break;
        case 5:
          v53 = "The .NET Runtime Optimization Service continue is pending.\n";
          break;
        case 6:
          v53 = "The .NET Runtime Optimization Service pause is pending.\n";
          break;
        case 7:
          v53 = "The .NET Runtime Optimization Service is started and paused.\n";
          break;
        default:
          v53 = "Unknown state";
          break;
      }
      NGenParser::Output(this, v53);
    }
    else if ( *(_DWORD *)a2 == 6 )
    {
      if ( !*((_QWORD *)a2 + 22) || !*((_QWORD *)a2 + 24) )
      {
        v105 = (const struct SString *)SString::SString(
                                         &v121,
                                         v39,
                                         L"Error: insufficient number of arguments to createpdb");
        ThrowHR(-2147024736, v105);
      }
      v46 = v137;
      v123 = &v135;
      if ( v136 )
      {
        if ( v135 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v135 + 16LL))(v135);
        v136 = 0;
      }
      v135 = 0;
      v47 = (**v46)(v46, &IID_ICorSvcOptimizer3, &v135);
      if ( v47 < 0 )
        ThrowHR(v47);
      v48 = v136;
      if ( v135 )
        v48 = 1;
      v136 = v48;
      v49 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v135 + 56LL))(
              v135,
              *((_QWORD *)a2 + 22),
              *((_QWORD *)a2 + 24),
              *((unsigned int *)a2 + 52),
              *((_QWORD *)a2 + 27));
      if ( v49 < 0 )
        ThrowHR(v49);
    }
    else
    {
      if ( *(_DWORD *)a2 == 7 )
      {
        DWORD2(v121) = 0;
        v123 = (__int64 *)&v121;
        *(_QWORD *)&v121 = 0;
        v43 = (**v131)(v131, &IID_ICorSvcSetTaskBootTriggerState, (__int64 *)&v121);
        if ( v43 < 0 )
          ThrowHR(v43);
        v44 = DWORD2(v121);
        if ( (_QWORD)v121 )
          v44 = 1;
        DWORD2(v121) = v44;
        v45 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)v121 + 24LL))(v121, 0);
        if ( v45 < 0 )
          ThrowHR(v45);
        NGenParser::Output(this, "Task boot trigger removed\n");
      }
      else
      {
        if ( *(_DWORD *)a2 != 8 )
          ThrowHR(-2147418113);
        DWORD2(v121) = 0;
        v123 = (__int64 *)&v121;
        *(_QWORD *)&v121 = 0;
        v40 = (**v131)(v131, &IID_ICorSvcSetTaskDelayStartTriggerState, (__int64 *)&v121);
        if ( v40 < 0 )
          ThrowHR(v40);
        v41 = DWORD2(v121);
        if ( (_QWORD)v121 )
          v41 = 1;
        DWORD2(v121) = v41;
        v42 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)v121 + 24LL))(v121, 0);
        if ( v42 < 0 )
          ThrowHR(v42);
        NGenParser::Output(this, "Task delay start trigger removed\n");
      }
      if ( DWORD2(v121) )
      {
        if ( (_QWORD)v121 )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v121 + 16LL))(v121);
        DWORD2(v121) = 0;
      }
    }
  }
  else
  {
    if ( !*((_QWORD *)a2 + 1) || v145 >> ((v146 & 0x100000000LL) == 0) == 1 )
    {
      v99 = (const struct SString *)SString::SString(&v121, v39, L"Error: You must specify an assembly to install.");
      ThrowHR(-2147024894, v99);
    }
    if ( (*((_BYTE *)a2 + 32) & 2) != 0 && (!*((_DWORD *)a2 + 36) || *((_DWORD *)a2 + 42) != 1) )
    {
      v120 = (const struct SString *)SString::SString(&v121, v39, L"Error: Cannot use /NetfxPri1 without /Queue:1.");
      ThrowHR(-2147024736, v120);
    }
    v88 = v131;
    v123 = &v133;
    if ( v134 )
    {
      if ( v133 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v133 + 16LL))(v133);
      v134 = 0;
    }
    v133 = 0;
    v89 = (**v88)(v88, &IID_ICorSvcAdvancedInstaller, &v133);
    if ( v89 < 0 )
      ThrowHR(v89);
    v90 = v134;
    if ( v133 )
      v90 = 1;
    v134 = v90;
    v91 = v131;
    v123 = &v126;
    if ( v127 )
    {
      if ( v126 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v126 + 16LL))(v126);
      v127 = 0;
    }
    v126 = 0;
    v92 = (**v91)(v91, &IID_ICorSvcManager, &v126);
    if ( v92 < 0 )
      ThrowHR(v92);
    v93 = v127;
    if ( v126 )
      v93 = 1;
    v127 = v93;
    v94 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD))(*(_QWORD *)v133 + 24LL))(
            v133,
            *((_QWORD *)a2 + 1),
            *((unsigned int *)a2 + 6),
            *((_QWORD *)a2 + 5),
            *((_DWORD *)a2 + 8),
            *((_DWORD *)a2 + 42));
    if ( v94 < 0 )
      ThrowHR(v94);
    if ( *((_DWORD *)a2 + 36) )
    {
      v95 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v126 + 40LL))(v126, 0);
      if ( v95 < 0 )
        ThrowHR(v95);
    }
    else
    {
      v96 = (*v131)[5](v131, a4, 0);
      if ( v96 < 0 )
        ThrowHR(v96);
    }
  }
  if ( (v146 & 0x800000000LL) != 0 )
    operator delete(v147);
  if ( v140 )
  {
    if ( v139 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v139 + 16LL))(v139);
    v140 = 0;
  }
  if ( v142 )
  {
    if ( v141 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v141 + 16LL))(v141);
    v142 = 0;
  }
  if ( v125 )
  {
    if ( v124 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v124 + 16LL))(v124);
    v125 = 0;
  }
  if ( v127 )
  {
    if ( v126 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v126 + 16LL))(v126);
    v127 = 0;
  }
  if ( v136 )
  {
    if ( v135 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v135 + 16LL))(v135);
    v136 = 0;
  }
  if ( v129 )
  {
    if ( v128 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v128 + 16LL))(v128);
    v129 = 0;
  }
  if ( v134 )
  {
    if ( v133 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v133 + 16LL))(v133);
    v134 = 0;
  }
  if ( v132 )
  {
    if ( v131 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v131)[2])(v131);
    v132 = 0;
  }
  if ( v138 )
  {
    if ( v137 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v137)[2])(v137);
    v138 = 0;
  }
}

```

## disassembly

```asm
0x180010530  push    rbp
0x180010532  push    rbx
0x180010533  push    rsi
0x180010534  push    rdi
0x180010535  push    r12
0x180010537  push    r13
0x180010539  push    r14
0x18001053b  push    r15
0x18001053d  lea     rbp, [rsp-2E8h]
0x180010545  sub     rsp, 3E8h
0x18001054c  mov     rax, cs:__security_cookie
0x180010553  xor     rax, rsp
0x180010556  mov     [rbp+320h+var_50], rax
0x18001055d  mov     r12, r9
0x180010560  mov     r15, r8
0x180010563  mov     rdi, rdx
0x180010566  mov     rsi, rcx
0x180010569  mov     r14, [rbp+320h+arg_20]
0x180010570  xor     r13d, r13d
0x180010573  mov     [rsp+420h+var_3E0], r13d
0x180010578  lea     r8, [rbp+320h+var_378]; bool *
0x18001057c  lea     rcx, ?EXTERNAL_NGENUseService@CLRConfig@@2UConfigDWORDInfo@1@B; struct CLRConfig::ConfigDWORDInfo *
0x180010583  call    ?GetConfigValue@CLRConfig@@SAKAEBUConfigDWORDInfo@1@_NPEA_N@Z; CLRConfig::GetConfigValue(CLRConfig::ConfigDWORDInfo const &,bool,bool *)
0x180010588  test    eax, eax
0x18001058a  jnz     short loc_180010593
0x18001058c  mov     [rdi+90h], r13d
0x180010593  mov     [rbp+320h+var_340], r13
0x180010597  mov     [rbp+320h+var_338], r13d
0x18001059b  lea     rax, [rbp+320h+var_340]
0x18001059f  mov     [rsp+420h+var_3B0], rax
0x1800105a4  mov     [rbp+320h+var_340], r13
0x1800105a8  mov     ebx, 1
0x1800105ad  mov     [rsp+420h+var_3E0], ebx
0x1800105b1  mov     rax, [r15]
0x1800105b4  lea     rdx, [rbp+320h+var_340]
0x1800105b8  mov     rcx, r15
0x1800105bb  mov     rax, [rax+18h]
0x1800105bf  call    cs:__guard_dispatch_icall_fptr
0x1800105c5  test    eax, eax
0x1800105c7  js      loc_1800117A4
0x1800105cd  and     ebx, 0FFFFFFFEh
0x1800105d0  mov     [rsp+420h+var_3E0], ebx
0x1800105d4  mov     eax, [rbp+320h+var_338]
0x1800105d7  cmp     [rbp+320h+var_340], r13
0x1800105db  mov     ecx, 1
0x1800105e0  cmovnz  eax, ecx
0x1800105e3  mov     [rbp+320h+var_338], eax
0x1800105e6  mov     [rbp+320h+var_370], r13
0x1800105ea  mov     [rbp+320h+var_368], r13d
0x1800105ee  mov     rcx, [rbp+320h+var_340]
0x1800105f2  lea     rax, [rbp+320h+var_370]
0x1800105f6  mov     [rsp+420h+var_3B0], rax
0x1800105fb  mov     [rbp+320h+var_370], r13
0x1800105ff  or      ebx, 2
0x180010602  mov     [rsp+420h+var_3E0], ebx
0x180010606  mov     rax, [rcx]
0x180010609  lea     r8, [rbp+320h+var_370]
0x18001060d  lea     rdx, IID_ICorSvcInstaller
0x180010614  mov     rax, [rax]
0x180010617  call    cs:__guard_dispatch_icall_fptr
0x18001061d  test    eax, eax
0x18001061f  js      loc_1800117AC
0x180010625  and     ebx, 0FFFFFFFDh
0x180010628  mov     [rsp+420h+var_3E0], ebx
0x18001062c  mov     eax, [rbp+320h+var_368]
0x18001062f  mov     rcx, [rbp+320h+var_370]
0x180010633  test    rcx, rcx
0x180010636  mov     edx, 1
0x18001063b  cmovnz  eax, edx
0x18001063e  mov     [rbp+320h+var_368], eax
0x180010641  mov     rax, [rcx]
0x180010644  mov     rdx, r14
0x180010647  mov     rax, [rax+30h]
0x18001064b  call    cs:__guard_dispatch_icall_fptr
0x180010651  mov     [rbp+320h+var_360], r13
0x180010655  mov     [rbp+320h+var_358], r13d
0x180010659  mov     [rbp+320h+var_388], r13
0x18001065d  mov     [rbp+320h+var_380], r13d
0x180010661  mov     [rbp+320h+var_350], r13
0x180010665  mov     [rbp+320h+var_348], r13d
0x180010669  mov     [rbp+320h+var_398], r13
0x18001066d  mov     [rbp+320h+var_390], r13d
0x180010671  mov     [rsp+420h+var_3A8], r13
0x180010676  mov     [rbp+320h+var_3A0], r13d
0x18001067a  cmp     [rdi+9Ch], r13d
0x180010681  jnz     short loc_18001069C
0x180010683  cmp     dword ptr [rdi+0A4h], 2
0x18001068a  jl      short loc_18001069C
0x18001068c  mov     rcx, [rsi]
0x18001068f  mov     rax, [rcx]
0x180010692  mov     rax, [rax+8]
0x180010696  call    cs:__guard_dispatch_icall_fptr
0x18001069c  lea     r8, [rbp+320h+var_378]; bool *
0x1800106a0  lea     rcx, ?EXTERNAL_ZapDisable@CLRConfig@@2UConfigDWORDInfo@1@B; struct CLRConfig::ConfigDWORDInfo *
0x1800106a7  call    ?GetConfigValue@CLRConfig@@SAKAEBUConfigDWORDInfo@1@_NPEA_N@Z; CLRConfig::GetConfigValue(CLRConfig::ConfigDWORDInfo const &,bool,bool *)
0x1800106ac  test    eax, eax
0x1800106ae  jz      short loc_180010711
0x1800106b0  cmp     dword ptr [rdi], 3
0x1800106b3  jz      short loc_180010711
0x1800106b5  mov     dword ptr [rsp+420h+var_3D0], 2
0x1800106bd  mov     dword ptr [rsp+420h+var_3D0+4], 2
0x1800106c5  mov     dword ptr [rsp+420h+var_3D0+8], 10h
0x1800106cd  lea     rax, ?s_EmptyBuffer@SString@@0QBEB; uchar const near * const SString::s_EmptyBuffer
0x1800106d4  mov     [rsp+420h+lpMem], rax
0x1800106d9  lea     rdx, aWarningZapdisa; "Warning: ZapDisable is turned on.\n"
0x1800106e0  lea     rcx, [rsp+420h+var_3D0]; this
0x1800106e5  call    ?Set@SString@@QEAAXPEBG@Z; SString::Set(ushort const *)
0x1800106ea  nop
0x1800106eb  mov     rcx, [rsi]
0x1800106ee  mov     rax, [rcx]
0x1800106f1  lea     rdx, [rsp+420h+var_3D0]
0x1800106f6  mov     rax, [rax]
0x1800106f9  call    cs:__guard_dispatch_icall_fptr
0x1800106ff  nop
0x180010700  test    byte ptr [rsp+420h+var_3D0+8], 8
0x180010705  jz      short loc_180010711
0x180010707  mov     rcx, [rsp+420h+lpMem]; lpMem
0x18001070c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180010711  mov     edx, [rdi+20h]
0x180010714  and     edx, 4
0x180010717  jz      short loc_180010757
0x180010719  cmp     [rdi+90h], r13d
0x180010720  jnz     loc_1800117B4
0x180010726  mov     r14d, 1
0x18001072c  cmp     [rdi], r13d
0x18001072f  jz      short loc_18001075D
0x180010731  cmp     [rdi], r14d
0x180010734  jz      short loc_180010741
0x180010736  cmp     dword ptr [rdi], 6
0x180010739  jnz     loc_1800116FC
0x18001073f  jmp     short loc_18001075D
0x180010741  cmp     [rdi+18h], r14d
0x180010745  jnz     loc_18001171C
0x18001074b  cmp     [rdi+28h], r13
0x18001074f  jnz     loc_18001171C
0x180010755  jmp     short loc_18001075D
0x180010757  mov     r14d, 1
0x18001075d  mov     r9, [rdi+70h]
0x180010761  mov     r8, [rdi+60h]
0x180010765  test    r8, r8
0x180010768  setz    cl
0x18001076b  test    r9, r9
0x18001076e  setz    al
0x180010771  cmp     cl, al
0x180010773  jnz     loc_1800117D4
0x180010779  test    r8, r8
0x18001077c  jz      short loc_180010795
0x18001077e  test    edx, edx
0x180010780  jz      loc_1800117F4
0x180010786  cmp     [rdi], r13d
0x180010789  jnz     short loc_180010795
0x18001078b  test    byte ptr [rdi+18h], 20h
0x18001078f  jz      loc_180011814
0x180010795  cmp     [rdi+50h], r13
0x180010799  jnz     short loc_1800107A5
0x18001079b  test    r8, r8
0x18001079e  jnz     short loc_1800107A5
0x1800107a0  test    r9, r9
0x1800107a3  jz      short loc_1800107B3
0x1800107a5  cmp     [rdi], r14d
0x1800107a8  jbe     short loc_1800107B3
0x1800107aa  cmp     dword ptr [rdi], 6
0x1800107ad  jnz     loc_180011834
0x1800107b3  mov     [rbp+320h+var_320], r13
0x1800107b7  mov     [rbp+320h+var_318], r13d
0x1800107bb  mov     rcx, [rbp+320h+var_370]
0x1800107bf  lea     rax, [rbp+320h+var_320]
0x1800107c3  mov     [rsp+420h+var_3B0], rax
0x1800107c8  mov     [rbp+320h+var_320], r13
0x1800107cc  or      ebx, 4
0x1800107cf  mov     [rsp+420h+var_3E0], ebx
0x1800107d3  mov     rax, [rcx]
0x1800107d6  lea     r8, [rbp+320h+var_320]
0x1800107da  lea     rdx, IID_ICorSvcRepository
0x1800107e1  mov     rax, [rax]
0x1800107e4  call    cs:__guard_dispatch_icall_fptr
0x1800107ea  test    eax, eax
0x1800107ec  js      loc_180011854
0x1800107f2  and     ebx, 0FFFFFFFBh
0x1800107f5  mov     [rsp+420h+var_3E0], ebx
0x1800107f9  mov     eax, [rbp+320h+var_318]
0x1800107fc  mov     rcx, [rbp+320h+var_320]
0x180010800  test    rcx, rcx
0x180010803  cmovnz  eax, r14d
0x180010807  mov     [rbp+320h+var_318], eax
0x18001080a  mov     rax, [rcx]
0x18001080d  mov     r8d, [rdi+48h]
0x180010811  mov     rdx, [rdi+38h]
0x180010815  mov     rax, [rax+18h]
0x180010819  call    cs:__guard_dispatch_icall_fptr
0x18001081f  test    eax, eax
0x180010821  js      loc_18001185C
0x180010827  mov     [rbp+320h+var_330], r13
0x18001082b  mov     [rbp+320h+var_328], r13d
0x18001082f  mov     rcx, [rbp+320h+var_370]
0x180010833  lea     rax, [rbp+320h+var_330]
0x180010837  mov     [rsp+420h+var_3B0], rax
0x18001083c  mov     [rbp+320h+var_330], r13
0x180010840  or      ebx, 8
0x180010843  mov     [rsp+420h+var_3E0], ebx
0x180010847  mov     rax, [rcx]
0x18001084a  lea     r8, [rbp+320h+var_330]
0x18001084e  lea     rdx, IID_ICorSvcSetPrivateAttributes
0x180010855  mov     rax, [rax]
0x180010858  call    cs:__guard_dispatch_icall_fptr
0x18001085e  test    eax, eax
0x180010860  js      loc_180011864
0x180010866  and     ebx, 0FFFFFFF7h
0x180010869  mov     [rsp+420h+var_3E0], ebx
0x18001086d  mov     eax, [rbp+320h+var_328]
0x180010870  mov     rcx, [rbp+320h+var_330]
0x180010874  test    rcx, rcx
0x180010877  cmovnz  eax, r14d
0x18001087b  mov     [rbp+320h+var_328], eax
0x18001087e  movups  xmm0, xmmword ptr [rdi+80h]
0x180010885  movdqu  [rsp+420h+var_3D0], xmm0
0x18001088b  mov     rax, [rcx]
0x18001088e  lea     rdx, [rsp+420h+var_3D0]
0x180010893  mov     rax, [rax+18h]
0x180010897  call    cs:__guard_dispatch_icall_fptr
0x18001089d  test    eax, eax
0x18001089f  js      loc_18001186C
0x1800108a5  cmp     [rdi+50h], r13
0x1800108a9  jz      loc_18001094F
0x1800108af  mov     rcx, [rsp+420h+var_3A8]
0x1800108b4  test    rcx, rcx
0x1800108b7  jnz     short loc_180010936
0x1800108b9  mov     r14, [rbp+320h+var_370]
0x1800108bd  lea     rax, [rsp+420h+var_3A8]
0x1800108c2  mov     [rsp+420h+var_3B0], rax
0x1800108c7  cmp     [rbp+320h+var_3A0], r13d
0x1800108cb  jz      short loc_1800108E8
0x1800108cd  mov     rcx, [rsp+420h+var_3A8]
0x1800108d2  test    rcx, rcx
0x1800108d5  jz      short loc_1800108E4
0x1800108d7  mov     rax, [rcx]
0x1800108da  mov     rax, [rax+10h]
0x1800108de  call    cs:__guard_dispatch_icall_fptr
0x1800108e4  mov     [rbp+320h+var_3A0], r13d
0x1800108e8  mov     [rsp+420h+var_3A8], r13
0x1800108ed  or      ebx, 10h
0x1800108f0  mov     [rsp+420h+var_3E0], ebx
0x1800108f4  mov     rax, [r14]
0x1800108f7  lea     r8, [rsp+420h+var_3A8]
0x1800108fc  lea     rdx, IID_ICorSvcManager2
0x180010903  mov     rcx, r14
0x180010906  mov     rax, [rax]
0x180010909  call    cs:__guard_dispatch_icall_fptr
0x18001090f  test    eax, eax
0x180010911  js      loc_180011874
0x180010917  and     ebx, 0FFFFFFEFh
0x18001091a  mov     [rsp+420h+var_3E0], ebx
0x18001091e  mov     eax, [rbp+320h+var_3A0]
0x180010921  mov     rcx, [rsp+420h+var_3A8]
0x180010926  test    rcx, rcx
0x180010929  mov     r14d, 1
0x18001092f  cmovnz  eax, r14d
0x180010933  mov     [rbp+320h+var_3A0], eax
0x180010936  mov     rax, [rcx]
0x180010939  mov     rdx, [rdi+50h]
0x18001093d  mov     rax, [rax+18h]
0x180010941  call    cs:__guard_dispatch_icall_fptr
0x180010947  test    eax, eax
0x180010949  js      loc_18001187C
0x18001094f  cmp     [rdi+60h], r13
0x180010953  jz      loc_1800109F9
0x180010959  mov     rcx, [rsp+420h+var_3A8]
0x18001095e  test    rcx, rcx
0x180010961  jnz     short loc_1800109E0
0x180010963  mov     r14, [rbp+320h+var_370]
0x180010967  lea     rax, [rsp+420h+var_3A8]
0x18001096c  mov     [rsp+420h+var_3B0], rax
0x180010971  cmp     [rbp+320h+var_3A0], r13d
0x180010975  jz      short loc_180010992
0x180010977  mov     rcx, [rsp+420h+var_3A8]
0x18001097c  test    rcx, rcx
0x18001097f  jz      short loc_18001098E
0x180010981  mov     rax, [rcx]
0x180010984  mov     rax, [rax+10h]
0x180010988  call    cs:__guard_dispatch_icall_fptr
0x18001098e  mov     [rbp+320h+var_3A0], r13d
0x180010992  mov     [rsp+420h+var_3A8], r13
0x180010997  or      ebx, 20h
0x18001099a  mov     [rsp+420h+var_3E0], ebx
0x18001099e  mov     rax, [r14]
0x1800109a1  lea     r8, [rsp+420h+var_3A8]
0x1800109a6  lea     rdx, IID_ICorSvcManager2
0x1800109ad  mov     rcx, r14
0x1800109b0  mov     rax, [rax]
0x1800109b3  call    cs:__guard_dispatch_icall_fptr
0x1800109b9  test    eax, eax
0x1800109bb  js      loc_180011884
0x1800109c1  and     ebx, 0FFFFFFDFh
0x1800109c4  mov     [rsp+420h+var_3E0], ebx
0x1800109c8  mov     eax, [rbp+320h+var_3A0]
0x1800109cb  mov     rcx, [rsp+420h+var_3A8]
0x1800109d0  test    rcx, rcx
0x1800109d3  mov     r14d, 1
0x1800109d9  cmovnz  eax, r14d
0x1800109dd  mov     [rbp+320h+var_3A0], eax
  ... truncated ...
```
