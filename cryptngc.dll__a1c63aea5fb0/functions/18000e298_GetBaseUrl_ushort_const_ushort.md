# GetBaseUrl(ushort const *,ushort * *)

- ea: `0x18000e298`
- end: `0x18000e40e`
- name: `?GetBaseUrl@@YAJPEBGPEAPEAG@Z`
- size: `374`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18000e248`
- `0x18004509c`

## callees

- `0x18000bfc0`
- `0x18000c190`
- `0x18000ced0`
- `0x18000e298`
- `0x180027448`
- `0x1800274cc`
- `0x180046ce0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18000e3b3`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18000e3ce`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18000e3b3`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18000e3ce`

## string_xrefs

- `0x18000e34f`: `Logger::WriteNullOrEmptyParameterFailureEvent`
- `0x18000e348`: `EventWriteNullOrEmptyParameterFailureEvent`

## pseudocode

```c
__int64 __fastcall GetBaseUrl(const unsigned __int16 *a1, unsigned __int16 **a2, int a3)
{
  unsigned __int16 *v4; // rbx
  unsigned int v5; // edi
  __int64 v6; // r8
  ULONG v7; // eax
  int v8; // eax
  const wchar_t *v9; // rcx
  wchar_t *v10; // rax
  wchar_t *v11; // rax
  unsigned __int16 *v13; // [rsp+30h] [rbp-58h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v14; // [rsp+38h] [rbp-50h] BYREF
  const wchar_t *v15; // [rsp+48h] [rbp-40h]
  __int64 v16; // [rsp+50h] [rbp-38h]
  const wchar_t *v17; // [rsp+58h] [rbp-30h]
  __int64 v18; // [rsp+60h] [rbp-28h]

  v4 = 0;
  v13 = 0;
  if ( a2 )
  {
    *a2 = 0;
    v8 = StringDup(a1, &v13, a3);
    v5 = v8;
    if ( v8 >= 0 )
    {
      v4 = v13;
      if ( !(unsigned int)IsEmptyString(v13) )
      {
        v10 = wcsstr(v9, L"://");
        if ( v10 )
        {
          if ( v10[3] )
          {
            v11 = wcsstr(v10 + 3, L"/");
            if ( v11 )
              *v11 = 0;
            *a2 = v4;
            v4 = 0;
          }
        }
      }
    }
    else
    {
      Logger::TraceError(L"%s: %s failed with error code: 0x%08x.", L"GetBaseUrl", L"StringDup", (unsigned int)v8);
      v4 = v13;
    }
  }
  else
  {
    v5 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"GetBaseUrl", L"baseUrl");
    if ( (Microsoft_Windows_User_Device_RegistrationEnableBits & 2) != 0 )
    {
      v15 = L"GetBaseUrl";
      v16 = 22;
      v17 = L"baseUrl";
      v18 = 16;
      v7 = McGenEventWrite_EventWriteTransfer(
             (REGHANDLE *)&UserDeviceRegistrationEventProvider_Context,
             (const EVENT_DESCRIPTOR *)NullOrEmptyParameterFailureEvent,
             v6,
             3u,
             &v14);
      if ( v7 )
        Logger::TraceError(
          L"%s: %s failed with win32 error code: 0x%08x.",
          L"Logger::WriteNullOrEmptyParameterFailureEvent",
          L"EventWriteNullOrEmptyParameterFailureEvent",
          v7);
    }
  }
  SafeFree(v4);
  return v5;
}

```

## disassembly

