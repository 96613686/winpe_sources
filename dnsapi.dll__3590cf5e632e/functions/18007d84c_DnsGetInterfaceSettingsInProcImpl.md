# DnsGetInterfaceSettingsInProcImpl

- ea: `0x18007d84c`
- end: `0x18007e189`
- name: `DnsGetInterfaceSettingsInProcImpl`
- size: `2365`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task`

## callers

- `0x18007d78c`

## callees

- `0x1800087a0`
- `0x1800089c0`
- `0x1800097e0`
- `0x18002b050`
- `0x180036360`
- `0x1800631f8`
- `0x180065b2c`
- `0x18007d84c`
- `0x18008b5f0`
- `0x1800dbfe0`
- `0x1800dc9e0`
- `0x1800dd468`
- `0x1800de650`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007e0ab`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007e0c8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007e0e5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007e0ab`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007e0c8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007e0e5`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18007d97b`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18007da08`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18007da9c`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18007dd9f`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18007de6d`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18007df39`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18007d97b`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18007da08`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18007da9c`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18007dd9f`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18007de6d`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18007df39`

## string_xrefs

- `0x18007d91a`: `System\CurrentControlSet\Services\Tcpip\Parameters\Interfaces`
- `0x18007d9a7`: `System\CurrentControlSet\Services\Tcpip6\Parameters\Interfaces`
- `0x18007da48`: `Dnscache`
- `0x18007da3d`: `SYSTEM\CurrentControlSet\Services\Dnscache`
- `0x18007d925`: `DnscacheTcpipInterfaces`
- `0x18007df6b`: `DnscacheTcpipInterfaces`
- `0x18007d9b2`: `DnscacheTcpip6Interfaces`
- `0x18007de9b`: `DnscacheTcpip6Interfaces`

## pseudocode

