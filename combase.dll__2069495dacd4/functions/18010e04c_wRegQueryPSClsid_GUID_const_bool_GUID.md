# wRegQueryPSClsid(_GUID const &,bool,_GUID *)

- ea: `0x18010e04c`
- end: `0x18010e3d0`
- name: `?wRegQueryPSClsid@@YAJAEBU_GUID@@_NPEAU1@@Z`
- size: `900`
- prototype: `HRESULT __fastcall(const _GUID *riid, bool suppressErrorOrigination, _GUID *lpclsid)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800cb3a0`

## callees

- `0x18003d1b0`
- `0x18003d494`
- `0x180040078`
- `0x1800421e0`
- `0x18004768c`
- `0x18004c4d8`
- `0x180086714`
- `0x18008db2c`
- `0x18010e04c`
- `0x1801999b0`
- `0x1801a8564`
- `0x1802135dd`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18010e116`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18010e24d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18010e116`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18010e24d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18010e2ec`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18010e330`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18010e2ec`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18010e330`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18010e0e8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18010e21b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18010e0e8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18010e21b`

## string_xrefs

- `0x18010e1e9`: `onecore\com\combase\class\compapi.cxx`
- `0x18010e159`: `ProxyStubClsid32 Default`
- `0x18010e1d5`: `wRegQueryPSClsid`
- `0x18010e214`: `ProxyStubClsid`
- `0x18010e30f`: `ProxyStubClsid`
- `0x18010e1dc`: `IID:%ws, Value:ProxyStubClsid32`
- `0x18010e37d`: `Failure opening ProxyStubClsid32 key with error %x for Interface key with IID:%ws`
- `0x18010e2cb`: `ProxyStubClsid Default`

## pseudocode

```c
__int64 __fastcall wRegQueryPSClsid(const _GUID *riid, bool suppressErrorOrigination, _GUID *lpclsid)
{
  HRESULT v6; // edi
  LSTATUS v7; // eax
  HRESULT v8; // ebx
  const char *v9; // rdx
  const char *v10; // rcx
  HRESULT level; // r8d
  TraceLevel v12; // r9d
  int v13; // edx
  TraceLevel v14; // ecx
  __int64 v15; // rax
  const char *v16; // rdx
  const char *v17; // rcx
  TraceLevel v18; // r9d
  const char *v19; // rdx
  const char *v20; // rcx
  TraceLevel v21; // r9d
  wchar_t *v22; // r8
  unsigned int v23; // edx
  const wchar_t *phkResult; // [rsp+20h] [rbp-E0h]
  const wchar_t *phkResulta; // [rsp+20h] [rbp-E0h]
  const wchar_t *phkResultb; // [rsp+20h] [rbp-E0h]
  HKEY__ *hIf; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int cbValue; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int dwType; // [rsp+4Ch] [rbp-B4h] BYREF
  HKEY__ *hkInterface; // [rsp+50h] [rbp-B0h] BYREF
  _GUID clsid; // [rsp+58h] [rbp-A8h] BYREF
  CGuidStr iidString; // [rsp+70h] [rbp-90h] BYREF
  wchar_t szValue[40]; // [rsp+C0h] [rbp-40h] BYREF
  wchar_t message[264]; // [rsp+110h] [rbp+10h] BYREF

  cbValue = 78;
  hkInterface = 0;
  *lpclsid = GUID_NULL;
  hIf = 0;
  dwType = 0;
  v6 = wRegOpenInterfaceKey(riid, &hkInterface);
  if ( v6 < 0 )
    return (unsigned int)v6;
  v6 = -2147221163;
  v7 = RegOpenKeyExW(hkInterface, Com::Catalog::Constants::ProxyStubClsid32, 0, 0x20019u, &hIf);
  v8 = v7;
  if ( !v7 )
  {
    if ( RegQueryValueExW(hIf, 0, 0, &dwType, (LPBYTE)szValue, &cbValue) )
    {
      if ( gfEnableTracing != v8 && IsWppLevelEnabled(VERBOSE) )
        ComTraceMessageT<_GUID const *,unsigned short const *,long>(
          v10,
          v9,
          840,
          v12,
          phkResult,
          riid,
          L"ProxyStubClsid32 Default",
          level);
    }
    else
    {
      v6 = wCLSIDFromString(szValue, lpclsid);
    }
    goto LABEL_30;
  }
  if ( v7 > 0 )
    v8 = (unsigned __int16)v7 | 0x80070000;
  v13 = gfEnableTracing;
  if ( v8 == -2147024894 )
  {
    if ( !gfEnableTracing )
      goto LABEL_20;
    if ( IsWppLevelEnabled(VERBOSE) )
      goto LABEL_19;
  }
  if ( v8 < 0 )
  {
    if ( v8 == -2147024894 )
      goto LABEL_20;
    if ( !Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1 )
    {
      if ( !gfEnableTracing )
        goto LABEL_20;
      v14 = ERRORS;
      goto LABEL_18;
    }
LABEL_19:
    CGuidStr::CGuidStr(&iidString, riid);
    ComTraceHr(
      v8,
      "onecore\\com\\combase\\class\\compapi.cxx",
      "wRegQueryPSClsid",
      852,
      L"IID:%ws, Value:ProxyStubClsid32",
      v15);
    goto LABEL_20;
  }
  if ( !v13 )
    goto LABEL_20;
  v14 = VERBOSE;
LABEL_18:
  if ( IsWppLevelEnabled(v14) )
    goto LABEL_19;
LABEL_20:
  if ( RegOpenKeyExW(hkInterface, L"ProxyStubClsid", 0, 0x20019u, &hIf) )
  {
    if ( gfEnableTracing && IsWppLevelEnabled(VERBOSE) )
      ComTraceMessageT<_GUID const *,unsigned short const *,long>(
        v20,
        v19,
        894,
        v21,
        phkResulta,
        riid,
        L"ProxyStubClsid",
        (HRESULT)v19);
    goto LABEL_34;
  }
  if ( RegQueryValueExW(hIf, 0, 0, &dwType, (LPBYTE)szValue, &cbValue) )
  {
    if ( gfEnableTracing && IsWppLevelEnabled(VERBOSE) )
      ComTraceMessageT<_GUID const *,unsigned short const *,long>(
        v17,
        v16,
        887,
        v18,
        phkResultb,
        riid,
        L"ProxyStubClsid Default",
        (HRESULT)v16);
  }
  else
  {
    clsid = 0;
    if ( wCLSIDFromString(szValue, &clsid) >= 0 && !memcmp_0(&CLSID_PSDispatch, &clsid, 0x10u) )
    {
      v6 = 0;
      *lpclsid = CLSID_PSDispatch;
    }
  }
LABEL_30:
  RegCloseKey(hIf);
LABEL_34:
  RegCloseKey(hkInterface);
  if ( v6 < 0 && (int)(v8 + 0x80000000) >= 0 && v8 != -2147024882 && !suppressErrorOrigination )
  {
    if ( v8 == -2147024894 )
    {
      v22 = 0;
      v23 = 0;
    }
    else
    {
      StringFromGUID2(riid, iidString._wszGuid, 39);
      StringCchPrintfW(
        message,
        0x104u,
        L"Failure opening ProxyStubClsid32 key with error %x for Interface key with IID:%ws",
        (unsigned int)v8,
        &iidString);
      v22 = message;
      v23 = 259;
    }
    RoOriginateErrorW(v6, v23, v22);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18010e04c  mov     [rsp-8+arg_8], rbx
0x18010e051  push    rbp
0x18010e052  push    rdi
0x18010e053  push    r12
0x18010e055  push    r14
0x18010e057  push    r15
0x18010e059  lea     rbp, [rsp-230h]
0x18010e061  sub     rsp, 330h
0x18010e068  mov     rax, cs:__security_cookie
0x18010e06f  xor     rax, rsp
0x18010e072  mov     [rbp+250h+var_30], rax
0x18010e079  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18010e080  mov     r12b, suppressErrorOrigination
0x18010e083  mov     [rsp+350h+cbValue], 4Eh ; 'N'
0x18010e08b  lea     rdx, [rsp+350h+hkInterface]; lphkeyIID
0x18010e090  mov     [rsp+350h+hkInterface], 0
0x18010e099  movdqu  xmmword ptr [lpclsid], xmm0
0x18010e09e  mov     r15, lpclsid
0x18010e0a1  mov     [rsp+350h+hIf], 0
0x18010e0aa  mov     r14, riid
0x18010e0ad  mov     [rsp+350h+dwType], 0
0x18010e0b5  call    ?wRegOpenInterfaceKey@@YAJAEBU_GUID@@PEAPEAUHKEY__@@@Z; wRegOpenInterfaceKey(_GUID const &,HKEY__ * *)
0x18010e0ba  mov     edi, eax
0x18010e0bc  test    eax, eax
0x18010e0be  js      loc_18010E3A7
0x18010e0c4  mov     riid, [rsp+350h+hkInterface]; hKey
0x18010e0c9  lea     rax, [rsp+350h+hIf]
0x18010e0ce  mov     r9d, 20019h; samDesired
0x18010e0d4  mov     [rsp+350h+phkResult], rax; phkResult
0x18010e0d9  xor     r8d, r8d; ulOptions
0x18010e0dc  lea     rdx, ?ProxyStubClsid32@Constants@Catalog@Com@@3QBGB; lpSubKey
0x18010e0e3  mov     edi, 80040155h
0x18010e0e8  call    cs:__imp_RegOpenKeyExW
0x18010e0ee  mov     ebx, eax
0x18010e0f0  test    eax, eax
0x18010e0f2  jnz     short loc_18010E16B
0x18010e0f4  mov     riid, [rsp+350h+hIf]; hKey
0x18010e0f9  lea     rax, [rsp+350h+cbValue]
0x18010e0fe  mov     [rsp+350h+lpcbData], rax; lpcbData
0x18010e103  lea     r9, [rsp+350h+dwType]; lpType
0x18010e108  lea     rax, [rbp+250h+szValue]
0x18010e10c  xor     r8d, r8d; lpReserved
0x18010e10f  xor     edx, edx; lpValueName
0x18010e111  mov     [rsp+350h+phkResult], rax; lpData
0x18010e116  call    cs:__imp_RegQueryValueExW
0x18010e11c  mov     r8d, eax
0x18010e11f  test    eax, eax
0x18010e121  jnz     short loc_18010E136
0x18010e123  mov     rdx, r15; lpclsid
0x18010e126  lea     riid, [rbp+250h+szValue]; lpsz
0x18010e12a  call    ?wCLSIDFromString@@YAJPEBGPEAU_GUID@@@Z; wCLSIDFromString(ushort const *,_GUID *)
0x18010e12f  mov     edi, eax
0x18010e131  jmp     loc_18010E2E7
0x18010e136  cmp     cs:?gfEnableTracing@@3HA, ebx; int gfEnableTracing
0x18010e13c  jz      loc_18010E2E7
0x18010e142  mov     ecx, 3; level
0x18010e147  call    IsWppLevelEnabled
0x18010e14c  test    al, al
0x18010e14e  jz      loc_18010E2E7
0x18010e154  mov     [rsp+350h+level], r8d
0x18010e159  lea     rax, aProxystubclsid_4; "ProxyStubClsid32 Default"
0x18010e160  mov     r8d, 348h
0x18010e166  jmp     loc_18010E2D8
0x18010e16b  jle     short loc_18010E176
0x18010e16d  movzx   ebx, ax
0x18010e170  or      ebx, 80070000h
0x18010e176  mov     edx, cs:?gfEnableTracing@@3HA; int gfEnableTracing
0x18010e17c  cmp     ebx, 80070002h
0x18010e182  jnz     short loc_18010E196
0x18010e184  test    edx, edx
0x18010e186  jz      short loc_18010E1FC
0x18010e188  mov     ecx, 3; level
0x18010e18d  call    IsWppLevelEnabled
0x18010e192  test    al, al
0x18010e194  jnz     short loc_18010E1C3
0x18010e196  test    ebx, ebx
0x18010e198  jns     loc_18010E29E
0x18010e19e  cmp     ebx, 80070002h
0x18010e1a4  jz      short loc_18010E1FC
0x18010e1a6  mov     eax, cs:_Tlgg_hCombaseTraceLoggingProviderProv.LevelPlus1
0x18010e1ac  test    eax, eax
0x18010e1ae  jnz     short loc_18010E1C3
0x18010e1b0  cmp     cs:?gfEnableTracing@@3HA, eax; int gfEnableTracing
0x18010e1b6  jz      short loc_18010E1FC
0x18010e1b8  xor     ecx, ecx; level
0x18010e1ba  call    IsWppLevelEnabled
0x18010e1bf  test    al, al
0x18010e1c1  jz      short loc_18010E1FC
0x18010e1c3  mov     rdx, r14; rguid
0x18010e1c6  lea     riid, [rsp+350h+iidString]; this
0x18010e1cb  call    ??0CGuidStr@@QEAA@AEBU_GUID@@@Z; CGuidStr::CGuidStr(_GUID const &)
0x18010e1d0  mov     [rsp+350h+lpcbData], rax
0x18010e1d5  lea     lpclsid, aWregquerypscls; "wRegQueryPSClsid"
0x18010e1dc  lea     rax, aIidWsValueProx; "IID:%ws, Value:ProxyStubClsid32"
0x18010e1e3  mov     r9d, 354h; line
0x18010e1e9  lea     rdx, aOnecoreComComb_97; "onecore\\com\\combase\\class\\compapi.c"...
0x18010e1f0  mov     [rsp+350h+phkResult], rax; format
0x18010e1f5  mov     ecx, ebx; hr
0x18010e1f7  call    ?ComTraceHr@@YAXJPEBD0HPEBGZZ; ComTraceHr(long,char const *,char const *,int,ushort const *,...)
0x18010e1fc  mov     riid, [rsp+350h+hkInterface]; hKey
0x18010e201  lea     rax, [rsp+350h+hIf]
0x18010e206  mov     r9d, 20019h; samDesired
0x18010e20c  mov     [rsp+350h+phkResult], rax; file
0x18010e211  xor     r8d, r8d; ulOptions
0x18010e214  lea     rdx, aProxystubclsid_2; "ProxyStubClsid"
0x18010e21b  call    cs:__imp_RegOpenKeyExW
0x18010e221  mov     edx, eax
0x18010e223  test    eax, eax
0x18010e225  jnz     loc_18010E2F4
0x18010e22b  mov     riid, [rsp+350h+hIf]; hKey
0x18010e230  lea     rax, [rsp+350h+cbValue]
0x18010e235  mov     [rsp+350h+lpcbData], rax; lpcbData
0x18010e23a  lea     r9, [rsp+350h+dwType]; lpType
0x18010e23f  lea     rax, [rbp+250h+szValue]
0x18010e243  xor     r8d, r8d; lpReserved
0x18010e246  xor     edx, edx; lpValueName
0x18010e248  mov     [rsp+350h+phkResult], rax; file
0x18010e24d  call    cs:__imp_RegQueryValueExW
0x18010e253  mov     edx, eax
0x18010e255  test    eax, eax
0x18010e257  jnz     short loc_18010E2B0
0x18010e259  xorps   xmm0, xmm0
0x18010e25c  lea     rdx, [rsp+350h+clsid]; lpclsid
0x18010e261  lea     riid, [rbp+250h+szValue]; lpsz
0x18010e265  movups  xmmword ptr [rsp+350h+clsid.Data1], xmm0
0x18010e26a  call    ?wCLSIDFromString@@YAJPEBGPEAU_GUID@@@Z; wCLSIDFromString(ushort const *,_GUID *)
0x18010e26f  test    eax, eax
0x18010e271  js      short loc_18010E2E7
0x18010e273  mov     r8d, 10h; Size
0x18010e279  lea     rdx, [rsp+350h+clsid]; Buf2
0x18010e27e  lea     riid, CLSID_PSDispatch; Buf1
0x18010e285  call    memcmp_0
0x18010e28a  test    eax, eax
0x18010e28c  jnz     short loc_18010E2E7
0x18010e28e  movups  xmm0, xmmword ptr cs:CLSID_PSDispatch.Data1
0x18010e295  xor     edi, edi
0x18010e297  movdqu  xmmword ptr [r15], xmm0
0x18010e29c  jmp     short loc_18010E2E7
0x18010e29e  test    edx, edx
0x18010e2a0  jz      loc_18010E1FC
0x18010e2a6  mov     ecx, 3
0x18010e2ab  jmp     loc_18010E1BA
0x18010e2b0  cmp     cs:?gfEnableTracing@@3HA, 0; int gfEnableTracing
0x18010e2b7  jz      short loc_18010E2E7
0x18010e2b9  mov     ecx, 3; level
0x18010e2be  call    IsWppLevelEnabled
0x18010e2c3  test    al, al
0x18010e2c5  jz      short loc_18010E2E7
0x18010e2c7  mov     [rsp+350h+level], edx; level
0x18010e2cb  lea     rax, aProxystubclsid_3; "ProxyStubClsid Default"
0x18010e2d2  mov     r8d, 377h; <args_1>
0x18010e2d8  mov     [rsp+350h+line], rax; line
0x18010e2dd  mov     [rsp+350h+lpcbData], r14; function
0x18010e2e2  call    ??$ComTraceMessageT@PEBU_GUID@@PEBGJ@@YAXPEBD0HW4TraceLevel@@PEBGPEBU_GUID@@2J@Z; ComTraceMessageT<_GUID const *,ushort const *,long>(char const *,char const *,int,TraceLevel,ushort const *,_GUID const *,ushort const *,long)
0x18010e2e7  mov     riid, [rsp+350h+hIf]; hKey
0x18010e2ec  call    cs:__imp_RegCloseKey
0x18010e2f2  jmp     short loc_18010E32B
0x18010e2f4  cmp     cs:?gfEnableTracing@@3HA, 0; int gfEnableTracing
0x18010e2fb  jz      short loc_18010E32B
0x18010e2fd  mov     ecx, 3; level
0x18010e302  call    IsWppLevelEnabled
0x18010e307  test    al, al
0x18010e309  jz      short loc_18010E32B
0x18010e30b  mov     [rsp+350h+level], edx; level
0x18010e30f  lea     rax, aProxystubclsid_2; "ProxyStubClsid"
0x18010e316  mov     [rsp+350h+line], rax; line
0x18010e31b  mov     r8d, 37Eh; <args_1>
0x18010e321  mov     [rsp+350h+lpcbData], r14; function
0x18010e326  call    ??$ComTraceMessageT@PEBU_GUID@@PEBGJ@@YAXPEBD0HW4TraceLevel@@PEBGPEBU_GUID@@2J@Z; ComTraceMessageT<_GUID const *,ushort const *,long>(char const *,char const *,int,TraceLevel,ushort const *,_GUID const *,ushort const *,long)
0x18010e32b  mov     riid, [rsp+350h+hkInterface]; hKey
0x18010e330  call    cs:__imp_RegCloseKey
0x18010e336  test    edi, edi
0x18010e338  jns     short loc_18010E3A7
0x18010e33a  mov     ecx, 80000000h
0x18010e33f  lea     eax, [rbx+riid]
0x18010e342  test    ecx, eax
0x18010e344  jnz     short loc_18010E3A7
0x18010e346  cmp     ebx, 8007000Eh
0x18010e34c  jz      short loc_18010E3A7
0x18010e34e  test    r12b, r12b
0x18010e351  jnz     short loc_18010E3A7
0x18010e353  cmp     ebx, 80070002h
0x18010e359  jnz     short loc_18010E362
0x18010e35b  xor     r8d, r8d
0x18010e35e  xor     edx, edx
0x18010e360  jmp     short loc_18010E3A0
0x18010e362  mov     r8d, 27h ; '''; cchMax
0x18010e368  lea     rdx, [rsp+350h+iidString]; lpsz
0x18010e36d  mov     riid, r14; rguid
0x18010e370  call    StringFromGUID2
0x18010e375  lea     rax, [rsp+350h+iidString]
0x18010e37a  mov     r9d, ebx
0x18010e37d  lea     lpclsid, aFailureOpening; "Failure opening ProxyStubClsid32 key wi"...
0x18010e384  mov     [rsp+350h+phkResult], rax
0x18010e389  mov     edx, 104h; cchDest
0x18010e38e  lea     riid, [rbp+250h+message]; pszDest
0x18010e392  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18010e397  lea     lpclsid, [rbp+250h+message]; message
0x18010e39b  mov     edx, 103h; cchMax
0x18010e3a0  mov     ecx, edi; error
0x18010e3a2  call    RoOriginateErrorW
0x18010e3a7  mov     eax, edi
0x18010e3a9  mov     riid, [rbp+250h+var_30]
0x18010e3b0  xor     riid, rsp; StackCookie
0x18010e3b3  call    __security_check_cookie
0x18010e3b8  mov     rbx, [rsp+350h+arg_8]
0x18010e3c0  add     rsp, 330h
0x18010e3c7  pop     r15
0x18010e3c9  pop     r14
0x18010e3cb  pop     r12
0x18010e3cd  pop     rdi
0x18010e3ce  pop     rbp
0x18010e3cf  retn
```
