# BthGetPolicyName

- ea: `0x180031fd8`
- end: `0x1800320a2`
- name: `BthGetPolicyName`
- size: `202`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18001e028`
- `0x18003278c`

## callees

- `0x180031fd8`

## string_xrefs

- `0x180032006`: `LinkSecurityLevel`
- `0x180032091`: `ServicesAllowedList`
- `0x18003207f`: `AllowPrepairing`

## pseudocode

```c
const wchar_t *__fastcall BthGetPolicyName(int a1)
{
  int v1; // ecx
  int v2; // ecx
  int v3; // ecx
  int v4; // ecx
  int v5; // ecx
  const wchar_t *result; // rax

  if ( a1 > 64 )
  {
    switch ( a1 )
    {
      case 128:
        return L"DevicesAllowedList";
      case 256:
        return L"ServicesAllowedList";
      case 512:
        return L"RequireRestrictedMode";
      case 1024:
        return L"AllowPrepairing";
      default:
        result = L"SetMinimumEncryptionKeySize";
        if ( a1 != 2048 )
          return L"Unknown";
        break;
    }
  }
  else if ( a1 == 64 )
  {
    return L"LocalDeviceName";
  }
  else
  {
    v1 = a1 - 1;
    if ( v1 )
    {
      v2 = v1 - 1;
      if ( v2 )
      {
        v3 = v2 - 2;
        if ( v3 )
        {
          v4 = v3 - 4;
          if ( v4 )
          {
            v5 = v4 - 8;
            if ( v5 )
            {
              if ( v5 == 16 )
                return L"LinkSecurityLevel";
              else
                return L"Unknown";
            }
            else
            {
              return L"AllowOutOfBandPairing";
            }
          }
          else
          {
            return L"AllowAdvertising";
          }
        }
        else
        {
          return L"AllowConnectableMode";
        }
      }
      else
      {
        return L"AllowDiscoverableMode";
      }
    }
    else
    {
      return L"AllowBluetooth";
    }
  }
  return result;
}

```

## disassembly

```asm
0x180031fd8  cmp     ecx, 40h ; '@'
0x180031fdb  jg      short loc_180032045
0x180031fdd  jz      short loc_18003203C
0x180031fdf  sub     ecx, 1
0x180031fe2  jz      short loc_180032033
0x180031fe4  sub     ecx, 1
0x180031fe7  jz      short loc_18003202A
0x180031fe9  sub     ecx, 2
0x180031fec  jz      short loc_180032021
0x180031fee  sub     ecx, 4
0x180031ff1  jz      short loc_180032018
0x180031ff3  sub     ecx, 8
0x180031ff6  jz      short loc_18003200F
0x180031ff8  cmp     ecx, 10h
0x180031ffb  jz      short loc_180032006
0x180031ffd  lea     rax, aUnknown; "Unknown"
0x180032004  retn
0x180032006  lea     rax, aLinksecurityle; "LinkSecurityLevel"
0x18003200d  retn
0x18003200f  lea     rax, aAllowoutofband; "AllowOutOfBandPairing"
0x180032016  retn
0x180032018  lea     rax, aAllowadvertisi; "AllowAdvertising"
0x18003201f  retn
0x180032021  lea     rax, aAllowconnectab; "AllowConnectableMode"
0x180032028  retn
0x18003202a  lea     rax, aAllowdiscovera; "AllowDiscoverableMode"
0x180032031  retn
0x180032033  lea     rax, aAllowbluetooth; "AllowBluetooth"
0x18003203a  retn
0x18003203c  lea     rax, aLocaldevicenam; "LocalDeviceName"
0x180032043  retn
0x180032045  cmp     ecx, 80h
0x18003204b  jz      short loc_18003209A
0x18003204d  cmp     ecx, 100h
0x180032053  jz      short loc_180032091
0x180032055  cmp     ecx, 200h
0x18003205b  jz      short loc_180032088
0x18003205d  cmp     ecx, 400h
0x180032063  jz      short loc_18003207F
0x180032065  cmp     ecx, 800h
0x18003206b  lea     rdx, aUnknown; "Unknown"
0x180032072  lea     rax, aSetminimumencr; "SetMinimumEncryptionKeySize"
0x180032079  cmovnz  rax, rdx
0x18003207d  retn
0x18003207f  lea     rax, aAllowprepairin; "AllowPrepairing"
0x180032086  retn
0x180032088  lea     rax, aRequirerestric; "RequireRestrictedMode"
0x18003208f  retn
0x180032091  lea     rax, aServicesallowe; "ServicesAllowedList"
0x180032098  retn
0x18003209a  lea     rax, aDevicesallowed; "DevicesAllowedList"
0x1800320a1  retn
```
