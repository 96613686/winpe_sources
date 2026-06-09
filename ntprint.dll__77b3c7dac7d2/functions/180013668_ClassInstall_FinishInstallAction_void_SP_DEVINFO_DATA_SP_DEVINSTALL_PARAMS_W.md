# ClassInstall_FinishInstallAction(void *,_SP_DEVINFO_DATA *,_SP_DEVINSTALL_PARAMS_W *)

- ea: `0x180013668`
- end: `0x1800137fd`
- name: `?ClassInstall_FinishInstallAction@@YAKPEAXPEAU_SP_DEVINFO_DATA@@PEAU_SP_DEVINSTALL_PARAMS_W@@@Z`
- size: `405`
- prototype: `unsigned int __fastcall(HDEVINFO DeviceInfoSet, PSP_DEVINFO_DATA DeviceInfoData, struct _SP_DEVINSTALL_PARAMS_W *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callers

- `0x180013260`

## callees

- `0x180002300`
- `0x18000d624`
- `0x180013050`
- `0x180013668`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800137a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800137a1`
- `SETUPAPI!SetupDiGetDevicePropertyW` at `0x180013706`
- `SETUPAPI!SetupDiGetDevicePropertyW` at `0x180013754`
- `SETUPAPI!SetupDiGetDevicePropertyW` at `0x180013706`
- `SETUPAPI!SetupDiGetDevicePropertyW` at `0x180013754`
- `WINSPOOL!OpenPrinterW` at `0x180013774`
- `WINSPOOL!OpenPrinterW` at `0x180013774`
- `WINSPOOL!ClosePrinter` at `0x180013799`
- `WINSPOOL!ClosePrinter` at `0x180013799`

## string_xrefs

- `0x1800136b6`: `ClassInstall_FinishInstallAction - Enter.`
- `0x1800136bd`: `ClassInstall_FinishInstallAction`
- `0x1800137cb`: `ClassInstall_FinishInstallAction`
- `0x1800137c4`: `ClassInstall_FinishInstallAction - Exit: %d`

## pseudocode

```c
__int64 __fastcall ClassInstall_FinishInstallAction(
        HDEVINFO DeviceInfoSet,
        PSP_DEVINFO_DATA DeviceInfoData,
        struct _SP_DEVINSTALL_PARAMS_W *a3)
{
  DWORD LastError; // ebx
  DEVPROPTYPE PropertyType; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE phPrinter; // [rsp+48h] [rbp-B8h] BYREF
  struct _PRINTER_DEFAULTSW pDefault; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR v10[264]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 PropertyBuffer[264]; // [rsp+280h] [rbp+180h] BYREF

  PropertyType = 0;
  phPrinter = 0;
  *(_QWORD *)&pDefault.DesiredAccess = 983052;
  *(_OWORD *)&pDefault.pDatatype = 0;
  ClassInstallerTelemetry::WriteDbgTraceInfo(
    "ClassInstall_FinishInstallAction",
    L"ClassInstall_FinishInstallAction - Enter.",
    a3);
  if ( SetupDiGetDevicePropertyW(
         DeviceInfoSet,
         DeviceInfoData,
         &PropertyKey,
         &PropertyType,
         (PBYTE)PropertyBuffer,
         0x208u,
         0,
         0)
    && PropertyType == 18
    && SetupDiGetDevicePropertyW(
         DeviceInfoSet,
         DeviceInfoData,
         &stru_1800418A8,
         &PropertyType,
         (PBYTE)v10,
         0x208u,
         0,
         0)
    && PropertyType == 18
    && OpenPrinterW(v10, &phPrinter, &pDefault) )
  {
    LastError = -536870386;
    CallVendorDll(PropertyBuffer, v10);
    ClosePrinter(phPrinter);
  }
  else
  {
    LastError = GetLastError();
    if ( LastError == 1168 )
    {
      LastError = -536870386;
    }
    else if ( !LastError )
    {
      LastError = 87;
    }
  }
  ClassInstallerTelemetry::WriteDbgTraceInfo(
    "ClassInstall_FinishInstallAction",
    L"ClassInstall_FinishInstallAction - Exit: %d",
    LastError);
  return LastError;
}

```

## disassembly

