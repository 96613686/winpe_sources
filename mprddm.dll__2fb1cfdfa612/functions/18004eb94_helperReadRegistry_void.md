# helperReadRegistry(void)

- ea: `0x18004eb94`
- end: `0x18004f394`
- name: `?helperReadRegistry@@YAXXZ`
- size: `2048`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180050110`

## callees

- `0x18004eb94`
- `0x180067e84`
- `0x1800680dc`
- `0x180071cec`
- `0x18008c5f2`
- `0x18008c630`
- `0x18008e010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x18004eeab`
- `KERNEL32!LocalFree` at `0x18004eef3`
- `KERNEL32!LocalFree` at `0x18004ef5e`
- `KERNEL32!LocalFree` at `0x18004f076`
- `KERNEL32!LocalFree` at `0x18004f183`
- `KERNEL32!LocalFree` at `0x18004f2f4`
- `KERNEL32!LocalFree` at `0x18004eeab`
- `KERNEL32!LocalFree` at `0x18004eef3`
- `KERNEL32!LocalFree` at `0x18004ef5e`
- `KERNEL32!LocalFree` at `0x18004f076`
- `KERNEL32!LocalFree` at `0x18004f183`
- `KERNEL32!LocalFree` at `0x18004f2f4`
- `KERNEL32!GetLastError` at `0x18004ed18`
- `KERNEL32!GetLastError` at `0x18004f129`
- `KERNEL32!GetLastError` at `0x18004ed18`
- `KERNEL32!GetLastError` at `0x18004f129`
- `KERNEL32!WideCharToMultiByte` at `0x18004ed05`
- `KERNEL32!WideCharToMultiByte` at `0x18004f116`
- `KERNEL32!WideCharToMultiByte` at `0x18004ed05`
- `KERNEL32!WideCharToMultiByte` at `0x18004f116`
- `ADVAPI32!RegCloseKey` at `0x18004f06d`
- `ADVAPI32!RegCloseKey` at `0x18004f36b`
- `ADVAPI32!RegCloseKey` at `0x18004f06d`
- `ADVAPI32!RegCloseKey` at `0x18004f36b`
- `ADVAPI32!RegOpenKeyExA` at `0x18004ec6c`
- `ADVAPI32!RegOpenKeyExA` at `0x18004f0a1`
- `ADVAPI32!RegOpenKeyExA` at `0x18004ec6c`
- `ADVAPI32!RegOpenKeyExA` at `0x18004f0a1`
- `ADVAPI32!RegQueryValueExA` at `0x18004ed9a`
- `ADVAPI32!RegQueryValueExA` at `0x18004eddd`
- `ADVAPI32!RegQueryValueExA` at `0x18004ee1c`
- `ADVAPI32!RegQueryValueExA` at `0x18004ee5b`
- `ADVAPI32!RegQueryValueExA` at `0x18004f1b4`
- `ADVAPI32!RegQueryValueExA` at `0x18004f325`
- `ADVAPI32!RegQueryValueExA` at `0x18004ed9a`
- `ADVAPI32!RegQueryValueExA` at `0x18004eddd`
- `ADVAPI32!RegQueryValueExA` at `0x18004ee1c`
- `ADVAPI32!RegQueryValueExA` at `0x18004ee5b`
- `ADVAPI32!RegQueryValueExA` at `0x18004f1b4`
- `ADVAPI32!RegQueryValueExA` at `0x18004f325`
- `ntdll!RtlIpv6StringToAddressA` at `0x18004f202`
- `ntdll!RtlIpv6StringToAddressA` at `0x18004f202`
- `ntdll!RtlIpv6AddressToStringA` at `0x18004f29e`
- `ntdll!RtlIpv6AddressToStringA` at `0x18004f29e`
- `ole32!CLSIDFromString` at `0x18004eccc`
- `ole32!CLSIDFromString` at `0x18004f0dd`
- `ole32!CLSIDFromString` at `0x18004eccc`
- `ole32!CLSIDFromString` at `0x18004f0dd`
- `WS2_32!__imp_inet_addr` at `0x18004ee95`
- `WS2_32!__imp_inet_addr` at `0x18004eed4`
- `WS2_32!__imp_inet_addr` at `0x18004ef21`
- `WS2_32!__imp_inet_addr` at `0x18004ef3c`
- `WS2_32!__imp_inet_addr` at `0x18004ee95`
- `WS2_32!__imp_inet_addr` at `0x18004eed4`
- `WS2_32!__imp_inet_addr` at `0x18004ef21`
- `WS2_32!__imp_inet_addr` at `0x18004ef3c`

## string_xrefs

- `0x18004ec3b`: `System\CurrentControlSet\Services\RemoteAccess\Parameters\Ip`
- `0x18004f093`: `System\CurrentControlSet\Services\RemoteAccess\Parameters\Ipv6`
- `0x18004ed3c`: `CLSIDFromString for AdapterGuid failed with error %d`
- `0x18004f14d`: `CLSIDFromString for AdapterGuid failed with error %d`
- `0x18004ee3f`: `AllowNetworkAccess`
- `0x18004f309`: `AllowNetworkAccess`
- `0x18004f21b`: `REGVAL_NAMESERVERS_A opened`
- `0x18004f34e`: `REGKEY_RAS_IPv6_PARAM_A open failed`

## pseudocode

```c
void helperReadRegistry(void)
{
  WCHAR *v0; // rsi
  int ValueWithAllocW; // eax
  HRESULT v2; // eax
  __int64 v3; // r8
  DWORD LastError; // eax
  const wchar_t *v5; // rdx
  unsigned int v6; // eax
  unsigned int v7; // eax
  _BYTE *v8; // rbx
  unsigned int v9; // edi
  __int64 v10; // rcx
  unsigned int v11; // eax
  WCHAR *v12; // rbx
  HRESULT v13; // eax
  __int64 v14; // r8
  DWORD v15; // eax
  const wchar_t *v16; // rdx
  CHAR *v17; // rbx
  CHAR *v18; // r8
  int cbMultiByte[2]; // [rsp+28h] [rbp-D8h]
  int cbMultiBytea[2]; // [rsp+28h] [rbp-D8h]
  LPBOOL lpUsedDefaultChar; // [rsp+38h] [rbp-C8h]
  LPBOOL lpUsedDefaultChara; // [rsp+38h] [rbp-C8h]
  DWORD cbData; // [rsp+50h] [rbp-B0h] BYREF
  BYTE Data[4]; // [rsp+54h] [rbp-ACh] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  char *cp; // [rsp+60h] [rbp-A0h]
  HKEY phkResult; // [rsp+68h] [rbp-98h] BYREF
  PCSTR Terminator; // [rsp+70h] [rbp-90h] BYREF
  HLOCAL hMem[2]; // [rsp+78h] [rbp-88h] BYREF
  LPCOLESTR lpsz[3]; // [rsp+88h] [rbp-78h] BYREF
  CHAR S[80]; // [rsp+A0h] [rbp-60h] BYREF
  int v32; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v33[2044]; // [rsp+F4h] [rbp-Ch] BYREF

  *(_DWORD *)Data = 0;
  cbData = 0;
  cp = 0;
  v0 = 0;
  hMem[0] = 0;
  Terminator = 0;
  hKey = 0;
  phkResult = 0;
  lpsz[0] = 0;
  v32 = 0;
  memset_0(v33, 0, sizeof(v33));
  HelperRegVal = 0;
  dword_1800C98D8 = 10;
  qword_1800C98E0 = 0;
  qword_1800C98E8 = 0;
  qword_1800C98F0 = 0;
  dword_1800C995C = 0;
  xmmword_1800C993C = 0;
  dword_1800C9934 = 0;
  xmmword_1800C994C = 0;
  if ( RegOpenKeyExA(
         HKEY_LOCAL_MACHINE,
         "System\\CurrentControlSet\\Services\\RemoteAccess\\Parameters\\Ip",
         0,
         0x20019u,
         &hKey) )
  {
    goto LABEL_38;
  }
  ValueWithAllocW = RegQueryValueWithAllocW(hKey);
  v0 = (WCHAR *)lpsz[0];
  if ( !ValueWithAllocW && *lpsz[0] )
  {
    v2 = CLSIDFromString(lpsz[0], &Buf2);
    v3 = (unsigned int)v2;
    if ( v2 < 0 )
    {
      if ( !(_QWORD)xmmword_1800C9740 )
        goto LABEL_12;
      v5 = L"CLSIDFromString for AdapterGuid failed with error %d";
      goto LABEL_11;
    }
    if ( WideCharToMultiByte(0, 0x400u, v0, -1, MultiByteStr, 39, 0, 0) )
    {
      HIDWORD(qword_1800C98F0) = 1;
      goto LABEL_12;
    }
    LastError = GetLastError();
    if ( (_QWORD)xmmword_1800C9740 )
    {
      v3 = LastError;
      v5 = L"Converting the specified GUID string to UTF7 failed with error %d";
LABEL_11:
      LOWORD(v32) = 0;
      FormatRRASErrorString(&v32, v5, v3);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
        gRasIpAddrMgmtEtwContext,
        xmmword_1800C9740,
        &v32);
    }
  }
