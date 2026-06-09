# NGenParser::IsCommandLineOption(ushort const *,NewCommandLineOptions &)

- ea: `0x140002168`
- end: `0x140004693`
- name: `?IsCommandLineOption@NGenParser@@AEAA_NPEBGAEAUNewCommandLineOptions@@@Z`
- size: `9515`
- prototype: `char __fastcall(NGenParser *this, const unsigned __int16 *, BSTR *, __int64)`
- caller_count: `1`
- callee_count: `25`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x140004694`

## callees

- `0x14000119c`
- `0x1400011d4`
- `0x140001214`
- `0x140001374`
- `0x140001504`
- `0x14000154c`
- `0x1400016f4`
- `0x140001e08`
- `0x140001f28`
- `0x140001fa0`
- `0x140002168`
- `0x1400060bc`
- `0x14000a10c`
- `0x14000ab08`
- `0x14000ad80`
- `0x14000aea4`
- `0x14000b010`
- `0x14000b578`
- `0x14000b898`
- `0x14000c51c`
- `0x14000e5e4`
- `0x1400102cc`
- `0x140010454`
- `0x140013200`
- `0x140013eb0`

## import_xrefs

- `KERNEL32!GetFileAttributesW` at `0x140002fcc`
- `KERNEL32!GetFileAttributesW` at `0x140002fcc`
- `ucrtbase_clr0400!_wtoi` at `0x140004277`
- `ucrtbase_clr0400!_wtoi` at `0x140004277`
- `ucrtbase_clr0400!_wcsicmp` at `0x140002538`
- `ucrtbase_clr0400!_wcsicmp` at `0x140002538`
- `OLEAUT32!__imp_SysAllocString` at `0x14000221f`
- `OLEAUT32!__imp_SysAllocString` at `0x140002271`
- `OLEAUT32!__imp_SysAllocString` at `0x1400022d0`
- `OLEAUT32!__imp_SysAllocString` at `0x140002cd1`
- `OLEAUT32!__imp_SysAllocString` at `0x140002ff8`
- `OLEAUT32!__imp_SysAllocString` at `0x140003251`
- `OLEAUT32!__imp_SysAllocString` at `0x1400034ae`
- `OLEAUT32!__imp_SysAllocString` at `0x140003707`
- `OLEAUT32!__imp_SysAllocString` at `0x140003989`
- `OLEAUT32!__imp_SysAllocString` at `0x140003be6`
- `OLEAUT32!__imp_SysAllocString` at `0x140003e43`
- `OLEAUT32!__imp_SysAllocString` at `0x14000221f`
- `OLEAUT32!__imp_SysAllocString` at `0x140002271`
- `OLEAUT32!__imp_SysAllocString` at `0x1400022d0`
- `OLEAUT32!__imp_SysAllocString` at `0x140002cd1`
- `OLEAUT32!__imp_SysAllocString` at `0x140002ff8`
- `OLEAUT32!__imp_SysAllocString` at `0x140003251`
- `OLEAUT32!__imp_SysAllocString` at `0x1400034ae`
- `OLEAUT32!__imp_SysAllocString` at `0x140003707`
- `OLEAUT32!__imp_SysAllocString` at `0x140003989`
- `OLEAUT32!__imp_SysAllocString` at `0x140003be6`
- `OLEAUT32!__imp_SysAllocString` at `0x140003e43`
- `OLEAUT32!__imp_SysFreeString` at `0x140002237`
- `OLEAUT32!__imp_SysFreeString` at `0x140002289`
- `OLEAUT32!__imp_SysFreeString` at `0x1400022e8`
- `OLEAUT32!__imp_SysFreeString` at `0x140002ce3`
- `OLEAUT32!__imp_SysFreeString` at `0x14000300a`
- `OLEAUT32!__imp_SysFreeString` at `0x140003263`
- `OLEAUT32!__imp_SysFreeString` at `0x1400034c0`
- `OLEAUT32!__imp_SysFreeString` at `0x140003719`
- `OLEAUT32!__imp_SysFreeString` at `0x14000399b`
- `OLEAUT32!__imp_SysFreeString` at `0x140003bf8`
- `OLEAUT32!__imp_SysFreeString` at `0x140003e55`
- `OLEAUT32!__imp_SysFreeString` at `0x140002237`
- `OLEAUT32!__imp_SysFreeString` at `0x140002289`
- `OLEAUT32!__imp_SysFreeString` at `0x1400022e8`
- `OLEAUT32!__imp_SysFreeString` at `0x140002ce3`
- `OLEAUT32!__imp_SysFreeString` at `0x14000300a`
- `OLEAUT32!__imp_SysFreeString` at `0x140003263`
- `OLEAUT32!__imp_SysFreeString` at `0x1400034c0`
- `OLEAUT32!__imp_SysFreeString` at `0x140003719`
- `OLEAUT32!__imp_SysFreeString` at `0x14000399b`
- `OLEAUT32!__imp_SysFreeString` at `0x140003bf8`
- `OLEAUT32!__imp_SysFreeString` at `0x140003e55`

## string_xrefs

- `0x140002714`: `LegacyServiceBehavior`
- `0x1400027c4`: `ExeConfig:`
- `0x14000286e`: `MoveFromRepository:`
- `0x1400028c3`: `CopyFromRepository:`
- `0x140002918`: `CopyToRepository:`
- `0x1400044cb`: `Error: Cannot use /ExeConfig with the Ngen Offline feature.`
- `0x1400044f3`: `Error: Cannot specify both /ExeConfig and /AppBase`
- `0x140004563`: `Error: Cannot specify both /ExeConfig and /AppBase`
- `0x14000451b`: `Error: /ExeConfig specified without an executable`
- `0x14000458b`: `Error: /AppBase specified without a valid directory`

## pseudocode

```c
char __fastcall NGenParser::IsCommandLineOption(NGenParser *this, const unsigned __int16 *a2, BSTR *a3, __int64 a4)
{
  BSTR v8; // rbx
  BSTR v9; // rbx
  BSTR v10; // rbx
  __int64 v11; // r9
  __int64 v12; // r9
  __int64 v13; // r9
  __int64 v14; // r9
  __int64 v15; // r9
  __int64 v16; // r9
  __int64 v17; // r9
  int v18; // r15d
  const unsigned __int16 *v19; // rbx
  __int64 v20; // r9
  __int64 v21; // r9
  __int64 v22; // r9
  __int64 v23; // r9
  unsigned __int16 v24; // dx
  unsigned int v25; // r9d
  unsigned int v26; // r9d
  __int64 v27; // rdx
  unsigned int Count; // eax
  bool v29; // r8
  BSTR v30; // rbx
  unsigned int v31; // r9d
  __int64 v32; // rdx
  unsigned int v33; // eax
  bool v34; // r8
  DWORD FileAttributesW; // eax
  BSTR v36; // rbx
  __int64 v37; // rdx
  unsigned int v38; // r9d
  OLECHAR *v39; // rbx
  unsigned int v40; // eax
  BSTR v41; // rbx
  __int64 v42; // rdx
  unsigned int v43; // r9d
  OLECHAR *v44; // rbx
  unsigned int v45; // eax
  BSTR v46; // rbx
  __int64 v47; // rdx
  unsigned int v48; // r9d
  OLECHAR *v49; // rbx
  unsigned int v50; // eax
  BSTR v51; // rbx
  __int64 v52; // rdx
  unsigned int v53; // r9d
  unsigned int v54; // eax
  BSTR v55; // rbx
  __int64 v56; // rdx
  unsigned int v57; // r9d
  unsigned int v58; // eax
  BSTR v59; // rbx
  __int64 v60; // rdx
  unsigned int v61; // eax
  BSTR v62; // rbx
  unsigned int v63; // r9d
  char v64; // cl
  char v65; // cl
  unsigned int v66; // eax
  int v67; // ebx
  int v68; // ebx
  int v69; // ebx
  int v70; // ebx
  int v71; // eax
  const struct SString *v72; // rax
  __int64 v73; // rdx
  const struct SString *v74; // rax
  __int64 v75; // rdx
  const struct SString *v76; // rax
  const struct SString *v77; // rax
  __int64 v78; // rdx
  const struct SString *v79; // rax
  __int64 v80; // rdx
  const struct SString *v81; // rax
  const struct SString *v82; // rax
  const struct SString *v83; // rax
  const struct SString *v84; // rax
  const struct SString *v85; // rax
  const struct SString *v86; // rax
  const struct SString *v87; // rax
  __int64 v88; // rdx
  const struct SString *v89; // rax
  OLECHAR *v90; // [rsp+30h] [rbp-1A28h] BYREF
  __int64 v91; // [rsp+38h] [rbp-1A20h]
  void *v92; // [rsp+40h] [rbp-1A18h]
  __int64 v93; // [rsp+48h] [rbp-1A10h] BYREF
  __int64 *v94; // [rsp+50h] [rbp-1A08h]
  void *lpMem; // [rsp+58h] [rbp-1A00h]
  __int64 *v96; // [rsp+60h] [rbp-19F8h]
  BOOL v97; // [rsp+68h] [rbp-19F0h]
  NGenParser *v98; // [rsp+70h] [rbp-19E8h]
  __int64 *v99; // [rsp+78h] [rbp-19E0h] BYREF
  __int64 *v100; // [rsp+80h] [rbp-19D8h] BYREF
  int v101; // [rsp+90h] [rbp-19C8h] BYREF
  __int64 v102; // [rsp+94h] [rbp-19C4h]
  OLECHAR *String; // [rsp+A0h] [rbp-19B8h]
  __int16 v104; // [rsp+A8h] [rbp-19B0h] BYREF
  int v105; // [rsp+2B0h] [rbp-17A8h] BYREF
  __int64 v106; // [rsp+2B4h] [rbp-17A4h]
  OLECHAR *psz; // [rsp+2C0h] [rbp-1798h]
  _WORD v108[260]; // [rsp+2C8h] [rbp-1790h] BYREF
  int v109; // [rsp+4D0h] [rbp-1588h] BYREF
  __int64 v110; // [rsp+4D4h] [rbp-1584h]
  void *v111; // [rsp+4E0h] [rbp-1578h]
  __int16 v112; // [rsp+4E8h] [rbp-1570h] BYREF
  int v113; // [rsp+6F0h] [rbp-1368h] BYREF
  __int64 v114; // [rsp+6F4h] [rbp-1364h]
  void *v115; // [rsp+700h] [rbp-1358h]
  __int16 v116; // [rsp+708h] [rbp-1350h] BYREF
  int v117; // [rsp+910h] [rbp-1148h] BYREF
  __int64 v118; // [rsp+914h] [rbp-1144h]
  void *v119; // [rsp+920h] [rbp-1138h]
  __int16 v120; // [rsp+928h] [rbp-1130h] BYREF
  int v121; // [rsp+B30h] [rbp-F28h] BYREF
  __int64 v122; // [rsp+B34h] [rbp-F24h]
  void *v123; // [rsp+B40h] [rbp-F18h]
  __int16 v124; // [rsp+B48h] [rbp-F10h] BYREF
  int v125; // [rsp+D50h] [rbp-D08h] BYREF
  __int64 v126; // [rsp+D54h] [rbp-D04h]
  void *v127; // [rsp+D60h] [rbp-CF8h]
  __int16 v128; // [rsp+D68h] [rbp-CF0h] BYREF
  int v129; // [rsp+F70h] [rbp-AE8h] BYREF
  __int64 v130; // [rsp+F74h] [rbp-AE4h]
  void *v131; // [rsp+F80h] [rbp-AD8h]
  __int16 v132; // [rsp+F88h] [rbp-AD0h] BYREF
  int v133; // [rsp+1190h] [rbp-8C8h] BYREF
  __int64 v134; // [rsp+1194h] [rbp-8C4h]
  void *v135; // [rsp+11A0h] [rbp-8B8h]
  __int16 v136; // [rsp+11A8h] [rbp-8B0h] BYREF
  int v137; // [rsp+13B0h] [rbp-6A8h] BYREF
  __int64 v138; // [rsp+13B4h] [rbp-6A4h]
  void *v139; // [rsp+13C0h] [rbp-698h]
  __int16 v140; // [rsp+13C8h] [rbp-690h] BYREF
  int v141; // [rsp+15D0h] [rbp-488h] BYREF
  __int64 v142; // [rsp+15D4h] [rbp-484h]
  void *v143; // [rsp+15E0h] [rbp-478h]
  __int16 v144; // [rsp+15E8h] [rbp-470h] BYREF
  char v145[8]; // [rsp+17F0h] [rbp-268h] BYREF
  char v146; // [rsp+17F8h] [rbp-260h]
  void *v147; // [rsp+1800h] [rbp-258h]

  v98 = this;
  if ( *(_DWORD *)a3 != 4 )
  {
    if ( *(_DWORD *)a3 == 6 )
    {
      if ( !a3[22] )
      {
        v8 = SysAllocString(a2);
        if ( *((_DWORD *)a3 + 46) )
        {
          SysFreeString(a3[22]);
          *((_DWORD *)a3 + 46) = 0;
        }
        a3[22] = v8;
        if ( v8 )
          *((_DWORD *)a3 + 46) = 1;
        return 1;
      }
      if ( !a3[24] )
      {
        v9 = SysAllocString(a2);
        if ( *((_DWORD *)a3 + 50) )
        {
          SysFreeString(a3[24]);
          *((_DWORD *)a3 + 50) = 0;
        }
        a3[24] = v9;
        if ( v9 )
          *((_DWORD *)a3 + 50) = 1;
        return 1;
      }
      if ( *((_DWORD *)a3 + 52) && !a3[27] )
      {
        v10 = SysAllocString(a2);
        if ( *((_DWORD *)a3 + 56) )
        {
          SysFreeString(a3[27]);
          *((_DWORD *)a3 + 56) = 0;
        }
        a3[27] = v10;
        if ( v10 )
          *((_DWORD *)a3 + 56) = 1;
        return 1;
      }
      goto LABEL_44;
    }
    if ( *(_DWORD *)a3 != 5 )
      goto LABEL_44;
    if ( !(unsigned int)SString::CaseCompareHelper(a2, L"scmstart", 0, a4, 1, 0) )
    {
      *((_DWORD *)a3 + 43) = 0;
      return 1;
    }
    if ( !(unsigned int)SString::CaseCompareHelper(a2, L"scmpause", 0, v11, 1, 0) )
    {
      *((_DWORD *)a3 + 43) = 2;
      return 1;
    }
    if ( !(unsigned int)SString::CaseCompareHelper(a2, L"scmstop", 0, v12, 1, 0) )
    {
      *((_DWORD *)a3 + 43) = 1;
      return 1;
    }
    if ( (unsigned int)SString::CaseCompareHelper(a2, L"scmcontinue", 0, v13, 1, 0) )
    {
      if ( !(unsigned int)SString::CaseCompareHelper(a2, L"scmstatus", 0, v14, 1, 0) )
        goto LABEL_42;
      if ( !(unsigned int)SString::CaseCompareHelper(a2, L"pause", 0, v15, 1, 0) )
      {
        *((_DWORD *)a3 + 43) = 5;
        return 1;
      }
      if ( (unsigned int)SString::CaseCompareHelper(a2, L"continue", 0, v16, 1, 0) )
      {
        if ( (unsigned int)SString::CaseCompareHelper(a2, L"status", 0, v17, 1, 0) )
          goto LABEL_44;
LABEL_42:
        *((_DWORD *)a3 + 43) = 4;
        return 1;
      }
    }
    *((_DWORD *)a3 + 43) = 3;
    return 1;
  }
  switch ( *a2 )
  {
    case '0':
      *((_DWORD *)a3 + 42) = 0;
      return 1;
    case '1':
      *((_DWORD *)a3 + 42) = 1;
      return 1;
    case '2':
      *((_DWORD *)a3 + 42) = 2;
      return 1;
    case '3':
      *((_DWORD *)a3 + 42) = 3;
      return 1;
  }
LABEL_44:
  if ( ((*a2 - 45) & 0xFFFD) == 0 )
  {
    v18 = 2;
    v19 = a2 + 1;
    if ( !(unsigned int)SString::CaseCompareHelper(v19, L"Silent", 0, a4, 1, 0) )
    {
      *((_DWORD *)a3 + 41) = 1;
      return 1;
    }
    if ( !(unsigned int)SString::CaseCompareHelper(v19, L"Verbose", 0, v20, 1, 0) )
    {
      *((_DWORD *)a3 + 41) = 3;
      return 1;
    }
    if ( *(_DWORD *)a3 == 2 )
    {
      if ( !(unsigned int)SString::CaseCompareHelper(v19, L"Force", 0, v21, 1, 0) )
      {
        *((_DWORD *)a3 + 7) |= 1u;
        return 1;
      }
      if ( *(_DWORD *)a3 == 2 && !_wcsicmp(v19, L"Postreboot") )
      {
        *((_DWORD *)a3 + 42) = 3;
        *((_DWORD *)a3 + 7) |= 2u;
        return 1;
      }
    }
    if ( (*(_DWORD *)a3 & 0xFFFFFFFD) == 0 && !(unsigned int)SString::CaseCompareHelper(v19, L"Queue", 0, v21, 1, 0) )
      goto LABEL_65;
    if ( !*(_DWORD *)a3 )
    {
      if ( !(unsigned int)SString::CaseCompareHelper(v19, L"Queue:1", 0, v21, 1, 0) )
      {
        *((_DWORD *)a3 + 36) = 1;
        *((_DWORD *)a3 + 42) = 1;
        return 1;
      }
      if ( !*(_DWORD *)a3 )
      {
        if ( !(unsigned int)SString::CaseCompareHelper(v19, L"Queue:2", 0, v21, 1, 0) )
        {
          *((_DWORD *)a3 + 36) = 1;
          *((_DWORD *)a3 + 42) = 2;
          return 1;
        }
        if ( !*(_DWORD *)a3 && !(unsigned int)SString::CaseCompareHelper(v19, L"Queue:3", 0, v21, 1, 0) )
        {
LABEL_65:
          *((_DWORD *)a3 + 36) = 1;
          *((_DWORD *)a3 + 42) = 3;
          return 1;
        }
      }
    }
    if ( *(_DWORD *)a3 == 2 && !(unsigned int)SString::CaseCompareHelper(v19, L"Delay", 0, v21, 1, 0) )
    {
      *((_DWORD *)a3 + 37) = 1;
      return 1;
    }
    if ( !*(_DWORD *)a3 && !(unsigned int)SString::CaseCompareHelper(v19, L"NetfxPri1", 0, v21, 1, 0) )
    {
      *((_DWORD *)a3 + 8) |= 2u;
      return 1;
    }
    if ( *(_DWORD *)a3 == 6 && !(unsigned int)SString::CaseCompareHelper(v19, L"lines", 0, v21, 1, 0) )
    {
      *((_DWORD *)a3 + 52) = 1;
      return 1;
    }
    if ( !(unsigned int)SString::CaseCompareHelper(v19, L"NoLogo", 0, v21, 1, 0) )
    {
      *((_DWORD *)a3 + 39) = 1;
      return 1;
    }
    if ( !(unsigned int)SString::CaseCompareHelper(v19, L"NoRoot", 0, v22, 1, 0) )
    {
      *((_DWORD *)a3 + 8) |= 4u;
      return 1;
    }
    if ( !(unsigned int)SString::CaseCompareHelper(v19, L"LegacyServiceBehavior", 0, v23, 1, 0) )
    {
      *((_DWORD *)a3 + 40) = 1;
      return 1;
    }
    v102 = 512;
    String = (OLECHAR *)&v104;
    v101 = 2;
    v104 = 0;
    ((void (__stdcall *)(SString *, const unsigned __int16 *))SString::Set)((SString *)&v101, v19);
    v142 = 512;
    v143 = &v144;
    v141 = 2;
    v144 = 0;
    ((void (__stdcall *)(SString *, const unsigned __int16 *))SString::Set)((SString *)&v141, L"ExeConfig:");
    v138 = 512;
    v139 = &v140;
    v137 = 2;
    v140 = 0;
    ((void (__stdcall *)(SString *, const unsigned __int16 *))SString::Set)((SString *)&v137, L"AppBase:");
    v134 = 512;
    v135 = &v136;
    v133 = 2;
    v136 = 0;
    ((void (__stdcall *)(SString *, const unsigned __int16 *))SString::Set)((SString *)&v133, L"MoveFromRepository:");
    v130 = 512;
    v131 = &v132;
    v129 = 2;
    v132 = 0;
    ((void (__stdcall *)(SString *, const unsigned __int16 *))SString::Set)((SString *)&v129, L"CopyFromRepository:");
    v126 = 512;
    v127 = &v128;
    v125 = 2;
    v128 = 0;
    ((void (__stdcall *)(SString *, const unsigned __int16 *))SString::Set)((SString *)&v125, L"CopyToRepository:");
    v122 = 512;
    v123 = &v124;
    v121 = 2;
    v124 = 0;
    ((void (__stdcall *)(SString *, const unsigned __int16 *))SString::Set)((SString *)&v121, L"Version:");
    v118 = 512;
    v119 = &v120;
    v117 = 2;
    v120 = 0;
    ((void (__stdcall *)(SString *, const unsigned __int16 *))SString::Set)((SString *)&v117, L"Package:");
    v114 = 512;
    v115 = &v116;
    v113 = 2;
    v116 = 0;
    ((void (__stdcall *)(SString *, const unsigned __int16 *))SString::Set)((SString *)&v113, L"LocalAppData:");
    v110 = 512;
    v111 = &v112;
    v109 = 2;
    v112 = 0;
    ((void (__stdcall *)(SString *, const unsigned __int16 *))SString::Set)((SString *)&v109, L"Stats");
    InlineSString<512>::InlineSString<512>(v145, &v109);
    v93 = 0x200000002LL;
    LODWORD(v94) = 16;
    lpMem = (void *)&SString::s_EmptyBuffer;
    SString::Set((SString *)&v93, v24);
    SString::Append((SString *)v145, (const struct SString *)&v93);
    if ( ((unsigned __int8)v94 & 8) != 0 )
      operator delete(lpMem);
    if ( (~(HIDWORD(v102) >> 1) & 1) == 0 && !(unsigned int)SString::ScanASCII((SString *)&v101) )
      SString::ConvertToUnicode((SString *)&v101);
    if ( (v102 & 0x1000000000LL) != 0 )
      SBuffer::ReallocateBuffer((const void **)&v101, v102, 1);
    v90 = String;
    LODWORD(v91) = (v102 & 0x100000000LL) == 0;
    if ( (unsigned int)SString::MatchCaseInsensitive(
                         (SString *)&v101,
                         (const struct SString::CIterator *)&v90,
                         (const struct SString *)&v141,
                         v25) )
    {
      if ( IsNgenOffline() )
      {
        v72 = (const struct SString *)SString::SString(
                                        &v90,
                                        v27,
                                        L"Error: Cannot use /ExeConfig with the Ngen Offline feature.");
        ((void (__stdcall __noreturn *)(int, const struct SString *))ThrowHR)(-2147024809, v72);
      }
      if ( a3[5] )
      {
        NGenParser::PrintLogoHelper(this);
        v74 = (const struct SString *)SString::SString(&v90, v73, L"Error: Cannot specify both /ExeConfig and /AppBase");
        ((void (__stdcall __noreturn *)(int, const struct SString *))ThrowHR)(-2147024809, v74);
      }
      if ( (~(HIDWORD(v102) >> 1) & 1) == 0 && !(unsigned int)SString::ScanASCII((SString *)&v101) )
        SString::ConvertToUnicode((SString *)&v101);
      if ( (v102 & 0x1000000000LL) != 0 )
        SBuffer::ReallocateBuffer((const void **)&v101, v102, 1);
      v90 = String;
      LODWORD(v91) = (v102 & 0x100000000LL) == 0;
      Count = SString::GetCount((SString *)&v141);
      SString::Replace(
        (SString *)&v101,
        (const struct SString::Iterator *)&v90,
        Count,
        *(const struct SString **)&SString::s_Empty);
      SString::ConvertToUnicode((SString *)&v101);
      if ( !(unsigned int)IsExe(String) )
      {
        NGenParser::PrintLogoHelper(this);
        v76 = (const struct SString *)SString::SString(&v90, v75, L"Error: /ExeConfig specified without an executable");
        ((void (__stdcall __noreturn *)(int, const struct SString *))ThrowHR)(-2147024809, v76);
      }
      v106 = 512;
      psz = v108;
      v105 = 2;
      v108[0] = 0;
      LODWORD(v93) = 0;
      v94 = 0;
      if ( __eh34_try(-1, 0) )
      {
        __eh34_scope_strut(0);
        if ( __eh34_try(0, 1) )
        {
          __eh34_scope_strut(1);
          v96 = &v93;
          SString::ConvertToUnicode((SString *)&v101);
          CanonicalizePath(String, (struct SString *)&v105, 1);
        }
        if ( __eh34_catch(1) )
        {
          if ( __eh34_catch_type(1, &Exception * `RTTI Type Descriptor', (Exception **)&v99) )
          {
            Exception::HandlerState::SetCaughtCxx((Exception::HandlerState *)&v93);
            v94 = v99;
            throw;
          }
        }
      }
      if ( __eh34_catch(0) )
      {
        if ( __eh34_catch_ellipsis(0) )
        {
          v91 = 0;
          v90 = (OLECHAR *)&DelegatingException::`vftable';
          v92 = (void *)-1LL;
          v96 = v94;
          v97 = v94 != 0;
          ((void (__fastcall *)(Exception::HandlerState *, int, bool))Exception::HandlerState::SetupCatch)(
            (Exception::HandlerState *)&v93,
            505,
            v29);
          NGenParser::PrintLogoHelper(v98);
          v97 = 0;
          throw;
        }
      }
      SString::ConvertToUnicode((SString *)&v105);
      v30 = SysAllocString(psz);
      if ( *((_DWORD *)a3 + 12) )
      {
        SysFreeString(a3[5]);
        *((_DWORD *)a3 + 12) = 0;
      }
      a3[5] = v30;
      if ( v30 )
        *((_DWORD *)a3 + 12) = 1;
      if ( (v106 & 0x800000000LL) != 0 )
        operator delete(psz);
      if ( (v146 & 8) != 0 )
        operator delete(v147);
      if ( (v110 & 0x800000000LL) != 0 )
        operator delete(v111);
      if ( (v114 & 0x800000000LL) != 0 )
        operator delete(v115);
      if ( (v118 & 0x800000000LL) != 0 )
        operator delete(v119);
      if ( (v122 & 0x800000000LL) != 0 )
        operator delete(v123);
      if ( (v126 & 0x800000000LL) != 0 )
        operator delete(v127);
      if ( (v130 & 0x800000000LL) != 0 )
        operator delete(v131);
      if ( (v134 & 0x800000000LL) != 0 )
        operator delete(v135);
      if ( (v138 & 0x800000000LL) != 0 )
        operator delete(v139);
      if ( (v142 & 0x800000000LL) != 0 )
        operator delete(v143);
LABEL_447:
      if ( (v102 & 0x800000000LL) != 0 )
        operator delete(String);
      return 1;
    }
    if ( (~(HIDWORD(v102) >> 1) & 1) == 0 && !(unsigned int)SString::ScanASCII((SString *)&v101) )
      SString::ConvertToUnicode((SString *)&v101);
    if ( (v102 & 0x1000000000LL) != 0 )
      SBuffer::ReallocateBuffer((const void **)&v101, v102, 1);
    v90 = String;
    LODWORD(v91) = (v102 & 0x100000000LL) == 0;
    if ( (unsigned int)SString::MatchCaseInsensitive(
                         (SString *)&v101,
                         (const struct SString::CIterator *)&v90,
                         (const struct SString *)&v137,
                         v26) )
    {
      if ( IsNgenOffline() )
      {
        v77 = (const struct SString *)SString::SString(
                                        &v90,
                                        v32,
                                        L"Error: Cannot use /AppBase with the Ngen Offline feature.");
        ((void (__stdcall __noreturn *)(int, const struct SString *))ThrowHR)(-2147024809, v77);
      }
      if ( a3[5] )
      {
        NGenParser::PrintLogoHelper(this);
        v79 = (const struct SString *)SString::SString(&v90, v78, L"Error: Cannot specify both /ExeConfig and /AppBase");
        ((void (__stdcall __noreturn *)(int, const struct SString *))ThrowHR)(-2147024809, v79);
      }
      if ( (~(HIDWORD(v102) >> 1) & 1) == 0 && !(unsigned int)SString::ScanASCII((SString *)&v101) )
        SString::ConvertToUnicode((SString *)&v101);
      if ( (v102 & 0x1000000000LL) != 0 )
        SBuffer::ReallocateBuffer((const void **)&v101, v102, 1);
      v90 = String;
      LODWORD(v91) = (v102 & 0x100000000LL) == 0;
      v33 = SString::GetCount((SString *)&v137);
      SString::Replace(
        (SString *)&v101,
        (const struct SString::Iterator *)&v90,
        v33,
        *(const struct SString **)&SString::s_Empty);
      v106 = 512;
      psz = v108;
      v105 = 2;
      v108[0] = 0;
      LODWORD(v93) = 0;
      v94 = 0;
      if ( __eh34_try(-1, 4) )
      {
        __eh34_scope_strut(4);
        if ( __eh34_try(4, 5) )
        {
          __eh34_scope_strut(5);
          v96 = &v93;
          SString::ConvertToUnicode((SString *)&v101);
          CanonicalizePathAux(String, (struct SString *)&v105, 1);
        }
        if ( __eh34_catch(5) )
        {
          if ( __eh34_catch_type(5, &Exception * `RTTI Type Descriptor', (Exception **)&v100) )
          {
            Exception::HandlerState::SetCaughtCxx((Exception::HandlerState *)&v93);
            v94 = v100;
            throw;
          }
        }
      }
      if ( __eh34_catch(4) )
      {
        if ( __eh34_catch_ellipsis(4) )
        {
          v91 = 0;
          v90 = (OLECHAR *)&DelegatingException::`vftable';
          v92 = (void *)-1LL;
          v96 = v94;
          v97 = v94 != 0;
          ((void (__fastcall *)(Exception::HandlerState *, int, bool))Exception::HandlerState::SetupCatch)(
            (Exception::HandlerState *)&v93,
            535,
            v34);
          NGenParser::PrintLogoHelper(v98);
          v97 = 0;
          throw;
        }
      }
      SString::ConvertToUnicode((SString *)&v105);
      FileAttributesW = GetFileAttributesW(psz);
      if ( FileAttributesW == -1 || (FileAttributesW & 0x10) == 0 )
      {
        NGenParser::PrintLogoHelper(this);
        v81 = (const struct SString *)SString::SString(
                                        &v90,
                                        v80,
                                        L"Error: /AppBase specified without a valid directory");
        ((void (__stdcall __noreturn *)(int, const struct SString *))ThrowHR)(-2147024809, v81);
      }
      SString::ConvertToUnicode((SString *)&v105);
      v36 = SysAllocString(psz);
      if ( *((_DWORD *)a3 + 12) )
      {
        SysFreeString(a3[5]);
        *((_DWORD *)a3 + 12) = 0;
      }
      a3[5] = v36;
      if ( v36 )
        *((_DWORD *)a3 + 12) = 1;
      if ( (v106 & 0x800000000LL) != 0 )
        operator delete(psz);
      if ( (v146 & 8) != 0 )
        operator delete(v147);
      if ( (v110 & 0x800000000LL) != 0 )
        operator delete(v111);
      if ( (v114 & 0x800000000LL) != 0 )
        operator delete(v115);
      if ( (v118 & 0x800000000LL) != 0 )
        operator delete(v119);
      if ( (v122 & 0x800000000LL) != 0 )
        operator delete(v123);
      if ( (v126 & 0x800000000LL) != 0 )
        operator delete(v127);
      if ( (v130 & 0x800000000LL) != 0 )
        operator delete(v131);
      if ( (v134 & 0x800000000LL) != 0 )
        operator delete(v135);
      if ( (v138 & 0x800000000LL) != 0 )
        operator delete(v139);
      if ( (v142 & 0x800000000LL) != 0 )
        operator delete(v143);
      goto LABEL_447;
    }
    if ( (~(HIDWORD(v102) >> 1) & 1) == 0 && !(unsigned int)SString::ScanASCII((SString *)&v101) )
      SString::ConvertToUnicode((SString *)&v101);
    if ( (v102 & 0x1000000000LL) != 0 )
      SBuffer::ReallocateBuffer((const void **)&v101, v102, 1);
    v90 = String;
    LODWORD(v91) = (v102 & 0x100000000LL) == 0;
    if ( (unsigned int)SString::MatchCaseInsensitive(
                         (SString *)&v101,
                         (const struct SString::CIterator *)&v90,
                         (const struct SString *)&v133,
                         v31) )
    {
      if ( a3[7] )
      {
        v82 = (const struct SString *)SString::SString(&v90, v37, L"Error: Cannot specify multiple repository options");
        ((void (__stdcall __noreturn *)(int, const struct SString *))ThrowHR)(-2147024809, v82);
      }
      v106 = 512;
      psz = v108;
      v105 = 2;
      v108[0] = 0;
      SString::ConvertToUnicode((SString *)&v101);
      v39 = String;
      v40 = SString::GetCount((SString *)&v133);
      CanonicalizePathAux(&v39[v40], (struct SString *)&v105, 0);
      SString::ConvertToUnicode((SString *)&v105);
      v41 = SysAllocString(psz);
      if ( *((_DWORD *)a3 + 16) )
      {
        SysFreeString(a3[7]);
        *((_DWORD *)a3 + 16) = 0;
      }
      a3[7] = v41;
      if ( v41 )
        *((_DWORD *)a3 + 16) = 1;
      *((_DWORD *)a3 + 18) |= 1u;
      if ( (v106 & 0x800000000LL) != 0 )
        operator delete(psz);
      if ( (v146 & 8) != 0 )
        operator delete(v147);
      if ( (v110 & 0x800000000LL) != 0 )
        operator delete(v111);
      if ( (v114 & 0x800000000LL) != 0 )
        operator delete(v115);
      if ( (v118 & 0x800000000LL) != 0 )
        operator delete(v119);
      if ( (v122 & 0x800000000LL) != 0 )
        operator delete(v123);
      if ( (v126 & 0x800000000LL) != 0 )
        operator delete(v127);
      if ( (v130 & 0x800000000LL) != 0 )
        operator delete(v131);
      if ( (v134 & 0x800000000LL) != 0 )
        operator delete(v135);
      if ( (v138 & 0x800000000LL) != 0 )
        operator delete(v139);
      if ( (v142 & 0x800000000LL) != 0 )
        operator delete(v143);
      goto LABEL_447;
    }
    if ( (~(HIDWORD(v102) >> 1) & 1) == 0 && !(unsigned int)SString::ScanASCII((SString *)&v101) )
      SString::ConvertToUnicode((SString *)&v101);
    if ( (v102 & 0x1000000000LL) != 0 )
      SBuffer::ReallocateBuffer((const void **)&v101, v102, 1);
    v90 = String;
    LODWORD(v91) = (v102 & 0x100000000LL) == 0;
    if ( (unsigned int)SString::MatchCaseInsensitive(
                         (SString *)&v101,
                         (const struct SString::CIterator *)&v90,
                         (const struct SString *)&v129,
                         v38) )
    {
      if ( a3[7] )
      {
        v83 = (const struct SString *)SString::SString(&v90, v42, L"Error: Cannot specify multiple repository options");
        ((void (__stdcall __noreturn *)(int, const struct SString *))ThrowHR)(-2147024809, v83);
      }
      v106 = 512;
      psz = v108;
      v105 = 2;
      v108[0] = 0;
      SString::ConvertToUnicode((SString *)&v101);
      v44 = String;
      v45 = SString::GetCount((SString *)&v129);
      CanonicalizePathAux(&v44[v45], (struct SString *)&v105, 0);
      SString::ConvertToUnicode((SString *)&v105);
      v46 = SysAllocString(psz);
      if ( *((_DWORD *)a3 + 16) )
      {
        SysFreeString(a3[7]);
        *((_DWORD *)a3 + 16) = 0;
      }
      a3[7] = v46;
      if ( v46 )
        *((_DWORD *)a3 + 16) = 1;
      if ( (v106 & 0x800000000LL) != 0 )
        operator delete(psz);
      if ( (v146 & 8) != 0 )
        operator delete(v147);
      if ( (v110 & 0x800000000LL) != 0 )
        operator delete(v111);
      if ( (v114 & 0x800000000LL) != 0 )
        operator delete(v115);
      if ( (v118 & 0x800000000LL) != 0 )
        operator delete(v119);
      if ( (v122 & 0x800000000LL) != 0 )
        operator delete(v123);
      if ( (v126 & 0x800000000LL) != 0 )
        operator delete(v127);
      if ( (v130 & 0x800000000LL) != 0 )
        operator delete(v131);
      if ( (v134 & 0x800000000LL) != 0 )
        operator delete(v135);
      if ( (v138 & 0x800000000LL) != 0 )
        operator delete(v139);
      if ( (v142 & 0x800000000LL) != 0 )
        operator delete(v143);
      goto LABEL_447;
    }
    if ( (~(HIDWORD(v102) >> 1) & 1) == 0 && !(unsigned int)SString::ScanASCII((SString *)&v101) )
      SString::ConvertToUnicode((SString *)&v101);
    if ( (v102 & 0x1000000000LL) != 0 )
      SBuffer::ReallocateBuffer((const void **)&v101, v102, 1);
    v90 = String;
    LODWORD(v91) = (v102 & 0x100000000LL) == 0;
    if ( (unsigned int)SString::MatchCaseInsensitive(
                         (SString *)&v101,
                         (const struct SString::CIterator *)&v90,
                         (const struct SString *)&v125,
                         v43) )
    {
      if ( a3[7] )
      {
        v84 = (const struct SString *)SString::SString(&v90, v47, L"Error: Cannot specify multiple repository options");
        ((void (__stdcall __noreturn *)(int, const struct SString *))ThrowHR)(-2147024809, v84);
      }
      v106 = 512;
      psz = v108;
      v105 = 2;
      v108[0] = 0;
      SString::ConvertToUnicode((SString *)&v101);
      v49 = String;
      v50 = SString::GetCount((SString *)&v125);
      CanonicalizePathAux(&v49[v50], (struct SString *)&v105, 1);
      SString::ConvertToUnicode((SString *)&v105);
      v51 = SysAllocString(psz);
      if ( *((_DWORD *)a3 + 16) )
      {
        SysFreeString(a3[7]);
        *((_DWORD *)a3 + 16) = 0;
      }
      a3[7] = v51;
      if ( v51 )
        *((_DWORD *)a3 + 16) = 1;
      *((_DWORD *)a3 + 18) |= 2u;
      if ( *(_DWORD *)a3 == 2 )
        *((_DWORD *)a3 + 7) |= 1u;
      if ( (v106 & 0x800000000LL) != 0 )
        operator delete(psz);
      if ( (v146 & 8) != 0 )
        operator delete(v147);
      if ( (v110 & 0x800000000LL) != 0 )
        operator delete(v111);
      if ( (v114 & 0x800000000LL) != 0 )
        operator delete(v115);
      if ( (v118 & 0x800000000LL) != 0 )
        operator delete(v119);
      if ( (v122 & 0x800000000LL) != 0 )
        operator delete(v123);
      if ( (v126 & 0x800000000LL) != 0 )
        operator delete(v127);
      if ( (v130 & 0x800000000LL) != 0 )
        operator delete(v131);
      if ( (v134 & 0x800000000LL) != 0 )
        operator delete(v135);
      if ( (v138 & 0x800000000LL) != 0 )
        operator delete(v139);
      if ( (v142 & 0x800000000LL) != 0 )
        operator delete(v143);
      goto LABEL_447;
    }
    if ( (~(HIDWORD(v102) >> 1) & 1) == 0 && !(unsigned int)SString::ScanASCII((SString *)&v101) )
      SString::ConvertToUnicode((SString *)&v101);
    if ( (v102 & 0x1000000000LL) != 0 )
      SBuffer::ReallocateBuffer((const void **)&v101, v102, 1);
    v90 = String;
    LODWORD(v91) = (v102 & 0x100000000LL) == 0;
    if ( (unsigned int)SString::MatchCaseInsensitive(
                         (SString *)&v101,
                         (const struct SString::CIterator *)&v90,
                         (const struct SString *)&v121,
                         v48) )
    {
      if ( a3[10] )
      {
        v85 = (const struct SString *)SString::SString(&v90, v52, L"Error: Cannot specify multiple runtime versions");
        ((void (__stdcall __noreturn *)(int, const struct SString *))ThrowHR)(-2147024809, v85);
      }
      if ( (~(HIDWORD(v102) >> 1) & 1) == 0 && !(unsigned int)SString::ScanASCII((SString *)&v101) )
        SString::ConvertToUnicode((SString *)&v101);
      if ( (v102 & 0x1000000000LL) != 0 )
        SBuffer::ReallocateBuffer((const void **)&v101, v102, 1);
      v90 = String;
      LODWORD(v91) = (v102 & 0x100000000LL) == 0;
      v54 = SString::GetCount((SString *)&v121);
      SString::Replace(
        (SString *)&v101,
        (const struct SString::Iterator *)&v90,
        v54,
        *(const struct SString **)&SString::s_Empty);
      SString::ConvertToUnicode((SString *)&v101);
      v55 = SysAllocString(String);
      if ( *((_DWORD *)a3 + 22) )
      {
        SysFreeString(a3[10]);
        *((_DWORD *)a3 + 22) = 0;
      }
      a3[10] = v55;
      if ( v55 )
        *((_DWORD *)a3 + 22) = 1;
      if ( (v146 & 8) != 0 )
        operator delete(v147);
      if ( (v110 & 0x800000000LL) != 0 )
        operator delete(v111);
      if ( (v114 & 0x800000000LL) != 0 )
        operator delete(v115);
      if ( (v118 & 0x800000000LL) != 0 )
        operator delete(v119);
      if ( (v122 & 0x800000000LL) != 0 )
        operator delete(v123);
      if ( (v126 & 0x800000000LL) != 0 )
        operator delete(v127);
      if ( (v130 & 0x800000000LL) != 0 )
        operator delete(v131);
      if ( (v134 & 0x800000000LL) != 0 )
        operator delete(v135);
      if ( (v138 & 0x800000000LL) != 0 )
        operator delete(v139);
      if ( (v142 & 0x800000000LL) != 0 )
        operator delete(v143);
      goto LABEL_447;
    }
    if ( (~(HIDWORD(v102) >> 1) & 1) == 0 && !(unsigned int)SString::ScanASCII((SString *)&v101) )
      SString::ConvertToUnicode((SString *)&v101);
    if ( (v102 & 0x1000000000LL) != 0 )
      SBuffer::ReallocateBuffer((const void **)&v101, v102, 1);
    v90 = String;
    LODWORD(v91) = (v102 & 0x100000000LL) == 0;
    if ( (unsigned int)SString::MatchCaseInsensitive(
                         (SString *)&v101,
                         (const struct SString::CIterator *)&v90,
                         (const struct SString *)&v117,
                         v53) )
    {
      if ( a3[12] )
      {
        v86 = (const struct SString *)SString::SString(&v90, v56, L"Error: Cannot specify multiple package monikers");
        ((void (__stdcall __noreturn *)(int, const struct SString *))ThrowHR)(-2147024809, v86);
      }
      if ( (~(HIDWORD(v102) >> 1) & 1) == 0 && !(unsigned int)SString::ScanASCII((SString *)&v101) )
        SString::ConvertToUnicode((SString *)&v101);
      if ( (v102 & 0x1000000000LL) != 0 )
        SBuffer::ReallocateBuffer((const void **)&v101, v102, 1);
      v90 = String;
      LODWORD(v91) = (v102 & 0x100000000LL) == 0;
      v58 = SString::GetCount((SString *)&v117);
      SString::Replace(
        (SString *)&v101,
        (const struct SString::Iterator *)&v90,
        v58,
        *(const struct SString **)&SString::s_Empty);
      SString::ConvertToUnicode((SString *)&v101);
      v59 = SysAllocString(String);
      if ( *((_DWORD *)a3 + 26) )
      {
        SysFreeString(a3[12]);
        *((_DWORD *)a3 + 26) = 0;
      }
      a3[12] = v59;
      if ( v59 )
        *((_DWORD *)a3 + 26) = 1;
      if ( (v146 & 8) != 0 )
        operator delete(v147);
      if ( (v110 & 0x800000000LL) != 0 )
        operator delete(v111);
      if ( (v114 & 0x800000000LL) != 0 )
        operator delete(v115);
      if ( (v118 & 0x800000000LL) != 0 )
        operator delete(v119);
      if ( (v122 & 0x800000000LL) != 0 )
        operator delete(v123);
      if ( (v126 & 0x800000000LL) != 0 )
        operator delete(v127);
      if ( (v130 & 0x800000000LL) != 0 )
        operator delete(v131);
      if ( (v134 & 0x800000000LL) != 0 )
        operator delete(v135);
      if ( (v138 & 0x800000000LL) != 0 )
        operator delete(v139);
      if ( (v142 & 0x800000000LL) != 0 )
        operator delete(v143);
      goto LABEL_447;
    }
    if ( (~(HIDWORD(v102) >> 1) & 1) == 0 && !(unsigned int)SString::ScanASCII((SString *)&v101) )
      SString::ConvertToUnicode((SString *)&v101);
    if ( (v102 & 0x1000000000LL) != 0 )
      SBuffer::ReallocateBuffer((const void **)&v101, v102, 1);
    v90 = String;
    LODWORD(v91) = (v102 & 0x100000000LL) == 0;
    if ( (unsigned int)SString::MatchCaseInsensitive(
                         (SString *)&v101,
                         (const struct SString::CIterator *)&v90,
                         (const struct SString *)&v113,
                         v57) )
    {
      if ( a3[14] )
      {
        v87 = (const struct SString *)SString::SString(
                                        &v90,
                                        v60,
                                        L"Error: Cannot specify multiple localappdata directories");
        ((void (__stdcall __noreturn *)(int, const struct SString *))ThrowHR)(-2147024809, v87);
      }
      if ( (~(HIDWORD(v102) >> 1) & 1) == 0 && !(unsigned int)SString::ScanASCII((SString *)&v101) )
        SString::ConvertToUnicode((SString *)&v101);
      if ( (v102 & 0x1000000000LL) != 0 )
        SBuffer::ReallocateBuffer((const void **)&v101, v102, 1);
      v90 = String;
      LODWORD(v91) = (v102 & 0x100000000LL) == 0;
      v61 = SString::GetCount((SString *)&v113);
      SString::Replace(
        (SString *)&v101,
        (const struct SString::Iterator *)&v90,
        v61,
        *(const struct SString **)&SString::s_Empty);
      SString::ConvertToUnicode((SString *)&v101);
      v62 = SysAllocString(String);
      if ( *((_DWORD *)a3 + 30) )
      {
        SysFreeString(a3[14]);
        *((_DWORD *)a3 + 30) = 0;
      }
      a3[14] = v62;
      if ( v62 )
        *((_DWORD *)a3 + 30) = 1;
      if ( (v146 & 8) != 0 )
        operator delete(v147);
      if ( (v110 & 0x800000000LL) != 0 )
        operator delete(v111);
      if ( (v114 & 0x800000000LL) != 0 )
        operator delete(v115);
      if ( (v118 & 0x800000000LL) != 0 )
        operator delete(v119);
      if ( (v122 & 0x800000000LL) != 0 )
        operator delete(v123);
      if ( (v126 & 0x800000000LL) != 0 )
        operator delete(v127);
      if ( (v130 & 0x800000000LL) != 0 )
        operator delete(v131);
      if ( (v134 & 0x800000000LL) != 0 )
        operator delete(v135);
      if ( (v138 & 0x800000000LL) != 0 )
        operator delete(v139);
      if ( (v142 & 0x800000000LL) != 0 )
        operator delete(v143);
      goto LABEL_447;
    }
    if ( (unsigned int)SString::EqualsCaseInsensitive((SString *)&v101, (const struct SString *)&v109) )
    {
      *((_DWORD *)a3 + 33) = 1;
      if ( (v146 & 8) != 0 )
        operator delete(v147);
      if ( (v110 & 0x800000000LL) != 0 )
        operator delete(v111);
      if ( (v114 & 0x800000000LL) != 0 )
        operator delete(v115);
      if ( (v118 & 0x800000000LL) != 0 )
        operator delete(v119);
      if ( (v122 & 0x800000000LL) != 0 )
        operator delete(v123);
      if ( (v126 & 0x800000000LL) != 0 )
        operator delete(v127);
      if ( (v130 & 0x800000000LL) != 0 )
        operator delete(v131);
      if ( (v134 & 0x800000000LL) != 0 )
        operator delete(v135);
      if ( (v138 & 0x800000000LL) != 0 )
        operator delete(v139);
      if ( (v142 & 0x800000000LL) != 0 )
        operator delete(v143);
      goto LABEL_447;
    }
    SString::ConvertToIteratable((SString *)&v101);
    v64 = BYTE4(v102);
    if ( (v102 & 0x1000000000LL) != 0 )
    {
      SBuffer::ReallocateBuffer((const void **)&v101, v102, 1);
      v64 = BYTE4(v102);
    }
    v90 = String;
    LODWORD(v91) = (v64 & 1) == 0;
    if ( (unsigned int)SString::MatchCaseInsensitive(
                         (SString *)&v101,
                         (const struct SString::CIterator *)&v90,
                         (const struct SString *)v145,
                         v63) )
    {
      SString::ConvertToIteratable((SString *)&v101);
      v65 = BYTE4(v102);
      if ( (v102 & 0x1000000000LL) != 0 )
      {
        SBuffer::ReallocateBuffer((const void **)&v101, v102, 1);
        v65 = BYTE4(v102);
      }
      v93 = (__int64)String;
      LODWORD(v94) = (v65 & 1) == 0;
      v66 = SString::GetCount((SString *)v145);
      SString::Replace(
        (SString *)&v101,
        (const struct SString::Iterator *)&v93,
        v66,
        *(const struct SString **)&SString::s_Empty);
      SString::SString((SString *)&v90, L"fixups");
      v67 = SString::EqualsCaseInsensitive((SString *)&v101, (const struct SString *)&v90);
      if ( (v91 & 8) != 0 )
        operator delete(v92);
      if ( !v67 )
      {
        SString::SString((SString *)&v90, L"calls");
        v68 = SString::EqualsCaseInsensitive((SString *)&v101, (const struct SString *)&v90);
        if ( (v91 & 8) != 0 )
          operator delete(v92);
        if ( v68 )
        {
          v18 = 4;
        }
        else
        {
          SString::SString((SString *)&v90, L"attributed");
          v69 = SString::EqualsCaseInsensitive((SString *)&v101, (const struct SString *)&v90);
          if ( (v91 & 8) != 0 )
            operator delete(v92);
          if ( v69 )
          {
            v18 = 8;
          }
          else
          {
            SString::SString((SString *)&v90, L"all");
            v70 = SString::EqualsCaseInsensitive((SString *)&v101, (const struct SString *)&v90);
            if ( (v91 & 8) != 0 )
              operator delete(v92);
            if ( v70 )
            {
              v18 = -1;
            }
            else
            {
              SString::ConvertToUnicode((SString *)&v101);
              v71 = _wtoi(String);
              if ( !v71 )
              {
                NGenParser::PrintLogoHelper(this);
                v89 = (const struct SString *)SString::SString(
                                                &v90,
                                                v88,
                                                L"Error: Unrecognized option used for /Stats:<option>");
                ((void (__stdcall __noreturn *)(int, const struct SString *))ThrowHR)(-2147024809, v89);
              }
              v18 = v71;
            }
          }
        }
      }
      *((_DWORD *)a3 + 33) = v18;
      if ( (v146 & 8) != 0 )
        operator delete(v147);
      if ( (v110 & 0x800000000LL) != 0 )
        operator delete(v111);
      if ( (v114 & 0x800000000LL) != 0 )
        operator delete(v115);
      if ( (v118 & 0x800000000LL) != 0 )
        operator delete(v119);
      if ( (v122 & 0x800000000LL) != 0 )
        operator delete(v123);
      if ( (v126 & 0x800000000LL) != 0 )
        operator delete(v127);
      if ( (v130 & 0x800000000LL) != 0 )
        operator delete(v131);
      if ( (v134 & 0x800000000LL) != 0 )
        operator delete(v135);
      if ( (v138 & 0x800000000LL) != 0 )
        operator delete(v139);
      if ( (v142 & 0x800000000LL) != 0 )
        operator delete(v143);
      goto LABEL_447;
    }
    if ( (v146 & 8) != 0 )
      operator delete(v147);
    if ( (v110 & 0x800000000LL) != 0 )
      operator delete(v111);
    if ( (v114 & 0x800000000LL) != 0 )
      operator delete(v115);
    if ( (v118 & 0x800000000LL) != 0 )
      operator delete(v119);
    if ( (v122 & 0x800000000LL) != 0 )
      operator delete(v123);
    if ( (v126 & 0x800000000LL) != 0 )
      operator delete(v127);
    if ( (v130 & 0x800000000LL) != 0 )
      operator delete(v131);
    if ( (v134 & 0x800000000LL) != 0 )
      operator delete(v135);
    if ( (v138 & 0x800000000LL) != 0 )
      operator delete(v139);
    if ( (v142 & 0x800000000LL) != 0 )
      operator delete(v143);
    if ( (v102 & 0x800000000LL) != 0 )
      operator delete(String);
  }
  return 0;
}

```

## disassembly

```asm
0x140002168  push    rbx
0x14000216a  push    rsi
0x14000216b  push    rdi
0x14000216c  push    r12
0x14000216e  push    r13
0x140002170  push    r14
0x140002172  push    r15
0x140002174  mov     eax, 1A20h
0x140002179  call    _alloca_probe
0x14000217e  sub     rsp, rax
0x140002181  mov     rax, cs:__security_cookie
0x140002188  xor     rax, rsp
0x14000218b  mov     [rsp+1A58h+var_48], rax
0x140002193  mov     rsi, r8
0x140002196  mov     rbx, rdx
0x140002199  mov     r12, rcx
0x14000219c  mov     [rsp+1A58h+var_19E8], rcx
0x1400021a1  cmp     dword ptr [r8], 4
0x1400021a5  jnz     short loc_140002207
0x1400021a7  cmp     word ptr [rdx], 30h ; '0'
0x1400021ab  jnz     short loc_1400021C0
0x1400021ad  xor     edi, edi
0x1400021af  mov     [r8+0A8h], edi
0x1400021b6  mov     eax, 1
0x1400021bb  jmp     loc_1400044A8
0x1400021c0  cmp     word ptr [rdx], 31h ; '1'
0x1400021c4  jnz     short loc_1400021DB
0x1400021c6  mov     r14d, 1
0x1400021cc  mov     [r8+0A8h], r14d
0x1400021d3  mov     al, r14b
0x1400021d6  jmp     loc_1400044A8
0x1400021db  cmp     word ptr [rdx], 32h ; '2'
0x1400021df  jnz     short loc_1400021F0
0x1400021e1  mov     r15d, 2
0x1400021e7  mov     [r8+0A8h], r15d
0x1400021ee  jmp     short loc_1400021B6
0x1400021f0  cmp     word ptr [rdx], 33h ; '3'
0x1400021f4  jnz     loc_14000247D
0x1400021fa  mov     dword ptr [r8+0A8h], 3
0x140002205  jmp     short loc_1400021B6
0x140002207  cmp     dword ptr [r8], 6
0x14000220b  jnz     loc_14000231D
0x140002211  xor     edi, edi
0x140002213  cmp     [r8+0B0h], rdi
0x14000221a  jnz     short loc_140002265
0x14000221c  mov     rcx, rbx; psz
0x14000221f  call    cs:__imp_SysAllocString
0x140002225  mov     rbx, rax
0x140002228  cmp     [rsi+0B8h], edi
0x14000222e  jz      short loc_140002243
0x140002230  mov     rcx, [rsi+0B0h]; bstrString
0x140002237  call    cs:__imp_SysFreeString
0x14000223d  mov     [rsi+0B8h], edi
0x140002243  mov     [rsi+0B0h], rbx
0x14000224a  test    rbx, rbx
0x14000224d  jz      loc_140002312
0x140002253  mov     r14d, 1
0x140002259  mov     [rsi+0B8h], r14d
0x140002260  jmp     loc_1400021D3
0x140002265  cmp     [r8+0C0h], rdi
0x14000226c  jnz     short loc_1400022B3
0x14000226e  mov     rcx, rbx; psz
0x140002271  call    cs:__imp_SysAllocString
0x140002277  mov     rbx, rax
0x14000227a  cmp     [rsi+0C8h], edi
0x140002280  jz      short loc_140002295
0x140002282  mov     rcx, [rsi+0C0h]; bstrString
0x140002289  call    cs:__imp_SysFreeString
0x14000228f  mov     [rsi+0C8h], edi
0x140002295  mov     [rsi+0C0h], rbx
0x14000229c  test    rbx, rbx
0x14000229f  jz      short loc_140002312
0x1400022a1  mov     r14d, 1
0x1400022a7  mov     [rsi+0C8h], r14d
0x1400022ae  jmp     loc_1400021D3
0x1400022b3  cmp     [r8+0D0h], edi
0x1400022ba  jz      loc_14000247F
0x1400022c0  cmp     [r8+0D8h], rdi
0x1400022c7  jnz     loc_14000247F
0x1400022cd  mov     rcx, rbx; psz
0x1400022d0  call    cs:__imp_SysAllocString
0x1400022d6  mov     rbx, rax
0x1400022d9  cmp     [rsi+0E0h], edi
0x1400022df  jz      short loc_1400022F4
0x1400022e1  mov     rcx, [rsi+0D8h]; bstrString
0x1400022e8  call    cs:__imp_SysFreeString
0x1400022ee  mov     [rsi+0E0h], edi
0x1400022f4  mov     [rsi+0D8h], rbx
0x1400022fb  test    rbx, rbx
0x1400022fe  jz      short loc_140002312
0x140002300  mov     r14d, 1
0x140002306  mov     [rsi+0E0h], r14d
0x14000230d  jmp     loc_1400021D3
0x140002312  mov     r14d, 1
0x140002318  jmp     loc_1400021D3
0x14000231d  cmp     dword ptr [r8], 5
0x140002321  jnz     loc_14000247D
0x140002327  xor     edi, edi
0x140002329  mov     [rsp+1A58h+var_1A30], edi; int
0x14000232d  lea     r14d, [rdi+1]
0x140002331  mov     [rsp+1A58h+var_1A38], r14d; int
0x140002336  xor     r8d, r8d; unsigned int
0x140002339  lea     rdx, aScmstart; "scmstart"
0x140002340  mov     rcx, rbx; unsigned __int16 *
0x140002343  call    ?CaseCompareHelper@SString@@CAHPEBG0IKHH@Z; SString::CaseCompareHelper(ushort const *,ushort const *,uint,ulong,int,int)
0x140002348  test    eax, eax
0x14000234a  jnz     short loc_140002357
0x14000234c  mov     [rsi+0ACh], edi
0x140002352  jmp     loc_1400021D3
0x140002357  mov     [rsp+1A58h+var_1A30], edi; int
0x14000235b  mov     [rsp+1A58h+var_1A38], r14d; int
0x140002360  xor     r8d, r8d; unsigned int
0x140002363  lea     rdx, aScmpause; "scmpause"
0x14000236a  mov     rcx, rbx; unsigned __int16 *
0x14000236d  call    ?CaseCompareHelper@SString@@CAHPEBG0IKHH@Z; SString::CaseCompareHelper(ushort const *,ushort const *,uint,ulong,int,int)
0x140002372  test    eax, eax
0x140002374  jnz     short loc_140002386
0x140002376  lea     r15d, [rax+2]
0x14000237a  mov     [rsi+0ACh], r15d
0x140002381  jmp     loc_1400021D3
0x140002386  mov     [rsp+1A58h+var_1A30], edi; int
0x14000238a  mov     [rsp+1A58h+var_1A38], r14d; int
0x14000238f  xor     r8d, r8d; unsigned int
0x140002392  lea     rdx, aScmstop; "scmstop"
0x140002399  mov     rcx, rbx; unsigned __int16 *
0x14000239c  call    ?CaseCompareHelper@SString@@CAHPEBG0IKHH@Z; SString::CaseCompareHelper(ushort const *,ushort const *,uint,ulong,int,int)
0x1400023a1  test    eax, eax
0x1400023a3  jnz     short loc_1400023B1
0x1400023a5  mov     [rsi+0ACh], r14d
0x1400023ac  jmp     loc_1400021D3
0x1400023b1  mov     [rsp+1A58h+var_1A30], edi; int
0x1400023b5  mov     [rsp+1A58h+var_1A38], r14d; int
0x1400023ba  xor     r8d, r8d; unsigned int
0x1400023bd  lea     rdx, aScmcontinue; "scmcontinue"
0x1400023c4  mov     rcx, rbx; unsigned __int16 *
0x1400023c7  call    ?CaseCompareHelper@SString@@CAHPEBG0IKHH@Z; SString::CaseCompareHelper(ushort const *,ushort const *,uint,ulong,int,int)
0x1400023cc  test    eax, eax
0x1400023ce  jz      loc_14000246E
0x1400023d4  mov     [rsp+1A58h+var_1A30], edi; int
0x1400023d8  mov     [rsp+1A58h+var_1A38], r14d; int
0x1400023dd  xor     r8d, r8d; unsigned int
0x1400023e0  lea     rdx, aScmstatus; "scmstatus"
0x1400023e7  mov     rcx, rbx; unsigned __int16 *
0x1400023ea  call    ?CaseCompareHelper@SString@@CAHPEBG0IKHH@Z; SString::CaseCompareHelper(ushort const *,ushort const *,uint,ulong,int,int)
0x1400023ef  test    eax, eax
0x1400023f1  jz      short loc_14000245F
0x1400023f3  mov     [rsp+1A58h+var_1A30], edi; int
0x1400023f7  mov     [rsp+1A58h+var_1A38], r14d; int
0x1400023fc  xor     r8d, r8d; unsigned int
0x1400023ff  lea     rdx, aPause; "pause"
0x140002406  mov     rcx, rbx; unsigned __int16 *
0x140002409  call    ?CaseCompareHelper@SString@@CAHPEBG0IKHH@Z; SString::CaseCompareHelper(ushort const *,ushort const *,uint,ulong,int,int)
0x14000240e  test    eax, eax
0x140002410  jnz     short loc_140002421
0x140002412  mov     dword ptr [rsi+0ACh], 5
0x14000241c  jmp     loc_1400021D3
0x140002421  mov     [rsp+1A58h+var_1A30], edi; int
0x140002425  mov     [rsp+1A58h+var_1A38], r14d; int
0x14000242a  xor     r8d, r8d; unsigned int
0x14000242d  lea     rdx, aContinue; "continue"
0x140002434  mov     rcx, rbx; unsigned __int16 *
0x140002437  call    ?CaseCompareHelper@SString@@CAHPEBG0IKHH@Z; SString::CaseCompareHelper(ushort const *,ushort const *,uint,ulong,int,int)
0x14000243c  test    eax, eax
0x14000243e  jz      short loc_14000246E
0x140002440  mov     [rsp+1A58h+var_1A30], edi; int
0x140002444  mov     [rsp+1A58h+var_1A38], r14d; int
0x140002449  xor     r8d, r8d; unsigned int
0x14000244c  lea     rdx, aStatus; "status"
0x140002453  mov     rcx, rbx; unsigned __int16 *
0x140002456  call    ?CaseCompareHelper@SString@@CAHPEBG0IKHH@Z; SString::CaseCompareHelper(ushort const *,ushort const *,uint,ulong,int,int)
0x14000245b  test    eax, eax
0x14000245d  jnz     short loc_140002485
0x14000245f  mov     dword ptr [rsi+0ACh], 4
0x140002469  jmp     loc_1400021D3
0x14000246e  mov     dword ptr [rsi+0ACh], 3
0x140002478  jmp     loc_1400021D3
0x14000247d  xor     edi, edi
0x14000247f  mov     r14d, 1
0x140002485  movzx   eax, word ptr [rbx]
0x140002488  sub     ax, 2Dh ; '-'
0x14000248c  mov     ecx, 0FFFDh
0x140002491  test    cx, ax
0x140002494  jnz     loc_1400044A6
0x14000249a  mov     r15d, 2
0x1400024a0  add     rbx, r15
0x1400024a3  mov     [rsp+1A58h+var_1A30], edi; int
0x1400024a7  mov     [rsp+1A58h+var_1A38], r14d; int
0x1400024ac  xor     r8d, r8d; unsigned int
0x1400024af  lea     rdx, aSilent; "Silent"
0x1400024b6  mov     rcx, rbx; unsigned __int16 *
0x1400024b9  call    ?CaseCompareHelper@SString@@CAHPEBG0IKHH@Z; SString::CaseCompareHelper(ushort const *,ushort const *,uint,ulong,int,int)
0x1400024be  test    eax, eax
0x1400024c0  jnz     short loc_1400024CE
0x1400024c2  mov     [rsi+0A4h], r14d
0x1400024c9  jmp     loc_1400021D3
0x1400024ce  mov     [rsp+1A58h+var_1A30], edi; int
0x1400024d2  mov     [rsp+1A58h+var_1A38], r14d; int
0x1400024d7  xor     r8d, r8d; unsigned int
0x1400024da  lea     rdx, aVerbose; "Verbose"
0x1400024e1  mov     rcx, rbx; unsigned __int16 *
0x1400024e4  call    ?CaseCompareHelper@SString@@CAHPEBG0IKHH@Z; SString::CaseCompareHelper(ushort const *,ushort const *,uint,ulong,int,int)
0x1400024e9  test    eax, eax
0x1400024eb  jnz     short loc_1400024FC
0x1400024ed  mov     dword ptr [rsi+0A4h], 3
0x1400024f7  jmp     loc_1400021D3
0x1400024fc  cmp     [rsi], r15d
0x1400024ff  jnz     short loc_140002555
0x140002501  mov     [rsp+1A58h+var_1A30], edi; int
0x140002505  mov     [rsp+1A58h+var_1A38], r14d; int
0x14000250a  xor     r8d, r8d; unsigned int
0x14000250d  lea     rdx, aForce; "Force"
0x140002514  mov     rcx, rbx; unsigned __int16 *
0x140002517  call    ?CaseCompareHelper@SString@@CAHPEBG0IKHH@Z; SString::CaseCompareHelper(ushort const *,ushort const *,uint,ulong,int,int)
0x14000251c  test    eax, eax
0x14000251e  jnz     short loc_140002529
0x140002520  or      [rsi+1Ch], r14d
0x140002524  jmp     loc_1400021D3
0x140002529  cmp     [rsi], r15d
0x14000252c  jnz     short loc_140002555
0x14000252e  lea     rdx, aPostreboot; "Postreboot"
0x140002535  mov     rcx, rbx; String1
0x140002538  call    cs:__imp__wcsicmp
0x14000253e  test    eax, eax
0x140002540  jnz     short loc_140002555
0x140002542  mov     dword ptr [rsi+0A8h], 3
0x14000254c  or      [rsi+1Ch], r15d
0x140002550  jmp     loc_1400021D3
0x140002555  test    dword ptr [rsi], 0FFFFFFFDh
0x14000255b  jnz     short loc_140002580
0x14000255d  mov     [rsp+1A58h+var_1A30], edi; int
0x140002561  mov     [rsp+1A58h+var_1A38], r14d; int
0x140002566  xor     r8d, r8d; unsigned int
0x140002569  lea     rdx, aQueue; "Queue"
0x140002570  mov     rcx, rbx; unsigned __int16 *
0x140002573  call    ?CaseCompareHelper@SString@@CAHPEBG0IKHH@Z; SString::CaseCompareHelper(ushort const *,ushort const *,uint,ulong,int,int)
0x140002578  test    eax, eax
0x14000257a  jz      loc_140002613
0x140002580  cmp     [rsi], edi
0x140002582  jnz     loc_140002629
0x140002588  mov     [rsp+1A58h+var_1A30], edi; int
0x14000258c  mov     [rsp+1A58h+var_1A38], r14d; int
0x140002591  xor     r8d, r8d; unsigned int
0x140002594  lea     rdx, aQueue1; "Queue:1"
0x14000259b  mov     rcx, rbx; unsigned __int16 *
0x14000259e  call    ?CaseCompareHelper@SString@@CAHPEBG0IKHH@Z; SString::CaseCompareHelper(ushort const *,ushort const *,uint,ulong,int,int)
0x1400025a3  test    eax, eax
0x1400025a5  jnz     short loc_1400025BA
0x1400025a7  mov     [rsi+90h], r14d
0x1400025ae  mov     [rsi+0A8h], r14d
0x1400025b5  jmp     loc_1400021D3
0x1400025ba  cmp     [rsi], edi
0x1400025bc  jnz     short loc_140002629
0x1400025be  mov     [rsp+1A58h+var_1A30], edi; int
0x1400025c2  mov     [rsp+1A58h+var_1A38], r14d; int
0x1400025c7  xor     r8d, r8d; unsigned int
0x1400025ca  lea     rdx, aQueue2; "Queue:2"
0x1400025d1  mov     rcx, rbx; unsigned __int16 *
0x1400025d4  call    ?CaseCompareHelper@SString@@CAHPEBG0IKHH@Z; SString::CaseCompareHelper(ushort const *,ushort const *,uint,ulong,int,int)
0x1400025d9  test    eax, eax
0x1400025db  jnz     short loc_1400025F0
0x1400025dd  mov     [rsi+90h], r14d
0x1400025e4  mov     [rsi+0A8h], r15d
0x1400025eb  jmp     loc_1400021D3
0x1400025f0  cmp     [rsi], edi
0x1400025f2  jnz     short loc_140002629
0x1400025f4  mov     [rsp+1A58h+var_1A30], edi; int
0x1400025f8  mov     [rsp+1A58h+var_1A38], r14d; int
0x1400025fd  xor     r8d, r8d; unsigned int
0x140002600  lea     rdx, aQueue3; "Queue:3"
0x140002607  mov     rcx, rbx; unsigned __int16 *
0x14000260a  call    ?CaseCompareHelper@SString@@CAHPEBG0IKHH@Z; SString::CaseCompareHelper(ushort const *,ushort const *,uint,ulong,int,int)
0x14000260f  test    eax, eax
0x140002611  jnz     short loc_140002629
0x140002613  mov     [rsi+90h], r14d
0x14000261a  mov     dword ptr [rsi+0A8h], 3
0x140002624  jmp     loc_1400021D3
0x140002629  cmp     [rsi], r15d
0x14000262c  jnz     short loc_140002659
0x14000262e  mov     [rsp+1A58h+var_1A30], edi; int
0x140002632  mov     [rsp+1A58h+var_1A38], r14d; int
0x140002637  xor     r8d, r8d; unsigned int
0x14000263a  lea     rdx, aDelay; "Delay"
0x140002641  mov     rcx, rbx; unsigned __int16 *
0x140002644  call    ?CaseCompareHelper@SString@@CAHPEBG0IKHH@Z; SString::CaseCompareHelper(ushort const *,ushort const *,uint,ulong,int,int)
0x140002649  test    eax, eax
0x14000264b  jnz     short loc_140002659
0x14000264d  mov     [rsi+94h], r14d
0x140002654  jmp     loc_1400021D3
0x140002659  cmp     [rsi], edi
0x14000265b  jnz     short loc_140002685
0x14000265d  mov     [rsp+1A58h+var_1A30], edi; int
0x140002661  mov     [rsp+1A58h+var_1A38], r14d; int
0x140002666  xor     r8d, r8d; unsigned int
0x140002669  lea     rdx, aNetfxpri1; "NetfxPri1"
0x140002670  mov     rcx, rbx; unsigned __int16 *
0x140002673  call    ?CaseCompareHelper@SString@@CAHPEBG0IKHH@Z; SString::CaseCompareHelper(ushort const *,ushort const *,uint,ulong,int,int)
0x140002678  test    eax, eax
0x14000267a  jnz     short loc_140002685
0x14000267c  or      [rsi+20h], r15d
0x140002680  jmp     loc_1400021D3
  ... truncated ...
```
