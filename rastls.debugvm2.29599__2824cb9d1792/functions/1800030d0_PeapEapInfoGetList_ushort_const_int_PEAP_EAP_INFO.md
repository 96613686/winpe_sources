# PeapEapInfoGetList(ushort const *,int,_PEAP_EAP_INFO * *)

- ea: `0x1800030d0`
- end: `0x180003d64`
- name: `?PeapEapInfoGetList@@YAKPEBGHPEAPEAU_PEAP_EAP_INFO@@@Z`
- size: `3220`
- prototype: `unsigned int(const unsigned __int16 *, int, struct _PEAP_EAP_INFO **)`
- caller_count: `9`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180002490`
- `0x180004230`
- `0x180004c10`
- `0x1800558a0`
- `0x180055b3c`
- `0x180055e20`
- `0x18005611c`
- `0x18005a060`
- `0x18006c11c`

## callees

- `0x1800023c0`
- `0x180003000`
- `0x1800030d0`
- `0x180003d6c`
- `0x180003db0`
- `0x1800075b0`
- `0x18000f350`
- `0x1800333b0`
- `0x180035680`
- `0x180036254`
- `0x18007c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x180003226`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x180003226`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180003bb1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180003bb1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003bd5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003bf5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003c13`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003bd5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003bf5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003c13`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003c56`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003c56`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003c74`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003c74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800034c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800036bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003824`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003a49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003d4f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800034c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800036bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003824`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003a49`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003d4f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003293`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003367`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003427`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003490`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003625`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000368e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000378d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800037f6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800038f1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800039b2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003a1b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003293`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003367`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003427`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003490`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003625`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000368e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000378d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800037f6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800038f1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800039b2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003a1b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003378`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800033cc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800034cd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800034d6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003541`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800035bc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800035c4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800036c7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800036d0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003729`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003731`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000382f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003838`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000388f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003897`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003943`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000394e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003a54`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003a5d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003a8d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003a95`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003c98`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003ca1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003d2f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003d3f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003378`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800033cc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800034cd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800034d6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003541`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800035bc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800035c4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800036c7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800036d0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003729`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003731`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000382f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003838`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000388f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003897`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003943`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000394e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003a54`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003a5d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003a8d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003a95`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003c98`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003ca1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003d2f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003d3f`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800031ea`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800031ea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003239`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003c7f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003cd9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003ce9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003cf9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003239`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003c7f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003cd9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003ce9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003cf9`
- `api-ms-win-core-registry-l1-1-0!RegLoadMUIStringW` at `0x18000334b`
- `api-ms-win-core-registry-l1-1-0!RegLoadMUIStringW` at `0x1800033a9`
- `api-ms-win-core-registry-l1-1-0!RegLoadMUIStringW` at `0x18000334b`
- `api-ms-win-core-registry-l1-1-0!RegLoadMUIStringW` at `0x1800033a9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003187`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003214`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003187`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003214`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003274`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800032ff`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000340e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000345a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000360c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003658`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003774`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800037c0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800038dc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003924`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003999`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800039e5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003b35`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003b86`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003274`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800032ff`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000340e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000345a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000360c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003658`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003774`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800037c0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800038dc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003924`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003999`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800039e5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003b35`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003b86`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000347c`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800034b0`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000367a`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800036ae`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800037e2`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180003816`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180003a07`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180003a3b`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000347c`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800034b0`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000367a`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800036ae`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800037e2`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180003816`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180003a07`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180003a3b`
- `DSROLE!DsRoleGetPrimaryDomainInformation` at `0x18000312b`
- `DSROLE!DsRoleGetPrimaryDomainInformation` at `0x18000312b`
- `DSROLE!DsRoleFreeMemory` at `0x180003144`
- `DSROLE!DsRoleFreeMemory` at `0x180003144`
- `api-ms-win-core-registry-l2-1-0!RegConnectRegistryW` at `0x180003158`
- `api-ms-win-core-registry-l2-1-0!RegConnectRegistryW` at `0x180003158`

## string_xrefs

- `0x1800038c1`: `ConfigCLSID`
- `0x180003915`: `ConfigCLSID`
- `0x1800035e8`: `IdentityPath`
- `0x180003649`: `IdentityPath`
- `0x180003750`: `InteractiveUIPath`
- `0x1800037b1`: `InteractiveUIPath`
- `0x1800033f2`: `ConfigUIPath`
- `0x18000344b`: `ConfigUIPath`
- `0x180003180`: `System\CurrentControlSet\Services\Rasman\PPP\EAP`

## pseudocode

