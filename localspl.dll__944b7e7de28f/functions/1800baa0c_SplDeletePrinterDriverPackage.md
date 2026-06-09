# SplDeletePrinterDriverPackage

- ea: `0x1800baa0c`
- end: `0x1800baebe`
- name: `SplDeletePrinterDriverPackage`
- size: `1202`
- prototype: `__int64 __fastcall(unsigned __int16 *, NPackageInstallLocalspl *this, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x18007e088`
- `0x1800ad410`

## callees

- `0x1800051f0`
- `0x180015e28`
- `0x18002ff50`
- `0x180032d4c`
- `0x180046650`
- `0x180047330`
- `0x18004e678`
- `0x18005bf38`
- `0x1800b7f9c`
- `0x1800baa0c`
- `0x1800e6010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800badac`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800badac`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800bab22`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800bab72`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800babc4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800bac14`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800bab22`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800bab72`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800babc4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800bac14`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800bae6a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800bae6a`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800baacb`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800baacb`

## string_xrefs

- `0x1800baabf`: `setupapi.dll`
- `0x1800bae8d`: `Remove`
- `0x1800baae8`: `LoadLibrary failed`
- `0x1800baad1`: `SplDeletePrinterDriverPackage`
- `0x1800bac35`: `SplDeletePrinterDriverPackage`
- `0x1800bac8e`: `SplDeletePrinterDriverPackage`
- `0x1800bacda`: `SplDeletePrinterDriverPackage`
- `0x1800bad65`: `SplDeletePrinterDriverPackage`
- `0x1800bae33`: `SplDeletePrinterDriverPackage`
- `0x1800bab68`: `DriverStoreDeleteDriverPackageW`
- `0x1800bab8a`: `GetProcAddress (DriverStoreDeleteDriverPackageW) failed`
- `0x1800bae28`: `DriverStoreDeleteDriverPackage failed`

## pseudocode

