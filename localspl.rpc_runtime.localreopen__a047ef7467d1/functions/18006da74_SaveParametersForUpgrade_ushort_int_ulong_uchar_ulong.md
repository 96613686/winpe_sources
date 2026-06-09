# SaveParametersForUpgrade(ushort *,int,ulong,uchar *,ulong)

- ea: `0x18006da74`
- end: `0x18006e0ad`
- name: `?SaveParametersForUpgrade@@YAHPEAGHKPEAEK@Z`
- size: `1593`
- prototype: `__int64 __usercall@<rax>(unsigned __int16 *@<rcx>, unsigned int@<edx>, unsigned int@<r8d>, unsigned __int8 *@<r9>, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180069f64`

## callees

- `0x18000b9ec`
- `0x18000edc4`
- `0x180046650`
- `0x18006d294`
- `0x18006d744`
- `0x18006da74`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18006db38`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18006db76`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18006dbb1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18006dbec`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18006db38`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18006db76`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18006dbb1`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18006dbec`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006e043`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006e053`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006e063`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006e073`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006e043`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006e053`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006e063`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006e073`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18006de46`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18006de74`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18006e000`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18006e02c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18006de46`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18006de74`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18006e000`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18006e02c`
- `SPOOLSS!RevertToPrinterSelf` at `0x18006dacc`
- `SPOOLSS!RevertToPrinterSelf` at `0x18006dacc`
- `SPOOLSS!ImpersonatePrinterClient` at `0x18006e081`
- `SPOOLSS!ImpersonatePrinterClient` at `0x18006e081`

## string_xrefs

- `0x18006df7f`: `InfPath`
- `0x18006dc76`: `DriverMoved`
- `0x18006dcf1`: `pDriverPath`
- `0x18006dd31`: `pConfigFile`

## pseudocode

