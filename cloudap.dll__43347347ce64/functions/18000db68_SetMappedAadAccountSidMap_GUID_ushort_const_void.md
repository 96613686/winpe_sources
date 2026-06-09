# SetMappedAadAccountSidMap(_GUID *,ushort const *,void *)

- ea: `0x18000db68`
- end: `0x18000e1e6`
- name: `?SetMappedAadAccountSidMap@@YAJPEAU_GUID@@PEBGPEAX@Z`
- size: `1662`
- prototype: `__int64 __fastcall(struct _GUID *, const unsigned __int16 *Src, PSID SourceSid)`
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180011960`
- `0x1800571b0`

## callees

- `0x180007fc0`
- `0x18000a600`
- `0x18000b0c0`
- `0x18000b9b0`
- `0x18000db68`
- `0x18000e900`
- `0x18000ee60`
- `0x18003ca18`
- `0x18003ea9c`
- `0x180042410`
- `0x18004317c`
- `0x18005e94c`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dcfc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dd06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dd10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000def5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000deff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000df09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dcfc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dd06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dd10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000def5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000deff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000df09`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000dcf2`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000deeb`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000dcf2`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000deeb`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x18000e048`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x18000e048`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e192`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000e192`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000dfa6`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000dfa6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e0f8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e101`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e1a2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e1b0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e1c0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e0f8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e101`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e1a2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e1b0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e1c0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000dd65`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000dd65`
- `ntdll!RtlAcquireResourceExclusive` at `0x18000de87`
- `ntdll!RtlAcquireResourceExclusive` at `0x18000de87`
- `ntdll!RtlReleaseResource` at `0x18000e119`
- `ntdll!RtlReleaseResource` at `0x18000e119`
- `ntdll!RtlLengthSid` at `0x18000dd56`
- `ntdll!RtlLengthSid` at `0x18000dd56`
- `ntdll!RtlCopySid` at `0x18000ddb4`
- `ntdll!RtlCopySid` at `0x18000ddb4`
- `ntdll!RtlEqualSid` at `0x18000e06f`
- `ntdll!RtlEqualSid` at `0x18000e06f`

## string_xrefs

- `0x18000dbf9`: `onecore\ds\ext\cloudap\dll\mappedaccount.cpp`
- `0x18000dc55`: `onecore\ds\ext\cloudap\dll\mappedaccount.cpp`
- `0x18000dcb6`: `onecore\ds\ext\cloudap\dll\mappedaccount.cpp`
- `0x18000dd1f`: `onecore\ds\ext\cloudap\dll\mappedaccount.cpp`
- `0x18000dd73`: `onecore\ds\ext\cloudap\dll\mappedaccount.cpp`
- `0x18000ddc0`: `onecore\ds\ext\cloudap\dll\mappedaccount.cpp`
- `0x18000de38`: `onecore\ds\ext\cloudap\dll\mappedaccount.cpp`
- `0x18000df18`: `onecore\ds\ext\cloudap\dll\mappedaccount.cpp`
- `0x18000dfbd`: `onecore\ds\ext\cloudap\dll\mappedaccount.cpp`
- `0x18000e016`: `onecore\ds\ext\cloudap\dll\mappedaccount.cpp`
- `0x18000e096`: `onecore\ds\ext\cloudap\dll\mappedaccount.cpp`
- `0x18000e121`: `onecore\ds\ext\cloudap\dll\mappedaccount.cpp`
- `0x18000dd3a`: `ConvertSidToStringSidW`
- `0x18000df33`: `ConvertSidToStringSidW`
- `0x18000dddb`: `RtlCopySid`
- `0x18000de64`: `LoadMappedSids`
- `0x18000dfd1`: `RegCreateKeyEx`
- `0x18000df6c`: `SidMap`
- `0x18000dfef`: `InternetSid`
- `0x18000e0b1`: `AddSidMapIntoCache`

## pseudocode

```c
__int64 __fastcall SetMappedAadAccountSidMap(struct _GUID *a1, const unsigned __int16 *Src, PSID SourceSid)
{
  LPCWSTR v6; // r15
  void *v7; // rsi
  const char *v8; // rax
  __int64 v9; // r8
  unsigned int HashString; // ebx
  const char *v11; // rax
  const char *v12; // r9
  const char *v13; // r9
  ULONG v14; // ebx
  HLOCAL v15; // rax
  const char *v16; // r9
  const char *v17; // r9
  signed __int32 v18; // eax
  signed __int32 v19; // ett
  const char *v20; // r9
  const char *v21; // rax
  bool v22; // zf
  HLOCAL *v23; // rax
  unsigned __int16 *v24; // rcx
  HLOCAL *v25; // rdi
  int v26; // r9d
  int v27; // edx
  const char *v28; // r9
  LSTATUS v29; // eax
  const char *v30; // r9
  const char *v31; // r9
  HLOCAL *i; // rbx
  const char *v33; // r9
  PSID v34; // rax
  void **v35; // rcx
  HLOCAL v36; // rcx
  const char *v37; // r9
  DWORD dwOptions[2]; // [rsp+20h] [rbp-E0h]
  DWORD dwOptionsa[2]; // [rsp+20h] [rbp-E0h]
  struct _ApPluginPkg *v41; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  DWORD dwDisposition; // [rsp+60h] [rbp-A0h] BYREF
  LPCWSTR lpSrcStr; // [rsp+68h] [rbp-98h] BYREF
  LPWSTR v45; // [rsp+70h] [rbp-90h] BYREF
  LPWSTR StringSid; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 v47[72]; // [rsp+80h] [rbp-80h] BYREF

  v6 = 0;
  lpSrcStr = 0;
  memset_0(v47, 0, 0x82u);
  v7 = 0;
  hKey = 0;
  dwDisposition = 0;
  v45 = 0;
  StringSid = 0;
  v41 = 0;
  if ( a1 && Src && SourceSid )
  {
    if ( (int)RefPackage(a1, &v41) >= 0 )
    {
      HashString = DuplicateString(Src, 0, (unsigned __int16 **)&lpSrcStr);
      if ( HashString )
      {
        v11 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\mappedaccount.cpp");
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", HashString, v11, 413, "DuplicateString", &Class);
        v6 = lpSrcStr;
      }
      else
      {
        v6 = lpSrcStr;
        HashString = GetHashString(lpSrcStr, v47);
        if ( HashString )
        {
          v12 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\mappedaccount.cpp");
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", HashString, v12, 418, "GetHashString", &Class);
        }
        else if ( ConvertSidToStringSidW(SourceSid, &StringSid) )
        {
          v14 = RtlLengthSid(SourceSid);
          v15 = LocalAlloc(0x40u, v14);
          v7 = v15;
          if ( v15 )
          {
            HashString = RtlCopySid(v14, v15, SourceSid);
            if ( HashString )
            {
              v17 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\mappedaccount.cpp");
              WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", HashString, v17, 435, "RtlCopySid", &Class);
            }
            else
            {
              _m_prefetchw((const void *)&g_lAccountCacheLoaded);
              v18 = g_lAccountCacheLoaded;
              do
              {
                v19 = v18;
                v18 = _InterlockedCompareExchange(&g_lAccountCacheLoaded, v18 & 1, v18);
              }
              while ( v19 != v18 );
              if ( v18 || (HashString = LoadMappedSids(*((HKEY *)v41 + 44))) == 0 )
              {
                RtlAcquireResourceExclusive(&g_AadConnectMapLock, 1u);
                v23 = (HLOCAL *)g_MappedUserNameHashList;
                if ( g_MappedUserNameHashList == &g_MappedUserNameHashList )
                  goto LABEL_63;
                do
                {
                  v24 = (unsigned __int16 *)(v23 + 2);
                  v25 = v23;
                  do
                  {
                    v26 = *(unsigned __int16 *)((char *)v24 + (char *)v47 - (char *)(v23 + 2));
                    v27 = *v24 - v26;
                    if ( v27 )
                      break;
                    ++v24;
                  }
                  while ( v26 );
                  if ( !v27 )
                    break;
                  v23 = (HLOCAL *)*v23;
                  v25 = 0;
                }
                while ( v23 != &g_MappedUserNameHashList );
                if ( !v25 )
                {
LABEL_63:
                  HashString = 0;
                }
                else
                {
                  if ( ConvertSidToStringSidW(v25[19], &v45) )
                  {
                    v29 = RegCreateKeyExW(*((HKEY *)v41 + 44), L"SidMap", 0, 0, 0, 0xF003Fu, 0, &hKey, &dwDisposition);
                    HashString = v29;
                    if ( v29 )
                    {
                      if ( v29 > 0 )
                        HashString = (unsigned __int16)v29 | 0xC0070000;
                      v30 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\mappedaccount.cpp");
                      dwOptions[0] = 487;
                      WPPTraceLogA(
                        0,
                        "0x%08x %s:%u : %s:%ws",
                        HashString,
                        v30,
                        *(_QWORD *)dwOptions,
                        L"RegCreateKeyEx",
                        L"SidMap");
                    }
                    else
                    {
                      HashString = SetStringRegVal(hKey, v45, 0, L"InternetSid", StringSid);
                      if ( HashString )
                      {
                        v31 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\mappedaccount.cpp");
                        dwOptionsa[0] = 496;
                        WPPTraceLogA(
                          0,
                          "0x%08x %s:%u : %s:%ws",
                          HashString,
                          v31,
                          *(_QWORD *)dwOptionsa,
                          L"SetStringRegVal",
                          L"InternetSid");
                      }
                      else
                      {
                        RegFlushKey(hKey);
                        for ( i = (HLOCAL *)g_MappedAccountCacheList; i != &g_MappedAccountCacheList; i = (HLOCAL *)*i )
                        {
                          if ( RtlEqualSid(i[2], v25[19]) )
                          {
                            i[3] = v7;
                            v7 = 0;
                            HashString = 0;
                            goto LABEL_57;
                          }
                        }
                        HashString = AddSidMapIntoCache(v25[19], v7);
                        if ( HashString )
                        {
                          v33 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\mappedaccount.cpp");
                          dwOptionsa[0] = 518;
                          WPPTraceLogA(
                            0,
                            "0x%08x %s:%u : %s:%ws",
                            HashString,
                            v33,
                            *(_QWORD *)dwOptionsa,
                            "AddSidMapIntoCache",
                            &Class);
                        }
                        else
                        {
                          v7 = 0;
                          v25[19] = 0;
                        }
                      }
                    }
                  }
                  else
                  {
                    if ( (int)GetLastError() > 0 )
                      HashString = (unsigned __int16)GetLastError() | 0xC0070000;
                    else
                      HashString = GetLastError();
                    v28 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\mappedaccount.cpp");
                    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", HashString, v28, 470, "ConvertSidToStringSidW", &Class);
                  }
LABEL_57:
                  v34 = *v25;
                  if ( *((HLOCAL **)*v25 + 1) != v25 || (v35 = (void **)v25[1], *v35 != v25) )
                    __fastfail(3u);
                  *v35 = v34;
                  *((_QWORD *)v34 + 1) = v35;
                  v36 = v25[19];
                  if ( v36 )
                    LocalFree(v36);
                  LocalFree(v25);
                }
                RtlReleaseResource(&g_AadConnectMapLock);
              }
              else
              {
                v20 = "";
                while ( 1 )
                {
                  v21 = v20--;
                  v22 = *v20 == 92;
                  if ( *v20 == 92 )
                    break;
                  if ( v20 <= "onecore\\ds\\ext\\cloudap\\dll\\mappedaccount.cpp" )
                  {
                    v22 = *v20 == 92;
                    break;
                  }
                }
                if ( v22 )
                  v20 = v21;
                WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", HashString, v20, 440, "LoadMappedSids", &Class);
              }
            }
          }
          else
          {
            HashString = -1073741801;
            v16 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\mappedaccount.cpp");
            WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225495LL, v16, 431, "LocalAlloc", &Class);
          }
        }
        else
        {
          if ( (int)GetLastError() > 0 )
            HashString = (unsigned __int16)GetLastError() | 0xC0070000;
          else
            HashString = GetLastError();
          v13 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\mappedaccount.cpp");
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", HashString, v13, 423, "ConvertSidToStringSidW", &Class);
        }
      }
    }
    else
    {
      v8 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\mappedaccount.cpp");
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v9, v8, 404, "RefPackage", &Class);
      HashString = -1073741637;
    }
  }
  else
  {
    HashString = -1073741811;
    v37 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\mappedaccount.cpp");
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225485LL, v37, 396, "Invalid Arg(s)", &Class);
  }
  DerefPackage(v41);
  if ( v6 )
    ((void (__fastcall *)(LPCWSTR))g_pLsaFunctionTable->FreeLsaHeap)(v6);
  if ( hKey )
    RegCloseKey(hKey);
  if ( v45 )
    LocalFree(v45);
  if ( v7 )
    LocalFree(v7);
  if ( StringSid )
    LocalFree(StringSid);
  return HashString;
}