```c
__int64 __fastcall SplDeletePrinterDriverPackage(
        unsigned __int16 *a1,
        NPackageInstallLocalspl *this,
        unsigned __int16 *a3,
        __int64 a4)
{
  const unsigned __int16 *v6; // r15
  int ProcessorArchitectureFromEnvironmentString; // ebx
  NCoreLibrary *v8; // rcx
  HMODULE LibraryW; // rsi
  NCoreLibrary *v10; // rcx
  FARPROC ProcAddress; // r13
  NCoreLibrary *v12; // rcx
  NCoreLibrary *v13; // rcx
  FARPROC v14; // r15
  NCoreLibrary *v15; // rcx
  FARPROC v16; // r12
  NCoreLibrary *v17; // rcx
  unsigned int LastErrorAsFailHRNoBreak; // ebx
  NCoreLibrary *v19; // rcx
  unsigned int v20; // ebx
  int *v21; // r9
  unsigned int v22; // r15d
  signed int v23; // eax
  __int16 v25; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v26; // [rsp+48h] [rbp-B8h]
  unsigned __int16 v27[4]; // [rsp+50h] [rbp-B0h] BYREF
  FARPROC v28; // [rsp+58h] [rbp-A8h]
  _DWORD v29[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v30; // [rsp+68h] [rbp-98h]
  __int16 v31; // [rsp+70h] [rbp-90h]
  __int64 v32; // [rsp+72h] [rbp-8Eh]
  __int16 v33; // [rsp+7Ah] [rbp-86h]
  wchar_t Str[264]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v35[528]; // [rsp+290h] [rbp+190h] BYREF

  v26 = a1;
  *(_DWORD *)v27 = 0;
  v6 = a1;
  if ( this && a3 && a4 )
  {
    if ( (unsigned int)ValidateObjectAccess(0, 1, 0, 0, a4, 0) )
    {
      memset_0(Str, 0, 0x208u);
      memset_0(v35, 0, 0x208u);
      v25 = -1;
      LibraryW = LoadLibraryW(L"setupapi.dll");
      if ( LibraryW
        || (ProcessorArchitectureFromEnvironmentString = NCoreLibrary::GetLastErrorAsFailHRNoBreak(v8),
            SplLogPrinterSetupGenericEvent(
              &SETUP_PRINTER_OPERATION_FAILED,
              L"SplDeletePrinterDriverPackage",
              L"LoadLibrary failed",
              0,
              a3,
              (unsigned __int16)ProcessorArchitectureFromEnvironmentString,
              ProcessorArchitectureFromEnvironmentString),
            ProcessorArchitectureFromEnvironmentString >= 0) )
      {
        ProcAddress = GetProcAddress(LibraryW, "SetupSetNonInteractiveMode");
        if ( ProcAddress
          || (ProcessorArchitectureFromEnvironmentString = NCoreLibrary::GetLastErrorAsFailHRNoBreak(v10),
              SplLogPrinterSetupGenericEvent(
                &SETUP_PRINTER_OPERATION_FAILED,
                L"SplDeletePrinterDriverPackage",
                L"GetProcAddress (SetupSetNonInteractiveMode) failed",
                0,
                a3,
                (unsigned __int16)ProcessorArchitectureFromEnvironmentString,
                ProcessorArchitectureFromEnvironmentString),
              ProcessorArchitectureFromEnvironmentString >= 0) )
        {
          v28 = GetProcAddress(LibraryW, "DriverStoreDeleteDriverPackageW");
          if ( v28
            || (ProcessorArchitectureFromEnvironmentString = NCoreLibrary::GetLastErrorAsFailHRNoBreak(v12),
                SplLogPrinterSetupGenericEvent(
                  &SETUP_PRINTER_OPERATION_FAILED,
                  L"SplDeletePrinterDriverPackage",
                  L"GetProcAddress (DriverStoreDeleteDriverPackageW) failed",
                  0,
                  a3,
                  (unsigned __int16)ProcessorArchitectureFromEnvironmentString,
                  ProcessorArchitectureFromEnvironmentString),
                ProcessorArchitectureFromEnvironmentString >= 0) )
          {
            v14 = GetProcAddress(LibraryW, "SetupGetInfPublishedNameW");
            if ( v14
              || (ProcessorArchitectureFromEnvironmentString = NCoreLibrary::GetLastErrorAsFailHRNoBreak(v13),
                  SplLogPrinterSetupGenericEvent(
                    &SETUP_PRINTER_OPERATION_FAILED,
                    L"SplDeletePrinterDriverPackage",
                    L"GetProcAddress (SetupGetInfPublishedNameW) failed",
                    0,
                    a3,
                    (unsigned __int16)ProcessorArchitectureFromEnvironmentString,
                    ProcessorArchitectureFromEnvironmentString),
                  ProcessorArchitectureFromEnvironmentString >= 0) )
            {
              v16 = GetProcAddress(LibraryW, "SetupGetInfDriverStoreLocationW");
              if ( v16
                || (ProcessorArchitectureFromEnvironmentString = NCoreLibrary::GetLastErrorAsFailHRNoBreak(v15),
                    SplLogPrinterSetupGenericEvent(
                      &SETUP_PRINTER_OPERATION_FAILED,
                      L"SplDeletePrinterDriverPackage",
                      L"GetProcAddress (SetupGetInfDriverStoreLocationW) failed",
                      0,
                      a3,
                      (unsigned __int16)ProcessorArchitectureFromEnvironmentString,
                      ProcessorArchitectureFromEnvironmentString),
                    ProcessorArchitectureFromEnvironmentString >= 0) )
              {
                if ( !((unsigned int (__fastcall *)(NPackageInstallLocalspl *, wchar_t *, __int64, _QWORD))v14)(
                        this,
                        Str,
                        260,
                        0) )
                {
                  LastErrorAsFailHRNoBreak = (unsigned __int16)NCoreLibrary::GetLastErrorAsFailHRNoBreak(v17);
                  SplLogPrinterSetupGenericEvent(
                    &SETUP_PRINTER_OPERATION_FAILED,
                    L"SplDeletePrinterDriverPackage",
                    L"SetupGetInfPublishedName failed",
                    0,
                    a3,
                    LastErrorAsFailHRNoBreak,
                    LastErrorAsFailHRNoBreak);
                }
                ProcessorArchitectureFromEnvironmentString = GetProcessorArchitectureFromEnvironmentString(a3, &v25);
                if ( ProcessorArchitectureFromEnvironmentString >= 0 )
                {
                  v31 = v25;
                  v30 = 0;
                  v32 = 0;
                  v33 = 0;
                  v29[0] = 28;
                  v29[1] = 2;
                  if ( !((unsigned int (__fastcall *)(wchar_t *, _DWORD *, _QWORD, _BYTE *, int, _QWORD))v16)(
                          Str,
                          v29,
                          0,
                          v35,
                          260,
                          0) )
                  {
                    v20 = (unsigned __int16)NCoreLibrary::GetLastErrorAsFailHRNoBreak(v19);
                    SplLogPrinterSetupGenericEvent(
                      &SETUP_PRINTER_OPERATION_FAILED,
                      L"SplDeletePrinterDriverPackage",
                      L"SetupGetInfDriverStoreLocation failed",
                      0,
                      a3,
                      v20,
                      v20);
                  }
                  if ( (unsigned int)_o__wcsicmp(this, v35) )
                  {
                    ProcessorArchitectureFromEnvironmentString = -2147024809;
                  }
                  else if ( wcsstr(Str, L"oem") == Str )
                  {
                    ProcessorArchitectureFromEnvironmentString = NPackageInstallLocalspl::IsPackageInUseAcrossIniSpoolers(
                                                                   this,
                                                                   a3,
                                                                   v27,
                                                                   v21);
                    if ( ProcessorArchitectureFromEnvironmentString >= 0 )
                    {
                      if ( *(_DWORD *)v27 )
                      {
                        ProcessorArchitectureFromEnvironmentString = -2147021881;
                      }
                      else
                      {
                        v22 = ((__int64 (__fastcall *)(__int64))ProcAddress)(1);
                        v23 = ((__int64 (__fastcall *)(NPackageInstallLocalspl *, _QWORD, _QWORD))v28)(this, 0, 0);
                        ProcessorArchitectureFromEnvironmentString = v23;
                        if ( v23 < 0 )
                          SplLogPrinterSetupGenericEvent(
                            &SETUP_PRINTER_OPERATION_FAILED,
                            L"SplDeletePrinterDriverPackage",
                            L"DriverStoreDeleteDriverPackage failed",
                            0,
                            a3,
                            (unsigned __int16)v23,
                            v23);
                        ((void (__fastcall *)(_QWORD))ProcAddress)(v22);
                      }
                    }
                  }
                  else
                  {
                    ProcessorArchitectureFromEnvironmentString = -2147024891;
                  }
                }
                else
                {
                  SplLogPrinterSetupGenericEvent(
                    &SETUP_PRINTER_OPERATION_FAILED,
                    L"SplDeletePrinterDriverPackage",
                    L"GetProcessorArchitectureFromEnvironmentString failed",
                    0,
                    a3,
                    (unsigned __int16)ProcessorArchitectureFromEnvironmentString,
                    ProcessorArchitectureFromEnvironmentString);
                }
              }
            }
            v6 = v26;
          }
        }
        if ( LibraryW )
          FreeLibrary(LibraryW);
      }
    }
    else
    {
      ProcessorArchitectureFromEnvironmentString = -2147024891;
    }
  }
  else
  {
    ProcessorArchitectureFromEnvironmentString = -2147024809;
  }
  LocalSpoolerTelemetry::LogPrinterDriverPackageChanged(
    L"Remove",
    v6,
    (const unsigned __int16 *)this,
    &qword_1800EBF90,
    a3,
    ProcessorArchitectureFromEnvironmentString);
  return (unsigned int)ProcessorArchitectureFromEnvironmentString;
}

```

