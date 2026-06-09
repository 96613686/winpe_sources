# InterfaceFieldModified(ulong)

- ea: `0x18002dd00`
- end: `0x18002e001`
- name: `?InterfaceFieldModified@@YAPEBDK@Z`
- size: `769`
- prototype: `const char *__fastcall(unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18003c6d0`
- `0x18003caa0`

## callees

- `0x18002dd00`

## string_xrefs

- `0x18002de12`: `LinkLocalAddressTimeout`
- `0x18002dd99`: `OtherStatefulConfigurationSupported`
- `0x18002dda1`: `ManagedAddressConfigurationSupported`
- `0x18002de35`: `PathMtuDiscoveryTimeout`
- `0x18002de25`: `LinkLocalAddressBehavior`
- `0x18002debe`: `LinkLocalAddress`
- `0x18002de9e`: `LimitedLinkConnectivity`
- `0x18002dfd9`: `ResetAutoconfigurationOnOperStatusDown`
- `0x18002dfc9`: `DnsAutoConfigurationEnabled`

## pseudocode

```c
const char *__fastcall InterfaceFieldModified(unsigned int a1)
{
  unsigned int v1; // ecx
  unsigned int v2; // ecx
  unsigned int v3; // ecx
  unsigned int v4; // ecx
  const char *result; // rax
  unsigned int v6; // ecx
  unsigned int v7; // ecx
  unsigned int v8; // ecx
  unsigned int v9; // ecx
  unsigned int v10; // ecx
  unsigned int v11; // ecx
  unsigned int v12; // ecx
  unsigned int v13; // ecx
  unsigned int v14; // ecx
  unsigned int v15; // ecx
  unsigned int v16; // ecx
  unsigned int v17; // ecx
  unsigned int v18; // ecx
  unsigned int v19; // ecx
  unsigned int v20; // ecx
  unsigned int v21; // ecx
  unsigned int v22; // ecx
  unsigned int v23; // ecx
  unsigned int v24; // ecx
  unsigned int v25; // ecx
  unsigned int v26; // ecx
  unsigned int v27; // ecx
  unsigned int v28; // ecx
  unsigned int v29; // ecx
  unsigned int v30; // ecx
  unsigned int v31; // ecx
  unsigned int v32; // ecx
  unsigned int v33; // ecx
  unsigned int v34; // ecx

  if ( a1 <= 0x10 )
  {
    if ( a1 == 16 )
      return "NetworkCategory";
    if ( a1 > 6 )
    {
      v6 = a1 - 7;
      if ( !v6 )
        return "UseZeroBroadcastAddress";
      v7 = v6 - 1;
      if ( !v7 )
        return "UseBroadcastForRouterDiscovery";
      v8 = v7 - 1;
      if ( !v8 )
        return "DhcpRouterDiscoveryEnabled";
      v9 = v8 - 1;
      if ( !v9 )
        return "ManagedAddressConfigurationSupported";
      v10 = v9 - 1;
      if ( !v10 )
        return "OtherStatefulConfigurationSupported";
      if ( v10 == 1 )
        return "AdvertiseDefaultRoute";
    }
    else
    {
      if ( a1 == 6 )
        return "UseAutomaticMetric";
      if ( !a1 )
        return "AdvertisingEnabled";
      v1 = a1 - 1;
      if ( !v1 )
        return "ForwardingEnabled";
      v2 = v1 - 1;
      if ( !v2 )
        return "MulticastForwardingEnabled";
      v3 = v2 - 1;
      if ( !v3 )
        return "WeakHostSend";
      v4 = v3 - 1;
      if ( !v4 )
        return "WeakHostReceive";
      if ( v4 == 1 )
        return "UseNeighborUnreachabilityDetection";
    }
    return "unknown";
  }
  if ( a1 > 0xA2 )
  {
    if ( a1 <= 0xD4 )
    {
      if ( a1 == 212 )
        return "ProxyDetected";
      v19 = a1 - 163;
      if ( !v19 )
        return "EnableDirectMACPattern";
      v20 = v19 - 1;
      if ( !v20 )
        return "EnableWol";
      v21 = v20 - 1;
      if ( !v21 )
        return "ForceTunneling";
      v22 = v21 - 3;
      if ( !v22 )
        return "DomainNetworkLocation";
      v23 = v22 - 8;
      if ( !v23 )
        return "RandomizedEpoch";
      v24 = v23 - 8;
      if ( !v24 )
        return "EcnCapability";
      v25 = v24 - 4;
      if ( !v25 )
        return "DomainType";
      v26 = v25 - 4;
      if ( !v26 )
        return "NetworkSignature";
      if ( v26 == 16 )
        return "InternetConnectivityDetected";
      return "unknown";
    }
    v27 = a1 - 216;
    if ( v27 )
    {
      v28 = v27 - 4;
      if ( v28 )
      {
        v29 = v28 - 1;
        if ( v29 )
        {
          v30 = v29 - 3;
          if ( v30 )
          {
            v31 = v30 - 4;
            if ( v31 )
            {
              v32 = v31 - 1;
              if ( v32 )
              {
                v33 = v32 - 1;
                if ( v33 )
                {
                  v34 = v33 - 1;
                  if ( v34 )
                  {
                    if ( v34 != 1 )
                      return "unknown";
                    return "IcmpRedirectEnabled";
                  }
                  else
                  {
                    return "DhcpStaticIPCoexistence";
                  }
                }
                else
                {
                  return "DnsAutoConfigurationEnabled";
                }
              }
              else
              {
                return "ClampMssEnabled";
              }
            }
            else
            {
              return "ResetAutoconfigurationOnOperStatusDown";
            }
          }
          else
          {
            return "ForwardingTag";
          }
        }
        else
        {
          return "RoutingFlags";
        }
      }
      else
      {
        return "PrefixSharing";
      }
    }
    else
    {
      return "DadRetransmitTime";
    }
  }
  else
  {
    if ( a1 == 162 )
      return "ForceARPNDPattern";
    if ( a1 > 0x38 )
    {
      v11 = a1 - 120;
      if ( !v11 )
        return "NlMtu";
      v12 = v11 - 4;
      if ( !v12 )
        return "SitePrefixLength";
      v13 = v12 - 4;
      if ( !v13 )
        return "MulticastForwardingHopLimit";
      v14 = v13 - 4;
      if ( !v14 )
        return "CurrentHopLimit";
      v15 = v14 - 4;
      if ( !v15 )
        return "LinkLocalAddress";
      v16 = v15 - 16;
      if ( !v16 )
        return "DisableDefaultRoutes";
      v17 = v16 - 4;
      if ( !v17 )
        return "AdvertisedRouterLifetime";
      v18 = v17 - 4;
      if ( !v18 )
        return "SendUnsolicitedNeighborAdvertisementOnDad";
      if ( v18 == 1 )
        return "LimitedLinkConnectivity";
      return "unknown";
    }
    switch ( a1 )
    {
      case 0x38u:
        return "ZoneIndices";
      case 0x14u:
        return "RouterDiscoveryBehavior";
      case 0x18u:
        return "TypeOfInterface";
      case 0x1Cu:
        return "Metric";
      case 0x20u:
        return "BaseReachableTime";
      case 0x24u:
        return "RetransmitTime";
      case 0x28u:
        return "PathMtuDiscoveryTimeout";
      case 0x2Cu:
        return "DadTransmits";
      case 0x30u:
        return "LinkLocalAddressBehavior";
      default:
        result = "unknown";
        if ( a1 == 52 )
          return "LinkLocalAddressTimeout";
        break;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002dd00  cmp     ecx, 10h
0x18002dd03  ja      loc_18002DDC9
0x18002dd09  jz      loc_18002DDC1
0x18002dd0f  cmp     ecx, 6
0x18002dd12  ja      short loc_18002DD6F
0x18002dd14  jz      short loc_18002DD67
0x18002dd16  test    ecx, ecx
0x18002dd18  jz      short loc_18002DD5F
0x18002dd1a  sub     ecx, 1
0x18002dd1d  jz      short loc_18002DD57
0x18002dd1f  sub     ecx, 1
0x18002dd22  jz      short loc_18002DD4F
0x18002dd24  sub     ecx, 1
0x18002dd27  jz      short loc_18002DD47
0x18002dd29  sub     ecx, 1
0x18002dd2c  jz      short loc_18002DD3F
0x18002dd2e  cmp     ecx, 1
0x18002dd31  jnz     loc_18002DFB1
0x18002dd37  lea     rax, aUseneighborunr; "UseNeighborUnreachabilityDetection"
0x18002dd3e  retn
0x18002dd3f  lea     rax, aWeakhostreceiv; "WeakHostReceive"
0x18002dd46  retn
0x18002dd47  lea     rax, aWeakhostsend; "WeakHostSend"
0x18002dd4e  retn
0x18002dd4f  lea     rax, aMulticastforwa; "MulticastForwardingEnabled"
0x18002dd56  retn
0x18002dd57  lea     rax, aForwardingenab; "ForwardingEnabled"
0x18002dd5e  retn
0x18002dd5f  lea     rax, aAdvertisingena; "AdvertisingEnabled"
0x18002dd66  retn
0x18002dd67  lea     rax, aUseautomaticme; "UseAutomaticMetric"
0x18002dd6e  retn
0x18002dd6f  sub     ecx, 7
0x18002dd72  jz      short loc_18002DDB9
0x18002dd74  sub     ecx, 1
0x18002dd77  jz      short loc_18002DDB1
0x18002dd79  sub     ecx, 1
0x18002dd7c  jz      short loc_18002DDA9
0x18002dd7e  sub     ecx, 1
0x18002dd81  jz      short loc_18002DDA1
0x18002dd83  sub     ecx, 1
0x18002dd86  jz      short loc_18002DD99
0x18002dd88  cmp     ecx, 1
0x18002dd8b  jnz     loc_18002DFB1
0x18002dd91  lea     rax, aAdvertisedefau; "AdvertiseDefaultRoute"
0x18002dd98  retn
0x18002dd99  lea     rax, aOtherstatefulc; "OtherStatefulConfigurationSupported"
0x18002dda0  retn
0x18002dda1  lea     rax, aManagedaddress; "ManagedAddressConfigurationSupported"
0x18002dda8  retn
0x18002dda9  lea     rax, aDhcprouterdisc; "DhcpRouterDiscoveryEnabled"
0x18002ddb0  retn
0x18002ddb1  lea     rax, aUsebroadcastfo; "UseBroadcastForRouterDiscovery"
0x18002ddb8  retn
0x18002ddb9  lea     rax, aUsezerobroadca; "UseZeroBroadcastAddress"
0x18002ddc0  retn
0x18002ddc1  lea     rax, aNetworkcategor; "NetworkCategory"
0x18002ddc8  retn
0x18002ddc9  mov     eax, 0A2h
0x18002ddce  cmp     ecx, eax
0x18002ddd0  ja      loc_18002DEEE
0x18002ddd6  jz      loc_18002DEE6
0x18002dddc  cmp     ecx, 38h ; '8'
0x18002dddf  ja      loc_18002DE6D
0x18002dde5  jz      short loc_18002DE65
0x18002dde7  cmp     ecx, 14h
0x18002ddea  jz      short loc_18002DE5D
0x18002ddec  cmp     ecx, 18h
0x18002ddef  jz      short loc_18002DE55
0x18002ddf1  cmp     ecx, 1Ch
0x18002ddf4  jz      short loc_18002DE4D
0x18002ddf6  cmp     ecx, 20h ; ' '
0x18002ddf9  jz      short loc_18002DE45
0x18002ddfb  cmp     ecx, 24h ; '$'
0x18002ddfe  jz      short loc_18002DE3D
0x18002de00  cmp     ecx, 28h ; '('
0x18002de03  jz      short loc_18002DE35
0x18002de05  cmp     ecx, 2Ch ; ','
0x18002de08  jz      short loc_18002DE2D
0x18002de0a  cmp     ecx, 30h ; '0'
0x18002de0d  jz      short loc_18002DE25
0x18002de0f  cmp     ecx, 34h ; '4'
0x18002de12  lea     rdx, aLinklocaladdre_1; "LinkLocalAddressTimeout"
0x18002de19  lea     rax, aUnknown_2; "unknown"
0x18002de20  cmovz   rax, rdx
0x18002de24  retn
0x18002de25  lea     rax, aLinklocaladdre; "LinkLocalAddressBehavior"
0x18002de2c  retn
0x18002de2d  lea     rax, aDadtransmits; "DadTransmits"
0x18002de34  retn
0x18002de35  lea     rax, aPathmtudiscove; "PathMtuDiscoveryTimeout"
0x18002de3c  retn
0x18002de3d  lea     rax, aRetransmittime; "RetransmitTime"
0x18002de44  retn
0x18002de45  lea     rax, aBasereachablet; "BaseReachableTime"
0x18002de4c  retn
0x18002de4d  lea     rax, aMetric; "Metric"
0x18002de54  retn
0x18002de55  lea     rax, aTypeofinterfac; "TypeOfInterface"
0x18002de5c  retn
0x18002de5d  lea     rax, aRouterdiscover; "RouterDiscoveryBehavior"
0x18002de64  retn
0x18002de65  lea     rax, aZoneindices; "ZoneIndices"
0x18002de6c  retn
0x18002de6d  sub     ecx, 78h ; 'x'
0x18002de70  jz      short loc_18002DEDE
0x18002de72  sub     ecx, 4
0x18002de75  jz      short loc_18002DED6
0x18002de77  sub     ecx, 4
0x18002de7a  jz      short loc_18002DECE
0x18002de7c  sub     ecx, 4
0x18002de7f  jz      short loc_18002DEC6
0x18002de81  sub     ecx, 4
0x18002de84  jz      short loc_18002DEBE
0x18002de86  sub     ecx, 10h
0x18002de89  jz      short loc_18002DEB6
0x18002de8b  sub     ecx, 4
0x18002de8e  jz      short loc_18002DEAE
0x18002de90  sub     ecx, 4
0x18002de93  jz      short loc_18002DEA6
0x18002de95  cmp     ecx, 1
0x18002de98  jnz     loc_18002DFB1
0x18002de9e  lea     rax, aLimitedlinkcon; "LimitedLinkConnectivity"
0x18002dea5  retn
0x18002dea6  lea     rax, aSendunsolicite; "SendUnsolicitedNeighborAdvertisementOnD"...
0x18002dead  retn
0x18002deae  lea     rax, aAdvertisedrout; "AdvertisedRouterLifetime"
0x18002deb5  retn
0x18002deb6  lea     rax, aDisabledefault; "DisableDefaultRoutes"
0x18002debd  retn
0x18002debe  lea     rax, aLinklocaladdre_0; "LinkLocalAddress"
0x18002dec5  retn
0x18002dec6  lea     rax, aCurrenthoplimi; "CurrentHopLimit"
0x18002decd  retn
0x18002dece  lea     rax, aMulticastforwa_0; "MulticastForwardingHopLimit"
0x18002ded5  retn
0x18002ded6  lea     rax, aSiteprefixleng; "SitePrefixLength"
0x18002dedd  retn
0x18002dede  lea     rax, aNlmtu; "NlMtu"
0x18002dee5  retn
0x18002dee6  lea     rax, aForcearpndpatt; "ForceARPNDPattern"
0x18002deed  retn
0x18002deee  mov     eax, 0D4h
0x18002def3  cmp     ecx, eax
0x18002def5  ja      loc_18002DF81
0x18002defb  jz      short loc_18002DF79
0x18002defd  sub     ecx, 0A3h
0x18002df03  jz      short loc_18002DF71
0x18002df05  sub     ecx, 1
0x18002df08  jz      short loc_18002DF69
0x18002df0a  sub     ecx, 1
0x18002df0d  jz      short loc_18002DF61
0x18002df0f  sub     ecx, 3
0x18002df12  jz      short loc_18002DF59
0x18002df14  sub     ecx, 8
0x18002df17  jz      short loc_18002DF51
0x18002df19  sub     ecx, 8
0x18002df1c  jz      short loc_18002DF49
0x18002df1e  sub     ecx, 4
0x18002df21  jz      short loc_18002DF41
0x18002df23  sub     ecx, 4
0x18002df26  jz      short loc_18002DF39
0x18002df28  cmp     ecx, 10h
0x18002df2b  jnz     loc_18002DFB1
0x18002df31  lea     rax, aInternetconnec; "InternetConnectivityDetected"
0x18002df38  retn
0x18002df39  lea     rax, aNetworksignatu; "NetworkSignature"
0x18002df40  retn
0x18002df41  lea     rax, aDomaintype; "DomainType"
0x18002df48  retn
0x18002df49  lea     rax, aEcncapability; "EcnCapability"
0x18002df50  retn
0x18002df51  lea     rax, aRandomizedepoc; "RandomizedEpoch"
0x18002df58  retn
0x18002df59  lea     rax, aDomainnetworkl; "DomainNetworkLocation"
0x18002df60  retn
0x18002df61  lea     rax, aForcetunneling; "ForceTunneling"
0x18002df68  retn
0x18002df69  lea     rax, aEnablewol; "EnableWol"
0x18002df70  retn
0x18002df71  lea     rax, aEnabledirectma; "EnableDirectMACPattern"
0x18002df78  retn
0x18002df79  lea     rax, aProxydetected; "ProxyDetected"
0x18002df80  retn
0x18002df81  sub     ecx, 0D8h
0x18002df87  jz      short loc_18002DFF9
0x18002df89  sub     ecx, 4
0x18002df8c  jz      short loc_18002DFF1
0x18002df8e  sub     ecx, 1
0x18002df91  jz      short loc_18002DFE9
0x18002df93  sub     ecx, 3
0x18002df96  jz      short loc_18002DFE1
0x18002df98  sub     ecx, 4
0x18002df9b  jz      short loc_18002DFD9
0x18002df9d  sub     ecx, 1
0x18002dfa0  jz      short loc_18002DFD1
0x18002dfa2  sub     ecx, 1
0x18002dfa5  jz      short loc_18002DFC9
0x18002dfa7  sub     ecx, 1
0x18002dfaa  jz      short loc_18002DFC1
0x18002dfac  cmp     ecx, 1
0x18002dfaf  jz      short loc_18002DFB9
0x18002dfb1  lea     rax, aUnknown_2; "unknown"
0x18002dfb8  retn
0x18002dfb9  lea     rax, aIcmpredirecten; "IcmpRedirectEnabled"
0x18002dfc0  retn
0x18002dfc1  lea     rax, aDhcpstaticipco; "DhcpStaticIPCoexistence"
0x18002dfc8  retn
0x18002dfc9  lea     rax, aDnsautoconfigu; "DnsAutoConfigurationEnabled"
0x18002dfd0  retn
0x18002dfd1  lea     rax, aClampmssenable; "ClampMssEnabled"
0x18002dfd8  retn
0x18002dfd9  lea     rax, aResetautoconfi; "ResetAutoconfigurationOnOperStatusDown"
0x18002dfe0  retn
0x18002dfe1  lea     rax, aForwardingtag; "ForwardingTag"
0x18002dfe8  retn
0x18002dfe9  lea     rax, aRoutingflags; "RoutingFlags"
0x18002dff0  retn
0x18002dff1  lea     rax, aPrefixsharing; "PrefixSharing"
0x18002dff8  retn
0x18002dff9  lea     rax, aDadretransmitt; "DadRetransmitTime"
0x18002e000  retn
```
