# LoadSubPkgs(_ApPluginPkg *)

- ea: `0x18004c808`
- end: `0x18004cc9a`
- name: `?LoadSubPkgs@@YAJPEAU_ApPluginPkg@@@Z`
- size: `1170`
- prototype: `__int64 __fastcall(struct _ApPluginPkg *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x18001a624`

## callees

- `0x180003ef4`
- `0x180007fc0`
- `0x18000a600`
- `0x18000a8f0`
- `0x18002b260`
- `0x18004c808`
- `0x180081010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004caa5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004cc30`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004cc3f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004caa5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004cc30`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004cc3f`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18004c902`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18004c902`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18004ca4c`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18004ca4c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004c85e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004cacc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004c85e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004cacc`

## string_xrefs

- `0x18004c89c`: `RegOpenKeyEx`
- `0x18004ca19`: `RegOpenKeyEx`
- `0x18004c881`: `onecore\ds\ext\cloudap\dll\appluginpackage.cpp`
- `0x18004c919`: `onecore\ds\ext\cloudap\dll\appluginpackage.cpp`
- `0x18004c97d`: `onecore\ds\ext\cloudap\dll\appluginpackage.cpp`
- `0x18004c9cc`: `onecore\ds\ext\cloudap\dll\appluginpackage.cpp`
- `0x18004ca66`: `onecore\ds\ext\cloudap\dll\appluginpackage.cpp`
- `0x18004cae6`: `onecore\ds\ext\cloudap\dll\appluginpackage.cpp`
- `0x18004cb5d`: `onecore\ds\ext\cloudap\dll\appluginpackage.cpp`
- `0x18004cbb7`: `onecore\ds\ext\cloudap\dll\appluginpackage.cpp`
- `0x18004cc5a`: `onecore\ds\ext\cloudap\dll\appluginpackage.cpp`

## pseudocode

