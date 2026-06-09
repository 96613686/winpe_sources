# HrSetupDiGetDeviceInstallParams(void * const,_SP_DEVINFO_DATA * const,_SP_DEVINSTALL_PARAMS_W *)

- ea: `0x180030c48`
- end: `0x180030c98`
- name: `?HrSetupDiGetDeviceInstallParams@@YAJQEAXQEAU_SP_DEVINFO_DATA@@PEAU_SP_DEVINSTALL_PARAMS_W@@@Z`
- size: `80`
- prototype: `__int64 __fastcall(HDEVINFO DeviceInfoSet, PSP_DEVINFO_DATA DeviceInfoData, PSP_DEVINSTALL_PARAMS_W DeviceInstallParams)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180030ef8`

## callees

- `0x180002320`
- `0x18003060c`
- `0x180030c48`

## import_xrefs

- `SETUPAPI!SetupDiGetDeviceInstallParamsW` at `0x180030c7c`
- `SETUPAPI!SetupDiGetDeviceInstallParamsW` at `0x180030c7c`

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
0x180030c48  push    rbx
0x180030c4a  push    rbp
0x180030c4b  push    rsi
0x180030c4c  push    rdi
0x180030c4d  sub     rsp, 28h
0x180030c51  mov     rsi, rcx
0x180030c54  mov     rbx, r8
0x180030c57  lea     rcx, [r8+4]; void *
0x180030c5b  mov     rdi, rdx
0x180030c5e  mov     r8d, 244h; Size
0x180030c64  xor     edx, edx; Val
0x180030c66  xor     ebp, ebp
0x180030c68  call    memset_0
0x180030c6d  mov     r8, rbx; DeviceInstallParams
0x180030c70  mov     dword ptr [rbx], 248h
0x180030c76  mov     rdx, rdi; DeviceInfoData
0x180030c79  mov     rcx, rsi; DeviceInfoSet
0x180030c7c  call    cs:__imp_SetupDiGetDeviceInstallParamsW
0x180030c82  test    eax, eax
0x180030c84  jnz     short loc_180030C8D
0x180030c86  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180030c8b  mov     ebp, eax
0x180030c8d  mov     eax, ebp
0x180030c8f  add     rsp, 28h
0x180030c93  pop     rdi
0x180030c94  pop     rsi
0x180030c95  pop     rbp
0x180030c96  pop     rbx
0x180030c97  retn
```
