# BuildExcludedDriverList

- ea: `0x1800266ec`
- end: `0x180026819`
- name: `BuildExcludedDriverList`
- size: `301`
- prototype: `__int64 __fastcall(HDEVINFO DeviceInfoSet, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180026c04`
- `0x180026d10`

## callees

- `0x180002300`
- `0x180002f48`
- `0x180007944`
- `0x18000d57c`
- `0x18000d624`
- `0x1800266ec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026743`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026743`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800267d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800267d8`
- `SETUPAPI!SetupDiBuildDriverInfoList` at `0x1800267b7`
- `SETUPAPI!SetupDiBuildDriverInfoList` at `0x1800267b7`
- `SETUPAPI!SetupDiSetDeviceInstallParamsW` at `0x1800267a0`
- `SETUPAPI!SetupDiSetDeviceInstallParamsW` at `0x1800267a0`
- `SETUPAPI!SetupDiGetDeviceInstallParamsW` at `0x180026764`
- `SETUPAPI!SetupDiGetDeviceInstallParamsW` at `0x180026764`

## pseudocode

```c
__int64 __fastcall BuildExcludedDriverList(HDEVINFO DeviceInfoSet, unsigned __int16 *a2, int a3)
{
  unsigned int DeviceInstallParamsW; // ebx
  DWORD LastError; // eax
  struct _SP_DEVINSTALL_PARAMS_W DeviceInstallParams; // [rsp+20h] [rbp-278h] BYREF

  memset_0(&DeviceInstallParams, 0, sizeof(DeviceInstallParams));
  if ( DeviceInfoSet == (HDEVINFO)-1LL )
    goto LABEL_10;
  if ( a3 )
  {
    DeviceInstallParamsW = a2 != 0;
    SetLastError(0x57u);
    if ( !a2 )
      goto LABEL_11;
  }
  DeviceInstallParams.cbSize = 584;
  DeviceInstallParamsW = SetupDiGetDeviceInstallParamsW(DeviceInfoSet, 0, &DeviceInstallParams);
  if ( !DeviceInstallParamsW )
    goto LABEL_11;
  if ( a3
    && (DeviceInstallParams.Flags |= 0x10000u, (int)StringCchCopyW(DeviceInstallParams.DriverPath, 0x104u, a2) < 0)
    || (DeviceInstallParams.FlagsEx |= 0x800u, !SetupDiSetDeviceInstallParamsW(DeviceInfoSet, 0, &DeviceInstallParams))
    || (DeviceInstallParamsW = 1, !SetupDiBuildDriverInfoList(DeviceInfoSet, 0, 1u)) )
  {
LABEL_10:
    DeviceInstallParamsW = 0;
LABEL_11:
    LastError = GetLastError();
    ClassInstallerTelemetry::WriteDbgTraceError("BuildExcludedDriverList", L"Error building driver list: %d", LastError);
    return DeviceInstallParamsW;
  }
  ClassInstallerTelemetry::WriteDbgTraceInfo("BuildExcludedDriverList", L"Successfully built driver list");
  return DeviceInstallParamsW;
}

```

## disassembly

```asm
0x1800266ec  mov     [rsp+arg_10], rbx
0x1800266f1  push    rbp
0x1800266f2  push    rsi
0x1800266f3  push    rdi
0x1800266f4  sub     rsp, 280h
0x1800266fb  mov     rax, cs:__security_cookie
0x180026702  xor     rax, rsp
0x180026705  mov     [rsp+298h+var_28], rax
0x18002670d  mov     ebp, r8d
0x180026710  mov     rsi, rdx
0x180026713  mov     rdi, rcx
0x180026716  xor     edx, edx; Val
0x180026718  mov     r8d, 248h; Size
0x18002671e  lea     rcx, [rsp+298h+DeviceInstallParams]; void *
0x180026723  call    memset_0
0x180026728  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18002672c  jz      loc_1800267D6
0x180026732  test    ebp, ebp
0x180026734  jz      short loc_180026752
0x180026736  xor     ebx, ebx
0x180026738  mov     ecx, 57h ; 'W'; dwErrCode
0x18002673d  test    rsi, rsi
0x180026740  setnz   bl
0x180026743  call    cs:__imp_SetLastError
0x180026749  test    rsi, rsi
0x18002674c  jz      loc_1800267D8
0x180026752  lea     r8, [rsp+298h+DeviceInstallParams]; DeviceInstallParams
0x180026757  mov     [rsp+298h+DeviceInstallParams.cbSize], 248h
0x18002675f  xor     edx, edx; DeviceInfoData
0x180026761  mov     rcx, rdi; DeviceInfoSet
0x180026764  call    cs:__imp_SetupDiGetDeviceInstallParamsW
0x18002676a  mov     ebx, eax
0x18002676c  test    eax, eax
0x18002676e  jz      short loc_1800267D8
0x180026770  test    ebp, ebp
0x180026772  jz      short loc_180026790
0x180026774  bts     [rsp+298h+DeviceInstallParams.Flags], 10h
0x18002677a  lea     rcx, [rsp+298h+DeviceInstallParams.DriverPath]; unsigned __int16 *
0x18002677f  mov     r8, rsi; unsigned __int16 *
0x180026782  mov     edx, 104h; unsigned __int64
0x180026787  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002678c  test    eax, eax
0x18002678e  js      short loc_1800267D6
0x180026790  bts     [rsp+298h+DeviceInstallParams.FlagsEx], 0Bh
0x180026796  lea     r8, [rsp+298h+DeviceInstallParams]; DeviceInstallParams
0x18002679b  xor     edx, edx; DeviceInfoData
0x18002679d  mov     rcx, rdi; DeviceInfoSet
0x1800267a0  call    cs:__imp_SetupDiSetDeviceInstallParamsW
0x1800267a6  test    eax, eax
0x1800267a8  jz      short loc_1800267D6
0x1800267aa  mov     ebx, 1
0x1800267af  xor     edx, edx; DeviceInfoData
0x1800267b1  mov     r8d, ebx; DriverType
0x1800267b4  mov     rcx, rdi; DeviceInfoSet
0x1800267b7  call    cs:__imp_SetupDiBuildDriverInfoList
0x1800267bd  test    eax, eax
0x1800267bf  jz      short loc_1800267D6
0x1800267c1  lea     rdx, aSuccessfullyBu; "Successfully built driver list"
0x1800267c8  lea     rcx, aBuildexcludedd; "BuildExcludedDriverList"
0x1800267cf  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800267d4  jmp     short loc_1800267F4
0x1800267d6  xor     ebx, ebx
0x1800267d8  call    cs:__imp_GetLastError
0x1800267de  mov     r8d, eax
0x1800267e1  lea     rdx, aErrorBuildingD_3; "Error building driver list: %d"
0x1800267e8  lea     rcx, aBuildexcludedd; "BuildExcludedDriverList"
0x1800267ef  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800267f4  mov     eax, ebx
0x1800267f6  mov     rcx, [rsp+298h+var_28]
0x1800267fe  xor     rcx, rsp; StackCookie
0x180026801  call    __security_check_cookie
0x180026806  mov     rbx, [rsp+298h+arg_10]
0x18002680e  add     rsp, 280h
0x180026815  pop     rdi
0x180026816  pop     rsi
0x180026817  pop     rbp
0x180026818  retn
```
