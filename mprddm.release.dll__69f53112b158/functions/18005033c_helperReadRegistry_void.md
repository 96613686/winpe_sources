# helperReadRegistry(void)

- ea: `0x18005033c`
- end: `0x180050bf6`
- name: `?helperReadRegistry@@YAXXZ`
- size: `2234`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180051a00`

## callees

- `0x18005033c`
- `0x18006a7c0`
- `0x18006aa20`
- `0x1800755b8`
- `0x180092a92`
- `0x180092ad0`
- `0x180095010`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180050690`
- `KERNEL32!LocalFree` at `0x1800506e4`
- `KERNEL32!LocalFree` at `0x180050761`
- `KERNEL32!LocalFree` at `0x180050885`
- `KERNEL32!LocalFree` at `0x1800509ad`
- `KERNEL32!LocalFree` at `0x180050b36`
- `KERNEL32!LocalFree` at `0x180050690`
- `KERNEL32!LocalFree` at `0x1800506e4`
- `KERNEL32!LocalFree` at `0x180050761`
- `KERNEL32!LocalFree` at `0x180050885`
- `KERNEL32!LocalFree` at `0x1800509ad`
- `KERNEL32!LocalFree` at `0x180050b36`
- `KERNEL32!GetLastError` at `0x1800504d9`
- `KERNEL32!GetLastError` at `0x18005094d`
- `KERNEL32!GetLastError` at `0x1800504d9`
- `KERNEL32!GetLastError` at `0x18005094d`
- `KERNEL32!WideCharToMultiByte` at `0x1800504c0`
- `KERNEL32!WideCharToMultiByte` at `0x180050934`
- `KERNEL32!WideCharToMultiByte` at `0x1800504c0`
- `KERNEL32!WideCharToMultiByte` at `0x180050934`
- `ADVAPI32!RegCloseKey` at `0x180050876`
- `ADVAPI32!RegCloseKey` at `0x180050bb9`
- `ADVAPI32!RegCloseKey` at `0x180050876`
- `ADVAPI32!RegCloseKey` at `0x180050bb9`
- `ADVAPI32!RegOpenKeyExA` at `0x18005041e`
- `ADVAPI32!RegOpenKeyExA` at `0x1800508b6`
- `ADVAPI32!RegOpenKeyExA` at `0x18005041e`
- `ADVAPI32!RegOpenKeyExA` at `0x1800508b6`
- `ADVAPI32!RegQueryValueExA` at `0x180050561`
- `ADVAPI32!RegQueryValueExA` at `0x1800505aa`
- `ADVAPI32!RegQueryValueExA` at `0x1800505ef`
- `ADVAPI32!RegQueryValueExA` at `0x180050634`
- `ADVAPI32!RegQueryValueExA` at `0x1800509e4`
- `ADVAPI32!RegQueryValueExA` at `0x180050b6d`
- `ADVAPI32!RegQueryValueExA` at `0x180050561`
- `ADVAPI32!RegQueryValueExA` at `0x1800505aa`
- `ADVAPI32!RegQueryValueExA` at `0x1800505ef`
- `ADVAPI32!RegQueryValueExA` at `0x180050634`
- `ADVAPI32!RegQueryValueExA` at `0x1800509e4`
- `ADVAPI32!RegQueryValueExA` at `0x180050b6d`
- `ntdll!RtlIpv6StringToAddressA` at `0x180050a38`
- `ntdll!RtlIpv6StringToAddressA` at `0x180050a38`
- `ntdll!RtlIpv6AddressToStringA` at `0x180050ada`
- `ntdll!RtlIpv6AddressToStringA` at `0x180050ada`
- `ole32!CLSIDFromString` at `0x180050484`
- `ole32!CLSIDFromString` at `0x1800508f8`
- `ole32!CLSIDFromString` at `0x180050484`
- `ole32!CLSIDFromString` at `0x1800508f8`
- `WS2_32!__imp_inet_addr` at `0x180050674`
- `WS2_32!__imp_inet_addr` at `0x1800506bf`
- `WS2_32!__imp_inet_addr` at `0x180050718`
- `WS2_32!__imp_inet_addr` at `0x180050739`
- `WS2_32!__imp_inet_addr` at `0x180050674`
- `WS2_32!__imp_inet_addr` at `0x1800506bf`
- `WS2_32!__imp_inet_addr` at `0x180050718`
- `WS2_32!__imp_inet_addr` at `0x180050739`

## string_xrefs

