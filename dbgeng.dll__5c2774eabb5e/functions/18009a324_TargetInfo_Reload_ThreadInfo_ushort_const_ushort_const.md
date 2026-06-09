# TargetInfo::Reload(ThreadInfo *,ushort const *,ushort const * *)

- ea: `0x18009a324`
- end: `0x18009beab`
- name: `?Reload@TargetInfo@@QEAAJPEAVThreadInfo@@PEBGPEAPEBG@Z`
- size: `7047`
- prototype: `__int64 __fastcall(TargetInfo *__hidden this, struct ThreadInfo *, const unsigned __int16 *, const unsigned __int16 **)`
- caller_count: `16`
- callee_count: `46`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x18009a100`
- `0x1800b1c38`
- `0x1801e0210`
- `0x1801ecd90`
- `0x1801f4580`
- `0x1801f4d50`
- `0x1801f7360`
- `0x180216510`
- `0x18023efa0`
- `0x18023f4e0`
- `0x18023f850`
- `0x1802449c0`
- `0x1802bcae8`
- `0x1802c0110`
- `0x180341f4c`
- `0x18038af5c`

## callees

- `0x180071a60`
- `0x1800727b8`
- `0x180072c8c`
- `0x180075b88`
- `0x1800793cc`
- `0x1800797ec`
- `0x18007cf9c`
- `0x18007daa4`
- `0x18007e158`
- `0x18007e29c`
- `0x18007fb98`
- `0x18008567c`
- `0x180085700`
- `0x1800866c0`
- `0x180086724`
- `0x180086af0`
- `0x18008b1d0`
- `0x18008d550`
- `0x18008e130`
- `0x18008fba0`
- `0x180098468`
- `0x18009a324`
- `0x18009fb80`
- `0x1800a4dc4`
- `0x1800b94c4`
- `0x1800c0064`
- `0x1800c12b8`
- `0x1800c899c`
- `0x1800f0f40`
- `0x1800f2560`
- `0x1801643c4`
- `0x180186ab8`
- `0x1801d7e30`
- `0x1801efb60`
- `0x180240c2c`
- `0x1802413fc`
- `0x1802888a4`
- `0x180288924`
- `0x180288f3c`
- `0x18028904c`
- `0x180289118`
- `0x1802895b0`
- `0x1802aa8f0`
- `0x1802c0110`
- `0x1802c13c8`
- `0x1804f4010`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x18009ab8d`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x18009b423`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x18009ab8d`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x18009b423`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x18009a732`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x18009a793`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x18009a732`
- `api-ms-win-crt-string-l1-1-0!_wcsnicmp` at `0x18009a793`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18009b24f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18009b26b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18009b24f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18009b26b`
- `dbghelp!ReportSymbolLoadSummary` at `0x18009be52`
- `dbghelp!ReportSymbolLoadSummary` at `0x18009be52`
- `dbghelp!RemoveInvalidModuleList` at `0x18009b239`
- `dbghelp!RemoveInvalidModuleList` at `0x18009b239`
- `dbghelp!SetCheckUserInterruptShared` at `0x18009b226`
- `dbghelp!SetCheckUserInterruptShared` at `0x18009b226`

## string_xrefs

- `0x18009a863`: `           /o  Overwrite symbol server cache files\n`
- `0x18009a8c3`: `\nUse ".hh .reload" or open debugger.chm in the debuggers directory to get\ndetailed documentation on this command.\n\n`
- `0x18009ac08`: `* Symbols can not be loaded because symbol path is not initialized. *\n`
- `0x18009ac20`: `* The Symbol Path can be set by:                                    *\n`
- `0x18009ac38`: `*   using the -y <symbol_path> argument when starting the debugger. *\n`
- `0x18009ac2c`: `*   using the _NT_SYMBOL_PATH environment variable.                 *\n`
- `0x18009ac44`: `*   using .sympath and .sympath+                                    *\n`
- `0x18009b3b9`: `Unable to read image header at %s\n`
- `0x18009b846`: `AddImage: %s\n DllBase  = %s\n Size     = %08x\n Checksum = %08x\n TimeDateStamp = %08x\n`
- `0x18009bca2`: `Debugger will attempt to load "%s" at given base %s.\n\n`
- `0x18009bcae`: `Please provide the full image name, including the extension (i.e. kernel32.dll)\nfor more reliable results.Base address and size overrides can be given as\n.reload <image.ext>=<base>,<size>.\n`
- `0x18009be73`: `WARNING: .reload failed, module list may be incomplete\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall TargetInfo::Reload(TargetInfo *this, struct ThreadInfo *a2, wchar_t *a3, wchar_t **a4)
{
  wchar_t *v5; // rbx
  unsigned int v8; // r9d
  int *v9; // rdi
  wchar_t *v10; // rdx
  int *v11; // r11
  int v12; // ecx
  __int64 v13; // r8
  __int64 v14; // rax
  unsigned int v16; // r10d
  char v17; // r15
  char v18; // r12
  char v19; // r13
  int v20; // r8d
  bool v21; // zf
  wchar_t v22; // ax
  unsigned int v23; // ebx
  unsigned __int16 *v24; // rax
  __int64 v25; // rdx
  __int64 v26; // r8
  int v27; // esi
  wchar_t *v28; // rcx
  wchar_t *v29; // rbx
  int v30; // r8d
  struct EvalExpression *v31; // rbx
  int v32; // eax
  wchar_t v33; // ax
  __int64 v34; // rax
  __int64 v35; // rax
  unsigned __int64 v36; // rax
  wchar_t *v37; // rax
  wchar_t *v38; // rax
  wchar_t *v39; // rdx
  ProcessInfo *v40; // rbx
  wchar_t *v41; // rcx
  const unsigned __int16 *v42; // rax
  wchar_t *v43; // rcx
  unsigned __int16 *v44; // rcx
  unsigned __int64 v45; // r12
  int v46; // ecx
  int v47; // eax
  struct MachineInfo *v48; // rcx
  unsigned __int16 *v49; // rax
  unsigned int v50; // edx
  ProcessInfo *v51; // rdi
  wchar_t *v52; // rdx
  struct UnloadedImageInfo *UnloadedImageByName; // rbx
  wchar_t *v54; // rdx
  unsigned int v55; // edx
  struct MachineInfo *v56; // rax
  unsigned __int16 *v57; // rax
  bool v58; // r12
  ProcessInfo *v59; // rdi
  unsigned int v60; // esi
  int v61; // ecx
  const wchar_t *v62; // rdx
  const unsigned __int16 *v63; // rcx
  const wchar_t *v64; // rdx
  struct ThreadInfo *v65; // rbx
  void ***v66; // rcx
  int v67; // eax
  int v68; // ebx
  int v69; // r15d
  int v70; // r12d
  int v71; // r13d
  DWORD TickCount; // edi
  unsigned int v73; // ebx
  int v74; // eax
  unsigned __int16 *v75; // rdx
  __int64 v76; // rcx
  __int64 v77; // r8
  __int64 v78; // r9
  int v79; // ebx
  struct MachineInfo *v80; // rax
  unsigned __int16 *v81; // rax
  char v82; // al
  struct MachineInfo *v83; // rax
  unsigned __int16 *v84; // rax
  unsigned int v85; // eax
  unsigned int v86; // edx
  unsigned __int16 *v87; // rdx
  wchar_t *v88; // rcx
  unsigned __int16 *v89; // rcx
  wchar_t *v90; // rax
  struct MODULE_ALIAS_LIST *ModuleAliasList; // rax
  wchar_t *v92; // rcx
  unsigned __int16 *v93; // rcx
  const unsigned __int16 *v94; // r13
  const WCHAR *v95; // r12
  unsigned int v96; // edi
  unsigned int v97; // ebx
  struct MachineInfo *v98; // rax
  unsigned __int16 *v99; // rax
  unsigned int v100; // ebx
  unsigned int v101; // r13d
  unsigned int v102; // edi
  struct MachineInfo *v103; // rax
  unsigned __int16 *v104; // rax
  struct IDebugServiceManager *ServiceManager; // rdi
  int (__fastcall *v106)(struct IDebugServiceManager *, __int64 *, GUID *, unsigned __int64 *); // rbx
  unsigned int v107; // ebx
  struct MachineInfo *v108; // rax
  unsigned __int16 *v109; // rax
  unsigned __int64 v110; // rax
  int v111; // eax
  struct MachineInfo *v112; // rcx
  unsigned __int16 *v113; // rax
  __int64 v114; // r9
  int v115; // eax
  struct ThreadInfo *v116; // rbx
  const unsigned __int16 *v117; // rcx
  ProcessInfo *v118; // rbx
  __int64 v119; // r8
  struct MachineInfo *v120; // rax
  unsigned __int16 *v121; // rax
  ProcessInfo *v122; // rdi
  int v123; // r9d
  struct MachineInfo *v124; // rax
  unsigned __int64 v125; // rsi
  unsigned __int16 *v126; // rax
  wchar_t *v127; // rdx
  int v128; // ecx
  int v129; // eax
  struct MachineInfo *v130; // rax
  unsigned __int16 *v131; // rax
  ScopeInfo *CurrentScope; // rax
  unsigned __int16 *v133; // [rsp+20h] [rbp-E0h]
  struct ImageInfo **v134; // [rsp+28h] [rbp-D8h]
  char v135; // [rsp+40h] [rbp-C0h]
  char v136; // [rsp+41h] [rbp-BFh]
  unsigned __int8 v137; // [rsp+42h] [rbp-BEh]
  char v138; // [rsp+43h] [rbp-BDh]
  char v139; // [rsp+44h] [rbp-BCh]
  char v140; // [rsp+45h] [rbp-BBh]
  unsigned int v141; // [rsp+48h] [rbp-B8h]
  char v142; // [rsp+4Ch] [rbp-B4h]
  unsigned __int8 v143; // [rsp+4Dh] [rbp-B3h]
  char v144; // [rsp+4Eh] [rbp-B2h]
  char v145; // [rsp+4Fh] [rbp-B1h]
  char v146; // [rsp+50h] [rbp-B0h]
  unsigned int v147; // [rsp+54h] [rbp-ACh]
  wchar_t *v148; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int64 v149; // [rsp+60h] [rbp-A0h] BYREF
  ProcessInfo *v150; // [rsp+68h] [rbp-98h]
  int v151; // [rsp+70h] [rbp-90h]
  unsigned int v152; // [rsp+74h] [rbp-8Ch] BYREF
  struct ThreadInfo *v153; // [rsp+78h] [rbp-88h]
  int v154; // [rsp+80h] [rbp-80h]
  void ***v155; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int64 v156; // [rsp+90h] [rbp-70h]
  int v157; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int64 v158; // [rsp+A0h] [rbp-60h]
  struct EvalExpression *v159; // [rsp+A8h] [rbp-58h] BYREF
  struct ImageInfo *v160; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int64 v161; // [rsp+B8h] [rbp-48h]
  const unsigned __int16 *v162; // [rsp+C0h] [rbp-40h]
  $D990375940501CF3248E84BDFFDCA564 pSymbolData; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v164; // [rsp+D8h] [rbp-28h]
  _BYTE v165[8]; // [rsp+E0h] [rbp-20h] BYREF
  int v166; // [rsp+E8h] [rbp-18h]
  int v167; // [rsp+ECh] [rbp-14h]
  unsigned int v168; // [rsp+F0h] [rbp-10h]
  unsigned int v169; // [rsp+F4h] [rbp-Ch]
  unsigned int v170; // [rsp+108h] [rbp+8h]
  int v171; // [rsp+10Ch] [rbp+Ch]
  unsigned __int16 *v172; // [rsp+180h] [rbp+80h] BYREF
  unsigned int v173; // [rsp+18Ch] [rbp+8Ch]
  unsigned int v174; // [rsp+328h] [rbp+228h]
  unsigned __int64 v175; // [rsp+340h] [rbp+240h]
  wchar_t *String1; // [rsp+390h] [rbp+290h] BYREF
  unsigned int v177; // [rsp+39Ch] [rbp+29Ch]
  char v178; // [rsp+3A8h] [rbp+2A8h] BYREF
  wchar_t *Str; // [rsp+400h] [rbp+300h] BYREF
  unsigned int v180; // [rsp+40Ch] [rbp+30Ch]

  v164 = -2;
  v5 = a3;
  v153 = a2;
  v148 = a3;
  DbsDeclDynamicString<unsigned short,50,1>::DbsDeclDynamicString<unsigned short,50,1>(&Str);
  DbsDynamicString<unsigned short>::DbsDynamicString<unsigned short>(
    (unsigned int)&String1,
    (unsigned int)&v178,
    40,
    1,
    1);
  v156 = 0;
  v149 = 0;
  v9 = (int *)((char *)this + 4104);
  if ( !this || (v141 = v8, *v9 - 2 > v8) )
    v141 = 0;
  v155 = 0;
  MODULE_INFO_ENTRY::MODULE_INFO_ENTRY((MODULE_INFO_ENTRY *)v165);
  v11 = 0;
  v160 = 0;
  if ( !this )
    goto LABEL_8;
  v12 = *v9;
  v13 = 1;
  if ( *v9 == 2 )
  {
    v12 = 2;
  }
  else if ( v12 == 3 )
  {
    v12 = 3;
  }
  else if ( v12 != 1 )
  {
    goto LABEL_8;
  }
  if ( !a2 )
  {
LABEL_8:
    ErrOut(L"ERROR: Reload failure, partially initialized target\n");
    v14 = -1;
    do
      ++v14;
    while ( v5[v14] );
    *a4 = &v5[v14];
    MODULE_INFO_ENTRY::~MODULE_INFO_ENTRY((MODULE_INFO_ENTRY *)v165);
    DbsDynamicArray<CODE_CHUNK>::~DbsDynamicArray<CODE_CHUNK>(&String1);
    DbsDynamicArray<CODE_CHUNK>::~DbsDynamicArray<CODE_CHUNK>(&Str);
    return 2147549183LL;
  }
  v16 = 0;
  v147 = 0;
  v143 = 1;
  v17 = 0;
  v144 = 0;
  v145 = 1;
  v140 = 1;
  v137 = 0;
  v135 = 0;
  v138 = 0;
  v18 = 0;
  v19 = 0;
  v142 = 0;
  v150 = *(ProcessInfo **)v153;
  if ( (unsigned int)(v12 - 2) <= 1 )
  {
    v10 = (wchar_t *)((char *)this + 4108);
    v20 = *((_DWORD *)this + 1027);
    if ( (unsigned int)(v20 - 1024) <= 5 || v20 == 3143 )
    {
      v13 = 1;
      goto LABEL_26;
    }
    v13 = 1;
    if ( v12 == 2 )
    {
      v10 = (wchar_t *)((char *)this + 4108);
      if ( *((_DWORD *)this + 1027) == 2 )
        goto LABEL_26;
      v21 = *(_DWORD *)v10 == 3;
    }
    else
    {
      if ( v12 != 1 )
        goto LABEL_23;
      v21 = *(_DWORD *)v10 == 5;
    }
    if ( !v21 )
    {
LABEL_23:
      if ( *(_DWORD *)v10 != 3145 )
      {
        v136 = 1;
        goto LABEL_29;
      }
    }
  }
LABEL_26:
  v136 = 0;
LABEL_29:
  while ( 1 )
  {
    v22 = *v5;
    if ( !*v5 )
      break;
    if ( v22 > 0x20u )
    {
      if ( v22 == 47 || v22 == 45 )
      {
        v148 = ++v5;
        while ( 1 )
        {
          while ( 1 )
          {
            while ( 1 )
            {
              while ( 1 )
              {
                while ( 1 )
                {
                  while ( 1 )
                  {
                    v33 = *v5;
                    if ( *v5 <= 0x20u || v33 == 59 )
                      goto LABEL_29;
                    v148 = ++v5;
                    if ( v33 > 0x6Cu )
                      break;
                    switch ( v33 )
                    {
                      case 'l':
                        v135 = v13;
                        break;
                      case '?':
                        goto LABEL_82;
                      case 'L':
                        v142 = v13;
                        break;
                      case 'P':
                        v18 = v13;
                        break;
                      case 'a':
                        v138 = v13;
                        break;
                      case 'd':
                        v136 = v13;
                        break;
                      default:
                        if ( v33 != 102 )
                        {
                          if ( v33 != 105 )
                            goto LABEL_81;
                          v16 |= 0x40u;
                          v147 = v16;
                        }
                        v137 = v13;
                        break;
                    }
                  }
                  if ( v33 != 110 )
                    break;
                  v145 = (char)v11;
                }
                if ( v33 != 111 )
                  break;
                v16 |= 0x100000u;
                v147 = v16;
              }
              if ( v33 != 115 )
                break;
              v136 = (char)v11;
            }
            if ( v33 == 117 )
              break;
            if ( v33 == 118 )
            {
              v144 = v13;
            }
            else
            {
              if ( v33 != 119 )
              {
LABEL_81:
                dprintf(L"Reload: Unknown option '%c'\n", *(v5 - 1), v13);
LABEL_82:
                dprintf(L"Usage: .reload [flags] [module [= Address [, Size] ]]\n", v10, v13);
                dprintf(L"  Flags:   /d  Use the debugger's module list\n");
                dprintf(L"               Default for live user-mode sessions\n");
                dprintf(L"           /f  Force immediate symbol load instead of deferred\n");
                dprintf(
                  L"           /i  Force symbol load by ignoring mismatches in the pdb signature\n"
                   "               (implies /f)\n");
                dprintf(L"           /l  Just list the modules.  Kernel output same as !drivers\n");
                dprintf(L"           /n  Do not load from user-mode list in kernel sessions\n");
                dprintf(L"           /o  Overwrite symbol server cache files\n");
                dprintf(L"           /s  Use the system's module list\n");
                dprintf(L"               Default for dump and kernel sessions\n");
                dprintf(L"           /u  Unload modules, no reload\n");
                dprintf(L"         /unl  Load from unloaded module info\n");
                dprintf(L"        /user  Load only user-mode modules in kernel sessions\n");
                dprintf(L"           /v  Verbose\n");
                dprintf(L"           /w  No wildcard matching on module name\n");
                dprintf(
                  L"\n"
                   "Use \".hh .reload\" or open debugger.chm in the debuggers directory to get\n"
                   "detailed documentation on this command.\n"
                   "\n");
                v34 = -1;
                do
                  ++v34;
                while ( v5[v34] );
LABEL_90:
                *a4 = &v5[v34];
                MODULE_INFO_ENTRY::~MODULE_INFO_ENTRY((MODULE_INFO_ENTRY *)v165);
                DbsDynamicArray<CODE_CHUNK>::~DbsDynamicArray<CODE_CHUNK>(&String1);
                DbsDynamicArray<CODE_CHUNK>::~DbsDynamicArray<CODE_CHUNK>(&Str);
                return 2147942487LL;
              }
              v143 = (unsigned __int8)v11;
            }
          }
          if ( _wcsnicmp(v5, L"ser", 3u) || !(unsigned int)IsCmdSep(v5[3]) )
          {
            v32 = _wcsnicmp(v5, L"nl", 2u);
            v11 = 0;
            if ( v32 || !(unsigned int)IsCmdSep(v5[2]) )
            {
              v13 = 1;
              v17 = 1;
            }
            else
            {
              v13 = (unsigned int)((_DWORD)v11 + 1);
              v19 = (_BYTE)v11 + 1;
              v5 += 2;
              v148 = v5;
            }
          }
          else
          {
            v13 = (unsigned int)((_DWORD)v11 + 1);
            if ( *v9 != (_DWORD)v13 )
            {
              ErrOut(L".reload /user is kernel-only\n");
              v34 = -1;
              do
                ++v34;
              while ( v5[v34] );
              goto LABEL_90;
            }
            if ( *((int **)this + 31) == v11 )
            {
              ErrOut(L"Unknown system range start, check kernel symbols. Cannot reload.\n");
              v34 = -1;
              do
                ++v34;
              while ( v5[v34] );
              goto LABEL_90;
            }
            v141 = (_DWORD)v11 + 1;
            v140 = (char)v11;
            v5 = v10;
            v148 = v10;
          }
          v16 = v147;
        }
      }
      break;
    }
    v148 = ++v5;
  }
  LODWORD(v161) = (_DWORD)v11;
  v23 = (unsigned int)v11;
  v158 = (unsigned int)v11;
  v152 = (unsigned int)v11;
  v24 = BufferStringValue(&v148, 0x31u, &v152, 0, v11);
  *a4 = v148;
  v27 = 0;
  if ( !v24 || (v26 = v152) == 0 )
  {
    v139 = 0;
    v138 = 0;
    goto LABEL_130;
  }
  if ( !DbsDynamicString<unsigned short>::CopyStr(&Str, v24, v152) )
    goto LABEL_160;
  v28 = 0;
  if ( v180 >= 2 )
    v28 = Str;
  v29 = wcschr(v28, 0x3Du);
  if ( v29 )
  {
    EvaluatorHolder::Hold((EvaluatorHolder *)&v159, g_EvalSyntax, v30);
    *v29 = 0;
    v148 = v29 + 1;
    v31 = v159;
    if ( (unsigned int)EvalExpression::EvalNumAndCatch(
                         v159,
                         (const unsigned __int16 **)&v148,
                         L"Base address missing from",
                         0,
                         &v149,
                         0) )
    {
      ErrOut(L"Invalid base address\n");
      goto LABEL_102;
    }
    v35 = *((_QWORD *)this + 83);
    if ( *(_BYTE *)(v35 + 56) || (v21 = *(_BYTE *)(*(_QWORD *)(v35 + 8) + 48LL) == 0, v36 = (int)v149, v21) )
      v36 = v149;
    v156 = v36;
    v37 = wcschr(v148, 0x2Cu);
    if ( v37 )
    {
      v149 = 0;
      v148 = v37 + 1;
      (*(void (__fastcall **)(struct EvalExpression *))(*(_QWORD *)v31 + 24LL))(v31);
      if ( (unsigned int)EvalExpression::EvalNumAndCatch(
                           v31,
                           (const unsigned __int16 **)&v148,
                           L"Size missing from",
                           0,
                           &v149,
                           0)
        || (v161 = v149, v149 > 0xFFFFFFFF) )
      {
        ErrOut(L"Invalid image size\n");
LABEL_102:
        if ( v31 )
          ReleaseEvaluator(v31);
        goto LABEL_135;
      }
      v38 = wcschr(v148, 0x2Cu);
      if ( v38 )
      {
        v148 = v38 + 1;
        (*(void (__fastcall **)(struct EvalExpression *))(*(_QWORD *)v31 + 24LL))(v31);
        if ( (unsigned int)EvalExpression::EvalNumAndCatch(
                             v31,
                             (const unsigned __int16 **)&v148,
                             L"Timestamp missing from",
                             0,
                             &v149,
                             0)
          || (v158 = v149, v149 > 0xFFFFFFFF) )
        {
          ErrOut(L"Invalid timestamp\n");
          goto LABEL_102;
        }
      }
    }
    if ( v31 )
      ReleaseEvaluator(v31);
  }
  v39 = 0;
  if ( v17 )
  {
    if ( v180 >= 2 )
      v39 = Str;
    v40 = v150;
    if ( (unsigned __int8)ProcessInfo::DeleteImageByName(v150, v39, 2) )
      goto LABEL_115;
    v41 = 0;
    if ( v180 >= 2 )
      v41 = Str;
    v42 = PathTail(v41);
    if ( (unsigned __int8)ProcessInfo::DeleteImageByName(v40, v42, 1) )
    {
LABEL_115:
      dprintf(L"Unloaded %s\n", Str);
    }
    else
    {
      dprintf(L"Unable to find module '%s'\n", Str);
      v27 = -2147467262;
    }
    goto LABEL_213;
  }
  if ( v180 >= 2 )
    v39 = Str;
  if ( !DbsDynamicString<unsigned short>::CopyStr(&String1, v39, 0xFFFFFFFFLL) )
    goto LABEL_160;
  LOBYTE(v26) = wcschr(String1, 0x2Au) != 0;
  v139 = v26;
  if ( *v9 != 1 )
    goto LABEL_126;
  v43 = 0;
  if ( v180 >= 2 )
    v43 = Str;
  if ( _wcsicmp(v43, L"nt") )
  {
    LOBYTE(v26) = v139;
LABEL_126:
    if ( v138 )
      DbsDynamicString<unsigned short>::EmptyStr(&String1);
    v139 = v26;
    goto LABEL_124;
  }
  v137 = 1;
LABEL_124:
  v23 = v158;
LABEL_130:
  v44 = 0;
  if ( !v135 && !v18 && (!g_SymbolSearchPath || !*g_SymbolSearchPath) )
  {
    dprintf(L"*********************************************************************\n", v25, v26, 0xFFFFFFFFLL);
    dprintf(L"* Symbols can not be loaded because symbol path is not initialized. *\n");
    dprintf(L"*                                                                   *\n");
    dprintf(L"* The Symbol Path can be set by:                                    *\n");
    dprintf(L"*   using the _NT_SYMBOL_PATH environment variable.                 *\n");
    dprintf(L"*   using the -y <symbol_path> argument when starting the debugger. *\n");
    dprintf(L"*   using .sympath and .sympath+                                    *\n");
    dprintf(L"*********************************************************************\n");
LABEL_135:
    v27 = -2147024809;
LABEL_213:
    MODULE_INFO_ENTRY::~MODULE_INFO_ENTRY((MODULE_INFO_ENTRY *)v165);
    DbsDynamicArray<CODE_CHUNK>::~DbsDynamicArray<CODE_CHUNK>(&String1);
    DbsDynamicArray<CODE_CHUNK>::~DbsDynamicArray<CODE_CHUNK>(&Str);
    return (unsigned int)v27;
  }
  v45 = v156;
  if ( v177 >= 4 && v156 )
  {
    if ( DbsDynamicString<unsigned short>::CopyStr(&v172, String1, 0xFFFFFFFFLL) )
    {
      v46 = (0x900000001LL - (unsigned __int64)(unsigned int)(*v9 - 2)) >> 32;
      v175 = v45;
      v169 = v161;
      v47 = v166 | 4;
      v166 |= 4u;
      if ( v23 )
      {
        v168 = v23;
        v166 = v47 | 2;
      }
      v174 = v174 & 0xFFFFFFFA | 4 | v46;
      v27 = ProcessInfo::AddImage(v150, (struct MODULE_INFO_ENTRY *)v165, v137, v147, 0, &v160);
      if ( v27 )
      {
        if ( g_Target )
        {
          if ( (unsigned int)(*((_DWORD *)g_Target + 1026) - 2) > 1
            || (v48 = (struct MachineInfo *)*((_QWORD *)g_Target + 85)) == 0 )
          {
            v48 = (struct MachineInfo *)*((_QWORD *)g_Target + 83);
          }
        }
        else
        {
          v48 = 0;
        }
        v49 = FormatMachineAddr64(v48, v45);
        ErrOut(L"Unable to add module at %s\n", v49);
      }
      goto LABEL_213;
    }
    goto LABEL_160;
  }
  if ( v173 >= 2 )
    v44 = v172;
  *((_DWORD *)this + 23) = FixARMBootMachineType(v44, this, *((_WORD *)this + 46));
  if ( v19 )
  {
    if ( v177 < 4 )
    {
      ErrOut(L"/unl requires an image name\n");
      goto LABEL_135;
    }
    v51 = v150;
    ProcessInfo::AddAllTargetUnloadedImages(v150, v50);
    v52 = 0;
    if ( v177 >= 2 )
      v52 = String1;
    UnloadedImageByName = ProcessInfo::FindUnloadedImageByName(v51, v52);
    if ( !UnloadedImageByName )
    {
      ErrOut(L"No unloaded module named '%s'\n", String1);
      goto LABEL_135;
    }
    v54 = 0;
    if ( v177 >= 2 )
      v54 = String1;
    if ( DbsDynamicString<unsigned short>::CopyStr(&v172, v54, 0xFFFFFFFFLL) )
    {
      v55 = ((unsigned int)(*((_DWORD *)this + 1026) - 2) <= 1) | v174 & 0xFFFFFFFA | 4;
      v174 = v55;
      if ( v45 )
        v175 = v45;
      else
        v175 = *((_QWORD *)UnloadedImageByName + 16);
      v169 = *((_DWORD *)UnloadedImageByName + 34);
      v168 = *((_DWORD *)UnloadedImageByName + 35);
      v167 = *((_DWORD *)UnloadedImageByName + 36);
      v166 |= 7u;
      v174 = v55 | 8;
      v27 = ProcessInfo::AddImage(v51, (struct MODULE_INFO_ENTRY *)v165, v137, v147, 0, &v160);
      if ( v27 )
      {
        if ( g_Target )
        {
          if ( (unsigned int)(*((_DWORD *)g_Target + 1026) - 2) > 1
            || (v56 = (struct MachineInfo *)*((_QWORD *)g_Target + 85)) == 0 )
          {
            v56 = (struct MachineInfo *)*((_QWORD *)g_Target + 83);
          }
        }
        else
        {
          v56 = 0;
        }
        v57 = FormatMachineAddr64(v56, v175);
        ErrOut(L"Unable to add %s at %s\n", String1, v57);
      }
      goto LABEL_213;
    }
LABEL_160:
    ErrOut(L"Out of memory, cannot reload\n");
    v27 = -2147024882;
    goto LABEL_213;
  }
  v58 = 0;
  if ( v177 >= 4 )
  {
    v59 = v150;
    goto LABEL_215;
  }
  if ( v135 )
  {
    v59 = v150;
  }
  else
  {
    if ( v136 && !v17 )
    {
      v59 = v150;
      goto LABEL_194;
    }
    if ( *((_DWORD *)this + 1026) == 1 && v141 == 1 )
    {
      v59 = v150;
      ProcessInfo::DeleteImagesBelowOffset(v150, *((_QWORD *)this + 31));
    }
    else
    {
      v59 = v150;
      ProcessInfo::DeleteImages(v150);
    }
  }
  if ( v17 )
  {
    dprintf(L"Unloaded all modules\n");
    v27 = 0;
    goto LABEL_213;
  }
  if ( !v136 )
  {
    v60 = v141;
    if ( v141 != 1 && *((_DWORD *)this + 1026) == 1 )
    {
      v61 = *((_DWORD *)this + 1027);
      if ( (unsigned int)(v61 - 1024) > 5
        && v61 != 3143
        && v61 != 5
        && !(*(unsigned __int8 (__fastcall **)(TargetInfo *))(*(_QWORD *)this + 1400LL))(this) )
      {
        (*(void (__fastcall **)(TargetInfo *))(*(_QWORD *)this + 1552LL))(this);
      }
    }
    (*(void (__fastcall **)(TargetInfo *))(*(_QWORD *)this + 40LL))(this);
    if ( v141 != 1 && *((_DWORD *)this + 1026) == 1 )
      TargetInfo::QueryKernelInfo(this, v153, 1);
    goto LABEL_195;
  }
LABEL_194:
  (*(void (__fastcall **)(TargetInfo *))(*(_QWORD *)this + 40LL))(this);
  v60 = v141;
LABEL_195:
  if ( !v135 )
  {
    if ( v136 )
    {
      dprintf(L"Reloading current modules\n");
      goto LABEL_216;
    }
    if ( (unsigned int)(*((_DWORD *)this + 1026) - 2) > 1 )
    {
      v64 = L"User";
      if ( v60 != 1 )
        v64 = L"Kernel";
      dprintf(L"Loading %s Symbols\n", v64);
    }
LABEL_212:
    v27 = (*(__int64 (__fastcall **)(TargetInfo *, _QWORD, void ****))(*(_QWORD *)this + 768LL))(this, v141, &v155);
    if ( v27 )
      goto LABEL_213;
    v66 = v155;
    v65 = v153;
    goto LABEL_220;
  }
  if ( v136 )
  {
    dprintf(L"Debugger Module List Summary\n");
  }
  else
  {
    v62 = L"Driver and Image";
    if ( (unsigned int)(*((_DWORD *)this + 1026) - 2) <= 1 )
      v62 = L"Image";
    dprintf(L"System %s Summary\n", v62);
  }
  dprintf(L"Base       ");
  if ( *(_BYTE *)(*((_QWORD *)this + 83) + 56LL) )
    dprintf(L"         ");
  v63 = L"Image Size      Image Name        Creation Time\n";
  if ( !v136 )
    v63 = L"Code Size      Data Size      Image Name        Creation Time\n";
  dprintf(v63);
LABEL_215:
  if ( !v136 )
    goto LABEL_212;
LABEL_216:
  v65 = v153;
  if ( v177 < 4 )
  {
    v27 = (*(__int64 (__fastcall **)(TargetInfo *, struct ThreadInfo *))(*(_QWORD *)this + 792LL))(this, v153);
    if ( v27 < 0 )
      goto LABEL_213;
  }
  v66 = &g_DebuggerModuleIterator;
  v155 = &g_DebuggerModuleIterator;
LABEL_220:
  v67 = ((__int64 (__fastcall *)(void ***, struct ThreadInfo *, __int64))(*v66)[1])(v66, v65, 3);
  v68 = v67;
  LODWORD(v148) = v67;
  if ( v67 )
  {
    if ( v67 >= 0 )
      v68 = 0;
    v69 = v68;
    v70 = v68;
    goto LABEL_421;
  }
  v146 = 0;
  v71 = 0;
  v154 = 0;
  v69 = 0;
  v151 = 0;
  ++g_EngNotify;
  SetCheckUserInterruptShared(CheckUserInterrupt);
  RemoveInvalidModuleList(*((HANDLE *)v59 + 51));
  while ( 2 )
  {
    TickCount = GetTickCount();
    LODWORD(v159) = TickCount;
    v73 = 0;
    while ( 1 )
    {
      v152 = v73;
      if ( TickCount && GetTickCount() - TickCount > 0x1388 )
      {
        LODWORD(v159) = 0;
        dprintf(L"\n\nPress ctrl-c (cdb, kd, ntsd) or ctrl-break (windbg) to abort symbol loads that take too long.\n");
        dprintf(L"Run !sym noisy before .reload to track down problems loading symbols.\n\n");
      }
      FlushCallbacks();
      if ( CheckUserInterruptInternal(0) )
      {
        WarnOut(L" -- User interrupt\n");
        v69 = -805306054;
LABEL_411:
        v70 = v151;
        goto LABEL_412;
      }
      if ( !v142 && v73 > 0x186A0 )
        break;
      MODULE_INFO_ENTRY::Empty((MODULE_INFO_ENTRY *)v165);
      v74 = ((__int64 (__fastcall *)(void ***, _BYTE *))(*v155)[2])(v155, v165);
      v79 = v74;
      LODWORD(v148) = v74;
      if ( v74 )
      {
        v70 = v74;
        goto LABEL_347;
      }
      if ( v173 < 4 )
        MicrosoftTelemetryAssertTriggeredNoArgs(v76, v75, v77, v78);
      if ( v169 )
      {
        v82 = v166;
      }
      else
      {
        if ( g_Target )
        {
          if ( (unsigned int)(*((_DWORD *)g_Target + 1026) - 2) > 1
            || (v80 = (struct MachineInfo *)*((_QWORD *)g_Target + 85)) == 0 )
          {
            v80 = (struct MachineInfo *)*((_QWORD *)g_Target + 83);
          }
        }
        else
        {
          v80 = 0;
        }
        v81 = FormatMachineAddr64(v80, v175);
        VerbOut(L"Image at %s had size %x\n", v81, 0);
        v169 = *(_DWORD *)(*((_QWORD *)this + 83) + 32LL);
        v82 = v166 | 4;
        v166 |= 4u;
      }
      if ( (v82 & 3) == 0 )
      {
        if ( g_Target )
        {
          if ( (unsigned int)(*((_DWORD *)g_Target + 1026) - 2) > 1
            || (v83 = (struct MachineInfo *)*((_QWORD *)g_Target + 85)) == 0 )
          {
            v83 = (struct MachineInfo *)*((_QWORD *)g_Target + 83);
          }
        }
        else
        {
          v83 = 0;
        }
        v84 = FormatMachineAddr64(v83, v175);
        VerbOut(L"Unable to read image header at %s\n", v84);
      }
      if ( !v138 || v156 >= v175 && v156 < v175 + v169 )
      {
        v85 = v177;
        if ( v177 < 4 )
          goto LABEL_282;
        if ( v141 != 1 )
        {
          if ( !_wcsicmp(String1, L"nt") )
          {
            if ( !*((_QWORD *)this + 97) )
              *((_QWORD *)this + 97) = v175;
            if ( !*((_QWORD *)this + 103) )
              *((_QWORD *)this + 103) = v175;
            if ( *((_DWORD *)this + 686) == 256 && *((_DWORD *)this + 54) == 2600 )
            {
              if ( v168 == 998105999 )
              {
                v86 = 0;
                goto LABEL_265;
              }
              if ( v168 == 1014679956 || v168 == 1015611201 )
              {
                v86 = 2425088;
LABEL_265:
                TargetInfo::SetNtCsdVersion(this, v86);
              }
            }
LABEL_282:
            v93 = 0;
            if ( v173 >= 2 )
              v93 = v172;
            v94 = PathTail(v93);
            v162 = v94;
            if ( v135 )
            {
              if ( *((_DWORD *)this + 1026) == 1
                && (*((_DWORD *)this + 1027) == 1024
                 || *((_DWORD *)this + 1027) == 5
                 && (*(__int64 (__fastcall **)(TargetInfo *))(*(_QWORD *)this + 1552LL))(this)
                 && *(_DWORD *)((*(__int64 (__fastcall **)(TargetInfo *))(*(_QWORD *)this + 1552LL))(this) + 4104) == 1
                 && *(_DWORD *)((*(__int64 (__fastcall **)(TargetInfo *))(*(_QWORD *)this + 1552LL))(this) + 4108) == 1024)
                && (unsigned int)(*((_DWORD *)this + 51) - 4097) <= 4 )
              {
                v95 = &strIn;
              }
              else
              {
                v95 = TimeToStr(v168);
              }
              if ( v136 )
              {
                v96 = v169;
                v97 = (v169 + 1023) >> 10;
                if ( g_Target )
                {
                  if ( (unsigned int)(*((_DWORD *)g_Target + 1026) - 2) > 1
                    || (v98 = (struct MachineInfo *)*((_QWORD *)g_Target + 85)) == 0 )
                  {
                    v98 = (struct MachineInfo *)*((_QWORD *)g_Target + 83);
                  }
                }
                else
                {
                  v98 = 0;
                }
                v99 = FormatMachineAddr64(v98, v175);
                dprintf(L"%s %6lx (%4ld k) %12s  %s\n", v99, v96, v97, v94, v95);
              }
              else
              {
                v100 = (unsigned int)(v171 + 1023) >> 10;
                v101 = v170;
                v102 = (v170 + 1023) >> 10;
                if ( g_Target )
                {
                  if ( (unsigned int)(*((_DWORD *)g_Target + 1026) - 2) > 1
                    || (v103 = (struct MachineInfo *)*((_QWORD *)g_Target + 85)) == 0 )
                  {
                    v103 = (struct MachineInfo *)*((_QWORD *)g_Target + 83);
                  }
                }
                else
                {
                  v103 = 0;
                }
                v104 = FormatMachineAddr64(v103, v175);
                LODWORD(v134) = v100;
                LODWORD(v133) = v171;
                dprintf(L"%s %6lx (%4ld k) %5lx (%3ld k) %12s  %s\n", v104, v101, v102, v133, v134, v162, v95);
              }
              v58 = 0;
LABEL_339:
              if ( v177 < 4 )
              {
                v71 = v154;
              }
              else
              {
                if ( !v139 )
                  goto LABEL_411;
                v71 = ++v154;
              }
              if ( v138 )
                goto LABEL_411;
              goto LABEL_344;
            }
            ServiceManager = TargetInfo::GetServiceManager(this);
            v149 = 0;
            v157 = 0;
            v106 = *(int (__fastcall **)(struct IDebugServiceManager *, __int64 *, GUID *, unsigned __int64 *))(*(_QWORD *)ServiceManager + 32LL);
            Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v149);
            if ( v106(ServiceManager, DEBUG_SERVICE_OS_INFORMATION, &GUID_40b23eac_f503_46fc_9c95_09384d050a11, &v149) >= 0
              && (*(int (__fastcall **)(unsigned __int64, int *))(*(_QWORD *)v149 + 24LL))(v149, &v157) >= 0 )
            {
              v58 = v157 != 2;
            }
            if ( v177 < 4
              && v141 != 1
              && *((_DWORD *)this + 1026) == 1
              && !v136
              && *((_QWORD *)this + 103) == v175
              && !v58 )
            {
              Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v149);
              v71 = v154;
              v58 = 0;
              goto LABEL_344;
            }
            v58 = 0;
            if ( v144 )
            {
              v107 = v169;
              if ( g_Target )
              {
                if ( (unsigned int)(*((_DWORD *)g_Target + 1026) - 2) > 1
                  || (v108 = (struct MachineInfo *)*((_QWORD *)g_Target + 85)) == 0 )
                {
                  v108 = (struct MachineInfo *)*((_QWORD *)g_Target + 83);
                }
              }
              else
              {
                v108 = 0;
              }
              v109 = FormatMachineAddr64(v108, v175);
              LODWORD(v134) = v168;
              LODWORD(v133) = v167;
              dprintf(
                L"AddImage: %s\n DllBase  = %s\n Size     = %08x\n Checksum = %08x\n TimeDateStamp = %08x\n",
                v172,
                v109,
                v107,
                v133,
                v134);
            }
            else if ( v177 < 4 )
            {
              dprintf(L".");
              if ( (((_BYTE)v152 + 1) & 0x3F) == 0 )
                dprintf(L"\n");
            }
            v110 = v175;
            if ( v156 )
              v110 = v156;
            v175 = v110;
            v174 |= 8u;
            v111 = ProcessInfo::AddImage(v150, (struct MODULE_INFO_ENTRY *)v165, v137, v147, 0, &v160);
            v69 = v111;
            if ( !v111 )
            {
LABEL_338:
              Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v149);
              goto LABEL_339;
            }
            if ( v111 != 995 )
            {
              if ( g_Target )
              {
                if ( (unsigned int)(*((_DWORD *)g_Target + 1026) - 2) > 1
                  || (v112 = (struct MachineInfo *)*((_QWORD *)g_Target + 85)) == 0 )
                {
                  v112 = (struct MachineInfo *)*((_QWORD *)g_Target + 83);
                }
              }
              else
              {
                v112 = 0;
              }
              v113 = FormatMachineAddr64(v112, v175);
              ErrOut(L"Unable to add module at %s\n", v113);
              v151 = v69;
              goto LABEL_338;
            }
            if ( g_Target )
            {
              if ( (unsigned int)(*((_DWORD *)g_Target + 1026) - 2) > 1
                || (v120 = (struct MachineInfo *)*((_QWORD *)g_Target + 85)) == 0 )
              {
                v120 = (struct MachineInfo *)*((_QWORD *)g_Target + 83);
              }
            }
            else
            {
              v120 = 0;
            }
            v121 = FormatMachineAddr64(v120, v175);
            ErrOut(L"Canceled Operation: Unable to add module at %s\n", v121);
            WarnOut(L" -- User interrupt\n");
            v69 = -805306054;
            v70 = -805306054;
            Microsoft::WRL::ComPtr<Debugger::TargetComposition::Host::InjectedInlineFrame>::InternalRelease(&v149);
LABEL_412:
            v122 = v150;
            goto LABEL_413;
          }
          v85 = v177;
        }
        v87 = 0;
        if ( v173 >= 2 )
          v87 = v172;
        v88 = 0;
        if ( v85 >= 2 )
          v88 = String1;
        if ( !(unsigned int)MatchPathTails(v88, v87, v143) )
        {
          v89 = 0;
          if ( v173 >= 2 )
            v89 = v172;
          v90 = (wchar_t *)PathTail(v89);
          ModuleAliasList = FindModuleAliasList(v90, 0);
          if ( !ModuleAliasList )
            goto LABEL_344;
          v92 = 0;
          if ( v177 >= 2 )
            v92 = String1;
          if ( !(unsigned int)MatchPathTails(v92, *((const unsigned __int16 **)ModuleAliasList + 2), v143) )
            goto LABEL_344;
          VerbOut(L"Module \"%s\" matches \"%s\" alias.\n", v172, String1);
        }
        goto LABEL_282;
      }
