# _AddEntryInLookupCache(HKEY__ *,ushort const *,ushort const *,ushort const *,void *,ulong,ushort const *,ushort const *,int *)

- ea: `0x180004e80`
- end: `0x180006a7a`
- name: `?_AddEntryInLookupCache@@YAJPEAUHKEY__@@PEBG11PEAXK11PEAH@Z`
- size: `7162`
- prototype: `__int64 __fastcall(HKEY hKey, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, void *, unsigned int, const unsigned __int16 *, const unsigned __int16 *, int *)`
- caller_count: `3`
- callee_count: `21`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000477c`
- `0x18000498c`
- `0x180018a20`

## callees

- `0x180003e70`
- `0x180004e80`
- `0x180006a80`
- `0x180006cb0`
- `0x180007690`
- `0x180007fc0`
- `0x18000a600`
- `0x18000a8f0`
- `0x18000b0c0`
- `0x18000b9b0`
- `0x18002f620`
- `0x180031260`
- `0x18003ca18`
- `0x18003ca64`
- `0x18003fcdc`
- `0x180042410`
- `0x18005be88`
- `0x18005c644`
- `0x18005e0e4`
- `0x18005e164`
- `0x180081010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180005616`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800056a4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800057e0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180005616`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800056a4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800057e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005801`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005801`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180005074`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180005074`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x18000554e`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x18000554e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000522d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000523c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800069df`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000522d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000523c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800069df`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004f8a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005733`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004f8a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180005733`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800069ea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800069ea`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180005520`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180006598`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180005520`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180006598`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x18000669c`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x18000669c`
- `ntdll!RtlInitUnicodeString` at `0x180005903`
- `ntdll!RtlInitUnicodeString` at `0x180005910`
- `ntdll!RtlInitUnicodeString` at `0x180005949`
- `ntdll!RtlInitUnicodeString` at `0x180005956`
- `ntdll!RtlInitUnicodeString` at `0x180005982`
- `ntdll!RtlInitUnicodeString` at `0x18000598f`
- `ntdll!RtlInitUnicodeString` at `0x180005903`
- `ntdll!RtlInitUnicodeString` at `0x180005910`
- `ntdll!RtlInitUnicodeString` at `0x180005949`
- `ntdll!RtlInitUnicodeString` at `0x180005956`
- `ntdll!RtlInitUnicodeString` at `0x180005982`
- `ntdll!RtlInitUnicodeString` at `0x18000598f`
- `ntdll!RtlConvertSharedToExclusive` at `0x180005089`
- `ntdll!RtlConvertSharedToExclusive` at `0x180005089`
- `ntdll!RtlConvertExclusiveToShared` at `0x180005f25`
- `ntdll!RtlConvertExclusiveToShared` at `0x180005f25`
- `ntdll!RtlCompareUnicodeString` at `0x180005921`
- `ntdll!RtlCompareUnicodeString` at `0x180005967`
- `ntdll!RtlCompareUnicodeString` at `0x1800059a0`
- `ntdll!RtlCompareUnicodeString` at `0x180005921`
- `ntdll!RtlCompareUnicodeString` at `0x180005967`
- `ntdll!RtlCompareUnicodeString` at `0x1800059a0`

## string_xrefs

