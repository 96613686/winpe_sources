# ClassInstall_InstallDevice(void *,_SP_DEVINFO_DATA *,_SP_DEVINSTALL_PARAMS_W *)

- ea: `0x180013804`
- end: `0x180013e61`
- name: `?ClassInstall_InstallDevice@@YAKPEAXPEAU_SP_DEVINFO_DATA@@PEAU_SP_DEVINSTALL_PARAMS_W@@@Z`
- size: `1629`
- prototype: `unsigned int __fastcall(void *, struct _SP_DEVINFO_DATA *, struct _SP_DEVINSTALL_PARAMS_W *)`
- caller_count: `1`
- callee_count: `26`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180013260`

## callees

- `0x180002300`
- `0x180002f48`
- `0x180007944`
- `0x18000d57c`
- `0x18000d624`
- `0x180012cbc`
- `0x180012d2c`
- `0x180013804`
- `0x180014b2c`
- `0x180014c44`
- `0x180014ebc`
- `0x1800153ac`
- `0x1800154c4`
- `0x1800155f4`
- `0x1800156c4`
- `0x180015b84`
- `0x180015e6c`
- `0x180016028`
- `0x1800162c8`
- `0x1800166b0`
- `0x18001c5c0`
- `0x18001c660`
- `0x18001e4f0`
- `0x180026820`
- `0x180036664`
- `0x18003a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001391b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001394c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013c5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001391b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001394c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013c5f`
- `SETUPAPI!SetupDiGetDeviceInstanceIdW` at `0x1800138fa`
- `SETUPAPI!SetupDiGetDeviceInstanceIdW` at `0x1800138fa`
- `SETUPAPI!SetupDiGetDevicePropertyW` at `0x1800139ce`
- `SETUPAPI!SetupDiGetDevicePropertyW` at `0x180013a24`
- `SETUPAPI!SetupDiGetDevicePropertyW` at `0x1800139ce`
- `SETUPAPI!SetupDiGetDevicePropertyW` at `0x180013a24`
- `SETUPAPI!SetupDiGetSelectedDriverW` at `0x180013911`
- `SETUPAPI!SetupDiGetSelectedDriverW` at `0x180013911`
- `SETUPAPI!SetupDiSetDeviceInstallParamsW` at `0x180013def`
- `SETUPAPI!SetupDiSetDeviceInstallParamsW` at `0x180013def`

## string_xrefs

- `0x1800138bf`: `ClassInstall_InstallDevice : Enter`
- `0x1800138c9`: `ClassInstall_InstallDevice`
- `0x18001395e`: `ClassInstall_InstallDevice`
- `0x1800139e1`: `ClassInstall_InstallDevice`
- `0x180013a35`: `ClassInstall_InstallDevice`
- `0x180013a7e`: `ClassInstall_InstallDevice`
- `0x180013af7`: `ClassInstall_InstallDevice`
- `0x180013b22`: `ClassInstall_InstallDevice`
- `0x180013b66`: `ClassInstall_InstallDevice`
- `0x180013bdd`: `ClassInstall_InstallDevice`
- `0x180013c34`: `ClassInstall_InstallDevice`
- `0x180013c96`: `ClassInstall_InstallDevice`
- `0x180013e29`: `ClassInstall_InstallDevice`
- `0x1800139da`: `Devnode was created by WSDMon for an existing Queue.`
- `0x180013a2e`: `Devnode was created by CSR.`
- `0x180013a77`: `ClassInstall_InstallDevice: Unable to read the PKEY_Printer_Name property from CSR devnode.  Error %d`
- `0x180013b1b`: `Installation is for a printer connection. Ignoring missing properties.`
- `0x180013c2d`: `WaitForDeviceConfigurationIfNeeded failed: %d`
- `0x180013c8f`: `User SID information is present in the port devnode. Installing printer as per user printer.`
- `0x180013e22`: `ClassInstall_InstallDevice: exit %d`

## pseudocode

```c
__int64 __fastcall ClassInstall_InstallDevice(
        void *a1,
        struct _SP_DEVINFO_DATA *a2,
        struct _SP_DEVINSTALL_PARAMS_W *a3)
{
  unsigned __int16 *v5; // r15
  unsigned __int16 *v6; // rdi
  unsigned __int16 *v7; // r12
  unsigned __int16 *v8; // r14
  __int64 v10; // rax
  __int64 v11; // rsi
  DWORD LastError; // eax
  unsigned __int16 *v13; // rdx
  unsigned int updated; // ebx
  unsigned int IsNullPrinterDriver; // eax
  HDEVINFO v16; // rbx
  unsigned int StringValueViaSetupDi; // eax
  unsigned int PlugAndPlayInfo; // eax
  unsigned int v19; // eax
  struct _GUID *v20; // rbx
  int v21; // eax
  int v22; // ecx
  unsigned int v23; // eax
  unsigned int v24; // eax
  unsigned __int16 *v25; // rcx
  HDEVINFO v26; // rcx
  struct _SP_DEVINSTALL_PARAMS_W *v27; // r8
  BYTE PropertyBuffer[8]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 *v29; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 *v30; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v31; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 *v32; // [rsp+70h] [rbp-90h] BYREF
  struct _GUID *v33; // [rsp+78h] [rbp-88h] BYREF
  HDEVINFO DeviceInfoSet; // [rsp+80h] [rbp-80h]
  int v35; // [rsp+88h] [rbp-78h] BYREF
  DEVPROPTYPE PropertyType; // [rsp+8Ch] [rbp-74h] BYREF
  BYTE v37[8]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 *v38; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int16 *v39; // [rsp+A0h] [rbp-60h] BYREF
  int *v40; // [rsp+A8h] [rbp-58h] BYREF
  PSP_DEVINSTALL_PARAMS_W DeviceInstallParams; // [rsp+B0h] [rbp-50h]
  int v42; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v43; // [rsp+C8h] [rbp-38h]
  unsigned __int16 *v44; // [rsp+D0h] [rbp-30h]
  unsigned __int16 *v45; // [rsp+D8h] [rbp-28h]
  int v46; // [rsp+E0h] [rbp-20h]
  unsigned __int16 *v47; // [rsp+E8h] [rbp-18h]
  unsigned __int16 *v48; // [rsp+F0h] [rbp-10h]
  struct _GUID *v49; // [rsp+F8h] [rbp-8h]
  unsigned __int16 *v50; // [rsp+100h] [rbp+0h]
  unsigned __int16 *v51; // [rsp+108h] [rbp+8h]
  struct _SP_DRVINFO_DATA_V2_W DriverInfoData; // [rsp+110h] [rbp+10h] BYREF
  WCHAR DeviceInstanceId[200]; // [rsp+730h] [rbp+630h] BYREF
  unsigned __int16 v54[264]; // [rsp+8C0h] [rbp+7C0h] BYREF

