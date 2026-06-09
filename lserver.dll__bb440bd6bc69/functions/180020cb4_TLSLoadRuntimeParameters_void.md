# TLSLoadRuntimeParameters(void)

- ea: `0x180020cb4`
- end: `0x180021494`
- name: `?TLSLoadRuntimeParameters@@YAKXZ`
- size: `2016`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x180020790`

## callees

- `0x180005665`
- `0x180020cb4`
- `0x180022910`
- `0x180022fcc`
- `0x180065134`

## import_xrefs

- `ADVAPI32!RegCreateKeyExW` at `0x180020cff`
- `ADVAPI32!RegCreateKeyExW` at `0x180020cff`
- `ADVAPI32!RegQueryValueExW` at `0x180020d64`
- `ADVAPI32!RegQueryValueExW` at `0x180020da8`
- `ADVAPI32!RegQueryValueExW` at `0x180020deb`
- `ADVAPI32!RegQueryValueExW` at `0x180020e24`
- `ADVAPI32!RegQueryValueExW` at `0x180020e60`
- `ADVAPI32!RegQueryValueExW` at `0x180020e8f`
- `ADVAPI32!RegQueryValueExW` at `0x180020ecb`
- `ADVAPI32!RegQueryValueExW` at `0x180020f0d`
- `ADVAPI32!RegQueryValueExW` at `0x180020f49`
- `ADVAPI32!RegQueryValueExW` at `0x180020f78`
- `ADVAPI32!RegQueryValueExW` at `0x180020fb4`
- `ADVAPI32!RegQueryValueExW` at `0x180020fe3`
- `ADVAPI32!RegQueryValueExW` at `0x18002101f`
- `ADVAPI32!RegQueryValueExW` at `0x180021054`
- `ADVAPI32!RegQueryValueExW` at `0x180021091`
- `ADVAPI32!RegQueryValueExW` at `0x1800210ca`
- `ADVAPI32!RegQueryValueExW` at `0x18002116b`
- `ADVAPI32!RegQueryValueExW` at `0x1800211c0`
- `ADVAPI32!RegQueryValueExW` at `0x180021215`
- `ADVAPI32!RegQueryValueExW` at `0x1800212a3`
- `ADVAPI32!RegQueryValueExW` at `0x1800212f2`
- `ADVAPI32!RegQueryValueExW` at `0x18002135e`
- `ADVAPI32!RegQueryValueExW` at `0x1800213ad`
- `ADVAPI32!RegQueryValueExW` at `0x1800213fc`
- `ADVAPI32!RegQueryValueExW` at `0x18002144b`
- `ADVAPI32!RegQueryValueExW` at `0x180020d64`
- `ADVAPI32!RegQueryValueExW` at `0x180020da8`
- `ADVAPI32!RegQueryValueExW` at `0x180020deb`
- `ADVAPI32!RegQueryValueExW` at `0x180020e24`
- `ADVAPI32!RegQueryValueExW` at `0x180020e60`
- `ADVAPI32!RegQueryValueExW` at `0x180020e8f`
- `ADVAPI32!RegQueryValueExW` at `0x180020ecb`
- `ADVAPI32!RegQueryValueExW` at `0x180020f0d`
- `ADVAPI32!RegQueryValueExW` at `0x180020f49`
- `ADVAPI32!RegQueryValueExW` at `0x180020f78`
- `ADVAPI32!RegQueryValueExW` at `0x180020fb4`
- `ADVAPI32!RegQueryValueExW` at `0x180020fe3`
- `ADVAPI32!RegQueryValueExW` at `0x18002101f`
- `ADVAPI32!RegQueryValueExW` at `0x180021054`
- `ADVAPI32!RegQueryValueExW` at `0x180021091`
- `ADVAPI32!RegQueryValueExW` at `0x1800210ca`
- `ADVAPI32!RegQueryValueExW` at `0x18002116b`
- `ADVAPI32!RegQueryValueExW` at `0x1800211c0`
- `ADVAPI32!RegQueryValueExW` at `0x180021215`
- `ADVAPI32!RegQueryValueExW` at `0x1800212a3`
- `ADVAPI32!RegQueryValueExW` at `0x1800212f2`
- `ADVAPI32!RegQueryValueExW` at `0x18002135e`
- `ADVAPI32!RegQueryValueExW` at `0x1800213ad`
- `ADVAPI32!RegQueryValueExW` at `0x1800213fc`
- `ADVAPI32!RegQueryValueExW` at `0x18002144b`
- `ADVAPI32!RegCloseKey` at `0x18002147c`
- `ADVAPI32!RegCloseKey` at `0x18002147c`

## string_xrefs

- `0x180020ccb`: `SYSTEM\CurrentControlSet\Services\TermServLicensing\Parameters`
- `0x180020f03`: `IssueTemporaryLicenses`
- `0x180020f3d`: `IssueTemporaryLicenses`
- `0x180021038`: `MaxCacheSize`
- `0x180021391`: `ExpireThreadSleep`

## pseudocode

```c
__int64 TLSLoadRuntimeParameters(void)
{
  unsigned int v0; // eax
  unsigned int v1; // ebx
  int v2; // eax
  __int64 v3; // rcx
  unsigned int v4; // eax
  struct _EVENT_DESCRIPTOR v6; // [rsp+50h] [rbp-18h] BYREF
  DWORD cbData; // [rsp+90h] [rbp+28h] BYREF
  DWORD Type; // [rsp+98h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+A0h] [rbp+38h] BYREF
  unsigned __int16 *v10; // [rsp+A8h] [rbp+40h] BYREF

  hKey = 0;
  Type = 0;
  cbData = 0;
  v0 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Services\\TermServLicensing\\Parameters",
         0,
         0,
         0,
         0x20019u,
         0,
         &hKey,
         0);
  if ( v0 )
  {
    v6 = (struct _EVENT_DESCRIPTOR)TLS_E_SERVICEINIT;
    TLSLogEvent(&v6, 0xC0010014, v0);
    v1 = 4115;
    goto LABEL_73;
  }
  cbData = 4;
  if ( RegQueryValueExW(hKey, L"DefaultJobInterval", 0, 0, &g_dwTlsJobInterval, &cbData) )
    *(_DWORD *)&g_dwTlsJobInterval = 3600;
  cbData = 4;
  if ( RegQueryValueExW(hKey, L"DefaultJobRetryTimes", 0, 0, &g_dwTlsJobRetryTimes, &cbData) )
    *(_DWORD *)&g_dwTlsJobRetryTimes = 216000;
  cbData = 4;
  if ( RegQueryValueExW(hKey, L"DefaultJobRestartTime", 0, 0, &g_dwTlsJobRestartTime, &cbData) )
    *(_DWORD *)&g_dwTlsJobRestartTime = 3600;
  cbData = 4;
  if ( !RegQueryValueExW(hKey, L"Low License Warning", 0, &Type, 0, &cbData) && Type == 4 )
    RegQueryValueExW(hKey, L"Low License Warning", 0, &Type, &g_LowLicenseCountWarning, &cbData);
  cbData = 4;
  if ( !RegQueryValueExW(hKey, L"GracePeriod", 0, &Type, 0, &cbData) && Type == 4 )
    RegQueryValueExW(hKey, L"GracePeriod", 0, &Type, &g_GracePeriod, &cbData);
  if ( *(_DWORD *)&g_GracePeriod > 0x5Au )
    *(_DWORD *)&g_GracePeriod = 90;
  cbData = 4;
  if ( !RegQueryValueExW(hKey, L"IssueTemporaryLicenses", 0, &Type, 0, &cbData) && Type == 4 )
    RegQueryValueExW(hKey, L"IssueTemporaryLicenses", 0, &Type, &g_IssueTemporayLicense, &cbData);
  cbData = 4;
  if ( !RegQueryValueExW(hKey, L"Db ConnectionTimeout", 0, &Type, 0, &cbData) && Type == 4 )
    RegQueryValueExW(hKey, L"Db ConnectionTimeout", 0, &Type, &g_GeneralDbTimeout, &cbData);
  cbData = 4;
  if ( !RegQueryValueExW(hKey, L"Enum DbConnection Timeout", 0, &Type, 0, &cbData) && Type == 4 )
    RegQueryValueExW(hKey, L"Enum DbConnection Timeout", 0, &Type, &g_EnumDbTimeout, &cbData);
  cbData = 4;
  if ( RegQueryValueExW(hKey, L"MaxCacheSize", 0, 0, &g_EsentMaxCacheSize, &cbData)
    || (cbData = 4, RegQueryValueExW(hKey, L"StartFlushThreshold", 0, 0, &g_EsentStartFlushThreshold, &cbData))
    || (cbData = 4, RegQueryValueExW(hKey, L"StopFlushThreshold", 0, 0, &g_EsentStopFlushThreadhold, &cbData))
    || *(_DWORD *)&g_EsentStartFlushThreshold > *(_DWORD *)&g_EsentStopFlushThreadhold )
  {
    v2 = *(_DWORD *)&g_EsentMaxCacheSize;
  }
  else
  {
    v2 = *(_DWORD *)&g_EsentMaxCacheSize;
    if ( *(_DWORD *)&g_EsentStopFlushThreadhold <= *(_DWORD *)&g_EsentMaxCacheSize
      && *(_DWORD *)&g_EsentMaxCacheSize >= 0x40u
      && *(_DWORD *)&g_EsentStartFlushThreshold >= 0x10u
      && *(_DWORD *)&g_EsentStopFlushThreadhold >= 0x20u
      && *(_DWORD *)&g_EsentMaxCacheSize <= 0x200u
      && *(_DWORD *)&g_EsentStartFlushThreshold <= 0x64u
      && *(_DWORD *)&g_EsentStopFlushThreadhold <= 0x190u )
    {
      goto LABEL_41;
    }
  }
  if ( v2 != -1 )
  {
    *(_DWORD *)&g_EsentMaxCacheSize = 256;
    *(_DWORD *)&g_EsentStartFlushThreshold = 100;
    *(_DWORD *)&g_EsentStopFlushThreadhold = 200;
  }
