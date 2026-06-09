# GenAndPersistNT4StyleName(bool,HKEY__ *,void *,ushort *,ushort *,_APPLUGIN_USER_INFO *,ushort * *)

- ea: `0x1800307d0`
- end: `0x180030fdc`
- name: `?GenAndPersistNT4StyleName@@YAJ_NPEAUHKEY__@@PEAXPEAG3PEAU_APPLUGIN_USER_INFO@@PEAPEAG@Z`
- size: `2060`
- prototype: `__int64 __fastcall(bool, HKEY, void *, unsigned __int16 *, unsigned __int16 *, struct _APPLUGIN_USER_INFO *, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004e7b0`
- `0x18004f600`
- `0x180059db8`

## callees

- `0x180003e70`
- `0x180006cb0`
- `0x180007fc0`
- `0x18000a600`
- `0x18000a8f0`
- `0x1800307d0`
- `0x180031494`
- `0x18004df2c`
- `0x18004e1b8`
- `0x180056684`
- `0x18005da64`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030d36`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030f8f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030d36`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180030f8f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180030917`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180030c31`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180030917`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180030c31`
- `ntdll!RtlReleaseResource` at `0x180030e42`
- `ntdll!RtlReleaseResource` at `0x180030f80`
- `ntdll!RtlReleaseResource` at `0x180030e42`
- `ntdll!RtlReleaseResource` at `0x180030f80`
- `ntdll!RtlInitUnicodeString` at `0x180030b67`
- `ntdll!RtlInitUnicodeString` at `0x180030b67`
- `ntdll!RtlAcquireResourceShared` at `0x180030860`
- `ntdll!RtlAcquireResourceShared` at `0x180030860`
- `ntdll!RtlConvertSharedToExclusive` at `0x180030dbe`
- `ntdll!RtlConvertSharedToExclusive` at `0x180030edf`
- `ntdll!RtlConvertSharedToExclusive` at `0x180030dbe`
- `ntdll!RtlConvertSharedToExclusive` at `0x180030edf`
- `ntdll!RtlConvertExclusiveToShared` at `0x180030e0c`
- `ntdll!RtlConvertExclusiveToShared` at `0x180030e0c`

## string_xrefs

