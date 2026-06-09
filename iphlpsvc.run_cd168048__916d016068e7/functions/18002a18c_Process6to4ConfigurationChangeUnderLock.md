# Process6to4ConfigurationChangeUnderLock

- ea: `0x18002a18c`
- end: `0x18002a9fc`
- name: `Process6to4ConfigurationChangeUnderLock`
- size: `2160`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180004b00`

## callees

- `0x180001d14`
- `0x180009000`
- `0x18000d7b0`
- `0x18002a18c`
- `0x18002aa10`
- `0x18002b46c`
- `0x18002c824`
- `0x18003b7d8`
- `0x18003ff98`
- `0x18004b630`
- `0x18004c1c8`
- `0x18004fa8c`
- `0x18005df14`
- `0x180082054`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002a2a1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002a31d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002a48d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002a4f9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002a560`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002a5c7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002a63c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002a76f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002a816`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002a87d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002a2a1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002a31d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002a48d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002a4f9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002a560`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002a5c7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002a63c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002a76f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002a816`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002a87d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a98b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a9a2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a98b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a9a2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002a21e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002a24c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002a21e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002a24c`

## string_xrefs

- `0x18002a34b`: `Not Configured`
- `0x18002a382`: `Not Configured`
- `0x18002a66a`: `Not Configured`
- `0x18002a6a1`: `Not Configured`
- `0x18002a3a6`: `GP: 6to4 state is configured in GP: %ws`
- `0x18002a20d`: `System\CurrentControlSet\Services\iphlpsvc\Config`
- `0x18002a926`: `6to4ConfigChange: Enable6to4 = %ls.`
- `0x18002a714`: `GP: for %ws, no relay/server name configured`
- `0x18002a7a6`: `6to4.ipv6.microsoft.com.`
- `0x18002a3e6`: `GP: 6to4 state is not configured in GP.`
- `0x18002a6f2`: `GP: for %ws, a relay/server name is configured: %ws`
- `0x18002a1d6`: `Entered: Process6to4ConfigurationChangeUnderLock`
- `0x18002a9c0`: `Leaving: Process6to4ConfigurationChange`

## pseudocode

