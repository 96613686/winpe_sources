# ClassInstall32(uint,void *,_SP_DEVINFO_DATA *)

- ea: `0x180013260`
- end: `0x180013496`
- name: `?ClassInstall32@@YAKIPEAXPEAU_SP_DEVINFO_DATA@@@Z`
- size: `566`
- prototype: `unsigned int(unsigned int, void *, struct _SP_DEVINFO_DATA *)`
- caller_count: `0`
- callee_count: `18`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180002300`
- `0x180002f48`
- `0x18000c368`
- `0x18000d624`
- `0x18000ea18`
- `0x180013260`
- `0x18001349c`
- `0x18001355c`
- `0x180013668`
- `0x180013804`
- `0x180013e68`
- `0x1800141a4`
- `0x180014330`
- `0x18001442c`
- `0x1800145fc`
- `0x1800148bc`
- `0x180014cf8`
- `0x180015c40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800132b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001340c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013430`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800132b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001340c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013430`
- `SETUPAPI!SetupDiGetDeviceInstallParamsW` at `0x1800132ad`
- `SETUPAPI!SetupDiGetDeviceInstallParamsW` at `0x1800132ad`

## string_xrefs

- `0x18001331b`: `Class installer invoked with WPP enabled. Action Code: %u Blocked Action: %d Error: %d`
- `0x180013322`: `ClassInstall32`
- `0x180013442`: `ClassInstall32`

## pseudocode

```c
__int64 __fastcall ClassInstall32(unsigned int a1, void *a2, struct _SP_DEVINFO_DATA *a3)
{
  DWORD LastError; // edi
  struct _SP_DEVINFO_DATA *v8; // rdx
  void *v9; // rcx
  struct _SP_DEVINSTALL_PARAMS_W *v10; // r8
  unsigned int v11; // r14d
  DWORD v12; // eax
  unsigned int v13; // ebx
  unsigned int v14; // ebx
  unsigned int v15; // ebx
  unsigned int v16; // ebx
  unsigned int v17; // ebx
  unsigned int v18; // ebx
  unsigned int v19; // ebx
  unsigned int v20; // ebx
  struct _SP_DEVINSTALL_PARAMS_W DeviceInstallParams; // [rsp+30h] [rbp-288h] BYREF

  memset_0(&DeviceInstallParams.Flags, 0, 0x244u);
  DeviceInstallParams.cbSize = 584;
  if ( !SetupDiGetDeviceInstallParamsW(a2, a3, &DeviceInstallParams) )
    return GetLastError();
  LastError = -536870386;
  if ( PrintCore::WindowsProtectedPrintHelpers::IsWindowsProtectedPrintEnabled() )
  {
    v11 = 0;
    switch ( a1 )
    {
      case 5u:
        v12 = ClassInstall_RemoveDevice(a2, a3, v10);
        break;
      case 0xCu:
LABEL_11:
        ClassInstallerTelemetry::WriteDbgTraceInfo(
          "ClassInstall32",
          L"Class installer invoked with WPP enabled. Action Code: %u Blocked Action: %d Error: %d",
          a1,
          v11,
          LastError);
        return LastError;
      case 0x17u:
        v12 = ClassInstall_SelectBestCompatDrv(a2, a3, v10);
        break;
      default:
        FireNotificationAndTelemetryEventForBlockedAction(a1, a2, a3);
        v11 = 1;
        goto LABEL_11;
    }
    LastError = v12;
    goto LABEL_11;
  }
  if ( a1 > 0x15 )
  {
    v17 = a1 - 23;
    if ( !v17 )
      return (DWORD)ClassInstall_SelectBestCompatDrv(a2, a3, v10);
    v18 = v17 - 1;
    if ( !v18 )
      return ClassInstall_AllowInstall(v9, v8, v10);
    v19 = v18 - 6;
    if ( !v19 )
      return (DWORD)ClassInstall_NewDevFinishInstall(a2, a3, &DeviceInstallParams);
    v20 = v19 - 7;
    if ( v20 )
    {
      if ( v20 == 5 )
        return (DWORD)ClassInstall_FinishInstallAction(a2, a3, v10);
    }
    else if ( (unsigned int)InitCodedownload(0) )
    {
      if ( SetPackageName(a2, a3) )
        LastError = 0;
      else
        LastError = GetLastError();
      ClassInstallerTelemetry::WriteDbgTraceInfo("ClassInstall32", L"SetPackageName returned :%d", LastError);
    }
    else
    {
      LastError = GetLastError();
      ClassInstallerTelemetry::WriteDbgTraceInfo("ClassInstall32", L"InitCodedownload returned :%d", LastError);
    }
  }
  else
  {
    if ( a1 == 21 )
      return (DWORD)ClassInstall_InstallDeviceFiles(a2, a3, &DeviceInstallParams);
    v13 = a1 - 1;
    if ( !v13 )
      return ClassInstall_SelectDevice(a2, a3);
    v14 = v13 - 1;
    if ( !v14 )
      return (DWORD)ClassInstall_InstallDevice(a2, a3, &DeviceInstallParams);
    v15 = v14 - 3;
    if ( !v15 )
      return ClassInstall_RemoveDevice(a2, a3, v10);
    v16 = v15 - 11;
    if ( !v16 )
      return ClassInstall_InstallWizard(a2, a3, &DeviceInstallParams);
    if ( v16 == 1 )
      return (DWORD)ClassInstall_DestroyWizardData(a2, a3, &DeviceInstallParams);
  }
  return LastError;
}

```