- `0x180030873`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x1800308bd`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18003092d`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x180030988`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x180030bd7`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x180030c48`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x180030ca8`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x180030cde`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x180030a2e`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180030af0`: `onecore\ds\ext\cloudap\dll\logonapi.cpp`
- `0x180030a42`: `FindUserInCacheBySid`
- `0x180030948`: `RegOpenKeyExW`
- `0x1800309a3`: `RegOpenKeyExW`
- `0x180030c63`: `RegOpenKeyExW`
- `0x180030cc3`: `RegOpenKeyExW`
- `0x180030e76`: `FlushIdentityCache`
- `0x180030de7`: `RemoveUserFromSAMNameCache`
- `0x180030f18`: `AddSAMNameInLookupCache`
- `0x1800308d1`: `GetUserSid2NameSubKey`

## pseudocode

```c
__int64 __fastcall GenAndPersistNT4StyleName(
        bool a1,
        HKEY a2,
        void *a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        struct _APPLUGIN_USER_INFO *a6,
        unsigned __int16 **a7)
{
  unsigned __int16 *v8; // rdi
  _WORD *v9; // rcx
  _WORD *v10; // rcx
  _WORD *v11; // rcx
  LPCWSTR v12; // r15
  int UserSAMNameSubKey; // r13d
  const WCHAR *v14; // r14
  unsigned int UserSid2NameSubKey; // ebx
  const char *v16; // rax
  const char *v17; // rax
  __int64 v18; // r8
  const char *v19; // rax
  __int64 v20; // r8
  const UCHAR *v21; // r9
  const UCHAR *v22; // rax
  bool v23; // zf
  const char *v24; // rax
  const char *v25; // r12
  struct _APPLUGIN_USER_INFO *v26; // rbx
  bool v27; // r13
  const char *v28; // rax
  PCWSTR v29; // rbx
  char v30; // r12
  HKEY v31; // r12
  const char *v32; // rax
  const char *v33; // rax
  __int64 v34; // r8
  const char *v35; // rax
  __int64 v36; // r8
  const char *v37; // r9
  const char *v38; // rax
  const WCHAR *v39; // rdx
  const char *v40; // rax
  __int64 v41; // r8
  void *v42; // r13
  const char *v43; // rax
  unsigned __int16 *Buffer; // r12
  const char *v45; // rax
  int v46; // r8d
  PHKEY phkResult; // [rsp+28h] [rbp-71h]
  PHKEY phkResulta; // [rsp+28h] [rbp-71h]
  PHKEY phkResultb; // [rsp+28h] [rbp-71h]
  PHKEY phkResultc; // [rsp+28h] [rbp-71h]
  char v52; // [rsp+48h] [rbp-51h]
  LPCWSTR lpSubKey; // [rsp+50h] [rbp-49h] BYREF
  HKEY hkey; // [rsp+58h] [rbp-41h] BYREF
  PCWSTR SourceString; // [rsp+60h] [rbp-39h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-31h] BYREF
  struct _UNICODE_STRING v57; // [rsp+70h] [rbp-29h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+80h] [rbp-19h] BYREF
  bool v59; // [rsp+E8h] [rbp+4Fh]

  v59 = a1;
  hkey = 0;
  SourceString = 0;
  hKey = a2;
  *a7 = 0;
  v8 = 0;
  DestinationString = 0;
  v57 = 0;
  if ( a1 )
  {
    v9 = (_WORD *)*((_QWORD *)a6 + 9);
    if ( !v9
      || !*v9
      || (v10 = (_WORD *)*((_QWORD *)a6 + 10)) == 0
      || !*v10
      || (v11 = (_WORD *)*((_QWORD *)a6 + 11)) == 0
      || !*v11 )
    {
      v59 = 0;
    }
  }
  RtlAcquireResourceShared(&g_LookupsCacheLock, 1u);
  lpSubKey = 0;
  hkey = 0;
  v12 = 0;
  UserSAMNameSubKey = -1073741811;
  v14 = &Class;
  if ( a2 && a3 )
  {
    UserSid2NameSubKey = GetUserSid2NameSubKey(a3, (unsigned __int16 **)&lpSubKey);
    if ( UserSid2NameSubKey )
    {
      v16 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", UserSid2NameSubKey, v16, 1463, "GetUserSid2NameSubKey", &Class);
      v12 = lpSubKey;
    }
    else
    {
      v12 = lpSubKey;
      UserSid2NameSubKey = RegOpenKeyExW(a2, lpSubKey, 0, 0x20019u, &hkey);
      if ( UserSid2NameSubKey )
      {
        v17 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
        LODWORD(phkResult) = 1473;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", UserSid2NameSubKey, v17, phkResult, "RegOpenKeyExW", v18);
        if ( UserSid2NameSubKey - 2 <= 1 )
        {
          UserSid2NameSubKey = -1073741275;
        }
        else if ( (int)UserSid2NameSubKey > 0 )
        {
          UserSid2NameSubKey = (unsigned __int16)UserSid2NameSubKey | 0xC0070000;
        }
        v19 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
        LODWORD(phkResulta) = 1483;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", UserSid2NameSubKey, v19, phkResulta, "RegOpenKeyExW", v20);
      }
      else
      {
        UserSid2NameSubKey = 0;
      }
    }
  }
  else
  {
    UserSid2NameSubKey = -1073741811;
    v21 = "";
    while ( 1 )
    {
      v22 = v21--;
      v23 = *v21 == 92;
      if ( *v21 == 92 )
        break;
      if ( v21 <= "onecore\\ds\\ext\\cloudap\\dll\\utils.cpp" )
      {
        v23 = *v21 == 92;
        break;
      }
    }
    if ( v23 )
      v21 = v22;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225485LL, v21, 1457, "Invalid Arg(s)", &Class);
  }
  if ( v12 )
    ((void (__fastcall *)(LPCWSTR))g_pLsaFunctionTable->FreeLsaHeap)(v12);
  if ( (UserSid2NameSubKey & 0x80000000) != 0 )
  {
    v24 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
    v25 = "FindUserInCacheBySid";
    LODWORD(phkResult) = 1212;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", UserSid2NameSubKey, v24, phkResult, "FindUserInCacheBySid", &Class);
    if ( UserSid2NameSubKey != -1073741275 )
    {
LABEL_83:
      v45 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
      LODWORD(phkResultb) = v46;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", UserSid2NameSubKey, v45, phkResultb, v25, v14);
      RtlReleaseResource(&g_LookupsCacheLock);
      goto LABEL_84;
    }
    v52 = 0;
    goto LABEL_32;
  }
  LODWORD(lpSubKey) = 0;
  UserSid2NameSubKey = GetRegVal(hkey, L"SAMName", 6u, (unsigned int *)&lpSubKey, (void **)&SourceString);
  if ( (UserSid2NameSubKey & 0x80000000) != 0 )
  {
    v28 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
    v25 = "GetStringRegVal";
    LODWORD(phkResultb) = 1228;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", UserSid2NameSubKey, v28, phkResultb, "GetStringRegVal", L"SAMName");
    if ( UserSid2NameSubKey != -1073741275 )
    {
      v14 = L"SAMName";
      v8 = (unsigned __int16 *)SourceString;
      goto LABEL_83;
    }
  }
  v8 = (unsigned __int16 *)SourceString;
  v29 = 0;
  v52 = 0;
  v30 = 0;
  if ( !SourceString )
  {
LABEL_32:
    v26 = a6;
    v27 = v59;
    goto LABEL_33;
  }
  RtlInitUnicodeString(&DestinationString, SourceString);
  if ( !DestinationString.Buffer
    || !DestinationString.Length
    || !DestinationString.MaximumLength
    || DestinationString.Length > (unsigned __int64)DestinationString.MaximumLength - 2
    || DestinationString.Buffer[(unsigned __int64)DestinationString.Length >> 1] )
  {
    v38 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
    LODWORD(phkResultb) = 869;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225485LL, v38, phkResultb, "Internal Error!!Invalid Arg(s)", &Class);
    goto LABEL_61;
  }
  v31 = hKey;
  SourceString = 0;
  lpSubKey = 0;
  if ( hKey )
  {
    UserSAMNameSubKey = GetUserSAMNameSubKey(DestinationString.Buffer, (unsigned __int16 **)&SourceString);
    if ( UserSAMNameSubKey )
    {
      v32 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
      LODWORD(phkResultb) = 1587;
      WPPTraceLogA(
        0,
        "0x%08x %s:%u : %s:%ws",
        (unsigned int)UserSAMNameSubKey,
        v32,
        phkResultb,
        "GetUserSAMNameSubKey",
        &Class);
      v29 = SourceString;
    }
    else
    {
      v29 = SourceString;
      UserSAMNameSubKey = RegOpenKeyExW(v31, SourceString, 0, 0x20019u, (PHKEY)&lpSubKey);
      if ( UserSAMNameSubKey )
      {
        v33 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
        LODWORD(phkResultb) = 1597;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", (unsigned int)UserSAMNameSubKey, v33, phkResultb, "RegOpenKeyExW", v34);
        if ( (unsigned int)(UserSAMNameSubKey - 2) <= 1 )
        {
          UserSAMNameSubKey = -1073741275;
        }
        else if ( UserSAMNameSubKey > 0 )
        {
          UserSAMNameSubKey = (unsigned __int16)UserSAMNameSubKey | 0xC0070000;
        }
        v35 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
        LODWORD(phkResultc) = 1607;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", (unsigned int)UserSAMNameSubKey, v35, phkResultc, "RegOpenKeyExW", v36);
      }
      else
      {
        UserSAMNameSubKey = 0;
      }
    }
  }
  else
  {
    v37 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
    LODWORD(phkResultb) = 1581;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225485LL, v37, phkResultb, "Invalid Arg(s)", &Class);
  }
  if ( v29 )
    ((void (__fastcall *)(PCWSTR))g_pLsaFunctionTable->FreeLsaHeap)(v29);
  if ( UserSAMNameSubKey < 0 )
  {
    ((void (__fastcall *)(unsigned __int16 *))g_pLsaFunctionTable->FreeLsaHeap)(v8);
    v8 = 0;
    goto LABEL_32;
  }
  RegCloseKey((HKEY)lpSubKey);
  v30 = 0;
