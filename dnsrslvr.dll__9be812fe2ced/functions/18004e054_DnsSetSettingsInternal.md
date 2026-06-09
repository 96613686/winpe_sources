# DnsSetSettingsInternal

- ea: `0x18004e054`
- end: `0x18004e461`
- name: `DnsSetSettingsInternal`
- size: `1037`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, service_task, installer_update`

## callers

- `0x18004fca0`

## callees

- `0x180004aa8`
- `0x18001f118`
- `0x18002025c`
- `0x18003431c`
- `0x180046ec0`
- `0x18004e054`
- `0x1800862fc`
- `0x1800864ac`
- `0x180086b1c`
- `0x180086f24`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004e415`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004e424`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004e415`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004e424`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004e1a4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004e216`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004e282`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004e1a4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004e216`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004e282`

## string_xrefs

- `0x18004e140`: `SYSTEM\CurrentControlSet\Services\Dnscache`
- `0x18004e150`: `Dnscache`
- `0x18004e109`: `DnscacheTcpipParameters`
- `0x18004e0fe`: `System\CurrentControlSet\Services\Tcpip\Parameters`

## pseudocode

```c
__int64 __fastcall DnsSetSettingsInternal(__int64 a1)
{
  unsigned int PersistedRegistryKeyHelper; // eax
  int v3; // r9d
  unsigned int v4; // ebx
  int v5; // r9d
  LSTATUS v6; // eax
  LSTATUS v7; // esi
  LSTATUS v8; // eax
  LSTATUS v9; // esi
  LSTATUS v10; // eax
  LSTATUS v11; // esi
  BYTE *v12; // r8
  unsigned int v13; // eax
  unsigned int v14; // esi
  BYTE *v15; // r8
  unsigned int v16; // eax
  unsigned int v17; // esi
  BYTE *v18; // r8
  unsigned int v19; // eax
  unsigned int v20; // esi
  __int64 v21; // rdx
  HKEY v23; // [rsp+40h] [rbp-38h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-30h] BYREF
  BYTE Data[4]; // [rsp+50h] [rbp-28h] BYREF
  BYTE lpData[4]; // [rsp+54h] [rbp-24h] BYREF
  BYTE v27[8]; // [rsp+58h] [rbp-20h] BYREF

  v23 = 0;
  hKey = 0;
  *(_DWORD *)v27 = 0;
  *(_DWORD *)Data = 0;
  *(_DWORD *)lpData = 0;
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_q(1035, 147, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids, a1);
  if ( !a1 || *(_DWORD *)a1 != 1 )
  {
    v4 = 87;
    goto LABEL_53;
  }
  PersistedRegistryKeyHelper = Rpc_DnsRegistryAccessCheck(0x20006u, qword_180094C40);
  v4 = PersistedRegistryKeyHelper;
  if ( PersistedRegistryKeyHelper )
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
      goto LABEL_53;
    v21 = 148;
    goto LABEL_51;
  }
  PersistedRegistryKeyHelper = CreatePersistedRegistryKeyHelper(
                                 (unsigned int)L"DnscacheTcpipParameters",
                                 (unsigned int)L"System\\CurrentControlSet\\Services\\Tcpip\\Parameters",
                                 0,
                                 v3,
                                 131078,
                                 0,
                                 0,
                                 (__int64)&v23);
  v4 = PersistedRegistryKeyHelper;
  if ( PersistedRegistryKeyHelper )
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
      goto LABEL_53;
    v21 = 149;
    goto LABEL_51;
  }
  PersistedRegistryKeyHelper = CreatePersistedRegistryKeyHelper(
                                 (unsigned int)L"Dnscache",
                                 (unsigned int)L"SYSTEM\\CurrentControlSet\\Services\\Dnscache",
                                 (unsigned int)L"Parameters",
                                 v5,
                                 131078,
                                 0,
                                 0,
                                 (__int64)&hKey);
  v4 = PersistedRegistryKeyHelper;
  if ( PersistedRegistryKeyHelper )
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
      goto LABEL_53;
    v21 = 150;
