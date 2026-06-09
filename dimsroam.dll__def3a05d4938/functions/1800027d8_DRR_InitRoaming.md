# DRR_InitRoaming

- ea: `0x1800027d8`
- end: `0x180002f57`
- name: `DRR_InitRoaming`
- size: `1919`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180003300`

## callees

- `0x180001fcc`
- `0x1800027d8`
- `0x1800035cc`
- `0x1800035f4`
- `0x1800070b8`
- `0x180007110`
- `0x18000d8d0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800028f1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800029cc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180002a88`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180002ae8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180002b3d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800028f1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800029cc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180002a88`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180002ae8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180002b3d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800028b4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002986`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800028b4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180002986`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180002959`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180002959`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002905`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002f22`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002f38`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002905`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002f22`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180002f38`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002cb6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180002cb6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002eb4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002ec8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002edc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002ef0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002eb4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002ec8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002edc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002ef0`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180002c1a`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180002c1a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180002bbf`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180002bbf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180002ba5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180002ba5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180002c08`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180002c08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002bcd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002c24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002c76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002d18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002d66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002dd8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002e34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002bcd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002c24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002c76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002d18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002d66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002dd8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002e34`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180002c70`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180002d0e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180002c70`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180002d0e`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180002dce`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180002dce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002f09`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002f09`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180002d5c`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180002d5c`
- `DSROLE!DsRoleGetPrimaryDomainInformation` at `0x180002922`
- `DSROLE!DsRoleGetPrimaryDomainInformation` at `0x180002922`
- `DSROLE!DsRoleFreeMemory` at `0x18000293f`
- `DSROLE!DsRoleFreeMemory` at `0x18000293f`
- `CRYPTSP!CryptReleaseContext` at `0x180002ea7`
- `CRYPTSP!CryptReleaseContext` at `0x180002ea7`
- `CRYPTSP!CryptAcquireContextW` at `0x180002e26`
- `CRYPTSP!CryptAcquireContextW` at `0x180002e26`

## string_xrefs

- `0x180002b36`: `DIMSRoamingMaxNumTokens`
- `0x180002ae1`: `DIMSRoamingMaxTokenSize`

## pseudocode

```c
__int64 DRR_InitRoaming()
{
  int v0; // ebx
  BOOL v1; // ebx
  DWORD Value; // ebx
  _QWORD *v3; // rcx
  __int64 v4; // rdx
  __int64 v5; // r9
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  HANDLE CurrentProcess; // rax
  DWORD v11; // eax
  HLOCAL v12; // rax
  __int64 v13; // rax
  __int64 ReturnLength; // [rsp+30h] [rbp-40h] BYREF
  DWORD Type; // [rsp+38h] [rbp-38h] BYREF
  DWORD cbData[2]; // [rsp+40h] [rbp-30h] BYREF
  HKEY hkey; // [rsp+48h] [rbp-28h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-20h] BYREF
  SYSTEMTIME SystemTime; // [rsp+58h] [rbp-18h] BYREF

  LODWORD(ReturnLength) = 0;
  hkey = 0;
  ::hKey = 0;
  SystemTime = 0;
  qword_180013830 = 0;
  qword_180013838 = 0;
  *(_OWORD *)&xmmword_180013840 = 0;
  StringSid = 0;
  qword_180013858 = 0;
  Src = 0;
  qword_180013868 = 0;
  lpFileName = 0;
  hProv = 0;
  hMem = 0;
  dword_180013890 = 0;
  if ( !(unsigned int)myRetrieveLogLevel(-2147483647, L"LogLevel")
    && !(unsigned int)myRetrieveLogLevel(-2147483647, L"AEEventLogLevel") )
  {
    RetrieveLogLevel(-2147483646);
  }
  hKey = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\SafeBoot\\Option", 0, 1u, &hKey) )
  {
    Type = 0;
    HIDWORD(ReturnLength) = 0;
    v0 = 0;
    cbData[0] = 4;
    if ( !RegQueryValueExW(hKey, L"OptionValue", 0, &Type, (LPBYTE)&ReturnLength + 4, cbData) )
      LOBYTE(v0) = HIDWORD(ReturnLength) != 0;
    RegCloseKey(hKey);
    if ( v0 )
      goto LABEL_83;
  }
  *(_QWORD *)cbData = 0;
  v1 = 0;
  if ( !DsRoleGetPrimaryDomainInformation(0, DsRolePrimaryDomainInfoBasic, (PBYTE *)cbData) )
    v1 = (**(_DWORD **)cbData & 0xFFFFFFFD) != 0;
  if ( *(_QWORD *)cbData )
    DsRoleFreeMemory(*(PVOID *)cbData);
  if ( !v1 )
  {
LABEL_83:
    Value = 1351;
    goto LABEL_84;
  }
  Value = RegOpenCurrentUser(0xF003Fu, &::hKey);
  if ( !Value )
  {
    Value = RegOpenKeyExW(::hKey, L"SOFTWARE\\Policies\\Microsoft\\Cryptography\\AutoEnrollment", 0, 1u, &hkey);
    if ( Value )
    {
      v3 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_84;
      v4 = 21;
LABEL_19:
      v5 = Value;
LABEL_20:
      WPP_SF_D(v3[2], v4, WPP_2763c61a6d2e37b8ad9d1883579751d2_Traceguids, v5);
      goto LABEL_84;
    }
    LODWORD(hKey) = 0;
    Type = 0;
    cbData[0] = 0;
    ReturnLength = 4;
    Value = RegQueryValueExW(
              hkey,
              L"DIMSRoaming",
              0,
              (LPDWORD)&ReturnLength + 1,
              (LPBYTE)&qword_180013838 + 4,
              (LPDWORD)&ReturnLength);
    if ( Value )
    {
      v3 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_84;
      v4 = 17;
      goto LABEL_19;
    }
    if ( ReturnLength != 0x400000004LL )
    {
      Value = 13;
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_84;
      v7 = 18;
LABEL_79:
      WPP_SF_(v6[2], v7, WPP_2763c61a6d2e37b8ad9d1883579751d2_Traceguids);
      goto LABEL_84;
    }
    if ( (qword_180013838 & 0x4100000000LL) == 0 )
    {
      Value = 1058;
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_84;
      v7 = 19;
      goto LABEL_79;
    }
    LODWORD(ReturnLength) = 4;
    if ( RegQueryValueExW(
           hkey,
           L"DIMSRoamingTombstoneDays",
           0,
           (LPDWORD)&ReturnLength + 1,
           (LPBYTE)&hKey,
           (LPDWORD)&ReturnLength)
      || ReturnLength != 0x400000004LL
      || (unsigned int)((_DWORD)hKey - 1) > 0x9C3F )
    {
      LODWORD(qword_180013830) = 1440;
    }
    else
    {
      LODWORD(qword_180013830) = 24 * (_DWORD)hKey;
    }
    LODWORD(ReturnLength) = 4;
    if ( RegQueryValueExW(
           hkey,
           L"DIMSRoamingMaxTokenSize",
           0,
           (LPDWORD)&ReturnLength + 1,
           (LPBYTE)&Type,
           (LPDWORD)&ReturnLength)
      || ReturnLength != 0x400000004LL
      || (HIDWORD(qword_180013830) = Type, Type > 0x7FFFFFFF) )
    {
      HIDWORD(qword_180013830) = 0xFFFF;
    }
    LODWORD(ReturnLength) = 4;
    if ( RegQueryValueExW(
           hkey,
           L"DIMSRoamingMaxNumTokens",
           0,
           (LPDWORD)&ReturnLength + 1,
           (LPBYTE)cbData,
           (LPDWORD)&ReturnLength)
      || ReturnLength != 0x400000004LL
      || (LODWORD(qword_180013838) = cbData[0], cbData[0] > 0x3FFFFFFF) )
    {
      LODWORD(qword_180013838) = 2000;
    }
    Value = drr_GetCertPropIdsFromRegistry(hkey);
    if ( Value )
    {
      v3 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_84;
      v4 = 20;
      goto LABEL_19;
    }
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 8u, 1, &xmmword_180013840 + 1) )
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError != 1008 )
      {
        Value = LastError;
        v3 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_84;
        v4 = 22;
        goto LABEL_20;
      }
      CurrentProcess = GetCurrentProcess();
      if ( !OpenProcessToken(CurrentProcess, 8u, &xmmword_180013840 + 1) )
      {
        Value = GetLastError();
        v3 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_84;
        v4 = 23;
        goto LABEL_19;
      }
    }
    GetTokenInformation(*(&xmmword_180013840 + 1), TokenUser, 0, 0, (PDWORD)&ReturnLength);
    v11 = GetLastError();
    v5 = v11;
    if ( v11 != 122 )
    {
      Value = v11;
      v3 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_84;
      v4 = 24;
      goto LABEL_20;
    }
    v12 = LocalAlloc(0, (unsigned int)ReturnLength);
    xmmword_180013840 = v12;
    if ( !v12 )
    {
      Value = 14;
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_84;
      v7 = 25;
      goto LABEL_79;
    }
    if ( !GetTokenInformation(*(&xmmword_180013840 + 1), TokenUser, v12, ReturnLength, (PDWORD)&ReturnLength) )
    {
      Value = GetLastError();
      v3 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_84;
      v4 = 26;
      goto LABEL_19;
    }
    if ( !ConvertSidToStringSidW(*(PSID *)xmmword_180013840, &StringSid) )
    {
      Value = GetLastError();
      v3 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_84;
      v4 = 27;
      goto LABEL_19;
    }
    v13 = -1;
    do
      ++v13;
    while ( StringSid[v13] );
    qword_180013858 = v13;
    *(_DWORD *)&SystemTime.wYear = 67526;
    *(_QWORD *)&SystemTime.wDay = 1;
    SystemTime.wMilliseconds = 0;
    if ( !SystemTimeToFileTime(&SystemTime, &FileTime) )
    {
      Value = GetLastError();
      v3 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_84;
      v4 = 28;
      goto LABEL_19;
    }
    if ( CryptAcquireContextW(&hProv, 0, L"Microsoft Enhanced Cryptographic Provider v1.0", 1u, 0xF0000000) )
      goto LABEL_90;
    Value = GetLastError();
  }