LABEL_61:
  v27 = v59;
  v26 = a6;
  if ( v59 )
  {
    v39 = (const WCHAR *)*((_QWORD *)a6 + 9);
    if ( v39 )
    {
      if ( CloudAPCompareStrings(v8, v39) )
      {
        RtlConvertSharedToExclusive(&g_LookupsCacheLock);
        if ( (unsigned int)RemoveUserFromSAMNameCache(a2, v8) )
        {
          v40 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
          LODWORD(phkResultb) = 1277;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v41, v40, phkResultb, "RemoveUserFromSAMNameCache", v8);
        }
        RtlConvertExclusiveToShared(&g_LookupsCacheLock);
        v30 = 1;
        v52 = 1;
        ((void (__fastcall *)(unsigned __int16 *))g_pLsaFunctionTable->FreeLsaHeap)(v8);
        v8 = 0;
      }
    }
  }
  if ( v8 )
  {
    v42 = a3;
    goto LABEL_69;
  }
LABEL_33:
  UserSid2NameSubKey = SanitizeSAMName(v27, (struct _tagCallerContext *)&hKey, a5, v26, &v57);
  if ( UserSid2NameSubKey )
  {
    v25 = "SanitizeSAMName";
    goto LABEL_83;
  }
  if ( !v57.Length
    || !v57.MaximumLength
    || v57.Length > (unsigned __int64)v57.MaximumLength - 2
    || (Buffer = v57.Buffer, v57.Buffer[(unsigned __int64)v57.Length >> 1]) )
  {
    UserSid2NameSubKey = -1073741595;
    v25 = "Internal Error!!Sanitized Name is invalid";
    goto LABEL_83;
  }
  v57.Buffer = 0;
  v8 = Buffer;
  RtlConvertSharedToExclusive(&g_LookupsCacheLock);
  v42 = a3;
  UserSid2NameSubKey = AddSAMNameInLookupCache(a2, a4, a5, Buffer, a3);
  if ( UserSid2NameSubKey )
  {
    if ( Buffer )
      v14 = Buffer;
    v25 = "AddSAMNameInLookupCache";
    goto LABEL_83;
  }
  v30 = v52;
