# IISRequestNotificationEvents::MODULE_SET_RESPONSE_ERROR_STATUS::TranslateEnumNotificationToString(IISRequestNotificationEvents::MODULE_SET_RESPONSE_ERROR_STATUS::enumNotification)

- ea: `0x1800282bc`
- end: `0x1800283ce`
- name: `?TranslateEnumNotificationToString@MODULE_SET_RESPONSE_ERROR_STATUS@IISRequestNotificationEvents@@SAPEBGW4enumNotification@12@@Z`
- size: `274`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callers

- `0x180027878`

## callees

- `0x1800282bc`

## string_xrefs

- `0x18002830d`: `RESOLVE_REQUEST_CACHE`
- `0x180028390`: `READ_ENTITY`
- `0x1800283bd`: `UPDATE_REQUEST_CACHE`
- `0x18002837d`: `MAP_PATH`

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
0x1800282bc  mov     eax, 80h
0x1800282c1  cmp     ecx, eax
0x1800282c3  ja      short loc_180028343
0x1800282c5  jz      short loc_18002833A
0x1800282c7  test    ecx, ecx
0x1800282c9  jz      short loc_180028331
0x1800282cb  sub     ecx, 1
0x1800282ce  jz      short loc_180028328
0x1800282d0  sub     ecx, 1
0x1800282d3  jz      short loc_18002831F
0x1800282d5  sub     ecx, 2
0x1800282d8  jz      short loc_180028316
0x1800282da  sub     ecx, 4
0x1800282dd  jz      short loc_18002830D
0x1800282df  sub     ecx, 8
0x1800282e2  jz      short loc_180028304
0x1800282e4  sub     ecx, 10h
0x1800282e7  jz      short loc_1800282FB
0x1800282e9  cmp     ecx, 20h ; ' '
0x1800282ec  jz      short loc_1800282F2
0x1800282ee  xor     eax, eax
0x1800282f0  retn
0x1800282f2  lea     rax, aPreExecuteRequ; "PRE_EXECUTE_REQUEST_HANDLER"
0x1800282f9  retn
0x1800282fb  lea     rax, aRequestAcquire; "REQUEST_ACQUIRE_STATE"
0x180028302  retn
0x180028304  lea     rax, aMapRequestHand; "MAP_REQUEST_HANDLER"
0x18002830b  retn
0x18002830d  lea     rax, aResolveRequest; "RESOLVE_REQUEST_CACHE"
0x180028314  retn
0x180028316  lea     rax, aAuthorizeReque; "AUTHORIZE_REQUEST"
0x18002831d  retn
0x18002831f  lea     rax, aAuthenticateRe; "AUTHENTICATE_REQUEST"
0x180028326  retn
0x180028328  lea     rax, aBeginRequest; "BEGIN_REQUEST"
0x18002832f  retn
0x180028331  lea     rax, aPreBeginReques; "PRE_BEGIN_REQUEST"
0x180028338  retn
0x18002833a  lea     rax, aExecuteRequest; "EXECUTE_REQUEST_HANDLER"
0x180028341  retn
0x180028343  cmp     ecx, 100h
0x180028349  jz      short loc_1800283C6
0x18002834b  cmp     ecx, 200h
0x180028351  jz      short loc_1800283BD
0x180028353  cmp     ecx, 400h
0x180028359  jz      short loc_1800283B4
0x18002835b  cmp     ecx, 800h
0x180028361  jz      short loc_1800283AB
0x180028363  cmp     ecx, 10000000h
0x180028369  jz      short loc_1800283A2
0x18002836b  cmp     ecx, 20000000h
0x180028371  jz      short loc_180028399
0x180028373  cmp     ecx, 40000000h
0x180028379  jz      short loc_180028390
0x18002837b  xor     edx, edx
0x18002837d  lea     rax, aMapPath; "MAP_PATH"
0x180028384  cmp     ecx, 80000000h
0x18002838a  cmovnz  rax, rdx
0x18002838e  retn
0x180028390  lea     rax, aReadEntity; "READ_ENTITY"
0x180028397  retn
0x180028399  lea     rax, aSendResponse; "SEND_RESPONSE"
0x1800283a0  retn
0x1800283a2  lea     rax, aCustomNotifica; "CUSTOM_NOTIFICATION"
0x1800283a9  retn
0x1800283ab  lea     rax, aEndRequest; "END_REQUEST"
0x1800283b2  retn
0x1800283b4  lea     rax, aLogRequest; "LOG_REQUEST"
0x1800283bb  retn
0x1800283bd  lea     rax, aUpdateRequestC; "UPDATE_REQUEST_CACHE"
0x1800283c4  retn
0x1800283c6  lea     rax, aReleaseRequest; "RELEASE_REQUEST_STATE"
0x1800283cd  retn
```
