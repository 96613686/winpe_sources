# HrSetupDiSetDeipFlags(void *,_SP_DEVINFO_DATA *,ulong,SD_DEID_FLAG_TYPE,SD_FLAGS_BINARY_OP)

- ea: `0x18000844c`
- end: `0x180008518`
- name: `?HrSetupDiSetDeipFlags@@YAJPEAXPEAU_SP_DEVINFO_DATA@@KW4SD_DEID_FLAG_TYPE@@W4SD_FLAGS_BINARY_OP@@@Z`
- size: `204`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x180006ecc`

## callees

- `0x180001f90`
- `0x180002a40`
- `0x180007f3c`
- `0x1800082c4`
- `0x18000844c`

## import_xrefs

- `SETUPAPI!SetupDiSetDeviceInstallParamsW` at `0x1800084dd`
- `SETUPAPI!SetupDiSetDeviceInstallParamsW` at `0x1800084dd`

## pseudocode

```c
__int64 __fastcall HrSetupDiSetDeipFlags(void *a1, struct _SP_DEVINFO_DATA *a2, int a3, int a4)
{
  unsigned int v8; // edi
  DWORD FlagsEx; // eax
  DWORD *p_FlagsEx; // rcx
  _SP_DEVINSTALL_PARAMS_W DeviceInstallParams; // [rsp+20h] [rbp-278h] BYREF

  memset_0(&DeviceInstallParams, 0, sizeof(DeviceInstallParams));
  v8 = HrSetupDiGetDeviceInstallParams(a1, a2, &DeviceInstallParams);
  if ( !v8 )
  {
    if ( a4 )
    {
      if ( a4 != 1 )
        return 2147942487LL;
      FlagsEx = DeviceInstallParams.FlagsEx;
      p_FlagsEx = &DeviceInstallParams.FlagsEx;
    }
    else
    {
      FlagsEx = DeviceInstallParams.Flags;
      p_FlagsEx = &DeviceInstallParams.Flags;
    }
    *p_FlagsEx = a3 | FlagsEx;
    v8 = 0;
    if ( !SetupDiSetDeviceInstallParamsW(a1, a2, &DeviceInstallParams) )
      return (unsigned int)HrFromLastWin32Error();
  }
  return v8;
}

```

## disassembly

```asm
0x18000844c  mov     [rsp+arg_10], rbx
0x180008451  mov     [rsp+arg_18], rbp
0x180008456  push    rsi
0x180008457  push    rdi
0x180008458  push    r14
0x18000845a  sub     rsp, 280h
0x180008461  mov     rax, cs:__security_cookie
0x180008468  xor     rax, rsp
0x18000846b  mov     [rsp+298h+var_28], rax
0x180008473  mov     r14d, r8d
0x180008476  mov     rbp, rdx
0x180008479  mov     rsi, rcx
0x18000847c  xor     edx, edx; Val
0x18000847e  mov     r8d, 248h; Size
0x180008484  lea     rcx, [rsp+298h+DeviceInstallParams]; void *
0x180008489  mov     ebx, r9d
0x18000848c  call    memset_0
0x180008491  lea     r8, [rsp+298h+DeviceInstallParams]; DeviceInstallParams
0x180008496  mov     rdx, rbp; DeviceInfoData
0x180008499  mov     rcx, rsi; DeviceInfoSet
0x18000849c  call    ?HrSetupDiGetDeviceInstallParams@@YAJQEAXQEAU_SP_DEVINFO_DATA@@PEAU_SP_DEVINSTALL_PARAMS_W@@@Z; HrSetupDiGetDeviceInstallParams(void * const,_SP_DEVINFO_DATA * const,_SP_DEVINSTALL_PARAMS_W *)
0x1800084a1  mov     edi, eax
0x1800084a3  test    eax, eax
0x1800084a5  jnz     short loc_1800084EE
0x1800084a7  test    ebx, ebx
0x1800084a9  jz      short loc_1800084C2
0x1800084ab  cmp     ebx, 1
0x1800084ae  jz      short loc_1800084B7
0x1800084b0  mov     eax, 80070057h
0x1800084b5  jmp     short loc_1800084F0
0x1800084b7  mov     eax, [rsp+298h+DeviceInstallParams.FlagsEx]
0x1800084bb  lea     rcx, [rsp+298h+DeviceInstallParams.FlagsEx]
0x1800084c0  jmp     short loc_1800084CB
0x1800084c2  mov     eax, [rsp+298h+DeviceInstallParams.Flags]
0x1800084c6  lea     rcx, [rsp+298h+DeviceInstallParams.Flags]
0x1800084cb  or      eax, r14d
0x1800084ce  lea     r8, [rsp+298h+DeviceInstallParams]; DeviceInstallParams
0x1800084d3  mov     [rcx], eax
0x1800084d5  mov     rdx, rbp; DeviceInfoData
0x1800084d8  mov     rcx, rsi; DeviceInfoSet
0x1800084db  xor     edi, edi
0x1800084dd  call    cs:__imp_SetupDiSetDeviceInstallParamsW
0x1800084e3  test    eax, eax
0x1800084e5  jnz     short loc_1800084EE
0x1800084e7  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x1800084ec  mov     edi, eax
0x1800084ee  mov     eax, edi
0x1800084f0  mov     rcx, [rsp+298h+var_28]
0x1800084f8  xor     rcx, rsp; StackCookie
0x1800084fb  call    __security_check_cookie
0x180008500  lea     r11, [rsp+298h+var_18]
0x180008508  mov     rbx, [r11+30h]
0x18000850c  mov     rbp, [r11+38h]
0x180008510  mov     rsp, r11
0x180008513  pop     r14
0x180008515  pop     rdi
0x180008516  pop     rsi
0x180008517  retn
```