LABEL_69:
  RtlReleaseResource(&g_LookupsCacheLock);
  if ( v30 && (UserSid2NameSubKey = FlushIdentityCache(v42)) != 0 )
  {
    v43 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\logonapi.cpp");
    LODWORD(phkResultb) = 1336;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", UserSid2NameSubKey, v43, phkResultb, "FlushIdentityCache", &Class);
  }
  else
  {
    UserSid2NameSubKey = 0;
    *a7 = v8;
    v8 = 0;
  }
LABEL_84:
  if ( hkey )
    RegCloseKey(hkey);
  if ( v8 )
    ((void (__fastcall *)(unsigned __int16 *))g_pLsaFunctionTable->FreeLsaHeap)(v8);
  if ( v57.Buffer )
    ((void (*)(void))g_pLsaFunctionTable->FreeLsaHeap)();
  return UserSid2NameSubKey;
}

```

## disassembly

```asm
0x1800307d0  mov     rax, rsp
0x1800307d3  mov     [rax+20h], r9
0x1800307d7  mov     [rax+18h], r8
0x1800307db  mov     [rax+10h], rdx
0x1800307df  mov     [rax+8], cl
0x1800307e2  push    rbp
0x1800307e3  push    rbx
0x1800307e4  push    rsi
0x1800307e5  push    rdi
0x1800307e6  push    r12
0x1800307e8  push    r13
0x1800307ea  push    r14
0x1800307ec  push    r15
0x1800307ee  lea     rbp, [rax-47h]
0x1800307f2  sub     rsp, 98h
0x1800307f9  mov     rax, [rbp+3Fh+arg_30]
0x1800307fd  xor     esi, esi
0x1800307ff  mov     [rbp+3Fh+hkey], rsi
0x180030803  xorps   xmm0, xmm0
0x180030806  mov     [rbp+3Fh+SourceString], rsi
0x18003080a  xorps   xmm1, xmm1
0x18003080d  mov     [rbp+3Fh+hKey], rdx
0x180030811  mov     r12, rdx
0x180030814  mov     [rax], rsi
0x180030817  mov     edi, esi
0x180030819  movups  xmmword ptr [rbp+3Fh+DestinationString.Length], xmm0
0x18003081d  movups  xmmword ptr [rbp+3Fh+var_68.Length], xmm1
0x180030821  test    cl, cl
0x180030823  jz      short loc_180030857
0x180030825  mov     rdx, [rbp+3Fh+arg_28]
0x180030829  mov     rcx, [rdx+48h]
0x18003082d  test    rcx, rcx
0x180030830  jz      short loc_180030853
0x180030832  cmp     si, [rcx]
0x180030835  jz      short loc_180030853
0x180030837  mov     rcx, [rdx+50h]
0x18003083b  test    rcx, rcx
0x18003083e  jz      short loc_180030853
0x180030840  cmp     si, [rcx]
0x180030843  jz      short loc_180030853
0x180030845  mov     rcx, [rdx+58h]
0x180030849  test    rcx, rcx
0x18003084c  jz      short loc_180030853
0x18003084e  cmp     si, [rcx]
0x180030851  jnz     short loc_180030857
0x180030853  mov     [rbp+3Fh+arg_0], sil
0x180030857  mov     dl, 1; Wait
0x180030859  lea     rcx, ?g_LookupsCacheLock@@3U_RTL_RESOURCE@@A; Resource
0x180030860  call    cs:__imp_RtlAcquireResourceShared
0x180030866  xor     ecx, ecx
0x180030868  mov     [rbp+3Fh+lpSubKey], rsi
0x18003086c  mov     [rbp+3Fh+hkey], rsi
0x180030870  mov     r15, rsi
0x180030873  lea     rdx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18003087a  mov     r13d, 0C000000Dh
0x180030880  lea     r14, Class
0x180030887  lea     rsi, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18003088e  lea     r8, aInvalidArgS; "Invalid Arg(s)"
0x180030895  test    r12, r12
0x180030898  jz      loc_1800309CB
0x18003089e  mov     rax, [rbp+3Fh+SourceSid]
0x1800308a2  test    rax, rax
0x1800308a5  jz      loc_1800309CB
0x1800308ab  lea     rdx, [rbp+3Fh+lpSubKey]; unsigned __int16 **
0x1800308af  mov     rcx, rax; void *
0x1800308b2  call    ?GetUserSid2NameSubKey@@YAJPEAXPEAPEAG@Z; GetUserSid2NameSubKey(void *,ushort * *)
0x1800308b7  mov     ebx, eax
0x1800308b9  test    eax, eax
0x1800308bb  jz      short loc_1800308FB
0x1800308bd  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x1800308c4  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800308c9  mov     r9, rax
0x1800308cc  mov     [rsp+30h], r14
0x1800308d1  lea     rax, aGetusersid2nam; "GetUserSid2NameSubKey"
0x1800308d8  mov     r8d, ebx
0x1800308db  mov     [rsp+0D0h+var_A8], rax
0x1800308e0  mov     rdx, rsi
0x1800308e3  xor     ecx, ecx
0x1800308e5  mov     dword ptr [rsp+0D0h+phkResult], 5B7h
0x1800308ed  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x1800308f2  mov     r15, [rbp+3Fh+lpSubKey]
0x1800308f6  jmp     loc_180030A0B
0x1800308fb  mov     r15, [rbp+3Fh+lpSubKey]
0x1800308ff  lea     rax, [rbp+3Fh+hkey]
0x180030903  mov     rdx, r15; lpSubKey
0x180030906  mov     [rsp+0D0h+phkResult], rax; phkResult
0x18003090b  mov     r9d, 20019h; samDesired
0x180030911  xor     r8d, r8d; ulOptions
0x180030914  mov     rcx, r12; hKey
0x180030917  call    cs:__imp_RegOpenKeyExW
0x18003091d  xor     r12d, r12d
0x180030920  mov     ebx, eax
0x180030922  test    eax, eax
0x180030924  jz      loc_1800309C6
0x18003092a  test    r15, r15
0x18003092d  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x180030934  mov     r8, r14
0x180030937  cmovnz  r8, r15
0x18003093b  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180030940  mov     [rsp+30h], r8
0x180030945  mov     r9, rax
0x180030948  lea     rax, aRegopenkeyexw; "RegOpenKeyExW"
0x18003094f  mov     r8d, ebx
0x180030952  mov     [rsp+0D0h+var_A8], rax
0x180030957  mov     rdx, rsi
0x18003095a  xor     ecx, ecx
0x18003095c  mov     dword ptr [rsp+0D0h+phkResult], 5C1h
0x180030964  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180030969  lea     eax, [rbx-2]
0x18003096c  cmp     eax, 1
0x18003096f  jbe     short loc_180030980
0x180030971  test    ebx, ebx
0x180030973  jle     short loc_180030985
0x180030975  movzx   ebx, bx
0x180030978  or      ebx, 0C0070000h
0x18003097e  jmp     short loc_180030985
0x180030980  mov     ebx, 0C0000225h
0x180030985  test    r15, r15
0x180030988  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18003098f  mov     r8, r14
0x180030992  cmovnz  r8, r15
0x180030996  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18003099b  mov     [rsp+30h], r8
0x1800309a0  mov     r9, rax
0x1800309a3  lea     rax, aRegopenkeyexw; "RegOpenKeyExW"
0x1800309aa  mov     r8d, ebx
0x1800309ad  mov     [rsp+0D0h+var_A8], rax
0x1800309b2  mov     rdx, rsi
0x1800309b5  xor     ecx, ecx
0x1800309b7  mov     dword ptr [rsp+0D0h+phkResult], 5CBh
0x1800309bf  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x1800309c4  jmp     short loc_180030A0E
0x1800309c6  mov     ebx, r12d
0x1800309c9  jmp     short loc_180030A0E
0x1800309cb  mov     ebx, r13d
0x1800309ce  lea     r9, pbInput+24h; ""
0x1800309d5  mov     rax, r9
0x1800309d8  dec     r9
0x1800309db  cmp     byte ptr [r9], 5Ch ; '\'
0x1800309df  jz      short loc_1800309EA
0x1800309e1  cmp     r9, rdx
0x1800309e4  ja      short loc_1800309D5
0x1800309e6  cmp     byte ptr [r9], 5Ch ; '\'
0x1800309ea  mov     [rsp+30h], r14
0x1800309ef  cmovz   r9, rax
0x1800309f3  mov     [rsp+0D0h+var_A8], r8
0x1800309f8  mov     rdx, rsi
0x1800309fb  mov     r8d, r13d
0x1800309fe  mov     dword ptr [rsp+0D0h+phkResult], 5B1h
0x180030a06  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180030a0b  xor     r12d, r12d
0x180030a0e  test    r15, r15
0x180030a11  jz      short loc_180030A26
0x180030a13  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x180030a1a  mov     rcx, r15
0x180030a1d  mov     rax, [rax+30h]
0x180030a21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030a26  test    ebx, ebx
0x180030a28  jns     loc_180030AC6
0x180030a2e  lea     r15, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180030a35  mov     rcx, r15; char *
0x180030a38  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180030a3d  mov     [rsp+30h], r14
0x180030a42  lea     r12, aFinduserincach; "FindUserInCacheBySid"
0x180030a49  mov     [rsp+0D0h+var_A8], r12
0x180030a4e  mov     r9, rax
0x180030a51  mov     r8d, ebx
0x180030a54  mov     dword ptr [rsp+0D0h+phkResult], 4BCh
0x180030a5c  mov     rdx, rsi
0x180030a5f  xor     ecx, ecx
0x180030a61  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180030a66  cmp     ebx, 0C0000225h
0x180030a6c  jz      short loc_180030A7C
0x180030a6e  xor     r13d, r13d
0x180030a71  mov     r8d, 4C0h
0x180030a77  jmp     loc_180030F4E
0x180030a7c  xor     r12b, r12b
0x180030a7f  mov     [rbp+3Fh+var_90], r12b
0x180030a83  mov     rbx, [rbp+3Fh+arg_28]
0x180030a87  mov     r13b, [rbp+3Fh+arg_0]
0x180030a8b  mov     r8, [rbp+3Fh+arg_20]; unsigned __int16 *
0x180030a8f  lea     rax, [rbp+3Fh+var_68]
0x180030a93  mov     r9, rbx; struct _APPLUGIN_USER_INFO *
0x180030a96  mov     [rsp+0D0h+phkResult], rax; struct _UNICODE_STRING *
0x180030a9b  lea     rdx, [rbp+3Fh+hKey]; struct _tagCallerContext *
0x180030a9f  mov     cl, r13b; bool
0x180030aa2  call    ?SanitizeSAMName@@YAJ_NPEAU_tagCallerContext@@PEAGPEAU_APPLUGIN_USER_INFO@@PEAU_UNICODE_STRING@@@Z; SanitizeSAMName(bool,_tagCallerContext *,ushort *,_APPLUGIN_USER_INFO *,_UNICODE_STRING *)
0x180030aa7  xor     r13d, r13d
0x180030aaa  mov     ebx, eax
0x180030aac  test    eax, eax
0x180030aae  jz      loc_180030E9C
0x180030ab4  mov     r8d, 515h
0x180030aba  lea     r12, aSanitizesamnam; "SanitizeSAMName"
0x180030ac1  jmp     loc_180030F4E
0x180030ac6  mov     rcx, [rbp+3Fh+hkey]; hkey
0x180030aca  lea     rax, [rbp+3Fh+SourceString]
0x180030ace  lea     rdi, aSamname; "SAMName"
0x180030ad5  mov     dword ptr [rbp+3Fh+lpSubKey], r12d
0x180030ad9  mov     rdx, rdi; lpValue
0x180030adc  mov     [rsp+0D0h+phkResult], rax; void **
0x180030ae1  lea     r9, [rbp+3Fh+lpSubKey]; unsigned int *
0x180030ae5  mov     r8d, 6; dwFlags
0x180030aeb  call    ?GetRegVal@@YAJPEAUHKEY__@@PEBGKPEAKPEAPEAX@Z; GetRegVal(HKEY__ *,ushort const *,ulong,ulong *,void * *)
0x180030af0  lea     r15, aOnecoreDsExtCl_6; "onecore\\ds\\ext\\cloudap\\dll\\logonap"...
0x180030af7  mov     ebx, eax
0x180030af9  test    eax, eax
0x180030afb  jns     short loc_180030B4B
0x180030afd  mov     rcx, r15; char *
0x180030b00  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180030b05  mov     [rsp+30h], rdi
0x180030b0a  lea     r12, aGetstringregva_3; "GetStringRegVal"
0x180030b11  mov     [rsp+0D0h+var_A8], r12
0x180030b16  mov     r9, rax
0x180030b19  mov     r8d, ebx
0x180030b1c  mov     dword ptr [rsp+0D0h+phkResult], 4CCh
0x180030b24  mov     rdx, rsi
0x180030b27  xor     ecx, ecx
0x180030b29  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180030b2e  cmp     ebx, 0C0000225h
0x180030b34  jz      short loc_180030B4B
0x180030b36  mov     r14, rdi
0x180030b39  xor     r13d, r13d
0x180030b3c  mov     rdi, [rbp+3Fh+SourceString]
0x180030b40  mov     r8d, 4D0h
0x180030b46  jmp     loc_180030F4E
0x180030b4b  mov     rdi, [rbp+3Fh+SourceString]
0x180030b4f  xor     ebx, ebx
0x180030b51  mov     [rbp+3Fh+var_90], bl
0x180030b54  mov     r12b, bl
0x180030b57  test    rdi, rdi
0x180030b5a  jz      loc_180030A83
0x180030b60  mov     rdx, rdi; SourceString
0x180030b63  lea     rcx, [rbp+3Fh+DestinationString]; DestinationString
0x180030b67  call    cs:__imp_RtlInitUnicodeString
0x180030b6d  mov     rcx, [rbp+3Fh+DestinationString.Buffer]; unsigned __int16 *
0x180030b71  test    rcx, rcx
0x180030b74  jz      loc_180030D5C
0x180030b7a  cmp     bx, [rbp+3Fh+DestinationString.Length]
0x180030b7e  jz      loc_180030D5C
0x180030b84  cmp     bx, [rbp+3Fh+DestinationString.MaximumLength]
0x180030b88  jz      loc_180030D5C
0x180030b8e  movzx   eax, [rbp+3Fh+DestinationString.MaximumLength]
0x180030b92  movzx   edx, [rbp+3Fh+DestinationString.Length]
0x180030b96  sub     rax, 2
0x180030b9a  cmp     rdx, rax
0x180030b9d  ja      loc_180030D5C
0x180030ba3  shr     rdx, 1
0x180030ba6  cmp     [rcx+rdx*2], bx
0x180030baa  jnz     loc_180030D5C
0x180030bb0  mov     r12, [rbp+3Fh+hKey]
0x180030bb4  xor     eax, eax
0x180030bb6  mov     [rbp+3Fh+SourceString], rbx
0x180030bba  mov     [rbp+3Fh+lpSubKey], rax
0x180030bbe  test    r12, r12
0x180030bc1  jz      loc_180030CDE
0x180030bc7  lea     rdx, [rbp+3Fh+SourceString]; unsigned __int16 **
0x180030bcb  call    ?GetUserSAMNameSubKey@@YAJPEBGPEAPEAG@Z; GetUserSAMNameSubKey(ushort const *,ushort * *)
0x180030bd0  mov     r13d, eax
0x180030bd3  test    eax, eax
0x180030bd5  jz      short loc_180030C15
0x180030bd7  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x180030bde  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180030be3  mov     r9, rax
0x180030be6  mov     [rsp+30h], r14
0x180030beb  lea     rax, aGetusersamname; "GetUserSAMNameSubKey"
0x180030bf2  mov     r8d, r13d
0x180030bf5  mov     [rsp+0D0h+var_A8], rax
0x180030bfa  mov     rdx, rsi
0x180030bfd  xor     ecx, ecx
0x180030bff  mov     dword ptr [rsp+0D0h+phkResult], 633h
0x180030c07  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180030c0c  mov     rbx, [rbp+3Fh+SourceString]
0x180030c10  jmp     loc_180030D13
0x180030c15  mov     rbx, [rbp+3Fh+SourceString]
0x180030c19  lea     rax, [rbp+3Fh+lpSubKey]
0x180030c1d  mov     rdx, rbx; lpSubKey
0x180030c20  mov     [rsp+0D0h+phkResult], rax; phkResult
0x180030c25  mov     r9d, 20019h; samDesired
0x180030c2b  xor     r8d, r8d; ulOptions
0x180030c2e  mov     rcx, r12; hKey
0x180030c31  call    cs:__imp_RegOpenKeyExW
0x180030c37  xor     r12d, r12d
0x180030c3a  mov     r13d, eax
0x180030c3d  test    eax, eax
0x180030c3f  jz      loc_180030CD9
0x180030c45  test    rbx, rbx
0x180030c48  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x180030c4f  mov     r8, r14
0x180030c52  cmovnz  r8, rbx
0x180030c56  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180030c5b  mov     [rsp+30h], r8
0x180030c60  mov     r9, rax
0x180030c63  lea     rax, aRegopenkeyexw; "RegOpenKeyExW"
0x180030c6a  mov     r8d, r13d
0x180030c6d  mov     [rsp+0D0h+var_A8], rax
0x180030c72  mov     rdx, rsi
0x180030c75  xor     ecx, ecx
0x180030c77  mov     dword ptr [rsp+0D0h+phkResult], 63Dh
0x180030c7f  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180030c84  lea     eax, [r13-2]
  ... truncated ...
```
