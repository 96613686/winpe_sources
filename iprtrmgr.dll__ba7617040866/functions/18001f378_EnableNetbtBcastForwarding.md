# EnableNetbtBcastForwarding

- ea: `0x18001f378`
- end: `0x18001f98e`
- name: `EnableNetbtBcastForwarding`
- size: `1558`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002aef4`
- `0x18002b4b8`

## callees

- `0x18000ac60`
- `0x18001f378`
- `0x18001f994`
- `0x180021674`
- `0x1800583cc`
- `0x180058536`
- `0x180058570`

## import_xrefs

- `msvcrt!wcschr` at `0x18001f543`
- `msvcrt!wcschr` at `0x18001f543`
- `KERNEL32!GetProcessHeap` at `0x18001f4a3`
- `KERNEL32!GetProcessHeap` at `0x18001f93a`
- `KERNEL32!GetProcessHeap` at `0x18001f4a3`
- `KERNEL32!GetProcessHeap` at `0x18001f93a`
- `KERNEL32!HeapFree` at `0x18001f948`
- `KERNEL32!HeapFree` at `0x18001f948`
- `KERNEL32!HeapAlloc` at `0x18001f4b2`
- `KERNEL32!HeapAlloc` at `0x18001f4b2`
- `ADVAPI32!RegCloseKey` at `0x18001f88e`
- `ADVAPI32!RegCloseKey` at `0x18001f89e`
- `ADVAPI32!RegCloseKey` at `0x18001f90f`
- `ADVAPI32!RegCloseKey` at `0x18001f91f`
- `ADVAPI32!RegCloseKey` at `0x18001f92f`
- `ADVAPI32!RegCloseKey` at `0x18001f88e`
- `ADVAPI32!RegCloseKey` at `0x18001f89e`
- `ADVAPI32!RegCloseKey` at `0x18001f90f`
- `ADVAPI32!RegCloseKey` at `0x18001f91f`
- `ADVAPI32!RegCloseKey` at `0x18001f92f`
- `ADVAPI32!RegOpenKeyExW` at `0x18001f447`
- `ADVAPI32!RegOpenKeyExW` at `0x18001f5a9`
- `ADVAPI32!RegOpenKeyExW` at `0x18001f797`
- `ADVAPI32!RegOpenKeyExW` at `0x18001f447`
- `ADVAPI32!RegOpenKeyExW` at `0x18001f5a9`
- `ADVAPI32!RegOpenKeyExW` at `0x18001f797`
- `ADVAPI32!RegQueryValueExW` at `0x18001f48f`
- `ADVAPI32!RegQueryValueExW` at `0x18001f517`
- `ADVAPI32!RegQueryValueExW` at `0x18001f604`
- `ADVAPI32!RegQueryValueExW` at `0x18001f80d`
- `ADVAPI32!RegQueryValueExW` at `0x18001f48f`
- `ADVAPI32!RegQueryValueExW` at `0x18001f517`
- `ADVAPI32!RegQueryValueExW` at `0x18001f604`
- `ADVAPI32!RegQueryValueExW` at `0x18001f80d`
- `ADVAPI32!RegSetValueExW` at `0x18001f734`
- `ADVAPI32!RegSetValueExW` at `0x18001f843`
- `ADVAPI32!RegSetValueExW` at `0x18001f734`
- `ADVAPI32!RegSetValueExW` at `0x18001f843`

## string_xrefs

- `0x18001f439`: `System\CurrentControlSet\Services\Tcpip\Parameters\Adapters\NdisWanIP`
- `0x18001f460`: `EnableNetbtBcastForwarding : error %d opening NdisWanIP key\n`
- `0x18001f488`: `IpConfig`
- `0x18001f510`: `IpConfig`
- `0x18001f8d2`: `EnableNetbtBcastForwarding : error %d querying IPConfig value\n`
- `0x18001f4d5`: `EnableNetbtBcastForwarding : error %d allocating buffer of size %d for IPConfig value`
- `0x18001f59b`: `System\CurrentControlSet\Services\Netbt\Parameters`
- `0x18001f5c2`: `EnableNetbtBcastForwarding : error %d opening Netbt\Parameters key\n`
- `0x18001f632`: `Netbt Proxy mode in registry is %d`
- `0x18001f75c`: `System\CurrentControlSet\Services\Netbt\Parameters\Interfaces\Tcpip_%s`
- `0x18001f7c1`: `EnableNetbtBcastForwarding : error %d opening %ls key\n`
- `0x18001f8c0`: `RASFlags already present with value %d`

## pseudocode

```c
__int64 __fastcall EnableNetbtBcastForwarding(int a1)
{
  BYTE *v2; // rdi
  unsigned int v3; // eax
  unsigned int v4; // ebx
  const wchar_t *v5; // rdx
  __int64 v6; // rbx
  HANDLE ProcessHeap; // rax
  wchar_t *v8; // rax
  wchar_t *v9; // rsi
  LSTATUS v10; // eax
  __int64 v11; // r9
  bool v12; // zf
  char v13; // al
  int v14; // edx
  unsigned int v15; // eax
  unsigned int v16; // eax
  __int64 v17; // r8
  const wchar_t *v18; // rdx
  HANDLE v19; // rax
  DWORD cbData; // [rsp+30h] [rbp-A78h] BYREF
  BYTE Data[4]; // [rsp+34h] [rbp-A74h] BYREF
  DWORD Type; // [rsp+38h] [rbp-A70h] BYREF
  BYTE v24[4]; // [rsp+3Ch] [rbp-A6Ch] BYREF
  HKEY phkResult; // [rsp+40h] [rbp-A68h] BYREF
  HKEY v26; // [rsp+48h] [rbp-A60h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-A58h] BYREF
  int v28; // [rsp+60h] [rbp-A48h] BYREF
  _BYTE v29[2044]; // [rsp+64h] [rbp-A44h] BYREF
  wchar_t pszDest[2]; // [rsp+860h] [rbp-248h] BYREF
  _BYTE v31[508]; // [rsp+864h] [rbp-244h] BYREF

  hKey = 0;
  phkResult = 0;
  v26 = 0;
  cbData = 0;
  v2 = 0;
  Type = 0;
  *(_DWORD *)Data = 0;
  *(_DWORD *)v24 = 0;
  *(_DWORD *)pszDest = 0;
  memset_0(v31, 0, sizeof(v31));
  v28 = 0;
  memset_0(v29, 0, sizeof(v29));
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    McTemplateU0z_EventWriteTransfer(
      &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      RasRtrmgrTraceInfo,
      L"EnterEnableNetbtBcastForwarding");
  v3 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Services\\Tcpip\\Parameters\\Adapters\\NdisWanIP",
         0,
         0x20019u,
         &hKey);
  v4 = v3;
  if ( !v3 )
  {
    v3 = RegQueryValueExW(hKey, L"IpConfig", 0, &Type, 0, &cbData);
    v4 = v3;
    if ( v3 )
      goto LABEL_48;
    v6 = cbData;
    ProcessHeap = GetProcessHeap();
    v2 = (BYTE *)HeapAlloc(ProcessHeap, 0, v6 + 2);
    if ( !v2 )
    {
      v4 = 8;
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
        goto LABEL_53;
      LOWORD(v28) = 0;
      FormatRRASErrorString(
        &v28,
        L"EnableNetbtBcastForwarding : error %d allocating buffer of size %d for IPConfig value",
        8,
        cbData);
      goto LABEL_51;
    }
    v3 = RegQueryValueExW(hKey, L"IpConfig", 0, &Type, v2, &cbData);
    v4 = v3;
    if ( v3 || Type != 7 )
    {
LABEL_48:
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
        goto LABEL_53;
      v5 = L"EnableNetbtBcastForwarding : error %d querying IPConfig value\n";
      goto LABEL_50;
    }
    v2[(unsigned __int64)cbData >> 1] = 0;
    v8 = wcschr((const wchar_t *)v2, 0x7Bu);
    v9 = v8;
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      LOWORD(v28) = 0;
      FormatRRASErrorString(&v28, L"Internal adapter GUID is %lS", v8);
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v28);
    }
    v3 = RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"System\\CurrentControlSet\\Services\\Netbt\\Parameters",
           0,
           0x2001Fu,
           &phkResult);
    v4 = v3;
    if ( v3 )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
        goto LABEL_53;
      v5 = L"EnableNetbtBcastForwarding : error %d opening Netbt\\Parameters key\n";
      goto LABEL_50;
    }
    *(_DWORD *)Data = 0;
    cbData = 4;
    v10 = RegQueryValueExW(phkResult, L"EnableProxy", 0, &Type, Data, &cbData);
    v11 = *(unsigned int *)Data;
    v12 = v10 == 0;
    v13 = Microsoft_Windows_RRASEnableBits;
    v14 = *(_DWORD *)Data;
    if ( !v12 )
      v14 = 0;
    *(_DWORD *)&g_dwOldNetbtProxyMode = v14;
    if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      LOWORD(v28) = 0;
      FormatRRASErrorString(&v28, L"Netbt Proxy mode in registry is %d", *(unsigned int *)Data);
      v13 = Microsoft_Windows_RRASEnableBits;
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v28);
        v13 = Microsoft_Windows_RRASEnableBits;
      }
      v11 = *(unsigned int *)Data;
    }
    if ( a1 )
    {
      v11 = 2;
      *(_DWORD *)Data = 2;
    }
    else if ( (_DWORD)v11 == 2 )
    {
      *(_DWORD *)&g_dwOldNetbtProxyMode = 0;
      *(_DWORD *)Data = 0;
      if ( v13 >= 0 )
        goto LABEL_33;
      LOWORD(v28) = 0;
      FormatRRASErrorString(&v28, L"Forcing Netbt Proxy mode to be %d", 0);
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
        goto LABEL_33;
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v28);
      v11 = *(unsigned int *)Data;
      v13 = Microsoft_Windows_RRASEnableBits;
    }
    if ( v13 < 0 )
    {
      LOWORD(v28) = 0;
      FormatRRASErrorString(
        &v28,
        L"Old Netbt Proxy mode is %d, New Nebt Proxy Mode is %d",
        *(unsigned int *)&g_dwOldNetbtProxyMode,
        v11);
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v28);
    }