```c
__int64 __fastcall PeapEapInfoGetList(const unsigned __int16 *a1, __int64 a2, struct _PEAP_EAP_INFO **a3)
{
  DWORD LastError; // ebx
  DWORD i; // eax
  unsigned int v6; // r12d
  struct _PEAP_EAP_INFO *v7; // rax
  struct _PEAP_EAP_INFO *v8; // rbx
  BYTE *v9; // rax
  HKEY v10; // r15
  char *v11; // r14
  HKEY v12; // rcx
  WCHAR *v13; // rbx
  LSTATUS MUIStringW; // edi
  HKEY v15; // r15
  char *v16; // r13
  HKEY v17; // rcx
  BYTE *v18; // rdi
  WCHAR *v19; // r14
  WCHAR *v20; // rax
  BYTE *v21; // rcx
  int v22; // ebx
  struct _EAPTLS_CONTROL_BLOCK *v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // r9
  unsigned int SZ; // eax
  HKEY v27; // r15
  char *v28; // r13
  HKEY v29; // rcx
  WCHAR *v30; // rax
  const unsigned __int16 *v31; // rcx
  HKEY v32; // r15
  char *v33; // r13
  HKEY v34; // rcx
  WCHAR *v35; // rax
  const unsigned __int16 *v36; // rcx
  HKEY v37; // r14
  char *v38; // r15
  HKEY v39; // rcx
  HLOCAL v40; // rdi
  HKEY v41; // r15
  char *v42; // r13
  WCHAR *v43; // rax
  __int64 v44; // rcx
  int BinaryArch; // ebx
  BYTE *v46; // rax
  LSTATUS v47; // eax
  BYTE *v48; // rax
  LSTATUS v49; // eax
  HMODULE v50; // rcx
  FARPROC ProcAddress; // rbx
  WCHAR *v52; // rcx
  BYTE Data[4]; // [rsp+40h] [rbp-C0h] BYREF
  DWORD v55; // [rsp+44h] [rbp-BCh] BYREF
  DWORD cbData; // [rsp+48h] [rbp-B8h] BYREF
  HKEY v57; // [rsp+50h] [rbp-B0h] BYREF
  DWORD Type; // [rsp+58h] [rbp-A8h] BYREF
  DWORD cchName; // [rsp+5Ch] [rbp-A4h] BYREF
  PBYTE Buffer; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  HKEY phkResult; // [rsp+70h] [rbp-90h] BYREF
  WCHAR Name[200]; // [rsp+80h] [rbp-80h] BYREF

  phkResult = 0;
  hKey = 0;
  v57 = 0;
  cchName = 0;
  cbData = 0;
  Type = 0;
  Buffer = 0;
  if ( (DsRoleGetPrimaryDomainInformation(0, DsRolePrimaryDomainInfoBasic, &Buffer) || Buffer) && Buffer )
    DsRoleFreeMemory(Buffer);
  LastError = RegConnectRegistryW(0, HKEY_LOCAL_MACHINE, &phkResult);
  if ( LastError )
    goto LABEL_106;
  LastError = RegOpenKeyExW(phkResult, L"System\\CurrentControlSet\\Services\\Rasman\\PPP\\EAP", 0, 0x20019u, &hKey);
  if ( LastError )
    goto LABEL_106;
  for ( i = 0; ; i = (_DWORD)Buffer + 1 )
  {
    while ( 1 )
    {
      LODWORD(Buffer) = i;
      cchName = 200;
      if ( RegEnumKeyExW(hKey, i, Name, &cchName, 0, 0, 0, 0) )
      {
        LastError = 0;
        goto LABEL_106;
      }
      if ( !RegOpenKeyExW(hKey, Name, 0, 0x20019u, &v57) )
      {
        v6 = _o__wtol(Name);
        if ( v6 == 25 )
          goto LABEL_102;
        *(_DWORD *)Data = 0;
        cbData = 4;
        if ( RegQueryValueExW(v57, L"RolesSupported", 0, &Type, Data, &cbData) || (Data[0] & 8) == 0 )
          break;
      }
LABEL_103:
      i = (_DWORD)Buffer + 1;
    }
    v7 = (struct _PEAP_EAP_INFO *)LocalAlloc(0x40u, 0xD8u);
    v8 = v7;
    if ( !v7 )
      goto LABEL_117;
    memset_0(v7, 0, 0xD8u);
    if ( *a3 )
      *(_QWORD *)v8 = *a3;
    *a3 = v8;
    *((_DWORD *)v8 + 2) = v6;
    v9 = (BYTE *)*a3 + 64;
    cbData = 4;
    if ( RegQueryValueExW(v57, L"StandAloneSupported", 0, &Type, v9, &cbData) )
      *((_DWORD *)*a3 + 16) = 1;
    v10 = v57;
    v11 = (char *)*a3;
    v12 = v57;
    *(_DWORD *)Data = 0;
    *((_QWORD *)v11 + 3) = 0;
    v13 = 0;
    MUIStringW = RegLoadMUIStringW(v12, L"FriendlyName", 0, 0, (LPDWORD)Data, 0, 0);
    if ( MUIStringW != 234 )
      goto LABEL_36;
    v13 = (WCHAR *)LocalAlloc(0x40u, *(unsigned int *)Data);
    if ( v13 )
    {
      MUIStringW = RegLoadMUIStringW(v10, L"FriendlyName", v13, *(DWORD *)Data, (LPDWORD)Data, 0, 0);
      if ( !MUIStringW )
      {
        v13[((unsigned __int64)*(unsigned int *)Data >> 1) - 1] = 0;
        *((_QWORD *)v11 + 3) = v13;
        LocalFree(0);
        goto LABEL_23;
      }
LABEL_36:
      LocalFree(v13);
      if ( !MUIStringW )
        goto LABEL_23;
      goto LABEL_37;
    }
    LocalFree(0);
LABEL_37:
    if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_83ba5ba3c75e3f9f9375e1243d99c081_Traceguids);
    SZ = PeapEapInfoReadSZ(v57, L"FriendlyName", (unsigned __int16 **)*a3 + 3);
    LastError = SZ;
    if ( SZ )
    {
      if ( SZ != 2 )
        goto LABEL_106;
      goto LABEL_82;
    }
LABEL_23:
    v15 = v57;
    v16 = (char *)*a3;
    v55 = 0;
    *(_DWORD *)Data = 0;
    v17 = v57;
    *((_QWORD *)v16 + 4) = 0;
    v18 = 0;
    v19 = 0;
    LastError = RegQueryValueExW(v17, L"ConfigUIPath", 0, &v55, 0, (LPDWORD)Data);
    if ( !LastError )
    {
      v18 = (BYTE *)LocalAlloc(0x40u, *(unsigned int *)Data);
      if ( !v18 )
        goto LABEL_115;
      LastError = RegQueryValueExW(v15, L"ConfigUIPath", 0, &v55, v18, (LPDWORD)Data);
      if ( !LastError )
      {
        *(_WORD *)&v18[2 * ((unsigned __int64)*(unsigned int *)Data >> 1) - 2] = 0;
        *(_DWORD *)Data = ExpandEnvironmentStringsW((LPCWSTR)v18, 0, 0);
        v20 = (WCHAR *)LocalAlloc(0x40u, 2LL * *(unsigned int *)Data);
        v19 = v20;
        v21 = v18;
        if ( !v20 )
          goto LABEL_104;
        *v20 = 0;
        *(_DWORD *)Data = ExpandEnvironmentStringsW((LPCWSTR)v18, v20, *(DWORD *)Data);
        if ( *(_DWORD *)Data )
        {
          *((_QWORD *)v16 + 4) = v19;
          LocalFree(v18);
          LocalFree(0);
          goto LABEL_31;
        }
        LastError = GetLastError();
      }
    }
    LocalFree(v18);
    LocalFree(v19);
    if ( LastError && LastError != 2 )
      goto LABEL_106;
LABEL_31:
    if ( *((_QWORD *)*a3 + 4) )
    {
      v22 = ((__int64 (*)(void))GetBinaryArch)();
      if ( v22 == -1 || v22 != (unsigned int)GetBinaryArch(0) )
      {
        v23 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          goto LABEL_82;
        v24 = 26;
        v25 = *((_QWORD *)*a3 + 4);
LABEL_89:
        WPP_SF_S(*((_QWORD *)v23 + 2), v24, WPP_83ba5ba3c75e3f9f9375e1243d99c081_Traceguids, v25);
        goto LABEL_82;
      }
    }
    v27 = v57;
    v28 = (char *)*a3;
    v55 = 0;
    v29 = v57;
    *(_DWORD *)Data = 0;
    *((_QWORD *)v28 + 5) = 0;
    v18 = 0;
    v19 = 0;
    LastError = RegQueryValueExW(v29, L"IdentityPath", 0, &v55, 0, (LPDWORD)Data);
    if ( !LastError )
    {
      v18 = (BYTE *)LocalAlloc(0x40u, *(unsigned int *)Data);
      if ( !v18 )
        goto LABEL_115;
      LastError = RegQueryValueExW(v27, L"IdentityPath", 0, &v55, v18, (LPDWORD)Data);
      if ( !LastError )
      {
        *(_WORD *)&v18[2 * ((unsigned __int64)*(unsigned int *)Data >> 1) - 2] = 0;
        *(_DWORD *)Data = ExpandEnvironmentStringsW((LPCWSTR)v18, 0, 0);
        v30 = (WCHAR *)LocalAlloc(0x40u, 2LL * *(unsigned int *)Data);
        v19 = v30;
        v21 = v18;
        if ( !v30 )
          goto LABEL_104;
        *v30 = 0;
        *(_DWORD *)Data = ExpandEnvironmentStringsW((LPCWSTR)v18, v30, *(DWORD *)Data);
        if ( *(_DWORD *)Data )
        {
          *((_QWORD *)v28 + 5) = v19;
          LocalFree(v18);
          LocalFree(0);
          goto LABEL_51;
        }
        LastError = GetLastError();
      }
    }
    LocalFree(v18);
    LocalFree(v19);
    if ( LastError && LastError != 2 )
      goto LABEL_106;
LABEL_51:
    v31 = (const unsigned __int16 *)*((_QWORD *)*a3 + 5);
    if ( v31 && !(unsigned int)IsSameArchAsCurrentModule(v31) )
    {
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        goto LABEL_82;
      v24 = 27;
      v25 = *((_QWORD *)*a3 + 5);
      goto LABEL_89;
    }
    v32 = v57;
    v33 = (char *)*a3;
    v55 = 0;
    v34 = v57;
    *(_DWORD *)Data = 0;
    *((_QWORD *)v33 + 6) = 0;
    v18 = 0;
    v19 = 0;
    LastError = RegQueryValueExW(v34, L"InteractiveUIPath", 0, &v55, 0, (LPDWORD)Data);
    if ( !LastError )
    {
      v18 = (BYTE *)LocalAlloc(0x40u, *(unsigned int *)Data);
      if ( !v18 )
        goto LABEL_115;
      LastError = RegQueryValueExW(v32, L"InteractiveUIPath", 0, &v55, v18, (LPDWORD)Data);
      if ( !LastError )
      {
        *(_WORD *)&v18[2 * ((unsigned __int64)*(unsigned int *)Data >> 1) - 2] = 0;
        *(_DWORD *)Data = ExpandEnvironmentStringsW((LPCWSTR)v18, 0, 0);
        v35 = (WCHAR *)LocalAlloc(0x40u, 2LL * *(unsigned int *)Data);
        v19 = v35;
        v21 = v18;
        if ( !v35 )
          goto LABEL_104;
        *v35 = 0;
        *(_DWORD *)Data = ExpandEnvironmentStringsW((LPCWSTR)v18, v35, *(DWORD *)Data);
        if ( *(_DWORD *)Data )
        {
          *((_QWORD *)v33 + 6) = v19;
          LocalFree(v18);
          LocalFree(0);
          goto LABEL_64;
        }
        LastError = GetLastError();
      }
    }
    LocalFree(v18);
    LocalFree(v19);
    if ( LastError && LastError != 2 )
      goto LABEL_106;
LABEL_64:
    v36 = (const unsigned __int16 *)*((_QWORD *)*a3 + 6);
    if ( v36 && !(unsigned int)IsSameArchAsCurrentModule(v36) )
    {
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        goto LABEL_82;
      v24 = 28;
      v25 = *((_QWORD *)*a3 + 6);
      goto LABEL_89;
    }
    v37 = v57;
    v38 = (char *)*a3;
    v55 = 0;
    *(_DWORD *)Data = 0;
    v39 = v57;
    *((_QWORD *)v38 + 7) = 0;
    v40 = 0;
    LastError = RegQueryValueExW(v39, L"ConfigCLSID", 0, &v55, 0, (LPDWORD)Data);
    if ( LastError )
    {
LABEL_73:
      LocalFree(v40);
      if ( LastError != 2 )
        goto LABEL_106;
      goto LABEL_74;
    }
    v40 = LocalAlloc(0x40u, *(unsigned int *)Data);
    if ( !v40 )
      break;
    LastError = RegQueryValueExW(v37, L"ConfigCLSID", 0, &v55, (LPBYTE)v40, (LPDWORD)Data);
    if ( LastError )
      goto LABEL_73;
    *((_WORD *)v40 + ((unsigned __int64)*(unsigned int *)Data >> 1) - 1) = 0;
    *((_QWORD *)v38 + 7) = v40;
    LocalFree(0);
LABEL_74:
    v41 = v57;
    v42 = (char *)*a3;
    v55 = 0;
    *(_DWORD *)Data = 0;
    v18 = 0;
    *((_QWORD *)v42 + 2) = 0;
    v19 = 0;
    LastError = RegQueryValueExW(v41, L"Path", 0, &v55, 0, (LPDWORD)Data);
    if ( !LastError )
    {
      v18 = (BYTE *)LocalAlloc(0x40u, *(unsigned int *)Data);
      if ( !v18 )
      {
LABEL_115:
        LocalFree(v18);
        v52 = 0;
        goto LABEL_105;
      }
      LastError = RegQueryValueExW(v41, L"Path", 0, &v55, v18, (LPDWORD)Data);
      if ( !LastError )
      {
        *(_WORD *)&v18[2 * ((unsigned __int64)*(unsigned int *)Data >> 1) - 2] = 0;
        *(_DWORD *)Data = ExpandEnvironmentStringsW((LPCWSTR)v18, 0, 0);
        v43 = (WCHAR *)LocalAlloc(0x40u, 2LL * *(unsigned int *)Data);
        v19 = v43;
        v21 = v18;
        if ( !v43 )
        {
LABEL_104:
          LocalFree(v21);
          v52 = v19;
LABEL_105:
          LocalFree(v52);
          LastError = 14;
          goto LABEL_106;
        }
        *v43 = 0;
        *(_DWORD *)Data = ExpandEnvironmentStringsW((LPCWSTR)v18, v43, *(DWORD *)Data);
        if ( *(_DWORD *)Data )
        {
          *((_QWORD *)v42 + 2) = v19;
          LocalFree(v18);
          LocalFree(0);
LABEL_84:
          v44 = *((_QWORD *)*a3 + 2);
          if ( v44 )
          {
            BinaryArch = GetBinaryArch(v44);
            if ( BinaryArch == -1 || BinaryArch != (unsigned int)GetBinaryArch(0) )
            {
              v23 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
                goto LABEL_82;
              v24 = 29;
              v25 = *((_QWORD *)*a3 + 2);
              goto LABEL_89;
            }
          }
          v46 = (BYTE *)*a3 + 68;
          cbData = 4;
          v47 = RegQueryValueExW(v57, L"InvokeUsernameDialog", 0, &Type, v46, &cbData);
          LastError = v47;
          if ( v47 )
          {
            if ( v47 != 2 )
              goto LABEL_106;
            *((_DWORD *)*a3 + 17) = 1;
          }
          v48 = (BYTE *)*a3 + 72;
          cbData = 4;
          v49 = RegQueryValueExW(v57, L"InvokePasswordDialog", 0, &Type, v48, &cbData);
          LastError = v49;
          if ( v49 )
          {
            if ( v49 != 2 )
              goto LABEL_106;
            *((_DWORD *)*a3 + 18) = 1;
          }
          *((_QWORD *)*a3 + 10) = LoadLibraryExW(*((LPCWSTR *)*a3 + 2), 0, 0);
          v50 = (HMODULE)*((_QWORD *)*a3 + 10);
          if ( !v50 || (ProcAddress = GetProcAddress(v50, "RasEapGetInfo")) == 0 )
          {
            LastError = GetLastError();
            goto LABEL_106;
          }
          *((_QWORD *)*a3 + 25) = GetProcAddress(*((HMODULE *)*a3 + 10), "RasEapGetCredentials");
          *((_QWORD *)*a3 + 26) = GetProcAddress(*((HMODULE *)*a3 + 10), "RasEapSetRetryFlag");
          *((_DWORD *)*a3 + 22) = 40;
          LastError = ((__int64 (__fastcall *)(_QWORD, char *))ProcAddress)(v6, (char *)*a3 + 88);
          if ( LastError )
            goto LABEL_106;
          if ( *((_QWORD *)*a3 + 12) )
          {
            EnterCriticalSection(&g_csPeapInnerMethodInitLock);
            (*((void (__fastcall **)(__int64))*a3 + 12))(1);
            LeaveCriticalSection(&g_csPeapInnerMethodInitLock);
          }
LABEL_102:
          RegCloseKey(v57);
          v57 = 0;
          goto LABEL_103;
        }
        LastError = GetLastError();
      }
    }
    LocalFree(v18);
    LocalFree(v19);
    if ( !LastError )
      goto LABEL_84;
    if ( LastError != 2 )
      goto LABEL_106;
LABEL_82:
    PeapEapInfoRemoveHeadNode(a3);
  }
  LocalFree(0);
LABEL_117:
  LastError = 14;
LABEL_106:
  if ( v57 )
    RegCloseKey(v57);
  if ( hKey )
    RegCloseKey(hKey);
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( LastError )
  {
    PeapEapInfoFreeList(*a3);
    *a3 = 0;
  }
  return LastError;
}

```

