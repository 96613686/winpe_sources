# BthGetPolicyKeyValueName

- ea: `0x180031f04`
- end: `0x180031fce`
- name: `BthGetPolicyKeyValueName`
- size: `202`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18001e028`

## callees

- `0x180031f04`

## string_xrefs

- `0x180031f32`: `PM_LinkSecurityLevel`
- `0x180031fbd`: `PM_ServicesAllowedList`
- `0x180031fab`: `PM_AllowPrepairing`

## pseudocode

```c
const WCHAR *__fastcall BthGetPolicyKeyValueName(int a1)
{
  int v1; // ecx
  int v2; // ecx
  int v3; // ecx
  int v4; // ecx
  int v5; // ecx
  const WCHAR *result; // rax

  if ( a1 > 64 )
  {
    switch ( a1 )
    {
      case 128:
        return L"PM_DevicesAllowedList";
      case 256:
        return L"PM_ServicesAllowedList";
      case 512:
        return L"PM_RequireRestrictedMode";
      case 1024:
        return L"PM_AllowPrepairing";
      default:
        result = L"PM_SetMinimumEncryptionKeySize";
        if ( a1 != 2048 )
          return L"Unknown";
        break;
    }
  }
  else if ( a1 == 64 )
  {
    return L"PM_LocalDeviceName";
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
                return L"PM_LinkSecurityLevel";
              else
                return L"Unknown";
            }
            else
            {
              return L"PM_AllowOutOfBandPairing";
            }
          }
          else
          {
            return L"PM_AllowAdvertising";
          }
        }
        else
        {
          return L"PM_AllowConnectableMode";
        }
      }
      else
      {
        return L"PM_AllowDiscoverableMode";
      }
    }
    else
    {
      return L"PM_AllowBluetooth";
    }
  }
  return result;
}

```

## disassembly

```asm
0x180031f04  cmp     ecx, 40h ; '@'
0x180031f07  jg      short loc_180031F71
0x180031f09  jz      short loc_180031F68
0x180031f0b  sub     ecx, 1
0x180031f0e  jz      short loc_180031F5F
0x180031f10  sub     ecx, 1
0x180031f13  jz      short loc_180031F56
0x180031f15  sub     ecx, 2
0x180031f18  jz      short loc_180031F4D
0x180031f1a  sub     ecx, 4
0x180031f1d  jz      short loc_180031F44
0x180031f1f  sub     ecx, 8
0x180031f22  jz      short loc_180031F3B
0x180031f24  cmp     ecx, 10h
0x180031f27  jz      short loc_180031F32
0x180031f29  lea     rax, aUnknown; "Unknown"
0x180031f30  retn
0x180031f32  lea     rax, aPmLinksecurity; "PM_LinkSecurityLevel"
0x180031f39  retn
0x180031f3b  lea     rax, aPmAllowoutofba; "PM_AllowOutOfBandPairing"
0x180031f42  retn
0x180031f44  lea     rax, aPmAllowadverti; "PM_AllowAdvertising"
0x180031f4b  retn
0x180031f4d  lea     rax, aPmAllowconnect; "PM_AllowConnectableMode"
0x180031f54  retn
0x180031f56  lea     rax, aPmAllowdiscove; "PM_AllowDiscoverableMode"
0x180031f5d  retn
0x180031f5f  lea     rax, aPmAllowbluetoo; "PM_AllowBluetooth"
0x180031f66  retn
0x180031f68  lea     rax, aPmLocaldevicen; "PM_LocalDeviceName"
0x180031f6f  retn
0x180031f71  cmp     ecx, 80h
0x180031f77  jz      short loc_180031FC6
0x180031f79  cmp     ecx, 100h
0x180031f7f  jz      short loc_180031FBD
0x180031f81  cmp     ecx, 200h
0x180031f87  jz      short loc_180031FB4
0x180031f89  cmp     ecx, 400h
0x180031f8f  jz      short loc_180031FAB
0x180031f91  cmp     ecx, 800h
0x180031f97  lea     rdx, aUnknown; "Unknown"
0x180031f9e  lea     rax, aPmSetminimumen; "PM_SetMinimumEncryptionKeySize"
0x180031fa5  cmovnz  rax, rdx
0x180031fa9  retn
0x180031fab  lea     rax, aPmAllowprepair; "PM_AllowPrepairing"
0x180031fb2  retn
0x180031fb4  lea     rax, aPmRequirerestr; "PM_RequireRestrictedMode"
0x180031fbb  retn
0x180031fbd  lea     rax, aPmServicesallo; "PM_ServicesAllowedList"
0x180031fc4  retn
0x180031fc6  lea     rax, aPmDevicesallow; "PM_DevicesAllowedList"
0x180031fcd  retn
```
