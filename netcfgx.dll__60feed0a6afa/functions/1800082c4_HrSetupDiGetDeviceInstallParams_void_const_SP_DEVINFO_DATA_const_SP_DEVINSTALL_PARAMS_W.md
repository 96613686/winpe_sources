# HrSetupDiGetDeviceInstallParams(void * const,_SP_DEVINFO_DATA * const,_SP_DEVINSTALL_PARAMS_W *)

- ea: `0x1800082c4`
- end: `0x180008314`
- name: `?HrSetupDiGetDeviceInstallParams@@YAJQEAXQEAU_SP_DEVINFO_DATA@@PEAU_SP_DEVINSTALL_PARAMS_W@@@Z`
- size: `80`
- prototype: `__int64 __fastcall(HDEVINFO DeviceInfoSet, PSP_DEVINFO_DATA DeviceInfoData, PSP_DEVINSTALL_PARAMS_W DeviceInstallParams)`
- caller_count: `3`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x1800070a8`
- `0x18000844c`
- `0x180008cc0`

## callees

- `0x180002a40`
- `0x180007f3c`
- `0x1800082c4`

## import_xrefs

- `SETUPAPI!SetupDiGetDeviceInstallParamsW` at `0x1800082f8`
- `SETUPAPI!SetupDiGetDeviceInstallParamsW` at `0x1800082f8`

## pseudocode

```c
__int64 __fastcall HrSetupDiGetDeviceInstallParams(
        HDEVINFO DeviceInfoSet,
        PSP_DEVINFO_DATA DeviceInfoData,
        PSP_DEVINSTALL_PARAMS_W DeviceInstallParams)
{
  unsigned int v6; // ebp

  v6 = 0;
  memset_0(&DeviceInstallParams->Flags, 0, 0x244u);
  DeviceInstallParams->cbSize = 584;
  if ( !SetupDiGetDeviceInstallParamsW(DeviceInfoSet, DeviceInfoData, DeviceInstallParams) )
    return (unsigned int)HrFromLastWin32Error();
  return v6;
}

```

## disassembly

```asm
0x1800082c4  push    rbx
0x1800082c6  push    rbp
0x1800082c7  push    rsi
0x1800082c8  push    rdi
0x1800082c9  sub     rsp, 28h
0x1800082cd  mov     rsi, rcx
0x1800082d0  mov     rbx, r8
0x1800082d3  lea     rcx, [r8+4]; void *
0x1800082d7  mov     rdi, rdx
0x1800082da  mov     r8d, 244h; Size
0x1800082e0  xor     edx, edx; Val
0x1800082e2  xor     ebp, ebp
0x1800082e4  call    memset_0
0x1800082e9  mov     r8, rbx; DeviceInstallParams
0x1800082ec  mov     dword ptr [rbx], 248h
0x1800082f2  mov     rdx, rdi; DeviceInfoData
0x1800082f5  mov     rcx, rsi; DeviceInfoSet
0x1800082f8  call    cs:__imp_SetupDiGetDeviceInstallParamsW
0x1800082fe  test    eax, eax
0x180008300  jnz     short loc_180008309
0x180008302  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180008307  mov     ebp, eax
0x180008309  mov     eax, ebp
0x18000830b  add     rsp, 28h
0x18000830f  pop     rdi
0x180008310  pop     rsi
0x180008311  pop     rbp
0x180008312  pop     rbx
0x180008313  retn
```