## disassembly

```asm
0x1800baa0c  push    rbp
0x1800baa0e  push    rbx
0x1800baa0f  push    rsi
0x1800baa10  push    rdi
0x1800baa11  push    r12
0x1800baa13  push    r13
0x1800baa15  push    r14
0x1800baa17  push    r15
0x1800baa19  lea     rbp, [rsp-3B8h]
0x1800baa21  sub     rsp, 4B8h
0x1800baa28  mov     rax, cs:__security_cookie
0x1800baa2f  xor     rax, rsp
0x1800baa32  mov     [rbp+3F0h+var_50], rax
0x1800baa39  mov     [rsp+4F0h+var_4A8], rcx
0x1800baa3e  mov     rdi, r8
0x1800baa41  mov     dword ptr [rsp+4F0h+var_4A0], 0
0x1800baa49  mov     r14, rdx
0x1800baa4c  mov     r15, rcx
0x1800baa4f  test    rdx, rdx
0x1800baa52  jz      loc_1800BAE72
0x1800baa58  test    r8, r8
0x1800baa5b  jz      loc_1800BAE72
0x1800baa61  test    r9, r9
0x1800baa64  jz      loc_1800BAE72
0x1800baa6a  mov     [rsp+4F0h+var_4C8], 0
0x1800baa72  xor     r8d, r8d
0x1800baa75  mov     [rsp+4F0h+var_4D0], r9
0x1800baa7a  xor     ecx, ecx
0x1800baa7c  xor     r9d, r9d
0x1800baa7f  lea     edx, [r9+1]
0x1800baa83  call    ?ValidateObjectAccess@@YAHKKPEAXPEAKPEAU_INISPOOLER@@W4SERVER_MANAGEMENT_ACCESS_REQUEST@@@Z; ValidateObjectAccess(ulong,ulong,void *,ulong *,_INISPOOLER *,SERVER_MANAGEMENT_ACCESS_REQUEST)
0x1800baa88  test    eax, eax
0x1800baa8a  jnz     short loc_1800BAA96
0x1800baa8c  mov     ebx, 80070005h
0x1800baa91  jmp     loc_1800BAE77
0x1800baa96  mov     ebx, 208h
0x1800baa9b  lea     rcx, [rbp+3F0h+Str]; void *
0x1800baa9f  mov     r8d, ebx; Size
0x1800baaa2  xor     edx, edx; Val
0x1800baaa4  call    memset_0
0x1800baaa9  mov     r8d, ebx; Size
0x1800baaac  lea     rcx, [rbp+3F0h+var_260]; void *
0x1800baab3  xor     edx, edx; Val
0x1800baab5  call    memset_0
0x1800baaba  mov     eax, 0FFFFh
0x1800baabf  lea     rcx, LibFileName; "setupapi.dll"
0x1800baac6  mov     [rsp+4F0h+var_4B0], ax
0x1800baacb  call    cs:__imp_LoadLibraryW
0x1800baad1  lea     r12, aSpldeleteprint_10; "SplDeletePrinterDriverPackage"
0x1800baad8  mov     rsi, rax
0x1800baadb  test    rax, rax
0x1800baade  jnz     short loc_1800BAB18
0x1800baae0  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x1800baae5  movzx   ecx, ax
0x1800baae8  lea     r8, aLoadlibraryFai; "LoadLibrary failed"
0x1800baaef  mov     [rsp+4F0h+var_4C0], eax; unsigned int
0x1800baaf3  xor     r9d, r9d; unsigned __int16 *
0x1800baaf6  mov     [rsp+4F0h+var_4C8], ecx; unsigned int
0x1800baafa  mov     rdx, r12; unsigned __int16 *
0x1800baafd  lea     rcx, SETUP_PRINTER_OPERATION_FAILED; struct _EVENT_DESCRIPTOR *
0x1800bab04  mov     [rsp+4F0h+var_4D0], rdi; unsigned __int16 *
0x1800bab09  mov     ebx, eax
0x1800bab0b  call    ?SplLogPrinterSetupGenericEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEBG111KK@Z; SplLogPrinterSetupGenericEvent(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ulong)
0x1800bab10  test    ebx, ebx
0x1800bab12  js      loc_1800BAE77
0x1800bab18  lea     rdx, aSetupsetnonint; "SetupSetNonInteractiveMode"
0x1800bab1f  mov     rcx, rsi; hModule
0x1800bab22  call    cs:__imp_GetProcAddress
0x1800bab28  mov     r13, rax
0x1800bab2b  test    rax, rax
0x1800bab2e  jnz     short loc_1800BAB68
0x1800bab30  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x1800bab35  movzx   ecx, ax
0x1800bab38  lea     r8, aGetprocaddress_1; "GetProcAddress (SetupSetNonInteractiveM"...
0x1800bab3f  mov     [rsp+4F0h+var_4C0], eax; unsigned int
0x1800bab43  xor     r9d, r9d; unsigned __int16 *
0x1800bab46  mov     [rsp+4F0h+var_4C8], ecx; unsigned int
0x1800bab4a  mov     rdx, r12; unsigned __int16 *
0x1800bab4d  lea     rcx, SETUP_PRINTER_OPERATION_FAILED; struct _EVENT_DESCRIPTOR *
0x1800bab54  mov     [rsp+4F0h+var_4D0], rdi; unsigned __int16 *
0x1800bab59  mov     ebx, eax
0x1800bab5b  call    ?SplLogPrinterSetupGenericEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEBG111KK@Z; SplLogPrinterSetupGenericEvent(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ulong)
0x1800bab60  test    ebx, ebx
0x1800bab62  js      loc_1800BAE62
0x1800bab68  lea     rdx, aDriverstoredel; "DriverStoreDeleteDriverPackageW"
0x1800bab6f  mov     rcx, rsi; hModule
0x1800bab72  call    cs:__imp_GetProcAddress
0x1800bab78  mov     [rsp+4F0h+var_498], rax
0x1800bab7d  test    rax, rax
0x1800bab80  jnz     short loc_1800BABBA
0x1800bab82  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x1800bab87  movzx   ecx, ax
0x1800bab8a  lea     r8, aGetprocaddress_9; "GetProcAddress (DriverStoreDeleteDriver"...
0x1800bab91  mov     [rsp+4F0h+var_4C0], eax; unsigned int
0x1800bab95  xor     r9d, r9d; unsigned __int16 *
0x1800bab98  mov     [rsp+4F0h+var_4C8], ecx; unsigned int
0x1800bab9c  mov     rdx, r12; unsigned __int16 *
0x1800bab9f  lea     rcx, SETUP_PRINTER_OPERATION_FAILED; struct _EVENT_DESCRIPTOR *
0x1800baba6  mov     [rsp+4F0h+var_4D0], rdi; unsigned __int16 *
0x1800babab  mov     ebx, eax
0x1800babad  call    ?SplLogPrinterSetupGenericEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEBG111KK@Z; SplLogPrinterSetupGenericEvent(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ulong)
0x1800babb2  test    ebx, ebx
0x1800babb4  js      loc_1800BAE62
0x1800babba  lea     rdx, ProcName; "SetupGetInfPublishedNameW"
0x1800babc1  mov     rcx, rsi; hModule
0x1800babc4  call    cs:__imp_GetProcAddress
0x1800babca  mov     r15, rax
0x1800babcd  test    rax, rax
0x1800babd0  jnz     short loc_1800BAC0A
0x1800babd2  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x1800babd7  movzx   ecx, ax
0x1800babda  lea     r8, aGetprocaddress_6; "GetProcAddress (SetupGetInfPublishedNam"...
0x1800babe1  mov     [rsp+4F0h+var_4C0], eax; unsigned int
0x1800babe5  xor     r9d, r9d; unsigned __int16 *
0x1800babe8  mov     [rsp+4F0h+var_4C8], ecx; unsigned int
0x1800babec  mov     rdx, r12; unsigned __int16 *
0x1800babef  lea     rcx, SETUP_PRINTER_OPERATION_FAILED; struct _EVENT_DESCRIPTOR *
0x1800babf6  mov     [rsp+4F0h+var_4D0], rdi; unsigned __int16 *
0x1800babfb  mov     ebx, eax
0x1800babfd  call    ?SplLogPrinterSetupGenericEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEBG111KK@Z; SplLogPrinterSetupGenericEvent(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ulong)
0x1800bac02  test    ebx, ebx
0x1800bac04  js      loc_1800BAE5D
0x1800bac0a  lea     rdx, aSetupgetinfdri_0; "SetupGetInfDriverStoreLocationW"
0x1800bac11  mov     rcx, rsi; hModule
0x1800bac14  call    cs:__imp_GetProcAddress
0x1800bac1a  mov     r12, rax
0x1800bac1d  test    rax, rax
0x1800bac20  jnz     short loc_1800BAC5E
0x1800bac22  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x1800bac27  movzx   ecx, ax
0x1800bac2a  lea     r8, aGetprocaddress_0; "GetProcAddress (SetupGetInfDriverStoreL"...
0x1800bac31  mov     [rsp+4F0h+var_4C0], eax; unsigned int
0x1800bac35  lea     rdx, aSpldeleteprint_10; "SplDeletePrinterDriverPackage"
0x1800bac3c  mov     [rsp+4F0h+var_4C8], ecx; unsigned int
0x1800bac40  xor     r9d, r9d; unsigned __int16 *
0x1800bac43  lea     rcx, SETUP_PRINTER_OPERATION_FAILED; struct _EVENT_DESCRIPTOR *
0x1800bac4a  mov     [rsp+4F0h+var_4D0], rdi; unsigned __int16 *
0x1800bac4f  mov     ebx, eax
0x1800bac51  call    ?SplLogPrinterSetupGenericEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEBG111KK@Z; SplLogPrinterSetupGenericEvent(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ulong)
0x1800bac56  test    ebx, ebx
0x1800bac58  js      loc_1800BAE5D
0x1800bac5e  xor     r9d, r9d
0x1800bac61  lea     rdx, [rbp+3F0h+Str]
0x1800bac65  mov     r8d, 104h
0x1800bac6b  mov     rcx, r14
0x1800bac6e  mov     rax, r15
0x1800bac71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bac76  xor     r15d, r15d
0x1800bac79  test    eax, eax
0x1800bac7b  jnz     short loc_1800BACB9
0x1800bac7d  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x1800bac82  mov     ebx, eax
0x1800bac84  lea     r8, aSetupgetinfpub_1; "SetupGetInfPublishedName failed"
0x1800bac8b  movzx   eax, ax
0x1800bac8e  lea     rdx, aSpldeleteprint_10; "SplDeletePrinterDriverPackage"
0x1800bac95  mov     [rsp+4F0h+var_4C0], ebx; unsigned int
0x1800bac99  lea     rcx, SETUP_PRINTER_OPERATION_FAILED; struct _EVENT_DESCRIPTOR *
0x1800baca0  mov     [rsp+4F0h+var_4C8], eax; unsigned int
0x1800baca4  xor     r9d, r9d; unsigned __int16 *
0x1800baca7  mov     [rsp+4F0h+var_4D0], rdi; unsigned __int16 *
0x1800bacac  call    ?SplLogPrinterSetupGenericEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEBG111KK@Z; SplLogPrinterSetupGenericEvent(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ulong)
0x1800bacb1  test    ebx, ebx
0x1800bacb3  js      loc_1800BAE5D
0x1800bacb9  lea     rdx, [rsp+4F0h+var_4B0]
0x1800bacbe  mov     rcx, rdi
0x1800bacc1  call    GetProcessorArchitectureFromEnvironmentString
0x1800bacc6  mov     ebx, eax
0x1800bacc8  test    eax, eax
0x1800bacca  jns     short loc_1800BACFE
0x1800baccc  movzx   eax, bx
0x1800baccf  lea     r8, aGetprocessorar; "GetProcessorArchitectureFromEnvironment"...
0x1800bacd6  mov     [rsp+4F0h+var_4C0], ebx; unsigned int
0x1800bacda  lea     rdx, aSpldeleteprint_10; "SplDeletePrinterDriverPackage"
0x1800bace1  mov     [rsp+4F0h+var_4C8], eax; unsigned int
0x1800bace5  lea     rcx, SETUP_PRINTER_OPERATION_FAILED; struct _EVENT_DESCRIPTOR *
0x1800bacec  xor     r9d, r9d; unsigned __int16 *
0x1800bacef  mov     [rsp+4F0h+var_4D0], rdi; unsigned __int16 *
0x1800bacf4  call    ?SplLogPrinterSetupGenericEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEBG111KK@Z; SplLogPrinterSetupGenericEvent(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ulong)
0x1800bacf9  jmp     loc_1800BAE5D
0x1800bacfe  movzx   eax, [rsp+4F0h+var_4B0]
0x1800bad03  lea     r9, [rbp+3F0h+var_260]
0x1800bad0a  mov     [rsp+4F0h+var_480], ax
0x1800bad0f  lea     rdx, [rsp+4F0h+var_490]
0x1800bad14  mov     rax, r12
0x1800bad17  mov     qword ptr [rsp+4F0h+var_4C8], r15
0x1800bad1c  xor     r8d, r8d
0x1800bad1f  mov     [rsp+4F0h+var_488], r15
0x1800bad24  lea     rcx, [rbp+3F0h+Str]
0x1800bad28  mov     [rsp+4F0h+var_47E], r15
0x1800bad2d  mov     [rsp+4F0h+var_476], r15w
0x1800bad33  mov     [rsp+4F0h+var_490], 1Ch
0x1800bad3b  mov     [rsp+4F0h+var_48C], 2
0x1800bad43  mov     dword ptr [rsp+4F0h+var_4D0], 104h
0x1800bad4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bad50  test    eax, eax
0x1800bad52  jnz     short loc_1800BADA2
0x1800bad54  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x1800bad59  mov     ebx, eax
0x1800bad5b  lea     r8, aSetupgetinfdri_1; "SetupGetInfDriverStoreLocation failed"
0x1800bad62  movzx   eax, ax
0x1800bad65  lea     rdx, aSpldeleteprint_10; "SplDeletePrinterDriverPackage"
0x1800bad6c  mov     [rsp+4F0h+var_4C0], ebx; unsigned int
0x1800bad70  lea     rcx, SETUP_PRINTER_OPERATION_FAILED; struct _EVENT_DESCRIPTOR *
0x1800bad77  mov     [rsp+4F0h+var_4C8], eax; unsigned int
0x1800bad7b  xor     r9d, r9d; unsigned __int16 *
0x1800bad7e  mov     [rsp+4F0h+var_4D0], rdi; unsigned __int16 *
0x1800bad83  call    ?SplLogPrinterSetupGenericEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEBG111KK@Z; SplLogPrinterSetupGenericEvent(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ulong)
0x1800bad88  cmp     ebx, 80070490h
0x1800bad8e  jnz     short loc_1800BAD9A
0x1800bad90  mov     ebx, 80070057h
0x1800bad95  jmp     loc_1800BAE5D
0x1800bad9a  test    ebx, ebx
0x1800bad9c  js      loc_1800BAE5D
0x1800bada2  lea     rdx, [rbp+3F0h+var_260]
0x1800bada9  mov     rcx, r14
0x1800badac  call    cs:__imp__o__wcsicmp
0x1800badb2  test    eax, eax
0x1800badb4  jnz     short loc_1800BAD90
0x1800badb6  lea     rdx, aOem; "oem"
0x1800badbd  lea     rcx, [rbp+3F0h+Str]; Str
0x1800badc1  call    ?wcsstr@@YAPEAGPEAGPEBG@Z; wcsstr(ushort *,ushort const *)
0x1800badc6  lea     rcx, [rbp+3F0h+Str]
0x1800badca  cmp     rax, rcx
0x1800badcd  jz      short loc_1800BADD9
0x1800badcf  mov     ebx, 80070005h
0x1800badd4  jmp     loc_1800BAE5D
0x1800badd9  lea     r8, [rsp+4F0h+var_4A0]; unsigned __int16 *
0x1800badde  mov     rdx, rdi; unsigned __int16 *
0x1800bade1  mov     rcx, r14; this
0x1800bade4  call    ?IsPackageInUseAcrossIniSpoolers@NPackageInstallLocalspl@@YAJPEBG0PEAH@Z; NPackageInstallLocalspl::IsPackageInUseAcrossIniSpoolers(ushort const *,ushort const *,int *)
0x1800bade9  mov     ebx, eax
0x1800badeb  test    eax, eax
0x1800baded  js      short loc_1800BAE5D
0x1800badef  cmp     dword ptr [rsp+4F0h+var_4A0], r15d
0x1800badf4  jz      short loc_1800BADFD
0x1800badf6  mov     ebx, 80070BC7h
0x1800badfb  jmp     short loc_1800BAE5D
0x1800badfd  mov     ecx, 1
0x1800bae02  mov     rax, r13
0x1800bae05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bae0a  mov     r15d, eax
0x1800bae0d  xor     r8d, r8d
0x1800bae10  mov     rax, [rsp+4F0h+var_498]
0x1800bae15  xor     edx, edx
0x1800bae17  mov     rcx, r14
0x1800bae1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bae1f  mov     ebx, eax
0x1800bae21  test    eax, eax
0x1800bae23  jns     short loc_1800BAE52
0x1800bae25  movzx   ecx, ax
0x1800bae28  lea     r8, aDriverstoredel_0; "DriverStoreDeleteDriverPackage failed"
0x1800bae2f  mov     [rsp+4F0h+var_4C0], eax; unsigned int
0x1800bae33  lea     rdx, aSpldeleteprint_10; "SplDeletePrinterDriverPackage"
0x1800bae3a  mov     [rsp+4F0h+var_4C8], ecx; unsigned int
0x1800bae3e  xor     r9d, r9d; unsigned __int16 *
0x1800bae41  lea     rcx, SETUP_PRINTER_OPERATION_FAILED; struct _EVENT_DESCRIPTOR *
0x1800bae48  mov     [rsp+4F0h+var_4D0], rdi; unsigned __int16 *
0x1800bae4d  call    ?SplLogPrinterSetupGenericEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEBG111KK@Z; SplLogPrinterSetupGenericEvent(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,ulong)
0x1800bae52  mov     ecx, r15d
0x1800bae55  mov     rax, r13
0x1800bae58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bae5d  mov     r15, [rsp+4F0h+var_4A8]
0x1800bae62  test    rsi, rsi
0x1800bae65  jz      short loc_1800BAE77
0x1800bae67  mov     rcx, rsi; hLibModule
0x1800bae6a  call    cs:__imp_FreeLibrary
0x1800bae70  jmp     short loc_1800BAE77
0x1800bae72  mov     ebx, 80070057h
0x1800bae77  mov     [rsp+4F0h+var_4C8], ebx; int
0x1800bae7b  lea     r9, qword_1800EBF90; unsigned __int16 *
0x1800bae82  mov     r8, r14; unsigned __int16 *
0x1800bae85  mov     [rsp+4F0h+var_4D0], rdi; unsigned __int16 *
0x1800bae8a  mov     rdx, r15; unsigned __int16 *
0x1800bae8d  lea     rcx, aRemove; "Remove"
0x1800bae94  call    ?LogPrinterDriverPackageChanged@LocalSpoolerTelemetry@@SAXPEBG0000J@Z; LocalSpoolerTelemetry::LogPrinterDriverPackageChanged(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,long)
0x1800bae99  mov     eax, ebx
0x1800bae9b  mov     rcx, [rbp+3F0h+var_50]
0x1800baea2  xor     rcx, rsp; StackCookie
0x1800baea5  call    __security_check_cookie
0x1800baeaa  add     rsp, 4B8h
0x1800baeb1  pop     r15
0x1800baeb3  pop     r14
0x1800baeb5  pop     r13
0x1800baeb7  pop     r12
0x1800baeb9  pop     rdi
0x1800baeba  pop     rsi
0x1800baebb  pop     rbx
0x1800baebc  pop     rbp
0x1800baebd  retn
```