- `0x180005156`: `onecore\ds\ext\cloudap\dll\lookups.cpp`
- `0x1800051ac`: `onecore\ds\ext\cloudap\dll\lookups.cpp`
- `0x18000576b`: `onecore\ds\ext\cloudap\dll\lookups.cpp`
- `0x180005818`: `onecore\ds\ext\cloudap\dll\lookups.cpp`
- `0x1800058b7`: `onecore\ds\ext\cloudap\dll\lookups.cpp`
- `0x1800059ed`: `onecore\ds\ext\cloudap\dll\lookups.cpp`
- `0x180005ad5`: `onecore\ds\ext\cloudap\dll\lookups.cpp`
- `0x180005bee`: `onecore\ds\ext\cloudap\dll\lookups.cpp`
- `0x180005c22`: `onecore\ds\ext\cloudap\dll\lookups.cpp`
- `0x180005c53`: `onecore\ds\ext\cloudap\dll\lookups.cpp`
- `0x180005cf6`: `onecore\ds\ext\cloudap\dll\lookups.cpp`
- `0x180005e9f`: `onecore\ds\ext\cloudap\dll\lookups.cpp`
- `0x180005edc`: `onecore\ds\ext\cloudap\dll\lookups.cpp`
- `0x180005f62`: `onecore\ds\ext\cloudap\dll\lookups.cpp`
- `0x180005fd6`: `onecore\ds\ext\cloudap\dll\lookups.cpp`
- `0x180006045`: `onecore\ds\ext\cloudap\dll\lookups.cpp`
- `0x180006094`: `onecore\ds\ext\cloudap\dll\lookups.cpp`
- `0x18000610b`: `onecore\ds\ext\cloudap\dll\lookups.cpp`
- `0x18000618c`: `onecore\ds\ext\cloudap\dll\lookups.cpp`
- `0x180006218`: `onecore\ds\ext\cloudap\dll\lookups.cpp`
- `0x1800062b9`: `onecore\ds\ext\cloudap\dll\lookups.cpp`
- `0x180006332`: `onecore\ds\ext\cloudap\dll\lookups.cpp`
- `0x18000639e`: `onecore\ds\ext\cloudap\dll\lookups.cpp`
- `0x180006402`: `onecore\ds\ext\cloudap\dll\lookups.cpp`
- `0x18000646c`: `onecore\ds\ext\cloudap\dll\lookups.cpp`
- `0x1800064b5`: `onecore\ds\ext\cloudap\dll\lookups.cpp`
- `0x1800064e6`: `onecore\ds\ext\cloudap\dll\lookups.cpp`
- `0x1800065bc`: `onecore\ds\ext\cloudap\dll\lookups.cpp`
- `0x1800065ff`: `onecore\ds\ext\cloudap\dll\lookups.cpp`
- `0x1800066ba`: `onecore\ds\ext\cloudap\dll\lookups.cpp`
- `0x1800066fc`: `onecore\ds\ext\cloudap\dll\lookups.cpp`
- `0x180006781`: `onecore\ds\ext\cloudap\dll\lookups.cpp`
- `0x1800067d3`: `onecore\ds\ext\cloudap\dll\lookups.cpp`
- `0x180006876`: `onecore\ds\ext\cloudap\dll\lookups.cpp`
- `0x1800068d4`: `onecore\ds\ext\cloudap\dll\lookups.cpp`
- `0x1800069ab`: `onecore\ds\ext\cloudap\dll\lookups.cpp`
- `0x1800061cd`: `Sid2Name`
- `0x18000628e`: `Sid2Name`
- `0x180006373`: `Sid2Name`
- `0x180006439`: `Sid2Name`
- `0x180006671`: `Sid2Name`
- `0x1800050fb`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x180005461`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x180005588`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x180005632`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x180005a53`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x180005b19`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x180005b61`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x180005bc4`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x180005c9a`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x180005d30`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x180005d68`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x180005dc7`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x180005dee`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x180006908`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x180006941`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x1800056ec`: `Name2Sid`
- `0x18000588c`: `Name2Sid`
- `0x180005e6f`: `Name2Sid`
- `0x180005f43`: `Name2Sid`
- `0x180006026`: `Name2Sid`
- `0x180006316`: `Name2Sid`
- `0x1800063df`: `Name2Sid`
- `0x18000578d`: `FindUserInCacheBySid`
- `0x1800067ee`: `FindUserInCacheBySid`
- `0x180005848`: `ConvertSidToStringSidW`
- `0x1800058d9`: `SetStringRegVal(Name2SID, AuthenticatingAuthority)`
- `0x180005af9`: `FindUserInCacheByName`
- `0x180005b76`: `RegOpenKeyExW`
- `0x180005d77`: `RegOpenKeyExW`
- `0x18000623c`: `RemoveUserFromName2SidCache`
- `0x1800060af`: `FindUserInCacheBySAMName`
- `0x180005eb7`: `SetStringRegVal(Name2SID)`
- `0x180005f7a`: `SetStringRegVal(Name2SID)`
- `0x18000605d`: `SetStringRegVal(Name2SID, SAMName)`
- `0x180005ef4`: `SetStringRegVal(SID2Name,IdentityName)`
- `0x1800062d1`: `SetStringRegVal(SID2Name, AuthenticatingAuthority)`
- `0x18000634a`: `SetStringRegVal(Name2SID, DisplayName)`
- `0x1800063b6`: `SetStringRegVal(SID2Name, DisplayName)`
- `0x18000641a`: `SetDWORDRegVal(Name2SID, Flags)`
- `0x180006484`: `SetDWORDRegVal(SID2Name, Flags)`
- `0x1800065dd`: `RegDeleteKeyW`
- `0x1800066de`: `RegDeleteKeyValueW`
- `0x180006720`: `CombinePaths`
- `0x180006799`: `SetStringRegVal(SID2Name)`
- `0x180005b2d`: `GetUserSid2NameSubKey`

## pseudocode

```c
__int64 __fastcall _AddEntryInLookupCache(
        HKEY hKey,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        void *a5,
        unsigned int a6,
        const unsigned __int16 *a7,
        const unsigned __int16 *a8,
        int *a9)
{
  const WCHAR *v11; // r14
  const WCHAR *v12; // r15
  int UserSid2NameSubKey; // eax
  LPCWSTR v14; // rbx
  unsigned __int64 v15; // rdi
  __int64 v16; // rdx
  const UCHAR *v17; // rsi
  int v18; // ebx
  int v19; // r13d
  unsigned int v20; // eax
  unsigned int v21; // edi
  __int64 v22; // rbx
  int v23; // ecx
  const unsigned __int16 *v24; // r9
  char v25; // al
  const UCHAR *v26; // rcx
  bool v27; // zf
  const char *v28; // r9
  char v29; // al
  const char *v30; // rcx
  bool v31; // zf
  char v32; // al
  LPCWSTR v33; // rbx
  unsigned __int16 **v34; // rdx
  int RegVal; // eax
  int v37; // eax
  int v38; // eax
  int v39; // eax
  void *v40; // rbx
  const UCHAR *v41; // rsi
  unsigned int v42; // ebx
  char v43; // al
  const UCHAR *v44; // rcx
  bool v45; // zf
  unsigned __int16 *v46; // rax
  const WCHAR *v47; // rbx
  HKEY v48; // rsi
  LSTATUS v49; // edi
  LSTATUS v50; // eax
  const UCHAR *v51; // r9
  char v52; // al
  const UCHAR *v53; // rcx
  bool v54; // zf
  const WCHAR *v55; // rdi
  LONG v56; // eax
  const char *v57; // r9
  LONG v58; // eax
  int HashString; // ebx
  const char *v60; // r9
  char v61; // al
  const char *v62; // rcx
  bool v63; // zf
  __int64 v64; // r8
  LONG v65; // eax
  signed int LastError; // eax
  const char *v67; // r9
  char v68; // al
  const char *v69; // rdx
  bool v70; // zf
  unsigned int v71; // eax
  char v72; // al
  const WCHAR *v73; // rdi
  const char *v74; // r9
  char v75; // cl
  const char *v76; // rdx
  bool v77; // zf
  const char *v78; // rax
  __int64 v79; // r8
  __int64 v80; // r10
  const char *v81; // r11
  int v82; // ecx
  WCHAR *v83; // rdx
  char v84; // cl
  const char *v85; // rdx
  bool v86; // zf
  const char *v87; // rax
  __int64 v88; // r8
  const char *v89; // rax
  __int64 v90; // r8
  const char *v91; // rax
  __int64 v92; // r8
  const char *v93; // r9
  const char *v94; // r9
  const char *v95; // r9
  const char *v96; // rax
  int v97; // r8d
  const char *v98; // r9
  const char *v99; // rax
  const char *v100; // rax
  HKEY v101; // r13
  const char *v102; // rax
  __int64 v103; // r8
  const char *v104; // rax
  __int64 v105; // r8
  const char *v106; // r9
  int v107; // eax
  const char *v108; // r9
  const char *v109; // r9
  int UserInCacheBySAMName; // eax
  const char *v111; // r9
  int v112; // eax
  const char *v113; // r9
  const char *v114; // r9
  int v115; // eax
  const char *v116; // rax
  __int64 v117; // r8
  __int64 v118; // rax
  const char *v119; // rax
  __int64 v120; // r8
  const char *v121; // r9
  const char *v122; // rax
  __int64 v123; // r8
  const unsigned __int16 *v124; // r9
  const char *v125; // r9
  const char *v126; // rax
  __int64 v127; // r8
  const char *v128; // r9
  const char *v129; // r9
  unsigned int v130; // eax
  LPCWSTR v131; // rdi
  __int64 v132; // rax
  const unsigned __int16 *v133; // rcx
  const char *v134; // rax
  __int64 v135; // r8
  __int64 v136; // r10
  const char *v137; // rax
  const char *v138; // rax
  __int64 v139; // r8
  const char *v140; // rax
  __int64 v141; // r8
  const unsigned __int16 *v142; // rdx
  const char *v143; // rax
  __int64 v144; // r8
  HKEY v145; // rcx
  const char *v146; // r9
  unsigned int MultiStringRegVal; // eax
  unsigned int v148; // eax
  const unsigned __int16 *v149; // rdx
  const unsigned __int16 *v150; // r9
  const char *v151; // r9
  const char *v152; // r9
  const char *v153; // r9
  const char *v154; // rax
  const char *v155; // r9
  __int64 v156; // rbx
  PHKEY phkResult; // [rsp+28h] [rbp-E0h]
  PHKEY phkResulta; // [rsp+28h] [rbp-E0h]
  PHKEY phkResultb; // [rsp+28h] [rbp-E0h]
  PHKEY phkResultc; // [rsp+28h] [rbp-E0h]
  PHKEY phkResultd; // [rsp+28h] [rbp-E0h]
  PHKEY phkResulte; // [rsp+28h] [rbp-E0h]
  PHKEY phkResultf; // [rsp+28h] [rbp-E0h]
  PHKEY phkResultg; // [rsp+28h] [rbp-E0h]
  PHKEY phkResulth; // [rsp+28h] [rbp-E0h]
  PHKEY phkResulti; // [rsp+28h] [rbp-E0h]
  PHKEY phkResultj; // [rsp+28h] [rbp-E0h]
  PHKEY phkResultk; // [rsp+28h] [rbp-E0h]
  PHKEY phkResultl; // [rsp+28h] [rbp-E0h]
  PHKEY phkResultm; // [rsp+28h] [rbp-E0h]
  const char *v171; // [rsp+30h] [rbp-D8h]
  const char *v172; // [rsp+30h] [rbp-D8h]
  const WCHAR *v173; // [rsp+38h] [rbp-D0h]
  LPCWSTR v174; // [rsp+48h] [rbp-C0h]
  BOOL v175; // [rsp+50h] [rbp-B8h]
  unsigned int v176; // [rsp+54h] [rbp-B4h]
  void *v177; // [rsp+58h] [rbp-B0h] BYREF
  LPCWSTR lpSubKey; // [rsp+60h] [rbp-A8h] BYREF
  LPWSTR StringSid; // [rsp+68h] [rbp-A0h] BYREF
  unsigned int v180[2]; // [rsp+70h] [rbp-98h] BYREF
  HKEY v181; // [rsp+78h] [rbp-90h]
  unsigned int v182; // [rsp+80h] [rbp-88h] BYREF
  void *v183; // [rsp+88h] [rbp-80h] BYREF
  HKEY hKeya; // [rsp+90h] [rbp-78h] BYREF
  void *v185; // [rsp+98h] [rbp-70h] BYREF
  LPCWSTR v186; // [rsp+A0h] [rbp-68h] BYREF
  unsigned __int16 **v187; // [rsp+A8h] [rbp-60h] BYREF
  PCWSTR v188; // [rsp+B0h] [rbp-58h]
  PCWSTR v189; // [rsp+B8h] [rbp-50h]
  unsigned __int16 *v190; // [rsp+C0h] [rbp-48h] BYREF
  PCWSTR v191; // [rsp+C8h] [rbp-40h]
  HKEY v192; // [rsp+D0h] [rbp-38h] BYREF
  HKEY hkey; // [rsp+D8h] [rbp-30h] BYREF
  PCWSTR v194; // [rsp+E0h] [rbp-28h] BYREF
  PCWSTR v195; // [rsp+E8h] [rbp-20h] BYREF
  PCWSTR lpSrcStr; // [rsp+F0h] [rbp-18h]
  PSID Sid; // [rsp+F8h] [rbp-10h]
  UNICODE_STRING String2; // [rsp+100h] [rbp-8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+110h] [rbp+8h] BYREF
  UNICODE_STRING v200; // [rsp+120h] [rbp+18h] BYREF
  UNICODE_STRING String1; // [rsp+130h] [rbp+28h] BYREF
  UNICODE_STRING v202; // [rsp+140h] [rbp+38h] BYREF
  UNICODE_STRING v203; // [rsp+150h] [rbp+48h] BYREF
  WCHAR SourceString[72]; // [rsp+168h] [rbp+60h] BYREF
  WCHAR SubKey[80]; // [rsp+1F8h] [rbp+F0h] BYREF
  unsigned __int16 v206[72]; // [rsp+298h] [rbp+190h] BYREF

  v189 = a2;
  v181 = hKey;
  v11 = 0;
  lpSrcStr = a7;
  v12 = 0;
  *a9 = 0;
  v188 = a4;
  Sid = a5;
  v191 = a8;
  v176 = 0;
  v182 = 0;
  v192 = 0;
  hkey = 0;
  StringSid = 0;
  v177 = 0;
  v194 = 0;
  v190 = 0;
  v195 = 0;
  v183 = 0;
  v187 = 0;
  v174 = 0;
  v186 = 0;
  lpSubKey = 0;
  hKeya = 0;
  if ( !hKey || !a5 )
  {
    LODWORD(v15) = -1073741811;
    v41 = "";
    v42 = -1073741811;
    while ( 1 )
    {
      v43 = *(v41 - 1);
      v44 = v41--;
      v45 = v43 == 92;
      if ( v43 == 92 )
        break;
      if ( v41 <= "onecore\\ds\\ext\\cloudap\\dll\\utils.cpp" )
      {
        v45 = v43 == 92;
        break;
      }
    }
    if ( v45 )
      v41 = v44;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225485LL, v41, 1457, "Invalid Arg(s)", &Class);
    goto LABEL_141;
  }
  UserSid2NameSubKey = GetUserSid2NameSubKey(a5, (unsigned __int16 **)&lpSubKey);
  v14 = lpSubKey;
  LODWORD(v15) = UserSid2NameSubKey;
  if ( UserSid2NameSubKey )
  {
    v87 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", (unsigned int)v15, v87, 1463, "GetUserSid2NameSubKey", v88);
  }
  else
  {
    LODWORD(v15) = RegOpenKeyExW(hKey, lpSubKey, 0, 0x20019u, &hKeya);
    if ( (_DWORD)v15 )
    {
      v89 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
      LODWORD(phkResult) = 1473;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", (unsigned int)v15, v89, phkResult, "RegOpenKeyExW", v90);
      if ( (unsigned int)(v15 - 2) <= 1 )
      {
        LODWORD(v15) = -1073741275;
      }
      else if ( (int)v15 > 0 )
      {
        LODWORD(v15) = (unsigned __int16)v15 | 0xC0070000;
      }
      v91 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
      LODWORD(phkResulte) = 1483;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", (unsigned int)v15, v91, phkResulte, "RegOpenKeyExW", v92);
    }
  }
  if ( v14 )
    ((void (__fastcall *)(LPCWSTR))g_pLsaFunctionTable->FreeLsaHeap)(v14);
  if ( (_DWORD)v15 != -1073741275 && (_DWORD)v15 )
  {
    v42 = v15;
LABEL_141:
    v60 = "";
    while ( 1 )
    {
      v61 = *(v60 - 1);
      v62 = v60--;
      v63 = v61 == 92;
      if ( v61 == 92 )
        break;
      if ( v60 <= "onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp" )
      {
        v63 = v61 == 92;
        break;
      }
    }
    v172 = "FindUserInCacheBySid";
    if ( v63 )
      v60 = v62;
    LODWORD(phkResult) = 1474;
    v64 = v42;
LABEL_148:
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v64, v60, phkResult, v172, &Class);
LABEL_149:
    v33 = 0;
    goto LABEL_59;
  }
  v17 = "";
  v180[0] = 0;
  if ( !hKeya )
  {
    v18 = 0;
    v180[1] = 0;
    goto LABEL_10;
  }
  LODWORD(lpSubKey) = 0;
  RegVal = GetRegVal(hKeya, L"IdentityName", 6u, (unsigned int *)&lpSubKey, &v177);
  LODWORD(v15) = 0;
  if ( RegVal != -1073741275 )
    LODWORD(v15) = RegVal;
  if ( (_DWORD)v15 )
  {
    v93 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
    LODWORD(phkResulta) = 1486;
    WPPTraceLogA(
      0,
      "0x%08x %s:%u : %s:%ws",
      (unsigned int)v15,
      v93,
      phkResulta,
      "GetStringRegVal(IdentityName)",
      &Class);
LABEL_190:
    v11 = (const WCHAR *)v177;
    v33 = 0;
    goto LABEL_59;
  }
  LODWORD(lpSubKey) = 0;
  v37 = GetRegVal(hKeya, L"AuthenticatingAuthority", 6u, (unsigned int *)&lpSubKey, (void **)&v194);
  LODWORD(v15) = 0;
  if ( v37 != -1073741275 )
    LODWORD(v15) = v37;
  if ( (_DWORD)v15 )
  {
    v74 = "";
    while ( 1 )
    {
      v75 = *(v74 - 1);
      v76 = v74--;
      v77 = v75 == 92;
      if ( v75 == 92 )
        break;
      if ( v74 <= "onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp" )
      {
        v77 = v75 == 92;
        break;
      }
    }
    if ( v77 )
      v74 = v76;
    LODWORD(phkResultb) = 1496;
    WPPTraceLogA(
      0,
      "0x%08x %s:%u : %s:%ws",
      (unsigned int)v15,
      v74,
      phkResultb,
      "GetStringRegVal(AuthenticatingAuthority)",
      &Class);
    goto LABEL_190;
  }
  LODWORD(lpSubKey) = 0;
  v38 = GetRegVal(hKeya, L"DisplayName", 6u, (unsigned int *)&lpSubKey, &v183);
  LODWORD(v15) = 0;
  if ( v38 != -1073741275 )
    LODWORD(v15) = v38;
  if ( (_DWORD)v15 )
  {
    v94 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
    LODWORD(phkResultc) = 1506;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", (unsigned int)v15, v94, phkResultc, "GetStringRegVal(DisplayName)", &Class);
    goto LABEL_212;
  }
  LODWORD(lpSubKey) = 0;
  v185 = 0;
  v180[1] = 0;
  v39 = GetRegVal(hKeya, L"Flags", 0x10u, (unsigned int *)&lpSubKey, &v185);
  v40 = v185;
  LODWORD(v15) = v39;
  if ( v39 )
  {
    v51 = "";
    while ( 1 )
    {
      v52 = *(v51 - 1);
      v53 = v51--;
      v54 = v52 == 92;
      if ( v52 == 92 )
        break;
      if ( v51 <= "onecore\\ds\\ext\\cloudap\\dll\\utils.cpp" )
      {
        v54 = v52 == 92;
        break;
      }
    }
    if ( v54 )
      v51 = v53;
    LODWORD(phkResult) = 474;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", (unsigned int)v15, v51, phkResult, "GetRegVal", &Class);
  }
  else if ( (_DWORD)lpSubKey == 4 )
  {
    LODWORD(v15) = 0;
    v180[1] = *(_DWORD *)v185;
  }
  else
  {
    LODWORD(v15) = -1073741275;
    v96 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%u", -1073741275, v96, 479, "Bad DWORD size", v97);
  }
  if ( v40 )
    ((void (__fastcall *)(void *))g_pLsaFunctionTable->FreeLsaHeap)(v40);
  if ( (_DWORD)v15 != -1073741275 )
  {
    if ( !(_DWORD)v15 )
    {
      v11 = (const WCHAR *)v177;
      v18 = 0;
      v12 = (const WCHAR *)v183;
      goto LABEL_10;
    }
    v95 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
    LODWORD(phkResult) = 1517;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", (unsigned int)v15, v95, phkResult, "GetDWordRegVal(Flags)", &Class);
LABEL_212:
    v11 = (const WCHAR *)v177;
    v12 = (const WCHAR *)v183;
    goto LABEL_149;
  }
  v11 = (const WCHAR *)v177;
  v12 = (const WCHAR *)v183;
  v18 = 0;
  v180[0] = 1;
