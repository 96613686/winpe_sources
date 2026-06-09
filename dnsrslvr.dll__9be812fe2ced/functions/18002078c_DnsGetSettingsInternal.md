# DnsGetSettingsInternal

- ea: `0x18002078c`
- end: `0x180020dd9`
- name: `DnsGetSettingsInternal`
- size: `1613`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, service_task`

## callers

- `0x18001ecb0`

## callees

- `0x180008b00`
- `0x18000b130`
- `0x18001f118`
- `0x18002039c`
- `0x18002078c`
- `0x1800223f0`
- `0x18002ab94`
- `0x18002af78`
- `0x18002b0a4`
- `0x180046ec0`
- `0x180047818`
- `0x18007da0c`
- `0x180086384`
- `0x180086b1c`
- `0x180086f24`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020be7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020d98`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020be7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020d98`
- `KERNELBASE!RegOpenKeyExInternalW` at `0x1800208a4`
- `KERNELBASE!RegOpenKeyExInternalW` at `0x180020919`
- `KERNELBASE!RegOpenKeyExInternalW` at `0x1800208a4`
- `KERNELBASE!RegOpenKeyExInternalW` at `0x180020919`

## string_xrefs

- `0x1800208db`: `SYSTEM\CurrentControlSet\Services\Dnscache`
- `0x1800208e2`: `Dnscache`
- `0x18002086d`: `DnscacheTcpipParameters`
- `0x180020866`: `System\CurrentControlSet\Services\Tcpip\Parameters`

## pseudocode

```c
__int64 __fastcall DnsGetSettingsInternal(__int64 a1)
{
  unsigned int v2; // eax
  unsigned int EncryptionPolicyFlags; // ebx
  int PersistedRegistryLocation; // eax
  unsigned int v5; // eax
  int v6; // eax
  unsigned int v7; // eax
  __int64 v8; // r8
  __int64 v9; // r8
  __int64 v10; // r8
  __int64 v11; // r8
  __int64 v12; // r8
  int v13; // edx
  int v14; // r8d
  int v15; // ecx
  __int64 v16; // rax
  _QWORD *v17; // rdi
  _QWORD *v18; // rax
  __int64 v19; // rax
  __int64 v21; // rdx
  __int64 v22; // r9
  __int64 v23; // [rsp+40h] [rbp-C0h] BYREF
  HKEY v24; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  void *v26; // [rsp+58h] [rbp-A8h] BYREF
  void *v27; // [rsp+60h] [rbp-A0h] BYREF
  void *v28; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v29; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v30; // [rsp+74h] [rbp-8Ch] BYREF
  __int64 v31; // [rsp+78h] [rbp-88h] BYREF
  __int64 v32; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v33[528]; // [rsp+90h] [rbp-70h] BYREF

  hKey = 0;
  v24 = 0;
  v26 = 0;
  v27 = 0;
  v28 = 0;
  LODWORD(v23) = 0;
  v29 = 0;
  v31 = 0;
  v30 = 0;
  v32 = 0;
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_q(1035, 120, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids, a1);
  if ( !a1 || *(_DWORD *)a1 != 1 )
  {
    EncryptionPolicyFlags = 87;
    goto LABEL_43;
  }
  v2 = Rpc_DnsRegistryAccessCheck(0x20019u, qword_180094C40);
  EncryptionPolicyFlags = v2;
  if ( v2 )
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
      goto LABEL_43;
    v21 = 121;
    v22 = v2;
    goto LABEL_79;
  }
  memset_0(v33, 0, 0x20Au);
  hKey = 0;
  PersistedRegistryLocation = WxGetPersistedRegistryLocation(
                                L"DnscacheTcpipParameters",
                                L"System\\CurrentControlSet\\Services\\Tcpip\\Parameters",
                                0,
                                v33,
                                522);
  if ( PersistedRegistryLocation < 0 )
    v5 = WX_WIN32_FROM_HR((unsigned int)PersistedRegistryLocation);
  else
    v5 = RegOpenKeyExInternalW(-2147483646, v33, 0, 131097, &hKey, 0);
  EncryptionPolicyFlags = v5;
  if ( v5 )
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
      goto LABEL_43;
    WPP_SF_SD(1035, 10, (unsigned int)WPP_cf96f6af26f535eeb3b7d66bdedfd114_Traceguids, (unsigned int)v33, v5);
    if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
      goto LABEL_43;
    v21 = 122;
    goto LABEL_67;
  }
  memset_0(v33, 0, 0x20Au);
  v24 = 0;
  v6 = WxGetPersistedRegistryLocation(
         L"Dnscache",
         L"SYSTEM\\CurrentControlSet\\Services\\Dnscache",
         L"Parameters",
         v33,
         522);
  if ( v6 < 0 )
    v7 = WX_WIN32_FROM_HR((unsigned int)v6);
  else
    v7 = RegOpenKeyExInternalW(-2147483646, v33, 0, 131097, &v24, 0);
  EncryptionPolicyFlags = v7;
  if ( v7 )
  {
    if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
      goto LABEL_43;
    WPP_SF_SD(1035, 10, (unsigned int)WPP_cf96f6af26f535eeb3b7d66bdedfd114_Traceguids, (unsigned int)v33, v7);
    if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
      goto LABEL_43;
    v21 = 123;
LABEL_67:
    v22 = EncryptionPolicyFlags;
LABEL_79:
    WPP_SF_d(1035, v21, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids, v22);
    goto LABEL_43;
  }
  EncryptionPolicyFlags = 14;
  if ( privateRegReadValue(hKey, RegPropertyTable, v8, 1, (BYTE *)&v26, (DWORD *)&v23) != 14
    && privateRegReadValue(hKey, L"Domain", v9, 1, (BYTE *)&v27, (DWORD *)&v23) != 14
    && privateRegReadValue(hKey, L"SearchList", v10, 1, (BYTE *)&v28, (DWORD *)&v23) != 14
    && privateRegReadValue(v24, L"EnableDdr", v11, 4, (BYTE *)&v31, (DWORD *)&v23) != 14
    && (!g_fVelocityDnr || privateRegReadValue(v24, L"EnableDnr", v12, 4, (BYTE *)&v31 + 4, (DWORD *)&v23) != 14) )
  {
    EncryptionPolicyFlags = DnsGetEncryptionPolicyFlags(&v32);
    if ( !EncryptionPolicyFlags
      && ((v32 & 0x108) != 0 || (EncryptionPolicyFlags = DnsReadDotSetting(v24, &v30)) == 0)
      && ((v32 & 0x208) != 0 || (EncryptionPolicyFlags = DnsReadDohSetting(v24, &v29)) == 0) )
    {
      if ( v26 )
      {
        *(_QWORD *)(a1 + 16) = v26;
        v26 = 0;
      }
      if ( v27 )
      {
        *(_QWORD *)(a1 + 24) = v27;
        v27 = 0;
      }
      v15 = (int)v28;
      if ( v28 )
      {
        *(_QWORD *)(a1 + 32) = v28;
        v28 = 0;
      }
      v16 = v29;
      if ( v29 )
      {
        if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
        {
          WPP_SF_d(1035, 124, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids, v29);
          v16 = v29;
        }
        v17 = (_QWORD *)(a1 + 40);
        *(_QWORD *)(a1 + 40) |= v16;
      }
      else
      {
        v17 = (_QWORD *)(a1 + 40);
      }
      v18 = v17;
      if ( (_DWORD)v31 )
      {
        if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
          WPP_SF_d(1035, 125, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids, (unsigned int)v31);
        v18 = (_QWORD *)(a1 + 40);
        *(_QWORD *)(a1 + 40) |= 0x40uLL;
      }
      if ( HIDWORD(v31) )
      {
        if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
        {
          WPP_SF_d(1035, 126, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids, HIDWORD(v31));
          v18 = v17;
        }
        *v18 |= 0x400uLL;
      }
      v19 = v30;
      if ( v30 )
      {
        if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
        {
          WPP_SF_d(1035, 127, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids, v30);
          v19 = v30;
        }
        *v17 |= v19;
      }
      if ( v32 )
      {
        if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
          WPP_SF_q(1035, 128, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids, v32);
        *v17 |= v32;
      }
      if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
        WPP_SF_SSSi(v15, v13, v14, *(_QWORD *)(a1 + 16), *(_QWORD *)(a1 + 24), *(_QWORD *)(a1 + 32), *v17);
    }
  }
