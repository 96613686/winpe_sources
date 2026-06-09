# Process6to4ConfigurationChangeUnderLock

- ea: `0x18002a19c`
- end: `0x18002aa0c`
- name: `Process6to4ConfigurationChangeUnderLock`
- size: `2160`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180004b10`

## callees

- `0x180001d24`
- `0x180009010`
- `0x18000d7c0`
- `0x18002a19c`
- `0x18002aa20`
- `0x18002b47c`
- `0x18002c834`
- `0x18003b7e8`
- `0x18003ff58`
- `0x18004b5f0`
- `0x18004c188`
- `0x18004fa4c`
- `0x18005df34`
- `0x180082244`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002a2b1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002a32d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002a49d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002a509`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002a570`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002a5d7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002a64c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002a77f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002a826`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002a88d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002a2b1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002a32d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002a49d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002a509`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002a570`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002a5d7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002a64c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002a77f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002a826`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002a88d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a99b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a9b2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a99b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a9b2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002a22e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002a25c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002a22e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002a25c`

## string_xrefs

- `0x18002a35b`: `Not Configured`
- `0x18002a392`: `Not Configured`
- `0x18002a67a`: `Not Configured`
- `0x18002a6b1`: `Not Configured`
- `0x18002a3b6`: `GP: 6to4 state is configured in GP: %ws`
- `0x18002a21d`: `System\CurrentControlSet\Services\iphlpsvc\Config`
- `0x18002a936`: `6to4ConfigChange: Enable6to4 = %ls.`
- `0x18002a724`: `GP: for %ws, no relay/server name configured`
- `0x18002a7b6`: `6to4.ipv6.microsoft.com.`
- `0x18002a3f6`: `GP: 6to4 state is not configured in GP.`
- `0x18002a702`: `GP: for %ws, a relay/server name is configured: %ws`
- `0x18002a1e6`: `Entered: Process6to4ConfigurationChangeUnderLock`
- `0x18002a9d0`: `Leaving: Process6to4ConfigurationChange`

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
0x18002a19c  push    rbp
0x18002a19e  push    rbx
0x18002a19f  push    rsi
0x18002a1a0  push    rdi
0x18002a1a1  push    r12
0x18002a1a3  push    r13
0x18002a1a5  push    r15
0x18002a1a7  lea     rbp, [rsp-770h]
0x18002a1af  sub     rsp, 870h
0x18002a1b6  mov     rax, cs:__security_cookie
0x18002a1bd  xor     rax, rsp
0x18002a1c0  mov     [rbp+7A0h+var_40], rax
0x18002a1c7  xor     r15d, r15d
0x18002a1ca  cmp     cs:IpHlpSvcEtwEnabled, r15b
0x18002a1d1  mov     [rsp+8A0h+hKey], r15
0x18002a1d6  mov     [rsp+8A0h+var_858], r15
0x18002a1db  jz      short loc_18002A200
0x18002a1dd  cmp     byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, r15b
0x18002a1e4  jge     short loc_18002A200
0x18002a1e6  lea     r8, aEnteredProcess; "Entered: Process6to4ConfigurationChange"...
0x18002a1ed  lea     rdx, EVENT_IPHLPSVC_ETW_FUNCTION_ENTRY_EXIT_MESSAGE
0x18002a1f4  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x18002a1fb  call    McTemplateU0z_EventWriteTransfer
0x18002a200  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18002a204  lea     rax, [rsp+8A0h+hKey]
0x18002a209  mov     rbx, 0FFFFFFFF80000002h
0x18002a210  mov     [rsp+8A0h+hKey], rdi
0x18002a215  xor     r8d, r8d; ulOptions
0x18002a218  mov     [rsp+8A0h+phkResult], rax; phkResult
0x18002a21d  lea     rdx, aSystemCurrentc_5; "System\\CurrentControlSet\\Services\\ip"...
0x18002a224  mov     rcx, rbx; hKey
0x18002a227  lea     r12d, [rdi+2]
0x18002a22b  mov     r9d, r12d; samDesired
0x18002a22e  call    cs:__imp_RegOpenKeyExW
0x18002a235  nop     dword ptr [rax+rax+00h]
0x18002a23a  lea     rax, [rsp+8A0h+var_858]
0x18002a23f  mov     [rsp+8A0h+var_858], rdi
0x18002a244  mov     r9d, 20019h; samDesired
0x18002a24a  mov     [rsp+8A0h+phkResult], rax; phkResult
0x18002a24f  xor     r8d, r8d; ulOptions
0x18002a252  lea     rdx, aSoftwarePolici; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x18002a259  mov     rcx, rbx; hKey
0x18002a25c  call    cs:__imp_RegOpenKeyExW
0x18002a263  nop     dword ptr [rax+rax+00h]
0x18002a268  mov     rcx, [rsp+8A0h+hKey]; hKey
0x18002a26d  lea     r13d, [rdi+5]
0x18002a271  mov     [rsp+8A0h+Type], r15d
0x18002a276  mov     dword ptr [rsp+8A0h+Data], r15d
0x18002a27b  cmp     rcx, rdi
0x18002a27e  jnz     short loc_18002A289
0x18002a280  mov     ebx, 2
0x18002a285  mov     eax, ebx
0x18002a287  jmp     short loc_18002A2D4
0x18002a289  lea     rax, [rsp+8A0h+cbData]
0x18002a28e  mov     [rsp+8A0h+cbData], r13d
0x18002a293  mov     [rsp+8A0h+lpcbData], rax; lpcbData
0x18002a298  lea     r9, [rsp+8A0h+Type]; lpType
0x18002a29d  lea     rax, [rsp+8A0h+Data]
0x18002a2a2  xor     r8d, r8d; lpReserved
0x18002a2a5  lea     rdx, aUndoonstop; "UndoOnStop"
0x18002a2ac  mov     [rsp+8A0h+phkResult], rax; lpData
0x18002a2b1  call    cs:__imp_RegQueryValueExW
0x18002a2b8  nop     dword ptr [rax+rax+00h]
0x18002a2bd  test    eax, eax
0x18002a2bf  jnz     short loc_18002A280
0x18002a2c1  lea     ebx, [rax+2]
0x18002a2c4  cmp     [rsp+8A0h+Type], r13d
0x18002a2c9  jnz     short loc_18002A285
0x18002a2cb  mov     eax, dword ptr [rsp+8A0h+Data]
0x18002a2cf  test    eax, eax
0x18002a2d1  cmovz   eax, ebx
0x18002a2d4  xor     edx, edx; Val
0x18002a2d6  mov     cs:dword_1800C9738, eax
0x18002a2dc  mov     r8d, 802h; Size
0x18002a2e2  mov     dword ptr [rsp+8A0h+Data], r15d
0x18002a2e7  lea     rcx, [rsp+8A0h+var_850]; void *
0x18002a2ec  call    memset_0
0x18002a2f1  mov     esi, 401h
0x18002a2f6  cmp     [rsp+8A0h+var_858], rdi
0x18002a2fb  jz      short loc_18002A35B
0x18002a2fd  mov     rcx, [rsp+8A0h+var_858]; hKey
0x18002a302  lea     rax, [rsp+8A0h+Type]
0x18002a307  mov     [rsp+8A0h+lpcbData], rax; lpcbData
0x18002a30c  lea     r9, [rsp+8A0h+Data]; lpType
0x18002a311  lea     rax, [rsp+8A0h+var_850]
0x18002a316  mov     [rsp+8A0h+Type], 800h
0x18002a31e  xor     r8d, r8d; lpReserved
0x18002a321  mov     [rsp+8A0h+phkResult], rax; lpData
0x18002a326  lea     rdx, a6to4State; "6to4_State"
0x18002a32d  call    cs:__imp_RegQueryValueExW
0x18002a334  nop     dword ptr [rax+rax+00h]
0x18002a339  test    eax, eax
0x18002a33b  jnz     short loc_18002A35B
0x18002a33d  cmp     dword ptr [rsp+8A0h+Data], r12d
0x18002a342  jnz     short loc_18002A35B
0x18002a344  cmp     [rsp+8A0h+var_850], r15w
0x18002a34a  jz      short loc_18002A35B
0x18002a34c  mov     ecx, [rsp+8A0h+Type]
0x18002a350  shr     rcx, 1
0x18002a353  mov     [rsp+rcx*2+8A0h+var_850], r15w
0x18002a359  jmp     short loc_18002A392
0x18002a35b  lea     rcx, aNotConfigured; "Not Configured"
0x18002a362  mov     rdx, rsi
0x18002a365  lea     rax, [rsp+8A0h+var_850]
0x18002a36a  movzx   r8d, word ptr [rcx]
0x18002a36e  test    r8w, r8w
0x18002a372  jz      short loc_18002A383
0x18002a374  mov     [rax], r8w
0x18002a378  add     rcx, rbx
0x18002a37b  add     rax, rbx
0x18002a37e  sub     rdx, r12
0x18002a381  jnz     short loc_18002A36A
0x18002a383  test    rdx, rdx
0x18002a386  lea     rcx, [rax-2]
0x18002a38a  cmovnz  rcx, rax
0x18002a38e  mov     [rcx], r15w
0x18002a392  lea     rdx, aNotConfigured; "Not Configured"
0x18002a399  lea     rcx, [rsp+8A0h+var_850]; String1
0x18002a39e  call    wcscmp_0
0x18002a3a3  mov     edi, 3
0x18002a3a8  mov     ecx, 1000000h
0x18002a3ad  test    eax, eax
0x18002a3af  jz      short loc_18002A3F6
0x18002a3b1  lea     r8, [rsp+8A0h+var_850]
0x18002a3b6  lea     rdx, aGp6to4StateIsC; "GP: 6to4 state is configured in GP: %ws"
0x18002a3bd  call    EventWrite0
0x18002a3c2  lea     rcx, [rsp+8A0h+var_850]; String1
0x18002a3c7  call    GetStateFromGPString
0x18002a3cc  mov     edi, eax
0x18002a3ce  cmp     eax, r13d
0x18002a3d1  jz      short loc_18002A404
0x18002a3d3  lea     ecx, [rax-1]
0x18002a3d6  cmp     ecx, r12d
0x18002a3d9  ja      short loc_18002A3F0
0x18002a3db  mov     edx, dword ptr cs:xmmword_1800C9770
0x18002a3e1  lea     rcx, aGp; "GP"
0x18002a3e8  mov     r8d, eax
0x18002a3eb  call    SixToFourTelemetryWriteEnabled
0x18002a3f0  test    edi, edi
0x18002a3f2  jnz     short loc_18002A450
0x18002a3f4  jmp     short loc_18002A411
0x18002a3f6  lea     rdx, aGp6to4StateIsN; "GP: 6to4 state is not configured in GP."
0x18002a3fd  call    EventWrite0
0x18002a402  jmp     short loc_18002A409
0x18002a404  mov     edi, 3
0x18002a409  test    cs:byte_1800C9734, bl
0x18002a40f  jz      short loc_18002A41D
0x18002a411  mov     dword ptr cs:xmmword_1800C9770, 3
0x18002a41b  jmp     short loc_18002A456
0x18002a41d  mov     rcx, [rsp+8A0h+hKey]
0x18002a422  lea     rdx, aEnable6to4; "Enable6to4"
0x18002a429  mov     r8d, edi
0x18002a42c  call    GetInteger
0x18002a431  mov     edi, eax
0x18002a433  lea     ecx, [rax-1]
0x18002a436  cmp     ecx, r12d
0x18002a439  ja      short loc_18002A450
0x18002a43b  mov     edx, dword ptr cs:xmmword_1800C9770
0x18002a441  lea     rcx, aReg; "Reg"
0x18002a448  mov     r8d, eax
0x18002a44b  call    SixToFourTelemetryWriteEnabled
0x18002a450  mov     dword ptr cs:xmmword_1800C9770, edi
0x18002a456  mov     rcx, [rsp+8A0h+hKey]; hKey
0x18002a45b  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18002a45f  mov     dword ptr [rsp+8A0h+Data], r15d
0x18002a464  mov     [rsp+8A0h+Type], r15d
0x18002a469  cmp     rcx, rdi
0x18002a46c  jnz     short loc_18002A475
0x18002a46e  mov     eax, 3
0x18002a473  jmp     short loc_18002A4C2
0x18002a475  lea     rax, [rsp+8A0h+cbData]
0x18002a47a  mov     [rsp+8A0h+cbData], r13d
0x18002a47f  mov     [rsp+8A0h+lpcbData], rax; lpcbData
0x18002a484  lea     r9, [rsp+8A0h+Data]; lpType
0x18002a489  lea     rax, [rsp+8A0h+Type]
0x18002a48e  xor     r8d, r8d; lpReserved
0x18002a491  lea     rdx, aAllow6to4shari; "Allow6to4Sharing"
0x18002a498  mov     [rsp+8A0h+phkResult], rax; lpData
0x18002a49d  call    cs:__imp_RegQueryValueExW
0x18002a4a4  nop     dword ptr [rax+rax+00h]
0x18002a4a9  test    eax, eax
0x18002a4ab  jnz     short loc_18002A46E
0x18002a4ad  cmp     dword ptr [rsp+8A0h+Data], r13d
0x18002a4b2  jnz     short loc_18002A46E
0x18002a4b4  mov     eax, [rsp+8A0h+Type]
0x18002a4b8  mov     ecx, 3
0x18002a4bd  test    eax, eax
0x18002a4bf  cmovz   eax, ecx
0x18002a4c2  mov     rcx, [rsp+8A0h+hKey]; hKey
0x18002a4c7  mov     dword ptr cs:xmmword_1800C9770+4, eax
0x18002a4cd  mov     dword ptr [rsp+8A0h+Data], r15d
0x18002a4d2  mov     [rsp+8A0h+Type], r15d
0x18002a4d7  cmp     rcx, rdi
0x18002a4da  jnz     short loc_18002A4E1
0x18002a4dc  mov     eax, r12d
0x18002a4df  jmp     short loc_18002A52A
0x18002a4e1  lea     rax, [rsp+8A0h+cbData]
0x18002a4e6  mov     [rsp+8A0h+cbData], r13d
0x18002a4eb  mov     [rsp+8A0h+lpcbData], rax; lpcbData
0x18002a4f0  lea     r9, [rsp+8A0h+Data]; lpType
0x18002a4f5  lea     rax, [rsp+8A0h+Type]
0x18002a4fa  xor     r8d, r8d; lpReserved
0x18002a4fd  lea     rdx, aEnablerouting; "EnableRouting"
0x18002a504  mov     [rsp+8A0h+phkResult], rax; lpData
0x18002a509  call    cs:__imp_RegQueryValueExW
0x18002a510  nop     dword ptr [rax+rax+00h]
0x18002a515  test    eax, eax
0x18002a517  jnz     short loc_18002A4DC
0x18002a519  cmp     dword ptr [rsp+8A0h+Data], r13d
0x18002a51e  jnz     short loc_18002A4DC
0x18002a520  mov     eax, [rsp+8A0h+Type]
0x18002a524  test    eax, eax
0x18002a526  cmovz   eax, r12d
0x18002a52a  mov     rcx, [rsp+8A0h+hKey]; hKey
0x18002a52f  mov     dword ptr cs:xmmword_1800C9770+8, eax
0x18002a535  mov     dword ptr [rsp+8A0h+Data], r15d
0x18002a53a  mov     [rsp+8A0h+Type], r15d
0x18002a53f  cmp     rcx, rdi
0x18002a542  jnz     short loc_18002A548
0x18002a544  mov     eax, ebx
0x18002a546  jmp     short loc_18002A590
0x18002a548  lea     rax, [rsp+8A0h+cbData]
0x18002a54d  mov     [rsp+8A0h+cbData], r13d
0x18002a552  mov     [rsp+8A0h+lpcbData], rax; lpcbData
0x18002a557  lea     r9, [rsp+8A0h+Data]; lpType
0x18002a55c  lea     rax, [rsp+8A0h+Type]
0x18002a561  xor     r8d, r8d; lpReserved
0x18002a564  lea     rdx, aEnablesiteloca; "EnableSiteLocals"
0x18002a56b  mov     [rsp+8A0h+phkResult], rax; lpData
0x18002a570  call    cs:__imp_RegQueryValueExW
0x18002a577  nop     dword ptr [rax+rax+00h]
0x18002a57c  test    eax, eax
0x18002a57e  jnz     short loc_18002A544
0x18002a580  cmp     dword ptr [rsp+8A0h+Data], r13d
0x18002a585  jnz     short loc_18002A544
0x18002a587  mov     eax, [rsp+8A0h+Type]
0x18002a58b  test    eax, eax
0x18002a58d  cmovz   eax, ebx
0x18002a590  mov     rcx, [rsp+8A0h+hKey]; hKey
0x18002a595  mov     cs:dword_1800C9780, eax
0x18002a59b  mov     dword ptr [rsp+8A0h+Data], r15d
0x18002a5a0  mov     [rsp+8A0h+Type], r15d
0x18002a5a5  cmp     rcx, rdi
0x18002a5a8  jnz     short loc_18002A5AF
0x18002a5aa  mov     eax, r12d
0x18002a5ad  jmp     short loc_18002A5F8
0x18002a5af  lea     rax, [rsp+8A0h+cbData]
0x18002a5b4  mov     [rsp+8A0h+cbData], r13d
0x18002a5b9  mov     [rsp+8A0h+lpcbData], rax; lpcbData
0x18002a5be  lea     r9, [rsp+8A0h+Data]; lpType
0x18002a5c3  lea     rax, [rsp+8A0h+Type]
0x18002a5c8  xor     r8d, r8d; lpReserved
0x18002a5cb  lea     rdx, aEnableresoluti; "EnableResolution"
0x18002a5d2  mov     [rsp+8A0h+phkResult], rax; lpData
0x18002a5d7  call    cs:__imp_RegQueryValueExW
0x18002a5de  nop     dword ptr [rax+rax+00h]
0x18002a5e3  test    eax, eax
0x18002a5e5  jnz     short loc_18002A5AA
0x18002a5e7  cmp     dword ptr [rsp+8A0h+Data], r13d
0x18002a5ec  jnz     short loc_18002A5AA
0x18002a5ee  mov     eax, [rsp+8A0h+Type]
0x18002a5f2  test    eax, eax
0x18002a5f4  cmovz   eax, r12d
0x18002a5f8  xor     edx, edx; Val
0x18002a5fa  mov     dword ptr cs:xmmword_1800C9770+0Ch, eax
0x18002a600  mov     r8d, 802h; Size
0x18002a606  mov     dword ptr [rsp+8A0h+Data], r15d
0x18002a60b  lea     rcx, [rsp+8A0h+var_850]; void *
0x18002a610  call    memset_0
0x18002a615  cmp     [rsp+8A0h+var_858], rdi
0x18002a61a  jz      short loc_18002A67A
0x18002a61c  mov     rcx, [rsp+8A0h+var_858]; hKey
0x18002a621  lea     rax, [rsp+8A0h+Type]
0x18002a626  mov     [rsp+8A0h+lpcbData], rax; lpcbData
0x18002a62b  lea     r9, [rsp+8A0h+Data]; lpType
0x18002a630  lea     rax, [rsp+8A0h+var_850]
0x18002a635  mov     [rsp+8A0h+Type], 800h
0x18002a63d  xor     r8d, r8d; lpReserved
0x18002a640  mov     [rsp+8A0h+phkResult], rax; lpData
0x18002a645  lea     rdx, a6to4Routername_0; "6to4_RouterName"
0x18002a64c  call    cs:__imp_RegQueryValueExW
0x18002a653  nop     dword ptr [rax+rax+00h]
0x18002a658  test    eax, eax
0x18002a65a  jnz     short loc_18002A67A
0x18002a65c  cmp     dword ptr [rsp+8A0h+Data], r12d
0x18002a661  jnz     short loc_18002A67A
0x18002a663  cmp     [rsp+8A0h+var_850], r15w
0x18002a669  jz      short loc_18002A67A
0x18002a66b  mov     ecx, [rsp+8A0h+Type]
0x18002a66f  shr     rcx, 1
0x18002a672  mov     [rsp+rcx*2+8A0h+var_850], r15w
0x18002a678  jmp     short loc_18002A6B1
0x18002a67a  lea     rcx, aNotConfigured; "Not Configured"
0x18002a681  mov     rdx, rsi
0x18002a684  lea     rax, [rsp+8A0h+var_850]
0x18002a689  movzx   r8d, word ptr [rcx]
0x18002a68d  test    r8w, r8w
0x18002a691  jz      short loc_18002A6A2
0x18002a693  mov     [rax], r8w
0x18002a697  add     rcx, rbx
  ... truncated ...
```