```c
LSTATUS Process6to4ConfigurationChangeUnderLock()
{
  int v0; // eax
  __int64 v1; // rsi
  const wchar_t *v2; // rcx
  __int64 v3; // rdx
  BYTE *v4; // rax
  BYTE *v5; // rcx
  unsigned int StateFromGPString; // eax
  unsigned int v7; // edi
  unsigned int Integer; // eax
  DWORD v9; // eax
  DWORD v10; // eax
  DWORD v11; // eax
  DWORD v12; // eax
  const wchar_t *v13; // rcx
  __int64 v14; // rdx
  BYTE *v15; // rax
  BYTE *v16; // rcx
  __int64 v17; // rax
  wchar_t *v18; // rdi
  const wchar_t *v19; // rax
  wchar_t *v20; // rcx
  int v21; // ecx
  DWORD v22; // eax
  unsigned int v23; // eax
  int v24; // eax
  LSTATUS result; // eax
  __int64 *v26; // rbx
  DWORD Type; // [rsp+30h] [rbp-D0h] BYREF
  BYTE Data[4]; // [rsp+34h] [rbp-CCh] BYREF
  DWORD cbData; // [rsp+38h] [rbp-C8h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t v32[1032]; // [rsp+50h] [rbp-B0h] BYREF

  hKey = 0;
  phkResult = 0;
  if ( IpHlpSvcEtwEnabled && (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x800000) != 0 )
    McTemplateU0z_EventWriteTransfer(
      MS_IPHLPSVC_ETW_PROVIDER_ID_Context,
      EVENT_IPHLPSVC_ETW_FUNCTION_ENTRY_EXIT_MESSAGE,
      L"Entered: Process6to4ConfigurationChangeUnderLock");
  hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services\\iphlpsvc\\Config", 0, 1u, &hKey);
  phkResult = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  RegOpenKeyExW(
    HKEY_LOCAL_MACHINE,
    L"SOFTWARE\\Policies\\Microsoft\\Windows\\Tcpip\\v6Transition",
    0,
    0x20019u,
    &phkResult);
  Type = 0;
  *(_DWORD *)Data = 0;
  if ( hKey == HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL
    || (cbData = 4, RegQueryValueExW(hKey, L"UndoOnStop", 0, &Type, Data, &cbData))
    || Type != 4 )
  {
    v0 = 2;
  }
  else
  {
    v0 = *(_DWORD *)Data;
    if ( !*(_DWORD *)Data )
      v0 = 2;
  }
  dword_1800C9738 = v0;
  *(_DWORD *)Data = 0;
  memset_0(v32, 0, 0x802u);
  v1 = 1025;
  if ( phkResult == HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL
    || (Type = 2048, RegQueryValueExW(phkResult, L"6to4_State", 0, (LPDWORD)Data, (LPBYTE)v32, &Type))
    || *(_DWORD *)Data != 1
    || !v32[0] )
  {
    v2 = L"Not Configured";
    v3 = 1025;
    v4 = (BYTE *)v32;
    do
    {
      if ( !*v2 )
        break;
      *(_WORD *)v4 = *v2++;
      v4 += 2;
      --v3;
    }
    while ( v3 );
    v5 = v4 - 2;
    if ( v3 )
      v5 = v4;
    *(_WORD *)v5 = 0;
  }
  else
  {
    v32[(unsigned __int64)Type >> 1] = 0;
  }
  if ( !wcscmp_0(v32, L"Not Configured") )
  {
    EventWrite0(0x1000000, L"GP: 6to4 state is not configured in GP.");
  }
  else
  {
    EventWrite0(0x1000000, L"GP: 6to4 state is configured in GP: %ws", v32);
    StateFromGPString = GetStateFromGPString(v32);
    v7 = StateFromGPString;
    if ( StateFromGPString != 4 )
    {
      if ( StateFromGPString - 1 <= 1 )
        SixToFourTelemetryWriteEnabled(L"GP", (unsigned int)xmmword_1800C9770, StateFromGPString);
      if ( !v7 )
        goto LABEL_29;
LABEL_32:
      LODWORD(xmmword_1800C9770) = v7;
      goto LABEL_33;
    }
  }
  if ( (byte_1800C9734 & 2) == 0 )
  {
    Integer = GetInteger(hKey, L"Enable6to4", 3);
    v7 = Integer;
    if ( Integer - 1 <= 1 )
      SixToFourTelemetryWriteEnabled(L"Reg", (unsigned int)xmmword_1800C9770, Integer);
    goto LABEL_32;
  }
LABEL_29:
  LODWORD(xmmword_1800C9770) = 3;
LABEL_33:
  *(_DWORD *)Data = 0;
  Type = 0;
  if ( hKey == HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL
    || (cbData = 4, RegQueryValueExW(hKey, L"Allow6to4Sharing", 0, (LPDWORD)Data, (LPBYTE)&Type, &cbData))
    || *(_DWORD *)Data != 4 )
  {
    v9 = 3;
  }
  else
  {
    v9 = Type;
    if ( !Type )
      v9 = 3;
  }
  DWORD1(xmmword_1800C9770) = v9;
  *(_DWORD *)Data = 0;
  Type = 0;
  if ( hKey == HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL
    || (cbData = 4, RegQueryValueExW(hKey, L"EnableRouting", 0, (LPDWORD)Data, (LPBYTE)&Type, &cbData))
    || *(_DWORD *)Data != 4 )
  {
    v10 = 1;
  }
  else
  {
    v10 = Type;
    if ( !Type )
      v10 = 1;
  }
  DWORD2(xmmword_1800C9770) = v10;
  *(_DWORD *)Data = 0;
  Type = 0;
  if ( hKey == HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL
    || (cbData = 4, RegQueryValueExW(hKey, L"EnableSiteLocals", 0, (LPDWORD)Data, (LPBYTE)&Type, &cbData))
    || *(_DWORD *)Data != 4 )
  {
    v11 = 2;
  }
  else
  {
    v11 = Type;
    if ( !Type )
      v11 = 2;
  }
  dword_1800C9780 = v11;
  *(_DWORD *)Data = 0;
  Type = 0;
  if ( hKey == HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL
    || (cbData = 4, RegQueryValueExW(hKey, L"EnableResolution", 0, (LPDWORD)Data, (LPBYTE)&Type, &cbData))
    || *(_DWORD *)Data != 4 )
  {
    v12 = 1;
  }
  else
  {
    v12 = Type;
    if ( !Type )
      v12 = 1;
  }
  HIDWORD(xmmword_1800C9770) = v12;
  *(_DWORD *)Data = 0;
  memset_0(v32, 0, 0x802u);
  if ( phkResult == HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL
    || (Type = 2048, RegQueryValueExW(phkResult, L"6to4_RouterName", 0, (LPDWORD)Data, (LPBYTE)v32, &Type))
    || *(_DWORD *)Data != 1
    || !v32[0] )
  {
    v13 = L"Not Configured";
    v14 = 1025;
    v15 = (BYTE *)v32;
    do
    {
      if ( !*v13 )
        break;
      *(_WORD *)v15 = *v13++;
      v15 += 2;
      --v14;
    }
    while ( v14 );
    v16 = v15 - 2;
    if ( v14 )
      v16 = v15;
    *(_WORD *)v16 = 0;
  }
  else
  {
    v32[(unsigned __int64)Type >> 1] = 0;
  }
  if ( !wcscmp_0(v32, L"Not Configured") )
    goto LABEL_73;
  v17 = -1;
  do
    ++v17;
  while ( v32[v17] );
  if ( (unsigned int)(v17 - 1) > 0x3FF )
  {
LABEL_73:
    EventWrite0(0x800000, L"GP: for %ws, no relay/server name configured", L"6to4_RouterName");
    v18 = &pszDest;
    *(_DWORD *)Data = 0;
    memset_0(&pszDest, 0, 0x802u);
    if ( hKey == HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL
      || (Type = 2048, RegQueryValueExW(hKey, L"RelayName", 0, (LPDWORD)Data, (LPBYTE)&pszDest, &Type))
      || *(_DWORD *)Data != 1
      || !pszDest )
    {
      v19 = L"6to4.ipv6.microsoft.com.";
      do
      {
        if ( !*v19 )
          break;
        *v18++ = *v19++;
        --v1;
      }
      while ( v1 );
      v20 = v18 - 1;
      if ( v1 )
        v20 = v18;
      *v20 = 0;
    }
    else
    {
      *((_WORD *)&g_ProtocolState6to4 + ((unsigned __int64)Type >> 1) + 52) = 0;
    }
  }
  else
  {
    StringCchCopyW(&pszDest, 0x401u, v32);
    EventWrite0(0x800000, L"GP: for %ws, a relay/server name is configured: %ws", L"6to4_RouterName", &pszDest);
  }
  if ( phkResult == HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL
    || (*(_DWORD *)Data = 0,
        Type = 0,
        cbData = 4,
        RegQueryValueExW(phkResult, L"6to4_RouterNameResolutionInterval", 0, (LPDWORD)Data, (LPBYTE)&Type, &cbData))
    || *(_DWORD *)Data != 4 )
  {
    *(_DWORD *)Data = 0;
    Type = 0;
    if ( hKey == HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL
      || (cbData = 4, RegQueryValueExW(hKey, L"ResolutionInterval", 0, (LPDWORD)Data, (LPBYTE)&Type, &cbData)) )
    {
      v21 = 1440;
    }
    else
    {
      v21 = 1440;
      if ( *(_DWORD *)Data == 4 )
      {
        v22 = Type;
        if ( !Type )
          v22 = 1440;
        v21 = v22;
      }
    }
    dword_1800C9784 = v21;
  }
  else
  {
    dword_1800C9784 = Type;
  }
  if ( (_DWORD)xmmword_1800C9770 == 3 )
  {
    *((_QWORD *)&xmmword_1800C9770 + 1) = 0x300000003LL;
  }
  else
  {
    if ( !dword_1800CA020 )
    {
      v23 = RegisterNotificationHandlers(&g_ProtocolState6to4, &off_1800C8000, 160);
      if ( v23 )
        EventWrite0(0x1000000, L"Failed to register 6to4 for NSI notifications: %d", v23);
      else
        dword_1800CA020 = 1;
    }
    if ( !qword_1800C9FC0 )
      RegisterForGlobalConnectivityNotification(&qword_1800C9FC0, OnConnectivityStatusChange6to4);
  }
  v24 = xmmword_1800C9770;
  if ( (unsigned int)xmmword_1800C9770 > 3 )
    v24 = 4;
  result = EventWrite0(0x1000000, L"6to4ConfigChange: Enable6to4 = %ls.", STATE_STRINGS[v24]);
  v26 = (__int64 *)g_ProtocolState6to4;
  if ( g_ProtocolState6to4 )
  {
    while ( v26 != &g_ProtocolState6to4 )
    {
      ForEachInterfaceInCompartment(v26, Read6to4SpecificInterfaceSettings, 0, 0);
      result = CompartmentRequirementChangeNotification6to4(v26, 0);
      v26 = (__int64 *)*v26;
    }
  }
  if ( hKey != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
    result = RegCloseKey(hKey);
  if ( phkResult != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
    result = RegCloseKey(phkResult);
  if ( IpHlpSvcEtwEnabled )
  {
    if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x800000) != 0 )
      return McTemplateU0z_EventWriteTransfer(
               MS_IPHLPSVC_ETW_PROVIDER_ID_Context,
               EVENT_IPHLPSVC_ETW_FUNCTION_ENTRY_EXIT_MESSAGE,
               L"Leaving: Process6to4ConfigurationChange");
  }
  return result;
}

```