LABEL_12:
  cbData = 4;
  if ( !RegQueryValueExA(hKey, "SuppressWINSNameServers", 0, 0, Data, &cbData) && *(_DWORD *)Data )
    HelperRegVal = 1;
  cbData = 4;
  if ( !RegQueryValueExA(hKey, "SuppressDNSNameServers", 0, 0, Data, &cbData) && *(_DWORD *)Data )
    *(&HelperRegVal + 1) = 1;
  cbData = 4;
  if ( !RegQueryValueExA(hKey, "InitialAddressPoolSize", 0, 0, Data, &cbData) )
    dword_1800C98D8 = *(_DWORD *)Data;
  cbData = 4;
  if ( !RegQueryValueExA(hKey, "AllowNetworkAccess", 0, 0, Data, &cbData) )
    LODWORD(qword_1800C98F0) = *(_DWORD *)Data;
  if ( !(unsigned int)RegQueryValueWithAllocA(hKey, "WINSNameServer") )
  {
    v6 = inet_addr(cp);
    if ( v6 != -1 )
      LODWORD(qword_1800C98E0) = v6;
    LocalFree(cp);
    cp = 0;
  }
  if ( !(unsigned int)RegQueryValueWithAllocA(hKey, "WINSNameServerBackup") )
  {
    v7 = inet_addr(cp);
    if ( v7 != -1 && (_DWORD)qword_1800C98E0 )
      HIDWORD(qword_1800C98E0) = v7;
    LocalFree(cp);
  }
  if ( !(unsigned int)RegQueryValueWithAllocA(hKey, "DNSNameServers") )
  {
    v8 = hMem[0];
    v9 = inet_addr((const char *)hMem[0]);
    v10 = -1;
    do
      ++v10;
    while ( v8[v10] );
    v11 = inet_addr(&v8[v10 + 1]);
    if ( v9 - 1 <= 0xFFFFFFFD )
    {
      LODWORD(qword_1800C98E8) = v9;
      if ( v11 != -1 )
        HIDWORD(qword_1800C98E8) = v11;
    }
    LocalFree(v8);
    hMem[0] = 0;
  }
