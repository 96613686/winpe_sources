# ClassInstall_InstallDeviceFiles(void *,_SP_DEVINFO_DATA *,_SP_DEVINSTALL_PARAMS_W *)

- ea: `0x180013e68`
- end: `0x18001419b`
- name: `?ClassInstall_InstallDeviceFiles@@YAKPEAXPEAU_SP_DEVINFO_DATA@@PEAU_SP_DEVINSTALL_PARAMS_W@@@Z`
- size: `819`
- prototype: `unsigned int __fastcall(HDEVINFO DeviceInfoSet, struct _SP_DEVINFO_DATA *, struct _SP_DEVINSTALL_PARAMS_W *)`
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180013260`

## callees

- `0x180002300`
- `0x180002f48`
- `0x18000d57c`
- `0x18000d624`
- `0x180012c4c`
- `0x180013e68`
- `0x1800166b0`
- `0x18001c5c0`
- `0x18001e4f0`
- `0x180020b60`
- `0x180022dec`
- `0x180026820`
- `0x180036664`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180014075`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18001408a`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18001409f`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180014075`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18001408a`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18001409f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014016`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014120`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014016`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014120`
- `SETUPAPI!SetupDiSetDevicePropertyW` at `0x18001415a`
- `SETUPAPI!SetupDiSetDevicePropertyW` at `0x18001415a`
- `SETUPAPI!SetupDiGetDeviceInstanceIdW` at `0x180013ee0`
- `SETUPAPI!SetupDiGetDeviceInstanceIdW` at `0x180013ee0`
- `SETUPAPI!SetupCloseInfFile` at `0x180013fde`
- `SETUPAPI!SetupCloseInfFile` at `0x180013fde`
- `SETUPAPI!SetupInstallFromInfSectionW` at `0x180013fd5`
- `SETUPAPI!SetupInstallFromInfSectionW` at `0x180013fd5`
- `WINSPOOL!InstallPrinterDriverFromPackageW` at `0x180013ff8`
- `WINSPOOL!InstallPrinterDriverFromPackageW` at `0x1800140cd`
- `WINSPOOL!InstallPrinterDriverFromPackageW` at `0x180013ff8`
- `WINSPOOL!InstallPrinterDriverFromPackageW` at `0x1800140cd`

## string_xrefs

- `0x180013eba`: `ClassInstall_InstallDeviceFiles - Enter:`
- `0x180013eb0`: `ClassInstall_InstallDeviceFiles`
- `0x180013f5d`: `ClassInstall_InstallDeviceFiles - it is legacy v3 driver`
- `0x180014007`: `ClassInstall_InstallDeviceFiles - v3: call InstallPrinterDriverFromPackage exit with %d`
- `0x180014050`: `ClassInstall_InstallDeviceFiles - v3: call PerformInfInstallActions exit with %d`
- `0x18001405f`: `ClassInstall_InstallDeviceFiles - v4: modern driver check`
- `0x1800140aa`: `ClassInstall_InstallDeviceFiles - v4: call InstallPrinterDriverFromPackage`
- `0x1800140e3`: `ClassInstall_InstallDeviceFiles - v4: call InstallPrinterDriverFromPackage exit with %d`
- `0x1800140ff`: `ClassInstall_InstallDeviceFiles - v4: modern driver check exit with %d Inf: %ws`
- `0x180014163`: `ClassInstall_InstallDeviceFiles - Exit: %d`

## pseudocode