```asm
0x180013668  mov     [rsp-8+arg_10], rbx
0x18001366d  mov     [rsp-8+arg_18], rdi
0x180013672  push    rbp
0x180013673  lea     rbp, [rsp-3A0h]
0x18001367b  sub     rsp, 4A0h
0x180013682  mov     rax, cs:__security_cookie
0x180013689  xor     rax, rsp
0x18001368c  mov     [rbp+3A0h+var_10], rax
0x180013693  mov     rdi, rdx
0x180013696  mov     [rsp+4A0h+PropertyType], 0
0x18001369e  mov     rbx, rcx
0x1800136a1  mov     [rsp+4A0h+phPrinter], 0
0x1800136aa  xorps   xmm0, xmm0
0x1800136ad  mov     qword ptr [rsp+4A0h+pDefault.DesiredAccess], 0F000Ch
0x1800136b6  lea     rdx, aClassinstallFi; "ClassInstall_FinishInstallAction - Ente"...
0x1800136bd  lea     rcx, aClassinstallFi_0; "ClassInstall_FinishInstallAction"
0x1800136c4  movdqu  xmmword ptr [rsp+4A0h+pDefault.pDatatype], xmm0
0x1800136ca  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800136cf  mov     [rsp+4A0h+Flags], 0; Flags
0x1800136d7  lea     rax, [rbp+3A0h+var_220]
0x1800136de  mov     [rsp+4A0h+RequiredSize], 0; RequiredSize
0x1800136e7  lea     r9, [rsp+4A0h+PropertyType]; PropertyType
0x1800136ec  mov     [rsp+4A0h+PropertyBufferSize], 208h; PropertyBufferSize
0x1800136f4  lea     r8, PropertyKey; PropertyKey
0x1800136fb  mov     rdx, rdi; DeviceInfoData
0x1800136fe  mov     [rsp+4A0h+PropertyBuffer], rax; PropertyBuffer
0x180013703  mov     rcx, rbx; DeviceInfoSet
0x180013706  call    cs:__imp_SetupDiGetDevicePropertyW
0x18001370c  test    eax, eax
0x18001370e  jz      loc_1800137A1
0x180013714  cmp     [rsp+4A0h+PropertyType], 12h
0x180013719  jnz     loc_1800137A1
0x18001371f  mov     [rsp+4A0h+Flags], 0; Flags
0x180013727  lea     rax, [rsp+4A0h+var_430]
0x18001372c  mov     [rsp+4A0h+RequiredSize], 0; RequiredSize
0x180013735  lea     r9, [rsp+4A0h+PropertyType]; PropertyType
0x18001373a  mov     [rsp+4A0h+PropertyBufferSize], 208h; PropertyBufferSize
0x180013742  lea     r8, stru_1800418A8; PropertyKey
0x180013749  mov     rdx, rdi; DeviceInfoData
0x18001374c  mov     [rsp+4A0h+PropertyBuffer], rax; PropertyBuffer
0x180013751  mov     rcx, rbx; DeviceInfoSet
0x180013754  call    cs:__imp_SetupDiGetDevicePropertyW
0x18001375a  test    eax, eax
0x18001375c  jz      short loc_1800137A1
0x18001375e  cmp     [rsp+4A0h+PropertyType], 12h
0x180013763  jnz     short loc_1800137A1
0x180013765  lea     r8, [rsp+4A0h+pDefault]; pDefault
0x18001376a  lea     rdx, [rsp+4A0h+phPrinter]; phPrinter
0x18001376f  lea     rcx, [rsp+4A0h+var_430]; pPrinterName
0x180013774  call    cs:__imp_OpenPrinterW
0x18001377a  test    eax, eax
0x18001377c  jz      short loc_1800137A1
0x18001377e  lea     rdx, [rsp+4A0h+var_430]; unsigned __int16 *
0x180013783  mov     ebx, 0E000020Eh
0x180013788  lea     rcx, [rbp+3A0h+var_220]; unsigned __int16 *
0x18001378f  call    ?CallVendorDll@@YAXPEBG0@Z; CallVendorDll(ushort const *,ushort const *)
0x180013794  mov     rcx, [rsp+4A0h+phPrinter]; hPrinter
0x180013799  call    cs:__imp_ClosePrinter
0x18001379f  jmp     short loc_1800137C1
0x1800137a1  call    cs:__imp_GetLastError
0x1800137a7  mov     ebx, eax
0x1800137a9  cmp     eax, 490h
0x1800137ae  jnz     short loc_1800137B7
0x1800137b0  mov     ebx, 0E000020Eh
0x1800137b5  jmp     short loc_1800137C1
0x1800137b7  test    ebx, ebx
0x1800137b9  mov     eax, 57h ; 'W'
0x1800137be  cmovz   ebx, eax
0x1800137c1  mov     r8d, ebx
0x1800137c4  lea     rdx, aClassinstallFi_1; "ClassInstall_FinishInstallAction - Exit"...
0x1800137cb  lea     rcx, aClassinstallFi_0; "ClassInstall_FinishInstallAction"
0x1800137d2  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800137d7  mov     eax, ebx
0x1800137d9  mov     rcx, [rbp+3A0h+var_10]
0x1800137e0  xor     rcx, rsp; StackCookie
0x1800137e3  call    __security_check_cookie
0x1800137e8  lea     r11, [rsp+4A0h+var_s0]
0x1800137f0  mov     rbx, [r11+20h]
0x1800137f4  mov     rdi, [r11+28h]
0x1800137f8  mov     rsp, r11
0x1800137fb  pop     rbp
0x1800137fc  retn
```