LABEL_51:
    WPP_SF_d(1035, v21, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids, PersistedRegistryKeyHelper);
    goto LABEL_53;
  }
  if ( (*(_DWORD *)(a1 + 8) & 0x8000LL) != 0 )
  {
    *(_DWORD *)Data = (*(_DWORD *)(a1 + 40) >> 6) & 1;
    v6 = RegSetValueExW(hKey, L"EnableDdr", 0, 4u, Data, 4u);
    v7 = v6;
    if ( v6 )
    {
      if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
        WPP_SF_SdD(
          *(_DWORD *)Data,
          151,
          (unsigned int)WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids,
          (unsigned int)L"EnableDdr",
          Data[0],
          v6);
      v4 = v7;
    }
  }
  if ( (*(_DWORD *)(a1 + 8) & 0x10000) != 0 )
  {
    if ( *(char *)(a1 + 40) < 0 )
      *(_DWORD *)lpData = 1;
    v8 = RegSetValueExW(hKey, L"EnableDot", 0, 4u, lpData, 4u);
    v9 = v8;
    if ( v8 )
    {
      if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
        WPP_SF_SdD(
          *(_DWORD *)lpData,
          152,
          (unsigned int)WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids,
          (unsigned int)L"EnableDot",
          lpData[0],
          v8);
      v4 = v9;
    }
  }
  if ( (*(_DWORD *)(a1 + 8) & 0x1000LL) != 0 )
  {
    *(_DWORD *)v27 = *(_DWORD *)(a1 + 40) & 3;
    v10 = RegSetValueExW(hKey, L"EnableAutoDoh", 0, 4u, v27, 4u);
    v11 = v10;
    if ( v10 )
    {
      if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
        WPP_SF_SdD(
          *(_DWORD *)v27,
          153,
          (unsigned int)WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids,
          (unsigned int)L"EnableAutoDoh",
          v27[0],
          v10);
      v4 = v11;
    }
  }
  if ( (*(_BYTE *)(a1 + 8) & 0x40) != 0 )
  {
    v12 = *(BYTE **)(a1 + 16);
    if ( v12 )
    {
      v13 = SetRegistryString(v23, RegPropertyTable, v12);
      v14 = v13;
      if ( v13 )
      {
        if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
          WPP_SF_SSD(
            *(_QWORD *)(a1 + 16),
            154,
            (unsigned int)WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids,
            (_DWORD)RegPropertyTable,
            *(_QWORD *)(a1 + 16),
            v13);
        v4 = v14;
      }
    }
  }
  if ( (*(_BYTE *)(a1 + 8) & 0x20) != 0 )
  {
    v15 = *(BYTE **)(a1 + 24);
    if ( v15 )
    {
      v16 = SetRegistryString(v23, L"Domain", v15);
      v17 = v16;
      if ( v16 )
      {
        if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
          WPP_SF_SSD(
            *(_QWORD *)(a1 + 24),
            155,
            (unsigned int)WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids,
            (unsigned int)L"Domain",
            *(_QWORD *)(a1 + 24),
            v16);
        v4 = v17;
      }
    }
  }
  if ( (*(_BYTE *)(a1 + 8) & 4) != 0 )
  {
    v18 = *(BYTE **)(a1 + 32);
    if ( v18 )
    {
      v19 = SetRegistryString(v23, L"SearchList", v18);
      v20 = v19;
      if ( v19 )
      {
        if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
          WPP_SF_SSD(
            *(_QWORD *)(a1 + 32),
            156,
            (unsigned int)WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids,
            (unsigned int)L"SearchList",
            *(_QWORD *)(a1 + 32),
            v19);
        v4 = v20;
      }
    }
  }
  if ( *(_QWORD *)(a1 + 8) )
  {
    UpdateNetworkInfo(0, 0);
    UpdateNetworkInfo(0, 1);
  }
LABEL_53:
  if ( v23 )
    RegCloseKey(v23);
  if ( hKey )
    RegCloseKey(hKey);
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_d(1035, 157, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids, v4);
  return v4;
}

