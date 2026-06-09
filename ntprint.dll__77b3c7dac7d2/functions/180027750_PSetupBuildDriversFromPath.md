# PSetupBuildDriversFromPath

- ea: `0x180027750`
- end: `0x180027884`
- name: `PSetupBuildDriversFromPath`
- size: `308`
- prototype: `__int64 __fastcall(HDEVINFO DeviceInfoSet, unsigned __int16 *)`
- caller_count: `4`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x18000ed30`
- `0x180011c70`
- `0x18002c0f0`
- `0x1800344b0`

## callees

- `0x180002300`
- `0x180002f48`
- `0x180007944`
- `0x18000d57c`
- `0x18000d624`
- `0x180027750`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027841`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027841`
- `SETUPAPI!SetupDiBuildDriverInfoList` at `0x18002781d`
- `SETUPAPI!SetupDiBuildDriverInfoList` at `0x18002781d`
- `SETUPAPI!SetupDiDestroyDriverInfoList` at `0x1800277fb`
- `SETUPAPI!SetupDiDestroyDriverInfoList` at `0x1800277fb`
- `SETUPAPI!SetupDiSetDeviceInstallParamsW` at `0x18002780b`
- `SETUPAPI!SetupDiSetDeviceInstallParamsW` at `0x18002780b`
- `SETUPAPI!SetupDiGetDeviceInstallParamsW` at `0x1800277a1`
- `SETUPAPI!SetupDiGetDeviceInstallParamsW` at `0x1800277a1`

## string_xrefs

- `0x1800277d0`: `PSetupBuildDriversFromPath`
- `0x180027831`: `PSetupBuildDriversFromPath`
- `0x180027851`: `PSetupBuildDriversFromPath`
- `0x1800277b9`: `Building driver list from the path %ws`

## pseudocode

```c
__int64 __fastcall PSetupBuildDriversFromPath(HDEVINFO DeviceInfoSet, unsigned __int16 *a2, int a3)
{
  unsigned __int16 *v6; // rdx
  unsigned int v7; // ebx
  DWORD LastError; // eax
  struct _SP_DEVINSTALL_PARAMS_W DeviceInstallParams; // [rsp+20h] [rbp-268h] BYREF

  memset_0(&DeviceInstallParams.Flags, 0, 0x244u);
  DeviceInstallParams.cbSize = 584;
  if ( !SetupDiGetDeviceInstallParamsW(DeviceInfoSet, 0, &DeviceInstallParams) )
    goto LABEL_9;
  if ( a3 )
    DeviceInstallParams.Flags |= 0x10000u;
  v6 = L"Building driver list from the single INF %ws";
  if ( !a3 )
    v6 = L"Building driver list from the path %ws";
  ClassInstallerTelemetry::WriteDbgTraceInfo("PSetupBuildDriversFromPath", v6, a2);
  StringCchCopyW(DeviceInstallParams.DriverPath, 0x104u, a2);
  v7 = 1;
  SetupDiDestroyDriverInfoList(DeviceInfoSet, 0, 1u);
  if ( SetupDiSetDeviceInstallParamsW(DeviceInfoSet, 0, &DeviceInstallParams)
    && SetupDiBuildDriverInfoList(DeviceInfoSet, 0, 1u) )
  {
    ClassInstallerTelemetry::WriteDbgTraceInfo("PSetupBuildDriversFromPath", L"Built driver list from %ws", a2);
  }
  else
  {
LABEL_9:
    v7 = 0;
    LastError = GetLastError();
    ClassInstallerTelemetry::WriteDbgTraceError(
      "PSetupBuildDriversFromPath",
      L"Error building driver list: %d",
      LastError);
  }
  return v7;
}