  DeviceInstallParams = a3;
  DeviceInfoSet = a1;
  memset_0(&v42, 0, 0x50u);
  v40 = 0;
  memset_0(v54, 0, 0x208u);
  memset_0(&DriverInfoData, 0, sizeof(DriverInfoData));
  v31 = 0;
  v29 = 0;
  v38 = 0;
  v5 = 0;
  v39 = 0;
  v6 = 0;
  v32 = 0;
  v7 = 0;
  v30 = 0;
  v8 = 0;
  v35 = 0;
  v33 = 0;
  memset_0(DeviceInstanceId, 0, sizeof(DeviceInstanceId));
  PropertyType = 0;
  ClassInstallerTelemetry::WriteDbgTraceInfo("ClassInstall_InstallDevice", L"ClassInstall_InstallDevice : Enter");
  if ( !a2 )
    return 87;
  SetupDiGetDeviceInstanceIdW(a1, a2, DeviceInstanceId, 0xC8u, 0);
  DriverInfoData.cbSize = 1568;
  if ( !SetupDiGetSelectedDriverW(a1, a2, &DriverInfoData) && GetLastError() == -536870397 )
    return 3758096910LL;
  v10 = BuildInternalData((int)a1, (int)a2);
  v11 = v10;
  if ( !v10 )
  {
    LastError = GetLastError();
    v13 = L"BuildInternalData failed: %d";
LABEL_8:
    updated = LastError;
    ClassInstallerTelemetry::WriteDbgTraceError("ClassInstall_InstallDevice", v13, LastError);
    goto LABEL_45;
  }
  IsNullPrinterDriver = InfFileIsNullPrinterDriver(v10, (unsigned int)MyPlatform, &v35);
  updated = StatusFromHResult(IsNullPrinterDriver);
  if ( updated || v35 )
    goto LABEL_45;
  PropertyBuffer[0] = 0;
  if ( !SetupDiGetDevicePropertyW(DeviceInfoSet, a2, &stru_180041588, &PropertyType, PropertyBuffer, 1u, 0, 0) )
  {
    v16 = DeviceInfoSet;
    *(_DWORD *)v37 = 0;
    if ( SetupDiGetDevicePropertyW(DeviceInfoSet, a2, &stru_1800415A0, &PropertyType, v37, 4u, 0, 0) )
    {
      ClassInstallerTelemetry::WriteDbgTraceInfo("ClassInstall_InstallDevice", L"Devnode was created by CSR.");
      v30 = 0;
      StringValueViaSetupDi = GetStringValueViaSetupDi(v16, a2, (DEVPROPKEY *)&stru_180041808, &v30);
      updated = StringValueViaSetupDi;
      if ( StringValueViaSetupDi )
        ClassInstallerTelemetry::WriteDbgTraceError(
          "ClassInstall_InstallDevice",
          L"ClassInstall_InstallDevice: Unable to read the PKEY_Printer_Name property from CSR devnode.  Error %d",
          StringValueViaSetupDi);
      else
        updated = UpdateDriverForInstalledConnection((struct _PSETUP_LOCAL_DATA *)v11, v30);
      if ( v30 )
        ((void (*)(void))DllFreeSplMem)();
      goto LABEL_45;
    }
    PlugAndPlayInfo = GetPlugAndPlayInfo(v16, a2, &v31, &v29, &v33, &v32, &v38, &v39, &v30);
    updated = PlugAndPlayInfo;
    if ( PlugAndPlayInfo )
    {
      ClassInstallerTelemetry::WriteDbgTraceWarning(
        "ClassInstall_InstallDevice",
        L"GetPlugAndPlayInfo failed: %d",
        PlugAndPlayInfo);
      if ( updated == 1168 && (unsigned int)IsPrinterConnectionInstall(DeviceInfoSet, a2) )
      {
        ClassInstallerTelemetry::WriteDbgTraceInfo(
          "ClassInstall_InstallDevice",
          L"Installation is for a printer connection. Ignoring missing properties.");
        v5 = v31;
        v6 = v29;
        v7 = v32;
        v8 = v30;
        goto LABEL_44;
      }
    }
    else
    {
      v19 = ProcessPerInstanceAddRegSections(DeviceInfoSet, a2, (struct _PSETUP_LOCAL_DATA *)v11);
      updated = v19;
      if ( !v19 )
      {
        v8 = v30;
        v5 = v31;
        v7 = v32;
        v20 = v33;
        v6 = v29;
        if ( v30 )
          v21 = DuplicatePerUserDevice((struct _PSETUP_LOCAL_DATA *)v11, v29, v33, v32, v30);
        else
          v21 = DuplicateDevice((struct _PSETUP_LOCAL_DATA *)v11, v31, v29, v33);
        if ( v21 )
        {
          updated = 0;
          ClassInstallerTelemetry::WriteDbgTraceInfo(
            "ClassInstall_InstallDevice",
            L"Duplicate Device. PortName: %ws",
            v5);
          ClassInstallerTelemetry::PnpDevice<unsigned short const (&)[16],unsigned short * &,unsigned short * &,unsigned short * &,unsigned short * &,_GUID * &>(
            v22,
            (unsigned int)&v32,
            (unsigned int)&v31,
            v11 + 8,
            (__int64)&v29,
            (__int64)&v33);
          goto LABEL_45;
        }
        v23 = WaitForDeviceConfigurationIfNeeded(DeviceInfoSet, a2, v6);
        if ( v23 )
          ClassInstallerTelemetry::WriteDbgTraceError(
            "ClassInstall_InstallDevice",
            L"WaitForDeviceConfigurationIfNeeded failed: %d",
            v23);
        if ( !NewDriverForInstalledDevice((struct _PSETUP_LOCAL_DATA *)v11, v5, v6) )
        {
          if ( (unsigned int)LoadAndInitializePrintui() )
          {
            if ( v7 )
              StringCchCopyW(v54, 0x104u, v7);
            if ( v8 )
              ClassInstallerTelemetry::WriteDbgTraceInfo(
                "ClassInstall_InstallDevice",
                L"User SID information is present in the port devnode. Installing printer as per user printer.");
            v42 = 80;
            v43 = *(_QWORD *)(v11 + 8);
            v44 = v5;
            v45 = v54;
            v48 = v38;
            v47 = v39;
            v40 = &v42;
            v46 = 260;
            v49 = v20;
            v50 = v6;
            v51 = v8;
            ClassInstallerTelemetry::PnpDevice<unsigned short const (&)[10],unsigned short * &,unsigned short * &,unsigned short * &,unsigned short * &,_GUID * &>(
              L"NewDevice",
              (__int64)&v29,
              (__int64)&v33);
            v24 = ((__int64 (__fastcall *)(_QWORD, int **))dwfnPnPInterface)(0, &v40);
            updated = v24;
            if ( v24 )
              ClassInstallerTelemetry::WriteDbgTraceError(
                "ClassInstall_InstallDevice",
                L"dwfnPnPInterface failed: %d",
                v24);
            goto LABEL_45;
          }
          LastError = GetLastError();
          v13 = L"LoadAndInitializePrintui failed: %d";
          goto LABEL_8;
        }
        ClassInstallerTelemetry::PnpDevice<unsigned short const (&)[10],unsigned short * &,unsigned short * &,unsigned short * &,unsigned short * &,_GUID * &>(
          L"NewDriver",
          (__int64)&v29,
          (__int64)&v33);
LABEL_44:
        updated = 0;
        goto LABEL_45;
      }
      ClassInstallerTelemetry::WriteDbgTraceError(
        "ClassInstall_InstallDevice",
        L"ProcessPerInstanceAddRegSections failed: %d",
        v19);
    }
    v5 = v31;
    v6 = v29;
    v7 = v32;
    v8 = v30;
    goto LABEL_45;
  }
  ClassInstallerTelemetry::WriteDbgTraceInfo(
    "ClassInstall_InstallDevice",
    L"Devnode was created by WSDMon for an existing Queue.");
LABEL_45:
  DestroyLocalData((HLOCAL)v11);
  if ( v5 )
    DllFreeSplMem(v5);
  if ( v38 )
    DllFreeSplMem(v38);
  v25 = v39;
  if ( v39 )
    DllFreeSplMem(v39);
  if ( v7 )
    DllFreeSplMem(v7);
  if ( v6 )
    DllFreeSplMem(v6);
  if ( v8 )
    DllFreeSplMem(v8);
  if ( v33 )
    DllFreeSplMem(v33);
  if ( !updated )
  {
    v26 = DeviceInfoSet;
    v27 = DeviceInstallParams;
    DeviceInstallParams->Flags |= 0x1000000u;
    SetupDiSetDeviceInstallParamsW(v26, a2, v27);
    updated = -536870386;
  }
  if ( DeviceInstanceId[0] )
  {
    if ( (Microsoft_Windows_DocumentsEnableBits & 1) != 0 )
      McTemplateU0z_EventWriteTransfer(v25, DocPerf_Setup_PnPPrinterInstall_Stop, DeviceInstanceId);
  }
  ClassInstallerTelemetry::WriteDbgTraceInfo(
    "ClassInstall_InstallDevice",
    L"ClassInstall_InstallDevice: exit %d",
    updated);
  return updated;
}

