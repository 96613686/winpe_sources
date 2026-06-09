# ReadDnsPolicyTableConfigInfo

- ea: `0x180017900`
- end: `0x180017df1`
- name: `ReadDnsPolicyTableConfigInfo`
- size: `1265`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180073de0`

## callees

- `0x180017900`
- `0x180017e00`
- `0x180017e78`
- `0x18003de30`
- `0x18007f24c`
- `0x18008b5f0`
- `0x18008bf98`
- `0x1800a4718`
- `0x1800cccb0`
- `0x1800dbb48`
- `0x1800dc4ac`
- `0x1800dc670`
- `0x1800dc9e0`
- `0x1800de650`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800179c5`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800179c5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800179de`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017b61`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017d24`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800179de`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017b61`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180017d24`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001796d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180017b32`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001796d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180017b32`
- `ntdll!RtlGetPersistedStateLocation` at `0x180017a8d`
- `ntdll!RtlGetPersistedStateLocation` at `0x180017a8d`
- `KERNELBASE!RegOpenKeyExInternalW` at `0x180017b9c`
- `KERNELBASE!RegOpenKeyExInternalW` at `0x180017b9c`

## string_xrefs

- `0x18001795f`: `SOFTWARE\Policies\Microsoft\Windows NT\DNSClient\DnsPolicyConfig`
- `0x180017a52`: `Parameters\DnsPolicyConfig`
- `0x180017ab0`: `Parameters\DnsPolicyConfig`
- `0x180017c63`: `Parameters\DnsPolicyConfig`
- `0x180017a73`: `Dnscache`
- `0x180017bf4`: `Dnscache`
- `0x180017c19`: `Dnscache`
- `0x180017c73`: `Dnscache`
- `0x180017a59`: `SYSTEM\CurrentControlSet\Services\Dnscache`

## pseudocode

