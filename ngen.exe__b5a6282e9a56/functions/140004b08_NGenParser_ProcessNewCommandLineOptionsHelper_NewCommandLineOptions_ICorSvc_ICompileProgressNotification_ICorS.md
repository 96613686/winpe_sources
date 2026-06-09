# NGenParser::ProcessNewCommandLineOptionsHelper(NewCommandLineOptions &,ICorSvc *,ICompileProgressNotification *,ICorSvcLogger *)

- ea: `0x140004b08`
- end: `0x1400060bc`
- name: `?ProcessNewCommandLineOptionsHelper@NGenParser@@AEAAXAEAUNewCommandLineOptions@@PEAUICorSvc@@PEAUICompileProgressNotification@@PEAUICorSvcLogger@@@Z`
- size: `5556`
- prototype: `void __fastcall(NGenParser *this, struct NewCommandLineOptions *, struct ICorSvc *, struct ICompileProgressNotification *, struct ICorSvcLogger *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1400081f8`

## callees

- `0x1400011d4`
- `0x140001fc8`
- `0x14000202c`
- `0x140004b08`
- `0x14000a10c`
- `0x14000a3bc`
- `0x14000ad80`
- `0x14000e4f4`
- `0x14000e5e4`
- `0x140010454`
- `0x140013200`
- `0x140013f30`

## string_xrefs

- `0x1400055c3`: `The .NET Runtime Optimization Service continue is pending.\n`
- `0x1400055ba`: `The .NET Runtime Optimization Service pause is pending.\n`
- `0x1400055b1`: `The .NET Runtime Optimization Service is started and paused.\n`
- `0x1400055cc`: `The .NET Runtime Optimization Service is running.\n`
- `0x1400055de`: `The .NET Runtime Optimization Service is starting.\n`
- `0x1400055d5`: `The .NET Runtime Optimization Service is stopping.\n`
- `0x1400055e7`: `The .NET Runtime Optimization Service is stopped.\n`
- `0x140005cc7`: `Error: /NoRoot can only be used with Install or Uninstall or CreatePDB commands.`
- `0x140005d7f`: `Error: Scenario, /ExeConfig or /AppBase not allowed with Uninstall /NoRoot command.`
- `0x140005ddf`: `Error: Install /Package requires /NoDependencies.`
- `0x140005dff`: `Error: /Version, /LocalAppData and /Package can only be used with Install or Uninstall or CreatePDB commands.`
- `0x140005d2f`: `Error: You must specify an assembly to install.`
- `0x14000606c`: `Error: You must specify an assembly to uninstall.`
- `0x140006016`: `Error: Cannot queue an uninstall action`
- `0x140005f62`: `Error: The specified assembly is not installed.`
- `0x140005ff0`: `Error: The specified assembly is not installed.`
- `0x140006046`: `Error: The specified assembly is not installed.`
- `0x140005fd0`: `Error: Cannot specify an assembly name to update`
- `0x140005ed2`: `Error: Cannot interact with the service when using the offline ngen feature`
- `0x140005555`: `Service name is: `
- `0x140005eb2`: `Error: insufficient number of arguments to createpdb`
- `0x1400052a8`: `Task boot trigger removed\n`
- `0x14000521b`: `Task delay start trigger removed\n`

## pseudocode