LABEL_33:
    v3 = RegSetValueExW(phkResult, L"EnableProxy", 0, 4u, Data, cbData);
    v4 = v3;
    if ( v3 )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
        goto LABEL_53;
      v5 = L"EnableNetbtBcastForwarding : error %d setting EnableProxy value\n";
      goto LABEL_50;
    }
    StringCbPrintfW(
      pszDest,
      0x200u,
      L"System\\CurrentControlSet\\Services\\Netbt\\Parameters\\Interfaces\\Tcpip_%s",
      v9);
    v15 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, pszDest, 0, 0x2001Fu, &v26);
    v4 = v15;
    if ( v15 )
    {
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
        goto LABEL_53;
      LOWORD(v28) = 0;
      FormatRRASErrorString(&v28, L"EnableNetbtBcastForwarding : error %d opening %ls key\n", v15, pszDest);
      goto LABEL_51;
    }
    *(_DWORD *)v24 = 0;
    cbData = 4;
    if ( RegQueryValueExW(v26, L"RASFlags", 0, &Type, v24, &cbData) )
    {
      *(_DWORD *)v24 = 1;
      v16 = RegSetValueExW(v26, L"RASFlags", 0, 4u, v24, 4u);
      if ( v16 && (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
      {
        v17 = v16;
        v18 = L"error %d setting RASFlags";
        goto LABEL_43;
      }
    }
    else if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    {
      v17 = *(unsigned int *)v24;
      v18 = L"RASFlags already present with value %d";
LABEL_43:
      LOWORD(v28) = 0;
      FormatRRASErrorString(&v28, v18, v17);
      if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v28);
    }
    RegCloseKey(phkResult);
    phkResult = 0;
    RegCloseKey(v26);
    v26 = 0;
    v4 = ForceNetbtRegistryRead();
    goto LABEL_53;
  }
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) == 0LL )
    goto LABEL_53;
  v5 = L"EnableNetbtBcastForwarding : error %d opening NdisWanIP key\n";
