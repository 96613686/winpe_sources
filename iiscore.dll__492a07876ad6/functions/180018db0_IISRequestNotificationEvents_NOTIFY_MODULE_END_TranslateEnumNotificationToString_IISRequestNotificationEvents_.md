# IISRequestNotificationEvents::NOTIFY_MODULE_END::TranslateEnumNotificationToString(IISRequestNotificationEvents::NOTIFY_MODULE_END::enumNotification)

- ea: `0x180018db0`
- end: `0x180018eb2`
- name: `?TranslateEnumNotificationToString@NOTIFY_MODULE_END@IISRequestNotificationEvents@@SAPEBGW4enumNotification@12@@Z`
- size: `258`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callers

- `0x180018c34`
- `0x18001924c`
- `0x180027af4`

## callees

- `0x180018db0`

## string_xrefs

- `0x180018e0b`: `RESOLVE_REQUEST_CACHE`
- `0x180018e7d`: `READ_ENTITY`
- `0x180018eaa`: `UPDATE_REQUEST_CACHE`
- `0x180018e6a`: `MAP_PATH`

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
0x180018db0  mov     eax, 100h
0x180018db5  cmp     ecx, eax
0x180018db7  ja      short loc_180018E38
0x180018db9  jz      short loc_180018E2F
0x180018dbb  sub     ecx, 1
0x180018dbe  jz      short loc_180018E26
0x180018dc0  sub     ecx, 1
0x180018dc3  jz      short loc_180018E1D
0x180018dc5  sub     ecx, 2
0x180018dc8  jz      short loc_180018E14
0x180018dca  sub     ecx, 4
0x180018dcd  jz      short loc_180018E0B
0x180018dcf  sub     ecx, 8
0x180018dd2  jz      short loc_180018E02
0x180018dd4  sub     ecx, 10h
0x180018dd7  jz      short loc_180018DF9
0x180018dd9  sub     ecx, 20h ; ' '
0x180018ddc  jz      short loc_180018DF0
0x180018dde  cmp     ecx, 40h ; '@'
0x180018de1  jz      short loc_180018DE7
0x180018de3  xor     eax, eax
0x180018de5  retn
0x180018de7  lea     rax, aExecuteRequest; "EXECUTE_REQUEST_HANDLER"
0x180018dee  retn
0x180018df0  lea     rax, aPreExecuteRequ; "PRE_EXECUTE_REQUEST_HANDLER"
0x180018df7  retn
0x180018df9  lea     rax, aRequestAcquire; "REQUEST_ACQUIRE_STATE"
0x180018e00  retn
0x180018e02  lea     rax, aMapRequestHand; "MAP_REQUEST_HANDLER"
0x180018e09  retn
0x180018e0b  lea     rax, aResolveRequest; "RESOLVE_REQUEST_CACHE"
0x180018e12  retn
0x180018e14  lea     rax, aAuthorizeReque; "AUTHORIZE_REQUEST"
0x180018e1b  retn
0x180018e1d  lea     rax, aAuthenticateRe; "AUTHENTICATE_REQUEST"
0x180018e24  retn
0x180018e26  lea     rax, aBeginRequest; "BEGIN_REQUEST"
0x180018e2d  retn
0x180018e2f  lea     rax, aReleaseRequest; "RELEASE_REQUEST_STATE"
0x180018e36  retn
0x180018e38  cmp     ecx, 200h
0x180018e3e  jz      short loc_180018EAA
0x180018e40  cmp     ecx, 400h
0x180018e46  jz      short loc_180018EA1
0x180018e48  cmp     ecx, 800h
0x180018e4e  jz      short loc_180018E98
0x180018e50  cmp     ecx, 10000000h
0x180018e56  jz      short loc_180018E8F
0x180018e58  cmp     ecx, 20000000h
0x180018e5e  jz      short loc_180018E86
0x180018e60  cmp     ecx, 40000000h
0x180018e66  jz      short loc_180018E7D
0x180018e68  xor     edx, edx
0x180018e6a  lea     rax, aMapPath; "MAP_PATH"
0x180018e71  cmp     ecx, 80000000h
0x180018e77  cmovnz  rax, rdx
0x180018e7b  retn
0x180018e7d  lea     rax, aReadEntity; "READ_ENTITY"
0x180018e84  retn
0x180018e86  lea     rax, aSendResponse; "SEND_RESPONSE"
0x180018e8d  retn
0x180018e8f  lea     rax, aCustomNotifica; "CUSTOM_NOTIFICATION"
0x180018e96  retn
0x180018e98  lea     rax, aEndRequest; "END_REQUEST"
0x180018e9f  retn
0x180018ea1  lea     rax, aLogRequest; "LOG_REQUEST"
0x180018ea8  retn
0x180018eaa  lea     rax, aUpdateRequestC; "UPDATE_REQUEST_CACHE"
0x180018eb1  retn
```
