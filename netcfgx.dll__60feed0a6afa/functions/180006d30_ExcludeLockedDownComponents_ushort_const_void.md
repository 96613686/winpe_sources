# ExcludeLockedDownComponents(ushort const *,void *)

- ea: `0x180006d30`
- end: `0x180006ec5`
- name: `?ExcludeLockedDownComponents@@YAXPEBGPEAX@Z`
- size: `405`
- prototype: `void __fastcall(LPCWSTR lpString2, HDEVINFO DeviceInfoSet)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180007a4c`

## callees

- `0x180001f90`
- `0x180002a40`
- `0x1800068e4`
- `0x180006d30`
- `0x180007d80`
- `0x180007f3c`
- `0x180008260`
- `0x18000831c`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180006dfb`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180006dfb`
- `SETUPAPI!SetupDiGetDriverInstallParamsW` at `0x180006dbd`
- `SETUPAPI!SetupDiGetDriverInstallParamsW` at `0x180006dbd`
- `SETUPAPI!SetupDiSetDriverInstallParamsW` at `0x180006e1a`
- `SETUPAPI!SetupDiSetDriverInstallParamsW` at `0x180006e1a`

## pseudocode

```c
void __fastcall ExcludeLockedDownComponents(LPCWSTR lpString2, HDEVINFO DeviceInfoSet)
{
  struct _SP_DEVINFO_DATA *v4; // rdx
  __int64 v5; // r8
  DWORD v6; // r9d
  int i; // esi
  void *v8; // rdi
  unsigned int v9; // eax
  __int64 v10; // r9
  void *lpMem; // [rsp+30h] [rbp-D0h] BYREF
  _SP_DRVINSTALL_PARAMS DriverInstallParams; // [rsp+38h] [rbp-C8h] BYREF
  _SP_DRVINFO_DATA_V2_W DriverInfoData; // [rsp+60h] [rbp-A0h] BYREF

  memset(&DriverInstallParams, 0, sizeof(DriverInstallParams));
  memset_0(&DriverInfoData, 0, sizeof(DriverInfoData));
  v6 = 0;
  lpMem = 0;
  for ( i = 1; ; ++i )
  {
    v9 = HrSetupDiEnumDriverInfo(DeviceInfoSet, v4, v5, v6, &DriverInfoData);
    if ( v9 )
      break;
    memset(&DriverInstallParams, 0, sizeof(DriverInstallParams));
    DriverInstallParams.cbSize = 32;
    if ( !SetupDiGetDriverInstallParamsW(DeviceInfoSet, 0, &DriverInfoData, &DriverInstallParams) )
      HrFromLastWin32Error();
    if ( (DriverInstallParams.Flags & 0x800) == 0
      && !(unsigned int)HrSetupDiGetDriverInfoDetail(
                          DeviceInfoSet,
                          v4,
                          &DriverInfoData,
                          (struct _SP_DRVINFO_DETAIL_DATA_W **)&lpMem) )
    {
      v8 = lpMem;
      if ( !lstrcmpiW((LPCWSTR)lpMem + 788, lpString2) )
      {
        DriverInstallParams.Flags |= 0x800u;
        if ( !SetupDiSetDriverInstallParamsW(DeviceInfoSet, 0, &DriverInfoData, &DriverInstallParams) )
          HrFromLastWin32Error();
      }
      MemFree(v8);
      lpMem = 0;
    }
    v6 = i;
  }
  v10 = 0;
  if ( v9 != -2147024637 )
    v10 = v9;
  if ( (_DWORD)v10
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_555e6cdaff2135333903973068bb5302_Traceguids, v10);
  }
}

```

## disassembly

