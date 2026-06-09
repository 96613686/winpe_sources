# PeapEapInfoGetList(ushort const *,int,_PEAP_EAP_INFO * *)

- ea: `0x180003240`
- end: `0x1800040cb`
- name: `?PeapEapInfoGetList@@YAKPEBGHPEAPEAU_PEAP_EAP_INFO@@@Z`
- size: `3723`
- prototype: `unsigned int(const unsigned __int16 *, int, struct _PEAP_EAP_INFO **)`
- caller_count: `9`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180002500`
- `0x1800045d0`
- `0x180005060`
- `0x18005892c`
- `0x180058be8`
- `0x180058ee4`
- `0x180059210`
- `0x18005d400`
- `0x180070884`

## callees

- `0x180002420`
- `0x180003118`
- `0x180003240`
- `0x1800040d4`
- `0x180004110`
- `0x180007d00`
- `0x180010140`
- `0x180035ce0`
- `0x180038270`
- `0x180038e64`
- `0x180082010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x1800033ba`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x1800033ba`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180003eb9`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180003eb9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003ee3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003f09`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003f2d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003ee3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003f09`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180003f2d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003f7a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003f7a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003f9e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003f9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800036b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800038f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003aa2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003d27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800040b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800036b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800038f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003aa2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003d27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800040b0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003439`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000351f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800035fd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003678`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003843`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800038be`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800039ed`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003a68`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003b93`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003c72`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003ced`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003439`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000351f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800035fd`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003678`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003843`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800038be`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800039ed`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003a68`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003b93`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003c72`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003ced`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003536`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003596`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800036c7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800036d6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003747`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800037c8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800037d6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003909`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003918`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003977`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003985`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003ab3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003ac2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003b1f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003b2d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003bf1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003c02`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003d38`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003d47`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003d7d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003d8b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003fce`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003fdd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004084`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000409a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003536`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003596`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800036c7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800036d6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003747`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800037c8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800037d6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003909`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003918`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003977`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003985`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003ab3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003ac2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003b1f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003b2d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003bf1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003c02`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003d38`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003d47`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003d7d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003d8b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003fce`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003fdd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004084`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000409a`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180003372`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180003372`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800033d3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003faf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000401b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004031`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004047`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800033d3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003faf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000401b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004031`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004047`
- `api-ms-win-core-registry-l1-1-0!RegLoadMUIStringW` at `0x1800034fd`
- `api-ms-win-core-registry-l1-1-0!RegLoadMUIStringW` at `0x18000356d`
- `api-ms-win-core-registry-l1-1-0!RegLoadMUIStringW` at `0x1800034fd`
- `api-ms-win-core-registry-l1-1-0!RegLoadMUIStringW` at `0x18000356d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003309`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800033a2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180003309`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800033a2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003414`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800034ab`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800035de`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003636`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003824`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000387c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800039ce`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003a26`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003b78`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003bcc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003c53`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003cab`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003e31`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003e88`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003414`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800034ab`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800035de`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003636`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003824`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000387c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800039ce`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003a26`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003b78`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003bcc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003c53`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003cab`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003e31`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180003e88`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000365e`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000369e`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800038a4`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800038e4`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180003a4e`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180003a8e`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180003cd3`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180003d13`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000365e`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000369e`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800038a4`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800038e4`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180003a4e`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180003a8e`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180003cd3`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180003d13`
- `DSROLE!DsRoleGetPrimaryDomainInformation` at `0x18000329b`
- `DSROLE!DsRoleGetPrimaryDomainInformation` at `0x18000329b`
- `DSROLE!DsRoleFreeMemory` at `0x1800032ba`
- `DSROLE!DsRoleFreeMemory` at `0x1800032ba`
- `api-ms-win-core-registry-l2-1-0!RegConnectRegistryW` at `0x1800032d4`
- `api-ms-win-core-registry-l2-1-0!RegConnectRegistryW` at `0x1800032d4`

## string_xrefs

