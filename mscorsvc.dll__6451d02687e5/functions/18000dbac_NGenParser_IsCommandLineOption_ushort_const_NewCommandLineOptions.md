# NGenParser::IsCommandLineOption(ushort const *,NewCommandLineOptions &)

- ea: `0x18000dbac`
- end: `0x1800100bc`
- name: `?IsCommandLineOption@NGenParser@@AEAA_NPEBGAEAUNewCommandLineOptions@@@Z`
- size: `9488`
- prototype: `bool __fastcall(NGenParser *__hidden this, const unsigned __int16 *, struct NewCommandLineOptions *)`
- caller_count: `1`
- callee_count: `25`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800100bc`

## callees

- `0x180001da0`
- `0x180001de0`
- `0x180001f00`
- `0x1800020c8`
- `0x180002504`
- `0x180002dec`
- `0x18000d138`
- `0x18000d84c`
- `0x18000d96c`
- `0x18000d9e4`
- `0x18000dbac`
- `0x180013dd4`
- `0x180013e2c`
- `0x180030568`
- `0x180030840`
- `0x180030ab8`
- `0x180030d84`
- `0x1800312ec`
- `0x1800321ac`
- `0x180032ef4`
- `0x18003303c`
- `0x1800350c4`
- `0x180037c10`
- `0x18003dc30`
- `0x18003f110`

## import_xrefs

- `KERNEL32!GetFileAttributesW` at `0x18000e9f5`
- `KERNEL32!GetFileAttributesW` at `0x18000e9f5`
- `ucrtbase_clr0400!_wtoi` at `0x18000fca0`
- `ucrtbase_clr0400!_wtoi` at `0x18000fca0`
- `ucrtbase_clr0400!_wcsicmp` at `0x18000df7c`
- `ucrtbase_clr0400!_wcsicmp` at `0x18000df7c`
- `OLEAUT32!__imp_SysAllocString` at `0x18000dc63`
- `OLEAUT32!__imp_SysAllocString` at `0x18000dcb5`
- `OLEAUT32!__imp_SysAllocString` at `0x18000dd14`
- `OLEAUT32!__imp_SysAllocString` at `0x18000e6fa`
- `OLEAUT32!__imp_SysAllocString` at `0x18000ea21`
- `OLEAUT32!__imp_SysAllocString` at `0x18000ec7a`
- `OLEAUT32!__imp_SysAllocString` at `0x18000eed7`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f130`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f3b2`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f60f`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f86c`
- `OLEAUT32!__imp_SysAllocString` at `0x18000dc63`
- `OLEAUT32!__imp_SysAllocString` at `0x18000dcb5`
- `OLEAUT32!__imp_SysAllocString` at `0x18000dd14`
- `OLEAUT32!__imp_SysAllocString` at `0x18000e6fa`
- `OLEAUT32!__imp_SysAllocString` at `0x18000ea21`
- `OLEAUT32!__imp_SysAllocString` at `0x18000ec7a`
- `OLEAUT32!__imp_SysAllocString` at `0x18000eed7`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f130`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f3b2`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f60f`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f86c`
- `OLEAUT32!__imp_SysFreeString` at `0x18000dc7b`
- `OLEAUT32!__imp_SysFreeString` at `0x18000dccd`
- `OLEAUT32!__imp_SysFreeString` at `0x18000dd2c`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e70c`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ea33`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ec8c`
- `OLEAUT32!__imp_SysFreeString` at `0x18000eee9`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f142`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f3c4`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f621`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f87e`
- `OLEAUT32!__imp_SysFreeString` at `0x18000dc7b`
- `OLEAUT32!__imp_SysFreeString` at `0x18000dccd`
- `OLEAUT32!__imp_SysFreeString` at `0x18000dd2c`
- `OLEAUT32!__imp_SysFreeString` at `0x18000e70c`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ea33`
- `OLEAUT32!__imp_SysFreeString` at `0x18000ec8c`
- `OLEAUT32!__imp_SysFreeString` at `0x18000eee9`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f142`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f3c4`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f621`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f87e`

## string_xrefs

- `0x18000e158`: `LegacyServiceBehavior`
- `0x18000e208`: `ExeConfig:`
- `0x18000e2b2`: `MoveFromRepository:`
- `0x18000e307`: `CopyFromRepository:`
- `0x18000e35c`: `CopyToRepository:`
- `0x18000fef4`: `Error: Cannot use /ExeConfig with the Ngen Offline feature.`
- `0x18000ff1c`: `Error: Cannot specify both /ExeConfig and /AppBase`
- `0x18000ff8c`: `Error: Cannot specify both /ExeConfig and /AppBase`
- `0x18000ff44`: `Error: /ExeConfig specified without an executable`
- `0x18000ffb4`: `Error: /AppBase specified without a valid directory`

## pseudocode

```c
// Hidden C++ exception states: #wind=75
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
  OLECHAR *v93; // [rsp+48h] [rbp-1A10h] BYREF
  OLECHAR **v94; // [rsp+50h] [rbp-1A08h]
  void *lpMem; // [rsp+58h] [rbp-1A00h]
  OLECHAR **v96; // [rsp+60h] [rbp-19F8h]
  BOOL v97; // [rsp+68h] [rbp-19F0h]
  NGenParser *v98; // [rsp+70h] [rbp-19E8h]
  OLECHAR **v99; // [rsp+78h] [rbp-19E0h] BYREF
  OLECHAR **v100; // [rsp+80h] [rbp-19D8h] BYREF
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
    SString::Set((SString *)&v101, v19);
    v142 = 512;
    v143 = &v144;
    v141 = 2;
    v144 = 0;
    SString::Set((SString *)&v141, L"ExeConfig:");
    v138 = 512;
    v139 = &v140;
    v137 = 2;
    v140 = 0;
    SString::Set((SString *)&v137, L"AppBase:");
    v134 = 512;
    v135 = &v136;
    v133 = 2;
    v136 = 0;
    SString::Set((SString *)&v133, L"MoveFromRepository:");
    v130 = 512;
    v131 = &v132;
    v129 = 2;
    v132 = 0;
    SString::Set((SString *)&v129, L"CopyFromRepository:");
    v126 = 512;
    v127 = &v128;
    v125 = 2;
    v128 = 0;
    SString::Set((SString *)&v125, L"CopyToRepository:");
    v122 = 512;
    v123 = &v124;
    v121 = 2;
    v124 = 0;
    SString::Set((SString *)&v121, L"Version:");
    v118 = 512;
    v119 = &v120;
    v117 = 2;
    v120 = 0;
    SString::Set((SString *)&v117, L"Package:");
    v114 = 512;
    v115 = &v116;
    v113 = 2;
    v116 = 0;
    SString::Set((SString *)&v113, L"LocalAppData:");
    v110 = 512;
    v111 = &v112;
    v109 = 2;
    v112 = 0;
    SString::Set((SString *)&v109, L"Stats");
    InlineSString<512>::InlineSString<512>(v145, &v109);
    SString::SString((SString *)&v93, v24);
    SString::Append((SString *)v145, (const struct SString *)&v93);
    if ( ((unsigned __int8)v94 & 8) != 0 )
      operator delete(lpMem);
    if ( (~(HIDWORD(v102) >> 1) & 1) == 0 && !(unsigned int)SString::ScanASCII((SString *)&v101) )
      SString::ConvertToUnicode((SString *)&v101);
    if ( (v102 & 0x1000000000LL) != 0 )
      SBuffer::ReallocateBuffer(&v101, (unsigned int)v102, 1);
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
        ThrowHR(-2147024809, v72);
      }
      if ( a3[5] )
      {
        NGenParser::PrintLogoHelper(this);
        v74 = (const struct SString *)SString::SString(&v90, v73, L"Error: Cannot specify both /ExeConfig and /AppBase");
        ThrowHR(-2147024809, v74);
      }
      if ( (~(HIDWORD(v102) >> 1) & 1) == 0 && !(unsigned int)SString::ScanASCII((SString *)&v101) )
        SString::ConvertToUnicode((SString *)&v101);
      if ( (v102 & 0x1000000000LL) != 0 )
        SBuffer::ReallocateBuffer(&v101, (unsigned int)v102, 1);
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
        ThrowHR(-2147024809, v76);
      }
      v106 = 512;
      psz = v108;
      v105 = 2;
      v108[0] = 0;
      LODWORD(v93) = 0;
      v94 = 0;
      try
      {
        try
        {
          v96 = &v93;
          SString::ConvertToUnicode((SString *)&v101);
          CanonicalizePath(String, (struct SString *)&v105, 1);
        }
        catch ( Exception *v99 )
        {
          Exception::HandlerState::SetCaughtCxx((Exception::HandlerState *)&v93);
          v94 = v99;
          throw;
        }
      }
      catch ( ... )
      {
        v91 = 0;
        v90 = (OLECHAR *)&DelegatingException::`vftable';
        v92 = (void *)-1LL;
        v96 = v94;
        v97 = v94 != 0;
        Exception::HandlerState::SetupCatch((Exception::HandlerState *)&v93, 505, v29);
        NGenParser::PrintLogoHelper(v98);
        v97 = 0;
        throw;
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
      SBuffer::ReallocateBuffer(&v101, (unsigned int)v102, 1);
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
        ThrowHR(-2147024809, v77);
      }
      if ( a3[5] )
      {
        NGenParser::PrintLogoHelper(this);
        v79 = (const struct SString *)SString::SString(&v90, v78, L"Error: Cannot specify both /ExeConfig and /AppBase");
        ThrowHR(-2147024809, v79);
      }
      if ( (~(HIDWORD(v102) >> 1) & 1) == 0 && !(unsigned int)SString::ScanASCII((SString *)&v101) )
        SString::ConvertToUnicode((SString *)&v101);
      if ( (v102 & 0x1000000000LL) != 0 )
        SBuffer::ReallocateBuffer(&v101, (unsigned int)v102, 1);
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
      try
      {
        try
        {
          v96 = &v93;
          SString::ConvertToUnicode((SString *)&v101);
          CanonicalizePathAux(String, (struct SString *)&v105, 1);
        }
        catch ( Exception *v100 )
        {
          Exception::HandlerState::SetCaughtCxx((Exception::HandlerState *)&v93);
          v94 = v100;
          throw;
        }
      }
      catch ( ... )
      {
        v91 = 0;
        v90 = (OLECHAR *)&DelegatingException::`vftable';
        v92 = (void *)-1LL;
        v96 = v94;
        v97 = v94 != 0;
        Exception::HandlerState::SetupCatch((Exception::HandlerState *)&v93, 535, v34);
        NGenParser::PrintLogoHelper(v98);
        v97 = 0;
        throw;
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
        ThrowHR(-2147024809, v81);
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
      SBuffer::ReallocateBuffer(&v101, (unsigned int)v102, 1);
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
        ThrowHR(-2147024809, v82);
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
      SBuffer::ReallocateBuffer(&v101, (unsigned int)v102, 1);
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
        ThrowHR(-2147024809, v83);
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
      SBuffer::ReallocateBuffer(&v101, (unsigned int)v102, 1);
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
        ThrowHR(-2147024809, v84);
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
      SBuffer::ReallocateBuffer(&v101, (unsigned int)v102, 1);
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
        ThrowHR(-2147024809, v85);
      }
      if ( (~(HIDWORD(v102) >> 1) & 1) == 0 && !(unsigned int)SString::ScanASCII((SString *)&v101) )
        SString::ConvertToUnicode((SString *)&v101);
      if ( (v102 & 0x1000000000LL) != 0 )
        SBuffer::ReallocateBuffer(&v101, (unsigned int)v102, 1);
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
      SBuffer::ReallocateBuffer(&v101, (unsigned int)v102, 1);
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
        ThrowHR(-2147024809, v86);
      }
      if ( (~(HIDWORD(v102) >> 1) & 1) == 0 && !(unsigned int)SString::ScanASCII((SString *)&v101) )
        SString::ConvertToUnicode((SString *)&v101);
      if ( (v102 & 0x1000000000LL) != 0 )
        SBuffer::ReallocateBuffer(&v101, (unsigned int)v102, 1);
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
      SBuffer::ReallocateBuffer(&v101, (unsigned int)v102, 1);
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
        ThrowHR(-2147024809, v87);
      }
      if ( (~(HIDWORD(v102) >> 1) & 1) == 0 && !(unsigned int)SString::ScanASCII((SString *)&v101) )
        SString::ConvertToUnicode((SString *)&v101);
      if ( (v102 & 0x1000000000LL) != 0 )
        SBuffer::ReallocateBuffer(&v101, (unsigned int)v102, 1);
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
      SBuffer::ReallocateBuffer(&v101, (unsigned int)v102, 1);
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
        SBuffer::ReallocateBuffer(&v101, (unsigned int)v102, 1);
        v65 = BYTE4(v102);
      }
      v93 = String;
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
                ThrowHR(-2147024809, v89);
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
0x18000dbac  push    rbx
0x18000dbae  push    rsi
0x18000dbaf  push    rdi
0x18000dbb0  push    r12
0x18000dbb2  push    r13
0x18000dbb4  push    r14
0x18000dbb6  push    r15
0x18000dbb8  mov     eax, 1A20h
0x18000dbbd  call    _alloca_probe
0x18000dbc2  sub     rsp, rax
0x18000dbc5  mov     rax, cs:__security_cookie
0x18000dbcc  xor     rax, rsp
0x18000dbcf  mov     [rsp+1A58h+var_48], rax
0x18000dbd7  mov     rsi, r8
0x18000dbda  mov     rbx, rdx
0x18000dbdd  mov     r12, rcx
0x18000dbe0  mov     [rsp+1A58h+var_19E8], rcx
0x18000dbe5  cmp     dword ptr [r8], 4
0x18000dbe9  jnz     short loc_18000DC4B
0x18000dbeb  cmp     word ptr [rdx], 30h ; '0'
0x18000dbef  jnz     short loc_18000DC04
0x18000dbf1  xor     edi, edi
0x18000dbf3  mov     [r8+0A8h], edi
0x18000dbfa  mov     eax, 1
0x18000dbff  jmp     loc_18000FED1
0x18000dc04  cmp     word ptr [rdx], 31h ; '1'
0x18000dc08  jnz     short loc_18000DC1F
0x18000dc0a  mov     r14d, 1
0x18000dc10  mov     [r8+0A8h], r14d
0x18000dc17  mov     al, r14b
0x18000dc1a  jmp     loc_18000FED1
0x18000dc1f  cmp     word ptr [rdx], 32h ; '2'
0x18000dc23  jnz     short loc_18000DC34
0x18000dc25  mov     r15d, 2
0x18000dc2b  mov     [r8+0A8h], r15d
0x18000dc32  jmp     short loc_18000DBFA
0x18000dc34  cmp     word ptr [rdx], 33h ; '3'
0x18000dc38  jnz     loc_18000DEC1
0x18000dc3e  mov     dword ptr [r8+0A8h], 3
0x18000dc49  jmp     short loc_18000DBFA
0x18000dc4b  cmp     dword ptr [r8], 6
0x18000dc4f  jnz     loc_18000DD61
0x18000dc55  xor     edi, edi
0x18000dc57  cmp     [r8+0B0h], rdi
0x18000dc5e  jnz     short loc_18000DCA9
0x18000dc60  mov     rcx, rbx; psz
0x18000dc63  call    cs:__imp_SysAllocString
0x18000dc69  mov     rbx, rax
0x18000dc6c  cmp     [rsi+0B8h], edi
0x18000dc72  jz      short loc_18000DC87
0x18000dc74  mov     rcx, [rsi+0B0h]; bstrString
0x18000dc7b  call    cs:__imp_SysFreeString
0x18000dc81  mov     [rsi+0B8h], edi
0x18000dc87  mov     [rsi+0B0h], rbx
0x18000dc8e  test    rbx, rbx
0x18000dc91  jz      loc_18000DD56
0x18000dc97  mov     r14d, 1
0x18000dc9d  mov     [rsi+0B8h], r14d
0x18000dca4  jmp     loc_18000DC17
0x18000dca9  cmp     [r8+0C0h], rdi
0x18000dcb0  jnz     short loc_18000DCF7
0x18000dcb2  mov     rcx, rbx; psz
0x18000dcb5  call    cs:__imp_SysAllocString
0x18000dcbb  mov     rbx, rax
0x18000dcbe  cmp     [rsi+0C8h], edi
0x18000dcc4  jz      short loc_18000DCD9
0x18000dcc6  mov     rcx, [rsi+0C0h]; bstrString
0x18000dccd  call    cs:__imp_SysFreeString
0x18000dcd3  mov     [rsi+0C8h], edi
0x18000dcd9  mov     [rsi+0C0h], rbx
0x18000dce0  test    rbx, rbx
0x18000dce3  jz      short loc_18000DD56
0x18000dce5  mov     r14d, 1
0x18000dceb  mov     [rsi+0C8h], r14d
0x18000dcf2  jmp     loc_18000DC17
0x18000dcf7  cmp     [r8+0D0h], edi
0x18000dcfe  jz      loc_18000DEC3
0x18000dd04  cmp     [r8+0D8h], rdi
0x18000dd0b  jnz     loc_18000DEC3
0x18000dd11  mov     rcx, rbx; psz
0x18000dd14  call    cs:__imp_SysAllocString
0x18000dd1a  mov     rbx, rax
0x18000dd1d  cmp     [rsi+0E0h], edi
0x18000dd23  jz      short loc_18000DD38
0x18000dd25  mov     rcx, [rsi+0D8h]; bstrString
0x18000dd2c  call    cs:__imp_SysFreeString
0x18000dd32  mov     [rsi+0E0h], edi
0x18000dd38  mov     [rsi+0D8h], rbx
0x18000dd3f  test    rbx, rbx
0x18000dd42  jz      short loc_18000DD56
0x18000dd44  mov     r14d, 1
0x18000dd4a  mov     [rsi+0E0h], r14d
0x18000dd51  jmp     loc_18000DC17
0x18000dd56  mov     r14d, 1
0x18000dd5c  jmp     loc_18000DC17
0x18000dd61  cmp     dword ptr [r8], 5
0x18000dd65  jnz     loc_18000DEC1
0x18000dd6b  xor     edi, edi
0x18000dd6d  mov     [rsp+1A58h+var_1A30], edi; int
0x18000dd71  lea     r14d, [rdi+1]
0x18000dd75  mov     [rsp+1A58h+var_1A38], r14d; int
0x18000dd7a  xor     r8d, r8d; unsigned int
0x18000dd7d  lea     rdx, aScmstart; "scmstart"
0x18000dd84  mov     rcx, rbx; unsigned __int16 *
0x18000dd87  call    ?CaseCompareHelper@SString@@CAHPEBG0IKHH@Z; SString::CaseCompareHelper(ushort const *,ushort const *,uint,ulong,int,int)
0x18000dd8c  test    eax, eax
0x18000dd8e  jnz     short loc_18000DD9B
0x18000dd90  mov     [rsi+0ACh], edi
0x18000dd96  jmp     loc_18000DC17
0x18000dd9b  mov     [rsp+1A58h+var_1A30], edi; int
0x18000dd9f  mov     [rsp+1A58h+var_1A38], r14d; int
0x18000dda4  xor     r8d, r8d; unsigned int
0x18000dda7  lea     rdx, aScmpause; "scmpause"
0x18000ddae  mov     rcx, rbx; unsigned __int16 *
0x18000ddb1  call    ?CaseCompareHelper@SString@@CAHPEBG0IKHH@Z; SString::CaseCompareHelper(ushort const *,ushort const *,uint,ulong,int,int)
0x18000ddb6  test    eax, eax
0x18000ddb8  jnz     short loc_18000DDCA
0x18000ddba  lea     r15d, [rax+2]
0x18000ddbe  mov     [rsi+0ACh], r15d
0x18000ddc5  jmp     loc_18000DC17
0x18000ddca  mov     [rsp+1A58h+var_1A30], edi; int
0x18000ddce  mov     [rsp+1A58h+var_1A38], r14d; int
0x18000ddd3  xor     r8d, r8d; unsigned int
0x18000ddd6  lea     rdx, aScmstop; "scmstop"
0x18000dddd  mov     rcx, rbx; unsigned __int16 *
0x18000dde0  call    ?CaseCompareHelper@SString@@CAHPEBG0IKHH@Z; SString::CaseCompareHelper(ushort const *,ushort const *,uint,ulong,int,int)
0x18000dde5  test    eax, eax
0x18000dde7  jnz     short loc_18000DDF5
0x18000dde9  mov     [rsi+0ACh], r14d
0x18000ddf0  jmp     loc_18000DC17
0x18000ddf5  mov     [rsp+1A58h+var_1A30], edi; int
0x18000ddf9  mov     [rsp+1A58h+var_1A38], r14d; int
0x18000ddfe  xor     r8d, r8d; unsigned int
0x18000de01  lea     rdx, aScmcontinue; "scmcontinue"
0x18000de08  mov     rcx, rbx; unsigned __int16 *
0x18000de0b  call    ?CaseCompareHelper@SString@@CAHPEBG0IKHH@Z; SString::CaseCompareHelper(ushort const *,ushort const *,uint,ulong,int,int)
0x18000de10  test    eax, eax
0x18000de12  jz      loc_18000DEB2
0x18000de18  mov     [rsp+1A58h+var_1A30], edi; int
0x18000de1c  mov     [rsp+1A58h+var_1A38], r14d; int
0x18000de21  xor     r8d, r8d; unsigned int
0x18000de24  lea     rdx, aScmstatus; "scmstatus"
0x18000de2b  mov     rcx, rbx; unsigned __int16 *
0x18000de2e  call    ?CaseCompareHelper@SString@@CAHPEBG0IKHH@Z; SString::CaseCompareHelper(ushort const *,ushort const *,uint,ulong,int,int)
0x18000de33  test    eax, eax
0x18000de35  jz      short loc_18000DEA3
0x18000de37  mov     [rsp+1A58h+var_1A30], edi; int
0x18000de3b  mov     [rsp+1A58h+var_1A38], r14d; int
0x18000de40  xor     r8d, r8d; unsigned int
0x18000de43  lea     rdx, aPause; "pause"
0x18000de4a  mov     rcx, rbx; unsigned __int16 *
0x18000de4d  call    ?CaseCompareHelper@SString@@CAHPEBG0IKHH@Z; SString::CaseCompareHelper(ushort const *,ushort const *,uint,ulong,int,int)
0x18000de52  test    eax, eax
0x18000de54  jnz     short loc_18000DE65
0x18000de56  mov     dword ptr [rsi+0ACh], 5
0x18000de60  jmp     loc_18000DC17
0x18000de65  mov     [rsp+1A58h+var_1A30], edi; int
0x18000de69  mov     [rsp+1A58h+var_1A38], r14d; int
0x18000de6e  xor     r8d, r8d; unsigned int
0x18000de71  lea     rdx, aContinue; "continue"
0x18000de78  mov     rcx, rbx; unsigned __int16 *
0x18000de7b  call    ?CaseCompareHelper@SString@@CAHPEBG0IKHH@Z; SString::CaseCompareHelper(ushort const *,ushort const *,uint,ulong,int,int)
0x18000de80  test    eax, eax
0x18000de82  jz      short loc_18000DEB2
0x18000de84  mov     [rsp+1A58h+var_1A30], edi; int
0x18000de88  mov     [rsp+1A58h+var_1A38], r14d; int
0x18000de8d  xor     r8d, r8d; unsigned int
0x18000de90  lea     rdx, aStatus; "status"
0x18000de97  mov     rcx, rbx; unsigned __int16 *
0x18000de9a  call    ?CaseCompareHelper@SString@@CAHPEBG0IKHH@Z; SString::CaseCompareHelper(ushort const *,ushort const *,uint,ulong,int,int)
0x18000de9f  test    eax, eax
0x18000dea1  jnz     short loc_18000DEC9
0x18000dea3  mov     dword ptr [rsi+0ACh], 4
0x18000dead  jmp     loc_18000DC17
0x18000deb2  mov     dword ptr [rsi+0ACh], 3
0x18000debc  jmp     loc_18000DC17
0x18000dec1  xor     edi, edi
0x18000dec3  mov     r14d, 1
0x18000dec9  movzx   eax, word ptr [rbx]
0x18000decc  sub     ax, 2Dh ; '-'
0x18000ded0  mov     ecx, 0FFFDh
0x18000ded5  test    cx, ax
0x18000ded8  jnz     loc_18000FECF
0x18000dede  mov     r15d, 2
0x18000dee4  add     rbx, r15
0x18000dee7  mov     [rsp+1A58h+var_1A30], edi; int
0x18000deeb  mov     [rsp+1A58h+var_1A38], r14d; int
0x18000def0  xor     r8d, r8d; unsigned int
0x18000def3  lea     rdx, aSilent; "Silent"
0x18000defa  mov     rcx, rbx; unsigned __int16 *
0x18000defd  call    ?CaseCompareHelper@SString@@CAHPEBG0IKHH@Z; SString::CaseCompareHelper(ushort const *,ushort const *,uint,ulong,int,int)
0x18000df02  test    eax, eax
0x18000df04  jnz     short loc_18000DF12
0x18000df06  mov     [rsi+0A4h], r14d
0x18000df0d  jmp     loc_18000DC17
0x18000df12  mov     [rsp+1A58h+var_1A30], edi; int
0x18000df16  mov     [rsp+1A58h+var_1A38], r14d; int
0x18000df1b  xor     r8d, r8d; unsigned int
0x18000df1e  lea     rdx, aVerbose; "Verbose"
0x18000df25  mov     rcx, rbx; unsigned __int16 *
0x18000df28  call    ?CaseCompareHelper@SString@@CAHPEBG0IKHH@Z; SString::CaseCompareHelper(ushort const *,ushort const *,uint,ulong,int,int)
0x18000df2d  test    eax, eax
0x18000df2f  jnz     short loc_18000DF40
0x18000df31  mov     dword ptr [rsi+0A4h], 3
0x18000df3b  jmp     loc_18000DC17
0x18000df40  cmp     [rsi], r15d
0x18000df43  jnz     short loc_18000DF99
0x18000df45  mov     [rsp+1A58h+var_1A30], edi; int
0x18000df49  mov     [rsp+1A58h+var_1A38], r14d; int
0x18000df4e  xor     r8d, r8d; unsigned int
0x18000df51  lea     rdx, aForce; "Force"
0x18000df58  mov     rcx, rbx; unsigned __int16 *
0x18000df5b  call    ?CaseCompareHelper@SString@@CAHPEBG0IKHH@Z; SString::CaseCompareHelper(ushort const *,ushort const *,uint,ulong,int,int)
0x18000df60  test    eax, eax
0x18000df62  jnz     short loc_18000DF6D
0x18000df64  or      [rsi+1Ch], r14d
0x18000df68  jmp     loc_18000DC17
0x18000df6d  cmp     [rsi], r15d
0x18000df70  jnz     short loc_18000DF99
0x18000df72  lea     rdx, aPostreboot; "Postreboot"
0x18000df79  mov     rcx, rbx; String1
0x18000df7c  call    cs:__imp__wcsicmp
0x18000df82  test    eax, eax
0x18000df84  jnz     short loc_18000DF99
0x18000df86  mov     dword ptr [rsi+0A8h], 3
0x18000df90  or      [rsi+1Ch], r15d
0x18000df94  jmp     loc_18000DC17
0x18000df99  test    dword ptr [rsi], 0FFFFFFFDh
0x18000df9f  jnz     short loc_18000DFC4
0x18000dfa1  mov     [rsp+1A58h+var_1A30], edi; int
0x18000dfa5  mov     [rsp+1A58h+var_1A38], r14d; int
0x18000dfaa  xor     r8d, r8d; unsigned int
0x18000dfad  lea     rdx, aQueue; "Queue"
0x18000dfb4  mov     rcx, rbx; unsigned __int16 *
0x18000dfb7  call    ?CaseCompareHelper@SString@@CAHPEBG0IKHH@Z; SString::CaseCompareHelper(ushort const *,ushort const *,uint,ulong,int,int)
0x18000dfbc  test    eax, eax
0x18000dfbe  jz      loc_18000E057
0x18000dfc4  cmp     [rsi], edi
0x18000dfc6  jnz     loc_18000E06D
0x18000dfcc  mov     [rsp+1A58h+var_1A30], edi; int
0x18000dfd0  mov     [rsp+1A58h+var_1A38], r14d; int
0x18000dfd5  xor     r8d, r8d; unsigned int
0x18000dfd8  lea     rdx, aQueue1; "Queue:1"
0x18000dfdf  mov     rcx, rbx; unsigned __int16 *
0x18000dfe2  call    ?CaseCompareHelper@SString@@CAHPEBG0IKHH@Z; SString::CaseCompareHelper(ushort const *,ushort const *,uint,ulong,int,int)
0x18000dfe7  test    eax, eax
0x18000dfe9  jnz     short loc_18000DFFE
0x18000dfeb  mov     [rsi+90h], r14d
0x18000dff2  mov     [rsi+0A8h], r14d
0x18000dff9  jmp     loc_18000DC17
0x18000dffe  cmp     [rsi], edi
0x18000e000  jnz     short loc_18000E06D
0x18000e002  mov     [rsp+1A58h+var_1A30], edi; int
0x18000e006  mov     [rsp+1A58h+var_1A38], r14d; int
0x18000e00b  xor     r8d, r8d; unsigned int
0x18000e00e  lea     rdx, aQueue2; "Queue:2"
0x18000e015  mov     rcx, rbx; unsigned __int16 *
0x18000e018  call    ?CaseCompareHelper@SString@@CAHPEBG0IKHH@Z; SString::CaseCompareHelper(ushort const *,ushort const *,uint,ulong,int,int)
0x18000e01d  test    eax, eax
0x18000e01f  jnz     short loc_18000E034
0x18000e021  mov     [rsi+90h], r14d
0x18000e028  mov     [rsi+0A8h], r15d
0x18000e02f  jmp     loc_18000DC17
0x18000e034  cmp     [rsi], edi
0x18000e036  jnz     short loc_18000E06D
0x18000e038  mov     [rsp+1A58h+var_1A30], edi; int
0x18000e03c  mov     [rsp+1A58h+var_1A38], r14d; int
0x18000e041  xor     r8d, r8d; unsigned int
0x18000e044  lea     rdx, aQueue3; "Queue:3"
0x18000e04b  mov     rcx, rbx; unsigned __int16 *
0x18000e04e  call    ?CaseCompareHelper@SString@@CAHPEBG0IKHH@Z; SString::CaseCompareHelper(ushort const *,ushort const *,uint,ulong,int,int)
0x18000e053  test    eax, eax
0x18000e055  jnz     short loc_18000E06D
0x18000e057  mov     [rsi+90h], r14d
0x18000e05e  mov     dword ptr [rsi+0A8h], 3
0x18000e068  jmp     loc_18000DC17
0x18000e06d  cmp     [rsi], r15d
0x18000e070  jnz     short loc_18000E09D
0x18000e072  mov     [rsp+1A58h+var_1A30], edi; int
0x18000e076  mov     [rsp+1A58h+var_1A38], r14d; int
0x18000e07b  xor     r8d, r8d; unsigned int
0x18000e07e  lea     rdx, aDelay; "Delay"
0x18000e085  mov     rcx, rbx; unsigned __int16 *
0x18000e088  call    ?CaseCompareHelper@SString@@CAHPEBG0IKHH@Z; SString::CaseCompareHelper(ushort const *,ushort const *,uint,ulong,int,int)
0x18000e08d  test    eax, eax
0x18000e08f  jnz     short loc_18000E09D
0x18000e091  mov     [rsi+94h], r14d
0x18000e098  jmp     loc_18000DC17
0x18000e09d  cmp     [rsi], edi
0x18000e09f  jnz     short loc_18000E0C9
0x18000e0a1  mov     [rsp+1A58h+var_1A30], edi; int
0x18000e0a5  mov     [rsp+1A58h+var_1A38], r14d; int
0x18000e0aa  xor     r8d, r8d; unsigned int
0x18000e0ad  lea     rdx, aNetfxpri1; "NetfxPri1"
0x18000e0b4  mov     rcx, rbx; unsigned __int16 *
0x18000e0b7  call    ?CaseCompareHelper@SString@@CAHPEBG0IKHH@Z; SString::CaseCompareHelper(ushort const *,ushort const *,uint,ulong,int,int)
0x18000e0bc  test    eax, eax
0x18000e0be  jnz     short loc_18000E0C9
0x18000e0c0  or      [rsi+20h], r15d
0x18000e0c4  jmp     loc_18000DC17
  ... truncated ...
```