```c
__int64 __fastcall DnsGetInterfaceSettingsInProcImpl(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  void *v5; // rsi
  void *v6; // r14
  void *v7; // r15
  unsigned int v10; // ebx
  unsigned int v11; // eax
  __int64 v12; // r9
  __int64 v13; // rdx
  HKEY v14; // rbx
  __int64 v15; // rax
  int DwordValue; // eax
  int v17; // ecx
  __int64 v18; // rax
  int v19; // eax
  int v20; // edx
  __int64 v21; // rax
  int v22; // eax
  int v23; // ecx
  __int64 v24; // rax
  int v25; // eax
  int v26; // ecx
  __int64 v27; // rax
  __int64 v28; // r9
  int v29; // eax
  int v30; // r12d
  __int64 v31; // rax
  int v32; // eax
  int v33; // r13d
  const WCHAR *v34; // rax
  const WCHAR *v35; // rax
  const WCHAR *v36; // rax
  const WCHAR *v37; // rax
  int StringValueW; // eax
  HKEY v39; // r10
  const WCHAR *v40; // rax
  HKEY v41; // r10
  int v42; // eax
  char v43; // al
  __int64 v44; // r9
  char v45; // al
  char v46; // al
  __int64 v47; // rcx
  bool v48; // zf
  __int64 v49; // rcx
  LPDWORD lpcbMaxSubKeyLen; // [rsp+28h] [rbp-D8h]
  LPDWORD lpcbMaxSubKeyLena; // [rsp+28h] [rbp-D8h]
  __int64 v53; // [rsp+60h] [rbp-A0h] BYREF
  int v54; // [rsp+68h] [rbp-98h] BYREF
  int v55; // [rsp+6Ch] [rbp-94h] BYREF
  int v56; // [rsp+70h] [rbp-90h] BYREF
  int v57; // [rsp+74h] [rbp-8Ch] BYREF
  int v58; // [rsp+78h] [rbp-88h] BYREF
  void *v59; // [rsp+80h] [rbp-80h]
  void *v60; // [rsp+88h] [rbp-78h]
  LPVOID lpMem; // [rsp+90h] [rbp-70h]
  LPVOID v62; // [rsp+98h] [rbp-68h]
  int v63; // [rsp+A0h] [rbp-60h]
  int v64; // [rsp+A4h] [rbp-5Ch]
  void *v65; // [rsp+A8h] [rbp-58h]
  HKEY v66; // [rsp+B0h] [rbp-50h] BYREF
  HKEY hKey; // [rsp+B8h] [rbp-48h] BYREF
  HKEY v68; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v69; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v70; // [rsp+D0h] [rbp-30h] BYREF
  int v71; // [rsp+D8h] [rbp-28h] BYREF
  int v72; // [rsp+DCh] [rbp-24h] BYREF
  struct _FILETIME v73; // [rsp+E0h] [rbp-20h] BYREF
  struct _FILETIME v74; // [rsp+E8h] [rbp-18h] BYREF
  struct _FILETIME lpftLastWriteTime; // [rsp+F0h] [rbp-10h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+F8h] [rbp-8h] BYREF

  hKey = 0;
  v5 = 0;
  v68 = 0;
  v6 = 0;
  v66 = 0;
  v7 = 0;
  v53 = 0;
  lpMem = 0;
  v62 = 0;
  v59 = 0;
  v60 = 0;
  v65 = 0;
  v54 = 0;
  v55 = 0;
  v56 = 0;
  v63 = 0;
  v57 = 0;
  v71 = 0;
  v72 = 0;
  v69 = 0;
  v70 = 0;
  v74 = 0;
  ftLastWriteTime = 0;
  lpftLastWriteTime = 0;
  v73 = 0;
  v64 = 0;
  v58 = 0;
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_SSq(a1, 10, (unsigned int)WPP_75ba1181f9a6332c212052b3f273b20c_Traceguids, a1, a2, a3);
  v10 = CreatePersistedRegistryKeyHelper(
          (__int64)L"DnscacheTcpipInterfaces",
          (__int64)L"System\\CurrentControlSet\\Services\\Tcpip\\Parameters\\Interfaces",
          a1,
          a4,
          0x20019u,
          (__int64)lpcbMaxSubKeyLen,
          0,
          &hKey);
  if ( !v10 )
  {
    v11 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, &ftLastWriteTime);
    v10 = v11;
    if ( v11 )
    {
      if ( (BYTE1(xmmword_1801119E0) & 8) == 0 )
        goto LABEL_89;
      v13 = 11;
      goto LABEL_87;
    }
    if ( (*(_BYTE *)(a3 + 8) & 1) != 0 )
    {
      v10 = CreatePersistedRegistryKeyHelper(
              (__int64)L"DnscacheTcpip6Interfaces",
              (__int64)L"System\\CurrentControlSet\\Services\\Tcpip6\\Parameters\\Interfaces",
              a1,
              v12,
              0x20019u,
              (__int64)lpcbMaxSubKeyLena,
              0,
              &v68);
      if ( v10 )
        goto LABEL_89;
      v11 = RegQueryInfoKeyW(v68, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, &lpftLastWriteTime);
      v10 = v11;
      if ( v11 )
      {
        if ( (BYTE1(xmmword_1801119E0) & 8) == 0 )
          goto LABEL_89;
        v13 = 12;
LABEL_87:
        v44 = v11;
        goto LABEL_88;
      }
    }
    CreatePersistedRegistryKeyHelper(
      (__int64)L"Dnscache",
      (__int64)L"SYSTEM\\CurrentControlSet\\Services\\Dnscache",
      a2,
      v12,
      0x20019u,
      (__int64)lpcbMaxSubKeyLena,
      0,
      &v66);
    if ( v66 )
    {
      v11 = RegQueryInfoKeyW(v66, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, &v74);
      v10 = v11;
      if ( v11 )
      {
        if ( (BYTE1(xmmword_1801119E0) & 8) == 0 )
          goto LABEL_89;
        v13 = 13;
        goto LABEL_87;
      }
    }
    v14 = hKey;
    v15 = regValueNameForId(63);
    DwordValue = privateRegReadDwordValue(v14, v15, (char *)&v53 + 4);
    v17 = HIDWORD(v53);
    if ( DwordValue )
      v17 = 1;
    HIDWORD(v53) = v17;
    v18 = regValueNameForId(65);
    v19 = privateRegReadDwordValue(v14, v18, &v54);
    v20 = v54;
    if ( v19 )
      v20 = 0;
    v54 = v20;
    v21 = regValueNameForId(92);
    v22 = privateRegReadDwordValue(v14, v21, &v55);
    v23 = v55;
    if ( v22 )
      v23 = 3;
    v55 = v23;
    v24 = regValueNameForId(10);
    v25 = privateRegReadDwordValue(v14, v24, &v56);
    v26 = v56;
    if ( v25 )
      v26 = 1;
    v56 = v26;
    if ( v66 )
    {
      v27 = regValueNameForId(114);
      v29 = privateRegReadDwordValue(v28, v27, &v57);
      v30 = v57;
      if ( v29 )
        v30 = 0;
      v31 = regValueNameForId(55);
      v32 = privateRegReadDwordValue(v66, v31, &v58);
      v33 = v58;
      if ( v32 )
        v33 = 0;
    }
    else
    {
      v30 = v63;
      v33 = v64;
    }
    v34 = (const WCHAR *)regValueNameForId(1);
    if ( (unsigned int)privateRegReadStringValueW(v14, v34, (__int64)&v53) == 14 )
      goto LABEL_30;
    if ( (*(_BYTE *)(a3 + 8) & 1) != 0 )
      v14 = v68;
    v35 = (const WCHAR *)regValueNameForId(9);
    if ( (unsigned int)privateRegReadStringValueW(v14, v35, (__int64)&v53) == 14 )
    {
LABEL_30:
      v10 = 14;
      goto LABEL_89;
    }
    v36 = (const WCHAR *)regValueNameForId(7);
    if ( (unsigned int)privateRegReadStringValueW(v14, v36, (__int64)&v53) == 14 )
    {
      v5 = v59;
      v10 = 14;
      goto LABEL_89;
    }
    v37 = (const WCHAR *)regValueNameForId(8);
    StringValueW = privateRegReadStringValueW(v14, v37, (__int64)&v53);
    v10 = 14;
    if ( StringValueW == 14 )
    {
LABEL_37:
      v5 = v59;
      v6 = v60;
      goto LABEL_89;
    }
    v39 = v66;
    if ( v66 )
    {
      v40 = (const WCHAR *)regValueNameForId(115);
      v42 = privateRegReadStringValueW(v41, v40, (__int64)&v53);
      v7 = v65;
      if ( v42 == 14 )
        goto LABEL_37;
      v39 = v66;
    }
    v5 = v59;
    v6 = v60;
    if ( v59 || v60 )
    {
      if ( (unsigned int)ResolverGetInterfaceProperties(
                           (_DWORD)v39,
                           *(_DWORD *)(a3 + 8) & 1,
                           (_DWORD)v59,
                           (_DWORD)v60,
                           (__int64)&v71,
                           (__int64)&v69,
                           (__int64)&v72,
                           (__int64)&v70) == 14 )
        goto LABEL_89;
      v39 = v66;
    }
    if ( !v39 )
      goto LABEL_56;
    v11 = RegQueryInfoKeyW(v39, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, &v73);
    v10 = v11;
    if ( v11 )
    {
      if ( (BYTE1(xmmword_1801119E0) & 8) == 0 )
        goto LABEL_89;
      v13 = 14;
      goto LABEL_87;
    }
    if ( v73 == v74 )
    {
LABEL_56:
      if ( !v68 )
        goto LABEL_63;
      v11 = RegQueryInfoKeyW(v68, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, &v73);
      v10 = v11;
      if ( v11 )
      {
        if ( (BYTE1(xmmword_1801119E0) & 8) == 0 )
          goto LABEL_89;
        v13 = 17;
        goto LABEL_87;
      }
      if ( v73 == lpftLastWriteTime )
      {
LABEL_63:
        v11 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, &v73);
        v10 = v11;
        if ( v11 )
        {
          if ( (BYTE1(xmmword_1801119E0) & 8) == 0 )
            goto LABEL_89;
          v13 = 20;
          goto LABEL_87;
        }
        if ( v73 == ftLastWriteTime )
        {
          if ( lpMem )
          {
            *(_QWORD *)(a3 + 16) = lpMem;
            lpMem = 0;
          }
          if ( v62 )
          {
            *(_QWORD *)(a3 + 32) = v62;
            v62 = 0;
          }
          if ( v5 )
          {
            *(_QWORD *)(a3 + 24) = v5;
            v5 = 0;
          }
          if ( v6 )
          {
            *(_QWORD *)(a3 + 56) = v6;
            v6 = 0;
          }
          if ( v7 )
          {
            *(_QWORD *)(a3 + 72) = v7;
            v7 = 0;
          }
          v47 = v69;
          v48 = HIDWORD(v53) == 0;
          *(_DWORD *)(a3 + 112) = v33;
          *(_DWORD *)(a3 + 40) = !v48;
          *(_DWORD *)(a3 + 44) = v54 != 0;
          *(_DWORD *)(a3 + 48) = v55 != 0;
          *(_DWORD *)(a3 + 52) = v56 != 0;
          *(_DWORD *)(a3 + 64) = v30 != 0;
          if ( v47 )
          {
            *(_DWORD *)(a3 + 80) = v71;
            v71 = 0;
            *(_QWORD *)(a3 + 88) = v47;
            v69 = 0;
          }
          v49 = v70;
          if ( v70 )
          {
            *(_DWORD *)(a3 + 96) = v72;
            v72 = 0;
            *(_QWORD *)(a3 + 104) = v49;
            v70 = 0;
          }
        }
        else
        {
          v46 = BYTE1(xmmword_1801119E0);
          if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
          {
            WPP_SF_S(1035, v10 + 21, WPP_75ba1181f9a6332c212052b3f273b20c_Traceguids, L"DnscacheTcpipInterfaces");
            v46 = BYTE1(xmmword_1801119E0);
          }
          v44 = 30;
          v10 = 30;
          if ( (v46 & 8) != 0 )
          {
            v13 = 22;
            goto LABEL_88;
          }
        }
      }
      else
      {
        v45 = BYTE1(xmmword_1801119E0);
        if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
        {
          WPP_SF_S(1035, v10 + 18, WPP_75ba1181f9a6332c212052b3f273b20c_Traceguids, L"DnscacheTcpip6Interfaces");
          v45 = BYTE1(xmmword_1801119E0);
        }
        v44 = 30;
        v10 = 30;
        if ( (v45 & 8) != 0 )
        {
          v13 = 19;
          goto LABEL_88;
        }
      }
    }
    else
    {
      v43 = BYTE1(xmmword_1801119E0);
      if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
      {
        WPP_SF_(1035, v10 + 15, WPP_75ba1181f9a6332c212052b3f273b20c_Traceguids);
        v43 = BYTE1(xmmword_1801119E0);
      }
      v44 = 30;
      v10 = 30;
      if ( (v43 & 8) != 0 )
      {
        v13 = 16;
LABEL_88:
        WPP_SF_d(1035, v13, WPP_75ba1181f9a6332c212052b3f273b20c_Traceguids, v44);
      }
    }
  }
LABEL_89:
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( v68 )
  {
    RegCloseKey(v68);
    v68 = 0;
  }
  if ( v66 )
  {
    RegCloseKey(v66);
    v66 = 0;
  }
  DnsApiFree(lpMem);
  DnsApiFree(v62);
  DnsApiFree(v5);
  DnsApiFree(v6);
  DnsApiFree(v7);
  DnsFreeServerProperties(&v71, &v69);
  DnsFreeServerProperties(&v72, &v70);
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_d(1035, 23, WPP_75ba1181f9a6332c212052b3f273b20c_Traceguids, v10);
  return v10;
}

```

