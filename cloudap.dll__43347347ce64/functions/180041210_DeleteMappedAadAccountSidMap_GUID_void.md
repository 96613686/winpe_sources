# DeleteMappedAadAccountSidMap(_GUID *,void *)

- ea: `0x180041210`
- end: `0x1800414fe`
- name: `?DeleteMappedAadAccountSidMap@@YAJPEAU_GUID@@PEAX@Z`
- size: `750`
- prototype: `__int64 __fastcall(struct _GUID *, void *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180040fe4`
- `0x180052358`

## callees

- `0x180007fc0`
- `0x18000a600`
- `0x18000e900`
- `0x18000ee60`
- `0x180041210`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800412f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800412fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041304`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800412f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800412fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041304`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800412e6`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800412e6`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800413cc`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800413cc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800414dc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800414dc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004137b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004137b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004144b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004145a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180041463`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800414eb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004144b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004145a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180041463`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800414eb`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800412a8`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800412a8`
- `ntdll!RtlReleaseResource` at `0x18004147e`
- `ntdll!RtlReleaseResource` at `0x18004147e`
- `ntdll!RtlEqualSid` at `0x1800412d0`
- `ntdll!RtlEqualSid` at `0x1800412d0`

## string_xrefs

- `0x180041251`: `onecore\ds\ext\cloudap\dll\mappedaccount.cpp`
- `0x180041313`: `onecore\ds\ext\cloudap\dll\mappedaccount.cpp`
- `0x180041394`: `onecore\ds\ext\cloudap\dll\mappedaccount.cpp`
- `0x1800413f8`: `onecore\ds\ext\cloudap\dll\mappedaccount.cpp`
- `0x180041486`: `onecore\ds\ext\cloudap\dll\mappedaccount.cpp`
- `0x18004132e`: `ConvertSidToStringSidW`
- `0x1800413a8`: `RegOpenKeyEx`
- `0x180041363`: `SidMap`
- `0x180041410`: `RegDeleteKeyEx`

## pseudocode