LABEL_41:
  cbData = 4;
  if ( RegQueryValueExW(hKey, L"MaxVerPages", 0, 0, &g_EsentMaxVerPages, &cbData)
    || (unsigned int)(*(_DWORD *)&g_EsentMaxVerPages - 512) > 0x600 )
  {
    *(_DWORD *)&g_EsentMaxVerPages = 1024;
  }
  cbData = 4;
  v1 = RegQueryValueExW(hKey, L"Role", 0, 0, &g_SrvRole, &cbData);
  if ( (g_SrvRole & 1) != 0 )
  {
    cbData = 510;
    memset_0(&g_szScope, 0, 0x200u);
    if ( RegQueryValueExW(hKey, L"Scope", 0, &Type, &g_szScope, &cbData) )
      LoadResourceString(0x76u, (LPWSTR)&g_szScope, 256);
    g_pszScope = (unsigned __int16 *)&g_szScope;
  }
  else
  {
    v10 = 0;
    if ( !(unsigned int)GetMachineGroup(v3, &v10) )
    {
      v6 = (struct _EVENT_DESCRIPTOR)TLS_E_SERVICEINIT;
      TLSLogEvent(&v6, 0x23u);
      goto LABEL_73;
    }
    g_pszScope = v10;
  }
  cbData = 4;
  if ( RegQueryValueExW(hKey, L"LeaseMinimum", 0, 0, &g_dwReissueLeaseMinimum, &cbData)
    || *(_DWORD *)&g_dwReissueLeaseMinimum >= 0x448E00u )
  {
    *(_DWORD *)&g_dwReissueLeaseMinimum = 4492800;
  }
  cbData = 4;
  if ( RegQueryValueExW(hKey, L"LeaseRange", 0, 0, &g_dwReissueLeaseRange, &cbData) )
  {
    *(_DWORD *)&g_dwReissueLeaseRange = 3196800;
  }
  else
  {
    v4 = *(_DWORD *)&g_dwReissueLeaseRange;
    if ( *(_DWORD *)&g_dwReissueLeaseRange >= 0x30C780u )
    {
      v4 = 3196800;
      *(_DWORD *)&g_dwReissueLeaseRange = 3196800;
    }
    if ( v4 <= 1 )
      *(_DWORD *)&g_dwReissueLeaseRange = 1;
  }
  cbData = 4;
  if ( RegQueryValueExW(hKey, L"LeaseLeeway", 0, 0, &g_dwReissueLeaseLeeway, &cbData)
    || *(_DWORD *)&g_dwReissueLeaseLeeway >= 0x93A80u )
  {
    *(_DWORD *)&g_dwReissueLeaseLeeway = 604800;
  }
  cbData = 4;
  if ( RegQueryValueExW(hKey, L"ExpireThreadSleep", 0, 0, &g_dwReissueExpireThreadSleep, &cbData)
    || *(_DWORD *)&g_dwReissueExpireThreadSleep >= 0x5265C00u )
  {
    *(_DWORD *)&g_dwReissueExpireThreadSleep = 86400000;
  }
  cbData = 4;
  if ( RegQueryValueExW(hKey, L"LeaseMinimumPU", 0, 0, &g_dwReissueLeasePU, &cbData)
    || *(_DWORD *)&g_dwReissueLeasePU >= 0x4F1A00u )
  {
    *(_DWORD *)&g_dwReissueLeasePU = 5184000;
  }
  cbData = 4;
  if ( RegQueryValueExW(hKey, L"LeaseMinimumPUFailed", 0, 0, &g_dwLeasePUFailed, &cbData)
    || *(_DWORD *)&g_dwLeasePUFailed >= 0xED4E00u )
  {
    *(_DWORD *)&g_dwLeasePUFailed = 15552000;
  }
  v1 = 0;