LABEL_10:
  LODWORD(lpSubKey) = 0;
  if ( !v11 )
  {
LABEL_11:
    v175 = 1;
    goto LABEL_12;
  }
  LODWORD(v15) = GetHashString(v11, SourceString);
  if ( (_DWORD)v15 )
  {
    v98 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
    LODWORD(phkResult) = 1526;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", (unsigned int)v15, v98, phkResult, "GetHashString", &Class);
    goto LABEL_149;
  }
  DestinationString = 0;
  String2 = 0;
  if ( (g_ulTestFlags & 2) != 0 )
  {
    v58 = _o__wcsicmp(SourceString, a3);
  }
  else
  {
    if ( !a3 )
      goto LABEL_177;
    RtlInitUnicodeString(&DestinationString, SourceString);
    RtlInitUnicodeString(&String2, a3);
    v58 = RtlCompareUnicodeString(&DestinationString, &String2, 1u);
  }
  if ( v58 )
  {
LABEL_177:
    *a9 = 1;
    LODWORD(lpSubKey) = 1;
    goto LABEL_11;
  }
  v192 = 0;
  if ( !v188 )
  {
    v100 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
    LODWORD(v15) = -1073741811;
    LODWORD(phkResult) = 1273;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225485LL, v100, phkResult, "Invalid Arg(s)", &Class);
    goto LABEL_196;
  }
  HashString = GetHashString(v188, v206);
  if ( HashString )
  {
    v78 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
    v82 = 1279;
    v177 = "GetHashString";
    v83 = (WCHAR *)&Class;
    v15 = (unsigned __int64)"GetHashString";
  }
  else
  {
    HashString = RtlStringCchPrintfW(SubKey, 0x4Au, L"%ws\\%ws", L"Name2Sid", v206);
    if ( HashString )
    {
      v78 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
      v82 = 1287;
      v177 = "RtlStringCchPrintfW";
      v83 = (WCHAR *)&Class;
      v15 = (unsigned __int64)"RtlStringCchPrintfW";
    }
    else
    {
      HashString = RegOpenKeyExW(v181, SubKey, 0, 0x20019u, &v192);
      if ( !HashString )
      {
        v18 = 0;
        v175 = 0;
        goto LABEL_12;
      }
      v99 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
      v15 = (unsigned __int64)"RegOpenKeyExW";
      LODWORD(phkResult) = 1298;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", (unsigned int)HashString, v99, phkResult, "RegOpenKeyExW", SubKey);
      if ( (unsigned int)(HashString - 2) <= 1 )
      {
        HashString = -1073741275;
      }
      else if ( HashString > 0 )
      {
        HashString = (unsigned __int16)HashString | 0xC0070000;
      }
      v78 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
      v83 = SubKey;
      v82 = 1308;
    }
  }
  LODWORD(phkResult) = v82;
  WPPTraceLogA(v80, v81, v79, v78, phkResult, v15, v83);
  LODWORD(v15) = 0;
  v175 = HashString == -1073741275;
  if ( HashString != -1073741275 )
    LODWORD(v15) = HashString;
  if ( (_DWORD)v15 )
  {
LABEL_196:
    v60 = "";
    while ( 1 )
    {
      v84 = *(v60 - 1);
      v85 = v60--;
      v86 = v84 == 92;
      if ( v84 == 92 )
        break;
      if ( v60 <= "onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp" )
      {
        v86 = v84 == 92;
        break;
      }
    }
    v172 = "FindUserInCacheByName";
    if ( v86 )
      v60 = v85;
    LODWORD(phkResult) = 1549;
    v64 = (unsigned int)v15;
    goto LABEL_148;
  }
  v18 = 0;
