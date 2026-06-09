# PSetupInstallDriverFromTheWeb(_DRIVER_INFO_6W const *,IDriverInstallStatusNotify *)

- ea: `0x18000ca40`
- end: `0x18000cc43`
- name: `?PSetupInstallDriverFromTheWeb@@YAJPEBU_DRIVER_INFO_6W@@PEAUIDriverInstallStatusNotify@@@Z`
- size: `515`
- prototype: `__int64 __fastcall(const struct _DRIVER_INFO_6W *, struct IDriverInstallStatusNotify *)`
- caller_count: `0`
- callee_count: `14`
- tags: `loader_planting, installer_update`

## callees

- `0x180002300`
- `0x180002f48`
- `0x18000ac60`
- `0x18000c2a4`
- `0x18000c368`
- `0x18000c398`
- `0x18000ca40`
- `0x18000d57c`
- `0x18000d624`
- `0x18000ea18`
- `0x18000ed30`
- `0x180011c20`
- `0x18002701c`
- `0x18003a010`

## import_xrefs

- `ntdll!RtlGetVersion` at `0x18000cae8`
- `ntdll!RtlGetVersion` at `0x18000cae8`

## string_xrefs

- `0x18000cb27`: `PSetupInstallDriverFromTheWeb`
- `0x18000cbf1`: `PSetupInstallDriverFromTheWeb`
- `0x18000cc0e`: `PSetupInstallDriverFromTheWeb`

## pseudocode

```c
__int64 __fastcall PSetupInstallDriverFromTheWeb(
        const struct _DRIVER_INFO_6W *a1,
        struct IDriverInstallStatusNotify *a2)
{
  NTSTATUS Version; // edi
  signed int DriverFromWindowsUpdate; // edi
  int inited; // ebx
  __int64 v7; // rcx
  __int64 v8; // r8
  int v9; // eax
  struct _OSVERSIONINFOW VersionInformation; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v12[16]; // [rsp+150h] [rbp+50h] BYREF
  unsigned __int16 v13[256]; // [rsp+160h] [rbp+60h] BYREF
  unsigned __int16 v14[256]; // [rsp+360h] [rbp+260h] BYREF
  unsigned __int16 v15[264]; // [rsp+560h] [rbp+460h] BYREF
  unsigned __int16 v16[264]; // [rsp+770h] [rbp+670h] BYREF
  unsigned __int16 v17[520]; // [rsp+980h] [rbp+880h] BYREF

  memset_0(&VersionInformation, 0, sizeof(VersionInformation));
  memset_0(v12, 0, 0x620u);
  if ( !a1 || !a2 )
  {
    DriverFromWindowsUpdate = -2147024809;
    goto LABEL_19;
  }
  if ( PrintCore::WindowsProtectedPrintHelpers::IsWindowsProtectedPrintEnabled()
    || !(unsigned int)IsFailoverToWindowsUpdateEnabled()
    || !(unsigned int)PSetupIsWindowsUpdateEnabled()
    || !(unsigned int)IsWindowsUpdateInternetAvailable() )
  {
    DriverFromWindowsUpdate = -2147023636;
    ClassInstallerTelemetry::WriteDbgTraceInfo("PSetupInstallDriverFromTheWeb", L"Download driver from WU disabled.");
LABEL_19:
    ClassInstallerTelemetry::WriteDbgTraceError(
      "PSetupInstallDriverFromTheWeb",
      L"Returning hr: 0x%x",
      (unsigned int)DriverFromWindowsUpdate);
    return (unsigned int)DriverFromWindowsUpdate;
  }
  VersionInformation.dwOSVersionInfoSize = 276;
  Version = RtlGetVersion(&VersionInformation);
  if ( Version < 0 )
  {
    DriverFromWindowsUpdate = Version | 0x10000000;
    if ( DriverFromWindowsUpdate < 0 )
      goto LABEL_19;
  }
  (**(void (__fastcall ***)(struct IDriverInstallStatusNotify *, __int64))a2)(a2, 4);
  inited = InitCodedownload(0);
  DriverFromWindowsUpdate = inited == 0 ? 0x80004005 : 0;
  ClassInstallerTelemetry::WriteDbgTraceInfo(
    "PSetupInstallDriverFromTheWeb",
    L"InitCodedownload returned hr: 0x%x",
    (unsigned int)DriverFromWindowsUpdate);
  if ( !inited )
    goto LABEL_19;
  v16[0] = 0;
  DriverFromWindowsUpdate = FillCatalog(v7, v16);
  if ( DriverFromWindowsUpdate < 0 )
    goto LABEL_19;
  DriverFromWindowsUpdate = FindDriverFromWindowsUpdate(a1, v16, v8, v17, v12);
  if ( DriverFromWindowsUpdate < 0 )
    goto LABEL_19;
  (**(void (__fastcall ***)(struct IDriverInstallStatusNotify *, __int64))a2)(a2, 5);
  v9 = InstallPrinterDriverFromTheWeb(0, v13, v14, v15, v17, &VersionInformation);
  DriverFromWindowsUpdate = v9;
  if ( v9 )
  {
    if ( v9 > 0 )
      DriverFromWindowsUpdate = (unsigned __int16)v9 | 0x80070000;
    if ( DriverFromWindowsUpdate < 0 )
      goto LABEL_19;
  }
  return (unsigned int)DriverFromWindowsUpdate;
}

```