## disassembly

```asm
0x1800030d0  push    rbp
0x1800030d2  push    rbx
0x1800030d3  push    rsi
0x1800030d4  push    r13
0x1800030d6  lea     rbp, [rsp-128h]
0x1800030de  sub     rsp, 228h
0x1800030e5  mov     rax, cs:__security_cookie
0x1800030ec  xor     rax, rsp
0x1800030ef  mov     [rbp+140h+var_30], rax
0x1800030f6  xor     r13d, r13d
0x1800030f9  mov     rsi, r8
0x1800030fc  lea     r8, [rsp+240h+Buffer]; Buffer
0x180003101  mov     [rsp+240h+phkResult], r13
0x180003106  mov     edx, 1; InfoLevel
0x18000310b  mov     [rsp+240h+hKey], r13
0x180003110  xor     ecx, ecx; lpServer
0x180003112  mov     [rsp+240h+var_1F0], r13
0x180003117  mov     [rsp+240h+cchName], r13d
0x18000311c  mov     [rsp+240h+cbData], r13d
0x180003121  mov     [rsp+240h+Type], r13d
0x180003126  mov     [rsp+240h+Buffer], r13
0x18000312b  call    cs:__imp_DsRoleGetPrimaryDomainInformation
0x180003131  mov     rcx, [rsp+240h+Buffer]; Buffer
0x180003136  test    eax, eax
0x180003138  jnz     short loc_18000313F
0x18000313a  test    rcx, rcx
0x18000313d  jz      short loc_18000314A
0x18000313f  test    rcx, rcx
0x180003142  jz      short loc_18000314A
0x180003144  call    cs:__imp_DsRoleFreeMemory
0x18000314a  lea     r8, [rsp+240h+phkResult]; phkResult
0x18000314f  mov     rdx, 0FFFFFFFF80000002h; hKey
0x180003156  xor     ecx, ecx; lpMachineName
0x180003158  call    cs:__imp_RegConnectRegistryW
0x18000315e  mov     ebx, eax
0x180003160  test    eax, eax
0x180003162  jnz     loc_180003CCF
0x180003168  mov     rcx, [rsp+240h+phkResult]; hKey
0x18000316d  lea     rax, [rsp+240h+hKey]
0x180003172  mov     r9d, 20019h; samDesired
0x180003178  mov     [rsp+240h+var_220], rax; phkResult
0x18000317d  xor     r8d, r8d; ulOptions
0x180003180  lea     rdx, aSystemCurrentc_6; "System\\CurrentControlSet\\Services\\Ra"...
0x180003187  call    cs:__imp_RegOpenKeyExW
0x18000318d  mov     ebx, eax
0x18000318f  test    eax, eax
0x180003191  jnz     loc_180003CCF
0x180003197  mov     [rsp+240h+arg_0], rdi
0x18000319f  mov     eax, r13d
0x1800031a2  mov     [rsp+240h+arg_8], r12
0x1800031aa  mov     [rsp+240h+arg_18], r14
0x1800031b2  mov     [rsp+240h+var_20], r15
0x1800031ba  mov     rcx, [rsp+240h+hKey]; hKey
0x1800031bf  lea     r9, [rsp+240h+cchName]; lpcchName
0x1800031c4  mov     [rsp+240h+lpftLastWriteTime], r13; lpftLastWriteTime
0x1800031c9  lea     r8, [rbp+140h+Name]; lpName
0x1800031cd  mov     [rsp+240h+lpcchClass], r13; lpcchClass
0x1800031d2  mov     edx, eax; dwIndex
0x1800031d4  mov     [rsp+240h+lpClass], r13; lpClass
0x1800031d9  mov     [rsp+240h+var_220], r13; lpReserved
0x1800031de  mov     dword ptr [rsp+240h+Buffer], eax
0x1800031e2  mov     [rsp+240h+cchName], 0C8h
0x1800031ea  call    cs:__imp_RegEnumKeyExW
0x1800031f0  test    eax, eax
0x1800031f2  jnz     loc_180003D5C
0x1800031f8  mov     rcx, [rsp+240h+hKey]; hKey
0x1800031fd  lea     rax, [rsp+240h+var_1F0]
0x180003202  mov     r9d, 20019h; samDesired
0x180003208  mov     [rsp+240h+var_220], rax; phkResult
0x18000320d  xor     r8d, r8d; ulOptions
0x180003210  lea     rdx, [rbp+140h+Name]; lpSubKey
0x180003214  call    cs:__imp_RegOpenKeyExW
0x18000321a  test    eax, eax
0x18000321c  jnz     loc_180003C8D
0x180003222  lea     rcx, [rbp+140h+Name]
0x180003226  call    cs:__imp__o__wtol
0x18000322c  mov     rcx, [rsp+240h+var_1F0]; hKey
0x180003231  mov     r12d, eax
0x180003234  cmp     eax, 19h
0x180003237  jnz     short loc_180003244
0x180003239  call    cs:__imp_RegCloseKey
0x18000323f  jmp     loc_180003C88
0x180003244  lea     rax, [rsp+240h+cbData]
0x180003249  mov     dword ptr [rsp+240h+Data], r13d
0x18000324e  mov     [rsp+240h+lpClass], rax; lpcbData
0x180003253  lea     r9, [rsp+240h+Type]; lpType
0x180003258  lea     rax, [rsp+240h+Data]
0x18000325d  mov     [rsp+240h+cbData], 4
0x180003265  xor     r8d, r8d; lpReserved
0x180003268  mov     [rsp+240h+var_220], rax; lpData
0x18000326d  lea     rdx, aRolessupported; "RolesSupported"
0x180003274  call    cs:__imp_RegQueryValueExW
0x18000327a  test    eax, eax
0x18000327c  jnz     short loc_180003289
0x18000327e  test    [rsp+240h+Data], 8
0x180003283  jnz     loc_180003C8D
0x180003289  mov     edx, 0D8h; uBytes
0x18000328e  mov     ecx, 40h ; '@'; uFlags
0x180003293  call    cs:__imp_LocalAlloc
0x180003299  mov     rbx, rax
0x18000329c  test    rax, rax
0x18000329f  jz      loc_180003D45
0x1800032a5  xor     edx, edx; Val
0x1800032a7  mov     r8d, 0D8h; Size
0x1800032ad  mov     rcx, rax; void *
0x1800032b0  call    memset_0
0x1800032b5  mov     rax, [rsi]
0x1800032b8  mov     rcx, rsi
0x1800032bb  test    rax, rax
0x1800032be  jz      short loc_1800032C3
0x1800032c0  mov     [rbx], rax
0x1800032c3  mov     [rcx], rbx
0x1800032c6  lea     r9, [rsp+240h+Type]; lpType
0x1800032cb  mov     [rbx+8], r12d
0x1800032cf  lea     rcx, [rsp+240h+cbData]
0x1800032d4  mov     [rsp+240h+lpClass], rcx; lpcbData
0x1800032d9  lea     rdx, aStandalonesupp; "StandAloneSupported"
0x1800032e0  mov     rcx, [rsp+240h+var_1F0]; hKey
0x1800032e5  mov     rax, rbx
0x1800032e8  mov     rax, [rsi]
0x1800032eb  xor     r8d, r8d; lpReserved
0x1800032ee  add     rax, 40h ; '@'
0x1800032f2  mov     [rsp+240h+cbData], 4
0x1800032fa  mov     [rsp+240h+var_220], rax; lpData
0x1800032ff  call    cs:__imp_RegQueryValueExW
0x180003305  test    eax, eax
0x180003307  jz      short loc_180003313
0x180003309  mov     rax, [rsi]
0x18000330c  mov     dword ptr [rax+40h], 1
0x180003313  mov     r15, [rsp+240h+var_1F0]
0x180003318  lea     rax, [rsp+240h+Data]
0x18000331d  mov     r14, [rsi]
0x180003320  lea     rdx, pszValue; "FriendlyName"
0x180003327  mov     [rsp+240h+lpcchClass], r13; pszDirectory
0x18000332c  xor     r9d, r9d; cbOutBuf
0x18000332f  mov     dword ptr [rsp+240h+lpClass], r13d; Flags
0x180003334  xor     r8d, r8d; pszOutBuf
0x180003337  mov     rcx, r15; hKey
0x18000333a  mov     dword ptr [rsp+240h+Data], r13d
0x18000333f  mov     [r14+18h], r13
0x180003343  mov     rbx, r13
0x180003346  mov     [rsp+240h+var_220], rax; pcbData
0x18000334b  call    cs:__imp_RegLoadMUIStringW
0x180003351  mov     edi, eax
0x180003353  cmp     eax, 0EAh
0x180003358  jnz     loc_18000353E
0x18000335e  mov     edx, dword ptr [rsp+240h+Data]; uBytes
0x180003362  mov     ecx, 40h ; '@'; uFlags
0x180003367  call    cs:__imp_LocalAlloc
0x18000336d  mov     rbx, rax
0x180003370  test    rax, rax
0x180003373  jnz     short loc_180003383
0x180003375  mov     rcx, rax; hMem
0x180003378  call    cs:__imp_LocalFree
0x18000337e  jmp     loc_18000354F
0x180003383  mov     r9d, dword ptr [rsp+240h+Data]; cbOutBuf
0x180003388  lea     rax, [rsp+240h+Data]
0x18000338d  mov     [rsp+240h+lpcchClass], r13; pszDirectory
0x180003392  lea     rdx, pszValue; "FriendlyName"
0x180003399  mov     dword ptr [rsp+240h+lpClass], r13d; Flags
0x18000339e  mov     r8, rbx; pszOutBuf
0x1800033a1  mov     rcx, r15; hKey
0x1800033a4  mov     [rsp+240h+var_220], rax; pcbData
0x1800033a9  call    cs:__imp_RegLoadMUIStringW
0x1800033af  mov     edi, eax
0x1800033b1  test    eax, eax
0x1800033b3  jnz     loc_18000353E
0x1800033b9  mov     ecx, dword ptr [rsp+240h+Data]
0x1800033bd  shr     rcx, 1
0x1800033c0  mov     [rbx+rcx*2-2], r13w
0x1800033c6  xor     ecx, ecx; hMem
0x1800033c8  mov     [r14+18h], rbx
0x1800033cc  call    cs:__imp_LocalFree
0x1800033d2  mov     r15, [rsp+240h+var_1F0]
0x1800033d7  lea     rax, [rsp+240h+Data]
0x1800033dc  mov     r13, [rsi]
0x1800033df  lea     r9, [rsp+240h+var_1FC]; lpType
0x1800033e4  xor     ebx, ebx
0x1800033e6  mov     [rsp+240h+lpClass], rax; lpcbData
0x1800033eb  xor     r8d, r8d; lpReserved
0x1800033ee  mov     [rsp+240h+var_1FC], ebx
0x1800033f2  lea     rdx, aConfiguipath; "ConfigUIPath"
0x1800033f9  mov     dword ptr [rsp+240h+Data], ebx
0x1800033fd  mov     rcx, r15; hKey
0x180003400  mov     [r13+20h], rbx
0x180003404  mov     edi, ebx
0x180003406  mov     [rsp+240h+var_220], rbx; lpData
0x18000340b  mov     r14d, ebx
0x18000340e  call    cs:__imp_RegQueryValueExW
0x180003414  mov     ebx, eax
0x180003416  test    eax, eax
0x180003418  jnz     loc_1800034CA
0x18000341e  mov     edx, dword ptr [rsp+240h+Data]; uBytes
0x180003422  mov     ecx, 40h ; '@'; uFlags
0x180003427  call    cs:__imp_LocalAlloc
0x18000342d  mov     rdi, rax
0x180003430  test    rax, rax
0x180003433  jz      loc_180003D2C
0x180003439  lea     rax, [rsp+240h+Data]
0x18000343e  xor     r8d, r8d; lpReserved
0x180003441  mov     [rsp+240h+lpClass], rax; lpcbData
0x180003446  lea     r9, [rsp+240h+var_1FC]; lpType
0x18000344b  lea     rdx, aConfiguipath; "ConfigUIPath"
0x180003452  mov     [rsp+240h+var_220], rdi; lpData
0x180003457  mov     rcx, r15; hKey
0x18000345a  call    cs:__imp_RegQueryValueExW
0x180003460  mov     ebx, eax
0x180003462  test    eax, eax
0x180003464  jnz     short loc_1800034CA
0x180003466  mov     ecx, dword ptr [rsp+240h+Data]
0x18000346a  xor     ebx, ebx
0x18000346c  shr     rcx, 1
0x18000346f  xor     r8d, r8d; nSize
0x180003472  xor     edx, edx; lpDst
0x180003474  mov     [rdi+rcx*2-2], bx
0x180003479  mov     rcx, rdi; lpSrc
0x18000347c  call    cs:__imp_ExpandEnvironmentStringsW
0x180003482  mov     edx, eax
0x180003484  mov     ecx, 40h ; '@'; uFlags
0x180003489  mov     dword ptr [rsp+240h+Data], edx
0x18000348d  add     rdx, rdx; uBytes
0x180003490  call    cs:__imp_LocalAlloc
0x180003496  mov     r14, rax
0x180003499  mov     rcx, rdi; hMem
0x18000349c  test    rax, rax
0x18000349f  jz      loc_180003C98
0x1800034a5  mov     [rax], bx
0x1800034a8  mov     rdx, rax; lpDst
0x1800034ab  mov     r8d, dword ptr [rsp+240h+Data]; nSize
0x1800034b0  call    cs:__imp_ExpandEnvironmentStringsW
0x1800034b6  mov     dword ptr [rsp+240h+Data], eax
0x1800034ba  test    eax, eax
0x1800034bc  jnz     loc_1800035B5
0x1800034c2  call    cs:__imp_GetLastError
0x1800034c8  mov     ebx, eax
0x1800034ca  mov     rcx, rdi; hMem
0x1800034cd  call    cs:__imp_LocalFree
0x1800034d3  mov     rcx, r14; hMem
0x1800034d6  call    cs:__imp_LocalFree
0x1800034dc  test    ebx, ebx
0x1800034de  jz      short loc_1800034E9
0x1800034e0  cmp     ebx, 2
0x1800034e3  jnz     loc_180003CAC
0x1800034e9  xor     ebx, ebx
0x1800034eb  mov     rax, [rsi]
0x1800034ee  mov     rcx, [rax+20h]
0x1800034f2  test    rcx, rcx
0x1800034f5  jz      loc_1800035D1
0x1800034fb  call    ?GetBinaryArch@@YA?AW4_ArchType@@PEBG@Z; GetBinaryArch(ushort const *)
0x180003500  mov     ebx, eax
0x180003502  cmp     eax, 0FFFFFFFFh
0x180003505  jz      short loc_180003516
0x180003507  xor     ecx, ecx
0x180003509  call    ?GetBinaryArch@@YA?AW4_ArchType@@PEBG@Z; GetBinaryArch(ushort const *)
0x18000350e  cmp     ebx, eax
0x180003510  jz      loc_1800035CF
0x180003516  mov     rcx, cs:WPP_GLOBAL_Control
0x18000351d  lea     rax, WPP_GLOBAL_Control
0x180003524  cmp     rcx, rax
0x180003527  jz      loc_180003AED
0x18000352d  mov     r9, [rsi]
0x180003530  mov     edx, 1Ah
0x180003535  mov     r9, [r9+20h]
0x180003539  jmp     loc_180003ADD
0x18000353e  mov     rcx, rbx; hMem
0x180003541  call    cs:__imp_LocalFree
0x180003547  test    edi, edi
0x180003549  jz      loc_1800033D2
0x18000354f  mov     rcx, cs:WPP_GLOBAL_Control
0x180003556  lea     rax, WPP_GLOBAL_Control
0x18000355d  cmp     rcx, rax
0x180003560  jz      short loc_180003577
0x180003562  mov     rcx, [rcx+10h]
0x180003566  lea     r8, WPP_83ba5ba3c75e3f9f9375e1243d99c081_Traceguids
0x18000356d  mov     edx, 19h
0x180003572  call    WPP_SF_
0x180003577  mov     r8, [rsi]
0x18000357a  lea     rdx, pszValue; "FriendlyName"
0x180003581  mov     rcx, [rsp+240h+var_1F0]; hKey
0x180003586  add     r8, 18h; unsigned __int16 **
0x18000358a  call    ?PeapEapInfoReadSZ@@YAKPEAUHKEY__@@PEBGPEAPEAG@Z; PeapEapInfoReadSZ(HKEY__ *,ushort const *,ushort * *)
0x18000358f  mov     ebx, eax
0x180003591  test    eax, eax
0x180003593  jz      loc_1800033D2
0x180003599  cmp     eax, 2
0x18000359c  jnz     loc_180003CAF
0x1800035a2  mov     rcx, rsi; struct _PEAP_EAP_INFO **
0x1800035a5  call    ?PeapEapInfoRemoveHeadNode@@YAXPEAPEAU_PEAP_EAP_INFO@@@Z; PeapEapInfoRemoveHeadNode(_PEAP_EAP_INFO * *)
0x1800035aa  mov     eax, dword ptr [rsp+240h+Buffer]
0x1800035ae  inc     eax
0x1800035b0  jmp     loc_1800031BA
0x1800035b5  mov     rcx, rdi; hMem
0x1800035b8  mov     [r13+20h], r14
0x1800035bc  call    cs:__imp_LocalFree
0x1800035c2  xor     ecx, ecx; hMem
0x1800035c4  call    cs:__imp_LocalFree
0x1800035ca  jmp     loc_1800034EB
0x1800035cf  xor     ebx, ebx
0x1800035d1  mov     r15, [rsp+240h+var_1F0]
0x1800035d6  lea     rax, [rsp+240h+Data]
  ... truncated ...
```