```c
__int64 __fastcall SaveParametersForUpgrade(
        unsigned __int16 *a1,
        unsigned int a2,
        int a3,
        unsigned __int8 *a4,
        unsigned int a5)
{
  unsigned int v5; // r14d
  HANDLE v9; // r15
  unsigned int v10; // eax
  int v11; // ecx
  HKEY v13; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int8 v14[8]; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int8 v15[8]; // [rsp+60h] [rbp-A0h] BYREF
  HKEY v16; // [rsp+68h] [rbp-98h] BYREF
  HKEY phkResult; // [rsp+70h] [rbp-90h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-88h] BYREF
  WCHAR SubKey[264]; // [rsp+80h] [rbp-80h] BYREF

  *(_DWORD *)v14 = a3;
  hKey = 0;
  v5 = 0;
  phkResult = 0;
  v16 = 0;
  v13 = 0;
  *(_DWORD *)v15 = a2;
  v9 = RevertToPrinterSelf();
  v10 = StringCchPrintfW(SubKey, 0x104u, L"Version-%d", a5);
  if ( (unsigned int)BoolFromHResult(v10)
    && !RegCreateKeyExW(
          HKEY_LOCAL_MACHINE,
          L"System\\CurrentControlSet\\Control\\Print",
          0,
          0,
          0,
          0x20006u,
          0,
          &hKey,
          0)
    && !RegCreateKeyExW(hKey, L"PendingUpgrades", 0, 0, 0, 0x20006u, 0, &phkResult, 0)
    && !RegCreateKeyExW(phkResult, SubKey, 0, 0, 0, 0x20006u, 0, &v16, 0)
    && !RegCreateKeyExW(v16, *((LPCWSTR *)a4 + 1), 0, 0, 0, 0x20006u, 0, &v13, 0) )
  {
    if ( *(_DWORD *)v14 == 101 )
    {
      v5 = SaveDriverVersionForUpgrade(v13, (struct _DRIVER_INFO_VERSION *)a4, a1, a2, a5);
      goto LABEL_43;
    }
    if ( !LocalRegSetValue(v13, L"SplName", 1u, (unsigned __int8 *)a1)
      && !LocalRegSetValue(v13, L"Level", 4u, v14)
      && !LocalRegSetValue(v13, L"DriverMoved", 4u, v15)
      && !LocalRegSetValue(v13, L"cVersion", 4u, (unsigned __int8 *)&a5)
      && !LocalRegSetValue(v13, L"pName", 1u, *((unsigned __int8 **)a4 + 1))
      && !LocalRegSetValue(v13, L"pEnvironment", 1u, *((unsigned __int8 **)a4 + 2))
      && !LocalRegSetValue(v13, L"pDriverPath", 1u, *((unsigned __int8 **)a4 + 3))
      && !LocalRegSetValue(v13, L"pDataFile", 1u, *((unsigned __int8 **)a4 + 4))
      && !LocalRegSetValue(v13, L"pConfigFile", 1u, *((unsigned __int8 **)a4 + 5)) )
    {
      if ( *(_DWORD *)v14 == 2 )
        goto LABEL_42;
      if ( !LocalRegSetValue(v13, L"pHelpFile", 1u, *((unsigned __int8 **)a4 + 6))
        && !LocalRegSetValue(v13, L"pDependentFiles", 7u, *((unsigned __int8 **)a4 + 7))
        && !LocalRegSetValue(v13, L"pMonitorName", 1u, *((unsigned __int8 **)a4 + 8))
        && !LocalRegSetValue(v13, L"pDefaultDataType", 1u, *((unsigned __int8 **)a4 + 9)) )
      {
        v11 = *(_DWORD *)v14;
        if ( ((*(_DWORD *)v14 - 4) & 0xFFFFFFF9) == 0 && *(_DWORD *)v14 != 10 )
        {
          if ( LocalRegSetValue(v13, L"pszzPreviousNames", 7u, *((unsigned __int8 **)a4 + 10)) )
            goto LABEL_43;
          v11 = *(_DWORD *)v14;
        }
        if ( ((v11 - 6) & 0xFFFFFFFD) != 0
          || !RegSetValueExW(v13, L"ftDriverDate", 0, 3u, a4 + 88, 8u)
          && !RegSetValueExW(v13, L"dwlDriverVersion", 0, 3u, a4 + 96, 8u)
          && !LocalRegSetValue(v13, L"pszMfgName", 1u, *((unsigned __int8 **)a4 + 13))
          && !LocalRegSetValue(v13, L"pszOEMUrl", 1u, *((unsigned __int8 **)a4 + 14))
          && !LocalRegSetValue(v13, L"pszHardwareID", 1u, *((unsigned __int8 **)a4 + 15))
          && !LocalRegSetValue(v13, L"pszProvider", 1u, *((unsigned __int8 **)a4 + 16))
          && (*(_DWORD *)v14 != 8
           || !LocalRegSetValue(v13, L"Print Processor", 1u, *((unsigned __int8 **)a4 + 17))
           && !LocalRegSetValue(v13, L"VendorSetup", 1u, *((unsigned __int8 **)a4 + 18))
           && !LocalRegSetValue(v13, L"ColorProfiles", 7u, *((unsigned __int8 **)a4 + 19))
           && !LocalRegSetValue(v13, L"InfPath", 1u, *((unsigned __int8 **)a4 + 20))
           && !LocalRegSetValue(v13, L"PrinterDriverAttributes", 4u, a4 + 168)
           && !LocalRegSetValue(v13, L"CoreDependencies", 7u, *((unsigned __int8 **)a4 + 22))
           && !RegSetValueExW(v13, L"MinInboxDriverVerDate", 0, 3u, a4 + 184, 8u)
           && !RegSetValueExW(v13, L"MinInboxDriverVerVersion", 0, 3u, a4 + 192, 8u)) )
        {
LABEL_42:
          v5 = 1;
        }
      }
    }
  }
LABEL_43:
  if ( v13 )
    RegCloseKey(v13);
  if ( v16 )
    RegCloseKey(v16);
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( hKey )
    RegCloseKey(hKey);
  if ( v9 )
    ImpersonatePrinterClient(v9);
  return v5;
}

```