## disassembly

```asm
0x180013260  push    rbx
0x180013262  push    rbp
0x180013263  push    rsi
0x180013264  push    rdi
0x180013265  push    r14
0x180013267  sub     rsp, 290h
0x18001326e  mov     rax, cs:__security_cookie
0x180013275  xor     rax, rsp
0x180013278  mov     [rsp+2B8h+var_38], rax
0x180013280  mov     rbp, r8
0x180013283  mov     rsi, rdx
0x180013286  mov     ebx, ecx
0x180013288  xor     edx, edx; Val
0x18001328a  mov     r8d, 244h; Size
0x180013290  lea     rcx, [rsp+2B8h+DeviceInstallParams.Flags]; void *
0x180013295  call    memset_0
0x18001329a  lea     r8, [rsp+2B8h+DeviceInstallParams]; DeviceInstallParams
0x18001329f  mov     [rsp+2B8h+DeviceInstallParams.cbSize], 248h
0x1800132a7  mov     rdx, rbp; DeviceInfoData
0x1800132aa  mov     rcx, rsi; DeviceInfoSet
0x1800132ad  call    cs:__imp_SetupDiGetDeviceInstallParamsW
0x1800132b3  test    eax, eax
0x1800132b5  jnz     short loc_1800132C2
0x1800132b7  call    cs:__imp_GetLastError
0x1800132bd  jmp     loc_180013474
0x1800132c2  mov     edi, 0E000020Eh
0x1800132c7  call    ?IsWindowsProtectedPrintEnabled@WindowsProtectedPrintHelpers@PrintCore@@SA_NXZ; PrintCore::WindowsProtectedPrintHelpers::IsWindowsProtectedPrintEnabled(void)
0x1800132cc  test    al, al
0x1800132ce  jz      short loc_180013333
0x1800132d0  xor     r14d, r14d
0x1800132d3  cmp     ebx, 5
0x1800132d6  jz      short loc_180013304
0x1800132d8  cmp     ebx, 0Ch
0x1800132db  jz      short loc_180013311
0x1800132dd  cmp     ebx, 17h
0x1800132e0  jz      short loc_1800132F7
0x1800132e2  mov     r8, rbp; struct _SP_DEVINFO_DATA *
0x1800132e5  mov     rdx, rsi; void *
0x1800132e8  mov     ecx, ebx; unsigned int
0x1800132ea  call    ?FireNotificationAndTelemetryEventForBlockedAction@@YAXIPEAXPEAU_SP_DEVINFO_DATA@@@Z; FireNotificationAndTelemetryEventForBlockedAction(uint,void *,_SP_DEVINFO_DATA *)
0x1800132ef  mov     r14d, 1
0x1800132f5  jmp     short loc_180013311
0x1800132f7  mov     rdx, rbp; DeviceInfoData
0x1800132fa  mov     rcx, rsi; DeviceInfoSet
0x1800132fd  call    ?ClassInstall_SelectBestCompatDrv@@YAKPEAXPEAU_SP_DEVINFO_DATA@@PEAU_SP_DEVINSTALL_PARAMS_W@@@Z; ClassInstall_SelectBestCompatDrv(void *,_SP_DEVINFO_DATA *,_SP_DEVINSTALL_PARAMS_W *)
0x180013302  jmp     short loc_18001330F
0x180013304  mov     rdx, rbp; DeviceInfoData
0x180013307  mov     rcx, rsi; DeviceInfoSet
0x18001330a  call    ?ClassInstall_RemoveDevice@@YAKPEAXPEAU_SP_DEVINFO_DATA@@PEAU_SP_DEVINSTALL_PARAMS_W@@@Z; ClassInstall_RemoveDevice(void *,_SP_DEVINFO_DATA *,_SP_DEVINSTALL_PARAMS_W *)
0x18001330f  mov     edi, eax
0x180013311  mov     r9d, r14d
0x180013314  mov     [rsp+2B8h+var_298], edi
0x180013318  mov     r8d, ebx
0x18001331b  lea     rdx, aClassInstaller; "Class installer invoked with WPP enable"...
0x180013322  lea     rcx, aClassinstall32_0; "ClassInstall32"
0x180013329  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18001332e  jmp     loc_180013476
0x180013333  cmp     ebx, 15h
0x180013336  ja      loc_1800133CF
0x18001333c  jz      short loc_1800133BA
0x18001333e  sub     ebx, 1
0x180013341  jz      short loc_1800133AA
0x180013343  sub     ebx, 1
0x180013346  jz      short loc_180013395
0x180013348  sub     ebx, 3
0x18001334b  jz      short loc_180013385
0x18001334d  sub     ebx, 0Bh
0x180013350  jz      short loc_180013370
0x180013352  cmp     ebx, 1
0x180013355  jnz     loc_180013476
0x18001335b  lea     r8, [rsp+2B8h+DeviceInstallParams]; struct _SP_DEVINSTALL_PARAMS_W *
0x180013360  mov     rdx, rbp; DeviceInfoData
0x180013363  mov     rcx, rsi; DeviceInfoSet
0x180013366  call    ?ClassInstall_DestroyWizardData@@YAKPEAXPEAU_SP_DEVINFO_DATA@@PEAU_SP_DEVINSTALL_PARAMS_W@@@Z; ClassInstall_DestroyWizardData(void *,_SP_DEVINFO_DATA *,_SP_DEVINSTALL_PARAMS_W *)
0x18001336b  jmp     loc_180013474
0x180013370  lea     r8, [rsp+2B8h+DeviceInstallParams]; struct _SP_DEVINSTALL_PARAMS_W *
0x180013375  mov     rdx, rbp; DeviceInfoData
0x180013378  mov     rcx, rsi; DeviceInfoSet
0x18001337b  call    ?ClassInstall_InstallWizard@@YAKPEAXPEAU_SP_DEVINFO_DATA@@PEAU_SP_DEVINSTALL_PARAMS_W@@@Z; ClassInstall_InstallWizard(void *,_SP_DEVINFO_DATA *,_SP_DEVINSTALL_PARAMS_W *)
0x180013380  jmp     loc_180013474
0x180013385  mov     rdx, rbp; DeviceInfoData
0x180013388  mov     rcx, rsi; DeviceInfoSet
0x18001338b  call    ?ClassInstall_RemoveDevice@@YAKPEAXPEAU_SP_DEVINFO_DATA@@PEAU_SP_DEVINSTALL_PARAMS_W@@@Z; ClassInstall_RemoveDevice(void *,_SP_DEVINFO_DATA *,_SP_DEVINSTALL_PARAMS_W *)
0x180013390  jmp     loc_180013474
0x180013395  lea     r8, [rsp+2B8h+DeviceInstallParams]; struct _SP_DEVINSTALL_PARAMS_W *
0x18001339a  mov     rdx, rbp; struct _SP_DEVINFO_DATA *
0x18001339d  mov     rcx, rsi; void *
0x1800133a0  call    ?ClassInstall_InstallDevice@@YAKPEAXPEAU_SP_DEVINFO_DATA@@PEAU_SP_DEVINSTALL_PARAMS_W@@@Z; ClassInstall_InstallDevice(void *,_SP_DEVINFO_DATA *,_SP_DEVINSTALL_PARAMS_W *)
0x1800133a5  jmp     loc_180013474
0x1800133aa  mov     rdx, rbp; DeviceInfoData
0x1800133ad  mov     rcx, rsi; DeviceInfoSet
0x1800133b0  call    ?ClassInstall_SelectDevice@@YAKPEAXPEAU_SP_DEVINFO_DATA@@@Z; ClassInstall_SelectDevice(void *,_SP_DEVINFO_DATA *)
0x1800133b5  jmp     loc_180013474
0x1800133ba  lea     r8, [rsp+2B8h+DeviceInstallParams]; struct _SP_DEVINSTALL_PARAMS_W *
0x1800133bf  mov     rdx, rbp; struct _SP_DEVINFO_DATA *
0x1800133c2  mov     rcx, rsi; DeviceInfoSet
0x1800133c5  call    ?ClassInstall_InstallDeviceFiles@@YAKPEAXPEAU_SP_DEVINFO_DATA@@PEAU_SP_DEVINSTALL_PARAMS_W@@@Z; ClassInstall_InstallDeviceFiles(void *,_SP_DEVINFO_DATA *,_SP_DEVINSTALL_PARAMS_W *)
0x1800133ca  jmp     loc_180013474
0x1800133cf  sub     ebx, 17h
0x1800133d2  jz      loc_180013469
0x1800133d8  sub     ebx, 1
0x1800133db  jz      loc_180013462
0x1800133e1  sub     ebx, 6
0x1800133e4  jz      short loc_180013450
0x1800133e6  sub     ebx, 7
0x1800133e9  jz      short loc_180013401
0x1800133eb  cmp     ebx, 5
0x1800133ee  jnz     loc_180013476
0x1800133f4  mov     rdx, rbp; DeviceInfoData
0x1800133f7  mov     rcx, rsi; DeviceInfoSet
0x1800133fa  call    ?ClassInstall_FinishInstallAction@@YAKPEAXPEAU_SP_DEVINFO_DATA@@PEAU_SP_DEVINSTALL_PARAMS_W@@@Z; ClassInstall_FinishInstallAction(void *,_SP_DEVINFO_DATA *,_SP_DEVINSTALL_PARAMS_W *)
0x1800133ff  jmp     short loc_180013474
0x180013401  xor     ecx, ecx
0x180013403  call    InitCodedownload
0x180013408  test    eax, eax
0x18001340a  jnz     short loc_18001341D
0x18001340c  call    cs:__imp_GetLastError
0x180013412  mov     edi, eax
0x180013414  lea     rdx, aInitcodedownlo; "InitCodedownload returned :%d"
0x18001341b  jmp     short loc_18001343F
0x18001341d  mov     rdx, rbp; DeviceInfoData
0x180013420  mov     rcx, rsi; DeviceInfoSet
0x180013423  call    ?SetPackageName@@YAHPEAXPEAU_SP_DEVINFO_DATA@@@Z; SetPackageName(void *,_SP_DEVINFO_DATA *)
0x180013428  test    eax, eax
0x18001342a  jz      short loc_180013430
0x18001342c  xor     edi, edi
0x18001342e  jmp     short loc_180013438
0x180013430  call    cs:__imp_GetLastError
0x180013436  mov     edi, eax
0x180013438  lea     rdx, aSetpackagename; "SetPackageName returned :%d"
0x18001343f  mov     r8d, edi
0x180013442  lea     rcx, aClassinstall32_0; "ClassInstall32"
0x180013449  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18001344e  jmp     short loc_180013476
0x180013450  lea     r8, [rsp+2B8h+DeviceInstallParams]; DeviceInstallParams
0x180013455  mov     rdx, rbp; DeviceInfoData
0x180013458  mov     rcx, rsi; DeviceInfoSet
0x18001345b  call    ?ClassInstall_NewDevFinishInstall@@YAKPEAXPEAU_SP_DEVINFO_DATA@@PEAU_SP_DEVINSTALL_PARAMS_W@@@Z; ClassInstall_NewDevFinishInstall(void *,_SP_DEVINFO_DATA *,_SP_DEVINSTALL_PARAMS_W *)
0x180013460  jmp     short loc_180013474
0x180013462  call    ?ClassInstall_AllowInstall@@YAKPEAXPEAU_SP_DEVINFO_DATA@@PEAU_SP_DEVINSTALL_PARAMS_W@@@Z; ClassInstall_AllowInstall(void *,_SP_DEVINFO_DATA *,_SP_DEVINSTALL_PARAMS_W *)
0x180013467  jmp     short loc_180013474
0x180013469  mov     rdx, rbp; DeviceInfoData
0x18001346c  mov     rcx, rsi; DeviceInfoSet
0x18001346f  call    ?ClassInstall_SelectBestCompatDrv@@YAKPEAXPEAU_SP_DEVINFO_DATA@@PEAU_SP_DEVINSTALL_PARAMS_W@@@Z; ClassInstall_SelectBestCompatDrv(void *,_SP_DEVINFO_DATA *,_SP_DEVINSTALL_PARAMS_W *)
0x180013474  mov     edi, eax
0x180013476  mov     eax, edi
0x180013478  mov     rcx, [rsp+2B8h+var_38]
0x180013480  xor     rcx, rsp; StackCookie
0x180013483  call    __security_check_cookie
0x180013488  add     rsp, 290h
0x18001348f  pop     r14
0x180013491  pop     rdi
0x180013492  pop     rsi
0x180013493  pop     rbp
0x180013494  pop     rbx
0x180013495  retn
```