LABEL_38:
  if ( (_QWORD)xmmword_1800C9740 )
  {
    LODWORD(lpUsedDefaultChar) = dword_1800C98D8;
    cbMultiByte[0] = *(&HelperRegVal + 1);
    LOWORD(v32) = 0;
    FormatRRASErrorString(
      &v32,
      L"%hs: %d, %hs: %d, %hs: %d",
      "SuppressWINSNameServers",
      HelperRegVal,
      "SuppressDNSNameServers",
      *(_QWORD *)cbMultiByte,
      "InitialAddressPoolSize",
      lpUsedDefaultChar);
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
      gRasIpAddrMgmtEtwContext,
      xmmword_1800C9740,
      &v32);
    if ( (_QWORD)xmmword_1800C9740 )
    {
      LODWORD(lpUsedDefaultChara) = qword_1800C98E8;
      cbMultiBytea[0] = HIDWORD(qword_1800C98E0);
      LOWORD(v32) = 0;
      FormatRRASErrorString(
        &v32,
        L"%hs: 0x%x, %hs: 0x%x, %hs: 0x%x, 0x%x",
        "WINSNameServer",
        (unsigned int)qword_1800C98E0,
        "WINSNameServerBackup",
        *(_QWORD *)cbMultiBytea,
        "DNSNameServers",
        lpUsedDefaultChara,
        HIDWORD(qword_1800C98E8));
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
        gRasIpAddrMgmtEtwContext,
        xmmword_1800C9740,
        &v32);
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  LocalFree(v0);
  lpsz[0] = 0;
  if ( !RegOpenKeyExA(
          HKEY_LOCAL_MACHINE,
          "System\\CurrentControlSet\\Services\\RemoteAccess\\Parameters\\Ipv6",
          0,
          0x20019u,
          &phkResult) )
  {
    if ( (unsigned int)RegQueryValueWithAllocW(phkResult) )
    {
LABEL_55:
      cbData = 4;
      if ( !RegQueryValueExA(phkResult, "SuppressDNSNameServers", 0, 0, Data, &cbData) && *(_DWORD *)Data )
        dword_1800C9998 = 1;
      if ( (unsigned int)RegQueryValueWithAllocA(phkResult, "DNSNameServers") )
      {
        if ( (unsigned int)RegQueryValueWithAllocA(phkResult, "NameServers") )
          goto LABEL_68;
        *(_OWORD *)hMem = 0;
        memset_0(S, 0, 0x41u);
        v17 = (CHAR *)Terminator;
        *(_OWORD *)hMem = *(_OWORD *)Terminator;
        RtlIpv6AddressToStringA((const struct in6_addr *)hMem, S);
        xmmword_1800C993C = *(_OWORD *)hMem;
        if ( !(_QWORD)xmmword_1800C9740 )
        {
LABEL_67:
          LocalFree(v17);
LABEL_68:
          cbData = 4;
          if ( !RegQueryValueExA(phkResult, "AllowNetworkAccess", 0, 0, Data, &cbData) )
            dword_1800C9934 = *(_DWORD *)Data;
          goto LABEL_72;
        }
        v18 = S;
      }
      else
      {
        v17 = (CHAR *)hMem[0];
        Terminator = 0;
        *(_OWORD *)lpsz = 0;
        RtlIpv6StringToAddressA((PCSTR)hMem[0], &Terminator, (struct in6_addr *)lpsz);
        if ( *((_QWORD *)&xmmword_1800C9740 + 1) )
          ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, const wchar_t *))gRasIpAddrMgmtTemplateFunc)(
            gRasIpAddrMgmtEtwContext,
            *((_QWORD *)&xmmword_1800C9740 + 1),
            L"REGVAL_NAMESERVERS_A opened");
        xmmword_1800C993C = *(_OWORD *)lpsz;
        if ( !(_QWORD)xmmword_1800C9740 )
          goto LABEL_67;
        v18 = v17;
      }
      LOWORD(v32) = 0;
      FormatRRASErrorString(&v32, L"IPv6 DNS Server from NameServer %hs", v18);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
        gRasIpAddrMgmtEtwContext,
        xmmword_1800C9740,
        &v32);
      goto LABEL_67;
    }
    v12 = (WCHAR *)lpsz[0];
    if ( *lpsz[0] )
    {
      v13 = CLSIDFromString(lpsz[0], &stru_1800C9960);
      v14 = (unsigned int)v13;
      if ( v13 < 0 )
      {
        if ( !(_QWORD)xmmword_1800C9740 )
          goto LABEL_54;
        v16 = L"CLSIDFromString for AdapterGuid failed with error %d";
      }
      else
      {
        if ( WideCharToMultiByte(0, 0x400u, v12, -1, String1, 39, 0, 0) )
        {
          dword_1800C995C = 1;
          goto LABEL_54;
        }
        v15 = GetLastError();
        if ( !(_QWORD)xmmword_1800C9740 )
          goto LABEL_54;
        v14 = v15;
        v16 = L"Converting the specified GUID string to UTF7 failed with error %d";
      }
      LOWORD(v32) = 0;
      FormatRRASErrorString(&v32, v16, v14);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
        gRasIpAddrMgmtEtwContext,
        xmmword_1800C9740,
        &v32);
    }
