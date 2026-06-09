# NPackageInstallLocalspl::TLinkedDriverEnvironment::CreateDriverPackageList(NCoreLibrary::TList<NCoreLibrary::TLinkedString> &)

- ea: `0x1800acfb4`
- end: `0x1800ad3fe`
- name: `?CreateDriverPackageList@TLinkedDriverEnvironment@NPackageInstallLocalspl@@AEAAJAEAV?$TList@VTLinkedString@NCoreLibrary@@@NCoreLibrary@@@Z`
- size: `1098`
- prototype: `__int64 __fastcall(struct NPackageInstallLocalspl::TLinkedDriverEnvironment *)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, registry_config, loader_planting, installer_update`

## callers

- `0x18000fc48`

## callees

- `0x180016128`
- `0x180016ebc`
- `0x180016fb0`
- `0x18001776c`
- `0x180017920`
- `0x18001fb10`
- `0x1800205f8`
- `0x180025cd8`
- `0x18003ea2c`
- `0x180046650`
- `0x180046a5c`
- `0x180047330`
- `0x180054638`
- `0x18009ef20`
- `0x18009ef60`
- `0x1800acfb4`
- `0x1800b9a34`
- `0x1800ccbd8`
- `0x1800e6010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ad1c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ad1c2`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800ad1a3`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800ad1a3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ad344`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ad3b0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ad344`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ad3b0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ad0bf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ad0bf`
- `SPOOLSS!DllFreeSplMem` at `0x1800ad32b`
- `SPOOLSS!DllFreeSplMem` at `0x1800ad339`
- `SPOOLSS!DllFreeSplMem` at `0x1800ad32b`
- `SPOOLSS!DllFreeSplMem` at `0x1800ad339`

## string_xrefs

- `0x1800ad2a4`: `NPackageInstallLocalspl::TLinkedDriverEnvironment::CreateDriverPackageList`
- `0x1800ad2e9`: `NPackageInstallLocalspl::TLinkedDriverEnvironment::CreateDriverPackageList`
- `0x1800ad3c5`: `NPackageInstallLocalspl::TLinkedDriverEnvironment::CreateDriverPackageList`
- `0x1800ad2e2`: `Failed to create Driver Package for %ws`
- `0x1800ad3be`: `Failed to create driver package list for environment '%ws'`
- `0x1800ad101`: `CabPath`
- `0x1800ad152`: `DriverStorePath`

## pseudocode