```

## disassembly

```asm
0x180013804  mov     [rsp-8+arg_18], rbx
0x180013809  push    rbp
0x18001380a  push    rsi
0x18001380b  push    rdi
0x18001380c  push    r12
0x18001380e  push    r13
0x180013810  push    r14
0x180013812  push    r15
0x180013814  lea     rbp, [rsp-9E0h]
0x18001381c  sub     rsp, 0AE0h
0x180013823  mov     rax, cs:__security_cookie
0x18001382a  xor     rax, rsp
0x18001382d  mov     [rbp+0A10h+var_40], rax
0x180013834  mov     r13, rdx
0x180013837  mov     [rbp+0A10h+DeviceInstallParams], r8
0x18001383b  xor     edx, edx; Val
0x18001383d  mov     [rbp+0A10h+DeviceInfoSet], rcx
0x180013841  mov     rbx, rcx
0x180013844  lea     rcx, [rbp+0A10h+var_A50]; void *
0x180013848  lea     r8d, [rdx+50h]; Size
0x18001384c  call    memset_0
0x180013851  xor     esi, esi
0x180013853  lea     rcx, [rbp+0A10h+var_250]; void *
0x18001385a  xor     edx, edx; Val
0x18001385c  mov     [rbp+0A10h+var_A68], rsi
0x180013860  mov     r8d, 208h; Size
0x180013866  call    memset_0
0x18001386b  xor     edx, edx; Val
0x18001386d  lea     rcx, [rbp+0A10h+DriverInfoData]; void *
0x180013871  mov     r8d, 620h; Size
0x180013877  call    memset_0
0x18001387c  xor     edx, edx; Val
0x18001387e  mov     [rsp+0B10h+var_AA8], rsi
0x180013883  mov     r8d, 190h; Size
0x180013889  mov     [rsp+0B10h+var_AB8], rsi
0x18001388e  lea     rcx, [rbp+0A10h+DeviceInstanceId]; void *
0x180013895  mov     [rbp+0A10h+var_A78], rsi
0x180013899  mov     r15d, esi
0x18001389c  mov     [rbp+0A10h+var_A70], rsi
0x1800138a0  mov     edi, esi
0x1800138a2  mov     [rsp+0B10h+var_AA0], rsi
0x1800138a7  mov     r12d, esi
0x1800138aa  mov     [rsp+0B10h+var_AB0], rsi
0x1800138af  mov     r14d, esi
0x1800138b2  mov     [rbp+0A10h+var_A88], esi
0x1800138b5  mov     [rsp+0B10h+var_A98], rsi
0x1800138ba  call    memset_0
0x1800138bf  lea     rdx, aClassinstallIn_9; "ClassInstall_InstallDevice : Enter"
0x1800138c6  mov     [rbp+0A10h+PropertyType], esi
0x1800138c9  lea     rcx, aClassinstallIn_13; "ClassInstall_InstallDevice"
0x1800138d0  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800138d5  test    r13, r13
0x1800138d8  jnz     short loc_1800138E2
0x1800138da  lea     eax, [rsi+57h]
0x1800138dd  jmp     loc_180013E37
0x1800138e2  mov     r9d, 0C8h; DeviceInstanceIdSize
0x1800138e8  mov     [rsp+0B10h+RequiredSize], rsi; RequiredSize
0x1800138ed  lea     r8, [rbp+0A10h+DeviceInstanceId]; DeviceInstanceId
0x1800138f4  mov     rdx, r13; DeviceInfoData
0x1800138f7  mov     rcx, rbx; DeviceInfoSet
0x1800138fa  call    cs:__imp_SetupDiGetDeviceInstanceIdW
0x180013900  lea     r8, [rbp+0A10h+DriverInfoData]; DriverInfoData
0x180013904  mov     [rbp+0A10h+DriverInfoData.cbSize], 620h
0x18001390b  mov     rdx, r13; DeviceInfoData
0x18001390e  mov     rcx, rbx; DeviceInfoSet
0x180013911  call    cs:__imp_SetupDiGetSelectedDriverW
0x180013917  test    eax, eax
0x180013919  jnz     short loc_180013932
0x18001391b  call    cs:__imp_GetLastError
0x180013921  cmp     eax, 0E0000203h
0x180013926  jnz     short loc_180013932
0x180013928  mov     eax, 0E000020Eh
0x18001392d  jmp     loc_180013E37
0x180013932  mov     r8d, cs:MyPlatform
0x180013939  mov     rdx, r13; int
0x18001393c  mov     rcx, rbx; int
0x18001393f  call    BuildInternalData
0x180013944  mov     rsi, rax
0x180013947  test    rax, rax
0x18001394a  jnz     short loc_18001396F
0x18001394c  call    cs:__imp_GetLastError
0x180013952  lea     rdx, aBuildinternald_0; "BuildInternalData failed: %d"
0x180013959  mov     ebx, eax
0x18001395b  mov     r8d, eax
0x18001395e  lea     rcx, aClassinstallIn_13; "ClassInstall_InstallDevice"
0x180013965  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18001396a  jmp     loc_180013D6C
0x18001396f  mov     edx, cs:MyPlatform
0x180013975  lea     r8, [rbp+0A10h+var_A88]
0x180013979  mov     rcx, rsi
0x18001397c  call    InfFileIsNullPrinterDriver
0x180013981  mov     ecx, eax
0x180013983  call    StatusFromHResult
0x180013988  mov     ebx, eax
0x18001398a  xor     eax, eax
0x18001398c  test    ebx, ebx
0x18001398e  jnz     loc_180013D6C
0x180013994  cmp     [rbp+0A10h+var_A88], eax
0x180013997  jnz     loc_180013D6C
0x18001399d  mov     rcx, [rbp+0A10h+DeviceInfoSet]; DeviceInfoSet
0x1800139a1  lea     r9, [rbp+0A10h+PropertyType]; PropertyType
0x1800139a5  mov     [rsp+0B10h+Flags], eax; Flags
0x1800139a9  lea     r8, stru_180041588; PropertyKey
0x1800139b0  mov     [rsp+0B10h+var_AE0], rax; RequiredSize
0x1800139b5  mov     rdx, r13; DeviceInfoData
0x1800139b8  mov     [rsp+0B10h+PropertyBuffer], al
0x1800139bc  lea     rax, [rsp+0B10h+PropertyBuffer]
0x1800139c1  mov     [rsp+0B10h+PropertyBufferSize], 1; PropertyBufferSize
0x1800139c9  mov     [rsp+0B10h+RequiredSize], rax; PropertyBuffer
0x1800139ce  call    cs:__imp_SetupDiGetDevicePropertyW
0x1800139d4  xor     ecx, ecx
0x1800139d6  test    eax, eax
0x1800139d8  jz      short loc_1800139F2
0x1800139da  lea     rdx, aDevnodeWasCrea_0; "Devnode was created by WSDMon for an ex"...
0x1800139e1  lea     rcx, aClassinstallIn_13; "ClassInstall_InstallDevice"
0x1800139e8  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800139ed  jmp     loc_180013D6C
0x1800139f2  mov     rbx, [rbp+0A10h+DeviceInfoSet]
0x1800139f6  lea     rax, [rbp+0A10h+var_A80]
0x1800139fa  mov     [rsp+0B10h+Flags], ecx; Flags
0x1800139fe  lea     r9, [rbp+0A10h+PropertyType]; PropertyType
0x180013a02  mov     [rsp+0B10h+var_AE0], rcx; RequiredSize
0x180013a07  lea     r8, stru_1800415A0; PropertyKey
0x180013a0e  mov     dword ptr [rbp+0A10h+var_A80], ecx
0x180013a11  mov     rdx, r13; DeviceInfoData
0x180013a14  mov     [rsp+0B10h+PropertyBufferSize], 4; PropertyBufferSize
0x180013a1c  mov     rcx, rbx; DeviceInfoSet
0x180013a1f  mov     [rsp+0B10h+RequiredSize], rax; PropertyBuffer
0x180013a24  call    cs:__imp_SetupDiGetDevicePropertyW
0x180013a2a  test    eax, eax
0x180013a2c  jz      short loc_180013AA2
0x180013a2e  lea     rdx, aDevnodeWasCrea; "Devnode was created by CSR."
0x180013a35  lea     rcx, aClassinstallIn_13; "ClassInstall_InstallDevice"
0x180013a3c  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180013a41  lea     r9, [rsp+0B10h+var_AB0]; unsigned __int16 **
0x180013a46  mov     [rsp+0B10h+var_AB0], rdi
0x180013a4b  lea     r8, stru_180041808; PropertyKey
0x180013a52  mov     rdx, r13; DeviceInfoData
0x180013a55  mov     rcx, rbx; DeviceInfoSet
0x180013a58  call    ?GetStringValueViaSetupDi@@YAKPEAXPEAU_SP_DEVINFO_DATA@@PEBU_tagpropertykey@@PEAPEAG@Z; GetStringValueViaSetupDi(void *,_SP_DEVINFO_DATA *,_tagpropertykey const *,ushort * *)
0x180013a5d  mov     ebx, eax
0x180013a5f  test    eax, eax
0x180013a61  jnz     short loc_180013A74
0x180013a63  mov     rdx, [rsp+0B10h+var_AB0]; unsigned __int16 *
0x180013a68  mov     rcx, rsi; struct _PSETUP_LOCAL_DATA *
0x180013a6b  call    ?UpdateDriverForInstalledConnection@@YAKPEAU_PSETUP_LOCAL_DATA@@PEAG@Z; UpdateDriverForInstalledConnection(_PSETUP_LOCAL_DATA *,ushort *)
0x180013a70  mov     ebx, eax
0x180013a72  jmp     short loc_180013A8A
0x180013a74  mov     r8d, eax
0x180013a77  lea     rdx, aClassinstallIn_2; "ClassInstall_InstallDevice: Unable to r"...
0x180013a7e  lea     rcx, aClassinstallIn_13; "ClassInstall_InstallDevice"
0x180013a85  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180013a8a  mov     rcx, [rsp+0B10h+var_AB0]
0x180013a8f  test    rcx, rcx
0x180013a92  jz      loc_180013D6C
0x180013a98  call    DllFreeSplMem
0x180013a9d  jmp     loc_180013D6C
0x180013aa2  lea     rax, [rsp+0B10h+var_AB0]
0x180013aa7  mov     rdx, r13; DeviceInfoData
0x180013aaa  mov     [rsp+0B10h+var_AD0], rax; unsigned __int16 **
0x180013aaf  lea     r9, [rsp+0B10h+var_AB8]; unsigned __int16 **
0x180013ab4  lea     rax, [rbp+0A10h+var_A70]
0x180013ab8  mov     rcx, rbx; DeviceInfoSet
0x180013abb  mov     qword ptr [rsp+0B10h+Flags], rax; unsigned __int16 **
0x180013ac0  lea     r8, [rsp+0B10h+var_AA8]; unsigned __int16 **
0x180013ac5  lea     rax, [rbp+0A10h+var_A78]
0x180013ac9  mov     [rsp+0B10h+var_AE0], rax; unsigned __int16 **
0x180013ace  lea     rax, [rsp+0B10h+var_AA0]
0x180013ad3  mov     qword ptr [rsp+0B10h+PropertyBufferSize], rax; unsigned __int16 **
0x180013ad8  lea     rax, [rsp+0B10h+var_A98]
0x180013add  mov     [rsp+0B10h+RequiredSize], rax; struct _GUID **
0x180013ae2  call    ?GetPlugAndPlayInfo@@YAKPEAXPEAU_SP_DEVINFO_DATA@@PEAPEAG2PEAPEAU_GUID@@2222@Z; GetPlugAndPlayInfo(void *,_SP_DEVINFO_DATA *,ushort * *,ushort * *,_GUID * *,ushort * *,ushort * *,ushort * *,ushort * *)
0x180013ae7  mov     ebx, eax
0x180013ae9  test    eax, eax
0x180013aeb  jz      short loc_180013B47
0x180013aed  mov     r8d, eax
0x180013af0  lea     rdx, aGetplugandplay; "GetPlugAndPlayInfo failed: %d"
0x180013af7  lea     rcx, aClassinstallIn_13; "ClassInstall_InstallDevice"
0x180013afe  call    ?WriteDbgTraceWarning@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180013b03  cmp     ebx, 490h
0x180013b09  jnz     short loc_180013B72
0x180013b0b  mov     rcx, [rbp+0A10h+DeviceInfoSet]; void *
0x180013b0f  mov     rdx, r13; struct _SP_DEVINFO_DATA *
0x180013b12  call    ?IsPrinterConnectionInstall@@YAHPEAXPEAU_SP_DEVINFO_DATA@@@Z; IsPrinterConnectionInstall(void *,_SP_DEVINFO_DATA *)
0x180013b17  test    eax, eax
0x180013b19  jz      short loc_180013B72
0x180013b1b  lea     rdx, aInstallationIs; "Installation is for a printer connectio"...
0x180013b22  lea     rcx, aClassinstallIn_13; "ClassInstall_InstallDevice"
0x180013b29  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180013b2e  mov     r15, [rsp+0B10h+var_AA8]
0x180013b33  mov     rdi, [rsp+0B10h+var_AB8]
0x180013b38  mov     r12, [rsp+0B10h+var_AA0]
0x180013b3d  mov     r14, [rsp+0B10h+var_AB0]
0x180013b42  jmp     loc_180013D6A
0x180013b47  mov     rcx, [rbp+0A10h+DeviceInfoSet]; DeviceInfoSet
0x180013b4b  mov     r8, rsi; struct _PSETUP_LOCAL_DATA *
0x180013b4e  mov     rdx, r13; DeviceInfoData
0x180013b51  call    ?ProcessPerInstanceAddRegSections@@YAKPEAXPEAU_SP_DEVINFO_DATA@@PEAU_PSETUP_LOCAL_DATA@@@Z; ProcessPerInstanceAddRegSections(void *,_SP_DEVINFO_DATA *,_PSETUP_LOCAL_DATA *)
0x180013b56  mov     ebx, eax
0x180013b58  test    eax, eax
0x180013b5a  jz      short loc_180013B8B
0x180013b5c  mov     r8d, eax
0x180013b5f  lea     rdx, aProcessperinst; "ProcessPerInstanceAddRegSections failed"...
0x180013b66  lea     rcx, aClassinstallIn_13; "ClassInstall_InstallDevice"
0x180013b6d  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180013b72  mov     r15, [rsp+0B10h+var_AA8]
0x180013b77  mov     rdi, [rsp+0B10h+var_AB8]
0x180013b7c  mov     r12, [rsp+0B10h+var_AA0]
0x180013b81  mov     r14, [rsp+0B10h+var_AB0]
0x180013b86  jmp     loc_180013D6C
0x180013b8b  mov     r14, [rsp+0B10h+var_AB0]
0x180013b90  mov     rcx, rsi; struct _PSETUP_LOCAL_DATA *
0x180013b93  mov     r15, [rsp+0B10h+var_AA8]
0x180013b98  mov     r12, [rsp+0B10h+var_AA0]
0x180013b9d  mov     rbx, [rsp+0B10h+var_A98]
0x180013ba2  mov     rdi, [rsp+0B10h+var_AB8]
0x180013ba7  test    r14, r14
0x180013baa  jz      short loc_180013BC1
0x180013bac  mov     r9, r12; unsigned __int16 *
0x180013baf  mov     [rsp+0B10h+RequiredSize], r14; unsigned __int16 *
0x180013bb4  mov     r8, rbx; struct _GUID *
0x180013bb7  mov     rdx, rdi; unsigned __int16 *
0x180013bba  call    ?DuplicatePerUserDevice@@YAHPEAU_PSETUP_LOCAL_DATA@@PEAGPEAU_GUID@@11@Z; DuplicatePerUserDevice(_PSETUP_LOCAL_DATA *,ushort *,_GUID *,ushort *,ushort *)
0x180013bbf  jmp     short loc_180013BCF
0x180013bc1  mov     r9, rbx; struct _GUID *
0x180013bc4  mov     r8, rdi; unsigned __int16 *
0x180013bc7  mov     rdx, r15; unsigned __int16 *
0x180013bca  call    ?DuplicateDevice@@YAHPEAU_PSETUP_LOCAL_DATA@@PEAG1PEAU_GUID@@@Z; DuplicateDevice(_PSETUP_LOCAL_DATA *,ushort *,ushort *,_GUID *)
0x180013bcf  test    eax, eax
0x180013bd1  jz      short loc_180013C17
0x180013bd3  mov     r8, r15
0x180013bd6  lea     rdx, aDuplicateDevic; "Duplicate Device. PortName: %ws"
0x180013bdd  lea     rcx, aClassinstallIn_13; "ClassInstall_InstallDevice"
0x180013be4  xor     ebx, ebx
0x180013be6  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180013beb  lea     rax, [rsp+0B10h+var_A98]
0x180013bf0  mov     qword ptr [rsp+0B10h+PropertyBufferSize], rax
0x180013bf5  lea     r9, [rsi+8]
0x180013bf9  lea     rax, [rsp+0B10h+var_AB8]
0x180013bfe  lea     r8, [rsp+0B10h+var_AA8]
0x180013c03  mov     [rsp+0B10h+RequiredSize], rax
0x180013c08  lea     rdx, [rsp+0B10h+var_AA0]
0x180013c0d  call    ??$PnpDevice@AEAY0BA@$$CBGAEAPEAGAEAPEAGAEAPEAGAEAPEAGAEAPEAU_GUID@@@ClassInstallerTelemetry@@SAXAEAY0BA@$$CBGAEAPEAG111AEAPEAU_GUID@@@Z; ClassInstallerTelemetry::PnpDevice<ushort const (&)[16],ushort * &,ushort * &,ushort * &,ushort * &,_GUID * &>(ushort const (&)[16],ushort * &,ushort * &,ushort * &,ushort * &,_GUID * &)
0x180013c12  jmp     loc_180013D6C
0x180013c17  mov     rcx, [rbp+0A10h+DeviceInfoSet]; DeviceInfoSet
0x180013c1b  mov     r8, rdi; unsigned __int16 *
0x180013c1e  mov     rdx, r13; DeviceInfoData
0x180013c21  call    ?WaitForDeviceConfigurationIfNeeded@@YAKPEAXPEAU_SP_DEVINFO_DATA@@PEAG@Z; WaitForDeviceConfigurationIfNeeded(void *,_SP_DEVINFO_DATA *,ushort *)
0x180013c26  test    eax, eax
0x180013c28  jz      short loc_180013C40
0x180013c2a  mov     r8d, eax
0x180013c2d  lea     rdx, aWaitfordevicec_0; "WaitForDeviceConfigurationIfNeeded fail"...
0x180013c34  lea     rcx, aClassinstallIn_13; "ClassInstall_InstallDevice"
0x180013c3b  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180013c40  mov     r8, rdi; unsigned __int16 *
0x180013c43  mov     rdx, r15; unsigned __int16 *
0x180013c46  mov     rcx, rsi; struct _PSETUP_LOCAL_DATA *
0x180013c49  call    ?NewDriverForInstalledDevice@@YAHPEAU_PSETUP_LOCAL_DATA@@PEAG1@Z; NewDriverForInstalledDevice(_PSETUP_LOCAL_DATA *,ushort *,ushort *)
0x180013c4e  test    eax, eax
0x180013c50  jnz     loc_180013D3C
0x180013c56  call    ?LoadAndInitializePrintui@@YAHXZ; LoadAndInitializePrintui(void)
0x180013c5b  test    eax, eax
0x180013c5d  jnz     short loc_180013C71
0x180013c5f  call    cs:__imp_GetLastError
0x180013c65  lea     rdx, aLoadandinitial; "LoadAndInitializePrintui failed: %d"
0x180013c6c  jmp     loc_180013959
0x180013c71  test    r12, r12
0x180013c74  jz      short loc_180013C8A
0x180013c76  mov     r8, r12; unsigned __int16 *
0x180013c79  lea     rcx, [rbp+0A10h+var_250]; unsigned __int16 *
0x180013c80  mov     edx, 104h; unsigned __int64
0x180013c85  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180013c8a  test    r14, r14
0x180013c8d  jz      short loc_180013CA2
0x180013c8f  lea     rdx, aUserSidInforma; "User SID information is present in the "...
0x180013c96  lea     rcx, aClassinstallIn_13; "ClassInstall_InstallDevice"
0x180013c9d  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180013ca2  lea     r9, [rsi+8]
0x180013ca6  mov     [rbp+0A10h+var_A50], 50h ; 'P'
0x180013cad  mov     rax, [r9]
0x180013cb0  lea     r8, [rsp+0B10h+var_AA8]
0x180013cb5  mov     [rbp+0A10h+var_A48], rax
0x180013cb9  lea     rdx, [rsp+0B10h+var_AA0]
0x180013cbe  lea     rax, [rbp+0A10h+var_250]
0x180013cc5  mov     [rbp+0A10h+var_A40], r15
0x180013cc9  mov     [rbp+0A10h+var_A38], rax
0x180013ccd  lea     rcx, aNewdevice; "NewDevice"
0x180013cd4  mov     rax, [rbp+0A10h+var_A78]
0x180013cd8  mov     [rbp+0A10h+var_A20], rax
0x180013cdc  mov     rax, [rbp+0A10h+var_A70]
0x180013ce0  mov     [rbp+0A10h+var_A28], rax
0x180013ce4  lea     rax, [rbp+0A10h+var_A50]
0x180013ce8  mov     [rbp+0A10h+var_A68], rax
0x180013cec  lea     rax, [rsp+0B10h+var_A98]
0x180013cf1  mov     qword ptr [rsp+0B10h+PropertyBufferSize], rax; __int64
0x180013cf6  lea     rax, [rsp+0B10h+var_AB8]
0x180013cfb  mov     [rsp+0B10h+RequiredSize], rax; __int64
0x180013d00  mov     [rbp+0A10h+var_A30], 104h
0x180013d07  mov     [rbp+0A10h+var_A18], rbx
0x180013d0b  mov     [rbp+0A10h+var_A10], rdi
  ... truncated ...
```