LABEL_43:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v24 )
    RegCloseKey(v24);
  if ( v26 )
    MIDL_user_free(v26);
  if ( v27 )
    MIDL_user_free(v27);
  if ( v28 )
    MIDL_user_free(v28);
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_d(1035, 130, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids, EncryptionPolicyFlags);
  return EncryptionPolicyFlags;
}

```

## disassembly

```asm
0x18002078c  push    rbp
0x18002078e  push    rbx
0x18002078f  push    rsi
0x180020790  push    rdi
0x180020791  push    r12
0x180020793  push    r13
0x180020795  push    r14
0x180020797  push    r15
0x180020799  lea     rbp, [rsp-1B8h]
0x1800207a1  sub     rsp, 2B8h
0x1800207a8  mov     rax, cs:__security_cookie
0x1800207af  xor     rax, rsp
0x1800207b2  mov     [rbp+1F0h+var_50], rax
0x1800207b9  xor     r14d, r14d
0x1800207bc  mov     rsi, rcx
0x1800207bf  mov     [rsp+2F0h+hKey], r14
0x1800207c4  mov     [rsp+2F0h+var_2A8], r14
0x1800207c9  mov     [rsp+2F0h+var_298], r14
0x1800207ce  mov     [rsp+2F0h+var_290], r14
0x1800207d3  mov     [rsp+2F0h+var_288], r14
0x1800207d8  mov     dword ptr [rsp+2F0h+var_2B0], r14d
0x1800207dd  mov     [rsp+2F0h+var_280], r14d
0x1800207e2  mov     dword ptr [rsp+2F0h+var_278], r14d
0x1800207e7  mov     dword ptr [rsp+2F0h+var_278+4], r14d
0x1800207ec  mov     [rsp+2F0h+var_27C], r14d
0x1800207f1  mov     [rbp+1F0h+var_270], r14
0x1800207f5  mov     r15b, 8
0x1800207f8  lea     r13, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids
0x1800207ff  test    byte ptr cs:xmmword_1800AB5A0+1, r15b
0x180020806  mov     r12d, 40Bh
0x18002080c  jnz     loc_180020BFC
0x180020812  test    rsi, rsi
0x180020815  jz      loc_180020BF2
0x18002081b  mov     edi, 1
0x180020820  cmp     [rsi], edi
0x180020822  jnz     loc_180020BF2
0x180020828  lea     rdx, qword_180094C40; pSecurityDescriptor
0x18002082f  mov     ecx, 20019h; DesiredAccess
0x180020834  call    Rpc_DnsRegistryAccessCheck
0x180020839  mov     ebx, eax
0x18002083b  test    eax, eax
0x18002083d  jnz     loc_180020D73
0x180020843  mov     ebx, 20Ah
0x180020848  lea     rcx, [rbp+1F0h+var_260]; void *
0x18002084c  mov     r8d, ebx; Size
0x18002084f  xor     edx, edx; Val
0x180020851  call    memset_0
0x180020856  lea     r9, [rbp+1F0h+var_260]
0x18002085a  mov     [rsp+2F0h+hKey], r14
0x18002085f  xor     r8d, r8d
0x180020862  mov     dword ptr [rsp+2F0h+var_2D0], ebx
0x180020866  lea     rdx, aSystemCurrentc_5; "System\\CurrentControlSet\\Services\\Tc"...
0x18002086d  lea     rcx, aDnscachetcpipp; "DnscacheTcpipParameters"
0x180020874  call    WxGetPersistedRegistryLocation
0x180020879  test    eax, eax
0x18002087b  js      loc_180020BCF
0x180020881  lea     rax, [rsp+2F0h+hKey]
0x180020886  mov     [rsp+2F0h+var_2C8], r14
0x18002088b  mov     r9d, 20019h
0x180020891  mov     [rsp+2F0h+var_2D0], rax
0x180020896  xor     r8d, r8d
0x180020899  lea     rdx, [rbp+1F0h+var_260]
0x18002089d  mov     rcx, 0FFFFFFFF80000002h
0x1800208a4  call    cs:__imp_RegOpenKeyExInternalW
0x1800208aa  mov     ebx, eax
0x1800208ac  test    eax, eax
0x1800208ae  jnz     loc_180020C14
0x1800208b4  mov     ebx, 20Ah
0x1800208b9  lea     rcx, [rbp+1F0h+var_260]; void *
0x1800208bd  mov     r8d, ebx; Size
0x1800208c0  xor     edx, edx; Val
0x1800208c2  call    memset_0
0x1800208c7  lea     r9, [rbp+1F0h+var_260]
0x1800208cb  mov     [rsp+2F0h+var_2A8], r14
0x1800208d0  lea     r8, aParameters; "Parameters"
0x1800208d7  mov     dword ptr [rsp+2F0h+var_2D0], ebx
0x1800208db  lea     rdx, aSystemCurrentc_0; "SYSTEM\\CurrentControlSet\\Services\\Dn"...
0x1800208e2  lea     rcx, aDnscache_0; "Dnscache"
0x1800208e9  call    WxGetPersistedRegistryLocation
0x1800208ee  test    eax, eax
0x1800208f0  js      loc_180020BDB
0x1800208f6  lea     rax, [rsp+2F0h+var_2A8]
0x1800208fb  mov     [rsp+2F0h+var_2C8], r14
0x180020900  mov     r9d, 20019h
0x180020906  mov     [rsp+2F0h+var_2D0], rax
0x18002090b  xor     r8d, r8d
0x18002090e  lea     rdx, [rbp+1F0h+var_260]
0x180020912  mov     rcx, 0FFFFFFFF80000002h
0x180020919  call    cs:__imp_RegOpenKeyExInternalW
0x18002091f  mov     ebx, eax
0x180020921  test    eax, eax
0x180020923  jnz     loc_180020C5E
0x180020929  mov     rdx, cs:RegPropertyTable; lpValueName
0x180020930  lea     rax, [rsp+2F0h+var_2B0]
0x180020935  mov     rcx, [rsp+2F0h+hKey]; hKey
0x18002093a  mov     r9d, edi
0x18002093d  mov     [rsp+2F0h+var_2C8], rax; __int64
0x180020942  lea     rax, [rsp+2F0h+var_298]
0x180020947  mov     [rsp+2F0h+var_2D0], rax; __int64
0x18002094c  call    privateRegReadValue
0x180020951  mov     ebx, 0Eh
0x180020956  cmp     eax, ebx
0x180020958  jz      loc_180020B04
0x18002095e  mov     rdx, cs:off_18008A840; lpValueName
0x180020965  lea     rax, [rsp+2F0h+var_2B0]
0x18002096a  mov     rcx, [rsp+2F0h+hKey]; hKey
0x18002096f  mov     r9d, edi
0x180020972  mov     [rsp+2F0h+var_2C8], rax; __int64
0x180020977  lea     rax, [rsp+2F0h+var_290]
0x18002097c  mov     [rsp+2F0h+var_2D0], rax; __int64
0x180020981  call    privateRegReadValue
0x180020986  cmp     eax, ebx
0x180020988  jz      loc_180020B04
0x18002098e  mov     rdx, cs:off_18008A8C0; lpValueName
0x180020995  lea     rax, [rsp+2F0h+var_2B0]
0x18002099a  mov     rcx, [rsp+2F0h+hKey]; hKey
0x18002099f  mov     r9d, edi
0x1800209a2  mov     [rsp+2F0h+var_2C8], rax; __int64
0x1800209a7  lea     rax, [rsp+2F0h+var_288]
0x1800209ac  mov     [rsp+2F0h+var_2D0], rax; __int64
0x1800209b1  call    privateRegReadValue
0x1800209b6  cmp     eax, ebx
0x1800209b8  jz      loc_180020B04
0x1800209be  mov     rdx, cs:off_18008AB70; lpValueName
0x1800209c5  lea     rax, [rsp+2F0h+var_2B0]
0x1800209ca  mov     rcx, [rsp+2F0h+var_2A8]; hKey
0x1800209cf  lea     edi, [rbx-0Ah]
0x1800209d2  mov     [rsp+2F0h+var_2C8], rax; __int64
0x1800209d7  mov     r9d, edi
0x1800209da  lea     rax, [rsp+2F0h+var_278]
0x1800209df  mov     [rsp+2F0h+var_2D0], rax; __int64
0x1800209e4  call    privateRegReadValue
0x1800209e9  cmp     eax, ebx
0x1800209eb  jz      loc_180020B04
0x1800209f1  cmp     cs:g_fVelocityDnr, r14d
0x1800209f8  jz      short loc_180020A2A
0x1800209fa  mov     rdx, cs:off_18008AB80; lpValueName
0x180020a01  lea     rax, [rsp+2F0h+var_2B0]
0x180020a06  mov     rcx, [rsp+2F0h+var_2A8]; hKey
0x180020a0b  mov     r9d, edi
0x180020a0e  mov     [rsp+2F0h+var_2C8], rax; __int64
0x180020a13  lea     rax, [rsp+2F0h+var_278+4]
0x180020a18  mov     [rsp+2F0h+var_2D0], rax; __int64
0x180020a1d  call    privateRegReadValue
0x180020a22  cmp     eax, ebx
0x180020a24  jz      loc_180020B04
0x180020a2a  lea     rcx, [rbp+1F0h+var_270]
0x180020a2e  call    DnsGetEncryptionPolicyFlags
0x180020a33  mov     ebx, eax
0x180020a35  test    eax, eax
0x180020a37  jnz     loc_180020B04
0x180020a3d  test    [rbp+1F0h+var_270], 108h
0x180020a45  jz      loc_180020BA3
0x180020a4b  test    [rbp+1F0h+var_270], 208h
0x180020a53  jz      loc_180020B7C
0x180020a59  mov     rcx, [rsp+2F0h+var_298]
0x180020a5e  test    rcx, rcx
0x180020a61  jnz     loc_180020BC1
0x180020a67  mov     rcx, [rsp+2F0h+var_290]
0x180020a6c  test    rcx, rcx
0x180020a6f  jnz     loc_180020C96
0x180020a75  mov     rcx, [rsp+2F0h+var_288]
0x180020a7a  test    rcx, rcx
0x180020a7d  jnz     loc_180020CA4
0x180020a83  mov     eax, [rsp+2F0h+var_280]
0x180020a87  test    eax, eax
0x180020a89  jz      loc_180020B9A
0x180020a8f  test    byte ptr cs:xmmword_1800AB5A0+1, r15b
0x180020a96  jnz     loc_180020CB2
0x180020a9c  lea     rdi, [rsi+28h]
0x180020aa0  or      [rdi], rax
0x180020aa3  mov     r9d, dword ptr [rsp+2F0h+var_278]
0x180020aa8  mov     rax, rdi
0x180020aab  test    r9d, r9d
0x180020aae  jnz     loc_180020CCE
0x180020ab4  mov     r9d, dword ptr [rsp+2F0h+var_278+4]
0x180020ab9  test    r9d, r9d
0x180020abc  jnz     loc_180020CF4
0x180020ac2  mov     eax, [rsp+2F0h+var_27C]
0x180020ac6  test    eax, eax
0x180020ac8  jz      short loc_180020ADA
0x180020aca  test    byte ptr cs:xmmword_1800AB5A0+1, r15b
0x180020ad1  jnz     loc_180020D1A
0x180020ad7  or      [rdi], rax
0x180020ada  mov     r9, [rbp+1F0h+var_270]
0x180020ade  test    r9, r9
0x180020ae1  jz      short loc_180020AF7
0x180020ae3  test    byte ptr cs:xmmword_1800AB5A0+1, r15b
0x180020aea  jnz     loc_180020D36
0x180020af0  mov     rax, [rbp+1F0h+var_270]
0x180020af4  or      [rdi], rax
0x180020af7  test    byte ptr cs:xmmword_1800AB5A0+1, r15b
0x180020afe  jnz     loc_180020D4B
0x180020b04  mov     rcx, [rsp+2F0h+hKey]; hKey
0x180020b09  test    rcx, rcx
0x180020b0c  jnz     loc_180020BE7
0x180020b12  mov     rcx, [rsp+2F0h+var_2A8]; hKey
0x180020b17  test    rcx, rcx
0x180020b1a  jnz     loc_180020D98
0x180020b20  mov     rcx, [rsp+2F0h+var_298]; void *
0x180020b25  test    rcx, rcx
0x180020b28  jnz     loc_180020DA3
0x180020b2e  mov     rcx, [rsp+2F0h+var_290]; void *
0x180020b33  test    rcx, rcx
0x180020b36  jnz     loc_180020DAD
0x180020b3c  mov     rcx, [rsp+2F0h+var_288]; void *
0x180020b41  test    rcx, rcx
0x180020b44  jnz     loc_180020DB7
0x180020b4a  test    byte ptr cs:xmmword_1800AB5A0+1, r15b
0x180020b51  jnz     loc_180020DC1
0x180020b57  mov     eax, ebx
0x180020b59  mov     rcx, [rbp+1F0h+var_50]
0x180020b60  xor     rcx, rsp; StackCookie
0x180020b63  call    __security_check_cookie
0x180020b68  add     rsp, 2B8h
0x180020b6f  pop     r15
0x180020b71  pop     r14
0x180020b73  pop     r13
0x180020b75  pop     r12
0x180020b77  pop     rdi
0x180020b78  pop     rsi
0x180020b79  pop     rbx
0x180020b7a  pop     rbp
0x180020b7b  retn
0x180020b7c  mov     rcx, [rsp+2F0h+var_2A8]
0x180020b81  lea     rdx, [rsp+2F0h+var_280]
0x180020b86  call    DnsReadDohSetting
0x180020b8b  mov     ebx, eax
0x180020b8d  test    eax, eax
0x180020b8f  jz      loc_180020A59
0x180020b95  jmp     loc_180020B04
0x180020b9a  lea     rdi, [rsi+28h]
0x180020b9e  jmp     loc_180020AA3
0x180020ba3  mov     rcx, [rsp+2F0h+var_2A8]
0x180020ba8  lea     rdx, [rsp+2F0h+var_27C]
0x180020bad  call    DnsReadDotSetting
0x180020bb2  mov     ebx, eax
0x180020bb4  test    eax, eax
0x180020bb6  jz      loc_180020A4B
0x180020bbc  jmp     loc_180020B04
0x180020bc1  mov     [rsi+10h], rcx
0x180020bc5  mov     [rsp+2F0h+var_298], r14
0x180020bca  jmp     loc_180020A67
0x180020bcf  mov     ecx, eax
0x180020bd1  call    WX_WIN32_FROM_HR
0x180020bd6  jmp     loc_1800208AA
0x180020bdb  mov     ecx, eax
0x180020bdd  call    WX_WIN32_FROM_HR
0x180020be2  jmp     loc_18002091F
0x180020be7  call    cs:__imp_RegCloseKey
0x180020bed  jmp     loc_180020B12
0x180020bf2  mov     ebx, 57h ; 'W'
0x180020bf7  jmp     loc_180020B04
0x180020bfc  mov     edx, 78h ; 'x'
0x180020c01  mov     ecx, r12d
0x180020c04  mov     r9, rsi
0x180020c07  mov     r8, r13
0x180020c0a  call    WPP_SF_q
0x180020c0f  jmp     loc_180020812
0x180020c14  test    byte ptr cs:xmmword_1800AB5A0+1, r15b
0x180020c1b  jz      loc_180020B04
0x180020c21  mov     edx, 0Ah
0x180020c26  mov     dword ptr [rsp+2F0h+var_2D0], ebx
0x180020c2a  mov     ecx, r12d
0x180020c2d  lea     r9, [rbp+1F0h+var_260]
0x180020c31  lea     r8, WPP_cf96f6af26f535eeb3b7d66bdedfd114_Traceguids
0x180020c38  call    WPP_SF_SD
0x180020c3d  test    byte ptr cs:xmmword_1800AB5A0+1, r15b
0x180020c44  jz      loc_180020B04
0x180020c4a  mov     edx, 7Ah ; 'z'
0x180020c4f  jmp     short loc_180020C56
0x180020c51  mov     edx, 7Bh ; '{'
0x180020c56  mov     r9d, ebx
0x180020c59  jmp     loc_180020D88
0x180020c5e  test    byte ptr cs:xmmword_1800AB5A0+1, r15b
0x180020c65  jz      loc_180020B04
0x180020c6b  mov     edx, 0Ah
0x180020c70  mov     dword ptr [rsp+2F0h+var_2D0], ebx
0x180020c74  mov     ecx, r12d
0x180020c77  lea     r9, [rbp+1F0h+var_260]
0x180020c7b  lea     r8, WPP_cf96f6af26f535eeb3b7d66bdedfd114_Traceguids
0x180020c82  call    WPP_SF_SD
0x180020c87  test    byte ptr cs:xmmword_1800AB5A0+1, r15b
0x180020c8e  jz      loc_180020B04
0x180020c94  jmp     short loc_180020C51
0x180020c96  mov     [rsi+18h], rcx
0x180020c9a  mov     [rsp+2F0h+var_290], r14
0x180020c9f  jmp     loc_180020A75
0x180020ca4  mov     [rsi+20h], rcx
0x180020ca8  mov     [rsp+2F0h+var_288], r14
0x180020cad  jmp     loc_180020A83
0x180020cb2  mov     edx, 7Ch ; '|'
0x180020cb7  mov     ecx, r12d
0x180020cba  mov     r9d, eax
0x180020cbd  mov     r8, r13
0x180020cc0  call    WPP_SF_d
0x180020cc5  mov     eax, [rsp+2F0h+var_280]
0x180020cc9  jmp     loc_180020A9C
0x180020cce  test    byte ptr cs:xmmword_1800AB5A0+1, r15b
0x180020cd5  jz      short loc_180020CE7
  ... truncated ...
```
