# Dns_WriteNrptRuleToRegistry

- ea: `0x18007ea4c`
- end: `0x18007f246`
- name: `Dns_WriteNrptRuleToRegistry`
- size: `2042`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x1800a4b74`

## callees

- `0x180017e00`
- `0x180018204`
- `0x18003de30`
- `0x180062c94`
- `0x18007ea4c`
- `0x18007f24c`
- `0x1800883e0`
- `0x18008b5f0`
- `0x18008bf98`
- `0x1800cccb0`
- `0x1800dbadc`
- `0x1800dbb48`
- `0x1800dc4ac`
- `0x1800dc670`
- `0x1800dc9e0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007f17e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007f1b7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007f17e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007f1b7`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18007effd`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18007f19f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18007effd`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18007f19f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18007f132`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18007f132`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18007f076`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18007f076`
- `ntdll!RtlGetPersistedStateLocation` at `0x18007ee3f`
- `ntdll!RtlGetPersistedStateLocation` at `0x18007ee3f`
- `KERNELBASE!RegCreateKeyExInternalW` at `0x18007ef87`
- `KERNELBASE!RegCreateKeyExInternalW` at `0x18007ef87`

## string_xrefs

- `0x18007edde`: `Parameters\DnsPolicyConfig`
- `0x18007ee5e`: `Parameters\DnsPolicyConfig`
- `0x18007eea3`: `Parameters\DnsPolicyConfig`
- `0x18007edfe`: `Dnscache`
- `0x18007ee23`: `Dnscache`
- `0x18007ee71`: `Dnscache`
- `0x18007ef00`: `Dnscache`
- `0x18007ede5`: `SYSTEM\CurrentControlSet\Services\Dnscache`
- `0x18007ee65`: `SYSTEM\CurrentControlSet\Services\Dnscache`
- `0x18007ef07`: `SYSTEM\CurrentControlSet\Services\Dnscache`
- `0x18007eb54`: `DirectAccessQueryIPSECEncryption`
- `0x18007eb2e`: `DirectAccessDNSServers`
- `0x18007eb41`: `DirectAccessQueryIPSECRequired`
- `0x18007eb6d`: `DirectAccessProxyType`
- `0x18007ecb1`: `IDNConfig`
- `0x18007ec1b`: `ConfigOptions`
- `0x18007eb86`: `DirectAccessProxyName`

## pseudocode

```c
__int64 __fastcall Dns_WriteNrptRuleToRegistry(LPCWSTR lpSubKey, __int64 a2, int a3)
{
  int v6; // r12d
  size_t v7; // rdi
  int v8; // edx
  int v9; // r8d
  int PersistedStateLocation; // eax
  int v11; // edx
  int v12; // ecx
  int v13; // r8d
  int v14; // esi
  int v15; // ebx
  size_t v16; // rdx
  wchar_t *v17; // rcx
  HRESULT v18; // eax
  int v19; // edx
  int v20; // ecx
  int v21; // r8d
  __int64 v22; // r10
  unsigned int v23; // eax
  int v24; // ecx
  unsigned int v25; // ebx
  LSTATUS v26; // eax
  int v27; // ecx
  int v28; // edx
  __int64 i; // r15
  const WCHAR *v30; // r12
  LSTATUS v31; // eax
  int v32; // ecx
  int v33; // ecx
  size_t pcbLength; // [rsp+58h] [rbp-A8h] BYREF
  _DWORD v36[2]; // [rsp+60h] [rbp-A0h]
  LPCWSTR lpValueName; // [rsp+68h] [rbp-98h]
  DWORD dwType[2]; // [rsp+70h] [rbp-90h]
  int v39; // [rsp+78h] [rbp-88h]
  STRSAFE_PCNZWCH psz; // [rsp+80h] [rbp-80h]
  int v41; // [rsp+88h] [rbp-78h]
  const wchar_t *v42; // [rsp+90h] [rbp-70h]
  __int64 v43; // [rsp+98h] [rbp-68h]
  int v44; // [rsp+A0h] [rbp-60h]
  __int64 v45; // [rsp+A8h] [rbp-58h]
  int v46; // [rsp+B0h] [rbp-50h]
  const wchar_t *v47; // [rsp+B8h] [rbp-48h]
  __int64 v48; // [rsp+C0h] [rbp-40h]
  int v49; // [rsp+C8h] [rbp-38h]
  __int64 v50; // [rsp+D0h] [rbp-30h]
  int v51; // [rsp+D8h] [rbp-28h]
  const wchar_t *v52; // [rsp+E0h] [rbp-20h]
  __int64 v53; // [rsp+E8h] [rbp-18h]
  int v54; // [rsp+F0h] [rbp-10h]
  __int64 v55; // [rsp+F8h] [rbp-8h]
  int v56; // [rsp+100h] [rbp+0h]
  const WCHAR *v57; // [rsp+108h] [rbp+8h]
  int v58; // [rsp+110h] [rbp+10h]
  int v59; // [rsp+114h] [rbp+14h]
  int v60; // [rsp+118h] [rbp+18h]
  __int64 v61; // [rsp+120h] [rbp+20h]
  int v62; // [rsp+128h] [rbp+28h]
  const wchar_t *v63; // [rsp+130h] [rbp+30h]
  __int64 v64; // [rsp+138h] [rbp+38h]
  int v65; // [rsp+140h] [rbp+40h]
  __int64 v66; // [rsp+148h] [rbp+48h]
  int v67; // [rsp+150h] [rbp+50h]
  const wchar_t *v68; // [rsp+158h] [rbp+58h]
  __int64 v69; // [rsp+160h] [rbp+60h]
  int v70; // [rsp+168h] [rbp+68h]
  __int64 v71; // [rsp+170h] [rbp+70h]
  int v72; // [rsp+178h] [rbp+78h]
  const wchar_t *v73; // [rsp+180h] [rbp+80h]
  __int64 v74; // [rsp+188h] [rbp+88h]
  int v75; // [rsp+190h] [rbp+90h]
  __int64 v76; // [rsp+198h] [rbp+98h]
  int v77; // [rsp+1A0h] [rbp+A0h]
  const wchar_t *v78; // [rsp+1A8h] [rbp+A8h]
  __int64 v79; // [rsp+1B0h] [rbp+B0h]
  int v80; // [rsp+1B8h] [rbp+B8h]
  __int64 v81; // [rsp+1C0h] [rbp+C0h]
  int v82; // [rsp+1C8h] [rbp+C8h]
  const wchar_t *v83; // [rsp+1D0h] [rbp+D0h]
  __int64 v84; // [rsp+1D8h] [rbp+D8h]
  int v85; // [rsp+1E0h] [rbp+E0h]
  __int64 v86; // [rsp+1E8h] [rbp+E8h]
  int v87; // [rsp+1F0h] [rbp+F0h]
  const WCHAR *v88; // [rsp+1F8h] [rbp+F8h]
  __int64 v89; // [rsp+200h] [rbp+100h]
  int v90; // [rsp+208h] [rbp+108h]
  __int64 v91; // [rsp+210h] [rbp+110h]
  int v92; // [rsp+218h] [rbp+118h]
  const WCHAR *v93; // [rsp+220h] [rbp+120h]
  __int64 v94; // [rsp+228h] [rbp+128h]
  int v95; // [rsp+230h] [rbp+130h]
  __int64 v96; // [rsp+238h] [rbp+138h]
  int v97; // [rsp+240h] [rbp+140h]
  const wchar_t *v98; // [rsp+248h] [rbp+148h]
  __int64 v99; // [rsp+250h] [rbp+150h]
  int v100; // [rsp+258h] [rbp+158h]
  __int64 v101; // [rsp+260h] [rbp+160h]
  int v102; // [rsp+268h] [rbp+168h]
  const wchar_t *v103; // [rsp+270h] [rbp+170h]
  int v104; // [rsp+278h] [rbp+178h]
  int v105; // [rsp+27Ch] [rbp+17Ch]
  int v106; // [rsp+280h] [rbp+180h]
  __int64 v107; // [rsp+288h] [rbp+188h]
  int v108; // [rsp+290h] [rbp+190h]
  const wchar_t *v109; // [rsp+298h] [rbp+198h]
  int v110; // [rsp+2A0h] [rbp+1A0h]
  int v111; // [rsp+2A4h] [rbp+1A4h]
  int v112; // [rsp+2A8h] [rbp+1A8h]
  __int64 v113; // [rsp+2B0h] [rbp+1B0h]
  int v114; // [rsp+2B8h] [rbp+1B8h]
  const wchar_t *v115; // [rsp+2C0h] [rbp+1C0h]
  int v116; // [rsp+2C8h] [rbp+1C8h]
  int v117; // [rsp+2CCh] [rbp+1CCh]
  int v118; // [rsp+2D0h] [rbp+1D0h]
  __int64 v119; // [rsp+2D8h] [rbp+1D8h]
  int v120; // [rsp+2E0h] [rbp+1E0h]
  const WCHAR *v121; // [rsp+2E8h] [rbp+1E8h]
  __int64 v122; // [rsp+2F0h] [rbp+1F0h]
  int v123; // [rsp+2F8h] [rbp+1F8h]
  __int64 v124; // [rsp+300h] [rbp+200h]
  unsigned int v125; // [rsp+310h] [rbp+210h] BYREF
  HKEY hKey; // [rsp+318h] [rbp+218h] BYREF
  HKEY phkResult; // [rsp+320h] [rbp+220h] BYREF
  _WORD v128[264]; // [rsp+330h] [rbp+230h] BYREF

  *(_QWORD *)dwType = 7;
  hKey = 0;
  phkResult = 0;
  lpValueName = L"Name";
  psz = *(STRSAFE_PCNZWCH *)(a2 + 8);
  v41 = 2;
  v42 = L"DNSSECValidationRequired";
  v44 = 2;
  v49 = 2;
  v45 = a2 + 16;
  v6 = 0;
  v54 = 2;
  v47 = L"DNSSECQueryIPSECRequired";
  v50 = a2 + 20;
  pcbLength = 0;
  v52 = L"DNSSECQueryIPSECEncryption";
  LODWORD(v7) = 0;
  v36[0] = 1;
  v55 = a2 + 24;
  v57 = L"IPSECCARestriction";
  v61 = *(_QWORD *)(a2 + 32);
  v63 = L"DirectAccessDNSServers";
  v66 = *(_QWORD *)(a2 + 40);
  v68 = L"DirectAccessQueryIPSECRequired";
  v71 = a2 + 48;
  v73 = L"DirectAccessQueryIPSECEncryption";
  v76 = a2 + 52;
  v78 = L"DirectAccessProxyType";
  v81 = a2 + 56;
  v39 = 1;
  v43 = 4;
  v46 = 4;
  v48 = 4;
  v51 = 8;
  v53 = 4;
  v56 = 16;
  v58 = 1;
  v59 = 1;
  v60 = 1;
  v62 = 32;
  v64 = 1;
  v65 = 4;
  v67 = 64;
  v69 = 4;
  v70 = 4;
  v72 = 128;
  v74 = 4;
  v75 = 4;
  v77 = 256;
  v79 = 4;
  v80 = 4;
  v82 = 512;
  v83 = L"DirectAccessProxyName";
  v86 = *(_QWORD *)(a2 + 64);
  v88 = L"ConfigOptions";
  v91 = a2 + 72;
  v93 = L"Version";
  v96 = a2 + 76;
  v98 = L"GenericDNSServers";
  v101 = *(_QWORD *)(a2 + 80);
  v103 = L"VPNRequired";
  v107 = a2 + 88;
  v109 = L"ProxyType";
  v113 = a2 + 92;
  v115 = L"ProxyName";
  v119 = *(_QWORD *)(a2 + 96);
  v121 = L"IDNConfig";
  v124 = a2 + 104;
  v84 = 1;
  v85 = 4;
  v87 = 1024;
  v89 = 4;
  v90 = 1;
  v92 = 2048;
  v94 = 4;
  v95 = 1;
  v97 = 4096;
  v99 = 1;
  v100 = 8;
  v102 = 0x2000;
  v104 = 4;
  v105 = 1;
  v106 = 8;
  v108 = 0x4000;
  v110 = 4;
  v111 = 1;
  v112 = 8;
  v114 = 0x8000;
  v116 = 1;
  v117 = 1;
  v118 = 8;
  v120 = 0x10000;
  v122 = 4;
  v123 = 16;
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_Sd(1035, 19, (unsigned int)WPP_94cf04630261351a9f00a12e24967b8a_Traceguids, (_DWORD)lpSubKey, a3);
  memset_0(v128, 0, 0x20Au);
  hKey = 0;
  v125 = 0;
  if ( (BYTE3(xmmword_1801119E0) & 0x20) != 0 )
    WPP_SF_SSSqd(
      (unsigned int)L"Parameters\\DnsPolicyConfig",
      v8,
      v9,
      (unsigned int)L"Dnscache",
      (__int64)L"SYSTEM\\CurrentControlSet\\Services\\Dnscache",
      (__int64)L"Parameters\\DnsPolicyConfig",
      (__int64)v128,
      10);
  PersistedStateLocation = RtlGetPersistedStateLocation(
                             L"Dnscache",
                             0,
                             L"SYSTEM\\CurrentControlSet\\Services\\Dnscache",
                             0,
                             v128,
                             522,
                             &v125);
  v14 = PersistedStateLocation;
  if ( PersistedStateLocation < 0 )
  {
    if ( (BYTE3(xmmword_1801119E0) & 0x20) != 0 )
      WPP_SF_SSSd(
        v12,
        v11,
        v13,
        (unsigned int)L"Dnscache",
        (__int64)L"SYSTEM\\CurrentControlSet\\Services\\Dnscache",
        (__int64)L"Parameters\\DnsPolicyConfig",
        PersistedStateLocation);
    v15 = HRESULT_FROM_NTSTATUS(v14);
    goto LABEL_14;
  }
  v16 = 522 - v125;
  v17 = &v128[(unsigned __int64)v125 >> 1];
  *(v17 - 1) = 92;
  v18 = StringCbCopyW(v17, v16, L"Parameters\\DnsPolicyConfig");
  v15 = v18;
  if ( v18 >= 0 )
  {
    if ( (BYTE3(xmmword_1801119E0) & 0x20) != 0 )
    {
      WPP_SF_SSSS(
        v20,
        v19,
        v21,
        (unsigned int)L"Dnscache",
        (__int64)L"SYSTEM\\CurrentControlSet\\Services\\Dnscache",
        v22,
        (__int64)v128);
LABEL_14:
      if ( (BYTE3(xmmword_1801119E0) & 0x20) != 0 )
        WPP_SF_d(1053, 14, WPP_5573ccff99bc3fd3725f4dc217ee9a93_Traceguids, (unsigned int)v15);
    }
  }
  else if ( (BYTE3(xmmword_1801119E0) & 0x20) != 0 )
  {
    WPP_SF_d(1053, 12, WPP_5573ccff99bc3fd3725f4dc217ee9a93_Traceguids, (unsigned int)v18);
    goto LABEL_14;
  }
  if ( v15 >= 0 )
    v23 = RegCreateKeyExInternalW(-2147483646, v128, 0, 0, 0, 131097, 0, &hKey, 0, 0);
  else
    v23 = WX_WIN32_FROM_HR((unsigned int)v15);
  v25 = v23;
  if ( v23 )
  {
    if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    {
      WPP_SF_SD(v24, 10, (unsigned int)WPP_cf96f6af26f535eeb3b7d66bdedfd114_Traceguids, (unsigned int)v128, v23);
      if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
        WPP_SF_d(1035, 20, WPP_94cf04630261351a9f00a12e24967b8a_Traceguids, v25);
    }
    goto LABEL_46;
  }
  v26 = RegDeleteKeyExW(hKey, lpSubKey, 0, 0);
  v25 = v26;
  if ( (v26 & 0xFFFFFFFD) != 0 )
  {
    if ( (BYTE1(xmmword_1801119E0) & 8) == 0 )
      goto LABEL_46;
    v28 = 21;
    goto LABEL_26;
  }
  v26 = RegCreateKeyExW(hKey, lpSubKey, 0, 0, a3 != 0, 0x20006u, 0, &phkResult, 0);
  v25 = v26;
  if ( v26 )
  {
    if ( (BYTE1(xmmword_1801119E0) & 8) == 0 )
      goto LABEL_46;
    v28 = 22;
LABEL_26:
    WPP_SF_SD(v27, v28, (unsigned int)WPP_94cf04630261351a9f00a12e24967b8a_Traceguids, (_DWORD)lpSubKey, v26);
    goto LABEL_46;
  }
  for ( i = 0; (unsigned int)i < 0x11; i = (unsigned int)(i + 1) )
  {
    if ( (v36[10 * i] & *(_DWORD *)(a2 + 4)) == 0 )
      continue;
    switch ( dwType[10 * i] )
    {
      case 1u:
        if ( StringCbLengthW((&psz)[5 * i], 0x104u, &pcbLength) < 0 )
        {
          v25 = 87;
LABEL_45:
          v6 = 0;
          goto LABEL_46;
        }
        v7 = pcbLength + 2;
        break;
      case 4u:
        v7 = 4;
        break;
      case 7u:
        v7 = (unsigned int)MultiSz_Size_W((&psz)[5 * i]);
        break;
      default:
        goto LABEL_41;
    }
    pcbLength = v7;
LABEL_41:
    v30 = *(const WCHAR **)&dwType[10 * i - 2];
    v31 = RegSetValueExW(phkResult, v30, 0, dwType[10 * i], (const BYTE *)(&psz)[5 * i], v7);
    v25 = v31;
    if ( v31 )
    {
      if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
        WPP_SF_SD(v32, 23, (unsigned int)WPP_94cf04630261351a9f00a12e24967b8a_Traceguids, (_DWORD)v30, v31);
      goto LABEL_45;
    }
  }
  v6 = 1;
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    Dns_TraceNrptRule(a2, "NRPT rule set successfully");
LABEL_46:
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( !v6 )
    RegDeleteKeyExW(hKey, lpSubKey, 0, 0);
  v33 = (int)hKey;
  if ( hKey )
    RegCloseKey(hKey);
  if ( v25 && (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_SD(v33, 24, (unsigned int)WPP_94cf04630261351a9f00a12e24967b8a_Traceguids, (_DWORD)lpSubKey, v25);
  return v25;
}

```

## disassembly

```asm
0x18007ea4c  mov     [rsp-8+arg_10], rbx
0x18007ea51  push    rbp
0x18007ea52  push    rsi
0x18007ea53  push    rdi
0x18007ea54  push    r12
0x18007ea56  push    r13
0x18007ea58  push    r14
0x18007ea5a  push    r15
0x18007ea5c  lea     rbp, [rsp-450h]
0x18007ea64  sub     rsp, 550h
0x18007ea6b  mov     rax, cs:__security_cookie
0x18007ea72  xor     rax, rsp
0x18007ea75  mov     [rbp+480h+var_40], rax
0x18007ea7c  xor     esi, esi
0x18007ea7e  mov     qword ptr [rsp+580h+dwType], 7
0x18007ea87  mov     r13, rdx
0x18007ea8a  mov     [rbp+480h+hKey], rsi
0x18007ea91  lea     rax, aName; "Name"
0x18007ea98  mov     [rbp+480h+var_260], rsi
0x18007ea9f  mov     [rsp+580h+lpValueName], rax
0x18007eaa4  mov     r14, rcx
0x18007eaa7  mov     rax, [rdx+8]
0x18007eaab  lea     r9d, [rsi+4]
0x18007eaaf  mov     [rbp+480h+psz], rax
0x18007eab3  lea     ecx, [rsi+2]
0x18007eab6  lea     rax, aDnssecvalidati; "DNSSECValidationRequired"
0x18007eabd  mov     [rbp+480h+var_4F8], ecx
0x18007eac0  mov     [rbp+480h+var_4F0], rax
0x18007eac4  mov     r15d, r8d
0x18007eac7  lea     r8d, [rsi+1]
0x18007eacb  mov     [rbp+480h+var_4E0], ecx
0x18007eace  lea     rax, [rdx+10h]
0x18007ead2  mov     [rbp+480h+var_4B8], ecx
0x18007ead5  mov     [rbp+480h+var_4D8], rax
0x18007ead9  mov     r12d, esi
0x18007eadc  lea     rax, aDnssecqueryips; "DNSSECQueryIPSECRequired"
0x18007eae3  mov     [rbp+480h+var_490], ecx
0x18007eae6  mov     [rbp+480h+var_4C8], rax
0x18007eaea  lea     ecx, [rsi+10h]
0x18007eaed  lea     rax, [rdx+14h]
0x18007eaf1  mov     [rsp+580h+var_530], esi
0x18007eaf5  mov     [rbp+480h+var_4B0], rax
0x18007eaf9  lea     edx, [rsi+8]
0x18007eafc  lea     rax, aDnssecqueryips_0; "DNSSECQueryIPSECEncryption"
0x18007eb03  mov     [rsp+580h+pcbLength], rsi
0x18007eb08  mov     [rbp+480h+var_4A0], rax
0x18007eb0c  mov     edi, esi
0x18007eb0e  lea     rax, [r13+18h]
0x18007eb12  mov     [rsp+580h+var_520], r8d
0x18007eb17  mov     [rbp+480h+var_488], rax
0x18007eb1b  lea     rax, aIpseccarestric; "IPSECCARestriction"
0x18007eb22  mov     [rbp+480h+var_478], rax
0x18007eb26  mov     rax, [r13+20h]
0x18007eb2a  mov     [rbp+480h+var_460], rax
0x18007eb2e  lea     rax, aDirectaccessdn; "DirectAccessDNSServers"
0x18007eb35  mov     [rbp+480h+var_450], rax
0x18007eb39  mov     rax, [r13+28h]
0x18007eb3d  mov     [rbp+480h+var_438], rax
0x18007eb41  lea     rax, aDirectaccessqu_0; "DirectAccessQueryIPSECRequired"
0x18007eb48  mov     [rbp+480h+var_428], rax
0x18007eb4c  lea     rax, [r13+30h]
0x18007eb50  mov     [rbp+480h+var_410], rax
0x18007eb54  lea     rax, aDirectaccessqu_1; "DirectAccessQueryIPSECEncryption"
0x18007eb5b  mov     [rbp+480h+var_400], rax
0x18007eb62  lea     rax, [r13+34h]
0x18007eb66  mov     [rbp+480h+var_3E8], rax
0x18007eb6d  lea     rax, aDirectaccesspr; "DirectAccessProxyType"
0x18007eb74  mov     [rbp+480h+var_3D8], rax
0x18007eb7b  lea     rax, [r13+38h]
0x18007eb7f  mov     [rbp+480h+var_3C0], rax
0x18007eb86  lea     rax, aDirectaccesspr_0; "DirectAccessProxyName"
0x18007eb8d  mov     [rsp+580h+var_508], r8d
0x18007eb92  mov     [rbp+480h+var_4E8], r9
0x18007eb96  mov     [rbp+480h+var_4D0], r9d
0x18007eb9a  mov     [rbp+480h+var_4C0], r9
0x18007eb9e  mov     [rbp+480h+var_4A8], edx
0x18007eba1  mov     [rbp+480h+var_498], r9
0x18007eba5  mov     [rbp+480h+var_480], ecx
0x18007eba8  mov     [rbp+480h+var_470], r8d
0x18007ebac  mov     [rbp+480h+var_46C], r8d
0x18007ebb0  mov     [rbp+480h+var_468], r8d
0x18007ebb4  mov     [rbp+480h+var_458], 20h ; ' '
0x18007ebbb  mov     [rbp+480h+var_448], r8
0x18007ebbf  mov     [rbp+480h+var_440], r9d
0x18007ebc3  mov     [rbp+480h+var_430], 40h ; '@'
0x18007ebca  mov     [rbp+480h+var_420], r9
0x18007ebce  mov     [rbp+480h+var_418], r9d
0x18007ebd2  mov     [rbp+480h+var_408], 80h
0x18007ebd9  mov     [rbp+480h+var_3F8], r9
0x18007ebe0  mov     [rbp+480h+var_3F0], r9d
0x18007ebe7  mov     [rbp+480h+var_3E0], 100h
0x18007ebf1  mov     [rbp+480h+var_3D0], r9
0x18007ebf8  mov     [rbp+480h+var_3C8], r9d
0x18007ebff  mov     [rbp+480h+var_3B8], 200h
0x18007ec09  mov     [rbp+480h+var_3B0], rax
0x18007ec10  mov     rax, [r13+40h]
0x18007ec14  mov     [rbp+480h+var_398], rax
0x18007ec1b  lea     rax, aConfigoptions; "ConfigOptions"
0x18007ec22  mov     [rbp+480h+var_388], rax
0x18007ec29  lea     rax, [r13+48h]
0x18007ec2d  mov     [rbp+480h+var_370], rax
0x18007ec34  lea     rax, aVersion; "Version"
0x18007ec3b  mov     [rbp+480h+var_360], rax
0x18007ec42  lea     rax, [r13+4Ch]
0x18007ec46  mov     [rbp+480h+var_348], rax
0x18007ec4d  lea     rax, aGenericdnsserv; "GenericDNSServers"
0x18007ec54  mov     [rbp+480h+var_338], rax
0x18007ec5b  mov     rax, [r13+50h]
0x18007ec5f  mov     [rbp+480h+var_320], rax
0x18007ec66  lea     rax, aVpnrequired; "VPNRequired"
0x18007ec6d  mov     [rbp+480h+var_310], rax
0x18007ec74  lea     rax, [r13+58h]
0x18007ec78  mov     [rbp+480h+var_2F8], rax
0x18007ec7f  lea     rax, aProxytype; "ProxyType"
0x18007ec86  mov     [rbp+480h+var_2E8], rax
0x18007ec8d  lea     rax, [r13+5Ch]
0x18007ec91  mov     [rbp+480h+var_2D0], rax
0x18007ec98  lea     rax, aProxyname; "ProxyName"
0x18007ec9f  mov     [rbp+480h+var_2C0], rax
0x18007eca6  mov     rax, [r13+60h]
0x18007ecaa  mov     [rbp+480h+var_2A8], rax
0x18007ecb1  lea     rax, aIdnconfig; "IDNConfig"
0x18007ecb8  mov     [rbp+480h+var_298], rax
0x18007ecbf  lea     rax, [r13+68h]
0x18007ecc3  mov     [rbp+480h+var_280], rax
0x18007ecca  mov     [rbp+480h+var_3A8], r8
0x18007ecd1  mov     [rbp+480h+var_3A0], r9d
0x18007ecd8  mov     [rbp+480h+var_390], 400h
0x18007ece2  mov     [rbp+480h+var_380], r9
0x18007ece9  mov     [rbp+480h+var_378], r8d
0x18007ecf0  mov     [rbp+480h+var_368], 800h
0x18007ecfa  mov     [rbp+480h+var_358], r9
0x18007ed01  mov     [rbp+480h+var_350], r8d
0x18007ed08  mov     [rbp+480h+var_340], 1000h
0x18007ed12  mov     [rbp+480h+var_330], r8
0x18007ed19  mov     [rbp+480h+var_328], edx
0x18007ed1f  mov     [rbp+480h+var_318], 2000h
0x18007ed29  mov     [rbp+480h+var_308], r9d
0x18007ed30  mov     [rbp+480h+var_304], r8d
0x18007ed37  mov     [rbp+480h+var_300], edx
0x18007ed3d  mov     [rbp+480h+var_2F0], 4000h
0x18007ed47  mov     [rbp+480h+var_2E0], r9d
0x18007ed4e  mov     [rbp+480h+var_2DC], r8d
0x18007ed55  mov     [rbp+480h+var_2D8], edx
0x18007ed5b  mov     [rbp+480h+var_2C8], 8000h
0x18007ed65  mov     [rbp+480h+var_2B8], r8d
0x18007ed6c  mov     [rbp+480h+var_2B4], r8d
0x18007ed73  mov     [rbp+480h+var_2B0], edx
0x18007ed79  mov     [rbp+480h+var_2A0], 10000h
0x18007ed83  mov     [rbp+480h+var_290], r9
0x18007ed8a  mov     [rbp+480h+var_288], ecx
0x18007ed90  test    byte ptr cs:xmmword_1801119E0+1, dl
0x18007ed96  jz      short loc_18007EDB4
0x18007ed98  lea     edx, [rsi+13h]
0x18007ed9b  mov     [rsp+580h+dwOptions], r15d
0x18007eda0  mov     ecx, 40Bh
0x18007eda5  lea     r8, WPP_94cf04630261351a9f00a12e24967b8a_Traceguids
0x18007edac  mov     r9, r14
0x18007edaf  call    WPP_SF_Sd
0x18007edb4  mov     ebx, 20Ah
0x18007edb9  lea     rcx, [rbp+480h+var_250]; void *
0x18007edc0  mov     r8d, ebx; Size
0x18007edc3  xor     edx, edx; Val
0x18007edc5  call    memset_0
0x18007edca  mov     [rbp+480h+hKey], rsi
0x18007edd1  mov     [rbp+480h+var_270], esi
0x18007edd7  test    byte ptr cs:xmmword_1801119E0+3, 20h
0x18007edde  lea     rcx, aParametersDnsp; "Parameters\\DnsPolicyConfig"
0x18007ede5  lea     rsi, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Dn"...
0x18007edec  jz      short loc_18007EE14
0x18007edee  mov     dword ptr [rsp+580h+phkResult], ebx
0x18007edf2  lea     rax, [rbp+480h+var_250]
0x18007edf9  mov     [rsp+580h+lpSecurityAttributes], rax
0x18007edfe  lea     r9, aDnscache_1; "Dnscache"
0x18007ee05  mov     qword ptr [rsp+580h+samDesired], rcx
0x18007ee0a  mov     qword ptr [rsp+580h+dwOptions], rsi
0x18007ee0f  call    WPP_SF_SSSqd
0x18007ee14  lea     rax, [rbp+480h+var_270]
0x18007ee1b  xor     r9d, r9d
0x18007ee1e  mov     [rsp+580h+lpSecurityAttributes], rax
0x18007ee23  lea     rcx, aDnscache_1; "Dnscache"
0x18007ee2a  lea     rax, [rbp+480h+var_250]
0x18007ee31  mov     [rsp+580h+samDesired], ebx
0x18007ee35  mov     r8, rsi
0x18007ee38  mov     qword ptr [rsp+580h+dwOptions], rax
0x18007ee3d  xor     edx, edx
0x18007ee3f  call    cs:__imp_RtlGetPersistedStateLocation
0x18007ee46  nop     dword ptr [rax+rax+00h]
0x18007ee4b  mov     esi, eax
0x18007ee4d  test    eax, eax
0x18007ee4f  jns     short loc_18007EE90
0x18007ee51  test    byte ptr cs:xmmword_1801119E0+3, 20h
0x18007ee58  jz      short loc_18007EE82
0x18007ee5a  mov     dword ptr [rsp+580h+lpSecurityAttributes], eax
0x18007ee5e  lea     r10, aParametersDnsp; "Parameters\\DnsPolicyConfig"
0x18007ee65  lea     rax, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Dn"...
0x18007ee6c  mov     qword ptr [rsp+580h+samDesired], r10
0x18007ee71  lea     r9, aDnscache_1; "Dnscache"
0x18007ee78  mov     qword ptr [rsp+580h+dwOptions], rax
0x18007ee7d  call    WPP_SF_SSSd
0x18007ee82  mov     ecx, esi; int
0x18007ee84  call    ?HRESULT_FROM_NTSTATUS@@YAJJ@Z; HRESULT_FROM_NTSTATUS(long)
0x18007ee89  mov     ebx, eax
0x18007ee8b  jmp     loc_18007EF1D
0x18007ee90  mov     eax, [rbp+480h+var_270]
0x18007ee96  lea     rcx, [rbp+480h+var_250]
0x18007ee9d  sub     ebx, [rbp+480h+var_270]
0x18007eea3  lea     r10, aParametersDnsp; "Parameters\\DnsPolicyConfig"
0x18007eeaa  shr     rax, 1
0x18007eead  mov     r8, r10; pszSrc
0x18007eeb0  mov     edx, ebx; cbDest
0x18007eeb2  lea     rcx, [rcx+rax*2]; pszDest
0x18007eeb6  mov     word ptr [rcx-2], 5Ch ; '\'
0x18007eebc  call    StringCbCopyW
0x18007eec1  mov     ebx, eax
0x18007eec3  test    eax, eax
0x18007eec5  jns     short loc_18007EEEB
0x18007eec7  test    byte ptr cs:xmmword_1801119E0+3, 20h
0x18007eece  jz      short loc_18007EF3F
0x18007eed0  mov     edx, 0Ch
0x18007eed5  lea     r8, WPP_5573ccff99bc3fd3725f4dc217ee9a93_Traceguids
0x18007eedc  mov     ecx, 41Dh
0x18007eee1  mov     r9d, eax
0x18007eee4  call    WPP_SF_d
0x18007eee9  jmp     short loc_18007EF1D
0x18007eeeb  test    byte ptr cs:xmmword_1801119E0+3, 20h
0x18007eef2  jz      short loc_18007EF3F
0x18007eef4  lea     rax, [rbp+480h+var_250]
0x18007eefb  mov     [rsp+580h+lpSecurityAttributes], rax
0x18007ef00  lea     r9, aDnscache_1; "Dnscache"
0x18007ef07  lea     rax, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Dn"...
0x18007ef0e  mov     qword ptr [rsp+580h+samDesired], r10
0x18007ef13  mov     qword ptr [rsp+580h+dwOptions], rax
0x18007ef18  call    WPP_SF_SSSS
0x18007ef1d  test    byte ptr cs:xmmword_1801119E0+3, 20h
0x18007ef24  jz      short loc_18007EF3F
0x18007ef26  mov     edx, 0Eh
0x18007ef2b  lea     r8, WPP_5573ccff99bc3fd3725f4dc217ee9a93_Traceguids
0x18007ef32  mov     ecx, 41Dh
0x18007ef37  mov     r9d, ebx
0x18007ef3a  call    WPP_SF_d
0x18007ef3f  test    ebx, ebx
0x18007ef41  jns     short loc_18007EF4C
0x18007ef43  mov     ecx, ebx
0x18007ef45  call    WX_WIN32_FROM_HR
0x18007ef4a  jmp     short loc_18007EF93
0x18007ef4c  mov     [rsp+580h+var_538], rdi
0x18007ef51  lea     rax, [rbp+480h+hKey]
0x18007ef58  mov     [rsp+580h+lpdwDisposition], rdi
0x18007ef5d  lea     rdx, [rbp+480h+var_250]
0x18007ef64  mov     [rsp+580h+phkResult], rax
0x18007ef69  xor     r9d, r9d
0x18007ef6c  mov     [rsp+580h+lpSecurityAttributes], rdi
0x18007ef71  xor     r8d, r8d
0x18007ef74  mov     [rsp+580h+samDesired], 20019h
0x18007ef7c  mov     rcx, 0FFFFFFFF80000002h
0x18007ef83  mov     [rsp+580h+dwOptions], edi
0x18007ef87  call    cs:__imp_RegCreateKeyExInternalW
0x18007ef8e  nop     dword ptr [rax+rax+00h]
0x18007ef93  mov     ebx, eax
0x18007ef95  test    eax, eax
0x18007ef97  jz      short loc_18007EFED
0x18007ef99  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18007efa0  jz      loc_18007F172
0x18007efa6  mov     edx, 0Ah
0x18007efab  mov     [rsp+580h+dwOptions], eax
0x18007efaf  lea     r9, [rbp+480h+var_250]
0x18007efb6  lea     r8, WPP_cf96f6af26f535eeb3b7d66bdedfd114_Traceguids
0x18007efbd  call    WPP_SF_SD
0x18007efc2  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18007efc9  jz      loc_18007F172
0x18007efcf  mov     edx, 14h
0x18007efd4  lea     r8, WPP_94cf04630261351a9f00a12e24967b8a_Traceguids
0x18007efdb  mov     ecx, 40Bh
0x18007efe0  mov     r9d, ebx
0x18007efe3  call    WPP_SF_d
0x18007efe8  jmp     loc_18007F172
0x18007efed  mov     rcx, [rbp+480h+hKey]; hKey
0x18007eff4  xor     r9d, r9d; Reserved
0x18007eff7  xor     r8d, r8d; samDesired
0x18007effa  mov     rdx, r14; lpSubKey
0x18007effd  call    cs:__imp_RegDeleteKeyExW
0x18007f004  nop     dword ptr [rax+rax+00h]
0x18007f009  mov     ebx, eax
0x18007f00b  test    eax, 0FFFFFFFDh
0x18007f010  jz      short loc_18007F03C
0x18007f012  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18007f019  jz      loc_18007F172
0x18007f01f  mov     edx, 15h
0x18007f024  mov     r9, r14
0x18007f027  mov     [rsp+580h+dwOptions], eax
0x18007f02b  lea     r8, WPP_94cf04630261351a9f00a12e24967b8a_Traceguids
0x18007f032  call    WPP_SF_SD
0x18007f037  jmp     loc_18007F172
0x18007f03c  xor     eax, eax
0x18007f03e  mov     [rsp+580h+lpdwDisposition], rdi; lpdwDisposition
0x18007f043  lea     rcx, [rbp+480h+var_260]
0x18007f04a  test    r15d, r15d
0x18007f04d  mov     [rsp+580h+phkResult], rcx; phkResult
0x18007f052  mov     rdx, r14; lpSubKey
  ... truncated ...
```