```c
__int64 ReadDnsPolicyTableConfigInfo()
{
  unsigned int v0; // ebx
  DWORD i; // edi
  int v3; // edx
  int v4; // r8d
  int PersistedStateLocation; // eax
  int v6; // edx
  int v7; // ecx
  int v8; // r8d
  int v9; // edi
  size_t v10; // rdx
  wchar_t *v11; // rcx
  HRESULT v12; // eax
  int v13; // edx
  int v14; // ecx
  int v15; // r8d
  __int64 v16; // r10
  int v17; // ebx
  unsigned int v18; // eax
  int v19; // ecx
  LSTATUS v20; // eax
  int v21; // ecx
  unsigned int DnsRulePolicyConfig; // eax
  int v23; // ecx
  __int64 v24; // rcx
  signed __int32 v25; // eax
  signed __int32 v26; // ett
  __int64 v27; // rcx
  char v28; // al
  unsigned int v29; // [rsp+40h] [rbp-458h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-450h] BYREF
  HKEY phkResult; // [rsp+50h] [rbp-448h] BYREF
  DWORD cchName; // [rsp+58h] [rbp-440h] BYREF
  WCHAR v33[264]; // [rsp+60h] [rbp-438h] BYREF
  WCHAR Name[264]; // [rsp+270h] [rbp-228h] BYREF

  hKey = 0;
  cchName = 0;
  phkResult = 0;
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_(1035, 33, WPP_3bf4b884ef3b304972f753916e0d484b_Traceguids);
  v0 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Policies\\Microsoft\\Windows NT\\DNSClient\\DnsPolicyConfig",
         0,
         0x20019u,
         &hKey);
  if ( !v0 )
    goto LABEL_4;
  memset_0(v33, 0, 0x20Au);
  hKey = 0;
  v29 = 0;
  if ( (BYTE3(xmmword_1801119E0) & 0x20) != 0 )
    WPP_SF_SSSqd(
      (unsigned int)L"Parameters\\DnsPolicyConfig",
      v3,
      v4,
      (unsigned int)L"Dnscache",
      (__int64)L"SYSTEM\\CurrentControlSet\\Services\\Dnscache",
      (__int64)L"Parameters\\DnsPolicyConfig",
      (__int64)v33,
      10);
  PersistedStateLocation = RtlGetPersistedStateLocation(
                             L"Dnscache",
                             0,
                             L"SYSTEM\\CurrentControlSet\\Services\\Dnscache",
                             0,
                             v33,
                             522,
                             &v29);
  v9 = PersistedStateLocation;
  if ( PersistedStateLocation < 0 )
  {
    if ( (BYTE3(xmmword_1801119E0) & 0x20) != 0 )
      WPP_SF_SSSd(
        v7,
        v6,
        v8,
        (unsigned int)L"Dnscache",
        (__int64)L"SYSTEM\\CurrentControlSet\\Services\\Dnscache",
        (__int64)L"Parameters\\DnsPolicyConfig",
        PersistedStateLocation);
    v17 = HRESULT_FROM_NTSTATUS(v9);
  }
  else
  {
    v10 = 522 - v29;
    v11 = &v33[(unsigned __int64)v29 >> 1];
    *(v11 - 1) = 92;
    v12 = StringCbCopyW(v11, v10, L"Parameters\\DnsPolicyConfig");
    v17 = v12;
    if ( v12 < 0 )
    {
      if ( (BYTE3(xmmword_1801119E0) & 0x20) == 0 )
        goto LABEL_15;
      WPP_SF_d(1053, 12, WPP_5573ccff99bc3fd3725f4dc217ee9a93_Traceguids, (unsigned int)v12);
    }
    else
    {
      if ( (BYTE3(xmmword_1801119E0) & 0x20) == 0 )
        goto LABEL_15;
      WPP_SF_SSSS(
        v14,
        v13,
        v15,
        (unsigned int)L"Dnscache",
        (__int64)L"SYSTEM\\CurrentControlSet\\Services\\Dnscache",
        v16,
        (__int64)v33);
    }
  }
  if ( (BYTE3(xmmword_1801119E0) & 0x20) != 0 )
    WPP_SF_d(1053, 14, WPP_5573ccff99bc3fd3725f4dc217ee9a93_Traceguids, (unsigned int)v17);
LABEL_15:
  if ( v17 >= 0 )
    v18 = RegOpenKeyExInternalW(-2147483646, v33, 0, 131097, &hKey, 0);
  else
    v18 = WX_WIN32_FROM_HR((unsigned int)v17);
  v0 = v18;
  if ( v18 )
  {
    if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
      WPP_SF_SD(v19, 10, (unsigned int)WPP_cf96f6af26f535eeb3b7d66bdedfd114_Traceguids, (unsigned int)v33, v18);
    v0 = 0;
    goto LABEL_7;
  }
LABEL_4:
  for ( i = 0; ; ++i )
  {
    cchName = 261;
    if ( RegEnumKeyExW(hKey, i, Name, &cchName, 0, 0, 0, 0) )
      break;
    v20 = RegOpenKeyExW(hKey, Name, 0, 0x20019u, &phkResult);
    v0 = v20;
    if ( v20 )
    {
      if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
        WPP_SF_SD(v21, 34, (unsigned int)WPP_3bf4b884ef3b304972f753916e0d484b_Traceguids, (unsigned int)Name, v20);
      break;
    }
    DnsRulePolicyConfig = GetDnsRulePolicyConfig(phkResult);
    v0 = DnsRulePolicyConfig;
    if ( DnsRulePolicyConfig )
    {
      if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
        WPP_SF_SD(
          v23,
          35,
          (unsigned int)WPP_3bf4b884ef3b304972f753916e0d484b_Traceguids,
          (unsigned int)Name,
          DnsRulePolicyConfig);
      RegCloseKey(phkResult);
      if ( v0 != 50 && v0 != 5010 )
      {
        if ( v0 != 1018 )
        {
          v28 = Microsoft_Windows_DNS_ClientEnableBits;
          LOBYTE(v29) = Microsoft_Windows_DNS_ClientEnableBits & 1;
          if ( (Microsoft_Windows_DNS_ClientEnableBits & 1) != 0 )
          {
            LOBYTE(v27) = Microsoft_Windows_DNS_ClientEnableBits & 1;
            McTemplateU0zq_EtwEventWriteTransfer(v27, PolicyReadError, Name, v0);
            v28 = Microsoft_Windows_DNS_ClientEnableBits;
          }
          if ( (v28 & 0x10) != 0 )
          {
            _m_prefetchw(&g_TraceOnceState);
            v25 = g_TraceOnceState;
            do
            {
              v24 = v25 | 0x10000u;
              v26 = v25;
              v25 = _InterlockedCompareExchange(&g_TraceOnceState, v24, v25);
            }
            while ( v26 != v25 );
            if ( (v25 & 0x10000) == 0 && (Microsoft_Windows_DNS_ClientEnableBits & 0x10) != 0 )
              McTemplateU0zq_EtwEventWriteTransfer(v24, PolicySystemReadError, Name, v0);
          }
        }
        v0 = 9572;
        break;
      }
      v0 = 0;
    }
    else
    {
      RegCloseKey(phkResult);
    }
  }
  RegCloseKey(hKey);
LABEL_7:
  dword_18011251C = v0;
  if ( (BYTE1(xmmword_1801119E0) & 8) != 0 )
    WPP_SF_d(1035, 36, WPP_3bf4b884ef3b304972f753916e0d484b_Traceguids, v0);
  return v0;
}

```