LABEL_344:
      v73 = v152 + 1;
      TickCount = (unsigned int)v159;
    }
    ErrOut(L"ModuleList is corrupt - walked over %u module entries\n", 100000);
    v70 = -2147024809;
    v79 = (int)v148;
LABEL_347:
    v151 = v70;
    v114 = 0;
    if ( !v136 && *((_DWORD *)this + 1026) != 1 && v141 != 1 )
    {
LABEL_354:
      if ( !v145 || v79 < 0 )
        goto LABEL_362;
      if ( !v138 && v177 < 4 )
        dprintf(L"Loading User Symbols\n", v75, v77, 0);
      v141 = 1;
      v115 = (*(__int64 (__fastcall **)(TargetInfo *, __int64, void ****, __int64))(*(_QWORD *)this + 768LL))(
               this,
               1,
               &v155,
               v114);
      v116 = v153;
      if ( v115 || ((unsigned int (__fastcall *)(void ***, struct ThreadInfo *, __int64))(*v155)[1])(v155, v153, 3) )
      {
LABEL_363:
        if ( v140 && v177 < 4 )
        {
          v117 = &strIn;
          if ( !v135 )
            v117 = L"Loading unloaded module list\n";
          ListUnloadedModules(v116, v135 != 0 ? 1 : 4, 0, 0, v117);
          v140 = 0;
        }
        goto LABEL_368;
      }
LABEL_225:
      v58 = 0;
      continue;
    }
    break;
  }
  if ( v177 < 4 )
  {
    dprintf(L"\n", v75, v77, 0);
    v114 = 0;
  }
  if ( !v136 )
  {
    if ( v141 != 1 )
      goto LABEL_354;
LABEL_362:
    v116 = v153;
    goto LABEL_363;
  }