```c
__int64 __fastcall DeleteMappedAadAccountSidMap(struct _GUID *a1, void *a2)
{
  struct _ApPluginPkg *v2; // r14
  unsigned int LastError; // ebx
  const char *v5; // rax
  HLOCAL *i; // rdi
  const char *v7; // r9
  LSTATUS v8; // eax
  const char *v9; // r9
  LSTATUS v10; // eax
  const char *v11; // rax
  __int64 v12; // r8
  _QWORD *v13; // rax
  HLOCAL *v14; // rcx
  HLOCAL v15; // rcx
  HLOCAL v16; // rcx
  const char *v17; // rax
  int phkResulta; // [rsp+20h] [rbp-20h]
  int phkResultb; // [rsp+20h] [rbp-20h]
  PHKEY phkResult; // [rsp+20h] [rbp-20h]
  int phkResultc; // [rsp+20h] [rbp-20h]
  LPWSTR StringSid; // [rsp+70h] [rbp+30h] BYREF
  struct _ApPluginPkg *v24; // [rsp+80h] [rbp+40h] BYREF
  HKEY hKey; // [rsp+88h] [rbp+48h] BYREF

  v2 = 0;
  v24 = 0;
  StringSid = 0;
  hKey = 0;
  if ( a1 && a2 )
  {
    LastError = RefPackage(a1, &v24);
    if ( (LastError & 0x80000000) == 0 )
    {
      RtlAcquireResourceExclusive(&g_AadConnectMapLock, 1u);
      for ( i = (HLOCAL *)g_MappedAccountCacheList; ; i = (HLOCAL *)*i )
      {
        v2 = v24;
        if ( i == &g_MappedAccountCacheList )
        {
          LastError = -1073741275;
          goto LABEL_34;
        }
        if ( RtlEqualSid(i[2], a2) )
          break;
      }
      if ( ConvertSidToStringSidW(a2, &StringSid) )
      {
        v8 = RegOpenKeyExW(*((HKEY *)v2 + 44), L"SidMap", 0, 0xF003Fu, &hKey);
        if ( v8 )
        {
          if ( v8 > 0 )
            LastError = (unsigned __int16)v8 | 0xC0070000;
          else
            LastError = v8;
          v9 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\mappedaccount.cpp");
          LODWORD(phkResult) = 628;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", LastError, v9, phkResult, "RegOpenKeyEx", L"SidMap");
        }
        else
        {
          v10 = RegDeleteKeyExW(hKey, StringSid, 0, 0);
          if ( (v10 & 0xFFFFFFFD) != 0 )
          {
            if ( v10 > 0 )
              LastError = (unsigned __int16)v10 | 0xC0070000;
            else
              LastError = v10;
            v11 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\mappedaccount.cpp");
            LODWORD(phkResult) = 640;
            WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", LastError, v11, phkResult, "RegDeleteKeyEx", v12);
          }
          else
          {
            v13 = *i;
            if ( *((HLOCAL **)*i + 1) != i || (v14 = (HLOCAL *)i[1], *v14 != i) )
              __fastfail(3u);
            *v14 = v13;
            v13[1] = v14;
            v15 = i[2];
            if ( v15 )
              LocalFree(v15);
            v16 = i[3];
            if ( v16 )
              LocalFree(v16);
            LocalFree(i);
          }
        }
      }
      else
      {
        if ( (int)GetLastError() > 0 )
          LastError = (unsigned __int16)GetLastError() | 0xC0070000;
        else
          LastError = GetLastError();
        v7 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\mappedaccount.cpp");
        phkResultb = 616;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", LastError, v7, phkResultb, "ConvertSidToStringSidW", &Class);
      }
LABEL_34:
      RtlReleaseResource(&g_AadConnectMapLock);
    }
    else
    {
      v5 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\mappedaccount.cpp");
      phkResulta = 595;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", LastError, v5, phkResulta, "RefPackage", &Class);
      v2 = v24;
      LastError = -1073741637;
    }
  }
  else
  {
    LastError = -1073741811;
    v17 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\mappedaccount.cpp");
    phkResultc = 587;
    WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225485LL, v17, phkResultc, "Invalid Arg(s)", &Class);
  }
  DerefPackage(v2);
  if ( hKey )
    RegCloseKey(hKey);
  if ( StringSid )
    LocalFree(StringSid);
  return LastError;
}

```

## disassembly

