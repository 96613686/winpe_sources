# ClassInstall_NewDevFinishInstall(void *,_SP_DEVINFO_DATA *,_SP_DEVINSTALL_PARAMS_W *)

- ea: `0x180014330`
- end: `0x180014424`
- name: `?ClassInstall_NewDevFinishInstall@@YAKPEAXPEAU_SP_DEVINFO_DATA@@PEAU_SP_DEVINSTALL_PARAMS_W@@@Z`
- size: `244`
- prototype: `unsigned int __fastcall(HDEVINFO DeviceInfoSet, PSP_DEVINFO_DATA DeviceInfoData, PSP_DEVINSTALL_PARAMS_W DeviceInstallParams)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180013260`

## callees

- `0x180002300`
- `0x18000d624`
- `0x180014330`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800143d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800143d7`
- `SETUPAPI!SetupDiGetDevicePropertyW` at `0x1800143af`
- `SETUPAPI!SetupDiGetDevicePropertyW` at `0x1800143af`
- `SETUPAPI!SetupDiSetDeviceInstallParamsW` at `0x1800143cd`
- `SETUPAPI!SetupDiSetDeviceInstallParamsW` at `0x1800143cd`

## string_xrefs

- `0x18001435f`: `ClassInstall_NewDevFinishInstall - Enter.`
- `0x180014366`: `ClassInstall_NewDevFinishInstall`
- `0x1800143f3`: `ClassInstall_NewDevFinishInstall`
- `0x1800143ec`: `ClassInstall_NewDevFinishInstall - Exit: %d`

## pseudocode

```c
__int64 __fastcall ClassInstall_NewDevFinishInstall(
        HDEVINFO DeviceInfoSet,
        PSP_DEVINFO_DATA DeviceInfoData,
        PSP_DEVINSTALL_PARAMS_W DeviceInstallParams)
{
  DWORD LastError; // ebx
  DEVPROPTYPE PropertyType[4]; // [rsp+40h] [rbp-248h] BYREF
  BYTE PropertyBuffer[528]; // [rsp+50h] [rbp-238h] BYREF

  PropertyType[0] = 0;
  LastError = -536870386;
  ClassInstallerTelemetry::WriteDbgTraceInfo(
    "ClassInstall_NewDevFinishInstall",
    L"ClassInstall_NewDevFinishInstall - Enter.");
  if ( SetupDiGetDevicePropertyW(
         DeviceInfoSet,
         DeviceInfoData,
         &PropertyKey,
         PropertyType,
         PropertyBuffer,
         0x208u,
         0,
         0) )
  {
    if ( PropertyType[0] == 18 )
    {
      DeviceInstallParams->FlagsEx |= 8u;
      if ( !SetupDiSetDeviceInstallParamsW(DeviceInfoSet, DeviceInfoData, DeviceInstallParams) )
      {
        LastError = GetLastError();
        if ( !LastError )
          LastError = 87;
      }
    }
  }
  ClassInstallerTelemetry::WriteDbgTraceInfo(
    "ClassInstall_NewDevFinishInstall",
    L"ClassInstall_NewDevFinishInstall - Exit: %d",
    LastError);
  return LastError;
}

```

## disassembly

```asm
0x180014330  mov     [rsp+arg_18], rbx
0x180014335  push    rbp
0x180014336  push    rsi
0x180014337  push    rdi
0x180014338  sub     rsp, 270h
0x18001433f  mov     rax, cs:__security_cookie
0x180014346  xor     rax, rsp
0x180014349  mov     [rsp+288h+var_28], rax
0x180014351  mov     rbp, rdx
0x180014354  mov     [rsp+288h+PropertyType], 0
0x18001435c  mov     rsi, rcx
0x18001435f  lea     rdx, aClassinstallNe; "ClassInstall_NewDevFinishInstall - Ente"...
0x180014366  lea     rcx, aClassinstallNe_0; "ClassInstall_NewDevFinishInstall"
0x18001436d  mov     rdi, r8
0x180014370  mov     ebx, 0E000020Eh
0x180014375  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18001437a  mov     [rsp+288h+Flags], 0; Flags
0x180014382  lea     rax, [rsp+288h+var_238]
0x180014387  mov     [rsp+288h+RequiredSize], 0; RequiredSize
0x180014390  lea     r9, [rsp+288h+PropertyType]; PropertyType
0x180014395  mov     [rsp+288h+PropertyBufferSize], 208h; PropertyBufferSize
0x18001439d  lea     r8, PropertyKey; PropertyKey
0x1800143a4  mov     rdx, rbp; DeviceInfoData
0x1800143a7  mov     [rsp+288h+PropertyBuffer], rax; PropertyBuffer
0x1800143ac  mov     rcx, rsi; DeviceInfoSet
0x1800143af  call    cs:__imp_SetupDiGetDevicePropertyW
0x1800143b5  test    eax, eax
0x1800143b7  jz      short loc_1800143E9
0x1800143b9  cmp     [rsp+288h+PropertyType], 12h
0x1800143be  jnz     short loc_1800143E9
0x1800143c0  or      dword ptr [rdi+8], 8
0x1800143c4  mov     r8, rdi; DeviceInstallParams
0x1800143c7  mov     rdx, rbp; DeviceInfoData
0x1800143ca  mov     rcx, rsi; DeviceInfoSet
0x1800143cd  call    cs:__imp_SetupDiSetDeviceInstallParamsW
0x1800143d3  test    eax, eax
0x1800143d5  jnz     short loc_1800143E9
0x1800143d7  call    cs:__imp_GetLastError
0x1800143dd  mov     ebx, eax
0x1800143df  mov     eax, 57h ; 'W'
0x1800143e4  test    ebx, ebx
0x1800143e6  cmovz   ebx, eax
0x1800143e9  mov     r8d, ebx
0x1800143ec  lea     rdx, aClassinstallNe_1; "ClassInstall_NewDevFinishInstall - Exit"...
0x1800143f3  lea     rcx, aClassinstallNe_0; "ClassInstall_NewDevFinishInstall"
0x1800143fa  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800143ff  mov     eax, ebx
0x180014401  mov     rcx, [rsp+288h+var_28]
0x180014409  xor     rcx, rsp; StackCookie
0x18001440c  call    __security_check_cookie
0x180014411  mov     rbx, [rsp+288h+arg_18]
0x180014419  add     rsp, 270h
0x180014420  pop     rdi
0x180014421  pop     rsi
0x180014422  pop     rbp
0x180014423  retn
```
