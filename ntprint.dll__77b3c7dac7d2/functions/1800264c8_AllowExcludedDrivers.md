# AllowExcludedDrivers

- ea: `0x1800264c8`
- end: `0x18002657d`
- name: `AllowExcludedDrivers`
- size: `181`
- prototype: `__int64 __fastcall(HDEVINFO DeviceInfoSet)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180011c70`
- `0x180026df0`

## callees

- `0x180002300`
- `0x180002f48`
- `0x18000d57c`
- `0x1800264c8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002653e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002653e`
- `SETUPAPI!SetupDiSetDeviceInstallParamsW` at `0x180026532`
- `SETUPAPI!SetupDiSetDeviceInstallParamsW` at `0x180026532`
- `SETUPAPI!SetupDiGetDeviceInstallParamsW` at `0x180026516`
- `SETUPAPI!SetupDiGetDeviceInstallParamsW` at `0x180026516`

## pseudocode

```c
__int64 __fastcall AllowExcludedDrivers(HDEVINFO DeviceInfoSet)
{
  unsigned int DeviceInstallParamsW; // ebx
  DWORD LastError; // eax
  struct _SP_DEVINSTALL_PARAMS_W DeviceInstallParams; // [rsp+20h] [rbp-268h] BYREF

  memset_0(&DeviceInstallParams, 0, sizeof(DeviceInstallParams));
  if ( DeviceInfoSet == (HDEVINFO)-1LL )
  {
    DeviceInstallParamsW = 0;
LABEL_5:
    LastError = GetLastError();
    ClassInstallerTelemetry::WriteDbgTraceError(
      "AllowExcludedDrivers",
      L"Error allowing enumeration of drivers marked with AlwaysExcludeFromSelect: %d",
      LastError);
    return DeviceInstallParamsW;
  }
  DeviceInstallParams.cbSize = 584;
  DeviceInstallParamsW = SetupDiGetDeviceInstallParamsW(DeviceInfoSet, 0, &DeviceInstallParams);
  if ( !DeviceInstallParamsW )
    goto LABEL_5;
  DeviceInstallParams.FlagsEx |= 0x800u;
  DeviceInstallParamsW = SetupDiSetDeviceInstallParamsW(DeviceInfoSet, 0, &DeviceInstallParams);
  if ( !DeviceInstallParamsW )
    goto LABEL_5;
  return DeviceInstallParamsW;
}

```

## disassembly

```asm
0x1800264c8  mov     [rsp+arg_8], rbx
0x1800264cd  push    rdi
0x1800264ce  sub     rsp, 280h
0x1800264d5  mov     rax, cs:__security_cookie
0x1800264dc  xor     rax, rsp
0x1800264df  mov     [rsp+288h+var_18], rax
0x1800264e7  mov     rdi, rcx
0x1800264ea  mov     ebx, 248h
0x1800264ef  mov     r8d, ebx; Size
0x1800264f2  lea     rcx, [rsp+288h+DeviceInstallParams]; void *
0x1800264f7  xor     edx, edx; Val
0x1800264f9  call    memset_0
0x1800264fe  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180026502  jnz     short loc_180026508
0x180026504  xor     ebx, ebx
0x180026506  jmp     short loc_18002653E
0x180026508  lea     r8, [rsp+288h+DeviceInstallParams]; DeviceInstallParams
0x18002650d  mov     [rsp+288h+DeviceInstallParams.cbSize], ebx
0x180026511  xor     edx, edx; DeviceInfoData
0x180026513  mov     rcx, rdi; DeviceInfoSet
0x180026516  call    cs:__imp_SetupDiGetDeviceInstallParamsW
0x18002651c  mov     ebx, eax
0x18002651e  test    eax, eax
0x180026520  jz      short loc_18002653E
0x180026522  bts     [rsp+288h+DeviceInstallParams.FlagsEx], 0Bh
0x180026528  lea     r8, [rsp+288h+DeviceInstallParams]; DeviceInstallParams
0x18002652d  xor     edx, edx; DeviceInfoData
0x18002652f  mov     rcx, rdi; DeviceInfoSet
0x180026532  call    cs:__imp_SetupDiSetDeviceInstallParamsW
0x180026538  mov     ebx, eax
0x18002653a  test    eax, eax
0x18002653c  jnz     short loc_18002655A
0x18002653e  call    cs:__imp_GetLastError
0x180026544  mov     r8d, eax
0x180026547  lea     rdx, aErrorAllowingE; "Error allowing enumeration of drivers m"...
0x18002654e  lea     rcx, aAllowexcludedd_0; "AllowExcludedDrivers"
0x180026555  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18002655a  mov     eax, ebx
0x18002655c  mov     rcx, [rsp+288h+var_18]
0x180026564  xor     rcx, rsp; StackCookie
0x180026567  call    __security_check_cookie
0x18002656c  mov     rbx, [rsp+288h+arg_8]
0x180026574  add     rsp, 280h
0x18002657b  pop     rdi
0x18002657c  retn
```
