# HrSetupDiSendPropertyChangeNotification(void *,_SP_DEVINFO_DATA *,ulong,ulong,ulong)

- ea: `0x180030ef8`
- end: `0x18003101b`
- name: `?HrSetupDiSendPropertyChangeNotification@@YAJPEAXPEAU_SP_DEVINFO_DATA@@KKK@Z`
- size: `291`
- prototype: `__int64 __fastcall(void *, struct _SP_DEVINFO_DATA *, unsigned int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x1800255b8`

## callees

- `0x180001710`
- `0x180002320`
- `0x18003060c`
- `0x180030c48`
- `0x180030ef8`
- `0x180031024`

## import_xrefs

- `SETUPAPI!SetupDiSetClassInstallParamsW` at `0x180030f50`
- `SETUPAPI!SetupDiSetClassInstallParamsW` at `0x180030f50`
- `SETUPAPI!SetupDiCallClassInstaller` at `0x180030fb8`
- `SETUPAPI!SetupDiCallClassInstaller` at `0x180030fb8`

## pseudocode

```c
__int64 __fastcall HrSetupDiSendPropertyChangeNotification(void *a1, struct _SP_DEVINFO_DATA *a2, int a3, int a4)
{
  int Win32Error; // ebx
  struct _SP_CLASSINSTALL_HEADER ClassInstallParams; // [rsp+20h] [rbp-E0h] BYREF
  int v9; // [rsp+28h] [rbp-D8h]
  int v10; // [rsp+2Ch] [rbp-D4h]
  int v11; // [rsp+30h] [rbp-D0h]
  _SP_DEVINSTALL_PARAMS_W DeviceInstallParams; // [rsp+40h] [rbp-C0h] BYREF

  v9 = a3;
  v10 = a4;
  ClassInstallParams.cbSize = 8;
  ClassInstallParams.InstallFunction = 18;
  v11 = 0;
  if ( SetupDiSetClassInstallParamsW(a1, a2, &ClassInstallParams, 0x14u)
    || (Win32Error = HrFromLastWin32Error(), Win32Error >= 0) )
  {
    memset_0(&DeviceInstallParams, 0, sizeof(DeviceInstallParams));
    Win32Error = HrSetupDiGetDeviceInstallParams(a1, a2, &DeviceInstallParams);
    if ( Win32Error >= 0 )
    {
      DeviceInstallParams.Flags |= 0x100000u;
      Win32Error = HrSetupDiSetDeviceInstallParams(a1, a2, &DeviceInstallParams);
      if ( Win32Error >= 0 )
      {
        Win32Error = 0;
        if ( !SetupDiCallClassInstaller(0x12u, a1, a2) )
        {
          Win32Error = HrFromLastWin32Error();
          if ( Win32Error == -2146500082 )
          {
            Win32Error = 0;
LABEL_9:
            HrSetupDiGetDeviceInstallParams(a1, a2, &DeviceInstallParams);
            DeviceInstallParams.Flags |= 0x4000u;
            HrSetupDiSetDeviceInstallParams(a1, a2, &DeviceInstallParams);
            return (unsigned int)Win32Error;
          }
        }
        if ( Win32Error >= 0 )
          goto LABEL_9;
      }
    }
  }
  return (unsigned int)Win32Error;
}

```

## disassembly

