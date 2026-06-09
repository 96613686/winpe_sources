# PSetupInstallClassDriver

- ea: `0x1800344b0`
- end: `0x180034776`
- name: `PSetupInstallClassDriver`
- size: `710`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x180002300`
- `0x180002f48`
- `0x18000b200`
- `0x18000c368`
- `0x18000d57c`
- `0x18001bc44`
- `0x18001c5c0`
- `0x180026820`
- `0x180027750`
- `0x1800284d0`
- `0x1800340b4`
- `0x1800344b0`
- `0x1800356a8`
- `0x180035728`
- `0x1800359b0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034678`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180034678`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x18003474d`
- `SETUPAPI!SetupDiDestroyDeviceInfoList` at `0x18003474d`
- `SETUPAPI!DriverStoreAddDriverPackageW` at `0x180034647`
- `SETUPAPI!DriverStoreAddDriverPackageW` at `0x180034647`
- `SETUPAPI!SetupOpenFileQueue` at `0x180034695`
- `SETUPAPI!SetupOpenFileQueue` at `0x180034695`
- `SETUPAPI!SetupDiCreateDeviceInfoList` at `0x18003452d`
- `SETUPAPI!SetupDiCreateDeviceInfoList` at `0x18003452d`
- `SETUPAPI!SetupTermDefaultQueueCallback` at `0x180034731`
- `SETUPAPI!SetupTermDefaultQueueCallback` at `0x180034731`
- `SETUPAPI!SetupCloseFileQueue` at `0x18003473f`
- `SETUPAPI!SetupCloseFileQueue` at `0x18003473f`
- `SETUPAPI!SetupInitDefaultQueueCallback` at `0x1800346b4`
- `SETUPAPI!SetupInitDefaultQueueCallback` at `0x1800346b4`

## string_xrefs

- `0x180034716`: `PSetupInstallClassDriver failure: hr: 0x%x`
- `0x1800345a3`: `PSetupInstallClassDriver`
- `0x18003471d`: `PSetupInstallClassDriver`

## pseudocode

```c
__int64 __fastcall PSetupInstallClassDriver(HLOCAL **a1, const WCHAR *a2, unsigned __int16 *a3)
{
  __int64 LastErrorAsFailHR; // rbx
  __int64 DeviceInfoList; // r15
  NCoreLibrary *v9; // rcx
  NCoreLibrary *v10; // rcx
  NCoreLibrary *v11; // rcx
  __int64 v12; // rax
  int v13; // edx
  NCoreLibrary *v14; // rcx
  int v15; // r8d
  unsigned int v16; // ebx
  __int64 v17; // rsi
  __int64 v18; // rsi
  NCoreLibrary *v19; // rcx
  PVOID inited; // r14
  NCoreLibrary *v21; // rcx
  bool v22; // [rsp+30h] [rbp-D0h] BYREF
  int v23[3]; // [rsp+34h] [rbp-CCh] BYREF
  _BYTE v24[8]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v25; // [rsp+48h] [rbp-B8h]
  PVOID v26; // [rsp+50h] [rbp-B0h]
  HLOCAL *v27; // [rsp+60h] [rbp-A0h]
  unsigned __int16 v28[264]; // [rsp+90h] [rbp-70h] BYREF

  if ( !a1 || !a2 || (LODWORD(LastErrorAsFailHR) = 0, !a3) )
    LODWORD(LastErrorAsFailHR) = -2147024809;
  *a1 = 0;
  if ( PrintCore::WindowsProtectedPrintHelpers::IsWindowsProtectedPrintEnabled() )
    return 2147943660LL;
  DeviceInfoList = -1;
  if ( (int)LastErrorAsFailHR >= 0 )
  {
    DeviceInfoList = (__int64)SetupDiCreateDeviceInfoList(&GUID_DEVCLASS_PRINTER, HWND_MESSAGE|0x2LL);
    if ( DeviceInfoList != -1
      || (LODWORD(LastErrorAsFailHR) = NCoreLibrary::GetLastErrorAsFailHR(v9), (int)LastErrorAsFailHR >= 0) )
    {
      if ( (unsigned int)PSetupBuildDriversFromPath((HDEVINFO)DeviceInfoList, a3)
        || (LODWORD(LastErrorAsFailHR) = NCoreLibrary::GetLastErrorAsFailHR(v10), (int)LastErrorAsFailHR >= 0) )
      {
        if ( (unsigned int)PreSelectDriverEx(DeviceInfoList, 0, a2, MyPlatform, 1)
          || (LastErrorAsFailHR = (unsigned int)NCoreLibrary::GetLastErrorAsFailHR(v11),
              ClassInstallerTelemetry::WriteDbgTraceError(
                "PSetupInstallClassDriver",
                L"Driver '%ws' from WU could not be found or is not a class driver: hr: 0x%x",
                a2,
                LastErrorAsFailHR),
              (int)LastErrorAsFailHR >= 0) )
        {
          v12 = BuildInternalData(DeviceInfoList, 0);
          *a1 = (HLOCAL *)v12;
          if ( !v12 )
            LODWORD(LastErrorAsFailHR) = NCoreLibrary::GetLastErrorAsFailHR(v14);
          if ( (int)LastErrorAsFailHR >= 0 )
          {
            v16 = 0;
            v23[0] = 260;
            v22 = 0;
            NSecurityLibrary::TSidUserContext::TSidUserContext((NSecurityLibrary::TSidUserContext *)v24, v13, v15);
            if ( (int)NSecurityLibrary::TSidUserContext::IsLocalSystem((NSecurityLibrary::TSidUserContext *)v24, &v22) >= 0
              && v22 )
            {
              v16 = 64;
            }
            LODWORD(LastErrorAsFailHR) = DriverStoreAddDriverPackageW(
                                           **a1,
                                           v16,
                                           0,
                                           (unsigned __int16)word_180047CE4[4 * MyPlatform],
                                           v28,
                                           v23);
            if ( (int)LastErrorAsFailHR >= 0 && v23[0] )
            {
              v17 = AllocStr(v28);
              if ( v17 )
              {
                LocalFree(**a1);
                **a1 = (HLOCAL)v17;
              }
              else
              {
                LODWORD(LastErrorAsFailHR) = -2147024882;
              }
            }
            NSecurityLibrary::TSidUserContext::~TSidUserContext((NSecurityLibrary::TSidUserContext *)v24);
          }
        }
      }
    }
  }
  v18 = -1;
  if ( (int)LastErrorAsFailHR >= 0 )
  {
    v18 = (__int64)SetupOpenFileQueue();
    if ( v18 == -1 )
      LODWORD(LastErrorAsFailHR) = NCoreLibrary::GetLastErrorAsFailHR(v19);
  }
  inited = 0;
  if ( (int)LastErrorAsFailHR < 0 )
    goto LABEL_45;
  inited = SetupInitDefaultQueueCallback(HWND_MESSAGE|0x2LL);
  if ( !inited )
    LODWORD(LastErrorAsFailHR) = NCoreLibrary::GetLastErrorAsFailHR(v21);
  if ( (int)LastErrorAsFailHR < 0
    || (memset_0(v24, 0, 0x50u),
        v27 = *a1,
        v25 = v18,
        v26 = inited,
        LODWORD(LastErrorAsFailHR) = InstallV4Driver((struct _SETUP_CONTEXT *)v24),
        (int)LastErrorAsFailHR < 0) )
  {
LABEL_45:
    if ( *a1 )
    {
      DestroyLocalData(*a1);
      *a1 = 0;
      ClassInstallerTelemetry::WriteDbgTraceError(
        "PSetupInstallClassDriver",
        L"PSetupInstallClassDriver failure: hr: 0x%x",
        (unsigned int)LastErrorAsFailHR);
    }
  }
  if ( inited )
    SetupTermDefaultQueueCallback(inited);
  if ( v18 != -1 )
    SetupCloseFileQueue((HSPFILEQ)v18);
  if ( DeviceInfoList != -1 )
    SetupDiDestroyDeviceInfoList((HDEVINFO)DeviceInfoList);
  return (unsigned int)LastErrorAsFailHR;
}

