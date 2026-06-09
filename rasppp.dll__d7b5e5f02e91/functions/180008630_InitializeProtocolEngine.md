# InitializeProtocolEngine

- ea: `0x180008630`
- end: `0x180008986`
- name: `InitializeProtocolEngine`
- size: `854`
- prototype: `__int64 __fastcall(void *, unsigned int, char)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003170`
- `0x1800046e0`
- `0x180005054`
- `0x180008630`
- `0x18002b0dc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18000892f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x18000892f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800088bc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800088bc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000895c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000895c`
- `rasman!RasGetPortUserData` at `0x1800087c9`
- `rasman!RasSendProtocolResultToRasman` at `0x18000874b`
- `rasman!RasPortSend` at `0x180008759`
- `rasman!RasGetBuffer` at `0x180008847`
- `rasman!RasInitializeNoWait` at `0x1800086ac`
- `rasman!RasInitializeNoWait` at `0x1800086ac`
- `rasman!RasBundleGetPort` at `0x18000879f`
- `rasman!RasPortGetStatisticsEx` at `0x180008767`
- `rasman!RasDeAllocateRoute` at `0x18000882b`
- `rasman!RasUpdateDefaultRouteSettings` at `0x180008801`
- `rasman!RasCompressionGetInfo` at `0x18000880f`
- `rasman!RasPortGetBundle` at `0x180008783`
- `rasman!RasProtocolStarted` at `0x180008721`
- `rasman!RasCompressionSetInfo` at `0x1800087e5`
- `rasman!RasPortSetFramingEx` at `0x1800087bb`
- `rasman!RasGetFramingCapabilities` at `0x1800087ad`
- `rasman!RasGetInfo` at `0x180008791`
- `rasman!RasPortCancelReceive` at `0x180008710`
- `rasman!RasPortSetProtocolCompression` at `0x180008855`
- `rasman!RasFreeBuffer` at `0x18000872f`
- `rasman!RasGetConnectInfo` at `0x180008775`
- `rasman!RasAllocateRoute` at `0x18000881d`
- `rasman!RasSetConnectionUserData` at `0x1800087d7`
- `rasman!RasActivateRoute` at `0x1800087f3`
- `rasman!RasPortGetProtocolCompression` at `0x180008839`
- `rasman!RasGetTimeSinceLastActivity` at `0x18000873d`

## string_xrefs

- `0x1800088ae`: `System\CurrentControlSet\Services\Rasman\Parameters`
- `0x1800088dd`: `System\CurrentControlSet\Services\Rasman\Parameters`
- `0x1800088e9`: `Failed to open registry: %hs`

## pseudocode

