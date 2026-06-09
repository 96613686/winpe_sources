# ClassInstall_InstallWizard(void *,_SP_DEVINFO_DATA *,_SP_DEVINSTALL_PARAMS_W *)

- ea: `0x1800141a4`
- end: `0x180014328`
- name: `?ClassInstall_InstallWizard@@YAKPEAXPEAU_SP_DEVINFO_DATA@@PEAU_SP_DEVINSTALL_PARAMS_W@@@Z`
- size: `388`
- prototype: `unsigned int __fastcall(HDEVINFO DeviceInfoSet, PSP_DEVINFO_DATA DeviceInfoData, struct _SP_DEVINSTALL_PARAMS_W *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180013260`

## callees

- `0x180002f48`
- `0x18000d624`
- `0x18001355c`
- `0x1800141a4`
- `0x1800155f4`
- `0x18003a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014245`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800142b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800142d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014245`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800142b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800142d7`
- `SETUPAPI!SetupDiSetClassInstallParamsW` at `0x1800142a9`
- `SETUPAPI!SetupDiSetClassInstallParamsW` at `0x1800142a9`
- `SETUPAPI!SetupDiGetClassInstallParamsW` at `0x180014223`
- `SETUPAPI!SetupDiGetClassInstallParamsW` at `0x180014223`
- `SETUPAPI!SetupDiSetDeviceInstallParamsW` at `0x1800142cd`
- `SETUPAPI!SetupDiSetDeviceInstallParamsW` at `0x1800142cd`

## string_xrefs

- `0x1800141e4`: `ClassInstall_InstallWizard - Enter`
- `0x1800141eb`: `ClassInstall_InstallWizard`
- `0x1800142fb`: `ClassInstall_InstallWizard`
- `0x1800142f4`: `ClassInstall_InstallWizard - Exit %d`

## pseudocode

```c
DWORD __fastcall ClassInstall_InstallWizard(
        HDEVINFO DeviceInfoSet,
        PSP_DEVINFO_DATA DeviceInfoData,
        struct _SP_DEVINSTALL_PARAMS_W *a3)
{
  DWORD LastError; // ebx
  __int128 v8; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v9; // [rsp+40h] [rbp-C0h]
  struct _SP_CLASSINSTALL_HEADER ClassInstallParams; // [rsp+50h] [rbp-B0h] BYREF
  __int128 *v11; // [rsp+158h] [rbp+58h] BYREF

  memset_0(&ClassInstallParams, 0, 0xD0u);
  v11 = 0;
  v8 = 0;
  v9 = 0;
  ClassInstallerTelemetry::WriteDbgTraceInfo("ClassInstall_InstallWizard", L"ClassInstall_InstallWizard - Enter");
  ClassInstallParams.cbSize = 8;
  if ( !SetupDiGetClassInstallParamsW(DeviceInfoSet, DeviceInfoData, &ClassInstallParams, 0xD0u, 0)
    || ClassInstallParams.InstallFunction != 16 )
  {
    return -536870386;
  }
  if ( !(unsigned int)LoadAndInitializePrintui() )
    return GetLastError();
  LODWORD(v8) = 32;
  *(_QWORD *)&v9 = &ClassInstallParams;
  *((_QWORD *)&v9 + 1) = a3->ClassInstallReserved;
  v11 = &v8;
  *((_QWORD *)&v8 + 1) = 0;
  LastError = ((__int64 (__fastcall *)(__int64, __int128 **))dwfnPnPInterface)(1, &v11);
  if ( LastError )
    goto LABEL_11;
  if ( !SetupDiSetClassInstallParamsW(DeviceInfoSet, DeviceInfoData, &ClassInstallParams, 0xD0u) )
    LastError = GetLastError();
  a3->ClassInstallReserved = *((_QWORD *)&v9 + 1);
  if ( !SetupDiSetDeviceInstallParamsW(DeviceInfoSet, DeviceInfoData, a3) )
    LastError = GetLastError();
  if ( LastError )
LABEL_11:
    ClassInstall_DestroyWizardData(DeviceInfoSet, DeviceInfoData, a3);
  ClassInstallerTelemetry::WriteDbgTraceInfo(
    "ClassInstall_InstallWizard",
    L"ClassInstall_InstallWizard - Exit %d",
    LastError);
  return LastError;
}

```

## disassembly

