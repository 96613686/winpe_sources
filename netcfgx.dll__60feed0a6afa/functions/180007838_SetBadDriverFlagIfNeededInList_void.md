# SetBadDriverFlagIfNeededInList(void *)

- ea: `0x180007838`
- end: `0x180007982`
- name: `?SetBadDriverFlagIfNeededInList@@YAXPEAX@Z`
- size: `330`
- prototype: `void __fastcall(HDEVINFO DeviceInfoSet)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180006ecc`

## callees

- `0x180001f90`
- `0x180002a40`
- `0x1800068e4`
- `0x180007838`
- `0x180007f3c`
- `0x180008260`

## import_xrefs

- `SETUPAPI!SetupDiGetDriverInstallParamsW` at `0x1800078b3`
- `SETUPAPI!SetupDiGetDriverInstallParamsW` at `0x1800078b3`
- `SETUPAPI!SetupDiSetDriverInstallParamsW` at `0x1800078eb`
- `SETUPAPI!SetupDiSetDriverInstallParamsW` at `0x1800078eb`

## pseudocode

```c
void __fastcall SetBadDriverFlagIfNeededInList(HDEVINFO DeviceInfoSet)
{
  struct _SP_DEVINFO_DATA *v2; // rdx
  unsigned int v3; // r8d
  unsigned int v4; // r9d
  int i; // edi
  unsigned int v6; // eax
  __int64 v7; // r9
  struct _SP_DRVINSTALL_PARAMS DriverInstallParams; // [rsp+30h] [rbp-D0h] BYREF
  struct _SP_DRVINFO_DATA_V2_W DriverInfoData; // [rsp+50h] [rbp-B0h] BYREF

  memset(&DriverInstallParams, 0, sizeof(DriverInstallParams));
  memset_0(&DriverInfoData, 0, sizeof(DriverInfoData));
  v4 = 0;
  for ( i = 1; ; ++i )
  {
    v6 = HrSetupDiEnumDriverInfo(DeviceInfoSet, v2, v3, v4, &DriverInfoData);
    if ( v6 )
      break;
    memset(&DriverInstallParams, 0, sizeof(DriverInstallParams));
    DriverInstallParams.cbSize = 32;
    if ( (SetupDiGetDriverInstallParamsW(DeviceInfoSet, 0, &DriverInfoData, &DriverInstallParams)
       || !(unsigned int)HrFromLastWin32Error())
      && (DriverInstallParams.Flags & 0x800) == 0
      && (DriverInstallParams.Flags & 4) != 0 )
    {
      DriverInstallParams.Flags |= 0x800u;
      if ( !SetupDiSetDriverInstallParamsW(DeviceInfoSet, 0, &DriverInfoData, &DriverInstallParams) )
        HrFromLastWin32Error();
    }
    v4 = i;
  }
  v7 = 0;
  if ( v6 != -2147024637 )
    v7 = v6;
  if ( (_DWORD)v7
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_555e6cdaff2135333903973068bb5302_Traceguids, v7);
  }
}

```

## disassembly

