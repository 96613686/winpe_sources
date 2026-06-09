# IISGeneralEvents::GENERAL_GET_URL_METADATA::TranslateEnumAccessPermsToString(IISGeneralEvents::GENERAL_GET_URL_METADATA::enumAccessPerms)

- ea: `0x180023524`
- end: `0x180023609`
- name: `?TranslateEnumAccessPermsToString@GENERAL_GET_URL_METADATA@IISGeneralEvents@@SAPEBGW4enumAccessPerms@12@@Z`
- size: `229`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800218e0`

## callees

- `0x180023524`

## string_xrefs

- `0x18002357d`: `Write`
- `0x1800235f1`: `NoRemoteWrite`
- `0x1800235e9`: `NoRemoteRead`

## pseudocode

```c
const wchar_t *__fastcall IISGeneralEvents::GENERAL_GET_URL_METADATA::TranslateEnumAccessPermsToString(unsigned int a1)
{
  unsigned int v1; // ecx
  unsigned int v2; // ecx
  unsigned int v3; // ecx
  unsigned int v4; // ecx
  unsigned int v5; // ecx
  unsigned int v6; // ecx
  const wchar_t *result; // rax

  if ( a1 > 0x80 )
  {
    switch ( a1 )
    {
      case 0x100u:
        return L"SSL128";
      case 0x200u:
        return L"Script";
      case 0x400u:
        return L"NoRemoteWrite";
      case 0x1000u:
        return L"NoRemoteRead";
      case 0x2000u:
        return L"NoRemoteExec";
      case 0x4000u:
        return L"NoRemoteScript";
      default:
        result = L"NoPhysicalDir";
        if ( a1 != 0x8000 )
          return 0;
        break;
    }
  }
  else if ( a1 == 128 )
  {
    return L"MapCliCert";
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
              v6 = v5 - 16;
              if ( v6 )
              {
                if ( v6 == 32 )
                  return L"ReqCliCert";
                else
                  return 0;
              }
              else
              {
                return L"CliCert";
              }
            }
            else
            {
              return L"Source";
            }
          }
          else
          {
            return L"SSL";
          }
        }
        else
        {
          return L"Exec";
        }
      }
      else
      {
        return L"Write";
      }
    }
    else
    {
      return L"Read";
    }
  }
  return result;
}

```

## disassembly

```asm
0x180023524  mov     eax, 80h
0x180023529  cmp     ecx, eax
0x18002352b  ja      short loc_180023595
0x18002352d  jz      short loc_18002358D
0x18002352f  sub     ecx, 1
0x180023532  jz      short loc_180023585
0x180023534  sub     ecx, 1
0x180023537  jz      short loc_18002357D
0x180023539  sub     ecx, 2
0x18002353c  jz      short loc_180023575
0x18002353e  sub     ecx, 4
0x180023541  jz      short loc_18002356D
0x180023543  sub     ecx, 8
0x180023546  jz      short loc_180023565
0x180023548  sub     ecx, 10h
0x18002354b  jz      short loc_18002355D
0x18002354d  cmp     ecx, 20h ; ' '
0x180023550  jz      short loc_180023555
0x180023552  xor     eax, eax
0x180023554  retn
0x180023555  lea     rax, aReqclicert; "ReqCliCert"
0x18002355c  retn
0x18002355d  lea     rax, aClicert; "CliCert"
0x180023564  retn
0x180023565  lea     rax, aSource; "Source"
0x18002356c  retn
0x18002356d  lea     rax, aSsl; "SSL"
0x180023574  retn
0x180023575  lea     rax, aExec; "Exec"
0x18002357c  retn
0x18002357d  lea     rax, aWrite; "Write"
0x180023584  retn
0x180023585  lea     rax, aRead; "Read"
0x18002358c  retn
0x18002358d  lea     rax, aMapclicert; "MapCliCert"
0x180023594  retn
0x180023595  cmp     ecx, 100h
0x18002359b  jz      short loc_180023601
0x18002359d  cmp     ecx, 200h
0x1800235a3  jz      short loc_1800235F9
0x1800235a5  cmp     ecx, 400h
0x1800235ab  jz      short loc_1800235F1
0x1800235ad  cmp     ecx, 1000h
0x1800235b3  jz      short loc_1800235E9
0x1800235b5  cmp     ecx, 2000h
0x1800235bb  jz      short loc_1800235E1
0x1800235bd  cmp     ecx, 4000h
0x1800235c3  jz      short loc_1800235D9
0x1800235c5  xor     edx, edx
0x1800235c7  lea     rax, aNophysicaldir; "NoPhysicalDir"
0x1800235ce  cmp     ecx, 8000h
0x1800235d4  cmovnz  rax, rdx
0x1800235d8  retn
0x1800235d9  lea     rax, aNoremotescript; "NoRemoteScript"
0x1800235e0  retn
0x1800235e1  lea     rax, aNoremoteexec; "NoRemoteExec"
0x1800235e8  retn
0x1800235e9  lea     rax, aNoremoteread; "NoRemoteRead"
0x1800235f0  retn
0x1800235f1  lea     rax, aNoremotewrite; "NoRemoteWrite"
0x1800235f8  retn
0x1800235f9  lea     rax, aScript; "Script"
0x180023600  retn
0x180023601  lea     rax, aSsl128; "SSL128"
0x180023608  retn
```