LABEL_54:
    LocalFree(v12);
    goto LABEL_55;
  }
  if ( *((_QWORD *)&xmmword_1800C9740 + 1) )
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, const wchar_t *))gRasIpAddrMgmtTemplateFunc)(
      gRasIpAddrMgmtEtwContext,
      *((_QWORD *)&xmmword_1800C9740 + 1),
      L"REGKEY_RAS_IPv6_PARAM_A open failed");
LABEL_72:
  if ( phkResult )
    RegCloseKey(phkResult);
}

```

## disassembly

```asm
0x18004eb94  push    rbp
0x18004eb96  push    rbx
0x18004eb97  push    rsi
0x18004eb98  push    rdi
0x18004eb99  push    r12
0x18004eb9b  push    r13
0x18004eb9d  push    r14
0x18004eb9f  push    r15
0x18004eba1  lea     rbp, [rsp-808h]
0x18004eba9  sub     rsp, 908h
0x18004ebb0  mov     rax, cs:__security_cookie
0x18004ebb7  xor     rax, rsp
0x18004ebba  mov     [rbp+840h+var_50], rax
0x18004ebc1  xor     r14d, r14d
0x18004ebc4  lea     rcx, [rbp+840h+var_84C]; void *
0x18004ebc8  xor     edx, edx; Val
0x18004ebca  mov     dword ptr [rsp+940h+Data], r14d
0x18004ebcf  mov     r8d, 7FCh; Size
0x18004ebd5  mov     [rsp+940h+cbData], r14d
0x18004ebda  mov     [rsp+940h+cp], r14
0x18004ebdf  mov     esi, r14d
0x18004ebe2  mov     [rsp+940h+hMem], r14
0x18004ebe7  mov     [rsp+940h+Terminator], r14
0x18004ebec  mov     [rsp+940h+hKey], r14
0x18004ebf1  mov     [rsp+940h+var_8D8], r14
0x18004ebf6  mov     [rbp+840h+lpsz], r14
0x18004ebfa  mov     [rbp+840h+var_850], r14d
0x18004ebfe  call    memset_0
0x18004ec03  xorps   xmm0, xmm0
0x18004ec06  mov     cs:?HelperRegVal@@3U_REGISTRY_VALUES@@A, r14; _REGISTRY_VALUES HelperRegVal
0x18004ec0d  xorps   xmm1, xmm1
0x18004ec10  mov     cs:dword_1800C98D8, 0Ah
0x18004ec1a  lea     rax, [rsp+940h+hKey]
0x18004ec1f  mov     cs:qword_1800C98E0, r14
0x18004ec26  mov     r9d, 20019h; samDesired
0x18004ec2c  mov     [rsp+940h+phkResult], rax; phkResult
0x18004ec31  xor     r8d, r8d; ulOptions
0x18004ec34  mov     cs:qword_1800C98E8, r14
0x18004ec3b  lea     rdx, aSystemCurrentc_15; "System\\CurrentControlSet\\Services\\Re"...
0x18004ec42  mov     cs:qword_1800C98F0, r14
0x18004ec49  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004ec50  mov     cs:dword_1800C995C, r14d
0x18004ec57  movups  cs:xmmword_1800C993C, xmm0
0x18004ec5e  mov     cs:dword_1800C9934, r14d
0x18004ec65  movups  cs:xmmword_1800C994C, xmm1
0x18004ec6c  call    cs:__imp_RegOpenKeyExA
0x18004ec72  lea     r15d, [r14+1]
0x18004ec76  lea     r13d, [r14+4]
0x18004ec7a  lea     rcx, aSuppressdnsnam; "SuppressDNSNameServers"
0x18004ec81  lea     rbx, aInitialaddress; "InitialAddressPoolSize"
0x18004ec88  lea     rdi, aWinsnameserver; "WINSNameServerBackup"
0x18004ec8f  lea     r12, aDnsnameservers; "DNSNameServers"
0x18004ec96  test    eax, eax
0x18004ec98  jnz     loc_18004EF85
0x18004ec9e  mov     rcx, [rsp+940h+hKey]; hKey
0x18004eca3  lea     r9, [rbp+840h+lpsz]
0x18004eca7  call    RegQueryValueWithAllocW
0x18004ecac  mov     rsi, [rbp+840h+lpsz]
0x18004ecb0  test    eax, eax
0x18004ecb2  jnz     loc_18004ED6F
0x18004ecb8  cmp     [rsi], r14w
0x18004ecbc  jz      loc_18004ED6F
0x18004ecc2  lea     rdx, Buf2; pclsid
0x18004ecc9  mov     rcx, rsi; lpsz
0x18004eccc  call    cs:__imp_CLSIDFromString
0x18004ecd2  mov     r8d, eax
0x18004ecd5  test    eax, eax
0x18004ecd7  js      short loc_18004ED33
0x18004ecd9  mov     [rsp+940h+lpUsedDefaultChar], r14; lpUsedDefaultChar
0x18004ecde  lea     rax, MultiByteStr
0x18004ece5  mov     [rsp+940h+lpDefaultChar], r14; lpDefaultChar
0x18004ecea  or      r9d, 0FFFFFFFFh; cchWideChar
0x18004ecee  mov     [rsp+940h+cbMultiByte], 27h ; '''; cbMultiByte
0x18004ecf6  mov     r8, rsi; lpWideCharStr
0x18004ecf9  mov     edx, 400h; dwFlags
0x18004ecfe  mov     [rsp+940h+phkResult], rax; lpMultiByteStr
0x18004ed03  xor     ecx, ecx; CodePage
0x18004ed05  call    cs:__imp_WideCharToMultiByte
0x18004ed0b  test    eax, eax
0x18004ed0d  jz      short loc_18004ED18
0x18004ed0f  mov     dword ptr cs:qword_1800C98F0+4, r15d
0x18004ed16  jmp     short loc_18004ED6F
0x18004ed18  call    cs:__imp_GetLastError
0x18004ed1e  cmp     qword ptr cs:xmmword_1800C9740, r14
0x18004ed25  jz      short loc_18004ED6F
0x18004ed27  mov     r8d, eax
0x18004ed2a  lea     rdx, aConvertingTheS; "Converting the specified GUID string to"...
0x18004ed31  jmp     short loc_18004ED43
0x18004ed33  cmp     qword ptr cs:xmmword_1800C9740, r14
0x18004ed3a  jz      short loc_18004ED6F
0x18004ed3c  lea     rdx, aClsidfromstrin; "CLSIDFromString for AdapterGuid failed "...
0x18004ed43  lea     rcx, [rbp+840h+var_850]
0x18004ed47  mov     word ptr [rbp+840h+var_850], r14w
0x18004ed4c  call    FormatRRASErrorString
0x18004ed51  mov     rdx, qword ptr cs:xmmword_1800C9740
0x18004ed58  lea     r8, [rbp+840h+var_850]
0x18004ed5c  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18004ed63  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18004ed6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ed6f  mov     rcx, [rsp+940h+hKey]; hKey
0x18004ed74  lea     rax, [rsp+940h+cbData]
0x18004ed79  mov     qword ptr [rsp+940h+cbMultiByte], rax; lpcbData
0x18004ed7e  lea     rdx, aSuppresswinsna; "SuppressWINSNameServers"
0x18004ed85  lea     rax, [rsp+940h+Data]
0x18004ed8a  mov     [rsp+940h+cbData], r13d
0x18004ed8f  xor     r9d, r9d; lpType
0x18004ed92  mov     [rsp+940h+phkResult], rax; lpData
0x18004ed97  xor     r8d, r8d; lpReserved
0x18004ed9a  call    cs:__imp_RegQueryValueExA
0x18004eda0  test    eax, eax
0x18004eda2  jnz     short loc_18004EDB2
0x18004eda4  cmp     dword ptr [rsp+940h+Data], r14d
0x18004eda9  jz      short loc_18004EDB2
0x18004edab  mov     dword ptr cs:?HelperRegVal@@3U_REGISTRY_VALUES@@A, r15d; _REGISTRY_VALUES HelperRegVal
0x18004edb2  mov     rcx, [rsp+940h+hKey]; hKey
0x18004edb7  lea     rax, [rsp+940h+cbData]
0x18004edbc  mov     qword ptr [rsp+940h+cbMultiByte], rax; lpcbData
0x18004edc1  lea     rdx, aSuppressdnsnam; "SuppressDNSNameServers"
0x18004edc8  lea     rax, [rsp+940h+Data]
0x18004edcd  mov     [rsp+940h+cbData], r13d
0x18004edd2  xor     r9d, r9d; lpType
0x18004edd5  mov     [rsp+940h+phkResult], rax; lpData
0x18004edda  xor     r8d, r8d; lpReserved
0x18004eddd  call    cs:__imp_RegQueryValueExA
0x18004ede3  test    eax, eax
0x18004ede5  jnz     short loc_18004EDF5
0x18004ede7  cmp     dword ptr [rsp+940h+Data], r14d
0x18004edec  jz      short loc_18004EDF5
0x18004edee  mov     dword ptr cs:?HelperRegVal@@3U_REGISTRY_VALUES@@A+4, r15d; _REGISTRY_VALUES HelperRegVal
0x18004edf5  mov     rcx, [rsp+940h+hKey]; hKey
0x18004edfa  lea     rax, [rsp+940h+cbData]
0x18004edff  mov     qword ptr [rsp+940h+cbMultiByte], rax; lpcbData
0x18004ee04  xor     r9d, r9d; lpType
0x18004ee07  lea     rax, [rsp+940h+Data]
0x18004ee0c  mov     [rsp+940h+cbData], r13d
0x18004ee11  xor     r8d, r8d; lpReserved
0x18004ee14  mov     [rsp+940h+phkResult], rax; lpData
0x18004ee19  mov     rdx, rbx; lpValueName
0x18004ee1c  call    cs:__imp_RegQueryValueExA
0x18004ee22  test    eax, eax
0x18004ee24  jnz     short loc_18004EE30
0x18004ee26  mov     eax, dword ptr [rsp+940h+Data]
0x18004ee2a  mov     cs:dword_1800C98D8, eax
0x18004ee30  mov     rcx, [rsp+940h+hKey]; hKey
0x18004ee35  lea     rax, [rsp+940h+cbData]
0x18004ee3a  mov     qword ptr [rsp+940h+cbMultiByte], rax; lpcbData
0x18004ee3f  lea     rdx, aAllownetworkac; "AllowNetworkAccess"
0x18004ee46  lea     rax, [rsp+940h+Data]
0x18004ee4b  mov     [rsp+940h+cbData], r13d
0x18004ee50  xor     r9d, r9d; lpType
0x18004ee53  mov     [rsp+940h+phkResult], rax; lpData
0x18004ee58  xor     r8d, r8d; lpReserved
0x18004ee5b  call    cs:__imp_RegQueryValueExA
0x18004ee61  test    eax, eax
0x18004ee63  jnz     short loc_18004EE6F
0x18004ee65  mov     eax, dword ptr [rsp+940h+Data]
0x18004ee69  mov     dword ptr cs:qword_1800C98F0, eax
0x18004ee6f  mov     rcx, [rsp+940h+hKey]; hKey
0x18004ee74  lea     r9, [rsp+940h+cp]
0x18004ee79  mov     r8d, r15d
0x18004ee7c  lea     rdx, aWinsnameserver_0; "WINSNameServer"
0x18004ee83  call    RegQueryValueWithAllocA
0x18004ee88  or      r12d, 0FFFFFFFFh
0x18004ee8c  test    eax, eax
0x18004ee8e  jnz     short loc_18004EEB6
0x18004ee90  mov     rcx, [rsp+940h+cp]; cp
0x18004ee95  call    cs:__imp_inet_addr
0x18004ee9b  cmp     eax, r12d
0x18004ee9e  jz      short loc_18004EEA6
0x18004eea0  mov     dword ptr cs:qword_1800C98E0, eax
0x18004eea6  mov     rcx, [rsp+940h+cp]; hMem
0x18004eeab  call    cs:__imp_LocalFree
0x18004eeb1  mov     [rsp+940h+cp], r14
0x18004eeb6  mov     rcx, [rsp+940h+hKey]; hKey
0x18004eebb  lea     r9, [rsp+940h+cp]
0x18004eec0  mov     r8d, r15d
0x18004eec3  mov     rdx, rdi; lpValueName
0x18004eec6  call    RegQueryValueWithAllocA
0x18004eecb  test    eax, eax
0x18004eecd  jnz     short loc_18004EEF9
0x18004eecf  mov     rcx, [rsp+940h+cp]; cp
0x18004eed4  call    cs:__imp_inet_addr
0x18004eeda  cmp     eax, r12d
0x18004eedd  jz      short loc_18004EEEE
0x18004eedf  cmp     dword ptr cs:qword_1800C98E0, r14d
0x18004eee6  jz      short loc_18004EEEE
0x18004eee8  mov     dword ptr cs:qword_1800C98E0+4, eax
0x18004eeee  mov     rcx, [rsp+940h+cp]; hMem
0x18004eef3  call    cs:__imp_LocalFree
0x18004eef9  mov     rcx, [rsp+940h+hKey]; hKey
0x18004eefe  lea     r9, [rsp+940h+hMem]
0x18004ef03  mov     r8d, 7
0x18004ef09  lea     rdx, aDnsnameservers; "DNSNameServers"
0x18004ef10  call    RegQueryValueWithAllocA
0x18004ef15  test    eax, eax
0x18004ef17  jnz     short loc_18004EF77
0x18004ef19  mov     rbx, [rsp+940h+hMem]
0x18004ef1e  mov     rcx, rbx; cp
0x18004ef21  call    cs:__imp_inet_addr
0x18004ef27  mov     edi, eax
0x18004ef29  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18004ef2d  inc     rcx
0x18004ef30  cmp     [rbx+rcx], r14b
0x18004ef34  jnz     short loc_18004EF2D
0x18004ef36  inc     rcx
0x18004ef39  add     rcx, rbx; cp
0x18004ef3c  call    cs:__imp_inet_addr
0x18004ef42  lea     ecx, [rdi-1]
0x18004ef45  cmp     ecx, 0FFFFFFFDh
0x18004ef48  ja      short loc_18004EF5B
0x18004ef4a  mov     dword ptr cs:qword_1800C98E8, edi
0x18004ef50  cmp     eax, r12d
0x18004ef53  jz      short loc_18004EF5B
0x18004ef55  mov     dword ptr cs:qword_1800C98E8+4, eax
0x18004ef5b  mov     rcx, rbx; hMem
0x18004ef5e  call    cs:__imp_LocalFree
0x18004ef64  mov     [rsp+940h+hMem], r14
0x18004ef69  lea     rbx, aInitialaddress; "InitialAddressPoolSize"
0x18004ef70  lea     rdi, aWinsnameserver; "WINSNameServerBackup"
0x18004ef77  lea     rcx, aSuppressdnsnam; "SuppressDNSNameServers"
0x18004ef7e  lea     r12, aDnsnameservers; "DNSNameServers"
0x18004ef85  cmp     qword ptr cs:xmmword_1800C9740, r14
0x18004ef8c  jz      loc_18004F063
0x18004ef92  mov     eax, cs:dword_1800C98D8
0x18004ef98  lea     r8, aSuppresswinsna; "SuppressWINSNameServers"
0x18004ef9f  mov     r9d, dword ptr cs:?HelperRegVal@@3U_REGISTRY_VALUES@@A; _REGISTRY_VALUES HelperRegVal
0x18004efa6  lea     rdx, aHsDHsDHsD; "%hs: %d, %hs: %d, %hs: %d"
0x18004efad  mov     dword ptr [rsp+940h+lpUsedDefaultChar], eax
0x18004efb1  mov     eax, dword ptr cs:?HelperRegVal@@3U_REGISTRY_VALUES@@A+4; _REGISTRY_VALUES HelperRegVal
0x18004efb7  mov     [rsp+940h+lpDefaultChar], rbx
0x18004efbc  mov     [rsp+940h+cbMultiByte], eax
0x18004efc0  mov     [rsp+940h+phkResult], rcx
0x18004efc5  lea     rcx, [rbp+840h+var_850]
0x18004efc9  mov     word ptr [rbp+840h+var_850], r14w
0x18004efce  call    FormatRRASErrorString
0x18004efd3  mov     rdx, qword ptr cs:xmmword_1800C9740
0x18004efda  lea     r8, [rbp+840h+var_850]
0x18004efde  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18004efe5  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18004efec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004eff1  cmp     qword ptr cs:xmmword_1800C9740, r14
0x18004eff8  jz      short loc_18004F063
0x18004effa  mov     eax, dword ptr cs:qword_1800C98E8+4
0x18004f000  lea     r8, aWinsnameserver_0; "WINSNameServer"
0x18004f007  mov     r9d, dword ptr cs:qword_1800C98E0
0x18004f00e  lea     rdx, aHs0xXHs0xXHs0x; "%hs: 0x%x, %hs: 0x%x, %hs: 0x%x, 0x%x"
0x18004f015  mov     [rsp+940h+var_900], eax
0x18004f019  lea     rcx, [rbp+840h+var_850]
0x18004f01d  mov     eax, dword ptr cs:qword_1800C98E8
0x18004f023  mov     dword ptr [rsp+940h+lpUsedDefaultChar], eax
0x18004f027  mov     eax, dword ptr cs:qword_1800C98E0+4
0x18004f02d  mov     [rsp+940h+lpDefaultChar], r12
0x18004f032  mov     [rsp+940h+cbMultiByte], eax
0x18004f036  mov     [rsp+940h+phkResult], rdi
0x18004f03b  mov     word ptr [rbp+840h+var_850], r14w
0x18004f040  call    FormatRRASErrorString
0x18004f045  mov     rdx, qword ptr cs:xmmword_1800C9740
0x18004f04c  lea     r8, [rbp+840h+var_850]
0x18004f050  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18004f057  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x18004f05e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f063  mov     rcx, [rsp+940h+hKey]; hKey
0x18004f068  test    rcx, rcx
0x18004f06b  jz      short loc_18004F073
0x18004f06d  call    cs:__imp_RegCloseKey
0x18004f073  mov     rcx, rsi; hMem
0x18004f076  call    cs:__imp_LocalFree
0x18004f07c  lea     rax, [rsp+940h+var_8D8]
0x18004f081  mov     [rbp+840h+lpsz], r14
0x18004f085  mov     r9d, 20019h; samDesired
0x18004f08b  mov     [rsp+940h+phkResult], rax; phkResult
0x18004f090  xor     r8d, r8d; ulOptions
0x18004f093  lea     rdx, aSystemCurrentc_35; "System\\CurrentControlSet\\Services\\Re"...
0x18004f09a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004f0a1  call    cs:__imp_RegOpenKeyExA
0x18004f0a7  test    eax, eax
0x18004f0a9  jnz     loc_18004F33B
0x18004f0af  mov     rcx, [rsp+940h+var_8D8]; hKey
0x18004f0b4  lea     r9, [rbp+840h+lpsz]
0x18004f0b8  call    RegQueryValueWithAllocW
0x18004f0bd  test    eax, eax
0x18004f0bf  jnz     loc_18004F189
0x18004f0c5  mov     rbx, [rbp+840h+lpsz]
0x18004f0c9  cmp     [rbx], r14w
0x18004f0cd  jz      loc_18004F180
0x18004f0d3  lea     rdx, stru_1800C9960; pclsid
0x18004f0da  mov     rcx, rbx; lpsz
0x18004f0dd  call    cs:__imp_CLSIDFromString
0x18004f0e3  mov     r8d, eax
0x18004f0e6  test    eax, eax
0x18004f0e8  js      short loc_18004F144
0x18004f0ea  mov     [rsp+940h+lpUsedDefaultChar], r14; lpUsedDefaultChar
0x18004f0ef  lea     rax, String1
0x18004f0f6  mov     [rsp+940h+lpDefaultChar], r14; lpDefaultChar
0x18004f0fb  or      r9d, 0FFFFFFFFh; cchWideChar
0x18004f0ff  mov     [rsp+940h+cbMultiByte], 27h ; '''; cbMultiByte
0x18004f107  mov     r8, rbx; lpWideCharStr
0x18004f10a  mov     edx, 400h; dwFlags
0x18004f10f  mov     [rsp+940h+phkResult], rax; lpMultiByteStr
0x18004f114  xor     ecx, ecx; CodePage
  ... truncated ...
```