```asm
0x18000e298  mov     [rsp+arg_10], rbx
0x18000e29d  mov     [rsp+arg_18], rbp
0x18000e2a2  push    rsi
0x18000e2a3  push    rdi
0x18000e2a4  push    r14
0x18000e2a6  sub     rsp, 70h
0x18000e2aa  mov     rax, cs:__security_cookie
0x18000e2b1  xor     rax, rsp
0x18000e2b4  mov     [rsp+88h+var_20], rax
0x18000e2b9  xor     ebp, ebp
0x18000e2bb  mov     rsi, rdx
0x18000e2be  mov     ebx, ebp
0x18000e2c0  mov     [rsp+88h+var_58], rbx
0x18000e2c5  test    rdx, rdx
0x18000e2c8  jnz     loc_18000E364
0x18000e2ce  lea     r14, aBaseurl; "baseUrl"
0x18000e2d5  mov     edi, 80070057h
0x18000e2da  lea     rsi, aGetbaseurl; "GetBaseUrl"
0x18000e2e1  mov     r8, r14
0x18000e2e4  mov     rdx, rsi
0x18000e2e7  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x18000e2ee  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000e2f3  test    cs:Microsoft_Windows_User_Device_RegistrationEnableBits, 2
0x18000e2fa  jz      loc_18000E3E2
0x18000e300  lea     rax, [rsp+88h+var_50]
0x18000e305  mov     [rsp+88h+var_40], rsi
0x18000e30a  lea     r9d, [rbp+3]
0x18000e30e  mov     [rsp+88h+var_68], rax
0x18000e313  lea     rdx, NullOrEmptyParameterFailureEvent
0x18000e31a  mov     [rsp+88h+var_38], 16h
0x18000e323  lea     rcx, UserDeviceRegistrationEventProvider_Context
0x18000e32a  mov     [rsp+88h+var_30], r14
0x18000e32f  mov     [rsp+88h+var_28], 10h
0x18000e338  call    McGenEventWrite_EventWriteTransfer
0x18000e33d  test    eax, eax
0x18000e33f  jz      loc_18000E3E2
0x18000e345  mov     r9d, eax
0x18000e348  lea     r8, aEventwritenull; "EventWriteNullOrEmptyParameterFailureEv"...
0x18000e34f  lea     rdx, aLoggerWritenul; "Logger::WriteNullOrEmptyParameterFailur"...
0x18000e356  lea     rcx, aSSFailedWithWi; "%s: %s failed with win32 error code: 0x"...
0x18000e35d  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000e362  jmp     short loc_18000E3E2
0x18000e364  mov     [rdx], rbp
0x18000e367  lea     rdx, [rsp+88h+var_58]; unsigned __int16 **
0x18000e36c  call    ?StringDup@@YAJPEBGPEAPEAGH@Z; StringDup(ushort const *,ushort * *,int)
0x18000e371  mov     edi, eax
0x18000e373  test    eax, eax
0x18000e375  jns     short loc_18000E39B
0x18000e377  mov     r9d, eax
0x18000e37a  lea     r8, aStringdup; "StringDup"
0x18000e381  lea     rdx, aGetbaseurl; "GetBaseUrl"
0x18000e388  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x18000e38f  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x18000e394  mov     rbx, [rsp+88h+var_58]
0x18000e399  jmp     short loc_18000E3E2
0x18000e39b  mov     rbx, [rsp+88h+var_58]
0x18000e3a0  mov     rcx, rbx; unsigned __int16 *
0x18000e3a3  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x18000e3a8  test    eax, eax
0x18000e3aa  jnz     short loc_18000E3E2
0x18000e3ac  lea     rdx, SubStr; "://"
0x18000e3b3  call    cs:__imp_wcsstr
0x18000e3b9  test    rax, rax
0x18000e3bc  jz      short loc_18000E3E2
0x18000e3be  lea     rcx, [rax+6]; Str
0x18000e3c2  cmp     [rcx], bp
0x18000e3c5  jz      short loc_18000E3E2
0x18000e3c7  lea     rdx, asc_180056A78; "/"
0x18000e3ce  call    cs:__imp_wcsstr
0x18000e3d4  test    rax, rax
0x18000e3d7  jz      short loc_18000E3DC
0x18000e3d9  mov     [rax], bp
0x18000e3dc  mov     [rsi], rbx
0x18000e3df  mov     rbx, rbp
0x18000e3e2  mov     rcx, rbx; lpMem
0x18000e3e5  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x18000e3ea  mov     eax, edi
0x18000e3ec  mov     rcx, [rsp+88h+var_20]
0x18000e3f1  xor     rcx, rsp; StackCookie
0x18000e3f4  call    __security_check_cookie
0x18000e3f9  lea     r11, [rsp+88h+var_18]
0x18000e3fe  mov     rbx, [r11+30h]
0x18000e402  mov     rbp, [r11+38h]
0x18000e406  mov     rsp, r11
0x18000e409  pop     r14
0x18000e40b  pop     rdi
0x18000e40c  pop     rsi
0x18000e40d  retn
```