- `0x1800503ed`: `System\CurrentControlSet\Services\RemoteAccess\Parameters\Ip`
- `0x1800508a8`: `System\CurrentControlSet\Services\RemoteAccess\Parameters\Ipv6`
- `0x180050500`: `CLSIDFromString for AdapterGuid failed with error %d`
- `0x180050974`: `CLSIDFromString for AdapterGuid failed with error %d`
- `0x180050618`: `AllowNetworkAccess`
- `0x180050b51`: `AllowNetworkAccess`
- `0x180050a57`: `REGVAL_NAMESERVERS_A opened`
- `0x180050b9c`: `REGKEY_RAS_IPv6_PARAM_A open failed`

## pseudocode

```c
void helperReadRegistry(void)
{
  WCHAR *v0; // rsi
  int ValueWithAllocW; // eax
  int LastError; // eax
  const wchar_t *v3; // rdx
  unsigned int v4; // eax
  unsigned int v5; // eax
  CHAR *v6; // rbx
  unsigned int v7; // edi
  __int64 v8; // rcx
  unsigned int v9; // eax
  WCHAR *v10; // rbx
  int v11; // eax
  const wchar_t *v12; // rdx
  CHAR *v13; // rbx
  CHAR *v14; // r8
  int cbMultiByte[2]; // [rsp+30h] [rbp-D8h]
  int cbMultiBytea[2]; // [rsp+30h] [rbp-D8h]
  LPBOOL lpUsedDefaultChar; // [rsp+40h] [rbp-C8h]
  LPBOOL lpUsedDefaultChara; // [rsp+40h] [rbp-C8h]
  BYTE Data[8]; // [rsp+58h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-A8h] BYREF
  char *cp; // [rsp+68h] [rbp-A0h]
  HKEY phkResult; // [rsp+70h] [rbp-98h] BYREF
  PCSTR hMem[3]; // [rsp+78h] [rbp-90h] BYREF
  LPCOLESTR lpsz[3]; // [rsp+90h] [rbp-78h] BYREF
  CHAR S[80]; // [rsp+A8h] [rbp-60h] BYREF
  int v26; // [rsp+F8h] [rbp-10h] BYREF
  _BYTE v27[2044]; // [rsp+FCh] [rbp-Ch] BYREF

  memset(Data, 0, sizeof(Data));
  cp = 0;
  v0 = 0;
  hMem[1] = 0;
  hMem[0] = 0;
  hKey = 0;
  phkResult = 0;
  lpsz[0] = 0;
  v26 = 0;
  memset_0(v27, 0, sizeof(v27));
  HelperRegVal = 0;
  dword_1800D08D8 = 10;
  qword_1800D08E0 = 0;
  qword_1800D08E8 = 0;
  qword_1800D08F0 = 0;
  dword_1800D095C = 0;
  xmmword_1800D093C = 0;
  dword_1800D0934 = 0;
  xmmword_1800D094C = 0;
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
    LastError = CLSIDFromString(lpsz[0], &pclsid);
    if ( LastError < 0 )
    {
      if ( !(_QWORD)xmmword_1800D0740 )
        goto LABEL_12;
      v3 = L"CLSIDFromString for AdapterGuid failed with error %d";
      goto LABEL_11;
    }
    if ( WideCharToMultiByte(0, 0x400u, v0, -1, MultiByteStr, 39, 0, 0) )
    {
      HIDWORD(qword_1800D08F0) = 1;
      goto LABEL_12;
    }
    LastError = GetLastError();
    if ( (_QWORD)xmmword_1800D0740 )
    {
      v3 = L"Converting the specified GUID string to UTF7 failed with error %d";
LABEL_11:
      LOWORD(v26) = 0;
      FormatRRASErrorString(&v26, v3, (unsigned int)LastError);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
        gRasIpAddrMgmtEtwContext,
        xmmword_1800D0740,
        &v26);
    }
  }
LABEL_12:
  *(_DWORD *)Data = 4;
  if ( !RegQueryValueExA(hKey, "SuppressWINSNameServers", 0, 0, &Data[4], (LPDWORD)Data) && *(_DWORD *)&Data[4] )
    HelperRegVal = 1;
  *(_DWORD *)Data = 4;
  if ( !RegQueryValueExA(hKey, "SuppressDNSNameServers", 0, 0, &Data[4], (LPDWORD)Data) && *(_DWORD *)&Data[4] )
    *(&HelperRegVal + 1) = 1;
  *(_DWORD *)Data = 4;
  if ( !RegQueryValueExA(hKey, "InitialAddressPoolSize", 0, 0, &Data[4], (LPDWORD)Data) )
    dword_1800D08D8 = *(_DWORD *)&Data[4];
  *(_DWORD *)Data = 4;
  if ( !RegQueryValueExA(hKey, "AllowNetworkAccess", 0, 0, &Data[4], (LPDWORD)Data) )
    LODWORD(qword_1800D08F0) = *(_DWORD *)&Data[4];
  if ( !(unsigned int)RegQueryValueWithAllocA(hKey, "WINSNameServer") )
  {
    v4 = inet_addr(cp);
    if ( v4 != -1 )
      LODWORD(qword_1800D08E0) = v4;
    LocalFree(cp);
    cp = 0;
  }
  if ( !(unsigned int)RegQueryValueWithAllocA(hKey, "WINSNameServerBackup") )
  {
    v5 = inet_addr(cp);
    if ( v5 != -1 && (_DWORD)qword_1800D08E0 )
      HIDWORD(qword_1800D08E0) = v5;
    LocalFree(cp);
  }
  if ( !(unsigned int)RegQueryValueWithAllocA(hKey, "DNSNameServers") )
  {
    v6 = (CHAR *)hMem[1];
    v7 = inet_addr(hMem[1]);
    v8 = -1;
    do
      ++v8;
    while ( v6[v8] );
    v9 = inet_addr(&v6[v8 + 1]);
    if ( v7 - 1 <= 0xFFFFFFFD )
    {
      LODWORD(qword_1800D08E8) = v7;
      if ( v9 != -1 )
        HIDWORD(qword_1800D08E8) = v9;
    }
    LocalFree(v6);
    hMem[1] = 0;
  }
LABEL_38:
  if ( (_QWORD)xmmword_1800D0740 )
  {
    LODWORD(lpUsedDefaultChar) = dword_1800D08D8;
    cbMultiByte[0] = *(&HelperRegVal + 1);
    LOWORD(v26) = 0;
    FormatRRASErrorString(
      &v26,
      L"%hs: %d, %hs: %d, %hs: %d",
      "SuppressWINSNameServers",
      HelperRegVal,
      "SuppressDNSNameServers",
      *(_QWORD *)cbMultiByte,
      "InitialAddressPoolSize",
      lpUsedDefaultChar);
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
      gRasIpAddrMgmtEtwContext,
      xmmword_1800D0740,
      &v26);
    if ( (_QWORD)xmmword_1800D0740 )
    {
      LODWORD(lpUsedDefaultChara) = qword_1800D08E8;
      cbMultiBytea[0] = HIDWORD(qword_1800D08E0);
      LOWORD(v26) = 0;
      FormatRRASErrorString(
        &v26,
        L"%hs: 0x%x, %hs: 0x%x, %hs: 0x%x, 0x%x",
        "WINSNameServer",
        (unsigned int)qword_1800D08E0,
        "WINSNameServerBackup",
        *(_QWORD *)cbMultiBytea,
        "DNSNameServers",
        lpUsedDefaultChara,
        HIDWORD(qword_1800D08E8));
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
        gRasIpAddrMgmtEtwContext,
        xmmword_1800D0740,
        &v26);
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
      *(_DWORD *)Data = 4;
      if ( !RegQueryValueExA(phkResult, "SuppressDNSNameServers", 0, 0, &Data[4], (LPDWORD)Data) && *(_DWORD *)&Data[4] )
        dword_1800D0998 = 1;
      if ( (unsigned int)RegQueryValueWithAllocA(phkResult, "DNSNameServers") )
      {
        if ( (unsigned int)RegQueryValueWithAllocA(phkResult, "NameServers") )
          goto LABEL_68;
        *(_OWORD *)&hMem[1] = 0;
        memset_0(S, 0, 0x41u);
        v13 = (CHAR *)hMem[0];
        *(_OWORD *)&hMem[1] = *(_OWORD *)hMem[0];
        RtlIpv6AddressToStringA((const struct in6_addr *)&hMem[1], S);
        xmmword_1800D093C = *(_OWORD *)&hMem[1];
        if ( !(_QWORD)xmmword_1800D0740 )
        {
LABEL_67:
          LocalFree(v13);
LABEL_68:
          *(_DWORD *)Data = 4;
          if ( !RegQueryValueExA(phkResult, "AllowNetworkAccess", 0, 0, &Data[4], (LPDWORD)Data) )
            dword_1800D0934 = *(_DWORD *)&Data[4];
          goto LABEL_72;
        }
        v14 = S;
      }
      else
      {
        v13 = (CHAR *)hMem[1];
        hMem[0] = 0;
        *(_OWORD *)lpsz = 0;
        RtlIpv6StringToAddressA(hMem[1], hMem, (struct in6_addr *)lpsz);
        if ( *((_QWORD *)&xmmword_1800D0740 + 1) )
          ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, const wchar_t *))gRasIpAddrMgmtTemplateFunc)(
            gRasIpAddrMgmtEtwContext,
            *((_QWORD *)&xmmword_1800D0740 + 1),
            L"REGVAL_NAMESERVERS_A opened");
        xmmword_1800D093C = *(_OWORD *)lpsz;
        if ( !(_QWORD)xmmword_1800D0740 )
          goto LABEL_67;
        v14 = v13;
      }
      LOWORD(v26) = 0;
      FormatRRASErrorString(&v26, L"IPv6 DNS Server from NameServer %hs", v14);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
        gRasIpAddrMgmtEtwContext,
        xmmword_1800D0740,
        &v26);
      goto LABEL_67;
    }
    v10 = (WCHAR *)lpsz[0];
    if ( *lpsz[0] )
    {
      v11 = CLSIDFromString(lpsz[0], &stru_1800D0960);
      if ( v11 < 0 )
      {
        if ( !(_QWORD)xmmword_1800D0740 )
          goto LABEL_54;
        v12 = L"CLSIDFromString for AdapterGuid failed with error %d";
      }
      else
      {
        if ( WideCharToMultiByte(0, 0x400u, v10, -1, String1, 39, 0, 0) )
        {
          dword_1800D095C = 1;
          goto LABEL_54;
        }
        v11 = GetLastError();
        if ( !(_QWORD)xmmword_1800D0740 )
          goto LABEL_54;
        v12 = L"Converting the specified GUID string to UTF7 failed with error %d";
      }
      LOWORD(v26) = 0;
      FormatRRASErrorString(&v26, v12, (unsigned int)v11);
      ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, int *))gRasIpAddrMgmtTemplateFunc)(
        gRasIpAddrMgmtEtwContext,
        xmmword_1800D0740,
        &v26);
    }
LABEL_54:
    LocalFree(v10);
    goto LABEL_55;
  }
  if ( *((_QWORD *)&xmmword_1800D0740 + 1) )
    ((void (__fastcall *)(struct _MCGEN_TRACE_CONTEXT *, _QWORD, const wchar_t *))gRasIpAddrMgmtTemplateFunc)(
      gRasIpAddrMgmtEtwContext,
      *((_QWORD *)&xmmword_1800D0740 + 1),
      L"REGKEY_RAS_IPv6_PARAM_A open failed");
LABEL_72:
  if ( phkResult )
    RegCloseKey(phkResult);
}

```

