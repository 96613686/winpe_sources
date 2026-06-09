# InitSessionKey(ISimpleTableRead2 *,IIS_CRYPTO_STORAGE * *,char *,int)

- ea: `0x18001f2c8`
- end: `0x18001f540`
- name: `?InitSessionKey@@YAJPEAUISimpleTableRead2@@PEAPEAVIIS_CRYPTO_STORAGE@@PEADH@Z`
- size: `632`
- prototype: `__int64 __fastcall(struct ISimpleTableRead2 *, struct IIS_CRYPTO_STORAGE **, char *, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180012ec0`
- `0x180020014`

## callees

- `0x18001ea74`
- `0x18001f2c8`
- `0x18001f720`
- `0x18001f8e4`

## import_xrefs

- `ADVAPI32!RegSetValueExA` at `0x18001f3d2`
- `ADVAPI32!RegSetValueExA` at `0x18001f3d2`
- `ADVAPI32!RegQueryValueExA` at `0x18001f34e`
- `ADVAPI32!RegQueryValueExA` at `0x18001f34e`
- `ADVAPI32!RegOpenKeyA` at `0x18001f319`
- `ADVAPI32!RegOpenKeyA` at `0x18001f319`
- `ADVAPI32!RegCloseKey` at `0x18001f416`
- `ADVAPI32!RegCloseKey` at `0x18001f416`
- `IisRTL!PuDbgPrint` at `0x18001f3a7`
- `IisRTL!PuDbgPrint` at `0x18001f40c`
- `IisRTL!PuDbgPrint` at `0x18001f3a7`
- `IisRTL!PuDbgPrint` at `0x18001f40c`
- `IisRTL!PuDbgPrintW` at `0x18001f491`
- `IisRTL!PuDbgPrintW` at `0x18001f529`
- `IisRTL!PuDbgPrintW` at `0x18001f491`
- `IisRTL!PuDbgPrintW` at `0x18001f529`

## string_xrefs

- `0x18001f347`: `MetabaseUnSecuredRead`
- `0x18001f3b9`: `MetabaseUnSecuredRead`
- `0x18001f387`: `Temporary disabling  decryption for metabase read\n`

## pseudocode

```c
__int64 __fastcall InitSessionKey(struct ISimpleTableRead2 *a1, struct IIS_CRYPTO_STORAGE **a2, char *a3, int a4)
{
  int v7; // esi
  unsigned int v9; // ebx
  int Value; // eax
  int inited; // eax
  LPDWORD lpcbData; // [rsp+28h] [rbp-28h]
  BYTE Data[4]; // [rsp+30h] [rbp-20h] BYREF
  unsigned int v15; // [rsp+34h] [rbp-1Ch] BYREF
  DWORD cbData; // [rsp+38h] [rbp-18h] BYREF
  DWORD Type; // [rsp+3Ch] [rbp-14h] BYREF
  HKEY phkResult; // [rsp+40h] [rbp-10h] BYREF
  unsigned __int8 *v19; // [rsp+48h] [rbp-8h] BYREF

  phkResult = 0;
  *(_DWORD *)Data = 0;
  Type = 0;
  v7 = 1;
  cbData = 4;
  if ( !RegOpenKeyA(HKEY_LOCAL_MACHINE, "SOFTWARE\\Microsoft\\InetStp", &phkResult) )
  {
    cbData = 4;
    if ( !RegQueryValueExA(phkResult, "MetabaseUnSecuredRead", 0, &Type, Data, &cbData)
      && Type == 4
      && *(_DWORD *)Data == 1 )
    {
      v7 = 0;
      *a2 = 0;
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
          9732,
          "InitSessionKey",
          "Temporary disabling  decryption for metabase read\n");
      *(_DWORD *)Data = 2;
      if ( !RegSetValueExA(phkResult, "MetabaseUnSecuredRead", 0, 4u, Data, 4u) && (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
          9745,
          "InitSessionKey",
          "Reanabling decryption after W9z upgrade\n");
    }
    RegCloseKey(phkResult);
  }
  v9 = 0;
  if ( !v7 )
    return v9;
  v15 = 0;
  v19 = 0;
  Value = GetValue(a1, L".", 0x34u, L"SessionKey", &v15, (void **)&v19);
  if ( Value >= 0 )
  {
    if ( *(_DWORD *)v19 == 1648583497 )
    {
      dword_180048964 = 0;
      fCryptoSettingsDoOverrride = 1;
      fCryptoSettingsOverrideFlag = 0;
    }
    if ( a3 )
      inited = InitStorageHelper2(a3, v19, v15, a2, a4);
    else
      inited = InitStorageHelper(v19, v15, a2);
    v9 = inited;
    if ( inited < 0 && (g_dwDebugFlags & 3) != 0 )
    {
      LODWORD(lpcbData) = inited;
      PuDbgPrintW(
        g_pDebug,
        "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
        9796,
        "InitSessionKey",
        L"[InitSessionKey] InitStorageHelper? failed with hr = 0x%x.\n",
        lpcbData);
    }
    return v9;
  }
  if ( (g_dwDebugFlags & 3) != 0 )
  {
    LODWORD(lpcbData) = Value;
    PuDbgPrintW(
      g_pDebug,
      "inetsrv\\iis\\mb\\metadata\\metasub.cxx",
      9766,
      "InitSessionKey",
      L"[InitSessionKey] Error: Session key could not be fetched. GetGlobalValue failed with hr = 0x%x.\n",
      lpcbData);
  }
  return 2148321309LL;
}

```

