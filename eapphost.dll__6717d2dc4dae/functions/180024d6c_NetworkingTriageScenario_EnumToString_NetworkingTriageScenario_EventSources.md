# NetworkingTriageScenario::EnumToString(NetworkingTriageScenario::EventSources)

- ea: `0x180024d6c`
- end: `0x180024f2f`
- name: `?EnumToString@NetworkingTriageScenario@@YAPEBDW4EventSources@1@@Z`
- size: `451`
- prototype: `const char *__fastcall(int)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180024054`
- `0x180024224`

## callees

- `0x180024d6c`
- `0x180032388`

## string_xrefs

- `0x180024eff`: `SharedAccess`

## pseudocode

```c
const char *__fastcall NetworkingTriageScenario::EnumToString(int a1)
{
  int v1; // ecx
  int v2; // ecx
  int v3; // ecx
  int v4; // ecx
  int v6; // ecx
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  int v16; // ecx
  int v17; // ecx
  int v18; // ecx
  int v19; // ecx

  if ( a1 <= 13 )
  {
    if ( a1 == 13 )
      return "WlanMediaManager";
    if ( a1 > 6 )
    {
      v6 = a1 - 7;
      if ( !v6 )
        return "NetworkStatus";
      v7 = v6 - 1;
      if ( !v7 )
        return "NetworkUX";
      v8 = v7 - 1;
      if ( !v8 )
        return "NetworkIcon";
      v9 = v8 - 1;
      if ( !v9 )
        return "WiFiNetworkManager";
      v10 = v9 - 1;
      if ( !v10 )
        return "NetworkSettingHandlers";
      if ( v10 == 1 )
        return "WiFiWinRTAPIs";
    }
    else
    {
      if ( a1 == 6 )
        return "PNI";
      if ( !a1 )
        return "NetworkListManager";
      v1 = a1 - 1;
      if ( !v1 )
        return "DUSM";
      v2 = v1 - 1;
      if ( !v2 )
        return "NCSI";
      v3 = v2 - 1;
      if ( !v3 )
        return "TcpIp";
      v4 = v3 - 1;
      if ( !v4 )
        return "WindowsConnectionManager";
      if ( v4 == 1 )
        return "Wwan";
    }
    goto LABEL_51;
  }
  if ( a1 <= 20 )
  {
    if ( a1 == 20 )
      return "EthernetMediaManager";
    v11 = a1 - 14;
    if ( !v11 )
      return "EapRequestHandler";
    v12 = v11 - 1;
    if ( !v12 )
      return "WiFi";
    v13 = v12 - 1;
    if ( !v13 )
      return "Firewall";
    v14 = v13 - 1;
    if ( !v14 )
      return "EapTls";
    v15 = v14 - 1;
    if ( !v15 )
      return "EapHost";
    if ( v15 == 1 )
      return "Peap";
    goto LABEL_51;
  }
  v16 = a1 - 21;
  if ( !v16 )
    return "Dot3";
  v17 = v16 - 1;
  if ( !v17 )
    return "SettingsApp";
  v18 = v17 - 2;
  if ( !v18 )
    return "EsimPolicyManager";
  v19 = v18 - 1;
  if ( !v19 )
    return "TetheringSvc";
  if ( v19 != 1 )
  {
LABEL_51:
    MicrosoftTelemetryAssertTriggeredNoArgs();
    return "Unknown";
  }
  return "SharedAccess";
}

```

## disassembly