## disassembly

```asm
0x18007d84c  mov     [rsp-8+arg_18], rbx
0x18007d851  push    rbp
0x18007d852  push    rsi
0x18007d853  push    rdi
0x18007d854  push    r12
0x18007d856  push    r13
0x18007d858  push    r14
0x18007d85a  push    r15
0x18007d85c  lea     rbp, [rsp-10h]
0x18007d861  sub     rsp, 110h
0x18007d868  mov     rax, cs:__security_cookie
0x18007d86f  xor     rax, rsp
0x18007d872  mov     [rbp+40h+var_40], rax
0x18007d876  xor     ebx, ebx
0x18007d878  mov     rdi, r8
0x18007d87b  mov     [rbp+40h+hKey], rbx
0x18007d87f  mov     esi, ebx
0x18007d881  mov     [rbp+40h+var_80], rbx
0x18007d885  mov     r14d, ebx
0x18007d888  mov     [rbp+40h+var_90], rbx
0x18007d88c  mov     r15d, ebx
0x18007d88f  mov     dword ptr [rsp+140h+var_E0], ebx
0x18007d893  mov     r13, rdx
0x18007d896  mov     [rbp+40h+lpMem], rbx
0x18007d89a  mov     r12, rcx
0x18007d89d  mov     [rbp+40h+var_A8], rbx
0x18007d8a1  mov     [rbp+40h+var_C0], rbx
0x18007d8a5  mov     [rbp+40h+var_B8], rbx
0x18007d8a9  mov     [rbp+40h+var_98], rbx
0x18007d8ad  mov     dword ptr [rsp+140h+var_E0+4], ebx
0x18007d8b1  mov     [rsp+140h+var_D8], ebx
0x18007d8b5  mov     [rsp+140h+var_D4], ebx
0x18007d8b9  mov     [rsp+140h+var_D0], ebx
0x18007d8bd  mov     [rbp+40h+var_A0], ebx
0x18007d8c0  mov     [rsp+140h+var_CC], ebx
0x18007d8c4  mov     [rbp+40h+var_68], ebx
0x18007d8c7  mov     [rbp+40h+var_64], ebx
0x18007d8ca  mov     [rbp+40h+var_78], rbx
0x18007d8ce  mov     [rbp+40h+var_70], rbx
0x18007d8d2  mov     qword ptr [rbp+40h+var_58.dwLowDateTime], rbx
0x18007d8d6  mov     qword ptr [rbp+40h+ftLastWriteTime.dwLowDateTime], rbx
0x18007d8da  mov     qword ptr [rbp+40h+var_50.dwLowDateTime], rbx
0x18007d8de  mov     qword ptr [rbp+40h+var_60.dwLowDateTime], rbx
0x18007d8e2  mov     [rbp+40h+var_9C], ebx
0x18007d8e5  mov     [rsp+140h+var_C8], ebx
0x18007d8e9  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18007d8f0  jz      short loc_18007D90E
0x18007d8f2  mov     [rsp+140h+lpcbMaxSubKeyLen], r8
0x18007d8f7  lea     edx, [rbx+0Ah]
0x18007d8fa  lea     r8, WPP_75ba1181f9a6332c212052b3f273b20c_Traceguids
0x18007d901  mov     [rsp+140h+lpcSubKeys], r13
0x18007d906  mov     r9, rcx
0x18007d909  call    WPP_SF_SSq
0x18007d90e  lea     rax, [rbp+40h+hKey]
0x18007d912  mov     r8, r12
0x18007d915  mov     [rsp+140h+lpcValues], rax
0x18007d91a  lea     rdx, aSystemCurrentc_3; "System\\CurrentControlSet\\Services\\Tc"...
0x18007d921  mov     dword ptr [rsp+140h+lpcbMaxClassLen], ebx
0x18007d925  lea     rcx, aDnscachetcpipi; "DnscacheTcpipInterfaces"
0x18007d92c  mov     dword ptr [rsp+140h+lpcSubKeys], 20019h
0x18007d934  call    CreatePersistedRegistryKeyHelper
0x18007d939  mov     ebx, eax
0x18007d93b  test    eax, eax
0x18007d93d  jnz     loc_18007E0A2
0x18007d943  mov     rcx, [rbp+40h+hKey]; hKey
0x18007d947  lea     rax, [rbp+40h+ftLastWriteTime]
0x18007d94b  mov     [rsp+140h+lpftLastWriteTime], rax; lpftLastWriteTime
0x18007d950  xor     r9d, r9d; lpReserved
0x18007d953  mov     [rsp+140h+lpcbSecurityDescriptor], rsi; lpcbSecurityDescriptor
0x18007d958  xor     r8d, r8d; lpcchClass
0x18007d95b  mov     [rsp+140h+lpcbMaxValueLen], rsi; lpcbMaxValueLen
0x18007d960  xor     edx, edx; lpClass
0x18007d962  mov     [rsp+140h+lpcbMaxValueNameLen], rsi; lpcbMaxValueNameLen
0x18007d967  mov     [rsp+140h+lpcValues], rsi; lpcValues
0x18007d96c  mov     [rsp+140h+lpcbMaxClassLen], rsi; lpcbMaxClassLen
0x18007d971  mov     [rsp+140h+lpcbMaxSubKeyLen], rsi; lpcbMaxSubKeyLen
0x18007d976  mov     [rsp+140h+lpcSubKeys], rsi; lpcSubKeys
0x18007d97b  call    cs:__imp_RegQueryInfoKeyW
0x18007d982  nop     dword ptr [rax+rax+00h]
0x18007d987  mov     ebx, eax
0x18007d989  test    eax, eax
0x18007d98b  jnz     loc_18007E080
0x18007d991  test    byte ptr [rdi+8], 1
0x18007d995  jz      loc_18007DA31
0x18007d99b  lea     rax, [rbp+40h+var_80]
0x18007d99f  mov     r8, r12
0x18007d9a2  mov     [rsp+140h+lpcValues], rax
0x18007d9a7  lea     rdx, aSystemCurrentc_0; "System\\CurrentControlSet\\Services\\Tc"...
0x18007d9ae  mov     dword ptr [rsp+140h+lpcbMaxClassLen], esi
0x18007d9b2  lea     rcx, aDnscachetcpip6; "DnscacheTcpip6Interfaces"
0x18007d9b9  mov     dword ptr [rsp+140h+lpcSubKeys], 20019h
0x18007d9c1  call    CreatePersistedRegistryKeyHelper
0x18007d9c6  mov     ebx, eax
0x18007d9c8  test    eax, eax
0x18007d9ca  jnz     loc_18007E0A2
0x18007d9d0  mov     rcx, [rbp+40h+var_80]; hKey
0x18007d9d4  lea     rax, [rbp+40h+var_50]
0x18007d9d8  mov     [rsp+140h+lpftLastWriteTime], rax; lpftLastWriteTime
0x18007d9dd  xor     r9d, r9d; lpReserved
0x18007d9e0  mov     [rsp+140h+lpcbSecurityDescriptor], rsi; lpcbSecurityDescriptor
0x18007d9e5  xor     r8d, r8d; lpcchClass
0x18007d9e8  mov     [rsp+140h+lpcbMaxValueLen], rsi; lpcbMaxValueLen
0x18007d9ed  xor     edx, edx; lpClass
0x18007d9ef  mov     [rsp+140h+lpcbMaxValueNameLen], rsi; lpcbMaxValueNameLen
0x18007d9f4  mov     [rsp+140h+lpcValues], rsi; lpcValues
0x18007d9f9  mov     [rsp+140h+lpcbMaxClassLen], rsi; lpcbMaxClassLen
0x18007d9fe  mov     [rsp+140h+lpcbMaxSubKeyLen], rsi; lpcbMaxSubKeyLen
0x18007da03  mov     [rsp+140h+lpcSubKeys], rsi; lpcSubKeys
0x18007da08  call    cs:__imp_RegQueryInfoKeyW
0x18007da0f  nop     dword ptr [rax+rax+00h]
0x18007da14  mov     ebx, eax
0x18007da16  test    eax, eax
0x18007da18  jz      short loc_18007DA31
0x18007da1a  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18007da21  jz      loc_18007E0A2
0x18007da27  mov     edx, 0Ch
0x18007da2c  jmp     loc_18007E08E
0x18007da31  lea     rax, [rbp+40h+var_90]
0x18007da35  mov     r8, r13
0x18007da38  mov     [rsp+140h+lpcValues], rax
0x18007da3d  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Dn"...
0x18007da44  mov     dword ptr [rsp+140h+lpcbMaxClassLen], esi
0x18007da48  lea     rcx, aDnscache_1; "Dnscache"
0x18007da4f  mov     dword ptr [rsp+140h+lpcSubKeys], 20019h
0x18007da57  call    CreatePersistedRegistryKeyHelper
0x18007da5c  mov     rcx, [rbp+40h+var_90]; hKey
0x18007da60  xor     r13d, r13d
0x18007da63  test    rcx, rcx
0x18007da66  jz      short loc_18007DAC4
0x18007da68  lea     rax, [rbp+40h+var_58]
0x18007da6c  xor     r9d, r9d; lpReserved
0x18007da6f  mov     [rsp+140h+lpftLastWriteTime], rax; lpftLastWriteTime
0x18007da74  xor     r8d, r8d; lpcchClass
0x18007da77  mov     [rsp+140h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x18007da7c  xor     edx, edx; lpClass
0x18007da7e  mov     [rsp+140h+lpcbMaxValueLen], r13; lpcbMaxValueLen
0x18007da83  mov     [rsp+140h+lpcbMaxValueNameLen], r13; lpcbMaxValueNameLen
0x18007da88  mov     [rsp+140h+lpcValues], r13; lpcValues
0x18007da8d  mov     [rsp+140h+lpcbMaxClassLen], r13; lpcbMaxClassLen
0x18007da92  mov     [rsp+140h+lpcbMaxSubKeyLen], r13; lpcbMaxSubKeyLen
0x18007da97  mov     [rsp+140h+lpcSubKeys], r13; lpcSubKeys
0x18007da9c  call    cs:__imp_RegQueryInfoKeyW
0x18007daa3  nop     dword ptr [rax+rax+00h]
0x18007daa8  mov     ebx, eax
0x18007daaa  test    eax, eax
0x18007daac  jz      short loc_18007DAC4
0x18007daae  test    byte ptr cs:xmmword_1801119E0+1, 8
0x18007dab5  jz      loc_18007E0A2
0x18007dabb  lea     edx, [r13+0Dh]
0x18007dabf  jmp     loc_18007E08E
0x18007dac4  mov     rbx, [rbp+40h+hKey]
0x18007dac8  mov     ecx, 3Fh ; '?'
0x18007dacd  call    regValueNameForId
0x18007dad2  mov     rdx, rax
0x18007dad5  lea     r8, [rsp+140h+var_E0+4]
0x18007dada  mov     rcx, rbx
0x18007dadd  call    privateRegReadDwordValue
0x18007dae2  mov     ecx, dword ptr [rsp+140h+var_E0+4]
0x18007dae6  test    eax, eax
0x18007dae8  mov     eax, 1
0x18007daed  cmovnz  ecx, eax
0x18007daf0  mov     dword ptr [rsp+140h+var_E0+4], ecx
0x18007daf4  lea     ecx, [rax+40h]
0x18007daf7  call    regValueNameForId
0x18007dafc  mov     rdx, rax
0x18007daff  lea     r8, [rsp+140h+var_D8]
0x18007db04  mov     rcx, rbx
0x18007db07  call    privateRegReadDwordValue
0x18007db0c  mov     edx, [rsp+140h+var_D8]
0x18007db10  test    eax, eax
0x18007db12  mov     ecx, 5Ch ; '\'
0x18007db17  cmovnz  edx, r13d
0x18007db1b  mov     [rsp+140h+var_D8], edx
0x18007db1f  call    regValueNameForId
0x18007db24  mov     rdx, rax
0x18007db27  lea     r8, [rsp+140h+var_D4]
0x18007db2c  mov     rcx, rbx
0x18007db2f  call    privateRegReadDwordValue
0x18007db34  mov     ecx, [rsp+140h+var_D4]
0x18007db38  test    eax, eax
0x18007db3a  mov     edx, 3
0x18007db3f  cmovnz  ecx, edx
0x18007db42  mov     [rsp+140h+var_D4], ecx
0x18007db46  lea     ecx, [rdx+7]
0x18007db49  call    regValueNameForId
0x18007db4e  mov     rdx, rax
0x18007db51  lea     r8, [rsp+140h+var_D0]
0x18007db56  mov     rcx, rbx
0x18007db59  call    privateRegReadDwordValue
0x18007db5e  mov     ecx, [rsp+140h+var_D0]
0x18007db62  test    eax, eax
0x18007db64  mov     r9, [rbp+40h+var_90]
0x18007db68  mov     r8d, 1
0x18007db6e  cmovnz  ecx, r8d
0x18007db72  mov     [rsp+140h+var_D0], ecx
0x18007db76  test    r9, r9
0x18007db79  jz      short loc_18007DBCD
0x18007db7b  lea     ecx, [r8+71h]
0x18007db7f  call    regValueNameForId
0x18007db84  mov     rdx, rax
0x18007db87  lea     r8, [rsp+140h+var_CC]
0x18007db8c  mov     rcx, r9
0x18007db8f  call    privateRegReadDwordValue
0x18007db94  mov     r12d, [rsp+140h+var_CC]
0x18007db99  test    eax, eax
0x18007db9b  mov     ecx, 37h ; '7'
0x18007dba0  cmovnz  r12d, r13d
0x18007dba4  call    regValueNameForId
0x18007dba9  mov     rcx, [rbp+40h+var_90]
0x18007dbad  lea     r8, [rsp+140h+var_C8]
0x18007dbb2  mov     rdx, rax
0x18007dbb5  call    privateRegReadDwordValue
0x18007dbba  mov     r13d, [rsp+140h+var_C8]
0x18007dbbf  xor     ecx, ecx
0x18007dbc1  test    eax, eax
0x18007dbc3  cmovnz  r13d, ecx
0x18007dbc7  lea     r8d, [rcx+1]
0x18007dbcb  jmp     short loc_18007DBD5
0x18007dbcd  mov     r12d, [rbp+40h+var_A0]
0x18007dbd1  mov     r13d, [rbp+40h+var_9C]
0x18007dbd5  mov     ecx, r8d
0x18007dbd8  call    regValueNameForId
0x18007dbdd  mov     rdx, rax; lpValueName
0x18007dbe0  lea     r9, [rbp+40h+lpMem]
0x18007dbe4  lea     rax, [rsp+140h+var_E0]
0x18007dbe9  mov     rcx, rbx; hKey
0x18007dbec  mov     [rsp+140h+lpcSubKeys], rax; __int64
0x18007dbf1  call    privateRegReadStringValueW
0x18007dbf6  cmp     eax, 0Eh
0x18007dbf9  jnz     short loc_18007DC05
0x18007dbfb  mov     ebx, 0Eh
0x18007dc00  jmp     loc_18007E0A2
0x18007dc05  mov     r8d, 1
0x18007dc0b  test    [rdi+8], r8b
0x18007dc0f  cmovnz  rbx, [rbp+40h+var_80]
0x18007dc14  lea     ecx, [r8+8]
0x18007dc18  call    regValueNameForId
0x18007dc1d  mov     rdx, rax; lpValueName
0x18007dc20  lea     r9, [rbp+40h+var_A8]
0x18007dc24  lea     rax, [rsp+140h+var_E0]
0x18007dc29  mov     rcx, rbx; hKey
0x18007dc2c  mov     [rsp+140h+lpcSubKeys], rax; __int64
0x18007dc31  call    privateRegReadStringValueW
0x18007dc36  cmp     eax, 0Eh
0x18007dc39  jz      short loc_18007DBFB
0x18007dc3b  mov     ecx, 7
0x18007dc40  call    regValueNameForId
0x18007dc45  mov     rdx, rax; lpValueName
0x18007dc48  lea     r9, [rbp+40h+var_C0]
0x18007dc4c  lea     rax, [rsp+140h+var_E0]
0x18007dc51  mov     esi, 1
0x18007dc56  mov     r8d, esi
0x18007dc59  mov     [rsp+140h+lpcSubKeys], rax; __int64
0x18007dc5e  mov     rcx, rbx; hKey
0x18007dc61  call    privateRegReadStringValueW
0x18007dc66  cmp     eax, 0Eh
0x18007dc69  jnz     short loc_18007DC76
0x18007dc6b  mov     rsi, [rbp+40h+var_C0]
0x18007dc6f  mov     ebx, eax
0x18007dc71  jmp     loc_18007E0A2
0x18007dc76  mov     ecx, 8
0x18007dc7b  call    regValueNameForId
0x18007dc80  mov     rdx, rax; lpValueName
0x18007dc83  lea     r9, [rbp+40h+var_B8]
0x18007dc87  lea     rax, [rsp+140h+var_E0]
0x18007dc8c  mov     r8d, esi
0x18007dc8f  mov     rcx, rbx; hKey
0x18007dc92  mov     [rsp+140h+lpcSubKeys], rax; __int64
0x18007dc97  call    privateRegReadStringValueW
0x18007dc9c  mov     ebx, 0Eh
0x18007dca1  cmp     eax, ebx
0x18007dca3  jnz     short loc_18007DCB2
0x18007dca5  mov     rsi, [rbp+40h+var_C0]
0x18007dca9  mov     r14, [rbp+40h+var_B8]
0x18007dcad  jmp     loc_18007E0A2
0x18007dcb2  mov     r10, [rbp+40h+var_90]
0x18007dcb6  test    r10, r10
0x18007dcb9  jz      short loc_18007DCED
0x18007dcbb  mov     ecx, 73h ; 's'
0x18007dcc0  call    regValueNameForId
0x18007dcc5  mov     rdx, rax; lpValueName
0x18007dcc8  lea     r9, [rbp+40h+var_98]
0x18007dccc  lea     rax, [rsp+140h+var_E0]
0x18007dcd1  mov     r8d, esi
0x18007dcd4  mov     rcx, r10; hKey
0x18007dcd7  mov     [rsp+140h+lpcSubKeys], rax; __int64
0x18007dcdc  call    privateRegReadStringValueW
0x18007dce1  mov     r15, [rbp+40h+var_98]
0x18007dce5  cmp     eax, ebx
0x18007dce7  jz      short loc_18007DCA5
0x18007dce9  mov     r10, [rbp+40h+var_90]
0x18007dced  mov     rsi, [rbp+40h+var_C0]
0x18007dcf1  mov     r14, [rbp+40h+var_B8]
0x18007dcf5  test    rsi, rsi
0x18007dcf8  jnz     short loc_18007DCFF
0x18007dcfa  test    r14, r14
0x18007dcfd  jz      short loc_18007DD43
0x18007dcff  mov     edx, [rdi+8]
0x18007dd02  lea     rax, [rbp+40h+var_70]
0x18007dd06  mov     [rsp+140h+lpcValues], rax
  ... truncated ...
```
