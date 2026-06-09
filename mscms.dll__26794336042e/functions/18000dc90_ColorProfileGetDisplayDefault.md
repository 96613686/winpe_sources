# ColorProfileGetDisplayDefault

- ea: `0x18000dc90`
- end: `0x18000e050`
- name: `ColorProfileGetDisplayDefault`
- size: `960`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config`

## callees

- `0x18000dc90`
- `0x18000e184`
- `0x18002e5f0`
- `0x18002f24c`
- `0x18002f2c4`
- `0x18002f2f4`
- `0x18002fbb0`
- `0x18004ca00`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000dd85`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000dfab`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000dfe8`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000e01a`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000dd85`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000dfab`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000dfe8`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000e01a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dec5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000df42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dec5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000df42`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000def8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000def8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e045`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e045`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!EnumDisplayDevicesW` at `0x18000dd62`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!EnumDisplayDevicesW` at `0x18000dd62`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!DisplayConfigGetDeviceInfo` at `0x18000dd43`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!DisplayConfigGetDeviceInfo` at `0x18000dd43`

## pseudocode

```c
__int64 __fastcall ColorProfileGetDisplayDefault(
        enum WCS_PROFILE_MANAGEMENT_SCOPE a1,
        LUID a2,
        UINT32 a3,
        enum COLORPROFILETYPE a4,
        enum COLORPROFILESUBTYPE a5,
        unsigned __int16 **a6)
{
  enum WCS_PROFILE_MANAGEMENT_SCOPE v8; // r14d
  WCHAR *i; // r15
  int v11; // eax
  int MonitorUniqueName; // ebx
  wint_t v13; // di
  wint_t v14; // bx
  WCHAR *v15; // r14
  wchar_t *v16; // rsi
  enum COLORPROFILETYPE v17; // r15d
  unsigned __int16 *v18; // rdi
  signed int LastError; // eax
  __int64 v20; // rsi
  __int64 v21; // rax
  unsigned int v22; // [rsp+40h] [rbp-C0h] BYREF
  enum WCS_PROFILE_MANAGEMENT_SCOPE v23; // [rsp+44h] [rbp-BCh]
  enum COLORPROFILETYPE v24; // [rsp+48h] [rbp-B8h]
  DISPLAYCONFIG_DEVICE_INFO_HEADER requestPacket; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Device[8]; // [rsp+64h] [rbp-9Ch] BYREF
  __int128 v27; // [rsp+74h] [rbp-8Ch]
  __int128 v28; // [rsp+84h] [rbp-7Ch]
  __int128 v29; // [rsp+94h] [rbp-6Ch]
  struct _DISPLAY_DEVICEW DisplayDevice; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 v31[264]; // [rsp+460h] [rbp+360h] BYREF

  v23 = a1;
  v8 = a1;
  v24 = a4;
  v22 = 0;
  memset_0(v31, 0, 0x208u);
  if ( (unsigned __int8)IsCreateDCWPresent() )
  {
    memset_0(&DisplayDevice, 0, sizeof(DisplayDevice));
    requestPacket.type = DISPLAYCONFIG_DEVICE_INFO_GET_SOURCE_NAME;
    requestPacket.size = 84;
    *(_OWORD *)Device = 0;
    requestPacket.adapterId = a2;
    v27 = 0;
    requestPacket.id = a3;
    v28 = 0;
    v29 = 0;
    if ( DisplayConfigGetDeviceInfo(&requestPacket) )
      return 2147942487LL;
    DisplayDevice.cb = 840;
    if ( !EnumDisplayDevicesW(Device, 0, &DisplayDevice, 0) )
      return 2147942487LL;
    for ( i = DisplayDevice.DeviceID; ; ++i )
    {
      v13 = *i;
      if ( !*i )
      {
        i = 0;
        goto LABEL_6;
      }
      v14 = gszMonitorGUID[0];
      v15 = i;
      v16 = gszMonitorGUID;
      if ( iswupper(v13) )
        v13 = o_towlower_0(v13);
      if ( iswupper(v14) )
        v14 = o_towlower_0(v14);
      if ( *i )
        break;
LABEL_24:
      if ( !*v16 )
        goto LABEL_6;
    }
    while ( *v16 )
    {
      if ( v13 == v14 )
      {
        v13 = v15[1];
        ++v15;
        v14 = v16[1];
        ++v16;
        if ( iswupper(v13) )
          v13 = o_towlower_0(v13);
        if ( iswupper(v14) )
          v14 = o_towlower_0(v14);
        if ( *v15 )
          continue;
      }
      goto LABEL_24;
    }
LABEL_6:
    v11 = _o_wcscpy_s(v31, 260, i);
    v8 = v23;
    goto LABEL_7;
  }
  memset_0(&DisplayDevice, 0, 0x3B0u);
  MonitorUniqueName = GetMonitorUniqueName(a2, a3, (struct _LUID *)&DisplayDevice);
  if ( MonitorUniqueName >= 0 )
  {
    MonitorUniqueName = _o_wcscpy_s(v31, 260, gszMonitorGUID);
    if ( MonitorUniqueName >= 0 )
    {
      v20 = -1;
      v21 = -1;
      do
        ++v21;
      while ( gszMonitorGUID[v21] );
      MonitorUniqueName = _o_wcscpy_s(&v31[v21], 260 - v21, L"\\");
      if ( MonitorUniqueName >= 0 )
      {
        do
          ++v20;
        while ( gszMonitorGUID[v20] );
        v11 = _o_wcscpy_s(&v31[v20 + 1], 259 - v20, &DisplayDevice.DeviceName[8]);
LABEL_7:
        MonitorUniqueName = v11;
      }
    }
  }
  if ( MonitorUniqueName < 0 )
    return (unsigned int)MonitorUniqueName;
  v17 = v24;
  if ( !(unsigned int)InternalGetDefaultColorProfile(v8, v31, v24, a5, 0, 0, &v22, 1) )
  {
    v18 = 0;
    LastError = GetLastError();
    MonitorUniqueName = LastError;
    if ( LastError <= 0 )
      goto LABEL_28;
    goto LABEL_34;
  }
  if ( !v22 )
    return 2147944415LL;
  v18 = (unsigned __int16 *)LocalAlloc(0x40u, 2LL * v22);
  if ( v18 )
  {
    if ( (unsigned int)InternalGetDefaultColorProfile(v8, v31, v17, a5, 0, v18, &v22, 1) )
    {
LABEL_29:
      *a6 = v18;
      return (unsigned int)MonitorUniqueName;
    }
    LastError = GetLastError();
    MonitorUniqueName = LastError;
    if ( LastError <= 0 )
    {
LABEL_28:
      if ( MonitorUniqueName < 0 )
      {
        if ( v18 )
          LocalFree(v18);
        return (unsigned int)MonitorUniqueName;
      }
      goto LABEL_29;
    }
LABEL_34:
    MonitorUniqueName = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_28;
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x18000dc90  push    rbp
0x18000dc92  push    rbx
0x18000dc93  push    rsi
0x18000dc94  push    rdi
0x18000dc95  push    r12
0x18000dc97  push    r13
0x18000dc99  push    r14
0x18000dc9b  push    r15
0x18000dc9d  lea     rbp, [rsp-588h]
0x18000dca5  sub     rsp, 688h
0x18000dcac  mov     rax, cs:__security_cookie
0x18000dcb3  xor     rax, rsp
0x18000dcb6  mov     [rbp+5C0h+var_50], rax
0x18000dcbd  mov     r13, [rbp+5C0h+arg_28]
0x18000dcc4  mov     edi, r8d
0x18000dcc7  mov     rbx, rdx
0x18000dcca  mov     [rsp+6C0h+var_67C], ecx
0x18000dcce  mov     r14d, ecx
0x18000dcd1  mov     [rsp+6C0h+var_678], r9d
0x18000dcd6  xor     edx, edx; Val
0x18000dcd8  mov     [rsp+6C0h+var_680], 0
0x18000dce0  mov     r8d, 208h; Size
0x18000dce6  lea     rcx, [rbp+5C0h+var_260]; void *
0x18000dced  call    memset_0
0x18000dcf2  call    IsCreateDCWPresent
0x18000dcf7  xor     edx, edx; Val
0x18000dcf9  test    al, al
0x18000dcfb  jz      loc_18000DF6C
0x18000dd01  mov     r8d, 348h; Size
0x18000dd07  lea     rcx, [rbp+5C0h+DisplayDevice]; void *
0x18000dd0b  call    memset_0
0x18000dd10  xorps   xmm0, xmm0
0x18000dd13  mov     [rsp+6C0h+requestPacket.type], 1
0x18000dd1b  lea     rcx, [rsp+6C0h+requestPacket]; requestPacket
0x18000dd20  mov     [rsp+6C0h+requestPacket.size], 54h ; 'T'
0x18000dd28  movups  xmmword ptr [rsp+6C0h+Device], xmm0
0x18000dd2d  mov     qword ptr [rsp+6C0h+requestPacket.adapterId.LowPart], rbx
0x18000dd32  movups  [rsp+6C0h+var_64C], xmm0
0x18000dd37  mov     [rsp+6C0h+requestPacket.id], edi
0x18000dd3b  movups  [rbp+5C0h+var_63C], xmm0
0x18000dd3f  movups  [rbp+5C0h+var_62C], xmm0
0x18000dd43  call    cs:__imp_DisplayConfigGetDeviceInfo
0x18000dd49  test    eax, eax
0x18000dd4b  jnz     short loc_18000DD6C
0x18000dd4d  xor     r9d, r9d; dwFlags
0x18000dd50  mov     [rbp+5C0h+DisplayDevice.cb], 348h
0x18000dd57  lea     r8, [rbp+5C0h+DisplayDevice]; lpDisplayDevice
0x18000dd5b  xor     edx, edx; iDevNum
0x18000dd5d  lea     rcx, [rsp+6C0h+Device]; lpDevice
0x18000dd62  call    cs:__imp_EnumDisplayDevicesW
0x18000dd68  test    eax, eax
0x18000dd6a  jnz     short loc_18000DDBF
0x18000dd6c  mov     eax, 80070057h
0x18000dd71  jmp     short loc_18000DD9C
0x18000dd73  xor     r15d, r15d
0x18000dd76  mov     r8, r15
0x18000dd79  lea     rcx, [rbp+5C0h+var_260]
0x18000dd80  mov     edx, 104h
0x18000dd85  call    cs:__imp__o_wcscpy_s
0x18000dd8b  mov     r14d, [rsp+6C0h+var_67C]
0x18000dd90  mov     ebx, eax
0x18000dd92  test    ebx, ebx
0x18000dd94  jns     loc_18000DE7C
0x18000dd9a  mov     eax, ebx
0x18000dd9c  mov     rcx, [rbp+5C0h+var_50]
0x18000dda3  xor     rcx, rsp; StackCookie
0x18000dda6  call    __security_check_cookie
0x18000ddab  add     rsp, 688h
0x18000ddb2  pop     r15
0x18000ddb4  pop     r14
0x18000ddb6  pop     r13
0x18000ddb8  pop     r12
0x18000ddba  pop     rdi
0x18000ddbb  pop     rsi
0x18000ddbc  pop     rbx
0x18000ddbd  pop     rbp
0x18000ddbe  retn
0x18000ddbf  lea     r15, [rbp+5C0h+DisplayDevice.DeviceID]
0x18000ddc6  lea     r12, gszMonitorGUID; "{4D36E96E-E325-11CE-BFC1-08002BE10318}"
0x18000ddcd  nop     dword ptr [rax]
0x18000ddd0  movzx   edi, word ptr [r15]
0x18000ddd4  test    di, di
0x18000ddd7  jz      short loc_18000DD73
0x18000ddd9  movzx   ebx, word ptr cs:gszMonitorGUID; "{4D36E96E-E325-11CE-BFC1-08002BE10318}"
0x18000dde0  movzx   ecx, di; C
0x18000dde3  mov     r14, r15
0x18000dde6  mov     rsi, r12
0x18000dde9  call    iswupper
0x18000ddee  test    eax, eax
0x18000ddf0  jz      short loc_18000DDFD
0x18000ddf2  movzx   ecx, di
0x18000ddf5  call    _o_towlower_0
0x18000ddfa  movzx   edi, ax
0x18000ddfd  movzx   ecx, bx; C
0x18000de00  call    iswupper
0x18000de05  test    eax, eax
0x18000de07  jnz     loc_18000DF5C
0x18000de0d  cmp     word ptr [r15], 0
0x18000de12  jz      short loc_18000DE69
0x18000de14  cmp     word ptr [rsi], 0
0x18000de18  jz      loc_18000DD76
0x18000de1e  cmp     di, bx
0x18000de21  jnz     short loc_18000DE69
0x18000de23  movzx   edi, word ptr [r14+2]
0x18000de28  add     r14, 2
0x18000de2c  movzx   ebx, word ptr [rsi+2]
0x18000de30  add     rsi, 2
0x18000de34  movzx   ecx, di; C
0x18000de37  call    iswupper
0x18000de3c  test    eax, eax
0x18000de3e  jz      short loc_18000DE4B
0x18000de40  movzx   ecx, di
0x18000de43  call    _o_towlower_0
0x18000de48  movzx   edi, ax
0x18000de4b  movzx   ecx, bx; C
0x18000de4e  call    iswupper
0x18000de53  test    eax, eax
0x18000de55  jz      short loc_18000DE62
0x18000de57  movzx   ecx, bx
0x18000de5a  call    _o_towlower_0
0x18000de5f  movzx   ebx, ax
0x18000de62  cmp     word ptr [r14], 0
0x18000de67  jnz     short loc_18000DE14
0x18000de69  cmp     word ptr [rsi], 0
0x18000de6d  jz      loc_18000DD76
0x18000de73  add     r15, 2
0x18000de77  jmp     loc_18000DDD0
0x18000de7c  mov     esi, [rbp+5C0h+arg_20]
0x18000de82  lea     rax, [rsp+6C0h+var_680]
0x18000de87  mov     r15d, [rsp+6C0h+var_678]
0x18000de8c  lea     rdx, [rbp+5C0h+var_260]; unsigned __int16 *
0x18000de93  mov     [rsp+6C0h+var_688], 1; int
0x18000de9b  mov     r9d, esi; enum COLORPROFILESUBTYPE
0x18000de9e  mov     [rsp+6C0h+var_690], rax; unsigned int *
0x18000dea3  mov     r8d, r15d; enum COLORPROFILETYPE
0x18000dea6  mov     [rsp+6C0h+var_698], 0; unsigned __int16 *
0x18000deaf  mov     ecx, r14d; enum WCS_PROFILE_MANAGEMENT_SCOPE
0x18000deb2  mov     [rsp+6C0h+var_6A0], 0; unsigned int
0x18000deba  call    ?InternalGetDefaultColorProfile@@YAHW4WCS_PROFILE_MANAGEMENT_SCOPE@@PEBGW4COLORPROFILETYPE@@W4COLORPROFILESUBTYPE@@KPEAGPEAKH@Z; InternalGetDefaultColorProfile(WCS_PROFILE_MANAGEMENT_SCOPE,ushort const *,COLORPROFILETYPE,COLORPROFILESUBTYPE,ulong,ushort *,ulong *,int)
0x18000debf  test    eax, eax
0x18000dec1  jnz     short loc_18000DEE2
0x18000dec3  xor     edi, edi
0x18000dec5  call    cs:__imp_GetLastError
0x18000decb  mov     ebx, eax
0x18000decd  test    eax, eax
0x18000decf  jg      short loc_18000DF4E
0x18000ded1  test    ebx, ebx
0x18000ded3  js      loc_18000E039
0x18000ded9  mov     [r13+0], rdi
0x18000dedd  jmp     loc_18000DD9A
0x18000dee2  mov     eax, [rsp+6C0h+var_680]
0x18000dee6  test    eax, eax
0x18000dee8  jz      loc_18000E025
0x18000deee  mov     edx, eax
0x18000def0  mov     ecx, 40h ; '@'; uFlags
0x18000def5  add     rdx, rdx; uBytes
0x18000def8  call    cs:__imp_LocalAlloc
0x18000defe  mov     rdi, rax
0x18000df01  test    rax, rax
0x18000df04  jz      loc_18000E02F
0x18000df0a  mov     [rsp+6C0h+var_688], 1; int
0x18000df12  lea     rax, [rsp+6C0h+var_680]
0x18000df17  mov     [rsp+6C0h+var_690], rax; unsigned int *
0x18000df1c  lea     rdx, [rbp+5C0h+var_260]; unsigned __int16 *
0x18000df23  mov     [rsp+6C0h+var_698], rdi; unsigned __int16 *
0x18000df28  mov     r9d, esi; enum COLORPROFILESUBTYPE
0x18000df2b  mov     r8d, r15d; enum COLORPROFILETYPE
0x18000df2e  mov     [rsp+6C0h+var_6A0], 0; unsigned int
0x18000df36  mov     ecx, r14d; enum WCS_PROFILE_MANAGEMENT_SCOPE
0x18000df39  call    ?InternalGetDefaultColorProfile@@YAHW4WCS_PROFILE_MANAGEMENT_SCOPE@@PEBGW4COLORPROFILETYPE@@W4COLORPROFILESUBTYPE@@KPEAGPEAKH@Z; InternalGetDefaultColorProfile(WCS_PROFILE_MANAGEMENT_SCOPE,ushort const *,COLORPROFILETYPE,COLORPROFILESUBTYPE,ulong,ushort *,ulong *,int)
0x18000df3e  test    eax, eax
0x18000df40  jnz     short loc_18000DED9
0x18000df42  call    cs:__imp_GetLastError
0x18000df48  mov     ebx, eax
0x18000df4a  test    eax, eax
0x18000df4c  jle     short loc_18000DED1
0x18000df4e  movzx   ebx, ax
0x18000df51  or      ebx, 80070000h
0x18000df57  jmp     loc_18000DED1
0x18000df5c  movzx   ecx, bx
0x18000df5f  call    _o_towlower_0
0x18000df64  movzx   ebx, ax
0x18000df67  jmp     loc_18000DE0D
0x18000df6c  mov     r8d, 3B0h; Size
0x18000df72  lea     rcx, [rbp+5C0h+DisplayDevice]; void *
0x18000df76  call    memset_0
0x18000df7b  lea     r8, [rbp+5C0h+DisplayDevice]; struct _DISPLAYCONFIG_GET_MONITOR_INTERNAL_INFO *
0x18000df7f  mov     edx, edi; unsigned int
0x18000df81  mov     rcx, rbx; struct _LUID
0x18000df84  call    ?GetMonitorUniqueName@@YAJU_LUID@@IAEAU_DISPLAYCONFIG_GET_MONITOR_INTERNAL_INFO@@@Z; GetMonitorUniqueName(_LUID,uint,_DISPLAYCONFIG_GET_MONITOR_INTERNAL_INFO &)
0x18000df89  mov     ebx, eax
0x18000df8b  test    eax, eax
0x18000df8d  js      loc_18000DD92
0x18000df93  lea     r12, gszMonitorGUID; "{4D36E96E-E325-11CE-BFC1-08002BE10318}"
0x18000df9a  mov     edi, 104h
0x18000df9f  mov     r8, r12
0x18000dfa2  lea     rcx, [rbp+5C0h+var_260]
0x18000dfa9  mov     edx, edi
0x18000dfab  call    cs:__imp__o_wcscpy_s
0x18000dfb1  mov     ebx, eax
0x18000dfb3  test    eax, eax
0x18000dfb5  js      loc_18000DD92
0x18000dfbb  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x18000dfc2  mov     rax, rsi
0x18000dfc5  inc     rax
0x18000dfc8  cmp     word ptr [r12+rax*2], 0
0x18000dfce  jnz     short loc_18000DFC5
0x18000dfd0  sub     rdi, rax
0x18000dfd3  lea     rcx, [rbp+5C0h+var_260]
0x18000dfda  lea     rcx, [rcx+rax*2]
0x18000dfde  mov     rdx, rdi
0x18000dfe1  lea     r8, StringValue; "\\"
0x18000dfe8  call    cs:__imp__o_wcscpy_s
0x18000dfee  mov     ebx, eax
0x18000dff0  test    eax, eax
0x18000dff2  js      loc_18000DD92
0x18000dff8  inc     rsi
0x18000dffb  cmp     word ptr [r12+rsi*2], 0
0x18000e001  jnz     short loc_18000DFF8
0x18000e003  mov     edx, 103h
0x18000e008  lea     rcx, [rbp+5C0h+var_25E]
0x18000e00f  sub     rdx, rsi
0x18000e012  lea     rcx, [rcx+rsi*2]
0x18000e016  lea     r8, [rbp+5C0h+DisplayDevice.DeviceName+10h]
0x18000e01a  call    cs:__imp__o_wcscpy_s
0x18000e020  jmp     loc_18000DD90
0x18000e025  mov     eax, 800707DFh
0x18000e02a  jmp     loc_18000DD9C
0x18000e02f  mov     eax, 8007000Eh
0x18000e034  jmp     loc_18000DD9C
0x18000e039  test    rdi, rdi
0x18000e03c  jz      loc_18000DD9A
0x18000e042  mov     rcx, rdi; hMem
0x18000e045  call    cs:__imp_LocalFree
0x18000e04b  jmp     loc_18000DD9A
```
