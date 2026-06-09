# IISRequestNotificationEvents::MODULE_SET_RESPONSE_ERROR_STATUS::TranslateEnumNotificationToString(IISRequestNotificationEvents::MODULE_SET_RESPONSE_ERROR_STATUS::enumNotification)

- ea: `0x180026294`
- end: `0x180026395`
- name: `?TranslateEnumNotificationToString@MODULE_SET_RESPONSE_ERROR_STATUS@IISRequestNotificationEvents@@SAPEBGW4enumNotification@12@@Z`
- size: `257`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callers

- `0x18002589c`

## callees

- `0x180026294`

## string_xrefs

- `0x1800262e1`: `RESOLVE_REQUEST_CACHE`
- `0x18002635d`: `READ_ENTITY`
- `0x180026385`: `UPDATE_REQUEST_CACHE`
- `0x18002634b`: `MAP_PATH`

## pseudocode

```c
const wchar_t *__fastcall IISRequestNotificationEvents::MODULE_SET_RESPONSE_ERROR_STATUS::TranslateEnumNotificationToString(
        unsigned int a1)
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
        return L"RELEASE_REQUEST_STATE";
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
  else if ( a1 == 128 )
  {
    return L"EXECUTE_REQUEST_HANDLER";
  }
  else if ( a1 )
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
                  return L"PRE_EXECUTE_REQUEST_HANDLER";
                else
                  return 0;
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
  else
  {
    return L"PRE_BEGIN_REQUEST";
  }
  return result;
}

```

## disassembly

```asm
0x180026294  mov     eax, 80h
0x180026299  cmp     ecx, eax
0x18002629b  ja      short loc_180026311
0x18002629d  jz      short loc_180026309
0x18002629f  test    ecx, ecx
0x1800262a1  jz      short loc_180026301
0x1800262a3  sub     ecx, 1
0x1800262a6  jz      short loc_1800262F9
0x1800262a8  sub     ecx, 1
0x1800262ab  jz      short loc_1800262F1
0x1800262ad  sub     ecx, 2
0x1800262b0  jz      short loc_1800262E9
0x1800262b2  sub     ecx, 4
0x1800262b5  jz      short loc_1800262E1
0x1800262b7  sub     ecx, 8
0x1800262ba  jz      short loc_1800262D9
0x1800262bc  sub     ecx, 10h
0x1800262bf  jz      short loc_1800262D1
0x1800262c1  cmp     ecx, 20h ; ' '
0x1800262c4  jz      short loc_1800262C9
0x1800262c6  xor     eax, eax
0x1800262c8  retn
0x1800262c9  lea     rax, aPreExecuteRequ; "PRE_EXECUTE_REQUEST_HANDLER"
0x1800262d0  retn
0x1800262d1  lea     rax, aRequestAcquire; "REQUEST_ACQUIRE_STATE"
0x1800262d8  retn
0x1800262d9  lea     rax, aMapRequestHand; "MAP_REQUEST_HANDLER"
0x1800262e0  retn
0x1800262e1  lea     rax, aResolveRequest; "RESOLVE_REQUEST_CACHE"
0x1800262e8  retn
0x1800262e9  lea     rax, aAuthorizeReque; "AUTHORIZE_REQUEST"
0x1800262f0  retn
0x1800262f1  lea     rax, aAuthenticateRe; "AUTHENTICATE_REQUEST"
0x1800262f8  retn
0x1800262f9  lea     rax, aBeginRequest; "BEGIN_REQUEST"
0x180026300  retn
0x180026301  lea     rax, aPreBeginReques; "PRE_BEGIN_REQUEST"
0x180026308  retn
0x180026309  lea     rax, aExecuteRequest; "EXECUTE_REQUEST_HANDLER"
0x180026310  retn
0x180026311  cmp     ecx, 100h
0x180026317  jz      short loc_18002638D
0x180026319  cmp     ecx, 200h
0x18002631f  jz      short loc_180026385
0x180026321  cmp     ecx, 400h
0x180026327  jz      short loc_18002637D
0x180026329  cmp     ecx, 800h
0x18002632f  jz      short loc_180026375
0x180026331  cmp     ecx, 10000000h
0x180026337  jz      short loc_18002636D
0x180026339  cmp     ecx, 20000000h
0x18002633f  jz      short loc_180026365
0x180026341  cmp     ecx, 40000000h
0x180026347  jz      short loc_18002635D
0x180026349  xor     edx, edx
0x18002634b  lea     rax, aMapPath; "MAP_PATH"
0x180026352  cmp     ecx, 80000000h
0x180026358  cmovnz  rax, rdx
0x18002635c  retn
0x18002635d  lea     rax, aReadEntity; "READ_ENTITY"
0x180026364  retn
0x180026365  lea     rax, aSendResponse; "SEND_RESPONSE"
0x18002636c  retn
0x18002636d  lea     rax, aCustomNotifica; "CUSTOM_NOTIFICATION"
0x180026374  retn
0x180026375  lea     rax, aEndRequest; "END_REQUEST"
0x18002637c  retn
0x18002637d  lea     rax, aLogRequest; "LOG_REQUEST"
0x180026384  retn
0x180026385  lea     rax, aUpdateRequestC; "UPDATE_REQUEST_CACHE"
0x18002638c  retn
0x18002638d  lea     rax, aReleaseRequest; "RELEASE_REQUEST_STATE"
0x180026394  retn
```
