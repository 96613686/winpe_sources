# HrSetupDiGetFixedSizeClassInstallParams(void *,_SP_DEVINFO_DATA *,_SP_CLASSINSTALL_HEADER *,int)

- ea: `0x1800083e8`
- end: `0x180008446`
- name: `?HrSetupDiGetFixedSizeClassInstallParams@@YAJPEAXPEAU_SP_DEVINFO_DATA@@PEAU_SP_CLASSINSTALL_HEADER@@H@Z`
- size: `94`
- prototype: `__int64 __fastcall(HDEVINFO DeviceInfoSet, PSP_DEVINFO_DATA DeviceInfoData, PSP_CLASSINSTALL_HEADER ClassInstallParams, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180006ac4`
- `0x1800070a8`

## callees

- `0x180002a40`
- `0x180007f3c`
- `0x1800083e8`

## import_xrefs

- `SETUPAPI!SetupDiGetClassInstallParamsW` at `0x180008426`
- `SETUPAPI!SetupDiGetClassInstallParamsW` at `0x180008426`

## pseudocode

```c
__int64 __fastcall HrSetupDiGetFixedSizeClassInstallParams(
        HDEVINFO DeviceInfoSet,
        PSP_DEVINFO_DATA DeviceInfoData,
        PSP_CLASSINSTALL_HEADER ClassInstallParams,
        signed int a4)
{
  unsigned int v8; // r14d

  v8 = 0;
  memset_0(ClassInstallParams, 0, a4);
  ClassInstallParams->cbSize = 8;
  if ( !SetupDiGetClassInstallParamsW(DeviceInfoSet, DeviceInfoData, ClassInstallParams, a4, 0) )
    return (unsigned int)HrFromLastWin32Error();
  return v8;
}

```

## disassembly

```asm
0x1800083e8  push    rbx
0x1800083ea  push    rbp
0x1800083eb  push    rsi
0x1800083ec  push    rdi
0x1800083ed  push    r14
0x1800083ef  sub     rsp, 30h
0x1800083f3  mov     rdi, r8
0x1800083f6  movsxd  rbx, r9d
0x1800083f9  mov     rsi, rdx
0x1800083fc  mov     rbp, rcx
0x1800083ff  mov     r8, rbx; Size
0x180008402  mov     rcx, rdi; void *
0x180008405  xor     edx, edx; Val
0x180008407  xor     r14d, r14d
0x18000840a  call    memset_0
0x18000840f  mov     r9d, ebx; ClassInstallParamsSize
0x180008412  mov     dword ptr [rdi], 8
0x180008418  mov     r8, rdi; ClassInstallParams
0x18000841b  mov     [rsp+58h+RequiredSize], r14; RequiredSize
0x180008420  mov     rdx, rsi; DeviceInfoData
0x180008423  mov     rcx, rbp; DeviceInfoSet
0x180008426  call    cs:__imp_SetupDiGetClassInstallParamsW
0x18000842c  test    eax, eax
0x18000842e  jnz     short loc_180008438
0x180008430  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x180008435  mov     r14d, eax
0x180008438  mov     eax, r14d
0x18000843b  add     rsp, 30h
0x18000843f  pop     r14
0x180008441  pop     rdi
0x180008442  pop     rsi
0x180008443  pop     rbp
0x180008444  pop     rbx
0x180008445  retn
```
