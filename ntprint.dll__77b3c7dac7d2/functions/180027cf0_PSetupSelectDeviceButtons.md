# PSetupSelectDeviceButtons

- ea: `0x180027cf0`
- end: `0x180027dc5`
- name: `PSetupSelectDeviceButtons`
- size: `213`
- prototype: `__int64 __fastcall(HDEVINFO DeviceInfoSet)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x180002300`
- `0x180002f48`
- `0x180027cf0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180027d38`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180027d38`
- `SETUPAPI!SetupDiSetDeviceInstallParamsW` at `0x180027da4`
- `SETUPAPI!SetupDiSetDeviceInstallParamsW` at `0x180027da4`
- `SETUPAPI!SetupDiGetDeviceInstallParamsW` at `0x180027d54`
- `SETUPAPI!SetupDiGetDeviceInstallParamsW` at `0x180027d54`

## pseudocode

```c
BOOL __fastcall PSetupSelectDeviceButtons(HDEVINFO DeviceInfoSet, int a2, int a3)
{
  DWORD FlagsEx; // eax
  DWORD Flags; // eax
  struct _SP_DEVINSTALL_PARAMS_W DeviceInstallParams; // [rsp+20h] [rbp-E0h] BYREF

  memset_0(&DeviceInstallParams.Flags, 0, 0x244u);
  if ( (a2 & a3) != 0 )
  {
    SetLastError(0x57u);
    return 0;
  }
  DeviceInstallParams.cbSize = 584;
  if ( !SetupDiGetDeviceInstallParamsW(DeviceInfoSet, 0, &DeviceInstallParams) )
    return 0;
  FlagsEx = DeviceInstallParams.FlagsEx;
  if ( (a2 & 2) != 0 )
  {
    FlagsEx = DeviceInstallParams.FlagsEx | 0x400000;
    DeviceInstallParams.FlagsEx |= 0x400000u;
  }
  if ( (a3 & 2) != 0 )
    DeviceInstallParams.FlagsEx = FlagsEx & 0xFFBFFFFF;
  Flags = DeviceInstallParams.Flags;
  if ( (a2 & 1) != 0 )
  {
    Flags = DeviceInstallParams.Flags | 1;
    DeviceInstallParams.Flags |= 1u;
  }
  if ( (a3 & 1) != 0 )
    DeviceInstallParams.Flags = Flags & 0xFFFFFFFE;
  return SetupDiSetDeviceInstallParamsW(DeviceInfoSet, 0, &DeviceInstallParams);
}

```

## disassembly

```asm
0x180027cf0  push    rbp
0x180027cf2  push    rbx
0x180027cf3  push    rsi
0x180027cf4  push    rdi
0x180027cf5  lea     rbp, [rsp-188h]
0x180027cfd  sub     rsp, 288h
0x180027d04  mov     rax, cs:__security_cookie
0x180027d0b  xor     rax, rsp
0x180027d0e  mov     [rbp+1A0h+var_30], rax
0x180027d15  mov     edi, r8d
0x180027d18  mov     ebx, edx
0x180027d1a  mov     rsi, rcx
0x180027d1d  xor     edx, edx; Val
0x180027d1f  mov     r8d, 244h; Size
0x180027d25  lea     rcx, [rsp+2A0h+DeviceInstallParams.Flags]; void *
0x180027d2a  call    memset_0
0x180027d2f  test    edi, ebx
0x180027d31  jz      short loc_180027D42
0x180027d33  mov     ecx, 57h ; 'W'; dwErrCode
0x180027d38  call    cs:__imp_SetLastError
0x180027d3e  xor     eax, eax
0x180027d40  jmp     short loc_180027DAA
0x180027d42  lea     r8, [rsp+2A0h+DeviceInstallParams]; DeviceInstallParams
0x180027d47  mov     [rsp+2A0h+DeviceInstallParams.cbSize], 248h
0x180027d4f  xor     edx, edx; DeviceInfoData
0x180027d51  mov     rcx, rsi; DeviceInfoSet
0x180027d54  call    cs:__imp_SetupDiGetDeviceInstallParamsW
0x180027d5a  test    eax, eax
0x180027d5c  jz      short loc_180027D3E
0x180027d5e  mov     eax, [rsp+2A0h+DeviceInstallParams.FlagsEx]
0x180027d62  test    bl, 2
0x180027d65  jz      short loc_180027D6F
0x180027d67  bts     eax, 16h
0x180027d6b  mov     [rsp+2A0h+DeviceInstallParams.FlagsEx], eax
0x180027d6f  test    dil, 2
0x180027d73  jz      short loc_180027D7D
0x180027d75  btr     eax, 16h
0x180027d79  mov     [rsp+2A0h+DeviceInstallParams.FlagsEx], eax
0x180027d7d  mov     eax, [rsp+2A0h+DeviceInstallParams.Flags]
0x180027d81  test    bl, 1
0x180027d84  jz      short loc_180027D8D
0x180027d86  or      eax, 1
0x180027d89  mov     [rsp+2A0h+DeviceInstallParams.Flags], eax
0x180027d8d  test    dil, 1
0x180027d91  jz      short loc_180027D9A
0x180027d93  and     eax, 0FFFFFFFEh
0x180027d96  mov     [rsp+2A0h+DeviceInstallParams.Flags], eax
0x180027d9a  lea     r8, [rsp+2A0h+DeviceInstallParams]; DeviceInstallParams
0x180027d9f  xor     edx, edx; DeviceInfoData
0x180027da1  mov     rcx, rsi; DeviceInfoSet
0x180027da4  call    cs:__imp_SetupDiSetDeviceInstallParamsW
0x180027daa  mov     rcx, [rbp+1A0h+var_30]
0x180027db1  xor     rcx, rsp; StackCookie
0x180027db4  call    __security_check_cookie
0x180027db9  add     rsp, 288h
0x180027dc0  pop     rdi
0x180027dc1  pop     rsi
0x180027dc2  pop     rbx
0x180027dc3  pop     rbp
0x180027dc4  retn
```
