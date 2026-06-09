# NetworkingTriageScenario::EnumToString(NetworkingTriageScenario::EventSources)

- ea: `0x18001b9fc`
- end: `0x18001bbbf`
- name: `?EnumToString@NetworkingTriageScenario@@YAPEBDW4EventSources@1@@Z`
- size: `451`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001b3f4`
- `0x18001b544`
- `0x1800372b4`

## callees

- `0x18001b9fc`
- `0x180043f48`

## string_xrefs

- `0x18001bb8f`: `SharedAccess`

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
0x18001b9fc  sub     rsp, 28h
0x18001ba00  cmp     ecx, 0Dh
0x18001ba03  jg      loc_18001BB01
0x18001ba09  jz      loc_18001BAF5
0x18001ba0f  cmp     ecx, 6
0x18001ba12  jg      short loc_18001BA8B
0x18001ba14  jz      short loc_18001BA7F
0x18001ba16  test    ecx, ecx
0x18001ba18  jz      short loc_18001BA73
0x18001ba1a  sub     ecx, 1
0x18001ba1d  jz      short loc_18001BA67
0x18001ba1f  sub     ecx, 1
0x18001ba22  jz      short loc_18001BA5B
0x18001ba24  sub     ecx, 1
0x18001ba27  jz      short loc_18001BA4F
0x18001ba29  sub     ecx, 1
0x18001ba2c  jz      short loc_18001BA43
0x18001ba2e  cmp     ecx, 1
0x18001ba31  jnz     loc_18001BB81
0x18001ba37  lea     rax, aWwan_0; "Wwan"
0x18001ba3e  jmp     loc_18001BBBA
0x18001ba43  lea     rax, aWindowsconnect; "WindowsConnectionManager"
0x18001ba4a  jmp     loc_18001BBBA
0x18001ba4f  lea     rax, aTcpip; "TcpIp"
0x18001ba56  jmp     loc_18001BBBA
0x18001ba5b  lea     rax, aNcsi; "NCSI"
0x18001ba62  jmp     loc_18001BBBA
0x18001ba67  lea     rax, aDusm; "DUSM"
0x18001ba6e  jmp     loc_18001BBBA
0x18001ba73  lea     rax, aNetworklistman; "NetworkListManager"
0x18001ba7a  jmp     loc_18001BBBA
0x18001ba7f  lea     rax, aPni; "PNI"
0x18001ba86  jmp     loc_18001BBBA
0x18001ba8b  sub     ecx, 7
0x18001ba8e  jz      short loc_18001BAE9
0x18001ba90  sub     ecx, 1
0x18001ba93  jz      short loc_18001BADD
0x18001ba95  sub     ecx, 1
0x18001ba98  jz      short loc_18001BAD1
0x18001ba9a  sub     ecx, 1
0x18001ba9d  jz      short loc_18001BAC5
0x18001ba9f  sub     ecx, 1
0x18001baa2  jz      short loc_18001BAB9
0x18001baa4  cmp     ecx, 1
0x18001baa7  jnz     loc_18001BB81
0x18001baad  lea     rax, aWifiwinrtapis; "WiFiWinRTAPIs"
0x18001bab4  jmp     loc_18001BBBA
0x18001bab9  lea     rax, aNetworksetting; "NetworkSettingHandlers"
0x18001bac0  jmp     loc_18001BBBA
0x18001bac5  lea     rax, aWifinetworkman; "WiFiNetworkManager"
0x18001bacc  jmp     loc_18001BBBA
0x18001bad1  lea     rax, aNetworkicon; "NetworkIcon"
0x18001bad8  jmp     loc_18001BBBA
0x18001badd  lea     rax, aNetworkux; "NetworkUX"
0x18001bae4  jmp     loc_18001BBBA
0x18001bae9  lea     rax, aNetworkstatus; "NetworkStatus"
0x18001baf0  jmp     loc_18001BBBA
0x18001baf5  lea     rax, aWlanmediamanag; "WlanMediaManager"
0x18001bafc  jmp     loc_18001BBBA
0x18001bb01  cmp     ecx, 14h
0x18001bb04  jg      short loc_18001BB68
0x18001bb06  jz      short loc_18001BB5F
0x18001bb08  sub     ecx, 0Eh
0x18001bb0b  jz      short loc_18001BB56
0x18001bb0d  sub     ecx, 1
0x18001bb10  jz      short loc_18001BB4D
0x18001bb12  sub     ecx, 1
0x18001bb15  jz      short loc_18001BB44
0x18001bb17  sub     ecx, 1
0x18001bb1a  jz      short loc_18001BB3B
0x18001bb1c  sub     ecx, 1
0x18001bb1f  jz      short loc_18001BB32
0x18001bb21  cmp     ecx, 1
0x18001bb24  jnz     short loc_18001BB81
0x18001bb26  lea     rax, aPeap; "Peap"
0x18001bb2d  jmp     loc_18001BBBA
0x18001bb32  lea     rax, aEaphost; "EapHost"
0x18001bb39  jmp     short loc_18001BBBA
0x18001bb3b  lea     rax, aEaptls; "EapTls"
0x18001bb42  jmp     short loc_18001BBBA
0x18001bb44  lea     rax, aFirewall; "Firewall"
0x18001bb4b  jmp     short loc_18001BBBA
0x18001bb4d  lea     rax, aWifi; "WiFi"
0x18001bb54  jmp     short loc_18001BBBA
0x18001bb56  lea     rax, aEaprequesthand; "EapRequestHandler"
0x18001bb5d  jmp     short loc_18001BBBA
0x18001bb5f  lea     rax, aEthernetmediam; "EthernetMediaManager"
0x18001bb66  jmp     short loc_18001BBBA
0x18001bb68  sub     ecx, 15h
0x18001bb6b  jz      short loc_18001BBB3
0x18001bb6d  sub     ecx, 1
0x18001bb70  jz      short loc_18001BBAA
0x18001bb72  sub     ecx, 2
0x18001bb75  jz      short loc_18001BBA1
0x18001bb77  sub     ecx, 1
0x18001bb7a  jz      short loc_18001BB98
0x18001bb7c  cmp     ecx, 1
0x18001bb7f  jz      short loc_18001BB8F
0x18001bb81  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001bb86  lea     rax, aUnknown; "Unknown"
0x18001bb8d  jmp     short loc_18001BBBA
0x18001bb8f  lea     rax, aSharedaccess; "SharedAccess"
0x18001bb96  jmp     short loc_18001BBBA
0x18001bb98  lea     rax, aTetheringsvc; "TetheringSvc"
0x18001bb9f  jmp     short loc_18001BBBA
0x18001bba1  lea     rax, aEsimpolicymana; "EsimPolicyManager"
0x18001bba8  jmp     short loc_18001BBBA
0x18001bbaa  lea     rax, aSettingsapp; "SettingsApp"
0x18001bbb1  jmp     short loc_18001BBBA
0x18001bbb3  lea     rax, aDot3; "Dot3"
0x18001bbba  add     rsp, 28h
0x18001bbbe  retn
```