```c
__int64 __fastcall NPackageInstallLocalspl::TLinkedDriverEnvironment::CreateDriverPackageList(
        struct NPackageInstallLocalspl::TLinkedDriverEnvironment *a1,
        __int64 a2)
{
  __int64 v2; // r14
  __int64 v4; // rdx
  signed int SubKeyUnderPackageInstallation; // ebx
  unsigned __int16 *v6; // r12
  unsigned int v7; // eax
  int v8; // eax
  unsigned __int16 *v9; // rsi
  LSTATUS v10; // eax
  bool v11; // sf
  bool v12; // sf
  NPackageInstallLocalspl::TLinkedDriverEnvironment *v13; // rcx
  struct SplLogType *v14; // rax
  int v15; // r14d
  _DWORD *v16; // rax
  void (__fastcall ***v17)(_QWORD, __int64); // rdi
  NPackageInstallLocalspl::TLinkedDriverEnvironment *v18; // rcx
  void **v20; // [rsp+28h] [rbp-D8h]
  unsigned int v21; // [rsp+28h] [rbp-D8h]
  struct _INISPOOLER *v22; // [rsp+30h] [rbp-D0h]
  const unsigned __int16 *v23; // [rsp+38h] [rbp-C8h]
  unsigned int v24; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v25; // [rsp+54h] [rbp-ACh]
  LPCWSTR lpFileName; // [rsp+58h] [rbp-A8h]
  unsigned int v27; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v28; // [rsp+64h] [rbp-9Ch] BYREF
  HKEY phkResult; // [rsp+68h] [rbp-98h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 *v31; // [rsp+78h] [rbp-88h] BYREF
  __int64 v32; // [rsp+80h] [rbp-80h]
  int v33; // [rsp+88h] [rbp-78h] BYREF
  __int64 v34; // [rsp+90h] [rbp-70h]
  int v35; // [rsp+98h] [rbp-68h]
  DWORD LastError; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v37; // [rsp+A8h] [rbp-58h]
  int v38; // [rsp+B0h] [rbp-50h]
  int v39; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v40; // [rsp+C0h] [rbp-40h]
  int v41; // [rsp+C8h] [rbp-38h]
  _QWORD v42[2]; // [rsp+D0h] [rbp-30h] BYREF
  int v43; // [rsp+E0h] [rbp-20h]
  _BYTE v44[24]; // [rsp+E8h] [rbp-18h] BYREF
  WCHAR SubKey[264]; // [rsp+100h] [rbp+0h] BYREF

  v2 = a2;
  v32 = a2;
  hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  memset_0(SubKey, 0, 0x208u);
  v4 = *((_QWORD *)a1 + 6);
  v28 = 260;
  if ( !v4 )
  {
    SubKeyUnderPackageInstallation = -2147024809;
    goto LABEL_53;
  }
  v6 = *(unsigned __int16 **)(*((_QWORD *)a1 + 24) + 72LL);
  SubKeyUnderPackageInstallation = NPackageInstallLocalspl::GetSubKeyUnderPackageInstallation(
                                     0,
                                     v4,
                                     L"DriverPackages",
                                     v6,
                                     (struct _INISPOOLER *)&hKey,
                                     v20);
  if ( SubKeyUnderPackageInstallation < 0 )
  {
LABEL_53:
    LocalSpoolerTelemetry::WriteDbgTraceError(
      "NPackageInstallLocalspl::TLinkedDriverEnvironment::CreateDriverPackageList",
      L"Failed to create driver package list for environment '%ws'",
      *((_QWORD *)a1 + 6));
    return (unsigned int)SubKeyUnderPackageInstallation;
  }
  v7 = 0;
  phkResult = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  v25 = 0;
  v27 = 0;
  while ( 1 )
  {
    v8 = SplRegEnumKey(hKey, v7, SubKey, &v28, 0, (struct _INISPOOLER *)v6);
    SubKeyUnderPackageInstallation = v8;
    if ( v8 )
      break;
    v9 = 0;
    v31 = 0;
    lpFileName = 0;
    v10 = RegOpenKeyExW(hKey, SubKey, 0, 0x20019u, &phkResult);
    v24 = v10;
    SubKeyUnderPackageInstallation = v10;
    if ( v10 > 0 )
      SubKeyUnderPackageInstallation = (unsigned __int16)v10 | 0x80070000;
    if ( SubKeyUnderPackageInstallation < 0 )
      goto LABEL_44;
    if ( (unsigned int)RegGetString(phkResult, L"CabPath", (__int64)&v24, 1, (struct _INISPOOLER *)v6) )
      goto LABEL_57;
    v11 = (v24 & 0x80000000) != 0;
    if ( v24 )
    {
      if ( (int)v24 > 0 )
        v11 = 1;
      if ( !v11 )
      {
LABEL_57:
        if ( (unsigned int)NPackageInstallLocalspl::TDriverStore::RegGetInfPath(
                             phkResult,
                             L"DriverStorePath",
                             &v31,
                             &v27,
                             &v24,
                             v21,
                             (const unsigned __int16 *)v22,
                             v23,
                             (struct _INISPOOLER *)v6) )
        {
          SubKeyUnderPackageInstallation = 0;
LABEL_20:
          v9 = v31;
          if ( (unsigned int)NCoreLibrary::IsStringInStringList(v31, v2) == 1 )
          {
            if ( !DeleteFileW(lpFileName) )
            {
              v33 = 104;
              v34 = 4;
              v35 = 0;
              LastError = GetLastError();
              v42[0] = L"-";
              v37 = 4;
              v38 = 0;
              v39 = 0;
              v40 = 4;
              v41 = 0;
              v42[1] = 4;
              v43 = 1;
              v14 = SplLogType::SplLogType((SplLogType *)v44, lpFileName);
              SplLogEvent2(&SPOOLER_DELETE_FILE_FAILED, v14, v42, &v39, &LastError, &v33, 0);
            }
            NPackageInstallLocalspl::TLinkedDriverEnvironment::SetPackageLock(v13, v9, 0);
            v15 = 1;
LABEL_34:
            if ( SubKeyUnderPackageInstallation >= 0 )
              goto LABEL_38;
            goto LABEL_37;
          }
          v15 = 0;
          v31 = (unsigned __int16 *)operator new(0x48u);
          v16 = (_DWORD *)NPackageInstallLocalspl::TLinkedDriverPackage::TLinkedDriverPackage(
                            (NPackageInstallLocalspl::TLinkedDriverPackage *)v31,
                            v9,
                            lpFileName,
                            SubKey,
                            a1);
          v17 = (void (__fastcall ***)(_QWORD, __int64))v16;
          if ( v16 )
          {
            SubKeyUnderPackageInstallation = v16[9];
            if ( SubKeyUnderPackageInstallation >= 0 )
            {
              if ( !(unsigned int)NPackageInstallLocalspl::TLinkedDriverPackage::IsDriverPackageAvailable((NPackageInstallLocalspl::TLinkedDriverPackage *)v16) )
              {
                LocalSpoolerTelemetry::WriteDbgTraceWarning(
                  "NPackageInstallLocalspl::TLinkedDriverEnvironment::CreateDriverPackageList",
                  L"Driver Package not available - ignoring: %ws",
                  SubKey);
                v15 = 1;
LABEL_33:
                (**v17)(v17, 1);
                goto LABEL_34;
              }
              NPackageInstallLocalspl::TLinkedDriverEnvironment::SetPackageLock(v18, v9, 1);
              SubKeyUnderPackageInstallation = NCoreLibrary::TList<NThreadingLibrary::TWorkItem>::AddAtTail(
                                                 (char *)a1 + 112,
                                                 v17);
              if ( SubKeyUnderPackageInstallation < 0 )
                goto LABEL_33;
              v17 = 0;
LABEL_32:
              if ( !v17 )
                goto LABEL_34;
              goto LABEL_33;
            }
          }
          else
          {
            SubKeyUnderPackageInstallation = -2147024882;
          }
          LocalSpoolerTelemetry::WriteDbgTraceWarning(
            "NPackageInstallLocalspl::TLinkedDriverEnvironment::CreateDriverPackageList",
            L"Failed to create Driver Package for %ws",
            SubKey);
          goto LABEL_32;
        }
        SubKeyUnderPackageInstallation = v24;
        v12 = (v24 & 0x80000000) != 0;
        if ( v24 )
        {
          if ( (int)v24 > 0 )
          {
            SubKeyUnderPackageInstallation = (unsigned __int16)v24 | 0x80070000;
            v12 = 1;
          }
          if ( !v12 )
            goto LABEL_20;
        }
        v9 = v31;
      }
    }
LABEL_37:
    SubKeyUnderPackageInstallation = 0;
    v15 = 1;
LABEL_38:
    if ( lpFileName )
      DllFreeSplMem(lpFileName);
    if ( v9 )
      DllFreeSplMem(v9);
    RegCloseKey(phkResult);
    phkResult = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
    if ( v15 && !(unsigned int)SplRegDeleteKey(hKey, SubKey, (struct _INISPOOLER *)v6) )
    {
      v7 = v25;
      goto LABEL_46;
    }
LABEL_44:
    v7 = ++v25;
LABEL_46:
    v2 = v32;
    v28 = 260;
    if ( SubKeyUnderPackageInstallation < 0 )
      goto LABEL_52;
  }
  if ( v8 == 259 )
  {
    SubKeyUnderPackageInstallation = 0;
  }
  else if ( v8 > 0 )
  {
    SubKeyUnderPackageInstallation = (unsigned __int16)v8 | 0x80070000;
  }
LABEL_52:
  RegCloseKey(hKey);
  if ( SubKeyUnderPackageInstallation < 0 )
    goto LABEL_53;
  return (unsigned int)SubKeyUnderPackageInstallation;
}

```

