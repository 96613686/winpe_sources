# NetworkingTriageScenario::EnumToString(NetworkingTriageScenario::EventSources)

- ea: `0x180025a58`
- end: `0x180025c1c`
- name: `?EnumToString@NetworkingTriageScenario@@YAPEBDW4EventSources@1@@Z`
- size: `452`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180024d28`
- `0x180024efc`

## callees

- `0x180025a58`
- `0x18003362c`

## string_xrefs

- `0x180025beb`: `SharedAccess`

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
0x180025a58  sub     rsp, 28h
0x180025a5c  cmp     ecx, 0Dh
0x180025a5f  jg      loc_180025B5D
0x180025a65  jz      loc_180025B51
0x180025a6b  cmp     ecx, 6
0x180025a6e  jg      short loc_180025AE7
0x180025a70  jz      short loc_180025ADB
0x180025a72  test    ecx, ecx
0x180025a74  jz      short loc_180025ACF
0x180025a76  sub     ecx, 1
0x180025a79  jz      short loc_180025AC3
0x180025a7b  sub     ecx, 1
0x180025a7e  jz      short loc_180025AB7
0x180025a80  sub     ecx, 1
0x180025a83  jz      short loc_180025AAB
0x180025a85  sub     ecx, 1
0x180025a88  jz      short loc_180025A9F
0x180025a8a  cmp     ecx, 1
0x180025a8d  jnz     loc_180025BDD
0x180025a93  lea     rax, aWwan; "Wwan"
0x180025a9a  jmp     loc_180025C16
0x180025a9f  lea     rax, aWindowsconnect; "WindowsConnectionManager"
0x180025aa6  jmp     loc_180025C16
0x180025aab  lea     rax, aTcpip; "TcpIp"
0x180025ab2  jmp     loc_180025C16
0x180025ab7  lea     rax, aNcsi; "NCSI"
0x180025abe  jmp     loc_180025C16
0x180025ac3  lea     rax, aDusm; "DUSM"
0x180025aca  jmp     loc_180025C16
0x180025acf  lea     rax, aNetworklistman; "NetworkListManager"
0x180025ad6  jmp     loc_180025C16
0x180025adb  lea     rax, aPni; "PNI"
0x180025ae2  jmp     loc_180025C16
0x180025ae7  sub     ecx, 7
0x180025aea  jz      short loc_180025B45
0x180025aec  sub     ecx, 1
0x180025aef  jz      short loc_180025B39
0x180025af1  sub     ecx, 1
0x180025af4  jz      short loc_180025B2D
0x180025af6  sub     ecx, 1
0x180025af9  jz      short loc_180025B21
0x180025afb  sub     ecx, 1
0x180025afe  jz      short loc_180025B15
0x180025b00  cmp     ecx, 1
0x180025b03  jnz     loc_180025BDD
0x180025b09  lea     rax, aWifiwinrtapis; "WiFiWinRTAPIs"
0x180025b10  jmp     loc_180025C16
0x180025b15  lea     rax, aNetworksetting; "NetworkSettingHandlers"
0x180025b1c  jmp     loc_180025C16
0x180025b21  lea     rax, aWifinetworkman; "WiFiNetworkManager"
0x180025b28  jmp     loc_180025C16
0x180025b2d  lea     rax, aNetworkicon; "NetworkIcon"
0x180025b34  jmp     loc_180025C16
0x180025b39  lea     rax, aNetworkux; "NetworkUX"
0x180025b40  jmp     loc_180025C16
0x180025b45  lea     rax, aNetworkstatus; "NetworkStatus"
0x180025b4c  jmp     loc_180025C16
0x180025b51  lea     rax, aWlanmediamanag; "WlanMediaManager"
0x180025b58  jmp     loc_180025C16
0x180025b5d  cmp     ecx, 14h
0x180025b60  jg      short loc_180025BC4
0x180025b62  jz      short loc_180025BBB
0x180025b64  sub     ecx, 0Eh
0x180025b67  jz      short loc_180025BB2
0x180025b69  sub     ecx, 1
0x180025b6c  jz      short loc_180025BA9
0x180025b6e  sub     ecx, 1
0x180025b71  jz      short loc_180025BA0
0x180025b73  sub     ecx, 1
0x180025b76  jz      short loc_180025B97
0x180025b78  sub     ecx, 1
0x180025b7b  jz      short loc_180025B8E
0x180025b7d  cmp     ecx, 1
0x180025b80  jnz     short loc_180025BDD
0x180025b82  lea     rax, aPeap; "Peap"
0x180025b89  jmp     loc_180025C16
0x180025b8e  lea     rax, aEaphost; "EapHost"
0x180025b95  jmp     short loc_180025C16
0x180025b97  lea     rax, aEaptls; "EapTls"
0x180025b9e  jmp     short loc_180025C16
0x180025ba0  lea     rax, aFirewall; "Firewall"
0x180025ba7  jmp     short loc_180025C16
0x180025ba9  lea     rax, aWifi; "WiFi"
0x180025bb0  jmp     short loc_180025C16
0x180025bb2  lea     rax, aEaprequesthand; "EapRequestHandler"
0x180025bb9  jmp     short loc_180025C16
0x180025bbb  lea     rax, aEthernetmediam; "EthernetMediaManager"
0x180025bc2  jmp     short loc_180025C16
0x180025bc4  sub     ecx, 15h
0x180025bc7  jz      short loc_180025C0F
0x180025bc9  sub     ecx, 1
0x180025bcc  jz      short loc_180025C06
0x180025bce  sub     ecx, 2
0x180025bd1  jz      short loc_180025BFD
0x180025bd3  sub     ecx, 1
0x180025bd6  jz      short loc_180025BF4
0x180025bd8  cmp     ecx, 1
0x180025bdb  jz      short loc_180025BEB
0x180025bdd  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180025be2  lea     rax, aUnknown; "Unknown"
0x180025be9  jmp     short loc_180025C16
0x180025beb  lea     rax, aSharedaccess; "SharedAccess"
0x180025bf2  jmp     short loc_180025C16
0x180025bf4  lea     rax, aTetheringsvc; "TetheringSvc"
0x180025bfb  jmp     short loc_180025C16
0x180025bfd  lea     rax, aEsimpolicymana; "EsimPolicyManager"
0x180025c04  jmp     short loc_180025C16
0x180025c06  lea     rax, aSettingsapp; "SettingsApp"
0x180025c0d  jmp     short loc_180025C16
0x180025c0f  lea     rax, aDot3; "Dot3"
0x180025c16  add     rsp, 28h
0x180025c1a  retn
```