```

## disassembly

```asm
0x1800344b0  push    rbp
0x1800344b2  push    rbx
0x1800344b3  push    rsi
0x1800344b4  push    rdi
0x1800344b5  push    r13
0x1800344b7  push    r14
0x1800344b9  push    r15
0x1800344bb  lea     rbp, [rsp-1B0h]
0x1800344c3  sub     rsp, 2B0h
0x1800344ca  mov     rax, cs:__security_cookie
0x1800344d1  xor     rax, rsp
0x1800344d4  mov     [rbp+1E0h+var_40], rax
0x1800344db  mov     r14, r8
0x1800344de  mov     rsi, rdx
0x1800344e1  mov     rdi, rcx
0x1800344e4  test    rcx, rcx
0x1800344e7  jz      short loc_1800344F5
0x1800344e9  test    rdx, rdx
0x1800344ec  jz      short loc_1800344F5
0x1800344ee  xor     ebx, ebx
0x1800344f0  test    r8, r8
0x1800344f3  jnz     short loc_1800344FA
0x1800344f5  mov     ebx, 80070057h
0x1800344fa  mov     qword ptr [rcx], 0
0x180034501  call    ?IsWindowsProtectedPrintEnabled@WindowsProtectedPrintHelpers@PrintCore@@SA_NXZ; PrintCore::WindowsProtectedPrintHelpers::IsWindowsProtectedPrintEnabled(void)
0x180034506  test    al, al
0x180034508  jz      short loc_180034514
0x18003450a  mov     eax, 800704ECh
0x18003450f  jmp     loc_180034755
0x180034514  or      r13, 0FFFFFFFFFFFFFFFFh
0x180034518  mov     r15, r13
0x18003451b  test    ebx, ebx
0x18003451d  js      loc_18003468E
0x180034523  mov     rdx, r13; hwndParent
0x180034526  lea     rcx, GUID_DEVCLASS_PRINTER; ClassGuid
0x18003452d  call    cs:__imp_SetupDiCreateDeviceInfoList
0x180034533  mov     r15, rax
0x180034536  cmp     rax, r13
0x180034539  jnz     short loc_18003454A
0x18003453b  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x180034540  mov     ebx, eax
0x180034542  test    eax, eax
0x180034544  js      loc_18003468E
0x18003454a  xor     r8d, r8d
0x18003454d  mov     rdx, r14; unsigned __int16 *
0x180034550  mov     rcx, r15; DeviceInfoSet
0x180034553  call    PSetupBuildDriversFromPath
0x180034558  test    eax, eax
0x18003455a  jnz     short loc_18003456B
0x18003455c  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x180034561  mov     ebx, eax
0x180034563  test    eax, eax
0x180034565  js      loc_18003468E
0x18003456b  mov     eax, cs:MyPlatform
0x180034571  xor     r9d, r9d
0x180034574  mov     [rsp+2E0h+var_2B8], 1; int
0x18003457c  mov     r8, rsi; LPCWSTR
0x18003457f  xor     edx, edx; lpString1
0x180034581  mov     [rsp+2E0h+var_2C0], eax; int
0x180034585  mov     rcx, r15; int
0x180034588  call    PreSelectDriverEx
0x18003458d  test    eax, eax
0x18003458f  jnz     short loc_1800345B9
0x180034591  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x180034596  mov     r9d, eax
0x180034599  lea     rdx, aDriverWsFromWu; "Driver '%ws' from WU could not be found"...
0x1800345a0  mov     r8, rsi
0x1800345a3  lea     rcx, aPsetupinstallc; "PSetupInstallClassDriver"
0x1800345aa  mov     ebx, eax
0x1800345ac  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800345b1  test    ebx, ebx
0x1800345b3  js      loc_18003468E
0x1800345b9  mov     r8d, cs:MyPlatform
0x1800345c0  xor     edx, edx; int
0x1800345c2  mov     rcx, r15; int
0x1800345c5  call    BuildInternalData
0x1800345ca  mov     [rdi], rax
0x1800345cd  test    rax, rax
0x1800345d0  jnz     short loc_1800345D9
0x1800345d2  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x1800345d7  mov     ebx, eax
0x1800345d9  test    ebx, ebx
0x1800345db  js      loc_18003468E
0x1800345e1  xor     ebx, ebx
0x1800345e3  mov     [rsp+2E0h+var_2AC], 104h
0x1800345eb  lea     rcx, [rsp+2E0h+var_2A0]; this
0x1800345f0  mov     [rsp+2E0h+var_2B0], bl
0x1800345f4  call    ??0TSidUserContext@NSecurityLibrary@@QEAA@HH@Z; NSecurityLibrary::TSidUserContext::TSidUserContext(int,int)
0x1800345f9  lea     rdx, [rsp+2E0h+var_2B0]; bool *
0x1800345fe  lea     rcx, [rsp+2E0h+var_2A0]; this
0x180034603  call    ?IsLocalSystem@TSidUserContext@NSecurityLibrary@@QEBAJPEA_N@Z; NSecurityLibrary::TSidUserContext::IsLocalSystem(bool *)
0x180034608  test    eax, eax
0x18003460a  js      short loc_180034616
0x18003460c  cmp     [rsp+2E0h+var_2B0], bl
0x180034610  lea     eax, [rbx+40h]
0x180034613  cmovnz  ebx, eax
0x180034616  movsxd  r9, cs:MyPlatform
0x18003461d  lea     rdx, word_180047CE4
0x180034624  mov     rcx, [rdi]
0x180034627  lea     rax, [rsp+2E0h+var_2AC]
0x18003462c  mov     qword ptr [rsp+2E0h+var_2B8], rax
0x180034631  xor     r8d, r8d
0x180034634  lea     rax, [rbp+1E0h+var_250]
0x180034638  movzx   r9d, word ptr [rdx+r9*8]
0x18003463d  mov     edx, ebx
0x18003463f  mov     rcx, [rcx]
0x180034642  mov     qword ptr [rsp+2E0h+var_2C0], rax
0x180034647  call    cs:__imp_DriverStoreAddDriverPackageW
0x18003464d  mov     ebx, eax
0x18003464f  test    eax, eax
0x180034651  js      short loc_180034684
0x180034653  cmp     [rsp+2E0h+var_2AC], 0
0x180034658  jbe     short loc_180034684
0x18003465a  lea     rcx, [rbp+1E0h+var_250]; unsigned __int16 *
0x18003465e  call    AllocStr
0x180034663  mov     rsi, rax
0x180034666  test    rax, rax
0x180034669  jnz     short loc_180034672
0x18003466b  mov     ebx, 8007000Eh
0x180034670  jmp     short loc_180034684
0x180034672  mov     rcx, [rdi]
0x180034675  mov     rcx, [rcx]; hMem
0x180034678  call    cs:__imp_LocalFree
0x18003467e  mov     rax, [rdi]
0x180034681  mov     [rax], rsi
0x180034684  lea     rcx, [rsp+2E0h+var_2A0]; this
0x180034689  call    ??1TSidUserContext@NSecurityLibrary@@UEAA@XZ; NSecurityLibrary::TSidUserContext::~TSidUserContext(void)
0x18003468e  mov     rsi, r13
0x180034691  test    ebx, ebx
0x180034693  js      short loc_1800346AA
0x180034695  call    cs:__imp_SetupOpenFileQueue
0x18003469b  mov     rsi, rax
0x18003469e  cmp     rax, r13
0x1800346a1  jnz     short loc_1800346AA
0x1800346a3  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x1800346a8  mov     ebx, eax
0x1800346aa  xor     r14d, r14d
0x1800346ad  test    ebx, ebx
0x1800346af  js      short loc_1800346FF
0x1800346b1  mov     rcx, r13; OwnerWindow
0x1800346b4  call    cs:__imp_SetupInitDefaultQueueCallback
0x1800346ba  mov     r14, rax
0x1800346bd  test    rax, rax
0x1800346c0  jnz     short loc_1800346C9
0x1800346c2  call    ?GetLastErrorAsFailHR@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHR(void)
0x1800346c7  mov     ebx, eax
0x1800346c9  test    ebx, ebx
0x1800346cb  js      short loc_1800346FF
0x1800346cd  xor     edx, edx; Val
0x1800346cf  lea     rcx, [rsp+2E0h+var_2A0]; void *
0x1800346d4  lea     r8d, [rdx+50h]; Size
0x1800346d8  call    memset_0
0x1800346dd  mov     rax, [rdi]
0x1800346e0  lea     rcx, [rsp+2E0h+var_2A0]; struct _SETUP_CONTEXT *
0x1800346e5  mov     [rsp+2E0h+var_280], rax
0x1800346ea  mov     [rsp+2E0h+var_298], rsi
0x1800346ef  mov     [rsp+2E0h+var_290], r14
0x1800346f4  call    InstallV4Driver
0x1800346f9  mov     ebx, eax
0x1800346fb  test    eax, eax
0x1800346fd  jns     short loc_180034729
0x1800346ff  mov     rcx, [rdi]; hMem
0x180034702  test    rcx, rcx
0x180034705  jz      short loc_180034729
0x180034707  call    DestroyLocalData
0x18003470c  mov     r8d, ebx
0x18003470f  mov     qword ptr [rdi], 0
0x180034716  lea     rdx, aPsetupinstallc_0; "PSetupInstallClassDriver failure: hr: 0"...
0x18003471d  lea     rcx, aPsetupinstallc; "PSetupInstallClassDriver"
0x180034724  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180034729  test    r14, r14
0x18003472c  jz      short loc_180034737
0x18003472e  mov     rcx, r14; Context
0x180034731  call    cs:__imp_SetupTermDefaultQueueCallback
0x180034737  cmp     rsi, r13
0x18003473a  jz      short loc_180034745
0x18003473c  mov     rcx, rsi; QueueHandle
0x18003473f  call    cs:__imp_SetupCloseFileQueue
0x180034745  cmp     r15, r13
0x180034748  jz      short loc_180034753
0x18003474a  mov     rcx, r15; DeviceInfoSet
0x18003474d  call    cs:__imp_SetupDiDestroyDeviceInfoList
0x180034753  mov     eax, ebx
0x180034755  mov     rcx, [rbp+1E0h+var_40]
0x18003475c  xor     rcx, rsp; StackCookie
0x18003475f  call    __security_check_cookie
0x180034764  add     rsp, 2B0h
0x18003476b  pop     r15
0x18003476d  pop     r14
0x18003476f  pop     r13
0x180034771  pop     rdi
0x180034772  pop     rsi
0x180034773  pop     rbx
0x180034774  pop     rbp
0x180034775  retn
```