LABEL_12:
  LODWORD(v183) = 0;
  if ( !v194 )
  {
    LODWORD(v185) = 1;
    if ( !v11 )
    {
LABEL_15:
      v19 = v175;
      goto LABEL_16;
    }
LABEL_14:
    *a9 = 1;
    goto LABEL_15;
  }
  String1 = 0;
  v200 = 0;
  if ( (g_ulTestFlags & 2) != 0 )
  {
    v65 = _o__wcsicmp(v194, v189);
  }
  else
  {
    v73 = v189;
    if ( !v189 )
      goto LABEL_223;
    RtlInitUnicodeString(&String1, v194);
    RtlInitUnicodeString(&v200, v73);
    v65 = RtlCompareUnicodeString(&String1, &v200, 1u);
  }
  if ( v65 )
  {
LABEL_223:
    LODWORD(v185) = 1;
    goto LABEL_14;
  }
  v19 = v175;
  LODWORD(v185) = v175;
LABEL_16:
  if ( v12 )
  {
    v55 = v191;
    LODWORD(v177) = 0;
    if ( v191 )
    {
      v203 = 0;
      v202 = 0;
      if ( (g_ulTestFlags & 2) != 0 )
      {
        v56 = _o__wcsicmp(v12, v191);
      }
      else
      {
        RtlInitUnicodeString(&v203, v12);
        RtlInitUnicodeString(&v202, v55);
        v56 = RtlCompareUnicodeString(&v203, &v202, 1u);
      }
      if ( v56 )
        LODWORD(v177) = 1;
    }
  }
  else
  {
    LODWORD(v177) = 1;
  }
  v20 = v180[0];
  v21 = a6;
  if ( a6 != v180[1] )
    v20 = 1;
  v180[0] = v20;
  if ( lpSrcStr )
  {
    if ( *lpSrcStr )
    {
      if ( (unsigned int)CloudAPCompareStrings(v188, lpSrcStr) )
        v18 = 1;
      LODWORD(v183) = v18;
    }
    v20 = v180[0];
  }
  v22 = -1;
  if ( !v19 && !(_DWORD)v185 )
  {
    v23 = (int)v183;
    if ( !(_DWORD)v183 && !(_DWORD)v177 && !v20 )
      goto LABEL_32;
  }
  if ( !ConvertSidToStringSidW(Sid, &StringSid) )
  {
    LastError = GetLastError();
    LODWORD(v15) = LastError;
    if ( LastError > 0 )
      LODWORD(v15) = (unsigned __int16)LastError | 0xC0070000;
    v67 = "";
    while ( 1 )
    {
      v68 = *(v67 - 1);
      v69 = v67--;
      v70 = v68 == 92;
      if ( v68 == 92 )
        break;
      if ( v67 <= "onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp" )
      {
        v70 = v68 == 92;
        break;
      }
    }
    if ( v70 )
      v67 = v69;
    LODWORD(phkResult) = 1622;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", (unsigned int)v15, v67, phkResult, "ConvertSidToStringSidW", &Class);
    goto LABEL_149;
  }
  RtlConvertSharedToExclusive(&g_LookupsCacheLock);
  v16 = 1;
  v19 = 1;
  if ( v175 )
  {
    v101 = v181;
    LODWORD(v15) = SetStringRegVal(v181, L"Name2Sid", a3, L"Sid", StringSid);
    if ( (_DWORD)v15 )
    {
      v102 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
      LODWORD(phkResultf) = 1638;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", (unsigned int)v15, v102, phkResultf, "SetStringRegVal(Name2SID)", v103);
    }
    else
    {
      LODWORD(v15) = SetStringRegVal(v101, L"Name2Sid", a3, L"IdentityName", v188);
      if ( (_DWORD)v15 )
      {
        if ( !a3 )
          a3 = &Class;
        v106 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
        LODWORD(phkResultg) = 1649;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", (unsigned int)v15, v106, phkResultg, "SetStringRegVal(Name2SID)", a3);
        goto LABEL_227;
      }
      if ( hKeya )
      {
        v180[1] = 0;
        v107 = GetRegVal(hKeya, L"SAMName", 6u, &v180[1], (void **)&v190);
        LODWORD(v15) = 0;
        if ( v107 != -1073741275 )
          LODWORD(v15) = v107;
        if ( (_DWORD)v15 )
        {
          v108 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
          LODWORD(phkResulth) = 1667;
          WPPTraceLogA(
            0,
            "0x%08x %s:%u : %s:%ws",
            (unsigned int)v15,
            v108,
            phkResulth,
            "GetStringRegVal(SAMName)",
            &Class);
          goto LABEL_227;
        }
        if ( v190 )
        {
          LODWORD(v15) = SetStringRegVal(v101, L"Name2Sid", a3, L"SAMName", v190);
          if ( (_DWORD)v15 )
          {
            if ( !a3 )
              a3 = &Class;
            v109 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
            LODWORD(phkResulti) = 1677;
            WPPTraceLogA(
              0,
              "0x%08x %s:%u : %s:%ws",
              (unsigned int)v15,
              v109,
              phkResulti,
              "SetStringRegVal(Name2SID, SAMName)",
              a3);
            goto LABEL_227;
          }
          UserInCacheBySAMName = FindUserInCacheBySAMName(v101, v190, &hkey);
          LODWORD(v15) = 0;
          if ( UserInCacheBySAMName != -1073741275 )
            LODWORD(v15) = UserInCacheBySAMName;
          if ( (_DWORD)v15 )
          {
            v111 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
            LODWORD(phkResulti) = 1691;
            WPPTraceLogA(
              0,
              "0x%08x %s:%u : %s:%ws",
              (unsigned int)v15,
              v111,
              phkResulti,
              "FindUserInCacheBySAMName",
              &Class);
            goto LABEL_227;
          }
          if ( hkey )
          {
            v180[1] = 0;
            v112 = GetRegVal(hkey, L"Sid", 6u, &v180[1], (void **)&v195);
            LODWORD(v15) = 0;
            if ( v112 != -1073741275 )
              LODWORD(v15) = v112;
            if ( (_DWORD)v15 )
            {
              v113 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
              LODWORD(phkResultj) = 1703;
              WPPTraceLogA(
                0,
                "0x%08x %s:%u : %s:%ws",
                (unsigned int)v15,
                v113,
                phkResultj,
                "GetStringRegVal(SAMName)",
                &Class);
              goto LABEL_227;
            }
            if ( v195 )
            {
              if ( !(unsigned int)CloudAPCompareStrings(StringSid, v195) )
              {
                LODWORD(v15) = SetStringRegVal(v101, L"SAM_Name", v190, L"IdentityName", v188);
                if ( (_DWORD)v15 )
                {
                  if ( !a3 )
                    a3 = &Class;
                  v114 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
                  LODWORD(phkResultk) = 1714;
                  WPPTraceLogA(
                    0,
                    "0x%08x %s:%u : %s:%ws",
                    (unsigned int)v15,
                    v114,
                    phkResultk,
                    "SetStringRegVal(SAMName, IdentityName)",
                    a3);
                  goto LABEL_227;
                }
              }
            }
          }
        }
      }
      LODWORD(v15) = SetStringRegVal(v101, L"Sid2Name", StringSid, L"IdentityName", v188);
      if ( !(_DWORD)v15 )
      {
        v16 = 1;
        v19 = 1;
        if ( (_DWORD)lpSubKey )
        {
          if ( v11 )
          {
            v115 = _RemoveUserFromName2SidCache(v181, v11, 0);
            v16 = 1;
            if ( v115 )
            {
              v116 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
              LODWORD(phkResult) = 1736;
              WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v117, v116, phkResult, "RemoveUserFromName2SidCache", &Class);
              v16 = 1;
            }
          }
        }
        v21 = a6;
        goto LABEL_28;
      }
      v104 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
      LODWORD(phkResult) = 1730;
      WPPTraceLogA(
        0,
        "0x%08x %s:%u : %s:%ws",
        (unsigned int)v15,
        v104,
        phkResult,
        "SetStringRegVal(SID2Name,IdentityName)",
        v105);
    }
