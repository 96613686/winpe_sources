# ClassInstall_DestroyWizardData(void *,_SP_DEVINFO_DATA *,_SP_DEVINSTALL_PARAMS_W *)

- ea: `0x18001355c`
- end: `0x180013660`
- name: `?ClassInstall_DestroyWizardData@@YAKPEAXPEAU_SP_DEVINFO_DATA@@PEAU_SP_DEVINSTALL_PARAMS_W@@@Z`
- size: `260`
- prototype: `unsigned int __fastcall(HDEVINFO DeviceInfoSet, PSP_DEVINFO_DATA DeviceInfoData, struct _SP_DEVINSTALL_PARAMS_W *)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180013260`
- `0x1800141a4`

## callees

- `0x180002f48`
- `0x18000d624`
- `0x18001355c`
- `0x18003a010`

## import_xrefs

- `SETUPAPI!SetupDiGetClassInstallParamsW` at `0x1800135e0`
- `SETUPAPI!SetupDiGetClassInstallParamsW` at `0x1800135e0`

## string_xrefs

- `0x180013593`: `ClassInstall_DestroyWizardData - Enter`
- `0x18001359a`: `ClassInstall_DestroyWizardData`
- `0x18001363d`: `ClassInstall_DestroyWizardData`
- `0x180013636`: `ClassInstall_DestroyWizardData - Exit %d`

## pseudocode

```c
__int64 __fastcall ClassInstall_DestroyWizardData(
        HDEVINFO DeviceInfoSet,
        PSP_DEVINFO_DATA DeviceInfoData,
        struct _SP_DEVINSTALL_PARAMS_W *a3)
{
  __int64 v6; // rbx
  __int128 v8; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v9; // [rsp+40h] [rbp-C0h]
  _SP_CLASSINSTALL_HEADER ClassInstallParams; // [rsp+50h] [rbp-B0h] BYREF
  __int128 *v11; // [rsp+168h] [rbp+68h] BYREF

  memset_0(&ClassInstallParams, 0, 0xD0u);
  v11 = 0;
  v8 = 0;
  v9 = 0;
  ClassInstallerTelemetry::WriteDbgTraceInfo(
    "ClassInstall_DestroyWizardData",
    L"ClassInstall_DestroyWizardData - Enter");
  if ( !dwfnPnPInterface )
    return 3758096910LL;
  ClassInstallParams.cbSize = 8;
  if ( !SetupDiGetClassInstallParamsW(DeviceInfoSet, DeviceInfoData, &ClassInstallParams, 0xD0u, 0)
    || ClassInstallParams.InstallFunction != 17 )
  {
    return 3758096910LL;
  }
  LODWORD(v8) = 32;
  *(_QWORD *)&v9 = &ClassInstallParams;
  *((_QWORD *)&v9 + 1) = a3->ClassInstallReserved;
  v11 = &v8;
  *((_QWORD *)&v8 + 1) = 0;
  v6 = (unsigned int)((__int64 (__fastcall *)(__int64, __int128 **))dwfnPnPInterface)(2, &v11);
  ClassInstallerTelemetry::WriteDbgTraceInfo(
    "ClassInstall_DestroyWizardData",
    L"ClassInstall_DestroyWizardData - Exit %d",
    v6);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001355c  push    rbp
0x18001355e  push    rbx
0x18001355f  push    rsi
0x180013560  push    rdi
0x180013561  lea     rbp, [rsp-28h]
0x180013566  sub     rsp, 128h
0x18001356d  mov     rsi, r8
0x180013570  mov     rbx, rdx
0x180013573  mov     rdi, rcx
0x180013576  xor     edx, edx; Val
0x180013578  mov     r8d, 0D0h; Size
0x18001357e  lea     rcx, [rsp+140h+ClassInstallParams]; void *
0x180013583  call    memset_0
0x180013588  xorps   xmm0, xmm0
0x18001358b  mov     [rbp+40h+arg_18], 0
0x180013593  lea     rdx, aClassinstallDe_1; "ClassInstall_DestroyWizardData - Enter"
0x18001359a  lea     rcx, aClassinstallDe_0; "ClassInstall_DestroyWizardData"
0x1800135a1  movups  [rsp+140h+var_110], xmm0
0x1800135a6  movups  [rsp+140h+var_100], xmm0
0x1800135ab  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800135b0  cmp     cs:?dwfnPnPInterface@@3P6AKW4EPnPFunctionCode@@PEAT_TParameterBlock@@@ZEA, 0; ulong (*dwfnPnPInterface)(EPnPFunctionCode,_TParameterBlock *)
0x1800135b8  jz      loc_18001364F
0x1800135be  mov     r9d, 0D0h; ClassInstallParamsSize
0x1800135c4  mov     [rsp+140h+ClassInstallParams.cbSize], 8
0x1800135cc  lea     r8, [rsp+140h+ClassInstallParams]; ClassInstallParams
0x1800135d1  mov     [rsp+140h+RequiredSize], 0; RequiredSize
0x1800135da  mov     rdx, rbx; DeviceInfoData
0x1800135dd  mov     rcx, rdi; DeviceInfoSet
0x1800135e0  call    cs:__imp_SetupDiGetClassInstallParamsW
0x1800135e6  test    eax, eax
0x1800135e8  jz      short loc_18001364F
0x1800135ea  cmp     [rsp+140h+ClassInstallParams.InstallFunction], 11h
0x1800135ef  jnz     short loc_18001364F
0x1800135f1  lea     rax, [rsp+140h+ClassInstallParams]
0x1800135f6  mov     dword ptr [rsp+140h+var_110], 20h ; ' '
0x1800135fe  mov     qword ptr [rsp+140h+var_100], rax
0x180013603  lea     rdx, [rbp+40h+arg_18]
0x180013607  mov     rax, [rsi+30h]
0x18001360b  mov     ecx, 2
0x180013610  mov     qword ptr [rsp+140h+var_100+8], rax
0x180013615  lea     rax, [rsp+140h+var_110]
0x18001361a  mov     [rbp+40h+arg_18], rax
0x18001361e  mov     rax, cs:?dwfnPnPInterface@@3P6AKW4EPnPFunctionCode@@PEAT_TParameterBlock@@@ZEA; ulong (*dwfnPnPInterface)(EPnPFunctionCode,_TParameterBlock *)
0x180013625  mov     qword ptr [rsp+140h+var_110+8], 0
0x18001362e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013633  mov     r8d, eax
0x180013636  lea     rdx, aClassinstallDe; "ClassInstall_DestroyWizardData - Exit %"...
0x18001363d  lea     rcx, aClassinstallDe_0; "ClassInstall_DestroyWizardData"
0x180013644  mov     ebx, eax
0x180013646  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18001364b  mov     eax, ebx
0x18001364d  jmp     short loc_180013654
0x18001364f  mov     eax, 0E000020Eh
0x180013654  add     rsp, 128h
0x18001365b  pop     rdi
0x18001365c  pop     rsi
0x18001365d  pop     rbx
0x18001365e  pop     rbp
0x18001365f  retn
```