## disassembly

```asm
0x18001f2c8  push    rbp
0x18001f2ca  push    rbx
0x18001f2cb  push    rsi
0x18001f2cc  push    rdi
0x18001f2cd  push    r12
0x18001f2cf  push    r14
0x18001f2d1  push    r15
0x18001f2d3  mov     rbp, rsp
0x18001f2d6  sub     rsp, 50h
0x18001f2da  mov     r14, r8
0x18001f2dd  mov     [rbp+phkResult], 0
0x18001f2e5  mov     rdi, rdx
0x18001f2e8  mov     dword ptr [rbp+Data], 0
0x18001f2ef  mov     r15, rcx
0x18001f2f2  mov     [rbp+Type], 0
0x18001f2f9  mov     esi, 1
0x18001f2fe  lea     r8, [rbp+phkResult]; phkResult
0x18001f302  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\InetStp"
0x18001f309  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001f310  mov     r12d, r9d
0x18001f313  lea     ebx, [rsi+3]
0x18001f316  mov     [rbp+cbData], ebx
0x18001f319  call    cs:__imp_RegOpenKeyA
0x18001f31f  test    eax, eax
0x18001f321  jnz     loc_18001F41C
0x18001f327  mov     rcx, [rbp+phkResult]; hKey
0x18001f32b  lea     rax, [rbp+cbData]
0x18001f32f  mov     [rsp+50h+lpcbData], rax; lpcbData
0x18001f334  lea     r9, [rbp+Type]; lpType
0x18001f338  lea     rax, [rbp+Data]
0x18001f33c  mov     [rbp+cbData], ebx
0x18001f33f  xor     r8d, r8d; lpReserved
0x18001f342  mov     [rsp+50h+lpData], rax; lpData
0x18001f347  lea     rdx, aMetabaseunsecu; "MetabaseUnSecuredRead"
0x18001f34e  call    cs:__imp_RegQueryValueExA
0x18001f354  test    eax, eax
0x18001f356  jnz     loc_18001F412
0x18001f35c  cmp     [rbp+Type], ebx
0x18001f35f  jnz     loc_18001F412
0x18001f365  cmp     dword ptr [rbp+Data], esi
0x18001f368  jnz     loc_18001F412
0x18001f36e  xor     esi, esi
0x18001f370  mov     qword ptr [rdi], 0
0x18001f377  test    byte ptr cs:g_dwDebugFlags, 3
0x18001f37e  jz      short loc_18001F3AD
0x18001f380  mov     rcx, cs:g_pDebug
0x18001f387  lea     rax, aTemporaryDisab; "Temporary disabling  decryption for met"...
0x18001f38e  lea     r9, aInitsessionkey; "InitSessionKey"
0x18001f395  mov     [rsp+50h+lpData], rax
0x18001f39a  mov     r8d, 2604h
0x18001f3a0  lea     rdx, aInetsrvIisMbMe; "inetsrv\\iis\\mb\\metadata\\metasub.cxx"
0x18001f3a7  call    cs:__imp_PuDbgPrint
0x18001f3ad  mov     rcx, [rbp+phkResult]; hKey
0x18001f3b1  lea     rax, [rbp+Data]
0x18001f3b5  mov     dword ptr [rsp+50h+lpcbData], ebx; cbData
0x18001f3b9  lea     rdx, aMetabaseunsecu; "MetabaseUnSecuredRead"
0x18001f3c0  mov     r9d, ebx; dwType
0x18001f3c3  mov     [rsp+50h+lpData], rax; lpData
0x18001f3c8  xor     r8d, r8d; Reserved
0x18001f3cb  mov     dword ptr [rbp+Data], 2
0x18001f3d2  call    cs:__imp_RegSetValueExA
0x18001f3d8  test    eax, eax
0x18001f3da  jnz     short loc_18001F412
0x18001f3dc  test    byte ptr cs:g_dwDebugFlags, 3
0x18001f3e3  jz      short loc_18001F412
0x18001f3e5  mov     rcx, cs:g_pDebug
0x18001f3ec  lea     rax, aReanablingDecr; "Reanabling decryption after W9z upgrade"...
0x18001f3f3  lea     r9, aInitsessionkey; "InitSessionKey"
0x18001f3fa  mov     [rsp+50h+lpData], rax
0x18001f3ff  mov     r8d, 2611h
0x18001f405  lea     rdx, aInetsrvIisMbMe; "inetsrv\\iis\\mb\\metadata\\metasub.cxx"
0x18001f40c  call    cs:__imp_PuDbgPrint
0x18001f412  mov     rcx, [rbp+phkResult]; hKey
0x18001f416  call    cs:__imp_RegCloseKey
0x18001f41c  xor     ebx, ebx
0x18001f41e  test    esi, esi
0x18001f420  jz      loc_18001F52F
0x18001f426  lea     rax, [rbp+var_8]
0x18001f42a  mov     [rbp+var_1C], ebx
0x18001f42d  mov     [rsp+50h+lpcbData], rax; void **
0x18001f432  lea     r9, aSessionkey; "SessionKey"
0x18001f439  lea     rax, [rbp+var_1C]
0x18001f43d  mov     [rbp+var_8], rbx
0x18001f441  lea     r8d, [rbx+34h]; unsigned int
0x18001f445  mov     [rsp+50h+lpData], rax; unsigned int *
0x18001f44a  lea     rdx, String; "."
0x18001f451  mov     rcx, r15; struct ISimpleTableRead2 *
0x18001f454  call    ?GetValue@@YAJPEAUISimpleTableRead2@@PEBGK1PEAKPEAPEAX@Z; GetValue(ISimpleTableRead2 *,ushort const *,ulong,ushort const *,ulong *,void * *)
0x18001f459  test    eax, eax
0x18001f45b  jns     short loc_18001F4A1
0x18001f45d  test    byte ptr cs:g_dwDebugFlags, 3
0x18001f464  jz      short loc_18001F497
0x18001f466  mov     rcx, cs:g_pDebug
0x18001f46d  lea     r9, aInitsessionkey; "InitSessionKey"
0x18001f474  mov     dword ptr [rsp+50h+lpcbData], eax
0x18001f478  lea     rdx, aInetsrvIisMbMe; "inetsrv\\iis\\mb\\metadata\\metasub.cxx"
0x18001f47f  lea     rax, aInitsessionkey_0; "[InitSessionKey] Error: Session key cou"...
0x18001f486  mov     r8d, 2626h
0x18001f48c  mov     [rsp+50h+lpData], rax
0x18001f491  call    cs:__imp_PuDbgPrintW
0x18001f497  mov     eax, 800CC81Dh
0x18001f49c  jmp     loc_18001F531
0x18001f4a1  mov     rax, [rbp+var_8]
0x18001f4a5  cmp     dword ptr [rax], 62436349h
0x18001f4ab  jnz     short loc_18001F4C3
0x18001f4ad  mov     cs:dword_180048964, ebx
0x18001f4b3  mov     cs:?fCryptoSettingsDoOverrride@@3HA, 1; int fCryptoSettingsDoOverrride
0x18001f4bd  mov     cs:?fCryptoSettingsOverrideFlag@@3HA, ebx; int fCryptoSettingsOverrideFlag
0x18001f4c3  test    r14, r14
0x18001f4c6  jnz     short loc_18001F4D8
0x18001f4c8  mov     edx, [rbp+var_1C]; unsigned int
0x18001f4cb  mov     r8, rdi; struct IIS_CRYPTO_STORAGE **
0x18001f4ce  mov     rcx, rax; unsigned __int8 *
0x18001f4d1  call    ?InitStorageHelper@@YAJPEAEKPEAPEAVIIS_CRYPTO_STORAGE@@@Z; InitStorageHelper(uchar *,ulong,IIS_CRYPTO_STORAGE * *)
0x18001f4d6  jmp     short loc_18001F4EF
0x18001f4d8  mov     r8d, [rbp+var_1C]; unsigned int
0x18001f4dc  mov     r9, rdi; struct IIS_CRYPTO_STORAGE **
0x18001f4df  mov     rdx, rax; unsigned __int8 *
0x18001f4e2  mov     dword ptr [rsp+50h+lpData], r12d; int
0x18001f4e7  mov     rcx, r14; char *
0x18001f4ea  call    ?InitStorageHelper2@@YAJPEADPEAEKPEAPEAVIIS_CRYPTO_STORAGE@@H@Z; InitStorageHelper2(char *,uchar *,ulong,IIS_CRYPTO_STORAGE * *,int)
0x18001f4ef  mov     ebx, eax
0x18001f4f1  test    eax, eax
0x18001f4f3  jns     short loc_18001F52F
0x18001f4f5  test    byte ptr cs:g_dwDebugFlags, 3
0x18001f4fc  jz      short loc_18001F52F
0x18001f4fe  mov     rcx, cs:g_pDebug
0x18001f505  lea     r9, aInitsessionkey; "InitSessionKey"
0x18001f50c  mov     dword ptr [rsp+50h+lpcbData], eax
0x18001f510  lea     rdx, aInetsrvIisMbMe; "inetsrv\\iis\\mb\\metadata\\metasub.cxx"
0x18001f517  lea     rax, aInitsessionkey_1; "[InitSessionKey] InitStorageHelper? fai"...
0x18001f51e  mov     r8d, 2644h
0x18001f524  mov     [rsp+50h+lpData], rax
0x18001f529  call    cs:__imp_PuDbgPrintW
0x18001f52f  mov     eax, ebx
0x18001f531  add     rsp, 50h
0x18001f535  pop     r15
0x18001f537  pop     r14
0x18001f539  pop     r12
0x18001f53b  pop     rdi
0x18001f53c  pop     rsi
0x18001f53d  pop     rbx
0x18001f53e  pop     rbp
0x18001f53f  retn
```