```asm
0x1800141a4  mov     [rsp-8+arg_0], rbx
0x1800141a9  mov     [rsp-8+arg_8], rsi
0x1800141ae  push    rbp
0x1800141af  push    rdi
0x1800141b0  push    r14
0x1800141b2  lea     rbp, [rsp-20h]
0x1800141b7  sub     rsp, 120h
0x1800141be  mov     rdi, r8
0x1800141c1  mov     rsi, rdx
0x1800141c4  mov     r14, rcx
0x1800141c7  xor     edx, edx; Val
0x1800141c9  mov     r8d, 0D0h; Size
0x1800141cf  lea     rcx, [rsp+130h+ClassInstallParams]; void *
0x1800141d4  call    memset_0
0x1800141d9  xorps   xmm0, xmm0
0x1800141dc  mov     [rbp+30h+arg_18], 0
0x1800141e4  lea     rdx, aClassinstallIn_12; "ClassInstall_InstallWizard - Enter"
0x1800141eb  lea     rcx, aClassinstallIn_1; "ClassInstall_InstallWizard"
0x1800141f2  movups  [rsp+130h+var_100], xmm0
0x1800141f7  movups  [rsp+130h+var_F0], xmm0
0x1800141fc  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180014201  mov     r9d, 0D0h; ClassInstallParamsSize
0x180014207  mov     [rsp+130h+ClassInstallParams.cbSize], 8
0x18001420f  lea     r8, [rsp+130h+ClassInstallParams]; ClassInstallParams
0x180014214  mov     [rsp+130h+RequiredSize], 0; RequiredSize
0x18001421d  mov     rdx, rsi; DeviceInfoData
0x180014220  mov     rcx, r14; DeviceInfoSet
0x180014223  call    cs:__imp_SetupDiGetClassInstallParamsW
0x180014229  test    eax, eax
0x18001422b  jz      loc_18001430B
0x180014231  cmp     [rsp+130h+ClassInstallParams.InstallFunction], 10h
0x180014236  jnz     loc_18001430B
0x18001423c  call    ?LoadAndInitializePrintui@@YAHXZ; LoadAndInitializePrintui(void)
0x180014241  test    eax, eax
0x180014243  jnz     short loc_180014250
0x180014245  call    cs:__imp_GetLastError
0x18001424b  jmp     loc_180014310
0x180014250  lea     rax, [rsp+130h+ClassInstallParams]
0x180014255  mov     dword ptr [rsp+130h+var_100], 20h ; ' '
0x18001425d  mov     qword ptr [rsp+130h+var_F0], rax
0x180014262  lea     rdx, [rbp+30h+arg_18]
0x180014266  mov     rax, [rdi+30h]
0x18001426a  mov     ecx, 1
0x18001426f  mov     qword ptr [rsp+130h+var_F0+8], rax
0x180014274  lea     rax, [rsp+130h+var_100]
0x180014279  mov     [rbp+30h+arg_18], rax
0x18001427d  mov     rax, cs:?dwfnPnPInterface@@3P6AKW4EPnPFunctionCode@@PEAT_TParameterBlock@@@ZEA; ulong (*dwfnPnPInterface)(EPnPFunctionCode,_TParameterBlock *)
0x180014284  mov     qword ptr [rsp+130h+var_100+8], 0
0x18001428d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014292  mov     ebx, eax
0x180014294  test    eax, eax
0x180014296  jnz     short loc_1800142E3
0x180014298  mov     r9d, 0D0h; ClassInstallParamsSize
0x18001429e  lea     r8, [rsp+130h+ClassInstallParams]; ClassInstallParams
0x1800142a3  mov     rdx, rsi; DeviceInfoData
0x1800142a6  mov     rcx, r14; DeviceInfoSet
0x1800142a9  call    cs:__imp_SetupDiSetClassInstallParamsW
0x1800142af  test    eax, eax
0x1800142b1  jnz     short loc_1800142BB
0x1800142b3  call    cs:__imp_GetLastError
0x1800142b9  mov     ebx, eax
0x1800142bb  mov     rax, qword ptr [rsp+130h+var_F0+8]
0x1800142c0  mov     r8, rdi; DeviceInstallParams
0x1800142c3  mov     rdx, rsi; DeviceInfoData
0x1800142c6  mov     [rdi+30h], rax
0x1800142ca  mov     rcx, r14; DeviceInfoSet
0x1800142cd  call    cs:__imp_SetupDiSetDeviceInstallParamsW
0x1800142d3  test    eax, eax
0x1800142d5  jnz     short loc_1800142DF
0x1800142d7  call    cs:__imp_GetLastError
0x1800142dd  mov     ebx, eax
0x1800142df  test    ebx, ebx
0x1800142e1  jz      short loc_1800142F1
0x1800142e3  mov     r8, rdi; struct _SP_DEVINSTALL_PARAMS_W *
0x1800142e6  mov     rdx, rsi; DeviceInfoData
0x1800142e9  mov     rcx, r14; DeviceInfoSet
0x1800142ec  call    ?ClassInstall_DestroyWizardData@@YAKPEAXPEAU_SP_DEVINFO_DATA@@PEAU_SP_DEVINSTALL_PARAMS_W@@@Z; ClassInstall_DestroyWizardData(void *,_SP_DEVINFO_DATA *,_SP_DEVINSTALL_PARAMS_W *)
0x1800142f1  mov     r8d, ebx
0x1800142f4  lea     rdx, aClassinstallIn_10; "ClassInstall_InstallWizard - Exit %d"
0x1800142fb  lea     rcx, aClassinstallIn_1; "ClassInstall_InstallWizard"
0x180014302  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180014307  mov     eax, ebx
0x180014309  jmp     short loc_180014310
0x18001430b  mov     eax, 0E000020Eh
0x180014310  lea     r11, [rsp+130h+var_10]
0x180014318  mov     rbx, [r11+20h]
0x18001431c  mov     rsi, [r11+28h]
0x180014320  mov     rsp, r11
0x180014323  pop     r14
0x180014325  pop     rdi
0x180014326  pop     rbp
0x180014327  retn
```