```c
__int64 __fastcall LoadSubPkgs(struct _ApPluginPkg *a1)
{
  unsigned __int16 *v1; // r14
  HKEY v3; // rcx
  unsigned int v4; // ebx
  const char *v5; // r9
  LSTATUS v6; // eax
  const char *v7; // r9
  __int64 v8; // rcx
  const char *v9; // r9
  WCHAR *v10; // rbx
  const char *v11; // r9
  DWORD i; // r15d
  const char *v13; // r9
  __int64 v14; // r8
  unsigned int v15; // eax
  __int64 v16; // rdx
  const char *v17; // r9
  __int64 v18; // r8
  const char *v19; // rax
  __int64 v20; // r8
  const char *v21; // r9
  __int64 v22; // r8
  const char *v24; // r9
  PHKEY phkResult; // [rsp+20h] [rbp-60h]
  PHKEY phkResulta; // [rsp+20h] [rbp-60h]
  PHKEY phkResultb; // [rsp+20h] [rbp-60h]
  PHKEY phkResultc; // [rsp+20h] [rbp-60h]
  PHKEY phkResultd; // [rsp+20h] [rbp-60h]
  HKEY hKey; // [rsp+60h] [rbp-20h] BYREF
  HKEY hkey; // [rsp+68h] [rbp-18h] BYREF
  unsigned __int16 *v32; // [rsp+70h] [rbp-10h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+C0h] [rbp+40h] BYREF
  DWORD cSubKeys; // [rsp+C8h] [rbp+48h] BYREF
  DWORD cchName; // [rsp+D0h] [rbp+50h] BYREF
  unsigned int v36; // [rsp+D8h] [rbp+58h] BYREF

  v1 = 0;
  cSubKeys = 0;
  v32 = 0;
  v3 = (HKEY)*((_QWORD *)a1 + 44);
  hKey = 0;
  hkey = 0;
  cbMaxSubKeyLen = 0;
  v4 = RegOpenKeyExW(v3, L"SubPkgs", 0, 0x20019u, &hKey);
  if ( v4 - 2 > 1 )
  {
    if ( v4 )
    {
      if ( (int)v4 > 0 )
        v4 = (unsigned __int16)v4 | 0xC0070000;
      v5 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\appluginpackage.cpp");
      LODWORD(phkResult) = 281;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v4, v5, phkResult, "RegOpenKeyEx", &Class);
      goto LABEL_34;
    }
    v6 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
    v4 = v6;
    if ( v6 )
    {
      if ( v6 > 0 )
        v4 = (unsigned __int16)v6 | 0xC0070000;
      v7 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\appluginpackage.cpp");
      LODWORD(phkResulta) = 303;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v4, v7, phkResulta, "RegQueryInfoKey", &Class);
      goto LABEL_34;
    }
    if ( !cSubKeys )
    {
      v4 = 0;
      goto LABEL_34;
    }
    v8 = cbMaxSubKeyLen + 1;
    if ( (unsigned int)v8 < cbMaxSubKeyLen )
    {
      cbMaxSubKeyLen = -1;
      v4 = -1073741675;
      v24 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\appluginpackage.cpp");
      LODWORD(phkResulta) = 313;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225621LL, v24, phkResulta, "RtlDWordAdd", &Class);
      goto LABEL_34;
    }
    ++cbMaxSubKeyLen;
    v4 = RtlULongLongToULong(2 * v8, &cbMaxSubKeyLen);
    if ( v4 )
    {
      v9 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\appluginpackage.cpp");
      LODWORD(phkResulta) = 316;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v4, v9, phkResulta, "RtlDWordMult", &Class);
      goto LABEL_34;
    }
    v10 = (WCHAR *)((__int64 (__fastcall *)(_QWORD))g_pLsaFunctionTable->AllocateLsaHeap)(cbMaxSubKeyLen);
    if ( !v10 )
    {
      v4 = -1073741801;
      v11 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\appluginpackage.cpp");
      LODWORD(phkResulta) = 322;
      WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", 3221225495LL, v11, phkResulta, "AllocateLsaHeap", &Class);
      goto LABEL_34;
    }
    for ( i = 0; i < cSubKeys; ++i )
    {
      cchName = cbMaxSubKeyLen >> 1;
      if ( RegEnumKeyExW(hKey, i, v10, &cchName, 0, 0, 0, 0) )
      {
        v13 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\appluginpackage.cpp");
        LODWORD(phkResultb) = 343;
        WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v14, v13, phkResultb, "RegEnumKeyEx", &Class);
      }
      else
      {
        v10[cchName] = 0;
        if ( hkey )
        {
          RegCloseKey(hkey);
          hkey = 0;
        }
        v15 = RegOpenKeyExW(hKey, v10, 0, 0x20019u, &hkey);
        if ( v15 )
        {
          v17 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\appluginpackage.cpp");
          LODWORD(phkResultc) = 364;
          WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v18, v17, phkResultc, "RegOpenKeyEx", v10);
        }
        else
        {
          if ( v1 )
          {
            ((void (__fastcall *)(unsigned __int16 *, __int64, _QWORD))g_pLsaFunctionTable->FreeLsaHeap)(v1, v16, v15);
            v32 = 0;
          }
          v36 = 0;
          if ( (int)GetRegVal(hkey, L"AuthenticatingAuthorityDns", 6u, &v36, (void **)&v32) >= 0 )
          {
            v1 = v32;
            if ( (unsigned int)RegisterSubPackage(1, a1, v10, v32) )
            {
              v21 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\appluginpackage.cpp");
              LODWORD(phkResultd) = 389;
              WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v22, v21, phkResultd, "RegisterSubPackage", v10);
            }
          }
          else
          {
            v19 = _DBG_BASENAME("onecore\\ds\\ext\\cloudap\\dll\\appluginpackage.cpp");
            LODWORD(phkResultd) = 380;
            WPPTraceLogA(0, "0x%08x %s:%u : %s:%ws", v20, v19, phkResultd, "GetStringRegVal", v10);
            v1 = v32;
          }
        }
      }
    }
    ((void (__fastcall *)(WCHAR *))g_pLsaFunctionTable->FreeLsaHeap)(v10);
  }
  v4 = 0;
  if ( v1 )
    ((void (__fastcall *)(unsigned __int16 *))g_pLsaFunctionTable->FreeLsaHeap)(v1);
LABEL_34:
  if ( hKey )
    RegCloseKey(hKey);
  if ( hkey )
    RegCloseKey(hkey);
  return v4;
}

```

## disassembly