## disassembly

```asm
0x180017900  mov     [rsp+arg_0], rbx
0x180017905  mov     [rsp+arg_8], rdi
0x18001790a  push    r13
0x18001790c  sub     rsp, 490h
0x180017913  mov     rax, cs:__security_cookie
0x18001791a  xor     rax, rsp
0x18001791d  mov     [rsp+498h+var_18], rax
0x180017925  mov     [rsp+498h+hKey], 0
0x18001792e  mov     [rsp+498h+cchName], 0
0x180017936  mov     [rsp+498h+var_448], 0
0x18001793f  test    byte ptr cs:xmmword_1801119E0+1, 8
0x180017946  jnz     loc_180017BAD
0x18001794c  lea     rax, [rsp+498h+hKey]
0x180017951  mov     r9d, 20019h; samDesired
0x180017957  xor     r8d, r8d; ulOptions
0x18001795a  mov     [rsp+498h+phkResult], rax; phkResult
0x18001795f  lea     rdx, aSoftwarePolici_1; "SOFTWARE\\Policies\\Microsoft\\Windows "...
0x180017966  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001796d  call    cs:__imp_RegOpenKeyExW
0x180017974  nop     dword ptr [rax+rax+00h]
0x180017979  mov     ebx, eax
0x18001797b  test    eax, eax
0x18001797d  jnz     loc_180017A26
0x180017983  xor     edi, edi
0x180017985  mov     rcx, [rsp+498h+hKey]; hKey
0x18001798a  lea     r9, [rsp+498h+cchName]; lpcchName
0x18001798f  mov     [rsp+498h+lpftLastWriteTime], 0; lpftLastWriteTime
0x180017998  lea     r8, [rsp+498h+Name]; lpName
0x1800179a0  mov     [rsp+498h+lpcchClass], 0; lpcchClass
0x1800179a9  mov     edx, edi; dwIndex
0x1800179ab  mov     [rsp+498h+lpClass], 0; lpClass
0x1800179b4  mov     [rsp+498h+phkResult], 0; lpReserved
0x1800179bd  mov     [rsp+498h+cchName], 105h
0x1800179c5  call    cs:__imp_RegEnumKeyExW
0x1800179cc  nop     dword ptr [rax+rax+00h]
0x1800179d1  test    eax, eax
0x1800179d3  jz      loc_180017B12
0x1800179d9  mov     rcx, [rsp+498h+hKey]; hKey
0x1800179de  call    cs:__imp_RegCloseKey
0x1800179e5  nop     dword ptr [rax+rax+00h]
0x1800179ea  mov     cs:dword_18011251C, ebx
0x1800179f0  test    byte ptr cs:xmmword_1801119E0+1, 8
0x1800179f7  jnz     loc_180017BC8
0x1800179fd  mov     eax, ebx
0x1800179ff  mov     rcx, [rsp+498h+var_18]
0x180017a07  xor     rcx, rsp; StackCookie
0x180017a0a  call    __security_check_cookie
0x180017a0f  lea     r11, [rsp+498h+var_8]
0x180017a17  mov     rbx, [r11+10h]
0x180017a1b  mov     rdi, [r11+18h]
0x180017a1f  mov     rsp, r11
0x180017a22  pop     r13
0x180017a24  retn
0x180017a26  mov     ebx, 20Ah
0x180017a2b  lea     rcx, [rsp+498h+var_438]; void *
0x180017a30  mov     r8d, ebx; Size
0x180017a33  xor     edx, edx; Val
0x180017a35  call    memset_0
0x180017a3a  mov     [rsp+498h+hKey], 0
0x180017a43  mov     [rsp+498h+var_458], 0
0x180017a4b  test    byte ptr cs:xmmword_1801119E0+3, 20h
0x180017a52  lea     rcx, aParametersDnsp; "Parameters\\DnsPolicyConfig"
0x180017a59  lea     r13, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\Dn"...
0x180017a60  jnz     loc_180017BE6
0x180017a66  lea     rax, [rsp+498h+var_458]
0x180017a6b  xor     r9d, r9d
0x180017a6e  mov     [rsp+498h+lpcchClass], rax
0x180017a73  lea     rcx, aDnscache_1; "Dnscache"
0x180017a7a  lea     rax, [rsp+498h+var_438]
0x180017a7f  mov     dword ptr [rsp+498h+lpClass], ebx
0x180017a83  mov     r8, r13
0x180017a86  mov     [rsp+498h+phkResult], rax
0x180017a8b  xor     edx, edx
0x180017a8d  call    cs:__imp_RtlGetPersistedStateLocation
0x180017a94  nop     dword ptr [rax+rax+00h]
0x180017a99  mov     edi, eax
0x180017a9b  test    eax, eax
0x180017a9d  js      loc_180017C5A
0x180017aa3  mov     eax, [rsp+498h+var_458]
0x180017aa7  lea     rcx, [rsp+498h+var_438]
0x180017aac  sub     ebx, [rsp+498h+var_458]
0x180017ab0  lea     r10, aParametersDnsp; "Parameters\\DnsPolicyConfig"
0x180017ab7  shr     rax, 1
0x180017aba  mov     r8, r10; pszSrc
0x180017abd  mov     edx, ebx; cbDest
0x180017abf  lea     rcx, [rcx+rax*2]; pszDest
0x180017ac3  mov     word ptr [rcx-2], 5Ch ; '\'
0x180017ac9  call    StringCbCopyW
0x180017ace  mov     ebx, eax
0x180017ad0  test    eax, eax
0x180017ad2  js      loc_180017C8F
0x180017ad8  test    byte ptr cs:xmmword_1801119E0+3, 20h
0x180017adf  jnz     loc_180017C0F
0x180017ae5  test    ebx, ebx
0x180017ae7  jns     loc_180017B74
0x180017aed  mov     ecx, ebx
0x180017aef  call    WX_WIN32_FROM_HR
0x180017af4  mov     ebx, eax
0x180017af6  test    eax, eax
0x180017af8  jz      loc_180017983
0x180017afe  test    byte ptr cs:xmmword_1801119E0+1, 8
0x180017b05  jnz     loc_180017CBA
0x180017b0b  xor     ebx, ebx
0x180017b0d  jmp     loc_1800179EA
0x180017b12  mov     rcx, [rsp+498h+hKey]; hKey
0x180017b17  lea     rax, [rsp+498h+var_448]
0x180017b1c  mov     r9d, 20019h; samDesired
0x180017b22  mov     [rsp+498h+phkResult], rax; phkResult
0x180017b27  xor     r8d, r8d; ulOptions
0x180017b2a  lea     rdx, [rsp+498h+Name]; lpSubKey
0x180017b32  call    cs:__imp_RegOpenKeyExW
0x180017b39  nop     dword ptr [rax+rax+00h]
0x180017b3e  mov     ebx, eax
0x180017b40  test    eax, eax
0x180017b42  jnz     loc_180017DC2
0x180017b48  mov     rcx, [rsp+498h+var_448]; hKey
0x180017b4d  call    GetDnsRulePolicyConfig
0x180017b52  mov     ebx, eax
0x180017b54  test    eax, eax
0x180017b56  jnz     loc_180017CF9
0x180017b5c  mov     rcx, [rsp+498h+var_448]; hKey
0x180017b61  call    cs:__imp_RegCloseKey
0x180017b68  nop     dword ptr [rax+rax+00h]
0x180017b6d  inc     edi
0x180017b6f  jmp     loc_180017985
0x180017b74  lea     rax, [rsp+498h+hKey]
0x180017b79  mov     [rsp+498h+lpClass], 0
0x180017b82  mov     r9d, 20019h
0x180017b88  mov     [rsp+498h+phkResult], rax
0x180017b8d  xor     r8d, r8d
0x180017b90  lea     rdx, [rsp+498h+var_438]
0x180017b95  mov     rcx, 0FFFFFFFF80000002h
0x180017b9c  call    cs:__imp_RegOpenKeyExInternalW
0x180017ba3  nop     dword ptr [rax+rax+00h]
0x180017ba8  jmp     loc_180017AF4
0x180017bad  mov     edx, 21h ; '!'
0x180017bb2  lea     r8, WPP_3bf4b884ef3b304972f753916e0d484b_Traceguids
0x180017bb9  mov     ecx, 40Bh
0x180017bbe  call    WPP_SF_
0x180017bc3  jmp     loc_18001794C
0x180017bc8  mov     edx, 24h ; '$'
0x180017bcd  lea     r8, WPP_3bf4b884ef3b304972f753916e0d484b_Traceguids
0x180017bd4  mov     ecx, 40Bh
0x180017bd9  mov     r9d, ebx
0x180017bdc  call    WPP_SF_d
0x180017be1  jmp     loc_1800179FD
0x180017be6  mov     dword ptr [rsp+498h+lpftLastWriteTime], ebx
0x180017bea  lea     rax, [rsp+498h+var_438]
0x180017bef  mov     [rsp+498h+lpcchClass], rax
0x180017bf4  lea     r9, aDnscache_1; "Dnscache"
0x180017bfb  mov     [rsp+498h+lpClass], rcx
0x180017c00  mov     [rsp+498h+phkResult], r13
0x180017c05  call    WPP_SF_SSSqd
0x180017c0a  jmp     loc_180017A66
0x180017c0f  lea     rax, [rsp+498h+var_438]
0x180017c14  mov     [rsp+498h+lpcchClass], rax
0x180017c19  lea     r9, aDnscache_1; "Dnscache"
0x180017c20  mov     [rsp+498h+lpClass], r10
0x180017c25  mov     [rsp+498h+phkResult], r13
0x180017c2a  call    WPP_SF_SSSS
0x180017c2f  test    byte ptr cs:xmmword_1801119E0+3, 20h
0x180017c36  jz      loc_180017AE5
0x180017c3c  mov     edx, 0Eh
0x180017c41  lea     r8, WPP_5573ccff99bc3fd3725f4dc217ee9a93_Traceguids
0x180017c48  mov     ecx, 41Dh
0x180017c4d  mov     r9d, ebx
0x180017c50  call    WPP_SF_d
0x180017c55  jmp     loc_180017AE5
0x180017c5a  test    byte ptr cs:xmmword_1801119E0+3, 20h
0x180017c61  jz      short loc_180017C84
0x180017c63  lea     r10, aParametersDnsp; "Parameters\\DnsPolicyConfig"
0x180017c6a  mov     dword ptr [rsp+498h+lpcchClass], edi
0x180017c6e  mov     [rsp+498h+lpClass], r10
0x180017c73  lea     r9, aDnscache_1; "Dnscache"
0x180017c7a  mov     [rsp+498h+phkResult], r13
0x180017c7f  call    WPP_SF_SSSd
0x180017c84  mov     ecx, edi; int
0x180017c86  call    ?HRESULT_FROM_NTSTATUS@@YAJJ@Z; HRESULT_FROM_NTSTATUS(long)
0x180017c8b  mov     ebx, eax
0x180017c8d  jmp     short loc_180017C2F
0x180017c8f  test    byte ptr cs:xmmword_1801119E0+3, 20h
0x180017c96  jz      loc_180017AE5
0x180017c9c  mov     edx, 0Ch
0x180017ca1  lea     r8, WPP_5573ccff99bc3fd3725f4dc217ee9a93_Traceguids
0x180017ca8  mov     ecx, 41Dh
0x180017cad  mov     r9d, eax
0x180017cb0  call    WPP_SF_d
0x180017cb5  jmp     loc_180017C2F
0x180017cba  mov     edx, 0Ah
0x180017cbf  mov     dword ptr [rsp+498h+phkResult], ebx
0x180017cc3  lea     r9, [rsp+498h+var_438]
0x180017cc8  lea     r8, WPP_cf96f6af26f535eeb3b7d66bdedfd114_Traceguids
0x180017ccf  call    WPP_SF_SD
0x180017cd4  jmp     loc_180017B0B
0x180017cd9  mov     ecx, eax
0x180017cdb  or      ecx, edx
0x180017cdd  lock cmpxchg cs:g_TraceOnceState, ecx
0x180017ce5  jnz     short loc_180017CD9
0x180017ce7  test    edx, eax
0x180017ce9  jz      loc_180017D99
0x180017cef  mov     ebx, 2564h
0x180017cf4  jmp     loc_1800179D9
0x180017cf9  test    byte ptr cs:xmmword_1801119E0+1, 8
0x180017d00  jz      short loc_180017D1F
0x180017d02  mov     edx, 23h ; '#'
0x180017d07  mov     dword ptr [rsp+498h+phkResult], ebx
0x180017d0b  lea     r9, [rsp+498h+Name]
0x180017d13  lea     r8, WPP_3bf4b884ef3b304972f753916e0d484b_Traceguids
0x180017d1a  call    WPP_SF_SD
0x180017d1f  mov     rcx, [rsp+498h+var_448]; hKey
0x180017d24  call    cs:__imp_RegCloseKey
0x180017d2b  nop     dword ptr [rax+rax+00h]
0x180017d30  cmp     ebx, 32h ; '2'
0x180017d33  jz      short loc_180017D92
0x180017d35  cmp     ebx, 1392h
0x180017d3b  jz      short loc_180017D92
0x180017d3d  cmp     ebx, 3FAh
0x180017d43  jz      short loc_180017CEF
0x180017d45  mov     eax, cs:Microsoft_Windows_DNS_ClientEnableBits
0x180017d4b  mov     cl, al
0x180017d4d  and     cl, 1
0x180017d50  mov     byte ptr [rsp+498h+var_458], cl
0x180017d54  jz      short loc_180017D73
0x180017d56  mov     r9d, ebx
0x180017d59  lea     r8, [rsp+498h+Name]
0x180017d61  lea     rdx, PolicyReadError
0x180017d68  call    McTemplateU0zq_EtwEventWriteTransfer
0x180017d6d  mov     eax, cs:Microsoft_Windows_DNS_ClientEnableBits
0x180017d73  test    al, 10h
0x180017d75  jz      loc_180017CEF
0x180017d7b  prefetchw byte ptr cs:g_TraceOnceState
0x180017d82  mov     eax, cs:g_TraceOnceState
0x180017d88  mov     edx, 10000h
0x180017d8d  jmp     loc_180017CD9
0x180017d92  xor     ebx, ebx
0x180017d94  jmp     loc_180017B6D
0x180017d99  test    byte ptr cs:Microsoft_Windows_DNS_ClientEnableBits, 10h
0x180017da0  jz      loc_180017CEF
0x180017da6  mov     r9d, ebx
0x180017da9  lea     r8, [rsp+498h+Name]
0x180017db1  lea     rdx, PolicySystemReadError
0x180017db8  call    McTemplateU0zq_EtwEventWriteTransfer
0x180017dbd  jmp     loc_180017CEF
0x180017dc2  test    byte ptr cs:xmmword_1801119E0+1, 8
0x180017dc9  jz      loc_1800179D9
0x180017dcf  mov     edx, 22h ; '"'
0x180017dd4  mov     dword ptr [rsp+498h+phkResult], eax
0x180017dd8  lea     r9, [rsp+498h+Name]
0x180017de0  lea     r8, WPP_3bf4b884ef3b304972f753916e0d484b_Traceguids
0x180017de7  call    WPP_SF_SD
0x180017dec  jmp     loc_1800179D9
```
