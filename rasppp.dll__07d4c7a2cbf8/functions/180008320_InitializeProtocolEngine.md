# InitializeProtocolEngine

- ea: `0x180008320`
- end: `0x18000865d`
- name: `InitializeProtocolEngine`
- size: `829`
- prototype: `__int64 __fastcall(__int64, unsigned int, char)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003110`
- `0x180004630`
- `0x180004eac`
- `0x180008320`
- `0x18002a138`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180008613`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180008613`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800085a6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x1800085a6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000863a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000863a`
- `rasman!RasGetPortUserData` at `0x1800084b3`
- `rasman!RasSendProtocolResultToRasman` at `0x180008435`
- `rasman!RasPortSend` at `0x180008443`
- `rasman!RasGetBuffer` at `0x180008531`
- `rasman!RasInitializeNoWait` at `0x18000839c`
- `rasman!RasInitializeNoWait` at `0x18000839c`
- `rasman!RasBundleGetPort` at `0x180008489`
- `rasman!RasPortGetStatisticsEx` at `0x180008451`
- `rasman!RasDeAllocateRoute` at `0x180008515`
- `rasman!RasUpdateDefaultRouteSettings` at `0x1800084eb`
- `rasman!RasCompressionGetInfo` at `0x1800084f9`
- `rasman!RasPortGetBundle` at `0x18000846d`
- `rasman!RasProtocolStarted` at `0x18000840b`
- `rasman!RasCompressionSetInfo` at `0x1800084cf`
- `rasman!RasPortSetFramingEx` at `0x1800084a5`
- `rasman!RasGetFramingCapabilities` at `0x180008497`
- `rasman!RasGetInfo` at `0x18000847b`
- `rasman!RasPortCancelReceive` at `0x1800083fa`
- `rasman!RasPortSetProtocolCompression` at `0x18000853f`
- `rasman!RasFreeBuffer` at `0x180008419`
- `rasman!RasGetConnectInfo` at `0x18000845f`
- `rasman!RasAllocateRoute` at `0x180008507`
- `rasman!RasSetConnectionUserData` at `0x1800084c1`
- `rasman!RasActivateRoute` at `0x1800084dd`
- `rasman!RasPortGetProtocolCompression` at `0x180008523`
- `rasman!RasGetTimeSinceLastActivity` at `0x180008427`

## string_xrefs

- `0x180008598`: `System\CurrentControlSet\Services\Rasman\Parameters`
- `0x1800085c1`: `System\CurrentControlSet\Services\Rasman\Parameters`
- `0x1800085cd`: `Failed to open registry: %hs`

## pseudocode

```c
__int64 __fastcall InitializeProtocolEngine(__int64 a1, unsigned int a2, char a3)
{
  unsigned int v6; // eax
  unsigned int v7; // ebx
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
  LODWORD(qword_18004C970) = a2;
  if ( (a3 & 1) != 0 )
  {
    v6 = RasInitializeNoWait();
    v7 = v6;
    if ( v6 )
    {
      if ( byte_18004CF33 >= 0 )
        return v7;
      LOWORD(v13) = 0;
      FormatRRASErrorString(&v13, L"RasInitializeNoWait failed: %d", v6);
      goto LABEL_7;
    }
  }
  *((_QWORD *)&xmmword_18004C450 + 1) = RasPortCancelReceive;
  *(_QWORD *)&xmmword_18004C420 = RasProtocolStarted;
  *(_QWORD *)&xmmword_18004C460 = RasFreeBuffer;
  *((_QWORD *)&xmmword_18004C420 + 1) = RasGetTimeSinceLastActivity;
  qword_18004C438 = RasSendProtocolResultToRasman;
  *((_QWORD *)&xmmword_18004C460 + 1) = RasPortSend;
  *(_QWORD *)&xmmword_18004C3F0 = RasPortGetStatisticsEx;
  *(_QWORD *)&xmmword_18004C470 = RasGetConnectInfo;
  *(_QWORD *)&xmmword_18004C410 = RasPortGetBundle;
  *((_QWORD *)&xmmword_18004C470 + 1) = RasGetInfo;
  *(_QWORD *)&xmmword_18004C480 = RasBundleGetPort;
  *((_QWORD *)&xmmword_18004C480 + 1) = RasGetFramingCapabilities;
  *(_QWORD *)&xmmword_18004C490 = RasPortSetFramingEx;
  qword_18004C408 = RasGetPortUserData;
  *((_QWORD *)&xmmword_18004C410 + 1) = RasSetConnectionUserData;
  *((_QWORD *)&xmmword_18004C490 + 1) = RasCompressionSetInfo;
  *((_QWORD *)&xmmword_18004C440 + 1) = RasActivateRoute;
  *(_QWORD *)&xmmword_18004C450 = RasUpdateDefaultRouteSettings;
  *(_QWORD *)&xmmword_18004C4A0 = RasCompressionGetInfo;
  *((_QWORD *)&xmmword_18004C3F0 + 1) = RasAllocateRoute;
  *(_QWORD *)&xmmword_18004C440 = RasDeAllocateRoute;
  *((_QWORD *)&xmmword_18004C4A0 + 1) = RasPortGetProtocolCompression;
  *(_QWORD *)&xmmword_18004C4B0 = RasGetBuffer;
  *((_QWORD *)&xmmword_18004C4B0 + 1) = RasPortSetProtocolCompression;
  v7 = InitializePPP(a1);
  if ( v7 )
  {
    PPPCleanUp();
    return v7;
  }
  if ( (byte_18004CF34 & 1) != 0 )
    McTemplateU0z_EventWriteTransfer(
      &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      RasPppTraceInfo,
      L"PPP Initialized successfully.");
  v7 = RegOpenKeyExA(HKEY_LOCAL_MACHINE, "System\\CurrentControlSet\\Services\\Rasman\\Parameters", 0, 0x20019u, &hKey);
  if ( v7 )
  {
    if ( byte_18004CF33 >= 0 )
      return v7;
    LOWORD(v13) = 0;
    FormatRRASErrorString(
      &v13,
      L"Failed to open registry: %hs",
      "System\\CurrentControlSet\\Services\\Rasman\\Parameters");
LABEL_7:
    if ( byte_18004CF33 < 0 )
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
0x180008320  push    rbp
0x180008322  push    rbx
0x180008323  push    rsi
0x180008324  push    rdi
0x180008325  lea     rbp, [rsp-768h]
0x18000832d  sub     rsp, 868h
0x180008334  mov     rax, cs:__security_cookie
0x18000833b  xor     rax, rsp
0x18000833e  mov     [rbp+780h+var_30], rax
0x180008345  mov     edi, r8d
0x180008348  mov     dword ptr [rsp+880h+Data], 0
0x180008350  mov     ebx, edx
0x180008352  mov     [rsp+880h+cbData], 0
0x18000835a  mov     rsi, rcx
0x18000835d  mov     [rsp+880h+hKey], 0
0x180008366  xor     eax, eax
0x180008368  mov     [rsp+880h+Type], 0
0x180008370  xor     edx, edx; Val
0x180008372  mov     [rsp+880h+var_830], eax
0x180008376  mov     r8d, 7FCh; Size
0x18000837c  lea     rcx, [rsp+880h+var_82C]; void *
0x180008381  call    memset_0
0x180008386  mov     eax, 3Dh ; '='
0x18000838b  cmp     ebx, eax
0x18000838d  cmova   ebx, eax
0x180008390  mov     dword ptr cs:qword_18004C970, ebx
0x180008396  test    dil, 1
0x18000839a  jz      short loc_1800083FA
0x18000839c  call    cs:__imp_RasInitializeNoWait
0x1800083a2  mov     ebx, eax
0x1800083a4  test    eax, eax
0x1800083a6  jz      short loc_1800083FA
0x1800083a8  cmp     cs:byte_18004CF33, 0
0x1800083af  jge     loc_180008640
0x1800083b5  xor     ecx, ecx
0x1800083b7  lea     rdx, aRasinitializen; "RasInitializeNoWait failed: %d"
0x1800083be  mov     word ptr [rsp+880h+var_830], cx
0x1800083c3  mov     r8d, eax
0x1800083c6  lea     rcx, [rsp+880h+var_830]
0x1800083cb  call    FormatRRASErrorString
0x1800083d0  cmp     cs:byte_18004CF33, 0
0x1800083d7  jge     loc_180008640
0x1800083dd  lea     r8, [rsp+880h+var_830]
0x1800083e2  lea     rdx, RasPppTraceError
0x1800083e9  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800083f0  call    McTemplateU0z_EventWriteTransfer
0x1800083f5  jmp     loc_180008640
0x1800083fa  mov     rax, cs:__imp_RasPortCancelReceive
0x180008401  mov     rcx, rsi
0x180008404  mov     qword ptr cs:xmmword_18004C450+8, rax
0x18000840b  mov     rax, cs:__imp_RasProtocolStarted
0x180008412  mov     qword ptr cs:xmmword_18004C420, rax
0x180008419  mov     rax, cs:__imp_RasFreeBuffer
0x180008420  mov     qword ptr cs:xmmword_18004C460, rax
0x180008427  mov     rax, cs:__imp_RasGetTimeSinceLastActivity
0x18000842e  mov     qword ptr cs:xmmword_18004C420+8, rax
0x180008435  mov     rax, cs:__imp_RasSendProtocolResultToRasman
0x18000843c  mov     cs:qword_18004C438, rax
0x180008443  mov     rax, cs:__imp_RasPortSend
0x18000844a  mov     qword ptr cs:xmmword_18004C460+8, rax
0x180008451  mov     rax, cs:__imp_RasPortGetStatisticsEx
0x180008458  mov     qword ptr cs:xmmword_18004C3F0, rax
0x18000845f  mov     rax, cs:__imp_RasGetConnectInfo
0x180008466  mov     qword ptr cs:xmmword_18004C470, rax
0x18000846d  mov     rax, cs:__imp_RasPortGetBundle
0x180008474  mov     qword ptr cs:xmmword_18004C410, rax
0x18000847b  mov     rax, cs:__imp_RasGetInfo
0x180008482  mov     qword ptr cs:xmmword_18004C470+8, rax
0x180008489  mov     rax, cs:__imp_RasBundleGetPort
0x180008490  mov     qword ptr cs:xmmword_18004C480, rax
0x180008497  mov     rax, cs:__imp_RasGetFramingCapabilities
0x18000849e  mov     qword ptr cs:xmmword_18004C480+8, rax
0x1800084a5  mov     rax, cs:__imp_RasPortSetFramingEx
0x1800084ac  mov     qword ptr cs:xmmword_18004C490, rax
0x1800084b3  mov     rax, cs:__imp_RasGetPortUserData
0x1800084ba  mov     cs:qword_18004C408, rax
0x1800084c1  mov     rax, cs:__imp_RasSetConnectionUserData
0x1800084c8  mov     qword ptr cs:xmmword_18004C410+8, rax
0x1800084cf  mov     rax, cs:__imp_RasCompressionSetInfo
0x1800084d6  mov     qword ptr cs:xmmword_18004C490+8, rax
0x1800084dd  mov     rax, cs:__imp_RasActivateRoute
0x1800084e4  mov     qword ptr cs:xmmword_18004C440+8, rax
0x1800084eb  mov     rax, cs:__imp_RasUpdateDefaultRouteSettings
0x1800084f2  mov     qword ptr cs:xmmword_18004C450, rax
0x1800084f9  mov     rax, cs:__imp_RasCompressionGetInfo
0x180008500  mov     qword ptr cs:xmmword_18004C4A0, rax
0x180008507  mov     rax, cs:__imp_RasAllocateRoute
0x18000850e  mov     qword ptr cs:xmmword_18004C3F0+8, rax
0x180008515  mov     rax, cs:__imp_RasDeAllocateRoute
0x18000851c  mov     qword ptr cs:xmmword_18004C440, rax
0x180008523  mov     rax, cs:__imp_RasPortGetProtocolCompression
0x18000852a  mov     qword ptr cs:xmmword_18004C4A0+8, rax
0x180008531  mov     rax, cs:__imp_RasGetBuffer
0x180008538  mov     qword ptr cs:xmmword_18004C4B0, rax
0x18000853f  mov     rax, cs:__imp_RasPortSetProtocolCompression
0x180008546  mov     qword ptr cs:xmmword_18004C4B0+8, rax
0x18000854d  call    InitializePPP
0x180008552  mov     ebx, eax
0x180008554  test    eax, eax
0x180008556  jz      short loc_180008562
0x180008558  call    PPPCleanUp
0x18000855d  jmp     loc_180008640
0x180008562  test    cs:byte_18004CF34, 1
0x180008569  jz      short loc_180008585
0x18000856b  lea     r8, aPppInitialized; "PPP Initialized successfully."
0x180008572  lea     rdx, RasPppTraceInfo
0x180008579  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180008580  call    McTemplateU0z_EventWriteTransfer
0x180008585  lea     rax, [rsp+880h+hKey]
0x18000858a  mov     r9d, 20019h; samDesired
0x180008590  xor     r8d, r8d; ulOptions
0x180008593  mov     [rsp+880h+phkResult], rax; phkResult
0x180008598  lea     rdx, aSystemCurrentc_3; "System\\CurrentControlSet\\Services\\Ra"...
0x18000859f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800085a6  call    cs:__imp_RegOpenKeyExA
0x1800085ac  mov     ebx, eax
0x1800085ae  test    eax, eax
0x1800085b0  jz      short loc_1800085E3
0x1800085b2  cmp     cs:byte_18004CF33, 0
0x1800085b9  jge     loc_180008640
0x1800085bf  xor     ecx, ecx
0x1800085c1  lea     r8, aSystemCurrentc_3; "System\\CurrentControlSet\\Services\\Ra"...
0x1800085c8  mov     word ptr [rsp+880h+var_830], cx
0x1800085cd  lea     rdx, aFailedToOpenRe; "Failed to open registry: %hs"
0x1800085d4  lea     rcx, [rsp+880h+var_830]
0x1800085d9  call    FormatRRASErrorString
0x1800085de  jmp     loc_1800083D0
0x1800085e3  mov     rcx, [rsp+880h+hKey]; hKey
0x1800085e8  lea     rax, [rsp+880h+cbData]
0x1800085ed  mov     [rsp+880h+lpcbData], rax; lpcbData
0x1800085f2  lea     r9, [rsp+880h+Type]; lpType
0x1800085f7  lea     rax, [rsp+880h+Data]
0x1800085fc  mov     [rsp+880h+cbData], 4
0x180008604  xor     r8d, r8d; lpReserved
0x180008607  mov     [rsp+880h+phkResult], rax; lpData
0x18000860c  lea     rdx, aAllowpptpweakc; "AllowPPTPWeakCrypto"
0x180008613  call    cs:__imp_RegQueryValueExA
0x180008619  mov     ebx, eax
0x18000861b  test    eax, eax
0x18000861d  jnz     short loc_180008630
0x18000861f  cmp     [rsp+880h+Type], 4
0x180008624  jnz     short loc_180008630
0x180008626  mov     eax, dword ptr [rsp+880h+Data]
0x18000862a  mov     cs:g_dwAllowPPTPWeakCrypto, eax
0x180008630  mov     rcx, [rsp+880h+hKey]; hKey
0x180008635  test    rcx, rcx
0x180008638  jz      short loc_180008640
0x18000863a  call    cs:__imp_RegCloseKey
0x180008640  mov     eax, ebx
0x180008642  mov     rcx, [rbp+780h+var_30]
0x180008649  xor     rcx, rsp; StackCookie
0x18000864c  call    __security_check_cookie
0x180008651  add     rsp, 868h
0x180008658  pop     rdi
0x180008659  pop     rsi
0x18000865a  pop     rbx
0x18000865b  pop     rbp
0x18000865c  retn
```