```c
__int64 __fastcall ClassInstall_InstallDeviceFiles(
        HDEVINFO DeviceInfoSet,
        struct _SP_DEVINFO_DATA *a2,
        struct _SP_DEVINSTALL_PARAMS_W *a3)
{
  __int64 v6; // rcx
  __int64 v7; // rax
  _QWORD *v8; // rbx
  unsigned int IsNullPrinterDriver; // eax
  __int64 v10; // rdi
  void *v11; // rax
  void *v12; // rdi
  unsigned int v13; // eax
  unsigned int v14; // eax
  HRESULT v15; // eax
  BYTE PropertyBuffer[4]; // [rsp+60h] [rbp-1D8h] BYREF
  _DWORD v18[3]; // [rsp+64h] [rbp-1D4h] BYREF
  WCHAR DeviceInstanceId[200]; // [rsp+70h] [rbp-1C8h] BYREF

  v18[0] = 0;
  memset_0(DeviceInstanceId, 0, sizeof(DeviceInstanceId));
  ClassInstallerTelemetry::WriteDbgTraceInfo(
    "ClassInstall_InstallDeviceFiles",
    L"ClassInstall_InstallDeviceFiles - Enter:");
  if ( SetupDiGetDeviceInstanceIdW(DeviceInfoSet, a2, DeviceInstanceId, 0xC8u, 0)
    && (Microsoft_Windows_DocumentsEnableBits & 1) != 0 )
  {
    McTemplateU0z_EventWriteTransfer(v6, DocPerf_Setup_PnPPrinterInstall_Start, DeviceInstanceId);
  }
  v7 = BuildInternalData((int)DeviceInfoSet, (int)a2);
  v8 = (_QWORD *)v7;
  if ( v7 )
  {
    IsNullPrinterDriver = InfFileIsNullPrinterDriver(v7, (unsigned int)MyPlatform, v18);
    LODWORD(v10) = StatusFromHResult(IsNullPrinterDriver);
    if ( !(_DWORD)v10 && !v18[0] )
    {
      if ( *((_DWORD *)v8 + 24) >= 4u )
      {
        ClassInstallerTelemetry::WriteDbgTraceInfo(
          "ClassInstall_InstallDeviceFiles",
          L"ClassInstall_InstallDeviceFiles - v4: modern driver check");
        if ( wcsstr((const wchar_t *)*v8, L"prnms012.inf")
          || wcsstr((const wchar_t *)*v8, L"prnms014.inf")
          || wcsstr((const wchar_t *)*v8, L"prnms015.inf") )
        {
          ClassInstallerTelemetry::ModernPrintDriverInstallAttempt<unsigned short * &>(v8);
          LODWORD(v10) = -536870386;
          ClassInstallerTelemetry::WriteDbgTraceError(
            "ClassInstall_InstallDeviceFiles",
            L"ClassInstall_InstallDeviceFiles - v4: modern driver check exit with %d Inf: %ws",
            3758096910LL,
            *v8);
        }
        else
        {
          ClassInstallerTelemetry::WriteDbgTraceInfo(
            "ClassInstall_InstallDeviceFiles",
            L"ClassInstall_InstallDeviceFiles - v4: call InstallPrinterDriverFromPackage");
          v15 = InstallPrinterDriverFromPackageW(0, (LPCWSTR)*v8, (LPCWSTR)v8[1], 0, 0);
          if ( v15 < 0 )
            LODWORD(v10) = StatusFromHResult((unsigned int)v15);
          ClassInstallerTelemetry::WriteDbgTraceError(
            "ClassInstall_InstallDeviceFiles",
            L"ClassInstall_InstallDeviceFiles - v4: call InstallPrinterDriverFromPackage exit with %d",
            (unsigned int)v10);
        }
      }
      else
      {
        ClassInstallerTelemetry::WriteDbgTraceInfo(
          "ClassInstall_InstallDeviceFiles",
          L"ClassInstall_InstallDeviceFiles - it is legacy v3 driver");
        if ( (a3->Flags & 8) != 0 )
        {
          v14 = PerformInfInstallActions(DeviceInfoSet, MyPlatform, 1);
          v10 = (unsigned int)StatusFromHResult(v14);
          ClassInstallerTelemetry::WriteDbgTraceError(
            "ClassInstall_InstallDeviceFiles",
            L"ClassInstall_InstallDeviceFiles - v3: call PerformInfInstallActions exit with %d",
            v10);
        }
        else
        {
          v11 = (void *)OpenPrinterInfFile((unsigned __int16 *)*v8);
          v12 = v11;
          if ( v11 == (void *)-1LL )
          {
            LODWORD(v10) = GetLastError();
          }
          else
          {
            SetupInstallFromInfSectionW(
              a3->hwndParent,
              v11,
              (PCWSTR)v8[2],
              0x7EFu,
              0,
              0,
              0,
              0,
              0,
              DeviceInfoSet,
              (PSP_DEVINFO_DATA)v8[3]);
            SetupCloseInfFile(v12);
            v13 = InstallPrinterDriverFromPackageW(0, (LPCWSTR)*v8, (LPCWSTR)v8[1], 0, 0x40000000u);
            v10 = (unsigned int)StatusFromHResult(v13);
            ClassInstallerTelemetry::WriteDbgTraceError(
              "ClassInstall_InstallDeviceFiles",
              L"ClassInstall_InstallDeviceFiles - v3: call InstallPrinterDriverFromPackage exit with %d",
              v10);
          }
        }
      }
    }
    DestroyLocalData(v8);
  }
  else
  {
    LODWORD(v10) = GetLastError();
  }
  PropertyBuffer[0] = -1;
  SetupDiSetDevicePropertyW(DeviceInfoSet, a2, &stru_180041488, 0x11u, PropertyBuffer, 1u, 0);
  ClassInstallerTelemetry::WriteDbgTraceInfo(
    "ClassInstall_InstallDeviceFiles",
    L"ClassInstall_InstallDeviceFiles - Exit: %d",
    (unsigned int)v10);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180013e68  mov     [rsp+arg_18], rbx
0x180013e6d  push    rbp
0x180013e6e  push    rsi
0x180013e6f  push    rdi
0x180013e70  push    r12
0x180013e72  push    r14
0x180013e74  sub     rsp, 210h
0x180013e7b  mov     rax, cs:__security_cookie
0x180013e82  xor     rax, rsp
0x180013e85  mov     [rsp+238h+var_38], rax
0x180013e8d  mov     rbp, r8
0x180013e90  mov     [rsp+238h+var_1D4], 0
0x180013e98  mov     r14, rdx
0x180013e9b  mov     rsi, rcx
0x180013e9e  xor     edx, edx; Val
0x180013ea0  lea     rcx, [rsp+238h+DeviceInstanceId]; void *
0x180013ea5  mov     r8d, 190h; Size
0x180013eab  call    memset_0
0x180013eb0  lea     r12, aClassinstallIn_0; "ClassInstall_InstallDeviceFiles"
0x180013eb7  mov     rcx, r12; char *
0x180013eba  lea     rdx, aClassinstallIn_8; "ClassInstall_InstallDeviceFiles - Enter"...
0x180013ec1  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180013ec6  mov     r9d, 0C8h; DeviceInstanceIdSize
0x180013ecc  mov     [rsp+238h+RequiredSize], 0; RequiredSize
0x180013ed5  lea     r8, [rsp+238h+DeviceInstanceId]; DeviceInstanceId
0x180013eda  mov     rdx, r14; DeviceInfoData
0x180013edd  mov     rcx, rsi; DeviceInfoSet
0x180013ee0  call    cs:__imp_SetupDiGetDeviceInstanceIdW
0x180013ee6  test    eax, eax
0x180013ee8  jz      short loc_180013F04
0x180013eea  test    cs:Microsoft_Windows_DocumentsEnableBits, 1
0x180013ef1  jz      short loc_180013F04
0x180013ef3  lea     r8, [rsp+238h+DeviceInstanceId]
0x180013ef8  lea     rdx, DocPerf_Setup_PnPPrinterInstall_Start
0x180013eff  call    McTemplateU0z_EventWriteTransfer
0x180013f04  mov     r8d, cs:MyPlatform
0x180013f0b  mov     rdx, r14; int
0x180013f0e  mov     rcx, rsi; int
0x180013f11  call    BuildInternalData
0x180013f16  mov     rbx, rax
0x180013f19  test    rax, rax
0x180013f1c  jz      loc_180014120
0x180013f22  mov     edx, cs:MyPlatform
0x180013f28  lea     r8, [rsp+238h+var_1D4]
0x180013f2d  mov     rcx, rax
0x180013f30  call    InfFileIsNullPrinterDriver
0x180013f35  mov     ecx, eax
0x180013f37  call    StatusFromHResult
0x180013f3c  mov     edi, eax
0x180013f3e  test    eax, eax
0x180013f40  jnz     loc_180014116
0x180013f46  cmp     [rsp+238h+var_1D4], eax
0x180013f4a  jnz     loc_180014116
0x180013f50  cmp     dword ptr [rbx+60h], 4
0x180013f54  mov     rcx, r12; char *
0x180013f57  jnb     loc_18001405F
0x180013f5d  lea     rdx, aClassinstallIn_15; "ClassInstall_InstallDeviceFiles - it is"...
0x180013f64  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180013f69  test    byte ptr [rbp+4], 8
0x180013f6d  jnz     loc_180014023
0x180013f73  mov     rcx, [rbx]; unsigned __int16 *
0x180013f76  xor     edx, edx
0x180013f78  call    OpenPrinterInfFile
0x180013f7d  mov     rdi, rax
0x180013f80  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180013f84  jz      loc_180014016
0x180013f8a  mov     rcx, [rbx+18h]
0x180013f8e  mov     r9d, 7EFh; Flags
0x180013f94  mov     r8, [rbx+10h]; SectionName
0x180013f98  mov     rdx, rax; InfHandle
0x180013f9b  mov     [rsp+238h+DeviceInfoData], rcx; DeviceInfoData
0x180013fa0  mov     rcx, [rbp+10h]; Owner
0x180013fa4  mov     [rsp+238h+DeviceInfoSet], rsi; DeviceInfoSet
0x180013fa9  mov     [rsp+238h+Context], 0; Context
0x180013fb2  mov     [rsp+238h+MsgHandler], 0; MsgHandler
0x180013fbb  mov     [rsp+238h+CopyFlags], 0; CopyFlags
0x180013fc3  mov     [rsp+238h+SourceRootPath], 0; SourceRootPath
0x180013fcc  mov     [rsp+238h+RequiredSize], 0; RelativeKeyRoot
0x180013fd5  call    cs:__imp_SetupInstallFromInfSectionW
0x180013fdb  mov     rcx, rdi; InfHandle
0x180013fde  call    cs:__imp_SetupCloseInfFile
0x180013fe4  mov     r8, [rbx+8]; pszDriverName
0x180013fe8  xor     r9d, r9d; pszEnvironment
0x180013feb  mov     rdx, [rbx]; pszInfPath
0x180013fee  xor     ecx, ecx; pszServer
0x180013ff0  mov     dword ptr [rsp+238h+RequiredSize], 40000000h; dwFlags
0x180013ff8  call    cs:__imp_InstallPrinterDriverFromPackageW
0x180013ffe  mov     ecx, eax
0x180014000  call    StatusFromHResult
0x180014005  mov     edi, eax
0x180014007  lea     rdx, aClassinstallIn_4; "ClassInstall_InstallDeviceFiles - v3: c"...
0x18001400e  mov     r8d, eax
0x180014011  jmp     loc_1800140EA
0x180014016  call    cs:__imp_GetLastError
0x18001401c  mov     edi, eax
0x18001401e  jmp     loc_180014116
0x180014023  mov     eax, cs:MyPlatform
0x180014029  mov     r9, rbx
0x18001402c  mov     rdx, [rbp+28h]
0x180014030  xor     r8d, r8d
0x180014033  mov     dword ptr [rsp+238h+SourceRootPath], 1; int
0x18001403b  mov     rcx, rsi; DeviceInfoSet
0x18001403e  mov     dword ptr [rsp+238h+RequiredSize], eax; int
0x180014042  call    PerformInfInstallActions
0x180014047  mov     ecx, eax
0x180014049  call    StatusFromHResult
0x18001404e  mov     edi, eax
0x180014050  lea     rdx, aClassinstallIn_7; "ClassInstall_InstallDeviceFiles - v3: c"...
0x180014057  mov     r8d, eax
0x18001405a  jmp     loc_1800140EA
0x18001405f  lea     rdx, aClassinstallIn_3; "ClassInstall_InstallDeviceFiles - v4: m"...
0x180014066  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18001406b  mov     rcx, [rbx]; Str
0x18001406e  lea     rdx, aPrnms012Inf; "prnms012.inf"
0x180014075  call    cs:__imp_wcsstr
0x18001407b  test    rax, rax
0x18001407e  jnz     short loc_1800140F4
0x180014080  mov     rcx, [rbx]; Str
0x180014083  lea     rdx, aPrnms014Inf; "prnms014.inf"
0x18001408a  call    cs:__imp_wcsstr
0x180014090  test    rax, rax
0x180014093  jnz     short loc_1800140F4
0x180014095  mov     rcx, [rbx]; Str
0x180014098  lea     rdx, aPrnms015Inf; "prnms015.inf"
0x18001409f  call    cs:__imp_wcsstr
0x1800140a5  test    rax, rax
0x1800140a8  jnz     short loc_1800140F4
0x1800140aa  lea     rdx, aClassinstallIn; "ClassInstall_InstallDeviceFiles - v4: c"...
0x1800140b1  mov     rcx, r12; char *
0x1800140b4  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800140b9  mov     r8, [rbx+8]; pszDriverName
0x1800140bd  xor     r9d, r9d; pszEnvironment
0x1800140c0  mov     rdx, [rbx]; pszInfPath
0x1800140c3  xor     ecx, ecx; pszServer
0x1800140c5  mov     dword ptr [rsp+238h+RequiredSize], 0; dwFlags
0x1800140cd  call    cs:__imp_InstallPrinterDriverFromPackageW
0x1800140d3  test    eax, eax
0x1800140d5  jns     short loc_1800140E0
0x1800140d7  mov     ecx, eax
0x1800140d9  call    StatusFromHResult
0x1800140de  mov     edi, eax
0x1800140e0  mov     r8d, edi
0x1800140e3  lea     rdx, aClassinstallIn_6; "ClassInstall_InstallDeviceFiles - v4: c"...
0x1800140ea  mov     rcx, r12; char *
0x1800140ed  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800140f2  jmp     short loc_180014116
0x1800140f4  mov     rcx, rbx
0x1800140f7  call    ??$ModernPrintDriverInstallAttempt@AEAPEAG@ClassInstallerTelemetry@@SAXAEAPEAG@Z; ClassInstallerTelemetry::ModernPrintDriverInstallAttempt<ushort * &>(ushort * &)
0x1800140fc  mov     r9, [rbx]
0x1800140ff  lea     rdx, aClassinstallIn_11; "ClassInstall_InstallDeviceFiles - v4: m"...
0x180014106  mov     edi, 0E000020Eh
0x18001410b  mov     rcx, r12; char *
0x18001410e  mov     r8d, edi
0x180014111  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180014116  mov     rcx, rbx; hMem
0x180014119  call    DestroyLocalData
0x18001411e  jmp     short loc_180014128
0x180014120  call    cs:__imp_GetLastError
0x180014126  mov     edi, eax
0x180014128  mov     [rsp+238h+CopyFlags], 0; Flags
0x180014130  lea     rax, [rsp+238h+PropertyBuffer]
0x180014135  mov     dword ptr [rsp+238h+SourceRootPath], 1; PropertyBufferSize
0x18001413d  lea     r8, stru_180041488; PropertyKey
0x180014144  mov     r9d, 11h; PropertyType
0x18001414a  mov     [rsp+238h+RequiredSize], rax; PropertyBuffer
0x18001414f  mov     rdx, r14; DeviceInfoData
0x180014152  mov     [rsp+238h+PropertyBuffer], 0FFh
0x180014157  mov     rcx, rsi; DeviceInfoSet
0x18001415a  call    cs:__imp_SetupDiSetDevicePropertyW
0x180014160  mov     r8d, edi
0x180014163  lea     rdx, aClassinstallIn_14; "ClassInstall_InstallDeviceFiles - Exit:"...
0x18001416a  mov     rcx, r12; char *
0x18001416d  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180014172  mov     eax, edi
0x180014174  mov     rcx, [rsp+238h+var_38]
0x18001417c  xor     rcx, rsp; StackCookie
0x18001417f  call    __security_check_cookie
0x180014184  mov     rbx, [rsp+238h+arg_18]
0x18001418c  add     rsp, 210h
0x180014193  pop     r14
0x180014195  pop     r12
0x180014197  pop     rdi
0x180014198  pop     rsi
0x180014199  pop     rbp
0x18001419a  retn
```