LABEL_368:
  if ( *((_DWORD *)this + 1026) == 1 && v141 == 1 )
  {
    v118 = g_Process;
    if ( *(_QWORD *)v153 )
      v118 = *(ProcessInfo **)v153;
    if ( *((TargetInfo **)v118 + 11) != this )
      MicrosoftTelemetryAssertTriggeredNoArgs(v76, v75, v77, 0);
    *((_BYTE *)v118 + 1572) &= 0x7Eu;
  }
  if ( !v136 && v177 < 4 && !v146 )
  {
    v155 = &g_NtWow64UserModuleIterator;
    if ( !((unsigned int (__fastcall *)(void ***, struct ThreadInfo *, __int64, _QWORD))g_NtWow64UserModuleIterator[1])(
            &g_NtWow64UserModuleIterator,
            v153,
            3,
            0) )
    {
      v146 = 1;
      dprintf(L"Loading Wow64 Symbols\n", v75, v119, 0);
      goto LABEL_225;
    }
  }
  v122 = v150;
  ProcessInfo::AddNonSystemClrImages(v150, v75, v137, 0);
  v69 = v123;
  if ( v135 != (_BYTE)v123 )
  {
    dprintf(L"****************************************************************************\n");
    DotDrivers(0, 0);
    dprintf(L"****************************************************************************\n");
LABEL_413:
    v123 = 0;
    goto LABEL_414;
  }
  if ( v177 < 4 )
    goto LABEL_414;
  if ( v139 == (_BYTE)v123 )
  {
    WarnOut(L"\n\"%s\" was not found in the image list.\n", String1);
    if ( g_Target )
    {
      if ( (unsigned int)(*((_DWORD *)g_Target + 1026) - 2) > 1
        || (v124 = (struct MachineInfo *)*((_QWORD *)g_Target + 85)) == 0 )
      {
        v124 = (struct MachineInfo *)*((_QWORD *)g_Target + 83);
      }
    }
    else
    {
      v124 = 0;
    }
    v125 = v156;
    v126 = FormatMachineAddr64(v124, v156);
    WarnOut(L"Debugger will attempt to load \"%s\" at given base %s.\n\n", String1, v126);
    WarnOut(
      L"Please provide the full image name, including the extension (i.e. kernel32.dll)\n"
       "for more reliable results.Base address and size overrides can be given as\n"
       ".reload <image.ext>=<base>,<size>.\n");
    MODULE_INFO_ENTRY::Empty((MODULE_INFO_ENTRY *)v165);
    v127 = 0;
    if ( v177 >= 2 )
      v127 = String1;
    if ( !DbsDynamicString<unsigned short>::CopyStr(&v172, v127, 0xFFFFFFFFLL) )
    {
      ErrOut(L"Out of memory, cannot reload\n");
      v69 = -2147024882;
      goto LABEL_413;
    }
    v128 = (0x900000001LL - (unsigned __int64)(unsigned int)(*((_DWORD *)this + 1026) - 2)) >> 32;
    v175 = v125;
    v169 = v161;
    v129 = v166 | 4;
    v166 |= 4u;
    if ( (_DWORD)v158 )
    {
      v168 = v158;
      v166 = v129 | 2;
    }
    v174 = v174 & 0xFFFFFFFA | 4 | v128;
    v69 = ProcessInfo::AddImage(v122, (struct MODULE_INFO_ENTRY *)v165, v137, v147, 0, &v160);
    v123 = 0;
    if ( v69 )
    {
      if ( g_Target )
      {
        if ( (unsigned int)(*((_DWORD *)g_Target + 1026) - 2) > 1
          || (v130 = (struct MachineInfo *)*((_QWORD *)g_Target + 85)) == 0 )
        {
          v130 = (struct MachineInfo *)*((_QWORD *)g_Target + 83);
        }
      }
      else
      {
        v130 = 0;
      }
      v131 = FormatMachineAddr64(v130, v125);
      ErrOut(L"Unable to add module at %s\n", v131);
      goto LABEL_413;
    }
  }
  else if ( !v71 )
  {
    v69 = -2147467259;
  }
