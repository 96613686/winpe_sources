# GetServiceControlCodeDescription(ulong)

- ea: `0x1800732c0`
- end: `0x18007343b`
- name: `?GetServiceControlCodeDescription@@YAPEBDK@Z`
- size: `379`
- prototype: `const char *__fastcall(unsigned int)`
- caller_count: `5`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18001ff60`
- `0x18004269c`
- `0x18007351c`
- `0x180074694`
- `0x18007523c`

## callees

- `0x1800732c0`

## string_xrefs

- `0x180073348`: `SERVICE_CONTROL_STOP`
- `0x18007333f`: `SERVICE_CONTROL_PAUSE`
- `0x180073336`: `SERVICE_CONTROL_CONTINUE`
- `0x18007332d`: `SERVICE_CONTROL_INTERROGATE`
- `0x180073324`: `SERVICE_CONTROL_SHUTDOWN`
- `0x18007331b`: `SERVICE_CONTROL_PARAMCHANGE`
- `0x180073312`: `SERVICE_CONTROL_NETBINDADD`
- `0x180073309`: `SERVICE_CONTROL_NETBINDREMOVE`
- `0x180073351`: `SERVICE_CONTROL_NETBINDENABLE`
- `0x1800733b7`: `SERVICE_CONTROL_NETBINDDISABLE`
- `0x1800733ae`: `SERVICE_CONTROL_DEVICEEVENT`
- `0x1800733a5`: `SERVICE_CONTROL_HARDWAREPROFILECHANGE`
- `0x18007339c`: `SERVICE_CONTROL_POWEREVENT`
- `0x180073393`: `SERVICE_CONTROL_SESSIONCHANGE`
- `0x18007338a`: `SERVICE_CONTROL_PRESHUTDOWN`
- `0x180073381`: `SERVICE_CONTROL_TIMECHANGE`
- `0x1800733c0`: `SERVICE_CONTROL_TRIGGEREVENT`
- `0x180073433`: `IPNATHLP_CONTROL_UPDATE_SETTINGS`
- `0x18007342a`: `IPNATHLP_CONTROL_UPDATE_CONNECTION`
- `0x180073421`: `IPNATHLP_CONTROL_UPDATE_AUTODIAL`
- `0x180073418`: `IPNATHLP_CONTROL_UPDATE_FWLOGGER`
- `0x18007340f`: `IPNATHLP_CONTROL_UPDATE_DNS_DISABLE`
- `0x180073406`: `IPNATHLP_CONTROL_UPDATE_DNS_ENABLE`
- `0x1800733fd`: `IPNATHLP_CONTROL_UPDATE_POLICY`
- `0x1800733f4`: `IPNATHLP_CONTROL_UPDATE_PORTMAPPING`

## pseudocode

```c
const char *__fastcall GetServiceControlCodeDescription(unsigned int a1)
{
  const char *result; // rax
  unsigned int v2; // ecx
  unsigned int v3; // ecx
  unsigned int v4; // ecx
  unsigned int v5; // ecx
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

  result = "UKNOWNN";
  if ( a1 > 0x20 )
  {
    v15 = a1 - 128;
    if ( v15 )
    {
      v16 = v15 - 1;
      if ( v16 )
      {
        v17 = v16 - 1;
        if ( v17 )
        {
          v18 = v17 - 1;
          if ( v18 )
          {
            v19 = v18 - 1;
            if ( v19 )
            {
              v20 = v19 - 1;
              if ( v20 )
              {
                v21 = v20 - 1;
                if ( v21 )
                {
                  if ( v21 == 1 )
                    return "IPNATHLP_CONTROL_UPDATE_PORTMAPPING";
                }
                else
                {
                  return "IPNATHLP_CONTROL_UPDATE_POLICY";
                }
              }
              else
              {
                return "IPNATHLP_CONTROL_UPDATE_DNS_ENABLE";
              }
            }
            else
            {
              return "IPNATHLP_CONTROL_UPDATE_DNS_DISABLE";
            }
          }
          else
          {
            return "IPNATHLP_CONTROL_UPDATE_FWLOGGER";
          }
        }
        else
        {
          return "IPNATHLP_CONTROL_UPDATE_AUTODIAL";
        }
      }
      else
      {
        return "IPNATHLP_CONTROL_UPDATE_CONNECTION";
      }
    }
    else
    {
      return "IPNATHLP_CONTROL_UPDATE_SETTINGS";
    }
  }
  else if ( a1 == 32 )
  {
    return "SERVICE_CONTROL_TRIGGEREVENT";
  }
  else if ( a1 > 9 )
  {
    v9 = a1 - 10;
    if ( v9 )
    {
      v10 = v9 - 1;
      if ( v10 )
      {
        v11 = v10 - 1;
        if ( v11 )
        {
          v12 = v11 - 1;
          if ( v12 )
          {
            v13 = v12 - 1;
            if ( v13 )
            {
              v14 = v13 - 1;
              if ( v14 )
              {
                if ( v14 == 1 )
                  return "SERVICE_CONTROL_TIMECHANGE";
              }
              else
              {
                return "SERVICE_CONTROL_PRESHUTDOWN";
              }
            }
            else
            {
              return "SERVICE_CONTROL_SESSIONCHANGE";
            }
          }
          else
          {
            return "SERVICE_CONTROL_POWEREVENT";
          }
        }
        else
        {
          return "SERVICE_CONTROL_HARDWAREPROFILECHANGE";
        }
      }
      else
      {
        return "SERVICE_CONTROL_DEVICEEVENT";
      }
    }
    else
    {
      return "SERVICE_CONTROL_NETBINDDISABLE";
    }
  }
  else if ( a1 == 9 )
  {
    return "SERVICE_CONTROL_NETBINDENABLE";
  }
  else
  {
    v2 = a1 - 1;
    if ( v2 )
    {
      v3 = v2 - 1;
      if ( v3 )
      {
        v4 = v3 - 1;
        if ( v4 )
        {
          v5 = v4 - 1;
          if ( v5 )
          {
            v6 = v5 - 1;
            if ( v6 )
            {
              v7 = v6 - 1;
              if ( v7 )
              {
                v8 = v7 - 1;
                if ( v8 )
                {
                  if ( v8 == 1 )
                    return "SERVICE_CONTROL_NETBINDREMOVE";
                }
                else
                {
                  return "SERVICE_CONTROL_NETBINDADD";
                }
              }
              else
              {
                return "SERVICE_CONTROL_PARAMCHANGE";
              }
            }
            else
            {
              return "SERVICE_CONTROL_SHUTDOWN";
            }
          }
          else
          {
            return "SERVICE_CONTROL_INTERROGATE";
          }
        }
        else
        {
          return "SERVICE_CONTROL_CONTINUE";
        }
      }
      else
      {
        return "SERVICE_CONTROL_PAUSE";
      }
    }
    else
    {
      return "SERVICE_CONTROL_STOP";
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800732c0  lea     rax, aUknownn; "UKNOWNN"
0x1800732c7  cmp     ecx, 20h ; ' '
0x1800732ca  ja      loc_1800733C9
0x1800732d0  jz      loc_1800733C0
0x1800732d6  cmp     ecx, 9
0x1800732d9  ja      short loc_18007335A
0x1800732db  jz      short loc_180073351
0x1800732dd  sub     ecx, 1
0x1800732e0  jz      short loc_180073348
0x1800732e2  sub     ecx, 1
0x1800732e5  jz      short loc_18007333F
0x1800732e7  sub     ecx, 1
0x1800732ea  jz      short loc_180073336
0x1800732ec  sub     ecx, 1
0x1800732ef  jz      short loc_18007332D
0x1800732f1  sub     ecx, 1
0x1800732f4  jz      short loc_180073324
0x1800732f6  sub     ecx, 1
0x1800732f9  jz      short loc_18007331B
0x1800732fb  sub     ecx, 1
0x1800732fe  jz      short loc_180073312
0x180073300  cmp     ecx, 1
0x180073303  jnz     locret_18007343A
0x180073309  lea     rax, aServiceControl_2; "SERVICE_CONTROL_NETBINDREMOVE"
0x180073310  retn
0x180073312  lea     rax, aServiceControl_9; "SERVICE_CONTROL_NETBINDADD"
0x180073319  retn
0x18007331b  lea     rax, aServiceControl_15; "SERVICE_CONTROL_PARAMCHANGE"
0x180073322  retn
0x180073324  lea     rax, aServiceControl_10; "SERVICE_CONTROL_SHUTDOWN"
0x18007332b  retn
0x18007332d  lea     rax, aServiceControl_12; "SERVICE_CONTROL_INTERROGATE"
0x180073334  retn
0x180073336  lea     rax, aServiceControl_11; "SERVICE_CONTROL_CONTINUE"
0x18007333d  retn
0x18007333f  lea     rax, aServiceControl_1; "SERVICE_CONTROL_PAUSE"
0x180073346  retn
0x180073348  lea     rax, aServiceControl_3; "SERVICE_CONTROL_STOP"
0x18007334f  retn
0x180073351  lea     rax, aServiceControl_4; "SERVICE_CONTROL_NETBINDENABLE"
0x180073358  retn
0x18007335a  sub     ecx, 0Ah
0x18007335d  jz      short loc_1800733B7
0x18007335f  sub     ecx, 1
0x180073362  jz      short loc_1800733AE
0x180073364  sub     ecx, 1
0x180073367  jz      short loc_1800733A5
0x180073369  sub     ecx, 1
0x18007336c  jz      short loc_18007339C
0x18007336e  sub     ecx, 1
0x180073371  jz      short loc_180073393
0x180073373  sub     ecx, 1
0x180073376  jz      short loc_18007338A
0x180073378  cmp     ecx, 1
0x18007337b  jnz     locret_18007343A
0x180073381  lea     rax, aServiceControl_5; "SERVICE_CONTROL_TIMECHANGE"
0x180073388  retn
0x18007338a  lea     rax, aServiceControl_7; "SERVICE_CONTROL_PRESHUTDOWN"
0x180073391  retn
0x180073393  lea     rax, aServiceControl; "SERVICE_CONTROL_SESSIONCHANGE"
0x18007339a  retn
0x18007339c  lea     rax, aServiceControl_8; "SERVICE_CONTROL_POWEREVENT"
0x1800733a3  retn
0x1800733a5  lea     rax, aServiceControl_6; "SERVICE_CONTROL_HARDWAREPROFILECHANGE"
0x1800733ac  retn
0x1800733ae  lea     rax, aServiceControl_14; "SERVICE_CONTROL_DEVICEEVENT"
0x1800733b5  retn
0x1800733b7  lea     rax, aServiceControl_13; "SERVICE_CONTROL_NETBINDDISABLE"
0x1800733be  retn
0x1800733c0  lea     rax, aServiceControl_0; "SERVICE_CONTROL_TRIGGEREVENT"
0x1800733c7  retn
0x1800733c9  sub     ecx, 80h
0x1800733cf  jz      short loc_180073433
0x1800733d1  sub     ecx, 1
0x1800733d4  jz      short loc_18007342A
0x1800733d6  sub     ecx, 1
0x1800733d9  jz      short loc_180073421
0x1800733db  sub     ecx, 1
0x1800733de  jz      short loc_180073418
0x1800733e0  sub     ecx, 1
0x1800733e3  jz      short loc_18007340F
0x1800733e5  sub     ecx, 1
0x1800733e8  jz      short loc_180073406
0x1800733ea  sub     ecx, 1
0x1800733ed  jz      short loc_1800733FD
0x1800733ef  cmp     ecx, 1
0x1800733f2  jnz     short locret_18007343A
0x1800733f4  lea     rax, aIpnathlpContro_6; "IPNATHLP_CONTROL_UPDATE_PORTMAPPING"
0x1800733fb  retn
0x1800733fd  lea     rax, aIpnathlpContro_5; "IPNATHLP_CONTROL_UPDATE_POLICY"
0x180073404  retn
0x180073406  lea     rax, aIpnathlpContro_0; "IPNATHLP_CONTROL_UPDATE_DNS_ENABLE"
0x18007340d  retn
0x18007340f  lea     rax, aIpnathlpContro_4; "IPNATHLP_CONTROL_UPDATE_DNS_DISABLE"
0x180073416  retn
0x180073418  lea     rax, aIpnathlpContro_1; "IPNATHLP_CONTROL_UPDATE_FWLOGGER"
0x18007341f  retn
0x180073421  lea     rax, aIpnathlpContro_2; "IPNATHLP_CONTROL_UPDATE_AUTODIAL"
0x180073428  retn
0x18007342a  lea     rax, aIpnathlpContro; "IPNATHLP_CONTROL_UPDATE_CONNECTION"
0x180073431  retn
0x180073433  lea     rax, aIpnathlpContro_3; "IPNATHLP_CONTROL_UPDATE_SETTINGS"
0x18007343a  retn
```
