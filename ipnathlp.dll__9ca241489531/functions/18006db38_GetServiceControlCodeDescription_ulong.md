# GetServiceControlCodeDescription(ulong)

- ea: `0x18006db38`
- end: `0x18006dc9b`
- name: `?GetServiceControlCodeDescription@@YAPEBDK@Z`
- size: `355`
- prototype: `const char *__fastcall(unsigned int)`
- caller_count: `5`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18001e8b0`
- `0x18003f1bc`
- `0x18006dd7c`
- `0x18006ee48`
- `0x18006f910`

## callees

- `0x18006db38`

## string_xrefs

- `0x18006dbb9`: `SERVICE_CONTROL_STOP`
- `0x18006dbb1`: `SERVICE_CONTROL_PAUSE`
- `0x18006dba9`: `SERVICE_CONTROL_CONTINUE`
- `0x18006dba1`: `SERVICE_CONTROL_INTERROGATE`
- `0x18006db99`: `SERVICE_CONTROL_SHUTDOWN`
- `0x18006db91`: `SERVICE_CONTROL_PARAMCHANGE`
- `0x18006db89`: `SERVICE_CONTROL_NETBINDADD`
- `0x18006db81`: `SERVICE_CONTROL_NETBINDREMOVE`
- `0x18006dbc1`: `SERVICE_CONTROL_NETBINDENABLE`
- `0x18006dc20`: `SERVICE_CONTROL_NETBINDDISABLE`
- `0x18006dc18`: `SERVICE_CONTROL_DEVICEEVENT`
- `0x18006dc10`: `SERVICE_CONTROL_HARDWAREPROFILECHANGE`
- `0x18006dc08`: `SERVICE_CONTROL_POWEREVENT`
- `0x18006dc00`: `SERVICE_CONTROL_SESSIONCHANGE`
- `0x18006dbf8`: `SERVICE_CONTROL_PRESHUTDOWN`
- `0x18006dbf0`: `SERVICE_CONTROL_TIMECHANGE`
- `0x18006dc28`: `SERVICE_CONTROL_TRIGGEREVENT`
- `0x18006dc93`: `IPNATHLP_CONTROL_UPDATE_SETTINGS`
- `0x18006dc8b`: `IPNATHLP_CONTROL_UPDATE_CONNECTION`
- `0x18006dc83`: `IPNATHLP_CONTROL_UPDATE_AUTODIAL`
- `0x18006dc7b`: `IPNATHLP_CONTROL_UPDATE_FWLOGGER`
- `0x18006dc73`: `IPNATHLP_CONTROL_UPDATE_DNS_DISABLE`
- `0x18006dc6b`: `IPNATHLP_CONTROL_UPDATE_DNS_ENABLE`
- `0x18006dc63`: `IPNATHLP_CONTROL_UPDATE_POLICY`
- `0x18006dc5b`: `IPNATHLP_CONTROL_UPDATE_PORTMAPPING`

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
0x18006db38  lea     rax, aUknownn; "UKNOWNN"
0x18006db3f  cmp     ecx, 20h ; ' '
0x18006db42  ja      loc_18006DC30
0x18006db48  jz      loc_18006DC28
0x18006db4e  cmp     ecx, 9
0x18006db51  ja      short loc_18006DBC9
0x18006db53  jz      short loc_18006DBC1
0x18006db55  sub     ecx, 1
0x18006db58  jz      short loc_18006DBB9
0x18006db5a  sub     ecx, 1
0x18006db5d  jz      short loc_18006DBB1
0x18006db5f  sub     ecx, 1
0x18006db62  jz      short loc_18006DBA9
0x18006db64  sub     ecx, 1
0x18006db67  jz      short loc_18006DBA1
0x18006db69  sub     ecx, 1
0x18006db6c  jz      short loc_18006DB99
0x18006db6e  sub     ecx, 1
0x18006db71  jz      short loc_18006DB91
0x18006db73  sub     ecx, 1
0x18006db76  jz      short loc_18006DB89
0x18006db78  cmp     ecx, 1
0x18006db7b  jnz     locret_18006DC9A
0x18006db81  lea     rax, aServiceControl_2; "SERVICE_CONTROL_NETBINDREMOVE"
0x18006db88  retn
0x18006db89  lea     rax, aServiceControl_9; "SERVICE_CONTROL_NETBINDADD"
0x18006db90  retn
0x18006db91  lea     rax, aServiceControl_15; "SERVICE_CONTROL_PARAMCHANGE"
0x18006db98  retn
0x18006db99  lea     rax, aServiceControl_10; "SERVICE_CONTROL_SHUTDOWN"
0x18006dba0  retn
0x18006dba1  lea     rax, aServiceControl_12; "SERVICE_CONTROL_INTERROGATE"
0x18006dba8  retn
0x18006dba9  lea     rax, aServiceControl_11; "SERVICE_CONTROL_CONTINUE"
0x18006dbb0  retn
0x18006dbb1  lea     rax, aServiceControl_1; "SERVICE_CONTROL_PAUSE"
0x18006dbb8  retn
0x18006dbb9  lea     rax, aServiceControl_3; "SERVICE_CONTROL_STOP"
0x18006dbc0  retn
0x18006dbc1  lea     rax, aServiceControl_4; "SERVICE_CONTROL_NETBINDENABLE"
0x18006dbc8  retn
0x18006dbc9  sub     ecx, 0Ah
0x18006dbcc  jz      short loc_18006DC20
0x18006dbce  sub     ecx, 1
0x18006dbd1  jz      short loc_18006DC18
0x18006dbd3  sub     ecx, 1
0x18006dbd6  jz      short loc_18006DC10
0x18006dbd8  sub     ecx, 1
0x18006dbdb  jz      short loc_18006DC08
0x18006dbdd  sub     ecx, 1
0x18006dbe0  jz      short loc_18006DC00
0x18006dbe2  sub     ecx, 1
0x18006dbe5  jz      short loc_18006DBF8
0x18006dbe7  cmp     ecx, 1
0x18006dbea  jnz     locret_18006DC9A
0x18006dbf0  lea     rax, aServiceControl_5; "SERVICE_CONTROL_TIMECHANGE"
0x18006dbf7  retn
0x18006dbf8  lea     rax, aServiceControl_7; "SERVICE_CONTROL_PRESHUTDOWN"
0x18006dbff  retn
0x18006dc00  lea     rax, aServiceControl; "SERVICE_CONTROL_SESSIONCHANGE"
0x18006dc07  retn
0x18006dc08  lea     rax, aServiceControl_8; "SERVICE_CONTROL_POWEREVENT"
0x18006dc0f  retn
0x18006dc10  lea     rax, aServiceControl_6; "SERVICE_CONTROL_HARDWAREPROFILECHANGE"
0x18006dc17  retn
0x18006dc18  lea     rax, aServiceControl_14; "SERVICE_CONTROL_DEVICEEVENT"
0x18006dc1f  retn
0x18006dc20  lea     rax, aServiceControl_13; "SERVICE_CONTROL_NETBINDDISABLE"
0x18006dc27  retn
0x18006dc28  lea     rax, aServiceControl_0; "SERVICE_CONTROL_TRIGGEREVENT"
0x18006dc2f  retn
0x18006dc30  sub     ecx, 80h
0x18006dc36  jz      short loc_18006DC93
0x18006dc38  sub     ecx, 1
0x18006dc3b  jz      short loc_18006DC8B
0x18006dc3d  sub     ecx, 1
0x18006dc40  jz      short loc_18006DC83
0x18006dc42  sub     ecx, 1
0x18006dc45  jz      short loc_18006DC7B
0x18006dc47  sub     ecx, 1
0x18006dc4a  jz      short loc_18006DC73
0x18006dc4c  sub     ecx, 1
0x18006dc4f  jz      short loc_18006DC6B
0x18006dc51  sub     ecx, 1
0x18006dc54  jz      short loc_18006DC63
0x18006dc56  cmp     ecx, 1
0x18006dc59  jnz     short locret_18006DC9A
0x18006dc5b  lea     rax, aIpnathlpContro_6; "IPNATHLP_CONTROL_UPDATE_PORTMAPPING"
0x18006dc62  retn
0x18006dc63  lea     rax, aIpnathlpContro_5; "IPNATHLP_CONTROL_UPDATE_POLICY"
0x18006dc6a  retn
0x18006dc6b  lea     rax, aIpnathlpContro_0; "IPNATHLP_CONTROL_UPDATE_DNS_ENABLE"
0x18006dc72  retn
0x18006dc73  lea     rax, aIpnathlpContro_4; "IPNATHLP_CONTROL_UPDATE_DNS_DISABLE"
0x18006dc7a  retn
0x18006dc7b  lea     rax, aIpnathlpContro_1; "IPNATHLP_CONTROL_UPDATE_FWLOGGER"
0x18006dc82  retn
0x18006dc83  lea     rax, aIpnathlpContro_2; "IPNATHLP_CONTROL_UPDATE_AUTODIAL"
0x18006dc8a  retn
0x18006dc8b  lea     rax, aIpnathlpContro; "IPNATHLP_CONTROL_UPDATE_CONNECTION"
0x18006dc92  retn
0x18006dc93  lea     rax, aIpnathlpContro_3; "IPNATHLP_CONTROL_UPDATE_SETTINGS"
0x18006dc9a  retn
```
