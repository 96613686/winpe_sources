# GetAuthenticatingAuthority(_ApPluginPkg *,ushort *,void *,ushort * *)

- ea: `0x18002ea68`
- end: `0x18002efe7`
- name: `?GetAuthenticatingAuthority@@YAJPEAU_ApPluginPkg@@PEAGPEAXPEAPEAG@Z`
- size: `1407`
- prototype: `__int64 __fastcall(struct _ApPluginPkg *, unsigned __int16 *, void *, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x180008060`
- `0x18004e7b0`
- `0x18004f600`

## callees

- `0x180006cb0`
- `0x180007690`
- `0x180007fc0`
- `0x18000a600`
- `0x18000a8f0`
- `0x18000b0c0`
- `0x18002ea68`
- `0x180042410`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002efa4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002efa4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002ebae`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002ed9e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002ebae`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002ed9e`
- `ntdll!RtlReleaseResource` at `0x18002ef94`
- `ntdll!RtlReleaseResource` at `0x18002ef94`
- `ntdll!RtlAcquireResourceShared` at `0x18002eabe`
- `ntdll!RtlAcquireResourceShared` at `0x18002eabe`

## string_xrefs

- `0x18002ec9b`: `onecore\ds\ext\cloudap\dll\lookups.cpp`
- `0x18002ece1`: `onecore\ds\ext\cloudap\dll\lookups.cpp`
- `0x18002eec9`: `onecore\ds\ext\cloudap\dll\lookups.cpp`
- `0x18002ef3f`: `onecore\ds\ext\cloudap\dll\lookups.cpp`
- `0x18002eb09`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18002eb70`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18002ebbe`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18002ec40`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18002ed3d`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18002edb1`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18002ee4f`: `onecore\ds\ext\cloudap\dll\utils.cpp`
- `0x18002eb4a`: `Name2Sid`
- `0x18002eee7`: `FindUserInCacheBySid`
- `0x18002ecb1`: `FindUserInCacheByName`
- `0x18002ebd0`: `RegOpenKeyExW`
- `0x18002edcc`: `RegOpenKeyExW`
- `0x18002ed51`: `GetUserSid2NameSubKey`

## pseudocode

```c
__int64 __fastcall GetAuthenticatingAuthority(
        struct _ApPluginPkg *a1,
        unsigned __int16 *a2,
        void *a3,
        unsigned __int16 **a4)
{
  void *v6; // r12
  HKEY v9; // rbx
  unsigned int HashString; // edi
  const UCHAR *v11; // rax
  const UCHAR *v12; // rcx
  __int64 v13; // r10
  const char *v14; // r15
  const char *v15; // r11
  __int64 v16; // r8
  int v17; // ecx
  const char *v18; // rax
  WCHAR *v19; // rdx
  unsigned int UserSid2NameSubKey; // ebx
  const char *v21; // r9
  HKEY v22; // rdi
  LPCWSTR v23; // r14
  const char *v24; // rax
  const char *v25; // rax
  __int64 v26; // r8
  const char *v27; // rax
  __int64 v28; // r8
  const UCHAR *v29; // rax
  const UCHAR *v30; // rcx
  bool v31; // zf
  const char *v32; // rax
  unsigned int RegVal; // eax
  const char *v34; // rax
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  PHKEY phkResulta; // [rsp+20h] [rbp-E0h]
  PHKEY phkResultb; // [rsp+20h] [rbp-E0h]
  PHKEY phkResultc; // [rsp+20h] [rbp-E0h]
  PHKEY phkResultd; // [rsp+20h] [rbp-E0h]
  const char *v41; // [rsp+28h] [rbp-D8h]
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  LPCWSTR lpSubKey; // [rsp+48h] [rbp-B8h] BYREF
  void *v44; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR SubKey[80]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v46[72]; // [rsp+100h] [rbp+0h] BYREF

  hKey = 0;
  v6 = 0;
  v44 = 0;
  *a4 = 0;
  RtlAcquireResourceShared(&g_LookupsCacheLock, 1u);
  if ( a2 )
  {
    v9 = (HKEY)*((_QWORD *)a1 + 44);
    hKey = 0;
    if ( !v9 )
    {
      HashString = -1073741811;
      v11 = (const UCHAR *)_DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
      v17 = 1273;
      v14 = "Invalid Arg(s)";
      goto LABEL_19;
    }
    HashString = GetHashString(a2, v46);
    if ( HashString )
    {
      v11 = "";
      do
        v12 = v11--;
      while ( *v11 != 92 && v11 > "onecore\\ds\\ext\\cloudap\\dll\\utils.cpp" );
      v13 = 0;
      v14 = "GetHashString";
      v15 = "0x%08x %s:%u : %s:%ws";
      v16 = HashString;
      if ( *v11 == 92 )
        v11 = v12;
      v17 = 1279;
      goto LABEL_19;
    }
    HashString = RtlStringCchPrintfW(SubKey, 0x4Au, L"%ws\\%ws", L"Name2Sid", v46);
    if ( HashString )
    {
      v11 = (const UCHAR *)_DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
      v17 = 1287;
      v14 = "RtlStringCchPrintfW";
LABEL_19:
      v19 = (WCHAR *)&Class;
      goto LABEL_20;
    }
    HashString = RegOpenKeyExW(v9, SubKey, 0, 0x20019u, &hKey);
    if ( HashString )
    {
      v18 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
      v14 = "RegOpenKeyExW";
      LODWORD(phkResulta) = 1298;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", HashString, v18, phkResulta, "RegOpenKeyExW", SubKey);
      if ( HashString - 2 <= 1 )
      {
        HashString = -1073741275;
      }
      else if ( (int)HashString > 0 )
      {
        HashString = (unsigned __int16)HashString | 0xC0070000;
      }
      v11 = (const UCHAR *)_DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
      v19 = SubKey;
      v17 = 1308;
LABEL_20:
      LODWORD(phkResult) = v17;
      WPPTraceLogA(v13, v15, v16, v11, phkResult, v14, v19);
      if ( HashString != -1073741275 )
      {
        UserSid2NameSubKey = HashString;
        v21 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
        v41 = "FindUserInCacheByName";
        LODWORD(phkResult) = 130;
LABEL_22:
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", HashString, v21, phkResult, v41, &Class);
        goto LABEL_52;
      }
      goto LABEL_51;
    }
  }
  else
  {
    if ( !a3 )
    {
      HashString = -1073741811;
      UserSid2NameSubKey = -1073741811;
      v21 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
      v41 = "Invalid para";
      LODWORD(phkResult) = 137;
      goto LABEL_22;
    }
    v22 = (HKEY)*((_QWORD *)a1 + 44);
    v23 = 0;
    lpSubKey = 0;
    hKey = 0;
    if ( v22 )
    {
      UserSid2NameSubKey = GetUserSid2NameSubKey(a3, (unsigned __int16 **)&lpSubKey);
      if ( UserSid2NameSubKey )
      {
        v24 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", UserSid2NameSubKey, v24, 1463, "GetUserSid2NameSubKey", &Class);
        v23 = lpSubKey;
      }
      else
      {
        v23 = lpSubKey;
        UserSid2NameSubKey = RegOpenKeyExW(v22, lpSubKey, 0, 0x20019u, &hKey);
        if ( UserSid2NameSubKey )
        {
          v25 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
          LODWORD(phkResultb) = 1473;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", UserSid2NameSubKey, v25, phkResultb, "RegOpenKeyExW", v26);
          if ( UserSid2NameSubKey - 2 <= 1 )
          {
            UserSid2NameSubKey = -1073741275;
          }
          else if ( (int)UserSid2NameSubKey > 0 )
          {
            UserSid2NameSubKey = (unsigned __int16)UserSid2NameSubKey | 0xC0070000;
          }
          v27 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\utils.cpp");
          LODWORD(phkResultc) = 1483;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", UserSid2NameSubKey, v27, phkResultc, "RegOpenKeyExW", v28);
        }
        else
        {
          UserSid2NameSubKey = 0;
        }
      }
    }
    else
    {
      v29 = "";
      UserSid2NameSubKey = -1073741811;
      while ( 1 )
      {
        v30 = v29--;
        v31 = *v29 == 92;
        if ( *v29 == 92 )
          break;
        if ( v29 <= "onecore\\ds\\ext\\cloudap\\dll\\utils.cpp" )
        {
          v31 = *v29 == 92;
          break;
        }
      }
      if ( v31 )
        v29 = v30;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225485LL, v29, 1457, "Invalid Arg(s)", &Class);
    }
    if ( v23 )
      ((void (__fastcall *)(LPCWSTR))g_pLsaFunctionTable->FreeLsaHeap)(v23);
    if ( UserSid2NameSubKey == -1073741275 )
      goto LABEL_51;
    if ( UserSid2NameSubKey )
    {
      v32 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
      LODWORD(phkResultb) = 148;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", UserSid2NameSubKey, v32, phkResultb, "FindUserInCacheBySid", &Class);
      goto LABEL_52;
    }
  }
  LODWORD(lpSubKey) = 0;
  RegVal = GetRegVal(hKey, L"AuthenticatingAuthority", 6u, (unsigned int *)&lpSubKey, &v44);
  UserSid2NameSubKey = RegVal;
  if ( RegVal != -1073741275 && RegVal )
  {
    v34 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\lookups.cpp");
    LODWORD(phkResultd) = 161;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", UserSid2NameSubKey, v34, phkResultd, "GetStringRegVal(Authority)", &Class);
    v6 = v44;
    goto LABEL_52;
  }
  *a4 = (unsigned __int16 *)v44;