## disassembly

```asm
0x1800acfb4  mov     [rsp-8+arg_10], rbx
0x1800acfb9  mov     [rsp-8+arg_18], rsi
0x1800acfbe  push    rbp
0x1800acfbf  push    rdi
0x1800acfc0  push    r12
0x1800acfc2  push    r13
0x1800acfc4  push    r14
0x1800acfc6  lea     rbp, [rsp-220h]
0x1800acfce  sub     rsp, 320h
0x1800acfd5  mov     rax, cs:__security_cookie
0x1800acfdc  xor     rax, rsp
0x1800acfdf  mov     [rbp+240h+var_30], rax
0x1800acfe6  mov     r14, rdx
0x1800acfe9  mov     [rbp+240h+var_2C0], rdx
0x1800acfed  mov     r13, rcx
0x1800acff0  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800acff4  xor     edx, edx; Val
0x1800acff6  mov     [rsp+340h+hKey], rdi
0x1800acffb  lea     rcx, [rbp+240h+SubKey]; void *
0x1800acfff  mov     r8d, 208h; Size
0x1800ad005  call    memset_0
0x1800ad00a  mov     rdx, [r13+30h]; int
0x1800ad00e  mov     [rsp+340h+var_2DC], 104h
0x1800ad016  test    rdx, rdx
0x1800ad019  jnz     short loc_1800AD025
0x1800ad01b  mov     ebx, 80070057h
0x1800ad020  jmp     loc_1800AD3BA
0x1800ad025  mov     rax, [r13+0C0h]
0x1800ad02c  lea     r8, aDriverpackages; "DriverPackages"
0x1800ad033  xor     ecx, ecx; this
0x1800ad035  mov     r12, [rax+48h]
0x1800ad039  lea     rax, [rsp+340h+hKey]
0x1800ad03e  mov     r9, r12; unsigned __int16 *
0x1800ad041  mov     [rsp+340h+phkResult], rax; struct _INISPOOLER *
0x1800ad046  call    ?GetSubKeyUnderPackageInstallation@NPackageInstallLocalspl@@YAJHPEBG0PEAU_INISPOOLER@@PEAPEAX@Z; NPackageInstallLocalspl::GetSubKeyUnderPackageInstallation(int,ushort const *,ushort const *,_INISPOOLER *,void * *)
0x1800ad04b  mov     ebx, eax
0x1800ad04d  test    eax, eax
0x1800ad04f  js      loc_1800AD3BA
0x1800ad055  xor     eax, eax
0x1800ad057  mov     [rsp+340h+var_2D8], rdi
0x1800ad05c  mov     [rsp+340h+var_2EC], eax
0x1800ad060  mov     [rsp+340h+var_2E0], eax
0x1800ad064  mov     rcx, [rsp+340h+hKey]; void *
0x1800ad069  lea     r9, [rsp+340h+var_2DC]; unsigned int *
0x1800ad06e  mov     [rsp+340h+var_318], r12; struct _INISPOOLER *
0x1800ad073  lea     r8, [rbp+240h+SubKey]; unsigned __int16 *
0x1800ad077  mov     edx, eax; unsigned int
0x1800ad079  mov     [rsp+340h+phkResult], 0; struct _FILETIME *
0x1800ad082  mov     edi, ebx
0x1800ad084  call    ?SplRegEnumKey@@YAJPEAXKPEAGPEAKPEAU_FILETIME@@PEAU_INISPOOLER@@@Z; SplRegEnumKey(void *,ulong,ushort *,ulong *,_FILETIME *,_INISPOOLER *)
0x1800ad089  mov     ebx, eax
0x1800ad08b  test    eax, eax
0x1800ad08d  jnz     loc_1800AD393
0x1800ad093  mov     rcx, [rsp+340h+hKey]; hKey
0x1800ad098  lea     rax, [rsp+340h+var_2D8]
0x1800ad09d  xor     esi, esi
0x1800ad09f  mov     [rsp+340h+phkResult], rax; phkResult
0x1800ad0a4  mov     r9d, 20019h; samDesired
0x1800ad0aa  mov     [rsp+340h+var_2C8], rsi
0x1800ad0af  xor     r8d, r8d; ulOptions
0x1800ad0b2  mov     [rsp+340h+lpFileName], 0
0x1800ad0bb  lea     rdx, [rbp+240h+SubKey]; lpSubKey
0x1800ad0bf  call    cs:__imp_RegOpenKeyExW
0x1800ad0c5  mov     [rsp+340h+var_2F0], eax
0x1800ad0c9  mov     ebx, eax
0x1800ad0cb  test    eax, eax
0x1800ad0cd  jle     short loc_1800AD0D8
0x1800ad0cf  movzx   ebx, ax
0x1800ad0d2  or      ebx, 80070000h
0x1800ad0d8  test    ebx, ebx
0x1800ad0da  js      loc_1800AD36D
0x1800ad0e0  mov     rcx, [rsp+340h+var_2D8]; void *
0x1800ad0e5  lea     rax, [rsp+340h+var_2F0]
0x1800ad0ea  mov     [rsp+340h+var_310], r12; unsigned __int16 *
0x1800ad0ef  lea     r9, [rsp+340h+var_2E0]
0x1800ad0f4  mov     dword ptr [rsp+340h+var_318], 1; unsigned int
0x1800ad0fc  lea     r8, [rsp+340h+lpFileName]
0x1800ad101  lea     rdx, aCabpath; "CabPath"
0x1800ad108  mov     [rsp+340h+phkResult], rax; __int64
0x1800ad10d  call    RegGetString
0x1800ad112  test    eax, eax
0x1800ad114  jnz     short loc_1800AD134
0x1800ad116  mov     eax, [rsp+340h+var_2F0]
0x1800ad11a  test    eax, eax
0x1800ad11c  jz      loc_1800AD318
0x1800ad122  jle     short loc_1800AD12E
0x1800ad124  movzx   eax, ax
0x1800ad127  or      eax, 80070000h
0x1800ad12c  test    eax, eax
0x1800ad12e  js      loc_1800AD318
0x1800ad134  mov     rcx, [rsp+340h+var_2D8]; void *
0x1800ad139  lea     rax, [rsp+340h+var_2F0]
0x1800ad13e  mov     [rsp+340h+var_300], r12; struct _INISPOOLER *
0x1800ad143  lea     r9, [rsp+340h+var_2E0]; unsigned int *
0x1800ad148  lea     r8, [rsp+340h+var_2C8]; unsigned __int16 **
0x1800ad14d  mov     [rsp+340h+phkResult], rax; unsigned int *
0x1800ad152  lea     rdx, aDriverstorepat; "DriverStorePath"
0x1800ad159  call    ?RegGetInfPath@TDriverStore@NPackageInstallLocalspl@@SAHPEAXPEBGPEAPEAGPEAK3H11PEAU_INISPOOLER@@@Z; NPackageInstallLocalspl::TDriverStore::RegGetInfPath(void *,ushort const *,ushort * *,ulong *,ulong *,int,ushort const *,ushort const *,_INISPOOLER *)
0x1800ad15e  test    eax, eax
0x1800ad160  jz      short loc_1800AD166
0x1800ad162  xor     ebx, ebx
0x1800ad164  jmp     short loc_1800AD185
0x1800ad166  mov     ebx, [rsp+340h+var_2F0]
0x1800ad16a  test    ebx, ebx
0x1800ad16c  jz      loc_1800AD313
0x1800ad172  jle     short loc_1800AD17F
0x1800ad174  movzx   ebx, bx
0x1800ad177  or      ebx, 80070000h
0x1800ad17d  test    ebx, ebx
0x1800ad17f  js      loc_1800AD313
0x1800ad185  mov     rsi, [rsp+340h+var_2C8]
0x1800ad18a  mov     rdx, r14
0x1800ad18d  mov     rcx, rsi
0x1800ad190  call    ?IsStringInStringList@NCoreLibrary@@YAJPEBGAEAV?$TList@VTLinkedString@NCoreLibrary@@@1@@Z; NCoreLibrary::IsStringInStringList(ushort const *,NCoreLibrary::TList<NCoreLibrary::TLinkedString> &)
0x1800ad195  cmp     eax, 1
0x1800ad198  jnz     loc_1800AD254
0x1800ad19e  mov     rcx, [rsp+340h+lpFileName]; lpFileName
0x1800ad1a3  call    cs:__imp_DeleteFileW
0x1800ad1a9  test    eax, eax
0x1800ad1ab  jnz     loc_1800AD23E
0x1800ad1b1  lea     edi, [rax+4]
0x1800ad1b4  mov     [rbp+240h+var_2B8], 68h ; 'h'
0x1800ad1bb  mov     [rbp+240h+var_2B0], rdi
0x1800ad1bf  mov     [rbp+240h+var_2A8], eax
0x1800ad1c2  call    cs:__imp_GetLastError
0x1800ad1c8  mov     rdx, [rsp+340h+lpFileName]; unsigned __int16 *
0x1800ad1cd  lea     rcx, [rbp+240h+var_258]; this
0x1800ad1d1  mov     [rbp+240h+var_2A0], eax
0x1800ad1d4  lea     rax, asc_1800ECF90; "-"
0x1800ad1db  mov     [rbp+240h+var_270], rax
0x1800ad1df  mov     [rbp+240h+var_298], rdi
0x1800ad1e3  mov     [rbp+240h+var_290], 0
0x1800ad1ea  mov     [rbp+240h+var_288], 0
0x1800ad1f1  mov     [rbp+240h+var_280], rdi
0x1800ad1f5  mov     [rbp+240h+var_278], 0
0x1800ad1fc  mov     [rbp+240h+var_268], rdi
0x1800ad200  mov     [rbp+240h+var_260], 1
0x1800ad207  call    ??0SplLogType@@QEAA@PEBG@Z; SplLogType::SplLogType(ushort const *)
0x1800ad20c  lea     rcx, [rbp+240h+var_2B8]
0x1800ad210  mov     [rsp+340h+var_310], 0
0x1800ad219  mov     [rsp+340h+var_318], rcx
0x1800ad21e  lea     r9, [rbp+240h+var_288]
0x1800ad222  lea     rcx, [rbp+240h+var_2A0]
0x1800ad226  mov     rdx, rax; struct SplLogType *
0x1800ad229  mov     [rsp+340h+phkResult], rcx
0x1800ad22e  lea     r8, [rbp+240h+var_270]
0x1800ad232  lea     rcx, SPOOLER_DELETE_FILE_FAILED; struct _EVENT_DESCRIPTOR *
0x1800ad239  call    ?SplLogEvent2@@YAXPEBU_EVENT_DESCRIPTOR@@PEAVSplLogType@@ZZ; SplLogEvent2(_EVENT_DESCRIPTOR const *,SplLogType *,...)
0x1800ad23e  xor     r8d, r8d; bool
0x1800ad241  mov     rdx, rsi; unsigned __int16 *
0x1800ad244  call    ?SetPackageLock@TLinkedDriverEnvironment@NPackageInstallLocalspl@@QEAAJPEBG_N@Z; NPackageInstallLocalspl::TLinkedDriverEnvironment::SetPackageLock(ushort const *,bool)
0x1800ad249  mov     r14d, 1
0x1800ad24f  jmp     loc_1800AD30D
0x1800ad254  xor     r14d, r14d
0x1800ad257  lea     ecx, [r14+48h]; Size
0x1800ad25b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800ad260  mov     [rsp+340h+var_2C8], rax
0x1800ad265  lea     r9, [rbp+240h+SubKey]; unsigned __int16 *
0x1800ad269  mov     r8, [rsp+340h+lpFileName]; unsigned __int16 *
0x1800ad26e  mov     rdx, rsi; unsigned __int16 *
0x1800ad271  mov     rcx, rax; this
0x1800ad274  mov     [rsp+340h+phkResult], r13; struct NPackageInstallLocalspl::TLinkedDriverEnvironment *
0x1800ad279  call    ??0TLinkedDriverPackage@NPackageInstallLocalspl@@QEAA@PEBG00PEAVTLinkedDriverEnvironment@1@@Z; NPackageInstallLocalspl::TLinkedDriverPackage::TLinkedDriverPackage(ushort const *,ushort const *,ushort const *,NPackageInstallLocalspl::TLinkedDriverEnvironment *)
0x1800ad27e  mov     rdi, rax
0x1800ad281  test    rax, rax
0x1800ad284  jz      short loc_1800AD2D9
0x1800ad286  mov     ebx, [rax+24h]
0x1800ad289  test    ebx, ebx
0x1800ad28b  js      short loc_1800AD2DE
0x1800ad28d  mov     rcx, rax; this
0x1800ad290  call    ?IsDriverPackageAvailable@TLinkedDriverPackage@NPackageInstallLocalspl@@QEAAHXZ; NPackageInstallLocalspl::TLinkedDriverPackage::IsDriverPackageAvailable(void)
0x1800ad295  test    eax, eax
0x1800ad297  jnz     short loc_1800AD2B8
0x1800ad299  lea     r8, [rbp+240h+SubKey]
0x1800ad29d  lea     rdx, aDriverPackageN; "Driver Package not available - ignoring"...
0x1800ad2a4  lea     rcx, aNpackageinstal_32; "NPackageInstallLocalspl::TLinkedDriverE"...
0x1800ad2ab  call    ?WriteDbgTraceWarning@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x1800ad2b0  mov     r14d, 1
0x1800ad2b6  jmp     short loc_1800AD2FA
0x1800ad2b8  mov     r8b, 1; bool
0x1800ad2bb  mov     rdx, rsi; unsigned __int16 *
0x1800ad2be  call    ?SetPackageLock@TLinkedDriverEnvironment@NPackageInstallLocalspl@@QEAAJPEBG_N@Z; NPackageInstallLocalspl::TLinkedDriverEnvironment::SetPackageLock(ushort const *,bool)
0x1800ad2c3  lea     rcx, [r13+70h]
0x1800ad2c7  mov     rdx, rdi
0x1800ad2ca  call    ?AddAtTail@?$TList@VTWorkItem@NThreadingLibrary@@@NCoreLibrary@@QEAAJPEAVTLink@2@@Z; NCoreLibrary::TList<NThreadingLibrary::TWorkItem>::AddAtTail(NCoreLibrary::TLink *)
0x1800ad2cf  mov     ebx, eax
0x1800ad2d1  test    eax, eax
0x1800ad2d3  js      short loc_1800AD2FA
0x1800ad2d5  xor     edi, edi
0x1800ad2d7  jmp     short loc_1800AD2F5
0x1800ad2d9  mov     ebx, 8007000Eh
0x1800ad2de  lea     r8, [rbp+240h+SubKey]
0x1800ad2e2  lea     rdx, aFailedToCreate_6; "Failed to create Driver Package for %ws"
0x1800ad2e9  lea     rcx, aNpackageinstal_32; "NPackageInstallLocalspl::TLinkedDriverE"...
0x1800ad2f0  call    ?WriteDbgTraceWarning@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x1800ad2f5  test    rdi, rdi
0x1800ad2f8  jz      short loc_1800AD30D
0x1800ad2fa  mov     rax, [rdi]
0x1800ad2fd  mov     edx, 1
0x1800ad302  mov     rcx, rdi
0x1800ad305  mov     rax, [rax]
0x1800ad308  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad30d  test    ebx, ebx
0x1800ad30f  jns     short loc_1800AD31E
0x1800ad311  jmp     short loc_1800AD318
0x1800ad313  mov     rsi, [rsp+340h+var_2C8]
0x1800ad318  xor     ebx, ebx
0x1800ad31a  lea     r14d, [rbx+1]
0x1800ad31e  cmp     [rsp+340h+lpFileName], 0
0x1800ad324  jz      short loc_1800AD331
0x1800ad326  mov     rcx, [rsp+340h+lpFileName]
0x1800ad32b  call    cs:__imp_DllFreeSplMem
0x1800ad331  test    rsi, rsi
0x1800ad334  jz      short loc_1800AD33F
0x1800ad336  mov     rcx, rsi
0x1800ad339  call    cs:__imp_DllFreeSplMem
0x1800ad33f  mov     rcx, [rsp+340h+var_2D8]; hKey
0x1800ad344  call    cs:__imp_RegCloseKey
0x1800ad34a  mov     [rsp+340h+var_2D8], 0FFFFFFFFFFFFFFFFh
0x1800ad353  test    r14d, r14d
0x1800ad356  jz      short loc_1800AD36D
0x1800ad358  mov     rcx, [rsp+340h+hKey]; void *
0x1800ad35d  lea     rdx, [rbp+240h+SubKey]; unsigned __int16 *
0x1800ad361  mov     r8, r12; struct _INISPOOLER *
0x1800ad364  call    ?SplRegDeleteKey@@YAJPEAXPEBGPEAU_INISPOOLER@@@Z; SplRegDeleteKey(void *,ushort const *,_INISPOOLER *)
0x1800ad369  test    eax, eax
0x1800ad36b  jz      short loc_1800AD379
0x1800ad36d  mov     eax, [rsp+340h+var_2EC]
0x1800ad371  inc     eax
0x1800ad373  mov     [rsp+340h+var_2EC], eax
0x1800ad377  jmp     short loc_1800AD37D
0x1800ad379  mov     eax, [rsp+340h+var_2EC]
0x1800ad37d  mov     r14, [rbp+240h+var_2C0]
0x1800ad381  mov     [rsp+340h+var_2DC], 104h
0x1800ad389  test    ebx, ebx
0x1800ad38b  jns     loc_1800AD064
0x1800ad391  jmp     short loc_1800AD3AB
0x1800ad393  cmp     eax, 103h
0x1800ad398  jnz     short loc_1800AD39E
0x1800ad39a  xor     ebx, ebx
0x1800ad39c  jmp     short loc_1800AD3AB
0x1800ad39e  test    eax, eax
0x1800ad3a0  jle     short loc_1800AD3AB
0x1800ad3a2  movzx   ebx, ax
0x1800ad3a5  or      ebx, 80070000h
0x1800ad3ab  mov     rcx, [rsp+340h+hKey]; hKey
0x1800ad3b0  call    cs:__imp_RegCloseKey
0x1800ad3b6  test    ebx, ebx
0x1800ad3b8  jns     short loc_1800AD3D1
0x1800ad3ba  mov     r8, [r13+30h]
0x1800ad3be  lea     rdx, aFailedToCreate_20; "Failed to create driver package list fo"...
0x1800ad3c5  lea     rcx, aNpackageinstal_32; "NPackageInstallLocalspl::TLinkedDriverE"...
0x1800ad3cc  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800ad3d1  mov     eax, ebx
0x1800ad3d3  mov     rcx, [rbp+240h+var_30]
0x1800ad3da  xor     rcx, rsp; StackCookie
0x1800ad3dd  call    __security_check_cookie
0x1800ad3e2  lea     r11, [rsp+340h+var_20]
0x1800ad3ea  mov     rbx, [r11+40h]
0x1800ad3ee  mov     rsi, [r11+48h]
0x1800ad3f2  mov     rsp, r11
0x1800ad3f5  pop     r14
0x1800ad3f7  pop     r13
0x1800ad3f9  pop     r12
0x1800ad3fb  pop     rdi
0x1800ad3fc  pop     rbp
0x1800ad3fd  retn
```