```asm
0x180007838  mov     [rsp-8+arg_8], rbx
0x18000783d  mov     [rsp-8+arg_10], rdi
0x180007842  push    rbp
0x180007843  lea     rbp, [rsp-580h]
0x18000784b  sub     rsp, 680h
0x180007852  mov     rax, cs:__security_cookie
0x180007859  xor     rax, rsp
0x18000785c  mov     [rbp+580h+var_10], rax
0x180007863  xorps   xmm0, xmm0
0x180007866  mov     rbx, rcx
0x180007869  lea     rcx, [rsp+680h+DriverInfoData]; void *
0x18000786e  xor     edx, edx; Val
0x180007870  mov     r8d, 620h; Size
0x180007876  movups  xmmword ptr [rsp+680h+DriverInstallParams.cbSize], xmm0
0x18000787b  movups  xmmword ptr [rsp+680h+DriverInstallParams.PrivateData], xmm0
0x180007880  call    memset_0
0x180007885  xor     r9d, r9d
0x180007888  mov     edi, 1
0x18000788d  jmp     short loc_1800078FF
0x18000788f  xorps   xmm0, xmm0
0x180007892  lea     r9, [rsp+680h+DriverInstallParams]; DriverInstallParams
0x180007897  movups  xmmword ptr [rsp+680h+DriverInstallParams.cbSize], xmm0
0x18000789c  lea     r8, [rsp+680h+DriverInfoData]; DriverInfoData
0x1800078a1  mov     [rsp+680h+DriverInstallParams.cbSize], 20h ; ' '
0x1800078a9  xor     edx, edx; DeviceInfoData
0x1800078ab  mov     rcx, rbx; DeviceInfoSet
0x1800078ae  movups  xmmword ptr [rsp+680h+DriverInstallParams.PrivateData], xmm0
0x1800078b3  call    cs:__imp_SetupDiGetDriverInstallParamsW
0x1800078b9  test    eax, eax
0x1800078bb  jnz     short loc_1800078C6
0x1800078bd  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x1800078c2  test    eax, eax
0x1800078c4  jnz     short loc_1800078FA
0x1800078c6  mov     eax, [rsp+680h+DriverInstallParams.Flags]
0x1800078ca  bt      eax, 0Bh
0x1800078ce  jb      short loc_1800078FA
0x1800078d0  test    al, 4
0x1800078d2  jz      short loc_1800078FA
0x1800078d4  bts     eax, 0Bh
0x1800078d8  lea     r9, [rsp+680h+DriverInstallParams]; DriverInstallParams
0x1800078dd  lea     r8, [rsp+680h+DriverInfoData]; DriverInfoData
0x1800078e2  mov     [rsp+680h+DriverInstallParams.Flags], eax
0x1800078e6  xor     edx, edx; DeviceInfoData
0x1800078e8  mov     rcx, rbx; DeviceInfoSet
0x1800078eb  call    cs:__imp_SetupDiSetDriverInstallParamsW
0x1800078f1  test    eax, eax
0x1800078f3  jnz     short loc_1800078FA
0x1800078f5  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x1800078fa  mov     r9d, edi; unsigned int
0x1800078fd  inc     edi
0x1800078ff  lea     rax, [rsp+680h+DriverInfoData]
0x180007904  mov     rcx, rbx; DeviceInfoSet
0x180007907  mov     [rsp+680h+var_660], rax; struct _SP_DRVINFO_DATA_V2_W *
0x18000790c  call    ?HrSetupDiEnumDriverInfo@@YAJPEAXPEAU_SP_DEVINFO_DATA@@KKPEAU_SP_DRVINFO_DATA_V2_W@@@Z; HrSetupDiEnumDriverInfo(void *,_SP_DEVINFO_DATA *,ulong,ulong,_SP_DRVINFO_DATA_V2_W *)
0x180007911  test    eax, eax
0x180007913  jz      loc_18000788F
0x180007919  xor     r9d, r9d
0x18000791c  cmp     eax, 80070103h
0x180007921  cmovnz  r9d, eax
0x180007925  test    r9d, r9d
0x180007928  jz      short loc_18000795E
0x18000792a  mov     rcx, cs:WPP_GLOBAL_Control
0x180007931  lea     rax, WPP_GLOBAL_Control
0x180007938  cmp     rcx, rax
0x18000793b  jz      short loc_18000795E
0x18000793d  cmp     byte ptr [rcx+19h], 2
0x180007941  jb      short loc_18000795E
0x180007943  test    byte ptr [rcx+1Ch], 10h
0x180007947  jz      short loc_18000795E
0x180007949  mov     rcx, [rcx+10h]
0x18000794d  lea     r8, WPP_555e6cdaff2135333903973068bb5302_Traceguids
0x180007954  mov     edx, 0Bh
0x180007959  call    WPP_SF_d
0x18000795e  mov     rcx, [rbp+580h+var_10]
0x180007965  xor     rcx, rsp; StackCookie
0x180007968  call    __security_check_cookie
0x18000796d  lea     r11, [rsp+680h+var_s0]
0x180007975  mov     rbx, [r11+18h]
0x180007979  mov     rdi, [r11+20h]
0x18000797d  mov     rsp, r11
0x180007980  pop     rbp
0x180007981  retn
```