```asm
0x180030ef8  push    rbp
0x180030efa  push    rbx
0x180030efb  push    rsi
0x180030efc  push    rdi
0x180030efd  lea     rbp, [rsp-1A8h]
0x180030f05  sub     rsp, 2A8h
0x180030f0c  mov     rax, cs:__security_cookie
0x180030f13  xor     rax, rsp
0x180030f16  mov     [rbp+1C0h+var_30], rax
0x180030f1d  mov     [rsp+2C0h+var_298], r8d
0x180030f22  mov     rsi, rdx
0x180030f25  mov     [rsp+2C0h+var_294], r9d
0x180030f2a  lea     r8, [rsp+2C0h+ClassInstallParams]; ClassInstallParams
0x180030f2f  mov     r9d, 14h; ClassInstallParamsSize
0x180030f35  mov     [rsp+2C0h+ClassInstallParams.cbSize], 8
0x180030f3d  mov     rdi, rcx
0x180030f40  mov     [rsp+2C0h+ClassInstallParams.InstallFunction], 12h
0x180030f48  mov     [rsp+2C0h+var_290], 0
0x180030f50  call    cs:__imp_SetupDiSetClassInstallParamsW
0x180030f56  test    eax, eax
0x180030f58  jnz     short loc_180030F69
0x180030f5a  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180030f5f  mov     ebx, eax
0x180030f61  test    eax, eax
0x180030f63  js      loc_180030FFE
0x180030f69  xor     edx, edx; Val
0x180030f6b  lea     rcx, [rsp+2C0h+DeviceInstallParams]; void *
0x180030f70  mov     r8d, 248h; Size
0x180030f76  call    memset_0
0x180030f7b  lea     r8, [rsp+2C0h+DeviceInstallParams]; DeviceInstallParams
0x180030f80  mov     rdx, rsi; DeviceInfoData
0x180030f83  mov     rcx, rdi; DeviceInfoSet
0x180030f86  call    ?HrSetupDiGetDeviceInstallParams@@YAJQEAXQEAU_SP_DEVINFO_DATA@@PEAU_SP_DEVINSTALL_PARAMS_W@@@Z; HrSetupDiGetDeviceInstallParams(void * const,_SP_DEVINFO_DATA * const,_SP_DEVINSTALL_PARAMS_W *)
0x180030f8b  mov     ebx, eax
0x180030f8d  test    eax, eax
0x180030f8f  js      short loc_180030FFE
0x180030f91  bts     [rsp+2C0h+DeviceInstallParams.Flags], 14h
0x180030f97  lea     r8, [rsp+2C0h+DeviceInstallParams]; struct _SP_DEVINSTALL_PARAMS_W *
0x180030f9c  mov     rdx, rsi; struct _SP_DEVINFO_DATA *
0x180030f9f  mov     rcx, rdi; void *
0x180030fa2  call    ?HrSetupDiSetDeviceInstallParams@@YAJQEAXQEAU_SP_DEVINFO_DATA@@QEAU_SP_DEVINSTALL_PARAMS_W@@@Z; HrSetupDiSetDeviceInstallParams(void * const,_SP_DEVINFO_DATA * const,_SP_DEVINSTALL_PARAMS_W * const)
0x180030fa7  mov     ebx, eax
0x180030fa9  test    eax, eax
0x180030fab  js      short loc_180030FFE
0x180030fad  xor     ebx, ebx
0x180030faf  mov     r8, rsi; DeviceInfoData
0x180030fb2  mov     rdx, rdi; DeviceInfoSet
0x180030fb5  lea     ecx, [rbx+12h]; InstallFunction
0x180030fb8  call    cs:__imp_SetupDiCallClassInstaller
0x180030fbe  test    eax, eax
0x180030fc0  jnz     short loc_180030FD4
0x180030fc2  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180030fc7  mov     ebx, eax
0x180030fc9  cmp     eax, 800F020Eh
0x180030fce  jnz     short loc_180030FD4
0x180030fd0  xor     ebx, ebx
0x180030fd2  jmp     short loc_180030FD8
0x180030fd4  test    ebx, ebx
0x180030fd6  js      short loc_180030FFE
0x180030fd8  lea     r8, [rsp+2C0h+DeviceInstallParams]; DeviceInstallParams
0x180030fdd  mov     rdx, rsi; DeviceInfoData
0x180030fe0  mov     rcx, rdi; DeviceInfoSet
0x180030fe3  call    ?HrSetupDiGetDeviceInstallParams@@YAJQEAXQEAU_SP_DEVINFO_DATA@@PEAU_SP_DEVINSTALL_PARAMS_W@@@Z; HrSetupDiGetDeviceInstallParams(void * const,_SP_DEVINFO_DATA * const,_SP_DEVINSTALL_PARAMS_W *)
0x180030fe8  bts     [rsp+2C0h+DeviceInstallParams.Flags], 0Eh
0x180030fee  lea     r8, [rsp+2C0h+DeviceInstallParams]; struct _SP_DEVINSTALL_PARAMS_W *
0x180030ff3  mov     rdx, rsi; struct _SP_DEVINFO_DATA *
0x180030ff6  mov     rcx, rdi; void *
0x180030ff9  call    ?HrSetupDiSetDeviceInstallParams@@YAJQEAXQEAU_SP_DEVINFO_DATA@@QEAU_SP_DEVINSTALL_PARAMS_W@@@Z; HrSetupDiSetDeviceInstallParams(void * const,_SP_DEVINFO_DATA * const,_SP_DEVINSTALL_PARAMS_W * const)
0x180030ffe  mov     eax, ebx
0x180031000  mov     rcx, [rbp+1C0h+var_30]
0x180031007  xor     rcx, rsp; StackCookie
0x18003100a  call    __security_check_cookie
0x18003100f  add     rsp, 2A8h
0x180031016  pop     rdi
0x180031017  pop     rsi
0x180031018  pop     rbx
0x180031019  pop     rbp
0x18003101a  retn
```
