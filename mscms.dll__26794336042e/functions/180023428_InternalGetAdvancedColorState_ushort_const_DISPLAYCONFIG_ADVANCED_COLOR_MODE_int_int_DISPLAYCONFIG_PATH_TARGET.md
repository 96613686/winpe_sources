# InternalGetAdvancedColorState(ushort const *,_DISPLAYCONFIG_ADVANCED_COLOR_MODE *,int *,int *,DISPLAYCONFIG_PATH_TARGET_INFO *)

- ea: `0x180023428`
- end: `0x18002351f`
- name: `?InternalGetAdvancedColorState@@YAJPEBGPEAW4_DISPLAYCONFIG_ADVANCED_COLOR_MODE@@PEAH2PEAUDISPLAYCONFIG_PATH_TARGET_INFO@@@Z`
- size: `247`
- prototype: `__int64 __usercall@<rax>(const unsigned __int16 *@<rcx>, enum _DISPLAYCONFIG_ADVANCED_COLOR_MODE *@<rdx>, int *@<r8>, int *@<r9>, struct DISPLAYCONFIG_PATH_TARGET_INFO *)`
- caller_count: `8`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000e184`
- `0x18001d6f4`
- `0x1800212e0`
- `0x18002435c`
- `0x1800441d0`
- `0x1800442e0`
- `0x180045470`
- `0x180047f20`

## callees

- `0x18001582c`
- `0x180023428`
- `0x18002e5f0`
- `0x18002f2f4`

## import_xrefs

- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!DisplayConfigGetDeviceInfo` at `0x1800234db`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!DisplayConfigGetDeviceInfo` at `0x1800234db`

## pseudocode

```c
__int64 __fastcall InternalGetAdvancedColorState(
        const unsigned __int16 *a1,
        enum _DISPLAYCONFIG_ADVANCED_COLOR_MODE *a2,
        int *a3,
        int *a4,
        struct DISPLAYCONFIG_PATH_TARGET_INFO *a5)
{
  signed int v7; // ebx
  UINT32 id; // edx
  LUID adapterId; // rax
  __int128 v10; // xmm1
  UINT32 statusFlags; // ecx
  LONG DeviceInfo; // eax
  struct DISPLAYCONFIG_PATH_INFO v14; // [rsp+20h] [rbp-41h] BYREF
  DISPLAYCONFIG_DEVICE_INFO_HEADER requestPacket; // [rsp+70h] [rbp+Fh] BYREF
  __int128 v16; // [rsp+84h] [rbp+23h]