```

## disassembly

```asm
0x180027750  mov     [rsp+arg_10], rbx
0x180027755  mov     [rsp+arg_18], rsi
0x18002775a  push    rdi
0x18002775b  sub     rsp, 280h
0x180027762  mov     rax, cs:__security_cookie
0x180027769  xor     rax, rsp
0x18002776c  mov     [rsp+288h+var_18], rax
0x180027774  mov     ebx, r8d
0x180027777  mov     rsi, rdx
0x18002777a  mov     rdi, rcx
0x18002777d  xor     edx, edx; Val
0x18002777f  mov     r8d, 244h; Size
0x180027785  lea     rcx, [rsp+288h+DeviceInstallParams.Flags]; void *
0x18002778a  call    memset_0
0x18002778f  lea     r8, [rsp+288h+DeviceInstallParams]; DeviceInstallParams
0x180027794  mov     [rsp+288h+DeviceInstallParams.cbSize], 248h
0x18002779c  xor     edx, edx; DeviceInfoData
0x18002779e  mov     rcx, rdi; DeviceInfoSet
0x1800277a1  call    cs:__imp_SetupDiGetDeviceInstallParamsW
0x1800277a7  test    eax, eax
0x1800277a9  jz      loc_18002783F
0x1800277af  test    ebx, ebx
0x1800277b1  jz      short loc_1800277B9
0x1800277b3  bts     [rsp+288h+DeviceInstallParams.Flags], 10h
0x1800277b9  lea     rax, aBuildingDriver_1; "Building driver list from the path %ws"
0x1800277c0  test    ebx, ebx
0x1800277c2  lea     rdx, aBuildingDriver; "Building driver list from the single IN"...
0x1800277c9  mov     r8, rsi
0x1800277cc  cmovz   rdx, rax; unsigned __int16 *
0x1800277d0  lea     rcx, aPsetupbuilddri_2; "PSetupBuildDriversFromPath"
0x1800277d7  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800277dc  mov     r8, rsi; unsigned __int16 *
0x1800277df  lea     rcx, [rsp+288h+DeviceInstallParams.DriverPath]; unsigned __int16 *
0x1800277e4  mov     edx, 104h; unsigned __int64
0x1800277e9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800277ee  mov     ebx, 1
0x1800277f3  xor     edx, edx; DeviceInfoData
0x1800277f5  mov     r8d, ebx; DriverType
0x1800277f8  mov     rcx, rdi; DeviceInfoSet
0x1800277fb  call    cs:__imp_SetupDiDestroyDriverInfoList
0x180027801  lea     r8, [rsp+288h+DeviceInstallParams]; DeviceInstallParams
0x180027806  xor     edx, edx; DeviceInfoData
0x180027808  mov     rcx, rdi; DeviceInfoSet
0x18002780b  call    cs:__imp_SetupDiSetDeviceInstallParamsW
0x180027811  test    eax, eax
0x180027813  jz      short loc_18002783F
0x180027815  mov     r8d, ebx; DriverType
0x180027818  xor     edx, edx; DeviceInfoData
0x18002781a  mov     rcx, rdi; DeviceInfoSet
0x18002781d  call    cs:__imp_SetupDiBuildDriverInfoList
0x180027823  test    eax, eax
0x180027825  jz      short loc_18002783F
0x180027827  mov     r8, rsi
0x18002782a  lea     rdx, aBuiltDriverLis; "Built driver list from %ws"
0x180027831  lea     rcx, aPsetupbuilddri_2; "PSetupBuildDriversFromPath"
0x180027838  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18002783d  jmp     short loc_18002785D
0x18002783f  xor     ebx, ebx
0x180027841  call    cs:__imp_GetLastError
0x180027847  mov     r8d, eax
0x18002784a  lea     rdx, aErrorBuildingD_3; "Error building driver list: %d"
0x180027851  lea     rcx, aPsetupbuilddri_2; "PSetupBuildDriversFromPath"
0x180027858  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18002785d  mov     eax, ebx
0x18002785f  mov     rcx, [rsp+288h+var_18]
0x180027867  xor     rcx, rsp; StackCookie
0x18002786a  call    __security_check_cookie
0x18002786f  lea     r11, [rsp+288h+var_8]
0x180027877  mov     rbx, [r11+20h]
0x18002787b  mov     rsi, [r11+28h]
0x18002787f  mov     rsp, r11
0x180027882  pop     rdi
0x180027883  retn
```
