# SetDevInstallParams

- ea: `0x180028a24`
- end: `0x180028acb`
- name: `SetDevInstallParams`
- size: `167`
- prototype: `__int64 __fastcall(HDEVINFO DeviceInfoSet, PSP_DEVINFO_DATA DeviceInfoData, unsigned __int16 *)`
- caller_count: `3`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x1800148bc`
- `0x18001de14`
- `0x180027910`

## callees

- `0x180002300`
- `0x180002f48`
- `0x180007944`
- `0x180028a24`

## import_xrefs

- `SETUPAPI!SetupDiSetDeviceInstallParamsW` at `0x180028aaa`
- `SETUPAPI!SetupDiSetDeviceInstallParamsW` at `0x180028aaa`
- `SETUPAPI!SetupDiGetDeviceInstallParamsW` at `0x180028a6f`
- `SETUPAPI!SetupDiGetDeviceInstallParamsW` at `0x180028a6f`

## pseudocode

```c
BOOL __fastcall SetDevInstallParams(HDEVINFO DeviceInfoSet, PSP_DEVINFO_DATA DeviceInfoData, unsigned __int16 *a3)
{
  BOOL result; // eax
  struct _SP_DEVINSTALL_PARAMS_W DeviceInstallParams; // [rsp+20h] [rbp-278h] BYREF

  memset_0(&DeviceInstallParams.Flags, 0, 0x244u);
  DeviceInstallParams.cbSize = 584;
  result = SetupDiGetDeviceInstallParamsW(DeviceInfoSet, DeviceInfoData, &DeviceInstallParams);
  if ( result )
  {
    DeviceInstallParams.Flags |= 0x8000005u;
    if ( a3 )
    {
      if ( *a3 )
        StringCchCopyW(DeviceInstallParams.DriverPath, 0x104u, a3);
    }
    return SetupDiSetDeviceInstallParamsW(DeviceInfoSet, DeviceInfoData, &DeviceInstallParams);
  }
  return result;
}

```

## disassembly

```asm
0x180028a24  push    rbx
0x180028a26  push    rsi
0x180028a27  push    rdi
0x180028a28  sub     rsp, 280h
0x180028a2f  mov     rax, cs:__security_cookie
0x180028a36  xor     rax, rsp
0x180028a39  mov     [rsp+298h+var_28], rax
0x180028a41  mov     rbx, r8
0x180028a44  mov     rsi, rdx
0x180028a47  mov     rdi, rcx
0x180028a4a  xor     edx, edx; Val
0x180028a4c  mov     r8d, 244h; Size
0x180028a52  lea     rcx, [rsp+298h+DeviceInstallParams.Flags]; void *
0x180028a57  call    memset_0
0x180028a5c  lea     r8, [rsp+298h+DeviceInstallParams]; DeviceInstallParams
0x180028a61  mov     [rsp+298h+DeviceInstallParams.cbSize], 248h
0x180028a69  mov     rdx, rsi; DeviceInfoData
0x180028a6c  mov     rcx, rdi; DeviceInfoSet
0x180028a6f  call    cs:__imp_SetupDiGetDeviceInstallParamsW
0x180028a75  xor     ecx, ecx
0x180028a77  test    eax, eax
0x180028a79  jz      short loc_180028AB0
0x180028a7b  or      [rsp+298h+DeviceInstallParams.Flags], 8000005h
0x180028a83  test    rbx, rbx
0x180028a86  jz      short loc_180028A9F
0x180028a88  cmp     [rbx], cx
0x180028a8b  jz      short loc_180028A9F
0x180028a8d  mov     r8, rbx; unsigned __int16 *
0x180028a90  lea     rcx, [rsp+298h+DeviceInstallParams.DriverPath]; unsigned __int16 *
0x180028a95  mov     edx, 104h; unsigned __int64
0x180028a9a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180028a9f  lea     r8, [rsp+298h+DeviceInstallParams]; DeviceInstallParams
0x180028aa4  mov     rdx, rsi; DeviceInfoData
0x180028aa7  mov     rcx, rdi; DeviceInfoSet
0x180028aaa  call    cs:__imp_SetupDiSetDeviceInstallParamsW
0x180028ab0  mov     rcx, [rsp+298h+var_28]
0x180028ab8  xor     rcx, rsp; StackCookie
0x180028abb  call    __security_check_cookie
0x180028ac0  add     rsp, 280h
0x180028ac7  pop     rdi
0x180028ac8  pop     rsi
0x180028ac9  pop     rbx
0x180028aca  retn
```