LABEL_227:
    v33 = 0;
LABEL_228:
    RtlConvertExclusiveToShared(&g_LookupsCacheLock);
    goto LABEL_59;
  }
LABEL_28:
  if ( !(_DWORD)v185 )
    goto LABEL_29;
  if ( v189 )
  {
    v118 = -1;
    do
      v27 = v189[++v118] == 0;
    while ( !v27 );
    v71 = 2 * v118 + 2;
  }
  else
  {
    v71 = 0;
  }
  LODWORD(v15) = SetRegValInt(v181, L"Name2Sid", a3, L"AuthenticatingAuthority", 1u, (unsigned __int8 *)v189, v71);
  if ( (_DWORD)v15 )
  {
    v28 = "";
    if ( !a3 )
      a3 = &Class;
    while ( 1 )
    {
      v72 = *(v28 - 1);
      v30 = v28--;
      v31 = v72 == 92;
      if ( v72 == 92 )
        break;
      if ( v28 <= "onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp" )
      {
        v31 = v72 == 92;
        break;
      }
    }
    v173 = a3;
    v171 = "SetStringRegVal(Name2SID, AuthenticatingAuthority)";
    LODWORD(phkResult) = 1749;
    goto LABEL_54;
  }
  LODWORD(v15) = SetStringRegVal(v181, L"Sid2Name", StringSid, L"AuthenticatingAuthority", v189);
  if ( !(_DWORD)v15 )
  {
    v21 = a6;
LABEL_29:
    if ( (_DWORD)v177 && v191 )
    {
      LODWORD(v15) = SetStringRegVal(v181, L"Name2Sid", a3, L"DisplayName", v191);
      if ( (_DWORD)v15 )
      {
        if ( !a3 )
          a3 = &Class;
        v121 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
        LODWORD(phkResultl) = 1772;
        WPPTraceLogA(
          0,
          "0x%08x %s:%u : %s:%ws",
          (unsigned int)v15,
          v121,
          phkResultl,
          "SetStringRegVal(Name2SID, DisplayName)",
          a3);
        goto LABEL_57;
      }
      LODWORD(v15) = SetStringRegVal(v181, L"Sid2Name", StringSid, L"DisplayName", v191);
      if ( (_DWORD)v15 )
      {
        v122 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
        LODWORD(phkResult) = 1781;
        WPPTraceLogA(
          0,
          "0x%08x %s:%u : %s:%ws",
          (unsigned int)v15,
          v122,
          phkResult,
          "SetStringRegVal(SID2Name, DisplayName)",
          v123);
        goto LABEL_57;
      }
      v21 = a6;
    }
    if ( v180[0] )
    {
      LODWORD(v15) = SetDWORDRegVal(v181, L"Name2Sid", a3, v24, v21);
      if ( (_DWORD)v15 )
      {
        if ( !a3 )
          a3 = &Class;
        v125 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
        LODWORD(phkResultm) = 1793;
        WPPTraceLogA(
          0,
          "0x%08x %s:%u : %s:%ws",
          (unsigned int)v15,
          v125,
          phkResultm,
          "SetDWORDRegVal(Name2SID, Flags)",
          a3);
        goto LABEL_57;
      }
      LODWORD(v15) = SetDWORDRegVal(v181, L"Sid2Name", StringSid, v124, a6);
      if ( (_DWORD)v15 )
      {
        v126 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
        LODWORD(phkResult) = 1802;
        WPPTraceLogA(
          0,
          "0x%08x %s:%u : %s:%ws",
          (unsigned int)v15,
          v126,
          phkResult,
          "SetDWORDRegVal(SID2Name, Flags)",
          v127);
        goto LABEL_57;
      }
    }
    v23 = (int)v183;
LABEL_32:
    if ( (_DWORD)lpSubKey )
    {
      LODWORD(v15) = GetMultiStringRegVal(hKeya, (const unsigned __int16 *)v16, &v187, &v182);
      if ( !(_DWORD)v15 )
      {
        v130 = v182;
        v131 = 0;
        while ( 1 )
        {
          v176 = v130;
          if ( !v130 )
            break;
          if ( v131 )
          {
            ((void (__fastcall *)(LPCWSTR))g_pLsaFunctionTable->FreeLsaHeap)(v131);
            v130 = v176;
            v131 = 0;
            v186 = 0;
          }
          v132 = v130 - 1;
          LODWORD(lpSubKey) = v132;
          v133 = v187[v132];
          if ( v133 )
          {
            LODWORD(v15) = GetUserAliasSubKey(v133, (unsigned __int16 **)&v186);
            if ( (_DWORD)v15 )
            {
              v137 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
              LODWORD(phkResult) = 1833;
              WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", (unsigned int)v15, v137, phkResult, "GetUserAliasSubKey", &Class);
              v33 = v186;
              goto LABEL_58;
            }
            v131 = v186;
            if ( RegDeleteKeyW(v181, v186) )
            {
              v134 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
              LODWORD(phkResult) = 1841;
              WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v135, v134, phkResult, "RegDeleteKeyW", v136);
            }
          }
          v130 = (unsigned int)lpSubKey;
        }
        if ( v131 )
        {
          ((void (__fastcall *)(LPCWSTR))g_pLsaFunctionTable->FreeLsaHeap)(v131);
          v186 = 0;
        }
        if ( (int)CombinePaths(L"Sid2Name", StringSid, (unsigned __int16 **)&v186) < 0 )
        {
          v140 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
          LODWORD(phkResult) = 1866;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v141, v140, phkResult, "CombinePaths", &Class);
          v174 = v186;
        }
        else
        {
          v174 = v186;
          if ( RegDeleteKeyValueW(v181, v186, L"AliasHashes") )
          {
            v138 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
            LODWORD(phkResult) = 1860;
            WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v139, v138, phkResult, "RegDeleteKeyValueW", L"AliasHashes");
          }
        }
        goto LABEL_34;
      }
      v128 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
      LODWORD(phkResult) = 1818;
      WPPTraceLogA(
        0,
        "0x%08x %s:%u : %s:%ws",
        (unsigned int)v15,
        v128,
        phkResult,
        "GetMultiStringRegVal(AliasHashes)",
        &Class);
    }
    else
    {
      if ( !v23 )
      {
        do
LABEL_34:
          ++v22;
        while ( a3[v22] );
        if ( (int)v22 + 12 >= (unsigned int)v22 )
        {
          v15 = 2LL * (unsigned int)(v22 + 12);
          if ( v15 > 0xFFFFFFFF )
          {
            LODWORD(v15) = -1073741675;
            v57 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
            LODWORD(phkResult) = 1726;
            WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225621LL, v57, phkResult, "RtlDWordMult", &Class);
          }
          else
          {
            v46 = (unsigned __int16 *)((__int64 (__fastcall *)(_QWORD))g_pLsaFunctionTable->AllocateLsaHeap)((unsigned int)v15);
            v47 = v46;
            if ( v46 )
            {
              LODWORD(v15) = RtlStringCchPrintfW(
                               v46,
                               (unsigned __int64)(unsigned int)v15 >> 1,
                               L"%ws\\%ws",
                               L"Alias2Name",
                               a3);
              if ( !(_DWORD)v15 )
              {
                v48 = v181;
                v49 = RegDeleteKeyW(v181, v47);
                ((void (__fastcall *)(const WCHAR *))g_pLsaFunctionTable->FreeLsaHeap)(v47);
                v174 = 0;
                if ( (v175 || (_DWORD)v185 || (_DWORD)v183 || (_DWORD)v177 || v180[0] || !v49)
                  && (v50 = RegFlushKey(v48), (LODWORD(v15) = v50) != 0) )
                {
                  if ( v50 > 0 )
                    LODWORD(v15) = (unsigned __int16)v50 | 0xC0070000;
                  v155 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
                  LODWORD(phkResultd) = 1957;
                  WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", (unsigned int)v15, v155, phkResultd, "RegFlushKey", &Class);
                }
                else
                {
                  LODWORD(v15) = 0;
                }
                goto LABEL_57;
              }
              v154 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
              LODWORD(phkResultd) = 1741;
              WPPTraceLogA(
                0,
                "0x%08x %s:%u : %s:%ws",
                (unsigned int)v15,
                v154,
                phkResultd,
                "RtlStringCchPrintfW",
                &Class);
              ((void (__fastcall *)(const WCHAR *))g_pLsaFunctionTable->FreeLsaHeap)(v47);
            }
            else
            {
              LODWORD(v15) = -1073741801;
              v153 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
              LODWORD(phkResult) = 1732;
              WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225495LL, v153, phkResult, "AllocateLsaHeap", &Class);
            }
          }
        }
        else
        {
          LODWORD(v15) = -1073741675;
          while ( 1 )
          {
            v25 = *(v17 - 1);
            v26 = v17--;
            v27 = v25 == 92;
            if ( v25 == 92 )
              break;
            if ( v17 <= "onecore\\ds\\ext\\cloudap\\dll\\utils.cpp" )
            {
              v27 = v25 == 92;
              break;
            }
          }
          if ( v27 )
            v17 = v26;
          LODWORD(phkResult) = 1723;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225621LL, v17, phkResult, "RtlDWordAdd", &Class);
        }
        v28 = "";
        while ( 1 )
        {
          v29 = *(v28 - 1);
          v30 = v28--;
          v31 = v29 == 92;
          if ( v29 == 92 )
            break;
          if ( v28 <= "onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp" )
          {
            v31 = v29 == 92;
            break;
          }
        }
        v173 = &Class;
        v171 = "GetUserAliasSubKey";
        LODWORD(phkResult) = 1934;
        goto LABEL_54;
      }
      LODWORD(v15) = GetHashString(lpSrcStr, SourceString);
      if ( (_DWORD)v15 )
      {
        v28 = "";
        while ( 1 )
        {
          v32 = *(v28 - 1);
          v30 = v28--;
          v31 = v32 == 92;
          if ( v32 == 92 )
            break;
          if ( v28 <= "onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp" )
          {
            v31 = v32 == 92;
            break;
          }
        }
        v173 = &Class;
        v171 = "GetHashString";
        LODWORD(phkResult) = 1873;
LABEL_54:
        if ( v31 )
          v28 = v30;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", (unsigned int)v15, v28, phkResult, v171, v173);
        goto LABEL_57;
      }
      LODWORD(v15) = SetStringRegVal(v181, L"Alias2Name", SourceString, L"IdentityName", v188);
      if ( (_DWORD)v15 )
      {
        v143 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
        LODWORD(phkResult) = 1882;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", (unsigned int)v15, v143, phkResult, "SetStringRegVal(SID2Name)", v144);
        goto LABEL_57;
      }
      v145 = hKeya;
      if ( !hKeya )
      {
        LODWORD(v15) = FindUserInCacheBySid(v181, Sid, &hKeya);
        if ( (_DWORD)v15 )
        {
          v146 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
          LODWORD(phkResult) = 1891;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", (unsigned int)v15, v146, phkResult, "FindUserInCacheBySid", &Class);
          goto LABEL_57;
        }
        v145 = hKeya;
      }
      MultiStringRegVal = GetMultiStringRegVal(v145, v142, &v187, &v182);
      v15 = MultiStringRegVal;
      if ( !MultiStringRegVal )
      {
        v176 = v182;
        v148 = v182 - 1;
        if ( v182 == 1 )
        {
LABEL_314:
          if ( (_DWORD)v15 == v148 )
          {
            LODWORD(v15) = DuplicateString(SourceString, 0, &v187[v15]);
            if ( (_DWORD)v15 )
            {
              v151 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
              LODWORD(phkResult) = 1917;
              WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", (unsigned int)v15, v151, phkResult, "DuplicateString", &Class);
              goto LABEL_57;
            }
            LODWORD(v15) = SetMultiStringRegVal(v181, v149, StringSid, v150, v187, v176);
            if ( (_DWORD)v15 )
            {
              v152 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
              LODWORD(phkResult) = 1926;
              WPPTraceLogA(
                0,
                "0x%08x %s:%u : %s:%ws",
                (unsigned int)v15,
                v152,
                phkResult,
                "SetMultiStringRegVal",
                &Class);
              goto LABEL_57;
            }
          }
        }
        else
        {
          while ( (unsigned int)CloudAPCompareStrings(v187[v15], SourceString) )
          {
            v15 = (unsigned int)(v15 + 1);
            v148 = v176 - 1;
            if ( (unsigned int)v15 >= v176 - 1 )
              goto LABEL_314;
          }
        }
        goto LABEL_34;
      }
      v129 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
      LODWORD(phkResult) = 1902;
      WPPTraceLogA(
        0,
        "0x%08x %s:%u : %s:%ws",
        (unsigned int)v15,
        v129,
        phkResult,
        "GetMultiStringRegVal(AliasHashes)",
        &Class);
    }
    v176 = v182;
    goto LABEL_57;
  }
  v119 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
  LODWORD(phkResult) = 1760;
  WPPTraceLogA(
    0,
    "0x%08x %s:%u : %s:%ws",
    (unsigned int)v15,
    v119,
    phkResult,
    "SetStringRegVal(SID2Name, AuthenticatingAuthority)",
    v120);
