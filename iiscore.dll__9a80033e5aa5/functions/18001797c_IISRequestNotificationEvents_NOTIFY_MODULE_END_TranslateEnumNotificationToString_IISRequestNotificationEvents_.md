# IISRequestNotificationEvents::NOTIFY_MODULE_END::TranslateEnumNotificationToString(IISRequestNotificationEvents::NOTIFY_MODULE_END::enumNotification)

- ea: `0x18001797c`
- end: `0x180017a6e`
- name: `?TranslateEnumNotificationToString@NOTIFY_MODULE_END@IISRequestNotificationEvents@@SAPEBGW4enumNotification@12@@Z`
- size: `242`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callers

- `0x180017800`
- `0x180017dcc`
- `0x180025b18`

## callees

- `0x18001797c`

## string_xrefs

- `0x1800179d2`: `RESOLVE_REQUEST_CACHE`
- `0x180017a3e`: `READ_ENTITY`
- `0x180017a66`: `UPDATE_REQUEST_CACHE`
- `0x180017a2c`: `MAP_PATH`

## pseudocode

```c
const wchar_t *__fastcall IISRequestNotificationEvents::NOTIFY_MODULE_END::TranslateEnumNotificationToString(
        unsigned int a1)
{
  unsigned int v1; // ecx
  unsigned int v2; // ecx
  unsigned int v3; // ecx
  unsigned int v4; // ecx
  unsigned int v5; // ecx
  unsigned int v6; // ecx
  unsigned int v7; // ecx
  const wchar_t *result; // rax

  if ( a1 > 0x100 )
  {
    switch ( a1 )
    {
      case 0x200u:
        return L"UPDATE_REQUEST_CACHE";
      case 0x400u:
        return L"LOG_REQUEST";
      case 0x800u:
        return L"END_REQUEST";
      case 0x10000000u:
        return L"CUSTOM_NOTIFICATION";
      case 0x20000000u:
        return L"SEND_RESPONSE";
      case 0x40000000u:
        return L"READ_ENTITY";
      default:
        result = L"MAP_PATH";
        if ( a1 != 0x80000000 )
          return 0;
        break;
    }
  }
  else if ( a1 == 256 )
  {
    return L"RELEASE_REQUEST_STATE";
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
                v7 = v6 - 32;
                if ( v7 )
                {
                  if ( v7 == 64 )
                    return L"EXECUTE_REQUEST_HANDLER";
                  else
                    return 0;
                }
                else
                {
                  return L"PRE_EXECUTE_REQUEST_HANDLER";
                }
              }
              else
              {
                return L"REQUEST_ACQUIRE_STATE";
              }
            }
            else
            {
              return L"MAP_REQUEST_HANDLER";
            }
          }
          else
          {
            return L"RESOLVE_REQUEST_CACHE";
          }
        }
        else
        {
          return L"AUTHORIZE_REQUEST";
        }
      }
      else
      {
        return L"AUTHENTICATE_REQUEST";
      }
    }
    else
    {
      return L"BEGIN_REQUEST";
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001797c  mov     eax, 100h
0x180017981  cmp     ecx, eax
0x180017983  ja      short loc_1800179FA
0x180017985  jz      short loc_1800179F2
0x180017987  sub     ecx, 1
0x18001798a  jz      short loc_1800179EA
0x18001798c  sub     ecx, 1
0x18001798f  jz      short loc_1800179E2
0x180017991  sub     ecx, 2
0x180017994  jz      short loc_1800179DA
0x180017996  sub     ecx, 4
0x180017999  jz      short loc_1800179D2
0x18001799b  sub     ecx, 8
0x18001799e  jz      short loc_1800179CA
0x1800179a0  sub     ecx, 10h
0x1800179a3  jz      short loc_1800179C2
0x1800179a5  sub     ecx, 20h ; ' '
0x1800179a8  jz      short loc_1800179BA
0x1800179aa  cmp     ecx, 40h ; '@'
0x1800179ad  jz      short loc_1800179B2
0x1800179af  xor     eax, eax
0x1800179b1  retn
0x1800179b2  lea     rax, aExecuteRequest; "EXECUTE_REQUEST_HANDLER"
0x1800179b9  retn
0x1800179ba  lea     rax, aPreExecuteRequ; "PRE_EXECUTE_REQUEST_HANDLER"
0x1800179c1  retn
0x1800179c2  lea     rax, aRequestAcquire; "REQUEST_ACQUIRE_STATE"
0x1800179c9  retn
0x1800179ca  lea     rax, aMapRequestHand; "MAP_REQUEST_HANDLER"
0x1800179d1  retn
0x1800179d2  lea     rax, aResolveRequest; "RESOLVE_REQUEST_CACHE"
0x1800179d9  retn
0x1800179da  lea     rax, aAuthorizeReque; "AUTHORIZE_REQUEST"
0x1800179e1  retn
0x1800179e2  lea     rax, aAuthenticateRe; "AUTHENTICATE_REQUEST"
0x1800179e9  retn
0x1800179ea  lea     rax, aBeginRequest; "BEGIN_REQUEST"
0x1800179f1  retn
0x1800179f2  lea     rax, aReleaseRequest; "RELEASE_REQUEST_STATE"
0x1800179f9  retn
0x1800179fa  cmp     ecx, 200h
0x180017a00  jz      short loc_180017A66
0x180017a02  cmp     ecx, 400h
0x180017a08  jz      short loc_180017A5E
0x180017a0a  cmp     ecx, 800h
0x180017a10  jz      short loc_180017A56
0x180017a12  cmp     ecx, 10000000h
0x180017a18  jz      short loc_180017A4E
0x180017a1a  cmp     ecx, 20000000h
0x180017a20  jz      short loc_180017A46
0x180017a22  cmp     ecx, 40000000h
0x180017a28  jz      short loc_180017A3E
0x180017a2a  xor     edx, edx
0x180017a2c  lea     rax, aMapPath; "MAP_PATH"
0x180017a33  cmp     ecx, 80000000h
0x180017a39  cmovnz  rax, rdx
0x180017a3d  retn
0x180017a3e  lea     rax, aReadEntity; "READ_ENTITY"
0x180017a45  retn
0x180017a46  lea     rax, aSendResponse; "SEND_RESPONSE"
0x180017a4d  retn
0x180017a4e  lea     rax, aCustomNotifica; "CUSTOM_NOTIFICATION"
0x180017a55  retn
0x180017a56  lea     rax, aEndRequest; "END_REQUEST"
0x180017a5d  retn
0x180017a5e  lea     rax, aLogRequest; "LOG_REQUEST"
0x180017a65  retn
0x180017a66  lea     rax, aUpdateRequestC; "UPDATE_REQUEST_CACHE"
0x180017a6d  retn
```