```asm
0x180006d30  mov     [rsp-8+arg_10], rbx
0x180006d35  mov     [rsp-8+arg_18], rsi
0x180006d3a  push    rbp
0x180006d3b  push    rdi
0x180006d3c  push    r14
0x180006d3e  lea     rbp, [rsp-590h]
0x180006d46  sub     rsp, 690h
0x180006d4d  mov     rax, cs:__security_cookie
0x180006d54  xor     rax, rsp
0x180006d57  mov     [rbp+5A0h+var_20], rax
0x180006d5e  xorps   xmm0, xmm0
0x180006d61  mov     rbx, rdx
0x180006d64  mov     r14, rcx
0x180006d67  xor     edx, edx; Val
0x180006d69  lea     rcx, [rsp+6A0h+DriverInfoData]; void *
0x180006d6e  mov     r8d, 620h; Size
0x180006d74  movups  xmmword ptr [rsp+6A0h+DriverInstallParams.cbSize], xmm0
0x180006d79  movups  xmmword ptr [rsp+6A0h+DriverInstallParams.PrivateData], xmm0
0x180006d7e  call    memset_0
0x180006d83  xor     r9d, r9d
0x180006d86  mov     [rsp+6A0h+lpMem], 0
0x180006d8f  mov     esi, 1
0x180006d94  jmp     loc_180006E3F
0x180006d99  xorps   xmm0, xmm0
0x180006d9c  lea     r9, [rsp+6A0h+DriverInstallParams]; DriverInstallParams
0x180006da1  movups  xmmword ptr [rsp+6A0h+DriverInstallParams.cbSize], xmm0
0x180006da6  lea     r8, [rsp+6A0h+DriverInfoData]; DriverInfoData
0x180006dab  mov     [rsp+6A0h+DriverInstallParams.cbSize], 20h ; ' '
0x180006db3  xor     edx, edx; DeviceInfoData
0x180006db5  mov     rcx, rbx; DeviceInfoSet
0x180006db8  movups  xmmword ptr [rsp+6A0h+DriverInstallParams.PrivateData], xmm0
0x180006dbd  call    cs:__imp_SetupDiGetDriverInstallParamsW
0x180006dc3  test    eax, eax
0x180006dc5  jnz     short loc_180006DCC
0x180006dc7  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180006dcc  test    [rsp+6A0h+DriverInstallParams.Flags], 800h
0x180006dd4  jnz     short loc_180006E3A
0x180006dd6  lea     r9, [rsp+6A0h+lpMem]; struct _SP_DRVINFO_DETAIL_DATA_W **
0x180006ddb  mov     rcx, rbx; DeviceInfoSet
0x180006dde  lea     r8, [rsp+6A0h+DriverInfoData]; struct _SP_DRVINFO_DATA_V2_W *
0x180006de3  call    ?HrSetupDiGetDriverInfoDetail@@YAJPEAXPEAU_SP_DEVINFO_DATA@@PEAU_SP_DRVINFO_DATA_V2_W@@PEAPEAU_SP_DRVINFO_DETAIL_DATA_W@@@Z; HrSetupDiGetDriverInfoDetail(void *,_SP_DEVINFO_DATA *,_SP_DRVINFO_DATA_V2_W *,_SP_DRVINFO_DETAIL_DATA_W * *)
0x180006de8  test    eax, eax
0x180006dea  jnz     short loc_180006E3A
0x180006dec  mov     rdi, [rsp+6A0h+lpMem]
0x180006df1  mov     rdx, r14; lpString2
0x180006df4  lea     rcx, [rdi+628h]; lpString1
0x180006dfb  call    cs:__imp_lstrcmpiW
0x180006e01  test    eax, eax
0x180006e03  jnz     short loc_180006E29
0x180006e05  bts     [rsp+6A0h+DriverInstallParams.Flags], 0Bh
0x180006e0b  lea     r9, [rsp+6A0h+DriverInstallParams]; DriverInstallParams
0x180006e10  lea     r8, [rsp+6A0h+DriverInfoData]; DriverInfoData
0x180006e15  xor     edx, edx; DeviceInfoData
0x180006e17  mov     rcx, rbx; DeviceInfoSet
0x180006e1a  call    cs:__imp_SetupDiSetDriverInstallParamsW
0x180006e20  test    eax, eax
0x180006e22  jnz     short loc_180006E29
0x180006e24  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180006e29  mov     rcx, rdi; lpMem
0x180006e2c  call    ?MemFree@@YAXPEAX@Z; MemFree(void *)
0x180006e31  mov     [rsp+6A0h+lpMem], 0
0x180006e3a  mov     r9d, esi; unsigned int
0x180006e3d  inc     esi
0x180006e3f  lea     rax, [rsp+6A0h+DriverInfoData]
0x180006e44  mov     rcx, rbx; DeviceInfoSet
0x180006e47  mov     [rsp+6A0h+var_680], rax; struct _SP_DRVINFO_DATA_V2_W *
0x180006e4c  call    ?HrSetupDiEnumDriverInfo@@YAJPEAXPEAU_SP_DEVINFO_DATA@@KKPEAU_SP_DRVINFO_DATA_V2_W@@@Z; HrSetupDiEnumDriverInfo(void *,_SP_DEVINFO_DATA *,ulong,ulong,_SP_DRVINFO_DATA_V2_W *)
0x180006e51  test    eax, eax
0x180006e53  jz      loc_180006D99
0x180006e59  xor     r9d, r9d
0x180006e5c  cmp     eax, 80070103h
0x180006e61  cmovnz  r9d, eax
0x180006e65  test    r9d, r9d
0x180006e68  jz      short loc_180006E9E
0x180006e6a  mov     rcx, cs:WPP_GLOBAL_Control
0x180006e71  lea     rax, WPP_GLOBAL_Control
0x180006e78  cmp     rcx, rax
0x180006e7b  jz      short loc_180006E9E
0x180006e7d  cmp     byte ptr [rcx+19h], 2
0x180006e81  jb      short loc_180006E9E
0x180006e83  test    byte ptr [rcx+1Ch], 10h
0x180006e87  jz      short loc_180006E9E
0x180006e89  mov     rcx, [rcx+10h]
0x180006e8d  lea     r8, WPP_555e6cdaff2135333903973068bb5302_Traceguids
0x180006e94  mov     edx, 0Ch
0x180006e99  call    WPP_SF_d
0x180006e9e  mov     rcx, [rbp+5A0h+var_20]
0x180006ea5  xor     rcx, rsp; StackCookie
0x180006ea8  call    __security_check_cookie
0x180006ead  lea     r11, [rsp+6A0h+var_10]
0x180006eb5  mov     rbx, [r11+30h]
0x180006eb9  mov     rsi, [r11+38h]
0x180006ebd  mov     rsp, r11
0x180006ec0  pop     r14
0x180006ec2  pop     rdi
0x180006ec3  pop     rbp
0x180006ec4  retn
```
