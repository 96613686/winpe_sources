# GetPlugAndPlayInfo(void *,_SP_DEVINFO_DATA *,ushort * *,ushort * *,_GUID * *,ushort * *,ushort * *,ushort * *,ushort * *)

- ea: `0x180014ebc`
- end: `0x1800153a5`
- name: `?GetPlugAndPlayInfo@@YAKPEAXPEAU_SP_DEVINFO_DATA@@PEAPEAG2PEAPEAU_GUID@@2222@Z`
- size: `1257`
- prototype: `unsigned int __usercall@<eax>(HDEVINFO DeviceInfoSet@<rcx>, PSP_DEVINFO_DATA DeviceInfoData@<rdx>, unsigned __int16 **@<r8>, unsigned __int16 **@<r9>, struct _GUID **, unsigned __int16 **, unsigned __int16 **, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180013804`

## callees

- `0x180002300`
- `0x18000d57c`
- `0x18000d624`
- `0x180014ebc`
- `0x1800153ac`
- `0x1800162c8`
- `0x18001bc44`
- `0x18001c660`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014f82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014ffa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015063`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015223`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015286`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800152e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800152ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014f82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014ffa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015063`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015223`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015286`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800152e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800152ec`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001507e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001507e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180014fd9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180015049`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180014fd9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180015049`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180015363`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180015363`
- `SETUPAPI!SetupDiSetDevicePropertyW` at `0x180015219`
- `SETUPAPI!SetupDiSetDevicePropertyW` at `0x18001527c`
- `SETUPAPI!SetupDiSetDevicePropertyW` at `0x180015219`
- `SETUPAPI!SetupDiSetDevicePropertyW` at `0x18001527c`
- `SETUPAPI!SetupDiGetDeviceInstanceIdW` at `0x1800152c1`
- `SETUPAPI!SetupDiGetDeviceInstanceIdW` at `0x1800152c1`
- `SETUPAPI!SetupDiGetDevicePropertyW` at `0x18001534a`
- `SETUPAPI!SetupDiGetDevicePropertyW` at `0x18001534a`
- `SETUPAPI!SetupDiOpenDevRegKey` at `0x180014f70`
- `SETUPAPI!SetupDiOpenDevRegKey` at `0x180014f70`

## string_xrefs

- `0x180014f95`: `SetupDiOpenDevRegKey failed: %d`
- `0x180015000`: `Failed to get PortName from device registry key: %d`
- `0x180015069`: `Failed to get PrinterName from device registry key: %d`
- `0x180015193`: `PortName='%ws', DeviceInstanceId='%ws', PrinterName='%ws', PrinterLocation='%ws', PrinterComment='%ws'`

## pseudocode

```c
__int64 __fastcall GetPlugAndPlayInfo(
        HDEVINFO DeviceInfoSet,
        PSP_DEVINFO_DATA DeviceInfoData,
        unsigned __int16 **a3,
        unsigned __int16 **a4,
        struct _GUID **a5,
        unsigned __int16 **a6,
        unsigned __int16 **a7,
        unsigned __int16 **a8,
        unsigned __int16 **a9)
{
  __int64 v13; // r15
  HKEY v14; // rbx
  DWORD LastError; // eax
  DWORD v16; // eax
  DWORD v17; // eax
  unsigned __int16 *v18; // rcx
  __int64 v19; // rbx
  unsigned __int16 **v20; // r15
  unsigned __int16 **v21; // r14
  unsigned __int16 **v22; // rsi
  unsigned __int16 **v23; // rax
  struct _GUID **v24; // rcx
  __int64 v25; // rax
  unsigned __int16 *v26; // rcx
  DWORD v27; // eax
  __int64 v28; // rax
  struct _GUID *v29; // rax
  DWORD PropertyType; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 **v31; // [rsp+48h] [rbp-B8h]
  unsigned __int16 **v32; // [rsp+50h] [rbp-B0h]
  unsigned __int16 **v33; // [rsp+58h] [rbp-A8h]
  struct _GUID **v34; // [rsp+60h] [rbp-A0h]
  unsigned __int16 **v35; // [rsp+68h] [rbp-98h]
  _OWORD pvData[33]; // [rsp+70h] [rbp-90h] BYREF

  v31 = a4;
  v34 = a5;
  v33 = a7;
  v32 = a8;
  v35 = a9;
  if ( !a9 )
    return 87;
  *a3 = 0;
  *a4 = 0;
  *a6 = 0;
  *a7 = 0;
  *a8 = 0;
  *a5 = 0;
  *a9 = 0;
  v13 = -1;
  v14 = SetupDiOpenDevRegKey(DeviceInfoSet, DeviceInfoData, 1u, 0, 1u, 1u);
  if ( v14 == HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
  {
    LastError = GetLastError();
    ClassInstallerTelemetry::WriteDbgTraceWarning("GetPlugAndPlayInfo", L"SetupDiOpenDevRegKey failed: %d", LastError);
  }
  else
  {
    PropertyType = 520;
    if ( RegGetValueW(v14, 0, L"PortName", 2u, 0, pvData, &PropertyType) )
    {
      v16 = GetLastError();
      ClassInstallerTelemetry::WriteDbgTraceWarning(
        "GetPlugAndPlayInfo",
        L"Failed to get PortName from device registry key: %d",
        v16);
    }
    else
    {
      *a3 = (unsigned __int16 *)AllocStr((unsigned __int16 *)pvData);
    }
    PropertyType = 520;
    if ( RegGetValueW(v14, 0, L"PrinterName", 2u, 0, pvData, &PropertyType) )
    {
      v17 = GetLastError();
      ClassInstallerTelemetry::WriteDbgTraceWarning(
        "GetPlugAndPlayInfo",
        L"Failed to get PrinterName from device registry key: %d",
        v17);
    }
    else
    {
      *a6 = (unsigned __int16 *)AllocStr((unsigned __int16 *)pvData);
    }
    RegCloseKey(v14);
  }
  v18 = *a3;
  if ( *a3 )
  {
    LODWORD(v19) = 0;
    v25 = -1;
    do
      ++v25;
    while ( v18[v25] );
    if ( !SetupDiSetDevicePropertyW(
            DeviceInfoSet,
            DeviceInfoData,
            &stru_180041680,
            0x12u,
            (const PBYTE)v18,
            2 * v25 + 2,
            0) )
    {
      v19 = GetLastError();
      ClassInstallerTelemetry::WriteDbgTraceError("GetPlugAndPlayInfo", L"Failed to set PKEY_Printer_PortName: %d", v19);
    }
    v26 = *a6;
    if ( *a6 )
    {
      do
        ++v13;
      while ( v26[v13] );
      if ( !SetupDiSetDevicePropertyW(
              DeviceInfoSet,
              DeviceInfoData,
              &stru_180041808,
              0x12u,
              (const PBYTE)v26,
              2 * v13 + 2,
              0) )
      {
        v27 = GetLastError();
        ClassInstallerTelemetry::WriteDbgTraceError("GetPlugAndPlayInfo", L"Failed to set PKEY_Printer_Name: %d", v27);
      }
    }
    if ( (_DWORD)v19 )
      goto LABEL_18;
LABEL_30:
    if ( SetupDiGetDeviceInstanceIdW(DeviceInfoSet, DeviceInfoData, (PWSTR)pvData, 0x104u, 0) )
    {
      v28 = AllocStr((unsigned __int16 *)pvData);
      v20 = v31;
      *v31 = (unsigned __int16 *)v28;
      if ( v28 )
        goto LABEL_35;
      LODWORD(v19) = GetLastError();
    }
    else
    {
      v19 = GetLastError();
      ClassInstallerTelemetry::WriteDbgTraceError("GetPlugAndPlayInfo", L"SetupDiGetDeviceInstanceId failed: %d", v19);
      v20 = v31;
    }
    if ( (_DWORD)v19 )
      goto LABEL_19;
LABEL_35:
    PropertyType = 0;
    if ( SetupDiGetDevicePropertyW(
           DeviceInfoSet,
           DeviceInfoData,
           &DEVPKEY_Device_ContainerId,
           &PropertyType,
           (PBYTE)pvData,
           0x10u,
           0,
           0)
      && PropertyType == 13 )
    {
      v29 = (struct _GUID *)LocalAlloc(0x40u, 0x10u);
      *v34 = v29;
      if ( v29 )
        *v29 = (struct _GUID)pvData[0];
    }
    GetStringValueViaSetupDi(DeviceInfoSet, DeviceInfoData, (DEVPROPKEY *)&stru_1800418C0, v35);
    v23 = v32;
    v21 = v33;
    goto LABEL_20;
  }
  LODWORD(v19) = GetStringValueViaSetupDi(DeviceInfoSet, DeviceInfoData, (DEVPROPKEY *)&stru_180041680, a3);
  if ( (_DWORD)v19 )
  {
    ClassInstallerTelemetry::WriteDbgTraceError(
      "GetPlugAndPlayInfo",
      L"Failed to retrieve PKEY_Printer_PortName: %d",
      (unsigned int)v19);
    goto LABEL_18;
  }
  LODWORD(v19) = GetStringValueViaSetupDi(DeviceInfoSet, DeviceInfoData, (DEVPROPKEY *)&stru_180041808, a6);
  if ( !(_DWORD)v19 )
  {
    GetStringValueViaSetupDi(DeviceInfoSet, DeviceInfoData, (DEVPROPKEY *)&stru_1800413F8, v33);
    GetStringValueViaSetupDi(DeviceInfoSet, DeviceInfoData, (DEVPROPKEY *)&stru_180041570, v32);
    goto LABEL_30;
  }
  ClassInstallerTelemetry::WriteDbgTraceError(
    "GetPlugAndPlayInfo",
    L"Failed to retrieve PKEY_Printer_Name: %d",
    (unsigned int)v19);
LABEL_18:
  v20 = v31;
LABEL_19:
  DllFreeSplMem(*a3);
  DllFreeSplMem(*v20);
  DllFreeSplMem(*a6);
  DllFreeSplMem(*v32);
  v21 = v33;
  DllFreeSplMem(*v33);
  DllFreeSplMem(*v34);
  v22 = v35;
  DllFreeSplMem(*v35);
  v23 = v32;
  v24 = v34;
  *a3 = 0;
  *v20 = 0;
  *a6 = 0;
  *v21 = 0;
  *v23 = 0;
  *v24 = 0;
  *v22 = 0;
LABEL_20:
  ClassInstallerTelemetry::WriteDbgTraceInfo(
    "GetPlugAndPlayInfo",
    L"PortName='%ws', DeviceInstanceId='%ws', PrinterName='%ws', PrinterLocation='%ws', PrinterComment='%ws'",
    *a3,
    *v20,
    *a6,
    *v21,
    *v23);
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x180014ebc  push    rbp
0x180014ebe  push    rbx
0x180014ebf  push    rsi
0x180014ec0  push    rdi
0x180014ec1  push    r12
0x180014ec3  push    r13
0x180014ec5  push    r14
0x180014ec7  push    r15
0x180014ec9  lea     rbp, [rsp-198h]
0x180014ed1  sub     rsp, 298h
0x180014ed8  mov     rax, cs:__security_cookie
0x180014edf  xor     rax, rsp
0x180014ee2  mov     [rbp+1D0h+var_50], rax
0x180014ee9  mov     r13, [rbp+1D0h+arg_28]
0x180014ef0  mov     rax, r9
0x180014ef3  mov     r9, [rbp+1D0h+arg_20]
0x180014efa  mov     rsi, rcx
0x180014efd  mov     rcx, [rbp+1D0h+arg_40]
0x180014f04  mov     r12, r8
0x180014f07  mov     r8, [rbp+1D0h+arg_38]
0x180014f0e  mov     r14, rdx
0x180014f11  mov     rdx, [rbp+1D0h+arg_30]
0x180014f18  xor     edi, edi
0x180014f1a  mov     [rsp+2D0h+var_288], rax
0x180014f1f  mov     [rsp+2D0h+var_270], r9
0x180014f24  mov     [rsp+2D0h+var_278], rdx
0x180014f29  mov     [rsp+2D0h+var_280], r8
0x180014f2e  mov     [rsp+2D0h+var_268], rcx
0x180014f33  test    rcx, rcx
0x180014f36  jnz     short loc_180014F40
0x180014f38  lea     eax, [rcx+57h]
0x180014f3b  jmp     loc_1800151C1
0x180014f40  mov     [r12], rdi
0x180014f44  mov     [rax], rdi
0x180014f47  mov     [r13+0], rdi
0x180014f4b  mov     [rdx], rdi
0x180014f4e  mov     rdx, r14; DeviceInfoData
0x180014f51  mov     [r8], rdi
0x180014f54  mov     r8d, 1; Scope
0x180014f5a  mov     [r9], rdi
0x180014f5d  xor     r9d, r9d; HwProfile
0x180014f60  mov     [rcx], rdi
0x180014f63  mov     rcx, rsi; DeviceInfoSet
0x180014f66  mov     [rsp+2D0h+samDesired], r8d; samDesired
0x180014f6b  mov     [rsp+2D0h+KeyType], r8d; KeyType
0x180014f70  call    cs:__imp_SetupDiOpenDevRegKey
0x180014f76  or      r15, 0FFFFFFFFFFFFFFFFh
0x180014f7a  mov     rbx, rax
0x180014f7d  cmp     rax, r15
0x180014f80  jnz     short loc_180014FA6
0x180014f82  call    cs:__imp_GetLastError
0x180014f88  lea     rdi, aGetplugandplay_0; "GetPlugAndPlayInfo"
0x180014f8f  mov     r8d, eax
0x180014f92  mov     rcx, rdi; char *
0x180014f95  lea     rdx, aSetupdiopendev; "SetupDiOpenDevRegKey failed: %d"
0x180014f9c  call    ?WriteDbgTraceWarning@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180014fa1  jmp     loc_180015084
0x180014fa6  lea     rax, [rsp+2D0h+PropertyType]
0x180014fab  mov     [rsp+2D0h+PropertyType], 208h
0x180014fb3  mov     [rsp+2D0h+pcbData], rax; pcbData
0x180014fb8  lea     r8, aPortname; "PortName"
0x180014fbf  lea     rax, [rsp+2D0h+pvData]
0x180014fc4  mov     r9d, 2; dwFlags
0x180014fca  mov     qword ptr [rsp+2D0h+samDesired], rax; pvData
0x180014fcf  xor     edx, edx; lpSubKey
0x180014fd1  mov     rcx, rbx; hkey
0x180014fd4  mov     qword ptr [rsp+2D0h+KeyType], rdi; pdwType
0x180014fd9  call    cs:__imp_RegGetValueW
0x180014fdf  lea     rdi, aGetplugandplay_0; "GetPlugAndPlayInfo"
0x180014fe6  test    eax, eax
0x180014fe8  jnz     short loc_180014FFA
0x180014fea  lea     rcx, [rsp+2D0h+pvData]; unsigned __int16 *
0x180014fef  call    AllocStr
0x180014ff4  mov     [r12], rax
0x180014ff8  jmp     short loc_180015012
0x180014ffa  call    cs:__imp_GetLastError
0x180015000  lea     rdx, aFailedToGetPor; "Failed to get PortName from device regi"...
0x180015007  mov     rcx, rdi; char *
0x18001500a  mov     r8d, eax
0x18001500d  call    ?WriteDbgTraceWarning@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180015012  lea     rax, [rsp+2D0h+PropertyType]
0x180015017  mov     [rsp+2D0h+PropertyType], 208h
0x18001501f  mov     [rsp+2D0h+pcbData], rax; pcbData
0x180015024  lea     r8, aPrintername; "PrinterName"
0x18001502b  lea     rax, [rsp+2D0h+pvData]
0x180015030  mov     r9d, 2; dwFlags
0x180015036  mov     qword ptr [rsp+2D0h+samDesired], rax; pvData
0x18001503b  xor     edx, edx; lpSubKey
0x18001503d  mov     rcx, rbx; hkey
0x180015040  mov     qword ptr [rsp+2D0h+KeyType], 0; pdwType
0x180015049  call    cs:__imp_RegGetValueW
0x18001504f  test    eax, eax
0x180015051  jnz     short loc_180015063
0x180015053  lea     rcx, [rsp+2D0h+pvData]; unsigned __int16 *
0x180015058  call    AllocStr
0x18001505d  mov     [r13+0], rax
0x180015061  jmp     short loc_18001507B
0x180015063  call    cs:__imp_GetLastError
0x180015069  lea     rdx, aFailedToGetPri; "Failed to get PrinterName from device r"...
0x180015070  mov     rcx, rdi; char *
0x180015073  mov     r8d, eax
0x180015076  call    ?WriteDbgTraceWarning@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18001507b  mov     rcx, rbx; hKey
0x18001507e  call    cs:__imp_RegCloseKey
0x180015084  mov     rcx, [r12]
0x180015088  xor     edx, edx
0x18001508a  test    rcx, rcx
0x18001508d  jnz     loc_1800151E4
0x180015093  mov     r9, r12; unsigned __int16 **
0x180015096  lea     r8, stru_180041680; PropertyKey
0x18001509d  mov     rdx, r14; DeviceInfoData
0x1800150a0  mov     rcx, rsi; DeviceInfoSet
0x1800150a3  call    ?GetStringValueViaSetupDi@@YAKPEAXPEAU_SP_DEVINFO_DATA@@PEBU_tagpropertykey@@PEAPEAG@Z; GetStringValueViaSetupDi(void *,_SP_DEVINFO_DATA *,_tagpropertykey const *,ushort * *)
0x1800150a8  xor     r15d, r15d
0x1800150ab  mov     ebx, eax
0x1800150ad  test    eax, eax
0x1800150af  jnz     short loc_180015108
0x1800150b1  mov     r9, r13; unsigned __int16 **
0x1800150b4  lea     r8, stru_180041808; PropertyKey
0x1800150bb  mov     rdx, r14; DeviceInfoData
0x1800150be  mov     rcx, rsi; DeviceInfoSet
0x1800150c1  call    ?GetStringValueViaSetupDi@@YAKPEAXPEAU_SP_DEVINFO_DATA@@PEBU_tagpropertykey@@PEAPEAG@Z; GetStringValueViaSetupDi(void *,_SP_DEVINFO_DATA *,_tagpropertykey const *,ushort * *)
0x1800150c6  mov     ebx, eax
0x1800150c8  test    eax, eax
0x1800150ca  jz      short loc_1800150D5
0x1800150cc  lea     rdx, aFailedToRetrie; "Failed to retrieve PKEY_Printer_Name: %"...
0x1800150d3  jmp     short loc_18001510F
0x1800150d5  mov     r9, [rsp+2D0h+var_278]; unsigned __int16 **
0x1800150da  lea     r8, stru_1800413F8; PropertyKey
0x1800150e1  mov     rdx, r14; DeviceInfoData
0x1800150e4  mov     rcx, rsi; DeviceInfoSet
0x1800150e7  call    ?GetStringValueViaSetupDi@@YAKPEAXPEAU_SP_DEVINFO_DATA@@PEBU_tagpropertykey@@PEAPEAG@Z; GetStringValueViaSetupDi(void *,_SP_DEVINFO_DATA *,_tagpropertykey const *,ushort * *)
0x1800150ec  mov     r9, [rsp+2D0h+var_280]; unsigned __int16 **
0x1800150f1  lea     r8, stru_180041570; PropertyKey
0x1800150f8  mov     rdx, r14; DeviceInfoData
0x1800150fb  mov     rcx, rsi; DeviceInfoSet
0x1800150fe  call    ?GetStringValueViaSetupDi@@YAKPEAXPEAU_SP_DEVINFO_DATA@@PEBU_tagpropertykey@@PEAPEAG@Z; GetStringValueViaSetupDi(void *,_SP_DEVINFO_DATA *,_tagpropertykey const *,ushort * *)
0x180015103  jmp     loc_1800152AB
0x180015108  lea     rdx, aFailedToRetrie_0; "Failed to retrieve PKEY_Printer_PortNam"...
0x18001510f  mov     rcx, rdi; char *
0x180015112  mov     r8d, ebx
0x180015115  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18001511a  mov     r15, [rsp+2D0h+var_288]
0x18001511f  mov     rcx, [r12]
0x180015123  call    DllFreeSplMem
0x180015128  mov     rcx, [r15]
0x18001512b  call    DllFreeSplMem
0x180015130  mov     rcx, [r13+0]
0x180015134  call    DllFreeSplMem
0x180015139  mov     rax, [rsp+2D0h+var_280]
0x18001513e  mov     rcx, [rax]
0x180015141  call    DllFreeSplMem
0x180015146  mov     r14, [rsp+2D0h+var_278]
0x18001514b  mov     rcx, [r14]
0x18001514e  call    DllFreeSplMem
0x180015153  mov     rax, [rsp+2D0h+var_270]
0x180015158  mov     rcx, [rax]
0x18001515b  call    DllFreeSplMem
0x180015160  mov     rsi, [rsp+2D0h+var_268]
0x180015165  mov     rcx, [rsi]
0x180015168  call    DllFreeSplMem
0x18001516d  mov     rax, [rsp+2D0h+var_280]
0x180015172  xor     edx, edx
0x180015174  mov     rcx, [rsp+2D0h+var_270]
0x180015179  mov     [r12], rdx
0x18001517d  mov     [r15], rdx
0x180015180  mov     [r13+0], rdx
0x180015184  mov     [r14], rdx
0x180015187  mov     [rax], rdx
0x18001518a  mov     [rcx], rdx
0x18001518d  mov     [rsi], rdx
0x180015190  mov     rax, [rax]
0x180015193  lea     rdx, aPortnameWsDevi; "PortName='%ws', DeviceInstanceId='%ws',"...
0x18001519a  mov     r9, [r15]
0x18001519d  mov     rcx, rdi; char *
0x1800151a0  mov     r8, [r12]
0x1800151a4  mov     [rsp+2D0h+pcbData], rax
0x1800151a9  mov     rax, [r14]
0x1800151ac  mov     qword ptr [rsp+2D0h+samDesired], rax
0x1800151b1  mov     rax, [r13+0]
0x1800151b5  mov     qword ptr [rsp+2D0h+KeyType], rax
0x1800151ba  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800151bf  mov     eax, ebx
0x1800151c1  mov     rcx, [rbp+1D0h+var_50]
0x1800151c8  xor     rcx, rsp; StackCookie
0x1800151cb  call    __security_check_cookie
0x1800151d0  add     rsp, 298h
0x1800151d7  pop     r15
0x1800151d9  pop     r14
0x1800151db  pop     r13
0x1800151dd  pop     r12
0x1800151df  pop     rdi
0x1800151e0  pop     rsi
0x1800151e1  pop     rbx
0x1800151e2  pop     rbp
0x1800151e3  retn
0x1800151e4  mov     ebx, edx
0x1800151e6  mov     rax, r15
0x1800151e9  inc     rax
0x1800151ec  cmp     [rcx+rax*2], dx
0x1800151f0  jnz     short loc_1800151E9
0x1800151f2  mov     dword ptr [rsp+2D0h+pcbData], edx; Flags
0x1800151f6  lea     eax, ds:2[rax*2]
0x1800151fd  mov     [rsp+2D0h+samDesired], eax; PropertyBufferSize
0x180015201  lea     r8, stru_180041680; PropertyKey
0x180015208  mov     qword ptr [rsp+2D0h+KeyType], rcx; PropertyBuffer
0x18001520d  mov     r9d, 12h; PropertyType
0x180015213  mov     rcx, rsi; DeviceInfoSet
0x180015216  mov     rdx, r14; DeviceInfoData
0x180015219  call    cs:__imp_SetupDiSetDevicePropertyW
0x18001521f  test    eax, eax
0x180015221  jnz     short loc_18001523D
0x180015223  call    cs:__imp_GetLastError
0x180015229  lea     rdx, aFailedToSetPke_1; "Failed to set PKEY_Printer_PortName: %d"
0x180015230  mov     rcx, rdi; char *
0x180015233  mov     r8d, eax
0x180015236  mov     ebx, eax
0x180015238  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18001523d  mov     rcx, [r13+0]
0x180015241  xor     eax, eax
0x180015243  test    rcx, rcx
0x180015246  jz      short loc_1800152A0
0x180015248  inc     r15
0x18001524b  cmp     [rcx+r15*2], ax
0x180015250  jnz     short loc_180015248
0x180015252  lea     eax, ds:2[r15*2]
0x18001525a  mov     rdx, r14; DeviceInfoData
0x18001525d  xor     r15d, r15d
0x180015260  lea     r8, stru_180041808; PropertyKey
0x180015267  mov     dword ptr [rsp+2D0h+pcbData], r15d; Flags
0x18001526c  mov     [rsp+2D0h+samDesired], eax; PropertyBufferSize
0x180015270  mov     qword ptr [rsp+2D0h+KeyType], rcx; PropertyBuffer
0x180015275  mov     rcx, rsi; DeviceInfoSet
0x180015278  lea     r9d, [r15+12h]; PropertyType
0x18001527c  call    cs:__imp_SetupDiSetDevicePropertyW
0x180015282  test    eax, eax
0x180015284  jnz     short loc_1800152A3
0x180015286  call    cs:__imp_GetLastError
0x18001528c  lea     rdx, aFailedToSetPke_0; "Failed to set PKEY_Printer_Name: %d"
0x180015293  mov     rcx, rdi; char *
0x180015296  mov     r8d, eax
0x180015299  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18001529e  jmp     short loc_1800152A3
0x1800152a0  xor     r15d, r15d
0x1800152a3  test    ebx, ebx
0x1800152a5  jnz     loc_18001511A
0x1800152ab  mov     r9d, 104h; DeviceInstanceIdSize
0x1800152b1  mov     qword ptr [rsp+2D0h+KeyType], r15; RequiredSize
0x1800152b6  lea     r8, [rsp+2D0h+pvData]; DeviceInstanceId
0x1800152bb  mov     rdx, r14; DeviceInfoData
0x1800152be  mov     rcx, rsi; DeviceInfoSet
0x1800152c1  call    cs:__imp_SetupDiGetDeviceInstanceIdW
0x1800152c7  test    eax, eax
0x1800152c9  jz      short loc_1800152EC
0x1800152cb  lea     rcx, [rsp+2D0h+pvData]; unsigned __int16 *
0x1800152d0  call    AllocStr
0x1800152d5  mov     r15, [rsp+2D0h+var_288]
0x1800152da  mov     [r15], rax
0x1800152dd  test    rax, rax
0x1800152e0  jnz     short loc_180015317
0x1800152e2  call    cs:__imp_GetLastError
0x1800152e8  mov     ebx, eax
0x1800152ea  jmp     short loc_18001530B
0x1800152ec  call    cs:__imp_GetLastError
0x1800152f2  lea     rdx, aSetupdigetdevi; "SetupDiGetDeviceInstanceId failed: %d"
0x1800152f9  mov     rcx, rdi; char *
0x1800152fc  mov     r8d, eax
0x1800152ff  mov     ebx, eax
0x180015301  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180015306  mov     r15, [rsp+2D0h+var_288]
0x18001530b  xor     eax, eax
0x18001530d  test    ebx, ebx
0x18001530f  jnz     loc_18001511F
0x180015315  jmp     short loc_180015319
0x180015317  xor     eax, eax
0x180015319  mov     [rsp+2D0h+Flags], eax; Flags
0x18001531d  lea     r9, [rsp+2D0h+PropertyType]; PropertyType
0x180015322  mov     [rsp+2D0h+pcbData], rax; RequiredSize
0x180015327  lea     r8, DEVPKEY_Device_ContainerId; PropertyKey
0x18001532e  mov     [rsp+2D0h+PropertyType], eax
0x180015332  mov     rdx, r14; DeviceInfoData
0x180015335  lea     rax, [rsp+2D0h+pvData]
0x18001533a  mov     [rsp+2D0h+samDesired], 10h; PropertyBufferSize
0x180015342  mov     rcx, rsi; DeviceInfoSet
0x180015345  mov     qword ptr [rsp+2D0h+KeyType], rax; PropertyBuffer
0x18001534a  call    cs:__imp_SetupDiGetDevicePropertyW
0x180015350  test    eax, eax
0x180015352  jz      short loc_18001537F
0x180015354  cmp     [rsp+2D0h+PropertyType], 0Dh
0x180015359  jnz     short loc_18001537F
0x18001535b  mov     edx, 10h; uBytes
0x180015360  lea     ecx, [rdx+30h]; uFlags
0x180015363  call    cs:__imp_LocalAlloc
0x180015369  mov     rcx, [rsp+2D0h+var_270]
0x18001536e  mov     [rcx], rax
0x180015371  test    rax, rax
0x180015374  jz      short loc_18001537F
0x180015376  movaps  xmm0, [rsp+2D0h+pvData]
0x18001537b  movdqu  xmmword ptr [rax], xmm0
0x18001537f  mov     r9, [rsp+2D0h+var_268]; unsigned __int16 **
  ... truncated ...
```
