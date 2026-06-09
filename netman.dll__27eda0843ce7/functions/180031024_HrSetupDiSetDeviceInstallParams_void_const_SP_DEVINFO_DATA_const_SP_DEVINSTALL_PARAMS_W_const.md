# HrSetupDiSetDeviceInstallParams(void * const,_SP_DEVINFO_DATA * const,_SP_DEVINSTALL_PARAMS_W * const)

- ea: `0x180031024`
- end: `0x180031045`
- name: `?HrSetupDiSetDeviceInstallParams@@YAJQEAXQEAU_SP_DEVINFO_DATA@@QEAU_SP_DEVINSTALL_PARAMS_W@@@Z`
- size: `33`
- prototype: `__int64 __fastcall(void *const, struct _SP_DEVINFO_DATA *const, struct _SP_DEVINSTALL_PARAMS_W *const)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180030ef8`

## callees

- `0x18003060c`
- `0x180031024`

## import_xrefs

- `SETUPAPI!SetupDiSetDeviceInstallParamsW` at `0x18003102c`
- `SETUPAPI!SetupDiSetDeviceInstallParamsW` at `0x18003102c`

## pseudocode

```c
__int64 __fastcall HrSetupDiSetDeviceInstallParams(
        void *const a1,
        struct _SP_DEVINFO_DATA *const a2,
        struct _SP_DEVINSTALL_PARAMS_W *const a3)
{
  unsigned int v3; // ebx

  v3 = 0;
  if ( !SetupDiSetDeviceInstallParamsW(a1, a2, a3) )
    return (unsigned int)HrFromLastWin32Error();
  return v3;
}

```

## disassembly

```asm
0x180031024  push    rbx
0x180031026  sub     rsp, 20h
0x18003102a  xor     ebx, ebx
0x18003102c  call    cs:__imp_SetupDiSetDeviceInstallParamsW
0x180031032  test    eax, eax
0x180031034  jnz     short loc_18003103D
0x180031036  call    ?HrFromLastWin32Error@@YAJXZ; HrFromLastWin32Error(void)
0x18003103b  mov     ebx, eax
0x18003103d  mov     eax, ebx
0x18003103f  add     rsp, 20h
0x180031043  pop     rbx
0x180031044  retn
```