```c
void __fastcall NGenParser::ProcessNewCommandLineOptionsHelper(
        NGenParser *this,
        struct NewCommandLineOptions *a2,
        struct ICorSvc *a3,
        struct ICompileProgressNotification *a4,
        struct ICorSvcLogger *a5)
{
  int v8; // eax
  int v9; // eax
  int v10; // eax
  int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // r9
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

  if ( !(unsigned int)CLRConfig::GetConfigValue(
                        (const struct CLRConfig::ConfigDWORDInfo *)&CLRConfig::EXTERNAL_NGENUseService,
                        (__int64)a2,
                        &v130,
                        (__int64)a4) )
    *((_DWORD *)a2 + 36) = 0;
  v138 = 0;
  v123 = (__int64 *)&v137;
  v137 = 0;
  v8 = (*(__int64 (__fastcall **)(struct ICorSvc *, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)a3 + 24LL))(
         a3,
         &v137);
  if ( v8 < 0 )
    ThrowHR(v8);
  v9 = v138;
  if ( v137 )
    v9 = 1;
  v138 = v9;
  v132 = 0;
  v123 = (__int64 *)&v131;
  v131 = 0;
  v10 = (**v137)(v137, &IID_ICorSvcInstaller, (__int64 *)&v131);
  if ( v10 < 0 )
    ThrowHR(v10);
  v11 = v132;
  if ( v131 )
    v11 = 1;
  v132 = v11;
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
  if ( (unsigned int)CLRConfig::GetConfigValue(
                       (const struct CLRConfig::ConfigDWORDInfo *)&CLRConfig::EXTERNAL_ZapDisable,
                       v12,
                       &v130,
                       v13) )
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
      v99 = (const struct SString *)SString::SString(&v121, v14, L"Error: Cannot use /NoRoot with /Queue.");
      ThrowHR(-2147024736, v99);
    }
    if ( *(_DWORD *)a2 )
    {
      if ( *(_DWORD *)a2 == 1 )
      {
        if ( *((_DWORD *)a2 + 6) != 1 || *((_QWORD *)a2 + 5) )
        {
          v100 = (const struct SString *)SString::SString(
                                           &v121,
                                           v14,
                                           L"Error: Scenario, /ExeConfig or /AppBase not allowed with Uninstall /NoRoot command.");
          ThrowHR(-2147024736, v100);
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
        v87 = (*v131)[5](v131, (GUID *)cCompileProgressNotification, 0);
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
        v77 = (*v131)[5](v131, (GUID *)cCompileProgressNotification, (__int64 *)1);
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
      v58 = (*v131)[5](v131, (GUID *)cCompileProgressNotification, (__int64 *)3);
      if ( v58 < 0 )
        ThrowHR(v58);
      v59 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v128 + 40LL))(v128, *((unsigned int *)a2 + 42));
      if ( v59 < 0 )
        ThrowHR(v59);
      v60 = (*v131)[5](v131, (GUID *)cCompileProgressNotification, (__int64 *)1);
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
      v98 = (const struct SString *)SString::SString(&v121, v39, L"Error: You must specify an assembly to install.");
      ThrowHR(-2147024894, v98);
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
      v96 = (*v131)[5](v131, (GUID *)cCompileProgressNotification, 0);
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
0x140004b08  mov     [rsp-8+arg_18], rbx
0x140004b0d  push    rbp
0x140004b0e  push    rsi
0x140004b0f  push    rdi
0x140004b10  push    r12
0x140004b12  push    r13
0x140004b14  push    r14
0x140004b16  push    r15
0x140004b18  lea     rbp, [rsp-2E0h]
0x140004b20  sub     rsp, 3E0h
0x140004b27  mov     rax, cs:__security_cookie
0x140004b2e  xor     rax, rsp
0x140004b31  mov     [rbp+310h+var_40], rax
0x140004b38  mov     r15, r8
0x140004b3b  mov     rdi, rdx
0x140004b3e  mov     rsi, rcx
0x140004b41  mov     r14, [rbp+310h+arg_20]
0x140004b48  xor     r12d, r12d
0x140004b4b  mov     [rsp+410h+var_3D0], r12d
0x140004b50  lea     r8, [rbp+310h+var_368]; bool *
0x140004b54  lea     rcx, ?EXTERNAL_NGENUseService@CLRConfig@@2UConfigDWORDInfo@1@B; struct CLRConfig::ConfigDWORDInfo *
0x140004b5b  call    ?GetConfigValue@CLRConfig@@SAKAEBUConfigDWORDInfo@1@_NPEA_N@Z; CLRConfig::GetConfigValue(CLRConfig::ConfigDWORDInfo const &,bool,bool *)
0x140004b60  test    eax, eax
0x140004b62  jnz     short loc_140004B6B
0x140004b64  mov     [rdi+90h], r12d
0x140004b6b  mov     [rbp+310h+var_330], r12
0x140004b6f  mov     [rbp+310h+var_328], r12d
0x140004b73  lea     rax, [rbp+310h+var_330]
0x140004b77  mov     [rsp+410h+var_3A0], rax
0x140004b7c  mov     [rbp+310h+var_330], r12
0x140004b80  mov     r13d, 1
0x140004b86  mov     [rsp+410h+var_3D0], r13d
0x140004b8b  mov     rax, [r15]
0x140004b8e  lea     rdx, [rbp+310h+var_330]
0x140004b92  mov     rcx, r15
0x140004b95  mov     rax, [rax+18h]
0x140004b99  call    cs:__guard_dispatch_icall_fptr
0x140004b9f  test    eax, eax
0x140004ba1  js      loc_140005D4F
0x140004ba7  mov     ebx, r13d
0x140004baa  and     ebx, 0FFFFFFFEh
0x140004bad  mov     [rsp+410h+var_3D0], ebx
0x140004bb1  mov     eax, [rbp+310h+var_328]
0x140004bb4  cmp     [rbp+310h+var_330], r12
0x140004bb8  cmovnz  eax, r13d
0x140004bbc  mov     [rbp+310h+var_328], eax
0x140004bbf  mov     [rbp+310h+var_360], r12
0x140004bc3  mov     [rbp+310h+var_358], r12d
0x140004bc7  mov     rcx, [rbp+310h+var_330]
0x140004bcb  lea     rax, [rbp+310h+var_360]
0x140004bcf  mov     [rsp+410h+var_3A0], rax
0x140004bd4  mov     [rbp+310h+var_360], r12
0x140004bd8  or      ebx, 2
0x140004bdb  mov     [rsp+410h+var_3D0], ebx
0x140004bdf  mov     rax, [rcx]
0x140004be2  lea     r8, [rbp+310h+var_360]
0x140004be6  lea     rdx, IID_ICorSvcInstaller
0x140004bed  mov     rax, [rax]
0x140004bf0  call    cs:__guard_dispatch_icall_fptr
0x140004bf6  test    eax, eax
0x140004bf8  js      loc_140005D57
0x140004bfe  and     ebx, 0FFFFFFFDh
0x140004c01  mov     [rsp+410h+var_3D0], ebx
0x140004c05  mov     eax, [rbp+310h+var_358]
0x140004c08  mov     rcx, [rbp+310h+var_360]
0x140004c0c  test    rcx, rcx
0x140004c0f  cmovnz  eax, r13d
0x140004c13  mov     [rbp+310h+var_358], eax
0x140004c16  mov     rax, [rcx]
0x140004c19  mov     rdx, r14
0x140004c1c  mov     rax, [rax+30h]
0x140004c20  call    cs:__guard_dispatch_icall_fptr
0x140004c26  mov     [rbp+310h+var_350], r12
0x140004c2a  mov     [rbp+310h+var_348], r12d
0x140004c2e  mov     [rbp+310h+var_378], r12
0x140004c32  mov     [rbp+310h+var_370], r12d
0x140004c36  mov     [rbp+310h+var_340], r12
0x140004c3a  mov     [rbp+310h+var_338], r12d
0x140004c3e  mov     [rbp+310h+var_388], r12
0x140004c42  mov     [rbp+310h+var_380], r12d
0x140004c46  mov     [rsp+410h+var_398], r12
0x140004c4b  mov     [rbp+310h+var_390], r12d
0x140004c4f  cmp     [rdi+9Ch], r12d
0x140004c56  jnz     short loc_140004C71
0x140004c58  cmp     dword ptr [rdi+0A4h], 2
0x140004c5f  jl      short loc_140004C71
0x140004c61  mov     rcx, [rsi]
0x140004c64  mov     rax, [rcx]
0x140004c67  mov     rax, [rax+8]
0x140004c6b  call    cs:__guard_dispatch_icall_fptr
0x140004c71  lea     r8, [rbp+310h+var_368]; bool *
0x140004c75  lea     rcx, ?EXTERNAL_ZapDisable@CLRConfig@@2UConfigDWORDInfo@1@B; struct CLRConfig::ConfigDWORDInfo *
0x140004c7c  call    ?GetConfigValue@CLRConfig@@SAKAEBUConfigDWORDInfo@1@_NPEA_N@Z; CLRConfig::GetConfigValue(CLRConfig::ConfigDWORDInfo const &,bool,bool *)
0x140004c81  test    eax, eax
0x140004c83  jz      short loc_140004CE6
0x140004c85  cmp     dword ptr [rdi], 3
0x140004c88  jz      short loc_140004CE6
0x140004c8a  mov     dword ptr [rsp+410h+var_3C0], 2
0x140004c92  mov     dword ptr [rsp+410h+var_3C0+4], 2
0x140004c9a  mov     dword ptr [rsp+410h+var_3C0+8], 10h
0x140004ca2  lea     rax, ?s_EmptyBuffer@SString@@0QBEB; uchar const near * const SString::s_EmptyBuffer
0x140004ca9  mov     [rsp+410h+lpMem], rax
0x140004cae  lea     rdx, aWarningZapdisa; "Warning: ZapDisable is turned on.\n"
0x140004cb5  lea     rcx, [rsp+410h+var_3C0]; this
0x140004cba  call    ?Set@SString@@QEAAXPEBG@Z; SString::Set(ushort const *)
0x140004cbf  nop
0x140004cc0  mov     rcx, [rsi]
0x140004cc3  mov     rax, [rcx]
0x140004cc6  lea     rdx, [rsp+410h+var_3C0]
0x140004ccb  mov     rax, [rax]
0x140004cce  call    cs:__guard_dispatch_icall_fptr
0x140004cd4  nop
0x140004cd5  test    byte ptr [rsp+410h+var_3C0+8], 8
0x140004cda  jz      short loc_140004CE6
0x140004cdc  mov     rcx, [rsp+410h+lpMem]; lpMem
0x140004ce1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140004ce6  mov     edx, [rdi+20h]
0x140004ce9  and     edx, 4
0x140004cec  jz      short loc_140004D24
0x140004cee  cmp     [rdi+90h], r12d
0x140004cf5  jnz     loc_140005D5F
0x140004cfb  cmp     [rdi], r12d
0x140004cfe  jz      short loc_140004D24
0x140004d00  cmp     [rdi], r13d
0x140004d03  jz      short loc_140004D10
0x140004d05  cmp     dword ptr [rdi], 6
0x140004d08  jnz     loc_140005CC7
0x140004d0e  jmp     short loc_140004D24
0x140004d10  cmp     [rdi+18h], r13d
0x140004d14  jnz     loc_140005D7F
0x140004d1a  cmp     [rdi+28h], r12
0x140004d1e  jnz     loc_140005D7F
0x140004d24  mov     r9, [rdi+70h]
0x140004d28  mov     r8, [rdi+60h]
0x140004d2c  test    r8, r8
0x140004d2f  setz    cl
0x140004d32  test    r9, r9
0x140004d35  setz    al
0x140004d38  cmp     cl, al
0x140004d3a  jnz     loc_140005D9F
0x140004d40  test    r8, r8
0x140004d43  jz      short loc_140004D5C
0x140004d45  test    edx, edx
0x140004d47  jz      loc_140005DBF
0x140004d4d  cmp     [rdi], r12d
0x140004d50  jnz     short loc_140004D5C
0x140004d52  test    byte ptr [rdi+18h], 20h
0x140004d56  jz      loc_140005DDF
0x140004d5c  cmp     [rdi+50h], r12
0x140004d60  jnz     short loc_140004D6C
0x140004d62  test    r8, r8
0x140004d65  jnz     short loc_140004D6C
0x140004d67  test    r9, r9
0x140004d6a  jz      short loc_140004D7A
0x140004d6c  cmp     [rdi], r13d
0x140004d6f  jbe     short loc_140004D7A
0x140004d71  cmp     dword ptr [rdi], 6
0x140004d74  jnz     loc_140005DFF
0x140004d7a  mov     [rbp+310h+var_310], r12
0x140004d7e  mov     [rbp+310h+var_308], r12d
0x140004d82  mov     rcx, [rbp+310h+var_360]
0x140004d86  lea     rax, [rbp+310h+var_310]
0x140004d8a  mov     [rsp+410h+var_3A0], rax
0x140004d8f  mov     [rbp+310h+var_310], r12
0x140004d93  or      ebx, 4
0x140004d96  mov     [rsp+410h+var_3D0], ebx
0x140004d9a  mov     rax, [rcx]
0x140004d9d  lea     r8, [rbp+310h+var_310]
0x140004da1  lea     rdx, IID_ICorSvcRepository
0x140004da8  mov     rax, [rax]
0x140004dab  call    cs:__guard_dispatch_icall_fptr
0x140004db1  test    eax, eax
0x140004db3  js      loc_140005E1F
0x140004db9  and     ebx, 0FFFFFFFBh
0x140004dbc  mov     [rsp+410h+var_3D0], ebx
0x140004dc0  mov     eax, [rbp+310h+var_308]
0x140004dc3  mov     rcx, [rbp+310h+var_310]
0x140004dc7  test    rcx, rcx
0x140004dca  cmovnz  eax, r13d
0x140004dce  mov     [rbp+310h+var_308], eax
0x140004dd1  mov     rax, [rcx]
0x140004dd4  mov     r8d, [rdi+48h]
0x140004dd8  mov     rdx, [rdi+38h]
0x140004ddc  mov     rax, [rax+18h]
0x140004de0  call    cs:__guard_dispatch_icall_fptr
0x140004de6  test    eax, eax
0x140004de8  js      loc_140005E27
0x140004dee  mov     [rbp+310h+var_320], r12
0x140004df2  mov     [rbp+310h+var_318], r12d
0x140004df6  mov     rcx, [rbp+310h+var_360]
0x140004dfa  lea     rax, [rbp+310h+var_320]
0x140004dfe  mov     [rsp+410h+var_3A0], rax
0x140004e03  mov     [rbp+310h+var_320], r12
0x140004e07  or      ebx, 8
0x140004e0a  mov     [rsp+410h+var_3D0], ebx
0x140004e0e  mov     rax, [rcx]
0x140004e11  lea     r8, [rbp+310h+var_320]
0x140004e15  lea     rdx, IID_ICorSvcSetPrivateAttributes
0x140004e1c  mov     rax, [rax]
0x140004e1f  call    cs:__guard_dispatch_icall_fptr
0x140004e25  test    eax, eax
0x140004e27  js      loc_140005E2F
0x140004e2d  and     ebx, 0FFFFFFF7h
0x140004e30  mov     [rsp+410h+var_3D0], ebx
0x140004e34  mov     eax, [rbp+310h+var_318]
0x140004e37  mov     rcx, [rbp+310h+var_320]
0x140004e3b  test    rcx, rcx
0x140004e3e  cmovnz  eax, r13d
0x140004e42  mov     [rbp+310h+var_318], eax
0x140004e45  movups  xmm0, xmmword ptr [rdi+80h]
0x140004e4c  movdqu  [rsp+410h+var_3C0], xmm0
0x140004e52  mov     rax, [rcx]
0x140004e55  lea     rdx, [rsp+410h+var_3C0]
0x140004e5a  mov     rax, [rax+18h]
0x140004e5e  call    cs:__guard_dispatch_icall_fptr
0x140004e64  test    eax, eax
0x140004e66  js      loc_140005E37
0x140004e6c  cmp     [rdi+50h], r12
0x140004e70  jz      loc_140004F10
0x140004e76  mov     rcx, [rsp+410h+var_398]
0x140004e7b  test    rcx, rcx
0x140004e7e  jnz     short loc_140004EF7
0x140004e80  mov     r14, [rbp+310h+var_360]
0x140004e84  lea     rax, [rsp+410h+var_398]
0x140004e89  mov     [rsp+410h+var_3A0], rax
0x140004e8e  cmp     [rbp+310h+var_390], r12d
0x140004e92  jz      short loc_140004EAF
0x140004e94  mov     rcx, [rsp+410h+var_398]
0x140004e99  test    rcx, rcx
0x140004e9c  jz      short loc_140004EAB
0x140004e9e  mov     rax, [rcx]
0x140004ea1  mov     rax, [rax+10h]
0x140004ea5  call    cs:__guard_dispatch_icall_fptr
0x140004eab  mov     [rbp+310h+var_390], r12d
0x140004eaf  mov     [rsp+410h+var_398], r12
0x140004eb4  or      ebx, 10h
0x140004eb7  mov     [rsp+410h+var_3D0], ebx
0x140004ebb  mov     rax, [r14]
0x140004ebe  lea     r8, [rsp+410h+var_398]
0x140004ec3  lea     rdx, IID_ICorSvcManager2
0x140004eca  mov     rcx, r14
0x140004ecd  mov     rax, [rax]
0x140004ed0  call    cs:__guard_dispatch_icall_fptr
0x140004ed6  test    eax, eax
0x140004ed8  js      loc_140005E3F
0x140004ede  and     ebx, 0FFFFFFEFh
0x140004ee1  mov     [rsp+410h+var_3D0], ebx
0x140004ee5  mov     eax, [rbp+310h+var_390]
0x140004ee8  mov     rcx, [rsp+410h+var_398]
0x140004eed  test    rcx, rcx
0x140004ef0  cmovnz  eax, r13d
0x140004ef4  mov     [rbp+310h+var_390], eax
0x140004ef7  mov     rax, [rcx]
0x140004efa  mov     rdx, [rdi+50h]
0x140004efe  mov     rax, [rax+18h]
0x140004f02  call    cs:__guard_dispatch_icall_fptr
0x140004f08  test    eax, eax
0x140004f0a  js      loc_140005E47
0x140004f10  cmp     [rdi+60h], r12
0x140004f14  jz      loc_140004FB4
0x140004f1a  mov     rcx, [rsp+410h+var_398]
0x140004f1f  test    rcx, rcx
0x140004f22  jnz     short loc_140004F9B
0x140004f24  mov     r14, [rbp+310h+var_360]
0x140004f28  lea     rax, [rsp+410h+var_398]
0x140004f2d  mov     [rsp+410h+var_3A0], rax
0x140004f32  cmp     [rbp+310h+var_390], r12d
0x140004f36  jz      short loc_140004F53
0x140004f38  mov     rcx, [rsp+410h+var_398]
0x140004f3d  test    rcx, rcx
0x140004f40  jz      short loc_140004F4F
0x140004f42  mov     rax, [rcx]
0x140004f45  mov     rax, [rax+10h]
0x140004f49  call    cs:__guard_dispatch_icall_fptr
0x140004f4f  mov     [rbp+310h+var_390], r12d
0x140004f53  mov     [rsp+410h+var_398], r12
0x140004f58  or      ebx, 20h
0x140004f5b  mov     [rsp+410h+var_3D0], ebx
0x140004f5f  mov     rax, [r14]
0x140004f62  lea     r8, [rsp+410h+var_398]
0x140004f67  lea     rdx, IID_ICorSvcManager2
0x140004f6e  mov     rcx, r14
0x140004f71  mov     rax, [rax]
0x140004f74  call    cs:__guard_dispatch_icall_fptr
0x140004f7a  test    eax, eax
0x140004f7c  js      loc_140005E4F
0x140004f82  and     ebx, 0FFFFFFDFh
0x140004f85  mov     [rsp+410h+var_3D0], ebx
0x140004f89  mov     eax, [rbp+310h+var_390]
0x140004f8c  mov     rcx, [rsp+410h+var_398]
0x140004f91  test    rcx, rcx
0x140004f94  cmovnz  eax, r13d
0x140004f98  mov     [rbp+310h+var_390], eax
0x140004f9b  mov     rax, [rcx]
0x140004f9e  mov     rdx, [rdi+60h]
0x140004fa2  mov     rax, [rax+20h]
0x140004fa6  call    cs:__guard_dispatch_icall_fptr
0x140004fac  test    eax, eax
0x140004fae  js      loc_140005E57
0x140004fb4  cmp     [rdi+70h], r12
  ... truncated ...
```