LABEL_414:
  --g_EngNotify;
  if ( v69 >= 0 )
  {
    NotifyChangeSymbolState(3u, 0, v122, 0);
    v123 = 0;
  }
  if ( *((_DWORD *)v122 + 124) != v123 && v69 >= 0 )
  {
    CurrentScope = GetCurrentScope();
    ScopeInfo::Reset(CurrentScope);
  }
  pSymbolData.pBinPathNonExist = (PCWSTR)&g_binPathNonExist;
  pSymbolData.pSymbolPathNonExist = (PCWSTR)&g_symbolPathNonExist;
  if ( !ReportSymbolLoadSummary(*((HANDLE *)v122 + 51), Str, &pSymbolData) )
    ErrOut(L"WARNING: The reporting load summary function failed\n");
LABEL_421:
  if ( v70 < 0 )
    ErrOut(L"WARNING: .reload failed, module list may be incomplete\n");
  MODULE_INFO_ENTRY::~MODULE_INFO_ENTRY((MODULE_INFO_ENTRY *)v165);
  DbsDynamicArray<CODE_CHUNK>::~DbsDynamicArray<CODE_CHUNK>(&String1);
  DbsDynamicArray<CODE_CHUNK>::~DbsDynamicArray<CODE_CHUNK>(&Str);
  return (unsigned int)v69;
}

