# BuildDriverListFromInfs(ushort const *,void *)

- ea: `0x18002407c`
- end: `0x18002422f`
- name: `?BuildDriverListFromInfs@@YAJPEBGPEAX@Z`
- size: `435`
- prototype: `__int64 __fastcall(const unsigned __int16 *, HDEVINFO DeviceInfoSet)`
- caller_count: `2`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x180026df0`
- `0x180027700`

## callees

- `0x180002300`
- `0x180002f48`
- `0x180007944`
- `0x18000d57c`
- `0x18000d624`
- `0x180018d18`
- `0x18002407c`

## import_xrefs

- `SETUPAPI!SetupDiBuildDriverInfoList` at `0x18002419a`
- `SETUPAPI!SetupDiBuildDriverInfoList` at `0x18002419a`
- `SETUPAPI!SetupDiSetDeviceInstallParamsW` at `0x180024158`
- `SETUPAPI!SetupDiSetDeviceInstallParamsW` at `0x180024158`
- `SETUPAPI!SetupDiGetDeviceInstallParamsW` at `0x1800240df`
- `SETUPAPI!SetupDiGetDeviceInstallParamsW` at `0x1800240df`

## string_xrefs

- `0x1800240f8`: `Error getting device install params: hr: 0x%x`
- `0x180024165`: `Error setting device install params: hr: 0x%x`

## pseudocode

```c
__int64 __fastcall BuildDriverListFromInfs(const unsigned __int16 *a1, char *DeviceInfoSet)
{
  __int64 LastErrorAsHResult; // rbx
  DWORD v5; // eax
  struct _SP_DEVINSTALL_PARAMS_W DeviceInstallParams; // [rsp+20h] [rbp-278h] BYREF

  memset_0(&DeviceInstallParams, 0, sizeof(DeviceInstallParams));
  if ( (unsigned __int64)(DeviceInfoSet - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    LODWORD(LastErrorAsHResult) = -2147024809;
    ClassInstallerTelemetry::WriteDbgTraceError(
      "BuildDriverListFromInfs",
      L"Invalid Argument: hDevInfo=%p",
      DeviceInfoSet);
LABEL_15:
    ClassInstallerTelemetry::WriteDbgTraceError(
      "BuildDriverListFromInfs",
      L"Error building driver list: hr: 0x%x",
      (unsigned int)LastErrorAsHResult);
    return (unsigned int)LastErrorAsHResult;
  }
  DeviceInstallParams.cbSize = 584;
  LODWORD(LastErrorAsHResult) = 0;
  if ( !SetupDiGetDeviceInstallParamsW(DeviceInfoSet, 0, &DeviceInstallParams) )
  {
    LastErrorAsHResult = (unsigned int)GetLastErrorAsHResult();
    ClassInstallerTelemetry::WriteDbgTraceError(
      "BuildDriverListFromInfs",
      L"Error getting device install params: hr: 0x%x",
      LastErrorAsHResult);
    if ( (int)LastErrorAsHResult < 0 )
      goto LABEL_15;
  }
  v5 = DeviceInstallParams.FlagsEx | 0x40000;
  DeviceInstallParams.FlagsEx |= 0x40000u;
  if ( a1 && *a1 )
    LODWORD(LastErrorAsHResult) = StringCchCopyW(DeviceInstallParams.DriverPath, 0x104u, a1);
  else
    DeviceInstallParams.FlagsEx = v5 | 0x80000000;
  if ( (int)LastErrorAsHResult < 0 )
    goto LABEL_15;
  if ( !SetupDiSetDeviceInstallParamsW(DeviceInfoSet, 0, &DeviceInstallParams) )
  {
    ClassInstallerTelemetry::WriteDbgTraceError(
      "BuildDriverListFromInfs",
      L"Error setting device install params: hr: 0x%x",
      (unsigned int)LastErrorAsHResult);
    LODWORD(LastErrorAsHResult) = GetLastErrorAsHResult();
    if ( (int)LastErrorAsHResult < 0 )
      goto LABEL_15;
  }
  ClassInstallerTelemetry::WriteDbgTraceInfo("BuildDriverListFromInfs", L"Building driver list from %ws", a1);
  if ( !SetupDiBuildDriverInfoList(DeviceInfoSet, 0, 1u) )
  {
    ClassInstallerTelemetry::WriteDbgTraceError(
      "BuildDriverListFromInfs",
      L"Error building driver list from %ws: hr: 0x%x",
      a1,
      (unsigned int)LastErrorAsHResult);
    LODWORD(LastErrorAsHResult) = GetLastErrorAsHResult();
    if ( (int)LastErrorAsHResult < 0 )
      goto LABEL_15;
  }
  ClassInstallerTelemetry::WriteDbgTraceInfo("BuildDriverListFromInfs", L"Finished building driver list");
  return (unsigned int)LastErrorAsHResult;
}

```

## disassembly

```asm
0x18002407c  mov     [rsp+arg_10], rbx
0x180024081  mov     [rsp+arg_18], rbp
0x180024086  push    rsi
0x180024087  push    rdi
0x180024088  push    r14
0x18002408a  sub     rsp, 280h
0x180024091  mov     rax, cs:__security_cookie
0x180024098  xor     rax, rsp
0x18002409b  mov     [rsp+298h+var_28], rax
0x1800240a3  mov     rbp, rdx
0x1800240a6  mov     rsi, rcx
0x1800240a9  mov     edi, 248h
0x1800240ae  lea     rcx, [rsp+298h+DeviceInstallParams]; void *
0x1800240b3  mov     r8d, edi; Size
0x1800240b6  xor     edx, edx; Val
0x1800240b8  call    memset_0
0x1800240bd  lea     rax, [rbp-1]
0x1800240c1  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800240c5  ja      loc_1800241D5
0x1800240cb  xor     r14d, r14d
0x1800240ce  mov     [rsp+298h+DeviceInstallParams.cbSize], edi
0x1800240d2  lea     r8, [rsp+298h+DeviceInstallParams]; DeviceInstallParams
0x1800240d7  xor     edx, edx; DeviceInfoData
0x1800240d9  mov     rcx, rbp; DeviceInfoSet
0x1800240dc  mov     ebx, r14d
0x1800240df  call    cs:__imp_SetupDiGetDeviceInstallParamsW
0x1800240e5  lea     rdi, aBuilddriverlis; "BuildDriverListFromInfs"
0x1800240ec  test    eax, eax
0x1800240ee  jnz     short loc_180024111
0x1800240f0  call    GetLastErrorAsHResult
0x1800240f5  mov     r8d, eax
0x1800240f8  lea     rdx, aErrorGettingDe_0; "Error getting device install params: hr"...
0x1800240ff  mov     rcx, rdi; char *
0x180024102  mov     ebx, eax
0x180024104  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180024109  test    ebx, ebx
0x18002410b  js      loc_1800241F3
0x180024111  mov     eax, [rsp+298h+DeviceInstallParams.FlagsEx]
0x180024115  bts     eax, 12h
0x180024119  mov     [rsp+298h+DeviceInstallParams.FlagsEx], eax
0x18002411d  test    rsi, rsi
0x180024120  jz      short loc_18002413E
0x180024122  cmp     [rsi], r14w
0x180024126  jz      short loc_18002413E
0x180024128  mov     r8, rsi; unsigned __int16 *
0x18002412b  lea     rcx, [rsp+298h+DeviceInstallParams.DriverPath]; unsigned __int16 *
0x180024130  mov     edx, 104h; unsigned __int64
0x180024135  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002413a  mov     ebx, eax
0x18002413c  jmp     short loc_180024146
0x18002413e  bts     eax, 1Fh
0x180024142  mov     [rsp+298h+DeviceInstallParams.FlagsEx], eax
0x180024146  test    ebx, ebx
0x180024148  js      loc_1800241F3
0x18002414e  lea     r8, [rsp+298h+DeviceInstallParams]; DeviceInstallParams
0x180024153  xor     edx, edx; DeviceInfoData
0x180024155  mov     rcx, rbp; DeviceInfoSet
0x180024158  call    cs:__imp_SetupDiSetDeviceInstallParamsW
0x18002415e  test    eax, eax
0x180024160  jnz     short loc_18002417F
0x180024162  mov     r8d, ebx
0x180024165  lea     rdx, aErrorSettingDe_1; "Error setting device install params: hr"...
0x18002416c  mov     rcx, rdi; char *
0x18002416f  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180024174  call    GetLastErrorAsHResult
0x180024179  mov     ebx, eax
0x18002417b  test    eax, eax
0x18002417d  js      short loc_1800241F3
0x18002417f  mov     r8, rsi
0x180024182  lea     rdx, aBuildingDriver_0; "Building driver list from %ws"
0x180024189  mov     rcx, rdi; char *
0x18002418c  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180024191  xor     edx, edx; DeviceInfoData
0x180024193  mov     rcx, rbp; DeviceInfoSet
0x180024196  lea     r8d, [rdx+1]; DriverType
0x18002419a  call    cs:__imp_SetupDiBuildDriverInfoList
0x1800241a0  test    eax, eax
0x1800241a2  jnz     short loc_1800241C4
0x1800241a4  mov     r9d, ebx
0x1800241a7  lea     rdx, aErrorBuildingD; "Error building driver list from %ws: hr"...
0x1800241ae  mov     r8, rsi
0x1800241b1  mov     rcx, rdi; char *
0x1800241b4  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800241b9  call    GetLastErrorAsHResult
0x1800241be  mov     ebx, eax
0x1800241c0  test    eax, eax
0x1800241c2  js      short loc_1800241F3
0x1800241c4  lea     rdx, aFinishedBuildi; "Finished building driver list"
0x1800241cb  mov     rcx, rdi; char *
0x1800241ce  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800241d3  jmp     short loc_180024205
0x1800241d5  lea     rdi, aBuilddriverlis; "BuildDriverListFromInfs"
0x1800241dc  mov     r8, rbp
0x1800241df  mov     rcx, rdi; char *
0x1800241e2  lea     rdx, aInvalidArgumen_14; "Invalid Argument: hDevInfo=%p"
0x1800241e9  mov     ebx, 80070057h
0x1800241ee  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800241f3  mov     r8d, ebx
0x1800241f6  lea     rdx, aErrorBuildingD_4; "Error building driver list: hr: 0x%x"
0x1800241fd  mov     rcx, rdi; char *
0x180024200  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180024205  mov     eax, ebx
0x180024207  mov     rcx, [rsp+298h+var_28]
0x18002420f  xor     rcx, rsp; StackCookie
0x180024212  call    __security_check_cookie
0x180024217  lea     r11, [rsp+298h+var_18]
0x18002421f  mov     rbx, [r11+30h]
0x180024223  mov     rbp, [r11+38h]
0x180024227  mov     rsp, r11
0x18002422a  pop     r14
0x18002422c  pop     rdi
0x18002422d  pop     rsi
0x18002422e  retn
```