LABEL_51:
  UserSid2NameSubKey = 0;
LABEL_52:
  RtlReleaseResource(&g_LookupsCacheLock);
  if ( hKey )
    RegCloseKey(hKey);
  if ( v6 )
    ((void (__fastcall *)(void *))g_pLsaFunctionTable->FreeLsaHeap)(v6);
  return UserSid2NameSubKey;
}

```

## disassembly

```asm
0x18002ea68  push    rbp
0x18002ea6a  push    rbx
0x18002ea6b  push    rsi
0x18002ea6c  push    rdi
0x18002ea6d  push    r12
0x18002ea6f  push    r13
0x18002ea71  push    r14
0x18002ea73  push    r15
0x18002ea75  lea     rbp, [rsp-0A8h]
0x18002ea7d  sub     rsp, 1A8h
0x18002ea84  mov     rax, cs:__security_cookie
0x18002ea8b  xor     rax, rsp
0x18002ea8e  mov     [rbp+0E0h+var_50], rax
0x18002ea95  mov     rsi, rdx
0x18002ea98  mov     [rsp+1E0h+hKey], 0
0x18002eaa1  mov     rdi, rcx
0x18002eaa4  xor     r12d, r12d
0x18002eaa7  mov     dl, 1; Wait
0x18002eaa9  mov     [rsp+1E0h+var_190], r12
0x18002eaae  lea     rcx, ?g_LookupsCacheLock@@3U_RTL_RESOURCE@@A; Resource
0x18002eab5  mov     [r9], r12
0x18002eab8  mov     r13, r9
0x18002eabb  mov     rbx, r8
0x18002eabe  call    cs:__imp_RtlAcquireResourceShared
0x18002eac4  lea     r14, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18002eacb  lea     r15, Class
0x18002ead2  test    rsi, rsi
0x18002ead5  jz      loc_18002ECD7
0x18002eadb  mov     rbx, [rdi+160h]
0x18002eae2  mov     [rsp+1E0h+hKey], r12
0x18002eae7  test    rbx, rbx
0x18002eaea  jz      loc_18002EC3B
0x18002eaf0  lea     rdx, [rbp+0E0h+var_E0]; unsigned __int16 *
0x18002eaf4  mov     rcx, rsi; lpSrcStr
0x18002eaf7  call    ?GetHashString@@YAJPEBGQEAG@Z; GetHashString(ushort const *,ushort * const)
0x18002eafc  mov     edi, eax
0x18002eafe  test    eax, eax
0x18002eb00  jz      short loc_18002EB41
0x18002eb02  lea     rax, pbInput+24h; ""
0x18002eb09  lea     rsi, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18002eb10  mov     rcx, rax
0x18002eb13  dec     rax
0x18002eb16  cmp     byte ptr [rax], 5Ch ; '\'
0x18002eb19  jz      short loc_18002EB20
0x18002eb1b  cmp     rax, rsi
0x18002eb1e  ja      short loc_18002EB10
0x18002eb20  xor     r10d, r10d
0x18002eb23  lea     r15, aGethashstring; "GetHashString"
0x18002eb2a  cmp     byte ptr [rax], 5Ch ; '\'
0x18002eb2d  mov     r11, r14
0x18002eb30  mov     r8d, edi
0x18002eb33  cmovz   rax, rcx
0x18002eb37  mov     ecx, 4FFh
0x18002eb3c  jmp     loc_18002EC61
0x18002eb41  lea     rax, [rbp+0E0h+var_E0]
0x18002eb45  mov     edx, 4Ah ; 'J'; unsigned __int64
0x18002eb4a  lea     r9, aName2sid; "Name2Sid"
0x18002eb51  mov     [rsp+1E0h+phkResult], rax
0x18002eb56  lea     r8, aWsWs_1; "%ws\\%ws"
0x18002eb5d  lea     rcx, [rsp+1E0h+SubKey]; unsigned __int16 *
0x18002eb62  call    ?RtlStringCchPrintfW@@YAJPEAG_KPEBGZZ; RtlStringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002eb67  mov     edi, eax
0x18002eb69  test    eax, eax
0x18002eb6b  jz      short loc_18002EB93
0x18002eb6d  xor     r10d, r10d
0x18002eb70  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18002eb77  mov     r11, r14
0x18002eb7a  mov     r8d, eax
0x18002eb7d  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18002eb82  mov     ecx, 507h
0x18002eb87  lea     r15, aRtlstringcchpr; "RtlStringCchPrintfW"
0x18002eb8e  jmp     loc_18002EC61
0x18002eb93  lea     rax, [rsp+1E0h+hKey]
0x18002eb98  mov     r9d, 20019h; samDesired
0x18002eb9e  xor     r8d, r8d; ulOptions
0x18002eba1  mov     [rsp+1E0h+phkResult], rax; phkResult
0x18002eba6  lea     rdx, [rsp+1E0h+SubKey]; lpSubKey
0x18002ebab  mov     rcx, rbx; hKey
0x18002ebae  call    cs:__imp_RegOpenKeyExW
0x18002ebb4  mov     edi, eax
0x18002ebb6  test    eax, eax
0x18002ebb8  jz      loc_18002EF07
0x18002ebbe  lea     rsi, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18002ebc5  mov     rcx, rsi; char *
0x18002ebc8  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18002ebcd  mov     r9, rax
0x18002ebd0  lea     r15, aRegopenkeyexw; "RegOpenKeyExW"
0x18002ebd7  lea     rax, [rsp+1E0h+SubKey]
0x18002ebdc  mov     r8d, edi
0x18002ebdf  mov     [rsp+1E0h+var_1B0], rax
0x18002ebe4  mov     rdx, r14
0x18002ebe7  mov     [rsp+1E0h+var_1B8], r15
0x18002ebec  xor     ecx, ecx
0x18002ebee  mov     dword ptr [rsp+1E0h+phkResult], 512h
0x18002ebf6  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18002ebfb  lea     eax, [rdi-2]
0x18002ebfe  cmp     eax, 1
0x18002ec01  jbe     short loc_18002EC12
0x18002ec03  test    edi, edi
0x18002ec05  jle     short loc_18002EC17
0x18002ec07  movzx   edi, di
0x18002ec0a  or      edi, 0C0070000h
0x18002ec10  jmp     short loc_18002EC17
0x18002ec12  mov     edi, 0C0000225h
0x18002ec17  xor     r10d, r10d
0x18002ec1a  mov     rcx, rsi; char *
0x18002ec1d  mov     r11, r14
0x18002ec20  mov     r8d, edi
0x18002ec23  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18002ec28  lea     rdx, [rsp+1E0h+SubKey]
0x18002ec2d  mov     ecx, 51Ch
0x18002ec32  lea     rsi, Class
0x18002ec39  jmp     short loc_18002EC6B
0x18002ec3b  mov     edi, 0C000000Dh
0x18002ec40  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18002ec47  xor     r10d, r10d
0x18002ec4a  mov     r8d, edi
0x18002ec4d  mov     r11, r14
0x18002ec50  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18002ec55  mov     ecx, 4F9h
0x18002ec5a  lea     r15, aInvalidArgS; "Invalid Arg(s)"
0x18002ec61  lea     rsi, Class
0x18002ec68  mov     rdx, rsi
0x18002ec6b  mov     [rsp+1E0h+var_1B0], rdx
0x18002ec70  mov     r9, rax
0x18002ec73  mov     [rsp+1E0h+var_1B8], r15
0x18002ec78  mov     rdx, r11
0x18002ec7b  mov     dword ptr [rsp+1E0h+phkResult], ecx
0x18002ec7f  mov     rcx, r10
0x18002ec82  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18002ec87  cmp     edi, 0C0000225h
0x18002ec8d  jz      loc_18002EF8B
0x18002ec93  test    edi, edi
0x18002ec95  jz      loc_18002EF07
0x18002ec9b  lea     rcx, aOnecoreDsExtCl_5; "onecore\\ds\\ext\\cloudap\\dll\\lookups"...
0x18002eca2  mov     ebx, edi
0x18002eca4  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18002eca9  mov     [rsp+1E0h+var_1B0], rsi
0x18002ecae  mov     r9, rax
0x18002ecb1  lea     rax, aFinduserincach_3; "FindUserInCacheByName"
0x18002ecb8  mov     [rsp+1E0h+var_1B8], rax
0x18002ecbd  mov     dword ptr [rsp+1E0h+phkResult], 82h
0x18002ecc5  mov     r8d, edi
0x18002ecc8  mov     rdx, r14
0x18002eccb  xor     ecx, ecx
0x18002eccd  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18002ecd2  jmp     loc_18002EF8D
0x18002ecd7  test    rbx, rbx
0x18002ecda  jnz     short loc_18002ED0D
0x18002ecdc  mov     edi, 0C000000Dh
0x18002ece1  lea     rcx, aOnecoreDsExtCl_5; "onecore\\ds\\ext\\cloudap\\dll\\lookups"...
0x18002ece8  mov     ebx, edi
0x18002ecea  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18002ecef  mov     [rsp+1E0h+var_1B0], r15
0x18002ecf4  mov     r9, rax
0x18002ecf7  lea     rax, aInvalidPara; "Invalid para"
0x18002ecfe  mov     [rsp+1E0h+var_1B8], rax
0x18002ed03  mov     dword ptr [rsp+1E0h+phkResult], 89h
0x18002ed0b  jmp     short loc_18002ECC5
0x18002ed0d  mov     rdi, [rdi+160h]
0x18002ed14  xor     r14d, r14d
0x18002ed17  mov     [rsp+1E0h+lpSubKey], r14
0x18002ed1c  mov     [rsp+1E0h+hKey], r12
0x18002ed21  test    rdi, rdi
0x18002ed24  jz      loc_18002EE41
0x18002ed2a  lea     rdx, [rsp+1E0h+lpSubKey]; unsigned __int16 **
0x18002ed2f  mov     rcx, rbx; void *
0x18002ed32  call    ?GetUserSid2NameSubKey@@YAJPEAXPEAPEAG@Z; GetUserSid2NameSubKey(void *,ushort * *)
0x18002ed37  mov     ebx, eax
0x18002ed39  test    eax, eax
0x18002ed3b  jz      short loc_18002ED80
0x18002ed3d  lea     rcx, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18002ed44  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18002ed49  mov     r9, rax
0x18002ed4c  mov     [rsp+1E0h+var_1B0], r15
0x18002ed51  lea     rax, aGetusersid2nam; "GetUserSid2NameSubKey"
0x18002ed58  mov     r8d, ebx
0x18002ed5b  mov     [rsp+1E0h+var_1B8], rax
0x18002ed60  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18002ed67  xor     ecx, ecx
0x18002ed69  mov     dword ptr [rsp+1E0h+phkResult], 5B7h
0x18002ed71  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18002ed76  mov     r14, [rsp+1E0h+lpSubKey]
0x18002ed7b  jmp     loc_18002EEA1
0x18002ed80  mov     r14, [rsp+1E0h+lpSubKey]
0x18002ed85  lea     rax, [rsp+1E0h+hKey]
0x18002ed8a  mov     rdx, r14; lpSubKey
0x18002ed8d  mov     [rsp+1E0h+phkResult], rax; phkResult
0x18002ed92  mov     r9d, 20019h; samDesired
0x18002ed98  xor     r8d, r8d; ulOptions
0x18002ed9b  mov     rcx, rdi; hKey
0x18002ed9e  call    cs:__imp_RegOpenKeyExW
0x18002eda4  mov     ebx, eax
0x18002eda6  test    eax, eax
0x18002eda8  jz      loc_18002EE3D
0x18002edae  test    r14, r14
0x18002edb1  lea     rsi, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18002edb8  mov     r8, r15
0x18002edbb  mov     rcx, rsi; char *
0x18002edbe  cmovnz  r8, r14
0x18002edc2  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18002edc7  mov     [rsp+1E0h+var_1B0], r8
0x18002edcc  lea     r15, aRegopenkeyexw; "RegOpenKeyExW"
0x18002edd3  mov     [rsp+1E0h+var_1B8], r15
0x18002edd8  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18002eddf  mov     r9, rax
0x18002ede2  mov     dword ptr [rsp+1E0h+phkResult], 5C1h
0x18002edea  mov     r8d, ebx
0x18002eded  xor     ecx, ecx
0x18002edef  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18002edf4  lea     eax, [rbx-2]
0x18002edf7  cmp     eax, 1
0x18002edfa  jbe     short loc_18002EE0B
0x18002edfc  test    ebx, ebx
0x18002edfe  jle     short loc_18002EE10
0x18002ee00  movzx   ebx, bx
0x18002ee03  or      ebx, 0C0070000h
0x18002ee09  jmp     short loc_18002EE10
0x18002ee0b  mov     ebx, 0C0000225h
0x18002ee10  test    r14, r14
0x18002ee13  lea     r8, Class
0x18002ee1a  mov     rcx, rsi; char *
0x18002ee1d  cmovnz  r8, r14
0x18002ee21  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18002ee26  mov     [rsp+1E0h+var_1B0], r8
0x18002ee2b  mov     r8d, ebx
0x18002ee2e  mov     [rsp+1E0h+var_1B8], r15
0x18002ee33  mov     dword ptr [rsp+1E0h+phkResult], 5CBh
0x18002ee3b  jmp     short loc_18002EE89
0x18002ee3d  xor     ebx, ebx
0x18002ee3f  jmp     short loc_18002EEA1
0x18002ee41  mov     edi, 0C000000Dh
0x18002ee46  lea     rax, pbInput+24h; ""
0x18002ee4d  mov     ebx, edi
0x18002ee4f  lea     rsi, pbInput; "onecore\\ds\\ext\\cloudap\\dll\\utils.c"...
0x18002ee56  mov     rcx, rax
0x18002ee59  dec     rax
0x18002ee5c  cmp     byte ptr [rax], 5Ch ; '\'
0x18002ee5f  jz      short loc_18002EE69
0x18002ee61  cmp     rax, rsi
0x18002ee64  ja      short loc_18002EE56
0x18002ee66  cmp     byte ptr [rax], 5Ch ; '\'
0x18002ee69  mov     [rsp+1E0h+var_1B0], r15
0x18002ee6e  cmovz   rax, rcx
0x18002ee72  lea     r15, aInvalidArgS; "Invalid Arg(s)"
0x18002ee79  mov     r8d, edi
0x18002ee7c  mov     [rsp+1E0h+var_1B8], r15
0x18002ee81  mov     dword ptr [rsp+1E0h+phkResult], 5B1h
0x18002ee89  mov     r9, rax
0x18002ee8c  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18002ee93  xor     ecx, ecx
0x18002ee95  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18002ee9a  lea     r15, Class
0x18002eea1  test    r14, r14
0x18002eea4  jz      short loc_18002EEB9
0x18002eea6  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18002eead  mov     rcx, r14
0x18002eeb0  mov     rax, [rax+30h]
0x18002eeb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eeb9  cmp     ebx, 0C0000225h
0x18002eebf  jz      loc_18002EF8B
0x18002eec5  test    ebx, ebx
0x18002eec7  jz      short loc_18002EF00
0x18002eec9  lea     rcx, aOnecoreDsExtCl_5; "onecore\\ds\\ext\\cloudap\\dll\\lookups"...
0x18002eed0  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18002eed5  mov     [rsp+1E0h+var_1B0], r15
0x18002eeda  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18002eee1  mov     r9, rax
0x18002eee4  mov     r8d, ebx
0x18002eee7  lea     rax, aFinduserincach; "FindUserInCacheBySid"
0x18002eeee  mov     [rsp+1E0h+var_1B8], rax
0x18002eef3  mov     dword ptr [rsp+1E0h+phkResult], 94h
0x18002eefb  jmp     loc_18002ECCB
0x18002ef00  lea     r14, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18002ef07  mov     rcx, [rsp+1E0h+hKey]; hkey
0x18002ef0c  lea     rax, [rsp+1E0h+var_190]
0x18002ef11  lea     r9, [rsp+1E0h+lpSubKey]; unsigned int *
0x18002ef16  mov     [rsp+1E0h+phkResult], rax; void **
0x18002ef1b  mov     r8d, 6; dwFlags
0x18002ef21  mov     dword ptr [rsp+1E0h+lpSubKey], r12d
0x18002ef26  lea     rdx, aAuthenticating; "AuthenticatingAuthority"
0x18002ef2d  call    ?GetRegVal@@YAJPEAUHKEY__@@PEBGKPEAKPEAPEAX@Z; GetRegVal(HKEY__ *,ushort const *,ulong,ulong *,void * *)
0x18002ef32  mov     ebx, eax
0x18002ef34  cmp     eax, 0C0000225h
0x18002ef39  jz      short loc_18002EF82
0x18002ef3b  test    eax, eax
0x18002ef3d  jz      short loc_18002EF82
0x18002ef3f  lea     rcx, aOnecoreDsExtCl_5; "onecore\\ds\\ext\\cloudap\\dll\\lookups"...
0x18002ef46  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18002ef4b  mov     r9, rax
0x18002ef4e  mov     r8d, ebx
0x18002ef51  lea     rax, Class
0x18002ef58  mov     rdx, r14
0x18002ef5b  mov     [rsp+1E0h+var_1B0], rax
0x18002ef60  xor     ecx, ecx
0x18002ef62  lea     rax, aGetstringregva_5; "GetStringRegVal(Authority)"
0x18002ef69  mov     [rsp+1E0h+var_1B8], rax
0x18002ef6e  mov     dword ptr [rsp+1E0h+phkResult], 0A1h
0x18002ef76  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18002ef7b  mov     r12, [rsp+1E0h+var_190]
  ... truncated ...
```
