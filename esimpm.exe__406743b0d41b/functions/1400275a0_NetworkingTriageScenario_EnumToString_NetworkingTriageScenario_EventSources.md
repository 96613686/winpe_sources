# NetworkingTriageScenario::EnumToString(NetworkingTriageScenario::EventSources)

- ea: `0x1400275a0`
- end: `0x140027763`
- name: `?EnumToString@NetworkingTriageScenario@@YAPEBDW4EventSources@1@@Z`
- size: `451`
- prototype: `const char *__fastcall(int)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14002776c`
- `0x140027a4c`
- `0x140027d1c`

## callees

- `0x1400275a0`
- `0x1400350e4`

## string_xrefs

- `0x140027733`: `SharedAccess`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x1400275a0  sub     rsp, 28h
0x1400275a4  cmp     ecx, 0Dh
0x1400275a7  jg      loc_1400276A5
0x1400275ad  jz      loc_140027699
0x1400275b3  cmp     ecx, 6
0x1400275b6  jg      short loc_14002762F
0x1400275b8  jz      short loc_140027623
0x1400275ba  test    ecx, ecx
0x1400275bc  jz      short loc_140027617
0x1400275be  sub     ecx, 1
0x1400275c1  jz      short loc_14002760B
0x1400275c3  sub     ecx, 1
0x1400275c6  jz      short loc_1400275FF
0x1400275c8  sub     ecx, 1
0x1400275cb  jz      short loc_1400275F3
0x1400275cd  sub     ecx, 1
0x1400275d0  jz      short loc_1400275E7
0x1400275d2  cmp     ecx, 1
0x1400275d5  jnz     loc_140027725
0x1400275db  lea     rax, aWwan; "Wwan"
0x1400275e2  jmp     loc_14002775E
0x1400275e7  lea     rax, aWindowsconnect; "WindowsConnectionManager"
0x1400275ee  jmp     loc_14002775E
0x1400275f3  lea     rax, aTcpip; "TcpIp"
0x1400275fa  jmp     loc_14002775E
0x1400275ff  lea     rax, aNcsi; "NCSI"
0x140027606  jmp     loc_14002775E
0x14002760b  lea     rax, aDusm; "DUSM"
0x140027612  jmp     loc_14002775E
0x140027617  lea     rax, aNetworklistman; "NetworkListManager"
0x14002761e  jmp     loc_14002775E
0x140027623  lea     rax, aPni; "PNI"
0x14002762a  jmp     loc_14002775E
0x14002762f  sub     ecx, 7
0x140027632  jz      short loc_14002768D
0x140027634  sub     ecx, 1
0x140027637  jz      short loc_140027681
0x140027639  sub     ecx, 1
0x14002763c  jz      short loc_140027675
0x14002763e  sub     ecx, 1
0x140027641  jz      short loc_140027669
0x140027643  sub     ecx, 1
0x140027646  jz      short loc_14002765D
0x140027648  cmp     ecx, 1
0x14002764b  jnz     loc_140027725
0x140027651  lea     rax, aWifiwinrtapis; "WiFiWinRTAPIs"
0x140027658  jmp     loc_14002775E
0x14002765d  lea     rax, aNetworksetting; "NetworkSettingHandlers"
0x140027664  jmp     loc_14002775E
0x140027669  lea     rax, aWifinetworkman; "WiFiNetworkManager"
0x140027670  jmp     loc_14002775E
0x140027675  lea     rax, aNetworkicon; "NetworkIcon"
0x14002767c  jmp     loc_14002775E
0x140027681  lea     rax, aNetworkux; "NetworkUX"
0x140027688  jmp     loc_14002775E
0x14002768d  lea     rax, aNetworkstatus; "NetworkStatus"
0x140027694  jmp     loc_14002775E
0x140027699  lea     rax, aWlanmediamanag; "WlanMediaManager"
0x1400276a0  jmp     loc_14002775E
0x1400276a5  cmp     ecx, 14h
0x1400276a8  jg      short loc_14002770C
0x1400276aa  jz      short loc_140027703
0x1400276ac  sub     ecx, 0Eh
0x1400276af  jz      short loc_1400276FA
0x1400276b1  sub     ecx, 1
0x1400276b4  jz      short loc_1400276F1
0x1400276b6  sub     ecx, 1
0x1400276b9  jz      short loc_1400276E8
0x1400276bb  sub     ecx, 1
0x1400276be  jz      short loc_1400276DF
0x1400276c0  sub     ecx, 1
0x1400276c3  jz      short loc_1400276D6
0x1400276c5  cmp     ecx, 1
0x1400276c8  jnz     short loc_140027725
0x1400276ca  lea     rax, aPeap; "Peap"
0x1400276d1  jmp     loc_14002775E
0x1400276d6  lea     rax, aEaphost; "EapHost"
0x1400276dd  jmp     short loc_14002775E
0x1400276df  lea     rax, aEaptls; "EapTls"
0x1400276e6  jmp     short loc_14002775E
0x1400276e8  lea     rax, aFirewall; "Firewall"
0x1400276ef  jmp     short loc_14002775E
0x1400276f1  lea     rax, aWifi; "WiFi"
0x1400276f8  jmp     short loc_14002775E
0x1400276fa  lea     rax, aEaprequesthand; "EapRequestHandler"
0x140027701  jmp     short loc_14002775E
0x140027703  lea     rax, aEthernetmediam; "EthernetMediaManager"
0x14002770a  jmp     short loc_14002775E
0x14002770c  sub     ecx, 15h
0x14002770f  jz      short loc_140027757
0x140027711  sub     ecx, 1
0x140027714  jz      short loc_14002774E
0x140027716  sub     ecx, 2
0x140027719  jz      short loc_140027745
0x14002771b  sub     ecx, 1
0x14002771e  jz      short loc_14002773C
0x140027720  cmp     ecx, 1
0x140027723  jz      short loc_140027733
0x140027725  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x14002772a  lea     rax, aUnknown; "Unknown"
0x140027731  jmp     short loc_14002775E
0x140027733  lea     rax, aSharedaccess; "SharedAccess"
0x14002773a  jmp     short loc_14002775E
0x14002773c  lea     rax, aTetheringsvc; "TetheringSvc"
0x140027743  jmp     short loc_14002775E
0x140027745  lea     rax, aEsimpolicymana; "EsimPolicyManager"
0x14002774c  jmp     short loc_14002775E
0x14002774e  lea     rax, aSettingsapp; "SettingsApp"
0x140027755  jmp     short loc_14002775E
0x140027757  lea     rax, aDot3; "Dot3"
0x14002775e  add     rsp, 28h
0x140027762  retn
```