## disassembly

```asm
0x18006da74  push    rbp
0x18006da76  push    rbx
0x18006da77  push    rsi
0x18006da78  push    rdi
0x18006da79  push    r12
0x18006da7b  push    r13
0x18006da7d  push    r14
0x18006da7f  push    r15
0x18006da81  lea     rbp, [rsp-1A8h]
0x18006da89  sub     rsp, 2A8h
0x18006da90  mov     rax, cs:__security_cookie
0x18006da97  xor     rax, rsp
0x18006da9a  mov     [rbp+1E0h+var_50], rax
0x18006daa1  xor     r12d, r12d
0x18006daa4  mov     dword ptr [rsp+2E0h+var_288], r8d
0x18006daa9  mov     [rsp+2E0h+hKey], r12
0x18006daae  mov     r14d, r12d
0x18006dab1  mov     [rsp+2E0h+var_270], r12
0x18006dab6  mov     rbx, r9
0x18006dab9  mov     [rsp+2E0h+var_278], r12
0x18006dabe  mov     esi, edx
0x18006dac0  mov     [rsp+2E0h+var_290], r12
0x18006dac5  mov     rdi, rcx
0x18006dac8  mov     dword ptr [rsp+2E0h+var_280], edx
0x18006dacc  call    cs:__imp_RevertToPrinterSelf
0x18006dad2  mov     r9d, dword ptr [rbp+1E0h+arg_20]
0x18006dad9  lea     r8, aVersionD; "Version-%d"
0x18006dae0  mov     edx, 104h; unsigned __int64
0x18006dae5  lea     rcx, [rbp+1E0h+SubKey]; unsigned __int16 *
0x18006dae9  mov     r15, rax
0x18006daec  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18006daf1  mov     ecx, eax
0x18006daf3  call    BoolFromHResult
0x18006daf8  test    eax, eax
0x18006dafa  jz      loc_18006E039
0x18006db00  mov     [rsp+2E0h+lpdwDisposition], r12; lpdwDisposition
0x18006db05  lea     rax, [rsp+2E0h+hKey]
0x18006db0a  mov     [rsp+2E0h+phkResult], rax; phkResult
0x18006db0f  lea     rdx, szRegistryRoot; "System\\CurrentControlSet\\Control\\Pri"...
0x18006db16  mov     [rsp+2E0h+lpSecurityAttributes], r12; lpSecurityAttributes
0x18006db1b  mov     r13d, 20006h
0x18006db21  mov     [rsp+2E0h+samDesired], r13d; samDesired
0x18006db26  xor     r9d, r9d; lpClass
0x18006db29  xor     r8d, r8d; Reserved
0x18006db2c  mov     [rsp+2E0h+dwOptions], r12d; dwOptions
0x18006db31  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18006db38  call    cs:__imp_RegCreateKeyExW
0x18006db3e  test    eax, eax
0x18006db40  jnz     loc_18006E039
0x18006db46  mov     rcx, [rsp+2E0h+hKey]; hKey
0x18006db4b  lea     rax, [rsp+2E0h+var_270]
0x18006db50  mov     [rsp+2E0h+lpdwDisposition], r12; lpdwDisposition
0x18006db55  lea     rdx, szPendingUpgrades; "PendingUpgrades"
0x18006db5c  mov     [rsp+2E0h+phkResult], rax; phkResult
0x18006db61  xor     r9d, r9d; lpClass
0x18006db64  mov     [rsp+2E0h+lpSecurityAttributes], r12; lpSecurityAttributes
0x18006db69  xor     r8d, r8d; Reserved
0x18006db6c  mov     [rsp+2E0h+samDesired], r13d; samDesired
0x18006db71  mov     [rsp+2E0h+dwOptions], r12d; dwOptions
0x18006db76  call    cs:__imp_RegCreateKeyExW
0x18006db7c  test    eax, eax
0x18006db7e  jnz     loc_18006E039
0x18006db84  mov     rcx, [rsp+2E0h+var_270]; hKey
0x18006db89  lea     rax, [rsp+2E0h+var_278]
0x18006db8e  mov     [rsp+2E0h+lpdwDisposition], r12; lpdwDisposition
0x18006db93  lea     rdx, [rbp+1E0h+SubKey]; lpSubKey
0x18006db97  mov     [rsp+2E0h+phkResult], rax; phkResult
0x18006db9c  xor     r9d, r9d; lpClass
0x18006db9f  mov     [rsp+2E0h+lpSecurityAttributes], r12; lpSecurityAttributes
0x18006dba4  xor     r8d, r8d; Reserved
0x18006dba7  mov     [rsp+2E0h+samDesired], r13d; samDesired
0x18006dbac  mov     [rsp+2E0h+dwOptions], r12d; dwOptions
0x18006dbb1  call    cs:__imp_RegCreateKeyExW
0x18006dbb7  test    eax, eax
0x18006dbb9  jnz     loc_18006E039
0x18006dbbf  mov     rdx, [rbx+8]; lpSubKey
0x18006dbc3  lea     rax, [rsp+2E0h+var_290]
0x18006dbc8  mov     rcx, [rsp+2E0h+var_278]; hKey
0x18006dbcd  xor     r9d, r9d; lpClass
0x18006dbd0  mov     [rsp+2E0h+lpdwDisposition], r12; lpdwDisposition
0x18006dbd5  xor     r8d, r8d; Reserved
0x18006dbd8  mov     [rsp+2E0h+phkResult], rax; phkResult
0x18006dbdd  mov     [rsp+2E0h+lpSecurityAttributes], r12; lpSecurityAttributes
0x18006dbe2  mov     [rsp+2E0h+samDesired], r13d; samDesired
0x18006dbe7  mov     [rsp+2E0h+dwOptions], r12d; dwOptions
0x18006dbec  call    cs:__imp_RegCreateKeyExW
0x18006dbf2  test    eax, eax
0x18006dbf4  jnz     loc_18006E039
0x18006dbfa  cmp     dword ptr [rsp+2E0h+var_288], 65h ; 'e'
0x18006dbff  mov     rcx, [rsp+2E0h+var_290]; hKey
0x18006dc04  jnz     short loc_18006DC26
0x18006dc06  mov     eax, dword ptr [rbp+1E0h+arg_20]
0x18006dc0c  mov     r9d, esi; unsigned int
0x18006dc0f  mov     r8, rdi; unsigned __int16 *
0x18006dc12  mov     [rsp+2E0h+dwOptions], eax; unsigned int
0x18006dc16  mov     rdx, rbx; struct _DRIVER_INFO_VERSION *
0x18006dc19  call    ?SaveDriverVersionForUpgrade@@YAHPEAXPEAU_DRIVER_INFO_VERSION@@PEAGKK@Z; SaveDriverVersionForUpgrade(void *,_DRIVER_INFO_VERSION *,ushort *,ulong,ulong)
0x18006dc1e  mov     r14d, eax
0x18006dc21  jmp     loc_18006E039
0x18006dc26  mov     r9, rdi; unsigned __int8 *
0x18006dc29  lea     rdx, aSplname; "SplName"
0x18006dc30  mov     edi, 1
0x18006dc35  mov     r8d, edi; dwType
0x18006dc38  call    ?LocalRegSetValue@@YAKPEAXPEBGKPEAE@Z; LocalRegSetValue(void *,ushort const *,ulong,uchar *)
0x18006dc3d  test    eax, eax
0x18006dc3f  jnz     loc_18006E039
0x18006dc45  mov     rcx, [rsp+2E0h+var_290]; hKey
0x18006dc4a  lea     esi, [rdi+3]
0x18006dc4d  mov     r8d, esi; dwType
0x18006dc50  lea     r9, [rsp+2E0h+var_288]; unsigned __int8 *
0x18006dc55  lea     rdx, aLevel; "Level"
0x18006dc5c  call    ?LocalRegSetValue@@YAKPEAXPEBGKPEAE@Z; LocalRegSetValue(void *,ushort const *,ulong,uchar *)
0x18006dc61  test    eax, eax
0x18006dc63  jnz     loc_18006E039
0x18006dc69  mov     rcx, [rsp+2E0h+var_290]; hKey
0x18006dc6e  lea     r9, [rsp+2E0h+var_280]; unsigned __int8 *
0x18006dc73  mov     r8d, esi; dwType
0x18006dc76  lea     rdx, aDrivermoved; "DriverMoved"
0x18006dc7d  call    ?LocalRegSetValue@@YAKPEAXPEBGKPEAE@Z; LocalRegSetValue(void *,ushort const *,ulong,uchar *)
0x18006dc82  test    eax, eax
0x18006dc84  jnz     loc_18006E039
0x18006dc8a  mov     rcx, [rsp+2E0h+var_290]; hKey
0x18006dc8f  lea     r9, [rbp+1E0h+arg_20]; unsigned __int8 *
0x18006dc96  mov     r8d, esi; dwType
0x18006dc99  lea     rdx, aCversion; "cVersion"
0x18006dca0  call    ?LocalRegSetValue@@YAKPEAXPEBGKPEAE@Z; LocalRegSetValue(void *,ushort const *,ulong,uchar *)
0x18006dca5  test    eax, eax
0x18006dca7  jnz     loc_18006E039
0x18006dcad  mov     r9, [rbx+8]; unsigned __int8 *
0x18006dcb1  lea     rdx, aPname; "pName"
0x18006dcb8  mov     rcx, [rsp+2E0h+var_290]; hKey
0x18006dcbd  mov     r8d, edi; dwType
0x18006dcc0  call    ?LocalRegSetValue@@YAKPEAXPEBGKPEAE@Z; LocalRegSetValue(void *,ushort const *,ulong,uchar *)
0x18006dcc5  test    eax, eax
0x18006dcc7  jnz     loc_18006E039
0x18006dccd  mov     r9, [rbx+10h]; unsigned __int8 *
0x18006dcd1  lea     rdx, aPenvironment; "pEnvironment"
0x18006dcd8  mov     rcx, [rsp+2E0h+var_290]; hKey
0x18006dcdd  mov     r8d, edi; dwType
0x18006dce0  call    ?LocalRegSetValue@@YAKPEAXPEBGKPEAE@Z; LocalRegSetValue(void *,ushort const *,ulong,uchar *)
0x18006dce5  test    eax, eax
0x18006dce7  jnz     loc_18006E039
0x18006dced  mov     r9, [rbx+18h]; unsigned __int8 *
0x18006dcf1  lea     rdx, aPdriverpath; "pDriverPath"
0x18006dcf8  mov     rcx, [rsp+2E0h+var_290]; hKey
0x18006dcfd  mov     r8d, edi; dwType
0x18006dd00  call    ?LocalRegSetValue@@YAKPEAXPEBGKPEAE@Z; LocalRegSetValue(void *,ushort const *,ulong,uchar *)
0x18006dd05  test    eax, eax
0x18006dd07  jnz     loc_18006E039
0x18006dd0d  mov     r9, [rbx+20h]; unsigned __int8 *
0x18006dd11  lea     rdx, aPdatafile; "pDataFile"
0x18006dd18  mov     rcx, [rsp+2E0h+var_290]; hKey
0x18006dd1d  mov     r8d, edi; dwType
0x18006dd20  call    ?LocalRegSetValue@@YAKPEAXPEBGKPEAE@Z; LocalRegSetValue(void *,ushort const *,ulong,uchar *)
0x18006dd25  test    eax, eax
0x18006dd27  jnz     loc_18006E039
0x18006dd2d  mov     r9, [rbx+28h]; unsigned __int8 *
0x18006dd31  lea     rdx, aPconfigfile; "pConfigFile"
0x18006dd38  mov     rcx, [rsp+2E0h+var_290]; hKey
0x18006dd3d  mov     r8d, edi; dwType
0x18006dd40  call    ?LocalRegSetValue@@YAKPEAXPEBGKPEAE@Z; LocalRegSetValue(void *,ushort const *,ulong,uchar *)
0x18006dd45  test    eax, eax
0x18006dd47  jnz     loc_18006E039
0x18006dd4d  cmp     dword ptr [rsp+2E0h+var_288], 2
0x18006dd52  jz      loc_18006E036
0x18006dd58  mov     r9, [rbx+30h]; unsigned __int8 *
0x18006dd5c  lea     rdx, aPhelpfile; "pHelpFile"
0x18006dd63  mov     rcx, [rsp+2E0h+var_290]; hKey
0x18006dd68  mov     r8d, edi; dwType
0x18006dd6b  call    ?LocalRegSetValue@@YAKPEAXPEBGKPEAE@Z; LocalRegSetValue(void *,ushort const *,ulong,uchar *)
0x18006dd70  test    eax, eax
0x18006dd72  jnz     loc_18006E039
0x18006dd78  mov     r9, [rbx+38h]; unsigned __int8 *
0x18006dd7c  lea     r13d, [rdi+6]
0x18006dd80  mov     rcx, [rsp+2E0h+var_290]; hKey
0x18006dd85  lea     rdx, aPdependentfile_0; "pDependentFiles"
0x18006dd8c  mov     r8d, r13d; dwType
0x18006dd8f  call    ?LocalRegSetValue@@YAKPEAXPEBGKPEAE@Z; LocalRegSetValue(void *,ushort const *,ulong,uchar *)
0x18006dd94  test    eax, eax
0x18006dd96  jnz     loc_18006E039
0x18006dd9c  mov     r9, [rbx+40h]; unsigned __int8 *
0x18006dda0  lea     rdx, aPmonitorname; "pMonitorName"
0x18006dda7  mov     rcx, [rsp+2E0h+var_290]; hKey
0x18006ddac  mov     r8d, edi; dwType
0x18006ddaf  call    ?LocalRegSetValue@@YAKPEAXPEBGKPEAE@Z; LocalRegSetValue(void *,ushort const *,ulong,uchar *)
0x18006ddb4  test    eax, eax
0x18006ddb6  jnz     loc_18006E039
0x18006ddbc  mov     r9, [rbx+48h]; unsigned __int8 *
0x18006ddc0  lea     rdx, aPdefaultdataty; "pDefaultDataType"
0x18006ddc7  mov     rcx, [rsp+2E0h+var_290]; hKey
0x18006ddcc  mov     r8d, edi; dwType
0x18006ddcf  call    ?LocalRegSetValue@@YAKPEAXPEBGKPEAE@Z; LocalRegSetValue(void *,ushort const *,ulong,uchar *)
0x18006ddd4  test    eax, eax
0x18006ddd6  jnz     loc_18006E039
0x18006dddc  mov     ecx, dword ptr [rsp+2E0h+var_288]
0x18006dde0  lea     eax, [rcx-4]
0x18006dde3  test    eax, 0FFFFFFF9h
0x18006dde8  jnz     short loc_18006DE13
0x18006ddea  cmp     ecx, 0Ah
0x18006dded  jz      short loc_18006DE13
0x18006ddef  mov     r9, [rbx+50h]; unsigned __int8 *
0x18006ddf3  lea     rdx, aPszzpreviousna; "pszzPreviousNames"
0x18006ddfa  mov     rcx, [rsp+2E0h+var_290]; hKey
0x18006ddff  mov     r8d, r13d; dwType
0x18006de02  call    ?LocalRegSetValue@@YAKPEAXPEBGKPEAE@Z; LocalRegSetValue(void *,ushort const *,ulong,uchar *)
0x18006de07  test    eax, eax
0x18006de09  jnz     loc_18006E039
0x18006de0f  mov     ecx, dword ptr [rsp+2E0h+var_288]
0x18006de13  lea     eax, [rcx-6]
0x18006de16  test    eax, 0FFFFFFFDh
0x18006de1b  jnz     loc_18006E036
0x18006de21  mov     rcx, [rsp+2E0h+var_290]; hKey
0x18006de26  lea     rax, [rbx+58h]
0x18006de2a  mov     esi, 8
0x18006de2f  lea     rdx, aFtdriverdate; "ftDriverDate"
0x18006de36  mov     [rsp+2E0h+samDesired], esi; cbData
0x18006de3a  xor     r8d, r8d; Reserved
0x18006de3d  mov     qword ptr [rsp+2E0h+dwOptions], rax; lpData
0x18006de42  lea     r9d, [rsi-5]; dwType
0x18006de46  call    cs:__imp_RegSetValueExW
0x18006de4c  test    eax, eax
0x18006de4e  jnz     loc_18006E039
0x18006de54  mov     rcx, [rsp+2E0h+var_290]; hKey
0x18006de59  lea     rax, [rbx+60h]
0x18006de5d  mov     [rsp+2E0h+samDesired], esi; cbData
0x18006de61  lea     r9d, [rsi-5]; dwType
0x18006de65  xor     r8d, r8d; Reserved
0x18006de68  mov     qword ptr [rsp+2E0h+dwOptions], rax; lpData
0x18006de6d  lea     rdx, aDwldriverversi; "dwlDriverVersion"
0x18006de74  call    cs:__imp_RegSetValueExW
0x18006de7a  test    eax, eax
0x18006de7c  jnz     loc_18006E039
0x18006de82  mov     r9, [rbx+68h]; unsigned __int8 *
0x18006de86  lea     rdx, aPszmfgname; "pszMfgName"
0x18006de8d  mov     rcx, [rsp+2E0h+var_290]; hKey
0x18006de92  mov     r8d, edi; dwType
0x18006de95  call    ?LocalRegSetValue@@YAKPEAXPEBGKPEAE@Z; LocalRegSetValue(void *,ushort const *,ulong,uchar *)
0x18006de9a  test    eax, eax
0x18006de9c  jnz     loc_18006E039
0x18006dea2  mov     r9, [rbx+70h]; unsigned __int8 *
0x18006dea6  lea     rdx, aPszoemurl; "pszOEMUrl"
0x18006dead  mov     rcx, [rsp+2E0h+var_290]; hKey
0x18006deb2  mov     r8d, edi; dwType
0x18006deb5  call    ?LocalRegSetValue@@YAKPEAXPEBGKPEAE@Z; LocalRegSetValue(void *,ushort const *,ulong,uchar *)
0x18006deba  test    eax, eax
0x18006debc  jnz     loc_18006E039
0x18006dec2  mov     r9, [rbx+78h]; unsigned __int8 *
0x18006dec6  lea     rdx, aPszhardwareid; "pszHardwareID"
0x18006decd  mov     rcx, [rsp+2E0h+var_290]; hKey
0x18006ded2  mov     r8d, edi; dwType
0x18006ded5  call    ?LocalRegSetValue@@YAKPEAXPEBGKPEAE@Z; LocalRegSetValue(void *,ushort const *,ulong,uchar *)
0x18006deda  test    eax, eax
0x18006dedc  jnz     loc_18006E039
0x18006dee2  mov     r9, [rbx+80h]; unsigned __int8 *
0x18006dee9  lea     rdx, aPszprovider; "pszProvider"
0x18006def0  mov     rcx, [rsp+2E0h+var_290]; hKey
0x18006def5  mov     r8d, edi; dwType
0x18006def8  call    ?LocalRegSetValue@@YAKPEAXPEBGKPEAE@Z; LocalRegSetValue(void *,ushort const *,ulong,uchar *)
0x18006defd  test    eax, eax
0x18006deff  jnz     loc_18006E039
0x18006df05  cmp     dword ptr [rsp+2E0h+var_288], esi
0x18006df09  jnz     loc_18006E036
0x18006df0f  mov     r9, [rbx+88h]; unsigned __int8 *
0x18006df16  lea     rdx, szPrintProcessor; "Print Processor"
0x18006df1d  mov     rcx, [rsp+2E0h+var_290]; hKey
0x18006df22  mov     r8d, edi; dwType
0x18006df25  call    ?LocalRegSetValue@@YAKPEAXPEBGKPEAE@Z; LocalRegSetValue(void *,ushort const *,ulong,uchar *)
0x18006df2a  test    eax, eax
0x18006df2c  jnz     loc_18006E039
0x18006df32  mov     r9, [rbx+90h]; unsigned __int8 *
0x18006df39  lea     rdx, szVendorSetup; "VendorSetup"
0x18006df40  mov     rcx, [rsp+2E0h+var_290]; hKey
0x18006df45  mov     r8d, edi; dwType
0x18006df48  call    ?LocalRegSetValue@@YAKPEAXPEBGKPEAE@Z; LocalRegSetValue(void *,ushort const *,ulong,uchar *)
0x18006df4d  test    eax, eax
0x18006df4f  jnz     loc_18006E039
0x18006df55  mov     r9, [rbx+98h]; unsigned __int8 *
0x18006df5c  lea     rdx, szColorProfiles; "ColorProfiles"
0x18006df63  mov     rcx, [rsp+2E0h+var_290]; hKey
0x18006df68  mov     r8d, r13d; dwType
0x18006df6b  call    ?LocalRegSetValue@@YAKPEAXPEBGKPEAE@Z; LocalRegSetValue(void *,ushort const *,ulong,uchar *)
0x18006df70  test    eax, eax
0x18006df72  jnz     loc_18006E039
0x18006df78  mov     r9, [rbx+0A0h]; unsigned __int8 *
0x18006df7f  lea     rdx, szInfPath; "InfPath"
0x18006df86  mov     rcx, [rsp+2E0h+var_290]; hKey
0x18006df8b  mov     r8d, edi; dwType
0x18006df8e  call    ?LocalRegSetValue@@YAKPEAXPEBGKPEAE@Z; LocalRegSetValue(void *,ushort const *,ulong,uchar *)
0x18006df93  test    eax, eax
0x18006df95  jnz     loc_18006E039
0x18006df9b  mov     rcx, [rsp+2E0h+var_290]; hKey
0x18006dfa0  lea     r9, [rbx+0A8h]; unsigned __int8 *
0x18006dfa7  lea     r8d, [rsi-4]; dwType
0x18006dfab  lea     rdx, szPrinterDriverAttributes; "PrinterDriverAttributes"
0x18006dfb2  call    ?LocalRegSetValue@@YAKPEAXPEBGKPEAE@Z; LocalRegSetValue(void *,ushort const *,ulong,uchar *)
0x18006dfb7  test    eax, eax
0x18006dfb9  jnz     short loc_18006E039
0x18006dfbb  mov     r9, [rbx+0B0h]; unsigned __int8 *
0x18006dfc2  lea     rdx, szCoreDependencies; "CoreDependencies"
0x18006dfc9  mov     rcx, [rsp+2E0h+var_290]; hKey
  ... truncated ...
```