LABEL_84:
  if ( hProv )
    CryptReleaseContext(hProv, 0);
  LocalFree(Src);
  Src = 0;
  LocalFree(StringSid);
  StringSid = 0;
  LocalFree(xmmword_180013840);
  xmmword_180013840 = 0;
  LocalFree(hMem);
  hMem = 0;
  if ( *(&xmmword_180013840 + 1) )
  {
    CloseHandle(*(&xmmword_180013840 + 1));
    *(&xmmword_180013840 + 1) = 0;
  }
  if ( ::hKey )
  {
    RegCloseKey(::hKey);
    ::hKey = 0;
  }
LABEL_90:
  if ( hkey )
    RegCloseKey(hkey);
  return Value;
}

```

## disassembly

```asm
0x1800027d8  push    rbp
0x1800027da  push    rbx
0x1800027db  push    rsi
0x1800027dc  push    rdi
0x1800027dd  push    r14
0x1800027df  mov     rbp, rsp
0x1800027e2  sub     rsp, 70h
0x1800027e6  mov     rax, cs:__security_cookie
0x1800027ed  xor     rax, rsp
0x1800027f0  mov     [rbp+var_8], rax
0x1800027f4  xor     edi, edi
0x1800027f6  lea     rdx, aLoglevel; "LogLevel"
0x1800027fd  xorps   xmm0, xmm0
0x180002800  mov     dword ptr [rbp+ReturnLength], edi
0x180002803  mov     rsi, 0FFFFFFFF80000001h
0x18000280a  mov     [rbp+hkey], rdi
0x18000280e  mov     rcx, rsi
0x180002811  mov     cs:hKey, rdi
0x180002818  movups  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x18000281c  mov     cs:qword_180013830, rdi
0x180002823  mov     cs:qword_180013838, rdi
0x18000282a  movdqa  cs:xmmword_180013840, xmm0
0x180002832  mov     cs:StringSid, rdi
0x180002839  mov     cs:qword_180013858, rdi
0x180002840  mov     cs:Src, rdi
0x180002847  mov     cs:qword_180013868, rdi
0x18000284e  mov     cs:lpFileName, rdi
0x180002855  mov     cs:hProv, rdi
0x18000285c  mov     cs:hMem, rdi
0x180002863  mov     cs:dword_180013890, edi
0x180002869  call    myRetrieveLogLevel
0x18000286e  lea     rbx, [rsi+1]
0x180002872  test    eax, eax
0x180002874  jnz     short loc_180002891
0x180002876  lea     rdx, aAeeventlogleve; "AEEventLogLevel"
0x18000287d  mov     rcx, rsi
0x180002880  call    myRetrieveLogLevel
0x180002885  test    eax, eax
0x180002887  jnz     short loc_180002891
0x180002889  mov     rcx, rbx
0x18000288c  call    _RetrieveLogLevel
0x180002891  lea     rax, [rbp+hKey]
0x180002895  mov     [rbp+hKey], rdi
0x180002899  mov     r14d, 1
0x18000289f  mov     [rsp+70h+phkResult], rax; phkResult
0x1800028a4  mov     r9d, r14d; samDesired
0x1800028a7  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Control\\Saf"...
0x1800028ae  xor     r8d, r8d; ulOptions
0x1800028b1  mov     rcx, rbx; hKey
0x1800028b4  call    cs:__imp_RegOpenKeyExW
0x1800028ba  lea     esi, [r14+3]
0x1800028be  test    eax, eax
0x1800028c0  jnz     short loc_180002913
0x1800028c2  mov     rcx, [rbp+hKey]; hKey
0x1800028c6  lea     rax, [rbp+cbData]
0x1800028ca  mov     [rsp+70h+lpcbData], rax; lpcbData
0x1800028cf  lea     r9, [rbp+Type]; lpType
0x1800028d3  lea     rax, [rbp+ReturnLength+4]
0x1800028d7  mov     [rbp+Type], edi
0x1800028da  xor     r8d, r8d; lpReserved
0x1800028dd  mov     [rsp+70h+phkResult], rax; lpData
0x1800028e2  lea     rdx, aOptionvalue; "OptionValue"
0x1800028e9  mov     dword ptr [rbp+ReturnLength+4], edi
0x1800028ec  mov     ebx, edi
0x1800028ee  mov     [rbp+cbData], esi
0x1800028f1  call    cs:__imp_RegQueryValueExW
0x1800028f7  test    eax, eax
0x1800028f9  jnz     short loc_180002901
0x1800028fb  cmp     dword ptr [rbp+ReturnLength+4], edi
0x1800028fe  setnz   bl
0x180002901  mov     rcx, [rbp+hKey]; hKey
0x180002905  call    cs:__imp_RegCloseKey
0x18000290b  test    ebx, ebx
0x18000290d  jnz     loc_180002E94
0x180002913  lea     r8, [rbp+cbData]; Buffer
0x180002917  mov     qword ptr [rbp+cbData], rdi
0x18000291b  mov     edx, r14d; InfoLevel
0x18000291e  xor     ecx, ecx; lpServer
0x180002920  mov     ebx, edi
0x180002922  call    cs:__imp_DsRoleGetPrimaryDomainInformation
0x180002928  mov     rcx, qword ptr [rbp+cbData]; Buffer
0x18000292c  test    eax, eax
0x18000292e  jnz     short loc_18000293A
0x180002930  test    dword ptr [rcx], 0FFFFFFFDh
0x180002936  cmovnz  ebx, r14d
0x18000293a  test    rcx, rcx
0x18000293d  jz      short loc_180002945
0x18000293f  call    cs:__imp_DsRoleFreeMemory
0x180002945  test    ebx, ebx
0x180002947  jz      loc_180002E94
0x18000294d  lea     rdx, hKey; phkResult
0x180002954  mov     ecx, 0F003Fh; samDesired
0x180002959  call    cs:__imp_RegOpenCurrentUser
0x18000295f  mov     ebx, eax
0x180002961  test    eax, eax
0x180002963  jnz     loc_180002E99
0x180002969  mov     rcx, cs:hKey; hKey
0x180002970  lea     rax, [rbp+hkey]
0x180002974  mov     r9d, r14d; samDesired
0x180002977  mov     [rsp+70h+phkResult], rax; phkResult
0x18000297c  xor     r8d, r8d; ulOptions
0x18000297f  lea     rdx, aSoftwarePolici; "SOFTWARE\\Policies\\Microsoft\\Cryptogr"...
0x180002986  call    cs:__imp_RegOpenKeyExW
0x18000298c  mov     ebx, eax
0x18000298e  test    eax, eax
0x180002990  jnz     loc_180002E71
0x180002996  mov     rcx, [rbp+hkey]; hKey
0x18000299a  lea     rax, [rbp+ReturnLength]
0x18000299e  mov     [rsp+70h+lpcbData], rax; lpcbData
0x1800029a3  lea     r9, [rbp+ReturnLength+4]; lpType
0x1800029a7  lea     rax, qword_180013838+4
0x1800029ae  mov     dword ptr [rbp+ReturnLength+4], edi
0x1800029b1  xor     r8d, r8d; lpReserved
0x1800029b4  mov     [rsp+70h+phkResult], rax; lpData
0x1800029b9  lea     rdx, aDimsroaming; "DIMSRoaming"
0x1800029c0  mov     dword ptr [rbp+hKey], edi
0x1800029c3  mov     [rbp+Type], edi
0x1800029c6  mov     [rbp+cbData], edi
0x1800029c9  mov     dword ptr [rbp+ReturnLength], esi
0x1800029cc  call    cs:__imp_RegQueryValueExW
0x1800029d2  mov     ebx, eax
0x1800029d4  test    eax, eax
0x1800029d6  jz      short loc_180002A16
0x1800029d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800029df  lea     rax, WPP_GLOBAL_Control
0x1800029e6  cmp     rcx, rax
0x1800029e9  jz      loc_180002E99
0x1800029ef  test    byte ptr [rcx+1Ch], 2
0x1800029f3  jz      loc_180002E99
0x1800029f9  mov     edx, 11h
0x1800029fe  mov     r9d, ebx
0x180002a01  mov     rcx, [rcx+10h]
0x180002a05  lea     r8, WPP_2763c61a6d2e37b8ad9d1883579751d2_Traceguids
0x180002a0c  call    WPP_SF_D
0x180002a11  jmp     loc_180002E99
0x180002a16  cmp     dword ptr [rbp+ReturnLength+4], esi
0x180002a19  jnz     loc_180002E3E
0x180002a1f  cmp     dword ptr [rbp+ReturnLength], esi
0x180002a22  jnz     loc_180002E3E
0x180002a28  test    byte ptr cs:qword_180013838+4, 41h
0x180002a2f  jnz     short loc_180002A61
0x180002a31  mov     ebx, 422h
0x180002a36  mov     rcx, cs:WPP_GLOBAL_Control
0x180002a3d  lea     rax, WPP_GLOBAL_Control
0x180002a44  cmp     rcx, rax
0x180002a47  jz      loc_180002E99
0x180002a4d  test    byte ptr [rcx+1Ch], 2
0x180002a51  jz      loc_180002E99
0x180002a57  mov     edx, 13h
0x180002a5c  jmp     loc_180002E5F
0x180002a61  mov     rcx, [rbp+hkey]; hKey
0x180002a65  lea     rax, [rbp+ReturnLength]
0x180002a69  mov     [rsp+70h+lpcbData], rax; lpcbData
0x180002a6e  lea     r9, [rbp+ReturnLength+4]; lpType
0x180002a72  lea     rax, [rbp+hKey]
0x180002a76  mov     dword ptr [rbp+ReturnLength], esi
0x180002a79  xor     r8d, r8d; lpReserved
0x180002a7c  mov     [rsp+70h+phkResult], rax; lpData
0x180002a81  lea     rdx, aDimsroamingtom; "DIMSRoamingTombstoneDays"
0x180002a88  call    cs:__imp_RegQueryValueExW
0x180002a8e  test    eax, eax
0x180002a90  jnz     short loc_180002AB7
0x180002a92  cmp     dword ptr [rbp+ReturnLength+4], esi
0x180002a95  jnz     short loc_180002AB7
0x180002a97  cmp     dword ptr [rbp+ReturnLength], esi
0x180002a9a  jnz     short loc_180002AB7
0x180002a9c  mov     ecx, dword ptr [rbp+hKey]
0x180002a9f  lea     eax, [rcx-1]
0x180002aa2  cmp     eax, 9C3Fh
0x180002aa7  ja      short loc_180002AB7
0x180002aa9  lea     eax, [rcx+rcx*2]
0x180002aac  shl     eax, 3
0x180002aaf  mov     dword ptr cs:qword_180013830, eax
0x180002ab5  jmp     short loc_180002AC1
0x180002ab7  mov     dword ptr cs:qword_180013830, 5A0h
0x180002ac1  mov     rcx, [rbp+hkey]; hKey
0x180002ac5  lea     rax, [rbp+ReturnLength]
0x180002ac9  mov     [rsp+70h+lpcbData], rax; lpcbData
0x180002ace  lea     r9, [rbp+ReturnLength+4]; lpType
0x180002ad2  lea     rax, [rbp+Type]
0x180002ad6  mov     dword ptr [rbp+ReturnLength], esi
0x180002ad9  xor     r8d, r8d; lpReserved
0x180002adc  mov     [rsp+70h+phkResult], rax; lpData
0x180002ae1  lea     rdx, aDimsroamingmax; "DIMSRoamingMaxTokenSize"
0x180002ae8  call    cs:__imp_RegQueryValueExW
0x180002aee  test    eax, eax
0x180002af0  jnz     short loc_180002B0C
0x180002af2  cmp     dword ptr [rbp+ReturnLength+4], esi
0x180002af5  jnz     short loc_180002B0C
0x180002af7  cmp     dword ptr [rbp+ReturnLength], esi
0x180002afa  jnz     short loc_180002B0C
0x180002afc  mov     eax, [rbp+Type]
0x180002aff  mov     dword ptr cs:qword_180013830+4, eax
0x180002b05  cmp     eax, 7FFFFFFFh
0x180002b0a  jbe     short loc_180002B16
0x180002b0c  mov     dword ptr cs:qword_180013830+4, 0FFFFh
0x180002b16  mov     rcx, [rbp+hkey]; hKey
0x180002b1a  lea     rax, [rbp+ReturnLength]
0x180002b1e  mov     [rsp+70h+lpcbData], rax; lpcbData
0x180002b23  lea     r9, [rbp+ReturnLength+4]; lpType
0x180002b27  lea     rax, [rbp+cbData]
0x180002b2b  mov     dword ptr [rbp+ReturnLength], esi
0x180002b2e  xor     r8d, r8d; lpReserved
0x180002b31  mov     [rsp+70h+phkResult], rax; lpData
0x180002b36  lea     rdx, aDimsroamingmax_0; "DIMSRoamingMaxNumTokens"
0x180002b3d  call    cs:__imp_RegQueryValueExW
0x180002b43  test    eax, eax
0x180002b45  jnz     short loc_180002B61
0x180002b47  cmp     dword ptr [rbp+ReturnLength+4], esi
0x180002b4a  jnz     short loc_180002B61
0x180002b4c  cmp     dword ptr [rbp+ReturnLength], esi
0x180002b4f  jnz     short loc_180002B61
0x180002b51  mov     eax, [rbp+cbData]
0x180002b54  mov     dword ptr cs:qword_180013838, eax
0x180002b5a  cmp     eax, 3FFFFFFFh
0x180002b5f  jbe     short loc_180002B6B
0x180002b61  mov     dword ptr cs:qword_180013838, 7D0h
0x180002b6b  mov     rcx, [rbp+hkey]; hkey
0x180002b6f  call    _drr_GetCertPropIdsFromRegistry
0x180002b74  mov     ebx, eax
0x180002b76  test    eax, eax
0x180002b78  jz      short loc_180002BA5
0x180002b7a  mov     rcx, cs:WPP_GLOBAL_Control
0x180002b81  lea     rax, WPP_GLOBAL_Control
0x180002b88  cmp     rcx, rax
0x180002b8b  jz      loc_180002E99
0x180002b91  test    byte ptr [rcx+1Ch], 2
0x180002b95  jz      loc_180002E99
0x180002b9b  mov     edx, 14h
0x180002ba0  jmp     loc_1800029FE
0x180002ba5  call    cs:__imp_GetCurrentThread
0x180002bab  mov     esi, 8
0x180002bb0  lea     r9, xmmword_180013840+8; TokenHandle
0x180002bb7  mov     rcx, rax; ThreadHandle
0x180002bba  mov     edx, esi; DesiredAccess
0x180002bbc  mov     r8d, r14d; OpenAsSelf
0x180002bbf  call    cs:__imp_OpenThreadToken
0x180002bc5  test    eax, eax
0x180002bc7  jnz     loc_180002C57
0x180002bcd  call    cs:__imp_GetLastError
0x180002bd3  mov     r9d, eax
0x180002bd6  cmp     eax, 3F0h
0x180002bdb  jz      short loc_180002C08
0x180002bdd  mov     ebx, eax
0x180002bdf  mov     rcx, cs:WPP_GLOBAL_Control
0x180002be6  lea     rax, WPP_GLOBAL_Control
0x180002bed  cmp     rcx, rax
0x180002bf0  jz      loc_180002E99
0x180002bf6  test    byte ptr [rcx+1Ch], 2
0x180002bfa  jz      loc_180002E99
0x180002c00  lea     edx, [rsi+0Eh]
0x180002c03  jmp     loc_180002A01
0x180002c08  call    cs:__imp_GetCurrentProcess
0x180002c0e  lea     r8, xmmword_180013840+8; TokenHandle
0x180002c15  mov     edx, esi; DesiredAccess
0x180002c17  mov     rcx, rax; ProcessHandle
0x180002c1a  call    cs:__imp_OpenProcessToken
0x180002c20  test    eax, eax
0x180002c22  jnz     short loc_180002C57
0x180002c24  call    cs:__imp_GetLastError
0x180002c2a  mov     ebx, eax
0x180002c2c  mov     rcx, cs:WPP_GLOBAL_Control
0x180002c33  lea     rax, WPP_GLOBAL_Control
0x180002c3a  cmp     rcx, rax
0x180002c3d  jz      loc_180002E99
0x180002c43  test    byte ptr [rcx+1Ch], 2
0x180002c47  jz      loc_180002E99
0x180002c4d  mov     edx, 17h
0x180002c52  jmp     loc_1800029FE
0x180002c57  mov     rcx, qword ptr cs:xmmword_180013840+8; TokenHandle
0x180002c5e  lea     rax, [rbp+ReturnLength]
0x180002c62  xor     r9d, r9d; TokenInformationLength
0x180002c65  mov     [rsp+70h+phkResult], rax; ReturnLength
0x180002c6a  xor     r8d, r8d; TokenInformation
0x180002c6d  mov     edx, r14d; TokenInformationClass
0x180002c70  call    cs:__imp_GetTokenInformation
0x180002c76  call    cs:__imp_GetLastError
0x180002c7c  mov     r9d, eax
0x180002c7f  cmp     eax, 7Ah ; 'z'
0x180002c82  jz      short loc_180002CB1
0x180002c84  mov     ebx, eax
0x180002c86  mov     rcx, cs:WPP_GLOBAL_Control
0x180002c8d  lea     rax, WPP_GLOBAL_Control
0x180002c94  cmp     rcx, rax
0x180002c97  jz      loc_180002E99
0x180002c9d  test    byte ptr [rcx+1Ch], 2
0x180002ca1  jz      loc_180002E99
0x180002ca7  mov     edx, 18h
0x180002cac  jmp     loc_180002A01
0x180002cb1  mov     edx, dword ptr [rbp+ReturnLength]; uBytes
0x180002cb4  xor     ecx, ecx; uFlags
0x180002cb6  call    cs:__imp_LocalAlloc
0x180002cbc  mov     qword ptr cs:xmmword_180013840, rax
0x180002cc3  test    rax, rax
0x180002cc6  jnz     short loc_180002CF4
0x180002cc8  lea     ebx, [rax+0Eh]
0x180002ccb  mov     rcx, cs:WPP_GLOBAL_Control
0x180002cd2  lea     rax, WPP_GLOBAL_Control
0x180002cd9  cmp     rcx, rax
0x180002cdc  jz      loc_180002E99
  ... truncated ...
```