```

## disassembly

```asm
0x18009a324  push    rbp
0x18009a326  push    rbx
0x18009a327  push    rsi
0x18009a328  push    rdi
0x18009a329  push    r12
0x18009a32b  push    r13
0x18009a32d  push    r14
0x18009a32f  push    r15
0x18009a331  lea     rbp, [rsp-398h]
0x18009a339  sub     rsp, 498h
0x18009a340  mov     [rbp+3D0h+var_3F8], 0FFFFFFFFFFFFFFFEh
0x18009a348  mov     rax, cs:__security_cookie
0x18009a34f  xor     rax, rsp
0x18009a352  mov     [rbp+3D0h+var_50], rax
0x18009a359  mov     rsi, r9
0x18009a35c  mov     rbx, r8
0x18009a35f  mov     r15, rdx
0x18009a362  mov     [rsp+4D0h+var_458], rdx
0x18009a367  mov     r14, rcx
0x18009a36a  mov     [rsp+4D0h+var_478], rbx
0x18009a36f  lea     rcx, [rbp+3D0h+Str]
0x18009a376  call    ??0?$DbsDeclDynamicString@G$0DC@$00@@QEAA@XZ; DbsDeclDynamicString<ushort,50,1>::DbsDeclDynamicString<ushort,50,1>(void)
0x18009a37b  nop
0x18009a37c  mov     r9d, 1
0x18009a382  mov     byte ptr [rsp+4D0h+var_4B0], r9b
0x18009a387  lea     r8d, [r9+27h]
0x18009a38b  lea     rdx, [rbp+3D0h+var_128]
0x18009a392  lea     rcx, [rbp+3D0h+String1]
0x18009a399  call    ??0?$DbsDynamicString@G@@QEAA@PEAGK_N1@Z; DbsDynamicString<ushort>::DbsDynamicString<ushort>(ushort *,ulong,bool,bool)
0x18009a39e  nop
0x18009a39f  xor     ecx, ecx
0x18009a3a1  mov     [rbp+3D0h+var_440], rcx
0x18009a3a5  mov     [rsp+4D0h+var_470], rcx
0x18009a3aa  lea     rdi, [r14+1008h]
0x18009a3b1  test    r14, r14
0x18009a3b4  jz      short loc_18009A3C5
0x18009a3b6  mov     eax, [rdi]
0x18009a3b8  sub     eax, 2
0x18009a3bb  cmp     eax, r9d
0x18009a3be  mov     [rsp+4D0h+var_488], r9d
0x18009a3c3  jbe     short loc_18009A3C9
0x18009a3c5  mov     [rsp+4D0h+var_488], ecx
0x18009a3c9  mov     [rbp+3D0h+var_448], rcx
0x18009a3cd  lea     rcx, [rbp+3D0h+var_3F0]; this
0x18009a3d1  call    ??0MODULE_INFO_ENTRY@@QEAA@XZ; MODULE_INFO_ENTRY::MODULE_INFO_ENTRY(void)
0x18009a3d6  nop
0x18009a3d7  xor     r11d, r11d
0x18009a3da  mov     [rbp+3D0h+var_420], r11
0x18009a3de  test    r14, r14
0x18009a3e1  jz      short loc_18009A3F8
0x18009a3e3  mov     ecx, [rdi]
0x18009a3e5  lea     r8d, [r11+1]
0x18009a3e9  cmp     ecx, 2
0x18009a3ec  jz      short loc_18009A46D
0x18009a3ee  cmp     ecx, 3
0x18009a3f1  jz      short loc_18009A466
0x18009a3f3  cmp     ecx, r8d
0x18009a3f6  jz      short loc_18009A472
0x18009a3f8  lea     rcx, aErrorReloadFai; "ERROR: Reload failure, partially initia"...
0x18009a3ff  call    ?ErrOut@@YAXPEBGZZ; ErrOut(ushort const *,...)
0x18009a404  or      rax, 0FFFFFFFFFFFFFFFFh
0x18009a408  xor     edi, edi
0x18009a40a  inc     rax
0x18009a40d  cmp     [rbx+rax*2], di
0x18009a411  jnz     short loc_18009A40A
0x18009a413  lea     rax, [rbx+rax*2]
0x18009a417  mov     [rsi], rax
0x18009a41a  lea     rcx, [rbp+3D0h+var_3F0]; this
0x18009a41e  call    ??1MODULE_INFO_ENTRY@@UEAA@XZ; MODULE_INFO_ENTRY::~MODULE_INFO_ENTRY(void)
0x18009a423  nop
0x18009a424  lea     rcx, [rbp+3D0h+String1]
0x18009a42b  call    ??1?$DbsDynamicArray@UCODE_CHUNK@@@@QEAA@XZ; DbsDynamicArray<CODE_CHUNK>::~DbsDynamicArray<CODE_CHUNK>(void)
0x18009a430  nop
0x18009a431  lea     rcx, [rbp+3D0h+Str]
0x18009a438  call    ??1?$DbsDynamicArray@UCODE_CHUNK@@@@QEAA@XZ; DbsDynamicArray<CODE_CHUNK>::~DbsDynamicArray<CODE_CHUNK>(void)
0x18009a43d  mov     eax, 8000FFFFh
0x18009a442  mov     rcx, [rbp+3D0h+var_50]
0x18009a449  xor     rcx, rsp; StackCookie
0x18009a44c  call    __security_check_cookie
0x18009a451  add     rsp, 498h
0x18009a458  pop     r15
0x18009a45a  pop     r14
0x18009a45c  pop     r13
0x18009a45e  pop     r12
0x18009a460  pop     rdi
0x18009a461  pop     rsi
0x18009a462  pop     rbx
0x18009a463  pop     rbp
0x18009a464  retn
0x18009a466  mov     ecx, 3
0x18009a46b  jmp     short loc_18009A472
0x18009a46d  mov     ecx, 2
0x18009a472  test    r15, r15
0x18009a475  jz      short loc_18009A3F8
0x18009a477  mov     r10d, r11d
0x18009a47a  mov     [rsp+4D0h+var_47C], r11d
0x18009a47f  mov     [rsp+4D0h+var_483], r8b
0x18009a484  mov     r15b, r11b
0x18009a487  mov     [rsp+4D0h+var_482], r11b
0x18009a48c  mov     [rsp+4D0h+var_481], r8b
0x18009a491  mov     [rsp+4D0h+var_48B], r8b
0x18009a496  mov     [rsp+4D0h+var_48E], r11b
0x18009a49b  mov     [rsp+4D0h+var_490], r11b
0x18009a4a0  mov     [rsp+4D0h+var_48D], r11b
0x18009a4a5  mov     r12b, r11b
0x18009a4a8  mov     r13b, r11b
0x18009a4ab  mov     [rsp+4D0h+var_484], r11b
0x18009a4b0  mov     rax, [rsp+4D0h+var_458]
0x18009a4b5  mov     rax, [rax]
0x18009a4b8  mov     [rsp+4D0h+var_468], rax
0x18009a4bd  lea     eax, [rcx-2]
0x18009a4c0  cmp     eax, r8d
0x18009a4c3  ja      short loc_18009A51E
0x18009a4c5  lea     rdx, [r14+100Ch]
0x18009a4cc  mov     r8d, [rdx]
0x18009a4cf  lea     eax, [r8-400h]
0x18009a4d6  cmp     eax, 5
0x18009a4d9  jbe     short loc_18009A518
0x18009a4db  cmp     r8d, 0C47h
0x18009a4e2  jz      short loc_18009A518
0x18009a4e4  mov     r8d, 1
0x18009a4ea  cmp     ecx, 2
0x18009a4ed  jnz     short loc_18009A4FF
0x18009a4ef  lea     rdx, [r14+100Ch]
0x18009a4f6  cmp     [rdx], ecx
0x18009a4f8  jz      short loc_18009A51E
0x18009a4fa  cmp     dword ptr [rdx], 3
0x18009a4fd  jmp     short loc_18009A507
0x18009a4ff  cmp     ecx, r8d
0x18009a502  jnz     short loc_18009A509
0x18009a504  cmp     dword ptr [rdx], 5
0x18009a507  jz      short loc_18009A51E
0x18009a509  cmp     dword ptr [rdx], 0C49h
0x18009a50f  jz      short loc_18009A51E
0x18009a511  mov     [rsp+4D0h+var_48F], r8b
0x18009a516  jmp     short loc_18009A538
0x18009a518  mov     r8d, 1
0x18009a51e  mov     [rsp+4D0h+var_48F], r11b
0x18009a523  jmp     short loc_18009A538
0x18009a525  cmp     ax, 20h ; ' '
0x18009a529  ja      loc_18009A62F
0x18009a52f  add     rbx, 2
0x18009a533  mov     [rsp+4D0h+var_478], rbx
0x18009a538  movzx   eax, word ptr [rbx]
0x18009a53b  test    ax, ax
0x18009a53e  jnz     short loc_18009A525
0x18009a540  mov     dword ptr [rbp+3D0h+var_418], r11d
0x18009a544  mov     ebx, r11d
0x18009a547  mov     [rbp+3D0h+var_430], rbx
0x18009a54b  mov     [rsp+4D0h+var_45C], r11d
0x18009a550  mov     [rsp+4D0h+var_4B0], r11; int *
0x18009a555  xor     r9d, r9d; unsigned __int16 *
0x18009a558  lea     r8, [rsp+4D0h+var_45C]; unsigned int *
0x18009a55d  lea     edx, [r9+31h]; unsigned int
0x18009a561  lea     rcx, [rsp+4D0h+var_478]; unsigned __int16 **
0x18009a566  call    ?BufferStringValue@@YAPEAGPEAPEAGKPEAKPEAGPEAH@Z; BufferStringValue(ushort * *,ulong,ulong *,ushort *,int *)
0x18009a56b  mov     rcx, [rsp+4D0h+var_478]
0x18009a570  mov     [rsi], rcx
0x18009a573  xor     esi, esi
0x18009a575  mov     r9d, 0FFFFFFFFh
0x18009a57b  test    rax, rax
0x18009a57e  jz      loc_18009ABCC
0x18009a584  mov     r8d, [rsp+4D0h+var_45C]
0x18009a589  test    r8d, r8d
0x18009a58c  jz      loc_18009ABCC
0x18009a592  mov     rdx, rax
0x18009a595  lea     rcx, [rbp+3D0h+Str]
0x18009a59c  call    ?CopyStr@?$DbsDynamicString@G@@QEAAPEAGPEBGK@Z; DbsDynamicString<ushort>::CopyStr(ushort const *,ulong)
0x18009a5a1  test    rax, rax
0x18009a5a4  jz      loc_18009AE2E
0x18009a5aa  mov     ecx, esi
0x18009a5ac  cmp     [rbp+3D0h+var_C4], 2
0x18009a5b3  cmovnb  rcx, [rbp+3D0h+Str]; Str
0x18009a5bb  lea     edx, [rsi+3Dh]; Ch
0x18009a5be  call    wcschr
0x18009a5c3  mov     rbx, rax
0x18009a5c6  test    rax, rax
0x18009a5c9  jz      loc_18009AA91
0x18009a5cf  mov     edx, cs:?g_EvalSyntax@@3KA; unsigned int
0x18009a5d5  lea     rcx, [rbp+3D0h+var_428]; this
0x18009a5d9  call    ?Hold@EvaluatorHolder@@QEAAXKH@Z; EvaluatorHolder::Hold(ulong,int)
0x18009a5de  nop
0x18009a5df  mov     [rbx], si
0x18009a5e2  lea     rax, [rbx+2]
0x18009a5e6  mov     [rsp+4D0h+var_478], rax
0x18009a5eb  mov     [rsp+4D0h+var_4A8], rsi; unsigned int *
0x18009a5f0  lea     rax, [rsp+4D0h+var_470]
0x18009a5f5  mov     [rsp+4D0h+var_4B0], rax; unsigned __int64 *
0x18009a5fa  xor     r9d, r9d; unsigned int
0x18009a5fd  lea     r8, aBaseAddressMis; "Base address missing from"
0x18009a604  lea     rdx, [rsp+4D0h+var_478]; unsigned __int16 **
0x18009a609  mov     rbx, [rbp+3D0h+var_428]
0x18009a60d  mov     rcx, rbx; this
0x18009a610  call    ?EvalNumAndCatch@EvalExpression@@QEAAJPEAPEBGPEBGKPEA_KPEAK@Z; EvalExpression::EvalNumAndCatch(ushort const * *,ushort const *,ulong,unsigned __int64 *,ulong *)
0x18009a615  test    eax, eax
0x18009a617  jz      loc_18009A94C
0x18009a61d  lea     rcx, aInvalidBaseAdd; "Invalid base address\n"
0x18009a624  call    ?ErrOut@@YAXPEBGZZ; ErrOut(ushort const *,...)
0x18009a629  nop
0x18009a62a  jmp     loc_18009AA70
0x18009a62f  cmp     ax, 2Fh ; '/'
0x18009a633  jz      short loc_18009A63F
0x18009a635  cmp     ax, 2Dh ; '-'
0x18009a639  jnz     loc_18009A540
0x18009a63f  add     rbx, 2
0x18009a643  mov     [rsp+4D0h+var_478], rbx
0x18009a648  jmp     loc_18009A7ED
0x18009a64d  cmp     ax, 3Bh ; ';'
0x18009a651  jz      loc_18009A538
0x18009a657  add     rbx, 2
0x18009a65b  mov     [rsp+4D0h+var_478], rbx
0x18009a660  cmp     ax, 6Ch ; 'l'
0x18009a664  ja      short loc_18009A6DD
0x18009a666  jz      short loc_18009A6D3
0x18009a668  cmp     ax, 3Fh ; '?'
0x18009a66c  jz      loc_18009A80F
0x18009a672  cmp     ax, 4Ch ; 'L'
0x18009a676  jz      short loc_18009A6C9
0x18009a678  cmp     ax, 50h ; 'P'
0x18009a67c  jz      short loc_18009A6C1
0x18009a67e  cmp     ax, 61h ; 'a'
0x18009a682  jz      short loc_18009A6B7
0x18009a684  cmp     ax, 64h ; 'd'
0x18009a688  jz      short loc_18009A6AD
0x18009a68a  cmp     ax, 66h ; 'f'
0x18009a68e  jz      short loc_18009A6A3
0x18009a690  cmp     ax, 69h ; 'i'
0x18009a694  jnz     loc_18009A7FF
0x18009a69a  or      r10d, 40h
0x18009a69e  mov     [rsp+4D0h+var_47C], r10d
0x18009a6a3  mov     [rsp+4D0h+var_48E], r8b
0x18009a6a8  jmp     loc_18009A7ED
0x18009a6ad  mov     [rsp+4D0h+var_48F], r8b
0x18009a6b2  jmp     loc_18009A7ED
0x18009a6b7  mov     [rsp+4D0h+var_48D], r8b
0x18009a6bc  jmp     loc_18009A7ED
0x18009a6c1  mov     r12b, r8b
0x18009a6c4  jmp     loc_18009A7ED
0x18009a6c9  mov     [rsp+4D0h+var_484], r8b
0x18009a6ce  jmp     loc_18009A7ED
0x18009a6d3  mov     [rsp+4D0h+var_490], r8b
0x18009a6d8  jmp     loc_18009A7ED
0x18009a6dd  movzx   ecx, ax
0x18009a6e0  sub     ecx, 6Eh ; 'n'
0x18009a6e3  jz      loc_18009A7E8
0x18009a6e9  sub     ecx, 1
0x18009a6ec  jz      loc_18009A7DC
0x18009a6f2  sub     ecx, 4
0x18009a6f5  jz      loc_18009A7D5
0x18009a6fb  sub     ecx, 2
0x18009a6fe  jz      short loc_18009A722
0x18009a700  sub     ecx, 1
0x18009a703  jz      short loc_18009A718
0x18009a705  cmp     ecx, 1
0x18009a708  jnz     loc_18009A7FF
0x18009a70e  mov     [rsp+4D0h+var_483], r11b
0x18009a713  jmp     loc_18009A7ED
0x18009a718  mov     [rsp+4D0h+var_482], r8b
0x18009a71d  jmp     loc_18009A7ED
0x18009a722  mov     r8d, 3; MaxCount
0x18009a728  lea     rdx, aSer; "ser"
0x18009a72f  mov     rcx, rbx; String1
0x18009a732  call    cs:__imp__wcsnicmp
0x18009a739  nop     dword ptr [rax+rax+00h]
0x18009a73e  xor     r11d, r11d
0x18009a741  test    eax, eax
0x18009a743  jnz     short loc_18009A783
0x18009a745  lea     rdx, [rbx+6]
0x18009a749  movzx   ecx, word ptr [rdx]; unsigned __int16
0x18009a74c  call    ?IsCmdSep@@YAHG@Z; IsCmdSep(ushort)
0x18009a751  test    eax, eax
0x18009a753  jz      short loc_18009A783
0x18009a755  lea     r8d, [r11+1]
0x18009a759  cmp     [rdi], r8d
0x18009a75c  jnz     loc_18009A8FD
0x18009a762  cmp     [r14+0F8h], r11
0x18009a769  jz      loc_18009A8E0
0x18009a76f  mov     [rsp+4D0h+var_488], r8d
0x18009a774  mov     [rsp+4D0h+var_48B], r11b
0x18009a779  mov     rbx, rdx
0x18009a77c  mov     [rsp+4D0h+var_478], rdx
0x18009a781  jmp     short loc_18009A7CE
0x18009a783  mov     r8d, 2; MaxCount
0x18009a789  lea     rdx, aNl; "nl"
0x18009a790  mov     rcx, rbx; String1
0x18009a793  call    cs:__imp__wcsnicmp
0x18009a79a  nop     dword ptr [rax+rax+00h]
0x18009a79f  xor     r11d, r11d
0x18009a7a2  test    eax, eax
0x18009a7a4  jnz     short loc_18009A7C5
0x18009a7a6  movzx   ecx, word ptr [rbx+4]; unsigned __int16
0x18009a7aa  call    ?IsCmdSep@@YAHG@Z; IsCmdSep(ushort)
0x18009a7af  test    eax, eax
0x18009a7b1  jz      short loc_18009A7C5
0x18009a7b3  lea     r8d, [r11+1]
0x18009a7b7  mov     r13b, r8b
0x18009a7ba  add     rbx, 4
0x18009a7be  mov     [rsp+4D0h+var_478], rbx
0x18009a7c3  jmp     short loc_18009A7CE
0x18009a7c5  mov     r8d, 1
  ... truncated ...
```
