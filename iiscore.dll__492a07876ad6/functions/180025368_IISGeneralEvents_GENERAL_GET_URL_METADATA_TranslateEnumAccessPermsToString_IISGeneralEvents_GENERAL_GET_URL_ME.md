# IISGeneralEvents::GENERAL_GET_URL_METADATA::TranslateEnumAccessPermsToString(IISGeneralEvents::GENERAL_GET_URL_METADATA::enumAccessPerms)

- ea: `0x180025368`
- end: `0x18002545c`
- name: `?TranslateEnumAccessPermsToString@GENERAL_GET_URL_METADATA@IISGeneralEvents@@SAPEBGW4enumAccessPerms@12@@Z`
- size: `244`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18002355c`

## callees

- `0x180025368`

## string_xrefs

- `0x1800253c7`: `Write`
- `0x180025442`: `NoRemoteWrite`
- `0x180025439`: `NoRemoteRead`

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
0x180025368  mov     eax, 80h
0x18002536d  cmp     ecx, eax
0x18002536f  ja      short loc_1800253E2
0x180025371  jz      short loc_1800253D9
0x180025373  sub     ecx, 1
0x180025376  jz      short loc_1800253D0
0x180025378  sub     ecx, 1
0x18002537b  jz      short loc_1800253C7
0x18002537d  sub     ecx, 2
0x180025380  jz      short loc_1800253BE
0x180025382  sub     ecx, 4
0x180025385  jz      short loc_1800253B5
0x180025387  sub     ecx, 8
0x18002538a  jz      short loc_1800253AC
0x18002538c  sub     ecx, 10h
0x18002538f  jz      short loc_1800253A3
0x180025391  cmp     ecx, 20h ; ' '
0x180025394  jz      short loc_18002539A
0x180025396  xor     eax, eax
0x180025398  retn
0x18002539a  lea     rax, aReqclicert; "ReqCliCert"
0x1800253a1  retn
0x1800253a3  lea     rax, aClicert; "CliCert"
0x1800253aa  retn
0x1800253ac  lea     rax, aSource; "Source"
0x1800253b3  retn
0x1800253b5  lea     rax, aSsl; "SSL"
0x1800253bc  retn
0x1800253be  lea     rax, aExec; "Exec"
0x1800253c5  retn
0x1800253c7  lea     rax, aWrite; "Write"
0x1800253ce  retn
0x1800253d0  lea     rax, aRead; "Read"
0x1800253d7  retn
0x1800253d9  lea     rax, aMapclicert; "MapCliCert"
0x1800253e0  retn
0x1800253e2  cmp     ecx, 100h
0x1800253e8  jz      short loc_180025454
0x1800253ea  cmp     ecx, 200h
0x1800253f0  jz      short loc_18002544B
0x1800253f2  cmp     ecx, 400h
0x1800253f8  jz      short loc_180025442
0x1800253fa  cmp     ecx, 1000h
0x180025400  jz      short loc_180025439
0x180025402  cmp     ecx, 2000h
0x180025408  jz      short loc_180025430
0x18002540a  cmp     ecx, 4000h
0x180025410  jz      short loc_180025427
0x180025412  xor     edx, edx
0x180025414  lea     rax, aNophysicaldir; "NoPhysicalDir"
0x18002541b  cmp     ecx, 8000h
0x180025421  cmovnz  rax, rdx
0x180025425  retn
0x180025427  lea     rax, aNoremotescript; "NoRemoteScript"
0x18002542e  retn
0x180025430  lea     rax, aNoremoteexec; "NoRemoteExec"
0x180025437  retn
0x180025439  lea     rax, aNoremoteread; "NoRemoteRead"
0x180025440  retn
0x180025442  lea     rax, aNoremotewrite; "NoRemoteWrite"
0x180025449  retn
0x18002544b  lea     rax, aScript; "Script"
0x180025452  retn
0x180025454  lea     rax, aSsl128; "SSL128"
0x18002545b  retn
```