```asm
0x18004c808  push    rbp
0x18004c80a  push    rbx
0x18004c80b  push    rdi
0x18004c80c  push    r12
0x18004c80e  push    r13
0x18004c810  push    r14
0x18004c812  push    r15
0x18004c814  mov     rbp, rsp
0x18004c817  sub     rsp, 80h
0x18004c81e  xor     r14d, r14d
0x18004c821  mov     [rbp+cSubKeys], 0
0x18004c828  mov     r13, rcx
0x18004c82b  mov     [rbp+var_10], r14
0x18004c82f  mov     rcx, [rcx+160h]; hKey
0x18004c836  lea     rax, [rbp+hKey]
0x18004c83a  mov     r9d, 20019h; samDesired
0x18004c840  mov     [rbp+hKey], r14
0x18004c844  xor     r8d, r8d; ulOptions
0x18004c847  mov     [rbp+hkey], r14
0x18004c84b  lea     rdx, aSubpkgs; "SubPkgs"
0x18004c852  mov     [rsp+80h+phkResult], rax; phkResult
0x18004c857  mov     [rbp+cbMaxSubKeyLen], 0
0x18004c85e  call    cs:__imp_RegOpenKeyExW
0x18004c864  mov     ebx, eax
0x18004c866  add     eax, 0FFFFFFFEh
0x18004c869  cmp     eax, 1
0x18004c86c  jbe     loc_18004CC0D
0x18004c872  test    ebx, ebx
0x18004c874  jz      short loc_18004C8C6
0x18004c876  jle     short loc_18004C881
0x18004c878  movzx   ebx, bx
0x18004c87b  or      ebx, 0C0070000h
0x18004c881  lea     rcx, aOnecoreDsExtCl; "onecore\\ds\\ext\\cloudap\\dll\\applugi"...
0x18004c888  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18004c88d  lea     rdi, Class
0x18004c894  mov     r9, rax
0x18004c897  mov     [rsp+80h+lpcbMaxClassLen], rdi
0x18004c89c  lea     r12, aRegopenkeyex_0; "RegOpenKeyEx"
0x18004c8a3  mov     [rsp+80h+lpcbMaxSubKeyLen], r12
0x18004c8a8  mov     dword ptr [rsp+80h+phkResult], 119h
0x18004c8b0  mov     r8d, ebx
0x18004c8b3  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18004c8ba  xor     ecx, ecx
0x18004c8bc  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18004c8c1  jmp     loc_18004CC27
0x18004c8c6  mov     rcx, [rbp+hKey]; hKey
0x18004c8ca  lea     rax, [rbp+cbMaxSubKeyLen]
0x18004c8ce  mov     [rsp+80h+lpftLastWriteTime], r14; lpftLastWriteTime
0x18004c8d3  xor     r9d, r9d; lpReserved
0x18004c8d6  mov     [rsp+80h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x18004c8db  xor     r8d, r8d; lpcchClass
0x18004c8de  mov     [rsp+80h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x18004c8e3  xor     edx, edx; lpClass
0x18004c8e5  mov     [rsp+80h+lpcbMaxValueNameLen], r14; lpcbMaxValueNameLen
0x18004c8ea  mov     [rsp+80h+lpcValues], r14; lpcValues
0x18004c8ef  mov     [rsp+80h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x18004c8f4  mov     [rsp+80h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x18004c8f9  lea     rax, [rbp+cSubKeys]
0x18004c8fd  mov     [rsp+80h+phkResult], rax; lpcSubKeys
0x18004c902  call    cs:__imp_RegQueryInfoKeyW
0x18004c908  mov     ebx, eax
0x18004c90a  test    eax, eax
0x18004c90c  jz      short loc_18004C94D
0x18004c90e  jle     short loc_18004C919
0x18004c910  movzx   ebx, ax
0x18004c913  or      ebx, 0C0070000h
0x18004c919  lea     rcx, aOnecoreDsExtCl; "onecore\\ds\\ext\\cloudap\\dll\\applugi"...
0x18004c920  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18004c925  mov     r9, rax
0x18004c928  lea     rdi, Class
0x18004c92f  mov     [rsp+80h+lpcbMaxClassLen], rdi
0x18004c934  lea     rax, aRegqueryinfoke; "RegQueryInfoKey"
0x18004c93b  mov     [rsp+80h+lpcbMaxSubKeyLen], rax
0x18004c940  mov     dword ptr [rsp+80h+phkResult], 12Fh
0x18004c948  jmp     loc_18004C8B0
0x18004c94d  cmp     [rbp+cSubKeys], r14d
0x18004c951  jnz     short loc_18004C95A
0x18004c953  xor     ebx, ebx
0x18004c955  jmp     loc_18004CC27
0x18004c95a  mov     eax, [rbp+cbMaxSubKeyLen]
0x18004c95d  lea     ecx, [rax+1]
0x18004c960  cmp     ecx, eax
0x18004c962  jb      loc_18004CC5A
0x18004c968  mov     [rbp+cbMaxSubKeyLen], ecx
0x18004c96b  lea     rdx, [rbp+cbMaxSubKeyLen]; unsigned int *
0x18004c96f  add     rcx, rcx; unsigned __int64
0x18004c972  call    ?RtlULongLongToULong@@YAJ_KPEAK@Z; RtlULongLongToULong(unsigned __int64,ulong *)
0x18004c977  mov     ebx, eax
0x18004c979  test    eax, eax
0x18004c97b  jz      short loc_18004C9B1
0x18004c97d  lea     rcx, aOnecoreDsExtCl; "onecore\\ds\\ext\\cloudap\\dll\\applugi"...
0x18004c984  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18004c989  mov     r9, rax
0x18004c98c  lea     rdi, Class
0x18004c993  mov     [rsp+80h+lpcbMaxClassLen], rdi
0x18004c998  lea     rax, aRtldwordmult; "RtlDWordMult"
0x18004c99f  mov     [rsp+80h+lpcbMaxSubKeyLen], rax
0x18004c9a4  mov     dword ptr [rsp+80h+phkResult], 13Ch
0x18004c9ac  jmp     loc_18004C8B0
0x18004c9b1  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18004c9b8  mov     ecx, [rbp+cbMaxSubKeyLen]
0x18004c9bb  mov     rax, [rax+28h]
0x18004c9bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c9c4  mov     rbx, rax
0x18004c9c7  test    rax, rax
0x18004c9ca  jnz     short loc_18004CA05
0x18004c9cc  lea     rcx, aOnecoreDsExtCl; "onecore\\ds\\ext\\cloudap\\dll\\applugi"...
0x18004c9d3  mov     ebx, 0C0000017h
0x18004c9d8  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18004c9dd  mov     r9, rax
0x18004c9e0  lea     rdi, Class
0x18004c9e7  mov     [rsp+80h+lpcbMaxClassLen], rdi
0x18004c9ec  lea     rax, aAllocatelsahea_3; "AllocateLsaHeap"
0x18004c9f3  mov     [rsp+80h+lpcbMaxSubKeyLen], rax
0x18004c9f8  mov     dword ptr [rsp+80h+phkResult], 142h
0x18004ca00  jmp     loc_18004C8B0
0x18004ca05  xor     r15d, r15d
0x18004ca08  cmp     [rbp+cSubKeys], r14d
0x18004ca0c  jbe     loc_18004CBFA
0x18004ca12  lea     rdi, Class
0x18004ca19  lea     r12, aRegopenkeyex_0; "RegOpenKeyEx"
0x18004ca20  mov     eax, [rbp+cbMaxSubKeyLen]
0x18004ca23  lea     r9, [rbp+cchName]; lpcchName
0x18004ca27  mov     rcx, [rbp+hKey]; hKey
0x18004ca2b  mov     r8, rbx; lpName
0x18004ca2e  shr     eax, 1
0x18004ca30  mov     edx, r15d; dwIndex
0x18004ca33  mov     [rbp+cchName], eax
0x18004ca36  xor     eax, eax
0x18004ca38  mov     [rsp+80h+lpcValues], rax; lpftLastWriteTime
0x18004ca3d  mov     [rsp+80h+lpcbMaxClassLen], rax; lpcchClass
0x18004ca42  mov     [rsp+80h+lpcbMaxSubKeyLen], rax; lpClass
0x18004ca47  mov     [rsp+80h+phkResult], rax; lpReserved
0x18004ca4c  call    cs:__imp_RegEnumKeyExW
0x18004ca52  mov     r8d, eax
0x18004ca55  test    eax, eax
0x18004ca57  jz      short loc_18004CA93
0x18004ca59  jle     short loc_18004CA66
0x18004ca5b  movzx   r8d, ax
0x18004ca5f  or      r8d, 0C0070000h
0x18004ca66  lea     rcx, aOnecoreDsExtCl; "onecore\\ds\\ext\\cloudap\\dll\\applugi"...
0x18004ca6d  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18004ca72  mov     [rsp+80h+lpcbMaxClassLen], rdi
0x18004ca77  mov     r9, rax
0x18004ca7a  lea     rax, aRegenumkeyex; "RegEnumKeyEx"
0x18004ca81  mov     [rsp+80h+lpcbMaxSubKeyLen], rax
0x18004ca86  mov     dword ptr [rsp+80h+phkResult], 157h
0x18004ca8e  jmp     loc_18004CBDF
0x18004ca93  mov     ecx, [rbp+cchName]
0x18004ca96  xor     eax, eax
0x18004ca98  mov     [rbx+rcx*2], ax
0x18004ca9c  mov     rcx, [rbp+hkey]; hKey
0x18004caa0  test    rcx, rcx
0x18004caa3  jz      short loc_18004CAB3
0x18004caa5  call    cs:__imp_RegCloseKey
0x18004caab  mov     [rbp+hkey], 0
0x18004cab3  mov     rcx, [rbp+hKey]; hKey
0x18004cab7  lea     rax, [rbp+hkey]
0x18004cabb  mov     r9d, 20019h; samDesired
0x18004cac1  mov     [rsp+80h+phkResult], rax; phkResult
0x18004cac6  xor     r8d, r8d; ulOptions
0x18004cac9  mov     rdx, rbx; lpSubKey
0x18004cacc  call    cs:__imp_RegOpenKeyExW
0x18004cad2  mov     r8d, eax
0x18004cad5  test    eax, eax
0x18004cad7  jz      short loc_18004CB0C
0x18004cad9  jle     short loc_18004CAE6
0x18004cadb  movzx   r8d, ax
0x18004cadf  or      r8d, 0C0070000h
0x18004cae6  lea     rcx, aOnecoreDsExtCl; "onecore\\ds\\ext\\cloudap\\dll\\applugi"...
0x18004caed  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18004caf2  mov     [rsp+80h+lpcbMaxClassLen], rbx
0x18004caf7  mov     r9, rax
0x18004cafa  mov     [rsp+80h+lpcbMaxSubKeyLen], r12
0x18004caff  mov     dword ptr [rsp+80h+phkResult], 16Ch
0x18004cb07  jmp     loc_18004CBDF
0x18004cb0c  test    r14, r14
0x18004cb0f  jz      short loc_18004CB2C
0x18004cb11  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18004cb18  mov     rcx, r14
0x18004cb1b  mov     rax, [rax+30h]
0x18004cb1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cb24  mov     [rbp+var_10], 0
0x18004cb2c  mov     rcx, [rbp+hkey]; hkey
0x18004cb30  lea     rax, [rbp+var_10]
0x18004cb34  lea     r9, [rbp+arg_18]; unsigned int *
0x18004cb38  mov     [rsp+80h+phkResult], rax; void **
0x18004cb3d  mov     r8d, 6; dwFlags
0x18004cb43  mov     [rbp+arg_18], 0
0x18004cb4a  lea     rdx, aAuthenticating_0; "AuthenticatingAuthorityDns"
0x18004cb51  call    ?GetRegVal@@YAJPEAUHKEY__@@PEBGKPEAKPEAPEAX@Z; GetRegVal(HKEY__ *,ushort const *,ulong,ulong *,void * *)
0x18004cb56  mov     r8d, eax
0x18004cb59  test    eax, eax
0x18004cb5b  jns     short loc_18004CB99
0x18004cb5d  lea     rcx, aOnecoreDsExtCl; "onecore\\ds\\ext\\cloudap\\dll\\applugi"...
0x18004cb64  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18004cb69  mov     r9, rax
0x18004cb6c  mov     [rsp+80h+lpcbMaxClassLen], rbx
0x18004cb71  lea     rax, aGetstringregva_3; "GetStringRegVal"
0x18004cb78  xor     ecx, ecx
0x18004cb7a  mov     [rsp+80h+lpcbMaxSubKeyLen], rax
0x18004cb7f  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18004cb86  mov     dword ptr [rsp+80h+phkResult], 17Ch
0x18004cb8e  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18004cb93  mov     r14, [rbp+var_10]
0x18004cb97  jmp     short loc_18004CBED
0x18004cb99  mov     r14, [rbp+var_10]
0x18004cb9d  mov     r8, rbx; unsigned __int16 *
0x18004cba0  mov     r9, r14; unsigned __int16 *
0x18004cba3  mov     rdx, r13; struct _ApPluginPkg *
0x18004cba6  mov     ecx, 1; int
0x18004cbab  call    ?RegisterSubPackage@@YAJHPEAU_ApPluginPkg@@PEBG1@Z; RegisterSubPackage(int,_ApPluginPkg *,ushort const *,ushort const *)
0x18004cbb0  mov     r8d, eax
0x18004cbb3  test    eax, eax
0x18004cbb5  jz      short loc_18004CBED
0x18004cbb7  lea     rcx, aOnecoreDsExtCl; "onecore\\ds\\ext\\cloudap\\dll\\applugi"...
0x18004cbbe  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18004cbc3  mov     [rsp+80h+lpcbMaxClassLen], rbx
0x18004cbc8  mov     r9, rax
0x18004cbcb  lea     rax, aRegistersubpac; "RegisterSubPackage"
0x18004cbd2  mov     [rsp+80h+lpcbMaxSubKeyLen], rax
0x18004cbd7  mov     dword ptr [rsp+80h+phkResult], 185h
0x18004cbdf  lea     rdx, a0x08xSUSWs; "0x%08x %s:%u : %s:%ws"
0x18004cbe6  xor     ecx, ecx
0x18004cbe8  call    ?WPPTraceLogA@@YAXW4_CLOUDAP_WPP_FLAG@@PEBDZZ; WPPTraceLogA(_CLOUDAP_WPP_FLAG,char const *,...)
0x18004cbed  inc     r15d
0x18004cbf0  cmp     r15d, [rbp+cSubKeys]
0x18004cbf4  jb      loc_18004CA20
0x18004cbfa  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18004cc01  mov     rcx, rbx
0x18004cc04  mov     rax, [rax+30h]
0x18004cc08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cc0d  xor     ebx, ebx
0x18004cc0f  test    r14, r14
0x18004cc12  jz      short loc_18004CC27
0x18004cc14  mov     rax, cs:?g_pLsaFunctionTable@@3PEAU_LSA_SECPKG_FUNCTION_TABLE@@EA; _LSA_SECPKG_FUNCTION_TABLE * g_pLsaFunctionTable
0x18004cc1b  mov     rcx, r14
0x18004cc1e  mov     rax, [rax+30h]
0x18004cc22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cc27  mov     rcx, [rbp+hKey]; hKey
0x18004cc2b  test    rcx, rcx
0x18004cc2e  jz      short loc_18004CC36
0x18004cc30  call    cs:__imp_RegCloseKey
0x18004cc36  mov     rcx, [rbp+hkey]; hKey
0x18004cc3a  test    rcx, rcx
0x18004cc3d  jz      short loc_18004CC45
0x18004cc3f  call    cs:__imp_RegCloseKey
0x18004cc45  mov     eax, ebx
0x18004cc47  add     rsp, 80h
0x18004cc4e  pop     r15
0x18004cc50  pop     r14
0x18004cc52  pop     r13
0x18004cc54  pop     r12
0x18004cc56  pop     rdi
0x18004cc57  pop     rbx
0x18004cc58  pop     rbp
0x18004cc59  retn
0x18004cc5a  lea     rcx, aOnecoreDsExtCl; "onecore\\ds\\ext\\cloudap\\dll\\applugi"...
0x18004cc61  mov     [rbp+cbMaxSubKeyLen], 0FFFFFFFFh
0x18004cc68  mov     ebx, 0C0000095h
0x18004cc6d  call    ?_DBG_BASENAME@@YAPEBDPEBD@Z; _DBG_BASENAME(char const *)
0x18004cc72  mov     r9, rax
0x18004cc75  lea     rdi, Class
0x18004cc7c  mov     [rsp+80h+lpcbMaxClassLen], rdi
0x18004cc81  lea     rax, aRtldwordadd; "RtlDWordAdd"
0x18004cc88  mov     [rsp+80h+lpcbMaxSubKeyLen], rax
0x18004cc8d  mov     dword ptr [rsp+80h+phkResult], 139h
0x18004cc95  jmp     loc_18004C8B0
```
