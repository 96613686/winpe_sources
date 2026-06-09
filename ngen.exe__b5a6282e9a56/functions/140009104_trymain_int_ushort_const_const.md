# trymain(int,ushort const * * const)

- ea: `0x140009104`
- end: `0x140009a78`
- name: `?trymain@@YAHHQEAPEBG@Z`
- size: `2420`
- prototype: `__int64 __fastcall(int, const unsigned __int16 **const)`
- caller_count: `1`
- callee_count: `23`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x140009c08`

## callees

- `0x1400012c0`
- `0x140001574`
- `0x140006188`
- `0x140006a38`
- `0x140006e3c`
- `0x140006e90`
- `0x140006fb8`
- `0x140007388`
- `0x14000750c`
- `0x14000793c`
- `0x140007bac`
- `0x1400081f8`
- `0x140008548`
- `0x140008ed0`
- `0x140009104`
- `0x14000a3bc`
- `0x14000aa04`
- `0x14000ad80`
- `0x14000b010`
- `0x14000e4f4`
- `0x140013200`
- `0x140013f10`
- `0x140013f30`

## import_xrefs

- `KERNEL32!HeapSetInformation` at `0x14000914f`
- `KERNEL32!HeapSetInformation` at `0x14000914f`
- `KERNEL32!SetErrorMode` at `0x1400093c9`
- `KERNEL32!SetErrorMode` at `0x1400093c9`
- `KERNEL32!HeapFree` at `0x14000929b`
- `KERNEL32!HeapFree` at `0x1400092cc`
- `KERNEL32!HeapFree` at `0x140009342`
- `KERNEL32!HeapFree` at `0x140009373`
- `KERNEL32!HeapFree` at `0x140009691`
- `KERNEL32!HeapFree` at `0x1400096c2`
- `KERNEL32!HeapFree` at `0x14000929b`
- `KERNEL32!HeapFree` at `0x1400092cc`
- `KERNEL32!HeapFree` at `0x140009342`
- `KERNEL32!HeapFree` at `0x140009373`
- `KERNEL32!HeapFree` at `0x140009691`
- `KERNEL32!HeapFree` at `0x1400096c2`
- `KERNEL32!GetProcessHeap` at `0x140009286`
- `KERNEL32!GetProcessHeap` at `0x1400092b7`
- `KERNEL32!GetProcessHeap` at `0x14000932d`
- `KERNEL32!GetProcessHeap` at `0x14000935e`
- `KERNEL32!GetProcessHeap` at `0x14000967c`
- `KERNEL32!GetProcessHeap` at `0x1400096ad`
- `KERNEL32!GetProcessHeap` at `0x140009286`
- `KERNEL32!GetProcessHeap` at `0x1400092b7`
- `KERNEL32!GetProcessHeap` at `0x14000932d`
- `KERNEL32!GetProcessHeap` at `0x14000935e`
- `KERNEL32!GetProcessHeap` at `0x14000967c`
- `KERNEL32!GetProcessHeap` at `0x1400096ad`
- `ucrtbase_clr0400!wcscpy_s` at `0x140009592`
- `ucrtbase_clr0400!wcscpy_s` at `0x140009592`
- `ucrtbase_clr0400!_wcsicmp` at `0x14000946a`
- `ucrtbase_clr0400!_wcsicmp` at `0x14000946a`
- `ucrtbase_clr0400!exit` at `0x14000954d`
- `ucrtbase_clr0400!exit` at `0x140009750`
- `ucrtbase_clr0400!exit` at `0x1400097d2`
- `ucrtbase_clr0400!exit` at `0x140009808`
- `ucrtbase_clr0400!exit` at `0x1400098dc`
- `ucrtbase_clr0400!exit` at `0x140009a60`
- `ucrtbase_clr0400!exit` at `0x140009a69`
- `ucrtbase_clr0400!exit` at `0x14000954d`
- `ucrtbase_clr0400!exit` at `0x140009750`
- `ucrtbase_clr0400!exit` at `0x1400097d2`
- `ucrtbase_clr0400!exit` at `0x140009808`
- `ucrtbase_clr0400!exit` at `0x1400098dc`
- `ucrtbase_clr0400!exit` at `0x140009a60`
- `ucrtbase_clr0400!exit` at `0x140009a69`
- `mscoree!CLRCreateInstance` at `0x140009403`
- `mscoree!CLRCreateInstance` at `0x140009716`
- `mscoree!CLRCreateInstance` at `0x140009403`
- `mscoree!CLRCreateInstance` at `0x140009716`
- `mscoree!CorBindToRuntime` at `0x14000989f`
- `mscoree!CorBindToRuntime` at `0x14000989f`
- `mscoree!GetRealProcAddress` at `0x140009911`
- `mscoree!GetRealProcAddress` at `0x140009928`
- `mscoree!GetRealProcAddress` at `0x140009939`
- `mscoree!GetRealProcAddress` at `0x14000994a`
- `mscoree!GetRealProcAddress` at `0x140009964`
- `mscoree!GetRealProcAddress` at `0x14000997b`
- `mscoree!GetRealProcAddress` at `0x14000998c`
- `mscoree!GetRealProcAddress` at `0x14000999d`
- `mscoree!GetRealProcAddress` at `0x140009911`
- `mscoree!GetRealProcAddress` at `0x140009928`
- `mscoree!GetRealProcAddress` at `0x140009939`
- `mscoree!GetRealProcAddress` at `0x14000994a`
- `mscoree!GetRealProcAddress` at `0x140009964`
- `mscoree!GetRealProcAddress` at `0x14000997b`
- `mscoree!GetRealProcAddress` at `0x14000998c`
- `mscoree!GetRealProcAddress` at `0x14000999d`

## string_xrefs

- `0x140009a40`: `\nUsage: ngen <action> [args] [/nologo] [/silent] [/verbose]\n       ngen /? or /help\n\n    /nologo    - Prevents displaying of logo\n    /silent    - Prevents displaying of success messages\n    /verbose   - Displays verbose output for debugging\n\nActions:\n    ngen install <assembly name> [scenarios] [config] [/queue[:[1|2|3]]\n        Generate native images for an assembly and its dependencies\n        and install them in the Native Images Cache\n        If /queue is specified compilation j`
- `0x140009a4c`: `\nScenarios:\n    /Debug          - Generate images that can be used under a debugger\n    /Profile        - Generate images that can be used under a profiler\n    /NoDependencies - Generate the minimal number of native images\n                      required by this scenario\n\nConfig:\n    /ExeConfig:<path to exe> - Use the configuration of the specified\n                 executable assembly\n    /AppBase:<path to appbase directory> - Use the specified directory as\n                 the appbase`
- `0x140009560`: `configuration context of the first EXE for all other inputs.\n`
- `0x1400091aa`: `Command line: `
- `0x1400093b2`: `WARNING: This syntax is deprecated or you mis-typed your command.  Run "ngen /?" to display a list of the currently supported parameters.\n`
- `0x140009742`: `Unable to load v1.1.4322 mscorjit.dll.\n`
- `0x1400097c4`: `Unable to load v1.1.4322 mscorjit.dll.\n`
- `0x1400097fa`: `Unable to load v1.1.4322 mscorjit.dll.\n`
- `0x1400097e0`: `mscorjit.dll`
- `0x14000990a`: `LegacyNGenCreateZapper`
- `0x14000995d`: `LegacyNGenCreateZapper`
- `0x140009921`: `LegacyNGenTryEnumerateFusionCache`
- `0x140009974`: `LegacyNGenTryEnumerateFusionCache`
- `0x140009932`: `LegacyNGenCompile`
- `0x140009985`: `LegacyNGenCompile`
- `0x140009a05`: `Unable to launch CLR Version %s to compile this assembly.\n`

## pseudocode

```c
__int64 __fastcall trymain(int a1, const unsigned __int16 **const a2)
{
  __int64 v3; // r13
  __int64 v4; // rsi
  MachineWideLogger *v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // r9
  __int64 i; // rbx
  void *v9; // rbx
  HANDLE ProcessHeap; // rax
  void *v11; // rbx
  HANDLE v12; // rax
  void *v14; // rbx
  HANDLE v15; // rax
  void *v16; // rbx
  HANDLE v17; // rax
  int CommandLine; // ebx
  const unsigned __int16 *v19; // r14
  int v20; // eax
  int v21; // eax
  unsigned int v22; // r15d
  unsigned int v23; // edi
  __int64 v24; // rcx
  __int64 v25; // rax
  void *v26; // rbx
  HANDLE v27; // rax
  void *v28; // rbx
  HANDLE v29; // rax
  int v30; // esi
  int v31; // ecx
  int v32; // esi
  int v33; // ecx
  int v34; // esi
  int v35; // esi
  int v36; // ecx
  int RealProcAddress; // ebx
  __int64 (__fastcall *v38)(__int64 *, int *); // r8
  unsigned int v39; // [rsp+64h] [rbp-9Ch] BYREF
  __int64 v40; // [rsp+68h] [rbp-98h] BYREF
  int v41; // [rsp+70h] [rbp-90h]
  bool v42; // [rsp+78h] [rbp-88h] BYREF
  __int64 v43; // [rsp+80h] [rbp-80h] BYREF
  int v44; // [rsp+88h] [rbp-78h]
  int v45; // [rsp+90h] [rbp-70h] BYREF
  __int64 v46; // [rsp+98h] [rbp-68h] BYREF
  int v47; // [rsp+A0h] [rbp-60h]
  LPVOID v48; // [rsp+A8h] [rbp-58h] BYREF
  unsigned __int64 v49; // [rsp+B0h] [rbp-50h]
  __int64 v50; // [rsp+B8h] [rbp-48h]
  __int64 v51; // [rsp+C0h] [rbp-40h]
  __int16 v52; // [rsp+C8h] [rbp-38h]
  int v53; // [rsp+CCh] [rbp-34h]
  char v54; // [rsp+D0h] [rbp-30h]
  struct NGenOptionsParser *v55; // [rsp+D8h] [rbp-28h] BYREF
  int v56; // [rsp+E0h] [rbp-20h]
  int (*v57)(void *, const unsigned __int16 *, bool, bool); // [rsp+E8h] [rbp-18h] BYREF
  int (*v58)(void *, const unsigned __int16 *); // [rsp+F0h] [rbp-10h] BYREF
  int (*v59)(void *); // [rsp+F8h] [rbp-8h] BYREF
  __int64 *v60; // [rsp+100h] [rbp+0h]
  __int64 *v61; // [rsp+108h] [rbp+8h] BYREF
  int v62; // [rsp+110h] [rbp+10h] BYREF
  __int64 v63; // [rsp+114h] [rbp+14h]
  LPVOID lpMem; // [rsp+120h] [rbp+20h]
  __int16 v65; // [rsp+128h] [rbp+28h] BYREF
  wchar_t Destination[32]; // [rsp+330h] [rbp+230h] BYREF
  wchar_t Source[64]; // [rsp+370h] [rbp+270h] BYREF

  v3 = a1;
  v4 = 0;
  HeapSetInformation(0, HeapEnableTerminationOnCorruption, 0, 0);
  SString::Startup();
  MachineWideLogger::Init(v5, v3, a2);
  v48 = 0;
  v49 = 0;
  v50 = 0;
  v51 = 256;
  v52 = 0;
  v53 = 0;
  v54 = 0;
  v63 = 512;
  lpMem = &v65;
  v62 = 2;
  v65 = 0;
  SString::Set((wchar_t **)&v62, L"Command line: ");
  if ( (int)v3 > 0 )
  {
    for ( i = 0; i < v3; ++i )
    {
      SString::Append((SString *)&v62, (unsigned __int16 *)a2[i]);
      SString::Append((SString *)&v62, L" ");
    }
  }
  dword_1400270F0 = CLRConfig::GetConfigValue(
                      (const struct CLRConfig::ConfigDWORDInfo *)&CLRConfig::EXTERNAL_NGenLogVerbosity,
                      v6,
                      &v42,
                      v7);
  SString::Append((SString *)&v62, L"\n");
  if ( byte_1400270D0 )
  {
    SString::ConvertToUnicode((SString *)&v62);
    MachineWideLogger::LogF((MachineWideLogger *)&g_MachineWideLogger, L"%s", lpMem);
  }
  if ( (unsigned int)IsInvalidOfflineNgenEnvironment() )
  {
    Output(L"To use the Offline Ngen feature, you must set all the environment variables outlined in the documentation.\n");
    MachineWideLogger::LogF(
      (MachineWideLogger *)&g_MachineWideLogger,
      L"%s",
      L"To use the Offline Ngen feature, you must set all the environment variables outlined in the documentation.\n");
    if ( (v63 & 0x800000000LL) != 0 )
    {
      v9 = lpMem;
      if ( lpMem )
      {
        ProcessHeap = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
        if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
        {
          ProcessHeap = GetProcessHeap();
          `ClrFreeInProcessHeap'::`2'::ProcessHeap = ProcessHeap;
        }
        HeapFree(ProcessHeap, 0, v9);
      }
    }
    v11 = v48;
    if ( v48 )
    {
      v12 = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
      if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
      {
        v12 = GetProcessHeap();
        `ClrFreeInProcessHeap'::`2'::ProcessHeap = v12;
      }
      HeapFree(v12, 0, v11);
    }
    return -1;
  }
  else if ( IsNewCommandLine(v3 - 1, a2 + 1) )
  {
    if ( (v63 & 0x800000000LL) != 0 )
    {
      v14 = lpMem;
      if ( lpMem )
      {
        v15 = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
        if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
        {
          v15 = GetProcessHeap();
          `ClrFreeInProcessHeap'::`2'::ProcessHeap = v15;
        }
        HeapFree(v15, 0, v14);
      }
    }
    v16 = v48;
    if ( v48 )
    {
      v17 = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
      if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
      {
        v17 = GetProcessHeap();
        `ClrFreeInProcessHeap'::`2'::ProcessHeap = v17;
      }
      HeapFree(v17, 0, v16);
    }
    return 0;
  }
  else
  {
    CommandLine = NGenOptionsParser::ReadCommandLine((NGenOptionsParser *)&v48, (int)v3 - 1, a2 + 1);
    if ( BYTE1(v51) && !BYTE6(v51) )
    {
      PrintLogoHelper();
      BYTE1(v51) = 0;
    }
    if ( CommandLine == 1
      || (Output(
            "WARNING: This syntax is deprecated or you mis-typed your command.  Run \"ngen /?\" to display a list of the "
            "currently supported parameters.\n"),
          CommandLine) )
    {
      Output(
        "\n"
        "Usage: ngen <action> [args] [/nologo] [/silent] [/verbose]\n"
        "       ngen /? or /help\n"
        "\n"
        "    /nologo    - Prevents displaying of logo\n"
        "    /silent    - Prevents displaying of success messages\n"
        "    /verbose   - Displays verbose output for debugging\n"
        "\n"
        "Actions:\n"
        "    ngen install <assembly name> [scenarios] [config] [/queue[:[1|2|3]]\n"
        "        Generate native images for an assembly and its dependencies\n"
        "        and install them in the Native Images Cache\n"
        "        If /queue is specified compilation job is queued up.  If a priority \n"
        "        is not specified, the default priority used is 3.\n"
        "    ngen uninstall <assembly name> [scenarios] [config]\n"
        "        Delete the native images of an assembly and its dependencies from\n"
        "        the Native Images Cache.\n"
        "    ngen update [/queue]\n"
        "        Update native images that have become invalid\n"
        "        If /queue is specified compilation jobs are queued up.\n"
        "    ngen display [assembly name]\n"
        "        Display the ngen state\n"
        "    ngen executeQueuedItems [1|2|3]\n"
        "        Executes queued compilation jobs.\n"
        "        If priority is not specified all queued compilation jobs are done.\n"
        "        If priority is specified compilation jobs with greater or equal\n"
        "        priority than the specified are done. (Short form: eqi)\n"
        "    ngen queue [pause|continue|status]\n"
        "        Allows the user to pause and continue the NGen Service, and to\n"
        "        query its status.\n"
        "    ngen createPDB <path to native image> <directory to store PDB>\n"
        "                    [/lines  [<search path for managed PDB>] ]\n"
        "        Generates a native PDB file for a native image that was previously\n"
        "        generated by NGen.  The generated PDB file includes names of methods\n"
        "        and ranges of IP offsets that map to those methods.\n"
        "        If /lines is specified, then additional information is written to the\n"
        "        PDB to map ranges of IP offsets to source file line numbers.  /lines\n"
        "        requires access to the managed PDB generated by the language compiler.\n"
        "        <search path for managed PDB> may optionally be specified to help NGen\n"
        "        find the managed PDB\n");
      Output(
        "\n"
        "Scenarios:\n"
        "    /Debug          - Generate images that can be used under a debugger\n"
        "    /Profile        - Generate images that can be used under a profiler\n"
        "    /NoDependencies - Generate the minimal number of native images\n"
        "                      required by this scenario\n"
        "\n"
        "Config:\n"
        "    /ExeConfig:<path to exe> - Use the configuration of the specified\n"
        "                 executable assembly\n"
        "    /AppBase:<path to appbase directory> - Use the specified directory as\n"
        "                 the appbase\n"
        "\n"
        "\n");
      if ( CommandLine < 0 )
        exit(-1);
      exit(0);
    }
    SetErrorMode(1u);
    v45 = 0;
    v39 = 0;
    v19 = 0;
    v44 = 0;
    v60 = &v43;
    v43 = 0;
    v20 = CLRCreateInstance(&CLSID_CLRMetaHostPolicy, &IID_ICLRMetaHostPolicy, &v43);
    if ( v20 < 0 )
      ThrowHR(v20);
    v21 = v44;
    if ( v43 )
      v21 = 1;
    v44 = v21;
    v22 = 0;
    v23 = -1;
    if ( v49 )
    {
      do
      {
        v24 = *((_QWORD *)v48 + v4);
        v25 = -1;
        do
          ++v25;
        while ( *(_WORD *)(v24 + 2 * v25) );
        if ( (int)v25 > 4 && !_wcsicmp((const wchar_t *)(v24 + 2LL * (int)v25 - 8), L".exe") )
        {
          if ( v19 )
          {
            Output("\nWARNING: Do not specify multiple EXEs as input. NGen uses the\n");
            Output("configuration context of the first EXE for all other inputs.\n");
            Output("Instead, run NGen separately for individual EXEs.\n\n");
            goto LABEL_47;
          }
          v45 = 64;
          Source[0] = 0;
          if ( (*(int (__fastcall **)(__int64, __int64, _QWORD, _QWORD, wchar_t *, int *, _QWORD, _QWORD, _QWORD, GUID *, _QWORD))(*(_QWORD *)v43 + 24LL))(
                 v43,
                 8,
                 *((_QWORD *)v48 + v4),
                 0,
                 Source,
                 &v45,
                 0,
                 0,
                 0,
                 &GUID_NULL,
                 0) >= 0 )
            v19 = (const unsigned __int16 *)*((_QWORD *)v48 + v4);
        }
        v4 = ++v22;
      }
      while ( v22 < v49 );
      if ( v19 )
        goto LABEL_47;
    }
    StringCchPrintfW(Source, 64, L"v%d.%d.%d");
LABEL_47:
    if ( HIBYTE(v51) )
    {
      Outputf(L"Version %s of the runtime would be used to generate this image.\n", Source);
      exit(0);
    }
    v56 = 32;
    wcscpy_s(Destination, 0x20u, Source);
    if ( (*(int (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v43 + 24LL))(v43, 8, 0) < 0
      || !wcscmp_0(Destination, L"v1.0.3705")
      || !wcscmp_0(Destination, L"v1.1.4322")
      || !(unsigned int)DoNGen_New((struct NGenOptionsParser *)&v48, v19, &v39) )
    {
      if ( !wcscmp_0(Source, L"v1.1.4322") )
      {
        v47 = 0;
        v60 = &v46;
        v46 = 0;
        v30 = CLRCreateInstance(&CLSID_CLRMetaHost, &IID_ICLRMetaHost, &v46);
        v31 = v47;
        if ( v46 )
          v31 = 1;
        v47 = v31;
        if ( v30 < 0 )
        {
          Output(L"Unable to load v1.1.4322 mscorjit.dll.\n");
          exit(v30);
        }
        v41 = 0;
        v60 = &v40;
        v40 = 0;
        v32 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, GUID *, __int64 *))(*(_QWORD *)v46 + 24LL))(
                v46,
                L"v1.1.4322",
                &IID_ICLRRuntimeInfo,
                &v40);
        v33 = v41;
        if ( v40 )
          v33 = 1;
        v41 = v33;
        if ( v32 < 0 )
        {
          Output(L"Unable to load v1.1.4322 mscorjit.dll.\n");
          exit(v32);
        }
        v34 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 **))(*(_QWORD *)v40 + 56LL))(
                v40,
                L"mscorjit.dll",
                &v61);
        if ( v34 < 0 )
        {
          Output(L"Unable to load v1.1.4322 mscorjit.dll.\n");
          exit(v34);
        }
        if ( v41 )
        {
          if ( v40 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
          v41 = 0;
        }
        if ( v47 )
        {
          if ( v46 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
          v47 = 0;
        }
      }
      v55 = 0;
      v57 = 0;
      v58 = 0;
      v59 = 0;
      v41 = 0;
      v61 = &v40;
      v40 = 0;
      v35 = CorBindToRuntime(Destination, 0, &CLSID_CLRRuntimeHost, &IID_ICLRRuntimeHost, &v40);
      v36 = v41;
      if ( v40 )
        v36 = 1;
      v41 = v36;
      if ( v35 < 0 )
      {
        Output(L"Unable to bind to runtime for legacy NGEN scenario.\n");
        exit(v35);
      }
      if ( v41 )
      {
        if ( v40 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
        v41 = 0;
      }
      RealProcAddress = GetRealProcAddress("LegacyNGenCreateZapper", &v55);
      if ( RealProcAddress >= 0 )
      {
        GetRealProcAddress("LegacyNGenTryEnumerateFusionCache", &v57);
        GetRealProcAddress("LegacyNGenCompile", &v58);
        GetRealProcAddress("LegacyNGenFreeZapper", &v59);
      }
      v38 = (__int64 (__fastcall *)(__int64 *, int *))v55;
      if ( !v55 )
      {
        RealProcAddress = GetRealProcAddress("LegacyNGenCreateZapper", &v55);
        if ( RealProcAddress >= 0 )
        {
          GetRealProcAddress("LegacyNGenTryEnumerateFusionCache", &v57);
          GetRealProcAddress("LegacyNGenCompile", &v58);
          GetRealProcAddress("LegacyNGenFreeZapper", &v59);
        }
        v38 = (__int64 (__fastcall *)(__int64 *, int *))v55;
        if ( !v55 )
          goto LABEL_105;
      }
      if ( v57 && v58 && v59 )
      {
        v23 = DoNGen_Legacy((struct NGenOptionsParser *)&v48, v19, v38, v57, v58, v59);
        v39 = v23;
      }
      else
      {
LABEL_105:
        if ( RealProcAddress == -2146232575 )
          RealProcAddress = ProcessV1(v3, a2, (struct NGenOptionsParser *)v38);
        if ( RealProcAddress >= 0 )
        {
          v23 = v39;
        }
        else
        {
          Outputf(L"Unable to launch CLR Version %s to compile this assembly.\n", Source);
          v39 = -1;
        }
      }
      if ( v44 )
      {
        if ( v43 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
        v44 = 0;
      }
    }
    else
    {
      v23 = v39;
      if ( v44 )
      {
        if ( v43 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
        v44 = 0;
      }
    }
    if ( (v63 & 0x800000000LL) != 0 )
    {
      v26 = lpMem;
      if ( lpMem )
      {
        v27 = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
        if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
        {
          v27 = GetProcessHeap();
          `ClrFreeInProcessHeap'::`2'::ProcessHeap = v27;
        }
        HeapFree(v27, 0, v26);
      }
    }
    v28 = v48;
    if ( v48 )
    {
      v29 = `ClrFreeInProcessHeap'::`2'::ProcessHeap;
      if ( !`ClrFreeInProcessHeap'::`2'::ProcessHeap )
      {
        v29 = GetProcessHeap();
        `ClrFreeInProcessHeap'::`2'::ProcessHeap = v29;
      }
      HeapFree(v29, 0, v28);
    }
    return v23;
  }
}

```

## disassembly

```asm
0x140009104  mov     [rsp-8+arg_10], rbx
0x140009109  push    rbp
0x14000910a  push    rsi
0x14000910b  push    rdi
0x14000910c  push    r12
0x14000910e  push    r13
0x140009110  push    r14
0x140009112  push    r15
0x140009114  lea     rbp, [rsp-300h]
0x14000911c  sub     rsp, 400h
0x140009123  mov     rax, cs:__security_cookie
0x14000912a  xor     rax, rsp
0x14000912d  mov     [rbp+330h+var_40], rax
0x140009134  mov     r12, rdx
0x140009137  movsxd  r13, ecx
0x14000913a  xor     esi, esi
0x14000913c  mov     [rsp+430h+var_3D0], esi
0x140009140  xor     r9d, r9d; HeapInformationLength
0x140009143  xor     r8d, r8d; HeapInformation
0x140009146  lea     r15d, [rsi+1]
0x14000914a  mov     edx, r15d; HeapInformationClass
0x14000914d  xor     ecx, ecx; HeapHandle
0x14000914f  call    cs:__imp_HeapSetInformation
0x140009155  call    ?Startup@SString@@SAXXZ; SString::Startup(void)
0x14000915a  mov     r8, r12; unsigned __int16 **
0x14000915d  mov     edx, r13d; int
0x140009160  call    ?Init@MachineWideLogger@@QEAA_NHQEAPEBG@Z; MachineWideLogger::Init(int,ushort const * * const)
0x140009165  mov     [rbp+330h+var_388], rsi
0x140009169  mov     [rbp+330h+var_380], rsi
0x14000916d  mov     [rbp+330h+var_378], rsi
0x140009171  mov     [rbp+330h+var_370], 100h
0x140009179  mov     [rbp+330h+var_368], si
0x14000917d  mov     [rbp+330h+var_364], esi
0x140009180  mov     [rbp+330h+var_360], sil
0x140009184  mov     [rbp+330h+var_320], rsi
0x140009188  mov     [rbp+330h+var_320+4], 200h
0x140009190  mov     [rbp+330h+lpMem], rsi
0x140009194  lea     rax, [rbp+330h+var_308]
0x140009198  mov     [rbp+330h+lpMem], rax
0x14000919c  mov     dword ptr [rbp+330h+var_320], 2
0x1400091a3  mov     rax, [rbp+330h+lpMem]
0x1400091a7  mov     [rax], si
0x1400091aa  lea     rdx, aCommandLine; "Command line: "
0x1400091b1  lea     rcx, [rbp+330h+var_320]; this
0x1400091b5  call    ?Set@SString@@QEAAXPEBG@Z; SString::Set(ushort const *)
0x1400091ba  nop
0x1400091bb  test    r13d, r13d
0x1400091be  jle     short loc_1400091E7
0x1400091c0  mov     ebx, esi
0x1400091c2  mov     rdx, [r12+rbx*8]; unsigned __int16 *
0x1400091c6  lea     rcx, [rbp+330h+var_320]; this
0x1400091ca  call    ?Append@SString@@QEAAXPEBG@Z; SString::Append(ushort const *)
0x1400091cf  lea     rdx, Source; " "
0x1400091d6  lea     rcx, [rbp+330h+var_320]; this
0x1400091da  call    ?Append@SString@@QEAAXPEBG@Z; SString::Append(ushort const *)
0x1400091df  add     rbx, r15
0x1400091e2  cmp     rbx, r13
0x1400091e5  jl      short loc_1400091C2
0x1400091e7  lea     r8, [rsp+430h+var_3B8]; bool *
0x1400091ec  lea     rcx, ?EXTERNAL_NGenLogVerbosity@CLRConfig@@2UConfigDWORDInfo@1@B; struct CLRConfig::ConfigDWORDInfo *
0x1400091f3  call    ?GetConfigValue@CLRConfig@@SAKAEBUConfigDWORDInfo@1@_NPEA_N@Z; CLRConfig::GetConfigValue(CLRConfig::ConfigDWORDInfo const &,bool,bool *)
0x1400091f8  mov     cs:dword_1400270F0, eax
0x1400091fe  lea     rdx, asc_1400168B8; "\n"
0x140009205  lea     rcx, [rbp+330h+var_320]; this
0x140009209  call    ?Append@SString@@QEAAXPEBG@Z; SString::Append(ushort const *)
0x14000920e  cmp     cs:byte_1400270D0, sil
0x140009215  jz      short loc_140009237
0x140009217  lea     rcx, [rbp+330h+var_320]; this
0x14000921b  call    ?ConvertToUnicode@SString@@AEBAXXZ; SString::ConvertToUnicode(void)
0x140009220  mov     r8, [rbp+330h+lpMem]
0x140009224  lea     rdx, aS; "%s"
0x14000922b  lea     rcx, ?g_MachineWideLogger@@3VMachineWideLogger@@A; this
0x140009232  call    ?LogF@MachineWideLogger@@QEAAXPEBGZZ; MachineWideLogger::LogF(ushort const *,...)
0x140009237  call    ?IsInvalidOfflineNgenEnvironment@@YAHXZ; IsInvalidOfflineNgenEnvironment(void)
0x14000923c  test    eax, eax
0x14000923e  jz      loc_140009300
0x140009244  lea     rcx, aToUseTheOfflin; "To use the Offline Ngen feature, you mu"...
0x14000924b  call    ?Output@@YAXPEBG@Z; Output(ushort const *)
0x140009250  lea     r8, aToUseTheOfflin; "To use the Offline Ngen feature, you mu"...
0x140009257  lea     rdx, aS; "%s"
0x14000925e  lea     rcx, ?g_MachineWideLogger@@3VMachineWideLogger@@A; this
0x140009265  call    ?LogF@MachineWideLogger@@QEAAXPEBGZZ; MachineWideLogger::LogF(ushort const *,...)
0x14000926a  nop
0x14000926b  test    [rbp+330h+var_318], 8
0x14000926f  jz      short loc_1400092A2
0x140009271  mov     rbx, [rbp+330h+lpMem]
0x140009275  test    rbx, rbx
0x140009278  jz      short loc_1400092A2
0x14000927a  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x140009281  test    rax, rax
0x140009284  jnz     short loc_140009293
0x140009286  call    cs:__imp_GetProcessHeap
0x14000928c  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x140009293  mov     r8, rbx; lpMem
0x140009296  xor     edx, edx; dwFlags
0x140009298  mov     rcx, rax; hHeap
0x14000929b  call    cs:__imp_HeapFree
0x1400092a1  nop
0x1400092a2  mov     rbx, [rbp+330h+var_388]
0x1400092a6  test    rbx, rbx
0x1400092a9  jz      short loc_1400092D2
0x1400092ab  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x1400092b2  test    rax, rax
0x1400092b5  jnz     short loc_1400092C4
0x1400092b7  call    cs:__imp_GetProcessHeap
0x1400092bd  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x1400092c4  mov     r8, rbx; lpMem
0x1400092c7  xor     edx, edx; dwFlags
0x1400092c9  mov     rcx, rax; hHeap
0x1400092cc  call    cs:__imp_HeapFree
0x1400092d2  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400092d6  mov     rcx, [rbp+330h+var_40]
0x1400092dd  xor     rcx, rsp; StackCookie
0x1400092e0  call    __security_check_cookie
0x1400092e5  mov     rbx, [rsp+430h+arg_10]
0x1400092ed  add     rsp, 400h
0x1400092f4  pop     r15
0x1400092f6  pop     r14
0x1400092f8  pop     r13
0x1400092fa  pop     r12
0x1400092fc  pop     rdi
0x1400092fd  pop     rsi
0x1400092fe  pop     rbp
0x1400092ff  retn
0x140009300  lea     rdx, [r12+8]; unsigned __int16 **
0x140009305  lea     ecx, [r13-1]; int
0x140009309  call    ?IsNewCommandLine@@YA_NHQEAPEBG@Z; IsNewCommandLine(int,ushort const * * const)
0x14000930e  test    al, al
0x140009310  jz      short loc_140009380
0x140009312  test    [rbp+330h+var_318], 8
0x140009316  jz      short loc_140009349
0x140009318  mov     rbx, [rbp+330h+lpMem]
0x14000931c  test    rbx, rbx
0x14000931f  jz      short loc_140009349
0x140009321  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x140009328  test    rax, rax
0x14000932b  jnz     short loc_14000933A
0x14000932d  call    cs:__imp_GetProcessHeap
0x140009333  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x14000933a  mov     r8, rbx; lpMem
0x14000933d  xor     edx, edx; dwFlags
0x14000933f  mov     rcx, rax; hHeap
0x140009342  call    cs:__imp_HeapFree
0x140009348  nop
0x140009349  mov     rbx, [rbp+330h+var_388]
0x14000934d  test    rbx, rbx
0x140009350  jz      short loc_140009379
0x140009352  mov     rax, cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x140009359  test    rax, rax
0x14000935c  jnz     short loc_14000936B
0x14000935e  call    cs:__imp_GetProcessHeap
0x140009364  mov     cs:?ProcessHeap@?1??ClrFreeInProcessHeap@@YAHKPEAX@Z@4PEAXEA, rax; void * `ClrFreeInProcessHeap(ulong,void *)'::`2'::ProcessHeap
0x14000936b  mov     r8, rbx; lpMem
0x14000936e  xor     edx, edx; dwFlags
0x140009370  mov     rcx, rax; hHeap
0x140009373  call    cs:__imp_HeapFree
0x140009379  xor     eax, eax
0x14000937b  jmp     loc_1400092D6
0x140009380  lea     r8, [r12+8]; unsigned __int16 **
0x140009385  lea     edx, [r13-1]; int
0x140009389  lea     rcx, [rbp+330h+var_388]; this
0x14000938d  call    ?ReadCommandLine@NGenOptionsParser@@QEAAJHQEAPEBG@Z; NGenOptionsParser::ReadCommandLine(int,ushort const * * const)
0x140009392  mov     ebx, eax
0x140009394  cmp     byte ptr [rbp+330h+var_370+1], sil
0x140009398  jz      short loc_1400093A9
0x14000939a  cmp     byte ptr [rbp+330h+var_370+6], sil
0x14000939e  jnz     short loc_1400093A9
0x1400093a0  call    ?PrintLogoHelper@@YAXXZ; PrintLogoHelper(void)
0x1400093a5  mov     byte ptr [rbp+330h+var_370+1], sil
0x1400093a9  cmp     ebx, r15d
0x1400093ac  jz      loc_140009A40
0x1400093b2  lea     rcx, aWarningThisSyn; "WARNING: This syntax is deprecated or y"...
0x1400093b9  call    ?Output@@YAXPEBD@Z; Output(char const *)
0x1400093be  test    ebx, ebx
0x1400093c0  jnz     loc_140009A40
0x1400093c6  mov     ecx, r15d; uMode
0x1400093c9  call    cs:__imp_SetErrorMode
0x1400093cf  mov     [rbp+330h+var_3A0], esi
0x1400093d2  mov     [rsp+430h+var_3CC], esi
0x1400093d6  mov     r14, rsi
0x1400093d9  mov     [rbp+330h+var_3B0], rsi
0x1400093dd  mov     [rbp+330h+var_3A8], esi
0x1400093e0  lea     rax, [rbp+330h+var_3B0]
0x1400093e4  mov     [rbp+330h+var_330], rax
0x1400093e8  mov     [rbp+330h+var_3B0], rsi
0x1400093ec  mov     [rsp+430h+var_3D0], r15d
0x1400093f1  lea     r8, [rbp+330h+var_3B0]
0x1400093f5  lea     rdx, IID_ICLRMetaHostPolicy
0x1400093fc  lea     rcx, CLSID_CLRMetaHostPolicy
0x140009403  call    cs:__imp_CLRCreateInstance
0x140009409  test    eax, eax
0x14000940b  js      loc_140009A70
0x140009411  mov     ebx, r15d
0x140009414  and     ebx, 0FFFFFFFEh
0x140009417  mov     [rsp+430h+var_3D0], ebx
0x14000941b  mov     eax, [rbp+330h+var_3A8]
0x14000941e  cmp     [rbp+330h+var_3B0], rsi
0x140009422  cmovnz  eax, r15d
0x140009426  mov     [rbp+330h+var_3A8], eax
0x140009429  mov     r15d, esi
0x14000942c  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140009430  cmp     [rbp+330h+var_380], rsi
0x140009434  jbe     loc_140009508
0x14000943a  mov     rax, [rbp+330h+var_388]
0x14000943e  mov     rcx, [rax+rsi*8]
0x140009442  mov     rax, rdi
0x140009445  xor     edx, edx
0x140009447  inc     rax
0x14000944a  cmp     [rcx+rax*2], dx
0x14000944e  jnz     short loc_140009447
0x140009450  cmp     eax, 4
0x140009453  jle     loc_1400094EE
0x140009459  cdqe
0x14000945b  lea     rcx, [rcx+rax*2]
0x14000945f  add     rcx, 0FFFFFFFFFFFFFFF8h; String1
0x140009463  lea     rdx, aExe; ".exe"
0x14000946a  call    cs:__imp__wcsicmp
0x140009470  xor     edx, edx
0x140009472  test    eax, eax
0x140009474  jnz     short loc_1400094EE
0x140009476  test    r14, r14
0x140009479  jnz     loc_140009554
0x14000947f  mov     [rbp+330h+var_3A0], 40h ; '@'
0x140009486  mov     [rbp+330h+Source], dx
0x14000948d  mov     rcx, [rbp+330h+var_3B0]
0x140009491  mov     rax, [rcx]
0x140009494  mov     [rsp+430h+var_3E0], rdx
0x140009499  lea     r8, GUID_NULL
0x1400094a0  mov     [rsp+430h+var_3E8], r8
0x1400094a5  mov     [rsp+430h+var_3F0], rdx
0x1400094aa  mov     [rsp+430h+var_3F8], rdx
0x1400094af  mov     [rsp+430h+var_400], rdx
0x1400094b4  lea     rdx, [rbp+330h+var_3A0]
0x1400094b8  mov     [rsp+430h+var_408], rdx
0x1400094bd  lea     rdx, [rbp+330h+Source]
0x1400094c4  mov     [rsp+430h+var_410], rdx
0x1400094c9  xor     r9d, r9d
0x1400094cc  mov     r8, [rbp+330h+var_388]
0x1400094d0  mov     r8, [r8+rsi*8]
0x1400094d4  lea     edx, [r14+8]
0x1400094d8  mov     rax, [rax+18h]
0x1400094dc  call    cs:__guard_dispatch_icall_fptr
0x1400094e2  test    eax, eax
0x1400094e4  js      short loc_1400094EE
0x1400094e6  mov     rax, [rbp+330h+var_388]
0x1400094ea  mov     r14, [rax+rsi*8]
0x1400094ee  mov     rax, r14
0x1400094f1  inc     r15d
0x1400094f4  mov     esi, r15d
0x1400094f7  cmp     rsi, [rbp+330h+var_380]
0x1400094fb  jb      loc_14000943A
0x140009501  xor     esi, esi
0x140009503  test    rax, rax
0x140009506  jnz     short loc_140009532
0x140009508  mov     dword ptr [rsp+430h+var_408], 766Fh
0x140009510  mov     [rsp+430h+var_410], rsi
0x140009515  mov     r9d, 4
0x14000951b  lea     r8, aVDDD; "v%d.%d.%d"
0x140009522  lea     edx, [r9+3Ch]; unsigned __int64
0x140009526  lea     rcx, [rbp+330h+Source]; Buffer
0x14000952d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140009532  cmp     byte ptr [rbp+330h+var_370+7], sil
0x140009536  jz      short loc_14000957C
0x140009538  lea     rdx, [rbp+330h+Source]
0x14000953f  lea     rcx, aVersionSOfTheR; "Version %s of the runtime would be used"...
0x140009546  call    ?Outputf@@YAXPEAGZZ; Outputf(ushort *,...)
0x14000954b  xor     ecx, ecx; Code
0x14000954d  call    cs:__imp_exit
0x140009554  lea     rcx, aWarningDoNotSp; "\nWARNING: Do not specify multiple EXEs"...
0x14000955b  call    ?Output@@YAXPEBD@Z; Output(char const *)
0x140009560  lea     rcx, aConfigurationC; "configuration context of the first EXE "...
0x140009567  call    ?Output@@YAXPEBD@Z; Output(char const *)
0x14000956c  lea     rcx, aInsteadRunNgen; "Instead, run NGen separately for indivi"...
0x140009573  call    ?Output@@YAXPEBD@Z; Output(char const *)
0x140009578  xor     esi, esi
0x14000957a  jmp     short loc_140009532
0x14000957c  mov     edx, 20h ; ' '; SizeInWords
0x140009581  mov     [rbp+330h+var_350], edx
0x140009584  lea     r8, [rbp+330h+Source]; Source
0x14000958b  lea     rcx, [rbp+330h+Destination]; Destination
0x140009592  call    cs:__imp_wcscpy_s
0x140009598  mov     rcx, [rbp+330h+var_3B0]
0x14000959c  mov     rax, [rcx]
0x14000959f  mov     [rsp+430h+var_3E0], rsi
0x1400095a4  lea     rdx, GUID_NULL
0x1400095ab  mov     [rsp+430h+var_3E8], rdx
0x1400095b0  mov     [rsp+430h+var_3F0], rsi
0x1400095b5  mov     [rsp+430h+var_3F8], rsi
0x1400095ba  mov     [rsp+430h+var_400], rsi
0x1400095bf  lea     rdx, [rbp+330h+var_350]
0x1400095c3  mov     [rsp+430h+var_408], rdx
0x1400095c8  lea     rdx, [rbp+330h+Destination]
0x1400095cf  mov     [rsp+430h+var_410], rdx
0x1400095d4  xor     r9d, r9d
0x1400095d7  xor     r8d, r8d
0x1400095da  lea     edx, [r9+8]
0x1400095de  mov     rax, [rax+18h]
0x1400095e2  call    cs:__guard_dispatch_icall_fptr
0x1400095e8  test    eax, eax
0x1400095ea  js      loc_1400096CF
  ... truncated ...
```