```c
__int64 __fastcall InitializeProtocolEngine(void *a1, unsigned int a2, char a3)
{
  DWORD v6; // eax
  DWORD v7; // ebx
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  BYTE Data[8]; // [rsp+38h] [rbp-C8h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  int v13; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v14[2044]; // [rsp+54h] [rbp-ACh] BYREF

  *(_DWORD *)Data = 0;
  cbData = 0;
  hKey = 0;
  Type = 0;
  v13 = 0;
  memset_0(v14, 0, sizeof(v14));
  if ( a2 > 0x3D )
    a2 = 61;
  LODWORD(qword_18004D970) = a2;
  if ( (a3 & 1) != 0 )
  {
    v6 = RasInitializeNoWait();
    v7 = v6;
    if ( v6 )
    {
      if ( byte_18004DF33 >= 0 )
        return v7;
      LOWORD(v13) = 0;
      FormatRRASErrorString((wchar_t *)&v13, L"RasInitializeNoWait failed: %d", v6);
      goto LABEL_7;
    }
  }
  *((_QWORD *)&xmmword_18004D450 + 1) = RasPortCancelReceive;
  *(_QWORD *)&xmmword_18004D420 = RasProtocolStarted;
  *(_QWORD *)&xmmword_18004D460 = RasFreeBuffer;
  *((_QWORD *)&xmmword_18004D420 + 1) = RasGetTimeSinceLastActivity;
  qword_18004D438 = RasSendProtocolResultToRasman;
  *((_QWORD *)&xmmword_18004D460 + 1) = RasPortSend;
  *(_QWORD *)&xmmword_18004D3F0 = RasPortGetStatisticsEx;
  *(_QWORD *)&xmmword_18004D470 = RasGetConnectInfo;
  *(_QWORD *)&xmmword_18004D410 = RasPortGetBundle;
  *((_QWORD *)&xmmword_18004D470 + 1) = RasGetInfo;
  *(_QWORD *)&xmmword_18004D480 = RasBundleGetPort;
  *((_QWORD *)&xmmword_18004D480 + 1) = RasGetFramingCapabilities;
  *(_QWORD *)&xmmword_18004D490 = RasPortSetFramingEx;
  qword_18004D408 = RasGetPortUserData;
  *((_QWORD *)&xmmword_18004D410 + 1) = RasSetConnectionUserData;
  *((_QWORD *)&xmmword_18004D490 + 1) = RasCompressionSetInfo;
  *((_QWORD *)&xmmword_18004D440 + 1) = RasActivateRoute;
  *(_QWORD *)&xmmword_18004D450 = RasUpdateDefaultRouteSettings;
  *(_QWORD *)&xmmword_18004D4A0 = RasCompressionGetInfo;
  *((_QWORD *)&xmmword_18004D3F0 + 1) = RasAllocateRoute;
  *(_QWORD *)&xmmword_18004D440 = RasDeAllocateRoute;
  *((_QWORD *)&xmmword_18004D4A0 + 1) = RasPortGetProtocolCompression;
  *(_QWORD *)&xmmword_18004D4B0 = RasGetBuffer;
  *((_QWORD *)&xmmword_18004D4B0 + 1) = RasPortSetProtocolCompression;
  v7 = InitializePPP(a1);
  if ( v7 )
  {
    PPPCleanUp();
    return v7;
  }
  if ( (byte_18004DF34 & 1) != 0 )
    McTemplateU0z_EventWriteTransfer(
      &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      RasPppTraceInfo,
      L"PPP Initialized successfully.");
  v7 = RegOpenKeyExA(HKEY_LOCAL_MACHINE, "System\\CurrentControlSet\\Services\\Rasman\\Parameters", 0, 0x20019u, &hKey);
  if ( v7 )
  {
    if ( byte_18004DF33 >= 0 )
      return v7;
    LOWORD(v13) = 0;
    FormatRRASErrorString(
      (wchar_t *)&v13,
      L"Failed to open registry: %hs",
      "System\\CurrentControlSet\\Services\\Rasman\\Parameters");
LABEL_7:
    if ( byte_18004DF33 < 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceError, &v13);
    return v7;
  }
  cbData = 4;
  v7 = RegQueryValueExA(hKey, "AllowPPTPWeakCrypto", 0, &Type, Data, &cbData);
  if ( !v7 && Type == 4 )
    g_dwAllowPPTPWeakCrypto = *(_DWORD *)Data;
  if ( hKey )
    RegCloseKey(hKey);
  return v7;
}

```

## disassembly