LABEL_73:
  if ( hKey )
    RegCloseKey(hKey);
  return v1;
}

```

## disassembly

```asm
0x180020cb4  push    rbp
0x180020cb6  push    rbx
0x180020cb7  push    rsi
0x180020cb8  push    rdi
0x180020cb9  mov     rbp, rsp
0x180020cbc  sub     rsp, 68h
0x180020cc0  xor     edi, edi
0x180020cc2  lea     rax, [rbp+hKey]
0x180020cc6  mov     [rsp+68h+lpdwDisposition], rdi; lpdwDisposition
0x180020ccb  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\Te"...
0x180020cd2  mov     [rsp+68h+phkResult], rax; phkResult
0x180020cd7  xor     r9d, r9d; lpClass
0x180020cda  mov     [rsp+68h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x180020cdf  xor     r8d, r8d; Reserved
0x180020ce2  mov     [rsp+68h+samDesired], 20019h; samDesired
0x180020cea  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180020cf1  mov     [rsp+68h+dwOptions], edi; dwOptions
0x180020cf5  mov     [rbp+hKey], rdi
0x180020cf9  mov     [rbp+Type], edi
0x180020cfc  mov     [rbp+cbData], edi
0x180020cff  call    cs:__imp_RegCreateKeyExW
0x180020d06  nop     dword ptr [rax+rax+00h]
0x180020d0b  test    eax, eax
0x180020d0d  jz      short loc_180020D36
0x180020d0f  movups  xmm0, cs:TLS_E_SERVICEINIT
0x180020d16  mov     r8d, eax
0x180020d19  lea     rcx, [rbp+var_18]; struct _EVENT_DESCRIPTOR
0x180020d1d  mov     edx, 0C0010014h; unsigned int
0x180020d22  movdqu  xmmword ptr [rbp+var_18.Id], xmm0
0x180020d27  call    ?TLSLogEvent@@YAXU_EVENT_DESCRIPTOR@@KZZ; TLSLogEvent(_EVENT_DESCRIPTOR,ulong,...)
0x180020d2c  mov     ebx, 1013h
0x180020d31  jmp     loc_180021473
0x180020d36  mov     rcx, [rbp+hKey]; hKey
0x180020d3a  lea     rax, [rbp+cbData]
0x180020d3e  mov     qword ptr [rsp+68h+samDesired], rax; lpcbData
0x180020d43  lea     rdx, ValueName; "DefaultJobInterval"
0x180020d4a  lea     rax, ?g_dwTlsJobInterval@@3KA; ulong g_dwTlsJobInterval
0x180020d51  mov     esi, 4
0x180020d56  xor     r9d, r9d; lpType
0x180020d59  mov     qword ptr [rsp+68h+dwOptions], rax; lpData
0x180020d5e  xor     r8d, r8d; lpReserved
0x180020d61  mov     [rbp+cbData], esi
0x180020d64  call    cs:__imp_RegQueryValueExW
0x180020d6b  nop     dword ptr [rax+rax+00h]
0x180020d70  mov     ebx, 0E10h
0x180020d75  test    eax, eax
0x180020d77  jz      short loc_180020D7F
0x180020d79  mov     cs:?g_dwTlsJobInterval@@3KA, ebx; ulong g_dwTlsJobInterval
0x180020d7f  mov     rcx, [rbp+hKey]; hKey
0x180020d83  lea     rax, [rbp+cbData]
0x180020d87  mov     qword ptr [rsp+68h+samDesired], rax; lpcbData
0x180020d8c  lea     rdx, aDefaultjobretr; "DefaultJobRetryTimes"
0x180020d93  lea     rax, ?g_dwTlsJobRetryTimes@@3KA; ulong g_dwTlsJobRetryTimes
0x180020d9a  mov     [rbp+cbData], esi
0x180020d9d  xor     r9d, r9d; lpType
0x180020da0  mov     qword ptr [rsp+68h+dwOptions], rax; lpData
0x180020da5  xor     r8d, r8d; lpReserved
0x180020da8  call    cs:__imp_RegQueryValueExW
0x180020daf  nop     dword ptr [rax+rax+00h]
0x180020db4  test    eax, eax
0x180020db6  jz      short loc_180020DC2
0x180020db8  mov     cs:?g_dwTlsJobRetryTimes@@3KA, 34BC0h; ulong g_dwTlsJobRetryTimes
0x180020dc2  mov     rcx, [rbp+hKey]; hKey
0x180020dc6  lea     rax, [rbp+cbData]
0x180020dca  mov     qword ptr [rsp+68h+samDesired], rax; lpcbData
0x180020dcf  lea     rdx, aDefaultjobrest; "DefaultJobRestartTime"
0x180020dd6  lea     rax, ?g_dwTlsJobRestartTime@@3KA; ulong g_dwTlsJobRestartTime
0x180020ddd  mov     [rbp+cbData], esi
0x180020de0  xor     r9d, r9d; lpType
0x180020de3  mov     qword ptr [rsp+68h+dwOptions], rax; lpData
0x180020de8  xor     r8d, r8d; lpReserved
0x180020deb  call    cs:__imp_RegQueryValueExW
0x180020df2  nop     dword ptr [rax+rax+00h]
0x180020df7  test    eax, eax
0x180020df9  jz      short loc_180020E01
0x180020dfb  mov     cs:?g_dwTlsJobRestartTime@@3KA, ebx; ulong g_dwTlsJobRestartTime
0x180020e01  mov     rcx, [rbp+hKey]; hKey
0x180020e05  lea     rax, [rbp+cbData]
0x180020e09  mov     qword ptr [rsp+68h+samDesired], rax; lpcbData
0x180020e0e  lea     r9, [rbp+Type]; lpType
0x180020e12  xor     r8d, r8d; lpReserved
0x180020e15  mov     qword ptr [rsp+68h+dwOptions], rdi; lpData
0x180020e1a  lea     rdx, aLowLicenseWarn; "Low License Warning"
0x180020e21  mov     [rbp+cbData], esi
0x180020e24  call    cs:__imp_RegQueryValueExW
0x180020e2b  nop     dword ptr [rax+rax+00h]
0x180020e30  test    eax, eax
0x180020e32  jnz     short loc_180020E6C
0x180020e34  cmp     [rbp+Type], esi
0x180020e37  jnz     short loc_180020E6C
0x180020e39  mov     rcx, [rbp+hKey]; hKey
0x180020e3d  lea     rax, [rbp+cbData]
0x180020e41  mov     qword ptr [rsp+68h+samDesired], rax; lpcbData
0x180020e46  lea     r9, [rbp+Type]; lpType
0x180020e4a  lea     rax, ?g_LowLicenseCountWarning@@3KA; ulong g_LowLicenseCountWarning
0x180020e51  xor     r8d, r8d; lpReserved
0x180020e54  lea     rdx, aLowLicenseWarn; "Low License Warning"
0x180020e5b  mov     qword ptr [rsp+68h+dwOptions], rax; lpData
0x180020e60  call    cs:__imp_RegQueryValueExW
0x180020e67  nop     dword ptr [rax+rax+00h]
0x180020e6c  mov     rcx, [rbp+hKey]; hKey
0x180020e70  lea     rax, [rbp+cbData]
0x180020e74  mov     qword ptr [rsp+68h+samDesired], rax; lpcbData
0x180020e79  lea     r9, [rbp+Type]; lpType
0x180020e7d  xor     r8d, r8d; lpReserved
0x180020e80  mov     qword ptr [rsp+68h+dwOptions], rdi; lpData
0x180020e85  lea     rdx, aGraceperiod; "GracePeriod"
0x180020e8c  mov     [rbp+cbData], esi
0x180020e8f  call    cs:__imp_RegQueryValueExW
0x180020e96  nop     dword ptr [rax+rax+00h]
0x180020e9b  test    eax, eax
0x180020e9d  jnz     short loc_180020ED7
0x180020e9f  cmp     [rbp+Type], esi
0x180020ea2  jnz     short loc_180020ED7
0x180020ea4  mov     rcx, [rbp+hKey]; hKey
0x180020ea8  lea     rax, [rbp+cbData]
0x180020eac  mov     qword ptr [rsp+68h+samDesired], rax; lpcbData
0x180020eb1  lea     r9, [rbp+Type]; lpType
0x180020eb5  lea     rax, ?g_GracePeriod@@3KA; ulong g_GracePeriod
0x180020ebc  xor     r8d, r8d; lpReserved
0x180020ebf  lea     rdx, aGraceperiod; "GracePeriod"
0x180020ec6  mov     qword ptr [rsp+68h+dwOptions], rax; lpData
0x180020ecb  call    cs:__imp_RegQueryValueExW
0x180020ed2  nop     dword ptr [rax+rax+00h]
0x180020ed7  cmp     cs:?g_GracePeriod@@3KA, 5Ah ; 'Z'; ulong g_GracePeriod
0x180020ede  jbe     short loc_180020EEA
0x180020ee0  mov     cs:?g_GracePeriod@@3KA, 5Ah ; 'Z'; ulong g_GracePeriod
0x180020eea  mov     rcx, [rbp+hKey]; hKey
0x180020eee  lea     rax, [rbp+cbData]
0x180020ef2  mov     qword ptr [rsp+68h+samDesired], rax; lpcbData
0x180020ef7  lea     r9, [rbp+Type]; lpType
0x180020efb  xor     r8d, r8d; lpReserved
0x180020efe  mov     qword ptr [rsp+68h+dwOptions], rdi; lpData
0x180020f03  lea     rdx, aIssuetemporary; "IssueTemporaryLicenses"
0x180020f0a  mov     [rbp+cbData], esi
0x180020f0d  call    cs:__imp_RegQueryValueExW
0x180020f14  nop     dword ptr [rax+rax+00h]
0x180020f19  test    eax, eax
0x180020f1b  jnz     short loc_180020F55
0x180020f1d  cmp     [rbp+Type], esi
0x180020f20  jnz     short loc_180020F55
0x180020f22  mov     rcx, [rbp+hKey]; hKey
0x180020f26  lea     rax, [rbp+cbData]
0x180020f2a  mov     qword ptr [rsp+68h+samDesired], rax; lpcbData
0x180020f2f  lea     r9, [rbp+Type]; lpType
0x180020f33  lea     rax, ?g_IssueTemporayLicense@@3HA; int g_IssueTemporayLicense
0x180020f3a  xor     r8d, r8d; lpReserved
0x180020f3d  lea     rdx, aIssuetemporary; "IssueTemporaryLicenses"
0x180020f44  mov     qword ptr [rsp+68h+dwOptions], rax; lpData
0x180020f49  call    cs:__imp_RegQueryValueExW
0x180020f50  nop     dword ptr [rax+rax+00h]
0x180020f55  mov     rcx, [rbp+hKey]; hKey
0x180020f59  lea     rax, [rbp+cbData]
0x180020f5d  mov     qword ptr [rsp+68h+samDesired], rax; lpcbData
0x180020f62  lea     r9, [rbp+Type]; lpType
0x180020f66  xor     r8d, r8d; lpReserved
0x180020f69  mov     qword ptr [rsp+68h+dwOptions], rdi; lpData
0x180020f6e  lea     rdx, aDbConnectionti; "Db ConnectionTimeout"
0x180020f75  mov     [rbp+cbData], esi
0x180020f78  call    cs:__imp_RegQueryValueExW
0x180020f7f  nop     dword ptr [rax+rax+00h]
0x180020f84  test    eax, eax
0x180020f86  jnz     short loc_180020FC0
0x180020f88  cmp     [rbp+Type], esi
0x180020f8b  jnz     short loc_180020FC0
0x180020f8d  mov     rcx, [rbp+hKey]; hKey
0x180020f91  lea     rax, [rbp+cbData]
0x180020f95  mov     qword ptr [rsp+68h+samDesired], rax; lpcbData
0x180020f9a  lea     r9, [rbp+Type]; lpType
0x180020f9e  lea     rax, ?g_GeneralDbTimeout@@3KA; ulong g_GeneralDbTimeout
0x180020fa5  xor     r8d, r8d; lpReserved
0x180020fa8  lea     rdx, aDbConnectionti; "Db ConnectionTimeout"
0x180020faf  mov     qword ptr [rsp+68h+dwOptions], rax; lpData
0x180020fb4  call    cs:__imp_RegQueryValueExW
0x180020fbb  nop     dword ptr [rax+rax+00h]
0x180020fc0  mov     rcx, [rbp+hKey]; hKey
0x180020fc4  lea     rax, [rbp+cbData]
0x180020fc8  mov     qword ptr [rsp+68h+samDesired], rax; lpcbData
0x180020fcd  lea     r9, [rbp+Type]; lpType
0x180020fd1  xor     r8d, r8d; lpReserved
0x180020fd4  mov     qword ptr [rsp+68h+dwOptions], rdi; lpData
0x180020fd9  lea     rdx, aEnumDbconnecti; "Enum DbConnection Timeout"
0x180020fe0  mov     [rbp+cbData], esi
0x180020fe3  call    cs:__imp_RegQueryValueExW
0x180020fea  nop     dword ptr [rax+rax+00h]
0x180020fef  test    eax, eax
0x180020ff1  jnz     short loc_18002102B
0x180020ff3  cmp     [rbp+Type], esi
0x180020ff6  jnz     short loc_18002102B
0x180020ff8  mov     rcx, [rbp+hKey]; hKey
0x180020ffc  lea     rax, [rbp+cbData]
0x180021000  mov     qword ptr [rsp+68h+samDesired], rax; lpcbData
0x180021005  lea     r9, [rbp+Type]; lpType
0x180021009  lea     rax, ?g_EnumDbTimeout@@3KA; ulong g_EnumDbTimeout
0x180021010  xor     r8d, r8d; lpReserved
0x180021013  lea     rdx, aEnumDbconnecti; "Enum DbConnection Timeout"
0x18002101a  mov     qword ptr [rsp+68h+dwOptions], rax; lpData
0x18002101f  call    cs:__imp_RegQueryValueExW
0x180021026  nop     dword ptr [rax+rax+00h]
0x18002102b  mov     rcx, [rbp+hKey]; hKey
0x18002102f  lea     rax, [rbp+cbData]
0x180021033  mov     qword ptr [rsp+68h+samDesired], rax; lpcbData
0x180021038  lea     rdx, aMaxcachesize; "MaxCacheSize"
0x18002103f  lea     rax, ?g_EsentMaxCacheSize@@3KA; ulong g_EsentMaxCacheSize
0x180021046  mov     [rbp+cbData], esi
0x180021049  xor     r9d, r9d; lpType
0x18002104c  mov     qword ptr [rsp+68h+dwOptions], rax; lpData
0x180021051  xor     r8d, r8d; lpReserved
0x180021054  call    cs:__imp_RegQueryValueExW
0x18002105b  nop     dword ptr [rax+rax+00h]
0x180021060  test    eax, eax
0x180021062  jnz     loc_180021119
0x180021068  mov     rcx, [rbp+hKey]; hKey
0x18002106c  lea     rax, [rbp+cbData]
0x180021070  mov     qword ptr [rsp+68h+samDesired], rax; lpcbData
0x180021075  lea     rdx, aStartflushthre; "StartFlushThreshold"
0x18002107c  lea     rax, ?g_EsentStartFlushThreshold@@3KA; ulong g_EsentStartFlushThreshold
0x180021083  mov     [rbp+cbData], esi
0x180021086  xor     r9d, r9d; lpType
0x180021089  mov     qword ptr [rsp+68h+dwOptions], rax; lpData
0x18002108e  xor     r8d, r8d; lpReserved
0x180021091  call    cs:__imp_RegQueryValueExW
0x180021098  nop     dword ptr [rax+rax+00h]
0x18002109d  test    eax, eax
0x18002109f  jnz     short loc_180021119
0x1800210a1  mov     rcx, [rbp+hKey]; hKey
0x1800210a5  lea     rax, [rbp+cbData]
0x1800210a9  mov     qword ptr [rsp+68h+samDesired], rax; lpcbData
0x1800210ae  lea     rdx, aStopflushthres; "StopFlushThreshold"
0x1800210b5  lea     rax, ?g_EsentStopFlushThreadhold@@3KA; ulong g_EsentStopFlushThreadhold
0x1800210bc  mov     [rbp+cbData], esi
0x1800210bf  xor     r9d, r9d; lpType
0x1800210c2  mov     qword ptr [rsp+68h+dwOptions], rax; lpData
0x1800210c7  xor     r8d, r8d; lpReserved
0x1800210ca  call    cs:__imp_RegQueryValueExW
0x1800210d1  nop     dword ptr [rax+rax+00h]
0x1800210d6  test    eax, eax
0x1800210d8  jnz     short loc_180021119
0x1800210da  mov     edx, cs:?g_EsentStartFlushThreshold@@3KA; ulong g_EsentStartFlushThreshold
0x1800210e0  mov     ecx, cs:?g_EsentStopFlushThreadhold@@3KA; ulong g_EsentStopFlushThreadhold
0x1800210e6  cmp     edx, ecx
0x1800210e8  ja      short loc_180021119
0x1800210ea  mov     eax, cs:?g_EsentMaxCacheSize@@3KA; ulong g_EsentMaxCacheSize
0x1800210f0  cmp     ecx, eax
0x1800210f2  ja      short loc_18002111F
0x1800210f4  cmp     eax, 40h ; '@'
0x1800210f7  jb      short loc_18002111F
0x1800210f9  cmp     edx, 10h
0x1800210fc  jb      short loc_18002111F
0x1800210fe  cmp     ecx, 20h ; ' '
0x180021101  jb      short loc_18002111F
0x180021103  cmp     eax, 200h
0x180021108  ja      short loc_18002111F
0x18002110a  cmp     edx, 64h ; 'd'
0x18002110d  ja      short loc_18002111F
0x18002110f  cmp     ecx, 190h
0x180021115  jbe     short loc_180021142
0x180021117  jmp     short loc_18002111F
0x180021119  mov     eax, cs:?g_EsentMaxCacheSize@@3KA; ulong g_EsentMaxCacheSize
0x18002111f  cmp     eax, 0FFFFFFFFh
0x180021122  jz      short loc_180021142
0x180021124  mov     cs:?g_EsentMaxCacheSize@@3KA, 100h; ulong g_EsentMaxCacheSize
0x18002112e  mov     cs:?g_EsentStartFlushThreshold@@3KA, 64h ; 'd'; ulong g_EsentStartFlushThreshold
0x180021138  mov     cs:?g_EsentStopFlushThreadhold@@3KA, 0C8h; ulong g_EsentStopFlushThreadhold
0x180021142  mov     rcx, [rbp+hKey]; hKey
0x180021146  lea     rax, [rbp+cbData]
0x18002114a  mov     qword ptr [rsp+68h+samDesired], rax; lpcbData
0x18002114f  lea     rdx, aMaxverpages; "MaxVerPages"
0x180021156  lea     rax, ?g_EsentMaxVerPages@@3KA; ulong g_EsentMaxVerPages
0x18002115d  mov     [rbp+cbData], esi
0x180021160  xor     r9d, r9d; lpType
0x180021163  mov     qword ptr [rsp+68h+dwOptions], rax; lpData
0x180021168  xor     r8d, r8d; lpReserved
0x18002116b  call    cs:__imp_RegQueryValueExW
0x180021172  nop     dword ptr [rax+rax+00h]
0x180021177  test    eax, eax
0x180021179  jnz     short loc_18002118D
0x18002117b  mov     eax, cs:?g_EsentMaxVerPages@@3KA; ulong g_EsentMaxVerPages
0x180021181  add     eax, 0FFFFFE00h
0x180021186  cmp     eax, 600h
0x18002118b  jbe     short loc_180021197
0x18002118d  mov     cs:?g_EsentMaxVerPages@@3KA, 400h; ulong g_EsentMaxVerPages
0x180021197  mov     rcx, [rbp+hKey]; hKey
0x18002119b  lea     rax, [rbp+cbData]
0x18002119f  mov     qword ptr [rsp+68h+samDesired], rax; lpcbData
0x1800211a4  lea     rdx, aRole; "Role"
0x1800211ab  lea     rax, ?g_SrvRole@@3KA; ulong g_SrvRole
0x1800211b2  mov     [rbp+cbData], esi
0x1800211b5  xor     r9d, r9d; lpType
0x1800211b8  mov     qword ptr [rsp+68h+dwOptions], rax; lpData
0x1800211bd  xor     r8d, r8d; lpReserved
0x1800211c0  call    cs:__imp_RegQueryValueExW
0x1800211c7  nop     dword ptr [rax+rax+00h]
0x1800211cc  test    byte ptr cs:?g_SrvRole@@3KA, 1; ulong g_SrvRole
0x1800211d3  mov     ebx, eax
0x1800211d5  jz      short loc_180021241
0x1800211d7  lea     rbx, ?g_szScope@@3PAGA; ushort near * g_szScope
0x1800211de  mov     [rbp+cbData], 1FEh
0x1800211e5  mov     rcx, rbx; void *
0x1800211e8  xor     edx, edx; Val
  ... truncated ...
```