```asm
0x180041210  push    rbp
0x180041212  push    rbx
0x180041213  push    rsi
0x180041214  push    rdi
0x180041215  push    r14
0x180041217  mov     rbp, rsp
0x18004121a  sub     rsp, 40h
0x18004121e  xor     r14d, r14d
0x180041221  mov     rsi, rdx
0x180041224  mov     [rbp+arg_10], r14
0x180041228  mov     [rbp+StringSid], r14
0x18004122c  mov     [rbp+hKey], r14
0x180041230  test    rcx, rcx
0x180041233  jz      loc_180041486
0x180041239  test    rdx, rdx
0x18004123c  jz      loc_180041486
0x180041242  lea     rdx, [rbp+arg_10]; struct _ApPluginPkg **
0x180041246  call    ?RefPackage@@YAJPEAU_GUID@@PEAPEAU_ApPluginPkg@@@Z; RefPackage(_GUID *,_ApPluginPkg * *)
0x18004124b  mov     ebx, eax
0x18004124d  test    eax, eax
0x18004124f  jns     short loc_18004129F
0x180041251  lea     rcx, aOnecoreDsExtCl_9; "onecore\\ds\\ext\\cloudap\\dll\\mappeda"...
0x180041258  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18004125d  lea     r8, Class
0x180041264  mov     r9, rax
0x180041267  mov     [rsp+40h+var_10], r8
0x18004126c  lea     rax, aRefpackage; "RefPackage"
0x180041273  mov     [rsp+40h+var_18], rax
0x180041278  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18004127f  mov     r8d, ebx
0x180041282  mov     dword ptr [rsp+40h+phkResult], 253h
0x18004128a  xor     ecx, ecx
0x18004128c  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180041291  mov     r14, [rbp+arg_10]
0x180041295  mov     ebx, 0C00000BBh
0x18004129a  jmp     loc_1800414CB
0x18004129f  mov     dl, 1; Wait
0x1800412a1  lea     rcx, ?g_AadConnectMapLock@@3U_RTL_RESOURCE@@A; Resource
0x1800412a8  call    cs:__imp_RtlAcquireResourceExclusive
0x1800412ae  mov     rdi, cs:?g_MappedAccountCacheList@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_MappedAccountCacheList
0x1800412b5  mov     r14, [rbp+arg_10]
0x1800412b9  lea     rax, ?g_MappedAccountCacheList@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_MappedAccountCacheList
0x1800412c0  cmp     rdi, rax
0x1800412c3  jz      loc_180041472
0x1800412c9  mov     rcx, [rdi+10h]; Sid1
0x1800412cd  mov     rdx, rsi; Sid2
0x1800412d0  call    cs:__imp_RtlEqualSid
0x1800412d6  test    al, al
0x1800412d8  jnz     short loc_1800412DF
0x1800412da  mov     rdi, [rdi]
0x1800412dd  jmp     short loc_1800412B5
0x1800412df  lea     rdx, [rbp+StringSid]; StringSid
0x1800412e3  mov     rcx, rsi; Sid
0x1800412e6  call    cs:__imp_ConvertSidToStringSidW
0x1800412ec  test    eax, eax
0x1800412ee  jnz     short loc_180041358
0x1800412f0  call    cs:__imp_GetLastError
0x1800412f6  test    eax, eax
0x1800412f8  jg      short loc_180041304
0x1800412fa  call    cs:__imp_GetLastError
0x180041300  mov     ebx, eax
0x180041302  jmp     short loc_180041313
0x180041304  call    cs:__imp_GetLastError
0x18004130a  movzx   ebx, ax
0x18004130d  or      ebx, 0C0070000h
0x180041313  lea     rcx, aOnecoreDsExtCl_9; "onecore\\ds\\ext\\cloudap\\dll\\mappeda"...
0x18004131a  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18004131f  mov     r9, rax
0x180041322  lea     r8, Class
0x180041329  mov     [rsp+40h+var_10], r8
0x18004132e  lea     rax, aConvertsidtost_0; "ConvertSidToStringSidW"
0x180041335  mov     [rsp+40h+var_18], rax
0x18004133a  mov     dword ptr [rsp+40h+phkResult], 268h
0x180041342  mov     r8d, ebx
0x180041345  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18004134c  xor     ecx, ecx
0x18004134e  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x180041353  jmp     loc_180041477
0x180041358  mov     rcx, [r14+160h]; hKey
0x18004135f  lea     rax, [rbp+hKey]
0x180041363  lea     rsi, SubKey; "SidMap"
0x18004136a  mov     [rsp+40h+phkResult], rax; phkResult
0x18004136f  mov     rdx, rsi; lpSubKey
0x180041372  mov     r9d, 0F003Fh; samDesired
0x180041378  xor     r8d, r8d; ulOptions
0x18004137b  call    cs:__imp_RegOpenKeyExW
0x180041381  test    eax, eax
0x180041383  jz      short loc_1800413BE
0x180041385  jg      short loc_18004138B
0x180041387  mov     ebx, eax
0x180041389  jmp     short loc_180041394
0x18004138b  movzx   ebx, ax
0x18004138e  or      ebx, 0C0070000h
0x180041394  lea     rcx, aOnecoreDsExtCl_9; "onecore\\ds\\ext\\cloudap\\dll\\mappeda"...
0x18004139b  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x1800413a0  mov     [rsp+40h+var_10], rsi
0x1800413a5  mov     r9, rax
0x1800413a8  lea     rax, aRegopenkeyex_0; "RegOpenKeyEx"
0x1800413af  mov     [rsp+40h+var_18], rax
0x1800413b4  mov     dword ptr [rsp+40h+phkResult], 274h
0x1800413bc  jmp     short loc_180041342
0x1800413be  mov     rdx, [rbp+StringSid]; lpSubKey
0x1800413c2  xor     r9d, r9d; Reserved
0x1800413c5  mov     rcx, [rbp+hKey]; hKey
0x1800413c9  xor     r8d, r8d; samDesired
0x1800413cc  call    cs:__imp_RegDeleteKeyExW
0x1800413d2  test    eax, 0FFFFFFFDh
0x1800413d7  jz      short loc_180041429
0x1800413d9  test    eax, eax
0x1800413db  jg      short loc_1800413E1
0x1800413dd  mov     ebx, eax
0x1800413df  jmp     short loc_1800413EA
0x1800413e1  movzx   ebx, ax
0x1800413e4  or      ebx, 0C0070000h
0x1800413ea  mov     rax, [rbp+StringSid]
0x1800413ee  lea     r8, Class
0x1800413f5  test    rax, rax
0x1800413f8  lea     rcx, aOnecoreDsExtCl_9; "onecore\\ds\\ext\\cloudap\\dll\\mappeda"...
0x1800413ff  cmovnz  r8, rax
0x180041403  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180041408  mov     [rsp+40h+var_10], r8
0x18004140d  mov     r9, rax
0x180041410  lea     rax, aRegdeletekeyex; "RegDeleteKeyEx"
0x180041417  mov     [rsp+40h+var_18], rax
0x18004141c  mov     dword ptr [rsp+40h+phkResult], 280h
0x180041424  jmp     loc_180041342
0x180041429  mov     rax, [rdi]
0x18004142c  cmp     [rax+8], rdi
0x180041430  jnz     short loc_18004146B
0x180041432  mov     rcx, [rdi+8]
0x180041436  cmp     [rcx], rdi
0x180041439  jnz     short loc_18004146B
0x18004143b  mov     [rcx], rax
0x18004143e  mov     [rax+8], rcx
0x180041442  mov     rcx, [rdi+10h]; hMem
0x180041446  test    rcx, rcx
0x180041449  jz      short loc_180041451
0x18004144b  call    cs:__imp_LocalFree
0x180041451  mov     rcx, [rdi+18h]; hMem
0x180041455  test    rcx, rcx
0x180041458  jz      short loc_180041460
0x18004145a  call    cs:__imp_LocalFree
0x180041460  mov     rcx, rdi; hMem
0x180041463  call    cs:__imp_LocalFree
0x180041469  jmp     short loc_180041477
0x18004146b  mov     ecx, 3
0x180041470  int     29h; Win8: RtlFailFast(ecx)
0x180041472  mov     ebx, 0C0000225h
0x180041477  lea     rcx, ?g_AadConnectMapLock@@3U_RTL_RESOURCE@@A; Resource
0x18004147e  call    cs:__imp_RtlReleaseResource
0x180041484  jmp     short loc_1800414CB
0x180041486  lea     rcx, aOnecoreDsExtCl_9; "onecore\\ds\\ext\\cloudap\\dll\\mappeda"...
0x18004148d  mov     ebx, 0C000000Dh
0x180041492  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x180041497  lea     r8, Class
0x18004149e  mov     r9, rax
0x1800414a1  mov     [rsp+40h+var_10], r8
0x1800414a6  lea     rax, aInvalidArgS; "Invalid Arg(s)"
0x1800414ad  mov     [rsp+40h+var_18], rax
0x1800414b2  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x1800414b9  mov     r8d, ebx
0x1800414bc  mov     dword ptr [rsp+40h+phkResult], 24Bh
0x1800414c4  xor     ecx, ecx
0x1800414c6  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x1800414cb  mov     rcx, r14; struct _ApPluginPkg *
0x1800414ce  call    ?DerefPackage@@YAXPEAU_ApPluginPkg@@@Z; DerefPackage(_ApPluginPkg *)
0x1800414d3  mov     rcx, [rbp+hKey]; hKey
0x1800414d7  test    rcx, rcx
0x1800414da  jz      short loc_1800414E2
0x1800414dc  call    cs:__imp_RegCloseKey
0x1800414e2  mov     rcx, [rbp+StringSid]; hMem
0x1800414e6  test    rcx, rcx
0x1800414e9  jz      short loc_1800414F1
0x1800414eb  call    cs:__imp_LocalFree
0x1800414f1  mov     eax, ebx
0x1800414f3  add     rsp, 40h
0x1800414f7  pop     r14
0x1800414f9  pop     rdi
0x1800414fa  pop     rsi
0x1800414fb  pop     rbx
0x1800414fc  pop     rbp
0x1800414fd  retn
```