```asm
0x180008630  push    rbp
0x180008632  push    rbx
0x180008633  push    rsi
0x180008634  push    rdi
0x180008635  lea     rbp, [rsp-768h]
0x18000863d  sub     rsp, 868h
0x180008644  mov     rax, cs:__security_cookie
0x18000864b  xor     rax, rsp
0x18000864e  mov     [rbp+780h+var_30], rax
0x180008655  mov     edi, r8d
0x180008658  mov     dword ptr [rsp+880h+Data], 0
0x180008660  mov     ebx, edx
0x180008662  mov     [rsp+880h+cbData], 0
0x18000866a  mov     rsi, rcx
0x18000866d  mov     [rsp+880h+hKey], 0
0x180008676  xor     eax, eax
0x180008678  mov     [rsp+880h+Type], 0
0x180008680  xor     edx, edx; Val
0x180008682  mov     [rsp+880h+var_830], eax
0x180008686  mov     r8d, 7FCh; Size
0x18000868c  lea     rcx, [rsp+880h+var_82C]; void *
0x180008691  call    memset_0
0x180008696  mov     eax, 3Dh ; '='
0x18000869b  cmp     ebx, eax
0x18000869d  cmova   ebx, eax
0x1800086a0  mov     dword ptr cs:qword_18004D970, ebx
0x1800086a6  test    dil, 1
0x1800086aa  jz      short loc_180008710
0x1800086ac  call    cs:__imp_RasInitializeNoWait
0x1800086b3  nop     dword ptr [rax+rax+00h]
0x1800086b8  mov     ebx, eax
0x1800086ba  test    eax, eax
0x1800086bc  jz      short loc_180008710
0x1800086be  cmp     cs:byte_18004DF33, 0
0x1800086c5  jge     loc_180008968
0x1800086cb  xor     ecx, ecx
0x1800086cd  lea     rdx, aRasinitializen; "RasInitializeNoWait failed: %d"
0x1800086d4  mov     word ptr [rsp+880h+var_830], cx
0x1800086d9  mov     r8d, eax
0x1800086dc  lea     rcx, [rsp+880h+var_830]
0x1800086e1  call    FormatRRASErrorString
0x1800086e6  cmp     cs:byte_18004DF33, 0
0x1800086ed  jge     loc_180008968
0x1800086f3  lea     r8, [rsp+880h+var_830]
0x1800086f8  lea     rdx, RasPppTraceError
0x1800086ff  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180008706  call    McTemplateU0z_EventWriteTransfer
0x18000870b  jmp     loc_180008968
0x180008710  mov     rax, cs:__imp_RasPortCancelReceive
0x180008717  mov     rcx, rsi
0x18000871a  mov     qword ptr cs:xmmword_18004D450+8, rax
0x180008721  mov     rax, cs:__imp_RasProtocolStarted
0x180008728  mov     qword ptr cs:xmmword_18004D420, rax
0x18000872f  mov     rax, cs:__imp_RasFreeBuffer
0x180008736  mov     qword ptr cs:xmmword_18004D460, rax
0x18000873d  mov     rax, cs:__imp_RasGetTimeSinceLastActivity
0x180008744  mov     qword ptr cs:xmmword_18004D420+8, rax
0x18000874b  mov     rax, cs:__imp_RasSendProtocolResultToRasman
0x180008752  mov     cs:qword_18004D438, rax
0x180008759  mov     rax, cs:__imp_RasPortSend
0x180008760  mov     qword ptr cs:xmmword_18004D460+8, rax
0x180008767  mov     rax, cs:__imp_RasPortGetStatisticsEx
0x18000876e  mov     qword ptr cs:xmmword_18004D3F0, rax
0x180008775  mov     rax, cs:__imp_RasGetConnectInfo
0x18000877c  mov     qword ptr cs:xmmword_18004D470, rax
0x180008783  mov     rax, cs:__imp_RasPortGetBundle
0x18000878a  mov     qword ptr cs:xmmword_18004D410, rax
0x180008791  mov     rax, cs:__imp_RasGetInfo
0x180008798  mov     qword ptr cs:xmmword_18004D470+8, rax
0x18000879f  mov     rax, cs:__imp_RasBundleGetPort
0x1800087a6  mov     qword ptr cs:xmmword_18004D480, rax
0x1800087ad  mov     rax, cs:__imp_RasGetFramingCapabilities
0x1800087b4  mov     qword ptr cs:xmmword_18004D480+8, rax
0x1800087bb  mov     rax, cs:__imp_RasPortSetFramingEx
0x1800087c2  mov     qword ptr cs:xmmword_18004D490, rax
0x1800087c9  mov     rax, cs:__imp_RasGetPortUserData
0x1800087d0  mov     cs:qword_18004D408, rax
0x1800087d7  mov     rax, cs:__imp_RasSetConnectionUserData
0x1800087de  mov     qword ptr cs:xmmword_18004D410+8, rax
0x1800087e5  mov     rax, cs:__imp_RasCompressionSetInfo
0x1800087ec  mov     qword ptr cs:xmmword_18004D490+8, rax
0x1800087f3  mov     rax, cs:__imp_RasActivateRoute
0x1800087fa  mov     qword ptr cs:xmmword_18004D440+8, rax
0x180008801  mov     rax, cs:__imp_RasUpdateDefaultRouteSettings
0x180008808  mov     qword ptr cs:xmmword_18004D450, rax
0x18000880f  mov     rax, cs:__imp_RasCompressionGetInfo
0x180008816  mov     qword ptr cs:xmmword_18004D4A0, rax
0x18000881d  mov     rax, cs:__imp_RasAllocateRoute
0x180008824  mov     qword ptr cs:xmmword_18004D3F0+8, rax
0x18000882b  mov     rax, cs:__imp_RasDeAllocateRoute
0x180008832  mov     qword ptr cs:xmmword_18004D440, rax
0x180008839  mov     rax, cs:__imp_RasPortGetProtocolCompression
0x180008840  mov     qword ptr cs:xmmword_18004D4A0+8, rax
0x180008847  mov     rax, cs:__imp_RasGetBuffer
0x18000884e  mov     qword ptr cs:xmmword_18004D4B0, rax
0x180008855  mov     rax, cs:__imp_RasPortSetProtocolCompression
0x18000885c  mov     qword ptr cs:xmmword_18004D4B0+8, rax
0x180008863  call    InitializePPP
0x180008868  mov     ebx, eax
0x18000886a  test    eax, eax
0x18000886c  jz      short loc_180008878
0x18000886e  call    PPPCleanUp
0x180008873  jmp     loc_180008968
0x180008878  test    cs:byte_18004DF34, 1
0x18000887f  jz      short loc_18000889B
0x180008881  lea     r8, aPppInitialized; "PPP Initialized successfully."
0x180008888  lea     rdx, RasPppTraceInfo
0x18000888f  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180008896  call    McTemplateU0z_EventWriteTransfer
0x18000889b  lea     rax, [rsp+880h+hKey]
0x1800088a0  mov     r9d, 20019h; samDesired
0x1800088a6  xor     r8d, r8d; ulOptions
0x1800088a9  mov     [rsp+880h+phkResult], rax; phkResult
0x1800088ae  lea     rdx, aSystemCurrentc_3; "System\\CurrentControlSet\\Services\\Ra"...
0x1800088b5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800088bc  call    cs:__imp_RegOpenKeyExA
0x1800088c3  nop     dword ptr [rax+rax+00h]
0x1800088c8  mov     ebx, eax
0x1800088ca  test    eax, eax
0x1800088cc  jz      short loc_1800088FF
0x1800088ce  cmp     cs:byte_18004DF33, 0
0x1800088d5  jge     loc_180008968
0x1800088db  xor     ecx, ecx
0x1800088dd  lea     r8, aSystemCurrentc_3; "System\\CurrentControlSet\\Services\\Ra"...
0x1800088e4  mov     word ptr [rsp+880h+var_830], cx
0x1800088e9  lea     rdx, aFailedToOpenRe; "Failed to open registry: %hs"
0x1800088f0  lea     rcx, [rsp+880h+var_830]
0x1800088f5  call    FormatRRASErrorString
0x1800088fa  jmp     loc_1800086E6
0x1800088ff  mov     rcx, [rsp+880h+hKey]; hKey
0x180008904  lea     rax, [rsp+880h+cbData]
0x180008909  mov     [rsp+880h+lpcbData], rax; lpcbData
0x18000890e  lea     r9, [rsp+880h+Type]; lpType
0x180008913  lea     rax, [rsp+880h+Data]
0x180008918  mov     [rsp+880h+cbData], 4
0x180008920  xor     r8d, r8d; lpReserved
0x180008923  mov     [rsp+880h+phkResult], rax; lpData
0x180008928  lea     rdx, aAllowpptpweakc; "AllowPPTPWeakCrypto"
0x18000892f  call    cs:__imp_RegQueryValueExA
0x180008936  nop     dword ptr [rax+rax+00h]
0x18000893b  mov     ebx, eax
0x18000893d  test    eax, eax
0x18000893f  jnz     short loc_180008952
0x180008941  cmp     [rsp+880h+Type], 4
0x180008946  jnz     short loc_180008952
0x180008948  mov     eax, dword ptr [rsp+880h+Data]
0x18000894c  mov     cs:g_dwAllowPPTPWeakCrypto, eax
0x180008952  mov     rcx, [rsp+880h+hKey]; hKey
0x180008957  test    rcx, rcx
0x18000895a  jz      short loc_180008968
0x18000895c  call    cs:__imp_RegCloseKey
0x180008963  nop     dword ptr [rax+rax+00h]
0x180008968  mov     eax, ebx
0x18000896a  mov     rcx, [rbp+780h+var_30]
0x180008971  xor     rcx, rsp; StackCookie
0x180008974  call    __security_check_cookie
0x180008979  add     rsp, 868h
0x180008980  pop     rdi
0x180008981  pop     rsi
0x180008982  pop     rbx
0x180008983  pop     rbp
0x180008984  retn
```