```

## disassembly

```asm
0x18004e054  push    rbp
0x18004e056  push    rbx
0x18004e057  push    rsi
0x18004e058  push    rdi
0x18004e059  push    r12
0x18004e05b  push    r13
0x18004e05d  mov     rbp, rsp
0x18004e060  sub     rsp, 78h
0x18004e064  mov     rax, cs:__security_cookie
0x18004e06b  xor     rax, rsp
0x18004e06e  mov     [rbp+var_18], rax
0x18004e072  mov     rdi, rcx
0x18004e075  mov     [rbp+var_38], 0
0x18004e07d  mov     [rbp+hKey], 0
0x18004e085  mov     dword ptr [rbp+var_20], 0
0x18004e08c  mov     dword ptr [rbp+Data], 0
0x18004e093  mov     dword ptr [rbp+var_24], 0
0x18004e09a  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18004e0a1  lea     r12, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids
0x18004e0a8  mov     r13d, 40Bh
0x18004e0ae  jz      short loc_18004E0C3
0x18004e0b0  mov     edx, 93h
0x18004e0b5  mov     ecx, r13d
0x18004e0b8  mov     r9, rdi
0x18004e0bb  mov     r8, r12
0x18004e0be  call    WPP_SF_q
0x18004e0c3  test    rdi, rdi
0x18004e0c6  jz      loc_18004E407
0x18004e0cc  cmp     dword ptr [rdi], 1
0x18004e0cf  jnz     loc_18004E407
0x18004e0d5  mov     esi, 20006h
0x18004e0da  lea     rdx, qword_180094C40; pSecurityDescriptor
0x18004e0e1  mov     ecx, esi; DesiredAccess
0x18004e0e3  call    Rpc_DnsRegistryAccessCheck
0x18004e0e8  mov     ebx, eax
0x18004e0ea  test    eax, eax
0x18004e0ec  jnz     loc_18004E3E9
0x18004e0f2  lea     rax, [rbp+var_38]
0x18004e0f6  xor     r8d, r8d
0x18004e0f9  mov     [rsp+78h+var_40], rax
0x18004e0fe  lea     rdx, aSystemCurrentc_5; "System\\CurrentControlSet\\Services\\Tc"...
0x18004e105  mov     [rsp+78h+var_48], ebx
0x18004e109  lea     rcx, aDnscachetcpipp; "DnscacheTcpipParameters"
0x18004e110  mov     qword ptr [rsp+78h+cbData], 0
0x18004e119  mov     dword ptr [rsp+78h+lpData], esi
0x18004e11d  call    CreatePersistedRegistryKeyHelper
0x18004e122  mov     ebx, eax
0x18004e124  test    eax, eax
0x18004e126  jnz     loc_18004E3D9
0x18004e12c  lea     rax, [rbp+hKey]
0x18004e130  mov     [rsp+78h+var_40], rax
0x18004e135  lea     r8, aParameters; "Parameters"
0x18004e13c  mov     [rsp+78h+var_48], ebx
0x18004e140  lea     rdx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Services\\Dn"...
0x18004e147  mov     qword ptr [rsp+78h+cbData], 0
0x18004e150  lea     rcx, aDnscache_0; "Dnscache"
0x18004e157  mov     dword ptr [rsp+78h+lpData], esi
0x18004e15b  call    CreatePersistedRegistryKeyHelper
0x18004e160  mov     ebx, eax
0x18004e162  test    eax, eax
0x18004e164  jnz     loc_18004E3C9
0x18004e16a  mov     eax, [rdi+8]
0x18004e16d  bt      rax, 0Fh
0x18004e172  jnb     short loc_18004E1DA
0x18004e174  mov     eax, [rdi+28h]
0x18004e177  lea     r9d, [rbx+4]; dwType
0x18004e17b  mov     rdx, cs:off_18008AB70; lpValueName
0x18004e182  xor     r8d, r8d; Reserved
0x18004e185  mov     rcx, [rbp+hKey]; hKey
0x18004e189  shr     rax, 6
0x18004e18d  and     eax, 1
0x18004e190  mov     [rsp+78h+cbData], 4; cbData
0x18004e198  mov     dword ptr [rbp+Data], eax
0x18004e19b  lea     rax, [rbp+Data]
0x18004e19f  mov     [rsp+78h+lpData], rax; lpData
0x18004e1a4  call    cs:__imp_RegSetValueExW
0x18004e1aa  mov     esi, eax
0x18004e1ac  test    eax, eax
0x18004e1ae  jz      short loc_18004E1DA
0x18004e1b0  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18004e1b7  jz      short loc_18004E1D8
0x18004e1b9  mov     ecx, dword ptr [rbp+Data]
0x18004e1bc  mov     edx, 97h
0x18004e1c1  mov     r9, cs:off_18008AB70; "EnableDdr"
0x18004e1c8  mov     r8, r12
0x18004e1cb  mov     [rsp+78h+cbData], eax
0x18004e1cf  mov     dword ptr [rsp+78h+lpData], ecx
0x18004e1d3  call    WPP_SF_SdD
0x18004e1d8  mov     ebx, esi
0x18004e1da  mov     eax, [rdi+8]
0x18004e1dd  bt      rax, 10h
0x18004e1e2  jnb     short loc_18004E24C
0x18004e1e4  test    byte ptr [rdi+28h], 80h
0x18004e1e8  jz      short loc_18004E1F1
0x18004e1ea  mov     dword ptr [rbp+var_24], 1
0x18004e1f1  mov     rdx, cs:off_18008AB40; lpValueName
0x18004e1f8  lea     rax, [rbp+var_24]
0x18004e1fc  mov     rcx, [rbp+hKey]; hKey
0x18004e200  mov     r9d, 4; dwType
0x18004e206  mov     [rsp+78h+cbData], 4; cbData
0x18004e20e  xor     r8d, r8d; Reserved
0x18004e211  mov     [rsp+78h+lpData], rax; lpData
0x18004e216  call    cs:__imp_RegSetValueExW
0x18004e21c  mov     esi, eax
0x18004e21e  test    eax, eax
0x18004e220  jz      short loc_18004E24C
0x18004e222  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18004e229  jz      short loc_18004E24A
0x18004e22b  mov     ecx, dword ptr [rbp+var_24]
0x18004e22e  mov     edx, 98h
0x18004e233  mov     r9, cs:off_18008AB40; "EnableDot"
0x18004e23a  mov     r8, r12
0x18004e23d  mov     [rsp+78h+cbData], eax
0x18004e241  mov     dword ptr [rsp+78h+lpData], ecx
0x18004e245  call    WPP_SF_SdD
0x18004e24a  mov     ebx, esi
0x18004e24c  mov     eax, [rdi+8]
0x18004e24f  bt      rax, 0Ch
0x18004e254  jnb     short loc_18004E2B8
0x18004e256  mov     eax, [rdi+28h]
0x18004e259  mov     ecx, 4
0x18004e25e  mov     rdx, cs:off_18008AB30; lpValueName
0x18004e265  and     eax, 3
0x18004e268  mov     [rsp+78h+cbData], ecx; cbData
0x18004e26c  mov     r9d, ecx; dwType
0x18004e26f  mov     rcx, [rbp+hKey]; hKey
0x18004e273  xor     r8d, r8d; Reserved
0x18004e276  mov     dword ptr [rbp+var_20], eax
0x18004e279  lea     rax, [rbp+var_20]
0x18004e27d  mov     [rsp+78h+lpData], rax; lpData
0x18004e282  call    cs:__imp_RegSetValueExW
0x18004e288  mov     esi, eax
0x18004e28a  test    eax, eax
0x18004e28c  jz      short loc_18004E2B8
0x18004e28e  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18004e295  jz      short loc_18004E2B6
0x18004e297  mov     ecx, dword ptr [rbp+var_20]
0x18004e29a  mov     edx, 99h
0x18004e29f  mov     r9, cs:off_18008AB30; "EnableAutoDoh"
0x18004e2a6  mov     r8, r12
0x18004e2a9  mov     [rsp+78h+cbData], eax
0x18004e2ad  mov     dword ptr [rsp+78h+lpData], ecx
0x18004e2b1  call    WPP_SF_SdD
0x18004e2b6  mov     ebx, esi
0x18004e2b8  test    byte ptr [rdi+8], 40h
0x18004e2bc  jz      short loc_18004E309
0x18004e2be  mov     r8, [rdi+10h]; lpData
0x18004e2c2  test    r8, r8
0x18004e2c5  jz      short loc_18004E309
0x18004e2c7  mov     rdx, cs:RegPropertyTable; lpValueName
0x18004e2ce  mov     rcx, [rbp+var_38]; hKey
0x18004e2d2  call    SetRegistryString
0x18004e2d7  mov     esi, eax
0x18004e2d9  test    eax, eax
0x18004e2db  jz      short loc_18004E309
0x18004e2dd  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18004e2e4  jz      short loc_18004E307
0x18004e2e6  mov     rcx, [rdi+10h]
0x18004e2ea  mov     edx, 9Ah
0x18004e2ef  mov     r9, cs:RegPropertyTable
0x18004e2f6  mov     r8, r12
0x18004e2f9  mov     [rsp+78h+cbData], eax
0x18004e2fd  mov     [rsp+78h+lpData], rcx
0x18004e302  call    WPP_SF_SSD
0x18004e307  mov     ebx, esi
0x18004e309  test    byte ptr [rdi+8], 20h
0x18004e30d  jz      short loc_18004E35A
0x18004e30f  mov     r8, [rdi+18h]; lpData
0x18004e313  test    r8, r8
0x18004e316  jz      short loc_18004E35A
0x18004e318  mov     rdx, cs:off_18008A840; lpValueName
0x18004e31f  mov     rcx, [rbp+var_38]; hKey
0x18004e323  call    SetRegistryString
0x18004e328  mov     esi, eax
0x18004e32a  test    eax, eax
0x18004e32c  jz      short loc_18004E35A
0x18004e32e  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18004e335  jz      short loc_18004E358
0x18004e337  mov     rcx, [rdi+18h]
0x18004e33b  mov     edx, 9Bh
0x18004e340  mov     r9, cs:off_18008A840; "Domain"
0x18004e347  mov     r8, r12
0x18004e34a  mov     [rsp+78h+cbData], eax
0x18004e34e  mov     [rsp+78h+lpData], rcx
0x18004e353  call    WPP_SF_SSD
0x18004e358  mov     ebx, esi
0x18004e35a  test    byte ptr [rdi+8], 4
0x18004e35e  jz      short loc_18004E3AB
0x18004e360  mov     r8, [rdi+20h]; lpData
0x18004e364  test    r8, r8
0x18004e367  jz      short loc_18004E3AB
0x18004e369  mov     rdx, cs:off_18008A8C0; lpValueName
0x18004e370  mov     rcx, [rbp+var_38]; hKey
0x18004e374  call    SetRegistryString
0x18004e379  mov     esi, eax
0x18004e37b  test    eax, eax
0x18004e37d  jz      short loc_18004E3AB
0x18004e37f  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18004e386  jz      short loc_18004E3A9
0x18004e388  mov     rcx, [rdi+20h]
0x18004e38c  mov     edx, 9Ch
0x18004e391  mov     r9, cs:off_18008A8C0; "SearchList"
0x18004e398  mov     r8, r12
0x18004e39b  mov     [rsp+78h+cbData], eax
0x18004e39f  mov     [rsp+78h+lpData], rcx
0x18004e3a4  call    WPP_SF_SSD
0x18004e3a9  mov     ebx, esi
0x18004e3ab  cmp     qword ptr [rdi+8], 0
0x18004e3b0  jz      short loc_18004E40C
0x18004e3b2  xor     edx, edx
0x18004e3b4  xor     ecx, ecx
0x18004e3b6  call    UpdateNetworkInfo
0x18004e3bb  mov     edx, 1
0x18004e3c0  xor     ecx, ecx
0x18004e3c2  call    UpdateNetworkInfo
0x18004e3c7  jmp     short loc_18004E40C
0x18004e3c9  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18004e3d0  jz      short loc_18004E40C
0x18004e3d2  mov     edx, 96h
0x18004e3d7  jmp     short loc_18004E3F7
0x18004e3d9  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18004e3e0  jz      short loc_18004E40C
0x18004e3e2  mov     edx, 95h
0x18004e3e7  jmp     short loc_18004E3F7
0x18004e3e9  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18004e3f0  jz      short loc_18004E40C
0x18004e3f2  mov     edx, 94h
0x18004e3f7  mov     ecx, r13d
0x18004e3fa  mov     r9d, eax
0x18004e3fd  mov     r8, r12
0x18004e400  call    WPP_SF_d
0x18004e405  jmp     short loc_18004E40C
0x18004e407  mov     ebx, 57h ; 'W'
0x18004e40c  mov     rcx, [rbp+var_38]; hKey
0x18004e410  test    rcx, rcx
0x18004e413  jz      short loc_18004E41B
0x18004e415  call    cs:__imp_RegCloseKey
0x18004e41b  mov     rcx, [rbp+hKey]; hKey
0x18004e41f  test    rcx, rcx
0x18004e422  jz      short loc_18004E42A
0x18004e424  call    cs:__imp_RegCloseKey
0x18004e42a  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18004e431  jz      short loc_18004E446
0x18004e433  mov     edx, 9Dh
0x18004e438  mov     ecx, r13d
0x18004e43b  mov     r9d, ebx
0x18004e43e  mov     r8, r12
0x18004e441  call    WPP_SF_d
0x18004e446  mov     eax, ebx
0x18004e448  mov     rcx, [rbp+var_18]
0x18004e44c  xor     rcx, rsp; StackCookie
0x18004e44f  call    __security_check_cookie
0x18004e454  add     rsp, 78h
0x18004e458  pop     r13
0x18004e45a  pop     r12
0x18004e45c  pop     rdi
0x18004e45d  pop     rsi
0x18004e45e  pop     rbx
0x18004e45f  pop     rbp
0x18004e460  retn
```