  v14.sourceInfo.adapterId.LowPart = 0;
  v7 = -2147024809;
  memset_0(&v14.sourceInfo.adapterId.HighPart, 0, 0x44u);
  if ( a2 )
  {
    *(_DWORD *)a2 = 0;
    v7 = InternalTranslateICMNameToPath(a1, &v14);
    if ( v7 >= 0 )
    {
      id = v14.targetInfo.id;
      adapterId = v14.targetInfo.adapterId;
      if ( a5 )
      {
        v10 = *(_OWORD *)&v14.targetInfo.refreshRate.Numerator;
        statusFlags = v14.targetInfo.statusFlags;
        *(_OWORD *)&a5->modeInfoIdx = *(_OWORD *)&v14.targetInfo.modeInfoIdx;
        a5->adapterId = adapterId;
        *(_OWORD *)&a5->refreshRate.Numerator = v10;
        a5->statusFlags = statusFlags;
        a5->id = id;
      }
      requestPacket.type = DISPLAYCONFIG_DEVICE_INFO_GET_SDR_WHITE_LEVEL|DISPLAYCONFIG_DEVICE_INFO_GET_ADAPTER_NAME;
      requestPacket.size = 36;
      v16 = 0;
      requestPacket.adapterId = adapterId;
      requestPacket.id = id;
      DeviceInfo = DisplayConfigGetDeviceInfo(&requestPacket);
      v7 = DeviceInfo;
      if ( DeviceInfo > 0 )
        v7 = (unsigned __int16)DeviceInfo | 0x80070000;
      if ( v7 >= 0 )
        *(_DWORD *)a2 = HIDWORD(v16);
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180023428  mov     [rsp-8+arg_10], rbx
0x18002342d  mov     [rsp-8+arg_18], rsi
0x180023432  push    rbp
0x180023433  push    rdi
0x180023434  push    r14
0x180023436  lea     rbp, [rsp-3Fh]
0x18002343b  sub     rsp, 0A0h
0x180023442  mov     rax, cs:__security_cookie
0x180023449  xor     rax, rsp
0x18002344c  mov     [rbp+4Fh+var_18], rax
0x180023450  mov     rdi, [rbp+4Fh+arg_20]
0x180023454  mov     rsi, rdx
0x180023457  xor     edx, edx; Val
0x180023459  mov     [rbp+4Fh+var_90.sourceInfo.adapterId.LowPart], 0
0x180023460  mov     r14, rcx
0x180023463  mov     ebx, 80070057h
0x180023468  lea     rcx, [rbp+4Fh+var_90.sourceInfo.adapterId.HighPart]; void *
0x18002346c  lea     r8d, [rdx+44h]; Size
0x180023470  call    memset_0
0x180023475  test    rsi, rsi
0x180023478  jz      short loc_1800234F9
0x18002347a  lea     rdx, [rbp+4Fh+var_90]; struct DISPLAYCONFIG_PATH_INFO *
0x18002347e  mov     dword ptr [rsi], 0
0x180023484  mov     rcx, r14; unsigned __int16 *
0x180023487  call    ?InternalTranslateICMNameToPath@@YAJPEBGPEAUDISPLAYCONFIG_PATH_INFO@@@Z; InternalTranslateICMNameToPath(ushort const *,DISPLAYCONFIG_PATH_INFO *)
0x18002348c  mov     ebx, eax
0x18002348e  test    eax, eax
0x180023490  js      short loc_1800234F9
0x180023492  mov     edx, [rbp+4Fh+var_90.targetInfo.id]
0x180023495  mov     rax, qword ptr [rbp+4Fh+var_90.targetInfo.adapterId.LowPart]
0x180023499  test    rdi, rdi
0x18002349c  jz      short loc_1800234BA
0x18002349e  movaps  xmm0, xmmword ptr [rbp+4Fh+var_90.targetInfo.0Ch]
0x1800234a2  movaps  xmm1, xmmword ptr [rbp+4Fh+var_90.targetInfo.refreshRate.Numerator]
0x1800234a6  mov     ecx, [rbp+4Fh+var_90.targetInfo.statusFlags]
0x1800234a9  movups  xmmword ptr [rdi+0Ch], xmm0
0x1800234ad  mov     [rdi], rax
0x1800234b0  movups  xmmword ptr [rdi+1Ch], xmm1
0x1800234b4  mov     [rdi+2Ch], ecx
0x1800234b7  mov     [rdi+8], edx
0x1800234ba  xorps   xmm0, xmm0
0x1800234bd  mov     [rbp+4Fh+requestPacket.type], 0Fh
0x1800234c4  lea     rcx, [rbp+4Fh+requestPacket]; requestPacket
0x1800234c8  mov     [rbp+4Fh+requestPacket.size], 24h ; '$'
0x1800234cf  movdqu  [rbp+4Fh+var_2C], xmm0
0x1800234d4  mov     qword ptr [rbp+4Fh+requestPacket.adapterId.LowPart], rax
0x1800234d8  mov     [rbp+4Fh+requestPacket.id], edx
0x1800234db  call    cs:__imp_DisplayConfigGetDeviceInfo
0x1800234e1  mov     ebx, eax
0x1800234e3  test    eax, eax
0x1800234e5  jle     short loc_1800234F0
0x1800234e7  movzx   ebx, ax
0x1800234ea  or      ebx, 80070000h
0x1800234f0  test    ebx, ebx
0x1800234f2  js      short loc_1800234F9
0x1800234f4  mov     eax, dword ptr [rbp+4Fh+var_2C+0Ch]
0x1800234f7  mov     [rsi], eax
0x1800234f9  mov     eax, ebx
0x1800234fb  mov     rcx, [rbp+4Fh+var_18]
0x1800234ff  xor     rcx, rsp; StackCookie
0x180023502  call    __security_check_cookie
0x180023507  lea     r11, [rsp+0B0h+var_10]
0x18002350f  mov     rbx, [r11+30h]
0x180023513  mov     rsi, [r11+38h]
0x180023517  mov     rsp, r11
0x18002351a  pop     r14
0x18002351c  pop     rdi
0x18002351d  pop     rbp
0x18002351e  retn
```