LABEL_50:
  LOWORD(v28) = 0;
  FormatRRASErrorString(&v28, v5, v3);
LABEL_51:
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasRtrmgrTraceInfo, &v28);
LABEL_53:
  if ( hKey )
    RegCloseKey(hKey);
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( v26 )
    RegCloseKey(v26);
  if ( v2 )
  {
    v19 = GetProcessHeap();
    HeapFree(v19, 0, v2);
  }
  if ( (Microsoft_Windows_RRASEnableBits & 0x80u) != 0LL )
    McTemplateU0z_EventWriteTransfer(
      &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      RasRtrmgrTraceInfo,
      L"Leaving: EnableNetbtBcastForwarding");
  return v4;
}

```

## disassembly

```asm
0x18001f378  push    rbx
0x18001f37a  push    rsi
0x18001f37b  push    rdi
0x18001f37c  push    r12
0x18001f37e  push    r13
0x18001f380  push    r14
0x18001f382  push    r15
0x18001f384  sub     rsp, 0A70h
0x18001f38b  mov     rax, cs:__security_cookie
0x18001f392  xor     rax, rsp
0x18001f395  mov     [rsp+0AA8h+var_48], rax
0x18001f39d  xor     r15d, r15d
0x18001f3a0  mov     r14d, ecx
0x18001f3a3  lea     rcx, [rsp+0AA8h+var_244]; void *
0x18001f3ab  mov     [rsp+0AA8h+hKey], r15
0x18001f3b0  xor     edx, edx; Val
0x18001f3b2  mov     [rsp+0AA8h+var_A68], r15
0x18001f3b7  mov     r8d, 1FCh; Size
0x18001f3bd  mov     [rsp+0AA8h+var_A60], r15
0x18001f3c2  mov     [rsp+0AA8h+cbData], r15d
0x18001f3c7  mov     edi, r15d
0x18001f3ca  mov     [rsp+0AA8h+Type], r15d
0x18001f3cf  mov     dword ptr [rsp+0AA8h+Data], r15d
0x18001f3d4  mov     dword ptr [rsp+0AA8h+var_A6C], r15d
0x18001f3d9  mov     dword ptr [rsp+0AA8h+pszDest], r15d
0x18001f3e1  call    memset_0
0x18001f3e6  xor     edx, edx; Val
0x18001f3e8  mov     [rsp+0AA8h+var_A48], r15d
0x18001f3ed  mov     r8d, 7FCh; Size
0x18001f3f3  lea     rcx, [rsp+0AA8h+var_A44]; void *
0x18001f3f8  call    memset_0
0x18001f3fd  test    byte ptr cs:Microsoft_Windows_RRASEnableBits, 80h
0x18001f404  lea     r12, RasRtrmgrTraceInfo
0x18001f40b  lea     r13, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001f412  jz      short loc_18001F426
0x18001f414  lea     r8, aEnterenablenet; "EnterEnableNetbtBcastForwarding"
0x18001f41b  mov     rdx, r12
0x18001f41e  mov     rcx, r13
0x18001f421  call    McTemplateU0z_EventWriteTransfer
0x18001f426  lea     rax, [rsp+0AA8h+hKey]
0x18001f42b  mov     r9d, 20019h; samDesired
0x18001f431  xor     r8d, r8d; ulOptions
0x18001f434  mov     [rsp+0AA8h+phkResult], rax; phkResult
0x18001f439  lea     rdx, aSystemCurrentc_0; "System\\CurrentControlSet\\Services\\Tc"...
0x18001f440  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001f447  call    cs:__imp_RegOpenKeyExW
0x18001f44d  mov     ebx, eax
0x18001f44f  test    eax, eax
0x18001f451  jz      short loc_18001F46C
0x18001f453  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r15b
0x18001f45a  jge     loc_18001F905
0x18001f460  lea     rdx, aEnablenetbtbca_0; "EnableNetbtBcastForwarding : error %d o"...
0x18001f467  jmp     loc_18001F8D9
0x18001f46c  mov     rcx, [rsp+0AA8h+hKey]; hKey
0x18001f471  lea     rax, [rsp+0AA8h+cbData]
0x18001f476  mov     [rsp+0AA8h+lpcbData], rax; lpcbData
0x18001f47b  lea     r9, [rsp+0AA8h+Type]; lpType
0x18001f480  xor     r8d, r8d; lpReserved
0x18001f483  mov     [rsp+0AA8h+phkResult], r15; lpData
0x18001f488  lea     rdx, aIpconfig; "IpConfig"
0x18001f48f  call    cs:__imp_RegQueryValueExW
0x18001f495  mov     ebx, eax
0x18001f497  test    eax, eax
0x18001f499  jnz     loc_18001F8C9
0x18001f49f  mov     ebx, [rsp+0AA8h+cbData]
0x18001f4a3  call    cs:__imp_GetProcessHeap
0x18001f4a9  lea     r8, [rbx+2]; dwBytes
0x18001f4ad  xor     edx, edx; dwFlags
0x18001f4af  mov     rcx, rax; hHeap
0x18001f4b2  call    cs:__imp_HeapAlloc
0x18001f4b8  mov     rdi, rax
0x18001f4bb  test    rax, rax
0x18001f4be  jnz     short loc_18001F4F4
0x18001f4c0  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r15b
0x18001f4c7  lea     ebx, [rax+8]
0x18001f4ca  jge     loc_18001F905
0x18001f4d0  mov     r9d, [rsp+0AA8h+cbData]
0x18001f4d5  lea     rdx, aEnablenetbtbca_1; "EnableNetbtBcastForwarding : error %d a"...
0x18001f4dc  mov     r8d, ebx
0x18001f4df  mov     word ptr [rsp+0AA8h+var_A48], r15w
0x18001f4e5  lea     rcx, [rsp+0AA8h+var_A48]
0x18001f4ea  call    FormatRRASErrorString
0x18001f4ef  jmp     loc_18001F8EC
0x18001f4f4  mov     rcx, [rsp+0AA8h+hKey]; hKey
0x18001f4f9  lea     rax, [rsp+0AA8h+cbData]
0x18001f4fe  mov     [rsp+0AA8h+lpcbData], rax; lpcbData
0x18001f503  lea     r9, [rsp+0AA8h+Type]; lpType
0x18001f508  xor     r8d, r8d; lpReserved
0x18001f50b  mov     [rsp+0AA8h+phkResult], rdi; lpData
0x18001f510  lea     rdx, aIpconfig; "IpConfig"
0x18001f517  call    cs:__imp_RegQueryValueExW
0x18001f51d  mov     ebx, eax
0x18001f51f  test    eax, eax
0x18001f521  jnz     loc_18001F8C9
0x18001f527  cmp     [rsp+0AA8h+Type], 7
0x18001f52c  jnz     loc_18001F8C9
0x18001f532  mov     eax, [rsp+0AA8h+cbData]
0x18001f536  lea     edx, [rbx+7Bh]; Ch
0x18001f539  shr     rax, 1
0x18001f53c  mov     rcx, rdi; Str
0x18001f53f  mov     [rax+rdi], r15b
0x18001f543  call    cs:__imp_wcschr
0x18001f549  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r15b
0x18001f550  mov     rsi, rax
0x18001f553  jge     short loc_18001F588
0x18001f555  mov     r8, rax
0x18001f558  mov     word ptr [rsp+0AA8h+var_A48], r15w
0x18001f55e  lea     rdx, aInternalAdapte; "Internal adapter GUID is %lS"
0x18001f565  lea     rcx, [rsp+0AA8h+var_A48]
0x18001f56a  call    FormatRRASErrorString
0x18001f56f  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r15b
0x18001f576  jge     short loc_18001F588
0x18001f578  lea     r8, [rsp+0AA8h+var_A48]
0x18001f57d  mov     rdx, r12
0x18001f580  mov     rcx, r13
0x18001f583  call    McTemplateU0z_EventWriteTransfer
0x18001f588  lea     rax, [rsp+0AA8h+var_A68]
0x18001f58d  mov     r9d, 2001Fh; samDesired
0x18001f593  xor     r8d, r8d; ulOptions
0x18001f596  mov     [rsp+0AA8h+phkResult], rax; phkResult
0x18001f59b  lea     rdx, aSystemCurrentc_3; "System\\CurrentControlSet\\Services\\Ne"...
0x18001f5a2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001f5a9  call    cs:__imp_RegOpenKeyExW
0x18001f5af  mov     ebx, eax
0x18001f5b1  test    eax, eax
0x18001f5b3  jz      short loc_18001F5CE
0x18001f5b5  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r15b
0x18001f5bc  jge     loc_18001F905
0x18001f5c2  lea     rdx, aEnablenetbtbca_4; "EnableNetbtBcastForwarding : error %d o"...
0x18001f5c9  jmp     loc_18001F8D9
0x18001f5ce  mov     rcx, [rsp+0AA8h+var_A68]; hKey
0x18001f5d3  lea     rax, [rsp+0AA8h+cbData]
0x18001f5d8  mov     [rsp+0AA8h+lpcbData], rax; lpcbData
0x18001f5dd  lea     r9, [rsp+0AA8h+Type]; lpType
0x18001f5e2  lea     rax, [rsp+0AA8h+Data]
0x18001f5e7  mov     dword ptr [rsp+0AA8h+Data], r15d
0x18001f5ec  mov     ebx, 4
0x18001f5f1  mov     [rsp+0AA8h+phkResult], rax; lpData
0x18001f5f6  xor     r8d, r8d; lpReserved
0x18001f5f9  mov     [rsp+0AA8h+cbData], ebx
0x18001f5fd  lea     rdx, aEnableproxy; "EnableProxy"
0x18001f604  call    cs:__imp_RegQueryValueExW
0x18001f60a  mov     r9d, dword ptr [rsp+0AA8h+Data]
0x18001f60f  test    eax, eax
0x18001f611  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x18001f618  mov     edx, r9d
0x18001f61b  cmovnz  edx, r15d
0x18001f61f  mov     cs:g_dwOldNetbtProxyMode, edx
0x18001f625  test    al, al
0x18001f627  jns     short loc_18001F66A
0x18001f629  mov     r8d, r9d
0x18001f62c  mov     word ptr [rsp+0AA8h+var_A48], r15w
0x18001f632  lea     rdx, aNetbtProxyMode; "Netbt Proxy mode in registry is %d"
0x18001f639  lea     rcx, [rsp+0AA8h+var_A48]
0x18001f63e  call    FormatRRASErrorString
0x18001f643  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x18001f64a  test    al, al
0x18001f64c  jns     short loc_18001F665
0x18001f64e  lea     r8, [rsp+0AA8h+var_A48]
0x18001f653  mov     rdx, r12
0x18001f656  mov     rcx, r13
0x18001f659  call    McTemplateU0z_EventWriteTransfer
0x18001f65e  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x18001f665  mov     r9d, dword ptr [rsp+0AA8h+Data]
0x18001f66a  test    r14d, r14d
0x18001f66d  jnz     short loc_18001F6CA
0x18001f66f  cmp     r9d, 2
0x18001f673  jnz     short loc_18001F6D5
0x18001f675  mov     cs:g_dwOldNetbtProxyMode, r15d
0x18001f67c  mov     dword ptr [rsp+0AA8h+Data], r15d
0x18001f681  test    al, al
0x18001f683  jns     loc_18001F710
0x18001f689  xor     r8d, r8d
0x18001f68c  mov     word ptr [rsp+0AA8h+var_A48], r15w
0x18001f692  lea     rdx, aForcingNetbtPr; "Forcing Netbt Proxy mode to be %d"
0x18001f699  lea     rcx, [rsp+0AA8h+var_A48]
0x18001f69e  call    FormatRRASErrorString
0x18001f6a3  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r15b
0x18001f6aa  jge     short loc_18001F710
0x18001f6ac  lea     r8, [rsp+0AA8h+var_A48]
0x18001f6b1  mov     rdx, r12
0x18001f6b4  mov     rcx, r13
0x18001f6b7  call    McTemplateU0z_EventWriteTransfer
0x18001f6bc  mov     r9d, dword ptr [rsp+0AA8h+Data]
0x18001f6c1  mov     rax, cs:Microsoft_Windows_RRASEnableBits
0x18001f6c8  jmp     short loc_18001F6D5
0x18001f6ca  mov     r9d, 2
0x18001f6d0  mov     dword ptr [rsp+0AA8h+Data], r9d
0x18001f6d5  test    al, al
0x18001f6d7  jns     short loc_18001F710
0x18001f6d9  mov     r8d, cs:g_dwOldNetbtProxyMode
0x18001f6e0  lea     rdx, aOldNetbtProxyM; "Old Netbt Proxy mode is %d, New Nebt Pr"...
0x18001f6e7  lea     rcx, [rsp+0AA8h+var_A48]
0x18001f6ec  mov     word ptr [rsp+0AA8h+var_A48], r15w
0x18001f6f2  call    FormatRRASErrorString
0x18001f6f7  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r15b
0x18001f6fe  jge     short loc_18001F710
0x18001f700  lea     r8, [rsp+0AA8h+var_A48]
0x18001f705  mov     rdx, r12
0x18001f708  mov     rcx, r13
0x18001f70b  call    McTemplateU0z_EventWriteTransfer
0x18001f710  mov     eax, [rsp+0AA8h+cbData]
0x18001f714  lea     rdx, aEnableproxy; "EnableProxy"
0x18001f71b  mov     rcx, [rsp+0AA8h+var_A68]; hKey
0x18001f720  mov     r9d, ebx; dwType
0x18001f723  mov     dword ptr [rsp+0AA8h+lpcbData], eax; cbData
0x18001f727  xor     r8d, r8d; Reserved
0x18001f72a  lea     rax, [rsp+0AA8h+Data]
0x18001f72f  mov     [rsp+0AA8h+phkResult], rax; lpData
0x18001f734  call    cs:__imp_RegSetValueExW
0x18001f73a  mov     ebx, eax
0x18001f73c  test    eax, eax
0x18001f73e  jz      short loc_18001F759
0x18001f740  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r15b
0x18001f747  jge     loc_18001F905
0x18001f74d  lea     rdx, aEnablenetbtbca_3; "EnableNetbtBcastForwarding : error %d s"...
0x18001f754  jmp     loc_18001F8D9
0x18001f759  mov     r9, rsi
0x18001f75c  lea     r8, aSystemCurrentc_1; "System\\CurrentControlSet\\Services\\Ne"...
0x18001f763  mov     edx, 200h; cbDest
0x18001f768  lea     rcx, [rsp+0AA8h+pszDest]; pszDest
0x18001f770  call    StringCbPrintfW
0x18001f775  lea     rax, [rsp+0AA8h+var_A60]
0x18001f77a  mov     r9d, 2001Fh; samDesired
0x18001f780  xor     r8d, r8d; ulOptions
0x18001f783  mov     [rsp+0AA8h+phkResult], rax; phkResult
0x18001f788  lea     rdx, [rsp+0AA8h+pszDest]; lpSubKey
0x18001f790  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001f797  call    cs:__imp_RegOpenKeyExW
0x18001f79d  mov     ebx, eax
0x18001f79f  test    eax, eax
0x18001f7a1  jz      short loc_18001F7D7
0x18001f7a3  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r15b
0x18001f7aa  jge     loc_18001F905
0x18001f7b0  lea     r9, [rsp+0AA8h+pszDest]
0x18001f7b8  mov     word ptr [rsp+0AA8h+var_A48], r15w
0x18001f7be  mov     r8d, eax
0x18001f7c1  lea     rdx, aEnablenetbtbca_5; "EnableNetbtBcastForwarding : error %d o"...
0x18001f7c8  lea     rcx, [rsp+0AA8h+var_A48]
0x18001f7cd  call    FormatRRASErrorString
0x18001f7d2  jmp     loc_18001F8EC
0x18001f7d7  mov     rcx, [rsp+0AA8h+var_A60]; hKey
0x18001f7dc  lea     rax, [rsp+0AA8h+cbData]
0x18001f7e1  mov     [rsp+0AA8h+lpcbData], rax; lpcbData
0x18001f7e6  lea     r9, [rsp+0AA8h+Type]; lpType
0x18001f7eb  lea     rax, [rsp+0AA8h+var_A6C]
0x18001f7f0  mov     dword ptr [rsp+0AA8h+var_A6C], r15d
0x18001f7f5  mov     ebx, 4
0x18001f7fa  mov     [rsp+0AA8h+phkResult], rax; lpData
0x18001f7ff  xor     r8d, r8d; lpReserved
0x18001f802  mov     [rsp+0AA8h+cbData], ebx
0x18001f806  lea     rdx, aRasflags; "RASFlags"
0x18001f80d  call    cs:__imp_RegQueryValueExW
0x18001f813  test    eax, eax
0x18001f815  jz      loc_18001F8B2
0x18001f81b  mov     rcx, [rsp+0AA8h+var_A60]; hKey
0x18001f820  lea     rax, [rsp+0AA8h+var_A6C]
0x18001f825  mov     dword ptr [rsp+0AA8h+lpcbData], ebx; cbData
0x18001f829  lea     rdx, aRasflags; "RASFlags"
0x18001f830  mov     r9d, ebx; dwType
0x18001f833  mov     [rsp+0AA8h+phkResult], rax; lpData
0x18001f838  xor     r8d, r8d; Reserved
0x18001f83b  mov     dword ptr [rsp+0AA8h+var_A6C], 1
0x18001f843  call    cs:__imp_RegSetValueExW
0x18001f849  test    eax, eax
0x18001f84b  jz      short loc_18001F889
0x18001f84d  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r15b
0x18001f854  jge     short loc_18001F889
0x18001f856  mov     r8d, eax
0x18001f859  lea     rdx, aErrorDSettingR; "error %d setting RASFlags"
0x18001f860  lea     rcx, [rsp+0AA8h+var_A48]
0x18001f865  mov     word ptr [rsp+0AA8h+var_A48], r15w
0x18001f86b  call    FormatRRASErrorString
0x18001f870  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r15b
0x18001f877  jge     short loc_18001F889
0x18001f879  lea     r8, [rsp+0AA8h+var_A48]
0x18001f87e  mov     rdx, r12
0x18001f881  mov     rcx, r13
0x18001f884  call    McTemplateU0z_EventWriteTransfer
0x18001f889  mov     rcx, [rsp+0AA8h+var_A68]; hKey
0x18001f88e  call    cs:__imp_RegCloseKey
0x18001f894  mov     rcx, [rsp+0AA8h+var_A60]; hKey
0x18001f899  mov     [rsp+0AA8h+var_A68], r15
0x18001f89e  call    cs:__imp_RegCloseKey
0x18001f8a4  mov     [rsp+0AA8h+var_A60], r15
0x18001f8a9  call    ForceNetbtRegistryRead
0x18001f8ae  mov     ebx, eax
0x18001f8b0  jmp     short loc_18001F905
0x18001f8b2  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r15b
0x18001f8b9  jge     short loc_18001F889
0x18001f8bb  mov     r8d, dword ptr [rsp+0AA8h+var_A6C]
0x18001f8c0  lea     rdx, aRasflagsAlread; "RASFlags already present with value %d"
0x18001f8c7  jmp     short loc_18001F860
0x18001f8c9  cmp     byte ptr cs:Microsoft_Windows_RRASEnableBits, r15b
0x18001f8d0  jge     short loc_18001F905
0x18001f8d2  lea     rdx, aEnablenetbtbca; "EnableNetbtBcastForwarding : error %d q"...
0x18001f8d9  mov     r8d, eax
0x18001f8dc  mov     word ptr [rsp+0AA8h+var_A48], r15w
0x18001f8e2  lea     rcx, [rsp+0AA8h+var_A48]
0x18001f8e7  call    FormatRRASErrorString
  ... truncated ...
```