- `0x180003b5d`: `ConfigCLSID`
- `0x180003bbd`: `ConfigCLSID`
- `0x180003800`: `IdentityPath`
- `0x18000386d`: `IdentityPath`
- `0x1800039aa`: `InteractiveUIPath`
- `0x180003a17`: `InteractiveUIPath`
- `0x1800035c2`: `ConfigUIPath`
- `0x180003627`: `ConfigUIPath`
- `0x180003302`: `System\CurrentControlSet\Services\Rasman\PPP\EAP`

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
0x180003240  push    rbp
0x180003242  push    rbx
0x180003243  push    rsi
0x180003244  push    r13
0x180003246  lea     rbp, [rsp-128h]
0x18000324e  sub     rsp, 228h
0x180003255  mov     rax, cs:__security_cookie
0x18000325c  xor     rax, rsp
0x18000325f  mov     [rbp+140h+var_30], rax
0x180003266  xor     r13d, r13d
0x180003269  mov     rsi, r8
0x18000326c  lea     r8, [rsp+240h+Buffer]; Buffer
0x180003271  mov     [rsp+240h+phkResult], r13
0x180003276  mov     edx, 1; InfoLevel
0x18000327b  mov     [rsp+240h+hKey], r13
0x180003280  xor     ecx, ecx; lpServer
0x180003282  mov     [rsp+240h+var_1F0], r13
0x180003287  mov     [rsp+240h+cchName], r13d
0x18000328c  mov     [rsp+240h+cbData], r13d
0x180003291  mov     [rsp+240h+Type], r13d
0x180003296  mov     [rsp+240h+Buffer], r13
0x18000329b  call    cs:__imp_DsRoleGetPrimaryDomainInformation
0x1800032a2  nop     dword ptr [rax+rax+00h]
0x1800032a7  mov     rcx, [rsp+240h+Buffer]; Buffer
0x1800032ac  test    eax, eax
0x1800032ae  jnz     short loc_1800032B5
0x1800032b0  test    rcx, rcx
0x1800032b3  jz      short loc_1800032C6
0x1800032b5  test    rcx, rcx
0x1800032b8  jz      short loc_1800032C6
0x1800032ba  call    cs:__imp_DsRoleFreeMemory
0x1800032c1  nop     dword ptr [rax+rax+00h]
0x1800032c6  lea     r8, [rsp+240h+phkResult]; phkResult
0x1800032cb  mov     rdx, 0FFFFFFFF80000002h; hKey
0x1800032d2  xor     ecx, ecx; lpMachineName
0x1800032d4  call    cs:__imp_RegConnectRegistryW
0x1800032db  nop     dword ptr [rax+rax+00h]
0x1800032e0  mov     ebx, eax
0x1800032e2  test    eax, eax
0x1800032e4  jnz     loc_180004011
0x1800032ea  mov     rcx, [rsp+240h+phkResult]; hKey
0x1800032ef  lea     rax, [rsp+240h+hKey]
0x1800032f4  mov     r9d, 20019h; samDesired
0x1800032fa  mov     [rsp+240h+var_220], rax; phkResult
0x1800032ff  xor     r8d, r8d; ulOptions
0x180003302  lea     rdx, aSystemCurrentc_6; "System\\CurrentControlSet\\Services\\Ra"...
0x180003309  call    cs:__imp_RegOpenKeyExW
0x180003310  nop     dword ptr [rax+rax+00h]
0x180003315  mov     ebx, eax
0x180003317  test    eax, eax
0x180003319  jnz     loc_180004011
0x18000331f  mov     [rsp+240h+arg_0], rdi
0x180003327  mov     eax, r13d
0x18000332a  mov     [rsp+240h+arg_8], r12
0x180003332  mov     [rsp+240h+arg_18], r14
0x18000333a  mov     [rsp+240h+var_20], r15
0x180003342  mov     rcx, [rsp+240h+hKey]; hKey
0x180003347  lea     r9, [rsp+240h+cchName]; lpcchName
0x18000334c  mov     [rsp+240h+lpftLastWriteTime], r13; lpftLastWriteTime
0x180003351  lea     r8, [rbp+140h+Name]; lpName
0x180003355  mov     [rsp+240h+lpcchClass], r13; lpcchClass
0x18000335a  mov     edx, eax; dwIndex
0x18000335c  mov     [rsp+240h+lpClass], r13; lpClass
0x180003361  mov     [rsp+240h+var_220], r13; lpReserved
0x180003366  mov     dword ptr [rsp+240h+Buffer], eax
0x18000336a  mov     [rsp+240h+cchName], 0C8h
0x180003372  call    cs:__imp_RegEnumKeyExW
0x180003379  nop     dword ptr [rax+rax+00h]
0x18000337e  test    eax, eax
0x180003380  jnz     loc_1800040C3
0x180003386  mov     rcx, [rsp+240h+hKey]; hKey
0x18000338b  lea     rax, [rsp+240h+var_1F0]
0x180003390  mov     r9d, 20019h; samDesired
0x180003396  mov     [rsp+240h+var_220], rax; phkResult
0x18000339b  xor     r8d, r8d; ulOptions
0x18000339e  lea     rdx, [rbp+140h+Name]; lpSubKey
0x1800033a2  call    cs:__imp_RegOpenKeyExW
0x1800033a9  nop     dword ptr [rax+rax+00h]
0x1800033ae  test    eax, eax
0x1800033b0  jnz     loc_180003FC3
0x1800033b6  lea     rcx, [rbp+140h+Name]
0x1800033ba  call    cs:__imp__o__wtol
0x1800033c1  nop     dword ptr [rax+rax+00h]
0x1800033c6  mov     rcx, [rsp+240h+var_1F0]; hKey
0x1800033cb  mov     r12d, eax
0x1800033ce  cmp     eax, 19h
0x1800033d1  jnz     short loc_1800033E4
0x1800033d3  call    cs:__imp_RegCloseKey
0x1800033da  nop     dword ptr [rax+rax+00h]
0x1800033df  jmp     loc_180003FBE
0x1800033e4  lea     rax, [rsp+240h+cbData]
0x1800033e9  mov     dword ptr [rsp+240h+Data], r13d
0x1800033ee  mov     [rsp+240h+lpClass], rax; lpcbData
0x1800033f3  lea     r9, [rsp+240h+Type]; lpType
0x1800033f8  lea     rax, [rsp+240h+Data]
0x1800033fd  mov     [rsp+240h+cbData], 4
0x180003405  xor     r8d, r8d; lpReserved
0x180003408  mov     [rsp+240h+var_220], rax; lpData
0x18000340d  lea     rdx, aRolessupported; "RolesSupported"
0x180003414  call    cs:__imp_RegQueryValueExW
0x18000341b  nop     dword ptr [rax+rax+00h]
0x180003420  test    eax, eax
0x180003422  jnz     short loc_18000342F
0x180003424  test    [rsp+240h+Data], 8
0x180003429  jnz     loc_180003FC3
0x18000342f  mov     edx, 0D8h; uBytes
0x180003434  mov     ecx, 40h ; '@'; uFlags
0x180003439  call    cs:__imp_LocalAlloc
0x180003440  nop     dword ptr [rax+rax+00h]
0x180003445  mov     rbx, rax
0x180003448  test    rax, rax
0x18000344b  jz      loc_1800040A6
0x180003451  xor     edx, edx; Val
0x180003453  mov     r8d, 0D8h; Size
0x180003459  mov     rcx, rax; void *
0x18000345c  call    memset_0
0x180003461  mov     rax, [rsi]
0x180003464  mov     rcx, rsi
0x180003467  test    rax, rax
0x18000346a  jz      short loc_18000346F
0x18000346c  mov     [rbx], rax
0x18000346f  mov     [rcx], rbx
0x180003472  lea     r9, [rsp+240h+Type]; lpType
0x180003477  mov     [rbx+8], r12d
0x18000347b  lea     rcx, [rsp+240h+cbData]
0x180003480  mov     [rsp+240h+lpClass], rcx; lpcbData
0x180003485  lea     rdx, aStandalonesupp; "StandAloneSupported"
0x18000348c  mov     rcx, [rsp+240h+var_1F0]; hKey
0x180003491  mov     rax, rbx
0x180003494  mov     rax, [rsi]
0x180003497  xor     r8d, r8d; lpReserved
0x18000349a  add     rax, 40h ; '@'
0x18000349e  mov     [rsp+240h+cbData], 4
0x1800034a6  mov     [rsp+240h+var_220], rax; lpData
0x1800034ab  call    cs:__imp_RegQueryValueExW
0x1800034b2  nop     dword ptr [rax+rax+00h]
0x1800034b7  test    eax, eax
0x1800034b9  jz      short loc_1800034C5
0x1800034bb  mov     rax, [rsi]
0x1800034be  mov     dword ptr [rax+40h], 1
0x1800034c5  mov     r15, [rsp+240h+var_1F0]
0x1800034ca  lea     rax, [rsp+240h+Data]
0x1800034cf  mov     r14, [rsi]
0x1800034d2  lea     rdx, pszValue; "FriendlyName"
0x1800034d9  mov     [rsp+240h+lpcchClass], r13; pszDirectory
0x1800034de  xor     r9d, r9d; cbOutBuf
0x1800034e1  mov     dword ptr [rsp+240h+lpClass], r13d; Flags
0x1800034e6  xor     r8d, r8d; pszOutBuf
0x1800034e9  mov     rcx, r15; hKey
0x1800034ec  mov     dword ptr [rsp+240h+Data], r13d
0x1800034f1  mov     [r14+18h], r13
0x1800034f5  mov     rbx, r13
0x1800034f8  mov     [rsp+240h+var_220], rax; pcbData
0x1800034fd  call    cs:__imp_RegLoadMUIStringW
0x180003504  nop     dword ptr [rax+rax+00h]
0x180003509  mov     edi, eax
0x18000350b  cmp     eax, 0EAh
0x180003510  jnz     loc_180003744
0x180003516  mov     edx, dword ptr [rsp+240h+Data]; uBytes
0x18000351a  mov     ecx, 40h ; '@'; uFlags
0x18000351f  call    cs:__imp_LocalAlloc
0x180003526  nop     dword ptr [rax+rax+00h]
0x18000352b  mov     rbx, rax
0x18000352e  test    rax, rax
0x180003531  jnz     short loc_180003547
0x180003533  mov     rcx, rax; hMem
0x180003536  call    cs:__imp_LocalFree
0x18000353d  nop     dword ptr [rax+rax+00h]
0x180003542  jmp     loc_18000375B
0x180003547  mov     r9d, dword ptr [rsp+240h+Data]; cbOutBuf
0x18000354c  lea     rax, [rsp+240h+Data]
0x180003551  mov     [rsp+240h+lpcchClass], r13; pszDirectory
0x180003556  lea     rdx, pszValue; "FriendlyName"
0x18000355d  mov     dword ptr [rsp+240h+lpClass], r13d; Flags
0x180003562  mov     r8, rbx; pszOutBuf
0x180003565  mov     rcx, r15; hKey
0x180003568  mov     [rsp+240h+var_220], rax; pcbData
0x18000356d  call    cs:__imp_RegLoadMUIStringW
0x180003574  nop     dword ptr [rax+rax+00h]
0x180003579  mov     edi, eax
0x18000357b  test    eax, eax
0x18000357d  jnz     loc_180003744
0x180003583  mov     ecx, dword ptr [rsp+240h+Data]
0x180003587  shr     rcx, 1
0x18000358a  mov     [rbx+rcx*2-2], r13w
0x180003590  xor     ecx, ecx; hMem
0x180003592  mov     [r14+18h], rbx
0x180003596  call    cs:__imp_LocalFree
0x18000359d  nop     dword ptr [rax+rax+00h]
0x1800035a2  mov     r15, [rsp+240h+var_1F0]
0x1800035a7  lea     rax, [rsp+240h+Data]
0x1800035ac  mov     r13, [rsi]
0x1800035af  lea     r9, [rsp+240h+var_1FC]; lpType
0x1800035b4  xor     ebx, ebx
0x1800035b6  mov     [rsp+240h+lpClass], rax; lpcbData
0x1800035bb  xor     r8d, r8d; lpReserved
0x1800035be  mov     [rsp+240h+var_1FC], ebx
0x1800035c2  lea     rdx, aConfiguipath; "ConfigUIPath"
0x1800035c9  mov     dword ptr [rsp+240h+Data], ebx
0x1800035cd  mov     rcx, r15; hKey
0x1800035d0  mov     [r13+20h], rbx
0x1800035d4  mov     edi, ebx
0x1800035d6  mov     [rsp+240h+var_220], rbx; lpData
0x1800035db  mov     r14d, ebx
0x1800035de  call    cs:__imp_RegQueryValueExW
0x1800035e5  nop     dword ptr [rax+rax+00h]
0x1800035ea  mov     ebx, eax
0x1800035ec  test    eax, eax
0x1800035ee  jnz     loc_1800036C4
0x1800035f4  mov     edx, dword ptr [rsp+240h+Data]; uBytes
0x1800035f8  mov     ecx, 40h ; '@'; uFlags
0x1800035fd  call    cs:__imp_LocalAlloc
0x180003604  nop     dword ptr [rax+rax+00h]
0x180003609  mov     rdi, rax
0x18000360c  test    rax, rax
0x18000360f  jz      loc_180004081
0x180003615  lea     rax, [rsp+240h+Data]
0x18000361a  xor     r8d, r8d; lpReserved
0x18000361d  mov     [rsp+240h+lpClass], rax; lpcbData
0x180003622  lea     r9, [rsp+240h+var_1FC]; lpType
0x180003627  lea     rdx, aConfiguipath; "ConfigUIPath"
0x18000362e  mov     [rsp+240h+var_220], rdi; lpData
0x180003633  mov     rcx, r15; hKey
0x180003636  call    cs:__imp_RegQueryValueExW
0x18000363d  nop     dword ptr [rax+rax+00h]
0x180003642  mov     ebx, eax
0x180003644  test    eax, eax
0x180003646  jnz     short loc_1800036C4
0x180003648  mov     ecx, dword ptr [rsp+240h+Data]
0x18000364c  xor     ebx, ebx
0x18000364e  shr     rcx, 1
0x180003651  xor     r8d, r8d; nSize
0x180003654  xor     edx, edx; lpDst
0x180003656  mov     [rdi+rcx*2-2], bx
0x18000365b  mov     rcx, rdi; lpSrc
0x18000365e  call    cs:__imp_ExpandEnvironmentStringsW
0x180003665  nop     dword ptr [rax+rax+00h]
0x18000366a  mov     edx, eax
0x18000366c  mov     ecx, 40h ; '@'; uFlags
0x180003671  mov     dword ptr [rsp+240h+Data], edx
0x180003675  add     rdx, rdx; uBytes
0x180003678  call    cs:__imp_LocalAlloc
0x18000367f  nop     dword ptr [rax+rax+00h]
0x180003684  mov     r14, rax
0x180003687  mov     rcx, rdi; hMem
0x18000368a  test    rax, rax
0x18000368d  jz      loc_180003FCE
0x180003693  mov     [rax], bx
0x180003696  mov     rdx, rax; lpDst
0x180003699  mov     r8d, dword ptr [rsp+240h+Data]; nSize
0x18000369e  call    cs:__imp_ExpandEnvironmentStringsW
0x1800036a5  nop     dword ptr [rax+rax+00h]
0x1800036aa  mov     dword ptr [rsp+240h+Data], eax
0x1800036ae  test    eax, eax
0x1800036b0  jnz     loc_1800037C1
0x1800036b6  call    cs:__imp_GetLastError
0x1800036bd  nop     dword ptr [rax+rax+00h]
0x1800036c2  mov     ebx, eax
0x1800036c4  mov     rcx, rdi; hMem
0x1800036c7  call    cs:__imp_LocalFree
0x1800036ce  nop     dword ptr [rax+rax+00h]
0x1800036d3  mov     rcx, r14; hMem
0x1800036d6  call    cs:__imp_LocalFree
0x1800036dd  nop     dword ptr [rax+rax+00h]
0x1800036e2  test    ebx, ebx
0x1800036e4  jz      short loc_1800036EF
0x1800036e6  cmp     ebx, 2
0x1800036e9  jnz     loc_180003FEE
0x1800036ef  xor     ebx, ebx
0x1800036f1  mov     rax, [rsi]
0x1800036f4  mov     rcx, [rax+20h]
0x1800036f8  test    rcx, rcx
0x1800036fb  jz      loc_1800037E9
0x180003701  call    ?GetBinaryArch@@YA?AW4_ArchType@@PEBG@Z; GetBinaryArch(ushort const *)
0x180003706  mov     ebx, eax
0x180003708  cmp     eax, 0FFFFFFFFh
0x18000370b  jz      short loc_18000371C
0x18000370d  xor     ecx, ecx
0x18000370f  call    ?GetBinaryArch@@YA?AW4_ArchType@@PEBG@Z; GetBinaryArch(ushort const *)
0x180003714  cmp     ebx, eax
0x180003716  jz      loc_1800037E7
0x18000371c  mov     rcx, cs:WPP_GLOBAL_Control
0x180003723  lea     rax, WPP_GLOBAL_Control
0x18000372a  cmp     rcx, rax
0x18000372d  jz      loc_180003DE9
0x180003733  mov     r9, [rsi]
0x180003736  mov     edx, 1Ah
0x18000373b  mov     r9, [r9+20h]
0x18000373f  jmp     loc_180003DD9
0x180003744  mov     rcx, rbx; hMem
0x180003747  call    cs:__imp_LocalFree
0x18000374e  nop     dword ptr [rax+rax+00h]
0x180003753  test    edi, edi
0x180003755  jz      loc_1800035A2
0x18000375b  mov     rcx, cs:WPP_GLOBAL_Control
0x180003762  lea     rax, WPP_GLOBAL_Control
0x180003769  cmp     rcx, rax
0x18000376c  jz      short loc_180003783
0x18000376e  mov     rcx, [rcx+10h]
0x180003772  lea     r8, WPP_83ba5ba3c75e3f9f9375e1243d99c081_Traceguids
  ... truncated ...
```
