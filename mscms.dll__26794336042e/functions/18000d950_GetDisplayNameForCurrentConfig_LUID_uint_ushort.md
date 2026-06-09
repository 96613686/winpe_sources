# GetDisplayNameForCurrentConfig(_LUID,uint,ushort *)

- ea: `0x18000d950`
- end: `0x18000dbdd`
- name: `?GetDisplayNameForCurrentConfig@@YAJU_LUID@@IPEAG@Z`
- size: `653`
- prototype: `__int64 __fastcall(struct _LUID, unsigned int, unsigned __int16 *)`
- caller_count: `5`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18004cea0`
- `0x18004d390`
- `0x18004d590`
- `0x18004d650`
- `0x18004d700`

## callees

- `0x18000d950`
- `0x18002e5f0`
- `0x18002f24c`
- `0x18002f2c4`
- `0x18002f2f4`
- `0x18002fbb0`
- `0x18004ca00`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000da14`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000db6c`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000dba0`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000dbd2`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000da14`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000db6c`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000dba0`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000dbd2`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!EnumDisplayDevicesW` at `0x18000d9f5`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!EnumDisplayDevicesW` at `0x18000d9f5`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!DisplayConfigGetDeviceInfo` at `0x18000d9ce`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!DisplayConfigGetDeviceInfo` at `0x18000d9ce`

## pseudocode

```c
__int64 __fastcall GetDisplayNameForCurrentConfig(LUID a1, UINT32 a2, unsigned __int16 *a3)
{
  __int64 result; // rax
  WCHAR *i; // r15
  wint_t v8; // di
  wint_t v9; // bx
  WCHAR *v10; // r14
  wchar_t *v11; // rsi
  __int64 v12; // rdi
  __int64 v13; // rax
  DISPLAYCONFIG_DEVICE_INFO_HEADER requestPacket; // [rsp+20h] [rbp-458h] BYREF
  WCHAR Device[8]; // [rsp+34h] [rbp-444h] BYREF
  __int128 v16; // [rsp+44h] [rbp-434h]
  __int128 v17; // [rsp+54h] [rbp-424h]
  __int128 v18; // [rsp+64h] [rbp-414h]
  _DISPLAY_DEVICEW DisplayDevice; // [rsp+80h] [rbp-3F8h] BYREF

  if ( (unsigned __int8)IsCreateDCWPresent() )
  {
    memset_0(&DisplayDevice, 0, sizeof(DisplayDevice));
    requestPacket.type = DISPLAYCONFIG_DEVICE_INFO_GET_SOURCE_NAME;
    requestPacket.size = 84;
    *(_OWORD *)Device = 0;
    requestPacket.adapterId = a1;
    v16 = 0;
    requestPacket.id = a2;
    v17 = 0;
    v18 = 0;
    if ( !DisplayConfigGetDeviceInfo(&requestPacket)
      && (DisplayDevice.cb = 840, EnumDisplayDevicesW(Device, 0, &DisplayDevice, 0)) )
    {
      for ( i = DisplayDevice.DeviceID; ; ++i )
      {
        v8 = *i;
        if ( !*i )
        {
          i = 0;
          return _o_wcscpy_s(a3, 260, i);
        }
        v9 = gszMonitorGUID[0];
        v10 = i;
        v11 = gszMonitorGUID;
        if ( iswupper(v8) )
          v8 = o_towlower_0(v8);
        if ( iswupper(v9) )
          v9 = o_towlower_0(v9);
        if ( *i )
          break;
LABEL_22:
        if ( !*v11 )
          return _o_wcscpy_s(a3, 260, i);
      }
      while ( *v11 )
      {
        if ( v8 == v9 )
        {
          v8 = v10[1];
          ++v10;
          v9 = v11[1];
          ++v11;
          if ( iswupper(v8) )
            v8 = o_towlower_0(v8);
          if ( iswupper(v9) )
            v9 = o_towlower_0(v9);
          if ( *v10 )
            continue;
        }
        goto LABEL_22;
      }
      return _o_wcscpy_s(a3, 260, i);
    }
    else
    {
      return 2147942487LL;
    }
  }
  else
  {
    memset_0(&DisplayDevice, 0, 0x3B0u);
    result = GetMonitorUniqueName(a1, a2, (struct _LUID *)&DisplayDevice);
    if ( (int)result >= 0 )
    {
      result = _o_wcscpy_s(a3, 260, gszMonitorGUID);
      if ( (int)result >= 0 )
      {
        v12 = -1;
        v13 = -1;
        do
          ++v13;
        while ( gszMonitorGUID[v13] );
        result = _o_wcscpy_s(&a3[v13], 260 - v13, L"\\");
        if ( (int)result >= 0 )
        {
          do
            ++v12;
          while ( gszMonitorGUID[v12] );
          return _o_wcscpy_s(&a3[v12 + 1], 259 - v12, &DisplayDevice.DeviceName[8]);
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000d950  push    rbx
0x18000d952  push    rbp
0x18000d953  push    rdi
0x18000d954  push    r12
0x18000d956  sub     rsp, 458h
0x18000d95d  mov     rax, cs:__security_cookie
0x18000d964  xor     rax, rsp
0x18000d967  mov     [rsp+478h+var_48], rax
0x18000d96f  mov     r12, r8
0x18000d972  mov     edi, edx
0x18000d974  mov     rbx, rcx
0x18000d977  call    IsCreateDCWPresent
0x18000d97c  xor     edx, edx; Val
0x18000d97e  test    al, al
0x18000d980  jz      loc_18000DB2B
0x18000d986  mov     r8d, 348h; Size
0x18000d98c  lea     rcx, [rsp+478h+DisplayDevice]; void *
0x18000d994  call    memset_0
0x18000d999  xorps   xmm0, xmm0
0x18000d99c  mov     [rsp+478h+requestPacket.type], 1
0x18000d9a4  lea     rcx, [rsp+478h+requestPacket]; requestPacket
0x18000d9a9  mov     [rsp+478h+requestPacket.size], 54h ; 'T'
0x18000d9b1  movups  xmmword ptr [rsp+478h+Device], xmm0
0x18000d9b6  mov     qword ptr [rsp+478h+requestPacket.adapterId.LowPart], rbx
0x18000d9bb  movups  [rsp+478h+var_434], xmm0
0x18000d9c0  mov     [rsp+478h+requestPacket.id], edi
0x18000d9c4  movups  [rsp+478h+var_424], xmm0
0x18000d9c9  movups  [rsp+478h+var_414], xmm0
0x18000d9ce  call    cs:__imp_DisplayConfigGetDeviceInfo
0x18000d9d4  test    eax, eax
0x18000d9d6  jnz     short loc_18000D9FF
0x18000d9d8  xor     r9d, r9d; dwFlags
0x18000d9db  mov     [rsp+478h+DisplayDevice.cb], 348h
0x18000d9e6  lea     r8, [rsp+478h+DisplayDevice]; lpDisplayDevice
0x18000d9ee  xor     edx, edx; iDevNum
0x18000d9f0  lea     rcx, [rsp+478h+Device]; lpDevice
0x18000d9f5  call    cs:__imp_EnumDisplayDevicesW
0x18000d9fb  test    eax, eax
0x18000d9fd  jnz     short loc_18000DA4F
0x18000d9ff  mov     eax, 80070057h
0x18000da04  jmp     short loc_18000DA32
0x18000da06  xor     r15d, r15d
0x18000da09  mov     r8, r15
0x18000da0c  mov     edx, 104h
0x18000da11  mov     rcx, r12
0x18000da14  call    cs:__imp__o_wcscpy_s
0x18000da1a  mov     r15, [rsp+478h+var_38]
0x18000da22  mov     r14, [rsp+478h+var_30]
0x18000da2a  mov     rsi, [rsp+478h+var_28]
0x18000da32  mov     rcx, [rsp+478h+var_48]
0x18000da3a  xor     rcx, rsp; StackCookie
0x18000da3d  call    __security_check_cookie
0x18000da42  add     rsp, 458h
0x18000da49  pop     r12
0x18000da4b  pop     rdi
0x18000da4c  pop     rbp
0x18000da4d  pop     rbx
0x18000da4e  retn
0x18000da4f  mov     [rsp+478h+var_28], rsi
0x18000da57  lea     rbp, gszMonitorGUID; "{4D36E96E-E325-11CE-BFC1-08002BE10318}"
0x18000da5e  mov     [rsp+478h+var_30], r14
0x18000da66  mov     [rsp+478h+var_38], r15
0x18000da6e  lea     r15, [rsp+478h+DisplayDevice.DeviceID]
0x18000da76  movzx   edi, word ptr [r15]
0x18000da7a  test    di, di
0x18000da7d  jz      short loc_18000DA06
0x18000da7f  movzx   ebx, word ptr cs:gszMonitorGUID; "{4D36E96E-E325-11CE-BFC1-08002BE10318}"
0x18000da86  movzx   ecx, di; C
0x18000da89  mov     r14, r15
0x18000da8c  mov     rsi, rbp
0x18000da8f  call    iswupper
0x18000da94  test    eax, eax
0x18000da96  jz      short loc_18000DAA3
0x18000da98  movzx   ecx, di
0x18000da9b  call    _o_towlower_0
0x18000daa0  movzx   edi, ax
0x18000daa3  movzx   ecx, bx; C
0x18000daa6  call    iswupper
0x18000daab  test    eax, eax
0x18000daad  jnz     short loc_18000DB1E
0x18000daaf  cmp     word ptr [r15], 0
0x18000dab4  jz      short loc_18000DB0B
0x18000dab6  cmp     word ptr [rsi], 0
0x18000daba  jz      loc_18000DA09
0x18000dac0  cmp     di, bx
0x18000dac3  jnz     short loc_18000DB0B
0x18000dac5  movzx   edi, word ptr [r14+2]
0x18000daca  add     r14, 2
0x18000dace  movzx   ebx, word ptr [rsi+2]
0x18000dad2  add     rsi, 2
0x18000dad6  movzx   ecx, di; C
0x18000dad9  call    iswupper
0x18000dade  test    eax, eax
0x18000dae0  jz      short loc_18000DAED
0x18000dae2  movzx   ecx, di
0x18000dae5  call    _o_towlower_0
0x18000daea  movzx   edi, ax
0x18000daed  movzx   ecx, bx; C
0x18000daf0  call    iswupper
0x18000daf5  test    eax, eax
0x18000daf7  jz      short loc_18000DB04
0x18000daf9  movzx   ecx, bx
0x18000dafc  call    _o_towlower_0
0x18000db01  movzx   ebx, ax
0x18000db04  cmp     word ptr [r14], 0
0x18000db09  jnz     short loc_18000DAB6
0x18000db0b  cmp     word ptr [rsi], 0
0x18000db0f  jz      loc_18000DA09
0x18000db15  add     r15, 2
0x18000db19  jmp     loc_18000DA76
0x18000db1e  movzx   ecx, bx
0x18000db21  call    _o_towlower_0
0x18000db26  movzx   ebx, ax
0x18000db29  jmp     short loc_18000DAAF
0x18000db2b  mov     r8d, 3B0h; Size
0x18000db31  lea     rcx, [rsp+478h+DisplayDevice]; void *
0x18000db39  call    memset_0
0x18000db3e  lea     r8, [rsp+478h+DisplayDevice]; struct _DISPLAYCONFIG_GET_MONITOR_INTERNAL_INFO *
0x18000db46  mov     edx, edi; unsigned int
0x18000db48  mov     rcx, rbx; struct _LUID
0x18000db4b  call    ?GetMonitorUniqueName@@YAJU_LUID@@IAEAU_DISPLAYCONFIG_GET_MONITOR_INTERNAL_INFO@@@Z; GetMonitorUniqueName(_LUID,uint,_DISPLAYCONFIG_GET_MONITOR_INTERNAL_INFO &)
0x18000db50  test    eax, eax
0x18000db52  js      loc_18000DA32
0x18000db58  lea     rbp, gszMonitorGUID; "{4D36E96E-E325-11CE-BFC1-08002BE10318}"
0x18000db5f  mov     ebx, 104h
0x18000db64  mov     r8, rbp
0x18000db67  mov     edx, ebx
0x18000db69  mov     rcx, r12
0x18000db6c  call    cs:__imp__o_wcscpy_s
0x18000db72  test    eax, eax
0x18000db74  js      loc_18000DA32
0x18000db7a  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x18000db81  mov     rax, rdi
0x18000db84  inc     rax
0x18000db87  cmp     word ptr [rbp+rax*2+0], 0
0x18000db8d  jnz     short loc_18000DB84
0x18000db8f  sub     rbx, rax
0x18000db92  lea     rcx, [r12+rax*2]
0x18000db96  mov     rdx, rbx
0x18000db99  lea     r8, StringValue; "\\"
0x18000dba0  call    cs:__imp__o_wcscpy_s
0x18000dba6  test    eax, eax
0x18000dba8  js      loc_18000DA32
0x18000dbae  inc     rdi
0x18000dbb1  cmp     word ptr [rbp+rdi*2+0], 0
0x18000dbb7  jnz     short loc_18000DBAE
0x18000dbb9  mov     edx, 103h
0x18000dbbe  lea     rcx, [r12+2]
0x18000dbc3  sub     rdx, rdi
0x18000dbc6  lea     rcx, [rcx+rdi*2]
0x18000dbca  lea     r8, [rsp+478h+DisplayDevice.DeviceName+10h]
0x18000dbd2  call    cs:__imp__o_wcscpy_s
0x18000dbd8  jmp     loc_18000DA32
```