```asm
0x180024d6c  sub     rsp, 28h
0x180024d70  cmp     ecx, 0Dh
0x180024d73  jg      loc_180024E71
0x180024d79  jz      loc_180024E65
0x180024d7f  cmp     ecx, 6
0x180024d82  jg      short loc_180024DFB
0x180024d84  jz      short loc_180024DEF
0x180024d86  test    ecx, ecx
0x180024d88  jz      short loc_180024DE3
0x180024d8a  sub     ecx, 1
0x180024d8d  jz      short loc_180024DD7
0x180024d8f  sub     ecx, 1
0x180024d92  jz      short loc_180024DCB
0x180024d94  sub     ecx, 1
0x180024d97  jz      short loc_180024DBF
0x180024d99  sub     ecx, 1
0x180024d9c  jz      short loc_180024DB3
0x180024d9e  cmp     ecx, 1
0x180024da1  jnz     loc_180024EF1
0x180024da7  lea     rax, aWwan; "Wwan"
0x180024dae  jmp     loc_180024F2A
0x180024db3  lea     rax, aWindowsconnect; "WindowsConnectionManager"
0x180024dba  jmp     loc_180024F2A
0x180024dbf  lea     rax, aTcpip; "TcpIp"
0x180024dc6  jmp     loc_180024F2A
0x180024dcb  lea     rax, aNcsi; "NCSI"
0x180024dd2  jmp     loc_180024F2A
0x180024dd7  lea     rax, aDusm; "DUSM"
0x180024dde  jmp     loc_180024F2A
0x180024de3  lea     rax, aNetworklistman; "NetworkListManager"
0x180024dea  jmp     loc_180024F2A
0x180024def  lea     rax, aPni; "PNI"
0x180024df6  jmp     loc_180024F2A
0x180024dfb  sub     ecx, 7
0x180024dfe  jz      short loc_180024E59
0x180024e00  sub     ecx, 1
0x180024e03  jz      short loc_180024E4D
0x180024e05  sub     ecx, 1
0x180024e08  jz      short loc_180024E41
0x180024e0a  sub     ecx, 1
0x180024e0d  jz      short loc_180024E35
0x180024e0f  sub     ecx, 1
0x180024e12  jz      short loc_180024E29
0x180024e14  cmp     ecx, 1
0x180024e17  jnz     loc_180024EF1
0x180024e1d  lea     rax, aWifiwinrtapis; "WiFiWinRTAPIs"
0x180024e24  jmp     loc_180024F2A
0x180024e29  lea     rax, aNetworksetting; "NetworkSettingHandlers"
0x180024e30  jmp     loc_180024F2A
0x180024e35  lea     rax, aWifinetworkman; "WiFiNetworkManager"
0x180024e3c  jmp     loc_180024F2A
0x180024e41  lea     rax, aNetworkicon; "NetworkIcon"
0x180024e48  jmp     loc_180024F2A
0x180024e4d  lea     rax, aNetworkux; "NetworkUX"
0x180024e54  jmp     loc_180024F2A
0x180024e59  lea     rax, aNetworkstatus; "NetworkStatus"
0x180024e60  jmp     loc_180024F2A
0x180024e65  lea     rax, aWlanmediamanag; "WlanMediaManager"
0x180024e6c  jmp     loc_180024F2A
0x180024e71  cmp     ecx, 14h
0x180024e74  jg      short loc_180024ED8
0x180024e76  jz      short loc_180024ECF
0x180024e78  sub     ecx, 0Eh
0x180024e7b  jz      short loc_180024EC6
0x180024e7d  sub     ecx, 1
0x180024e80  jz      short loc_180024EBD
0x180024e82  sub     ecx, 1
0x180024e85  jz      short loc_180024EB4
0x180024e87  sub     ecx, 1
0x180024e8a  jz      short loc_180024EAB
0x180024e8c  sub     ecx, 1
0x180024e8f  jz      short loc_180024EA2
0x180024e91  cmp     ecx, 1
0x180024e94  jnz     short loc_180024EF1
0x180024e96  lea     rax, aPeap; "Peap"
0x180024e9d  jmp     loc_180024F2A
0x180024ea2  lea     rax, aEaphost; "EapHost"
0x180024ea9  jmp     short loc_180024F2A
0x180024eab  lea     rax, aEaptls; "EapTls"
0x180024eb2  jmp     short loc_180024F2A
0x180024eb4  lea     rax, aFirewall; "Firewall"
0x180024ebb  jmp     short loc_180024F2A
0x180024ebd  lea     rax, aWifi; "WiFi"
0x180024ec4  jmp     short loc_180024F2A
0x180024ec6  lea     rax, aEaprequesthand; "EapRequestHandler"
0x180024ecd  jmp     short loc_180024F2A
0x180024ecf  lea     rax, aEthernetmediam; "EthernetMediaManager"
0x180024ed6  jmp     short loc_180024F2A
0x180024ed8  sub     ecx, 15h
0x180024edb  jz      short loc_180024F23
0x180024edd  sub     ecx, 1
0x180024ee0  jz      short loc_180024F1A
0x180024ee2  sub     ecx, 2
0x180024ee5  jz      short loc_180024F11
0x180024ee7  sub     ecx, 1
0x180024eea  jz      short loc_180024F08
0x180024eec  cmp     ecx, 1
0x180024eef  jz      short loc_180024EFF
0x180024ef1  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180024ef6  lea     rax, aUnknown; "Unknown"
0x180024efd  jmp     short loc_180024F2A
0x180024eff  lea     rax, aSharedaccess; "SharedAccess"
0x180024f06  jmp     short loc_180024F2A
0x180024f08  lea     rax, aTetheringsvc; "TetheringSvc"
0x180024f0f  jmp     short loc_180024F2A
0x180024f11  lea     rax, aEsimpolicymana; "EsimPolicyManager"
0x180024f18  jmp     short loc_180024F2A
0x180024f1a  lea     rax, aSettingsapp; "SettingsApp"
0x180024f21  jmp     short loc_180024F2A
0x180024f23  lea     rax, aDot3; "Dot3"
0x180024f2a  add     rsp, 28h
0x180024f2e  retn
```