## disassembly

```asm
0x18005033c  mov     rax, rsp
0x18005033f  mov     [rax+8], rbx
0x180050343  mov     [rax+10h], rsi
0x180050347  mov     [rax+18h], rdi
0x18005034b  push    rbp
0x18005034c  push    r12
0x18005034e  push    r13
0x180050350  push    r14
0x180050352  push    r15
0x180050354  lea     rbp, [rax-828h]
0x18005035b  sub     rsp, 900h
0x180050362  mov     rax, cs:__security_cookie
0x180050369  xor     rax, rsp
0x18005036c  mov     [rbp+820h+var_30], rax
0x180050373  xor     r14d, r14d
0x180050376  lea     rcx, [rbp+820h+var_82C]; void *
0x18005037a  xor     edx, edx; Val
0x18005037c  mov     dword ptr [rsp+920h+Data+4], r14d
0x180050381  mov     r8d, 7FCh; Size
0x180050387  mov     dword ptr [rsp+920h+Data], r14d
0x18005038c  mov     [rsp+920h+cp], r14
0x180050391  mov     esi, r14d
0x180050394  mov     qword ptr [rsp+920h+hMem+8], r14
0x180050399  mov     qword ptr [rsp+920h+hMem], r14
0x18005039e  mov     [rsp+920h+hKey], r14
0x1800503a3  mov     [rsp+920h+var_8B8], r14
0x1800503a8  mov     [rbp+820h+lpsz], r14
0x1800503ac  mov     [rbp+820h+var_830], r14d
0x1800503b0  call    memset_0
0x1800503b5  xorps   xmm0, xmm0
0x1800503b8  mov     cs:?HelperRegVal@@3U_REGISTRY_VALUES@@A, r14; _REGISTRY_VALUES HelperRegVal
0x1800503bf  xorps   xmm1, xmm1
0x1800503c2  mov     cs:dword_1800D08D8, 0Ah
0x1800503cc  lea     rax, [rsp+920h+hKey]
0x1800503d1  mov     cs:qword_1800D08E0, r14
0x1800503d8  mov     r9d, 20019h; samDesired
0x1800503de  mov     [rsp+920h+phkResult], rax; phkResult
0x1800503e3  xor     r8d, r8d; ulOptions
0x1800503e6  mov     cs:qword_1800D08E8, r14
0x1800503ed  lea     rdx, aSystemCurrentc_15; "System\\CurrentControlSet\\Services\\Re"...
0x1800503f4  mov     cs:qword_1800D08F0, r14
0x1800503fb  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180050402  mov     cs:dword_1800D095C, r14d
0x180050409  movups  cs:xmmword_1800D093C, xmm0
0x180050410  mov     cs:dword_1800D0934, r14d
0x180050417  movups  cs:xmmword_1800D094C, xmm1
0x18005041e  call    cs:__imp_RegOpenKeyExA
0x180050425  nop     dword ptr [rax+rax+00h]
0x18005042a  lea     r15d, [r14+1]
0x18005042e  lea     r13d, [r14+4]
0x180050432  lea     rcx, aSuppressdnsnam; "SuppressDNSNameServers"
0x180050439  lea     rbx, aInitialaddress; "InitialAddressPoolSize"
0x180050440  lea     rdi, aWinsnameserver; "WINSNameServerBackup"
0x180050447  lea     r12, aDnsnameservers; "DNSNameServers"
0x18005044e  test    eax, eax
0x180050450  jnz     loc_18005078E
0x180050456  mov     rcx, [rsp+920h+hKey]; hKey
0x18005045b  lea     r9, [rbp+820h+lpsz]
0x18005045f  call    RegQueryValueWithAllocW
0x180050464  mov     rsi, [rbp+820h+lpsz]
0x180050468  test    eax, eax
0x18005046a  jnz     loc_180050536
0x180050470  cmp     [rsi], r14w
0x180050474  jz      loc_180050536
0x18005047a  lea     rdx, pclsid; pclsid
0x180050481  mov     rcx, rsi; lpsz
0x180050484  call    cs:__imp_CLSIDFromString
0x18005048b  nop     dword ptr [rax+rax+00h]
0x180050490  test    eax, eax
0x180050492  js      short loc_1800504F7
0x180050494  mov     [rsp+920h+lpUsedDefaultChar], r14; lpUsedDefaultChar
0x180050499  lea     rax, MultiByteStr
0x1800504a0  mov     [rsp+920h+lpDefaultChar], r14; lpDefaultChar
0x1800504a5  or      r9d, 0FFFFFFFFh; cchWideChar
0x1800504a9  mov     [rsp+920h+cbMultiByte], 27h ; '''; cbMultiByte
0x1800504b1  mov     r8, rsi; lpWideCharStr
0x1800504b4  mov     edx, 400h; dwFlags
0x1800504b9  mov     [rsp+920h+phkResult], rax; lpMultiByteStr
0x1800504be  xor     ecx, ecx; CodePage
0x1800504c0  call    cs:__imp_WideCharToMultiByte
0x1800504c7  nop     dword ptr [rax+rax+00h]
0x1800504cc  test    eax, eax
0x1800504ce  jz      short loc_1800504D9
0x1800504d0  mov     dword ptr cs:qword_1800D08F0+4, r15d
0x1800504d7  jmp     short loc_180050536
0x1800504d9  call    cs:__imp_GetLastError
0x1800504e0  nop     dword ptr [rax+rax+00h]
0x1800504e5  cmp     qword ptr cs:xmmword_1800D0740, r14
0x1800504ec  jz      short loc_180050536
0x1800504ee  lea     rdx, aConvertingTheS; "Converting the specified GUID string to"...
0x1800504f5  jmp     short loc_180050507
0x1800504f7  cmp     qword ptr cs:xmmword_1800D0740, r14
0x1800504fe  jz      short loc_180050536
0x180050500  lea     rdx, aClsidfromstrin; "CLSIDFromString for AdapterGuid failed "...
0x180050507  mov     r8d, eax
0x18005050a  mov     word ptr [rbp+820h+var_830], r14w
0x18005050f  lea     rcx, [rbp+820h+var_830]
0x180050513  call    FormatRRASErrorString
0x180050518  mov     rdx, qword ptr cs:xmmword_1800D0740
0x18005051f  lea     r8, [rbp+820h+var_830]
0x180050523  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x18005052a  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180050531  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050536  mov     rcx, [rsp+920h+hKey]; hKey
0x18005053b  lea     rax, [rsp+920h+Data]
0x180050540  mov     qword ptr [rsp+920h+cbMultiByte], rax; lpcbData
0x180050545  lea     rdx, aSuppresswinsna; "SuppressWINSNameServers"
0x18005054c  lea     rax, [rsp+920h+Data+4]
0x180050551  mov     dword ptr [rsp+920h+Data], r13d
0x180050556  xor     r9d, r9d; lpType
0x180050559  mov     [rsp+920h+phkResult], rax; lpData
0x18005055e  xor     r8d, r8d; lpReserved
0x180050561  call    cs:__imp_RegQueryValueExA
0x180050568  nop     dword ptr [rax+rax+00h]
0x18005056d  test    eax, eax
0x18005056f  jnz     short loc_18005057F
0x180050571  cmp     dword ptr [rsp+920h+Data+4], r14d
0x180050576  jz      short loc_18005057F
0x180050578  mov     dword ptr cs:?HelperRegVal@@3U_REGISTRY_VALUES@@A, r15d; _REGISTRY_VALUES HelperRegVal
0x18005057f  mov     rcx, [rsp+920h+hKey]; hKey
0x180050584  lea     rax, [rsp+920h+Data]
0x180050589  mov     qword ptr [rsp+920h+cbMultiByte], rax; lpcbData
0x18005058e  lea     rdx, aSuppressdnsnam; "SuppressDNSNameServers"
0x180050595  lea     rax, [rsp+920h+Data+4]
0x18005059a  mov     dword ptr [rsp+920h+Data], r13d
0x18005059f  xor     r9d, r9d; lpType
0x1800505a2  mov     [rsp+920h+phkResult], rax; lpData
0x1800505a7  xor     r8d, r8d; lpReserved
0x1800505aa  call    cs:__imp_RegQueryValueExA
0x1800505b1  nop     dword ptr [rax+rax+00h]
0x1800505b6  test    eax, eax
0x1800505b8  jnz     short loc_1800505C8
0x1800505ba  cmp     dword ptr [rsp+920h+Data+4], r14d
0x1800505bf  jz      short loc_1800505C8
0x1800505c1  mov     dword ptr cs:?HelperRegVal@@3U_REGISTRY_VALUES@@A+4, r15d; _REGISTRY_VALUES HelperRegVal
0x1800505c8  mov     rcx, [rsp+920h+hKey]; hKey
0x1800505cd  lea     rax, [rsp+920h+Data]
0x1800505d2  mov     qword ptr [rsp+920h+cbMultiByte], rax; lpcbData
0x1800505d7  xor     r9d, r9d; lpType
0x1800505da  lea     rax, [rsp+920h+Data+4]
0x1800505df  mov     dword ptr [rsp+920h+Data], r13d
0x1800505e4  xor     r8d, r8d; lpReserved
0x1800505e7  mov     [rsp+920h+phkResult], rax; lpData
0x1800505ec  mov     rdx, rbx; lpValueName
0x1800505ef  call    cs:__imp_RegQueryValueExA
0x1800505f6  nop     dword ptr [rax+rax+00h]
0x1800505fb  test    eax, eax
0x1800505fd  jnz     short loc_180050609
0x1800505ff  mov     eax, dword ptr [rsp+920h+Data+4]
0x180050603  mov     cs:dword_1800D08D8, eax
0x180050609  mov     rcx, [rsp+920h+hKey]; hKey
0x18005060e  lea     rax, [rsp+920h+Data]
0x180050613  mov     qword ptr [rsp+920h+cbMultiByte], rax; lpcbData
0x180050618  lea     rdx, aAllownetworkac; "AllowNetworkAccess"
0x18005061f  lea     rax, [rsp+920h+Data+4]
0x180050624  mov     dword ptr [rsp+920h+Data], r13d
0x180050629  xor     r9d, r9d; lpType
0x18005062c  mov     [rsp+920h+phkResult], rax; lpData
0x180050631  xor     r8d, r8d; lpReserved
0x180050634  call    cs:__imp_RegQueryValueExA
0x18005063b  nop     dword ptr [rax+rax+00h]
0x180050640  test    eax, eax
0x180050642  jnz     short loc_18005064E
0x180050644  mov     eax, dword ptr [rsp+920h+Data+4]
0x180050648  mov     dword ptr cs:qword_1800D08F0, eax
0x18005064e  mov     rcx, [rsp+920h+hKey]; hKey
0x180050653  lea     r9, [rsp+920h+cp]
0x180050658  mov     r8d, r15d
0x18005065b  lea     rdx, aWinsnameserver_0; "WINSNameServer"
0x180050662  call    RegQueryValueWithAllocA
0x180050667  or      r12d, 0FFFFFFFFh
0x18005066b  test    eax, eax
0x18005066d  jnz     short loc_1800506A1
0x18005066f  mov     rcx, [rsp+920h+cp]; cp
0x180050674  call    cs:__imp_inet_addr
0x18005067b  nop     dword ptr [rax+rax+00h]
0x180050680  cmp     eax, r12d
0x180050683  jz      short loc_18005068B
0x180050685  mov     dword ptr cs:qword_1800D08E0, eax
0x18005068b  mov     rcx, [rsp+920h+cp]; hMem
0x180050690  call    cs:__imp_LocalFree
0x180050697  nop     dword ptr [rax+rax+00h]
0x18005069c  mov     [rsp+920h+cp], r14
0x1800506a1  mov     rcx, [rsp+920h+hKey]; hKey
0x1800506a6  lea     r9, [rsp+920h+cp]
0x1800506ab  mov     r8d, r15d
0x1800506ae  mov     rdx, rdi; lpValueName
0x1800506b1  call    RegQueryValueWithAllocA
0x1800506b6  test    eax, eax
0x1800506b8  jnz     short loc_1800506F0
0x1800506ba  mov     rcx, [rsp+920h+cp]; cp
0x1800506bf  call    cs:__imp_inet_addr
0x1800506c6  nop     dword ptr [rax+rax+00h]
0x1800506cb  cmp     eax, r12d
0x1800506ce  jz      short loc_1800506DF
0x1800506d0  cmp     dword ptr cs:qword_1800D08E0, r14d
0x1800506d7  jz      short loc_1800506DF
0x1800506d9  mov     dword ptr cs:qword_1800D08E0+4, eax
0x1800506df  mov     rcx, [rsp+920h+cp]; hMem
0x1800506e4  call    cs:__imp_LocalFree
0x1800506eb  nop     dword ptr [rax+rax+00h]
0x1800506f0  mov     rcx, [rsp+920h+hKey]; hKey
0x1800506f5  lea     r9, [rsp+920h+hMem+8]
0x1800506fa  mov     r8d, 7
0x180050700  lea     rdx, aDnsnameservers; "DNSNameServers"
0x180050707  call    RegQueryValueWithAllocA
0x18005070c  test    eax, eax
0x18005070e  jnz     short loc_180050780
0x180050710  mov     rbx, qword ptr [rsp+920h+hMem+8]
0x180050715  mov     rcx, rbx; cp
0x180050718  call    cs:__imp_inet_addr
0x18005071f  nop     dword ptr [rax+rax+00h]
0x180050724  mov     edi, eax
0x180050726  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18005072a  inc     rcx
0x18005072d  cmp     [rbx+rcx], r14b
0x180050731  jnz     short loc_18005072A
0x180050733  inc     rcx
0x180050736  add     rcx, rbx; cp
0x180050739  call    cs:__imp_inet_addr
0x180050740  nop     dword ptr [rax+rax+00h]
0x180050745  lea     ecx, [rdi-1]
0x180050748  cmp     ecx, 0FFFFFFFDh
0x18005074b  ja      short loc_18005075E
0x18005074d  mov     dword ptr cs:qword_1800D08E8, edi
0x180050753  cmp     eax, r12d
0x180050756  jz      short loc_18005075E
0x180050758  mov     dword ptr cs:qword_1800D08E8+4, eax
0x18005075e  mov     rcx, rbx; hMem
0x180050761  call    cs:__imp_LocalFree
0x180050768  nop     dword ptr [rax+rax+00h]
0x18005076d  mov     qword ptr [rsp+920h+hMem+8], r14
0x180050772  lea     rbx, aInitialaddress; "InitialAddressPoolSize"
0x180050779  lea     rdi, aWinsnameserver; "WINSNameServerBackup"
0x180050780  lea     rcx, aSuppressdnsnam; "SuppressDNSNameServers"
0x180050787  lea     r12, aDnsnameservers; "DNSNameServers"
0x18005078e  cmp     qword ptr cs:xmmword_1800D0740, r14
0x180050795  jz      loc_18005086C
0x18005079b  mov     eax, cs:dword_1800D08D8
0x1800507a1  lea     r8, aSuppresswinsna; "SuppressWINSNameServers"
0x1800507a8  mov     r9d, dword ptr cs:?HelperRegVal@@3U_REGISTRY_VALUES@@A; _REGISTRY_VALUES HelperRegVal
0x1800507af  lea     rdx, aHsDHsDHsD; "%hs: %d, %hs: %d, %hs: %d"
0x1800507b6  mov     dword ptr [rsp+920h+lpUsedDefaultChar], eax
0x1800507ba  mov     eax, dword ptr cs:?HelperRegVal@@3U_REGISTRY_VALUES@@A+4; _REGISTRY_VALUES HelperRegVal
0x1800507c0  mov     [rsp+920h+lpDefaultChar], rbx
0x1800507c5  mov     [rsp+920h+cbMultiByte], eax
0x1800507c9  mov     [rsp+920h+phkResult], rcx
0x1800507ce  lea     rcx, [rbp+820h+var_830]
0x1800507d2  mov     word ptr [rbp+820h+var_830], r14w
0x1800507d7  call    FormatRRASErrorString
0x1800507dc  mov     rdx, qword ptr cs:xmmword_1800D0740
0x1800507e3  lea     r8, [rbp+820h+var_830]
0x1800507e7  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x1800507ee  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x1800507f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800507fa  cmp     qword ptr cs:xmmword_1800D0740, r14
0x180050801  jz      short loc_18005086C
0x180050803  mov     eax, dword ptr cs:qword_1800D08E8+4
0x180050809  lea     r8, aWinsnameserver_0; "WINSNameServer"
0x180050810  mov     r9d, dword ptr cs:qword_1800D08E0
0x180050817  lea     rdx, aHs0xXHs0xXHs0x; "%hs: 0x%x, %hs: 0x%x, %hs: 0x%x, 0x%x"
0x18005081e  mov     [rsp+920h+var_8E0], eax
0x180050822  lea     rcx, [rbp+820h+var_830]
0x180050826  mov     eax, dword ptr cs:qword_1800D08E8
0x18005082c  mov     dword ptr [rsp+920h+lpUsedDefaultChar], eax
0x180050830  mov     eax, dword ptr cs:qword_1800D08E0+4
0x180050836  mov     [rsp+920h+lpDefaultChar], r12
0x18005083b  mov     [rsp+920h+cbMultiByte], eax
0x18005083f  mov     [rsp+920h+phkResult], rdi
0x180050844  mov     word ptr [rbp+820h+var_830], r14w
0x180050849  call    FormatRRASErrorString
0x18005084e  mov     rdx, qword ptr cs:xmmword_1800D0740
0x180050855  lea     r8, [rbp+820h+var_830]
0x180050859  mov     rcx, cs:?gRasIpAddrMgmtEtwContext@@3PEAU_MCGEN_TRACE_CONTEXT@@EA; _MCGEN_TRACE_CONTEXT * gRasIpAddrMgmtEtwContext
0x180050860  mov     rax, cs:?gRasIpAddrMgmtTemplateFunc@@3P6AKPEAU_MCGEN_TRACE_CONTEXT@@PEBU_EVENT_DESCRIPTOR@@PEBG@ZEA; ulong (*gRasIpAddrMgmtTemplateFunc)(_MCGEN_TRACE_CONTEXT *,_EVENT_DESCRIPTOR const *,ushort const *)
0x180050867  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005086c  mov     rcx, [rsp+920h+hKey]; hKey
0x180050871  test    rcx, rcx
0x180050874  jz      short loc_180050882
0x180050876  call    cs:__imp_RegCloseKey
0x18005087d  nop     dword ptr [rax+rax+00h]
0x180050882  mov     rcx, rsi; hMem
0x180050885  call    cs:__imp_LocalFree
0x18005088c  nop     dword ptr [rax+rax+00h]
0x180050891  lea     rax, [rsp+920h+var_8B8]
0x180050896  mov     [rbp+820h+lpsz], r14
0x18005089a  mov     r9d, 20019h; samDesired
0x1800508a0  mov     [rsp+920h+phkResult], rax; phkResult
0x1800508a5  xor     r8d, r8d; ulOptions
0x1800508a8  lea     rdx, aSystemCurrentc_35; "System\\CurrentControlSet\\Services\\Re"...
0x1800508af  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800508b6  call    cs:__imp_RegOpenKeyExA
0x1800508bd  nop     dword ptr [rax+rax+00h]
0x1800508c2  test    eax, eax
0x1800508c4  jnz     loc_180050B89
0x1800508ca  mov     rcx, [rsp+920h+var_8B8]; hKey
0x1800508cf  lea     r9, [rbp+820h+lpsz]
0x1800508d3  call    RegQueryValueWithAllocW
0x1800508d8  test    eax, eax
0x1800508da  jnz     loc_1800509B9
  ... truncated ...
```