LABEL_57:
  v33 = v174;
LABEL_58:
  if ( v19 )
    goto LABEL_228;
LABEL_59:
  if ( hKeya )
    RegCloseKey(hKeya);
  if ( v192 )
    RegCloseKey(v192);
  if ( hkey )
    RegCloseKey(hkey);
  if ( StringSid )
    LocalFree(StringSid);
  if ( v11 )
    ((void (__fastcall *)(const WCHAR *))g_pLsaFunctionTable->FreeLsaHeap)(v11);
  if ( v194 )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  if ( v190 )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  if ( v195 )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  if ( v12 )
    ((void (__fastcall *)(const WCHAR *))g_pLsaFunctionTable->FreeLsaHeap)(v12);
  if ( v33 )
    ((void (__fastcall *)(LPCWSTR))g_pLsaFunctionTable->FreeLsaHeap)(v33);
  v34 = v187;
  if ( v187 )
  {
    LODWORD(v156) = v176;
    if ( v176 )
    {
      do
      {
        v156 = (unsigned int)(v156 - 1);
        if ( v34[v156] )
        {
          ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
          v34 = v187;
        }
      }
      while ( (_DWORD)v156 );
    }
    ((void (__fastcall *)(unsigned __int16 **))g_pLsaFunctionTable->FreeLsaHeap)(v34);
  }
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180004e80  mov     r11, rsp
0x180004e83  push    rbp
0x180004e84  push    rbx
0x180004e85  push    rdi
0x180004e86  lea     rbp, [r11-278h]
0x180004e8d  sub     rsp, 360h
0x180004e94  mov     rax, cs:__security_cookie
0x180004e9b  xor     rax, rsp
0x180004e9e  mov     [rbp+270h+var_50], rax
0x180004ea5  mov     rax, [rbp+270h+arg_30]
0x180004eac  mov     [r11-20h], rsi
0x180004eb0  mov     rsi, rcx
0x180004eb3  mov     [r11-28h], r12
0x180004eb7  mov     r12, r8
0x180004eba  mov     [r11-30h], r13
0x180004ebe  mov     r13, [rbp+270h+arg_40]
0x180004ec5  mov     [r11-38h], r14
0x180004ec9  mov     [rbp+270h+var_2C0], rdx
0x180004ecd  xor     edx, edx
0x180004ecf  mov     [rsp+370h+var_300], rcx
0x180004ed4  mov     r14d, edx
0x180004ed7  mov     rcx, [rbp+270h+arg_20]; void *
0x180004ede  mov     [rbp+270h+lpSrcStr], rax
0x180004ee2  mov     rax, [rbp+270h+arg_38]
0x180004ee9  mov     [r11-40h], r15
0x180004eed  mov     r15d, edx
0x180004ef0  mov     [r13+0], edx
0x180004ef4  mov     [rbp+270h+var_2C8], r9
0x180004ef8  mov     [rbp+270h+Sid], rcx
0x180004efc  mov     [rbp+270h+var_2B0], rax
0x180004f00  mov     [rsp+370h+var_328+4], edx
0x180004f04  mov     [rsp+370h+var_2F8], edx
0x180004f08  mov     [rbp+270h+var_2A8], rdx
0x180004f0c  mov     [rbp+270h+hkey], rdx
0x180004f10  mov     [rsp+370h+StringSid], rdx
0x180004f15  mov     [rsp+370h+var_320], rdx
0x180004f1a  mov     [rbp+270h+var_298], rdx
0x180004f1e  mov     [rbp+270h+var_2B8], rdx
0x180004f22  mov     [rbp+270h+var_290], rdx
0x180004f26  mov     [rbp+270h+var_2F0], rdx
0x180004f2a  mov     [rbp+270h+var_2D0], rdx
0x180004f2e  mov     qword ptr [rsp+370h+var_330], rdx
0x180004f33  mov     [rbp+270h+var_2D8], rdx
0x180004f37  mov     [rsp+370h+lpSubKey], rdx
0x180004f3c  mov     [rbp+270h+hKey], rdx
0x180004f40  test    rsi, rsi
0x180004f43  jz      loc_180005453
0x180004f49  test    rcx, rcx
0x180004f4c  jz      loc_180005453
0x180004f52  lea     rdx, [rsp+370h+lpSubKey]; unsigned __int16 **
0x180004f57  call    ?GetUserSid2NameSubKey@@YAJPEAXPEAPEAG@Z; GetUserSid2NameSubKey(void *,ushort * *)
0x180004f5c  mov     rbx, [rsp+370h+lpSubKey]
0x180004f61  mov     edi, eax
0x180004f63  lea     r8, Class
0x180004f6a  test    eax, eax
0x180004f6c  jnz     loc_180005B19
0x180004f72  lea     rax, [rbp+270h+hKey]
0x180004f76  mov     r9d, 20019h; samDesired
0x180004f7c  xor     r8d, r8d; ulOptions
0x180004f7f  mov     [rsp+370h+phkResult], rax; phkResult
0x180004f84  mov     rdx, rbx; lpSubKey
0x180004f87  mov     rcx, rsi; hKey
0x180004f8a  call    cs:__imp_RegOpenKeyExW
0x180004f90  mov     edi, eax
0x180004f92  test    eax, eax
0x180004f94  jnz     loc_180005B57
0x180004f9a  test    rbx, rbx
0x180004f9d  jz      short loc_180004FB2
0x180004f9f  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x180004fa6  mov     rcx, rbx
0x180004fa9  mov     rax, [rax+30h]
0x180004fad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fb2  cmp     edi, 0C0000225h
0x180004fb8  jnz     loc_180005753
0x180004fbe  mov     rcx, [rbp+270h+hKey]; hkey
0x180004fc2  lea     rsi, pbInput+24h; ""
0x180004fc9  mov     [rsp+370h+var_308], r14d
0x180004fce  mov     eax, 1
0x180004fd3  test    rcx, rcx
0x180004fd6  jnz     loc_180005302
0x180004fdc  xor     ebx, ebx
0x180004fde  mov     [rsp+370h+var_308+4], ebx
0x180004fe2  mov     dword ptr [rsp+370h+lpSubKey], ebx
0x180004fe6  test    r14, r14
0x180004fe9  jnz     loc_18000566B
0x180004fef  mov     [rsp+370h+var_328], eax
0x180004ff3  mov     rcx, [rbp+270h+var_298]
0x180004ff7  mov     dword ptr [rbp+270h+var_2F0], ebx
0x180004ffa  test    rcx, rcx
0x180004ffd  jnz     loc_1800057C0
0x180005003  mov     dword ptr [rbp+270h+var_2E0], eax
0x180005006  test    r14, r14
0x180005009  jz      short loc_18000500F
0x18000500b  mov     [r13+0], eax
0x18000500f  mov     r13d, [rsp+370h+var_328]
0x180005014  test    r15, r15
0x180005017  jnz     loc_1800055DF
0x18000501d  mov     dword ptr [rsp+370h+var_320], eax
0x180005021  mov     ecx, 1
0x180005026  mov     eax, [rsp+370h+var_308]
0x18000502a  mov     edi, [rbp+270h+arg_28]
0x180005030  cmp     edi, [rsp+370h+var_308+4]
0x180005034  cmovnz  eax, ecx
0x180005037  mov     rcx, [rbp+270h+lpSrcStr]
0x18000503b  mov     [rsp+370h+var_308], eax
0x18000503f  test    rcx, rcx
0x180005042  jnz     loc_1800059BD
0x180005048  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18000504f  test    r13d, r13d
0x180005052  jnz     short loc_18000506B
0x180005054  cmp     dword ptr [rbp+270h+var_2E0], r13d
0x180005058  jnz     short loc_18000506B
0x18000505a  mov     ecx, dword ptr [rbp+270h+var_2F0]
0x18000505d  test    ecx, ecx
0x18000505f  jnz     short loc_18000506B
0x180005061  cmp     dword ptr [rsp+370h+var_320], ecx
0x180005065  jnz     short loc_18000506B
0x180005067  test    eax, eax
0x180005069  jz      short loc_1800050C5
0x18000506b  mov     rcx, [rbp+270h+Sid]; Sid
0x18000506f  lea     rdx, [rsp+370h+StringSid]; StringSid
0x180005074  call    cs:__imp_ConvertSidToStringSidW
0x18000507a  test    eax, eax
0x18000507c  jz      loc_180005801
0x180005082  lea     rcx, ?g_LookupsCacheLock@@3U_RTL_RESOURCE@@A; Resource
0x180005089  call    cs:__imp_RtlConvertSharedToExclusive
0x18000508f  cmp     [rsp+370h+var_328], 0
0x180005094  mov     edx, 1; unsigned __int16 *
0x180005099  mov     r13d, edx
0x18000509c  jnz     loc_180005E5E
0x1800050a2  cmp     dword ptr [rbp+270h+var_2E0], 0
0x1800050a6  jnz     loc_180005861
0x1800050ac  cmp     dword ptr [rsp+370h+var_320], 0
0x1800050b1  jnz     loc_1800062F5
0x1800050b7  cmp     [rsp+370h+var_308], 0
0x1800050bc  jnz     loc_1800063DA
0x1800050c2  mov     ecx, dword ptr [rbp+270h+var_2F0]
0x1800050c5  cmp     dword ptr [rsp+370h+lpSubKey], 0
0x1800050ca  jnz     loc_18000649D
0x1800050d0  test    ecx, ecx
0x1800050d2  jnz     loc_18000518E
0x1800050d8  nop     dword ptr [rax+rax+00000000h]
0x1800050e0  inc     rbx
0x1800050e3  cmp     word ptr [r12+rbx*2], 0
0x1800050e9  jnz     short loc_1800050E0
0x1800050eb  lea     eax, [rbx+0Ch]
0x1800050ee  cmp     eax, ebx
0x1800050f0  jnb     loc_1800054BA
0x1800050f6  mov     edi, 0C0000095h
0x1800050fb  lea     rdx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x180005102  movzx   eax, byte ptr [rsi-1]
0x180005106  mov     rcx, rsi
0x180005109  dec     rsi
0x18000510c  cmp     al, 5Ch ; '\'
0x18000510e  jz      short loc_180005117
0x180005110  cmp     rsi, rdx
0x180005113  ja      short loc_180005102
0x180005115  cmp     al, 5Ch ; '\'
0x180005117  lea     rbx, Class
0x18000511e  cmovz   rsi, rcx
0x180005122  mov     [rsp+30h], rbx
0x180005127  lea     rax, aRtldwordadd; "RtlDWordAdd"
0x18000512e  mov     [rsp+370h+var_348], rax
0x180005133  mov     r9, rsi
0x180005136  mov     dword ptr [rsp+370h+phkResult], 6BBh
0x18000513e  mov     r8d, edi
0x180005141  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x180005148  xor     ecx, ecx
0x18000514a  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18000514f  lea     r9, aOnecoreDsExtCl_5+26h; ""
0x180005156  lea     rdx, aOnecoreDsExtCl_5; "onecore\\ds\\ext\\cloudap\\dll\\lookups"...
0x18000515d  movzx   eax, byte ptr [r9-1]
0x180005162  mov     rcx, r9
0x180005165  dec     r9
0x180005168  cmp     al, 5Ch ; '\'
0x18000516a  jz      short loc_180005173
0x18000516c  cmp     r9, rdx
0x18000516f  ja      short loc_18000515D
0x180005171  cmp     al, 5Ch ; '\'
0x180005173  mov     [rsp+30h], rbx
0x180005178  lea     rax, aGetuseraliassu; "GetUserAliasSubKey"
0x18000517f  mov     [rsp+370h+var_348], rax
0x180005184  mov     dword ptr [rsp+370h+phkResult], 78Eh
0x18000518c  jmp     short loc_1800051E9
0x18000518e  mov     rcx, [rbp+270h+lpSrcStr]; lpSrcStr
0x180005192  lea     rdx, [rbp+270h+SourceString]; unsigned __int16 *
0x180005196  call    ?GetHashString@@YAJPEBGQEAG@Z; GetHashString(ushort const *,ushort * const)
0x18000519b  mov     edi, eax
0x18000519d  test    eax, eax
0x18000519f  jz      loc_180006747
0x1800051a5  lea     r9, aOnecoreDsExtCl_5+26h; ""
0x1800051ac  lea     rdx, aOnecoreDsExtCl_5; "onecore\\ds\\ext\\cloudap\\dll\\lookups"...
0x1800051b3  movzx   eax, byte ptr [r9-1]
0x1800051b8  mov     rcx, r9
0x1800051bb  dec     r9
0x1800051be  cmp     al, 5Ch ; '\'
0x1800051c0  jz      short loc_1800051C9
0x1800051c2  cmp     r9, rdx
0x1800051c5  ja      short loc_1800051B3
0x1800051c7  cmp     al, 5Ch ; '\'
0x1800051c9  lea     rax, Class
0x1800051d0  mov     [rsp+30h], rax
0x1800051d5  lea     rax, aGethashstring; "GetHashString"
0x1800051dc  mov     [rsp+370h+var_348], rax
0x1800051e1  mov     dword ptr [rsp+370h+phkResult], 751h
0x1800051e9  cmovz   r9, rcx
0x1800051ed  mov     r8d, edi
0x1800051f0  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x1800051f7  xor     ecx, ecx
0x1800051f9  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x1800051fe  mov     rbx, qword ptr [rsp+370h+var_330]
0x180005203  test    r13d, r13d
0x180005206  jnz     loc_180005F1E
0x18000520c  mov     rcx, [rbp+270h+hKey]; hKey
0x180005210  mov     r13, [rsp+370h+var_28]
0x180005218  mov     r12, [rsp+370h+var_20]
0x180005220  mov     rsi, [rsp+358h]
0x180005228  test    rcx, rcx
0x18000522b  jz      short loc_180005233
0x18000522d  call    cs:__imp_RegCloseKey
0x180005233  mov     rcx, [rbp+270h+var_2A8]; hKey
0x180005237  test    rcx, rcx
0x18000523a  jz      short loc_180005242
0x18000523c  call    cs:__imp_RegCloseKey
0x180005242  mov     rcx, [rbp+270h+hkey]; hKey
0x180005246  test    rcx, rcx
0x180005249  jnz     loc_1800069DF
0x18000524f  mov     rcx, [rsp+370h+StringSid]; hMem
0x180005254  test    rcx, rcx
0x180005257  jnz     loc_1800069EA
0x18000525d  test    r14, r14
0x180005260  jz      short loc_180005275
0x180005262  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x180005269  mov     rcx, r14
0x18000526c  mov     rax, [rax+30h]
0x180005270  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005275  mov     rcx, [rbp+270h+var_298]
0x180005279  mov     r14, [rsp+370h+var_30]
0x180005281  test    rcx, rcx
0x180005284  jz      short loc_180005296
0x180005286  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18000528d  mov     rax, [rax+30h]
0x180005291  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005296  mov     rcx, [rbp+270h+var_2B8]
0x18000529a  test    rcx, rcx
0x18000529d  jnz     loc_1800069F5
0x1800052a3  mov     rcx, [rbp+270h+var_290]
0x1800052a7  test    rcx, rcx
0x1800052aa  jnz     loc_180006A0A
0x1800052b0  test    r15, r15
0x1800052b3  jz      short loc_1800052C8
0x1800052b5  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x1800052bc  mov     rcx, r15
0x1800052bf  mov     rax, [rax+30h]
0x1800052c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052c8  mov     r15, [rsp+370h+var_38]
0x1800052d0  test    rbx, rbx
0x1800052d3  jnz     loc_180006A1F
0x1800052d9  mov     rdx, [rbp+270h+var_2D0]
0x1800052dd  test    rdx, rdx
0x1800052e0  jnz     loc_180006A37
0x1800052e6  mov     eax, edi
0x1800052e8  mov     rcx, [rbp+270h+var_50]
0x1800052ef  xor     rcx, rsp; StackCookie
0x1800052f2  call    __security_check_cookie
0x1800052f7  add     rsp, 360h
0x1800052fe  pop     rdi
0x1800052ff  pop     rbx
0x180005300  pop     rbp
0x180005301  retn
0x180005302  lea     rax, [rsp+370h+var_320]
0x180005307  mov     dword ptr [rsp+370h+lpSubKey], r14d
0x18000530c  lea     r9, [rsp+370h+lpSubKey]; unsigned int *
0x180005311  mov     [rsp+370h+phkResult], rax; void **
0x180005316  mov     r8d, 6; dwFlags
0x18000531c  lea     rdx, aIdentityname; "IdentityName"
0x180005323  call    ?GetRegVal@@YAJPEAUHKEY__@@PEBGKPEAKPEAPEAX@Z; GetRegVal(HKEY__ *,ushort const *,ulong,ulong *,void * *)
0x180005328  cmp     eax, 0C0000225h
0x18000532d  mov     edi, r14d
0x180005330  cmovnz  edi, eax
0x180005333  test    edi, edi
0x180005335  jnz     loc_180005BEE
0x18000533b  mov     rcx, [rbp+270h+hKey]; hkey
0x18000533f  lea     rax, [rbp+270h+var_298]
0x180005343  lea     r9, [rsp+370h+lpSubKey]; unsigned int *
0x180005348  mov     [rsp+370h+phkResult], rax; void **
0x18000534d  mov     r8d, 6; dwFlags
0x180005353  mov     dword ptr [rsp+370h+lpSubKey], r14d
0x180005358  lea     rdx, aAuthenticating; "AuthenticatingAuthority"
0x18000535f  call    ?GetRegVal@@YAJPEAUHKEY__@@PEBGKPEAKPEAPEAX@Z; GetRegVal(HKEY__ *,ushort const *,ulong,ulong *,void * *)
0x180005364  cmp     eax, 0C0000225h
0x180005369  mov     edi, r14d
0x18000536c  cmovnz  edi, eax
0x18000536f  test    edi, edi
0x180005371  jnz     loc_1800059E6
0x180005377  mov     rcx, [rbp+270h+hKey]; hkey
0x18000537b  lea     rax, [rbp+270h+var_2F0]
0x18000537f  lea     r9, [rsp+370h+lpSubKey]; unsigned int *
0x180005384  mov     [rsp+370h+phkResult], rax; void **
0x180005389  mov     r8d, 6; dwFlags
  ... truncated ...
```
