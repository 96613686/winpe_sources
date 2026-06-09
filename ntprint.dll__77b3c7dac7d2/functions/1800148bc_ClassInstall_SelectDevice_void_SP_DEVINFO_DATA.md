# ClassInstall_SelectDevice(void *,_SP_DEVINFO_DATA *)

- ea: `0x1800148bc`
- end: `0x180014918`
- name: `?ClassInstall_SelectDevice@@YAKPEAXPEAU_SP_DEVINFO_DATA@@@Z`
- size: `92`
- prototype: `unsigned int __fastcall(HDEVINFO DeviceInfoSet, PSP_DEVINFO_DATA DeviceInfoData)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180013260`

## callees

- `0x18000d624`
- `0x1800148bc`
- `0x180028a24`
- `0x180028ad4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014907`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014907`

## string_xrefs

- `0x1800148cc`: `ClassInstall_SelectDevice - Enter`
- `0x1800148d3`: `ClassInstall_SelectDevice`

## pseudocode

```c
DWORD __fastcall ClassInstall_SelectDevice(HDEVINFO DeviceInfoSet, PSP_DEVINFO_DATA DeviceInfoData)
{
  ClassInstallerTelemetry::WriteDbgTraceInfo("ClassInstall_SelectDevice", L"ClassInstall_SelectDevice - Enter");
  if ( SetSelectDevParams(DeviceInfoSet, DeviceInfoData) && SetDevInstallParams(DeviceInfoSet, DeviceInfoData, 0) )
    return -536870386;
  else
    return GetLastError();
}

```

## disassembly

```asm
0x1800148bc  mov     [rsp+arg_0], rbx
0x1800148c1  push    rdi
0x1800148c2  sub     rsp, 20h
0x1800148c6  mov     rbx, rdx
0x1800148c9  mov     rdi, rcx
0x1800148cc  lea     rdx, aClassinstallSe_2; "ClassInstall_SelectDevice - Enter"
0x1800148d3  lea     rcx, aClassinstallSe_1; "ClassInstall_SelectDevice"
0x1800148da  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800148df  mov     rdx, rbx; DeviceInfoData
0x1800148e2  mov     rcx, rdi; DeviceInfoSet
0x1800148e5  call    SetSelectDevParams
0x1800148ea  test    eax, eax
0x1800148ec  jz      short loc_180014907
0x1800148ee  xor     r8d, r8d; unsigned __int16 *
0x1800148f1  mov     rdx, rbx; DeviceInfoData
0x1800148f4  mov     rcx, rdi; DeviceInfoSet
0x1800148f7  call    SetDevInstallParams
0x1800148fc  test    eax, eax
0x1800148fe  jz      short loc_180014907
0x180014900  mov     eax, 0E000020Eh
0x180014905  jmp     short loc_18001490D
0x180014907  call    cs:__imp_GetLastError
0x18001490d  mov     rbx, [rsp+28h+arg_0]
0x180014912  add     rsp, 20h
0x180014916  pop     rdi
0x180014917  retn
```