## disassembly

```asm
0x18000ca40  mov     [rsp-8+arg_10], rbx
0x18000ca45  mov     [rsp-8+arg_18], rsi
0x18000ca4a  push    rbp
0x18000ca4b  push    rdi
0x18000ca4c  push    r14
0x18000ca4e  lea     rbp, [rsp-0CA0h]
0x18000ca56  sub     rsp, 0DA0h
0x18000ca5d  mov     rax, cs:__security_cookie
0x18000ca64  xor     rax, rsp
0x18000ca67  mov     [rbp+0CB0h+var_20], rax
0x18000ca6e  mov     rsi, rdx
0x18000ca71  mov     r14, rcx
0x18000ca74  mov     ebx, 114h
0x18000ca79  lea     rcx, [rsp+0DB0h+VersionInformation]; void *
0x18000ca7e  mov     r8d, ebx; Size
0x18000ca81  xor     edx, edx; Val
0x18000ca83  call    memset_0
0x18000ca88  xor     edx, edx; Val
0x18000ca8a  lea     rcx, [rbp+0CB0h+var_C60]; void *
0x18000ca8e  mov     r8d, 620h; Size
0x18000ca94  call    memset_0
0x18000ca99  test    r14, r14
0x18000ca9c  jz      loc_18000CBFF
0x18000caa2  test    rsi, rsi
0x18000caa5  jz      loc_18000CBFF
0x18000caab  call    ?IsWindowsProtectedPrintEnabled@WindowsProtectedPrintHelpers@PrintCore@@SA_NXZ; PrintCore::WindowsProtectedPrintHelpers::IsWindowsProtectedPrintEnabled(void)
0x18000cab0  test    al, al
0x18000cab2  jnz     loc_18000CBE5
0x18000cab8  call    ?IsFailoverToWindowsUpdateEnabled@@YAHXZ; IsFailoverToWindowsUpdateEnabled(void)
0x18000cabd  test    eax, eax
0x18000cabf  jz      loc_18000CBE5
0x18000cac5  call    PSetupIsWindowsUpdateEnabled
0x18000caca  test    eax, eax
0x18000cacc  jz      loc_18000CBE5
0x18000cad2  call    ?IsWindowsUpdateInternetAvailable@@YAHXZ; IsWindowsUpdateInternetAvailable(void)
0x18000cad7  test    eax, eax
0x18000cad9  jz      loc_18000CBE5
0x18000cadf  lea     rcx, [rsp+0DB0h+VersionInformation]; lpVersionInformation
0x18000cae4  mov     [rsp+0DB0h+VersionInformation.dwOSVersionInfoSize], ebx
0x18000cae8  call    cs:__imp_RtlGetVersion
0x18000caee  mov     edi, eax
0x18000caf0  test    eax, eax
0x18000caf2  jns     short loc_18000CB00
0x18000caf4  or      edi, 10000000h
0x18000cafa  jl      loc_18000CC04
0x18000cb00  mov     rax, [rsi]
0x18000cb03  mov     edx, 4
0x18000cb08  mov     rcx, rsi
0x18000cb0b  mov     rax, [rax]
0x18000cb0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb13  xor     ecx, ecx
0x18000cb15  call    InitCodedownload
0x18000cb1a  mov     ecx, eax
0x18000cb1c  lea     rdx, aInitcodedownlo_0; "InitCodedownload returned hr: 0x%x"
0x18000cb23  neg     ecx
0x18000cb25  mov     ebx, eax
0x18000cb27  lea     rcx, aPsetupinstalld_0; "PSetupInstallDriverFromTheWeb"
0x18000cb2e  sbb     edi, edi
0x18000cb30  not     edi
0x18000cb32  and     edi, 80004005h
0x18000cb38  mov     r8d, edi
0x18000cb3b  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18000cb40  test    ebx, ebx
0x18000cb42  jz      loc_18000CC04
0x18000cb48  xor     eax, eax
0x18000cb4a  lea     rdx, [rbp+0CB0h+var_640]; unsigned __int16 *
0x18000cb51  mov     [rbp+0CB0h+var_640], ax
0x18000cb58  call    ?FillCatalog@@YAJKPEAG@Z; FillCatalog(ulong,ushort *)
0x18000cb5d  mov     edi, eax
0x18000cb5f  test    eax, eax
0x18000cb61  js      loc_18000CC04
0x18000cb67  lea     rax, [rbp+0CB0h+var_C60]
0x18000cb6b  mov     rcx, r14
0x18000cb6e  lea     r9, [rbp+0CB0h+var_430]
0x18000cb75  mov     [rsp+0DB0h+var_D90], rax
0x18000cb7a  lea     rdx, [rbp+0CB0h+var_640]
0x18000cb81  call    FindDriverFromWindowsUpdate
0x18000cb86  mov     edi, eax
0x18000cb88  test    eax, eax
0x18000cb8a  js      short loc_18000CC04
0x18000cb8c  mov     rax, [rsi]
0x18000cb8f  mov     edx, 5
0x18000cb94  mov     rcx, rsi
0x18000cb97  mov     rax, [rax]
0x18000cb9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb9f  lea     rax, [rsp+0DB0h+VersionInformation]
0x18000cba4  xor     ecx, ecx
0x18000cba6  mov     [rsp+0DB0h+var_D88], rax
0x18000cbab  lea     r9, [rbp+0CB0h+var_850]
0x18000cbb2  lea     rax, [rbp+0CB0h+var_430]
0x18000cbb9  lea     r8, [rbp+0CB0h+var_A50]
0x18000cbc0  mov     [rsp+0DB0h+var_D90], rax
0x18000cbc5  lea     rdx, [rbp+0CB0h+var_C50]
0x18000cbc9  call    InstallPrinterDriverFromTheWeb
0x18000cbce  mov     edi, eax
0x18000cbd0  test    eax, eax
0x18000cbd2  jz      short loc_18000CC1A
0x18000cbd4  jle     short loc_18000CBDF
0x18000cbd6  movzx   edi, ax
0x18000cbd9  or      edi, 80070000h
0x18000cbdf  test    edi, edi
0x18000cbe1  jns     short loc_18000CC1A
0x18000cbe3  jmp     short loc_18000CC04
0x18000cbe5  lea     rdx, aDownloadDriver; "Download driver from WU disabled."
0x18000cbec  mov     edi, 800704ECh
0x18000cbf1  lea     rcx, aPsetupinstalld_0; "PSetupInstallDriverFromTheWeb"
0x18000cbf8  call    ?WriteDbgTraceInfo@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18000cbfd  jmp     short loc_18000CC04
0x18000cbff  mov     edi, 80070057h
0x18000cc04  mov     r8d, edi
0x18000cc07  lea     rdx, aReturningHr0xX; "Returning hr: 0x%x"
0x18000cc0e  lea     rcx, aPsetupinstalld_0; "PSetupInstallDriverFromTheWeb"
0x18000cc15  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18000cc1a  mov     eax, edi
0x18000cc1c  mov     rcx, [rbp+0CB0h+var_20]
0x18000cc23  xor     rcx, rsp; StackCookie
0x18000cc26  call    __security_check_cookie
0x18000cc2b  lea     r11, [rsp+0DB0h+var_10]
0x18000cc33  mov     rbx, [r11+30h]
0x18000cc37  mov     rsi, [r11+38h]
0x18000cc3b  mov     rsp, r11
0x18000cc3e  pop     r14
0x18000cc40  pop     rdi
0x18000cc41  pop     rbp
0x18000cc42  retn
```