## disassembly

```asm
0x18002a18c  push    rbp
0x18002a18e  push    rbx
0x18002a18f  push    rsi
0x18002a190  push    rdi
0x18002a191  push    r12
0x18002a193  push    r13
0x18002a195  push    r15
0x18002a197  lea     rbp, [rsp-770h]
0x18002a19f  sub     rsp, 870h
0x18002a1a6  mov     rax, cs:__security_cookie
0x18002a1ad  xor     rax, rsp
0x18002a1b0  mov     [rbp+7A0h+var_40], rax
0x18002a1b7  xor     r15d, r15d
0x18002a1ba  cmp     cs:IpHlpSvcEtwEnabled, r15b
0x18002a1c1  mov     [rsp+8A0h+hKey], r15
0x18002a1c6  mov     [rsp+8A0h+var_858], r15
0x18002a1cb  jz      short loc_18002A1F0
0x18002a1cd  cmp     byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, r15b
0x18002a1d4  jge     short loc_18002A1F0
0x18002a1d6  lea     r8, aEnteredProcess; "Entered: Process6to4ConfigurationChange"...
0x18002a1dd  lea     rdx, EVENT_IPHLPSVC_ETW_FUNCTION_ENTRY_EXIT_MESSAGE
0x18002a1e4  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x18002a1eb  call    McTemplateU0z_EventWriteTransfer
0x18002a1f0  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18002a1f4  lea     rax, [rsp+8A0h+hKey]
0x18002a1f9  mov     rbx, 0FFFFFFFF80000002h
0x18002a200  mov     [rsp+8A0h+hKey], rdi
0x18002a205  xor     r8d, r8d; ulOptions
0x18002a208  mov     [rsp+8A0h+phkResult], rax; phkResult
0x18002a20d  lea     rdx, aSystemCurrentc_5; "System\\CurrentControlSet\\Services\\ip"...
0x18002a214  mov     rcx, rbx; hKey
0x18002a217  lea     r12d, [rdi+2]
0x18002a21b  mov     r9d, r12d; samDesired
0x18002a21e  call    cs:__imp_RegOpenKeyExW
0x18002a225  nop     dword ptr [rax+rax+00h]
0x18002a22a  lea     rax, [rsp+8A0h+var_858]
0x18002a22f  mov     [rsp+8A0h+var_858], rdi
0x18002a234  mov     r9d, 20019h; samDesired
0x18002a23a  mov     [rsp+8A0h+phkResult], rax; phkResult
0x18002a23f  xor     r8d, r8d; ulOptions
0x18002a242  lea     rdx, aSoftwarePolici; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x18002a249  mov     rcx, rbx; hKey
0x18002a24c  call    cs:__imp_RegOpenKeyExW
0x18002a253  nop     dword ptr [rax+rax+00h]
0x18002a258  mov     rcx, [rsp+8A0h+hKey]; hKey
0x18002a25d  lea     r13d, [rdi+5]
0x18002a261  mov     [rsp+8A0h+Type], r15d
0x18002a266  mov     dword ptr [rsp+8A0h+Data], r15d
0x18002a26b  cmp     rcx, rdi
0x18002a26e  jnz     short loc_18002A279
0x18002a270  mov     ebx, 2
0x18002a275  mov     eax, ebx
0x18002a277  jmp     short loc_18002A2C4
0x18002a279  lea     rax, [rsp+8A0h+cbData]
0x18002a27e  mov     [rsp+8A0h+cbData], r13d
0x18002a283  mov     [rsp+8A0h+lpcbData], rax; lpcbData
0x18002a288  lea     r9, [rsp+8A0h+Type]; lpType
0x18002a28d  lea     rax, [rsp+8A0h+Data]
0x18002a292  xor     r8d, r8d; lpReserved
0x18002a295  lea     rdx, aUndoonstop; "UndoOnStop"
0x18002a29c  mov     [rsp+8A0h+phkResult], rax; lpData
0x18002a2a1  call    cs:__imp_RegQueryValueExW
0x18002a2a8  nop     dword ptr [rax+rax+00h]
0x18002a2ad  test    eax, eax
0x18002a2af  jnz     short loc_18002A270
0x18002a2b1  lea     ebx, [rax+2]
0x18002a2b4  cmp     [rsp+8A0h+Type], r13d
0x18002a2b9  jnz     short loc_18002A275
0x18002a2bb  mov     eax, dword ptr [rsp+8A0h+Data]
0x18002a2bf  test    eax, eax
0x18002a2c1  cmovz   eax, ebx
0x18002a2c4  xor     edx, edx; Val
0x18002a2c6  mov     cs:dword_1800C9738, eax
0x18002a2cc  mov     r8d, 802h; Size
0x18002a2d2  mov     dword ptr [rsp+8A0h+Data], r15d
0x18002a2d7  lea     rcx, [rsp+8A0h+var_850]; void *
0x18002a2dc  call    memset_0
0x18002a2e1  mov     esi, 401h
0x18002a2e6  cmp     [rsp+8A0h+var_858], rdi
0x18002a2eb  jz      short loc_18002A34B
0x18002a2ed  mov     rcx, [rsp+8A0h+var_858]; hKey
0x18002a2f2  lea     rax, [rsp+8A0h+Type]
0x18002a2f7  mov     [rsp+8A0h+lpcbData], rax; lpcbData
0x18002a2fc  lea     r9, [rsp+8A0h+Data]; lpType
0x18002a301  lea     rax, [rsp+8A0h+var_850]
0x18002a306  mov     [rsp+8A0h+Type], 800h
0x18002a30e  xor     r8d, r8d; lpReserved
0x18002a311  mov     [rsp+8A0h+phkResult], rax; lpData
0x18002a316  lea     rdx, a6to4State; "6to4_State"
0x18002a31d  call    cs:__imp_RegQueryValueExW
0x18002a324  nop     dword ptr [rax+rax+00h]
0x18002a329  test    eax, eax
0x18002a32b  jnz     short loc_18002A34B
0x18002a32d  cmp     dword ptr [rsp+8A0h+Data], r12d
0x18002a332  jnz     short loc_18002A34B
0x18002a334  cmp     [rsp+8A0h+var_850], r15w
0x18002a33a  jz      short loc_18002A34B
0x18002a33c  mov     ecx, [rsp+8A0h+Type]
0x18002a340  shr     rcx, 1
0x18002a343  mov     [rsp+rcx*2+8A0h+var_850], r15w
0x18002a349  jmp     short loc_18002A382
0x18002a34b  lea     rcx, aNotConfigured; "Not Configured"
0x18002a352  mov     rdx, rsi
0x18002a355  lea     rax, [rsp+8A0h+var_850]
0x18002a35a  movzx   r8d, word ptr [rcx]
0x18002a35e  test    r8w, r8w
0x18002a362  jz      short loc_18002A373
0x18002a364  mov     [rax], r8w
0x18002a368  add     rcx, rbx
0x18002a36b  add     rax, rbx
0x18002a36e  sub     rdx, r12
0x18002a371  jnz     short loc_18002A35A
0x18002a373  test    rdx, rdx
0x18002a376  lea     rcx, [rax-2]
0x18002a37a  cmovnz  rcx, rax
0x18002a37e  mov     [rcx], r15w
0x18002a382  lea     rdx, aNotConfigured; "Not Configured"
0x18002a389  lea     rcx, [rsp+8A0h+var_850]; String1
0x18002a38e  call    wcscmp_0
0x18002a393  mov     edi, 3
0x18002a398  mov     ecx, 1000000h
0x18002a39d  test    eax, eax
0x18002a39f  jz      short loc_18002A3E6
0x18002a3a1  lea     r8, [rsp+8A0h+var_850]
0x18002a3a6  lea     rdx, aGp6to4StateIsC; "GP: 6to4 state is configured in GP: %ws"
0x18002a3ad  call    EventWrite0
0x18002a3b2  lea     rcx, [rsp+8A0h+var_850]; String1
0x18002a3b7  call    GetStateFromGPString
0x18002a3bc  mov     edi, eax
0x18002a3be  cmp     eax, r13d
0x18002a3c1  jz      short loc_18002A3F4
0x18002a3c3  lea     ecx, [rax-1]
0x18002a3c6  cmp     ecx, r12d
0x18002a3c9  ja      short loc_18002A3E0
0x18002a3cb  mov     edx, dword ptr cs:xmmword_1800C9770
0x18002a3d1  lea     rcx, aGp; "GP"
0x18002a3d8  mov     r8d, eax
0x18002a3db  call    SixToFourTelemetryWriteEnabled
0x18002a3e0  test    edi, edi
0x18002a3e2  jnz     short loc_18002A440
0x18002a3e4  jmp     short loc_18002A401
0x18002a3e6  lea     rdx, aGp6to4StateIsN; "GP: 6to4 state is not configured in GP."
0x18002a3ed  call    EventWrite0
0x18002a3f2  jmp     short loc_18002A3F9
0x18002a3f4  mov     edi, 3
0x18002a3f9  test    cs:byte_1800C9734, bl
0x18002a3ff  jz      short loc_18002A40D
0x18002a401  mov     dword ptr cs:xmmword_1800C9770, 3
0x18002a40b  jmp     short loc_18002A446
0x18002a40d  mov     rcx, [rsp+8A0h+hKey]
0x18002a412  lea     rdx, aEnable6to4; "Enable6to4"
0x18002a419  mov     r8d, edi
0x18002a41c  call    GetInteger
0x18002a421  mov     edi, eax
0x18002a423  lea     ecx, [rax-1]
0x18002a426  cmp     ecx, r12d
0x18002a429  ja      short loc_18002A440
0x18002a42b  mov     edx, dword ptr cs:xmmword_1800C9770
0x18002a431  lea     rcx, aReg; "Reg"
0x18002a438  mov     r8d, eax
0x18002a43b  call    SixToFourTelemetryWriteEnabled
0x18002a440  mov     dword ptr cs:xmmword_1800C9770, edi
0x18002a446  mov     rcx, [rsp+8A0h+hKey]; hKey
0x18002a44b  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18002a44f  mov     dword ptr [rsp+8A0h+Data], r15d
0x18002a454  mov     [rsp+8A0h+Type], r15d
0x18002a459  cmp     rcx, rdi
0x18002a45c  jnz     short loc_18002A465
0x18002a45e  mov     eax, 3
0x18002a463  jmp     short loc_18002A4B2
0x18002a465  lea     rax, [rsp+8A0h+cbData]
0x18002a46a  mov     [rsp+8A0h+cbData], r13d
0x18002a46f  mov     [rsp+8A0h+lpcbData], rax; lpcbData
0x18002a474  lea     r9, [rsp+8A0h+Data]; lpType
0x18002a479  lea     rax, [rsp+8A0h+Type]
0x18002a47e  xor     r8d, r8d; lpReserved
0x18002a481  lea     rdx, aAllow6to4shari; "Allow6to4Sharing"
0x18002a488  mov     [rsp+8A0h+phkResult], rax; lpData
0x18002a48d  call    cs:__imp_RegQueryValueExW
0x18002a494  nop     dword ptr [rax+rax+00h]
0x18002a499  test    eax, eax
0x18002a49b  jnz     short loc_18002A45E
0x18002a49d  cmp     dword ptr [rsp+8A0h+Data], r13d
0x18002a4a2  jnz     short loc_18002A45E
0x18002a4a4  mov     eax, [rsp+8A0h+Type]
0x18002a4a8  mov     ecx, 3
0x18002a4ad  test    eax, eax
0x18002a4af  cmovz   eax, ecx
0x18002a4b2  mov     rcx, [rsp+8A0h+hKey]; hKey
0x18002a4b7  mov     dword ptr cs:xmmword_1800C9770+4, eax
0x18002a4bd  mov     dword ptr [rsp+8A0h+Data], r15d
0x18002a4c2  mov     [rsp+8A0h+Type], r15d
0x18002a4c7  cmp     rcx, rdi
0x18002a4ca  jnz     short loc_18002A4D1
0x18002a4cc  mov     eax, r12d
0x18002a4cf  jmp     short loc_18002A51A
0x18002a4d1  lea     rax, [rsp+8A0h+cbData]
0x18002a4d6  mov     [rsp+8A0h+cbData], r13d
0x18002a4db  mov     [rsp+8A0h+lpcbData], rax; lpcbData
0x18002a4e0  lea     r9, [rsp+8A0h+Data]; lpType
0x18002a4e5  lea     rax, [rsp+8A0h+Type]
0x18002a4ea  xor     r8d, r8d; lpReserved
0x18002a4ed  lea     rdx, aEnablerouting; "EnableRouting"
0x18002a4f4  mov     [rsp+8A0h+phkResult], rax; lpData
0x18002a4f9  call    cs:__imp_RegQueryValueExW
0x18002a500  nop     dword ptr [rax+rax+00h]
0x18002a505  test    eax, eax
0x18002a507  jnz     short loc_18002A4CC
0x18002a509  cmp     dword ptr [rsp+8A0h+Data], r13d
0x18002a50e  jnz     short loc_18002A4CC
0x18002a510  mov     eax, [rsp+8A0h+Type]
0x18002a514  test    eax, eax
0x18002a516  cmovz   eax, r12d
0x18002a51a  mov     rcx, [rsp+8A0h+hKey]; hKey
0x18002a51f  mov     dword ptr cs:xmmword_1800C9770+8, eax
0x18002a525  mov     dword ptr [rsp+8A0h+Data], r15d
0x18002a52a  mov     [rsp+8A0h+Type], r15d
0x18002a52f  cmp     rcx, rdi
0x18002a532  jnz     short loc_18002A538
0x18002a534  mov     eax, ebx
0x18002a536  jmp     short loc_18002A580
0x18002a538  lea     rax, [rsp+8A0h+cbData]
0x18002a53d  mov     [rsp+8A0h+cbData], r13d
0x18002a542  mov     [rsp+8A0h+lpcbData], rax; lpcbData
0x18002a547  lea     r9, [rsp+8A0h+Data]; lpType
0x18002a54c  lea     rax, [rsp+8A0h+Type]
0x18002a551  xor     r8d, r8d; lpReserved
0x18002a554  lea     rdx, aEnablesiteloca; "EnableSiteLocals"
0x18002a55b  mov     [rsp+8A0h+phkResult], rax; lpData
0x18002a560  call    cs:__imp_RegQueryValueExW
0x18002a567  nop     dword ptr [rax+rax+00h]
0x18002a56c  test    eax, eax
0x18002a56e  jnz     short loc_18002A534
0x18002a570  cmp     dword ptr [rsp+8A0h+Data], r13d
0x18002a575  jnz     short loc_18002A534
0x18002a577  mov     eax, [rsp+8A0h+Type]
0x18002a57b  test    eax, eax
0x18002a57d  cmovz   eax, ebx
0x18002a580  mov     rcx, [rsp+8A0h+hKey]; hKey
0x18002a585  mov     cs:dword_1800C9780, eax
0x18002a58b  mov     dword ptr [rsp+8A0h+Data], r15d
0x18002a590  mov     [rsp+8A0h+Type], r15d
0x18002a595  cmp     rcx, rdi
0x18002a598  jnz     short loc_18002A59F
0x18002a59a  mov     eax, r12d
0x18002a59d  jmp     short loc_18002A5E8
0x18002a59f  lea     rax, [rsp+8A0h+cbData]
0x18002a5a4  mov     [rsp+8A0h+cbData], r13d
0x18002a5a9  mov     [rsp+8A0h+lpcbData], rax; lpcbData
0x18002a5ae  lea     r9, [rsp+8A0h+Data]; lpType
0x18002a5b3  lea     rax, [rsp+8A0h+Type]
0x18002a5b8  xor     r8d, r8d; lpReserved
0x18002a5bb  lea     rdx, aEnableresoluti; "EnableResolution"
0x18002a5c2  mov     [rsp+8A0h+phkResult], rax; lpData
0x18002a5c7  call    cs:__imp_RegQueryValueExW
0x18002a5ce  nop     dword ptr [rax+rax+00h]
0x18002a5d3  test    eax, eax
0x18002a5d5  jnz     short loc_18002A59A
0x18002a5d7  cmp     dword ptr [rsp+8A0h+Data], r13d
0x18002a5dc  jnz     short loc_18002A59A
0x18002a5de  mov     eax, [rsp+8A0h+Type]
0x18002a5e2  test    eax, eax
0x18002a5e4  cmovz   eax, r12d
0x18002a5e8  xor     edx, edx; Val
0x18002a5ea  mov     dword ptr cs:xmmword_1800C9770+0Ch, eax
0x18002a5f0  mov     r8d, 802h; Size
0x18002a5f6  mov     dword ptr [rsp+8A0h+Data], r15d
0x18002a5fb  lea     rcx, [rsp+8A0h+var_850]; void *
0x18002a600  call    memset_0
0x18002a605  cmp     [rsp+8A0h+var_858], rdi
0x18002a60a  jz      short loc_18002A66A
0x18002a60c  mov     rcx, [rsp+8A0h+var_858]; hKey
0x18002a611  lea     rax, [rsp+8A0h+Type]
0x18002a616  mov     [rsp+8A0h+lpcbData], rax; lpcbData
0x18002a61b  lea     r9, [rsp+8A0h+Data]; lpType
0x18002a620  lea     rax, [rsp+8A0h+var_850]
0x18002a625  mov     [rsp+8A0h+Type], 800h
0x18002a62d  xor     r8d, r8d; lpReserved
0x18002a630  mov     [rsp+8A0h+phkResult], rax; lpData
0x18002a635  lea     rdx, a6to4Routername_0; "6to4_RouterName"
0x18002a63c  call    cs:__imp_RegQueryValueExW
0x18002a643  nop     dword ptr [rax+rax+00h]
0x18002a648  test    eax, eax
0x18002a64a  jnz     short loc_18002A66A
0x18002a64c  cmp     dword ptr [rsp+8A0h+Data], r12d
0x18002a651  jnz     short loc_18002A66A
0x18002a653  cmp     [rsp+8A0h+var_850], r15w
0x18002a659  jz      short loc_18002A66A
0x18002a65b  mov     ecx, [rsp+8A0h+Type]
0x18002a65f  shr     rcx, 1
0x18002a662  mov     [rsp+rcx*2+8A0h+var_850], r15w
0x18002a668  jmp     short loc_18002A6A1
0x18002a66a  lea     rcx, aNotConfigured; "Not Configured"
0x18002a671  mov     rdx, rsi
0x18002a674  lea     rax, [rsp+8A0h+var_850]
0x18002a679  movzx   r8d, word ptr [rcx]
0x18002a67d  test    r8w, r8w
0x18002a681  jz      short loc_18002A692
0x18002a683  mov     [rax], r8w
0x18002a687  add     rcx, rbx
  ... truncated ...
```