```

## disassembly

```asm
0x18000db68  push    rbp
0x18000db6a  push    rbx
0x18000db6b  push    rsi
0x18000db6c  push    rdi
0x18000db6d  push    r13
0x18000db6f  push    r14
0x18000db71  push    r15
0x18000db73  lea     rbp, [rsp-20h]
0x18000db78  sub     rsp, 120h
0x18000db7f  mov     rax, cs:__security_cookie
0x18000db86  xor     rax, rsp
0x18000db89  mov     [rbp+50h+var_40], rax
0x18000db8d  mov     rdi, r8
0x18000db90  mov     rbx, rdx
0x18000db93  mov     r14, rcx
0x18000db96  xor     r15d, r15d
0x18000db99  xor     edx, edx; Val
0x18000db9b  mov     [rsp+150h+lpSrcStr], r15
0x18000dba0  mov     r8d, 82h; Size
0x18000dba6  lea     rcx, [rbp+50h+var_D0]; void *
0x18000dbaa  call    memset_0
0x18000dbaf  xor     esi, esi
0x18000dbb1  mov     [rsp+150h+hKey], r15
0x18000dbb6  mov     [rsp+150h+dwDisposition], r15d
0x18000dbbb  mov     [rsp+150h+var_E0], r15
0x18000dbc0  mov     [rsp+150h+StringSid], r15
0x18000dbc5  mov     [rsp+150h+var_100], rsi
0x18000dbca  test    r14, r14
0x18000dbcd  jz      loc_18000E121
0x18000dbd3  test    rbx, rbx
0x18000dbd6  jz      loc_18000E121
0x18000dbdc  test    rdi, rdi
0x18000dbdf  jz      loc_18000E121
0x18000dbe5  lea     rdx, [rsp+150h+var_100]; struct _ApPluginPkg **
0x18000dbea  mov     rcx, r14; struct _GUID *
0x18000dbed  call    ?RefPackage@@YAJPEAU_GUID@@PEAPEAU_ApPluginPkg@@@Z; RefPackage(_GUID *,_ApPluginPkg * *)
0x18000dbf2  mov     r8d, eax
0x18000dbf5  test    eax, eax
0x18000dbf7  jns     short loc_18000DC40
0x18000dbf9  lea     rcx, aOnecoreDsExtCl_9; "onecore\\ds\\ext\\cloudap\\dll\\mappeda"...
0x18000dc00  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000dc05  mov     r9, rax
0x18000dc08  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18000dc0f  lea     rax, Class
0x18000dc16  xor     ecx, ecx
0x18000dc18  mov     [rsp+150h+lpSecurityAttributes], rax
0x18000dc1d  lea     rax, aRefpackage; "RefPackage"
0x18000dc24  mov     qword ptr [rsp+150h+samDesired], rax
0x18000dc29  mov     [rsp+150h+dwOptions], 194h
0x18000dc31  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18000dc36  mov     ebx, 0C00000BBh
0x18000dc3b  jmp     loc_18000E166
0x18000dc40  lea     r8, [rsp+150h+lpSrcStr]; unsigned __int16 **
0x18000dc45  xor     edx, edx; int
0x18000dc47  mov     rcx, rbx; Src
0x18000dc4a  call    ?DuplicateString@@YAJPEBGHPEAPEAG@Z; DuplicateString(ushort const *,int,ushort * *)
0x18000dc4f  mov     ebx, eax
0x18000dc51  test    eax, eax
0x18000dc53  jz      short loc_18000DC9F
0x18000dc55  lea     rcx, aOnecoreDsExtCl_9; "onecore\\ds\\ext\\cloudap\\dll\\mappeda"...
0x18000dc5c  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000dc61  mov     r9, rax
0x18000dc64  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18000dc6b  lea     rax, Class
0x18000dc72  mov     r8d, ebx
0x18000dc75  mov     [rsp+150h+lpSecurityAttributes], rax
0x18000dc7a  xor     ecx, ecx
0x18000dc7c  lea     rax, aDuplicatestrin_1; "DuplicateString"
0x18000dc83  mov     qword ptr [rsp+150h+samDesired], rax
0x18000dc88  mov     [rsp+150h+dwOptions], 19Dh
0x18000dc90  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18000dc95  mov     r15, [rsp+150h+lpSrcStr]
0x18000dc9a  jmp     loc_18000E166
0x18000dc9f  mov     r15, [rsp+150h+lpSrcStr]
0x18000dca4  lea     rdx, [rbp+50h+var_D0]; unsigned __int16 *
0x18000dca8  mov     rcx, r15; lpSrcStr
0x18000dcab  call    ?GetHashString@@YAJPEBGQEAG@Z; GetHashString(ushort const *,ushort * const)
0x18000dcb0  mov     ebx, eax
0x18000dcb2  test    eax, eax
0x18000dcb4  jz      short loc_18000DCEA
0x18000dcb6  lea     rcx, aOnecoreDsExtCl_9; "onecore\\ds\\ext\\cloudap\\dll\\mappeda"...
0x18000dcbd  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000dcc2  mov     r9, rax
0x18000dcc5  lea     rax, Class
0x18000dccc  mov     [rsp+150h+lpSecurityAttributes], rax
0x18000dcd1  lea     rax, aGethashstring; "GetHashString"
0x18000dcd8  mov     qword ptr [rsp+150h+samDesired], rax
0x18000dcdd  mov     [rsp+150h+dwOptions], 1A2h
0x18000dce5  jmp     loc_18000E155
0x18000dcea  lea     rdx, [rsp+150h+StringSid]; StringSid
0x18000dcef  mov     rcx, rdi; Sid
0x18000dcf2  call    cs:__imp_ConvertSidToStringSidW
0x18000dcf8  test    eax, eax
0x18000dcfa  jnz     short loc_18000DD53
0x18000dcfc  call    cs:__imp_GetLastError
0x18000dd02  test    eax, eax
0x18000dd04  jg      short loc_18000DD10
0x18000dd06  call    cs:__imp_GetLastError
0x18000dd0c  mov     ebx, eax
0x18000dd0e  jmp     short loc_18000DD1F
0x18000dd10  call    cs:__imp_GetLastError
0x18000dd16  movzx   ebx, ax
0x18000dd19  or      ebx, 0C0070000h
0x18000dd1f  lea     rcx, aOnecoreDsExtCl_9; "onecore\\ds\\ext\\cloudap\\dll\\mappeda"...
0x18000dd26  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000dd2b  mov     r9, rax
0x18000dd2e  lea     rax, Class
0x18000dd35  mov     [rsp+150h+lpSecurityAttributes], rax
0x18000dd3a  lea     rax, aConvertsidtost_0; "ConvertSidToStringSidW"
0x18000dd41  mov     qword ptr [rsp+150h+samDesired], rax
0x18000dd46  mov     [rsp+150h+dwOptions], 1A7h
0x18000dd4e  jmp     loc_18000E155
0x18000dd53  mov     rcx, rdi; Sid
0x18000dd56  call    cs:__imp_RtlLengthSid
0x18000dd5c  mov     edx, eax; uBytes
0x18000dd5e  mov     ecx, 40h ; '@'; uFlags
0x18000dd63  mov     ebx, eax
0x18000dd65  call    cs:__imp_LocalAlloc
0x18000dd6b  mov     rsi, rax
0x18000dd6e  test    rax, rax
0x18000dd71  jnz     short loc_18000DDAC
0x18000dd73  lea     rcx, aOnecoreDsExtCl_9; "onecore\\ds\\ext\\cloudap\\dll\\mappeda"...
0x18000dd7a  mov     ebx, 0C0000017h
0x18000dd7f  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000dd84  mov     r9, rax
0x18000dd87  lea     rax, Class
0x18000dd8e  mov     [rsp+150h+lpSecurityAttributes], rax
0x18000dd93  lea     rax, aLocalalloc; "LocalAlloc"
0x18000dd9a  mov     qword ptr [rsp+150h+samDesired], rax
0x18000dd9f  mov     [rsp+150h+dwOptions], 1AFh
0x18000dda7  jmp     loc_18000E155
0x18000ddac  mov     r8, rdi; SourceSid
0x18000ddaf  mov     rdx, rsi; DestinationSid
0x18000ddb2  mov     ecx, ebx; DestinationSidLength
0x18000ddb4  call    cs:__imp_RtlCopySid
0x18000ddba  mov     ebx, eax
0x18000ddbc  test    eax, eax
0x18000ddbe  jz      short loc_18000DDF4
0x18000ddc0  lea     rcx, aOnecoreDsExtCl_9; "onecore\\ds\\ext\\cloudap\\dll\\mappeda"...
0x18000ddc7  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000ddcc  mov     r9, rax
0x18000ddcf  lea     rax, Class
0x18000ddd6  mov     [rsp+150h+lpSecurityAttributes], rax
0x18000dddb  lea     rax, aRtlcopysid; "RtlCopySid"
0x18000dde2  mov     qword ptr [rsp+150h+samDesired], rax
0x18000dde7  mov     [rsp+150h+dwOptions], 1B3h
0x18000ddef  jmp     loc_18000E155
0x18000ddf4  prefetchw byte ptr cs:?g_lAccountCacheLoaded@@3JC; long volatile g_lAccountCacheLoaded
0x18000ddfb  mov     eax, cs:?g_lAccountCacheLoaded@@3JC; long volatile g_lAccountCacheLoaded
0x18000de01  mov     r13d, 1
0x18000de07  mov     ecx, eax
0x18000de09  and     ecx, r13d
0x18000de0c  lock cmpxchg cs:?g_lAccountCacheLoaded@@3JC, ecx; long volatile g_lAccountCacheLoaded
0x18000de14  jnz     short loc_18000DE07
0x18000de16  test    eax, eax
0x18000de18  jnz     short loc_18000DE7D
0x18000de1a  mov     rcx, [rsp+150h+var_100]
0x18000de1f  mov     rcx, [rcx+160h]; hKey
0x18000de26  call    LoadMappedSids
0x18000de2b  mov     ebx, eax
0x18000de2d  test    eax, eax
0x18000de2f  jz      short loc_18000DE7D
0x18000de31  lea     r9, aOnecoreDsExtCl_9+2Ch; ""
0x18000de38  lea     rcx, aOnecoreDsExtCl_9; "onecore\\ds\\ext\\cloudap\\dll\\mappeda"...
0x18000de3f  mov     rax, r9
0x18000de42  dec     r9
0x18000de45  cmp     byte ptr [r9], 5Ch ; '\'
0x18000de49  jz      short loc_18000DE54
0x18000de4b  cmp     r9, rcx
0x18000de4e  ja      short loc_18000DE3F
0x18000de50  cmp     byte ptr [r9], 5Ch ; '\'
0x18000de54  cmovz   r9, rax
0x18000de58  lea     rax, Class
0x18000de5f  mov     [rsp+150h+lpSecurityAttributes], rax
0x18000de64  lea     rax, aLoadmappedsids; "LoadMappedSids"
0x18000de6b  mov     qword ptr [rsp+150h+samDesired], rax
0x18000de70  mov     [rsp+150h+dwOptions], 1B8h
0x18000de78  jmp     loc_18000E155
0x18000de7d  mov     dl, r13b; Wait
0x18000de80  lea     rcx, ?g_AadConnectMapLock@@3U_RTL_RESOURCE@@A; Resource
0x18000de87  call    cs:__imp_RtlAcquireResourceExclusive
0x18000de8d  mov     rax, cs:?g_MappedUserNameHashList@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_MappedUserNameHashList
0x18000de94  lea     r10, ?g_MappedUserNameHashList@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_MappedUserNameHashList
0x18000de9b  cmp     rax, r10
0x18000de9e  jz      loc_18000E110
0x18000dea4  lea     rcx, [rax+10h]
0x18000dea8  mov     rdi, rax
0x18000deab  lea     r8, [rbp+50h+var_D0]
0x18000deaf  sub     r8, rcx
0x18000deb2  movzx   edx, word ptr [rcx]
0x18000deb5  movzx   r9d, word ptr [rcx+r8]
0x18000deba  sub     edx, r9d
0x18000debd  jnz     short loc_18000DEC8
0x18000debf  add     rcx, 2
0x18000dec3  test    r9d, r9d
0x18000dec6  jnz     short loc_18000DEB2
0x18000dec8  test    edx, edx
0x18000deca  jz      short loc_18000DED6
0x18000decc  mov     rax, [rax]
0x18000decf  xor     edi, edi
0x18000ded1  cmp     rax, r10
0x18000ded4  jnz     short loc_18000DEA4
0x18000ded6  test    rdi, rdi
0x18000ded9  jz      loc_18000E110
0x18000dedf  mov     rcx, [rdi+98h]; Sid
0x18000dee6  lea     rdx, [rsp+150h+var_E0]; StringSid
0x18000deeb  call    cs:__imp_ConvertSidToStringSidW
0x18000def1  test    eax, eax
0x18000def3  jnz     short loc_18000DF5D
0x18000def5  call    cs:__imp_GetLastError
0x18000defb  test    eax, eax
0x18000defd  jg      short loc_18000DF09
0x18000deff  call    cs:__imp_GetLastError
0x18000df05  mov     ebx, eax
0x18000df07  jmp     short loc_18000DF18
0x18000df09  call    cs:__imp_GetLastError
0x18000df0f  movzx   ebx, ax
0x18000df12  or      ebx, 0C0070000h
0x18000df18  lea     rcx, aOnecoreDsExtCl_9; "onecore\\ds\\ext\\cloudap\\dll\\mappeda"...
0x18000df1f  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000df24  mov     r9, rax
0x18000df27  lea     rax, Class
0x18000df2e  mov     [rsp+150h+lpSecurityAttributes], rax
0x18000df33  lea     rax, aConvertsidtost_0; "ConvertSidToStringSidW"
0x18000df3a  mov     qword ptr [rsp+150h+samDesired], rax
0x18000df3f  mov     [rsp+150h+dwOptions], 1D6h
0x18000df47  mov     r8d, ebx
0x18000df4a  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18000df51  xor     ecx, ecx
0x18000df53  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18000df58  jmp     loc_18000E0D3
0x18000df5d  mov     rcx, [rsp+150h+var_100]
0x18000df62  lea     rax, [rsp+150h+dwDisposition]
0x18000df67  mov     [rsp+150h+lpdwDisposition], rax; lpdwDisposition
0x18000df6c  lea     r14, SubKey; "SidMap"
0x18000df73  lea     rax, [rsp+150h+hKey]
0x18000df78  xor     r9d, r9d; lpClass
0x18000df7b  mov     [rsp+150h+phkResult], rax; phkResult
0x18000df80  xor     r8d, r8d; Reserved
0x18000df83  mov     rcx, [rcx+160h]; hKey
0x18000df8a  mov     rdx, r14; lpSubKey
0x18000df8d  mov     [rsp+150h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18000df96  mov     [rsp+150h+samDesired], 0F003Fh; samDesired
0x18000df9e  mov     [rsp+150h+dwOptions], 0; dwOptions
0x18000dfa6  call    cs:__imp_RegCreateKeyExW
0x18000dfac  mov     ebx, eax
0x18000dfae  test    eax, eax
0x18000dfb0  jz      short loc_18000DFEA
0x18000dfb2  jle     short loc_18000DFBD
0x18000dfb4  movzx   ebx, ax
0x18000dfb7  or      ebx, 0C0070000h
0x18000dfbd  lea     rcx, aOnecoreDsExtCl_9; "onecore\\ds\\ext\\cloudap\\dll\\mappeda"...
0x18000dfc4  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000dfc9  mov     [rsp+150h+lpSecurityAttributes], r14
0x18000dfce  mov     r9, rax
0x18000dfd1  lea     rax, aRegcreatekeyex_0; "RegCreateKeyEx"
0x18000dfd8  mov     qword ptr [rsp+150h+samDesired], rax
0x18000dfdd  mov     [rsp+150h+dwOptions], 1E7h
0x18000dfe5  jmp     loc_18000DF47
0x18000dfea  mov     rax, [rsp+150h+StringSid]
0x18000dfef  lea     r14, aInternetsid; "InternetSid"
0x18000dff6  mov     rdx, [rsp+150h+var_E0]; unsigned __int16 *
0x18000dffb  mov     r9, r14; unsigned __int16 *
0x18000dffe  mov     rcx, [rsp+150h+hKey]; HKEY
0x18000e003  xor     r8d, r8d; unsigned __int16 *
0x18000e006  mov     qword ptr [rsp+150h+dwOptions], rax; unsigned __int16 *
0x18000e00b  call    ?SetStringRegVal@@YAJPEAUHKEY__@@PEBG111@Z; SetStringRegVal(HKEY__ *,ushort const *,ushort const *,ushort const *,ushort const *)
0x18000e010  mov     ebx, eax
0x18000e012  test    eax, eax
0x18000e014  jz      short loc_18000E043
0x18000e016  lea     rcx, aOnecoreDsExtCl_9; "onecore\\ds\\ext\\cloudap\\dll\\mappeda"...
0x18000e01d  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18000e022  mov     [rsp+150h+lpSecurityAttributes], r14
0x18000e027  mov     r9, rax
0x18000e02a  lea     rax, aSetstringregva_8; "SetStringRegVal"
0x18000e031  mov     qword ptr [rsp+150h+samDesired], rax
0x18000e036  mov     [rsp+150h+dwOptions], 1F0h
0x18000e03e  jmp     loc_18000DF47
0x18000e043  mov     rcx, [rsp+150h+hKey]; hKey
0x18000e048  call    cs:__imp_RegFlushKey
0x18000e04e  mov     rbx, cs:?g_MappedAccountCacheList@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_MappedAccountCacheList
0x18000e055  mov     rcx, [rdi+98h]
0x18000e05c  lea     rax, ?g_MappedAccountCacheList@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_MappedAccountCacheList
0x18000e063  cmp     rbx, rax
0x18000e066  jz      short loc_18000E088
0x18000e068  mov     rdx, rcx; Sid2
0x18000e06b  mov     rcx, [rbx+10h]; Sid1
0x18000e06f  call    cs:__imp_RtlEqualSid
0x18000e075  test    al, al
0x18000e077  jnz     short loc_18000E07E
0x18000e079  mov     rbx, [rbx]
0x18000e07c  jmp     short loc_18000E055
0x18000e07e  mov     [rbx+18h], rsi
0x18000e082  xor     esi, esi
0x18000e084  xor     ebx, ebx
0x18000e086  jmp     short loc_18000E0D3
0x18000e088  mov     rdx, rsi
0x18000e08b  call    AddSidMapIntoCache
0x18000e090  mov     ebx, eax
0x18000e092  test    eax, eax
  ... truncated ...
```
